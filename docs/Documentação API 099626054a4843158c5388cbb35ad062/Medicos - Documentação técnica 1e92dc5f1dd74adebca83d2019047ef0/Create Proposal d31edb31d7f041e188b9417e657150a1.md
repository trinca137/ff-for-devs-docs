# Create Proposal

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
💡 **Endpoint usado para se criar uma proposta**

</aside>

```
**METHOD** POST
**Endpoint**: https://azuh1-br-fairfax-gateway.azure-api.net/partner/api/v1/quotation/proposal
**Content**-Type: application/x-www-form-urlencoded
**Ocp-Apim-Subscription-Key**: your apiKey
```

<aside>
💡 **Exemplo de json de request**

</aside>

```json
{
	 
	 "identifier":"7dfac165-a63e-40d8-b6bb-23431e057982",
   "operationCode":"MEDICAL-CIVIL-LIABILITY",
   "answers":[
      {
         "code":"MODALITY",
         "answer":"MEDICAL-CIVIL-LIABILITY"
      },
      {
         "code":"PRODUCT"
      },
      {
         "code":"CURRENCY"
      },
      {
         "code":"PERSON-TYPE",
         "answer":"NATURAL"
      },
      {
         "code":"START-VIGENCY-DATE",
         "answer":"2022-09-09T03:00:00.000Z"
      },
      {
         "code":"VIGENCY-DURATION"
      },
      {
         "code":"CONGENER",
         "answer":"NEW"
      },
      {
         "code":"INSURED-NAME",
         "answer":"samuel emidio"
      },
      {
         "code":"INSURED-EMAIL",
         "answer":"e@test.com"
      },
      {
         "code":"IDENTITY",
         "answer":"462.564.658-81"
      },
      {
         "code":"GENDER"
      },
      {
         "code":"INSURED-CELLPHONE",
         "answer":"(12) 99644.0332"
      },
      {
         "code":"INSURED-ADDRESS-ZIPCODE",
         "answer":"12422-320"
      },
      {
         "code":"INSURED-ADDRESS-STREET",
         "answer":"Rua Antônio Lopes Pereira"
      },
      {
         "code":"INSURED-ADDRESS-NUMBER",
         "answer":"998"
      },
      {
         "code":"INSURED-ADDRESS-COMPLEMENT",
         "answer":""
      },
      {
         "code":"INSURED-ADDRESS-NEIGHBORHOOD",
         "answer":"Residencial Campos Maia"
      },
      {
         "code":"INSURED-ADDRESS-CITY",
         "answer":"Pindamonhangaba"
      },
      {
         "code":"INSURED-ADDRESS-STATE",
         "answer":"SP"
      },
      {
         "code":"PROFESSIONAL-REGISTER",
         "answer":"568568567"
      },
      {
         "code":"PROFESSION"
      },
      {
         "code":"CATEGORIES",
         "answer":["OBSTETRICIAN"]
      },
      {
         "code":"RESIDENT",
         "answer":true
      },
      {
         "code":"PROCEDURES-ACTIVITIES",
         "answer":[
            "AESTHETIC-PROCEDURES",
            "ENDOSCOPY-COLONOSCOPY",
            "RADIOTHERAPY-CHEMOTHERAPY-IMMUNOTHERAPY",
            "AESTHETIC-PROCEDURES-MEDICAL-SPECIALTY"
         ]
      },
      {
         "code":"RETROACTIVITY",
         "answer":0
      },
      {
         "code":"RETROACTIVITY-DATE",
         "answer":null
      },
      {
         "code":"RETROACTIVITY-AGREEMENT"
      },
      {
         "code":"VIGENCY-RETROACTIVITY-AGREEMENT"
      },
      {
         "code":"CLAIMS",
         "answer":"0"
      },
      {
         "code":"CLAIM-EXPECTATION",
         "answer":false
      },
      {
         "code":"CLAIM-EXPECTATION-THIRD-PARTY"
      },
      {
         "code":"CLAIM-EXPECTATION-AGREEMENT"
      },
      {
         "code":"TERRITORIALITY"
      },
      {
         "code":"SCOPE"
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
      },
      {
         "code":"COMMISSION",
         "answer":20
      },
      {
         "code":"GRIEVANCE-DISCOUNT",
         "answer":0
      },
			{
      "code": "INSURED-BIRTH-DATE",
			"answer":"1990-09-09T03:00:00.000Z"
	    },
	    {
	      "code": "DUE-DAY",
				"answer":7
	    },
	    {
	      "code": "PAYMENT-INSTALLMENT-IDENTIFIER",
	      "answer": "3e9a5381-5d53-4a18-b34b-24cee545e042"
	    },
	    {
	      "code": "PAYMENT-METHOD",
				"answer":"CREDIT-CARD"
	    }    
   ]
}
```

