!!! Aviso

      Isso é um padrão de envio para todos produtos.
      Verifique os campos adicionais para cada produto para adicionar no array de **```Answers```**

### 💡Desmistificando o json de request - part 1

```json
{
	"operationCode":"BIKE-MULTIPLE-PERIL-PARTNER",
	"answers":[],
}
```

> **Field**: OperationCode </br>
> **Tipo**: ```text``` </br>
> <text class="aviso">❗campo obrigatório</text> </br>
> Campo usado para definir qual produto esta sendo cotado, neste caso o produto é bike, representado pelo operation code "BIKE-MULTIPLE-PERIL-PARTNER".

---------------------------------------------------------

> **Field**: Answers </br>
> **Tipo**: ```array<answer>``` </br>
> <text class="aviso"> ❗ Campo obrigatório</text> </br>
> Campo usado para enviar as perguntas mais gerais de uma cotação, um exemplo de pergunta seria se a pessoa que esta realizando a operação é jurídica ou física.</br>
> Veremos mais detalhes sobre essas perguntas mais abaixo na documentacao.
Abaixo, podemos ver a modelagem de answer.

### 💡 Desmistificando o json de request - part 2


> O campo **answers** tem como finalidade enviar as perguntas referentes a cotação, abaixo você vera os valores que poderão/deverão estar inclusos nesse array.

```json
{
    "operationCode": "BIKE-MULTIPLE-PERIL-PARTNER",
    "answers": [
        {
            "code": "MODALITY",
            "answer": "BIKE-MULTIPLE-PERIL"
        }
    ]
}
```


> **Code**: MODALITY </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir qual produto esta sendo cotado, neste caso o produto é bike, representado pelo operation code **BIKE-MULTIPLE-PERIL** 

------------------------------------------------------------------------

> **Code**: PERSON-TYPE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatorio que esteja incluido no array </text> </br>
> 
> - Pergunta usada para saber que a cotacao esta sendo feita por uma pessoa física ou jurídica. </br>
> 
***Os possiveis valores para esta pergunta são:*** </br>
> **NATURAL =** Significa que a pessoa em questão é física </br>
> **LEGAL =** Significa que a pessoa em questão é jurídica

------------------------------------------------------------------------

> **Code**: START-VIGENCY-DATE </br>
> **Tipo**: ```date``` </br>
> <text class="aviso"> ❗Obrigatorio que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o inicio da vigencia do seguro.

------------------------------------------------------------------------

> **Code**: VIGENCY-DURATION </br>
> **Tipo**: ```integer``` </br>
> No momento so é possivel o padrão, não sendo possível mudar a duração da vigência </br>
> 
> - Pergunta usada para definir a duração da vigência em anos, o valor padrao é 1.

------------------------------------------------------------------------

> **Code**: VIGENCY-RETROACTIVITY-AGREEMENT </br>
> **Tipo**: ```boolean``` </br>
> 
> - Pergunta usada para definir "**Entendimento e concordância de vigência retroativa**".
 Se defida  como true, indica que "**Estou ciente e de acordo que não possuo conhecimento de qualquer fato que possa acarretar uma reclamação futura entre o início de vigência e a data de emissão da apólice**"

------------------------------------------------------------------------

> **Code**: CONGENER </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir se a cotação em questão é um seguro novo, ou uma renovação.
> 
> ***Os possíveis valores para esta pergunta são:***</br>
> **NEW =** Indica que é um seguro novo. </br>
> **RENEW =** Indica que é a renovação de um seguro.

------------------------------------------------------------------------

> **Code**: PREVIOUS-INSURER </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array (se a cotação for uma renovação de outra seguradora) </text>
> 
> - Pergunta usada para definir qual era a seguradora anterior. </br>
> - Neste campo se deve enviar um **cnpj**.

------------------------------------------------------------------------

> **Code**: PREVIOUS-NAME</br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array (se a cotacao for uma renovação de outra seguradora)</text></br>
> 
> - Pergunta usada para definir o nome da seguradora anterior.

------------------------------------------------------------------------

> **Code**: INSURED-NAME </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o nome do segurado

------------------------------------------------------------------------

> **Code**: INSURED-EMAIL </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o email do segurado

------------------------------------------------------------------------

> **Code**: IDENTITY </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir a identificação do segurado, seja ela um **cpf** ou um **cnpj**

------------------------------------------------------------------------

> **Code**: GENDER </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o genero do segurado </br>
> 
> ***Os possiveis valores para esta pergunta são:*** </br>
> **M =** Masculino </br>
> **F =** Feminino </br>
> **I =** Não informado </br>
> 
> - Caso nada seja enviado, o valor padrao é "**I**".

------------------------------------------------------------------------

> **Code**: INSURED-CELLPHONE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o telefone do segurado.

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-ZIPCODE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o codigo postal do segurado

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-STREET </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir a rua do segurado

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-NUMBER </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o número da moradia do segurado

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-COMPLEMENT </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatorio que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o numero da moradia do segurado

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-NEIGHBORHOOD </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o bairro do segurado

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-CITY </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir a cidade do segurado

------------------------------------------------------------------------

> **Code**: INSURED-ADDRESS-STATE </br>
> **Tipo**: ```text``` </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido no array </text> </br>
> 
> - Pergunta usada para definir o estado do segurado

------------------------------------------------------------------------

> **Code**: COMMISSION </br>
> **Tipo**: ```decimal``` </br>
> - Pergunta usada para definir a comissao. </br>
> <text class="aviso"> ❗Obrigatório que esteja incluido</text>
> 
> - Pode ser enviado valores entre 1 e 20
>     - O valor padrao é 20.00


>**Code**: INSURED-BIRTH-DATE <br>
>❗ Obrigatorio que esteja incluido no array (quando for para o endpoint de PROPOSAL) <br>
>**Type**: ```date``` <br>
>Pergunta usada para definir a data de nascimento do segurado <br>

--------------------------------------------------------------------------


>**Code**: PAYMENT-METHOD <br>
>**Type**: ```text``` <br>
>❗ Obrigatorio que esteja incluido no array (quando for para o endpoint de PROPOSAL) <br>
>Pergunta usada para definir o metodo de pagamento <br>
>os possiveis valores para esta pergunta são: <br>
>**CREDIT-CARD** <br>

--------------------------------------------------------------------------


>**Code**: DUE-DAY <br>
>**Type**: ```integer``` <br>
>❗ Obrigatorio que esteja incluido no array  (apenas quando o PAYMENT-METHOD for TICKET)  <br>
>❗ Obrigatorio que esteja incluido no array  (quando for para o endpoint de PROPOSAL) <br>
>Pergunta usada para definir a data de vencimento <br>

---------------------------------------------------------------------------



>**Code**: PAYMENT-INSTALLMENT-IDENTIFIER <br>
>**Type**: ```guid``` <br>
>❗ Obrigatorio que esteja incluido no array (quando for para o endpoint de PROPOSAL) <br>
>O guid que sera enviando nesse campo, é retornado no array de installments, no retorno do endpoint de criar cotacao <br>

------------------------------------------------------------------------------


> **Code**: GRIEVANCE-DISCOUNT </br>
> **Tipo**: ```decimal```
> 
> - Pergunta usada para definir Agravo (aumento de valor acima do valor final da cotação).
> 
> O Padrão é 0

---------------------------------------------------------------------------------


