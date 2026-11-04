---
title: Manifeste sur la confidentialité
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
  created_at: '2024-01-15T10:17:30Z'
  edited_at: '2024-07-01T11:08:37Z'
  id: 21677433322641
  locale: fr
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/fr/articles/21677433322641
---
> **En bref :** Lors de la WWDC23, Apple a présenté de nouveaux manifestes concernant la confidentialité. Grâce aux manifestes sur la confidentialité, les développeurs d'apps peuvent maintenant fournir des informations plus détaillées sur la manière dont leurs apps gèrent la confidentialité. AppsFlyer a créé un manifeste sur la confidentialité pour le SDK AppsFlyer, dont vous trouverez les éléments ci-dessous.

<div id="background" />

## Arrière-plan

Grâce aux manifestes sur la confidentialité, un développeur d'app pourra créer un registre avec les catégories de données collectées par son app, ou par des services tiers (comme les SDK tiers utilisés par l'app). Ces éléments aident les développeurs d'apps à communiquer sur les pratiques de leurs apps en termes de protection de la vie privée, ce qui inclut les étiquettes nutritionnelles proposées aux utilisateurs.

Dans de nombreux cas, les développeurs d'apps ne savent pas quelles données les SDK tiers collectent, ni comment ces données sont utilisées par les SDK. Le manifeste sur la confidentialité permet aux SDK tiers de bien transmettre ces informations aux développeurs d'apps, afin qu’ils puissent ensuite à créer des étiquettes nutritionnelles exactes.

<div id="what-are-nutrition-labels" />

### Qu'est-ce qu’une étiquette nutritionnelle ?

Les étiquettes nutritionnelles expliquent dans un langage simple et précis ce qu’un utilisateur doit attendre d’une app en matière de confidentialité. Les utilisateurs finaux ont accès à plus d’informations sur les données collectées par l'app, et sur la manière dont elles sont utilisées. Pour plus d'informations sur les étiquettes nutritionnelles, cf <Anchor target="_blank" href="/marketers/fr/docs/preparing-for-the-app-store-review-nutrition-labels">cet article</Anchor>.

<div id="what-is-in-the-appsflyer-privacy-manifest" />

## Que contient le manifeste sur la confidentialité AppsFlyer ?

<div id="important" />

> 🚧 **Important !**
>
> En plus du SDK AppsFlyer, vous devrez déterminer votre propre collecte de données, l'API Required Reason ainsi que l'utilisation dans votre app ou dans différents SDK, et enfin faire apparaître ces informations dans l'étiquette nutritionnelle.

AppsFlyer SDK 6.14.0 inclut le manifeste sur la confidentialité AppsFlyer. Ce qui veut dire :

