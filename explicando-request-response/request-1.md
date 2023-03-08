# Proposta

{% hint style="danger" %}
A página de [formulários](../formularios/formulario-proposta.md) explica as informamações que todos os produtos necessitam de enviar para a proposta.

**(vale lembrar que todos produtos possui informações a mais para enviar junto ao json explicado na aba formulários)**
{% endhint %}

<mark style="color:blue;"></mark>

## <mark style="color:blue;">Request</mark>

{% swagger method="post" path="/quotation/proposal" baseUrl="{{url_ambiente}}/v1" summary="Criar Proposta" %}
{% swagger-description %}
Cria uma proposta.
{% endswagger-description %}

{% swagger-parameter in="body" name="identifier" required="true" type="guid" %}
Identificador da cotação.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="operationCode" required="true" type="string" %}
Identificador da operação.\
_<mark style="color:red;">Obrigatório o uso do mesmo código utilizado no processo de cotação.</mark>_\


_O identificador da **operação** de cada produto está localizado na sua seção._
{% endswagger-parameter %}

{% swagger-parameter in="body" name="answers" type="array" required="true" %}
Array de respostas necessárias para a criação da proposta.

\\

\\

_Saiba mais sobre o modelo de objeto de resposta na seção de_

[_**formulários**_](../formularios/)

