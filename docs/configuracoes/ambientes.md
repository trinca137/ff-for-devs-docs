# Ambientes

A API do 4Devs possui um ambiente de homologação para realização de testes e um ambiente de produção, cada um com sua respectiva Chave de Acesso.

#### Homologação
https://azuh1-br-fairfax-gateway.azure-api.net/partner/

#### Produção
https://azup-br-fairfax-gateway.azure-api.net/partner/

!!! Sobre

    A URL de cada recurso vai conter o parametro **{{url_ambiente}}** como prefixo, que deve ser substituido de acordo com o ambiente para o qual serão feitas as requisições.
    
    Exemplo de chamada: https://azuh1-br-fairfax-gateway.azure-api.net/partner/api/v1/quotation