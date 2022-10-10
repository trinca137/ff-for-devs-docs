
> **Code**: ITEMS </br>
> **Tipo**: ```array<answer>``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text>
> 
> - Esta pergunta em formato de array de answer é usado para enviar as perguntas mais específicas do produto em questão, neste caso bike. Veremos essas perguntas com mais detalhes adiante.

-------------------------------------------------------------------------------------------

> ❕ Como explicado mais acima, o campo **items** dentro do **array de answer** tem como finalidade enviar as perguntas mais específicas do produto que esta sendo contado (bikes), abaixo você vera os valores que poderão/deverão estar inclusos nesse array.

```json
{
    "operationCode": "BIKE-MULTIPLE-PERIL-PARTNER",
    "answers": [
        {
            "code": "MODALITY",
            "answer": "BIKE-MULTIPLE-PERIL"
        },
        {
            "code": "PERSON-TYPE",
            "answer": "NATURAL"
        },
        {
            "code": "ITEMS",
            "answer": [
                {
                     {
                        "code": "SERIAL-NUMBER",
                        "answer": "15"
                     },
                     {
                        "code": "ITEM-TYPE",
                        "answer": "TRADITIONAL"
                     },
                }
            ]
        }
    ]
}
```