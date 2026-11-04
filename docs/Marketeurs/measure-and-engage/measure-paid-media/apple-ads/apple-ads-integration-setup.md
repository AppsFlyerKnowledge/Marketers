---
title: Configuration de l'intégration Apple Search Ads
metadata:
  keywords:
    - cost
    - Advertisers
    - apple search ads
    - asa
    - apple ads
    - apple search advanced
    - apple search ads campaign group
    - apple keywords
    - apple searchads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-08-31T09:04:38Z'
  edited_at: '2024-11-13T12:23:49Z'
  id: 213747963
  locale: fr
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/fr/articles/213747963
---
> **En bref :** Apple Search Ads (ASA), un partenaire SRN d'AppsFlyer, aide les utilisateurs à trouver votre application dans l'App Store à l'aide de mots-clés.

<Image alt="apple_search_ads.png" src="https://support.appsflyer.com/hc/article_attachments/17210504660625" width="217px" />

C'est la pertinence de l'application qui définit si votre publicité s'affichera en réponse à une recherche dans l'App Store. La manière dont l'utilisateur répond à une publicité indique la pertinence de cette même publicité. ASA utilise la réponse de l'utilisateur comme curseur pour décider quelles publicités afficher en premier.

> 📘 **Note**
>
> * ASA fournit des données via API pour [l'attribution mobile basée sur les clics](/docs/apple-ads-integration-setup#asa-attribution), <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide">le retargeting d'utilisateur</Anchor> et les <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview">coûts</Anchor> (sous couvert d'un abonnement ROI360)
> * Alors qu'ASA affiche des mesures de fréquentation dans son tableau de bord, l'intégration avec AppsFlyer reste basée sur les clics, ASA ne réagissant qu'aux clics publicitaires des utilisateurs pour l'attribution.

<div id="set-up-apple-ads-integration" />

## Configurer l'intégration ASA

<div id="get-started" />

<Accordion title="Démarrer">

**Conditions préalables**

* C'est la dernière version du SDK iOS AppsFlyer qui est adoptée

**Configurez les Apple Search Ads dans AppsFlyer :**

L'installation se fait à partir de la page **Intégrations actives** mais pour trouver de nouveaux partenaires, vous devez d'abord vous rendre sur la page Marketplace partenaire Allez au bout de la configuration pour chacun des onglets, cf ci-après. ci-dessous.

> 📘 **Remarque**
>
> Avant de configurer l'intégration, vous devrez : Contacter le partenaire et ouvrir un compte chez eux.

Onglet Intégration

</Accordion>

Apple Search Ads, qui est un SRN, s'intègre à AppsFlyer via API. Les paramètres de postback n'existent donc pas. Renseignez les paramètres suivants : en fonction de vos objectifs d'attribution.

<table><thead><tr><th>Section </th><th>Détails</th></tr></thead><tbody><tr><td>Activation de l'intégration</td><td><p> <strong>Pour activer ou modifier l'intégration :</strong> </p><ol><li> <span><strong>Activation :</strong><span> </span>dans AppsFlyer, dans le menu latéral, choisissez </span><strong><span>Collaboration</span><span> </span></strong><span>&gt; </span><strong>Partenaire Marketplace</strong><span>.<br/><strong>Modification :</strong> dans AppsFlyer, dans le menu latéral, sélectionnez <strong>Collaborer</strong> &gt; <strong>Intégrations actives</strong>.</span> </li><li>Sélectionnez le partenaire de votre choix.</li><li> Cliquez sur <span>Configurer l'intégration</span>. Vous êtes alors dirigé vers la page de configuration de l'intégration. Page </li><li> Dans <span><strong>l'onglet intégration</strong>:</span> Dans l'onglet  Integration , sélectionnez l'app à intégrer et cochez l’option <span> </span><strong>Activer le partenaire</strong><span> </span>.<br/> <strong>Remarque :<span> La case doit rester cochée </span>(activée)/span&gt; tant que vous collaborez avec le partenaire. </strong> </li><li> Complétez la configuration en utilisant les comme décrit ci-dessous. </li></ol></td></tr><tr><td>Attribution des installations</td><td><p> Fenêtre rétrospective post-clic d'installation </p><p> Définissez la durée maximale entre le clic et l'installation. Faire Cela permet à AppsFlyer d'attribuer les installations (premier les lancements) qui ont lieu dans la fenêtre de rétroaction à l'ASA. </p><p>Période :  1 (30 jours) </p></td></tr><tr><td rowspan="2">Réinstallations </td><td><p> <strong>Attribution de réinstallation</strong> </p><p> <strong>Attribution de réinstallation</strong> est activée. AppsFlyer peut attribuer les réinstallations à l'ASA. </p><p> Réinstaller les paramètres de la fenêtre de rétrospection de l'attribution sont définis en fonction de l'attribution de l'installation Réglages : </p><p> Si l'utilisateur se trouve dans la zone Fenêtre de réattribution (définie au moment de l'installation initiale), la fonction est attribuée à l'ASA en tant que réinstallation. </p><p> La réinstallation s'affiche dans le tableau de bord de retargeting. À propos du tableau de bord général </p><p> store_reinstall Le champ "données brutes" est défini sur "true".  </p><p>À l'heure actuelle, le retargeting ASA ne prend pas en charge les réengagements.</p></td></tr><tr><td><p> <strong>Fenêtre d'inactivité</strong> </p><p> Définir l'utilisateur Seuil d'inactivité (en jours) pour contrôler l'impact du reciblage Campagnes  </p></td></tr></tbody></table>


<div id="cost-tab" />

<Accordion title="Onglet Coût">

L'intégration des coûts fournit les données agrégées suivantes :

* Données sur les coûts pour vos campagnes, vos adsets, vos zones géographiques/pays et vos mots-clés. keywords Voir le <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tableau d'intégration des coûts des réseaux publicitaires</Anchor> pour obtenir des informations détaillées sur les dimensions, les mesures et les Caractéristiques  
   **Remarque :** Les données de coût nécessitent un abonnement ROI360.
* Données sur les clics, les impressions et les mots-clés enrichis, les noms de campagne et les ensembles d'annonces.

> 📘 **Remarque**
>
> * L'utilisation de plusieurs comptes ASA est prise en charge. En d'autres termes, si vous menez des campagnes pour la même app en utilisant différents comptes ASA, AppsFlyer pourra recevoir les données de l'ensemble des comptes.
> * Les données relatives aux coûts des "groupes de campagne" ne sont pas étayées par le rapport de la Commission européenne. API de reporting de l'ASA, les données sur les "groupes de campagne" ne sont donc pas disponibles. Dans AppsFlyer  :
> * Pour vous connecter avec Apple, il vous faut les autorisations ASA de niveau admin (Compte en lecture seule ou Compte en lecture et écriture).
> * Lorsque vous vous connectez avec Apple, tous les certificats d'API qui ont déjà été fournis cessent d'extraire les données.
> * Lorsque vous vous connectez via Apple, l'autorisation des groupes de campagne de l'ASA n'est pas permanente. Cela signifie que lorsque vous intégrez une nouvelle application, l'autorisation pour les groupes de campagne choisie pour les applications précédentes est révoquée, à moins qu'elle ne soit à nouveau choisie.
> * Lorsque vous vous connectez avec Apple, vous ne pouvez pas utiliser de <Anchor target="_blank" href="https://support.apple.com/en-il/guide/apple-business-manager/axmb19317543/web">connexion fédérée</Anchor>.

**Pour permettre le calcul des coûts, des clics, des impressions et des données enrichies :**

* Suivre <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">Ces instructions pour mettre en place l'intégration</Anchor>

<Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Consulter l'état de votre API de coûts</Anchor> et la dernière fois qu'AppsFlyer a réussi à obtenir des données sur les coûts correspondants dans le tableau de bord de l'intégration des coûts (et des recettes publicitaires), ou dans le tableau de bord de chaque réseau publicitaire.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Onglet Autorisations">

<Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">Définir les autorisations des réseaux publicitaires et des agences.</Anchor>

</Accordion>

<div id="set-up-agencies-and-apple-ads-marketing-partners" />

## Configurer les agences et les partenaires marketing ASA

<div id="principles" />

<Accordion title="Principes de base">

Apple Search Ads Partenaire marketing Agence

Les annonceurs et les agences peuvent choisir de collaborer avec des partenaires marketing d'ASA pour obtenir leur rapports et optimiser leurs campagnes sur ASA.

Le tableau ci-dessous liste les différences qui existent entre les agences et les partenaires marketing.

<div id="agency-vs-marketing-partner" />

#### Différence entre agence et partenaire marketing

|  | Agence | Partenaire marketing |
| --- | --- | --- |
| AppsFlyer envoie des postbacks | Non | Oui |
| technologie | Lancement de campagnes en votre nom | Proposent une solution technologique à valeur ajoutée pour optimiser les campagnes |

<div id="configuring-agencies-and-marketing-partners" />

#### Configurer les agences et les partenaires marketing

La liste ci-dessous vous permet de vérifier si toutes les étapes du processus de configuration ont bien été remplies. Des instructions précises par type de partenaire sont disponibles dans les sections suivantes.

<div id="configuration-steps-checklist" />

#### Liste pour vérifier les étapes de la configuration

| Configuré par | Intégration avec une agence | Intégration avec un partenaire marketing |
| --- | --- | --- |
| Annonceur | <ol><li>Dans AppsFlyer, dans l'onglet Intégration ASA, sélectionnez **Activer le partenaire.**</li><li>Dans l'onglet Autorisations de l'agence, sélectionnez l'agence et activez **Autorisation de l'agence.**</li></ol> | <ol><li>Dans l'onglet Intégration ASA, cochez**Activer le partenaire**.</li><li>Dans le tableau de bord ASA, récupérez **l'ID de groupe de campagne** du partenaire marketing.</li><li>Dans l'onglet intégration du partenaire marketing :<ol><li>Cochez **Activer le partenaire**.</li><li>Définissez le groupe de campagne.</li><li>Configurez le postback des événements in-app.</li></ol></li></ol> |
| Agence | Dans l'onglet Intégration ASA, définissez le nom de **Apple Search Ads Campaign Group.** | N/A |

</Accordion>

<div id="marketing-partner-setup" />

<Accordion title="Configuration du partenaire marketing">

**Pour configurer un partenaire marketing :**

1. Si besoin est, activez l'intégration des **Apple Search Ads :**
   1. Dans AppsFlyer, rendez-vous dans **Configuration** > **Partenaires actifs intégrés** > **Apple Search Ads**.
   2. Cochez **Activer le partenaire**.
   3. Cliquez sur **Enregistrer**.
2. **Dans votre tableau de bord Apple Search Ads** : Obtenir le paramètre d'ID de groupe de la campagne Apple Search Ads lié au partenaire marketing. La capture d'écran suivante vous indique comment localiser l'ID.
3. **Dans AppsFlyer, configurez le partenaire marketing ASA :**
   1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Collaboration** > **Intégration active**.
   2. Recherchez le **partenaire marketing** *Apple Search Ads.*  **La liste des partenaires marketing s'affiche.**
   3. Sélectionnez un partenaire marketing.
   4. Cochez **Activer le partenaire**.
   5. Saisissez **l'ID Apple Search Ads Campaign Group** du partenaire que vous avez récupéré à l'étape précédente. Saisir les chiffres uniquement.
   6. Cliquez sur **Enregistrer**.
4. [Optionnel] Configurez le postback des événements in-app :
   1. Activez **Postback des événements in-app.**
   2. Cliquez sur **Ajouter un événement** pour ajouter un événement SDK à la liste.
   3. Remplissez les paramètres suivants :
      1. Nom de l'évènement SDK Le nom de l'événement, tel qu'il a été reçu par AppsFlyer à partir du SDK intégré à votre application ou des événements de serveur à serveur.  Astuce Astuce : si l'événement que vous cherchez n'est pas dans la liste, vérifiez que vous activez bien l'événement sur un appareil avec une installation non-organique.
      2. Envoyer les revenus Sélectionnez l'une des options suivantes : Pas de valeurs et pas de revenus, Valeurs et pas de revenus, ou Valeurs et revenus.
5. **Cliquez sur Enregistrer l'intégration.**

</Accordion>

<div id="agency-setup" />

<Accordion title="Configuration de l'agence">

Les annonceurs autorisent les agences à exécuter des campagnes via Apple Search Ads. Les annonceurs et les agences définissent chacun des paramètres de configuration dans AppsFlyer, cette section les abordent en détail.

**Prérequis**

Avant de configurer une agence sur AppsFlyer, l'agence et l'annonceur doivent suivre les étapes suivantes sur la plateforme ASA :

* **Agence :**
  1. Créez des groupes de campagnes distincts au sein du compte de l'agence.
  2. Invitez l'annonceur en tant que responsable de groupe de campagne ou par le biais du rôle de liaison des comptes à connecter son compte App Store Connect.
* **Annonceur** : Après avoir reçu l'invitation à lier les comptes, l'annonceur doit lier les groupes de campagne à son compte App Store Connect.

Voir la documentation de l'ASA sur la <Anchor target="_blank" href="https://searchads.apple.com/help/get-started/0012-link-app-store-connect-accounts">façon de lier le compte App Store Connect d'un client à un compte d'agence.</Anchor>

**Apple Search Ads campaign group**

* Les campagnes d'agences et les campagnes d'annonceurs doivent faire partie de groupes de campagne Apple Search Ads bien distincts.
* N'utilisez pas de caractère spécial ni d'espace dans le nom de groupe.
* Lorsque vous vous connectez via Apple, l'autorisation des groupes de campagne de l'ASA n'est pas permanente. Cela signifie que lorsque vous intégrez une nouvelle application, l'autorisation pour les groupes de campagne choisie pour les applications précédentes est révoquée, à moins qu'elle ne soit à nouveau choisie. Vous devrez sélectionner **Accès limité** et chacun des groupes de campagne concernés (liés aux applications que vous souhaitez connecter pour l'annonceur).

<div id="advertiser-actions" />

#### **Actions de l'annonceur**

**Conditions préalables** :

<Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#autorisations-pour-lagence">Accorder l'autorisation à une agence</Anchor>.

**Pour activer l'attribution des Apple Search Ads, l'annonceur doit  :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Collaboration** > **Intégration active**.
2. Sélectionnez **Apple Search Ads.**
3. Allez dans l'onglet **Intégration**, et sélectionnez **Activer le partenaire**.
4. [Optionnel] Si vous souhaitez attribuer les utilisateurs qui réinstallent l'app au cours de la fenêtre de réattribution, activez l'option **Attribution de réinstallation.**
5. Cliquez sur **Enregistrer**.

<div id="agency-actions" />

#### **Actions de l'agence**

1. **Dans votre tableau de bord Apple Search Ads** : Obtenez l'identifiant de votre groupe de campagne. La capture d'écran suivante vous indique comment localiser l'ID. N'obtenir que les chiffres. ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)
2. Dans AppsFlyer, sélectionnez une application.
3. Dans le menu latéral, sélectionnez **Collaboration** > **Intégrations actives.**
4. Sélectionnez **Apple Search Ads.**
5. Saisissez le paramètre **ID de campagne Apple Search Ads**. Remarque! Saisir des chiffres (uniquement des nombres)
6. Cliquez sur **Enregistrer**.

