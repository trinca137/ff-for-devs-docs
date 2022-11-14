# Serviço de apólice


Consulta Apólice
----------------

#### Endpoint
```
GET: {{url_ambiente}}/v1/policy/{policyNumber}
```

> ❕ Chamada GET, passando como route parameter o numero da apólice


#### Response

💡 **Exemplo de json de response**

```json
{
   "policy":{
      "identifier":"33c66b30-0ad8-41fa-a411-8215dee1d29f",
      "number":"046692022100101710000902",
      "status":"Emitida",
      "insuredName":"Cecilia Koelpin Jr.",
      "insuredIdentity":"11607537095",
      "vigencyStartedAt":"2022-11-14T11:00:04Z",
      "vigencyExpiredAt":"2023-11-14T11:00:04Z",
      "modalityCode":"BIKE-MULTIPLE-PERIL",
      "modalityText":"Bicicletas",
      "createdAt":"2022-11-14T12:02:02.147485Z",
      "quotationIdentifier":"c7f2ab5a-1615-4ade-86f9-63009560671e",
      "quotationDocumentUrl":"https://azuqbrfairfaxstorage.blob.core.windows.net/document/policy/046692022100101710000902/apolice_046692022100101710000902_v01.00_1bbf.pdf",
      "ticketDocumentUrl":"https://azuqbrfairfaxstorage.blob.core.windows.net/document/policy/046692022100101710000902/boletos_046692022100101710000902_v01.00_gjnd.pdf",
      "version":"01.00",
      "totalClaims":0
   },
   "success":true,
   "executed":"2022-11-14T13:05:37.192139Z"
}
```




Listagem Apólice
----------------

#### Endpoint
```
GET: {{url_ambiente}}/v1/policy/all
```

#### Query Parameters

>**Field**: page <br>
>**Type**: ```string``` <br>
>
>Possível passar número da pagina.

-----------------------------------------------------


>**Field**: sort <br>
>**Type**: ```string``` <br>
>
> Campo para ordernar pelo campo passado.. Os valores possíveis para esta query parameter são: </br><br>
> 
>  - **producttext =** ordernar pelo produto.</br>
>  - **modalitytext =** ordernar pela modalidade.</br>
>  - **createdat =** ordernar pela data de criação.</br>
>  - **status =** ordernar pelo status</br>
>  - **insuredname =** ordernar pelo nome do segurado</br> 
>  - **insuredidentity =** ordernar pela identificação do segurado.</br>
>
>
> Caso queira definir se a ordem sera crescente ou não, basta passar o operador ```-``` quando for decrescente.</br>
> Caso queria passar mais de um campo para ordenação, tambem é possivel, basta colocar os campos separados por ```,```</br>
>
> Exemplo:</br>
> ```{{url_ambiente}}/v1/policy/all?sort=-status,insuredname```</br>
> No exemplo acima é passado dois campos para a ordenação, onde o status sera em ordem decrescente e o insuredname será em ordem crescente.</br>
>
-----------------------------------------------------

>**Field**: search <br>
>**Type**: ```string``` <br>
>
>Campo para buscar pelo nome do segurado.

-----------------------------------------------------

>**Field**: modality <br>
>**Type**: ```string``` <br>
>
>Campo para buscar pela modalidade.

-----------------------------------------------------

>**Field**: product <br>
>**Type**: ```string``` <br>
>
>Campo para buscar pelo produto.

-----------------------------------------------------

>**Field**: startDate <br>
>**Type**: ```string``` <br>
>
>Campo para buscar pela data de inicio de vigencia.

-----------------------------------------------------

>**Field**: endDate <br>
>**Type**: ```string``` <br>
>
>Campo para buscar pela data final de vigencia.

-----------------------------------------------------

>**Field**: status <br>
>**Type**: ```string``` <br>
>
> Campo para buscar pelo status. Os valores possíveis para esta query parameter são: </br><br>
> 
>  - **Issued** = Emitida</br>
>  - **Expired** = Expirada</br>
>  - **Canceled** = Cancelada.

-----------------------------------------------------




#### Response

💡 **Exemplo de json de response**

