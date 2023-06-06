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
    "operationCode": "CONSTRUCTION-EQUIPMENT-MULTIPLE-PERIL-PARTNER",
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
        "quotationIdentifier": "fd553149-0a95-4c5b-b94d-e9377d099cf3",
        "status": "Draft",
        "proposal": {
            "number": "04958103120001",
            "date": "2023-05-23T00:00:00Z"
        },
        "pricing": [
            {
                "variantIdentifier": "3aabec8a-45ca-433a-9954-e6ae7853d299",
                "underwriting": {
                    "approved": true,
                    "evaluations": []
                },
                "price": {
                    "commission": 1964.84,
                    "grievanceDiscount": 0.0,
                    "itemValue": 1000000.0,
                    "netValue": 9824.21,
                    "interestValue": 0.0,
                    "taxValue": 725.03,
                    "totalValue": 10549.24,
                    "policyLimit": 1060000.0,
                    "rates": [
                        {
                            "code": "DAMAGE-COVERAGE",
                            "description": "Danos à bike",
                            "limit": 1000000.0,
                            "netValue": 6719.57,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento"
                            }
                        },
                        {
                            "code": "THEFT-COVERAGE",
                            "description": "Roubo e/ou furto qualificado",
                            "limit": 1000000.0,
                            "netValue": 2728.69,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "15% dos prejuízos indenizáveis com o mínimo de 2,5% do valor do equipamento"
                            }
                        },
                        {
                            "code": "ELECTRICAL-DAMAGE-COVERAGE",
                            "description": "Danos elétricos",
                            "limit": 70000.0,
                            "netValue": 212.23,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento"
                            }
                        },
                        {
                            "code": "LOSS-RENT-COVERAGE",
                            "description": "Perda de Aluguel",
                            "limit": 30000.0,
                            "netValue": 81.86,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "5 dias"
                            }
                        },
                        {
                            "code": "PAYMENT-THIRD-PARTIES-COVERAGE",
                            "description": "Pagamento de Aluguel a Terceiros",
                            "limit": 30000.0,
                            "netValue": 81.86,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "5 dias"
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
                                    "identifier": "f14a0bfa-4bb3-4650-97df-9a2ccbbd7f4c",
                                    "number": 1,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 10549.24,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 725.03,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "22fd848b-b3dc-481b-9d6a-e9b51a44e525",
                                    "number": 2,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 5274.62,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 362.52,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "22fe57bf-996e-4c8a-8500-7c0b4b53e62b",
                                    "number": 3,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 3516.41,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 241.68,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "79d8da7a-fb6f-4333-8d6c-c625012bd469",
                                    "number": 4,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 2637.31,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 181.26,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "738da76b-b370-4a33-add0-11f6b71cc621",
                                    "number": 5,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 2109.85,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 145.01,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "1c2f4934-2cf3-49d1-91ec-83567a4feb2d",
                                    "number": 6,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1758.21,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 120.84,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "f8c9522d-8c96-4631-a364-3a0e64eba9c5",
                                    "number": 7,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1507.03,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 103.58,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "9d5f6724-7bbe-4bf4-b47c-8745585f0d1e",
                                    "number": 8,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1318.66,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 90.63,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z",
                                        "2024-01-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "7c4857fe-2459-4b64-9343-44a872a5a0e2",
                                    "number": 9,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1172.14,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 80.56,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z",
                                        "2024-01-01T12:00:00Z",
                                        "2024-02-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "f1915552-a7a7-4dd1-9cee-d54c0a061271",
                                    "number": 10,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1054.92,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 72.5,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z",
                                        "2024-01-01T12:00:00Z",
                                        "2024-02-01T12:00:00Z",
                                        "2024-03-01T12:00:00Z"
                                    ]
                                }
                            ]
                        },
                        {
                            "paymentMethod": "Ticket",
                            "paymentType": "Ticket",
                            "installments": [
                                {
                                    "identifier": "80f592dc-162d-4eba-a98f-25751e9da9e9",
                                    "number": 1,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 10549.24,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 725.03,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "668c687b-5e57-4003-aa6d-eeb38ebdc1c3",
                                    "number": 2,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 5274.62,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 362.52,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "166f90eb-d47b-4bfe-9294-6b8b51998d52",
                                    "number": 3,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 3516.41,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 241.68,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "e87bbb03-13ce-4698-acbf-3008755b117f",
                                    "number": 4,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 2637.31,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 181.26,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "88060f40-70c4-4c46-9b56-bf1fdbd9c612",
                                    "number": 5,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 2109.85,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 145.01,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "5d857030-9c6f-42a7-bb11-b97f2abbc3fd",
                                    "number": 6,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1758.21,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 120.84,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z"
                                    ]
                                }
                            ]
                        }
                    ]
                }
            },
            {
                "variantIdentifier": "00000000-0000-0000-0000-000000000000",
                "price": {
                    "commission": 1964.84,
                    "grievanceDiscount": 0.0,
                    "netValue": 9824.21,
                    "interestValue": 0.0,
                    "taxValue": 725.03,
                    "totalValue": 10549.24,
                    "policyLimit": 1060000.0,
                    "rates": [
                        {
                            "code": "DAMAGE-COVERAGE",
                            "description": "Danos à bike",
                            "limit": 1000000.0,
                            "netValue": 6719.57,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento"
                            }
                        },
                        {
                            "code": "THEFT-COVERAGE",
                            "description": "Roubo e/ou furto qualificado",
                            "limit": 1000000.0,
                            "netValue": 2728.69,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "15% dos prejuízos indenizáveis com o mínimo de 2,5% do valor do equipamento"
                            }
                        },
                        {
                            "code": "ELECTRICAL-DAMAGE-COVERAGE",
                            "description": "Danos elétricos",
                            "limit": 70000.0,
                            "netValue": 212.23,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento"
                            }
                        },
                        {
                            "code": "LOSS-RENT-COVERAGE",
                            "description": "Perda de Aluguel",
                            "limit": 30000.0,
                            "netValue": 81.86,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "5 dias"
                            }
                        },
                        {
                            "code": "PAYMENT-THIRD-PARTIES-COVERAGE",
                            "description": "Pagamento de Aluguel a Terceiros",
                            "limit": 30000.0,
                            "netValue": 81.86,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "5 dias"
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
                                    "identifier": "d2da28ca-61f9-4000-918c-f936862b5454",
                                    "number": 1,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 10549.24,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 725.03,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "c6468fe2-c8b4-4aea-8da4-82cb311e7ef0",
                                    "number": 2,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 5274.62,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 362.52,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "ef5cadff-1152-4ca3-b0ca-49253ff22601",
                                    "number": 3,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 3516.41,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 241.68,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "e61e6f1b-7901-4933-b66e-fd0c40db024a",
                                    "number": 4,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 2637.31,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 181.26,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "9562b1dc-4ab7-4008-a69a-a19d81577995",
                                    "number": 5,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 2109.85,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 145.01,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "2f7954dc-e61f-4ac2-8054-e2464a19d493",
                                    "number": 6,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1758.21,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 120.84,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "e0977305-63f6-4b83-9f03-38c8f13764b5",
                                    "number": 7,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1507.03,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 103.58,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "53f77cae-0098-4260-bbe4-a7e837d835ab",
                                    "number": 8,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1318.66,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 90.63,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z",
                                        "2024-01-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "7968a66b-b9ed-4f78-9ee7-0dd3c03e7e23",
                                    "number": 9,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1172.14,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 80.56,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z",
                                        "2024-01-01T12:00:00Z",
                                        "2024-02-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "c5176b03-c0b1-443d-b57f-e58c90027789",
                                    "number": 10,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1054.92,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 72.5,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z",
                                        "2024-01-01T12:00:00Z",
                                        "2024-02-01T12:00:00Z",
                                        "2024-03-01T12:00:00Z"
                                    ]
                                }
                            ]
                        },
                        {
                            "paymentMethod": "Ticket",
                            "paymentType": "Ticket",
                            "installments": [
                                {
                                    "identifier": "cabcc32c-18cd-4f18-b742-502f68e07e02",
                                    "number": 1,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 10549.24,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 725.03,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "9d4c85c8-9891-40b8-9085-f18ed3da0ff4",
                                    "number": 2,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 5274.62,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 362.52,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "d16c6a49-32d8-40fe-ba8d-a32696062fa5",
                                    "number": 3,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 3516.41,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 241.68,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "e2ec4a20-dd46-4224-9100-69d44b8ae24e",
                                    "number": 4,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 2637.31,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 181.26,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "3994139b-0e1d-425b-b91b-629b198159ba",
                                    "number": 5,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 2109.85,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 145.01,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "478d4108-2f6a-4a7d-a362-77af3c592d0c",
                                    "number": 6,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1758.21,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 120.84,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z"
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
    "executed": "2023-05-25T20:52:49.0805476Z"
}
```

### Explicando campos de retorno

Diferente do Response de Cotação, o de proposta possui um campo a mais logo após o "Status", que seria o proposal:

```json
"proposal": {
            "number": "04958103120001",
            "date": "2023-05-23T19:09:27.6820058Z"
        }
```

Onde temos o número da proposta, e a data que foi realizada a chamada da proposta.
