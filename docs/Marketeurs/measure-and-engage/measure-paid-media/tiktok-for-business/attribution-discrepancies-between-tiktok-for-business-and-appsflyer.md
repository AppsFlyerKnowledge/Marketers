---
title: Discordances dans l'attribution entre TikTok for Business et AppsFlyer
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-10-30T07:45:29Z'
  edited_at: '2024-11-04T15:10:01Z'
  id: 19733501619473
  locale: fr
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/fr/articles/19733501619473
---
> **En bref :** Découvrez les différences entre les modèles d'attribution de TikTok for Business et AppsFlyer.

## Aperçu

TikTok for Business et AppsFlyer, deux acteurs majeurs de l'écosystème de l'acquisition d'utilisateurs mobiles, utilisent des modèles d'attribution distincts. Cela peut entraîner des divergences entre les tableaux de bord de TikTok for Business et d'AppsFlyer. Nous collaborons étroitement avec TikTok for Business pour minimiser ces écarts, mais les annonceurs doivent être attentifs aux causes potentielles.

## Différences dans les modèles d'attribution

Le tableau ci-dessous indique les raisons possibles des divergences entre TikTok Ads Manager et les tableaux de bord AppsFlyer :

<table><thead><tr><th>Cause</th><th>Gestionnaire de publicités TikTok</th><th>AppsFlyer</th></tr></thead><tbody><tr><td><span id="click-attribution-lookback-window"></span><p><strong>Fenêtre de rétrospective d'attribution par clic</strong></p></td><td><p>La fenêtre par défaut est de 7 jours. Cependant, cela peut être configuré différemment pour les applications Android et celles passées à l'auto-attribution de TikTok (TikTok—SRN).</p></td><td><p>La fenêtre par défaut est de 7 jours. La fenêtre peut être réglée entre 1 et 30 jours. Assurez-vous de vous aligner sur la fenêtre d'attribution de TikTok.</p></td></tr><tr><td><span id="viewthrough-attribution-lookback-window"></span><p><strong>Fenêtre de rétrospective d'attribution après affichage</strong></p></td><td><p>La fenêtre par défaut est de 1 jour. Cependant, cela peut être configuré différemment pour les applications Android et celles passées à l'auto-attribution de TikTok (TikTok—SRN).</p></td><td><p>La fenêtre par défaut est de 1 jour. La fenêtre peut être réglée entre 1 et 48 heures. Assurez-vous de vous aligner sur la fenêtre d'attribution de TikTok.</p></td></tr><tr><td><span id="multichannel-sourceattribution"></span><p><strong>Attribution multi-source</strong></p></td><td><p>TikTok s'auto-attribue les installations indépendamment des autres sources média.</p></td><td><p>AppsFlyer utilise une attribution au dernier clic (en savoir plus sur le <a href="./appsflyer-attribution-model" target="_blank">modèle d'attribution d'AppsFlyer</a>).</p></td></tr><tr><td><span id="crossdevice-attribution"></span><p><strong>Attribution inter-appareils</strong></p></td><td><p>TikTok attribue les utilisateurs qui effectuent l'engagement et l'installation avec différents appareils, comme iOS, Android et ordinateur de bureau.</p></td><td><p>AppsFlyer attribue les utilisateurs effectuant l'engagement et l'installation sur le même appareil.</p></td></tr><tr><td><span id="different-time-zones"></span><p><strong>Différents fuseaux horaires</strong></p></td><td><p>Le <a href="https://ads.tiktok.com/help/article/time-zone" target="_blank">fuseau horaire de TikTok</a> (affiché à côté de la plage de dates) ne peut être ajusté. Il a été configuré lors de la création du compte publicitaire.</p></td><td><p>Le fuseau horaire par défaut d'AppsFlyer pour l'application est UTC+0. Pour s'aligner sur le fuseau horaire du gestionnaire d'événements TikTok, modifiez le fuseau horaire de l'application sur la <a href="./app-settings#localization-time-zone" target="_blank">page des paramètres de l'application</a>.</p></td></tr><tr><td><span id="ios-attribution"></span><p><strong>Attribution iOS</strong></p></td><td><p>Pour les applications iOS, le gestionnaire de publicités TikTok affiche uniquement les résultats d'attribution SKAN.</p></td><td><p>Pour les applications iOS, AppsFlyer affiche les résultats d'attribution SKAN, ainsi que l'attribution AppsFlyer pour les SRN et les SRN avancés, en plus des données SSOT dédupliquées. Seules les données SKAN sont censées correspondre sur les deux plateformes. </p></td></tr><tr><td><span id="in-app-event-attribution-periods"></span><p><strong>Périodes d'attribution des événements in-app</strong></p></td><td colspan="2"><p>L'attribution sur chaque plateforme peut différer en fonction des fenêtres de période depuis l'installation initiale :</p></td></tr><tr><td><span id="day-1-90"></span><p>Jour 1-90</p></td><td colspan="2"><p>Aucune divergence d'attribution. Les deux plateformes attribuent les événements in-app au moment de l'installation.</p></td></tr><tr><td><span id="day-91-180"></span><p>Jour 91-180</p></td><td rowspan="2"><p>Après 90 jours, les événements in-app ne sont pas signalés sur TikTok.</p></td><td><div><div><div>AppsFlyer attribue les événements in-app à l'heure de l'installation.</div></div></div></td></tr><tr><td><span id="day-180"></span><p>Jour 180+</p></td><td><div><div><div>En raison de la <a href="./user-level-data-retention#périodes-de-conservation-des-données-des-partenaires" target="_blank">politique de rétention des données de TikTok</a>, les événements in-app sont considérés comme organiques.</div></div></div></td></tr></tbody></table>

