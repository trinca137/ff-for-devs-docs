

>**Code**: PROFESSIONAL-REGISTER<br>
>**Type**: ```text```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
> Pergunta usada para definir o rigistro do profissional



**Code**: REGISTER-NUMBER-TYPE<br>
**Type**: ```text```<br>
<text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br> 
* pergunta usada para definir o tipo de susep
os possiveis valores para esta pergunta são:
**FULL =** Susep Plena
**BASIC =** Susepinha



**Code**: PROFESSION<br>
**Type**: ```text```<br>
<text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
* pergunta usada para definir Profissão
os possiveis valores para esta pergunta são:
**INSURANCE-BROKER**



**Code**: CATEGORIES<br>
**Type**: ```array<string>```<br>
<text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
* pergunta usada para definir as especialidades Odontológicas, pode-se enviar mais de uma resposta dentro desse array de string, sendo elas:

**CAR** = Automóvel (disponivel SE REGISTER-NUMBER-TYPE for FULL)

**AERONAUTICAL** = Aeronáutico (disponivel SE REGISTER-NUMBER-TYPE for FULL)

**HEALTH-INSURANCE** = Planos de Saúde 

**GUARANTEE** = Garantia (disponivel SE REGISTER-NUMBER-TYPE for FULL)

**TRANSPORT** = Transportes (disponivel SE REGISTER-NUMBER-TYPE for FULL)

**ENGINEERING-RISKS** = Riscos de Engenharia (disponivel SE REGISTER-NUMBER-TYPE for FULL)

**GENERAL-PROFESSIONAL-CIVIL-LIABILITY** = RC Geral e RC Profissional (disponivel SE REGISTER-NUMBER-TYPE for FULL)

**BENEFITS-HEALTH-LIFE-PENSION** = Seguro Saúde, Seguro de Vida e/ou Previdência Privada

**CONSORTIUM** = Consórcio (disponivel SE REGISTER-NUMBER-TYPE for FULL)

**OTHERS** = Demais seguros não listados (disponivel SE REGISTER-NUMBER-TYPE for FULL)



**Code**: DIGITAL-CERTIFICATION-COVERAGE<br>
**Type**: ```boolean```<br>
<text class="aviso">❗ Obrigatório que esteja incluido no array (se o PERSON-TYPE for LEGAL).</text><br> 
* pergunta usada para definir se corretora é Certificadora Digital e deseja cobertura para esse serviço?



**Code**: RETROACTIVITY<br>
**Type**: ```integer```<br>
* pergunta usada para definir a retroatividade.
os possiveis valores para esta pergunta são:
**0** = Sem retroatividade
**1** = 1 ano
**2** = 2 anos
**3** = 3 anos
**4** = 4 anos
**5** = 5 anos



**Code**: RETROACTIVITY-DATE<br>
**Type**: ```date```<br>
<text class="aviso">❗ Obrigatório que esteja incluido no array (se o RETROACTIVITY for maior que zero).</text><br>
* pergunta usada para definir a Data de Retroatividade.



**Code**: RETROACTIVITY-AGREEMENT<br>
**Type**: ```boolean```<br>
<text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
* pergunta usada para definir "Entendimento e concordância de retroatividade"
se defida  como true, indica que "**Estou ciente e de acordo que a confirmação da data de retroatividade ocorrerá apenas num eventual sinistro, sendo obrigatório apresentar as apólices anteriores para comprovação. A apólice anterior não ode ter sido cancelada ou ter tido interrupção de vigência.**"




**Code**: REVENUES<br>
**Type**: ```text```<br>
<text class="aviso">❗ Obrigatório que esteja incluido no array  (se o PERSON-TYPE for LEGAL).</text><br>
* pergunta usada para definir o Faturamento nos últimos 12 meses.
os possiveis valores para esta pergunta são:
0.00-100000.00 ****= Entre R$ 0,00 e R$ 100.000,00
100000.01-300000.00 ****= Entre R$ 100.000,01 e R$ 300.000,00
300000.01-500000.00 ****= Entre R$ 300.000,01 e R$ 500.000,00
500000.01-1000000.00 ****= Entre R$ 500.000,01 e R$ 1.000.000,00
1000000.01-1500000.00 ****= Entre R$ 1.000.000,01 e R$ 1.500.000,00
1500000.01-2000000.00 ****= Entre R$ 1.500.000,01 e R$ 2.000.000,00
2000000.01-3000000.00 ****= Entre R$ 2.000.000,01 e R$ 3.000.000,00
3000000.01-5000000.00 ****= Entre R$ 3.000.000,01 e R$ 5.000.000,00
5000000.01-7500000.00 ****= Entre R$ 5.000.000,01 e R$ 7.500.000,00
7500000.01-10000000.00 ****= Entre R$ 7.500.000,01 e R$ 10.000.000,00
10000000.01+ ****= Acima de R$ 10.000.000,00



**Code**: CLAIMS<br>
**Type**: ```text```<br>
<text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
* pergunta usada para definir se ha Sinistro nos últimos 24 meses.
os valores possiveis para esta pergunta sao:
**0 =** nenhum
**1 =** 1 reclamação
**2** **=** 2 reclamação
**3+** = 3 ou mais



**Code**: CLAIM-EXPECTATION<br>
**Type**: ```boolean```<br>
<text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
* pergunta usada para definir se ha Expectativas de Sinistro



**Code**: CLAIM-EXPECTATION-THIRD-PARTY<br>
**Type**: ```text```<br>
<text class="aviso">❗ Obrigatório que esteja incluido no array  (se CLAIM-EXPECTATION for TRUE).</text><br>
* pergunta usada para definir Possíveis terceiros reclamantes de expectativas de sinistro



**Code**: CLAIM-EXPECTATION-AGREEMENT<br>
**Type**: ```boolean ```<br>
* pergunta usada para definir "**Entendimento e concordância de expectativas de sinistro**"
se defida  como true, indica que "**Entendido e acordado que não haverá cobertura securitária para qualquer tipo de fato já conhecido pelo segurado.**"



**Code**: TERRITORIALITY<br>
**Type**: ```text```<br>
<text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
* pergunta usada para definir a Territorialidade
os valores possiveis para esta pergunta sao:
**BR =** Brasil



**Code**: SCOPE<br>
**Type**: ```text```<br>
<text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
* pergunta usada para definir o Âmbito
os valores possiveis para esta pergunta sao:
**NATIONAL =** nacional



**Code**: LIMIT-DEDUCTIBLE<br>
**Type**: ```array<array<answer>>```<br>
<text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
* Campo para definir Limite e Franquia, veremos mais detalhadamente nas proximas partes.
