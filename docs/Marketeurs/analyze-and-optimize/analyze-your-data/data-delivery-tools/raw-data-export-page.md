---
title: Page d'exportation des données brutes
metadata:
  keywords:
    - ad networks
    - Advertisers
    - Agencies
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
    - Ad Networks
  created_at: '2020-05-11T22:25:33Z'
  edited_at: '2024-09-18T17:32:39Z'
  id: 360008613838
  locale: fr
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/fr/articles/360008613838
---
> **En bref :** comprendre comment télécharger les rapports de données brutes en fichiers CSV. 1 million de lignes maximum par téléchargement. Limitez les données dont vous avez besoin dans le rapport en utilisant des filtres.

Le visuel ci-dessous s'affiche la première fois que vous ouvrez la page d'**exportation des données brutes**. La page **Mes rapports** s'ouvre si vous avez des rapports prêts à être téléchargés ou dupliqués.

[![RawDataSplash.png](https://files.readme.io/febb6a32a3a7b86c5b396cd77ff9e7968057f57ed20fd991d6dbb4899d5eaf07-41225791757969.png)](https://files.readme.io/febb6a32a3a7b86c5b396cd77ff9e7968057f57ed20fd991d6dbb4899d5eaf07-41225791757969.png)

**Mes rapports**

La page **Mes rapports** contient les rapports déjà générés et qui peuvent être téléchargés et/ou dupliqués. Les rapports listés ont été générés durant les 90 derniers jours, leur période de téléchargement est de 7 jours maxi. Au delà de 7 jours, si vous avez besoin du rapport, vous devez le générer à nouveau.

Pour en savoir plus sur le contenu des rapports de données brutes, cf <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">Présentation des rapports de données brutes.</Anchor>

Pour générer ou télécharger un rapport, consultez la section *Marche à suivre* de cet article.

[![MyReportsRawDataExport.png](https://files.readme.io/1f82e365a7e6cd802ee899666b800be357ea5e99aa6909e75b1fa39a2e4a164e-41225791760145.png)](https://files.readme.io/1f82e365a7e6cd802ee899666b800be357ea5e99aa6909e75b1fa39a2e4a164e-41225791760145.png)

<div id="raw-data-export-page-features-and-filter-options" />

<Accordion title="Fonctionnalités de la page d'exportation des données brutes et options de filtrage">

La page d'exportation des données brutes offre des rapports avec les fonctionnalités décrites dans ce tableau :

<Table>
  <thead>
    <tr>
      <th>
        Fonctionnalité
      </th>
      <th>
        Remarques
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="report-categories"></span>
        Catégories des rapports
      </td>
      <td>
        Varie selon votre type d'abonnement
      </td>
    </tr>
    <tr>
      <td><span id="date-range"></span>
        Période
      </td>
      <td>
        Les rapports de données brutes sont filtrés par date d'activité (moment de l'événement). Vous pouvez également ajouter un filtre pour voir les dates d'installation. La liste des options de filtrage se trouve dans le tableau suivant.
      </td>
    </tr>
    <tr>
      <td><span id="maximum-number-of-rows"></span>
        Nombre maximum de lignes
      </td>
      <td>
        1 million de lignes
      </td>
    </tr>
    <tr>
      <td><span id="rate-limitation"></span>
        Limitation du taux
      </td>
      <td>
        Un système d’application de <Anchor target="_blank" href="/marketers/fr/docs/report-generation-quotas-rate-limitations">quotas</Anchor> limite le nombre de rapports pouvant être générés chaque jour.
      </td>
    </tr>
    <tr>
      <td><span id="retentionreport-window"></span>
        Rétention / Fenêtre du rapport
      </td>
      <td>
        Rapports sur les installations (installations, postbacks d'installation) **60** jours sur les 90 derniers jours dans un même téléchargement.

        Rapports sur les événements in-app : 31 jours sur les 90 derniers jours dans un même téléchargement.
      </td>
    </tr>
    <tr>
      <td><span id="filter-options"></span>
        Options de filtrage
      </td>
      <td>
        Vous pouvez utiliser les filtres répertoriés. Pour certains filtres, les options du filtre sont indiquées. Par exemple, lors d'un filtrage par Géo, la liste des pays disponibles s'affiche.
      </td>
    </tr>
    <tr>
      <td><span id="field-selection"></span>
        Sélection des champs
      </td>
      <td>
        Les champs les plus importants sont présélectionnés. Vous pouvez ajouter / effacer des champs dans l'onglet **Champs du rapport.** Certains champs peuvent être inutiles dans certains types de rapport. Mais vous pourrez malgré tout les sélectionner. Nous faisons la présélection pour que vous puissiez obtenir des formats de rapport cohérents (colonnes).

        Exemple : sélectionner des champs liés à la fraude (Protect360) dans un rapport sur les événements in-app d’acquisition utilisateurs donnera des colonnes vides. Ces champs ne sont renseignés que dans le cas de rapports spécifiques à Protect360.
      </td>
    </tr>
    <tr>
      <td><span id="report-csv-field-order"></span>
        Ordre des champs du rapport (CSV)
      </td>
      <td>
        Les colonnes des rapports sont classées en fonction de l'ordre des champs. La suite de colonnes [contenues dans une feuille de calcul](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGYcMOgC5yy_82yn3DWd3ucLE5KtuTA72eJfvu5KVB9fFH_mYwzM3KpR_inQOnat-KzgVjuuvXa6_g/pub?output=xlsx) a des onglets séparés pour les options héritées et les options par défaut.

        | Paramètre | Sélection des champs possible | Remarques |
        | --- | --- | --- |
        | <span id="default"></span>Par défaut | Oui | * Les champs sélectionnés sont classés d’après le modèle AppsFlyer.<br />* Pour la suite, la sélection sera conservée. Les nouveaux champs seront ajoutés à droite des champs existants. |
        | <span id="alphabetical-az"></span>Alphabet (A-Z) | Oui | Les champs sélectionnés sont classés par ordre alphabétique (croissant). |
        | <span id="alphabetical-za"></span>Alphabet (Z-A) | Oui | Les champs sélectionnés sont classés par ordre alphabétique (décroissant). |
        | <span id="legacy"></span>Versions antérieures | Non | * Les champs sont classés selon la suite de colonnes dans les rapports conçus dans la version précédente de la page de données d'exportation.<br />* La sélection des champs est fixe et ne peut être modifiée.<br />* Les rapports varient d'un champ à l'autre en fonction du type de rapport. |
      </td>
    </tr>
  </tbody>
</Table>

> 📘 **Remarque**
>
> Si vous utilisez à la fois les filtres *agence* et *source média*, les filtres *source média* ne s'appliqueront pas aux agences non transparentes. Ce qui veut dire que pour les agences non transparentes, toutes les données seront incluses (et pas uniquement les données issues des sources média choisies dans les filtres).

| Filtre | Annonceur | Réseau publicitaire | Agence |
| --- | --- | --- | --- |
| Source média | Oui | Non | Oui |
| Période d'activité | Oui | Oui | Oui |
| Plage de dates d'installation | Oui | Oui | Oui |
| Agence | Oui | Non | Non |
| Géo (territoire/pays) | Oui | Oui | Oui |
| Événements in-app (disponibles pour les rapports d'événements in-app) | Oui | Non | Oui |

</Accordion>

## Marche à suivre

<div id="create-a-default-report" />

<Accordion title="Créer un rapport par défaut">

Vous pouvez créer un rapport avec les paramètres par défaut sans avoir à personnaliser ses champs ou filtres.

**Pour créer un rapport par défaut :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Exporter** > **Exporter les données brutes**.
2. Cliquez sur + **Nouveau rapport**
3. Passez la souris sur le type de rapport que vous souhaitez générer et cliquez sur **Créer.**
4. Sélectionnez **Générer maintenant** dans le menu déroulant.
5. Dans la fenêtre contextuelle, cliquez sur **Générer maintenant.** L’action peut prendre jusqu'à 10 minutes.
   * Pendant la génération du rapport, vous pouvez continuer à travailler, créer d’autres rapports, ou naviguer sur différentes pages.

**Les paramètres par défaut des filtres de rapport :**

| Filtre | Réglage par défaut |
| --- | --- |
| Dates d'activité | Les 7 derniers jours |
| Nombre maxi de lignes par fichier | 200 000 |
| Source média | Toutes les sources média |
| Agence | Toutes agences |
| Géo | Toutes les zones géo |

</Accordion>

<div id="create-a-custom-report" />

<Accordion title="Créer un rapport personnalisé">

Vous pouvez créer un rapport personnalisé en choisissant les filtres et champs qu’il contient.

**Pour créer un rapport personnalisé :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Exporter** > **Exporter les données brutes**.
2. Cliquez sur + **Nouveau rapport**
3. Passez la souris sur le type de rapport que vous souhaitez générer et cliquez sur **Créer.**
4. Sélectionnez **Personnaliser** dans le menu déroulant.
5. Configurez les filtres du rapport
   * **Dates d'activité :** Sélectionnez la période d’activité. Vous pouvez définir un jour précis, ou sélectionner parmi différentes options de type : personnalisé, hier, les 7 derniers jours, etc.
   * **Nombre maximum de lignes par fichier :** [Facultatif] définissez le nombre maxi de lignes qu'un fichier peut contenir. Sélectionnez 100, 200 000, 500 000 ou 1 million de lignes.
   * **Source média :** [Facultatif] seuls les événements attribués aux sources média sélectionnées seront inclus dans le rapport. Vous pouvez ajouter une source média à la liste en cliquant sur **Ajouter un élément.**
   * **Agence :** [Facultatif] seuls les événements attribués aux agences sélectionnées seront inclus dans le rapport. Vous pouvez ajouter une agence à la liste en cliquant sur **Ajouter un élément.**
   * **Géo :** [Facultatif] seuls les événements attribués aux zones géo sélectionnées seront inclus dans le rapport.
   * **Filtre propre à un type de rapport** : chaque type de rapport peut avoir son propre filtre pour lequel vous pouvez sélectionner un critère.
6. [Optionnel] : les rapports sont automatiquement remplis avec les champs requis. Vous pouvez ajouter ou supprimer un champ comme suit :
   1. Ouvrez l’onglet **Champs du rapport**, la liste des champs sélectionnés s'affiche. Vous ne pouvez pas modifier la sélection des champs obligatoires.
   2. Sélectionnez ou supprimez les champs selon vos besoins.
   3. [Facultatif] Définissez l’**ordre des champs du rapport (CSV)** pour créer la suite de colonnes.
   4. [Option] Cliquez sur **Restaurer les valeurs par défaut** si nécessaire.
7. Cliquez sur **Créer.**
   * La page **Mes rapports** s'affiche. Dans un premier temps, le statut indique que le rapport est en cours de génération.
   * L’action peut prendre jusqu'à 10 minutes.
   * Pendant la génération du rapport, vous pouvez continuer à travailler, créer d’autres rapports, ou naviguer sur différentes pages.

</Accordion>

<div id="download-report" />

<Accordion title="Télécharger le rapport">

**Pour télécharger un rapport :**

1. Vérifiez que vous êtes bien sur la page d'**exportation des données brutes**. Si ce n’est pas le cas, allez dans **Rapports** > **Exportation de données brutes.**
2. Cliquez sur ![DownloadIcon.png](https://files.readme.io/6c00f4922fc3a835a856d7fdf527aa32d2f50570710c1527b039f43a7acbba79-41225791763217.png) (télécharger), pour télécharger le rapport. Les rapports qui ont été générés sont téléchargeables pendant 7 jours.

</Accordion>

<div id="duplicate-and-edit-report-settings" />

<Accordion title="Dupliquer et modifier les paramètres d'un rapport">

**Pour dupliquer et modifier les paramètres d'un rapport :**

1. Vérifiez que vous êtes bien sur la page d'**exportation des données brutes**.
2. Cliquez sur ![Duplicate.png](https://files.readme.io/f745081f1bf0c4f5861e275a29048fe84e8020f8b3bf4ebe4ad6a8d9254ab4b5-41225784681233.png) pour dupliquer les paramètres du rapport et faire les modifications.
3. Cliquez sur **Créer**. Les rapports qui ont été générés sont disponibles pendant 7 jours.   
   * La page **Mes rapports** s'affiche. Dans un premier temps, le statut indique que le rapport est en cours de génération.
   * L’action peut prendre jusqu'à 10 minutes.
   * Pendant la génération du rapport, vous pouvez continuer à travailler, créer d’autres rapports, ou naviguer sur différentes pages.

</Accordion>

## Informations supplémentaires

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique | Remarques |
| --- | --- |
| Accès du réseau publicitaire | Oui |
| Autorisations de l'agence | Oui |
| Transparence de l'agence | Oui. Notez que si vous utilisez à la fois les filtres *agence* et *source média*, les filtres *source média* ne s'appliqueront pas aux agences non transparentes. Ce qui veut dire que pour les agences non transparentes, toutes les données sont incluses (pas uniquement les données issues des sources média filtrées). |
| Fuseau horaire propre à l'app | Oui |
| Devise propre à l'app | Oui |
| Limitations | Jusqu'à 1 million d'enregistrements par téléchargement |
| Données organiques | Disponible |
| Données non organiques | Disponible |
| Actualisation des données | Selon le rapport |
| Données historiques | Les 90 jours précédents |
| Accès des utilisateurs du compte | Utilisateurs ayant le <Anchor target="_blank" href="/marketers/fr/docs/user-management">rôle qui leur donne les bonnes autorisations</Anchor> |
| Envoi d’e-mail | Non pris en charge |
| Période d'installation | La période d'installation doit précéder la période d'activité. |
| Rapports de postbacks des données brutes | Les postbacks transmis aux partenaires suite à des événements attribués à des agences **non transparentes** ne sont pas inclus dans les rapports de postbacks des données brutes de l'annonceur. |

</Accordion>

<div id="field-sequence-templates" />

<Accordion title="Modèles de suite de champs">

Le paramètre *Ordre des champs du rapport* vous permet de définir l'ordre des colonnes dans les rapports et, dans certains cas, les champs eux-mêmes.

| Paramètre | Sélection des champs possible | Remarques |
| --- | --- | --- |
| <span id="default::b7bb6355"></span>Par défaut | Oui | <ul><li>Les champs sélectionnés sont classés d’après le modèle AppsFlyer.</li><li>Pour la suite, la sélection sera conservée. Les nouveaux champs seront ajoutés à droite des champs existants.</li></ul> |
| <span id="alphabetical-az::b08af6b3"></span>Alphabet (A-Z) | Oui | Les champs sélectionnés sont classés par ordre alphabétique. |
| <span id="alphabetical-za::f0b3beb8"></span>Alphabet (Z-A) | Oui | Les champs sélectionnés sont classés par ordre alphabétique inversé. |
| <span id="legacy::fb5fd8ec"></span>Versions antérieures | Non | <ul><li>Les champs sont classés selon la suite de colonnes dans les rapports conçus dans la version précédente de la page de données d'exportation.</li><li>La sélection des champs est fixe et ne peut être modifiée.</li><li>Les rapports varient d'un champ à l'autre en fonction du rapport généré.</li></ul> |

Cette [feuille de calcul](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGYcMOgC5yy_82yn3DWd3ucLE5KtuTA72eJfvu5KVB9fFH_mYwzM3KpR_inQOnat-KzgVjuuvXa6_g/pub?output=xlsx) contient un onglet Par défaut et un onglet Hérité. Chaque onglet affiche l’ordre des champs correspondant.

**Pour modifier l'ordre des champs :**

1. Dans l'onglet Champs du rapport, sélectionnez une option pour choisir l’**ordre des champs du rapport.**
2. Si besoin est, modifiez les champs sélectionnés en les sélectionnant ou désélectionnant.

</Accordion>

<div data-zendesk-anchors="h_01HA28AT6QRSG68NBFYHH5SQY8=raw-data-export-page-features-and-filter-options h_01HA28CJ4W692V6EVC7XTQEZG6=remarque procedures=marche-%C3%A0-suivre h_01HA28AT6Q9PV3M55C1YM3XN2E=marche-%C3%A0-suivre h_01HZY1HQ9AVH6Q9QAQB4SM1VPX=create-a-default-report h_01HZY1HQ9ACEMZ4N8WPYNHZQP7=create-a-custom-report h_01HA28AT6QV1XP4N952PAEGSSG=download-report h_01HA28AT6QFT88RHJ3M05MV3B3=duplicate-and-edit-report-settings additional-information=informations-suppl%C3%A9mentaires h_01HA28AT6Q4DXKCZ22R9XEN2RR=informations-suppl%C3%A9mentaires h_01HA28AT6Q6SE8CB3EEXFMAN0H=traits-and-limitations h_01HA28AT6RW8C99ZGEBTN5E44R=field-sequence-templates" />
