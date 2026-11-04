---
title: Identifiants d'appareil
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2021-10-12T14:16:09Z'
  edited_at: '2023-11-24T14:39:31Z'
  id: 4408847686161
  locale: fr
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/fr/articles/4408847686161
---
> **En bref :** les ID d'appareils pris en charge par le SDK AppsFlyer.

<div id="overview" />

## Présentation

Le SDK AppsFlyer collecte des ID d'appareils à des <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#attribution">fins d'attribution</Anchor>. Les identifiants peuvent vous aider à mapper le parcours de vos utilisateurs et à détecter leurs préférences.

Le SDK collecte automatiquement des identifiants tels que l'ID AppsFlyer et le Google Advertising ID (GAID). La collecte d'autres identifiants pour votre application dépend de vos besoins (ex : collecte d'app stores tiers Android ou d'applications commercialisées en Chine).

## Identifiants d'appareils pour toutes les plateformes

Le SDK prend en charge les ID d'appareils suivants sur l'ensemble des plateformes :

| ID d'appareil | Objectif |
| --- | --- |
| <span id="appsflyer-id"></span>ID AppsFlyer | Un ID AppsFlyer est automatiquement créé à chaque installation d'une application. Avec cet identifiant vous pouvez :<ul><li>Envoyez des <Anchor target="_blank" href="/marketers/fr/docs/server-to-server-events-api-for-mobile-s2s-mobile">événements in-app serveur à serveur</Anchor>.</li><li>Faites correspondre l'ID AppsFlyer et les enregistrements utilisateur dans vos systèmes en arrière-plan.</li><li>Mappez les entrées au moment de la fusion des données des API Pull et Push.</li></ul> |
| <span id="customer-user-id"></span>ID utilisateur du client | Le champ « <Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid">ID utilisateur du client</Anchor> » (CUID) est un identifiant unique défini par les propriétaires d'app et de sites web.Le fait de définir votre propre ID utilisateur client dans AppsFlyer vous permet de croiser votre ID et avec l'ID unique d'un appareil AppsFlyer, ou tout autre identifiant. Le CUID est disponible dans les rapports de <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary">données brutes</Anchor> AppsFlyer. Vous pouvez également l'utiliser dans les API de postback pour le croiser avec vos ID internes. |

<div id="android-device-identifiers" />

## ID des appareils Android

Le SDK prend en charge les ID d'appareils suivants pour les plateformes Android :

<div id="apps-published-on-google-play" />

#### Applications publiées dans Google Play

| ID d'appareil | Objectif |
| --- | --- |
| <span id="gaid"></span>GAID | Un identifiant **réinitialisable par l'utilisateur** pour les utilisateurs de Google Play Android.<br /><br />Depuis le SDK V4.8.0, AppsFlyer collecte automatiquement cet identifiant d'appareil. |

<div id="apps-published-in-third-party-app-stores" />

#### Applications publiées dans les app stores tiers

| ID d'appareil | Objectif |
| --- | --- |
| <span id="amazon-advertising-id"></span>ID publicitaire Amazon | Identifiant unique, **réinitialisable par l'utilisateur**, utilisé par Amazon Fire TV. <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">Voir la présentation CTV</Anchor> |
| <span id="oaid"></span>OAID | Identifiant **réinitialisable par l'utilisateur** utilisé par certains marchés Android hors store.  Pour plus d'informations, consultez le <Anchor target="_blank" href="/marketers/fr/docs/android-oaid-implementation-in-the-sdk">Guide de mise en œuvre de l'OAID</Anchor>. |
| <span id="imei"></span>IMEI | Identifiant unique et **non réinitialisable** d'un appareil mobile utilisé sur les marchés autres que Google Play. Le SDK ne collecte pas automatiquement l'IMEI. Toutefois, s'il est nécessaire de récupérer ces identifiants, votre développeur peut implémenter la collecte.<br /><br />**Remarque :**<ul><li>À partir d'Android 10, l'accès à l'IMEI est <Anchor target="_blank" href="https://developer.android.com/about/versions/10/privacy/changes#non-resettable-device-ids">restreint</Anchor>.</li><li>L'IMEI ne peut pas être utilisé conjointement avec le GAID.</li></ul> |
| <span id="android-id"></span>ID Android | Identifiant unique et **non réinitialisable** d'un appareil mobile utilisé dans les app stores tiers. Le SDK ne collecte pas automatiquement l'IMEI ou l'Android ID. Toutefois, s'il est nécessaire de récupérer ces identifiants, votre développeur peut implémenter la collecte.<br /><br />**Remarque :** l'ID Android ne peut pas être utilisé en même temps que le GAID. |

