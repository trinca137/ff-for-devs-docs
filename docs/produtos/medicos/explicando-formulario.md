> **Code**: PROFESSIONAL-REGISTER <br> >**Type**: `text` <br> > <text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
>
> Pergunta usada para definir o registro do profissional.

---

> **Code**: PROFESSION <br> >**Type**: `text` <br> > <text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
>
> Pergunta usada para definir a profissão do segurado. Os possíveis valores para esta pergunta são: <br><br>
>
> - **DOCTOR**</br>

---

> **Code**: CATEGORIES <br> >**Type**: `array<string>` <br> ><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
>
> Pergunta usada para definir a especialidade médica. Pode-se enviar mais de uma resposta dentro desse array de string (exceto se o PERSON-TYPE for NATURAL), sendo elas:<br><br>
>
> - **NO-SURGERY** = Médico sem Cirurgia e Medicina de Urgência e Emergência (disponível SE PERSON-TYPE for NATURAL).<br>
>
> - **SURGERY-EXCEPT-PLASTIC** = Médico com Cirurgia (exceto Plástico), Anestesiologistas (disponível SE PERSON-TYPE for NATURAL).<br>
>
> - **OBSTETRICIAN** = Obstetra (disponível SE PERSON-TYPE for NATURAL).<br>
>
> - **PLASTIC-SURGERY** = Cirurgião(ã) Plástico(a) (disponível SE PERSON-TYPE for NATURAL).<br>
>
> - **CLINIC-WITHOUT-SURGERY** = Clínicas (outras, sem cirurgia) (disponível SE PERSON-TYPE for LEGAL).<br>
>
> - **PATIENT-TRANSPORT** = Transporte de Pacientes (disponível SE PERSON-TYPE for LEGAL).<br>
>
> - **HOME-CARE** = Home care (disponível SE PERSON-TYPE for LEGAL).<br>
>
> - **SURGERY-CLINIC-EXCEPT-PLASTIC** = Clínica de Cirurgia e/ou Anestesiologia, Exceto Plástica (disponível SE PERSON-TYPE for igual a LEGAL).<br>
>
> - **CLINICAL-LABORATORY** = Laboratório de Análises Clínicas (disponível SE PERSON-TYPE for LEGAL).<br><br>
>
> - **BLOOD-BANK** = Bancos de Sangue (disponível SE PERSON-TYPE for LEGAL).<br>
>
> - **CLINICAL-OBSTETRICS** = Clínica com Obstetrícia (disponível SE PERSON-TYPE for LEGAL).<br>
>
> - **HOSPITAL** = Hospitais (disponível SE PERSON-TYPE for LEGAL).<br>
>
> - **PLASTIC-SURGERY-CLINIC** = Clínica de Cirurgia Plástica (disponível SE PERSON-TYPE for LEGAL).<br>
>
> - **CLINICAL-MULTIDISCIPLINARY** = Clínica Multidisciplinar (disponível SE PERSON-TYPE for LEGAL).

---

> **Code**: RESIDENT <br> >**Type**: `text` <br> > <text class="aviso">❗ Obrigatório que esteja incluído no array (se o PERSON-TYPE for NATURAL ou se CATEGORIES for diferente de PLASTIC-SURGERY).</text><br>
>
> Pergunta usada para definir se o profissional é residente ou não.

---

> **Code**: PROCEDURES-ACTIVITIES <br> >**Type**: `array<string>` <br>
>
> Procedimentos e/ou atividades. Pode-se enviar mais de uma resposta dentro desse array de string, sendo elas:<br><br>
>
> - **AESTHETIC-PROCEDURES** = Procedimentos Estéticos Minimamente Invasivos. <br>
> - **ENDOSCOPY-COLONOSCOPY** = Endoscopia e/ou Colonoscopia. <br>
> - **RADIOTHERAPY-CHEMOTHERAPY-IMMUNOTHERAPY** = Radioterapia e/ou Quimioterapia e/ou Imunoterapia. <br>
> - **AESTHETIC-PROCEDURES-MEDICAL-SPECIALTY** = Procedimentos Estéticos relacionados à Especialidade Médica.

---

> **Code**: RETROACTIVITY <br> >**Type**: `integer` <br>
>
> Pergunta usada para definir a retroatividade. Os possíveis valores para esta pergunta são:<br><br>
>
> - **0** = Sem retroatividade.
> - **1** = 1 ano.
> - **2** = 2 anos.
> - **3** = 3 anos.
> - **4** = 4 anos.
> - **5** = 5 anos.

