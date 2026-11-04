---
title: Intégration complémentaire du SDK
metadata:
  keywords:
    - iOS
    - Android
    - Integration
    - Advertisers
    - firetv
    - Advertiser
    - appuid
    - anonymous
    - kakao
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2021-10-10T11:54:14Z'
  edited_at: '2023-11-13T12:28:40Z'
  id: 4408735106193
  locale: fr
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/fr/articles/4408735106193
---
> **En bref :** pensez à profiter des fonctionnalités de SDK complémentaires et avec la collaboration de votre développeur implémentez différentes API comme la mesure des désinstallations, l'attribution des invitations d'utilisateurs, les notifications push et les paramètres de confidentialité.

<div id="additional-attribution-methods" />

## Méthodes d'attribution complémentaire

Ces méthodes d'attribution complémentaire vous seront utiles si vous prévoyez de mesurer la TV, les désinstallations ou les applications préinstallées.

**Toutes les plateformes**

<div id="tv-attribution" />

<Accordion title="Attribution TV">

Attribuez les <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">utilisateurs mobile à des publicités TV</Anchor> diffusées dans un lieu et à moment précis.

</Accordion>

<div id="measure-uninstalls" />

<Accordion title="Mesure des désinstallations">

Mesurez le taux de désinstallation des utilisateurs provenant de différentes sources. La mesure des désinstallations peut vous aider à analyser et optimiser vos campagnes en fonction de ce KPI significatif.

<Anchor target="_blank" href="/marketers/fr/docs/measure-uninstalls">Découvrez comment configurer la mesure des désinstallations</Anchor>.

</Accordion>

**Android uniquement**

<div id="preinstalled-apps" />

<Accordion title="Applications pré-installées">

Dans les <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-factory-preinstall-using-manifest-android">campagnes de pré-installation</Anchor>, les propriétaires d'apps passent un contrat avec les fabricants d'appareils (OEM) pour qu'ils y préinstallent leurs applications.

Avec AppsFlyer, vous pouvez facilement attribuer les installations d'applications pré-installées. Lorsque les utilisateurs lancent votre application pour la première fois, AppsFlyer attribue l'installation au fabricant en tant que source média.

</Accordion>

## Sessions

Mesurez l'engagement des utilisateurs vis-à-vis de votre app en comptabilisant le nombre de sessions utilisateur au cours d'une période donnée.

**Toutes les plateformes**

<div id="custom-time-between-sessions" />

<Accordion title="Personnalisation de la durée entre sessions">

Par défaut, il doit s'écouler au moins 5 secondes entre deux lancements d'app pour que les sessions soient considérées comme distinctes. En savoir plus sur la <Anchor target="_blank" href="/marketers/fr/docs/measure-sessions#session-reporting-by-the-app-sdk">comptabilisation des sessions</Anchor>.

Le fait de définir la **durée personnalisée entre deux lancements sur une valeur élevée peut impacter négativement les API** **qui s'appuient sur les données de session, comme le deep linking**.

</Accordion>

**Android uniquement**

<div id="background-sessions-for-utility-apps" />

<Accordion title="Sessions d'arrière-plan pour applications utilitaires">

Vous pouvez <Anchor target="_blank" href="/marketers/fr/docs/measure-sessions#session-reporting-by-the-app-sdk">créer manuellement des rapports de sessions utilisateur</Anchor>. Cela peut être utile pour les apps utilitaires qui s'exécutent en back-end.

</Accordion>

<div id="owned-media" />

## Médias propres

Utilisez OneLink pour attribuer vos sources média propres, comme les sites, réseaux sociaux et invitations d'utilisateurs.

**Toutes les plateformes**

<div id="resolve-wrapped-deep-link-urls" />

<Accordion title="Résoudre les URL Deep Link encapsulées">

Certains services tiers tels que les <Anchor target="_blank" href="/marketers/fr/docs/email-service-provider-esp-integration-guide">prestataires de services de messagerie</Anchor> encapsulent des liens dans des emails avec leurs propres domaines d'enregistrement des clics. Certains vous permettent même de définir vos propres domaines d'enregistrement des clics. Si OneLink est encapsulé dans de tels domaines, il est possible que ses fonctionnalités soient limitées.

Pour résoudre ce problème, votre développeur doit configurer l'application à l'aide des API suivantes :

<Tabs>
<Tab title="Android natif">

