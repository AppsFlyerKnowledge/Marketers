---
title: Extension du SDK Adobe Launch
metadata:
  keywords:
    - SDK
    - Adobe
    - Advertisers
    - AppsFlyer SDK
    - Adobe Experience Platform
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
  created_at: '2019-02-13T08:03:45Z'
  edited_at: '2024-03-05T14:48:14Z'
  id: 360000939097
  locale: fr
  section: Other platforms
  section_id: 6551244207121
  url: https://support.appsflyer.com/hc/fr/articles/360000939097
---
> **En bref :** envoyer des données aux SDK Adobe Launch et SDK AppsFlyer via l’extension du SDK AppsFlyer Adobe Launch.

## Introduction

Le SDK Adobe Launch fait partie intégrante d'Adobe Experience Platform. Adobe Experience Platform aide les entreprises à rassembler, consolider et analyser les données provenant de plusieurs applications et plateformes. Il permet aux chefs d'entreprise et aux développeurs de mieux comprendre le comportement des clients afin d'optimiser leur expérience et améliorer le contenu. Si votre application exploite à la fois le SDK Adobe Launch et le SDK AppsFlyer, vous pouvez envoyer des données aux deux via l'**extension SDK AppsFlyer Adobe Launch**. Cela simplifie l’ensemble de votre processus de développement et permet d'obtenir une base de code plus simple et plus facile à maintenir.

> 📘 **Remarque**
>
> Si vous utilisez l'extension Adobe Launch, l’intégration standard <Anchor target="_blank" href="/marketers/fr/docs/adobe-analytics-integration-with-appsflyer">d'Adobe Analytics</Anchor> n'est pas nécessaire.

## Conditions techniques

Quelques éléments sont nécessaires avant d'intégrer l’extension SDK AppsFlyer Adobe.

<div id="get-your-appsflyer-dev-key" />

<Accordion title="Récupérer votre clé dev">

<Image alt="dev_key.png" src="https://files.readme.io/bf25b5d583f3eaab57c230b68764f08c49806a50401955a511993d8a847e7d42-360006050318.png" width="357px" />

1. Dans le tableau de bord de votre app, cliquez sur ***Réglages de l'app*** dans ***Configuration*** dans le menu de gauche.
2. Dans ***Installation du SDK***, copiez votre ***clé dev***.

</Accordion>

<div id="get-your-app-id" />

<Accordion title="Obtenir votre ID d'app">

* Pour Android - l’ID d’app est le nom du package, par exemple example.com.app.
* Pour iOS - l'ID d’app est l'identifiant iTunes de l'application sans le préfixe *id*, par exemple 123456748.

</Accordion>

## Étape 1 : Configuration d'Adobe Launch

Suivez les instructions ici pour configurer Adobe Launch.

<div id="11-creating-a-new-property-in-adobe-launch" />

<Accordion title="1.1 Création d'une nouvelle propriété dans Adobe Launch">

