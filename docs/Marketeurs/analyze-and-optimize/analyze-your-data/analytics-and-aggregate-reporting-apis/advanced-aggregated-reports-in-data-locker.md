---
title: '[Bêta fermée] Rapports agrégés avancés dans Data Locker'
metadata:
  keywords:
    - Premium
    - Premium Feature
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2024-03-06T10:46:12Z'
  edited_at: '2024-06-10T07:05:11Z'
  id: 23127074968721
  locale: fr
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/fr/articles/23127074968721
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

![beta_feature.png](https://files.readme.io/d57432ddeb4d168760f9acd97f4287473658a8528edc1114ecee8ee2f8e9c9b2-16484830033425.png)

> **En bref :** Les rapports agrégés avancés dans Data Locker contiennent des données agrégées qui sont des données récentes (fraîches), précises, dont la granularité et le volume illimité sont optimaux. Ces rapports sont actuellement en version bêta.

<div id="advanced-aggregated-reports-in-data-locker" />

## Rapports agrégés avancés dans Data Locker

Rapports agrégés avancés dans Data Locker :

* Fournissez un moyen efficace et respectueux de la vie privée de construire vos systèmes de BI internes sur la base de données agrégées : données d’attribution, d’événements et de revenus, avec toutes les mesures possibles ;
* Vous pouvez charger les données dans vos systèmes de BI et les utiliser dans le cadre de vos processus de performance et d’optimisation des campagnes ;
* Avoir les données les plus récentes et précises : les données arrivent <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">plusieurs fois par jour</Anchor> et sont mises à jour avec chaque nouvelle version du rapport contenant toutes les données disponibles pour cette même journée.
* Vous aide à augmenter les données brutes qui peuvent être limitées et <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">restreintes</Anchor> en raison des politiques de partage des données des sources multimédias ou de vos <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">politiques de préservation de la confidentialité</Anchor>. Les restrictions ont un impact sur les champs liés à l’attribution telles que la campagne et le groupe d’annonces.

<div id="setup" />

## Configuration

Pour obtenir des rapports agrégés avancés, effectuez l’une des procédures suivantes.

| Obtenez-vous actuellement des données via Data Locker ? | Procédure |
| --- | --- |
| Oui | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/fd2f20f4365b0ccf2b4f39700587a960563f4087b6f576063c0e49b95e0907c1-23127074967441.png)Pour ajouter les rapports à Data Locker :<ol><li>Dans AppsFlyer, dans le menu latéral, sélectionnez **Signaler > Data Locker**.</li><li>Sélectionnez tous les rapports que vous souhaitez obtenir.</li><li>Cliquez sur **Enregistrer la configuration**.<br />Les rapports seront disponibles le lendemain.</li></ol> |
| Non | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/fd2f20f4365b0ccf2b4f39700587a960563f4087b6f576063c0e49b95e0907c1-23127074967441.png)**Pour configurer Data Locker** :<ol><li>Achevez la toute première configuration Data Locker (<Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers#set-up-data-locker">annonceur</Anchor> \| <Anchor target="_blank" href="/partners/fr/docs/data-locker-for-partners">partenaire</Anchor>).</li><li>Ajoutez des rapports à Data Locker :<ol><li>Dans AppsFlyer, dans le menu latéral, sélectionnez **Signaler > Data Locker**.</li><li>Sélectionnez tous les rapports que vous souhaitez obtenir.</li><li>Cliquez sur **Enregistrer la configuration**.<br />Les rapports seront disponibles le lendemain.</li></ol></li></ol> |

<div id="reports-available" />

## Rapports disponibles

<div id="cohort-versioned-report" />

<Accordion title="Rapport de cohorte versionné">

<div id="report-facts" />

### Faits rapportés

| Introduction | Le rapport versionné par cohorte contient toutes vos données agrégées, par cohorte, avec toute la granularité des dimensions de campagne. Le rapport est mis à jour quasiment toutes les heures pour maximiser la fraîcheur et la précision des données.<br /><br /><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vT8NQKO287TxXpdTYpIASL55t4muIt9G3lnkEE436FQhNn5_14DfYgf0ztbm1VVZXI4ecPaGktdixS7/pub?output=xlsx">Télécharger un exemple de rapport</Anchor> |
| --- | --- |
| Rapports disponibles | Les rapports suivants peuvent être téléchargés. Les types de rapports sont décrits plus en détail dans le tableau de bord Cohorte.<ul><li>**Acquisition d'utilisateurs :**  attribués à une source média d'acquisition d'utilisateurs, y compris la lifetime value (LTV) se produisant pendant les fenêtres de réengagement.</li><li>**Retargeting :** attribués à une source média de retargeting pour les événements qui ont lieu :<ul><li>pendant une fenêtre de réengagement ;</li><li>suite à une réattribution</li></ul></li><li>**Unifiés :** affichent les données sous la dernière source média ayant attiré l'utilisateur, selon les règles de <Anchor target="_blank" href="/marketers/fr/docs/resolve-retargeting-double-attribution">double attribution</Anchor> d'AppsFlyer. Cela signifie que les LTV survenant lors de réengagements s'affichent sous la source média de retargeting et non sous la source média d'UA.</li></ul> |
| Période de reporting | Utilisateurs ayant convertis au cours des 1 095 derniers jours. En d’autres termes, chaque jour, les rapports incluent les événements des utilisateurs qui ont effectué une conversion au cours des 1 095 jours précédents. |
| Structure du rapport | Le schéma du rapport (les mesures et les métriques incluses) est fixe et ne peut pas être modifié. |
| Actualisation des données | <ul><li>Intraday. Les rapports sont envoyés toutes les heures.</li><li>Les rapports sont pour les données du jour. Cela signifie que le 18 avril, chaque version du rapport contient toutes les données actuelles pour le 18 avril. [En savoir plus](/docs/advanced-aggregated-reports-in-data-locker#versions-des-rapports-et-actualisation-des-données)</li></ul> |
| Fuseau horaire | UTC |
| Structure des répertoires et des noms de fichiers | [En savoir plus](/docs/advanced-aggregated-reports-in-data-locker#structure-du-rapport) |
| L'impact des politiques de rétention des partenaires | Considérez que certains partenaires mettent en œuvre une politique de conservation des données. Dans ce cas, les événements survenant après la fin de la période de conservation ne sont pas pris en compte dans les rapports de cohorte.<br /><br />Exemple : SRN «A» a une politique de conservation des données de 180 jours. Les événements utilisateur jusqu’au 180e jour sont attribués à SRN «A». Les événements qui se produisent après le 180e jour ne sont pas pris en compte.<br /><br />**Remarque** : Les événements s’affichent dans le tableau de bord «Vue d’ensemble» comme étant des événements organiques. |

<div id="report-structure" />

### Structure du rapport

Le rapport est composé de mesures et de métriques.

Le format des champs est le suivant :

* **Mesures :** Chaîne. La longueur maximale de la chaîne est dynamique et, dans la plupart des cas, dépend de la façon dont vous renseignez les éléments de la hiérarchie publicitaire.
* **Indicateurs** : Nombre. **Remarque :** Le format de champ selected\_currency est une chaîne.  
  Les métriques disponibles sont les revenus, les utilisateurs uniques qui effectuent un événement et le nombre d’occurrences d’événements. Pour calculer des indicateurs liés aux coûts tels que le ROI (retour sur investissement) et le ROAS (retour sur les dépenses publicitaires), vous avez besoin à la fois de données liés aux revenus et aux coûts. Les mesures de revenus sont dans la partie «Cohorte». Les mesures de coûts sont fournies par le <Anchor target="_blank" href="/marketers/fr/docs/set-up-and-use-roi360-cost-etl-reports">ROI360 Cost ETL.</Anchor>

#### Dimensions

<Table>
  <thead>
    <tr>
      <th>
        Nom du champ
      </th>
      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        app\_id
      </td>
      <td>
        --
      </td>
    </tr>
    <tr>
      <td>
        media\_source
      </td>
      <td>
        --
      </td>
    </tr>
    <tr>
      <td>
        conversion\_type
      </td>
      <td>
        Valeurs possibles : install, install-unified (représentant les installations dans le rapport unifié), réengagement, réattribution
      </td>
    </tr>
    <tr>
      <td>
        attributed\_touch\_type
      </td>
      <td>
        Valeurs possibles : clic, impressions, préinstallation, inconnu, tv, nul
      </td>
    </tr>
    <tr>
      <td>
        days\_post\_attribution
      </td>
      <td>
        * Le nombre de jours écoulés depuis la date de conversion (pas l'horodatage spécifique de la conversion).
        * Astuce ! Utilisez ce tag pour calculer les jours de rétention et ceux des KPI.
      </td>
    </tr>
    <tr>
      <td>
        event\_date
      </td>
      <td>
        * Date à laquelle un utilisateur effectue un événement donné.
        * Format : aaaa-mm-jj
        * Exemple : La date à laquelle un utilisateur a effectué un événement in-app donné. Dans le cas d’une conversion.
        * Important ! Si le event\_name est af\_conversion, la date de l’événement et la date de conversion seront les mêmes.
      </td>
    </tr>
    <tr>
      <td>
        conversion\_date
      </td>
      <td>
        * La date à laquelle la conversion a eu lieu
        * Format : aaaa-mm-jj
        * Exemple : La date d’installation
      </td>
    </tr>
    <tr>
      <td>
        event\_name
      </td>
      <td>
        Identifie l’événement. Certains noms d’événements ont une signification spécifique, tandis que d’autres sont liés à des événements intégrés définis par l’annonceur dans l’application. 

        | event\_name | Qu’a fait l’utilisateur ? |
        | --- | --- |
        | af\_conversion | Utilisateur converti. Utilisez conversion\_type pour identifier s’il s’agit d’une installation, d’un réengagement ou d’une réattribution. |
        | af\_session | a ouvert l'application |
        | cohort\_uninstalls | a désinstallé l'app |
        | Événement in-app défini par l’annonceur | a effectué un événement dans l’application |
      </td>
    </tr>
    <tr>
      <td>
        campagne
      </td>
      <td>
        Hiérarchie des campagnes

        N'oubliez pas : Il n’est pas possible de modifier le nom de la campagne, une fois celui-ci établi. Par conséquent, plusieurs noms peuvent être associés à un même identifiant de campagne.
      </td>
    </tr>
    <tr>
      <td>
        campaign\_id
      </td>
      <td>
        Hiérarchie des campagnes
      </td>
    </tr>
    <tr>
      <td>
        adset
      </td>
      <td>
        Hiérarchie des campagnes
      </td>
    </tr>
    <tr>
      <td>
        adset\_id
      </td>
      <td>
        Hiérarchie des campagnes
      </td>
    </tr>
    <tr>
      <td>
        ad
      </td>
      <td>
        Hiérarchie des campagnes
      </td>
    </tr>
    <tr>
      <td>
        ad\_id
      </td>
      <td>
        Hiérarchie des campagnes
      </td>
    </tr>
    <tr>
      <td>
        canal
      </td>
      <td>
        Hiérarchie des campagnes.

        [À jour le 27 octobre 2021] À l'heure actuelle, les annonces Meta ne renseignent pas le canal dans les données fournies via le mécanisme de référencement d'installation de Google, le Google Install Referrer.
      </td>
    </tr>
    <tr>
      <td>
        site\_id
      </td>
      <td>
        Hiérarchie des campagnes
      </td>
    </tr>
    <tr>
      <td>
        {"is_primary_"} attribution
      </td>
      <td>
        Permet d’identifier et de dédupliquer les données de retargeting.
      </td>
    </tr>
    <tr>
      <td>
        geo
      </td>
      <td>
        Le code de pays ISO dérivé de l’adresse IP de l’utilisateur.
      </td>
    </tr>
    <tr>
      <td>
        agency
      </td>
      <td>
        * Information sur l'agence prise en charge.
        * Lorsque les agences ne fournissent pas de détails complets sur leurs activités (non transparentes), plusieurs lignes avec le même nom de campagne peuvent apparaître si l'annonceur et l'agence lancent des campagnes portant le même nom. Pas d'inquiétude. Les lignes ne sont pas dupliquées.
      </td>
    </tr>
    <tr>
      <td>
        install\_app\_store
      </td>
      <td>
        Applications Android uniquement : La boutique Android à partir de laquelle l’application a été téléchargée. Alimenté par les annonceurs mettant en œuvre <Anchor target="_blank" href="/marketers/fr/docs/set-up-multi-store-android-attribution">l'attribution multi-magasins sur Android.</Anchor> Si ce champ est vide, cela signifie Google Play Store.
      </td>
    </tr>
    <tr>
      <td>
        keywords
      </td>
      <td>
        Le ou les mots utilisés par l'internaute lors de sa recherche. Tels que rapportés par le réseau publicitaire.
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        Keyword ID renvoyé par le réseau publicitaire.
      </td>
    </tr>
  </tbody>
</Table>

<div id="metrics" />

#### Métriques

| Nom du champ | Description | Format |
| --- | --- | --- |
| unique\_users | Nombre d’utilisateurs uniques le jour de l’événement. | Nombre |
| revenue\_usd | <ul><li>Montant du chiffre d’affaires en USD. Par exemple, 100,56 $ est présenté comme 100,56.</li><li>Maximum de 2 décimales après la virgule.</li></ul> | Nombre |
| event\_count | Nombre d'événements. | Nombre |
| selected\_currency | Code de devise à 3 lettres (USD, EUR) que vous définissez dans les paramètres de l’application. Format <Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor>. Il s’agit de la même devise que celle utilisée pour afficher les revenus dans «Cohorte» dans l’interface utilisateur. | Chaîne |
| revenue\_selected\_currency | <ul><li>Montant du revenu dans la devise sélectionnée. Par exemple, si la devise sélectionnée est EUR, alors 1234,56 € est indiqué comme 1234,56</li><li>Maximum de 2 décimales après la virgule</li></ul> | Nombre |
| first\_inapp | <ul><li>Nombre d’utilisateurs effectuant l’événement pour la première fois après leur conversion.</li><li>La somme des indicateurs first\_inapp vous donne le nombre cumulé d’utilisateurs uniques pour l’événement.</li></ul> | Nombre |

<div id="directory-and-filename-structure" />

#### Structure des répertoires et des noms de fichiers

Le chemin vers le rapport consiste en la hiérarchie de dossiers suivante :

Avec le format suivant : `/t=cohort_unified_versioned/dt=/version=/`

<div id="report-folder-hierarchy" />

#### Hiérarchie des dossiers de rapports

Exemple de hiérarchie de dossiers de rapport versionné de cohorte dans le compartiment de l’annonceur :

```
bucket
|
└── t=cohort_unified_versioned
    |
    ├── dt=2024-05-05
    |   |
    |   └── version=1714890235
    |   |    |
    |   |    ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    |
    |   |    ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    │
    |   |    └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |
    |   |
    |   └── version=1714890286
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |   |
    .   . 
    .   .
```

**Légende :**

* **dt** : Date à laquelle les événements inclus dans le rapport se sont produits.
* **t** : type de rapport.
* **version**: Horodatage Unix lors de la création de la version.

<div id="report-versions-and-data-freshness" />

### Versions des rapports et actualisation des données

* Intraday. Les rapports sont envoyés toutes les heures.
* Les rapports concernent toutes les données actuellement disponibles pour la journée. Cela signifie que le 18 avril, chaque version du rapport contient toutes les données disponibles à date pour le 18 avril.
* **Ingérez uniquement la dernière version disponible du rapport.**

| Version | Le rapport inclut les données reçues par AppsFlyer (heure UTC) | Cas d'utilisation | Le rapport d’heure est disponible (heure UTC) |
| --- | --- | --- | --- |
| 1 | Jour 0 à 4h du matin | Données partielles pour le jour 0 | Jour 0 à 8h du matin |
| 2 | Jour 0 à 8h du matin | Données partielles pour le jour 0 | Jour 0 à 13h |
| 3 | Jour 0 à 12h | Données partielles pour le jour 0 | Jour 0 à 18h |
| 4 | Jour 0 à 16h | Données partielles pour le jour 0 | Jour 0 à 21h |
| 5 | Jour 0 à 20h | Données partielles pour le jour 0 | Jour 0 à 23h59 |
| 6 | Jour 0 à 23h59 | Données complètes sur les conversions et les événements in-app pour le jour 0 (à l’exception des événements S2S qu’AppsFlyer reçoit entre le jour 0 à 23h59 et le jour 1 à 2h) | Jour 1 à 4 heures du matin |
| 7 | Jour 1 à 3h | Données complètes sur les conversions et les événements in-app pour le jour 0, ainsi que toutes les données sur les revenus publicitaires actuellement disponibles envoyées via S2S | Jour 1 à 8h |
| 8 | Jour 1 à 11h | Données complètes sur les conversions et les événements in-app pour le jour 0, ainsi que toutes les données sur les revenus publicitaires actuellement disponibles envoyées via S2S | Jour 1 à 18h |
| 9 | Jour 1 à 17h | Données complètes sur les conversions et les événements in-app pour le jour 0, ainsi que toutes les données sur les revenus publicitaires actuellement disponibles envoyées via S2S | Jour 1 à 23:59 |
| 10 | Jour 8 à 7h du matin | Données complètes sur les conversions et les événements in-app pour le jour 0, et données complètes sur les revenus publicitaires envoyées via S2S, en tenant compte de tout problème potentiel qui aurait pu se produire du côté du réseau de revenus publicitaires. | Jour 8 à 13h |

</Accordion>

<div id="cohort-timezone-versioned-report" />

<Accordion title="Rapport versionné sur le fuseau horaire de la cohorte">

<div id="report-facts-1" />

### Faits rapportés

| Introduction | Le rapport versionné par fuseau horaire de cohorte contient toutes vos données agrégées, par cohorte, avec toute la granularité des mesures de campagne, en fonction des fuseaux horaires localisés. Le rapport est mis à jour quasiment toutes les heures pour maximiser la fraîcheur et la précision des données.<br /><br /><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQk1cZkeJhlx3trW13SjGbD4aWX3LmXZJRDJRApuAJkjB7XAg4nSFUyN0_YoirX-QMHkhFeMHwEmiVj/pub?output=xlsx">Télécharger un exemple de rapport</Anchor> |
| --- | --- |
| Rapports disponibles | Les rapports suivants peuvent être téléchargés. Les types de rapports sont décrits plus en détail dans le <Anchor target="_blank" href="/marketers/fr/docs/cohort-and-retention-dashboard#cohort-principles">tableau de bord «Cohorte».</Anchor><ul><li>**Acquisition d'utilisateurs :**  attribués à une source média d'acquisition d'utilisateurs, y compris la lifetime value (LTV) se produisant pendant les fenêtres de réengagement.</li><li>**Retargeting :** attribués à une source média de retargeting pour les événements qui ont lieu :<ul><li>pendant une fenêtre de réengagement ;</li><li>suite à une réattribution</li></ul></li><li>**Unifiés :** affichent les données sous la dernière source média ayant attiré l'utilisateur, selon les règles de <Anchor target="_blank" href="/marketers/fr/docs/resolve-retargeting-double-attribution">double attribution</Anchor> d'AppsFlyer. Cela signifie que les LTV survenant lors de réengagements s'affichent sous la source média de retargeting et non sous la source média d'UA.</li></ul> |
| Période de reporting | Utilisateurs ayant convertis au cours des 1 095 derniers jours. En d’autres termes, chaque jour, les rapports incluent les événements des utilisateurs qui ont effectué une conversion au cours des 1 095 jours précédents.<br /><br />**Remarque** : Si une journée n’a pas encore commencé dans votre fuseau horaire local, les rapports versionnés par fuseau horaire arriveront sans données. |
| Structure du rapport | Le schéma du rapport (les mesures et les métriques incluses) est fixe et ne peut pas être modifié. |
| Actualisation des données | <ul><li>Intraday. Les rapports sont envoyés toutes les heures.</li><li>Les rapports sont pour les données du jour. Cela signifie que le 18 avril, chaque version du rapport contient toutes les données actuelles pour le 18 avril. [En savoir plus](/docs/advanced-aggregated-reports-in-data-locker#versions-des-rapports-et-actualisation-des-données-1)</li></ul> |
| Fuseau horaire | N’importe quel fuseau horaire sauf UTC. Cela signifie que les rapports ne contiennent pas de données pour toutes les applications avec des paramètres de fuseau horaire UTC dans AppsFlyer. |
| Structure des répertoires et des noms de fichiers | [En savoir plus](/docs/advanced-aggregated-reports-in-data-locker#structure-du-rapport-1) |
| L'impact des politiques de rétention des partenaires | Considérez que certains partenaires mettent en œuvre une politique de conservation des données. Dans ce cas, les événements survenant après la fin de la période de conservation ne sont pas pris en compte dans les rapports de cohorte.<br /><br />Exemple : SRN «A» a une politique de conservation des données de 180 jours. Les événements utilisateur jusqu’au 180e jour sont attribués à SRN «A». Les événements qui se produisent après le 180e jour ne sont pas pris en compte.<br /><br />**Remarque** : Les événements s’affichent dans le tableau de bord «Vue d’ensemble» comme étant des événements organiques. |

<div id="report-structure-1" />

### Structure du rapport

Le rapport est composé de mesures et de métriques.

Le format des champs est le suivant :

* **Mesures :** Chaîne. La longueur maximale de la chaîne est dynamique et, dans la plupart des cas, dépend de la façon dont vous renseignez les éléments de la hiérarchie publicitaire.
* **Indicateurs** : Nombre. **Remarque :** Le format de champ selected\_currency est une chaîne.  
  Les métriques disponibles sont les revenus, les utilisateurs uniques qui effectuent un événement et le nombre d’occurrences d’événements. Pour calculer des indicateurs liés aux coûts tels que le ROI (retour sur investissement) et le ROAS (retour sur les dépenses publicitaires), vous avez besoin à la fois de données liés aux revenus et aux coûts. Les mesures de revenus sont dans la partie «Cohorte». Les mesures de coûts sont fournies par le <Anchor target="_blank" href="/marketers/fr/docs/set-up-and-use-roi360-cost-etl-reports">ROI360 Cost ETL.</Anchor>

#### Dimensions

<Table>
  <thead>
    <tr>
      <th>
        Nom du champ
      </th>
      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        app\_id
      </td>
      <td>
        --
      </td>
    </tr>
    <tr>
      <td>
        media\_source
      </td>
      <td>
        --
      </td>
    </tr>
    <tr>
      <td>
        conversion\_type
      </td>
      <td>
        Valeurs possibles : install, install-unified (représentant les installations dans le rapport unifié), réengagement, réattribution
      </td>
    </tr>
    <tr>
      <td>
        attributed\_touch\_type
      </td>
      <td>
        Valeurs possibles : clic, impressions, préinstallation, inconnu, tv, nul
      </td>
    </tr>
    <tr>
      <td>
        days\_post\_attribution
      </td>
      <td>
        * Le nombre de jours écoulés depuis la date de conversion (pas l'horodatage spécifique de la conversion).
        * Astuce ! Utilisez ce tag pour calculer les jours de rétention et ceux des KPI.
      </td>
    </tr>
    <tr>
      <td>
        event\_date
      </td>
      <td>
        * Date à laquelle un utilisateur effectue un événement donné.
        * Format : aaaa-mm-jj
        * Exemple : La date à laquelle un utilisateur a effectué un événement in-app donné. Dans le cas d’une conversion.
        * Important ! Si le event\_name est af\_conversion, la date de l’événement et la date de conversion seront les mêmes.
      </td>
    </tr>
    <tr>
      <td>
        conversion\_date
      </td>
      <td>
        * La date à laquelle la conversion a eu lieu
        * Format : aaaa-mm-jj
        * Exemple : La date d’installation
      </td>
    </tr>
    <tr>
      <td>
        event\_name
      </td>
      <td>
        Identifie l’événement. Certains noms d’événements ont une signification spécifique, tandis que d’autres sont liés à des événements intégrés définis par l’annonceur dans l’application. 

        | event\_name | Qu’a fait l’utilisateur ? |
        | --- | --- |
        | af\_conversion | Utilisateur converti. Utilisez conversion\_type pour identifier s’il s’agit d’une installation, d’un réengagement ou d’une réattribution. |
        | af\_session | a ouvert l'application |
        | cohort\_uninstalls | a désinstallé l'app |
        | Événement in-app défini par l’annonceur | a effectué un événement dans l’application |
      </td>
    </tr>
    <tr>
      <td>
        event\_timezone
      </td>
      <td>
        Le fuseau horaire pour :

        * days\_post\_atribution
        * date\_event
        * conversion\_date
      </td>
    </tr>
    <tr>
      <td>
        campagne
      </td>
      <td>
        Hiérarchie des campagnes

        N'oubliez pas : Il n’est pas possible de modifier le nom de la campagne, une fois celui-ci établi. Par conséquent, plusieurs noms peuvent être associés à un même identifiant de campagne.
      </td>
    </tr>
    <tr>
      <td>
        campaign\_id
      </td>
      <td>
        Hiérarchie des campagnes
      </td>
    </tr>
    <tr>
      <td>
        adset
      </td>
      <td>
        Hiérarchie des campagnes
      </td>
    </tr>
    <tr>
      <td>
        adset\_id
      </td>
      <td>
        Hiérarchie des campagnes
      </td>
    </tr>
    <tr>
      <td>
        ad
      </td>
      <td>
        Hiérarchie des campagnes
      </td>
    </tr>
    <tr>
      <td>
        ad\_id
      </td>
      <td>
        Hiérarchie des campagnes
      </td>
    </tr>
    <tr>
      <td>
        canal
      </td>
      <td>
        Hiérarchie des campagnes.

        [À jour le 27 octobre 2021] À l'heure actuelle, les annonces Meta ne renseignent pas le canal dans les données fournies via le mécanisme de référencement d'installation de Google, le Google Install Referrer.
      </td>
    </tr>
    <tr>
      <td>
        site\_id
      </td>
      <td>
        Hiérarchie des campagnes
      </td>
    </tr>
    <tr>
      <td>
        {"is_primary_"} attribution
      </td>
      <td>
        Permet d’identifier et de dédupliquer les données de retargeting.
      </td>
    </tr>
    <tr>
      <td>
        geo
      </td>
      <td>
        Le code de pays ISO dérivé de l’adresse IP de l’utilisateur.
      </td>
    </tr>
    <tr>
      <td>
        agency
      </td>
      <td>
        * Information sur l'agence prise en charge.
        * Lorsque les agences ne fournissent pas de détails complets sur leurs activités (non transparentes), plusieurs lignes avec le même nom de campagne peuvent apparaître si l'annonceur et l'agence lancent des campagnes portant le même nom. Pas d'inquiétude. Les lignes ne sont pas dupliquées.
      </td>
    </tr>
    <tr>
      <td>
        install\_app\_store
      </td>
      <td>
        Applications Android uniquement : La boutique Android à partir de laquelle l’application a été téléchargée. Alimenté par les annonceurs mettant en œuvre <Anchor target="_blank" href="/marketers/fr/docs/set-up-multi-store-android-attribution">l'attribution multi-magasins sur Android.</Anchor> Si ce champ est vide, cela signifie Google Play Store.
      </td>
    </tr>
    <tr>
      <td>
        keywords
      </td>
      <td>
        Le ou les mots utilisés par l'internaute lors de sa recherche. Tels que rapportés par le réseau publicitaire.
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        Keyword ID renvoyé par le réseau publicitaire.
      </td>
    </tr>
  </tbody>
</Table>

<div id="metrics-1" />

#### Métriques

| Nom du champ | Description | Format |
| --- | --- | --- |
| unique\_users | Nombre d’utilisateurs uniques le jour de l’événement. | Nombre |
| revenue\_usd | <ul><li>Montant du chiffre d’affaires en USD. Par exemple, 100,56 $ est présenté comme 100,56.</li><li>Maximum de 2 décimales après la virgule.</li></ul> | Nombre |
| event\_count | Nombre d'événements. | Nombre |
| selected\_currency | Code de devise à 3 lettres (USD, EUR) que vous définissez dans les paramètres de l’application. Format <Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor>. Il s’agit de la même devise que celle utilisée pour afficher les revenus dans «Cohorte» dans l’interface utilisateur. | Chaîne |
| revenue\_selected\_currency | <ul><li>Montant du revenu dans la devise sélectionnée. Par exemple, si la devise sélectionnée est EUR, alors 1234,56 € est indiqué comme 1234,56</li><li>Maximum de 2 décimales après la virgule</li></ul> | Nombre |
| first\_inapp | <ul><li>Nombre d’utilisateurs effectuant l’événement pour la première fois après leur conversion.</li><li>La somme des indicateurs first\_inapp vous donne le nombre cumulé d’utilisateurs uniques pour l’événement.</li></ul> | Nombre |

<div id="directory-and-filename-structure-1" />

#### Structure des répertoires et des noms de fichiers

Le chemin vers le rapport consiste en la hiérarchie de dossiers suivante :

Avec le format suivant : `/t=cohort_unified_timezone_versioned/dt=/version=/`

<div id="report-folder-hierarchy-1" />

#### Hiérarchie des dossiers de rapports

Exemple de hiérarchie de dossiers de rapport versionnés par fuseau horaire de cohorte dans le compartiment de l’annonceur :

```
bucket
|
└── t=cohort_unified_timezone_versioned
    |
    ├── dt=2024-05-05
    |   |
    |   └── version=1714890235
    |   |    |
    |   |    ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    |
    |   |    ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    │
    |   |    └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |
    |   |
    |   └── version=1714890286
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |   |
    .   . 
    .   .
```

**Légende :**

* **dt** : Date à laquelle les événements inclus dans le rapport se sont produits.
* **t** : type de rapport.
* **version**: Horodatage Unix lors de la création de la version.

<div id="report-versions-and-data-freshness-1" />

### Versions des rapports et actualisation des données

* Intraday. Les rapports sont envoyés toutes les heures.
* Les rapports concernent toutes les données actuellement disponibles pour la journée. Cela signifie que le 18 avril, chaque version du rapport contient toutes les données disponibles à date pour le 18 avril.
* Les cas d’utilisation des rapports peuvent varier en fonction de votre zone géographique et de votre fuseau horaire. [En savoir plus](/docs/advanced-aggregated-reports-in-data-locker#timezone-geos)
* **Ingérez uniquement la dernière version disponible du rapport.**

| Version | Le rapport inclut les données reçues par AppsFlyer (heure UTC) | Cas d'utilisation | Le rapport d’heure est disponible (heure UTC) |
| --- | --- | --- | --- |
| 1 | Jour 1 à 4 heures du matin | Géos de l’Est - données partielles pour le Jour 0 | Jour -1 à 8h du matin |
| 2 | Jour -1 à 8h du matin | Géos de l’Est - données partielles pour le Jour 0 | Jour -1 à 13h |
| 3 | Jour -1 à 12h | Géos de l’Est - données partielles pour le Jour 0 | Jour -1 à 18h |
| 4 | Jour -1 à 16h | Géos de l’Est - données partielles pour le Jour 0 | Jour -1 à 21h |
| 5 | Jour -1 à 20h | Géos de l’Est - données partielles pour le Jour 0 | Jour -1 à 23:59 |
| 6 | Jour -1 à 23:59 | Zones géographiques de l’Est et du Centre - données partielles pour le Jour 0 | Jour 0 à 4h du matin |
| 7 | Jour 0 à 4h du matin | Toutes les zones géographiques - données partielles pour le jour 0 | Jour 0 à 8h du matin |
| 8 | Jour 0 à 8h du matin | Toutes les zones géographiques - données partielles pour le jour 0 | Jour 0 à 13h |
| 9 | Jour 0 à 12h | Toutes les zones géographiques - données partielles pour le jour 0 | Jour 0 à 18h |
| 10 | Jour 0 à 16h | Toutes les zones géographiques - données partielles pour le jour 0 | Jour 0 à 21h |
| 11 | Jour 0 à 20h | <ul><li>Zones géographiques de l’Est - Données complètes sur les conversions et les événements dans l’application pour le jour 0</li><li>Zones géographiques du centre et de l’Ouest - données partielles pour le jour 0</li></ul> | Jour 0 à 23h59 |
| 12 | Jour 0 à 23h59 | Zones géographiques du centre et de l’Ouest - données partielles pour le jour 0 | Jour 1 à 4 heures du matin |
| 13 | Jour 1 à 4 heures du matin | <ul><li>Géos Centraux - Données complètes sur les conversions et les événements dans l’application pour le jour 0</li><li>Zones géographiques occidentales - données partielles pour le jour 0</li><li>Toutes les données de revenus publicitaires actuellement disponibles envoyées via S2S</li></ul> | Jour 1 à 8h |
| 14 | Jour 1 à 8h | Zones géographiques occidentales - données partielles pour le jour 0 et toutes les données sur les revenus publicitaires actuellement disponibles envoyées via S2S | Jour 1 à 13h |
| 15 | Jour 1 à 12h | Zones géographiques occidentales - données partielles pour le jour 0 et toutes les données sur les revenus publicitaires actuellement disponibles envoyées via S2S | Jour 1 à 18h |
| 16 | Jour 1 à 16h | Zones géographiques occidentales - données partielles pour le jour 0 et toutes les données sur les revenus publicitaires actuellement disponibles envoyées via S2S | Jour 1 à 21h |
| 17 | Jour 1 à 18h | Zones géographiques occidentales - données partielles pour le jour 0 et toutes les données sur les revenus publicitaires actuellement disponibles envoyées via S2S | Jour 1 à 23:59 |
| 18 | Jour 1 à 20h | Zones géographiques occidentales : conversion complète, données d’événements in-app pour le jour 0 et données complètes sur les revenus publicitaires envoyées via S2S | Jour 1 à 23:59 |
| 19 | Jour 1 à 23:59 | Données complètes sur les conversions et les événements in-app pour le jour 0, et données complètes sur les revenus publicitaires envoyées via S2S, en tenant compte de tout problème potentiel qui aurait pu se produire du côté du réseau de revenus publicitaires. | Jour 2 à 4h du matin |
| 20 | Jour 8 à 00h00 | Données complètes sur les conversions et les événements in-app pour le jour 0, et données complètes sur les revenus publicitaires envoyées via S2S, en tenant compte de tout problème potentiel qui aurait pu se produire du côté du réseau de revenus publicitaires. | Jour 8 à 6h du matin |

</Accordion>

<div id="additional-information" />

## Informations supplémentaires

<div id="timezone-geos" />

<Accordion title="Zones géographiques de fuseau horaire">

Les cas d’utilisation des rapports peuvent varier en fonction de votre zone géographique et de votre fuseau horaire. Utilisez le tableau suivant pour comprendre quelles zones géographiques correspondent à quels fuseaux horaires.

| Géo | Fuseau horaire |
| --- | --- |
| Europe | UTC+12 - UTC+3 |
| Central | UTC+2.5 - UTC-3 |
| Occidental | UTC-3.5 - UTC-12 |

</Accordion>

<div id="bi-developer-considerations" />

<Accordion title="Considérations pour les développeurs BI">

**Portée des données dans le rapport**

Les rapports contiennent les installations par les utilisateurs en acquisition, les ré-attributions et les ré-engagements de retargeting, ainsi que les événements associés dans l'application.

Vous pouvez charger des rapports unifiés, d’acquisition d’utilisateurs et de retargeting séparément ou ensemble dans votre BI. Si vous les chargez ensemble et que vous souhaitez filtrer les vues par vous-même :

* Pour consolider les données, utilisez le champ is\_primary\_attribution=true ou laissez le champ nul.
* Pour l’acquisition d’utilisateurs, utilisez conversion\_type=Install.
* Pour le retargeting, utilisez conversion\_type=réengagement ou réattribution.

Si vous utilisez simplement la vue unifiée dans votre processus de chargement des données, vous pouvez utiliser la logique pour répartir les données entre les types de campagne, c’est-à-dire l’attribution des utilisateurs (installations) et le retargeting (réengagements). Pour ce faire, utilisez les conversion\_type=install, install-unified, re-engagement ou re-attribution. <Anchor target="_blank" href="/marketers/fr/docs/resolve-retargeting-double-attribution">Double attribution d'événements de retargeting.</Anchor>

**Considérations au niveau du champ**

* Utilisez les jours de post-attribution pour faciliter le calcul des mesures de rétention.
* Calcul des utilisateurs uniques à l’aide des mesures liées au nom et et à l’ID de campagne : Si vous pouvez ignorer la granularité des noms de campagne, vous pouvez totaliser un décompte unique à partir de l'ID de campagne. Les indicateurs seront ainsi fiables.
* Vous pouvez agréger les données à l’aide des champs de hiérarchie de campagne.
* Les revenus en USD sont calculés en utilisant le taux de change du jour de l’événement.

**Considérations générales**

Les données de toutes les applications sont configurables. Ces données peuvent être fournies dans un seul fichier ou des fichiers séparés par application.

</Accordion>

<div id="use-cases" />

<Accordion title="Cas d’utilisation">

Voici quelques exemples d’applications populaires et pratiques des données que les développeurs BI peuvent extraire via Data Locker. Chaque exemple est illustré par une requête SQL et un exemple de visuel Excel.

<div id="1-calculate-retention" />

#### **1. Calcul de la rétention**

Dans l’exemple suivant, nous :

* Calculons la rétention Jour 1 et Jour 7, ainsi que le nombre total d’installations par campagne et publicité ;
* Additionnons le nombre d’événements par événement de conversion en filtrant `event_name` pour qu’il soit `af_conversion` ;
* Analysons spécifiquement les campagnes d’acquisition d’utilisateurs en filtrant les données afin que `conversion_type=install`.

**instruction SQL**

```sql
select
    campaign_id, ad_id,
    sum(if(event_name = 'af_conversion', event_count,0)) as installs,
    sum(if(event_name = 'af_session' and days_post_attribution = 1, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day1,
    sum(if(event_name = 'af_session' and days_post_attribution = 7, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and conversion_type = 'install'
    and app_id = YOUR_APP
group by 1,2
```

**Exemple d’Excel**

| ID de campagne | ID publicitaire | Installations | Jour 1 de rétention | Jour 7 de rétention |
| --- | --- | --- | --- | --- |
| 12345678 | 987654 | 100 | 30 % | 10 % |
| 98765432 | 123456 | 200 | 25 % | 15 % |
| 07315466 | 613770 | 300 | 20 % | 12% |

<div id="2-calculate-arpu-of-multiple-in-app-events" />

#### **2. Calcul de l’ARPU de plusieurs événements dans l’application**

Dans l’exemple suivant, nous :

* Calculons l’ARPU de plusieurs événements in-app par campagne.
* Analysons spécifiquement les campagnes de reciblage en filtrant les données de sorte que `conversion_type=re-engagement` et `conversion_type=re-attribution`.
* Additionnons le nombre d’événements par événement de conversion en filtrant `event_name` pour qu’il soit `af_conversion` ;
* Additionnons les revenus de plusieurs événements, dans ce cas `af_purchase`et `af_coins`.
* Définissez `days_post_attribution` le minimum nécessaire (dans ce cas, 7) pour minimiser la charge de traitement des données.

**instruction SQL**

```sql
select
    campaign_id,
    sum(if(days_post_attribution <= 1 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day1,
    sum(if(days_post_attribution <= 3 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day3,
    sum(if(days_post_attribution <= 7 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and days_post_attribution <= 7
    and conversion_type in ('re-engagement', 're-attribution')
    and app_id = YOUR_APP
group by 1
```

**Exemple d’Excel**

| ID de campagne | Types de conversion | ARPU<br /><br />Jour 1 | ARPU<br /><br />Jour 3 | ARPU<br /><br />Jour 7 |
| --- | --- | --- | --- | --- |
| 12345678 | Réengagement | 6,23 | 5,11 | 2,34 |
| 98765432 | Réengagement | 3,57 | 1,34 | 4,86 |
| 07315466 | Réattribution | 7,41 | 6,79 | 5,29 |

<div id="3-calculate-in-app-event-conversion-rate-for-a-specific-cohort-day" />

#### **3. Calcul du taux de conversion des événements in-app pour un jour de cohorte spécifique**

Dans l’exemple suivant, nous :

* Calculons le taux de conversion de l’événement dans l’application Jour 0 pour plusieurs mesures (dans ce cas, la date de conversion, la zone géographique, la campagne, l’annonce et l’ID du site).
* Analysons les données unifiées (UA et campagnes de remarketing) en filtrant les données de sorte que `is_primary=true`.
* Additionnons le nombre d’événements par événement de conversion en filtrant `event_name` pour qu’il soit `af_conversion` ;
* Définissez `days_post_attribution` le minimum nécessaire (dans ce cas, 7) pour minimiser la charge de traitement des données.

**instruction SQL**

```sql
select
    conversion_date, geo, campaign_id, ad_id, site_id,
    sum(if(days_post_attribution = 0 and event_name = 'af_complete_tutorial', unique_users, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as day0_af_tutorial_conversion
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and is_primary = true
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Exemple d’Excel**

| Date de la conversion | Géo | ID de campagne | ID publicitaire | ID site | Jour 0 af\_complete\_tutorial |
| --- | --- | --- | --- | --- | --- |
| 2022-11-07 | États-Unis | 12345678 | 123456 | site\_123 | 45 % |
| 2022-11-05 | GB | 98765432 | Nul | site\_654 | 70 % |
| 2022-10-31 | KR | 07315466 | Nul | Nul | 63% |

<div id="4-calculate-daily-installs" />

#### **4. Calcul des installations quotidiennes**

Dans l’exemple suivant, nous :

* Calculons le nombre d’installations par ID d’application, date de conversion, source multimédia, nom de l’événement et type de conversion.
* Filtrons les données pour afficher les installations UA (pas le reciblage), en définissant `conversion_type` sur `install`.
* Additionnons les installations en définissant `event_name` pour qu’elles soient `af_conversion`

**instruction SQL**

```sql
select
    app_id,
    conversion_date,
    media_source,
    event_name,
    conversion_type,
    sum(events_count) as total
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and conversion_type = 'install'
    and event_name = 'af_conversion'
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Exemple d’Excel**

| ID d'app | Date de la conversion | Source média | Nom de l'événement | Total |
| --- | --- | --- | --- | --- |
| id123456789 | 2022-11-07 | adnet1\_int | af\_conversion | 105 |
| id123456789 | 2022-11-05 | adnet2\_int | af\_conversion | 216 |
| id123456789 | 2022-10-31 | adnet3\_int | af\_conversion | 327 |

<div id="5-calculate-revenue-from-facebook-ads" />

#### **5. Calcul des revenus à partir des publicités Facebook**

Dans l’exemple suivant, nous :

* Calculons les revenus de Facebook du jour 3 par date de conversion et ID d’application.
* Analysons les données Facebook en filtrant les données de sorte que `media_source='Facebook Ads'`.
* Définissons `days_post_attribution` le minimum nécessaire (dans ce cas, 3) pour minimiser la charge de traitement des données.

**instruction SQL**

```sql
select
    conversion_date,
    app_id,
    media_source,
    sum(if(days_post_attribution <= 3, revenue_usd, 0)) as revenue_day3
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and days_post_attribution <= 3
    and media_source = 'Facebook Ads'
    and app_id in (APP_ID1, APP_ID2, ...)
group by 1,2,3
```

**Exemple d’Excel**

| Date de la conversion | ID d'app | Source média | Revenus<br /><br />Jour 3 |
| --- | --- | --- | --- |
| 2022-11-07 | id123456789 | adnet1\_int | 400,45 |
| 2022-11-05 | id123456789 | adnet2\_int | 99,23 |
| 2022-10-31 | id123456789 | adnet3\_int | 13,34 |

<div id="6-calculate-arpu-per-asa-keyword-id-for-up-to-365-cohort-days" />

#### **6. Calcul de l’ARPU par ID de mot-clé ASA pour un maximum de 365 jours de cohorte**

Dans l’exemple suivant, nous :

* Calculons l’ARPU à partir d’Apple Search Ads par identifiant de mot-clé jusqu’au jour de cohorte 365.
* Analysons les données Apple Search Ads en les filtrant de sorte que `media_source='Apple Search Ads'`.
* Additionnons le nombre d’événements par événement de conversion en filtrant `event_name` pour qu’il soit `af_conversion` ;

**instruction SQL**

```sql
select
    media_source,
    keyword_id,
    sum(if(days_post_attribution <= 365, revenue_usd,0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day365
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and media_source = 'Apple Search Ads'
    and app_id = YOUR_APP
group by 1
```

**Exemple d’Excel**

| Source média | ID de mot clé | ARPU<br /><br />Jour 365 |
| --- | --- | --- |
| adnet1\_int | 123456 | 57,019.93 |
| adnet2\_int | 987654 | 64,867.84 |
| adnet3\_int | 666854 | 48,160.02 |

<div id="9-calculate-dau" />

<div id="8-calculate-purchases-day-7-after-conversion" />

<div id="7-calculate-arpu-days-7-by-attribution-time-per-geo" />

#### **7. Calcul du ARPU (revenu moyen par utilisateur) à J+7 par heure d'attribution et par zone géographique**

L’exemple suivant illustre comment utiliser <Anchor target="_blank" href="/marketers/fr/docs/cohort-and-retention-dashboard#trend-type-kpi-by-attribution-time">les indicateurs de performance par heure d’attribution</Anchor>. Dans cet exemple, nous :

* Calculons l’ARPU à J+7 par date d’attribution et par zone géographique ;
* Les résultats sont triés en fonction du nombre de conversions, les 20 premières zones géographiques s’affichant ;
* Les données sont filtrées de sorte que `conversion_type='install'` ;
* La première colonne indique la zone géographique. La deuxième colonne indique le nombre total de conversions. Les colonnes suivantes affichent le revenu à J+7 pour chaque jour spécifié comme une ligne dans la requête.

**instruction SQL**

```sql
select
    geo,
    sum(if(event_name = 'af_conversion', event_count, 0)) total_conversions,
    sum(if(cohort_day = '2023-07-11' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-11' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_11,
    sum(if(cohort_day = '2023-07-12' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-12' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_12,
    sum(if(cohort_day = '2023-07-13' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-13' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_13,
    sum(if(cohort_day = '2023-07-14' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-14' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_14,
    sum(if(cohort_day = '2023-07-15' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-15' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_15,
    sum(if(cohort_day = '2023-07-16' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-16' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_16
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-07-11' and '2023-07-16'
    and days_post_attribution <= 7
    and conversion_type = 'install'
    and app_id = 'YOUR_APP'
group by 1
order by 2 desc
limit 20
```

**Exemple d’Excel**

| Zone géographique | Total des conversions | ARPU Jour 7 pour 2023-07-11 | ARPU Jour 7 pour 2023-07-12 | ARPU Jour 7 pour 2023-07-13 | ARPU Jour 7 pour 2023-07-14 | ARPU Jour 7 pour 2023-07-15 | ARPU Jour 7 pour 2023-07-16 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Corée du Sud | 120.660 | 7.798,89 $ | 6.997,37 $ | 8.258,95 $ | 9.050,21 $ | 10.018,04 $ | 13.765,73 $ |
| Canada | 35.099 | 64.867,84 $ | 7.050,19 $ | 5.656,33 $ | 9.553,75 $ | 8.632,41 $ | 11.308,06 $ |
| Chili | 26.750 | 48.160,02 $ | 21.249,55 $ | 22.584,57 $ | 24.033,07 $ | 31.118,91 $ | 41.145,22 $ |

#### **8. Calcul des achats à J+7 après la conversion**

Dans l’exemple suivant, nous :

* Calculez le nombre cumulé d’utilisateurs uniques qui effectuent des événements af\_purchase à J+17 après leur conversion (en vue consolidée).
* Calculer le taux de conversion à l'événement, c'est-à-dire la part des personnes converties qui effectuent un achat dans les 7 jours suivant leur conversion.
* Les données sont filtrées de sorte que `conversion_type='install'` ;
* Les données sont regroupées par application, date de conversion, source média, campagne et ensemble publicitaire.

**instruction SQL**

```
select
    app_id, conversion_date, media_source, campaign, adset,
    sum(if(event_name = 'af_conversion', event_count,0)) as unified_conversions,
    sum(if(event_name = 'af_purchase', first_inapp, 0)) as af_purchase_day_7_cumulative_unique_users,
    concat(
        cast(
            round(
                sum(if(event_name = 'af_purchase', first_inapp, 0)) /
                sum(if(event_name = 'af_conversion', event_count, 0)) * 100.0
            ,2)
        as varchar),
    '%') as af_purchase_day_7_cumulative_unique_users_conversion_rate
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-12-01' and '2023-12-31'
    and is_primary = True
    and days_post_attribution <= 7
    and app_id in (APP_ID1, APP_ID2, ...)
group by 1,2,3,4,5
```

**Exemple d’Excel**

| ID d'app | Date de la conversion | Source média | Campagne | Adset | Conversions consolidées | J+7 af\_purchase cumulé | Taux de conversion J+7 af\_purchase |
| --- | --- | --- | --- | --- | --- | --- | --- |
| id123456789 | 2024-03-05 | adnet1\_int | campaign\_1 | adset\_1 | 100 | 20 | 20 % |
| id123456789 | 2024-03-07 | adnet2\_int | campaign\_2 | adset\_2 | 200 | 10 | 5 % |
| id123456789 | 2024-03-31 | adnet3\_int | campaign\_3 | adset\_3 | 150 | 15 | 10 % |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique |  |
| --- | --- |
| Données de coûts | Non disponible. <Anchor target="_blank" href="/marketers/fr/docs/set-up-and-use-roi360-cost-etl-reports">Utilisez Cost ETL.</Anchor> |
| Changements de nom de campagne | Pas de prise en charge. Utilisez l’ID de campagne pour regrouper et filtrer si les noms de campagne ont été modifiés. |
| Actualisation des données | Dans la journée |
| Revenus publicitaires | Disponible |
| Devise | L’USD et la devise spécifique à l’application sont toutes deux disponibles par ligne |
| Fuseau horaire | Le fuseau horaire spécifique à l'application est disponible avec le rapport versionné du fuseau horaire. |
| Données organiques | Disponible |
| Les données sur le nombre de jours suivant la conversion (installation, réattribution, réengagement) sont disponibles | 1 095 jours sont disponibles. |
| Transparence de l'agence | <ul><li>Prise en charge</li><li>Les données des publicités X et Meta sont toujours transparentes</li></ul> |
| Segmentation des apps | Prise en charge |
| Données SKAN | Non inclus. Cela signifie que les données sont fournies par les postbacks iOS. |
| Désinstallation des données | Les désinstallations sont traitées quotidiennement. Ainsi, elles n’apparaissent que dans les rapports qui contiennent des données complètes pour une journée (et non des données partielles). |

</Accordion>

<div id="see-also" />

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/cohort-and-retention-dashboard">Tableau de bord des cohortes</Anchor>

<div data-zendesk-anchors="advanced-aggregated-reports-in-data-locker=rapports-agr%C3%A9g%C3%A9s-avanc%C3%A9s-dans-data-locker h_01HWWH83KNSF4BRGTDJ0JD271G=rapports-agr%C3%A9g%C3%A9s-avanc%C3%A9s-dans-data-locker setup=configuration h_01HWWH83KN9CM7ZY43W01AV6TA=configuration reports-available=rapports-disponibles h_01HWWNY76W6RFKX33MXHE4GSBD=rapports-disponibles h_01HWWNR256DRMBNFX3NV8ATNAY=cohort-versioned-report report-facts=faits-rapport%C3%A9s h_01HVRBVXS47K91A6KVV33S1BY6=faits-rapport%C3%A9s report-structure=structure-du-rapport h_01HWWH83KNE46SPK1MS99XX64D=structure-du-rapport 01H7WG3CA14PQ2PJ58FX8TE6ZH=dimensions metrics=m%C3%A9triques 01H7WG3CA24VQKFVP99S82GCXZ=m%C3%A9triques directory-and-filename-structure=structure-des-r%C3%A9pertoires-et-des-noms-de-fichiers h_01HVRDKKQA17SMJFFAEDG7A2X2=structure-des-r%C3%A9pertoires-et-des-noms-de-fichiers the-report-folder-hierarchy-in-aws=hi%C3%A9rarchie-des-dossiers-de-rapports h_01HETBAQVVA750VTE1ABSM2M47=hi%C3%A9rarchie-des-dossiers-de-rapports report-versions-and-data-freshness=versions-des-rapports-et-actualisation-des-donn%C3%A9es h_01HWWH83KN51RR2VJ2F5N8YQ3J=versions-des-rapports-et-actualisation-des-donn%C3%A9es h_01HWWNVFCWJ7DZCKKKSBMH9NM5=cohort-timezone-versioned-report report-facts::15e071f=faits-rapport%C3%A9s-1 h_01HWWH83KNPZETHR2TQS2E4QNT=faits-rapport%C3%A9s-1 report-structure::43ffff28=structure-du-rapport-1 h_01HWWH83KNG0V2ZMZZ7CTV2GE7=structure-du-rapport-1 01HWSX3FA0K39D9M5RQ7J36Q23=dimensions-1 01HWSX3FA035Z8W6EPV4Q6E3JP=m%C3%A9triques-1 01HWSX3FA189EMBJZ1P21YHC45=structure-des-r%C3%A9pertoires-et-des-noms-de-fichiers-1 01HX97NC4F2WCJABSM2NBSBEDN=hi%C3%A9rarchie-des-dossiers-de-rapports-1 report-versions-and-data-freshness::e0755e26=versions-des-rapports-et-actualisation-des-donn%C3%A9es-1 h_01HWWH83KPS2ANCQKS2B3V529Z=versions-des-rapports-et-actualisation-des-donn%C3%A9es-1 additional-information=informations-suppl%C3%A9mentaires h_01HWWH83KPK8535X9EBZVJ9SQK=informations-suppl%C3%A9mentaires h_01HWWN6GAAD75HPC5GTE40QA37=timezone-geos 01H7WG3CA2C3HV8YT5ZMP9E0QY=bi-developer-considerations 01H7WG3CA2YF03SC6RBMCJYYVX=use-cases 1-calculating-retention=1-calcul-de-la-r%C3%A9tention h_01HMTZ0DZWN54HBQ0ZTY0VFNFM=1-calcul-de-la-r%C3%A9tention 2-calculating-arpu-of-multiple-inapp-events=2-calcul-de-larpu-de-plusieurs-%C3%A9v%C3%A9nements-dans-lapplication h_01HMTZ0DZWHZ77RYWYAQEJV7X5=2-calcul-de-larpu-de-plusieurs-%C3%A9v%C3%A9nements-dans-lapplication 3-calculating-inapp-event-conversion-rate-for-a-specific-cohort-day=3-calcul-du-taux-de-conversion-des-%C3%A9v%C3%A9nements-in-app-pour-un-jour-de-cohorte-sp%C3%A9cifique h_01HMTZ0DZW7VA6T6MQY7BY1JZT=3-calcul-du-taux-de-conversion-des-%C3%A9v%C3%A9nements-in-app-pour-un-jour-de-cohorte-sp%C3%A9cifique 4-calculating-daily-installs=4-calcul-des-installations-quotidiennes h_01HMTZ0DZWARZFAQ9R4VF56YN3=4-calcul-des-installations-quotidiennes 5-calculating-revenue-from-facebook-ads=5-calcul-des-revenus-%C3%A0-partir-des-publicit%C3%A9s-facebook h_01HMTZ0DZW74HWW6Z3VDWDMGRF=5-calcul-des-revenus-%C3%A0-partir-des-publicit%C3%A9s-facebook 6-calculating-arpu-per-asa-keyword-id-for-up-to-365-cohort-days=6-calcul-de-larpu-par-id-de-mot-cl%C3%A9-asa-pour-un-maximum-de-365-jours-de-cohorte h_01HMTZ0DZWSN83V0TEHVM2H5XS=6-calcul-de-larpu-par-id-de-mot-cl%C3%A9-asa-pour-un-maximum-de-365-jours-de-cohorte calculating-arpu-days-0-7-by-attribution-time-per-geo=7-calcul-du-arpu-revenu-moyen-par-utilisateur-%C3%A0-j7-par-heure-dattribution-et-par-zone-g%C3%A9ographique 01H8XYTJVQ1YFBHPWVPP9D7MJ8=7-calcul-du-arpu-revenu-moyen-par-utilisateur-%C3%A0-j7-par-heure-dattribution-et-par-zone-g%C3%A9ographique 01H7WG3CA2Y59D2EVMN3YFFY1W=traits-and-limitations h_01HDNZ8A0QH74CGSEG6TKKARJP=%C3%A0-consulter-%C3%A9galement" />