```json
{
    "totalItems": 275,
    "itemsPerPage": 10,
    "list": [
        {
            "policyIdentifier": "fc408b7b-9017-40be-844d-e730dd81e953",
            "number": "046692022100101710000907",
            "policyNumber": "1007100000907",
            "status": "Issued",
            "insuredName": "Mrs. Garrett Wolff",
            "insuredIdentity": "40774220511",
            "modalityText": "Bike",
            "productText": "RD Equipamentos",
            "vigencyStartedAt": "2022-11-14T13:23:49Z",
            "vigencyExpiredAt": "2023-11-14T13:23:49Z",
            "createdAt": "2022-11-14T14:06:31.1077184Z",
            "quotationDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/policy/046692022100101710000907/apolice_046692022100101710000907_v01.00_ocy8.pdf",
            "version": "01.00",
            "count": 275
        },
        {
            "policyIdentifier": "0810694d-7197-4c19-a51e-123d58934fc9",
            "number": "046692022100103780001904",
            "policyNumber": "1007800001904",
            "status": "Issued",
            "insuredName": "Angela Leannon",
            "insuredIdentity": "86816500334",
            "modalityText": "Dentista",
            "productText": "RC Profissional",
            "vigencyStartedAt": "2022-11-14T13:23:49Z",
            "vigencyExpiredAt": "2023-11-14T13:23:49Z",
            "createdAt": "2022-11-14T14:04:35.5555354Z",
            "quotationDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/policy/046692022100103780001904/apolice_046692022100103780001904_v01.00_hs0r.pdf",
            "version": "01.00",
            "count": 275
        },
        {
            "policyIdentifier": "6c07e53c-42a5-453f-955a-42f717dc296b",
            "number": "046692022100103780001903",
            "policyNumber": "1007800001903",
            "status": "Issued",
            "insuredName": "Ray Volkman",
            "insuredIdentity": "86031528290",
            "modalityText": "Corretor de Seguros",
            "productText": "RC Profissional",
            "vigencyStartedAt": "2022-11-14T13:23:44Z",
            "vigencyExpiredAt": "2023-11-14T13:23:44Z",
            "createdAt": "2022-11-14T14:02:56.9358468Z",
            "quotationDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/policy/046692022100103780001903/apolice_046692022100103780001903_v01.00_csfy.pdf",
            "ticketDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/policy/046692022100103780001903/boletos_046692022100103780001903_v01.00_a8d3.pdf",
            "version": "01.00",
            "count": 275
        },
        {
            "policyIdentifier": "28ead239-f6ad-409b-a9f1-a4510c5bbd36",
            "number": "046692022100103780001902",
            "policyNumber": "1007800001902",
            "status": "Issued",
            "insuredName": "Dexter Harvey I",
            "insuredIdentity": "01382857802",
            "modalityText": "Dentista",
            "productText": "RC Profissional",
            "vigencyStartedAt": "2022-11-14T13:23:42Z",
            "vigencyExpiredAt": "2023-11-14T13:23:42Z",
            "createdAt": "2022-11-14T14:01:33.6165537Z",
            "quotationDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/policy/046692022100103780001902/apolice_046692022100103780001902_v01.00_c2qi.pdf",
            "ticketDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/policy/046692022100103780001902/boletos_046692022100103780001902_v01.00_r601.pdf",
            "version": "01.00",
            "count": 275
        },
        {
            "policyIdentifier": "33c66b30-0ad8-41fa-a411-8215dee1d29f",
            "number": "046692022100101710000902",
            "policyNumber": "1007100000902",
            "status": "Issued",
            "insuredName": "Cecilia Koelpin Jr.",
            "insuredIdentity": "11607537095",
            "modalityText": "Bike",
            "productText": "RD Equipamentos",
            "vigencyStartedAt": "2022-11-14T11:00:04Z",
            "vigencyExpiredAt": "2023-11-14T11:00:04Z",
            "createdAt": "2022-11-14T12:02:02.147485Z",
            "quotationDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/policy/046692022100101710000902/apolice_046692022100101710000902_v01.00_1bbf.pdf",
            "ticketDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/policy/046692022100101710000902/boletos_046692022100101710000902_v01.00_gjnd.pdf",
            "version": "01.00",
            "count": 275
        },
        {
            "policyIdentifier": "62b99b28-5467-4881-b952-6181a8c71eb5",
            "number": "046692022100101710000901",
            "policyNumber": "1007100000901",
            "status": "Issued",
            "insuredName": "Ray Erdman",
            "insuredIdentity": "22313547809",
            "modalityText": "Bike",
            "productText": "RD Equipamentos",
            "vigencyStartedAt": "2022-11-14T10:59:45Z",
            "vigencyExpiredAt": "2023-11-14T10:59:45Z",
            "createdAt": "2022-11-14T11:02:05.5991632Z",
            "quotationDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/policy/046692022100101710000901/apolice_046692022100101710000901_v01.00_jsyg.pdf",
            "version": "01.00",
            "count": 275
        },
        {
            "policyIdentifier": "0b001b7d-1040-4a0a-af7e-acc4f6cf2d44",
            "number": "046692022100103100000037",
            "policyNumber": "1001000000037",
            "status": "Issued",
            "insuredName": "Melba Hauck DDS",
            "insuredIdentity": "82310664724896",
            "modalityText": "D&O",
            "productText": "RC Administradores e Diretores",
            "vigencyStartedAt": "2022-11-10T11:10:57Z",
            "vigencyExpiredAt": "2023-11-10T11:10:57Z",
            "createdAt": "2022-11-10T16:09:03.5978649Z",
            "quotationDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/policy/046692022100103100000037/apolice_046692022100103100000037_v01.00_tsfm.pdf",
            "ticketDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/policy/046692022100103100000037/boletos_046692022100103100000037_v01.00_ppe4.pdf",
            "version": "01.00",
            "count": 275
        },
        {
            "policyIdentifier": "f1ef6d9a-4241-4b9e-81df-33e3703ccfb0",
            "number": "046692022100103100000035",
            "policyNumber": "1001000000035",
            "status": "Issued",
            "insuredName": "Scott Bartell PhD",
            "insuredIdentity": "88744418401574",
            "modalityText": "D&O",
            "productText": "RC Administradores e Diretores",
            "vigencyStartedAt": "2022-11-09T20:12:03Z",
            "vigencyExpiredAt": "2023-11-09T20:12:03Z",
            "createdAt": "2022-11-10T16:07:54.3196625Z",
            "quotationDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/policy/046692022100103100000035/apolice_046692022100103100000035_v01.00_v53f.pdf",
            "ticketDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/policy/046692022100103100000035/boletos_046692022100103100000035_v01.00_sp81.pdf",
            "version": "01.00",
            "count": 275
        },
        {
            "policyIdentifier": "9bb4efbb-61e4-409d-b6c8-9c5eb5e2dc6c",
            "number": "046692022100101710000883",
            "policyNumber": "1007100000883",
            "status": "Issued",
            "insuredName": "Noah Keeling",
            "insuredIdentity": "77722437745",
            "modalityText": "Bike",
            "productText": "RD Equipamentos",
            "vigencyStartedAt": "2022-11-08T14:41:40Z",
            "vigencyExpiredAt": "2023-11-08T14:41:40Z",
            "createdAt": "2022-11-10T14:23:17.8206571Z",
            "quotationDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/policy/046692022100101710000883/apolice_046692022100101710000883_v01.00_bfcu.pdf",
            "ticketDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/policy/046692022100101710000883/boletos_046692022100101710000883_v01.00_lxac.pdf",
            "version": "01.00",
            "count": 275
        },
        {
            "policyIdentifier": "e7add0e5-5caf-4249-8267-154d9321a42e",
            "number": "046692022100101710000882",
            "policyNumber": "1007100000882",
            "status": "Issued",
            "insuredName": "Luke Beatty",
            "insuredIdentity": "68044874518",
            "modalityText": "Bike",
            "productText": "RD Equipamentos",
            "vigencyStartedAt": "2022-11-08T14:41:19Z",
            "vigencyExpiredAt": "2023-11-08T14:41:19Z",
            "createdAt": "2022-11-10T14:20:22.6067508Z",
            "quotationDocumentUrl": "https://azuqbrfairfaxstorage.blob.core.windows.net/document/policy/046692022100101710000882/apolice_046692022100101710000882_v01.00_ozni.pdf",
            "version": "01.00",
            "count": 275
        }
    ],
    "success": true,
    "executed": "2022-11-14T14:07:30.0741757Z"
}
```



