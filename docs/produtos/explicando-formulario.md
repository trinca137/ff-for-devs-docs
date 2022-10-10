!!! Aviso

      Isso é um padrão de envio para todos produtos.
      Verifique os campos adicionais para cada produto para adicionar no array de **```Answers```**

### 💡Desmistificando o json de request - part 1

```json
{
	"operationCode":"BIKE-MULTIPLE-PERIL-PARTNER",
	"answers":[],
}
```

> **Field**: OperationCode </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗campo obrigatório</text> </br>
> Campo usado para definir qual produto esta sendo cotado, neste caso o produto é bike, representado pelo operation code "BIKE-MULTIPLE-PERIL-PARTNER".

---------------------------------------------------------

> **Field**: Answers </br>
> **Tipo**: ```array<answer>``` </br>
> <text class="aviso"> ❗ Campo obrigatório</text> </br>
> Campo usado para enviar as perguntas mais gerais de uma cotação, um exemplo de pergunta seria se a pessoa que esta realizando a operação é jurídica ou física.</br>
> Veremos mais detalhes sobre essas perguntas mais abaixo na documentacao.
Abaixo, podemos ver a modelagem de answer.

### 💡 Desmistificando o json de request - part 2


> O campo **answers** tem como finalidade enviar as perguntas referentes a cotação, abaixo você vera os valores que poderão/deverão estar inclusos nesse array.

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


> **Code**: MODALITY </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir qual produto esta sendo cotado, neste caso o produto é bike, representado pelo operation code **BIKE-MULTIPLE-PERIL** 

------------------------------------------------------------------------

> **Code**: PERSON-TYPE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatorio que esteja incluido no array </text> </br>
> 
> - Pergunta usada para saber que a cotacao esta sendo feita por uma pessoa física ou jurídica. </br>
> 
***Os possiveis valores para esta pergunta são:*** </br>
> **NATURAL =** Significa que a pessoa em questão é física </br>
> **LEGAL =** Significa que a pessoa em questão é jurídica

------------------------------------------------------------------------

> **Code**: START-VIGENCY-DATE </br>
> **Tipo**: ```date``` </br>
> <text class="aviso"> ❗Obrigatorio que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o inicio da vigencia do seguro.

------------------------------------------------------------------------

> **Code**: VIGENCY-DURATION </br>
> **Tipo**: ```integer``` </br>
> No momento so é possivel o padrão, não sendo possível mudar a duração da vigência </br>
> 
> - Pergunta usada para definir a duração da vigência em anos, o valor padrao é 1.

------------------------------------------------------------------------

> **Code**: VIGENCY-RETROACTIVITY-AGREEMENT </br>
> **Tipo**: ```boolean``` </br>
> 
> - Pergunta usada para definir "**Entendimento e concordância de vigência retroativa**".
 Se defida  como true, indica que "**Estou ciente e de acordo que não possuo conhecimento de qualquer fato que possa acarretar uma reclamação futura entre o início de vigência e a data de emissão da apólice**"

------------------------------------------------------------------------

> **Code**: CONGENER </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir se a cotação em questão é um seguro novo, ou uma renovação.
> 
> ***Os possíveis valores para esta pergunta são:***</br>
> **NEW =** Indica que é um seguro novo. </br>
> **RENEW =** Indica que é a renovação de um seguro.

------------------------------------------------------------------------

> **Code**: PREVIOUS-INSURER </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array (se a cotação for uma renovação de outra seguradora) </text>
> 
> - Pergunta usada para definir qual era a seguradora anterior. </br>
> - Neste campo se deve enviar um **cnpj**.

------------------------------------------------------------------------

> **Code**: PREVIOUS-NAME</br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array (se a cotacao for uma renovação de outra seguradora)</text></br>
> 
> - Pergunta usada para definir o nome da seguradora anterior.

------------------------------------------------------------------------

> **Code**: INSURED-NAME </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o nome do segurado

------------------------------------------------------------------------

> **Code**: INSURED-EMAIL </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o email do segurado

------------------------------------------------------------------------

> **Code**: IDENTITY </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir a identificação do segurado, seja ela um **cpf** ou um **cnpj**

------------------------------------------------------------------------

> **Code**: GENDER </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o genero do segurado </br>
> 
> ***Os possiveis valores para esta pergunta são:*** </br>
> **M =** Masculino </br>
> **F =** Feminino </br>
> **I =** Não informado </br>
> 
> - Caso nada seja enviado, o valor padrao é "**I**".

------------------------------------------------------------------------

> **Code**: INSURED-CELLPHONE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o telefone do segurado.

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-ZIPCODE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o codigo postal do segurado

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-STREET </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir a rua do segurado

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-NUMBER </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o número da moradia do segurado

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-COMPLEMENT </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatorio que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o numero da moradia do segurado

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-NEIGHBORHOOD </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o bairro do segurado

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-CITY </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir a cidade do segurado

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-STATE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o estado do segurado

------------------------------------------------------------------------