<div id="apple-device-identifiers" />

## ID des appareils Apple

Le SDK prend en charge les ID d'appareils suivants sur l'ensemble des plateformes :

| ID d'appareil | Objectif |
| --- | --- |
| <span id="idfa"></span>idfa | Un identifiant unique **réinitialisable par l'utilisateur** pour les utilisateurs d'Apple iOS ou de tvOS (Apple TV). Depuis la sortie de l'iOS 14.5, l'IDFA n'est disponible que si l'utilisateur donne son accord via l'<Anchor target="_blank" href="/marketers/fr/docs/about-att-and-skan#att-principles">invite ATT</Anchor>. |
| <span id="idfv"></span>IDFV | ID de l'appareil partagé par l'ensemble des applications d'un **même fournisseur** sur l'appareil. Une fois la première application installée, l'ID lui est attribué et les autres applications du même fournisseur se voient attribuer le même IDFV. Les applications d'autres fournisseurs se voient attribuer un IDFV différent.<br /><br />En outre, lorsque toutes les applications d'un fournisseur sont supprimées, le VDFI de ce fournisseur est supprimé et, lorsqu'une nouvelle installation a lieu, un nouveau VDFI est attribué. |

<div id="ctv--pc-and-console-app-device-identifiers" />

## ID des appareils CTV

Le SDK prend en charge les ID d'appareils suivants sur l'ensemble des plateformes :

| ID d'appareil | Objectif |
| --- | --- |
| <span id="rida"></span>RIDA | Pour les appareils Roku CTV. <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">Voir la présentation CTV</Anchor> |
| <span id="vida"></span>VIDA | Pour les appareils Vizio CTV. <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">Voir la présentation CTV</Anchor> |
| <span id="tifa"></span>TIFA | Pour les appareils Samsung CTV. <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">Voir la présentation CTV</Anchor> |
| <span id="lgudid"></span>LGUDID | Pour les appareils LG CTV. <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">Voir la présentation CTV</Anchor> |

<div data-zendesk-anchors="overview=pr%C3%A9sentation h_01H9YXEYC3PA271B3G3Y3GM9PS=pr%C3%A9sentation device-identifiers-for-all-platforms=identifiants-dappareils-pour-toutes-les-plateformes h_01H9YXEYC3RCB3RDBKRW19WYQD=identifiants-dappareils-pour-toutes-les-plateformes android-device-identifiers=id-des-appareils-android h_01H9YXEYC3D95A6G70EGNR8ENK=id-des-appareils-android apps-published-on-google-play=applications-publi%C3%A9es-dans-google-play h_01H9YXEYC3RG2XCVVW8MJ5VZSC=applications-publi%C3%A9es-dans-google-play apps-published-in-thirdparty-app-stores=applications-publi%C3%A9es-dans-les-app-stores-tiers h_01H9YXEYC3JA3DPN6P43J1ZXR9=applications-publi%C3%A9es-dans-les-app-stores-tiers apple-device-identifiers=id-des-appareils-apple h_01H9YXEYC3733B1A85TEF35EAY=id-des-appareils-apple ctv-device-identifiers=id-des-appareils-ctv h_01H9YXEYC3DFPWVXA5Y3XANQ3P=id-des-appareils-ctv" />
