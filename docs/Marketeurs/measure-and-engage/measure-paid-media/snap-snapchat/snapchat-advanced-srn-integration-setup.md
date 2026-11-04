---
title: Snapchat—Configuration de l'intégration SRN avancée
metadata:
  keywords:
    - configuration
    - snapchat measurement partner
    - snapchat
    - measurement
    - snapchat measurement analytics
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
  created_at: '2016-06-13T12:28:59Z'
  edited_at: '2023-12-18T17:40:05Z'
  id: 211011983
  locale: fr
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/fr/articles/211011983
---
> **En bref :** depuis mi-septembre 2023, Snapchat est devenu un SRN avancé. Découvrez comment configurer l'intégration entre AppsFlyer et Snapchat pour permettre la mesure de l'attribution.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/snapchat.png?v=1" width="52px" />

<div id="overview" />

## Présentation

Une intégration SRN avancée signifie que tout le trafic<Anchor target="_blank" href="/marketers/fr/docs/appsflyer-knowledge-base-glossary?query=glossar#dual-consent">à double consentement</Anchor> est attribué et rapporté comme du trafic SRN normal. Pour le trafic non consenti, AppsFlyer est en mesure d'attribuer et de mesurer l'attribution basée sur les clics et les impressions provenant de Snapchat en utilisant d'<Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns#comment-fonctionne-lattribution-avec-les-srn-avancés">autres méthodes d'attribution</Anchor>, conformément aux restrictions de confidentialité.

<div id="set-up-snapchat-integration" />

## Configurer l'intégration de Snapchat

La configuration se fait depuis la page **Intégrations actives**, mais pour trouver de nouveaux partenaires vous devez d'abord vous rendre dans le <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations">marketplace</Anchor>.

**Pour configurer vos campagnes avec Snapchat :**

1. Dans AppsFlyer, allez dans **Configuration** et ouvrez **Marketplace des partenaires**.
2. Trouvez et sélectionnez **Snapchat**.
3. Lisez les conditions générales d'utilisation de Snapchat pour le suivi des conversions pour les apps mobile (MAST) et cliquez sur **Accepter** .
4. Terminez la configuration à l'aide des onglets correspondants.
5. Cliquez sur **Enregistrer l'intégration**.

Pour obtenir une description détaillée de l'en-tête de la fenêtre de configuration du partenaire, cliquez <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">ici</Anchor>.

> 📘 **Remarque**
>
> * Certains paramètres diffèrent entre les appareils iOS et Android
> * En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner">la configuration des intégrations de partenaires</Anchor>

<div id="integration-tab" />

<Accordion title="Onglet Intégration">

L'intégration prend en charge l'attribution des clics et des impressions, les coûts, les revenus publicitaires et les audiences.

<div id="activate-partner" />

#### Activation du partenaire

Lors de votre **première visite** ici, vous devez activer la fonction **Activer le partenaire** pour permettre la configuration.  
Pour plus de détails sur l'activation des partenaires, cliquez <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">ici</Anchor>.

<div id="advanced-privacy" />

<div id="general-settings" />

#### Paramètres généraux

**Activer l'attribution**

Cochez **Activer le partenaire** pour permettre l'attribution à Snapchat.

