---
title: Envoyer des copies de postback SKAN directement à AppsFlyer (iOS 15 et +)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-06-08T12:09:25Z'
  edited_at: '2023-11-12T12:52:58Z'
  id: 4402320969617
  locale: fr
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/fr/articles/4402320969617
---
> **En bref :** depuis iOS 15, vous pouvez configurer votre app pour qu'elle envoie des copies de postback à AppsFlyer en plus de ceux transmis aux réseaux publicitaires. AppsFlyer peut ainsi valider la valeur de conversion (VC) et vérifier que le postback est correct. Il suffit de configurer l’API Push AppsFlyer pour envoyer les copies de postback au deuxième point de terminaison choisi.

<div id="why-send-postback-copies-to-appsflyer" />

## Pourquoi transmettre des copies de postback à AppsFlyer ?

* Tous les postbacks sont rassemblés au même endroit : les postbacks contiennent des informations très importantes pour les annonceurs, notamment la CV qui permet de mesurer la qualité des utilisateurs. La CV transmise dans les postbacks, n'est ni cryptée ni incluse dans la signature du postback. Une CV rapportée par un réseau publicitaire ne peut donc pas être vérifiée et elle est sujette à la manipulation. AppsFlyer envoie les copies de postback aux points de terminaison que vous avez définis, le transfert se fait via API Push.
* Les chiffres concernant les re-téléchargements sont disponibles. Certains réseaux publicitaires ne partagent pas les données de re-téléchargement avec AppsFlyer. La copie du postback pallie ce manquement.
* Les données de l’app de l’éditeur sont disponibles
* L'engagement par type de touch est accessible

**Remarque !** AppsFlyer doit malgré tout continuer à recevoir les postbacks des réseaux publicitaires car ils contiennent d'autres données relatives au réseau publicitaire (ex : le nom de la campagne).

<div id="important" />

<div id="configure-your-app-to-send-postback-copies-to-appsflyer" />

## Configurer votre app pour envoyer des copies de postback à AppsFlyer

Selon la documentation d'Apple, vous pouvez définir un seul point de terminaison de postback SKAN.

**Pour enregistrer le point de terminaison AppsFlyer :**

1. Demandez à votre développeur iOS d'<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#sending-skan-postback-copies-to-appsflyer">ajouter AppsFlyer</Anchor> comme point de terminaison de postback SKAN dans la prochaine version de l'app.
2. Soumettez l'app iOS.
3. Les postbacks seront envoyées à AppsFlyer au fur et à mesure que la nouvelle version sera publiée (et non à partir de TestFlight).
4. Vous pouvez voir les postbacks reçus dans le <Anchor target="_blank" href="/marketers/fr/docs/skan-raw-data-reports">rapport des copies de postbacks</Anchor>.

<div id="common-misconceptions" />

## Infos ou intox ?

<div id="traits-and-limitations" />

<div id="dont-believe-everything-you-hear" />

> 📘 **Certaines idées fausses circulent !**
>
> Ces déclarations sont-elles vraies, ou fausses ?
>
> ![TrueOrFalse.png](https://files.readme.io/77212d5a12ce2af35b0a4c87ca9e58213b4f9fd88c775007793e7abb5aaa3f04-35682597298577.png)
>
> * Les annonceurs ne dépendent plus des réseaux publicitaires pour recevoir des postbacks.
>   * **Faux.** L'annonceur dépend toujours du réseau publicitaire pour déchiffrer les données sensibles. Exemple : seul le réseau publicitaire pourra mapper un ID de campagne SKAN au nom de la campagne.
> * Dès que mon deuxième point de terminaison est défini, des copies de tous les postbacks lui sont transmises.
>   * **Faux.** La fonctionnalité proposant un point de terminaison supplémentaire n'est disponible que pour les appareils sous iOS 15 et +. Les copies de postback ne seront pas transmises depuis un appareil avec une version IOS plus ancienne.

<div id="see-also" />

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_an_advertised_app?changes=latest_minor#see-also">Développeur Apple</Anchor>

<div data-zendesk-anchors="why-send-postback-copies-to-appsflyer=pourquoi-transmettre-des-copies-de-postback-%C3%A0-appsflyer h_01HE7SV29Y7DNSKAAR91MJX986=pourquoi-transmettre-des-copies-de-postback-%C3%A0-appsflyer configure-your-app-to-send-postback-copies-to-appsflyer=configurer-votre-app-pour-envoyer-des-copies-de-postback-%C3%A0-appsflyer h_01HE7SV29YDFA5Z0X4WS87YK0Y=configurer-votre-app-pour-envoyer-des-copies-de-postback-%C3%A0-appsflyer common-misconceptions=infos-ou-intox h_01HE7SV29YC855TGCXTCT4KHRN=infos-ou-intox h_01HE7SV29YMMTPH6EKYF3GQYEN=certaines-id%C3%A9es-fausses-circulent- h_01HE7SX466CMCC03K99H68ZRBN=%C3%A0-consulter-%C3%A9galement" />
