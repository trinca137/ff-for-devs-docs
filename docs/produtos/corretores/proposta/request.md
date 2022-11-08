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
	"identifier":"2942faa1-09b8-4345-9bdd-6764c4f1ad35",
    "operationCode": "INSURANCE-BROKER-CIVIL-LIABILITY-PARTNER",
    "answers": [
         {
            "code": "MODALITY",
            "answer": "INSURANCE-BROKER-CIVIL-LIABILITY"
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
            "answer": "2022-09-20T03:00:00.000Z"
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
            "answer": "segurado"
        },
        {
            "code": "INSURED-EMAIL",
            "answer": "samuel@gmail.com"
        },
        {
            "code": "IDENTITY",
            "answer": "209.654.740-70"
        },
        {
            "code": "GENDER"
        },
        {
            "code": "INSURED-CELLPHONE",
            "answer": "(12) 99644.1335"
        },
        {
            "code": "INSURED-ADDRESS-ZIPCODE",
            "answer": "12422-120"
        },
        {
            "code": "INSURED-ADDRESS-STREET",
            "answer": "Rua Antônio"
        },
        {
            "code": "INSURED-ADDRESS-NUMBER",
            "answer": "4657"
        },
        {
            "code": "INSURED-ADDRESS-COMPLEMENT",
            "answer": ""
        },
        {
            "code": "INSURED-ADDRESS-NEIGHBORHOOD",
            "answer": "Residencial Campos"
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
            "answer": "67867"
        },
        {
            "code": "REGISTER-NUMBER-TYPE",
            "answer": "FULL"
        },
        {
            "code": "PROFESSION"
        },
        {
            "code": "CATEGORIES",
            "answer": [
                "CAR",
                "AERONAUTICAL"
            ]
        },
        {
            "code": "DIGITAL-CERTIFICATION-COVERAGE"
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
                        "answer": 100000
                    },
                    {
                        "code": "DEDUCTIBLE",
                        "answer": "DEFAULT"
                    },
                    {
                        "code": "VARIANT-IDENTIFIER",
                        "answer": "c338d8ce-d7fb-4968-990f-5b400f138283"
                    }
                ]
            ]
        },
        {
            "code": "COMMISSION",
            "answer": 1
        },
        {
            "code": "GRIEVANCE-DISCOUNT",
            "answer": 0
        },
              {
         "code":"PAYMENT-METHOD",
         "answer":"CREDIT-CARD"
      },
      {
         "code":"INSURED-BIRTH-DATE",
         "answer":"1990-09-08T03:00:00.000Z"
      },
      {
         "code":"PAYMENT-INSTALLMENT-IDENTIFIER",
         "answer":"6689e62a-ce02-4633-9e11-d01695c549ed"
      }
    ]
}
```



Response
--------



```json
{
    "item": {
        "quotationIdentifier": "2942faa1-09b8-4345-9bdd-6764c4f1ad35",
        "status": "Draft",
        "proposal": {
            "number": "29251022080001",
            "date": "0001-01-01T00:00:00Z"
        },
        "pricing": [
            {
                "variantIdentifier": "c338d8ce-d7fb-4968-990f-5b400f138283",
                "underwriting": {
                    "approved": true,
                    "evaluations": []
                },
                "price": {
                    "commission": 2.54,
                    "grievanceDiscount": 0,
                    "netValue": 253.91,
                    "interestValue": 0,
                    "taxValue": 18.74,
                    "totalValue": 272.65
                },
                "payment": {
                    "financialType": "Charge",
                    "paymentOptions": [
                        {
                            "paymentMethod": "All",
                            "paymentType": "CreditCard",
                            "installments": [
                                {
                                    "identifier": "6689e62a-ce02-4633-9e11-d01695c549ed",
                                    "number": 1,
                                    "commissionValue": 2.54,
                                    "netValue": 253.91,
                                    "interestValue": 0,
                                    "taxValue": 18.74,
                                    "totalValue": 272.65,
                                    "installmentValue": 272.65,
                                    "installmentInterest": 0,
                                    "installmentTax": 18.74,
                                    "dueDates": [
                                        "2022-09-28T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "dffd5b1b-1b90-407b-875d-5c7863959749",
                                    "number": 2,
                                    "commissionValue": 2.54,
                                    "netValue": 253.91,
                                    "interestValue": 0,
                                    "taxValue": 18.74,
                                    "totalValue": 272.65,
                                    "installmentValue": 136.32,
                                    "installmentInterest": 0,
                                    "installmentTax": 9.37,
                                    "dueDates": [
                                        "2022-09-28T00:00:00Z",
                                        "2022-10-15T12:00:00Z"
                                    ]
                                }
                            ]
                        },
                        {
                            "paymentMethod": "Ticket",
                            "paymentType": "Ticket",
                            "installments": [
                                {
                                    "identifier": "c8be5748-d0ef-41b3-b83c-71e696867867",
                                    "number": 1,
                                    "commissionValue": 2.54,
                                    "netValue": 253.91,
                                    "interestValue": 0,
                                    "taxValue": 18.74,
                                    "totalValue": 272.65,
                                    "installmentValue": 272.65,
                                    "installmentInterest": 0,
                                    "installmentTax": 18.74,
                                    "dueDates": [
                                        "2022-09-28T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "a5c49c0a-ec59-4b24-9e3e-b62d93da87be",
                                    "number": 2,
                                    "commissionValue": 2.54,
                                    "netValue": 253.91,
                                    "interestValue": 0,
                                    "taxValue": 18.74,
                                    "totalValue": 272.65,
                                    "installmentValue": 136.32,
                                    "installmentInterest": 0,
                                    "installmentTax": 9.37,
                                    "dueDates": [
                                        "2022-09-28T00:00:00Z",
                                        "2022-10-15T12:00:00Z"
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
    "executed": "2022-09-21T12:40:39.4651958Z"
}
```
