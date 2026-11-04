---
title: '[Beta] TikTok for Business—configurer l''intégration des SRN avancés '
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-06-09T16:49:57Z'
  edited_at: '2023-12-27T14:41:36Z'
  id: 6722785184913
  locale: fr
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/fr/articles/6722785184913
---
> **En bref :** TikTok for Business (tiktokglobal\_int) est un réseau auto-reporting (<Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns">SRN</Anchor>) offrant aux propriétaires d’applications la possibilité de mesurer l’attribution mobile basée sur les clics et sur les vues avec AppsFlyer.

> 📘 **Remarque**
>
> le 30 janvier 2023, la nouvelle intégration **TikTok for Business—SRN avancé** `tiktokglobal_in` a été ajoutée. L'ancienne intégration TikTok for Business `bytedanceglobal_int` est quant à elle en cours de suppression et sera définitivement désactivée en mars 2024.Cette transition est gérée par TikTok, qui vous informera lorsque vous pourrez supprimer l'ancienne intégration. **Pour éviter de perdre des données, faites en sorte que les deux intégrations restent actives tout au long de la phase de transition**. Pour en savoir plus, consultez <Anchor target="_blank" href="/marketers/fr/docs/bulletin-tiktok-for-business-advanced-srn">ce bulletin</Anchor> .

<Image alt="TikTok_logo__2_.png" src="https://files.readme.io/3a081755b08fcf19b60ff178506a083449890cb900821f7f1e4b7ef85426dd45-11844735832081.png" width="193px" />

<div id="overview" />

## Vue d'ensemble

Une intégration SRN avancée signifie que tout le trafic <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-knowledge-base-glossary?query=glossar#dual-consent">à consentement double</Anchor> est attribué et signalé comme un trafic SRN classique. Pour le trafic non consenti, AppsFlyer attribue et mesure l'attribution basée sur les clics et les impressions provenant de TikTok, conformément aux conditions de confidentialité.L'intégration prend en charge l'attribution des clics et des impressions, les coûts, les revenus publicitaires et les audiences.

## Activation du partenaire

**Condition préalable :** avant de configurer l'intégration, assurez-vous de <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations#contacter-le-partenaire">contacter le partenaire</Anchor> et d'ouvrir un compte chez lui.

La configuration se fait depuis la page **Intégrations actives**, mais pour trouver de nouveaux partenaires vous devez d'abord vous rendre dans le <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations">marketplace</Anchor>.

**Pour activer l'intégration des partenaires :**

1. Dans AppsFlyer, allez dans **Configuration** et **Marketplace des partenaires**.
2. Recherchez **TikTok for Business** et sélectionnez-le.
3. Cliquez sur **Configurer l'intégration**. Vous êtes alors dirigé vers la page de configuration de l'intégration.
4. Dans l'onglet **Intégration**, activez **Activer le partenaire**.  
   **Remarque :** La case doit rester cochée (<Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">option activée</Anchor>) tant que vous travaillez avec le partenaire.
5. Cliquez sur **Enregistrer l'intégration**.
6. Terminez la configuration en suivant les onglets requis, cf description ci-dessous.

<div id="set-up-tiktok-for-business" />

## Configurer TikTok For Business

La fenêtre de configuration comprend les onglets suivants : Intégration, Lien d'attribution, Coût, Revenus publicitaires et Autorisations. L'onglet **Lien d'attribution** n'est pas disponible dans TikTok for Business, les autres onglets sont facultatifs.

> 📘 **Remarque**
>
> * Certains paramètres diffèrent entre les appareils iOS et Android.
> * Le nom de la campagne ne doit pas commencer ou se terminer par un espace vide, car cela peut entraîner des divergences dans les tableaux de bord et rapports. En savoir plus sur <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=9535">la configuration d'une campagne sur TikTok</Anchor>.
> * Les publicités provenant de <Anchor target="_blank" href="https://www.tiktok.com/business/en/blog/introducing-tiktok-search-ads-toggle">TikTok Search Ads</Anchor> sont incluses dans toutes les attributions de TikTok. AppsFlyer ne reçoit pas de données concernant des termes de recherche ou mots-clés spécifiques.

<div id="integration-tab" />

<Accordion title="Onglet Intégration">

L'onglet **Integration** comprend un certain nombre de sections, décrites ci-dessous.

<div id="activate-partner" />

#### Activation du partenaire

Pour configurer l'intégration, vous devez d'abord [activer](#activation-du-partenaire) la fonction **Activer le partenaire**. En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation#activating-a-partner">l'activation et la désactivation des intégrations des partenaires</Anchor>.

<div id="advanced-data-sharing" />

#### Protection de la vie privée avancée

Pour les apps iOS uniquement : votre contrôle des données partagées avec le partenaire via les postbacks et <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">rapports</Anchor> dépend du statut de le <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">**Confidentialité avancée**</Anchor> (pour iOS 14.5 et +) :

| Confidentialité avancée : ON | Confidentialité avancée : OFF |
| --- | --- |
| Les postbacks sont envoyés uniquement pour les événements attribués au partenaire. | Les postbacks sont envoyés selon votre configuration :<ul><li>**Toutes les sources média, y compris organiques**</li><li>**Ce partenaire uniquement**</li></ul> |
| Les postbacks sont envoyés selon le <Anchor target="_blank" href="/partners/fr/docs/advanced-privacy-guide-postback-macros-for-ad-networks">modèle de confidentialité avancée</Anchor> |  |
| <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">Les données agrégées et anonymes</Anchor> sont partagées avec le partenaire, ce qui signifie qu'aucune donnée de niveau utilisateur (identifiant de l'appareil) n'est partagée. |  |

> 📘 **Remarque**
>
> * Lors de l'activation de l'intégration (`tiktokglobal_int`), l'option **Confidentialité avancée** est activée par défaut.
> * Après la migration depuis l'ancienne intégration (`bytedanceglobal_int`) et l'activation de la nouvelle intégration (`tiktokglobal_int`), l'option **Confidentialité avancée** est activée par défaut, même si elle ne l'était pas avant la migration.
> * D'après TikTok for Business, laisser la **Confidentialité avancée** **activée** peut générer une sous-déclaration du nombre d'événements de la campagne et limiter les performances des campagnes futures sur TikTok.

<div id="general-settings" />

#### Paramètres généraux

**ID d'app TikTok**

L'ID d'app TikTok est un code unique généré dans TikTok Ads Manager et utilisé par TikTok pour confirmer la propriété des apps par l'annonceur. Ce n'est pas obligatoire, mais nous vous recommandons de saisir un ID pour chacune de vos applications. Cela vous permet de mieux contrôler vos données TikTok for Business et de déverrouiller des produits supplémentaires.

**Pour ajouter vos ID d'app :**

1. [Facultatif] Entrez votre <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10001060">ID d’app TikTok</Anchor> disponible dans votre tableau de bord TikTok Ads.
2. [Facultatif] Pour ajouter d'autres ID d'app :
   1. Après avoir saisi le premier ID d'app, appuyez sur la touche Entrée.
   2. Saisissez votre ID d'app TikTok suivant.

> 📘 **Remarque**
>
> * La configuration d’un ID d’app TikTok n’a pas d’impact sur vos données dans AppsFlyer
> * Après la migration vers la nouvelle intégration (`tiktokglobal_int`), toutes les valeurs de l'ancienne intégration (`bytedanceglobal_int`) sont automatiquement remplies.
> * <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10001070">En savoir plus sur les conditions relatives à l'ID d'app TikTok pour iOS 14</Anchor>

<div id="default-postbacks" />

#### Postbacks par défaut

**Cette section ne concerne que** **le trafic non autorisé**. Le trafic autorisé est envoyé directement à TikTok for Business via <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns?query=about%20srn">le mode SRN</Anchor>.

Configurer l'envoi des postbacks pour les **installations**, **installations rejetées**, et **réengagements** se produisant avant le lancement de l'application :

* **Ce partenaire uniquement** (par défaut) : envoi de postbacks uniquement lorsque l'événement est attribué à ce partenaire, c'est-à-dire lorsque l'utilisateur qui effectue l'événement provient de ce partenaire.
* **Toutes les sources média, y compris organiques**: envoi de postbacks pour les événements attribués à n'importe quel partenaire et pour les événements organiques, c'est-à-dire lorsque l'utilisateur qui les produit est issu de n'importe quelle source média. TikTok for Business recommande de mettre sur l'option sur **Toutes les surces média y compris organiques** pour optimiser les résultats.

> 📘 **Remarque**
>
> * Pour les applications iOS uniquement : votre contrôle des données partagées avec le partenaire via les postbacks et les <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">rapports</Anchor> dépend de l'état de la fonction **Confidentialité avancée (pour iOS 14.5 et +)**.
> * Après la migration depuis l'ancienne intégration (`bytedanceglobal_int`) et l'activation de la nouvelle intégration (`tiktokglobal_int`), les postbacks d'installations sont réglés par défaut sur **Ce partenaire uniquement**, sans aucun rapport avec leur statut avant la migration.

<div id="install-attribution" />

#### Attribution d'installation

Définir l'attribution post-clic et post-vue pour les installations (premiers lancements). Notez que seules les installations effectuées durant la fenêtre d'attribution peuvent être attribuées à TikTok for Business.

1. Définissez la **Fenêtre rétrospective post-clic d'installation** sur 1-23 heures ou 1-30 jours.  
   **Remarque :** TikTok for Business recommande de s'aligner sur leurs paramètres en réglant la fenêtre rétrospective post-clic sur 7 jours.
2. [Facultatif] Activez l'option **Installer l'attribution post-vue** et définissez la fenêtre **Fenêtre d'attribution post-vue des installations** entre 1 et 23 heures.  
   **Remarque :** TikTok for Business recommande de s'aligner sur leurs paramètres en réglant la fenêtre rétrospective post-vue sur 7 jours.

> 📘 **Remarque**
>
> * TikTok for Business utilise des mesures avancées de confidentialité des données pour protéger les personnes qui utilisent ses services. Depuis le 23 octobre 2021, TikTok for Business fournit aux annonceurs des données d’attribution limitées au niveau de l’appareil. Pour les sources de niveau utilisateur telles que les rapports de données brutes, les messages API Push, les rapports API Pull et Data Locker, les champs suivants sont renseignés :
>
> * * Source média (bytedanceglobal\_int)
>   * Canal
>   * Type de touch attribué (impression)
>   * Date de touch attribué (date uniquement - « jj/mm/aaaa »)
>   * La campagne est signalée comme étant «restreinte»
>     Ces données ne sont pas disponibles dans le GCD. Les rapports de données agrégées continuent d'afficher les conversions post-vue.
> * Après la migration depuis l'ancienne intégration (`bytedanceglobal_int`) et l'activation de la nouvelle intégration (`tiktokglobal_int`), les fenêtres rétrospectives sont réglées sur les **Valeurs par défaut**, sans aucun rapport avec leur statut avant la migration. Vous pouvez mettre à jour ces paramètres.

<div id="re-engagement-attribution" />

#### Attribution du ré-engagement

Définir des fenêtres de réengagement, y compris des attributions post clic et post vue :

1. [Facultatif] Activez **Attribution de réengagement**, puis configurez la **fenêtre rétrospective de réengagement post-clic**.
2. [Facultatif] Activez **l'attribution de réengagement post-vue**, puis configurez la **fenêtre rétrospective de réengagement post-vue**.
3. [Facultatif] Configurez la **fenêtre de réengagement**.

> 🚧 **Important !**
>
> Après la migration depuis l'ancienne intégration (`bytedanceglobal_int`) et l'activation de la nouvelle intégration (`tiktokglobal_int`), l'option **Réengagement** est **désactivée par défaut,**, même si elle ne l'était pas avant la migration. Si votre ancienne intégration comporte <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide">des campagnes de retargeting</Anchor>, veillez à **les activer** dans la nouvelle intégration **afin de ne pas interrompre le fonctionnement des opérations.**

Pour en savoir plus sur les <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide#reengagement-rules-and-windows">règles et fenêtres de réengagement</Anchor>.

<div id="in-app-event-postbacks" />

#### Postback d'évènements in-app

**Cette section ne concerne que le trafic non autorisé.** Le trafic autorisé est envoyé directement à TikTok for Business via <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns?query=about%20srn">le mode SRN</Anchor>.

Configurer le mappage des événements in-app avec les événements TikTok for Business, envoyés via les postbacks :

1. Activez **Postbacks d'événement in-app.**
2. Cliquez sur **Ajouter un événement** pour ajouter un SDK ou événement de serveur à serveur à la liste. Le tableau suivant explique les champs à remplir :  

| Nom du paramètre | Description |
| --- | --- |
| **Événement AppsFlyer** | Le nom de l'événement tel que reçu par AppsFlyer, soit depuis le SDK intégré à votre app, soit depuis les événements de serveur à serveur.<br />**Astuce** : vous ne voyez pas s'afficher un événement en particulier ?<ul><li>Assurez-vous d'activer l'évènement sur un appareil avec une installation non-organique avant de vérifier à nouveau.</li><li>Saisissez-le dans **Événement AppsFlyer** puis cliquez sur **Créer événement personnalisé**. En savoir plus sur le <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#événements-personnalisés">mappage d'événements personnalisés.</Anchor></li></ul> |
| **mappé à l’événement partenaire** | Le nom ou l'identifiant unique de chaque événement, tel que défini du côté du partenaire. Les différentes configurations du mapping sont :<ul><li>**Champ de texte :** obtenez l'ID d'événement correspondant auprès du partenaire.</li><li>**Liste déroulante :** sélectionnez l’événement AppsFlyer prédéfini approprié.</li><li>**Tel quel** : envoyez les événements à l'état brut, sans mappage du nom.</li></ul> |
| **pour les utilisateurs de** | Sélectionnez l'option d'envoi pour l'événement :<ul><li>**Ce partenaire uniquement** : envoie des postbacks uniquement dans le cas où cet événement est attribué à ce partenaire.</li><li>**Toutes les sources média, y compris organiques**: envoi de postbacks pour les événements attribués à n'importe quel partenaire, ainsi que pour les événements organiques. TikTok for Business recommande de mettre sur l'option sur **Toutes les sources média y compris organiques** pour optimiser les résultats.</li></ul> |
| **Y compris** | <ul><li>**Sans valeur et sans revenu** (par défaut) : AppsFlyer envoie uniquement l'évènement en lui-même, sans aucune valeur.</li><li>**Avec valeurs et sans revenu** : envoie tous les paramètres **à l'exception** de la valeur du revenu.</li><li>**Valeurs et revenus** : envoie tous les paramètres de l’événement, **y compris** la valeur du revenu (si présente dans l’événement). TikTok for Business recommande de choisir **Valeurs et revenus** pour de meilleurs résultats.</li></ul> |

3. [Facultatif] Cliquez sur l'icône **Ajouter une condition**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> pour <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#postbacks-conditionnels-dévénements-in-app">définir les conditions</Anchor> d'un événement.
4. Cliquez sur **Enregistrer l'intégration**.
5. [Facultatif] Une fois l'intégration enregistrée, restez sur la page de configuration pour intégrer plus d'apps avec le partenaire :
   1. Dans le coin en haut à gauche, sous le nom du partenaire, cliquez sur le nom de l’app pour ouvrir la liste des apps.
   2. Sélectionnez une autre app dans la liste déroulante.
   3. Répétez les différentes étapes d’intégration pour l’app sélectionnée.

> 📘 **Remarque**
>
> * Pour les applications iOS uniquement : votre contrôle des données partagées avec le partenaire via les postbacks et les <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">rapports</Anchor> dépend de l'état de la fonction **Confidentialité avancée (pour iOS 14.5 et +)**.
> * Lors de la migration vers la nouvelle intégration (`tiktokglobal_int`), tous les événements de postback configurés dans l'ancienne intégration (`bytedanceglobal_int`) sont automatiquement réglés avec les mêmes paramètres.
>   * Si un événement est lié à l'événement [Legacy] TikTok for Business **Pay** , après la migration vers la nouvelle intégration, le nom de cet événement devient automatiquement **Purchase**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Onglet Lien d'attribution">

Les liens d'attribution ne concernent pas les <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns">SRN</Anchor> ou les SRN avancés.

Les SRN effectuent l'attribution sur leur propre plateforme. L'attribution pour les SRN avancés s'effectue en regroupant leurs données d'engagement avec les données d'AppsFlyer, et ce avec les paramètres d'attribution que vous avez définis dans l'onglet [Integration](#integration-tab).

</Accordion>

<div id="cost-tab-for-cost-clicks-and-impressions" />

<Accordion title="Onglet Coût (pour les coûts, les clics et les impressions)">

Cette intégration fournit des données agrégées sur les coûts, les clics et les impressions pour vos campagnes, vos ensembles de publicités, vos publicités et vos zones géographiques/pays. Consultez le <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tableau d'intégration des coûts du réseau publicitaire</Anchor> pour obtenir plus d'infos sur les dimensions, les métriques et les fonctionnalités prises en charge.

**Remarque :** les données sur les clics et les impressions sont incluses dans l'intégration. Cependant, **les données sur les coûts nécessitent un abonnement à <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>**.

**Pour activer la connexion d'API pour les coûts, les clics et les impressions avec TikTok for Business**  :

1. Allez dans l'onglet **Coût** et activez **Obtenir des données sur les coûts**.
2. Cliquez sur **Se connecter à TikTok Ads**.
3. Dans la fenêtre TikTok qui s'ouvre, connectez-vous à votre compte TikTok et confirmez les autorisations nécessaires.
4. Fermez la fenêtre TikTok après l'affichage du message de confirmation. Les détails de votre compte TikTok apparaissent alors dans **Comptes connectés**.
5. Depuis **ID de compte d'annonceur** > **ID d'annonceur** : saisissez l'ID du compte annonceur TikTok et cliquez sur **Ajouter**.  

   > 📘 **Remarque**
   >
   > * Pour obtenir votre **ID d'annonceur** à partir de votre compte TikTok Business : allez dans **Utilisateurs** > **Membres**. L'ID s'affiche dans le compte de l'annonceur.
   > * Assurez-vous que **l'ID d'annonceur** que vous ajoutez est associé au **compte TikTok** que vous avez connecté à l'étape 2, car c'est depuis ce compte que les données seront collectées.
   > * Connectez au moins un **ID d'annonceur**. Vous pouvez en ajouter jusqu'à 30.

6. Cliquez sur **Sauvegarder les coûts**.

<div id="for-roi360-subscribers" />

#### Pour les abonnés à ROI360

* Les annonceurs et les agences qui ont activé l'API de coût dans les intégrations ancienne `bytedanceglobal_int` et actuelle `tiktokglobal_int` risquent d'avoir des données de coûts en double. Pour éviter cela, allez dans l'onglet Intégration `bytedanceglobal_int` > **Coûts** et désactivez la fonctionnalité.Toutefois, lors de l'activation de la nouvelle intégration des coûts, les données de coûts des 5 jours précédant le jour de la transition sont automatiquement collectées. Cela signifie que la nouvelle intégration peut afficher des données de coûts en double pour ces 5 jours. **Par exemple**, si l'ancienne intégration des coûts a été désactivée le 15 janvier et que la nouvelle intégration des coûts a été activée le même jour, des données de coûts en double apparaissent dans la nouvelle intégration des coûts entre le 10 et le 14 janvier, même si elle n'a été activée qu'au 15 janvier.
* Consultez le <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tableau d'intégration des coûts du réseau publicitaire</Anchor> pour obtenir plus d'infos sur les dimensions, les métriques et les fonctionnalités prises en charge.
* <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Consultez le statut de votre API de coût</Anchor> et affichez l'heure où AppsFlyer a réussi pour la dernière fois à extraire les données de coûts correspondantes, que ce soit dans le tableau de bord du statut d'intégration des coûts (et des revenus publicitaires), ou dans le tableau de bord du réseau publicitaire individuel.
* En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">l'activation de l'API de coût</Anchor>.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Onglet Revenus publicitaires">

Cette section vous concerne si vous agissez en tant qu'éditeur, c'est-à-dire si vous affichez les publicités du partenaire à l'intention de vos utilisateurs. Vous pouvez mesurer l'engagement de vos utilisateurs provenant de différentes sources, afin d'identifier celles qui offrent le maximum de rentabilité.

**Pour activer l'API de revenus publicitaires** :

* Suivez  <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">ces instructions d'intégration</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Onglet Autorisations">

Dans cette section, vous pouvez sélectionner des autorisations permettant à TikTok for Business d'accéder à vos données et d'effectuer diverses actions.

Notez que même après la <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">désactivation</Anchor> de l'intégration, lorsque la fonction **Autorisations TikTok for Business** est activée, les autorisations sont toujours accordées. 

En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">l'octroi d'autorisations</Anchor> à une agence.

</Accordion>

<div id="set-up-tiktok-for-business-for-agencies" />

## Configuration de TikTok for Business pour les agences

Les agences travaillant pour le compte d'annonceurs peuvent activer l'intégration de TikTok for Business et obtenir les attributions pour leurs campagnes. Toutefois, cette intégration présente certaines limites en ce qui concerne les agences.

<div id="agency-limitations" />

### Limites de l'agence

* Une agence ne peut accéder à l'intégration TikTok for Business qu'une fois que l'annonceur avec qui elle travaille l'a activée de son côté.
* À compter du 1er janvier 2024, les paramètres d'attribution affichés sur la page d'intégration de l'agence seront hérités de l'intégration de l'annonceur en mode **lecture seule**. Cela signifie que l'agence pourra voir comment l'annonceur a configuré les fenêtres d'attribution , mais qu'elle ne pourra pas les configurer elle-même.
* Pour les événements post-attribution, si l'annonceur l'autorise, une agence peut configurer les postbacks d'événements in-app.
* Une agence ne peut pas activer le paramètre Confidentialité avancée (même si elle en a reçu l'autorisation), ce paramètre est en strictement réservé à l'annonceur.

**Pour configurer TikTok for Business pour les agences :**

1. Dans AppsFlyer, allez dans **Configuration** et **Marketplace des partenaires**.
2. Cherchez et sélectionnez **TikTok for Business**.
3. Saisissez l'**ID d'app TikTok**.
4. Saisissez l'**ID du compte TikTok** de votre agence. Cela permet d'identifier le trafic de l'agence et de le séparer de celui de l'annonceur .
5. Cliquez sur **Enregistrer l'intégration**.

   <Image alt="tiktok_agency_account_id.png" src="https://support.appsflyer.com/hc/article_attachments/15195630638609" width="442px" />

> ❗️ **Avertissement**
>
> Les identifiants des comptes TikTok for Business NE DOIVENT PAS être partagés entre l'annonceur et l'agence. S'ils sont partagés, TOUTES les installations de l'annonceur sont automatiquement attribuées dans le tableau de bord de l'agence.

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/bytedance-ads-china-campaign-configuration">ByteDance Ads (Ocean Engine)</Anchor> pour le trafic en Chine (bytedance\_int)
> * <Anchor target="_blank" href="/marketers/fr/docs/skan-interoperation-with-tiktok-for-business">Interopération SKAN avec TikTok for Business</Anchor>

<div data-zendesk-anchors="01H8VVCC8GW5AZ3M475XFZY9JW=remarque overview=vue-densemble 01H8VVCC8G3ZXZJMHSMJ67GMG4=vue-densemble activate-partner=activation-du-partenaire 01H8VVCC8GH1MNRAY9HC9P6JR0=activation-du-partenaire setting-up-tiktok-for-business%C2%A0integration=configurer-tiktok-for-business 01H8VVCC8GPY4SEFGK30Q1BJZ6=configurer-tiktok-for-business 01H8VVCC8G6P25R0N5A7S3NGY7=remarque-1 01H8VVCC8GY6WTH0404RH2AR9F=integration-tab activate-partner::e4f2f638=activation-du-partenaire-1 01H8VVCC8G0KR4AA2HD9S8QBKD=activation-du-partenaire-1 advanced-privacy=protection-de-la-vie-priv%C3%A9e-avanc%C3%A9e 01H8VVCC8G0Z6ZHC10KVY9CGGQ=protection-de-la-vie-priv%C3%A9e-avanc%C3%A9e 01H8VVCC8GC57YTDWA9EB2VP87=remarque-2 general-settings=param%C3%A8tres-g%C3%A9n%C3%A9raux 01H8VVCC8GSDPSNN0AJPVZPR8P=param%C3%A8tres-g%C3%A9n%C3%A9raux 01H8VVCC8G2JB115XW49HJQFHA=remarque-3 default-postbacks=postbacks-par-d%C3%A9faut 01H8VVCC8GW677RN6R6CV35KGG=postbacks-par-d%C3%A9faut 01H8VVCC8G6M8D3WQ2CM10ZNZX=remarque-6 install-attribution=attribution-dinstallation 01H8VVCC8GK8VFPBEPAMVHCAWM=attribution-dinstallation 01H8VVCC8G3YFDZVV9X9709F9M=remarque-5 reengagement-attribution=attribution-du-r%C3%A9-engagement 01H8VVCC8HHG5290PYF0BT29QA=attribution-du-r%C3%A9-engagement 01H8VVDWH85M34K7Z75BAT7BQW=important- inapp-event-postbacks=postback-d%C3%A9v%C3%A8nements-in-app 01H8VVCC8HHZRFQ2T1X478YZMP=postback-d%C3%A9v%C3%A8nements-in-app 01H8VVCC8HDMTY1P2SG31HD61K=remarque-6 01H8VVCC8H53ZRMDBNK1436NAX=attribution-link-tab 01H8VVCC8H74GDVCNAXT0741MG=cost-tab-for-cost-clicks-and-impressions 01H8VVCC8HFJF62TC7DNXRH22A=remarque-7 for-xpend-subscribers=pour-les-abonn%C3%A9s-%C3%A0-roi360 01H8VVCC8HWDC9A03FRY5BC87Y=pour-les-abonn%C3%A9s-%C3%A0-roi360 01H8VVCC8H90ANM70QAHKTQQ1S=ad-revenue-tab 01H8VVCC8HAG0XVWE2T9PRDHTK=permissions-tab setting-up-tiktok-for-business-for-agencies=configuration-de-tiktok-for-business-pour-les-agences 01H8VVCC8HVNNQ9PJS4ZQCVDNS=configuration-de-tiktok-for-business-pour-les-agences agency-limitations=limites-de-lagence h_01HHVGS94CB9XC0T63VFDZ18JS=limites-de-lagence 01H8VVCC8HWJ2WQ83E0CZMEHH1=avertissement h_01HE7RY8K7HV2CTZ2S537YRCNQ=%C3%A0-consulter-%C3%A9galement" />