[![](https://files.readme.io/d03e61047c536785e7601d4f0efbd9b6488bd41c92efdd6e0d1021b42a5bec3a-small-360005983477.png)](https://files.readme.io/d03e61047c536785e7601d4f0efbd9b6488bd41c92efdd6e0d1021b42a5bec3a-small-360005983477.png)

1. Connectez-vous à Adobe Experience Cloud.
2. Sélectionner ***Lancer***.
3. Cliquez sur ***Aller au lancement***.
4. Cliquez sur ***Nouvelle propriété***.
5. Donnez un nom à la propriété et sélectionnez ***Mobile***.
6. Cliquez sur ***Enregistrer***.

</Accordion>

<div id="12-installing-required-adobe-launch-extensions" />

<Accordion title="1.2 Installation des extensions Adobe Launch requises">

Installez les extensions suivantes dans Adobe Launch :

[![adboe_extensions.png](https://files.readme.io/bf0c0652c3807d4da0819a62b600ac875af1f8764387a36cc3f256a58e1ea852-360005983597.png)](https://files.readme.io/bf0c0652c3807d4da0819a62b600ac875af1f8764387a36cc3f256a58e1ea852-360005983597.png)

* Adobe Analytics - connecte les données enregistrées par le SDK au module Adobe Analytics.
* Extension SDK AppsFlyer - envoie des données et des événements à la fois à Adobe et à AppsFlyer en utilisant le SDK Adobe Launch.
* Adobe Profile - permet au SDK de stocker des données dans un profil du côté client.
* Adobe Mobile Core - permet de configurer le SDK mobile et donne accès aux événements et conditions du cycle de vie par défaut.

#### Installation de l'extension Adobe Analytics

1. Connectez-vous à Adobe Analytics.
2. <Anchor target="_blank" href="https://docs.adobe.com/help/en/analytics/admin/admin-console/create-report-suite.html">Créez une suite de rapports</Anchor>.
3. Reconnectez-vous à Adobe Launch.
4. Dans la liste des propriétés, cliquez sur la propriété que vous venez de créer.
5. Cliquez sur ***Extensions***.
6. Recherchez et installez ***Adobe Analytics***.
7. Dans ***Suites de rapports***indiquez la suite de rapports que vous avez créée à l'étape 2.
8. Cliquez sur ***Enregistrer***.

#### Installation de l'extension du SDK AppsFlyer

1. Sélectionnez à nouveau ***Extensions***.
2. Recherchez et installez ***Extension SDK AppsFlyer***.
3. Sous ***ID d’app iOS AppsFlyer,***indiquez l'identifiant de l'app iOS que vous avez obtenu à l'étape Conditions techniques.
4. Dans ***Clé dev AppsFlyer*** indiquez la clé dév que vous avez obtenue à l'étape des Conditions techniques.
5. Activez ***Envoyer les données d'attribution à Adobe Analytics***. Notez qu'il existe certaines <Anchor target="_blank" href="/marketers/fr/docs/user-level-data-retention">restrictions concernant le partage des données relatives aux utilisateurs avec des plateformes d'analyse tierces</Anchor>.
6. Cliquez sur ***Enregistrer***.

#### Installer le profil et l'extension Mobile Core

1. Sélectionnez à nouveau ***Extensions***.
2. Recherchez et installez ***Profile***.
3. Recherchez et installez ***Mobile Core***.
   * Lors de l'installation de Mobile Core, il suffit de sauvegarder l'extension telle quelle. Il n'est pas nécessaire de spécifier le ***serveur Experience Cloud***.

</Accordion>

## Étape 2 : Mise en œuvre de l'extension SDK Adobe AppsFlyer

Suivez les instructions de cette section pour installer l'extension SDK Adobe dans votre application.

<div id="21-adding-the-sdk-to-the-app" />

<Accordion title="2.1 Ajouter le SDK à l'application">

[![adobe_sdk.png](https://files.readme.io/076e6cc5911a0a515e5510a8da233bcefcb4144c92cf49190416b593fcdecc8f-small-360006050518.png)](https://files.readme.io/076e6cc5911a0a515e5510a8da233bcefcb4144c92cf49190416b593fcdecc8f-small-360006050518.png)

1. Dans votre propriété Adobe, sélectionnez ***Environnements***.
2. Sélectionnez l'environnement pour lequel vous souhaitez déployer le SDK.
3. Dans la partie droite, cochez sur l’icône.
4. Copiez les extraits de code dans la fenêtre qui s'ouvre et suivez les instructions. Si c'est vous qui configurez Adobe, envoyez ces extraits de code à votre développeur d'applications.

</Accordion>

<div id="22-publishing-the-environment" />

<Accordion title="2.2 Publication de l'environnement">

Pour compléter la mise en œuvre du SDK, vous devez publier l'environnement dans une bibliothèque.

[![adobe_publishing.png](https://files.readme.io/4e9ad08fce291ef59e7a3567726c678754ae3a3c96de75f4ae27cd80a84945d1-small-360006050558.png)](https://files.readme.io/4e9ad08fce291ef59e7a3567726c678754ae3a3c96de75f4ae27cd80a84945d1-small-360006050558.png)

1. Dans votre propriété Adobe, sélectionnez ***Publication***.
2. Cliquez sur ***Ajouter une nouvelle bibliothèque***.
3. Donnez-lui un nom et, dans Environnement, sélectionnez ***Développement***.
4. Cliquez sur ***Enregistrer et monter pour le développement***.
5. Une fois la compilation terminée, dans ***Développement***cliquez sur les trois points situés à côté de la bibliothèque, puis sélectionnez ***Envoyer pour approbation***.
6. Dans ***Envoyé***cliquez sur les trois points à côté de la bibliothèque et sélectionnez ***Monter pour le test***.
7. Une fois la compilation terminée, cliquez sur les trois points situés à côté de la bibliothèque et sélectionnez ***Approuver la publication***.
8. Dans ***Approuver***cliquez sur les trois points à côté de la bibliothèque et sélectionnez ***Monter et publier en production***.

</Accordion>

<div id="23-adding-android-install-referrer-to-your-app" />

<Accordion title="2.3 Ajout d'un référent d'installation Android à votre app">

Le référent d'installation Android améliore la précision de l'attribution, protège contre les installations frauduleuses, et autres. Il est pris en charge par le SDK Android AppsFlyer version 4.8.6.

> 📘 **Remarque**
>
> Google a rendu le BroadcastReceiver obsolète en mars 2020.
>
> * Cette modification n'affecte pas l'app.
> * Le BroadcastReceiver peut malgré tout vous être encore utile pour l'attribution hors store. Renseignez-vous auprès du store dans lequel l'app est répertoriée pour vous en assurer.
> * L'implémentation du référent d'installation est désormais obligatoire.

Il existe deux façons d'ajouter le référent d'installation à votre app :

* En utilisant Gradle (recommandé)
* Ajout manuel du référent d'installation

<Tabs>
<Tab title="Ajout du référent d'installation à l'aide de Gradle">

Ajoutez le référent d'installation Android en tant que dépendance. Vous pouvez trouver la dernière version <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.android.installreferrer/installreferrer/1.0">ici</Anchor>.

1.
   ```java
   dependencies {
   //make sure to use the latest SDK version: https://mvnrepository.com/artifact/com.appsflyer/af-android-sdk
   	implementation 'com.appsflyer:af-android-sdk:5.+'
   	implementation 'com.android.installreferrer:installreferrer:1.1'
   }
   ```
2. Synchronisez le projet pour récupérer les dépendances. Voir la capture d'écran suivante :  

    [![android_af_sdk_sync_gradle.png](https://files.readme.io/f8835cf76d51d7ddeb51206707d95b7214e398c5960299893118ad57ccffe890-22939234622609.png)](https://files.readme.io/f8835cf76d51d7ddeb51206707d95b7214e398c5960299893118ad57ccffe890-22939234622609.png)

Si vous utilisez ProGuard et souhaitez utiliser la nouvelle API référent d’installation Google, vous devez définir la règle ProGuard suivante : `-dontwarn com.android.installreferrer`

</Tab>

<Tab title="Ajout manuel du référent d'installation">

1. <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.android.installreferrer/installreferrer/1.0">Téléchargez le fichier Référent d’installation</Anchor>
2. <Anchor target="_blank" href="https://stackoverflow.com/questions/16682847/how-to-manually-include-external-aar-package-using-new-gradle-android-build-syst">Ajoutez-le au projet</Anchor>
3. Ajoutez l'autorisation suivante au manifeste : `com.google.android.finsky.permission.BIND_GET_INSTALL_REFERRER_SERVICE`

</Tab>
</Tabs>

</Accordion>

<div id="24-setting-required-permissions" />

<Accordion title="2.4 Définir les autorisations requises">

L'ajout d'autorisations permet d'augmenter le taux d'<Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#probabilistic-modeling">attribution de modélisation probabiliste</Anchor>. Cela permet au SDK d'envoyer plus de données,comme les données de réseau Wi-Fi ou d'opérateurs. Vous pouvez trouver ces données dans les <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">rapports de données brutes</Anchor> et les utiliser pour l'analyse et l'optimisation des campagnes.

#### Ajouter les autorisations requises

1. Ajoutez les autorisations suivantes à AndroidManifest.xml :  

   ```html Markup
   <uses-permission android:name="android.permission.INTERNET" />
   <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
   <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
   <!-- Optional : -->
   <uses-permission android:name="android.permission.READ_PHONE_STATE" />
   ```

</Accordion>

## Utilisation de l'extension SDK Adobe

Vous pouvez maintenant commencer à utiliser l'extension SDK Adobe pour envoyer des données à Adobe et à AppsFlyer.

> 📘 **Remarque**
>
> Actuellement, l'extension SDK Adobe Launch permet uniquement d'obtenir des données de conversion et d'envoyer des événements. Cependant, lorsque vous ajoutez l'extension SDK Adobe Launch à votre app, le SDK AppsFlyer est également ajouté. Toute fonctionnalité actuellement absente de l'extension SDK Adobe peut donc être implémentée à l'aide du SDK AppsFlyer.

<div id="sending-events" />

<Accordion title="Envoyer les événements">

Les événements in-app permettent une analyse de ce qui se passe dans votre application. Nous vous recommandons de prendre le temps de définir les évènements que vous voulez enregistrer. L'enregistrement des évènements in-app vous permet de mesurer les KPI tels que le ROI (retour sur investissement) et la LTV (durée lifetime).

L'extension de SDK Adobe Launch vous permet d'envoyer des données d'événements in-app autant à Adobe qu’à AppsFlyer. Vous pouvez ensuite utiliser Adobe Analytics pour analyser le comportement des utilisateurs, et AppsFlyer pour analyser le ROI et la LTV.

<Tabs>
<Tab title="Android">

```java
final Map<String,String> eventMap = new HashMap<>();  
eventMap.put("currency", "USD");  
eventMap.put("revenue", "200");  
eventMap.put("freehand", "param");

MobileCore.trackAction("af_purchase", eventMap);
```

</Tab>

<Tab title="iOS">

```objectivec
[ACPCore trackAction:@"af_purchase data:@{@"revenue":@"200",@"currency":@"USD"];
```

</Tab>
</Tabs>

L'envoi des événements, comme stipulé dans le code ci-dessus, génère dans le tableau de bord AppsFlyer un événement nommé af\_purchase, ayant un revenu de 200 USD. Cet événement est également envoyé à Adobe Analytics, où il s’affiche.

Toutes les <Anchor target="_blank" href="https://dev.appsflyer.com/docs/direct-deep-linking-1">données de conversion</Anchor> envoyées avec les événements portent le préfixe ***appsflyer***. Voir le tableau suivant pour exemples :

| Variables de données de conversion avec préfixes |
| --- |
| appsflyer.af\_click\_lookback |
| appsflyer.install\_time |
| appsflyer.cost\_cents\_USD |
| appsflyer.media\_source |
| appsflyer.af\_adset |
| appsflyer.click\_time |
| appsflyer.orig\_cost |
| appsflyer.campaign |

Les données de conversion sont utilisées dans l'application que vous créez dans Adobe Mobile Services. D'autres paramètres peuvent apparaître dans les données de conversion. Pour en savoir plus, cliquez <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#paramètres-du-lien-dattribution">ici</Anchor>.

</Accordion>

<div id="getting-data-for-deep-linking-and-deferred-deep-linking" />

<Accordion title="Obtenir des données pour le deep linking et le deep linking différé.">

Le deep linking et le deep linking différé vous aident à améliorer l'expérience de l'utilisateur. Ils vous permettent d'ouvrir l'app dans le cadre d'activités spécifiques, et de personnaliser le contenu en fonction des données de la campagne.

Pour obtenir les données du deep linking, vous devez utiliser les rappels d'extension.

<Tabs>
<Tab title="Android">

Dans la classe d'application globale, implémentez le code suivant :

```java
AppsFlyerAdobeExtension.registerAppsFlyerExtensionCallbacks(new AppsFlyerExtensionCallbacksListener() {
		@Override
		public void onCallbackReceived(Map<String, String> callback) {
			Log.d(AppsFlyerLibCore.LOG_TAG, callback.toString());
			if(callback.get("callback_type").equals("onConversionDataReceived")){
				// conversion data returned 
				if(callback.get("is_first_launch").equals("true")){
					String af_status = callback.get("af_status");
					if(af_status.equals("Non-organic")){
						Log.d(AppsFlyerLibCore.LOG_TAG, "this is first launch and a non organic install!");
					}
				}
			} else if(callback.get("callback_type").equals("onAppOpenAttribution")){
				// direct deeplink - redirect user
				Log.d(AppsFlyerLibCore.LOG_TAG, callback.toString());
			}
		}
		@Override
		public void onCallbackError(String errorMessage) {
			Log.d("TAG", errorMessage);
		}
	});
```

</Tab>

<Tab title="iOS">

Dans AppDelegate.m, implémentez le code suivant :

```objectivec
[AppsFlyerAdobeExtension registerCallbacks:^(NSDictionary *dictionary) {
        NSLog(@"[AppsFlyerAdobeExtension] Received callback: %@", dictionary);
        if([[dictionary objectForKey:@"callback_type"] isEqualToString:@"onConversionDataReceived"]){
            if([[dictionary objectForKey:@"is_first_launch"] boolValue] == YES){
                NSString* af_status = [dictionary objectForKey:@"af_status"];
                if([af_status isEqualToString:@"Non-organic"]){
                    NSLog(@"this is first launch and a non organic install!");
                }
            }
        } else if([[dictionary objectForKey:@"callback_type"] isEqualToString:@"onAppOpenAttribution"]) {
            NSLog(@"onAppOpenAttribution Received");
        }
     }];
    [AppsFlyerAdobeExtension callbacksErrorHandler:^(NSError *error) {
          NSLog(@"[AppsFlyerAdobeExtension] Error recieving callback: %@" , error);
    }];
```

</Tab>
</Tabs>

</Accordion>

## Connecter les données de conversion d'AppsFlyer

Les données de conversion sont envoyées avec les événements à la plateforme Adobe. Ces variables vous permettent d'appliquer une logique et des règles aux dimensions, aux mesures ou aux filtres des rapports.

![adobe_analytics.png](https://files.readme.io/9c4355286d2e5f2254a8a16a49b1b1305b56628b54e738efcd4fdc90a6de8fab-360006050778.png)

1. Connectez-vous à vos <Anchor target="_blank" href="https://mobilemarketing.adobe.com">Services Adobe Mobile</Anchor>.
2. Sélectionnez l'application concernée et ouvrez la page ***Gérer les variables et les métriques***.
3. Sélectionnez l’onglet ***Variables personnalisées*** et configurez les variables pour mapper les données du SDK AppsFlyer au système Adobe.
4. Saisissez un nom adéquat pour chaque variable personnalisée.
5. Sélectionnez ou saisissez les données de conversion AppsFlyer mappées et choisissez votre ***échelle de persistance***.

Voir le tableau suivant pour l'affectation des variables de contexte AppsFlyer :

| **Nom recommandé pour le mappage** | **Données de conversion** |
| --- | --- |
| Fenêtre rétrospective AppsFlyer | appsflyer.af\_click\_lookback |
| Heure d'installation pour AppsFlyer | appsflyer.install\_time |
| Coûts AppsFlyer (Cents US) | appsflyer.cost\_cents\_USD |
| Source média AppsFlyer | appsflyer.media\_source |
| Adset AppsFlyer | appsflyer.af\_adset |
| AppsFlyer (Clic DB) | appsflyer.click\_time |
| Coût initial AppsFlyer | appsflyer.orig\_cost |
| Campagne AppsFlyer | appsflyer.campaign |

### Utilisation des données de conversion mappées par AppsFlyer pour l'analyse

Toutes les données provenant du SDK sont disponibles dans la suite de rapports Adobe Analytics connectée à l'application.

Vous pouvez utiliser les données, dimensions et métriques associées dans vos rapports et tableaux de bord Adobe Analytics. Ces données sont également disponibles dans le tableau de bord AppsFlyer pour l'attribution et l'analyse des événements in-app.

<div data-zendesk-anchors="overview=introduction h_01HQQN1Y7MP7B0GXJFP5330G80=introduction h_01HQQNCMYNN0YH7S8Q5F2EWFG5=remarque prerequisites=conditions-techniques h_01HQQN1JWAQZZ9S3YV7VXTMRWM=conditions-techniques h_01HQQN1JWA4JYET26CB11JGY46=get-your-appsflyer-dev-key h_01HQQN1JWAHYQBRY43EWANQ57Z=get-your-app-id step-1-configuring-adobe-launch=%C3%A9tape1-configuration-dadobe-launch h_01HQQN1JWAAR873B679QGA9NSX=%C3%A9tape1-configuration-dadobe-launch h_01HQQN1JWAE1T7SP3DHTFB55TK=11-creating-a-new-property-in-adobe-launch h_01HQQN1JWA8FDWMNZ4Y17AWYKW=12-installing-required-adobe-launch-extensions installing-adobe-analytics-extension=installation-de-lextension-adobe-analytics h_01HQQN1JWAMB8607K8V2F3YKHE=installation-de-lextension-adobe-analytics installing-appsflyer-sdk-extension=installation-de-lextension-du-sdk-appsflyer h_01HQQN1JWAYHP9243MTFZ4B2EF=installation-de-lextension-du-sdk-appsflyer install-profile-and-mobile-core-extension=installer-le-profil-et-lextension-mobile-core h_01HQQN1JWA1TEBQY1NH3YP2HQB=installer-le-profil-et-lextension-mobile-core step-2-implementing-appsflyer-adobe-sdk-extension=%C3%A9tape2-mise-en-%C5%93uvre-de-lextension-sdk-adobe-appsflyer h_01HQQN1JWB3B24RHP9QMNPJK8J=%C3%A9tape2-mise-en-%C5%93uvre-de-lextension-sdk-adobe-appsflyer h_01HQQN1JWBMP4ARMH2VPX35TGH=21-adding-the-sdk-to-the-app h_01HQQN1JWBV3144WY92PAX6PW2=22-publishing-the-environment h_01HQQN1JWBRRCTGA6Q9RDC41KN=23-adding-android-install-referrer-to-your-app h_01HQQN1JWB40T4K3ZJB6AE42WQ=remarque-1 h_01HQQN1JWB19NTCNTWX9QRP8AC=24-setting-required-permissions add-required-permissions=ajouter-les-autorisations-requises h_01HQQN1JWBVVVGRRXGX9ZJTBT8=ajouter-les-autorisations-requises using-the-adobe-sdk-extension=utilisation-de-lextension-sdk-adobe h_01HQQN1JWBFD2CZ4PMCBRM3JN8=utilisation-de-lextension-sdk-adobe h_01HQQN1JWBSBVFVB911WH54Q32=remarque-2 h_01HQQN1JWBVZDAVAZD4NXMBG4S=sending-events h_01HQQN1JWBXG0JCE9RKA659H6V=getting-data-for-deep-linking-and-deferred-deep-linking connecting-appsflyer-conversion-data=connecter-les-donn%C3%A9es-de-conversion-dappsflyer h_01HQQN1JWBMBXGQFKGWHE058VT=connecter-les-donn%C3%A9es-de-conversion-dappsflyer using-appsflyer-mapped-conversion-data-for-analytics-and-analysis=utilisation-des-donn%C3%A9es-de-conversion-mapp%C3%A9es-par-appsflyer-pour-lanalyse h_01HQQN1JWB0WBD6HZXQN6STJY9=utilisation-des-donn%C3%A9es-de-conversion-mapp%C3%A9es-par-appsflyer-pour-lanalyse" />
