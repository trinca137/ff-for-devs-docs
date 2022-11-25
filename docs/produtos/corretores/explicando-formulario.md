>**Code**: PROFESSIONAL-REGISTER<br>
>**Type**: ```text```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
> Pergunta usada para definir o rigistro do profissional



-----------------------------------------------------------------------------------------------




>**Code**: REGISTER-NUMBER-TYPE<br>
>**Type**: ```text```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br> 
> Pergunta usada para definir o tipo de susep. Os possíveis valores para esta pergunta são: <br><br>
>
>   - **FULL =** Susep Plena
>   - **BASIC =** Susepinha



-----------------------------------------------------------------------------------------------




>**Code**: PROFESSION<br>
>**Type**: ```text```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
> Pergunta usada para definir Profissão. Os possíveis valores para esta pergunta são: <br><br>
>
>   - **INSURANCE-BROKER**



-----------------------------------------------------------------------------------------------




>**Code**: CATEGORIES<br>
>**Type**: ```array<string>```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
> Pergunta usada para definir as especialidades Odontológicas, pode-se enviar mais de uma resposta dentro desse array de string, sendo elas:<br><br>
>
>   - **CAR** = Automóvel (disponivel SE REGISTER-NUMBER-TYPE for FULL)<br>
>
>   - **AERONAUTICAL** = Aeronáutico (disponivel SE REGISTER-NUMBER-TYPE for FULL)<br>
>
>   - **HEALTH-INSURANCE** = Planos de Saúde <br>
>
>   - **GUARANTEE** = Garantia (disponivel SE REGISTER-NUMBER-TYPE for FULL)<br>
>
>   - **TRANSPORT** = Transportes (disponivel SE REGISTER-NUMBER-TYPE for FULL)<br>
>
>   - **ENGINEERING-RISKS** = Riscos de Engenharia (disponivel SE REGISTER-NUMBER-TYPE for FULL)<br>
>
>   - **GENERAL-PROFESSIONAL-CIVIL-LIABILITY** = RC Geral e RC Profissional (disponivel SE REGISTER-NUMBER-TYPE for FULL)<br>
>
>   - **BENEFITS-HEALTH-LIFE-PENSION** = Seguro Saúde, Seguro de Vida e/ou Previdência Privada<br>
>
>   - **CONSORTIUM** = Consórcio (disponivel SE REGISTER-NUMBER-TYPE for FULL)<br>
>
>   - **OTHERS** = Demais seguros não listados (disponivel SE REGISTER-NUMBER-TYPE for FULL)<br>



-----------------------------------------------------------------------------------------------




>**Code**: DIGITAL-CERTIFICATION-COVERAGE<br>
>**Type**: ```boolean```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array (se o PERSON-TYPE for LEGAL).</text><br> 
> Pergunta usada para definir se corretora é Certificadora Digital e deseja cobertura para esse serviço?



-----------------------------------------------------------------------------------------------




>**Code**: RETROACTIVITY<br>
>**Type**: ```integer```<br>
> Pergunta usada para definir a retroatividade. Os possíveis valores para esta pergunta são: <br><br>
>
>   - **0** = Sem retroatividade
>   - **1** = 1 ano
>   - **2** = 2 anos
>   - **3** = 3 anos
>   - **4** = 4 anos
>   - **5** = 5 anos



-----------------------------------------------------------------------------------------------




>**Code**: RETROACTIVITY-DATE<br>
>**Type**: ```date```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array (se o RETROACTIVITY for maior que zero).</text><br>
> Pergunta usada para definir a Data de Retroatividade.



-----------------------------------------------------------------------------------------------




>**Code**: RETROACTIVITY-AGREEMENT<br>
>**Type**: ```boolean```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
> Pergunta usada para definir "Entendimento e concordância de retroatividade"
se defida  como true, indica que "**Estou ciente e de acordo que a confirmação da data de retroatividade ocorrerá apenas num eventual sinistro, sendo obrigatório apresentar as apólices anteriores para comprovação. A apólice anterior não ode ter sido cancelada ou ter tido interrupção de vigência.**"



-----------------------------------------------------------------------------------------------





>**Code**: REVENUES<br>
>**Type**: ```text```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array  (se o PERSON-TYPE for LEGAL).</text><br>
> Pergunta usada para definir o Faturamento nos últimos 12 meses. Os possíveis valores para esta pergunta são: <br><br>
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
>   - **10000000.01+**= Acima de R$ 10.000.000,00



-----------------------------------------------------------------------------------------------




>**Code**: CLAIMS<br>
>**Type**: ```text```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
> Pergunta usada para definir se ha Sinistro nos últimos 24 meses. Os possíveis valores para esta pergunta são: <br><br>
>
>   - **0 =** nenhum
>   - **1 =** 1 reclamação
>   - **2** **=** 2 reclamação
>   - **3+** = 3 ou mais



-----------------------------------------------------------------------------------------------




>**Code**: CLAIM-EXPECTATION<br>
>**Type**: ```boolean```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
> Pergunta usada para definir se ha Expectativas de Sinistro



-----------------------------------------------------------------------------------------------




>**Code**: CLAIM-EXPECTATION-THIRD-PARTY<br>
>**Type**: ```text```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array  (se CLAIM-EXPECTATION for TRUE).</text><br>
> Pergunta usada para definir Possíveis terceiros reclamantes de expectativas de sinistro



