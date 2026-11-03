---
title: Relatórios do Data Locker para anunciantes
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2021-11-11T09:48:51Z'
  edited_at: '2026-10-20T03:36:29Z'
  id: 4410643856657
  locale: pt
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/pt/articles/4410643856657
---
> **Resumo**: relatórios de dados agregados e brutos disponíveis via Data Locker

## Relatórios do Data Locker disponíveis para anunciantes

<table><colgroup><col/><col/><col/></colgroup><thead><tr><th>Tipo de dados</th><th>Grupo de relatórios</th><th>Assinatura do Data Locker necessária</th></tr></thead><tbody><tr><td>Dados</td><td>Jornada do usuário—dados brutos</td><td>Sim (2)</td></tr><tr><td>Dados</td><td>Os alertas do Protect360 são atualizados no horário UTC diário.</td><td>Sim</td></tr><tr><td>Dados</td><td>People-Based Attribution (PBA) </td><td>Não </td></tr><tr><td>Dados</td><td>Incrementalidade</td><td>Não </td></tr><tr><td>Dados</td><td>SKAN</td><td>Não (1)</td></tr><tr><td>Dados</td><td>Resultados</td><td><p>Para acessar o relatório de receita de anúncios é necessário ter uma assinatura do Data Locker.</p><p>Todos os outros relatórios exigem uma assinatura do pacote ROI360 Advanced.</p></td></tr><tr><td>Dados</td><td>Aplicativos de CTV, PC e console</td><td>Sim</td></tr><tr><td>Agregados</td><td>Análise de cohort</td><td>Não (1)</td></tr><tr><td>Agregado avançado</td><td>Análise de cohort</td><td>Não (3)</td></tr><tr><td>Agregados</td><td>Otimização de criativos</td><td><p>Não (1)</p><p>Requer um plano de assinatura de otimização de criativos premium.</p></td></tr><tr><td>Agregados</td><td>Métricas</td><td>Não (1)</td></tr><tr><td colspan="3"><p>(1) Se você não tiver uma assinatura do Data Locker, você deve fornecer um <a href="./data-locker-for-marketers#storage-options" target="_blank">armazenamento da sua propriedade</a>.</p><p>(2) Exceto para engajamento cross-platform</p><p>(3) Disponível com assinatura do Data Locker ou com o conjunto de analytics da API.</p></td></tr></tbody></table>

<div id="data-freshness-explanations" />

<Accordion title="Atualização de dados">

A disponibilidade dos relatórios do Data Locker varia de acordo com o tipo de relatório. Dependendo do tipo de relatório, os dados são entregues com um modelo de atualização por hora, dia ou versão. Para mais informações sobre como esses intervalos de atualização correspondem à hierarquia de pastas do Data Locker, veja a <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers#folder-structure">estrutura da pasta</Anchor>.

| Atualização de dados | Descrição | Exemplo de relatório |
| --- | --- | --- |
| Por hora | Relatórios atualizados ao longo do dia e escritos em pastas `h` por hora com base no momento em que a AppsFlyer recebe os dados. | <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">Relatório de eventos in-app</Anchor> |
| Por dia | Relatórios gerados uma vez por dia em vez de serem atualizados continuamente ao longo do dia. | <Anchor target="_blank" href="/marketers/pt/docs/measure-uninstalls">Relatório de instalação</Anchor> |
| Por versão | Relatórios em que os dados do mesmo dia podem ser publicados várias vezes à medida que dados mais recentes ou completos são disponibilizados (a versão mais recente é a mais precisa). | <Anchor target="_blank" href="/marketers/pt/docs/revenue-etl-reports#ad-revenue-versioned">Relatório de receita de anúncios atribuída</Anchor> |

</Accordion>

## Relatórios de dados brutos

<div id="user-journey" />

<Accordion title="Jornada do usuário">

Para mais informações sobre a descrição dos tipos de relatório, consulte os <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">relatórios de jornada do usuário</Anchor>.

