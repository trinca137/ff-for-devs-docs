# Criar cotação

### Endpoint
```
POST: {{url_ambiente}}/v1/quotation
```

Request
-------

!!! Aviso

      Esse json abaixo contém as informações onde TODOS os produtos utilizam, na pagina do produto é necessário adicionar os campos (contém exemplo nos produtos)

      As respostas estão usando valores referentes a um produto, no caso "Bike"

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
          "code": "START-VIGENCY-DATE",
          "answer": "2022-11-20T03:00:00.000Z"
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

!!! Aviso "Aviso sobre os campos documentados abaixo."

      Isso é um padrão de envio para todos produtos.
      
      Verifique os campos adicionais para cada produto para adicionar no array de **```Answers```**

### 💡Desmistificando o json de request

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

---------------------------------------------------------

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
> Pergunta usada para definir qual modalidade está sendo cotado. Neste caso, a modalidade é "Bike", representado pelo código **"BIKE-MULTIPLE-PERIL"**.

------------------------------------------------------------------------

> **Code**: PERSON-TYPE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> <text class="aviso">❗ O produto de D&O não contém pessoa física, apenas pessoa jurídica.</text></br>
> 
> Pergunta usada para saber se a cotação está sendo preenchida por uma Pessoa Física ou Jurídica. Os valores possíveis para esta pergunta são:</br>
> 
>  - **NATURAL** = significa que a pessoa em questão é física. </br>
>  - **LEGAL** = significa que a pessoa em questão é jurídica.

------------------------------------------------------------------------

> **Code**: CONGENER </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir se a cotação em questão é um Seguro Novo ou uma Renovação. Os valores possíveis para esta pergunta são:<br><br>
> 
>  - **NEW** = indica que é um novo seguro. </br>
>  - **RENEWAL** = indica que é a renovação de um seguro.

------------------------------------------------------------------------

> **Code**: PREVIOUS-INSURER </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. (se a cotação for uma renovação de outra seguradora). </text>
> 
> Pergunta usada para definir qual é a seguradora anterior. </br>
> Neste campo, deve-se enviar um **CNPJ**.

------------------------------------------------------------------------

> **Code**: PREVIOUS-INSURER-NAME</br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. (se a cotação for uma renovação de outra seguradora).</text></br>
> 
> Pergunta usada para definir o nome da seguradora anterior.

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
> Pergunta usada para definir a duração da vigência em anos. O valor padrão é 1.  </br>
> <text class="aviso"> ❗Atualmente não é possivel colocar mais do que 1 ano. </text>

------------------------------------------------------------------------

> **Code**: IDENTITY </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir a identificação do segurado, seja ela um **CPF** ou um **CNPJ**.

------------------------------------------------------------------------

> **Code**: INSURED-NAME </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir o nome do segurado.
> 
------------------------------------------------------------------------

> **Code**: INSURED-EMAIL </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir o e-mail do segurado.

------------------------------------------------------------------------

> **Code**: INSURED-CELLPHONE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir o telefone ou celular do segurado.

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-ZIPCODE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir o código postal (CEP) do segurado.

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
> <text class="aviso">❗Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir o estado do segurado.

------------------------------------------------------------------------

> **Code**: COMMISSION </br>
> **Tipo**: ```decimal``` </br>
> <text class="aviso">❗Obrigatório que esteja incluído</text><br>
> Pergunta usada para definir a comissão. </br>
> 
> Pode ser enviado valores entre 1 e 30.<br>
> Valor padrão é 20.00.

--------------------------------------------------------------------------

> **Code**: GRIEVANCE-DISCOUNT </br>
> **Tipo**: ```decimal```<br>
> 
> Pergunta usada para definir Agravo (aumento de preço sobre o netValue* da cotação).<br>
> O Padrão é 0.<br>
> <text class="aviso"> * Preço líquido do produto sem IOF. </text>

------------------------------------------------------------------------

Response
--------

### Retornos