-----------------------------------------------------------------------------------------------




>**Code**: CLAIM-EXPECTATION-AGREEMENT<br>
>**Type**: ```boolean ```<br>
> Pergunta usada para definir "**Entendimento e concordância de expectativas de sinistro**"
se defida  como true, indica que "**Entendido e acordado que não haverá cobertura securitária para qualquer tipo de fato já conhecido pelo segurado.**"



-----------------------------------------------------------------------------------------------




>**Code**: TERRITORIALITY<br>
>**Type**: ```text```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
> Pergunta usada para definir a Territorialidade. Os possíveis valores para esta pergunta são: <br><br>
>
>   - **BR =** Brasil



-----------------------------------------------------------------------------------------------




>**Code**: SCOPE<br>
>**Type**: ```text```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
> Pergunta usada para definir o Âmbito. Os possíveis valores para esta pergunta são: <br><br>
>
>   - **NATIONAL =** nacional



-----------------------------------------------------------------------------------------------




>**Code**: LIMIT-DEDUCTIBLE<br>
>**Type**: ```array<array<answer>>```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
> Campo para definir Limite e Franquia, veremos mais detalhadamente nas proximas partes.


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


> **Code**: VARIANT-IDENTIFIER <br> **Type**: ```guid``` <br> <text class="aviso">❗ Obrigatório que esteja incluído no array de proposta.</text><br>
>
> Pergunta usada para definir o identificador da variante.


-------------------------------------------------------------------------


> **Code**: LIMIT <br> **Type**: `decimal` <br> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
>
> Os valores possíveis para esta pergunta são:<br><br>
>
> - **30000.0m** = R$ 30.000.
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



-------------------------------------------------------------------------


> **Code**: DEDUCTIBLE <br> 
> **Type**: ```text``` <br> 
> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
>
> Pergunta usada para definir o tipo da franquia. Os valores possíveis para esta pergunta são:<br><br>
>
>   - **DEFAULT**<br>
>   - **INCREASED**<br>
>   - **REDUCED**<br><br>
> 
>**Dependendo do tipo de categoria definido no campo CATEGORIES, o cálculo acontecerá de maneira diferente. Abaixo, você pode ver detalhadamente:**<br><br>
>
>Se for **AERONAUTICAL** (PERSON-TYPE = NATURAL):<br>
>
>    - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>    - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>    - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00 <br><br>
>
>Se for **AERONAUTICAL** (PERSON-TYPE = LEGAL):<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br><br>
>
>Se for **CAR** (PERSON-TYPE = NATURAL):<br>
>
>   - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>   - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00<br><br>
>
>Se for **CAR** (PERSON-TYPE = LEGAL):<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br><br>
>
>Se for **GUARANTEE** (PERSON-TYPE = NATURAL):<br>
>
>   - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>   - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00<br><br>
>
>Se for **GUARANTEE** (PERSON-TYPE = LEGAL):<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br><br>
>
>Se for **GENERAL-PROFESSIONAL-CIVIL-LIABILITY** (PERSON-TYPE = NATURAL):<br>
>
>   - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>   - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00<br><br>
>
>Se for **GENERAL-PROFESSIONAL-CIVIL-LIABILITY** (PERSON-TYPE = LEGAL):<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br><br>
>
>Se for **ENGINEERING-RISKS** (PERSON-TYPE = NATURAL):<br>
>
>   - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>   - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00<br><br>
>
>Se for **ENGINEERING-RISKS** (PERSON-TYPE = LEGAL):<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br><br>
>
>Se for **TRANSPORT** (PERSON-TYPE = NATURAL):<br>
>
>   - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>   - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00<br><br>
>
>Se for **TRANSPORT** (PERSON-TYPE = LEGAL):<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br><br>
>
>Se for **CONSORTIUM** (PERSON-TYPE = NATURAL):<br>
>
>   - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>   - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00<br><br>
>
>Se for **CONSORTIUM** (PERSON-TYPE = LEGAL):<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br><br>
>
>Se for **BENEFITS-HEALTH-LIFE-PENSION** (PERSON-TYPE = NATURAL):<br>
>
>   - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>   - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00<br><br>
>
>Se for **BENEFITS-HEALTH-LIFE-PENSION** (PERSON-TYPE = LEGAL):<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br><br>

>Se for **HEALTH-INSURANCE** (PERSON-TYPE = NATURAL):<br>
>
>   - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>   - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00<br><br>
>
>Se for **HEALTH-INSURANCE** (PERSON-TYPE = LEGAL):<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br><br>
>
>Se for **OTHERS** (PERSON-TYPE = NATURAL):<br>
>
>   - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00 e o máximo de R$ 7.000,00<br>
>   - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00 e o máximo de R$ 8.000,00<br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos com Mínimo de R$ 1.500,00 e o Máximo de R$ 6.000,00<br><br>
>
>Se for **OTHERS** (PERSON-TYPE = LEGAL):<br>
>
>   - **DEFAULT =** Padrão - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 3.000,00<br>
>   - **INCREASED =** Majorada - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 5.000,00 <br>
>   - **REDUCED =** Reduzida - 10% dos Prejuízos Indenizáveis com o Mínimo de R$ 2.500,00<br><br>
