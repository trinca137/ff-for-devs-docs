# Informações e explicações a mais para o produto de D\&O.

> **Code**: PERSON-TYPE\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Para D\&O so é possivel pessoa jurídica. A única resposta permitida até o momento é:\
>
>
> * **LEGAL** = significa que a pessoa em questão é jurídica.

***

> **Code**: CONGENER\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir se a cotação em questão é um Seguro Novo ou uma Renovação.\
> \
>
>
> Os valores possíveis para esta pergunta são:\
>
>
> * **NEW** = indica que é um novo seguro.\
>
> * **RENEW** = indica que é a renovação de um seguro.\
>
> * **RENEWAL-INTERNAL** = indica que é a renovação de um seguro - Renovação Fairfax

***

> **Code**: PARTNER-TYPE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir qual tipo societário da empresa.\
> \
>
>
> Os valores possíveis para esta pergunta são:\
>
>
> * **SOCIETY** = Sociedade LTDA\
>
> * **CLOSED-CAPITAL** = S/A Capital Fechado\
>
> * **OPEN-CAPITAL** = S/A Capital Aberto\
>
> * **CREDIT-COOPERATIVE** = Cooperativa de Crédito\
>
> * **OTHER-COOPERATIVE** = Cooperativa (demais)\
>
> * **EIRELLI** = Eirelli\
>
> * **LEGAL-PERSON** = MEI - Micro Empresário Individual

***

> **Code**: CORPORATE-COMPOSITION\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir qual a composição societária.\
> \
>
>
> Os valores possíveis para esta pergunta são:\
>
>
> * **PRIVATE-CAPITAL** = Capital Privado

***

> **Code**: YEARS-COMPANY-STARTED\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir há quantos anos a empresa foi constituída e iniciou suas atividades.\
> \
>
>
> Os valores possíveis para esta pergunta são:\
>
>
> * **3** = Até 3 anos\
>
> * **3+** = Acima de 3 anos

***

> **Code**: COMPANY-ACTIVITY\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir a atividade principal da empresa.\
> \
>
>
> Os valores possíveis para esta pergunta são:\
>
>
> * **AGRICULTURE-RELATED-SERVICES** = Agricultura, Pecuária, Floresta, Aquicultura e Serviços Relacionados.\
>
> * **ARTS-CULTURE-RECREATION** = Artes, Cultura e Recreação (exceto Esportes).\
>
> * **ADMINISTRATIVE-ACTIVITIES-COMPLEMENTARY** = Atividades Administrativas e Serviços Complementares - Locação, Mão de Obra, Segurança, Administração Imobiliária.\
>
> * **HEALTH-CARE** = Atividades de Atenção a Saúde.\
>
> * **LEGAL-ACCOUNTING-AUDITING** = Atividades Jurídicas, de Contabilidade e de Auditoria.\
>
> * **RETAIL-TRADE** = Comércio Atacadista E/ou Varejista.\
>
> * **TRADE-REPAIR-MAINTENANCE** = Comércio, Reparação e Manutenção de Veículos Automotores e Motocicletas.\
>
> * **CREDIT-UNIONS** = Cooperativas de Crédito.\
>
> * **ELECTRICITY-OTHER-UTILITIES** = Eletricidade, Gás e Outras Utilidades, Exceto Concessões.\
>
> * **MANUFACTURE-COMPUTER-EQUIPMENT** = Fabricação de Equipamentos de Informática, Produtos Eletrônicos e Ópticos.\
>
> * **MANUFACTURE-MACHINERY-EQUIPMENT** = Fabricação de Máquinas e Equipamentos.\
>
> * **MANUFACTURE-ELECTRICAL-MACHINES** = Fabricação de Máquinas, Aparelhos e Materiais Elétricos.\
>
> * **MANUFACTURE-FURNITURE-WOOD** = Fabricação de Móveis e Produtos de Madeira.\
>
> * **MANUFACTURE-FOOD-PRODUCTS** = Fabricação de Produtos Alimentício e Bebidas.\
>
> * **MANUFACTURE-PLASTIC-MATERIAL** = Fabricação de Produtos de Borracha e de Material Plástico.\
>
> * **MANUFACTURE-METAL-PRODUCTS-EXCEPT-MACHINES** = Fabricação de Produtos de Metal, Exceto Máquinas e Equipamentos.\
>
> * **MANUFACTURE-NON-METALLIC-MINERAL** = Fabricação de Produtos de Minerais Não-metálicos.\
>
> * **MANUFACTURE-VARIED-PRODUCTS** = Fabricação de Produtos Diversos.\
>
> * **MANUFACTURE-PHARMACEUTICAL-CHEMICAL** = Fabricação de Produtos Farmacêuticos e/ou Químicos.\
>
> * **MANUFACTURE-TEXTILE-PRODUCTS** = Fabricação de Produtos Têxteis e Confecção, Incluindo Artigos de Couro.\
>
> * **MANUFACTURE-MOTOR-VEHICLES** = Fabricação de Veículos Automotores, Reboques e Carrocerias.\
>
> * **REAL-ESTATE** = Imobiliárias.\
>
> * **MAINTENANCE-REPAIR-INSTALLATION** = Manutenção, Reparação e Instalação de Máquinas e Equipamentos.\
>
> * **METALLURGY** = Metalurgia.\
>
> * **PAPER-PULP** = Papel e Celulose.\
>
> * **IT-SERVICES** = Serviços de Tecnologia da Informação.\
>
> * **GRAPHIC-SERVICES** = Serviços Gráficos - Impressão e Gravações.

