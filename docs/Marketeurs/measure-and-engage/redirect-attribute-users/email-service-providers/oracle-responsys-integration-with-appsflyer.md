---
title: Intégration d'Oracle Responsys avec AppsFlyer
metadata:
  keywords:
    - Oracle Responsys
    - Advertisers
    - Developers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-11-20T09:26:13Z'
  edited_at: '2023-10-26T13:34:31Z'
  id: 360003798297
  locale: fr
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/fr/articles/360003798297
---
> **En bref :** Oracle Responsys, une plateforme d'analyse et de messagerie, intègre AppsFlyer OneLink dans les e-mails.Les destinataires de l'e-mail qui cliquent sur le lien sont deep linkés vers votre application.

<Image align="center" alt="oracle-responsys-af-logo.png" src="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png" />

Les ESP (Email Service Providers) peuvent être d'excellentes sources de trafic segmenté.

L'un des défis posés par les ESP est d'obtenir une attribution et un deep linking corrects.Les ESP intègrent l'URL de deep linking dans le domaine d'enregistrement des clics de leur propre ESP. Cette procédure perturbe souvent la fonctionnalité des liens universels iOS et des liens d'app Android.

Cependant, l'enregistrement des liens de deep linking et des clics est toujours possible avec les ESP qui prennent en charge les liens universels et les liens d'app en plus de leur domaine d'enregistrement des clics. Vous pouvez également configurer votre propre domaine de clics comme domaine d'enregistrement des clics.

<div id="prerequisites" />

## Conditions préalables

* Configurez votre application pour qu'elle prenne en charge le <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">deep linking avec OneLink</Anchor>.
* Vérifiez la version de votre SDK (Android et iOS)

<Tabs>
<Tab title="iOS">

* SDK iOS AppsFlyer version 4.9.0 (ou +)

</Tab>

<Tab title="Android">

* SDK Android AppsFlyer version 4.9.0 (ou +)

</Tab>
</Tabs>

<div id="setting-up-oracle-responsys-click-domain" />

## Configuration du domaine de clics dans Oracle Responsys

