# Checkout

## Request

{% swagger method="post" path="/checkout" baseUrl="{{url_ambiente}}/v1" summary="Criar Checkout" expanded="true" %}
{% swagger-description %}
Realiza o checkout e solicita emissão de apólice.
{% endswagger-description %}

{% swagger-parameter in="header" name="Ocp-Apim-Subscription-Key" type="md5" required="true" %}
chave de acesso da api.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="quotationIdentifier" type="guid" required="true" %}
identificador da cotação.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="creditCard" type="string" %}
informações do cartão de crédito.



_<mark style="color:red;">Obrigatório quando foi informada a opção de pagamento por cartão de crédito, caso contrário, não é necessário o envio no request.</mark>_
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Retorno sucesso." %}
```javascript
{
    "success": true,
    "executed": "2022-10-13T12:44:38.1296147Z"
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Retorno erro com código." %}
```javascript
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
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="Retorno não autorizado." %}
```javascript
{
    "statusCode": 401,
    "message": "Access denied due to missing subscription key. Make sure to include subscription key when making requests to an API."
}
```
{% endswagger-response %}
{% endswagger %}
