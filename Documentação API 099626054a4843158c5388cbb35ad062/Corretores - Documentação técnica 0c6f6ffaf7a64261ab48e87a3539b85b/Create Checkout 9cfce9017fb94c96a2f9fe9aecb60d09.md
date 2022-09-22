# Create Checkout

# Qual a ordem do fluxo ?

<aside>
1️⃣ **Primeiro deve-se chamar o endpoint para se criar uma cotação.**

</aside>

<aside>
2️⃣ **Em seguida deve-se chamar o endpoint de proposal com o id da cotação criada.**

</aside>

<aside>
3️⃣ **Para finalizar o fluxo, é necessário prosseguir para o endpoint de checkout.**

</aside>

<aside>
💡 **Endpoint usado para enviar quotation para o checkout**

</aside>

```
**METHOD** POST
**Endpoint**: https://azuh1-br-fairfax-gateway.azure-api.net/partner/api/v1/checkout
**Content**-Type: application/x-www-form-urlencoded
**Ocp-Apim-Subscription-Key**: your apiKey
```

<aside>
💡 **Exemplo de json de request**

</aside>

```json
{
   "quotationIdentifier":"2942faa1-09b8-4345-9bdd-6764c4f1ad35",
   "creditCard":{
      "number":"5431315941306755",
      "name":"samuel emidio",
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

<aside>
💡 **Desmistificando o json de request - part 1**

</aside>

```json
{
   "quotationIdentifier":"2942faa1-09b8-4345-9bdd-6764c4f1ad35",
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

```
**Field**: **QuotationIdentifier**
**Type**: guid
campo obrigatorio
* campo usado para definir qual cotacao sera enviada para checkout, é o mesmo identifier que é recebido quando se cria uma cotacao.
```

```
**Field**: **CreditCard.Number**
**Type**: text
campo obrigatorio
* campo usado para definir o numero do cartao de credito.
```

```
**Field**: **CreditCard.Name**
**Type**: text
campo obrigatorio
* campo usado para definir o nome do titular do cartao
```

```
**Field**: **CreditCard.Identity**
**Type**: text
campo obrigatorio
* campo usado para definir a identificacao do titular do cartao (cpf)
```

```
**Field**: **CreditCard.Cvv**
**Type**: text
campo obrigatorio
* campo usado para definir o codigo de seguranca do cartao (3 digitos)
```

```
**Field**: **CreditCard.ExpiryMonth**
**Type**: integer
campo obrigatorio
* campo usado para definir o mes de expiracao do cartao
```

```
**Field**: **CreditCard.ExpiryYear**
**Type**: integer
campo obrigatorio
* campo usado para definir o ano de expiracao do cartao
```

```
**Field**: **CreditCard.ExpiryYear**
**Type**: integer
campo obrigatorio
* campo usado para definir o ano de expiracao do cartao
```

```
**Field**: **CreditCard.UseCustomerAddress**
**Type**: boolean
campo obrigatorio
* campo usado para definir se sera usado o endereco que é enviado nessa request através do campo **billingAddress,** ou se sera usado o endereco definido anteriormente na criacao da cotacao
**true** = usara endereco enviado na quoation
**false =** usara endereco enviado no **UseCustomerAddress**
```

```
**Field**: **CreditCard.BillingAddress.ZipCode**
**Type**: text
campo obrigatorio
* campo usado para definir o cep
```

```
**Field**: **CreditCard.BillingAddress.Street**
**Type**: text
campo obrigatorio
* campo usado para definir o nome da rua
```

```
**Field**: **CreditCard.BillingAddress.Number**
**Type**: text
campo obrigatorio
* campo usado para definir o numero do endereco
```

```
**Field**: **CreditCard.BillingAddress.Complement**
**Type**: text
campo obrigatorio
* campo usado para definir um complemente para o endereco
```

```
**Field**: **CreditCard.BillingAddress.Neighborhood**
**Type**: text
campo obrigatorio
* campo usado para definir o bairro do endereco
```

```
**Field**: **CreditCard.BillingAddress.City**
**Type**: text
campo obrigatorio
* campo usado para definir a cidade
```

```
**Field**: **CreditCard.BillingAddress.State**
**Type**: text
campo obrigatorio
* campo usado para definir o estado
```