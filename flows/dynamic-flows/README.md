# WhatsApp Flows

## Flows dinâmicos

### Endpoint

Qualquer `Flow` que seja do tipo dinâmico precisa ter um `endpoint` configurado durante a sua criação para que possa efetuar trocas de dados entre as telas, além da troca de dados, o `endpoint` também é responsável por gerenciar qual será a próxima tela do fluxo.

> O `endpoint` precisa estar sempre ativo e respondendo, caso o `endpoint` apresente problemas o `Flow` pode sofrer bloqueios por parte do WhatsApp, saiba mais na sessão que fala sobre [throttle](#throttle)

### Webhook

O webhook do número que enviou o `Flow` será chamado apenas após o `Flow` ser preenchido e enviado pelo usuário em uma tela que possui a propriedade `terminal: true`.

Exemplo de webhook a ser preenchido após o envio pelo usuário:

```json
{
  "contacts": [
    {
      "profile": {
        "name": "Felipe Carvalho"
      },
      "wa_id": "5511999999999"
    }
  ],
  "messages": [
    {
      "context": {
        "from": "5511988888888",
        "id": "wamid.HBgMNTU0Mzk2NDE2NTkwFQIAERgSRTc2QkUxMzk4MzEyMDM1OEU1AA=="
      },
      "from": "5511999999999",
      "id": "wamid.HBgMNTU0Mzk2NDE2NTkwFQIAEhgUM0E4Njg5RkE1NzVGNjA4Mzg0NjEA",
      "timestamp": "1721069262",
      "type": "interactive",
      "interactive": {
        "type": "nfm_reply",
        "nfm_reply": {
          "response_json": "{\"flow_token\":\"flow-token\",\"source\":\"0\",\"lastName\":\"Carvalho\",\"email\":\"felipe.carv@gmail.com\",\"firstName\":\"Felipe\"}",
          "body": "Sent",
          "name": "flow"
        }
      }
    }
  ]
}
```

> Este webhook pertence a um de nossos `Flows` de exemplo, você pode acessar o `Flow` de exemplo ao qual este webhook pertence [clicando aqui](../samples/course-registration/README.md).

### Saúde do endpoint

#### Throttle

> Sessão indisponível

## Precisa de ajuda?

Caso a sua dúvida não tenha sido respondida ou você acha que algum conteúdo importante está faltando nesta documentação, sinta-se livre para abrir uma [issue](https://github.com/positusapps/quick-docs/issues) ou [abra um ticket](https://studio.posit.us/suporte) no nosso suporte.