---

> **Code**: RETROACTIVITY-DATE<br> >**Type**: `date` <br> ><text class="aviso">❗ Obrigatório que esteja incluído no array (se o RETROACTIVITY for maior que zero).</text><br>
>
> Pergunta usada para definir a data de retroatividade.

---

> **Code**: RETROACTIVITY-AGREEMENT <br> >**Type**: `boolean` <br> ><text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
>
> Pergunta usada para definir **"Entendimento e concordância de retroatividade"**. \***\*Se definida como true, indica que "**Estou ciente e de acordo que a confirmação da data de retroatividade ocorrerá apenas num eventual sinistro, sendo obrigatório apresentar as apólices anteriores para comprovação. A apólice anterior não pode ter sido cancelada ou ter tido interrupção de vigência.\*\*"

---

> **Code**: REVENUES <br> >**Type**: `text` <br> ><text class="aviso">❗ Obrigatório que esteja incluído no array (se o PERSON-TYPE for LEGAL).</text><br>
>
> Pergunta usada para definir o Faturamento nos últimos 12 meses. Os possíveis valores para esta pergunta são:<br><br>
>
> - **0.00-100000.00** = Entre R$ 0,00 e R$ 100.000,00.
> - **100000.01-300000.00** = Entre R$ 100.000,01 e R$ 300.000,00.
> - **300000.01-500000.00** = Entre R$ 300.000,01 e R$ 500.000,00.
> - **500000.01-1000000.00** = Entre R$ 500.000,01 e R$ 1.000.000,00.
> - **1000000.01-1500000.00** = Entre R$ 1.000.000,01 e R$ 1.500.000,00.
> - **1500000.01-2000000.00** = Entre R$ 1.500.000,01 e R$ 2.000.000,00.
> - **2000000.01-3000000.00** = Entre R$ 2.000.000,01 e R$ 3.000.000,00.
> - **3000000.01-5000000.00** = Entre R$ 3.000.000,01 e R$ 5.000.000,00.
> - **5000000.01-7500000.00** = Entre R$ 5.000.000,01 e R$ 7.500.000,00.
> - **7500000.01-10000000.00** = Entre R$ 7.500.000,01 e R$ 10.000.000,00.
> - **10000000.01+** = Acima de R$ 10.000.000,00.

---

> **Code**: CLAIMS <br> >**Type**: `text` <br> ><text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
>
> Pergunta usada para definir se houve sinistros nos últimos 24 meses. Os valores possíveis para esta pergunta são: <br><br>
>
> - **0 =** nenhum.
> - **1 =** 1 reclamação.
> - **2** **=** 2 reclamações.
> - **3+** = 3 ou mais.

---

> **Code**: CLAIM-EXPECTATION <br> >**Type**: `boolean` <br> ><text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
>
> Pergunta usada para definir se há expectativas de sinistro.

---

> **Code**: CLAIM-EXPECTATION-THIRD-PARTY <br> >**Type**: `text` <br> ><text class="aviso">❗ Obrigatório que esteja incluído no array (se CLAIM-EXPECTATION for TRUE).</text><br>
>
> Pergunta usada para definir possíveis terceiros reclamantes de expectativas de sinistro.

---

> **Code**: CLAIM-EXPECTATION-AGREEMENT <br> >**Type**: `boolean` <br>
>
> Pergunta usada para definir "**Entendimento e concordância de expectativas de sinistro**". Se definida como true, indica que "**Entendido e acordado que não haverá cobertura securitária para qualquer tipo de fato já conhecido pelo segurado.**"

---

> **Code**: TERRITORIALITY <br> >**Type**: `text` <br> ><text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
>
> Pergunta usada para definir a territorialidade. Os valores possíveis para esta pergunta são: <br><br>
>
> - **BR =** Brasil.

---

> **Code**: SCOPE <br> >**Type**: `text` <br> ><text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
>
> Pergunta usada para definir o âmbito. Os valores possiveis para esta pergunta são: <br><br>
>
> - **NATIONAL** = Nacional.

---

> **Code**: LIMIT-DEDUCTIBLE <br> >**Type**: `array<array<answer>>` <br> ><text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
>
> Campo para definir limite e franquia. Abordaremos mais detalhadamente no decorrer da documentação.

