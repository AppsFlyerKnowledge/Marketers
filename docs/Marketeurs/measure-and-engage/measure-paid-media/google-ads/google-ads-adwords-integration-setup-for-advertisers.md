---
title: Configurer l'intégration de Google Ads (AdWords)
metadata:
  keywords:
    - Integration
    - Google AdWords
    - Configuration
    - google
    - migration
    - Advertisers
    - google ads configuration
    - ads
    - google ads
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2017-05-17T19:16:15Z'
  edited_at: '2024-04-02T09:52:15Z'
  id: 115002504686
  locale: fr
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/fr/articles/115002504686
---
> **En bref :** intégrez votre compte Google Ads avec AppsFlyer pour afficher les données d'attribution de l'ensemble de vos campagnes.

> 🚧 **Important !**
>
> Voir le bulletin d'information sur le <Anchor target="_blank" href="/marketers/fr/docs/bulletin-supporting-the-new-google-eu-consent-policy">soutien à la nouvelle politique de consentement Google dans l'UE</Anchor>.

## Utilisation de Google Ads

L’IU de Google Ads vous permet uniquement de configurer une <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6247380?hl=en">Campagne d'applications</Anchor> pour appareils iOS et Android.

Pour attribuer des utilisateurs d'autres plates-formes, par exemple Pour Google Ads, les utilisateurs de Windows Phone doivent utiliser une <Anchor target="_blank" href="/marketers/fr/docs/set-up-smart-script-to-convert-web-visitors#google-ads-gclid">solution de page de destination</Anchor> .

Pour configurer d'autres types de campagnes spécifiques en plus des campagnes d'applications, contactez votre représentant Google.

<div id="configuring-google-ads-attribution-for-advertisers" />

## Configuration de l'attribution de Google Ads pour les annonceurs

Pour commencer l'attribution de campagnes Google Ads avec AppsFlyer, procédez comme suit :

> 📘 **Remarque**
>
> Pour pouvoir être intégrée à Google Ads, l’application doit obligatoirement recueillir l'IDFA ou le GAID. Pour plus d'informations, vous pouvez consulter le <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">guide de l'intégration SDK.</Anchor>

<Embed title="Configurer l'intégration de Google Ads (AdWords)" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/f3i7cti7r5" providerUrl="https://fast.wistia.com" />

<Accordion title="">

<div id="step-1-create-the-google-ads-link-id-mandatory" />

<Accordion title="Étape 1 : création de l'ID du lien Google Ads (obligatoire)">

La création d'un ID de lien nécessite un **accès admin** au compte Google.

1. Connectez-vous à votre compte admin Google Ads.
2. Dans le menu d’en haut, cliquez sur **Outils et paramètres**.
3. Dans le menu **Configuration**, sélectionnez **Gestionnaire des données** et cliquez sur **+ Connecter le produit**.
4. Dans la barre de recherche **Sources de données**, tapez "analyses des apps tierces", sélectionnez les sources puis cliquez sur **Continuer**.
5. Cliquez sur **Créer un ID de lien**
6. Sélectionnez **AppsFlyer** comme fournisseur d'analyse des applications.
7. Sélectionnez la plateforme (Android ou iOS).
8. Trouvez votre app et sélectionnez-la.
9. Cliquez sur **Créer un ID de lien**

</Accordion>

<div id="step-2-set-up-google-ads-on-appsflyer-mandatory" />

<Accordion title="Étape 2 : configuration de Google Ads dans AppsFlyer (Obligatoire)">

