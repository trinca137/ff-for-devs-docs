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

{% code title="Resquest de exemplo" %}
```json
{
   "quotationIdentifier":"2aea86d1-a9e5-4220-ab29-68c3fba8483f",
   "creditCard":{
      "number":"5431315941306755",
      "name":"João da costa",
      "identity":"59989083096",
      "cvv":"789",
      "expiryMonth":10,
      "expiryYear":2027,
      "useCustomerAddress":false,
      "billingAddress":{
         "zipCode":"12433234",
         "street":"rua ficticia",
         "number":"123",
         "complement":"proximo a padaria",
         "neighborhood":"campos",
         "city":"São José dos Campos",
         "state":"Campo belo"
      }
   }
}
```
{% endcode %}

💡 **Explicando o JSON de request**

> **Field**: **QuotationIdentifier**\
> **Type**: `guid`\
> ❗Campo obrigatório.
>
> Campo usado para definir qual cotação será enviada para checkout. É o mesmo identifier que é recebido quando se cria uma cotação.

***

!!! Aviso

```
  As campos referentes a cartão de credito só são obrigatorios caso o tipo de pagamento definido na proposta tenha sido CREDIT-CARD.

  Caso contrario não enviar o objeto de cartão de credito.
```

\
\---------------------------------------------------------------------------------

> **Field**: **CreditCard.Number**\
> **Type**: `text`\
> ❗Campo obrigatório.\
>
>
> Campo usado para definir o número do cartão de crédito.

***

> **Field**: **CreditCard.Name**\
> **Type**: `text`\
> ❗Campo obrigatório.\
>
>
> Campo usado para definir o nome do titular do cartão.

***

> **Field**: **CreditCard.Identity**\
> **Type**: `text`\
> ❗Campo obrigatório.\
>
>
> Campo usado para definir a identificação do titular do cartão (CPF).

***

> **Field**: **CreditCard.Cvv**\
> **Type**: `text`\
> ❗Campo obrigatório.\
>
>
> Campo usado para definir o código de seguranca do cartão (3 digitos).

***

> **Field**: **CreditCard.ExpiryMonth**\
> **Type**: `integer`\
> ❗Campo obrigatório.\
>
>
> Campo usado para definir o mês de expiração do cartão.

***

> **Field**: **CreditCard.ExpiryYear**\
> **Type**: `integer`\
> ❗Campo obrigatório.\
>
>
> Campo usado para definir o ano de expiração do cartão.

***

> **Field**: **CreditCard.UseCustomerAddress**\
> **Type**: `boolean`\
> ❗Campo obrigatório.\
>
>
> Campo usado para definir se será usado o endereço que é enviado nessa request através do campo **billingAddress** ou se será usado o endereço definido anteriormente na criação da cotação.\
>
>
> * **true =** usara endereço enviado na quoation
> * **false =** usara endereço enviado no **UseCustomerAddress**

***

> **Field**: **CreditCard.BillingAddress.ZipCode**\
> **Type**: `text`\
> ❗Campo obrigatório.\
>
>
> Campo usado para definir o CEP.

***

> **Field**: **CreditCard.BillingAddress.Street**\
> **Type**: `text`\
> ❗Campo obrigatório.\
>
>
> Campo usado para definir o nome da rua.

***

> **Field**: **CreditCard.BillingAddress.Number**\
> **Type**: `text`\
> ❗Campo obrigatório.\
>
>
> Campo usado para definir o número do endereço.

***

> **Field**: **CreditCard.BillingAddress.Complement**\
> **Type**: `text`\
> ❗Campo obrigatório.\
>
>
> Campo usado para definir o complemento para o endereço.

***

> **Field**: **CreditCard.BillingAddress.Neighborhood**\
> **Type**: `text`\
> ❗Campo obrigatório.\
>
>
> Campo usado para definir o bairro do endereço.

***

> **Field**: **CreditCard.BillingAddress.City**\
> **Type**: `text`\
> ❗Campo obrigatório.\
>
>
> Campo usado para definir a cidade.

***

> **Field**: **CreditCard.BillingAddress.State**\
> **Type**: `text`\
> ❗Campo obrigatório.\
>
>
> Campo usado para definir o estado.

***

## Response

### Retornos

<pre class="language-json"><code class="lang-json"><strong>{
</strong>    "success": true,
    "executed": "2022-10-13T12:44:38.1296147Z"
}
</code></pre>
