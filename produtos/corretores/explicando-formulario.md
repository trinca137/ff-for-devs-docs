# Explicando formulário de Corretores.

> **Code**: PROFESSIONAL-REGISTER\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta para definir o número de registro do corretor/corretora.

***

> **Code**: REGISTER-NUMBER-TYPE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir o tipo de susep.
>
>
>
> Os possíveis valores para esta pergunta são:
>
> * **FULL =** Plena
> * **BASIC =** Susepinha

***

> **Code**: CATEGORIES\
> **Type**: `array<string>`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir as especialidades comercializados pelo corretor\
> \
> Pode-se enviar mais de uma resposta e depende do tipo de susep escolhido:
>
> **REGISTER-NUMBER-TYPE for FULL (Plena)**
>
>
>
> * **CAR** = Automóvel
> * **HEALTH-INSURANCE** = Planos de Saúde
> * **AERONAUTICAL** = Aeronáutico
> * **CONSORTIUM** = Consórcio
> * **OTHERS** = Demais seguros não listados
> * **BENEFITS-HEALTH-LIFE-PENSION** = Seguro Saúde, Seguro de Vida e/ou Previdência Privada
> * **GUARANTEE** = Garantia
> * **GENERAL-PROFESSIONAL-CIVIL-LIABILITY** = RC Geral e RC Profissional
> * **ENGINEERING-RISKS** = Riscos de Engenharia
> * **TRANSPORT** = Transportes

> **REGISTER-NUMBER-TYPE for BASIC (Susepinha)**
>
> \
> \- \*\*BENEFITS-HEALTH-LIFE-PENSION\*\* = Seguro Saúde, Seguro de Vida e/ou Previdência Privada\
> \- \*\*HEALTH-INSURANCE\*\* = Planos de Saúde

***

> **Code**: DIGITAL-CERTIFICATION-COVERAGE\
> **Type**: `boolean`\
> ❗ Obrigatório que esteja incluído no array se for pessoa jurídica (PERSON-TYPE for LEGAL).\
> Pergunta usada para definir se corretora é Certificadora Digital e deseja cobertura para esse serviço.

***

> **Code**: RETROACTIVITY\
> **Type**: `integer`
>
> Pergunta usada para definir a retroatividade. Os possíveis valores para esta pergunta são:\\
>
> * **0** = Sem retroatividade
> * **1** = 1 ano
> * **2** = 2 anos
> * **3** = 3 anos
> * **4** = 4 anos
> * **5** = 5 anos

***

> **Code**: RETROACTIVITY-AGREEMENT\
> **Type**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir "Entendimento e concordância de retroatividade" se defida como true, indica que "**Estou ciente e de acordo que a confirmação da data de retroatividade ocorrerá apenas num eventual sinistro, sendo obrigatório apresentar as apólices anteriores para comprovação. A apólice anterior não ode ter sido cancelada ou ter tido interrupção de vigência.**"

***

> **Code**: REVENUES\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array para pessoa jurídica (se o PERSON-TYPE for LEGAL).\
> Pergunta usada para definir o Faturamento nos últimos 12 meses.\
>
>
> Os possíveis valores para esta pergunta são:
>
> * **0.00-100000.00**= Entre R$ 0,00 e R$ 100.000,00
> * **100000.01-300000.00**= Entre R$ 100.000,01 e R$ 300.000,00
> * **300000.01-500000.00**= Entre R$ 300.000,01 e R$ 500.000,00
> * **500000.01-1000000.00**= Entre R$ 500.000,01 e R$ 1.000.000,00
> * **1000000.01-1500000.00**= Entre R$ 1.000.000,01 e R$ 1.500.000,00
> * **1500000.01-2000000.00**= Entre R$ 1.500.000,01 e R$ 2.000.000,00
> * **2000000.01-3000000.00**= Entre R$ 2.000.000,01 e R$ 3.000.000,00
> * **3000000.01-5000000.00**= Entre R$ 3.000.000,01 e R$ 5.000.000,00
> * **5000000.01-7500000.00**= Entre R$ 5.000.000,01 e R$ 7.500.000,00
> * **7500000.01-10000000.00**= Entre R$ 7.500.000,01 e R$ 10.000.000,00

***

> **Code**: CLAIMS\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir se ha Sinistro nos últimos 24 meses.\
>
>
> _Um sinistro é qualquer tipo de reclamação extrajudicial, processo judicial civil, criminal ou ético administrativo ou de qualquer tipo similar de pedido de reparação de dano(s) causados(s) pela prestação de seus serviços._\
>
>
> Os possíveis valores para esta pergunta são:
>
> * **0 =** nenhum
> * **1 =** 1 reclamação
> * **2 =** 2 reclamação
> * **3 ou mais não é possível**

***

> **Code**: CLAIM-EXPECTATION\
> **Type**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir se o segurado tem conhecimento ou Expectativas de Sinistro (alguma circunstância que possa gerar um sinistro).

***

> **Code**: CLAIM-EXPECTATION-THIRD-PARTY\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array (se CLAIM-EXPECTATION for TRUE).
>
> Pergunta usada para definir Possíveis terceiros reclamantes de expectativas de sinistro.

***

