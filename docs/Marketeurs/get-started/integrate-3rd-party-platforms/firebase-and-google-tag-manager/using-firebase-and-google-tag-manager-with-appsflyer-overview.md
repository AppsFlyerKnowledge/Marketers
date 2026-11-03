---
title: Utiliser Firebase et Google Tag Manager avec AppsFlyer
metadata:
  keywords:
    - GTM
    - Google Tag Manager
    - firebase
    - Advertisers
    - datalayer
    - data layer
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
  created_at: '2016-05-13T19:42:23Z'
  edited_at: '2023-11-12T12:52:02Z'
  id: 210353513
  locale: fr
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/fr/articles/210353513
---
> **En bref :** à propos de l'envoi d'événements signalés transmis par Firebase SDK à AppsFlyer via Google Tag Manager.

<Image alt="gtm.png" src="https://files.readme.io/fbb4e0f83baf6f5f7f8dc83e02986ca011f5cb919b9870768da1606798211dcc-360002517245.png" width="289px" />

L'intégration d'AppsFlyer avec Google Tag Manager (GTM) et Firebase permet au développeur d'envoyer des événements in-app à Firebase en utilisant le Firebase SDK, et de transmettre les événements à AppsFlyer via SDK en utilisant Google Tag Manager. Cela permet d'éviter d'envoyer deux fois le même événement.

Les événements envoyés via GTM sont calqués sur les événements in-app d'AppsFlyer. Le nom, les paramètres et la structure de l'événement sont les mêmes. Si vous avez déjà GTM dans votre application, il est très simple de l'utiliser pour envoyer des événements à AppsFlyer.

Suivez les instructions de ce guide pour envoyer des événements. 

### Attention

* **Source de l'événement dans les données brutes :** les événements générés par GTM ont leur source définie sur S2S dans les rapports de données brutes. Cela peut entraîner une certaine confusion, car les événements sont rapportés par le SDK.
* **Mise à jour de la valeur de conversion de SKAdNetwork** : les événements qui sont générés par GTM et transmis au SDK comme stipulé dans ce guide font que le SDK met à jour la valeur de conversion de la même manière que pour les événements classiques du SDK. Il vous suffit d'activer et de configurer les <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">paramètres de mesure de SKAdNetwork</Anchor>.

> 📘 **Note**
>
> * Actuellement, l'intégration de Google Tag Manager ne permet pas d'envoyer les paramètres suivants à AppsFlyer :
>   * ID utilisateur
>     du client
>   * `att`
>   * `os`Notez que :
>   * Le paramètre `att` est requis lors de l'envoi de postbacks d'événements in-app aux SRN.
>   * Les paramètres `att` et `os` sont nécessaires lors de l'envoi d'un postback d'événement in-app à Meta Ads.

### Conditions préalables

Avant de commencer à envoyer des événements à AppsFlyer via GTM, vous devez implémenter le SDK GTM dans votre application. Conditions :

1. Vous avez besoin d'un [compte GTM](https://www.google.com/analytics/tag-manager/).
2. Vous devez avoir configuré l'intégration GTM + Firebase pour votre application (cf instructions pour [Android](https://developers.google.com/tag-manager/android) et [iOS](https://developers.google.com/tag-manager/ios/)).
3. <Anchor target="_blank" href="/marketers/fr/docs/integrate-the-appsflyer-sdk">Intégrez le SDK AppsFlyer</Anchor> si vous ne l'avez pas encore fait.

Une fois que tout est en place, passez à la <Anchor target="_blank" href="/marketers/fr/docs/using-firebase-and-google-tag-manager-with-appsflyer-google-tag-manager-setup">mise en place de GTM</Anchor>.

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/migrate-from-firebase-dynamic-links-to-appsflyer">Migrer des liens Firebase Dynamic vers AppsFlyer</Anchor>

<div data-zendesk-anchors="considerations=attention h_01HE7SKSCBH47YYFTKBWY3JVSV=attention h_01HE7SKSCBBTTWATRZ87BYRW6G=note prerequisites=conditions-pr%C3%A9alables h_01HE7SKSCB9QHA4WEERVSWMF0P=conditions-pr%C3%A9alables h_01HE7SQQG2VJW9179Q77PTZFPH=%C3%A0-consulter-%C3%A9galement" />
