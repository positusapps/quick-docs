# WhatsApp Templates

## API de gerenciamento da Positus

- [Atributos](#atributos)
- [Referência da API](#referência-da-api)
  - [Listando todos os templates](#listando-todos-os-templates)
  - [Exibindo um único template](#exibindo-um-único-template)
  - [Criando um template](#criando-um-template)
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

| Id | Description | Code | Status |
| --- | --- | --- | --- |
| 0 | Desconhecido | UNKNOWN | `not allowed` |
| 1 | Detalhes do pedido | ORDER_DETAILS | `allowed` |

#### Sub Category

Define se um template é do tipo `status do pedido`.

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

#### Listando todos os templates

Endpoint utilizado para listar todos os templates de um workspace:

##### (GET) https://api.positus.global/v2/workspaces/{WORKSPACE_ID}/message-templates

###### Response

```json
{
    "data": [
        {
            "id": "e864d335-50b7-4cc8-a072-b585b68e428a",
            "wa_id": "211647153820823",
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
                "description": "Servi\u00e7os"
            },
            "language": {
                "id": 17,
                "code": "en_US",
                "name": "English (US)"
            },
            "name": "sample_flight_confirmation",
            "components": [
                {
                    "type": "HEADER",
                    "format": "DOCUMENT"
                },
                {
                    "type": "BODY",
                    "text": "This is your flight confirmation for {{1}}-{{2}} on {{3}}."
                },
                {
                    "type": "FOOTER",
                    "text": "This message is from an unverified business."
                }
            ],
            "header_file": null,
            "carousel_files": [],
            "created_at": "2021-08-25T07:21:18.000000Z",
            "updated_at": "2024-10-01T13:14:48.000000Z"
        }
    ]
}
```

#### Exibindo um único template

Endpoint utilizado para exibir um template específico de um workspace:

##### (GET) https://api.positus.global/v2/workspaces/{WORKSPACE_ID}/message-templates/{TEMPLATE_ID}

###### Response

```json
{
    "data": {
        "id": "e864d335-50b7-4cc8-a072-b585b68e428a",
        "wa_id": "211647153820823",
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
            "description": "Servi\u00e7os"
        },
        "language": {
            "id": 17,
            "code": "en_US",
            "name": "English (US)"
        },
        "name": "sample_flight_confirmation",
        "components": [
            {
                "type": "HEADER",
                "format": "DOCUMENT"
            },
            {
                "type": "BODY",
                "text": "This is your flight confirmation for {{1}}-{{2}} on {{3}}."
            },
            {
                "type": "FOOTER",
                "text": "This message is from an unverified business."
            }
        ],
        "header_file": null,
        "carousel_files": [],
        "created_at": "2021-08-25T07:21:18.000000Z",
        "updated_at": "2024-10-01T13:14:48.000000Z"
    }
}
```

#### Criando um template

Endpoint utilizado para criar um novo template:

##### (POST) https://api.positus.global/v2/workspaces/{WORKSPACE_ID}/message-templates

###### Body - FormData

> Não esqueça de enviar os dados como **FormData**.

```json
{
    "name": "Meu primeiro template",
    "category": "MARKETING",
    "language": "pt_BR",
    "components": [
        {
            "type": "BODY",
            "text": "Olá {{1}}, tudo bem, temos uma atualização sobre o seu pedido!",
            "example": {
                "body_text": [
                    [
                        "Caio"
                    ]
                ]
            }
        }
    ]
}
```

###### Response

```json
⁠{
    "data": {
        "id": "a1bb46d6-0ec6-49ad-a7a0-4ed7f0f24b1b",
        "wa_id": "894983259173415",
        "status": {
            "id": 1,
            "code": "PENDING",
            "description": "Pendente"
        },
        "quality_score": {
            "id": 0,
            "code": "UNKNOWN"
        },
        "category": {
            "id": 13,
            "code": "MARKETING",
            "description": "Marketing"
        },
        "language": {
            "id": 46,
            "code": "pt_BR",
            "name": "Portuguese (BR)"
        },
        "name": "testeeeeeeeee",
        "components": [
            {
                "type": "BODY",
                "text": "Ol\u00e1 {{1}}, tudo bem, temos uma atualiza\u00e7\u00e3o sobre o seu pedido!",
                "example": {
                    "body_text": [
                        [
                            "Caio"
                        ]
                    ]
                }
            }
        ],
        "created_at": "2024-10-01T15:06:09.000000Z",
        "updated_at": "2024-10-01T15:06:09.000000Z"
    }
} ⁠
```

> Considerações antes de se criar um template:

Caso seja efetuada a tentativa de criar um template com um nome que já existe, será retornado erro, é recomendado verificar se já existe um template com o mesmo nome através do seguinte endpoint:

##### (POST) https://api.positus.global/v2/workspaces/{WORKSPACE_ID}/message-templates/validate

###### Body

```json
{
    "name": "Meu primeiro template"
}
```

###### Response Success

Se não houver um template cadastrado com o nome informado será retornado:

```sh
Status code 204 - No Content
```

###### Response Error

Se já houver um template cadastrado com o nome informado será retornado:

```sh
⁠{
    "message": "J\u00e1 existe um template com este nome, insira um nome diferente."
} ⁠
```

#### Deletando um template

Endpoint utilizado para deletar um template específico de um workspace:

##### (DELETE) https://api.positus.global/v2/workspaces/{WORKSPACE_ID}/message-templates/{TEMPLATE_ID}

###### Response

```sh
Status code 204 - No Content
```

### Webhooks