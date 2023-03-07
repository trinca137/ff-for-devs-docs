# Formulário proposta

{% hint style="info" %}
Esse json abaixo contém as informações onde TODOS os produtos utilizam, na pagina do produto é necessário adicionar os campos (contém exemplo nos produtos)

As respostas estão usando valores referentes ao produto de "Bike".
{% endhint %}

### Explicando formulário

```json
{
   "identifier":"2aea86d1-a9e5-4220-ab29-68c3fba8483f",
   "registerNumber": "100000",
   "operationCode":"BIKE-MULTIPLE-PERIL-PARTNER",
   "answers":[
      {
         "code":"PAYMENT-METHOD",
         "answer":"CREDIT-CARD"
      },
      {
         "code":"INSURED-BIRTH-DATE",
         "answer":"1990-09-08T03:00:00.000Z"
      },
      {
         "code":"DUE-DAY",
         "answer":15
      },
      {
         "code":"PAYMENT-INSTALLMENT-IDENTIFIER",
         "answer":"ee88a83c-1764-4e28-8272-e27d49d32dc8"
      }
   ]
}
```

***

> **Code**: INSURED-BIRTH-DATE\
> **Type**: `date`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir a data de nascimento do segurado.

> **Field:** RegisterNumber
>
> **Tipo:** `text`&#x20;
>
> ❗ Campo Obrigatório.
>
> Campo usado para definir qual o SusepNumber da corretora que está sendo cotada. Neste caso, o susep da corretora é "100000".

> **Code**: PAYMENT-METHOD\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o método de pagamento.\
> Os possíveis valores para esta pergunta são:
>
> * _CREDIT-CARD_
> * _TICKET_

> **Code**: DUE-DAY\
> **Type**: `integer`\
> ❗ Obrigatório que esteja incluído no array. (apenas quando o PAYMENT-METHOD for TICKET).
>
> Pergunta usada para definir o dia de vencimento quando o PAYMENT-METHOD for TICKET (boleto).

> **Code**: PAYMENT-INSTALLMENT-IDENTIFIER\
> **Type**: `guid`\
> ❗ Obrigatório que esteja incluído no array.
>
> O guid que será enviado nesse campo é retornado no array de installments, no retorno do endpoint de criar cotação.
