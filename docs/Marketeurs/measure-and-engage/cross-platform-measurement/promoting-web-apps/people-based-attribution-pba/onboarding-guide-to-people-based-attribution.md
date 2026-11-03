---
title: Guide de l’attribution basée sur les utilisateurs (PBA)
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-10-01T08:00:26Z'
  edited_at: '2024-08-11T06:45:49Z'
  id: 360013821097
  locale: fr
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/fr/articles/360013821097
---
> **En bref :** Marche à suivre pour configurer la PBA

## Configurer la PBA

Pour mettre en pace la PBA, veuillez suivre les étapes décrites ci-dessous et dans le tableau qui suit.

* Contactez votre CSM AppsFlyer ou votre représentant commercial pour activer la PBA.
* Rassemblez dans un bundle de marques les propriétés numériques de la marque.
* Intégrez le SDK web à votre site web, et le SDK mobile à votre app.
* AppsFlyer collecte et attribue les données.
  * Les données sont extraites de différentes sources.
  * Les données enregistrées sont classées en points de contact et en événements.
  * Les événements sont attribués à la dernière visite non-directe sur le web qui a eu lieu les derniers 30 jours.
  * Les annonceurs peuvent choisir de définir certains événements comme étant des événements de conversion. Par exemple, les achats. Les événements de conversion sont analysés dans les tableaux de bord.
  * Les données brutes sont utilisées pour obtenir des analyses de données personnalisées.
* Analysez les parcours des clients pour optimiser les campagnes

### Étapes de configuration de la PBA

Avant de commencer, contactez votre CSM AppsFlyer ou votre représentant commercial pour activer la PBA.  Lancez ensuite l’installation. Les étapes de la configuration sont détaillées dans le tableau. Téléchargez cette  feuille de calcul/span> <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQkYW2k1VUFugYLZ7Xv5esBL4kxfoNXMw0wyfRvoNGHdgiyZS5K5BE4seR2bjocK5HAArj97nlqF4By/pub?output=xlsx">pour suivre votre progression et ne rien oublier.</Anchor>

**Recommandation :** Implémentez le <Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid">CUID</Anchor>  à la fois dans l'application et dans votre site web. AppsFlyer reçoit le CUID lorsqu'un utilisateur s'enregistre ou se connecte.

