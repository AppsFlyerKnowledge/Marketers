---
title: Guide d'attribution de retargeting
metadata:
  keywords:
    - Attribution
    - Re-targeting
    - retargeting
    - Advertisers
    - reatribution
    - re-atribution
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-09-30T13:18:26Z'
  edited_at: '2023-11-14T11:19:34Z'
  id: 207033786
  locale: fr
  section: Retargeting attribution
  section_id: 6551326229265
  url: https://support.appsflyer.com/hc/fr/articles/207033786
---
> **En bref :** les campagnes de retargeting (remarketing) incitent les utilisateurs à ouvrir une application et à se réengager, elles poussent également ceux qui ont supprimé une app à la réinstaller à nouveau.

## Les bases du retargeting

L'attribution de retargeting a lieu lorsqu'un utilisateur s'engage dans une campagne de retargeting en cliquant sur un [lien d'attribution de retargeting](/docs/retargeting-attribution-guide#retargeting-attribution-links) ou bien sur un <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template">deep link.</Anchor> Ce qui génère l'un des événements d'attribution suivants :

* **Réengagement :** si l'app est déjà sur l'appareil, la source média qui incite l'utilisateur à ouvrir l'application est créditée d'un réengagement.
* **Réattribution (ou «réinstallation de retargeting»)** : si l'app n'est pas présente sur l'appareil de l'utilisateur (car celui-ci l'a désinstallée), l'engagement dans la campagne de retargeting fait qu'il réinstalle puis ouvre l'application. Si cela se produit au cours d'une <Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window">fenêtre de réattribution</Anchor> : la réattribution sera imputée à la source média de retargeting. Lecture connexe : <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#reinstalls">Les réinstallations.</Anchor>

![](https://files.readme.io/64b8d9f5040daa281ae13f0855749ab4a88a2e7e8616d6ada37975899db92c80-31937591646097.png)

Avant de lancer une campagne de retargeting, consultez les règles de réengagement et les exemples pratiques des sections suivantes. Vous pourrez ensuite mettre en place le retargeting en suivant les es instructions du chapitre dédié au retargeting. Pour une meilleure compréhension, nous vous conseillons de prendre connaissance du <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model">modèle d'attribution</Anchor> AppsFlyer et des fenêtres d'attribution qui lui sont associées.

> 👍 **Astuce**
>
> Vous voulez en savoir plus le retargeting ? Suivez cette <Anchor target="_blank" href="https://elevate.appsflyer.com/pages/142/remarketing">brève formation</Anchor> sur le portail d'apprentissage AppsFlyer.

<div id="reengagement-rules-and-windows" />

<Accordion title="Règles et fenêtres de réengagement">

* Les règles d'attribution de retargeting permettent de déterminer si un événement est un événement de retargeting, et s'il est bien attribué à la source média de retargeting.
* Tout comme dans les campagnes d'attribution d'acquisition d'utilisateur, les réengagements de retargeting des SRN sont rapportés via API, et ceux des non-SRN via lien d'attribution.
* Les règles, qui se basent sur le parcours utilisateur, sont constituées de :
  * [Fenêtres d'inclusion](/docs/retargeting-attribution-guide#fenêtres-dinclusion), la période durant laquelle un réengagement peut avoir lieu.
  * [Fenêtres d'exclusion](/docs/retargeting-attribution-guide#fenêtres-dexclusion), la période durant laquelle un réengagement ne peut pas avoir lieu.
* Si un réengagement est attribué, les événements in-app sur toute la durée de la fenêtre de réengagement sont <Anchor target="_blank" href="/marketers/fr/docs/resolve-retargeting-double-attribution">doublement attribués.</Anchor> Ce qui signifie qu'il sera attribué d'une part à la source média de retargeting et d'autre part à la source média AU d'origine, si celle-ci est connue.

Le schéma suivant détaille l'ensemble des règles de réengagement. Il vous aidera à déterminer si une interaction avec une campagne de retargeting sera attribuée ou non comme un réengagement.

**Règles de réengagement**

![](https://files.readme.io/e6643112f3e9969242c0dd394f6401406fbc837a9494cc4bb3825cff6365f36d-33563511578513.png) **Références—les fenêtres d'inclusion et d'exclusion**

Les tableaux suivants contiennent des informations relatives aux fenêtres liées à l'attribution de retargeting.

#### Fenêtres d'inclusion

| Type de fenêtre | Description |
| --- | --- |
| Fraude de visibilité | Durée maximum entre le moment où l'utilisateur consulte une publicité et celui où il ouvre une app.<br /><br />**Où est-elle configurée**: lien d'attribution<br /><br />**Durée** :<ul><li>Par défaut : 1 jour</li><li>Période : 01-23 heures / 1-7 jours</li></ul> |
| Rétrospective post-clic | Durée maximum entre le moment où l'utilisateur clique sur une publicité et celui où il ouvre une app.<br /><br />**Où est-elle configurée**: lien d'attribution<br /><br />**Durée** :<ul><li>Par défaut : 7 jours</li><li>Période : 1-23 heures / 1-30 jours</li></ul>**Spécificités SRN :** demandez au SRN quels sont les termes spécifiques à leur fenêtre rétrospective. |
| RÉENGAGEMENT | Quelques éléments à prendre en compte au sujet des fenêtres de réengagement :<ul><li>La fenêtre démarre lorsque l'utilisateur ouvre l'app pour la première après son interaction avec la source média de retargeting.</li><li>À l'intérieur de la fenêtre, les événements in-app sont <Anchor target="_blank" href="/marketers/fr/docs/resolve-retargeting-double-attribution">doublement attribués</Anchor> aux sources média de retargeting et d'acquisition d'utilisateurs.</li><li>La durée de la fenêtre est déterminée par le paramètre de l'app ou par le SRN.</li><li>Si l'utilisateur s'engage dans une autre campagne de retargeting au cours de la fenêtre de réengagement (celle-ci n'étant pas bloquée par une fenêtre d'exclusion), alors la fenêtre de réengagement en cours se termine sur le champ et une nouvelle fenêtre de réengagement démarre.</li><li>Dans le cadre d'une réattribution : la  **fenêtre d'attribution**  est illimitée dans le temps (similaire aux installations). Notez cependant que la fenêtre prend fin dans le cas d'une nouvelle installation, d'une réinstallation, ou à cause d'une limitation de la rétention des données.</li></ul>**Où est-elle définie** : lien d'attribution<ul><li>Défaut : 30 jours</li><li>Période : 1-23 heures / 1-90 jours / valeur vie (lifetime).</li></ul>**Spécificités SRN**: configurable pour les SRN<br /><br />Si vous modifiez le paramètre de la fenêtre, les changements s'appliquent sur les réengagements à venir. Ils n'affectent pas les réengagements déjà existants. |

#### Fenêtres d'exclusion

| Type de fenêtre | Description |
| --- | --- |
| Durée minimale entre les conversions de réengagement | N'enregistrez jamais un réengagement au cours de la fenêtre d'exclusion.<br /><br />**Durée minimale entre les conversions de réengagement**<ul><li>Lors du réengagement, une fenêtre pendant laquelle les événements in-app sont attribués à la fois aux campagnes de retargeting (primaires) et d'UA (non primaires) débute.</li><li>Cela permet de mesurer les performances des campagnes de retargeting.</li><li>Si un autre réseau ou une autre campagne génère un réengagement pendant cette fenêtre :<ul><li>[Par défaut], la fenêtre de réengagement existante est fermée, un autre réengagement est enregistré et les événements in-app suivants sont attribués au réengagement le plus récent.</li><li>Pour éviter que cela se produise, définissez un délai minimum entre les conversions de réengagement. Chaque nouvel engagement ne pourra ainsi être enregistré qu'une fois le temps minimum écoulé.</li></ul></li><li>Ce réglage n'a aucune incidence dans les cas où la durée de la fenêtre de réengagement est plus courte que la durée de ce réglage. Exemple : si les fenêtres de réengagement sont de 1 jour et que ce paramètre est de 4 jours, alors ce paramètre n'a aucun impact.</li><li>Ces paramètres n'affectent pas le délai entre l'installation et le réengagement.</li></ul>**Où la régler :** page des paramètres de l'app<br /><br />**Durée** :<ul><li>Par défaut : aucune</li><li>Période : 1-23 heures / 1-30 jours</li></ul> |
| <Anchor target="_blank" href="/marketers/fr/docs/set-retargeting-inactivity-window">Période d'inactivité minimale</Anchor> | N'enregistre pas de réengagement ou de réattribution pendant la fenêtre d'exclusion.<br /><br />**Où définir :** la page des paramètres des partenaires intégrés, dans l'onglet Intégration.<br /><br />**Durée** :<ul><li>Par défaut : aucune</li><li>0-30 jours</li></ul>**Remarques sur les SRN** : Considérez que les SRN suivent généralement leurs propres règles en matière de période d'inactivité. Si votre réglage diffère de celui du SRN, cela peut entraîner des divergences. |
| <Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window">Réattribution</Anchor> | La fenêtre de réattribution influence les réattributions mais pas les réengagements.<br /><br />Les utilisateurs qui réinstallent au cours d'une fenêtre de réattribution après interaction avec une campagne de retargeting sont attribués aux sources média de retargeting. Lecture connexe : <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#reinstalls">Les réinstallations</Anchor><br /><br />**Où la définir :** paramètres de l'app |

#### **Exemple d'implémentation des règles**

![](https://files.readme.io/f4b53c27319370434863c156bf29051db9c2c12fda2128d0faf0f8a6ca6b7002-33563511579537.png)

Liste des règles de réengagement pour l'attribution post clic et post vue :

| Règle | Règle |
| --- | --- |
| A | Un utilisateur s'est engagé dans une campagne de retargeting, en d'autres termes il a visualisé (ou a cliqué sur) une publicité définie comme étant une publicité de retargeting. |
| B | L'engagement a eu lieu **au cours** d'une fenêtre rétrospective post-vue ou post-clic. |
| C | L'utilisateur a été inactif sur un temps plus long que la durée d'inactivité minimale. |
| D | Dans le cas d'événements in-app, ils ont lieu au cours de la fenêtre de réengagement. |
| E | Le temps après le dernier réengagement est plus long que la durée minimale entre deux réengagements. |

</Accordion>

<div id="example-retargeting-scenarios" />

<Accordion title="Exemples pratiques de retargeting">

| **Exemple 1 : des achats avant, pendant et après la fenêtre de réengagement**<br /><br />Parcours utilisateur :<ul><li>S'engage avec une publicité du réseau Z, installe l'application et effectue un achat (A).</li><li>S'engage avec une publicité de retargeting du réseau Y, installe l'app et effectue un achat (B).</li><li>Effectue un achat (C).</li></ul>![](https://files.readme.io/f4b53c27319370434863c156bf29051db9c2c12fda2128d0faf0f8a6ca6b7002-33563511579537.png)<br /><br />Colonne P/S : primaire ou secondaire comme défini dans la <Anchor target="_blank" href="/marketers/fr/docs/resolve-retargeting-double-attribution">double attribution des événements de retargeting</Anchor> |
| --- |
| **Exemple 2 : plusieurs conversions au cours de la fenêtre d'attribution de réengagement**<br /><br />Parcours utilisateur :<ul><li>S'engage avec une publicité du réseau Z, installe l'application et effectue un achat (A).</li><li>S'engage avec une publicité de retargeting du réseau Y, installe l'app et effectue un achat (B).</li><li>Effectue un achat (C).</li></ul>![](https://files.readme.io/bf57f8a9597bd56a89bb3f1be3700195e1b153b548cb11ee3d37c65d5382e711-33563474530321.png)<br /><br />Colonne P/S : primaire ou secondaire comme défini dans la <Anchor target="_blank" href="/marketers/fr/docs/resolve-retargeting-double-attribution">double attribution des événements de retargeting</Anchor> |

</Accordion>

## Opérations de retargeting

<div id="retargeting-settings" />

<Accordion title="Paramètres de retargeting">

Les réglages suivants sont requis en fonction des différents cas.

| Type de conversion | SRN | Non SRN |
| --- | --- | --- |
| RÉENGAGEMENT | <ol><li>Rendez-vous dans **Configuration** > **Paramètres de l'app**.</li><li>Vérifiez que l'option **attribution** de **réengagement** est bien activée.</li><li>Par SRN : allez dans **Configuration** > **Intégrations actives, puis** sélectionnez le SRN.</li><li>Activez **Attribution de réengagement.**</li></ol> | <ol><li>Rendez-vous dans **Configuration** > **Paramètres de l'app**.</li><li>Vérifiez que l'option **attribution** de **réengagement** est bien activée.</li><li>Par non-SRN : appliquer le paramètre de retargeting aux liens d'attribution tel que décrit dans cette section</li></ol> |
| Réattribution | <ol><li>Allez dans **Configuration** > **Intégrations actives,** puis sélectionnez le SRN.</li><li>Activez l'**attribution de réinstallation.**</li></ol> | <ol><li>Aucun réglage particulier n'est requis.</li><li>Ajouter le paramètre de retargeting aux liens d'attribution tel que décrit dans cette section.</li></ol> |

#### **Paramètres non-SRN**

**Pour installer un partenaire de retargeting du réseau publicitaire (non-SRN)** :

1. Dans AppsFlyer, allez dans **Configuration** > **Intégrations actives**.
2. Sélectionnez le réseau publicitaire.
3. Sélectionnez **Activer** **les paramètres de retargeting**. Cette opération transforme le lien d'attribution en URL de retargeting en ajoutant `is_retargeting=true` au lien.  

   [![](https://files.readme.io/68b8939885439a4f0e6d1ec6601552185905d1afc817da9fb88ccfe043a83364-33563511582609.png)](https://files.readme.io/68b8939885439a4f0e6d1ec6601552185905d1afc817da9fb88ccfe043a83364-33563511582609.png)
4. Sélectionnez l'une des options suivantes :
   * **Utilisez un lien d'attribution standard** pour les liens de plate-forme unique (spécifique à l'app)
   * **Utilisez OneLink**.
     * Si besoin est, entrez une **URL de deep link** , (voir notre guide du <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Deep Link</Anchor>).
5. Copiez l'URL qui a été générée, et transmettez-la au réseau publicitaire afin de l'utiliser pour votre campagne de retargeting.  
   **Remarque**: l'URL ne dure pas dans le temps pas et ne peut pas être enregistrée.

</Accordion>

<div id="retargeting-dashboard" />

<Accordion title="Tableau de bord de retargeting">

Le tableau de bord général contient des mesures de retargeting ainsi que des métriques d'acquisition d'utilisateurs. Les mesures sont basées sur la LTV et concernent les utilisateurs qui s'engagent dans une campagne de retargeting.

**Pour afficher les données de retargeting** :

1. Dans AppsFlyer, allez dans **Tableaux de bord** > **Général.**
2. Cliquez sur **Type d'affichage**, puis sélectionnez **Retargeting**.  
   Les données de retargeting s'affichent.  
   Important ! Vous pouvez également visualiser les données de retargeting dans la vue unifiée. Voir Types de vues du tableau de bord.

</Accordion>

<div id="retargeting-attribution-links" />

<Accordion title="Liens d'attribution de retargeting">

* Les liens de retargeting sont similaires aux liens d'acquisition utilisateur conventionnels.
* Vous pouvez les créer pour :
  * Les non SRN qui prennent en charge le retargeting.
  * Les médias propres, à l'aide de la page de <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">gestion des liens.</Anchor>

Paramètres du lien d'attribution de retargeting

| Paramètre | Descriptions | Obligatoire |
| --- | --- | --- |
| `is_retargeting` | Définir sur : `is_retargeting=true` | Oui |
| ID publicitaire | Dans la mesure du possible, envoyez un ID publicitaire de type IDFA, OAID, IDFV, etc. <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#probabilistic-modeling">Restrictions de modélisation probabiliste pour les apps iOS.</Anchor> | Non |
| Fenêtre rétrospective de clic de retargeting | <ul><li>La <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">fenêtre rétrospective de clic</Anchor> de retargeting fonctionne comme celle des campagnes d'acquisition d'utilisateur.</li><li>Elle définit la durée maximale qui peut s'écouler entre le moment où un utilisateur clique sur une publicité et celui où il est attribué.</li><li>La fenêtre rétrospective est définie avec le paramètre `&af_click_lookback`.</li><li>Le réglage par défaut est de 7 jours.</li></ul>**<span id="01ECF12NKTFH6Q2NH4B1WKSYF9"></span>Exemple**<br />Pour fixer la fenêtre rétrospective post clic à 14 jours, ajoutez le texte suivant au lien d'attribution de la campagne de retargeting : `&af_click_lookback=14d` | Non |
| Délai de la fenêtre rétrospective post vue de retargeting | <ul><li>La <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">fenêtre rétrospective post vue</Anchor> de retargeting fonctionne comme celles des campagnes d'acquisition utilisateur.</li><li>Elle définit la durée maximale qui peut s'écouler entre le moment où un utilisateur consulte une publicité et celui où il est attribué.</li><li>La valeur par défaut est de 1 jour.</li><li>La fenêtre rétrospective est définie avec</li></ul>`af_viewthrough_lookback={time}`<br /><br /><br /><br />**<span id="01ECF12NKTE8W4K72VATN9RM2X"></span>Exemple**<br />Pour fixer la fenêtre rétrospective post vue à 5 heures, ajoutez le code suivant au lien d'attribution de la campagne de retargeting : `&af_viewthrough_lookback=5h` | Non |
| Fenêtre de réengagement | <ul><li>La **fenêtre de réengagement** peut être définie dans l'interface utilisateur du lien d'attribution. Cette action définit le paramètre **af\_reengagement\_window** du lien d'attribution. Le paramètre peut être ajouté manuellement.</li><li>La valeur par défaut est de 30 jours.</li><li>Les valeurs suivantes de la fenêtre de réengagement sont disponibles :</li><li>Heures : 1 à 23 heures</li><li>Jours : 1-90 jours</li><li>Valeur vie : dure jusqu'à ce que l'utilisateur désinstalle l'app ou procède à un autre réengagement, par exemple : af\_reengagement\_window=lifetime</li></ul>Par exemple, **af\_reengagement\_window=60d** signifie que les événements rapportés dans les 60 jours qui suivent le réengagement seront attribués à la source média de retargeting. | Non |

#### Période rétrospective post vue de retargeting

```http
https://app.appsflyer.com/id123456789?pid=remerge_int&af_dp=mydeeplink%3A%2F%2F&
clickid={clickid}&af_siteid={publisher}&idfa={device_id_raw}&sha1_idfa={device_id}
&af_sub1={creative_name}&is_retargeting=true&af_reengagement_window=60d
```

</Accordion>

<div id="retargeting-reports-and-raw-data" />

<Accordion title="Rapports de retargeting et données brutes">

* Les rapports de retargeting, tout comme les rapports <Anchor target="_blank" href="/marketers/fr/docs/aggregated-and-analytics-reporting-overview">agrégés</Anchor> et de <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">données brutes</Anchor> d'AU, sont proposés par les outils de reporting.
* Le retargeting des événements et sessions in-app est <Anchor target="_blank" href="/marketers/fr/docs/resolve-retargeting-double-attribution">doublement attribué.</Anchor>

**Rapport des conversions de retargeting**

* Le rapport de Conversions de retargeting contient les données brutes des réengagements et des réattributions.
* Certains champs du retargeting n'ont pas la même signification quand ils apparaissent dans un rapport d'acquisition utilisateur.

Interpréter les rapports de données brutes dans le contexte du retargeting

| Colonne | **Description** |
| --- | --- |
| Nom de l'événement | <ul><li>Le champ est rempli en fonction du type de rapport.</li><li>Rapports d'événements in-app : le nom de l'événement in-app.</li><li>Rapports de conversion de retargeting : réengagement ou réattribution. **Attention** ! En ce qui concerne Data Locker, les valeurs sont les suivantes :<ul><li>installation signifie réattribution</li><li>retargeting signifie réengagement</li></ul></li></ul> |
| Type de touche d'attribution | Types d'engagement :<ul><li>Clic</li><li>Impression</li></ul> |
| Temps de touch attribué | Moment d'engagement du retargeting |
| Heure d'installation | Le premier lancement de l'app après le réengagement ou la réattribution. |
| Heure de l'évènement | L'heure à laquelle l'événement s'est produit |
| ID AppsFlyer | <ul><li>Réattributions : un nouvel ID AppsFlyer</li><li>Réengagement : reste inchangé</li></ul> |
| Est retargeting | TRUE pour les conversions et événements de retargeting |
| Est une attribution principale | TRUE pour les conversions et événements de retargeting |
| Type de conversion de retargeting | Ce champ sera prochainement obsolète (date à venir). Utilisez conversion\_type et campaign\_type pour déterminer le contexte de la conversion.<ul><li>RÉENGAGEMENT</li><li>Réattribution</li></ul> |
| Types de conversion | Le type de conversion :<ul><li>sans rapport</li><li>Réinstallation (1)</li><li>RÉENGAGEMENT</li><li>Inconnu (2)</li></ul>(1) Si conversion\_type= reinstall et campaign\_type=retargeting est équivalent à retargeting\_conversion\_type=re-attribution<br /><br />(2) Événements in-app/sessions non attribués à une source média. |
| Type de campagne | La source qui draine l'utilisateur :<ul><li>UA</li><li>Organique</li><li>Re-Targeting</li><li>Inconnu</li></ul> |
| Attribution rétrospective | Fenêtre rétrospective post clic de retargeting |
| URL d'origine | Comprend l'un des éléments suivants :<ul><li>Lien de retargeting</li><li>Données de deep linking</li><li>Vide pour les SRN</li></ul> |
| Champs contributeur | Non disponible pour les réengagements |

</Accordion>

## Informations supplémentaires

<div id="probabilistic-modeling" />

<Accordion title="Modélisation probabiliste">

Depuis le 17 février 2021, la modélisation probabiliste est compatible avec le retargeting. Des limitations s'appliquent avec <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#remarque-concernant-les-apps-ios-">iOS 14.5+</Anchor>. La fenêtre rétrospective utilisée dans la modélisation probabiliste de retargeting est définie dynamiquement par AppsFlyer, elle dépend du système d'exploitation.

Vérifier que les clics envoyés incluent les <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#paramètres-de-modélisation-probabiliste-pour-les-réseaux-publicitaires">paramètres de modélisation probabiliste</Anchor> nécessaires.

</Accordion>

<div id="app-requirements" />

<Accordion title="Conditions d'utilisation de l'app">

Pour exécuter une campagne de retargeting, l'application doit répondre aux critères minimum suivants.

* iOS
  * Outre l'intégration standard du SDK AppsFlyer, vous devez ajouter un code au délégué d'app, consultez l'article <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#lien-profond-avec-onelink">Integration du SDK</Anchor> (section liens d'attribution).
  * Sous iOS 9, le code Universal Link App Open doit être implémenté. <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">Liens universels avec iOS 9</Anchor>.
* Android :

  * Si le deep link ouvre une activité différente de l'activité principale, consultez l'article <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#deep-linking">Integration du SDK</Anchor> (section liens d'attribution).

</Accordion>

<div id="retargeting-limitations" />

<Accordion title="Limitations du retargeting">

* Depuis le 17 février 2021, le retargeting est compatible avec la modélisation probabiliste.
* Les données sur le coût des campagnes de retargeting sont disponibles dans les tableaux de bord et les rapports de vue d'ensemble et de cohorte dans la vue unifiée.

</Accordion>

<div id="faq" />

<Accordion title="FAQ">

| **Clics de retargeting :**<ul><li>Les clics de retargeting incluent les utilisateurs reciblés qui s'engagent avec un lien d'attribution AppsFlyer.</li><li>Les clics provenant des SRN ou des <Anchor target="_blank" href="/marketers/fr/docs/measuring-push-notification-re-engagement-campaigns">notifications push</Anchor> ne sont pas compris dans le décompte.</li><li>Certains clics génèrent de nouvelles installations qui sont attribuées en tant qu'acquisition d'utilisateur. Cette situation survient lorsque des non-utilisateurs (ou des utilisateurs passés dont la <Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window">fenêtre de réattribution</Anchor> a expiré) s'engagent avec un lien de retargeting et une installation.</li></ul> |
| --- |
| **Dans quels cas l'heure de touch attribué est-elle identique à l'heure d'installation ?**<ul><li>Lorsque les utilisateurs de liens universels ou de liens d'apps Android emploient le deep linking, ils sont redirigés vers l'app sans transiter d'abord par AppsFlyer.</li><li>Lors du lancement d'une app lorsque le SDK signale un nouveau réengagement, AppsFlyer reproduit les données du clic en employant l'horodatage du lancement. L'heure d'engagement et l'heure de lancement sont ainsi identiques.</li></ul> |

</Accordion>

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model">Modèle d'attribution AppsFlyer</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/audiences-guide">Guide des audiences</Anchor>

<div data-zendesk-anchors="retargeting-fundamentals=les-bases-du-retargeting h_01HCFJHC85VK0A05X5F69E2WKT=les-bases-du-retargeting h_01HCFJHC851PV0VR42H07VQAXF=astuce h_01HCFJHC85EW8MBQ8MBXBVPF03=reengagement-rules-and-windows inclusion-windows=fen%C3%AAtres-dinclusion h_01HCFJHC85FRFJ531Y08DW03Y2=fen%C3%AAtres-dinclusion exclusion-windows=fen%C3%AAtres-dexclusion h_01HCFJHC85ECS3PJV80D943TVY=fen%C3%AAtres-dexclusion example-flow-implementing-the-rules=exemple-dimpl%C3%A9mentation-des-r%C3%A8gles h_01HCFJHC8529NW0ABMQ0RB3E8R=exemple-dimpl%C3%A9mentation-des-r%C3%A8gles h_01HCFJHC85E1SWGYN0BH603BV9=example-retargeting-scenarios retargeting-operations=op%C3%A9rations-de-retargeting h_01HCFJHC863XPHNWRHJ60JPSRF=op%C3%A9rations-de-retargeting h_01HCFJHC86XNCT5AQP48R9ZDC4=retargeting-settings nonsrn-settings=param%C3%A8tres-non-srn h_01HCFJHC865V36R3H58D5PWXYY=param%C3%A8tres-non-srn h_01HCFJHC860BS9YJM99G437G24=retargeting-dashboard h_01HCFJHC860Y5HZN66DRNN2Q89=retargeting-attribution-links retargeting-viewthrough-lookback-period=p%C3%A9riode-r%C3%A9trospective-post-vue-de-retargeting h_01HCFJHC863CSP03AYBXFSNC37=p%C3%A9riode-r%C3%A9trospective-post-vue-de-retargeting h_01HCFJHC86MNFRGYMN776FYHJV=retargeting-reports-and-raw-data additional-information=informations-suppl%C3%A9mentaires h_01HCFJHC86RKKPPMBYEZV4Q3X9=informations-suppl%C3%A9mentaires h_01HCFJHC8690EN19DDX7P24AD0=probabilistic-modeling h_01HCFJHC862E6C46Q7645VJ6CZ=app-requirements h_01HCFJHC86SMKZ1HT5KHQNQS1N=retargeting-limitations h_01HCFJHC86BVSVRNAGJEKZFCJP=faq h_01HE7TPR7928SF2W8ZJS55Y5BG=%C3%A0-consulter-%C3%A9galement" />
