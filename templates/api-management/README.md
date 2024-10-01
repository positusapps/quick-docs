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

```json

```

#### Exibindo um único template

Endpoint utilizado para exibir um template específico de um workspace:

##### (GET) https://api.positus.global/v2/workspaces/{WORKSPACE_ID}/message-templates/{TEMPLATE_ID}

`Response`

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

#### Considerações para criar um template

A propriedade `components` segue o padrão da meta, você pode acompanhar todas as possibilidades de componentes através da própria [documentação da Meta sobre componentes](https://developers.facebook.com/docs/whatsapp/business-management-api/message-templates/components).

Caso seja efetuada a tentativa de criar um template com um nome já existente, será retornado erro, é recomendado verificar se já existe um template com o mesmo nome antes de se criar outro através do seguinte endpoint:

##### (POST) https://api.positus.global/v2/workspaces/{WORKSPACE_ID}/message-templates/validate

`Body`

```json
{
    "name": "Meu primeiro template"
}
```

`Response Success`

Se não houver um template cadastrado com o nome informado será retornado:

```sh
Status code 204 - No Content
```

`Response Error`

Se já houver um template cadastrado com o nome informado será retornado:

```sh
⁠{
    "message": "J\u00e1 existe um template com este nome, insira um nome diferente."
} ⁠
```

#### Criando um template

Endpoint utilizado para criar um novo template:

##### (POST) https://api.positus.global/v2/workspaces/{WORKSPACE_ID}/message-templates

###### Criando um template simples

Exemplo de criação de um template simples

`Body - FormData`

> Não esqueça de enviar os dados como **FormData**.

```json
{
    "name": "Meu primeiro template",
    "category": "UTILITY",
    "language": "pt_BR",
    "components": [
        {
            "type": "BODY",
            "text": "Olá {{1}}, tudo bem, temos uma atualização sobre o seu pedido!",
            "example": {
                "body_text": [
                    [
                        "Gabriel"
                    ]
                ]
            }
        }
    ]
}
```

`Response`

```json
{
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
                            "Gabriel"
                        ]
                    ]
                }
            }
        ],
        "created_at": "2024-10-01T15:06:09.000000Z",
        "updated_at": "2024-10-01T15:06:09.000000Z"
    }
}
```

###### Criando um template com arquivos no header

Exemplo de criação de um template com arquivos no `header`:

`Body - FormData`

> Não esqueça de enviar os dados como **FormData**.

```json
{
    "name": "newsletter mensal",
    "category": "MARKETING",
    "language": "pt_BR",
    "components": [
        {
            "type": "HEADER",
            "format": "IMAGE",
            "example": {
                "header_handle": [
                    "(binary)"
                ]
            }
        },
        {
            "type": "BODY",
            "text": "Olá {{1}}, a nossa newsletter mensal está no ar, clique no botão a baixo agora mesmo.",
            "example": {
                "body_text": [
                    [
                        "Gabriel"
                    ]
                ]
            }
        },
        {
            "type": "BUTTONS",
            "buttons": [
                {
                    "type": "URL",
                    "text": "Acessar newsletter",
                    "url": "https://site.com.br"
                }
            ]
        }
    ]
}
```

`Response`

```json
{
    "data": {
        "id": "bdd3a694-5116-47ed-9175-f5acbe739d79",
        "wa_id": "1725243708311138",
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
        "name": "newsletter_mensal",
        "components": [
            {
                "type": "HEADER",
                "format": "IMAGE",
                "example": {
                    "header_handle": [
                        "4::aW1hZ2UvanBlZw==:ARbsPlnfCjMj35DMsDEsoWgNcr1AYUlGgECyJA9h3Wj9R2dU_c1fk-Z9lX015FkB_A0LES6LVQBnn7QyYF54bgPDyt30anXKCrlH3Se4fV16Ig:e:1728149598:483680386418392:100050396492156:ARbNBHI-fuZNKfddvtY"
                    ]
                }
            },
            {
                "type": "BODY",
                "text": "Ol\u00e1 {{1}}, a nossa newsletter mensal est\u00e1 no ar, clique no bot\u00e3o a baixo agora mesmo.",
                "example": {
                    "body_text": [
                        [
                            "Gabriel"
                        ]
                    ]
                }
            },
            {
                "type": "BUTTONS",
                "buttons": [
                    {
                        "type": "URL",
                        "text": "Acessar newsletter",
                        "url": "https:\/\/site.com.br"
                    }
                ]
            }
        ],
        "header_file": {
            "mime_type": "image\/jpeg",
            "original_name": "Paschoalotto Gupy.jpg",
            "name": "af09984a-fbe5-4bf5-8ee3-8c4e706297ec.jpg",
            "url": "https:\/\/cdn.positus.global\/production\/templates\/a4056ecf-f7cf-418b-b44e-8c1d8808c57d\/af09984a-fbe5-4bf5-8ee3-8c4e706297ec.jpg",
            "size": "161.41 KB"
        },
        "created_at": "2024-10-01T17:33:23.000000Z",
        "updated_at": "2024-10-01T17:33:23.000000Z"
    }
}
```

###### Criando um template do tipo carrossel

Exemplo de criação de um template do tipo `carrossel`:

`Body - FormData`

> Não esqueça de enviar os dados como **FormData**.

```json
{
    "name": "Exemplo template carrossel",
    "category": "MARKETING",
    "language": "pt_BR",
    "components": [
        {
            "type": "BODY",
            "text": "Olá {{1}}, os produtos que você estava de olho acabaram de chegar na nossa loja!",
            "example": {
                "body_text": [
                    [
                        "Gabriel"
                    ]
                ]
            }
        },
        {
            "type": "CAROUSEL",
            "cards": [
                {
                    "components": [
                        {
                            "type": "HEADER",
                            "format": "IMAGE",
                            "example": {
                                "header_handle": [
                                    "(binary)"
                                ]
                            }
                        },
                        {
                            "type": "BODY",
                            "text": "Produto: {{1}}",
                            "example": {
                                "body_text": [
                                    [
                                        "Blusa plush preta"
                                    ]
                                ]
                            }
                        },
                        {
                            "type": "BUTTONS",
                            "buttons": [
                                {
                                    "type": "URL",
                                    "text": "Comprar agora",
                                    "url": "https://loja.com.br"
                                }
                            ]
                        }
                    ]
                },
                {
                    "components": [
                        {
                            "type": "HEADER",
                            "format": "IMAGE",
                            "example": {
                                "header_handle": [
                                    "(binary)"
                                ]
                            }
                        },
                        {
                            "type": "BODY",
                            "text": "Produto: {{1}}",
                            "example": {
                                "body_text": [
                                    [
                                        "Blusa plush verde"
                                    ]
                                ]
                            }
                        },
                        {
                            "type": "BUTTONS",
                            "buttons": [
                                {
                                    "type": "URL",
                                    "text": "Comprar agora",
                                    "url": "https://loja.com.br"
                                }
                            ]
                        }
                    ]
                }
            ]
        }
    ]
}
```

`Response`

```json
{
    "data": {
        "id": "5c0de172-a159-4f67-8318-42c76f99a6ec",
        "wa_id": "1236731587519011",
        "status": {
            "id": 3,
            "code": "REJECTED",
            "description": "Rejeitado"
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
        "name": "exemplo_template_carrossel",
        "components": [
            {
                "type": "BODY",
                "text": "Ol\u00e1 {{1}}, os produtos que voc\u00ea estava de olho acabaram de chegar na nossa loja!",
                "example": {
                    "body_text": [
                        [
                            "Gabriel"
                        ]
                    ]
                }
            },
            {
                "type": "CAROUSEL",
                "cards": [
                    {
                        "components": [
                            {
                                "type": "HEADER",
                                "format": "IMAGE",
                                "example": {
                                    "header_handle": [
                                        "4::aW1hZ2UvcG5n:ARYmoB1GN1J2OmL26BydRduq3ZDUdRGGftnPobkR2SUEFWj2eJ7X5gVY6Dp1Dx4aX7b0AxxTeGJdPoX-XwrHvtkCOiuY_3uLFn3zFXW7SA-WuA:e:1728149115:483680386418392:100050396492156:ARaLBVKzrCud9sL5Xvc\n4::aW1hZ2UvcG5n:ARYwcpq9tk3dQpsSCa-UJzBX7zoTTEO37PdA8r74T0qJhDkDCNYZF1Qapi1qCgC9Cev2aE5PI6UH9snGGTILm5qAx0pTZ22psF4muraPwxmsvA:e:1728149115:483680386418392:100050396492156:ARaLBslBE2gAE1cWqDU\n4::aW1hZ2UvcG5n:ARZ9bPLnJXfizt5VtQ6W5pKTLJE7NS06oTLm9rSJ9203pWWSpj2eMEWUirCC8vFgloar9daT_Bt26qe-Gj_k4yhoCcCHKMkz0Mpnk-bgrbqcrw:e:1728149115:483680386418392:100050396492156:ARZOFZPad6lOjDvkqBQ"
                                    ]
                                }
                            },
                            {
                                "type": "BODY",
                                "text": "Produto: {{1}}",
                                "example": {
                                    "body_text": [
                                        [
                                            "Blusa plush preta"
                                        ]
                                    ]
                                }
                            },
                            {
                                "type": "BUTTONS",
                                "buttons": [
                                    {
                                        "type": "URL",
                                        "text": "Comprar agora",
                                        "url": "https:\/\/loja.com.br"
                                    }
                                ]
                            }
                        ]
                    },
                    {
                        "components": [
                            {
                                "type": "HEADER",
                                "format": "IMAGE",
                                "example": {
                                    "header_handle": [
                                        "4::aW1hZ2UvcG5n:ARaW2WfFaZpNS4gY-5DVZnoRnRp6lziJ7_41vIHpwNAGggieS7VxMZnepx_2ierS6loFpAsR6pNfaLJhHUK__w_WPdOgtRUY158tjQENJ0WiLg:e:1728149116:483680386418392:100050396492156:ARbovWbbmoDxgUJN1W4\n4::aW1hZ2UvcG5n:ARaD3e1Ndh_ZHrdu_yfIglekeRs_HTev_IU8LGpHHvmOAN6cLAX8e2w_DxlaiKCz4O7r4iP-Ue0m9bTG_cWDIASlZltwd8FJiyvc8XSXrgrocA:e:1728149117:483680386418392:100050396492156:ARaKwBPQFfcfrhzt9kU\n4::aW1hZ2UvcG5n:ARbkOUVAZ_Em2COJzc-2q-ErzwjgGrkx0q6liTqprak1kJdT2CbNbYZBIcKAfX9M-BQYUIllTTtuooELPwC_SRolP_pULASKc_Fo1Ln8gCRhgA:e:1728149116:483680386418392:100050396492156:ARbKEe_FPU2-86jqS_E"
                                    ]
                                }
                            },
                            {
                                "type": "BODY",
                                "text": "Produto: {{1}}",
                                "example": {
                                    "body_text": [
                                        [
                                            "Blusa plush verde"
                                        ]
                                    ]
                                }
                            },
                            {
                                "type": "BUTTONS",
                                "buttons": [
                                    {
                                        "type": "URL",
                                        "text": "Comprar agora",
                                        "url": "https:\/\/loja.com.br"
                                    }
                                ]
                            }
                        ]
                    }
                ]
            }
        ],
        "carousel_files": [
            {
                "mime_type": "image\/png",
                "original_name": "01.png",
                "name": "7f2e87f7-808f-4287-82df-8d239e8268f4.png",
                "url": "https:\/\/cdn.positus.global\/production\/templates\/a4056ecf-f7cf-418b-b44e-8c1d8808c57d\/7f2e87f7-808f-4287-82df-8d239e8268f4.png",
                "size": "2.54 MB"
            },
            {
                "mime_type": "image\/png",
                "original_name": "02.png",
                "name": "7c19aece-a33c-4b65-acee-11f446e0d1a0.png",
                "url": "https:\/\/cdn.positus.global\/production\/templates\/a4056ecf-f7cf-418b-b44e-8c1d8808c57d\/7c19aece-a33c-4b65-acee-11f446e0d1a0.png",
                "size": "2.52 MB"
            }
        ],
        "created_at": "2024-10-01T17:25:23.000000Z",
        "updated_at": "2024-10-01T17:25:23.000000Z"
    }
}
```

###### Criando um template do tipo autenticação

Exemplo de criação de um template do tipo `autenticação`:

`Body - FormData`

> Não esqueça de enviar os dados como **FormData**

```json
{
    "name": "Exemplo template autenticação",
    "category": "AUTHENTICATION",
    "language": "pt_BR",
    "components": [
        {
            "type": "BODY",
            "add_security_recommendation": true
        },
        {
            "type": "BUTTONS",
            "buttons": [
                {
                    "type": "OTP",
                    "otp_type": "copy_code",
                    "text": "Copiar código"
                }
            ]
        }
    ]
}
```

`Response`

```json
{
    "data": {
        "id": "0f60c187-4691-4965-9898-f41d799a7946",
        "wa_id": "1224134558828762",
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
            "id": 16,
            "code": "AUTHENTICATION",
            "description": "Autentica\u00e7\u00e3o"
        },
        "language": {
            "id": 46,
            "code": "pt_BR",
            "name": "Portuguese (BR)"
        },
        "name": "Exemplo template autenticação",
        "components": [
            {
                "type": "BODY",
                "add_security_recommendation": "true"
            },
            {
                "type": "BUTTONS",
                "buttons": [
                    {
                        "type": "OTP",
                        "otp_type": "copy_code",
                        "text": "Copiar c\u00f3digo"
                    }
                ]
            }
        ],
        "created_at": "2024-10-01T18:32:29.000000Z",
        "updated_at": "2024-10-01T18:32:29.000000Z"
    }
}
```

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

```json
{
    "event": "message_template_sync",
    "workspace": {
        "id": "d4156ecf-f7cf-438b-b44e-8c4d8805c57d",
        "name": "Positus",
        "business_id": "112223522534868",
        "waba_id": "1235395715662892"
    },
    "template": {
        "id": "e180bg54-ef94-4da2-9349-66422e380c1d",
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
            "description": "Serviços"
        },
        "language": {
            "id": 46,
            "code": "pt_BR",
            "name": "Portuguese (BR)"
        },
        "name": "sample_movie_ticket_confirmation",
        "components": [
            {
                "type": "HEADER",
                "format": "IMAGE"
            },
            {
                "type": "BODY",
                "text": "Seu ingresso para *{{1}}*\n*Horário* - {{2}}\n*Local* - {{3}}\n*Assentos* - {{4}}"
            },
            {
                "type": "FOOTER",
                "text": "Esta mensagem é de uma empresa não verificada."
            }
        ],
        "header_file": null,
        "carousel_files": []
    }
}
```

## Precisa de ajuda?

Caso a sua dúvida não tenha sido respondida ou você acha que algum conteúdo importante está faltando nesta documentação, sinta-se livre para abrir uma [issue](https://github.com/positusapps/quick-docs/issues) ou [abra um ticket](https://studio.posit.us/suporte) no nosso suporte.
