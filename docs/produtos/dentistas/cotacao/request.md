# Create Quotation

#### Endpoint
```
POST: {{url_ambiente}}/v1/quotation
```

Request
-------


💡 **Exemplo de json de request**

```json
{
  "operationCode": "DENTIST-CIVIL-LIABILITY-PARTNER",
  "answers": [
    {
      "code": "MODALITY",
      "answer": "DENTIST-CIVIL-LIABILITY"
    },
    {
      "code": "PRODUCT"
    },
    {
      "code": "CURRENCY"
    },
    {
      "code": "PERSON-TYPE",
      "answer": "NATURAL"
    },
    {
      "code": "START-VIGENCY-DATE",
      "answer": "2022-10-02T03:00:00.000Z"
    },
    {
      "code": "VIGENCY-DURATION"
    },
    {
      "code": "CONGENER",
      "answer": "NEW"
    },
    {
      "code": "INSURED-NAME",
      "answer": " segurado"
    },
    {
      "code": "INSURED-EMAIL",
      "answer": "e@test.com"
    },
    {
      "code": "IDENTITY",
      "answer": "850.492.420-37"
    },
    {
      "code": "GENDER"
    },
    {
      "code": "INSURED-CELLPHONE",
      "answer": "(12) 99644.0332"
    },
    {
      "code": "INSURED-ADDRESS-ZIPCODE",
      "answer": "12422-320"
    },
    {
      "code": "INSURED-ADDRESS-STREET",
      "answer": "Rua Antônio Lopes Pereira"
    },
    {
      "code": "INSURED-ADDRESS-NUMBER",
      "answer": "4667"
    },
    {
      "code": "INSURED-ADDRESS-COMPLEMENT",
      "answer": ""
    },
    {
      "code": "INSURED-ADDRESS-NEIGHBORHOOD",
      "answer": "Residencial Campos Maia"
    },
    {
      "code": "INSURED-ADDRESS-CITY",
      "answer": "Pindamonhangaba"
    },
    {
      "code": "INSURED-ADDRESS-STATE",
      "answer": "SP"
    },
    {
      "code": "PROFESSIONAL-REGISTER",
      "answer": "567657"
    },
    {
      "code": "PROFESSION"
    },
    {
      "code": "CATEGORIES",
      "answer": [
        "OROFACIAL-HARMONIZATION",
        "FACIAL-FILLERS",
        "GENERAL-PROCEDURES",
        "IMPLANTS",
        "ORALMAXILLOFACIAL-SURGERY"
      ]
    },
    {
      "code": "LEGAL-TYPE",
      "answer": []
    },
    {
      "code": "RETROACTIVITY",
      "answer": 0
    },
    {
      "code": "RETROACTIVITY-DATE",
      "answer": null
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
      "code": "TERRITORIALITY"
    },
    {
      "code": "SCOPE"
    },
    {
      "code": "LIMIT-DEDUCTIBLE",
      "answer": [
        [
          {
            "code": "LIMIT",
            "answer": 50000
          },
          {
            "code": "DEDUCTIBLE",
            "answer": "INCREASED"
          }
        ]
      ]
    },
    {
      "code": "COMMISSION",
      "answer": 20
    },
    {
      "code": "GRIEVANCE-DISCOUNT",
      "answer": 0
    }
  ]
  }
```




Response
--------




