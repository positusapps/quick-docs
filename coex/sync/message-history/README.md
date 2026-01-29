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

`Payload`

https://github.com/positusapps/quick-docs/blob/e28abe037f7afbf256485a05cbf82a57c3d9daf8/coex/sync/message-history/json/payload.json#L1-L86

## Precisa de ajuda?

Caso a sua dúvida não tenha sido respondida ou você acha que algum conteúdo importante está faltando nesta documentação, sinta-se livre para abrir uma [issue](https://github.com/positusapps/quick-docs/issues) ou [abra um ticket](https://studio.posit.us/suporte) no nosso suporte.