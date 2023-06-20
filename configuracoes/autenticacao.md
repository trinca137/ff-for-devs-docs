# Autenticação e Autorização

{% hint style="warning" %}
Para começar a utilizar nossos recursos, você deve possuir uma _Chave de Acesso_, previamente fornecida pela Fairfax.\
\
A API possui um ambiente de homologação para realização de testes e um ambiente de produção, cada um com sua respectiva _Chave de Acesso_.
{% endhint %}

Para obter autorização no consumo dos recursos da API, você deve enviar a Chave de Acesso no Header da requisição toda vez que fizer chamadas para a API.

A chave de acesso deve ser enviada como valor da propriedade: **Ocp-Apim-Subscription-Key**

```
Ocp-Apim-Subscription-Key: {Chave de Acesso}
```
