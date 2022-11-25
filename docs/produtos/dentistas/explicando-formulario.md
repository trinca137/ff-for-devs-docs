
> **Code**: PRODUCT </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para saber o produto. Os valores possíveis para esta pergunta são:<br><br>
> 
>  - **PROFESSIONAL-CIVIL-LIABILITY** </br>

------------------------------------------------------------------------

> **Code**: CURRENCY </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para saber a moeda do seguro. Os valores possíveis para esta pergunta são:<br><br>
> 
>  - **BRL** </br>


------------------------------------------------------------------------

> **Code**: PROFESSIONAL-REGISTER <br> >**Type**: `text` <br> > <text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
>
> Pergunta usada para definir o registro do profissional.

---

> **Code**: PROFESSION <br> >**Type**: `text` <br> > <text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
>
> Pergunta usada para definir a profissão do segurado. Os possíveis valores para esta pergunta são: <br><br>
>
> - **DENTIST**</br>

---

> **Code**: CATEGORIES <br> >**Type**: `array<string>` <br> ><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
>
> pergunta usada para definir as especialidades Odontológicas, pode-se enviar mais de uma resposta dentro desse array de string, sendo elas:<br><br>
>
> - **OROFACIAL-HARMONIZATION** = Harmonização Orofacial (HOF) <br>
>
> - **IMPLANTS** = Implantodontia <br>
>
> - **ORALMAXILLOFACIAL-SURGERY** = Cirurgia Bucomaxilofacial <br>
>
> - **FACIAL-FILLERS** = Preenchedores Faciais (não-estético) <br>
>
> - **GENERAL-PROCEDURES** = Procedimentos Clínicos em Geral <br>

---

> **Code**: LEGAL-TYPE <br> >**Type**: `array<string>` <br><text class="aviso">❗ Obrigatorio que esteja incluido no array (se o PERSON-TYPE for LEGAL).</text><br>
>
> pergunta usada para definir Característica da PJ. Os possiveis valores para esta pergunta são:<br><br>
>
> - **PRIVATE-OFFICE** = Consultório Particular <br>
> - **HIGHER-EDUCATION-INSTITUTION** = Instituição de Ensino Superior<br>
> - **DENTAL-PLAN-OPERATOR** = Operadora de Planos Odontológicos <br>
> - **MASTER-FRANCHISOR** = Franqueador Master

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
  "operationCode": "DENTIST-CIVIL-LIABILITY-PARTNER",
  "answers": [
    {
      "code": "MODALITY",
      "answer": "DENTIST-CIVIL-LIABILITY"
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
> Se for **GENERAL-PROCEDURES** (PERSON-TYPE NORMAL):<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 500,00.<br>
> - **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 400,00.<br><br>
>
> Se for **IMPLANTS** (PERSON-TYPE NORMAL):<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 500,00.<br>
> - **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 400,00.<br><br>
>
> Se for **FACIAL-FILLERS** (PERSON-TYPE NORMAL):<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 500,00.<br>
> - **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 400,00.<br><br>
>
> Se for **ORALMAXILLOFACIAL-SURGERY** (PERSON-TYPE NORMAL):<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.500,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.500,00.<br>
> - **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.<br><br>
>
> Se for **OROFACIAL-HARMONIZATION** (PERSON-TYPE NORMAL):<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.<br>
> - **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.500,00.<br><br>
>
> Se for **GENERAL-PROCEDURES**(PERSON-TYPE LEGAL):<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$4.500,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1,500,00.<br>
> - **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.<br><br>
>
> Se for **IMPLANTS** (PERSON-TYPE LEGAL):<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$4.500,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1,500,00.<br>
> - **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.<br><br>
>
> Se for **FACIAL-FILLERS** (PERSON-TYPE LEGAL):<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$4.500,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1,500,00.<br>
> - **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.<br><br>
>
> Se for **ORALMAXILLOFACIAL-SURGERY** (PERSON-TYPE LEGAL):<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.500,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.500,00.<br>
> - **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.<br><br>
>
> Se for **OROFACIAL-HARMONIZATION** (PERSON-TYPE LEGAL):<br>
>
> - **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00.<br>
> - **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,00.<br>
> - **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.<br>
> - **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.500,00.<br><br>
