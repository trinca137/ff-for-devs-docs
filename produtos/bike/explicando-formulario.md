> ❕ O campo **items** dentro do **array de answer** tem como finalidade enviar perguntas mais específicas do de *bike*. A seguir, você verá os valores que poderão/deverão estar inclusos nesse array.<br>
> Ao final dessa explicação, sua resposta de *items* deverá parecer algo no json abaixo.

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

------------------------------------------------------------------------

> **Code**: ITEMS </br>
> **Tipo**: ```array<answer>``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text><br>
> 
> Pergunta em formato de array de answer é usada para enviar perguntas mais específicas do produto em questão. Neste caso, o "Bike". Mais detalhes sobre essas perguntas a seguir, na documentação.

------------------------------------------------------------------------

> **Code**: ITEM-IDENTIFIER </br>
> **Tipo**: ```guid``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array (quando for na PROPOSTA). </text><br>
> 
> Pergunta usada para definir o número de série da bike em questão. Máximo de 30 caracteres.

------------------------------------------------------------------------

> **Code**: SERIAL-NUMBER </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
> 
> Pergunta usada para definir o número de série da bike em questão. Máximo de 30 caracteres.

------------------------------------------------------------------------

> **Code**: ITEM-TYPE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text> </br>
> 
> Pergunta usada para definir o tipo da bike.<br><br>
> Os valores possíveis para esta pergunta são: </br>
> 
>  - **TRADITIONAL =** bike tradicional.</br>
>  - **ELETRIC =** bike elétrica (até 500W).

------------------------------------------------------------------------

> **Code**: MANUFACTURE-YEAR </br>
> **Tipo**: ```integer``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
> 
> Pergunta usada para definir o ano de fabricação da bike. Não cobrimos bikes fabricadas em 2017 ou antes.
>
> **❕São aceitos de 2018 ate 2022*** </br>

------------------------------------------------------------------------

> **Code**: MODEL </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text><br>
> 
> Pergunta usada para definir o modelo da bike.

------------------------------------------------------------------------

> **Code**: COMPETITIONS </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
> 
> Pergunta usada para definir se a bike será utilizada em competições.

------------------------------------------------------------------------

> **Code**: ORIGINAL-VALUE </br>
> **Tipo**: ```decimal``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
> 
> Pergunta usada para definir o valor original da bike.

------------------------------------------------------------------------

> **Code**: VALUE-AGREEMENT </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
> 
> Pergunta usada para definir "**Entendimento e concordância de valor aprovado.**".
> Se definida como true, indica que "**Estou de acordo com o valor aprovado pela Fairfax.**".

------------------------------------------------------------------------

> **Code**: NEW </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
> 
> Pergunta usada para definir se a bike é nova ou não.<br>
> 
> <text class="definicao">❕Uma bike é considerada nova quando o segurado é o primeiro proprietário e a data de emissão da Nota Fiscal (NF) seja de até 60 dias da data atual.</text>

------------------------------------------------------------------------

> **Code**: BRAND </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text><br>
> 
> Mesmo que Brand-Name, porém é necessário enviar essa resposta também.

------------------------------------------------------------------------

> **Code**: BRAND-NAME </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text><br>
> 
> Pergunta usada para definir o nome da marca da bike.

------------------------------------------------------------------------

> **Code**: FRAME-TYPE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatorio que esteja incluído no array. </text><br>
> 
> Pergunta usada para definir o tipo de quadro da bike.<br><br>
> Os valores possíveis para esta pergunta são:<br>
> 
>  - **CARBON =** carbono. </br>
>  - **ALUMINUM =** alumínio. </br>
>  - **STEEL=** aço.

------------------------------------------------------------------------

> **Code**: FRAME-TYPE-AGREEMENT </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text><br>
> 
> Pergunta usada para definir "**Entendimento e concordância do tipo de quadro.**"
> Se definida como true, indica que "**Estou ciente e de acordo que o material do quadro da Bicicleta acima indicado está correto. A informação incorreta acarretará perda do direito.**"

------------------------------------------------------------------------

