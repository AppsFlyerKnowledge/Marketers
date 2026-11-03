---
title: Configuration de la campagne Reddit
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - Agencies
    - reddit
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2020-07-09T09:50:46Z'
  edited_at: '2024-11-13T11:00:56Z'
  id: 360011016138
  locale: fr
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/fr/articles/360011016138
---
> **En bref :** Reddit, un partenaire intégré au réseau publicitaire d'AppsFlyer, compte 430 millions d'utilisateurs mensuels très engagés, qui ne peuvent être trouvés nulle part ailleurs.

## Mise en place de Reddit

**Prérequis :** avant de configurer l’intégration, vous devez contacter le partenaire et ouvrir un compte chez lui.

**Pour activer ou modifier l'intégration :**

1. <strong>Activation :</strong> dans AppsFlyer, dans le menu latéral, sélectionnez Collaboration > Marketplace partenaire.  
   **Modification :** dans AppsFlyer, dans le menu latéral, sélectionnez Collaboration > **Intégrations actives**.
2. Sélectionnez le partenaire de votre choix.
3. Cliquez sur **Configurer l'intégration**. Vous êtes alors dirigé vers la page de configuration de l'intégration.
4. Dans l’onglet **Integration**, cochez Activer le partenaire.  
   **Remarque : La case doit rester cochée (activée) tant que vous travaillez avec le partenaire.**
5. Terminez la configuration pour chacun des onglets détaillés ci-après.

<div id="integration-tab" />

<Accordion title="Onglet Intégration">

L'***onglet Intégration*** est divisé en différentes sections.

#### Activer les partenaires

Pour activer la configuration, <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation#activating-a-partner">activez le partenaire.</Anchor>

#### Protection de la vie privée avancée

Pour les apps IOS uniquement, lorsque **la confidentialité avancée (pour iOS 14.5 et +)** est activée, vous pouvez choisir quelles données sont transmises à Reddit via les postbacks et les rapports.

#### ID de transaction

**Pour les applications iOS uniquement, lorsque** l'option **<Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">Partager l'ID de transaction SKAN</Anchor>** est activée, vous autorisez AppsFlyer à partager l'ID de transaction des postbacks SKAdNetwork avec Reddit. Reddit peut ainsi décoder vos valeurs de conversion SKAdNetwork.

#### Paramètres généraux

**Activer l'attribution post-vue**

Activez-la si vous souhaitez attribuer des installations en mode post-vue à partir de Reddit. Le curseur de visualisation est disponible dans la rubrique [***Lien d'attribution***](/docs/reddit-campaign-configuration#attribution-link-tab) dans l'onglet Attribution.

#### Postbacks par défaut

Envoyez des postbacks automatiques à Reddit suite aux installations d'utilisateurs. Sélectionnez si vous souhaitez envoyer des postbacks pour les installations attribuées à :

* Reddit uniquement
* Toutes les sources, y compris organiques

#### Paramètres des événements in-app

Dans cette section, vous pouvez configurer les postbacks d'événements in-app qui sont envoyés à Reddit.

**Pour configurer les postbacks d'événement in-app :**

1. Activez l’option ***Postbacks d'événements in-app***
2. Cliquez sur ***Ajouter un événement*** pour ajouter un événement du SDK à la liste.
3. Complétez les données suivantes :

| Nom du paramètre | Description |
| --- | --- |
| **Nom de l'évènement SDK** | Le nom de l'événement tel que reçu par AppsFlyer, soit depuis le SDK intégré à votre application, ou soit depuis les événements de serveur à serveur.  <br />**Conseil** : Si vous ne voyez pas l'évènement voulu dans la liste, assurez-vous d'activer l'évènement sur un appareil avec une installation non-organique et revérifiez. |
| **ID d'événement partenaire** | Le nom unique ou l'ID de chaque événement, tel que défini par Reddit. Sélectionnez l'événement prédéfini le plus approprié pour votre événement SDK :<ul><li>rdt\_install</li><li>rdt\_signup</li><li>rdt\_app\_launch</li><li>rdt\_search</li><li>rdt\_view\_content</li><li>rdt\_add\_payment\_info</li><li>rdt\_add\_to\_cart</li><li>rdt\_purchase</li><li>rdt\_completed\_tutorial</li><li>rdt\_level\_achieved</li><li>rdt\_spend\_credits</li><li>rdt\_ad\_click</li><li>rdt\_ad\_view</li><li>rdt\_add\_to\_wishlist</li><li>rdt\_unlock\_achievement</li><li>rdt\_login</li><li>rdt\_rate</li><li>rdt\_checkout</li><li>rdt\_start\_trial</li><li>rdt\_subscribe</li><li>rdt\_onboard\_started</li><li>rdt\_onboard\_completed</li><li>rdt\_first\_time\_purchase</li></ul> |
| **Option d'envoi** | Sélectionnez l'envoi d'événements par :<ul><li>Reddit uniquement</li><li>Toutes les sources, y compris organiques</li></ul> |
| **Envoi des données d'événement** | <ul><li>**Sans valeur et sans revenu** : AppsFlyer envoie uniquement l'évènement en lui-même, sans sa valeur.</li><li>**Avec valeurs et sans revenu** : envoie tous les paramètres à l'exception de la valeur de revenu.</li><li>**Avec valeurs et revenus :** envoie tous les paramètres, y compris la valeur de revenu (si présente dans l'événement).</li></ul> |