---

> ❕ Como explicado anteriormente, o campo **LIMIT-DEDUCTIBLE** dentro do array de answer tem como finalidade enviar perguntas referentes aos limites e franquias. A seguir, você verá os valores que poderão/deverão estar inclusos nesse array.

```json
{
  "identifier": "7dfac165-a63e-40d8-b6bb-23431e057982",
  "operationCode": "MEDICAL-CIVIL-LIABILITY-PARTNER",
  "answers": [
    {
      "code": "MODALITY",
      "answer": "MEDICAL-CIVIL-LIABILITY"
    },
    {
      "code": "LIMIT-DEDUCTIBLE",
      "answer": [
        [
          {
            "code": "LIMIT",
            "answer": 30000
          },
          {
            "code": "DEDUCTIBLE",
            "answer": "DEFAULT"
          },
          {
            "code": "VARIANT-IDENTIFIER",
            "answer": "17a9aad2-1d5d-49ea-8270-04feb6272394"
          }
        ]
      ]
    }
  ]
}
```

> **Code**: VARIANT-IDENTIFIER <br> >**Type**: `guid` <br> ><text class="aviso">❗ Obrigatório que esteja incluído no array de proposta.</text><br>
>
> Pergunta usada para definir o identificador da variante.

---

> **Code**: LIMIT <br> >**Type**: `decimal` <br> ><text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
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

---

> **Code**: DEDUCTIBLE <br> >**Type**: `text` <br> ><text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
>
> Pergunta usada para definir o tipo da franquia. Os valores possíveis para esta pergunta são:<br><br>
>
> - **DEFAULT**<br>
> - **INCREASED**<br>
> - **REDUCED**<br>
> - **MINIMUM**<br> ><br> >**Dependendo do tipo de categoria definido no campo CATEGORIES, o cálculo acontecerá de maneira diferente. Abaixo, você pode ver detalhadamente:**<br><br>
>
> Se for **NO-SURGERY**:<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.<br>
> - **MINIMUM =** Mínima - Sem franquia.<br><br>
>
> Se for **SURGERY-EXCEPT-PLASTIC**:<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.<br>
> - **MINIMUM =** Mínima - Sem franquia.<br><br>
>
> Se for **OBSTETRICIAN**:<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 500,00.<br>
> - **MINIMUM =** Mínima - 5% dos prejuízos indenizáveis com o mínimo de R$ 200,00.<br><br>
>
> Se for **PLASTIC-SURGERY**:<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,000.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 10.000,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00.<br>
> - **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.<br><br>
>
> Se for **PLASTIC-SURGERY-CLINIC**:<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 15.000,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 20.000,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 10.000,00.<br>
> - **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 7.500,00.<br><br>
>
> Se for **CLINICAL-LABORATORY**:<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 7.000,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 9.000,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,00.<br>
> - **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.000,00.<br><br>
>
> Se for **HOME-CARE**:<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.500,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.<br>
> - **MINIMUM =** Mínima - Sem franquia.<br><br>
>
> Se for **HOSPITAL**:<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 15.000,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 20.000,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 10.000,00.<br>
> - **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 7.500,00.<br><br>
>
> Se for **PATIENT-TRANSPORT**:<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.500,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.<br>
> - **MINIMUM =** Mínima - Sem franquia.<br><br>
>
> Se for **CLINIC-WITHOUT-SURGERY**:<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.500,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 500,00.<br>
> - **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 400,00.<br><br>
>
> Se for **BLOOD-BANK**:<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 15.000,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 20.000,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 10.000,00.<br>
> - **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 7.500,00.<br><br>
>
> Se for **SURGERY-CLINIC-EXCEPT-PLASTIC**:<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.500,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.<br>
> - **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.<br><br>
>
> Se for **CLINICAL-OBSTETRICS**:<br>
>
> - **DEFAULT =** Padrão - 15% dos prejuízos indenizáveis com o mínimo de R$ 500,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.500,00.<br>
> - **REDUCED =** Reduzida - 15% dos prejuízos indenizáveis com o mínimo de R$ 1.500,00.<br>
> - **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.<br><br>
>
> Se for **CLINICAL-MULTIDISCIPLINARY**:<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.500,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.500,00.<br>
> - **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 800,00.<br><br>
