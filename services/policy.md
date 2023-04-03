# Consulta de apólice

{% swagger method="get" path="/policy/{policyNumber}" baseUrl="{{url_ambiente}}/v1" summary="Consulta Apólice Única" %}
{% swagger-description %}
Retorna informações da apólice solicitada
{% endswagger-description %}

{% swagger-parameter in="path" name="PolicyNumber" type="string" required="true" %}
Número da apólice
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Ocp-Apim-Subscription-Key" type="md5" required="true" %}
Chave de acesso
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Retorno da apólice contratada" %}
```javascript
{
    "policy": {
        "identifier": "ca523a8b-01d3-4927-a41d-75f1d1982894",
        "number": "046692022100101710000820",
        "status": "Emitida",
        "insuredName": "nome do segurado",
        "insuredIdentity": "66941973064",
        "vigencyStartedAt": "2022-09-08T03:00:00Z",
        "vigencyExpiredAt": "2023-09-08T03:00:00Z",
        "modalityCode": "BIKE-MULTIPLE-PERIL",
        "modalityText": "Bicicletas",
        "createdAt": "2022-11-07T18:28:04.9078375Z",
        "quotationIdentifier": "96582a46-2032-4acf-b7d2-a7a61160943d",
        "quotationDocumentUrl": "http://127.0.0.1:10000/devstoreaccount1/document/policy/046692022100101710000820/apolice_046692022100101710000820_v01.00_j3oc.pdf",
        "installments": [
            {
                "installmentNumber": 1,
                "extraValue": 0.00,
                "dueDate": "2022-09-23T00:00:00Z",
                "valueIof": 82.23,
                "tariffPremiumValue": 1114.29,
                "premiumTotalValue": 1196.52,
                "status": "pendente",
                "interestValue": 0.00,
                "createdAt": "2022-09-16T17:02:30.0584567Z"
            },
            {
                "installmentNumber": 2,
                "extraValue": 0.00,
                "dueDate": "2022-09-27T00:00:00Z",
                "valueIof": 16.68,
                "tariffPremiumValue": 225.98,
                "premiumTotalValue": 242.66,
                "status": "pendente",
                "interestValue": 0.00,
                "createdAt": "2022-09-16T20:41:07.3162239Z"
            },
            {
                "installmentNumber": 3,
                "extraValue": 0.00,
                "dueDate": "2022-09-27T00:00:00Z",
                "valueIof": 18.74,
                "tariffPremiumValue": 253.91,
                "premiumTotalValue": 272.65,
                "status": "pendente",
                "interestValue": 0.00,
                "createdAt": "2022-09-20T15:54:46.5951803Z"
            },
            {
                "installmentNumber": 4,
                "extraValue": 0.00,
                "dueDate": "2022-10-19T00:00:00Z",
                "valueIof": 85.64,
                "tariffPremiumValue": 1160.48,
                "premiumTotalValue": 1246.12,
                "status": "pendente",
                "interestValue": 0.00,
                "createdAt": "2022-10-05T19:44:14.2735256Z"
            },
            {
                "installmentNumber": 5,
                "extraValue": 0.00,
                "dueDate": "2022-11-14T00:00:00Z",
                "valueIof": 52.32,
                "tariffPremiumValue": 708.97,
                "premiumTotalValue": 761.29,
                "status": "pendente",
                "interestValue": 0.00,
                "createdAt": "2022-11-07T18:28:07.2086256Z"
            }
        ],
        "version": "01.00",
        "totalClaims": 0
    },
    "success": true,
    "executed": "2022-11-22T13:47:30.0768846Z"
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/v1/policy/all" baseUrl="{{url_ambiente}}" summary="Listagem apólice" %}
{% swagger-description %}
Retorna lista de apólices.
{% endswagger-description %}

{% swagger-parameter in="header" name="Ocp-Apim-Subscription-Key" type="md5" required="true" %}
Chave de acesso
{% endswagger-parameter %}

{% swagger-parameter in="query" name="page" type="string" required="false" %}
Passar o número da chave
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "totalItems": 1,
    "itemsPerPage": 10,
    "list": [
        {
            "identifier": "ca523a8b-01d3-4927-a41d-75f1d1982894",
            "number": "046692022100101710000820",
            "policyNumber": "1007100000820",
            "status": "Issued",
            "insuredName": "nome do segurado",
            "insuredIdentity": "66941973064",
            "vigencyStartedAt": "2022-09-08T03:00:00Z",
            "vigencyExpiredAt": "2023-09-08T03:00:00Z",
            "createdAt": "2022-11-07T18:28:04.9078375Z",
            "quotationIdentifier": "00000000-0000-0000-0000-000000000000",
            "quotationDocumentUrl": "http://127.0.0.1:10000/devstoreaccount1/document/policy/046692022100101710000820/apolice_046692022100101710000820_v01.00_j3oc.pdf",
            "installments": [
                {
                    "installmentNumber": 1,
                    "extraValue": 0.00,
                    "dueDate": "2022-09-23T00:00:00Z",
                    "valueIof": 82.23,
                    "tariffPremiumValue": 1114.29,
                    "premiumTotalValue": 1196.52,
                    "status": "pendente",
                    "interestValue": 0.00,
                    "createdAt": "2022-09-16T17:02:30.0584567Z"
                },
                {
                    "installmentNumber": 2,
                    "extraValue": 0.00,
                    "dueDate": "2022-09-27T00:00:00Z",
                    "valueIof": 16.68,
                    "tariffPremiumValue": 225.98,
                    "premiumTotalValue": 242.66,
                    "status": "pendente",
                    "interestValue": 0.00,
                    "createdAt": "2022-09-16T20:41:07.3162239Z"
                },
                {
                    "installmentNumber": 3,
                    "extraValue": 0.00,
                    "dueDate": "2022-09-27T00:00:00Z",
                    "valueIof": 18.74,
                    "tariffPremiumValue": 253.91,
                    "premiumTotalValue": 272.65,
                    "status": "pendente",
                    "interestValue": 0.00,
                    "createdAt": "2022-09-20T15:54:46.5951803Z"
                },
                {
                    "installmentNumber": 4,
                    "extraValue": 0.00,
                    "dueDate": "2022-10-19T00:00:00Z",
                    "valueIof": 85.64,
                    "tariffPremiumValue": 1160.48,
                    "premiumTotalValue": 1246.12,
                    "status": "pendente",
                    "interestValue": 0.00,
                    "createdAt": "2022-10-05T19:44:14.2735256Z"
                },
                {
                    "installmentNumber": 5,
                    "extraValue": 0.00,
                    "dueDate": "2022-11-14T00:00:00Z",
                    "valueIof": 52.32,
                    "tariffPremiumValue": 708.97,
                    "premiumTotalValue": 761.29,
                    "status": "pendente",
                    "interestValue": 0.00,
                    "createdAt": "2022-11-07T18:28:07.2086256Z"
                }
            ],
            "version": "01.00",
            "totalClaims": 0
        }
    ],
    "success": true,
    "executed": "2022-11-22T13:49:41.0776542Z"
}
```
{% endswagger-response %}
{% endswagger %}

