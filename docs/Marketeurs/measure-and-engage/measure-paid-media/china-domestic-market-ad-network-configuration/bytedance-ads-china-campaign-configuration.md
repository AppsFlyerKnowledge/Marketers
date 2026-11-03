---
title: ByteDance Ads China – Configuration de la campagne
metadata:
  keywords:
    - bytedance
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-06-18T07:05:42Z'
  edited_at: '2024-10-25T10:43:36Z'
  id: 115003019403
  locale: fr
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/fr/articles/115003019403
---
> **En bref :** ByteDance Ads China (Ocean Engine), un partenaire intégré d'AppsFlyer, est une entreprise technologique spécialisée dans les plateformes de contenu utilisant l'apprentissage automatique.

> 📘 **Remarque**
>
> Si vous souhaitez promouvoir vos applications Android avec ByteDance Ads China, vous devez envoyer votre OAID au SDK AppsFlyer conformément aux instructions fournies dans la section <Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">Intégration du SDK AppsFlyer - Android</Anchor>. Le service Google Play est bloqué en Chine, OAID est l’identifiant d’appareil Android le plus populaire pour l’attribution des annonces.

En plus de l’attribution mobile basée sur les clics, ByteDance Ads China propose l’attribution post vue, que vous pouvez enregistrer avec AppsFlyer.

Pour configurer vos campagnes avec ByteDance Ads China, suivez les étapes ci-dessous.

## Configuration de ByteDance Ads China

**Conditions préalables :**  Avant de configurer une intégration, vous devez  <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations#contacter-le-partenaire">contacter le partenaire</Anchor> et ouvrir un compte chez lui.

**Pour activer ou modifier l'intégration :**

1. **Pour activer :** dans AppsFlyer, dans le menu latéral, sélectionnez **Collaboration**> **Marketplace partenaire**.  
   **Pour les modifier :** dans AppsFlyer, dans le menu latéral, sélectionnez **Collaborer** > **Intégrations actives**.