| Categoria | Tipo de relatório (tópico) | Atualização dos dados | Orgânico/Não orgânico | Exclusivo para Data Locker |
| --- | --- | --- | --- | --- |
| Aquisição de usuários | Cliques | 1-3 horas | N/D | ✓ |
| Redirecionamento | Cliques | 1-3 horas | N/D | ✓ |
| Aquisição de usuários | Impressões | 1-3 horas | N/D | ✓ |
| Redirecionamento | Impressões | 1-3 horas | N/D | ✓ |
| Aquisição de usuários | Instalações | 1-3 horas | Ambos |  |
| Aquisição de usuários | Eventos in-app | 1-3 horas | Ambos |  |
| Aquisição de usuários | Receita de anúncios atribuída | Diariamente+1 | Não orgânico |  |
| Aquisição de usuários | Receita de anúncios orgânica | Diariamente+1 | Orgânico |  |
| Redirecionamento | Receita de anúncios de retargeting | Diariamente+1 | Não orgânico |  |
| Redirecionamento | Conversões | 1-3 horas | Não orgânico |  |
| Redirecionamento | Eventos in-app | 1-3 horas | Não orgânico |  |
| Redirecionamento | Sessões | 1-3 horas | Ambos | ✓ |
| Aquisição de usuários | Sessões | 1-3 horas | Ambos | ✓ |
| Aquisição de usuários | Desinstalações | Diariamente-desinstalação | Não orgânico |  |
| Aquisição de usuários | Desinstalações orgânicas | Diariamente-desinstalação | Orgânico |  |
| Reinstalações | Reinstalações | 1-3 horas | Não orgânico |  |
| Reinstalações | Reinstalações orgânicas | 1-3 horas | Orgânico |  |
| Aquisição de usuários | Engajamentos entre plataformas | Por hora | Ambos | ✓ |

</Accordion>

<div id="protect360" />

<Accordion title="Os alertas do Protect360 são atualizados no horário UTC diário.">

Saiba mais sobre os <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports">relatórios do Protect360</Anchor>

| Tipo de relatório (tópico) | Atualização dos dados |
| --- | --- |
| Instalações bloqueadas | 1-3 horas |
| Eventos in-app bloqueados | 1-3 horas |
| Cliques bloqueados | 1-3 horas |
| Instalações pós-atribuição | Por dia<br /><br />O relatório de cada dia contém instalações pós-atribuição relatadas no dia anterior. Por exemplo, o relatório dos dados gerados na segunda-feira está no relatório de terça-feira. |

</Accordion>

<div id="peoplebased-attribution" />

<Accordion title="People-based attribution">

**Atualização dos dados**

Disponível diariamente 10-12 horas após o final do dia anterior UTC. Por exemplo, os dados recebidos em uma segunda-feira são processados após o final do dia e estão disponíveis na pasta Monday h=23. Os dados ficam disponíveis antes das 12h UTC de terça-feira

**Considerações**

* Os dados de todos os brand bundles de PBA são sempre fornecidos sem considerar o filtro do aplicativo.
* A separação de dados por aplicativo não está disponível.

| Tipo de relatório (tópico) |
| --- |
| <Anchor target="_blank" href="/marketers/pt/docs/pba-raw-data-reports#website-visits-and-website-events">Visitas ao site</Anchor> |
| <Anchor target="_blank" href="/marketers/pt/docs/pba-raw-data-reports#website-visits-and-website-events">Eventos do site</Anchor> |
| <Anchor target="_blank" href="/marketers/pt/docs/pba-raw-data-reports#websiteassisted-installs::7e12586d">Instalações assistidas a partir do site</Anchor> |
| <Anchor target="_blank" href="/marketers/pt/docs/pba-raw-data-reports#conversion-paths">Caminhos de conversão</Anchor> |

</Accordion>

<div id="incrementality" />

<Accordion title="Incrementalidade">

Consulte <Anchor target="_blank" href="/marketers/pt/docs/incrementality-for-remarketing-overview#available-reports">Relatórios de incrementalidade</Anchor>

</Accordion>

<div id="skan" />

<Accordion title="SKAN">

Sobre <Anchor target="_blank" href="/marketers/pt/docs/skan-raw-data-reports">relatórios de dados brutos da SKAN</Anchor>

**Atualização dos dados**

* Os dados ficam disponíveis no dia seguinte ao dia em que o postback é recebido pela AppsFlyer ou os dados relatados à AppsFlyer pela API
* Os dados ficam contidos na pasta h=23 da data em que os dados são recebidos pela AppsFlyer. Exemplo: se o postback foi recebido na segunda-feira, ele é processado após o final do dia. O processamento é concluído até às 12:00 UTC de terça-feira e os dados são disponibilizados na pasta Monday h=23.

| Tipo de relatório (tópico) |
| --- |
| Postbacks |
| Cópia de postbacks (enviada diretamente pelo iOS para a AppsFlyer) |
| Instalações |
| Re-downloads |
| Eventos in-app |
| Dimensões de SRN |

