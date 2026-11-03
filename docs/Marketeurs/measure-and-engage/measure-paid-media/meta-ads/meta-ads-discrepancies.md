---
title: Inexactitudes dans les Meta ads
metadata:
  keywords:
    - Facebook
    - Advertisers
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
  created_at: '2021-11-09T10:10:54Z'
  edited_at: '2023-12-31T08:41:33Z'
  id: 4410481130641
  locale: fr
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/fr/articles/4410481130641
---
> **En bref :** découvrez les différences entre les modèles d'attribution des Meta ads et d'AppsFlyer.

## Discordances entre les Meta ads et AppsFlyer

En tant qu'acteurs majeurs dans l'écosystème d'acquisition des utilisateurs mobile, AppsFlyer et Meta ads diffèrent dans leurs modèles d'attribution. Cette situation peut entraîner des discordances entre les tableaux de bord de Meta ads et d'AppsFlyer.

Même si nous travaillons en étroite collaboration avec Meta ads pour réduire ces discordances, les annonceurs doivent être conscients des conséquences suivantes.

### Comment détecter les écarts entre AppsFlyer et Meta ads

Comparez les événements répertoriés dans le **Gestionnaire d'événements** de Meta ads à ceux des rapports AppsFlyer. Si le nombre d'événements varie considérablement, cela peut indiquer une anomalie.

## Discordances dans les modèles d'attribution

<table><thead><tr><th>Cause</th><th>Meta Ads</th><th>AppsFlyer</th></tr></thead><tbody><tr><td><span id="click-attribution-lookback-window"></span><p><strong>Clic sur la fenêtre rétrospective d'attribution</strong></p></td><td><p>7 jours (sachez que <a href="https://www.facebook.com/business/help/395050428485124?id=428636648170202" target="_blank">dans certains cas précis la valeur par défaut est différente</a>).</p></td><td><p>1-30 jours. Assurez-vous de définir sur 7 jours avec Meta ads.</p></td></tr><tr><td><span id="viewthrough-attribution-lookback-window"></span><p><strong>Fenêtre rétrospective d'attribution post vue</strong></p></td><td><p>1 jour (sachez que <a href="https://www.facebook.com/business/help/395050428485124?id=428636648170202" target="_blank">dans certains cas précis la valeur par défaut est différente</a>).</p></td><td><p>1 jour par défaut, mais peut être configuré de 1 à 48 heures (conserver cette valeur par défaut)</p></td></tr><tr><td><span id="multichannel-sourceattribution"></span><p><strong>Attribution<br/>de sources multi-canaux</strong></p></td><td><p>Meta ads attribue les installations de manière indépendante sans se soucier des autres sources média. </p></td><td><p>AppsFlyer utilise l'attribution du dernier clic (plus d'informations sur l'attribution AppsFlyer disponibles <a href="./appsflyer-attribution-model" title="Modèle d'attribution AppsFlyer" target="_blank">ici</a>).</p></td></tr><tr><td><span id="crossdevice-attribution"></span><p><strong>Attribution inter-appareils</strong></p></td><td><p>Meta ads attribue ses utilisateurs qui cliquent puis installent sur différents appareils, par exemple iOS / Android / ordinateur de bureau.</p></td><td><p>AppsFlyer attribue des appareils uniques, qui effectuent à la fois l'engagement et l'installation</p></td></tr><tr><td><span id="different-time-zones"></span><p><strong>Différents fuseaux horaires</strong></p></td><td><p>Le fuseau horaire par défaut des Meta ads est PST. Veillez à le modifier <a href="https://www.facebook.com/business/help/754049591334898" target="_blank">dans Meta Ads Manager</a> pour qu'il corresponde à celui qui a été défini dans les paramètres de l'app du côté d'AppsFlyer.</p></td><td><p>Le fuseau horaire par défaut d'AppsFlyer est UTC + 0. Vous pouvez modifier le fuseau horaire défini pour l'app sur la page <a href="./app-settings#localization-time-zone" target="_blank">paramètres de l'app</a> afin de correspondre au fuseau horaire défini dans Meta Ads Manager.</p></td></tr><tr><td><span id="google-install-referrer"></span><p><strong>Référent d'installation Google</strong></p></td><td colspan="2"><p>Lorsqu'une installation dénuée d'ID d'annonceur a été attribuée à Meta Ads à l'aide du référent d'installation Google Play, AppsFlyer ne la rapportera pas à Meta Ads. Cela entraînera des résultats différents car elle s’affichera chez AppsFlyer, mais pas dans Meta Ads.</p></td></tr><tr><td><span id="AEM-for-data-sharing"></span><p><strong>AEM pour le partage des données</strong></p></td><td colspan="2"><p><span>Pour <a href="./meta-ads-aggregate-event-measurement-aem-for-ios#aem-data-sharing" target="_blank">le partage de données AEM</a>, Meta ads reçoit tous les événements de conversion. Ces attributions supplémentaires n'apparaissent pas dans AppsFlyer. Les écarts de résultat entre les deux plateformes sont donc plus importants en ce qui concerne le nombre d'installations (la majorité des cas), et le nombre d'événements in-app, ce qui inclut les sessions.</span></p></td></tr></tbody></table>

