---
title: API de data de chegada do postback agregado do SKAN
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-12-21T09:03:09Z'
  edited_at: '2026-08-18T00:32:17Z'
  id: 360016646557
  locale: pt
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/pt/articles/360016646557
---
> **Visão geral:** Postbacks agregados do SKAdNetwork via API. Os dados são agregados usando a data de chegada do postback.

## API de data de chegada do postback agregado do SKAN

A API retorna postbacks agregados do SKAdNetwork, usando o intervalo da data de chegada do postback.

**Nota**! A data de chegada do postback é diferente da data de instalação usada no painel e nos relatórios do SKAdNetwork.

<div id="using-skan-aggregated-performance-report-api" />

<Accordion title="Usar a API de data de chegada do postback agregado do SKAN">

**Para usar a API de relatório de desempenho agregado do SKAN**:

1. Obtenha o token da API. Um administrador precisa recuperar o token.
2. Forneça ao seu desenvolvedor o token da API para ser usado no cabeçalho de autenticação.
3. Dê aos seus desenvolvedores os parâmetros para inserir quando fizerem a chamada da API, conforme descrito na seção que se segue. Os parâmetros determinam no que o relatório se foca, como ele é organizado e fornecem um período de tempo para o relatório.
4. Peça ao seu desenvolvedor que siga a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/skan-agg-postback-arrival-date-api-get">API de relatório de desempenho agregado do SKAN</Anchor> no hub do desenvolvedor.

#### Parâmetros

