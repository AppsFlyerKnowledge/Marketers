---
title: Guide de l'Optimisation créative
metadata:
  keywords:
    - Premium
    - Marketers
    - Design team
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2023-09-14T13:32:13Z'
  edited_at: '2023-11-27T14:03:14Z'
  id: 18564718580625
  locale: fr
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/fr/articles/18564718580625
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** l'optimisation créative vous permet de rassembler toutes les données relatives aux ressources créatives de toutes vos campagnes sur une seule plateforme. Cela vous permet d'analyser leurs performances, de découvrir quelles sont les créations qui fonctionnent le mieux et de prendre de bonnes décisions basées sur les données.

[![Main KB image 2023-11-14_10-07-47.jpg](https://files.readme.io/931a64db9b96154f101f6425fad1dfd9559aab2855b6ca6c4b82f250b283e87b-20126060107793.jpg)](https://files.readme.io/931a64db9b96154f101f6425fad1dfd9559aab2855b6ca6c4b82f250b283e87b-20126060107793.jpg)

<div id="about-creative-optimization" />

## À propos de l'optimisation des créations

**L'optimisation des créations** est votre guichet unique pour mesurer la performance des créations utilisées dans toutes vos campagnes. Elle vous permet de rassembler sans effort toutes vos ressources créatives issues de tous les canaux média sur une même plateforme, ou dans votre système de veille stratégique, pour analyser leurs performances en fonction des dimensions, sur plusieurs campagnes, canaux, etc. L'optimisation des créations vous permet de découper les créations en fonction de différents paramètres et KPI, afin d'obtenir des informations essentielles avant de planifier, sélectionner et produire votre prochaine série de créations.

Les tableaux de bord d'optimisation créative vous permettent de mesurer les performances des vidéos, des images, du HTML et du texte, et de voir comment ces éléments se comportent dans le temps et sur les différents canaux. Chaque création est analysée, agrégée et matchée à l'aide de puissants algorithmes d'IA. Cela signifie que les mêmes créations utilisées pour différentes campagnes et sources média sont identifiées et affichées comme une seule création dans le tableau de bord, indépendamment de leur nomenclature, ID publicitaire ou autre métadonnée.

Le <Anchor target="_blank" href="/marketers/fr/docs/creative-optimization-overview-dashboard">Tableau de bord général</Anchor> vous permet de voir vos données présentées dans des graphiques et un tableau détaillé. Vous disposez ainsi de toutes les informations pour optimiser et garder les meilleures créations pour vos campagnes.

Avec le <Anchor target="_blank" href="/marketers/fr/docs/creative-optimization-discovery-ai-dashboard">tableau de bord Découverte IA</Anchor>, produisez des créatiosn performantes en vous basant sur les données. Gardez une vue d'ensemble sur toutes vos créations, ou suivez de près les performances des scènes ou éléments individuels pour obtenir un maximum d'informations.

<Anchor target="_blank" href="/marketers/fr/docs/creative-optimization-etl-reporting">L'ETL (Extract Transform Load) de l'optimisation des créations</Anchor> fournit à vos analystes de données toutes les informations nécessaires à l'analyse des performances créatives en envoyant automatiquement les rapports sur un stockage cloud pour un chargement efficace et programmatique dans vos systèmes BI.

L'optimisation créative offre les possibilités suivantes :

* Savoir de suite quelles créations, scènes ou éléments fonctionnent ou pas
* Optimiser vos créations en fonction des données
* Augmenter les performances et le ROI de vos créations
* Produire de meilleures créations
* Suivre la baisse d'efficacité des créations au fil du temps, des canaux ou campagnes, et agir en conséquences.
* Liste non exhaustive

## Démarrer

Une fois que vous êtes abonné et que votre compte a été configuré, le tableau de bord **Optimisation créative** apparaîtra sous la rubrique **Tableaux de bord de** la plateforme AppsFlyer.

|  | Étapes |
| --- | --- |
| 1 | Cliquez sur **Optimisation des créations** (dans le menu principal de gauche, dans Tableaux de bord). |
| 2 | Configurez les <Anchor target="_blank" href="/marketers/fr/docs/creative-optimization-partner-integrations">intégrations de partenaires</Anchor>.<br /><br />**Remarque :** les données seront disponibles dans Optimisation des créations environ 24 heures après l'intégration. |
| 3 | Configurez les principaux [filtres du tableau de bord](/docs/creative-optimization-guide#filtrage-et-mesures). |
| OPTIONNEL | Configuration :<ul><li>[Balises personnalisées](/docs/creative-optimization-guide#balises-personnalisées)</li><li>[Mesures personnalisées](/docs/creative-optimization-guide#custom-metrics)</li><li>[Vues personnalisées du tableau de bord](/docs/creative-optimization-guide#save-and-share-views)</li></ul> |
| 4 | Parcourez vos tableaux de bord :<br /><br /><Anchor target="_blank" href="/marketers/fr/docs/creative-optimization-overview-dashboard">Tableau de bord général</Anchor> - Permet d'analyser les performances créatives et de maximiser l'impact de vos campagnes.<br /><br /><Anchor target="_blank" href="/marketers/fr/docs/creative-optimization-discovery-ai-dashboard">Tableau de bord Découvertes</Anchor> - Permet de produire non stop des créations efficaces. |
| 5 | Analysez les données de performance des créations et optimisez vos créations et/ou campagnes en fonction des résultats. |

<div id="notes" />

<div id="creative-assets" />

## Ressources de créations

Cette section fournit des informations sur les ressources de créations que nous mesurons.

<div id="supported-asset-types" />

<Accordion title="Types de ressources prises en charge">

Les types d'actifs pris en charge par le tableau de bord Optimisation créative sont les suivants :

* Vidéos
* Images
* HTML (Playable inclus)
* Texte

Les actifs qui peuvent être prévisualisés dans le tableau de bord sont les images, les vidéos et le texte.

</Accordion>

<div id="matching-creatives" />

<Accordion title="Créations jumelées">

L'optimisation créative a la capacité unique d'identifier les ressources identiques, sur plusieurs canaux et campagnes, indépendamment des nomenclatures ou identifiants. Pour ce faire, des algorithmes d'intelligence artificielle et de vision par ordinateur font correspondre des propriétés telles que le contexte visuel, le son et les pixels. En outre :

* Les créations jumelées doivent avoir le même rapport hauteur/largeur (portrait, paysage ou carré).
* Les vidéos de durées différentes sont considérées comme des créations distinctes.

</Accordion>

<div id="measuring-creatives-with-multiple-assets" />

<Accordion title="Mesurer les créations à ressources multiples">

**Comment l'optimisation créative mesure-t-elle une création publicitaire comportant plusieurs éléments ?**

Meta Advantage+ (créations dynamiques) et Google Universal App Campaigns (UAC) peuvent inclure des créations publicitaires à ressources multiples.Cependant, AppsFlyer ne ventile pas les données par ressources.Meta ads fournit des données jusqu'au **niveau publicitaire** et Google fournit des données de **niveau groupe publicitaire** maximum.Pour ces types de créations publicitaires, AppsFlyer utilise la modélisation des données pour répartir les données de performance entre les ressources.

<div id="example" />

> 📄 **Exemple**
>
> Prenons une création publicitaire sur Facebook qui a plusieurs ressources. Facebook lui attribue 100 installations au total, réparties entre les ressources comme suit : la **ressource A** a 60 installations et la **ressource B** 40 installations, selon les mesures de Facebook. Dans AppsFlyer, disons que la publicité est attribuée à 50 installations (en raison des différences d'attribution qui existent entre AppsFlyer et les SRN). Pour permettre une analyse au niveau de la ressource, AppsFlyer distribue les données de performance (impressions, clics, installations et coûts) en fonction de taux des mesures de la ressource par rapport au total, comme indiqué ci-dessous.
>
> Ainsi, **pour la ressource A, il y a**
> 60 installations divisées par 60+40 (nombre total d'installations attribuées par Facebook) = 0,6
> Ensuite, nous multiplions 0,6 par 50 (nombre d'installations attribuées par AppsFlyer) = 30 installations.
>
> **Pour la ressource B, il y a :**
> 40 installations divisées par 60+40 (nombre total d'installations attribuées par Facebook) = 0,4
> Ensuite, nous multiplions 0,4 par 50 (nombre d'installations attribuées par AppsFlyer) = 20 installations.
>
> Ainsi, la création publicitaire est attribuée à un total de 50 installations par AppsFlyer, mais le volume d'installations par ressource est conservé, ce qui signifie que la **ressource A** a généré plus d'installations que la **ressource B**.
> Les mesures en aval de l'entonnoir, telles que le revenu et le ROAS, sont également calculées sur ce rapport.
>
> ![Creative_data_example_en-us.png](https://files.readme.io/ca556904829b809238b8b994fd6d762d6cb58ae993c41dd19a7de978f774e8b9-small-18564727253649.png)

</Accordion>

<div id="creative-optimization-roi360" />

<div id="using-the-dashboard" />

## Filtrage et mesures

Cette section présente les principaux filtres du tableau de bord et les différentes mesures et dimensions disponibles pour obtenir des données de création utiles. 

[![Filter bar and metrics New.jpg](https://files.readme.io/f2fbccaefa76bd5c9543902a2b670ee67c9edd6271fab141083ddd6f331fe138-20126434102801.jpg)](https://files.readme.io/f2fbccaefa76bd5c9543902a2b670ee67c9edd6271fab141083ddd6f331fe138-20126434102801.jpg)

<div id="filter-bar" />

<Accordion title="Barre de filtre">

La première étape de configuration de votre tableau de bord consiste à sélectionner vos options de filtrage. Tous les filtres sont appliqués aux tableaux de bord Général et Découvertes.

[![filter_bar.jpg](https://files.readme.io/99da48c37938e573af66cf1f46ce3273c3ca010e68070cb59b5e12cbad1981e3-18564730224913.jpg)](https://files.readme.io/99da48c37938e573af66cf1f46ce3273c3ca010e68070cb59b5e12cbad1981e3-18564730224913.jpg)

Sélectionnez d'abord votre :

* App
* Période - La création s'affiche dans le tableau de bord lorsqu'il y a des données la concernant pour la période choisie.
* Type de vue

Cliquez sur l'icône + pour ajouter l'un des types de filtrage ci-dessous :

* Dimensions et métriques
* Les filtres numériques (disponibles pour toutes les métriques) avec les options suivantes :
  * Supérieur à - Affiche les créations dont les valeurs sont supérieures ou égales à la valeur choisie.
  * Inférieur à - Affiche les créations dont les valeurs sont inférieures ou égales à la valeur choisie.

Outre les mesures et dimensions standard, le tableau de bord d'optimisation créative propose plusieurs mesures et dimensions uniques.

</Accordion>

<div id="view-type" />

<Accordion title="Type de vue">

Les données sur les créations du tableau de bord sont disponibles dans 3 types de vues : Unifié, Acquisition d'utilisateurs (UA) et Retargeting.

* **Unifié** - Affiche toutes les données de création des publicités/adsets pour l'AU et le retargeting.
* **Acquisition d'utilisateurs** - Affiche les données de création des publicités/adsets pour l'AU uniquement.
* **Retargeting** - Affiche toutes les données de création des publicités/adsets pour le retargeting uniquement.Les données de coûts sont également accessibles.

[![View_types.jpg](https://files.readme.io/e73cc643581e94d6fbc6455e16615eb2e1d8b387cda626d39b17bbe714122611-18564727261585.jpg)](https://files.readme.io/e73cc643581e94d6fbc6455e16615eb2e1d8b387cda626d39b17bbe714122611-18564727261585.jpg)

</Accordion>

<div id="standard-metrics-and-dimensions" />

<Accordion title="Mesures et dimensions standard">

Les mesures/dimensions standard disponibles dans le tableau de bord sont les suivantes :

| Mesure/dimension | Description |
| --- | --- |
| Impressions | Nombre de fois où une publicité a été regardée |
| Clics | Nombre de clics dans une source média, redirigeant l'utilisateur vers l'app store pour installer ou ouvrir l'application. |
| Conversions | <ul><li>Installations - Nombre d'utilisateurs uniques qui ont installé l'application</li><li>Réengagements - Nombre d'utilisateurs uniques qui ont ouvert l'application après interaction avec une campagne de retargeting</li><li>Réattributions - Nombre d'utilisateurs uniques qui ont réinstallé l'application après interaction avec une campagne de retargeting</li></ul> |
| Coût | Coût de la création |
| CTR (taux post clics) | Pourcentage d'utilisateurs qui ont cliqué sur une publicité sur le nombre total de vues. Formule : clics/impressions x 100 |
| CVR (taux de conversion) | Pourcentage d'utilisateurs qui complètent le parcours depuis le clic jusqu'à l'attribution (installations, réengagements et réattributions). Formule : Conversions / Clics X 100 |
| IPM (Installations par mille) | Nombre d'installations par tranche de 1 000 utilisateurs qui ont visionné votre publicité (impressions). Formule : Conversions/impressions X 1000 |
| eCPI (coût effectif par installation) | Coût total disponible / toutes les attributions non organiques.L'eCPI ne prend pas en compte les installations organiques et calcule le coût des attributions non organiques (installations, réengagements et réattributions). |
| CPM (Coût par mille) | Coût de 1000 impressions publicitaires. Formule : Dépenses créatives totales / nombre d'impressions) X 1 000 |
| Plate-forme | Renvoie au système d'exploitation (soit Android) |
| Canal | Segmentation du trafic au sein des sources média  <br />(soit YouTube pour Google, Instagram pour Meta ads, etc.) |
| Géo | Pays/localité |
| ID | <ul><li>Créatif</li><li>Publicité</li><li>Ensemble de publicités</li><li>Campagne</li></ul> |
| agences | Affiche les données de création des agences sélectionnées |
| Mesures de la cohorte | Description |
| Revenu (J1, J3, J7, J14, J30, J60, J90) | Revenu de cohorte transmis à AppsFlyer |
| ROAS (J1, J3, J7, J14, J30, J60, J90) | Retour sur les dépenses publicitaires par cohorte (%). Calcule le revenu généré par unité de dépense publicitaire. Formule : Revenu / Coût x 100 |
| Utilisateurs uniques (J1, J3, J7, J14, J30, J60, J90) | Utilisateurs uniques de la cohorte qui ont interagi avec votre app jusqu'au jour (inclus) spécifié dans l'installation |
| Rétention (J1, J3, J7, J14, J30, J60, J90) | Pourcentage d'utilisateurs de la cohorte qui continuent à utiliser votre service ou votre produit sur une période prédéterminée<br /><br />**Remarque :** les données sont les mêmes que celles du tableau de bord de cohorte AppsFlyer. |

</Accordion>

<div id="unique-metrics-and-dimensions" />

<Accordion title="Mesures et dimensions uniques">

Les mesures/dimensions uniques disponibles dans le tableau de bord sont les suivantes :

| Mesure/dimension | Description |
| --- | --- |
| Nombre de publicités | Affiche le nombre de campagnes/adsets/publicités où une création spécifique est affichée sur les différents canaux. |
| [Mesures des partenaires](/docs/creative-optimization-guide#partner-metrics::e592ecd3) | Données provenant directement des partenaires intégrés (et non des données d'attribution AppsFlyer). |
| Similarité de la création | Regroupe les créations quasi identiques (à quelques différences près) et vous permet de comparer leurs performances pour savoir quelle version est la plus performante. Exemple : les mêmes images avec des orientations différentes (portrait ou paysage) seront regroupées, de même que des vidéos avec le même contenu mais dans des langues différentes. Cette dimension ne s'applique qu'aux images et vidéos. |
| Âge de la création | Affiche le nombre de jours où une création a été diffusée dans le cadre d'une campagne. L'ancienneté est calculée à compter de la première impression, du premier clic ou de la première installation transmise à AppsFlyer et peut varier en fonction des dimensions .Cela signifie que si une création a été importée dans une campagne un jour, puis dans une campagne différente un autre jour, et que les dimensions « campagne » et « ancienneté » sont ajoutées au filtre, alors l'ancienneté est calculée depuis la première importation.<br /><br />**Remarque :** pour les créations de campagne qui sont diffusées avant d'avoir été ingérées dans le tableau de bord des créations, AppsFlyer affiche les données jusqu'à 90 jours avant l'ingestion. Par exemple, si une création a été diffusée pendant plus de 90 jours avant d'être ingérée, l'ancienneté de la création commence à 90, puis continue à augmenter de là chaque jour. |
| Création vue pour la première fois (tableau uniquement) | Mesure la performance de la création au moment où nous obtenons pour la première fois des données sur ces ressources.Le calcul de l'ancienneté démarre à partir de cet instant.Cette dimension n'est disponible que dans le tableau (dans les paramètres ainsi que dans la liste déroulante *Regrouper par*). |
| Durée | Durée en secondes d'une ressource créative (applicable aux vidéos) |
| Résolution | Taille en pixels d'une ressource créative (applicable aux images et vidéos)<br /><br />**Remarque :** nous affichons la résolution fournie aux utilisateurs par vos partenaires médias intégrés. Il peut s'agir d'une résolution différente de celle importée à l'origine. |
| Orientation | Orientation d'une ressource créative (portrait, carré ou paysage) |
| Mois | Ventilation des performances par mois |
| Semaine | Ventilation des performances par semaine |
| Encart de fin | Les publicités statiques qui peuvent s'afficher à la fin des vidéos publicitaires et qui contiennent généralement des infos de base sur l'application concernée. La possibilité de regrouper les créations par encart de fin donne plus d'indices pour optimiser les créations, par exemple en comparant un même encart de fin sur différentes vidéos pour voir la meilleure combinaison. Vous pouvez visualiser les créations en fonction des données sur l'encart de fin suivantes :<ul><li>Encart de fin</li><li>Durée de l'encart de fin</li><li>Résolution de l'encart de fin</li><li>Orientation de l'encart de fin</li><li>Type d'encart de fin</li></ul> |

</Accordion>

<div id="custom-metrics" />

<Accordion title="Mesures personnalisées">

Créez des mesures personnalisés afin de suivre la performance de vos créations exactement comme vous le souhaitez.

<Embed title="Guide de l'Optimisation créative" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/p4unlaykr8" providerUrl="https://fast.wistia.com" />

**Pour créer une mesure personnalisée :**

1. Cliquez sur le menu déroulant en haut à droite du tableau de bord, puis sélectionnez **Mesures personnalisées**.

![Custom_metric_select.jpg](https://files.readme.io/99ca0ee30d09e42ef2798188e8d95fc4cf56ee31ad055209efadc47c9df8a859-18564742772625.jpg)

2. **Remplissez le formulaire :**

* **Nom** - Saisissez un nom de mesure unique
* **Type** - Sélectionnez Nombre, Pourcentage ou Devise.
* **Description** - Saisissez une description (facultatif)
* **Formule de la mesure** - Créez une formule en cliquant sur **+ Ajouter une formule**.   
  * Les *mesures* incluent les impressions, les clics, les installations, le CTR, le CVR, le CPM, l'IPM, le coût, l'eCPI, les réattributions, les réengagements, les revenus, le ROAS, la rétention, les utilisateurs uniques, le nombre de publicités et les mesures du partenaire
  * Combinaison avec divers *opérateurs, numéros* et/ou *événements in-app.*
  * Des événements in-app spécifiques sont sélectionnés dans le menu déroulant. Pour chaque événement in-app, vous pouvez ajouter séparément n'importe quelle mesure pour l'événement afin d'obtenir des informations très spécifiques, par exemple, af\_purchase revenue + af\_login count.

<Image alt="Custom_metrics_form.jpg" src="https://files.readme.io/2fdbcd2e8fcc17b6a47fd3ae252d03b1eec5099400ed46855b3b4ae83a4c8e00-18564718424209.jpg" width="625px" />

3. Cliquez sur **Enregistrer**

Votre nouvelle mesure personnalisée est créée et s'affiche dans la barre de filtre et dans les paramètres du tableau avec la mention «*Personnalisée*».

**Remarque :**

* Vous pouvez créer jusqu'à 10 mesures personnalisées par compte.
* Vous pouvez survoler la balise «Personnalisée» dans les paramètres du tableau pour voir sa description.

Les mesures personnalisées peuvent être facilement modifiées ou supprimées.

**Pour les modifier :**

1. Cliquez sur le menu déroulant **Modifier une mesure personnalisée existante** (dans le formulaire **Mesures personnalisées** ) puis sélectionnez la mesure à modifier.

<Image alt="Edit_cstom_metric_full_window.jpg" src="https://files.readme.io/26a33b98ded52599d420be3860c6129b7c748ef0867bcffc351ad1c526641c97-18564744997905.jpg" width="623px" />

2. Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**

**Remarque :** vous pouvez également cliquer sur **Enregistrer sous** pour enregistrer comme nouvelle mesure personnalisée.

**Pour supprimer :** après avoir sélectionné dans la liste déroulante la mesure personnalisée à supprimer, cliquez sur l'icône de suppression.

<Image alt="Delete_custom_metric.jpg" src="https://files.readme.io/185b9c3f071518ff2da549b6c34c4ddfecf12bc442b2f7990eb11f04fae10925-18564742779921.jpg" width="514px" />

</Accordion>

<div id="partner-dimensions-and-metrics" />

<div id="partner-metrics::e592ecd3" />

<Accordion title="Mesures des partenaires">

Les mesures des partenaires sont des données qui proviennent directement des partenaires médias intégrés (et non des données d'attribution AppsFlyer). Les mesures varient selon le partenaire et peuvent inclure les impressions, les clics, le coût, les installations, l'IPM, le CVR, le CTR, l'eCPI, le CPM, etc (cf le tableau ci-dessous pour les éléments propres aux partenaires). Les mesures peuvent être sélectionnées dans les filtres, elles sont consultables dans le tableau de bord.

<div id="to-set-up-partner-metrics" />

#### Table des partenaires

| Réseau publicitaire | Source média (pid) | Campagne | Ensemble de publicités | Publicité | Géo | Canal | Commentaires et conditions particulières | Clics rapportés | Impressions rapportées | Conversions rapportées | Coût rapporté | Méthode de connexion |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Adikteev | trademob\_int | Oui | Non | Oui | Oui | Non |  | Oui | Oui | Oui | Oui | Paramètres statiques |
| AppLovin | applovin\_int | Oui | Non | Non | Oui | Non | Cf mesures AppLovin | Oui | Oui | Oui | Oui | OAuth + Paramètres statiques |
| Google Ads | googleadwords\_int | Oui | Oui | Non | Oui | Non | Cf mesures Google Ads | Oui | Oui | Oui | Oui | OAuth |
| IronSource | ironsource\_int | Oui | Non | Oui | Oui | Oui |  | Oui | Oui | Oui | Oui | OAuth |
| Liftoff | liftoff\_int | Oui | Non | Oui | Oui | Non | Les données sont disponibles 2 jours en arrière | Oui | Oui | Oui | Oui | Paramètres statiques |
| Meta Ads | facebook | Oui | Oui | Oui | Oui | Non | Cf Meta Ads | Oui | Oui | Oui | Oui | OAuth |
| Moloco | moloco\_int | Oui | Oui | Oui | Oui | Oui |  | Oui | Oui | Oui | Oui | Paramètres statiques |
| TikTok | bytedanceglobal\_int | Oui | Oui | Oui | Oui | Non |  | Oui | Oui | Oui | Oui | OAuth + Paramètres statiques |
| Unity Ads | unityads\_int | Oui | Non | Oui | Oui | Oui | Les données sont disponibles 2 jours en arrière | Oui | Oui | Oui | Oui | Paramètres statiques |
| YouAppi | youappi\_int | Oui | Non | Non | Oui | Non |  | Oui | Oui | Oui | Oui | Paramètres statiques |

Les mesures des partenaires sont actuellement disponibles pour ces partenaires :

* Adikteev
* AppLovin
* Google Ads
* IronSource
* Liftoff
* Meta Ads
* Moloco
* TikTok
* Unity Ads (cf instructions particulières ci-dessous)
* YouAppi

**Pour mettre en place des mesures de partenaires :**

Il suffit d'ajouter une nouvelle intégration de partenaire pour que les mesures des partenaires pris en charge soient automatiquement transférées dans Creative (Unity Ads est une exception et fait l'objet d'instructions particulières).Une fois paramétrées, ces mesures s'affichent avec la mention «*Partenaire*»

![partner metrics image.jpg](https://files.readme.io/074948fd8e4707c1353b6f8ce387e76e04801eeef397e94a604619bc8a0ad420-18564730240145.jpg)

**Instructions et remarques particulières :**

<div id="applovin-metrics" />

<Accordion title="Mesures AppLovin">

**Veuillez noter que :**

* En raison d'une restriction de l'API AppLovin, les données historiques ne sont disponibles que pendant 45 jours maximum.AppsFlyer peut généralement afficher les données historiques jusqu'à 90 jours, mais en raison de la restriction imposée par AppLovin, seuls 45 jours de données sont disponibles.
* Les données créatives AppsFlyer s'appuient sur le rapport probabiliste AppLovin (et non sur le rapport facturable).

</Accordion>

<div id="google-ads-metrics" />

<Accordion title="Mesures Google Ads">

**Veuillez noter que :**

* Il y a des différences entre le nombre d'installations rapportées par Google Ads et AppsFlyer en raison d'un système d'attribution différent.
* Il y a des différences entre Google et AppsFlyer pour toutes les mesures. Cela est dû aux mesures des partenaires de Google qui se basent sur le rapport des ressources de Google, tandis que les données AppsFlyer se basent sur celui des groupes publicitaires de Google. Ces rapports ne donnent pas les mêmes résultats de performance. Exemple : le nombre total d'impressions de ressources pour un groupe publicitaire donné ne sera pas égal au nombre total d'impressions rapporté par le groupe publicitaire.
* Il existe des différences entre le produit Creative et la plateforme Google AdWords. Lorsque l'on compare les chiffres des ressources entre la plateforme Google et AppsFlyer, il peut y avoir de petites différences en raison de : 1. Les fuseaux horaires (Creative est UTC+0). 2. Le taux d'actualisation des données (la différence entre le moment où se produit un événement et la disponibilité de ses données sur la plateforme).

</Accordion>

<div id="meta-ads" />

<Accordion title="Meta Ads">

**Veuillez noter que :**

* Il y a des différences dans le nombre d'installations rapportées par Meta Ads et AppsFlyer en raison d'un système d'attribution différent.
* Meta ne rapporte pas les installations au niveau de la ressource pour iOS, ces données ne sont donc pas disponibles dans Creative.

</Accordion>

<div id="unity-ads-metrics" />

<Accordion title="Mesures Unity Ads">

**Pour obtenir des données de partenaires depuis Unity Ads :**

1. Dans le tableau de bord de Optimisation créative, cliquez sur l'icône  ⋮  en haut à droite pour accéder aux **intégrations créatives**.

![3 dots icon.jpg](https://files.readme.io/ed1f8ac5cee987a10a81b70c97e88a04897a6102c61ee4a0c87fde0a658354e0-18564744949393.jpg)

2. Cliquez sur **+Nouvelle intégration**.

3. Sélectionnez **Unity Ads** dans la liste déroulante des **partenaires**.

<Image alt="New integration - Unity Ads.jpg" src="https://files.readme.io/8a03c4b50287768cd95217af142ec551c8526b2cf5f7f7af06c04704a868093d-18564745005073.jpg" width="493px" />

4. Saisissez l'**ID de clé** Unity, la **clé secrète** et l'**ID principal de l'organisation** pour l'intégration (cf instructions concernant <Anchor target="_blank" href="/marketers/fr/docs/creative-optimization-partner-integrations#unity-ads">l'intégration Unity</Anchor> pour savoir comment obtenir ces clés).

5. Dans la section **métriques du partenaire**, entrez la **clé d'API** Unity et l'**ID de l'organisation**. Vous pouvez obtenir ces éléments en suivant les instructions ci-dessous.

**Remarque :** Si vous avez une intégration ROI360 Cost avec Unity Ads, vous pouvez également vous y rendre pour obtenir les ID.

**Pour obtenir la clé d'API :**

a. Connectez-vous à votre plateforme Unity Gaming Services.

b. Cliquez sur **Produits** dans le menu latéral.

c. Cliquez ensuite sur **Développer**.

<Image alt="Unity Org ID step 1.jpg" src="https://files.readme.io/79d445c8588ef6fa7b34ad8983d068b80a7ab733e7dd9906ad079fa647b3e10b-20348482802833.jpg" width="567px" />

d. Cliquez sur **Acquisition utilisateurs Unity Ads**.

<Image alt="Unity Org ID step 2.jpg" src="https://files.readme.io/1e0efbece8777100ac7046f09c52887f52bc5fba2e28c724298340afe78ba8f4-20348466710545.jpg" width="312px" />

e. Cliquez sur **Gestion de l'API**.

![Unity-from API mngmt, get API key w arrow.jpg](https://files.readme.io/c617593d5935fbe8072d9fac0146fb3257c395c8dcf173130b97cc2a4a043285-20348783332881.jpg)

f. Copiez la clé API.

**Pour obtenir l'ID de l'organisation :**

1. Dans Unity Ads, cliquez sur **Produits** dans le menu latéral.

2. Cliquez ensuite sur **Développer**.

<Image alt="Unity Org ID step 1.jpg" src="https://files.readme.io/79d445c8588ef6fa7b34ad8983d068b80a7ab733e7dd9906ad079fa647b3e10b-20348482802833.jpg" width="583px" />

3. Cliquez sur **Acquisition utilisateurs Unity Ads**.

<Image alt="Unity Org ID step 2.jpg" src="https://files.readme.io/1e0efbece8777100ac7046f09c52887f52bc5fba2e28c724298340afe78ba8f4-20348466710545.jpg" width="336px" />

4. Cliquez sur **Paramètres**.

![Get Organization ID instructions 2 arrows.jpg](https://files.readme.io/7514d25a8c9a7a9f64e7e5b6f9008c649cb949eff7d25c49a1693f806518e07d-20348948474897.jpg)

5. Copiez l'**ID de l'organisation**.

<div id="share-view-url" />

<div id="save-shared-dashboard-view" />

<div id="save-private-dashboard-view" />

<div id="note" />

> 📘 **Remarque**
>
> Nous vous recommandons de saisir les références des mesures du partenaire lors de l'installation d'une nouvelle intégration de partenaire. Mais ce n'est pas ne obligation. Vous pouvez enregistrer l'intégration et ajouter les informations d'identification plus tard.Notez cependant que nous extrayons les données des partenaires sur 90 jours à compter du moment où l'intégration des partenaires est créée, si les informations d'identification de mesure du partenaire ne sont pas renseignées tout de suite, cela entraine donc l'absence de données.

</Accordion>

</Accordion>

<div id="save-and-share-views" />

<Accordion title="Enregistrer et partager les vues">

Après avoir sélectionné vos filtres, vous pouvez enregistrer vos configurations de filtres pour accéder rapidement aux informations, vous n'aurez pas à sélectionner les filtres à chaque fois que vous vous connecterez.De plus, vous pouvez partager l'URL de la vue avec votre équipe.

**Pour enregistrer une vue (configuration du filtre) :**

Cliquez sur l'icône *liste déroulante* à côté du titre **Aperçu des créations** en haut à gauche > cliquez sur **+ Enregistrer en tant que nouveau** > Saisissez un nom de rapport et cliquez sur **Enregistrer**.

**<Image alt="Save_new_view_report_with_mouse_icon.jpg" src="https://files.readme.io/1f0c445ba77a03868e44dfb9045ad760390a6a54a86007747efb3e56466ed6af-18564727344017.jpg" width="445px" />**

Vous pouvez créer plusieurs vues, les modifier et les supprimer en cliquant sur les icônes correspondantes. Vous pouvez également marquer une vue par défaut, c'est elle qui s'affichera après connexion.

**Pour partager l'URL de la vue (avec un utilisateur enregistré) :**

Cliquez sur l'icône en haut à droite du tableau de bord pour copier l'URL de la page, puis transmettez-la.

<Image alt="Copy_page_URL_with_cursor.jpg" src="https://files.readme.io/2d1cc2f9585850c1d9c723f959be96e953fe6cc90b6b2a31ac8c16bf4e7b4b8f-18564702245777.jpg" width="121px" />

</Accordion>

<div id="h_01HA282W8WHHNDG75XZNSV2QQF" />

<div id="additional-information" />

<div id="custom-tags" />

## Balises personnalisées

Regroupez et analysez vos créations selon les balises que vous importez, ou selon les identifiants uniques inclus dans les noms de fichiers. Cette section décrit les différentes manières de créer des balises personnalisées, celles-ci s'affichent comme des dimensions, vous pouvez les sélectionner dans les filtres et les vues des tableaux de bord.

<div id="custom-dimensions" />

<Accordion title="Balises personnalisées via CSV">

Vous pouvez ajouter des dimensions personnalisées au tableau de bord. Ces dimensions personnalisées, ainsi que les créations balisées associées sont transmises via un fichier CSV et s'alignent sur les créations en cours utilisées dans les différentes campagnes. Cette fonction permet d'afficher, organiser, trier et filtrer les créations en fonction des dimensions et balises personnalisées de votre choix.

<div id="create-and-manage-custom-dimensions" />

<Accordion title="Créer et gérer des dimensions personnalisées">

Le processus de création et de gestion des dimensions personnalisées inclut ces trois étapes :

1. Téléchargement d'un fichier CSV à partir du tableau de bord Optimisation créative qui contient les créations actuelles.
2. Création de nouvelles dimensions ou modification des dimensions et balises existantes. Chaque en-tête de colonne du fichier CSV correspond au nom de la dimension personnalisée (ex : Couleur). Toutes les créations de cette colonne porteront la balise de la dimension personnalisée et s'afficheront avec la mention de cette balise dans le tableau de bord. Vous pouvez ajouter ou modifier n'importe quelle dimension ou balise personnalisée via le fichier CSV.
3. Importation du fichier CSV mis à jour dans le tableau de bord Optimisation créative. Les données sont disponibles sous 30 minutes.

Les procédures de téléchargement et d'importation du fichier CSV se trouvent ici :

**Pour télécharger un fichier CSV contenant les créations en cours depuis le tableau de bord :**

1. Cliquez sur le menu<Image alt="3_dots_icon.png" src="https://files.readme.io/e958f262f824e2d6d259f123f550697f2916628c71cde515697e51af832d2410-18564718539665.png" width="16px" /> en haut à droite du tableau de bord.  

   ![Main menu highlighted.jpg](https://files.readme.io/9461227252c0e9100b43f2a7fbecbea803effd4f9ab2f5d903810ce682b11240-20126844522641.jpg)
2. Cliquez sur **Télécharger le fichier de balises personnalisées**.
3. Sélectionnez les créations que vous souhaitez inclure dans le fichier (soit toutes les créations, soit uniquement celles actuellement affichées dans le tableau de bord - à l'exclusion des créations filtrées).
4. Cliquez sur **Télécharger**.

Apportez les modifications souhaitées au fichier, puis enregistrez-le et importez-le à nouveau dans le tableau de bord.

**Pour importer le fichier CSV dans le tableau de bord d'Optimisation créative :**

1. Cliquez sur le menu<Image alt="3_dots_icon.png" src="https://files.readme.io/e958f262f824e2d6d259f123f550697f2916628c71cde515697e51af832d2410-18564718539665.png" width="16px" /> en haut à droite du tableau de bord.
2. Cliquez sur **Importer le fichier de balises personnalisées**.
3. Sélectionnez le fichier à importer.  
   Assurez-vous de prendre connaissance de toutes les remarques et restrictions liées à l'importation d'un CSV.
4. Cliquez sur **Importer dans le tableau de bord**.

Les données seront disponibles sous 30 minutes.

</Accordion>

<div id="example-csv" />

<Accordion title="Exemple de CSV">

Voici un exemple de fichier CSV de dimensions personnalisées (que vous téléchargez à partir du tableau de bord). Chaque titre de colonne (ligne 1) est le nom d'une dimension personnalisée (ex : Thème ou Variation). Vous pouvez ajouter de nouvelles dimensions ou modifier les dimensions existantes. Vous pouvez également ajouter ou modifier les balises (ex : 3 Moves ou DarkPalette).

[![Screen_Shot_2022-08-08_at_16.25.23.png](https://files.readme.io/33137d3c8eab51069a3863a2af193d2192cd28546442abcaf8b74073e737c63e-18564702296977.png)](https://files.readme.io/33137d3c8eab51069a3863a2af193d2192cd28546442abcaf8b74073e737c63e-18564702296977.png)

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et restrictions des dimensions personnalisées">

* Les dimensions personnalisées portent la mention *Personnalisée* dans les filtres et le tableau.

<Image alt="Custom_tag.png" src="https://files.readme.io/f8003396943a406dec2b825f4a4725aeb2f0ea3b23f3c67643cc0c096321b401-18564730363025.png" width="477px" />

* Vous pouvez ajouter jusqu'à 15 dimensions personnalisées au tableau de bord d'Optimisation créative.
* La taille du fichier importé est limitée à 1 Mo.
* Les dimensions et noms de balises existants peuvent être modifiés en mettant à jour le fichier CSV et en l'important à nouveau. Notez que vous ne pourrez mettre à jour ou ajouter qu'une seule dimension par importation du fichier.
* Les dimensions personnalisées définies dans le fichier CSV s'appliquent au niveau du compte, c'est-à-dire à l'ensemble des applications et utilisateurs.
* Chaque création peut avoir une balise par dimension. Ainsi, si "Couleur" est la dimension personnalisée, la balise ne peut être que d'une seule couleur, par exemple rouge.
* Lors de la création ou de la modification des dimensions personnalisées, veillez à ne pas modifier le creative\_id afin d'éviter les écrasements et erreurs.

</Accordion>

</Accordion>

<div id="name-convention-tags" />

<Accordion title="Balise de nomenclature">

Vous pouvez créer des balises personnalisées basées sur les nomenclatures de vos ressources créatives. Ces balises personnalisées apparaîtront sous forme de dimensions que vous pourrez choisir comme filtres et afficher dans le tableau de bord.

Cette fonctionnalité est utile pour les équipes marketing et créatifs dont les créations ont des identifiants uniques intégrés aux noms. Ces créations peuvent être automatiquement taguées par les identificateurs intégrés puis regroupées à des fins d'analyse.

<Embed title="Guide de l'Optimisation créative" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/xy631xxspo" providerUrl="https://fast.wistia.com" />

<div id="create-and-manage-name-convention-tags" />

<Accordion title="Créer et modifier les balises de nomenclature">

**Pour créer des balises de nomenclature :**

1. Cliquez sur l'icône  ⋮ en haut à droite du tableau de bord, puis sélectionnez **Balises de nomenclature**.

La fenêtre **Gérer les les balises de nomenclature** s'affiche.

<Image alt="Name convention tags main window.jpg" src="https://files.readme.io/e59721daabccd23ae7735d3e8cca68194983a3c28453daf00bf0ab39ad76fa98-18564727397393.jpg" width="795px" />

2. Dans **Créer un nouveau type de nomenclature,** entrez les informations suivantes :

* **Nom** - Donnez-lui un nom unique.
* **Séparateur** - Le caractère qui sépare chaque section. Exemple, dans une création appelée "enUS\_bluegalaxy\_launch.mp4", chaque section est séparée par "\_". "\_" est le séparateur.
* **Nombre de sections** - Exemple, dans une création appelée "enUS\_bluegalaxy\_launch.mp4", il y a 3 sections séparées par un "\_".  
  **Remarque :** le type de fichier n'est pas inclus dans les balises.
* **App** (facultatif) - Vous pouvez inclure toutes les apps ou limiter les balises aux créations associées à certaines applications.
* **Source média** (facultatif) - Vous pouvez inclure toutes les sources média, ou limiter les balises aux créations diffusées sur certaines sources média.

3. Ajoutez les infos de la balise personnalisée :

* **Numéro de section** - Sélectionnez le numéro de section de la balise que vous souhaitez créer.
* **Nom de la balise personnalisée** - Créez un nom en cliquant sur **+ Créer une nouvelle balise personnalisée**, ou sélectionnez un nom existant.
* **Format** - Sélectionnez comme les balises doivent s'afficher dans le tableau : en majuscules, en minuscules ou comme l'original (telles qu'affichées dans le nom de la création).

Vous pouvez ajouter des balises personnalisées supplémentaires en cliquant sur **+ Ajouter une balise personnalisée**.

4. Avant d'enregistrer, vous pouvez prévisualiser comment vos balises personnalisées s'appliquent à vos créations en cliquant sur **Télécharger le fichier de prévisualisation** (facultatif). Cette opération permet de télécharger un fichier contenant toutes les créations qui répondent au type de nomenclature que vous avez créé, toutes étant taguées avec les nouvelles balises.

5. Cliquez sur **Enregistrer**.

Les balises seront appliquées et disponibles dans le tableau de bord dans les heures suivantes.

**Pour modifier des balises de nomenclature :**

1. Cliquez sur l'icône  ⋮ en haut à droite du tableau de bord, puis sélectionnez **Balises de nomenclature**.

2. Cliquez sur le menu déroulant **Modifier le type de nomenclature** pour faire votre sélection.

3. Apportez les modifications nécessaires et cliquez sur **Enregistrer**.

**Pour supprimer un type de nomenclature :**

1. Cliquez sur le menu déroulant **Modifier le type de nomenclature** pour sélectionnez celui à supprimer.

2. Cliquez sur l'icône  <Image alt="Delete icon.jpg" src="https://files.readme.io/a4bb54fefcdd474edbb897dc334b8219c36273fd5e4f45a03e1b39091856e137-18564742905873.jpg" width="19px" />  qui s'affiche lorsque vous passez la souris à droite de votre sélection.

**Remarque :** Les balises personnalisées associées ne s'appliqueront plus à vos créations. L'application de la modification peut prendre quelques heures.

<div id="name-tag-traits-and-limitations" />

<Accordion title="Caractéristiques et limitations des balises de nomenclature">

* Vous pouvez créer jusqu'à 10 types de nomenclature différents (avec les balises personnalisées associées).
* Si les balises personnalisées qui ont été importées via un fichier CSV entrent en conflit avec les balises de nomenclature de que vous avez créées, les balises CSV importées seront prioritaires et elles seront les seules à s'appliquer.

</Accordion>

</Accordion>

</Accordion>

## Remarques et restrictions

Remarques :

* La source de toutes les données de performance dans les tableaux de bord d'Optimisation créative (à part les mesures des partenaires) est le modèle d'attribution AppsFlyer. Veuillez noter qu'il existe des différences inhérentes aux modèles d'attribution utilisés par les différentes plateformes publicitaires et les acteurs de la publicité mobile, ce qui peut expliquer les divergences entre les rapports.
* Pour les créations comprenant plusieurs ressources, une seule ressource est affichée (généralement la vidéo).
* Il peut y avoir des différences entre le tableau de bord d'optimisation créative et la vue d'ensemble AppsFlyer en raison de l'actualisation des données (les données sont extraites une fois par jour par le tableau de bord d'optimisation créative, et plusieurs fois par jour pour la vue d'ensemble).

<div data-zendesk-anchors="overview=%C3%A0-propos-de-loptimisation-des-cr%C3%A9ations 01H7SZ8R9ZWZ81WHV26P00YAYP=%C3%A0-propos-de-loptimisation-des-cr%C3%A9ations get-started=d%C3%A9marrer 01H7SZ8RA0YTWWETTZ6N00JSK1=d%C3%A9marrer creative-assets=ressources-de-cr%C3%A9ations 01H7SZ8RA14Q5D32EY5J0WMVYA=ressources-de-cr%C3%A9ations 01H7SZ8RA1C863VRG1P10CJHTR=supported-asset-types 01H7SZ8RA1D9JVG1145CAXEZFX=matching-creatives 01H7SZ8RA191221K683N1Z9R69=measuring-creatives-with-multiple-assets 01H7SZ8RA1KRPFF9AW5P4QKQXH=exemple creative-dashboard=filtrage-et-mesures 01H7SZ8RA1JX2TCQHB5XW21EK8=filtrage-et-mesures 01H7SZ8RA1ATSBZPMFJC0T7HRG=filter-bar 01H7SZ8RA1RT91HKKD0R93T2TA=view-type h_01H9JS005MCGMPJM7NYTW2HCAF=standard-metrics-and-dimensions 01H7SZ8RA222QS1AXDKT49DEK3=unique-metrics-and-dimensions 01H7SZ8RA23SCGJ435B4V32CP1=custom-metrics 01H7SZ8RA2R9N2NC6JXNZZ7C5Z=partner-metrics::e592ecd3 partner-table=table-des-partenaires 01H7SZ8RA2VJ9466WSMN3WHR90=table-des-partenaires 01H8GHNPQKS7REZ9RPH0ZYEBHE=applovin-metrics 01H8GHNPQKCKMDS8AYETEDDZKH=google-ads-metrics 01H8H1GTRV7VNJDKFEF35HCNKY=meta-ads 01H7SZ8RA28T63K3NASWC92R0F=unity-ads-metrics 01H7W4JTRSJJ2R45JQVYHMYGX2=remarque 01H7SZ8RA3TPD6ED2HJZGTVRMS=save-and-share-views custom-tags=balises-personnalis%C3%A9es h_01H9J4Z9V9SJBTE63C358FME95=balises-personnalis%C3%A9es h_01H9J4R9MTMGF9F1PNZRT2QZ1W=custom-dimensions 01H7SZ8RA3GW927GJBKKR4582T=create-and-manage-custom-dimensions 01H7SZ8RA3P8VQFH268G453FKM=example-csv 01H7SZ8RA307CBMA0533M3VGWK=traits-and-limitations h_01H9J67GSXXZ20W56NDVW2XDJC=name-convention-tags h_01H9J6PCQNVAB88ZCKRT3MVJEH=create-and-manage-name-convention-tags h_01H9J6PCQN6MV2KPYNFF7SB44Q=name-tag-traits-and-limitations considerations-and-limitations=remarques-et-restrictions 01H7SZ8RA30MQ4S3B0KVSWAZ51=remarques-et-restrictions" />
