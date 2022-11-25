# Criar Proposta

#### Endpoint
```
POST: {{url_ambiente}}/v1/quotation/proposal
```

Request
-------


💡 **Exemplo de json de request**

```json
{
    "identifier":"bb514827-6c53-447f-b8c9-5b0aa79b8905",
    "operationCode": "DIRECTORS-OFFICERS-CIVIL-LIABILITY-PARTNER",
    "answers": [
 {
            "code": "MODALITY",
            "answer": "DIRECTORS-OFFICERS-CIVIL-LIABILITY"
        },
        {
            "code": "PRODUCT"
        },
        {
            "code": "CURRENCY"
        },
        {
            "code": "PERSON-TYPE",
            "answer": "LEGAL"
        },
        {
            "code": "START-VIGENCY-DATE",
            "answer": "2022-11-20T03:00:00.000Z"
        },
        {
            "code": "VIGENCY-DURATION"
        },
        {
            "code": "VIGENCY-RETROACTIVITY-AGREEMENT"
        },
        {
            "code": "CONGENER",
            "answer": "NEW"
        },
        {
            "code": "RETROACTIVITY-AGREEMENT"
        },
        {
            "code": "INSURED-NAME",
            "answer": "segurado"
        },
        {
            "code": "INSURED-EMAIL",
            "answer": "seg@gmail.com"
        },
        {
            "code": "IDENTITY",
            "answer": "41.896.570/0001-99"
        },
        {
            "code": "GENDER"
        },
        {
            "code": "INSURED-CELLPHONE",
            "answer": "(12) 99643.2351"
        },
        {
            "code": "INSURED-ADDRESS-ZIPCODE",
            "answer": "06717-265"
        },
        {
            "code": "INSURED-ADDRESS-STREET",
            "answer": "Rua Voturama"
        },
        {
            "code": "INSURED-ADDRESS-NUMBER",
            "answer": "998"
        },
        {
            "code": "INSURED-ADDRESS-COMPLEMENT",
            "answer": ""
        },
        {
            "code": "INSURED-ADDRESS-NEIGHBORHOOD",
            "answer": "Recanto dos Victor's"
        },
        {
            "code": "INSURED-ADDRESS-CITY",
            "answer": "Cotia"
        },
        {
            "code": "INSURED-ADDRESS-STATE",
            "answer": "SP"
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
            "code": "COMPANY-SOLVENT",
            "answer": true
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
            "code": "INQUIRIES-ADMINISTRATIVE-CRIMINAL-PROCEDURES",
            "answer": false
        },
        {
            "code": "COVERAGE-PENALTIES",
            "answer": false
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
            "code": "COMPANY-ACTIVITY",
            "answer": "AGRICULTURE-RELATED-SERVICES"
        },
        {
            "code": "REVENUES",
            "answer": "200000.01-250000.00"
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
                        "answer":"c4c98f45-ad66-45d9-b558-4f63ef0a6006"
                    }
                ]
            ]
        },
        {
            "code": "TERRITORIALITY"
        },
        {
            "code": "SCOPE"
        },
        {
            "code": "PROFESSION"
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
            "code": "PAYMENT-INSTALLMENT-IDENTIFIER",
            "answer": "98d56358-0a24-404d-b384-1536a7236384"
        },
        {
            "code": "PAYMENT-METHOD",
            "answer":"TICKET"
        }
    ]
}
```



Response
--------



```json
{
    "item": {
        "quotationIdentifier": "bb514827-6c53-447f-b8c9-5b0aa79b8905",
        "status": "Draft",
        "proposal": {
            "number": "22373311000001",
            "date": "0001-01-01T00:00:00Z"
        },
        "pricing": [
            {
                "variantIdentifier": "c4c98f45-ad66-45d9-b558-4f63ef0a6006",
                "underwriting": {
                    "approved": true,
                    "evaluations": []
                },
                "price": {
                    "commission": 234.2,
                    "grievanceDiscount": 0.0,
                    "netValue": 1170.99,
                    "interestValue": 0.0,
                    "taxValue": 86.42,
                    "totalValue": 1257.41,
                    "policyLimit": 1000000.0,
                    "rates": [
                        {
                            "code": "TOTAL-ASSETS",
                            "description": "Ativos",
                            "limit": 1000000.0,
                            "netValue": 24.26,
                            "deductible": {
                                "code": "NO-DEDUCTIBLE",
                                "text": "Sem franquia"
                            }
                        },
                        {
                            "code": "COMPANY-ACTIVITY",
                            "description": "Atividade",
                            "limit": 1000000.0,
                            "netValue": 55.0,
                            "deductible": {
                                "code": "NO-DEDUCTIBLE",
                                "text": "Sem franquia"
                            }
                        },
                        {
                            "code": "REVENUES",
                            "description": "Faturamento",
                            "limit": 1000000.0,
                            "netValue": 32.37,
                            "deductible": {
                                "code": "NO-DEDUCTIBLE",
                                "text": "Sem franquia"
                            }
                        },
                        {
                            "code": "LIMIT",
                            "description": "Limite",
                            "limit": 1000000.0,
                            "netValue": 1059.36,
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
                                    "identifier": "98d56358-0a24-404d-b384-1536a7236384",
                                    "number": 1,
                                    "commissionValue": 234.2,
                                    "netValue": 1170.99,
                                    "interestValue": 0.0,
                                    "taxValue": 86.42,
                                    "totalValue": 1257.41,
                                    "installmentValue": 1257.41,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 86.42,
                                    "dueDates": [
                                        "2022-11-03T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "8b88887e-b4a4-49aa-9477-a424676fc586",
                                    "number": 2,
                                    "commissionValue": 234.2,
                                    "netValue": 1170.99,
                                    "interestValue": 0.0,
                                    "taxValue": 86.42,
                                    "totalValue": 1257.41,
                                    "installmentValue": 628.7,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 43.21,
                                    "dueDates": [
                                        "2022-11-03T00:00:00Z",
                                        "2022-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "913fdfc1-af08-495d-ae07-ee3e1f4e3b04",
                                    "number": 3,
                                    "commissionValue": 234.2,
                                    "netValue": 1170.99,
                                    "interestValue": 0.0,
                                    "taxValue": 86.42,
                                    "totalValue": 1257.41,
                                    "installmentValue": 419.14,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 28.81,
                                    "dueDates": [
                                        "2022-11-03T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "e0a7b82b-53c9-441e-a511-634eefa5adaf",
                                    "number": 4,
                                    "commissionValue": 234.2,
                                    "netValue": 1170.99,
                                    "interestValue": 0.0,
                                    "taxValue": 86.42,
                                    "totalValue": 1257.41,
                                    "installmentValue": 314.35,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 21.6,
                                    "dueDates": [
                                        "2022-11-03T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "310c67ba-e7fc-488d-92a6-81915915692c",
                                    "number": 5,
                                    "commissionValue": 234.2,
                                    "netValue": 1170.99,
                                    "interestValue": 0.0,
                                    "taxValue": 86.42,
                                    "totalValue": 1257.41,
                                    "installmentValue": 251.48,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 17.28,
                                    "dueDates": [
                                        "2022-11-03T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "4e22816b-ea19-446d-8209-782732612545",
                                    "number": 6,
                                    "commissionValue": 234.2,
                                    "netValue": 1170.99,
                                    "interestValue": 0.0,
                                    "taxValue": 86.42,
                                    "totalValue": 1257.41,
                                    "installmentValue": 209.57,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 14.4,
                                    "dueDates": [
                                        "2022-11-03T00:00:00Z",
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
    "executed": "2022-10-27T14:48:48.8796252Z"
}
```