## Différences dans les installations

Dans certains cas, TikTok for Business inclut des installations qu'AppsFlyer rejette ou ne considère pas comme nouvelles installations.

### Campagnes de réengagement

Une campagne de réengagement peut amener les utilisateurs à ouvrir une application déjà installée (**réengagement**). Lorsque AppsFlyer reconnaît une installation précédente de l'application sur le même appareil, cette conversion est qualifiée de **réattribution**.

Les utilisateurs sont enregistrés sur AppsFlyer en tant que **nouvelles installations d'acquisition utilisateurs** s'ils installent l'application pour la première fois à partir d'une campagne de réengagement TikTok for Business. De plus, si les utilisateurs installent l'application après la <Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window">fenêtre de réattribution</Anchor> **désignée suivant l'installation initiale, ils sont également considérés comme de nouvelles acquisitions.**

En revanche, les installations qui se produisent **dans la fenêtre de réattribution définie** suivant l'installation initiale sont classées comme des réattributions. Ces installations sont visibles sur la page de retargeting d'AppsFlyer. Cependant, elles pourraient être considérées comme de nouvelles installations par TikTok for Business.

### Installations rejetées lors de l'utilisation des règles de Validation et de Protect360

<Anchor target="_blank" href="/marketers/fr/docs/implement-validation-rules-to-prevent-fraud">Les règles de validation</Anchor> et <Anchor target="_blank" href="/marketers/fr/docs/protect360-anti-fraud-guide">Protect360</Anchor> sont des fonctionnalités d'AppsFlyer qui ajoutent une protection en rejetant (bloquant) certains types d'installations. Lors de l'utilisation de ces fonctionnalités, les installations rejetées provenant de TikTok for Business sont bloquées par AppsFlyer tandis que TikTok for Business autocomptabilise ces installations.

> 📄 **Exemple**
>
> Jeff, le responsable de l'acquisition d'utilisateurs pour GreatApp, crée une campagne appelée SPNA, qui cible uniquement les hispanophones en Amérique du Nord. Pour s'assurer que cela fonctionne, Jeff définit une règle de validation qui accepte uniquement les utilisateurs du Canada et des États-Unis.
> Lorsqu'un utilisateur TikTok for Business d'Espagne clique et installe l'application, TikTok for Business auto-signale l'installation, tandis qu'AppsFlyer rejette l'installation qui ne passe pas la règle de validation.

## Réduction des écarts

Bien qu'il existe des différences dans les modèles d'attribution, dans certains cas, les écarts peuvent être réduits.

### Attribution par clic et par vue

AppsFlyer prend en charge à la fois l'attribution par clic et par vue. Pour réduire les écarts entre TikTok for Business et AppsFlyer, assurez-vous que les fenêtres de rétrospective après clic et après vue sont cohérentes avec celles définies par TikTok for Business.

