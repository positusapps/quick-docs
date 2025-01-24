# Bloqueio de Usuários

Com a API de Bloqueio de Usuários, sua empresa impede que indivíduos mal-intencionados entrem em contato.

## Funcionamento

Quando você bloqueia um usuário do WhatsApp, acontece o seguinte:

- O usuário não pode entrar em contato com sua empresa nem ver quando você está online.
- Sua empresa não pode enviar mensagens ao usuário. Caso envie uma mensagem, você receberá um erro.

Erros na API ocorrem de acordo com o número, pois os bloqueios podem funcionar em alguns números e não em outros.

## Limitações

- Você só pode bloquear usuários que enviaram mensagens para sua empresa nas últimas 24 horas.
- O limite da lista de bloqueio é de 64.000 usuários.

Se você deseja acessar a documentação completa da Meta sobre `Bloqueio de usuários`, [clique aqui](https://developers.facebook.com/docs/whatsapp/cloud-api/block-users).

## API de gerenciamento da Positus

- [Listar todos os usuários bloqueados](#listar-todos-os-usuários-bloqueados)
- [Bloquear um usuário](#bloquear-um-usuário)
- [Desbloquear um usuário](#desbloquear-um-usuário)

### Listar todos os usuários bloqueados

Endpoint utilizado para listar todos os usuários bloqueados:

#### (GET) https://api.positus.global/v2/whatsapp/numbers/{NUMBER_ID}/contacts/blocklist

`Params`

| Parâmetro | Description | Tipo | Padrão |
| --- | --- | --- | --- |
| limit | Define o limite de usuários listados por página | Integer | 10 |
| before | Utilizado para definir paginação | String | - |
| after | Utilizado para definir paginação | String | - |

`Response`

https://github.com/positusapps/quick-docs/blob/f69451614d919ea243e9bff2d344134be359acea/user-blocking/json/user-blocking-list-response.json#L1-L14

### Bloquear um usuário

Endpoint utilizado para bloquear um usuário:

#### (POST) https://api.positus.global/v2/whatsapp/numbers/{NUMBER_ID}/contacts/block

`Body`

https://github.com/positusapps/quick-docs/blob/f69451614d919ea243e9bff2d344134be359acea/user-blocking/json/user-blocking-block-body.json#L1-L7

`Response`

https://github.com/positusapps/quick-docs/blob/f69451614d919ea243e9bff2d344134be359acea/user-blocking/json/user-blocking-block-response.json#L1-L12

### Desbloquear um usuário

Endpoint utilizado para desbloquear um usuário:

#### (POST) https://api.positus.global/v2/whatsapp/numbers/{NUMBER_ID}/contacts/unblock

`Body`

https://github.com/positusapps/quick-docs/blob/f69451614d919ea243e9bff2d344134be359acea/user-blocking/json/user-blocking-unblock-body.json#L1-L7

`Response`

https://github.com/positusapps/quick-docs/blob/f69451614d919ea243e9bff2d344134be359acea/user-blocking/json/user-blocking-unblock-response.json#L1-L12

## Precisa de ajuda?

Caso a sua dúvida não tenha sido respondida ou você acha que algum conteúdo importante está faltando nesta documentação, sinta-se livre para abrir uma [issue](https://github.com/positusapps/quick-docs/issues) ou [abra um ticket](https://studio.posit.us/suporte) no nosso suporte.
