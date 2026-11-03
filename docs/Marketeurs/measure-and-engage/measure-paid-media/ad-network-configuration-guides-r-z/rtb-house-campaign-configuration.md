---
title: Configuration de la campagne RTB House
metadata:
  keywords:
    - Advertisers
    - RTB
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-07-05T08:30:48Z'
  edited_at: '2024-10-27T09:23:04Z'
  id: 360001274325
  locale: fr
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/fr/articles/360001274325
---
> **En bref :** RTB House, un partenaire intégré du réseau publicitaire AppsFlyer, offre un service de retargeting aux entreprises de E-commerce et gaming. RTB House a développé sa propre solution de retargeting, qui repose sur des algorithmes de deep learning, pour l'achat de publicités en ligne dans le modèle Real-Time Bidding. En plus de l'attribution mobile basée sur les clics, RTB House propose une attribution de retargeting, qui peut être enregistrée avec AppsFlyer.

## Configurer RTB House

**À effectuer en amont :**  avant de configurer l’intégration, vous devez  <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations#contacter-le-partenaire">contacter le partenaire</Anchor> et ouvrir un compte chez lui.

**Pour activer ou modifier l'intégration :**

1. **Activation :** dans AppsFlyer, dans le menu latéral, sélectionnez **Collaboration**> **Marketplace partenaire**.  
   **Modification :** dans AppsFlyer, dans le menu latéral, sélectionnez **Collaboration** > **Intégrations actives**.
2. Sélectionnez le partenaire de votre choix.
3. Cliquez sur **Configurer l'intégration**. Vous êtes alors dirigé vers la page de configuration de l'intégration.
4. Dans l’onglet **Integration**, cochez Activer le partenaire.  
   **Remarque :** La case doit rester cochée (activée) tant que vous travaillez avec le partenaire.
5. Allez au bout de la configuration pour chacun des onglets, cf ci-après.

La fenêtre de configuration de RTB House contient 3 onglets actifs : Intégration, lien d'attribution et autorisations. Cliquez sur les éléments ci-dessous pour en savoir plus sur la configuration des onglets.

Pour obtenir une description détaillée de l'en-tête de la fenêtre de configuration du partenaire, cliquez <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">ici</Anchor>.

> 👍 **À savoir**
>
> * L'étape <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#d-general%20settings">Paramètres généraux</Anchor> de l'onglet Intégration est **obligatoire** pour tous les partenaires.
> * Toutes les autres étapes sont soit informatives, soit **optionnelles**

<div id="integration-tab" />

<Accordion title="Onglet Intégration">

L'onglet Intégration est divisé en différentes sections, cf ci-dessous.

### Activer le partenaire

Lors de votre **première visite** ici, vous devrez enclencher **Activer le partenaire** pour permettre la configuration des paramètres d'intégration. Cette option DOIT RESTER ACTIVÉE tant que vous travaillez avec le partenaire.  
Pour plus de détails sur l'activation des partenaires, cliquez <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">ici</Anchor>.

### Postbacks par défaut

Pour envoyer automatiquement des postbacks à RTB House après les installations et ré-engagements des utilisateurs. Utilisez cette section pour définir **la source des utilisateurs** qui autorisent l'envoi de ces postbacks.

> 📘 **Remarque**
>
> IronSource étant un réseau **toutes-installations**, il préfère recevoir les postbacks pour toute nouvelle installation de votre app, QUELLE QUE SOIT LA SOURCE, y compris organique. Pour ce faire, sélectionnez **Événements attribués à tout partenaire** pour envoyer tous les postbacks d'installation à ironSource.

### Paramètres des événements in-app

Dans cette section, vous pouvez mapper vos événements AppsFlyer avec RTB House via des postbacks.

#### Région

Saisissez la région de votre centre de données RTB House. Régions possibles : **emea**, **us**, **asia**.

#### Paramètres des postbacks d'évènements in-app

1. Activez lespostbacks d'événement in-app.
2. Sélectionnez le type d'envoi pour tous les évènements définis dans le SDK.  
   **- Seuls les évènements attribués à ce partenaire** pour les évènements générés **exclusivement** par des utilisateurs attribués à ce partenaire  
   **- Évènements attribués à n’importe quel partenaire ou organique** pour que l’intégralité de votre base d'utilisateurs puisse être rapportée au partenaire
3. Cliquez sur **Ajouter un événement** pour ajouter un événement SDK à la liste
4. Remplissez les paramètres suivants :

