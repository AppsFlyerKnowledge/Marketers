---
title: Configuration de l'intégration de X Ads (anciennement Twitter Ads)
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
  created_at: '2021-11-09T09:33:40Z'
  edited_at: '2023-11-24T14:12:09Z'
  id: 4410472471825
  locale: fr
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/fr/articles/4410472471825
---
> **En bref :** intégrez votre compte X Ads dans AppsFlyer pour afficher les données d'attribution de l'ensemble de vos campagnes X Ads.

<div id="connecting-your-x-ads-account-to-appsflyer" />

## Connecter votre compte X Ads à AppsFlyer

<Embed title="Configuration de l'intégration de X Ads (anciennement Twitter Ads)" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/a65pnqoyxw" providerUrl="https://fast.wistia.com" />


> 📘 **Avant de commencer**
>
> Assurez-vous d'avoir <Anchor target="_blank" href="https://business.twitter.com/en/help/account-setup/billing-basics.html">ajouté un mode de paiement</Anchor> à votre compte X Ads. Sinon, vous ne pourrez pas activer l'intégration du partenaire dans AppsFlyer.

1. Connectez-vous à votre compte X Ads sur <Anchor target="_blank" href="https://ads.twitter.com">ads.twitter.com</Anchor>  
   Si vous n'êtes pas automatiquement dirigé vers la page Ads, cliquez sur le bouton Ads dans le coin supérieur gauche.