4. Cliquez sur ***Enregistrer***.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Onglet Lien d'attribution">

Pour générer et enregistrer les liens d’attribution et les envoyer au partenaire dans le but d’attribuer des campagnes spécifiques, des ad sets ou des publicités uniques, et ce autant pour les campagnes UA que les campagnes de retargeting. Vous pouvez utiliser un lien à plateforme unique, ou un OneLink.  
<Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">En savoir plus sur la structure et les paramètres des liens d’attribution</Anchor>.  

**Pour générer un lien d’attribution, veuillez**suivre <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#attribution-link-tab">ces instructions</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Onglet Coût">

AppsFlyer reçoit les données de coûts par API. Consultez le <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tableau d'intégration des coûts du réseau publicitaire</Anchor> pour obtenir plus d'infos sur les dimensions, les métriques et les fonctionnalités prises en charge. **Remarque** : Les données de coût nécessitent un abonnement ROI360.

**Pour activer l'API de coûts :**

* Suivez  <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">ces instructions d'intégration</Anchor>.

<Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Affichez le statut de votre API des coûts,</Anchor> ainsi que la dernière fois où AppsFlyer a pu extraire les données de coûts correspondantes, soit dans le tableau de bord du statut d'intégration des coûts (et des revenus publicitaires), soit dans le tableau de bord du réseau publicitaire individuel.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Onglet Revenus publicitaires">

Les données relatives aux revenus publicitaires ne sont pas prises en charge par Reddit.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Onglet Autorisations">

Dans cet onglet, vous pouvez sélectionner les autorisations à accorder à Reddit. Notez que même si l'attribution est désactivée pour Reddit, l'onglet des autorisations est actif et vous pouvez accorder le contrôle à Reddit.

#### Autorisations pour le réseau publicitaire

Dans cet onglet, vous pouvez sélectionner les autorisations à accorder à Reddit. Notez que même si l'attribution est désactivée pour Reddit, l'onglet des autorisations est actif et vous pouvez accorder le contrôle à Reddit.

Utilisez ces boutons pour autoriser le réseau publicitaire à gérer sa propre configuration pour votre application :

