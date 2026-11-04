---
title: Intégration de Braze (anciennement Appboy) avec AppsFlyer
metadata:
  keywords:
    - Appboy
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2017-03-30T08:39:03Z'
  edited_at: '2024-10-08T10:20:54Z'
  id: 115001603343
  locale: fr
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/fr/articles/115001603343
---
> **En bref :** Braze, un partenaire intégré d'AppsFlyer, propose une plateforme d'engagement tout au long du cycle de vie pour les équipes marketing, de croissance et d'engagement. La plateforme permet aux spécialistes du marketing de se connecter humain à humain, à grande échelle, avec leurs clients, générant ainsi un engagement profond et un ROI. Le centre de notre plateforme est le profil utilisateur holistique qui offre une vue unique du client.

En savoir plus sur <Anchor target="_blank" href="https://www.braze.com/">braze.com</Anchor>.

> 🚧 **Important !**
>
> <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions#restrictions-des-sources-média">Certaines sources média</Anchor> restreignent le partage de données avec des tiers. Par conséquent, les postbacks pour les événements restreints ne seront pas envoyés à ce partenaire, peu importe la configuration choisie pour l'envoi des postbacks.

<div id="integration-overview" />

## Présentation de l'intégration

Suivez les instructions ci-dessous pour configurer l'intégration avec Braze.

Exigences minimales – SDK AppsFlyer :

* <Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">Android</Anchor> (SDK Android – version 2.3.1.18 et supérieure)
* <Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">iOS</Anchor>

Sur Android, l'intégration avec Braze nécessite que l'identifiant d'appareil <Anchor target="_blank" href="https://www.braze.com/docs/partners/advertising_technologies/attribution/appsflyer/#integration">Braze</Anchor> (identifiant utilisateur unique Braze) soit renseigné dans le SDK Android d'AppsFlyer. Ce paramètre est envoyé avec chaque postback et permet l'identification de chaque utilisateur. Pour ce faire, vous devez insérer les chaînes suivantes dans le code de votre application :

> 📘 **Remarque importante**
>
> Assurez-vous que les lignes de code sont insérées au bon endroit : après le lancement du SDK Braze et avant le code d'initialisation du SDK AppsFlyer (voir la section Initialisation du SDK dans notre Guide d'intégration du SDK Android).

<Tabs>
<Tab title="Android">

```java
HashMap<String, Object> customData = new HashMap<String,Object>();
String deviceId =(Braze.getInstance(MyActivity.this).getDeviceId());
customData.put("brazeCustomerId", deviceId);
AppsFlyerLib.getInstance().setAdditionalData(customData);
```

</Tab>

<Tab title="iOS">

<div id="swift" />

#### Swift

Il existe deux API Swift, une avec un gestionnaire de complétion et l'autre utilisant la nouvelle prise en charge de la concurrence de Swift. Elles produisent toutes deux la même valeur : le choix de l'une ou l'autre dépend du contexte.

**Gestionnaire de complétion Swift**

```swift
let configuration = Braze.Configuration(
    apiKey: "<BRAZE_API_KEY>",
    endpoint: "<BRAZE_ENDPOINT>")
configuration.useUUIDAsDeviceId = false
let braze = Braze(configuration: configuration)
braze.deviceId {
    brazeDeviceId in
    AppsFlyerLib.shared().customData = [“brazeDeviceId”: brazeDeviceId]
}
```

**Swift await**

```swift
let configuration = Braze.Configuration(
    apiKey: "<BRAZE_API_KEY>",
    endpoint: "<BRAZE_ENDPOINT>")
configuration.useUUIDAsDeviceId = false
let braze = Braze(configuration: configuration)
let brazeDeviceId = await braze.deviceId()
AppsFlyerLib.shared().customData = ["brazeDeviceId": brazeDeviceId]
```

#### Objective-C

```objc
BRZConfiguration *configurations = [[BRZConfiguration alloc] initWithApiKey:@"BRAZE_API_KEY" endpoint:@"BRAZE_END_POINT"];
[configurations setUseUUIDAsDeviceId:NO];
Braze *braze = [[Braze alloc] initWithConfiguration:configurations];
[braze deviceIdWithCompletion:^(NSString * _Nonnull brazeDeviceId) {
    NSLog(@">>[BRZ]: %@", brazeDeviceId);
    [[AppsFlyerLib shared] setAdditionalData:@{
        @"brazeDeviceId": brazeDeviceId
    }];
}];
```

</Tab>

<Tab title="Unity">

```csharp
Appboy.AppboyBinding.getDeviceID()
Dictionary<string, string> customData = new Dictionary<string, string>();
customData.Add("brazeCustomerId", Appboy.AppboyBinding.getDeviceId());
AppsFlyer.setAdditionalData(customData);
```

</Tab>
</Tabs>

<div id="setting-up-braze" />

## Configuration de Braze

**Prérequis :** Avant de configurer l'intégration, assurez-vous de <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations#contacter-le-partenaire">contacter le partenaire</Anchor> et d'ouvrir un compte chez lui.

**Pour activer ou modifier l'intégration :**

1. <strong>Pour activer :</strong> Dans AppsFlyer, dans le menu latéral, sélectionnez Collaborer<strong> > </strong>Marketplace Partenaire.  
   <strong>Pour modifier</strong> : Dans AppsFlyer, dans le menu latéral, sélectionnez <strong>Collaborer</strong> > Intégrations actives.
