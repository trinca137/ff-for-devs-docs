# Criar Proposta

{% swagger method="post" path="{{version}}/quotation/proposal" baseUrl="{{url_ambiente}}/" summary="Criar proposta" expanded="true" fullWidth="true" %}
{% swagger-description %}
Cria uma proposta (atualiza informações adicionais)
{% endswagger-description %}

{% swagger-parameter in="header" name="Ocp-Apim_Subscription-Key" type="key" required="true" %}
chave de acesso da api.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Retorno sucesso " %}


[#response](proposta.md#response "mention")


{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Retorno com mensagem do local do erro" %}
```json
Neste caso não foi enviado o PAYMENT-INSTALLMENT-IDENTIFIER resultando nos outros
erros como aparece abaixo.
{
    "success": false,
    "executed": "2023-05-25T15:04:47.1182243Z",
    "errors": [
        {
            "code": "ANSWERS-NOT-EVALUATED",
            "message": "One or more answers could not be evaluated.",
            "properties": [
                "PAYMENT-INSTALLMENT-IDENTIFIER",
                "NET-VALUE",
                "INTEREST-VALUE",
                "TAX-VALUE",
                "TOTAL-VALUE",
                "INSTALLMENT-NUMBER"
            ]
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
    "identifier": "3a7d4d0f-905b-4abf-859d-8b1cebddb53a",
    "registerNumber": "100000",
    "operationCode": "INSURANCE-BROKER-CIVIL-LIABILITY-PARTNER",
    "answers": [
        {
            "code": "DUE-DAY",
            "answer": "1"
        },
        {
            "code": "PAYMENT-METHOD",
            "answer": "CREDIT-CARD"
        },
        {
            "code": "INSURED-BIRTH-DATE",
            "answer": "1990-09-08T03:00:00.000Z"
        },
        {
            "code": "PAYMENT-INSTALLMENT-IDENTIFIER",
            "answer": "fab2abd1-88f3-40fe-b37f-0db0ed5ba9b5"
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
> * _CREDIT-CARD_
> * _TICKET_



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

```json
{
    "item": {
        "quotationIdentifier": "3a7d4d0f-905b-4abf-859d-8b1cebddb53a",
        "status": "Draft",
        "proposal": {
            "number": "52848305630001",
            "date": "0001-01-01T00:00:00Z"
        },
        "pricing": [
            {
                "variantIdentifier": "01d46264-70d5-4f44-aba5-805fedba0d7a",
                "underwriting": {
                    "approved": true,
                    "evaluations": []
                },
                "price": {
                    "commission": 82.09,
                    "grievanceDiscount": 0.0,
                    "netValue": 410.47,
                    "interestValue": 0.0,
                    "taxValue": 30.29,
                    "totalValue": 440.76
                },
                "payment": {
                    "financialType": "Charge",
                    "paymentOptions": [
                        {
                            "paymentMethod": "All",
                            "paymentType": "CreditCard",
                            "installments": [
                                {
                                    "identifier": "fab2abd1-88f3-40fe-b37f-0db0ed5ba9b5",
                                    "number": 1,
                                    "commissionValue": 82.09,
                                    "netValue": 410.47,
                                    "interestValue": 0.0,
                                    "taxValue": 30.29,
                                    "totalValue": 440.76,
                                    "installmentValue": 440.76,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 30.29,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "e33971fa-fc12-41ab-afbb-bc7e769c888f",
                                    "number": 2,
                                    "commissionValue": 82.09,
                                    "netValue": 410.47,
                                    "interestValue": 0.0,
                                    "taxValue": 30.29,
                                    "totalValue": 440.76,
                                    "installmentValue": 220.38,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 15.14,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "64dce913-cede-41d4-ac09-72c6b2baa969",
                                    "number": 3,
                                    "commissionValue": 82.09,
                                    "netValue": 410.47,
                                    "interestValue": 0.0,
                                    "taxValue": 30.29,
                                    "totalValue": 440.76,
                                    "installmentValue": 146.92,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 10.1,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "b16095f5-ace5-48bf-a75a-4d1a1823841b",
                                    "number": 4,
                                    "commissionValue": 82.09,
                                    "netValue": 410.47,
                                    "interestValue": 0.0,
                                    "taxValue": 30.29,
                                    "totalValue": 440.76,
                                    "installmentValue": 110.19,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 7.57,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z"
                                    ]
                                }
                            ]
                        },
                        {
                            "paymentMethod": "Ticket",
                            "paymentType": "Ticket",
                            "installments": [
                                {
                                    "identifier": "547f2446-4248-4b9b-8431-1485e04bdee4",
                                    "number": 1,
                                    "commissionValue": 82.09,
                                    "netValue": 410.47,
                                    "interestValue": 0.0,
                                    "taxValue": 30.29,
                                    "totalValue": 440.76,
                                    "installmentValue": 440.76,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 30.29,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "3c901abc-8519-4eab-84ea-3d0d987e855d",
                                    "number": 2,
                                    "commissionValue": 82.09,
                                    "netValue": 410.47,
                                    "interestValue": 0.0,
                                    "taxValue": 30.29,
                                    "totalValue": 440.76,
                                    "installmentValue": 220.38,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 15.14,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "56b20baa-a04b-4b36-8fe8-bf704cc85279",
                                    "number": 3,
                                    "commissionValue": 82.09,
                                    "netValue": 410.47,
                                    "interestValue": 0.0,
                                    "taxValue": 30.29,
                                    "totalValue": 440.76,
                                    "installmentValue": 146.92,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 10.1,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "15df082d-643c-4ba7-8171-fe1eddd7e9d4",
                                    "number": 4,
                                    "commissionValue": 82.09,
                                    "netValue": 410.47,
                                    "interestValue": 0.0,
                                    "taxValue": 30.29,
                                    "totalValue": 440.76,
                                    "installmentValue": 110.19,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 7.57,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z"
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
    "executed": "2022-11-23T13:45:40.6711499Z"
}
```

### Explicando campos de retorno

Diferente do Response de Cotação, o de proposta possui um campo a mais logo após o "Status", que seria o proposal:

```json
"proposal": {
            "number": "52848305630001",
            "date": "2023-05-23T19:09:27.6820058Z"
        }
```

Onde temos o número da proposta, e a data que foi realizada a chamada da proposta.
