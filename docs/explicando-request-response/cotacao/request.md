
# Create Quotation

#### Endpoint
```
POST: {{url_ambiente}}/v1/quotation
```


!!! Aviso

      O JSON Usado de exemplo abaixo é do produto BIKE.

💡 **Exemplo de json de request**

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
            "code": "START-VIGENCY-DATE",
            "answer": "2022-09-08T03:00:00.000Z"
        },
        {
            "code": "CONGENER",
            "answer": "RENEWAL"
        },
        {
            "code": "PREVIOUS-INSURER",
            "answer": "0"
        },
        {
            "code": "PREVIOUS-INSURER-NAME",
            "answer": "Seguradora anterior"
        },
        {
            "code": "INSURED-NAME",
            "answer": "Nome segurado"
        },
        {
            "code": "INSURED-EMAIL",
            "answer": "email@email.com"
        },
        {
            "code": "IDENTITY",
            "answer": "000.111.222-33"
        },
        {
            "code": "GENDER",
            "answer": "F"
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
            "code": "ITEMS",
            "answer": [
                [
                    {
                        "code": "SERIAL-NUMBER",
                        "answer": "1213132"
                    },
                    {
                        "code": "ITEM-TYPE",
                        "answer": "TRADITIONAL"
                    },
                    {
                        "code": "MANUFACTURE-YEAR",
                        "answer": 2019
                    },
                    {
                        "code": "MODEL",
                        "answer": "129"
                    },
                    {
                        "code": "COMPETITIONS",
                        "answer": true
                    },
                    {
                        "code": "ORIGINAL-VALUE",
                        "answer": "12312,00"
                    },
                    {
                        "code": "VALUE-AGREEMENT"
                    },
                    {
                        "code": "NEW",
                        "answer": true
                    },
                    {
                        "code": "BRAND",
                        "answer": "AIST"
                    },
                    {
                        "code": "BRAND-NAME",
                        "answer": "AIST"
                    },
                    {
                        "code": "FRAME-TYPE",
                        "answer": "ALUMINUM"
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
                        "answer": "INCREASED"
                    },
                    {
                        "code": "PART-BIKE-AGREEMENT"
                    },
                    {
                        "code": "PARTS",
                        "answer": null
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
        },
        {
            "code": "COMMISSION",
            "answer": 20
        },
        {
            "code": "GRIEVANCE-DISCOUNT",
            "answer": 0
        }
    ]
}
```

<br>
<br>
<br>

!!! Aviso "Aviso sobre os campos documentados abaixo."

      Isso é um padrão de envio para todos produtos.
      Verifique os campos adicionais para cada produto para adicionar no array de **```Answers```**

<br>
<br>

### 💡Desmistificando o json de request - part 1

```json
{
	"operationCode":"BIKE-MULTIPLE-PERIL-PARTNER",
	"answers":[],
}
```




> **Field**: OperationCode </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Campo Obrigatório.</text> </br>
> 
> Campo usado para definir qual produto está sendo cotado. Neste caso, o produto é "Bike", representado pelo operation code "BIKE-MULTIPLE-PERIL-PARTNER".

---------------------------------------------------------

> **Field**: Answers </br>
> **Tipo**: ```array<answer>``` </br>
> <text class="aviso">❗ Campo Obrigatório.</text> </br>
> 
> Campo usado para enviar perguntas mais gerais de uma cotação – um exemplo de pergunta seria se a pessoa é Jurídica ou Física. Mais detalhes sobre essas perguntas a seguir, na documentação.

<br>
<br>

### 💡 Desmistificando o json de request - part 2


> Como explicado anteriormente, o campo **answers** tem como finalidade enviar perguntas referentes a cotação. A seguir, você verá os valores que poderão/deverão estar inclusos nesse array.

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
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir qual produto está sendo cotado. Neste caso, o produto é "Bike", representado pelo operation code **"BIKE-MULTIPLE-PERIL"**.

------------------------------------------------------------------------

> **Code**: PERSON-TYPE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para saber se a cotação está sendo preenchida por uma Pessoa Física ou Jurídica. Os valores possíveis para esta pergunta são:
> 
>  - **NATURAL** = significa que a pessoa em questão é física. </br>
>  - **LEGAL** = significa que a pessoa em questão é jurídica.

------------------------------------------------------------------------

> **Code**: START-VIGENCY-DATE </br>
> **Tipo**: ```date``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir o início da vigência do seguro.

------------------------------------------------------------------------

> **Code**: VIGENCY-DURATION </br>
> **Tipo**: ```integer``` </br>
> <text class="aviso"> No momento so é possivel o padrão, não sendo possível mudar a duração da vigência. </text> </br>
> 
> Pergunta usada para definir a duração da vigência em anos. O valor padrão é 1.

------------------------------------------------------------------------

> **Code**: VIGENCY-RETROACTIVITY-AGREEMENT </br>
> **Tipo**: ```boolean``` </br>
> 
> Pergunta usada para definir "**Entendimento e concordância de vigência retroativa**".
 Se defida como true, indica que "**Estou ciente e de acordo que não possuo conhecimento de qualquer fato que possa acarretar uma reclamação futura entre o início de vigência e a data de emissão da apólice**"

------------------------------------------------------------------------

> **Code**: CONGENER </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir se a cotação em questão é um Seguro Novo ou uma Renovação. Os valores possíveis para esta pergunta são:
> 
>  - **NEW** = indica que é um novo seguro. </br>
>  - **RENEW** = indica que é a renovação de um seguro.

------------------------------------------------------------------------

> **Code**: PREVIOUS-INSURER </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. (se a cotação for uma renovação de outra seguradora). </text>
> 
> Pergunta usada para definir qual é a seguradora anterior. </br>
> Neste campo, deve-se enviar um **CNPJ**.

------------------------------------------------------------------------

> **Code**: PREVIOUS-NAME</br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. (se a cotação for uma renovação de outra seguradora).</text></br>
> 
> Pergunta usada para definir o nome da seguradora anterior.

------------------------------------------------------------------------

> **Code**: INSURED-NAME </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir o nome do segurado.

------------------------------------------------------------------------

> **Code**: INSURED-EMAIL </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir o e-mail do segurado.

------------------------------------------------------------------------

> **Code**: IDENTITY </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir a identificação do segurado, seja ela um **CPF** ou um **CNPJ**.

------------------------------------------------------------------------

> **Code**: GENDER </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir o gênero do segurado.
Os possíveis valores para esta pergunta são: </br>
> 
> **M** = masculino </br>
> **F** = feminino </br>
> **I** = não informado. </br>
> 
> O valor padrão é "**I**".

------------------------------------------------------------------------

> **Code**: INSURED-CELLPHONE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir o telefone do segurado.

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-ZIPCODE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir o código postal do segurado.

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-STREET </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir a rua do segurado.

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-NUMBER </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir o número da moradia do segurado.

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-COMPLEMENT </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir o número da moradia do segurado.

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-NEIGHBORHOOD </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir o bairro do segurado.

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-CITY </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir a cidade do segurado.

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-STATE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir o estado do segurado.

------------------------------------------------------------------------

> **Code**: COMMISSION </br>
> **Tipo**: ```decimal``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído</text>
> Pergunta usada para definir a comissão. </br>
> 
> Pode ser enviado valores entre 1 e 20.<br>
> Valor padrão é 20.00.


--------------------------------------------------------------------------

> **Code**: GRIEVANCE-DISCOUNT </br>
> **Tipo**: ```decimal```
> 
> Pergunta usada para definir Agravo/Desconto.<br>
> O Padrão é 0.

---------------------------------------------------------------------------------