> **Code**: COMMISSION </br>
> **Tipo**: ```decimal``` </br>
> - Pergunta usada para definir a comissao. </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido</text>
> 
> - Pode ser enviado valores entre 1 e 20
>     - O valor padrao é 20.00


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


> **Code**: ITEMS </br>
> **Tipo**: ```array<answer>``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text>
> 
> - Esta pergunta em formato de array de answer é usado para enviar as perguntas mais específicas do produto em questão, neste caso bike. Veremos essas perguntas com mais detalhes adiante.

> **Code**: GRIEVANCE-DISCOUNT </br>
> **Tipo**: ```decimal```
> 
> - Pergunta usada para definir Agravo (aumento de valor acima do valor final da cotação).
> 
> O Padrão é 0

------------------------------------------------------------------------

> **Code**: ITEMS </br>
> **Tipo**: ```array<answer>``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text>
> 
> - Esta pergunta em formato de array de answer é usado para enviar as perguntas mais específicas do produto em questão, neste caso bike. Veremos essas perguntas com mais detalhes adiante.

________________________________________________________________________

### 💡 Desmistificando o json de request - part 3

> ❕ Como explicado mais acima, o campo **items** dentro do **array de answer** tem como finalidade enviar as perguntas mais específicas do produto que esta sendo contado (bikes), abaixo você vera os valores que poderão/deverão estar inclusos nesse array.

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
> - Esta pergunta é usada para definir o número de serie da bike em questão.(30 caracteres no máximo)

------------------------------------------------------------------------

> **Code**: ITEM-TYPE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> Esta pergunta é usada para definir o tipo da bike. </br>
> 
> ***Os possíveis valores para esta pergunta são:*** </br>
> **TRADITIONAL =** Bike tradicional </br>
> **ELETRIC =** Bike elétrica (Elétrica (até 500W))

------------------------------------------------------------------------

> **Code**: MANUFACTURE-YEAR </br>
> **Tipo**: ```integer``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array.</text>
> 
> - Esta pergunta é usada para definir o ano de fabricacão da bike. (2017 ou menor não cobrimos).
>
> ***São aceitos de 2018 ate 2022*** </br>

------------------------------------------------------------------------

> **Code**: MODEL </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text>
> 
> - Esta pergunta é usada para definir o modelo da bike.

------------------------------------------------------------------------

> **Code**: COMPETITIONS </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array.</text>
> 
> - Esta pergunta é usada para definir se a bike sera usada para competições.

------------------------------------------------------------------------

> **Code**: ORIGINAL-VALUE </br>
> **Tipo**: ```decimal``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array.</text>
> 
> - Esta pergunta é usada para definir o valor original da bike.

------------------------------------------------------------------------

> **Code**: VALUE-AGREEMENT </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array.</text>
> 
> - Pergunta usada para definir "**Entendimento e concordância de valor aprovado**".
se defida  como true, indica que "**Estou de acordo com o valor aprovado pela Fairfax.**"

------------------------------------------------------------------------

> **Code**: NEW </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array.</text>
> 
> - Pergunta usada para definir se a bike é nova ou não.
> 
> - ❕***Considera-se Novo Quando o Segurado é o 1º Proprietário e que a data de emissão da nota fiscal seja de até 60 dias após a data de compra.***

------------------------------------------------------------------------

> **Code**: BRAND-NAME </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array. </text>
> 
> - Pergunta usada para definir a marca da bike.

------------------------------------------------------------------------

> **Code**: FRAME-Tipo </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatorio que esteja incluido no array. </text>
> 
> - Pergunta usada para definir o quadro da bike.
> 
> - ***Os possíveis valores para esta pergunta são:*** </br>
>     - **CARBON =** carbono </br>
>     - **ALUMINUM =** aluminio </br>
>     - **STEEL=** aço

------------------------------------------------------------------------

> **Code**: FRAME-TYPE-AGREEMENT </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array. </text>
> 
> - Pergunta usada para definir "**Entendimento e concordância do tipo de quadro**"
se defida  como true, indica que "**Estou ciente e de acordo que o material do quadro da Bicicleta acima indicado está correto. A informação incorreta acarretará perda do direito.**"

------------------------------------------------------------------------

> **Code**: CLAIMS </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array. </text></br>
> Pergunta usada para definir se houve Sinistro nos últimos 36 meses.
> 
> - ***Os possíveis valores para esta pergunta são:*** </br>
>     - **0 =** nenhum </br>
>     - **1 =** sinistro </br>
>     - **2 =** sinistros </br>
>     - **3 ou mais é declinado (não cobrimos)**

------------------------------------------------------------------------

> **Code**: DEDUCTIBLE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text></br>
> Pergunta usada para definir o tipo de franquia. </br>
> - ***Os possíveis valores para esta pergunta são:*** </br>
>     - DEFAULT **= padrao** </br>
>     - REDUCED  **= reduzida** </br>
>     - INCREASED **= aumentada** </br>

------------------------------------------------------------------------

