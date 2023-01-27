# Rate Limits

Para conseguirmos prover maior segurança e tempo de resposta para os usuarios das apis, utilizamos os limites de requests. Nossos limites funcionam da seguinte forma:

| Grupo                  | Chamadas                           | Política          | Tempo de espera |
| ---------------------- | ---------------------------------- | ----------------- | --------------- |
| Todas chamadas         | Qualquer chamada                   | 100 solitações    | 1 minuto        |
| Subscription-Key       | Qualquer chamada = 1 requisição    | 1000 soliticações | Por dia         |
| Receber apólice única  | GET /{versão}/get/{registerNumber} | 20 solicitações   | 20 segundos     |
| Receber lista apólices | GET /{versão}/get-all              | 10 solicitações   | 20 segundos     |

{% hint style="warning" %}
Ressaltamos a orientação para o parceiro que também limite as chamadas como medida de segurança, para complementar as travas já existentes na API. &#x20;
{% endhint %}

## Retornos

**Erro 429, Chamdas excedidas**

```json
{
    "statusCode": 429,
    "message": "Rate limit is exceeded. Try again in 69 seconds."
}
```

**Erro 403, limites de chamadas da chave atingida.**

```json
{
    "statusCode": 403,
    "message": "Out of call volume quota. Quota will be replenished in 10:25:13."
}
```
