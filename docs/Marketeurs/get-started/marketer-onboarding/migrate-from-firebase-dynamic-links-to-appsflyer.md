---
title: Migrer des liens dynamiques Firebase vers AppsFlyer
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2023-06-19T09:27:37Z'
  edited_at: '2024-11-06T11:47:09Z'
  id: 16282289097105
  locale: fr
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/fr/articles/16282289097105
---
> **En bref :** Passez facilement de Firebase Dynamic Links à AppsFlyer grâce à notre guide de migration étape par étape

<div id="about-the-migration" />

## Aperçu

Avec l'<Anchor target="_blank" href="https://firebase.google.com/support/dynamic-links-faq">annonce de Google</Anchor> de la fermeture de Firebase Dynamic Links, c'est le moment idéal pour migrer facilement vers AppsFlyer.

<div id="step-3-create-a-onelink-template" />

<div id="step-2-add-your-app" />

<div id="step-1-create-an-appsflyer-account" />

<div id="migrate-from-firebase-to-appsflyer" />

## Comment migrer de Firebase vers AppsFlyer

> 🚧 **Important !**
>
> Avant de commencer la migration, assurez-vous de disposer des éléments suivants :
>
> 1. Vos liens dynamiques Firebase
> 2. Votre développeur d'apps

### 1. Création de compte

*Qui est nécessaire - Marketeur*

* <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Créer un compte AppsFlyer</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/user-management">Ajoutez des utilisateurs au compte avec les autorisations appropriées</Anchor>

### 2. Ajouter l'application

*Qui est nécessaire - Marketeur*

* <Anchor target="_blank" href="/marketers/fr/docs/adding-an-app-to-appsflyer">Ajoutez l'application</Anchor> dans AppsFlyer.
* [Facultatif] Modifiez la fenêtre par défaut de 90 jours <Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window">de réattribution</Anchor> pour l'aligner sur votre définition des utilisateurs actifs.

altajouteralt

### 3. Configurer le modèle OneLink

*Qui est nécessaire - Marketeur et développeur d'apps*

Un modèle OneLink constitue la base de la logique de redirection pour tous les liens OneLink que vous créez pour vos différentes campagnes marketing. Un modèle est requis pour créer des liens et des expériences pour les utilisateurs finaux.

* <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template#procédures">Créer un modèle OneLink</Anchor>
  * Le marketeur doit être un utilisateur administrateur chez AppsFlyer ou disposer des autorisations <Anchor target="_blank" href="/marketers/fr/docs/user-management">pour ajouter\/modifier des modèles OneLink</Anchor>

<Image align="center" alt="OneLink" src="https://files.readme.io/d773d60cd2febcf6a8389e9586e8ca23a1515fc853e4d42d0db98661cacb387a-360009665478.png" />

### 4. Configurer le SDK

*Qui est nécessaire - Développeur d'apps*

Le SDK AppsFlyer intégré à l'application est le lien entre l'application et la plateforme AppsFlyer. Il fournit :

* Deep Linking - Le SDK permet la mise en œuvre de liens profonds unifiés (UDL)
* Attribution - Le SDK rapporte les installations d'applications, les ouvertures d'applications, les événements in-app, etc.

Intégrez le SDK AppsFlyer dans votre application en suivant les étapes ci-dessous.

<div id="step-5-understand-parameter-mapping" />

<div id="appsflyer-sdk-integration-steps" />

<div id="step-4-set-up-the-appsflyer-sdk" />

<Accordion title="Étapes d'intégration du SDK AppsFlyer">

1. Intégrez le SDK AppsFlyer dans l'application.  
   Consultez les guides d'intégration du SDK pour <Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">Android</Anchor> et <Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">iOS</Anchor>.
2. Cartographiez les événements in-app que vous souhaitez enregistrer à l'aide des schémas AppsFlyer.  
   Cela peut être fait via <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">SDK</Anchor> ou <Anchor target="_blank" href="/marketers/fr/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>.
3. Gérez le SDK de Firebase.  
   Vous pouvez passer exclusivement à AppsFlyer ou utiliser les deux SDK simultanément pendant quelques semaines. Consultez la répartition de ces options dans le tableau ci-dessous.  

| Option | Que se passe-t-il après  <br />la mise à jour de la version de l'application | Impact |
| --- | --- | --- |
| Supprimer le SDK de Firebase (recommandé) | Seul AppsFlyer enregistre les nouvelles installations et les utilisateurs qui mettent à jour.  <br />Firebase affiche toujours les événements réalisés par les utilisateurs, jusqu'à ce que ceux-ci mettent également à jour leur application. | <ul><li>Transition rapide</li><li>Pas de double attribution</li><li>Vous permet de voir si vous avez des versions d'app persistantes avec le SDK Firebase toujours présent.</li></ul> |
| Conserver le SDK de Firebase pour une période de transition | AppsFlyer et Firebase attribuent les nouvelles installations et rapportent les événements. À une date ultérieure, retirez le SDK Firebase. | <ul><li>La validation des données est possible. Cela signifie que vous pouvez comparer les données d'AppsFlyer et de Firebase.</li><li>Double attribution, ce qui peut entraîner des frais doublés auprès des réseaux publicitaires.</li><li>Charge de travail plus élevée</li></ul> |

