---
title: Visão geral dos relatórios agregados e analíticos
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
    - Ad Networks
  created_at: '2020-02-04T09:38:14Z'
  edited_at: '2026-09-08T00:02:16Z'
  id: 360005437257
  locale: pt
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/pt/articles/360005437257
---
> **At a glance:** Descrição e comparação dos relatórios de atribuição agregados e analíticos, das ferramentas e das APIs disponíveis.

<div id="aggregated-and-analytics-performance-reporting-overview" />

## Relatórios de análise e de performance agregada — ferramentas e relatórios

As ferramentas de análise agregadas na plataforma fornecem aos anunciantes métricas que permitem que eles avaliem a performance de seus aplicativos, campanhas e usuários.

As ferramentas diferem na forma como os dados são apresentados. Alguns relatórios mostram métricas de valor do tempo de vida (LTV) para campanhas, enquanto outros, como Cohort, são usados para analisar o engajamento do usuário ao longo do tempo.

Neste artigo, as informações detalhadas sobre as ferramentas dizem respeito a dados que podem ser exportados da plataforma. Use a tabela de comparação de ferramentas a seguir para entender a função principal e as diferenças entre as ferramentas.

<Accordion title="Comparação do método de relatório">

A tabela a seguir descreve os diferentes métodos de relatórios e painéis para obter dados agregados.

[Baixe a tabela como um arquivo CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vSICicxcvD0996RT59fTLDJvdGUKxqPqr47f5SMD8BmsbZtrWIoxRxJEo7tAXTBBmnIbiH097VtK6L9/pub?output=xlsx) para ver campos adicionais que explicam várias especificações e limitações para ajudá-lo a comparar e contrastar os diferentes métodos de relatório.

Os campos de especificação adicionais no arquivo CSV para download incluem:

* <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support">Atualização de dados</Anchor>:o período de tempo entre a ocorrência do evento e a disponibilização dos dados por meio do método de relatório.
* <Anchor target="_blank" href="/marketers/pt/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV/atividade</Anchor>: se os dados são LTV ou atividade.
* <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">Retargeting</Anchor>: se os dados de retargeting (reengajamento e reatribuição) são exibidos.
* <Anchor target="_blank" href="/marketers/pt/docs/measure-reinstalls#attributed-to-the-first-install">Atribuição de eventos de reinstalação à primeira instalação</Anchor>: se os eventos após uma reinstalação podem ser atribuídos à instalação original.
* <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#date-and-timezone-principles">Fuso horário</Anchor>: qual fuso horário (UTC ou selecionado pelo aplicativo) é usado para exibir os dados.
* <Anchor target="_blank" href="/marketers/pt/docs/measure-reinstalls#unattributed-organic-inapps">Eventos não atribuídos</Anchor>: se os eventos que não são atribuídos após uma reinstalação são exibidos.
* <Anchor target="_blank" href="/marketers/pt/docs/campaign-name-changes?">Mudanças de nome de campanha</Anchor>: se você pode alterar nomes de campanha sem criar exibições duplicadas.