## Attribution post clic et post vue

AppsFlyer prend en charge aussi bien l'attribution post clic que l'attribution post vue. Pour éviter les écarts entre les Meta ads et AppsFlyer, faites en sorte que les fenêtres de réattribution post-clic et post-vue soient en accord avec les fenêtres par défaut des Meta ads.

Par défaut, la fenêtre rétrospective post-clic des Meta ads est définie sur 7 jours. Même si [dans certains cas la valeur par défaut est différente](https://www.facebook.com/business/help/395050428485124?id=428636648170202), nous vous conseillons de définir la fenêtre rétrospective post-clic sur 7 jours dans AppsFlyer, et ce afin de couvrir toutes les options par défaut des Meta Ads.

Pour comparer les fenêtres d'attribution post clic et post vue sur Meta ads avec celles d'AppsFlyer, merci de consulter le site Meta ads. Nous vous recommandons de configurer les fenêtres d'attribution sur AppsFlyer d'après les valeurs de Meta ads, telles qu'indiquées dans la capture d'écran suivante :

![Facebook_Discrepancies.png](https://support.appsflyer.com/hc/article_attachments/4411036047505)

> 📄 **Exemple**
>
> Supposons que la fenêtre rétrospective de clic de Meta ads est définie sur 1 jour pour votre app com.greatapp sur AppsFlyer, mais qu'elle est de 7  jours par défaut sur Meta ads. Les utilisateurs qui cliquent sur l'annonce de Greatapp sur Facebook, mais qui lancent l'application pour la première fois au bout de 2 à 7 jours, sont attribués en tant qu'utilisateurs organiques sur AppsFlyer, alors que Meta ads déclare automatiquement ces utilisateurs.

## Différences de médias restreints

Depuis le 28 octobre 2021, les données d'attribution des utilisateurs apportées par l'attribution post vue (VTA) sont <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">limitées et ne sont pas disponibles pour les annonceurs</Anchor>.Depuis le 29 octobre 2021, les restrictions s'appliquent aux utilisateurs dont l'attribution se fait à la fois par vue et par clic. Les rapports agrégés ne sont pas concernés par cette mesure.

Comme Meta ads ne transmet aucune données de niveau utilisateur, il peut arriver que AppsFlyer n'attribue pas les impressions ou les clics de conversions à Meta ads.

> 📄 **Exemple**
>
> * Un utilisateur consulte ou clique sur une publicité dans Facebook pour AwesomeApp. Plus tard, il consulte et clique sur une publicité GreatAdNetwork pour AwesomeApp, puis il l'installe.
> * Meta ads revendique la conversion puisqu’elle a eu lieu durant sa fenêtre rétrospective.
> * AppsFlyer attribue la conversion à GreatAdNetwork, car ils ont eu le dernier engagement avant l'installation.
> * Comme les données brutes de Meta ads sont limitées, AppsFlyer ne verra pas Meta ads comme un réseau d'aide à la conversion.

Toutefois, pour l'attribution posts clic, si l'annonce dirige les utilisateurs vers le Google Play Store, les champs d'attribution sont disponibles pour les annonceurs dans le référent d'installation Google. Les champs fournis via le référent peuplent les rapports de données brutes AppsFlyer mis à votre disposition et permettent à AppsFlyer d'attribuer des utilisateurs qui n'ont pas d'identifiant publicitaire (option LAT activée).

## Discordances entre les événements in-app

Les différences entre les plateformes peuvent aussi se présenter avec les événements en post-installation (ex : achats in-app) qui s'affichent sur Meta ads et sur AppsFlyer. Le tableau suivant détaille les principales causes qui provoquent ces décalages, et propose des solutions pour les minimiser :

| Cause | Description | Conseil d'AppsFlyer |
| --- | --- | --- |
| <span id="selfattribution"></span>**Auto-attribution** | Meta ads attribue toujours les événements aux campagnes qui les ont générés, tandis que AppsFlyer attribue ces événements à la source d'acquisition. | Les installations et événements que Facebook s'auto-attribue à tort portent la mention <Anchor target="_blank" href="/marketers/fr/docs/measure-assisted-installs#le-reporting-des-installations-assistées">assistances dans AppsFlyer</Anchor>.  <br />Combinez les données brutes de conversions attribuées par Meta ads avec les données brutes où Meta ads est le contributeur. |
| <span id="different-lifetime-definition"></span>**Définition différente de la durée de vie** | La durée lifetime des utilisateurs monte à 7 jours sur Meta ads, ce qui signifie que Meta ads ne montre pas les événements qui se produisent plus de 7 jours après le clic sur une publicité.  <br />La durée Lifetime des utilisateurs Meta ads sur AppsFlyer est fixée à 180 jours. | Lorsque vous évaluez la valeur des utilisateurs à partir des campagnes Meta ads remontant à plus de 7 jours, utilisez les données d'AppsFlyer pour obtenir de meilleurs résultats. |
| <span id="unmapped-events"></span>**Événements non mappés** | AppsFlyer reçoit les événements provenant du SDK, mais ils ne sont pas mappés sur Meta ads, et ne sont donc pas envoyés. | Assurez-vous <Anchor target="_blank" href="/marketers/fr/docs/meta-ads-in-app-event-mapping">de mapper à Meta ads</Anchor> tous les événements in-app qui indiquent la qualité des utilisateurs. |
| <span id="unsent-revenue"></span>**Revenu non envoyé** | AppsFlyer obtient le revenu des événements générés par le SDK, mais ils ne sont pas envoyés à Meta ads. | Vérifiez que les cases **Envoyer les revenus** des événements in-app sont bien cochées, par exemple l'événement d'achat dans la capture d'écran ci-dessous. |
| <span id="missing-event-values-on-facebook"></span>**Valeurs d'évenement manquantes dans Meta ads** | AppsFlyer envoie les paramètres et les valeurs à Meta ads dans le cadre du mappage des événements, s'ils possèdent les structures appropriées. | Créez vos événements in-app de SDK conformément aux <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-event-structure">structures recommandées par AppsFlyer</Anchor> pour assurer le mappage intégral des valeurs d'événement avec Meta ads. |

## Installation à partir des campagnes de réengagement dans Mon tableau de bord AU

Une campagne de réengagement peut amener les utilisateurs à ouvrir une application déjà installée (**réengagement**). Autrement, si AppsFlyer reconnaît qu'une installation précédente de l'application existait sur le même appareil, il peut assimiler cette conversion à une **réattribution**.

Si, lors d'une campagne de réengagement, Meta ads cible de **nouveaux utilisateurs** ou des utilisateurs qui ont installé l'application pour la première fois **après un délai excédant** **<Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window">la fenêtre de réattribution</Anchor>** définie après l'installation initiale, ces utilisateurs sont enregistrés en tant que **nouvelles installations d'acquisition utilisateur sur AppsFlyer** , appartenant à des campagnes de réengagement sur Meta ads.

En revanche, les installations intervenant **pendant la fenêtre de réattribution définie** à la suite de l'installation initiale, sont considérées comme des réattributions et apparaissent sur la page de retargeting d'AppsFlyer, alors qu'elles peuvent apparaître comme de nouvelles installations sur Meta ads.

> 📘 **Note**
>
> Alors que Meta ads affiche toutes les installations d'une campagne de retargeting au même endroit, sur le tableau de bord AppsFlyer, les installations sont réparties entre la page Présentation (nouvelles installations) et la page Retargeting (réattribution et réengagements).

## Attribution inter-appareils

Rapports Meta ads sur l'attribution inter-appareils. Cette opération peut parfois entraîner des problèmes lorsqu'une campagne pour une plate-forme (iOS/Android) montre des installations sur une autre plateforme.

> 📄 **Exemple**
>
> Sur son téléphone Android, Linda clique sur une annonce mobile de GreatApp dans Facebook. Facebook enregistre le clic effectué par Linda dans le cadre de la campagne d'origine ciblée Android «Android / Femmes». Linda décide d'installer GreatApp sur son iPad personnel. Au premier lancement, AppsFlyer demande à Meta ads l'origine de cette installation iOS, et Meta ads répond en indiquant la campagne « Android / Femmes ».

## Règles de validation et Protect360

Si vous utilisez les <Anchor target="_blank" href="/marketers/fr/docs/implement-validation-rules-to-prevent-fraud">règles de validation d'AppsFlyer</Anchor>, les résultats peuvent différer entre AppsFlyer et Meta ads lorsque des installations provenant de Meta ads sont rejetées. Dans ces cas précis, Facebook s'auto-attribue ces installations, tandis que AppsFlyer rejette les mêmes installations.

De même, si vous utilisez la solution antifraude AppsFlyer, Protect360, vous pouvez constater des installations, puisque Meta ads s'auto-attribue tandis que AppsFlyer rejette.

> 📄 **Exemple**
>
> Jeff, directeur AU de GreatApp, crée une campagne appelée SPNA, qui cible uniquement les hispanophones basés en Amérique du Nord. Pour ce faire, Jeff définit une règle de validation qui accepte exclusivement les utilisateurs basés au Canada et aux États-Unis.
> Lorsqu'un utilisateur Meta ads résidant en Espagne clique et installe l'app, Meta ads s'auto-attribue l'installation, tandis qu'AppsFlyer rejette toutes les installations qui ne suivent pas la règle de validation.

## Écarts liés au SDK

Il peut arriver que des <Anchor target="_blank" href="/marketers/fr/docs/meta-ads-faq#who-needs-facebooks-sdk">annonceurs implémentent à la fois des SDK AppsFlyer et Facebook</Anchor>. Cela peut entraîner des divergences de résultat, tant pour les événements in-app que pour les événements in-app. Meta Ads ne redivise pas pas les événements in-app rapportés par les deux SDK à la fois. Cela signifie que Meta Ads peut rapporter des revenus ou d'autres événements de manière incorrecte.

* Utilisez l'une des méthodes suivantes pour éviter la création de rapports dupliqués sur les évènements in-app dans Meta ads :
  * Ne configurez pas les évènements dans le SDK Facebook.
  * Désactivez le <Anchor target="_blank" href="/marketers/fr/docs/meta-ads-in-app-event-mapping">mappage des évènements in-app Meta ads</Anchor> à partir d'AppsFlyer.

<div data-zendesk-anchors="facebook-ads-discrepancies-with-appsflyer=discordances-entre-les-meta-ads-et-appsflyer 01H890CZSXPMK0BDMC4202HNYM=discordances-entre-les-meta-ads-et-appsflyer detect-a-discrepancy-between-appsflyer-and-facebook=comment-d%C3%A9tecter-les-%C3%A9carts-entre-appsflyer-et-meta-ads 01H890CZSXGHVBH21SQA0671JQ=comment-d%C3%A9tecter-les-%C3%A9carts-entre-appsflyer-et-meta-ads differences-in-attribution-models=discordances-dans-les-mod%C3%A8les-dattribution 01H890CZSX8M6VGGREYX4W2X37=discordances-dans-les-mod%C3%A8les-dattribution clickthrough-and-viewthrough-attribution=attribution-post-clic-et-post-vue 01H890CZSX40JDGY8P8AQ4CYGS=attribution-post-clic-et-post-vue 01H890CZSXRD7PCZBK52GW7QE9=exemple restricted-media-discrepancies=diff%C3%A9rences-de-m%C3%A9dias-restreints 01H890CZSX5WFX5Q0RNSG01GFH=diff%C3%A9rences-de-m%C3%A9dias-restreints 01H890CZSX567CQ3ZWZS5F05XW=exemple-1 inapp-events-differences=discordances-entre-les-%C3%A9v%C3%A9nements-in-app 01H890CZSXKC5JKK9051MC0VY6=discordances-entre-les-%C3%A9v%C3%A9nements-in-app installs-from-reengagement-campaigns-in-my-ua-dashboard=installation-%C3%A0-partir-des-campagnes-de-r%C3%A9engagement-dans-mon-tableau-de-bord-au 01H890CZSYE21K7PBQK4PNMGJR=installation-%C3%A0-partir-des-campagnes-de-r%C3%A9engagement-dans-mon-tableau-de-bord-au 01H890CZSY7TRCA4NVKSVPY7DB=note crossdevice-attribution::77a37a1f=attribution-inter-appareils 01H890CZSYS8QKEAF6799SBS8J=attribution-inter-appareils 01H890CZSY2Z3S6E9R5MYC1CHX=exemple-2 validation-rules-and-protect360=r%C3%A8gles-de-validation-et-protect360 01H890CZSYDHZE4V0ZWTT8V0EJ=r%C3%A8gles-de-validation-et-protect360 01H890CZSYCTQZCAYAZP9TCBBF=exemple-3 sdk-related-discrepancies=%C3%A9carts-li%C3%A9s-au-sdk 01H890CZSYVFPQP0SKNPWMPB1R=%C3%A9carts-li%C3%A9s-au-sdk" />
