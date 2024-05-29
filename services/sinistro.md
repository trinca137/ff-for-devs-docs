# Sinistro

## Criar sinistro

<mark style="color:green;">`POST`</mark> `{{url_ambiente}}v1/claim`

### Request

```json
{
    "registerNumber":"100000"
    "description":"descricao para o sinistro",
    "policyNumber":"046692022100101710000820",
    "notificationEmail":"email@gmail.com",
    "files":[]
}
```

💡 **Explicando o JSON de request**



> **Field**: registerNumber\
> **Type**: `string`\
> ❗Campo obrigatório.
>
> Campo usado para definir o susep.



> **Field**: description\
> **Type**: `string`\
> ❗Campo obrigatório.\
> ❗Minimo de 20 caracteres.
>
> Campo usado para definir a descrição do sinistro.

***

> **Field**: policyNumber\
> **Type**: `string`\
> ❗Campo obrigatório.
>
> Campo usado para definir o vinculo entre apolice e sinistro.

***

> **Field**: notificationEmail\
> **Type**: `string`\
> ❗Campo obrigatório.
>
> Campo usado para definir o email que recebera uma notificação.

***

> **Field**: files\
> **Type**: `array<string>`
>
> Campo usado para enviar um array de arquivos no formato de base64.

***

#### Response

```json
{
    "protocol": "202212120011",
    "success": true,
    "executed": "2022-12-12T10:56:32.00473372"
}
```

💡 **Explicando o JSON de response**

> **Field**: protocol\
> **Type**: `string`
>
> Numero de protocolo gerado vinculado ao sinistro.

***

## Consultar Sinistro

#### Endpoint

<mark style="color:blue;">`GET`</mark> `{{url_ambiente}}/v1/{registerNumber}/{policyNumber}`

Chamada GET, para consultar o sinistro, passando como route parameter o numero da apolice e susep.

#### Path Parameters

| Name                                             | Type   | Description       |
| ------------------------------------------------ | ------ | ----------------- |
| policyNumber<mark style="color:red;">\*</mark>   |        | Número da apólice |
| registerNumber<mark style="color:red;">\*</mark> | String | Número Susep      |

#### Query Parameters

| Name     | Type   | Description                          |
| -------- | ------ | ------------------------------------ |
| page     | String | Possível passar número da pagina.    |
| protocol | String | Possível passar número do protocolo. |

***

***

#### Response

```json
{
    "totalItems": 12,
    "itemsPerPage": 10,
    "list": [
        {
            "updatedAt": "0001-01-01T00:00:00Z",
            "createdAt": "2022-11-30T15:08:48.8390442Z",
            "description": "descricao para o sinistro",
            "protocol": "202211300001",
            "notificationEmail": "email@gmail.com",
            "files": []
        },
        {
            "updatedAt": "0001-01-01T00:00:00Z",
            "createdAt": "2022-11-30T15:41:28.9666929Z",
            "description": "descricao para o sinistro",
            "protocol": "202211300002",
            "notificationEmail": "email@gmail.com",
            "files": []
        },
        {
            "updatedAt": "0001-01-01T00:00:00Z",
            "createdAt": "2022-12-02T00:51:50.6185862Z",
            "description": "descricao para o sinistro",
            "protocol": "202212010003",
            "notificationEmail": "email@gmail.com",
            "files": [
                {
                    "url": ""
                }
            ]
        },
        {
            "updatedAt": "0001-01-01T00:00:00Z",
            "createdAt": "2022-12-02T00:52:44.29048Z",
            "description": "descricao para o sinistro",
            "protocol": "202212010004",
            "notificationEmail": "email@gmail.com",
            "files": [
                {
                    "url": ""
                }
            ]
        },
        {
            "updatedAt": "0001-01-01T00:00:00Z",
            "createdAt": "2022-12-02T00:58:19.2392716Z",
            "description": "descricao para o sinistro",
            "protocol": "202212010005",
            "notificationEmail": "email@gmail.com",
            "files": [
                {
                    "url": ""
                }
            ]
        },
        {
            "updatedAt": "0001-01-01T00:00:00Z",
            "createdAt": "2022-12-02T00:58:34.6285619Z",
            "description": "descricao para o sinistro",
            "protocol": "202212010006",
            "notificationEmail": "email@gmail.com",
            "files": [
                {
                    "url": ""
                }
            ]
        },
        {
            "updatedAt": "0001-01-01T00:00:00Z",
            "createdAt": "2022-12-02T01:00:57.1733333Z",
            "description": "descricao para o sinistro",
            "protocol": "202212010007",
            "notificationEmail": "email@gmail.com",
            "files": [
                {
                    "url": ""
                }
            ]
        },
        {
            "updatedAt": "0001-01-01T00:00:00Z",
            "createdAt": "2022-12-06T11:50:39.8020657Z",
            "description": "descricao para o sinistro",
            "protocol": "202212060008",
            "notificationEmail": "email@gmail.com",
            "files": [
                {
                    "url": ""
                }
            ]
        },
        {
            "updatedAt": "0001-01-01T00:00:00Z",
            "createdAt": "2022-12-06T11:55:21.9120622Z",
            "description": "descricao para o sinistro",
            "protocol": "202212060009",
            "notificationEmail": "email@gmail.com",
            "files": [
                {
                    "url": ""
                }
            ]
        },
        {
            "updatedAt": "0001-01-01T00:00:00Z",
            "createdAt": "2022-12-08T15:49:17.9276681Z",
            "description": "descricao para o sinistro",
            "protocol": "202212080010",
            "notificationEmail": "email@gmail.com",
            "files": []
        }
    ],
    "success": true,
    "executed": "2022-12-14T11:51:02.8707949Z"
}
```

💡 **Explicando o JSON de response**

> **Field**: list.updatedAt\
> **Type**: `date`
>
> Data de atualização do sinistro.

***

> **Field**: list.createdAt\
> **Type**: `date`
>
> Data de criação do sinistro.

***

> **Field**: list.description\
> **Type**: `string`
>
> Descrição do sinistro.

***

> **Field**: list.protocol\
> **Type**: `string`
>
> Protocolo do sinistro.

***

> **Field**: list.notificationEmail\
> **Type**: `string`
>
> Email que recebeu a notificação do sinistro.

***

> **Field**: list.notificationEmail\
> **Type**: `string`
>
> Email que recebeu a notificação do sinistro.

***

> **Field**: list.files\
> **Type**: `array`
>
> Array contendo os arquivos vinculados ao sinistro.

***

> **Field**: list.files\[].url\
> **Type**: `string`
>
> Link do arquivo.
