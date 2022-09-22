# Create Quotation

# Qual a ordem do fluxo ?

<aside>
1️⃣ **Primeiro deve-se chamar o endpoint para se criar uma cotação.**

</aside>

<aside>
2️⃣ **Em seguida deve-se chamar o endpoint de proposal com o id da cotação criada.**

</aside>

<aside>
3️⃣ **Para finalizar o fluxo, é necessário prosseguir para o endpoint de checkout.**

</aside>

<aside>
💡 **Endpoint usado para se criar uma cotação**

</aside>

```
**METHOD** POST
**Endpoint**: https://azuh1-br-fairfax-gateway.azure-api.net/partner/api/v1/quotation
**Content**-Type: application/x-www-form-urlencoded
**Ocp-Apim-Subscription-Key**: your apiKey
```

<aside>
💡 **Exemplo de json de request**

</aside>

```json
{
    "operationCode": "INSURANCE-BROKER-CIVIL-LIABILITY",
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
            "answer": "samuel emidio"
        },
        {
            "code": "INSURED-EMAIL",
            "answer": "samuel.lucas.emidio@gmail.com"
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
            "answer": "4657"
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
        }
    ]
}
```

<aside>
💡 **Desmistificando o json de request - part 1**

</aside>

```json
{
		"operationCode":"INSURANCE-BROKER-CIVIL-LIABILITY",
		"answers":[],
}
```

```
**Field**: **OperationCode**
**Type**: text
campo obrigatorio
* campo usado para definir qual produto esta sendo cotado, neste caso o produto é corretor, representado pelo operation code "INSURANCE-BROKER-CIVIL-LIABILITY".
```

```
**Field**: answers
**Type**: array<answer>
campo obrigatorio
* campo usado para enviar as perguntas mais gerais de uma cotacao, um exemplo de pergunta seria se a pessoa que esta realizando a operacao é juridica ou fisica.
veremos mais detalhes sobre essas perguntas mais abaixo na documentacao.
Abaixo, podemos ver a modelagem de answer.

```

## Answer model

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
    "operationCode": "INSURANCE-BROKER-CIVIL-LIABILITY",
    "answers": [
        {
            "code": "MODALITY",
            "answer": "INSURANCE-BROKER-CIVIL-LIABILITY"
        }
    ]
}
```

```
**Code**: MODALITY
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para definir qual modalidade esta sendo cotada, neste caso a modalidade é corretor, representado pelo modality code "INSURANCE-BROKER-CIVIL-LIABILITY" 
```

```
**Code**: PRODUCT
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para definir o produto, neste caso o produto, neste caso, representado pelo product code "PROFESSIONAL-CIVIL-LIABILITY" 
```

```
**Code**: CURRENCY
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para definir Moeda do Seguro
os valores possiveis para esta pergunta sao:
**BRL**
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
**Code**: PROFESSIONAL-REGISTER
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para definir o rigistro do profissional
```

```
**Code**: REGISTER-NUMBER-TYPE
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para definir o tipo de susep
os possiveis valores para esta pergunta são:
**FULL =** Susep Plena
**BASIC =** Susepinha
```

```
**Code**: PROFESSION
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para definir Profissão
os possiveis valores para esta pergunta são:
**INSURANCE-BROKER**
```

```
**Code**: CATEGORIES
**Type**: array<string>
Obrigatorio que esteja incluido no array 
* pergunta usada para definir as especialidades Odontológicas, pode-se enviar mais de uma resposta dentro desse array de string, sendo elas:

**CAR** = Automóvel (disponivel SE REGISTER-NUMBER-TYPE for FULL)

**AERONAUTICAL** = Aeronáutico (disponivel SE REGISTER-NUMBER-TYPE for FULL)

**HEALTH-INSURANCE** = Planos de Saúde 

**GUARANTEE** = Garantia (disponivel SE REGISTER-NUMBER-TYPE for FULL)

**TRANSPORT** = Transportes (disponivel SE REGISTER-NUMBER-TYPE for FULL)

**ENGINEERING-RISKS** = Riscos de Engenharia (disponivel SE REGISTER-NUMBER-TYPE for FULL)

**GENERAL-PROFESSIONAL-CIVIL-LIABILITY** = RC Geral e RC Profissional (disponivel SE REGISTER-NUMBER-TYPE for FULL)

**BENEFITS-HEALTH-LIFE-PENSION** = Seguro Saúde, Seguro de Vida e/ou Previdência Privada

**CONSORTIUM** = Consórcio (disponivel SE REGISTER-NUMBER-TYPE for FULL)

