# WhatsApp Flows

## Flows dinâmicos

### Endpoints

Qualquer `Flow` que seja do tipo dinâmico precisa ter um `endpoint` configurado durante a sua criação para que possa efetuar trocas de dados entre as telas, além da troca de dados, o `endpoint` também é responsável por gerenciar qual será a próxima tela do fluxo.

> O `endpoint` precisa estar sempre ativo e respondendo, caso o `endpoint` apresente problemas o `Flow` pode sofrer bloqueios por parte do WhatsApp, saiba mais na sessão que fala sobre [throttle](#throttle)

#### Throttle

> Sessão indisponível
