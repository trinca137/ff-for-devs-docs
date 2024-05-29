# Checkout

## Inicia processo de checkout

<mark style="color:green;">`POST`</mark> `{{url_ambiente}}/{{version}}/checkout`

Envia a cotação para a fila de checkout para gerarmos a apólice.

#### Headers

| Name                                                        | Type | Description             |
| ----------------------------------------------------------- | ---- | ----------------------- |
| Ocp-Apim-Subscription-Key<mark style="color:red;">\*</mark> | key  | chave de acesso da api. |

{% tabs %}
{% tab title="200: OK Retorno sucesso." %}
Simples retorno informando true ou false:

```json
{
    "success": true,
    "executed": "2023-05-25T20:27:49.1872173Z"
}
```
{% endtab %}

{% tab title="401: Unauthorized Caso não envie uma "chave" ou envie uma inválida" %}
{% code overflow="wrap" %}
```json
{
    "statusCode": 401,
    "message": "Access denied due to invalid subscription key. Make sure to provide a valid key for an active subscription."
}
```
{% endcode %}
{% endtab %}

{% tab title="400: Bad Request Falha ao encontrar a cotação " %}
```json
{
    "success": false,
    "executed": "2023-05-25T20:27:49.1872173Z",
    "errors": [
        {
            "code": "QUOTATION-NOT-FOUND"
        }
    ]
}
```
{% endtab %}

{% tab title="500: Internal Server Error Erro de aplicação/servidor" %}

{% endtab %}
{% endtabs %}

## Request

<details>

<summary>Request para Cartão de Crédito</summary>

```json
{
   "registerNumber:"",
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

</details>

<details>

<summary>Request para Boleto</summary>

```
{
   "registerNumber":"",
   "quotationIdentifier":"2aea86d1-a9e5-4220-ab29-68c3fba8483f"
}
```

</details>

## **Detalhando campos de envio.**

> **Code**: **RegisterNumber**\
> **Type**: text\
> ❗Campo obrigatório.
>
> Número Susep

> **Code**: **Quotation Identifier**\
> **Type**: `guid`\
> ❗Campo obrigatório.
>
> Campo usado para definir qual cotação será enviada para checkout. É o mesmo identifier que é recebido quando se cria uma cotação.

{% hint style="warning" %}
Os campos referentes a cartão de credito so são obrigatorios no caso do tipo de pagamento definido na proposta tenha sido cartão de crédito ( PAYMENT-TYPE = _CREDIT-CARD )._
{% endhint %}

> **Field**: **CreditCard.Number**\
> **Type**: `text`\
> ❗Campo obrigatório.
>
> Campo usado para definir o número do cartão de crédito.

***

> **Field**: **CreditCard.Name**\
> **Type**: `text`\
> ❗Campo obrigatório.
>
> Campo usado para definir o nome do titular do cartão.

***

> **Field**: **CreditCard.Identity**\
> **Type**: `text`\
> ❗Campo obrigatório.
>
> Campo usado para definir a identificação do titular do cartão (CPF).

***

> **Field**: **CreditCard.Cvv**\
> **Type**: `text`\
> ❗Campo obrigatório.
>
> Campo usado para definir o código de segurança do cartão (3 digitos).

***

> **Field**: **CreditCard.ExpiryMonth**\
> **Type**: `integer`\
> ❗Campo obrigatório.
>
> Campo usado para definir o mês de expiração do cartão.

***

> **Field**: **CreditCard.ExpiryYear**\
> **Type**: `integer`\
> ❗Campo obrigatório.
>
> Campo usado para definir o ano de expiração do cartão.

***

> **Field**: **CreditCard.UseCustomerAddress**\
> **Type**: `boolean`\
> ❗Campo obrigatório.
>
> Campo usado para definir se será usado o endereço que é enviado nessa request através do campo **billingAddress** ou se será usado o endereço definido anteriormente na criação da cotação.
>
> * **true =** usara endereço enviado na cotação
> * **false =** usara endereço enviado no **UseCustomerAddress**

***

> **Field**: **CreditCard.BillingAddress.ZipCode**\
> **Type**: `text`\
> ❗Campo obrigatório.
>
> Campo usado para definir o CEP.

***

> **Field**: **CreditCard.BillingAddress.Street**\
> **Type**: `text`\
> ❗Campo obrigatório.
>
> Campo usado para definir o nome da rua.

***

> **Field**: **CreditCard.BillingAddress.Number**\
> **Type**: `text`\
> ❗Campo obrigatório.
>
> Campo usado para definir o número do endereço.

***

> **Field**: **CreditCard.BillingAddress.Complement**\
> **Type**: `text`\
> ❗Campo obrigatório.
>
> Campo usado para definir o complemento para o endereço.

***

> **Field**: **CreditCard.BillingAddress.Neighborhood**\
> **Type**: `text`\
> ❗Campo obrigatório.
>
> Campo usado para definir o bairro do endereço.

***

> **Field**: **CreditCard.BillingAddress.City**\
> **Type**: `text`\
> ❗Campo obrigatório.
>
> Campo usado para definir a cidade.

***

> **Field**: **CreditCard.BillingAddress.State**\
> **Type**: `text`\
> ❗Campo obrigatório.
>
> Campo usado para definir o estado.