**OTHERS** = Demais seguros não listados (disponivel SE REGISTER-NUMBER-TYPE for FULL)
```

```
**Code**: DIGITAL-CERTIFICATION-COVERAGE
**Type**: boolean
Obrigatorio que esteja incluido no array (se o PERSON-TYPE for LEGAL)
* pergunta usada para definir se corretora é Certificadora Digital e deseja cobertura para esse serviço?
```

```
**Code**: RETROACTIVITY
**Type**: integer
* pergunta usada para definir a retroatividade.
os possiveis valores para esta pergunta são:
**0** = Sem retroatividade
**1** = 1 ano
**2** = 2 anos
**3** = 3 anos
**4** = 4 anos
**5** = 5 anos
```

```
**Code**: RETROACTIVITY-DATE
**Type**: date
Obrigatorio que esteja incluido no array (se o RETROACTIVITY for maior que zero)
* pergunta usada para definir a Data de Retroatividade.
```

```
**Code**: RETROACTIVITY-AGREEMENT
**Type**: boolean
Obrigatorio que esteja incluido no array
* pergunta usada para definir "Entendimento e concordância de retroatividade"
se defida  como true, indica que "**Estou ciente e de acordo que a confirmação da data de retroatividade ocorrerá apenas num eventual sinistro, sendo obrigatório apresentar as apólices anteriores para comprovação. A apólice anterior não ode ter sido cancelada ou ter tido interrupção de vigência.**"
```

```
**Code**: VIGENCY-RETROACTIVITY-AGREEMENT
**Type**: boolean 
* pergunta usada para definir "**Entendimento e concordância de vigência retroativa**"
se defida  como true, indica que "**Estou ciente e de acordo que não possuo conhecimento de qualquer fato que possa acarretar uma reclamação futura entre o início de vigência e a data de emissão da apólice**"
```

```
**Code**: REVENUES
**Type**: text
Obrigatorio que esteja incluido no array (se o PERSON-TYPE for LEGAL)
* pergunta usada para definir o Faturamento nos últimos 12 meses.
os possiveis valores para esta pergunta são:
0.00-100000.00 ****= Entre R$ 0,00 e R$ 100.000,00
100000.01-300000.00 ****= Entre R$ 100.000,01 e R$ 300.000,00
300000.01-500000.00 ****= Entre R$ 300.000,01 e R$ 500.000,00
500000.01-1000000.00 ****= Entre R$ 500.000,01 e R$ 1.000.000,00
1000000.01-1500000.00 ****= Entre R$ 1.000.000,01 e R$ 1.500.000,00
1500000.01-2000000.00 ****= Entre R$ 1.500.000,01 e R$ 2.000.000,00
2000000.01-3000000.00 ****= Entre R$ 2.000.000,01 e R$ 3.000.000,00
3000000.01-5000000.00 ****= Entre R$ 3.000.000,01 e R$ 5.000.000,00
5000000.01-7500000.00 ****= Entre R$ 5.000.000,01 e R$ 7.500.000,00
7500000.01-10000000.00 ****= Entre R$ 7.500.000,01 e R$ 10.000.000,00
10000000.01+ ****= Acima de R$ 10.000.000,00
```

```
**Code**: CLAIMS
**Type**: text
Obrigatorio que esteja incluido no array
* pergunta usada para definir se ha Sinistro nos últimos 24 meses.
os valores possiveis para esta pergunta sao:
**0 =** nenhum
**1 =** 1 reclamação
**2** **=** 2 reclamação
**3+** = 3 ou mais
```

```
**Code**: CLAIM-EXPECTATION
**Type**: boolean
Obrigatorio que esteja incluido no array
* pergunta usada para definir se ha Expectativas de Sinistro
```

```
**Code**: CLAIM-EXPECTATION-THIRD-PARTY
**Type**: text
Obrigatorio que esteja incluido no array (se CLAIM-EXPECTATION for TRUE)
* pergunta usada para definir Possíveis terceiros reclamantes de expectativas de sinistro
```

```
**Code**: CLAIM-EXPECTATION-AGREEMENT
**Type**: boolean 
* pergunta usada para definir "**Entendimento e concordância de expectativas de sinistro**"
se defida  como true, indica que "**Entendido e acordado que não haverá cobertura securitária para qualquer tipo de fato já conhecido pelo segurado.**"
```

```
**Code**: TERRITORIALITY
**Type**: text
Obrigatorio que esteja incluido no array
* pergunta usada para definir a Territorialidade
os valores possiveis para esta pergunta sao:
**BR =** Brasil
```

```
**Code**: SCOPE
**Type**: text
Obrigatorio que esteja incluido no array
* pergunta usada para definir o Âmbito
os valores possiveis para esta pergunta sao:
**NATIONAL =** nacional
```

```
**Code**: LIMIT-DEDUCTIBLE
**Type**: array<array<answer>>
Obrigatorio que esteja incluido no array
* Campo para definir Limite e Franquia, veremos mais detalhadamente nas proximas partes.
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

