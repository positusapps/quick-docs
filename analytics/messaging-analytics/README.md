# Análises de Mensagens (/analytics)

- [Introdução](#introdução)
- [Funcionalidades específicas](#funcionalidades-específicas)

### Introdução

Fornece o número e o tipo de mensagens enviadas e entregues pelos números de telefone associados a um WABA específico — para métricas de conversação, consulte Análise de Conversas. Ao chamar /{whatsapp-business-account-ID}?fields=analytics.{filtering-parameters}, você pode anexar os seguintes parâmetros.

## Funcionalidades específicas

#### Aqui estão os parâmetros de análise de mensagens que você pode usar ao consultar a análise da conta comercial.
#### Esses parâmetros ajudam a refinar os dados com base em critérios específicos:

`Parameters`

| Parameter | Type             | Description                                                                                                          |
|-----------|------------------|----------------------------------------------------------------------------------------------------------------------|
| type      | String | (obrigatório) Define o tipo da análise. <br/>ex.: 'analytics'                                                        |
| granularity       | String           | (obrigatório)  A granularidade com a qual você deseja a análise. <br/>Valores possíveis: (HALF_HOUR, DAY ou MONTH).     |
| start     | UNIX Timestamp   | (obrigatório) A data de início do intervalo de dados. <br/>ex.: 1738368000                                              |
| end       | UNIX Timestamp   | (obrigatório) A data de término do intervalo de dados. <br/>ex.: 1742833145                                             |
| product_types       | Array  | (opcional) Tipos de produtos analisados. <br/>Valores possíveis: (notification_messages, customer_support_messages). |
| phone_numbers       | Array            | (opcional) Filtra a análise por um ou mais número de telefone.                                                       |
| country_codes       | Array            | (opcional) Filtra os resultados pelo código do país. <br/>ex.: ["US", "BR"].                                         |

### Métricas disponíveis:
Essas métricas fornecem insights sobre o desempenho das mensagens:

sent – Número total de mensagens enviadas.

delivered – Número de mensagens entregues com sucesso.

read – Número de mensagens lidas pelos destinatários.

failed – Número de mensagens que falharam ao ser enviadas.

received – Total de mensagens recebidas pelo WABA.

template_messages_sent – Número de mensagens de modelo enviadas.

## Listando (get)

Endpoint utilizado para listar a análise de mensagens:

##### (GET) https://api.positus.global/v2/admin/workspaces/{WORKSPACE_UUID}/analytics?type=analytics

`Response`

https://github.com/positusapps/quick-docs/blob/main/analytics/messaging-analytics/json/template-call-response.json#L1-L40

## Precisa de ajuda?

Caso a sua dúvida não tenha sido respondida ou você acha que algum conteúdo importante está faltando nesta documentação, sinta-se livre para abrir uma [issue](https://github.com/positusapps/quick-docs/issues) ou [abra um ticket](https://studio.posit.us/suporte) no nosso suporte.