> **Code**: PART-BIKE-AGREEMENT </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> Pergunta usada para definir "**Entendimento e concordância das peças modificadas**"
se defida  como true, indica que "**Estou ciente e de acordo que as peças modificadas deverão conter Nota Fiscal e/ou Cupom Fiscal, em nome do segurado. A não apresentação acarretará perda de direito.**"

------------------------------------------------------------------------

> **Code**: PARTS </br>
> **Tipo**: ```array<answer>``` </br>
> Campo usado para enviar as partes customizadas da bike, **haverá uma seção nesta documentação explicando mais detalhadamente** 

------------------------------------------------------------------------

> **Code**: COVERAGES</br>
> **Tipo**: ```array<answer>``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array</text></br>
> Campo usado para enviar as coberturas, **haverá uma seção nesta documentação explicando mais detalhadamente** 

------------------------------------------------------------------------

> **Code**: RENT</br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array</text></br>
> Pergunta usada para definir se a bike sera usada para locações.

------------------------------------------------------------------------

> **Code**: INVOICE </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array.</text></br>
> Pergunta usada para definir se a bike possui ou não nota fiscal.

------------------------------------------------------------------------

> **Code**: INVOICE-AGREEMENT </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso"> Obrigatório que esteja incluido no array (se INVOICE == TRUE)</text> </br>
> Pergunta usada para definir "**Entendimento e concordância de solicitação de nota fiscal**"
> Se defida  como true, indica que "**Estou ciente e de acordo que a nota fiscal e/ou cupom fiscal da bicicleta em nome do segurado, serão solicitados em caso de sinistro.**"

### 💡 Desmistificando o json de request - part 4.1

> Como explicado mais acima, o campo **parts** dentro do **array de items** tem como finalidade enviar as partes customizadas da bike, abaixo você vera os valores que poderão estar inclusos nesse array.
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

> - ***Os possíveis valores para esta pergunta são:*** </br>
>     - **DEFAULT =** padrão </br>
>     - **REDUCED =** reduzida </br>
>     - **INCREASED =** aumentada </br>

> **Code:** PART-TYPE </br>
> **Tipo:** ```text``` </br>
> Pergunta usada para definir partes adicionais da bike.
> - **Os possíveis valores para esta pergunta são:**<br>
>     - **FRONT-DERAILLEUR =** Câmbio diantero <br>
>     - **REAR-DERAILLEUR =** Câmbio transeiro <br>
>     - **SEATPOST =** Canote <br>
>     - **SEATPOST-BRAND =** <br>
>     - **CLIP-PEDAL =** Clip pedal <br>
>     - **COLOR =**  Cor <br>
>     - **HUB =** Cubos <br>
>     - **BRAKE =** Freios <br>
>     - **FORK =** Garfo <br>
>     - **HANDLEBAR =** Guidão <br>
>     - **STEM =** Tronco <br>
>     - **PEDAL =** Pedal <br>
>     - **CRANKSET =**  <br>
>     - **TIRE =** Pneu <br>
>     - **FRAME =** Quadro <br>
>     - **WHEEL =** Roda <br>
>     - **SADDLE =** Banco <br>
>     - **FRONT-SHIFTER =** <br>
>     - **REAR-SHIFTER =** <br>

------------------------------------------------------------------------

> **Code**: PART-BRAND<br>
> **Tipo**: ```text```<br>
> Pergunta usada para definir a marca da parte.

------------------------------------------------------------------------

> **Code**: PART-MODEL<br>
> **Tipo**: ```text```<br>
> Pergunta usada para definir o modelo da parte.

------------------------------------------------------------------------

**Code**: PART-VALUE<br>
**Tipo**: ```decimal```<br>
> Pergunta usada para definir o valor da parte.

------------------------------------------------------------------------

### 💡Desmistificando o json de request - part 4.2

> Como explicado mais acima, o campo **coverages** dentro do **array de items** tem como finalidade enviar as coberturas, abaixo voce vera os valores que poderão/deverão estar inclusos nesse array.

<text> ❗**É obrigatório pelo menos uma das coberturas entre:** </text>

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
> Pergunta usada para definir o tipo de cobertura.<br>
> **Os possíveis valores para esta pergunta são:**

> **DAMAGE-COVERAGE =** Cobertura a danos <br>
> **THEFT-COVERAGE =** Cobertura a roubo <br>
> **CIVIL-LIABILITY-COVERAGE =**  <br>
> **ACCESSORIES-COVERAGE =**  <br>
> **ELECTRICAL-DAMAGE-COVERAGE =**  <br>
> **INTERNATIONAL-COVERAGE =**  <br>

------------------------------------------------------------------------

> **Code**: COVERAGE-LIMIT <br>
> **Tipo**: ```integer``` <br>
> Pergunta usada para definir o limite de uma cobertura, caso uma delas sejam: <br>
>  - CIVIL-LIABILITY-COVERAGE
>  - ACCESSORIES-COVERAGE <br>
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