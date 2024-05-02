# Consulta de cotação

## Consulta cotação

<mark style="color:blue;">`GET`</mark> `{{url_ambiente}}/v1/quotation/{registerNumber}/{identifier}`

Retorna informações da cotação com base no identifier

#### Path Parameters

| Name                                         | Type   | Description           |
| -------------------------------------------- | ------ | --------------------- |
| identifier<mark style="color:red;">\*</mark> | string | identifier da cotação |
| registerNumber                               | String | Número Susep          |

#### Headers

| Name                                                        | Type | Description     |
| ----------------------------------------------------------- | ---- | --------------- |
| Ocp-Apim-Subscription-Key<mark style="color:red;">\*</mark> | md5  | Chave de acesso |

{% tabs %}
{% tab title="200: OK Retorno da cotação" %}
````json

{
    "item": {
        "type": "Contracting",
        "quotationIdentifier": "03c2f9e4-7819-4c7d-b90b-5fda53be3ab0",
        "quotationNumber": "6710852750",
        "operationCode": "MEDICAL-CIVIL-LIABILITY-PARTNER",
        "operationConfigIdentifier": "75b8bdac-367a-4f29-bc8c-8c6b389bb4ba",
        "riskAnalysisConfigIdentifier": "e936bb22-cd52-474b-b4a9-936d45e63172",
        "status": "Quoted",
        "expiredAt": "2023-06-14T11:53:51.9861961Z",
        "agents": [
            {
                "type": "Broker",
                "agentIdentifier": "6da62c33-c3f7-44f7-af05-f7f6106ed788"
            },
            {
                "type": "Brokerage",
                "agentIdentifier": "9ac9f6fe-5a25-4cee-baea-ac868222e382"
            },
            {
                "type": "Partner",
                "agentIdentifier": "714924ea-ff52-4f47-919a-10d361fba015"
            }
        ],
        "answers": [
            {
                "code": "MODALITY",
                "answer": "MEDICAL-CIVIL-LIABILITY",
                "properties": {
                    "questionText": "Modalidade",
                    "answerText": "Médico"
                }
            },
            {
                "code": "PERSON-TYPE",
                "answer": "NATURAL",
                "properties": {
                    "questionText": "Segurado",
                    "answerText": "Pessoa Física"
                }
            },
            {
                "code": "CONGENER",
                "answer": "NEW",
                "properties": {
                    "questionText": "Tipo de Seguro",
                    "answerText": "Novo"
                }
            },
            {
                "code": "START-VIGENCY-DATE",
                "answer": "2022-11-20T03:00:00Z",
                "properties": {
                    "questionText": "Início",
                    "answerText": "Às 03:00 do dia 20/11/2022"
                }
            },
            {
                "code": "IDENTITY",
                "answer": "46256465881",
                "properties": {
                    "questionText": "CPF",
                    "answerText": "462.564.658-81"
                }
            },
            {
                "code": "INSURED-NAME",
                "answer": "Nome segurado",
                "properties": {
                    "questionText": "Nome Completo",
                    "answerText": "Nome segurado"
                }
            },
            {
                "code": "INSURED-EMAIL",
                "answer": "email@segurado.com",
                "properties": {
                    "questionText": "E-mail",
                    "answerText": "email@segurado.com"
                }
            },
            {
                "code": "INSURED-CELLPHONE",
                "answer": "11911112222",
                "properties": {
                    "questionText": "Celular",
                    "answerText": "(11) 91111-2222"
                }
            },
            {
                "code": "INSURED-ADDRESS-ZIPCODE",
                "answer": "12345123",
                "properties": {
                    "questionText": "CEP",
                    "answerText": "12345-123"
                }
            },
            {
                "code": "INSURED-ADDRESS-STREET",
                "answer": "Nome da rua",
                "properties": {
                    "questionText": "Rua",
                    "answerText": "Nome da rua"
                }
            },
            {
                "code": "INSURED-ADDRESS-NUMBER",
                "answer": "Número",
                "properties": {
                    "questionText": "Número",
                    "answerText": "Número"
                }
            },
            {
                "code": "INSURED-ADDRESS-NEIGHBORHOOD",
                "answer": "Bairro",
                "properties": {
                    "questionText": "Bairro",
                    "answerText": "Bairro"
                }
            },
            {
                "code": "INSURED-ADDRESS-CITY",
                "answer": "São Paulo",
                "properties": {
                    "questionText": "Cidade",
                    "answerText": "São Paulo"
                }
            },
            {
                "code": "INSURED-ADDRESS-STATE",
                "answer": "SP",
                "properties": {
                    "questionText": "UF",
                    "answerText": "São Paulo"
                }
            },
            {
                "code": "COMMISSION",
                "answer": 20.0,
                "properties": {
                    "questionText": "Comissão",
                    "answerText": "20,00%"
                }
            },
            {
                "code": "GRIEVANCE-DISCOUNT",
                "answer": 0.0,
                "properties": {
                    "questionText": "Agravo",
                    "answerText": "0,00"
                }
            },
            {
                "code": "PROFESSIONAL-REGISTER",
                "answer": "568568567",
                "properties": {
                    "questionText": "Registro Profissional",
                    "answerText": "568568567"
                }
            },
            {
                "code": "CATEGORIES",
                "answer": "OBSTETRICIAN",
                "properties": {
                    "questionText": "Especialidades Médicas",
                    "answerText": "Obstetra"
                }
            },
            {
                "code": "RESIDENT",
                "answer": true,
                "properties": {
                    "questionText": "Médico Residente",
                    "answerText": "Sim"
                }
            },
            {
                "code": "PROCEDURES-ACTIVITIES",
                "answer": [
                    "AESTHETIC-PROCEDURES",
                    "ENDOSCOPY-COLONOSCOPY",
                    "RADIOTHERAPY-CHEMOTHERAPY-IMMUNOTHERAPY",
                    "AESTHETIC-PROCEDURES-MEDICAL-SPECIALTY"
                ],
                "properties": {
                    "questionText": "Realiza alguns dos seguintes procedimentos e/ou atividades",
                    "answerText": [
                        "Procedimentos Estéticos Minimamente Invasivos",
                        "Endoscopia e/ou Colonoscopia",
                        "Radioterapia e/ou Quimioterapia e/ou Imunoterapia",
                        "Procedimentos Estéticos relacionados à Especialidade Médica"
                    ]
                }
            },
            {
                "code": "RETROACTIVITY",
                "answer": 0,
                "properties": {
                    "questionText": "Retroatividade",
                    "answerText": "Sem retroatividade"
                }
            },
            {
                "code": "CLAIMS",
                "answer": "0",
                "properties": {
                    "questionText": "Sinistralidade dos últimos 24 meses",
                    "answerText": "Nenhum"
                }
            },
            {
                "code": "CLAIM-EXPECTATION",
                "answer": false,
                "properties": {
                    "questionText": "Expectativas de sinistro",
                    "answerText": "Não"
                }
            },
            {
                "code": "TERRITORIALITY",
                "answer": "BR",
                "properties": {
                    "questionText": "Territorialidade",
                    "answerText": "Brasil"
                }
            },
            {
                "code": "SCOPE",
                "answer": "NATIONAL",
                "properties": {
                    "questionText": "Âmbito",
                    "answerText": "Território Nacional"
                }
            },
            {
                "code": "LIMIT-DEDUCTIBLE",
                "answer": [
                    [
                        {
                            "code": "VARIANT-IDENTIFIER",
                            "answer": "c754cd54-e2f5-489e-90e5-67c4b424792f",
                            "properties": {
                                "questionText": "Identificador da Variante",
                                "answerText": "c754cd54-e2f5-489e-90e5-67c4b424792f"
                            }
                        },
                        {
                            "code": "LIMIT",
                            "answer": 100000.0,
                            "properties": {
                                "questionText": "Limite de cobertura",
                                "answerText": "R$ 100.000"
                            }
                        },
                        {
                            "code": "DEDUCTIBLE",
                            "answer": "DEFAULT",
                            "properties": {
                                "questionText": "Franquia",
                                "answerText": "Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00"
                            }
                        }
                    ]
                ],
                "properties": {}
            },
            {
                "code": "PRODUCT",
                "answer": "PROFESSIONAL-CIVIL-LIABILITY",
                "properties": {
                    "questionText": "Produto",
                    "answerText": "RC Profissional"
                }
            },
            {
                "code": "CURRENCY",
                "answer": "BRL",
                "properties": {
                    "questionText": "Moeda do Seguro",
                    "answerText": "Real"
                }
            },
            {
                "code": "VIGENCY-DURATION",
                "answer": 1,
                "properties": {
                    "questionText": "Vigência",
                    "answerText": "1 ano"
                }
            },
            {
                "code": "GENDER",
                "answer": "I",
                "properties": {
                    "questionText": "Gênero",
                    "answerText": "Não Informado"
                }
            },
            {
                "code": "INSURED-ADDRESS-COMPLEMENT",
                "answer": "",
                "properties": {
                    "questionText": "Complemento",
                    "answerText": ""
                }
            },
            {
                "code": "PROFESSION",
                "answer": "DOCTOR",
                "properties": {
                    "questionText": "Profissão",
                    "answerText": "Médico"
                }
            },
            {
                "code": "RETROACTIVITY-DATE",
                "answer": "2022-11-20T03:00:00Z",
                "properties": {
                    "questionText": "Data de Retroatividade",
                    "answerText": "20/11/2022"
                }
            },
            {
                "code": "DUE-DAY",
                "answer": 1,
                "properties": {
                    "questionText": "Dia de Vencimento",
                    "answerText": "1"
                }
            },
            {
                "code": "PAYMENT-METHOD",
                "answer": "TICKET",
                "properties": {
                    "questionText": "Meio de pagamento",
                    "answerText": "Boleto"
                }
            }
        ],
        "pricing": [
            {
                "type": "Item",
                "variantIdentifier": "c754cd54-e2f5-489e-90e5-67c4b424792f",
                "underwriting": {
                    "approved": true,
                    "evaluations": []
                },
                "price": {
                    "netValue": 1079.46,
                    "commission": 215.89,
                    "grievanceDiscount": 0.00,
                    "interestValue": 0.0,
                    "taxValue": 79.66,
                    "totalValue": 1159.12
                },
                "payment": {
                    "financialType": "Charge",
                    "paymentOptions": [
                        {
                            "paymentType": "CreditCard",
                            "paymentMethod": "All",
                            "installments": [
                                {
                                    "identifier": "6b45f958-a586-45b8-9af3-b6d80cfc294c",
                                    "number": 1,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 1159.12,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 79.66,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "75e41c25-5f24-4294-b20a-f161acbdba52",
                                    "number": 2,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 579.56,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 39.83,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "6c018fbe-61f9-4c7f-9264-518e2b54aec6",
                                    "number": 3,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 386.37,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 26.55,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "902ae2b1-0f09-490e-8f6c-ca76285f9f4b",
                                    "number": 4,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 289.78,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 19.92,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "3c57fbdf-74eb-4f34-83de-5a89da06fba3",
                                    "number": 5,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 231.82,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 15.93,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "5443e650-2ba4-47c1-ba39-eb9371e0c4eb",
                                    "number": 6,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 193.19,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 13.28,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "c7b85518-bb88-41e7-adad-96a3701d5989",
                                    "number": 7,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 165.59,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 11.38,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "2ccecaea-cef4-4048-9c7b-d3d626702834",
                                    "number": 8,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 144.89,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 9.96,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z",
                                        "2024-01-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "7f24f4bc-07fb-4663-8729-996cdcb2d773",
                                    "number": 9,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 128.79,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 8.85,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z",
                                        "2024-01-01T12:00:00Z",
                                        "2024-02-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "a77d60d9-69ea-47bd-a7c1-4ff3b3455260",
                                    "number": 10,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 115.91,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 7.97,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z",
                                        "2024-01-01T12:00:00Z",
                                        "2024-02-01T12:00:00Z",
                                        "2024-03-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "22ffa55f-5656-4cd1-9cf7-e75a88720af8",
                                    "number": 11,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 105.37,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 7.24,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z",
                                        "2024-01-01T12:00:00Z",
                                        "2024-02-01T12:00:00Z",
                                        "2024-03-01T12:00:00Z",
                                        "2024-04-01T12:00:00Z"
                                    ]
                                }
                            ]
                        },
                        {
                            "paymentType": "Ticket",
                            "paymentMethod": "Ticket",
                            "installments": [
                                {
                                    "identifier": "c9b1914f-06a9-4384-a4de-e567deae6a37",
                                    "number": 1,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 1159.12,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 79.66,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "723fd685-a647-40cf-903a-92829ec54308",
                                    "number": 2,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 579.56,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 39.83,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "f9f0e07d-95f4-400c-a437-b0a884d3e8fe",
                                    "number": 3,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 386.37,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 26.55,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "72f971c1-0316-453f-87df-4990874b97e6",
                                    "number": 4,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 289.78,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 19.92,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "f9f822bd-776e-4a7a-adc8-322c8d1033f8",
                                    "number": 5,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 231.82,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 15.93,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "e604d55e-fc43-4fbd-bdb3-735bfbfb3161",
                                    "number": 6,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 193.19,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 13.28,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "4322851d-fcc5-4914-ba68-c8098b43b3ce",
                                    "number": 7,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 165.59,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 11.38,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "b2c0f63f-5bc5-4207-89fe-2b56ecead4db",
                                    "number": 8,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 144.89,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 9.96,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z",
                                        "2024-01-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "69df04cd-d328-4329-9f27-bbc7cda402d0",
                                    "number": 9,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 128.79,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 8.85,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z",
                                        "2024-01-01T12:00:00Z",
                                        "2024-02-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "ee1cc78c-6a33-4258-aa51-f7a3a223820f",
                                    "number": 10,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 115.91,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 7.97,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z",
                                        "2024-01-01T12:00:00Z",
                                        "2024-02-01T12:00:00Z",
                                        "2024-03-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "96fae90d-c94c-469d-80f6-ee1874037c97",
                                    "number": 11,
                                    "commissionValue": 215.89,
                                    "netValue": 1079.46,
                                    "interestValue": 0.0,
                                    "taxValue": 79.66,
                                    "totalValue": 1159.12,
                                    "installmentValue": 105.37,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 7.24,
                                    "dueDates": [
                                        "2023-06-06T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z",
                                        "2024-01-01T12:00:00Z",
                                        "2024-02-01T12:00:00Z",
                                        "2024-03-01T12:00:00Z",
                                        "2024-04-01T12:00:00Z"
                                    ]
                                }
                            ]
                        }
                    ]
                }
            }
        ],
        "modality": {
            "name": "Responsabilidade Civil Profissional - Área da Saúde",
            "text": "Médico",
            "registerNumber": "15414.612655/2020-92",
            "product": {
                "name": "Responsabilidade Civil Profissional",
                "text": "RC Profissional",
                "branch": "378 - Responsabilidade Civil Profissional",
                "segment": {
                    "name": "Erros e Omissões",
                    "text": "Erros e Omissões"
                }
            }
        },
        "brokerage": {
            "name": "Corretora 100000",
            "identity": "04281856000133",
            "registerNumber": "100000",
            "broker": {
                "phoneNumber": "51981801082",
                "email": "fairfax+100000@trin.ca"
            }
        },
        "insuredName": "Nome segurado",
        "insuredIdentity": "46256465881",
        "insuredEmail": "email@segurado.com",
        "insuredPhoneNumber": "11911112222",
        "isPartner": true
    },
    "success": true,
    "executed": "2023-05-30T11:54:47.8388526Z"
}
```
````
{% endtab %}
{% endtabs %}

## Explicando campos de response de cotação pelo identifier





> **Field**: item.type\
> **Type**: `string`
>
> Tipo da cotação.

> **Field**: item.quotationIdentifier\
> **Type**: `guid`
>
> Identifier da cotação.

> **Field**: item.quotationNumber\
> **Type**: `string`
>
> Numero da cotação.

> **Field**: item.operationCode\
> **Type**: `string`
>
> Código da operação usada para fazer a cotação.

> **Field**: item.status\
> **Type**: `string`
>
> status da cotação.

> **Field**: item.expiredAt\
> **Type**: date
>
> Data de expiração da cotação.

> **Field**: item.insuredName\
> **Type**: `string`
>
> Nome do segurado.

> **Field**: item.insuredIdentity\
> **Type**: `string`
>
> Identificação do segurado.

> **Field**: item.insuredEmail\
> **Type**: `string`
>
> Email do segurado.

> **Field**: item.insuredPhoneNumber\
> **Type**: `string`
>
> Telefone do segurado.

> **Field**: item.answers\[].code\
> **Type**: `string`
>
> Código da pergunta.

> **Field**: item.answers\[].answer\
> **Type**: dynamic
>
> Resposta da pergunta.
>
> * Dependendo do produto cotado, a answer pode ser um array de array contendo objetos compostos por **code** e **answer** ou apenas ser uma **string,** segue um exemplo abaixo**:**
>
>
>
> ```postman_json
> {
>     "code": "code",
>     "answer": ""
> }
> ```
>
> `OU`
>
> ```postman_json
> {
>     "code":"code",
>     "answer":[
>         [
>             {
>                 "code":"code",
>                 "answer":""
>             }
>         ]
>     ]
> }
> ```

> **Field**: item.proposal.date\
> **Type**: `date`
>
> Data da proposta.



> **Field**: item.proposal.number\
> **Type**: `string`
>
> Número da proposta.

> **Field**: item.proposal.DocumentUrl\
> **Type**: `string`
>
> Documento da proposta.



> **Field**: item.proposal.AcceptanceUrl\
> **Type**: `string`
>
> Link para para envio de fotos e checkout.





> **Field**: item.pricing\
> **Type**: `array`
>
> Retorna as propriedades do item, taxas, valores, tipos de pagamentos.\
> Array de items cotados. Ele pode retornar mais de 1 item também.

***

> **Field**: item.pricing\[].variantIdentifier\
> **Type**: `guid`
>
> Identificador do item cotado.

***

> **Field**: item.pricing\[].underwriting.approved\
> **Type**: `boolean`
>
> Retorna true ou false referente as regras de subscrição do produto.

***

> **Field**: item.pricing\[].underwriting.evaluations\
> **Type**: `array`
>
> Retorna aviso referente as questões do questionário de risco do produto.

***

> **Field**: item.pricing\[].price.commission\
> **Type**: `decimal`
>
> Comissão de corretagem.

***

> **Field**: item.pricing\[].price.grievanceDiscount\
> **Type**: `decimal`
>
> Porcentagem de agravo adicionada ao valor da cotação, onde os valores permitidos vão de 0% até 500%.

***

> **Field**: item.pricing\[].price.itemValue\
> **Type**: `decimal`
>
> Valor do item.

***

> **Field**: item.pricing\[].price.netValue\
> **Type**: `decimal`
>
> Valor de prêmio líquido sem o IOF.

***

> **Field**: item.pricing\[].price.interestValue\
> **Type**: `decimal`
>
> Valor de juros (Por enquanto nenhum produto possui juros, nem para boleto e nem para cartão, mas futuramente terá para boleto).

***

> **Field**: item.pricing\[].price.taxValue\
> **Type**: `decimal`
>
> Valor de IOF.

***

> **Field**: item.pricing\[].price.totalValue\
> **Type**: `decimal`
>
> Valor de Prêmio Total, composto pelo prêmio líquido somado ao IOF.

***

> **Field**: item.pricing\[].price.policyLimit\
> **Type**: `decimal`
>
> Valor de Limite da apólice (no caso de Bikes, o valor do limite da apólice é igual ao valor informado para a bike).

***

> **Field**: item.pricing\[].price.rates\
> **Type**: `array`
>
> Trata-se de um array, que retornará todas as coberturas contratadas para o produto.

***

> **Field**: item.pricing\[].payment.financialType\
> **Type**: `text`
>
> Trata-se do tipo de financeiro que no caso é "Cobrança".

***

> **Field**: item.pricing\[].payment.paymentOptions\
> **Type**: `array`
>
> Retorna as opções de pagamento disponíveis que são: Boleto e Cartão de crédito.

***

> **Field**: item.pricing\[].price.rates\[].code\
> **Type**: `text`
>
> Exibe o código que identifica a ou as coberturas contratadas. Ex: DAMAGE-COVERAGE, trata-se da cobertura de Danos à Bike.

***

> **Field**: item.pricing\[].price.rates\[].description\
> **Type**: `text`
>
> Trata-se do nome da cobertura em português. Ex: "Danos à Bike".

***

> **Field**: item.pricing\[].price.rates\[].limit\
> **Type**: `decimal`
>
> Trata-se do valor do limite da cobertura.

***

> **Field**: item.pricing\[].price.rates\[].netValue\
> **Type**: `decimal`
>
> Valor do prêmio específico de cada cobertura contratada.

***

> **Field**: item.pricing\[].price.rates\[].deductible.code\
> **Type**: `text`
>
> Trata-se do código identificador de cada franquia.

***

> **Field**: item.pricing\[].price.rates\[].deductible.text\
> **Type**: `text`
>
> Nome da franquia selecionada em português - Ex: "Padrão".

***

> **Field**: item.pricing\[].price.rates\[].deductible.description\
> **Type**: `text`
>
> Descrição da franquia.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].paymentMethod\
> **Type**: `text`
>
> Retorna o nome da forma de pagamento que pode ser: Ticket (Boleto) ou CreditCard (Cartão de Crédito).

***

> **Field**: item.pricing\[].payment.paymentOptions\[].paymentType\
> **Type**: `text`
>
> Forma de pagamento que pode ser escolhida: Boleto ou Cartão de crédito.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\
> **Type**: `array`
>
> Retorna a quantidade de parcelas disponíveis para realizar o pagamento referente ao tipo de pagamento.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].identifier\
> **Type**: `guid`
>
> Código identificador da parcela.\
> Este é o código necessário enviar ao selecionar o método de pagamento. Exemplo: Se foi selecionado cartão de crédito, enviar o identificador daquele meio de pagamento.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].number\
> **Type**: `integer`
>
> Número da respectiva parcela (2 parcela, número 2).

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].commissionValue\
> **Type**: `decimal`
>
> Valor de comissão de cada parcela.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].netValue\
> **Type**: `decimal`
>
> Valor de prêmio líquido de cada parcela, ou seja, sem o IOF.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].interestValue\
> **Type**: `decimal`
>
> Valor de juros de cada parcela.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].taxValue\
> **Type**: `decimal`
>
> IOF que implica em cada parcela.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].totalValue\
> **Type**: `decimal`
>
> Valor total de cada parcela que é composto do valor líquido + IOF.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].installmentValue\
> **Type**: `decimal`
>
> Valor total da parcela.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].installmentInterest\
> **Type**: `decimal`
>
> Valor de juros da parcela.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].installmentTax\
> **Type**: `decimal`
>
> Valor de IOF de cada parcela.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].dueDates\
> **Type**: `array<string>`
>
> Datas de vencimento da parcela caso a forma de pagamento seja boleto.



> **Field**: item.modality.name\
> **Type**: `string`
>
> Nome da modalidade.

> **Field**: item.modality.text\
> **Type**: `string`
>
> Nome da modalidade.

> **Field**: item.modality.registerNumber\
> **Type**: `string`
>
> Numero de registro da modalidade.

> **Field**: item.modality.product.name\
> **Type**: `string`
>
> Nome do produto.

> **Field**: item.modality.product.text\
> **Type**: `string`
>
> Nome do produto.

> **Field**: item.modality.product.branch\
> **Type**: `string`
>
> Ramo do seguro.

> **Field**: item.modality.product.segment.name\
> **Type**: `string`
>
> Nome do segmento.

> **Field**: item.modality.product.segment.text\
> **Type**: `string`
>
> Nome do segmento.

> **Field**: item.brokerage.name\
> **Type**: `string`
>
> Nome da corretora.

> **Field**: item.brokerage.identity\
> **Type**: `string`
>
> Identificação da corretora.

> **Field**: item.brokerage.registerNumber\
> **Type**: `string`
>
> Susep da corretora.

> **Field**: item.brokerage.broker.phoneNumber\
> **Type**: `string`
>
> Telefone do corretor.

> **Field**: item.brokerage.broker.email\
> **Type**: `string`
>
> Email do corretor.





## Listagem de cotações

<mark style="color:blue;">`GET`</mark> `{{url_ambiente}}/v1/quotation/{registerNumber}/all`

Retorna lista de cotações

#### Path Parameters

| Name           | Type   | Description  |
| -------------- | ------ | ------------ |
| registerNumber | String | Número Susep |

#### Query Parameters

| Name      | Type   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| --------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| page      |        | Passar o número da chave                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| sort      |        | <p>Possível ordernar pelo campo desejado.<br><br>Os valores possíveis para esta query parameter são:</p><p>Caso queira definir se a ordem sera crescente ou não, basta passar o operador <code>-</code> quando for decrescente.<br>Caso queria passar mais de um campo para ordenação, tambem é possivel, basta colocar os campos separados por <code>,</code></p><p>Exemplo:<br><code>{{url_ambiente}}/v1/policy/all?sort=-status,insuredname</code><br>No exemplo acima é passado dois campos para a ordenação, onde o status sera em ordem decrescente e o insuredName será em ordem crescente.</p> |
| Search    |        | Campo para buscar pelo nome do segurado ou CPF/CNPJ.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Modality  |        | Campo para buscar pela modalidade.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Product   |        | Campo para buscar pelo produto.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| startDate | String | Data de inicio de cração da cotação.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| endDate   | String | Data limite de criação da cotação.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| status    | String | <p>Campo para buscar pelo status. Os valores possíveis para esta query parameter são:</p><p></p><p><strong>Draft</strong>= Rascunho.</p><p><strong>Quoted</strong> = Cotada.</p><p><strong>Saved</strong> = Salva.</p><p><strong>Choosed</strong> = Proposta do corretor.</p><p><strong>Proposal</strong> = Proposta enviada.</p><p><strong>Confirmed</strong> = Confirmada.</p><p><strong>Received</strong> = Recebido documentos do segurado.</p><p><strong>Accepted</strong> = Aceita.</p><p><strong>Finished</strong> = Finalizada.</p><p><strong>Expired</strong> = Expirada.</p>                 |
| type      | String | <p>Buscar pelo tipo da cotação.</p><p>Os valores possíveis para esta query parameter são:</p><p></p><p><strong>Contracting</strong> = Contratação.</p><p><strong>Renewal</strong> = Renovação.</p><p><strong>Endorsement</strong> = Endosso.</p><p><strong>Cancellation</strong> = Cancelamento.</p><p><strong>Simulation</strong> = Simulação.</p><p></p><p></p>                                                                                                                                                                                                                                      |

#### Headers

| Name                                                        | Type | Description     |
| ----------------------------------------------------------- | ---- | --------------- |
| Ocp-Apim-Subscription-Key<mark style="color:red;">\*</mark> | md5  | Chave de acesso |

{% tabs %}
{% tab title="200: OK Listagem retornada" %}
```json
{
    "totalItems": 1169,
    "itemsPerPage": 10,
    "list": [
        {
            "quotationIdentifier": "24943f77-a860-4f41-a560-313a332350f2",
            "expiredAt": "2023-07-29T03:00:00Z",
            "createdAt": "2023-05-25T02:43:56.3912784Z",
            "type": "Renewal",
            "typeText": "Renovação",
            "status": "Finished",
            "statusText": "Finalizada",
            "insuredName": "Segurado Teste RENEW 46631866375",
            "insuredEmail": "email",
            "insuredPhoneNumber": "51984483080",
            "insuredIdentity": "46631866331",
            "modalityCode": "DENTIST-CIVIL-LIABILITY",
            "modalityText": "Dentista",
            "productCode": "PROFESSIONAL-CIVIL-LIABILITY",
            "productText": "RC Profissional",
            "personType": "NATURAL",
            "quotationDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/quotation/24943f77-a860-4f41-a560-313a332350f2/cotacao_SeguradoTesteRENEW46631866375_4129219937_v01.00_oezj.pdf",
            "previousPolicyNumber": "10078000119929151"
        },
        {
            "quotationIdentifier": "64a1dc58-1297-4957-8c88-29135f29e12b",
            "expiredAt": "2023-07-25T03:00:00Z",
            "createdAt": "2023-05-25T17:11:56.0465801Z",
            "type": "Renewal",
            "typeText": "Renovação",
            "status": "Draft",
            "statusText": "Rascunho",
            "insuredName": "Teste RENEW - Corretora 100000 - Renovação para eu mesmo",
            "insuredEmail": "email",
            "insuredIdentity": "04281856000131",
            "modalityCode": "INSURANCE-BROKER-CIVIL-LIABILITY",
            "modalityText": "Corretor de Seguros",
            "productCode": "PROFESSIONAL-CIVIL-LIABILITY",
            "productText": "RC Profissional",
            "personType": "LEGAL",
            "previousPolicyNumber": "10078000120072543"
        },
        {
            "quotationIdentifier": "49afbe4b-6547-43e3-80bf-91addc676569",
            "expiredAt": "2023-07-24T03:00:00Z",
            "createdAt": "2023-05-25T02:45:30.4692677Z",
            "type": "Renewal",
            "typeText": "Renovação",
            "status": "Proposal",
            "statusText": "Proposta enviada",
            "insuredName": "Segurado Teste RENEW 35639515350",
            "insuredEmail": "email",
            "insuredPhoneNumber": "51984483031",
            "insuredIdentity": "35639515331",
            "modalityCode": "INSURANCE-BROKER-CIVIL-LIABILITY",
            "modalityText": "Corretor de Seguros",
            "productCode": "PROFESSIONAL-CIVIL-LIABILITY",
            "productText": "RC Profissional",
            "personType": "NATURAL",
            "quotationDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/quotation/49afbe4b-6547-43e3-80bf-91addc676569/cotacao_SeguradoTesteRENEW35639515350_4759909113_v01.00_zmo8.pdf",
            "previousPolicyNumber": "10078000119940403"
        },
        {
            "quotationIdentifier": "6c70e34a-fddd-42b6-9fba-d98f37f0baf6",
            "expiredAt": "2023-07-24T03:00:00Z",
            "createdAt": "2023-05-25T02:42:20.4705939Z",
            "type": "Renewal",
            "typeText": "Renovação",
            "status": "Finished",
            "statusText": "Finalizada",
            "insuredName": "Segurado Teste RENEW 10005854577063",
            "insuredEmail": "email",
            "insuredPhoneNumber": "51984483080",
            "insuredIdentity": "100058545031",
            "modalityCode": "MEDICAL-CIVIL-LIABILITY",
            "modalityText": "Médico",
            "productCode": "PROFESSIONAL-CIVIL-LIABILITY",
            "productText": "RC Profissional",
            "personType": "LEGAL",
            "quotationDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/quotation/6c70e34a-fddd-42b6-9fba-d98f37f0baf6/cotacao_SeguradoTesteRENEW10005854577063_4225222309_v01.00_l4as.pdf",
            "previousPolicyNumber": "10078000119909019"
        },
        {
            "quotationIdentifier": "570e6e92-0693-4d54-b329-eb8cb5c098d1",
            "expiredAt": "2023-07-17T03:00:00Z",
            "createdAt": "2023-05-25T16:56:11.5823687Z",
            "type": "Renewal",
            "typeText": "Renovação",
            "status": "Draft",
            "statusText": "Rascunho",
            "insuredName": "Teste RENEW - Médico - Seguro Novo - Troca de Corretora",
            "insuredEmail": "email",
            "insuredIdentity": "80487179331",
            "modalityCode": "MEDICAL-CIVIL-LIABILITY",
            "modalityText": "Médico",
            "productCode": "PROFESSIONAL-CIVIL-LIABILITY",
            "productText": "RC Profissional",
            "personType": "NATURAL",
            "previousPolicyNumber": "10078000118259486"
        },
        {
            "quotationIdentifier": "56073f56-4f3a-4422-9aed-7b015b677e53",
            "expiredAt": "2023-06-27T03:00:00Z",
            "createdAt": "2023-04-28T19:39:35.0022985Z",
            "type": "Renewal",
            "typeText": "Renovação",
            "status": "Finished",
            "statusText": "Finalizada",
            "insuredName": "Teste RENEW - Médicos - Incident",
            "insuredEmail": "email",
            "insuredPhoneNumber": "51981801082",
            "insuredIdentity": "53682752431",
            "modalityCode": "MEDICAL-CIVIL-LIABILITY",
            "modalityText": "Médico",
            "productCode": "PROFESSIONAL-CIVIL-LIABILITY",
            "productText": "RC Profissional",
            "personType": "NATURAL",
            "quotationDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/quotation/56073f56-4f3a-4422-9aed-7b015b677e53/cotacao_TesteRENEWMedicosIncident_9940587334_v01.00_ep9x.pdf",
            "previousPolicyNumber": "10078000115288530"
        },
        {
            "quotationIdentifier": "d693b588-d658-4051-b625-b2855ba5aadc",
            "expiredAt": "2023-06-26T03:00:00Z",
            "createdAt": "2023-04-28T02:06:23.9275156Z",
            "type": "Renewal",
            "typeText": "Renovação",
            "status": "Finished",
            "statusText": "Finalizada",
            "insuredName": "Segurado Teste RENEW 10007478363160",
            "insuredEmail": "email",
            "insuredPhoneNumber": "51984483080",
            "insuredIdentity": "10007478363131",
            "modalityCode": "MEDICAL-CIVIL-LIABILITY",
            "modalityText": "Médico",
            "productCode": "PROFESSIONAL-CIVIL-LIABILITY",
            "productText": "RC Profissional",
            "personType": "LEGAL",
            "quotationDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/quotation/d693b588-d658-4051-b625-b2855ba5aadc/cotacao_SeguradoTesteRENEW10007478363160_4990848273_v01.00_cjlj.pdf",
            "previousPolicyNumber": "10078000115179562"
        },
        {
            "quotationIdentifier": "ef16c86a-6903-457e-9e31-91d08d845e9b",
            "expiredAt": "2023-06-18T03:00:00Z",
            "createdAt": "2023-05-18T13:29:54.6975531Z",
            "type": "Renewal",
            "typeText": "Renovação",
            "status": "Draft",
            "statusText": "Rascunho",
            "insuredName": "Teste RENEW - Médico - Seguro Novo - Sem Retro - Emitido",
            "insuredEmail": "email",
            "insuredIdentity": "30363583431",
            "modalityCode": "MEDICAL-CIVIL-LIABILITY",
            "modalityText": "Médico",
            "productCode": "PROFESSIONAL-CIVIL-LIABILITY",
            "productText": "RC Profissional",
            "personType": "NATURAL",
            "previousPolicyNumber": "10078000113914532"
        },
        {
            "quotationIdentifier": "feb22864-c098-40a4-8f75-b4737999249a",
            "expiredAt": "2023-06-17T03:00:00Z",
            "createdAt": "2023-04-18T18:56:09.8917697Z",
            "type": "Renewal",
            "typeText": "Renovação",
            "status": "Finished",
            "statusText": "Finalizada",
            "insuredName": "Teste RENEW - Médico PJ - Seguro Novo",
            "insuredEmail": "email",
            "insuredPhoneNumber": "51981801082",
            "insuredIdentity": "70788455000131",
            "modalityCode": "MEDICAL-CIVIL-LIABILITY",
            "modalityText": "Médico",
            "productCode": "PROFESSIONAL-CIVIL-LIABILITY",
            "productText": "RC Profissional",
            "personType": "LEGAL",
            "quotationDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/quotation/feb22864-c098-40a4-8f75-b4737999249a/cotacao_TesteRENEWMedicoPJSeguroNovo_0219257644_v01.00_nmq5.pdf",
            "previousPolicyNumber": "10078000113558279"
        },
        {
            "quotationIdentifier": "5a389b4a-f41b-4054-b357-3d9e50d49931",
            "expiredAt": "2023-06-14T03:00:00Z",
            "createdAt": "2023-04-11T13:56:31.6918011Z",
            "type": "Renewal",
            "typeText": "Renovação",
            "status": "Draft",
            "statusText": "Rascunho",
            "insuredName": "Segurado Teste RENEW 92387155726",
            "insuredEmail": "email",
            "insuredIdentity": "92387155726",
            "modalityCode": "DENTIST-CIVIL-LIABILITY",
            "modalityText": "Dentista",
            "productCode": "PROFESSIONAL-CIVIL-LIABILITY",
            "productText": "RC Profissional",
            "personType": "NATURAL",
            "previousPolicyNumber": "10078000111570669"
        }
    ],
    "success": true,
    "executed": "2023-05-30T11:44:59.990466Z"
}
```
{% endtab %}
{% endtabs %}

***

## Explicando campos de response da listagem de cotação

> **Field**: totalItems\
> **Type**: `integer`
>
> Numero total de cotações.

> **Field**: itemsPerPage\
> **Type**: `integer`
>
> Items exibidos por pagina .

> **Field**: list\[].quotationIdentifier\
> **Type**: guid
>
> Identifier da cotação .

> **Field**: list\[].expiredAt\
> **Type**: date
>
> Data de expiração da cotação .

> **Field**: list\[].createdAt\
> **Type**: date
>
> Data de criação da cotação .

> **Field**: list\[].type\
> **Type**: `string`
>
> Tipo da cotação.

> **Field**: list\[].typeText\
> **Type**: `string`
>
> Tipo da cotação.

> **Field**: list\[].status\
> **Type**: `string`
>
> Status da cotação.

> **Field**: list\[].statusText\
> **Type**: `string`
>
> Status da cotação.

> **Field**: list\[].insuredName\
> **Type**: `string`
>
> Nome do segurado.

> **Field**: list\[].insuredEmail\
> **Type**: `string`
>
> Email do segurado.

> **Field**: list\[].insuredPhoneNumber\
> **Type**: `string`
>
> Telefone do segurado.

> **Field**: list\[].insuredIdentity\
> **Type**: `string`
>
> Identificação do segurado.

> **Field**: list\[].modalityCode\
> **Type**: `string`
>
> Modalidade da cotação.

> **Field**: list\[].modalityText\
> **Type**: `string`
>
> Modalidade da cotação.

> **Field**: list\[].productCode\
> **Type**: `string`
>
> Produto da cotação.

> **Field**: list\[].productText\
> **Type**: `string`
>
> Produto da cotação.

> **Field**: list\[].personType\
> **Type**: `string`
>
> Tipo de entidade, **Fisica** ou **Juridica**

> **Field**: list\[].quotationDocumentUrl\
> **Type**: `string`
>
> Url do pdf de cotação.

> **Field**: list\[].previousPolicyNumber\
> **Type**: `string`
>
> Numero da apólice anterior.