> 📘 **Remarque**
>
> Lorsqu'une agence travaille avec un partenaire marketing Apple Search Ads, l'agence doit définir le même nom de groupe de campagne sur la page de configuration d'Apple Search Ads et sur la page de configuration du partenaire marketing.

<div id="cost-clicks-and-impressions-data" />

### Données sur le coût, les clics et les impressions

Si vous activez l'API de coût, AppsFlyer reçoit les données de coûts, de clics, et d'impression d'ASA via l'API.  Consultez le tableau d'intégration des coûts du réseau publicitaire <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">pour obtenir plus d'infos sur les dimensions, les métriques et les fonctionnalités prises en charge. **Remarque** : Les données de coût nécessitent un abonnement ROI360. Sans ROI360, seules les données de clic et d'impression sont transmises.</Anchor>

**Pour activer l'API de coût :**

* <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">Suivez</Anchor> ces instructions d'intégration.  Suivez  **ces instructions d'intégration** . Assurez-vous de sélectionner l'une des options suivantes lorsque vous êtes invité à vous connecter à votre compte Apple Search Ads dans Sélectionner les autorisations :
  * **Compte avec autorisation lecture/écriture**
  * **Compte en lecture seule**  
    **Remarque** : Compte en lecture seuleRemarque : si vous choisissez Accès limité et un groupe de campagnes spécifique, des erreurs de données peuvent survenir.

<Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Consultez le statut de votre API de coût</Anchor> et affichez l'heure où AppsFlyer a réussi pour la dernière fois à extraire les données de coûts correspondantes, que ce soit dans le tableau de bord du statut d'intégration des coûts (et des revenus publicitaires), ou dans le tableau de bord du réseau publicitaire individuel.

</Accordion>

<div id="disable-agencies-and-marketing-partners" />

<Accordion title="Désactiver les agences et les partenaires marketing">

**Pour cesser d'enregistrer l'attribution des installations Apple Search Ads générées par des agences ou des partenaires marketing :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Collaboration** > **Intégration active**.
2. Sélectionnez l'agence ou le partenaire marketing en fonction.
3. Supprimez le contenu du champ **ID de groupe de campagne Apple Search Ads.**
4. Cliquez sur **Enregistrer l'intégration**.

</Accordion>

<div id="additional-information" />

## Informations supplémentaires

<div id="asa-attribution" />

<Accordion title="Attribution ASA">

Apple Search Ads fonctionne indépendamment du SKAdNetwork et attribue les utilisateurs de manière déterministe, quel que soit leur niveau de consentement ATT. Cela signifie que pour les utilisateurs attribués à ASA, vous disposez de toute la gamme des fonctionnalités et mesures inclues dans notre <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model">modèle d'attribution LTV.</Anchor>

