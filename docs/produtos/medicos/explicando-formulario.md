
>**Code**: PROFESSIONAL-REGISTER <br>
>**Type**: ```text``` <br>
> <text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
>
>Pergunta usada para definir o registro do profissional.

--------------------------------------------------------------------------------


>**Code**: PROFESSION <br>
>**Type**: ```text``` <br>
> <text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
>
>Pergunta usada para definir a profissão do segurado. Os possíveis valores para esta pergunta são: <br><br>
>
>  - **DOCTOR**</br>



--------------------------------------------------------------------------------


>**Code**: CATEGORIES <br>
>**Type**: ```array<string>``` <br>
><text class="aviso">❗ Obrigatório que esteja incluido no array.</text><br>
>
>Pergunta usada para definir a especialidade médica. Pode-se enviar mais de uma resposta dentro desse array de string (exceto se o PERSON-TYPE for NATURAL), sendo elas:<br><br>
>
>   - **NO-SURGERY** = Médico sem Cirurgia e Medicina de Urgência e Emergência (disponível SE PERSON-TYPE for NATURAL).<br>
>
>   - **SURGERY-EXCEPT-PLASTIC** = Médico com Cirurgia (exceto Plástico), Anestesiologistas (disponível SE PERSON-TYPE for NATURAL).<br>
>
>   - **OBSTETRICIAN** = Obstetra (disponível SE PERSON-TYPE for NATURAL).<br>
>
>   - **PLASTIC-SURGERY** = Cirurgião(ã) Plástico(a) (disponível SE PERSON-TYPE for NATURAL).<br>
>
>   - **CLINIC-WITHOUT-SURGERY** = Clínicas (outras, sem cirurgia) (disponível SE PERSON-TYPE for LEGAL).<br>
>
>   - **PATIENT-TRANSPORT** = Transporte de Pacientes (disponível SE PERSON-TYPE for LEGAL).<br>
>
>   - **HOME-CARE** = Home care (disponível SE PERSON-TYPE for LEGAL).<br>
>
>   - **SURGERY-CLINIC-EXCEPT-PLASTIC** = Clínica de Cirurgia e/ou Anestesiologia, Exceto Plástica (disponível SE PERSON-TYPE for igual a LEGAL).<br>
>
>   - **CLINICAL-LABORATORY** = Laboratório de Análises Clínicas (disponível SE PERSON-TYPE for   LEGAL).<br><br>
>
>   - **BLOOD-BANK** = Bancos de Sangue (disponível SE PERSON-TYPE for LEGAL).<br>
>
>   - **CLINICAL-OBSTETRICS** = Clínica com Obstetrícia (disponível SE PERSON-TYPE for LEGAL).<br>
>
>   - **HOSPITAL** = Hospitais (disponível SE PERSON-TYPE for LEGAL).<br>
>
>   - **PLASTIC-SURGERY-CLINIC** = Clínica de Cirurgia Plástica (disponível SE PERSON-TYPE for    LEGAL).<br>
>
>   - **CLINICAL-MULTIDISCIPLINARY** = Clínica Multidisciplinar (disponível SE PERSON-TYPE for    LEGAL).

--------------------------------------------------------------------------------


>**Code**: RESIDENT <br>
>**Type**: ```text``` <br>
> <text class="aviso">❗ Obrigatório que esteja incluído no array (se o PERSON-TYPE for NATURAL ou se CATEGORIES for diferente de PLASTIC-SURGERY).</text><br>
>
>Pergunta usada para definir se o profissional é residente ou não.

--------------------------------------------------------------------------------


>**Code**: PROCEDURES-ACTIVITIES <br>
>**Type**: ```array<string>``` <br>
>
>Procedimentos e/ou atividades. Pode-se enviar mais de uma resposta dentro desse array de string, sendo elas:<br><br>
>
>   - **AESTHETIC-PROCEDURES** = Procedimentos Estéticos Minimamente Invasivos. <br>
>   - **ENDOSCOPY-COLONOSCOPY** = Endoscopia e/ou Colonoscopia. <br>
>   - **RADIOTHERAPY-CHEMOTHERAPY-IMMUNOTHERAPY** = Radioterapia e/ou Quimioterapia e/ou Imunoterapia. <br>
>   - **AESTHETIC-PROCEDURES-MEDICAL-SPECIALTY** = Procedimentos Estéticos relacionados à Especialidade Médica.

--------------------------------------------------------------------------------