Voir [`setResolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setresolvedeeplinkurls) dans le cadre du SDK Android

</Tab>

<Tab title="iOS natif">

Voir [`resolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#resolvedeeplinkurls) dans le cadre du SDK iOS

</Tab>

<Tab title="Unity">

Voir [`setMinTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/api#setresolvedeeplinkurls) dans le cadre du SDK Unity

</Tab>
</Tabs>

</Accordion>

<div id="record-push-notifications" />

<Accordion title="Enregistrement des notifications push">

AppsFlyer prend en charge la mesure des campagnes de notification push pour l'ensemble des fournisseurs, dont les services de notification push Google Cloud Messaging et Apple.

<Anchor target="_blank" href="/marketers/fr/docs/measuring-push-notification-re-engagement-campaigns">En savoir plus sur la mesure des notifications push</Anchor>.

</Accordion>

<div id="user-invite-attribution" />

<Accordion title="Attribution des invitations utilisateur">

Le fait de permettre à vos utilisateurs existants d'inviter leurs amis et contacts en tant que nouveaux utilisateurs de votre application peut être un facteur de croissance important pour votre application. Avec AppsFlyer, vous pouvez attribuer et enregistrer les installations provenant d'invitations utilisateur au sein de votre app.

En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/user-invite-attribution">l'attribution des invitations</Anchor>.

</Accordion>

<div id="crosspromotion-attribution" />

<Accordion title="Attribution des promotions croisées">

Les applications de promotion croisée peuvent être un facteur de croissance important en entrainant plus d'installations de vos applications. AppsFlyer vous permet d'attribuer et d'enregistrer les installations issues de la promotion croisée d'une app que l'utilisateur a déjà installé, vers une autre de vos applications.  

<Anchor target="_blank" href="/marketers/fr/docs/cross-promotion-attribution-for-marketers">En savoir plus sur l'attribution des promotions croisées</Anchor>.

</Accordion>

<div id="attribute-app-sessions-initiated-from-owned-websites-domains" />

<Accordion title="Attribuer des sessions d'app initiées depuis des sites (domaines) propres">

Les propriétaires d'app qui passent par les liens universels pour le deep linking (sans OneLink) peuvent configurer le SDK pour attribuer les sessions initiées via un domaine associé à leur app (<Anchor target="_blank" href="https://developer.android.com/studio/write/app-link-indexing#associatesite">Android</Anchor> / <Anchor target="_blank" href="https://developer.apple.com/documentation/xcode/supporting-associated-domains?preferredLanguage=occ">IOS</Anchor>).

Par exemple :

* Un utilisateur lance une recherche sur Google puis clique sur votre domaine **www.example.com**.
* Si l'utilisateur n'a pas encore installé l'application, il est dirigé vers le site (www.example.com).
* Si l'utilisateur a installé l'app sur son appareil, il est deep linké à l'application qui est associée à www.example.com. La session est attribuée à la source média (paramètre `pid` ) configurée dans le SDK.

La documentation destinée aux développeurs est disponible ci-dessous :

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl">Référence du SDK Android</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl">Référence du SDK iOS</Anchor>

**Conseil** ! Les <Anchor target="_blank" href="/marketers/fr/docs/convert-your-mobile-web-visitors-to-app-users#attribution-solutions">smart scripts One Link</Anchor> permettent aux propriétaires d'app d'augmenter la conversion des visiteurs d'un site en utilisateurs d'app.

</Accordion>

<div id="user-privacy" />

## Confidentialité des utilisateurs

Prenez en compte les différentes réglementations comme le GDPR et le CCPA, ainsi que les besoins de votre entreprise, et réfléchissez aux politiques de demande de consentement (accord ou refus) à mettre en place.

**Toutes les plateformes**

<div id="optout-policy" />

<Accordion title="Politique de demande de consentement (refus)">

Il pourra vous être nécessaire de demander à votre développeur de paramétrer le SDK AppsFlyer afin de stopper ou limiter la collecte de données, (par exemple pour vous conformer au RGPD ou CCPA). La demande de consentement peut avoir lieu à différents niveaux en fonction des réglementations et des droits des utilisateurs. Pour en savoir plus sur le sujet, cf <Anchor target="_blank" href="/marketers/fr/docs/apply-privacy-preserving-sdk-methods#scénarios">le refus de consentement des utilisateurs</Anchor>.

</Accordion>

<div id="exclude-partners-from-getting-data" />

<Accordion title="Exclure les partenaires de l'obtention de données">

Dans certains cas, les annonceurs peuvent choisir de cesser le partage de données de niveau utilisateur avec des réseaux publicitaires/partenaires pour certains utilisateurs. Parmi les motifs on retrouve : 

* Les politiques de confidentialité telles que la CCPA ou le RGPD
* Les mécanismes de retrait des utilisateurs
* La concurrence avec certains partenaires (ad networks, tiers)

Le partage de données avec les partenaires est contrôlé via la méthode `setSharingFilterForPartners` :

<Tabs>
<Tab title="Android natif">

Voir [`setSharingFilterForPartners`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners) dans le cadre du SDK Android

</Tab>

<Tab title="iOS natif">

Voir [`resolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforpartners) dans le cadre du SDK iOS

</Tab>

<Tab title="Unity">

Voir [`setSharingFilterForPartners`](https://dev.appsflyer.com/hc/docs/api#setsharingfilterforpartners) dans le cadre du SDK Unity

</Tab>
</Tabs>

</Accordion>

**iOS uniquement**

<div id="strictmode-sdk" />

<Accordion title="SDK en mode strict">

Utilisez le SDK en mode strict pour supprimer complètement la fonctionnalité de collecte IDFA et les dépendances de structure AdSupport (par exemple, lors du développement d'une <Anchor target="_blank" href="https://developer.apple.com/app-store/review/guidelines/#kids-category">app jeune public).</Anchor>

Si vous commercialisez des apps destinées au jeune public, votre développeur doit installer le <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">SDK en mode strict</Anchor> et non pas en mode standard. **Remarque :** l'IDFV reste disponible.

</Accordion>

<div id="disable-ad-frameworks" />

<Accordion title="Désactiver des infrastructures publicitaires">

Pour désactiver les infrastructures AdSupport et iAd, le SDK fournit les paramètres suivants :

<Tabs>
<Tab title="iOS natif">

* [`disableCollectASA`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disablecollectasa) pour refuser les attributions d'Apple Search Ads.
* [`disableAdvertisingIdentifier`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableadvertisingidentifier) pour ne pas collecter l'`ID publicitaire` Apple

</Tab>

<Tab title="Unity">

* [`setDisableCollectIAd`](https://dev.appsflyer.com/hc/docs/api#setdisablecollectiad) pour refuser les attributions d'Apple Search Ads.
* [`setDisableCollectAppleAdSupport`](https://dev.appsflyer.com/hc/docs/api#setdisablecollectappleadsupport) pour ne pas collecter l'`ID publicitaire`Apple

</Tab>
</Tabs>

</Accordion>

<div data-zendesk-anchors="additional-attribution-methods=m%C3%A9thodes-dattribution-compl%C3%A9mentaire 01H8W01DRHQHJKNMJA24PR5S2T=m%C3%A9thodes-dattribution-compl%C3%A9mentaire 01H8W01DRHXR0BRCB9RECH7KS1=tv-attribution 01H8W01DRHMZN2P0FKADM0NQ96=measure-uninstalls 01H8W01DRH2HM3N06YAGRZ030F=preinstalled-apps 01H8W01DRHD3EZBQT0ZKDMM1QB=sessions 01H8W01DRH2SR3NBQSMSQ6QR6K=custom-time-between-sessions 01H8W01DRH4NGYYABE274DJ1A5=background-sessions-for-utility-apps owned-media=m%C3%A9dias-propres 01H8W01DRHV8H3QFJX5QKABK5E=m%C3%A9dias-propres 01H8W01DRHJS8MM3ZQX2RX4JJG=resolve-wrapped-deep-link-urls 01H8W01DRHHDEEXP8GDFX9134R=record-push-notifications 01H8W01DRHZDB82AB63JKE1B6V=user-invite-attribution 01H8W01DRHVR8JHZCJ6SW8TAA6=crosspromotion-attribution 01H8W01DRHXSYWCS6RW2ZVDKXT=attribute-app-sessions-initiated-from-owned-websites-domains user-privacy=confidentialit%C3%A9-des-utilisateurs 01H8W01DRHJFB71DVJ64QWJME4=confidentialit%C3%A9-des-utilisateurs 01H8W01DRHD7FDERJZFJP9GG0T=optout-policy 01H8W01DRHYNYYFTF82XZ21J3P=exclude-partners-from-getting-data 01H8W01DRJD0XRX4VX03T3YEKX=strictmode-sdk 01H8W01DRJKJFFMBMJ4KNTXPXE=disable-ad-frameworks" />
