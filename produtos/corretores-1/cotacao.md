# Criar Cotação

#### Endpoint

```
POST: {{url_ambiente}}/v1/quotation/contracting
```

## Request

```json
{
    "operationCode": "CONSTRUCTION-EQUIPMENT-MULTIPLE-PERIL-PARTNER",
    "registerNumber": "100000",
    "answers": [
        {
            "code": "MODALITY",
            "answer": "CONSTRUCTION-EQUIPMENT-MULTIPLE-PERIL"
        },
        {
            "code": "START-VIGENCY-DATE",
            "answer": "2023-04-19T03:00:00.000Z"
        },
        {
            "code": "CONGENER",
            "answer": "NEW"
        },
        {
            "code": "PERSON-TYPE",
            "answer": "LEGAL"
        },
        {
            "code": "INSURED-NAME",
            "answer": "Teste thomaz travas operacao"
        },
        {
            "code": "INSURED-EMAIL",
            "answer": "thomaz@trin.ca"
        },
        {
            "code": "IDENTITY",
            "answer": "53.941.385/0001-58"
        },
        {
            "code": "GENDER"
        },
        {
            "code": "INSURED-CELLPHONE",
            "answer": "(55) 11999-999"
        },
        {
            "code": "INSURED-ADDRESS-ZIPCODE",
            "answer": "90240-601"
        },
        {
            "code": "INSURED-ADDRESS-STREET",
            "answer": "Avenida Paraná"
        },
        {
            "code": "INSURED-ADDRESS-NUMBER",
            "answer": "1192"
        },
        {
            "code": "INSURED-ADDRESS-COMPLEMENT",
            "answer": ""
        },
        {
            "code": "INSURED-ADDRESS-NEIGHBORHOOD",
            "answer": "São Geraldo"
        },
        {
            "code": "INSURED-ADDRESS-CITY",
            "answer": "Porto Alegre"
        },
        {
            "code": "INSURED-ADDRESS-STATE",
            "answer": "RS"
        },
        {
            "code": "ITEMS",
            "answer": [
                [
                    {
                        "code": "ITEM-IDENTIFIER",
                        "answer": "3aabec8a-45ca-433a-9954-e6ae7853d299"
                    },
                    {
                        "code": "ITEM-TYPE",
                        "answer": "PILE-DRIVER"
                    },
                    {
                        "code": "BRAND",
                        "answer": "marca"
                    },
                    {
                        "code": "SERIAL-NUMBER",
                        "answer": "12378"
                    },
                    {
                        "code": "ORIGIN",
                        "answer": "NATIONAL"
                    },
                    {
                        "code": "EMISSION-DATE",
                        "answer": "2023/03/28"
                    },
                    {
                        "code": "MANUFACTURE-YEAR",
                        "answer": 2023
                    },
                    {
                        "code": "MODEL",
                        "answer": "modelo"
                    },
                    {
                        "code": "ITEM-VALUE",
                        "answer": "R$ 100.000,00"
                    },
                    {
                        "code": "TYPE-USE",
                        "answer": "PERSONAL"
                    },
                    {
                        "code": "INVOICE-NUMBER",
                        "answer": "45207"
                    },
                    {
                        "code": "COVERAGES",
                        "answer": [
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "DAMAGE-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 100.000,00"
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "THEFT-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 100.000,00"
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "OPERATIONS-WATER-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 100.000,00"
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "ELECTRICAL-DAMAGE-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 70.000,00"
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "CIVIL-LIABILITY-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 50.000,00"
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "LOSS-RENT-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 30.000,00"
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "PAYMENT-THIRD-PARTIES-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 30.000,00"
                                }
                            ]
                        ]
                    }
                ],
                [
                    {
                        "code": "ITEM-TYPE",
                        "answer": "VIBRATORS-CONCRETE"
                    },
                    {
                        "code": "BRAND",
                        "answer": "marca vibrador"
                    },
                    {
                        "code": "MODEL",
                        "answer": "modelo vibrador"
                    },
                    {
                        "code": "SERIAL-NUMBER",
                        "answer": "13789"
                    },
                    {
                        "code": "ITEM-VALUE",
                        "answer": "R$ 100.000,00"
                    },
                    {
                        "code": "MANUFACTURE-YEAR",
                        "answer": 2022
                    },
                    {
                        "code": "EMISSION-DATE",
                        "answer": "2023/03/28"
                    },
                    {
                        "code": "INVOICE-NUMBER",
                        "answer": "0978312"
                    },
                    {
                        "code": "ORIGIN",
                        "answer": "NATIONAL"
                    },
                    {
                        "code": "TYPE-USE",
                        "answer": "PERSONAL"
                    },
                    {
                        "code": "COVERAGES",
                        "answer": [
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "DAMAGE-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 100.000,00"
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "THEFT-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 100.000,00"
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "ELECTRICAL-DAMAGE-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 70.000,00"
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "LOSS-RENT-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 30.000,00"
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "PAYMENT-THIRD-PARTIES-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 30.000,00"
                                }
                            ]
                        ]
                    },
                    {
                        "code": "ITEM-IDENTIFIER",
                        "answer": "d161f740-3c91-4186-ba53-b64f42ff1aa3"
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

## Response

Expicamos os campos de retorno neste [link](../../explicando-request-response/request.md#response)

```json
{
    "item": {
        "quotationIdentifier": "663fa4d0-05e6-4e5a-9395-a225bc22d571",
        "status": "Draft",
        "pricing": [
            {
                "variantIdentifier": "3aabec8a-45ca-433a-9954-e6ae7853d299",
                "underwriting": {
                    "approved": true,
                    "evaluations": []
                },
                "price": {
                    "commission": 715.89,
                    "grievanceDiscount": 0.0,
                    "itemValue": 100000.0,
                    "netValue": 3579.45,
                    "interestValue": 0.0,
                    "taxValue": 264.16,
                    "totalValue": 3843.61,
                    "policyLimit": 160000.0,
                    "rates": [
                        {
                            "code": "DAMAGE-COVERAGE",
                            "description": "Danos à bike",
                            "limit": 100000.0,
                            "netValue": 1163.14,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento"
                            }
                        },
                        {
                            "code": "THEFT-COVERAGE",
                            "description": "Roubo e/ou furto qualificado",
                            "limit": 100000.0,
                            "netValue": 945.0,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "15% dos prejuízos indenizáveis com o mínimo de 2,5% do valor do equipamento"
                            }
                        },
                        {
                            "code": "OPERATIONS-WATER-COVERAGE",
                            "description": "Operações em Proximidade de Água",
                            "limit": 100000.0,
                            "netValue": 525.0,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento"
                            }
                        },
                        {
                            "code": "ELECTRICAL-DAMAGE-COVERAGE",
                            "description": "Danos elétricos",
                            "limit": 70000.0,
                            "netValue": 183.75,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento"
                            }
                        },
                        {
                            "code": "CIVIL-LIABILITY-COVERAGE",
                            "description": "Danos Materiais E/ou Corporais a Terceiros (RC)",
                            "limit": 50000.0,
                            "netValue": 132.56,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,00 por evento"
                            }
                        },
                        {
                            "code": "LOSS-RENT-COVERAGE",
                            "description": "Perda de Aluguel",
                            "limit": 30000.0,
                            "netValue": 315.0,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "5 dias"
                            }
                        },
                        {
                            "code": "PAYMENT-THIRD-PARTIES-COVERAGE",
                            "description": "Pagamento de Aluguel a Terceiros",
                            "limit": 30000.0,
                            "netValue": 315.0,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "5 dias"
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
                                    "identifier": "c71b76e8-9478-4826-b688-4bf2086f4444",
                                    "number": 1,
                                    "commissionValue": 715.89,
                                    "netValue": 3579.45,
                                    "interestValue": 0.0,
                                    "taxValue": 264.16,
                                    "totalValue": 3843.61,
                                    "installmentValue": 3843.61,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 264.16,
                                    "dueDates": [
                                        "2023-04-25T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "9e4f6512-a080-4832-947f-a60cbb2e8899",
                                    "number": 2,
                                    "commissionValue": 715.89,
                                    "netValue": 3579.45,
                                    "interestValue": 0.0,
                                    "taxValue": 264.16,
                                    "totalValue": 3843.61,
                                    "installmentValue": 1921.8,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 132.08,
                                    "dueDates": [
                                        "2023-04-25T00:00:00Z",
                                        "2023-05-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "ea313604-56f9-4ab3-9d40-247fa30ea965",
                                    "number": 3,
                                    "commissionValue": 715.89,
                                    "netValue": 3579.45,
                                    "interestValue": 0.0,
                                    "taxValue": 264.16,
                                    "totalValue": 3843.61,
                                    "installmentValue": 1281.2,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 88.05,
                                    "dueDates": [
                                        "2023-04-25T00:00:00Z",
                                        "2023-05-01T12:00:00Z",
                                        "2023-06-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "c9cc7ac7-fa40-4a0c-a6aa-af538032e904",
                                    "number": 4,
                                    "commissionValue": 715.89,
                                    "netValue": 3579.45,
                                    "interestValue": 0.0,
                                    "taxValue": 264.16,
                                    "totalValue": 3843.61,
                                    "installmentValue": 960.9,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 66.04,
                                    "dueDates": [
                                        "2023-04-25T00:00:00Z",
                                        "2023-05-01T12:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "a9eaab18-1259-4360-bf9a-8eac8554f0b4",
                                    "number": 5,
                                    "commissionValue": 715.89,
                                    "netValue": 3579.45,
                                    "interestValue": 0.0,
                                    "taxValue": 264.16,
                                    "totalValue": 3843.61,
                                    "installmentValue": 768.72,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 52.83,
                                    "dueDates": [
                                        "2023-04-25T00:00:00Z",
                                        "2023-05-01T12:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "fbc4e973-9e21-440f-86cd-e3ffd2cf1167",
                                    "number": 6,
                                    "commissionValue": 715.89,
                                    "netValue": 3579.45,
                                    "interestValue": 0.0,
                                    "taxValue": 264.16,
                                    "totalValue": 3843.61,
                                    "installmentValue": 640.6,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 44.03,
                                    "dueDates": [
                                        "2023-04-25T00:00:00Z",
                                        "2023-05-01T12:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "b1527188-366b-4fd3-ad3f-d13f2dd0e4c3",
                                    "number": 7,
                                    "commissionValue": 715.89,
                                    "netValue": 3579.45,
                                    "interestValue": 0.0,
                                    "taxValue": 264.16,
                                    "totalValue": 3843.61,
                                    "installmentValue": 549.09,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 37.74,
                                    "dueDates": [
                                        "2023-04-25T00:00:00Z",
                                        "2023-05-01T12:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "de863745-4007-49af-ad83-6e85a686d0a8",
                                    "number": 8,
                                    "commissionValue": 715.89,
                                    "netValue": 3579.45,
                                    "interestValue": 0.0,
                                    "taxValue": 264.16,
                                    "totalValue": 3843.61,
                                    "installmentValue": 480.45,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 33.02,
                                    "dueDates": [
                                        "2023-04-25T00:00:00Z",
                                        "2023-05-01T12:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "71424dcb-c3ea-43e6-9662-466f191ecb0b",
                                    "number": 9,
                                    "commissionValue": 715.89,
                                    "netValue": 3579.45,
                                    "interestValue": 0.0,
                                    "taxValue": 264.16,
                                    "totalValue": 3843.61,
                                    "installmentValue": 427.07,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 29.35,
                                    "dueDates": [
                                        "2023-04-25T00:00:00Z",
                                        "2023-05-01T12:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "9f147fd6-8cbb-4668-b8b1-b68f70c66f95",
                                    "number": 10,
                                    "commissionValue": 715.89,
                                    "netValue": 3579.45,
                                    "interestValue": 0.0,
                                    "taxValue": 264.16,
                                    "totalValue": 3843.61,
                                    "installmentValue": 384.36,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 26.42,
                                    "dueDates": [
                                        "2023-04-25T00:00:00Z",
                                        "2023-05-01T12:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z",
                                        "2024-01-01T12:00:00Z"
                                    ]
                                }
                            ]
                        },
                        {
                            "paymentMethod": "Ticket",
                            "paymentType": "Ticket",
                            "installments": [
                                {
                                    "identifier": "8079e241-effe-4888-bce2-a3101fad03f6",
                                    "number": 1,
                                    "commissionValue": 715.89,
                                    "netValue": 3579.45,
                                    "interestValue": 0.0,
                                    "taxValue": 264.16,
                                    "totalValue": 3843.61,
                                    "installmentValue": 3843.61,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 264.16,
                                    "dueDates": [
                                        "2023-04-25T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "dcbc3eff-f3e6-4e0c-88d6-4ea60d0fca42",
                                    "number": 2,
                                    "commissionValue": 715.89,
                                    "netValue": 3579.45,
                                    "interestValue": 0.0,
                                    "taxValue": 264.16,
                                    "totalValue": 3843.61,
                                    "installmentValue": 1921.8,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 132.08,
                                    "dueDates": [
                                        "2023-04-25T00:00:00Z",
                                        "2023-05-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "85c9c1f6-0f65-4c3f-8b85-66a612dff465",
                                    "number": 3,
                                    "commissionValue": 715.89,
                                    "netValue": 3579.45,
                                    "interestValue": 0.0,
                                    "taxValue": 264.16,
                                    "totalValue": 3843.61,
                                    "installmentValue": 1281.2,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 88.05,
                                    "dueDates": [
                                        "2023-04-25T00:00:00Z",
                                        "2023-05-01T12:00:00Z",
                                        "2023-06-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "f9622045-a7dc-451c-a6cb-f030430c56be",
                                    "number": 4,
                                    "commissionValue": 715.89,
                                    "netValue": 3579.45,
                                    "interestValue": 0.0,
                                    "taxValue": 264.16,
                                    "totalValue": 3843.61,
                                    "installmentValue": 960.9,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 66.04,
                                    "dueDates": [
                                        "2023-04-25T00:00:00Z",
                                        "2023-05-01T12:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "6809ef70-19e0-4933-a1ac-bea4d384d645",
                                    "number": 5,
                                    "commissionValue": 715.89,
                                    "netValue": 3579.45,
                                    "interestValue": 0.0,
                                    "taxValue": 264.16,
                                    "totalValue": 3843.61,
                                    "installmentValue": 768.72,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 52.83,
                                    "dueDates": [
                                        "2023-04-25T00:00:00Z",
                                        "2023-05-01T12:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "b3ad5d00-d845-4264-9c32-7566982748ce",
                                    "number": 6,
                                    "commissionValue": 715.89,
                                    "netValue": 3579.45,
                                    "interestValue": 0.0,
                                    "taxValue": 264.16,
                                    "totalValue": 3843.61,
                                    "installmentValue": 640.6,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 44.03,
                                    "dueDates": [
                                        "2023-04-25T00:00:00Z",
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
        }
}
```
