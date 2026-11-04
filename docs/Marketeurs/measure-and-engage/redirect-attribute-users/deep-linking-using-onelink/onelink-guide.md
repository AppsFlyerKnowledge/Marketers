---
title: Expérience client et vue d'ensemble du deep linking
metadata:
  keywords:
    - Marketers
    - start
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2017-10-19T08:53:16Z'
  edited_at: '2023-07-06T08:40:16Z'
  id: 115005248543
  locale: fr
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/fr/articles/115005248543
---
> **En bref :** créez des liens avec des fonctionnalités d'attribution, de redirection et de deep linking qui convertissent les utilisateurs de médias propres ou payants en utilisateurs d'app, quel que soit l'appareil, le système d'exploitation, le canal ou la plateforme utilisé(e).Ces liens vous permettent de créer la meilleure expérience possible pour vos utilisateurs, quelles que soient les sources média qu'ils convertissent : sites web, bannières, publications de réseaux sociaux, e-mails, SMS, etc.

<div id="introduction-video" />

## Vidéo de présentation

<Embed title="Lecteur vidéo YouTube" typeOfEmbed="youtube" url="https://www.youtube.com/embed/golT4p9D8MA" providerUrl="https://www.youtube.com" />

<div id="benefits" />

## Avantages

La suite expérience client et deep linking portés par OneLink que proposé AppsFlyer vous permet de créer des liens pour mesurer les campagnes de marketing mobile sur tous les principaux canaux. Les liens que vous créez vous permettent de :

* Interagissez avec vos clients sur différents points de contact en ligne et hors ligne.
* Augmentez les conversions en fournissant aux utilisateurs les meilleures expériences contextuelles, du clic à l'installation de l'app, à partir de n'importe quel point de contact.
* Obtenez une attribution et des mesures précises concernant les résultats de votre campagne.
* Envoyez de nouveaux utilisateurs qui ne possèdent pas votre app vers l'App Store ou l'URL web appropriée, peu importe l'appareil, le système d'exploitation, le canal ou la plateforme.
* Envoyez les utilisateurs qui ont installé votre app directement à un endroit précis de l'app (via les liens d'app, liens universels et schémas d'URI).
* Deep linkez les utilisateurs à des pages ou expériences dédiées dans l’app.

La suite est gratuite pour tous les forfaits.

<div id="experiences" />

## Expériences

La suite expérience client et deep linking portés par OneLink que propose AppsFlyer vous permet de créer des liens qui donnent une expérience optimale à vos utilisateurs, quelle que soit leur provenance. Les expériences client que vous pouvez configurer incluent :

* **Social-to-app** : engagez vos utilisateurs issus des réseaux sociaux et envoyez-les des publications depuis les réseaux sociaux vers votre app.
* **App-to-app** : dirigez les utilisateurs vers votre app à partir d’autres apps.
* <Anchor target="_blank" href="/marketers/fr/docs/convert-your-mobile-web-visitors-to-app-users">**Web-to-app**</Anchor> : convertissez les visiteurs de votre site web mobile en nouveaux utilisateurs d'app mobile avec des bannières et des scripts intelligents.
* **QR-to-app** : utilisez les QR codes pour baliser l'installation de votre app : les utilisateurs scannent un QR code à chaque moment clé de leur expérience hors ligne. Vous pouvez également mettre des QR codes sur votre site desktop ou sur des publicités TV et CTV afin de diriger les utilisateurs vers votre app.
* **Email-to-app** : utilisez des ESP (fournisseurs de services e-mail) pour engager les utilisateurs par e-mail puis envoyez-les vers votre app depuis leur boîte de réception.
* **Text-to-app** : créez des liens pour vos campagnes SMS et e-mail et contactez les utilisateurs via SMS.
* **Referral-to-app** : créez des liens d'invitation qui permettent aux utilisateurs ou influenceurs d'inviter d'autres personnes sur votre app, ou de partager un contenu in-app en particulier (comme un article).
* **Personnalisé** : que vos utilisateurs proviennent d'un appareil de bureau ou mobile, d'un média propre ou payant, en ligne ou hors ligne, OneLink vous permet d'envoyer vos utilisateurs au bon endroit, très simplement.

<div id="setting-up-onelink" />

## Configuration

Pour fournir l'expérience client souhaitée depuis le lien jusqu'à l'installation de l'app à l'aide de l'interface utilisateur AppsFlyer, vous avez besoin de :

* Deux rôles au sein d'une organisation (marketers et développeurs) travaillant ensemble.
* <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template">Créer un template OneLink</Anchor> qui représente la logique d'acheminement de vos liens, pour rediriger :
  * Les nouveaux utilisateurs qui n'ont pas installé votre app vers l'App Store ou l'URL web appropriée.
  * Les utilisateurs existants qui ont installée votre app vers louverture de l’app via des liens d’app Android, des liens universels iOS ou des schémas d’URI
    * Si ces paramètres ne sont pas définis, les utilisateurs utiliseront par défaut les mêmes paramètres que les nouveaux utilisateurs qui n'ont pas installé votre app (URL web ou app store).**Remarque** : un template OneLink n'est pas un lien cliquable pour vos utilisateurs finaux, c'est le socle qui permet de générer de nombreux liens personnalisés. Sur la base du template, vous pouvez créer de nombreux liens personnalisés OneLink sur lesquels les utilisateurs peuvent cliquer. Il est rare d'avoir besoin de plus d'un ou deux templates OneLink durant la vie d'une app (en dehors des tests).
