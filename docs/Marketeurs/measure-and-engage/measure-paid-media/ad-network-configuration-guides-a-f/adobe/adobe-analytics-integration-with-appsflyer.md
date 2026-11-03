---
title: Intégration d'Adobe Analytics avec AppsFlyer
metadata:
  keywords:
    - Adobe Analytics
    - Integration
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-07-05T07:20:10Z'
  edited_at: '2024-08-26T13:21:04Z'
  id: 115003326706
  locale: fr
  section: Adobe
  section_id: 6551419728657
  url: https://support.appsflyer.com/hc/fr/articles/115003326706
---
> **En bref :** [Adobe Analytics](http://www.adobe.com/marketing-cloud/web-analytics.html) (anciennement Omniture) est un ensemble d'outils d'analyse prédictive et en temps réel intégrables dans des sources tierces. Il comprend les applications Marketing Reports and Analytics (SiteCatalyst), Ad hoc analysis (Adobe Discover) et Insight, qui permettent de créer une vision holistique des activités commerciales en transformant les interactions avec les clients en informations.

## Présentation

Cette intégration consiste en un flux de données bidirectionnel entre Adobe et AppsFlyer. Pour que l'intégration soit réussie, elle nécessite l'implémentation d'un code dans votre app. Les exigences d'AppsFlyer et d'Adobe doivent être respectées pour que l'intégration soit pleinement réussie.

## Configuration de l'intégration d'Adobe Analytics

Si vous utilisez Adobe Analytics Report Suite pour l'analyse des performances globales de la campagne et la création de segments, intégrer AppsFlyer avec Adobe Analytics permettra de transférer automatiquement des données d'attribution d'AppsFlyer à Adobe pour vous aider à atteindre vos objectifs.

### Conditions préalables :

* Configuration des <Anchor target="_blank" href="https://developer.adobe.com/client-sdks/documentation/">documents relatifs au kit SDK mobile Adobe Experience Platform</Anchor>
* <Anchor target="_blank" href="https://marketing.adobe.com/resources/help/en_US/mcvid/">Marketing Cloud Visitor ID</Anchor> ou Experience cloud ID service
* Trois eVars dans chaque suite de rapports à utiliser dans le seul but de cette intégration

### Étape 1 : Partager l'identifiant Adobe Experience Cloud (ECID, Marketing Cloud ID ou Visitor ID) avec AppsFlyer.

Pour extraire et partager l'ID Adobe Experience Cloud :

1. <Anchor target="_blank" href="https://developer.adobe.com/client-sdks/documentation/mobile-core/identity/api-reference/#getexperiencecloudid">Mettez l’app à jour et extrayez l'ID visiteur de Marketing Cloud</Anchor> à l'aide de la méthode du SDK Adobe juste après son initialisation.
2. Utilisez l'une des méthodes du SDK AppsFlyer suivantes pour définir l'ID visiteur Adobe Marketing Cloud :

<div id="setadditionaldata" />

<Accordion title="setAdditionalData">

<Tabs>
<Tab title="Android">

En savoir plus sur [la `setAdditionalData`méthode](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata).

```java
HashMap<String, Object> customData = new HashMap<String,Object>();
customData .put("marketingCloudID", "ADOBE_VISITOR_ID");
AppsFlyerLib.setAdditionalData(customData);
```

</Tab>

<Tab title="iOS">

En savoir plus sur [la `setAdditionalData`méthode](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata).

Objectif C

```objectivec
[[AppsFlyerTracker sharedTracker] setAdditionalData:@{
  @"marketingCloudID" : "ADOBE_VISITOR_ID"
}];
```

Swift

```swift
let CustomDataMap: [AnyHashable: Any] = [
  "marketingCloudID" : "ADOBE_VISITOR_ID"
]
AppsFlyerTracker.shared().customData = CustomDataMap
```

</Tab>

<Tab title="Unity">

En savoir plus sur [la `setAdditionalData`méthode](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata).

```csharp
Dictionary<string, string> CustomDataMap = new Dictionary<string, string>();
CustomDataMap.Add("marketingCloudID", "ADOBE_VISITOR_ID");
AppsFlyer.setAdditionalData(CustomDataMap);
```

</Tab>
</Tabs>

</Accordion>

<div id="setcustomeruserid" />

<Accordion title="Définir l'ID Utilisateur-Client">

<Tabs>
<Tab title="Android">

En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">la</Anchor> méthode<Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">setCustomerUserId</Anchor>.

```java
AppsFlyerLib.getInstance().setCustomerUserId("ADOBE_VISITOR_ID");
```

</Tab>

<Tab title="iOS">

En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">la méthode setCustomerUserId.</Anchor>

Objectif C

```objectivec
NSString *customerUserID = [AppsFlyerLib shared].customerUserID;
```

Swift

```swift
let customerUserID = AppsFlyerLib.shared().customerUserIDp
```

</Tab>
</Tabs>

</Accordion>

<div id="setpartnerdata" />

<Accordion title="setPartnerData">

<Tabs>
<Tab title="Android">

En savoir plus sur [la `setPatnerData`méthode](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setpartnerdata).

```java
Map<String, Object> partnerData = new HashMap();
partnerData.put("puid", "some-adobe-external-id-value");
AppsFlyerLib.getInstance().setPartnerData("aeplaunchmobile_int", partnerData);
```

</Tab>

<Tab title="iOS">

En savoir plus sur [la `setPartnerData`méthode](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setpartnerdata).

```objectivec
NSDictionary *adobeInfo = @{@"external_user_id":@"some-adobe-external-id-value"};[[AppsFlyerLib shared] setPartnerDataWithPartnerId:@"aeplaunchmobile_int" partnerInfo:adobeInfo];
```

</Tab>
</Tabs>

</Accordion>

### Étape 2 : Configurer Adobe analytics dans AppsFlyer

**Conditions minimum :** Avant de configurer l'intégration, assurez-vous de [transmettre l'ID visiteur d'Adobe Marketing Cloud au SDK AppsFlyer.](/docs/adobe-analytics-integration-with-appsflyer#étape1-partager-lidentifiant-adobe-experience-cloud-ecid-marketing-cloud-id-ou-visitor-id-avec-appsflyer)

**Pour activer ou modifier l'intégration :**

1. **Activation :** dans AppsFlyer, dans le menu latéral, choisissez **Collaboration**> **Partenaire Marketplace**.  
   **Modification :** dans AppsFlyer, dans le menu latéral, sélectionnez **Collaboration** > **Intégrations actives**.
2. Recherchez **Adobe Analytics** et sélectionnez-le.
3. Cliquez sur Configurer l'intégration. Vous êtes alors dirigé vers la page de configuration de l'intégration.
4. Dans l'onglet Integration, sélectionnez l'app à intégrer et cochez l’option **Activer le partenaire**.  
   **Remarque : La case doit rester cochée (activée)/span> tant que vous collaborez avec le partenaire.**
5. Depuis le **SDK Adobe Analytics**, dans le fichier **ADBMobileConfig.XML**, copiez l’élément **Report\_Suite\_ID** (surligné en bleu) et l'élément **Adobe\_Analytic\_server\_URL** (surligné en vert) et collez-les dans les champs respectifs de la page d'intégration Adobe Analytics dans AppsFlyer.  

   ![](https://files.readme.io/fb46a40178b88dc8f8fb0f9bcce5aa289fc27c2dbf52d1e67783c7b764729f0f-360001063605.png)
6. Cliquez sur **Enregistrer l'intégration**.

Une fois enregistré, AppsFlyer envoie les données suivantes à Adobe Analytics pour chaque installation organique et non organique :

* Adobe ID (MCVID)
* ID suite de rapports et URL du serveur
* ID appareil du client
* Source média
* Nom de la campagne

> 📘 **Remarque**
>
> Conformément aux conditions de service de Meta ads et de X Ads, AppsFlyer n'a pas le droit de partager les données des utilisateurs avec des tiers. Cela signifie que les installations via Meta ads et X Ads sont envoyées en tant qu'annonces organiques.

### Étape 3 : Cartographier les données vers les eVars dans Adobe Analytics

En raison de l'abandon des connecteurs de données Adobe Analytics, vous devrez utiliser des règles de traitement pour faire correspondre les variables contextuelles aux eVars.

En savoir plus sur [l'utilisation des règles de traitement](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html?lang=en).

Les variables de données contextuelles d'AppsFlyer sont mappées en conséquence :

* MobileAdCampaign(Context Data)
* MobileAdNetwork(Context Data)
* MobileAdProvider(Context Data)

Si vous rencontrez des problèmes lors du mappage des variables de données contextuelles d'AppsFlyer par le biais de règles de traitement, contactez l'équipe de votre compte Adobe pour obtenir de l'aide.

### Étape 4 [facultatif] : Mettre en place votre canal de commercialisation

Consultez la <Anchor target="_blank" href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-channels.html">documentation d'Adobe Analytics</Anchor> pour savoir comment configurer votre canal marketing sur leur plateforme. Veillez à sélectionner les champs suivants dans les règles d'identification :

1. « La valeur de la variable de conversion définie par la balise web d'Adobe » : Sélectionnez **AppsFlyer** et **Exists**.
2. « Identifier le canal comme » : Sélectionnez **Attribution app mobile.**
3. « Régler la valeur du canal sur » : Sélectionnez **Campagne AppsFlyer**.

## Domaine et données de sécurité

Les détails concernant le domaine et les problèmes de sécurité sont présentés ci-dessous :

1. ANALYTIC\_SERVER\_DOMAIN peut être trouvé comme variable serveur dans le fichier Config de votre app. Vous pouvez sélectionner n'importe quel domaine pour l'analyse d'attribution. En général, les domaines standard du service de collecte Adobe Analytics, tels que sc.omtrdc.net, sont utilisés. Cela se trouve dans les paramètres d'analyse (serveur) du fichier **ADBMobile.config.**
2. Le protocole (HTTP/HTTPS) de l'URL dépend de la sécurisation ou non du Domaine du Serveur ANALYTIC. Il est important d'utiliser le bon protocole. Pour savoir si le paramètre est sécurisé, vérifiez si le paramètre analytics (SSL) est défini sur **true** dans le fichier **ADBMobile.config.** Si votre connexion est sécurisée, utilisez HTTPS. Si elle ne l'est pas, utilisez HTTP.
3. L’ID DE SUITE DE RAPPORTS se trouve dans la variable **rsids** du fichier de configuration de vos apps. Vous pouvez donner n'importe quel nom à votre suite de rapports.
4. La variable ts=`{timestamp}` n'est utilisée que si votre configuration **offlineEnabled** est True dans votre fichier Config. Supprimez ce paramètre de l'URL si le paramètre **offlineEnabled** est défini sur False ou si l'**horodatage** n'est pas activé pour votre suite de rapports.

<div data-zendesk-anchors="overview=pr%C3%A9sentation h_01HA4ZWDM1MEW2VDFXYMAJ2QE2=pr%C3%A9sentation setting-up-adobe-analytics-integration=configuration-de-lint%C3%A9gration-dadobe-analytics h_01HA4ZWDM11RJ6GRJ7W8QMFACT=configuration-de-lint%C3%A9gration-dadobe-analytics prerequisite=conditions-pr%C3%A9alables h_01HA4ZWDM1YK58Q56Y0S8PC1E2=conditions-pr%C3%A9alables step-1-share-adobe-experience-cloud-id-ecid-marketing-cloud-id-or-visitor-id-with-appsflyer=%C3%A9tape1-partager-lidentifiant-adobe-experience-cloud-ecid-marketing-cloud-id-ou-visitor-id-avec-appsflyer h_01HA4ZWDM1J65D32PVXY0ZD9YV=%C3%A9tape1-partager-lidentifiant-adobe-experience-cloud-ecid-marketing-cloud-id-ou-visitor-id-avec-appsflyer h_01HA4ZWDM1RDRDGZ3X7WC0ACV1=setadditionaldata h_01HA4ZWDM1CAXZH7ZNJ0Z37EE1=setcustomeruserid h_01HA4ZWDM2VQWC36BPMPXW7DAD=setpartnerdata step-2-configure-adobe-analytics-in-appsflyer=%C3%A9tape2-configurer-adobe-analytics-dans-appsflyer h_01HA4ZWDM26AVEQKC4CXF18D22=%C3%A9tape2-configurer-adobe-analytics-dans-appsflyer h_01HA4ZWDM23A6BFXDV2JH4NR2J=remarque step-3-map-data-to-evars-in-adobe-analytics=%C3%A9tape3-cartographier-les-donn%C3%A9es-vers-les-evars-dans-adobe-analytics h_01HA4ZWDM27S52KY36GS1QPKJ5=%C3%A9tape3-cartographier-les-donn%C3%A9es-vers-les-evars-dans-adobe-analytics step-4-%5Boptional%5D-set-up-your-marketing-channel=%C3%A9tape-4-facultatif--mettre-en-place-votre-canal-de-commercialisation h_01HA4ZX6FG6RM5JNDKQP6GVAD1=%C3%A9tape-4-facultatif--mettre-en-place-votre-canal-de-commercialisation domain-and-security-details=domaine-et-donn%C3%A9es-de-s%C3%A9curit%C3%A9 h_01HA4ZWDM2NNFVPP1XYWKPS89A=domaine-et-donn%C3%A9es-de-s%C3%A9curit%C3%A9" />