<aside>
💡 **Desmistificando o json de request - part 1**

</aside>

```json
{
    
		"identifier":"7dfac165-a63e-40d8-b6bb-23431e057982",
		"operationCode":"MEDICAL-CIVIL-LIABILITY",
		"answers":[],
}
```

```
**Field**: **Identifier**
**Type**: guid
campo obrigatorio
* campo usado para definir qual a cotacao sera enviada para proposta.
```

```
**Field**: **OperationCode**
**Type**: text
campo obrigatorio
* campo usado para definir qual produto esta sendo cotado, neste caso o produto é medicos, representado pelo operation code "MEDICAL-CIVIL-LIABILITY".
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
		"identifier":"7dfac165-a63e-40d8-b6bb-23431e057982",
    "operationCode": "MEDICAL-CIVIL-LIABILITY",
    "answers": [
        {
            "code": "MODALITY",
            "answer": "MEDICAL-CIVIL-LIABILITY"
        }
    ]
}
```

```
**Code**: MODALITY
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para definir qual modalidade esta sendo cotada, neste caso a modalidade é medicos, representado pelo modality code "MEDICAL-CIVIL-LIABILITY" 
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
**Code**: PROFESSION
**Type**: text
Obrigatorio que esteja incluido no array 
* pergunta usada para definir Profissão
os possiveis valores para esta pergunta são:
**DOCTOR**
```

```
**Code**: CATEGORIES
**Type**: array<string>
Obrigatorio que esteja incluido no array 
* pergunta usada para definir a especialidade medica,pode-se enviar mais de uma resposta dentro desse array de string (exceto se o PERSON-TYPE for NATURAL), sendo elas:

**NO-SURGERY** = Médico sem Cirurgia e Medicina de Urgência e Emergência (disponivel SE PERSON-TYPE for NATURAL)

**SURGERY-EXCEPT-PLASTIC** = Médico com Cirurgia (exceto plástico), Anestesiologistas (disponivel SE PERSON-TYPE for NATURAL)

**OBSTETRICIAN** = Obstetra (disponivel SE PERSON-TYPE for NATURAL)

**PLASTIC-SURGERY** = Cirurgião (ã) Plástico (a) (disponivel SE PERSON-TYPE for NATURAL)

**CLINIC-WITHOUT-SURGERY** = Clinicas (outras, sem cirurgia) (disponivel SE PERSON-TYPE for LEGAL)

**PATIENT-TRANSPORT** = Transporte de Pacientes (disponivel SE PERSON-TYPE for LEGAL)

**HOME-CARE** = Home care (disponivel SE PERSON-TYPE for LEGAL)

**SURGERY-CLINIC-EXCEPT-PLASTIC** = Clínica de Cirurgia e/ou Anestesiologia, Exceto Plástica (disponivel SE PERSON-TYPE for igual a LEGAL)

**CLINICAL-LABORATORY** = Laboratório de Análises Clínicas (disponivel SE PERSON-TYPE for   LEGAL)

**BLOOD-BANK** = Bancos de Sangue (disponivel SE PERSON-TYPE for LEGAL)

**CLINICAL-OBSTETRICS** = Clínica com Obstetrícia (disponivel SE PERSON-TYPE for LEGAL)

**HOSPITAL** = Hospitais (disponivel SE PERSON-TYPE for LEGAL)

**PLASTIC-SURGERY-CLINIC** = Clinica de Cirurgia Plástica (disponivel SE PERSON-TYPE for    LEGAL)

**CLINICAL-MULTIDISCIPLINARY** = Clínica Multidisciplinar (disponivel SE PERSON-TYPE for    LEGAL)
```

