


>**Field**: documents <br>
>**Type**: ```array<document>```<br>
> <text class="aviso">❗ Campo obrigatorio </text><br>
> 
> Campo usado para enviar as fotos referentes a bike que está sendo cotada. A
seguir, veremos também a modelagem de document.

---------------------------------------------------------------------------------

### Document model

```json

{
	"itemIdentifier":"92cc00b4-9ba6-4f50-bf5a-38b76ade9370",
	"files":[]
}
```


>**Field**: **itemIdentifier** <br>
>**Type**: ```text``` <br>
> <text class="aviso">❗ Campo obrigatorio </text><br>
> 
>Campo usado para mandar um guid que será vinculado às fotos no array de **files, esse guid é retornado com variantIdentifier dentro do objeto de pricing ao obter o response quando se cria uma cotação.**

--------------------------------------------------------------------------


>**Field**: files <br>
>**Type**: ```array<string>``` <br>
><text class="aviso"> ❗ Campo obrigatorio </text><br>

>Campo usado como resposta para enviar as fotos no formato de **base64**.

-------------------------------------------------------------------------



> **Code**: ITEMS </br>
> **Tipo**: ```array<answer>``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text>
> 
> Pergunta em formato de array de answer é usada para enviar perguntas mais específicas do produto em questão. Neste caso, o "Bike". Mais detalhes sobre essas perguntas a seguir, na documentação.

-------------------------------------------------------------------------------------------

> ❕ Como explicado anteriormente, o campo **items** dentro do **array de answer** tem como finalidade enviar perguntas mais específicas do produto que está sendo cotado (Bike). A seguir, você verá os valores que poderão/deverão estar inclusos nesse array.

```json
{
    "operationCode": "BIKE-MULTIPLE-PERIL-PARTNER",
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
            "code": "ITEMS",
            "answer": [
                {
                     {
                        "code": "SERIAL-NUMBER",
                        "answer": "15"
                     },
                     {
                        "code": "ITEM-TYPE",
                        "answer": "TRADITIONAL"
                     },
                }
            ]
        }
    ]
}
```


> **Code**: SERIAL-NUMBER </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text>
> 
> Pergunta usada para definir o número de série da bike em questão. Máximo de 30 caracteres

------------------------------------------------------------------------

> **Code**: ITEM-TYPE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> Pergunta usada para definir o tipo da bike. Os valores possíveis para esta pergunta são: </br>
> 
>  - **TRADITIONAL =** Bike tradicional </br>
>  - **ELETRIC =** Bike elétrica (Elétrica (até 500W))

------------------------------------------------------------------------

> **Code**: MANUFACTURE-YEAR </br>
> **Tipo**: ```integer``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array.</text>
> 
> Pergunta usada para definir o ano de fabricação da bike. Não cobrimos bikes fabricadas em 2017 ou antes.
>
> **❕São aceitos de 2018 ate 2022*** </br>

------------------------------------------------------------------------

> **Code**: MODEL </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text>
> 
> Pergunta usada para definir o modelo da bike.

------------------------------------------------------------------------

> **Code**: COMPETITIONS </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array.</text>
> 
> Pergunta usada para definir se a bike será utilizada em competições.

------------------------------------------------------------------------

> **Code**: ORIGINAL-VALUE </br>
> **Tipo**: ```decimal``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array.</text>
> 
> Pergunta usada para definir o valor original da bike.

------------------------------------------------------------------------

> **Code**: VALUE-AGREEMENT </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array.</text>
> 
> Pergunta usada para definir "**Entendimento e concordância de valor aprovado.**".
> Se definida como true, indica que "**Estou de acordo com o valor aprovado pela Fairfax.**".

------------------------------------------------------------------------

> **Code**: NEW </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array.</text>
> 
> Pergunta usada para definir se a bike é nova ou não.
> 
> ❕Uma bike é considerada nova quando o segurado é o primeiro proprietário e a data de emissão da Nota Fiscal (NF) seja de até 60 dias da data atual.

------------------------------------------------------------------------

> **Code**: BRAND-NAME </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array. </text>
> 
> Pergunta usada para definir o nome da marca da bike.

------------------------------------------------------------------------

> **Code**: FRAME-TYPE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatorio que esteja incluido no array. </text>
> 
> Pergunta usada para definir o tipo de quadro da bike. Os valores possíveis para esta pergunta são:
> 
>  - **CARBON =** carbono </br>
>  - **ALUMINUM =** aluminio </br>
>  - **STEEL=** aço

------------------------------------------------------------------------

> **Code**: FRAME-TYPE-AGREEMENT </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array. </text>
> 
> Pergunta usada para definir "**Entendimento e concordância do tipo de quadro.**"
> Se definida como true, indica que "**Estou ciente e de acordo que o material do quadro da Bicicleta acima indicado está correto. A informação incorreta acarretará perda do direito.**"

------------------------------------------------------------------------

> **Code**: CLAIMS </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array. </text>
> 
> Pergunta usada para definir se houve sinistros nos últimos 36 meses. Os valores possíveis para esta pergunta são:
> 
>    - **0 =** nenhum </br>
>    - **1 =** sinistro </br>
>    - **2 =** sinistros </br>
>    - **3 ou mais é declinado (não cobrimos)**

------------------------------------------------------------------------

> **Code**: DEDUCTIBLE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text>
> 
> Pergunta usada para definir o tipo de franquia. Os valores possíveis para esta pergunta são:
> 
>    - DEFAULT **= padrao** </br>
>    - REDUCED  **= reduzida** </br>
>    - INCREASED **= aumentada** </br>

------------------------------------------------------------------------

> **Code**: PART-BIKE-AGREEMENT </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text>
> 
> Pergunta usada para definir "**Entendimento e concordância das peças modificadas.**"
Se definida como true, indica que "**Estou ciente e de acordo que as peças modificadas deverão conter Nota Fiscal e/ou Cupom Fiscal, em nome do segurado. A não apresentação acarretará perda de direito.**"

------------------------------------------------------------------------

> **Code**: PARTS </br>
> **Tipo**: ```array<answer>```
> 
> Campo usado para enviar as partes customizadas da bike. **Haverá uma seção nesta documentacão com explicação detalhada.** 

------------------------------------------------------------------------

> **Code**: COVERAGES</br>
> **Tipo**: ```array<answer>``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array</text>
> 
> Campo usado para enviar as coberturas. **Haverá uma seção nesta documentacão com explicação detalhada.** 