L'attribution ASA ne repose pas sur l'IDFA : l'attribution se fait avec un jeton issu de l'appareil (attribution déterministe), et elle dépend du niveau de consentement ATT :

| **Consentement ATT** | **Heure de clic disponible** | **Fenêtre rétrospective des clics** | **Remarques** |
| --- | --- | --- | --- |
| Oui | Oui | Défini par l'annonceur | Règles d'attribution de dernier clic AppsFlyer utilisées |
| Non | Non | 30 jours  <br />(fixé par l'ASA) | L'heure du clic n'est pas fourni. La priorité est donnée aux candidats déterministes |

</Accordion>

<div id="discrepancies" />

<Accordion title="Écarts dans les mesures">

AppsFlyer et Apple Search Ads utilisent une logique d'attribution différente, des écarts entre les deux plates-formes sont donc à prévoir. <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns#attribution">Apple Search Ads</Anchor>, qui est un SRN, rapporte les nouvelles installations via API.

**Rapports Apple Search Ads transmis à AppsFlyer via API**

* Les campagnes sont agrégées par géo.
* Les éléments suivants ne sont pas rapportés : Impressions, écoutes ou coût des géos ayant moins de 100 impressions pour une campagne donnée.
* Lors du regroupement par géo dans AppsFlyer, les zones avec des données non disponibles ne sont pas affichées et le total des données non disponibles apparaît sous N/A.

<div id="retargeting-related-discrepancies" />

### Écarts concernant le retargeting

Le mécanisme d'attribution de retargeting d'AppsFlyer permet aux annonceurs de mesurer et analyser les campagnes de retargeting, ainsi que les campagnes d'acquisition d'utilisateur.

Les chiffres suivant illustrent les écarts qui peuvent survenir en cas de campagnes de retargeting lancées sur Apple Search Ads (et ce quels que soient les paramètre de mesure du retargeting).

**Retargeting activé**

[![ASA R Enabled2.jpg](https://files.readme.io/0d26cc4844aa97adb793a266cb2a51961a1345e71a24eec305fcc16539d86027-31197524086801.jpg)](https://files.readme.io/0d26cc4844aa97adb793a266cb2a51961a1345e71a24eec305fcc16539d86027-31197524086801.jpg)

**Retargeting désactivé**

[![ASA_R_Disabled.png](https://files.readme.io/425a0e1e802482a00230d7ceaebdcaa7f74523fb6feb75d60168f94b56886201-31197514618001.png)](https://files.readme.io/425a0e1e802482a00230d7ceaebdcaa7f74523fb6feb75d60168f94b56886201-31197514618001.png)

<div id="additional-reasons-for-discrepancies" />

### Motifs supplémentaires d'écart

Le tableau qui suit répertorie les principales raisons qui justifient ces écarts :

| Écarts | Apple Search Ads | AppsFlyer |
| --- | --- | --- |
| <span id="differences-related-to-appsflyer-sdk-versions"></span>Différences inhérentes aux versions du SDK AppsFlyer | Comptabilise les conversions, quelle que soit la version du SDK AppsFlyer. | Pour AdsServices, le SDK V6.1.3 et + est requis pour obtenir la bonne attribution. |
| <span id="limit-ad-tracking-lat-and-att"></span>Suivi Publicitaire Limité (LAT) et ATT. | Comptabilise systématiquement la conversion.<br /><br />Si votre campagne est restreinte selon l'âge et le sexe, les utilisateurs LAT sont exclus de la campagne.<br /><br />Les utilisateurs d'Apple qui ont moins de 18 ans sont toujours LAT. | Les conversions LAT sont attribuées à l'organique.<br /><br />Si AdServices est implémenté et iOS14.3 et + est installé, les utilisateurs qui n'ont pas donné leur accord sont attribués correctement. |
| <span id="counting-users"></span>Comptage des utilisateurs | Comptabilise les utilisateurs d'après les téléchargements | Comptabilise les utilisateurs d'après la première ouverture d'app |
| <span id="reinstall-a-user-after-installing-the-app-deletes-it-clicks-on-a-search-ad-then-installs-the-app-again"></span>reinstall Réinstallation : après avoir installé l'app, un utilisateur la supprime, puis clique sur une Search Ad, et installe à nouveau l'application | Est comptabilisé comme une conversion (installation) | <ul><li>Avec l'IDFA : AppsFlyer identifie la réinstallation et ne la prend pas en compte pour l'AU. Astuce ! Astuce ! Activez le retargeting, la réinstallation sera alors rapportée comme une installation de retargeting (c'est à dire une réattribution)</li><li>Sans l'IDFA : Sans IDFA : AppsFlyer peut s'appuyer sur l'IDFV pour déterminer s'il s'agit d'une réinstallation ou d'une nouvelle installation<ol><li>Si une ou plusieurs autres apps du fournisseur sont installées sur l'appareil, AppsFlyer attribue l'ASA avec une réattribution.</li><li>Sinon (aucune autre app n'existe), AppsFlyer attribue l'ASA avec une nouvelle installation.</li></ol></li></ul> |
| <span id="click-lookback-window"></span>Fenêtre rétrospective des clics | Fenêtre fixe de 30 jours | Pour les réponses d'AdServices qui n'incluent pas l'heure du clic, la fenêtre rétrospective de clic est définie sur 30 jours. |
| <span id="winning-click"></span>Remporte un clic | S'attribue toujours à lui-même si l'utilisateur s'est engagé et a téléchargé l'app. | A une visibilité sur plusieurs réseaux, et attribue selon la méthode du dernier clic |
| <span id="install-time"></span>Heure d'installation | Heure de téléchargement de l'app | Première app ouverte |
| <span id="time-zone"></span>Fuseau horaire | Fuseau horaire local de l'app store | Fuseau horaire UTC, ou tel que défini dans les paramètres AppsFlyer |
| <span id="conversion-data"></span>Données de conversion | Cela peut prendre plus de 5 secondes avant qu'AppsFlyer ne soit informé que les Search Ads ont provoqué l'installation | Attributs dans les 5 secondes, soit au moment où l'API de données de conversion répond. Si aucune donnée n'a été reçue, alors la réponse fournie est organique. |
| <span id="cost-data"></span>Données de coûts | Coût des rapports pour tous les mots-clés | Ne fournit pas de données sur les coûts pour les mots clés qui contiennent des lettres majuscules, tant dans le tableau de bord que l'API de cohorte. |
| <span id="geo-locations"></span>Emplacements géo | Apple Search Ads permet aux annonceurs de cibler les utilisateurs en fonction de leur pays et de leur région. Apple Search Ads prend en charge un nombre limité de [**pays**](https://searchads.Apple.com/storefronts/). | AppsFlyer reconnaît la localisation géographique exacte de l'utilisateur d'après l'adresse IP, et signale ainsi les géos non disponibles sur Apple Search Ads.<br /><br />Astuce ! Astuce ! Les utilisateurs qui installent l'app lorsqu'ils sont dans le pays de l'app store auront les mêmes données géo pour AppsFlyer et Apple Search Ads |

</Accordion>

<div id="tips" />

<Accordion title="Nos conseils">

Travailler avec Apple Search Ads vous permet de collecter de précieuses données marketing, ce qui peut avoir un impact sur vos efforts d'acquisition d'utilisateurs sur toutes les sources média pour vos apps iOS.

Conseils pour vous aider à optimiser votre utilisation d'Apple Search Ads :

| Conseil | Détails |
| --- | --- |
| <span id="get-keyword-data"></span>Obtenir des données de mots clés | Apple Search Ads partage des données de mots clés avec AppsFlyer. Vous pouvez afficher les données de mots clés dans les données brutes et les outils d'analyses de type tableau croisé dynamique, rétention, ou cohorte.<br /><br />**Remarque :**<ul><li>L'obtention des données de mots clés peut prendre entre 8 et 12 heures et, dans certains cas, elles peuvent contenir l’ID du mot clé seul, sans le terme clé.</li><li>Pour obtenir les données des mots-clés, l'option Coût doit être activée. Les données des mots-clés sont fournies dans le cadre de [l'intégration des coûts](/docs/apple-ads-integration-setup#cost-tab), sans qu'il soit nécessaire d'avoir un abonnement ROI360.</li></ul>Si certaines données de mots-clés manquent sur AppsFlyer, cela peut être dû aux éléments suivants :<ul><li>**Type d'emballage :** Les données relatives aux mots-clés sont partagées par Apple Search Ads avec les annonceurs qui ont souscrit à l'offre [avancée](https://searchads.Apple.com/advanced/) Apple Search Ads.</li><li>Type de campagne Vous pouvez configurer différents types de correspondance de mots-clés de campagne dans Apple Search Ads. En fonction du type de correspondance, Apple Search Ads partage les mots clés comme suit :<ul><li>**Correspondance exacte (Exact match) : Les mots-clés exacts recherchés par l'utilisateur**</li><li>**Match large (Broad match) :** Les mots-clés utilisés par Apple pour effectuer la recherche. Ils sont similaires aux termes de recherche effectifs de l'utilisateur.</li><li>**Correspondance de recherche (Search match) :** Apple **ne** partage **pas** ces mots-clés avec les annonceurs.</li></ul></li></ul>**Utilisez uniquement des campagnes de recherche de correspondance exacte ou large** pour obtenir des données complètes sur les mots clés. |
| <span id="compare-the-quality-of-users-based-on-keyword-data"></span>Comparez la qualité des utilisateurs en fonction des données des mots clés | Tous les mots-clés ne sont pas égaux, ce qui signifie que même si différents mots-clés ont le même coût, la qualité des utilisateurs attirés peut être différente. Utilisez les rapports de rétention ou de <Anchor target="_blank" href="/marketers/fr/docs/pivot-table-user-metrics">tableaux croisés dynamiques</Anchor> pour identifier les mots-clés qui optimisent votre ROI. |
| <span id="analyze-keyword-cost"></span>Analyser le coût des mots-clés | La plate-forme contient des données agrégées de coût des mots-clés lorsque les campagnes de mots-clés de l'ASA sont configurées sur [«correspondance exacte» ou «correspondance élargie».](/docs/apple-ads-integration-setup#get-keyword-data) Les données de coût des mots-clés présentent les caractéristiques suivantes :<ul><li>Les données historiques sont disponibles à compter du 13 octobre 2019.</li><li>Dimensions :<ul><li>Date</li><li>Campagne</li><li>Adset</li></ul></li><li>Outils d'analyse :<ul><li><Anchor target="_blank" href="/marketers/fr/docs/cohort-and-retention-dashboard">Cohorte</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/pivot-table-user-metrics">Tableau croisé</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/master-api-user-acquisition-metrics-via-api">API principale</Anchor></li></ul></li></ul>**Limitations**<ul><li>Utilisez uniquement les dimensions indiquées pour filtrer et regrouper les requêtes de données de coûts. Par exemple, n'appliquez pas de filtre ou de regroupement en utilisant le paramètre Geo.</li></ul>**<span id="cohort-example"></span>Exemple de cohorte**<br />L'exemple suivant montre comment configurer la cohorte pour afficher les informations de coûts et de ROI.<br /><br />**Mise en place de la cohorte**<br /><br />[<Image alt="CohortRequest.png" src="https://files.readme.io/73004ab25cfff029786ec4601e22a0ac4b02a146141787b51bda1a02d5412330-31197524095377.png" width="327px" />](https://files.readme.io/73004ab25cfff029786ec4601e22a0ac4b02a146141787b51bda1a02d5412330-31197524095377.png)<br /><br />**Tableau de résultats de cohorte**<br /><br />Le coût total et le ROI de la cohorte sont affichés dans le tableau qui suit<br /><br />[<Image alt="CohortTable.png" src="https://files.readme.io/ebceedb82207bdbc7f58daafc0557630ac35a73a11b14d207a7283b93294073d-31197514633233.png" width="429px" />](https://files.readme.io/ebceedb82207bdbc7f58daafc0557630ac35a73a11b14d207a7283b93294073d-31197514633233.png)<br /><br />**<span id="pivot-example"></span>Exemple de tableau croisé dynamique**<br /><br />**Configuration des tableaux croisés dynamiques**<br /><br />[<Image alt="Pivot_define.png" src="https://files.readme.io/29ad177a5ef681f8358968092005d8ba871f3dd06661a8dea6d186318c08a476-31197524107153.png" width="413px" />](https://files.readme.io/29ad177a5ef681f8358968092005d8ba871f3dd06661a8dea6d186318c08a476-31197524107153.png)<br /><br />**Tableau de résultats de tableau croisé dynamique**<br /><br />[<Image alt="Pivot.png" src="https://files.readme.io/ef9766de2059d0608e8ae6dc063053f2926ffa296e7eca2e13a1bc4171921d2c-31197524111505.png" width="439px" />](https://files.readme.io/ef9766de2059d0608e8ae6dc063053f2926ffa296e7eca2e13a1bc4171921d2c-31197524111505.png) |
| <span id="find-the-best-performing-creative-set"></span>Trouvez l'ensemble créatif le plus performant | ![creative_sets.png](https://files.readme.io/ef8e38d67121283742dcbd1faef11d94a8ea1c612dc258611e72cbf826d7ef8f-31197524112785.png)<br /><br />Il est recommandé de tester la réponse des prospects aux différents ensembles de créations que vous utilisez. Les ensembles de créations les plus performants affichent les taux de conversion les plus élevés. De plus, les meilleurs ensembles de créations convertissent les utilisateurs avec un niveau d'engagement plus élevé.<br /><br />Cela affecte tous vos prospects iOS, pas seulement les prospects ASA, car ils atteignent tous la page de votre app dans l'App Store. Cependant, avec les installations ASA, AppsFlyer indique l'ID de l'ensemble de créations dans le paramètre <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary">AD ID</Anchor> **des données brutes**, ce qui vous permet de comparer les performances de différents ensembles de créations. |
| <span id="target-redownloaders"></span>Ciblez les utilisateurs qui ont déjà téléchargé l'app | Vos anciens utilisateurs sont probablement le meilleur public à cibler à l'aide de l'ASA.<br /><br />Un utilisateur qui a désinstallé votre app et qui, à la suite de votre campagne de retargeting ASA , l'installe à nouveau, est nommé « Re-Downloader » par ASA. Si la réinstallation est effectuée pendant la <Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window">fenêtre de réattribution</Anchor> , AppsFlyer voit cela comme une réattribution. Dans tous les autres cas, elle est traitée comme une nouvelle installation.<br /><br />![ASACGroupID.png](https://files.readme.io/ebdc380f2abc3e9a3b134cd258d90ae32f75b3ee4d9eadde39adbc728daae523-31197514645265.png) |

</Accordion>

<div id="asa-change-log" />

<Accordion title="Log des changements ASA">

| Date d'entrée en vigueur | Mise à jour/modification |
| --- | --- |
| <span id="20230207"></span>07-02-2023 | Les paramètres d'attribution enrichis `Nom de la campagne`, `Nom de l'annonce` et `Mots-clés` ne sont disponibles que lorsque l'onglet Coût est activé, quelle que soit votre formule d'abonnement.  <br />**Cela signifie que pour que vos tableaux de bord et vos rapports de données brutes affichent des noms de campagne, des noms d'adset ou des mots-clés, l'onglet Coût doit être activé.** |
| <span id="20220216"></span>16/02/2022 | Les mots-clés sont disponibles via l'API de coût. Vous devez activer l'API sur la page d'intégration d'Apple Search Ads. Remarque! L'API est accessible à tous les annonceurs, quelle que soit leur formule d'abonnement. |
| <span id="20210407"></span>07/04/2021 | Configuration de l'intégration Apple Search Ads L'ASA fonctionne indépendamment du SKAdNetwork et attribue les utilisateurs de manière déterministe. Cela signifie que pour les utilisateurs attribués à ASA, vous disposez de toute la gamme des fonctionnalités et mesures inclues dans notre modèle d'attribution LTV. |
| <span id="20210307"></span>07/03/2021 | Apple Search Ads déploie l'API de gestion des campagnes V4.0. L'API gère les coûts et autres données en lien avec les campagnes. Il n'a aucun impact sur l'attribution. Nous sommes en train d'adopter l'API mise à jour. Aucune action requise. |
| <span id="20210215"></span>15/02/2021 | À compter d'aujourd'hui, les champs du nom de campagne et du nom de l'adset peuvent être renseignés lorsque vous activez [l'API de coût ASA.](/docs/apple-ads-integration-setup#cost-tab) L'API est disponible pour tous les annonceurs, quel que soit le plan d'abonnement. |

Mises à jour et modifications ASA

</Accordion>

<div id="availability-of-apple-search-ads-campaign-parameters" />

<Accordion title="Disponibilité des paramètres de campagne Apple Search Ads">

Le tableau ci-dessous liste les différents paramètres d’attribution disponibles dans les rapports de données brutes ou dans le tableau de bord.

| Paramètre des rapports de données brutes | Disponibilité |
| --- | --- |
| Nom de la campagne | Pour que ce paramètre soit disponible, vous devez d'abord activer l'API de [Coût](/docs/apple-ads-integration-setup#cost-tab) sur la page d'intégration Apple Search Ads. L’API est disponible pour tous les annonceurs, quel que soit leur type d'abonnement. |
| ID de la campagne | Toujours disponible |
| Nom de l'adset | Pour que ce paramètre soit disponible, vous devez d'abord activer l'API de [Coût](/docs/apple-ads-integration-setup#cost-tab) sur la page d'intégration Apple Search Ads. L’API est disponible pour tous les annonceurs, quel que soit leur type d'abonnement. |
| ID de l'adset | Toujours disponible |
| Annonce | Actuellement indisponible |
| ID de l'annonce | Ce paramètre est disponible uniquement lorsque les deux conditions suivantes sont remplies :<ul><li>Les utilisateurs utilisent iOS 15.2 et +</li><li>La publicité utilise des <Anchor target="_blank" href="https://developer.apple.com/app-store/product-page/">pages de produit personnalisées</Anchor> pour les campagnes associées à l’un des emplacements de publicité suivants :<ul><li>`Today tab`</li><li>`Search results`</li></ul></li></ul> |
| Mots-clés | Pour que ce paramètre soit disponible, vous devez d'abord activer l'API de [Coût](/docs/apple-ads-integration-setup#cost-tab) sur la page d'intégration Apple Search Ads. L’API est disponible pour tous les annonceurs, quel que soit leur type d'abonnement. |
| ID de mot clé | Ce paramètre est disponible dans les rapports de données brutes. Il doit cependant être sélectionné dans Data Locker, les API Push et Données d'exportation. Dans le cas des API Pull, ajoutez `keyword_id` au paramètre d'appel `&additional_fields` <Anchor target="_blank" href="/marketers/fr/docs/pull-api-raw-data#additional-fields">de l'API Pull</Anchor>. |
| Type de correspondance de mots-clés | Actuellement indisponible |

</Accordion>

<div id="impact-of-aggregated-advanced-privacy" />

<Accordion title="Impact de la confidentialité avancée agrégée">

À partir d'iOS 14, [ATTrackingManager](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/) (ATT) régit la disponibilité de l'IDFA et les données d'attribution de niveau utilisateur relatives aux installations fournies par ASA sont contrôlées par ASA. La disponibilité des données de niveau utilisateur pour les installations apportées par ASA n'est pas affectée par <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">la confidentialité avancée agrégée.</Anchor>

Remarque! Important ! Les installations effectuées par ASA ne sont pas prises en compte dans l'infrastructure SKAdNetwork.

| **Accord ATT** | **Heure de clic disponible** | **Fenêtre rétrospective des clics** | **Remarques** | **Disponibilité des données** | **IDFA disponible** |
| --- | --- | --- | --- | --- | --- |
| Accord donné | Oui | Défini par l'annonceur | Règles d'attribution de dernier clic AppsFlyer utilisées | Données d'attribution au niveau de l'utilisateur | Oui |
| Accord refusé | Non | 30 jours  <br />(fixé par l'ASA) | La priorité est donnée aux candidats déterministes | Données d'attribution au niveau de l'utilisateur sans l'heure de clic. | Non |

</Accordion>

> 📄 **Articles connexes**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">Cadre de confidentialité avancée agrégé</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">Explication des fenêtres rétrospectives</Anchor>

<div data-zendesk-anchors="h_01J3WQNHJZSW1MX8SWXTNX8JKD=note set-up-asa-integration=configurer-lint%C3%A9gration-asa h_01HDPCGMP2CY4B37VM3AT2P114=configurer-lint%C3%A9gration-asa h_01HDPCGMP35S325269JETX1EJW=get-started h_01HDPCGMP383Y223E1YXF60C8S=remarque h_01HDPCGMP3JC93JWHM2SM8EVZA=cost-tab h_01HDPCGMP3XGYXVZZJ8SGDK3G2=remarque-1 h_01HDPCGMP3KXMKSHN0GFD6MAFG=permissions-tab set-up-agencies-and-asa-marketing-partners=configurer-les-agences-et-les-partenaires-marketing-asa h_01HDPCGMP3D96BG496G7H97YWP=configurer-les-agences-et-les-partenaires-marketing-asa h_01HDPCGMP3EBHM0CQXKP05SG9F=principles agency-vs-marketing-partner=diff%C3%A9rence-entre-agence-et-partenaire-marketing h_01HDPCGMP3YGJEA942DF2YC9P1=diff%C3%A9rence-entre-agence-et-partenaire-marketing configuring-agencies-and-marketing-partners=configurer-les-agences-et-les-partenaires-marketing h_01HDPCGMP3NQQ76SC32SEC8TS4=configurer-les-agences-et-les-partenaires-marketing configuration-steps-checklist=liste-pour-v%C3%A9rifier-les-%C3%A9tapes-de-la-configuration h_01HDPCGMP39HE117X4MP25M77W=liste-pour-v%C3%A9rifier-les-%C3%A9tapes-de-la-configuration h_01HDPCGMP3BT4YJWJ2G8X76NSE=marketing-partner-setup h_01HDPCGMP3X6B4RYF289WY49P7=agency-setup advertiser-actions=actions-de-lannonceur h_01HDPCGMP3S3PHHH3F6KZE3SEV=actions-de-lannonceur agency-actions=actions-de-lagence h_01HDPCGMP3MK61YRMCQA2KA5X2=actions-de-lagence h_01HDPCGMP3E7PZB8FDG4XN79JA=remarque-2 cost-clicks-and-impressions-data=donn%C3%A9es-sur-le-co%C3%BBt-les-clics-et-les-impressions h_01HDPCGMP3AVYYK2X03RF057FN=donn%C3%A9es-sur-le-co%C3%BBt-les-clics-et-les-impressions h_01HDPCGMP3113BYD1GPJM7XBQH=disable-agencies-and-marketing-partners additional-information=informations-suppl%C3%A9mentaires h_01HDPCGMP3BXVASH2YJ9G8AS2C=informations-suppl%C3%A9mentaires h_01HDPCGMP31QFVN1SWBCABJ65K=asa-attribution h_01HDPCGMP4DCKH898AEWAY6N01=discrepancies retargeting-related-discrepancies=%C3%A9carts-concernant-le-retargeting h_01HDPCGMP4Z9M3QR6QGRR7A8BM=%C3%A9carts-concernant-le-retargeting additional-reasons-for-discrepancies=motifs-suppl%C3%A9mentaires-d%C3%A9cart h_01HDPCGMP4QJ3HYEP7EAYMHRQQ=motifs-suppl%C3%A9mentaires-d%C3%A9cart h_01HDPCGMP4A8NAD8SYD191YJYR=tips h_01HDPCGMP4HNS84AVWH7J8H7YA=motifs-suppl%C3%A9mentaires-d%C3%A9cart h_01HDPCGMP4MF9FBP4WDRHVZ4BR=cohort-example h_01HDPCGMP4EFMZ4FHZ8WBWW9R2=pivot-example h_01HDPCGMP4XKB75F6R7DDWDHPB=asa-change-log h_01HDPCGMP40MW37BFT8A096PNG=availability-of-apple-search-ads-campaign-parameters h_01HDPCGMP48M04SDA4FGYW6XNQ=impact-of-aggregated-advanced-privacy h_01HDPD3C1T4ZXXZ2RE0GSXPZP3=articles-connexes" />
