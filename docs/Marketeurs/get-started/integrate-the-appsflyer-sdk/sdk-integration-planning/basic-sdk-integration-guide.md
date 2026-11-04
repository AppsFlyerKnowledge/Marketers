---
title: Guide de l'intégration de base du SDK
metadata:
  keywords:
    - sdk
    - iOS
    - Android
    - Integration
    - Advertisers
    - appuid
    - anonymous
    - kakao
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2013-08-22T16:09:08Z'
  edited_at: '2023-11-30T11:59:10Z'
  id: 207032066
  locale: fr
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/fr/articles/207032066
---
> **En bref :** en partenariat avec votre développeur mobile ou d'app CTV, intégrez et installez le SDK dans vos apps Android ou iOS. Une fois les opérations d'intégration de base terminées, votre app sera prête à attribuer les installations et à mesurer les événements in-app.

<div id="implementing-the-dev-key-in-your-app" />

## **Récupérer la clé dev**

Avant que votre développeur ne puisse installer et intégrer le SDK, vous devez récupérer la clé dev. AppsFlyer utilise la clé dev pour identifier votre compte de manière unique. La clé dev est obligatoire car elle permet au SDK d'envoyer et de récupérer en toute sécurité les données appartenant à votre compte.

**Pour récupérer votre clé dev :**