| Método de relatório | Descrição |
| --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor>  <br />(Recurso Premium) | KPIs selecionados de LTV, atividade, retenção, coorte e desempenho de campanha Protect360 por API, no formato CSV ou JSON. |
| <Anchor target="_blank" href="/marketers/pt/docs/pull-api-aggregate-data">Pull API - relatórios agregados</Anchor> | Valor permanente (LTV) de usuários que instalam, reativam ou reatribuem em arquivos CSV. Os dados de UA e retargeting são separados; não há uma opção unificada. |
| <Anchor target="_blank" href="/marketers/pt/docs/aggregated-data-export-page">Página de exportação de dados - relatórios agregados</Anchor> | Valor permanente (LTV) de usuários que instalam, reativam ou reatribuem em arquivos CSV. Os dados de UA e retargeting são separados; não há uma opção unificada. |
| <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">Visão geral do SKAN</Anchor> | Métricas relatadas por meio de postbacks do SKAN iOS e postbacks adicionais durante as janelas iniciais de métrica do usuário. |
| <Anchor target="_blank" href="/marketers/pt/docs/skan-aggregated-performance-report-api">APIs de dados agregados do SKAN</Anchor> | Métricas relatadas por meio de postbacks do SKAN iOS e postbacks adicionais durante as janelas iniciais de métrica do usuário. |
| <Anchor target="_blank" href="/marketers/pt/docs/protect360-dashboard">Painel do Protect360</Anchor> | Métricas e insights relacionados ao tráfego fraudulento.  <br />Dados baseados em LTV para instalações e dados baseados em atividades para eventos in-app. |
| <Anchor target="_blank" href="/marketers/pt/docs/cohort-and-retention-dashboard">Painel de coorte</Anchor> | Várias métricas de usuário para cada dia pós-instalação. |
| <Anchor target="_blank" href="/marketers/pt/docs/cohort-api">API de coorte</Anchor>  <br />(Recurso Premium) | Várias métricas de usuário para cada dia pós-instalação. Também inclui atividade no nível do evento por event\_date para usuários cuja conversão ocorreu dentro de 365 dias. |
| <Anchor target="_blank" href="/marketers/pt/docs/cohort-analytics-via-data-locker">Coorte Data Locker</Anchor>  <br />(Recurso Premium) | Várias métricas de usuário para cada dia pós-instalação. Também inclui atividade no nível do evento por event\_date para usuários cuja conversão ocorreu dentro de 1.095 dias. |
| Eles são o <Anchor target="_blank" href="/marketers/pt/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">Lifetime value (LTV)</Anchor> , de modo que o intervalo de datas do relatório se relaciona com a data de atribuição sendo: | Relatórios de dados agregados versionados. o LTV (limitado). |
| <Anchor target="_blank" href="/marketers/pt/docs/custom-dashboards">Painel Personalizado</Anchor> | Painel personalizado com métricas de LTV de aquisição de usuários. |
| <Anchor target="_blank" href="/marketers/pt/docs/pivot-table-user-metrics">Relatórios de tabela dinâmica</Anchor>  <br />(Recurso Premium) | KPIs selecionados de LTV, atividade, retenção e desempenho da campanha Protect360, no painel ou via CSV. |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-and-use-roi360-cost-etl-reports">ETL de custos</Anchor> | Dados de custo de campanha com a melhor granularidade disponível por fonte de mídia. |
| Relatório de uso | Uma combinação de todos os recursos baseados em uso na AppsFlyer que afetam as obrigações contratuais durante os prazos dos ciclos de cobrança. |
| <Anchor target="_blank" href="/marketers/pt/docs/creative-optimization-guide">Dashboard de otimização de criativos</Anchor> | Dados de performance de LTV sobre criativos. Isso significa que as métricas são de conversões que ocorreram a partir de criativos durante o intervalo de datas selecionado. |

</Accordion>

<Accordion title="Métodos de entrega de dados de coorte">

O cohort está disponível por meio de diferentes métodos de entrega: <Anchor target="_blank" href="/marketers/pt/docs/cohort-and-retention-dashboard">dashboard de cohort</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/cohort-api">API de Cohort</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/cohort-analytics-via-data-locker">análises de cohort via Data Locker</Anchor>. A tabela a seguir lista as diferenças entre cada formato.

| Característica | Análise de coorte no Data Locker | Relatórios agregados avançados no Data Locker | Dashboard de cohort | API de Coorte |
| --- | --- | --- | --- | --- |
| Aplicativo único ou vários | Vários. Os dados são agrupados por aplicativo em um único arquivo ou segregados em arquivos separados por aplicativo. | Vários. Desempenho combinado ou agrupado por opções de aplicativo. | Vários. Desempenho combinado ou agrupado por opções de aplicativo. | Único |
| Agrupamentos | Hierarquia completa de campanhas e nomes de eventos. 20 agrupamentos | Hierarquia completa de campanhas e nomes de eventos. 20 agrupamentos | 4 agrupamentos | 7 agrupamentos |
| Métricas disponíveis | Várias métricas de usuário para cada dia pós-instalação. | Todas as métricas | 1 métrica selecionável e 4 métricas fixas por visualização | 1 métrica selecionável e 4 métricas fixas por chamada |
| Dias disponíveis após a atribuição (dias de cohort) | 365 | 1095 | 180 | 180 |
| Limitações de exportação de dados | Todo o conjunto de dados está disponível | Tipos de cohort | Download e configurações manuais | Taxa e tamanho de resposta limitados |
| Solicitação personalizável | Retargeting | Não | Sim | Sim |

Diferenças entre os tipos de cohort

