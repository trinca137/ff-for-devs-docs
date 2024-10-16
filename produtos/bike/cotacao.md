---
description: >-
  Aqui temos um exemplo de envio e retorno para criar uma cotação. (talvez seja
  necessário alterar informações como "RegisterNumber" ou data de vigência para
  funcionar).
---

# Criar cotação



## Criar Cotação

<mark style="color:green;">`POST`</mark> `{{url_ambiente}}/{{version}}/quotation/contracting`

Cria ou edita uma cotação.

#### Headers

| Name                                                        | Type | Description             |
| ----------------------------------------------------------- | ---- | ----------------------- |
| Ocp-Apim-Subscription-Key<mark style="color:red;">\*</mark> | key  | chave de acesso da api. |

{% tabs %}
{% tab title="200: OK Retorno sucesso." %}
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
    "operationCode": "BIKE-MULTIPLE-PERIL-PARTNER",
    "quotationIdentifier": "ea0da0ea-1623-47b7-bbbe-75e8eee15ee0", 
    "registerNumber": "100000",
    "answers": [
    ...
    ...
    ]
}
```
{% endhint %}

## Request <a href="#request" id="request"></a>

```json
{
    "operationCode": "BIKE-MULTIPLE-PERIL-PARTNER",
    "registerNumber": "100000",
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
            "answer": "2023-08-23T03:00:00.000Z"
        },
        {
            "code": "CONGENER",
            "answer": "NEW"
        },
        {
            "code": "PREVIOUS-INSURER",
            "answer": ""
        },
        {
            "code": "PREVIOUS-INSURER-NAME",
            "answer": ""
        },
        {
            "code": "INSURED-NAME",
            "answer": "Teste bike"
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
            "answer": "segurado@trin.ca"
        },
        {
            "code": "IDENTITY",
            "answer": "28214722268"
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
            "answer": "44"
        },
        {
            "code": "INSURED-ADDRESS-COMPLEMENT",
            "answer": "Não é obrigatório"
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
            "code": "ITEMS",
            "answer": [
                [
                    {
                        "code": "SERIAL-NUMBER",
                        "answer": "13"
                    },
                    {
                        "code": "ITEM-TYPE",
                        "answer": "TRADITIONAL"
                    },
                    {
                        "code": "MANUFACTURE-YEAR",
                        "answer": 2022
                    },
                    {
                        "code": "MODEL",
                        "answer": "12"
                    },
                    {
                        "code": "COMPETITIONS",
                        "answer": false
                    },
                    {
                        "code": "ORIGINAL-VALUE",
                        "answer": 5000.00
                    },
                    {
                        "code": "ORIGINAL-VALUE-FACTOR",
                        "answer": 100
                    },
                    {
                        "code": "NEW",
                        "answer": false
                    },
                    {
                        "code": "BRAND",
                        "answer": "ACCELL"
                    },
                    {
                        "code": "BRAND-NAME",
                        "answer": "ACCELL"
                    },
                    {
                        "code": "FRAME-TYPE",
                        "answer": "CARBON"
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
                        "answer": "DEFAULT"
                    },
                    {
                        "code": "PARTS",
                        "answer": [
                            [
                                {
                                    "code": "PART-TYPE",
                                    "answer": "UNMODIFIED"
                                },
                                {
                                    "code": "PART-BRAND"
                                },
                                {
                                    "code": "PART-MODEL"
                                },
                                {
                                    "code": "PART-VALUE"
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
                    },
                    {
                        "code": "VALUE-AGREEMENT",
                        "answer": true
                    }
                ]
            ]
        }
    ]
}
```

### Explicando campos de envio <a href="#request-cotacao" id="request-cotacao"></a>

```json
{
	"operationCode": "BIKE-MULTIPLE-PERIL-PARTNER",
	"registerNumber": "100000",
	"answers":[],
}
```

> **Field**: OperationCode\
> **Tipo**: `text`\
> ❗ Campo Obrigatório.
>
> Campo usado para definir qual produto está sendo cotado. Neste caso, o produto é "Bike", representado pelo operation code "BIKE-MULTIPLE-PERIL-PARTNER".



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
> ❗ Campo Obrigatório caso <mark style="color:yellow;">CONGENER = RENEW</mark>.
>
> Campo usado para definir o cnpj que vem a cotação marcada com renovação.



> **Field**: PREVIOUS-INSURER-NAME\
> **Tipo**: `string`\
> ❗ Campo Obrigatório caso <mark style="color:yellow;">CONGENER = RENEW</mark>.
>
> Campo usado para definir o nome que vem a cotação marcada com renovação.



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
> ❗ Obrigatório que esteja incluído no array.
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

***

> **Code**: ITEMS\
> **Tipo**: `array<answer>`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta em formato de array de answer é usada para enviar perguntas mais específicas do produto em questão. Neste caso, o "Bike". Mais detalhes sobre essas perguntas a seguir, na documentação.

<details>

<summary>Exemplo do array de items</summary>

```json
{
    "code": "ITEMS",
    "answer": [
        [
            {
                "code": "SERIAL-NUMBER",
                "answer": "13"
            },
            {
                "code": "ITEM-TYPE",
                "answer": "TRADITIONAL"
            },
            {
                "code": "MANUFACTURE-YEAR",
                "answer": 2022
            },
            {
                "code": "MODEL",
                "answer": "12"
            },
            {
                "code": "COMPETITIONS",
                "answer": false
            },
            {
                "code": "ORIGINAL-VALUE",
                "answer": 3500
            },
            {
                "code": "VALUE-AGREEMENT",
                "answer": true
            }
         {
                "code": "NEW",
                "answer": false
            },
            {
                "code": "BRAND",
                "answer": "ACCELL"
            },
            {
                "code": "BRAND-NAME",
                "answer": "ACCELL"
            },
            {
                "code": "FRAME-TYPE",
                "answer": "CARBON"
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
                "answer": "DEFAULT"
            },
            {
                "code": "PARTS",
                "answer": [
                    [
                        {
                            "code": "PART-TYPE",
                            "answer": "UNMODIFIED"
                        },
                        {
                            "code": "PART-BRAND"
                        },
                        {
                            "code": "PART-MODEL"
                        },
                        {
                            "code": "PART-VALUE"
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
}
```

</details>

***

> **Code**: SERIAL-NUMBER\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o número de série da bike em questão. Máximo de 30 caracteres.

***

> **Code**: ITEM-TYPE\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o tipo da bike.\
> \
> Os valores possíveis para esta pergunta são:
>
> * **TRADITIONAL =** bike tradicional.
> * **ELECTRIC =** bike elétrica (até 1000W).

***

> **Code**: MANUFACTURE-YEAR\
> **Tipo**: `integer`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o ano de fabricação da bike. Não cobrimos bikes fabricadas 4 anos anteriores do atual.
>
> **❕São aceitas apenas bikes fabricadas no ano atual e até 7 anos anteriores.**

***

> **Code**: MODEL\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o modelo da bike.

***

> **Code**: COMPETITIONS\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir se a bike será utilizada em competições.

***

> **Code**: ORIGINAL-VALUE\
> **Tipo**: `decimal`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o valor original da bike.

***

> **Code**: ORIGINAL-VALUE-FACTOR\
> **Tipo**: `decimal`\
> ❗Obrigatório caso a pergunta de **INVOICE** seja **True**. Caso seja **False,** pode enviar mas não é obrigatório.\
>
>
> Esta pergunta serve para o **Valor da Nota Fiscal em %,** onde deixa o cliente com a opção de contratar um valor superior ao valor da bike para cobrir eventuais diferenças cambiais ou desvalorização do bem.
>
> \
> **As respostar permitidas para essa pergunta são:**
>
> \
> **100 =** 100%
>
> **105 =** 105%
>
> **107 =** 107%
>
> **110 =** 110%

***

> **Code**: VALUE-AGREEMENT\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array (se for falso, indica que não concorda com o valor e impossibilitando a contratação).
>
> Pergunta usada para definir "**Entendimento e concordância de valor aprovado.**". Se definida como true, indica que "**Estou de acordo com o valor aprovado pela Fairfax.**".

***

> **Code**: NEW\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir se a bike é nova ou não.
>
> ❕Uma bike é considerada nova quando o segurado é o primeiro proprietário e a data de emissão da Nota Fiscal (NF) seja de até 60 dias da data atual.

***

> **Code**: BRAND\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o nome da marca da bike, caso tenha algum nome diferente, enviar **OTHER**.

***

> **Code**: BRAND-NAME\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta também utilizada para definir o nome da marca da bike, porém quando **BRAND = OTHER** enviar o nome da marca como resposta.

***

> **Code**: FRAME-TYPE\
> **Tipo**: `text`\
> ❗ Obrigatorio que esteja incluído no array.
>
> Pergunta usada para definir o tipo de quadro da bike.\
> \
> Os valores possíveis para esta pergunta são:
>
> * **CARBON =** carbono.
> * **ALUMINUM =** alumínio.
> * **STEEL=** aço.

***

> **Code**: FRAME-TYPE-AGREEMENT\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array (se for falso, indica não concordância com o material informado e impossibilitando a contratação).
>
> Pergunta usada para definir "**Entendimento e concordância do tipo de quadro.**" Se definida como true, indica que "**Estou ciente e de acordo que o material do quadro da Bicicleta acima indicado está correto. A informação incorreta acarretará perda do direito.**"

***

> **Code**: CLAIMS\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir se houve sinistros nos últimos 36 meses.\
> \
> Os valores possíveis para esta pergunta são:
>
> * **0 =** nenhum.
> * **1 =** sinistro.
> * **2 =** sinistros.
> * **3+ é declinado (não cobrimos).**

***

> **Code**: DEDUCTIBLE\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o tipo de franquia.\
> \
> Os valores possíveis para esta pergunta são:
>
> * **DEFAULT** = padrão.
> * **REDUCED** = reduzida.
> * **INCREASED** = aumentada.

***

> **Code**: PARTS\
> **Tipo**: `array<answer>`
>
> Campo usado para enviar as partes customizadas da bike.\
> **Abaixo contém um detalhamento sobre as partes customizadas.**

<details>

<summary>💡Detalhamento de partes customizadas</summary>

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

**Code:** PART-TYPE\
**Tipo:** `text`\
Pergunta usada para definir partes adicionais da bike.\
\
Os possíveis valores para esta pergunta são:

* **FRONT-DERAILLEUR** = Câmbio diantero
* **REAR-DERAILLEUR** = Câmbio transeiro
* **SEATPOST** = Canote
* **CLIP-PEDAL** = Clip pedal
* **COLOR** = Cor
* **HUB** = Cubos
* **BRAKE** = Freios
* **FORK** = Garfo
* **HANDLEBAR** = Guidão
* **STEM** = Mesa
* **PEDAL** = Pedal
* **CRANKSET** = Pedivela
* **TIRE** = Pneu
* **FRAME** = Quadro
* **WHEEL** = Roda
* **SADDLE** = Banco
* **FRONT-SHIFTER** = Trocador Dianteiro
* **REAR-SHIFTER** = Trocador Traseiro

***

**Code**: PART-BRAND\
**Tipo**: `text`

Pergunta usada para definir a marca da parte adicionada.

**Code**: PART-MODEL\
**Tipo**: `text`

Pergunta usada para definir o modelo da parte adicionada.

**Code**: PART-VALUE\
**Tipo**: `decimal`

Pergunta usada para definir o valor da parte adicionada.

</details>

> **Code**: PART-BIKE-AGREEMENT\
> **Tipo**: `boolean`\
> ❗ Caso tenha modificação (Parts) é necessário que essa pergunta seja true
>
> Pergunta usada para definir "**Entendimento e concordância das peças modificadas.**"\
> Se definida como true, indica que "**Estou ciente e de acordo que as peças modificadas deverão conter Nota Fiscal e/ou Cupom Fiscal, em nome do segurado. A não apresentação acarretará perda de direito.**"

***

> **Code**: COVERAGES\
> **Tipo**: `array<answer>`\
> ❗ Obrigatório que esteja incluído no array.
>
> Campo usado para as coberturas.\
> **Abaixo contém uma explicação detalhada das coberturas disponiveis.**

<details>

<summary>💡Detalhamento de coberturas</summary>

**❗É obrigatório o envio de uma das coberturas entre:**

* DAMAGE-COVERAGE
* THIEFT COVERAGE

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
                  ],
                  [
                     {
                        "code":"COVERAGE-TYPE",
                        "answer":"MOBILE-THEFT-COVERAGE"
                     }
                  ]
               ]
            }
         ]
      }
   ]
}
```

**Code**: COVERAGE-TYPE\
**Tipo**: `text`

Pergunta usada para definir o tipo de cobertura.\
\
Os possíveis valores para esta pergunta são:

* **DAMAGE-COVERAGE** = Cobertura a danos
* **THEFT-COVERAGE** = Cobertura a roubo
* **CIVIL-LIABILITY-COVERAGE** = Danos Materiais E/ou Corporais a Terceiros (RC)
* **ACCESSORIES-COVERAGE** = Acessórios
* **ELECTRICAL-DAMAGE-COVERAGE** = Danos elétricos
* **INTERNATIONAL-COVERAGE** = Cobertura internacional
* **MOBILE-THEFT-COVERAGE** = Celular/Smartwatch Roubo
  * Quando for MOBILE-THEFT-COVERAGE o MANUFACTURE-YEAR devera ser maior ou igual a 2 anos
  * O valor máximo da cobertura é de R$ 10.000,00 limitado a 30% do valor da bike.

***

**Code**: COVERAGE-LIMIT\
**Tipo**: `integer`

Pergunta usada para definir o limite de uma cobertura, caso uma delas sejam:

* CIVIL-LIABILITY-COVERAGE
* ACCESSORIES-COVERAGE

**Os possíveis valores para esta pergunta são:**\
**50** - enviar no mesmo array que contiver _**CIVIL-LIABILITY-COVERAGE**_\
**100** - enviar no mesmo array que contiver _**CIVIL-LIABILITY-COVERAGE**_\
**200** - enviar no mesmo array que contiver _**CIVIL-LIABILITY-COVERAGE**_\
**300** - enviar no mesmo array que contiver _**CIVIL-LIABILITY-COVERAGE**_\
**400** - enviar no mesmo array que contiver _**CIVIL-LIABILITY-COVERAGE**_\
**500** - enviar no mesmo array que contiver _**CIVIL-LIABILITY-COVERAGE**_\
**05** - enviar no mesmo array que contiver _**ACCESSORIES-COVERAGE**_\
**10** - enviar no mesmo array que contiver _**ACCESSORIES-COVERAGE**_



**Code**: COVERAGE-LIMIT-VALUE\
**Tipo**: `integer`\
❗ Obrigatório quando a cobertura for **MOBILE-THEFT-COVERAGE**

Pergunta usada para definir limite de cobertura.



</details>



> **Code**: RENT\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.\
> ❗ Atualmente a resposta dessa pergunta so é possivel como falsa, ela é recusada caso for usada para locações (true).
>
> Pergunta usada para definir se a bike será utilizada para locações.

***

> **Code**: INVOICE\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir se a bike possui ou não nota fiscal.

***

> **Code**: INVOICE-AGREEMENT\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array (se INVOICE for TRUE).
>
> Pergunta usada para definir "**Entendimento e concordância de solicitação de nota fiscal.**"\
> Se definida como true, indica que "**Estou ciente e de acordo que a nota fiscal e/ou cupom fiscal da bicicleta em nome do segurado, serão solicitados em caso de sinistro.**"

## Response

```json
{
    "item": {
        "quotationIdentifier": "210117cf-2a0b-4f2a-8a7f-04c301e9cf49",
        "quotationDocumentUrl":"",
        "status": "Draft",
        "pricing": [
            {
                "variantIdentifier": "423fcec9-2fb9-4c22-a14d-4ff3427974f6",
                "underwriting": {
                    "approved": true,
                    "evaluations": []
                },
                "price": {
                    "commission": 37.72,
                    "grievanceDiscount": 0.0,
                    "itemValue": 3000.0,
                    "netValue": 188.6,
                    "interestValue": 0.0,
                    "taxValue": 13.92,
                    "totalValue": 202.52,
                    "policyLimit": 3000.0,
                    "rates": [
                        {
                            "code": "DAMAGE-COVERAGE",
                            "description": "Danos à bike",
                            "limit": 3000.0,
                            "netValue": 49.63,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "Padrão",
                                "description": "15% dos prejuízos indenizáveis com o mínimo de R$ 500,00"
                            }
                        },
                        {
                            "code": "THEFT-COVERAGE",
                            "description": "Roubo e/ou furto qualificado",
                            "limit": 3000.0,
                            "netValue": 138.97,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "Padrão",
                                "description": "10% dos prejuízos indenizáveis com o mínimo de R$ 500,00"
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
                                    "identifier": "6360803f-2969-410a-be77-7a835a339c4f",
                                    "number": 1,
                                    "commissionValue": 37.72,
                                    "netValue": 188.6,
                                    "interestValue": 0.0,
                                    "taxValue": 13.92,
                                    "totalValue": 202.52,
                                    "installmentValue": 202.52,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 13.92,
                                    "dueDates": [
                                        "2023-05-30T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "1ba6df3d-68e4-45d2-8c97-504017fb2a14",
                                    "number": 2,
                                    "commissionValue": 37.72,
                                    "netValue": 188.6,
                                    "interestValue": 0.0,
                                    "taxValue": 13.92,
                                    "totalValue": 202.52,
                                    "installmentValue": 101.26,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 6.96,
                                    "dueDates": [
                                        "2023-05-30T00:00:00Z",
                                        "2023-06-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "5b3ed249-abb6-4060-b17a-08c2a7257b2b",
                                    "number": 3,
                                    "commissionValue": 37.72,
                                    "netValue": 188.6,
                                    "interestValue": 0.0,
                                    "taxValue": 13.92,
                                    "totalValue": 202.52,
                                    "installmentValue": 67.51,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 4.64,
                                    "dueDates": [
                                        "2023-05-30T00:00:00Z",
                                        "2023-06-01T12:00:00Z",
                                        "2023-07-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "ec4d3238-b4c4-4192-bc9e-4e8d3193aa09",
                                    "number": 4,
                                    "commissionValue": 37.72,
                                    "netValue": 188.6,
                                    "interestValue": 0.0,
                                    "taxValue": 13.92,
                                    "totalValue": 202.52,
                                    "installmentValue": 50.63,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 3.48,
                                    "dueDates": [
                                        "2023-05-30T00:00:00Z",
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
                                    "identifier": "251bb938-01c6-405a-b1af-1adb2dfec7e5",
                                    "number": 1,
                                    "commissionValue": 37.72,
                                    "netValue": 188.6,
                                    "interestValue": 0.0,
                                    "taxValue": 13.92,
                                    "totalValue": 202.52,
                                    "installmentValue": 202.52,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 13.92,
                                    "dueDates": [
                                        "2023-05-30T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "65f488a0-d5a6-4cb2-b4e2-5599010236eb",
                                    "number": 2,
                                    "commissionValue": 37.72,
                                    "netValue": 188.6,
                                    "interestValue": 0.0,
                                    "taxValue": 13.92,
                                    "totalValue": 202.52,
                                    "installmentValue": 101.26,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 6.96,
                                    "dueDates": [
                                        "2023-05-30T00:00:00Z",
                                        "2023-06-01T12:00:00Z"
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
    "executed": "2023-05-23T18:40:44.3053429Z"
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
