---
title: 'Présentation du Smart Script OneLink : le générateur d''URL web-to-app'
metadata:
  keywords:
    - OneLink
    - Adwords
    - Advertisers
    - referral
    - referal
    - landing
    - redirect
    - gclid
    - facebook
    - landing page
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2018-12-12T16:32:47Z'
  edited_at: '2024-09-09T10:28:43Z'
  id: 360000677217
  locale: fr
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/fr/articles/360000677217
---
> **En bref :** Utilisez OneLink Smart Script pour convertir et attribuer les visiteurs de votre site web mobile (quelle que soit la source) en utilisateurs d'app mobile.

![7901_Smart_Script_flow_1920x1080_2__1_.png](https://files.readme.io/5181971c27e89974a86afeb83f48eb5c127b64765334bc3b5644ed47adb974e8-30193884510225.png)

## À propos du Smart Script OneLink

Les utilisateurs atterrissent sur votre site web mobile avant d’atteindre la page de votre app store, soit de manière organique, soit après s’être engagés dans une campagne publicitaire. Cependant, deux clics se produisent, comme suit :

* Directement vers la page web
* Directement depuis la page web vers l'app store

Dans ce scénario, l'attribution et le deep linking posent un problème. Les installations effectuées par les utilisateurs qui finissent par télécharger l'app peuvent être mal attribuées, ou être attribuées comme organiques. Cette erreur peut survenir même si le premier clic provient d’un réseau publicitaire, d’un clic Google ou d’une source média propriétaire.

OneLink Smart Script corrige les problèmes suivants :

* Il utilise les URL entrantes pointées vers la page web pour générer dynamiquement des URL OneLink sortantes qui dirigent vers l'app store.
* Il fournit une attribution web-to-app nette et précise pour toutes les sources média, y compris les réseaux publicitaires, SRN, clics Google et médias propriétaires.
* Il peut être utilisé pour le deep linking.
* Il fonctionne très bien sur n'importe quelle page web ou page d'accueil.
* Il ne requiert pas l’utilisation de bannières intelligentes.   
  **Remarque** : Les bannières intelligentes sont d'excellents outils de conversion pour de nombreux secteurs, de plus elles n'ont pas besoin d’un développeur pour être configurées, par contre elles ajoutent une étape (la bannière) au parcours de l’utilisateur.
* Il peut être configuré par le marketeur dans Google Tag Manager.

Il existe deux versions du Smart Script OneLink :

<Anchor target="_blank" href="/marketers/fr/docs/set-up-smart-script-to-convert-web-visitors">**OneLink Smart Script V2 (recommandé)**</Anchor> : si vous configurez OneLink Smart Script pour la première fois, c’est la version à utiliser en priorité. Il peut être configuré dans l'interface utilisateur AppsFlyer, ce qui simplifie le travail des développeurs, mais la configuration peut aussi se faire via Google Tag Manager.

<Anchor target="_blank" href="/marketers/fr/docs/legacy-onelink-smart-script-v1-setup">**OneLink Smart Script V1 (version héritée)**</Anchor> : si vous avez déjà configuré Onelink Smart Script, suivez les instructions propres à cette version pour gérer et modifier le script. **Remarque** : bien que ce ne soit pas obligatoire, mieux vaut migrer vers la version 2.

> 📘 **Remarque**
>
> Vous ne savez pas si OneLink Smart Script est la meilleure solution pour vous ? <Anchor target="_blank" href="/marketers/fr/docs/convert-your-mobile-web-visitors-to-app-users">Comparez</Anchor> OneLink Smart Script avec les autres solutions web-to-app AppsFlyer.

### Exemples

Dans cette section, vous trouverez des cas d'utilisation de OneLink Smart Script visant à générer des URL OneLink sortantes et offrant une attribution nette et précise, ou du deep linking. Pour voir des exemples d’utilisation par type de campagne avec certaines sources média, cf <Anchor target="_blank" href="/marketers/fr/docs/set-up-smart-script-to-convert-web-visitors#cas-dutilisation">Etudes de cas</Anchor>.

<div id="attribution" />

<Accordion title="Attribution">

Marc est le marketeur d'une chaîne d'hôtels. Il envoie un e-mail qui annonce un séjour à Orlando, en Floride. Le lien contenu dans l'e-mail est celui-ci : https://hotel.me/pid=email&c=orlando

Le lien redirige les utilisateurs vers le site web mobile de l'hôtel. Sur le site, les visiteurs voient s’afficher des boutons qui les invitent à télécharger l'app mobile de l'hôtel. Le Smart Script OneLink génère automatiquement une URL qui contient les mêmes paramètres **pid** et **c** que le lien contenu initialement dans l’e-mail. Le lien est celui-ci : https://hotel.onelink.me/Ac4G?pid=email&c=orlando

Lorsqu'un utilisateur clique sur un bouton du site mobile pour télécharger l'app, l'installation de cette dernière est attribuée à la campagne e-mail spécial Orlando de Marc.

</Accordion>

<div id="deep-linking" />

<Accordion title="Deep linking">

Emma reçoit un e-mail qui lui annonce un prochain séjour à Orlando, en Floride.

Le lien contenu dans l’e-mail est celui-ci : https://hotel.me?type=email&campaign=Florida&city=orlando

Lorsqu’elle clique sur le lien, elle est redirigée vers le site web mobile de l’hôtel. Le site contient des boutons l’invitant à télécharger l’app mobile de l’hôtel. Le Smart Script OneLink génère automatiquement une URL qui contient les mêmes paramètres **pid** et **c** que le lien contenu initialement dans l’e-mail. Le lien généré est le suivant : https://hotel.onelink.me/Ac4G?pid=email&c=Florida&deep_link_value=orlando

**Emma clique sur les boutons du site mobile, et elle est redirigée vers l’app store. Lorsqu'elle télécharge et lance l'app, elle est deep linkée vers la page de l'app dédiée au séjour à Orlando.**

> 📘 **Remarque**
>
> Le deep linking a les mêmes paramètres que ceux que les développeurs ont implémentés dans l'app. <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#créer-un-lien-onelink">En savoir plus.</Anchor>

</Accordion>

<div data-zendesk-anchors="about-onelink-smart-script=%C3%A0-propos-du-smart-script-onelink h_01HE7RW9G26CNME9TP350GFGS4=%C3%A0-propos-du-smart-script-onelink h_01HE7RW9G2BV2NFJ0YZ9QKAA2V=remarque examples=exemples h_01HE7RW9G2WBZ1A0RS66CJ7BNH=exemples h_01HE7RW9G24Y604NTZFGKJJXSS=attribution h_01HE7RW9G2ZDDWE1M1B2G175ZF=deep-linking h_01HE7RW9G3W5GKQ2CD2BZW8YAW=remarque-1" />