Explicando campos de response da apólice
----------------------------------------

>**Field**: identifier <br>
>**Type**: ```guid``` <br>
>
>identificação unica da apólice em formatdo de ```guid```.

-----------------------------------------------------


>**Field**: policyIdentifier <br>
>**Type**: ```guid``` <br>
>
>identificação unica da apólice em formatdo de ```guid```.

-----------------------------------------------------


>**Field**: number <br>
>**Type**: ```text``` <br>
>
>Número referente a apólice .

-----------------------------------------------------

>**Field**: policyNumber <br>
>**Type**: ```text``` <br>
>
>Número referente a apólice .

-----------------------------------------------------

>**Field**: status <br>
>**Type**: ```text``` <br>
>
>Status da apólice .

-----------------------------------------------------


>**Field**: insuredName <br>
>**Type**: ```text``` <br>
>
>Nome do Segurado .

-----------------------------------------------------

>**Field**: insuredIdentity <br>
>**Type**: ```text``` <br>
>
>Identificação do segurado.

-----------------------------------------------------


>**Field**: modalityText <br>
>**Type**: ```text``` <br>
>
>Modalidade.

-----------------------------------------------------

>**Field**: productText <br>
>**Type**: ```text``` <br>
>
>Produto.

-----------------------------------------------------

>**Field**: vigencyStartedAt <br>
>**Type**: ```date``` <br>
>
>Inicio da vigencia.

-----------------------------------------------------


>**Field**: vigencyExpiredAt <br>
>**Type**: ```date``` <br>
>
>Final da vigencia.

-----------------------------------------------------


>**Field**: createdAt <br>
>**Type**: ```date``` <br>
>
>Data de criação.

-----------------------------------------------------


>**Field**: quotationIdentifier <br>
>**Type**: ```string``` <br>
>
>identificação refente a cotação.

-----------------------------------------------------


>**Field**: quotationDocumentUrl <br>
>**Type**: ```string``` <br>
>
>Url do pdf da apólice.

-----------------------------------------------------

>**Field**: TicketUrl <br>
>**Type**: ```string``` <br>
>
>Url do boleto.

-----------------------------------------------------

>**Field**: version <br>
>**Type**: ```string``` <br>
>
>versão da apólice.

