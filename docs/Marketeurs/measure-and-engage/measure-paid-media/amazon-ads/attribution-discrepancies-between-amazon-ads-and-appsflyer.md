---
title: Discrepancies d'attribution entre Amazon Ads et AppsFlyer
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2024-09-18T04:28:03Z'
  edited_at: '2024-11-13T14:10:46Z'
  id: 28461159218449
  locale: fr
  section: Amazon Ads
  section_id: 28703975923729
  url: https://support.appsflyer.com/hc/fr/articles/28461159218449
---
> **En bref :** Découvrez les différences entre les modèles d'attribution d'Amazon Ads et d'AppsFlyer.

## Aperçu

En tant que deux acteurs majeurs de l'acquisition d'utilisateurs mobiles, Amazon Ads et AppsFlyer adoptent des modèles d'attribution distincts. Cela peut provoquer des divergences entre leurs tableaux de bord respectifs. Bien que nous collaborions étroitement avec Amazon Ads pour réduire ces divergences, les annonceurs doivent être conscients des causes potentielles.

## Différences dans les modèles d'attribution

Le tableau ci-dessous explique les raisons possibles des divergences entre les tableaux de bord d'Amazon Ads et d'AppsFlyer :

| Cause | Gestionnaire Amazon Ads | AppsFlyer |
| --- | --- | --- |
| <span id="clickthrough-attribution-lookback-window"></span>Fenêtre de rétrospection d'attribution par clic | La fenêtre par défaut est de 14 jours. Elle ne peut actuellement pas être configurée. | La fenêtre par défaut est de 7 jours. La fenêtre peut être configurée entre 1 et 30 jours. Assurez-vous d'aligner avec la fenêtre d'attribution d'Amazon Ads. |
| <span id="viewthrough-attribution-lookback-window"></span>Fenêtre de rétrospection d'attribution après affichage | La fenêtre par défaut est de 14 jours. Elle ne peut actuellement pas être configurée. | La fenêtre par défaut est de 1 jour. La fenêtre peut être configurée entre 1 et 48 heures. Assurez-vous d'aligner avec la fenêtre d'attribution d'Amazon Ads. |
| <span id="multichannel-source-attribution"></span>Attribution multi-channele | Amazon Ads s'auto-attribue les installations indépendamment des autres sources média. | AppsFlyer utilise l'attribution au dernier clic.  <br />En savoir plus sur le <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model">modèle d'attribution AppsFlyer</Anchor>. |
| <span id="different-timezones"></span>Fuseaux horaires différents | Le fuseau horaire d'Amazon Ads (indiqué à côté de la plage de dates) ne peut pas être ajusté. Il a été configuré lors de la création du compte publicitaire. | Le fuseau horaire par défaut des applications AppsFlyer est UTC+0. Pour correspondre au fuseau horaire défini dans Amazon Ads, modifiez le fuseau horaire de l'application sur la <Anchor target="_blank" href="/marketers/fr/docs/app-settings#localization-time-zone">page des paramètres de l'application</Anchor>. |

## Réduction des divergences

Bien qu'il y ait des différences dans les modèles d'attribution, il est parfois possible de réduire les divergences.

### Attribution par clic et par consultation

AppsFlyer prend en charge l'attribution par clic et par consultation. Pour réduire les divergences entre Amazon Ads et AppsFlyer, assurez-vous que les fenêtres de rétrospection après clic et après affichage sont cohérentes avec celles définies par Amazon Ads.

> 📄 **Exemple**
>
> Supposons que la fenêtre rétrospective post-clic des Amazon Ads soit configurée sur AppsFlyer à 1 jour pour votre application com.greatapp, alors que sur Amazon Ads, elle est configurée sur la valeur par défaut de 7 jours. Les utilisateurs qui cliquent sur l'annonce de Greatapp sur Amazon Ads mais qui lancent l'application pour la première fois après 2 à 7 jours sont considérés comme des utilisateurs organiques sur AppsFlyer, tandis qu'Amazon Ads se charge de les déclarer.

<div data-zendesk-anchors="overview=aper%C3%A7u h_01J81NN4J4A1KWBXJQD9SM2AWH=aper%C3%A7u differences-in-attribution-models=diff%C3%A9rences-dans-les-mod%C3%A8les-dattribution h_01J81NN4J4WSJBFHBARKTQ9JG5=diff%C3%A9rences-dans-les-mod%C3%A8les-dattribution reducing-discrepancies=r%C3%A9duction-des-divergences h_01J81NN4J4EJQH47YJF0H5M97G=r%C3%A9duction-des-divergences clickthrough-and-viewthrough-attribution=attribution-par-clic-et-par-consultation h_01J81NN4J4X6V3XWRZWNDJ14PV=attribution-par-clic-et-par-consultation h_01J81NN4J4NC0SK4QRTQZRJS0F=exemple" />