_._
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Ocp-Apim-Subscription-Key" type="md5" required="true" %}
chave de acesso da api.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Retorno sucesso." %}
```json
{
  "item": {
    "quotationIdentifier": "2aea86d1-a9e5-4220-ab29-68c3fba8483f",
    "status": 0,
    "expiredAt": null,
    "quotationDocumentUrl": null,
    "proposal": {
      "number": "89678023660002",
      "date": "0001-01-01T00:00:00Z"
    },
    "pricing": [
      {
        "variantIdentifier": "92cc00b4-9ba6-4f50-bf5a-38b76ade9370",
        "underwriting": {
          "approved": true,
          "evaluations": []
        },
        "price": {
          "commission": 150.84,
          "grievanceDiscount": 0,
          "itemValue": 11696.4,
          "netValue": 754.22,
          "interestValue": 0,
          "taxValue": 55.66,
          "totalValue": 809.88,
          "policyLimit": 23977.62,
          "rates": [
            {
              "code": "DAMAGE-COVERAGE",
              "description": "Danos à bike",
              "limit": 11696.4,
              "netValue": 122.85,
              "deductible": {
                "code": "INCREASED",
                "text": "Majorada",
                "description": "10% dos prejuízos indenizáveis com o mínimo de R$ 1.100,00"
              }
            },
            {
              "code": "THEFT-COVERAGE",
              "description": "Roubo e/ou furto qualificado",
              "limit": 11696.4,
              "netValue": 343.99,
              "deductible": {
                "code": "INCREASED",
                "text": "Majorada",
                "description": "10% dos prejuízos indenizáveis com o mínimo de R$ 1.100,00"
              }
            },
            {
              "code": "CIVIL-LIABILITY-COVERAGE",
              "description": "Danos Materiais E/ou Corporais a Terceiros (RC)",
              "limit": 11696.4,
              "netValue": 143.69,
              "deductible": {
                "code": "INCREASED",
                "text": "Majorada",
                "description": "R$ 500,00"
              }
            },
            {
              "code": "ACCESSORIES-COVERAGE",
              "description": "Acessórios",
              "limit": 584.82,
              "netValue": 39.19,
              "deductible": {
                "code": "INCREASED",
                "text": "Majorada",
                "description": "15% dos prejuízos indenizáveis com o mínimo de R$ 300,00"
              }
            },
            {
              "code": "INTERNATIONAL-COVERAGE",
              "description": "Cobertura internacional",
              "limit": 11696.4,
              "netValue": 104.5,
              "deductible": {
                "code": "INCREASED",
                "text": "Majorada",
                "description": "Conforme cobertura a ser acionada"
              }
            }
          ]
        },
        "payment": {
          "financialType": "Charge",
          "paymentOptions": [
            {
              "paymentMethod": "All",
              "paymentType": "CreditCard",
              "installments": [
                {
                  "identifier": "ee88a83c-1764-4e28-8272-e27d49d32dc8",
                  "number": 1,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 809.88,
                  "installmentInterest": 0,
                  "installmentTax": 55.66,
                  "dueDates": [
                    "2022-09-22T00:00:00Z"
                  ]
                },
                {
                  "identifier": "572b39db-f139-4dff-96b7-fbb972484b1a",
                  "number": 2,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 404.94,
                  "installmentInterest": 0,
                  "installmentTax": 27.83,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-15T12:00:00Z"
                  ]
                },
                {
                  "identifier": "296a576b-9a49-43af-9408-22850993cf34",
                  "number": 3,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 269.96,
                  "installmentInterest": 0,
                  "installmentTax": 18.55,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z"
                  ]
                },
                {
                  "identifier": "9b341236-7fab-4053-a746-e06cda830af2",
                  "number": 4,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 202.47,
                  "installmentInterest": 0,
                  "installmentTax": 13.92,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z"
                  ]
                },
                {
                  "identifier": "16074860-0465-4695-9211-19c8ad3b1106",
                  "number": 5,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 161.98,
                  "installmentInterest": 0,
                  "installmentTax": 11.13,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z",
                    "2023-01-15T12:00:00Z"
                  ]
                },
                {
                  "identifier": "e7abdcd3-67e2-4538-9319-735adca855e3",
                  "number": 6,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 134.98,
                  "installmentInterest": 0,
                  "installmentTax": 9.28,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z",
                    "2023-01-15T12:00:00Z",
                    "2023-02-15T12:00:00Z"
                  ]
                },
                {
                  "identifier": "a737a7d4-f9b7-4c49-b8f1-e1c9da737204",
                  "number": 7,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 115.7,
                  "installmentInterest": 0,
                  "installmentTax": 7.95,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z",
                    "2023-01-15T12:00:00Z",
                    "2023-02-15T12:00:00Z",
                    "2023-03-15T12:00:00Z"
                  ]
                },
                {
                  "identifier": "321f86b9-3769-4d63-8639-b4f251519d9f",
                  "number": 8,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 101.24,
                  "installmentInterest": 0,
                  "installmentTax": 6.96,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z",
                    "2023-01-15T12:00:00Z",
                    "2023-02-15T12:00:00Z",
                    "2023-03-15T12:00:00Z",
                    "2023-04-15T12:00:00Z"
                  ]
                }
              ]
            },
            {
              "paymentMethod": "Ticket",
              "paymentType": "Ticket",
              "installments": [
                {
                  "identifier": "f8702529-a575-407a-9636-d3703eb50937",
                  "number": 1,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 809.88,
                  "installmentInterest": 0,
                  "installmentTax": 55.66,
                  "dueDates": [
                    "2022-09-22T00:00:00Z"
                  ]
                },
                {
                  "identifier": "db3582c3-3465-436e-a336-e76b7392c632",
                  "number": 2,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 404.94,
                  "installmentInterest": 0,
                  "installmentTax": 27.83,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-15T12:00:00Z"
                  ]
                },
                {
                  "identifier": "f671ba0a-6b6a-4aa2-a9d5-e2267d7a7672",
                  "number": 3,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 269.96,
                  "installmentInterest": 0,
                  "installmentTax": 18.55,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z"
                  ]
                },
                {
                  "identifier": "a8d655d6-7218-4f11-ac19-f717d5df3a78",
                  "number": 4,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 202.47,
                  "installmentInterest": 0,
                  "installmentTax": 13.92,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z"
                  ]
                },
                {
                  "identifier": "2cf29028-0328-421e-8075-2fc20e4be78d",
                  "number": 5,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 161.98,
                  "installmentInterest": 0,
                  "installmentTax": 11.13,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z",
                    "2023-01-15T12:00:00Z"
                  ]
                },
                {
                  "identifier": "b829ce1c-44bf-4ec4-9dcc-fc7ccb664acd",
                  "number": 6,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 134.98,
                  "installmentInterest": 0,
                  "installmentTax": 9.28,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z",
                    "2023-01-15T12:00:00Z",
                    "2023-02-15T12:00:00Z"
                  ]
                },
                {
                  "identifier": "ff8151ef-25b7-4b77-9d84-d81564637117",
                  "number": 7,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 115.7,
                  "installmentInterest": 0,
                  "installmentTax": 7.95,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z",
                    "2023-01-15T12:00:00Z",
                    "2023-02-15T12:00:00Z",
                    "2023-03-15T12:00:00Z"
                  ]
                },
                {
                  "identifier": "abf68d10-613b-4c85-82cb-e07e58df476c",
                  "number": 8,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 101.24,
                  "installmentInterest": 0,
                  "installmentTax": 6.96,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z",
                    "2023-01-15T12:00:00Z",
                    "2023-02-15T12:00:00Z",
                    "2023-03-15T12:00:00Z",
                    "2023-04-15T12:00:00Z"
                  ]
                }
              ]
            }
          ]
        }
      }
    ]
  },
  "success": true,
  "executed": "2022-09-15T15:15:13.9056702Z",
  "errors": null
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Retorno erro com código. " %}
```json
{
    "success": false,
    "executed": "2022-10-06T19:58:31.2050064Z",
    "errors": [
        {
            "code": "ANSWERS-NOT-EVALUATED",
            "message": "One or more answers could not be evaluated.",
            "properties": [
                "INSURED-NAME"
            ]
        }
    ]
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="Retorno não autorizado." %}
```json
{
    "statusCode": 401,
    "message": "Access denied due to missing subscription key. Make sure to include subscription key when making requests to an API."
}
```
{% endswagger-response %}
{% endswagger %}

