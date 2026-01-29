# Sync

## Contatos

- [Introdução](#introdução)
- [Sincronização](#sincronização)
- [Evento Webhook](#evento-webhook)

### Introdução

Sincronize os contatos do seu número de whatsapp com o Coex da META


### Sincronização

Endpoint utilizado para sincronizar os contatos:

### (POST) https://api.positus.global/v2/whatsapp/numbers/{NUMBER_ID}/onboarding-smb-app/sync-contacts

## Evento Webhook

Ao iniciar a sincronização, você receberá eventos de webhook informando sobre o status da sincronização dos contatos.

### Evento: `smb_app_state_sync`

Este evento é disparado quando há uma atualização no estado da sincronização dos contatos do aplicativo SMB.

#### Exemplo de Payload

`Payload`

https://github.com/positusapps/quick-docs/blob/33d0daf2e05a27e78c9f6cf7298fc3ee397855f7/coex/sync/contacts/json/payload.json#L1-L34


## Precisa de ajuda?

Caso a sua dúvida não tenha sido respondida ou você acha que algum conteúdo importante está faltando nesta documentação, sinta-se livre para abrir uma [issue](https://github.com/positusapps/quick-docs/issues) ou [abra um ticket](https://studio.posit.us/suporte) no nosso suporte.