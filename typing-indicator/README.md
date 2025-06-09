# Indicador de Digitação no WhatsApp (Typing Indicator)

Com a API de Typing Indicator do WhatsApp, sua empresa pode informar ao usuário final que uma resposta está sendo preparada, proporcionando uma experiência mais fluida e transparente durante o atendimento.

## Funcionamento

Quando o **Typing Indicator** é ativado, o WhatsApp mostra ao usuário final que o sistema está digitando. Isso ocorre **antes** da resposta ser enviada e é especialmente útil em situações em que o processamento da resposta pode levar alguns segundos.

- O indicador de digitação desaparece automaticamente após **25 segundos** ou assim que a mensagem for enviada.
- Deve ser utilizado **somente quando houver uma resposta sendo preparada**.

## Limitações

- Não deve ser utilizado caso nenhuma resposta esteja sendo gerada.
- Enviar múltiplos indicadores antes de uma única mensagem pode causar comportamentos inesperados.
- O envio incorreto (sem `message_id`, por exemplo) resultará em erro da API.

### Envio do Indicador de Digitação (Typing Indicator)

Para enviar o Typing Indicator, utilize o seguinte endpoint:

#### (POST) https://api.positus.global/v2/whatsapp/numbers/{NUMBER_ID}/messages/typing-indicator

`Body`

https://github.com/positusapps/quick-docs/blob/5fe5c8599b225a119375a11f9c400c7b2fe77511/typing-indicator/json/typing-indicator-body.json#L1-L3

`Response`

https://github.com/positusapps/quick-docs/blob/5fe5c8599b225a119375a11f9c400c7b2fe77511/typing-indicator/json/typing-indicator-response.json#L1-L3