> 📄 **Exemple**
>
> Supposons que la fenêtre de rétrospective des clics de TikTok for Business soit configurée sur AppsFlyer à 1 jour pour votre application `com.greatapp`, tandis que sur TikTok for Business, elle est réglée sur la valeur par défaut de 7 jours. Les utilisateurs qui cliquent sur l'annonce de Greatapp sur TikTok mais lancent l'application pour la première fois après 2 à 7 jours sont considérés comme utilisateurs organiques sur AppsFlyer, tandis que TikTok for Business déclare ces utilisateurs.

### Attribution des événements in-app

Les différences entre les plateformes peuvent aussi exister avec les événements post-installation (par exemple, les achats in-app), qui sont affichés sur TikTok for Business et AppsFlyer. Le tableau suivant décrit les raisons les plus courantes de ces différences et donne des conseils sur la façon de les réduire :

| Cause | Description | Conseil AppsFlyer |
| --- | --- | --- |
| <span id="selfattribution"></span>**Auto-attribution** | TikTok attribue toujours les installations et les événements à ses propres campagnes, tandis qu'AppsFlyer les attribue à la source d'acquisition. Ces événements sont indiqués comme des aides TikTok dans AppsFlyer. | Combinez les données brutes des conversions attribuées à TikTok avec les données brutes où TikTok est contributeur. |
| <span id="unmapped-events"></span>**Événements non mappés** | AppsFlyer reçoit les événements provenant du SDK, mais ceux-ci ne sont pas mappés à TikTok for Business et ne sont donc pas envoyés. | Assurez-vous de <Anchor target="_blank" href="/marketers/fr/docs/tiktok-for-business-advanced-srn-integration-setup#postback-dévènements-in-app">mapper avec TikTok for Business</Anchor> les événements in-app qui reflètent la qualité de l'utilisateur. |
| <span id="unsent-revenue"></span>**Revenus non envoyés** | AppsFlyer reçoit les revenus des événements générés par le SDK, mais ceux-ci ne sont pas envoyés à TikTok for Business. | Assurez-vous d'inclure les revenus lors du <Anchor target="_blank" href="/marketers/fr/docs/tiktok-for-business-advanced-srn-integration-setup#postback-dévènements-in-app">mappage des événements in-app TikTok for Business</Anchor>. |
| <span id="missing-event-values-on-tiktok"></span>**Valeurs d'événements manquantes sur TikTok for Business** | AppsFlyer envoie des paramètres et des valeurs à TikTok for Business dans le cadre du mappage des événements, à condition qu'ils aient les structures correctes. | Créez vos événements in-app dans le SDK conformément aux <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-event-structure">structures recommandées par AppsFlyer</Anchor> pour mapper entièrement les valeurs des événements avec TikTok for Business. |

<div data-zendesk-anchors="overview=aper%C3%A7u h_01HFXTVVZNJQJFAAR1F3HW1D5M=aper%C3%A7u differences-in-attribution-models=diff%C3%A9rences-dans-les-mod%C3%A8les-dattribution h_01HFXTVVZN79JX9E5PTXMPB8BS=diff%C3%A9rences-dans-les-mod%C3%A8les-dattribution differences-in-installs=diff%C3%A9rences-dans-les-installations h_01HFXTVVZNDQKNW85BBWR0PE2Z=diff%C3%A9rences-dans-les-installations reengagement-campaigns=campagnes-de-r%C3%A9engagement h_01HFXTVVZNA1R59KCA41H2YSBJ=campagnes-de-r%C3%A9engagement rejected-installs-when-using-validation-rules-and-protect360=installations-rejet%C3%A9es-lors-de-lutilisation-des-r%C3%A8gles-de-validation-et-de-protect360 h_01HFXTVVZNJVFHE0W5DTP5PDCG=installations-rejet%C3%A9es-lors-de-lutilisation-des-r%C3%A8gles-de-validation-et-de-protect360 01H890CZSYCTQZCAYAZP9TCBBF=exemple minimizing-discrepancies=r%C3%A9duction-des-%C3%A9carts h_01HFXTVVZNW9GZB8QYMR1KTNMN=r%C3%A9duction-des-%C3%A9carts clickthrough-and-viewthrough-attribution=attribution-par-clic-et-par-vue h_01HFXTVVZNN45WY997DK9K8WA4=attribution-par-clic-et-par-vue h_01HFRQMF6HTT84J4EDFXZMK7CP=exemple-1 inapp-event-attribution=attribution-des-%C3%A9v%C3%A9nements-in-app h_01HFXTVVZNG7TKQVY1229X594G=attribution-des-%C3%A9v%C3%A9nements-in-app" />