***

> **Field**: sort\
> **Type**: `string`
>
> Possível ordernar pelo campo desejado.\
> \
> Os valores possíveis para esta query parameter são:
>
> * **producttext =** ordernar pelo produto.
> * **modalitytext =** ordernar pela modalidade.
> * **createdat =** ordernar pela data de criação.
> * **status =** ordernar pelo status
> * **insuredname =** ordernar pelo nome do segurado
> * **insuredidentity =** ordernar pela identificação do segurado.
>
> Caso queira definir se a ordem sera crescente ou não, basta passar o operador `-` quando for decrescente.\
> Caso queria passar mais de um campo para ordenação, tambem é possivel, basta colocar os campos separados por `,`
>
> Exemplo:\
> `{{url_ambiente}}/v1/policy/all?sort=-status,insuredname`\
> No exemplo acima é passado dois campos para a ordenação, onde o status sera em ordem decrescente e o insuredName será em ordem crescente.

***

> **Field**: search\
> **Type**: `string`
>
> Campo para buscar pelo nome do segurado.

***

> **Field**: modality\
> **Type**: `string`
>
> Campo para buscar pela modalidade.

***

> **Field**: product\
> **Type**: `string`
>
> Campo para buscar pelo produto.

***

> **Field**: startDate\
> **Type**: `string`
>
> Campo para buscar pela data de inicio de vigencia.

***

> **Field**: endDate\
> **Type**: `string`
>
> Campo para buscar pela data final de vigencia.

***

> **Field**: status\
> **Type**: `string`
>
> Campo para buscar pelo status. Os valores possíveis para esta query parameter são:
>
>
>
> * **Issued** = Emitida
> * **Expired** = Expirada
> * **Canceled** = Cancelada.

***

## Explicando campos de response da apólice

> **Field**: identifier\
> **Type**: `guid`
>
> Identificação unica da apólice em formatdo de `guid`.

***

> **Field**: number\
> **Type**: `text`
>
> Número referente a apólice .

***

> **Field**: policyNumber\
> **Type**: `text`
>
> Número referente a apólice .

***

> **Field**: status\
> **Type**: `text`
>
> Status da apólice .

***

> **Field**: insuredName\
> **Type**: `text`
>
> Nome do Segurado .

***

> **Field**: insuredIdentity\
> **Type**: `text`
>
> Identificação do segurado.

***

> **Field**: modalityText\
> **Type**: `text`
>
> Modalidade.

***

> **Field**: modalityCode\
> **Type**: `text`
>
> Codigo da modalidade.

***

> **Field**: productText\
> **Type**: `text`
>
> Produto.

***

> **Field**: productCode\
> **Type**: `text`
>
> Codigo do produto.

***

> **Field**: vigencyStartedAt\
> **Type**: `date`
>
> Inicio da vigencia.

***

> **Field**: vigencyExpiredAt\
> **Type**: `date`
>
> Final da vigencia.

***

> **Field**: createdAt\
> **Type**: `date`
>
> Data de criação.

***

> **Field**: quotationIdentifier\
> **Type**: `string`
>
> Identificação refente a cotação.

***

> **Field**: quotationDocumentUrl\
> **Type**: `string`
>
> Url do pdf da apólice.

***

> **Field**: TicketUrl\
> **Type**: `string`
>
> Url do boleto.

***

> **Field**: version\
> **Type**: `string`
>
> Versão da apólice.

***

> **Field**: installments\
> **Type**: `array`
>
> Lista das informações de parcelas.

***

> **Field**: installments\[].installmentNumber\
> **Type**: `integer`
>
> Número da parcela.

***

> **Field**: installments\[].dueDate\
> **Type**: `date`
>
> Data de vencimento.

***

> **Field**: installments\[].valueIof\
> **Type**: `decimal`
>
> Valor do IOF.

***

> **Field**: installments\[].tariffPremiumValue\
> **Type**: `decimal`
>
> Valor do prêmio tarifário.

***

> **Field**: installments\[].premiumTotalValue\
> **Type**: `decimal`
>
> Valor do prêmio total da cotação.

***

> **Field**: installments\[].status\
> **Type**: `string`
>
> Status de pagamento.

***

> **Field**: installments\[].interestValue\
> **Type**: `decimal`
>
> Valor de juros de cada parcela.

***

> **Field**: installments\[].createdAt\
> **Type**: `date`
>
> Data de criação da parcela.

***
