# Criar Cotação

#### Endpoint

```
POST: {{url_ambiente}}/v1/quotation/contracting
```

## Request

```json
{
    "operationCode": "INSURANCE-BROKER-CIVIL-LIABILITY-PARTNER",
    "registerNumber": "100000",
    "answers": [
        {
          "code": "MODALITY",
          "answer": "INSURANCE-BROKER-CIVIL-LIABILITY"
        },
        {
          "code": "PERSON-TYPE",
          "answer": "NATURAL"
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
          "answer": "2022-11-22T03:00:00.000Z"
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
            "code": "PROFESSIONAL-REGISTER",
            "answer": "123456"
        },
        {
            "code": "REGISTER-NUMBER-TYPE",
            "answer": "FULL"
        },
        {
            "code": "CATEGORIES",
            "answer": [
                "CAR",
                "AERONAUTICAL",
                "CONSORTIUM"
            ]
        },
        {
            "code": "DIGITAL-CERTIFICATION-COVERAGE"
        },
        {
            "code": "RETROACTIVITY",
            "answer": 3
        },
        {
            "code": "RETROACTIVITY-AGREEMENT"
        },
        {
            "code": "VIGENCY-RETROACTIVITY-AGREEMENT"
        },
        {
            "code": "CLAIMS",
            "answer": "0"
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
            "code": "TERRITORIALITY",
            "answer": "BR"
        },
        {
            "code": "SCOPE",
            "answer": "NATIONAL"
        },
        {
            "code": "LIMIT-DEDUCTIBLE",
            "answer": [
                [
                    {
                        "code": "LIMIT",
                        "answer": 100000
                    },
                    {
                        "code": "DEDUCTIBLE",
                        "answer": "INCREASED"
                    }
                ]
            ]
        },
    ]
}
```

## Response

Expicamos os campos de retorno neste [link](../../explicando-request-response/request.md#response)

```json
{
    "item": {
        "quotationIdentifier": "3a7d4d0f-905b-4abf-859d-8b1cebddb53a",
        "status": "Draft",
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
    "executed": "2022-11-23T13:41:44.798028Z"
}
```
