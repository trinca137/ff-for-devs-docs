<h3>💡Desmistificando o json de request - part 1</h3>

```json
{
	"operationCode":"BIKE-MULTIPLE-PERIL-PARTNER",
	"answers":[],
}
```

> **Field**: OperationCode </br>
> **Type**: ```text``` </br>
> <text>❗campo obrigatorio</text> </br>
> * campo usado para definir qual produto esta sendo cotado, neste caso o produto é bike, representado pelo operation code "BIKE-MULTIPLE-PERIL-PARTNER".

---------------------------------------------------------

> **Field**: answers </br>
> **Type**: ```array<answer>``` </br>
> campo obrigatorio </br>
> * campo usado para enviar as perguntas mais gerais de uma cotacao, um exemplo de pergunta seria se a pessoa que esta realizando a operacao é juridica ou fisica.
veremos mais detalhes sobre essas perguntas mais abaixo na documentacao.
Abaixo, podemos ver a modelagem de answer.

<h5>Answer model</h5>

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

<aside>
💡 **Desmistificando o json de request - part 2**

</aside>

> Como explicado mais acima, o campo **answers** tem como finalidade enviar as perguntas referentes a cotação, abaixo voce vera os valores que poderão/deverão estar inclusos nesse array.
> 

```json
{
    "operationCode": "BIKE-MULTIPLE-PERIL-PARTNER",
    "answers": [
        {
            "code": "MODALITY",
            "answer": "BIKE-MULTIPLE-PERIL"
        }
    ]
}
```

```
**Code**: MODALITY
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para definir qual produto esta sendo cotado, neste caso o produto é bike, representado pelo operation code "BIKE-MULTIPLE-PERIL" 
```

```
**Code**: PERSON-TYPE
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para saber que a cotacao esta sendo feita por uma pessoa fisica ou juridica.
os valores possiveis para esta pergunta sao:
**NATURAL =** significa que a pessoa em questao é fisica
**LEGAL =** significa que a pessoa em questao é juridica
```

```
**Code**: START-VIGENCY-DATE
**Type**: date
Obrigatorio que esteja incluido no array 
* pergunta usada para definir o inicio da vigencia do seguro.
```

```
**Code**: VIGENCY-DURATION
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


>**Code**: INSURED-BIRTH-DATE <br>
>❗ Obrigatorio que esteja incluido no array (quando for para o endpoint de PROPOSAL) <br>
>**Type**: ```date``` <br>
>Pergunta usada para definir a data de nascimento do segurado <br>

--------------------------------------------------------------------------


>**Code**: PAYMENT-METHOD <br>
>**Type**: ```text``` <br>
>❗ Obrigatorio que esteja incluido no array (quando for para o endpoint de PROPOSAL) <br>
>Pergunta usada para definir o metodo de pagamento <br>
>os possiveis valores para esta pergunta são: <br>
>**CREDIT-CARD** <br>

--------------------------------------------------------------------------


>**Code**: DUE-DAY <br>
>**Type**: ```integer``` <br>
>❗ Obrigatorio que esteja incluido no array  (apenas quando o PAYMENT-METHOD for TICKET)  <br>
>❗ Obrigatorio que esteja incluido no array  (quando for para o endpoint de PROPOSAL) <br>
>Pergunta usada para definir a data de vencimento <br>

---------------------------------------------------------------------------



>**Code**: PAYMENT-INSTALLMENT-IDENTIFIER <br>
>**Type**: ```guid``` <br>
>❗ Obrigatorio que esteja incluido no array (quando for para o endpoint de PROPOSAL) <br>
>O guid que sera enviando nesse campo, é retornado no array de installments, no retorno do endpoint de criar cotacao <br>

------------------------------------------------------------------------------


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
    "operationCode": "BIKE-MULTIPLE-PERIL-PARTNER",
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
   "operationCode":"BIKE-MULTIPLE-PERIL-PARTNER",
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
   "operationCode":"BIKE-MULTIPLE-PERIL-PARTNER",
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

**Code**: COVERAGE-TYPE
**Type**: text
<p> pergunta usada para definir o tipo de cobertura.
os possiveis valores para esta pergunta são: </p>

> **DAMAGE-COVERAGE <br>
> THEFT-COVERAGE <br>
> CIVIL-LIABILITY-COVERAGE <br>
> ACCESSORIES-COVERAGE <br>
> ELECTRICAL-DAMAGE-COVERAGE <br>
> INTERNATIONAL-COVERAGE** <br>
<p>Teste</p>

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