- Quando retornar 400, retorna a pergunta que faltou alguma resposta, no exemplo a baixo o <text>nome do segurado</text> não foi enviado
```json
{
    "success": false,
    "executed": "2022-10-06T19:58:31.2050064Z",
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

!!! Aviso

      O JSON de response usado de exemplo abaixo é do produto BIKE.

      O response contém algumas informações a mais nesse exemplo pois foi utilizado o retorno de uma cotação de bikes, mas cada produto tem a necessidade de incluir mais perguntas, assim alterando o retorno (dentro de item.price.rates).

- Caso retorno 200, retorna o cálculo com algumas informações.

```json
{
  "item": {
    "quotationIdentifier": "2aea86d1-a9e5-4220-ab29-68c3fba8483f",
    "status": 0,
    "expiredAt": null,
    "quotationDocumentUrl": null,
    "proposal": null,
    "pricing": [
      {
        "variantIdentifier": "92cc00b4-9ba6-4f50-bf5a-38b76ade9370",
        "underwriting": {
          "approved": true,
          "evaluations": []
        },
        "price": {
          "commission": 150.84,
          "grievanceDiscount": 0,
          "itemValue": 11696.4,
          "netValue": 754.22,
          "interestValue": 0,
          "taxValue": 55.66,
          "totalValue": 809.88,
          "policyLimit": 23977.62,
          "rates": [
            {
              "code": "DAMAGE-COVERAGE",
              "description": "Danos à bike",
              "limit": 11696.4,
              "netValue": 122.85,
              "deductible": {
                "code": "INCREASED",
                "text": "Majorada",
                "description": "10% dos prejuízos indenizáveis com o mínimo de R$ 1.100,00"
              }
            },
            {
              "code": "THEFT-COVERAGE",
              "description": "Roubo e/ou furto qualificado",
              "limit": 11696.4,
              "netValue": 343.99,
              "deductible": {
                "code": "INCREASED",
                "text": "Majorada",
                "description": "10% dos prejuízos indenizáveis com o mínimo de R$ 1.100,00"
              }
            },
            {
              "code": "CIVIL-LIABILITY-COVERAGE",
              "description": "Danos Materiais E/ou Corporais a Terceiros (RC)",
              "limit": 11696.4,
              "netValue": 143.69,
              "deductible": {
                "code": "INCREASED",
                "text": "Majorada",
                "description": "R$ 500,00"
              }
            },
            {
              "code": "ACCESSORIES-COVERAGE",
              "description": "Acessórios",
              "limit": 584.82,
              "netValue": 39.19,
              "deductible": {
                "code": "INCREASED",
                "text": "Majorada",
                "description": "15% dos prejuízos indenizáveis com o mínimo de R$ 300,00"
              }
            },
            {
              "code": "INTERNATIONAL-COVERAGE",
              "description": "Cobertura internacional",
              "limit": 11696.4,
              "netValue": 104.5,
              "deductible": {
                "code": "INCREASED",
                "text": "Majorada",
                "description": "Conforme cobertura a ser acionada"
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
                  "identifier": "ee88a83c-1764-4e28-8272-e27d49d32dc8",
                  "number": 1,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88, 
                  "installmentValue": 809.88,
                  "installmentInterest": 0,
                  "installmentTax": 55.66,
                  "dueDates": [
                    "2022-09-22T00:00:00Z"
                  ]
                },
                {
                  "identifier": "572b39db-f139-4dff-96b7-fbb972484b1a",
                  "number": 2,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 404.94,
                  "installmentInterest": 0,
                  "installmentTax": 27.83,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "296a576b-9a49-43af-9408-22850993cf34",
                  "number": 3,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 269.96,
                  "installmentInterest": 0,
                  "installmentTax": 18.55,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "9b341236-7fab-4053-a746-e06cda830af2",
                  "number": 4,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 202.47,
                  "installmentInterest": 0,
                  "installmentTax": 13.92,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
                    "2022-12-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "16074860-0465-4695-9211-19c8ad3b1106",
                  "number": 5,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 161.98,
                  "installmentInterest": 0,
                  "installmentTax": 11.13,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
                    "2022-12-01T12:00:00Z",
                    "2023-01-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "e7abdcd3-67e2-4538-9319-735adca855e3",
                  "number": 6,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 134.98,
                  "installmentInterest": 0,
                  "installmentTax": 9.28,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
                    "2022-12-01T12:00:00Z",
                    "2023-01-01T12:00:00Z",
                    "2023-02-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "a737a7d4-f9b7-4c49-b8f1-e1c9da737204",
                  "number": 7,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 115.7,
                  "installmentInterest": 0,
                  "installmentTax": 7.95,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
                    "2022-12-01T12:00:00Z",
                    "2023-01-01T12:00:00Z",
                    "2023-02-01T12:00:00Z",
                    "2023-03-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "321f86b9-3769-4d63-8639-b4f251519d9f",
                  "number": 8,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 101.24,
                  "installmentInterest": 0,
                  "installmentTax": 6.96,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
                    "2022-12-01T12:00:00Z",
                    "2023-01-01T12:00:00Z",
                    "2023-02-01T12:00:00Z",
                    "2023-03-01T12:00:00Z",
                    "2023-04-01T12:00:00Z"
                  ]
                }
              ]
            },
            {
              "paymentMethod": "Ticket",
              "paymentType": "Ticket",
              "installments": [
                {
                  "identifier": "f8702529-a575-407a-9636-d3703eb50937",
                  "number": 1,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 809.88,
                  "installmentInterest": 0,
                  "installmentTax": 55.66,
                  "dueDates": [
                    "2022-09-22T00:00:00Z"
                  ]
                },
                {
                  "identifier": "db3582c3-3465-436e-a336-e76b7392c632",
                  "number": 2,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 404.94,
                  "installmentInterest": 0,
                  "installmentTax": 27.83,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "f671ba0a-6b6a-4aa2-a9d5-e2267d7a7672",
                  "number": 3,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 269.96,
                  "installmentInterest": 0,
                  "installmentTax": 18.55,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "a8d655d6-7218-4f11-ac19-f717d5df3a78",
                  "number": 4,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 202.47,
                  "installmentInterest": 0,
                  "installmentTax": 13.92,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
                    "2022-12-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "2cf29028-0328-421e-8075-2fc20e4be78d",
                  "number": 5,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 161.98,
                  "installmentInterest": 0,
                  "installmentTax": 11.13,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
                    "2022-12-01T12:00:00Z",
                    "2023-01-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "b829ce1c-44bf-4ec4-9dcc-fc7ccb664acd",
                  "number": 6,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 134.98,
                  "installmentInterest": 0,
                  "installmentTax": 9.28,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
                    "2022-12-01T12:00:00Z",
                    "2023-01-01T12:00:00Z",
                    "2023-02-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "ff8151ef-25b7-4b77-9d84-d81564637117",
                  "number": 7,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 115.7,
                  "installmentInterest": 0,
                  "installmentTax": 7.95,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
                    "2022-12-01T12:00:00Z",
                    "2023-01-01T12:00:00Z",
                    "2023-02-01T12:00:00Z",
                    "2023-03-01T12:00:00Z"
                  ]
                },
                {
                  "identifier": "abf68d10-613b-4c85-82cb-e07e58df476c",
                  "number": 8,
                  "commissionValue": 150.84,
                  "netValue": 754.22,
                  "interestValue": 0,
                  "taxValue": 55.66,
                  "totalValue": 809.88,
                  "installmentValue": 101.24,
                  "installmentInterest": 0,
                  "installmentTax": 6.96,
                  "dueDates": [
                    "2022-09-22T00:00:00Z",
                    "2022-10-01T12:00:00Z",
                    "2022-11-01T12:00:00Z",
                    "2022-12-01T12:00:00Z",
                    "2023-01-01T12:00:00Z",
                    "2023-02-01T12:00:00Z",
                    "2023-03-01T12:00:00Z",
                    "2023-04-01T12:00:00Z"
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
  "executed": "2022-09-15T15:04:10.4663707Z",
  "errors": null
}
```

</br>

### 💡 **Desmistificando o json de response**

> **Field**: success <br>
> **Type**: ```boolean``` <br>
>
> Indica se a requisição foi feita com sucesso.

-------------------------------------------------------------------------------

> **Field**: executed <br>
> **Type**: ```date``` <br>
>
> Data em que a requisição foi feita.

-------------------------------------------------------------------------------

> **Field**: errors  <br>
> **Type**: ```array``` <br>
>
> Array de erros ao fazer a requisição.

-------------------------------------------------------------------------------

> **Field**: item.quotationIdentifier <br>
> **Type**: ```guid``` <br>
>
> Identificador da cotação.

-------------------------------------------------------------------------------

> **Field**: item.status <br>
> **Type**: ```integer``` <br>
>
> Status da cotação.

-------------------------------------------------------------------------------

> **Field**: item.expiredAt <br>
> **Type**: ```date``` <br>
>
> Data de expiração da cotação.

-------------------------------------------------------------------------------

> **Field**: item.quotationDocumentUrl <br>
> **Type**: ```text``` <br>
>
> Url do documento de cotação.

-------------------------------------------------------------------------------

> **Field**: item.pricing <br>
> **Type**: ```array``` <br>
>
> Retorna as propriedades do item, taxas, valores, tipos de pagamentos.</br>
> Array de items cotados. Ele pode retornar mais de 1 item também.<br>
> Ex: seriam dois obj's dentro do array se duas bikes fossem cotadas.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].variantIdentifier <br>
> **Type**: ```guid``` <br>
>
> Identificador do item cotado.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].underwriting.approved <br>
> **Type**: ```boolean``` <br>
>
> Retorna true ou false referente as regras de subscrição do produto.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].underwriting.evaluations <br>
> **Type**: ```array``` <br>
>
> Retorna aviso referente as questões do questionário de risco do produto.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].price.commission <br>
> **Type**: ```decimal``` <br>
>
> Comissão de corretagem.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].price.grievanceDiscount <br>
> **Type**: ```decimal``` <br>
>
> Porcentagem de agravo adicionada ao valor da cotação, onde os valores permitidos vão de 0% até 500%.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].price.itemValue <br>
> **Type**: ```decimal``` <br>
>
> Valor do item.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].price.netValue <br>
> **Type**: ```decimal``` <br>
>
> Valor de prêmio líquido sem o IOF.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].price.interestValue <br>
> **Type**: ```decimal``` <br>
>
> Valor de juros (Por enquanto nenhum produto possui juros, nem para boleto e nem para cartão, mas futuramente terá para boleto).

-------------------------------------------------------------------------------

> **Field**: item.pricing[].price.taxValue <br>
> **Type**: ```decimal``` <br>
>
> Valor de IOF.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].price.totalValue <br>
> **Type**: ```decimal``` <br>
>
> Valor de Prêmio Total, composto pelo prêmio líquido somado ao IOF.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].price.policyLimit <br>
> **Type**: ```decimal``` <br>
>
> Valor de Limite da apólice (no caso de Bikes, o valor do limite da apólice é igual ao valor informado para a bike).

-------------------------------------------------------------------------------

> **Field**: item.pricing[].price.rates <br>
> **Type**: ```array``` <br>
>
> Trata-se de um array, que retornará todas as coberturas contratadas para o produto.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].payment.financialType <br>
> **Type**: ```text``` <br>
>
> Trata-se do tipo de financeiro que no caso é "Cobrança".

-------------------------------------------------------------------------------

> **Field**: item.pricing[].payment.paymentOptions <br>
> **Type**: ```array``` <br>
>
> Retorna as opções de pagamento disponíveis que são: Boleto e Cartão de crédito.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].price.rates[].code <br>
> **Type**: ```text``` <br>
>
> Exibe o código que identifica a ou as coberturas contratadas. Ex: DAMAGE-COVERAGE, trata-se da cobertura de Danos à Bike.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].price.rates[].description <br>
> **Type**: ```text``` <br>
>
> Trata-se do nome da cobertura em português. Ex: "Danos à Bike".

-------------------------------------------------------------------------------

> **Field**: item.pricing[].price.rates[].limit <br>
> **Type**: ```decimal``` <br>
>
> Trata-se do valor do limite da cobertura.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].price.rates[].netValue <br>
> **Type**: ```decimal``` <br>
>
> Valor do prêmio específico de cada cobertura contratada.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].price.rates[].deductible.code <br>
> **Type**: ```text``` <br>
>
> Trata-se do código identificador de cada franquia.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].price.rates[].deductible.text <br>
> **Type**: ```text``` <br>
>
> Nome da franquia selecionada em português - Ex: "Padrão".

-------------------------------------------------------------------------------

> **Field**: item.pricing[].price.rates[].deductible.description <br>
> **Type**: ```text``` <br>
>
> Descrição da franquia.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].payment.paymentOptions[].paymentMethod <br>
> **Type**: ```text``` <br>
>
> Retorna o nome da forma de pagamento que pode ser: Ticket (Boleto) ou CreditCard (Cartão de Crédito).

-------------------------------------------------------------------------------

> **Field**: item.pricing[].payment.paymentOptions[].paymentType <br>
> **Type**: ```text``` <br>
>
> Forma de pagamento que pode ser escolhida: Boleto ou Cartão de crédito.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].payment.paymentOptions[].installments <br>
> **Type**: ```array``` <br>
>
> Retorna a quantidade de parcelas disponíveis para realizar o pagamento referente ao tipo de pagamento.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].payment.paymentOptions[].installments[].identifier <br>
> **Type**: ```guid``` <br>
>
> Código identificador da parcela.<br>
> <text class="aviso"> Esté é o código necessário enviar ao selecionar o método de pagamento. Exemplo: Se foi selecionado cartão de crédito, enviar o identificador daquele meio de pagamento</text>

-------------------------------------------------------------------------------

> **Field**: item.pricing[].payment.paymentOptions[].installments[].number <br>
> **Type**: ```integer``` <br>
>
> Número da respectiva parcela (2 parcela, número 2).

-------------------------------------------------------------------------------

> **Field**: item.pricing[].payment.paymentOptions[].installments[].commissionValue <br>
> **Type**: ```decimal``` <br>
>
> Valor de comissão de cada parcela.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].payment.paymentOptions[].installments[].netValue <br>
> **Type**: ```decimal``` <br>
>
> Valor de prêmio líquido de cada parcela, ou seja, sem o IOF.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].payment.paymentOptions[].installments[].interestValue <br>
> **Type**: ```decimal``` <br>
>
> Valor de juros de cada parcela.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].payment.paymentOptions[].installments[].taxValue <br>
> **Type**: ```decimal``` <br>
>
> IOF que implica em cada parcela.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].payment.paymentOptions[].installments[].totalValue <br>
> **Type**: ```decimal``` <br>
>
> Valor total de cada parcela que é composto do valor líquido + IOF.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].payment.paymentOptions[].installments[].installmentValue <br>
> **Type**: ```decimal``` <br>
>
> Valor total da parcela.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].payment.paymentOptions[].installments[].installmentInterest <br>
> **Type**: ```decimal``` <br>
>
> Valor de juros da parcela.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].payment.paymentOptions[].installments[].installmentTax <br>
> **Type**: ```decimal``` <br>
>
> Valor de IOF de cada parcela.

-------------------------------------------------------------------------------

> **Field**: item.pricing[].payment.paymentOptions[].installments[].dueDates<br>
> **Type**: ```array<string>``` <br>
>
> Datas de vencimento da parcela caso a forma de pagamento seja boleto.
