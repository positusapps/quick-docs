# Análises de Templates (template_analytics)

- [Introdução](#introdução)
- [Funcionalidades específicas](#funcionalidades-específicas)

### Introdução

A análise de templates oferece insights detalhados sobre o desempenho e os custos dos templates de mensagem, incluindo:

- Envio, entrega e leitura: Quantidade de vezes que o template foi enviado, entregue e lido.

- Interações com botões: Número de cliques em botões de URL e Resposta Rápida dentro do template.

- Outros indicadores importantes para otimizar o uso e a eficácia das mensagens.

### 📅 Granularidade dos Dados
Os dados são fornecidos diariamente no fuso horário UTC, com um período de retrospectiva de 90 dias.

### ⚠️ Limitações
- Apenas para API On-Premises: Disponível apenas se a conta não tiver optado pela análise de modelos da Cloud API.

- Limite Mínimo de Eventos: Um mínimo de 1.000 eventos é necessário antes que os dados sejam exibidos, devido a políticas de agregação e anonimização.

- Análise de Cliques em Botões: Disponível somente para modelos categorizados como MARKETING ou UTILITY.

- Restrições Regionais: Não disponível para WABAs pertencentes ou compartilhados com Contas Comerciais Meta na UE, Reino Unido ou Japão, ou com um número de telefone comercial registrado nessas regiões.


## Funcionalidades específicas

#### Aqui estão os parâmetros de análise de template que você pode usar ao consultar a análise da conta comercial.
#### Esses parâmetros ajudam a refinar os dados com base em critérios específicos:

`Parameters`

| Parameter | Type             | Description                                                                                                 |
|-----------|------------------|-------------------------------------------------------------------------------------------------------------|
| start     | UNIX Timestamp   | (obrigatório) A data de início do intervalo de dados. <br/>ex.: 1738368000                                  |
| end       | UNIX Timestamp   | (obrigatório) A data de término do intervalo de dados. <br/>ex.: 1742833145                                 |
| granularity       | String           | (obrigatório)  O intervalo de tempo com a qual você deseja a análise. <br/>Valores possíveis: (DAILY).      |
| template_ids       | Array  | (obrigatório) Lista de IDs dos templates a serem analisados.                                                |
| metric_types       | Array            | (opcional) Tipos de métricas a serem coletadas. <br/>Valores possíveis: (clicked, delivered, read ou sent). |

## Listando (get)

Endpoint utilizado para listar a análise de templates:

##### (GET) https://api.positus.global/v2/workspaces/{WORKSPACE_UUID}/analytics?type=template_analytics

`Response`

https://github.com/positusapps/quick-docs/blob/main/template-analytics/json/template-call-response.json#L1-L68

## Precisa de ajuda?

Caso a sua dúvida não tenha sido respondida ou você acha que algum conteúdo importante está faltando nesta documentação, sinta-se livre para abrir uma [issue](https://github.com/positusapps/quick-docs/issues) ou [abra um ticket](https://studio.posit.us/suporte) no nosso suporte.