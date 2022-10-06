# Criar Cotação

```
**METHOD** POST
**Endpoint**: https://azuh1-br-fairfax-gateway.azure-api.net/partner/api/v1/quotation
**Content**-Type: application/x-www-form-urlencoded
**Ocp-Apim-Subscription-Key**: your apiKey
```
___

💡 **Exemplo do JSON de Request**


```json
{
    "operationCode": "BIKE-MULTIPLE-PERIL",
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
            "answer": "seg teste"
        },
        {
            "code": "INSURED-NAME",
            "answer": "samuel emidio"
        },
        {
            "code": "INSURED-EMAIL",
            "answer": "e@test.come"
        },
        {
            "code": "IDENTITY",
            "answer": "462.564.658-81"
        },
        {
            "code": "GENDER"
        },
        {
            "code": "INSURED-CELLPHONE",
            "answer": "(12) 99644-0332"
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
            "answer": "98"
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
            "code": "ITEMS",
            "answer": [
                [
                    {
                        "code": "ITEM-IDENTIFIER",
                        "answer": "92cc00b4-9ba6-4f50-bf5a-38b76ade9370"
                    },
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
                        "answer": [
                            [
                                {
                                    "code": "PART-TYPE",
                                    "answer": [
                                        "UNMODIFIED"
                                    ]
                                }
                            ]
                        ]
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
___


💡 **Desmistificando o JSON de request - parte 1**


```json
{
	"operationCode":"BIKE-MULTIPLE-PERIL",
	"answers":[]
}
```

```
**Field**: **OperationCode**
**Type**: text
campo obrigatorio
* campo usado para definir qual produto esta sendo cotado, neste caso o produto é bike, representado pelo operation code "BIKE-MULTIPLE-PERIL".
```

```
**Field**: answers
**Type**: array<answer>
campo obrigatorio
* campo usado para enviar as perguntas mais gerais de uma cotacao, um exemplo de pergunta seria se a pessoa que esta realizando a operacao é juridica ou fisica.
veremos mais detalhes sobre essas perguntas mais abaixo na documentacao.
Abaixo, podemos ver a modelagem de answer.

```

#### Answer model

```json

	{
		"code":"code",
		"answer":dynamic
	}
```

```
**Field**: code
**Type**: text
campo obrigatorio
* campo usado para identificar o a pergunta que esta sendo enviada.
```

```
**Field**: answer
**Type**: dynamic
campo obrigatorio
* campo usado como resposta para a pergunta, este campo é dinamico, podendo ser enviado de uma simples string até um array de array de answer "**array<array<answer>>**" 
```
___
 

💡 **Desmistificando o JSON de Request - parte 2**

Como explicado mais acima, o campo **answers** tem como finalidade enviar as perguntas referentes a cotação, abaixo você verá os valores que podem estar inclusos nesse array.


```json
{
    "operationCode": "BIKE-MULTIPLE-PERIL",
    "answers": [
        {
            "code": "MODALITY",
            "answer": "BIKE-MULTIPLE-PERIL"
        }
    ]
}
```


> **Code**: MODALITY <br/>
> **Type**: text <br/>
> **Campo Obrigatório:** Sim <br/>
> **pergunta usada para definir qual produto esta sendo cotado, neste caso o produto é bike, representado pelo operation code "BIKE-MULTIPLE-PERIL"*

___

> **Code**: PERSON-TYPE <br/>
> **Type**: text <br/>
> **Campo Obrigatório:** Sim <br/>
> **Valores Esperados:**<br/>
> - **NATURAL =** significa que a pessoa em questao é fisica<br/>
> - **LEGAL =** significa que a pessoa em questao é juridica<br/>
> **pergunta usada para saber que a cotacao esta sendo feita por uma pessoa fisica ou juridica.*

___


> **Code**: START-VIGENCY-DATE <br/>
> **Type**: date <br/>
> **Campo Obrigatório:** Sim <br/>
> **pergunta usada para definir o inicio da vigencia do seguro.*


```text
*Code*: VIGENCY-DURATION
**Type**: integer
No momento so é possivel o padrão, não sendo possível mudar a duração da vigência

