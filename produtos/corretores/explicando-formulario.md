### Informações e explicações a mais para o produto de corretores de seguros.

> **Code**: PROFESSIONAL-REGISTER<br>
> **Type**: ```text```<br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
> Pergunta para definir o número de registro do corretor/corretora.

-----------------------------------------------------------------------------------------------

> **Code**: REGISTER-NUMBER-TYPE<br>
> **Type**: ```text```<br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br> 
> Pergunta usada para definir o tipo de susep.<br><br>
> 
> Os possíveis valores para esta pergunta são: <br>
>   
>   - **FULL =** Plena
>   - **BASIC =** Susepinha

-----------------------------------------------------------------------------------------------

> **Code**: CATEGORIES<br>
> **Type**: ```array<string>```<br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
> Pergunta usada para definir as especialidades comercializados pelo corretor<br><br>
> Pode-se enviar mais de uma resposta e depende do tipo de susep escolhido:<br>
> <h6>REGISTER-NUMBER-TYPE for FULL (Plena)</h6><br>
>
>   - **CAR** = Automóvel<br>
>
>   - **HEALTH-INSURANCE** = Planos de Saúde<br>
>
>   - **AERONAUTICAL** = Aeronáutico<br>
>
>   - **CONSORTIUM** = Consórcio<br>
> 
>   - **OTHERS** = Demais seguros não listados<br>
> 
>   - **BENEFITS-HEALTH-LIFE-PENSION** = Seguro Saúde, Seguro de Vida e/ou Previdência Privada<br>
> 
>   - **GUARANTEE** = Garantia<br>
> 
>   - **GENERAL-PROFESSIONAL-CIVIL-LIABILITY** = RC Geral e RC Profissional<br>
> 
>   - **ENGINEERING-RISKS** = Riscos de Engenharia<br>
> 
>   - **TRANSPORT** = Transportes

> <h6>REGISTER-NUMBER-TYPE for BASIC (Susepinha)</h6><br>
>   - **BENEFITS-HEALTH-LIFE-PENSION** = Seguro Saúde, Seguro de Vida e/ou Previdência Privada<br>
>   - **HEALTH-INSURANCE** = Planos de Saúde

-----------------------------------------------------------------------------------------------

> **Code**: DIGITAL-CERTIFICATION-COVERAGE<br>
> **Type**: ```boolean```<br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array se for pessoa jurídica (PERSON-TYPE for LEGAL).</text><br> 
> Pergunta usada para definir se corretora é Certificadora Digital e deseja cobertura para esse serviço.

-----------------------------------------------------------------------------------------------

> **Code**: RETROACTIVITY<br>
> **Type**: ```integer```<br>
> 
> Pergunta usada para definir a retroatividade. Os possíveis valores para esta pergunta são: <br>
>
>   - **0** = Sem retroatividade
>   - **1** = 1 ano
>   - **2** = 2 anos
>   - **3** = 3 anos
>   - **4** = 4 anos
>   - **5** = 5 anos

-----------------------------------------------------------------------------------------------

> **Code**: RETROACTIVITY-AGREEMENT<br>
> **Type**: ```boolean```<br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
> 
> Pergunta usada para definir "Entendimento e concordância de retroatividade" se defida como true, indica que "**Estou ciente e de acordo que a confirmação da data de retroatividade ocorrerá apenas num eventual sinistro, sendo obrigatório apresentar as apólices anteriores para comprovação. A apólice anterior não ode ter sido cancelada ou ter tido interrupção de vigência.**"

-----------------------------------------------------------------------------------------------

> **Code**: REVENUES<br>
> **Type**: ```text```<br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array para pessoa jurídica (se o PERSON-TYPE for LEGAL).</text><br>
> Pergunta usada para definir o Faturamento nos últimos 12 meses.<br><br>
> 
> Os possíveis valores para esta pergunta são: <br>
>
>   - **0.00-100000.00**= Entre R$ 0,00 e R$ 100.000,00
>   - **100000.01-300000.00**= Entre R$ 100.000,01 e R$ 300.000,00
>   - **300000.01-500000.00**= Entre R$ 300.000,01 e R$ 500.000,00
>   - **500000.01-1000000.00**= Entre R$ 500.000,01 e R$ 1.000.000,00
>   - **1000000.01-1500000.00**= Entre R$ 1.000.000,01 e R$ 1.500.000,00
>   - **1500000.01-2000000.00**= Entre R$ 1.500.000,01 e R$ 2.000.000,00
>   - **2000000.01-3000000.00**= Entre R$ 2.000.000,01 e R$ 3.000.000,00
>   - **3000000.01-5000000.00**= Entre R$ 3.000.000,01 e R$ 5.000.000,00
>   - **5000000.01-7500000.00**= Entre R$ 5.000.000,01 e R$ 7.500.000,00
>   - **7500000.01-10000000.00**= Entre R$ 7.500.000,01 e R$ 10.000.000,00

-----------------------------------------------------------------------------------------------

> **Code**: CLAIMS<br>
> **Type**: ```text```<br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
> Pergunta usada para definir se ha Sinistro nos últimos 24 meses.<br><br>
> 
> <text class="definicao">*Um sinistro é qualquer tipo de reclamação extrajudicial, processo judicial civil, criminal ou ético administrativo ou de qualquer tipo similar de pedido de reparação de dano(s) causados(s) pela prestação de seus serviços.* </text><br><br>
> 
> Os possíveis valores para esta pergunta são: <br>
>
>   - **0 =** nenhum
>   - **1 =** 1 reclamação
>   - **2 =** 2 reclamação
>   - **3 ou mais não é possível**

