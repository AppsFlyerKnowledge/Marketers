---
title: Rapport sur les coûts publicitaires par clic
metadata:
  keywords:
    - eCPI
    - clicks
    - ROI
    - Advertisers
    - Agencies
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2020-05-20T10:50:58Z'
  edited_at: '2024-05-22T09:36:41Z'
  id: 360008981698
  locale: fr
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/fr/articles/360008981698
---
> **En bref :** Affichage des données de coût agrégées pour chaque clic sur une annonce, telles qu’elles sont signalées par les réseaux publicitaires.

## Rapports de base sur les coûts

Les données de coût sont communiquées à AppsFlyer par :

* Réseaux publicitaires : chaque fois qu’un utilisateur clique sur une annonce. L’affichage du coût de la campagne dans AppsFlyer aide les annonceurs à mesurer le retour sur investissement et à prendre des décisions budgétaires appropriées.
  * Le coût est indiqué sur le <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">lien d’attribution</Anchor> à l’aide du modèle de coût par installation (CPI).
  * Lorsque vous envoyez le lien d’attribution au réseau publicitaire, assurez-vous que le réseau publicitaire <Anchor target="_blank" href="/partners/fr/docs/cost-reporting-on-the-attribution-link-for-ad-networks">ajoute les paramètres de rapport sur les coûts</Anchor>.
* <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview">Options avancées pour l’agrégation des coûts</Anchor>, y compris par API et importation de coûts (téléchargement de fichiers CSV).

  * Les méthodes d'agrégation des coûts prennent en charge les modèles de coûts utilisés par le partenaire, y compris le CPI, le CPA, le CPC et le CPM.

<div id="viewing-ad-cost-by-click" />

<Accordion title="Affichage du coût de l’annonce par clic">

Les données de coût par clic sont agrégées et disponibles pour consultation en temps réel (maximum jusqu’à 2 heures après le clic) dans les tableaux de bord AppsFlyer, les rapports de performance et les rapports de données brutes.

Dans le ***tableau de bord Vue d’ensemble,** le rapport sur les performances agrégées* contient les données sur le coût, les clics, les impressions, le retour sur investissement et l’eCPI moyen.

[![CostReporting.jpg](https://files.readme.io/5d4dbe5dc74fd0915924518f76c63e379f0b072b5d5dbb7a7f92455b83e33a12-17313191631633.jpg)](https://files.readme.io/5d4dbe5dc74fd0915924518f76c63e379f0b072b5d5dbb7a7f92455b83e33a12-17313191631633.jpg)

Les rapports de performance et de données brutes sont également disponibles <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">en téléchargement</Anchor>.

</Accordion>

<div id="ad-networks-providing-cost-by-click-data" />

<Accordion title="Les réseaux publicitaires fournissant des données de coût par clic">

Pour les réseaux publicitaires qui fournissent le coût par clic, les mesures prises en charge sont celles contenues dans le clic.

**Les réseaux publicitaires qui fournissent le coût par clic sont les suivants :**

* AdAction
* Aura de Unity
* Blind Ferret
* Chartboost
* Cross Install
* Digital Turbine
* Fyber
* HangMyAds
* ironSource
* Criteo DSP (Manage)
* Mintegral
* TikTok pour Business
* Unity Ads
* Vungle
* <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTMPZ9anfZoFBelK2bsBUoHG9n4YE3WxpXOayDF_wI8vyYClM6_6yXelFCZ3khwhd9Z_5Louxd4VVgx/pub?gid=0&single=true&output=csv">Voir la liste complète des réseaux publicitaires qui collectent le coût par clic</Anchor>

</Accordion>

<div id="limitations" />

<Accordion title="Restrictions">

Limites du coût par clic :

* Le coût est uniquement indiqué à l’aide du modèle de coût par installation (CPI). Les autres modèles, notamment CPA, CPC et CPM, ne sont pas pris en charge.
* <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns">Les réseaux autodéclarés</Anchor> (SRN) ne déclarent pas les coûts par clic.
* Les données de clic sont immuables. Par conséquent, une fois que ces données sont connectées à AppsFlyer, elles ne peuvent pas être modifiées, même s’il y a des erreurs dans les rapports de ces données.

</Accordion>

<div data-zendesk-anchors="basic-cost-reporting=rapports-de-base-sur-les-co%C3%BBts h_01HX954Y5X7ZP2VMB5W2XAMCR0=rapports-de-base-sur-les-co%C3%BBts h_01HX954Y5XTRRQV4JHA5XX1AQ0=viewing-ad-cost-by-click h_01HX954Y5XV8M2R2VDAV34641R=ad-networks-providing-cost-by-click-data h_01HX954Y5X84BM7F8TGQRDPBTS=limitations" />
