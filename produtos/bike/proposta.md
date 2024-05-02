# Criar Proposta

## Criar proposta

<mark style="color:green;">`POST`</mark> `{{url_ambiente}}/{{version}}/quotation/proposal`

Cria uma proposta (atualiza informações adicionais).

#### Headers

| Name                                                         | Type | Description             |
| ------------------------------------------------------------ | ---- | ----------------------- |
| Ocp-Apim\_Subscription-Key<mark style="color:red;">\*</mark> | key  | chave de acesso da api. |

{% tabs %}
{% tab title="200: OK Retorno sucesso " %}
[#response](proposta.md#response "mention")
{% endtab %}

{% tab title="400: Bad Request Retorno com mensagem do local do erro" %}
```json
{
    "success": false,
    "executed": "2023-05-22T20:25:43.6362739Z",
    "errors": [
        {
            "code": "INVALID-FORM-FIELD",
            "message": "'Item Identifier' must not be empty.",
            "properties": {
                "validationType": "NotEmptyValidator",
                "field": "Documents[0].ItemIdentifier"
            }
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
    "message": "Access denied due to missing subscription key. Make sure to include subscription key when making requests to an API."
}
```
{% endcode %}
{% endtab %}

{% tab title="500: Internal Server Error Erro de aplicação/servidor" %}

{% endtab %}
{% endtabs %}

## Request

```json
{
   "identifier":"2aea86d1-a9e5-4220-ab29-68c3fba8483f",
   "registerNumber": "100000",
   "operationCode":"BIKE-MULTIPLE-PERIL-PARTNER",
   "answers":[
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
      },
      {
         "code": "PEP",
         "answer": "RELATION"
      },
      {
         "code": "PEP-NAME",
         "answer": "teste"
      },
      {
         "code": "PEP-PARENTING",
         "answer": "SON/DAUGHTER"
      }
   ]
}
```

### Detalhamento request de proposta

> **Code**: INSURED-BIRTH-DATE\
> **Type**: `date`\
> ❗ Obrigatório que esteja incluído no array (apenas se o segurado for Pessoa Fisica).
>
> Pergunta usada para definir a data de nascimento do segurado.



> **Field:** RegisterNumber
>
> **Tipo:** `text`&#x20;
>
> ❗ Campo Obrigatório.
>
> Campo usado para definir qual o SusepNumber da corretora que está sendo cotada. Neste caso, o susep da corretora é "100000".



> **Code**: PAYMENT-METHOD\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o método de pagamento.\
> Os possíveis valores para esta pergunta são:
>
> Se o INVOICE FOR TRUE
>
> * _CREDIT-CARD_
>   * _Para o ambiente de homologação, é necessário que o valor do prêmio da cotação, campo "Total Value", seja um número par, para que seja possível obter sucesso no checkout._
> * _TICKET_
>
> _Se o INVOICE FOR FALSE_
>
> * _CREDIT-CARD_
>
> &#x20;

> **Code**: DUE-DAY\
> **Type**: `integer`\
> ❗ Obrigatório que esteja incluído no array. (apenas quando o PAYMENT-METHOD for TICKET).
>
> Pergunta usada para definir o dia de vencimento quando o PAYMENT-METHOD for TICKET (boleto).
>
> \
> Só é possivel envio do dia 1 ao dia 20.



> **Code**: PAYMENT-INSTALLMENT-IDENTIFIER\
> **Type**: `guid`\
> ❗ Obrigatório que esteja incluído no array.
>
> O guid que será enviado nesse campo é retornado no array de installments, no retorno do endpoint de criar cotação.



> **Code**: PEP\
> **Type**: `string`\
> ❗ Obrigatório que esteja incluído no array quando for **PESSOA FÍSICA**.
>
> Pergunta usada para definir se é uma **pessoa exposta publicamente.**
>
> \
> Respostas para PEP:\
> \
> **NO:** Não é publicamente exposta.
>
> **YES:** É publicamente exposta.
>
> **RELATION:** Relacionamento próximo.

<details>

<summary>Caso PEP for RELATION, é necessário o envio de mais duas perguntas, sendo elas:</summary>

```markdown
Code: PEP-NAME
Type: string
❗ Obrigatório que esteja incluído no array.
Pergunta usada para definir o nome da pessoa com relação.
```

```markdown
Code: PEP-PARENTING
Type: string
❗ Obrigatório que esteja incluído no array.
Pergunta usada para definir a relação da pessoa.

Opções de Envio:

- FATHER/MOTHER = Pai/Mãe
- SON/DAUGHTER = Filho/Filha
- SPOUSE = Cônjugue
- PARTNER = Companheiro/Companheira
- STEPSON = Enteado/Enteada
- OTHER = Outros
```

</details>

{% code overflow="wrap" %}
```json
{
    "item": {
        "quotationIdentifier": "be73c0d9-da81-450f-9546-570f36813b22",
        "status": "Draft",
        "proposal": {
            "number": "97595175730001",
            "date": "0001-01-01T00:00:00Z",
            "acceptanceUrl": "https://bit.ly/47DabRH",
            "documentUrl": "https://azusbrfairfaxstorage.blob.core.windows.net/document/quotation/be73c0d9-da81-450f-9546-570f36813b22/proposta_Testebike_97595175730001_v01.00_yp0z.pdf"
        },
        "pricing": [
            {
                "variantIdentifier": "6456a551-78e3-4ec6-9318-63c5e8b45990",
                "underwriting": {
                    "approved": true,
                    "evaluations": []
                },
                "price": {
                    "commission": 52.89,
                    "grievanceDiscount": 0.0,
                    "itemValue": 5000.0,
                    "netValue": 264.44,
                    "interestValue": 0.0,
                    "taxValue": 19.52,
                    "totalValue": 283.96,
                    "policyLimit": 5000.0,
                    "rates": [
                        {
                            "code": "DAMAGE-COVERAGE",
                            "description": "Danos à bike",
                            "limit": 5000.0,
                            "netValue": 69.59,
                            "deductible": {
                                "code": "INCREASED",
                                "text": "Majorada",
                                "description": "15% dos prejuízos indenizáveis com o mínimo de R$ 900,00"
                            }
                        },
                        {
                            "code": "THEFT-COVERAGE",
                            "description": "Roubo e/ou furto qualificado",
                            "limit": 5000.0,
                            "netValue": 194.85,
                            "deductible": {
                                "code": "INCREASED",
                                "text": "Majorada",
                                "description": "10% dos prejuízos indenizáveis com o mínimo de R$ 900,00"
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
                                    "identifier": "51a6ae54-60b7-4888-b287-149056a568eb",
                                    "number": 1,
                                    "commissionValue": 52.89,
                                    "netValue": 264.44,
                                    "interestValue": 0.0,
                                    "taxValue": 19.52,
                                    "totalValue": 283.96,
                                    "installmentValue": 283.96,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 19.52,
                                    "dueDates": [
                                        "2023-12-07T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "11f610e5-bac0-434e-831c-b4adfbecb9be",
                                    "number": 2,
                                    "commissionValue": 52.89,
                                    "netValue": 264.44,
                                    "interestValue": 0.0,
                                    "taxValue": 19.52,
                                    "totalValue": 283.96,
                                    "installmentValue": 141.98,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 9.76,
                                    "dueDates": [
                                        "2023-12-07T00:00:00Z",
                                        "2024-01-20T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "a0121da8-a425-4845-b845-8cd8bc661b11",
                                    "number": 3,
                                    "commissionValue": 52.89,
                                    "netValue": 264.44,
                                    "interestValue": 0.0,
                                    "taxValue": 19.52,
                                    "totalValue": 283.96,
                                    "installmentValue": 94.65,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 6.51,
                                    "dueDates": [
                                        "2023-12-07T00:00:00Z",
                                        "2024-01-20T12:00:00Z",
                                        "2024-02-20T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "364ce728-0864-4859-9ec4-01739d1accd1",
                                    "number": 4,
                                    "commissionValue": 52.89,
                                    "netValue": 264.44,
                                    "interestValue": 0.0,
                                    "taxValue": 19.52,
                                    "totalValue": 283.96,
                                    "installmentValue": 70.99,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 4.88,
                                    "dueDates": [
                                        "2023-12-07T00:00:00Z",
                                        "2024-01-20T12:00:00Z",
                                        "2024-02-20T12:00:00Z",
                                        "2024-03-20T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "56eda369-9de8-4bf5-bdcf-f87fc622ab32",
                                    "number": 5,
                                    "commissionValue": 52.89,
                                    "netValue": 264.44,
                                    "interestValue": 0.0,
                                    "taxValue": 19.52,
                                    "totalValue": 283.96,
                                    "installmentValue": 56.79,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 3.9,
                                    "dueDates": [
                                        "2023-12-07T00:00:00Z",
                                        "2024-01-20T12:00:00Z",
                                        "2024-02-20T12:00:00Z",
                                        "2024-03-20T12:00:00Z",
                                        "2024-04-20T12:00:00Z"
                                    ]
                                }
                            ]
                        },
                        {
                            "paymentMethod": "Ticket",
                            "paymentType": "Ticket",
                            "installments": [
                                {
                                    "identifier": "22094ea0-2789-4181-b04b-723c8c1e9fe4",
                                    "number": 1,
                                    "commissionValue": 52.89,
                                    "netValue": 264.44,
                                    "interestValue": 0.0,
                                    "taxValue": 19.52,
                                    "totalValue": 283.96,
                                    "installmentValue": 283.96,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 19.52,
                                    "dueDates": [
                                        "2023-12-07T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "6c6f271d-d507-4537-bcef-d4324fe4f347",
                                    "number": 2,
                                    "commissionValue": 52.89,
                                    "netValue": 264.44,
                                    "interestValue": 0.0,
                                    "taxValue": 19.52,
                                    "totalValue": 283.96,
                                    "installmentValue": 141.98,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 9.76,
                                    "dueDates": [
                                        "2023-12-07T00:00:00Z",
                                        "2024-01-20T12:00:00Z"
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
    "executed": "2023-11-30T20:03:36.2261873Z"
}
```
{% endcode %}

### Explicando campos de retorno

Diferente do Response de Cotação, o de proposta possui um campo a mais logo após o "Status", que seria o proposal:

```json
"proposal": {
    "number": "97595175730001",
    "date": "0001-01-01T00:00:00Z",
    "acceptanceUrl": "https://bit.ly/47DabRH",
    "documentUrl": "https://azusbrfairfaxstorage.blob.core.windows.net/document/quotation/be73c0d9-da81-450f-9546-570f36813b22/proposta_Testebike_97595175730001_v01.00_yp0z.pdf"
}
```



> **Field**: number\
> **Type**: `text`
>
> Número da proposta.

***

> **Field**: date\
> **Type**: `date`
>
> Data que a proposta foi criada.

***

> **Field**: acceptanceUrl\
> **Type**: `text`
>
> Link para enviar fotos e realizar checkout.

***

> **Field**: documentUrl\
> **Type**: `text`
>
> Link do documento da proposta.

