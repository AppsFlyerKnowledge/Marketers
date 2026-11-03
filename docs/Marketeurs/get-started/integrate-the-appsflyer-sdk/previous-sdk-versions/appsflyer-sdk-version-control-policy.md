---
title: Politique de contrôle des versions du SDK AppsFlyer
metadata:
  keywords:
    - iOS
    - Android
    - SDK
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
  created_at: '2021-11-30T10:43:19Z'
  edited_at: '2023-11-12T12:53:04Z'
  id: 4412316953105
  locale: fr
  section: Previous SDK versions
  section_id: 6551300280977
  url: https://support.appsflyer.com/hc/fr/articles/4412316953105
---
> **En bref :** découvrez les règles de contrôle des différentes versions du SDK AppsFlyer, ainsi que celles que nous continuons à utiliser.

## À propos des versions

Au fil des ans, AppsFlyer a publié de nombreuses versions du SDK. Chaque version du SDK correspond à une version de l'API. L'objectif de la politique de contrôle des différentes versions du SDK est de définir la durée pendant laquelle chaque API repose sur l'une de ces versions.

## Pourquoi faire un contrôle des versions ?

L'objectif du contrôle des versions est le suivant :

* Il permet de savoir à l'avance quand une API sera supprimée pour certaines versions du SDK intégrées à vos apps.C'est important car adopter une nouvelle version prend du temps, ce qui signifie qu'il peut s'écouler une certaine période avant que vos utilisateurs ne passent à la version la plus récente de votre application.
* Améliorer la stabilité (la rétrocompatibilité est de 2 ans et demi), ce qui élimine les éventuelles erreurs lors de l'utilisation de versions du SDK très datées.
* Vous pouvez profiter des nouvelles fonctionnalités qui requièrent les mises à jour du SDK.

## Cycles de vie des versions du SDK

La durée de vie d'une version d'API est garantie pour 2 ans et demi. Chaque fois qu'une nouvelle version (majeure ou mineure) du SDK est publiée, AppsFlyer fixe une date d'expiration pour la version mineure en cours (avec tous ses patchs correctifs).

## Que se passe-t-il lorsqu'une version du SDK disparaît ?

Une fois qu'une version du SDK est devenue obsolète, les serveurs d'AppsFlyer ne mesurent plus ses installations, sessions et événements in-app. Les événements qui atteignent ces points de terminaisons sont tout simplement refusés.

Comme l'adoption d'une nouvelle version prend du temps, nous **recommandons fortement** à votre développeur d'anticiper les choses et de passer à la dernière version du SDK bien avant la date d'expiration.

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-android-sdk-release-notes">Notes de publication du SDK Android AppsFlyer</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-ios-sdk-release-notes">Notes de mise à jour du SDK iOS d'AppsFlyer</Anchor>

<div data-zendesk-anchors="about-versioning=%C3%A0-propos-des-versions h_01HE7RHYC4YGZWF9EKK96RPMAN=%C3%A0-propos-des-versions why-do-we-need-version-control=pourquoi-faire-un-contr%C3%B4le-des-versions- h_01HE7RHYC4QSVTA4ZCHTKYQSAT=pourquoi-faire-un-contr%C3%B4le-des-versions- sdk-version-lifecycles=cycles-de-vie-des-versions-du-sdk h_01HE7RHYC41QN657ZTEQ0P45GD=cycles-de-vie-des-versions-du-sdk what-happens-when-an-sdk-version-is-sunset=que-se-passe-t-il-lorsquune-version-du-sdk-dispara%C3%AEt- h_01HE7RHYC4EVSNA2F4DQ1594DH=que-se-passe-t-il-lorsquune-version-du-sdk-dispara%C3%AEt- h_01HE7RPQBD858TQSF27NFGGP43=%C3%A0-consulter-%C3%A9galement" />
