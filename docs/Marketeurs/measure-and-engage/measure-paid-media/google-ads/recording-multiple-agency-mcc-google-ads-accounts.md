---
title: Enregistrement de plusieurs comptes Google Ads agence/MCC
metadata:
  keywords:
    - Advertisers
    - Multiple Agencies
    - MCC
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2017-09-28T11:11:04Z'
  edited_at: '2024-10-09T13:54:27Z'
  id: 115004970386
  locale: fr
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/fr/articles/115004970386
---
> **En bref :** Configurez l'enregistrement pour différents comptes Google Ads afin que le trafic soit correctement attribué.

## Introduction

Le trafic Google Ads provient souvent de divers comptes, tels que des agences spécialisées dans Google Ads ou même différentes équipes locales au sein de l'organisation du propriétaire de l'application. Il est crucial de savoir comment configurer les enregistrements pour différents comptes Google Ads afin que l'attribution bénéficie aux bonnes parties.

Cet article aborde ces cas, allant des mesures prises par les agences à l'utilisation des MCC et même des MCC de MCC.

> 📘 **Remarque**
>
> Ce qui suit s'applique **uniquement** aux clients utilisant la nouvelle API Google Ads.

Pour plus de détails sur la configuration du compte agence sur Google Ads, <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-agencies">cliquez ici</Anchor>.

## Définitions importantes

* **ID de lien** – **un** **identifiant unique d'une application mobile défini sur Google Ads**.

> 📘 **Remarque**
>
> Les versions Android et iOS de la même application nécessitent des identifiants de lien distincts.

* **ID client** – **identifiant unique d'un compte Google Ads**.  
  Chaque compte peut promouvoir plusieurs identifiants de lien, par exemple pour toutes les applications de l'entreprise. Lorsque vous liez des comptes agence à des applications existantes sur le tableau de bord d'AppsFlyer, vous pouvez définir jusqu'à 10 identifiants client.
