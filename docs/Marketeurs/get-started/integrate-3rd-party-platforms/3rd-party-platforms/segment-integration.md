---
title: Intégration de Segment
metadata:
  keywords:
    - Integration
    - segment IO
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
  created_at: '2016-06-30T07:54:38Z'
  edited_at: '2024-10-22T13:18:45Z'
  id: 210041606
  locale: fr
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/fr/articles/210041606
---
> **En bref :** Envoyez vos données d'analyse de segment à AppsFlyer.

## Introduction

Segment facilite l'envoi de vos données à AppsFlyer. Une fois que vous avez enregistré vos données à l'aide des bibliothèques open source de Segment, les données sont traduites et acheminées vers AppsFlyer dans le format approprié. AppsFlyer aide les marketeurs à affiner le ciblage, optimiser les dépenses publicitaires et augmenter le retour sur investissement.

## Intégrer Segment à AppsFlyer

Suivez <Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/">ce guide de Segment</Anchor> pour savoir comment intégrer Segment à AppsFlyer.

## FAQ

<div id="how-can-i-integrate-segment-with-appsflyer" />

<Accordion title="Comment intégrer Segment à AppsFlyer ?">

Pour intégrer Segment à AppsFlyer, suivez les étapes suivantes :

* <Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/#getting-started">Configurez votre tableau de bord Segment</Anchor> pour vous connecter à AppsFlyer
* Mettez en œuvre [le wrapper du SDK Segment](/docs/segment-integration#how-does-the-sdk-wrapper-work) dans votre application :
  * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/segment-appsflyer-ios">Native iOS</Anchor>
  * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AppsFlyer-Segment-Integration">Native Android</Anchor>

</Accordion>

<div id="what-sdks-do-i-need-to-add-to-my-app" />

<Accordion title="Quels SDK dois-je ajouter à mon application ?">

Il vous suffit d'ajouter le wrapper du SDK Segment. Lorsque vous ajoutez la dépendance du wrapper Segment SDK, le processus de compilation de l'application ajoute automatiquement le Segment SDK et le SDK AppsFlyer à votre application.

</Accordion>

<div id="how-does-the-sdk-wrapper-work" />

<Accordion title="Comment fonctionne le wrapper du SDK ?">

Le wrapper du SDK Segment relie le SDK Segment et le SDK AppsFlyer.

Lorsque vous utilisez le wrapper du SDK Segment pour appeler les méthodes de Segment pour enregistrer des installations et des événements in-app, le wrapper appelle à la fois les méthodes de Segment et celles d'AppsFlyer.

Cela vous fait gagner du temps et des efforts, tout en réduisant la quantité de code nécessaire.

> ❗️ **Avertissement**
>
> Attention - **N'UTILISEZ PAS** simultanément les méthodes du wrapper du SDK Segment et du SDK AppsFlyer. Cela pourrait entraîner des erreurs et des divergences de données.
>
> **N'utilisez que les méthodes du wrapper du SDK Segment.**

</Accordion>

<div id="is-there-any-difference-in-functionality-between-the-segment-sdk-wrapper-and-the-appsflyer-sdk" />

<Accordion title="Existe-t-il une différence de fonctionnalité entre le wrapper du SDK Segment et le SDK AppsFlyer ?">

Non, il n'y a pas de changement de fonctionnalité. Toutes les fonctions du SDK AppsFlyer sont disponibles dans le wrapper du SDK Segment.

</Accordion>

<div id="i-dont-see-inapp-event-data-in-the-appsflyer-dashboard" />

<Accordion title="Je ne vois pas de données sur les événements in-app dans le tableau de bord d'AppsFlyer.">

* Assurez-vous de suivre les instructions pour mettre en œuvre la méthode de suivi dans le wrapper du SDK Segment :
  * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AppsFlyer-Segment-Integration#adding_events">Android</Anchor>
  * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/segment-appsflyer-ios/blob/master/examples/SwiftPodsSample/SwiftPodsSample/ViewController.swift">iOS</Anchor>
* Veillez à <Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/#getting-started">spécifier votre clé de développement</Anchor> lors de l'intégration d'AppsFlyer dans le tableau de bord de Segment.

</Accordion>

<div id="install-and-inapp-events-data-in-segment-and-appsflyer-doesnt-match" />

<Accordion title="Les données d'installation et d'événements in-app dans Segment et AppsFlyer ne correspondent pas">

Assurez-vous d'utiliser uniquement le wrapper du SDK Segment. Ne combinez pas le wrapper SDK Segment avec le SDK AppsFlyer. Voir [ici](/docs/segment-integration#how-does-the-sdk-wrapper-work) pour plus d'informations.

[La FAQ ci-dessus](/docs/segment-integration#i-dont-see-inapp-event-data-in-the-appsflyer-dashboard) précise également les raisons pour lesquelles les données peuvent ne pas être alignées entre Segment et AppsFlyer.

</Accordion>

<div id="im-getting-a-validation-error-when-testing-events-in-segment" />

<Accordion title="J'obtiens une erreur de validation lorsque je teste des événements dans Segment">

Lorsque vous testez des événements à l'aide du***testeur d'événements*** dans la fenêtre ***Destination,*** il se peut que vous obteniez une erreur : ***Erreur de validation L'identifiant de l'appareil AppsFlyer (integrations.AppsFlyer.appsFlyerId) est nécessaire pour envoyer des événements de serveur à serveur.***.

Cette erreur ne signifie pas qu'il y a un problème d'intégration entre Segment et AppsFlyer. Le testeur d'événements vous permet de tester l'envoi de données de serveur à serveur de Segment à AppsFlyer. Tout événement envoyé de serveur à serveur nécessite l'AppsFlyerID, c'est pourquoi le testeur d'événements génère une erreur.

Toutefois, cela ne concerne que les événements entre serveurs. Lorsque vous utilisez l'API du SDK Segment pour enregistrer des événements, ceux-ci sont envoyés à la fois à Segment et AppsFlyer. Pour l'appel API d'AppsFlyer, l'ID de l'appareil AppsFlyer est inclus.

</Accordion>

<div id="im-using-a-thirdparty-analytics-tool-should-i-integrate-it-with-both-appsflyer-and-segment" />

<Accordion title="J'utilise un outil d'analyse tiers. Dois-je l'intégrer à la fois à AppsFlyer et à Segment ?">

Non, vous devez utiliser le tableau de bord Segment uniquement pour activer les outils d'analyse tiers.

</Accordion>

<div data-zendesk-anchors="integrating-segment-with-appsflyer=int%C3%A9grer-segment-%C3%A0-appsflyer faqs=faq" />