* pergunta usada para definir a duracao da vigência em anos, o valor padrao é 1
```

```
**Code**: VIGENCY-RETROACTIVITY-AGREEMENT
**Type**: boolean 
* pergunta usada para definir "**Entendimento e concordância de vigência retroativa**"
se defida  como true, indica que "**Estou ciente e de acordo que não possuo conhecimento de qualquer fato que possa acarretar uma reclamação futura entre o início de vigência e a data de emissão da apólice**"
```

```
**Code**: CONGENER
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para definir se a cotacao em questao é um seguro novo, ou uma renovacao.
os valores possiveis para esta pergunta sao:
**NEW =** indica que é um seguro novo
**RENEW =** indica que é a renovacao de um seguro
```

```
**Code**: PREVIOUS-INSURER
**Type**: text
Obrigatorio que esteja incluido no array (se a cotacao for uma renovacao)
* pergunta usada para definir qual era a seguradora anterior.
* neste campo se deve enviar um **cnpj**
```

```
**Code**: PREVIOUS-NAME
**Type**: text
Obrigatorio que esteja incluido no array (se a cotacao for uma renovacao)
* pergunta usada para definir o nome da seguradora anterior.
```

```
**Code**: INSURED-NAME
**Type**: text
Obrigatorio que esteja incluido no array
* pergunta usada para definir o nome do segurado
```

```
**Code**: INSURED-EMAIL
**Type**: text
Obrigatorio que esteja incluido no array
* pergunta usada para definir o email do segurado
```

```
**Code**: IDENTITY
**Type**: text
Obrigatorio que esteja incluido no array
* pergunta usada para definir a identificacao do segurado, seja ela um **cpf** ou um **cnpj**
```

```
**Code**: GENDER
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para definir o genero do segurado
os possiveis valores para esta pergunta são:
**M =** masculino
**F =** feminino
I = nao informado
* o valor padrao é "**I**"
```

```
**Code**: INSURED-CELLPHONE
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para definir o telefone do segurado
```

```
**Code**: INSURED-ADDRESS-ZIPCODE
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para definir o codigo postal do segurado
```

```
**Code**: INSURED-ADDRESS-STREET
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para definir a rua do segurado
```

```
**Code**: INSURED-ADDRESS-NUMBER
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para definir o numero da moradia do segurado
```

```
**Code**: INSURED-ADDRESS-COMPLEMENT
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para definir o numero da moradia do segurado
```

```
**Code**: INSURED-ADDRESS-NEIGHBORHOOD
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para definir o bairro do segurado
```

```
**Code**: INSURED-ADDRESS-CITY
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para definir a cidade do segurado
```

```
**Code**: INSURED-ADDRESS-STATE
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para definir o estado do segurado
```

```
**Code**: COMMISSION
**Type**: decimal
* pergunta usada para definir a comissao.
* o valor padrao é 20.00
```

```
**Code**: GRIEVANCE-DISCOUNT
**Type**: decimal
* pergunta usada para definir Agravo/Desconto.
```

```
**Code**: ITEMS
**Type**: array<answer>
Obrigatorio que esteja incluido no array
* esta pergunta em formato de array de answer é usado para enviar as perguntas mais especificas do produto em questao, neste caso bike. Veremos essas perguntas com mais detalhes na proxima parte.
```

<aside>
💡 **Desmistificando o json de request - part 3**

</aside>

> Como explicado mais acima, o campo **items** dentro do **array de answer** tem como finalidade enviar as perguntas mais especificas do produto que esta sendo contado (bike), abaixo voce vera os valores que poderão/deverão estar inclusos nesse array.
> 

```json
{
    "operationCode": "BIKE-MULTIPLE-PERIL",
    "answers": [
        {
            "code": "MODALITY",
            "answer": "BIKE-MULTIPLE-PERIL"
        },
        {
            "code": "ITEMS",
            "answer": [
                {
                    "code": "ITEM-IDENTIFIER",
                    "answer": "af323495-d286-4300-88f3-e911f06c85fe"
                }
            ]
        }
    ]
}
```

```
**Code**: ITEM-IDENTIFIER
**Type**: guid
Obrigatorio que esteja incluido no array
* esta pergunta é usada para definir a identificacao do item que esta sendo cotado, no caso bike.
```

```
**Code**: SERIAL-NUMBER
**Type**: text
Obrigatorio que esteja incluido no array
* esta pergunta é usada para definir o numero de serie da bike em questao.(30 caracteres no maximo)
```

```
**Code**: ITEM-TYPE
**Type**: text
Obrigatorio que esteja incluido no array
* esta pergunta é usada para definir o tipo da bike.
os valores possiveis para esta pergunta sao:
**TRADITIONAL =** bike tradicional
**ELETRIC =** bike eletrica (Elétrica (até 500W))
```

```
**Code**: MANUFACTURE-YEAR
**Type**: integer
Obrigatorio que esteja incluido no array
* esta pergunta é usada para definir o ano de fabricacao da bike.(2017 ou menor não cobrimos)
```

```
**Code**: MODEL
**Type**: text
Obrigatorio que esteja incluido no array
* esta pergunta é usada para definir o modelo da bike
```

```
**Code**: COMPETITIONS
**Type**: boolean
Obrigatorio que esteja incluido no array
* esta pergunta é usada para definir se a bike sera usada para competicoes
```

```
**Code**: ORIGINAL-VALUE
**Type**: decimal
Obrigatorio que esteja incluido no array
* esta pergunta é usada para definir o valor original da bike
```

```
**Code**: VALUE-AGREEMENT
**Type**: boolean
Obrigatorio que esteja incluido no array
* pergunta usada para definir "**Entendimento e concordância de valor aprovado**"
se defida  como true, indica que "**Estou de acordo com o valor aprovado pela Fairfax.**"
```

```
**Code**: NEW
**Type**: boolean
Obrigatorio que esteja incluido no array
* pergunta usada para definir se a bike é nova ou nao
*Considera-se Novo Quando o Segurado é o 1º Proprietário e Que a Data de Emissão da Nota Fiscal Seja de Até 60 Dias da Data Atual
```

```
**Code**: BRAND-NAME
**Type**: text
Obrigatorio que esteja incluido no array
* pergunta usada para definir o nome da marca da bike
```

```
**Code**: FRAME-TYPE
**Type**: text
Obrigatorio que esteja incluido no array
* pergunta usada para definir o tipo de quadro da bike
os valores possiveis para esta pergunta sao:
**CARBON =** carbono
**ALUMINUM =** aluminio
**STEEL=** aço
```

```
**Code**: FRAME-TYPE-AGREEMENT
**Type**: boolean
Obrigatorio que esteja incluido no array
* pergunta usada para definir "**Entendimento e concordância do tipo de quadro**"
se defida  como true, indica que "**Estou ciente e de acordo que o material do quadro da Bicicleta acima indicado está correto. A informação incorreta acarretará perda do direito.**"
```

```
**Code**: CLAIMS
**Type**: text
Obrigatorio que esteja incluido no array
* pergunta usada para definir se ha Sinistro nos últimos 36 meses.
os valores possiveis para esta pergunta sao:
**0 =** nenhum
**1 =** sinistro
**2** **=** sinistros
**3+** = 3 ou mais sinistros

