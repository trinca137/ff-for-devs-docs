# Criar Proposta

{% swagger method="post" path="{{version}}/quotation/proposal" baseUrl="{{url_ambiente}}/" summary="Criar proposta" expanded="true" fullWidth="true" %}
{% swagger-description %}
Cria uma proposta (atualiza informações adicionais)
{% endswagger-description %}

{% swagger-parameter in="header" name="Ocp-Apim_Subscription-Key" type="key" required="true" %}
chave de acesso da api.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Retorno sucesso" %}
[#response](proposta.md#response "mention")
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Retorno com mensagem do local do erro" %}
{% code overflow="wrap" %}
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
{% endcode %}
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
    "identifier": "4c6781df-b736-4158-8948-f91daa00e65a",
    "registerNumber": "100000",
    "operationCode": "DIRECTORS-OFFICERS-CIVIL-LIABILITY-PARTNER",
    "answers": [
        {
            "code": "PAYMENT-INSTALLMENT-IDENTIFIER",
            "answer": "d9048f5a-1899-404d-8b33-db9a625167f6"
        },
        {
            "code": "SELECTED-VARIANT-IDENTIFIER",
            "answer": "77b5b96a-f55f-4699-b00c-2d11adbf2ca9"
        },
        {
            "code": "DUE-DAY",
            "answer": 1
        },
        {
            "code": "PAYMENT-METHOD",
            "answer": "TICKET"
        }
    ]
}
```

### Detalhamento request de proposta

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
> Pergunta usada para definir o método de pagamento.
>
> \
> Para D\&O so é possivel pagamento por boleto:
>
> * _TICKET_



> **Code**: DUE-DAY\
> **Type**: `integer`\
> ❗ Obrigatório que esteja incluído no array. (apenas quando o PAYMENT-METHOD for TICKET).
>
> Pergunta usada para definir o dia de vencimento quando o PAYMENT-METHOD for TICKET (boleto).\
> \
> Só é possivel envio do dia 1 ao dia 20.



> **Code**: PAYMENT-INSTALLMENT-IDENTIFIER\
> **Type**: `guid`\
> ❗ Obrigatório que esteja incluído no array.
>
> O guid que será enviado nesse campo é retornado no array de installments, no retorno do endpoint de criar cotação.



> **Code**: SELECTED-VARIANT-IDENTIFIER\
> **Type**: `guid`\
> ❗ Obrigatório que esteja incluído no array.
>
> O guid que será enviado nesse campo é retornado no array de PRICING -> VARIANT-IDENTIFIER, no retorno do endpoint de criar cotação.

## Response

```json
{
    "item": {
        "quotationIdentifier": "1698b961-f72d-4e34-80a6-4133291889b9",
        "status": "Draft",
        "proposal": {
            "number": "77475047170001",
            "date": "0001-01-01T00:00:00Z",
            "documentUrl":""
        },
        "pricing": [
            {
                "variantIdentifier": "5d410b7f-3620-4894-8083-2114ca1f9dae",
                "underwriting": {
                    "approved": true,
                    "evaluations": []
                },
                "price": {
                    "commission": 218.95,
                    "grievanceDiscount": 0.0,
                    "netValue": 1094.75,
                    "interestValue": 0.0,
                    "taxValue": 80.79,
                    "totalValue": 1175.54,
                    "policyLimit": 1000000.0,
                    "rates": [
                        {
                            "code": "COMPANY-ACTIVITY",
                            "description": "Atividade",
                            "limit": 1000000.0,
                            "netValue": 52.25,
                            "deductible": {
                                "code": "NO-DEDUCTIBLE",
                                "text": "Sem franquia"
                            }
                        },
                        {
                            "code": "TOTAL-ASSETS",
                            "description": "Ativos",
                            "limit": 1000000.0,
                            "netValue": 23.05,
                            "deductible": {
                                "code": "NO-DEDUCTIBLE",
                                "text": "Sem franquia"
                            }
                        },
                        {
                            "code": "REVENUES",
                            "description": "Faturamento",
                            "limit": 1000000.0,
                            "netValue": 13.06,
                            "deductible": {
                                "code": "NO-DEDUCTIBLE",
                                "text": "Sem franquia"
                            }
                        },
                        {
                            "code": "LIMIT",
                            "description": "Limite",
                            "limit": 1000000.0,
                            "netValue": 1006.39,
                            "deductible": {
                                "code": "NO-DEDUCTIBLE",
                                "text": "Sem franquia"
                            }
                        }
                    ]
                },
                "payment": {
                    "financialType": "Charge",
                    "paymentOptions": [
                        {
                            "paymentMethod": "Ticket",
                            "paymentType": "Ticket",
                            "installments": [
                                {
                                    "identifier": "96cbe205-5e41-43c3-a5c4-e334cb9cde1c",
                                    "number": 1,
                                    "commissionValue": 218.95,
                                    "netValue": 1094.75,
                                    "interestValue": 0.0,
                                    "taxValue": 80.79,
                                    "totalValue": 1175.54,
                                    "installmentValue": 1175.54,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 80.79,
                                    "dueDates": [
                                        "2022-11-20T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "668d3655-c255-4a25-a2a7-e16c44dba15c",
                                    "number": 2,
                                    "commissionValue": 218.95,
                                    "netValue": 1094.75,
                                    "interestValue": 0.0,
                                    "taxValue": 80.79,
                                    "totalValue": 1175.54,
                                    "installmentValue": 587.77,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 40.4,
                                    "dueDates": [
                                        "2022-11-20T00:00:00Z",
                                        "2022-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "c71dac18-5c9e-4f66-a795-1583c4310aa9",
                                    "number": 3,
                                    "commissionValue": 218.95,
                                    "netValue": 1094.75,
                                    "interestValue": 0.0,
                                    "taxValue": 80.79,
                                    "totalValue": 1175.54,
                                    "installmentValue": 391.85,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 26.93,
                                    "dueDates": [
                                        "2022-11-20T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "b1dda90a-18c3-40e7-bc88-68f18d3d6439",
                                    "number": 4,
                                    "commissionValue": 218.95,
                                    "netValue": 1094.75,
                                    "interestValue": 0.0,
                                    "taxValue": 80.79,
                                    "totalValue": 1175.54,
                                    "installmentValue": 293.88,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 20.2,
                                    "dueDates": [
                                        "2022-11-20T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "ea56d214-2f4e-48a9-8ce4-e3c9d1ab8fe5",
                                    "number": 5,
                                    "commissionValue": 218.95,
                                    "netValue": 1094.75,
                                    "interestValue": 0.0,
                                    "taxValue": 80.79,
                                    "totalValue": 1175.54,
                                    "installmentValue": 235.11,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 16.16,
                                    "dueDates": [
                                        "2022-11-20T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "1010e97a-5b3e-44ef-8c3d-0f84156a410f",
                                    "number": 6,
                                    "commissionValue": 218.95,
                                    "netValue": 1094.75,
                                    "interestValue": 0.0,
                                    "taxValue": 80.79,
                                    "totalValue": 1175.54,
                                    "installmentValue": 195.92,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 13.46,
                                    "dueDates": [
                                        "2022-11-20T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z",
                                        "2023-04-01T12:00:00Z"
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
    "executed": "2022-11-23T17:29:37.5394123Z"
}
```

### Explicando campos de retorno&#x20;

Diferente do Response de Cotação, o de proposta possui um campo a mais logo após o "Status", que seria o proposal:

```json
"proposal": {
            "number": "34990940670001",
            "date": "2023-05-23T19:09:27.6820058Z",
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

> **Field**: documentUrl\
> **Type**: `text`
>
> Link do documento da proposta.
