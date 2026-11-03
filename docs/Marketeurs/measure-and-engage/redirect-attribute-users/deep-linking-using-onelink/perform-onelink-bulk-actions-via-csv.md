---
title: Groupe de liens
metadata:
  keywords:
    - Marketers
    - bulk
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2023-04-13T11:31:43Z'
  edited_at: '2023-12-27T02:41:10Z'
  id: 14511403892369
  locale: fr
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/fr/articles/14511403892369
---
> **En bref :** la page des groupes de liens OneLink vous permet de créer instantanément un grand nombre de liens personnalisés OneLink et de les afficher à un seul endroit pour une utilisation ultérieure.

Les groupes de liens vous permettent de créer et d'afficher des liens créés en groupes. Ces groupes de liens sont regroupés dans une collection qui vous permet d'effectuer des actions sur l'ensemble de la collection, notamment l'ajout de nouveaux liens ou leur téléchargement.

## Mise en route

1. Dans AppsFlyer, allez dans **Expériences et Deep Linking** > **Groupes de liens OneLink**.
2. Vous verrez une page d'introduction avec l'un des boutons suivants :
   1. **Démarrer** - (envoyer pour créer votre première collection).
   2. **Créer un template OneLink** - Un template OneLink est nécessaire pour créer une collection. Voir <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template">Templates OneLink</Anchor>.
   3. **Mise à niveau** - Les groupes de liens ne sont pas disponibles avec votre package actuel. Contactez votre CSM ou écrivez à [hello@appsflyer.com](mailto:hello@appsflyer.com) pour obtenir une mise à niveau.

## Créer votre première collection

1. Cliquez sur **Démarrer.**
2. Saisissez un nom pour votre collection.  
   Choisissez un nom qui reflète l'objectif de votre collection pour l'identifier plus facilement par la suite.
