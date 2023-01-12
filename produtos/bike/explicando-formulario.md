# Explicando Formulário de bikes

> ❕O campo **items** dentro do **array de answer** tem como finalidade enviar perguntas mais específicas de _**bike**_. A seguir, você verá os valores que poderão/deverão estar inclusos nesse array.\
> Ao final dessa explicação, sua resposta de _items_ deverá parecer algo no json abaixo.

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

***

> **Code**: ITEMS\
> **Tipo**: `array<answer>`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta em formato de array de answer é usada para enviar perguntas mais específicas do produto em questão. Neste caso, o "Bike". Mais detalhes sobre essas perguntas a seguir, na documentação.

***

> **Code**: ITEM-IDENTIFIER\
> **Tipo**: `guid`\
> ❗ Obrigatório que esteja incluído no array (quando for na PROPOSTA).\
>
>
> Pergunta usada para definir o número de série da bike em questão. Máximo de 30 caracteres.

***

> **Code**: SERIAL-NUMBER\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir o número de série da bike em questão. Máximo de 30 caracteres.

***

> **Code**: ITEM-TYPE\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir o tipo da bike.\
> \
> Os valores possíveis para esta pergunta são:\
>
>
> * **TRADITIONAL =** bike tradicional.\
>
> * **ELETRIC =** bike elétrica (até 500W).

***

> **Code**: MANUFACTURE-YEAR\
> **Tipo**: `integer`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir o ano de fabricação da bike. Não cobrimos bikes fabricadas em 2017 ou antes.
>
> **❕São aceitos de 2018 ate 2022**\*\
>

***

> **Code**: MODEL\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir o modelo da bike.

***

> **Code**: COMPETITIONS\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir se a bike será utilizada em competições.

***

> **Code**: ORIGINAL-VALUE\
> **Tipo**: `decimal`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir o valor original da bike.

***

> **Code**: VALUE-AGREEMENT\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir "**Entendimento e concordância de valor aprovado.**". Se definida como true, indica que "**Estou de acordo com o valor aprovado pela Fairfax.**".

***

> **Code**: NEW\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir se a bike é nova ou não.\
>
>
> ❕Uma bike é considerada nova quando o segurado é o primeiro proprietário e a data de emissão da Nota Fiscal (NF) seja de até 60 dias da data atual.

***

> **Code**: BRAND\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Mesmo que Brand-Name, porém é necessário enviar essa resposta também.

***

> **Code**: BRAND-NAME\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir o nome da marca da bike.

***

> **Code**: FRAME-TYPE\
> **Tipo**: `text`\
> ❗ Obrigatorio que esteja incluído no array.\
>
>
> Pergunta usada para definir o tipo de quadro da bike.\
> \
> Os valores possíveis para esta pergunta são:\
>
>
> * **CARBON =** carbono.\
>
> * **ALUMINUM =** alumínio.\
>
> * **STEEL=** aço.

***

> **Code**: FRAME-TYPE-AGREEMENT\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir "**Entendimento e concordância do tipo de quadro.**" Se definida como true, indica que "**Estou ciente e de acordo que o material do quadro da Bicicleta acima indicado está correto. A informação incorreta acarretará perda do direito.**"

***

> **Code**: CLAIMS\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir se houve sinistros nos últimos 36 meses.\
> \
> Os valores possíveis para esta pergunta são:\
>
>
> * **0 =** nenhum.\
>
> * **1 =** sinistro.\
>
> * **2 =** sinistros.\
>
> * **3+ é declinado (não cobrimos).**

***

> **Code**: DEDUCTIBLE\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir o tipo de franquia.\
> \
> Os valores possíveis para esta pergunta são:\
>
>
> * **DEFAULT** = padrão.\
>
> * **REDUCED** = reduzida.\
>
> * **INCREASED** = aumentada.

***

> **Code**: PARTS\
> **Tipo**: `array<answer>`\
>
>
> Campo usado para enviar as partes customizadas da bike.\
> **Haverá uma seção nesta documentacão com explicação detalhada.**

***

> **Code**: PART-BIKE-AGREEMENT\
> **Tipo**: `boolean`\
> ❗ Caso tenha modificação (Parts) é necessário que essa pergunta seja true\
>
>
> Pergunta usada para definir "**Entendimento e concordância das peças modificadas.**"\
> Se definida como true, indica que "**Estou ciente e de acordo que as peças modificadas deverão conter Nota Fiscal e/ou Cupom Fiscal, em nome do segurado. A não apresentação acarretará perda de direito.**"

***

> **Code**: COVERAGES\
> **Tipo**: `array<answer>`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Campo usado para enviar as coberturas.\
> **Haverá uma seção nesta documentacão com explicação detalhada.**

***

