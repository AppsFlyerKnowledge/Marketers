---
title: Notes de mise à jour du SDK iOS d'AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Release Notes
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
  created_at: '2017-03-09T19:49:54Z'
  edited_at: '2023-11-22T15:03:06Z'
  id: 115001224823
  locale: fr
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/fr/articles/115001224823
---
> **En bref :** notes de mise à jour pour le SDK iOS `V4+`.

## iOS SDK V6

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk">Guide d'intégration du SDK iOS pour les développeurs</Anchor>

| Version | Date de sortie | Maintenance uniquement | Remarques |
| --- | --- | --- | --- |
| 6.12.2 | 24/08/2023 | Oui |  |
| 6.12.1 | 20/07/2023 |  | <ul><li>Correction d'un problème dans SKAdNetwork 4.0, qu indiquait la conversion approximative comme None.</li><li>Correction d'un problème lors de l'implémentation de tvOS</li></ul> |
| 6.12.0 | 28/06/2023 |  | Suppression de la prise en charge du bitcode dans le SDK |
| 6.11.2 | 13/06/2023 |  | Correction d'un problème dans la version 6.11.0, où l'appel de  `validateAndLogInAppPurchase`  (l'ancienne API pour la validation et l'enregistrement des achats) n'enregistre pas l'événement d'achat.   <br />  <br />**Important :** si vous utilisez la version `v6.11.0` ou `v6.11.1` et l'API `validateAndLogInAppPurchase`, veuillez mettre à jour vers cette version. |
| 6.11.1 | 24/05/2023 | Oui |  |
| 6.11.0 | 25/04/2023 |  | <ul><li>Un nouveau nom de domaine AppsFlyer dans l'URL utilisée par le SDK pour envoyer des demandes aux serveurs AppsFlyer.</li><li>Modification du comportement de l'API setHost lorsque des valeurs vides ou nulles sont envoyées. [En savoir plus](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#sethost)</li></ul> |
| 6.10.1 | 02/04/2023 |  | Ajout du paramètre `link` à la charge utile UDL des scénarios de deep linking direct |
| 6.10.0 | 15/02/2023 |  | Assistance SKAdNetwork 4.0 <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">En savoir plus sur la solution AppsFlyer SKAdNetwork</Anchor> |
| 6.9.2 | 31/01/2023 |  | Mise à jour de la structure de demande interne pour Get Conversion Data (GCD).**Remarque :** les données transmises dans les réponses restent identiques. |
| 6.9.1 | 28/11/2022 |  | Mise à jour de la structure de demande interne pour Get Conversion Data (GCD).**Remarque :** les données transmises dans les réponses restent identiques. |
| 6.9.0 | 06/11/2022 |  | Mise à jour de l'API interne pour les rapports AdRevenue. À partir de cette version, seul le [connecteur générique pour AdRevenue](https://dev.appsflyer.com/hc/docs/ad-revenue-2) est pris en charge.<br /><br />Cette version du SDK est compatible avec AdRevenue Connector `V6.9.0`. |
| 6.8.1 | 09/08/2022 |  | **Détection de réinstallation** : amélioration de la capacité à détecter et à signaler les réinstallations de l'application utilisant le stockage sur l'appareil. Cette capacité peut être contrôlée dans le tableau de bord d'AppsFlyer à partir de la <Anchor target="_blank" href="/marketers/fr/docs/app-settings">page Paramètres des applications</Anchor>. |
| 6.8.0  <br />(obsolète) | 19/07/2022 |  | Pour la détection de réinstallation, veuillez utiliser le SDK V6.8.1+. |
| 6.7.0 | 19/06/2022 |  | Mise à jour de l'implémentation de SKAdNetwork pour utiliser la nouvelle API Apple `updatePostbackConversionValue`, introduite avec iOS 15.4.<br /><br />Cela n'a aucun effet sur les données envoyées par SKAdNetwork et ne nécessite aucune modification du code de l'application. |
| 6.6.1 | 16/05/2022 | Oui |  |
| 6.6.0 | 01/05/2022 |  | Ajout de paramètres au rappel UDL `onDeepLinking` pour le flux de deep linking direct (utilisateurs existants). <Anchor target="_blank" href="/marketers/fr/docs/bulletin-additional-parameters-available-for-deep-linking-existing-users">En savoir plus</Anchor>. |
| 6.5.4 | 23/03/2022 | Oui |  |
| 6.5.3 | 02/03/2022 |  | **Correction :** correction d'un problème de double invocation de `didResolveDeepLink` sur les liens basés sur le schéma d'URI. |
| 6.5.2 | 26/01/2022 | Oui |  |
| 6.5.1 | 03/01/2022 | Oui |  |
| 6.5.0 | 22/12/2021 |  | Remaniement et changements internes. |
| 6.4.4 | 12/12/2021 | Oui |  |
| 6.4.3 | 30/11/2021 |  | Correction de stabilité pour MacOS 10.14.6 avec xcframework. |
| 6.4.2 | 28/10/2021 | Oui |  |
| 6.4.1 | 24/10/2021 |  | Stabilité résolue dans les applications Unity. |
| 6.4.0 | 12/09/2021 |  | **API ajoutée :** `setSharingFilterForPartners` vous permet de configurer les partenaires que le SDK ne doit pas inclure dans le partage des données.<br /><br />Depuis cette version, `setSharingFilter` et `setSharingFilterForAllPartners` sont obsolètes. |
| 6.3.5 | 19/08/2021 |  | **API ajoutée :** `setCurrentDeviceLanguage`<br /><br />À partir de cette version, la langue n'est plus collectée automatiquement par le SDK. |
| 6.3.4 | 21/07/2021 |  | <ul><li>**Correction :** correction d'un problème lié à l'exécution du SDK sur les simulateurs XCode 12.5</li><li>Corrections et mises à jour mineures.</li></ul> |
| 6.3.2 | 2021-06-17 |  | Amélioration des journaux de débogage. |
| 6.3.1 | 2021-06-02 | Oui | Amélioration de la stabilité du plugin Unity. |
| 6.3.0 | 13/05/2021 |  | <ul><li>Prise en charge d'Apple Silicon : ajout d'un support pour exécuter le SDK sur un simulateur utilisant des appareils Mac avec le chipset M1</li><li>À partir de cette version, le SDK prend en charge iOS `9+`. iOS `8` n'est plus pris en charge.</li><li>SDK iOS Strict Mode : ajout du support pour le gestionnaire de dépendances Carthage</li><li>Mise à jour technique de l'API OneLink</li></ul> |
| 6.2.6 | 25/04/2021 |  | <ul><li>Correction : les règles SKAdNetwork ne se chargeaient pas lorsque l'initialisation du SDK avait lieu après `didFinishLaunchingWithOptions`.</li><li>Correction : erreur `waitForATTUserAuthorization` générant l'envoi de l'événement de lancement sans IDFA malgré le consentement de l'utilisateur</li><li>SDK compatible avec les appareils iOS 8</li><li>Nettoyage et suppression du code et des données inutilisés</li></ul> |
| 6.2.5 | 06/04/2021 |  | Refonte, nettoyage, suppression des données inutilisées du SDK.<br /><br />À partir de cette version :<ul><li>La méthode `setShouldCollectDeviceName` est obsolète et ne renvoie pas le nom de l'appareil</li><li>Le paramètre `wifi` envoyé par le SDK est défini sur `False`.</li></ul> |
| 6.2.4 | 15/03/2021 |  | Correction d'un bug lié au mode de mesure des revenus de SKAdNetwork, ainsi qu'aux événements in-app qui contiennent le paramètre `AF_REVENUE`.<br /><br />À partir de cette version, concernant la mesure des revenus : tout événement contenant `AF_REVENUE` affecte la valeur de conversion. Avant cette modification, la valeur de conversion n'était fixée que si elle se trouvait dans l'infrastructure de l'évènement `AF_PURCHASE`. <br /><br />**Remarque :** si vous implémentez la mesure des revenus de SKAdNetwork, vous devez passer à cette version. |
| 6.2.3 | 07/03/2021 |  | Correction d'un bug lié à l'appel de la fonction `updateConversionValue` de SKAdNetwork. |
| 6.2.2 | 18/02/2021 | Oui |  |
| 6.2.1 | 15/02/2021 |  | Assistance <Anchor target="_blank" href="/marketers/fr/docs/server-to-server-events-api-for-mobile-s2s-mobile">Rapport d'événements par S2S</Anchor> |
| 6.2.0 | 07-02-2021 |  | API supplémentaire : <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setpartnerdata">setPartnerData</Anchor> |
| 6.1.4 | 12-01-2021 | Oui |  |
| 6.1.3 | 24/12/2020 |  | <ul><li>API supplémentaire : <Anchor target="_blank" href="/marketers/fr/docs/additional-sdk-integration-guide#record-push-notifications">`addPushNotificationDeepLinkPath`</Anchor> (prend en charge Movable Ink)</li><li>Assistance <Anchor target="_blank" href="https://developer.apple.com/documentation/adservices">Apple AdServices Framework</Anchor></li></ul> |
| 6.1.2 | 03/12/2020 | Oui |  |
| 6.1.1 | 17/11/2020 |  | Introduire le <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">SDK en mode strict</Anchor> |
| 6.1.0 | 09/11/2020 |  | Assistance <Anchor target="_blank" href="https://dev.appsflyer.com/docs/ios-unified-deep-linking">API de deep linking unifié</Anchor> |
| 6.0.8 | 28/10/2022 |  | Assistance attribution <Anchor target="_blank" href="/marketers/fr/docs/apple-app-clips-integration-guide">Apple App Clips</Anchor> |
| 6.0.7 | 21/10/2021 | Oui |  |
| 6.0.6 | 20/10/2020 | Oui |  |
| 6.0.5 | 08/10/2020 | Oui |  |
| 6.0.4 | 30/09/2020 |  | Prise en charge de redirections multiples à partir d'ESP |
| 6.0.3 | 06/09/2020 |  | <ul><li>Changement de nom de l'API :<br />waitForAdvertisingIdentifier --> waitForATTUserAuthorization</li><li>Le SDK collecte l'IDFA par défaut pour iOS 14 (comme pour les versions précédentes d'iOS)</li></ul> |
| 6.0.2 [obsolète] | 27/08/2020 |  | <ul><li>Changement de nom de l'API :<br />deviceLoggingDisabled --> anonymizeUser</li><li>Le boîte de dialogue AppTrackingTransparency (ATT) est nécessaire pour collecter l'IDFA avec iOS 14</li><li>Ajout d'un support pour l'attribution des promotions croisées IDFV</li></ul> |
| 6.0.1 beta<br /><br />[obsolète] | 06/08/2020 |  | <ul><li>Ajout d'une assistance pour l'<Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">attribution SKAdNetwork</Anchor>, afin d'aider les annonceurs à mesurer le succès de leurs campagnes tout en préservant la confidentialité des utilisateurs.</li></ul> |
| 6.0.0 beta<br /><br />[obsolète] | 04/08/2020 |  | <ul><li>Capacités de débogage étendues</li><li>Changements majeurs dans les fonctionnalités du SDK et de l'API. [En savoir plus](/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes)</li></ul> |

<div id="ios-v600-release-notes" />

<Accordion title="Notes de publications iOS V6.0.0">

### Méthodes ajoutées, supprimées ou renommées

#### Méthodes ajoutées

Les méthodes suivantes ont été ajoutées au SDK :

* waitForAdvertisingIdentifier

#### Méthodes retirées

Les méthodes suivantes ont été supprimées du SDK :

* disableAppleAdSupportTracking

#### Méthodes renommées

| Nom de l'API (avant V6) | Nom de l'API actuelle (V6 et suivantes) |
| --- | --- |
| AppsFlyerTracker | AppsFlyerLib |
| disableIAdTracking | disableCollectASA |
| trackAppLaunchWithCompletionHandler | startWithCompletionHandler |
| trackLocation | logLocationEvent |
| trackAppLaunch | Démarrer |
| trackEvent | logEvent |
| disableAppleAdSupportTracking | disableAdvertiserIdentifier |
| validateAndTrackInAppPurchase | validateAndLogInAppPurchase |
| isStopTracking | isStopped |
| deviceTrackingDisabled | deviceLoggingDisabled |
| sharedTracker (Objective C) | Partagé |

### Support App Tracking Transparency (ATT)

Le SDK iOS prend en charge la collecte de l'IDFA sur iOS 14+ via l'infrastructure App Tracking Transparency. Pour plus d'informations :

* <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">Configurer le support ATT dans le SDK iOS</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#customize-att-consent-dialog">Personnalisation de la boîte de dialogue de consentement au TCA</Anchor>

</Accordion>

## iOS SDK V5

<div id="ios-sdk-v5::7a4821ba" />

<Accordion title="iOS SDK V5">

| Version | Date de sortie | Remarques |
| --- | --- | --- |
| 5.4.4 | 23/08/2020 | Correction des bugs et maintenance |
| 5.4.3 | 2020-07-30 | <ul><li>Capacités étendues de logging et de débogage</li><li>Correction des bugs et maintenance</li></ul> |
| 5.4.1 | 30-06-2020 | <ul><li>Permettre aux annonceurs de contrôler le partage des données avec les partenaires/réseaux intégrés. <Anchor target="_blank" href="/marketers/fr/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">En savoir plus</Anchor></li><li>La méthode onAppOpenAttribution a été améliorée pour les URL longues des liens universels : les paramètres du lien sont renvoyés déjà analysés</li><li>Correction des bugs et maintenance</li></ul> |
| 5.4.0 | 2020-06-03 | Support MAC Catalyst |
| 5.3.0 | 27/04/2020 | <ul><li>Accès aux dernières données de conversion de deep linking direct via la méthode onAppOpenAttribution</li><li>Paramètres supplémentaires disponibles pour les impressions de promotion croisée</li><li>Les applications principales et les extensions d'applications reçoivent le même identifiant AppsFlyer, les événements in-app sont donc regroupés de la même manière</li><li>Correction des bugs et maintenance</li></ul> |
| 5.2.0 | 10/03/2020 | <ul><li>Capacités étendues de logging et de débogage</li><li>Correction des bugs et maintenance</li></ul> |
| 5.1.0 | 23/12/2019 | <ul><li>Amélioration de l'interopérabilité Obj-C - Swift</li><li>Correction des bugs et maintenance</li></ul> |

</Accordion>

<div id="ios-v500-release-notes" />

<Accordion title="Notes de publications iOS V5.0.0">

### Amélioration du temps de réponse du SDK

À partir du SDK V5.0.0, le temps de réponse de la GCD a été amélioré pour les installations organiques.

### Méthodes supprimées ou renommées

#### Changements de noms de méthodes

Les noms des méthodes de conversion des données d'installation sont désormais les mêmes pour Android et iOS. Cela a un impact sur les méthodes qui gèrent :

* Données de conversion à l'installation
* Erreurs si les données ne sont pas disponibles

| Nom pour Android avant le SDK V5 | Nom pour l'iOS avant le SDK V5 | Nom standardisé |
| --- | --- | --- |
| `onInstallConversionDataLoaded` | `onConversionDataReceived` | `onConversionDataSuccess` |
| `onInstallConversionFailure` | `onConversionDataRequestFailure` | `onConversionDataFail` |

#### Méthodes retirées

Les méthodes suivantes étaient obsolètes dans les versions précédentes du SDK. Elles ont maintenant été retirées du SDK.

**Android**

* setGCMProjectID (String projectNumber)
* setGCMProjectNumber (String projectNumber)
* setGCMProjectNumber (Context context, String projectNumber)
* enableUninstallTracking (String senderId)
* setAppUserId (String id)
* setUserEmail (String email)
* setCollectFingerPrint (booléen isCollect)
* getAttributionId (ContentResolver contentResolver)
* Classe FirebaseInstanceIdListener (instance de FirebaseInstanceIdService)

 iOS

* loadConversionDataWithDelegate: (id`<AppsFlyerTrackerDelegate>`) delegate
* setHost :(NSString *) host

#### Modifications du format des données de conversion

Dans cette version, pour chaque installation ou ouverture d'application, le SDK renvoie un objet map qui contient des données de conversion (GCD), comme la source média ou le nom de la campagne. Dans les versions précédentes du SDK, GCD ne retournait que les paramètres qui contenaient une valeur

À partir de cette version, tous les paramètres sont retournés, y compris ceux qui n'ont pas de valeur. Les paramètres sans valeur ont la valeur nulle.

> 📄 **Exemple**
>
> Une installation suit un clic sur l'URL suivante :
>
> ```http
> https://app.appsflyer.com/com.sample.app?pid=super_media_source&c=awesome_campaign
>  & campaign_id=1234&af_sub1=promo
> ```
>
> Les réponses sont les suivantes :
>
>
> <Tabs>
> <Tab title="Réponse du GCD avant le SDK V5">
>
> ```json
>    {
>       "install_time": "2019-11-11 15:00:59.828",
>       "media_source": "super_media_source",
>       "orig_cost": "0.0",
>       "advertising_id": "215d8172-c61e-4d0c-9eb2-aa4d0971ed8c",
>       "af_status": "Non-organic",
>       "is_first_launch": true,
>       "af_sub1": "promo",
>       "af_click_lookback": "7d",
>       "cost_cents_USD": "0",
>       "iscache": "true",
>       "click_time": "2019-11-11 15:00:35.102",
>       "campaign": "awesome_campaign",
>       "campaign_id": "1234",
>   }
> ```
>
> </Tab>
>
> <Tab title="Réponse du GCD à partir du SDK V5">
>
> ```json
>    {
>       "adgroup": null,
>       "campaign": "awesome_campaign",
>       "media_source": "super_media_source",
>       "adset_id": null,
>       "campaign_id": 1234,
>       "iscache": true,
>       "install_time": "2019-11-11 15:00:59.828",
>       "adgroup_id": null,
>       "af_sub5": null,
>       "click_time": "2019-11-11 15:00:35.102",
>       "agency": null,
>       "cost_cents_USD": "0",
>       "advertising_id": "215d8172-c61e-4d0c-9eb2-aa4d0971ed8",
>       "adset": null,
>       "af_sub3": null,
>       "af_siteid": null,
>       "http_referrer": null,
>       "orig_cost": "0.0",
>       "af_sub4": null,
>       "af_cpi": null,
>       "af_sub1": "promo",
>       "af_click_lookback": "7d",
>       "af_sub2": null,
>       "af_status": "Non-organic",
>       "is_first_launch": true,
>       "retargeting_conversion_type": "none"
>   }
> ```
>
> </Tab>
> </Tabs>
>

GCD renvoie la même structure, quelles que soient les données. Si un paramètre est vide, il est inclus dans le GCD avec la valeur nulle. Les développeurs peuvent ainsi traiter plus facilement les GCD sans devoir adapter leur logique de traitement, et ce que certains paramètres soient inclus ou non. Pour en savoir plus sur les données de conversion en fonction des cas, cliquez <Anchor target="_blank" href="/marketers/fr/docs/conversion-data-payloads-and-scenarios">ici</Anchor>.

</Accordion>

<div id="deprecated-versions" />

<Accordion title="Versions obsolètes">

Lecture connexe : <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-sdk-version-control-policy">Politique de contrôle des versions du SDK AppsFlyer</Anchor>

| Version | Date de sortie | Remarques |
| --- | --- | --- |
| 5.0.0 | 12/11/2019 | <ul><li>Correction des bugs et maintenance</li><li>Changements majeurs dans les fonctionnalités du SDK et de l'API. [En savoir plus](/docs/appsflyer-ios-sdk-release-notes#ios-v500-release-notes)</li></ul> |
| 4.11.2 | 07/11/2019 | Correction des bugs et maintenance |
| 4.11.1 | 31/10/2019 | Correction des bugs et maintenance |
| 4.11.0 | 17/10/2019 | <ul><li>La prise en charge d'iOS 7 a stoppé. iOS 8 est désormais la version minimum prise en charge.</li><li>Amélioration des journaux pour de meilleures capacités de débogage, la résolution des liens ESP et de marque ainsi que pour onInstallConversionData et onAppOpenAttribution.</li><li>Amélioration de la collecte de données Apple Search Ads.</li></ul> |
| 4.10.4 | 12/09/2019 | <ul><li>Mise à jour pour la récupération du jeton push iOS 13 nécessaire pour la mesure des désinstallations</li><li>Correction des bugs et maintenance</li></ul> |
| 4.10.3 | 16/07/2019 | Correction des bugs et maintenance |
| 4.10.2 | 02/07/2019 | Correction des bugs et maintenance |
| 4.10.1 | 01/07/2019 | Correction des bugs et maintenance |
| 4.10.0 | 14/05/2019 | <ul><li>API trackAppLaunchWithCompletionHandler pour gérer le succès ou l'échec du lancement d'une application de tracking</li><li>API completionHandler pour gérer le succès ou l'échec de l'enregistrement des événements in-app</li><li>Correction des bugs et maintenance</li></ul> |
| 4.9.0 | 18/03/2019 | <ul><li>API setResolveDeepLinkURLs pour la résolution des OneLinks encapsulés dans un autre lien universel</li><li>Suppression de l'utilisation de l'UIPasteboard pour l'attribution Meta ads pour iOS 7 et -</li><li>Correction des bugs et maintenance</li></ul> |
| 4.8.12 | 13/02/2019 | <ul><li>Amélioration des capacités de notation zéro pour les fournisseurs de téléphonie mobile.</li><li>Amélioration des capacités de notation zéro pour les fournisseurs de téléphonie mobile.</li><li>Correction des bugs et maintenance</li></ul> |
| 4.8.11 | 09/01/2019 | <ul><li>Correction de l'API waitForCustomerUserId() API qui cassait generateLink</li></ul> |
| 4.8.10 | 31/10/2018 | <ul><li>Correction d'un problème de concurrence lorsque continueUserActivity était appelé après applicationDidBecomeActive, qui empêchait onAppOpenAttribution d'être appelé.</li><li>validateAndTrackInAppPurchase ignore la correction des paramètres supplémentaires</li><li>Correction des bugs et maintenance</li></ul> |
| 4.8.9 | 27/08/2018 | <ul><li>Événements SDK supplémentaires : Abonnement, Essai démarré, Clic sur une publicité, Affichage d'une publicité</li><li>Correction des bugs et maintenance</li></ul> |
| 4.8.8 | 30/07/2018 | <ul><li>Correction d'un problème lorsque l'utilisation de is\_first\_launch par JSONSerialiser était retournée sous la forme entière plutôt que booléenne.</li><li>Correction des bugs et maintenance 4.8.7</li></ul> |
| 4.8.7 | 22/07/2018 | Correction des bugs et maintenance |
| 4.8.6 | 18/06/2018 | Correction des bugs et maintenance |
| 4.8.5 | 29/05/2018 | Correction des bugs et maintenance |
| 4.8.4 | 03/05/2018 | Correction des bugs et maintenance |
| 4.8.3 | 25/01/2018 | <ul><li>Correction des bugs et maintenance</li><li>API shouldCollectDeviceName</li><li>Paramètre d'événement af\_content</li><li>API shouldCollectDeviceName</li><li>Paramètre d'événement af\_content</li></ul> |

</Accordion>

## Checksums du SDK iOS

AppsFlyer utilise des checksums md5 :

<div id="v6-checksums" />

<Accordion title="Checksums V6">

| Version du SDK iOS | Static Lib | Static Framework |
| --- | --- | --- |
| 6.6.1 | ff41a3dfeb9fe7579f8f706f3c62bbbc | 7acf1f10de7602b363a70d4a710b050d |
| 6.6.0 | ba2d2d0b64f3b0f6476b818c1b8faf5f | 544c7c7e4af29afa4100b6c43affcf8f |
| 6.5.4 | 5a1146a95abc84b20940b43cacc8b42a | 3a0a22a28b4082a5b2f0931104b0a9c8 |
| 6.5.3 | b33008f83f5eafa864902db97c003c06 | 3ff6754c8c238dd13e4c6251ffb4aedf |
| 6.5.2 | 3083df065d14553fb1b4e34f3f7fb381 | 3ce0ea75e4fe3cf6313fde27d57d20ed |
| 6.5.1 | 8d91f52cc2df073d1bca9919b44aeeeb | c9353bdfa71ff9b4acc9097eee83d35e |
| 6.5.0 | 4b72dcf125430d3d374967df5e084c6a | 5d6ac0e9f7a1430e106685da117a7716 |
| 6.4.4 | 86586acda674d95f5661a613dccea3dd | 7f4c431de13b84fd0926132c2154f0a8 |
| 6.4.3 | dd5fcf42065ba2ad28f6311153fd4752 | 178274e63a6aa604682a3095ddf59ac5 |
| 6.4.2 | 2341911e4f34d17560b85409b86528c4 | 46df5badc29ee983a872d7859cedd59a |
| 6.4.1 | 4ef6e6d424bc9b95a1ee8ebda0d5c639 | 0efc4140b47cbaf65b24a9087c61c434 |
| 6.4.0 | 9210f7064a7692c8dff7a779043e97fc | f103763da687fef88db60ca6b395dc41 |
| 6.3.5 | b61193ab28a601ec0dfaf4aa641a7834 | 9fbbf0f4cb865c95d919396d2af9a053 |
| 6.3.4 | 9cca998fde11c473e60bee3854f0c0da | c47a02177c28290ed8c934a6428dc0dc |
| 6.3.2 | c563e2b8ee4bf6647e496d1b0ad31285 | 5c474247d3ce607fca43af9c9faf1fbc |
| 6.3.1 | e04a567680676b3784079d35ca32b5fe | 36b808db3952803c929188ca57fe88c6 |
| 6.3.0 | baa5e6d82a363e636740d6c5494e107d | f2ebe86a93a2fd5122ad11224f17736c |
| 6.2.6 | 9b989e131fe596b51223b6f47efac3c6 | 6396371abf0f66f0e6aeccd8303eeb0a |
| 6.2.5 | 5b23262cb4b15230e262005b648aff0d | 85ec7457b36de4402ce2c4b591fa87ab |
| 6.2.4 | f61648cd99d94c05d50a6e3213329779 | 3b20d45695f5e196e78d3db6c2bd738d |
| 6.2.3 | 51eaa0654ec83db7da31511092312f00 | d540bdc543a06ff5ccd40f90b2078557 |
| 6.2.2 | 9e5ceb08a3121f42b3315da87c698af3 | 08917804e4fe48bcb797f391d5a111f6 |
| 6.2.1 | cbfe915e31bc06bb28227cb33ed22304 | abfa9d9dc81fd90b0ca65de973fb1ab8 |
| 6.2.0 | 652ee1362af8c93119335a337deba1a5 | 91bb64493b344b010ebc277c849e9234 |
| 6.1.4 | 7e2e74d3cc186807d73c1fcf57f8b117 | 6c9b4ed760c9c1139681f61e6a508c8e |
| 6.1.3 | 749e6c3de91afdfcddec91d290c46807 | ab5884cb0c1ea00c3b3fe9a1d26a4511 |
| 6.1.2 | 940da06a6f8f7e3931a2a80f4e8defc9 | 4d39c9e6d46c49b5bde2c5ff19781957 |
| 6.1.1 | 7d259bd1cc5e5d2c3fea4909953375ba | 09a273cf0300656ed995405e41eced58 |
| 6.1.0 | e95e509d48e7b87e0213c7f12ea253e4 | 2c87f3a79c9318a4ed49ad8c377b007f |
| 6.0.8 | d903e6c145492488e126e46b3a233444 | 3237e91d12ee0871ceb0f6a0829dd43b |
| 6.0.7 | 2d83f856d8d34c4f2e0e4e8561ddee05 | bbb742ded1e49eae0622deb40c3becc3 |
| 6.0.6 | 1dd3bfc9919db8ccb7c0de8cf6505d47 | 5d5e5fe1624123f8316c6bdc020aa47b |
| 6.0.5 | e8afac7ef0bc7e38432bf5187fcbde7d | 41966239e783ce0bbba852471a439caa |
| 6.0.4 | a88278fdb8c2f504ecb4406b8fbc1fe4 | a7bba01c6484baf721f5be51242c492b |
| 6.0.3 | 9f0cfed3c889ba3e334857c6d81e26be | 13b07e2da8316759a8f84efb2476e854 |
| 6.0.2 |  | 13936cb4e05221e134ae1539971b9317 |
| 6.0.1 beta |  | 6167276b56ac3b1fbdad2a4858b17bf3 |

</Accordion>

<div id="v5-checksums" />

<Accordion title="Checksum V5">

| Version du SDK iOS | Static Lib | Static Framework |
| --- | --- | --- |
| 5.4.4 | 47d90cbc4ed48dd1c5d6f42a8d419e8b | 93716e13258fce87c81c0fc604bfd6fd |
| 5.4.3 | e5691c3ae1f20726168b4eb221937d98 | dbfa30607f44fa2819191c7a8d7a3fe4 |
| 5.4.1 | 61564250f26ab0693255e002873d1674 | fc86776f0ffcdf65cc49f33f7d943258 |
| 5.4.0 | fa835b3577f389a12ef635eea0b000bb | 0bd6a7b4441dc8f397831533e719a833 |
| 5.3.0 | e787da7334e6c68e0098fd53ebea285e | 2f160176b1c011f9aca558543cd63190 |
| 5.2.0 | 057c18bb7485e1c06f2b452d80ee5b22 | 736b50840b8c08093401f3bba2c4389b |
| 5.1.0 | f39819c11b06f98ff24e39cbd0f0f6ce | 39889a253dafcfb2d53151523c1c1d80 |
| 5.0.0 | 5ac9e35af65fbfcaf81c1f63a36542b9 | 1727be9fa19906f0c1e1907b4b160086 |

</Accordion>

<div id="v4-checksums" />

<Accordion title="Checksum V4">

| Version du SDK iOS | Static Lib | Static Framework |
| --- | --- | --- |
| 4.11.2 | f5415c2014402a03b8ca2c9901ddf12d | 3fcf5afd6a20f353f7f88f1fbb4d4410 |
| 4.11.1 | 716394142df4d8e7a98e2c11cfe92ed1 | e6521d8216d3aa8d681ac74e279dab34 |
| 4.11.0 | e7238410372dfa7ca65e5839a31b1c2e | c6d3283bf69adb75aa9ed6c43195a3d6 |
| 4.10.0 | 4d5c01129b80d7ad182e32cf3b47faa4 | da926eeb09d61f68f2076a9b31c30d7a |
| 4.9.0 | d283ace3237479d1aabc2a81271ea5ba | bad6d9b8c627d7450e7acc8165b05618 |
| 4.8.9 | e9640a7f95257a89c3e99215df79f1df | fb0975064d2b93cedb71ce248cf3afb9 |
| 4.8.4 | b7748ea6b86afbc295e17bac3d5bdda6 | 4cd7a95f49cfb79ecd9a0ce0c73750a3 |
| 4.8.3 | 51d38c4b77f39c75c5fc5734165fedc2 | 23096a32726a9def3e215a761bf7ad30 |
| 4.8.2 | 0908336d4e9bcf4de1d5f4f2e37ad0cb | a386cfadd76fd783e6a10d0cd8fcb685 |
| 4.8.1 |  | 3b8a7d70b96bd7c5718feafeb31296b9 |
| 4.8.0 | bb1358226bd3ca70d70f4717b62ca38b | 3d81144bb653e91cb624778c87641051 |
| 4.7.9 | e9183f23954a3f42a9fa6ae3eeebb6df | 03905309048e26e9be7ee02895532d11 |
| 4.7.8 | 5595fa7dfc4c13b4a955638ba1da062e | 61c30629f3dcb5ae48da10a458e80d28 |
| 4.7.7 | 3a8d0be3b304de5e81c967ab8a465de3 | b8dd0ee60c75aa30884f56569068f32e |
| 4.7.6 | 6cc80a31cf9daae5709a22258f434c6d | 3d4607b13b6f138264db703e36f5452e |
| 4.7.3 | 73db4e0173fcfdb758644b08fdbbd7bf | 06572392afe0ae28a814601642963469 |
| 4.7.2 | 14a79e4ecffad264bc62b307d2db23a7 | 0aae1d0ace09e5b092f9906747119cfd |
| 4.7.11 | 27e228c921f560205c0ad2c7962e83b2 | d94cdab5734a88598cfcc078573e5b21 |
| 4.7.10 | 5cb1275b488369fee4713d21812186a0 |  |
| 4.7.1 | b121dfdf8d0dc53d031481114eba0c18 | 74ac06d17f167a0e22c361e06f4a2554 |
| 4.7.0 | c3c0a453caa9971492ef8acd8bee04ae | cadeab0479c4a723173943d77d253051 |

</Accordion>

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/about-att-and-skan">Guide de démarrage rapide pour iOS 14, ATT et SKAdNetwork</Anchor>

<div data-zendesk-anchors="01H8W3DDM1BYRSPMFTA3TCY8EQ=ios-sdk-v6 01EEYC8A6FEW8WN28KQ9CKX0G7=ios-v600-release-notes methods-added-removed-or-renamed=m%C3%A9thodes-ajout%C3%A9es-supprim%C3%A9es-ou-renomm%C3%A9es 01EEYC8A6FD7JZK1A63EF675HJ=m%C3%A9thodes-ajout%C3%A9es-supprim%C3%A9es-ou-renomm%C3%A9es methods-added=m%C3%A9thodes-ajout%C3%A9es 01EEYC8A6FKPYQ35EKVW7X0EC0=m%C3%A9thodes-ajout%C3%A9es methods-removed=m%C3%A9thodes-retir%C3%A9es 01EEYC8A6FNJ91R15X633BHSXF=m%C3%A9thodes-retir%C3%A9es methods-renamed=m%C3%A9thodes-renomm%C3%A9es 01EEYC8A6F8PB4C94Z14KXYD68=m%C3%A9thodes-renomm%C3%A9es app-tracking-transparency-att-support=support-app-tracking-transparency-att 01EEYC8A6G19ER7FGWQ51XPGJF=support-app-tracking-transparency-att 01EEYC8A6GYYRK4F7CVT7YMTHJ=ios-sdk-v5 01H8W3DDM19M6R8AV62WKZ931G=ios-sdk-v5::7a4821ba 01EEYC8A6GR18M6KN5D2ZV2573=ios-v500-release-notes improved-sdk-response-time=am%C3%A9lioration-du-temps-de-r%C3%A9ponse-du-sdk 01EEYC8A6GF3MF7GJZWCE9TY88=am%C3%A9lioration-du-temps-de-r%C3%A9ponse-du-sdk methods-removed-or-renamed=m%C3%A9thodes-supprim%C3%A9es-ou-renomm%C3%A9es 01EEYC8A6G3KWSZ3FGKF904QM1=m%C3%A9thodes-supprim%C3%A9es-ou-renomm%C3%A9es method-name-changes=changements-de-noms-de-m%C3%A9thodes 01EEYC8A6G1EFHXBMW229RTKYA=changements-de-noms-de-m%C3%A9thodes methods-removed::92ba13cc=m%C3%A9thodes-retir%C3%A9es-1 01EEYC8A6GE57XWGHTNQSAN516=m%C3%A9thodes-retir%C3%A9es-1 changes-to-get-conversion-data-format=modifications-du-format-des-donn%C3%A9es-de-conversion 01EEYC8A6HVPFA5K349KHT5B3T=modifications-du-format-des-donn%C3%A9es-de-conversion 01EEYC8A6HG072RP472KEQ74S8=exemple 01H8W3DDM1G62RTK2S3XEG3KGT=deprecated-versions ios-sdk-checksums=checksums-du-sdk-ios 01EEYC8A6J6VF2WEPFEC9JRVA9=checksums-du-sdk-ios 01EEYC8A6J77PYMCNDEGWZD3FJ=v6-checksums 01EEYC8A6JGHWTNJY0C06PD7H6=v4-checksums h_01HE7RE2EPQX872DKNDBJ2G2QE=%C3%A0-consulter-%C3%A9galement" />
