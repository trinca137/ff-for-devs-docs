# Rate Limits

Para conseguirmos prover maior segurança e tempo de resposta para os usuarios das apis, utilizamos os limites de requests. Nossos limities funcionam da seguinte forma:


Grupo                           | Chamadas                          | Política          | Tempo de espera
---                             | ---                               | ---               | ---
Todas chamadas                  | Qualquer chamada                  | 100 solitações    | 1 minuto
Subscription-Key                | Qualquer chamada = 1 requisição   | 1000 soliticações | Por dia
Receber apólice única           | GET /{versão}/get/{registerNumber}| 20 solicitações   | 20 segundos
Receber lista apólices          | GET /{versão}/get-all             | 10 solicitações   | 20 segundos