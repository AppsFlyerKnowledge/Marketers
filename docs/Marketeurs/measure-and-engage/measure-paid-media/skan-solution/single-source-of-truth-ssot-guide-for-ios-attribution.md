---
title: 'Guide de l''attribution IOS en SSOT (Single Source Of Truth) '
metadata:
  keywords:
    - iOS
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-11-11T09:28:42Z'
  edited_at: '2024-01-15T10:38:05Z'
  id: 4410634145425
  locale: fr
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/fr/articles/4410634145425
---
> **En bref** : sous environnement iOS 14 et +, AppsFlyer rassemble les données issues de différentes méthodes de correspondance d'attribution (IDFA, IDFV, SKAN, Apple Search Ads, etc), et donne une vision globale des performances des campagnes d'app. Aucune méthode d'attribution ne donne une image complète des performances d'une app. Ce qui est important, c'est de réussir à comptabiliser une seule fois les utilisateurs qui sont attribués par deux méthodes distinctes. Et c'est exactement ce que permet le procédé SSOT (Single Source of Truth) d'AppsFlyer. Les rapports et les métriques SSOT sont fidèles et précis, et ils ne comptabilisent un même utilisateur qu'une seule fois.

<Embed title="Guide de l'attribution IOS en SSOT (Single Source Of Truth)" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/545isomgo1" providerUrl="https://fast.wistia.com" />

<div id="about-single-source-of-truthtrue-ios-performance-data" />

## Comment obtenir des données de performances fidèles sous iOS 14 et + ?

Lecture connexe : <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">Guide de la solution SKAN</Anchor> | <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio">Studio de conversion SKAN</Anchor> | Tableau de bord général

À compter d'iOS 14, AppsFlyer attribue les utilisateurs d'iOS grâce aux données issues de différents flux de données comme SKAdNetwork, les utilisateurs ayant donné leur accord ATT, la modélisation probabiliste, les analyses basées sur l'incrémentalité, et les API dédiées aux Apple Search Ads. Sans IDFA, il est quasi impossible de mettre en commun les méthodes d'attribution sans que les données ne se retrouvent en double.

