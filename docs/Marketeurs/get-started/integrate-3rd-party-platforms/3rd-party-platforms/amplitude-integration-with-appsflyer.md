---
title: Intégration d'Amplitude avec AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Amplitude
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2016-08-02T05:18:03Z'
  edited_at: '2023-10-08T11:40:02Z'
  id: 211200306
  locale: fr
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/fr/articles/211200306
---
> **En bref :** Amplitude, partenaire intégré d'AppsFlyer, fournit des analyses de produits qui permettent aux entreprises mobile et Web de mieux comprendre le comportement des utilisateurs. Les équipes produit, marketing et croissance utilisent Amplitude pour découvrir et partager des informations sur l'engagement des utilisateurs, la fidélisation et le chiffre d'affaires.

> 🚧 **Important !**
>
> <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions#restrictions-des-sources-média">Certaines sources média</Anchor> limitent le partage des données avec les tiers. Par conséquent, les postbacks des événements limités ne seront pas envoyés à ce partenaire, quelle que soit la sélection configurée pour l'envoi de postbacks.

## Configuration d'Amplitude

La configuration se fait depuis la page **Intégrations actives**, mais pour trouver le partenaire vous devez d'abord vous rendre dans le <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations">marketplace</Anchor>.

> 📘 **Note**
>
> Avant de configurer une attribution, vous devez <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations#contacter-le-partenaire">contacter le partenaire</Anchor> et ouvrir un compte chez lui.

**Pour activer l'intégration :**

1. Dans le menu situé en haut de n'importe quelle page AppsFlyer, cliquez sur **Marketplace**.
2. Trouvez le partenaire voulu et sélectionnez-le.
3. Cliquez sur **Configurer l'intégration**. Vous êtes alors dirigé vers la page de configuration de l'intégration.
4. Dans l'onglet **Integration** , sélectionnez l'app à intégrer et cochez **Activer le partenaire**.  
   **Remarque :** La case doit rester <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">cochée (option activée)</Anchor> tant que vous travaillez avec le partenaire.
5. Terminez la configuration en suivant les onglets requis, cf description ci-dessous.

Pour obtenir une description détaillée de l'en-tête de la fenêtre de configuration du partenaire, cliquez <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">ici</Anchor>.

<div id="integration-tab" />

<Accordion title="Onglet Intégration">

L'onglet Intégration est divisé en différentes sections, comme décrit ci-dessous.

### Activation du partenaire

Lors de votre **première visite**, vous devrez activer l'option **Activer le partenaire** pour permettre la configuration des paramètres de l'onglet d'intégration. L'option doit rester activée tant que vous travaillez avec le partenaire.  
En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">l'activation d'un partenaire.</Anchor>

### Paramètres généraux

#### Partage avancé des données

Pour partager des informations d'installation supplémentaires avec Amplitude, activez le **partage avancé des données.** Lorsque l'option est activée, Amplitude reçoit les données d'installation suivantes (sans les données des événements in-app) mappées à la propriété d'Amplitude :

| Propriété d'Amplitude | Point de données AppsFlyer |
| --- | --- |
| sub\_publisher | af\_siteid |
| network\_name | pid |
| adgroup\_name | af\_adset |
| creative\_name | af\_ad\_id |
| installed\_at | install\_timestamp |
| search\_term | af\_keywords |
| canal | af\_channel |
| user\_id | af\_customer\_user\_id |
| af\_sub1 | af\_sub1 |
| af\_sub2 | af\_sub2 |
| app\_version | app\_version |

#### Centre de données UE Amplitude

Lorsque **Centre de données UE Amplitude** est désactivé, les postbacks d'installation sont envoyés au centre de données des États-Unis.  
Pour envoyer les postbacks d'installation au centre de données européen d'Amplitude, activez le centre de données UE d'Amplitude.

#### Clé API

Amplitude se connecte à AppsFlyer via une clé API unique. Si vous ne l'avez pas encore, vous devez la récupérer auprès d'Amplitude pour poursuivre l'intégration ou suivre les étapes ci-dessous.

<span id="obtaining-the-api-key-from-amplitude"></span>**Obtention de la clé API auprès d'Amplitude**

**Remarque** : Seuls les utilisateurs ayant le rôle Admin ou manager sur Amplitude peuvent accéder à la clé API.

1. Connectez-vous à votre compte Amplitude.
2. En haut à droite de la page, cliquez sur l'icône des paramètres > **Paramètres de l'organisation**.  

   <Image alt="Amplitude" src="https://files.readme.io/214df773c045239924b65a4a1e6b0a1957f6b7ea09e225af80d83ffa0a469c26-16258070772625.png" width="240px" />
