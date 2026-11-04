---
title: Guide d'attribution des revenus publicitaires
metadata:
  keywords:
    - ad revenue
    - ad monetization
    - monetization
    - Advertisers
    - adrevenue
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2016-12-12T10:53:27Z'
  edited_at: '2023-12-18T14:41:41Z'
  id: 217490046
  locale: fr
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/fr/articles/217490046
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** attribuez les revenus publicitaires pour compléter l'affichage des performances LTV.

[![Attributes_ad_revenue.png](https://files.readme.io/e512531f0363fcda600fbad8ca8e5081d882b5721fb35fc9c449f8774859a5da-small-15734558614033.png)](https://files.readme.io/e512531f0363fcda600fbad8ca8e5081d882b5721fb35fc9c449f8774859a5da-small-15734558614033.png)

<div id="ad-revenue-attribution" />

## L'attribution des revenus publicitaires

* Les publicités s'affichent dans l'application sur des bannières, des murs d'offres, des interstitiels, etc., et elles génèrent des revenus publicitaires.
* La somme des revenus publicitaires, achats in-app et revenus d'abonnement offrent une vision complète de la LTV de l'utilisateur. Le ROI est déterminé en associant la LTV de l'utilisateur et la dépenses des médias de la campagne, et il s'affiche sur la plateforme pour permettre une analyse.

**Données des revenus publicitaires attribués** :

* Obtenues sur les réseaux de médiation et/ou de monétisation publicitaire via les API de serveur, ou via le SDK de reporting intégré à l'app (iOS 14 inclus).
* Attribuées à la source média qui a initialement amené l'utilisateur. Par exemple :
  * L'utilisateur voit une publicité du réseau A et télécharge votre application.
  * La publicité s'affiche au sein de l'application.
  * Les recettes publicitaires sont attribuées au réseau A (à l'origine de l'acquisition d'utilisateur), quel que soit l'auteur de la publicité.
* La granularité des rapports dépend de l'intégration du réseau de monétisation et du type d'attribution des revenus publicitaires.

<div id="integration-types-for-ad-revenue-attribution" />

<Accordion title="Types d'intégration pour l'attribution des revenus publicitaires">

L'attribution des revenus publicitaires prend en charge différentes méthodes de granularité. La granularité dépend du réseau de monétisation.

| Type d’intégration de l’attribution des revenus publicitaires | Description |
| --- | --- |
| [Niveau agrégé via API](/docs/roi360-guide-ad-revenue-attribution#aggregate-granularity-using-app-open-or-inapp-events) S2S | <ul><li>AppsFlyer obtient le revenu quotidien réparti par zone géographique.</li><li>Le revenu effectif par action (eRPA) est obtenu en divisant le revenu par le nombre de fois où un événement déclencheur s'est produit.</li><li>Les événements déclencheurs sont une ouverture d'app, ou des événements in-app spécifiques qui ont été définis dans l'app.</li><li>Si vous utilisez un réseau de médiation, veillez à désactiver les intégrations de revenus publicitaires pour les partenaires de monétisation médiatisés via ce réseau avant d'activer l'intégration des revenus publicitaires au sein du réseau de médiation. Si vous ne le faites pas, les données apparaitront en double.</li></ul> |
| [Niveau appareil](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data) via API S2S | <ul><li>Le réseau de médiation ou de monétisation rapporte le revenu par utilisateur au niveau de l'appareil. Tous les réseaux ne prennent pas en charge la granularité de niveau utilisateur.</li><li>Ce chiffre d'affaires est attribué à la source média qui a conduit l'utilisateur. L'attribution des revenus publicitaires d'AppsFlyer est conforme aux règles d'attribution de la plateforme, y compris les règles d'attribution du retargeting.</li><li>Si vous utilisez un réseau de médiation, veillez à désactiver les intégrations de revenus publicitaires pour les partenaires de monétisation médiatisés via ce réseau avant d'activer l'intégration des revenus publicitaires au sein du réseau de médiation. Si vous ne le faites pas, les données apparaitront en double.</li><li>Le niveau utilisateur via API S2S inclut la totalité des revenus publicitaires et il offre une précision optimale pour les données de type intégration des revenus publicitaires.</li><li>Les données sont disponibles dans les <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">rapports de données brutes</Anchor>. Nous n'envoyons aucun postback aux partenaires intégrés pour les données de niveau appareil.</li></ul> |
| Niveau impression via SDK | <ul><li>Le niveau impression concerne la manière dont AppsFlyer reçoit les données. Les données peuvent cependant être rapportées à un niveau de granularité différent (ex : au niveau de l'appareil).</li><li>Le réseau de médiation ou de monétisation rapporte le revenu par utilisateur au niveau de l'impression. Tous les réseaux ne prennent pas en charge la granularité au niveau de l'impression.</li><li>Ce chiffre d'affaires est attribué à la source média qui a conduit l'utilisateur. L'attribution des revenus publicitaires d'AppsFlyer est conforme aux règles d'attribution de la plateforme, y compris les règles d'attribution du retargeting.</li><li>Si vous utilisez un réseau de médiation, veillez à désactiver les intégrations de revenus publicitaires pour les partenaires de monétisation médiatisés via ce réseau avant d'activer l'intégration des revenus publicitaires au sein du réseau de médiation. Si vous ne le faites pas, les données apparaitront en double.</li><li>Parmi tous les types d'intégration des revenus publicitaires, le niveau impression via SDK est celui qui permet la meilleure actualisation des données.</li><li>Prend en charge SKAN.</li></ul> |
| Niveau impression (via le SDK) avec niveau appareil (via API S2S) | <ul><li>Permet aux données de niveau impression qui arrivent via SDK d'être attribuées et rapportées au Jour X, et d'être échangées avec les données de niveau appareil transmises par API le Jour 1, et les suivants. **Remarque** : Pour Android, les données communiquées via le SDK à partir d'appareils inconnus (sans ID d'appareil disponible) ne sont pas remplacées par les données qui arrivent via l'API.</li><li>Permet une actualisation des données précise. Vous bénéficiez ainsi de l'actualisation des données au jour X et de la précision des données pour les jours X + 1 et suivants.</li><li>Prend en charge SKAN.</li></ul> |

</Accordion>

<div id="note-1" />

<div id="note" />

<div id="implementation" />

## Implémentation

Les sections suivantes décrivent les types d'attribution de revenus publicitaires existants, ainsi que les opérations nécessaires à leur mise en place et suivi.

<div id="connect-to-ad-revenue-integrated-partners" />

<Accordion title="Se connecter aux partenaires intégrés de revenus publicitaires">

**Avant de commencer** :

* Demandez au partenaire intégré des revenus publicitaires de vous fournir des identifiants API.

**Pour activer l'intégration des revenus publicitaires avec le réseau de revenus publicitaires** :

1. Dans AppsFlyer, allez dans **ROI360** > **Paramètres des revenus** > **Revenus publicitaires**.
2. Dans Integration des revenus publicitaires, cliquez sur **Nouvelle intégration des revenus publicitaires**.
3. Sélectionnez un partenaire des revenus publicitaires et cliquez sur **Suivant**.  
   ![ad_revenue_ui.png](https://files.readme.io/d91b886ed5b9715a508a481afbb86a7dd8381894322455214674ba68b483e91b-13751596101649.png)
4. Sélectionnez le type de données des revenus publicitaires que vous souhaitez recevoir. **Remarque** : tous les réseaux publicitaires ne proposent pas l'intégralité des options ci-dessous.
   * Revenus attribués. Signifie que le revenu est basé sur la source d'acquisition d'utilisateurs. Les rapports sur les revenus attribués peuvent être soit :
     * [Niveau agrégé](/docs/roi360-guide-ad-revenue-attribution#aggregate-granularity-using-app-open-or-inapp-events) via API S2S. 
       * Sélectionnez l’événement sur lequel baser les revenus publicitaires. Exemple : si vous choisissez l'événement af\_app\_opened, le revenu publicitaire total est divisé entre tous les événements correspondant à l'ouverture de l'app, ce qui vous donne le revenu publicitaire par ouverture d'app.
     * Niveau appareil via API S2S
       * **Remarque** : Si vous activez l'API de revenus publicitaires de niveau appareil pour un réseau de médiation, vous devez désactiver les intégrations de revenus publicitaires des réseaux de monétisation qu'il concilie. Si vous ne le faites pas, les données seront affichées en double.
     * Niveau impression via SDK
     * Demandez à vos développeurs d'intégrer le connecteur SDK de revenu publicitaire AppsFlyer. Les options existent pour <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-2">iOS</Anchor> et <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad_revenue_unity_connector">Unity</Anchor>.* Niveau impression (via le SDK) avec niveau appareil (via API S2S)
     * Demandez à vos développeurs d'intégrer le connecteur SDK de revenu publicitaire AppsFlyer. Les options existent pour <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-2">iOS</Anchor> et <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad_revenue_unity_connector">Unity</Anchor>.* **Remarque :** si vous utilisez un réseau de médiation, veillez à désactiver les intégrations de revenus publicitaires pour les partenaires de monétisation médiatisés via ce réseau avant d'activer l'intégration des revenus publicitaires au sein du réseau de médiation. Si vous ne le faites pas, les données seront dupliquées.
5. Complétez les identifiants d'API, ou le login, comme l'exige le partenaire intégré. Ne concerne pas les intégrations SDK.
6. Cliquez sur **Enregistrer**.
7. Si le bouton Test de connexion s'affiche (cf image ci-dessus), cliquez sur **Test de connexion**.
   * La clé API vérifiée s'affiche, la procédure est bien terminée.
   * Si un autre message s'affiche, consultez la section [Statut et test de l'API de revenus publicitaires,](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-api-status-and-testing) et recommencez la procédure.
8. Si vous ne voyez pas s'afficher le bouton Tester la connexion , la procédure est bien terminée.   
   AppsFlyer collecte les données du partenaire plusieurs fois par jour<Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#ad-revenue">.</Anchor>
9. [Facultatif ] Suivez et comparez les données de revenus publicitaires affichées dans AppsFlyer avec les données de revenu publicitaire présentes dans les tableaux de bord de votre partenaire de médiation et de votre partenaire UA. <Anchor target="_blank" href="/marketers/fr/docs/compare-roi360-ad-revenue-data-with-partner-data">En savoir plus</Anchor>
10. [Facultatif] Partagez les données de revenu publicitaire avec vos partenaires via les <Anchor target="_blank" href="/marketers/fr/docs/compare-roi360-ad-revenue-data-with-partner-data">signaux UA</Anchor> et les [postbacks d'événements de revenu publicitaire](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks).

**Remarque** : si vous passez d’un type d’intégration à l'autre, la modification prend effet à 00 h (minuit) UTC le jour qui suit.

</Accordion>

<div id="view-edit-and-delete-ad-revenue-integrated-partners" />

<Accordion title="Afficher, modifier et supprimer les revenus publicitaires des partenaires intégrés">

![delete_edit_adi.png](https://support.appsflyer.com/hc/article_attachments/13751607197713)

**Pour afficher, modifier ou supprimer les intégrations des réseaux de revenus publicitaires :**:

1. Dans AppsFlyer, allez dans **ROI360** > **Paramètres des revenus** > **Revenus publicitaires** et sélectionnez votre app.  
   Une liste contenant toutes les intégrations de vos partenaires s'affiche, elle inclut des informations sur le produit et le type d'intégration, le statut de l'intégration ainsi que les noms des événements de revenus publicitaires.
2. Passez la souris sur l'intégration et cliquez sur **Modifier** ou **Supprimer**.

</Accordion>

<div id="deduplicate-cross-referenced" />

<Accordion title="Supprimer les doublons des revenus publicitaires croisés">

Une partie des données des revenus publicitaires peut se retrouver en double lorsque une app utilise deux <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-knowledge-base-glossary#plateforme-de-médiation">plateformes de médiation</Anchor>, et que les deux sont associées au même <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-knowledge-base-glossary#réseau-de-monétisation">réseau de monétisation.</Anchor> Dans ce cas, chaque plateforme de médiation rapporte tous les revenus publicitaires générées par le réseau de monétisation qui lui est associé, que ces revenus aient été générées par un seul des réseaux, ou les deux.

**Pour éviter la duplication d'une partie des données de revenu lorsque deux plateformes de médiation se croisent :**

1. Dans AppsFlyer, allez dans **ROI360** > **Paramètres des revenus** > **Revenus publicitaires**.
2. Dans **Paramètres généraux**, cliquez sur **Supprimer les doublons quand deux plateformes de médiation se croisent.Remarque** : Ne supprimez pas les doublons si les deux plateformes média gèrent des formats publicitaires différents. Par exemple, lorsque la plateforme 1 affiche des bannières et des interstitiels, et que la plateforme 2 affiche des publicités Natives et AppOpen.

[![dedup.png](https://support.appsflyer.com/hc/article_attachments/17299804281361)](https://support.appsflyer.com/hc/article_attachments/17299804281361)

</Accordion>

<div id="aggregate-granularity-using-app-open-or-inapp-events" />

<Accordion title="Granularité agrégée à l'aide d'événements d'ouverture d'app ou d'événements d'in-app">

La granularité agrégée des revenus publicitaires fonctionne comme suit :

* Le réseau intégré signale le revenu total par jour réparti par géo.
* AppsFlyer calcule le revenu effectif par action (eRPA) en divisant le revenu publicitaire par le nombre de fois où un événement déclencheur s'est produit.
* AppsFlyer crée un événement \_monetized qui inclut le total des eRPA pour chaque appareil attribué. Ex  : ad\_matched\_monetized.
* Avec une eRPA le revenu est attribué aux sources média.
* Vous pouvez utiliser l'un des types d'événements suivants :
  * **L'événement d'app unique de monétisation** nécessite des modifications de l'app.
  * Évènement **af\_app\_opened** disponible par défaut.
* Ne rapportez pas le montant des revenus publicitaires dans les événements in-app si l'intégration des revenus publicitaires est en cours. Si vous le faites les revenus publicitaires sont dupliqués dans le tableau de bord car AppsFlyer obtient les données de revenus du réseau de monétisation par intégration.

<div id="aggregate-ad-revenue-using-events" />

#### Agrégation des revenus publicitaires à l'aide d'événements

| Méthode d'événement | Comment procéder à l'implémentation ? | Attention |
| --- | --- | --- |
| Événement d'app unique de monétisation | <ul><li>Un événement d'app est défini au moment de l'affichage de la publicité</li><li>Cela fournit un nombre distinct d'actions utilisateur, ce qui permet d'effectuer des calculs eRPA supérieurs</li><li>On peut augmenter le niveau de précision en créant un événement in-app différent pour chaque réseau de monétisation, ce qui permet de ventiler les revenus par réseau de monétisation<br />. Voir le tableau suivant pour une explication avancée.</li></ul> | <ul><li>Nécessite que le développeur modifie l'app</li><li>Les revenus peuvent être divisés par réseau de monétisation dans le tableau de bord</li></ul> |
| af\_app\_opened event | <ul><li>L'événement af\_app\_opened est envoyé par le SDK Appsflyer par défaut</li><li>Est déclenché par chaque session d'utilisateur</li></ul> | <ul><li>Aucune modification requise dans l'app</li><li>Implémentation rapide</li><li>Les valeurs eRPA sont significativement déformées à moins que vous n'affichiez qu'une seule app par session</li><li>Pas de répartition des revenus par réseau de monétisation</li><li>L'événement concerne tous les utilisateurs qui lancent l'app, et dans le cas ou vous n'avez aucune indication de l'intention de l'utilisateur de regarder les publicités ou non</li></ul> |

<div id="note-2" />

<div id="comparison-of-in-app-event-methods" />

#### Comparaison des méthodes d'événements d'app

| Méthode | Avantages | Inconvénients | Attention |
| --- | --- | --- | --- |
| Utilisez le même événement pour tous les réseaux. Ex : ad\_watched. Cela génère automatiquement l'événement ad\_watched\_monetized qui inclut les détails de la monétisation. | Le plus simple à implémenter | Aucune information de qualité, comme le nombre de clics et les revenus publicitaires par réseau | <ul><li>Idéal si l'objectif principal est de trouver des sources/campagnes qui attirent les utilisateurs les plus enclins à cliquer sur les publicités.</li><li>N'est pas adapté pour comparer les performances des réseaux de monétisation.</li></ul> |
| **(Recommandé)** Attribuez un événement unique à chaque réseau pour le visionnage des publicités. Ex  : ad\_watch\_admob,<br /><br /> ad\_watch\_vungle. | Visibilité totale et possibilité de comparer les réseaux de monétisation dans le tableau de bord, en plus des données brutes. | Les revenus publicitaires ne se cumulent pas en un seul événement. Le nombre d'événements est équivalent au nombre de réseaux | Permet de comparer la monétisation des réseaux dans le tableau de bord. Les revenus publicitaires sont classés par réseau à l'aide d'un événement in-app par réseau. |

</Accordion>

<div id="ad-revenue-api-status-and-testing" />

<Accordion title="Statut et test de l'API pour les revenus publicitaires">

* Le statut opérationnel de l'intégration des revenus publicitaires est indiqué comme suit :

  * <Anchor target="_blank" href="/marketers/fr/docs/dashboard-cost-and-ad-revenue-status">Tableau de bord du statut de l'intégration des coûts et revenus publicitaires</Anchor> : la liste exhaustive des partenaires pour qui l'intégration des revenus publicitaires est activée, et ce pour une ou plusieurs apps hébergées sur votre compte.
  * Certains partenaires vous permettent de tester la connexion API. Dans ce cas, un bouton **Tester la connexion** s'affiche. <Image alt="mceclip0.png" src="https://support.appsflyer.com/hc/article_attachments/360006975517" width="104px" />
  * Pour vérifier que la connexion API est opérationnelle :
  * Cliquez sur **Tester la connexion.**   
    Le message **Clé API vérifiée s'affiche.** Si le message ne s'affiche pas, suivez les instructions du tableau suivant pour corriger le problème.

| Statut | Signification | Remarques/actions requises |
| --- | --- | --- |
| Clé API vérifiée | <ul><li>La connexion est active et peut extraire des données.</li><li><Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#ad-revenue">Les données sont extraites une fois par jour.</Anchor></li></ul> | Aucun |
| Identifiants invalides. | Un ou plusieurs des identifiants fournis sont incorrects. | Obtenez des identifiants corrects auprès du partenaire de revenus publicitaires. |
| Détails de configuration manquants | Un ou plusieurs champs d'identifiants sont incomplets | Récupérez les identifiants dans le tableau de bord du partenaire de revenu publicitaire, ou contactez le partenaire pour obtenir les identifiants. |

</Accordion>

<div id="ad-revenue-data" />

## Données sur les revenus publicitaires

Les données sur les revenus publicitaires sont disponibles via les tableaux de bord AppsFlyer et les rapports de données brutes.

<div id="ad-revenue-aggregate-data" />

<Accordion title="Données agrégées des revenus publicitaires">

Les revenus publicitaires indiquent la qualité des utilisateurs issus de différentes sources au fil du temps. Plus les utilisateurs lancent l'app et s'engagent dans les publicités, plus leur LTV augmente.

**Remarque**: les données de revenus publicitaires peuvent être légèrement différentes d'un tableau de bord et d'un rapport à l'autre. [En savoir plus.](#is-there-discrepency)

L'attribution des revenus publicitaires est disponible comme suit :

* Basés sur la LTV :
  * Les tableaux de bord sont les suivants : Général, Événements,
  * Rapports LTV
  * Tableau de bord et rapports de cohorte
  * Master API
* Basés sur l'activité :
  * Tableau de bord : Activité
  * Données brutes des revenus publicitaires

<div id="overview-dashboard---aggregated-performance-report" />

#### **Tableau de bord général - rapport de performance agrégé**

[![](https://support.appsflyer.com/hc/article_attachments/360002239229)](https://support.appsflyer.com/hc/article_attachments/360002239229)

Dans le tableau Vue d'ensemble :

* Les valeurs, y compris les revenus, sont des LTV. Voir <Anchor target="_blank" href="/marketers/fr/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">La LTV et les données d'activité.</Anchor>
* La colonne **Revenus** inclut l'ensemble des revenus, y compris les revenus publicitaires et les achats in-app.
* Descendez dans la hiérarchie publicitaire (source média, campagne, ad set, geo) pour consulter les événements **monétisés** du rapport.

**Tableau de bord des événements**[![](https://support.appsflyer.com/hc/article_attachments/360002218905)](https://support.appsflyer.com/hc/article_attachments/360002218905)

Dans le tableau de bord Activité :

* Les valeurs qui incluent les revenus sont basées sur la date d'activité. Voir <Anchor target="_blank" href="/marketers/fr/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">La LTV et les données d'activité</Anchor>.
* La **moyenne des actions par utilisateur** indique la tendance des utilisateurs en termes d'engagement avec les publicités présentées dans l'app.

<div id="examples" />

> 📄 **Exemples**
>
> Trois utilisateurs installent une app le 31 décembre 2017. Ils sont attribués comme suit :
>
> * Utilisateur A : Réseau A
> * Utilisateur B : Réseau B
> * Utilisateur C : Organique
>
> L'app est intégrée à cinq plateformes de monétisation différentes. Chaque plateforme utilise un événement in-app unique via le SDK AppsFlyer, comme indiqué ci-après :
>
> * Meta Audience Network : fb\_ad\_view
> * Chartboost : chartboost\_ad\_view
> * Admob : admob\_ad\_view
> * Applovin : applovin\_ad\_view
> * IronSource : is\_ad\_view
>
> Pendant les 4 jours qui suivent l'installation, les utilisateurs voient s'afficher les publicités tel que décrit ci-après :
>
>
>
> | Utilisateur | Réseau UA | fb\_  <br />ad\_view | chartboost\_  <br />ad\_view | admob\_  <br />ad\_view | applovin\_  <br />ad\_view | is\_ad\_view | Total |
> | --- | --- | --- | --- | --- | --- | --- | --- |
> | A | Réseau A<br /><br />31/12/2017 | 01/01/2018<br /><br />1 $ | 02/01/2018<br /><br />1 $ | 03/01/2018<br /><br />1 $ | 04/01/2018<br /><br />1 $ |  | 4 $ |
> | B | Réseau B<br /><br />31/12/2017 | 02/01/2018<br /><br />1 $ |  | 04/01/2018<br /><br />1 $ |  |  | 2 $ |
> | C | Trafic<br /><br />31/12/2017 | 01/01/2018<br /><br />1 $ |  |  |  | 02/01/2018<br /><br />1 $ | 2 $ |
>
>
>
> En examinant les données, nous pouvons maintenant résumer les revenus collectés soit par utilisateur, soit par jour (et par événement in-app) :
>
>
>
> | Utilisateur | 01/01/2018 | 02/01/2018 | 03/01/2018 | 04/01/2018 | LTV totale |
> | --- | --- | --- | --- | --- | --- |
> | A | 1 $ | 1 $ | 1 $ | 1 $ | 4 $ |
> | B |  | 1 $ |  | 1 $ | 2 $ |
> | C | 1 $ | 1 $ |  |  | 2 $ |
> | Total | 2 $ | 3 $ | 1 $ | 2 $ | 8 $ |
>
>
>
> **Comprendre les rapports :**
>
> Comme mentionné, les revenus publicitaires sont liés à la LTV de l'utilisateur. Par conséquent, la période que vous sélectionnez dans le tableau de bord représente la cohorte d'installations pour lesquelles les revenus sont agrégés jusqu'à l'heure et le jour actuels. Examinons un rapport avec deux sélections de dates différentes :
>
> Rapport agrégé : dates sélectionnées : 31/12/2017-05/01/2018
>
>
>
> | Réseau | Revenus LTV |
> | --- | --- |
> | Trafic | 2 $ |
> | Réseau A | 4 $ |
> | Réseau B | 2 $ |
> | Réseau C | 2 $ |
>
>
>
> Dans ce cas, la cohorte est celle des utilisateurs qui ont installé l'app entre le 31/12/2017 et le jour en cours, soit le 05/01/2018. Tous les revenus générés par ces utilisateurs sont liés à la source d'acquisition et représentés dans la LTV de l'utilisateur.

</Accordion>

<div id="ad-revenue-raw-data" />

<Accordion title="Données brutes des revenus publicitaires">

<Image alt="PremiumFeature.jpg" src="https://files.readme.io/674e5d0c9efde9d12008bd705b3ba95f04e133fec3f39d4278612675123d4de4-360007173877.jpg" width="78px" />

Les rapports de données brutes sur les revenus publicitaires contiennent des données fournies par les réseaux de monétisation intégrés à AppsFlyer au niveau appareil et au niveau impression.

**Principes des données brutes sur les revenus publicitaires**

* Les données sont agrégées par le nombre d'impressions uniques par utilisateur. Les impressions uniques sont dérivées de la combinaison du réseau de monétisation publicitaire, de l'unité publicitaire et du placement.
* Les données brutes de niveau impression sont :
  * Agrégées au niveau de l'appareil et disponibles dans les rapports de niveau appareil.
  * Disponibles dans les rapports de niveau impression dans Data Locker.
  * [Les données brutes sont actualisées](/docs/roi360-guide-ad-revenue-attribution#data-freshness) au même rythme que les revenus publicitaires de niveau appareil du tableau de bord Activité.

<table><tbody><tr><th>Rapport</th><th><p>Page Données d'exportation</p></th><th>API Pull </th><th>Data Locker</th></tr><tr><td>Revenus publicitaires attribués (non organiques)</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Revenus publicitaires organiques</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Revenus publicitaires de retargeting </td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Données brutes de niveau impression </td><td><span>-</span></td><td><span>-</span></td><td><span>✓ </span></td></tr><tr><td colspan="4">\* Un rapport versionné est également disponible, il est actualisé plusieurs fois par jour et comporte des données agrégées au niveau de l’appareil. Les rapports Data Locker non versionnés sont émis quotidiennement.</td></tr></tbody></table>

**Caractéristiques et champs des données**

Les champs des rapports sur les revenus publicitaires sont remplis :

* Par l'événement de revenus publicitaires lui-même, et ils sont répertoriés dans le tableau suivant. Ces champs sont divisés en trois catégories :
  * **Spécifique :** champs spécifiques aux revenus publicitaires. Par exemple, les impressions et le placement. **Important !** Les champs renseignés diffèrent selon le partenaire de monétisation, comme le montre le tableau Champs par réseau de cette section.
  * **Contexte :** les champs ayant une signification similaire dans d'autres rapports de données brutes. Par exemple, nom de l'événement, valeur de l'événement, devise.
* Correspond à l'attribution de l'événement à la source média qui a drainé l'utilisateur. Ce qui signifie que ces champs sont copiés depuis l'événement de conversion qui a drainé l'utilisateur. Par exemple, la source média et la campagne. Ces champs ne figurent pas dans le tableau qui suit.

<div id="customer_user_id" />

<div id="mediation_network" />

<div id="impressions" />

<div id="monetization_network" />

<div id="segment" />

<div id="ad_unit" />

<div id="country" />

<div id="event_revenue_xxx" />

<div id="event_revenue_currency" />

<div id="event_revenue" />

<div id="event_name" />

<div id="event_time" />

<div id="fields-populated-by-ad-revenue" />

#### Champs alimentés par les revenus publicitaires

| api\_name | Nom du champ | Type de champ | Description |
| --- | --- | --- | --- |
| event\_time | Heure de l'évènement | Contexte | Date à laquelle le revenu est attribué |
| event\_name | Nom de l'événement | Contexte | <ul><li>La valeur par défaut est af\_ad\_revenue</li><li>Peut également être un événement personnalisé</li></ul> |
| event\_revenue | Devise du revenu des évènements | Contexte | <ul><li>Montant des revenus selon la devise des revenus d'événements.</li><li>La valeur zéro indique une impression dénuée de revenu</li></ul> |
| event\_revenue\_currency | Devise de l'événement | Contexte | Devise du revenu des évènements |
| event\_revenue\_XXX | Revenu de l'évènement XXX | Contexte | <ul><li>Sur la page d'exportation : revenu converti dans la devise spécifique à l'app</li><li>Dans Data Locker, toujours en USD</li><li>Dans l'API Pull, en fonction de la devise de l'extraction.</li></ul> |
| country | Pays | Contexte | Pays d'installation de la conversion de l'installation |
| ad\_unit | Unité publicitaire | Spécifique | Type de publicité |
| segment | Segment | Spécifique | Nom d'emplacement de la publicité |
| monetization\_network | Réseau de monétisation | Spécifique | Réseau qui envoie la publicité |
| Impressions | Impressions | Spécifique | Nombre de fois où l'utilisateur a vu la publicité |
| mediation\_network | Réseau de médiation | Spécifique | Réseau de médiation qui signale l'événement à AppsFlyer |

<div id="h_01KRKHJN2G5SER73D3EZB14GDS" />

<div id="fields-by-network" />

#### Champs par réseau

<table><tbody><tr><th>Nom d'affichage</th><th>Admob</th><th>ironSource</th><th>AppLovin MAX</th><th>Appodeal</th><th>Fyber</th></tr><tr><td>Unité publicitaire</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Segment</td><td>-</td><td>(1)</td><td>-</td><td>-</td><td>-</td></tr><tr><td>Placement</td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Réseau de monétisation</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Impressions</td><td><span>-</span></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td>Réseau de médiation</td><td><span>-</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td colspan="6">(1) L'annonceur doit configurer cet élément dans ironSource</td></tr></tbody></table>

[Exemple de rapport sur les données brutes des revenus publicitaires](https://docs.google.com/spreadsheets/d/e/2PACX-1vRm_1tevWFdzdj6JgdxYawLBtYAJj-ubDeY4g1QfbdSkd2-Adi18oemPMdd7m7cM2e3fzm7VH0w6lhD/pub?output=xlsx)

</Accordion>

<div id="data-freshness" />

<Accordion title="Actualisation des données">

L'actualisation des données dépend du type d'intégration et de la méthode de reporting.

Pour les intégrations d'API S2S, les données sont disponibles au plus tôt :

* Tableaux de bord et rapports (via Data Locker), depuis le jour X+1, 08:00 UTC, environ 4 fois par jour, soit toutes les 6 heures.Et pour les abonnés ROI360, les jours 2, 3, 7 et 14, une fois par jour.

Pour les intégrations SDK de niveau impression, les données sont disponibles au plus tôt :

* Tableaux de bord et rapports (via Data Locker), au plus tôt depuis le jour X à 05:00 UTC, mise à jour environ 6 fois par jour, soit toutes les 4 heures.
* Les rapports de données brutes de niveau impression (via Data Locker) commencent au Jour X à 01:00 UTC, avec une mise à jour toutes les heures.

Pour le niveau impression (via le SDK) avec un niveau appareil (via l'API S2S), l'actualisation des données au jour X et la précision des données pour les jours X+1 sont les suivantes :

* Pour les données de niveau impression qui arrivent via SDK :
  * Tableaux de bord et rapports (via Data Locker), au plus tôt depuis le jour X à 05:00 UTC, mise à jour environ 6 fois par jour, soit toutes les 4 heures.
  * Les rapports de données brutes de niveau impression (via Data Locker) commencent au Jour X à 01:00 UTC, avec une mise à jour toutes les heures.
* Pour les données de niveau appareil qui arrivent via API S2S :
  * Tableaux de bord et rapports (via Data Locker) depuis le jour X+1, 08:00 UTC, environ 4 fois par jour, soit toutes les 6 heures. Et pour les abonnés ROI360, les jours 2, 3, 7 et 14, une fois par jour.

Pour les intégrations héritées (antérieures à ROI360), les données sont actualisées au jour X+1, au plus tôt à 17:00 UTC.

**Remarque :** Lors du changement de type d'intégration, les données reçues avec le type d'intégration précédent pour des dates antérieures ne sont pas complétées par le nouveau type d'intégration. Par exemple, si le jour X le type d'intégration est passé de SDK à S2S, les données sont extraites à partir du jour X+1 et ne sont pas extraites pour les jours précédant le jour X.

<div id="ad-revenue-data-locker-reports" />

<Accordion title="Rapports Data Locker sur les revenus publicitaires">

| Nom | Actualisation | Sections du rapport |
| --- | --- | --- |
| ***Revenus publicitaires quotidiens (agrégées au niveau de l'appareil)*** | Les revenus publicitaires pour un jour donné (jour X) apparaissent dans le rapport du jour suivant (X+1), à 20:00 UTC.<br /><br />Par exemple, les revenus publicitaires du 1er mai apparaîtront dans le rapport du 2 mai. | Le rapport comprend des sections sur les revenus publicitaires attribués, organiques et provenant du retargeting. |
| ***Rapport sur les revenus publicitaires quotidiens*** ***(agrégé au niveau de l'appareil)*** | Le rapport quotidien comprend :<ul><li>Les versions du jour, créées toutes les 4 heures pendant le jour des revenus (jour X). Les données journalières sont collectées par le connecteur SDK ROI.</li><li>Les versions de la journée entière créées les jours 2, 3, 7 et 13, sur la base de données provenant des rapports S2S API.</li></ul>En d'autres termes, le jeu de versions d'un rapport journalier comprend les versions suivantes :<ul><li>00:00 — 04:00 au jour X.</li><li>00:00 — 08:00 au jour X [connecteur SDK ROI]</li><li>00:00 — 12:00 au jour X [connecteur SDK ROI]</li></ul>...* 00:00 — 24:00 au jour X [connecteur SDK ROI]<ul><li>00:00 — 24:00 au jour x+1 [S2S]</li><li>00:00 — 24:00 au jour x+2 [S2S]</li><li>00:00 — 24:00 au jour x+6 [S2S]</li><li>00:00 — 24:00 au jour x+13 [S2S]</li></ul> | Chaque version du rapport comprend des sections sur les revenus publicitaires attribués, organiques et provenant du retargeting. |
| ***Rapport sur les revenus publicitaires au niveau de l'impression (niveau de l'impression)*** | Les enregistrements des revenus publicitaires au niveau de l'impression sont enregistrés toutes les heures dans un fichier distinct. |  |

</Accordion>

</Accordion>

<div id="additional-information" />

## Informations supplémentaires

<div id="migrating-from-aggregate-to-userlevel-granularity" />

<Accordion title="Migrer d'une granularité de niveau agrégé à un niveau appareil">

* La migration n'a pas d'impact sur les données historiques des revenus publicitaires. Ces données restent inchangées.
* Les données sur les revenus publicitaires sont extraites une fois par jour à 1400 UTC, en utilisant les options de granularité sélectionnées à ce moment-là.
* La granularité de niveau appareil ne nécessite pas de définir des événements in-app (comme vous le faites pour les rapports agrégés). Vous pouvez continuer à envoyer ces événements, mais ils n'affectent pas les rapports de granularité de niveau utilisateur dans AppsFlyer.

</Accordion>

<div id="closed-beta--ua-signals-for-ad-networks" />

<Accordion title="Signaux UA pour les réseaux publicitaires">

Travailler avec des réseaux publicitaires pouvant recevoir des signaux UA est une possibilité. Cela signifie que les réseaux publicitaires responsables de l'acquisition d'utilisateurs peuvent recevoir les données des réseaux de médiation pour ce qui concerne les revenus publicitaires, et qu'ils peuvent les mettre à profit pour optimiser les campagnes UA de leurs clients.

Pour transmettre des signaux aux réseaux publicitaires UA, les partenaires de médiation doivent avoir une intégration de niveau impression ou appareil.

* Pour savoir ce que le **partenaire** doit faire pour recevoir le rapport, consultez <Anchor target="_blank" href="/partners/fr/docs/ad-revenue-signals-for-ua-ad-networks#enable-the-ad-revenue-report">ce lien</Anchor>.
* Pour savoir ce que l'**annonceur** doit faire pour donner au partenaire l'accès au rapport, veuillez consulter [ce lien](#permission-to-get-ad-revenue-data).

**Liste des partenaires de médiation pouvant envoyer des signaux UA aux réseaux publicitaires UA :**

* Applovin Max
* Google AdMob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* Médiation Unity LevelPlay (anciennement ironSource)
* Admost
* Tradplusad
* Yandex

**Liste des réseaux publicitaires UA qui peuvent recevoir des signaux UA :**

* AdAction
* Adamobi
* Adjoe
* Adonco
* Adshow
* Appier
* Apprainbow
* Aura par Unity
* Betop
* Bidswave
* Brandscale
* Chameleostudios
* Chartboost
* Datawave
* DLab
* Ecomonline
* Etusdigital
* Foregon
* GNA Company
* Happimobi
* Hybrid
* Inflecto
* Irismedia
* Lambadapp
* Leadidadmonster
* Lifestreet
* Liftoff
* Melodong
* Mintegral
* Mobrand
* Moloco
* Motive
* Mpnd
* Msla
* Muvmobile
* Nexamob
* Nftdroper
* Nsofmedia
* Performadlive
* Personalyrtb
* Pitatroas
* Rebornads
* RTBhouse
* Runfuns
* Scmobi
* Shalltry
* Shareit
* Smadex
* Tapjoy
* Targetmedia
* Thepurpleline
* TikTok pour les entreprises
* Trademob
* Truemoney
* Unity Ads
* Yandex
* Yeahmobi
* Z2A Digital
* Zoyo

</Accordion>

<div id="permission-to-get-ad-revenue-data" />

<Accordion title="Permettre aux réseaux publicitaires d'obtenir les données brutes de revenus publicitaires">

Avant de pouvoir recevoir les données des réseaux de médiation, les réseaux publicitaires responsables de l'acquisition d'utilisateurs doivent obtenir votre autorisation.

**Conditions préalables** :

* L'abonnement à ROI360 Advanced est requis.
* Contactez le réseau publicitaire pour confirmer qu'il dispose du processus d'ingestion nécessaire pour traiter au mieux vos données.

**Pour permettre aux réseaux publicitaires d'obtenir les données de revenus publicitaires :**

1. Allez dans **Configuration** > **Intégrations actives**.
2. Sélectionnez le partenaire intégré.
3. Ouvrez l'onglet **Intégration**.
4. Vérifiez que **Activer le partenaire** est coché. Si l'option n'est pas activée, les données ne seront pas partagées.
5. Allez dans l'onglet **Autorisations**.
6. Activez les **Autorisations du réseau publicitaire**.
7. Activez **Accéder aux données brutes des revenus publicitaires**.
8. Dans **Option d'envoi**, précisez si vous souhaitez envoyer les données de revenus publicitaires de ce partenaire uniquement (**Ce partenaire uniquement**) ou celles issues de toutes les sources média (**Toutes les sources média, y compris organiques**).
9. Cliquez sur **Enregistrer les paramètres**.
10. Contactez le réseau publicitaire pour l'informer que vous lui avez accordé les autorisations.
11. Assurez-vous que <Anchor target="_blank" href="/partners/fr/docs/ad-revenue-signals-for-ua-ad-networks#enable-the-ad-revenue-report">le réseau publicitaire a activé le rapport dans son Data Locker, et configuré ses paramètres de sortie.</Anchor>

</Accordion>

<div id="ad-revenue-event-postbacks-for-ad-networks" />

<Accordion title="Postbacks d'événements des revenus publicitaires pour les réseaux publicitaires">

Vous pouvez configurer les postbacks de revenu publicitaire pour les réseaux publicitaires. Cela signifie que les réseaux publicitaires responsables de l'acquisition d'utilisateurs peuvent recevoir les données des réseaux de médiation en temps réel (pour ce qui concerne les revenus publicitaires) et qu'ils peuvent les mettre à profit pour optimiser les campagnes UA de leurs clients. 

Pour envoyer des postbacks aux réseaux publicitaires UA, vous devez avoir une intégration de niveau impression via le SDK avec le réseau de médiation. AppsFlyer génère automatiquement un événement af\_ad\_revenue pour chaque impression. Ces événements peuvent être sélectionnés dans la liste des événements à envoyer au réseau publicitaire UA via les <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration">postbacks d'évènements in-app</Anchor>.

> 🚧 **Important !**
>
> Bien que vous puissiez envoyer des postbacks de revenus publicitaires à des partenaires spécifiques, vous devez valider la façon dont les partenaires utilisent les données avant de commencer l'intégration.

**Pour mettre en place des postbacks d'événements générateurs de revenus publicitaires** :

1. Recherchez et sélectionnez votre partenaire, soit <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations#gérer-les-intégrations-existantes">à partir du marketplace</Anchor> , soit à partir de la page **Configuration** > **Intégrations** **actives**.
2. Dans l'onglet **Integration**, faites défiler vers le bas et activez **Postbacks d'évènements in-app**.
3. Sélectionnez l'événement AppsFlyer af\_ad\_revenue.
4. Mettez-le en correspondance avec l'événement du réseau publicitaire UA comme suit : 

| Réseau publicitaire UA | Événement à associer à af\_ad\_revenue | Capture d'écran |
| --- | --- | --- |
| ironSource | adRevenue | [![](https://files.readme.io/fd902115e177e02ad96e20f2e0a81bbebbc324f5cc02b7e504e26ddd4f840897-17566964074257.png)](https://files.readme.io/fd902115e177e02ad96e20f2e0a81bbebbc324f5cc02b7e504e26ddd4f840897-17566964074257.png) |
| Unity Ads | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Moloco | Aucun mappage n'est nécessaire |  |
| Mintegral | Aucun mappage n'est nécessaire |  |
| Smadex | Aucun mappage n'est nécessaire |  |
| Meta Ads | fb\_mobile\_purchase | [![](https://files.readme.io/fa62ae03002f9989482f8cb2b2d1628529110dbb8d17041d6ad865e381ee0361-17566964080145.png)](https://files.readme.io/fa62ae03002f9989482f8cb2b2d1628529110dbb8d17041d6ad865e381ee0361-17566964080145.png) |
| TikTok for Business - SRN avancé | ImpressionLevelAdRevenue | [![](https://files.readme.io/8beed93895ac3e9d52049bea06b89388e8f32ca12d404c3461a3dcc493aed26f-24100803659665.png)](https://files.readme.io/8beed93895ac3e9d52049bea06b89388e8f32ca12d404c3461a3dcc493aed26f-24100803659665.png) |
| Aura par Unity | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |

5. Cliquez sur **Enregistrer l'intégration**.

**Liste des partenaires de médiation pouvant envoyer des événements de revenus publicitaires de niveau impression aux réseaux publicitaires UA :**

* Applovin Max
* Google AdMob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* ironSource
* Admost
* Tradplusad
* Yandex

**Liste des réseaux publicitaires UA pouvant recevoir des postbacks d'événements des revenus publicitaires :**

* ironSource
* Unity Ads
* Moloco
* Mintegral
* Meta Ads
* Smadex
* TikTok for Business - SRN avancé

</Accordion>

<div id="faq" />

<Accordion title="FAQ">

<span id="01ECF1PZ38DM24YCZPVH104FP4"></span>| **Comment puis-je obtenir le revenu publicitaire total de chaque plateforme ?**<ul><li>L'attribution des revenus publicitaires est liée et s'affiche par rapport à la source d'acquisition utilisateur.</li><li>Cela permet d'avoir une vue de la LTV de votre ROI et de vos KPI.</li><li>Pour afficher le revenu total de chaque plateforme de monétisation, [utilisez un événement in-app différent pour chaque réseau](/docs/roi360-guide-ad-revenue-attribution#aggregate-granularity-using-app-open-or-inapp-events) et suivez la procédure suivante :<ol><li>Dans le dashboard général, rendez-vous dans **tableau de rapports des performances agrégées**.</li><li>Sélectionnez jusqu'à quatre événements monétisés représentant les plate-formes que vous souhaitez interroger.</li></ol></li></ul>![selecting_monetized_events.png](https://support.appsflyer.com/hc/article_attachments/360002218865)<ol><li>Téléchargez le rapport en cliquant sur **Exporter le CSV.**</li><li>Additionnez les chiffres de la colonne **Revenue** correspondant à l'événement monétisé de la plateforme demandée.</li></ol>![revenue_sum_up.png](https://support.appsflyer.com/hc/article_attachments/360002218885)<br /><br />Remarque : ce revenu publicitaire total est composé de données LTV, c'est-à-dire l'entièreté des revenus générés par un réseau monétisé sur votre app, et ce pour les utilisateurs qui ont installé l'app pendant la période spécifiée. |
| --- |
| **Les revenus publicitaires sont-ils disponibles sur la page d'activité ?**<br /><br />Oui. La page Activité indique l'ensemble des revenus issus des achats in-app et des revenus publicitaires. **Remarque** : les données de revenus publicitaires sont envoyées à AppsFlyer sur une base quotidienne, le lendemain de l'événement. |
<span id="01ECF1PZ39C7CG3R7H9P64QF51"></span>| **Dois-je activer le partenaire dans l'onglet Intégration ?**<br /><br />Si vous collaborez avec le partenaire uniquement en ce qui concerne la monétisation publicitaire (revenus publicitaires), ne choisissez pas l'option **Activer le partenaire** dans l'onglet intégration. Activez uniquement **Obtenir les revenus publicitaires** dans l'onglet des revenus publicitaires. |
<span id="01ECF1PZ39KCKY2BC3ZGK3CA0V"></span>| **Comment les revenus publicitaires au niveau de l'appareil sont-ils attribués si un utilisateur a une version de l'app sans le SDK AppsFlyer ?**<br /><br />Les revenus publicitaires sont attribués comme étant organiques. |
<span id="is-there-discrepency"></span>| **Y a-t-il des différences de données de revenus publicitaires d'un tableau de bord ou d'un rapport à l'autre ?**<br /><br />Il peut y avoir des écarts entre les données de revenus publicitaires affichées dans le tableau de bord général, dans les rapports de données brut et dans les tableaux de bord Activité ou Cohorte. Explications :<ul><li>Les données de revenus publicitaires des tableaux de bord Cohorte et Activité, ainsi que les données issues des API principales et API de cohorte, sont mises à jour rétroactivement. Ce qui n'est pas le cas dans le tableau de bord Général, ni dans l'exportation de données brutes ou l'API Pull.</li><li>Les données s'affichent parfois dans les tableaux de bord Activité et Cohorte avant d'apparaitre dans le tableau de bord général.</li><li>Les tableaux de bord incluent les événements marqués comme `af_ad_revenue` et `_monetized`, alors que les données brutes ne comprennent que les événements `af_ad_revenue`.</li></ul> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Particularités et limites">

| Particularité | Remarques |
| --- | --- |
| Limites | Les événements de revenus publicitaires ne sont pas disponibles pour :<ul><li>API push</li><li>Tableau de bord de retargeting</li></ul>Limitations de granularité au niveau de l'appareil :<ul><li>L'événement af\_ad\_revenue n'est pas disponible pour les cohortes dans Pivot et Master API.</li><li>L'événement est disponible dans l'analyse de cohorte.</li><li><Anchor target="_blank" href="/marketers/fr/docs/applovin-max-ad-revenue-configuration#best-practice">Des divergences peuvent se produire lors de l'implémentation des revenus d'enchères **in-app** de Meta ads.</Anchor></li></ul>Le nombre d'utilisateurs uniques qui ont déclenché un événement af\_ad\_revenue n'est pas disponible dans les tableaux de bord AppsFlyer. |
| Accès du réseau publicitaire | Impossible d'accéder aux rapports de cohorte |
| Autorisations de l'agence | Agences :<ul><li>Impossible d'accéder aux configurations des revenus publicitaires.</li><li>Peut consulter tous les dashboards et les données qui y sont liées.</li></ul> |
| Transparence de l'agence | Non pris en charge |
| Fuseau horaire | Les revenus publicitaires s’affichent dans les tableaux de bord et les rapports AppsFlyer uniquement dans le fuseau horaire UTC. En d'autres termes, si les données sont rapportées à 14 h UTC+2, dans AppsFlyer elles s'affichent à 14 h UTC. Traitement quotidien.<br /><br />AppsFlyer doit en effet standardiser les données issues de multiples sources et partenaires, or la plupart rapportent leurs données en UTC. |
| Devise | Dans AppsFlyer  :<ul><li>Le dashboard affiche la devise spécifique à l'app de l'annonceur.</li><li>Les rapports sur les données brutes affichent la devise d'origine, qu'elles convertissent en plus dans la devise spécifique à l'app de l'annonceur.</li></ul> |
| Type de données | Les données organiques et non organiques sont toutes prises en charge |
| Actualisation des données | [Revenus publicitaires](/docs/roi360-guide-ad-revenue-attribution#data-freshness) |
| Données historiques/rétroactives | <ul><li>Les données sont extraites et disponibles à compter du jour de l'intégration. Les données historiques ne sont donc pas disponibles avant le jour de l'intégration (jour 0).</li><li>Les données de revenus publicitaires reçues via API S2S un certain jour sont mises à jour les jours 1, 2 et 3.</li><li>Les données de revenus publicitaires des tableaux de bord Cohorte et Activité, ainsi que les données issues des API principales et API de cohorte, sont mises à jour rétroactivement. Ceci n'est pas le cas dans le tableau de bord Général, ni dans l'exportation de données brutes ou l'API Pull.  Si vous disposez du package revenus avancés, les données sont également mises à jour dans Data Locker.</li></ul> |
| Accès utilisateur du compte | Prise en charge |
| SKAN | Pris en charge par des connecteurs SDK de revenus publicitaires au niveau de l’impression. |
| Géo/pays | Dans le tableau de bord de cohorte, lorsque les données géo sont inconnues (N/A), les données N/A ne s'affichent pas lors de l'agrégation par géo. |
| Postback d'évènements in-app | Les postbacks envoyés aux partenaires sont ceux qui concernent les données des événements in-app attribués à ces mêmes partenaires ; ils n'incluent pas les données relatives aux autres sources média. |
| Applications CTV, PC et consoles | Pas de prise en charge. Seules les applications Android et iOS sont prises en charge. |

</Accordion>

<div id="list-of-ad-revenue-integrated-partners" />

<Accordion title="Liste des partenaires intégrés de revenus publicitaires">

| Partenaire | Paramètres d'identification requis | Granularité des données |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/fr/docs/adcolony-campaign-configuration">AdColony</Anchor> | <ul><li>Clé API</li><li>ID d'app</li></ul> | Niveau agrégé avec géo |
| Admost | <ul><li>ID de l'app réseau</li><li>Jeton</li></ul> | Au niveau appareil avec géolocalisation |
| <Anchor target="_blank" href="/marketers/fr/docs/applovin-campaign-configuration">AppLovin</Anchor> | <ul><li>Clé du rapport</li><li>Nom du package de l'app</li></ul> | Niveau agrégé avec géo |
| <Anchor target="_blank" href="/marketers/fr/docs/applovin-max-ad-revenue-configuration">AppLovin MAX</Anchor> | <ul><li>Clé du rapport</li><li>Nom du package de l'app</li></ul> | <ul><li>Niveau appareil avec géolocalisation</li><li>Niveau impression (via le SDK)</li></ul> |
| <Anchor target="_blank" href="/marketers/fr/docs/appodeal-campaign-configuration">Appodeal</Anchor> | <ul><li>Clé d'application</li><li>Clé API</li><li>ID utilisateur</li></ul> | <ul><li>Niveau agrégé avec géo</li><li>Niveau appareil</li></ul> |
| <Anchor target="_blank" href="/marketers/fr/docs/bytedance-ads-china-campaign-configuration">Bytedance Ads - Trafic en Chine</Anchor> | <ul><li>Clé sécurisée</li><li>ID d'app</li><li>ID de compte</li></ul> | Niveau agrégé avec géo |
| <Anchor target="_blank" href="/marketers/fr/docs/chartboost-campaign-configuration">Chartboost</Anchor> | <ul><li>ID utilisateur</li><li>Signature de l'utilisateur</li><li>ID d'app</li></ul> | Niveau agrégé avec géo |
| <Anchor target="_blank" href="/marketers/fr/docs/meta-ads-integration-setup">Meta Ads</Anchor> | <ul><li>Se connecter à Meta ads</li></ul> | Niveau agrégé avec géo |
| <Anchor target="_blank" href="/marketers/fr/docs/fyber-campaign-configuration#ad-revenue-tab">Fyber</Anchor> | <ul><li>Code secret client</li><li>ID D'API</li><li>ID du client</li></ul> | <ul><li>Niveau appareil avec géolocalisation</li><li>Niveau impression (via le SDK)</li></ul> |
| Google marketing platform - DV360/CM (DoubleClick) | <ul><li>Connexion à Google Marketing Platform - DV360/CM</li></ul> | Niveau agrégé avec géo |
| <Anchor target="_blank" href="/marketers/fr/docs/google-admob-ad-revenue-attribution-configuration">Google Admob</Anchor> | <ul><li>ID d'app AdMob</li></ul> | <ul><li>Niveau agrégé avec géo</li><li>Niveau impression (via le SDK)</li></ul> |
| <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-cost-and-ad-revenue#enregistrement-des-revenus-publicitaires-avec-google-ads">Google Ads</Anchor> | <ul><li>Authentification API par OAuth</li></ul> | Niveau agrégé avec géo |
| <Anchor target="_blank" href="/marketers/fr/docs/ironsource-campaign-configuration#ad-revenue-tab">IronSource</Anchor> | <ul><li>Clé secrète</li><li>Nom d'utilisateur</li><li>ID d'app</li></ul> | <ul><li>Niveau agrégé avec géo</li><li>Niveau appareil</li><li>Niveau impression (via le SDK)</li></ul> |
| Mintegral | <ul><li>ID d'app</li><li>Clé secrète</li><li>Clé API</li></ul> | Niveau agrégé avec géo |
| Tapjoy | <ul><li>ID d'app</li><li>Clé API marketing</li></ul> | Au niveau appareil avec géolocalisation |
| TikTok pour les entreprises | <ul><li>Clé sécurisée</li><li>ID d'app</li><li>ID de compte</li></ul> | Niveau agrégé avec géo |
| TopOn | <ul><li>ID de l'app réseau</li><li>Clé de l'éditeur</li></ul> | Au niveau appareil avec géolocalisation |
| Médiation Tradplus | <ul><li>Clé API</li><li>ID de l'app réseau</li></ul> | Au niveau appareil avec géolocalisation |
| <Anchor target="_blank" href="/marketers/fr/docs/unity-ads-campaign-configuration">Unity Ads</Anchor> | <ul><li>Clé API</li><li>ID d'app</li></ul> | <ul><li>Niveau agrégé avec géo</li><li>Niveau impression (via le SDK)</li></ul> |
| Voodoo Ads | <ul><li>ID de groupe</li><li>Jeton d'accès</li></ul> | Niveau agrégé avec géo |
| <Anchor target="_blank" href="/marketers/fr/docs/vungle-campaign-configuration">Vungle</Anchor> | <ul><li>Clé API</li><li>ID d'app</li></ul> | Niveau agrégé avec géo |
| Yandex | S/O | <ul><li>Niveau impression (via le SDK)</li></ul> |

</Accordion>

<div data-zendesk-anchors="ad-revenue-attribution=lattribution-des-revenus-publicitaires 01ECF1PZ2XNCHR4QPATTBV0VMV=lattribution-des-revenus-publicitaires 01ECF1PZ2Y6ZBAWSNQPEXGJWX3=integration-types-for-ad-revenue-attribution implementation=impl%C3%A9mentation 01ECF1PZ2Y9ERT5C50ZD4CDJET=impl%C3%A9mentation 01ECF1PZ31TBRGG7GW3404Y1HN=connect-to-ad-revenue-integrated-partners 01H8V10BKK6TVY9G1KWC273K0S=deduplicate-cross-referenced aggregate-ad-revenue-using-events=agr%C3%A9gation-des-revenus-publicitaires-%C3%A0-laide-d%C3%A9v%C3%A9nements 01H8V10BKK06Z3E823G6GNTPKH=agr%C3%A9gation-des-revenus-publicitaires-%C3%A0-laide-d%C3%A9v%C3%A9nements comparison-of-inapp-event-methods=comparaison-des-m%C3%A9thodes-d%C3%A9v%C3%A9nements-dapp 01H8V10BKKMG2A704NZC2VFSJM=comparaison-des-m%C3%A9thodes-d%C3%A9v%C3%A9nements-dapp 01ECF1PZ32Z4C20NADJ2SF3EPC=ad-revenue-api-status-and-testing ad-revenue-data=donn%C3%A9es-sur-les-revenus-publicitaires 01ECF1PZ3315R242DC78HV60YC=donn%C3%A9es-sur-les-revenus-publicitaires 01ECF1PZ33EJHN1YY0DMFKWY7N=ad-revenue-aggregate-data overview-dashboard-aggregated-performance-report=tableau-de-bord-g%C3%A9n%C3%A9ral---rapport-de-performance-agr%C3%A9g%C3%A9 01ECF1PZ348365STFGE3136WEJ=tableau-de-bord-g%C3%A9n%C3%A9ral---rapport-de-performance-agr%C3%A9g%C3%A9 01ECF1PZ348P0JCBASS4QBD56W=exemples 01ECF1PZ36R9W7A0X4WBR95JDS=ad-revenue-raw-data fields-populated-by-ad-revenue=champs-aliment%C3%A9s-par-les-revenus-publicitaires 01H8V10BKK7BHC31W27G22D23K=champs-aliment%C3%A9s-par-les-revenus-publicitaires fields-by-network=champs-par-r%C3%A9seau 01H8V10BKKW6NERRYCRD6BVZ54=champs-par-r%C3%A9seau 01H8V10BKK6N5XJ6GHKC201E3Y=data-freshness 01H8V10BKKG50X5RZR8T2YB092=ad-revenue-data-locker-reports additional-information=informations-suppl%C3%A9mentaires 01H8V10BKMX7H9H04ZBF3HRJVY=informations-suppl%C3%A9mentaires 01H8V10BKMH781GR6GHFSD5N50=migrating-from-aggregate-to-userlevel-granularity %5Bclosed-beta%5D-ua-signals-for-ad-networks=closed-beta--ua-signals-for-ad-networks 01H8V10BKM7MMM63JHGCF2DYMC=closed-beta--ua-signals-for-ad-networks 01H8V10BKMGBZ6APJ8A9G7XDKS=informations-suppl%C3%A9mentaires h_01H5W1BP1CA6F3HDX1F5TS98P1=permission-to-get-ad-revenue-data 01H8V10BKMED8J73G22CFVH6GJ=ad-revenue-event-postbacks-for-ad-networks h_01HFAAC1J9KQ6ZNSCRSRKE9GA3=important- 01H8V10BKM75W6YZ59S6FHFY93=faq 01ECF1PZ39PTEPWJDQA4XPBR4R=traits-and-limitations 01ECF1PZ3A2E5GVNC6D6XDC6WW=list-of-ad-revenue-integrated-partners" />
