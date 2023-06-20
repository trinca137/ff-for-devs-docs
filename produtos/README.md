---
description: Uma breve descrição do fluxo de uma contratação e das nossa API.
---

# Produtos

O nosso fluxo de maneira mais resumida para facilitar a integração funciona da seguinte maneira.



**Criar cotação.**

* Realizamos o cálculo e damos inicio a cotação.

**Criar proposta.**

* Na proposta, atualizamos algumas informações, selecionamos o método de pagamento e parcelas e damos ínicio ao processo de finalização do seguro.
* Caso o método de pagamento selecionado seja cartão de crédito a cobrança já é realizada neste processo também.

**Checkout**

* Finalizamos a contratação e enviamos para a fila para gerarmos a apólice do segurado e gerarmos o boleto caso sejá o método de pagamento selecionado.
