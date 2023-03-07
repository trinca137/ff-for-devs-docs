# Formulário cotação

{% hint style="info" %}
Esse json abaixo contém as informações onde TODOS os produtos utilizam, na pagina do produto é necessário adicionar os campos (contém exemplo nos produtos)

As respostas estão usando valores referentes ao produto "Bike"
{% endhint %}

### Explicando formulário

```json
{
	"operationCode": "BIKE-MULTIPLE-PERIL-PARTNER",
	"registerNumber": "100000",
	"answers":[],
}
```

> **Field**: OperationCode\
> **Tipo**: `text`\
> ❗ Campo Obrigatório.
>
> Campo usado para definir qual produto está sendo cotado. Neste caso, o produto é "Bike", representado pelo operation code "BIKE-MULTIPLE-PERIL-PARTNER".

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

```json
{
    "operationCode": "BIKE-MULTIPLE-PERIL-PARTNER",
    "registerNumber": "100000",
    "answers": [
        {
            "code": "MODALITY",
            "answer": "BIKE-MULTIPLE-PERIL"
        }
    ]
}
```

> **Code**: MODALITY\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir qual modalidade está sendo cotado. Neste caso, a modalidade é "Bike", representado pelo código **"BIKE-MULTIPLE-PERIL"**.

> **Code**: PERSON-TYPE\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.\
> ❗ O produto de D\&O não contém pessoa física, apenas pessoa jurídica.
>
> Pergunta usada para saber se a cotação está sendo preenchida por uma Pessoa Física ou Jurídica. Os valores possíveis para esta pergunta são:
>
> * **NATURAL** = significa que a pessoa em questão é física.
> * **LEGAL** = significa que a pessoa em questão é jurídica.

> **Code**: CONGENER\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir se a cotação em questão é um Seguro Novo ou uma Renovação. Os valores possíveis para esta pergunta são:\
> \\
>
> * **NEW** = indica que é um novo seguro.
> * **RENEWAL** = indica que é a renovação de um seguro.

***

> **Code**: PREVIOUS-INSURER\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array. (se a cotação for uma renovação de outra seguradora).
>
> Pergunta usada para definir qual é a seguradora anterior.\
> Neste campo, deve-se enviar um **CNPJ**.

***

> **Code**: PREVIOUS-INSURER-NAME\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array. (se a cotação for uma renovação de outra seguradora).
>
> Pergunta usada para definir o nome da seguradora anterior.

***

> **Code**: START-VIGENCY-DATE\
> **Tipo**: `date`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o início da vigência do seguro.

***

> **Code**: VIGENCY-DURATION\
> **Tipo**: `integer`\
> No momento so é possivel o padrão, não sendo possível mudar a duração da vigência.
>
> Pergunta usada para definir a duração da vigência em anos. O valor padrão é 1.\
> ❗Atualmente não é possivel colocar mais do que 1 ano.

***

> **Code**: IDENTITY\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir a identificação do segurado, seja ela um **CPF** ou um **CNPJ**.

***

> **Code**: INSURED-NAME\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o nome do segurado.

***

> **Code**: INSURED-EMAIL\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o e-mail do segurado.

***

> **Code**: INSURED-CELLPHONE\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o telefone ou celular do segurado.

***

> **Code**: INSURED-ADDRESS-ZIPCODE\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o código postal (CEP) do segurado.

***

> **Code**: INSURED-ADDRESS-STREET\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir a rua do segurado.

***

> **Code**: INSURED-ADDRESS-NUMBER\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o número da moradia do segurado.

***

> **Code**: INSURED-ADDRESS-COMPLEMENT\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o número da moradia do segurado.

***

> **Code**: INSURED-ADDRESS-NEIGHBORHOOD\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o bairro do segurado.

***

> **Code**: INSURED-ADDRESS-CITY\
> **Tipo**: `text`\
> ❗ Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir a cidade do segurado.

***

> **Code**: INSURED-ADDRESS-STATE\
> **Tipo**: `text`\
> ❗Obrigatório que esteja incluído no array.
>
> Pergunta usada para definir o estado do segurado.

***

> **Code**: COMMISSION\
> **Tipo**: `decimal`\
> ❗Obrigatório que esteja incluído\
> Pergunta usada para definir a comissão.
>
> Pode ser enviado valores entre 1 e 30.\
> Valor padrão é 20.00.

***

> **Code**: GRIEVANCE-DISCOUNT\
> **Tipo**: `decimal`
>
> Pergunta usada para definir Agravo (aumento de preço sobre o netValue\* da cotação).\
> O Padrão é 0.\
> \* Preço líquido do produto sem IOF.
