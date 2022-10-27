> **Code**: PRODUCT </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para saber o produto. Os valores possíveis para esta pergunta são:<br><br>
> 
>  - **DAO-CIVIL-LIABILITY** </br>

------------------------------------------------------------------------

> **Code**: CURRENCY </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para saber a moeda do seguro. Os valores possíveis para esta pergunta são:<br><br>
> 
>  - **BRL** </br>


------------------------------------------------------------------------


> **Code**: PERSON-TYPE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para saber se a cotação está sendo preenchida por uma Pessoa Física ou Jurídica. Os valores possíveis para esta pergunta são:<br><br>
> 
>  - **LEGAL** = significa que a pessoa em questão é jurídica. </br>


------------------------------------------------------------------------


> **Code**: CONGENER </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array. </text> </br>
> 
> Pergunta usada para definir se a cotação em questão é um Seguro Novo ou uma Renovação. Os valores possíveis para esta pergunta são:<br><br>
> 
>  - **NEW** = indica que é um novo seguro. </br>
>  - **RENEW** = indica que é a renovação de um seguro.<br>
>  - **RENEWAL-INTERNAL** = indica que é a renovação de um seguro - Renovação Fairfax<br>

------------------------------------------------------------------------


>**Code**: PARTNER-TYPE<br>
>**Type**: ```text```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
> Pergunta usada para definir qual tipo de societário. Os valores possíveis para esta pergunta são:<br><br>
>
>   - **SOCIETY** = Sociedade LTDA<br>
>
>   - **CLOSED-CAPITAL** = S/A Capital Fechado<br>
>
>   - **OPEN-CAPITAL** = S/A Capital Aberto <br>
>
>   - **OPEN-CAPITAL-INTERNATIONAL** = S/A Capital Aberto (Internacional) - (Não Disponível)<br>
>
>   - **FINANCIAL-INSTITUTION-EXCEPT-CREDIT-UNION** = Instituição Financeira, exceto Cooperativa de Crédito  - (Não Disponível)<br>
>
>   - **CREDIT-COOPERATIVE** = Cooperativa de Crédito<br>
>
>   - **OTHER-COOPERATIVE** = Cooperativa (demais)<br>
>
>   - **PRIVATE-ASSOCIATION** = Associação Privada  - (Não Disponível)<br>
>
>   - **EIRELLI** = Eirelli<br>
>
>   - **FOUNDATION** = Fundação  - (Não Disponível)<br>
> 
>   - **LEGAL-PERSON** = MEI - Micro Empresário Individual<br>
> 
>   - **SYNDICATE** = Sindicato  - (Não Disponível)<br>


-----------------------------------------------------------------------------------------------


>**Code**: CORPORATE-COMPOSITION<br>
>**Type**: ```text```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
> Pergunta usada para definir qual a composição societária. Os valores possíveis para esta pergunta são:<br><br>
>
>   - **PRIVATE-CAPITAL** = Capital Privado<br>
>
>   - **MIXED-CAPITAL** = Capital Misto - (Não Disponível)<br>
>
>   - **PUBLIC** = Pública - (Não Disponível)<br>

---------------------------------------------------------------------------------------------


>**Code**: YEARS-COMPANY-STARTED<br>
>**Type**: ```text```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
> Pergunta usada para definir há quantos anos a empresa foi constituída e iniciou suas atividades. Os valores possíveis para esta pergunta são:<br><br>
>
>   - **0** = Pré-Operacional - (Não Disponível)<br>
>
>   - **3** = Até 3 anos<br>
>
>   - **3+** = Acima de 3 anos<br>

---------------------------------------------------------------------------------------------

> **Code**: COMPANY-SOLVENT </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído  no array.</text><br>
> 
> Pergunta usada para definir se a empresa contratante da apólice está solvente.
> 
> ❕ Obrigatório enviar ```true```

------------------------------------------------------------------------




>**Code**: CLAIM-EXPECTATION<br>
>**Type**: ```boolean```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
> Pergunta usada para definir se o proponente possui expectativa ou conhecimento de reclamações contra os administradores atuais e/ou anteriores



-----------------------------------------------------------------------------------------------




