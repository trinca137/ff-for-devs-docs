# Explicando formulário de Dentistas.

> **Code**: PROFESSIONAL-REGISTER\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir o registro do profissional.

***

> **Code**: CATEGORIES\
> **Type**: `array<string>`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir as especialidades Odontológicas.\
>
>
> Pode-se enviar mais de uma resposta dentro desse array de string, sendo elas:\
>
>
> * **OROFACIAL-HARMONIZATION** = Harmonização Orofacial (HOF)\
>
> * **IMPLANTS** = Implantodontia\
>
> * **ORALMAXILLOFACIAL-SURGERY** = Cirurgia Bucomaxilofacial\
>
> * **FACIAL-FILLERS** = Preenchedores Faciais (não-estético)\
>
> * **GENERAL-PROCEDURES** = Procedimentos Clínicos em Geral

***

> **Code**: LEGAL-TYPE\
> **Type**: `array<string>`\
> ❗ Obrigatorio que esteja incluído no array se for pessoa jurídica (PERSON-TYPE for LEGAL).\
>
>
> Pergunta usada para definir Característica da PJ.\
>
>
> Os possiveis valores para esta pergunta são:\
>
>
> * **PRIVATE-OFFICE** = Consultório Particular\
>
> * **HIGHER-EDUCATION-INSTITUTION** = Instituição de Ensino Superior\
>
> * **DENTAL-PLAN-OPERATOR** = Operadora de Planos Odontológicos\
>
> * **MASTER-FRANCHISOR** = Franqueador Master

***

> **Code**: RETROACTIVITY\
> **Type**: `integer`\
>
>
> Pergunta usada para definir a retroatividade.\
>
>
> Os possíveis valores para esta pergunta são:\
>
>
> * **0** = Sem retroatividade.
> * **1** = 1 ano.
> * **2** = 2 anos.
> * **3** = 3 anos.
> * **4** = 4 anos.
> * **5** = 5 anos.

***

> **Code**: RETROACTIVITY-AGREEMENT\
> **Type**: `boolean`\
> ❗ Obrigatório que esteja incluído no array. (se o RETROACTIVITY for maior que zero).\
>
>
> Pergunta usada para definir **"Entendimento e concordância de retroatividade"**. Se definida como true, indica que _**Estou ciente e de acordo que a confirmação da data de retroatividade ocorrerá apenas num eventual sinistro, sendo obrigatório apresentar as apólices anteriores para comprovação. A apólice anterior não pode ter sido cancelada ou ter tido interrupção de vigência.**_

***

> **Code**: REVENUES\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array se for pessoa jurídica (PERSON-TYPE for LEGAL).\
>
>
> Pergunta usada para definir o Faturamento nos últimos 12 meses.\
>
>
> Os possíveis valores para esta pergunta são:\
>
>
> * **0.00-100000.00** = Entre R$ 0,00 e R$ 100.000,00.
> * **100000.01-300000.00** = Entre R$ 100.000,01 e R$ 300.000,00.
> * **300000.01-500000.00** = Entre R$ 300.000,01 e R$ 500.000,00.
> * **500000.01-1000000.00** = Entre R$ 500.000,01 e R$ 1.000.000,00.
> * **1000000.01-1500000.00** = Entre R$ 1.000.000,01 e R$ 1.500.000,00.
> * **1500000.01-2000000.00** = Entre R$ 1.500.000,01 e R$ 2.000.000,00.
> * **2000000.01-3000000.00** = Entre R$ 2.000.000,01 e R$ 3.000.000,00.
> * **3000000.01-5000000.00** = Entre R$ 3.000.000,01 e R$ 5.000.000,00.
> * **5000000.01-7500000.00** = Entre R$ 5.000.000,01 e R$ 7.500.000,00.
> * **7500000.01-10000000.00** = Entre R$ 7.500.000,01 e R$ 10.000.000,00.

***

> **Code**: CLAIMS\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir se houve sinistros nos últimos 24 meses.\
>
>
> Os valores possíveis para esta pergunta são:\
>
>
> * **0 =** nenhum.
> * **1 =** 1 reclamação.
> * **2 =** 2 reclamações.

***

> **Code**: CLAIM-EXPECTATION\
> **Type**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir se o segurado tem conhecimento ou Expectativas de Sinistro (alguma circunstância que possa gerar um sinistro).

***

> **Code**: CLAIM-EXPECTATION-THIRD-PARTY\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array (se CLAIM-EXPECTATION for TRUE).\
>
>
> Pergunta usada para definir possíveis terceiros reclamantes de expectativas de sinistro.

***