| Nom du paramètre | Description |
| --- | --- |
| **Nom de l'évènement SDK** | Le nom de l'événement, tel qu'il a été reçu par AppsFlyer à partir du SDK intégré à votre application, ou des événements de serveur à serveur.  <br />**À savoir** : si l'événement que vous cherchez n'est pas dans la liste, vérifiez que vous activez bien l'événement sur un appareil avec une installation non-organique. |
| **ID d'événement partenaire** | Le nom ou l'identifiant unique de chaque événement tel que défini chez RTB House.  <br />Obtenez l’ID d’événement correspondant auprès de RTB House et insérez-le dans le champ de texte. |
| **Envoyer les revenus** | **Si la case n'est pas cochée**, AppsFlyer envoie tous les paramètres de l'évènement in-app riche au partenaire, à l'exception du paramètre revenu, qui se trouve dans le paramètre **af\_revenue**.  <br />**Lorsque cette option est cochée**, AF envoie tous les paramètres, y compris la valeur des revenus (si incluse dans l'événement). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Onglet Lien d'attribution">

Pour créer et enregistrer les liens d’attribution et les envoyer au partenaire dans le but d’attribuer des campagnes spécifiques, des ad sets ou des publicités uniques, et ce autant pour les campagnes UA que les campagnes de retargeting. Vous pouvez utiliser un lien à plateforme unique, ou un <Anchor target="_blank" href="/marketers/fr/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">En savoir plus sur la structure et les paramètres des liens d’attribution</Anchor>.  

**Pour créer un lien d'attribution,** suivez <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#attribution-link-tab">ces instructions</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Onglet Coût">

Les données de coûts ne sont pas prises en charge dans l'intégration avec ce partenaire.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Onglet Revenus publicitaires">

Les revenus publicitaires ne sont pas pris en charge dans l'intégration avec ce partenaire.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Onglet Autorisations">

Dans cet onglet, vous pouvez sélectionner les autorisations à accorder à RTB House, que le partenaire agisse en tant que ad network, agence ou même les deux. Notez que même si l'attribution est désactivée pour RTB House, l'onglet des autorisations reste actif et vous pouvez accorder le contrôle à RTB House.

### Autorisations pour le réseau publicitaire

Utilisez ces boutons d’activation pour autoriser le réseau publicitaire à gérer sa propre configuration pour votre app :

* ***Autoriser la configuration de l'intégration*** - permet au partenaire de configurer l'onglet d'intégration (sauf les postbacks d'événements in-app)
* ***Autoriser la configuration des postbacks d'événement in-app*** - permet au partenaire de configurer l'auto-mappage des postbacks d'événements in-app dans l'onglet Intégration
* ***Autoriser l'accès à votre rapport de rétention*** - uniquement pour les données de rétention du partenaire
* ***Autoriser l'accès à vos données agrégées sur les utilisateurs fidèles***  - uniquement pour les données sur les utilisateurs fidèles du partenaire
* ***Autoriser l'accès à vos données agrégées d'évènements in-app** -* uniquement pour les données d'évènements in-app du partenaire
* ***Autoriser l'accès à vos données agrégées de revenus*** - uniquement pour les données de revenus attribuées au partenaire
* ***Autoriser l'accès à votre tableau de bord Protect360*** - uniquement pour les données Protect360 du partenaire, dans le cas où la fonctionnalité est activée pour l'annonceur

En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">l'octroi des autorisations à un réseau publicitaire.</Anchor>

</Accordion>

<div data-zendesk-anchors="setting-up-rtb-house=configurer-rtb-house h_01HJRZXXH277REM62TJA907WX0=configurer-rtb-house h_01HJRZXXH2P8Q15V7DKQT7AVTT=%C3%A0-savoir h_01HJRZXXH2DJ8WMYPQ0NV08R05=integration-tab activate-partner=activer-le-partenaire h_01HJRZXXH309BVZZ2VRRJQ02N8=activer-le-partenaire default-postbacks=postbacks-par-d%C3%A9faut h_01HJRZXXH3X46N8KQ8GTP4BYYP=postbacks-par-d%C3%A9faut h_01HJRZXXH3SDCH4K86YV4VC5VH=remarque inapp-events-settings=param%C3%A8tres-des-%C3%A9v%C3%A9nements-in-app h_01HJRZXXH3HJP28D34NW8A8EZN=param%C3%A8tres-des-%C3%A9v%C3%A9nements-in-app region=r%C3%A9gion h_01HJRZXXH3E7STC8XVRDP39282=r%C3%A9gion inapp-event-postback-settings=param%C3%A8tres-des-postbacks-d%C3%A9v%C3%A8nements-in-app h_01HJRZXXH3336ZJZZD1P8408GP=param%C3%A8tres-des-postbacks-d%C3%A9v%C3%A8nements-in-app h_01HJRZXXH3R7F4QA9PYWY7EYZZ=attribution-link-tab h_01HJRZXXH30PDV0S32THB0C4FM=cost-tab h_01HJRZXXH37CHDD10ASEXPN7VH=ad-revenue-tab h_01HJRZXXH3CASE2ZTRJDSW9545=permissions-tab ad-network-permissions=autorisations-pour-le-r%C3%A9seau-publicitaire h_01HJRZXXH3TJSTVG4Z8ZDQBATG=autorisations-pour-le-r%C3%A9seau-publicitaire" />