## Response

### Explicando campos de retorno

> **Field**: success\
> **Type**: `boolean`
>
> Indica se a requisição foi feita com sucesso.

***

> **Field**: executed\
> **Type**: `date`
>
> Data em que a requisição foi feita.

***

> **Field**: errors\
> **Type**: `array`
>
> Array de erros ao fazer a requisição.

***

> **Field**: item.quotationIdentifier\
> **Type**: `guid`
>
> Identificador da cotação.

***

> **Field**: item.status\
> **Type**: `integer`
>
> Status da cotação.

***

> **Field**: item.expiredAt\
> **Type**: `date`
>
> Data de expiração da cotação.

***

> **Field**: item.quotationDocumentUrl\
> **Type**: `text`
>
> Url do documento de cotação.

***

> **Field**: item.proposal.number\
> **Type**: `text`
>
> Número da proposta.

***

> **Field**: item.proposal.date\
> **Type**: `text`
>
> Data da proposta.

***

> **Field**: item.pricing\
> **Type**: `array`
>
> Retorna as propriedades do item, taxas, valores, tipos de pagamentos.\
> Array de items cotados. Ele pode retornar mais de 1 item também.\
> Ex. seriam dois obj's dentro do array se duas bikes fossem cotadas.

***

> **Field**: item.pricing\[].variantIdentifier\
> **Type**: `guid`
>
> Identificador do item cotado.

***

> **Field**: item.pricing\[].underwriting.approved\
> **Type**: `boolean`
>
> Retorna true ou false referente as regras de subscrição do produto.

***

> **Field**: item.pricing\[].underwriting.evaluations\
> **Type**: `array`
>
> Retorna aviso referente as questões do questionário de risco do produto.

***

> **Field**: item.pricing\[].price.commission\
> **Type**: `decimal`
>
> Comissão de corretagem.

***

> **Field**: item.pricing\[].price.grievanceDiscount\
> **Type**: `decimal`
>
> Porcentagem de agravo adicionada ao valor da cotação, onde os valores permitidos vão de 0% até 500%.

***

> **Field**: item.pricing\[].price.itemValue\
> **Type**: `decimal`
>
> Valor do item.

***

> **Field**: item.pricing\[].price.netValue\
> **Type**: `decimal`
>
> Valor de prêmio líquido sem o IOF.

***

> **Field**: item.pricing\[].price.interestValue\
> **Type**: `decimal`
>
> Valor de juros (Por enquanto nenhum produto possui juros, nem para boleto e nem para cartão, mas futuramente terá a princípio para boleto).