> **Code**: CLAIM-EXPECTATION-AGREEMENT\
> **Type**: `boolean`\
> ❗ Obrigatório que esteja incluído no array (se CLAIM-EXPECTATION for TRUE).\
>
>
> Pergunta usada para definir "**Entendimento e concordância de expectativas de sinistro**". Se definida como true, indica que "**Entendido e acordado que não haverá cobertura securitária para qualquer tipo de fato já conhecido pelo segurado.**"

***

> **Code**: TERRITORIALITY\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array. Atualmente so atendemos dentistas que atendem no Brasil\
> Pergunta usada para definir a territorialidade.\
>
>
> Os valores possíveis para esta pergunta são:\
>
>
> * **BR =** Brasil.

***

> **Code**: SCOPE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array. Atualmente só atender dentistas com trabalhos nacionais.\
> Pergunta usada para definir o Âmbito de trabalho do dentista.\
>
>
> Os possíveis valores para esta pergunta são:\
>
>
> * **NATIONAL =** Nacional.

***

> **Code**: LIMIT-DEDUCTIBLE\
> **Type**: `array<array<answer>>`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Campo para definir limite e franquia. Abordaremos mais detalhadamente a seguir.

***

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

> **Code**: VARIANT-IDENTIFIER\
> **Type**: `guid`\
> ❗ Obrigatório que esteja incluído no array de proposta.\
>
>
> Pergunta usada para definir o identificador da variante (variante retorna na cotação com nome de _variantIdentifier_).

***

> **Code**: LIMIT\
> **Type**: `decimal`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Os valores possíveis para esta pergunta são:\
>
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
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir o tipo da franquia.\
> \
> Os valores possíveis para esta pergunta são:\
>
>
> * **DEFAULT**\
>
> * **INCREASED**\
>
> * **REDUCED**\
>
> * **MINIMUM**\
>
>
> **Dependendo do tipo de categoria definido no campo CATEGORIES e o tipo de PESSOA (física ou jurídica), a resposta será diferente. Abaixo, você pode ver detalhadamente:**\
> \
>
>
> **Para pessoa física (PERSON-TYPE = NATURAL)**
>
> \
>
>
> Se for **GENERAL-PROCEDURES** (PERSON-TYPE NORMAL):\
>
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.\
>
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00.\
>
> * **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 500,00.\
>
> * **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 400,00.\
>   \
>
>
> Se for **IMPLANTS** (PERSON-TYPE NORMAL):\
>
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.\
>
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00.\
>
> * **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 500,00.\
>
> * **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 400,00.\
>   \
>
>
> Se for **FACIAL-FILLERS** (PERSON-TYPE NORMAL):\
>
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.\
>
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00.\
>
> * **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 500,00.\
>
> * **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 400,00.\
>   \
>
>
> Se for **ORALMAXILLOFACIAL-SURGERY** (PERSON-TYPE NORMAL):\
>
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00.\
>
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.500,00.\
>
> * **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.500,00.\
>
> * **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.\
>   \
>
>
> Se for **OROFACIAL-HARMONIZATION** (PERSON-TYPE NORMAL):\
>
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00.\
>
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,00.\
>
> * **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.\
>
> * **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.500,00.\
>   \
>
>
> **Para pessoa jurídica (PERSON-TYPE = LEGAL)**
>
> \
>
>
> Se for **GENERAL-PROCEDURES**(PERSON-TYPE LEGAL):\
>
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00.\
>
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$4.500,00.\
>
> * **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1,500,00.\
>
> * **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.\
>   \
>
>
> Se for **IMPLANTS** (PERSON-TYPE LEGAL):\
>
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00.\
>
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$4.500,00.\
>
> * **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1,500,00.\
>
> * **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.\
>   \
>
>
> Se for **FACIAL-FILLERS** (PERSON-TYPE LEGAL):\
>
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00.\
>
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$4.500,00.\
>
> * **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1,500,00.\
>
> * **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.\
>   \
>
>
> Se for **ORALMAXILLOFACIAL-SURGERY** (PERSON-TYPE LEGAL):\
>
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.500,00.\
>
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 4.500,00.\
>
> * **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.500,00.\
>
> * **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.000,00.\
>   \
>
>
> Se for **OROFACIAL-HARMONIZATION** (PERSON-TYPE LEGAL):\
>
>
> * **DEFAULT =** Padrão - 10% dos prejuízos indenizáveis com o mínimo de R$ 3.000,00.\
>
> * **INCREASED =** Majorada - 10% dos prejuízos indenizáveis com o mínimo de R$ 5.000,00.\
>
> * **REDUCED =** Reduzida - 10% dos prejuízos indenizáveis com o mínimo de R$ 2.000,00.\
>
> * **MINIMUM =** Mínima - 10% dos prejuízos indenizáveis com o mínimo de R$ 1.500,00.\
>   \
>
