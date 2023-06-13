# Criar Cotação



{% swagger method="post" path="{{version}}/quotation/contracting" baseUrl="{{url_ambiente}}/" summary="Criar Cotação" fullWidth="true" expanded="true" %}
{% swagger-description %}
Cria ou edita uma cotação.
{% endswagger-description %}

{% swagger-parameter in="header" name="Ocp-Apim-Subscription-Key" required="true" type="key" %}
chave de acesso da api.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Retorno sucesso." %}


[#response](cotacao.md#response "mention")


{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Retorno com mensagem do local do erro" %}
```json
{
    "success": false,
    "executed": "2023-05-22T20:10:41.1631988Z",
    "errors": [
        {
            "code": "ANSWERS-NOT-EVALUATED",
            "message": "One or more answers could not be evaluated.",
            "properties": [
                "INSURED-NAME"
            ]
        }
    ]
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Erro de "register number"" %}
```json
{
    "success": false,
    "executed": "2023-05-22T20:11:50.6875419Z",
    "errors": [
        {
            "code": "INCORRECT-OR-NONEXISTENT"
        },
        {
            "code": "TOKEN-ERROR"
        }
    ]
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="Caso não envie uma "chave" ou envie uma inválida" %}
{% code overflow="wrap" %}
```json
{
    "statusCode": 401,
    "message": "Access denied due to invalid subscription key. Make sure to provide a valid key for an active subscription."
}
```
{% endcode %}
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Erro de aplicação/servidor" %}

{% endswagger-response %}
{% endswagger %}

{% hint style="info" %}
Para editar uma cotação, basta enviar o identifier antes de answers, exemplo:

```json
{
    "operationCode": "MEDICAL-CIVIL-LIABILITY-PARTNER",
    "quotationIdentifier": "ea0da0ea-1623-47b7-bbbe-75e8eee15ee0", 
    "registerNumber": "100000",
    "answers": [
    ...
    ...
    ]
}
```
{% endhint %}

## Request

```json
{
    "operationCode": "MEDICAL-CIVIL-LIABILITY-PARTNER",
    "registerNumber": "100000",
    "answers": [
        {
            "code": "MODALITY",
            "answer": "MEDICAL-CIVIL-LIABILITY"
        },
        {
            "code": "PERSON-TYPE",
            "answer": "NATURAL"
        },
        {
            "code": "CONGENER",
            "answer": "NEW"
        },
        {
            "code": "START-VIGENCY-DATE",
            "answer": "2023-05-04T03:00:00.000Z"
        },
        {
            "code": "IDENTITY",
            "answer": "000.111.222-33"
        },
        {
            "code": "INSURED-NAME",
            "answer": "Teste Sistema Sul"
        },
        {
            "code": "INSURED-EMAIL",
            "answer": "teste@segurado.com"
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
            "code": "COMMISSION",
            "answer": 20
        },
        {
            "code": "GRIEVANCE-DISCOUNT",
            "answer": 0
        },
        {
            "code": "PROFESSIONAL-REGISTER",
            "answer": "568568567"
        },
        {
            "code": "CATEGORIES",
            "answer": [
                "OBSTETRICIAN"
            ]
        },
        {
            "code": "RESIDENT",
            "answer": false
        },
        {
            "code": "PROCEDURES-ACTIVITIES",
            "answer": [
                "AESTHETIC-PROCEDURES",
                "ENDOSCOPY-COLONOSCOPY",
                "RADIOTHERAPY-CHEMOTHERAPY-IMMUNOTHERAPY",
                "AESTHETIC-PROCEDURES-MEDICAL-SPECIALTY"
            ]
        },
        {
            "code": "RETROACTIVITY",
            "answer": 0
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
            "code": "TERRITORIALITY",
            "answer": "BR"
        },
        {
            "code": "SCOPE",
            "answer": "NATIONAL"
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
                    }
                ]
            ]
        }
    ]
}
```

### Explicando campos de envio.

```json
{
	"operationCode": "MEDICAL-CIVIL-LIABILITY-PARTNER",
	"registerNumber": "100000",
	"answers":[],
}
```

> **Field**: OperationCode\
> **Tipo**: `text`\
> ❗ Campo Obrigatório.
>
> Campo usado para definir qual produto está sendo cotado. Neste caso, o produto é "Médicos", representado pelo operation code "MEDICAL-CIVIL-LIABILITY-PARTNER".



> **Field:** RegisterNumber
>
> **Tipo:** `text`&#x20;
>
> ❗ Campo Obrigatório.
>
> Campo usado para definir qual o SusepNumber da corretora está sendo cotada. Neste caso, o susep da corretora é "100000".



> **Field**: Answers\
> **Tipo**: `array<answer>`\
> ❗ Campo Obrigatório.
>
> Campo usado para enviar perguntas gerais de uma cotação.



> **Field**: PERSON-TYPE\
> **Tipo**: `string`\
> ❗ Campo Obrigatório.
>
> Campo usado para definir o tipo de pessoa, sendo possivel enviar:
>
> * **NATURAL** = Pessoa Fisíca
> * **LEGAL** = Pessoa Jurídica



> **Field**: CONGENER\
> **Tipo**: `string`\
> ❗ Campo Obrigatório.
>
> Campo usado para definir o tipo de cotação, sendo possivel enviar:
>
> * **NEW** = Cotação Nova.
> * **RENEW** = Renovação vinda de outra corretora.



> **Field**: PREVIOUS-INSURER\
> **Tipo**: `string`\
> ❗ Campo Obrigatório caso <mark style="color:yellow;">CONGENER = RENEW</mark>.
>
> Campo usado para definir o cnpj que vem a cotação marcada com renovação.



> **Field**: PREVIOUS-INSURER-NAME\
> **Tipo**: `string`\
> ❗ Campo Obrigatório caso <mark style="color:yellow;">CONGENER = RENEW</mark>.
>
> Campo usado para definir o nome que vem a cotação marcada com renovação.



> **Code**: INSURED-ADDRESS-COMPLEMENT\
> **Tipo**: `text`\
>
>
> Pergunta usada para definir o número da moradia do segurado.



> **Code**: INSURED-ADDRESS-NEIGHBORHOOD\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o bairro do segurado.



> **Code**: INSURED-ADDRESS-CITY\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir a cidade do segurado.



> **Code**: INSURED-ADDRESS-STATE\
> **Tipo**: `text`\
> ❗Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o estado do segurado.



> **Code**: COMMISSION\
> **Tipo**: `decimal`\
> ❗Obrigatório que esteja incluído\
> Pergunta usada para definir a comissão.
>
> Pode ser enviado valores entre 1 e 30.\
> Valor padrão é 20.00.



> **Code**: GRIEVANCE-DISCOUNT\
> **Tipo**: `decimal`
>
> Pergunta usada para definir Agravo (aumento de preço sobre o netValue\* da cotação).\
> O Padrão é 0.\
> \* Preço líquido do produto sem IOF.

***

> **Code**: PROFESSIONAL-REGISTER\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o registro do profissional.

***

> **Code**: CATEGORIES\
> **Type**: `array<string>`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir a especialidade médica.
>
> Pode-se enviar mais de uma resposta dentro desse array de string, sendo elas:

<details>

<summary>Categorias disponiveis</summary>



**Especialidades para pessoa física**

* **NO-SURGERY** = Médico sem Cirurgia e Medicina de Urgência e Emergência (disponível SE PERSON-TYPE for NATURAL).
* **SURGERY-EXCEPT-PLASTIC** = Médico com Cirurgia (exceto Plástico), Anestesiologistas (disponível SE PERSON-TYPE for NATURAL).
* **OBSTETRICIAN** = Obstetra (disponível SE PERSON-TYPE for NATURAL).
* **PLASTIC-SURGERY** = Cirurgião(ã) Plástico(a) (disponível SE PERSON-TYPE for NATURAL).

**Especialidades para pessoa jurídica**

* **CLINIC-WITHOUT-SURGERY** = Clínicas (outras, sem cirurgia) (disponível SE PERSON-TYPE for LEGAL).
* **PATIENT-TRANSPORT** = Transporte de Pacientes (disponível SE PERSON-TYPE for LEGAL).
* **HOME-CARE** = Home care (disponível SE PERSON-TYPE for LEGAL).
* **SURGERY-CLINIC-EXCEPT-PLASTIC** = Clínica de Cirurgia e/ou Anestesiologia, Exceto Plástica (disponível SE PERSON-TYPE for igual a LEGAL).
* **CLINICAL-LABORATORY** = Laboratório de Análises Clínicas (disponível SE PERSON-TYPE for LEGAL).
* **BLOOD-BANK** = Bancos de Sangue (disponível SE PERSON-TYPE for LEGAL).
* **CLINICAL-OBSTETRICS** = Clínica com Obstetrícia (disponível SE PERSON-TYPE for LEGAL).
* **HOSPITAL** = Hospitais (disponível SE PERSON-TYPE for LEGAL).
* **PLASTIC-SURGERY-CLINIC** = Clínica de Cirurgia Plástica (disponível SE PERSON-TYPE for LEGAL).
* **CLINICAL-MULTIDISCIPLINARY** = Clínica Multidisciplinar (disponível SE PERSON-TYPE for LEGAL).

</details>

***

> **Code**: RESIDENT\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array para _pessoa física_ ou especialidade não for _Cirurgião(ã) Plástico(a)_ (se o PERSON-TYPE for NATURAL ou se CATEGORIES for diferente de PLASTIC-SURGERY).
>
> Pergunta usada para definir se o profissional é residente ou não.



> **Code**: PROCEDURES-ACTIVITIES\
> **Type**: `array<string>`
>
> Se atua com alguns desses procedimentos e/ou atividades.\
> \
> Pode-se enviar mais de uma resposta dentro desse array de string, sendo elas:

<details>

<summary>Procedimentos e/ou atividades</summary>

* **AESTHETIC-PROCEDURES** = Procedimentos Estéticos Minimamente Invasivos.

<!---->

* **ENDOSCOPY-COLONOSCOPY** = Endoscopia e/ou Colonoscopia.

<!---->

* **RADIOTHERAPY-CHEMOTHERAPY-IMMUNOTHERAPY** = Radioterapia e/ou Quimioterapia e/ou Imunoterapia.

<!---->

* **AESTHETIC-PROCEDURES-MEDICAL-SPECIALTY** = Procedimentos Estéticos relacionados à Especialidade Médica.

</details>

> **Code**: RETROACTIVITY\
> **Type**: `integer`
>
> Pergunta usada para definir a retroatividade.\
> \
> Os possíveis valores para esta pergunta são:

<details>

<summary>Retroatividade</summary>

* **0** = Sem retroatividade.
* **1** = 1 ano.
* **2** = 2 anos.
* **3** = 3 anos.
* **4** = 4 anos.
* **5** = 5 anos.

</details>

> **Code**: RETROACTIVITY-AGREEMENT\
> **Type**: `boolean`\
> ❗ Obrigatório que esteja incluído no array caso tenha retroatividade (RETROACTIVITY for MAIOR que 0).
>
> Pergunta usada para definir **"Entendimento e concordância de retroatividade"**. Se definida como true, indica que _**Estou ciente e de acordo que a confirmação da data de retroatividade ocorrerá apenas num eventual sinistro, sendo obrigatório apresentar as apólices anteriores para comprovação. A apólice anterior não pode ter sido cancelada ou ter tido interrupção de vigência.**_"

***

> **Code**: REVENUES\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array para pessoa jurídica (PERSON-TYPE for LEGAL).
>
> Pergunta usada para definir o Faturamento nos últimos 12 meses.\
> \
> Os possíveis valores para esta pergunta são:

<details>

<summary>Faturamento</summary>

* **0.00-100000.00** = Entre R$ 0,00 e R$ 100.000,00.

<!---->

* **100000.01-300000.00** = Entre R$ 100.000,01 e R$ 300.000,00.

<!---->

* **300000.01-500000.00** = Entre R$ 300.000,01 e R$ 500.000,00.

<!---->

* **500000.01-1000000.00** = Entre R$ 500.000,01 e R$ 1.000.000,00.

<!---->

* **1000000.01-1500000.00** = Entre R$ 1.000.000,01 e R$ 1.500.000,00.

<!---->

* **1500000.01-2000000.00** = Entre R$ 1.500.000,01 e R$ 2.000.000,00.

<!---->

* **2000000.01-3000000.00** = Entre R$ 2.000.000,01 e R$ 3.000.000,00.

<!---->

* **3000000.01-5000000.00** = Entre R$ 3.000.000,01 e R$ 5.000.000,00.

<!---->

* **5000000.01-7500000.00** = Entre R$ 5.000.000,01 e R$ 7.500.000,00.

<!---->

* **7500000.01-10000000.00** = Entre R$ 7.500.000,01 e R$ 10.000.000,00.

<!---->

* **10000000.01-15000000.00** = Entre R$ 10.000.000,01 e R$ 15.000.000,00.

<!---->

* **15000000.01-20000000.00** = Entre R$ 15.000.000,01 e R$ 20.000.000,00.

</details>

> **Code**: CLAIMS\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir se houve sinistros nos últimos 24 meses\
> \
> Os valores possíveis para esta pergunta são:
>
> * **0 =** nenhum.
> * **1 =** 1 reclamação.
> * **2** **=** 2 reclamações.

***

> **Code**: CLAIM-EXPECTATION\
> **Type**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir se o segurado tem conhecimento ou Expectativas de Sinistro (alguma circunstância que possa gerar um sinistro).

***

> **Code**: CLAIM-EXPECTATION-THIRD-PARTY\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array (se CLAIM-EXPECTATION for TRUE).
>
> Pergunta usada para definir possíveis terceiros reclamantes de expectativas de sinistro.

***

> **Code**: CLAIM-EXPECTATION-AGREEMENT\
> **Type**: `boolean`\
> ❗ Obrigatório que esteja incluído no array (se CLAIM-EXPECTATION for TRUE).
>
> Pergunta usada para definir "**Entendimento e concordância de expectativas de sinistro**". Se definida como true, indica que "**Entendido e acordado que não haverá cobertura securitária para qualquer tipo de fato já conhecido pelo segurado.**"

***

> **Code**: TERRITORIALITY\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array. Atualmente so atendemos corretores/corretoras que atendem no Brasil\
> Pergunta usada para definir a Territorialidade.\
> \
> Os possíveis valores para esta pergunta são:
>
> * **BR =** Brasil

***

> **Code**: SCOPE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array. Atualmente só atender corretoras/corretores com trabalhos nacionais.\
> Pergunta usada para definir o Âmbito de trabalho do corretor/corretora.\
> \
> Os possíveis valores para esta pergunta são:
>
> * **NATIONAL =** nacional

***

> **Code**: LIMIT-DEDUCTIBLE\
> **Type**: `array<array<answer>>`\
> ❗ Obrigatório que esteja incluído no array.
>
> Campo para definir limite e franquia. Abordaremos mais detalhadamente a seguir.

***

```json
{
  "identifier": "7dfac165-a63e-40d8-b6bb-23431e057982",
  "operationCode": "MEDICAL-CIVIL-LIABILITY-PARTNER",
  "answers": [
    {
      "code": "MODALITY",
      "answer": "MEDICAL-CIVIL-LIABILITY"
    },
    {
      "code": "LIMIT-DEDUCTIBLE",
      "answer": [
        [
          {
            "code": "LIMIT",
            "answer": 30000
          },
          {
            "code": "DEDUCTIBLE",
            "answer": "DEFAULT"
          }
        ]
      ]
    }
  ]

```

> **Code**: LIMIT\
> **Type**: `decimal`\
> ❗ Obrigatório que esteja incluído no array.
>
> Os valores possíveis para esta pergunta são:

<details>

<summary>Limites</summary>

* **30000.0** = R$ 30.000.

<!---->

* **50000.0** = R$ 50.000.

<!---->

* **100000.0** = R$ 100.000.

<!---->

* **150000.0** = R$ 150.000.

<!---->

* **200000.0** = R$ 200.000.

<!---->

* **250000.0** = R$ 250.000.

<!---->

* **300000.0** = R$ 300.000.

<!---->

* **400000.0** = R$ 400.000.

<!---->

* **500000.0** = R$ 500.000.

<!---->

* **600000.0** = R$ 600.000.

<!---->

* **700000.0** = R$ 700.000.

<!---->

* **800000.0** = R$ 800.000.

<!---->

* **900000.0** = R$ 900.000.

<!---->

* **1000000.0** = R$ 1.000.000.

<!---->

* **1100000.0** = R$ 1.100.000.

<!---->

* **1200000.0** = R$ 1.200.000.

<!---->

* **1300000.0** = R$ 1.300.000.\

* **1400000.0** = R$ 1.400.000.\

* **1500000.0** = R$ 1.500.000.\

* **1600000.0** = R$ 1.600.000.\

* **1700000.0** = R$ 1.700.000.\

* **1800000.0** = R$ 1.800.000.\

* **1900000.0** = R$ 1.900.000.\

* **2000000.0** = R$ 2.000.000.

</details>

***

> **Code**: DEDUCTIBLE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array. Essa é uma parte um pouco mais complicada\\
>
> Pergunta usada para definir o tipo da franquia.\
> \
> Verifique abaixo como funciona a regra de franquias:

<details>

<summary>Franquias</summary>

* **DEFAULT**
* **INCREASED**
* **REDUCED**
* **MINIMUM**

**Dependendo do tipo de categoria definido no campo CATEGORIES. Abaixo, você pode ver detalhadamente:**\


Se for **NO-SURGERY**:

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.
* **MINIMUM =** Mínima - Sem franquia.

Se for **SURGERY-EXCEPT-PLASTIC**:

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.
* **MINIMUM =** Mínima - Sem franquia.

Se for **OBSTETRICIAN**:

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 500,00.
* **MINIMUM =** Mínima - 5% dos prejuízos indenizáveis com o mínimo de R$ 200,00.

Se for **PLASTIC-SURGERY**:

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,000.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 10.000,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00.
* **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.

Se for **PLASTIC-SURGERY-CLINIC**:

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 15.000,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 20.000,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 10.000,00.
* **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 7.500,00.

Se for **CLINICAL-LABORATORY**:

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 7.000,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 9.000,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,00.
* **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.000,00.

Se for **HOME-CARE**:

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.500,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.
* **MINIMUM =** Mínima - Sem franquia.

Se for **HOSPITAL**:

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 15.000,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 20.000,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 10.000,00.
* **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 7.500,00.

Se for **PATIENT-TRANSPORT**:

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.500,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.
* **MINIMUM =** Mínima - Sem franquia.

Se for **CLINIC-WITHOUT-SURGERY**:

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.500,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 500,00.
* **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 400,00.

Se for **BLOOD-BANK**:

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 15.000,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 20.000,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 10.000,00.
* **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 7.500,00.

Se for **SURGERY-CLINIC-EXCEPT-PLASTIC**:

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.500,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.
* **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.

Se for **CLINICAL-OBSTETRICS**:

* **DEFAULT =** Padrão - 15% dos prejuízos indenizáveis com o mínimo de R$ 500,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.500,00.
* **REDUCED =** Reduzida - 15% dos prejuízos indenizáveis com o mínimo de R$ 1.500,00.
* **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.

Se for **CLINICAL-MULTIDISCIPLINARY**:

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.500,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.500,00.
* **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 800,00.

</details>

## Response

```json
{
    "item": {
        "quotationIdentifier": "606af046-2a40-4688-af2c-148d65f73aef",
        "status": "Draft",
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
                    "totalValue": 1794.78,
                    "limitDeductible": {
                        "deductible": {
                            "answer": [
                                "DEFAULT"
                            ],
                            "questionText": "Franquia",
                            "answerText": [
                                "Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00"
                            ]
                        },
                        "limits": {
                            "answer": [
                                100000.0
                            ],
                            "questionText": "Limite de cobertura",
                            "answerText": [
                                "R$ 100.000"
                            ]
                        }
                    }
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
    "executed": "2022-11-23T20:55:03.0612167Z"
}
```

### Explicando campos de retorno

> **Field**: success\
> **Type**: `boolean`
>
> Indica se a requisição foi feita com sucesso.

***

> **Field**: executed\
> **Type**: `date`
>
> Data em que a requisição foi feita.

***

> **Field**: errors\
> **Type**: `array`
>
> Array de erros ao fazer a requisição.

***

> **Field**: item.quotationIdentifier\
> **Type**: `guid`
>
> Identificador da cotação.

***

> **Field**: item.status\
> **Type**: `integer`
>
> Status da cotação.

***

> **Field**: item.expiredAt\
> **Type**: `date`
>
> Data de expiração da cotação.

***

> **Field**: item.quotationDocumentUrl\
> **Type**: `text`
>
> Url do documento de cotação.

***

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
> Valor de Limite da apólice.

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
> Exibe o código que identifica a ou as coberturas contratadas.

***

> **Field**: item.pricing\[].price.rates\[].description\
> **Type**: `text`
>
> Trata-se do nome da cobertura em português.

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
> Esté é o código necessário enviar ao selecionar o método de pagamento.
>
> Exemplo: Se foi selecionado cartão de crédito, enviar o identificador daquele meio de pagamento.

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