***

> **Code**: NET-PATRIMONY\
> **Tipo**: `currency`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir patrimônio líquido.
>
> ❕ Exemplo: "R$ 1.000,00"

***

> **Code**: TOTAL-ASSETS\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir total de ativos.\
> \
>
>
> Os valores possíveis para esta pergunta são:\
>
>
> * **0.00-1000000.00** = Entre R$ 0,00 e R$ 1.000.000,00\
>
> * **1000000.01-3000000.00** = Entre R$ 1.000.000,01 e R$ 3.000.000,00\
>
> * **3000000.01-5000000.00** = Entre R$ 3.000.000,01 e R$ 5.000.000,00\
>
> * **5000000.01-10000000.00** = Entre R$ 5.000.000,01 e R$ 10.000.000,00\
>
> * **10000000.01-15000000.00** = Entre R$ 10.000.000,01 e R$ 15.000.000,00\
>
> * **15000000.01-20000000.00** = Entre R$ 15.000.000,01 e R$ 20.000.000,00\
>
> * **20000000.01-30000000.00** = Entre R$ 20.000.000,01 e R$ 30.000.000,00\
>
> * **30000000.01-40000000.00** = Entre R$ 30.000.000,01 e R$ 40.000.000,00\
>
> * **40000000.01-50000000.00** = Entre R$ 40.000.000,01 e R$ 50.000.000,00\
>
> * **50000000.01-60000000.00** = Entre R$ 50.000.000,01 e R$ 60.000.000,00\
>
> * **60000000.01-70000000.00** = Entre R$ 60.000.000,01 e R$ 70.000.000,00\
>
> * **70000000.01-80000000.00** = Entre R$ 70.000.000,01 e R$ 80.000.000,00\
>
> * **80000000.01-90000000.00** = Entre R$ 80.000.000,01 e R$ 90.000.000,00\
>
> * **90000000.01-100000000.00** = Entre R$ 90.000.000,01 e R$ 100.000.000,00\
>
> * **100000000.01-200000000.00** = Entre R$ 100.000.000,01 e R$ 200.000.000,00\
>
> * **200000000.01-300000000.00** = Entre R$ 200.000.000,01 e R$ 300.000.000,00\
>
> * **300000000.01-400000000.00** = Entre R$ 300.000.000,01 e R$ 400.000.000,00\
>
> * **400000000.01-500000000.00** = Entre R$ 400.000.000,01 e R$ 500.000.000,00\
>
> * **500000000.01-600000000.00** = Entre R$ 500.000.000,01 e R$ 600.000.000,00\
>
> * **600000000.01-700000000.00** = Entre R$ 600.000.000,01 e R$ 700.000.000,00\
>
> * **700000000.01-800000000.00** = Entre R$ 700.000.000,01 e R$ 800.000.000,00\
>
> * **800000000.01-900000000.00** = Entre R$ 800.000.000,01 e R$ 900.000.000,00\
>
> * **900000000.01-1000000000.00** = Entre R$ 900.000.000,01 e R$ 1.000.000.000,00