> **Code**: RENT\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.\
> ❗ Atualmente a resposta dessa pergunta so é possivel como falsa, ela é recusada caso for usada para locações (true).\
>
>
> Pergunta usada para definir se a bike será utilizada para locações.

***

> **Code**: INVOICE\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.\
> ❗ É obrigatório que tenha nota fiscal (resposta true).\
>
>
> Pergunta usada para definir se a bike possui ou não nota fiscal.

***

> **Code**: INVOICE-AGREEMENT\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array (se INVOICE for TRUE).\
>
>
> Pergunta usada para definir "**Entendimento e concordância de solicitação de nota fiscal.**"\
> Se definida como true, indica que "**Estou ciente e de acordo que a nota fiscal e/ou cupom fiscal da bicicleta em nome do segurado, serão solicitados em caso de sinistro.**"

#### 💡 Explicando PARTS

> Como explicado anteriormente, o campo **parts** dentro do **array de items** tem como finalidade enviar partes customizadas da bike. A seguir, você verá os valores que poderão/deverão estar inclusos nesse array.

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

> **Code:** PART-TYPE\
> **Tipo:** `text`\
> Pergunta usada para definir partes adicionais da bike.\
> \
> Os possíveis valores para esta pergunta são:\
>
>
> * **FRONT-DERAILLEUR** = Câmbio diantero
> * **REAR-DERAILLEUR** = Câmbio transeiro
> * **SEATPOST** = Canote
> * **CLIP-PEDAL** = Clip pedal
> * **COLOR** = Cor
> * **HUB** = Cubos
> * **BRAKE** = Freios
> * **FORK** = Garfo
> * **HANDLEBAR** = Guidão
> * **STEM** = Tronco
> * **PEDAL** = Pedal
> * **CRANKSET** =
> * **TIRE** = Pneu
> * **FRAME** = Quadro
> * **WHEEL** = Roda
> * **SADDLE** = Banco
> * **FRONT-SHIFTER** = Trocador Dianteiro
> * **REAR-SHIFTER** = Trocador Traseiro

***

> **Code**: PART-BRAND\
> **Tipo**: `text`\
>
>
> Pergunta usada para definir a marca da parte adicionada.

***

> **Code**: PART-MODEL\
> **Tipo**: `text`\
>
>
> Pergunta usada para definir o modelo da parte adicionada.

***

> **Code**: PART-VALUE\
> **Tipo**: `decimal`\
>
>
> Pergunta usada para definir o valor da parte adicionada.

***

#### 💡 Explicando COVERAGES

> Como explicado anteriormente, o campo **coverages** dentro do **array de items** tem como finalidade enviar as coberturas.\
> A seguir, você verá os valores que poderão/deverão estar inclusos nesse array.\
>

