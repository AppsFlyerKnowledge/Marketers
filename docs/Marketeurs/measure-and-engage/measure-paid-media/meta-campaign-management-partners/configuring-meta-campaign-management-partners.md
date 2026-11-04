---
title: Configuration des partenaires de gestion des campagnes Meta
metadata:
  keywords:
    - Facebook
    - FMP
    - Advertisers
    - Partners
    - facebook marketing partner
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
  created_at: '2018-03-18T12:43:51Z'
  edited_at: '2024-10-23T12:07:40Z'
  id: 360000562569
  locale: fr
  section: Meta campaign management partners
  section_id: 6551188365457
  url: https://support.appsflyer.com/hc/fr/articles/360000562569
---
> **En bref :** Optimiser les campagnes publicitaires Meta en utilisant les partenaires de gestion de campagne Meta (anciennement connus sous le nom de Facebook Marketing Partners), tels que Kenshoo, Bidalgo et Smartly. Lorsqu'ils sont configurés, AppsFlyer leur envoie les postbacks.

<div id="configure-meta-campaign-management-partners" />

## Configurer les partenaires de gestion de la campagne Meta

**Conditions préalables :**  avant de configurer une intégration, vous devez  <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations#contacter-le-partenaire">contacter le partenaire</Anchor> et ouvrir un compte chez lui.

**Pour activer ou modifier l'intégration :**

1. **Pour activer :** dans AppsFlyer, dans le menu latéral, sélectionnez **Collaboration** > **Marketplace partenaire**.  
   **Pour les modifier :** dans AppsFlyer, dans le menu latéral, sélectionnez **Collaborer** > **Intégrations actives**.
2. Sélectionnez le partenaire de votre choix.
3. Cliquez sur  **Configurer l'intégration**. Vous êtes alors dirigé vers la page de configuration de l'intégration.
4. Dans l'onglet  **Integration** , sélectionnez l'app à intégrer et cochez l’option  **Activer le partenaire** .  
   **Remarque :** La case doit rester cochée <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">(activée)</Anchor> tant que vous collaborez avec le partenaire.
5. Terminez la configuration pour chacun des onglets détaillés ci-après.

<div id="in-app-event-postback-setup" />

## Configuration du postback des événements in-app

**Conditions préalables** :

Pour que le partenaire obtienne des postbacks, les noms de campagne **doivent être** précédés du nom du partenaire de gestion de la campagne Meta. Par exemple, si le nom du partenaire de gestion de la campagne Meta est *Mcmpexample* et que le segment est *Young\_Segment,* définissez le nom de la campagne sur *mcmpexample\_Young\_Segment*.  
**Remarque :** Le nom du partenaire de gestion de la campagne Meta est **sensible à la casse**.

**Pour configurer les postbacks d'événements in-app**:

