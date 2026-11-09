---
title: Data Locker pour les marketeurs
metadata:
  keywords:
    - Reports
    - Data Locker
    - Advertisers
    - Raw Data
    - Developers
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2019-02-03T12:20:08Z'
  edited_at: '2023-11-20T08:41:12Z'
  id: 360000877538
  locale: fr
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/fr/articles/360000877538
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** Data Locker envoie les données de vos rapports dans un stockage Cloud pour les charger ensuite dans vos systèmes BI. Vous pouvez choisir pa  
> rmi différents stockages : un compartiment appartenant à AppsFlyer dans AWS, ou un stockage dont vous êtes propriétaire dans AWS, GCS, Yandex, BigQuery ou Snowflake. Data Locker prend en charge les [destinations multiples](/docs/data-locker-for-marketers#multipleconnections-principles-more-than-one-destination). Cela signifie que vous pouvez envoyer l'ensemble des données vers plusieurs destinations, regrouper les données par destination, ou cumuler les deux.

## Data Locker

<Image align="center" alt="6133DataLockerForAdvertisers.png" src="https://files.readme.io/820fee89515ccdcdfac2043bcb9fde722ddc8ec852a140ec250378c581d9c375-32966274469649.png" />

Dans Data Locker, sélectionnez vos apps, sources média, événements et rapports à inclure dans les données qu’AppsFlyer envoie aux solutions de stockage Cloud sélectionnées. Chargez les données par programme dans vos systèmes BI à partir du stockage.

<div id="data-locker-features" />

<Accordion title="Data Locker : fonctionnalités">

| Contient | Description |
| --- | --- |
| [Options de stockage (Cloud)](/docs/data-locker-for-marketers#storage-options) | Data Locker peut envoyer vos données à l'un des fournisseurs de services Cloud suivants :<ul><li>Stockage appartenant à AppsFlyer dans AWS</li><li><Anchor target="_blank" href="/marketers/fr/docs/data-locker-cloud-service-setup">Stockage dont vous êtes propriétaire dans :</Anchor><ul><li>AWS</li><li>GCS</li><li>[Beta] Azure Blob</li><li>[Beta] Yandex</li><li>BigQuery</li><li>Snowflake</li></ul></li></ul>Vous pouvez définir plus d'une destination dans Data Locker. Cela signifie que vous pouvez envoyer toutes ou une partie de vos données vers [plusieurs destinations](/docs/data-locker-for-marketers#multipleconnections-principles-more-than-one-destination).<br /><br />**Exemples**<ul><li>Séparer les données par type de rapport. Envoyer des données brutes à GCS et des données agrégées à Snowflake.</li><li>Séparer les données par app et envoyer les données par groupe d'apps à différents compartiments.</li></ul> |
| Multi-app | Diffusez les données de l'une, de plusieurs ou de l'ensemble des apps de votre compte. Lorsque vous ajoutez des apps au compte, elles peuvent être incluses automatiquement. |
| Fenêtre de disponibilité | 14 jours |
| [Segmentation des données](/docs/data-locker-for-marketers#app-segregation) | Options de séparation des données disponibles (valables pour le stockage dans des compartiments sur le cloud) :<ul><li>[Par défaut] **Unifié :** les données cumulées de toutes les apps. Le champ ID d'app au niveau des lignes permet d'identifier l'app dans les fichiers de données.</li><li>**Segmenté par app :** les données de chaque app sont classées dans un dossier séparé. Le nom du dossier est constitué par l'ID de l'app.</li></ul> |
| Options de format de données | <ul><li>Pour le stockage dans des compartiments sur le cloud :<ul><li>CSV</li><li>PARQUET</li><li><Anchor target="_blank" href="/marketers/fr/docs/adobe-experience-platform-aep-integration-with-appsflyer-data-locker">Adobe</Anchor></li></ul></li><li>Base de données</li></ul> |
| Actualisation des données | L'actualisation dépend du type de rapport<ul><li>**Chaque heure :** données générées en continu, exemple : les installations et les données d'événements in-app sont inscrites dans les heures qui suivent l'arrivée de l'événement chez AppsFlyer.</li><li>**Chaque jour :** certains rapports, comme les désinstallations, sont générés quotidiennement et sont prêts le jour suivant.</li><li>**Version** : si le même rapport est généré plusieurs fois pour la même période, un mécanisme de versions est mis en place.</li></ul> |

</Accordion>

<div id="reports-available-via-data-locker" />

<Accordion title="Rapports disponibles via Data Locker">

<Anchor target="_blank" href="/marketers/fr/docs/data-locker-advertiser-reports">Rapports disponibles via Data Locker</Anchor>

</Accordion>

<div id="data-storage-architecture" />

## Architecture de stockage des données

<div id="zd-overview" />

<div id="9-save-the-connection" />

<div id="8-remove-legacy-fields" />

<div id="7-select-the-reportlevel-filters" />

<div id="6-select-the-report-fields" />

<div id="customize-or-duplicate" />

<div id="5-select-the-report" />

<div id="select-global-level-filters" />

<div id="3-set-the-report-output-settings" />

<div id="snowflake-data-warehouse-connection" />

<div id="bigquery-data-warehouse-connection" />

<div id="yandex-cloud-bucket-connection" />

<div id="azure-cloud-bucket-connection" />

<div id="gcs-cloud-bucket-connection" />

<div id="aws-cloud-bucket-connection" />

<div id="2-add-a-connection-to-your-cloud-service" />

<div id="1-set-up-your-cloud-service" />

<div id="note-4" />

<div id="review-filters-after-changing-ownership" />

<div id="manage-ownership-and-editors" />

<div id="give-data-locker-access" />

<div id="manage-data-locker-access-and-ownership-admins" />

<div id="set-user-permissions" />

<div id="important" />

<div id="non-empty-legacy-fields" />

<div id="note-3" />

<div id="note-2" />

<div id="note-1" />

<div id="note" />

<div id="set-data-locker-report-settings" />

<div id="overview" />

<Accordion title="Présentation">

La structure des données stockées varie si les données sont envoyées vers un stockage Cloud ou une banque de données. La structure des dossiers décrite ici s'applique au stockage (compartiments). Dans le cas du stockage dans une banque de données (Snowflake), la référence des dossiers modifie l'affichage. Cf <Anchor target="_blank" href="/partners/fr/docs/data-locker-for-partners">Snowflake</Anchor>.

Les données sont inscrites dans le stockage que vous avez choisi. Dans le cas du stockage Cloud, soit le stockage appartient à AppsFlyer sur AWS, soit vous en êtes propriétaire sur AWS, GCS ou Yandex. Vous pouvez changer d’option de stockage à tout moment, ou envoyer une partie ou la totalité de vos données à plusieurs options de stockage.

Les données stockées sont rangées dans une structure de dossiers hiérarchisée selon le type de rapport, la date et l'heure. La figure suivante vous donne un exemple de cette structure :

<Image align="center" alt="DLFolderOVerview.png" src="https://files.readme.io/78f360ec1df72253e5b2cd725f3eecf4e17548a7f06b544a94a75a2c319d77a0-18107910420369.png" />

Les données d'un certain rapport sont contenues dans les dossiers «heure» (h) associés à ce rapport :

* Le nombre de dossiers par heure dépend de l'actualisation des données du rapport (chaque heure, chaque jour ou selon la version).
* Les données sont fournies dans des fichiers compressés GZIP ou Snappy, ou des fichiers non compressés, au format Parquet ou CSV.
* Les fichiers de données se composent de colonnes (champs).
* La structure (les champs) des <Anchor target="_blank" href="/marketers/fr/docs/data-locker-advertiser-reports#user-journey">rapports sur les parcours utilisateurs</Anchor> est toujours la même et correspond aux champs que vous avez choisis. Il existe d'autres rapports qui ont leurs propres champs définis et que l'on nomme « rapports sans schéma ». Consultez les <Anchor target="_blank" href="/marketers/fr/docs/data-locker-advertiser-reports#user-journey">Rapports des annonceurs Data Locker</Anchor> pour découvrir les rapports disponibles et accéder aux liens vers leurs caractéristiques.

</Accordion>

<div id="folder-structure" />

<Accordion title="Structure de dossier">

| Dossier | Description |
| --- | --- |
| ID d'abonnement | <Image alt="DataLockerFolders.png" src="https://files.readme.io/0cda5728e48dab772878cad13ed3b81168f152e1bf01604ac45b700af804dd16-32966264039185.png" width="439px" /><ul><li>Le dossier racine du compartiment dépend du propriétaire et du fournisseur de stockage. En général, le dossier racine est votre ID d’abonnement, mais dans certains cas (par exemple si vous utilisez Cyberduck), l’ID est défini dans le signet et ne s’affiche pas dans la structure des dossiers.</li><li>Le dossier *data-locker-hourly* contient les sujets du rapport. Les dossiers supérieurs à ce niveau dépendent de la propriété du compartiment et du fournisseur de services Cloud.</li></ul>**Exemples de structure de dossiers en fonction du propriétaire du compartiment et du fournisseur de Cloud**<ul><li>**Compartiment AppsFlyer** : &lt;af-ext-reports>/&lt;unique\_identifier>/&lt;data-locker-hourly></li><li>**Votre compartiment AWS** : *&lt;af-datalocker-your bucket prefix>/&lt;generated-home-folder>&lt;subscription-id>*</li><li>**Votre compartiment GCS :** &lt;your bucket name>/&lt;generated-home-folder>/&lt;subscription-id></li></ul> |
| Sujet (t) | Le type de rapport est lié au sujet du rapport. |
| Date (dt) | Il s'agit de la date des données associées. Dans le cas de données brutes, il s'agit de la date de l'événement. Dans le cas de données agrégées, il s'agit de la date du rapport lui-même. |
| Temps (h ou version) | Les dossiers de dates sont divisés en dossiers par **heure (h)** ou par **version** selon le type de rapport.<br /><br />**<span id="hourly-folders"></span>Dossiers par heure**<br /><br />Les dossiers h correspondent à l'heure à laquelle AppsFlyer reçoit les données AppsFlyer. Exemple : les événements d'installation reçus entre 14:00 et 15:00 UTC sont inscrits dans le fichier h=14. Important ! Il y a un décalage d'environ 1 à 3 heures entre le moment où les données arrivent dans AppsFlyer et l'heure à laquelle le dossier h est enregistré dans Data Locker. Exemple : le dossier h=14 est enregistré 1 heure plus tard, soit à 15 h UTC.<br /><br />**Caractéristiques du dossier par heure** :<ul><li>Il y a 24 dossiers h numérotés de 0 à 23. Par exemple : h=0, h=1, etc</li><li>Un dossier «h=late», contient les événements du jour précédent mais qui sont arrivés après minuit. C'est à dire les événements qui arrivent entre 00:00 et 02:00 UTC le lendemain. Exemple  : si un utilisateur installe une app lundi à 08:00 UTC et que l'événement arrive mardi à 01:00 UTC, l'événement est inscrit dans le dossier « late » du lundi.</li><li>Les données qui arrivent après 02:00 UTC sont inscrites dans le dossier correspondant au jour et au moment où l'événement est arrivé.</li><li>Vérifiez que les données du dossier h=late sont bien consommées. Elles ne sont pas contenues dans un autre dossier.</li><li>\_temporary folder : dans certains cas, un dossier temporaire est généré au sein d'un dossier h. Vous devez ignorer le dossier temporaire ainsi que ses sous-dossiers. Exemple : /t=impressions/dt=2021-04-11/h=18/**\_temporary**.</li><li>**Remarque** :<ul><li>Les rapports de données brutes actualisés sur une base quotidienne sont stockés dans le dossier h=23. Le rapport de désinstallation se trouve généralement dans le dossier h=2 mais peut se trouver dans n'importe quel dossier.</li><li>Les rapports de cohorte et d'augmentation sont stockés directement dans le dossier dt.</li><li>Les rapports avec version respectent une convention différente décrite dans cette section.</li></ul></li></ul>**Notes sur les rapports heure par heure pour les apps qui n'utilisent pas l'horaire UTC.**<br /><br />Pour vous assurer d'obtenir l'ensemble des données sur un certain jour, vous devez utiliser les dossiers en fonction du jour défini par le fuseau horaire de l'app, comme expliqué ici :<ul><li>**Fuseau horaire de l'hémisphère Est**: pour obtenir l'ensemble des données sur un jour J, il faut utiliser les dossiers qui correspondent l'heure et à la date UTC. Exemple : le fuseau horaire de votre app est UTC+10 (Sydney, Australie). Pour obtenir toutes les données heure par heure du mardi (Sydney) vous devez utiliser les dossiers suivants : Lundi h=14-23 et « late », Mardi h=0-13 et 14-15 Pourquoi utiliser Mardi h=14-15 ? Car certaines données peuvent arriver en retard. Ainsi, les dossiers h=14–15 peuvent contenir des événements arrivés avec un décalage. Vous devez filtrer event\_time pour aligner le jour du calendrier de l'app selon l'UTC.</li><li>**Fuseau horaire de l'hémisphère Ouest**: pour obtenir l'ensemble des données sur un jour J, il faut utiliser les dossiers qui correspondent l'heure et à la date UTC. Exemple : le fuseau horaire de votre app est UTC- 7 (Los Angeles). Pour obtenir toutes les données heure par heure du mardi (Los Angeles) vous devez utiliser les dossiers suivants : Mardi h=7-23 et « late », Mercredi h=0-6 et 7-8 Pourquoi utiliser Mercredi h=7-8 ? Car certaines données peuvent arriver en retard. Ainsi, les dossiers h=7-8 peuvent contenir des événements arrivés avec un décalage. Vous devez filtrer event\_time pour l'aligner sur le jour calendaire de l'app selon l'UTC.</li></ul>**<span id="version-folders"></span>Dossiers de versions**<br /><br />Certains rapports ont une option de version. Cela signifie que les données les plus récentes pour un jour donné sont fournies plusieurs fois. Comme les données peuvent continuer à être mises à jour en raison de données tardives ou plus précises, le même rapport comporte plusieurs versions où la version la plus récente est la plus précise.<br /><br />Les rapports d'un jour donné sont contenus dans le dossier des versions de ce jour. Chaque version se trouve dans un dossier distinct dont le nom est défini à l'aide d'un horodateur Epoch qui identifie de manière unique le rapport.<br /><br />Vos processus d'importation de données doivent tenir compte du fait que les données peuvent être écrites rétroactivement. Par exemple, le 14 janvier, les données peuvent être écrites dans le dossier Jan 1. Si vous êtes le propriétaire du compartiment, envisagez d'utiliser la notification du service Cloud pour déclencher votre processus d'importation (<Anchor target="_blank" href="https://docs.aws.amazon.com/AmazonS3/latest/userguide/NotificationHowTo.html">AWS</Anchor> \| <Anchor target="_blank" href="https://cloud.google.com/storage/docs/pubsub-notifications">GCS</Anchor>). |

</Accordion>

<div id="app-segregation" />

<Accordion title="Segmentation des apps">

Les données sont fournies dans des fichiers de données unifiés contenant les données de toutes les apps sélectionnées ou séparées en dossiers par app. La segmentation se trouve dans le dossier h, comme décrit dans le tableau suivant. 

| Type de segmentation | Description |
| --- | --- |
| [Défaut] Unifié | Les données de toutes les apps sont fournies dans des fichiers de données unifiés. Lorsque vous consommez les données, utilisez le champ app\_id au niveau des lignes pour faire la distinction entre les applications.<br /><br />**Des exemples de fichiers de données sont disponibles dans le dossier h=2**<br /><br />![UnifiedByApp.png](https://files.readme.io/dbc39c2ce99c1ff607fd553b9c9034e55728c102f31fd18a501cc00910267b28-18107874522513.png)<br /><br />La nomenclature du fichier de données est unique\_id.gz.<ul><li>Votre processus de chargement des données doit :<ul><li>Charger les données après la définition de l'indicateur \_SUCCESS.</li><li>Charger tous les fichiers du dossier avec *.gz*comme extension. N'élaborez pas votre processus d'importation en utilisant une logique de numérotation par parties. .</li></ul></li></ul> |
| Segmenté par application | Le dossier contient des sous-dossiers pour chaque app. Les fichiers de données correspondant à chaque app sont contenus dans le dossier de l'app. Dans la figure qui suit, le dossier h=19 contient des dossiers d'app. Chaque dossier d'app contient les fichiers de données associés. Important ! Les fichiers de données ne contiennent pas l'app\_id. Vous devez le déterminer à l'aide du dossier.<br /><br />![DLSegregateByApp.png](https://files.readme.io/90639507da82f7dafacfa5bfb67fa96a8277747cd0eee226d74498bf5ff16869-32966264040977.png)<br /><br />Dans chaque dossier d'app, la convention de dénomination est unique\_id.gz :<ul><li>Votre processus de chargement des données doit :<ul><li>Charger les données après la définition de l'indicateur \_SUCCESS.</li><li>Charger tous les fichiers du dossier avec *.gz*comme extension. N'élaborez pas votre processus d'importation en utilisant une logique de numérotation par parties. .</li></ul></li></ul>Limitation : cette option n'est pas disponible pour les rapports d'attribution basés sur les personnes. |

</Accordion>

<div id="data-files" />

<Accordion title="Fichiers de données">

Les fichiers de données dépendent du type de segmentation.

<table><thead><tr><th>Contenu</th><th colspan="2">Détails</th></tr></thead><tbody><tr><td>Indicateur d'achèvement</td><td colspan="2"><p>L'indicateur du dernier fichier (terminé) est activé lorsque l'ensemble des données d'un dossier h ont été inscrites.</p><ul><li><p>Ne lisez pas les données d'un dossier avant de vérifier que l'indicateur _SUCCESS existe.</p></li><li><p>L'indicateur _SUCCESS s'affiche même dans le cas où il n'y a aucune données à inscrire dans le dossier en question, et que celui-ci est vide. </p></li><li>Important ! Dans l'option de segmentation par app, l'indicateur est défini dans le dossier h et non dans les dossiers individuels de l'application. Cf illustrations dans la section précédente.</li></ul></td></tr><tr><td>Types de fichiers</td><td colspan="2"><ul><li>Les données sont fournies dans des fichiers compressés GZIP ou Snappy, ou des fichiers non compressés, au format Parquet ou CSV.</li><li>Une fois décompressés, les fichiers de données sont au format Parquet ou CSV, en fonction de vos paramètres.</li></ul></td></tr><tr><td>Séquence de colonnes (fichiers CSV) </td><td colspan="2"><p>Pour les fichiers CSV, la séquence des champs dans les rapports est toujours la même. Lorsque nous ajoutons de nouveaux champs, ceux-ci sont ajoutés à droite des champs existants.</p><p>À cet égard : </p><ul><li>La structure des colonnes des rapports de parcours utilisateur est identique. Vous pouvez ainsi profiter des mêmes procédures de chargement des données pour des types de rapports différents. Vous sélectionnez les champs (colonnes) qui apparaissent dans les rapports. La signification des champs se trouve dans le <a href="./raw-data-field-dictionary" target="_blank">dictionnaire des données brutes</a>. </li><li>Les rapports ayant une indication FF dans la section de disponibilité des rapports ne respectent pas la structure de colonne commune. </li></ul></td></tr><tr><td>Considérations relatives au remplissage des champs</td><td colspan="2"><p><strong>Champs vides :</strong> certains champs font apparaitre le message<em>null</em> ou restent vides. Cela signifie que dans le cadre d'un rapport donné, il n'y a aucune donnée à signaler. En général, <em>null</em> indique que le champ n'est pas renseigné pour ce rapport et ce type d'application donnés. Un espace vide « » indique que le champ relève bien du cadre, mais qu'aucune donnée n'a été trouvée pour pouvoir le renseigner.</p><p>En cas de source média restreinte, le contenu des champs restreints est défini sur Null. </p><p>Les termes null et blank sont généralement considérés comme une seule et même chose ; il n'y a pas de données disponibles. </p><p><strong>Fuseau horaire et devise</strong></p><p>Les paramètres de fuseau horaire et de devise propres à l'application n'ont aucun effet sur les données inscrites dans Data Locker. Les conditions suivantes s'appliquent :</p><ul><li> <strong>Fuseau horaire</strong> : les données de la date et de l'heure sont en UTC.</li><li> <strong>Devise</strong> : le champ event_revenue_usd est en USD. </li></ul><p><strong>Valeurs avec virgules</strong> : les valeurs qui comportent une virgule sont placées entre guillemets, exemple, <code>`"iPhone6,1"`</code>.</p></td></tr></tbody></table>

</Accordion>

<div id="storage-options" />

<Accordion title="Options de stockage">

<div id="caution" />

> ❗️ **Attention !**
>
> Si vous utilisez l'option de stockage appartenant au marketeur :
>
> * Vérifiez que vous respectez les réglementations sur la confidentialité des données telles que le RGPD et les politiques de conservation des données du réseau publicitaire/SRN.
> * N'utilisez pas la solution de stockage appartenant au marketeur pour envoyer des données à des tiers.

* Les données sont inscrites pour le propriétaire de compartiment de votre choix, comme suit :
  * Stockage appsFlyer
  * Stockage client : AWS, GCS, Yandex, BigQuery et Snowflake
* Vous pouvez modifier la sélection du stockage à tout moment.
* Si vous modifiez l'espace de stockage, voici ce qui se passe :
  * Nous commençons à écrire dans le stockage nouvellement sélectionné dans l'heure qui suit.
  * Nous continuons à écrire dans le stockage existant pendant une période de transition de 7 jours. L'heure d'expiration de la période de transition s'affiche dans l'interface utilisateur. Cette période de transition peut vous permettre de mettre à jour vos processus de chargement des données.  Vous pouvez relancer la période de transition ou revenir au compartiment AppsFlyer selon vos besoins.
  * **Modification du stockage** : vous pouvez migrer d’une option de stockage à une autre en utilisant l’option multi-stockage et en envoyant des données vers plusieurs destinations en même temps. Une fois la migration et les tests terminés, supprimez l’option de stockage dont vous n’avez plus besoin.

|  | Stockage appartenant à AppsFlyer (AWS) | Stockage appartenant au marketeur (GCS, AWS, Azure, Yandex, BigQuery, Snowflake) |
| --- | --- | --- |
| Nom du compartiment | Définir par AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/fr/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor> : aucune restriction</li><li><Anchor target="_blank" href="/marketers/fr/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor> : défini par vous. Doit comporter le préfixe af-.</li></ul>Exemple : `af-datalocker-votre-nom-de-compartiment` |
| Propriété du stockage | AppsFlyer | Marketeur |
| Plate-forme de stockage | AWS | AWS, GCS, Azure, Yandex, BigQuery, Snowflake |
| Autorisations d'accès aux données que vous accordez | Disponible dans l'interface utilisateur de Data Locker pour les admins de votre compte AppsFlyer | Inconnu par AppsFlyer. Utilisez les informations d'identification fournies par le fournisseur de stockage Cloud. |
| Conservation des données | Les données sont supprimées après 14 jours | Responsabilité du marketeur |
| Demandes de suppression de données | Responsabilité d'AppsFlyer | Responsabilité du marketeur |
| Sécurité | AppsFlyer contrôle le stockage. Le client a un accès en lecture seule. | Le marketeur contrôle le stockage.<ul><li>**AWS** : AppsFlyer demande l'autorisation pour GetObject, ListBucket, DeleteObject, PutObject au compartiment. Le compartiment doit être soumis à l'utilisation exclusive d'AppsFlyer. Ne l'utilisez pas à d'autres fins.</li><li>**GCS** : voir <Anchor target="_blank" href="/marketers/fr/docs/data-locker-cloud-service-setup">article sur la configuration GCS</Anchor>.</li></ul> |
| Capacité de stockage | Géré par AppsFlyer | Géré par le marketeur |
| Contrôle de l'accès à l'aide de points de terminaison VPC avec règles de compartiment | Non applicable | [Facultatif] Dans AWS, si vous installez la sécurité des points de terminaison VPC au niveau compartiment, vous devez autoriser les serveurs AppsFlyer. |

<div id="notice-to-security-officers-in-the-case-of-customer-controlled-storage" />

#### **Avis aux agents de sécurité dans le cas de stockage contrôlé par le client**

À prendre en compte :

* Le compartiment (ou destination) est soumis à l'utilisation exclusive d'AppsFlyer. Aucune autre entité ne doit inscrire quoi que ce soit dans une destination.
* Vous pouvez supprimer les données de la destination 25 heures après leur écriture.
* Les données que nous inscrivons dans la destination sont une copie des données déjà présentes sur nos serveurs. Les données restent stockées sur nos serveurs, conformément à notre politique de rétention des données.
* Pour des raisons techniques, il nous arrive de supprimer puis d'inscrire à nouveau des données.C'est la raison pour laquelle nous avons besoin d'obtenir les autorisations pour supprimer et répertorier les données.Aucune des autorisations ne compromet votre sécurité. Lorsque nous répertorions les données, nous sommes les seuls à inscrire les infos dans le compartiment. Lorsque nous supprimons des éléments, nous sommes en mesure de générer à nouveau les données.
* Pour toute information complémentaire, vous pouvez joindre notre équipe dédiée à la sécurité sur[hello@appsflyer.com](mailto:hello@appsflyer.com), ou votre CSM.

</Accordion>

<div id="multipleconnections-principles-more-than-one-destination" />

<Accordion title="Fonctionnement des multi-connexions (plus d'une seule destination)">

Dans Data Locker, vous pouvez envoyer une partie ou la totalité de vos données vers 2 destinations (définies dans les paramètres de connexion). Vous pouvez par exemple envoyer les données d’une app A à AWS, et les données d’une app B à GCS.

Chaque connexion se compose d’un ensemble complet de paramètres Data Locker, qui inclut une destination. Les paramètres de connexion sont indépendants les uns des autres.

Pour gérer vos connexions, n'oubliez pas que :

* Dans les paramètres Data Locker, les connexions s'affichent dans des onglets. Chaque connexion possède son propre onglet Paramètres, d'où vous pouvez gérer la connexion. Pour chaque onglet, l'icône représente le type de stockage.
* Pour afficher les détails d'une connexion, dupliquer ou supprimer une connexion, cliquez sur ⋮ (options).

</Accordion>

## Procédures

<div id="set-up-data-locker" />

<Accordion title="Configurer Data Locker">

Suivez cette procédure pour mettre en place Data Locker. Toute modification apportée aux paramètres Data Locker met jusqu'à 3 heures avant d'être effective.

**Conditions préalables**

**Pour mettre en place un stockage appartenant au marketeur :**

Si vous configurez Data Locker avec un service de stockage cloud appartenant à un marketeur, veuillez suivre la ou les procédures suivantes.

* Configuration :
  * Compartiment <Anchor target="_blank" href="/marketers/fr/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>
  * Compartiment <Anchor target="_blank" href="/marketers/fr/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor>
  * [Beta] <Anchor target="_blank" href="/marketers/fr/docs/data-locker-cloud-service-setup#beta--azure-storage">Azure</Anchor> Blob
  * [Beta] Compartiment <Anchor target="_blank" href="/marketers/fr/docs/data-locker-cloud-service-setup#yandex">Yandex</Anchor>
  * Compartiment <Anchor target="_blank" href="/marketers/fr/docs/data-locker-cloud-service-setup#bigquery">BigQuery</Anchor>
  * Compartiment <Anchor target="_blank" href="/marketers/fr/docs/data-locker-cloud-service-setup#snowflake">Snowflake</Anchor>

**Important !** Si vous n'avez pas d'abonnement à Data Locker et que vous avez uniquement accès aux analyses de cohorte ou aux données SKAN, vous devez suivre la procédure pour le stockage cloud appartenant aux marketeurs.

**![AppsFlyerAdmin_us-en.png](https://support.appsflyer.com/hc/article_attachments/16581340456849) Pour configurer Data Locker :**

1. Un admin doit effectuer la configuration.
2. Dans Appsflyer, allez dans **Integration**>**Data Locker**.
3. [Facultatif] Si vous avez déjà une destination Data Locker active et que vous souhaitez en ajouter une nouvelle, cliquez sur **Ajouter connexion**. Nommez votre connexion.
4. **Sélectionnez une destination pour les données de service Cloud**. Effectuez l'une des opérations suivantes :  
   * Sélectionnez **Compartiment AWS AppsFlyer** (option disponible uniquement pour les abonnés Data Locker). Cliquez sur **Enregistrer** et passez à l'étape 5.
   * Sélectionnez **S3**.
     1. Saisissez le nom de votre compartiment AWS S3. `Le préfixe af-` est obligatoire et doit être saisi manuellement.
     2. Cliquez sur **Test de connexion**.
     3. Vérifiez qu'aucun message d'erreur ne s'affiche pour indiquer que le chemin du compartiment est invalide.
     4. Choisissez si vous voulez **Rendre cette connexion compatible avec Adobe Experience Platform**. Si cette option est sélectionnée, cliquez sur **Enregistrer** et passez à l'étape 6.
     5. Cliquez sur ***Enregistrer***.
   * Sélectionnez **GCS**.
     1. Entrez le **nom de votre compartiment GCS**.
     2. Cliquez sur **Test de connexion**.
     3. Vérifiez qu'aucun message d'erreur ne s'affiche pour indiquer que le chemin du compartiment est invalide.
     4. Choisissez si vous voulez **Rendre cette connexion compatible avec Adobe Experience Platform**. Si cette option est sélectionnée, cliquez sur **Enregistrer** et passez à l'étape 6.
     5. Cliquez sur ***Enregistrer***.
   * [Beta] Sélectionnez **Azure**.
     1. Saisissez votre **nom de connexion**, votre **nom de compte de stockage** et votre **clé**.
     2. Vérifiez qu'aucun message d'erreur ne s'affiche pour indiquer que le chemin du compartiment est invalide.
     3. Choisissez si vous voulez **Rendre cette connexion compatible avec Adobe Experience Platform**. Si cette option est sélectionnée, cliquez sur **Enregistrer** et passez à l'étape 6.
     4. Cliquez sur ***Enregistrer***.
   * [Beta] Sélectionner **Yandex**.
     1. Saisissez le nom de votre **Compartiment**, **Clé d'accès**, et **Clé secrète**.
     2. Vérifiez qu'aucun message d'erreur ne s'affiche pour indiquer que le chemin du compartiment est invalide.
     3. Choisissez si vous voulez **Rendre cette connexion compatible avec Adobe Experience Platform**. Si cette option est sélectionnée, cliquez sur **Enregistrer** et passez à l'étape 6.
     4. Cliquez sur ***Enregistrer***.
   * Sélectionnez **BigQuery**.
     1. Saisissez l'ID de votre projet BigQuery et le nom de votre ensemble de données.
     2. Cliquez sur **Test de connexion**.
     3. Vérifiez qu'aucun message d'erreur ne s'affiche pour indiquer que le chemin du compartiment est invalide.
     4. Cliquez sur **Enregistrer** et passez à l'étape 6.
   * Sélectionnez **Snowflake.**
     1. Saisissez votre région Snowflake et votre ID de compte.
     2. Cliquez sur **Test de connexion**.
     3. Vérifiez qu'aucun message d'erreur ne s'affiche pour indiquer que le chemin du compartiment est invalide.
     4. Cliquez sur **Enregistrer** et passez à l'étape 6.
5. Remplissez la section **Paramètres généraux** :
   1. Sélectionnez le format de fichier désiré :
      * [Par défaut] **Parquet**
      * **CSV**
   2. Sélectionnez le type de compression de fichier désiré :
      * Snappy (uniquement disponible pour les fichiers Parquet)
      * GZIP
      * Non compressé
   3. Sélectionnez le nombre maximum de lignes que peut contenir votre fichier : 10k, 25k, 50, 100k, 200k ou 500k. Plus il y a de lignes dans le fichier, moins il y aura de fichiers, mais plus ils seront volumineux.
   4. Sélectionnez la structure de dossier ([segmentation des données](/docs/data-locker-for-marketers#app-segregation)) :
      * [Par défaut] **Unifié**
      * **Segmenté par application**
6. Complétez la section **Data Locker** :
7. Sélectionnez une ou plusieurs **applications**à inclure dans les rapports. <mark>Sélectionnez **tout** pour inclure automatiquement les apps que vous ajouterez par la suite.</mark>
8. Cliquez sur **Appliquer**.
9. Sélectionnez une ou plusieurs **sources média** à inclure dans les rapports.
   * Par défaut : toutes Signifie que les sources média ajoutées à l'avenir seront ajoutées automatiquement.
10. Cliquez sur **Appliquer**.
11. [Facultatif] Sélectionnez les **champs** à inclure dans les rapports. **Remarque** : nous pouvons être amenés à proposer des champs supplémentaires. Veuillez en tenir compte dans votre processus d'importation des données.
12. Cliquez sur **Appliquer**.
13. Sélectionnez un [type de rapport](/docs/data-locker-for-marketers#data-locker). Vous devez en sélectionner au moins 1.
14. [facultatif] Pour le rapport d'**événements in-app**, sélectionnez les événements in-app à inclure. Si vous avez plus de 100 types d'événements in-app, vous ne pouvez pas lancer de recherche pour les trouver. Saisissez leur nom exact pour les sélectionner.
    * Par défaut : tous Signifie que les événements in-app ajoutés à l'avenir seront ajoutés automatiquement.
15. Cliquez sur **Appliquer**.
16. Cliquez sur **Enregistrer la configuration**. L'un des événements suivants se produit :  
    * Si vous avez choisi le **compartiment AWS AppsFLyer :**
      * Un compartiment AWS dédié est créé. Les informations d'identification du compartiment s'affichent.
      * Le compartiment est accessible uniquement à l'aide des informations d'identification. Les informations d'identification vous permettent d'accéder en lecture seule au compartiment.
    * Si vous avez sélectionné un de vos services de stockage cloud : les données seront inscrites dans votre service dans un délai de 3 heures.

</Accordion>

<div id="reset-credentials" />

<Accordion title="Réinitialiser les identifiants">

Un admin peut réinitialiser les identifiants du compartiment AppsFlyer à tout moment. Important ! Si vous réinitialisez les identifiants, vous devez mettre à jour vos scripts d'importation des données avec les nouveaux identifiants.

**![AppsFlyerAdmin_us-en.png](https://support.appsflyer.com/hc/article_attachments/16581340456849) Pour réinitialiser les identifiants d'un stockage appartenant à AppsFlyer :**

1. Dans Appsflyer, allez dans **Integration**>**Data Locker**.
2. Sélectionnez la destination appartenant à AppsFlyer.
3. Dans la section Identifiants, cliquez sur **Réinitialiser les identifiants.**  
   Une fenêtre de confirmation apparait.
4. Cliquez sur **Réinitialiser**.
5. Attendez que le message **Les identifiants ont bien été réinitialisés** s'affiche (environ 20 secondes).  
   Les nouveaux identifiants sont alors disponibles.

</Accordion>

<div id="track-connection-changes-in-the-audit-log" />

<div id="additional-information" />

## Informations supplémentaires

<div id="traits-and-limitations" />

<Accordion title="Particularités et limites">

| **Particularité** | Remarques |
| --- | --- |
| Réseaux publicitaires | Ne doit pas être utilisé les réseaux publicitaires |
| Agences | Non utilisé pour les agences. |
| Fuseau horaire spécifique à l'app | Ne s'applique pas. Les dossiers Data Locker sont divisés en heures en se basant sur l'UTC. Les événements réels contiennent les heures en UTC. Vous pouvez convertir les heures dans un autre fuseau horaire si nécessaire. Quel que soit le fuseau horaire de votre app, le délai entre l'apparition de l'événement et son enregistrement dans Data Locker reste le même. |
| Devise spécifique à l'app | Non pris en charge |
| Limitations de taille | Ne s'applique pas |
| Actualisation des données | Les données sont mises à jour en fonction de l'actualisation des données du rapport, abordée dans <Anchor target="_blank" href="/marketers/fr/docs/data-locker-advertiser-reports#rapports-de-données-brutes">l'article</Anchor> suivant. |
| Données historiques | Pas de prise en charge. Si vous avez besoin des données historiques, certains rapports sont disponibles via l'API Pull (mais pas tous). |
| Données restreintes | Les champs de certains rapports sont restreints pour raison de confidentialité. <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">En savoir plus</Anchor> |
| Accès des utilisateurs | Seuls les <Anchor target="_blank" href="/marketers/fr/docs/user-management">utilisateurs de compte disposant des autorisations requises</Anchor> peuvent configurer Data Locker. |
| Application unique/applications multiples | Prise en charge multi-applications. Data locker est au niveau du compte |

</Accordion>

<div id="troubleshooting" />

<Accordion title="Dépannage">

* **Symptôme** : impossible de récupérer des données via AWS CLI
* **Message d'erreur** : une erreur s'est produite (accès refusé) lors de l'appel de l'opération ListObjectsV2 : accès refusé
* **Cause** : les informations d'identification AWS utilisées ne sont pas les informations d'identification correctes pour le compartiment AppsFlyer. Cela peut être dû au fait que les informations d'identification sur votre appareil sont multiples ou non valides.
* Solution :
  1. Utilisez une autre méthode que la CLI (par exemple [Cyber Duck](/docs/data-locker-for-marketers#cyberduck)) pour accéder au compartiment. Effectuez cette opération pour vérifier que les informations d'identification que vous utilisez fonctionnent. Si vous parvenez à vous connecter à l'aide de Cyber Duck, c'est le signe qu'un problème existe au niveau du cache des identifiants.
  2. <Anchor target="_blank" href="https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-role.html">Actualisez le cache des identifiants AWS</Anchor>.  
     **Capture d'écran de AWS**

     <Image align="center" alt="mceclip0.png" src="https://files.readme.io/e6608b196c39cb71e0a02e0eabe95378f24659a1578a16fd381bfd0053ca309e-32966264043537.png" />

</Accordion>

<div id="aws-data-retrieval" />

## Récupération des données AWS

Utilisez votre outil de recherche de données AWS habituel, AWS CLI, ou l'un des outils décrits dans les sections qui suivent. Important ! Les instructions exactes conviennent aux compartiments appartenant à AppsFlyer. Si vous vous connectez à votre compartiment, ajustez les instructions si besoin.

<div id="aws-cli" />

<Accordion title="AWS CLI">

Avant de commencer :

* Installez AWS CLI sur votre ordinateur.
* Dans AppsFlyer, accédez à Data Locker et récupérez les informations contenues dans le panneau d'informations d'identification.

**Pour utiliser AWS CLI** :

1. Ouvrez le terminal. Dans Windows, &lt;Windows>+&lt;R>, cliquez sur **OK**.  
   La fenêtre de ligne de commande s'ouvre.
2. Saisissez **aws configure.**
3. Saisissez la clé d'accès AWS telle qu'elle apparaît dans le panneau des informations d'identification.
4. Saisissez votre clé secrète AWS telle qu'elle apparaît dans le panneau des informations d'identification.
5. Saisissez **eu-west-1.**
6. Appuyez sur Entrée (aucun).

Utilisez les commandes CLI qui suivent au besoin.

Dans les commandes suivantes, la valeur de `{home-folder}` peut être trouvée

**Pour répertorier les dossiers de votre compartiment :**

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/
```

<div id="listing-files-and-folders" />

### Liste des fichiers et des dossiers

Il existe trois types de dossiers dans votre compartiment Data Locker :

* Type de rapport `t=`
* Date `dt=`
* Heure `h=`

Pour répertorier tous les rapports d'un type de rapport spécifique :

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/
```

Pour répertorier tous les rapports d'un type de rapport spécifique pour un jour spécifique :

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/dt=2019-01-17
```

Pour répertorier tous les rapports d'un rapport spécifique, à une heure spécifique d'un jour spécifique :

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/dt=2019-01-17/h=23
```

Pour télécharger les fichiers correspondant à une date spécifique :

```bash
aws s3 cp s3://af-ext-reports/<home-folder>/data-locker-hourly/t=installs/dt=2020-08-01/h=9/part-00000.gz ~/Downloads/
```

</Accordion>

<div id="cyberduck" />

<Accordion title="Cyberduck">

Avant de commencer :

* Installez le client Cyberduck.
* Dans AppsFlyer, accédez à Data Locker et récupérez les informations contenues dans le panneau d'informations d'identification.

**Pour configurer Cyberduck** :

1. Dans Cyberduck, cliquez sur Action.
2. Sélectionnez **Nouveau signet**. La fenêtre s'ouvre.
3. Dans le premier champ, (marqué [1] dans la capture d'écran qui suit), sélectionnez **Amazon S3.**

   <Image align="center" alt="DataDuckSmall2.png" src="https://files.readme.io/a2aba523ca9489315260f34c6c42571f67d37f7985d0f18b1eb0ed2a95b4b4ad-32966274482705.png" />
4. Remplissez les champs comme suit :
   * **Pseudo :** texte libre
   * **Serveur :** s3.amazonaws.com
   * **ID de clé d'accès :** copiez la clé d'accès AWS telle qu'elle apparaît dans le panneau des identifiants sur AppsFlyer
   * **Clé d'accès secrète :** copiez la clé secrète de compartiment telle qu'elle apparaît dans le panneau des identifiants sur AppsFlyer.
   * **Chemin** : `{Bucket Name}/{Home Folder}` Par exemple : **af-ext-reports/1234-abc-ffffffff**
5. Fermez la fenêtre. Pour ce faire, cliquez sur la croix en haut à droite de la fenêtre.
6. Sélectionnez la connexion.  
    Les répertoires de données s'affichent.

</Accordion>

<div id="amazon-s3-browser" />

<Accordion title="Navigateur Amazon S3">

Avant de commencer :

* Installez le navigateur Amazon S3.
* Dans AppsFlyer, accédez à Data Locker et récupérez les informations contenues dans le panneau d'informations d'identification.

**Pour configurer le navigateur Amazon S3** :

1. Dans le navigateur S3, cliquez sur **Comptes** > **Ajouter** **Nouveau compte**.  
   La fenêtre Ajouter un nouveau compte s'ouvre.

   <Image align="center" alt="mceclip0.png" src="https://files.readme.io/f7ea8b02f27a5e7eaf89b578b177a9e1a9f34273eaa41d41652156a6dbb23d5c-32966274485009.png" />
2. Remplissez les champs comme suit :
   * **Nom de compte** : texte libre.
   * **ID de clé d'accès :** copiez la clé d'accès AWS telle qu'elle apparaît dans le panneau des informations d'identification.
   * **Clé d'accès secrète :** copiez la clé secrète de compartiment telle qu'elle apparaît dans le panneau des informations d'identification.
   * Sélectionnez **Crypter les clés d'accès** avec un mot de passe puis saisissez un mot de passe. Notez ce mot de passe quelque part.
   * Sélectionnez **Utiliser le transfert sécurisé.**
3. Cliquez sur **Enregistrer les modifications**.
4. Cliquez sur **Compartiments** > **Ajouter compartiment** **externe**.  
   La fenêtre Ajouter un compartiment externe s'ouvre.   

   <Image align="center" alt="mceclip2.png" src="https://files.readme.io/88dd43f62dbd68d0295b52a7f7b9b09449bd915e6a6d52703c24a50583e05a6e-32966264054929.png" width="433px" />
5. Saisissez le **nom du compartiment.** Le nom de compartiment est au format suivant : `{Bucket Name}/{Home Folder}`. Les valeurs nécessaires pour le nom du compartiment et le dossier racine s'affichent dans la fenêtre des informations d'identification.
6. Cliquez sur **Ajouter un compartiment externe.**  
   Le compartiment est créé et s'affiche dans le panneau gauche de la fenêtre.   
   Vous pouvez maintenant accéder aux fichiers Data Locker.

</Accordion>

<div id="see-also" />

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/data-locker-advertiser-reports">Rapports disponibles via Data Locker</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Sélection de l'outil de livraison de données brutes adapté à vos besoins</Anchor>

<div data-zendesk-anchors="h_01HE2S6FANNTNB580CMHNX34YA=data-locker data-locker%E2%80%94features=data-locker-features h_01HE2S6FANQH2GZ11S8S87H0YH=data-locker-features h_01HE2S6FAN6BFPJSZJBEE9P5VK=reports-available-via-data-locker data-storage-architecture=architecture-de-stockage-des-donn%C3%A9es h_01HE2S6FAN4H9DQ5HBTKSNJ72B=architecture-de-stockage-des-donn%C3%A9es h_01HE2S6FANY1FWEY6Y34T85GHM=overview h_01HE2S6FANDJ65MZ2H2FBAZYJR=folder-structure h_01HE2S6FAN7PBZ8M86FQVSN5KQ=hourly-folders h_01HE2S6FAN366V8HNCY4PFNTFG=version-folders h_01HE2S6FANHFZMCY3WZBZB9QMP=app-segregation h_01HE2S6FANVDFH9S9JN8E9J7ES=data-files h_01HE2S6FAN8ZDF5N4ECKKN1D1H=storage-options h_01HE2S6FAN2HY7V3G9NS9XCVE1=attention- notice-to-security-officers-in-the-case-of-customercontrolled-storage=avis-aux-agents-de-s%C3%A9curit%C3%A9-dans-le-cas-de-stockage-contr%C3%B4l%C3%A9-par-le-client h_01HE2S6FANRVGYPRWWFA50JAQ4=avis-aux-agents-de-s%C3%A9curit%C3%A9-dans-le-cas-de-stockage-contr%C3%B4l%C3%A9-par-le-client h_01HE2S6FANBRXA0NS4E8SP3618=multipleconnections-principles-more-than-one-destination procedures=proc%C3%A9dures h_01HE2S6FANEGZC1SAPSEK0EJJQ=proc%C3%A9dures h_01HE2S6FAN9ZQKVYH9PBN5GCB4=set-up-data-locker h_01HE2S6FANG1NGEDPXEKF5RNBD=reset-credentials additional-information=informations-suppl%C3%A9mentaires h_01HE2S6FAP4SA77B0SX7R8JMTY=informations-suppl%C3%A9mentaires h_01HE2S6FAP6FKAJCW92JVWD828=traits-and-limitations h_01HE2S6FAPJC20G7YZSRWP5E34=troubleshooting aws-data-retrieval=r%C3%A9cup%C3%A9ration-des-donn%C3%A9es-aws h_01HE2S6FAPJMKX567HSAR16TCN=r%C3%A9cup%C3%A9ration-des-donn%C3%A9es-aws h_01HE2S6FAPB5MW09Y4HKFV3RM8=aws-cli listing-files-and-folders=liste-des-fichiers-et-des-dossiers h_01HE2S6FAP31H9NK6V870FGXZF=liste-des-fichiers-et-des-dossiers h_01HE2S6FAP2E2TW4F5PJ4226Q0=cyberduck h_01HE2S6FAP74NG5VNEWKWXXJX2=amazon-s3-browser h_01HE7RB5N99WJ3XP69Z69H81AD=%C3%A0-consulter-%C3%A9galement" />
