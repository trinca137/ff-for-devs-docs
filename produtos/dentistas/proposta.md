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
    "identifier": "8324a438-c765-44ee-a7ea-bcfc4b810d22",
    "registerNumber": "100000",
    "operationCode": "DENTIST-CIVIL-LIABILITY-PARTNER",
    "answers": [
        {
            "code": "DUE-DAY",
            "answer": "1"
        },
        {
            "code": "INSURED-BIRTH-DATE",
            "answer": "1990-09-09T03:00:00.000Z"
        },
        {
            "code": "PAYMENT-INSTALLMENT-IDENTIFIER",
            "answer": "5acb297e-08d3-4561-bb54-9a194c2ab9fb"
        },
        {
            "code": "PAYMENT-METHOD",
            "answer": "CREDIT-CARD"
        },
        {
            "code": "PEP",
            "answer": "RELATION"
        },
        {
            "code": "PEP-NAME",
            "answer": "teste"
        },
        {
            "code": "PEP-PARENTING",
            "answer": "SON/DAUGHTER"
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
> Pergunta usada para definir o dia de vencimento quando o PAYMENT-METHOD for TICKET (boleto).\
> \
> So é possivel envio do dia 1 ao dia 20.



> **Code**: PAYMENT-INSTALLMENT-IDENTIFIER\
> **Type**: `guid`\
> ❗ Obrigatório que esteja incluído no array.
>
> O guid que será enviado nesse campo é retornado no array de installments, no retorno do endpoint de criar cotação.

> **Code**: PEP\
> **Type**: `string`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir se é uma **pessoa exposta publicamente.**
>
> \
> Respostas para PEP:\
> \
> **NO:** Não é publicamente exposta.
>
> **YES:** É publicamente exposta.
>
> **RELATION:** Relacionamento próximo.

<details>

<summary>Caso PEP for RELATION, é necessário o envio de mais duas perguntas, sendo elas:</summary>

```markdown
Code: PEP-NAME
Type: string
❗ Obrigatório que esteja incluído no array.
Pergunta usada para definir o nome da pessoa com relação.
```

```markdown
Code: PEP-PARENTING
Type: string
❗ Obrigatório que esteja incluído no array.
Pergunta usada para definir a relação da pessoa.

Opções de Envio:

- FATHER/MOTHER = Pai/Mãe
- SON/DAUGHTER = Filho/Filha
- SPOUSE = Cônjugue
- PARTNER = Companheiro/Companheira
- STEPSON = Enteado/Enteada
- OTHER = Outros
```

</details>

## Response

```json
{
    "item": {
        "quotationIdentifier": "ff5324b7-1d2d-4c31-8a70-8afe1d7d1b4e",
        "status": "Draft",
        "proposal": {
            "number": "17848685910001",
            "date": "0001-01-01T00:00:00Z",
            "documentUrl":""
        },
        "pricing": [
            {
                "variantIdentifier": "36856c9a-b19b-4a39-b572-f5384dc3393f",
                "underwriting": {
                    "approved": true,
                    "evaluations": []
                },
                "price": {
                    "commission": 196.11,
                    "grievanceDiscount": 0.0,
                    "netValue": 980.57,
                    "interestValue": 0.0,
                    "taxValue": 72.37,
                    "totalValue": 1052.94,
                    "limitDeductible": {
                        "deductible": {
                            "answer": [
                                "DEFAULT"
                            ],
                            "questionText": "Franquia",
                            "answerText": [
                                "Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00"
                            ]
                        },
                        "limits": {
                            "answer": [
                                100000.0
                            ],
                            "questionText": "Limite de cobertura",
                            "answerText": [
                                "R$ 100.000"
                            ]
                        }
                    }
                },
                "payment": {
                    "financialType": "Charge",
                    "paymentOptions": [
                        {
                            "paymentMethod": "All",
                            "paymentType": "CreditCard",
                            "installments": [
                                {
                                    "identifier": "2279bda1-39a1-4c57-8054-7b24dfd2300a",
                                    "number": 1,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 1052.94,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 72.37,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "072d7612-8323-4954-9c71-6ac5a96ec95a",
                                    "number": 2,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 526.47,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 36.18,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z",
                                        "2023-06-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "6bfda74c-4dc3-4137-9eea-97c4f2032729",
                                    "number": 3,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 350.98,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 24.12,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "646c8e9f-8f64-4924-8c1c-a063461b08ae",
                                    "number": 4,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 263.24,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 18.09,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "f3326c4b-2b37-41e4-a212-ccf87a27528c",
                                    "number": 5,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 210.59,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 14.47,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "5f4afdbb-7c09-4c77-9b95-bf02e3c190d3",
                                    "number": 6,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 175.49,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 12.06,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "55f6375f-28f0-4a49-9827-7984c7252674",
                                    "number": 7,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 150.42,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 10.34,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "ef95f1aa-22a6-4962-b714-8ce281cad3b0",
                                    "number": 8,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 131.62,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 9.05,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "8e2b8126-e12e-4416-85f2-5497cb9c24b8",
                                    "number": 9,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 116.99,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 8.04,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z",
                                        "2023-06-01T12:00:00Z",
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
                                    "identifier": "5465ff18-64bb-4271-813e-54cffaa14778",
                                    "number": 10,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 105.29,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 7.24,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z",
                                        "2024-01-01T12:00:00Z",
                                        "2024-02-01T12:00:00Z"
                                    ]
                                }
                            ]
                        },
                        {
                            "paymentMethod": "Ticket",
                            "paymentType": "Ticket",
                            "installments": [
                                {
                                    "identifier": "6ed41ba6-ceec-423d-acc4-da9dcbdba92f",
                                    "number": 1,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 1052.94,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 72.37,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "77242ec3-afb8-41dd-a5ef-655e40c7cdc0",
                                    "number": 2,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 526.47,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 36.18,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z",
                                        "2023-06-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "9e6bdbcd-7b20-4632-8f8d-9ac9abed0381",
                                    "number": 3,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 350.98,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 24.12,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "0d992d83-536e-4712-91d6-cd830619b389",
                                    "number": 4,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 263.24,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 18.09,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "97eb995a-9284-4d60-ae0c-d790823f7471",
                                    "number": 5,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 210.59,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 14.47,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "d00a5b1a-86ee-4716-bac8-0ae0ae55ad69",
                                    "number": 6,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 175.49,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 12.06,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "5f112303-9609-4d7e-a140-fbdab6fb7225",
                                    "number": 7,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 150.42,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 10.34,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "b520d5be-7677-4aeb-8185-fced440fc833",
                                    "number": 8,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 131.62,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 9.05,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "7372ea73-b294-48da-82ed-ea326a043100",
                                    "number": 9,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 116.99,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 8.04,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z",
                                        "2023-06-01T12:00:00Z",
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
                                    "identifier": "920f3bd0-e526-4478-bd5b-0c32f0201bbf",
                                    "number": 10,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 105.29,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 7.24,
                                    "dueDates": [
                                        "2023-05-20T00:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z",
                                        "2024-01-01T12:00:00Z",
                                        "2024-02-01T12:00:00Z"
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
    "executed": "2023-05-24T20:49:58.3856737Z"
}
```

### Explicando campos de retorno

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
