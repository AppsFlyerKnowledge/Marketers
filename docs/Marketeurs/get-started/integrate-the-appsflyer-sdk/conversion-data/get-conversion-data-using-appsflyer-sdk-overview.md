---
title: "Obtenir des données de conversion à l'aide du SDK AppsFlyer\_– Présentation"
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:06:52Z'
  edited_at: '2024-08-26T13:36:15Z'
  id: 4410481069969
  locale: fr
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/fr/articles/4410481069969
---
> **En bref :** **En bref :** utilisez les données de conversion pour identifier les scénarios de conversion, personnaliser l'expérience utilisateur, etc.

Utilisez les données de conversion pour :

* Diriger les utilisateurs vers des activités spécifiques
* Leur proposer un contenu personnalisé

En raison du rapport précision/latence, les données de conversion pour les mêmes ID d'appareils peuvent varier d'une API à l'autre.

## Obtenir les données de conversion

Le SDK AppsFlyer renvoie les données de conversion comme suit :

* * `onConversionDataSuccess` : Conversions d'acquisition d'utilisateurs (UA) et de réattribution  
    * Android : <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerconversionlistener#onconversiondatasuccess">OnConversionDataSuccess</Anchor>
    * iOS : <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlibdelegate#onconversiondatasuccess">onConversionDataSuccess</Anchor>
    * Unity : loadConversionData
  * `onAppOpenAttribution` : Pour les conversions liées au réengagement

<div data-zendesk-anchors="get-conversion-data=obtenir-les-donn%C3%A9es-de-conversion h_01HTZ6M409RPZAQM66R0H5HA16=obtenir-les-donn%C3%A9es-de-conversion" />