* **MCC** - Un compte gestionnaire Google Ads (MCC, anciennement appelé Centre Mes clients) est un **outil pour gérer plusieurs comptes Google Ads**.  
  Avec un compte MCC, vous pouvez lier plusieurs comptes afin de les consulter en un seul endroit (<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6139186?hl=en&ref_topic=7554904">En savoir plus</Anchor>).

## Configuration de l'enregistrement Google Ads

AppsFlyer peut enregistrer un seul ID de lien par application. **Lorsque plusieurs comptes gèrent la même application, ils doivent tous utiliser le même ID de lien.** Cette configuration doit être faite sur le tableau de bord d'AppsFlyer pour des fins d'attribution.

### Partage de l'ID de lien Google avec un autre compte

Les propriétaires d'applications disposant d'un seul compte Google Ads, ou envisageant de travailler avec des agences gérant le trafic Google Ads, doivent utiliser la méthode suivante.

Le propriétaire de l'application peut partager n'importe quel ID de lien avec un autre compte, identifié par son ID client, comme le montre la capture ci-dessous. Voici quelques détails supplémentaires sur le <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-agencies#setting-up-google-ads-attribution-for-agencies">partage de l'ID de lien avec une agence</Anchor>.

> 🚧 **Important**
>
> * Si le MCC est le gestionnaire d'enregistrement pour les sous-comptes, il n'est pas nécessaire de partager l'ID de lien du MCC aux sous-comptes. Cependant, si un sous-compte sous le MCC est son propre gestionnaire d'enregistrement, le MCC doit partager l'ID de lien avec le gestionnaire d'enregistrement du sous-compte.
> * Importation des conversions : Si le MCC est le gestionnaire d'enregistrement, il est responsable de l'importation des conversions pour les sous-comptes qu'il gère. Cependant, si un sous-compte sous le MCC est son propre gestionnaire d'enregistrement, ce sous-compte doit également importer les conversions.

> 📘 **Remarque**
>
> * Dans le tableau de bord Google Ads, cliquez sur (3 points) >> ***Comptes associés*** >> ***Détails des applications tierces***
> * L'autre compte doit approuver le « partage ».
> * Ainsi, l'autre compte est autorisé à lancer des campagnes Google Ads pour l'application.

> 👍 **Astuce**
>
> AppsFlyer recommande de partager l'ID de lien depuis le compte principal de l'annonceur vers les autres comptes, plutôt que de générer directement des ID de lien dans ces comptes. C'est l'option la plus rapide et elle permet aussi une séparation aisée entre l'annonceur et les agences une fois le travail mutuel terminé.

## MCC

Les agences ou grands annonceurs qui gèrent plusieurs comptes Google Ads utilisent souvent un MCC (My Client Center), qui permet de visualiser tous leurs comptes en un seul endroit.

Lors de la configuration du MCC, il est possible de définir si le MCC ou les sous-comptes gèrent les conversions.

[altMCC\_1\_nouveau.pngalt](https://files.readme.io/3320465f5def5f3da9afdb028577e49cdbf0b5b9ddf2f04ce708b8a31c5d9cc3-360001513758.png)

Cette configuration peut être modifiée par la suite si nécessaire.

![paramètres-mmc-googleads.png](https://files.readme.io/d0f0ffda25f88d5a37c8466818170243ed9f0040b3a3ad03e860d9a92bf59d4d-11240341292049.png)

## MCC de MCCs

Les grands annonceurs travaillant avec plusieurs agences peuvent utiliser un compte MCC de MCCs. C'est similaire au compte MCC standard. Il est recommandé que le MCC de niveau le plus élevé ou l'annonceur soit celui qui génère l'identifiant de lien. La bonne configuration de cette structure nécessite que les sous-comptes sélectionnent le niveau approprié de MCC (probablement le niveau le plus élevé) comme gestionnaire d'enregistrement. Si c'est cette configuration qui est utilisée, alors l'identifiant de lien n'a pas besoin d'être partagé avec les sous-comptes et les conversions importées au niveau le plus élevé sont suffisantes.

> 👍 **Astuce**
>
> Pour plus d'informations sur les MCC et les hiérarchies de comptes, consultez les liens ci-dessous :
>
> * <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7456530">Associer des comptes à votre gestionnaire de compte</Anchor>
> * <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7519925?hl=en&ref_topic=7554359">Voir la hiérarchie de votre compte gestionnaire</Anchor>
> * <Anchor target="_blank" href="https://support.google.com/google-ads/topic/7554359?hl=en&ref_topic=6031997">Travailler avec des comptes gérés</Anchor>
>
> Pour toute question concernant les structures de compte et les recommandations, consultez votre représentant Google.

## Ouverture d'une campagne Google Ads

Un MCC ne peut pas ouvrir directement une campagne Google Ads. Ceci doit être fait via un sous-compte Google Ads standard.

Il existe deux options pour l'enregistrement des conversions :

1. **MCC gère l'enregistrement des sous-comptes**  
   Courant lorsque différentes équipes travaillent au sein de la même entreprise, par exemple, **un compte Google Ads par région géographique dans la même entreprise**.  
   Le MCC détient la configuration d'enregistrement pour tous ses sous-comptes. Toute modification de la configuration d'enregistrement est effectuée uniquement au niveau du MCC et tous les sous-comptes en héritent automatiquement.  
   Le MCC doit également importer les conversions, ce qui est fait une fois et couvre tous les sous-comptes, et aussi obtenir les identifiants de lien à partager avec les sous-comptes.
2. **Les sous-comptes gèrent leur propre enregistrement**  
   Commun pour les comptes qui ne sont pas connectés, sauf par une seule entité qui les sert, par exemple, **une agence qui sert différents comptes d'annonceurs clients**.  
   L'importation des conversions, dans ce cas, doit être effectuée séparément pour chaque sous-compte. AppsFlyer enregistre un seul ID de lien par application, donc, pour l'enregistrement sur mobile, le MCC ou l'annonceur doit partager l'ID de lien avec les sous-comptes.

Les conversions sur Google Ads peuvent être importées UNIQUEMENT après que la première instance de toute conversion se produise, qu'il s'agisse d'une installation ou d'un événement in-app.

<div data-zendesk-anchors="important-definitions=d%C3%A9finitions-importantes setting-up-google-ads-recording=configuration-de-lenregistrement-google-ads sharing-google-link-id-with-another-account=partage-de-lid-de-lien-google-avec-un-autre-compte mcc-of-mccs=mcc-de-mccs opening-a-google-ads-campaign=ouverture-dune-campagne-google-ads" />
