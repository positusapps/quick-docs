# Sync

## Histórico de mensagens

- [Introdução](#introdução)
- [Sincronização](#sincronização)
- [Evento Webhook](#evento-webhook)

### Introdução

Sincronize os historicos de mensagens do seu número de whatsapp com o Coex da META

### Sincronização

Endpoint utilizado para sincronizar os históricos de mensagens:

### (POST) https://api.positus.global/v2/whatsapp/numbers/{NUMBER_ID}/onboarding-smb-app/sync-message-history

## Evento Webhook

Após solicitar a sincronização do histórico, a Meta enviará eventos de webhook do tipo `history` contendo os lotes de mensagens.

### Evento: `history`

Este evento contém partes do histórico de mensagens sincronizado. A sincronização é dividida em fases e pode conter vários arquivos (chunks).

#### Detalhes do Evento
- **Phases**: A sincronização ocorre em fases (Phase 0: imediata, Phase 1: até 90 dias, Phase 2: até 180 dias).
- **Progress**: Indica a porcentagem total de conclusão (ex: 100 significa concluído).
- **Chunk Order**: A ordem do lote de mensagens atual para remontagem do histórico.

#### Exemplo de Payload

```json
{
  "object": "whatsapp_business_account",
  "entry": [
    {
      "id": "xxxxxxxxxxxxxxxxxxx",
      "changes": [
        {
          "value": {
            "messaging_product": "whatsapp",
            "metadata": {
              "display_phone_number": "xxxxxxxxxxxxxxxxxxx",
              "phone_number_id": "xxxxxxxxxxxxxxxxxxx"
            },
            "history": [
              {
                "metadata": {
                  "phase": 0,
                  "chunk_order": 1,
                  "progress": 55
                },
                "threads": [
                  {
                    "id": "16505551234",
                    "messages": [
                      {
                        "from": "xxxxxxxxxxxxxxxxxxx",
                        "id": "wamid.HBgLMTY0NjcwNDM1OTUVAgARGBIyNDlBOEI5QUQ4NDc0N0FCNjMA",
                        "timestamp": "1739230955",
                        "type": "text",
                        "text": {
                          "body": "mensagem1"
                        },
                        "history_context": {
                          "status": "READ"
                        }
                      },
                      {
                        "from": "xxxxxxxxxxxxxxxxxxx",
                        "id": "wamid.xyz",
                        "timestamp": "1739230970",
                        "type": "media_placeholder",
                        "history_context": {
                          "status": "PLAYED"
                        }
                      },
                    ]
                  },
                  {
                    "id": "xxxxxxxxxxxxxxxxxxx",
                    "messages": [
                      {
                        "from": "xxxxxxxxxxxxxxxxxxx",
                        "id": "wamid.abc",
                        "timestamp": "1739230970",
                        "type": "text",
                        "text": {
                          "body": "mensagem2"
                        },
                        "history_context": {
                          "status": "DELIVERED"
                        }
                      }
                    ]
                  }
                ]
              }
            ]
          },
          "field": "history"
        }
      ]
    }
  ]
}


```

## Precisa de ajuda?

Caso a sua dúvida não tenha sido respondida ou você acha que algum conteúdo importante está faltando nesta documentação, sinta-se livre para abrir uma [issue](https://github.com/positusapps/quick-docs/issues) ou [abra um ticket](https://studio.posit.us/suporte) no nosso suporte.