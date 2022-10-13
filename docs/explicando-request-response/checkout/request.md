# Realizar Checkout

#### Endpoint
```
POST: {{url_ambiente}}/v1/checkout
```

💡 **Exemplo de json de request**

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


💡 **Desmistificando o JSON de request - parte 1**



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




> **Field**: **QuotationIdentifier** <br>
> **Type**: ```guid``` <br>
> <text class="aviso">❗Campo obrigatório.</text>
> 
> Campo usado para definir qual cotação será enviada para checkout. É o mesmo identifier que é recebido quando se cria uma cotação.

------------------------------------------------------------------------------


!!! Aviso

      As campos referentes a cartão de credito só são obrigatorios caso o tipo de pagamento definido na proposta tenha sido CREDIT-CARD.
      Caso contrario não enviar o objeto de cartão de credito.

<br>
<br>

---------------------------------------------------------------------------------


> **Field**: **CreditCard.Number** <br>
> **Type**: ```text``` <br>
> <text class="aviso">❗Campo obrigatório.</text>
> 
> Campo usado para definir o número do cartão de crédito.


------------------------------------------------------------------------------


> **Field**: **CreditCard.Name** <br>
> **Type**: ```text```<br>
> <text class="aviso">❗Campo obrigatório.</text>
> 
> Campo usado para definir o nome do titular do cartão.


------------------------------------------------------------------------------



> **Field**: **CreditCard.Identity** <br>
> **Type**: ```text``` <br>
> <text class="aviso">❗Campo obrigatório.</text>
> 
> Campo usado para definir a identificação do titular do cartão (CPF).


------------------------------------------------------------------------------



> **Field**: **CreditCard.Cvv** <br>
> **Type**: ```text``` <br>
> <text class="aviso">❗Campo obrigatório.</text>
> 
> Campo usado para definir o código de seguranca do cartão (3 digitos).


------------------------------------------------------------------------------




> **Field**: **CreditCard.ExpiryMonth** <br>
> **Type**: ```integer``` <br>
> <text class="aviso">❗Campo obrigatório.</text>
> 
> Campo usado para definir o mês de expiração do cartão.




------------------------------------------------------------------------------


> **Field**: **CreditCard.ExpiryYear** <br>
> **Type**: ```integer``` <br>
> <text class="aviso">❗Campo obrigatório.</text>
> 
> Campo usado para definir o ano de expiração do cartão.



------------------------------------------------------------------------------



> **Field**: **CreditCard.UseCustomerAddress** <br>
> **Type**: ```boolean``` <br>
> <text class="aviso">❗Campo obrigatório.</text>
> 
> Campo usado para definir se será usado o endereço que é enviado nessa request através do campo **billingAddress** ou se será usado o endereço definido anteriormente na criação da cotação.
**true** = usara endereco enviado na quoation
**false =** usara endereco enviado no **UseCustomerAddress**


------------------------------------------------------------------------------




> **Field**: **CreditCard.BillingAddress.ZipCode** <br>
> **Type**: ```text``` <br>
> <text class="aviso">❗Campo obrigatório.</text>
> 
> Campo usado para definir o CEP.


------------------------------------------------------------------------------



> **Field**: **CreditCard.BillingAddress.Street** <br>
> **Type**: ```text``` <br>
> <text class="aviso">❗Campo obrigatório.</text>
> 
> Campo usado para definir o nome da rua.



------------------------------------------------------------------------------


> **Field**: **CreditCard.BillingAddress.Number** <br>
> **Type**: ```text``` <br>
> <text class="aviso">❗Campo obrigatório.</text>
> 
> Campo usado para definir o número do endereço.



------------------------------------------------------------------------------



> **Field**: **CreditCard.BillingAddress.Complement** <br>
> **Type**: ```text``` <br>
> <text class="aviso">❗Campo obrigatório.</text>
> 
> Campo usado para definir o complemento para o endereço.



------------------------------------------------------------------------------



> **Field**: **CreditCard.BillingAddress.Neighborhood** <br>
> **Type**: ```text``` <br>
> <text class="aviso">❗Campo obrigatório.</text>
> 
> Campo usado para definir o bairro do endereço.


------------------------------------------------------------------------------



> **Field**: **CreditCard.BillingAddress.City** <br>
> **Type**: ```text```<br>
> <text class="aviso">❗Campo obrigatório.</text>
>  
> Campo usado para definir a cidade.



------------------------------------------------------------------------------


> **Field**: **CreditCard.BillingAddress.State** <br>
> **Type**: ```text``` <br>
> <text class="aviso">❗Campo obrigatório.</text>
> 
> Campo usado para definir o estado.



------------------------------------------------------------------------------