❗**É obrigatório o envio de uma das coberturas entre:**

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
                  ]
               ]
            }
         ]
      }
   ]
}
```

> **Code**: COVERAGE-TYPE\
> **Tipo**: `text`\
>
>
> Pergunta usada para definir o tipo de cobertura.\
> \
> Os possíveis valores para esta pergunta são:\
>
>
> * **DAMAGE-COVERAGE** = Cobertura a danos
> * **THEFT-COVERAGE** = Cobertura a roubo
> * **CIVIL-LIABILITY-COVERAGE** = Danos Materiais E/ou Corporais a Terceiros (RC)
> * **ACCESSORIES-COVERAGE** = Acessórios
> * **ELECTRICAL-DAMAGE-COVERAGE** = Danos elétricos
> * **INTERNATIONAL-COVERAGE** = Cobertura internacional

***

> **Code**: COVERAGE-LIMIT\
> **Tipo**: `integer`\
>
>
> Pergunta usada para definir o limite de uma cobertura, caso uma delas sejam:\
>
>
> * CIVIL-LIABILITY-COVERAGE
> * ACCESSORIES-COVERAGE\
>
>
> **Os possíveis valores para esta pergunta são:**\
> **50** - enviar no mesmo array que contiver _**CIVIL-LIABILITY-COVERAGE**_\
> **100** - enviar no mesmo array que contiver _**CIVIL-LIABILITY-COVERAGE**_\
> **200** - enviar no mesmo array que contiver _**CIVIL-LIABILITY-COVERAGE**_\
> **300** - enviar no mesmo array que contiver _**CIVIL-LIABILITY-COVERAGE**_\
> **400** - enviar no mesmo array que contiver _**CIVIL-LIABILITY-COVERAGE**_\
> **500** - enviar no mesmo array que contiver _**CIVIL-LIABILITY-COVERAGE**_\
> **05** - enviar no mesmo array que contiver _**ACCESSORIES-COVERAGE**_\
> **10** - enviar no mesmo array que contiver _**ACCESSORIES-COVERAGE**_

#### Documents (passo obrigatório na proposta)

```json
"documents":[
      {
         "itemIdentifier":"92cc00b4-9ba6-4f50-bf5a-38b76ade9370",
         "files": [
                "data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/4gIoSUNDX1BST0ZJTEUAAQEAAAIYAAAAAAQwAABtbnRyUkdCIFhZWiAAAAAAAAAAAAAAAABhY3NwAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQAA9tYAAQAAAADTLQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAlkZXNjAAAA8AAAAHRyWFlaAAABZAAAABRnWFlaAAABeAAAABRiWFlaAAABjAAAABRyVFJDAAABoAAAAChnVFJDAAABoAAAAChiVFJDAAABoAAAACh3dHB0AAAByAAAABRjcHJ0AAAB3AAAADxtbHVjAAAAAAAAAAEAAAAMZW5VUwAAAFgAAAAcAHMAUgBHAEIAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAFhZWiAAAAAAAABvogAAOPUAAAOQWFlaIAAAAAAAAGKZAAC3hQAAGNpYWVogAAAAAAAAJKAAAA+EAAC2z3BhcmEAAAAAAAQAAAACZmYAAPKnAAANWQAAE9AAAApbAAAAAAAAAABYWVogAAAAAAAA9tYAAQAAAADTLW1sdWMAAAAAAAAAAQAAAAxlblVTAAAAIAAAABwARwBvAG8AZwBsAGUAIABJAG4AYwAuACAAMgAwADEANv/bAEMAAwICAgICAwICAgMDAwMEBgQEBAQECAYGBQYJCAoKCQgJCQoMDwwKCw4LCQkNEQ0ODxAQERAKDBITEhATDxAQEP/bAEMBAwMDBAMECAQECBALCQsQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEP/AABEIAZoCgAMBIgACEQEDEQH/xAAVAAEBAAAAAAAAAAAAAAAAAAAAB//EABQQAQAAAAAAAAAAAAAAAAAAAAD/xAAVAQEBAAAAAAAAAAAAAAAAAAAACP/EABQRAQAAAAAAAAAAAAAAAAAAAAD/2gAMAwEAAhEDEQA/AKwAkRWYAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAD//2Q==",
                "data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/4gIoSUNDX1BST0ZJTEUAAQEAAAIYAAAAAAQwAABtbnRyUkdCIFhZWiAAAAAAAAAAAAAAAABhY3NwAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQAA9tYAAQAAAADTLQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAlkZXNjAAAA8AAAAHRyWFlaAAABZAAAABRnWFlaAAABeAAAABRiWFlaAAABjAAAABRyVFJDAAABoAAAAChnVFJDAAABoAAAAChiVFJDAAABoAAAACh3dHB0AAAByAAAABRjcHJ0AAAB3AAAADxtbHVjAAAAAAAAAAEAAAAMZW5VUwAAAFgAAAAcAHMAUgBHAEIAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAFhZWiAAAAAAAABvogAAOPUAAAOQWFlaIAAAAAAAAGKZAAC3hQAAGNpYWVogAAAAAAAAJKAAAA+EAAC2z3BhcmEAAAAAAAQAAAACZmYAAPKnAAANWQAAE9AAAApbAAAAAAAAAABYWVogAAAAAAAA9tYAAQAAAADTLW1sdWMAAAAAAAAAAQAAAAxlblVTAAAAIAAAABwARwBvAG8AZwBsAGUAIABJAG4AYwAuACAAMgAwADEANv/bAEMAAwICAgICAwICAgMDAwMEBgQEBAQECAYGBQYJCAoKCQgJCQoMDwwKCw4LCQkNEQ0ODxAQERAKDBITEhATDxAQEP/bAEMBAwMDBAMECAQECBALCQsQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEP/AABEIAZoCgAMBIgACEQEDEQH/xAAVAAEBAAAAAAAAAAAAAAAAAAAAB//EABQQAQAAAAAAAAAAAAAAAAAAAAD/xAAVAQEBAAAAAAAAAAAAAAAAAAAACP/EABQRAQAAAAAAAAAAAAAAAAAAAAD/2gAMAwEAAhEDEQA/AKwAkRWYAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAD//2Q=="
            ]
      }
   ]
```

> **Field**: documents\
> **Type**: `array<document>`\
> ❗ Campo Obrigatório\
>
>
> Campo usado para enviar as fotos referentes a bike que está sendo cotada. A seguir, veremos também a modelagem de documents.

***

> **Field**: item Identifier\
> **Type**: `text`\
> ❗ Campo Obrigatório.\
>
>
> Campo usado para enviar um guid que será vinculado às fotos no array de files, **esse guid é retornado como variantIdentifier dentro do objeto de pricing ao obter o response quando se cria uma cotação.**

***

> **Field**: files\
> **Type**: `array<string>`\
> ❗ Campo Obrigatório. é necessário 2 ou mais fotos\
>
>
> Campo usado como resposta para enviar as fotos no formato de **base64**.
