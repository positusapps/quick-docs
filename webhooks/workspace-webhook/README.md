# WhatsApp Templates

## Webhook do Workspace

- [Introdução](#introdução)
- [Eventos](#eventos)
  - [Eventos de Flows](#eventos-de-flows)
  - [Eventos de Templates](#eventos-de-templates)
  - [Eventos de Números](#eventos-de-números)
  - [Eventos de Ativação de Números](#eventos-de-números)

### Introdução

Os webhooks do workspace são de extrema importância para receber eventos sobre a qualidade dos números e dos templates, além de eventos sobre alteração de status da conta.

É necessário [configurar um webhook no workspace](https://studio.posit.us/workspace/configuracoes) para receber as atualizações em tempo real.

### Eventos

#### Eventos de Flows

| Event Type | Description |
| --- | --- |
| flow_created | Este evento é recebido quando um novo flow é criado |
| flow_updated | Este evento é recebido quando um flow é atualizado |
| flow_published | Este evento é recebido quando um flow é publicado |
| flow_throttled | Este evento é recebido quando um novo flow é restrito |
| flow_deprecated | Este evento é recebido quando um novo flow é descontinuado |
| flow_blocked | Este evento é recebido quando um novo flow é bloqueado |
| flow_deleted | Este evento é recebido quando um novo flow é deletado |
| flow_sync | Este evento é recebido quando o sistema da Positus força uma sincronização com a Meta |

A estrutura dos webhooks recebidos relacionados a flows é a seguinte:

https://github.com/positusapps/quick-docs/blob/dacb80ba35f8f666f31ca44c9b23b9021a743946/webhooks/workspace-webhook/json/flow-webhook.json#L1-L62

#### Eventos de Templates

| Event Type | Description |
| --- | --- |
| message_template_created | Este evento é recebido quando um novo template é criado |
| message_template_category_update | Este evento é recebido quando a categoria de um template é alterada pela Meta |
| message_template_quality_update | Este evento é recebido quando a qualidade de um template muda |
| message_template_status_update | Este evento é recebido quando o status do template muda |
| message_template_deleted | Este evento é recebido quando um template é deletado |
| message_template_sync | Este evento é recebido quando o sistema da Positus força uma sincronização com a Meta |

A estrutura dos webhooks recebidos relacionados a templates é a seguinte:

https://github.com/positusapps/quick-docs/blob/3f5372cb47da777afd19b0f9bae34b66f24490b4/webhooks/workspace-webhook/json/template-webhook.json#L1-L48

#### Eventos de Números

| Event Type | Description |
| --- | --- |
| phone_number_status_update | Este evento é recebido quando os seguintes campos mudam: <br><br> <ul><li>`messaging_limit`</li><li>`quality_status`</li><li>`quality_rating`</li></ul> |
| phone_number_sync | Este evento é recebido quando o sistema da Positus força uma sincronização com a Meta |

A estrutura dos webhooks relacionados a números recebidos é a seguinte:

https://github.com/positusapps/quick-docs/blob/99387492833866c9d8961c706426793704d938f2/webhooks/workspace-webhook/json/phone-number-webhook.json#L1-L34

#### Eventos de Ativação de Números

| Event Type | Description |
| --- | --- |
| number_activation_status_update | Este evento é recebido quando o status de uma ativação de número muda |

A estrutura dos webhooks relacionados a ativação de números recebidos é a seguinte:

https://github.com/positusapps/quick-docs/blob/4cf0a28ec3fadfa1e90dedce08a22be94f286806/webhooks/workspace-webhook/json/number-activation-webhook.json#L1-L30

## Precisa de ajuda?

Caso a sua dúvida não tenha sido respondida ou você acha que algum conteúdo importante está faltando nesta documentação, sinta-se livre para abrir uma [issue](https://github.com/positusapps/quick-docs/issues) ou [abra um ticket](https://studio.posit.us/suporte) no nosso suporte.