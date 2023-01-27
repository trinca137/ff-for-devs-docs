# Criar Proposta

#### Endpoint

```
POST: {{url_ambiente}}/v1/quotation/proposal
```

## Request

```json
{
    "identifier": "606af046-2a40-4688-af2c-148d65f73aef",
    "operationCode": "MEDICAL-CIVIL-LIABILITY-PARTNER",
    "answers": [
        {
            "code": "INSURED-BIRTH-DATE",
            "answer": "2001-09-15T03:00:00.000Z"
        },
        {
            "code": "DUE-DAY",
            "answer": 1
        },
        {
            "code": "PAYMENT-INSTALLMENT-IDENTIFIER",
            "answer": "5b232a16-50a9-4cf2-8af8-df5c16368b28"
        },
        {
            "code": "PAYMENT-METHOD",
            "answer": "CREDIT-CARD"
        }
    ]
}
```

## Response

Expicamos os campos de retorno neste [link](../../explicando-request-response/request-1.md#response)

```json
{
    "item": {
        "quotationIdentifier": "606af046-2a40-4688-af2c-148d65f73aef",
        "status": "Draft",
        "proposal": {
            "number": "41125730650001",
            "date": "0001-01-01T00:00:00Z"
        },
        "pricing": [
            {
                "variantIdentifier": "96abb261-b6a1-418a-bcca-bc9b1b51cda3",
                "underwriting": {
                    "approved": true,
                    "evaluations": []
                },
                "price": {
                    "commission": 334.29,
                    "grievanceDiscount": 0.0,
                    "netValue": 1671.43,
                    "interestValue": 0.0,
                    "taxValue": 123.35,
                    "totalValue": 1794.78
                },
                "payment": {
                    "financialType": "Charge",
                    "paymentOptions": [
                        {
                            "paymentMethod": "All",
                            "paymentType": "CreditCard",
                            "installments": [
                                {
                                    "identifier": "5b232a16-50a9-4cf2-8af8-df5c16368b28",
                                    "number": 1,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 1794.78,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 123.35,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "efc3ad52-5ed5-4441-88e1-99b40846b2b7",
                                    "number": 2,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 897.39,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 61.68,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "7b34f592-5836-43a3-aaba-cd1995eecdd3",
                                    "number": 3,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 598.26,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 41.12,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "6dafcbac-ff8c-4556-99d3-c6cabf33b32b",
                                    "number": 4,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 448.7,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 30.84,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "7bbf4da8-7bba-45ac-b8a9-da4f1a5df9b5",
                                    "number": 5,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 358.96,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 24.67,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "e5bbab51-272f-446c-9dc1-86f0c5ccc025",
                                    "number": 6,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 299.13,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 20.56,
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
                                    "identifier": "34da341c-6ad6-4f54-a232-e03d957d0d21",
                                    "number": 7,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 256.4,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 17.62,
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
                                    "identifier": "f39c436b-a240-4513-b53d-88318f2b726b",
                                    "number": 8,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 224.35,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 15.42,
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
                                    "identifier": "b5f63422-c096-4148-aa46-93b578218df6",
                                    "number": 9,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 199.42,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 13.71,
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
                                    "identifier": "fad8e350-57fb-4033-8dbd-3b0de5b2a374",
                                    "number": 10,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 179.48,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 12.34,
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
                                },
                                {
                                    "identifier": "cc6a7f8d-b33d-4db1-9c6a-790015285ca5",
                                    "number": 11,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 163.16,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 11.21,
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
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z"
                                    ]
                                }
                            ]
                        },
                        {
                            "paymentMethod": "Ticket",
                            "paymentType": "Ticket",
                            "installments": [
                                {
                                    "identifier": "8f130cbd-7b0c-4155-b980-9e714497bdba",
                                    "number": 1,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 1794.78,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 123.35,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "e8e192f2-f096-4e2c-b09a-2b1699927162",
                                    "number": 2,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 897.39,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 61.68,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "566dded8-5abc-4458-a49f-02a980fcb9c0",
                                    "number": 3,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 598.26,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 41.12,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "1fbf5bf8-63da-4d15-8608-a6b3ddd0c1e3",
                                    "number": 4,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 448.7,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 30.84,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "eea96962-5ab5-4e85-9912-c86070725ac1",
                                    "number": 5,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 358.96,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 24.67,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "b8cf254a-e608-4fd6-9cce-abced40cc88a",
                                    "number": 6,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 299.13,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 20.56,
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
                                    "identifier": "c844e005-006f-4293-a2c9-ffa09b0b19ae",
                                    "number": 7,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 256.4,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 17.62,
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
                                    "identifier": "0349b356-5c80-4b63-ae0a-0c772f38e4cb",
                                    "number": 8,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 224.35,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 15.42,
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
                                    "identifier": "c76867c1-c504-457b-9e30-03b9f7a103c1",
                                    "number": 9,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 199.42,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 13.71,
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
                                    "identifier": "c6ca222d-819d-4c75-bcd1-257729eff756",
                                    "number": 10,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 179.48,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 12.34,
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
                                },
                                {
                                    "identifier": "7c2f0686-0b8b-448c-8d41-5a620526fd4a",
                                    "number": 11,
                                    "commissionValue": 334.29,
                                    "netValue": 1671.43,
                                    "interestValue": 0.0,
                                    "taxValue": 123.35,
                                    "totalValue": 1794.78,
                                    "installmentValue": 163.16,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 11.21,
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
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z"
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
    "executed": "2022-11-23T21:28:24.7239656Z"
}
```