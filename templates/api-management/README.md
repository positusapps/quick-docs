# WhatsApp Templates

## API de gerenciamento da Positus

- [Atributos](#atributos)
- [Referência da API](#referência-da-api)
  - [Listando todos os templates](#listando-todos-os-templates)
  - [Exibindo um único template](#exibindo-um-único-template)
  - [Criando um template](#considerações-para-criar-um-template)
    - [Considerações para criar um template](#considerações-para-criar-um-template)
    - [Criando um template simples](#criando-um-template-simples)
    - [Criando um template com arquivos no header](#criando-um-template-com-arquivos-no-header)
    - [Criando um template do tipo carrossel](#criando-um-template-do-tipo-carrossel)
    - [Criando um template do tipo autenticação](#criando-um-template-do-tipo-autenticação)
  - [Deletando um template](#deletando-um-template)
- [Webhooks](#webhooks)

### Atributos

#### Status

Define o status do template.

| Id | Description | Code | Type |
| --- | --- | --- | --- |
| 0 | Indefinido | `UNDEFINED` | |
| 1 | Pendente | `PENDING` | |
| 2 | Aprovado | `APPROVED` | |
| 3 | Rejeitado | `REJECTED` | |
| 4 | Em recurso | `IN_APPEAL` | |
| 5 | Exclusão pendente | `PENDING_DELETION` | |
| 6 | Excluído | `DELETED` | |
| 7 | Desabilitado | `DISABLED` | |
| 8 | Sinalizado | `FLAGGED` | |
| 9 | Reinstalado | `REINSTATED` | |
| 10 | Pausado - 3 horas | `PAUSED` | `FIRST_PAUSE` |
| 11 | Pausado - 6 horas | `PAUSED` | `SECOND_PAUSE` |

#### Quality Score

Define a qualidade to template.

| Id | Code |
| --- | --- |
| 0 | UNKNOWN |
| 1 | GREEN |
| 2 | YELLOW |
| 3 | RED |

#### Category

Define a categoria do template.

| Id | Description | Code | Status |
| --- | --- | --- | --- |
| 0 | Indefinido | `UNDEFINED` | `not allowed` |
| 1 | Atualização da conta | `ACCOUNT_UPDATE` | `deprecated` |
| 2 | Atualização de pagamento | `PAYMENT_UPDATE` | `deprecated` |
| 3 | Atualização de finanças pessoais | `PERSONAL_FINANCE_UPDATE` | `deprecated` |
| 4 | Atualização de envio | `SHIPPING_UPDATE` | `deprecated` |
| 5 | Atualização de reserva | `RESERVATION_UPDATE` | `deprecated` |
| 6 | Resolução de problemas | `ISSUE_RESOLUTION` | `deprecated` |
| 7 | Atualização de compromisso | `APPOINTMENT_UPDATE` | `deprecated` |
| 8 | Atualização de transporte | `TRANSPORTATION_UPDATE` | `deprecated` |
| 9 | Atualização de suporte | `TICKET_UPDATE` | `deprecated` |
| 10 | Atualização de alerta | `ALERT_UPDATE` | `deprecated` |
| 11 | Resposta automática | `AUTO_REPLY` | `deprecated` |
| 12 | Transacional | `TRANSACTIONAL` | `deprecated` |
| 13 | Marketing | `MARKETING` | `allowed` |
| 14 | Senhas descartáveis | `OTP` | `deprecated` |
| 15 | Serviços | `UTILITY` | `allowed` |
| 16 | Autenticação | `AUTHENTICATION` | `allowed` |

#### Display Format

Define se um template é do tipo `detalhe do pedido`.

> [!NOTE]
> Só é permitida a utilização desta propriedade caso o `Waba` relacionado ao `Workspace` possua permissão de enviar mensagens do tipo `order`.

| Id | Description | Code | Status |
| --- | --- | --- | --- |
| 0 | Desconhecido | UNKNOWN | `not allowed` |
| 1 | Detalhes do pedido | ORDER_DETAILS | `allowed` |

#### Sub Category

Define se um template é do tipo `status do pedido`.

> [!NOTE]
> Só é permitida a utilização desta propriedade caso o `Waba` relacionado ao `Workspace` possua permissão de enviar mensagens do tipo `order`.

| Id | Description | Code | Status |
| --- | --- | --- | --- |
| 0 | Desconhecido | UNKNOWN | `not allowed` |
| 1 | Status do pedido | ORDER_STATUS | `allowed` |

#### Languages

Define o idioma do template.

| Id | Name | Code | Status |
| --- | --- | --- | --- |
| 0 | Undefined | ? | `not allowed` |
| 1 | Afrikaans | af | `allowed` |
| 2 | Albanian | sq | `allowed` |
| 3 | Arabic | ar | `allowed` |
| 4 | Azerbaijani | az | `allowed` |
| 5 | Bengali | bn | `allowed` |
| 6 | Bulgarian | bg | `allowed` |
| 7 | Catalan | ca | `allowed` |
| 8 | Chinese (CHN) | zh_CN | `allowed` |
| 9 | Chinese (HKG) | zh_HK | `allowed` |
| 10 | Chinese (TAI) | zh_TW | `allowed` |
| 11 | Croatian | hr | `allowed` |
| 12 | Czech | cs | `allowed` |
| 13 | Danish | da | `allowed` |
| 14 | Dutch | nl | `allowed` |
| 15 | English | en | `allowed` |
| 16 | English (UK) | en_GB | `allowed` |
| 17 | English (US) | en_US | `allowed` |
| 18 | Estonian | et | `allowed` |
| 19 | Filipino | fil | `allowed` |
| 20 | Finnish | fi | `allowed` |
| 21 | French | fr | `allowed` |
| 22 | German | de | `allowed` |
| 23 | Greek | el | `allowed` |
| 24 | Gujarati | gu | `allowed` |
| 25 | Hausa | ha | `allowed` |
| 26 | Hebrew | he | `allowed` |
| 27 | Hindi | hi | `allowed` |
| 28 | Hungarian | hu | `allowed` |
| 29 | Indonesian | id | `allowed` |
| 30 | Irish | ga | `allowed` |
| 31 | Italian | it | `allowed` |
| 32 | Japanese | ja | `allowed` |
| 33 | Kannada | kn | `allowed` |
| 34 | Kazakh | kk | `allowed` |
| 35 | Korean | ko | `allowed` |
| 36 | Lao | lo | `allowed` |
| 37 | Latvian | lv | `allowed` |
| 38 | Lithuanian | lt | `allowed` |
| 39 | Macedonian | mk | `allowed` |
| 40 | Malay | ms | `allowed` |
| 41 | Malayalam | ml | `allowed` |
| 42 | Marathi | mr | `allowed` |
| 43 | Norwegian | nb | `allowed` |
| 44 | Persian | fa | `allowed` |
| 45 | Polish | pl | `allowed` |
| 46 | Portuguese (BR) | pt_BR | `allowed` |
| 47 | Portuguese (POR) | pt_PT | `allowed` |
| 48 | Punjabi | pa | `allowed` |
| 49 | Romanian | ro | `allowed` |
| 50 | Russian | ru | `allowed` |
| 51 | Serbian | sr | `allowed` |
| 52 | Slovak | sk | `allowed` |
| 53 | Slovenian | sl | `allowed` |
| 54 | Spanish | es | `allowed` |
| 55 | Spanish (ARG) | es_AR | `allowed` |
| 56 | Spanish (SPA) | es_ES | `allowed` |
| 57 | Spanish (MEX) | es_MX | `allowed` |
| 58 | Swahili | sw | `allowed` |
| 59 | Swedish | sv | `allowed` |
| 60 | Tamil | ta | `allowed` |
| 61 | Telugu | te | `allowed` |
| 62 | Thai | th | `allowed` |
| 63 | Turkish | tr | `allowed` |
| 64 | Ukrainian | uk | `allowed` |
| 65 | Urdu | ur | `allowed` |
| 66 | Uzbek | uz | `allowed` |
| 67 | Vietnamese | vi | `allowed` |
| 68 | Zulu | zu | `allowed` |
| 69 | Georgian | ka | `allowed` |
| 70 | Kinyarwanda | rw_RW | `allowed` |
| 71 | Kyrgyz (Kyrgyzstan) | ky_KG | `allowed` |

### Referência da API

- [Listando todos os templates](#listando-todos-os-templates)
- [Exibindo um único template](#exibindo-um-único-template)
- [Criando um template](#considerações-para-criar-um-template)
  - [Considerações para criar um template](#considerações-para-criar-um-template)
  - [Criando um template simples](#criando-um-template-simples)
  - [Criando um template com arquivos no header](#criando-um-template-com-arquivos-no-header)
  - [Criando um template do tipo carrossel](#criando-um-template-do-tipo-carrossel)
  - [Criando um template do tipo autenticação](#criando-um-template-do-tipo-autenticação)
- [Deletando um template](#deletando-um-template)

#### Listando todos os templates

Endpoint utilizado para listar todos os templates de um workspace:

##### (GET) https://api.positus.global/v2/workspaces/{WORKSPACE_ID}/message-templates

`Response`

https://github.com/positusapps/quick-docs/blob/6df4c55cda1ab46026f913264a646c9867b77bde/templates/api-management/json/templates-list.json#L1-L46

#### Exibindo um único template

Endpoint utilizado para exibir um template específico de um workspace:

##### (GET) https://api.positus.global/v2/workspaces/{WORKSPACE_ID}/message-templates/{TEMPLATE_ID}

`Response`

https://github.com/positusapps/quick-docs/blob/e28abe037f7afbf256485a05cbf82a57c3d9daf8/templates/api-management/json/templates-show.json#L1-L44

#### Considerações para criar um template

A propriedade `components` segue o padrão da meta, você pode acompanhar todas as possibilidades de componentes através da própria [documentação da Meta sobre componentes](https://developers.facebook.com/docs/whatsapp/business-management-api/message-templates/components).

Caso seja efetuada a tentativa de criar um template com um nome já existente, será retornado erro, é recomendado verificar se já existe um template com o mesmo nome antes de se criar outro através do seguinte endpoint:

##### (POST) https://api.positus.global/v2/workspaces/{WORKSPACE_ID}/message-templates/validate

`Body`

https://github.com/positusapps/quick-docs/blob/cb2f68223ec1de81b3b6e349f6756e49ab02acb4/templates/api-management/json/templates-validate-body.json#L1-L3

`Response Success`

Se não houver um template cadastrado com o nome informado será retornado:

```sh
Status code 204 - No Content
```

`Response Error`

Se já houver um template cadastrado com o nome informado será retornado:

https://github.com/positusapps/quick-docs/blob/f06c260e191f0f6b6d19191d461fc6a5053c1839/templates/api-management/json/templates-validate-response-error.json#L1-L3

#### Criando um template

Endpoint utilizado para criar um novo template:

##### (POST) https://api.positus.global/v2/workspaces/{WORKSPACE_ID}/message-templates

###### Criando um template simples

Exemplo de criação de um template simples

`Body - FormData`

> Não esqueça de enviar os dados como **FormData**.

https://github.com/positusapps/quick-docs/blob/1f01f2b313948e7b58dfe8d8a45ca1a505f06c0c/templates/api-management/json/template-store-simple-body.json#L1-L18

`Response`

https://github.com/positusapps/quick-docs/blob/1f01f2b313948e7b58dfe8d8a45ca1a505f06c0c/templates/api-management/json/template-store-simple-response.json#L1-L41

###### Criando um template com arquivos no header

Exemplo de criação de um template com arquivos no `header`:

`Body - FormData`

> Não esqueça de enviar os dados como **FormData**.

https://github.com/positusapps/quick-docs/blob/d4a1a16182048fde60f9856fc1cfc92d3fce66a5/templates/api-management/json/template-store-header-file-body.json#L1-L37

`Response`

https://github.com/positusapps/quick-docs/blob/d4a1a16182048fde60f9856fc1cfc92d3fce66a5/templates/api-management/json/template-store-header-file-response.json#L1-L67

###### Criando um template do tipo carrossel

Exemplo de criação de um template do tipo `carrossel`:

`Body - FormData`

> Não esqueça de enviar os dados como **FormData**.

https://github.com/positusapps/quick-docs/blob/793e16d102df12dbb6ebaf365e41d84e429f718f/templates/api-management/json/template-store-carrousel-body.json#L1-L91

`Response`

https://github.com/positusapps/quick-docs/blob/793e16d102df12dbb6ebaf365e41d84e429f718f/templates/api-management/json/template-store-carrousel-response.json#L1-L130

###### Criando um template do tipo autenticação

Exemplo de criação de um template do tipo `autenticação`:

`Body - FormData`

> Não esqueça de enviar os dados como **FormData**

https://github.com/positusapps/quick-docs/blob/d2d8964e694cae265ad91e5a8154f9e7f2ede389/templates/api-management/json/template-store-auth-body.json#L1-L21

`Response`

https://github.com/positusapps/quick-docs/blob/d2d8964e694cae265ad91e5a8154f9e7f2ede389/templates/api-management/json/template-store-auth-response.json#L1-L44

#### Deletando um template

Endpoint utilizado para deletar um template específico de um workspace:

##### (DELETE) https://api.positus.global/v2/workspaces/{WORKSPACE_ID}/message-templates/{TEMPLATE_ID}

`Response`

```sh
Status code 204 - No Content
```

### Webhooks

Para acompanhar as atualizações dos templates, é recomendado que se [configure um webhook no workspace](https://studio.posit.us/workspace/configuracoes) para receber as atualizações sobre os templates em tempo real.

| Event Type | Description |
| --- | --- |
| message_template_created | Este evento é recebido quando um novo template é criado |
| message_template_category_update | Este evento é recebido quando a categoria de um template é alterada pela Meta |
| message_template_quality_update | Este evento é recebido quando a qualidade de um template muda |
| message_template_status_update | Este evento é recebido quando o status do template muda |
| message_template_deleted | Este evento é recebido quando um template é deletado |
| message_template_sync | Este evento é recebido quando o sistema da Positus força uma sincronização com a Meta |

A estrutura dos webhooks recebidos é a seguinte:

https://github.com/positusapps/quick-docs/blob/d2d8964e694cae265ad91e5a8154f9e7f2ede389/templates/api-management/json/template-webhook.json#L1-L48

## Precisa de ajuda?

Caso a sua dúvida não tenha sido respondida ou você acha que algum conteúdo importante está faltando nesta documentação, sinta-se livre para abrir uma [issue](https://github.com/positusapps/quick-docs/issues) ou [abra um ticket](https://studio.posit.us/suporte) no nosso suporte.
