# WhatsApp Templates

## Webhook do Workspace

- [Introdução](#introdução)
- [Eventos](#eventos)
  - [Eventos de Templates](#eventos-de-templates)
  - [Eventos de Números](#eventos-de-números)
  - [Eventos de Workspaces](#eventos-de-workspaces)

### Introdução

Os webhooks do workspace são de extrema importância para receber eventos sobre a qualidade dos números e dos templates, além de eventos sobre alteração de status da conta.

É necessário [configurar um webhook no workspace](https://studio.posit.us/workspace/configuracoes) para receber as atualizações em tempo real.

### Eventos

#### Eventos de Templates

| Event Type | Description |
| --- | --- |
| message_template_created | Este evento é recebido quando um novo template é criado |
| message_template_category_update | Este evento é recebido quando a categoria de um template é alterada pela Meta |
| message_template_quality_update | Este evento é recebido quando a qualidade de um template muda |
| message_template_status_update | Este evento é recebido quando o status do template muda |
| message_template_deleted | Este evento é recebido quando um template é deletado |
| message_template_sync | Este evento é recebido quando o sistema da Positus força uma sincronização com a Meta |

A estrutura dos webhooks recebidos é a seguinte:

```json
{
    "event": "message_template_sync",
    "workspace": {
        "id": "d4156ecf-f7cf-438b-b44e-8c4d8805c57d",
        "name": "Positus",
        "business_id": "112223522534868",
        "waba_id": "1235395715662892"
    },
    "template": {
        "id": "e180bg54-ef94-4da2-9349-66422e380c1d",
        "status": {
            "id": 2,
            "code": "APPROVED",
            "description": "Aprovado"
        },
        "quality_score": {
            "id": 0,
            "code": "UNKNOWN"
        },
        "category": {
            "id": 15,
            "code": "UTILITY",
            "description": "Serviços"
        },
        "language": {
            "id": 46,
            "code": "pt_BR",
            "name": "Portuguese (BR)"
        },
        "name": "sample_movie_ticket_confirmation",
        "components": [
            {
                "type": "HEADER",
                "format": "IMAGE"
            },
            {
                "type": "BODY",
                "text": "Seu ingresso para *{{1}}*\n*Horário* - {{2}}\n*Local* - {{3}}\n*Assentos* - {{4}}"
            },
            {
                "type": "FOOTER",
                "text": "Esta mensagem é de uma empresa não verificada."
            }
        ],
        "header_file": null,
        "carousel_files": []
    }
}
```

#### Eventos de Números

| Event Type | Description |
| --- | --- |
| message_template_created | Este evento é recebido quando um novo template é criado |
| message_template_category_update | Este evento é recebido quando a categoria de um template é alterada pela Meta |
| message_template_quality_update | Este evento é recebido quando a qualidade de um template muda |
| message_template_status_update | Este evento é recebido quando o status do template muda |
| message_template_deleted | Este evento é recebido quando um template é deletado |
| message_template_sync | Este evento é recebido quando o sistema da Positus força uma sincronização com a Meta |

A estrutura dos webhooks recebidos é a seguinte:

```json
{
    "event": "message_template_sync",
    "workspace": {
        "id": "d4156ecf-f7cf-438b-b44e-8c4d8805c57d",
        "name": "Positus",
        "business_id": "112223522534868",
        "waba_id": "1235395715662892"
    },
    "template": {
        "id": "e180bg54-ef94-4da2-9349-66422e380c1d",
        "status": {
            "id": 2,
            "code": "APPROVED",
            "description": "Aprovado"
        },
        "quality_score": {
            "id": 0,
            "code": "UNKNOWN"
        },
        "category": {
            "id": 15,
            "code": "UTILITY",
            "description": "Serviços"
        },
        "language": {
            "id": 46,
            "code": "pt_BR",
            "name": "Portuguese (BR)"
        },
        "name": "sample_movie_ticket_confirmation",
        "components": [
            {
                "type": "HEADER",
                "format": "IMAGE"
            },
            {
                "type": "BODY",
                "text": "Seu ingresso para *{{1}}*\n*Horário* - {{2}}\n*Local* - {{3}}\n*Assentos* - {{4}}"
            },
            {
                "type": "FOOTER",
                "text": "Esta mensagem é de uma empresa não verificada."
            }
        ],
        "header_file": null,
        "carousel_files": []
    }
}
```

#### Eventos de Workspaces

| Event Type | Description |
| --- | --- |
| message_template_created | Este evento é recebido quando um novo template é criado |
| message_template_category_update | Este evento é recebido quando a categoria de um template é alterada pela Meta |
| message_template_quality_update | Este evento é recebido quando a qualidade de um template muda |
| message_template_status_update | Este evento é recebido quando o status do template muda |
| message_template_deleted | Este evento é recebido quando um template é deletado |
| message_template_sync | Este evento é recebido quando o sistema da Positus força uma sincronização com a Meta |

A estrutura dos webhooks recebidos é a seguinte:

https://github.com/positusapps/quick-docs/blob/3f5372cb47da777afd19b0f9bae34b66f24490b4/webhooks/workspace-webhook/json/template-webhook.json#L1-L48

## Precisa de ajuda?

Caso a sua dúvida não tenha sido respondida ou você acha que algum conteúdo importante está faltando nesta documentação, sinta-se livre para abrir uma [issue](https://github.com/positusapps/quick-docs/issues) ou [abra um ticket](https://studio.posit.us/suporte) no nosso suporte.