| Nome do parâmetro | Detalhes | Obrigatório |
| --- | --- | --- |
| `start_date` | O intervalo de datas de chegada dos postbacks é delimitado por start\_date e end\_date. Nota! A data de chegada é diferente da data de instalação usada no painel e nos relatórios do SKAdNetwork.<ul><li>AAAA-MM-DD</li><li>Data mais antiga permitida: $2020-11-01<br />Exemplo: `2020-11-05`</li></ul> | Sim |
| `end_date` | <ul><li>AAAA-MM-DD</li><li>Número máximo de dias por chamada de relatório: 60 dias</li><li>Exemplo: `2020-11-12`</li></ul> | Sim |
| `ad_network_name` | Filtrar por fonte de mídia | Não |
| `geo` | Filtrar por código de país usando ISO 3166 (alpha-2). Exemplo: `US`, `CN` | Não |
| `skad_redownload` | Filtrar por `true` ou `false` | Não |
| `skad_source_app_id` | Filtrar por ID da app de origem | Não |
| `ad_network_campaign_id` | Filtrar por ID da campanha da rede de publicidade.<br /><br />**Nota**: Este não é o ID da campanha reportado pelo SKAdNetwork. | Não |
| `modeled_conversion_values` | <ul><li>Apenas suportado a partir da V2</li><li>O valor pode ser `true` ou `false`</li><li>Se `true`, o postback preenche a coluna “contagem” com dados de valor de conversão modelados.  [Veja o campo disponível para dados modelados](/docs/skan-aggregated-postback-arrival-date-api#report-structure-and-example)</li><li>Se , o postback apresenta a contagem de valor de conversão com todos os campos disponíveis conforme recebido e listado na estrutura do relatório, sem dados modelados.</li><li>O valor padrão é `false`.</li></ul> | Não |

</Accordion>

<div id="report-structure-and-example" />

<Accordion title="Estrutura de relatório e exemplo">

A API retorna um ficheiro CSV.

As colunas e métricas disponíveis estão listadas na tabela a seguir.

Exemplos: <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRXgsWlkyvMS20HgZuOQnH1YC8QQcRhOMYIOxyj_fcgikfDfmW6wNAMHO6alPWVA1j_KZwtqowohqrK/pub?gid=0&single=true&output=csv">V1</Anchor> | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRMFEELm8JCAQBBAIJqAc1eE5YdN0kOcSVkOPd_Ki2ngnX61wHL4sXypVouOhto8u-JCQmdIYY_5UG6/pub?gid=219191499&single=true&output=csv">V2</Anchor>

| Nome da coluna | Dimensão ou medida | Disponível com o token API V1 | Disponível com o token API V2 | Disponível com o token API V2 (para SKAN 4) | Disponível apenas com filtro de dados modelados |
| --- | --- | --- | --- | --- | --- |
| skad\_postback\_sequence\_index | Agrupar por | Não | Não | S | S |
| skad\_conversion\_value | Agrupar por | S | S | S | S |
| skad\_coarse\_conversion\_value | Agrupar por | Não | Não | S | S |
| skad\_ad\_network\_id<br /><br />Algumas SRNs não partilham o seu ID connosco. Neste caso, o campo fica vazio e o nome da ad\_network é preenchido. | Agrupar por | S | S | S | S |
| ad\_network\_name<br /><br />Atualmente, na maioria dos casos, este campo fica vazio. Preenchemo-lo no caso das SRNs que não partilham o seu skad\_ad\_network\_id | Agrupar por | S | S | S | S |
| skad\_source\_identifier | Agrupar por | Não | Não | S | S |
| skad\_campaign\_id | Agrupar por | S | S | S | S |
| ad\_network\_campaign\_id | Agrupar por | S | S | S | S |
| ad\_network\_campaign\_name | Agrupar por | S | S | S | S |
| ad\_network\_adset\_id | Agrupar por | Não | S | S | S |
| ad\_network\_adset\_name | Agrupar por | Não | S | S | S |
| ad\_network\_ad\_id | Agrupar por | Não | S | S | Não |
| ad\_network\_ad\_name | Agrupar por | Não | S | S | Não |
| ad\_network\_creative | Agrupar por | Não | Não | S | Não |
| ad\_network\_channel | Agrupar por | Não | Não | S | Não |
| skad\_version | Agrupar por | S | S | S | Não |
| skad\_redownload | Agrupar por | S | S | S | Não |
| skad\_source\_app\_id | Agrupar por | S | S | S | Não |
| skad\_source\_domain | Agrupar por | Não | Não | S | S |
| skad\_fidelity\_type | Agrupar por | Não | S | S | Não |
| geo | Agrupar por | S | S | S | Não |
| arrival\_date | Agrupar por | S | S | S | S |
| count | Medida | S | S | S | S |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Especificações e limitações">

| Especificação | Observações |
| --- | --- |
| Atualização dos dados | O relatório atualiza-se <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#eod">diariamente.</Anchor><br /><br />A disponibilidade dos dados está de acordo com a taxa de atualização de dados da <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#skan">SKAdNetwork</Anchor>. |
| Intervalo de datas | <ul><li>Data mais antiga suportada: 1 de novembro de 2020</li><li>Intervalo máximo de consulta: 60 dias</li></ul> |
| Limite de taxa | <ul><li>Consultas retornam até 200K linhas</li><li>60 chamadas por minuto</li></ul> |
| SRNs | Google Ads: A data de chegada do postback é derivada utilizando a última hora do clique relatada pelo Google. |
| Acesso à rede de anúncios | Disponível para parceiros de análise se o anunciante conceder permissão. |
| Acesso à agência | Não disponível |
| Fuso horário específico do aplicativo | UTC apenas |
| Moeda específica do aplicativo | Sempre USD |
| Dados orgânicos | Não disponível com esta API |
| Dados não orgânicos | Calculados usando postbacks do SKAdNetwork recebidos pela AppsFlyer |
| Dados históricos | Dados de conversão mais antigos (instalação ou retargeting) suportados: 1 de novembro de 2020 |
| Acesso do utilizador à conta | O token de autorização está disponível para um utilizador administrador no painel de controlo. |

</Accordion>

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/skan-aggregated-performance-report-api">API de relatório de desempenho agregado do SKAN</Anchor>

<div data-zendesk-anchors="skadnetwork-postback-arrival-date-aggregation-reporting-api=api-de-data-de-chegada-do-postback-agregado-do-skan h_01HDNZKFEHWET0FPX9WN136MB2=api-de-data-de-chegada-do-postback-agregado-do-skan h_01HDNZKFEH76Y06091QS6Y5K1Z=using-skan-aggregated-performance-report-api parameters=par%C3%A2metros h_01HDNZKFEHA6N6EE4RMG0HGABA=par%C3%A2metros h_01HDNZKFEHM2D7GS3RMSRCKZY7=report-structure-and-example h_01HDNZKFEJ5P3245V1R99DGAQW=specifications-and-limitations h_01HDNZP87CWGVJ3G1BDXAR1WN0=veja-tamb%C3%A9m" />