***

> **Code**: REVENUES\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir o faturamento anual.\
> \
>
>
> Os valores possíveis para esta pergunta são:\
>
>
> * **0.00-50000.00** = Entre R$ 0 e R$ 50.000,00\
>
> * **50000.01-100000.00** = Entre R$ 50.000,01 e R$ 100.000,00\
>
> * **100000.01-150000.00** = Entre R$ 100.000,01 e R$ 150.000,00\
>
> * **150000.01-200000.00** = Entre R$ 150.000,01 e R$ 200.000,00\
>
> * **200000.01-250000.00** = Entre R$ 200.000,01 e R$ 250.000,00\
>
> * **250000.01-350000.00** = Entre R$ 250.000,01 e R$ 350.000,00\
>
> * **350000.01-500000.00** = Entre R$ 350.000,01 e R$ 500.000,00\
>
> * **500000.01-800000.00** = Entre R$ 500.000,01 e R$ 800.000,00\
>
> * **800000.01-1000000.00** = Entre R$ 800.000,01 e R$ 1.000.000,00\
>
> * **1000000.01-1500000.00** = Entre R$ 1.000.000,01 e R$ 1.500.000,00\
>
> * **1500000.01-2500000.00** = Entre R$ 1.500.000,01 e R$ 2.500.000,00\
>
> * **2500000.01-5000000.00** = Entre R$ 2.500.000,01 e R$ 5.000.000,00\
>
> * **5000000.01-7500000.00** = Entre R$ 5.000.000,01 e R$ 7.500.000,00\
>
> * **7500000.01-10000000.00** = Entre R$ 7.500.000,01 e R$ 10.000.000,00\
>
> * **10000000.01-15000000.00** = Entre R$ 10.000.000,01 e R$ 15.000.000,00\
>
> * **15000000.01-20000000.00** = Entre R$ 15.000.000,01 e R$ 20.000.000,00\
>
> * **20000000.01-25000000.00** = Entre R$ 20.000.000,01 e R$ 25.000.000,00\
>
> * **25000000.01-30000000.00** = Entre R$ 25.000.000,01 e R$ 30.000.000,00\
>
> * **30000000.01-34000000.00** = Entre R$ 30.000.000,01 e R$ 34.000.000,00\
>
> * **34000000.01-40000000.00** = Entre R$ 34.000.000,01 e R$ 40.000.000,00\
>
> * **40000000.01-45000000.00** = Entre R$ 40.000.000,01 e R$ 45.000.000,00\
>
> * **45000000.01-50000000.00** = Entre R$ 45.000.000,01 e R$ 50.000.000,00\
>
> * **50000000.01-60000000.00** = Entre R$ 50.000.000,01 e R$ 60.000.000,00\
>
> * **60000000.01-72000000.00** = Entre R$ 60.000.000,01 e R$ 72.000.000,00\
>
> * **72000000.01-82000000.00** = Entre R$ 72.000.000,01 e R$ 82.000.000,00\
>
> * **82000000.01-100000000.00** = Entre R$ 82.000.000,01 e R$ 100.000.000,00\
>
> * **100000000.01-200000000.00** = Entre R$ 100.000.000,01 e R$ 200.000.000,00\
>
> * **200000000.01-300000000.00** = Entre R$ 200.000.000,01 e R$ 300.000.000,00\
>
> * **300000000.01-500000000.00** = Entre R$ 300.000.000,01 e R$ 500.000.000,00\
>
> * **500000000.01-700000000.00** = Entre R$ 500.000.000,01 e R$ 700.000.000,00\
>
> * **700000000.01-1000000000.00** = Entre R$ 700.000.000,01 e R$ 1.000.000.000,00

***

> **Code**: COMPANY-SOLVENT\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir se a empresa contratante da apólice está solvente.\
>
>
> ❕ So é aceito como `true`