```
**Code**: RESIDENT
**Type**: boolean
Obrigatorio que esteja incluido no array (se o PERSON-TYPE for NATURAL ou se CATEGORIES for diferente de PLASTIC-SURGERY)
* pergunta usada para definir se o profissional é resident ou nao.
```

```
**Code**: PROCEDURES-ACTIVITIES
**Type**: array<string>
* Procedimentos e/ou Atividades. pode-se enviar mais de uma resposta dentro desse array de string, sendo elas:
**AESTHETIC-PROCEDURES** = Procedimentos Estéticos Minimamente Invasivos
**ENDOSCOPY-COLONOSCOPY** = Endoscopia e/ou Colonoscopia
**RADIOTHERAPY-CHEMOTHERAPY-IMMUNOTHERAPY** = Radioterapia e/ou Quimioterapia e/ou Imunoterapia
**AESTHETIC-PROCEDURES-MEDICAL-SPECIALTY** = Procedimentos Estéticos relacionados à Especialidade Médica
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

```
**Code**: INSURED-BIRTH-DATE
Obrigatorio que esteja incluido no array
**Type**: date
* pergunta usada para definir a data de nascimento do segurado
```

```
**Code**: PAYMENT-METHOD
**Type**: text
Obrigatorio que esteja incluido no array
* pergunta usada para definir o metodo de pagamento.
os possiveis valores para esta pergunta são:
**CREDIT-CARD**
```

```
**Code**: DUE-DAY
**Type**: integer
Obrigatorio que esteja incluido no array
* pergunta usada para definir a data de vencimento
```

```
**Code**: PAYMENT-INSTALLMENT-IDENTIFIER
**Type**: guid
Obrigatorio que esteja incluido no array
* O guid que sera enviando nesse campo, é retornado no array de installments, no retorno do endpoint de criar cotacao
```

<aside>
💡 **Desmistificando o json de request - part 3**

</aside>

> Como explicado mais acima, o campo **LIMIT-DEDUCTIBLE** dentro do **array de answer** tem como finalidade enviar as perguntas  referentes aos limites e franquias, abaixo voce vera os valores que poderão/deverão estar inclusos nesse array.
> 

```json
{
	"identifier":"7dfac165-a63e-40d8-b6bb-23431e057982",
   "operationCode":"MEDICAL-CIVIL-LIABILITY",
   "answers":[
      {
         "code":"MODALITY",
         "answer":"MEDICAL-CIVIL-LIABILITY"
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
**REDUCED**
**MINIMUM

*dependendo do tipo de categoria definido no campo CLASSIFICATION, o calculo acontecera de manera diferente, abaixo vc pode ver detalhadamente:**

Se for **NO-SURGERY:
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,00
**REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00
**MINIMUM =** Mínima - Sem Franquia

Se for **SURGERY-EXCEPT-PLASTIC:
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,00
**REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00
**MINIMUM =** Mínima - Sem Franquia

Se for **OBSTETRICIAN:
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,00
**REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 500,00
**MINIMUM =** Mínima - 5% dos prejuízos indenizáveis com o mínimo de R$ 200,00

Se for **PLASTIC-SURGERY:
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,000
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 10.000,00
**REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00
**MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00

Se for **PLASTIC-SURGERY-CLINIC:
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 15.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 20.000,00
**REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 10.000,00
**MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 7.500,00

Se for **CLINICAL-LABORATORY:
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 7.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 9.000,00
**REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,00
**MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.000,00

Se for **HOME-CARE:
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.500,00
**REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00
**MINIMUM =** Mínima - Sem Franquia

Se for **HOSPITAL:
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 15.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 20.000,00
**REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 10.000,00
**MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 7.500,00

Se for **PATIENT-TRANSPORT:
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.500,00
**REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00
**MINIMUM =** Mínima - Sem Franquia

Se for **CLINIC-WITHOUT-SURGERY:
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.500,00
**REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 500,00
**MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 400,00

Se for **BLOOD-BANK:
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 15.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 20.000,00
**REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 10.000,00
**MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 7.500,00

Se for **SURGERY-CLINIC-EXCEPT-PLASTIC:
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.500,00
**REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00
**MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00

Se for **CLINICAL-OBSTETRICS:
DEFAULT =** Padrão - 15% dos prejuízos indenizáveis com o mínimo de R$ 500,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.500,00
**REDUCED =** Reduzida - 15% dos prejuízos indenizáveis com o mínimo de R$ 1.500,00
**MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00

Se for **CLINICAL-MULTIDISCIPLINARY:
DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00
**INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.500,00
**REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.500,00
**MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 800,00
****
```

<aside>
💡 **Exemplo de json de response**

</aside>

```json
{
   "item":{
      "quotationIdentifier":"7dfac165-a63e-40d8-b6bb-23431e057982",
      "status":0,
      "expiredAt":null,
      "quotationDocumentUrl":null,
      "proposal": {
	      "number": "89678023460002",
	      "date": "0001-01-01T00:00:00Z"
	    },
      "pricing":[
         {
            "variantIdentifier":"17a9aad2-1d5d-49ea-8270-04feb6272394",
            "underwriting":{
               "approved":true,
               "evaluations":[
                  
               ]
            },
            "price":{
               "commission":222.86,
               "grievanceDiscount":0.0,
               "netValue":1114.29,
               "interestValue":0.0,
               "taxValue":82.23,
               "totalValue":1196.52
            },
            "payment":{
               "financialType":"Charge",
               "paymentOptions":[
                  {
                     "paymentMethod":"All",
                     "paymentType":"CreditCard",
                     "installments":[
                        {
                           "identifier":"4628a4ec-3368-44df-8919-163bab1c0ecd",
                           "number":1,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":1196.52,
                           "installmentInterest":0.0,
                           "installmentTax":82.23,
                           "dueDates":[
                              "2022-09-12T00:00:00Z"
                           ]
                        },
                        {
                           "identifier":"d33cc32b-dbbb-48f5-ac7f-34ddd1c065d8",
                           "number":2,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":598.26,
                           "installmentInterest":0.0,
                           "installmentTax":41.12,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z"
                           ]
                        },
                        {
                           "identifier":"e46be589-048f-4a1e-b815-cbc947221c18",
                           "number":3,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":398.84,
                           "installmentInterest":0.0,
                           "installmentTax":27.41,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z",
                              "2022-11-07T12:00:00Z"
                           ]
                        },
                        {
                           "identifier":"d978c2af-3499-4f35-96ad-9ba2c0321d67",
                           "number":4,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":299.13,
                           "installmentInterest":0.0,
                           "installmentTax":20.56,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z",
                              "2022-11-07T12:00:00Z",
                              "2022-12-07T12:00:00Z"
                           ]
                        },
                        {
                           "identifier":"49f6380c-a8c1-410a-825e-01b925ae20e6",
                           "number":5,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":239.3,
                           "installmentInterest":0.0,
                           "installmentTax":16.45,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z",
                              "2022-11-07T12:00:00Z",
                              "2022-12-07T12:00:00Z",
                              "2023-01-07T12:00:00Z"
                           ]
                        },
                        {
                           "identifier":"1f178c05-1006-4c75-9b56-a867a859df2b",
                           "number":6,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":199.42,
                           "installmentInterest":0.0,
                           "installmentTax":13.7,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z",
                              "2022-11-07T12:00:00Z",
                              "2022-12-07T12:00:00Z",
                              "2023-01-07T12:00:00Z",
                              "2023-02-07T12:00:00Z"
                           ]
                        },
                        {
                           "identifier":"689b51ed-0e01-4c0f-b837-c66662a05952",
                           "number":7,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":170.93,
                           "installmentInterest":0.0,
                           "installmentTax":11.75,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z",
                              "2022-11-07T12:00:00Z",
                              "2022-12-07T12:00:00Z",
                              "2023-01-07T12:00:00Z",
                              "2023-02-07T12:00:00Z",
                              "2023-03-07T12:00:00Z"
                           ]
                        },
                        {
                           "identifier":"4aa357ef-39ca-4a7e-8c1f-94964943d47e",
                           "number":8,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":149.56,
                           "installmentInterest":0.0,
                           "installmentTax":10.28,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z",
                              "2022-11-07T12:00:00Z",
                              "2022-12-07T12:00:00Z",
                              "2023-01-07T12:00:00Z",
                              "2023-02-07T12:00:00Z",
                              "2023-03-07T12:00:00Z",
                              "2023-04-07T12:00:00Z"
                           ]
                        },
                        {
                           "identifier":"ccb52162-0a26-4f2a-943b-3411fbec825f",
                           "number":9,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":132.95,
                           "installmentInterest":0.0,
                           "installmentTax":9.14,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z",
                              "2022-11-07T12:00:00Z",
                              "2022-12-07T12:00:00Z",
                              "2023-01-07T12:00:00Z",
                              "2023-02-07T12:00:00Z",
                              "2023-03-07T12:00:00Z",
                              "2023-04-07T12:00:00Z",
                              "2023-05-07T12:00:00Z"
                           ]
                        },
                        {
                           "identifier":"bac9089e-6b22-4e18-8f7e-0bf82ef91045",
                           "number":10,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":119.65,
                           "installmentInterest":0.0,
                           "installmentTax":8.22,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z",
                              "2022-11-07T12:00:00Z",
                              "2022-12-07T12:00:00Z",
                              "2023-01-07T12:00:00Z",
                              "2023-02-07T12:00:00Z",
                              "2023-03-07T12:00:00Z",
                              "2023-04-07T12:00:00Z",
                              "2023-05-07T12:00:00Z",
                              "2023-06-07T12:00:00Z"
                           ]
                        },
                        {
                           "identifier":"ca0a4841-a590-457d-8461-520272efe636",
                           "number":11,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":108.77,
                           "installmentInterest":0.0,
                           "installmentTax":7.48,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z",
                              "2022-11-07T12:00:00Z",
                              "2022-12-07T12:00:00Z",
                              "2023-01-07T12:00:00Z",
                              "2023-02-07T12:00:00Z",
                              "2023-03-07T12:00:00Z",
                              "2023-04-07T12:00:00Z",
                              "2023-05-07T12:00:00Z",
                              "2023-06-07T12:00:00Z",
                              "2023-07-07T12:00:00Z"
                           ]
                        }
                     ]
                  },
                  {
                     "paymentMethod":"Ticket",
                     "paymentType":"Ticket",
                     "installments":[
                        {
                           "identifier":"3e9a5381-5d53-4a18-b34b-24cee545e042",
                           "number":1,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":1196.52,
                           "installmentInterest":0.0,
                           "installmentTax":82.23,
                           "dueDates":[
                              "2022-09-12T00:00:00Z"
                           ]
                        },
                        {
                           "identifier":"373ac391-9488-486f-912a-5047a2ef4345",
                           "number":2,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":598.26,
                           "installmentInterest":0.0,
                           "installmentTax":41.12,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z"
                           ]
                        },
                        {
                           "identifier":"d59da991-60c6-4f95-9af1-6f10b843e395",
                           "number":3,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":398.84,
                           "installmentInterest":0.0,
                           "installmentTax":27.41,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z",
                              "2022-11-07T12:00:00Z"
                           ]
                        },
                        {
                           "identifier":"54c11fd3-66cf-4496-bb0a-c832fc4e5e14",
                           "number":4,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":299.13,
                           "installmentInterest":0.0,
                           "installmentTax":20.56,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z",
                              "2022-11-07T12:00:00Z",
                              "2022-12-07T12:00:00Z"
                           ]
                        },
                        {
                           "identifier":"0dbf2828-7c4e-4e41-9e49-63d4b884b8a4",
                           "number":5,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":239.3,
                           "installmentInterest":0.0,
                           "installmentTax":16.45,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z",
                              "2022-11-07T12:00:00Z",
                              "2022-12-07T12:00:00Z",
                              "2023-01-07T12:00:00Z"
                           ]
                        },
                        {
                           "identifier":"db5b41b9-c816-4389-9f9c-58a48f7202f7",
                           "number":6,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":199.42,
                           "installmentInterest":0.0,
                           "installmentTax":13.7,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z",
                              "2022-11-07T12:00:00Z",
                              "2022-12-07T12:00:00Z",
                              "2023-01-07T12:00:00Z",
                              "2023-02-07T12:00:00Z"
                           ]
                        },
                        {
                           "identifier":"03e2eac3-3748-4a6d-a1f1-74aea6dd2771",
                           "number":7,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":170.93,
                           "installmentInterest":0.0,
                           "installmentTax":11.75,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z",
                              "2022-11-07T12:00:00Z",
                              "2022-12-07T12:00:00Z",
                              "2023-01-07T12:00:00Z",
                              "2023-02-07T12:00:00Z",
                              "2023-03-07T12:00:00Z"
                           ]
                        },
                        {
                           "identifier":"181af3fd-e556-477d-b380-ae9cd905c3a3",
                           "number":8,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":149.56,
                           "installmentInterest":0.0,
                           "installmentTax":10.28,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z",
                              "2022-11-07T12:00:00Z",
                              "2022-12-07T12:00:00Z",
                              "2023-01-07T12:00:00Z",
                              "2023-02-07T12:00:00Z",
                              "2023-03-07T12:00:00Z",
                              "2023-04-07T12:00:00Z"
                           ]
                        },
                        {
                           "identifier":"779297fe-017a-4b60-9109-7380c148974c",
                           "number":9,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":132.95,
                           "installmentInterest":0.0,
                           "installmentTax":9.14,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z",
                              "2022-11-07T12:00:00Z",
                              "2022-12-07T12:00:00Z",
                              "2023-01-07T12:00:00Z",
                              "2023-02-07T12:00:00Z",
                              "2023-03-07T12:00:00Z",
                              "2023-04-07T12:00:00Z",
                              "2023-05-07T12:00:00Z"
                           ]
                        },
                        {
                           "identifier":"0ffb543c-be91-4632-a53e-35dbdc4a2174",
                           "number":10,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":119.65,
                           "installmentInterest":0.0,
                           "installmentTax":8.22,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z",
                              "2022-11-07T12:00:00Z",
                              "2022-12-07T12:00:00Z",
                              "2023-01-07T12:00:00Z",
                              "2023-02-07T12:00:00Z",
                              "2023-03-07T12:00:00Z",
                              "2023-04-07T12:00:00Z",
                              "2023-05-07T12:00:00Z",
                              "2023-06-07T12:00:00Z"
                           ]
                        },
                        {
                           "identifier":"1c7124f6-98e0-404f-93c5-06cf6a6b1d4f",
                           "number":11,
                           "commissionValue":222.86,
                           "netValue":1114.29,
                           "interestValue":0.0,
                           "taxValue":82.23,
                           "totalValue":1196.52,
                           "installmentValue":108.77,
                           "installmentInterest":0.0,
                           "installmentTax":7.48,
                           "dueDates":[
                              "2022-09-12T00:00:00Z",
                              "2022-10-07T12:00:00Z",
                              "2022-11-07T12:00:00Z",
                              "2022-12-07T12:00:00Z",
                              "2023-01-07T12:00:00Z",
                              "2023-02-07T12:00:00Z",
                              "2023-03-07T12:00:00Z",
                              "2023-04-07T12:00:00Z",
                              "2023-05-07T12:00:00Z",
                              "2023-06-07T12:00:00Z",
                              "2023-07-07T12:00:00Z"
                           ]
                        }
                     ]
                  }
               ]
            }
         }
      ]
   },
   "success":true,
   "executed":"2022-09-05T22:29:49.8957345Z",
   "errors":null
}
```