```

```
**Code**: DEDUCTIBLE
**Type**: text
Obrigatorio que esteja incluido no array
* pergunta usada para definir o tipo de frnaquia.
os valores possiveis para esta pergunta sao:
DEFAULT **= padrao**
REDUCED  **= reduzida**
INCREASED **= aumentada**

```

```
**Code**: PART-BIKE-AGREEMENT
**Type**: boolean
Obrigatorio que esteja incluido no array
* pergunta usada para definir "**Entendimento e concordância das peças modificadas**"
se defida  como true, indica que "**Estou ciente e de acordo que as peças modificadas deverão conter Nota Fiscal e/ou Cupom Fiscal, em nome do segurado. A não apresentação acarretará perda de direito.**"
```

```
**Code**: PARTS
**Type**: array<array<answer>>
* campo usado para enviar as partes customizadas da bike, **havera uma secao nesta documentacao explicando mais detalhadamente** 
```

```
**Code**: COVERAGES
**Type**: array<array<answer>>
Obrigatorio que esteja incluido no array
* campo usado para enviar as coberturas, **havera uma secao nesta documentacao explicando mais detalhadamente** 
```

```
**Code**: RENT
**Type**: boolean
Obrigatorio que esteja incluido no array
* pergunta usada para definir se a bike sera usada para locacoes
```

```
**Code**: INVOICE
**Type**: boolean
Obrigatorio que esteja incluido no array
* pergunta usada para definir se a bike possui ou nao nota fiscal
```

```
**Code**: INVOICE-AGREEMENT
**Type**: boolean
Obrigatorio que esteja incluido no array (se INVOICE == TRUE)
* pergunta usada para definir "**Entendimento e concordância de solicitação de nota fiscal**"
se defida  como true, indica que "**Estou ciente e de acordo que a nota fiscal e/ou cupom fiscal da bicicleta em nome do segurado, serão solicitados em caso de sinistro.**"
```

<aside>
💡 **Desmistificando o json de request - part 4.1**

</aside>

> Como explicado mais acima, o campo **parts** dentro do **array de items** tem como finalidade 
enviar as partes customizadas da bike, abaixo você vera os valores que poderão 
estar inclusos nesse array.
> 

```json
{
   "operationCode":"BIKE-MULTIPLE-PERIL",
   "answers":[
      {
         "code":"MODALITY",
         "answer":"BIKE-MULTIPLE-PERIL"
      },
      {
         "code":"ITEMS",
         "answer":[
            {
               "code":"ITEM-IDENTIFIER",
               "answer":"af323495-d286-4300-88f3-e911f06c85fe"
            },
            {
               "code":"PARTS",
               "answer":[
                  [
                     {
                        "code":"PART-TYPE",
                        "answer":"value"
                     },
                     {
                        "code":"PART-BRAND",
                        "answer":"value"
                     },
                     {
                        "code":"PART-MODEL",
                        "answer":"value"
                     },
                     {
                        "code":"PART-VALUE",
                        "answer":0
                     }
                  ],
                  [
                     {
                        "code":"PART-TYPE",
                        "answer":"value"
                     },
                     {
                        "code":"PART-BRAND",
                        "answer":"value"
                     },
                     {
                        "code":"PART-MODEL",
                        "answer":"value"
                     },
                     {
                        "code":"PART-VALUE",
                        "answer":0
                     }
                  ]
               ]
            }
         ]
      }
   ]
}
```

```markdown
Code: PART-TYPE