* <span id="01EDKYCTJGZCQ05BQ5JXR6457Y"></span>***<span id="01EDKYCTJHNYT3SRD6Q40YJKR1"></span>Autoriser la configuration de l'intégration*** : permet au partenaire de configurer l'onglet d'intégration (à l'exception des postbacks d'événement in-app)
* <span id="01EDKYCTJHVW0E6TD5ARMFEQQC"></span>***Autoriser la configuration des postbacks d'événement in-app*** : permettre au partenaire de configurer l'auto-mappage des postbacks d'événements in-app dans l'onglet Intégration
* <span id="01EDKYCTJH6C06V91M50CXNSZS"></span>***Autoriser l'accès à votre rapport de rétention*** : valable uniquement pour les données de rétention du partenaire
* <span id="01EDKYCTJHY2JXJHQRQM6S1T7H"></span>***Autoriser l'accès à vos données agrégées sur les utilisateurs fidèles*** : uniquement pour les données sur les utilisateurs fidèles du partenaire
* <span id="01EDKYCTJHF1W3FPJCSSEKJ4GZ"></span>***Autoriser l'accès à vos données agrégées d'évènements in-app*** : uniquement pour les données d'évènements in-app du partenaire
* <span id="01EDKYCTJHVN8E1QPY3BSMC3WD"></span>***Autoriser l'accès à vos données agrégées de revenus*** : valable uniquement pour les données de revenus attribuées au partenaire
* <span id="01EDKYCTJHX0T89JNPJKY71WVW"></span>***Autoriser l'ingestion des dépenses :*** permet au partenaire d'envoyer des données sur les dépenses publicitaires dans des fichiers réservés à cette application.
* <span id="01EDKYCTJHWKWYJS7ZFCJ8558V"></span>***Autoriser l'accès à votre tableau de bord Protect360 :*** uniquement pour les données Protect360 du partenaire, si la fonctionnalité est activée pour l'annonceur

En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">l'octroi d'autorisations à un réseau publicitaire.</Anchor>

</Accordion>

## Restriction relatives aux données brutes

À partir du 22 octobre 2024, les données brutes de Reddit sont <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions#restrictions-des-sources-média">restreintes sur la plateforme AppsFlyer</Anchor>. En conséquence, la source médiatique est signalée comme étant "restreinte". Les clics et les impressions provenant de Reddit ne sont pas inclus dans les rapports de données brutes.

<div data-zendesk-anchors="setting-up-reddit=mise-en-place-de-reddit 01EDKYCH117BTY81G0Z2NF181F=mise-en-place-de-reddit 01EDKYCH11YM04HDJTAWP4XHWH=integration-tab activate-partners=activer-les-partenaires 01EDKYCH11E2X1VSSG2HKKP6VS=activer-les-partenaires advanced-privacy=protection-de-la-vie-priv%C3%A9e-avanc%C3%A9e h_01HJRZF42CYME3EZ37470339CF=protection-de-la-vie-priv%C3%A9e-avanc%C3%A9e transaction-id=id-de-transaction h_01HJRZF42CN7VT8SKNX5E638R0=id-de-transaction general-settings=param%C3%A8tres-g%C3%A9n%C3%A9raux 01EDKYCH11WFJ09XBND6RQT0XA=param%C3%A8tres-g%C3%A9n%C3%A9raux default-postbacks=postbacks-par-d%C3%A9faut 01EDKYCH11KZT2BN64AGETTMD6=postbacks-par-d%C3%A9faut inapp-events-settings=param%C3%A8tres-des-%C3%A9v%C3%A9nements-in-app 01EDKYCH11QAYSV2GMYD4R6DJJ=param%C3%A8tres-des-%C3%A9v%C3%A9nements-in-app h_01HJRZF42DHDDHPCE4NYA7QKV2=attribution-link-tab h_01HJRZF42DYG18DTKSV4G8NHV4=cost-tab 01EDKYCH124QTAFK6VQ3ARHCTM=ad-revenue-tab 01EDKYCH12RY4P6DY3QSWG1A18=permissions-tab ad-network-permissions=autorisations-pour-le-r%C3%A9seau-publicitaire 01EDKYCH12FXE1WASY5YQF80CV=autorisations-pour-le-r%C3%A9seau-publicitaire raw-data-restrictions=restriction-relatives-aux-donn%C3%A9es-brutes 01JAQ0TCR54Q03RQWPNT5PJGPN=restriction-relatives-aux-donn%C3%A9es-brutes" />
