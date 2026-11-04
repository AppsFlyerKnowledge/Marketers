---
title: Configuration de la campagne ironSource
metadata:
  keywords:
    - Supersonic
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
  created_at: '2016-03-06T10:47:23Z'
  edited_at: '2023-10-16T13:08:18Z'
  id: 208005096
  locale: fr
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/fr/articles/208005096
---
> **En bref :** ironSource est un partenaire intégré d'AppsFlyer qui crée des outils de monétisation, d'engagement, d'analyse et de découverte pour les développeurs d'app, les fabricants d'appareils, les opérateurs mobile et les annonceurs. Outre l'attribution mobile basée sur les clics, ironSource offre la possibilité d'enregistrer via AppsFlyer l'attribution des coûts, des revenus publicitaires, du retargeting et post-vue.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/ironsource.png?v=1" width="213px" />

 Remarque : En tant que réseau *toutes-installations*, ironSource préfère recevoir les postbacks pour toute nouvelle installation de votre app, QUELLE QUE SOIT la source, y compris organique. Pour ce faire, sélectionnez *Événements attribués à tout partenaire* pour envoyer tous les postbacks d'installation à ironSource.

La configuration se fait depuis la page **Configuration de l'intégration du partenaire**, mais pour trouver le partenaire vous devez d'abord vous rendre dans le <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations">marketplace</Anchor>.

> 📘 **Remarque**
>
> Avant de configurer une attribution, vous devez <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations#contacter-le-partenaire">contacter le partenaire</Anchor> et ouvrir un compte chez lui.

**Pour activer l'intégration :**

