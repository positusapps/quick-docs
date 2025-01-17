# Mensagens

## Modelos de mensagem

- [Introdução](#introdução)
- [Funcionalidades específicas](#funcionalidades-específicas)
  - [Botão de chamadas do WhatsApp](#enviar-modelo-de-mensagem-com-botão-de-chamadas-do-whatsapp)

### Introdução

Os modelos de mensagens do WhatsApp são formatos de mensagens específicos que as empresas usam para enviar notificações ou mensagens de atendimento ao cliente para pessoas que optaram por receber notificações. As mensagens podem incluir lembretes de compromissos, informações de envio, resolução de problemas ou atualizações de pagamento.

## Funcionalidades específicas

### Enviar modelo de mensagem com botão de chamadas do WhatsApp

| Parameter | Type | Description |
| --- | --- | --- |
| type | String | Define o tipo do parâmetro. |
| ttl_minutes | Integer | - O tempo de vida do botão CTA é em minutos. Após esse tempo expirar, o botão não pode ser usado para iniciar uma chamada para a empresa.<br>- O valor esperado é um valor inteiro entre 1 e 43200 (30 dias).<br>- O valor padrão é 10080 (7 dias). |

https://github.com/positusapps/quick-docs/blob/2e0aa95af69f67ecde90dfa65af0d61de04b1009/messages/message-template/json/template-call-button-body.json#L1-L25

> [!WARNING]
> Enviar esta mensagem para usuários em versões mais antigas do aplicativo resultará em um erro no webhook com código de erro [131026](https://developers.facebook.com/docs/whatsapp/cloud-api/support/error-codes).

## Precisa de ajuda?

Caso a sua dúvida não tenha sido respondida ou você acha que algum conteúdo importante está faltando nesta documentação, sinta-se livre para abrir uma [issue](https://github.com/positusapps/quick-docs/issues) ou [abra um ticket](https://studio.posit.us/suporte) no nosso suporte.