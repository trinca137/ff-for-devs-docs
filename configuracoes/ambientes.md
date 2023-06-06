# Ambientes

{% hint style="info" %}


A URL de cada recurso vai conter o parametro **\{{**[**url\_ambiente**](#user-content-fn-1)[^1]**\}}** e **\{{**[**apiVersion**](#user-content-fn-2)[^2]**\}}** como prefixo, que deve ser substituido de acordo com o ambiente para o qual serão feitas as requisições.



Exemplo de chamada:&#x20;

<mark style="color:yellow;">**`https://azuh1-br-fairfax-gateway.azure-api.net/partner/api/v1/quotation/contracting`**</mark>
{% endhint %}

### <mark style="color:blue;">Homologação</mark>

```url
https://azuh1-br-fairfax-gateway.azure-api.net/partner/api
```

{% hint style="warning" %}
Para os checkouts em homologação, é necessário que a cotação tenha um valor **"par"** quando a opção de pagamento for **cartão de crédito** (isso é um requerimento do serviço de pagamento que utilizamos).

Os testes que utilizamos caso queira copiar, já foi preparado para que os cálculos retornem valor **"par"**.
{% endhint %}

### <mark style="color:blue;">Produção</mark> <a href="#producao" id="producao"></a>

```url
https://azup-br-fairfax-gateway.azure-api.net/partner/api
```

[^1]: ```
    https://azuh1-br-fairfax-gateway.azure-api.net/partner/api
    ```

[^2]: v1