-----------------------------------------------------------------------------------------------

> **Code**: CLAIM-EXPECTATION<br>
> **Type**: ```boolean```<br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
> 
> Pergunta usada para definir se o segurado tem conhecimento ou Expectativas de Sinistro (alguma circunstância que possa gerar um sinistro).

-----------------------------------------------------------------------------------------------

> **Code**: CLAIM-EXPECTATION-THIRD-PARTY<br>
> **Type**: ```text```<br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array (se CLAIM-EXPECTATION for TRUE).</text><br>
> 
> Pergunta usada para definir Possíveis terceiros reclamantes de expectativas de sinistro.

-----------------------------------------------------------------------------------------------

> **Code**: CLAIM-EXPECTATION-AGREEMENT<br>
> **Type**: ```boolean ```<br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array (se CLAIM-EXPECTATION for TRUE).</text><br>
> 
> Pergunta usada para definir "**Entendimento e concordância de expectativas de sinistro**" se defida como true, indica que "**Entendido e acordado que não haverá cobertura securitária para qualquer tipo de fato já conhecido pelo segurado.**"

-----------------------------------------------------------------------------------------------

> **Code**: TERRITORIALITY<br>
> **Type**: ```text```<br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. Atualmente so atendemos corretores/corretoras que atendem no Brasil</text><br>
> Pergunta usada para definir a Territorialidade.<br><br>
> 
> Os possíveis valores para esta pergunta são: <br>
>
>   - **BR =** Brasil

-----------------------------------------------------------------------------------------------

> **Code**: SCOPE<br>
> **Type**: ```text```<br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. Atualmente só atender corretoras/corretores com trabalhos nacionais. </text><br>
> Pergunta usada para definir o Âmbito de trabalho do corretor/corretora.<br><br>
> 
> Os possíveis valores para esta pergunta são: <br>
>
>   - **NATIONAL =** nacional

-----------------------------------------------------------------------------------------------

> **Code**: LIMIT-DEDUCTIBLE<br>
> **Type**: ```array<array<answer>>```<br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
> Campo para definir Limite e Franquia, veremos mais detalhadamente a seguir.

-----------------------------------------------------------------------------------------------

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

> **Code**: VARIANT-IDENTIFIER <br>
> **Type**: ```guid``` <br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array de **proposta**.</text><br>
>
> Pergunta usada para definir o identificador da variante.

-----------------------------------------------------------------------------------------------

> **Code**: LIMIT <br>
> **Type**: ```decimal``` <br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br><br>
> 
> Os valores possíveis para esta pergunta são:<br>
>
> - **30000.0** = R$ 30.000.
> - **50000.0** = R$ 50.000.
> - **100000.0** = R$ 100.000.
> - **150000.0** = R$ 150.000.
> - **200000.0** = R$ 200.000.
> - **250000.0** = R$ 250.000.
> - **300000.0** = R$ 300.000.
> - **400000.0** = R$ 400.000.
> - **500000.0** = R$ 500.000.
> - **600000.0** = R$ 600.000.
> - **700000.0** = R$ 700.000.
> - **800000.0** = R$ 800.000.
> - **900000.0** = R$ 900.000.
> - **1000000.0** = R$ 1.000.000.

-----------------------------------------------------------------------------------------------

> **Code**: DEDUCTIBLE <br> 
> **Type**: ```text``` <br> 
> <text class="aviso">❗ Obrigatório que esteja incluído no array. Essa é uma parte um pouco mais complicada</text><br>
>
> Pergunta usada para definir o tipo da franquia.<br>
> Verifique abaixo como funciona a regra de franquias: <br><br>
> 
> **Dependendo do tipo de categoria definido no campo CATEGORIES e o tipo de PESSOA (física ou jurídica), a resposta será diferente. Abaixo, você pode ver detalhadamente:**<br><br>
> <h6>Para pessoa física (PERSON-TYPE = NATURAL)</h6><br>
> 
> Se for **AERONAUTICAL**<br>
>
>    - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>    - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>    - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00 <br>
>
> Se for **CAR**<br>
>
>   - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>   - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00<br>
> 
> Se for **GUARANTEE**<br>
>
>   - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>   - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00<br>
> 
> Se for **GENERAL-PROFESSIONAL-CIVIL-LIABILITY** <br>
>
>   - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>   - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00<br>
>
>Se for **ENGINEERING-RISKS** <br>
>
>   - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>   - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00<br>
>
> Se for **TRANSPORT** <br>
>
>   - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>   - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00<br>
>
> Se for **CONSORTIUM** <br>
>
>   - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>   - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00<br>
>
> Se for **BENEFITS-HEALTH-LIFE-PENSION** <br>
>
>   - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>   - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00<br>
>
> Se for **HEALTH-INSURANCE** <br>
>
>   - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>   - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00<br>
>
> Se for **OTHERS** <br>
>
>   - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>   - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00<br>
> <h6>Para pessoa jurídica (PERSON-TYPE = LEGAL)</h6><br>
> 
> Se for **AERONAUTICAL**<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br>
>
> Se for **CAR**<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br>
>
> Se for **GUARANTEE**<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br>
>
> Se for **GENERAL-PROFESSIONAL-CIVIL-LIABILITY**<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br>
>
> Se for **ENGINEERING-RISKS**<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br>
>
> Se for **TRANSPORT**<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br>
>
> Se for **CONSORTIUM**<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br>
>
> Se for **BENEFITS-HEALTH-LIFE-PENSION**<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br>

> Se for **HEALTH-INSURANCE**<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br>
>
> Se for **OTHERS**<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00 <br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br>
