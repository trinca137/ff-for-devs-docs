# Criar Cotação



## Criar Cotação

<mark style="color:green;">`POST`</mark> `{{url_ambiente}}/{{version}}/quotation/contracting`

Cria ou edita uma cotação.

#### Headers

| Name                                                        | Type | Description             |
| ----------------------------------------------------------- | ---- | ----------------------- |
| Ocp-Apim-Subscription-Key<mark style="color:red;">\*</mark> | key  | chave de acesso da api. |

{% tabs %}
{% tab title="200: OK Retorno sucesso. " %}
[#response](cotacao.md#response "mention")
{% endtab %}

{% tab title="400: Bad Request Retorno com mensagem do local do erro" %}
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
{% endtab %}

{% tab title="400: Bad Request Erro de "register number"" %}
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
{% endtab %}

{% tab title="401: Unauthorized Caso não envie uma "chave" ou envie uma inválida" %}
{% code overflow="wrap" %}
```json
{
    "statusCode": 401,
    "message": "Access denied due to invalid subscription key. Make sure to provide a valid key for an active subscription."
}
```
{% endcode %}
{% endtab %}

{% tab title="500: Internal Server Error Erro de aplicação/servidor" %}

{% endtab %}
{% endtabs %}

{% hint style="info" %}
Para editar uma cotação, basta enviar o identifier antes de answers, exemplo:

```json
{
    "operationCode": "DENTIST-CIVIL-LIABILITY-PARTNER",
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
    "operationCode": "DENTIST-CIVIL-LIABILITY-PARTNER",
    "registerNumber": "100000",
    "answers": [
        {
             "code": "TEAM-LEADER",
             "answer": true
        },
        {
             "code": "CLINIC-OR-TECHNICAL-DIRECTOR",
             "answer": true
        },
        {
            "code": "MODALITY",
            "answer": "DENTIST-CIVIL-LIABILITY"
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
            "code": "PREVIOUS-INSURER",
            "answer": "0"
        },
        {
            "code": "PREVIOUS-INSURER-NAME"
        },
        {
            "code": "START-VIGENCY-DATE",
            "answer": "2022-11-23T03:00:00.000Z"
        },
        {
            "code": "IDENTITY",
            "answer": "000.111.222-33"
        },
        {
            "code": "INSURED-NAME",
            "answer": "Nome segurado"
        },
        {
            "code": "INSURED-SOCIAL-NAME",
            "answer": "nome teste"
        },
        {
            "code": "INSURED-SOCIAL-NAME-AGREEMENT",
            "answer": true
        },
        {
            "code": "INSURED-EMAIL",
            "answer": "email@segurado.com"
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
            "code": "BROKERAGE-COMMISSION",
            "answer": 20
        },
        {
            "code": "GRIEVANCE-DISCOUNT",
            "answer": 0
        },
        {
            "code": "PROFESSIONAL-REGISTER",
            "answer": "567657"
        },
        {
            "code": "CATEGORIES",
            "answer": [
                "OROFACIAL-HARMONIZATION",
                "FACIAL-FILLERS",
                "GENERAL-PROCEDURES"
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

> **Field**: TEAM-LEADER
>
> **Tipo**: `boolean`
>
> Campo que expressa se o médico é o líder da equipe, nas quais as respostas possível são **TRUE** ou **FALSE.**

> **Field**: CLINIC-OR-TECHNICAL-DIRECTOR
>
> **Tipo**: `boolean`
>
> Campo que expressa se o médico é diretor clínico ou técnico, nas quais as respostas possível são **TRUE** ou **FALSE.**

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
> * **RENEWAL** = Renovação vinda de outra seguradora (renovação **congênere**).



> **Field**: PREVIOUS-INSURER\
> **Tipo**: `string`\
> ❗ Campo Obrigatório caso <mark style="color:yellow;">CONGENER = RENEWAL</mark>.
>
> Campo usado para definir o cnpj que vem a cotação marcada com renovação **congênere**.



> **Field**: PREVIOUS-INSURER-NAME\
> **Tipo**: `string`\
> ❗ Campo Obrigatório caso <mark style="color:yellow;">CONGENER = RENEWAL</mark>.
>
> Campo usado para definir o nome que vem a cotação marcada com renovação **congênere**.



> **Field**: INSURED-SOCIAL-NAME\
> **Tipo**: `string`
>
> Pergunta usada para informar o nome social do segurado, caso o mesmo possua.
>
> &#x20;\* Pergunta apenas permitida quando **PERSON-TYPE** for **NATURAL.**



> **Field**: INSURED-SOCIAL-NAME-AGREEMENT\
> **Tipo**: `string`\
> ❗ Obrigatório caso segurado possuir nome social.
>
> Pergunta usada para definir "Permitir a utilização de nome social do segurado na cotação". Caso segurado possuir nome social, então este campo deverá obrigatoriamente receber a resposta "true".



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



> **Code**: BROKERAGE-COMMISSION\
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
> Pergunta usada para definir as especialidades Odontológicas.
>
> Pode-se enviar mais de uma resposta dentro desse array de string, sendo elas:

<details>

<summary>Categorias</summary>

* **OROFACIAL-HARMONIZATION** = Harmonização Orofacial (HOF)

<!---->

* **IMPLANTS** = Implantodontia

<!---->

* **ORALMAXILLOFACIAL-SURGERY** = Cirurgia Bucomaxilofacial

<!---->

* **FACIAL-FILLERS** = Preenchedores Faciais (não-estético)

<!---->

* **GENERAL-PROCEDURES** = Procedimentos Clínicos em Geral

</details>

***

> **Code**: LEGAL-TYPE\
> **Type**: `array<string>`\
> ❗ Obrigatorio que esteja incluído no array se for pessoa jurídica (PERSON-TYPE for LEGAL).
>
> Pergunta usada para definir Característica da PJ.
>
> Os possiveis valores para esta pergunta são:

<details>

<summary>Perfil PJ</summary>

* **PRIVATE-OFFICE** = Consultório Particular

<!---->

* **HIGHER-EDUCATION-INSTITUTION** = Instituição de Ensino Superior

<!---->

* **DENTAL-PLAN-OPERATOR** = Operadora de Planos Odontológicos

<!---->

* **MASTER-FRANCHISOR** = Franqueador Master

</details>

***

> **Code**: RETROACTIVITY\
> **Type**: `integer`
>
> Pergunta usada para definir a retroatividade.
>
> Os possíveis valores para esta pergunta são:

<details>

<summary>Retroatividade</summary>

* **0** = Sem retroatividade.

<!---->

* **1** = 1 ano.

<!---->

* **2** = 2 anos.

<!---->

* **3** = 3 anos.

<!---->

* **4** = 4 anos.

<!---->

* **5** = 5 anos.

</details>

***

> **Code**: RETROACTIVITY-DATE\
> **Type**: `date (aaaa-mm-dd)`
>
> Pergunta usada para definir a data de retroatividade para renovação **congênere**.\
> \
> Para esta pergunta é possivel enviar qualquer data, e pode enviar '**RETROACTIVITY**' como 0 (a data de **RETROACTIVITY** vai ser sobreescrita caso envie algum valor, mas ainda sera necessário enviar retroactivity e a resposta para **renovação congênere**).

<details>

<summary>Exemplo de json</summary>

```
.
.
.
{
    "code": "CONGENER",
    "answer": "RENEWAL"
},
.
.
.
{
    "code": "RETROACTIVITY",
    "answer": 0
},
{
    "code": "RETROACTIVITY-DATE",
    "answer": "2010-08-31"
},
```

</details>

***

> **Code**: RETROACTIVITY-AGREEMENT\
> **Type**: `boolean`\
> ❗ Obrigatório que esteja incluído no array. (se o RETROACTIVITY for maior que zero).
>
> Pergunta usada para definir **"Entendimento e concordância de retroatividade"**. Se definida como true, indica que _**Estou ciente e de acordo que a confirmação da data de retroatividade ocorrerá apenas num eventual sinistro, sendo obrigatório apresentar as apólices anteriores para comprovação. A apólice anterior não pode ter sido cancelada ou ter tido interrupção de vigência.**_

***

> **Code**: REVENUES\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array se for pessoa jurídica (PERSON-TYPE for LEGAL).
>
> Pergunta usada para definir o Faturamento nos últimos 12 meses.
>
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

* **10000000.01-12500000.00** = Entre R$ 10.000.000,01 e R$ 12.500.000,00.

<!---->

* **12500000.01-15000000.00** = Entre R$ 12.500.000,01 e R$ 15.000.000,00.

</details>

***

> **Code**: CLAIMS\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir se houve sinistros nos últimos 24 meses.
>
> Os valores possíveis para esta pergunta são:
>
> * **0 =** nenhum.
> * **1 =** 1 reclamação.
> * **2 =** 2 reclamações.

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
> ❗ Obrigatório que esteja incluído no array. Atualmente so atendemos dentistas que atendem no Brasil\
> Pergunta usada para definir a territorialidade.
>
> Os valores possíveis para esta pergunta são:
>
> * **BR =** Brasil.

***

> **Code**: SCOPE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array. Atualmente só atender dentistas com trabalhos nacionais.\
> Pergunta usada para definir o Âmbito de trabalho do dentista.
>
> Os possíveis valores para esta pergunta são:
>
> * **NATIONAL =** Nacional.

***

> **Code**: LIMIT-DEDUCTIBLE\
> **Type**: `array<array<answer>>`\
> ❗ Obrigatório que esteja incluído no array.
>
> Campo para definir limite e franquia. Abordaremos mais detalhadamente a seguir.

```json
{
  "identifier": "7dfac165-a63e-40d8-b6bb-23431e057982",
  "operationCode": "DENTIST-CIVIL-LIABILITY-PARTNER",
  "answers": [
    {
      "code": "MODALITY",
      "answer": "DENTIST-CIVIL-LIABILITY"
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
}
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
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o tipo da franquia.
>
>
>
> <mark style="color:yellow;">**Dependendo do tipo de categoria definido no campo CATEGORIES e o tipo de PESSOA (física ou jurídica), a resposta será diferente. Abaixo, você pode ver detalhadamente nos campos expandiveis:**</mark>

<details>

<summary>Pessoa fisica (PERSON-TYPE = NATURAL)</summary>

Franquias para **GENERAL-PROCEDURES**

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 500,00.
* **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 400,00.\


Franquia para **IMPLANTS**

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 500,00.
* **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 400,00.\


Franquia para **FACIAL-FILLERS**

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 500,00.
* **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 400,00.\


Franquia para **ORALMAXILLOFACIAL-SURGERY**

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.500,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.500,00.
* **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.\


Franquia para **OROFACIAL-HARMONIZATION**

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.
* **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.500,00.\


</details>

<details>

<summary>Pessoa juridica (PERSON-TYPE = LEGAL)</summary>



Franquia para **GENERAL-PROCEDURES**

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$4.500,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1,500,00.
* **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.\


Franquia para **IMPLANTS**

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$4.500,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1,500,00.
* **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.\


Franquia para **FACIAL-FILLERS**

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$4.500,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1,500,00.
* **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.\


Franquia para **ORALMAXILLOFACIAL-SURGERY**

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.500,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.500,00.
* **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.\


Franquia para **OROFACIAL-HARMONIZATION**

* **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00.
* **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,00.
* **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.
* **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.500,00.

</details>



## Response

```json
{
    "item": {
        "quotationIdentifier": "8324a438-c765-44ee-a7ea-bcfc4b810d22",
        "quotationDocumentUrl":"",
        "status": "Draft",
        "pricing": [
            {
                "variantIdentifier": "a5802d31-650d-441a-be7b-35578da2c25d",
                "underwriting": {
                    "approved": true,
                    "evaluations": []
                },
                "price": {
                    "commission": 196.11,
                    "grievanceDiscount": 0.0,
                    "netValue": 980.57,
                    "interestValue": 0.0,
                    "taxValue": 72.37,
                    "totalValue": 1052.94,
                    "limitDeductible": {
                        "deductible": {
                            "answer": [
                                "DEFAULT"
                            ],
                            "questionText": "Franquia",
                            "answerText": [
                                "Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00"
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
                                    "identifier": "5acb297e-08d3-4561-bb54-9a194c2ab9fb",
                                    "number": 1,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 1052.94,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 72.37,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "50a436dd-1595-4afc-8d00-aebbd5e5b82a",
                                    "number": 2,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 526.47,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 36.18,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "0b8e498d-3f5a-4653-b011-26f5e93e28bc",
                                    "number": 3,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 350.98,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 24.12,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "54b4a4b4-36e8-4faf-83c6-f00ecdd87b50",
                                    "number": 4,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 263.24,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 18.09,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "b8199a1f-300f-4fc5-bea6-bf728cf79f6f",
                                    "number": 5,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 210.59,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 14.47,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "f955afcd-60f3-4cbf-b7e9-dd5c3c93e323",
                                    "number": 6,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 175.49,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 12.06,
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
                                    "identifier": "317c153c-ccc3-4c25-b996-23798ced8651",
                                    "number": 7,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 150.42,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 10.34,
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
                                    "identifier": "cb13b262-7f92-4747-9566-b8432ff16adb",
                                    "number": 8,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 131.62,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 9.05,
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
                                    "identifier": "38ba064f-5798-42e8-837f-a31854762462",
                                    "number": 9,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 116.99,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 8.04,
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
                                    "identifier": "c9ae667e-1a85-40ae-bca6-2e4ddae0843c",
                                    "number": 10,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 105.29,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 7.24,
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
                                }
                            ]
                        },
                        {
                            "paymentMethod": "Ticket",
                            "paymentType": "Ticket",
                            "installments": [
                                {
                                    "identifier": "6dd8ad5e-4f35-48da-b1e5-f8d4e6f3d094",
                                    "number": 1,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 1052.94,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 72.37,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "628dff00-0575-4b5c-b1af-141973d1aa96",
                                    "number": 2,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 526.47,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 36.18,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "eff81616-34f7-4e07-973b-8344c372a2f6",
                                    "number": 3,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 350.98,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 24.12,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "56031475-16e0-411e-a61c-d70eb94b0a37",
                                    "number": 4,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 263.24,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 18.09,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "962c2e09-2c33-4d99-b2e0-f464bdb5d6b2",
                                    "number": 5,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 210.59,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 14.47,
                                    "dueDates": [
                                        "2022-11-30T00:00:00Z",
                                        "2022-12-01T12:00:00Z",
                                        "2023-01-01T12:00:00Z",
                                        "2023-02-01T12:00:00Z",
                                        "2023-03-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "618c2480-d451-4b45-bcfa-007c77426703",
                                    "number": 6,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 175.49,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 12.06,
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
                                    "identifier": "c0eaeeec-ad63-48f4-bfd7-2c7f22425689",
                                    "number": 7,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 150.42,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 10.34,
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
                                    "identifier": "c08e9ab2-8bb9-4c82-ada5-f2e3b6dd9898",
                                    "number": 8,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 131.62,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 9.05,
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
                                    "identifier": "a29eef1a-eab0-4ecd-8d42-24cbf2f6a301",
                                    "number": 9,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 116.99,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 8.04,
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
                                    "identifier": "d03bd19e-fedd-4dab-9f4e-42cedcbf59c6",
                                    "number": 10,
                                    "commissionValue": 196.11,
                                    "netValue": 980.57,
                                    "interestValue": 0.0,
                                    "taxValue": 72.37,
                                    "totalValue": 1052.94,
                                    "installmentValue": 105.29,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 7.24,
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
                                }
                            ]
                        }
                    ]
                }
            }
        ]
    },
    "success": true,
    "executed": "2022-11-23T18:16:57.5122616Z"
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

> **Field**: item.pricing\[].price.limitDeductible\
> **Type**: `object`
>
> Limites e franquias selecionadas.

***

> **Field**: item.pricing\[].price.limitDeductible.deductible.answer\
> **Type**: `text`
>
> Tipo de franquia selecionada.&#x20;

***

> **Field**: item.pricing\[].price.limitDeductible.deductible.answerText\
> **Type**: `text`
>
> Texto da franquia selecionada

***

> **Field**: item.pricing\[].price.limitDeductible.limits.answer\
> **Type**: `decimal`
>
> Valor do limite selecionado.&#x20;

***

> **Field**: item.pricing\[].price.limitDeductible.limits.answerText\
> **Type**: `text`
>
> Texto do limite selecionado.

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