1. Ouvrez le marketplace : dans le menu situé en haut de n'importe quelle page AppsFlyer, cliquez sur **Marketplace**.
2. Trouvez le partenaire voulu et sélectionnez-le.
3. Cliquez sur **Configurer l'intégration**. Vous êtes alors dirigé vers la page de configuration de l'intégration.
4. Dans l'**onglet Intégration**, cochez **Activer le partenaire**.  
   **Remarque :** La case doit rester cochée (option <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">activée</Anchor>) tant que vous travaillez avec le partenaire.
5. Terminez la configuration en suivant les onglets requis, cf description ci-dessous.

La fenêtre de configuration d'ironSource comprend 5 onglets : Intégration, Lien d'attribution, Coût, Revenu publicitaire et Autorisations. Cliquez sur les éléments ci-dessous pour en savoir plus sur la configuration des onglets.

Pour obtenir une description détaillée de l'en-tête de la fenêtre de configuration du partenaire, cliquez <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">ici</Anchor>.

> 👍
>
> * <span id="h_01HCFHXQQ8FRF8D22A85PDN1B1"></span>L'étape <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#d">Paramètres généraux</Anchor> de l'onglet Intégration est **obligatoire** pour tous les partenaires.
> * Toutes les autres étapes sont soit descriptives, soit **optionnelles**

<div id="integration-tab" />

<Accordion title="Onglet Intégration">

<div id="activate-partners" />

### Activer les partenaires

Lors de votre **première visite**, vous devrez déclencher **Activer le partenaire** pour permettre la configuration des paramètres de l'onglet d'intégration. L'option doit rester activée tant que vous travaillez avec le partenaire.  
Pour plus de détails sur l'activation des partenaires, cliquez <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">ici</Anchor>.

<div id="advanced-privacy" />

#### Protection de la vie privée avancée

Pour les apps IOS uniquement, lorsque **la confidentialité avancée (pour iOS 14.5 et +)** est activée, vous pouvez <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#b">choisir quelles données sont transmises à ironSource</Anchor> via les postbacks et les rapports.

<div id="transaction-id" />

### ID de transaction

Pour les apps iOS uniquement, lorsque **Partager l'ID de transaction SKAN** est activé, vous  autorisez AppsFlyer à <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">partager l'ID de transaction des postbacks SKAdNetwork</Anchor> avec ironSource. ironSource peut alors décoder vos valeurs de conversion SKAdNetwork.

<div id="note-2" />

> 📘 **Remarque**
>
> Pour l'interopérabilité de SKAN avec AppsFlyer, contactez votre responsable ironSource afin <Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/general/universal-skan-reporting/#step-1">d'autoriser l'envoi des données SKAN aux MMP</Anchor>.

<div id="general-settings" />

### Paramètres généraux

**ID d'annonceur**

ironSource se connecte à AppsFlyer à l'aide d'un ID publicitaire unique (à 6 chiffres) et d'un mot de passe. Si vous n'avez pas encore l'identifiant et le mot de passe de l'annonceur, vous devez les récupérer dans ironSource avant de poursuivre l'intégration. Si vous les possédez déjà, copiez et collez l'ID et le mot de passe dans les champs concernés.

<div id="install-and-re-engagement-attribution" />

### Attribution de l'installation et de réengagement

Ces deux boutons permettent d'attribuer à ironSource les nouvelles installations et les réattributions d'utilisateurs qui **ont visualisé** votre publicité, mais **n'ont pas cliqué dessus**. En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/measure-view-through-engagements">l'attribution post vue</Anchor>.

**Pour attribuer les nouvelles installations :**

1. Activez **Installer l'attribution post-vue**.
2. Configurez la durée de la fenêtre rétrospective **post-vue** dans l'onglet [Lien d'attribution](/docs/ironsource-campaign-configuration#attribution-link-tab).

**Pour attribuer de nouveaux réengagements aux utilisateurs existants :**

1. Activez **l'attribution de réengagement post-vue.**
2. Configurez la durée de la fenêtre rétrospective **post-vue** dans l'onglet [Lien d'attribution](/docs/ironsource-campaign-configuration#attribution-link-tab).

<div id="default-postbacks" />

### Postbacks par défaut

Pour envoyer des messages automatiques à ironSource lors d'installations et de réengagements d'utilisateurs. Utilisez cette section pour définir **la source des utilisateurs** qui autorisent l'envoi de ces postbacks.

Sélectionnez **Uniquement les événements attribués à ce partenaire** pour les événements provenant uniquement des utilisateurs attribués à ironSource.  
Sélectionnez **Événements attribués à tout partenaire, ou organique** pour que l'ensemble de votre base d'utilisateurs puisse être transmise à ironSource.

<div id="note-3" />

> 📘 **Note**
>
> En tant que réseau *toutes-installations*, ironSource préfère recevoir les postbacks pour toute nouvelle installation de votre app, quelle que soit la source, y compris organique. Pour ce faire, sélectionnez **Événements attribués à tout partenaire, ou organique** pour envoyer tous les postbacks d'installation à ironSource.

<div id="in-app-event-postbacks" />

### Postback d'évènements in-app

Configurer le mappage des événements in-app avec les événements ironSource qui sont envoyés via postback :

1. Activez **Postbacks d'événement in-app.**
2. Cliquez sur **Ajouter un événement** pour ajouter un SDK ou événement de serveur à serveur à la liste. Le tableau suivant explique les champs à remplir :  

| Nom du paramètre | Description |
| --- | --- |
| **Événement AppsFlyer** | Le nom de l'événement tel que reçu par AppsFlyer, soit depuis le SDK intégré à votre app, soit depuis les événements de serveur à serveur.<br />**Astuce** : vous ne voyez pas s'afficher un événement en particulier ?<ul><li>Assurez-vous d'activer l'évènement sur un appareil avec une installation non-organique avant de vérifier à nouveau.</li><li>Saisissez-le dans **Événement AppsFlyer** puis cliquez sur **Créer événement personnalisé**. En savoir plus sur le <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#événements-personnalisés">mappage d'événements personnalisés.</Anchor></li></ul> |
| **mappé à l’événement partenaire** | Le nom ou l'identifiant unique de chaque événement, tel que défini du côté du partenaire. Les différentes configurations du mapping sont :<ul><li>**Champ de texte :** obtenez l'ID d'événement correspondant auprès du partenaire.</li><li>**Liste déroulante :** sélectionnez l’événement AppsFlyer prédéfini approprié.</li><li>**Tel quel** : envoyez les événements à l'état brut, sans mappage du nom.</li></ul> |
| **pour les utilisateurs de** | Sélectionnez l'option d'envoi pour l'événement :<ul><li>**Ce partenaire uniquement** : envoie des postbacks uniquement dans le cas où cet événement est attribué à ce partenaire.</li><li>**Toutes les sources média, y compris organiques** : envoie des postbacks pour les événements attribués à n'importe quel partenaire, ainsi que pour les événements organiques.</li></ul> |
| **Y compris** | <ul><li>**Aucune donnée (par défaut)** : envoie uniquement l'événement en lui-même mais sans sa valeur.</li><li>**Valeurs et revenus** : envoie tous les paramètres de l’événement, **y compris** la valeur de revenu (si présente dans l’événement).</li><li>**Avec valeurs et sans revenu** : envoie tous les paramètres **à l'exception** de la valeur de revenu.</li></ul> |

3. [Facultatif] Cliquez sur l'icône **Ajouter une condition**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/a97c5e34c264ddfa9f94b894520f849a3e59b42be14839ee37c71a5b6cc5ebd7-17612766801425.png" width="30px" /> pour <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#postbacks-conditionnels-dévénements-in-app">définir les conditions</Anchor> d'un événement.
4. Cliquez sur **Enregistrer l'intégration**.
5. [Facultatif] Après avoir enregistré l'intégration, si vous restez sur la page de configuration vous pouvez intégrer d'autres apps à votre partenaire :
   1. Dans le coin en haut à gauche, sous le nom du partenaire, cliquez sur le nom de l’app pour ouvrir la liste des apps.
   2. Sélectionnez une autre app dans la liste déroulante.
   3. Répétez les différentes <Anchor target="_blank" href="/marketers/fr/docs/amazon-ads-campaign-configuration#integration-tab">étapes d’intégration</Anchor> pour l’app sélectionnée.

<div id="note-4" />

> 📘 **Remarque**
>
> * Pour les apps IOS uniquement : la manière dont vous pouvez gérer les données envoyées au partenaire via les postbacks et <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">rapports</Anchor> dépend si la **Confidentialité avancée (pour IOS 14.5 et +)** est <Anchor target="_blank" href="/marketers/fr/docs/tiktok-for-business-advanced-srn-integration-setup#protection-de-la-vie-privée-avancée">activée ou non.</Anchor>
> * Vous pouvez envoyer <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">des postbacks de revenus publicitaires</Anchor> à ironSource pour qu'il optimise les campagnes avec les données des revenus publicitaires :
>   * **Nom de l'événement :** af\_ad\_revenue
>   * **Mappé à :** adRevenue

<div id="attribution-link-tab" />

<Accordion title="Onglet Lien d'attribution">

Générez et enregistrez les liens d’attribution et envoyez-les au partenaire pour attribuer des campagnes spécifiques, des ad sets ou des publicités uniques, à la fois pour les campagnes UA et les campagnes de retargeting. Vous pouvez utiliser un lien à plateforme unique ou <Anchor target="_blank" href="/marketers/fr/docs/onelink-guide">OneLink</Anchor>.<Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">En savoir plus sur la structure et les paramètres des liens d’attribution.</Anchor>

**Pour générer un lien d’attribution,** suivez <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#attribution-link-tab">ces instructions</Anchor>.  
En savoir plus sur la façon dont ironSource définit les clics et les vues.

</Accordion>

<div id="cost-tab" />

<Accordion title="Onglet Coût">

AppsFlyer reçoit le détail des coûts par API. Consultez le <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tableau d'intégration des coûts du réseau publicitaire</Anchor> pour obtenir plus d'infos sur les dimensions, les métriques et les fonctionnalités prises en charge. **Remarque :** Les données de coût nécessitent un abonnement ROI360.

**Pour activer l'API de coût :**

* <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">Veuillez suivre ces étapes pour mettre en place l'intégration</Anchor>

<Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Consultez le statut de votre API de coût</Anchor> et affichez l'heure où AppsFlyer a réussi pour la dernière fois à extraire les données de coûts correspondantes, que ce soit dans le tableau de bord du statut d'intégration des coûts (et des revenus publicitaires), ou dans le tableau de bord du réseau publicitaire individuel.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Onglet Revenus publicitaires">

Si vous affichez des publicités dans l'app envoyée par le partenaire, cette section vous concerne.

* ironSource offre une granularité des revenus publicitaires de niveau agrégé et utilisateur.
* **Divergence possible lors de l'utilisation de la granularité de niveau utilisateur** : les données de revenus publicitaires sont extraites quotidiennement à 14:00 UTC dans ironSource et contiennent les données de la veille. ironSource peut continuer à mettre à jour les données après leur extraction. Ceci peut entraîner une différence de résultat entre les données d'AppsFlyer et d'ironSource.

En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution">l'attribution des revenus publicitaires.</Anchor>

**Pour activer l'API de revenus publicitaires** :

* Suivez ces <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">instructions d'intégration</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Onglet Autorisations">

Dans cet onglet, vous pouvez sélectionner les autorisations à accorder à ironSource, que le partenaire agisse en tant que ad network, agence ou bien les deux. Notez que même si l'attribution est désactivée pour ironSource, l'onglet *Autorisations* est actif et vous pouvez accorder le contrôle à ironSource.

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

En savoir plus sur l'octroi <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">d'autorisations à un réseau publicitaire</Anchor>.

<div id="agency-permissions" />

### Autorisations pour l'agence

Utilisez ces boutons pour autoriser l'agence à gérer sa propre configuration pour votre application :

* **Bouton général** - définir sur Activé pour afficher les options d'autorisations de l'agence
* **Autoriser l'accès à votre rapport de rétention** - uniquement pour les données de rétention de l'agence
* **Autoriser l'accès aux données organiques agrégées**
* **Autoriser la configuration des postbacks d'événement in-app** : permettre au partenaire de configurer l'auto-mappage des postbacks d'événements in-app dans l'onglet Intégration

En savoir plus sur l'octroi <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#autorisations-pour-lagence">d'autorisations à une agence</Anchor>.

</Accordion>

</Accordion>

<div data-zendesk-anchors="h_01HCFHXQQ8111WGWYVA8FAB8J1=remarque h_01HCFHXQQ8XYCKWPVTMK8HF165=integration-tab activate-partners=activer-les-partenaires h_01HCFHXQQ8HCXPEWR4CWY55M2H=activer-les-partenaires advanced-privacy=protection-de-la-vie-priv%C3%A9e-avanc%C3%A9e h_01HCFHXQQ8ABQYRSBGC7Z1F1SV=protection-de-la-vie-priv%C3%A9e-avanc%C3%A9e transaction-id=id-de-transaction h_01HCFHXQQ8Q3BX7GSGD5MH4QT8=id-de-transaction h_01HCFHXQQ8D26KT5E6YEQ50DA4=remarque-1 general-settings=param%C3%A8tres-g%C3%A9n%C3%A9raux h_01HCFHXQQ8J0ZC9FGCNTPMKHK6=param%C3%A8tres-g%C3%A9n%C3%A9raux install-and-reengagement-attribution=attribution-de-linstallation-et-de-r%C3%A9engagement h_01HCFHXQQ8V2E8982XRSY4G50F=attribution-de-linstallation-et-de-r%C3%A9engagement default-postbacks=postbacks-par-d%C3%A9faut h_01HCFHXQQ8Q27JXG2V7G4XZX43=postbacks-par-d%C3%A9faut h_01HCFHXQQ8XZ6H3733GPR3ZFYE=note inapp-event-postbacks=postback-d%C3%A9v%C3%A8nements-in-app h_01HCFHXQQ891GH196XFRXY8MYS=postback-d%C3%A9v%C3%A8nements-in-app h_01HCFHXQQ8VF25W10CWQHTEAYW=remarque-2 h_01HCFHXQQ8AYNTCH9GHZJG594E=attribution-link-tab h_01HCFHXQQ87EBRW9NBY58XYFGP=cost-tab h_01HCFHXQQ8XZ8XQFH3XRFVHRZV=ad-revenue-tab h_01HCFHXQQ891P7ET9Q4BSQWJXT=permissions-tab ad-network-permissions=autorisations-pour-le-r%C3%A9seau-publicitaire h_01HCFHXQQ86VNX9WRFEZECYV7R=autorisations-pour-le-r%C3%A9seau-publicitaire agency-permissions=autorisations-pour-lagence h_01HCFHXQQ936CQ1FVHCRC58H4C=autorisations-pour-lagence" />