<table><thead><tr><th> </th><th>Responsable</th><th>Actions</th><th>Remarques</th></tr></thead><tbody><tr><td><span id="1"></span><p> 1</p></td><td><p>Annonceur </p></td><td><ul><li> <span><a href="./adding-an-app-to-appsflyer" target="_blank">Ajoute une application web</a> à votre compte AppsFlyer. L'app web spécifie l'URL du site dont vous souhaitez mesurer le trafic et </span> elle est utilisée pour empêcher l'<a href="./pba-media-source-attribution-rules" target="_blank">auto-attribution</a>.</li><li> <span><a href="./pba-brand-bundles-and-settings" target="_blank">Configure les bundles de marque</a> ; celles-ci rassemblent les propriétés numériques d'une marque (les apps mobile et l’app web).</span> </li><li>Indique les <a href="./pba-brand-bundles-and-settings#domain-exclusion" target="_blank">domaines qui sont exclus</a>.</li></ul></td><td><ul><li><span>Les analyses et les rapports sont regroupés au sein de la marque.</span></li></ul></td></tr><tr><td><span id="2"></span><p> 2</p></td><td> Webmaster </td><td><ul><li>Installe le <a href="./pba-web-sdk-integration-guide" target="_blank">SDK Web</a> sur le site défini par l'app web. </li><li>Configure le SDK web pour :  <ul><li>Enregistrer les visites</li><li>Enregistrer les événements</li><li><mark> Définir le <a href="./pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid" target="_blank">CUID</a> </mark></li><li>Implémente des tests via l'<a href="./test-pba-web-sdk-integration" target="_blank">outil de test SDK</a> </li></ul></li></ul></td><td><ul><li><span>Le SDK enregistre les visites et les événements.</span></li><li>L'intégration est entièrement prise en charge par Google Tag Manager (GTM), Adobe ou Tealium<span></span> </li><li> <strong>Obligatoire :</strong>  Appeller SetCustomerUserID() immédiatement après l'enregistrement ou la connexion d'un utilisateur. Si vous n'avez pas de CUID, parlez-en avec votre CSM pour trouver une solution. </li></ul></td></tr><tr><td><span id="3"></span><p>3</p></td><td><p>Annonceur</p></td><td><p>Vérifier que le webmaster a bien utilisé l'<a href="./test-pba-web-sdk-integration" target="_blank">outil de test du SDK</a> pour s’assurer que le site web auquel le SDK est associé réalise les actions suivantes :</p><ul><li>Enregistrement des visites</li><li>Enregistrement des événements</li><li>Définition du CUID</li></ul></td><td><p><mark>Annonceur attention : ne poursuivez pas tant que cette étape n'a pas été complétée.  </mark></p></td></tr><tr><td><span id="4"></span><p>4 </p></td><td><p>Développeur et annonceur</p></td><td><p>[Facultatif] <a href="./web-server-to-server-events-api-for-pba-web-s2s" target="_blank">API de serveur à serveur web</a></p></td><td>Rapporte les événements liés au web, comme le renouvellement automatique des abonnements.</td></tr><tr><td><span id="5"></span><p>5</p></td><td><p>Annonceur</p></td><td><ul><li> <span>Marquer</span> les événements de conversion : <ul><li><span><a href="./pba-brand-bundles-and-settings#web-event-settings" target="_blank">Evénements web</a></span></li><li><span>[Facultatif] <a href="./pba-brand-bundles-and-settings#inapp-event-settings" target="_blank">Événements in-app mobile</a>.</span></li></ul></li></ul></td><td><ul><li><span>Attendre que le traitement quotidien\* soit terminé avant de réaliser cette action.</span></li></ul></td></tr><tr><td><span id="6"></span><p> 6</p></td><td><p>Annonceur</p></td><td><p>Commencer à utiliser les tableaux de bord</p></td><td><ul><li><a href="./pba-website-attribution-dashboard" target="_blank">Attribution de site web</a></li><li><a href="./pba-web-assisted-installs" target="_blank">installations web-assistées</a></li></ul></td></tr><tr><td><span id="7"></span><p> 7</p></td><td>Annonceur</td><td><a href="./pba-raw-data-reports#setting-up-pba-reports-in-data-locker" target="_blank">Configurer Data Locker</a></td><td><p>Donne accès aux rapports de données brutes de la PBA qui incluent les points de contact, les événements standard et de conversion, ainsi que les rapports propres aux installations web-assistées.</p></td></tr><tr><td><span id="8"></span><p>8</p></td><td><p>Annonceur</p></td><td><p>[Facultatifl]<br/>Commence à utiliser les <a href="./pba-raw-data-reports" target="_blank">données brutes</a></p></td><td><p>Les données sont disponibles après le traitement quotidien\*.</p></td></tr><tr><td colspan="4"><span id="-due-to-processing-data-is-available-10-hours-after-midnight-utc-on-the-day-of-the-event-meaning-mondays-events-are-available-tuesday-1000-utc"></span>\* En raison du temps nécessaire au traitement, les données sont disponibles le jour de l’événement, 10 heures après minuit (UTC). Les événements du lundi seront par exemple disponibles le mardi à 10:00 UTC.  </td></tr></tbody></table>

## Acquisition de données de la PBA via SDK/API

|  | Plateforme web | Plateforme mobile (app) |
| --- | --- | --- |
| SDK | <Anchor target="_blank" href="/marketers/fr/docs/pba-web-sdk-integration-guide">Web</Anchor><ul><li>SDK de balise JavaScript installé sur le site web</li><li>Rapporte les visites sur le site, ainsi que les événements web</li></ul> | <Anchor target="_blank" href="/marketers/fr/docs/integrate-the-appsflyer-sdk">Mobile</Anchor><ul><li>SDK d'app intégré à iOS, Android, Unity, etc.</li><li>Rapporte les installations de l'app et les actions d'utilisateur qui se produisent dans l'app</li></ul> |
| API de serveur à serveur | <Anchor target="_blank" href="/marketers/fr/docs/web-server-to-server-events-api-for-pba-web-s2s">Serveur à serveur Web</Anchor><ul><li>Rapporte les événements se produisant dans les serveurs en back-end (et non sur le web)</li><li>Exemple : renouvellement d'un abonnement</li></ul> | <Anchor target="_blank" href="/marketers/fr/docs/server-to-server-events-api-for-mobile-s2s-mobile">Serveur à serveur mobile</Anchor><ul><li>Rapporte les événements se produisant dans les serveurs en backend (et non dans l'app)</li><li>Exemple : renouvellement d'un abonnement</li></ul> |

<div data-zendesk-anchors="setting-up-pba=configurer-la-pba 01H8V1XPAHGFVJRKM56S2ZQTBD=configurer-la-pba pba-setup-steps=%C3%A9tapes-de-configuration-de-la-pba 01ECF26CMN668ZZV6XNZA3W692=%C3%A9tapes-de-configuration-de-la-pba pba-dataacquisition-via-sdkapi=acquisition-de-donn%C3%A9es-de-la-pba-via-sdkapi 01H8V1XPAH23BV25ZCMFR7MM9Q=acquisition-de-donn%C3%A9es-de-la-pba-via-sdkapi" />
