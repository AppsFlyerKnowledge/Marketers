---
title: Rapport SSOT (Single Source of Truth) Data Locker pour les marketeurs
metadata:
  keywords:
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2024-07-08T14:14:21Z'
  edited_at: '2024-10-31T09:51:53Z'
  id: 26542697382417
  locale: fr
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/fr/articles/26542697382417
---
> **En bref :** Le rapport SSOT (Single Source of Truth) de Data Locker offre une vue d’ensemble détaillée des performances des campagnes d’app en assemblant les données des différentes méthodes d’attribution, comme la correspondance d’ID et SKAN.  Il permet de gérer des données dans des systèmes BI internes, améliorant ainsi vos capacités d'analyse et de reporting. Si votre plan d'abonnement inclut l'accès aux données brutes, aucun abonnement Data Locker séparé n'est requis.

<div id="ssot-reports-in-data-locker" />

<div id="what-is-data-locker" />

## Qu’est-ce que Data Locker ?

Data Locker est une solution sécurisée qui envoie vos données directement aux principales plate-formes sur le cloud, comme AWS, GCS et Snowflake. Cela permet aux marketeurs d'intégrer et de gérer facilement des données dans leurs systèmes BI internes pour des analyses et des rapports complets. <Anchor target="_blank" href="/marketers/fr/docs/data-locker-advertiser-reports?query=data%20locker">En savoir plus.</Anchor>

<div id="what-is-single-source-of-truth-ssot" />

## Qu’est-ce que la Single source of truth (SSOT) ?

La SSOT (Single Source of Truth) permet d’éviter les problèmes de fragmentation des données en offrant une vue d’ensemble détaillée des performances des campagnes d’app grâce à l’assemblage des données des différentes méthodes d’attribution, comme la correspondance d’ID et SKAN. <Anchor target="_blank" href="/marketers/fr/docs/single-source-of-truth-ssot-guide-for-ios-attribution">En savoir plus.</Anchor>

<div id="benefits-of-ssot-reports-in-data-locker" />

## Intérêts des rapports SSOT dans Data Locker

Rapport SSOT :

* **Obtenir une vue d’attribution précise et complète :** le SSOT assemble les données issues de différentes méthodes d’attribution, elle empêche ainsi de compter deux fois les installations attribuées par plusieurs méthodes d’attribution. Vous avez ainsi la garantie que les données sont exactes et reflètent le comportement et l’attribution véritables des utilisateurs.
* **Charger des données dans vos systèmes BI :** Le SSOT fournit un moyen efficace et précis de créer vos systèmes BI internes à l'aide de données agrégées. Les éléments transférés incluent les attributions, événements in-app et données de revenus, ce qui couvre l’ensemble des dimensions et métriques. En chargeant ces données dans vos systèmes BI, vous pouvez améliorer les performances de vos campagnes et vos processus d'optimisation tout en préservant la confidentialité des utilisateurs.
* **Meilleure granularité** : Le SSOT offre le plus haut niveau de granularité possible, même lors de la modélisation des lacunes de données inhérentes à SKAN. Ces données détaillées permettent de prendre des décisions précises et éclairées.

<div id="setting-up-data-locker" />

<Accordion title="Configuration de Data Locker">

Pour activer les rapports SSOT, effectuez l'une des procédures suivantes.

