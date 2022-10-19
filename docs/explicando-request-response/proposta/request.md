# Criar Proposta

#### Endpoint
```
POST: {{url_ambiente}}/v1/quotation/proposal
```

Request
-------


!!! Aviso

      O JSON Usado de exemplo abaixo é do produto BIKE.

**Exemplo de json de request**

```json
{
   "identifier":"2aea86d1-a9e5-4220-ab29-68c3fba8483f",
   "operationCode":"BIKE-MULTIPLE-PERIL",
   "answers":[
      {
         "code":"MODALITY",
         "answer":"BIKE-MULTIPLE-PERIL"
      },
      {
         "code":"PERSON-TYPE",
         "answer":"NATURAL"
      },
      {
         "code":"START-VIGENCY-DATE",
         "answer":"2022-09-08T03:00:00.000Z"
      },
      {
         "code":"CONGENER",
         "answer":"RENEWAL"
      },
      {
         "code":"PREVIOUS-INSURER",
         "answer":"0"
      },
      {
         "code":"PREVIOUS-INSURER-NAME",
         "answer":"seg teste"
      },
      {
         "code":"INSURED-NAME",
         "answer":"samuel emidio"
      },
      {
         "code":"INSURED-EMAIL",
         "answer":"e@test.come"
      },
      {
         "code":"IDENTITY",
         "answer":"462.564.658-81"
      },
      {
         "code":"GENDER"
      },
      {
         "code":"INSURED-CELLPHONE",
         "answer":"(12) 99644-0332"
      },
      {
         "code":"INSURED-ADDRESS-ZIPCODE",
         "answer":"12422-320"
      },
      {
         "code":"INSURED-ADDRESS-STREET",
         "answer":"Rua Antônio Lopes Pereira"
      },
      {
         "code":"INSURED-ADDRESS-NUMBER",
         "answer":"98"
      },
      {
         "code":"INSURED-ADDRESS-COMPLEMENT",
         "answer":""
      },
      {
         "code":"INSURED-ADDRESS-NEIGHBORHOOD",
         "answer":"Residencial Campos Maia"
      },
      {
         "code":"INSURED-ADDRESS-CITY",
         "answer":"Pindamonhangaba"
      },
      {
         "code":"INSURED-ADDRESS-STATE",
         "answer":"SP"
      },
      {
         "code":"ITEMS",
         "answer":[
            [
               {
                  "code":"ITEM-IDENTIFIER",
                  "answer":"92cc00b4-9ba6-4f50-bf5a-38b76ade9370"
               },
               {
                  "code":"SERIAL-NUMBER",
                  "answer":"1213132"
               },
               {
                  "code":"ITEM-TYPE",
                  "answer":"TRADITIONAL"
               },
               {
                  "code":"MANUFACTURE-YEAR",
                  "answer":2019
               },
               {
                  "code":"MODEL",
                  "answer":"129"
               },
               {
                  "code":"COMPETITIONS",
                  "answer":true
               },
               {
                  "code":"ORIGINAL-VALUE",
                  "answer":"12312,00"
               },
               {
                  "code":"VALUE-AGREEMENT"
               },
               {
                  "code":"NEW",
                  "answer":true
               },
               {
                  "code":"BRAND",
                  "answer":"AIST"
               },
               {
                  "code":"BRAND-NAME",
                  "answer":"AIST"
               },
               {
                  "code":"FRAME-TYPE",
                  "answer":"ALUMINUM"
               },
               {
                  "code":"FRAME-TYPE-AGREEMENT",
                  "answer":true
               },
               {
                  "code":"CLAIMS",
                  "answer":"0"
               },
               {
                  "code":"DEDUCTIBLE",
                  "answer":"INCREASED"
               },
               {
                  "code":"PART-BIKE-AGREEMENT"
               },
               {
                  "code":"PARTS",
                  "answer":[
                     [
                        {
                           "code":"PART-TYPE",
                           "answer":[
                              "UNMODIFIED"
                           ]
                        }
                     ]
                  ]
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
               },
               {
                  "code":"RENT",
                  "answer":false
               },
               {
                  "code":"INVOICE",
                  "answer":true
               },
               {
                  "code":"INVOICE-AGREEMENT",
                  "answer":true
               }
            ]
         ]
      },
      {
         "code":"COMMISSION",
         "answer":20
      },
      {
         "code":"GRIEVANCE-DISCOUNT",
         "answer":0
      },
      {
         "code":"PAYMENT-METHOD",
         "answer":"CREDIT-CARD"
      },
      {
         "code":"INSURED-BIRTH-DATE",
         "answer":"1990-09-08T03:00:00.000Z"
      },
      {
         "code":"DUE-DAY",
         "answer":15
      },
      {
         "code":"PAYMENT-INSTALLMENT-IDENTIFIER",
         "answer":"ee88a83c-1764-4e28-8272-e27d49d32dc8"
      }
   ],
   "documents":[
      {
         "itemIdentifier":"92cc00b4-9ba6-4f50-bf5a-38b76ade9370",
         "files":[
            "data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/4gIoSUNDX1BST0ZJTEUAAQEAAAIYAAAAAAQwAABtbnRyUkdCIFhZWiAAAAAAAAAAAAAAAABhY3NwAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQAA9tYAAQAAAADTLQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAlkZXNjAAAA8AAAAHRyWFlaAAABZAAAABRnWFlaAAABeAAAABRiWFlaAAABjAAAABRyVFJDAAABoAAAAChnVFJDAAABoAAAAChiVFJDAAABoAAAACh3dHB0AAAByAAAABRjcHJ0AAAB3AAAADxtbHVjAAAAAAAAAAEAAAAMZW5VUwAAAFgAAAAcAHMAUgBHAEIAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAFhZWiAAAAAAAABvogAAOPUAAAOQWFlaIAAAAAAAAGKZAAC3hQAAGNpYWVogAAAAAAAAJKAAAA+EAAC2z3BhcmEAAAAAAAQAAAACZmYAAPKnAAANWQAAE9AAAApbAAAAAAAAAABYWVogAAAAAAAA9tYAAQAAAADTLW1sdWMAAAAAAAAAAQAAAAxlblVTAAAAIAAAABwARwBvAG8AZwBsAGUAIABJAG4AYwAuACAAMgAwADEANv/bAEMAAwICAgICAwICAgMDAwMEBgQEBAQECAYGBQYJCAoKCQgJCQoMDwwKCw4LCQkNEQ0ODxAQERAKDBITEhATDxAQEP/bAEMBAwMDBAMECAQECBALCQsQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEP/AABEIAZoCgAMBIgACEQEDEQH/xAAVAAEBAAAAAAAAAAAAAAAAAAAAB//EABQQAQAAAAAAAAAAAAAAAAAAAAD/xAAVAQEBAAAAAAAAAAAAAAAAAAAACP/EABQRAQAAAAAAAAAAAAAAAAAAAAD/2gAMAwEAAhEDEQA/AKwAkRWYAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAD//2Q=="
         ]
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


>**Field**: Identifier <br>
>**Type**: ```guid``` <br>
> <text class="aviso">❗ Campo obrigatório (quando for Proposta ou Checkout).</text> <br>
> 
>Campo usado para definir qual a cotação será enviada para proposta e checkout.<br>

------------------------------------------------------------------------------

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
> Pergunta usada para saber se a cotação está sendo preenchida por uma Pessoa Física ou Jurídica. Os valores possíveis para esta pergunta são:<br><br>
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
> Pergunta usada para definir se a cotação em questão é um Seguro Novo ou uma Renovação. Os valores possíveis para esta pergunta são: <br><br>
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

>**Code**: INSURED-BIRTH-DATE <br>
>**Type**: ```date``` <br>
><text class="aviso">❗ Obrigatório que esteja incluído no array. (quando for para o endpoint de PROPOSAL).</text> <br>
>
>Pergunta usada para definir a data de nascimento do segurado. <br>

--------------------------------------------------------------------------


>**Code**: PAYMENT-METHOD <br>
>**Type**: ```text``` <br>
><text class="aviso">❗ Obrigatório que esteja incluído no array. (quando for para o endpoint de PROPOSAL).</text> <br>
>
>Pergunta usada para definir o método de pagamento.
Os possíveis valores para esta pergunta são:
>
>  - **CREDIT-CARD**
>  - **TICKET**

--------------------------------------------------------------------------


>**Code**: DUE-DAY <br>
>**Type**: ```integer``` <br>
><text class="aviso">❗ Obrigatório que esteja incluído no array. (apenas quando o PAYMENT-METHOD for TICKET).  </text><br>
><text class="aviso">❗ Obrigatório que esteja incluído no array.  (quando for para o endpoint de PROPOSAL).</text> <br>
>
>Pergunta usada para definir o dia de vencimento quando o PAYMENT-METHOD for TICKET (boleto). <br>

---------------------------------------------------------------------------


retornado
>**Code**: PAYMENT-INSTALLMENT-IDENTIFIER <br>
>**Type**: ```guid``` <br>
><text class="aviso">❗ Obrigatório que esteja incluído no array. (quando for para o endpoint de PROPOSAL). </text><br>
>
>O guid que será enviado nesse campo é retornado no array de installments, no retorno do endpoint de criar cotação. <br>

------------------------------------------------------------------------------


> **Code**: GRIEVANCE-DISCOUNT </br>
> **Tipo**: ```decimal```
> 
> Pergunta usada para definir Agravo/Desconto.<br>
> O Padrão é 0.

---------------------------------------------------------------------------------




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

      O JSON Usado de exemplo abaixo é do produto BIKE.

- Caso retorno 200, retorna o cálculo com algumas informações.

```json
{
  "item": {
    "quotationIdentifier": "2aea86d1-a9e5-4220-ab29-68c3fba8483f",
    "status": 0,
    "expiredAt": null,
    "quotationDocumentUrl": null,
    "proposal": {
      "number": "89678023660002",
      "date": "0001-01-01T00:00:00Z"
    },
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
                    "2022-10-15T12:00:00Z"
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
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z"
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
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z"
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
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z",
                    "2023-01-15T12:00:00Z"
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
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z",
                    "2023-01-15T12:00:00Z",
                    "2023-02-15T12:00:00Z"
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
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z",
                    "2023-01-15T12:00:00Z",
                    "2023-02-15T12:00:00Z",
                    "2023-03-15T12:00:00Z"
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
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z",
                    "2023-01-15T12:00:00Z",
                    "2023-02-15T12:00:00Z",
                    "2023-03-15T12:00:00Z",
                    "2023-04-15T12:00:00Z"
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
                    "2022-10-15T12:00:00Z"
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
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z"
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
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z"
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
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z",
                    "2023-01-15T12:00:00Z"
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
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z",
                    "2023-01-15T12:00:00Z",
                    "2023-02-15T12:00:00Z"
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
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z",
                    "2023-01-15T12:00:00Z",
                    "2023-02-15T12:00:00Z",
                    "2023-03-15T12:00:00Z"
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
                    "2022-10-15T12:00:00Z",
                    "2022-11-15T12:00:00Z",
                    "2022-12-15T12:00:00Z",
                    "2023-01-15T12:00:00Z",
                    "2023-02-15T12:00:00Z",
                    "2023-03-15T12:00:00Z",
                    "2023-04-15T12:00:00Z"
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
  "executed": "2022-09-15T15:15:13.9056702Z",
  "errors": null
}
```