3. Cliquez sur **Projets** et sélectionnez le projet à partir duquel vous souhaitez envoyer des données à AppsFlyer.   

   ![amplitude](https://files.readme.io/eaf158e4505f47f8da0fdae4f97be773ab32910352b50cab5ca5d4de3e8782ac-16335170399505.png)
4. Dans l'onglet **Projet**, copiez votre clé API.  

   <Image alt="Amplitude" src="https://files.readme.io/cf65648a9a8c122febe2b36fd4bd0b9f7f436cac49cfeec7f41870f614a16c6c-16258070773649.png" width="648px" />
5. Procédez à la configuration d'Amplitude dans le tableau de bord d'AppsFlyer.

### Postbacks par défaut

AppsFlyer envoie des postbacks automatiques pour les installations utilisateurs d'Amplitude uniquement lorsqu'elles sont attribuées à Amplitude.

### Paramètres des événements in-app

* Saisissez la clé API.
* Lorsque **Centre de données UE Amplitude** est désactivé, les postbacks d'évènements in-app sont envoyés au centre de données américain.  
  **Pour envoyer les postbacks d'évènements in-app au centre de données européen d'Amplitude, activez le centre de données européen d'Amplitude.**

Une fois la configuration sauvegardée, AppsFlyer envoie les données suivantes à Amplitude :

* ID d'appareil (IDFV/ID Google Advertising)
* Source média
* Nom de la campagne

L'envoi de l'IDFA pour les appareils iOS est soumis au <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">consentement ATT de l'utilisateur et aux paramètres de confidentialité avancés</Anchor>.

### Postback d'évènements in-app

<Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#g">Configurer l'envoi de postbacks d'événements in-app</Anchor> à Amplitude.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Onglet Lien d'attribution">

Les liens d'attribution ne sont pas disponibles pour Amplitude.

</Accordion>

<div id="cost-tab" />

<Accordion title="Onglet Coût">

Les données relatives aux coûts ne sont pas prises en charge dans le cadre de l'intégration avec ce partenaire.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Onglet Revenus publicitaires">

Les revenus publicitaires ne sont pas pris en charge dans l'intégration avec ce partenaire.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Onglet Autorisations">

Les autorisations ne sont pas disponibles pour Amplitude.

</Accordion>

## Visualisation des données d'attribution dans la console Amplitude

Les données d'attribution envoyées par AppsFlyer à Amplitude s'affichent dans vos tableaux de bord sous forme d'événements et de propriétés préfixés par **[AppsFlyer]** :

![amplitude-properties.png](https://files.readme.io/bf52831ea6060172ce251136f47962ffb7f1ec9ffce13b9e35c614c4178e77f1-360009623597.png)

> 🚧 **Important !**
>
> * Pour éviter les problèmes de correspondance entre l'installation et les événements in-app, activez l'**API HTTP d'Amplitude** pour les postbacks d'installation. Si vous ne le faites pas, lorsque le premier événement in-app suivant une installation se produit 72 heures après celle-ci, Amplitude ne fait pas correspondre l'installation aux événements in-app suivants. Dans ce cas, Amplitude ne tient pas compte de l'événement d'installation mais affiche les événements in-app survenus 72 heures après.
> * Dans certains cas, Amplitude affiche des données provenant d'AppsFlyer ave le statut « Bloqué ». Si vous ne voyez pas les données AppsFlyer dans Amplitude, vérifiez si elles sont définies comme un événement bloqué.![amplitude-blocked-data.png](https://support.appsflyer.com/hc/article_attachments/4409532783889)

<div data-zendesk-anchors="01H8KPA9JJDP2945TQJT1Z3EY2=important- setting-up-amplitude=configuration-damplitude 01H8KPA9JJXHMEYD8HD9DKK6D1=configuration-damplitude 01H8KPA9JJG0MNK2EK75XVZBHX=note 01H8KPA9JK6XTFR0XW91XZB5XR=integration-tab activate-partner=activation-du-partenaire 01H8KPA9JKDRA680Y0WPZ172EM=activation-du-partenaire general-settings=param%C3%A8tres-g%C3%A9n%C3%A9raux 01H8KPA9JKF4VCA4S22SYT40WT=param%C3%A8tres-g%C3%A9n%C3%A9raux advanced-data-sharing=partage-avanc%C3%A9-des-donn%C3%A9es 01H8KPA9JKJ2XN1AEPV74QVJYZ=partage-avanc%C3%A9-des-donn%C3%A9es amplitude-data-center=centre-de-donn%C3%A9es-ue-amplitude 01H8KPA9JKP0T0FDND97VA23EY=centre-de-donn%C3%A9es-ue-amplitude api-key=cl%C3%A9-api 01H8KPA9JKDYDPDGRXZSH2BAV8=cl%C3%A9-api 01H8KPA9JK510YKV47816DT7E7=obtaining-the-api-key-from-amplitude default-postbacks=postbacks-par-d%C3%A9faut 01H8KRBGYQ973CT3H8GHZ8R0BH=postbacks-par-d%C3%A9faut inapp-event-settings=param%C3%A8tres-des-%C3%A9v%C3%A9nements-in-app 01H8KPA9JKM4S79160BEYN3B6V=param%C3%A8tres-des-%C3%A9v%C3%A9nements-in-app inapp-event-postbacks=postback-d%C3%A9v%C3%A8nements-in-app 01H8KSQ76XE9Z191P1RMANF6EQ=postback-d%C3%A9v%C3%A8nements-in-app 01H8KPA9JK4D6XX55Q55TBF4QN=attribution-link-tab 01H8KPA9JKK04NNDZA0XTSSWM5=cost-tab 01H8KPA9JK6X04T661D6YBHTVC=ad-revenue-tab 01H8KPA9JKG1VQJJBNFM6Q985X=permissions-tab viewing-attribution-data-in-the-amplitude-console=visualisation-des-donn%C3%A9es-dattribution-dans-la-console-amplitude 01H8KPA9JK75TA0H8T4P65BMSE=visualisation-des-donn%C3%A9es-dattribution-dans-la-console-amplitude 01H8KPA9JK2B4MR26GJZEZJSVT=important--1" />