* <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Création d'un lien OneLink</Anchor>. Il s'agit du lien cliquable ou du QR code scannable affiché dans vos publicités. Lors de la configuration du lien, vous définissez l’expérience client souhaitée, et ajoutez les paramètres de votre choix.

Le tableau suivant décrit les détails des tâches du marketeur et du développeur et fournit les liens vers les ressources correspondantes.

| Tâche | Détails | Ressources |
| --- | --- | --- |
| Créez un template OneLink | <ul><li>Le marketeur/chef de produit configure le template dans AppsFlyer.</li><li>Le développeur Android configure les méthodes d'ouverture d'app pour les utilisateurs existants (liens d'app Android et schéma d'URI).</li><li>Le développeur iOS configure les méthodes d’ouverture d’app pour les utilisateurs existants (liens universels iOS et schéma d’URI).</li></ul> | <ul><li>Tableau de bord AppsFlyer</li><li><Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template">Instructions pour les marketeurs</Anchor></li><li>Instructions pour les <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#app-opening-methods">développeurs Android</Anchor> et <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup">iOS</Anchor></li></ul> |
| Créer un lien OneLink | <ul><li>Le marketeur/chef de produit configure le lien dans AppsFlyer. Il sélectionne l’expérience client souhaitée et ajoute tout paramètre d’attribution ou de deep linking souhaité.</li><li>Les développeurs Android et iOS implémentent la méthode de DLU pour le deep linking (si le deep linking est requis).</li></ul> | <ul><li><Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Instructions pour les marketeurs</Anchor></li><li>Instructions pour les <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_unified_deep_linking">développeurs Android</Anchor> et <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_unified_deep_linking">iOS</Anchor></li><li>Exemples d'apps (Github)</li></ul> |

<div id="additional-options" />

## Options supplémentaires

Après avoir terminé une partie ou la totalité de la configuration dans l'interface utilisateur, pensez à mettre en œuvre les fonctionnalités supplémentaires décrites ci-dessous.

**Note** : toutes les fonctionnalités sont incluses dans les plans AppsFlyer <Anchor target="_blank" href="/marketers/fr/docs/account-management-plans-payments-and-billing">Zéro et Croissance</Anchor>, à l'exception de l'API OneLink, qui est une fonctionnalité premium.

* <Anchor target="_blank" href="/marketers/fr/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API OneLink</Anchor> et <Anchor target="_blank" href="/marketers/fr/docs/perform-onelink-bulk-actions-via-csv">création de liens multiples</Anchor> : redimensionnez et lancez plusieurs campagnes en même temps. Créez des milliers de OneLinks en quelques clics et gagnez un temps précieux pour vous concentrer sur vos actions marketing et vos campagnes.
* <Anchor target="_blank" href="/marketers/fr/docs/export-onelink-urls">Exporter les URL OneLink</Anchor>: téléchargez toutes les URL OneLink qui ont été créées dans l'interface utilisateur d'AppsFlyer (les URL OneLink issues du SDK, de l'API OneLink ou d'importations groupées ne sont pas incluses).
* <Anchor target="_blank" href="/marketers/fr/docs/measuring-push-notification-re-engagement-campaigns">Mesure des campagnes de ré-engagement par notifications push</Anchor> : utilise les notifications Push via OneLink pour mesurer le réengagement des utilisateurs de mobile.
* <Anchor target="_blank" href="/marketers/fr/docs/cross-promotion-attribution-for-marketers">Attribution de promotion croisée</Anchor> : les utilisateurs de vos apps existantes sont d'excellents candidats pour l'installation de vos nouvelles applications.Apprenez à utiliser les méthodes du SDK pour créer et mesurer facilement les campagnes d'invitation des utilisateurs.
* <Anchor target="_blank" href="/marketers/fr/docs/understand-onelink-short-vs-long-urls">URL longues</Anchor> : ajoutez des paramètres à vos liens personnalisés OneLink ou générez un grand nombre de liens personnalisés OneLink  en appliquant vos propres formules simples dans une feuille de calcul.
* <Anchor target="_blank" href="/marketers/fr/docs/redirect-app-users-to-a-website">Redirection d'une application vers le web</Anchor> : redirigez les utilisateurs de votre app vers un site web ou une page de réseau social.

<div id="troubleshooting-and-faq" />

## Dépannage et FAQ

Avec notre <Anchor target="_blank" href="/marketers/fr/docs/onelink-troubleshooting-and-faq">guide de dépannage OneLink</Anchor>, vous trouverez rapidement les solutions pour tester et déboguer les problèmes de redirection ou comportement des liens personnalisés OneLink.

<div id="limitations" />

## Limites

* OneLink n'est pas pris en charge par l'objectif d'installation de l'app mobile Meta, où seuls les liens d'app Meta sont acceptés.

<div data-zendesk-anchors="introduction-video=vid%C3%A9o-de-pr%C3%A9sentation benefits=avantages experiences=exp%C3%A9riences setup=configuration additional-options=options-suppl%C3%A9mentaires troubleshooting-and-faq=d%C3%A9pannage-et-faq limitations=limites" />
