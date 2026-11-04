---
title: 'Google Ads (AdWords) : réengagement'
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
  created_at: '2022-01-20T09:55:51Z'
  edited_at: '2023-10-27T11:12:34Z'
  id: 4417296925073
  locale: fr
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/fr/articles/4417296925073
---
> **En bref :** pour mesurer les campagnes de retargeting Google Ads.

<div id="google-ads-retargeting-campaigns" />

## Campagnes de reciblage Google Ads

AppsFlyer vous permet de mesurer les résultats des **campagnes Google Ads pour l'engagement**.  
Dans AppsFlyer, ces campagnes sont appelées campagnes de retargeting. AppsFlyer prend en charge l'obtention des données relatives aux coûts, aux clics et aux impressions pour les campagnes de retargeting. Cette intégration vous permet d'afficher et de mesurer vos dépenses publicitaires sur Google Ads, puis de calculer l'eCPI et le ROI de vos campagnes Google Ads.

Les campagnes de reciblage ciblent les utilisateurs ayant déjà installé votre application.

* Les engagements de reciblage par les utilisateurs chez qui votre application est installée sont appelés **réengagement**. Ils génèrent généralement des interactions de deep linking.
* Les engagements de reciblage par les utilisateurs qui n'ont pas installé votre application sont appelés **Réinstallations** ou **Réattributions**.

Pour plus d'informations, consultez la <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">documentation d'utilisation de Google Ads pour l'engagement</Anchor>.

<div id="setting-up-google-ads-app-campaigns-for-engagement" />

## Configuration des campagnes d'apps Google Ads pour l'engagement

Avant de commencer, consultez les <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001?hl=en">instructions de Google concernant le partage d'un lien avec d'autres comptes Google Ads</Anchor>, et ce afin d'être sûr que vos campagnes d'engagement sont mesurées via votre l'ID de votre lien existant.

Pour mesurer les campagnes d'application Google Ads pour l'engagement, suivez les trois étapes suivantes :

<div id="enabling-retargeting-in-app-settings" />

<Accordion title="Activer le retargeting dans Paramètres d'app">

Pour activer les campagnes de retargeting d'une source média, vous devez le faire au niveau de l'app. S'il s'agit de la première campagne de retargeting pour votre app, effectuez les actions suivantes :

1. Dans AppsFlyer, rendez-vous dans **Paramètres de l'app**.
2. Faites défiler jusqu'en bas.
3. Activez **Attribution de réengagement.**

</Accordion>

<div id="enable-google-ads-retargeting-in-appsflyer" />

<Accordion title="Activez le retargeting Google Ads dans AppsFlyer">

* Suivez l'élément #5 dans les <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">instructions</Anchor> pour configurer Google Ads dans AppsFlyer.

</Accordion>

<div id="importing-session-start-conversions-in-google-ads" />

<Accordion title="Importer les conversions de début de session dans Google Ads">

Pour enregistrer les conversions des campagnes de réengagement **dans Google Ads**, vous devez importer l'évènement session\_start dans Google Ads.

Cet évènement apparaît dans Google Ads si au moins un utilisateur lance l'app après que vous ayez activé le retargeting dans AppsFlyer pour Google Ads. Pour vous en assurer, lancez vous-même l'app après avoir activé le retargeting.

Pour apprendre à importer les conversions dans Google Ads, cliquez <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">ici</Anchor>.

> 📘 **Note**
>
> Contrairement à tous les autres événements, session\_start peut être appelé par l'API Google Ads, même si vous n'importez pas session\_start dans Google Ads depuis AppsFlyer.
>  Cependant, dans ce cas, ces conversions seront toujours attribuées dans AppsFlyer. Ceci **crée une grande différence entre vos données dans AppsFlyer et dans Google Ads**. En outre, cela **empêche Google Ads d'optimiser** le ciblage des utilisateurs de votre campagne.

</Accordion>

<div id="setting-up-deep-linking-for-app-campaigns-for-engagement" />

<Accordion title="Configurer le deep linking pour les campagnes d'applications pour l'engagement">

Pour pouvoir exécuter des campagnes d'applications Google pour l'engagement, vous devez <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6310747?hl=en&ref_topic=3121770">utiliser le deep linking pour les campagnes de réengagement</Anchor>. Les solutions tierces de deep linking ne peuvent pas être utilisées en raison d'une incompatibilité de domaine. Cela inclut OneLink d'AppsFlyer. Utilisez vos <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6046977?hl=en">liens d'application, liens universels ou schémas d'URI personnalisées développés en interne</Anchor>.

Il n'est pas nécessaire d'ajouter des paramètres supplémentaires au deep link (is\_retargeting=true et pid=adwords ne sont pas obligatoires).

</Accordion>

<div id="support-for-non-app-campaigns-demand-gen-and-sem" />

<div id="dynamic-remarketing-and-shopping-campaigns" />

## Remarketing dynamique et campagnes de shopping

Le remarketing dynamique pour les applications et les campagnes de shopping est pris en charge dans AppsFlyer. Pour AppsFlyer, il s'agit simplement de campagnes de réengagement.

Pour en savoir plus sur le remarketing dynamique pour les applications, cliquez <Anchor target="_blank" href="https://support.google.com/adwords/answer/7538938">ici</Anchor>.  
 Pour en savoir plus sur les campagnes de shopping, cliquez <Anchor target="_blank" href="https://support.google.com/google-ads/answer/2454022?hl=en">ici</Anchor>.  
 Pour en savoir plus sur Google Ads pour l'engagement, cliquez <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">ici</Anchor>.

<div id="see-also" />

> 📄 **À consulter également**
>
> * Pour iOS 14, voir l'<Anchor target="_blank" href="/marketers/fr/docs/get-skan-postback-data-from-google-ads">interopérabilité entre Google Ads SKAdNetwork et AppsFlyer</Anchor>.

<div data-zendesk-anchors="google-ads-retargeting-campaigns=campagnes-de-reciblage-google-ads h_01HDP34BWZFG09ABN5NQB6EY32=campagnes-de-reciblage-google-ads setting-up-google-ads-app-campaigns-for-engagement=configuration-des-campagnes-dapps-google-ads-pour-lengagement h_01HDP34BWZXXNZDE0SR4MXBC9V=configuration-des-campagnes-dapps-google-ads-pour-lengagement h_01HDP34BWZNHY08NDX6YSE9CXR=enabling-retargeting-in-app-settings h_01HDP34BWZNNNT4HRMXJB2X3S2=enable-google-ads-retargeting-in-appsflyer h_01HDP34BWZ8MGJKEZFC77VYWNG=importing-session-start-conversions-in-google-ads h_01HDP34BWZHWVKKNB7CEHY73R0=note h_01HDP34BWZ64XG2G0PTH6XCCMG=setting-up-deep-linking-for-app-campaigns-for-engagement dynamic-remarketing-and-shopping-campaigns=remarketing-dynamique-et-campagnes-de-shopping h_01HDP34BWZ990SD3B1C5DZRESK=remarketing-dynamique-et-campagnes-de-shopping h_01HDP2XBSEJVQ5G0MD0V5R05CM=%C3%A0-consulter-%C3%A9galement" />