> **Code**: CLAIMS </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text><br>
> 
> Pergunta usada para definir se houve sinistros nos últimos 36 meses.<br><br>
> Os valores possíveis para esta pergunta são:<br>
> 
>    - **0 =** nenhum. </br>
>    - **1 =** sinistro. </br>
>    - **2 =** sinistros. </br>
>    - **3+ é declinado (não cobrimos).**

------------------------------------------------------------------------

> **Code**: DEDUCTIBLE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text><br>
> 
> Pergunta usada para definir o tipo de franquia.<br><br>
> Os valores possíveis para esta pergunta são:<br>
> 
>    - **DEFAULT** = padrão. </br>
>    - **REDUCED** = reduzida. </br>
>    - **INCREASED** = aumentada.

------------------------------------------------------------------------

> **Code**: PARTS </br>
> **Tipo**: ```array<answer>```<br>
> 
> Campo usado para enviar as partes customizadas da bike.<br>
> **Haverá uma seção nesta documentacão com explicação detalhada.** 

------------------------------------------------------------------------

> **Code**: PART-BIKE-AGREEMENT </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso">❗ Caso tenha modificação (Parts) é necessário que essa pergunta seja true </text><br>
> 
> Pergunta usada para definir "**Entendimento e concordância das peças modificadas.**"<br>
Se definida como true, indica que "**Estou ciente e de acordo que as peças modificadas deverão conter Nota Fiscal e/ou Cupom Fiscal, em nome do segurado. A não apresentação acarretará perda de direito.**"

------------------------------------------------------------------------

