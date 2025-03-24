# Análises de Mensagens (/analytics)

- [Introdução](#introdução)
- [Funcionalidades específicas](#funcionalidades-específicas)

### Introdução

Fornece o número e o tipo de mensagens enviadas e entregues pelos números de telefone associados a um WABA específico — para métricas de conversação, consulte [Análise de Conversas](https://github.com/positusapps/quick-docs/tree/main/analytics/conversation-analytics). 

### Métricas disponíveis:
Essas métricas fornecem insights sobre o desempenho das mensagens:

sent – Número total de mensagens enviadas.

delivered – Número de mensagens entregues com sucesso.

read – Número de mensagens lidas pelos destinatários.

failed – Número de mensagens que falharam ao ser enviadas.

received – Total de mensagens recebidas pelo WABA.

template_messages_sent – Número de mensagens de modelo enviadas.


## Funcionalidades específicas

#### Aqui estão os parâmetros de análise de mensagens que você pode usar ao consultar a análise da conta comercial.
#### Esses parâmetros ajudam a refinar os dados com base em critérios específicos:

`Parameters`

| Parameter | Type             | Description                                                                                                          |
|-----------|------------------|----------------------------------------------------------------------------------------------------------------------|
| start     | UNIX Timestamp   | (obrigatório) A data de início do intervalo de dados. <br/>ex.: 1738368000                                              |
| end       | UNIX Timestamp   | (obrigatório) A data de término do intervalo de dados. <br/>ex.: 1742833145                                             |
| granularity       | String           | (obrigatório)  O intervalo de tempo com a qual você deseja a análise. <br/>Valores possíveis: (HALF_HOUR, DAY ou MONTH).     |
| product_types       | Array  | (opcional) Tipos de produtos analisados. <br/>Valores possíveis: (notification_messages, customer_support_messages). |
| phone_numbers       | Array            | (opcional) Filtra a análise por um ou mais número de telefone.                                                       |
| country_codes       | Array            | (opcional) Filtra os resultados pelo código do país. <br/>ex.: ["US", "BR"].                                         |

## Listando (get)

Endpoint utilizado para listar a análise de mensagens:

##### (GET) https://api.positus.global/v2/admin/workspaces/{workspace-uuid}/analytics?type=analytics

`Response`

https://github.com/positusapps/quick-docs/blob/main/analytics/messaging-analytics/json/template-call-response.json#L1-L40

## Precisa de ajuda?

Caso a sua dúvida não tenha sido respondida ou você acha que algum conteúdo importante está faltando nesta documentação, sinta-se livre para abrir uma [issue](https://github.com/positusapps/quick-docs/issues) ou [abra um ticket](https://studio.posit.us/suporte) no nosso suporte.