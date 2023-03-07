# Formulário de checkout

{% code title="Resquest para cartão de crédito" %}
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

{% code title="Request para boleto" %}
```json
{
   "quotationIdentifier":"2aea86d1-a9e5-4220-ab29-68c3fba8483f"
}
```
{% endcode %}

💡 **Explicando o JSON de request**

> **Field**: **QuotationIdentifier**\
> **Type**: `guid`\
> ❗Campo obrigatório.
>
> Campo usado para definir qual cotação será enviada para checkout. É o mesmo identifier que é recebido quando se cria uma cotação.

{% hint style="warning" %}
Os campos referentes a cartão de credito so são obrigatorios no caso do tipo de pagamento definido na proposta tenha sido _CREDIT-CARD._
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
> Campo usado para definir o código de seguranca do cartão (3 digitos).

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
> * **true =** usara endereço enviado na quoation
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