</Accordion>

<div id="user-journey-reports" />

### Relatórios de jornada do usuário

Os relatórios descritos estão disponíveis na página Exportar dados ou através da Pull API agregada.

São relatórios de <Anchor target="_blank" href="/marketers/pt/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">valor do tempo de vida (LTV)</Anchor>. Portanto:

* A data mais antiga do relatório é a primeira data de instalação do aplicativo.
* O intervalo de datas do relatório está relacionado à data de atribuição:
  * Data de instalação dos relatórios UA e Protect360
  * Data da reatribuição ou do reengajamento no caso de relatórios de retargeting

<Accordion title="Relatórios de dados agregados UA LTV que contêm usuários não orgânicos e orgânicos">

<table><thead><tr><th>Nome do relatório</th><th>Agrupado por</th></tr></thead><tbody><tr><td>Parceiros (fontes de mídia)</td><td>Agência, fonte de mídia, campanha</td></tr><tr><td>Parceiros por data</td><td>Data, agência, fonte de mídia, campanha</td></tr><tr><td>Atividade diária</td><td>Data, agência, fonte de mídia, campanha</td></tr><tr><td>Localização</td><td>País, agência, fonte de mídia, campanha</td></tr><tr><td>Geolocalização por data</td><td>Data, país, agência, fonte de mídia, campanha</td></tr><tr><td>KPIs de atribuição de exibição (VTA)</td><td><a href="./pull-api-aggregate-data" target="_blank">Os relatórios VTA estão disponíveis pela Pull API</a></td></tr><tr><td colspan="2"> <strong>Observação</strong>: se Meta ads for o <em>canal de mídia</em> selecionado, colunas adicionais serão incluídas: ID do grupo de anúncios, nome do grupo de anúncios, ID do conjunto de anúncios, nome do conjunto de anúncios</td></tr></tbody></table>

Os campos de data nos arquivos CSV têm o formato aaaa-mm-dd. Quando você abre um arquivo CSV no Excel, os campos de data são formatados usando as configurações de data e hora do seu computador. Certifique-se de selecionar a exibição da data apropriada no <Anchor target="_blank" href="https://support.office.com/en-us/article/format-a-date-the-way-you-want-8e10019e-d5d8-47a1-ba95-db95123d273e#ID0EAACAAA=Windows">Excel.</Anchor>

<div id="examples-of-aggregate-reports" />

#### Exemplos de relatórios agregados

