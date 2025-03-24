# Análises de Preços (price_analytics)

- [Introdução](#introdução)
- [Funcionalidades específicas](#funcionalidades-específicas)

### Introdução
A análise de preços fornece um detalhamento detalhado dos custos para todas as mensagens entregues dentro de um intervalo de datas especificado.

Ajuda a acompanhar a distribuição de custos e otimizar os gastos com mensagens.

- Importante: A análise de preços fica disponível assim que a precificação por mensagem for aplicada ao seu grupo de implementação. Para mais detalhes, consulte [Atualizações de Preços](https://developers.facebook.com/docs/whatsapp/pricing/updates-to-pricing?locale=en_US)(Julho 1, 2025).

### 📅 Granularidade dos Dados
Os dados são fornecidos diariamente no fuso horário UTC, com um período de retrospectiva de 90 dias.

## Funcionalidades específicas

#### Aqui estão os parâmetros de análise de preços que você pode usar ao consultar a análise da conta comercial.
#### Esses parâmetros ajudam a refinar os dados com base em critérios específicos:

`Parameters`

| Parameter | Type             | Description                                                                                                   |
|-----------|------------------|---------------------------------------------------------------------------------------------------------------|
| start     | UNIX Timestamp   | (obrigatório) A data de início do intervalo de dados. <br/>ex.: 1738368000                                    |
| end       | UNIX Timestamp   | (obrigatório) A data de término do intervalo de dados. <br/>ex.: 1742833145                                   |
| granularity       | String           | (obrigatório)   O intervalo de tempo com a qual você deseja a análise. <br/>Valores possíveis: (half_hour, daily, monthly)                       |
| metric_types       | Array            | (opcional) Tipos de métricas a serem coletadas. <br/>Valores possíveis: (clicked, delivered, read, sent).     |
| pricing_categories       | Array            | (opcional) Categorias de precificação. <br/>Valores possíveis: (authentication, marketing, service, utility). |
| phone_numbers       | Array            | (opcional) Filtra a análise por um ou mais número de telefone.                                                |
| country_codes       | Array            | (opcional) Filtra os resultados pelo código do país. <br/>ex.: ["US", "BR"].                                         |

## Listando (get)
Endpoint utilizado para listar a análise de preços:

##### (GET) https://api.positus.global/v2/workspaces/{WORKSPACE_UUID}/analytics?type=pricing_analytics

`Response`

https://github.com/positusapps/quick-docs/blob/main/analytics/pricing-analytics/json/template-call-response.json#L1-L47

## Precisa de ajuda?

Caso a sua dúvida não tenha sido respondida ou você acha que algum conteúdo importante está faltando nesta documentação, sinta-se livre para abrir uma [issue](https://github.com/positusapps/quick-docs/issues) ou [abra um ticket](https://studio.posit.us/suporte) no nosso suporte.