4. Après avoir terminé toutes les autres tâches prévues, mettez à jour la version de l'application avec le SDK AppsFlyer sur le marché. Les nouveaux utilisateurs sont attribués par AppsFlyer.   
   **Remarque** :
   * Assurez-vous de mettre à jour l'application pour iOS, Google Play et tous les marchés Android hors store concernés.
   * Votre app Android peut exister sur des sites APK non officiels, même si vous n'en êtes pas conscient (cherchez le nom de package de votre app sur le web pour le découvrir). Les sites APK prennent du temps pour se mettre à jour vers la dernière version, ils peuvent donc attirer des utilisateurs organiques qui installent d'anciennes versions sans le SDK AppsFlyer.
   * Le déploiement des mises à jour d'apps dans les app stores peut prendre quelques jours pour être complété. Les utilisateurs qui installent pendant cette phase peuvent encore obtenir l'ancienne version.

</Accordion>

### 5. Comprendre le mappage des paramètres

*Qui est nécessaire - Développeur d'apps*

Comprenez comment les paramètres des liens dynamiques de Firebase se rapportent aux paramètres correspondants d'AppsFlyer.

Un mappage correct et une bonne compréhension des paramètres correspondants garantiront que vos liens donnent les mêmes résultats.

Le tableau ci-dessous répertorie tous les paramètres de Firebase avec leurs équivalents AppsFlyer.

Utilisez ce tableau comme référence pour tous les paramètres que vous utilisez actuellement lors de votre migration vers AppsFlyer.

<div id="step-6-create-onelink-links-with-mapped-parameters" />

<div id="note" />

> 📘 **Remarque**
>
> Si un paramètre Firebase n'est pas répertorié, c'est parce qu'AppsFlyer le prend en charge dans la configuration du modèle OneLink sans que vous ayez besoin d'ajouter un paramètre dans vos liens.

<table><thead><tr><th>Regroupement</th><th>Firebase</th><th>AppsFlyer</th><th>Description</th></tr></thead><tbody><tr><td><span>Paramètres mobiles</span></td><td><span>Lien</span></td><td><ul><li><span>af_dp</span></li><li><span>deep_link_value</span></li></ul></td><td><ul><li><span><strong>af_dp</strong> - Schéma URI utilisé comme méthode de secours pour lancer les applications iOS et Android.</span></li><li> <strong>deep_link_value</strong> - Nom de la valeur pour le contenu spécifique in-app vers lequel les utilisateurs seront dirigés.</li></ul></td></tr><tr><td> <span></span><br/><span>Paramètres Android</span> </td><td><span>afl</span></td><td><span>af_android_url</span></td><td>Permet de rediriger les utilisateurs Android vers une page Web personnalisée</td></tr><tr><td rowspan="2"> <span>Paramètres iOS</span><br/><span></span><br/> </td><td><span>ifl</span></td><td><span>af_ios_url</span></td><td>Permet de rediriger les utilisateurs iOS vers une page Web personnalisée</td></tr><tr><td><span>efr</span></td><td><span>af_force_deeplink</span></td><td>Utilisé pour forcer une application iOS à s'ouvrir en utilisant le schéma URI af_dp. Sans cela, l'application ne s'ouvrira pas à l'aide du schéma URI</td></tr><tr><td><span>Autre URL de plateforme</span></td><td><span>ofl</span></td><td><span>af_web_dp</span></td><td>Permet de rediriger les utilisateurs de bureau vers une page Web personnalisée</td></tr><tr><td rowspan="3"> <span></span><br/><span>Tags sociaux</span><br/><span></span><br/> </td><td><span>st</span></td><td><span>af_og_title</span></td><td>Utilisé pour personnaliser le titre du contenu partagé sur les réseaux sociaux</td></tr><tr><td><span>sd</span></td><td><span>af_og_description</span></td><td>Utilisé pour personnaliser la description du contenu partagé sur les réseaux sociaux</td></tr><tr><td><span>si</span></td><td><span>af_og_image</span></td><td>Utilisé pour personnaliser l'image du contenu partagé sur les réseaux sociaux</td></tr><tr><td rowspan="5"><p><span>Paramètres analytiques </span><br/><span></span><br/><span></span><br/><span></span><br/></p></td><td><span>utm_source</span></td><td><span>pid</span></td><td>Source du média</td></tr><tr><td><span>utm_medium</span></td><td><span>af_channel</span></td><td>Identifie les canaux des sources médias sur lesquels vos publicités sont diffusées</td></tr><tr><td><span>utm_campaign</span></td><td><span>c</span></td><td>Nom de la campagne</td></tr><tr><td><span>utm_term</span></td><td><span>af_keywords</span></td><td>Liste de mots-clés pour les campagnes ciblées par texte</td></tr><tr><td><span>utm_content</span></td><td><span>af_adset</span></td><td>Ensemble de publicités associées à une campagne</td></tr></tbody></table>

