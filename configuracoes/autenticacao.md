# Autenticação e Autorização

{% hint style="warning" %}
Para começar a utilizar nossos recursos, você deve possuir uma _Chave de Acesso_, previamente fornecida pela Fairfax.
{% endhint %}

Para obter autorização no consumo dos recursos da API, você deve enviar a Chave de Acesso no Header da requisição toda vez que fizer chamadas para a API.

A chave de acesso deve ser enviada como valor da propriedade: **Ocp-Apim-Subscription-Key**

```
Ocp-Apim-Subscription-Key: {Chave de Acesso}
```