* [L’utilisation des données](#lutilisation-des-données)
* [Les API Required Reason](#les-api-required-reason)
* [Le suivi des domaines](#suivi-des-domaines)

<div id="data-usage" />

### L’utilisation des données

Apple demande aux développeurs d'apps et de SDK d'enregistrer la catégorie des données, ainsi que les motifs pour lesquels l'app ou le SDK tiers collecte ces mêmes données.

Les développeurs d'apps peuvent ensuite utiliser Xcode pour créer un rapport de confidentialité, qui vient résumer toutes les infos sur les données collectées.

Voici les types de données collectées par le SDK AppsFlyer, qui sont inclus dans le Manifeste sur la confidentialité :

<div id="note" />

> 📘 **Remarque**
>
> Le contenu ci-dessous se base sur les réglages par défaut du logiciel AppsFlyer. Les développeurs doivent veiller à adapter leur manifeste à leurs propres configurations et à la manière dont ils utilisent le SDK AppsFlyer.

| Nom | NSPrivacyCollectedDataType | NSPrivacyCollectedDataTypeLinked | NSPrivacyCollectedDataTypeTracking | NSPrivacyCollectedDataTypePurposes |
| --- | --- | --- | --- | --- |
| ID d'appareil (IDFA, IDFV) | NSPrivacyCollectedDataTypeDeviceID | Oui | Oui | NSPrivacyCollectedDataTypePurposeThirdPartyAdvertising |
| Interaction avec les produits (lancements) | NSPrivacyCollectedDataTypeProductInteraction | Non | Non | NSPrivacyCollectedDataTypePurposeAnalytics |

<div id="required-reason-apis" />

### Les API Required Reason

Apple a sorti la liste des API dont l'utilisation est assujettie à une raison. Les apps et les SDK qui utilisent ces API doivent les détailler dans la section API Required Reason du manifeste sur la confidentialité. Ces API sont regroupées par catégories selon leur fonctionnalité et les informations qu'elles fournissent, conformément à la<Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api?language=objc">liste des sujets Apple</Anchor>. Il s'agit des API incluses dans le manifeste sur la confidentialité pour la version 6.14.0 du SDK AppsFlyer :

* <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">Les API d'horodatage des fichiers</Anchor>
* <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">Les API utilisateur par défaut (UserDefault)</Anchor>

Pour clarifier l'utilisation des API Required Reason, les développeurs d'apps devront déclarer la catégorie de l’API et préciser les raisons pour lesquelles ils l’utilisent. Vous trouverez indiquées ci-dessous les API AppsFlyer, ainsi que leur utilisation.

<div id="sdk-version-6140-and-above" />

<Accordion title="SDK version 6.14.0 et +">

| Catégorie de l’API | Type de catégorie de l’API | Raison | Commentaires |
| --- | --- | --- | --- |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">Les API d'horodatage des fichiers</Anchor> | NSPrivacyAccessedAPICategoryFileTimestamp | C617.1 | Le SDK utilise les API <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilecreationdate?language=objc">NSFileCreationDate</Anchor> et <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilemodificationdate?language=objc">NSFileModificationDate</Anchor> pour déterminer la date d'installation ainsi que la date de mise à jour de l'app. |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">Les API utilisateur par défaut (UserDefault)</Anchor> | NSPrivacyAccessedAPICategoryUserDefaults | CA92.1 | Le SDK stocke les données dont il a besoin pour fonctionner. Par exemple, le nombre de fois où l'application a été lancée. |

</Accordion>

<div id="sdk-versions-6130-and-earlier" />

<Accordion title="SDK versions 6.13.x et -">

| Catégorie de l’API | Type de catégorie de l’API | Raison | Commentaires |
| --- | --- | --- | --- |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">Les API d'horodatage des fichiers</Anchor> | NSPrivacyAccessedAPICategoryFileTimestamp | C617.1 | Le SDK utilise les API <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilecreationdate?language=objc">NSFileCreationDate</Anchor> et <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilemodificationdate?language=objc">NSFileModificationDate</Anchor> pour déterminer la date d'installation ainsi que la date de mise à jour de l'app. |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278394">API de boot du système</Anchor> | NSPrivacyAccessedAPICategorySystemBootTime | 35F9.1 | Permet de mesurer les performances du SDK (temps d'exécution d'une requête, etc.) |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">Les API utilisateur par défaut (UserDefault)</Anchor> | NSPrivacyAccessedAPICategoryUserDefaults | CA92.1 | Le SDK stocke les données dont il a besoin pour fonctionner. Par exemple, le nombre de fois où l'application a été lancée. |

Pour gagner du temps, vous pouvez copier l'extrait de code suivant, qui inclut les Required Reasons précédentes, et le coller dans votre fichier PrivacyInfo.xcprivacy.

```xml
<key>NSPrivacyAccessedAPITypes</key>
<array>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>CA92.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategoryUserDefaults</string>
    </dict>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>C617.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategoryFileTimestamp</string>
    </dict>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>35F9.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategorySystemBootTime</string>
    </dict>
</array>
```

</Accordion>

<div id="tracking-domains" />

### Suivi des domaines

Tout suivi de domaine utilisé dans une app ou un SDK tiers doit obligatoirement être enregistré dans le manifeste sur la confidentialité. Si les utilisateurs ne donnent pas leur accord (opt-out) via ATT (App Tracking Transparency), le système d'exploitation iOS bloque tout trafic qui sort vers ce domaine. Le SDK AppsFlyer vérifie le statut ATT de l'utilisateur avant toute requête du serveur, il exécute ensuite la requête en fonction de l’accord (ou du refus) de l'utilisateur.

## FAQ

<div id="do-i-have-to-update-my-appsflyer-sdk" />

<Accordion title="AppsFlyer dispose-t-il d'un SDK qui prend en charge le Manifeste sur la confidentialité ?">

Oui, à partir de la version 6.14.0, le SDK prend entièrement en charge le manifeste sur la confidentialité.

</Accordion>

<div id="do-i-have-to-report-my-own-data-collection" />

<Accordion title="Dois-je déclarer ma propre collecte de données ?">

Oui, en plus des SDK AppsFlyer ou autres, vous devrez déterminer votre propre collecte ainsi que l’utilisation des données, puis indiquer ces éléments dans l'étiquette nutritionnelle, ce qui comprend tout changement apporté aux réglages par défaut du SDK AppsFlyer (ex : la mesure des événements in-app).

</Accordion>

<div data-zendesk-anchors="background=arri%C3%A8re-plan h_01HCY4D9EKHYB5B3YNWRCB53F4=arri%C3%A8re-plan what-are-nutrition-labels=quest-ce-quune-%C3%A9tiquette-nutritionnelle- h_01HCY4ZASEAR69RT3YMHMSE4NP=quest-ce-quune-%C3%A9tiquette-nutritionnelle- what-to-consider-when-getting-your-app-ready-to-ios17=que-contient-le-manifeste-sur-la-confidentialit%C3%A9-appsflyer- h_01HCY4D9EKTKB50BSZD7RBMMYB=que-contient-le-manifeste-sur-la-confidentialit%C3%A9-appsflyer- h_01HQ5C9WGW669HBWSG4WQMJTGP=important- data-usage=lutilisation-des-donn%C3%A9es h_01HQ03P71BG159MCE3VQY4GTMH=lutilisation-des-donn%C3%A9es h_01HT9QHRQSKDQ8GR17N7X5QB8N=remarque required-reason-apis=les-api-required-reason h_01HQ03NV880VHFTXQDE8R6ZRZH=les-api-required-reason h_01HSZSWW6Y91BTY1GNXMMVJCEQ=sdk-version-6140-and-above h_01HT9QVD9KZVN7RXWP03XCH8JZ=sdk-versions-6130-and-earlier required-reasons-api=suivi-des-domaines h_01HQ03NV88SJPYKBM66S7X6GP8=suivi-des-domaines 01HQQXSN96D4QTTYHG8CBE8695=faq h_01HCY5XRA96XAYYGB4XCZ8EXXG=do-i-have-to-update-my-appsflyer-sdk h_01HDDQV25KC9XWF7CJ7QBH4XW2=do-i-have-to-report-my-own-data-collection" />
