---
title: Atribuição Baseada em Pessoas (PBA)—Visão Geral
metadata:
  keywords:
    - People Based Analysis
    - People Based Attribution
    - People Based Attribution SDK
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-08-19T11:53:56Z'
  edited_at: '2026-08-18T00:23:58Z'
  id: 360002274017
  locale: pt
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/pt/articles/360002274017
---
> **Visão geral:** People-Based Attribution (PBA) oferece uma visão unificada da jornada do cliente por diferentes canais, plataformas e dispositivos.

<Image align="center" alt="PBANoSilos_us-en.gif" src="https://files.readme.io/1ac3614eb1b9d4c01bffbe904f1a060d1facd681ff32c274b12f0a15612a2e4a-360009359798.gif" />

<div id="pba-principles" />

## Princípios de PBA

* O PBA consolida dados de sites e aplicativos mobile para oferecer uma visão holística da performance da campanha em todas as propriedades digitais de uma marca. Os anunciantes usam o PBA para entender as jornadas dos clientes em termos de pessoas, no lugar de dispositivos.
* Os dados do PBA—nos painéis do PBA e nos relatórios de dados brutos—são usados para análises de marketing e otimização de campanhas.
* Os dados que consistem em visitas ao site e eventos do usuário são adquiridos usando <Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide">SDKs e/ou APIs.</Anchor>
* Para cada visita ao site: a fonte de mídia responsável por gerar a visita é determinada. Qualquer evento resultante (conversão) é <Anchor target="_blank" href="/marketers/pt/docs/pba-media-source-attribution-rules">atribuído</Anchor> à fonte de mídia responsável pela visita.

<div id="pba-analytics-dashboards-and-raw-data" />

### Painéis analíticos de PBA e dados brutos

* Os dados de PBA são exibidos em dashboards de análise e relatórios:
  * Atribuição do site
  * Instalações Auxiliadas pela Web
  * Relatórios de dados brutos
* Os dados nos painéis são <Anchor target="_blank" href="/marketers/pt/docs/using-pba-dashboards">filtrados e agrupados</Anchor> usando dimensões como plataforma mobile, canal e tipo de mídia. Isso permite que você detalhe e examine os dados.

<div id="website-attribution" />

### <Anchor target="_blank" href="/marketers/pt/docs/pba-website-attribution-dashboard">Atribuição do site</Anchor>

<Image align="center" alt="WebsiteAttributionTable" src="https://files.readme.io/46f03ee216dc23f3f184663aeef7d6b64ae6fb9a64e7a161ff0482e4d2eab204-360013057757.jpg" />

Analise fontes de tráfego da web e campanhas de marketing que impulsionam visitas e conversões de usuários no seu site. Descubra diferenças entre as performances a nível de anúncio. Compatível com todos os parâmetros de consulta (query) da AppsFlyer no link sem a necessidade de redirecionar os usuários para servidores da AppsFlyer.

<div id="web-assisted-installs" />

### <Anchor target="_blank" href="/marketers/pt/docs/pba-web-assisted-installs">Instalações Auxiliadas pela Web</Anchor>

<Image align="center" alt="AppsFlyer-Web-to-App_us.en.gif" src="https://files.readme.io/4a278b57379c999d80fd7f1dfea750049f56c03ed32051f9af92577b2a51742a-360009705058.gif" />

Use as Instalações Auxiliadas pela Web para analisar o impacto e os resultados de seus esforços de marketing na web na condução de instalações de aplicativos mobile.

* Receba insights de como diferentes tipos de mídia (paga, própria, adquirida), canais de mídia (direto, mídia social, busca orgânica) e fontes de mídia interagem e contribuem para seus esforços gerais de aquisição de usuário.
* Atribua instalações orgânicas impulsionadas por seus esforços na web.
* Examine a interação entre esforços da web e instalações não orgânicas.

<div id="raw-data" />

### <Anchor target="_blank" href="/marketers/pt/docs/pba-raw-data-reports">Dados brutos</Anchor>

Os relatórios de dados brutos estão disponíveis no Data Locker. Os dados brutos oferecem insights aprofundados e incluem a fonte de mídia atribuída/responsável por trazer o usuário ao site.

* **Visitas à web:** visitas ao site
* **Eventos da web**: ações realizadas no site, como fazer uma assinatura ou comprar
* **Instalações auxiliadas pela web** e jornadas do **Caminho de conversão** são oferecidas na íntegra.
* As ferramentas de BI são usadas para analisar os dados para obter informações adicionais.
* <Anchor target="_blank" href="/marketers/pt/docs/pba-raw-data-reports">Saiba mais sobre dados brutos do PBA</Anchor>.

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/onboarding-guide-to-people-based-attribution">Guia de integração para PBA</Anchor>

<div data-zendesk-anchors="pba-principles=princ%C3%ADpios-de-pba 01ECF26CMJ8TB4ADT6VN277EMQ=princ%C3%ADpios-de-pba pba-analytics-dashboards-and-raw-data=pain%C3%A9is-anal%C3%ADticos-de-pba-e-dados-brutos 01ECF26CMJDA1HBC22DGRWY2EA=pain%C3%A9is-anal%C3%ADticos-de-pba-e-dados-brutos website-attribution=atribui%C3%A7%C3%A3o-do-site 01ECF26CMK0T5C9JKQ0SYMXQVM=atribui%C3%A7%C3%A3o-do-site webassisted-installs=instala%C3%A7%C3%B5es-auxiliadas-pela-web 01ECF26CMKDS16XWRBQ1SDAX2Q=instala%C3%A7%C3%B5es-auxiliadas-pela-web raw-data=dados-brutos 01ECF26CMM4KHX9W94DND4BY8C=dados-brutos h_01HE0Y2KTXS06WHN57MQ91AD09=veja-tamb%C3%A9m" />
