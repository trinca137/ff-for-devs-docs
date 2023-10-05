# Criar Cotação

{% hint style="info" %}
Para equipamentos de contrução civil, possuimos algumas diferenças sobre os outros produtos.\
\
Para motivo de alerta, é necessário selecionar o método de pagamento que vem a partir do VariantIdentifier "000...000" pois é onde é agrupado o valor de todos equipamentos.
{% endhint %}

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
    "operationCode": "CONSTRUCTION-EQUIPMENT-MULTIPLE-PERIL-PARTNER",
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
    "operationCode": "CONSTRUCTION-EQUIPMENT-MULTIPLE-PERIL-PARTNER",
    "registerNumber": "100000",
    "answers": [
        {
            "code": "MODALITY",
            "answer": "CONSTRUCTION-EQUIPMENT-MULTIPLE-PERIL"
        },
        {
            "code": "START-VIGENCY-DATE",
            "answer": "2023-04-27T03:00:00.000Z"
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
            "code": "COMMISSION",
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
                        "code": "ITEM-IDENTIFIER",
                        "answer": "3aabec8a-45ca-433a-9954-e6ae7853d299"
                    },
                    {
                        "code": "ITEM-TYPE",
                        "answer": "AIR-COMPRESSOR"
                    },
                    {
                        "code": "BRAND",
                        "answer": "marca"
                    },
                    {
                        "code": "MODEL",
                        "answer": "modelo"
                    },
                    {
                        "code": "SERIAL-NUMBER",
                        "answer": "12378"
                    },
                    {
                        "code": "ORIGIN",
                        "answer": "IMPORTED"
                    },
                    {
                        "code": "EMISSION-DATE",
                        "answer": "2023/04/28"
                    },
                    {
                        "code": "INVOICE-NUMBER",
                        "answer": "45207"
                    },
                    {
                        "code": "MANUFACTURE-YEAR",
                        "answer": 2023
                    },
                    {
                        "code": "ITEM-VALUE",
                        "answer": "R$ 1000.000,00"
                    },
                    {
                        "code": "TYPE-USE",
                        "answer": "LOCATIONS"
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
                                    "answer": "R$ 1000.000,00"
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "THEFT-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 1000.000,00"
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
	"operationCode": "CONSTRUCTION-EQUIPMENT-MULTIPLE-PERIL-PARTNER",
	"registerNumber": "100000",
	"answers":[],
}
```

> **Field**: OperationCode\
> **Tipo**: `text`\
> ❗ Campo Obrigatório.
>
> Campo usado para definir qual produto está sendo cotado.



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



> **Code**: ITEM-IDENTIFIER\
> **Type**: `guid`\
> ❗ Obrigatório que esteja incluído no array em cada equipamento com um novo.\
> Pergunta para separar cada equipamento por um identificador.



> **Code**: ITEM-TYPE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Qual o tipo do equipamento.

<details>

<summary>Tipos de equipamentos (os codigos estão da maneira que devem ser enviados)</summary>

**PILE-DRIVER** = Bate estaca

**CONCRETE-MIXERS** = Betoneiras

**BOMB-SPEAR** = Bomba Lança

**SUCTION-BOOSTER-PUMPS** = Bombas de Sucção ou Recalque

**CRUSHER** = Britador

**BULLDOZERS** = Bulldozers

**WHEEL-LOADER** = Carregadeira Sobre Rodas

**SOIL-COMPACTOR** = Compactador de Solo

**AIR-COMPRESSOR** = Compressor de Ar

**EARTHMOVER** = Earthmover

**CONSTRUCTION-ELEVATOR** = Elevador de Obras

**SCISSOR-LIFT-WITH-WHEELS** = Elevador de Tesoura (com rodas)

**PANTOGRAPHIC-HYDRAULIC-ELEVATOR** = Elevador Hidráulico Pantográfico

**FORK-LIFT** = Empilhadeira

**EXCAVATOR-MACHINE** = Escavadeira

**GENERATOR** = Gerador

**WINCHES-EXCLUSIVELY-CONSTRUCTION** = Guinchos (exclusivamente em canteiros de obras)

**TELESCOPIC-MANIPULATOR** = Manipulador de Telescópio

**HYDRAULIC-HAMMER** = Martelo Hidráulico

**VIBRATING-HAMMER** = Martelo Vibratório

**SMALL-LOADER** = Mini Carregadeira

**SMALL-EXCAVATOR** = Mini Escavadeira

**SMALL-BACKHOE-LOADER** = Mini Retroescavedeira

**GRADER** = Motoniveladora

**WHEEL-SHOVER** = Pá Carregadeira

**SHEEP-FEET** = Pés de Carneiro

**AERIAL-WORK-PLATFORM** = Plataforma Aérea de Trabalho

**LIFTING-PLATFORM** = Plataforma Elevatória

**BACKHOE** = Retroescavadeira

**ROAD-ROLLER** = Rolo Compactador

**BREAKER** = Rompedor

**SCRAPERS** = Scrapers

**LIGHTING-TOWER** = Torre de Iluminação

**FIXED-CONVEYORS** = Transportadores Fixos (de correia, esteira, rosca sem fim o caçambas)

**TRACTOR** = Trator

**ASPHALT-PLANT** = Usina de Asfalto

**VIBRATORS-CONCRETE** = Vibradores para Concreto

**ASPHALT-PAVER** = Vibroacabadora de Asfalto

</details>

***

> **Code**: EQUIPMENT-NEW\
> **Type**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.\
> Para sabermos se o equipamento é novo.
>
> \
> Para este item, sempre que for **TRUE**, a pergunta de [MANUFACTURE-YEAR](cotacao.md#detalhamento-de-regra-para-manufacture-year) terá uma regra especifica.

<details>

<summary>Caso a pergunta de equipamento novo seja TRUE:</summary>

Se a pergunta de equipamento novo for **TRUE,** será necessário enviar as duas perguntas abaixo:

**Code**: EMISSION-DATE\
**Type**: `date`

❗ Obrigatório que esteja incluído no array.

Usada para sabermos a data de emissão da nota fiscal.\
\
❗ Só é aceito equipamentos com nota fiscal emitida em até 60 dias.

***

**Code**: INVOICE-NUMBER\
**Type**: `text`

❗ Obrigatório que esteja incluído no array.

Usada para sabermos o número da nota fiscal.

</details>

***

> **Code**: BRAND\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Qual a marca do equipamento.

***

> **Code**: SERIAL-NUMBER\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Usada para definir o número de série do equipamento.

***

> **Code**: ORIGIN\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Usada para saber se o equipamento foi produzido em território nacional ou no exterior.\
> \
> Os possíveis valores para serem enviados são:
>
> * **NATIONAL** = Nacional
> * **IMPORTED** = Importado

***

> **Code**: BENEFIT-CLAUSE\
> **Type**: `boolean`
>
> ❗ Obrigatório que esteja incluído no array.
>
> Usada para definir responsável que sera indenizado em caso de sinistro no equipamentos.

<details>

<summary>Caso BENEFIT-CLAUSE seja enviado TRUE</summary>

Se for **TRUE,** é necessário enviar as duas perguntas abaixo:\
\
**Code**: DOCUMENT-NUMBER\
**Type**: `string`

❗ Obrigatório que esteja incluído no array.

Usada para definir número de CNPJ que sera indenizado.



**Code**: INSTITUTION-NAME\
**Type**: `string`

❗ Obrigatório que esteja incluído no array.

Usada para definir o nome da instituição financeira que sera indenizado.

</details>

***



> **Code**: MANUFACTURE-YEAR\
> **Type**: `int`\
> ❗ Obrigatório que esteja incluído no array.
>
> Usada para informar o ano que o equipamento foi feito.

<details>

<summary>Detalhamento de regra para MANUFACTURE-YEAR</summary>

**Caso TRUE:** Se a a pergunta de <mark style="color:yellow;">**EQUIPMENT-NEW**</mark> for **TRUE:**

&#x20;Será permitidos equipamentos com fabricação do ano atual ou anterior.\
\
**Caso FALSE:**

&#x20;Será permitidos equipamentos com fabricação de até **6 anos** a partir do ano atual.

</details>

***

> **Code**: ITEM-VALUE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir o valor do equipamento.\
> \
> ❗São aceitos equipamentos com valor máximo de ate RS 1.000.000,00 (um milhão). &#x20;

***

> **Code**: TYPE-USE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir o uso do equipamento.\
>
>
> Os possíveis valores para serem enviados são:
>
> * **PERSONAL** = Uso pessoal
> * **LOCATIONS** = Locação para terceiros

***

> **Code**: COVERAGES\
> **Type**: `array<array<answer>>`\
> ❗ Obrigatório que esteja incluído no array.\
> Campo para definir as coberturas para o equipamento (cada equipamento tem suas proprias coberturas).

{% hint style="info" %}
Segue um exemplo como fica o array de items com o coverages (algumas perguntas/respostas foram apagadas para ficar mais limpo o exemplo com os coverages).\
\
Abaixo do json de exemplo, vai ter explicando as perguntas dentro do coverages.
{% endhint %}

```json
{
            "code": "ITEMS",
            "answer": [
                [
                    {
                        "code": "ITEM-IDENTIFIER",
                        "answer": "3aabec8a-45ca-433a-9954-e6ae7853d299"
                    }
                    .
                    .
                    .
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
                ]
```

{% hint style="info" %}
Como podemos perceber, dentro do array de coverages, temos um outro array com duas perguntas que se repetem por cobertura adicionada.
{% endhint %}

***

> **Code**: COVERAGE-TYPE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array. (Cobertura básica é obrigatoria para qualquer equipamento)\
>
>
> Tipo de coberturas permitidos:

<details>

<summary>Coberturas</summary>

* **DAMAGE-COVERAGE -** Cobertura Básica

<!---->

* **THEFT-COVERAGE -** Roubo e/ou furto qualificado

<!---->

* **OPERATIONS-WATER-COVERAGE -** Operações em Proximidade de Água

<!---->

* **ELECTRICAL-DAMAGE-COVERAGE -** Danos Elétricos

<!---->

* **CIVIL-LIABILITY-COVERAGE -** Responsabilidade Civil Equipamentos

<!---->

* **LOSS-RENT-COVERAGE -** Perda de Aluguel

<!---->

* **PAYMENT-THIRD-PARTIES-COVERAGE -** Pagamento de Aluguel a Terceiros

</details>

***

> **Code**: COVERAGE-LIMIT-VALUE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para o valor da cobertura selecionada.\
>
>
> Para cada cobertura temos um limite de valor, segue limite para as respectivas cobeturas.

<details>

<summary>Limites de valores das coberturas selecionadas</summary>

* **DAMAGE-COVERAGE -** Sempre cobre 100% do valor do equipamento

<!---->

* **THEFT-COVERAGE -** Sempre cobre 100% do valor do equipamento

<!---->

* **OPERATIONS-WATER-COVERAGE -** Sempre cobre 100% do valor do equipamento

<!---->

* **ELECTRICAL-DAMAGE-COVERAGE -** Cobre no máximo 70% do valor do equipamento

<!---->

* **CIVIL-LIABILITY-COVERAGE -** Cobre no máximo 50% do valor do equipamento

<!---->

* **LOSS-RENT-COVERAGE -** Cobre 30% do valor do equipamento, se os 30% passar dos 100mil, cobre o limite de 100mil

<!---->

* **PAYMENT-THIRD-PARTIES-COVERAGE -** Cobre 30% do valor do equipamento, se os 30% passar dos 100mil, cobre o limite de 100mil

</details>

## Response

```json
{
    "item": {
        "quotationIdentifier": "fd553149-0a95-4c5b-b94d-e9377d099cf3",
        "quotationDocumentUrl":"",
        "status": "Draft",
        "pricing": [
            {
                "variantIdentifier": "3aabec8a-45ca-433a-9954-e6ae7853d299",
                "underwriting": {
                    "approved": true,
                    "evaluations": []
                },
                "price": {
                    "commission": 1964.84,
                    "grievanceDiscount": 0.0,
                    "itemValue": 1000000.0,
                    "netValue": 9824.21,
                    "interestValue": 0.0,
                    "taxValue": 725.03,
                    "totalValue": 10549.24,
                    "policyLimit": 1060000.0,
                    "rates": [
                        {
                            "code": "DAMAGE-COVERAGE",
                            "description": "Cobertura Básica",
                            "limit": 1000000.0,
                            "netValue": 6719.57,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento"
                            }
                        },
                        {
                            "code": "THEFT-COVERAGE",
                            "description": "Roubo e/ou furto qualificado",
                            "limit": 1000000.0,
                            "netValue": 2728.69,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "15% dos prejuízos indenizáveis com o mínimo de 2,5% do valor do equipamento"
                            }
                        },
                        {
                            "code": "ELECTRICAL-DAMAGE-COVERAGE",
                            "description": "Danos elétricos",
                            "limit": 70000.0,
                            "netValue": 212.23,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento"
                            }
                        },
                        {
                            "code": "LOSS-RENT-COVERAGE",
                            "description": "Perda de Aluguel",
                            "limit": 30000.0,
                            "netValue": 81.86,
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
                            "netValue": 81.86,
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
                                    "identifier": "f14a0bfa-4bb3-4650-97df-9a2ccbbd7f4c",
                                    "number": 1,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 10549.24,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 725.03,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "22fd848b-b3dc-481b-9d6a-e9b51a44e525",
                                    "number": 2,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 5274.62,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 362.52,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "22fe57bf-996e-4c8a-8500-7c0b4b53e62b",
                                    "number": 3,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 3516.41,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 241.68,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "79d8da7a-fb6f-4333-8d6c-c625012bd469",
                                    "number": 4,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 2637.31,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 181.26,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "738da76b-b370-4a33-add0-11f6b71cc621",
                                    "number": 5,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 2109.85,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 145.01,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "1c2f4934-2cf3-49d1-91ec-83567a4feb2d",
                                    "number": 6,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1758.21,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 120.84,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "f8c9522d-8c96-4631-a364-3a0e64eba9c5",
                                    "number": 7,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1507.03,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 103.58,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "9d5f6724-7bbe-4bf4-b47c-8745585f0d1e",
                                    "number": 8,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1318.66,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 90.63,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
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
                                    "identifier": "7c4857fe-2459-4b64-9343-44a872a5a0e2",
                                    "number": 9,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1172.14,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 80.56,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
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
                                    "identifier": "f1915552-a7a7-4dd1-9cee-d54c0a061271",
                                    "number": 10,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1054.92,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 72.5,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
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
                                }
                            ]
                        },
                        {
                            "paymentMethod": "Ticket",
                            "paymentType": "Ticket",
                            "installments": [
                                {
                                    "identifier": "80f592dc-162d-4eba-a98f-25751e9da9e9",
                                    "number": 1,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 10549.24,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 725.03,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "668c687b-5e57-4003-aa6d-eeb38ebdc1c3",
                                    "number": 2,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 5274.62,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 362.52,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "166f90eb-d47b-4bfe-9294-6b8b51998d52",
                                    "number": 3,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 3516.41,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 241.68,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "e87bbb03-13ce-4698-acbf-3008755b117f",
                                    "number": 4,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 2637.31,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 181.26,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "88060f40-70c4-4c46-9b56-bf1fdbd9c612",
                                    "number": 5,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 2109.85,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 145.01,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "5d857030-9c6f-42a7-bb11-b97f2abbc3fd",
                                    "number": 6,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1758.21,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 120.84,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z"
                                    ]
                                }
                            ]
                        }
                    ]
                }
            },
            {
                "variantIdentifier": "00000000-0000-0000-0000-000000000000",
                "price": {
                    "commission": 1964.84,
                    "grievanceDiscount": 0.0,
                    "netValue": 9824.21,
                    "interestValue": 0.0,
                    "taxValue": 725.03,
                    "totalValue": 10549.24,
                    "policyLimit": 1060000.0,
                    "rates": [
                        {
                            "code": "DAMAGE-COVERAGE",
                            "description": "Danos à bike",
                            "limit": 1000000.0,
                            "netValue": 6719.57,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento"
                            }
                        },
                        {
                            "code": "THEFT-COVERAGE",
                            "description": "Roubo e/ou furto qualificado",
                            "limit": 1000000.0,
                            "netValue": 2728.69,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "15% dos prejuízos indenizáveis com o mínimo de 2,5% do valor do equipamento"
                            }
                        },
                        {
                            "code": "ELECTRICAL-DAMAGE-COVERAGE",
                            "description": "Danos elétricos",
                            "limit": 70000.0,
                            "netValue": 212.23,
                            "deductible": {
                                "code": "DEFAULT",
                                "text": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento",
                                "description": "10% dos prejuízos indenizáveis com o mínimo de 1,5% do valor do equipamento"
                            }
                        },
                        {
                            "code": "LOSS-RENT-COVERAGE",
                            "description": "Perda de Aluguel",
                            "limit": 30000.0,
                            "netValue": 81.86,
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
                            "netValue": 81.86,
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
                                    "identifier": "d2da28ca-61f9-4000-918c-f936862b5454",
                                    "number": 1,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 10549.24,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 725.03,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "c6468fe2-c8b4-4aea-8da4-82cb311e7ef0",
                                    "number": 2,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 5274.62,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 362.52,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "ef5cadff-1152-4ca3-b0ca-49253ff22601",
                                    "number": 3,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 3516.41,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 241.68,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "e61e6f1b-7901-4933-b66e-fd0c40db024a",
                                    "number": 4,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 2637.31,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 181.26,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "9562b1dc-4ab7-4008-a69a-a19d81577995",
                                    "number": 5,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 2109.85,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 145.01,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "2f7954dc-e61f-4ac2-8054-e2464a19d493",
                                    "number": 6,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1758.21,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 120.84,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "e0977305-63f6-4b83-9f03-38c8f13764b5",
                                    "number": 7,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1507.03,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 103.58,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z",
                                        "2023-12-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "53f77cae-0098-4260-bbe4-a7e837d835ab",
                                    "number": 8,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1318.66,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 90.63,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
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
                                    "identifier": "7968a66b-b9ed-4f78-9ee7-0dd3c03e7e23",
                                    "number": 9,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1172.14,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 80.56,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
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
                                    "identifier": "c5176b03-c0b1-443d-b57f-e58c90027789",
                                    "number": 10,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1054.92,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 72.5,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
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
                                }
                            ]
                        },
                        {
                            "paymentMethod": "Ticket",
                            "paymentType": "Ticket",
                            "installments": [
                                {
                                    "identifier": "cabcc32c-18cd-4f18-b742-502f68e07e02",
                                    "number": 1,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 10549.24,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 725.03,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "9d4c85c8-9891-40b8-9085-f18ed3da0ff4",
                                    "number": 2,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 5274.62,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 362.52,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "d16c6a49-32d8-40fe-ba8d-a32696062fa5",
                                    "number": 3,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 3516.41,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 241.68,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "e2ec4a20-dd46-4224-9100-69d44b8ae24e",
                                    "number": 4,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 2637.31,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 181.26,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "3994139b-0e1d-425b-b91b-629b198159ba",
                                    "number": 5,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 2109.85,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 145.01,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "478d4108-2f6a-4a7d-a362-77af3c592d0c",
                                    "number": 6,
                                    "commissionValue": 1964.84,
                                    "netValue": 9824.21,
                                    "interestValue": 0.0,
                                    "taxValue": 725.03,
                                    "totalValue": 10549.24,
                                    "installmentValue": 1758.21,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 120.84,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z",
                                        "2023-11-01T12:00:00Z"
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
    "executed": "2023-05-25T20:52:13.2584543Z"
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
> Nome da franquia atrelada a cobertura (para RD so existem a franquia de "Default" para as coberturas).

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
