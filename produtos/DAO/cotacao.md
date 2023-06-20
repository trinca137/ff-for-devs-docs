# Criar cotação

{% swagger method="post" path="{{version}}/quotation/contracting" baseUrl="{{url_ambiente}}/" summary="Criar Cotação" fullWidth="true" expanded="true" %}
{% swagger-description %}
Cria ou edita uma cotação.
{% endswagger-description %}

{% swagger-parameter in="header" name="Ocp-Apim-Subscription-Key" required="true" type="key" %}
chave de acesso da api.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Retorno sucesso." %}


[#response](cotacao.md#response "mention")


{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Retorno com mensagem do local do erro" %}
```json
{
    "success": false,
    "executed": "2023-05-22T20:10:41.1631988Z",
    "errors": [
        {
            "code": "ANSWERS-NOT-EVALUATED",
            "message": "One or more answers could not be evaluated.",
            "properties": [
                "INSURED-NAME"
            ]
        }
    ]
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Erro de "register number"" %}
```json
{
    "success": false,
    "executed": "2023-05-22T20:11:50.6875419Z",
    "errors": [
        {
            "code": "INCORRECT-OR-NONEXISTENT"
        },
        {
            "code": "TOKEN-ERROR"
        }
    ]
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="Caso não envie uma "chave" ou envie uma inválida" %}
{% code overflow="wrap" %}
```json
{
    "statusCode": 401,
    "message": "Access denied due to invalid subscription key. Make sure to provide a valid key for an active subscription."
}
```
{% endcode %}
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Erro de aplicação/servidor" %}

{% endswagger-response %}
{% endswagger %}

{% hint style="info" %}
Para editar uma cotação, basta enviar o identifier antes de answers, exemplo:

```json
{
    "operationCode": "DIRECTORS-OFFICERS-CIVIL-LIABILITY-PARTNER",
    "quotationIdentifier": "ea0da0ea-1623-47b7-bbbe-75e8eee15ee0", 
    "registerNumber": "100000",
    "answers": [
    ...
    ...
    ]
}
```
{% endhint %}

## Request

```json
{
    "operationCode": "DIRECTORS-OFFICERS-CIVIL-LIABILITY-PARTNER",
    "registerNumber": "100000",
    "answers": [
        {
            "code": "MODALITY",
            "answer": "DIRECTORS-OFFICERS-CIVIL-LIABILITY"
        },
        {
            "code": "PERSON-TYPE",
            "answer": "LEGAL"
        },
        {
            "code": "CONGENER",
            "answer": "RENEWAL"
        },
        {
            "code": "PREVIOUS-INSURER",
            "answer": "0"
        },
        {
            "code": "PREVIOUS-INSURER-NAME",
            "answer": "Seguradora anterior"
        },
        {
            "code": "START-VIGENCY-DATE",
            "answer": "2022-11-23T03:00:00.000Z"
        },
        {
            "code": "IDENTITY",
            "answer": "65.854.012/0001-29"
        },
        {
            "code": "INSURED-NAME",
            "answer": "Nome segurado"
        },
        {
            "code": "INSURED-EMAIL",
            "answer": "email@segurado.com"
        },
        {
            "code": "INSURED-CELLPHONE",
            "answer": "(11) 91111-2222"
        },
        {
            "code": "INSURED-ADDRESS-ZIPCODE",
            "answer": "12345-123"
        },
        {
            "code": "INSURED-ADDRESS-STREET",
            "answer": "Nome da rua"
        },
        {
            "code": "INSURED-ADDRESS-NUMBER",
            "answer": "Número"
        },
        {
            "code": "INSURED-ADDRESS-COMPLEMENT",
            "answer": ""
        },
        {
            "code": "INSURED-ADDRESS-NEIGHBORHOOD",
            "answer": "Bairro"
        },
        {
            "code": "INSURED-ADDRESS-CITY",
            "answer": "São Paulo"
        },
        {
            "code": "INSURED-ADDRESS-STATE",
            "answer": "SP"
        },
        {
            "code": "COMMISSION",
            "answer": 20
        },
        {
            "code": "GRIEVANCE-DISCOUNT",
            "answer": 0
        },
        {
            "code": "PARTNER-TYPE",
            "answer": "SOCIETY"
        },
        {
            "code": "CORPORATE-COMPOSITION",
            "answer": "PRIVATE-CAPITAL"
        },
        {
            "code": "YEARS-COMPANY-STARTED",
            "answer": "3"
        },
        {
            "code": "COMPANY-ACTIVITY",
            "answer": "AGRICULTURE-RELATED-SERVICES"
        },
        {
            "code": "NET-PATRIMONY",
            "answer": "R$ 1.000,00"
        },
        {
            "code": "TOTAL-ASSETS",
            "answer": "3000000.01-5000000.00"
        },
        {
            "code": "REVENUES",
            "answer": "0.00-50000.00"
        },
        {
            "code": "COMPANY-SOLVENT",
            "answer": true
        },
        {
            "code": "INQUIRIES-ADMINISTRATIVE-CRIMINAL-PROCEDURES",
            "answer": false
        },
        {
            "code": "CLAIM-EXPECTATION",
            "answer": false
        },
        {
            "code": "CLAIM-EXPECTATION-THIRD-PARTY"
        },
        {
            "code": "CLAIM-EXPECTATION-AGREEMENT"
        },
        {
            "code": "COVERAGE-PENALTIES",
            "answer": false
        },
        {
            "code": "TERRITORIALITY",
            "answer": "BR"
        },
        {
            "code": "SCOPE",
            "answer": "NATIONAL"
        },
        {
            "code": "LIMITS",
            "answer": [
                [
                    {
                        "code": "LIMIT",
                        "answer": 1000000
                    }
                ]
            ]
        }
    ]
}
```

### Explicando campos de envio.

```json
{
	"operationCode": "DIRECTOR-OFFICERS-CIVIL-LIABILITY-PARTNER",
	"registerNumber": "100000",
	"answers":[],
}
```

> **Field**: OperationCode\
> **Tipo**: `text`\
> ❗ Campo Obrigatório.
>
> Campo usado para definir qual produto está sendo cotado. Neste caso, o produto é "Médicos", representado pelo operation code "MEDICAL-CIVIL-LIABILITY-PARTNER".



> **Field:** RegisterNumber
>
> **Tipo:** `text`&#x20;
>
> ❗ Campo Obrigatório.
>
> Campo usado para definir qual o SusepNumber da corretora está sendo cotada. Neste caso, o susep da corretora é "100000".



> **Field**: Answers\
> **Tipo**: `array<answer>`\
> ❗ Campo Obrigatório.
>
> Campo usado para enviar perguntas gerais de uma cotação.



> **Code**: INSURED-ADDRESS-COMPLEMENT\
> **Tipo**: `text`\
>
>
> Pergunta usada para definir o número da moradia do segurado.



> **Code**: INSURED-ADDRESS-NEIGHBORHOOD\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o bairro do segurado.



> **Code**: INSURED-ADDRESS-CITY\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir a cidade do segurado.



> **Code**: INSURED-ADDRESS-STATE\
> **Tipo**: `text`\
> ❗Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o estado do segurado.



> **Code**: COMMISSION\
> **Tipo**: `decimal`\
> ❗Obrigatório que esteja incluído\
> Pergunta usada para definir a comissão.
>
> Pode ser enviado valores entre 1 e 30.\
> Valor padrão é 20.00.



> **Code**: GRIEVANCE-DISCOUNT\
> **Tipo**: `decimal`
>
> Pergunta usada para definir Agravo (aumento de preço sobre o netValue\* da cotação).\
> O Padrão é 0.\
> \* Preço líquido do produto sem IOF.



> **Code**: PERSON-TYPE\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Para D\&O so é possivel pessoa jurídica. A única resposta permitida até o momento é:
>
> * **LEGAL** = significa que a pessoa em questão é jurídica.

***

> **Code**: CONGENER\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir se a cotação em questão é um Seguro Novo ou uma Renovação.\
>
>
> Os valores possíveis para esta pergunta são:
>
> * **NEW** = indica que é um novo seguro.
> * **RENEW** = indica que é a renovação de um seguro.
> * **RENEWAL-INTERNAL** = indica que é a renovação de um seguro - Renovação Fairfax

***

> **Code**: PARTNER-TYPE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir qual tipo societário da empresa.\
>
>
> Os valores possíveis para esta pergunta são:

<details>

<summary>Tipo societário</summary>

* **SOCIETY** = Sociedade LTDA

<!---->

* **CLOSED-CAPITAL** = S/A Capital Fechado

<!---->

* **OPEN-CAPITAL** = S/A Capital Aberto

<!---->

* **CREDIT-COOPERATIVE** = Cooperativa de Crédito

<!---->

* **OTHER-COOPERATIVE** = Cooperativa (demais)

<!---->

* **EIRELLI** = Eirelli

<!---->

* **LEGAL-PERSON** = MEI - Micro Empresário Individual

</details>

> **Code**: CORPORATE-COMPOSITION\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir qual a composição societária.\
>
>
> Os valores possíveis para esta pergunta são:
>
> * **PRIVATE-CAPITAL** = Capital Privado

***

> **Code**: YEARS-COMPANY-STARTED\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir há quantos anos a empresa foi constituída e iniciou suas atividades.\
>
>
> Os valores possíveis para esta pergunta são:
>
> * **3** = Até 3 anos
> * **3+** = Acima de 3 anos

***

> **Code**: COMPANY-ACTIVITY\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir a atividade principal da empresa.\
>
>
> Os valores possíveis para esta pergunta são:

<details>

<summary>Atividade principal da empresa</summary>

* **AGRICULTURE-RELATED-SERVICES** = Agricultura, Pecuária, Floresta, Aquicultura e Serviços Relacionados.
* **ARTS-CULTURE-RECREATION** = Artes, Cultura e Recreação (exceto Esportes).
* **ADMINISTRATIVE-ACTIVITIES-COMPLEMENTARY** = Atividades Administrativas e Serviços Complementares - Locação, Mão de Obra, Segurança, Administração Imobiliária.
* **HEALTH-CARE** = Atividades de Atenção a Saúde.
* **LEGAL-ACCOUNTING-AUDITING** = Atividades Jurídicas, de Contabilidade e de Auditoria.
* **RETAIL-TRADE** = Comércio Atacadista E/ou Varejista.
* **TRADE-REPAIR-MAINTENANCE** = Comércio, Reparação e Manutenção de Veículos Automotores e Motocicletas.
* **CREDIT-UNIONS** = Cooperativas de Crédito.
* **ELECTRICITY-OTHER-UTILITIES** = Eletricidade, Gás e Outras Utilidades, Exceto Concessões.
* **MANUFACTURE-COMPUTER-EQUIPMENT** = Fabricação de Equipamentos de Informática, Produtos Eletrônicos e Ópticos.
* **MANUFACTURE-MACHINERY-EQUIPMENT** = Fabricação de Máquinas e Equipamentos.
* **MANUFACTURE-ELECTRICAL-MACHINES** = Fabricação de Máquinas, Aparelhos e Materiais Elétricos.
* **MANUFACTURE-FURNITURE-WOOD** = Fabricação de Móveis e Produtos de Madeira.
* **MANUFACTURE-FOOD-PRODUCTS** = Fabricação de Produtos Alimentício e Bebidas.
* **MANUFACTURE-PLASTIC-MATERIAL** = Fabricação de Produtos de Borracha e de Material Plástico.
* **MANUFACTURE-METAL-PRODUCTS-EXCEPT-MACHINES** = Fabricação de Produtos de Metal, Exceto Máquinas e Equipamentos.
* **MANUFACTURE-NON-METALLIC-MINERAL** = Fabricação de Produtos de Minerais Não-metálicos.
* **MANUFACTURE-VARIED-PRODUCTS** = Fabricação de Produtos Diversos.
* **MANUFACTURE-PHARMACEUTICAL-CHEMICAL** = Fabricação de Produtos Farmacêuticos e/ou Químicos.
* **MANUFACTURE-TEXTILE-PRODUCTS** = Fabricação de Produtos Têxteis e Confecção, Incluindo Artigos de Couro.
* **MANUFACTURE-MOTOR-VEHICLES** = Fabricação de Veículos Automotores, Reboques e Carrocerias.
* **REAL-ESTATE** = Imobiliárias.
* **MAINTENANCE-REPAIR-INSTALLATION** = Manutenção, Reparação e Instalação de Máquinas e Equipamentos.
* **METALLURGY** = Metalurgia.
* **PAPER-PULP** = Papel e Celulose.
* **IT-SERVICES** = Serviços de Tecnologia da Informação.
* **GRAPHIC-SERVICES** = Serviços Gráficos - Impressão e Gravações.

</details>

> **Code**: NET-PATRIMONY\
> **Tipo**: `currency`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir patrimônio líquido.
>
> ❕ Exemplo: "R$ 1.000,00"

***

> **Code**: TOTAL-ASSETS\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir total de ativos.\
>
>
> Os valores possíveis para esta pergunta são:

<details>

<summary>Total de ativos</summary>

* **0.00-1000000.00** = Entre R$ 0,00 e R$ 1.000.000,00
* **1000000.01-3000000.00** = Entre R$ 1.000.000,01 e R$ 3.000.000,00
* **3000000.01-5000000.00** = Entre R$ 3.000.000,01 e R$ 5.000.000,00
* **5000000.01-10000000.00** = Entre R$ 5.000.000,01 e R$ 10.000.000,00
* **10000000.01-15000000.00** = Entre R$ 10.000.000,01 e R$ 15.000.000,00
* **15000000.01-20000000.00** = Entre R$ 15.000.000,01 e R$ 20.000.000,00
* **20000000.01-30000000.00** = Entre R$ 20.000.000,01 e R$ 30.000.000,00
* **30000000.01-40000000.00** = Entre R$ 30.000.000,01 e R$ 40.000.000,00
* **40000000.01-50000000.00** = Entre R$ 40.000.000,01 e R$ 50.000.000,00
* **50000000.01-60000000.00** = Entre R$ 50.000.000,01 e R$ 60.000.000,00
* **60000000.01-70000000.00** = Entre R$ 60.000.000,01 e R$ 70.000.000,00
* **70000000.01-80000000.00** = Entre R$ 70.000.000,01 e R$ 80.000.000,00
* **80000000.01-90000000.00** = Entre R$ 80.000.000,01 e R$ 90.000.000,00
* **90000000.01-100000000.00** = Entre R$ 90.000.000,01 e R$ 100.000.000,00
* **100000000.01-200000000.00** = Entre R$ 100.000.000,01 e R$ 200.000.000,00
* **200000000.01-300000000.00** = Entre R$ 200.000.000,01 e R$ 300.000.000,00
* **300000000.01-400000000.00** = Entre R$ 300.000.000,01 e R$ 400.000.000,00
* **400000000.01-500000000.00** = Entre R$ 400.000.000,01 e R$ 500.000.000,00
* **500000000.01-600000000.00** = Entre R$ 500.000.000,01 e R$ 600.000.000,00
* **600000000.01-700000000.00** = Entre R$ 600.000.000,01 e R$ 700.000.000,00
* **700000000.01-800000000.00** = Entre R$ 700.000.000,01 e R$ 800.000.000,00
* **800000000.01-900000000.00** = Entre R$ 800.000.000,01 e R$ 900.000.000,00
* **900000000.01-1000000000.00** = Entre R$ 900.000.000,01 e R$ 1.000.000.000,00

</details>

> **Code**: REVENUES\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> Pergunta usada para definir o faturamento anual.\
>
>
> Os valores possíveis para esta pergunta são:

<details>

<summary>Faturamento anual</summary>

* **0.00-50000.00** = Entre R$ 0 e R$ 50.000,00
* **50000.01-100000.00** = Entre R$ 50.000,01 e R$ 100.000,00
* **100000.01-150000.00** = Entre R$ 100.000,01 e R$ 150.000,00
* **150000.01-200000.00** = Entre R$ 150.000,01 e R$ 200.000,00
* **200000.01-250000.00** = Entre R$ 200.000,01 e R$ 250.000,00
* **250000.01-350000.00** = Entre R$ 250.000,01 e R$ 350.000,00
* **350000.01-500000.00** = Entre R$ 350.000,01 e R$ 500.000,00
* **500000.01-800000.00** = Entre R$ 500.000,01 e R$ 800.000,00
* **800000.01-1000000.00** = Entre R$ 800.000,01 e R$ 1.000.000,00
* **1000000.01-1500000.00** = Entre R$ 1.000.000,01 e R$ 1.500.000,00
* **1500000.01-2500000.00** = Entre R$ 1.500.000,01 e R$ 2.500.000,00
* **2500000.01-5000000.00** = Entre R$ 2.500.000,01 e R$ 5.000.000,00
* **5000000.01-7500000.00** = Entre R$ 5.000.000,01 e R$ 7.500.000,00
* **7500000.01-10000000.00** = Entre R$ 7.500.000,01 e R$ 10.000.000,00
* **10000000.01-15000000.00** = Entre R$ 10.000.000,01 e R$ 15.000.000,00
* **15000000.01-20000000.00** = Entre R$ 15.000.000,01 e R$ 20.000.000,00
* **20000000.01-25000000.00** = Entre R$ 20.000.000,01 e R$ 25.000.000,00
* **25000000.01-30000000.00** = Entre R$ 25.000.000,01 e R$ 30.000.000,00
* **30000000.01-34000000.00** = Entre R$ 30.000.000,01 e R$ 34.000.000,00
* **34000000.01-40000000.00** = Entre R$ 34.000.000,01 e R$ 40.000.000,00
* **40000000.01-45000000.00** = Entre R$ 40.000.000,01 e R$ 45.000.000,00
* **45000000.01-50000000.00** = Entre R$ 45.000.000,01 e R$ 50.000.000,00
* **50000000.01-60000000.00** = Entre R$ 50.000.000,01 e R$ 60.000.000,00
* **60000000.01-72000000.00** = Entre R$ 60.000.000,01 e R$ 72.000.000,00
* **72000000.01-82000000.00** = Entre R$ 72.000.000,01 e R$ 82.000.000,00
* **82000000.01-100000000.00** = Entre R$ 82.000.000,01 e R$ 100.000.000,00
* **100000000.01-200000000.00** = Entre R$ 100.000.000,01 e R$ 200.000.000,00
* **200000000.01-300000000.00** = Entre R$ 200.000.000,01 e R$ 300.000.000,00
* **300000000.01-500000000.00** = Entre R$ 300.000.000,01 e R$ 500.000.000,00
* **500000000.01-700000000.00** = Entre R$ 500.000.000,01 e R$ 700.000.000,00
* **700000000.01-1000000000.00** = Entre R$ 700.000.000,01 e R$ 1.000.000.000,0

</details>

> **Code**: COMPANY-SOLVENT\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir se a empresa contratante da apólice está solvente.
>
> ❕ So é aceito como `true`

***

> **Code**: INQUIRIES-ADMINISTRATIVE-CRIMINAL-PROCEDURES\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir se o proponente Possui Inquéritos, Procedimentos Administrativos E/ou Criminais Contra os Segurados.
>
> ❕ So é aceito como `false`

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
> Pergunta usada para o proponente descrever as reclamações.

***

> **Code**: CLAIM-EXPECTATION-AGREEMENT\
> **Type**: `boolean`\
> ❗ Obrigatório que esteja incluído no array (se CLAIM-EXPECTATION for TRUE).
>
> Pergunta usada para definir "**Entendimento e concordância**" se definida como true, indica que positivamente "**Entendimento e concordância do conhecimento de reclamações contra os administradores atuais e/ou anteriores.**"

***

> **Code**: COVERAGE-PENALTIES\
> **Tipo**: `boolean`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir se deseja Cobertura para Multas e Penalidades.

***

> **Code**: TERRITORIALITY\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array. Atualmente so atendemos seguros de D\&O no Brasil\
> Pergunta usada para definir a Territorialidade.\
>
>
> Os possíveis valores para esta pergunta são:
>
> * **BR =** Brasil

***

> **Code**: SCOPE\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array. Atualmente so atendemos seguros de D\&O nacionais.\
> Pergunta usada para definir o Âmbito de trabalho da empresa.\
>
>
> Os possíveis valores para esta pergunta são:
>
> * **NATIONAL =** nacional

***

> **Code**: PAYMENT-METHOD\
> **Type**: `text`\
> ❗ Obrigatório que esteja incluído no array. (quando for para o endpoint de PROPOSAL).\
> Pergunta usada para definir o método de pagamento.\
>
>
> Os possíveis valores para esta pergunta são:
>
> * **TICKET**

***

> **Code**: LIMITS\
> **Type**: `array<array<answer>>`\
> ❗ Obrigatório que esteja incluído no array.
>
> Campo para definir Limite e Franquia, veremos mais detalhadamente a seguir.

> **Code**: LIMIT\
> **Type**: `decimal`\
> ❗ Obrigatório que esteja incluído no array.\
>
>
> Os valores possíveis para esta pergunta são:

<details>

<summary>Limites</summary>

* **500000.00m** = R$ 500.000,00
* **1000000.00m** = R$ 1.000.000,00
* **1500000.00m** = R$ 1.500.000,00
* **2000000.00m** = R$ 2.000.000,00
* **2500000.00m** = R$ 2.500.000,00
* **3000000.00m** = R$ 3.000.000,00
* **3500000.00m** = R$ 3.500.000,00
* **4000000.00m** = R$ 4.000.000,00
* **4500000.00m** = R$ 4.500.000,00
* **5000000.00m** = R$ 5.000.000,00
* **5500000.00m** = R$ 5.500.000,00
* **6000000.00m** = R$ 6.000.000,00
* **6500000.00m** = R$ 6.500.000,00
* **7000000.00m** = R$ 7.000.000,00
* **7500000.00m** = R$ 7.500.000,00
* **8000000.00m** = R$ 8.000.000,00
* **8500000.00m** = R$ 8.500.000,00
* **9000000.00m** = R$ 9.000.000,00
* **9500000.00m** = R$ 9.500.000,00
* **10000000.00m** = R$ 10.000.000,00

</details>

## Response

````json
{
    "item": {
        "quotationIdentifier": "9eaee84d-1825-4651-ae06-0e173cdc6df3",
        "status": "Draft",
        "pricing": [
            {
                "variantIdentifier": "a33d382e-e15e-4ef4-b751-e9140f29e3dd",
                "underwriting": {
                    "approved": true,
                    "evaluations": []
                },
                "price": {
                    "commission": 218.95,
                    "grievanceDiscount": 0.0,
                    "netValue": 1094.75,
                    "interestValue": 0.0,
                    "taxValue": 80.79,
                    "totalValue": 1175.54,
                    "policyLimit": 1000000.0,
                    "rates": [
                        {
                            "code": "COMPANY-ACTIVITY",
                            "description": "Atividade",
                            "limit": 1000000.0,
                            "netValue": 52.25,
                            "deductible": {
                                "code": "NO-DEDUCTIBLE",
                                "text": "Sem franquia"
                            }
                        },
                        {
                            "code": "TOTAL-ASSETS",
                            "description": "Ativos",
                            "limit": 1000000.0,
                            "netValue": 23.05,
                            "deductible": {
                                "code": "NO-DEDUCTIBLE",
                                "text": "Sem franquia"
                            }
                        },
                        {
                            "code": "REVENUES",
                            "description": "Faturamento",
                            "limit": 1000000.0,
                            "netValue": 13.06,
                            "deductible": {
                                "code": "NO-DEDUCTIBLE",
                                "text": "Sem franquia"
                            }
                        },
                        {
                            "code": "LIMIT",
                            "description": "Limite",
                            "limit": 1000000.0,
                            "netValue": 1006.39,
                            "deductible": {
                                "code": "NO-DEDUCTIBLE",
                                "text": "Sem franquia"
                            }
                        }
                    ]
                },
                "payment": {
                    "financialType": "Charge",
                    "paymentOptions": [
                        {
                            "paymentMethod": "Ticket",
                            "paymentType": "Ticket",
                            "installments": [
                                {
                                    "identifier": "1ea02901-317e-421e-b9d8-bdc7d131648c",
                                    "number": 1,
                                    "commissionValue": 218.95,
                                    "netValue": 1094.75,
                                    "interestValue": 0.0,
                                    "taxValue": 80.79,
                                    "totalValue": 1175.54,
                                    "installmentValue": 1175.54,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 80.79,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "ef03ea07-05a2-49a8-9b33-3c7185fbe3d2",
                                    "number": 2,
                                    "commissionValue": 218.95,
                                    "netValue": 1094.75,
                                    "interestValue": 0.0,
                                    "taxValue": 80.79,
                                    "totalValue": 1175.54,
                                    "installmentValue": 587.77,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 40.4,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "b0e28bb2-6b08-4e6c-aaf7-bfcd2b671471",
                                    "number": 3,
                                    "commissionValue": 218.95,
                                    "netValue": 1094.75,
                                    "interestValue": 0.0,
                                    "taxValue": 80.79,
                                    "totalValue": 1175.54,
                                    "installmentValue": 391.85,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 26.93,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "b3a10a19-8fe9-4307-8a0d-faefe7d28020",
                                    "number": 4,
                                    "commissionValue": 218.95,
                                    "netValue": 1094.75,
                                    "interestValue": 0.0,
                                    "taxValue": 80.79,
                                    "totalValue": 1175.54,
                                    "installmentValue": 293.88,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 20.2,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z"
                                    ]
                                },
                                {
                                    "identifier": "95c2e0cc-4a03-4cd9-9a5e-fa3d2d9cb99b",
                                    "number": 5,
                                    "commissionValue": 218.95,
                                    "netValue": 1094.75,
                                    "interestValue": 0.0,
                                    "taxValue": 80.79,
                                    "totalValue": 1175.54,
                                    "installmentValue": 235.11,
                                    "installmentInterest": 0.0,
                                    "installmentTax": 16.16,
                                    "dueDates": [
                                        "2023-06-01T00:00:00Z",
                                        "2023-07-01T12:00:00Z",
                                        "2023-08-01T12:00:00Z",
                                        "2023-09-01T12:00:00Z",
                                        "2023-10-01T12:00:00Z"
                                    ]
                                }
                            ]
                        }
                    ]
                }
            }
        ]
    },
    "success": true,
    "executed": "2023-05-25T14:26:40.814527Z"
}
```
````

### Explicando campos de retorno

> **Field**: success\
> **Type**: `boolean`
>
> Indica se a requisição foi feita com sucesso.

***

> **Field**: executed\
> **Type**: `date`
>
> Data em que a requisição foi feita.

***

> **Field**: errors\
> **Type**: `array`
>
> Array de erros ao fazer a requisição.

***

> **Field**: item.quotationIdentifier\
> **Type**: `guid`
>
> Identificador da cotação.

***

> **Field**: item.status\
> **Type**: `integer`
>
> Status da cotação.

***

> **Field**: item.expiredAt\
> **Type**: `date`
>
> Data de expiração da cotação.

***

> **Field**: item.quotationDocumentUrl\
> **Type**: `text`
>
> Url do documento de cotação.

***

> **Field**: item.pricing\
> **Type**: `array`
>
> Retorna as propriedades do item, taxas, valores, tipos de pagamentos.\
> Array de items cotados. Ele pode retornar mais de 1 item também.

***

> **Field**: item.pricing\[].variantIdentifier\
> **Type**: `guid`
>
> Identificador do item cotado.

***

> **Field**: item.pricing\[].underwriting.approved\
> **Type**: `boolean`
>
> Retorna true ou false referente as regras de subscrição do produto.

***

> **Field**: item.pricing\[].underwriting.evaluations\
> **Type**: `array`
>
> Retorna aviso referente as questões do questionário de risco do produto.

***

> **Field**: item.pricing\[].price.commission\
> **Type**: `decimal`
>
> Comissão de corretagem.

***

> **Field**: item.pricing\[].price.grievanceDiscount\
> **Type**: `decimal`
>
> Porcentagem de agravo adicionada ao valor da cotação, onde os valores permitidos vão de 0% até 500%.

***

> **Field**: item.pricing\[].price.itemValue\
> **Type**: `decimal`
>
> Valor do item.

***

> **Field**: item.pricing\[].price.netValue\
> **Type**: `decimal`
>
> Valor de prêmio líquido sem o IOF.

***

> **Field**: item.pricing\[].price.interestValue\
> **Type**: `decimal`
>
> Valor de juros (Por enquanto nenhum produto possui juros, nem para boleto e nem para cartão, mas futuramente terá para boleto).

***

> **Field**: item.pricing\[].price.taxValue\
> **Type**: `decimal`
>
> Valor de IOF.

***

> **Field**: item.pricing\[].price.totalValue\
> **Type**: `decimal`
>
> Valor de Prêmio Total, composto pelo prêmio líquido somado ao IOF.

***

> **Field**: item.pricing\[].price.policyLimit\
> **Type**: `decimal`
>
> Valor de Limite da apólice.

***

> **Field**: item.pricing\[].price.rates\
> **Type**: `array`
>
> Trata-se de um array, que retornará todas as coberturas contratadas para o produto.

***

> **Field**: item.pricing\[].payment.financialType\
> **Type**: `text`
>
> Trata-se do tipo de financeiro que no caso é "Cobrança".

***

> **Field**: item.pricing\[].payment.paymentOptions\
> **Type**: `array`
>
> Retorna as opções de pagamento disponíveis que são: Boleto e Cartão de crédito.

***

> **Field**: item.pricing\[].price.rates\[].code\
> **Type**: `text`
>
> Exibe o código que identifica a ou as coberturas contratadas.

***

> **Field**: item.pricing\[].price.rates\[].description\
> **Type**: `text`
>
> Trata-se do nome da cobertura em português.

***

> **Field**: item.pricing\[].price.rates\[].limit\
> **Type**: `decimal`
>
> Trata-se do valor do limite da cobertura.

***

> **Field**: item.pricing\[].price.rates\[].netValue\
> **Type**: `decimal`
>
> Valor do prêmio específico de cada cobertura contratada.

***

> **Field**: item.pricing\[].price.rates\[].deductible.code\
> **Type**: `text`
>
> Trata-se do código identificador de cada franquia.

***

> **Field**: item.pricing\[].price.rates\[].deductible.text\
> **Type**: `text`
>
> Nome da franquia selecionada em português - Ex: "Padrão".

***

> **Field**: item.pricing\[].price.rates\[].deductible.description\
> **Type**: `text`
>
> Descrição da franquia.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].paymentMethod\
> **Type**: `text`
>
> Retorna o nome da forma de pagamento que pode ser: Ticket (Boleto) ou CreditCard (Cartão de Crédito).

***

> **Field**: item.pricing\[].payment.paymentOptions\[].paymentType\
> **Type**: `text`
>
> Forma de pagamento que pode ser escolhida: Boleto ou Cartão de crédito.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\
> **Type**: `array`
>
> Retorna a quantidade de parcelas disponíveis para realizar o pagamento referente ao tipo de pagamento.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].identifier\
> **Type**: `guid`
>
> Código identificador da parcela.\
> Esté é o código necessário enviar ao selecionar o método de pagamento.
>
> Exemplo: Se foi selecionado cartão de crédito, enviar o identificador daquele meio de pagamento.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].number\
> **Type**: `integer`
>
> Número da respectiva parcela (2 parcela, número 2).

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].commissionValue\
> **Type**: `decimal`
>
> Valor de comissão de cada parcela.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].netValue\
> **Type**: `decimal`
>
> Valor de prêmio líquido de cada parcela, ou seja, sem o IOF.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].interestValue\
> **Type**: `decimal`
>
> Valor de juros de cada parcela.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].taxValue\
> **Type**: `decimal`
>
> IOF que implica em cada parcela.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].totalValue\
> **Type**: `decimal`
>
> Valor total de cada parcela que é composto do valor líquido + IOF.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].installmentValue\
> **Type**: `decimal`
>
> Valor total da parcela.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].installmentInterest\
> **Type**: `decimal`
>
> Valor de juros da parcela.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].installmentTax\
> **Type**: `decimal`
>
> Valor de IOF de cada parcela.

***

> **Field**: item.pricing\[].payment.paymentOptions\[].installments\[].dueDates\
> **Type**: `array<string>`
>
> Datas de vencimento da parcela caso a forma de pagamento seja boleto.
