# Criar Proposta

#### Endpoint
```
POST: {{url_ambiente}}/v1/quotation/proposal
```

Request
--------

```json
{
    "identifier": "4ebed38e-db7a-40df-ae51-87edef9d2d69",
    "operationCode": "BIKE-MULTIPLE-PERIL-PARTNER",
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
            "code": "PAYMENT-METHOD",
            "answer": "CREDIT-CARD"
        },
        {
            "code": "INSURED-BIRTH-DATE",
            "answer": "1990-09-08T03:00:00.000Z"
        },
        {
            "code": "DUE-DAY",
            "answer": 15
        },
        {
            "code": "PAYMENT-INSTALLMENT-IDENTIFIER",
            "answer": "adee1bc9-154f-4fa2-937d-34d2610bed83"
        },
        {
            "code": "ITEMS",
            "answer": [
                [
                    {
                        "code":"ITEM-IDENTIFIER",
                        "answer":"1634aa56-f096-43a2-bd47-11ecd4600c7e"
                    },
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
    ],
    "documents": [
        {
            "itemIdentifier": "1634aa56-f096-43a2-bd47-11ecd4600c7e",
            "files": [
                "data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/4gIoSUNDX1BST0ZJTEUAAQEAAAIYAAAAAAQwAABtbnRyUkdCIFhZWiAAAAAAAAAAAAAAAABhY3NwAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQAA9tYAAQAAAADTLQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAlkZXNjAAAA8AAAAHRyWFlaAAABZAAAABRnWFlaAAABeAAAABRiWFlaAAABjAAAABRyVFJDAAABoAAAAChnVFJDAAABoAAAAChiVFJDAAABoAAAACh3dHB0AAAByAAAABRjcHJ0AAAB3AAAADxtbHVjAAAAAAAAAAEAAAAMZW5VUwAAAFgAAAAcAHMAUgBHAEIAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAFhZWiAAAAAAAABvogAAOPUAAAOQWFlaIAAAAAAAAGKZAAC3hQAAGNpYWVogAAAAAAAAJKAAAA+EAAC2z3BhcmEAAAAAAAQAAAACZmYAAPKnAAANWQAAE9AAAApbAAAAAAAAAABYWVogAAAAAAAA9tYAAQAAAADTLW1sdWMAAAAAAAAAAQAAAAxlblVTAAAAIAAAABwARwBvAG8AZwBsAGUAIABJAG4AYwAuACAAMgAwADEANv/bAEMAAwICAgICAwICAgMDAwMEBgQEBAQECAYGBQYJCAoKCQgJCQoMDwwKCw4LCQkNEQ0ODxAQERAKDBITEhATDxAQEP/bAEMBAwMDBAMECAQECBALCQsQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEP/AABEIAZoCgAMBIgACEQEDEQH/xAAVAAEBAAAAAAAAAAAAAAAAAAAAB//EABQQAQAAAAAAAAAAAAAAAAAAAAD/xAAVAQEBAAAAAAAAAAAAAAAAAAAACP/EABQRAQAAAAAAAAAAAAAAAAAAAAD/2gAMAwEAAhEDEQA/AKwAkRWYAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAD//2Q==",
                "data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/4gIoSUNDX1BST0ZJTEUAAQEAAAIYAAAAAAQwAABtbnRyUkdCIFhZWiAAAAAAAAAAAAAAAABhY3NwAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQAA9tYAAQAAAADTLQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAlkZXNjAAAA8AAAAHRyWFlaAAABZAAAABRnWFlaAAABeAAAABRiWFlaAAABjAAAABRyVFJDAAABoAAAAChnVFJDAAABoAAAAChiVFJDAAABoAAAACh3dHB0AAAByAAAABRjcHJ0AAAB3AAAADxtbHVjAAAAAAAAAAEAAAAMZW5VUwAAAFgAAAAcAHMAUgBHAEIAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAFhZWiAAAAAAAABvogAAOPUAAAOQWFlaIAAAAAAAAGKZAAC3hQAAGNpYWVogAAAAAAAAJKAAAA+EAAC2z3BhcmEAAAAAAAQAAAACZmYAAPKnAAANWQAAE9AAAApbAAAAAAAAAABYWVogAAAAAAAA9tYAAQAAAADTLW1sdWMAAAAAAAAAAQAAAAxlblVTAAAAIAAAABwARwBvAG8AZwBsAGUAIABJAG4AYwAuACAAMgAwADEANv/bAEMAAwICAgICAwICAgMDAwMEBgQEBAQECAYGBQYJCAoKCQgJCQoMDwwKCw4LCQkNEQ0ODxAQERAKDBITEhATDxAQEP/bAEMBAwMDBAMECAQECBALCQsQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEP/AABEIAZoCgAMBIgACEQEDEQH/xAAVAAEBAAAAAAAAAAAAAAAAAAAAB//EABQQAQAAAAAAAAAAAAAAAAAAAAD/xAAVAQEBAAAAAAAAAAAAAAAAAAAACP/EABQRAQAAAAAAAAAAAAAAAAAAAAD/2gAMAwEAAhEDEQA/AKwAkRWYAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAD//2Q=="
            ]
        }
    ]
}
```

Response
--------

```json
{
    "item": {
        "quotationIdentifier": "4ebed38e-db7a-40df-ae51-87edef9d2d69",
        "status": "Draft",
        "proposal": {
            "number": "80473385610001",
            "date": "0001-01-01T00:00:00Z"
        },
        "pricing": [
            {
                "variantIdentifier": "1634aa56-f096-43a2-bd47-11ecd4600c7e",
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
                                    "identifier": "adee1bc9-154f-4fa2-937d-34d2610bed83",
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
                                    "identifier": "cc10c58c-e644-43aa-8522-f7b83ffec506",
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
                                        "2022-12-15T12:00:00Z"
                                    ]
                                }
                            ]
                        },
                        {
                            "paymentMethod": "Ticket",
                            "paymentType": "Ticket",
                            "installments": [
                                {
                                    "identifier": "81ac6741-e675-4815-bde5-5c8e2b0115cf",
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
                                    "identifier": "db715e00-13d7-4902-98d4-26d4fdfe0717",
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
                                        "2022-12-15T12:00:00Z"
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
    "executed": "2022-11-22T19:05:53.5943162Z"
}
```
