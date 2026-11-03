---
title: Modèle d'attribution AppsFlyer
metadata:
  keywords:
    - Attribution
    - NativeTrack
    - Look-Back
    - Twiiter
    - Multi-Channel
    - Re-Install
    - Facebook
    - media source
    - Advertisers
    - Ad Networks
    - reinstall
    - branch
    - attribution determination
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T10:54:37Z'
  edited_at: '2023-11-15T15:37:47Z'
  id: 207447053
  locale: fr
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/fr/articles/207447053
---
> **En bref :** AppsFlyer détermine la source média qui incite un utilisateur à installer une app ou à s'y ré-engager, AppsFlyer attribue ensuite l'action de l'utilisateur à cette même source en utilisant en se basant sur sa méthode d'attribution.

[![Mobile_user_journey.png](https://support.appsflyer.com/hc/article_attachments/19544107641105)](https://support.appsflyer.com/hc/article_attachments/19544107641105)

## Qu’est-ce que l’attribution ?

**L'attribution** vise à déterminer ce qui a motivé (poussé) un utilisateur à installer une app, ou à effectuer une action post-installation de type réengagement ou réattribution. Le résultat de l'attribution est soit :

* **Une source média non organique** : l'utilisateur a interagi (généralement par impression ou clic) avec une source média.
* **Organique** : l'utilisateur n'a pas interagi avec une source média. Attention ! Pour simplifier les choses, nous écrivons souvent qu'un utilisateur est *attribué de manière organique*. Nous savons que ce n'est pas possible à strictement parler, puisque qu'un utilisateur qui installe d'une manière organique n'est pas attribué du tout.

L'attribution est essentielle à l'optimisation de l'acquisition utilisateur ainsi qu'aux actions et résultats de réengagement.

> 👍 **Astuce**
>
> Vous voulez en savoir plus sur l'attribution ? Suivez cette <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7766/play/18609/attribution-101-part-1">brève formation</Anchor> sur le portail d'apprentissage AppsFlyer.

## Qu'est-ce qu'une installation d'app ?

Le **modèle d'attribution** est un ensemble de règles qui déterminent comment un événement est attribué aux points de contact le long des chemins de conversion. Chacun des acteurs de l'éco-marketing mobile, que ce soit Google Play, l'App Store, Apple, les plateformes CTV, PC ou console, les réseaux publicitaires tels que Meta ads et Twitter, ou les sociétés de mesure mobile ont leurs propres modèles d'attribution. Chacun compte les installations et les événements différemment.

Ce qui importe ce n'est pas la différence entre les modèles, mais plutôt que les règles soient clairement définies et qu'elles soient suivies par chacun. Ceci permettra aux annonceurs d'optimiser les campagnes et de comparer le niveau de performance des utilisateurs.

Il est capital de bien comprendre les modèles et les règles des acteurs avec lesquels vous travaillez. Mais plus important encore est de comprendre les différents modèles pris en charge par AppsFlyer, et ce qui les caractérise.

Dans AppsFlyer, un événement attribuable se produit lorsque l'un des événements suivants a lieu :

* Dans le cas d'une acquisition d'utilisateurs : une **installation** est enregistrée et attribuée une fois que l'utilisateur a téléchargé et lancé l'app mobile. Cela signifie que, dans AppsFlyer, **l'horodatage de l'installation d'une app correspond à son premier lancement**. Les réseaux publicitaires utilisent l'heure d'engagement et les app stores utilisent l'heure de téléchargement.
* Dans le cas du retargeting  :
  * **RÉENGAGEMENT**
  * **Réattribution**

## Méthodes d'attribution

Un certain nombre de modèles d'attribution sont pris en charge par AppsFlyer (cf tableau ci-dessous).

<table><thead><tr><th>Méthode</th><th>Utilise un ID</th><th>Méthode</th><th><p>Attribué par</p></th><th><p>Android (1)</p></th><th>iOS </th><th>Plateforme Windows Universelle</th><th>Plateformes CTV, PC et console (3)</th></tr></thead><tbody><tr><td><a href="#install-referrer-android-only">Référent</a></td><td>Non</td><td>Déterministe</td><td>AppsFlyer</td><td>Oui (2)</td><td>Non</td><td>Oui</td><td>Non</td></tr><tr><td><a href="./appsflyer-attribution-model#device-id-matching">Correspondance du Device ID</a></td><td>Oui</td><td>Déterministe</td><td>AppsFlyer</td><td>Oui </td><td>Oui</td><td>Oui</td><td>Oui</td></tr><tr><td><a href="./appsflyer-attribution-model#probabilistic-modeling">Modélisation probabiliste</a></td><td>Non</td><td>Probabiliste</td><td>AppsFlyer</td><td>Oui </td><td>Oui </td><td>Non</td><td>Oui</td></tr><tr><td><a href="./appsflyer-attribution-model#aggregated-advanced-privacy-aap">Confidentialité avancée agrégée (CAA)</a></td><td>Non</td><td>Données agrégées</td><td>AppsFlyer</td><td>Non</td><td>Oui</td><td>Non</td><td>Non</td></tr><tr><td><a href="./appsflyer-attribution-model#preload-campaigns">Pré-chargement</a></td><td>Non</td><td>Déterministe</td><td>AppsFlyer</td><td>Oui</td><td>Non</td><td>Oui</td><td>Non</td></tr><tr><td> <a href="./skadnetwork-skan-solution-guide" target="_blank">SKAdNetwork</a> (SKAN)</td><td>Non</td><td>Déterministe</td><td>Apple</td><td>Non</td><td>Oui</td><td>Non</td><td>Non</td></tr><tr><td><a href="./apple-ads-integration-setup" target="_blank">Apple Search Ads</a></td><td>Non</td><td>Déterministe</td><td>Apple</td><td>Non</td><td>Oui</td><td>Non</td><td>Non</td></tr><tr><td><a href="./appsflyer-attribution-model#deep-link">Deep link</a></td><td>Non</td><td>Déterministe</td><td>AppsFlyer</td><td>Oui</td><td>Oui</td><td>Oui</td><td>Non</td></tr><tr><td colspan="7"><p>(1) Google Play et stores tiers</p><p>(2) Prise en charge par certains stores tiers</p><p>(3) Voir la <a href="./ctv-pc-and-console-platform-attribution-concepts#plateformes-prises-en-charge" target="_blank">liste complète des plateformes <span>CTV, PC et console</span></a> </p></td><td></td></tr></tbody></table>

Les méthodes d'attribution sont appliquées en fonction de l'ordre des priorités indiqué dans le schéma. Lors d'une nouvelle installation, s'il y a plus d'un engagement valide, **AppsFlyer privilégie les clics sur les impressions et choisit les méthodes déterministes avant les méthodes probabilistes**.

![Attribution method priorities 23.png](https://support.appsflyer.com/hc/article_attachments/19910400460561)

Vous trouverez ci-dessous une explication détaillée des modèles d'attribution AppsFlyer.

<div id="install-referrer-android-only" />

<Accordion title="Install Referrer (Android uniquement)">

Les apps Android téléchargées depuis Google Play ainsi que certaines app stores sont généralement attribuées selon la méthode du référent d'installation. Le référent fournit l'URL originale, celle qui a été cliquée avant la redirection vers le store Android. C'est la principale méthode d'attribution d'Android. À l'heure actuelle, Google Play, Huawei App Store, Samsung Galaxy Store et Xiaomi GetApps Store, prennent en charge l’attribution de référent d’installation. <Anchor target="_blank" href="/marketers/fr/docs/set-up-multi-store-android-attribution#referrer-implementation-thirdparty-android-app-stores">Attribution par référent des autres app stores.</Anchor>

</Accordion>

<div id="device-id-matching" />

<Accordion title="Correspondance du Device ID">

Le réseau publicitaire, qui a accès à l'appareil de l'utilisateur, transmet l'ID d'appareil à AppsFlyer dans l'URL du clic ou lorsqu'une notification d'impression à AppsFlyer a été traitée. AppsFlyer peut ainsi faire correspondre l'ID d'appareil de clic et l'ID d'appareil récupéré par le SDK AppsFlyer.

La correspondance du Device ID constitue la principale méthode d'attribution sur iOS.

Les ID disponibles sont les suivants :

* **Appareils iOS** : IDFA, IDFV
* **Appareils Android disposant de Google Play Services** : (GAID)
* **Appareils Android ne disposant pas de Google Play Services** : OAID, ID Android, IMEI, Fire ID

Les ID d'appareil peuvent être cryptés sur les liens d'attribution en utilisant SHA1 ou MD5.

</Accordion>

<div id="device-id-matching-using-idfv-ios" />

<Accordion title="Correspondance d'ID d'appareil à l'aide d'IDFV (iOS)">

* L'identifiant pour les fournisseurs (IDFV) est disponible à partir de iOS 6.0. Il n'est pas soumis aux mécanismes Apple <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor> et LAT. Il est toujours disponible et peut être utilisé pour la publicité croisée des apps d'un même fournisseur.
* Le SDK AppsFlyer collecte l'IDFV par défaut.
* <Anchor target="_blank" href="https://developer.apple.com/documentation/uikit/uidevice/1620059-identifierforvendor">Selon Apple,</Anchor> *la valeur de cette propriété est la même pour les apps qui proviennent du même vendeur et qui fonctionnent sur le même appareil.*
* Un IDFV est généré par Apple lorsque l'utilisateur installe la première app d'un fournisseur donné. Cela signifie qu'Apple vérifie qu'il n'y a pas d'autres apps du même fournisseur sur l'appareil. Par conséquent, la suppression de toutes les apps d'un fournisseur donné, puis l'installation d'une app du même fournisseur, entraîne la création d'un nouvel IDFV.
* Vous devez envoyer l'IDFV si disponible. Il améliore l'attribution. Nous utilisons l'IDFV dans un certain nombre de scénarios, notamment  :
  * Attribution des promotions croisées.
  * L'attribution de réinstallation sur le même appareil.
  * Rapports de données brutes.
  * Audiences.

</Accordion>

<div id="device-id-matching-for-selfreporting-networks" />

<Accordion title="Correspondance d'ID d'appareil pour les réseaux auto-reporting">

Au premier lancement de l'app, AppsFlyer vérifie dans les réglages de l'app si du trafic est attendu de l'un des <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns#srn-intégrés-à-appsflyer">réseaux auto-reporting</Anchor> (SRN), comme Meta ads, Snapchat et Google Ads.

AppsFlyer interroge les SRN pertinents à l'aide de l'ID d'appareil unique de la nouvelle installation. La requête utilise les API MMP (Mobile Measurement Partners) telles que définies par les SRN. Sur la base de la réponse, AppsFlyer peut attribuer les nouvelles utilisations à un SRN.

</Accordion>

<div id="probabilistic-modeling" />

<Accordion title="Modélisation probabiliste">

La modélisation probabiliste est une technique statistique qui utilise le machine learning pour estimer les performances d'une campagne. Des paramètres de modélisation probabiliste sont collectés :

* Une première fois au moment du clic ou de l'affichage de la publicité (si activé)
* Une deuxième fois lorsque l'app est lancée

#### **Remarque concernant les apps iOS :**

Depuis IOS 14.5, la modélisation probabiliste peut être utilisée dans le cadre des médias propres, de la promotion croisée et des flux web-to-app consentis. Dans les autres cas, c'est la [Confidentialité avancée agrégée](/docs/appsflyer-attribution-model#aggregated-advanced-privacy-aap) qui est utilisée.

**Caractéristiques de l'implémentation**

* S'appuie sur des statistiques et ne se base pas sur des ID uniques.
* C'est une méthode de secours, utilisée en l'absence de référent ou d'ID publicitaire. Les méthodes d'attribution déterministes, c'est-à-dire les clics associés à un ID ou référent, ont la priorité s'ils elles ont lieu dans la fenêtre rétrospective.
* La fenêtre d'attribution est déterminée par AppsFlyer de manière dynamique, en fonction du réseau de l'utilisateur. La durée de la fenêtre est adaptative mais aussi plus courte que celle des autres méthodes (jusqu'à 24 heures).
* La modélisation probabiliste post clic est toujours activée.
* La modélisation probabiliste post-vue doit être activée dans la page des paramètres de l'app et dans l'onglet d'intégration des non-SRN. Pour les applications CTV, PC et console, cette fonction est activée par défaut.

#### Paramètres de modélisation probabiliste pour les réseaux publicitaires

Les réseaux publicitaires qui utilisent l'attribution par modélisation probabiliste doivent envoyer les paramètres suivants via le lien d'attribution ou via les en-têtes de requête HTTP :

* <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#af_ua">af\_ua</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#af_os_version">af\_os\_version</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#af_model">af\_model</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#af_ip">af\_ip</Anchor>

</Accordion>

<div id="aggregated-advanced-privacy-aap" />

<Accordion title="Confidentialité avancée agrégée (CAA)">

La confidentialité avancée agrégée (CAA) reproduit les performances de campagnes d'une manière agrégée, ce qui bloque toute possibilité de suivre les utilisateurs sur les apps ou sites web appartenant à plusieurs sociétés, et empêche d'identifier tout utilisateur ou appareil de manière individuelle.

La CAA prend comme référence les seuils de confidentialité d'Apple SKAdNetwork pour définir son niveau de protection de la vie privée. La CAA est le modèle d'attribution par défaut pour les appareils Apple sous IOS 14.5 et +, à la seule exception des cas autorisés par Apple, comme les médias propres ou les utilisateurs qui ont accepté l'ATT.

Contrairement aux autres méthodes d'attribution, l'objectif du machine learning de la CAA est d'améliorer la précision des performances agrégées de la campagne, et non pas la précision de l'attribution des utilisateurs finaux.

</Accordion>

<div id="preload-campaigns" />

<Accordion title="Pré-chargement des campagnes">

Pour pré-charger une campagne, le partenaire de pré-chargement installe l'app sur l'appareil, soit au moment de la fabrication, soit lors de l'activation de l'appareil. Les partenaires de pré-chargement peuvent être :

* Les fabricants d’équipement d’origine (OEM)
* Les plateformes de recherche d'applications
* Les opérateurs mobile

Il y a 3 manières d'attribuer une campagne de pré-chargement. Ces trois méthodes peuvent être utilisées en même temps sans interférer les unes avec les autres.

Ces méthodes et certaines des principales fonctionnalités sont présentées dans le tableau suivant. Cliquez sur les liens pour en savoir plus sur chacune des méthodes de pré-chargement.

<table><thead><tr><th>Méthode d’attribution de pré-chargement</th><th>Cas d'utilisation</th><th>Infos sur l'activation de l'appareil et le lancement de l'app\*</th><th>Fenêtre rétrospective\*\*</th><th>Type de matching dans les données brutes</th></tr></thead><tbody><tr><td> <a href="./set-up-appsflyer-preload-referrer-attribution" target="_blank">Référent AppsFlyer\*</a> </td><td><ul><li>Pré-chargé en usine</li><li>Pré-chargé lors de l'activation de l'appareil</li></ul></td><td>Oui</td><td><ul><li>Jusqu'à 180 jours</li><li>90 jours par défaut</li></ul></td><td><ul><li>Pré-chargement : preload_rfr</li><li>Cliquez pour télécharger : af_referrer</li></ul></td></tr><tr><td> <a href="./measure-preload-campaigns-with-google-play-install" target="_blank">Installation automatique Google Play</a>\*\*</td><td><p>Pré-chargé lors de l'activation de l'appareil (pour les apps Google Play)</p></td><td>Non</td><td><ul><li>Jusqu'à 180 jours</li><li>90 jours par défaut</li></ul></td><td>preload_pai</td></tr><tr><td> <a href="./appsflyer-factory-preinstall-using-manifest-android" target="_blank">Pré-chargement en usine via les propriétés du système (Android)</a>\*\*</td><td><ul><li>Pré-chargé en usine</li><li>Pré-chargé lors de l'activation de l'appareil</li></ul></td><td>Non</td><td><p>Illimité</p></td><td><p>preload_conf</p></td></tr><tr><td colspan="5"><p>\* Le pré-chargement du référent AppsFlyer permet une visibilité et un suivi des mesures entre le moment de la première activation de l'appareil et la première ouverture de l'app. Vous avez ainsi la possibilité de savoir combien d'appareils ayant l'app préchargée ont été activés pour un partenaire précis, puis de savoir quand l'application est lancée pour la première fois.</p><p>Avec les deux autres méthodes, l’attribution n’est connue que lorsque l’utilisateur lance l’app pour la première fois. Il n'est pas possible de savoir combien d’appareils contenaient l’application avant qu'elle ne soit lancée pour la première fois.</p><p>\*\* Entre le moment où l’utilisateur allume son appareil pour la première fois et celui où il lance l’app pré-chargée pour la première fois, il peut se passer des jours, voire des semaines. C'est pourquoi AppsFlyer place l'attribution des campagnes de pré-chargement en priorité haute, grâce à des fenêtres rétrospectives plus larges.</p></td></tr></tbody></table>

</Accordion>

<div id="deep-link" />

<Accordion title="Deep link">

En cas de réengagement, les utilisateurs ne sont pas redirigés vers un app store pour télécharger l'app. Les informations contenues dans l'URL peuvent donc être directement rattachées au clic (et à l'ouverture ultérieure de l'app). Cette méthode d'attribution est appelée deep linking, car c'est l'URL du deep link qui contient les informations nécessaires à l'attribution du réengagement.

</Accordion>

### Méthodes d'attribution par source média et fonctionnalité AppsFlyer

Voir les sections suivantes pour le détail des cas où des méthodes d'attribution particulières sont prises en charge, en fonction des éléments suivants :

* Source média  : propriétaire ou payante
* Fonctionnalité AppsFlyer utilisée
* Appareil de l'utilisateur : Android ou iOS

<div id="owned-media" />

<Accordion title="Médias propres">

<table><thead><tr><th rowspan="2">Source média</th><th rowspan="2">Contient</th><th colspan="2">Méthode d'attribution</th></tr><tr><th>Android</th><th>iOS</th></tr></thead><tbody><tr><td>Médias propriétaires : courrier électronique (y compris les ESP), SMS, messages sur les réseaux sociaux, influenceurs/affiliés, imprimés, etc.</td><td><a href="./onelink-guide" target="_blank"><span>Le lien profond universel OneLink</span></a></td><td><ul><li>Référent d'installation</li><li>Modélisation probabiliste</li></ul></td><td><p>Modélisation probabiliste</p></td></tr><tr><td rowspan="2">Site web mobile/page d'accueil propriétaire avec trafic entrant payant ou organique</td><td><a href="./smart-banners-mobile-web-to-app-for-marketers" target="_blank">Smart Banners</a></td><td>Modélisation probabiliste</td><td>Modélisation probabiliste</td></tr><tr><td><a href="./onelink-smart-script-overview" target="_blank">Script intelligent OneLink</a></td><td><ul><li>Référent d'installation</li><li>Modélisation probabiliste</li></ul></td><td>Modélisation probabiliste</td></tr><tr><td rowspan="2">Applications mobile propriétaires</td><td><a href="./user-invite-attribution" target="_blank">Invitations/référencement des utilisateurs</a></td><td><p>Modélisation probabiliste</p></td><td><p>Modélisation probabiliste</p></td></tr><tr><td><a href="./cross-promotion-attribution-for-marketers" target="_blank">Promotion croisée</a></td><td>Correspondance du Device ID</td><td>Correspondance du Device ID</td></tr></tbody></table>

</Accordion>

<div id="paid-media" />

<Accordion title="Médias payants">

<table><thead><tr><th rowspan="2">Source média</th><th colspan="3">Méthode d'attribution</th></tr><tr><th>Android</th><th>iOS</th><th><strong>Plateformes CTV, PC et console</strong></th></tr></thead><tbody><tr><td><a href="./self-reporting-networks-srns" target="_blank">Les SRN</a></td><td><p>Correspondance du Device ID</p></td><td><ul><li>Correspondance du Device ID</li><li>AAP (IOS 14.5+)</li><li>SKAdNetwork (iOS 14+)</li></ul></td><td><p>Correspondance du Device ID</p></td></tr><tr><td><ul><li>Réseaux publicitaires (non SRN) via des <a href="./set-up-an-integrated-partner#attribution-link-tab" target="_blank">liens d'attribution pour les partenaires</a> </li><li><span>Plateformes CTV, PC et console</span></li></ul></td><td><ul><li>Référent d'installation</li><li>Correspondance du Device ID</li><li>Modélisation probabiliste</li></ul></td><td><ul><li>Correspondance du Device ID</li><li>Modélisation probabiliste (avant iOS 14.5)</li><li>AAP (IOS 14.5+)</li><li>SKAdNetwork (iOS 14+)</li></ul></td><td> </td></tr><tr><td><p><a href="./appsflyer-factory-preinstall-using-manifest-android" target="_blank">Préinstallé sur l'appareil</a></p></td><td>Préinstallations</td><td>--</td><td> </td></tr></tbody></table>

</Accordion>

## Types d'engagement utilisateur menant à une attribution

L'attribution est effectuée sur la base des engagements de clics et de vues. L'attribution de la source média est réalisée à l'aide de techniques de modélisation probabiliste et de mise en correspondance d'ID d'appareil.

<div id="clickthrough-attribution" />

<Accordion title="Attribution post clic">

La plupart des installations sont le résultat de clics d'utilisateurs sur des publicités, comme des bannières, des vidéos et des interstitiels.

Lors d'un clic sur une publicité, AppsFlyer ouvre une fenêtre rétrospective d'attribution des clics de 7 jours par défaut. Les installations qui ont lieu sur la durée de la fenêtre rétrospective sont considérées comme non organiques, et sont attribuées aux sources média. Les installations qui ont lieu après la fenêtre rétrospective sont considérées comme des installations organiques. Souvent appelées attributions organiques.

* Une fenêtre rétrospective des clics de sept jours est considérée comme la norme du secteur. Définissez la durée de la fenêtre conformément à votre accord avec la source média.
* Alignez les fenêtres rétrospectives du SRN sur la durée déterminée par le SRN.

<table><thead><tr><th rowspan="2"><p><strong>Type d'attribution</strong></p></th><th rowspan="2"><p><strong>Méthode d'attribution</strong></p></th><th rowspan="2"><p>Plage</p></th><th rowspan="2">Par défaut</th></tr></thead><tbody><tr><td rowspan="2"><p>Clic</p><p>(tous les partenaires intégrés)</p></td><td><p>Referrer, ID Matching</p></td><td><p>1 à 30 jours</p></td><td><p>7 jours</p></td></tr><tr><td><p>Modélisation probabiliste</p></td><td><p>0-24 heures</p></td><td><ul><li>Adaptive</li><li>Déterminé par AppsFlyer</li></ul></td></tr></tbody></table>

<Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">En savoir plus sur les fenêtres d'attribution</Anchor>

</Accordion>

<div id="viewthrough-attribution" />

<Accordion title="Attribution post vue">

Les utilisateurs qui consultent les publicités mais ne cliquent pas dessus peuvent être attribués au réseau publicitaire qui diffuse la publicité.

Fenêtre rétrospective pour l'attribution post vue :

* est plus courte que celle de l'attribution post clic
* est configurable.

Pour activer l'attribution post vue, définissez la fenêtre rétrospective dans la fenêtre de configuration.

Cette fonction est particulièrement utile pour les réseaux publicitaires vidéo présentant traditionnellement de faibles CTRs sur leurs publicités vidéo, mais également pour les réseaux publicitaires conventionnels diffusant des publicités ordinaires.

<table><thead><tr><th><strong>Type d'attribution</strong></th><th><p><strong>Méthode d'attribution</strong></p></th><th><p><strong>Plage</strong></p></th><th><p><strong>Par défaut<br/></strong></p></th></tr></thead><tbody><tr><td rowspan="2"><p>Post vue</p><p>(<a href="./measure-view-through-engagements#view-vta-partner-list" target="_blank">Partenaires intégrés sélectionnés</a>)</p></td><td><p>ID Matching</p></td><td><p>0-24 heures</p></td><td><p>1 jour</p></td></tr><tr><td><p>Modélisation probabiliste</p></td><td><p>0-24 heures</p></td><td><ul><li>Adaptive</li><li>Déterminé par AppsFlyer</li></ul></td></tr></tbody></table>

Dans les cas où à la fois un clic et une impression ont lieu, le clic prévaut toujours, car il s'agit d'un engagement actif.

<Anchor target="_blank" href="/marketers/fr/docs/measure-view-through-engagements">En savoir plus sur l'attribution post-vue</Anchor>

</Accordion>

## Rubriques d'attribution avancée

<div id="in-app-events" />

<Accordion title="Évènement in-app">

Lors de l'installation d'une app, AppsFlyer crée un ID AppsFlyer unique associé aux informations d’attribution. Cela permet à la plateforme **d’attribuer les événements in-app à la source média d'origine**. Les annonceurs peuvent utiliser cette information pour suivre le parcours complet de l’utilisateur dans les données brutes de leur app.

Pour plus d'informations sur l'attribution des évènements, cliquez <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview?query=in%20app%20event#how-does-appsflyer-attribute-events">ici</Anchor>.

</Accordion>

<div id="assisted-installs" />

<Accordion title="Installations assistées">

AppsFlyer attribue entièrement une seule source média par installation, généralement en fonction du dernier clic publicitaire ou de la dernière impression publicitaire (en l'absence de clic).

Les installations assistées (ou « attribution multitouch ») correspondent aux installations lors desquelles la source média / campagne n'a pas été le dernier point de contact, mais a touché l'utilisateur avant que l'installation et l'action aient lieu dans la fenêtre d'attribution rétrospective.

Les réseaux assistants apparaissent comme contributeurs de l'installation dans AppsFlyer.

Pour plus d'informations, veuillez cliquer <Anchor target="_blank" href="/marketers/fr/docs/measure-assisted-installs">ici</Anchor>.

</Accordion>

<div id="reinstalls" />

<Accordion title="Réinstallations">

Une réinstallation se produit lorsqu'un utilisateur installe l'app, la désinstalle, puis la réinstalle. L'attribution de la réinstallation est régie par la <Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window">fenêtre de réattribution</Anchor> comme suit :

* Si la réinstallation a lieu après l'expiration de la fenêtre de réattribution : une nouvelle installation est enregistrée.
* Si la réinstallation se produit pendant la fenêtre de réattribution, l'une des conditions suivantes s'applique :
  * Si l'utilisateur s'est engagé dans une campagne de retargeting avant la réinstallation : une <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide">réinstallation de retargeting</Anchor> (alias réattribution) est enregistrée.
  * Si l'utilisateur ne s'est pas engagé dans une campagne ou s'est engagé dans une campagne d'UA : aucune installation n'est enregistrée. Selon l’état <Anchor target="_blank" href="/marketers/fr/docs/measure-reinstalls#présentation">**d’attribution des événements post-réinstallation**</Anchor>, les événements in-app de ces utilisateurs qui ont réinstallé l'app sont attribués à l’installation organique ou à l’installation d’origine.

Pour les tests d'appareil et les installations multiples, vous devez <Anchor target="_blank" href="/marketers/fr/docs/registering-test-devices">enregistrer</Anchor> l'appareil dans AppsFlyer. Si vous n'enregistrez pas l'appareil, seule la première installation sera enregistrée.

Veuillez noter qu'AppsFlyer offre une meilleure précision d'attribution des réinstallations iOS sans ID d'annonceur. Vous pouvez activer cette fonctionnalité sur la <Anchor target="_blank" href="/marketers/fr/docs/app-settings#reinstall-detection-using-ondevice-storage-ios-only">page Paramètres de l’app</Anchor>.

#### Réinstallation des apps iOS sauvegardées dans iCloud

Lorsqu'une application est sauvegardée via iCloud et restaurée ultérieurement (sur le même appareil ou sur un autre différent), AppsFlyer ne la considère pas comme une nouvelle installation ou réinstallation. Un utilisateur qui restaure une app depuis iCloud conserve son identifiant AppsFlyer et ses données d'attribution.

</Accordion>

<div id="retargeting-attribution" />

<Accordion title="Attribution de retargeting">

![Retargeting_-_Flow__2_.png](https://files.readme.io/64b8d9f5040daa281ae13f0855749ab4a88a2e7e8616d6ada37975899db92c80-31937591646097.png)

Un utilisateur qui réinstalle une app dans la <Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window">fenêtre de réattribution</Anchor> (90 jours par défaut) est considéré comme une réattribution. Si cette installation se produit après avoir participé à une campagne de retargeting, elle est enregistrée comme réinstallation de retargeting, autrement dit une réattribution, et est signalée dans le <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide">retargeting</Anchor>.

</Accordion>

<div id="app-updates" />

<Accordion title="Mises à jour d'app">

* Lorsqu'un utilisateur existant met à jour l'app vers une version plus récente, ce n'est pas comptabilisé comme un événement d'attribution si ce même utilisateur a été déjà été attribué par AppsFlyer. Attention ! Si vous migrez vers AppsFlyer depuis une MMP différente, une fois la migration terminée, les utilisateurs existants qui ouvrent pour la première fois l'app sont attribués à l'organique.
* Les métriques relatives au nombre d'utilisateurs par version d'app sont disponibles dans le <Anchor target="_blank" href="/marketers/fr/docs/sdk-information-version-consent-dashboard">tableau de bord d'information du SDK.</Anchor>

</Accordion>

<div data-zendesk-anchors="what-is-attribution=quest-ce-que-lattribution 01H8GG9XPSS8KA9CHPD6ECNR2J=quest-ce-que-lattribution 01H8GG9XPSA15N5CSHGZNBWSAV=astuce what-is-an-app-install=quest-ce-quune-installation-dapp 01EDRHGMTXK94Y97DPKFAMCJ5B=quest-ce-quune-installation-dapp attribution-methods=m%C3%A9thodes-dattribution 01EDRHGMTXCRNVXS9JGHQ1JAQT=m%C3%A9thodes-dattribution 01H8GG9XPS6P3CXX5AN2KY8WN4=install-referrer-android-only 01H8GG9XPSGVK90FV0K9HZARH7=device-id-matching 01H8GG9XPSQZPWJZ0BC0EAMB97=device-id-matching-using-idfv-ios 01H8GG9XPSV247F3JRCR870JK0=device-id-matching-for-selfreporting-networks 01EDRHGMTXHAKWZK99Q2X86BND=probabilistic-modeling note-for-ios-apps=remarque-concernant-les-apps-ios- 01H8GG9XPSE1H8F9TCCXSZSW9W=remarque-concernant-les-apps-ios- probabilistic-modeling-parameters-for-ad-networks=param%C3%A8tres-de-mod%C3%A9lisation-probabiliste-pour-les-r%C3%A9seaux-publicitaires h_01HEMSHXKGNW2DF41094BXY0FY=param%C3%A8tres-de-mod%C3%A9lisation-probabiliste-pour-les-r%C3%A9seaux-publicitaires 01H8GG9XPSZ5CPKNSCV7NF1MKW=preload-campaigns attribution-methods-per-media-source-and-appsflyer-feature=m%C3%A9thodes-dattribution-par-source-m%C3%A9dia-et-fonctionnalit%C3%A9-appsflyer 01H8GG9XPTXDR41QANF4XVSZMM=m%C3%A9thodes-dattribution-par-source-m%C3%A9dia-et-fonctionnalit%C3%A9-appsflyer 01H8GG9XPT65G88DE8548HZREE=owned-media 01H8GG9XPTADWMQ37WBB6P9WVS=paid-media user-engagement-attribution-types=types-dengagement-utilisateur-menant-%C3%A0-une-attribution 01EDRHGMTX7851H14R20F9KNAN=types-dengagement-utilisateur-menant-%C3%A0-une-attribution 01EDRHGMTXJ7WKTWQXFCHTD9AV=clickthrough-attribution 01EDRHGMTXN0Y0ZRVBX7HHW7NN=viewthrough-attribution advanced-attribution-topics=rubriques-dattribution-avanc%C3%A9e 01EDRHGMTYYXBSCDPKXCDK1641=rubriques-dattribution-avanc%C3%A9e 01EDRHGMTYMH3SVNBTQ28D4F42=in-app-events 01EDRHGMTY2CF0B70T3RAGPCJ1=reinstalls reinstalling-ios-apps-that-are-backed-up-in-icloud=r%C3%A9installation-des-apps-ios-sauvegard%C3%A9es-dans-icloud 01EDRHGMTYDSNJKQNPNYFXJPAZ=r%C3%A9installation-des-apps-ios-sauvegard%C3%A9es-dans-icloud 01EDRHGMTYYB9XVM5CBWSPJGMN=retargeting-attribution 01EDRHGMTYTQRMG1W7ZBW4G6W4=app-updates" />
