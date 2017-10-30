#Sistemas de Informação da Rede Suas

Web services REST que expõem as informações relativas Secretaria Nacional de Assistência Social.


# Guia de desenvolvimento php (API RESTful)

## Sumário

  1. [Introdução](#introdução)
  2. [Requisições](#requisições)
  3. [Respostas](#respostas)
     * [Use namespace em itens sozinhos](#use-namespace-em-itens-sozinhos)
     * [Use namespace para vários itens](#use-namespace-para-vários-itens)
  4. [Variáveis](#variáveis)
     * [Use variáveis pronunciaveis e com significado claro](#use-variáveis-pronunciaveis-e-com-significado-claro)
     * [Use o mesmo vocabulário para o mesmo tipo de variável](#use-o-mesmo-vocabulário-para-o-mesmo-tipo-de-variável)

## Introdução

Padrões de codificação são definições de como estruturar o código em qualquer dado projeto. 
Os padrões se aplicam a tudo, de conversões de nomenclatura a espaços ou códigos de etatus, erros 
e mensagens, requisições e respostas dos dados. Usamos padrões como uma maneira de manter o 
código uniforme em todo o projeto, independentemente do número de desenvolvedores que possam trabalhar nele.

## Requisições

**[⬆ voltar para o topo](#sumário)**

## Respostas

Colocando a coleção no namespace *“data”*, poderemos facilmente acrescentar outro contexto
relacionado à resposta, mas que não é parte da lista de recursos. Contagens, links e etc poderão
fazer parte da resposta. Assim também é possível incorporar outras relações aninhadas em 
seu próprio elemento “data” e até mesmo incluir metadados para essas relações incorporadas. 

### Use namespace em itens sozinhos

```json
{
    "data": {
        "nome": "Philipe Almeida",
        "id": "511501255"
    }
}
```
**[⬆ voltar para o topo](#sumário)**

### Use namespace para vários itens

```json
{
    "data": [
        {
            "nome": "Júlia Costa",
            "id": "100002"
        },
        {
            "nome": "Aline Foley",
            "id": "100003"
        }
    ]
}
```

**[⬆ voltar para o topo](#sumário)**

## Variáveis

### Use variáveis pronunciaveis e com significado claro

**Ruim:**

```php
$dmastr = $data->format('y-m-d');
```

**Bom:**

```php
$dataAtual = $data->format('y-m-d');
```
**[⬆ voltar para o topo](#sumário)**

### Use o mesmo vocabulário para o mesmo tipo de variável

**Ruim:**

```php
getUserInfo();
getUserData();
getUserRecord();
getUserProfile();
```

**Bom:**

```php
getUser();
```

**[⬆ voltar para o topo](#sumário)**

