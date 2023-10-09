# Criar Proposta

{% swagger method="post" path="{{version}}/quotation/proposal" baseUrl="{{url_ambiente}}/" summary="Criar proposta" expanded="true" fullWidth="true" %}
{% swagger-description %}
Cria uma proposta (atualiza informações adicionais).
{% endswagger-description %}

{% swagger-parameter in="header" name="Ocp-Apim_Subscription-Key" type="key" required="true" %}
chave de acesso da api.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Retorno sucesso " %}
[#response](proposta.md#response "mention")
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Retorno com mensagem do local do erro" %}
```json
{
    "success": false,
    "executed": "2023-05-22T20:25:43.6362739Z",
    "errors": [
        {
            "code": "INVALID-FORM-FIELD",
            "message": "'Item Identifier' must not be empty.",
            "properties": {
                "validationType": "NotEmptyValidator",
                "field": "Documents[0].ItemIdentifier"
            }
        }
    ]
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="Caso não envie uma "chave" ou envie uma inválida" %}
{% code overflow="wrap" %}
```json
{
    "statusCode": 401,
    "message": "Access denied due to missing subscription key. Make sure to include subscription key when making requests to an API."
}
```
{% endcode %}
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Erro de aplicação/servidor" %}

{% endswagger-response %}
{% endswagger %}

## Request

```json
{
   "identifier":"2aea86d1-a9e5-4220-ab29-68c3fba8483f",
   "registerNumber": "100000",
   "operationCode":"BIKE-MULTIPLE-PERIL-PARTNER",
   "answers":[
      {
         "code":"PAYMENT-METHOD",
         "answer":"CREDIT-CARD"
      },
      {
         "code":"INSURED-BIRTH-DATE",
         "answer":"1990-09-08T03:00:00.000Z"
      },
      {
         "code":"DUE-DAY",
         "answer":15
      },
      {
         "code":"PAYMENT-INSTALLMENT-IDENTIFIER",
         "answer":"ee88a83c-1764-4e28-8272-e27d49d32dc8"
      }
   ]
}
```

### Detalhamento request de proposta

> **Code**: INSURED-BIRTH-DATE\
> **Type**: `date`\
> ❗ Obrigatório que esteja incluído no array (apenas se o segurado for Pessoa Fisica).
>
> Pergunta usada para definir a data de nascimento do segurado.



> **Field:** RegisterNumber
>
> **Tipo:** `text`&#x20;
>
> ❗ Campo Obrigatório.
>
> Campo usado para definir qual o SusepNumber da corretora que está sendo cotada. Neste caso, o susep da corretora é "100000".



> **Code**: PAYMENT-METHOD\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o método de pagamento.\
> Os possíveis valores para esta pergunta são:
>
> Se o INVOICE FOR TRUE
>
> * _CREDIT-CARD_
> * _TICKET_
>
> _Se o INVOICE FOR FALSE_
>
> * _CREDIT-CARD_
>
> &#x20;

> **Code**: DUE-DAY\
> **Type**: `integer`\
> ❗ Obrigatório que esteja incluído no array. (apenas quando o PAYMENT-METHOD for TICKET).
>
> Pergunta usada para definir o dia de vencimento quando o PAYMENT-METHOD for TICKET (boleto).



> **Code**: PAYMENT-INSTALLMENT-IDENTIFIER\
> **Type**: `guid`\
> ❗ Obrigatório que esteja incluído no array.
>
> O guid que será enviado nesse campo é retornado no array de installments, no retorno do endpoint de criar cotação.

## Response

{% code overflow="wrap" %}
```json
{
    "item": {
        "quotationIdentifier": "210117cf-2a0b-4f2a-8a7f-04c301e9cf49",
        "status": "Draft",
        "proposal": {
            "number": "34990940670001",
            "date": "2023-05-23T00:00:00Z",
            "acceptanceUrl": "",
            "documentUrl": ""
        },
        "pricing": [
            {
                "variantIdentifier": "423fcec9-2fb9-4c22-a14d-4ff3427974f6",
                "underwriting": {
                    "approved": true,
                    "evaluations": []
                },
                "price": {
                    "commission": 37.72,
                    "grievanceDiscount": 0.0,
                    "itemValue": 3000.0,
                    "netValue": 188.6,
                    "interestValue": 0.0,
                    "taxValue": 13.92,
                    "totalValue": 202.52,
                    "policyLimit": 3000.0,
                    "rates": [
                        {
                            "code": "DAMAGE-COVERAGE",
                            "description": "Danos à bike",
                            "limit": 3000.0,
                            "netValue": 49.63,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "Padrão",
                                "description": "15% dos prejuízos indenizáveis com o mínimo de R$ 500,00"
                            }
                        },
                        {
                            "code": "THEFT-COVERAGE",
                            "description": "Roubo e/ou furto qualificado",
                            "limit": 3000.0,
                            "netValue": 138.97,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "Padrão",
                                "description": "10% dos prejuízos indenizáveis com o mínimo de R$ 500,00"
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
                                    "identifier": "6360803f-2969-410a-be77-7a835a339c4f",
                                    "number": 1,
                                    "commissionValue": 37.72,
                                    "netValue": 188.6,
                                    "interestValue": 0.0,
                                    "taxValue": 13.92,
                                    "totalValue": 202.52,
                                    "installmentValue": 202.52,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 13.92,
                                    "dueDates": [
                                        "2023-05-30T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "1ba6df3d-68e4-45d2-8c97-504017fb2a14",
                                    "number": 2,
                                    "commissionValue": 37.72,
                                    "netValue": 188.6,
                                    "interestValue": 0.0,
                                    "taxValue": 13.92,
                                    "totalValue": 202.52,
                                    "installmentValue": 101.26,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 6.96,
                                    "dueDates": [
                                        "2023-05-30T00:00:00Z",
                                        "2023-06-15T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "5b3ed249-abb6-4060-b17a-08c2a7257b2b",
                                    "number": 3,
                                    "commissionValue": 37.72,
                                    "netValue": 188.6,
                                    "interestValue": 0.0,
                                    "taxValue": 13.92,
                                    "totalValue": 202.52,
                                    "installmentValue": 67.51,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 4.64,
                                    "dueDates": [
                                        "2023-05-30T00:00:00Z",
                                        "2023-06-15T12:00:00Z",
                                        "2023-07-15T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "ec4d3238-b4c4-4192-bc9e-4e8d3193aa09",
                                    "number": 4,
                                    "commissionValue": 37.72,
                                    "netValue": 188.6,
                                    "interestValue": 0.0,
                                    "taxValue": 13.92,
                                    "totalValue": 202.52,
                                    "installmentValue": 50.63,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 3.48,
                                    "dueDates": [
                                        "2023-05-30T00:00:00Z",
                                        "2023-06-15T12:00:00Z",
                                        "2023-07-15T12:00:00Z",
                                        "2023-08-15T12:00:00Z"
                                    ]
                                }
                            ]
                        },
                        {
                            "paymentMethod": "Ticket",
                            "paymentType": "Ticket",
                            "installments": [
                                {
                                    "identifier": "251bb938-01c6-405a-b1af-1adb2dfec7e5",
                                    "number": 1,
                                    "commissionValue": 37.72,
                                    "netValue": 188.6,
                                    "interestValue": 0.0,
                                    "taxValue": 13.92,
                                    "totalValue": 202.52,
                                    "installmentValue": 202.52,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 13.92,
                                    "dueDates": [
                                        "2023-05-30T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "65f488a0-d5a6-4cb2-b4e2-5599010236eb",
                                    "number": 2,
                                    "commissionValue": 37.72,
                                    "netValue": 188.6,
                                    "interestValue": 0.0,
                                    "taxValue": 13.92,
                                    "totalValue": 202.52,
                                    "installmentValue": 101.26,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 6.96,
                                    "dueDates": [
                                        "2023-05-30T00:00:00Z",
                                        "2023-06-15T12:00:00Z"
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
    "executed": "2023-05-23T19:07:19.6820058Z"
}
```
{% endcode %}

### Explicando campos de retorno

Diferente do Response de Cotação, o de proposta possui um campo a mais logo após o "Status", que seria o proposal:

```json
"proposal": {
            "number": "34990940670001",
            "date": "2023-05-23T19:09:27.6820058Z",
            "acceptanceUrl": "",
            "documentUrl": ""
        }
```



> **Field**: number\
> **Type**: `text`
>
> Número da proposta.

***

> **Field**: date\
> **Type**: `date`
>
> Data que a proposta foi criada.

***

> **Field**: acceptanceUrl\
> **Type**: `text`
>
> Link para enviar fotos e realizar checkout.

***

> **Field**: documentUrl\
> **Type**: `text`
>
> Link do documento da proposta.