***

> **Code**: INQUIRIES-ADMINISTRATIVE-CRIMINAL-PROCEDURES\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir se o proponente Possui Inquéritos, Procedimentos Administrativos E/ou Criminais Contra os Segurados.\
>
>
> ❕ So é aceito como `false`

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
> Pergunta usada para o proponente descrever as reclamações.

***

> **Code**: CLAIM-EXPECTATION-AGREEMENT\
> **Type**: `boolean`\
> ❗ Obrigatório que esteja incluído no array (se CLAIM-EXPECTATION for TRUE).\
>
>
> Pergunta usada para definir "**Entendimento e concordância**" se definida como true, indica que positivamente "**Entendimento e concordância do conhecimento de reclamações contra os administradores atuais e/ou anteriores.**"

***

> **Code**: COVERAGE-PENALTIES\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Pergunta usada para definir se deseja Cobertura para Multas e Penalidades.

***

> **Code**: TERRITORIALITY\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array. Atualmente so atendemos seguros de D\&O no Brasil\
> Pergunta usada para definir a Territorialidade.\
> \
>
>
> Os possíveis valores para esta pergunta são:\
>
>
> * **BR =** Brasil

***

> **Code**: SCOPE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array. Atualmente so atendemos seguros de D\&O nacionais.\
> Pergunta usada para definir o Âmbito de trabalho da empresa\
> \
>
>
> Os possíveis valores para esta pergunta são:\
>
>
> * **NATIONAL =** nacional

***

> **Code**: PAYMENT-METHOD\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array. (quando for para o endpoint de PROPOSAL).\
> Pergunta usada para definir o método de pagamento.\
> \
>
>
> Os possíveis valores para esta pergunta são:\
>
>
> * **TICKET**

***

> **Code**: LIMITS\
> **Type**: `array<array<answer>>`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Campo para definir Limite e Franquia, veremos mais detalhadamente a seguir.

***

> ❕ Como explicado anteriormente, o campo **LIMITS** dentro do array de answer tem como finalidade enviar perguntas referentes aos limites e franquias. A seguir, você verá os valores que poderão/deverão estar inclusos nesse array.

```json
{
   "identifier":"2942faa1-09b8-4345-9bdd-6764c4f1ad35",
   "operationCode":"DIRECTORS-OFFICERS-CIVIL-LIABILITY-PARTNER",
   "answers":[
      {
         "code":"MODALITY",
         "answer":"DIRECTORS-OFFICERS-CIVIL-LIABILITY"
      },
      {
         "code":"LIMITS",
         "answer":[
            [
               {
                  "code":"LIMIT",
                  "answer":100000
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
> ❗ Obrigatório que esteja incluído no array de **proposta**.\
>
>
> Pergunta usada para definir o identificador da variante.

***

> **Code**: LIMIT\
> **Type**: `decimal`\
> ❗ Obrigatório que esteja incluído no array.\
> \
>
>
> Os valores possíveis para esta pergunta são:\
>
>
> * **500000.00m** = R$ 500.000,00
> * **1000000.00m** = R$ 1.000.000,00
> * **1500000.00m** = R$ 1.500.000,00
> * **2000000.00m** = R$ 2.000.000,00
> * **2500000.00m** = R$ 2.500.000,00
> * **3000000.00m** = R$ 3.000.000,00
> * **3500000.00m** = R$ 3.500.000,00
> * **4000000.00m** = R$ 4.000.000,00
> * **4500000.00m** = R$ 4.500.000,00
> * **5000000.00m** = R$ 5.000.000,00
> * **5500000.00m** = R$ 5.500.000,00
> * **6000000.00m** = R$ 6.000.000,00
> * **6500000.00m** = R$ 6.500.000,00
> * **7000000.00m** = R$ 7.000.000,00
> * **7500000.00m** = R$ 7.500.000,00
> * **8000000.00m** = R$ 8.000.000,00
> * **8500000.00m** = R$ 8.500.000,00
> * **9000000.00m** = R$ 9.000.000,00
> * **9500000.00m** = R$ 9.500.000,00
> * **10000000.00m** = R$ 10.000.000,00
