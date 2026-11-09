---
title: People-Based Attribution (PBA)—Vue d'ensemble
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
  edited_at: '2024-02-22T07:54:54Z'
  id: 360002274017
  locale: fr
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/fr/articles/360002274017
---
> **En bref :** l'attribution basée sur les personnes (PBA) offre une vue d'ensemble du parcours des clients à travers différents canaux, plate-formes et appareils.

<Image align="center" alt="PBANoSilos_us-en.gif" src="https://files.readme.io/1ac3614eb1b9d4c01bffbe904f1a060d1facd681ff32c274b12f0a15612a2e4a-360009359798.gif" />

<div id="pba-principles" />

## Les principes de la PBA

* La PBA consolide les données des sites web et des apps mobile pour offrir une vision globale des performances d'une campagne, et ce d'après les propriétés numériques d'une marque. Les annonceurs utilisent la PBA pour comprendre les parcours client en fonction des individus plutôt qu'en fonction des appareils.
* Les données de la PBA - présentes dans les tableaux de bord de PBA et dans les rapports de données brutes - sont utilisées pour les analyses marketing et l'optimisation des campagnes.
* Les données relatives aux visites de site et aux événements d'utilisateur sont collectées via un <Anchor target="_blank" href="/marketers/fr/docs/pba-web-sdk-integration-guide">SDK et/ou une API</Anchor>.
* Pour chaque visite sur un site : la source média responsable de la visite est déterminée. Tout événement résultant (conversion) est <Anchor target="_blank" href="/marketers/fr/docs/pba-media-source-attribution-rules">attribué</Anchor> à la source média à l'origine de la visite.

<div id="pba-analytics-dashboards-and-raw-data" />

### Tableaux de bord d'analyses et données brutes de la PBA

* Les données PBA sont présentées via des tableaux de bord et des rapports d'analyse :
  * Attribution de site web
  * Installations web-assistées
  * Chemins de conversion
  * Rapports de données brutes
* Les données des tableaux de bord sont <Anchor target="_blank" href="/marketers/fr/docs/using-pba-dashboards">filtrées et regroupées</Anchor> selon certaines dimensions telles que la plate-forme mobile, le canal média ou le type de média, ce qui vous permet de décomposer et analyser les données.

<div id="website-attribution" />

### <Anchor target="_blank" href="/marketers/fr/docs/pba-website-attribution-dashboard">Attribution de site web</Anchor>

<Image align="center" alt="WebsiteAttributionTable_us-en.jpg" src="https://files.readme.io/327a4830ca20ba9067bb9f7a5e5264908fd918ada9462261befcef2f48fd0fd0-360013135398.jpg" />

Analysez les sources de trafic web et les campagnes de marketing qui génèrent des visites et des conversions sur votre site. Découvrez les différences de performances jusqu'au niveau de la publicité. Prend en charge l'ensemble des paramètres AppsFlyer de requête de lien sans avoir à rediriger les utilisateurs vers les serveurs AppsFlyer.

<div id="web-assisted-installs" />

### <Anchor target="_blank" href="/marketers/fr/docs/pba-web-assisted-installs">Installations web-assistées</Anchor>

<Image align="center" alt="AppsFlyer-Web-to-App_us.en.gif" src="https://files.readme.io/4a278b57379c999d80fd7f1dfea750049f56c03ed32051f9af92577b2a51742a-360009705058.gif" />

Les installations web-assistées vous permettent d'examiner l'impact et les résultats de vos actions marketing Web sur le nombre d'installations d'app mobile.

* Découvrez comment les différents types de médias (payants, propres, gagnés), canaux média (direct, réseaux sociaux, recherche organique) et sources média agissent pour contribuer à générer des acquisitions d'utilisateur.
* Attribuez des installations organiques en fonction de vos actions sur le Web.
* Découvrez dans quelle mesure les actions que vous déployez sur le Web génèrent des installations non organiques.

<div id="raw-data" />

### <Anchor target="_blank" href="/marketers/fr/docs/pba-raw-data-reports">Données Brutes</Anchor>

Les données brutes offrent des informations détaillées, elles indiquent notamment la source média attribuée qui a déclenché l'arrivée de l'utilisateur sur le site web.

* **Visites web :** visites sur le site web
* **Événements web** : actions effectuées sur le site, comme une inscription ou un achat
* Les parcours **Installations web-assistées** et **Chemin de conversion** sont complets.
* Les outils de BI sont utilisés pour analyser les données afin d'obtenir des éléments supplémentaires.

<div id="see-also" />

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/onboarding-guide-to-people-based-attribution">Guide de démarrage pour la PBA</Anchor>

<div data-zendesk-anchors="pba-principles=les-principes-de-la-pba 01ECF26CMJ8TB4ADT6VN277EMQ=les-principes-de-la-pba pba-analytics-dashboards-and-raw-data=tableaux-de-bord-danalyses-et-donn%C3%A9es-brutes-de-la-pba 01ECF26CMJDA1HBC22DGRWY2EA=tableaux-de-bord-danalyses-et-donn%C3%A9es-brutes-de-la-pba website-attribution=attribution-de-site-web 01ECF26CMK0T5C9JKQ0SYMXQVM=attribution-de-site-web webassisted-installs=installations-web-assist%C3%A9es 01ECF26CMKDS16XWRBQ1SDAX2Q=installations-web-assist%C3%A9es raw-data=donn%C3%A9es-brutes 01ECF26CMM4KHX9W94DND4BY8C=donn%C3%A9es-brutes h_01HE0Y2KTXS06WHN57MQ91AD09=%C3%A0-consulter-%C3%A9galement" />