2. Lorsqu'il vous est demandé de sélectionner une campagne **simple (NOUVELLE)** ou **avancée**, sélectionnez **avancée**.
3. Dans **Objectif de la campagne**, sélectionnez **Installations** ou **Réengagements d'applications**, puis cliquez sur **Suivant.**  

   ![twitter-campaign-objective.png](https://files.readme.io/d91bd357dea4878f098086a573191f64c2d1a38af8a6a809c6de7c468e04e043-6148255768337.png)
4. Sélectionnez votre application, puis cliquez sur le lien du **partenaire de mesure mobile** .
5. Sur la page de **suivi des conversions** , cliquez sur **Aller à AppsFlyer**.   

   ![twitter-mmp-selection.png](https://files.readme.io/ebe8e97971c01e0d87c694d2ca1fcc996abf608309d96badcbcda2713ab80d3e-6148393350033.png)
6. Une notification s'affiche pour vous informer que vous êtes sur le point de quitter X Ads pour accéder au site d'AppsFlyer. Cliquez sur **Aller sur AppsFlyer** et connectez-vous à votre tableau de bord.  

   <Image alt="twitter-go-to-appsflyer.png" src="https://support.appsflyer.com/hc/article_attachments/4411046208401" width="576px" />
7. Dans AppsFlyer, allez dans **Configuration** et ouvrez **Marketplace des partenaires**.
8. Recherchez et sélectionnez **X Ads**.
9. Dans l'onglet **Integration** , acceptez les conditions générales de X Ads concernant l'enregistrement des conversions des apps mobile (MACT), puis cliquez sur **Enregistrer l'intégration**.
10. Enclenchez **Activer le partenaire**, puis cliquez sur **Se connecter avec X Ads**.
11. Autorisez AppsFlyer à utiliser votre compte X Ads en cliquant sur **Autoriser l'application**.   

    [<Image alt="" src="https://support.appsflyer.com/hc/en-us/article_attachments/4411037924497/Twitter_Ads_6.png" width="476px" />](https://support.appsflyer.com/hc/fr/article_attachments/4411037924497/Twitter_Ads_6.png)
12. Enclenchez à nouveau l'option **Activer le partenaire** pour afficher les paramètres de l'onglet **Intégration** et activer l'attribution.  
    **Remarque :** La case doit rester cochée (option activée) tant que vous travaillez avec le partenaire. En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">l'activation d'un partenaire.</Anchor>
13. Sélectionnez vos comptes X Ads pour les activer, puis cliquez sur **Enregistrer et fermer**.  

    ![twitter_account_name.png](https://support.appsflyer.com/hc/article_attachments/4411046818193)


<div id="x-ads-attribution-setup" />

## Configuration de l'attribution X Ads

Pour obtenir une description détaillée de l'en-tête de page de configuration du partenaire, cliquez <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner">ici</Anchor>.

<div id="integration-tab" />

<Accordion title="Onglet Intégration">

L'**onglet Intégration** est divisé en différentes sections, comme indiqué ci-dessous. Le <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">partenaire doit être activé</Anchor> lors de sa première visite pour permettre sa configuration.

<div id="ad-account-connected" />

### Compte publicitaire connecté

Sélectionnez les comptes pour activer l'attribution.

![Twitter_msc_new_4.png](https://files.readme.io/c64dd5ddc51f35ce195c689b3d14ec4ed4010133662096926f4e8c45e48d60c4-4411049509137.png)

<div id="click-through-attribution" />

### Attribution post clic

Utilisez le curseur pour définir la **durée maximale entre le clic et l'installation**. Seules les installations (premiers lancements) qui ont lieu dans la fenêtre d'attribution peuvent être attribuées à X Ads.

Vous pouvez personnaliser cette valeur en heures (de 1 à 23) ou en jours (de 1 à 30). Afin de garantir la correspondance avec X Ads, nous vous recommandons de définir la durée de la fenêtre d'attribution sur 14 jours.

![Twitter_msc_new_6.png](https://files.readme.io/39c3e080cf2fff3b7d9b3e2cf694fc439cd447a263b113ecfc6730a38f653283-4411047369361.png)

<div id="view-through-attribution-lookback-window" />

### Fenêtre rétrospective d'attribution post vue

Ce curseur vous permet de définir le **délai maximum entre l'impression et l'installation**. Seules les installations (premiers lancements) qui ont lieu dans cette fenêtre d'attribution, suite à une impression de publicité, sont attribuées à X Ads, à condition qu'il n'y ait pas eu d'autre clic pertinent sur la publicité.

Vous pouvez personnaliser cette valeur en heures (1 à 23) ou en jours (1 à 7). Nous recommandons de définir la durée de la fenêtre d'attribution sur 1 jour, afin de garantir la correspondance avec X Ads.

![Twitter_msc_new_7.png](https://files.readme.io/4f64c994b0cffec692ab99345e539caa4ef07b8f4a439851f18af3aada6ab473-4411049638033.png)

<div id="re-engagement-settings" />

### Paramètres de réengagement

L'attribution de retargeting de X Ads inclut uniquement les conversions de réengagement.

Activez l'option **Attribution de réengagement** pour démarrer l'attribution des réengagements pour X Ads.

<div id="re-engagement-click-through-lookback-window" />

#### Fenêtre rétrospective de réengagement post clic

Définissez la durée de la **Fenêtre rétrospective de réengagement post clic** (la période maximale après le clic sur une publicité pendant laquelle un utilisateur reciblé peut être attribué à celle-ci). Vous pouvez définir la valeur en heures (jusqu'à 23) ou en jours (1-30).

![twitter-reengagement-activate.png](https://files.readme.io/9272c626eceeb8457584d2f1bd1d2adb16f9022994a2efa22eeaeb5b584e2149-4411049796625.png)

<div id="re-engagement-view-through-lookback-window" />

#### Fenêtre rétrospective de réengagement post vue

Pour commencer à attribuer des impressions d'annonces de retargeting, activez **Attribution de réengagement post vue**.

Définissez la durée de la **Fenêtre rétrospective de réengagement post vue** (la période maximale pendant laquelle une publicité est vue et pendant laquelle un utilisateur reciblé peut être attribué à la publicité). Vous pouvez définir la valeur en heures (jusqu'à 23) ou en jours (1-7) :

![twitter-reengagement-view-through.png](https://files.readme.io/6d4b80bbe1b953e5df5a6420d71ead781342c616e864e4d1b4d71c68fa9d17fa-4411038679569.png)

<div id="re-engagement-window" />

#### Fenêtre de réengagement

Définissez la durée de la **Fenêtre de réengagement** (période au cours de laquelle les événements in-app de l'utilisateur sont attribués à la source média de retargeting). Vous pouvez définir la valeur en jours (1-90), en heures (jusqu'à 23) ou même en valeur vie :

![Twitter-reengagement-window.png](https://files.readme.io/de80d79c777fc97caa0a28a342657475f0a05c14e30b1f96d24898a4638e1af8-4411047581201.png)

<div id="in-app-event-postback-settings" />

### Paramètres de postback d'évènements in-app

Dans cette section, vous pouvez mapper vos événements AppsFlyer avec vos partenaires via des postbacks.

[![In-app_event_postbacks_en-us.png](https://files.readme.io/b215324955412d3a6fc0f719ad54560c25b537a4d1b87475d23c91fbf4262632-7900234463121.png)](https://files.readme.io/b215324955412d3a6fc0f719ad54560c25b537a4d1b87475d23c91fbf4262632-7900234463121.png)

**Pour configurer les postbacks d'événement in-app :**

1. Définissez **l'ID du partenaire** (si nécessaire).
2. Activez **Postbacks d'événements in-app.**
3. Cliquez sur **Ajouter un événement** pour ajouter à la liste un SDK ou un événement de serveur à serveur.
4. Complétez les paramètres requis selon le tableau ci-dessous.  

| Paramètre | Description |
| --- | --- |
| **Événement AppsFlyer** | Le nom de l'événement tel que reçu par AppsFlyer, soit depuis le SDK intégré à votre app, soit depuis les événements de serveur à serveur.<br />**Astuce** : vous ne voyez pas s'afficher un événement en particulier ?<ul><li>Assurez-vous d'activer l'évènement sur un appareil avec une installation non-organique et revérifiez.</li><li>Saisissez-le dans **Événement AppsFlyer** puis cliquez sur **Créer événement personnalisé**. En savoir plus sur le <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#événements-personnalisés">mappage d'événements personnalisés.</Anchor></li></ul> |
| **mappé à l’événement partenaire** | Le nom ou l'identifiant unique de chaque événement, tel que défini du côté du partenaire. Les différentes <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#le-mappage-dévénement">configurations de mappage</Anchor> sont :<ul><li>**Champ de texte :** obtenez l'ID d'événement correspondant auprès du partenaire.</li><li>**Liste déroulante :** sélectionnez l’événement AppsFlyer prédéfini approprié.</li><li>**Tel quel** : envoyez les événements à l'état brut, sans mappage du nom.</li></ul> |
| **pour les utilisateurs de** | Sélectionnez l'option d'envoi pour l'événement :<br /><br /><br /><br />**<span id="h_01HDJVBAEZATGM580CNC7BCVTN"></span>Remarque**<br />Pour que X Ads reçoive des postbacks attribués à une agence, vous devez sélectionner **Toutes les sources média, y compris organiques**. Dans le cas contraire, X Ads ne recevra pas ces postbacks.<ul><li>**Ce partenaire uniquement** : envoie des postbacks exclusivement lorsque cet événement est attribué à ce partenaire.</li><li>**Toutes les sources média, y compris organiques** : envoie un postback pour tout événement attribué à n'importe quel partenaire ou événement organique.</li></ul> |
| **Y compris** | <ul><li>**Aucune donnée (par défaut)** : envoie uniquement l'événement en lui-même mais sans sa valeur.</li><li>**Valeurs et revenus** : envoie tous les paramètres de l’événement, **y compris** la valeur de revenu (si présente dans l’événement).</li><li>**Avec valeurs et sans revenu** : envoie tous les paramètres **à l'exception** de la valeur de revenu.</li></ul> |

5. [Facultatif] Cliquez sur <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/d84715dd43041f10684d42e4fe56fd4f76aa4c38fbf9df227c8f8f5610c4f859-19616850611857.png" width="30px" /> pour définir les conditions d'envoi de certains événements in-app au partenaire.  
   En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#postbacks-conditionnels-dévénements-in-app">les postbacks d'événement in-app conditionnels</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Onglet Lien d'attribution">

X Ads n'utilise pas les liens d'attribution à des fins d'attribution.

<div id="note-2" />

> 📘 **Note**
>
> Cet onglet n'est pas fonctionnel pour les <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns">réseaux auto-reporting (SRN)</Anchor> tels que Meta ads, Apple Search Ads, Adwords, X Ads, etc., car ils n'utilisent pas de liens d'attribution externes.

</Accordion>

<div id="cost-tab" />

<Accordion title="Onglet Coût">

L'intégration des coûts fournit les données agrégées suivantes :

* Données sur les coûts pour vos campagnes, vos adsets, vos publicités et vos canaux. Consultez le <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tableau d'intégration des coûts du réseau publicitaire</Anchor> pour obtenir plus d'infos sur les dimensions, les métriques et les fonctionnalités prises en charge.**Remarque :** les données de coût nécessitent un abonnement <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>.
* Données sur les clics, les impressions et les données enrichies (mots-clés, noms de campagne et adsets).

**Pour activer l'API de coûts :**

* Suivez  <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">ces instructions d'intégration</Anchor>.

<Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Affichez le statut de votre API de coûts</Anchor> et la dernière fois qu'AppsFlyer a réussi à extraire des données de coûts correspondantes, soit dans le tableau de bord du statut d'intégration des coûts (et des revenus publicitaires), soit dans le tableau de bord du réseau publicitaire individuel.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Onglet Revenus publicitaires">

L'intégration des revenus publicitaires n'est pas disponible pour X Ads. Pour recevoir des données des revenus publicitaires, vous devez intégrer MoPub.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Onglet Autorisations">

Dans cet onglet, vous pouvez sélectionner les autorisations à accorder à X Ads, que le partenaire agisse en tant que ad network, agence ou même les deux. Notez que même si l'attribution est désactivée pour X Ads l'onglet des autorisations est actif et vous pouvez accorder le contrôle à X Ads.

Utilisez ces boutons pour autoriser le réseau publicitaire à gérer sa propre configuration pour votre application :

<div id="ad-network-permissions" />

### Autorisations pour le réseau publicitaire

* **Autoriser la configuration de l'intégration** : permet au partenaire de configurer l'onglet d'intégration (à l'exception des postbacks d'événement in-app)
* **Autoriser la configuration des postbacks d'événement in-app** : permettre au partenaire de configurer l'auto-mappage des postbacks d'événements in-app dans l'onglet Intégration
* **Autoriser l'accès à votre rapport de rétention** : valable uniquement pour les données de rétention du partenaire
* **Autoriser l'accès aux données agrégées de vos utilisateurs fidèles** : valable uniquement pour les données des utilisateurs fidèles du partenaire
* **Autoriser l'accès à vos données agrégées d'évènements in-app** : uniquement pour les données d'évènements in-app du partenaire
* **Autoriser l'accès à vos données agrégées de revenus** : valable uniquement pour les données de revenus attribuées au partenaire
* **Autoriser l'accès à votre tableau de bord Protect360** : valable uniquement pour les données Protect360 du partenaire, attendu que cette fonctionnalité est activée chez l'annonceur

En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">l'octroi d'autorisations à un réseau publicitaire.</Anchor>

<div id="agency-permissions" />

### Autorisations pour l'agence

En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#autorisations-pour-lagence">l'octroi d'autorisations à une agence.</Anchor>

</Accordion>

## Vidéo de configuration avancée de X Ads

<Embed title="Configuration de l'intégration de X Ads (anciennement Twitter Ads)" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/3ypfld8enr" providerUrl="https://fast.wistia.com" />


## Restrictions

X Ads ne prend pas en charge l'attribution MMP pour les campagnes Pre-roll.

<div data-zendesk-anchors="connecting-your-twitter-ads-account-to-appsflyer=connecter-votre-compte-x-ads-%C3%A0-appsflyer h_01HDJVCRYQESA17XZ83GS81YZ3=connecter-votre-compte-x-ads-%C3%A0-appsflyer h_01HDJVBAEZXA0WJ94JYMK84MAX=avant-de-commencer twitter-ads-attribution-setup=configuration-de-lattribution-x-ads h_01HDJVBAEZ5W3JH1BN7WXJ08P6=configuration-de-lattribution-x-ads h_01HDJVBAEZSFKRXAKQJP58N550=integration-tab ad-account-connected=compte-publicitaire-connect%C3%A9 h_01HDJVBAEZD89BSGHQTPR84HSC=compte-publicitaire-connect%C3%A9 clickthrough-attribution=attribution-post-clic h_01HDJVBAEZFJWQ6FD4Q4GSPD76=attribution-post-clic viewthrough-attribution-lookback-window=fen%C3%AAtre-r%C3%A9trospective-dattribution-post-vue h_01HDJVBAEZ2H91WBHNSMRQYQ7H=fen%C3%AAtre-r%C3%A9trospective-dattribution-post-vue reengagement-settings=param%C3%A8tres-de-r%C3%A9engagement h_01HDJVBAEZZR1W06YH4XJSBKHV=param%C3%A8tres-de-r%C3%A9engagement reengagement-clickthrough-lookback-window=fen%C3%AAtre-r%C3%A9trospective-de-r%C3%A9engagement-post-clic h_01HDJVBAEZ59ERYD2WQQYK6T37=fen%C3%AAtre-r%C3%A9trospective-de-r%C3%A9engagement-post-clic reengagement-viewthrough-lookback-window=fen%C3%AAtre-r%C3%A9trospective-de-r%C3%A9engagement-post-vue h_01HDJVBAEZSCK7430NJ8AMQYVY=fen%C3%AAtre-r%C3%A9trospective-de-r%C3%A9engagement-post-vue reengagement-window=fen%C3%AAtre-de-r%C3%A9engagement h_01HDJVBAEZCMWY5X47FEEFXTBX=fen%C3%AAtre-de-r%C3%A9engagement inapp-event-postback-settings=param%C3%A8tres-de-postback-d%C3%A9v%C3%A8nements-in-app h_01HDJVBAEZ5ZM9RDXPWTJPPYVA=param%C3%A8tres-de-postback-d%C3%A9v%C3%A8nements-in-app h_01HDJVBAEZR1Q2SVE9MEQ9EXKP=attribution-link-tab h_01HDJVBAEZ7R7BKFAZYXXBGS5Y=note h_01HDJVBAEZYSWN59VNXTDEWX93=cost-tab h_01HDJVBAF0VPBBAEHJPG40HJP8=ad-revenue-tab h_01HDJVBAF0KEVSWJ0EW54AEAWV=permissions-tab ad-network-permissions=autorisations-pour-le-r%C3%A9seau-publicitaire h_01HDJVBAF0BMSCKF6J9NJ019YJ=autorisations-pour-le-r%C3%A9seau-publicitaire agency-permissions=autorisations-pour-lagence h_01HDJVBAF0W3ZE7J93CRE8EBRP=autorisations-pour-lagence advanced-twitter-ads-setup-video=vid%C3%A9o-de-configuration-avanc%C3%A9e-de-x-ads h_01HDJVBAF0SJ93TNQ8WSFVE91P=vid%C3%A9o-de-configuration-avanc%C3%A9e-de-x-ads limitations=restrictions h_01HDJVSZSVMX9ARG2B0CHY45X3=restrictions" />