> **Code**: COVERAGES</br>
> **Tipo**: ```array<answer>``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
> 
> Campo usado para enviar as coberturas. <br>
> **Haverá uma seção nesta documentacão com explicação detalhada.** 

------------------------------------------------------------------------

> **Code**: RENT</br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
> <text class="aviso">❗ Atualmente a resposta dessa pergunta so é possivel como falsa, ela é recusada caso for usada para locações (true).</text><br>
> 
> Pergunta usada para definir se a bike será utilizada para locações.

------------------------------------------------------------------------

> **Code**: INVOICE </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
> <text class="aviso">❗ É obrigatório que tenha nota fiscal (resposta true).</text><br>
> 
> Pergunta usada para definir se a bike possui ou não nota fiscal.

------------------------------------------------------------------------

> **Code**: INVOICE-AGREEMENT </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array (se INVOICE for TRUE).</text><br>
> 
> Pergunta usada para definir "**Entendimento e concordância de solicitação de nota fiscal.**"<br>
> Se definida como true, indica que  "**Estou ciente e de acordo que a nota fiscal e/ou cupom fiscal da bicicleta em nome do segurado, serão solicitados em caso de sinistro.**"

### 💡 Explicando PARTS

> Como explicado anteriormente, o campo **parts** dentro do **array de items** tem como finalidade 
enviar partes customizadas da bike. A seguir, você verá os valores que poderão/deverão estar inclusos nesse array.

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

> **Code:** PART-TYPE </br>
> **Tipo:** ```text``` </br>
> Pergunta usada para definir partes adicionais da bike.<br><br>
> Os possíveis valores para esta pergunta são:<br>
> 
>    - **FRONT-DERAILLEUR** = Câmbio diantero
>    - **REAR-DERAILLEUR** = Câmbio transeiro
>    - **SEATPOST** = Canote
>    - **CLIP-PEDAL** = Clip pedal
>    - **COLOR** =  Cor
>    - **HUB** = Cubos
>    - **BRAKE** = Freios
>    - **FORK** = Garfo
>    - **HANDLEBAR** = Guidão
>    - **STEM** = Tronco
>    - **PEDAL** = Pedal
>    - **CRANKSET** =
>    - **TIRE** = Pneu
>    - **FRAME** = Quadro
>    - **WHEEL** = Roda
>    - **SADDLE** = Banco
>    - **FRONT-SHIFTER** = Trocador Dianteiro
>    - **REAR-SHIFTER** = Trocador Traseiro

------------------------------------------------------------------------

> **Code**: PART-BRAND<br>
> **Tipo**: ```text```<br>
> 
> Pergunta usada para definir a marca da parte adicionada.

------------------------------------------------------------------------

> **Code**: PART-MODEL<br>
> **Tipo**: ```text```<br>
> 
> Pergunta usada para definir o modelo da parte adicionada.

------------------------------------------------------------------------

> **Code**: PART-VALUE<br>
> **Tipo**: ```decimal```<br>
>
> Pergunta usada para definir o valor da parte adicionada.

------------------------------------------------------------------------

### 💡 Explicando COVERAGES

> Como explicado anteriormente, o campo **coverages** dentro do **array de items** tem como 
finalidade enviar as coberturas. <br>
> A seguir, você verá os valores que poderão/deverão estar inclusos nesse array.<br>

<text> ❗**É obrigatório o envio de uma das coberturas entre:** </text>

- DAMAGE-COVERAGE
- THIEFT COVERAGE


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

> **Code**: COVERAGE-TYPE <br>
> **Tipo**: ```text``` <br>
> 
> Pergunta usada para definir o tipo de cobertura.<br><br>
> Os possíveis valores para esta pergunta são:<br>
>
>   - **DAMAGE-COVERAGE** = Cobertura a danos
>   - **THEFT-COVERAGE** = Cobertura a roubo
>   - **CIVIL-LIABILITY-COVERAGE** =  Danos Materiais E/ou Corporais a Terceiros (RC)
>   - **ACCESSORIES-COVERAGE** =  Acessórios
>   - **ELECTRICAL-DAMAGE-COVERAGE** = Danos elétricos
>   - **INTERNATIONAL-COVERAGE** = Cobertura internacional

------------------------------------------------------------------------

> **Code**: COVERAGE-LIMIT <br>
> **Tipo**: ```integer``` <br>
> 
> Pergunta usada para definir o limite de uma cobertura, caso uma delas sejam: <br>
>
>  - CIVIL-LIABILITY-COVERAGE
>  - ACCESSORIES-COVERAGE <br>
> 
> **Os possíveis valores para esta pergunta são:** <br>
> **50** - enviar no mesmo array que contiver ***CIVIL-LIABILITY-COVERAGE*** <br>
> **100** - enviar no mesmo array que contiver ***CIVIL-LIABILITY-COVERAGE*** <br>
> **200** - enviar no mesmo array que contiver ***CIVIL-LIABILITY-COVERAGE*** <br>
> **300** - enviar no mesmo array que contiver ***CIVIL-LIABILITY-COVERAGE*** <br>
> **400** - enviar no mesmo array que contiver ***CIVIL-LIABILITY-COVERAGE*** <br>
> **500** - enviar no mesmo array que contiver ***CIVIL-LIABILITY-COVERAGE*** <br>
> **05** - enviar no mesmo array que contiver ***ACCESSORIES-COVERAGE*** <br>
> **10** - enviar no mesmo array que contiver ***ACCESSORIES-COVERAGE***

### Documents (passo obrigatório na proposta)

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

> **Field**: documents <br>
> **Type**: ```array<document>```<br>
> <text class="aviso">❗ Campo Obrigatório</text><br>
> 
> Campo usado para enviar as fotos referentes a bike que está sendo cotada. A seguir, veremos também a modelagem de documents.

--------------------------------------------------------------------------

> **Field**: item Identifier <br>
> **Type**: ```text``` <br>
> <text class="aviso">❗ Campo Obrigatório. </text><br>
> 
> Campo usado para enviar um guid que será vinculado às fotos no array de files, **esse guid é retornado como variantIdentifier dentro do objeto de pricing ao obter o response quando se cria uma cotação.**

--------------------------------------------------------------------------

> **Field**: files <br>
> **Type**: ```array<string>``` <br>
> <text class="aviso">❗ Campo Obrigatório. é necessário 2 ou mais fotos </text><br>
>
> Campo usado como resposta para enviar as fotos no formato de **base64**.