</Accordion>

<div id="ad-revenue" />

<Accordion title="Resultados">

Consulte os <Anchor target="_blank" href="/marketers/pt/docs/revenue-etl-reports">relatórios de ETL de receita do Data Locker</Anchor>

Veja os <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">dados brutos da receita de anúncios</Anchor>

</Accordion>

<div id="ctv" />

<Accordion title="Dados das plataformas de CTV, PC e console.">

Veja <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-data-via-data-locker">dados de CTV, PC e console via Data Locker</Anchor>

</Accordion>

## Relatórios de dados brutos avançados (Beta)

Os relatórios avançados introduzem uma nova geração de relatórios de dados brutos projetados para fornecer conjuntos de dados estruturados, validados e **prontos para IA**. Eles permitem a ingestão e análise da **jornada completa do usuário, desde o primeiro engajamento até a conversão e atividade pós-instalação, usando apenas três relatórios**.  
Feitos com **campos tipados**, **nomenclatura de campo refinada** e um esquema consistente em todos os conjuntos de dados, esses relatórios garantem clareza, precisão e facilidade de uso. A estrutura unificada simplifica as junções de conjuntos de dados, **reduz a complexidade de ETL e processamento** e fornece dados que ajudam com análises avançadas e oferecem a flexibilidade necessária para trabalhar com seus dados da forma como você precisar. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/about-data-locker-advanced-reports">Sobre os relatórios avançados do Data Locker</Anchor>.

<div id="advanced-reports" />

<Accordion title="Relatório de engajamentos brutos">

O relatório de engajamentos brutos consolida dados de cliques e impressões de atividades de aquisição de usuários e retargeting, tanto em plataformas mobile quanto de TV conectada (CTV). Ao fornecer uma visão unificada das interações dos usuários com seus anúncios, esse relatório permite uma análise aprofundada da performance no topo do funil e ajuda os profissionais de marketing a identificarem quais criativos e canais geram engajamento significativo. Ele também permite uma otimização de custo e alcance a nível de engajamento, oferecendo a base para avaliar a exposição de marketing e a qualidade do tráfego. Para mais informações, consulte o <Anchor target="_blank" href="/marketers/pt/docs/about-data-locker-advanced-reports#engagements">relatório de engajamentos brutos</Anchor> em Sobre os relatórios avançados do Data Locker.

| Categoria | Tipo de relatório (tópico) | Atualização dos dados | Exclusivo para Data Locker |
| --- | --- | --- | --- |
| Guias de aquisição de usuários e retargeting | Cliques e impressões | 1–3 horas | ✅ |

</Accordion>

<div id="conversion-report" />

<Accordion title="Relatório de conversão">

O relatório de conversão oferece uma visão completa de todas as instalações de aplicativos, abrangendo fontes orgânicas e não orgânicas em plataformas mobile e de TV conectada (CTV). Ao centralizar os dados de conversão, os profissionais de marketing podem realizar uma análise completa do seu crescimento usando um único conjunto de dados simplificado. Use esse relatório para mensurar e otimizar com precisão a performance do seu marketing. Para mais informações, consulte o <Anchor target="_blank" href="/marketers/pt/docs/about-data-locker-advanced-reports#conversions">relatório de conversão</Anchor> em Sobre os relatórios avançados do Data Locker.

| Categoria | Tipo de relatório (tópico) | Atualização dos dados | Exclusivo para Data Locker |
| --- | --- | --- | --- |
| Guias de aquisição de usuários e retargeting | Conversões | 1–3 horas | ✅ |

> 📘 **Atenção**
>
> * Reinstalações não estão incluídas neste relatório.
> * Para aplicativos de plataforma estendida, incluindo CTV, PC e console, os eventos de conversão de retargeting não estão incluídos.

</Accordion>

<div id="h_01K9CROSSPLATFORMREPORT" />

<Accordion title="Relatório de eventos do usuário final">