1. Dans AppsFlyer, allez à **Configuration** > **Paramètres de l'app**.
2. Copiez votre clé dev et transmettez-la à votre développeur mobile.

   [![](https://files.readme.io/5078fdabbcce4d3977f3d32351b61bacbc8af406a68911f2c6b4cdca458712a5-30603573703057.png)](https://files.readme.io/5078fdabbcce4d3977f3d32351b61bacbc8af406a68911f2c6b4cdca458712a5-30603573703057.png)
3. Transférez à votre développeur mobile les instructions concernant <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">l'installation</Anchor> et <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-integration">l'intégration du SDK</Anchor>.

<div id="where-to-start-the-sdk" />

## **Quand démarrer le SDK ?**

Lorsque vous planifiez l'intégration du SDK AppsFlyer, la première chose à savoir est : quand initialiser et démarrer le SDK dans le processus de lancement de votre app ?

La règle d'or c'est que le SDK doit commencer à envoyer des données le plus tôt possible après le lancement de l'app.**Cela garantit que le SDK capture l'événement d'installation et tous les événements in-app se de la session.**

Cependant, afin de suivre les règles de protection de la confidentialité telles que le RGPD et le CCPA, il est souvent nécessaire d'attendre que les utilisateurs consentent à partager leurs informations avant d'envoyer les données à AppsFlyer.

<Tabs>
<Tab title="Android natif">

<div id="starting-the-sdk-in-android-native" />

### Démarrer le SDK dans Android natif

<div id="select-in-what-class-to-start-the-sdk" />

#### SÉLECTIONNER LA CLASSE DANS LAQUELLE DÉMARRER LE SDK

Choisissez de démarrer le SDK dans la classe globale `Application` ou dans la classe `Activity` :

* **Démarrez le SDK dans la **classe** globale `Application`** : il est recommandé d'initialiser le SDK dans la classe/sous-classe globale `Application` car la classe `Application` se charge et s'initialise avant que l'interface utilisateur de l'app ne s'affiche. Cela vous garantit que le SDK démarre dans n'importe quel contexte, y compris celui du deep linking.
* **Lancez le SDK dans une classe** `Activity` **(démarrage différé)** pour permettre aux utilisateurs d'accepter le partage des données. Obtenir le consentement de l'utilisateur requiert en effet d'avoir une interface utilisateur (UI) rendue dans une classe `Activity`.

<div id="android-developer-instructions" />

#### INSTRUCTIONS POUR LES DEVS ANDROID

* Informez le développeur de vos choix concernant :
  * Faut-il démarrer le SDK dans la classe `Application` ou `Activity` ?
  * Le scénario de demande de consentement à utiliser.

* Transmettez à votre développeur les liens de référence suivants :
  * [Comment effectuer un démarrage différé](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#starting-the-android-sdk)
  * <Anchor target="_blank" href="/marketers/fr/docs/apply-privacy-preserving-sdk-methods#refus-à-linstallation">Scénarios courants de demande de consentement</Anchor>
  * [Exemples de code de demande de consentement](https://github.com/AppsFlyerSDK/SampleApp-Examples/tree/master/AndroidOptOutSampleApp/app/src/main/java/com/appsflyer/optoutsamples)

</Tab>

<Tab title="iOS natif">

<div id="starting-the-sdk-in-ios" />

### Démarrer le SDK en mode natif iOS

<div id="delay-the-sdk-start-in-ios" />

#### RETARDER LE DÉMARRAGE DU SDK DANS IOS

Il est important de savoir s'il faut retarder le `démarrage` du SDK jusqu'à ce que l'utilisateur donne son consentement.

Le SDK fournit la méthode `waitForATTUserAuthorization` qui vous permet de **définir combien de temps le SDK doit attendre le consentement de l'utilisateur avant d'envoyer les données aux serveurs AppsFlyer.**

Pour plus d'infos sur le flux de données de la méthode et son interaction avec l'infrastructure ATT d'iOS, consultez la section [Comment configurer l'App Tracking Transparency (ATT)](/docs/basic-sdk-integration-guide#aperçu-de-waitforattuserauthorization).

<div id="ios-developer-instructions" />

#### INSTRUCTIONS POUR LES DEVS IOS

Transmettez à votre développeur les éléments suivants :

* Quelle est la durée (en secondes) du temps d'attente avant l'envoi des données à AppsFlyer ?
* Le scénario de demande de consentement à utiliser.
* Liens pour les développeurs :
  * [Démarrer le SDK iOS](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#starting-the-ios-sdk), un guide du développeur pour savoir comment démarrer le SDK.
  * [Configurer App Tracking Transparency (ATT)](/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support), pour obtenir des infos sur le flux de données de la méthode `waitForATTUserAuthorization` et son interaction avec l'infrastructure ATT d'IOS.
  * [Activer la prise en charge de App Tracking Transparency (ATT)](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support), un guide du développeur sur `waitForATTUserAuthorization`

</Tab>

<Tab title="Unity">

<div id="starting-the-sdk-in-Unity" />

### Démarrer le SDK dans Unity

Indiquez à votre développeur <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#manual-integration">cet article du Dev Hub</Anchor> qui explique comment démarrer le SDK.

</Tab>

<Tab title="React Natif">

<div id="starting-the-sdk-in-react" />

### Démarrer le SDK dans React Natif

Indiquez à votre développeur <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#startsdk">cet article du Dev Hub</Anchor> qui explique comment démarrer le SDK.

</Tab>
</Tabs>

<div id="select-your-privacy-preserving-strategy" />

## Sélectionnez votre stratégie de protection de la vie privée

Choisissez **comment protéger la confidentialité de l'utilisateur**. Par exemple, vous pouvez choisir d'arrêter le SDK à l'installation, d'empêcher le partage des données avec des tiers, d'anonymiser les données de l'utilisateur ou de désactiver des identifiants spécifiques.

Pour plus d'informations sur les scénarios de demande de consentement disponibles, rendez-vous dans <Anchor target="_blank" href="/marketers/fr/docs/apply-privacy-preserving-sdk-methods#scénarios-de-demande-de-consentement">Scénarios de demande de consentement.</Anchor>

## **Attribution**

Le SDK collecte les identifiants à des fins d'attribution. En suivant ces directives, vous aurez la garantie que les installations sont enregistrées et attribuées correctement.

**Toutes les plateformes**

<div id="unique-identifier-for-installs" />

<Accordion title="Identifiant unique pour toutes les installations">

Un ID AppsFlyer est automatiquement créé pour chaque nouvelle installation de l'application. Aucune action n'est requise de la part du marketeur.

Avec cet identifiant vous pouvez :

* Envoyez des <Anchor target="_blank" href="/marketers/fr/docs/server-to-server-events-api-for-mobile-s2s-mobile">événements in-app serveur à serveur.</Anchor>
* Faire correspondre l'ID AppsFlyer et les enregistrements utilisateur dans vos systèmes en back-end.
* Téléchargez <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">le rapport de données brutes des événements in-app</Anchor> et utilisez **appsflyer\_id** pour analyser le comportement et le parcours des utilisateurs.

</Accordion>

<div id="integrate-unique-identifiers-from-your-bi-system-with-appsflyer" />

<Accordion title="Intégrer les ID uniques de votre système BI avec AppsFlyer">

Définissez votre propre ID utilisateur client (CUID) dans le SDK AppsFlyer pour croiser l'ID unique de votre système BI avec l'ID AppsFlyer, ou tout autre identifiant. Le CUID est disponible dans les rapports de <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary">données brutes</Anchor> AppsFlyer. Vous pouvez également l'utiliser dans les API de postback pour les croiser avec vos ID internes.

Pour en savoir plus sur le CUID, consultez <Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid">cet article</Anchor>.

</Accordion>

**Android uniquement**

Les sections suivantes présentes les possibilités d'attribution pour Google Play Store ou les app stores tiers.

<div id="attribute-apps-published-on-google-play" />

<Accordion title="Attribuer les apps publiées sur Google Play">

<div id="google-play-install-referrer" />

#### RÉFÉRENT D'INSTALLATION GOOGLE PLAY

[L'API de référent d'installation Google Play](https://developer.android.com/google/play/installreferrer) augmente la précision de <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#méthodes-dattribution">l'attribution</Anchor>, protège contre les installations frauduleuses et permet de récupérer en toute sécurité les données de référence de Google Play (ex : la version de l'app au moment de sa première installation).

Nous vous recommandons de fournir des [instructions à votre développeur pour ajouter l'API de référent d'installation Google Play.](https://developer.android.com/google/play/installreferrer/library)

#### GAID

Depuis le SDK V4.8.0, AppsFlyer collecte automatiquement cet identifiant d'appareil.

</Accordion>

<div id="attribute-apps-in-thirdparty-app-stores" />

<Accordion title="Attribuer les apps dans les app stores tiers">

Avec AppsFlyer, vous pouvez <Anchor target="_blank" href="/marketers/fr/docs/set-up-multi-store-android-attribution">attribuer les installations issues d'app stores tiers</Anchor> comme Amazon, Opera, GetJar, Baidu, ou Huawei. Cela vous permet de promouvoir vos apps et de toucher plus d'audiences sur les marchés où Google Play n'est pas disponible

AppsFlyer prend en charge l'attribution dans le contexte des app stores tiers comme suit :

* **IMEI ou ID Android** : le SDK ne collecte pas automatiquement l'IMEI ou l'ID Android. Cependant, si vous avez besoin de récupérer ces identifiants (par exemple pour une <Anchor target="_blank" href="/marketers/fr/docs/measure-attribution-in-the-chinese-domestic-market#attribution-android-apps-in-the-chinese-domestic-market">app du marché intérieur chinois</Anchor>), votre développeur peut implémenter l'une des méthodes de collecte suivantes :
  * Collecte manuelle : l'application transmet l'IMEI ou l'ID Android au SDK à l'aide de l'API `setImeiData` ou `setAndroidIdData` (voir la référence des fonctions dans les onglets ci-dessous). Le SDK envoie les données aux serveurs d'AppsFlyer.

    <Tabs>
    <Tab title="Android natif">

    Voir la référence du SDK Android pour :

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setimeidata">`setImeiData`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setandroididdata">`setAndroidIdData`</Anchor>

    </Tab>

    <Tab title="Unity">

    Voir la référence du SDK Unity pour :

    * `setImeiData`
    * `setAndroidIdData`

    </Tab>
    </Tabs>

  * Accepter la collecte de l'ID de l'appareil : force le SDK à collecter l'IMEI ou l'ID Android à l'aide de setCollectIMEI et setCollectAndroid (voir la référence des fonctions dans les onglets ci-dessous).

    <Tabs>
    <Tab title="Android natif">

    Voir la référence du SDK Android pour :

    * `setCollectIMEI`
    * `setCollectAndroidID`

    </Tab>

    <Tab title="Unity">

    Voir la référence du SDK Unity pour :

    * `setCollectIMEI`
    * `setCollectAndroidID`

    </Tab>

    <Tab title="React natif">

    Voir la référence React Native pour :

    * `setCollectIMEI`
    * `setCollectAndroidID`

    </Tab>
    </Tabs>

* **OAID :** attribut les installations issues des app stores Android tiers. Pour plus d'informations, consultez notre <Anchor target="_blank" href="/marketers/fr/docs/android-oaid-implementation-in-the-sdk">Guide pour implémenter l'OAID.</Anchor>
* **Référents d'installation :** le SDK prend en charge la récupération des données de référence à partir de Samsung Gallery et Huawei AppGallery.

</Accordion>

**iOS uniquement**

Les sections suivantes comprennent des informations importantes au sujet de la prise en charge des appareils iOS 14 et +.

<div id="configure-app-tracking-transparency-att-support" />

<Accordion title="Configurer la prise en charge de la transparence du suivi d'app (ATT)">

**CONTEXTE**

Depuis iOS 14.5, la collecte de l'IDFA est soumise au consentement de l'utilisateur. En pratique, cela signifie que l'accès à l'IDFA est régi par l'infrastructure [**App Tracking Transparency**(ATT](https://developer.apple.com/documentation/apptrackingtransparency)). Sur les appareils iOS 14 et +, le SDK utilise l'infrastructure ATT pour obtenir l'accès à l'IDFA de l'appareil. Pour une introduction à l'ATT, voir la section Principes de l'ATT.

<Tabs>
<Tab title="iOS native">

CF le Dev Hub pour voir les <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support">instructions de mise en œuvre de l'ATT pour les devs</Anchor>.

</Tab>

<Tab title="Unity">

CF le Dev Hub pour voir les <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#collect-idfa-with-attrackingmanager">instructions de mise en œuvre de l'ATT pour les devs</Anchor>.

</Tab>
</Tabs>

Lorsque l'attribution se produit à l'aide de l'IDFA, il est important que ce dernier soit envoyé lors du **premier lancement**.C'est la raison pour laquelle le SDK fournit la méthode `waitForATTUserAuthorization`.

<div id="waitforattuserauthorization-overview" />

#### Aperçu de waitForATTUserAuthorization

> 🚧 **Important !**
>
> N'appelez pas `waitForATTUserAuthorization` si vous n'avez pas l'intention d'invoquer la boîte de dialogue de consentement ATT.

`waitForATTUserAuthorization` vous permet de définir combien de temps le SDK doit attendre le statut ATT avant d'envoyer les données aux serveurs AppsFlyer.

[![](https://files.readme.io/a41e66c5aa23d2c673aba5b06589dcc24d34175e90900a8232343272ecca427c-30603573710993.png)](https://files.readme.io/a41e66c5aa23d2c673aba5b06589dcc24d34175e90900a8232343272ecca427c-30603573710993.png)

Lorsqu'un utilisateur lance l'app, le statut de l'ATT est **notDetermined** (non défini). En attendant l'expiration du délai de `waitForATTUserAuthorization`, le SDK stocke en mémoire l'événement de lancement et les événements in-app consécutifs. La même chose se produit lorsque [les événements hors ligne sont enregistrés](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#offline-in-app-events) :

* Si l'utilisateur **donne son accord** ATT (collecte IDFA) :
  * Le SDK ajoute l'IDFA aux événements mis en cache.
  * Le SDK se lance et envoie les événements mis en cache accompagnés de l'IDFA (sans attendre la fin du délai d'expiration).

* Si l'utilisateur **ne donne pas son accord** ATT : le SDK démarre et envoie les événements mis en cache sans l'IDFA (sans attendre la fin du délai d'expiration).
* Si le délai expire et que l'ATT est toujours sur **notDetermined**, le SDK se lance et envoie les événements mis en cache mais sans l'IDFA.

**Attention**

* Appeler `requestTrackingAuthorization` sans définir `waitForATTUserAuthorization` entraînera l'envoi de lancements et d'événements sans IDFA pour les appareils sous iOS 14+.
* Si l'utilisateur déplace l'app en arrière-plan durant le temps d'attente :
  * Le minuteur se met en pause jusqu'à ce que l'app revienne au premier plan.
  * Les événements sont mis en mémoire cache.

* Si l'utilisateur ferme l'application pedant le délai d'attente :
  * Le minuteur redémarre lorsque l'app est à nouveau lancée.
  * Les événements mis en cache sont perdus.

</Accordion>

<div id="customize-att-consent-dialog" />

<Accordion title="Personnaliser la boîte de dialogue de consentement ATT">

Vous pouvez personnaliser la boîte de dialogue de consentement ATT. Un message qui énonce clairement l'objet de la demande peut contribuer à augmenter le taux d'adhésion des utilisateurs.

Lorsque vous créez votre message, pensez à :

* Utilisez une formulation qui explique au mieux à vos utilisateurs pourquoi l'app leur demande leur consentement.
* Expliquer aux utilisateurs comment leurs données seront utilisées. [En savoir plus sur la confidentialité des utilisateurs et l'utilisation des données.](https://developer.apple.com/app-store/user-privacy-and-data-use/)

Une fois votre message terminé, transmettez à votre développeur le texte accompagné des instructions d'implémentation.

<Tabs>
<Tab title="iOS native">

Consultez le Dev Hub pour connaître les <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#customizing-the-att-consent-dialog">instructions de personnalisation de la boîte de dialogue de consentement ATT pour les devs.</Anchor>

</Tab>

<Tab title="Unity">

Cf le Dev Hub pour voir les [instructions de personnalisation de la boîte de dialogue de consentement ATT pour les devs](https://dev.appsflyer.com/hc/docs/basicintegration#collect-idfa-with-attrackingmanager).

</Tab>
</Tabs>

[Voir quelques exemples de demande de consentement ATT.](https://www.attprompts.com/)

</Accordion>

<div id="support-for-skan-attribution" />

<Accordion title="Prise en charge de l'attribution SKAN">

> 📘 **Remarque**
>
> Pour une prise en charge complète de l'attribution SKAN, vous devez passer au SDK iOS V6.2.3 et +.

SKAN est une classe utilisée par iOS pour valider les installations d'app pilotées par les annonceurs. Le processus de validation d'installation d'une app comprend l'app source et l'app à promouvoir.

Une app source est une application qui participe à une campagne publicitaire en affichant les publicités issues d'un réseau publicitaire. La configuration de votre app propre à l'affichage des publicités sort du cadre d'action du SDK AppsFlyer. Pour effectuer la configuration, veuillez suivre les [instructions d'Apple.](https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app)

Pour l'app à promouvoir (l'app avec le SDK AppsFlyer), la solution <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">AppsFlyer SKAN</Anchor> utilise SKAN pour produire le postback d'attribution, tandis que AppsFlyer collecte, traduit et agrège les données, et ce tout en protégeant la confidentialité des utilisateurs. Lorsque l'app est lancée pour la première fois, la plateforme AppsFlyer suit la configuration provenant du marketeur pour indiquer au SDK comment définir la valeur de conversion SKAN.

Pour utiliser la solution SKAN :

* Le marketeur doit configurer la mesure SKAdNetwork dans AppsFlyer. Le développeur n'a aucune action à réaliser.
* Le SDK AppsFlyer appelle automatiquement les API SKAN requises.
* Pensez à désactiver les appels SKAN des autres SDK si vous comptez sur AppsFlyer pour l'attribution SKAN.
* Aucune autre action ou procédure d'enregistrement n'est requise de la part du développeur ou du marketeur dans l'App Store.

Pour désactiver l'attribution SKAN, vous devez demander à votre développeur de le faire à l'intérieur du SDK .

<Tabs>
<Tab title="iOS natif">

Pour désactiver l'attribution SKAN, utilisez <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableskadnetwork">`disableSKAdNetwork`</Anchor>

</Tab>

<Tab title="Unity">

Pour désactiver l'attribution SKAN, utilisez `disableSKAdNetwork`

</Tab>

<Tab title="React Natif">

Pour désactiver l'attribution SKAN, utilisez `disableSKAd`

</Tab>
</Tabs>

</Accordion>

<div id="recording-in-app-events" />

## **Enregistrer les événements in-app**

Les événements in-app (IAE) permettent une analyse de ce qui se produit dans votre app. L'enregistrement des évènements in-app vous permet de mesurer certains KPI comme le ROI (retour sur investissement) et la LTV (lifetime value - durée vie). Nous vous recommandons de bien réfléchir aux événements que vous souhaitez enregistrer.

Une fois que vous avez déterminé les événements in-app que vous souhaitez mesurer, transmettez les noms d'évènements et paramètres à votre développeur, accompagnés du lien vers les [instructions d'implémentation](http://dev.appsflyer.com/hc/docs/in-app-events-sdk).

Pour en savoir plus sur les événements in-app, consultez notre <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">Guide des événements in-app riches.</Anchor>

**Toutes les plateformes**

<div id="record-revenue" />

<Accordion title="Enregistrement du revenu">

Vous pouvez envoyer un revenu avec n'importe quel évènement in-app. Veillez à utiliser le paramètre **af\_revenue** pour inclure le revenu. Il s'agit du seul paramètre d'événement que AppsFlyer considère comme un revenu réel à la fois dans le tableau de bord et les rapports de données brutes. <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#revenue-events">En savoir plus.</Anchor>

<Tabs>
<Tab title="Android native">

Pour les instructions à l'attention des devs sur la définition des événements de revenus, voir [ici](https://dev.appsflyer.com/hc/docs/in-app-events-android#logging-revenue).

</Tab>

<Tab title="iOS natif">

Pour les instructions à l'attention des devs sur la définition des événements de revenus, voir [ici](https://dev.appsflyer.com/hc/docs/in-app-events-ios#logging-revenue).

</Tab>

<Tab title="Unity">

* Pour les instructions aux développeurs sur les événements in-app en général, voir [ici](https://dev.appsflyer.com/hc/docs/inappevents#send-event).
* Pour les instructions spécifiques aux revenus dans iOS et Android, voir les onglets Android et iOS.

</Tab>
</Tabs>

</Accordion>

<div id="validate-inapp-purchases" />

<Accordion title="Valider les achats in-app">

Le SDK AppsFlyer effectue une vérification au niveau du serveur pour les achats in-app. La validation d'un achat in-app envoie automatiquement un évènement d'achat in-app à AppsFlyer. Le fait d'envoyer vous-même cet évènement crée un rapport d'évènements en double.

</Accordion>

<div id="industry-verticals" />

<Accordion title="Secteur d'activité">

Consultez la liste des <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#recommended-events-by-business-vertical">événements in-app recommandés par verticale</Anchor> (voyages, gaming, e-commerce, etc).

</Accordion>

<div id="deep-linking-with-onelink" />

## **Lien profond avec OneLink**

OneLink est la solution d'AppsFlyer pour l'attribution multiplateforme, **la redirection et le deep linking**.

**Toutes les plateformes**

<div id="device-detection-and-redirection" />

<Accordion title="Détecter et rediriger les appareils">

Pour les utilisateurs qui n'ont pas installé votre app, OneLink détecte le type d'appareil et les redirige vers la bonne destination, par exemple Google Play, l'App Store d'Apple, l'app store tiers ou une page web. Cette action se base sur les paramètres de votre template OneLink.<Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template">En savoir plus</Anchor>

</Accordion>

<div id="deep-linking" />

<Accordion title="Deep Linking">

Pour les utilisateurs qui ont installé votre app, OneLink ouvre l'app. En plus de l'ouverture de l'app, vous pouvez deep linker les utilisateurs à une activité ou page spécifique de l'app. Cela nécessite que votre développeur implémente le [deep linking unifié (DLU)](https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl).

**Remarque** :

* Le DLU nécessite un SDK V6.1 et +.
* Les clients qui utilisent déjà OneLink pour le deep linking peuvent utiliser la [méthode traditionnelle](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking), plutôt que le DLU.

Consultez notre guide sur le paramétrage du <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">deep linking et deep linking différé</Anchor>.

</Accordion>

<div id="deferred-deep-linking" />

<Accordion title="Deep linking différé">

Pour les utilisateurs qui n'ont pas installé votre app, OneLink détecte le type d'appareil et les redirige vers la bonne destination : Google Play, l'App Store d'Apple, l'app store tiers ou la page web. Une fois que l'utilisateur a lancé l'app, vous pouvez utiliser le deep linking différé pour qu'il soit redirigé vers une activité ou page spécifique de l'application.

Cela nécessite que votre développeur implémente le [deep linking différé étendu](https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking).

**Remarque** :

* Le DLU nécessite un SDK V6.1 et +.
* Les clients qui utilisent déjà OneLink pour le deep linking différé peuvent utiliser la [méthode traditionnelle](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking) au lieu du DLU.

Consultez notre guide sur le paramétrage du <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">deep linking et deep linking différé</Anchor>.

</Accordion>

<div id="accessing-attribution-and-deep-linking-data" />

## **Accéder aux données d'attribution et de deep linking**

Le tableau suivant détaille les différentes méthodes qui permettent de récupérer les données d'attribution et de deep linking :

| Méthode | Qui est concerné ? | Résultats du retour | Méthode de récupération | Données d'attribution | Données de deep linking | Disponibilité |
| --- | --- | --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/fr/docs/push-api-streaming-raw-data">**API push**</Anchor> | • Marketeur • Développeur back-end | Généralement en quelques minutes | Backend | Y | N | Premium |
| <Anchor target="_blank" href="/marketers/fr/docs/pull-api-raw-data">**API pull**</Anchor> | • Marketeur • Développeur back-end | • Par cycle (non en temps réel). • Vous pouvez programmer le téléchargement des rapports de données brutes. | Backend | Y | Y | Premium pour les rapports de données brutes |
| <Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers">**Data Locker**</Anchor> | • Marketeur • Développeur back-end | Les rapports horaires sont disponibles sous 1 à 3 heures. | Stockage cloud via l'une des options suivantes : • Un panier appartenant à AppsFlyer sur AWS • Un stockage vous appartenant (AWS ou GCS) | Y | Y | Premium |
| <Anchor target="_blank" href="/marketers/fr/docs/conversion-data-payloads-and-scenarios#présentation">**Obtenir des données de conversion (GCD)**</Anchor> | • Marketeur • Développeur mobile <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking">Voir la documentation du développeur</Anchor> | Jusqu'à 5 secondes | SDK | Y | Y | Tous les comptes |
| <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template">**Deep linking unifié (DLU)**</Anchor> | • Marketeur • Développeur mobile <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">Voir la documentation pour les devs</Anchor> | Jusqu'à 1 seconde | SDK | N | Y | Tous les comptes |

Ce qui suit s'applique uniquement aux utilisateurs d'iOS 14.5 et + qui n'ont pas donné leur accord :

* Lorsque vous utilisez le DLU pour les médias payants et propriétaires, les données de deep linking sont disponibles.
* Lorsque vous utilisez la fonction GCD pour les médias payants, les données sont limitées et n'incluent pas les détails d'attribution et de deep linking.

> 👍 **Astuce**
>
> Ce que nous vous recommandons :
>
> * Utilisez l'API Push pour récupérer les données d'attribution et les envoyer à vos serveurs pour traitement. Cette méthode permet d'attendre que les données soient disponibles, elle est donc très précise et quasi en temps réel. La GCD renvoie des données en temps réel, mais peut être imprécise lorsque les décisions d'attribution finales sont déterminées après plus de 5 secondes.
> * Utilisez l'API Pull pour traiter par cycle (par exemple chaque jour) les données d'attribution en temps réel, vous éviterez ainsi les éventuelles erreurs de communication.

<div id="testing-your-sdk-integration" />

## **tester vZtre intégration SDK**

Une fois l'intégration du SDK terminée, vous pouvez vous rendre dans le tableau de bord AppsFlyer, sur la page Tests d'intégration du SDK, et tester les installations organiques et non organiques, les événements in-app ainsi que le deep linking (retargeting). Vous pourrez ainsi vous assurer que les installations et événements in-app ont été correctement enregistrés et attribués.

Si vous voulez que votre développeur teste l'intégration du SDK, vous devez l'ajouter à votre compte en tant qu'<Anchor target="_blank" href="/marketers/fr/docs/user-management">utilisateur</Anchor> pour qu'il puisse accéder au tableau de bord.

Pour découvrir des exemples de test et parcourir les instructions, consultez les <Anchor target="_blank" href="/marketers/fr/docs/testing-the-sdk-integration-for-marketers">tests d'intégration SDK</Anchor>.

**Remarque :** Lors des tests d'attribution, <Anchor target="_blank" href="/marketers/fr/docs/registering-test-devices">enregistrez un appareil de test</Anchor> (Android ou iOS) pour vous assurer que chaque installation est enregistrée comme une nouvelle installation. Un appareil de test enregistré empêche les installations d'être enregistrées comme des réinstallations.

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">Aperçu des plateformes CTV, PC et consoles</Anchor>

<div data-zendesk-anchors="retrieving-the-dev-key=r%C3%A9cup%C3%A9rer-la-cl%C3%A9-dev h_01HAWCK9K4QBRE74JAS8Q7MEXW=r%C3%A9cup%C3%A9rer-la-cl%C3%A9-dev where-to-start-the-sdk=quand-d%C3%A9marrer-le-sdk h_01HAWCK9K4MBS0F0HE6QE1W1AN=quand-d%C3%A9marrer-le-sdk starting-the-sdk-in-android=d%C3%A9marrer-le-sdk-dans-android-natif h_01HAWCK9K45HCJEDRW761WHKES=d%C3%A9marrer-le-sdk-dans-android-natif select-in-what-class-to-start-the-sdk=s%C3%A9lectionner-la-classe-dans-laquelle-d%C3%A9marrer-le-sdk h_01HAWCK9K428SDFBFCCSZ15X9J=s%C3%A9lectionner-la-classe-dans-laquelle-d%C3%A9marrer-le-sdk android-developer-instructions=instructions-pour-les-devs-android h_01HAWCK9K4XR1HZHP7Y15Q2Q4N=instructions-pour-les-devs-android h_01HAWCK9K4693729EX1WYFR6XT=starting-the-sdk-in-ios h_01HAWCK9K4QSBP874RX2ZRA7EB=delay-the-sdk-start-in-ios h_01HAWCK9K4VHDFB9CYHC144BZN=ios-developer-instructions select-the-optoutin-scenario::ae4c6e25=s%C3%A9lectionnez-votre-strat%C3%A9gie-de-protection-de-la-vie-priv%C3%A9e h_01HAWCK9K4EXBA2F0BPVBXFAMG=s%C3%A9lectionnez-votre-strat%C3%A9gie-de-protection-de-la-vie-priv%C3%A9e h_01HAWCK9K41T5GGWDB3ABYGRHW=attribution h_01HAWCK9K4HY8NZC0VM3NBF4H9=unique-identifier-for-installs h_01HAWCK9K44GRVGBB1P3FWBX4A=integrate-unique-identifiers-from-your-bi-system-with-appsflyer h_01HAWCK9K4SE4YWTQYF3R1WH2Z=attribute-apps-published-on-google-play google-play-install-referrer=r%C3%A9f%C3%A9rent-dinstallation-google-play h_01HAWCK9K4V91MPQHXDZBD0HKR=r%C3%A9f%C3%A9rent-dinstallation-google-play h_01HAWCK9K4YD8CYQDB2YRA8W1F=gaid h_01HAWCK9K4EFCGWJ45K8VRAFFM=attribute-apps-in-thirdparty-app-stores h_01HAWCK9K5VKBZS5MSF27WNG1G=configure-app-tracking-transparency-att-support waitforattuserauthorization-overview=aper%C3%A7u-de-waitforattuserauthorization h_01HAWCK9K5JHDWS8KTBTTGSS9G=aper%C3%A7u-de-waitforattuserauthorization h_01HAWCK9K5X4Z9DWRT1VDSFEPH=important- h_01HAWCK9K5FY2H211JFQQDSXHK=customize-att-consent-dialog h_01HAWCK9K5HV3SBY82A28ZD4KN=support-for-skan-attribution h_01HAWCK9K5HS9Y836X33YMV21C=remarque recording-inapp-events=enregistrer-les-%C3%A9v%C3%A9nements-in-app h_01HAWCK9K5ZZYQR8KPCWANZEA5=enregistrer-les-%C3%A9v%C3%A9nements-in-app h_01HAWCK9K50T438WCG0PKP5M3G=record-revenue h_01HAWCK9K5Z0N6DP38VCB3K3B2=validate-inapp-purchases h_01HAWCK9K5A3W2XKCM7XRNGKQK=industry-verticals deep-linking-with-onelink=lien-profond-avec-onelink h_01HAWCK9K5PK9RE7WZQVCY97KC=lien-profond-avec-onelink h_01HAWCK9K593KCJ9QQQV0E0E71=device-detection-and-redirection h_01HAWCK9K5SNBFHNFXYBBC20HN=deep-linking h_01HAWCK9K5YJSB78Z4RJSAP1KM=deferred-deep-linking accessing-attribution-and-deep-linking-data=acc%C3%A9der-aux-donn%C3%A9es-dattribution-et-de-deep-linking h_01HAWCK9K5ACPZ2WKBTVR3VVTD=acc%C3%A9der-aux-donn%C3%A9es-dattribution-et-de-deep-linking h_01HAWCK9K6N405V344RDEGC0QJ=astuce testing-your-sdk-integration=tester-vztre-int%C3%A9gration-sdk h_01HAWCK9K6JQ33T32RYKYH20P1=tester-vztre-int%C3%A9gration-sdk h_01H9FHRVKE88CXGH8G7E26ZXT2=%C3%A0-consulter-%C3%A9galement" />
