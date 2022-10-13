# Create Quotation

#### Endpoint
```
POST: {{url_ambiente}}/v1/quotation
```

💡 **Exemplo de json de request**

```json
{
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
            "answer": "2022-09-08T03:00:00.000Z"
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
            "code": "INSURED-NAME",
            "answer": "Nome segurado"
        },
        {
            "code": "INSURED-EMAIL",
            "answer": "email@email.com"
        },
        {
            "code": "IDENTITY",
            "answer": "000.111.222-33"
        },
        {
            "code": "GENDER",
            "answer": "F"
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
            "code": "ITEMS",
            "answer": [
                [
                    {
                        "code": "SERIAL-NUMBER",
                        "answer": "1213132"
                    },
                    {
                        "code": "ITEM-TYPE",
                        "answer": "TRADITIONAL"
                    },
                    {
                        "code": "MANUFACTURE-YEAR",
                        "answer": 2019
                    },
                    {
                        "code": "MODEL",
                        "answer": "129"
                    },
                    {
                        "code": "COMPETITIONS",
                        "answer": true
                    },
                    {
                        "code": "ORIGINAL-VALUE",
                        "answer": "12312,00"
                    },
                    {
                        "code": "VALUE-AGREEMENT"
                    },
                    {
                        "code": "NEW",
                        "answer": true
                    },
                    {
                        "code": "BRAND",
                        "answer": "AIST"
                    },
                    {
                        "code": "BRAND-NAME",
                        "answer": "AIST"
                    },
                    {
                        "code": "FRAME-TYPE",
                        "answer": "ALUMINUM"
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
                        "answer": "INCREASED"
                    },
                    {
                        "code": "PART-BIKE-AGREEMENT"
                    },
                    {
                        "code": "PARTS",
                        "answer": null
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
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "CIVIL-LIABILITY-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT",
                                    "answer": 100
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "ACCESSORIES-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT",
                                    "answer": 5
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "INTERNATIONAL-COVERAGE"
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