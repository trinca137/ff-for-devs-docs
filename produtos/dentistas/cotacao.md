# Criar cotação

#### Endpoint

```
POST: {{url_ambiente}}/v1/quotation/contracting
```

## Request

```json
{
    "operationCode": "DENTIST-CIVIL-LIABILITY-PARTNER",
    "registerNumber": "100000",
    "identifier": "8324a438-c765-44ee-a7ea-bcfc4b810d22",
    "answers": [
        {
            "code": "MODALITY",
            "answer": "DENTIST-CIVIL-LIABILITY"
        },
        {
            "code": "PERSON-TYPE",
            "answer": "NATURAL"
        },
        {
            "code": "CONGENER",
            "answer": "NEW"
        },
        {
            "code": "PREVIOUS-INSURER",
            "answer": "0"
        },
        {
            "code": "PREVIOUS-INSURER-NAME"
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
            "code": "PROFESSIONAL-REGISTER",
            "answer": "567657"
        },
        {
            "code": "CATEGORIES",
            "answer": [
                "OROFACIAL-HARMONIZATION",
                "FACIAL-FILLERS",
                "GENERAL-PROCEDURES"
            ]
        },
        {
            "code": "RETROACTIVITY",
            "answer": 0
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
                        "answer": "DEFAULT"
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
        "quotationIdentifier": "8324a438-c765-44ee-a7ea-bcfc4b810d22",
        "status": "Draft",
        "pricing": [
            {
                "variantIdentifier": "a5802d31-650d-441a-be7b-35578da2c25d",
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
                    "totalValue": 1052.94
                },
                "payment": {
                    "financialType": "Charge",
                    "paymentOptions": [
                        {
                            "paymentMethod": "All",
                            "paymentType": "CreditCard",
                            "installments": [
                                {
                                    "identifier": "5acb297e-08d3-4561-bb54-9a194c2ab9fb",
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
                                        "2022-11-30T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "50a436dd-1595-4afc-8d00-aebbd5e5b82a",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "0b8e498d-3f5a-4653-b011-26f5e93e28bc",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "54b4a4b4-36e8-4faf-83c6-f00ecdd87b50",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "b8199a1f-300f-4fc5-bea6-bf728cf79f6f",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "f955afcd-60f3-4cbf-b7e9-dd5c3c93e323",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z",
                                        "2023-04-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "317c153c-ccc3-4c25-b996-23798ced8651",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z",
                                        "2023-04-01T12:00:00Z",
                                        "2023-05-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "cb13b262-7f92-4747-9566-b8432ff16adb",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z",
                                        "2023-04-01T12:00:00Z",
                                        "2023-05-01T12:00:00Z",
                                        "2023-06-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "38ba064f-5798-42e8-837f-a31854762462",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z",
                                        "2023-04-01T12:00:00Z",
                                        "2023-05-01T12:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "c9ae667e-1a85-40ae-bca6-2e4ddae0843c",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z",
                                        "2023-04-01T12:00:00Z",
                                        "2023-05-01T12:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z"
                                    ]
                                }
                            ]
                        },
                        {
                            "paymentMethod": "Ticket",
                            "paymentType": "Ticket",
                            "installments": [
                                {
                                    "identifier": "6dd8ad5e-4f35-48da-b1e5-f8d4e6f3d094",
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
                                        "2022-11-30T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "628dff00-0575-4b5c-b1af-141973d1aa96",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "eff81616-34f7-4e07-973b-8344c372a2f6",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "56031475-16e0-411e-a61c-d70eb94b0a37",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "962c2e09-2c33-4d99-b2e0-f464bdb5d6b2",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "618c2480-d451-4b45-bcfa-007c77426703",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z",
                                        "2023-04-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "c0eaeeec-ad63-48f4-bfd7-2c7f22425689",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z",
                                        "2023-04-01T12:00:00Z",
                                        "2023-05-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "c08e9ab2-8bb9-4c82-ada5-f2e3b6dd9898",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z",
                                        "2023-04-01T12:00:00Z",
                                        "2023-05-01T12:00:00Z",
                                        "2023-06-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "a29eef1a-eab0-4ecd-8d42-24cbf2f6a301",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z",
                                        "2023-04-01T12:00:00Z",
                                        "2023-05-01T12:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "d03bd19e-fedd-4dab-9f4e-42cedcbf59c6",
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
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z",
                                        "2023-04-01T12:00:00Z",
                                        "2023-05-01T12:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z"
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
    "executed": "2022-11-23T18:16:57.5122616Z"
}
```