O relatório de eventos do usuário final captura dados detalhados de eventos in-app, incluindo sessões, compras, cadastros e conclusões de níveis, em plataformas mobile e CTV. Cada evento é enriquecido com um contexto completo de atribuição, permitindo uma análise detalhada do comportamento do usuário, retenção e lifetime value, além de garantir a rastreabilidade completa da atribuição. Para mais informações, consulte o [relatório de eventos do usuário final](#enduser-events) em Sobre os relatórios avançados do Data Locker.

| Categoria | Tipo de relatório (tópico) | Atualização dos dados | Exclusivo para Data Locker |
| --- | --- | --- | --- |
| Guias de aquisição de usuários e retargeting | Eventos de usuários finais | 1–3 horas | ✅ |

> 📘 **Atenção**
>
> Para aplicativos de plataforma estendida, incluindo CTV, PC e console, eventos de retargeting para usuários finais não estão incluídos.

</Accordion>

## Relatórios agregados

<div id="cohort-analytics" />

<Accordion title="Análise de cohort">

**Atualização dos dados**

Os relatórios geralmente estão disponíveis às 12:00 UTC na pasta do dia anterior. Por exemplo, se o processamento for concluído até às 12:00 UTC de terça-feira, os dados são disponibilizados na pasta Monday.

| Tipo de relatório (tópico) |
| --- |
| <Anchor target="_blank" href="/marketers/pt/docs/cohort-analytics-via-data-locker">Cohort unificado</Anchor> |
| <Anchor target="_blank" href="/marketers/pt/docs/cohort-analytics-via-data-locker">Cohort de aquisição de usuários</Anchor> |
| <Anchor target="_blank" href="/marketers/pt/docs/cohort-analytics-via-data-locker">Cohort de retargeting</Anchor> |

</Accordion>

<div id="advanced-aggregated-reports" />

<Accordion title="Relatórios agregados avançados">

Os relatórios agregados avançados no Data Locker oferecem dados agregados atualizados, precisos, granulares e com um volume ilimitado. <Anchor target="_blank" href="/marketers/pt/docs/advanced-aggregated-reports-in-data-locker">Saiba mais</Anchor>

</Accordion>

<div id="creative-optimization-etl" />

<Accordion title="Otimização de criativos">

Os relatórios de ETL de otimização de criativos permitem que os seus analistas de dados acessem todas as informações necessárias para a análise da performance dos seus assets criativos. São fornecidos relatórios completos de performance a nível de criativo, incluindo todos os principais indicadores de performance (KPIs), KPIs de fundo e topo de funil, dados de atribuição e dados de assets criativos. <Anchor target="_blank" href="/marketers/pt/docs/creative-optimization-etl-reporting">Saiba mais</Anchor>

</Accordion>

<div data-zendesk-anchors="reports-available-via-data-locker-for-advertisers=relat%C3%B3rios-do-data-locker-dispon%C3%ADveis-para-anunciantes 01H7WFZN6P1S49NYX8Q0W55P0B=relat%C3%B3rios-do-data-locker-dispon%C3%ADveis-para-anunciantes 01H7WFZN6PQWASTMXM9V72QZER=data-freshness-explanations raw-data-reports=relat%C3%B3rios-de-dados-brutos 01H7WFZN6P94YW1V79NT3HV5G4=relat%C3%B3rios-de-dados-brutos 01H7WFZN6PD75S557PDB5PSFFR=user-journey 01H7WFZN6QY2GV69N464EE196M=protect360 01H7WFZN6QW72FDBTMW2ZD7NZQ=peoplebased-attribution 01H7WFZN6QZ1B7BS6E59RVAF30=incrementality 01H7WFZN6Q0P99DCFA7MZQTVSX=skan 01H7WFZN6Q717F9Z1HG38JVBG3=ad-revenue 01H7WFZN6QMJGSAJR00MHYJB6Z=ctv Unified%20raw-data-reports=relat%C3%B3rios-de-dados-brutos-avan%C3%A7ados-beta h_01JX9T0PGE93JNJ3S4NDP0C2YW=relat%C3%B3rios-de-dados-brutos-avan%C3%A7ados-beta h_01K85EE8DA4E8D4SVHYV2PE42E=conversion-report h_01K85EE8DAWY52B7RJQ33MJ59B=aten%C3%A7%C3%A3o cross-platform-end-user-events-report=h_01K9CROSSPLATFORMREPORT h_01KMD3WY9MQABBWFCTJYVWG66S=aten%C3%A7%C3%A3o-1 aggregated-reports=relat%C3%B3rios-agregados 01H7WFZN6Q90AT8N0VY5PKQ407=relat%C3%B3rios-agregados 01H7WFZN6QNKXTRM7G6VFANSZ7=cohort-analytics h_01J0K1MEKEEAQBXF1YRZTG8V0X=advanced-aggregated-reports h_01J0TQ88VNSFZJ27T3E2P3MVE6=creative-optimization-etl" />