Le procédé SSOT élimine les données d'installation qui ont été dupliquées et il corrige l'attribution des utilisateurs qui ont été incorrectement attribués. En d'autres termes, les utilisateurs qui ont été attribués par erreur comme organiques se retrouvent ben attribués par une source média non organique. Le nombre d'installations attribuées à une campagne est ainsi corrigé et les métriques associées aux coûts et revenus (comme l'eCPI, le ROI et le ROAS) sont également calculées comme il se doit.

En un mot : le procédé SSOT permet d'indiquer les installations SKAN qui ont aussi été attribuées via un autre type de matching. L'indicateur est intégré au calcul des métriques agrégées afin d'éviter de comptabiliser deux fois le même utilisateur. L'indicateur est également pris en compte lors du traitement des données brutes SKAN.

Pour inclure l'indicateur SSOT dans vos données, vous devez d'abord activer SSOT dans le Studio de Conversion.

<div id="turn-on-single-source-of-truth" />

<Accordion title="Activer le SSOT">

![SSOTControl.png](https://files.readme.io/fd99117e9278ebda3b1f0cc137afb266643e5e45325345ec51aeb58c16d4f13c-31247514683153.png)

**Pour activer le SSOT :**

1. Avant de commencer, veuillez consulter la politique d'AppsFlyer concernant le <Anchor target="_blank" href="https://content.appsflyer.com/ios-hub/billing/">Single Source of Truth</Anchor>.
2. Dans AppsFlyer, ouvrez **Configuration** > **Studio de Conversion SKAN**.
3. Sélectionnez le mode **Personnalisé**.
4. Activez le **SSOT.**
5. Définissez l'ensemble des paramètres.

Voir <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio">Studio de conversion SKAN</Anchor>

</Accordion>

<div id="overview-dashboard-single-source-of-truth-view" />

## Tableau de bord général, fenêtre SSOT

![SSOTisNowOn.png](https://files.readme.io/8e21fd0c64bb85fb94af752eb037472726d68cd55bf028dc5306b0acb398d199-31247490958225.png)

La vue SSOT proposée dans le tableau de bord général offre une vision complète des métriques de performance non organiques. Dans la fenêtre :

* Les métriques d'installation sont fidèles à la réalité.
* Les chiffres liés aux coûts et aux revenus découlant des métriques d'installation (dont l'eCPI, l'ARPU et le ROAS) sont forcément corrects.
* Métriques organiques corrigées après comptabilisation des installations mal attribuées.

Cette section décrit les différences et caractéristiques propres à la fenêtre SSOT. Les instructions partent du principe que vous connaissez déjà le fonctionnement du tableau de bord général.

<div id="turn-on-single-source-of-truth-view" />

<Accordion title="Activer la fenêtre SSOT">

Les données s'affichent dans la fenêtre SSOT entre 3 et 5 jours après activation du SSOT (Source Unique de Vérité) dans le Studio de conversion.

**Pour activer la fenêtre SSOT :**

1. Avant de démarrer, vérifiez que <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio#single-source-of-truth">SSOT (Single Source of Truth)</Anchor> est bien activé dans le Studio de Conversion.
2. Dans AppsFlyer, allez dans **Tableau de bord** > **Général.**  

   <Image alt="SelectSavedReport.png" src="https://files.readme.io/863a9c66c37e031a1f1b2a7fb3e0c68eb9c29405283214e68a432357c35524dd-31247514684177.png" width="243px" />
3. Cliquez sur ▼.
4. Sélectionnez **Aperçu réduit**.  
   Le bouton SSOT s'affiche.  

   <Image alt="SSOTviewon.png" src="https://files.readme.io/7b0a664f0882dad46e7239b5363592717358a79d920377dde13aa9c5dfbe84c3-31247514684433.png" width="246px" />
5. Activez le **SSOT.**
6. L'un des événements suivants se produit :  
   * Affichage des chiffres et graphiques du tableau de bord.  
     Les sections ci-dessous détaillent les données disponibles. Consultez les sections suivantes pour connaître les différentes données.  
     Enregistrer la fenêtre SSOT dans un nouveau rapport. Pour ce faire :  
     1. Cliquez sur ▼.
     2. Cliquez sur **+ Enregistrer le nouveau rapport.**
     3. Saisissez le nom du rapport.
     4. Cliquez sur **Enregistrer**.
   * Les données ne s'affichent pas. Notez que l'affichage des données peut prendre entre 3 et 5 jours après activation de la SSOT. Revenez consulter le tableau de bord une fois le délai écoulé.

Vous pouvez désactiver le SSOT à n'importe quel moment pour accéder aux données classiques contenant les dimensions non disponibles dans la fenêtre SSOT. Vous pourrez ainsi obtenir une analyse encore plus poussée.

</Accordion>

<div id="ssot-view-considerations" />

<Accordion title="Remarques au sujet de la fenêtre SSOT">

Dans la fenêtre SSOT :

* **Valeurs de conversion (VC) Null :** modélisées. Le machine learning avancé est utilisé pour modéliser une valeur Null attribuée par AppsFlyer ou SKAN à l’aide de  [l’indicateur af\_attribution](/docs/single-source-of-truth-ssot-guide-for-ios-attribution#champ-de-lindicateur-dattribution). Si elles sont attribuées à SKAN, toutes les mesures post-installation de SKAN sont incluses dans le tableau de bord SSOT. <Anchor target="_blank" href="/marketers/fr/docs/skan-modeled-data">En savoir plus</Anchor>
* **Re-téléchargements** : compris dans la mesure des installations. Il n'y a pas de différence entre les installations et les re-téléchargements.
* **Fuseau horaire**: les installations et les événements rapportés par AppsFlyer s'affichent en UTC ou dans le fuseau horaire local propre à l'application, tel que défini sur la  page des <Anchor target="_blank" href="/marketers/fr/docs/app-settings">paramètres de l'app.</Anchor> Pour les données rapportées par SKAN, les installations et les événements s'affichent en utilisant UTC, à l'exception des  données Meta et Google SKAN, pour lesquelles le fuseau horaire est basé sur le fuseau horaire configuré dans vos comptes Meta et Google, respectivement.
* **Devise** : est affichée en USD, ou suit la devise propre à l'application qui a été définie sur la  <Anchor target="_blank" href="/marketers/fr/docs/app-settings">page des paramètres de l'app.</Anchor>

<div id="filter-considerations" />

#### Remarques concernant les filtres

Les tableaux ci-dessous indiquent comment les filtres agissent sur l'affichage des données et des résultats.

| Filtre | Remarque |
| --- | --- |
| SSOT (Source Unique de Vérité) | Pour afficher les résultats du SSOT, vérifiez que le contrôle est bien activé. |
| Type de vue | <ul><li>**Acquisition d'utilisateur :** la fenêtre privilégiée pour les données SSOT.</li><li>**Retargeting** : SKAN ne prend pas en charge le retargeting.</li><li>**Unifié** : les campagnes d'installation incluent les données SSOT. Le SSOT n'influe pas sur les campagnes de retargeting.</li></ul> |
| Dates | <ul><li>[Recommandé] Pour obtenir des résultats vraiment précis, choisissez une période d'au moins 7 jours qui n'inclut pas les 3 derniers jours.</li><li>N'oubliez pas :<ul><li>Les périodes inférieures à 7 jours sont moins précises à cause des différences de fuseaux horaires et des estimations sur les heures d'installation SKAN.</li><li>Les installations SKAN Google peuvent être rapportées avec un décalage allant jusqu'à 13 jours.</li></ul></li><li>Au minimum, il faut en général compter 3 jours après l'activation du SSOT. C'est AppsFlyer qui détermine cette date.</li><li>Exemple de sélection de la date (au plus tôt) :<ul><li>Si nous sommes le 10 février et que vous avez activé le SSOT le 29 janvier, vous pouvez sélectionner un jour entre le 1 et le 7 février.</li></ul></li></ul> |
| Filtres de la campagne | Filtres de campagne disponibles (hiérarchie) :<ul><li>Source média</li><li>Campagne</li></ul> |
| Les KPI majeurs | Les KPI majeurs proposés dans le tableau de bord SSOT vous permettent de voir :<ul><li>L'acquisition d'utilisateurs : non organique et organique</li><li>Doublons SKAN</li><li>Le retargeting : réengagements, réattributions</li><li>Coût</li><li>eCPI</li><li>Nombre d'événements frauduleux (in app)</li></ul>À chaque KPI correspond une valeur en pourcentage. Cette valeur indique l'évolution du KPI sur une même durée mais au cours de la période précédente. Par exemple, cette semaine par rapport à la semaine précédente, ou n'importe quels jours de la période comparés au même nombre de jours précédant : si une augmentation de X % du nombre d'installations s'affiche, cela signifie que la période précédente avait X % d'installations en moins. |
| Diagrammes | **Dimensions disponibles :**<ul><li>Méthode d'attribution :<ul><li>Modèles AF : installations matchées via différentes méthodes, y compris SKAN. Dans le tableau de bord, les enregistrements SKAN ne sont pas pris en compte pour éviter de comptabiliser deux fois la même installation. Dans les données brutes SKAN, l'indicateur af\_attribution\_flag de l'installation est défini sur « true ».</li><li>SKAN uniquement : les installations ne matchent qu'avec SKAN et avec aucune autre méthode. Dans les données brutes SKAN, l'élément af\_attribution\_flag de l'installation est défini sur « false ».</li></ul></li><li>Type d'attribution</li><li>Type de touche d'attribution</li><li>Campagne</li><li>Identifiant de la campagne</li><li>Source média</li><li>Source</li><li>ID d'app (pour certains graphiques)</li><li>Géo (les géos SKAN sont <Anchor target="_blank" href="/marketers/fr/docs/skan-modeled-data#geo">modélisés</Anchor>)</li><li>Nom de l'événement in-app (c'est-à-dire le nom d'un événement in-app tel que configuré dans SKAN Conversion Studio).</li></ul>**Métriques :**<br /><br />Telles que décrites dans les sections mesures. |
| Tableau | **Regroupements :**<ul><li>[Par défaut] Le tableau regroupe entre elles les sources média et les campagnes.</li><li>Les différents regroupement incluent : source média, type d’attribution, méthode d’attribution, campagne, ID de campagne, type de touch attribué, date, source, géo, ainsi que toute combinaison des éléments de la liste. **Remarque** : Les géos SKAN sont <Anchor target="_blank" href="/marketers/fr/docs/skan-modeled-data#geo">modélisés</Anchor>.</li><li>Si vous sélectionnez un regroupement dont les dimensions s’appliquent uniquement au trafic non organique, le tableau indiquera N/A pour les sources média organiques.</li></ul>**Métriques :**<br /><br />Telles que décrites dans les sections mesures. |

</Accordion>

<div id="metrics" />

<Accordion title="Métriques">

Métriques disponibles dans le tableau de bord SSOT :

| Métrique | Description et remarques |
| --- | --- |
| Regroupements | <ul><li>[Par défaut] Le tableau regroupe entre elles les sources média et les campagnes.</li><li>Les différents regroupement incluent : source média, type d’attribution, méthode d’attribution, campagne, ID de campagne, type de touch attribué, date, source et toute combinaison de la liste.</li><li>Si vous sélectionnez un regroupement dont les dimensions s’appliquent uniquement au trafic non organique, le tableau indique N/A pour les sources média organiques.</li></ul> |
| **Attributions de la SSOT** | **Répartition par installations SSOT, réattributions et réengagements sur les périodes sélectionnées.**<ul><li>**Non organique : la campagne qui draine l'utilisateur. Le procédé SSOT garantit qu'une même installation n'est comptabilisée qu'une seule fois.**</li><li>**Mesures organiques.**</li></ul> |
| Total | Nombre d'installations, de réattributions et de réengagements. |
| d'installations | Le nombre d'utilisateurs uniques qui installent l'app. Calculé en additionnant les installations attribuées par AppsFlyer dans le cadre des campagnes UA, et les nouvelles installations et re-téléchargements rapportés par SKAN (après suppression des doublons). |
| Ré-attributions | Les mesures de retargeting sont disponibles dans les types de vue Unifiée et Retargeting. N'oubliez pas que SKAN ne prend pas en charge le retargeting. |
| Réengagements | Les mesures de retargeting sont disponibles dans les types de vue Unifiée et Retargeting. N'oubliez pas que SKAN ne prend pas en charge le retargeting. |
| **Autres métriques** | **Diverses autres mesures liées à la SSOT et aux performances publicitaires** |
| Doublons SKAN | Le nombre d'installations SKAN avec af\_attribution\_flag=true |
| Clics | Données sur les clics et les impressions transmises par les réseaux publicitaires via API. Le procédé SSOT n'affecte pas les mesures des points de contact. |
| Impressions | Données sur les clics et les impressions transmises par les réseaux publicitaires via API. Le procédé SSOT n'affecte pas les mesures des points de contact. |
| de l'installation à la première commande | Clic par installation |
| Coût ($) | Données des <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview">Coûts de la campagne</Anchor>  communiquées par les réseaux publicitaires via API. Les données s'affichent pour les campagnes qui possèdent au minimum une installation. Le procédé SSOT n'influe pas sur le coût total indiqué. Il n'affecte que les résultats qui découlent du nombre d'installations. |
| ECPI moyenne ($) | La mesure du coût réel par installation est calculée à partir des résultats d'installations de la fenêtre SSOT.  Elle n'inclut pas les installations organiques. |
| Post clic | Nombre d'attributions se produisant après qu'un utilisateur a cliqué sur une publicité (CTA) |
| Taux de désinstallation | Taux (%) d'utilisateurs qui désinstallent l'app, proportionnellement aux utilisateurs l'attribuant. Soit le nombre d'utilisateurs qui installent, se réengagent ou sont réattribués. Formule : Désinstallations / Attributions x 100 (valable pour l'acquisition d'utilisateurs uniquement) |
| Désinstallations | <span id="simple-tabpanel-2"></span>Nombre d'utilisateurs qui installent l'app et qui la désinstallent (la suppriment) par la suite (pertinent pour l'acquisition d'utilisateurs seulement) |
| Post vue | Nombre d'attributions se produisant après qu'un utilisateur a vu une publicité (VTA) |
| Revenus (J2) | Revenu transmis par SKAN et AF (revenu publicitaire y compris) pour la fenêtre de mesure SKAN (AW) :<ul><li>Revenu SKAN : le revenu pour les installations SKAN (lorsque af\_attribution\_flag=false/null). Repose sur les paramètres de valeur de conversion du <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio#revenue-component">revenu dans Conversion Studio</Anchor>, et sur la durée de la fenêtre de mesure.</li><li>**Revenu transmis par AF :** revenu généré par les utilisateurs d'une app suite à une installation attribuée par AppsFlyer au cours de la fenêtre de mesure SKAN.</li><li>Pour ceux qui utilisent SKAN 4 dans Conversion Studio, il s'agit de données sur les 2 jours qui suivent l'installation. Pour ceux qui utilisent SKAN 3 dans Conversion Studio, les données sont basées sur la fenêtre d'activité SKAN définie, qu'elle soit supérieure ou inférieure à 2 jours.</li><li>N'inclut pas les données relatives aux installations organiques.</li><li>**Exemple :**<ul><li>La fenêtre d'activité est de 24h.</li><li>Les événements de revenu se produisent un jour après l’installation (Jour X+1), mais au cours de la fenêtre d’activité de 24 heures.<ul><li>Les revenus rapportés par SKAN et AF sont comptabilisés étant donné qu'ils ont lieu dans la fenêtre de 24 heures (même s’ils se produisent un autre jour que l’installation).</li></ul></li></ul></li></ul>**Remarque** :<ul><li>Si le revenu SKAN n'est configuré que pour certains événements, la mesure du revenu SSOT prend en compte uniquement les événements de revenu transmis par AF qui lui correspondent.</li></ul>**Conseil** pour augmenter la précision du revenu SKAN :<ul><li>Suivez les <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">instructions relatives au revenu publicitaire SKAN</Anchor>.</li><li>Utilisez nos recommandations concernant le revenu. [Prochainement]</li></ul> |
| Revenus j7 | <ul><li>Inclut les données modélisées, en dehors de la fenêtre de mesure SKAN, jusqu'à 7 jours après l'installation. <Anchor target="_blank" href="/marketers/fr/docs/skan-modeled-data#revenue-ltv">En savoir plus</Anchor></li><li>N'inclut pas les données relatives aux installations organiques.</li></ul> |
| ARPU J2 | Revenu moyen par utilisateur.<br /><br />Formule : Revenu / Utilisateurs uniques<br /><br />Pour ceux qui utilisent SKAN 4 dans Conversion Studio, il s'agit de données sur les 2 jours qui suivent l'installation. Pour ceux qui utilisent SKAN 3 dans Conversion Studio, les données sont basées sur la fenêtre d'activité SKAN définie, qu'elle soit supérieure ou inférieure à 2 jours. |
| ARPU J7 | Inclut les données modélisées, en dehors de la fenêtre de mesure SKAN, jusqu'à 7 jours après l'installation. <Anchor target="_blank" href="/marketers/fr/docs/skan-modeled-data#revenue-ltv">En savoir plus</Anchor> |
| ROAS J2 | Retour sur investissement publicitaire (%).<br /><br />Formule : Revenu / Coût x 100<br /><br />Pour ceux qui utilisent SKAN 4 dans Conversion Studio, il s'agit de données sur les 2 jours qui suivent l'installation. Pour ceux qui utilisent SKAN 3 dans Conversion Studio, les données sont basées sur la fenêtre d'activité SKAN définie, qu'elle soit supérieure ou inférieure à 2 jours. |
| ROAS j7 | Inclut les données modélisées, en dehors de la fenêtre de mesure SKAN, jusqu'à 7 jours après l'installation. <Anchor target="_blank" href="/marketers/fr/docs/skan-modeled-data#revenue-ltv">En savoir plus</Anchor> |
| ROI J2 | Retour sur investissement (%%).<br /><br />Formule : (Revenu - Coût) / Coût x 100<br /><br />Pour ceux qui utilisent SKAN 4 dans Conversion Studio, il s'agit de données sur les 2 jours qui suivent l'installation. Pour ceux qui utilisent SKAN 3 dans Conversion Studio, les données sont basées sur la fenêtre d'activité SKAN définie, qu'elle soit supérieure ou inférieure à 2 jours. |
| ROI J7 | Inclut les données modélisées, en dehors de la fenêtre de mesure SKAN, jusqu'à 7 jours après l'installation. <Anchor target="_blank" href="/marketers/fr/docs/skan-modeled-data#revenue-ltv">En savoir plus</Anchor> |
| Bénéfice brut J2 | Bénéfice après déduction du coût de la campagne.<br /><br />Formule : Revenu - Coût<br /><br />Pour ceux qui utilisent SKAN 4 dans Conversion Studio, il s'agit de données sur les 2 jours qui suivent l'installation. Pour ceux qui utilisent SKAN 3 dans Conversion Studio, les données sont basées sur la fenêtre d'activité SKAN définie, qu'elle soit supérieure ou inférieure à 2 jours. |
| Bénéfice brut J7 | Inclut les données modélisées, en dehors de la fenêtre de mesure SKAN, jusqu'à 7 jours après l'installation. <Anchor target="_blank" href="/marketers/fr/docs/skan-modeled-data#revenue-ltv">En savoir plus</Anchor> |
| **Mesures des événements in-app** | **Mesures des événements in-app spécifiques (IAE)** |
| Utilisateurs uniques de l'événement (J2) | Utilisateurs uniques ayant réalisé l'événement, la mesure résulte de la somme des chiffres AppsFlyer et SKAN, qui incluent les données modélisées des valeurs nulles. Pour ceux qui utilisent SKAN 4, ces données s'additionnent durant les deux premiers jours qui suivent l'installation. Pour ceux qui utilisent SKAN 3, les données s'additionnent durant les jours qui suivent l'installation selon la fenêtre d'activité définie. |
| Événement eCPA (J2) | Coût effectif par action : Coût / Utilisateurs uniques produisant l'événement |
| Conversion d'événement (J2) | Taux (%) d'utilisateurs uniques effectuant l'événement, en proportion de l'attribution des utilisateurs (c'est-à-dire l'installation, la réengagement ou la réattribution). Formule : Utilisateurs uniques / attributions X 100 |
| Revenu des événements (J2) | Revenu généré par cet événement, au cours des jours post installation qui ont été définis |

</Accordion>

<div id="how-does-ssot-work" />

## Comment fonctionne le SSOT ?

<div id="understanding-skanaf-modeled-attribution-duplication" />

<Accordion title="Comprendre la duplication d'attribution modélisée SKAN-AF">

L'attribution SKAN et l'attribution AF modélisée fonctionnent différemment. Elles ont des caractéristiques et des limites différentes. Chaque installation peut donc être attribuée à une source média non organique, soit :

* Via SKAN ou un modèle AF exclusivement (attribution unique).
* Via SKAN et un modèle AF simultanément (doublons). Dans ce cas, le [mécanisme SSOT](/docs/single-source-of-truth-ssot-guide-for-ios-attribution#ssot-mechanism-workings) signale une installation en double de SKAN avec l'indicateur af\_attribution\_flag=TRUE. Et dans le tableau de bord SSOT, une seule installation s'affiche au lieu de deux.
* Ni SKAN ni AF, ce qui signifie que l'installation est organique.

Les scénarios possibles d'attribution du modèle SKAN-AF sont illustrés dans le diagramme de Venn suivant.

![skan_af_model_diagram.png](https://files.readme.io/1b305d053044f79d12b9190d0b6c24dcc7e0bd17e17ef29029ad0b1c3c7d84c0-31247514684689.png)

Le tableau suivant décrit les motifs de chaque scénario d'attribution.

| SKAN uniquement | Modèle AF uniquement | Modèles SKAN et AF | Ni le modèle SKAN ni le modèle AF |
| --- | --- | --- | --- |
| <ul><li>La source média est un SRN, l'appareil de l'utilisateur dispose d'iOS 14,5 et +, l'utilisateur ne fournit pas de consentement ATT double.</li><li>La source média n'est pas un SRN, l'appareil de l'utilisateur dispose d'iOS 14.5 et +, la modélisation probabiliste n'est pas disponible, l'utilisateur ne fournit pas de double consentement ATT.</li></ul> | <ul><li>L'appareil de l'utilisateur dispose d'iOS 14.4 et -.</li><li>La source média ne supporte pas SKAN.</li><li>L'installation s'effectue via un flux web-to-app (SKAN ne prend en charge que l'application d'app à app.</li><li>L'installation se fait par retargeting (non pris en charge par SKAN).</li></ul> | Aucune restriction n'existe et à la fois SKAN et un modèle AF attribuent l'installation.<br /><br />Cela crée des installations en double. SSOT est alors nécessaire pour supprimer le double. | L'utilisateur est organique |

</Accordion>

<div id="ssot-mechanism-workings" />

<Accordion title="Fonctionnement du procédé SSOT">

Le fonctionnement du SSOT est illustré dans le schéma suivant.

![SingleSourceOfTruth.png](https://files.readme.io/882527d4828cf3c7156caf183652368de33463a440715c69f7ec39bfd0f655fa-31247514685329.png)

**Comment fonctionne le procédé SSOT ?**

Le procédé SSOT agit dans le SDK AppsFlyer de votre app soit sur l'appareil utilisateur, soit sur la plateforme AppsFlyer :

**Appareil de l'utilisateur :**

* Un utilisateur ouvre l'application pour la première fois. La plateforme AppsFlyer cherche à attribuer l'utilisateur. La capacité d'attribution dépend du type de campagne et du statut du consentement ATT de l'utilisateur.
* Si l'attribution réussit, le SDK définit le bit d'attribution dans la valeur de conversion (VC)
* Le flux SKAdNetwork se poursuit comme d'habitude. Ce qui signifie que l'activité de l'utilisateur continue d'être mesurée, et que la CV est définie tant que la fenêtre de mesure perdure.
* iOS envoie ensuite le postback.

**Plate-forme AppsFlyer**

* AppsFlyer reçoit le postback d'iOS, il décode la valeur de la conversion puis transmet la valeur du bit d'attribution via af\_attribution\_flag (cf détails dans le tableau suivant).

**Attention**

* En temps normal, AppsFlyer ne comptabilise pas les réinstallations. Dans le cadre du SSOT, l'état de réinstallation n'est pas pris en compte. Ce qui induit que le SSOT ne supprime pas les installations SKAN en double issues des réinstallations mesurées via SSOT, et que ces installations n'affectent pas les paramètres de af\_attribution.

<div id="attribution-flag-field" />

#### **Champ de l'indicateur d'attribution**

| Indicateur SSOT dans la valeur de conversion | Signification | Champ af\_attribution\_flag |
| --- | --- | --- |
| sur | SSOT est activé dans le Studio de Conversion, et AppsFlyer a fini d'attribuer l'utilisateur. | true |
| Désactivé | SSOT est activé dans le Studio de Conversion, et AppsFlyer n'a pas pu attribuer l'utilisateur. | Faux |
| -- | La SSOT est désactivé dans le Studio de conversion. | Null |

**Comment af\_attribution\_flag (bit d'attribution) agit-t-il sur les outils de reporting ?**

* Tableau de bord SKAN : affiche uniquement les performances transmises via postback SKAN. L'indicateur af\_attribution n'est donc pas pris en compte et les doublons ne sont pas supprimés.
* <Anchor target="_blank" href="/marketers/fr/docs/skan-aggregated-performance-report-api">Rapports de performances agrégés</Anchor> et <Anchor target="_blank" href="/marketers/fr/docs/skan-raw-data-reports">rapports de données brutes</Anchor> SKAN : af\_attribution\_flag est présent dans ces rapports. Vous pouvez le mettre à profit dans vos différents rapports. Si vous combinez les données SKAN et les données AppsFlyer, l'indicateur vous permet de supprimer les données en double. Est valable pour les rapports de données brutes et les rapports agrégés.
* Fenêtre SSOT du tableau de bord général : les données de l'ensemble des méthodes d'attribution (SKAN, IDFA, IDFV, Apple Search Ads, etc). sont réunies en une seule fenêtre une fois que les données SKAN en double ont été supprimées.

</Accordion>

<div id="metrics-derived-by-combining-data-from-multiple-attribution-methods" />

<Accordion title="Mesures résultant de l'ajout des données issues de différentes méthodes d'attribution">

Lorsque vous combinez des données SKAN avec des données issues de méthodes d'attribution différentes, l'indicateur af\_attribution\_flag vous permet de supprimer les données en double. Est valable pour les rapports de données brutes et les rapports agrégés.

Les exemples suivants de mesures peuvent être calculés à l'aide de af\_attribution\_flag :

* installations non organiques
* Installations organiques
* eCPI
* Revenus en cohorte

Formule permettant de calculer des exemples de métriques :

| Description de la métrique | Désignation | Formule |
| --- | --- | --- |
| Installations AppsFlyer non organiques | A | Installations non organiques rapportées par AppsFlyer |
| Installations SKAN uniques | B | Installations SKAN lorsque af\_attribution\_flag = false |
| Toutes les installations non organiques | C | A + B |
| Installations organiques | D | Total des installations - C<br /><br />**Remarque** : le nombre total d’installations inclut toutes les installations qui sont enregistrées par le SDK AppsFlyer, quelle que soit leur attribution. |
| ECPI de la campagne | E | Coût / C |
| Revenus en cohorte | F | Additionner les éléments suivants :<ul><li>Revenus des utilisateurs définis par A. Inclure les événements générés au cours de la période post installation égale à votre fenêtre de mesure SKAN.</li><li>Revenus SKAN lorsque af\_attribution\_flag = false</li></ul> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Particularités et limites">

| Particularité | Remarques |
| --- | --- |
| Vue SSOT | La SSOT est disponible uniquement s'il existe au moins un postback SKAN qui contient `af_attribution_flag=true` sur les 5 jours écoulés. |
| Total Installs | Dans certains cas, plus d’installations s'affichent lorsque SSOT est activé que lorsqu’il est désactivé. Cela s'explique notamment par le fait que la modélisation des valeurs de conversion nulles peut avoir un impact sur le calcul de la date d’installation, et peut entraîner des différences lors de la comparaison du nombre d’installations à des dates similaires. |
| Revenu | Les mesures relatives au revenu (ARPU, ROAS, ROI, bénéfice brut) sont proposées depuis le 1er septembre 2022. |
| Agences | Les utilisateurs de l'agence peuvent consulter la vue SSOT dans la vue d'ensemble du tableau de bord. |
| Réseaux publicitaires | <ul><li>Les réseaux publicitaires peuvent accéder à la vue SSOT dans la vue d'ensemble du tableau de bord pour voir les données attribuées à leur source média. Pour voir la vue SSOT :<ul><li>L'annonceur doit avoir activé SSOT dans Conversion Studio.</li><li>Le réseau publicitaire doit exécuter des campagnes SKAN.</li><li>Le réseau publicitaire doit disposer des <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">autorisations requises</Anchor> de la part de l'annonceur pour accéder aux données agrégées.</li></ul></li><li>Le réseau publicitaire peut recevoir des signaux SSOT par l'intermédiaire de postbacks SKAN.</li></ul> |
| Métriques du J7 | Les mesures du J7 peuvent être manquantes ou inférieures aux mesures du J2 si :<ul><li>La plage de dates contient les dates pour lesquelles 8 jours ne se sont pas écoulés.</li><li>Les données modélisées ne sont pas disponibles. Par exemple, s'il n'y a pas 14 jours de données sur le revenu. <Anchor target="_blank" href="/marketers/fr/docs/skan-modeled-data#revenue-ltv">En savoir plus</Anchor></li><li>La configuration de SKAN Conversion Studio a été modifiée au cours des 14 derniers jours.</li><li>Il y a moins de 10 installations pour une date donnée.</li></ul> |
| Modifications de la configuration de SKAN Conversion Studio | Lorsque vous modifiez la configuration de SKAN Conversion Studio, les données SSOT peuvent présenter des inexactitudes pendant environ 84 heures. En effet, AppsFlyer commence immédiatement à décoder les retours SKAN avec le nouveau schéma, mais les retours continuent d'arriver des installations qui ont été encodées avec le schéma précédent. |
| Données rapportées par AF | <ul><li>Les données rapportées par AF, parfois nommées «données de modèle AF», font référence aux données des installations ou autres événements attribués par une autre méthode d'attribution AppsFlyer, qui n'est pas SKAN.</li><li>Le tableau de bord SSOT permet d'empêcher la duplication des installations et des événements attribués à la fois via SKAN et une autre méthode AppsFlyer.</li><li>Si vous activez la SSOT, mais que vous souhaitez accéder aux données qui précèdent l'activation de la SSOT, sachez que le tableau de bord SSOT n'affiche que les données rapportées par AF.</li></ul> |
| Évènement in-app | Les événements in-app (en tant que dimensions) et leurs mesures sont disponibles uniquement pour :<ul><li>Les événements configurés dans SKAN Conversion Studio sont disponibles.</li><li>Les événements survenus au cours de la fenêtre 1 sont disponibles.</li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **À consulter également**
>
> * Vue d'ensemble du tableau de bord

<div data-zendesk-anchors="how-to-get-true-ios-14-performance-data=comment-obtenir-des-donn%C3%A9es-de-performances-fid%C3%A8les-sous-ios-14-et- 01H8TZV6P41Z3ZEZ8VS86DK1J9=comment-obtenir-des-donn%C3%A9es-de-performances-fid%C3%A8les-sous-ios-14-et- 01H8TZV6P4G5AF2MJDQB8J6W2M=turn-on-single-source-of-truth overview-dashboard-single-source-of-truth-view=tableau-de-bord-g%C3%A9n%C3%A9ral-fen%C3%AAtre-ssot 01H8TZV6P4ZBJTDH0FQ6F5D6Q9=tableau-de-bord-g%C3%A9n%C3%A9ral-fen%C3%AAtre-ssot 01H8TZV6P47ZE6PMPF7S9GCJ16=turn-on-single-source-of-truth-view 01H8TZV6P4VCC5NRKBRQNJ4NX3=ssot-view-considerations filter-considerations=remarques-concernant-les-filtres 01H8TZV6P4QXEXYWSXKDB7B5SV=remarques-concernant-les-filtres 01H8TZV6P4YNTFBX5RXVKK8J0F=metrics how-does-ssot-work=comment-fonctionne-le-ssot 01H8TZV6P4K8VXNKDR7JHM8PFW=comment-fonctionne-le-ssot 01H8TZV6P4QYQJ177E2ZG676MH=understanding-skanaf-modeled-attribution-duplication 01H8TZV6P58E502Y1FDFHC3KHM=ssot-mechanism-workings attribution-flag-field=champ-de-lindicateur-dattribution 01H8TZV6P5SSKDTKV4BV3TTA7D=champ-de-lindicateur-dattribution 01H8TZV6P5AHZD8VRWRS4SPBYW=metrics-derived-by-combining-data-from-multiple-attribution-methods 01H8TZV6P5KN4F24ZN33V0TK7K=traits-and-limitations h_01HE182N43SSBX051E4GK7NFQ8=%C3%A0-consulter-%C3%A9galement" />
