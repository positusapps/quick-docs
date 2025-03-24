# Análises de Conversas (/conversation_analytics)

- [Introdução](#introdução)
- [Funcionalidades específicas](#funcionalidades-específicas)

### Introdução

Fornece informações detalhadas sobre conversas, seus custos e categorias.

## Funcionalidades específicas

#### Aqui estão os parâmetros de análise de mensagens que você pode usar ao consultar a análise da conta comercial.
#### Esses parâmetros ajudam a refinar os dados com base em critérios específicos:

`Parameters`

| Parameter | Type             | Description                                                                                                         |
|-----------|------------------|---------------------------------------------------------------------------------------------------------------------|
| type      | String | (obrigatório) Define o tipo da análise. <br/>ex.: 'conversation_analytics'                                                       |
| granularity       | String           | (obrigatório)  A granularidade com a qual você deseja a análise. <br/>Valores possíveis: (HALF_HOUR, DAY ou MONTH). |
| start     | UNIX Timestamp   | (obrigatório) A data de início do intervalo de dados. <br/>ex.: 1738368000                                          |
| end       | UNIX Timestamp   | (obrigatório) A data de término do intervalo de dados. <br/>ex.: 1742833145                                         |
| metric_types       | Array  | (opcional) Tipos de métricas a serem coletadas. <br/>Valores possíveis: (cost, conversation).                       |
| conversation_categories       | Array            | (opcional) Categorias das conversas. <br/>Valores possíveis: (authentication, marketing, service, utility).         |
| phone_numbers       | Array            | (opcional) Filtra a análise por um ou mais número de telefone.                                                      |

## Listando (get)

Endpoint utilizado para listar a análise de conversas:

##### (GET) https://api.positus.global/v2/admin/workspaces/{WORKSPACE_UUID}/analytics?type=conversation_analytics

`Response`

https://github.com/positusapps/quick-docs/blob/main/analytics/conversation-analytics/json/template-call-response.json#L1-L102

## Precisa de ajuda?

Caso a sua dúvida não tenha sido respondida ou você acha que algum conteúdo importante está faltando nesta documentação, sinta-se livre para abrir uma [issue](https://github.com/positusapps/quick-docs/issues) ou [abra um ticket](https://studio.posit.us/suporte) no nosso suporte.