---
title: Sobre as APIs para anunciantes
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2020-05-24T15:14:53Z'
  edited_at: '2026-08-18T00:10:28Z'
  id: 360009122638
  locale: pt
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: https://support.appsflyer.com/hc/pt/articles/360009122638
---
> **Resumo:** APIs disponíveis para o acesso e atualização de dados por parte dos anunciantes.

<div id="advertiser-api-list-and-interfaces" />

## Interfaces e lista de APIs disponíveis para anunciantes

<span id="01EEQJERAWW3HY59HVPY3YWA0B"></span>Informações específicas sobre relatórios, ferramentas de relatórios e APIs:

* <span id="01EEQJERAW2ZTBWBQKBCDSC76Z"></span><span id="01EEQJERAWQ2WCPV0207XM6FR4"></span><Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview"><span id="01EEQJERAX0W7RCYQWVM2M5S13"></span>APIs/ferramentas de relatórios de dados brutos</Anchor>
* <span id="01EEQJERAWA09P200SGR985846"></span><span id="01EEQJERAW6AC6WR7E46T5DMHW"></span><Anchor target="_blank" href="/marketers/pt/docs/aggregated-and-analytics-reporting-overview">APIs/ferramentas de relatórios agregados e analytics</Anchor>

<div id="interfaces-for-advertisers" />

#### Interfaces para anunciantes

| Arena | Nome da API | ![af_premium.png](https://files.readme.io/ad0c279c48242ea25529f1bc386ee2c747bcd332f5fb1eb2fc26dd378a257f6e-4403570953105.png)<br /><br />Funcionalidade premium | Descrição | Autenticação  <br />token/key | Tipo de interface |
| --- | --- | --- | --- | --- | --- |
| Atribuição mobile | <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">Eventos server-to-server</Anchor> | Não | Registrar eventos no aplicativo que ocorrem fora de um aplicativo mobile | <Anchor target="_blank" href="/marketers/pt/docs/app-settings#sdk-authentication-dev-key">SDK dev key</Anchor> | REST API |
| People-Based Attribution (PBA) | <Anchor target="_blank" href="/marketers/pt/docs/web-server-to-server-events-api-for-pba-web-s2s">Server-to-server web</Anchor> | Não | Relatar eventos de PBA que ocorrem no Backend | <Anchor target="_blank" href="/marketers/pt/docs/pba-brand-bundles-and-settings#gerenciamento-de-bundles-de-marca">PBA key</Anchor> | REST API |
| com o anúncios | <Anchor target="_blank" href="/marketers/pt/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">Os links diretos universais do OneLink</Anchor> | Sim | Gerenciar OneLinks: criar, atualizar, recuperar, excluir | <Anchor target="_blank" href="/marketers/pt/docs/app-settings#sdk-authentication-dev-key">SDK dev key</Anchor> | REST API |
| Remarketing | <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide#import-an-audience">Audiências</Anchor> | Sim | Upload de listas de usuários no Audiences | <Anchor target="_blank" href="/marketers/pt/docs/audiences-import-audience-segments-from-internal-systems">Import key</Anchor> | REST API |
| Privacidade | <Anchor target="_blank" href="/marketers/pt/docs/send-opendsr-api-requests">Solicitações openDSR</Anchor> | Não | Solicitações de remoção de dados e status | <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Relatórios | <Anchor target="_blank" href="/marketers/pt/docs/master-api-user-acquisition-metrics-via-api">Master performance KPIs</Anchor> | Sim | Métricas de performance de campanhas de vários aplicativos em arquivos CSV | <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Relatórios | <Anchor target="_blank" href="/marketers/pt/docs/pull-api-aggregate-data">Extrair relatórios agregados</Anchor> | Não | Agregar relatórios em arquivos CSV | <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Relatórios | <Anchor target="_blank" href="/marketers/pt/docs/pull-api-raw-data">Extrair dados brutos</Anchor> | Sim | Relatórios de dados brutos em arquivos CSV | <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Relatórios | <Anchor target="_blank" href="/marketers/pt/docs/cohort-api">Analytics de cohort</Anchor> | Sim | Métricas de cohort em arquivos JSON ou CSV | <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Relatórios | <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers">Relatório do Data Locker</Anchor> | Sim | Relatórios de dados brutos e agregados | N/D | Cloud storage |
| Atribuição mobile | <Anchor target="_blank" href="/marketers/pt/docs/push-api-streaming-raw-data">Empurre</Anchor> | Sim | Instalações em tempo real e eventos no aplicativo enviados para os servidores dos anunciantes | N/D | REST API |
| Custo da campanha | <Anchor target="_blank" href="/partners/pt/docs/cost-import-for-ad-networks">Importação de custos</Anchor> | Não | Relatar o custo da campanha | N/D | Upload de arquivos |
| Conta | <Anchor target="_blank" href="/marketers/pt/docs/app-list-api-for-app-owners">Obter lista de aplicativos</Anchor> | Não | Obter uma lista de aplicativos na sua conta | <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Relatórios | <Anchor target="_blank" href="/marketers/pt/docs/set-up-and-use-roi360-cost-etl-reports">ETL Cost</Anchor> | Sim | Cost ETL - custo granular da campanha | N/D | Cloud storage |
| Relatórios | <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#reporting-options">Relatórios SKAN</Anchor> | Não | Relatórios agregados da SKAN | V2.0 | REST API |
| Parceiros integrados | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-copy">Copiar configurações de integração do parceiro</Anchor> | Não | Copiar parâmetros de configuração da integração de um aplicativo para o outro | V2.0 | REST API |
| Parceiros integrados | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-integration-params">Definir chave de descriptografia do install referrer</Anchor> | Não | Definir a chave de install referrer decryption recebida do Meta ads | V2.0 | REST API |

<div data-zendesk-anchors="advertiser-api-list-and-interfaces=interfaces-e-lista-de-apis-dispon%C3%ADveis-para-anunciantes h_01HX9638DX6EHR4ETMSH10K68F=interfaces-e-lista-de-apis-dispon%C3%ADveis-para-anunciantes interfaces-for-advertisers=interfaces-para-anunciantes h_01HX9638DXNJM3A968A2PSRRKS=interfaces-para-anunciantes" />