Suivez cette section pour configurer votre domaine de clics (domaine d'enregistrement de clics) dans Oracle Responsys.

<div id="step-1-set-up-a-click-domain-in-oracle-responsys" />

### Étape 1 : Configurer un domaine de clics dans Oracle Responsys

Pour configurer un domaine de clics, suivez le guide officiel d'Oracle Responsys <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCEA/LinkTable_Main.htm?cshid=LinkTable_Main">Créer des domaines de clics</Anchor>.Oracle Responsys utilise des tableaux de liens pour faciliter l'enregistrement des clics des campagnes.

**Remarque**: Dans les tableaux de liens, vous pouvez définir l'**URL du lien iOS** comme étant identique à l'URL du lien.

<Image align="center" alt="Oracle-responsys-link-tracking-table.png" src="https://files.readme.io/c151c58af73cf460ba4275a9159e45c15807f311fa8d8b4b1531b0cdf7e3bc4e-49839256667665.png" />

Une fois que vous avez défini des domaines de clics dans les tableaux de liens, Responsys utilise ces domaines pour encapsuler les OneLinks que vous incluez dans les campagnes d'e-mailing. De cette manière, Responsys peut enregistrer les clics dans son système tout en préservant les fonctionnalités de OneLink et de deep linking.

<div id="step-2-give-responsys-an-aasa-ios-and-an-asset-links-file-android" />

### Étape 2 : Donner à Responsys un fichier AASA (iOS) et un fichier Asset Links (Android)

<div id="aasa-for-ios" />

<Accordion title="AASA pour iOS">

Un fichier AASA est nécessaire pour que Responsys prenne en charge les liens universels iOS.Consultez les instructions suivantes.

Lorsque vous configurez OneLink avec des liens universels, vous avez déjà une AASA associée à OneLink. Pour obtenir l'AASA :

1. Allez dans la configuration de OneLink et trouvez un OneLink configuré avec des liens universels.
2. Ajoutez **/.well-known/apple-app-site-association** à la fin de l'URL OneLink.
3. Collez le OneLink dans la barre d'adresse du navigateur et appuyez sur Entrée. Par exemple : **`<OneLinkSubdomain>`.onelink.me/.well-known/apple-app-site-association**. Le fichier AASA est alors téléchargé sur votre ordinateur. Vous pouvez l'ouvrir à l'aide d'un simple éditeur de texte.
4. Envoyez ce fichier AASA à Responsys. Pour plus d'informations et pour en savoir plus sur le contenu de ce fichier, voir la page 11 du <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCFB/pdf/ios-universal-links-dev-guide.pdf">guide d'utilisation d'Oracle</Anchor>.

</Accordion>

<div id="asset-links-for-android" />

<Accordion title="Asset Links pour Android">

Lorsque vous configurez OneLink avec des liens d'app, un fichier Asset Links est déjà associé à OneLink. Pour obtenir le fichier Asset Links. Pour obtenir le fichier Asset Links :

1. Allez dans la configuration de OneLink et trouvez un OneLink configuré avec des liens d'app.
2. Ajoutez **/.well-known/assetlinks.json** à la fin de l'URL OneLink.
3. Collez le OneLink dans la barre d'adresse du navigateur et appuyez sur Entrée. Par exemple :**`<OneLinkSubdomain>`.onelink.me/.well-known/assetlinks.json**. Le fichier Asset Links est alors téléchargé sur votre ordinateur. Vous pouvez l'ouvrir à l'aide d'un simple éditeur de texte.
4. Envoyez ce fichier Asset Links à Responsys. Pour plus d'informations et pour en savoir plus sur le contenu de ce fichier, voir <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCFB/android/app-links/">ce guide</Anchor>.

</Accordion>

<div id="setting-up-your-app" />

## Configuration de votre app

<div id="step-1-for-android-setting-up-your-app-to-support-app-links" />

<Accordion title="Étape 1 pour Android : Configurer votre application pour qu'elle prenne en charge les liens d'app">

<div id="adding-the-click-domain-to-the-activity-in-the-android-manifest" />

#### Ajouter le domaine de clic à l'activité dans le manifeste Android

Dans le manifeste Android, ajoutez l'hôte du domaine de clic et son préfixe dans la balise d'activité de l'activité que vous souhaitez deep linker.

```html Markup
<activity android:name=".DeepLinkActivity">
    <intent-filter  android:autoVerify="true">
        <action android:name="android.intent.action.VIEW" />
           <category android:name="android.intent.category.DEFAULT" />
           <category android:name="android.intent.category.BROWSABLE" />
           <data android:scheme="https"
               android:host="click.example.com"
               android:pathPrefix="/campaign" />
     </intent-filter>
</activity>
```

<div id="setting-up-the-app-to-resolve-click-domains" />

#### Configurez l'application pour les domaines de clics

Pour obtenir les détails de la campagne, le SDK doit résoudre le OneLink qui soutient le domaine de clic. Les détails sont renvoyés dans la méthode `onAppOpenAttribution`.

Pour résoudre les domaine de clics :

1. Assurez-vous de posséder le SDK 4.9.0 ou +.
2. Listez les domaines de clics dans l'API SDK `setResolveDeepLinkURLs`. Cette API doit être appelée avant l'initialisation du SDK. Pour plus d'informations, veuillez vous référer à la <Anchor target="_blank" href="/marketers/fr/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">documentation du SDK</Anchor>.  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("click.example.com");
   ```

   * **Important !** Si vous utilisez Movable Ink (MI) conjointement avec Oracle, vous devez obtenir le CNAME MI et les domaines internes auprès de votre gestionnaire de compte MI et les ajouter à `setResolveDeepLinkURLs`, en plus du lien de clic pour Oracle. Par exemple :

     ```java
     AppsFlyerLib.getInstance().setResolveDeepLinkURLs("oracle-click.example.com", "mi.example.com", "example.micpn.com");
     ```

</Accordion>

<div id="step-1-for-ios-setting-up-your-app-to-support-universal-links" />

<Accordion title="Étape 1 pour iOS : Configurer votre application pour qu'elle prenne en charge les liens universels">

Cette section explique comment configurer votre app pour qu'elle prenne en charge les liens universels.

<div id="associating-click-domains-in-xcode" />

#### Associer des domaines de clics dans Xcode

1. Dans Xcode, cliquez sur votre projet.
2. Cliquez sur ***Capacités***.[![configure-xcode-deeplinking-domain.png](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)
3. Activez les ***Domaines associés**.*
4. Cliquez sur le signe + et ajoutez votre domaine de clics. Par exemple, applinks:click.example.com.

</Accordion>

<div id="step-2-setting-up-the-app-to-resolve-click-domains" />

### Étape 2 : Configurer l'application pour les domaines de clics

Pour obtenir les détails de la campagne, le SDK doit résoudre le OneLink qui soutient le domaine de clic. Les détails sont renvoyés dans la méthode `onAppOpenAttribution`.

Pour résoudre les domaine de clics :

1. Assurez-vous de posséder le SDK 4.9.0 ou +.
2. Listez les domaines de clics dans la propriété du SDK `ResolveDeepLinkURLs`. Cette propriété doit être définie avant l'initialisation du SDK. Pour plus d'informations, veuillez vous référer à cette <Anchor target="_blank" href="/marketers/fr/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">documentation sur le SDK</Anchor>.  

   <Tabs>
   <Tab title="Objective-C">

   ```objectivec
   [AppsFlyerTracker sharedTracker].resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```

   </Tab>

   <Tab title="Swift">

   ```swift
   AppsFlyerTracker.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   </Tab>
   </Tabs>

   * **Important !** Si vous utilisez Movable Ink (MI) conjointement avec Oracle, vous devez obtenir le CNAME MI et les domaines internes auprès de votre gestionnaire de compte MI et les ajouter à `setResolveDeepLinkURLs`, en plus du lien de clic pour Oracle. Exemples de domaines :
     * Domaine Oracle : oracle-click.example.com
     * Domaine MI CNAME : mi.example.com
     * Domaine interne MI : example.micpn.com
3. Ajoutez le code suivant pour que le SDK puisse résoudre le domaine d'enregistrement des clics :  

   <Tabs>
   <Tab title="Objective-C">

   Ajouter ce code dans AppDelegate.m

   ```objectivec
   - (NSDictionary *)allHTTPHeaderFieldsForResolveDeepLinkURL:(NSURL *)URL {
       if ([URL.host  isEqual: @"click.example.com"]) {
           return [NSDictionary dictionary];
       }
       else {
           return nil;
       }
   }
   ```

   </Tab>

   <Tab title="Swift">

   Ajouter ce code dans AppDelgate.swift

   ```swift
   func allHTTPHeaderFields(forResolveDeepLinkURL URL: URL!) -> [String : String]! {
       if (URL.host == "click.example.com") {
           /// Change User-Agent
           return [:]
       } else {
           return nil;
       }
   }
   ```

   </Tab>
   </Tabs>

<div id="sending-your-first-email" />

## Envoyer le premier e-mail

1. Créez une URL OneLink dans la page de gestion des liens (ou manuellement).
2. Lors de la création de l'URL OneLink, veillez à encoder toutes les valeurs des paramètres.
3. Nous vous recommandons d'utiliser les paramètres suivants :
   * pid (source média) - Utilisez une source média qui indique cette utilisation, par exemple Email.
   * c (campagne) - Le nom de la campagne que vous souhaitez mesurer.
   * af\_dp - Le schéma d'URI de deep linking vers lequel vos utilisateurs seront deep linkés.
   * af\_web\_dp - Où rediriger les utilisateurs qui cliquent sur le lien depuis un ordinateur de bureau.
   * af\_ios\_url - Où rediriger les utilisateurs qui n'ont pas l'application en cliquant sur le lien depuis un appareil iOS.
   * af\_android\_url - Où rediriger les utilisateurs qui n'ont pas l'application et qui cliquent sur le lien depuis un appareil Android.
4. Placez l'URL OneLink dans l'e-mail que vous créez dans Responsys. Exemple :

   ```http
   <a href="greatapp.onelink.me/abcd/1234567">Téléchargez ma super app !</a>
   ```

   À ce stade, Responsys entoure le lien ci-dessus avec le domaine de clics que vous avez défini dans les étapes précédentes. Tout clic sur le domaine de clics redirige vers le lien d'attribution OneLink. Si l'application est installée sur l'appareil de l'utilisateur, le domaine de clics envoie le deep link dans l'app.

<div id="note" />

> 📄 **Exemple**
>
> Par souci de lisibilité, les paramètres d'URL ne sont pas encodés dans cet exemple :
>
> ```http
> https://greatapp.onelink.me/abcd?pid=Email&c=Spring_Newsletter&is_retargeting=true&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

<div id="testing-your-links" />

### Tester vos liens

Après avoir suivi toutes les étapes mentionnées ci-dessus, créé l'URL OneLink et l'avoir placée dans un e-mail, envoyez-vous un e-mail de test.

Que va-t-il se passer ?

Si l'application est bien installée, elle devrait être appelée.Si les bonnes API de deep linking du SDK AppsFlyer ont été mises en œuvre, vous devez être deep linké vers le contenu attendu.  
Un clic doit apparaître à la fois dans le tableau de bord d'AppsFlyer, attribué à la source média et à la campagne fournies, et dans les données de Responsys.

<div data-zendesk-anchors="prerequisites=conditions-pr%C3%A9alables h_01HDNSK7GR33AN2M4GP956S1FD=conditions-pr%C3%A9alables setting-up-oracle-responsys-click-domain=configuration-du-domaine-de-clics-dans-oracle-responsys h_01HDNSK7GR84QSRTS86GH556WK=configuration-du-domaine-de-clics-dans-oracle-responsys step-1-set-up-a-click-domain-in-oracle-responsys=%C3%A9tape-1--configurer-un-domaine-de-clics-dans-oracle-responsys h_01HDNSK7GRHYJZSMYCMT9RVEBW=%C3%A9tape-1--configurer-un-domaine-de-clics-dans-oracle-responsys step-2-give-responsys-an-aasa-ios-and-an-asset-links-file-android=%C3%A9tape-2--donner-%C3%A0-responsys-un-fichier-aasa-ios-et-un-fichier-asset-links-android h_01HDNSK7GRW57NNXMN1SWFTTFZ=%C3%A9tape-2--donner-%C3%A0-responsys-un-fichier-aasa-ios-et-un-fichier-asset-links-android h_01HDNSK7GR77N60SFVBD57S9GQ=aasa-for-ios h_01HDNSK7GR6ADJCPG63ZVP19NJ=asset-links-for-android setting-up-your-app=configuration-de-votre-app h_01HDNSK7GRN751HAPPQ3HVRMDG=configuration-de-votre-app h_01HDNSK7GRHCK378A8XKMK7ZZF=step-1-for-android-setting-up-your-app-to-support-app-links adding-the-click-domain-to-the-activity-in-the-android-manifest=ajouter-le-domaine-de-clic-%C3%A0-lactivit%C3%A9-dans-le-manifeste-android h_01HDNSK7GRQNQGWXAEGHSTHADH=ajouter-le-domaine-de-clic-%C3%A0-lactivit%C3%A9-dans-le-manifeste-android setting-up-the-app-to-resolve-click-domains=configurez-lapplication-pour-les-domaines-de-clics h_01HDNSK7GRP9ND0MHC3ZHD7G8H=configurez-lapplication-pour-les-domaines-de-clics h_01HDNSK7GRJ682QYAMPB4PSGRZ=step-1-for-ios-setting-up-your-app-to-support-universal-links associating-click-domains-in-xcode=associer-des-domaines-de-clics-dans-xcode h_01HDNSK7GSRENM232MQ25EB3J3=associer-des-domaines-de-clics-dans-xcode step-2-setting-up-the-app-to-resolve-click-domains=%C3%A9tape-2-configurer-lapplication-pour-les-domaines-de-clics h_01HDNSK7GSP08G2EQSNVR5G45B=%C3%A9tape-2-configurer-lapplication-pour-les-domaines-de-clics sending-your-first-email=envoyer-le-premier-e-mail h_01HDNSK7GSA9VAMTRFCX8SZGSC=envoyer-le-premier-e-mail h_01HDNSK7GS8HP7BAA8BYBVBABD=exemple testing-your-links=tester-vos-liens h_01HDNSK7GSTAJXAP6KGKE9TD8T=tester-vos-liens" />