***

> **Field**: item.pricing\[].price.taxValue\
> **Type**: `decimal`
>
> Valor de IOF.

***

> **Field**: item.pricing\[].price.totalValue\
> **Type**: `decimal`
>
> Valor de Prêmio Total, composto pelo prêmio líquido somado ao IOF.

***

> **Field**: item.pricing\[].price.policyLimit\
> **Type**: `decimal`
>
> Valor de Limite da apólice (no caso de Bikes, o valor do limite da apólice é igual ao valor informado para a bike).

***

> **Field**: item.pricing\[].price.rates\
> **Type**: `array`
>
> Trata-se de um array, que retornará todas as coberturas contratadas para o produto.

***

> **Field**: item.pricing\[].payment.financialType\
> **Type**: `text`
>
> Trata-se do tipo de financeiro que no caso é "Cobrança".

***

> **Field**: item.pricing\[].payment.paymentOptions\
> **Type**: `array`
>
> Retorna as opções de pagamento disponíveis que são: Boleto e Cartão de crédito.

***

> **Field**: item.pricing\[].price.rates\[].code\
> **Type**: `text`
>
> Exibe o código que identifica a ou as coberturas contratadas. Ex: DAMAGE-COVERAGE, trata-se da cobertura de Danos à Bike.

***

> **Field**: item.pricing\[].price.rates\[].description\
> **Type**: `text`
>
> Trata-se do nome da cobertura em português. Ex: "Danos à Bike".

***

> **Field**: item.pricing\[].price.rates\[].limit\
> **Type**: `decimal`
>
> Trata-se do valor do limite da cobertura.

***

> **Field**: item.pricing\[].price.rates\[].netValue\
> **Type**: `decimal`
>
> Valor do prêmio específico de cada cobertura contratada.

***

> **Field**: item.pricing\[].price.rates\[].deductible.code\
> **Type**: `text`
>
> Trata-se do código identificador de cada franquia.

***

> **Field**: item.pricing\[].price.rates\[].deductible.text\
> **Type**: `text`
>
> Nome da franquia selecionada em português - Ex: "Padrão".

***

> **Field**: item.pricing\[].price.rates\[].deductible.description\
> **Type**: `text`
>
> Descrição da franquia.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].paymentMethod\
> **Type**: `text`
>
> Retorna o nome da forma de pagamento que pode ser: Ticket (Boleto) ou CreditCard (Cartão de Crédito).

***

> **Field**: item.pricing\[].payment.paymentOptions\[].paymentType\
> **Type**: `text`
>
> Forma de pagamento que pode ser escolhida: Boleto ou Cartão de crédito.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\
> **Type**: `array`
>
> Retorna a quantidade de parcelas disponíveis para realizar o pagamento referente ao tipo de pagamento.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].identifier\
> **Type**: `guid`
>
> Código identificador da parcela.\
> Esté é o código necessário enviar ao selecionar o método de pagamento. Exemplo: Se foi selecionado cartão de crédito, enviar o identificador daquele meio de pagamento

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].number\
> **Type**: `integer`
>
> Número da respectiva parcela (2 parcela, número 2).

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].commissionValue\
> **Type**: `decimal`
>
> Valor de comissão de cada parcela.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].netValue\
> **Type**: `decimal`
>
> Valor de prêmio líquido de cada parcela, ou seja, sem o IOF.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].interestValue\
> **Type**: `decimal`
>
> Valor de juros de cada parcela.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].taxValue\
> **Type**: `decimal`
>
> IOF que implica em cada parcela.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].totalValue\
> **Type**: `decimal`
>
> Valor total de cada parcela que é composto do valor líquido + IOF.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].installmentValue\
> **Type**: `decimal`
>
> Valor total da parcela.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].installmentInterest\
> **Type**: `decimal`\\
>
> Valor de juros da parcela.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].installmentTax\
> **Type**: `decimal`
>
> Valor de IOF de cada parcela.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].dueDates\
> **Type**: `array<string>`
>
> Datas de vencimento da parcela caso a forma de pagamento seja boleto.