### 6. Migrer

*Qui est nécessaire - Marketeur*

En utilisant vos paramètres mappés, vous pouvez créer des liens OneLink sur votre modèle OneLink.

Les liens peuvent être créés à l'aide du <Anchor target="_blank" href="/marketers/fr/docs/onelink-guide">tableau de bord AppsFlyer</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/perform-onelink-bulk-actions-via-csv">en masse</Anchor> via un fichier CSV, par programmation avec notre <Anchor target="_blank" href="/marketers/fr/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API OneLink</Anchor>, dans le <Anchor target="_blank" href="/marketers/fr/docs/user-invite-attribution">SDK</Anchor>, ou via des <Anchor target="_blank" href="/marketers/fr/docs/understand-onelink-short-vs-long-urls">liens longs</Anchor>.

Utilisez le tableau suivant pour déterminer quelle méthode convient le mieux à votre utilisation.

| Firebase | AppsFlyer | À utiliser si | Remarques |
| --- | --- | --- | --- |
| Console Firebase | Page de gestion OneLink | Vous souhaitez créer des liens OneLink un par un. De cette manière, vous pouvez utiliser pleinement toutes les fonctionnalités et possibilités offertes par OneLink |  |
| API de générateur de liens dynamiques | SDK | Vous souhaitez créer des liens générés programmatiquement dans l'application pour des utilisations telles que des invitations et des recommandations utilisateurs | <ul><li>Nécessite un développeur iOS ou Android</li></ul> |
| API REST de Firebase | API OneLink | Vous souhaitez créer des liens par programmation hors de l'application mobile | <ul><li>Nécessite un développeur</li><li>Non disponible sur le plan gratuit</li></ul> |
| Construction manuelle des liens | Liens longs | Vous souhaitez construire manuellement le lien avec ses paramètres de requête. À utiliser si vous n'avez pas besoin de liens courts. Par exemple, si le lien est derrière un bouton ou une bannière |  |
|  | Page de liens en masse | Vous souhaitez migrer en masse tous vos liens dynamiques Firebase vers AppsFlyer.<br /><br />Ceci est recommandé pour transférer rapidement tous vos liens sans aucune erreur | <ul><li>Nécessite une étape préalable de [mappage des clés et valeurs de paramètres de lien selon les paramètres Firebase correspondants](/docs/migrate-from-firebase-dynamic-links-to-appsflyer#5-comprendre-le-mappage-des-paramètres)</li><li>Non disponible dans le forfait gratuit.</li></ul> |
|  | Script intelligent | Si vous souhaitez créer un lien long de façon dynamique sur une page web pour une expérience web à app | <ul><li><Anchor target="_blank" href="/marketers/fr/docs/set-up-smart-script-to-convert-web-visitors">Cliquez ici</Anchor> pour découvrir si Smart Script offre des fonctionnalités qui vous conviendraient mieux.</li></ul> |

<div id="see-also" />

> 📄 **Voir aussi**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/using-firebase-and-google-tag-manager-with-appsflyer-overview">Utilisation de Firebase et de Google Tag Manager avec AppsFlyer — Aperçu</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/brand-onelink-with-your-domain">Domaines de marque</Anchor>

<div data-zendesk-anchors="overview=aper%C3%A7u 01H8K961JHRXNQHBVN930XW70Q=aper%C3%A7u how-to-migrate-from-firebase-to-appsflyer=comment-migrer-de-firebase-vers-appsflyer 01H8K961JHCK0Z4GTTHCAKF98E=comment-migrer-de-firebase-vers-appsflyer 01H8K961JHTGFTD3337JNKQXV5=important- 1-account-creation=1-cr%C3%A9ation-de-compte 01H8K961JHE743GS9PZ33WJSCX=1-cr%C3%A9ation-de-compte 2-add-the-app=2-ajouter-lapplication 01H8K961JHSS4FBTCH9F7VTTKB=2-ajouter-lapplication 3-configure-onelink-template=3-configurer-le-mod%C3%A8le-onelink 01H8K961JH10ZGTEM5XJ55TVA3=3-configurer-le-mod%C3%A8le-onelink 4-set-up-the-sdk=4-configurer-le-sdk 01H8K961JH19G43JBQ03F8XZAV=4-configurer-le-sdk 01H8K961JHCRCNFEK4P320HAAB=appsflyer-sdk-integration-steps map-parameters=5-comprendre-le-mappage-des-param%C3%A8tres 01H8K961JHJJ1NTH9RNJRVBSND=5-comprendre-le-mappage-des-param%C3%A8tres 01H8K961JHBXVKXM0XQYY605EQ=remarque migrate=6-migrer 01H8K961JH2DN7XEX5FB3C5J8Y=6-migrer h_01HE7SZPKKQETH260G45V0D0HN=voir-aussi" />
