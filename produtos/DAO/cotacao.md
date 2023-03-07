# Criar cotação

#### Endpoint

```
POST: {{url_ambiente}}/v1/quotation/contracting
```

## Request

```json
{
    "operationCode": "DIRECTORS-OFFICERS-CIVIL-LIABILITY-PARTNER",
    "registerNumber": "100000",
    "answers": [
        {
            "code": "MODALITY",
            "answer": "DIRECTORS-OFFICERS-CIVIL-LIABILITY"
        },
        {
            "code": "PERSON-TYPE",
            "answer": "LEGAL"
        },
        {
            "code": "CONGENER",
            "answer": "RENEWAL"
        },
        {
            "code": "PREVIOUS-INSURER",
            "answer": "0"
        },
        {
            "code": "PREVIOUS-INSURER-NAME",
            "answer": "Seguradora anterior"
        },
        {
            "code": "START-VIGENCY-DATE",
            "answer": "2022-11-23T03:00:00.000Z"
        },
        {
            "code": "IDENTITY",
            "answer": "65.854.012/0001-29"
        },
        {
            "code": "INSURED-NAME",
            "answer": "Nome segurado"
        },
        {
            "code": "INSURED-EMAIL",
            "answer": "email@segurado.com"
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
            "answer": "Número"
        },
        {
            "code": "INSURED-ADDRESS-COMPLEMENT",
            "answer": ""
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
            "code": "PARTNER-TYPE",
            "answer": "SOCIETY"
        },
        {
            "code": "CORPORATE-COMPOSITION",
            "answer": "PRIVATE-CAPITAL"
        },
        {
            "code": "YEARS-COMPANY-STARTED",
            "answer": "3"
        },
        {
            "code": "COMPANY-ACTIVITY",
            "answer": "AGRICULTURE-RELATED-SERVICES"
        },
        {
            "code": "NET-PATRIMONY",
            "answer": "R$ 1.000,00"
        },
        {
            "code": "TOTAL-ASSETS",
            "answer": "3000000.01-5000000.00"
        },
        {
            "code": "REVENUES",
            "answer": "0.00-50000.00"
        },
        {
            "code": "COMPANY-SOLVENT",
            "answer": true
        },
        {
            "code": "INQUIRIES-ADMINISTRATIVE-CRIMINAL-PROCEDURES",
            "answer": false
        },
        {
            "code": "CLAIM-EXPECTATION",
            "answer": false
        },
        {
            "code": "CLAIM-EXPECTATION-THIRD-PARTY"
        },
        {
            "code": "CLAIM-EXPECTATION-AGREEMENT"
        },
        {
            "code": "COVERAGE-PENALTIES",
            "answer": false
        },
        {
            "code": "TERRITORIALITY",
            "answer": "BR"
        },
        {
            "code": "SCOPE",
            "answer": "NATIONAL"
        },
        {
            "code": "LIMITS",
            "answer": [
                [
                    {
                        "code": "LIMIT",
                        "answer": 1000000
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
        "quotationIdentifier": "42e9a23f-6d03-44b2-aea6-c407aa605fbb",
        "status": "Draft",
        "pricing": [
            {
                "variantIdentifier": "1a420302-f94a-4a06-9bca-ad203f65a395",
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
                                    "identifier": "c6b2e46c-12c3-4eaa-b624-c782d65cef02",
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
                                        "2022-11-30T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "8c82f0f5-62df-447f-9bd6-90273238e671",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "d61be87a-cd3a-41f0-8f04-244ac1cb70a4",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "293bcbcf-db2e-4b3e-b719-4fa120204195",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "2fe3a900-c6a6-4a41-a2b1-63823fbf8e47",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "3e52401c-35de-49ae-8123-660a650ec2c9",
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
                                        "2022-11-30T00:00:00Z",
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
    "executed": "2022-11-23T16:57:15.4133765Z"
}
```