Type: text
* pergunta usada para definir partes adicionais da bike.
os possiveis valores para esta pergunta são:

**FRONT-DERAILLEUR
REAR-DERAILLEUR
SEATPOST
SEATPOST-BRAND
CLIP-PEDAL
COLOR
HUB
BRAKE
FORK
HANDLEBAR
STEM
PEDAL
CRANKSET
TIRE
FRAME
WHEEL
SADDLE
FRONT-SHIFTER
REAR-SHIFTER**
```

```
**Code**: PART-BRAND
**Type**: text
* pergunta usada para definir a marca da parte.
```

```
**Code**: PART-MODEL
**Type**: text
* pergunta usada para definir o modelo da parte
```

```
**Code**: PART-VALUE
**Type**: decimal
* pergunta usada para definir o valor da parte
```

<aside>
💡 **Desmistificando o json de request - part 4.2**

</aside>

> Como explicado mais acima, o campo **coverages** dentro do **array de items** tem como 
finalidade enviar as coberturas, abaixo voce vera os valores que poderão/deverão estar inclusos nesse array.

É obrigatório o envio de uma das coberturas entre:

	- **DAMAGE-COVERAGE
	- THIEFT COVERAGE**
> 

```json
{
   "operationCode":"BIKE-MULTIPLE-PERIL",
   "answers":[
      {
         "code":"MODALITY",
         "answer":"BIKE-MULTIPLE-PERIL"
      },
      {
         "code":"ITEMS",
         "answer":[
            {
               "code":"ITEM-IDENTIFIER",
               "answer":"af323495-d286-4300-88f3-e911f06c85fe"
            },
            {
               "code":"COVERAGES",
               "answer":[
                  [
                     {
                        "code":"COVERAGE-TYPE",
                        "answer":"DAMAGE-COVERAGE"
                     }
                  ],
                  [
                     {
                        "code":"COVERAGE-TYPE",
                        "answer":"THEFT-COVERAGE"
                     }
                  ],
                  [
                     {
                        "code":"COVERAGE-TYPE",
                        "answer":"CIVIL-LIABILITY-COVERAGE"
                     },
                     {
                        "code":"COVERAGE-LIMIT",
                        "answer":100
                     }
                  ],
                  [
                     {
                        "code":"COVERAGE-TYPE",
                        "answer":"ACCESSORIES-COVERAGE"
                     },
                     {
                        "code":"COVERAGE-LIMIT",
                        "answer":5
                     }
                  ],
                  [
                     {
                        "code":"COVERAGE-TYPE",
                        "answer":"INTERNATIONAL-COVERAGE"
                     }
                  ]
               ]
            }
         ]
      }
   ]
}
```

```
**Code**: COVERAGE-TYPE
**Type**: text
* pergunta usada para definir o tipo de cobertura.
os possiveis valores para esta pergunta são:

**DAMAGE-COVERAGE
THEFT-COVERAGE
CIVIL-LIABILITY-COVERAGE
ACCESSORIES-COVERAGE
ELECTRICAL-DAMAGE-COVERAGE
INTERNATIONAL-COVERAGE**
```

```markdown
**Code**: COVERAGE-LIMIT
**Type**: integer
* pergunta usada para definir o limite de uma cobertura, caso uma delas sejam:
 - ***CIVIL-LIABILITY-COVERAGE
 - ACCESSORIES-COVERAGE***

Os possiveis valores para esta pergunta são:

50 - enviar no mesmo array que contiver CIVIL-LIABILITY-COVERAGE
100 - enviar no mesmo array que contiver CIVIL-LIABILITY-COVERAGE
200 - enviar no mesmo array que contiver CIVIL-LIABILITY-COVERAGE
300 - enviar no mesmo array que contiver CIVIL-LIABILITY-COVERAGE
400 - enviar no mesmo array que contiver CIVIL-LIABILITY-COVERAGE
500 - enviar no mesmo array que contiver CIVIL-LIABILITY-COVERAGE
05 - enviar no mesmo array que contiver ACCESSORIES-COVERAGE
10 - enviar no mesmo array que contiver ACCESSORIES-COVERAGE
```

```json
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
}
```

<aside>
💡 **Exemplo de json de response**

</aside>

```json
{
  "item": {
    "quotationIdentifier": "2aea86d1-a9e5-4220-ab29-68c3fba8483f",
    "status": 0,
    "expiredAt": null,
    "quotationDocumentUrl": null,
    "proposal": null,
    "pricing": [
      {
        "variantIdentifier": "92cc00b4-9ba6-4f50-bf5a-38b76ade9370",
        "underwriting": {
          "approved": true,
          "evaluations": []
        },
        "price": {
          "commission": 150.84,
          "grievanceDiscount": 0,
          "itemValue": 11696.4,
          "netValue": 754.22,
          "interestValue": 0,
          "taxValue": 55.66,
          "totalValue": 809.88,
          "policyLimit": 23977.62,
          "rates": [
            {
              "code": "DAMAGE-COVERAGE",
              "description": "Danos à bike",
              "limit": 11696.4,
              "netValue": 122.85,
              "deductible": {
                "code": "INCREASED",
                "text": "Majorada",
                "description": "10% dos prejuízos indenizáveis com o mínimo de R$ 1.100,00"
              }
            },
            {
              "code": "THEFT-COVERAGE",
              "description": "Roubo e/ou furto qualificado",
              "limit": 11696.4,
              "netValue": 343.99,
              "deductible": {
                "code": "INCREASED",
                "text": "Majorada",
                "description": "10% dos prejuízos indenizáveis com o mínimo de R$ 1.100,00"
              }
            },
            {
              "code": "CIVIL-LIABILITY-COVERAGE",
              "description": "Danos Materiais E/ou Corporais a Terceiros (RC)",
              "limit": 11696.4,
              "netValue": 143.69,
              "deductible": {
                "code": "INCREASED",
                "text": "Majorada",
                "description": "R$ 500,00"
              }
            },
            {
              "code": "ACCESSORIES-COVERAGE",
              "description": "Acessórios",
              "limit": 584.82,
              "netValue": 39.19,
              "deductible": {
                "code": "INCREASED",
                "text": "Majorada",
                "description": "15% dos prejuízos indenizáveis com o mínimo de R$ 300,00"
              }
            },
            {
              "code": "INTERNATIONAL-COVERAGE",
              "description": "Cobertura internacional",
              "limit": 11696.4,
              "netValue": 104.5,
              "deductible": {
                "code": "INCREASED",
                "text": "Majorada",
                "description": "Conforme cobertura a ser acionada"
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
                  "identifier": "ee88a83c-1764-4e28-8272-e27d49d32dc8",
                  "number": 1,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 809.88,
                  "installmentInterest": 0,
                  "installmentTax": 55.66,
                  "dueDates": [
                    "2022-09-22T00:00:00Z"
                  ]
                },
                {
                  "identifier": "572b39db-f139-4dff-96b7-fbb972484b1a",
                  "number": 2,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 404.94,
                  "installmentInterest": 0,
                  "installmentTax": 27.83,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "296a576b-9a49-43af-9408-22850993cf34",
                  "number": 3,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 269.96,
                  "installmentInterest": 0,
                  "installmentTax": 18.55,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "9b341236-7fab-4053-a746-e06cda830af2",
                  "number": 4,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 202.47,
                  "installmentInterest": 0,
                  "installmentTax": 13.92,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
                    "2022-12-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "16074860-0465-4695-9211-19c8ad3b1106",
                  "number": 5,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 161.98,
                  "installmentInterest": 0,
                  "installmentTax": 11.13,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
                    "2022-12-01T12:00:00Z",
                    "2023-01-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "e7abdcd3-67e2-4538-9319-735adca855e3",
                  "number": 6,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 134.98,
                  "installmentInterest": 0,
                  "installmentTax": 9.28,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
                    "2022-12-01T12:00:00Z",
                    "2023-01-01T12:00:00Z",
                    "2023-02-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "a737a7d4-f9b7-4c49-b8f1-e1c9da737204",
                  "number": 7,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 115.7,
                  "installmentInterest": 0,
                  "installmentTax": 7.95,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
                    "2022-12-01T12:00:00Z",
                    "2023-01-01T12:00:00Z",
                    "2023-02-01T12:00:00Z",
                    "2023-03-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "321f86b9-3769-4d63-8639-b4f251519d9f",
                  "number": 8,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 101.24,
                  "installmentInterest": 0,
                  "installmentTax": 6.96,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
                    "2022-12-01T12:00:00Z",
                    "2023-01-01T12:00:00Z",
                    "2023-02-01T12:00:00Z",
                    "2023-03-01T12:00:00Z",
                    "2023-04-01T12:00:00Z"
                  ]
                }
              ]
            },
            {
              "paymentMethod": "Ticket",
              "paymentType": "Ticket",
              "installments": [
                {
                  "identifier": "f8702529-a575-407a-9636-d3703eb50937",
                  "number": 1,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 809.88,
                  "installmentInterest": 0,
                  "installmentTax": 55.66,
                  "dueDates": [
                    "2022-09-22T00:00:00Z"
                  ]
                },
                {
                  "identifier": "db3582c3-3465-436e-a336-e76b7392c632",
                  "number": 2,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 404.94,
                  "installmentInterest": 0,
                  "installmentTax": 27.83,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "f671ba0a-6b6a-4aa2-a9d5-e2267d7a7672",
                  "number": 3,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 269.96,
                  "installmentInterest": 0,
                  "installmentTax": 18.55,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "a8d655d6-7218-4f11-ac19-f717d5df3a78",
                  "number": 4,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 202.47,
                  "installmentInterest": 0,
                  "installmentTax": 13.92,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
                    "2022-12-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "2cf29028-0328-421e-8075-2fc20e4be78d",
                  "number": 5,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 161.98,
                  "installmentInterest": 0,
                  "installmentTax": 11.13,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
                    "2022-12-01T12:00:00Z",
                    "2023-01-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "b829ce1c-44bf-4ec4-9dcc-fc7ccb664acd",
                  "number": 6,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 134.98,
                  "installmentInterest": 0,
                  "installmentTax": 9.28,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
                    "2022-12-01T12:00:00Z",
                    "2023-01-01T12:00:00Z",
                    "2023-02-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "ff8151ef-25b7-4b77-9d84-d81564637117",
                  "number": 7,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 115.7,
                  "installmentInterest": 0,
                  "installmentTax": 7.95,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
                    "2022-12-01T12:00:00Z",
                    "2023-01-01T12:00:00Z",
                    "2023-02-01T12:00:00Z",
                    "2023-03-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "abf68d10-613b-4c85-82cb-e07e58df476c",
                  "number": 8,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 101.24,
                  "installmentInterest": 0,
                  "installmentTax": 6.96,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
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
  "executed": "2022-09-15T15:04:10.4663707Z",
  "errors": null
}
```