[![in-app_event_mapping.png](https://files.readme.io/ced254c1aa0ad454c1876cfc0bc85de20d275824efb34c9665ca144dabffaa2a-14050539243793.png)](https://files.readme.io/ced254c1aa0ad454c1876cfc0bc85de20d275824efb34c9665ca144dabffaa2a-14050539243793.png)

1. Activez l’option **Postbacks d'événement in-app.**
2. Complétez les paramètres requis selon la <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#les-méthodes-de-mappage">méthode de mappage</Anchor> :  
   

| Nom du paramètre | Description |
| --- | --- |
| <span id="appsflyer-event"></span>**Évènement AppsFlyer** | Le nom de l'événement tel que reçu par AppsFlyer, soit depuis le SDK intégré à votre app, soit depuis des événements de serveur à serveur.<br />**Conseil** : Vous ne trouvez pas l'événement que vous recherchez ?<ul><li>veillez à activer l'évènement sur un appareil avec une installation non-organique et vérifiez à nouveau.</li><li>Saisissez l’événement dans la rubrique **Evénement AppsFlyer** puis cliquez sur **Créer un événement personnalisé**. En savoir plus sur le <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#événements-personnalisés">mappage d'événements personnalisés.</Anchor></li></ul> |
| <span id="mapped-to-partner-event"></span>**mappé à l’événement partenaire** | Le nom ou l'identifiant unique de chaque événement, tel que défini du côté du partenaire. <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#les-méthodes-de-mappage">Les différentes configurations de mappage</Anchor> sont :<ul><li>**Champ de texte :** Obtenez l'identifiant d'événement correspondant auprès du partenaire.</li><li>**Liste déroulante :** Sélectionnez l'événement partenaire prédéfini le plus approprié.</li><li>**Tel quel** : envoie les événements à l'état brut, sans mappage du nom.</li></ul> |
| <span id="for-users-from"></span>**pour les utilisateurs de** | Sélectionnez l'option d'envoi pour l'événement :<ul><li>**Ce partenaire uniquement** : envoi de postbacks uniquement lorsque l'événement est attribué à ce partenaire, c'est-à-dire lorsque l'utilisateur qui l'effectue provient de ce partenaire.</li><li>**Toutes les sources média, y compris organiques** : envoi de postbacks pour les événements attribués à n'importe quel partenaire ainsi que pour les événements organiques (soit tout utilisateur qui réalise l'événement depuis n'importe quelle source média).</li></ul> |
| <span id="including"></span>**y compris** | Sélectionnez <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#données-à-inclure-dans-les-postbacks">les données d’événement</Anchor> à partager avec le partenaire dans le postback :<ul><li>**Pas de valeurs et pas de revenus** : envoi de l'événement sans aucun paramètre (valeurs ou revenus).</li><li>**Valeurs et pas de revenus** : envoi de tous les paramètres **à l'exception** de la valeur de revenu.</li><li>**Valeurs et revenus :** envoie tous les paramètres de l’événement, **y compris** la valeur du revenu (si présente dans l’événement).</li></ul> |

3. [Facultatif] Cliquez sur ![conditional-iae-postbacks-icon.png](https://files.readme.io/5345c5ebe95b3f1a0d0858b88ce29f9965178ce750df86c04cb131a93d006a5e-14050481317393.png) pour <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#postbacks-conditionnels-dévénements-in-app">définir les conditions</Anchor> d'envoi de certains événements in-app au partenaire.
4. [Facultatif] Cliquez sur **Ajouter un événement** pour ajouter un autre SDK ou un événement serveur à serveur à la liste.
5. Cliquez sur **Enregistrer l'intégration**.

<div id="important-notes" />

> 📘 **Remarques importantes**
>
> * La désactivation de l'attribution pour les publicités Meta empêche l'envoi de postbacks vers les partenaires de gestion des campagnes Meta.
> * Le mappage des événements in-app avec les partenaires de gestion de campagne de Meta, ou l'absence de celle-ci, n'affecte pas l'envoi d'événements in-app vers les publicités Meta directement depuis le compte de l'annonceur.
> * Le mappage des événements in-app peut nécessiter des paramètres de configuration différents en fonction du partenaire de gestion de la campagne Meta.
> * Les noms des campagnes Meta Ads et X Ads doivent commencer par le nom du compte du partenaire de gestion de la campagne Meta, tel que défini dans la plateforme AppsFlyer, suivi d'un signe underscore « \_ ». Lorsque les campagnes ne sont pas nommées comme mentionné, elles sont visibles pour l'annonceur mais pas pour le partenaire de gestion de campagne de Meta. Le nom du partenaire de gestion de la campagne Meta est **sensible à la casse**.

<div data-zendesk-anchors="configuring-facebook-marketing-partners=configurer-les-partenaires-de-gestion-de-la-campagne-meta h_01HGFQCBT217ZV0R6E2YHTV88N=configurer-les-partenaires-de-gestion-de-la-campagne-meta inapp-event-postback-setup=configuration-du-postback-des-%C3%A9v%C3%A9nements-in-app h_01HGFQCBT3R7HH8M5SQJK1EPSP=configuration-du-postback-des-%C3%A9v%C3%A9nements-in-app h_01HGFQCBT3HGZVFHCC1S04MVQW=remarques-importantes" />