![mceclip0.png](https://files.readme.io/cf4e73fec951e4e9d2c1919ca20adff88fc0d49d7fea9b033ab9c39194ce2702-360003259638.png)

**ID d'app Snap**

1. Dans votre Gestionnaire de compte Snap, allez dans Apps, et copiez l'ID d'app Snap (lisez le guide de Snapchat sur <Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/a/snap-app-id">comment générer un ID d'app Snap</Anchor>).
2. Collez l'ID dans le champ ID d'app Snap dans AppsFlyer.

![snapchat-app-id.png](https://files.readme.io/2e5f53240893e2a80ba36065f67f4504f69e1167d96ef35bd7a4ab874d5a7bb9-360008280878.png)

**Dans le cas où l'application est promue par une agence**,

* l'ID d'app Snap ne peut être ajouté que par l'annonceur.
* Si l'agence fait partie de la même organisation que vous sur la plateforme publicitaire Snapchat, n'utilisez qu'un seul ID d'app Snap.
* Si l'agence relève d'une organisation différente sur la plateforme publicitaire Snapchat, demandez-lui de fournir son ID d'app Snap pour cette application, et saisissez-le dans ce champ. Plusieurs ID peuvent être saisis. Appuyez sur Entrée après chaque ID.

#### Attribution post clic

Ce curseur vous permet de définir la **durée maximale entre le clic et l'installation**. Seules les installations (premiers lancements) qui ont lieu dans la fenêtre rétrospective peuvent être attribuées à Snapchat.

Vous pouvez personnaliser cette valeur en heures (de 1 à 23) ou en jours (de 1 à 30). Nous recommandons de définir la durée de la fenêtre rétrospective sur 18 jours, afin de garantir la correspondance avec Snapchat

Obtenez plus de détails concernant la <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">fenêtre rétrospective de clic ici</Anchor>.

<Image alt="snap-click-window.png" src="https://files.readme.io/07eb4b7d4a5ec37791cdef31e0fbb77e22f0b65cd189a426bf293d166827b44a-360011563618.png" width="552px" />

#### Fenêtre rétrospective d'attribution post vue

Ce curseur vous permet de définir le **délai maximum entre l'impression et l'installation**. Seules les installations (premiers lancements) qui ont lieu dans cette fenêtre rétrospective, suite à une impression de publicité, sont attribuées à Snapchat, à condition qu'il n'y ait pas eu d'autre clic pertinent sur la publicité.

Vous pouvez personnaliser cette valeur en heures (1 à 23) ou en jours (1 à 7). Nous recommandons de définir la durée de la fenêtre rétrospective sur 1 jour, afin de garantir la correspondance avec Snapchat.

Obtenez plus de détails concernant <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">l'attribution post vue ici</Anchor>.

<Image alt="snap-viewthrough-window.png" src="https://files.readme.io/a493869ca1bb6f6b9ff63438e3b5aa4ade45d047e05fe0d8ebdd99c3ef6affcc-360011482617.png" width="663px" />

<div id="note-3" />

<div id="ignore-active-users-for-retargeting" />

<div id="note-2" />

<div id="re-engagement-attribution" />

#### Attribution du ré-engagement

Activez l'attribution de réengagement pour démarrer l'attribution des réengagements pour Snapchat.  
Si vous êtes une agence, demandez à l'annonceur de le faire pour vous.

#### Fenêtre rétrospective de réengagement post clic

Définissez la durée de la **Fenêtre rétrospective de réengagement post clic** (la période maximale après le clic sur une publicité, pendant laquelle un utilisateur reciblé peut être attribué à celle-ci). Vous pouvez définir la valeur en heures (jusqu'à 23) ou en jours (1-30) :

<Image alt="snap-reengagement-activate.png" src="https://files.readme.io/318deeab0432870035a163a7b8a5b8c03be7d683bfc369104c8577674fde0036-36433422309905.png" width="642px" />

#### Fenêtre rétrospective de réengagement post vue

Pour commencer à attribuer des impressions d'annonces de retargeting, activez **Attribution de réengagement post vue**.  
Définissez la durée de la fenêtre rétrospective de réengagement post vue (la période maximale pendant laquelle une publicité est vue et pendant laquelle un utilisateur reciblé peut être attribué à la publicité). Vous pouvez définir la valeur en heures (jusqu'à 23) ou en jours (1-7) :

![snap-reengagement-view-through.png](https://files.readme.io/4faf93b6d8a8e45043eb9440d8f56a70eba2da51f3a572ea6cd698e072f033c6-36433415112849.png)

#### Fenêtre de réengagement

Définissez la durée de la **Fenêtre de réengagement** (période au cours de laquelle les événements in-app de l'utilisateur sont attribués à la source média de retargeting). Vous pouvez définir la valeur en jours (1-90), en heures (jusqu'à 23) ou même en valeur vie :

<Image alt="snap-reengagement-window.png" src="https://files.readme.io/99aab0e0e808514d1450fd297a1e7d2217be4e21d8ca85bd5a922e797f39755e-360008512418.png" width="557px" />

<div id="in-app-event-postbacks" />

#### Paramètres de postback d'évènements in-app

Mappage des événements AppsFlyer avec le partenaire via postback. Si l'envoi de postback est activé, il inclut les événements in-app rejetés (événements bloqués par Protect360 ou événements jugés non conformes par les règles de validation de cible)

[![In-app_event_postbacks_en-us.png](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)

**Pour configurer les postbacks d'événement in-app :**

1. Définissez **l'ID du partenaire** (si nécessaire).
2. Activez **Postbacks d'événements in-app.**
3. Si nécessaire, configurez la **fenêtre de postback d'évènement in-app**, (en savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#fenêtre-des-postbacks-dévénements-in-app">la configuration de la fenêtre de postback d'événement in-app</Anchor>).
4. Si cela vous est proposé, vous devez choisir d'envoyer les événements automatiquement ou manuellement. En savoir plus sur l'envoi de <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped">tous les événements tels quels.</Anchor>
5. Cliquez sur **Ajouter un événement** pour ajouter à la liste un SDK ou un événement de serveur à serveur.
6. Renseignez les paramètres demandés.
7. [Facultatif] Cliquez sur <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/6524810d15f08b4b85deab9c2cbfb8fd7880126b3c3180e3ecf4ead5f1f0a9ae-17798909160465.png" width="30px" /> pour définir les conditions d'envoi de certains événements in-app au partenaire.  
   En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#postbacks-conditionnels-dévénements-in-app">les postbacks d'événements in-app conditionnels</Anchor>.

| Nom du paramètre | Description |
| --- | --- |
| **Événement AppsFlyer** | Le nom de l'événement tel que reçu par AppsFlyer, soit depuis le SDK intégré à votre app, soit depuis les événements de serveur à serveur.<br />**Astuce** : vous ne voyez pas s'afficher un événement en particulier ?<ul><li>Assurez-vous d'activer l'évènement sur un appareil avec une installation non-organique et revérifiez.</li><li>Saisissez-le dans **Événement AppsFlyer** puis cliquez sur **Créer événement personnalisé**. En savoir plus sur le <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#événements-personnalisés">mappage d'événements personnalisés.</Anchor></li></ul> |
| **mappé à l’événement partenaire** | Le nom ou l'identifiant unique de chaque événement, tel que défini du côté du partenaire. Les différentes configurations du mapping sont :<ul><li>**Champ de texte :** obtenez l'ID d'événement correspondant auprès du partenaire.</li><li>**Liste déroulante :** sélectionnez l’événement AppsFlyer prédéfini approprié.</li><li>**Tel quel** : envoyez les événements à l'état brut, sans mappage du nom.</li></ul> |
| **pour les utilisateurs de** | Sélectionnez l'option d'envoi pour l'événement :<ul><li>**Ce partenaire uniquement** : envoie des postbacks exclusivement lorsque cet événement est attribué à ce partenaire.</li><li>**Toutes les sources média, organiques comprises** : envoie des postbacks pour les événements attribués à n'importe quel partenaire ou n'importe quel événement organique.</li></ul> |
| **Y compris** | <ul><li>**Aucune donnée (par défaut)** : envoie uniquement l'événement en lui-même mais sans sa valeur.</li><li>**Valeurs et revenus** : envoie tous les paramètres de l’événement, **y compris** la valeur de revenu (si présente dans l’événement).</li><li>**Avec valeurs et sans revenu** : envoie tous les paramètres **à l'exception** de la valeur de revenu.</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Onglet Lien d'attribution">

Les liens d'attribution ne sont pas disponibles pour Snapchat.

<div id="web-to-app-measuring-app-activity-for-non-app-campaigns" />

<div id="note-6" />

<div id="note-5" />

<div id="note-1" />

<div id="install-attribution" />

<div id="advanced-matching-data-sharing" />

<div id="note-4" />

> 📘 **Note**
>
> Pour tous les SRN, tels que Facebook, les publicités de recherche Apple, Adwords, Snapchat etc., cet onglet n'est pas fonctionnel, car ils n'utilisent pas de liens d'attribution externes.

</Accordion>

<div id="cost-tab" />

<Accordion title="Onglet Coût">

L'intégration des coûts fournit les données agrégées suivantes :

* Données sur les coûts pour vos campagnes, vos adsets, vos publicités et vos canaux. Consultez le <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tableau d'intégration des coûts du réseau publicitaire</Anchor> pour obtenir plus d'infos sur les dimensions, les métriques et les fonctionnalités prises en charge.**Remarque :** les données de coût nécessitent un abonnement <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>.
* Données sur les clics et les impressions.

**Pour activer l'API de coûts :**

* Suivez  <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">ces instructions d'intégration</Anchor>.

<div id="cost-data-sync-status" />

<Accordion title="État de synchronisation des données de coût">

<Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Affichez le statut de votre API de coûts</Anchor> et la dernière fois qu'AppsFlyer a réussi à extraire des données de coûts correspondantes, soit dans le tableau de bord du statut d'intégration des coûts (et des revenus publicitaires), soit dans le tableau de bord du réseau publicitaire individuel.

</Accordion>

<div id="stop-snapchat-cost-sync" />

<Accordion title="Arrêter la synchronisation des coûts de Snapchat">

**Pour ne plus recevoir les coûts Snapchat et pour supprimer un compte Snapchat connecté :**

* <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">Dans la colonne Actions, survolez un compte, cliquez sur **Supprimer la connexion**</Anchor>   
  Une fois supprimée, AppsFlyer cesse de recevoir les coûts. Le fait de supprimer la connexion ne supprime pas les données historiques.

</Accordion>

> 📘 **Remarques**
>
> * Assurez-vous que la configuration de votre campagne dans Snapchat concerne une application iOS ou Android, et non les deux. Si la campagne concerne les deux applications, AppsFlyer ne peut pas ventiler le coût par application, et le coût ne s'affiche pas dans AppsFlyer.
> * Pour éviter les divergences dans les données relatives aux coûts, définissez le même fuseau horaire dans les <Anchor target="_blank" href="/marketers/fr/docs/changing-app-time-zone-settings#changing-the-time-zone">paramètres de l'application</Anchor> et dans votre compte publicitaire Snapchat.
> * Une fois que vous avez défini les coûts Snapchat, vous ne devez pas changer le nom d'une campagne, d'un ensemble de publicités ou d'une publicité unique, car cela pourrait entraîner de graves discordances ou des données de coût manquantes.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Onglet Revenus publicitaires">

Les revenus publicitaires ne sont pas pris en charge dans l'intégration avec ce partenaire.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Onglet Autorisations">

Dans cet onglet, vous pouvez sélectionner les autorisations à accorder à Snapchat. Notez que même si l'attribution est désactivée pour Snapchat, l'onglet des autorisations est actif et vous pouvez accorder le contrôle à Snapchat.

Activez **Autorisations du réseau publicitaire** pour démarrer la configuration.

Une fois que vous avez activé les **Autorisations du réseau publicitaire** :

* L'application apparaît sur le tableau de bord du réseau publicitaire
* Les autorisations sont uniquement accordées à ce réseau publicitaire
* L'administrateur du réseau publicitaire peut <Anchor target="_blank" href="/marketers/fr/docs/manage-data-access-permissions">consulter les données de base concernant l'app</Anchor>

#### Octroyez des autorisations aux membres d'équipe du réseau publicitaire

Par défaut, l'admin de Snapchat a accès à votre app, mais vous pouvez donner à certains employés de Snapchat les autorisations nécessaires pour gérer votre application. Pour qu'ils puissent agir, ces personnes doivent être ajoutées par l'admin de Snapchat en tant que **membres d'équipe** d'AppsFlyer.

Ensuite, vous devez récupérer les adresses e-mail des membres de l'équipe Snapchat concernés.

Pour ajouter des membres d'équipe qui auront la permission de gérer votre application :

1. Cliquez sur **Ajouter un membre d'équipe**.
2. Saisissez l'adresse email du membre d'équipe du réseau publicitaire
3. Cliquez sur **Ajouter**.
4. Répétez l'opération pour ajouter autant de membres d'équipe que nécessaire.

Une fois que vous avez activé les autorisations pour le réseau publicitaire, sélectionnez les autorisations vous souhaitez lui accorder.

Utilisez ces boutons pour autoriser le réseau publicitaire à gérer sa propre configuration pour votre application :

#### Autorisations pour le réseau publicitaire

* **Autoriser la configuration de l'intégration** : permet au partenaire de configurer l'onglet d'intégration (à l'exception des postbacks d'événement in-app)
* **Autoriser la configuration des postbacks d'événement in-app** : permettre au partenaire de configurer l'auto-mappage des postbacks d'événements in-app dans l'onglet Intégration
* **Autoriser l'accès à votre rapport de rétention** : valable uniquement pour les données de rétention du partenaire
* **Autoriser l'accès aux données agrégées de vos utilisateurs fidèles** : valable uniquement pour les données des utilisateurs fidèles du partenaire
* **Autoriser l'accès à vos données agrégées d'évènements in-app** : uniquement pour les données d'évènements in-app du partenaire
* **Autoriser l'accès à vos données agrégées de revenus** : valable uniquement pour les données de revenus attribuées au partenaire
* **Autoriser l'intégration des dépenses** au niveau de l'application.
* **Autoriser l'accès à votre tableau de bord Protect360** : valable uniquement pour les données Protect360 du partenaire, attendu que cette fonctionnalité est activée chez l'annonceur

En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">l'octroi d'autorisations à un réseau publicitaire.</Anchor>

</Accordion>

<div id="note-7" />

<div id="deep-linking-with-snapchat" />

## Deep linking avec Snapchat

Le deep linking avec Snapchat est basé sur l'utilisation d'un deep linking natif à la plateforme de Snapchat, tout en y ajoutant des paramètres AppsFlyer.

Pour utiliser le deep linking avec Snapchat :

1. Vérifiez que la fonction de **deep linking** pour [le retargeting est activée pour Snapchat.](/docs/snapchat-advanced-srn-integration-setup#comment-mettre-en-place-le-deep-linking-sur-la-plateforme-snapchat)
2. Vérifiez que l'attribution de réengagement <Anchor target="_blank" href="/marketers/fr/docs/app-settings#reengagement-attribution">est bien activée dans AppsFlyer.</Anchor>
3. Ajoutez **au moins** les paramètres suivants au schéma d'URI de deep linking de l'app :

* **PID** - La source média dans ce cas est toujours **snapchat\_int**. Cela permet à toutes les données d'apparaître dans le tableau de bord AppsFlyer sous la source média **Snapchat\_int** .
* **C -** Le nom de la campagne concernée
* **is\_retargeting=true -** Ce champ définit la campagne comme une campagne de retargeting. Les engagements des utilisateurs existants avec la campagne de retargeting sont marqués comme des réengagements en raison de l'existence de ce champ dans l'URI. Cela garantit que les données de l'utilisateur apparaissent dans le tableau de bord de retargeting.

> 📄 **Exemple d'URI**
>
> client://home?pid=snapchat\_int&c=TEST&is\_retargeting=true

<div id="set-up-deep-links-on-the-snap-platform" />

### Comment mettre en place le deep linking sur la plateforme Snapchat ?

1. Sélectionnez le type d'opportunité **Diriger le trafic vers l'app**.
2. Ajoutez l'URI de deep linking :  
     
    [![](https://files.readme.io/428258bbc5eb2fc7332ea07356e098eb66ac2cfdd0955117a14666eb76a20f79-360001717778.png)](https://files.readme.io/428258bbc5eb2fc7332ea07356e098eb66ac2cfdd0955117a14666eb76a20f79-360001717778.png)

<div id="deferred-deep-linking-with-snapchat" />

### Deep linking différé avec Snapchat

Vous pouvez accéder aux données de conversion des utilisateurs de Snapchat en temps réel directement au niveau du SDK en utilisant le <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">deep linking différé</Anchor>.

<Anchor target="_blank" href="/marketers/fr/docs/conversion-data-payloads-and-scenarios#snapchat-conversion-data">Les données de conversion Snapchat</Anchor> comprennent le paramètre **af\_dp**, qui vous permet d'utiliser le deep linking et de diffuser du contenu personnalisé en fonction de l'engagement de l'utilisateur avec votre publicité dans Snapchat.

Vous pouvez également utiliser d'autres paramètres de données de conversion tels que **af\_adset** ou **af\_channel**.

<div id="important" />

<div id="agency-limitations" />

<div id="set-up-snapchat-for-agencies" />

## Configurer Snapchat pour les agences

La configuration de l'attribution Snapchat pour une agence est similaire à celle d'un annonceur.

Les agences ne peuvent pas définir les paramètres de confidentialité avancés — seul l'annonceur possède cette autorisation.

Pour terminer la configuration, deux étapes sont nécessaires :

1. L'annonceur doit activer **Activer le partenaire** pour Snapchat pour permettre la configuration des paramètres de l'onglet d'intégration.  
   Pour plus de détails sur l'activation des partenaires, cliquez sur <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">ici</Anchor>.
2. Sur le tableau de bord de l'agence, sur la page de configuration de Snapchat, la zone de texte de l'identifiant du compte Snapchat est activée comme indiqué ci-dessous. Les agences peuvent saisir jusqu'à 50 identifiants de comptes Snapchat différents dans la zone de texte. Toutes les données d'attribution provenant de ces comptes sont ensuite visibles dans le tableau de bord de l'agence uniquement.[![snapchat-agency-integration.png](https://files.readme.io/261a0246bb7da0899e653a776eb25e17ce3ae8bff1efef33acac0ef0bf99abcf-21074932431505.png)](https://files.readme.io/261a0246bb7da0899e653a776eb25e17ce3ae8bff1efef33acac0ef0bf99abcf-21074932431505.png)

> ❗️ **Avertissement**
>
> Les identifiants des comptes Snapchat ne doivent pas être partagés entre l'annonceur et l'agence. S'ils sont partagés, TOUTES les installations de l'annonceur sont automatiquement attribuées sur le tableau de bord de l'agence.

<div id="raw-data-restrictions" />

## Restriction relatives aux données brutes

* Depuis le 1er mars 2023, les désinstallations de Snapchat ne sont pas incluses dans les rapports de données brutes.
* À partir du 12 septembre 2023, Snapchat fournira aux annonceurs des données d'attribution limitées au niveau de l'appareil. Pour les sources de niveau utilisateur telles que les rapports de données brutes, les messages Push API, les rapports Pull API et Data Locker, les champs suivants sont renseignés :

* * Source média (snapchat\_int)
  * Canal
  * Type de touch attribué (impression)
  * Date de touch attribué (date uniquement - « jj/mm/aaaa »)
  * La campagne est marquée comme « restreinte »

<div id="snapchat-data-retention" />

## Conserver les données de Snapchat

Snapchat demande aux prestataires d'attribution de supprimer ses données de niveau utilisateur 12 mois après l'installation. Cela signifie que les évènements effectués par ces utilisateurs 12 mois après l'installation de l'app sont considérés comme organiques.

Les données agrégées passées restent les mêmes.

> 📄 **À consulter également**
>
> <Anchor target="_blank" href="/marketers/fr/docs/skan-interoperation-with-snapchat">Interopérabilité d'AppsFlyer SKAdNewtork avec Snapchat</Anchor>

<div data-zendesk-anchors="overview=pr%C3%A9sentation 01H8F1RWVPTHBDGF3830DY7G7M=pr%C3%A9sentation setting-up-snapchat-integration=configurer-lint%C3%A9gration-de-snapchat 01H7WQ47ECTZHPKMG5Z5ZPAND5=configurer-lint%C3%A9gration-de-snapchat 01H88VAJH3BYZSXQGGZZJQ9N0C=remarque 01H7WQ47ECD76GFNM7VVV7C9RG=integration-tab activate-partner=activation-du-partenaire 01H7WQ47ECZB5GNCQ0XH68N1DK=activation-du-partenaire general-settings=param%C3%A8tres-g%C3%A9n%C3%A9raux 01H7WQ47ECQSQPP63H398NTQ6M=param%C3%A8tres-g%C3%A9n%C3%A9raux clickthrough-attribution=attribution-post-clic 01H7WQ47ECP56VNB2MY0WYE420=attribution-post-clic viewthrough-attribution-lookback-window=fen%C3%AAtre-r%C3%A9trospective-dattribution-post-vue 01H7WQ47EC7S1SPVV70SR04CPY=fen%C3%AAtre-r%C3%A9trospective-dattribution-post-vue reengagement-attribution=attribution-du-r%C3%A9-engagement 01H7WQ47ECHGMWS35VEM8MD2F2=attribution-du-r%C3%A9-engagement reengagement-clickthrough-lookback-window=fen%C3%AAtre-r%C3%A9trospective-de-r%C3%A9engagement-post-clic 01H7WQ47ECSP3H6202PAR816CX=fen%C3%AAtre-r%C3%A9trospective-de-r%C3%A9engagement-post-clic reengagement-viewthrough-lookback-window=fen%C3%AAtre-r%C3%A9trospective-de-r%C3%A9engagement-post-vue 01H7WQ47ECEW3QBCA65DVGGB7E=fen%C3%AAtre-r%C3%A9trospective-de-r%C3%A9engagement-post-vue reengagement-window=fen%C3%AAtre-de-r%C3%A9engagement 01H7WQ47ECDVE76A1TA81SJAYZ=fen%C3%AAtre-de-r%C3%A9engagement inapp-event-postback-settings=param%C3%A8tres-de-postback-d%C3%A9v%C3%A8nements-in-app 01H7WQ47ECYF4XW9F657WRJWFW=param%C3%A8tres-de-postback-d%C3%A9v%C3%A8nements-in-app 01H7WQ47EDWX9TGAD4X0E41RQ8=attribution-link-tab 01H7WQ47ED5N4REX0SFVY5ZG2K=note 01H7WQ47EDCKQ1T4NVFD3C1KV0=cost-tab 01H7WQ47ED1HYEBHFJDHTB6HJH=cost-data-sync-status 01H7WQ47ED3P53B269W93Z341E=stop-snapchat-cost-sync 01H7WQ47EDQ0253RY37PX67REV=remarques 01H7WQ47EDC3YB1BKNG2C7AD6J=ad-revenue-tab 01H7WQ47EDXRE05R6M1YVD9DK7=permissions-tab grant-permissions-to-ad-network-team-members=octroyez-des-autorisations-aux-membres-d%C3%A9quipe-du-r%C3%A9seau-publicitaire 01H7WQ47ED0KXZ1ACV2ER2B0GJ=octroyez-des-autorisations-aux-membres-d%C3%A9quipe-du-r%C3%A9seau-publicitaire ad-network-permissions=autorisations-pour-le-r%C3%A9seau-publicitaire 01H7WQ47ED6YSJ5Q64578A9RF8=autorisations-pour-le-r%C3%A9seau-publicitaire deep-linking-with-snapchat=deep-linking-avec-snapchat 01H7WQ47EDC973V7CPE38QAQE7=deep-linking-avec-snapchat 01H7WQ47EDXS702A9TZ7DJ8MPG=exemple-duri how-to-set-up-deep-links-on-snap-platform=comment-mettre-en-place-le-deep-linking-sur-la-plateforme-snapchat 01H7WQ47EDJAX2DW7A2JJ4XVJN=comment-mettre-en-place-le-deep-linking-sur-la-plateforme-snapchat deferred-deep-linking-with-snapchat=deep-linking-diff%C3%A9r%C3%A9-avec-snapchat 01H7WQ47EDS3MYRN9A9ZPHXG9Z=deep-linking-diff%C3%A9r%C3%A9-avec-snapchat setting-up-snapchat-for-agencies=configurer-snapchat-pour-les-agences 01H7WQ47EDARK9SSP47V5MGX18=configurer-snapchat-pour-les-agences 01H7WQ47EDPEDQHX9XRDKYKB1W=avertissement raw-data-restrictions=restriction-relatives-aux-donn%C3%A9es-brutes h_01HA3XZPWSKVRX7VTRXT1WQ1EZ=restriction-relatives-aux-donn%C3%A9es-brutes keeping-snapchat-data=conserver-les-donn%C3%A9es-de-snapchat 01H7WQ47ED9STKS1CVW5EXYX0Z=conserver-les-donn%C3%A9es-de-snapchat h_01HE7RP6VPPAY2CCSNTJ0RVSXM=%C3%A0-consulter-%C3%A9galement" />