<aside>
💡 **Desmistificando o json de request - part 3**

</aside>

> Como explicado mais acima, o campo **LIMIT-DEDUCTIBLE** dentro do **array de answer** tem como finalidade enviar as perguntas  referentes aos limites e franquias, abaixo voce vera os valores que poderão/deverão estar inclusos nesse array.
> 

```json
{
   "operationCode":"DENTIST-CIVIL-LIABILITY",
   "answers":[
      {
         "code":"MODALITY",
         "answer":"DENTIST-CIVIL-LIABILITY"
      },
      {
         "code":"LIMIT-DEDUCTIBLE",
         "answer":[
            [
               {
                  "code":"LIMIT",
                  "answer":30000
               },
               {
                  "code":"DEDUCTIBLE",
                  "answer":"DEFAULT"
               },
               {
                  "code":"VARIANT-IDENTIFIER",
                  "answer":"17a9aad2-1d5d-49ea-8270-04feb6272394"
               }
            ]
         ]
      }
   ]
}
```

```
**Code**: VARIANT-IDENTIFIER
**Type**: guid
Obrigatorio que esteja incluido no array
* esta pergunta é usada para definir o Identificador da Variante.
```

```
**Code**: LIMIT
**Type**: decimal
Obrigatorio que esteja incluido no array
* os valores possiveis para esta pergunta sao:
**30000.0m** **=** R$ 30.000
**50000.0** **=** R$ 50.000
**100000.0 = R$ 100.000**
**150000.0 = R$ 150.000**
**200000.0 = R$ 200.000**
**250000.0 = R$ 250.000**
**300000.0 = R$ 300.000**
**400000.0 = R$ 400.000**
**500000.0 = R$ 500.000**
**600000.0 = R$ 600.000**
**700000.0 = R$ 700.000**
**800000.0 = R$ 800.000**
**900000.0 = R$ 900.000**
**1000000.0 = R$ 1.000.000**
```

```
**Code**: DEDUCTIBLE
**Type**: text
Obrigatorio que esteja incluido no array
* esta pergunta é usada para definir o tipo da Franquia.
os valores possiveis para esta pergunta sao:
**DEFAULT
INCREASED**
**REDUCED

*dependendo do tipo de categoria definido no campo CLASSIFICATION, o calculo acontecera de manera diferente, abaixo vc pode ver detalhadamente:**

Se for **AERONAUTICAL (PERSON-TYPE = NATURAL):
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00

Se for **AERONAUTICAL (PERSON-TYPE = LEGAL):
DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
**INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00

Se for **CAR (PERSON-TYPE = NATURAL):
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00

Se for **CAR (PERSON-TYPE = LEGAL):
DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
**INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00

Se for **GUARANTEE (PERSON-TYPE = NATURAL):
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00

Se for **GUARANTEE (PERSON-TYPE = LEGAL):
DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
**INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00

Se for **GENERAL-PROFESSIONAL-CIVIL-LIABILITY (PERSON-TYPE = NATURAL):
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00

Se for **GENERAL-PROFESSIONAL-CIVIL-LIABILITY (PERSON-TYPE = LEGAL):
DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
**INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00

Se for **ENGINEERING-RISKS (PERSON-TYPE = NATURAL):
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00

Se for **ENGINEERING-RISKS (PERSON-TYPE = LEGAL):
DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
**INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00

Se for **TRANSPORT (PERSON-TYPE = NATURAL):
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00

Se for **TRANSPORT (PERSON-TYPE = LEGAL):
DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
**INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00

Se for **CONSORTIUM (PERSON-TYPE = NATURAL):
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00

Se for **CONSORTIUM (PERSON-TYPE = LEGAL):
DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
**INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00

Se for **BENEFITS-HEALTH-LIFE-PENSION (PERSON-TYPE = NATURAL):
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00

Se for **BENEFITS-HEALTH-LIFE-PENSION (PERSON-TYPE = LEGAL):
DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
**INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00

Se for **HEALTH-INSURANCE (PERSON-TYPE = NATURAL):
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00

Se for **HEALTH-INSURANCE (PERSON-TYPE = LEGAL):
DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
**INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00

Se for **OTHERS (PERSON-TYPE = NATURAL):
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00

Se for **OTHERS (PERSON-TYPE = LEGAL):
DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
**INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
**REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00

```

<aside>
💡 **Exemplo de json de response**

</aside>

```json
{
    "item": {
        "quotationIdentifier": "2942faa1-09b8-4345-9bdd-6764c4f1ad35",
        "status": "Draft",
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
                                        "2022-10-01T12:00:00Z"
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
                                        "2022-10-01T12:00:00Z"
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
    "executed": "2022-09-21T12:33:30.801451Z"
}
```