| Obtenez-vous actuellement des données via Data Locker ? | Marche à suivre |
| --- | --- |
| Oui | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)Pour ajouter les rapports à Data Locker :<ol><li>Dans AppsFlyer, dans le menu latéral, sélectionnez **Exporter > Data Locker**.</li><li>Sélectionnez tous les rapports que vous souhaitez obtenir.</li><li>Cliquez sur **Enregistrer la configuration**.<br />Les rapports seront disponibles le lendemain.</li></ol> |
| Non | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)**Pour configurer Data Locker** :<ol><li>Achevez la toute première configuration Data Locker (<Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers#set-up-data-locker">annonceur</Anchor> \| <Anchor target="_blank" href="/partners/fr/docs/data-locker-for-partners">partenaire</Anchor>).</li><li>Ajoutez des rapports à Data Locker :<ol><li>Dans AppsFlyer, dans le menu latéral, sélectionnez **Exporter > Data Locker**.</li><li>Sélectionnez tous les rapports que vous souhaitez obtenir.</li><li>Cliquez sur **Enregistrer la configuration**.<br />Les rapports seront disponibles le lendemain.</li></ol></li></ol> |

</Accordion>

<div id="ssot-report-facts" />

<Accordion title="Contenu des rapports SSOT">

| Nom | Description |
| --- | --- |
| Rapports disponibles | Les rapports suivants sont disponibles :<ul><li>Acquisition d’utilisateurs : attribue les conversions aux canaux d’acquisition d’utilisateurs. Inclut les activités post-installation qui ont lieu dans les fenêtres de réengagement.</li><li>Retargeting : attribue les conversions aux canaux de retargeting pour les événements qui ont lieu :<ul><li>Suite à une réattribution</li><li>Au cours d’une fenêtre de réengagement</li></ul></li><li>Unifié : attribue les conversions au dernier canal de touch, selon les règles de <Anchor target="_blank" href="/marketers/fr/docs/resolve-retargeting-double-attribution">Double attribution</Anchor> d’AppsFlyer. Cela signifie qu’une activité post-installation qui se produit lors des réengagements s’affichera dans la source de média de retargeting, et non dans la source média AU.</li></ul> |
| Période de reporting | Le rapport fournit des mesures de cohorte jusqu’à 7 jours après l’installation. |
| Structure du répertoire | La structure du répertoire repose sur la date d’installation. Chaque dossier de jour d’installation contient plusieurs versions créées quotidiennement. Chaque version présente le cumul des données mises à jour pour le jour d’installation concerné. Cela signifie que vous ne devez vous occuper que la toute dernière version du rapport. [En savoir plus](/docs/single-source-of-truth-ssot-data-locker-report-for-marketers#structure-du-répertoire) |
| Structure du rapport | Le schéma du rapport (dimensions et métriques comprises) est fixe et ne peut pas être modifié. |
| Fuseau horaire | UTC |
| Actualisation des données | <ul><li>quotidienne.</li><li>Les mesures sont calculées à l’aide des données disponibles à minuit UTC (fin de la journée).</li><li>SLA : les nouveaux rapports sont disponibles dans Data Locker à 16:00 UTC. Une nouvelle version est créée chaque jour pour les 15 derniers jours d’installation. [Lire plus](/docs/single-source-of-truth-ssot-data-locker-report-for-marketers#report-folder-hierarchy)</li></ul> |

</Accordion>

<div id="report-structure" />

## Structure du rapport

Le rapport se compose de dimensions et métriques.

Les métriques couvrent les données des attributions, des revenus et des utilisateurs uniques qui produisent un événement. Pour calculer des indicateurs liés aux coûts tels que le ROI (retour sur investissement) et le ROAS (retour sur les dépenses publicitaires), vous avez besoin à la fois de données liés aux revenus et aux coûts. Les mesures de revenus sont dans le rapport SSOT. Les mesures de coûts sont fournies par l’ETL des coûts ROI360.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/1e32M7XW7Lr7s7LTZUKO4EGwm4VrbbfwT/pub?output=xlsx">Télécharger un exemple de rapport</Anchor>

<div id="field-formats" />

<Accordion title="Formats de champs">

<Table>
  <thead>
    <tr>
      <th>
        Nom de format
      </th>
      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        String [n]
      </td>
      <td>
        La longueur maximale de la chaîne. En général, nous ne limitons pas la longueur des champs à la réception des données, mais les données peuvent être tronquées ensuite.
      </td>
    </tr>
    <tr>
      <td>
        Time string
      </td>
      <td>
        Les chaînes ont le format :

        ```
        yyyy-mm-dd hh:mm:ss.
        ```

        ex.

        ```
        2019-09-17 00:09:25
        ```
      </td>
    </tr>
    <tr>
      <td>
        Enum [n]
      </td>
      <td>
        Les champs Enum ne peuvent contenir que des valeurs spécifiques. Par exemple, selected\_currency a 3 caractères et ne peut contenir que les codes de devise spécifiés
      </td>
    </tr>
    <tr>
      <td>
        Horodatage
      </td>
      <td>
        Horodatage UNIX à 10 chiffres. Ex.  
        4 août 2020, 07:25 UTC se traduit par

        ```
         "timestamp": "1596525944"
        ```
      </td>
    </tr>
    <tr>
      <td>
        Booléen
      </td>
      <td>
        *La valeur du champ peut être *TRUE* ou *FALSE**
      </td>
    </tr>
    <tr>
      <td>
        Integer
      </td>
      <td>
        Integer
      </td>
    </tr>
    <tr>
      <td>
        Float
      </td>
      <td>
        Nombre réel flottant qui peut contenir une décimale et des chiffres après la virgule.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="dimensions" />

<Accordion title="Dimensions">

<Table>
  <thead>
    <tr>
      <th>
        Nom du champ
      </th>
      <th>
        Description
      </th>
      <th>
        Format
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        af\_ad\_id
      </td>
      <td>
        Identifiant publicitaire. Hiérarchie de la campagne.
      </td>
      <td>
        chaîne
      </td>
    </tr>
    <tr>
      <td>
        af\_ad
      </td>
      <td>
        Nom publicitaire.
      </td>
      <td>
        chaîne
      </td>
    </tr>
    <tr>
      <td>
        af\_adset\_id
      </td>
      <td>
        Identifiant de l’adset. Hiérarchie de la campagne.
      </td>
      <td>
        chaîne
      </td>
    </tr>
    <tr>
      <td>
        af\_adset
      </td>
      <td>
        Nom de l'adset.
      </td>
      <td>
        chaîne
      </td>
    </tr>
    <tr>
      <td>
        identifiant\_application
      </td>
      <td>
        ID d'app (app de l'annonceur) avec le préfixe ID.
      </td>
      <td>
        chaîne
      </td>
    </tr>
    <tr>
      <td>
        attribution\_method
      </td>
      <td>
        Méthode utilisée pour attribuer l’événement. Parmi ces procédés, citons les méthodes AppsFlyer, SKAdNetwork (SKAN) et organique.
      </td>
      <td>
        chaîne
      </td>
    </tr>
    <tr>
      <td>
        attributed\_touch\_type
      </td>
      <td>
        Valeurs possibles : impression de clic, null.
      </td>
      <td>
        chaîne
      </td>
    </tr>
    <tr>
      <td>
        campaign
      </td>
      <td>
        Nom de la campagne communiqué par le réseau publicitaire à AppsFlyer.
      </td>
      <td>
        chaîne
      </td>
    </tr>
    <tr>
      <td>
        af\_c\_id
      </td>
      <td>
        Identifiant de la campagne.
      </td>
      <td>
        chaîne
      </td>
    </tr>
    <tr>
      <td>
        days\_post\_attribution
      </td>
      <td>
        Le nombre de jours écoulés depuis la date de conversion (non l'horodatage de la conversion).  
        Astuce ! Vous pouvez l’utiliser pour calculer les jours de rétention et de KPI.
      </td>
      <td>
        int
      </td>
    </tr>
    <tr>
      <td>
        event\_name
      </td>
      <td>
        Identifie l’événement. Certains noms d’événements ont une signification précise, tandis que d’autres sont liés à des événements in-app définis par l’annonceur dans l’application. 

        | event\_name | Action de l’utilisateur |
        | --- | --- |
        | af\_conversion | Utilisateur converti. Utilisez conversion\_type pour identifier s’il s’agit d’une installation, d’un réengagement ou d’une réattribution. |
        | Événement in-app défini par l’annonceur | a effectué un événement in-app |
      </td>
      <td>
        chaîne
      </td>
    </tr>
    <tr>
      <td>
        géolocalisation
      </td>
      <td>
        Le code pays ISO. Dérivé de l’adresse IP de l’utilisateur dans les méthodes d’attribution classiques d’AppsFlyer. Dans SKAN, les données sont soit enrichies à partir de réseaux publicitaires, soit modélisées.
      </td>
      <td>
        chaîne
      </td>
    </tr>
    <tr>
      <td>
        install\_date
      </td>
      <td>
        SKAN : estimé par AppsFlyer d’après l'heure d'arrivée du postback.

        AF :

        * AU : Premier lancement après l’installation
        * Retargeting : Premier lancement après le réengagement/ la réattribution
      </td>
      <td>
        chaîne
      </td>
    </tr>
    <tr>
      <td>
        is\_primary\_attribution
      </td>
      <td>
        AU : True

        Retargeting : Au cours d'une fenêtre de réengagement, nous attribuons à la fois la source média d'origine (qui précède le réengagement) et la source média de réengagement. Pendant que l'événement se trouve dans la fenêtre de réengagement. La source média d'origine sera FALSE (pas d'attribution principale). La source média de réengagement sera TRUE.
      </td>
      <td>
        Bool
      </td>
    </tr>
    <tr>
      <td>
        media\_source
      </td>
      <td>
        Réseau publicitaire attribué à un événement.
      </td>
      <td>
        chaîne
      </td>
    </tr>
    <tr>
      <td>
        selected\_currency
      </td>
      <td>
        Code de devise à 3 lettres (USD, EUR) que vous définissez dans les paramètres de l’application. Format ISO-4217. Il s’agit de la même devise que celle dans laquelle s’affichent les revenus dans l’interface utilisateur SSOT.
      </td>
      <td>
        chaîne
      </td>
    </tr>
    <tr>
      <td>
        conversion\_type
      </td>
      <td>
        Valeurs possibles :  
        Installation : L’utilisateur télécharge et ouvre une app pour la première fois.  
        Réattribution : L’utilisateur réinstalle et il est est attribué à une nouvelle campagne.  
        Re-téléchargement (SKAN) : L’utilisateur réinstalle l’application après l’avoir désinstallée.  
        Réengagement : Réengagement : L’utilisateur ouvre à nouveau l’app après interaction avec une publicité de retargeting.
      </td>
      <td>
        chaîne
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="metrics" />

<Accordion title="Métriques">

| Nom dl choisi | Description | Format |
| --- | --- | --- |
| revenue\_selected\_currency | Cumul des revenus dans la devise sélectionnée. Maximum 2 chiffres après la virgule.  <br />Ex. Pour event\_name=achat avec days\_post\_attribution=2, la valeur reflète le revenu total des événements d’achat dans les deux jours qui suivent l’installation (et pas uniquement le deuxième jour). | double |
| revenue\_usd | Le montant cumulé des revenus en USD.  <br />Ex. Pour event\_name=achat avec days\_post\_attribution=2, la valeur reflète le revenu total des événements d’achat dans les deux jours qui suivent l’installation (et pas uniquement le deuxième jour). | double |
| skan\_duplicates | Les installations attribuées simultanément par SKAN et par d’autres méthodes AF sont ensuite supprimées pour éviter de compter les données SSOT deux fois. | long |
| uninstalls\_count | Nombre d'utilisateurs qui installent l'app et qui la désinstallent (la suppriment) par la suite (valable pour l'acquisition d'utilisateurs uniquement) | long |
| unique\_users | Nombre d’utilisateurs uniques qui produisent un événement. Les valeurs s’additionnent.  <br />Ex. Pour event\_name=achat avec days\_post\_attribution=2, la valeur reflète le nombre total d’utilisateurs qui ont acheté dans les deux jours qui suivent l’installation (et pas uniquement le deuxième jour). | int |

</Accordion>

<div id="modeled-data" />

<Accordion title="Données modélisées">

AppsFlyer modélise des données que les rapports de base de SKAdNetwork ne peuvent pas fournir.

* Valeurs de conversion (CV) nulles : Dans SKAN, Apple peut remplacer les données réelles par une valeur « Null » afin de protéger la confidentialité de l’utilisateur. Pour s’assurer qu’aucune donnée n’est omise, ces valeurs nulles sont modélisées dans la SSOT. <Anchor target="_blank" href="/marketers/fr/docs/skan-modeled-data#null-conversion-values">En savoir plus.</Anchor>
* Métriques post-installation plus longues : Il y a une diminution dans la précision des données de SKAN pour les périodes post-installation qui dépassent des deux premiers jours, ce qui peut entraîner des inexactitudes. Pour maintenir un haut niveau des données, nous modélisons les revenus et les utilisateurs uniques d’événements in-app avec une days\_post\_attribution supérieure à 2. <Anchor target="_blank" href="/marketers/fr/docs/skan-modeled-data#revenue-ltv">En savoir plus.</Anchor>

Données géographiques : SKAN limite la granularité des données, de fait les données géo sont souvent indisponibles. Lorsque cela se produit, nous modélisons les données pour permettre une bonne analyse des performances. <Anchor target="_blank" href="/marketers/fr/docs/skan-modeled-data#geo">En savoir plus.</Anchor>

</Accordion>

<div id="partial-data" />

<Accordion title="Données partielles">

Lors de l’analyse des jours d’installation récents, les mesures relatives aux périodes post-installation plus longues (ex. 7 jours) peuvent être approximatives. Dans ce cas, les mesures sont disponibles mais correspondent à des données partielles.

Quelques règles de base :

* Le rapport affiche toutes les données dès lors qu’elles sont disponibles.
* Après 5 jours, les mesures pour les deux jours post-installation sont complètes*.
* Après 7 jours, les mesures pour les sept jours post-installation sont complètes*. Jusqu’à 15 jours post-installation, le modèle peut continuer à affiner la valeur.

Pourquoi les données partielles apparaissent :

* Maturité des données : lorsque la période écoulée depuis le jour d’installation est plus courte que le nombre de jours analysés, les données continuent à arriver et ne sont pas complètes.
* Retards SKAN : Les données SKAN sont reçues avec un décalage aléatoire. Par exemple, l’activité post-installation des deux premiers jours peut être reçue jusqu’à 96 heures (4 jours) après l’installation.
* Synchronisation des données modélisées : Les données SKAN pour les périodes qui dépassent les 2 jours post-installation sont modélisées. Nos modèles génèrent la première estimation de valeur après 7 jours. Sur cette période (jours 2 à 7), les données issues des méthodes d’attribution classiques AppsFlyer sont disponibles, ce qui n’est pas le cas des données modélisées par SKAN.

Exemples (pour une date d’installation au 1er janvier) :

* Le 2 janvier : Les données SKAN n’ont pas encore été reçues. Les données des 2 jours post-installation seront égales aux données sur moins de 7 jours après l’installation. Toutes les données seront partielles, et composées des données issues des méthodes d’attribution classiques AppsFlyer.
* Le 3 janvier : Les données SKAN sont partiellement reçues. Les données des 2 jours post-installation sont toujours partielles, et contiennent alors partiellement des données SKAN. Les données des 7 jours suivant l’installation n’incluent pas encore de données SKAN modélisées (la première valeur modélisée est disponible 7 jours après l’installation). Par conséquent, entre 2 et 7 jours après l’installation, il est possible d’avoir un résultat plus petit pour les 7 jours post-installation que pour la période des 2 jours post-installation.
* Le 6 janvier : Les données SKAN des deux premiers jours qui suivent l’installation ont été entièrement reçues, y compris les postbacks qui ont le décalage le plus long. Les mesures des deux jours suivant l’installation sont terminées. À ce stade, les mesures des 7 jours suivant l’installation ne sont pas encore complètes.
* Le 8 janvier : Les données modélisées par SKAN pour les 7 jours post-installation sont terminées. Notre modèle continuera à affiner la valeur jusqu’au 16 janvier.

</Accordion>

<div id="directory-structure" />

## Structure du répertoire

<div id="report-folder-hierarchy" />

<Accordion title="Hiérarchie des dossiers d’un rapport">

* Les dossiers principaux sont organisés par type de rapport. Valeurs possibles :
  * ssot\_unified
  * ssot\_retargeting
  * ssot\_user\_acquisition
* Dans ces dossiers, les sous-dossiers sont créés selon la date d’installation.

**Gérer les versions**

* Chaque dossier de date d'installation contient plusieurs versions, créées chaque jour.
* Chaque version reflète les données cumulées mises à jour pour cette date d'installation.
* Les rapports incluent toutes les données qui sont disponibles pour la date d’installation. Par exemple, le 18 avril, la dernière version pour chaque date d’installation contient toutes les données recueillies jusqu'à cette date pour le 18 avril.
* Conseil : traitez toujours la dernière version du rapport disponible pour garantir la précision.

Chaque jour d’installation contient au maximum 15 versions. Au bout de 15 jours, toutes les mesures ont été entièrement corrigées et sont terminées. [En savoir plus.](/docs/single-source-of-truth-ssot-data-locker-report-for-marketers#partial-data)

</Accordion>

<div id="directory-and-filename-structure" />

<Accordion title="Structure des répertoires et noms des fichiers">

Le chemin d’accès au rapport a le format suivant :

`<bucket-name>`/t=`<ssot_unified OR ssot_retargeting OR ssot_user_acquisition>`/install\_date=`<yyyy-mm-dd>`/version=`<unix timestamp>`/`<parquet file number>`

Exemple de structure de dossier dans le compartiment d’un annonceur :

```
bucket
|
└── t=ssot_unified
    |
    ├── install_date=2024-05-05
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

Légende :

* t : Sujet du rapport (type).
* install\_date: La date de l’installation de l’application. Cela signifie que cette activité post-installation apparaîtra en fonction de la date d’installation à laquelle l'utilisateur a téléchargé l'application, et non le jour où l’action a eu lieu.
* Version : Horodatage Unix indiquant quand la version a été créée.

</Accordion>

<div id="bi-developer-considerations" />

## Remarques pour les développeurs BI

**Portée des données dans le rapport :**

Les rapports contiennent des données sur les installations d’acquisition d’utilisateurs, les réattributions de retargeting (re-téléchargements dans SKAN) et les réengagements, ainsi que leurs événements in-app.

<div id="loading-reports" />

<Accordion title="Chargement des rapports">

Vous pouvez charger des rapports unifiés, d'acquisition d'utilisateurs et de retargeting séparément ou ensemble dans votre système BI. Si vous les chargez ensemble et souhaitez filtrer les vues :

* Rapports unifiés : Utilisez le champ is\_primary\_attribution=true ou null .
* Rapports d’acquisition d’utilisateurs : Utilisez conversion\_type=Install.
* Rapports de retargeting : Utilisez conversion\_type=re-engagement ou réattribution :
* Vue unifiée : si vous utilisez la vue unifiée lors du processus de chargement de vos données, vous pouvez répartir les données entre les types de campagnes :

* Utilisez conversion\_type=install, re-engagement ou re-attribution (retéléchargements dans SKAN).
* Consultez la section « Double attribution des événements de retargeting » pour en savoir plus détails

</Accordion>

<div id="days-postattribution" />

<Accordion title="Jours post-attribution">

<div id="important" />

> 🚧 **Attention !**
>
> Le rapport inclut une dimension, days\_post\_attribution, qui associe les revenus et les données uniques des utilisateurs au nombre de jours après l'installation

* Pour les attributions (installations, réengagements, etc.), la valeur est 0.
* Pour les revenus et les événements intégrés à l'application, les données sont classées en cohortes prédéfinies, actuellement limitées à 2 jours et à 7 jours après l'installation.

**Pour analyser avec précision les événements et revenus in-app, vous devez appliquer un filtre pour la dimension days\_post\_attribution.** Voir : l'exemple de requête ci-dessous.

Un exemple d'erreur courante consiste à appliquer une logique simplifiée qui cumule la colonne des recettes pour un ensemble spécifique de dimensions. Cette approche aboutit à des chiffres incorrects, car certaines données de revenus sont comptées deux fois (une fois pour days\_post\_install=2 et une fois de plus pour days\_post\_install=7). Cet exemple est également pertinent pour l’analyse des utilisateurs uniques pour des événements in-app spécifiques.

</Accordion>

<div id="considerations" />

<Accordion title="Attention">

**N’oubliez pas :**

* Dernière version : recherchez toujours la dernière version disponible pour chaque date d'installation, pour vous assurer de travailler avec le plus de données à jour et précises pour votre analyse.
* Calcul des revenus : Le chiffre d'affaires en dollars américains est basé sur le taux de change le jour de l'événement.
* Analyser les attributions : enregistrements où event\_name=af\_conversion reflète les attributions (installations), les réattributions (re-téléchargements) dans SKAN) et les réengagements). Le décompte des attributions apparaît sous la métrique des utilisateurs uniques, et la métrique des revenus pour ces champs sera vide. La valeur sous days\_post\_attribution sera égale à 0.
* Comparer les résultats avec le tableau de bord : lorsque vous comparez les installations au tableau de bord, additionnez les types de conversion de téléchargement et d'installation, comme le tableau de bord considère les deux dans la colonne d'installation.
* Analyser les événements in-app : enregistrements où event\_name n’est pas égal à « af\_conversion » dans les évènements in-app. Le comte d’utilisateurs uniques effectuant l'événement apparaissent dans la métrique unique des utilisateurs, tandis que les revenus générés par ces événements apparaissent sous les indicateurs de revenus.
* Type de conversion : différencier l'acquisition d'utilisateurs et le retargeting des conversions avec cette dimension. À noter qu'une ventilation supplémentaire des données SKAN est disponible (installations vs réinstallations). Lorsque vous comparez les données au tableau de bord SSOT, les deux types sont considérés comme des installations.
* Événement de revenus publicitaires : ils sont inclus lorsque disponibles.
* Segmentation des données : Toutes les données de l’app sont fournies dans un même fichier. Utilisez le champ ID d'application pour segmenter les données par application ou configurez Data Locker pour une segmentation par application.
* Les données de pré-attribution telles que le coût, les clics et les impressions doivent être extraites du rapport ETL des coûts.

</Accordion>

<div id="example-use-cases" />

<Accordion title="Exemple de cas d'utilisation">

Voici quelques exemples d'applications pratiques et populaires des données que les développeurs BI peuvent extraire via Data Locker. Chaque exemple propose une requête SQL et un exemple de visuel Excel.

<div id="calculating-total-attributions-per-campaign" />

<Accordion title="Calcul du nombre total d’attributions par campagne">

Dans cette requête, nous allons :

* Additionner le total des attributions uniques par campagne pour chaque date d'installation.
* Filtrer les conversions avec le nom d'événement « af\_conversion » et un identifiant de campagne spécifique (af\_c\_id).

```sql
SELECT install_date, SUM(unique_users) AS total_attributions
FROM ssot_unified
WHERE event_name = 'af_conversion'
    AND af_c_id = '4475903638579'  -- Change to your specific campaign
    AND app_id = 'YOUR_APP'
GROUP BY install_date;
```

</Accordion>

<div id="calculating-conversions-installs-redownloads-to-compare-to-the-installs-in-the-dashboard-per-unique-campaign" />

<Accordion title="Calcul des conversions (installations et réinstallations) pour les comparer aux installations affichées dans le tableau de bord par campagne unique.">

Dans cette requête, nous allons :

* Compter les conversions en distinguant les nouvelles installations et les retéléchargements par campagne unique et date d'installation.
* Comparer les installations à la métrique d'installations du tableau de bord, qui regroupe les types de conversion « installation » et « réinstallation ».

```sql
SELECT install_date, conversion_type, SUM(unique_users) AS total_conversions
FROM ssot_unified
WHERE event_name = 'af_conversion'
    AND af_c_id = '4475903638579'  -- Change to your specific campaign
    AND conversion_type IN ('install', 're-download')    
-- The dashboard sums both under the install field
    AND app_id = 'YOUR_APP'
GROUP BY install_date, conversion_type;
```

</Accordion>

<div id="calculating-retargeting-conversions-per-geo" />

<Accordion title="Calcul des conversions de retargeting par zone géo">

Dans cette requête, nous allons :

* Compter les conversions issues des campagnes de retargeting ventilées par zones géographiques.
* Considérer les types « réattribution » et « réengagement » pour ces conversions.

```sql
SELECT install_date, conversion_type, geo, SUM(unique_users) AS total_conversions
FROM ssot_unified
WHERE event_name = 'af_conversion'
    AND conversion_type IN ('re-attribution', 're-engagement')    
-- Both types are relevant for re-targeting
    AND app_id = 'YOUR_APP'
GROUP BY install_date, conversion_type, geo;
```

</Accordion>

<div id="calculating-installs-by-attribution-method-per-media-source" />

<Accordion title="Calcul des installations par méthode d’attribution et source média">

Dans cette requête, nous allons :

* Compter les installations par méthodes d'attribution (SKAN, méthodes AppsFlyer et organique) et les segmenter par source média.
* Filtrer par événements « af\_conversion » avec un type de conversion « installation ».

```sql
SELECT install_date, attribution_method, media_source, SUM(unique_users)   
AS total_installs
FROM ssot_unified
WHERE event_name = 'af_conversion'
    AND conversion_type = 'install'
    AND app_id = 'YOUR_APP'
GROUP BY install_date, attribution_method, media_source;
```

</Accordion>

<div id="calculating-cumulative-revenue-of-7-days-postinstall-for-facebook-per-adset" />

<Accordion title="Calcul du revenu cumulé 7 jours après l'installation pour Facebook par ensemble d'annonces">

Dans cette requête, nous mesurons les revenus accumulés dans les 7 jours suivant l'installation pour les publicités diffusées sur Facebook.

```sql
SELECT install_date,
       af_adset,
       SUM(revenue_usd) AS total_revenue_day_7
FROM ssot_unified
WHERE media_source = 'facebook'
    AND days_post_attribution = 7  -- Choose a specific post-install period (cohort)
    AND app_id = 'YOUR_APP'
GROUP BY install_date, af_adset;
```

</Accordion>

<div id="calculating-cumulative-revenue-for-selected-postinstall-periods" />

<Accordion title="Calcul du revenu cumulé pour la période après installation sélectionnée">

Dans cette requête, nous allons :

* Calculer le revenu cumulé pour plusieurs jours sélectionnés après l'installation, en distinguant les sommes pour le jour 2 et le jour 7.
* Veuillez noter que lors de l'analyse des installations des 7 derniers jours, les données des 7 jours suivant l'installation peuvent être incomplètes. [En savoir plus](/docs/single-source-of-truth-ssot-data-locker-report-for-marketers#partial-data)

```sql
SELECT install_date,
       SUM(IF(days_post_attribution = 2, revenue_usd, 0)) AS total_revenue_day2,
       SUM(IF(days_post_attribution = 7, revenue_usd, 0)) AS total_revenue_day7
FROM ssot_unified
WHERE app_id = 'YOUR_APP'
GROUP BY install_date;
```

</Accordion>

<div id="calculating-revenue-from-a-specific-inapp-event-purchase-per-media-source" />

<Accordion title="Calcul des revenus générés par un événement in-app spécifique (achat) par source média">

Dans cette requête, nous allons :

* Mesurez la valeur des revenus à partir d'un évènement in-app spécifique (comme « af\_purchase ») et additionnez ces données par source média.
* Filtrez les jours sélectionnés après l'installation pour vous assurer que les données ne sont pas comptées deux fois.

```sql
SELECT install_date, media_source, SUM(revenue_usd) AS total_purchase_revenue
FROM ssot_unified
WHERE event_name = 'af_purchase'  -- Change to your specific event
    AND days_post_attribution = 7  -- Choose a specific post-install period (cohort)
    AND app_id = 'YOUR_APP'
GROUP BY install_date, media_source;
```

</Accordion>

<div id="calculating-inapp-event-conversion-rate-for-2-days-postinstalls" />

<Accordion title="Calcul du taux de conversion des événements in-app pour les 2 jours post-installation">

Dans cette requête, nous calculons le taux de conversion d’un évènement in-app spécifique (tel que « af\_complete\_tutorial ») par rapport à toutes les installations.

```sql
SELECT install_date,
  SUM(IF(days_post_attribution = 2 AND   
event_name = 'af_complete_tutorial', unique_users, 0)) 
  / SUM(IF(event_name = 'af_conversion', unique_users, 0))   
AS conversion_rate_day2_af_tutorial_conversion
FROM ssot_unified
WHERE conversion_type = 'install'    
-- Choose the conversion types for the sample group you want to measure
    AND app_id = 'YOUR_APP'
GROUP BY install_date;
```

</Accordion>

<div id="calculating-arpu-for-7-days-and-2-days-postinstall-per-campaign-id" />

<Accordion title="Calcul de l’ARPU pour les 7 jours et 2 jours post-installation par ID de campagne">

Dans cette requête, nous allons :

* Calculer le revenu moyen par utilisateur (ARPU) pendant les jours 2 et 7 après l'installation, pour toutes les campagnes.
* Veuillez noter que lors de l'analyse des installations des 7 derniers jours, les données des 7 jours suivant l'installation peuvent être incomplètes. [En savoir plus](/docs/single-source-of-truth-ssot-data-locker-report-for-marketers#partial-data)

```sql
SELECT install_date,
       af_c_id,
       SUM(IF(days_post_attribution = 2, revenue_usd, 0)) 
       / SUM(IF(event_name = 'af_conversion', unique_users, 0)) AS ARPU_day2,
       SUM(IF(days_post_attribution = 7, revenue_usd, 0)) 
       / SUM(IF(event_name = 'af_conversion', unique_users, 0)) AS ARPU_day7
FROM ssot_unified
WHERE conversion_type = 'install'  
       -- Choose the conversion types for the sample group you want to measure
    AND app_id = 'YOUR_APP'
GROUP BY install_date, af_c_id;
```

</Accordion>

<div id="calculating-amount-of-duplicates-per-media-source-in-this-query" />

<Accordion title="Calcul du nombre de doublons par source média dans cette requête">

Dans cette requête, nous comptons le nombre total de doublons pour les attributions des utilisateurs par source média et date d'installation, pour mettre en avant les canaux média susceptibles d'avoir un contenu dupliqué plus élevé dans l'attribution des utilisateurs.

```sql
SELECT install_date, media_source, SUM(skan_duplicates)
FROM ssot_unified
WHERE app_id = 'YOUR_APP'
    AND event_name = 'af_conversion'
GROUP BY install_date, media_source;
```

```sql
SELECT install_date, media_source, SUM(skan_duplicates)
FROM ssot_unified
WHERE app_id = 'YOUR_APP'
GROUP BY install_date, media_source;
```

</Accordion>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limites">

| Col a | Col b |
| --- | --- |
| Données de coûts | Les données sur les coûts ne sont pas disponibles. <Anchor target="_blank" href="/marketers/fr/docs/set-up-and-use-roi360-cost-etl-reports">ETL des coûts</Anchor> peut être utilisé à la place. |
| Disponibilité des rapports par jour | Seuls les jours d’installation où la SSOT a été activée en fin de journée auront un rapport SSOT pour ce jour-là |
| Mesures 2 jours post-installation | <ul><li>Pour SKAN 4 dans Conversion Studio : les données correspondent aux 2 jours post-installation.</li><li>Pour SKAN 3 dans Conversion Studio : les données sont basées sur la fenêtre d’activité SKAN définie.<br />Ex. Si la fenêtre d’activité est de 24 heures, les événements qui se produisent dans cette fenêtre (même au jour X+1) sont comptés.</li></ul> |
| Disponibilité des événements in-app | <ul><li>Disponible uniquement pour les événements configurés dans SKAN Conversion Studio.</li><li>Disponible uniquement pour les événements qui se sont produits pendant la fenêtre 1.</li></ul> |
| Revenu | Si le revenu SKAN n'est configuré que pour certains événements, la mesure du revenu SSOT prend en compte uniquement les événements de revenu transmis par AF qui correspondent. |
| Répartition des re-téléchargements SKAN | Disponible. Dans le tableau de bord SSOT, cette répartition n’est pas disponible et les installations et re-téléchargements sont compris dans la mesure des installations. |
| Modifications de la configuration de SKAN Conversion Studio | Modifier la configuration de SKAN Conversion Studio peut entraîner des inexactitudes dans les données SSOT pendant environ 96 heures, puisque les postbacks des installations encodées avec le précédent schéma continuent à arriver. |
| Fuseau horaire | Le fuseau horaire spécifique à l'application n'est pas disponible. |
| Données organiques | <ul><li>Disponible pour les mesures des 2 jours post-installation.</li><li>Indisponible pour les mesures des 7 jours post-installation.</li></ul> |
| Données des jours post-conversion (installation, réattribution, réengagement) | Limité à 7 jours après la conversion |
| Transparence de l'agence | Soutenu. Les données des publicités X et Meta sont toujours transparentes |
| Changements de nom de campagne | Pas de prise en charge. Utilisez l’ID de campagne pour regrouper et filtrer si les noms de campagne ont été modifiés. |
| Réseaux publicitaires | <ul><li>Peut accéder aux rapports DataLocker SSOT pour voir les données attribuées à leur source média si :<ul><li>L’annonceur a activé la SSOT dans Conversion Studio.</li><li>Le réseau publicitaire mène des campagnes SKAN.</li><li>Le réseau publicitaire doit disposer des <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">autorisations</Anchor> données par l'annonceur pour accéder aux données agrégées.</li></ul></li></ul> |
| Accès aux agences | Non disponible. Les utilisateurs de l’agence peuvent afficher les données SSOT dans le tableau de bord SSOT. |
| Mesures du J7 | <ul><li>Peuvent être manquantes ou inférieures aux mesures du J2 si :<ul><li>La période comprend des dates qui ont moins de 8 jours.</li><li>Les données modélisées ne sont pas disponibles (ex. moins de 14 jours de données sur les revenus). <Anchor target="_blank" href="/marketers/fr/docs/skan-modeled-data#revenue-ltv">En savoir plus.</Anchor></li><li>La configuration de SKAN Conversion Studio a été modifiée au cours des 14 derniers jours.</li><li>Il y a moins de 10 installations pour une date donnée.</li></ul></li></ul> |
| Nom d'événement prédéfini | Comme le nom d’événement af\_conversion est utilisé pour indiquer différents types de conversions, les apps qui ont un événement spécifiquement nommé af\_conversion verront le nom de leur événement d’origine changé en af\_conversion\_event. |
| Différences pour la devise locale | Comme le tableau de bord SSOT et le rapport DataLocker SSOT ne sont pas calculés simultanément, de petits écarts peuvent exister entre les revenus en devise locale dans le tableau de bord, et la devise définie dans le rapport. Cela est dû aux légères différences dans le taux de change utilisé au moment des calculs. |
| Données partielles de SKAN au J7 | Étant donné que les données SKAN au J7 sont modélisées et que la version initiale est prête 7 jours après l’installation, les données au J7 seront partielles lors de l’analyse des mesures au J7. Pour les enregistrements dont la méthode d’attribution est SKAN, les mesures au J7 seront inférieures aux mesures du J2. |
| Granularité limitée pour les revenus J7 et les mesures d’événements in-app | Les mesures des revenus et des événements d’utilisateurs uniques pour les 7 jours post-installation ne sont pas disponibles aux niveaux adset, publicité et type de conversion. Comme ce degrés de précision n’est généralement pas disponible dans SKAN, le modèle ne tient pas compte ces dimensions. |
| Actualisation des données sur les revenus publicitaires | Les données sur les revenus publicitaires sont retardées d'un jour.<br /><br />Par exemple, un rapport créé le matin du 3 juillet inclura des données sur les revenus publicitaires jusqu'au 1er juillet inclus. |

</Accordion>

<div data-zendesk-anchors="ssot-reports-in-data-locker=quest-ce-que-data-locker- h_01J454K90GWKME8F4JCDQKM3CK=quest-ce-que-data-locker- what-is-single-source-of-truth-ssot=quest-ce-que-la-single-source-of-truth-ssot- h_01J454K90GRCFR3PSAQRTX98B4=quest-ce-que-la-single-source-of-truth-ssot- benefits-of-ssot-reports-in-data-locker=int%C3%A9r%C3%AAts-des-rapports-ssot-dans-data-locker h_01J454PANH9J6ZZ069RS6FVWZM=int%C3%A9r%C3%AAts-des-rapports-ssot-dans-data-locker h_01J46BV63AM52S5NFRJQ0CTG4M=setting-up-data-locker h_01J29BTC9CESJF592P616WMK46=ssot-report-facts report-structure::673746b9=structure-du-rapport h_01J29CQ5K4JBEP4X8YQ0V32WYR=structure-du-rapport h_01J29CHBX2QNFTAQSA1W01PFH0=field-formats h_01J29BTC9CJ8GZDDCHK9NBZ4YX=dimensions h_01J29BTC9C86YMVEY17QQZNZCV=metrics h_01J29BTC9CH3DAA7ZRHG8C04MF=modeled-data h_01J29M72WAPH3KEW9N60JHTT3W=partial-data directory-structure=structure-du-r%C3%A9pertoire h_01J29MB7B7Q3PJ9YWFQESWN0KD=structure-du-r%C3%A9pertoire h_01J29MCSH4V41CPB7ZG41751QW=report-folder-hierarchy h_01J29MCSH40ATHNAJMY8KR7ANZ=directory-and-filename-structure bi-developer-considerations=remarques-pour-les-d%C3%A9veloppeurs-bi h_01J29MS6XV7XYTA9Q81454WEQN=remarques-pour-les-d%C3%A9veloppeurs-bi h_01J2F4HG8YHDGYFKHBBC5KSN2G=loading-reports h_01J2F4HG8YKNEVGEWTR91ADSDS=days-postattribution h_01J3YT1X908JVMDXKRQBCRD1JR=attention- h_01J2F4HG8YAAE0E04Y6Q9Z62NZ=considerations h_01J3A82HZF14CCS027FE991M0T=example-use-cases h_01J3A883DQFQE0WTTY4FMX3AQ4=calculating-total-attributions-per-campaign h_01J3A883DQ82K71XY408M2BW0B=calculating-conversions-installs-redownloads-to-compare-to-the-installs-in-the-dashboard-per-unique-campaign h_01J3A883DQ5QAVH6AX7CGCBSWG=calculating-retargeting-conversions-per-geo h_01J3A883DQE25X31SPPF166BRH=calculating-installs-by-attribution-method-per-media-source h_01J3A883DQ8QVR8WKPPX1QF414=calculating-cumulative-revenue-of-7-days-postinstall-for-facebook-per-adset h_01J3A883DQ51T3Z6H239P5JDJ1=calculating-cumulative-revenue-for-selected-postinstall-periods h_01J3A883DQXRCQ4NWY0BCX886E=calculating-revenue-from-a-specific-inapp-event-purchase-per-media-source h_01J3A883DQRR62BWQ6JBTZ7238=calculating-inapp-event-conversion-rate-for-2-days-postinstalls h_01J3A883DRPEVDQCWKCT9M3EC1=calculating-arpu-for-7-days-and-2-days-postinstall-per-campaign-id h_01J3A883DRRZ9Y8F3KNAAPZT2S=calculating-amount-of-duplicates-per-media-source-in-this-query h_01J29MV69M667QDHMS5WGYKPCZ=traits-and-limitations" />
