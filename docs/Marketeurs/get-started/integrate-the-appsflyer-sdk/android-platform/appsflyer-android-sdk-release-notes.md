---
title: Notes de publication du SDK Android AppsFlyer
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
  created_at: '2017-03-09T20:17:19Z'
  edited_at: '2023-10-27T11:13:10Z'
  id: 115001256006
  locale: fr
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/fr/articles/115001256006
---
> **En bref :** notes de version du SDK Android à partir de la V4.x.

## SDK Android V6

<Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">Guide d'intégration du SDK Android pour les marketeurs</Anchor>

| Version | Date de sortie | Maintenance uniquement | Remarques |
| --- | --- | --- | --- |
| 6.12.4 | 25/10/2023 |  | <ul><li>Dexguard a été mis à jour vers la version 9.4.16 pour améliorer la stabilité du SDK.</li></ul> |
| 6.12.3 | 31/08/2023 | Oui |  |
| 6.12.2 | 02/08/2023 |  | <ul><li>Correction d'un bug pouvant entraîner le plantage de l'application sur certains appareils sous Android 8.1.0 et Android 11.</li></ul> |
| 6.12.1 | 29/06/2023 |  | <ul><li>Correction d'une erreur qui retardait le lancement du Play Store lors d'une promotion croisée.</li><li>Correction d'un bug provoquant le plantage de l'application sur certains appareils.</li></ul> |
| 6.12.0 | 28/06/2023 |  | <ul><li>Obsolète - veuillez utiliser la version 6.12.1.</li></ul> |
| 6.11.2 | 29/06/2023 |  | <ul><li>Correction d'un bug provoquant le plantage de l'application sur certains appareils.</li></ul> |
| 6.11.1 | 06/06/2023 |  | <ul><li>Obsolète - veuillez utiliser la version 6.12.1.</li><li>Correction d'un bug qui bloquait parfois l'app après l'initialisation du SDK.</li></ul> |
| 6.11.0 | 16/05/2023 |  | <ul><li>Correction d'un problème qui pouvait bloquer l'application sur certains appareils lorsque le SDK cherchait à obtenir le référent Google Play.</li></ul> |
| 6.10.3 | 25/04/2023 | Oui |  |
| 6.10.1 | 01/03/2023 |  | <ul><li>Correction d'un problème qui pouvait entraîner la fermeture des applications sur les appareils Samsung lors de l'initialisation du SDK. Ce problème concernait les applications ayant le SDK V6.6.0 et +.</li></ul> |
| 6.10.0 | 13/02/2023 |  | <ul><li>Nouveau domaine AppsFlyer pour que le SDK communique avec les serveurs AppsFlyer.</li><li>Modification de l'API setHost lorsque des valeurs vides ou nulles sont envoyées. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#sethost">En savoir plus</Anchor></li></ul> |
| 6.9.4 | 06/12/2022 |  | <ul><li>Correction de l'erreur qui faisait que l'envoi d'un événement de revenu publicitaire depuis le connecteur SDK de revenu publicitaire déclenchait un appel vers le port d'écoute de conversion.</li><li>Correction de l'erreur qui bloquait parfois les apps lorsqu'un événement de revenu publicitaire était envoyé par le connecteur SDK des revenus publicitaires.</li></ul> |
| 6.9.3 | 28/11/2022 |  | <ul><li>Mise à jour de la structure de demande interne pour Get Conversion Data (GCD). **Remarque :** les données transmises dans les réponses restent identiques.</li><li>Correction de l'erreur qui faisait que le SDK déclenchait une demande GCD lorsque l'app avait ConversionListener défini sur *null*.</li></ul> |
| 6.9.2 | 02/10/2022 |  | <ul><li>Correction du retard dans la demande de validation d'un achat via l'API validateAndLogInAppPurchase.</li></ul> |
| 6.9.1 | 10/09/2022 | Oui |  |
| 6.9.0 | 12/09/2022 |  | <ul><li>Ajout de la prise en charge de Xiaomi GetApps Store Referrer.</li><li>Mise à jour de l'API interne pour le reporting des revenus publicitaires. À partir de cette version, seul le <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">connecteur SDK générique pour les revenus publicitaires</Anchor> est pris en charge.</li></ul> |
| 6.8.2 | 29-08-2022 |  | <ul><li>Correction d'une erreur de mécanisme de mise en cache du SDK introduit dans la V6.7.0, et qui entraîne l'envoi répété des événements mis en cache.</li></ul> |
| 6.8.1  <br />(obsolète) | 24-08-2022 | Oui | <ul><li>**Obsolète.** Merci d'utiliser la V6.8.2.</li></ul> |
| 6.8.0  <br />(obsolète) | 18-07-2020 |  | <ul><li>**Obsolète.** Merci d'utiliser la V6.8.2.</li><li>Retrait du SDK de l'API `enableLocationCollection`. L'application peut toujours communiquer les données de localisation de l'utilisateur en les transmettant directement au SDK via l'API `logLocation`.</li><li>Ajout de l'autorisation `com.google.android.gms.permission.AD_ID` au SDK `AndroidManifest.xml`. Pour en savoir plus, rendez-vous <Anchor target="_blank" href="/marketers/fr/docs/bulletin-the-android-sdk-adds-the-ad-id-permission">ici</Anchor>.</li><li>Correction d'un problème d'optimisation et d'obfuscation avec R8.</li></ul> |
| 6.7.0  <br />(obsolète) | 19/06/2022 |  | <ul><li>**Obsolète.** Merci d'utiliser la V6.8.2.</li><li>Modification de la manière dont le SDK traite les demandes envoyées aux serveurs AppsFlyer. Suite à ce changement, la demande de rapport sur la première ouverture de l'app (conversion) sera prioritaire sur les événements in-app et aux autres types de demandes. Pour en savoir plus, rendez-vous <Anchor target="_blank" href="/marketers/fr/docs/bulletin-adding-a-priority-queue-to-the-android-sdk">ici</Anchor>.</li><li>**Nouvelle API :** `setDisableNetworkData` pour refuser de collecter les informations sur le réseau cellulaire (nom du transporteur, nom de l'opérateur).</li></ul> |
| 6.6.1 | 16/05/2022 | Oui |  |
| 6.6.0 | 01/05/2022 |  | <ul><li>Ajout de paramètres au callback `onDeepLinking` du UDL pour le flux de deep linking direct (utilisateurs existants). <Anchor target="_blank" href="/marketers/fr/docs/bulletin-additional-parameters-available-for-deep-linking-existing-users">En savoir plus</Anchor></li></ul> |
| 6.5.4 | 23/03/2022 | Oui |  |
| 6.5.3 | 09/03/2022 |  | <ul><li>**Correction :** correction du problème de création de liens d'invitation utilisateurs contenant des caractères non latins.</li></ul> |
| 6.5.2 | 26/01/2022 |  | <ul><li>Correction d'un problème de résolution de l'URL pour les deep links différés dans UDL.</li><li>Mise à jour vers DexGuard 9.2</li><li>Remaniement et changements internes.</li></ul> |
| 6.5.1 | 29/12/2021 |  | <ul><li>Résolution du deep linking avec UDL pour les apps qui utilisent l'option <Anchor target="_blank" href="/marketers/fr/docs/set-up-multi-store-android-attribution#channel-name">Hors-store avec un canal</Anchor>.</li></ul> |
| 6.5.0 | 07-12-2021 |  | <ul><li>Remaniement et changements internes.</li></ul> |
| 6.4.3 | 14/11/2021 |  | <ul><li>Correction d'un bug introduit dans  `V6.4.2` avec `LinkGenerator`  qui génère des liens avec des paramètres URL manquants.</li></ul> |
| 6.4.2 | 24/10/2021 |  | Les problèmes suivants ont été résolus :<ul><li>`pid` paramètre ajouté deux fois aux URL personnalisées générées par `LinkGenerator`.</li><li>Un `/` en plus était ajouté à la valeur `af_dp` lors de l'utilisation de `LinkGenerator` pour créer des schémas d'URI personnalisés.</li><li>L'IMEI et l'AndroidID étaient tous les deux été collectés lorsque l'application déclenchait la collecte d'un seul d'entre eux.</li></ul> |
| 6.4.1 | 17/10/2021 |  | Résolution d'une erreur de compilation lors de l'utilisation d'une version de Gradle antérieure à la V3.5.4. |
| 6.4.0 | 12/09/2021 |  | **Nouvelle API :** `setSharingFilterForPartners` vous permet de configurer les partenaires que le SDK ne doit pas inclure dans le partage des données.<br /><br />Depuis cette version, `setSharingFilter` et `setSharingFilterForAllPartners` sont obsolètes. |
| 6.3.2 | 06/06/2021 |  | **Nouvelle API**: [`setDisableAdvertisingIdentifiers`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers) |
| 6.3.1 | 26/05/2021 |  | <ul><li>**Nouvelle API**: [`performOnDeepLinking`](https://dev.appsflyer.com/hc/docs/conversion-data)</li><li>Ajout de la possibilité de déclencher l'API <Anchor target="_blank" href="/marketers/fr/docs/user-invite-attribution#procédures">User Invite</Anchor> avant d'appeler `start`/après avoir appelé `stop`</li><li>**Correction d'un bug**: correction de l'erreur qui empêchait l'appel à `waitForCustomerUserId` d'être lancé, même après avoir appelé `setCustomerUserId`</li></ul> |
| 6.3.0 | 29/04/2021 |  | <ul><li>**Correction**: invocation erronée de `onConversionDataFail` en cas d'échec de la demande d'envoi d'un événement in-app.</li><li>**Correction de bug**: collecte des métriques des capteurs de mouvement (pour la détection des fraudes)</li><li>**Correction de bug**: correction liée à l'obfuscation dans <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl">UDL</Anchor></li><li>Mise à jour technique de l'API OneLink</li></ul> |
| 6.2.3 | 04/03/2021 | Oui |  |
| 6.2.0 | 07-02-2021 |  | <ul><li>**Nouvelle API**: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setpartnerdata">`setPartnerData`</Anchor></li></ul> |
| 6.1.4 | 12-01-2021 |  | <ul><li>Ajout de prise en charge pour DexGuard V9</li></ul> |
| 6.1.3 | 24/12/2020 |  | <ul><li>**Nouvelle API**: <Anchor target="_blank" href="/marketers/fr/docs/additional-sdk-integration-guide#record-push-notifications">`addPushNotificationDeepLinkPath`</Anchor> (prend en charge Movable Ink)</li></ul> |
| 6.1.1 | 03/12/2020 |  | <ul><li>Ajout de la prise en charge du référent Samsung Galaxy Store</li><li>Correction de bugs mineurs et amélioration des performances.</li></ul> |
| 6.1.0 | 09/11/2020 |  | <ul><li>Ajout de la prise en charge de <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl">l'API de deep linking unifiée</Anchor></li></ul> |
| 6.0.1 | 28/10/2022 | Oui |  |
| 6.0.0 | 14/10/2020 |  | <ul><li>Modifications majeures apportées aux fonctionnalités et à l'API du SDK, entre autres la dépréciation et les changements de noms de méthodes. [En savoir plus](/docs/appsflyer-android-sdk-release-notes#android-v600-release-notes)</li></ul> |

<div id="android-v600-release-notes" />

<Accordion title="Notes de mise à jour d'Android V6.0.0">

### Méthodes supprimées/obsolètes ou renommées

#### Méthodes supprimées/obsolètes

Les méthodes suivantes ont été supprimées du SDK :

* sendDeepLinkData
* trackAppLaunch
* setPluginDeepLinkData
* setConsumeAFDeepLinks
* setHostName

#### Méthodes renommées

| Nom de l'API (avant V6) | Nom de l'API actuelle (V6 et suivantes) |
| --- | --- |
| stopTracking | stop |
| setCustomerIdAndTrack | setCustomerIdAndLogSession |
| startTracking | Démarrer |
| trackLocation | logLocation |
| reportTrackSession | logSession |
| trackEvent | logEvent |
| setDeviceTrackingDisabled | anonymizeUser |
| validateAndTrackInAppPurchase | validateAndLogInAppPurchase |
| isStopTracking | isStopped |
| trackAndOpenStore | logAndOpenStore |
| trackCrossPromoteImpression | logCrossPromoteImpression |
| trackInvite | logInvite |

### Interface renommée

| Nom de l'interface (avant V6) | Nom de l'interface actuelle (V6 et suivantes) |
| --- | --- |
| AppsFlyerTrackingRequestListener | AppsFlyerRequestListener |

</Accordion>

## Android SDK V5

<div id="android-sdk-v5-release-notes" />

<Accordion title="Notes de publication du SDK Android V5">

| Version | Date de sortie | Maintenance uniquement | Remarques |
| --- | --- | --- | --- |
| 5.4.6 | 09/11/2020 |  | <ul><li>Ajout de la prise en charge du référent Huawei AppGallery.</li></ul> |
| 5.4.4 | 2020-10-01 |  | <ul><li>Ajout d'un support pour le SDK afin de gérer les redirections multiples des ESP.</li><li>Correction des bugs et maintenance</li></ul> |
| 5.4.3 | 2020-07-30 |  | <ul><li>Capacités étendues de logging et de débogage</li><li>Correction des bugs et maintenance</li><li>Prise en charge du référent d'installation Google V2</li></ul> |
| 5.4.1 | 30-06-2020 |  | <ul><li>Permettre aux annonceurs de contrôler le partage des données avec les partenaires/réseaux intégrés. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">En savoir plus</Anchor></li><li>Correction des bugs et maintenance</li></ul> |
| 5.4.0 | 2020-06-03 |  | <ul><li>Prise en charge complète de la collecte automatique d'OAID</li><li>Prise en charge multiréférents : le SDK peut collecter les référents Huawei et Google.</li><li>Amélioration des performances du SDK</li><li>Correction des bugs et maintenance</li></ul> |
| 5.3.0 | 27/04/2020 |  | <ul><li>Accéder à tout moment aux dernières données de conversion de deep linking direct via la méthode onAppOpenAttribution.</li><li>Paramètres supplémentaires disponibles pour les impressions de promotion croisée</li><li>Correction d'un bug : correction des problèmes avec les noms de fichiers a. et b. dans Windows</li><li>La méthode sendDeepLinkData, qui permet d'obtenir des données d'attribution même si l'utilisateur est lié à une activité spécifique, a été abandonnée au profit de la méthode startTracking().</li></ul> |
| 5.2.0 | 10/03/2020 |  | <ul><li>Permettre l'initialisation du SDK dans n'importe quelle activité</li><li>Sécurité étendue, logging et débogage.</li><li>Correction des bugs et maintenance</li></ul> |
| 5.1.2 | 19/02/2020 | Oui |  |
| 5.1.1 | 23/01/2020 | Oui |  |
| 5.1.0 | 06/01/2020 |  | <ul><li>Cible Android 9 (niveau 28 de l'API) selon les exigences de Google en matière de niveau d'API cible.</li><li>Améliorations des protections anti-fraude - pour les clients de Protect360</li><li>Module optionnel pour la collecte de l'OAID (valable pour le marché intérieur chinois) - Xiaomi et Huawei (voir <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-oaid">https://github.com/AppsFlyerSDK/appsflyer-oaid</Anchor>).</li><li>Amélioration de la stabilité lors de l'utilisation de setOneLinkCustomDomain pour les ESPs</li></ul> |

</Accordion>

<div id="android-v500-release-notes" />

<Accordion title="Notes de mise à jour d'Android V5.0.0">

#### **Amélioration du temps de réponse du SDK**

À partir du SDK V5.0.0, le temps de réponse de la GCD a été amélioré pour les installations organiques.

#### **Méthodes supprimées ou renommées**

**Changements de noms de méthodes**

Les noms des méthodes de conversion des données d'installation sont désormais les mêmes pour Android et iOS. Cela a un impact sur les méthodes qui gèrent :

* données de conversion à l'installation
* erreurs si les données ne sont pas disponibles

| Nom pour Android avant le SDK V5 | Nom pour l'iOS avant le SDK V5 | Nom standardisé |
| --- | --- | --- |
| `onInstallConversionDataLoaded` | `onConversionDataReceived` | `onConversionDataSuccess` |
| `onInstallConversionFailure` | `onConversionDataRequestFailure` | `onConversionDataFail` |

**Méthodes retirées**

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
>       "is_first_launch": "true",
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
>       "is_first_launch": "true",
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

| Version | Date de sortie | Remarques |
| --- | --- | --- |
| 5.0.2 | 23/12/2019 |  |
| 5.0.1 | 12/12/2019 |  |
| 5.0.0 | 12/11/2019 | <ul><li>Correction des bugs et maintenance</li><li>Modifications majeures apportées aux fonctionnalités et à l'API du SDK, entre autres la dépréciation et les changements de noms de méthodes. [En savoir plus](/docs/appsflyer-android-sdk-release-notes#android-v500-release-notes)</li></ul> |
| 4.11.0 | 22/10/2019 | <ul><li>Amélioration du logging pour obtenir de meilleures capacités de débogage pour les éléments suivants :<ul><li>ESP</li><li>Résolution des liens de marque</li><li>onInstallConversionData et onAppOpenAttribution.</li></ul></li><li>Correction des bugs et maintenance</li></ul> |
| 4.10.3 | 15/09/2019 | <ul><li>Correction des bugs et maintenance</li><li>Prise en charge de l'Open Advertiser ID (OAID)</li></ul>4.10.2 |
| 4.10.1 | 01/07/2019 | Correction des bugs et maintenance |
| 4.10.0 | 14/05/2019 | <ul><li>Améliorations du SDK pour les développeurs qui utilisent ProGuard.</li><li>Correction des bugs et maintenance</li></ul> |
| 4.9.0 | 17/03/2019 | <ul><li>API setResolveDeepLinkURLs pour la résolution des OneLinks encapsulés dans un autre lien universel</li><li>Correction pour l'enregistrement des notifications push lorsque l'enregistrement de la notification push ignoré de la charge utile précédente contenait le même pid, et était toujours en mémoire.</li><li>Correction d'une faute de frappe : af\_county devient af\_country</li><li>Correction des bugs et maintenance</li></ul> |
| 4.8.20 | 13/02/2019 | <ul><li>Amélioration des capacités de notation zéro pour les fournisseurs de téléphonie mobile.</li><li>Correction des bugs et maintenance</li></ul> |
| 4.8.19 | 26/12/2018 | <ul><li>Correction d'un problème où la méthode `waitForCustomerUserId()` interrompait `generateLink`</li><li>Correction des bugs et maintenance</li></ul> |
| 4.8.18 | 11/11/2018 | <ul><li>Correction des problèmes de deep links liés aux activités de trampoline</li><li>Amélioration de la précision du réengagement lors du passage de l'arrière-plan au premier plan</li><li>Correction des bugs et maintenance</li></ul> |
| 4.8.17 | 02/11/2018 | Correction du problème de conflit dans ProGuard qui entraînait la perte des données de lancement de l'application dans certains cas. Ce problème ne concerne que la version 4.8.16 du SDK. |
| 4.8.16 | 31/10/2018 | Correction des bugs et maintenance |
| 4.8.15 | 27/08/2018 | <ul><li>Événements SDK supplémentaires : Abonnement, Essai démarré, Clic sur une publicité, Affichage d'une publicité</li><li>Correction des bugs et maintenance</li></ul> |
| 4.8.14 | 31/07/2018 | <ul><li>Added setOutOfStore and getOutOfStore APIs for dynamically setting the AF\_STORE value</li><li>Ajout des API `onTrackingRequestFailure` et `onTrackingRequestSuccess` pour obtenir la confirmation que AppsFlyer a reçu les serveurs de demande de suivi.</li></ul> |
| 4.8.13 | 20/06/2018 | <ul><li>Correction d'une erreur qui faisait que l'IMEI était manquant lorsqu'il était transmis explicitement par l'API setImeiData.</li><li>Correction des bugs et maintenance</li></ul> |
| 4.8.12 | 27/05/2018 | <ul><li>Correction de l'arrêt de l'application lors de l'utilisation d'un test JUnit avec Robolectric</li><li>Correction des bugs et maintenance</li></ul> |
| 4.8.11 | 02/05/2018 | Correction des bugs et maintenance |
| 4.8.10 | 26/04/2018 | <ul><li>API `setPreinstallAttribution` ajoutée</li><li>Correction des bugs et maintenance</li></ul> |
| 4.8.9 | 02/04/2018 | <ul><li>Collecter l'IMEI uniquement si GooglePlayServices n'existe pas sur l'appareil et qu'il est impossible de récupérer le GAID sur ce même appareil.</li><li>Correction des bugs et maintenance</li></ul> |
| 4.8.8 | 11/03/2018 | <ul><li>Ajout d'une API pour attendre que customerUserID soit fourni avant d'initialiser le SDK</li><li>Correction des bugs et maintenance</li></ul> |
| 4.8.7 | 25/01/2018 | <ul><li>API `isStopTracking` pour arrêter toutes les activités du SDK</li><li>Paramètre d'événement `af_content`</li></ul> |
| 4.8.5 | 29/11/2017 | <ul><li>Prise en charge de la nouvelle API Referrer Google</li><li>Nouvelle méthode init qui réceptionne le contexte</li></ul> |
| 4.8.4 | 14/11/2017 | <ul><li>Ajout d'un indicateur à getConversionData `is_first_launch` qui signale s'il s'agit du premier lancement de l'application. Cet indicateur permet aux développeurs d'identifier facilement le premier lancement de l'application dans la réponse du callback getConversionData qui est renvoyé à chaque lancement. Les valeurs possibles pour is\_first\_launch sont *true* ou *false*.</li><li>Correction des bugs et maintenance</li></ul> |
| 4.8.3 | 27/09/2017 | Ajout de la prise en charge des données de référence HTTP dans getConversionData |
| 4.8.2 | 19/09/2017 | Correction de sendDeepLinkData(this) pour les applications qui établissent des deep links avec plusieurs activités. |
| 4.8.1 | 17/09/2017 | Protection améliorée contre les événements in-app appelés avant l'initialisation du SDK |
| 4.8.0 | 03/09/2017 | <ul><li>API d'invitation utilisateur</li><li>API de promotion croisée</li><li>Personnalisation de la durée entre sessions</li><li>Soutien à la notation zéro pour les fournisseurs de services mobile</li><li>Paramètre supplémentaire de l'événement af\_projected\_revenue</li><li>Correction des bugs et maintenance</li><li>Introduction d'une nouvelle méthode d'init - AppsFlyerLib.getInstance().init(AF\_DEV\_KEY,conversionDataListener) ;</li></ul> |
| 4.7.4 | 28/06/2017 | Amélioration de la gestion des arrêts multiples de ScheduledExecutorSerice |
| 4.7.3 | 06/06/2017 | Améliorations pour l'intégration de mParticle |
| 4.7.2 | 22/05/2017 | <ul><li>Correction d'un problème mineur de fuite de mémoire</li><li>Amélioration de la précision de la mesure des désinstallations</li><li>Correction de l'avertissement ProGaurd qui impactait la mesure des désinstallations</li><li>Correction des bugs et maintenance</li></ul> |
| 4.7.1 | 22/02/2017 | Correction de l'avertissement lancé par ProGuard |
| 4.7.0 | 13/02/2019 | <ul><li>Paramètres supplémentaires de l'événement</li><li>Prise en charge de la mesure des désinstallations basée sur Firebase</li><li>Correction des bugs et maintenance</li></ul> |

</Accordion>

## Checksums du SDK Android

AppsFlyer utilise des checksums md5 :

<div id="v6-checksums" />

<Accordion title="Checksums V6">

| Version du SDK Android | Checksum |
| --- | --- |
| 6.6.1 | 1ec98047f8cb4145137f3c97459d052c |
| 6.6.0 | 6f5aef27ea407c7fc1691b52ff800c61 |
| 6.5.4 | c71aacbf201449dd5ef1158b55bd2ad0 |
| 6.5.3 | 7db44f0852be1c94fe36cc535b7c61f7 |
| 6.5.2 | 71e3a16c4278f857cd86b7b05aedd066 |
| 6.5.1 | 261928cfc55b27a6c2ab19cf9081d705 |
| 6.5.0 | 2a6d500fd4939a8faa47bbbba97288b6 |
| 6.4.3 | c62f9359d6b5497d54e248c526c5f547 |
| 6.4.2 | dc385fb62eaf68aff2e7f9c1c0ed19ea |
| 6.4.1 | 94945db2c0e81baab79535393f210f1b |
| 6.4.0 | d7910a35901d4299b54259f1c1bbe2d6 |
| 6.3.2 | 46bc92bb2eed1416de28ccccb3a28620 |
| 6.3.1 | ca47af77ffbcd7525e82d0bdaaef5b91 |
| 6.3.0 | f969bb5a62885e8084794d5334787275 |
| 6.2.3 | bab1309f77acd1f0453372150c82694a |
| 6.2.0 | fc727698c7b8bfb1ca448726492931b4 |
| 6.1.4 | 983785b1c30a15e8fac029e370bb3b73 |
| 6.1.3 | c0392a091659dc445a1014e14da6a31a |
| 6.1.1 | 0a18fafb2826c90b3388b371a3cbdeec |
| 6.1.0 | e8d6df04ac2642b2d7b16efb57f315e9 |
| 6.0.1 | 9ebeb6f4f49476667c07d0e8eb1aa2e8 |
| 6.0.0 | cff3d453ea94e67182f5b1b023aeb1c1 |

</Accordion>

<div id="v5-checksums" />

<Accordion title="Checksum V5">

| Version du SDK Android | Checksum |
| --- | --- |
| 5.4.6 | 4f1bdc33ac0d6dd3f9b75411c3c0a06c |
| 5.4.4 | 13a04913cf61276238f54e5e2d73e88d |
| 5.4.3 | 7b1caef46942c70edcd2e59cad69e439 |
| 5.4.1 | e4eb21c0030f376857b53e2e30022fc8 |
| 5.4.0 | 8c0270f6c3e7e58b1db42be82cc341d8 |
| 5.3.0 | d602dd28d9ee807855e5426d6a9b7ebf |
| 5.2.0 | 64fe94447def6d99549d3274ce908f09 |
| 5.1.2 | 1a7dbb23aad32d697835f3ec29337ca9 |
| 5.1.1 | dfea6a49e6ae57fc2c700f6dcd904bc1 |
| 5.1.0 | 89cc7e08a0430180e64f3cccf955768f |
| 5.0.2 | c113618ea379531cba6ce42bc4c79d72 |
| 5.0.1 | db0502faa5b02102dd99ac6cec666d04 |
| 5.0.0 | 98f1f78ae5f63cb4f40ba838d3d1be22 |

</Accordion>

<div id="v4-checksums" />

<Accordion title="Checksum V4">

| Version du SDK Android | Checksum |
| --- | --- |
| 4.10.3 | 855186d68912810fa47897262a9ba0a0 |
| 4.10.2 | 13ed5716d5a8583eeee527f01bd2a69d |
| 4.10.1 | ab3e49bb4640990267466b7852cd3de7 |
| 4.10.0 | b5fb55ee76cd6a742d9bd25b910745a1 |
| 4.9.0 | afa49524ddceda28ca1648946489a6b0 |
| 4.8.20 | 2f59d0f8db09b92f8261475a1d0807d0 |
| 4.8.19 | baf8fa419f38de52cef6091de32aca86 |
| 4.8.18 | 3a0641720811a25542449f1927daf13e |
| 4.8.17 | 3a0641720811a25542449f1927daf13e |
| 4.8.16 | 501be427b0c2a831e148649131ce3fc0 |
| 4.8.15 | 7b6759a006d72d3a7c78ec80160c3502 |
| 4.8.14 | bc4facd80958d0600b4d000104e524d9 |
| 4.8.13 | bc4facd80958d0600b4d000104e524d9 |
| 4.8.12 | 171569002d93fb8d49787b363192973f |
| 4.8.11 | 4419af159a42e4ee7a218ef8615e2abb |
| 4.8.10 | 468ad04e4a2088ba7af9c45d42f4ed6d |
| 4.8.9 | 9a923bbbf3f6c7cc19b900e49644da2c |
| 4.8.8 | 6dee4814986061a0723cc9f844796e2e |
| 4.8.7 | ca13997ccb781a5935e91983b7be81ea |
| 4.8.6 | da117a3e9e05df7dd28297df762cfbfa |
| 4.8.5 | f8ea07b8a60d664541686ba7064730f5 |
| 4.8.4 | b10f185c1094cf283b11339810a47c87 |
| 4.8.3 | 7f94ec175b948c5009bfbfe2fb25b2b0 |
| 4.8.2 | 3e34b55e13cd3f8d387b1a33c20105eb |
| 4.8.1 | 6c2930d2997a7b2b6ab7b3ecf0e3135b |
| 4.8.1 | 468ad04e4a2088ba7af9c45d42f4ed6d |
| 4.8.1 | 4419af159a42e4ee7a218ef8615e2abb latest |
| 4.8.0 | 32d67577ce59b2072475e509579baece |
| 4.7.4 | 7e649e6a1cf8999ca39b05402946b3d6 |
| 4.7.3 | e30c020f8ee5dd3af274fa94ef414a38 |
| 4.7.2 | 945aaaca554aa8b2f96219f25eed9777 |
| 4.7.1 | 862c349025e4725d4e5044a190c60337 |
| 4.7.0 | b060ad140ffd0c8f2b3febb26122d173 |

</Accordion>

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-sdk-version-control-policy">Politique de contrôle des versions du SDK AppsFlyer</Anchor>

<div data-zendesk-anchors="android-sdk-v6=sdk-android-v6 h_01H9ZPCP8RWF24WAZ6YYMA1GS0=sdk-android-v6 h_01H9ZPCP8S2P9Z93ZDENDHKJHD=android-v600-release-notes methods-removeddeprecated-or-renamed=m%C3%A9thodes-supprim%C3%A9esobsol%C3%A8tes-ou-renomm%C3%A9es h_01H9ZPCP8SCYTEYJG9J1SANGVJ=m%C3%A9thodes-supprim%C3%A9esobsol%C3%A8tes-ou-renomm%C3%A9es methods-removeddeprecated=m%C3%A9thodes-supprim%C3%A9esobsol%C3%A8tes 01EEYC8A6FNJ91R15X633BHSXF=m%C3%A9thodes-supprim%C3%A9esobsol%C3%A8tes methods-renamed=m%C3%A9thodes-renomm%C3%A9es 01EEYC8A6F8PB4C94Z14KXYD68=m%C3%A9thodes-renomm%C3%A9es renamed-interface=interface-renomm%C3%A9e h_01H9ZPCP8SV4VPEZA39VDTMCZ7=interface-renomm%C3%A9e h_01H9ZPCP8S37W1456YQN6RQDM7=android-sdk-v5 h_01H9ZPCP8SZ3QVX773J2X3QEGX=android-sdk-v5-release-notes h_01H9ZPCP8SAMFHXZW0T6CPEEYZ=android-v500-release-notes improved-sdk-response-time=am%C3%A9lioration-du-temps-de-r%C3%A9ponse-du-sdk h_01H9ZPCP8SN7NRGH3FZBEGCB3E=am%C3%A9lioration-du-temps-de-r%C3%A9ponse-du-sdk methods-removed-or-renamed=m%C3%A9thodes-supprim%C3%A9es-ou-renomm%C3%A9es h_01H9ZPCP8SY1HYDNR6HEZHXN37=m%C3%A9thodes-supprim%C3%A9es-ou-renomm%C3%A9es changes-to-get-conversion-data-format=modifications-du-format-des-donn%C3%A9es-de-conversion h_01H9ZPCP8S6Q97DNCZ8ANVMVT8=modifications-du-format-des-donn%C3%A9es-de-conversion h_01H9ZPCP8TAWT16MR1TVZVEVJ8=exemple h_01H9ZPCP8TFSA3SXDGTAZYC00V=deprecated-versions android-sdk-checksums=checksums-du-sdk-android h_01H9ZPCP8T7DJFPXGYX5EQ3BVB=checksums-du-sdk-android h_01H9ZPCP8TWG0ZXGFJG4GQ4E0F=v6-checksums h_01H9ZPCP8TS9CE2B55511H8JBY=v5-checksums h_01H9ZPCP8TKSJB1X4YT3W83EVJ=v4-checksums h_01HDNZ774ME3SVT89JS7R4MSKE=%C3%A0-consulter-%C3%A9galement" />
