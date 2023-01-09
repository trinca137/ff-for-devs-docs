# Criar Proposta

#### Endpoint

```
POST: {{url_ambiente}}/v1/quotation/proposal
```

## Request

```json
{
    "identifier": "1698b961-f72d-4e34-80a6-4133291889b9",
    "operationCode": "DIRECTORS-OFFICERS-CIVIL-LIABILITY-PARTNER",
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
            "answer": "000.111.222-33"
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
                    },
                    {
                        "code":"VARIANT-IDENTIFIER",
                        "answer":"5d410b7f-3620-4894-8083-2114ca1f9dae"
                    }
                ]
            ]
        },
        {
            "code": "PAYMENT-INSTALLMENT-IDENTIFIER",
            "answer": "96cbe205-5e41-43c3-a5c4-e334cb9cde1c"
        },
        {
            "code": "DUE-DAY",
            "answer": 1
        },
        {
            "code": "PAYMENT-METHOD",
            "answer":"TICKET"
        }
    ]
}
```

## Response

```json
{
    "item": {
        "quotationIdentifier": "1698b961-f72d-4e34-80a6-4133291889b9",
        "status": "Draft",
        "proposal": {
            "number": "77475047170001",
            "date": "0001-01-01T00:00:00Z"
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
                                        "2022-11-30T00:00:00Z"
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
                                        "2022-11-30T00:00:00Z",
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
                                        "2022-11-30T00:00:00Z",
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
                                        "2022-11-30T00:00:00Z",
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
                                        "2022-11-30T00:00:00Z",
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
    "executed": "2022-11-23T17:29:37.5394123Z"
}
```