**(n’importe quel membre du compte AppsFlyer)**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez Collaboration **> Marketplace partenaire**
2. Recherchez **Google Ads** puis sélectionnez-le.
3. Cliquez sur **Configurer l'intégration. Vous êtes alors dirigé vers la page de configuration de l'intégration.**
4. Dans l'onglet **Intégration** , cochez **Activer le partenaire**.  
   **Remarque :** la case doit rester cochée (<Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">activée</Anchor>) tant que vous travaillez avec le partenaire<Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">.</Anchor>
5. Collez **l'ID de lien** que vous avez copié à l'étape précédente.
6. Faites le choix d'activer ou non les<Anchor target="_blank" href="/marketers/fr/docs/support-google-eu-consent-policy#do-i-have-control-over-consent-data-for-nonue-users">**Utilisateurs hors UE**</Anchor>.  

   <Image align="center" alt="non eu usrs.png" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="557px" />
7. Configuration des **attributions d'installations** :
   1. Définissez la **fenêtre rétrospective post-clic d’installation.**  
      Sélectionnez les unités de la fenêtre rétrospective (heures ou jours) et réglez le curseur sur la valeur souhaitée. Nous recommandons de définir la durée de la fenêtre rétrospective sur 30 jours, afin de garantir la correspondance avec Google Ads.
   2. [Facultatif] si vous lancez des campagnes de pré-enregistrement pour les apps Android, définissez **la fenêtre d'attribution de la campagne de pré-enregistrement** (90 jours par défaut). Ce curseur détermine la fenêtre d'attribution des installations aux campagnes de pré-inscription.
   3. Activation de **l'attribution post vue.**
   4. Sélectionnez les unités de la fenêtre rétrospective (heures ou jours) et réglez le curseur sur la valeur souhaitée. Nous recommandons de définir la durée de la fenêtre rétrospective sur 1 jour, afin de garantir la correspondance avec Google Ads.  
      **Remarque :** Google n'envoie pas de demande pour les impressions des apps iOS. Le bouton d'activation des attributions post vue d'installations ainsi que le curseur pour la fenêtre d'attribution ne font plus partie des applications iOS.  

      <Image align="center" alt="" src="https://files.readme.io/a6f05b9f92abf6dfdbaafc248c0381bfe063086daa10727dc088d484c1b38f0b-30759221879825.png" />
8. Pour activer l'attribution de réinstallation, activez l'option **Réinstaller l'attribution**.  
   Il est inutile de configurer les fenêtres d'attribution pour les réinstallations, car les valeurs sont extraites des paramètres d'attribution d'installation.  

   <div id="important" />

   > 🚧 **Important !**
   >
   > Une réinstallation des données de conversion est **présentée sous la forme session\_start** dans le tableau de bord Google Ads. Dans AppsFlyer, elle est attribuée et considérée comme une réattribution.

9. Configurer **l'attribution du réengagement** :  
   1. <Anchor target="_blank" href="/marketers/fr/docs/app-settings#reengagement-attribution">Activez le retargeting dans les paramètres de l'app</Anchor>.
   2. Activez **Attribution de réengagement.**
   3. Définissez la **fenêtre rétrospective de réengagement post vue**, elle commence au moment du clic sur la publicité, c'est la période pendant laquelle l'application doit être lancée pour que le clic soit enregistré en tant que réengagement. Sélectionnez une fenêtre rétrospective en heures ou en jours et réglez le curseur sur la valeur souhaitée.
   4. Activez **l'attribution de réengagement post vue.**  
      **Remarque :** Google n'envoie pas de demande pour les impressions des apps iOS. Le bouton d'activation des attributions post vue d'installations ainsi que le curseur pour la fenêtre d'attribution ne font plus partie des applications iOS.
   5. Définissez la **fenêtre rétrospective de réengagement post vue**, elle commence au moment de l'impression d'une publicité, c'est la période pendant laquelle l'application doit être lancée pour que l'impression soit enregistrée en tant que réengagement. Sélectionnez une fenêtre rétrospective en heures ou en jours et réglez le curseur sur la valeur souhaitée.
   6. Définissez la **fenêtre de réengagement**. C'est la période pendant laquelle les évènements in-app de l'utilisateur sont attribués à la source média de retargeting après un clic ou une impression. Vous pouvez définir la valeur en jours (1-90), en heures (jusqu'à 23) ou même en valeur Lifetime. La valeur par défaut est 30 jours.  

      <Image align="center" alt="" src="https://files.readme.io/221a5489e91a15f1d9e4db9ab8f7cbff9e47dc1b50b0f7b43323096b26008870-30759261966225.png" />
10. Si vous disposez d'une extension de l'app Google Ads iOS :  
    pour obtenir des attributions à partir du lien de la publicité, accédez à l’onglet <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#attribution-link-tab">**Lien d’attribution**</Anchor>, créez un lien d’attribution AppsFlyer sur une plateforme unique et insérez-le dans l’extension de l’app Google Ads.  
    **Remarque :** pensez à ajouter un nom de campagne statique (obligatoire).  

    <Image align="center" alt="" src="https://files.readme.io/6b7513829fb3abbaab75942e3612760f39f6ae6502064eac1f31b0783a63e95b-30759221884561.png" />
11. Rendez-vous dans l'onglet **Coût**.
12. Activez **Obtenir les données de coût, de clic et d'impression**.
13. Cliquez sur le bouton **Connecter Google Ads** et connectez-vous à votre compte Google pour obtenir tous les coûts de votre campagne Google Ads sur AppsFlyer. <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-cost-and-ad-revenue">Plus de détails ici</Anchor>.
14. Cliquez sur **Enregistrer**.

<div id="stop" />

> ❗️ **Attention !**
>
> Vous DEVEZ **[passer par l'étape 4](/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory) pour que les installations de Google Ads s'affichent dans AppsFlyer.**
> Si vous souhaitez également mapper vos événements in-app à Google Ads, vous devez d’abord compléter [l'étape 3.](/docs/google-ads-adwords-integration-setup-for-advertisers#step-3-map-your-inapp-events-recommended)

</Accordion>

<div id="step-3-map-your-inapp-events-recommended" />

<Accordion title="Étape 3 : mappage de vos évènements in-app (recommandé)">

**(Tout membre lié au compte AppsFlyer)**

<Image align="center" alt="In-app_event_postbacks_en-us.png" src="https://files.readme.io/fbeef1b9d6f4462750d849878045d31b4a6614a9f36d20cd9c6f69d91a34f65a-30759221886609.png" />

1. Ouvrez l'onglet **Intégration** et faites défiler jusqu'à la section **Postbacks d'événement in-app**.

   <div id="note-1" />

   > 📘 **Remarque**
   >
   > Lorsque vous activez le mappage des événements in-app Google Ads pour une app **pour la première fois :**
   >
   > * L'événement **af\_app\_opened** est automatiquement défini et mappé sur **session\_start** (si ce n'est pas le cas, ajoutez-le manuellement).
   > * Dans la section **Pour les utilisateurs de**, vous devrez sélectionner **Toutes les sources média, organiques comprises** pour chaque événement afin de permettre à Google Ads de recevoir ces événements. Une fois l'intégration définie, vous pouvez modifier cette selection pour n'importe quel événement.

2. Activez **Postbacks d'événement in-app.**
3. Cliquez sur **Ajouter un événement** pour ajouter à la liste un SDK ou un événement de serveur à serveur.
4. Remplissez les paramètres suivants : 

| Nom du paramètre | Description |
| --- | --- |
| **Événement AppsFlyer** | Le nom de l'événement tel que reçu par AppsFlyer, soit depuis le SDK intégré à votre app, soit depuis les événements de serveur à serveur.<br />Astuce : vous ne voyez pas s'afficher un événement en particulier ?<ul><li>Activez l'évènement sur un appareil avec une installation non-organique et vérifiez à nouveau.</li><li>Saisissez-le dans **Événement AppsFlyer** puis cliquez sur **Créer événement personnalisé**. En savoir plus sur le <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#événements-personnalisés">mappage d'événements personnalisés.</Anchor></li></ul> |
| **mappé à l’événement partenaire** | Le nom ou l'ID unique de chaque événement, tel que défini du côté de Google Ads. Les différentes configurations du mapping sont :<ul><li>**Champ de texte :** obtenez l'ID d'événement correspondant auprès de Google Ads.</li><li>**Liste déroulante :** sélectionnez l’événement AppsFlyer prédéfini approprié.</li><li>**Tel quel** : envoyez les événements à l'état brut, sans mappage du nom.</li></ul> |
| **pour les utilisateurs de** | Sélectionnez l'option d'envoi pour l'événement :<ul><li>Ce partenaire uniquement envoie des postbacks uniquement lorsque cet événement est attribué à Google Ads.</li><li>**Toutes les sources média, y compris organiques** : envoie des postbacks pour les événements attribués à n'importe quel partenaire, et pour les événements organiques.</li></ul> |
| **Y compris** | <ul><li>**Pas de données (par défaut)** : envoie uniquement l'événement, sans sa valeur.</li><li>**Valeurs et revenus** : envoie tous les paramètres de l’événement, **y compris** la valeur du revenu (si présente dans l’événement).</li><li>**Valeurs sans revenus** : envoie tous les paramètres **à l'exception** de la valeur de revenu.</li></ul> |

5. Cliquez sur **Enregistrer l'intégration**.
6. Une fois l'intégration enregistrée, restez sur la page de configuration pour intégrer plus d'apps avec le partenaire.
   1. En haut à gauche, sous le nom du partenaire, cliquez sur le nom de l’app pour ouvrir la liste des apps.
   2. Sélectionnez une autre app dans la liste déroulante.
   3. Répétez les différentes étapes d’intégration pour l’app sélectionnée.

</Accordion>

<div id="step-4-measure-your-app-conversions-mandatory" />

<Accordion title="Étape 4 mesure de vos conversions d'app (obligatoire)">

<div id="note" />

<div id="important-1" />

> 🚧 **Important !**
>
> Pour que Google Ads puisse enregistrer vos nouvelles conversions, **vous devez lancer votre app et exécuter au moins une fois vos évènements in-app mappés**. Pour tester une app iOS, vous devez collecter l'IDFA afin de voir l'événement. Les conversions d'évènement peuvent mettre jusqu'à 6 heures avant d'apparaître dans la file d'attente. Une fois ajoutées, vous pouvez les importer. L'état des nouvelles conversions passe de « Aucune conversion récente » à « Enregistrement de la conversion en cours ».

Cette étape nécessite un **accès admin Google** au compte pour créer un ID de lien.

Suivez les étapes décrites dans la <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7382633?sjid=11699141105296914680-EU">documentation d'aide de Google Ads</Anchor>. Éléments à prendre en compte :

* À l’étape 7, cochez la case située à côté de **first\_open** pour TOUTES vos applications et pour chaque événement que vous souhaitez importer. Si l'identifiant de l'événement partenaire dans Google Ads a été modifié ou est étiqueté comme PERSONNALISÉ et que le nom de l'événement correspondant a été modifié dans AppsFlyer, vous devez réimporter les données.
* Vous pouvez désormais voir vos événements de conversion tiers dans la page **Conversions** > **Résumé**. Si un événement n'apparaît pas dans la liste, ou s'il a été supprimé de la liste des conversions Google Ads :
  1. Cliquez sur **Afficher toutes les actions de conversion**. Le filtre **Statut** s'affiche.
  2. Cliquez sur **Statut** et sélectionnez **Tout** pour afficher tous les événements, y compris les événements désactivés et supprimés.
* Vérifiez que votre réglage « inclure dans les conversions » correspond bien aux objectifs de votre campagne dans Google Ads. Pour plus d'informations, consultez votre représentant Google, ou parcourez la documentation Google disponible ici.

Bravo ! Vous mesurez maintenant les campagnes mobiles Google Ads avec AppsFlyer !

</Accordion>

</Accordion>


<div id="tip" />

> 👍 **Astuce**
>
> L'intégration de l'API Google Ads inclut automatiquement la fonctionnalité de remarketing de Google Ads. En effectuant cette intégration et en envoyant des évènements à Google Ads, vous pouvez créer des listes d'audiences de remarketing dans Google Ads sans aucune intégration supplémentaire.

<div id="granting-permissions-to-google-ads-team-members" />

## Octroyer des autorisations aux membres d'équipe Google Ads

Vous pouvez accorder à Google Ads <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">des autorisations d'accès à certaines données de votre compte.</Anchor> Pour ce faire, rendez-vous sur la page de configuration de Google Ads, dans l'onglet Autorisations pour chacune de vos applications.

Pour obtenir ces autorisations et accéder à votre application, votre représentant Google Ads doit être membre de l'équipe du compte partenaire de Google Ads sur Appsflyer.

En raison de ses exigences en matière de confidentialité, Google ne peut ajouter de nouveaux membres à son compte partenaire AppsFlyer que si un annonceur le demande explicitement.

Pour accorder l'accès à votre app à un membre d'équipe Google Ads, procédez comme suit :

1. Remplissez et envoyez <Anchor target="_blank" href="https://docs.google.com/forms/d/e/1FAIpQLSfJmwEPxy4bXw0mEsKfJ3D5dZmRZgHS3LCiyoEFsZRos0jWIQ/viewform">ce formulaire</Anchor> pour demander l'ajout de votre gestionnaire de compte au compte partenaire de Google sur AppsFlyer.
2. Attendez que Google Ads confirme que votre gestionnaire de compte GA a bien été ajouté.
3. Allez dans **Configuration** > **Intégrations actives** > **Google Ads** > **Autorisations** et ajoutez l'adresse e-mail de votre gestionnaire de compte à la liste des membres d'équipe.
4. Activez les autorisations que vous souhaitez accorder à votre gestionnaire de compte Google Ads.

Plus d'informations sur <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">l'octroi d'autorisations aux ad networks</Anchor>.

<div id="enabling-google-ads-attribution-for-agencies" />

## Activation de l'attribution de Google Ads pour les agences

AppsFlyer prend en charge les configurations d'agence avec Google Ads. Il est essentiel que l'annonceur et l'agence disposent de comptes Google Ads distincts pour permettre à AppsFlyer d'attribuer correctement les données. Pour plus d'informations, veuillez cliquer <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-agencies">ici</Anchor>.

<div id="running-with-multiple-google-ads-accounts" />

## Fonctionnement avec plusieurs comptes Google Ads

AppsFlyer prend en charge l'utilisation de plusieurs comptes Google Ads pour la même application. Pour ce faire, l'identifiant de lien est partagé dans Google Ads et les évènements sont importés dans chaque compte Google Ads.

Pour plus d'informations sur le partage de votre identifiant de lien Google Ads, cliquez <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001">ici</Anchor>.

<div id="ios-app-campaigns" />

## Campagnes d'apps iOS

**Remarque** : cette section s'applique aux campagnes d'applications pour les installations **et non aux** campagnes d'applications pour l'engagement.

Le 27 janvier 2021, <Anchor target="_blank" href="https://blog.google/products/ads-commerce/preparing-developers-and-advertisers-for-policy-updates/">Google a annoncé une mise à jour de sa politique</Anchor> en écho à la sortie d'iOS 14.

Depuis que l'ATT a été initié, les apps iOS de Google ne demandent pas l'accord ATT, les produits Google Ads ont donc <Anchor target="_blank" href="https://support.google.com/google-ads/answer/10417364">cessé d'utiliser</Anchor> les ID d'appareils (IDFA) qui relèvent de l'ATT.

Pour préserver le reporting et l'optimisation des campagnes, Google a élargi les conversions modélisées au trafic iOS 14 et +.

Attendu que les conversions modélisées ne reposent pas sur les ID d'appareils, à compter de la version iOS 14.5, la logique Google d'inventaire des campagnes d'installation d'apps iOS est la suivante :

* Le canal ou l'inventaire de recherche iOS ACI n'est pas attribué (conformément à la politique antérieure au 24 janvier 2020).
* Le canal ou l'inventaire YouTube IOS ACI n'est pas attribué, et comme l'app YouTube ne demande pas l'ATT, l'IDFA ne peut pas être utilisé.
* Le canal ou l'inventaire d'affichage IOS ACI ne peut être attribué que lorsqu'un ID d'appareil est renseigné, dans le cas où l'accord a été donné aussi bien pour les apps de l'annonceur que de l'éditeur.

<div id="note-2" />

<div id="using-deferred-deep-linking-in-app-campaigns" />

## Utilisation du deep linking différé dans les campagnes d'app

<Anchor target="_blank" href="https://support.google.com/google-ads/answer/9959794?hl=en&ref_topic=10011599">Les flux Google des campagnes d'app</Anchor> vous permettent d'offrir aux utilisateurs mobile une expérience fluide pour ce qui concerne le contenu spécifique.

Lorsqu'un utilisateur potentiel clique sur un flux, il est redirigé vers la page de l'app. Une fois que l'utilisateur a installé l'application et l'a lancée, le SDK fournit les détails sur le produit (ex : chaussures de course) via un deep link différé. Le développeur de l'app utilise ces données pour optimiser l'expérience des utilisateurs.

**Pour activer le deep linking différé avec Google Ads :**

1. Assurez-vous d'utiliser <Anchor target="_blank" href="/marketers/fr/docs/conversion-data-payloads-and-scenarios#réattribution-avec-deep-linking-différé">GCD</Anchor> pour recevoir le paramètre `af_dp`af\_dpaf\_dp dans le SDK AppsFlyer.
2. Dans Google, <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9958973?hl=en&ref_topic=10011599">paramétrez les flux</Anchor>.
3. Dans AppsFlyer, allez dans **Configuration** > **Intégrations actives**. Sélectionnez **Google Ads (Adwords)**.
4. Dans l'onglet **Intégration**, activez le **Deep linking différé avec Google Ads.**
5. Cliquez sur **Enregistrer l'intégration**.

<div id="google-ads-parameter-mapping" />

## Mappage des paramètres Google Ads

Le tableau ci-dessous indique le mappage des paramètres entre Google Ads et AppsFlyer. Notez que les annonceurs ne peuvent pas ajouter de paramètres personnalisés aux campagnes Google Ads.

<table><thead><tr><th><p><strong>Type de réseau</strong></p></th><th><strong>Recherche</strong></th><th><strong>Affichage</strong></th><th><strong>Youtube</strong></th></tr></thead><tbody><tr><td>Canal (af_channel)</td><td>Voir le tableau ci-dessous, <a href="./google-ads-adwords-integration-setup-for-advertisers#comment-remplir-le-paramètre-canal">Comment remplir le paramètre <kbd>Canal</kbd></a> </td></tr><tr><td>Campagne (c)</td><td>Oui</td><td>Oui</td><td>Oui</td></tr><tr><td><p>Identifiant de la campagne (af_c_id)</p></td><td>Oui</td><td>Oui</td><td>Oui</td></tr><tr><td>Ensemble de publicités (af_adset)<br/>Renseigné d'après le paramètre ad_group_name.<br/>Si ce paramètre est nul, AF définit af_adset avec ad_group_id.</td><td>Oui</td><td>Oui</td><td>Oui</td></tr><tr><td>ID d'adset (af_adset_id) renseigné d'après le paramètre Google ad_group_id</td><td>Oui</td><td>Oui</td><td>Oui</td></tr><tr><td><p>Publicité (af_ad)</p></td><td>N/A</td><td>N/A</td><td>N/A</td></tr><tr><td>Identifiant de publicité (af_ad_id)</td><td>N/A</td><td>N/A</td><td>N/A</td></tr><tr><td>Type de publicité (af_ad_type)</td><td>Oui\*</td><td>Oui\*</td><td>Oui\*</td></tr><tr><td>ID du site (af_siteid)</td><td>GoogleSearch/<br/>SearchPartners</td><td>N/A</td><td>YouTubeVideos/<br/>VideoPartners</td></tr><tr><td>Mots-clés</td><td>N/A</td><td>N/A</td><td>N/A</td></tr></tbody></table>

<div id="note-3" />

<div id="populate-the-channel-parameter" />

### Comment remplir le paramètre `Canal`

Google Ads n’envoie pas le paramètre `Canal (af_channel)`. AppsFlyer détermine comment renseigner ce paramètre pour les types de campagnes envoyés par Google Ads, en appliquant les règles suivantes :

<table><thead><tr><th colspan="2">Principe pour les types de campagnes <strong>ET</strong> types de réseaux :</th><th rowspan="2"> Paramètre <kbd>Canal</kbd> </th><th rowspan="2">Exemple</th></tr><tr><th>campaign_type</th><th>network_type</th></tr></thead><tbody><tr><td> <kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>Shopping</kbd>, ou <kbd>Hotel</kbd> </td><td><p>Tous les types de réseaux</p></td><td><kbd>campaign_type_network_type</kbd></td><td>canal = <kbd>ACI_Search</kbd> </td></tr><tr><td><p><strong>Non :</strong></p><kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>Shopping</kbd>, ou <kbd>Hotel</kbd> </td><td><kbd>Affichage</kbd></td><td><kbd>network_subtype</kbd></td><td>canal = <kbd>mGDN</kbd> </td></tr><tr><td><p><strong>Non :</strong></p><kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>Shopping</kbd>, ou <kbd>Hotel</kbd> </td><td><p><strong>Non :</strong></p><kbd>Affichage</kbd> </td><td><kbd>network_type</kbd></td><td>canal = <kbd>Search</kbd> </td></tr></tbody></table>

* Pour plus d'informations sur les types de publicités que peuvent contenir les réponses de Google, cliquez <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">ici</Anchor>.

<div id="campaign-type-app-campaigns" />

### Type de campagne : campagnes d'app

<div id="changes-to-campaign-names-by-google-ads" />

#### Modifications apportées aux noms de campagne par Google Ads

| Jusqu'au 15 février 2021 | Depuis le 23 février 2021 |
| --- | --- |
| UAC | ACI |
| UACE | ACE |
| UACPre | ACPRE |

**Remarque :** le type de nom de campagne est défini selon la date du clic ou de l'impression, et non selon la date d'installation.

<div id="engaged-view-parameter-in-raw-data-reports" />

### Le paramètre des vues engagées dans les rapports de données brutes

Une vue engagée correspond à l'impression d'un utilisateur sur une publicité vidéo pour une durée de plus de 10 secondes. L'action compte comme un clic. Pour Android, elle s'affiche dans les rapports de données brutes, au niveau du paramètre sub param 5.  
Ce paramètre s'affiche si la vue engagée s'est produite dans la fenêtre d'attribution de clic définie dans AppsFlyer, qui dure au maximum 3 jours.

<div id="send-complex-in-app-events-to-google-ads" />

<div id="important-2" />

> 🚧 **Important !**
>
> * Google est un SRN (Self Reporting Network : réseau auto-reporting). Pour plus d'informations sur le fonctionnement du flux d'attribution pour ces réseaux, cliquez <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns">ici</Anchor>.
> * AppsFlyer peut présenter toutes les informations de campagne fournies par Google. Le type de campagne (Recherche, Vidéo, Affichage) et les informations associées sont déterminés par Google. Pour plus d'informations, veuillez cliquer <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">ici</Anchor>.

<div id="optimize-google-ads-campaigns-for-conversions-without-device-id" />

## Optimiser les campagnes Google Ads pour les conversions sans ID d'appareil

Depuis IOS 14.5 et Android 12, Google Ads a introduit différents identifiants. Ces identifiants permettent de déterminer l'attribution des conversions sans nécessiter l'ID d'appareil :

| Identifiant | Disponible depuis | Source | Système d'exploitation | Utilisé pour | Granularité des données |
| --- | --- | --- | --- | --- | --- |
| gclid | Décembre 2021 | Référent Google Play | Android | Installations | Niveau utilisateur |
| gclid | Décembre 2021 | URL de deep link | Android + iOS | Réengagements | Niveau utilisateur |
| gbraid | Mars 2021 | URL de deep link | iOS | Réengagements | Données agrégées |

Lorsque AppsFlyer reçoit ces identifiants et les transfère via postback Google Ads, Google Ads peut réclamer les conversions liées à ces identifiants. AppsFlyer reçoit la réclamation et analyse les paramètres pour attribuer et associer les événements LTV.  
**Aucune action n'est requise du côté annonceur pour activer la réception de ces paramètres.**

<div id="google-probabilistic-attribution-icm-traits-and-limitations" />

<div id="advertising-without-the-firebase-sdk" />

<div id="data-visibility-by-operating-system" />

### Visibilité des données selon le système d'exploitation

**Apps Android :**

Dans AppsFlyer et Google Ads, les annonceurs peuvent recevoir l'ensemble des données de campagne concernant le trafic sans utiliser l'ID d'appareil (valable pour les installations et les réengagements).

**Apps iOS :**

Dans Google Ads, les annonceurs peuvent recevoir l'ensemble des données de campagne concernant le trafic sans utiliser l'ID d'appareil (valable pour l'activité de réengagement).

<div id="h_01HDP0SBEE75MAT4A4S9E7Y7FF" />

> 📄 **À consulter également**
>
> * Pour iOS 14, voir l'<Anchor target="_blank" href="/marketers/fr/docs/get-skan-postback-data-from-google-ads">interopérabilité entre Google Ads SKAdNetwork et AppsFlyer</Anchor>.

<div data-zendesk-anchors="h_01HMEH8VW3PYCZ6GC4T5BYBS3V=important- using-google-ads=utilisation-de-google-ads h_01HACTC1H575PKYKRH4T4NVKH1=utilisation-de-google-ads configuring-google-ads-attribution-for-advertisers=configuration-de-lattribution-de-google-ads-pour-les-annonceurs h_01HACTC1H5MANBCRWYQPNW5CC2=configuration-de-lattribution-de-google-ads-pour-les-annonceurs h_01HACTC1H5XXGREE80GFHGZY7N=remarque h_01HACTC1H5XEJEPMZ4C7GP8GG6=step-1-create-the-google-ads-link-id-mandatory h_01HACTC1H5HEP9759J2PCPPZSW=step-2-set-up-google-ads-on-appsflyer-mandatory h_01HACTC1H5R995RXYRFQBFHRF1=important--1 h_01HACTC1H5EFJKV6AXNSTNFZA4=attention- h_01HACTC1H50DDS3WCZ9DCHKN0P=step-3-map-your-inapp-events-recommended h_01HACTC1H58WHJDBN2DRQAZKGB=remarque-1 h_01HACTC1H5GV04KFM29NCCK8J2=step-4-measure-your-app-conversions-mandatory h_01HSX7TJC7PQ0ATM1J86Z4HMYJ=important--2 h_01HACTC1H5Z3XXS1MGBS4WYJBV=astuce granting-permissions-to-google-ads-team-members=octroyer-des-autorisations-aux-membres-d%C3%A9quipe-google-ads h_01HACTC1H5PAY95M4H1A6WTSEF=octroyer-des-autorisations-aux-membres-d%C3%A9quipe-google-ads enabling-google-ads-attribution-for-agencies=activation-de-lattribution-de-google-ads-pour-les-agences h_01HACTC1H5QE93EAYYVVDQV2WC=activation-de-lattribution-de-google-ads-pour-les-agences running-with-multiple-google-ads-accounts=fonctionnement-avec-plusieurs-comptes-google-ads h_01HACTC1H5Z8B15RHQ75HVV2RP=fonctionnement-avec-plusieurs-comptes-google-ads ios-app-campaigns=campagnes-dapps-ios h_01HACTC1H5X567H6A8M3FWCTAN=campagnes-dapps-ios using-deferred-deep-linking-in-app-campaigns=utilisation-du-deep-linking-diff%C3%A9r%C3%A9-dans-les-campagnes-dapp h_01HACTC1H57HJZNAGDKSQD6MVC=utilisation-du-deep-linking-diff%C3%A9r%C3%A9-dans-les-campagnes-dapp google-ads-parameter-mapping=mappage-des-param%C3%A8tres-google-ads h_01HACTC1H6P1A2E160Z6GAGZZS=mappage-des-param%C3%A8tres-google-ads how-to-populate-the-channel-parameter=comment-remplir-le-param%C3%A8tre-canal h_01HACTC1H6TPTDDFSMPQ9YVMDY=comment-remplir-le-param%C3%A8tre-canal campaign-type-app-campaigns=type-de-campagne-campagnes-dapp h_01HACTC1H6CEGD2E3HXHWFWBRB=type-de-campagne-campagnes-dapp changes-to-campaign-names-by-google-ads=modifications-apport%C3%A9es-aux-noms-de-campagne-par-google-ads h_01HACTC1H6A028HKVXJ66MCF6M=modifications-apport%C3%A9es-aux-noms-de-campagne-par-google-ads engaged-view-parameter-in-raw-data-reports=le-param%C3%A8tre-des-vues-engag%C3%A9es-dans-les-rapports-de-donn%C3%A9es-brutes h_01HACTC1H6Q6WCTK4Z9RGV6PA4=le-param%C3%A8tre-des-vues-engag%C3%A9es-dans-les-rapports-de-donn%C3%A9es-brutes h_01HACTC1H62HC36C08ZBFZ05XS=important--3 optimize-google-ads-campaigns-for-conversions-without-device-id=optimiser-les-campagnes-google-ads-pour-les-conversions-sans-id-dappareil h_01HACTC1H6EFDVN9N89Y17HDFR=optimiser-les-campagnes-google-ads-pour-les-conversions-sans-id-dappareil data-visibility-by-operating-system=visibilit%C3%A9-des-donn%C3%A9es-selon-le-syst%C3%A8me-dexploitation h_01HACTC1H6WZNMVJK479M5KJYF=visibilit%C3%A9-des-donn%C3%A9es-selon-le-syst%C3%A8me-dexploitation h_01HDP0SBEE75MAT4A4S9E7Y7FF=%C3%A0-consulter-%C3%A9galement" />
