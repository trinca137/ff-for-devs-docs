# Explicando formulário de RD Equipamentos.

> **Code**: ITEM-IDENTIFIER\
> **Type**: `guid`\
> ❗ Obrigatório que esteja incluído no array em cada equipamento com um novo.\
> Pergunta para separar cada equipamento por um identificador.



> **Code**: ITEM-TYPE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Qual o tipo do equipamento.

***

> **Code**: BRAND\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Qual a marca do equipamento.

***

> **Code**: SERIAL-NUMBER\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Usada para definir o número de série do equipamento.

***

> **Code**: ORIGIN\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Usada para saber se o equipamento foi produzido em território nacional ou no exterior.\
> \
> Os possíveis valores para serem enviados são:
>
> * **NATIONAL** = Nacional
> * **IMPORTED** = Importado

***

> **Code**: EMISSION-DATE\
> **Type**: `date`
>
> ❗ Obrigatório que esteja incluído no array.
>
> Usada para sabermos a data de emissão da nota fiscal.\
> \
> ❗ Só é aceito equipamentos com nota fiscal emitida em até 60 dias.

***

> **Code**: INVOICE-NUMBER\
> **Type**: `text`
>
> ❗ Obrigatório que esteja incluído no array.
>
> Usada para sabermos o número da nota fiscal.

***

> **Code**: MANUFACTURE-YEAR\
> **Type**: `int`\
> ❗ Obrigatório que esteja incluído no array.
>
> Usada para informar o ano que o equipamento foi feito.\
> \
> São permitidos equipamentos com fabricação do ano anterior ou atual.

***

> **Code**: ITEM-VALUE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir o valor do equipamento.\
> \
> ❗São aceitos equipamentos com valor máximo de ate RS 1.000.000,00 (um milhão). &#x20;

***

> **Code**: TYPE-USE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir o uso do equipamento.\
>
>
> Os possíveis valores para serem enviados são:
>
> * **PERSONAL** = Uso pessoal
> * **LOCATIONS** = Locação para terceiros

***

> **Code**: COVERAGES\
> **Type**: `array<array<answer>>`\
> ❗ Obrigatório que esteja incluído no array.\
> Campo para definir as coberturas para o equipamento (cada equipamento tem suas proprias coberturas).

***

{% hint style="info" %}
***
{% endhint %}

```json
{
            "code": "ITEMS",
            "answer": [
                [
                    {
                        "code": "ITEM-IDENTIFIER",
                        "answer": "3aabec8a-45ca-433a-9954-e6ae7853d299"
                    }
                    .
                    .
                    .
                    {
                        "code": "COVERAGES",
                        "answer": [
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "DAMAGE-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 100.000,00"
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "THEFT-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 100.000,00"
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "OPERATIONS-WATER-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 100.000,00"
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "ELECTRICAL-DAMAGE-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 70.000,00"
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "CIVIL-LIABILITY-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 50.000,00"
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "LOSS-RENT-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 30.000,00"
                                }
                            ],
                            [
                                {
                                    "code": "COVERAGE-TYPE",
                                    "answer": "PAYMENT-THIRD-PARTIES-COVERAGE"
                                },
                                {
                                    "code": "COVERAGE-LIMIT-VALUE",
                                    "answer": "R$ 30.000,00"
                                }
                            ]
                        ]
                    }
                ]
```

{% hint style="info" %}
Como podemos perceber, dentro do array de coverages, temos um outro array com duas perguntas que se repetem por cobertura adicionada.
{% endhint %}

***

> **Code**: COVERAGE-TYPE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array. (Cobertura básica é obrigatoria para qualquer equipamento)\
>
>
> Tipo de coberturas permitidos:
>
> * **DAMAGE-COVERAGE -** Cobertura Básica
> * **THEFT-COVERAGE -** Roubo e/ou furto qualificado
> * **OPERATIONS-WATER-COVERAGE -** Operações em Proximidade de Água
> * **ELECTRICAL-DAMAGE-COVERAGE -** Danos Elétricos
> * **CIVIL-LIABILITY-COVERAGE -** Responsabilidade Civil Equipamentos
> * **LOSS-RENT-COVERAGE -** Perda de Aluguel
> * **PAYMENT-THIRD-PARTIES-COVERAGE -** Pagamento de Aluguel a Terceiros

***

> **Code**: COVERAGE-LIMIT-VALUE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para o valor da cobertura selecionada.\
>
>
> Para cada cobertura temos um limite de valor, segue limite para as respectivas cobeturas.\
>
>
> * **DAMAGE-COVERAGE -** Sempre cobre 100% do valor do equipamento
> * **THEFT-COVERAGE -** Sempre cobre 100% do valor do equipamento
> * **OPERATIONS-WATER-COVERAGE -** Sempre cobre 100% do valor do equipamento
> * **ELECTRICAL-DAMAGE-COVERAGE -** Cobre no máximo 70% do valor do equipamento
> * **CIVIL-LIABILITY-COVERAGE -** Cobre no máximo 50% do valor do equipamento
> * **LOSS-RENT-COVERAGE -** Cobre 30% do valor do equipamento, se os 30% passar dos 100mil, cobre o limite de 100mil
> * **PAYMENT-THIRD-PARTIES-COVERAGE -** Cobre 30% do valor do equipamento, se os 30% passar dos 100mil, cobre o limite de 100mil
