---
title: Data Clean Room - Travailler avec les sources
metadata:
  keywords:
    - Advertisers
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2022-03-27T10:58:23Z'
  edited_at: '2024-02-14T08:41:37Z'
  id: 5041487011601
  locale: fr
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/fr/articles/5041487011601
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** configurez les sources de données personnalisées que vous partagez avec la Data Clean Room (DCR) pour les associer aux données d'attribution et créer des rapports DCR.

## Introduction

De nombreux rapports DCR sont conçus pour faire correspondre vos données d'attribution avec les données de vos sources personnalisées. Cet article contient tout ce qu'il faut savoir pour utiliser vos sources personnalisées, ce qui inclut comment :

* [Formater les données sources](/docs/data-clean-room-working-with-sources#obligations-concernant-les-données-sources)
* [Créer la source](/docs/data-clean-room-working-with-sources#créer-une-source) dans la DCR
  * [Nommer la source](/docs/data-clean-room-working-with-sources#1-name-the-source)
  * [Indiquer l'emplacement](/docs/data-clean-room-working-with-sources#2-specify-the-source-location) où la DCR devra récupérer les données sources.
  * [Définir la structure](/docs/data-clean-room-working-with-sources#3-define-the-source-structure) de la source (en étiquetant les champs comme métrique, dimension et identifiant)
  * [Enregistrer la source](/docs/data-clean-room-working-with-sources#4-save-the-source)
* [Mettre à jour régulièrement les données sources](/docs/data-clean-room-working-with-sources#mettre-à-jour-les-sources-pour-déclencher-lédition-des-rapports) pour déclencher l'édition des rapports.
* [Travailler avec les sources existantes](/docs/data-clean-room-working-with-sources#travailler-avec-les-sources-existantes)

<div id="important" />

> 🚧 **Avant de commencer**
>
> Avant de créer des sources personnalisées, vous devez :
>
> * [Obligatoire] <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-setting-up-cloud-services">Définir les services cloud</Anchor> où la DCR devra récupérera les données. Deux types de services cloud sont pris en charge :
>   * **Entrepôts de données :** BigQuery et Snowflake
>   * **Compartiment de stockage dans le cloud :** Amazon S3 (AWS) et GCS
> * [Facultatif] <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-working-with-connections#creating-inbound-connections">Créer des connexions entrantes</Anchor> sur la plateforme AppsFlyer pour connecter ces services cloud à la DCR.
>   * Si ces connexions n'ont pas déjà été définies, vous serez invité à les configurer lors de la création de la source.

<div id="source-requirements" />

## Obligations concernant les données sources

Les sources doivent répondre à ces exigences afin d'éviter les erreurs au cours de leur création et lors du traitement des rapports.

<div id="data-format" />

<Accordion title="Format des données (valable pour toutes les sources)">

Les données contenues dans les sources doivent se conformer aux points suivants :

* **Date et heure :**
  * **Format :** aaaa-MMM-jj hh:mm:ss (*ex :* `2023-AVR-18 15:30:35`)
  * **Fuseau horaire :** UTC
* **Nombres :** 2 chiffres maxi après la virgule
* **Longueur de la chaîne :** 256 caractères maximum
* **Restrictions liées aux caractères :**
  * **Pour les noms de champs (en-têtes de colonnes) :** aucun espace ni caractère spécial
  * **Toutes les autres données :** aucune restriction (tous les caractères sont valides)

</Accordion>

<div id="table-columns" />

<Accordion title="Colonnes du tableau (uniquement pour les sources dans les entrepôts de données)">

En plus des données partagées en vue d'être traitées, les tableaux sources dans BigQuery ou Snowflake doivent inclure 2 autres colonnes, soit une pour la **date** et une pour la **version** :

* **Date :**
  * **En-tête de colonne :** `dt`
  * **Type de colonne :** date
  * **Format des données :** aaaa-mm-jj (*ex :* `2023-04-18`)
  * **Colonne supplémentaire :** les tableaux BigQuery doivent être <Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/partitioned-tables">séparés</Anchor> par cette colonne.
* **Version :**
  * **En-tête de colonne :** `v`
  * **Type de colonne :** chaîne
  * **Format des données :** nombre (ex : `1`, `2`, `3`, `10`)
  * **Important !** La nouvelle version d'un rapport est déclenchée à chaque fois que la DCR détecte une nouvelle valeur dans cette colonne. Pour garantir que votre rapport est bien complet, pensez à alimenter le tableau source avec un ensemble complet de données à chaque fois que la valeur de la colonne est modifiée.

</Accordion>

<div id="file-format" />

<Accordion title="Nom et format du fichier (concerne uniquement les sources dans les compartiments de stockage sur le cloud)">

Les fichiers sources stockés sur Amazon S3 ou GCS doivent suivre ces normes en matière de nom de fichier et de format :

* Le nom du fichier doit être conforme à la nomenclature utilisée dans la DCR ( <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">).</Anchor>
* Format CSV ou GZIP
  * Le fichier fondamental de la compression GZIP doit être un fichier CSV.
* Nombre de fichiers sources de données par dossier de données :
  * **CSV :** 1 maxi
  * **GZIP :** 1 fichier maxi en une seule partie. Les fichiers GZIP en plusieurs parties sont pris en charge lorsqu'ils sont nommés : `nom_fichier_part01.gzip`, `nom_fichier_part02.gzip`, etc.

</Accordion>

<div id="creating-a-source" />

## Créer une source

Pour créer une source il faut suivre **toutes les étapes décrites ci-dessous.** Chaque étape apparait dans un onglet pour simplifier la lecture.

**Suivez ces instructions pour créer une source :**

<div id="1-name-the-source" />

<Accordion title="#1 : Nommer la source">

1. Allez dans l'onglet **Sources** de la **Data Clean Room.**
2. Cliquez sur le bouton **+ Nouvelle source**.  
   Une page **Nouvelle source** s'ouvre.
3. Saisissez le nom de la source en haut à gauche de la page.
   * Vous pouvez choisir n'importe quel nom pourvu qu'il vous aide à identifier la source sur la plateforme DCR. Il ne doit pas forcément correspondre au nom du fichier.
   * **Important !** Veillez à ce que le nom de la source ne soit pas utilisé pour une autre source sur votre compte, ou vous ne pourrez pas [enregistrer la source](/docs/data-clean-room-working-with-sources#4-save-the-source).
   * Obligations pour le nom de la source :
     * Longueur : 2-80 caractères
     * Caractères valides :
       * lettres `(A-Z, a-z)`
       * les chiffres `(0-9)` *ne peuvent pas être le premier caractère d'un nom ;*
     * Caractères non valides :
       * espaces
       * tous les autres symboles ou caractères spéciaux

</Accordion>

<div id="2-specify-the-source-location" />

<Accordion title="#2 : Indiquer l'emplacement de la source">

**Pour définir l'emplacement de la source :**

1. Sélectionnez la <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-setting-up-cloud-services#overview">connexion</Anchor> où la source sera (ou a été) créée.
   * Si aucune connexion n'a été définie dans votre compte, une boîte de dialogue **Nouvelle connexion** s'ouvre et vous invite à en créer une. Suivez <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-working-with-connections#complete-the-connection">ces instructions</Anchor> pour la créer.
   * Si vous avez déjà des connexions mais que vous souhaitez en utiliser une nouvelle, cliquez sur le bouton ![dcr_new_connection_button.png](https://files.readme.io/0a6766bcb5deef0b2264b372592b82485cc59b11e454cdcbd4a1718de4df951d-14989643499153.png) pour ouvrir la boîte de dialogue **Nouvelle connexion**. Suivez <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-working-with-connections#complete-the-connection">ces instructions</Anchor> pour la créer.
2. Suivez les instructions ci-dessous en fonction de là où se trouvent les données de votre source.

<div id="source-locations-in-bigquery" />

#### Emplacements des sources dans BigQuery

**Pour terminer la définition de l'emplacement de la source pour les sources BigQuery :**

1. Sélectionnez l'ensemble de données où se trouve le tableau source.
2. Sélectionnez le tableau où se trouvent les données sources.

Les listes où vous sélectionnez ces éléments contiennent les ensembles de données et les tableaux disponibles dans le projet BigQuery que vous avez défini en créant la connexion.

<div id="source-locations-in-snowflake" />

#### Emplacements de la source dans Snowflake

**Pour terminer la définition de l'emplacement de la source pour les sources Snowflake :**

1. Sélectionnez le partage qui contient les données sources.
2. Sélectionnez le schéma où se trouve le tableau source.
3. Sélectionnez le tableau où se trouvent les données sources.

Les listes où vous sélectionnez ces éléments contiennent les partages, schémas et tableaux disponibles dans le projet Snowflake que vous avez défini en créant la connexion.

<div id="source-locations-in-cloud-storage-buckets" />

#### Emplacements des sources dans les compartiments de stockage sur le cloud

Les emplacements des sources dans Amazon S3 ou GCS correspondent à l'espace de stockage sur le cloud défini dans la connexion, ainsi que du chemin d'accès au dossier racine où la DCR lit le fichier source à chaque mise à jour.

Une fois que vous avez spécifié la connexion, AppsFlyer peut générer automatiquement le chemin du dossier racine lors de la création de la source.

* Autorisez AppsFlyer à générer les dossiers facilite le processus. Cependant, vous pouvez choisir de les créer manuellement, en suivant <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-setting-up-cloud-services">ces instructions</Anchor>.

Si AppsFlyer génère les dossiers, la seule information supplémentaire requise est le nom que vous souhaitez donner au **dossier source** (le dossier de premier niveau où vous mettez à jour la source à chaque fois que vous l'utilisez pour éditer une nouvelle version de rapport.) Vous pouvez également indiquer si vous souhaitez que le dossier source soit créé dans un dossier parent - souvent nommé **input.**

**Pour terminer la définition de l'emplacement de la source dans un compartiment sur le cloud, saisissez le nom du dossier source.**

* Par défaut, le nom du dossier source affiché :
  * Se base sur le nom [que vous avez donné à la source](/docs/data-clean-room-working-with-sources#1-name-the-source). Vous pouvez modifier le nom du dossier à condition qu'il soit suive la <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">nomenclature de la DCR.</Anchor>
  * Indique qu'il sera généré dans un dossier parent nommé **input.** Ce dossier sert de dossier parent pour toutes les sources que vous importez dans le DCR.
    * Le dossier **input** n'est pas obligatoire et vous pouvez le supprimer, ou le nommer différemment (tant que vous suivez la <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">nomenclature de la DCR.</Anchor>
    * Bien que ce dossier ne soit pas obligatoire, l'existence d'un dossier **input** (ou d'un dossier équivalent avec un nom différent) est souvent conseillé. Il est aussi fortement recommandé d'utiliser le même espace de stockage sur le cloud pour importer les fichiers de données (input) et recevoir des rapports (output).

<div id="important-1" />

> 🚧 **Important !**
>
> Si vous avez créé manuellement le chemin d'accès au dossier, vérifiez que la connexion et le chemin d'accès que vous indiquez dans la section **Emplacement de la source** lui correspondent.

</Accordion>

<div id="3-define-the-source-structure" />

<Accordion title="#3 : Définir la structure de la source">

Pour toutes les sources que vous partagez avec la DCR en vue d'être traitées, AppsFlyer doit savoir comment chaque champ de données doit être utilisé pour créer les rapports. Définir la structure de la source se fait comme suit :

* [Chargement des champs source](/docs/data-clean-room-working-with-sources#chargement-des-champs-source)
* [Classement de chaque champ](/docs/data-clean-room-working-with-sources#classer-les-champs-par-catégorie) (colonne) dans l'une des catégories suivantes :
  * **Identifiant :** champ qui identifie un utilisateur unique de l'application (ex. CUID, ID AppsFlyer, etc.).
    * La mission principale des ID dans une DCR est de relier les sources de données afin que les données de niveau utilisateur correspondantes puissent être utilisées.
  * **Dimension :** attribut permettant de classer les utilisateurs de l'application (ex. géographie, date d'installation, campagne, etc.)
  * **Métrique :** les données numériques que vous avez collectées au sujet d'un utilisateur d'app (ex. revenu, nombre d'ouvertures de l'appl, LTV, etc.)
    * Un champ de données défini comme étant une métrique ne peut contenir **que des valeurs numériques.**

<div id="loading-source-fields" />

#### Chargement des champs source

Chargez les champs source en suivant les instructions ci-dessous :

**Sources de l'entrepôt de données**

Pour charger les champs depuis une source située dans un entrepôt de données (BigQuery ou Snowflake), cliquez sur le bouton  ![dcr_load_fields_from_source.png](https://files.readme.io/667761e044a45e9a63bf904ada0ba07917014b5b446379213742510278b5a2dd-14986195290897.png).

<div id="important-2" />

> 🚧 **Important !**
>
> Si le tableau source sélectionné ne contient pas les colonnes de date et de version [requises](/docs/data-clean-room-working-with-sources#table-columns), vous recevrez un message d'erreur.

**Sources de compartiment de stockage sur le cloud**

Pour charger des champs à partir d'une source située dans un compartiment de stockage sur le cloud (Amazon S3 ou GCS), vous devez importer un fichier source type.

Pour définir la structure de la source :

* Vous pouvez importer une version type de la source depuis un fichier local.
  * Si vous sélectionnez cette option, AppsFlyer créera toujours le chemin du dossier source automatiquement.

                                                                - ou -

* Vous pouvez importer une version type du fichier source directement depuis sa connexion.
  * Si vous définissez cette option, vous devrez choisir entre :
    * Permettre à AppsFlyer de créer automatiquement la structure du dossier source, OU
    * Créer manuellement la structure du dossier source

**Pour importer le fichier source de votre modèle, suivez les instructions dans l'onglet correspondant :**

<Tabs>
<Tab title="Fichier local">

1. Dans la section **Structure de la source**, cliquez sur le bouton <Image alt="DCR_load_fields_from_file.png" src="https://files.readme.io/544a069a05fd1afed0b4d9935ccea11dafae6afc78c09491b27809dd52daa373-11240944795025.png" width="125px" />.
2. Dans la fenêtre qui s'ouvre, sélectionnez **Importer un fichier local.**
3. Indiquez le fichier CSV ou GZIP que vous souhaitez importer, puis cliquez sur OK.

</Tab>

<Tab title="Connexion (création automatique)">

**Pour charger le fichier depuis sa connexion et permettre à AppsFlyer de créer la structure du dossier source :**

1. Dans la section **Structure de la source**, cliquez sur le bouton <Image alt="DCR_load_fields_from_file.png" src="https://files.readme.io/544a069a05fd1afed0b4d9935ccea11dafae6afc78c09491b27809dd52daa373-11240944795025.png" width="125px" />.
2. Dans la fenêtre qui s'ouvre, sélectionnez **Charger depuis une connexion.**
3. Cliquez sur le lien **Générer les dossiers**.
   * AppsFlyer crée automatiquement la structure du dossier ainsi que le dossier source requis (sur la connexion que vous avez définie, avec le nom de dossier source que vous avez choisi).
4. Une fois la structure du dossier source créée, un message de confirmation s'affiche, avec un lien vers le dossier source. Cliquez sur le lien pour importer votre fichier type dans le dossier source.
5. Une fois l'importation du fichier terminée, cliquez sur **OK.**

</Tab>

<Tab title="Connexion (création manuelle)">

**Pour importer le fichier source à partir d'une structure que vous avez créée manuellement :**

1. Dans la section **Structure de la source**, cliquez sur le bouton <Image alt="DCR_load_fields_from_file.png" src="https://files.readme.io/544a069a05fd1afed0b4d9935ccea11dafae6afc78c09491b27809dd52daa373-11240944795025.png" width="125px" />.
2. Dans la fenêtre qui s'ouvre, sélectionnez **Charger depuis une connexion.**
3. **NE CLIQUEZ PAS** sur **Générer les dossiers.** À la place, importez le fichier directement dans le dossier source que vous avez créé.
4. Une fois l'importation du fichier terminée, cliquez sur **OK.**

</Tab>
</Tabs>

<div id="categorize-fields" />

#### Classer les champs par catégorie

Après avoir importé les champs, AppsFlyer analyse le fichier, puis la liste de tous les champs de données (colonnes) s'affiche dans les **Champs disponibles**.

**Pour classer les champs par catégorie :**

1. Sélectionnez un ou plusieurs champs dans la liste **Champs disponibles** sur la gauche, puis utilisez les boutons au milieu de l'écran pour les mettre dans la catégorie [identifiant, dimension ou métrique](/docs/data-clean-room-working-with-sources#3-define-the-source-structure).
   * Une fois que vous avez classé un champ dans une catégorie, il s'affiche dans la liste de la catégorie correspondante, à droite de l'écran.
   * Vous pouvez utiliser la barre de recherche pour localiser les champs dans les listes.
   * Pour supprimer un champ d'une catégorie où il a été classé, sélectionnez-le dans la liste de la catégorie en question et utilisez le bouton **Supprimer** pour qu'il retourne dans la liste **Champs disponibles**.
2. Répétez l'opération jusqu'à ce qu'au classement de tous les champs que vous souhaitez inclure dans les rapports DCR.
   * Il n'est pas nécessaire de classer chaque champ dans la liste **Champs disponibles**. Toutefois, un champ doit forcément être catégorisé pour pouvoir être utilisé dans un rapport.
3. Si vous modifiez la source avant [d'enregistrer la source](/docs/data-clean-room-working-with-sources#4-save-the-source), mais que vous souhaitez utiliser les champs des données source modifiées, cliquez sur le lien **Charger à nouveau les champs**, en bas de la liste **Champs disponibles**.
   * Notez qu'en chargeant à nouveau une source vous écraserez les noms des champs dans la liste des champs disponibles. Tous les champs précédemment catégorisés resteront dans les listes **Identifiant,** **Dimension,** ou **Métrique**.
   * Si un champ déjà catégorisé n'est pas inclus dans les données source à nouveau chargées, il s'affichera toujours dans la liste de sa catégorie, mais il sera marqué d'une icône d'erreur.

> 📘 **Note**
>
> [Si vous décidez d'utiliser d'autres champs de cette source après l'avoir enregistrée, vous pouvez le faire en modifiant la structure de la source](/docs/data-clean-room-working-with-sources#editing-the-source-structure).

</Accordion>

<div id="4-save-the-source" />

<Accordion title="#4 : Enregistrer la source">

**Pour enregistrer la source :**

1. [Facultatif] Cliquez sur <Image alt="DCR_test_source.png" src="https://files.readme.io/c8d2bb2e7062d062a2ed7ddb84472c5acd02fc93b178b2299515b2374a3ad3e3-11240865384849.png" width="43px" /> pour vérifier les erreurs de format ou de validité des champs source.
2. Cliquez sur **Enregistrer** pour enregistrer la source.

   La source est créée et un message de confirmation s'affiche.

   * Si vous avez importé la source depuis un fichier local, l'enregistrement de la source déclenche la création automatique de la structure du dossier, et le message de confirmation qui s'affiche contient un lien vers le dossier source.

   La nouvelle source apparaît dans la liste de toutes les sources existantes dans l'onglet **Sources** de la Data Clean Room.

</Accordion>

<div id="updating-sources-to-trigger-report-processing" />

## Mettre à jour les sources pour déclencher l'édition des rapports

Lorsque vous souhaitez que AppsFlyer traite un fichier source de données et sorte le rapport associé, vous devez importer une nouvelle version du fichier dans le dossier source, à l'intérieur d'une arborescence de sous-dossiers qui indiquent la date et le numéro de version (auquel s'ajoute une autre sous-dossier qui permet à AppsFlyer de savoir où se trouvent les données).

AppsFlyer recherche en permanence les nouvelles versions des fichiers sources pour **le jour en cours et les 2 jours précédents.** La nouvelle version d'un rapport est lancée à chaque fois que de nouvelles versions des fichiers sources sont trouvées (y compris les fichiers [\_SUCCESS](/docs/data-clean-room-working-with-sources#_success-files), comme expliqué ci-dessous).

<div id="nested-subfolders-for-each-date-and-version" />

<Accordion title="Arborescence de sous-dossiers pour chaque date et version">

La structure des sous-dossiers est la suivante :

* Dans le dossier source --> 1 sous-dossier pour chaque date ("dossier date")
  * **Format :** `dt=yyyy-mm-dd/`
  * **Exemple :** `dt=2022-12-15/`
* Dans chaque dossier de date --> 1 sous-dossier pour chaque version sur cette date ("dossier version")
  * **Format :** `v=n/`
  * **Exemple :** `v=1/`
  * **Remarque :** Le dossier version est requis même si vous n'importez le fichier qu'une fois par jour.
* Dans chaque dossier de version --> 1 sous-dossier pour indiquer l'emplacement des données ("folder données")
  * **Format :** `data/`
  * Le dossier données correspond à l'emplacement où le fichier source est importé.

Dans la plupart des cas, vous utilisez des appels d'API ou d'autres méthodes programmatiques pour créer automatiquement les dossiers date/version/données à chaque fois que le fichier source de données est importé. Pour plus d'informations, consultez la section API de votre service cloud : <Anchor target="_blank" href="https://docs.aws.amazon.com/AmazonS3/latest/API/Welcome.html">AWS</Anchor>, <Anchor target="_blank" href="https://cloud.google.com/storage/docs/reference/libraries">GCS</Anchor>.

</Accordion>

<div id="_success-files" />

<Accordion title="Fichiers _SUCCESS">

Une fois que l'importation d'un fichier source dans le dossier de données est terminé, un fichier vide nommé `_SUCCESS` doit être importé dans le dossier **version**. Cette action signale à AppsFlyer qu'un nouveau fichier à traiter est disponible. Dans la plupart des cas, vous utilisez un script API pour générer et importer automatiquement ce fichier.

**Important !** Le fichier `_SUCCESS` doit être importé dans le dossier **version**, en dehors du dossier données.

Le nom du fichier \_SUCCESS :

* Doit être écrit tout en MAJUSCULE
* Doit être précédé d'un tiret du bas `(_)`
* Ne doit pas avoir d'extension de fichier

Pour les fichiers GZIP en plusieurs parties :

* Un seul fichier `_SUCCESS` doit être importé pour toutes les parties du fichier.
* Le fichier `_SUCCESS` ne doit être importé qu'une fois que toutes les parties du fichier ont été importées.

</Accordion>

<div id="example-after-uploading-files" />

<Accordion title="Exemple (après importation des fichiers)">

Après avoir importé des fichiers sources pendant deux jours (et créé par programme les dossiers date/version/données et les fichiers `_SUCCESS`), la structure de votre compartiment/dossier doit être celle-ci :

<Image alt="dcr_file_structure_after_uploads.png" src="https://files.readme.io/f6e753cdf8389c0b99cad9cbf1a06261473ef87ce6f840a21ab8d9ccea20aed4-11420299723665.png" width="308px" />

</Accordion>

<div id="working-with-existing-sources" />

## Travailler avec les sources existantes

Il y a différentes manières de travailler avec des sources existantes. Vous effectuez ces opérations depuis l'onglet **Sources** de la DCR :

* [Modification du nom de la source](/docs/data-clean-room-working-with-sources#editing-the-source-name)
* [Modification de la structure de la source](/docs/data-clean-room-working-with-sources#editing-the-source-structure)
* [Suppression d'une source](/docs/data-clean-room-working-with-sources#deleting-a-source) (si elle n'est pas utilisée pour un rapport)

<div id="editing-the-source-name" />

<Accordion title="Modification du nom de la source">

Pour modifier le nom de la source :

1. Allez dans l'onglet **Sources** de la **Data Clean Room.**
2. Dans la liste des sources, survolez la ligne de la source à modifier.
3. Cliquez sur le bouton d'édition ![edit_button.png](https://files.readme.io/aeb81045ac5e49107cfb1e6cb0b49d5184ea1d70a20e3c58f684bc44f6e25c66-5366594803473.png) à droite de la ligne.
4. Sur la page **Modifier la source**, modifiez le nom de la source.
5. Cliquez sur le bouton **Enregistrer** pour enregistrer la source avec le nouveau nom, ou sur **Annuler**  si vous souhaitez annuler vos modifications.

</Accordion>

<div id="editing-the-source-structure" />

<Accordion title="Modification de la structure de la source">

Pour modifier la structure de la source :

1. Allez dans l'onglet **Sources** de la **Data Clean Room.**
2. Dans la liste des sources, survolez la ligne de la source à modifier.
3. Cliquez sur le bouton d'édition ![edit_button.png](https://files.readme.io/aeb81045ac5e49107cfb1e6cb0b49d5184ea1d70a20e3c58f684bc44f6e25c66-5366594803473.png) à droite de la ligne.
4. Sur la page **Modifier la source**, les champs précédemment classés dans la catégorie [identifiant, dimension ou métrique](/docs/data-clean-room-working-with-sources#3-define-the-source-structure), s'affichent dans la nouvelle catégorie à droite de l'écran.
5. Vous pouvez déplacer un champ précédemment classé dans une nouvelle catégorie sans avoir à charger à nouveau les champs du fichier source. Pour ce faire :
   1. Tout d'abord, sélectionnez-le dans la liste de la catégorie en question et utilisez le bouton **Supprimer** pour qu'il retourne dans la liste **Champs disponibles**.
   2. Ensuite, sélectionnez-le dans la liste **Champs disponibles** et utilisez les boutons au milieu de l'écran pour le classer dans la catégorie identifiant, dimension ou métrique.
6. Pour travailler avec des rubriques du fichier source qui n'ont pas encore été catégorisées, il faut les charger à nouveau depuis l'emplacement de la source ou un fichier local. Accédez à cette action en cliquant sur le lien **Charger à nouveau les champs** au bas de la liste **Champs disponibles**.
7. AppsFlyer analyse le fichier, puis la liste de tous les champs de données (colonnes) qui n'ont pas encore été classés par catégorie s'affiche dans les **Champs disponibles**.
   * Les champs précédemment classés dans la catégorie identifiant, dimension ou métrique, s'affichent toujours dans la bonne catégorie à droite de l'écran.
   * Si un champ déjà catégorisé n'est pas inclus dans le fichier de la source à nouveau chargée, il s'affichera toujours dans la bonne catégorie, mais il sera marqué d'une icône d'erreur.
8. Sélectionnez un ou plusieurs champs dans la liste **Champs disponibles** sur la gauche, puis utilisez les boutons au milieu de l'écran pour les mettre dans la catégorie identifiant, dimension ou métrique.
9. Une fois que vous avez effectué toutes les modifications nécessaires, cliquez sur le bouton **Enregistrer** pour enregistrer la source avec la structure mise à jour, ou choisissez **Annuler** pour annuler vos modifications.

<div id="important-3" />

> 🚧 **Important !**
>
> N'oubliez pas d'apporter les modifications pour que la nouvelle structure de la source apparaisse dans tous les rapports qui utilisent cette source :
>
> * Les champs supprimés, non classés par catégorie ou qui ont changé de catégorie sont automatiquement supprimés de tous les rapports où ils sont utilisés.
> * Les champs nouvellement ajoutés ou catégorisés ne sont pas automatiquement inclus dans les rapports tant que vous ne modifiez pas les définitions des rapports pour les intégrer.

</Accordion>

<div id="deleting-a-source" />

<Accordion title="Supprimer une source">

1. Allez dans l'onglet **Sources** de la **Data Clean Room.**
2. Dans la liste des sources, survolez la ligne de la source à supprimer.
3. Cliquez sur le bouton de suppression ![delete_button.png](https://files.readme.io/dbdbc085f6b7b5c2143c14494d1694fad5a3902ed57f8b34ded2144260164716-5367408938513.png) à droite de la ligne.
4. Dans la boîte de dialogue, confirmez la suppression de la source.
   * Vous ne pouvez pas supprimer une source qui est utilisée par un rapport. Si vous le faites, un message liste les rapports qui utilisent la source. Pour supprimer la source, vous pouvez au choix :
     * Supprimer les rapports qui l'utilisent, ou bien
     * Supprimer les champs sources des définitions de rapports qui l'utilisent.

</Accordion>

<div id="reference" />

## Référence

<div id="manually-creating-a-folder-structure" />

<Accordion title="Création manuelle d'une structure de dossiers pour les compartiments de stockage (si vous choisissez de le faire manuellement)">

En général, il est plus facile d'autoriser AppsFlyer à générer automatiquement la structure d'un dossier lors de la création de la source. Toutefois, si vous souhaitez créer ces dossiers manuellement, vous pouvez procéder comme suit.

<div id="create-a-dcr-key-folder" />

#### Créer un dossier clé DCR

Pour garantir une sécurité maximale, le premier dossier situé dans le compartiment (le dossier «DCR key») doit porter le nom de la **clé DCR** composée de 8 caractères alphanumériques et attribuée à votre compte (ex. `01bcc5fb`). *Notez que ce mot de passe est différent de tout autre mot de passe ou clé associé à votre compte AppsFlyer.*

Le dossier de la clé DCR est généralement créé manuellement via l'interface du service cloud que vous avez choisi.

**Pour obtenir la clé DCR de votre compte, cliquez sur le bouton Clé DCR en haut de la page principale DCR.**

[![dcr_key_button.png](https://files.readme.io/8d02c129ce45b19b28523419e43ec8227a9179e3bafb2b84c0a523b247061c19-16571022734353.png)](https://files.readme.io/8d02c129ce45b19b28523419e43ec8227a9179e3bafb2b84c0a523b247061c19-16571022734353.png)

Après avoir créé le dossier de la clé DCR, la structure de votre compartiment/dossier sera celle-ci :

<Image alt="dcr_file_structure_dcr_key_folder.png" src="https://files.readme.io/a57ba8076a2af5ef1f5a8339ac6b24e1ab6f8ff60956013a0a6547320a13072f-16571304308497.png" width="308px" />

<div id="top-level-input-folder" />

#### Dossier d'entrée de premier niveau

Bien que cela ne soit pas obligatoire, le mieux consiste à créer un dossier d'entrée de premier niveau directement dans le dossier de la clé DCR. Ce dossier sera dédié aux fichiers que vous importez dans la DCR.

Le dossier d'entrée de premier niveau est généralement créé manuellement via l'interface du service cloud que vous avez choisi.

* Nous vous recommandons cette pratique si vous utilisez le même espace de stockage sur le cloud pour importer les fichiers de données (input) et recevoir des rapports (output).
* Vous pouvez donner n'importe quel nom au dossier, à condition qu'il soit suive la <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">nomenclature de la DCR.</Anchor> Pour faciliter son identification, il est généralement nommé `input/`.

Après avoir créé le dossier d'entrée de premier niveau, la structure de votre compartiment/dossier sera celle-ci :

<Image alt="dcr_file_structure_input_folder.png" src="https://files.readme.io/cb7249ee0cbc0b4721c701f7d735c73eb7acc0a2a9e73de102b5a5ec9a6a79fd-16571312292753.png" width="308px" />

<div id="second-level-folder-for-each-data-source" />

#### Dossier de second niveau pour chaque source de données

Vous pouvez régulièrement importer différents fichiers de sources de données vers la DCR pour qu'elles soient traitées. Chacune de ces sources de données doit se voir attribuer un dossier distinct («dossier source de données»).

Par exemple, si vous prévoyez d'envoyer chaque jour deux fichiers à la DCR pour traitement : *BI-data.csv* et *CRM-data.gzip*, vous devez attribuer un dossier à chacune de ces sources de données. Vous pouvez choisir d'appeler ces dossiers `BI-data/` et `CRM-data/`.

Les dossiers de source de données sont généralement créés manuellement via l'interface du service cloud que vous avez choisi.

Après avoir créé 2 dossiers de source de données, la structure de votre compartiment/dossier sera celle-ci :

<Image alt="dcr_file_structure_source_folders.png" src="https://files.readme.io/f4624a213b79978d8ec080551649fae72d04d2f58a78344fc9df74a859881549-16571312297361.png" width="307px" />

Dans chaque dossier de source de données, [des sous-dossiers classés par date et par version](/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version) doivent être créés à chaque mise à jour de la source.

</Accordion>

<div data-zendesk-anchors="h_01HPKB2ERNRQG73AFA0X7XEDEF=introduction h_01HPKB2ERPGD2PS4JBSDGYW3MC=avant-de-commencer source-format=obligations-concernant-les-donn%C3%A9es-sources h_01HPKB2ERPANE0CAXFP9RG5YEH=obligations-concernant-les-donn%C3%A9es-sources h_01HPKB2ERPQ787V0PAABP7Q2YY=data-format h_01HPKB2ERPJ5PVQ2QM5XCYZE0D=table-columns h_01HPKB2ERPWZFZN2DSCHWNXKXX=file-format creating-a-source=cr%C3%A9er-une-source h_01HPKB2ERPX2T413N3T93YBBZB=cr%C3%A9er-une-source h_01HPKB2ERPQMT0NKTE5NN40KG4=1-name-the-source h_01HPKB2ERQWDMYBEPDZY17T9PG=2-specify-the-source-location source-locations-in-bigquery=emplacements-des-sources-dans-bigquery h_01HPKB2ERQ28JQ2CK16RYZ38G6=emplacements-des-sources-dans-bigquery source-locations-in-snowflake=emplacements-de-la-source-dans-snowflake h_01HPKB2ERQWFGF8MN8ZYAXWC87=emplacements-de-la-source-dans-snowflake source-locations-in-cloud-storage-buckets=emplacements-des-sources-dans-les-compartiments-de-stockage-sur-le-cloud h_01HPKB2ERQZT3Y6GNZ2WWWM0M7=emplacements-des-sources-dans-les-compartiments-de-stockage-sur-le-cloud h_01HPKB2ERQK2HFDATGKV0X7GCG=important- h_01HPKB2ERQ40VTVZA5DGNR907G=3-define-the-source-structure loading-source-fields=chargement-des-champs-source h_01HPKB2ERQTJPGG68FSEBHVVJA=chargement-des-champs-source h_01HPKB2ERRZNPYVVD8GHD7PBPE=important--1 categorize-fields=classer-les-champs-par-cat%C3%A9gorie h_01HPKB2ERSYCFE1EYTCK550VTK=classer-les-champs-par-cat%C3%A9gorie h_01HPKB2ERSNT8Y9QPN03HJKHCD=note h_01HPKB2ERS55YGWY3RMRPR02Y4=4-save-the-source uploading-source-files-to-trigger-report-processing=mettre-%C3%A0-jour-les-sources-pour-d%C3%A9clencher-l%C3%A9dition-des-rapports h_01HPKB2ERSCPAPB6WE3354ECW9=mettre-%C3%A0-jour-les-sources-pour-d%C3%A9clencher-l%C3%A9dition-des-rapports h_01HPKB2ERSEVBTS3DR2TB6Y1AQ=nested-subfolders-for-each-date-and-version h_01HPKB2ERSJ9KNDK6CEBRQB65C=_success-files h_01HPKB2ERSJKGVE61T6J9HXTCK=example-after-uploading-files working-with-existing-sources=travailler-avec-les-sources-existantes h_01HPKB2ERS5PK2P2XTC4ZMPCMC=travailler-avec-les-sources-existantes h_01HPKB2ERTC48MGS0BM5SDR6XV=editing-the-source-name h_01HPKB2ERTS6DEQX0KP0EQTGSP=editing-the-source-structure h_01HPKB2ERTYP6BFAESN3MHZSQG=important--2 h_01HPKB2ERVGJYJ9KW1RGX24CGV=deleting-a-source reference=r%C3%A9f%C3%A9rence h_01HPKB2ERV1KK3J8YX918GCF3M=r%C3%A9f%C3%A9rence h_01HPKB2ERVZ88MJ35JC66YDPAB=manually-creating-a-folder-structure creating-a-dcr-key-folder=cr%C3%A9er-un-dossier-cl%C3%A9-dcr h_01HPKB2ERV7MQJ9CK44T92GK2G=cr%C3%A9er-un-dossier-cl%C3%A9-dcr toplevel-input-folder=dossier-dentr%C3%A9e-de-premier-niveau h_01HPKB2ERVPG4R9FHWZPQ8TCZQ=dossier-dentr%C3%A9e-de-premier-niveau secondlevel-folder-for-each-data-source=dossier-de-second-niveau-pour-chaque-source-de-donn%C3%A9es h_01HPKB2ERVVFMP81RE8ATZ6SZ8=dossier-de-second-niveau-pour-chaque-source-de-donn%C3%A9es" />