2. Recherchez le partenaire et sélectionnez-le.
3. Cliquez sur **Configurer l'intégration**. Vous êtes dirigé vers la page de configuration de l'intégration.
4. Dans l'onglet **Intégration**, sélectionnez l'application pour l'intégration et activez **Activer le partenaire**.  
   **Remarque : Le commutateur doit être sur <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">(activé)</Anchor> tant que vous travaillez avec le partenaire.**
5. Terminez la configuration en utilisant les onglets pertinents, comme décrit ci-dessous.

Pour une description détaillée de l'en-tête de la fenêtre de configuration du partenaire, cliquez <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">ici</Anchor>.

<div id="integration-tab" />

<Accordion title="Onglet Intégration">

L'onglet Intégration est divisé en plusieurs sections comme expliqué ci-dessous.

<div id="activate-partner" />

### Activer le partenaire

Lors de votre **première visite** ici, vous devez ***activer le partenaire*** pour permettre la configuration des paramètres de l'onglet Intégration. Le commutateur DOIT être activé tant que vous travaillez avec le partenaire.  
Pour plus de détails sur l'activation du partenaire, veuillez cliquer <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">ici</Anchor>.

<div id="general-settings" />

### Paramètres généraux

Braze se connecte à AppsFlyer via une clé API unique et un point de terminaison REST.

**Pour obtenir la clé API et le point de terminaison REST de Braze :**

1. Dans votre compte Braze, sous **Partenaires technologiques** , allez à **Attribution**.
2. Sélectionnez **AppsFlyer**.  

   ![braze-af-API-key.png](https://files.readme.io/db96e8b5e2363f5250c6c1146a1f7a15e1ed6457fe4543dbe649f8818bb5db78-360017328637.png)
3. Sous **Importation de données pour l'attribution d'installation**, cliquez sur Générer la clé API.
4. Copiez la clé API générée et le point de terminaison REST.
5. Dans AppsFlyer, insérez la clé API Braze et le point de terminaison REST.  

   ![Braze_msc_new_2.png](https://files.readme.io/b13aba84c394c0b4603e0aad2edd723525dadf204250349620b571bc47b0ba9d-360001907229.png)
6. Cliquez sur **Enregistrer et fermer**.

Une fois la configuration enregistrée, AppsFlyer envoie les données suivantes à Braze pour chaque installation organique et non organique :

* ID du développeur Braze
* Source média
* Nom de la campagne
* Nom du groupe d'annonces
* Nom de la publicité

<div id="default-postbacks" />

### Postbacks par défaut

AppsFlyer peut envoyer des postbacks automatiques aux installations des utilisateurs de Braze. Utilisez cette section pour définir l'envoi de ces postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Sélectionnez **Événements attribués à tout partenaire ou organiques** pour envoyer des postbacks à Braze pour tout utilisateur qui télécharge l'application.

Cliquez sur **Enregistrer.**

> 📘 **Remarque :**
>
> Bien que tous les événements soient envoyés par AppsFlyer, les installations organiques ne sont pas comptabilisées par Braze et sont donc ignorées par l'API Braze.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Onglet de lien d'attribution">

Les liens d'attribution ne sont pas disponibles pour Braze.

</Accordion>

<div id="cost-tab" />

<Accordion title="Onglet Coût">

Les données de coût ne sont pas prises en charge dans l'intégration avec ce partenaire.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Onglet Revenus publicitaires">

Les recettes publicitaires ne sont pas prises en charge dans l'intégration avec ce partenaire.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Onglet Autorisations">

Les autorisations ne sont pas disponibles pour Braze.

</Accordion>

<div id="viewing-user-attribution-data-in-braze" />

## Visualisation des données d'attribution des utilisateurs dans Braze

Dans le tableau de bord Braze, vous pouvez segmenter votre base d'utilisateurs à l'aide des filtres d'attribution d'installation.

En outre, les données d'attribution pour un utilisateur particulier sont disponibles sur le profil de chaque utilisateur dans le tableau de bord Braze.

<div data-zendesk-anchors="h_01H9FK453A9852FTMBM9T0YP7B=important- integration-overview=pr%C3%A9sentation-de-lint%C3%A9gration h_01H9FK453A9W5DCPR4X8PR06MZ=pr%C3%A9sentation-de-lint%C3%A9gration h_01H9FK453ANSTRYM8V8YXVTS2M=remarque-importante h_01H9FK453AFZA6TS3DYWN2V65T=swift setting-up-braze=configuration-de-braze h_01H9FK453AWXF006KEVKD797QF=configuration-de-braze h_01H9FK453A4RFFH84JHWPV0STH=integration-tab activate-partner=activer-le-partenaire h_01H9FK453AVK4YKF41FEP0YRJN=activer-le-partenaire general-settings=param%C3%A8tres-g%C3%A9n%C3%A9raux h_01H9FK453AG6AXA7J43X6NGZT1=param%C3%A8tres-g%C3%A9n%C3%A9raux default-postbacks=postbacks-par-d%C3%A9faut h_01H9FK453ASAKVHT7GV8BG56YS=postbacks-par-d%C3%A9faut h_01H9FK453ARG95477MA92RA91D=remarque- h_01H9FK453A2W3HWEY0FBM1BZXR=attribution-link-tab h_01H9FK453AQ7MTMDHYNZQRAH7R=cost-tab h_01H9FK453AVQDFQ4K69GFTTTJ5=ad-revenue-tab h_01H9FK453AP7KZDQJCBAPTYCX8=permissions-tab viewing-user-attribution-data-in-braze=visualisation-des-donn%C3%A9es-dattribution-des-utilisateurs-dans-braze h_01H9FK453AQXG7NNT2841686MJ=visualisation-des-donn%C3%A9es-dattribution-des-utilisateurs-dans-braze" />