[Exemplos de relatórios em uma planilha](https://docs.google.com/spreadsheets/d/e/2PACX-1vQmzRons779Dk5QWVoPsOF8E7yJLwNPB1IF87shZr6rcMJLjszlSNIbAMVcdeQLysr8Bc4QAby5QB4u/pub?output=xlsx)

<div id="fields-in-ua-aggregate-reports" />

#### Campos nos relatórios agregados de UA

<table><thead><tr><th rowspan="2">Campo</th><th rowspan="2">Descrição</th><th colspan="5">Nome do relatório</th></tr><tr><th>Parceiro (fonte de mídia)</th><th>Parceiro por data</th><th>Diariamente</th><th>Localização</th><th>Geolocalização por data</th></tr></thead><tbody><tr><td>País</td><td>País da instalação</td><td></td><td></td><td></td><td>✓</td><td>✓</td></tr><tr><td>Data</td><td>Data da atribuição</td><td></td><td>✓</td><td></td><td></td><td>✓</td></tr><tr><td>Agência/PMD (af_prt)</td><td>Nome da agência/parceiro</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Canal de mídia (pid)</td><td>Fonte de mídia que trouxe o usuário (pid = fonte de mídia)</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Campanha</td><td>Nome da campanha (c = nome da campanha)</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>ID da campanha</td><td>ID da campanha do Meta</td><td>Somente Meta ads</td><td>Somente Meta ads</td><td>Somente Meta ads</td><td>Somente Meta ads</td><td>Somente Meta ads</td></tr><tr><td>ID do grupo de anúncios</td><td>ID do grupo de anúncios do Meta ou ID do anúncio</td><td>Somente Meta ads</td><td>Somente Meta ads</td><td>Somente Meta ads</td><td>Somente Meta ads</td><td>Somente Meta ads</td></tr><tr><td>Nome do grupo de anúncios</td><td>Grupo de anúncios do Meta</td><td>Somente Meta ads</td><td>Somente Meta ads</td><td>Somente Meta ads</td><td>Somente Meta ads</td><td>Somente Meta ads</td></tr><tr><td>Adset ID</td><td>ID do conjunto de anúncios do Meta</td><td>Somente Meta ads</td><td>Somente Meta ads</td><td>Somente Meta ads</td><td>Somente Meta ads</td><td>Somente Meta ads</td></tr><tr><td>Nome do adset</td><td>Nome do conjunto de anúncios do Meta</td><td>Somente Meta ads</td><td>Somente Meta ads</td><td>Somente Meta ads</td><td>Somente Meta ads</td><td>Somente Meta ads</td></tr><tr><td>OPCIONAL</td><td>receita média por usuário</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>eCPI médio</td><td>eCPI médio</td><td></td><td>✓</td><td></td><td></td><td></td></tr><tr><td>Cliques</td><td>Número de cliques</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Taxa de conversão</td><td>Número de instalações/número de cliques</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Click-through rate</td><td>Taxa de cliques</td><td></td><td>✓</td><td>✓</td><td></td><td></td></tr><tr><td>`{your event name}(Usuários únicos)</td><td>Número de usuários únicos que realizaram o evento</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>{your event name} (Contador de eventos)</td><td>Contador de eventos</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>{your event name}` (Vendas em XXX)</td><td>Vendas do evento em XXX, em que XXX é a moeda selecionada pelo aplicativo</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>Impressões</td><td>Número de impressões</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>Instalações</td><td>Número de instalações</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Usuários fiéis</td><td>[padrão] Usuário que abre o aplicativo mais de 3 vezes</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Usuários fiéis/Instalações</td><td>Taxa de usuários fiéis</td><td>✓</td><td>✓</td><td></td><td></td><td></td></tr><tr><td>ROI</td><td>Retorno sobre o investimento</td><td>✓</td><td>✓</td><td></td><td></td><td></td></tr><tr><td>Sessões</td><td><ul><li>Número de aberturas de aplicativos não orgânicos</li><li>Sessões orgânicas e não orgânicas estão disponíveis na Análise da coorte</li></ul></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Custo total</td><td>-</td><td>✓</td><td>✓</td><td></td><td></td><td></td></tr><tr><td>Receita total</td><td>Receita total gerada a partir da fonte de mídia e da campanha</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td colspan="7"> <strong>Observação:</strong> as colunas que mostram "somente Meta ads" são incluídas ao selecionar o Meta as como o único canal de mídia.</td></tr></tbody></table>

</Accordion>

<Accordion title="Relatórios de dados agregados de retargeting">

Os relatórios de retargeting consistem em usuários que engajaram com uma <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide#retargeting-reports-and-raw-data">campanha de retargeting</Anchor> e realizaram um reengajamento ou reatribuição

Nos relatórios de retargeting, não há distinção entre usuários orgânicos e não orgânicos.

Para obter relatórios de retargeting via Pull API, adicione o parâmetro *&reattr=true* aos URIs dos relatórios de performance.

<div id="aggregate-ltv-retargeting-reports" />

#### Relatórios de retargeting de LTV agregado

| Nome do relatório | Agrupado por |
| --- | --- |
| Parceiros (fontes de mídia) | Agência, fonte de mídia, campanha |
| Parceiros por data | Data, agência, fonte de mídia, campanha |
| Atividade por data | Data, agência, fonte de mídia, campanha |
| País | País, agência, fonte de mídia, campanha |
| País por data | Data, país, agência, fonte de mídia, campanha |

<div id="aggregate-ltv-retargeting-reports-1" />

#### Relatórios de retargeting de LTV agregado

| Campo | Descrição | Parceiros | Diariamente | Parceiros por data | Geolocalização por data | Geolocalização |
| --- | --- | --- | --- | --- | --- | --- |
| Data | Data de conversão | - | - | ✓ | ✓ | - |
| País |  | - | ✓ |  | ✓ | ✓ |
| Agência/PMD (af\_prt) | Nome da agência/parceiro | ✓ | ✓ | ✓ | ✓ | ✓ |
| Canal de mídia (pid) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Campanha (c) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Cliques |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Conversões |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Tipo de conversão | Reatribuição ou reengajamento | ✓ | ✓ | ✓ | ✓ | ✓ |
| Taxa de conversão | Conversões/cliques | ✓ | ✓ | ✓ | ✓ | ✓ |
| Sessões |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Usuários fiéis |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Usuários fiéis/Instalações |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Custo total |  | - | - | - | - | - |
| eCPI médio |  | - | - | - | - | - |
| Receita total |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| ROI |  | - | - | - | - | - |
| OPCIONAL |  | ✓ | ✓ | ✓ | - | ✓ |

</Accordion>

<div id="feature-reports" />

## Relatórios de recurso

<Accordion title="Proteção contra fraudes">

<Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#reporting-options">Relatórios agregados SKAdNetwork</Anchor>

</Accordion>

<Accordion title="Protect360—fraude bloqueada">

![Exemplo de relatório de fraude bloqueado do Protect360](https://theme.zdassets.com/theme_assets/245528/ffbbc473bb0e74b9fb636ed735f69e9af6a25a18.png)

Os relatórios agregados de fraude bloqueada fornecem detalhes de eventos bloqueados pela <Anchor target="_blank" href="/marketers/pt/docs/protect360-anti-fraud-guide">Protect360</Anchor>.

Os relatórios estão disponíveis pela Pull API. Estes relatórios não estão disponíveis na página Export Data.

O período está relacionado à data de instalação.

<div id="aggregate-protect360-reports-available-via-pull-api" />

#### Relatórios agregados do Protect360 disponíveis pela Pull API

| Nome do relatório |
| --- |
| Parceiros (fontes de mídia) |
| Parceiros por data |
| Geolocalização |
| Geolocalização por data |
| Relatório de campanha do parceiro |

**Limitação:** O motivo do bloqueio **Bots** é exibido mesmo em casos em que o motivo deveria ser **versão do aplicativo** ou **ID de usuário do cliente ausente**.

</Accordion>

<div id="see-also" />

#### Veja também

* <Anchor target="_blank" href="/marketers/pt/docs/configuring-meta-campaign-management-partners">Configuração de parceiros de gerenciamento de campanhas do Meta</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">Visão geral dos relatórios de dados brutos</Anchor>

<div data-zendesk-anchors="aggregated-and-analytics-performance-reporting%E2%80%94tools-and-reports=relat%C3%B3rios-de-an%C3%A1lise-e-de-performance-agregada--ferramentas-e-relat%C3%B3rios 01EWA9VQ2HH93525BMK6WN0P6S=relat%C3%B3rios-de-an%C3%A1lise-e-de-performance-agregada--ferramentas-e-relat%C3%B3rios user-journey-reports=relat%C3%B3rios-de-jornada-do-usu%C3%A1rio 01ED4D7W8CVAQ9V2GCEX1G6KD7=relat%C3%B3rios-de-jornada-do-usu%C3%A1rio examples-of-aggregate-reports=exemplos-de-relat%C3%B3rios-agregados 01ED4D7W8C3ZNBYR3CMHJF3QSE=exemplos-de-relat%C3%B3rios-agregados fields-in-ua-aggregate-reports=campos-nos-relat%C3%B3rios-agregados-de-ua h_01HDNYFR9KTQ7ZF35C7E7M7AF1=campos-nos-relat%C3%B3rios-agregados-de-ua aggregate-ltv-retargeting-reports=relat%C3%B3rios-de-retargeting-de-ltv-agregado h_01HDNYFR9MSJWCP3JA4M1WXN1H=relat%C3%B3rios-de-retargeting-de-ltv-agregado aggregate-ltv-retargeting-reports::b2093953=relat%C3%B3rios-de-retargeting-de-ltv-agregado-1 h_01HDNYFR9MSK9VQQ0Q889Z55TN=relat%C3%B3rios-de-retargeting-de-ltv-agregado-1 feature-reports=relat%C3%B3rios-de-recurso h_01HDNYFR9MYXVZ5BA9FDZ6D82M=relat%C3%B3rios-de-recurso aggregate-protect360-reports-available-via-pull-api=relat%C3%B3rios-agregados-do-protect360-dispon%C3%ADveis-pela-pull-api h_01HDNYFR9MSZ9K8F283J0WBHCZ=relat%C3%B3rios-agregados-do-protect360-dispon%C3%ADveis-pela-pull-api h_01HDNYYJXVY9XHX87K06NXYQNS=veja-tamb%C3%A9m" />