```json
{
    "item": {
        "quotationIdentifier": "c17a2eb8-e006-42d2-8f78-e90c4374a1c6",
        "status": 0,
        "expiredAt": null,
        "quotationDocumentUrl": null,
        "proposal": null,
        "pricing": [
        {
            "variantIdentifier": "d5bd8886-d735-4f07-a138-5a4e773fec3e",
            "underwriting": {
                "approved": true,
                "evaluations": []
                },
                "price": {
                    "commission": 98.89,
                    "grievanceDiscount": 0,
                    "netValue": 494.43,
                    "interestValue": 0,
                    "taxValue": 36.49,
                    "totalValue": 530.92
                    },
                    "payment": {
                        "financialType": "Charge",
                        "paymentOptions": [
                        {
                            "paymentMethod": "All",
                            "paymentType": "CreditCard",
                            "installments": [
                            {
                                "identifier": "0bbf6180-8b49-444b-b734-bf61fcdf0d65",
                                "number": 1,
                                "commissionValue": 98.89,
                                "netValue": 494.43,
                                "interestValue": 0,
                                "taxValue": 36.49,
                                "totalValue": 530.92,
                                "installmentValue": 530.92,
                                "installmentInterest": 0,
                                "installmentTax": 36.49,
                                "dueDates": [
                                "2022-09-22T00:00:00Z"
                                ]
                                },
                                {
                                    "identifier": "1b6d765c-52b6-4b93-ac90-5a3ba32dafdb",
                                    "number": 2,
                                    "commissionValue": 98.89,
                                    "netValue": 494.43,
                                    "interestValue": 0,
                                    "taxValue": 36.49,
                                    "totalValue": 530.92,
                                    "installmentValue": 265.46,
                                    "installmentInterest": 0,
                                    "installmentTax": 18.24,
                                    "dueDates": [
                                    "2022-09-22T00:00:00Z",
                                    "2022-10-01T12:00:00Z"
                                    ]
                                    },
                                    {
                                        "identifier": "e39fd0f3-b501-49cd-b1fa-97d46ea928fe",
                                        "number": 3,
                                        "commissionValue": 98.89,
                                        "netValue": 494.43,
                                        "interestValue": 0,
                                        "taxValue": 36.49,
                                        "totalValue": 530.92,
                                        "installmentValue": 176.97,
                                        "installmentInterest": 0,
                                        "installmentTax": 12.16,
                                        "dueDates": [
                                        "2022-09-22T00:00:00Z",
                                        "2022-10-01T12:00:00Z",
                                        "2022-11-01T12:00:00Z"
                                        ]
                                        },
                                        {
                                            "identifier": "dd400120-9bd6-4165-b8ec-0cacf33df858",
                                            "number": 4,
                                            "commissionValue": 98.89,
                                            "netValue": 494.43,
                                            "interestValue": 0,
                                            "taxValue": 36.49,
                                            "totalValue": 530.92,
                                            "installmentValue": 132.73,
                                            "installmentInterest": 0,
                                            "installmentTax": 9.12,
                                            "dueDates": [
                                            "2022-09-22T00:00:00Z",
                                            "2022-10-01T12:00:00Z",
                                            "2022-11-01T12:00:00Z",
                                            "2022-12-01T12:00:00Z"
                                            ]
                                            },
                                            {
                                                "identifier": "eac6b8fa-1234-4e3f-ad4a-9ac32cf41ab9",
                                                "number": 5,
                                                "commissionValue": 98.89,
                                                "netValue": 494.43,
                                                "interestValue": 0,
                                                "taxValue": 36.49,
                                                "totalValue": 530.92,
                                                "installmentValue": 106.18,
                                                "installmentInterest": 0,
                                                "installmentTax": 7.3,
                                                "dueDates": [
                                                "2022-09-22T00:00:00Z",
                                                "2022-10-01T12:00:00Z",
                                                "2022-11-01T12:00:00Z",
                                                "2022-12-01T12:00:00Z",
                                                "2023-01-01T12:00:00Z"
                                                ]
                                                }
                                                ]
                                                },
                                                {
                                                    "paymentMethod": "Ticket",
                                                    "paymentType": "Ticket",
                                                    "installments": [
                                                    {
                                                        "identifier": "e5c82ef0-2a13-4b7f-96c5-ef51c40514d7",
                                                        "number": 1,
                                                        "commissionValue": 98.89,
                                                        "netValue": 494.43,
                                                        "interestValue": 0,
                                                        "taxValue": 36.49,
                                                        "totalValue": 530.92,
                                                        "installmentValue": 530.92,
                                                        "installmentInterest": 0,
                                                        "installmentTax": 36.49,
                                                        "dueDates": [
                                                        "2022-09-22T00:00:00Z"
                                                        ]
                                                        },
                                                        {
                                                            "identifier": "84366599-e4d0-49d8-8b15-789ea290840b",
                                                            "number": 2,
                                                            "commissionValue": 98.89,
                                                            "netValue": 494.43,
                                                            "interestValue": 0,
                                                            "taxValue": 36.49,
                                                            "totalValue": 530.92,
                                                            "installmentValue": 265.46,
                                                            "installmentInterest": 0,
                                                            "installmentTax": 18.24,
                                                            "dueDates": [
                                                            "2022-09-22T00:00:00Z",
                                                            "2022-10-01T12:00:00Z"
                                                            ]
                                                            },
                                                            {
                                                                "identifier": "ac745af5-f8e1-4160-9439-76315cdfa991",
                                                                "number": 3,
                                                                "commissionValue": 98.89,
                                                                "netValue": 494.43,
                                                                "interestValue": 0,
                                                                "taxValue": 36.49,
                                                                "totalValue": 530.92,
                                                                "installmentValue": 176.97,
                                                                "installmentInterest": 0,
                                                                "installmentTax": 12.16,
                                                                "dueDates": [
                                                                "2022-09-22T00:00:00Z",
                                                                "2022-10-01T12:00:00Z",
                                                                "2022-11-01T12:00:00Z"
                                                                ]
                                                                },
                                                                {
                                                                    "identifier": "77555faa-16f7-4ce6-a8fb-9ebc7fa5e942",
                                                                    "number": 4,
                                                                    "commissionValue": 98.89,
                                                                    "netValue": 494.43,
                                                                    "interestValue": 0,
                                                                    "taxValue": 36.49,
                                                                    "totalValue": 530.92,
                                                                    "installmentValue": 132.73,
                                                                    "installmentInterest": 0,
                                                                    "installmentTax": 9.12,
                                                                    "dueDates": [
                                                                    "2022-09-22T00:00:00Z",
                                                                    "2022-10-01T12:00:00Z",
                                                                    "2022-11-01T12:00:00Z",
                                                                    "2022-12-01T12:00:00Z"
                                                                    ]
                                                                    },
                                                                    {
                                                                        "identifier": "93490f71-9dce-4fa7-8f49-f11052555d48",
                                                                        "number": 5,
                                                                        "commissionValue": 98.89,
                                                                        "netValue": 494.43,
                                                                        "interestValue": 0,
                                                                        "taxValue": 36.49,
                                                                        "totalValue": 530.92,
                                                                        "installmentValue": 106.18,
                                                                        "installmentInterest": 0,
                                                                        "installmentTax": 7.3,
                                                                        "dueDates": [
                                                                        "2022-09-22T00:00:00Z",
                                                                        "2022-10-01T12:00:00Z",
                                                                        "2022-11-01T12:00:00Z",
                                                                        "2022-12-01T12:00:00Z",
                                                                        "2023-01-01T12:00:00Z"
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
                                                                        "executed": "2022-09-15T14:33:57.5185419Z",
                                                                        "errors": null
                                                                        }
```