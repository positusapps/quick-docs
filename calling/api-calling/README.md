# WhatsApp Calling

### Importante

- Precisa estar habilitado para o número no workspace a permissão de retorno de ligações.

## API de gerenciamento da Positus

- [Iniciar uma chamada](#iniciar-uma-chamada)
- [Aceitar uma chamada](#aceitar-uma-chamada)
- [Rejeitar uma chamada](#rejeitar-uma-chamada)
- [Encerrar uma chamada](#encerrar-uma-chamada)


### Iniciar uma chamada

Endpoint utilizado para iniciar a chamada:

#### (POST) https://api.positus.global/v2/whatsapp/numbers/{NUMBER_ID}/calls/make

`Body`

https://github.com/positusapps/quick-docs/blob/39cf01e44af4c535ea53cdadc293bc96beb155f1/calling/api-calling/json/calls-make-body.json#L1-L4

`Response`

https://github.com/positusapps/quick-docs/blob/39cf01e44af4c535ea53cdadc293bc96beb155f1/calling/api-calling/json/calls-make-response.json#L1-L3

---

### Aceitar uma chamada

Endpoint utilizado para aceitar a chamada:

#### (POST) https://api.positus.global/v2/whatsapp/numbers/{NUMBER_ID}/calls/accept

`Body`

https://github.com/positusapps/quick-docs/blob/39cf01e44af4c535ea53cdadc293bc96beb155f1/calling/api-calling/json/calls-accept-body.json#L1-L4

`Response`

https://github.com/positusapps/quick-docs/blob/39cf01e44af4c535ea53cdadc293bc96beb155f1/calling/api-calling/json/calls-accept-response.json#L1-L3

---

### Rejeitar uma chamada

Endpoint utilizado para rejeitar a chamada:

#### (POST) https://api.positus.global/v2/whatsapp/numbers/{NUMBER_ID}/calls/reject

`Body`

https://github.com/positusapps/quick-docs/blob/39cf01e44af4c535ea53cdadc293bc96beb155f1/calling/api-calling/json/calls-reject-body.json#L1-L3

`Response`

https://github.com/positusapps/quick-docs/blob/39cf01e44af4c535ea53cdadc293bc96beb155f1/calling/api-calling/json/calls-reject-response.json#L1-L3


---

### Encerrar uma chamada

Endpoint utilizado para encerrar a chamada:

#### (POST) https://api.positus.global/v2/whatsapp/numbers/{NUMBER_ID}/calls/hang-up

`Body`

https://github.com/positusapps/quick-docs/blob/39cf01e44af4c535ea53cdadc293bc96beb155f1/calling/api-calling/json/calls-hang-up-body.json#L1-L3

`Response`

https://github.com/positusapps/quick-docs/blob/39cf01e44af4c535ea53cdadc293bc96beb155f1/calling/api-calling/json/calls-hang-up-response.json#L1-L3


## Webhooks

#### Eventos de Chamadas

| Tipos de Eventos | Descrição                                                                                                                                              |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| connect          | Este evento é recebido quando uma chamada é iniciada por um usuário no WhatsApp. O webhook contém o call_id, direção da chamada, e dados de sessão (SDP).         |
| pre_accept       | Este evento não gera webhook, mas corresponde à ação tomada pela empresa ao pré-aceitar uma chamada recebida usando a API.                                        |
| accept           | Este evento não gera webhook, mas corresponde à ação da empresa de aceitar a chamada. Pode ser usado após o pre_accept.                                           |
| reject           | Este evento não gera webhook, mas indica que a chamada foi rejeitada pela empresa utilizando a API.                                                               |
| terminate        | Este evento é recebido quando a chamada é encerrada (pelo usuário, empresa, ou devido a timeout). O webhook inclui o call_id, status final, duração e timestamps. |

A estrutura dos webhooks relacionados a chamadas é a seguinte:

### connect
https://github.com/positusapps/quick-docs/blob/39cf01e44af4c535ea53cdadc293bc96beb155f1/calling/api-calling/webhooks/connect-webhook.json#L1-L19

### terminate
https://github.com/positusapps/quick-docs/blob/39cf01e44af4c535ea53cdadc293bc96beb155f1/calling/api-calling/webhooks/terminate-webhook.json#L1-L16

## Precisa de ajuda?
Se sua dúvida não foi respondida ou algum conteúdo está faltando, abra uma [issue no GitHub](https://github.com/positusapps/quick-docs/issues) ou um [ticket no suporte](https://studio.posit.us/suporte).