------------------------------------------------------------------------

> **Code**: RENT</br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array</text>
> 
> Pergunta usada para definir se a bike será utilizada para locações.

------------------------------------------------------------------------

> **Code**: INVOICE </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array.</text>
> 
> Pergunta usada para definir se a bike possui ou não nota fiscal.

------------------------------------------------------------------------

> **Code**: INVOICE-AGREEMENT </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso"> Obrigatório que esteja incluido no array (se INVOICE == TRUE)</text>
> 
> Pergunta usada para definir "**Entendimento e concordância de solicitação de nota fiscal.**"
> Se definida como true, indica que  "**Estou ciente e de acordo que a nota fiscal e/ou cupom fiscal da bicicleta em nome do segurado, serão solicitados em caso de sinistro.**"


<br>
<br>


### 💡 Explicando PARTS

> Como explicado anteriormente, o campo **parts** dentro do **array de items** tem como finalidade 
enviar partes customizadas da bike. A seguir, você verá os valores que poderão/deverão estar inclusos nesse array.
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


> **Code:** PART-TYPE </br>
> **Tipo:** ```text``` </br>
> Pergunta usada para definir partes adicionais da bike. Os possíveis valores para esta pergunta são:
> 
>    - **FRONT-DERAILLEUR =** Câmbio diantero
>    - **REAR-DERAILLEUR =** Câmbio transeiro
>    - **SEATPOST =** Canote
>    - **SEATPOST-BRAND =**
>    - **CLIP-PEDAL =** Clip pedal
>    - **COLOR =**  Cor
>    - **HUB =** Cubos
>    - **BRAKE =** Freios
>    - **FORK =** Garfo
>    - **HANDLEBAR =** Guidão
>    - **STEM =** Tronco
>    - **PEDAL =** Pedal
>    - **CRANKSET =**
>    - **TIRE =** Pneu
>    - **FRAME =** Quadro
>    - **WHEEL =** Roda
>    - **SADDLE =** Banco
>    - **FRONT-SHIFTER =**
>    - **REAR-SHIFTER =**

------------------------------------------------------------------------

> **Code**: PART-BRAND<br>
> **Tipo**: ```text```<br>
> 
> Pergunta usada para definir a marca da parte.

------------------------------------------------------------------------

> **Code**: PART-MODEL<br>
> **Tipo**: ```text```<br>
> 
> Pergunta usada para definir o modelo da parte.

------------------------------------------------------------------------

**Code**: PART-VALUE<br>
**Tipo**: ```decimal```<br>
> Pergunta usada para definir o valor da parte.

------------------------------------------------------------------------

### 💡 Explicando COVERAGES

> Como explicado anteriormente, o campo **coverages** dentro do **array de items** tem como 
finalidade enviar as coberturas. A seguir, você verá os valores que poderão/deverão estar inclusos nesse array.
>
><text> ❗ **É obrigatório o envio de uma das coberturas entre:** </text>
>
> - DAMAGE-COVERAGE
> - THIEFT COVERAGE


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

> **Code**: COVERAGE-TYPE <br>
> **Tipo**: ```text``` <br>
> 
> Pergunta usada para definir o tipo de cobertura. Os possíveis valores para esta pergunta são:
>
>   - **DAMAGE-COVERAGE =** Cobertura a danos
>   - **THEFT-COVERAGE =** Cobertura a roubo
>   - **CIVIL-LIABILITY-COVERAGE =**  
>   - **ACCESSORIES-COVERAGE =**  
>   - **ELECTRICAL-DAMAGE-COVERAGE =**  
>   - **INTERNATIONAL-COVERAGE =** 

------------------------------------------------------------------------

> **Code**: COVERAGE-LIMIT <br>
> **Tipo**: ```integer``` <br>
> 
> Pergunta usada para definir o limite de uma cobertura, caso uma delas sejam: <br>
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