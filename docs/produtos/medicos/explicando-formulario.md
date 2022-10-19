
>**Code**: PROFESSIONAL-REGISTER <br>
>**Type**: ```text``` <br>
> <text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
>
>Pergunta usada para definir o rigistro do profissional

--------------------------------------------------------------------------------


>**Code**: PROFESSION <br>
>**Type**: ```text``` <br>
> <text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
>
>Pergunta usada para definir Profissão. Os valores possíveis para esta pergunta são: <br><br>
>
>  - **DOCTOR**</br>



--------------------------------------------------------------------------------


>**Code**: CATEGORIES <br>
>**Type**: ```array<string>``` <br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
>
>Pergunta usada para definir a especialidade medica,pode-se enviar mais de uma resposta dentro desse array de string (exceto se o PERSON-TYPE for NATURAL). Os valores possíveis para esta pergunta são:<br><br>
>
>   - **NO-SURGERY** = Médico sem Cirurgia e Medicina de Urgência e Emergência (disponivel SE PERSON-TYPE for NATURAL)<br>
>
>   - **SURGERY-EXCEPT-PLASTIC** = Médico com Cirurgia (exceto plástico), Anestesiologistas (disponivel SE PERSON-TYPE for NATURAL)<br>
>
>   - **OBSTETRICIAN** = Obstetra (disponivel SE PERSON-TYPE for NATURAL)<br>
>
>   - **PLASTIC-SURGERY** = Cirurgião (ã) Plástico (a) (disponivel SE PERSON-TYPE for NATURAL)<br>
>
>   - **CLINIC-WITHOUT-SURGERY** = Clinicas (outras, sem cirurgia) (disponivel SE PERSON-TYPE for LEGAL)<br>
>
>   - **PATIENT-TRANSPORT** = Transporte de Pacientes (disponivel SE PERSON-TYPE for LEGAL)<br>
>
>   - **HOME-CARE** = Home care (disponivel SE PERSON-TYPE for LEGAL)<br>
>
>   - **SURGERY-CLINIC-EXCEPT-PLASTIC** = Clínica de Cirurgia e/ou Anestesiologia, Exceto Plástica (disponivel SE PERSON-TYPE for igual a LEGAL)<br>
>
>   - **CLINICAL-LABORATORY** = Laboratório de Análises Clínicas (disponivel SE PERSON-TYPE for   LEGAL)<br><br>
>
>   - **BLOOD-BANK** = Bancos de Sangue (disponivel SE PERSON-TYPE for LEGAL)<br>
>
>   - **CLINICAL-OBSTETRICS** = Clínica com Obstetrícia (disponivel SE PERSON-TYPE for LEGAL)<br>
>
>   - **HOSPITAL** = Hospitais (disponivel SE PERSON-TYPE for LEGAL)<br>
>
>   - **PLASTIC-SURGERY-CLINIC** = Clinica de Cirurgia Plástica (disponivel SE PERSON-TYPE for    LEGAL)<br>
>
>   - **CLINICAL-MULTIDISCIPLINARY** = Clínica Multidisciplinar (disponivel SE PERSON-TYPE for    LEGAL)

--------------------------------------------------------------------------------


>**Code**: RESIDENT <br>
>**Type**: ```text``` <br>
> <text class="aviso">❗ Obrigatório que esteja incluido no array (se o PERSON-TYPE for NATURAL ou se CATEGORIES for diferente de PLASTIC-SURGERY)</text><br>
>
>Pergunta usada para definir se o profissional é resident ou nao.

--------------------------------------------------------------------------------


>**Code**: PROCEDURES-ACTIVITIES <br>
>**Type**: ```array<string>``` <br>
>
>Procedimentos e/ou Atividades. pode-se enviar mais de uma resposta dentro desse array de string. Os valores possíveis para esta pergunta são: <br><br>
>
>   - **AESTHETIC-PROCEDURES** = Procedimentos Estéticos Minimamente Invasivos <br>
>   - **ENDOSCOPY-COLONOSCOPY** = Endoscopia e/ou Colonoscopia <br>
>   - **RADIOTHERAPY-CHEMOTHERAPY-IMMUNOTHERAPY** = Radioterapia e/ou Quimioterapia e/ou Imunoterapia <br>
>   - **AESTHETIC-PROCEDURES-MEDICAL-SPECIALTY** = Procedimentos Estéticos relacionados à Especialidade Médica 

--------------------------------------------------------------------------------