2. Sélectionnez le partenaire de votre choix.
3. Cliquez sur **Configurer l'intégration**. Vous êtes alors dirigé vers la page de configuration de l'intégration.
4. Dans l’onglet **Integration**, cochez Activer le partenaire.  
   **Remarque :** La case doit rester cochée (<Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">activée</Anchor>) tant que vous travaillez avec le partenaire.
5. Terminez la configuration pour chacun des onglets détaillés ci-après.

Conseil

> 👍 **Tip**
>
> * L'étape <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#d-general%20settings">Paramètres généraux</Anchor> de l'onglet Intégration est **obligatoire** pour tous les partenaires.
> * Toutes les autres étapes sont soit descriptives, soit **optionnelles**

<div id="integration-tab" />

<Accordion title="Onglet Intégration">

L'onglet Intégration est divisé en différentes sections, comme décrit ci-dessous.

### Activer les partenaires

Lors de la **première visite** ici, vous devez activer l’icône ***Activer le partenaire*** pour permettre la configuration des paramètres de l’onglet intégration. Cette option doit rester activée tant que vous travaillez avec le partenaire.  
Pour plus de détails sur l'activation des partenaires, cliquez <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">ici</Anchor>.

Paramètres généraux

**Activer l'attribution post-vue**

[![](https://files.readme.io/3340b894428079e37c238cd78883669abd53cd6895165c5f9b5ea90d27d570c9-50612201111697.png)](https://files.readme.io/3340b894428079e37c238cd78883669abd53cd6895165c5f9b5ea90d27d570c9-50612201111697.png)

Basculez cette option sur **ON** si vous souhaitez attribuer les installations après affichage de ByteDance Ads China. Le curseur rétroactif post-vue est disponible dans l'onglet Lien d'attribution (détails ci-dessous).

### Postbacks par défaut

AppsFlyer peut envoyer des postbacks automatiques à ByteDance Ads China suite aux installations et aux réengagements des utilisateurs. Utilisez cette section pour définir **la source des utilisateurs** autorisant l'envoi de ces postbacks.

![bytedance-default-postbacks.png](https://files.readme.io/5f3cb637fb9ff652533fcfd9c02ea8dc1768e0e1c1686a180ea18c0d2e09309f-50612201121425.png)

### Paramètres des événements in-app

Dans cette section, vous pouvez mapper vos événements AppsFlyer avec ByteDance Ads China via des postbacks.

1. Activez les postbacks d'événement in-app.
2. Sélectionnez le type d'envoi pour tous les évènements définis dans le SDK.  
   **- Uniquement les évènements attribués à ce partenaire** pour les évènements issus **exclusivement** des utilisateurs attribués à ce partenaire  
   **- Évènements attribués à n’importe quel partenaire ou organique** pour que l’intégralité de votre base d'utilisateurs puisse être reliée au partenaire
3. Cliquez sur **Ajouter un événement** pour ajouter un événement du SDK à la liste.
4. Remplissez les paramètres suivants :

| Nom du paramètre | Description |
| --- | --- |
| **Événement AppsFlyer** | Le nom de l'événement tel que reçu par AppsFlyer, soit depuis le SDK intégré à votre app, soit depuis des événements de serveur à serveur.<br />**Conseil** : Vous ne voyez pas s'afficher un événement en particulier ?<ul><li>Activez l'événement sur un appareil avec une installation non-organique et vérifiez à nouveau.</li><li>Saisissez l’événement dans **AppsFlyer event** puis cliquez sur **Créer un événement personnalisé**. En savoir plus sur le <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#événements-personnalisés">mappage d'événements personnalisés.</Anchor></li></ul> |
| **mappé à l’événement partenaire** | Le nom ou l'identifiant unique de chaque événement, tel que défini du côté du partenaire. Les différentes configurations du mappage sont :<ul><li>**Champ de texte :** Obtenez l'identifiant d'événement correspondant auprès du partenaire.</li><li>**Liste déroulante :** Sélectionnez l’événement AppsFlyer approprié et prédéfini.</li><li>**Tel quel** : Envoyez les événements tels quels, sans mapper le nom de l’événement.</li></ul> |
| **pour les utilisateurs de** | Sélectionnez l'option d'envoi pour l'événement :<ul><li>**Ce partenaire uniquement** : Ce partenaire uniquement : envoi de postbacks uniquement lorsque l'événement est attribué à ce partenaire, c'est-à-dire lorsque l'utilisateur qui l'effectue provient de ce partenaire.</li><li>**Toutes les sources média, y compris les sources organiques** : Envoi de postbacks pour les événements attribués à n'importe quel partenaire, ainsi que pour les événements organiques (soit tout utilisateur qui réalise l'événement depuis n'importe quelle source média).</li></ul> |
| **y compris** | Sélectionnez les données d’événement à partager avec le partenaire dans le postback :<ul><li>**Pas de valeurs et pas de revenus** : Envoyez uniquement l’événement lui-même sans aucun paramètre (valeurs ou revenus).</li><li>**Valeurs et pas de revenus** : envoie tous les paramètres **à l'exception** de la valeur de revenu.</li><li>**Valeurs et revenus :** envoie tous les paramètres de l’événement, **y compris** la valeur du revenu (si présente dans l’événement).</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Onglet Lien d'attribution">

Pour générer et enregistrer les liens d’attribution et les envoyer au partenaire dans le but d’attribuer des campagnes spécifiques, des ad sets ou des publicités uniques, et ce autant pour les campagnes UA que les campagnes de retargeting. Vous pouvez utiliser un lien à plateforme unique ou un <Anchor target="_blank" href="/marketers/fr/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">En savoir plus sur la structure et les paramètres des liens d’attribution</Anchor>.  

**Pour générer un lien d’attribution, veuillez**suivre <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#attribution-link-tab">ces instructions</Anchor>.

### Lien d'attribution de clic

Une fois que vous avez généré le lien d’attribution, terminez le processus de configuration de la campagne sur le site ByteDance Ads China.

**1. Créez un suivi des conversions dans Ocean Engine.**

Connectez-vous à Ocean Engine ([https://ad.oceanengine.com/](https://ad.oceanengine.com/)) > **Bibliothèque** > **Suivi des conversions**.

![OE_dashboard_1.png](https://files.readme.io/fda140ac7e3023033880b04ed500a675ae78187e4eb694ee200922b729ab119f-50612185108497.png)

Cliquez sur **Application de suivi** et créez une **Transformation de nouvelles applications**.

![OE_dashboard_2.png](https://files.readme.io/dbf0c13c23d21d08c195a4ab747e5de0986cb01f5ebde98f6c701ce731480958-50612185109009.png)

Cliquez sur la méthode **API**.

![OE_dashboard3.png](https://files.readme.io/70e7f6ca01c532fafb8f2ab7d31d6de51494f11749329c1c1333d1da6f28f284-50612185110417.png)

Dans la section Lien de surveillance, saisissez le lien d’attribution des clics et/ou le lien d’attribution des impressions AppsFlyer.

![dashboard4.png](https://files.readme.io/d36ec92a03062fc7ee169bb1ff3863722343577f3ee2b12779065b3e52731348-50612201124369.png)

**2. Terminez le test d’attribution en suivant les instructions sur le site web**.

**3. Créez une campagne publicitaire avec la conversion nouvellement créée**.

Allez à **Nouvelle annonce** >> **Définir le budget et l’enchère** puis sélectionnez la conversion que vous avez créée pour cette application.

</Accordion>

<div id="cost-tab" />

<Accordion title="Onglet Coût">

AppsFlyer reçoit les données de coûts par API. Notez qu’AppsFlyer ne prend pas en charge les données de coût au niveau de l’annonce pour ByteDance, à l’exception des campagnes diffusées sur le système ByteDance v1.0.

### Tailles d'API prises en charge

| Géo | Source média | Campagne | Adset | Annonce | Autre |
| --- | --- | --- | --- | --- | --- |
| Oui | - | Oui | Oui | Non<br /><br />(Les publicités sont acceptées pour les campagnes ByteDance v1.0) | - |

**Pour activer l’API de coût de ByteDance Ads China** :

1. Dans l'onglet Coût du partenaire intégré, activez ***Obtenir les données de coût***.
2. Connectez-vous à ByteDance Ads China.
3. Cliquez sur ***Enregistrer les coûts***.
   * Vous avez terminé la procédure avec succès. L'API est active. AppsFlyer collecte les données du partenaire 6 fois par jour, soit en moyenne toutes les quatre heures.
   * L'onglet Coût affiche l'état de votre intégration des coûts et le dernier moment où AppsFlyer est parvenu à rassembler les données de coût correspondantes.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Onglet Revenus publicitaires">

Cette section vous concerne si vous agissez en tant qu'éditeur, en affichant les publicités du partenaire à vos utilisateurs. En tant que tel, vous souhaiterez certainement mesurer l'engagement de vos utilisateurs provenant de différentes sources, afin d'identifier celles qui offrent le maximum de rentabilité.

**Pour activer l'API de revenus publicitaires** :

* Suivez  <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">ces instructions d'intégration</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Onglet Autorisations">

Dans cet onglet, vous pouvez sélectionner les autorisations à accorder à ByteDance Ads China, que le partenaire agisse en tant que réseau publicitaire, agence ou les deux. Notez que même si l'attribution est désactivée pour ByteDance Ads China, l'onglet des autorisations est actif et vous pouvez accorder le contrôle à ByteDance Ads China.

Utilisez ces boutons pour autoriser le réseau publicitaire à gérer sa propre configuration pour votre application :

### Autorisations pour le réseau publicitaire

* ***Autoriser la configuration de l'intégration*** - permettre au partenaire de configurer l'onglet d'intégration (sauf les postbacks d'événements in-app)
* ***Autoriser la configuration des postbacks d'événements in-app*** -  permettre au partenaire de configurer le mappage des postbacks d'événements in-app sur l'onglet d'intégration
* ***Autoriser l'accès à votre rapport de rétention*** - uniquement pour les données de rétention du partenaire
* ***Autoriser l'accès à vos données agrégées sur les utilisateurs fidèles***  - uniquement pour les données sur les utilisateurs fidèles du partenaire
* ***Autoriser l'accès à vos données agrégées d'évènements in-app** -* uniquement pour les données d'évènements in-app du partenaire
* ***Autoriser l'accès à vos données agrégées de revenus*** - uniquement pour les données de revenus attribuées au partenaire
* ***Autoriser l'accès à votre tableau de bord Protect360*** - uniquement pour les données Protect360 du partenaire, si la fonctionnalité est activée pour l'annonceur

En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">l'octroi d'autorisations à un réseau publicitaire.</Anchor>

</Accordion>

<div data-zendesk-anchors="h_01HJR1HREQDCQDN6JZRPD356VS=remarque setting-up-bytedance-ads-china=configuration-de-bytedance-ads-china h_01HJR1HREQ6YAW1WPX2BTZS2R7=configuration-de-bytedance-ads-china h_01HJR1HRERBBZFKBHH78BK6QW2=integration-tab activate-partners=activer-les-partenaires h_01HJR1HRER22XX94R1WEQK60GJ=activer-les-partenaires default-postbacks=postbacks-par-d%C3%A9faut h_01HJR1HRERMXHAAGXEFJS4ZS8C=postbacks-par-d%C3%A9faut inapp-events-settings=param%C3%A8tres-des-%C3%A9v%C3%A9nements-in-app h_01HJR1HRERF2Y205KP0J8HZFR3=param%C3%A8tres-des-%C3%A9v%C3%A9nements-in-app h_01HJR1HRER391J6PD9Q0M1MW3F=attribution-link-tab click-attribution-link=lien-dattribution-de-clic h_01HJR1HRERCHNHQGX3X1E1ARDK=lien-dattribution-de-clic h_01HJR1HRER1G4K3PQG1Z7M6CCX=cost-tab api-dimensions-supported=tailles-dapi-prises-en-charge h_01HJR1HRES86BJM4ABQ0B414F1=tailles-dapi-prises-en-charge h_01HJR1HRES470MKXS1S08X202D=ad-revenue-tab h_01HJR1HRESJ7KNFZ9TDHZKESJ7=permissions-tab ad-network-permissions=autorisations-pour-le-r%C3%A9seau-publicitaire h_01HJR1HRESZCC6YV9D40YYSYX0=autorisations-pour-le-r%C3%A9seau-publicitaire" />