> **Code**: CLAIM-EXPECTATION-AGREEMENT\
> **Type**: `boolean`\
> ❗ Obrigatório que esteja incluído no array (se CLAIM-EXPECTATION for TRUE).
>
> Pergunta usada para definir "**Entendimento e concordância de expectativas de sinistro**" se defida como true, indica que "**Entendido e acordado que não haverá cobertura securitária para qualquer tipo de fato já conhecido pelo segurado.**"

***

> **Code**: TERRITORIALITY\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array. Atualmente so atendemos corretores/corretoras que atendem no Brasil\
> Pergunta usada para definir a Territorialidade.\
>
>
> Os possíveis valores para esta pergunta são:
>
> * **BR =** Brasil

***

> **Code**: SCOPE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array. Atualmente só atender corretoras/corretores com trabalhos nacionais.\
> Pergunta usada para definir o Âmbito de trabalho do corretor/corretora.\
>
>
> Os possíveis valores para esta pergunta são:
>
> * **NATIONAL =** nacional

***

> **Code**: LIMIT-DEDUCTIBLE\
> **Type**: `array<array<answer>>`\
> ❗ Obrigatório que esteja incluído no array.\
> Campo para definir Limite e Franquia, veremos mais detalhadamente a seguir.

***

> ❕ Como explicado anteriormente, o campo **LIMIT-DEDUCTIBLE** dentro do array de answer tem como finalidade enviar perguntas referentes aos limites e franquias. A seguir, você verá os valores que poderão/deverão estar inclusos nesse array.

```json
{
   "identifier":"2942faa1-09b8-4345-9bdd-6764c4f1ad35",
   "operationCode":"INSURANCE-BROKER-CIVIL-LIABILITY-PARTNER",
   "answers":[
      {
         "code":"MODALITY",
         "answer":"INSURANCE-BROKER-CIVIL-LIABILITY"
      },
      {
         "code":"LIMIT-DEDUCTIBLE",
         "answer":[
            [
               {
                  "code":"LIMIT",
                  "answer":100000
               },
               {
                  "code":"DEDUCTIBLE",
                  "answer":"DEFAULT"
               },
               {
                  "code":"VARIANT-IDENTIFIER",
                  "answer":"c338d8ce-d7fb-4968-990f-5b400f138283"
               }
            ]
         ]
      }
   ]
}
```

> **Code**: VARIANT-IDENTIFIER\
> **Type**: `guid`\
> ❗ Obrigatório que esteja incluído no array de **proposta**.
>
> Pergunta usada para definir o identificador da variante.

***

> **Code**: LIMIT\
> **Type**: `decimal`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Os valores possíveis para esta pergunta são:
>
> * **30000.0** = R$ 30.000.
> * **50000.0** = R$ 50.000.
> * **100000.0** = R$ 100.000.
> * **150000.0** = R$ 150.000.
> * **200000.0** = R$ 200.000.
> * **250000.0** = R$ 250.000.
> * **300000.0** = R$ 300.000.
> * **400000.0** = R$ 400.000.
> * **500000.0** = R$ 500.000.
> * **600000.0** = R$ 600.000.
> * **700000.0** = R$ 700.000.
> * **800000.0** = R$ 800.000.
> * **900000.0** = R$ 900.000.
> * **1000000.0** = R$ 1.000.000.

***

> **Code**: DEDUCTIBLE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array. Essa é uma parte um pouco mais complicada\\
>
> Pergunta usada para definir o tipo da franquia.\
> Verifique abaixo como funciona a regra de franquias:\
>
>
> **Dependendo do tipo de categoria definido no campo CATEGORIES e o tipo de PESSOA (física ou jurídica), a resposta será diferente. Abaixo, você pode ver detalhadamente:**\
>
>
> **Para pessoa física (PERSON-TYPE = NATURAL)**
>
>
>
> Se for **AERONAUTICAL**
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00
>
> Se for **CAR**
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00
>
> Se for **GUARANTEE**
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00
>
> Se for **GENERAL-PROFESSIONAL-CIVIL-LIABILITY**
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00
>
> Se for **ENGINEERING-RISKS**
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00
>
> Se for **TRANSPORT**
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00
>
> Se for **CONSORTIUM**
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00
>
> Se for **BENEFITS-HEALTH-LIFE-PENSION**
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00
>
> Se for **HEALTH-INSURANCE**
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00
>
> Se for **OTHERS**
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00
>
> **Para pessoa jurídica (PERSON-TYPE = LEGAL)**
>
>
>
> Se for **AERONAUTICAL**
>
> * **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
> * **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00
>
> Se for **CAR**
>
> * **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
> * **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00
>
> Se for **GUARANTEE**
>
> * **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
> * **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00
>
> Se for **GENERAL-PROFESSIONAL-CIVIL-LIABILITY**
>
> * **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
> * **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00
>
> Se for **ENGINEERING-RISKS**
>
> * **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
> * **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00
>
> Se for **TRANSPORT**
>
> * **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
> * **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00
>
> Se for **CONSORTIUM**
>
> * **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
> * **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00
>
> Se for **BENEFITS-HEALTH-LIFE-PENSION**
>
> * **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
> * **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00

> Se for **HEALTH-INSURANCE**
>
> * **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
> * **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00
>
> Se for **OTHERS**
>
> * **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00
> * **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00
> * **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00
