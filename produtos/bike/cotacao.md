# Criar cotação

#### Endpoint

```
POST: {{url_ambiente}}/v1/quotation/contracting
```

## Request

```json
{
    "operationCode": "BIKE-MULTIPLE-PERIL-PARTNER",
    "registerNumber": "100000",
    "answers": [
        {
            "code": "MODALITY",
            "answer": "BIKE-MULTIPLE-PERIL"
        },
        {
            "code": "PERSON-TYPE",
            "answer": "NATURAL"
        },
        {
            "code": "START-VIGENCY-DATE",
            "answer": "2022-11-22T03:00:00.000Z"
        },
        {
            "code": "VIGENCY-DURATION",
            "answer": 1
        },
        {
            "code": "CONGENER",
            "answer": "NEW"
        },
        {
            "code": "INSURED-NAME",
            "answer": "Nome do segurado"
        },
        {
            "code": "INSURED-EMAIL",
            "answer": "teste@email.com"
        },
        {
            "code": "IDENTITY",
            "answer": "10481767703"
        },
        {
            "code": "GENDER",
            "answer": "I"
        },
        {
            "code": "INSURED-CELLPHONE",
            "answer": "(11) 91111-2222"
        },
        {
            "code": "INSURED-ADDRESS-ZIPCODE",
            "answer": "12345-123"
        },
        {
            "code": "INSURED-ADDRESS-STREET",
            "answer": "Nome da rua"
        },
        {
            "code": "INSURED-ADDRESS-NUMBER",
            "answer": "44"
        },
        {
            "code": "INSURED-ADDRESS-COMPLEMENT",
            "answer": "Não é obrigatório"
        },
        {
            "code": "INSURED-ADDRESS-NEIGHBORHOOD",
            "answer": "Bairro"
        },
        {
            "code": "INSURED-ADDRESS-CITY",
            "answer": "São Paulo"
        },
        {
            "code": "INSURED-ADDRESS-STATE",
            "answer": "SP"
        },
        {
            "code": "COMMISSION",
            "answer": 20
        },
        {
            "code": "GRIEVANCE-DISCOUNT",
            "answer": 0
        },
        {
            "code": "ITEMS",
            "answer": [
                [
                    {
                        "code": "SERIAL-NUMBER",
                        "answer": "13"
                    },
                    {
                        "code": "ITEM-TYPE",
                        "answer": "TRADITIONAL"
                    },
                    {
                        "code": "MANUFACTURE-YEAR",
                        "answer": 2022
                    },
                    {
                        "code": "MODEL",
                        "answer": "12"
                    },
                    {
                        "code": "COMPETITIONS",
                        "answer": false
                    },
                    {
                        "code": "ORIGINAL-VALUE",
                        "answer": 3500
                    },
                    {
                        "code": "NEW",
                        "answer": false
                    },
                    {
                        "code": "BRAND",
                        "answer": "ACCELL"
                    },
                    {
                        "code": "BRAND-NAME",
                        "answer": "ACCELL"
                    },
                    {
                        "code": "FRAME-TYPE",
                        "answer": "CARBON"
                    },
                    {
                        "code": "FRAME-TYPE-AGREEMENT",
                        "answer": true
                    },
                    {
                        "code": "CLAIMS",
                        "answer": "0"
                    },
                    {
                        "code": "DEDUCTIBLE",
                        "answer": "DEFAULT"
                    },
                    {
                        "code": "PARTS",
                        "answer": [
                            [
                                {
                                    "code": "PART-TYPE",
                                    "answer": "UNMODIFIED"
                                },
                                {
                                    "code": "PART-BRAND"
                                },
                                {
                                    "code": "PART-MODEL"
                                },
                                {
                                    "code": "PART-VALUE"
                                }
                            ]
                        ]
                    },
                    {
                        "code": "COVERAGES",
                        "answer": [
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "DAMAGE-COVERAGE"
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "THEFT-COVERAGE"
                                }
                            ]
                        ]
                    },
                    {
                        "code": "RENT",
                        "answer": false
                    },
                    {
                        "code": "INVOICE",
                        "answer": true
                    },
                    {
                        "code": "INVOICE-AGREEMENT",
                        "answer": true
                    },
                    {
                        "code": "VALUE-AGREEMENT",
                        "answer": true
                    }
                ]
            ]
        }
    ]
}
```

## Response

Expicamos os campos de retorno neste [link](../../explicando-request-response/request.md#response)

```json
{
    "item": {
        "quotationIdentifier": "c74ac985-4805-411e-903b-c5d6c1219f07",
        "status": "Draft",
        "pricing": [
            {
                "variantIdentifier": "55d64b7a-e698-4631-8e05-058604c381cc",
                "underwriting": {
                    "approved": true,
                    "evaluations": []
                },
                "price": {
                    "commission": 45.2,
                    "grievanceDiscount": 0.0,
                    "itemValue": 3500.0,
                    "netValue": 225.98,
                    "interestValue": 0.0,
                    "taxValue": 16.68,
                    "totalValue": 242.66,
                    "policyLimit": 3500.0,
                    "rates": [
                        {
                            "code": "DAMAGE-COVERAGE",
                            "description": "Danos à bike",
                            "limit": 3500.0,
                            "netValue": 59.47,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "Padrão",
                                "description": "15% dos prejuízos indenizáveis com o mínimo de R$ 500,00"
                            }
                        },
                        {
                            "code": "THEFT-COVERAGE",
                            "description": "Roubo e/ou furto qualificado",
                            "limit": 3500.0,
                            "netValue": 166.51,
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
                                    "identifier": "910aea66-01f7-45d6-bf02-8db14ab3fb0f",
                                    "number": 1,
                                    "commissionValue": 45.2,
                                    "netValue": 225.98,
                                    "interestValue": 0.0,
                                    "taxValue": 16.68,
                                    "totalValue": 242.66,
                                    "installmentValue": 242.66,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 16.68,
                                    "dueDates": [
                                        "2022-11-29T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "483be4f9-9725-42f7-9b8b-a0a91ccdae35",
                                    "number": 2,
                                    "commissionValue": 45.2,
                                    "netValue": 225.98,
                                    "interestValue": 0.0,
                                    "taxValue": 16.68,
                                    "totalValue": 242.66,
                                    "installmentValue": 121.33,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 8.34,
                                    "dueDates": [
                                        "2022-11-29T00:00:00Z",
                                        "2022-12-01T12:00:00Z"
                                    ]
                                }
                            ]
                        },
                        {
                            "paymentMethod": "Ticket",
                            "paymentType": "Ticket",
                            "installments": [
                                {
                                    "identifier": "e9ccdf2e-4683-4b60-9d6a-580a635f25a1",
                                    "number": 1,
                                    "commissionValue": 45.2,
                                    "netValue": 225.98,
                                    "interestValue": 0.0,
                                    "taxValue": 16.68,
                                    "totalValue": 242.66,
                                    "installmentValue": 242.66,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 16.68,
                                    "dueDates": [
                                        "2022-11-29T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "cf53f82d-4b9f-4203-9202-6fad59436c15",
                                    "number": 2,
                                    "commissionValue": 45.2,
                                    "netValue": 225.98,
                                    "interestValue": 0.0,
                                    "taxValue": 16.68,
                                    "totalValue": 242.66,
                                    "installmentValue": 121.33,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 8.34,
                                    "dueDates": [
                                        "2022-11-29T00:00:00Z",
                                        "2022-12-01T12:00:00Z"
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
    "executed": "2022-11-22T13:55:28.6822763Z"
}
```
