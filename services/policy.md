# Serviço de apólice

Consulta Apólice única
----------------

#### Endpoint
```
GET: {{url_ambiente}}/v1/policy/{policyNumber}
```

> ❕ Chamada GET, passando como paramêtro o numero da apólice.

#### Response

```json
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

Listagem Apólice
----------------

#### Endpoint
```
GET: {{url_ambiente}}/v1/policy/all
```

#### Query Parameters

> **Field**: page <br>
> **Type**: ```string``` <br>
>
> Possível passar número da pagina.

-----------------------------------------------------

> **Field**: sort <br>
> **Type**: ```string``` <br>
>
> Possível ordernar pelo campo desejado.<br><br>
> Os valores possíveis para esta query parameter são: </br>
> 
>  - **producttext =** ordernar pelo produto.</br>
>  - **modalitytext =** ordernar pela modalidade.</br>
>  - **createdat =** ordernar pela data de criação.</br>
>  - **status =** ordernar pelo status</br>
>  - **insuredname =** ordernar pelo nome do segurado</br> 
>  - **insuredidentity =** ordernar pela identificação do segurado.</br>
>
> Caso queira definir se a ordem sera crescente ou não, basta passar o operador ```-``` quando for decrescente.</br>
> Caso queria passar mais de um campo para ordenação, tambem é possivel, basta colocar os campos separados por ```,```</br>
>
> Exemplo:</br>
> ```{{url_ambiente}}/v1/policy/all?sort=-status,insuredname```</br>
> No exemplo acima é passado dois campos para a ordenação, onde o status sera em ordem decrescente e o insuredName será em ordem crescente.</br>
>
-----------------------------------------------------

> **Field**: search <br>
> **Type**: ```string``` <br>
>
> Campo para buscar pelo nome do segurado.

-----------------------------------------------------

> **Field**: modality <br>
> **Type**: ```string``` <br>
>
> Campo para buscar pela modalidade.

-----------------------------------------------------

> **Field**: product <br>
> **Type**: ```string``` <br>
>
> Campo para buscar pelo produto.

-----------------------------------------------------

> **Field**: startDate <br>
> **Type**: ```string``` <br>
>
> Campo para buscar pela data de inicio de vigencia.

-----------------------------------------------------

> **Field**: endDate <br>
> **Type**: ```string``` <br>
>
> Campo para buscar pela data final de vigencia.

-----------------------------------------------------

> **Field**: status <br>
> **Type**: ```string``` <br>
>
> Campo para buscar pelo status. Os valores possíveis para esta query parameter são: </br><br>
> 
>  - **Issued** = Emitida</br>
>  - **Expired** = Expirada</br>
>  - **Canceled** = Cancelada.

-----------------------------------------------------

#### Response

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

Explicando campos de response da apólice
----------------------------------------

> **Field**: identifier <br>
> **Type**: ```guid``` <br>
>
> Identificação unica da apólice em formatdo de ```guid```.

-----------------------------------------------------

> **Field**: number <br>
> **Type**: ```text``` <br>
>
> Número referente a apólice .

-----------------------------------------------------

> **Field**: policyNumber <br>
> **Type**: ```text``` <br>
>
> Número referente a apólice .

-----------------------------------------------------

> **Field**: status <br>
> **Type**: ```text``` <br>
>
> Status da apólice .

-----------------------------------------------------

> **Field**: insuredName <br>
> **Type**: ```text``` <br>
>
> Nome do Segurado .

-----------------------------------------------------

> **Field**: insuredIdentity <br>
> **Type**: ```text``` <br>
>
> Identificação do segurado.

-----------------------------------------------------

> **Field**: modalityText <br>
> **Type**: ```text``` <br>
>
> Modalidade.

-----------------------------------------------------

> **Field**: modalityCode <br>
> **Type**: ```text``` <br>
>
> Codigo da modalidade.

-----------------------------------------------------

> **Field**: productText <br>
> **Type**: ```text``` <br>
>
> Produto.

-----------------------------------------------------

> **Field**: productCode <br>
> **Type**: ```text``` <br>
>
> Codigo do produto.

-----------------------------------------------------

> **Field**: vigencyStartedAt <br>
> **Type**: ```date``` <br>
>
> Inicio da vigencia.

-----------------------------------------------------

> **Field**: vigencyExpiredAt <br>
> **Type**: ```date``` <br>
>
> Final da vigencia.

-----------------------------------------------------

> **Field**: createdAt <br>
> **Type**: ```date``` <br>
>
> Data de criação.

-----------------------------------------------------

> **Field**: quotationIdentifier <br>
> **Type**: ```string``` <br>
>
> Identificação refente a cotação.

-----------------------------------------------------

> **Field**: quotationDocumentUrl <br>
> **Type**: ```string``` <br>
>
> Url do pdf da apólice.

-----------------------------------------------------

> **Field**: TicketUrl <br>
> **Type**: ```string``` <br>
>
> Url do boleto.

-----------------------------------------------------

> **Field**: version <br>
> **Type**: ```string``` <br>
>
> Versão da apólice.

-----------------------------------------------------

> **Field**: installments <br>
> **Type**: ```array``` <br>
>
> Lista das informações de parcelas.

-----------------------------------------------------

> **Field**: installments[].installmentNumber <br>
> **Type**: ```integer``` <br>
>
> Número da parcela.

-----------------------------------------------------

> **Field**: installments[].dueDate <br>
> **Type**: ```date``` <br>
>
> Data de vencimento.

-----------------------------------------------------

> **Field**: installments[].valueIof <br>
> **Type**: ```decimal``` <br>
>
> Valor do IOF.

-----------------------------------------------------

> **Field**: installments[].tariffPremiumValue <br>
> **Type**: ```decimal``` <br>
>
> Valor do prêmio tarifário.

-----------------------------------------------------

> **Field**: installments[].premiumTotalValue <br>
> **Type**: ```decimal``` <br>
>
> Valor do prêmio total da cotação.

-----------------------------------------------------

> **Field**: installments[].status <br>
> **Type**: ```string``` <br>
>
> Status de pagamento.

-----------------------------------------------------

> **Field**: installments[].interestValue <br>
> **Type**: ```decimal``` <br>
>
> Valor de juros de cada parcela.

-----------------------------------------------------

> **Field**: installments[].createdAt <br>
> **Type**: ```date``` <br>
>
> Data de criação da parcela.
