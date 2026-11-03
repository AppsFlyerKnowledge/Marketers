---
title: FAQ générales sur l'intégration du SDK
metadata:
  keywords:
    - Advertisers
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
  created_at: '2015-01-18T11:13:24Z'
  edited_at: '2024-09-20T13:46:30Z'
  id: 207033546
  locale: fr
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/fr/articles/207033546
---
> **En bref:** Le SDK AppsFlyer vous permet de promouvoir en toute sécurité votre application, d'attribuer, de créer des liens profonds et de collecter des informations comportementales sur vos utilisateurs mobiles. Vous pouvez configurer et commencer à travailler avec n'importe quel réseau publicitaire et/ou plateforme en quelques minutes, et non en semaines ou en mois !

## Est-il obligatoire d'intégrer le SDK AppsFlyer?

Le SDK AppsFlyer vous permet de collecter tous les événements pertinents de pré-installation et de post-installation effectués par les utilisateurs de votre application. Sans ces données, l'attribution, les liens profonds et la collecte d'événements dans l'application ne sont pas possibles.

Bien que la communication <Anchor target="_blank" href="/marketers/fr/docs/server-to-server-events-api-for-mobile-s2s-mobile">de serveur à serveur</Anchor> avec AppsFlyer soit possible, intégrer le SDK (et le mettre à jour périodiquement) est la **méthode recommandée car le SDK garantit une communication à jour et sécurisée** entre l'application et les serveurs AppsFlyer.

## Comment installer et mettre à jour le SDK AppsFlyer?

Pour savoir comment installer et mettre à jour le SDK AppsFlyer, veuillez consulter le <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">Dev Hub</Anchor>. **Remarque**: La mise à niveau du SDK implique la publication d'une nouvelle version de votre application sur les magasins.

## Est-il difficile d'intégrer le SDK AppsFlyer?

En moins d'une heure, un développeur expérimenté peut préparer des applications pour l'attribution avec AppsFlyer. Ensuite, il ne lui faut que  quelques minutes par application.

Consultez les guides d'intégration du SDK AppsFlyer pour <Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">Android</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">iOS</Anchor>, Unity ou ces <Anchor target="_blank" href="/marketers/fr/docs/other-platforms">autres plateformes</Anchor>.

## Le SDK AppsFlyer affecte-t-il le temps de téléchargement d'une application?

Les packages SDK AppsFlyer sont conçus et codés pour avoir un impact *quasi nul* sur les performances des applications. Toutes les versions du SDK sont légères et occupent généralement moins de 1% de la taille d'une application. En d'autres termes, **l'impact sur le temps global de téléchargement de l'application est marginal**.

* **SDK Android:** ~300Ko
* **SDK iOS:** ~3,4Mo

## Le SDK AppsFlyer affecte-t-il les performances des applications?

Les API du SDK AppsFlyer sont principalement des méthodes *setter* / *getter* ou des services web asynchrones rapides qui envoient/reçoivent des données des serveurs AppsFlyer. Cela signifie que les API du SDK ont un effet négligeable sur les performances des applications.

En d'autres termes, **le SDK** **AppsFlyer n'a aucun effet sur les performances de l'application ou sur l'expérience utilisateur**.

## Puis-je enregistrer des événements intégrés à l'application qui se produisent en dehors de mon application?

Vous pouvez utiliser l'<Anchor target="_blank" href="/marketers/fr/docs/server-to-server-events-api-for-mobile-s2s-mobile">API S2S pour signaler des événements</Anchor> qui se produisent en dehors de l'application ; par exemple, lorsqu'un utilisateur renouvelle son abonnement via votre interface web. Les événements S2S, une fois enregistrés, sont disponibles sur toute la plateforme, y compris les tableaux de bord, les données brutes et les analyses.

<div data-zendesk-anchors="is-it-mandatory-to-integrate-the-appsflyer-sdk=est-il-obligatoire-dint%C3%A9grer-le-sdk-appsflyer h_01HMTWWE6EQ4EF0SMJM0Q8V7KB=est-il-obligatoire-dint%C3%A9grer-le-sdk-appsflyer how-to-install-and-update-the-appsflyer-sdk=comment-installer-et-mettre-%C3%A0-jour-le-sdk-appsflyer h_01HSXBYM9WMD9CDX03RFHM0JY1=comment-installer-et-mettre-%C3%A0-jour-le-sdk-appsflyer is-it-hard-to-integrate-the-appsflyer-sdk=est-il-difficile-dint%C3%A9grer-le-sdk-appsflyer h_01HMTWQHQRGE6Z2BM1BBQY04H1=est-il-difficile-dint%C3%A9grer-le-sdk-appsflyer does-the-appsflyer-sdk-affect-app-download-time=le-sdk-appsflyer-affecte-t-il-le-temps-de-t%C3%A9l%C3%A9chargement-dune-application h_01HMTWQHQRQQ47CAJCA4Y0AASZ=le-sdk-appsflyer-affecte-t-il-le-temps-de-t%C3%A9l%C3%A9chargement-dune-application does-the-appsflyer-sdk-affect-app-performance=le-sdk-appsflyer-affecte-t-il-les-performances-des-applications h_01HMTWQHQRXBPQN75J0KM48AJ2=le-sdk-appsflyer-affecte-t-il-les-performances-des-applications can-i-record-inapp-events-that-occur-outside-my-app=puis-je-enregistrer-des-%C3%A9v%C3%A9nements-int%C3%A9gr%C3%A9s-%C3%A0-lapplication-qui-se-produisent-en-dehors-de-mon-application h_01HMTWQHQSP646Y8KVZSBA01TF=puis-je-enregistrer-des-%C3%A9v%C3%A9nements-int%C3%A9gr%C3%A9s-%C3%A0-lapplication-qui-se-produisent-en-dehors-de-mon-application" />
