---
title: Intégration d'Iterable avec AppsFlyer
metadata:
  keywords:
    - OneLink
    - Advertisers
    - ESP
    - Developers
    - Iterable
    - Deep Likning
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-09-16T13:14:19Z'
  edited_at: '2024-10-23T11:53:19Z'
  id: 360002522337
  locale: fr
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/fr/articles/360002522337
---
> **En bref :** Intégrer les liens d'attribution basés sur OneLink au système Iterable pour <Anchor target="_blank" href="/marketers/fr/docs/email-service-provider-esp-integration-guide">utiliser le deep linking à partir des e-mails</Anchor>. L'intégration utilise le support d'Iterable pour les liens universels en plus des domaines de suivi de clics personnalisés.

![iterable-af-logo.png](https://files.readme.io/e339ea75a54e53711f3c577c7f82339151af13e6c086cc1435cbb57cf1fae3f0-49839295443089.png)

## Introduction

Les ESP (fournisseurs de services d'e-mails) peuvent être d'excellentes sources de trafic segmenté.

L'un des problèmes des ESP est d'enregistrer les clics tout en conservant la fonctionnalité du deep linking. Les ESP encapsulent les URL de deep linking avec leur propre domaine d'enregistrement des clics. Cette procédure peut parfois perturber le processus des liens universels sur iOS.

Avec Iterable, qui prend en charge les liens universels en plus de leur domaine d'enregistrement de clics, il est toujours possible d'effectuer du deep linking et de l'enregistrement de clics.

<div id="prerequisites" />

## Conditions préalables

<Tabs>
<Tab title="iOS">

* SDK AppsFlyer iOS version 4.9.0

</Tab>

<Tab title="Android">

* SDK AppsFlyer Android version 4.9.0

Iterable ne prend pas en charge les liens d’app Android. Toutefois, <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">le deep linking via le schéma d’URI est toujours pris en charge.</Anchor> Aucune action particulière n'est requise de la part d'Iterable pour prendre en charge le deep linking sur Android.

</Tab>
</Tabs>

<div id="setting-up-iterable" />

## Mise en place d'Iterable

<div id="step-1-setting-up-link-branding-in-iterable" />

### Étape 1 : Mise en place du marquage des liens dans Iterable

Créez un domaine dédié à l'enregistrement des clics et définissez un sous-domaine (par exemple, [click.exemple.com](http://click.example.com)). Vous pouvez acheter un domaine désigné ou utiliser votre propre domaine.

Pour plus d'informations sur la création d'un domaine d'enregistrement de clics avec Iterable, voir <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/115002651226-Setting-up-mail-domains">ici.</Anchor>

<div id="step-2-uploading-your-ssl-certificate-to-iterable" />

### Étape 2 : Téléchargement de votre certificat SSL sur Iterable

Votre domaine d'enregistrement des clics doit inclure le certificat SSL de votre domaine. Le certificat SSL doit être installé dans votre compte Iterable. Les instructions relatives à l'installation de vos certificats SSL sont disponibles <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/115000427446-How-to-Set-up-HTTPS-for-Links-for-Click-Tracking">ici.</Anchor>

<div id="step-2-give-iterable-an-aasa-ios-and-an-asset-links-file-android" />

### Étape 2 : Fournir à Iterable un fichier AASA (iOS) et un fichier Asset Links (Android).

<div id="aasa-for-ios" />

<Accordion title="AASA pour iOS">

Pour qu'Iterable prenne en charge les liens universels iOS, un fichier AASA est nécessaire. Consultez les instructions suivantes.

Lorsque vous configurez OneLink avec des liens universels, vous avez déjà une AASA associée à OneLink. Pour obtenir l'AASA :

1. Allez dans les ***templates OneLink*** et trouvez un OneLink configuré avec des liens universels.
2. Ajoutez **/.well-known/apple-app-site-association** à la fin de l'URL OneLink.
3. Collez le OneLink dans la barre d'adresse du navigateur et appuyez sur Entrée. Par exemple : **`<OneLinkSubdomain>`.onelink.me/.well-known/apple-app-site-association**. Le fichier AASA est alors téléchargé sur votre ordinateur. Vous pouvez l'ouvrir à l'aide d'un simple éditeur de texte.
4. Définissez les règles de réécriture des liens. Pour plus d'informations, <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/360035496511">veuillez cliquer ici</Anchor>.
5. Envoyez ce fichier AASA à Iterable. Pour plus d'informations et pour en savoir plus sur le contenu de ce fichier, voir <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/360035496511-iOS-Universal-Lin">ce guide</Anchor>.

</Accordion>

<div id="asset-links-for-android" />

<Accordion title="Asset Links pour Android">

Lorsque vous configurez OneLink avec des liens d'app, un fichier Asset Links est déjà associé à OneLink. Pour obtenir le fichier Asset Links :

1. Allez dans les ***templates OneLink*** et trouvez un OneLink configuré avec des liens d’app.
2. Ajoutez **/.well-known/assetlinks.json** à la fin de l'URL OneLink.
3. Collez le OneLink dans la barre d'adresse du navigateur et appuyez sur Entrée. Par exemple :**`<OneLinkSubdomain>`.onelink.me/.well-known/assetlinks.json**. Le fichier Asset Links est alors téléchargé sur votre ordinateur. Vous pouvez l'ouvrir à l'aide d'un simple éditeur de texte.
4. Envoyez ce fichier Asset Links à Iterable. Pour plus d'informations et pour en savoir plus sur le contenu de ce fichier, voir <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/360035127392">ce guide Iterable</Anchor>.

</Accordion>

<div id="setting-up-your-app" />

## Configuration de votre app

Pour configurer vos applications de manière à ce qu'elles prennent en charge les liens d’app et les liens universels, veuillez vous reporter à ce qui suit.

<div id="step-1-for-android-setting-up-your-app-to-support-app-links" />

<Accordion title="Étape 1 pour Android : Configurer votre application pour qu'elle prenne en charge les liens d’app">

<div id="step-1-adding-the-click-domain-to-the-activity-in-the-android-manifest" />

#### Étape 1 : Ajouter le domaine de clic à l'activité dans le manifeste Android

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

<div id="step-2-setting-up-the-app-to-resolve-click-domains" />

#### Étape 2 : Configurer l'application pour les domaines de clics

Le SDK doit résoudre le OneLink derrière le domaine de clic pour obtenir les détails de la campagne. Les détails sont renvoyés dans la méthode `onAppOpenAttribution`.

Pour résoudre les domaine de clics :

1. Assurez-vous de posséder le SDK 4.9.0 ou +.
2. Liste des domaines de clics dans le SDK d'API `setResolveDeepLinkURLs`. Cette API doit être appelée avant l'initialisation du SDK. Pour plus d'informations, voir la documentation du SDK <Anchor target="_blank" href="/marketers/fr/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">ici.</Anchor>  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("click.example.com");
   ```

</Accordion>

<div id="step-1-for-ios-setting-up-your-app-to-support-universal-links" />

<Accordion title="Étape 1 pour iOS : Configurer votre application pour qu'elle prenne en charge les liens universels">

Cette section explique comment configurer votre app pour qu'elle prenne en charge les liens universels.

<div id="step-1-associating-click-domains-in-xcode" />

#### Étape 1 : Associer des domaines de clics dans Xcode

1. Dans Xcode, cliquez sur votre projet.
2. Cliquez sur ***Capacités***.[![configure-xcode-deeplinking-domain.png](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)
3. Activez les ***Domaines associés**.*
4. Cliquez sur le signe + et ajoutez votre domaine de clics. Par exemple, applinks:click.example.com.

</Accordion>

Pour configurer le SDK afin de résoudre les deep links, veuillez suivre les étapes ci-dessous.

<div id="step-2-for-android-resolve-deep-links" />

<Accordion title="Étape 2 pour Android : résoudre les deep links">

Le SDK doit résoudre le OneLink derrière le domaine de clic pour obtenir les détails de la campagne. Les détails sont renvoyés dans la méthode `onAppOpenAttribution`.

Pour résoudre les domaine de clics :

1. Assurez-vous de posséder le SDK 4.9.0 ou +.
2. Dressez la liste des domaines de clics dans la propriété SDK `resolveDeepLinkURLs`. Cette propriété doit être définie avant l'initialisation du SDK. Pour plus d'informations, voir la documentation du SDK <Anchor target="_blank" href="/marketers/fr/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">ici.</Anchor>  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("clickdomain.com", "myclickdomain.com", "anotherclickdomain.com");
   ```

</Accordion>

<div id="step-2-for-ios-resolve-deep-links" />

<Accordion title="Étape 2 pour iOS : résoudre les deep links">

Le SDK doit résoudre le OneLink derrière le domaine de clic pour obtenir les détails de la campagne. Les détails sont renvoyés dans la méthode `onAppOpenAttribution`.

Pour résoudre les domaine de clics :

1. Assurez-vous de posséder le SDK 4.9.0 ou +.
2. Dressez la liste des domaines de clics dans la propriété SDK `resolveDeepLinkURLs`. Cette propriété doit être définie avant l'initialisation du SDK. Pour plus d'informations, voir la documentation du SDK <Anchor target="_blank" href="/marketers/fr/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">ici.</Anchor>  

   <Tabs>
   <Tab title="Objective-C">

   ```objectivec
   [AppsFlyerLib shared].resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```

   </Tab>

   <Tab title="Swift">

   ```swift
   AppsFlyerLib.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   </Tab>
   </Tabs>

3. Ajoutez le code suivant pour que le SDK puisse résoudre le domaine d'enregistrement des clics :  

   <Tabs>
   <Tab title="Objective-C">

   Ajoutez ce code dans AppDelegate.m

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

   Ajoutez ce code dans AppDelgate.swift

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

</Accordion>

<div id="sending-your-first-email" />

## Envoyer le premier e-mail

1. Créez une URL OneLink sur la page de gestion des liens (ou manuellement).
2. Lors de la création de l'URL OneLink, veillez à encoder toutes les valeurs des paramètres.
3. Nous vous recommandons d'utiliser les paramètres suivants :
   * pid (source média) - Utilisez une source média qui indique cette utilisation, par exemple e-mail.
   * c (campagne) - Le nom de la campagne que vous souhaitez mesurer.
   * af\_dp - Le schéma d'URI de deep linking vers lequel vos utilisateurs seront deep linkés.
   * af\_web\_dp - Où rediriger les utilisateurs qui cliquent sur le lien sur le bureau.
   * af\_ios\_url - Où rediriger les utilisateurs qui n'ont pas l'application en cliquant sur le lien depuis un appareil iOS.
   * af\_android\_url - Où rediriger les utilisateurs qui n'ont pas l'application en cliquant sur le lien sur un appareil Android.
4. Placez l'URL de OneLink dans l'e-mail que vous créez dans Iterable. Exemple :

   ```http
   <a href="greatapp.onelink.me/abcd/1234567">Download my great app!</a>
   ```

   À ce stade, Iterable enveloppe le lien ci-dessus avec le domaine de clic que vous avez défini dans les étapes précédentes. Tout clic sur le domaine de clics redirige vers le lien d'attribution OneLink. Si l'application est installée sur l'appareil de l'utilisateur, le domaine de clics envoie le deep link dans l'app.

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

Si l'application est bien installée, elle devrait être appelée. Si les API de deep linking pertinentes du SDK AppsFlyer sont mises en œuvre, vous devriez être redirigé vers le contenu correspondant.  
Un clic doit apparaître à la fois dans le tableau de bord d'AppsFlyer, attribué à la source média et à la campagne fournies, et dans les données d’Iterable.

<div data-zendesk-anchors="h_01HV6PJQRMT8037JMVMMXDPWGN=introduction prerequisites=conditions-pr%C3%A9alables h_01HV6PJQRM5N1K6CY0NSSFXT3X=conditions-pr%C3%A9alables setting-up-iterable=mise-en-place-diterable h_01HV6PJQRMX18FRB3NMZH6NCH0=mise-en-place-diterable step-1-setting-up-link-branding-in-iterable=%C3%A9tape1-mise-en-place-du-marquage-des-liens-dans-iterable h_01HV6PJQRMMYV3A5ZSEGTT7993=%C3%A9tape1-mise-en-place-du-marquage-des-liens-dans-iterable step-2-uploading-your-ssl-certificate-to-iterable=%C3%A9tape2-t%C3%A9l%C3%A9chargement-de-votre-certificat-ssl-sur-iterable h_01HV6PJQRMYDDWK9AKGN258TTM=%C3%A9tape2-t%C3%A9l%C3%A9chargement-de-votre-certificat-ssl-sur-iterable step-2-give-iterable-an-aasa-ios-and-an-asset-links-file-android=%C3%A9tape2-fournir-%C3%A0-iterable-un-fichier-aasa-ios-et-un-fichier-asset-links-android h_01HV6PJQRMFJ23627KS83D4C6A=%C3%A9tape2-fournir-%C3%A0-iterable-un-fichier-aasa-ios-et-un-fichier-asset-links-android h_01HV6PJQRMNSYK8N7QEE00KSPE=aasa-for-ios h_01HV6PJQRMSMZCVJ5XRXZ3SWEH=asset-links-for-android setting-up-your-app=configuration-de-votre-app h_01HV6PJQRMJHDF94JSAT8N8SP9=configuration-de-votre-app h_01HV6PJQRM5S772CTH219MGY44=step-1-for-android-setting-up-your-app-to-support-app-links step-1-adding-the-click-domain-to-the-activity-in-the-android-manifest=%C3%A9tape1-ajouter-le-domaine-de-clic-%C3%A0-lactivit%C3%A9-dans-le-manifeste-android h_01HV6PJQRM2V31JAJ52Q3FHQWH=%C3%A9tape1-ajouter-le-domaine-de-clic-%C3%A0-lactivit%C3%A9-dans-le-manifeste-android step-2%C2%A0setting-up-the-app-to-resolve-click-domains=%C3%A9tape2configurer-lapplication-pour-les-domaines-de-clics h_01HV6PJQRMCRFM90QSP5SS72SE=%C3%A9tape2configurer-lapplication-pour-les-domaines-de-clics h_01HV6PJQRMVJB6J6GV41DCYAVQ=step-1-for-ios-setting-up-your-app-to-support-universal-links step-1-associating-click-domains-in-xcode=%C3%A9tape1-associer-des-domaines-de-clics-dans-xcode h_01HV6PJQRNRW8Y97JWHP0MSXZF=%C3%A9tape1-associer-des-domaines-de-clics-dans-xcode h_01HV6PJQRNHFH8XGMCEWVGSPA5=step-2-for-android-resolve-deep-links h_01HV6PJQRN4NYPWS2XQQSJAM5R=step-2-for-ios-resolve-deep-links sending-your-first-email=envoyer-le-premier-e-mail h_01HV6PJQRN2H29D8HKXHBYE1NB=envoyer-le-premier-e-mail h_01HV6PJQRNB327E42Y0ZJM9306=exemple testing-your-links=tester-vos-liens h_01HV6PJQRNET2J17ZGGZE0K0Q6=tester-vos-liens" />
