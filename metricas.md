---
description: >-
  Nesta página de métricas futuramente terá mais endpoint relacionados as
  métricas que disponibilizamos para o parceiro.
---

# Métricas

Neste endpoint temos um endpoint onde conseguimos identificar quantas chamadas você realizou, quantas deram erros, quais deram sucesso, etc.

{% swagger method="get" path="/infra/metrics" baseUrl="{{url_ambiente}}/v1" summary="Consulta Métricas de Requisições" %}
{% swagger-description %}
Retorna métrica de requisições
{% endswagger-description %}

{% swagger-parameter in="header" name="Ocp-Apim-Subscription-Key" type="md5" required="true" %}
Chave de acesso
{% endswagger-parameter %}

{% swagger-parameter in="query" name="startDate" type="" %}
example: startDate=2023-02-27T00:00:00
{% endswagger-parameter %}

{% swagger-parameter in="query" name="endDate" type="" %}
example: endDate=2023-02-27T23:59:00
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Retorno da métrica de requsições" %}
```json
{
    "value": [
        {
            "apiTimeAvg": 1026.9530200000002,
            "apiTimeMax": 1958.8924000000002,
            "apiTimeMin": 679.7546,
            "bandwidth": 11070,
            "cacheHitCount": 0,
            "cacheMissCount": 0,
            "callCountBlocked": 0,
            "callCountFailed": 0,
            "callCountOther": 0,
            "callCountSuccess": 15,
            "callCountTotal": 15,
            "name": "FF 4 devs",
            "productId": "/products/ff-4-devs",
            "serviceTimeAvg": 1026.4037666666668,
            "serviceTimeMax": 1958.4173,
            "serviceTimeMin": 679.2035000000001,
            "subscriptionId": "/subscriptions/630389ade7ba8e146c1ee625",
            "userId": "/users/1"
        }
    ],
    "count": 1,
    "success": true,
    "executed": "2023-02-28T10:43:36.3911772Z"
    }

```
{% endswagger-response %}
{% endswagger %}



{% hint style="info" %}
Se não for passando nenhum range de datas, por padrão a busca será feita com base no primeiro ao ultimo dia do mes.
{% endhint %}

> **Field**: value\[].apiId\
> **Type**: `string`
>
> Path identificador de API - /apis/{apiId}.

> **Field**: value\[].apiRegion\
> **Type**: `string`
>
> Identificador da região API.

> **Field**: value\[].apiTimeAvg\
> **Type**: number
>
> Tempo médio que levou para processar a solicitção.

> **Field**: value\[].apiTimeMax\
> **Type**: `number`
>
> Tempo maximo que levou para processar a solicitação.

> **Field**: value\[].apiTimeMin\
> **Type**: `number`
>
> Tempo minimo que levou para processar a solicitação.

> **Field**: value\[].bandwidth\
> **Type**: `interger`
>
> Largura de banda consumida.

> **Field**: value\[].cacheHitCount\
> **Type**: `interger`
>
> Numero de vezes em que o conteúdo foi exibido a partir da politica de cache.

> **Field**: value\[].cacheMissCount\
> **Type**: `interger`
>
> Numero de vezes em que o conteúdo foi obtido do backend.

> **Field**: value\[].callCountBlocked\
> **Type**: `interger`
>
> Número de chamadas bloqueadas devido a credenciais inválidas. Isso inclui chamadas que retornam HttpStatusCode.Unauthorized e HttpStatusCode.Forbidden e HttpStatusCode.TooManyRequests.

> **Field**: value\[].callCountFailed\
> **Type**: `interger`
>
> Número de chamadas com falha devido a erros de proxy ou back-end. Isso inclui chamadas que retornam HttpStatusCode.BadRequest(400) e qualquer código entre HttpStatusCode.InternalServerError (500) e 600.

> **Field**: value\[].callCountOther\
> **Type**: `interger`
>
> Número de outras chamadas.

> **Field**: value\[].callCountSuccess\
> **Type**: `interger`
>
> Número de chamadas bem-sucedidas. Isso inclui chamadas que retornam HttpStatusCode <= 301 e HttpStatusCode.NotModified e HttpStatusCode.TemporaryRedirect.

> **Field**: value\[].callCountTotal\
> **Type**: `interger`
>
> Número total de chamadas.

> **Field**: value\[].country\
> **Type**: `string`
>
> País ao qual os dados deste registro estão relacionados.

> **Field**: value\[].interval\
> **Type**: `string`\\
>
> Duração do período de agregação. O intervalo deve ser múltiplo de 15 minutos e não pode ser zero. O valor deve estar no formato ISO 8601.
>
> ([http://en.wikipedia.org/wiki/ISO\_8601#Durations](http://en.wikipedia.org/wiki/ISO\_8601#Durations)).

> **Field**: value\[].name\
> **Type**: `string`
>
> O nome, dependendo do endpoint do relatório, especifica o nome do produto, API, operação ou desenvolvedor.

> **Field**: value\[].operationId\
> **Type**: `string`
>
> Caminho do identificador de operação - /apis/{apiId}/operations/{operationId}.

> **Field**: value\[].productId\
> **Type**: `string`
>
> Caminho do identificador do produto - /products/{productId}.

> **Field**: value\[].region\
> **Type**: `string`
>
> Região do país à qual esses dados de registro estão relacionados.

> **Field**: value\[].serviceTimeAvg\
> **Type**: `number`
>
> Tempo médio que levou para processar a solicitação no backend.

> **Field**: value\[].serviceTimeMax\
> **Type**: `number`
>
> Tempo máximo que levou para processar a solicitação no backend.

> **Field**: value\[].serviceTimeMin\
> **Type**: `number`
>
> Tempo minimo que levou para processar a solicitação no backend.

> **Field**: value\[].subscriptionId\
> **Type**: `string`
>
> Caminho do identificador de assinatura - /subscriptions/{subscriptionId}.

> **Field**: value\[].timestamp\
> **Type**: `string`
>
> Início do período de agregação. A data segue o seguinte formato: aaaa-MM-ddTHH:mm:ssZ conforme especificado pelo padrão ISO 8601.

> **Field**: value\[].userId\
> **Type**: `string`
>
> Caminho do identificador do usuário - /users/{userId}.

> **Field**: value\[].zip\
> **Type**: `string`
>
> Código postal ao qual os dados deste registro estão relacionados.