3. Sélectionnez un template OneLink Remarque : tous les liens de la collection seront basés sur ce modèle.
4. Cliquez sur **Enregistrer et continuer.**
5. Importez votre fichier CSV. Vous pouvez utiliser l'exemple suivant <Anchor target="_blank" href="https://cdn.appsflyer.com/onelink-bulk-links-mgmt/sample_file.csv">Exemple de CSV</Anchor> comme guide.  
   Voir [Format de téléchargement](/docs/perform-onelink-bulk-actions-via-csv#upload-format) pour vous assurer que votre fichier CSV est compatible et qu'il s'exporte avec succès. Une fois que le fichier CSV est exporté, il est validé. S'il y a des lignes non valides, un rapport de validité CSV sera disponible au téléchargement pour vous aider à corriger votre fichier. Suivez les instructions de l'interface utilisateur et téléchargez un fichier corrigé.
6. Cliquez sur **Créer une collection.**

## Gestion des groupes de liens avec des collections

Les groupes de liens sont gérés dans des collections.

* En haut de la page, le widget **Utilisation de groupes de liens ce mois-ci** indique le nombre de demandes de liens  (ce qui inclut les créations et les mises à jour de liens) sur le quota mensuel pour le mois en cours.
  * Actuellement, la limite par défaut est fixée à 20 000 créations de liens par mois.
* La section **Collections** vous permet de créer une nouvelle collection et d'effectuer d'autres actions sur vos collections de liens actuelles.
* Si vous avez plus de sept collections, vous pouvez effectuer des recherches et filtrer votre liste de collections.

## Autres actions

Voici les autres actions qui peuvent être effectuées sur une collection :

<div id="creating-a-new-collection" />

<Accordion title="Créer une nouvelle collection">

La création d'une nouvelle collection est possible lorsque de [l'utilisation mensuelle](/docs/perform-onelink-bulk-actions-via-csv#gestion-des-groupes-de-liens-avec-des-collections) n'a pas été dépassée.

1. Cliquez sur **Nouvelle connexion**.
2. Suivez les instructions.
   1. Le processus suit les mêmes étapes que [Créer votre première collection](/docs/perform-onelink-bulk-actions-via-csv#créer-votre-première-collection).

</Accordion>

<div id="downloading-a-collection" />

<Accordion title="Télécharger une collection">

L'option de téléchargement est disponible dans les cas suivants :

* Il existe des liens actifs dans cette collection.
* Vous disposez d'autorisations d'accès à au moins l'une des applications mobile du template OneLink liées à la collection.

Pour télécharger une collection :

1. Cliquez sur l'icône de téléchargement sur la ligne de la collection.
2. Sélectionnez le domaine pour la sortie de l'URL courte.
3. Cliquez sur **Télécharger**.

> 🚧 **Important !**
>
> AppsFlyer recommande d'utiliser des domaines de marque car ils peuvent améliorer les performances de la campagne en suscitant la confiance et en promouvant la notoriété de la marque. <Anchor target="_blank" href="/marketers/fr/docs/brand-onelink-with-your-domain">Pour en savoir plus, cliquez ici.</Anchor>

</Accordion>

<div id="adding-links-to-a-collection" />

<Accordion title="Ajouter des liens à la collection">

L'option d'ajout de liens est disponible dans les cas suivants :

* Vous disposez d'autorisations d'accès à au moins l'une des applications mobile du template OneLink liées à la collection.
* La collection compte moins de 2000 liens actifs.
* [L'utilisation mensuelle](/docs/perform-onelink-bulk-actions-via-csv#gestion-des-groupes-de-liens-avec-des-collections) n'a pas été dépassée.

Pour ajouter des liens à une collection, cliquez sur **options du menu** > **Ajouter des liens à la collection.**

* Les liens seront ajoutés en utilisant la même méthode que celle décrite dans [Créer votre première collection](/docs/perform-onelink-bulk-actions-via-csv#créer-votre-première-collection) à partir du point 5.

</Accordion>

<div id="editing-links-in-a-collection" />

<Accordion title="Modifier les liens d'une collection">

L'option de modification des liens est disponible lorsque :

* Il existe des liens actifs dans cette collection.
* Vous disposez d'autorisations d'accès à au moins l'une des applications mobile du template OneLink liées à la collection.
* [L'utilisation mensuelle](/docs/perform-onelink-bulk-actions-via-csv#gestion-des-groupes-de-liens-avec-des-collections) n'a pas été dépassée.

**Pour modifier les liens d'une collection :**

1. Cliquez sur **options du menu** > **Modifier les liens**.
2. Télécharger la base de la collection au format CSV. Ce fichier contient tous les liens de la collection que vous pouvez modifier.
3. Suivez les instructions de la première étape pour modifier les paramètres du lien. Pour tous les liens que vous souhaitez mettre à jour, assurez-vous que **Marquer pour la mise à jour** est réglé sur **true**.
4. Cliquez sur **Suivant**.
5. Téléchargez votre fichier CSV modifié. Voir [Format de téléchargement](/docs/perform-onelink-bulk-actions-via-csv#upload-format) pour vous assurer que votre fichier CSV est compatible et qu'il est exporté avec succès.
   * Une fois le fichier CSV exporté, il est validé.
   * En cas de lignes invalides, un rapport de validité CSV peut être téléchargé pour vous aider à corriger votre fichier. Suivez les instructions de l'interface utilisateur et exportez le fichier corrigé.
6. Cliquez sur **Mettre les liens à jour**.

</Accordion>

<div id="viewing-the-collection-history" />

<Accordion title="Visualisation de l'historique de la collection">

Pour consulter l'historique d'une collection, cliquez sur **Options du menu** > **Voir l'historique de la collection.**

La fenêtre d'historique affiche les actions suivantes, ainsi que la date et l'heure auxquelles elles ont été effectuées et par qui :

* **Changements de nom :** les changements de nom de la collection.
* **Liens ajoutés :** date à laquelle les liens ont été ajoutés à la collection.
* **Liens mis à jour** : lorsque des liens de la collection ont été édités et mis à jour.
* **Collection** **créée** : date de création de la collection.

<span id="page-components"></span>**Les liens ajoutés et mis à jour** vous indiquent également comment les changements ont affecté votre [utilisation](/docs/perform-onelink-bulk-actions-via-csv#gestion-des-groupes-de-liens-avec-des-collections) et vous permettent de télécharger un rapport d'action sur ce changement.

* * Les rapports d'action ne peuvent être téléchargés que si vous disposez d'autorisations d'accès à au moins l'une des applications mobile du template OneLink liées à la collection.

</Accordion>

<div id="editing-the-collection-name" />

<Accordion title="Modification du nom de la collection">

L'option d'édition du nom de la collection est disponible dans les cas suivants :

* Vous disposez d'autorisations d'accès à au moins l'une des applications mobile du template OneLink liées à la collection.

Pour modifier le nom d'une collection :

1. Survolez le nom de la collection que vous souhaitez modifier.
2. Cliquez sur l'icône de modification à côté du nom de la collection.
3. Après avoir modifié le nom, cliquez sur Entrée ou sur une autre partie de l'écran.

</Accordion>

<div id="deleting-empty-collections" />

<Accordion title="Suppression des collections vides">

Si une collection est vide et que vous disposez d'autorisations d'accès à au moins l'une des applications mobile du template OneLink liées à la collection, celle-ci peut être supprimée en cliquant sur **Options de menu -> Supprimer la collection**.

Les collections peuvent être vides pour les raisons suivantes :

* La <Anchor target="_blank" href="/marketers/fr/docs/bulletin-onelink-short-url-ttls-automatically-extend">durée de vie</Anchor> de tous les liens de la collection a expiré.
* La création de nouvelle collection a été interrompu ou ne s'est pas achevé avant la création des liens. Ce qui crée une collection vide.

</Accordion>

## Informations générales

> 📘 **Remarque**
>
> Les groupes de liens créés avant avril 2023 ne s'afficheront pas et ne seront pas gérés sur la page des groupes de liens.

<div id="upload-format" />

<Accordion title="Format d'exportation">

Pour que votre fichier CSV soit exporté sans erreur, assurez-vous qu'il respecte les normes suivantes.

* Le fichier doit être au format CSV
* Le fichier ne doit pas dépasser 4 Mo
* Le fichier ne doit contenir que le contenu des liens que vous créez/mettez à jour.
* Chaque lien doit être placé sur sa propre ligne
* Chaque colonne représente un paramètre
  * Maximum 35 colonnes de paramètres
* Seul le codage de caractères UTF-8 est accepté
* 2000 liens maximum par collection

</Accordion>

<div id="csv-parameters" />

<Accordion title="Paramètres CSV">

* Les paramètres CSV peuvent être n'importe quel paramètre acceptable dans un lien AppsFlyer. Il peut s'agir de paramètres réservés à l'attribution (par exemple : c, af\_channel, af\_adset, etc.), à la redirection et au deep linking (par exemple : af\_ios\_url, af\_dp, deep\_link\_value, etc.), ou de paramètres personnalisés.
* Le paramètre (pid) de la source média est obligatoire.
* Les agences doivent ajouter manuellement le paramètre `af_prt` à leurs liens.
* Même si un schéma d'URI est défini dans le template OneLink, pour les liens créés en groupe le paramètre af\_dp avec le schéma URI doit être spécifié dans votre fichier CSV.

</Accordion>

<div data-zendesk-anchors="getting-started=mise-en-route h_01HJJRRJCD2F57FE0A4Z5BCMTE=mise-en-route creating-your-first-collection=cr%C3%A9er-votre-premi%C3%A8re-collection h_01HJJRRJCDSTTR2FQ53J86RGSJ=cr%C3%A9er-votre-premi%C3%A8re-collection collection-features=gestion-des-groupes-de-liens-avec-des-collections h_01HJJRRJCDCF830CCFCV3HQSJY=gestion-des-groupes-de-liens-avec-des-collections other-actions=autres-actions h_01HJJRRJCD2XE454G11WMY5AK9=autres-actions h_01HJJRRJCDZVFG9STE7PA38D4D=creating-a-new-collection h_01HJJRRJCDHMCWFBVRHYBS1D1N=downloading-a-collection h_01HJJRRJCDJ1201WPSMPMAJ6Q9=important- h_01HJJRRJCDPRV1DVSAGQRD4ANG=adding-links-to-a-collection h_01HJJRRJCDW88HYY4W7M2W5BD8=editing-links-in-a-collection h_01HJJRRJCDANN18DS1CEZS8001=viewing-the-collection-history h_01HJJRRJCDKAVCD4M8R187XER9=editing-the-collection-name h_01HJJRRJCD47RM4VYGN8TRJPHJ=deleting-empty-collections general-information=informations-g%C3%A9n%C3%A9rales h_01HJJRRJCDR7MA544ZX324B4Y2=informations-g%C3%A9n%C3%A9rales h_01HJJRRJCD2CHGKVSG22TKFMM9=remarque h_01HJJRRJCDCZ0ZBPZ2AH77JJTJ=upload-format h_01HJJRRJCDN5MWX72S9P37E69N=csv-parameters" />
