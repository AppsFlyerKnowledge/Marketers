---
title: Présentation de l'intégration SDK
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Integration
    - Advertisers
    - firetv
    - fire tv
    - Advertiser
    - Developer
    - appuid
    - anonymous
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2012-12-26T14:34:58Z'
  edited_at: '2023-11-15T13:12:03Z'
  id: 207032126
  locale: fr
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/fr/articles/207032126
---
> **En bref :** découvrez les fonctionnalités SDK proposées par AppsFlyer et choisissez les API qui seront utilisées par votre app Android ou iOS.

Cette vidéo présente ce que vous devez savoir sur l'intégration du SDK.

<Embed title="Présentation de l'intégration SDK" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/4iybquc6q3" providerUrl="https://fast.wistia.com" />

<div id="about-the-sdk" />

## À propos du SDK

Le SDK offre des fonctionnalités d'enregistrement pour les installations d'app et événements. Vous pouvez enregistrer les installations, les sessions et les événements in-app. Les événements in-app peuvent inclure, par exemple, un achat in-app ou un nouveau niveau atteint dans un jeu. Enregistrer ces événements peut vous aider à évaluer le ROI et la qualité des utilisateurs. 

Cet article présente la mise en place de l'intégration SDK V6 et +, il aide de plus les annonceurs (les propriétaires d'app) à préparer l'intégration du SDK AppsFlyer dans leur application Android ou iOS.

La documentation supplémentaire comprend les éléments suivants :

<Tabs>
<Tab title="Android natif">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk">Documentation sur l'installation du SDK à l'usage des développeurs</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-android-sdk-release-notes">Notes de mise à jour</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference">Documentation de référence sur le SDK à l'attention des développeurs</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/fill-out-google-safety-section-form">Section « Sécurité des données » sur Google Play</Anchor>

</Tab>

<Tab title="iOS natif">

* <Anchor target="_blank" href="/marketers/fr/docs/updating-to-ios-sdk-v6-and-plugins">Mise à jour vers le SDK iOS V6</Anchor>. Le SDK iOS V5.4.4 est totalement opérationnel sous iOS 14. Cependant, nous recommandons d'adopter le SDK V6.X pour assurer la compatibilité avec les futures versions d'iOS.
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">Documentation sur l'installation du SDK à l'usage des développeurs</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes">Notes de mise à jour</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference">Documentation de référence sur le SDK à l'attention des développeurs</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/preparing-for-the-app-store-review-nutrition-labels">Préparation à l'examen de l'App Store—étiquettes nutritionnelles</Anchor>

</Tab>

<Tab title="UnityReact">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">Documentation sur l'installation du SDK à l'usage des développeurs</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api">Documentation de référence sur le SDK à l'attention des développeurs</Anchor>

</Tab>

<Tab title="natif">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">Documentation sur l'installation du SDK à l'usage des développeurs</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api">Documentation de référence sur le SDK à l'attention des développeurs</Anchor>

</Tab>
</Tabs>

<div id="sdk-compatibility" />

## Compatibilité du SDK

Le SDK AppsFlyer est compatible avec les plateformes suivantes :

<Tabs>
<Tab title="Android">

* Démarrer Android V4.0
* Plateformes Android non mobile comme les Smart TV (Amazon Fire TV compris) <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">Voir la présentation CTV</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/set-up-multi-store-android-attribution">Marchés hors-store</Anchor> pour les apps Android, comme Amazon et Baidu

</Tab>

<Tab title="iOS">

* iOS 9 et + (iPhone, iPod, iPad)
* tvOS 9 et + (Apple TV)
* En conformité avec les réseaux <Anchor target="_blank" href="https://developer.apple.com/library/content/documentation/NetworkingInternetWeb/Conceptual/NetworkingOverview/UnderstandingandPreparingfortheIPv6Transition/UnderstandingandPreparingfortheIPv6Transition.html#//apple_ref/doc/uid/TP40010220-CH213-SW1">DNS64/NAT64 IPv6</Anchor> d'Apple.

Le SDK prend en charge <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model">plusieurs méthodes d'attribution</Anchor>. Les méthodes d'attribution utilisées dépendent des éléments suivants :

* La version d'iOS installée sur l'appareil de l'utilisateur
* La version du SDK iOS utilisée dans l'app

<table><thead><tr><th><span>Les méthodes d'attribution prises en charge</span></th><th><span>Version iOS</span></th><th><span>La prise en charge du SDK iOS</span></th><th><span>Remarques</span></th></tr></thead><tbody><tr><td rowspan="2"><span>Modélisation probabiliste</span></td><td><p><span>8 – 14.4</span></p></td><td>5.0.0+</td><td> </td></tr><tr><td><p><span>14.5+</span></p></td><td><span> 6.0.3+</span></td><td><span>La modélisation probabiliste peut uniquement être utilisée dans le cadre des médias propres, de la promotion croisée et des flux web-to-app consentis.</span></td></tr><tr><td rowspan="2"> <span>Correspondance d'ID</span><br/><span></span><br/> </td><td><span>8 - 13</span></td><td>5.0.0+</td><td><span>Les utilisateurs peuvent désactiver le paramètre Limit Ad Tracking (LAT).</span></td></tr><tr><td><span>14.5+</span></td><td><span>6.0.3+</span></td><td><p>La transparence du suivi des apps (ATT) ainsi que le consentement de l'utilisateur sont obligatoires. Pour en savoir plus, cf <a href="./basic-sdk-integration-guide#configure-app-tracking-transparency-att-support" target="_blank">Configurer le SDK iOS pour qu'il prenne en charge l'ATT</a>.</p></td></tr><tr><td rowspan="2"><p><a href="./skadnetwork-skan-solution-guide" target="_blank"><span>SKAdNetwork</span></a></p></td><td><p><span>11.3 - 13</span></p></td><td rowspan="2"><p><span>6.2.3</span><br/><span></span><br/></p></td><td><p>La solution SKAdNetwork (SKAN) <span>se limite à l'attribution des installations, conformément aux</span> normes spécifiques de <a href="https://developer.apple.com/documentation/storekit/skadnetwork" target="_blank">SKAN</a>, <span>les valeurs de conversion n'existent donc pas.</span></p></td></tr><tr><td><p><span>14 et +</span></p></td><td><ul><li>Est toujours disponible au niveau iOS et au niveau SDK, quel que soit le réglage ATT.</li><li>Le marketeur active SKAN dans le tableau de bord AppsFlyer.</li></ul></td></tr></tbody></table>

