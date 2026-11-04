---
title: Configuration de l'intégration Salesforce Marketing Cloud MobilePush
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-14T06:37:05Z'
  edited_at: '2023-09-11T10:52:32Z'
  id: 10590769196817
  locale: fr
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/fr/articles/10590769196817
---
> **En bref :** Salesforce Marketing Cloud MobilePush, partenaire intégré d'AppsFlyer, est une plateforme d'engagement des utilisateurs destinée aux équipes de marketing, de croissance et d'engagement.

<div id="overview" />

## Vue d'ensemble

Salesforce Marketing Cloud MobilePush vous permet de créer et d'envoyer des notifications Push ciblées basées sur des données utilisateurs multicanaux. Cela incite les utilisateurs à utiliser l'application, pour un ROI plus important. Avec MobilePush, découvrez comment les utilisateurs naviguent dans votre application, les produits qu'ils consultent ou le temps passé sur chaque page. En intégrant MobilePush, vous pourrez :

* Stimuler l'engagement et le mCommerce
* Obtenir des informations précieuses sur les utilisateurs
* Créer facilement des campagnes multicanaux
* Segmenter et programmer les notifications

<div id="important" />

> 🚧 **Important !**
>
> <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions#restrictions-des-sources-média">Certaines sources média</Anchor> limitent le partage de données avec des tiers .Par conséquent, les postbacks pour les événements limités ne seront pas envoyés à ce partenaire, quelle que soit la sélection configurée pour l'envoi de postbacks.

<div id="setting-up-salesforce-marketing-cloud-mobilepush" />

## Configurer Salesforce Marketing Cloud MobilePush

La majeure partie de la configuration s'effectue dans Salesforce (étapes 1 à 4). L'étape 5 est réalisée dans AppsFlyer.

<div id="step-1-set-up-mobilepush-sdk" />

### Étape 1 : configurer le SDK MobilePush

* <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_get_started.htm&type=5">Installer le SDK MobilePush</Anchor>

<div id="step-2-provision-for-push-notifications" />

### Étape 2 : prévoir les notifications push.

* <Anchor target="_blank" href="https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-provision.html">Créer un certificat `.p12` .</Anchor>

<div id="step-3-enable-app-push-notifications" />

### Étape 3 : activer les notifications Push de l'application

* <Anchor target="_blank" href="https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-configureforpush.html">Installer les notifications Push.</Anchor>

<div id="step-4-set-up-app-push-notifications" />

### Étape 4 : configurer les notifications Push de l'application

* <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_outbound_message.htm&type=5">Créer et envoyer des notifications Push aux appareils mobile.</Anchor>

<div id="note" />

> 📘 **Remarque**
>
> Pour créer une notification Push sur Salesforce Marketing Cloud, vous devez ajouter une <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_custom_keys.htm&type=5">clé personnalisée</Anchor> pour permettre à AppsFlyer d'attribuer correctement le PID et les attributs de la campagne. Utilisez `AF_xxxxxxxxx` comme clé personnalisée.

<div id="step-5-set-up-push-notifications-in-appsflyer" />

### Étape 5 : configurer les notifications Push dans AppsFlyer

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications-ios#addpushnotificationdeeplinkpath-recommended">Configurer le SDK iOS à l'aide de OneLink (étape 3 de ce lien).</Anchor>

<div id="note-1" />

> 📘 **Remarque**
>
> Assurez-vous que la clé personnalisée `AF_xxxxxxxxx` que vous avez saisie à l'étape 4  est la même que celle saisie dans la fonction `addPushNotificationDeepLinkPath`.

<div data-zendesk-anchors="overview=vue-densemble h_01H9HWK3F5TQZ8YQZBHGBZACPG=vue-densemble h_01H9HWK5DM87JTDVFND0KB965G=important- setting-up-salesforce-marketing-cloud-mobilepush=configurer-salesforce-marketing-cloud-mobilepush h_01H9HWK3F52YGQPX4B82N40PPD=configurer-salesforce-marketing-cloud-mobilepush step-1-set-up-mobilepush-sdk=%C3%A9tape-1-configurer-le-sdk-mobilepush h_01H9HWK3F5HCVZ0225MFRYRW5Q=%C3%A9tape-1-configurer-le-sdk-mobilepush step-2-provision-for-push-notifications=%C3%A9tape-2-pr%C3%A9voir-les-notifications-push h_01H9HWK3F5RNCZG340E0CT5XJC=%C3%A9tape-2-pr%C3%A9voir-les-notifications-push step-3-enable-app-push-notifications=%C3%A9tape-3-activer-les-notifications-push-de-lapplication h_01H9HWK3F5E4W8FG35V4JTFN7F=%C3%A9tape-3-activer-les-notifications-push-de-lapplication step-4-set-up-app-push-notifications=%C3%A9tape-4-configurer-les-notifications-push-de-lapplication h_01H9HWK3F5K8V8AVADXNNG25GY=%C3%A9tape-4-configurer-les-notifications-push-de-lapplication h_01H9HWK3F5VG2GBCE93B69AADH=remarque step-5-set-up-push-notifications-in-appsflyer=%C3%A9tape-5-configurer-les-notifications-push-dans-appsflyer h_01H9HWK3F5YJ71YCWHV4B02VYP=%C3%A9tape-5-configurer-les-notifications-push-dans-appsflyer h_01H9HWK3F5T67NSPE9CVPS1KTA=remarque-1" />
