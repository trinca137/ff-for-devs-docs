# Ambientes

A API do 4Devs possui um ambiente de homologação para realização de testes e um ambiente de produção, cada um com sua respectiva Chave de Acesso.

#### <mark style="color:blue;">Homologação</mark>

```url
https://azuh1-br-fairfax-gateway.azure-api.net/partner/
```

{% hint style="warning" %}
Para os checkouts em homologação, é necessário que a cotação tenha um valor **PAR** quando a opção de pagamento for **cartão de crédito** (isso é um requerimento do nosso serviço de pagamento que utilizamos).

Os testes que utilizamos caso queira copiar tudo, já foi preparado para que os cálculos retornem valor par.
{% endhint %}

#### <mark style="color:blue;">Produção</mark>

```url
https://azup-br-fairfax-gateway.azure-api.net/partner/
```

<mark style="color:blue;">**Sobre**</mark>

{% hint style="info" %}
A URL de cada recurso vai conter o parametro **\{{url\_ambiente\}}** como prefixo, que deve ser substituido de acordo com o ambiente para o qual serão feitas as requisições.

Exemplo de chamada: _**`https://azuh1-br-fairfax-gateway.azure-api.net/partner/api/v1/quotation`**_
{% endhint %}