À partir du SDK V6.0.8, l'<Anchor target="_blank" href="/marketers/fr/docs/apple-app-clips-integration-guide">attribution des clips d'app Apple</Anchor> est disponible. Vous pouvez également lire notre <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/apple-app-clips">article de blog</Anchor> sur les clips d'app Apple.

</Tab>
</Tabs>

<div id="sdk-integration" />

## Intégration SDK

L'installation et l'intégration du SDK requièrent la collaboration du responsable produit avec le développeur.  **Avant** d'intégrer le SDK à votre app, passez en revue l'ensemble des tâches liées à l'intégration et choisissez les fonctionnalités que vous voulez voir votre application utiliser.

<div id="sdk-planning-checklist" />

### Checklist pour préparer le SDK

Pour bien commencer, nous avons créé une <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTD4OimHC93iw2AJCcAY45yAc9lOBfJe8PskI_0NFZTnWnrIq1hjPBvCztkbom9acMDDd4d1d5mMFfi/pub?output=xlsx">checklist</Anchor> qui vous guidera tout au long des étapes de préparation. Chaque opération contient des liens qui permettront au marketeur et au développeur de trouver les informations qui le concernent.

<div id="sdk-integration-tasks" />

### Étapes d'intégration du SDK

L'intégration de base du SDK comporte les étapes suivantes. Le temps de réalisation n'est donné qu'à titre indicatif.

| Opérations d'intégration de base du SDK | Temps de préparation |
| --- | --- |
| Récupérez la clé dév <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#récupérer-la-clé-dev">AppsFlyer</Anchor> et transmettez à votre développeur le lien contenant les instructions d'installation et d'intégration. | 15 min |
| Listez les différentes fonctions de l'attribution , et choisissez les identifiants d'appareil à collecter. | 30 min |
| Choisissez quels <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#enregistrer-les-événements-in-app">événements in-app</Anchor> vous souhaitez mesurer puis transmettez les noms et paramètres d'événement à votre développeur. | 1 heure |
| Choisissez les méthodes de deep linking qui seront appliquées. | 30 min |
| Déterminez les méthodes qui seront utilisées pour <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#accéder-aux-données-dattribution-et-de-deep-linking">accéder aux données d'attribution</Anchor>. | 30 min |
| Une fois l'intégration de base terminée, tout utilisateur du compte ayant accès au tableau de bord AppsFlyer peut effectuer les <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#tester-vztre-intégration-sdk">tests de base</Anchor>.<br /><br />Les développeurs peuvent utiliser les journaux de débogage dans <Anchor target="_blank" href="/marketers/fr/docs/testing-the-sdk-integration-for-marketers#testing-in-the-development-environment">l'environnement de développement</Anchor>. | 1 heure |

Vous pouvez demander à vos développeurs mobile d'implémenter dans le SDK ces différentes API facultatives.

| Opérations d'intégration complémentaire du SDK | Temps de préparation |
| --- | --- |
| Déterminez si votre app nécessite des ajustements pour une attribution complémentaire  (ex : mesure des désinstallations, attribution des installations pour les app stores tiers). | 30 min |
| Définissez les <Anchor target="_blank" href="/marketers/fr/docs/additional-sdk-integration-guide#sessions">rapports de session utilisateur</Anchor>. | 30 min |
| Déterminez quelles méthodes d'attribution seront utilisées pour les <Anchor target="_blank" href="/marketers/fr/docs/additional-sdk-integration-guide#médias-propres">sources média propriétaires</Anchor>. | 1 heure |
| Faites en sorte que les politiques de <Anchor target="_blank" href="/marketers/fr/docs/additional-sdk-integration-guide#confidentialité-des-utilisateurs">confidentialité des utilisateurs</Anchor> de votre app soient conformes aux réglementations en matière de protection de la vie privée (RGPD, CCPA). | 1 heure |

<div id="note" />

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">Aperçu des plateformes CTV, PC et consoles</Anchor>

<div data-zendesk-anchors="about-the-sdk=%C3%A0-propos-du-sdk h_01H9FHRVKE6BHGW05G6YMKF737=%C3%A0-propos-du-sdk sdk-compatibility=compatibilit%C3%A9-du-sdk h_01H9FHRVKEQ837Q0GFECNPPAN2=compatibilit%C3%A9-du-sdk sdk-integration=int%C3%A9gration-sdk h_01H9FHRVKEN0MMGTSD362FTWPS=int%C3%A9gration-sdk sdk-planning-checklist=checklist-pour-pr%C3%A9parer-le-sdk h_01H9FHRVKE468M1RTMF7VTYV1R=checklist-pour-pr%C3%A9parer-le-sdk sdk-integration-tasks=%C3%A9tapes-dint%C3%A9gration-du-sdk h_01H9FHRVKERHXY19R97EN86EGP=%C3%A9tapes-dint%C3%A9gration-du-sdk h_01H9FHRVKE88CXGH8G7E26ZXT2=%C3%A0-consulter-%C3%A9galement" />
