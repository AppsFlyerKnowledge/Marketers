---
title: Guide de configuration de X Ads (anciennement Twitter Ads) - Aperçu
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:31:36Z'
  edited_at: '2023-11-24T14:12:15Z'
  id: 4410464316049
  locale: fr
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/fr/articles/4410464316049
---
> **En bref :** découvrez l'historique de l'intégration de votre compte X Ads avec AppsFlyer.

<Image alt="X Ads logo.png" src="https://files.readme.io/cecae90650321943ad1cb6d22b7f27d3d28b0484f1706cb1be1a19099dfbb20d-20375448207377.png" width="167px" />

## Promotion d'apps mobile sur X Ads

X Ads Mobile App Promotion est une méthode permettant de promouvoir les apps sur X Ads. Elle permet aux annonceurs de promouvoir leurs applications mobile avec un excellent design de carte d'app qui booste les installations, les engagements des applications et le deep linking. Les utilisateurs d'app peuvent facilement installer et s'engager dans les applications directement depuis le fil d'actualités de X Ads.

## Confidentialité des utilisateurs sur X Ads

Les utilisateurs de X Ads peuvent décider comment leurs informations sont partagées avec les annonceurs :

* Si les paramètres des utilisateurs sont réglés de manière à empêcher le partage de leurs informations d'engagement avec les annonceurs, leurs installations et événements in-app pilotés par X Ads sont retirés des données brutes mais sont toujours attribués à X Ads.
* Les données d'attribution agrégées se reflètent correctement dans AppsFlyer et ne sont pas affectées par la politique de X Ads.
* Par conséquent, les rapports de données agrégées et brutes de X Ads ne sont pas corrélés.

Depuis le 31 juillet 2021, les annonceurs qui ne participent pas au programme X Ads Advanced Mobile Measurement (AMM) cessent de recevoir toutes les données de niveau utilisateur X Ads MACT.

Avec le programme AMM, les annonceurs ont la possibilité de recevoir des données de niveau utilisateur plus importantes s'ils accordent à X Ads le droit d'effectuer un audit visant à vérifier que les données X Ads sont utilisées à des fins de mesure exclusivement. Ce contrat se conforme à la législation en matière de protection des données ainsi qu'aux pratiques générales du secteur.  
**Pour rejoindre le programme AMM :** rendez-vous sur ads.twitter.com/help > **App Mobile, Suivi des conversions et gestionnaire d'audiences,** puis sélectionnez **Formulaire d'accès au programme Advanced Mobile Measurement (AMM)**.

Notez que les données de niveau utilisateur qui ont été reçues avant de rejoindre le programme AMM ne peuvent pas être exportées.

Pour de plus amples informations, contactez votre responsable de compte X Ads.

## Interaction entre X Ads et AppsFlyer SKAN

X Ads envoie les données de postback SKAdNetwork via une API dédiée. Les données SKAN issues de X Ads s'afficheront dans le <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">tableau de bord SKAN</Anchor>.

X Ads enrichit les postbacks SKAN en y ajoutant les champs de données suivants :

* Nom de la campagne
* Identifiant de la campagne
* Nom d'adset
* Identifiant de l'ensemble de publicités

<div data-zendesk-anchors="mobile-app-promotion-on-twitter=promotion-dapps-mobile-sur-x-ads h_01H9QR6TH7M0H5YMXRWVVAYRK9=promotion-dapps-mobile-sur-x-ads twitter-user-privacy=confidentialit%C3%A9-des-utilisateurs-sur-x-ads h_01H9QR6TH74R50K00H7FYN61KC=confidentialit%C3%A9-des-utilisateurs-sur-x-ads twitter-ads-and-appsflyer-skan-interoperation=interaction-entre-x-ads-et-appsflyer-skan h_01H9QR6TH74PKBGM5RC4M118GE=interaction-entre-x-ads-et-appsflyer-skan" />