>**Code**: CLAIM-EXPECTATION-THIRD-PARTY<br>
>**Type**: ```text```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array  (se CLAIM-EXPECTATION for TRUE).</text><br>
> Pergunta usada para definir se o proponente possui expectativa ou conhecimento de reclamações contra os administradores atuais e/ou anteriores



-----------------------------------------------------------------------------------------------




>**Code**: CLAIM-EXPECTATION-AGREEMENT<br>
>**Type**: ```boolean ```<br>
> Pergunta usada para definir "**Entendimento e concordância**"
se definida  como true, indica que positivamente "**Entendimento e concordância do conhecimento de reclamações contra os administradores atuais e/ou anteriores.**"



-----------------------------------------------------------------------------------------------


> **Code**: INQUIRIES-ADMINISTRATIVE-CRIMINAL-PROCEDURES </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído  no array.</text><br>
> 
> Pergunta usada para definir se o proponente Possui Inquéritos, Procedimentos Administrativos E/ou Criminais Contra os Segurados.
> 
> ❕ Obrigatório enviar ```false```

------------------------------------------------------------------------


> **Code**: COVERAGE-PENALTIES </br>
> **Tipo**: ```boolean``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído  no array.</text><br>
> 
> Pergunta usada para definir se deseja Cobertura para Multas e Penalidades.

------------------------------------------------------------------------

> **Code**: NET-PATRIMONY </br>
> **Tipo**: ```currency``` </br>
> <text class="aviso">❗ Obrigatório que esteja incluído  no array.</text><br>
> 
> Pergunta usada para definir patrimônio líquido.
> 
> ❕ Exemplo: "R$ 1.000,00"

------------------------------------------------------------------------



>**Code**: TOTAL-ASSETS<br>
>**Type**: ```text```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
> Pergunta usada para definir total de ativos. Os valores possíveis para esta pergunta são:<br><br>
>
>   - **0.00-1000000.00** = Entre R$ 0,00 e R$ 1.000.000,00 <br>
>   - **1000000.01-3000000.00** = Entre R$ 1.000.000,01 e R$ 3.000.000,00 <br>
>   - **3000000.01-5000000.00** = Entre R$ 3.000.000,01 e R$ 5.000.000,00 <br>
>   - **5000000.01-10000000.00** = Entre R$ 5.000.000,01 e R$ 10.000.000,00 <br>
>   - **10000000.01-15000000.00** = Entre R$ 10.000.000,01 e R$ 15.000.000,00 <br>
>   - **15000000.01-20000000.00** = Entre R$ 15.000.000,01 e R$ 20.000.000,00 <br>
>   - **20000000.01-30000000.00** = Entre R$ 20.000.000,01 e R$ 30.000.000,00 <br>
>   - **30000000.01-40000000.00** = Entre R$ 30.000.000,01 e R$ 40.000.000,00 <br>
>   - **40000000.01-50000000.00** = Entre R$ 40.000.000,01 e R$ 50.000.000,00 <br>
>   - **50000000.01-60000000.00** = Entre R$ 50.000.000,01 e R$ 60.000.000,00 <br>
>   - **60000000.01-70000000.00** = Entre R$ 60.000.000,01 e R$ 70.000.000,00 <br>
>   - **70000000.01-80000000.00** = Entre R$ 70.000.000,01 e R$ 80.000.000,00 <br>
>   - **80000000.01-90000000.00** = Entre R$ 80.000.000,01 e R$ 90.000.000,00 <br>
>   - **90000000.01-100000000.00** = Entre R$ 90.000.000,01 e R$ 100.000.000,00 <br>
>   - **100000000.01-200000000.00** = Entre R$ 100.000.000,01 e R$ 200.000.000,00 <br>
>   - **200000000.01-300000000.00** = Entre R$ 200.000.000,01 e R$ 300.000.000,00 <br>
>   - **300000000.01-400000000.00** = Entre R$ 300.000.000,01 e R$ 400.000.000,00 <br>
>   - **400000000.01-500000000.00** = Entre R$ 400.000.000,01 e R$ 500.000.000,00 <br>
>   - **500000000.01-600000000.00** = Entre R$ 500.000.000,01 e R$ 600.000.000,00 <br>
>   - **600000000.01-700000000.00** = Entre R$ 600.000.000,01 e R$ 700.000.000,00 <br>
>   - **700000000.01-800000000.00** = Entre R$ 700.000.000,01 e R$ 800.000.000,00 <br>
>   - **800000000.01-900000000.00** = Entre R$ 800.000.000,01 e R$ 900.000.000,00 <br>
>   - **900000000.01-1000000000.00** = Entre R$ 900.000.000,01 e R$ 1.000.000.000,00 <br>
>   - **1000000000.00+** = Acima de R$ 1.000.000.000,00  - (Não Disponível)<br>

--------------------------------------------------------------------------------------



>**Code**: COMPANY-ACTIVITY<br>
>**Type**: ```text```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
> Pergunta usada para definir a atividade principal da empresa. Os valores possíveis para esta pergunta são:<br><br>
>
>   - **CONSORTIUM-ADMINISTRATOR** = Administrador de Consórcio e Empréstimos - (Não Disponível). <br>
>   - **TRAVEL-AGENCIES-OPERATORS-RESERVATION-SERVICES** = Agências de Viagens, Operadores Turísticos e Serviços de Reservas- (Não Disponível). <br>
>   - **AGRICULTURE-RELATED-SERVICES** = Agricultura, Pecuária, Floresta, Aquicultura e Serviços Relacionados. <br>
>   - **ARTS-CULTURE-RECREATION** = Artes, Cultura e Recreação (exceto Esportes). <br>
>   - **ADMINISTRATIVE-ACTIVITIES-COMPLEMENTARY** = Atividades Administrativas e Serviços Complementares - Locação, Mão de Obra, Segurança, Administração Imobiliária. <br>
>   - **HEALTH-CARE** = Atividades de Atenção a Saúde. <br>
>   - **LEGAL-ACCOUNTING-AUDITING** = Atividades Jurídicas, de Contabilidade e de Auditoria. <br>
>   - **RETAIL-TRADE** = Comércio Atacadista E/ou Varejista. <br>
>   - **TRADE-REPAIR-MAINTENANCE** = Comércio, Reparação e Manutenção de Veículos Automotores e Motocicletas. <br>
>   - **CREDIT-UNIONS** = Cooperativas de Crédito. <br>
>   - **INSURANCE-BROKERS** = Corretores de Seguros- (Não Disponível). <br>
>   - **EDUCATION** = Educação- (Não Disponível). <br>
>   - **ELECTRICITY-OTHER-UTILITIES** = Eletricidade, Gás e Outras Utilidades, Exceto Concessões. <br>
>   - **MANUFACTURE-COMPUTER-EQUIPMENT** = Fabricação de Equipamentos de Informática, Produtos Eletrônicos e Ópticos. <br>
>   - **MANUFACTURE-MACHINERY-EQUIPMENT** = Fabricação de Máquinas e Equipamentos. <br>
>   - **MANUFACTURE-ELECTRICAL-MACHINES** = Fabricação de Máquinas, Aparelhos e Materiais Elétricos. <br>
>   - **MANUFACTURE-FURNITURE-WOOD** = Fabricação de Móveis e Produtos de Madeira. <br>
>   - **MANUFACTURE-FOOD-PRODUCTS** = Fabricação de Produtos Alimentício e Bebidas. <br>
>   - **MANUFACTURE-PLASTIC-MATERIAL** = Fabricação de Produtos de Borracha e de Material Plástico. <br>
>   - **MANUFACTURE-METAL-PRODUCTS-EXCEPT-MACHINES** = Fabricação de Produtos de Metal, Exceto Máquinas e Equipamentos. <br>
>   - **MANUFACTURE-NON-METALLIC-MINERAL** = Fabricação de Produtos de Minerais Não-metálicos. <br>
>   - **MANUFACTURE-VARIED-PRODUCTS** = Fabricação de Produtos Diversos. <br>
>   - **MANUFACTURE-PHARMACEUTICAL-CHEMICAL** = Fabricação de Produtos Farmacêuticos e/ou Químicos. <br>
>   - **MANUFACTURE-TEXTILE-PRODUCTS** = Fabricação de Produtos Têxteis e Confecção, Incluindo Artigos de Couro. <br>
>   - **MANUFACTURE-MOTOR-VEHICLES** = Fabricação de Veículos Automotores, Reboques e Carrocerias. <br>
>   - **FINTECH-INSURTECH** = Fintech E/ou Insurtech- (Não Disponível). <br>
>   - **HOTELS-RESTAURANTS** = Hotéis, restaurantes e Similares- (Não Disponível). <br>
>   - **REAL-ESTATE** = Imobiliárias. <br>
>   - **EXTRACTIVE-INDUSTRIES** = Indústrias Extrativas - Mineração (minerais Metálicos e Não-metálicos), Óleo e Gás e Atividade de Apoio- (Não Disponível). <br>
>   - **INFORMATION-COMMUNICATION** = Informação e Comunicação - Cinema, Radio, Televisão e Atividades Relacionadas - (Não Disponível).<br>
>   - **MAINTENANCE-REPAIR-INSTALLATION** = Manutenção, Reparação e Instalação de Máquinas e Equipamentos. <br>
>   - **METALLURGY** = Metalurgia. <br>
>   - **ASSOCIATIVE-ORGANIZATIONS** = Organizações Associativas - (Não Disponível). <br>
>   - **PAPER-PULP** = Papel e Celulose. <br>
>   - **IT-SERVICES** = Serviços de Tecnologia da Informação. <br>
>   - **GRAPHIC-SERVICES** = Serviços Gráficos - Impressão e Gravações. <br>
>   - **WATER-TRANSPORT** = Transporte Terrestre, Aquaviário e Aéreo - (Não Disponível). <br>
>   - **NOT-LISTED** = Demais Atividades Não Listadas - (Não Disponível). <br>


-----------------------------------------------------------------------------------------------


>**Code**: REVENUES<br>
>**Type**: ```text```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
> Pergunta usada para definir o faturamento anual. Os valores possíveis para esta pergunta são:<br><br>
>
>   - **0.00-50000.00** = Entre R$ 0 e R$ 50.000,00 <br>
>   - **50000.01-100000.00** = Entre R$ 50.000,01 e R$ 100.000,00 <br>
>   - **100000.01-150000.00** = Entre R$ 100.000,01 e R$ 150.000,00 <br>
>   - **150000.01-200000.00** = Entre R$ 150.000,01 e R$ 200.000,00 <br>
>   - **200000.01-250000.00** = Entre R$ 200.000,01 e R$ 250.000,00 <br>
>   - **250000.01-350000.00** = Entre R$ 250.000,01 e R$ 350.000,00 <br>
>   - **350000.01-500000.00** = Entre R$ 350.000,01 e R$ 500.000,00 <br>
>   - **500000.01-800000.00** = Entre R$ 500.000,01 e R$ 800.000,00 <br>
>   - **800000.01-1000000.00** = Entre R$ 800.000,01 e R$ 1.000.000,00 <br>
>   - **1000000.01-1500000.00** = Entre R$ 1.000.000,01 e R$ 1.500.000,00 <br>
>   - **1500000.01-2500000.00** = Entre R$ 1.500.000,01 e R$ 2.500.000,00 <br>
>   - **2500000.01-5000000.00** = Entre R$ 2.500.000,01 e R$ 5.000.000,00 <br>
>   - **5000000.01-7500000.00** = Entre R$ 5.000.000,01 e R$ 7.500.000,00 <br>
>   - **7500000.01-10000000.00** = Entre R$ 7.500.000,01 e R$ 10.000.000,00 <br>
>   - **10000000.01-15000000.00** = Entre R$ 10.000.000,01 e R$ 15.000.000,00 <br>
>   - **15000000.01-20000000.00** = Entre R$ 15.000.000,01 e R$ 20.000.000,00 <br>
>   - **20000000.01-25000000.00** = Entre R$ 20.000.000,01 e R$ 25.000.000,00 <br>
>   - **25000000.01-30000000.00** = Entre R$ 25.000.000,01 e R$ 30.000.000,00 <br>
>   - **30000000.01-34000000.00** = Entre R$ 30.000.000,01 e R$ 34.000.000,00 <br>
>   - **34000000.01-40000000.00** = Entre R$ 34.000.000,01 e R$ 40.000.000,00 <br>
>   - **40000000.01-45000000.00** = Entre R$ 40.000.000,01 e R$ 45.000.000,00 <br>
>   - **45000000.01-50000000.00** = Entre R$ 45.000.000,01 e R$ 50.000.000,00 <br>
>   - **50000000.01-60000000.00** = Entre R$ 50.000.000,01 e R$ 60.000.000,00 <br>
>   - **60000000.01-72000000.00** = Entre R$ 60.000.000,01 e R$ 72.000.000,00 <br>
>   - **72000000.01-82000000.00** = Entre R$ 72.000.000,01 e R$ 82.000.000,00 <br>
>   - **82000000.01-100000000.00** = Entre R$ 82.000.000,01 e R$ 100.000.000,00 <br>
>   - **100000000.01-200000000.00** = Entre R$ 100.000.000,01 e R$ 200.000.000,00 <br>
>   - **200000000.01-300000000.00** = Entre R$ 200.000.000,01 e R$ 300.000.000,00 <br>
>   - **300000000.01-500000000.00** = Entre R$ 300.000.000,01 e R$ 500.000.000,00 <br>
>   - **500000000.01-700000000.00** = Entre R$ 500.000.000,01 e R$ 700.000.000,00 <br>
>   - **700000000.01-1000000000.00** = Entre R$ 700.000.000,01 e R$ 1.000.000.000,00 <br>
>   - **1000000000.00+** = Acima de R$ 1.000.000.000,00 - (Não Disponível).<br>


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



>**Code**: PROFESSION<br>
>**Type**: ```text```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
> Pergunta usada para definir profissão. Os possíveis valores para esta pergunta são: <br><br>
>
>   - **DAO**



-----------------------------------------------------------------------------------------------


>**Code**: PAYMENT-METHOD <br>
>**Type**: ```text``` <br>
><text class="aviso">❗ Obrigatório que esteja incluído no array. (quando for para o endpoint de PROPOSAL).</text> <br>
>
>Pergunta usada para definir o método de pagamento.
Os possíveis valores para esta pergunta são:
>
>  - **TICKET**

----------------------------------------------------------------------------------------------------


>**Code**: LIMITS<br>
>**Type**: ```array<array<answer>>```<br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
> Campo para definir Limite e Franquia, veremos mais detalhadamente nas proximas partes.


-----------------------------------------------------------------------------------------------


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

> **Code**: VARIANT-IDENTIFIER <br> **Type**: ```guid``` <br> <text class="aviso">❗ Obrigatório que esteja incluído no array de proposta.</text><br>
>
> Pergunta usada para definir o identificador da variante.


-------------------------------------------------------------------------


> **Code**: LIMIT <br> **Type**: `decimal` <br> <text class="aviso">❗ Obrigatório que esteja incluído no array.</text><br>
>
> Os valores possíveis para esta pergunta são:<br><br>
>
> - **500000.00m**   = R$ 500.000,00
> - **1000000.00m**  = R$ 1.000.000,00
> - **1500000.00m**  = R$ 1.500.000,00
> - **2000000.00m**  = R$ 2.000.000,00
> - **2500000.00m**  = R$ 2.500.000,00
> - **3000000.00m**  = R$ 3.000.000,00
> - **3500000.00m**  = R$ 3.500.000,00
> - **4000000.00m**  = R$ 4.000.000,00
> - **4500000.00m**  = R$ 4.500.000,00
> - **5000000.00m**  = R$ 5.000.000,00
> - **5500000.00m**  = R$ 5.500.000,00
> - **6000000.00m**  = R$ 6.000.000,00
> - **6500000.00m**  = R$ 6.500.000,00
> - **7000000.00m**  = R$ 7.000.000,00
> - **7500000.00m**  = R$ 7.500.000,00
> - **8000000.00m**  = R$ 8.000.000,00
> - **8500000.00m**  = R$ 8.500.000,00
> - **9000000.00m**  = R$ 9.000.000,00
> - **9500000.00m**  = R$ 9.500.000,00
> - **10000000.00m** = R$ 10.000.000,00
