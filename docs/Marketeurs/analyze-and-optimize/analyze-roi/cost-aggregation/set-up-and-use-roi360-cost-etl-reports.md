---
title: "ETL des coûts\_: coût de campagne détaillé dans un compartiment"
metadata:
  keywords:
    - Campaign
    - eCPI
    - clicks
    - Impressions
    - ROI
    - cost
    - Advertisers
    - Premium
    - Premium Feature
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - ROI360
  created_at: '2020-05-17T15:36:41Z'
  edited_at: '2024-07-09T08:45:29Z'
  id: 360008849238
  locale: fr
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/fr/articles/360008849238
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** L’ETL des coûts, qui fait partie de l’offre ROI360 AppsFlyer, offre aux annonceurs des données de coût de campagne par source média d’une grande précision. Les données (actualisées 4 fois par jour) sont transmises à votre compartiment AWS S3 ou GCS où elles peuvent être immédiatement importées dans les systèmes BI des annonceurs.

![5896_CostETL_graphic__2_.png](https://files.readme.io/3c9b8721fa4aba170c1ed7b7b365b4a5fe1cd74080469b3020d395352cede674-11178721788817.png)

## Fonctionnement de l’ETL des coûts

Les données de coût de la campagne sont inscrites :

* Dans votre compartiment pour que vous puissiez consulter, transférer et charger les données de coûts dans vos systèmes.
* Dans le compartiment 4 fois par jour (actualisation des données : <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">dans la journée)</Anchor>.
* Pour la journée en cours et les 6 jours précédents (nous parlons des «7 jours» dans cet article), ainsi que les jours 14, 29 et 88. Les données rétroactives permettent des mises à jour et des corrections dans le reporting des données de coût.
* Pour le coût matché à l'attribution, au clic ou à l'impression.  
  **Remarque** :
  * Les données des 7 derniers jours sont à nouveau extraites des sources média. Les données des jours 14, 29 et 88 sont traitées une seconde fois.
  * Seules les données de coûts sont mises à jour rétroactivement ; pas de données d'attribution.

Les données sont fournies de base avec les principales dimensions :

* Géo : répartition par pays
* Canal : canal de la source média, par exemple, dans le cas de Google il s’agit de YouTube

Vous pouvez personnaliser les autres dimensions, ainsi que les mesures disponibles dans les rapports.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRqyHRTiLq8KUtELHqdaF6yVTfNE22X5UmUqXX89oOK5ZpS6lksXD0401G8MFmsaEzg2Csvf-d3y08Z/pub?output=xlsx">Voir un exemple de fichier</Anchor>. **Remarque** : Cet exemple est celui d’un fichier Excel avec les données réparties par canal ; Les fichiers ETL des coûts sont envoyés à votre compartiment sous forme de fichiers Parquet.

## Mise en place

<div id="report-dimensions" />

<Accordion title="Dimensions du rapport">

* Les rapports concernent toutes les applications incluses dans l’ETL des coûts, par jour et par lot.
* Chaque fois que des données sont inscrites dans le compartiment, soit 4 fois par jour, elles représentent l’ensemble des données disponibles, y compris l'historique, les mises à jour et les corrections des 6 jours précédents, ainsi que les jours 14, 29 et 88. Merci de garder ces éléments en tête lorsque vous chargez vos données.
* La structure des rapports est détaillée dans le[tableau des champs de fichiers](/docs/set-up-and-use-roi360-cost-etl-reports#file-fields). La structure est :
  * **Rapport bilan**: Moins granulaire (détaillé) pour permettre une lecture plus rapide.
  * **Rapports de dimension** : Contiennent forcément une dimension de base. Cela signifie que la dimension est disponible pour chaque source média contenue dans ce rapport. Par contre, si une source média ne fournit pas les données de la dimension de base, ces données ne seront pas incluses dans le rapport de cette dimension. Les dimensions secondaires sont incluses lorsqu’elles sont disponibles. Elles ne sont pas toujours garanties.
  * Les dimensions de base (garanties) disponibles sont :  
    * Geo : Données regroupées par pays
    * Canal : Canal source média, par exemple YouTube dans le cas de Google et Instagram dans le cas des Meta ads.
  * Pensez à utiliser les dimensions et mesures qui répondent le mieux à votre entreprise. Elles peuvent varier selon la source média.
  * [Bêta fermé] **Rapport sur l’ensemble des coûts** : Basé sur la dimension geo. Inclut les données de coût pour toutes les activités marketing sur l’ensemble des plateformes, y compris pour les apps/plateformes qui n’ont pas été ajoutées à AppsFlyer (dans ce cas, l'ID d’app s’affiche comme inconnu.

</Accordion>

<div id="directory-and-filename-structure" />

<Accordion title="Structure des répertoires et noms des fichiers">

* Les données inscrites dans le compartiment ont la structure des répertoires et fichiers décrits. <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRqyHRTiLq8KUtELHqdaF6yVTfNE22X5UmUqXX89oOK5ZpS6lksXD0401G8MFmsaEzg2Csvf-d3y08Z/pub?output=xlsx">Voir un exemple de fichier</Anchor>. **Remarque** : cet exemple est celui d’un fichier Excel avec les données réparties par canal ; Les fichiers ETL des coûts sont envoyés à votre compartiment sous forme de fichiers Parquet.
* Lorsque l’ETL des coûts termine l’inscription dans un répertoire, un flag est défini au moment où le fichier *success* (réussi) est créé. Il s'agit toujours de l'horodatage le plus récent du répertoire.
* Chaque inscription des données inclut les données de la journée en cours et des 6 jours précédents (nous parlons des «7 jours» dans cet article), ainsi que des jours 14, 29 et 88.
* Le nombre de dossiers/fichiers est le suivant :  
  * Bilan : 4 lots de dossiers par jour.
    * Chaque lot de dossiers contient des fichiers Parquet avec 7 jours de données.
  * Dimensions : Chaque dimension garantie contient 4 lots de dossiers par jour.
    * Chaque lot de dossiers contient des fichiers parquet contenant des données numérotées (démarrant par 1).
  * [Bêta fermé] Tous les coûts : Basé sur la dimension géo, contient 4 lots de dossiers par jour.

**Exemple de structure de répertoire**

![cost_etl_structure_4.jpg](https://support.appsflyer.com/hc/article_attachments/360019240077)

**Structure du répertoire**

```
/<advertiser bucket name>/cost_etl/version/dt=<yyyy-mm-dd>/b=<n>/
<dimension>/<file name>
```

#### Structure du répertoire

| **Variable** | **Contenu** |
| --- | --- |
| advertiser\_bucket\_name | Tel que défini dans la configuration ETL des coûts : af-xpend-cost-etl-&lt;af-account-id>-[suffixe du nom de votre compartiment] |
| cost\_etl | Toujours cost\_etl |
| version | Version de l’ETL des coûts |
| date | Date du coût<br /><br />Format : aaaa-mm-jj |
| batch | Numéro 1-4 |
| dimension | Dimension des données :<ul><li>geo</li><li>canal</li></ul> |
| file\_name | <ul><li>Bilan</li><li>Tous les coûts</li></ul> |
| Parquet file number | <ul><li>La numérotation démarre à 00000</li><li>Exemple : `part-`</li></ul> |

**Structure du nom de fichier**

```
part-<number>
```

> 📄 **Exemple**
>
> Pour une première extraction de données du 23 juin 2020, la structure des répertoires et des noms de fichiers est la suivante :
>
> `/bucket-name/cost_etl/v1/dt=2020-06-23/b=1/geo/part-00001`

</Accordion>

<div id="file-fields" />

<Accordion title="Champs du fichier">

<div id="fieldsdimensions" />

#### Champs/Dimensions

| **Champ** | **Remarques** | **Toujours rempli** | **Format** | **Inclus dans le fichier bilan** |
| --- | --- | --- | --- | --- |
| date | Date où le coût a été rapporté par la source média | Oui | chaîne aaaa-mm-jj | ✓ |
| app\_id | ID de l'app sur la plateforme AppsFlyer | Oui | Chaîne | ✓ |
| media\_source | Source média qui affiche la publicité | Oui | Chaîne | ✓ |
| os | Système d'exploitation de l'appareil. Valeurs possibles :<ul><li>Android</li><li>Windows Phone</li><li>iOS</li></ul> | Oui | Chaîne | - |
| agency | Agence chargée de placer la publicité | Non | Chaîne | - |
| campagne | Composant de la hiérarchie publicitaire | Non | Chaîne | - |
| campaign\_id | Composant de la hiérarchie publicitaire | Non | Chaîne | - |
| adset | Composant de la hiérarchie publicitaire | Non | Chaîne | - |
| adset\_id | Composant de la hiérarchie publicitaire | Non | Chaîne | - |
| ad | Composant de la hiérarchie publicitaire | Non | Chaîne | - |
| ad\_id | Composant de la hiérarchie publicitaire | Non | Chaîne | - |
| ad\_account | <ul><li>Compte publicitaire d’où les données de coût ont été extraites</li><li>Concerne les réseaux où la connexion s'effectue via oAuth (connexion avec vos identifiants), comme dans Google ou Meta Ads</li></ul> | Non | Chaîne | - |
| devise | Devise des dépenses de l'annonceur telle que définie pour l'app dans AppsFlyer | Oui | Chaîne de 3 caractères au format ISO-4217 | ✓ |
| original\_currency | La devise du coût rapportée par le réseau avant toute conversion | Oui | Chaîne de 3 caractères au format ISO-4217 | - |
| timezone | <ul><li>Fuseau horaire des données telles que stockées dans AppsFlyer</li><li>Parfois, les réseaux transmettent les données dans un fuseau horaire différent de celui défini dans AppsFlyer. Cet aspect des données explique les écarts de coûts possibles entre AppsFlyer et les réseaux</li></ul> | Oui | Chaîne | - |
| geo | Dimension dans la hiérarchie publicitaire | Non | Chaîne de 2 caractères au format ISO 3166 | ✓ |
| canal | Dimension dans la hiérarchie publicitaire | Non | Chaîne | - |
| keyword\_term | Mot(s) utilisé(s) par l'internaute pour la recherche en ligne | Oui | Chaîne | - |
| keyword\_id | ID des termes du mot-clé ASA | Oui | Chaîne | - |
| site\_id | ID éditeur | Non | Chaîne | - |
| campaign\_objective | Composant des propriétés de la campagne. <Anchor target="_blank" href="/marketers/fr/docs/campaign-properties-in-cost-etl-reports">En savoir plus</Anchor> | Non | Chaîne | - |
| cost\_model | Composant des propriétés de la campagne. <Anchor target="_blank" href="/marketers/fr/docs/campaign-properties-in-cost-etl-reports">En savoir plus</Anchor> | Non | Chaîne | - |
| af\_cost\_model | Modèle de coût mappé et normalisé par AppsFlyer. Composant des propriétés de campagne. <Anchor target="_blank" href="/marketers/fr/docs/campaign-properties-in-cost-etl-reports">En savoir plus</Anchor> | Non | Chaîne | - |
| bid\_strategy | Composant des propriétés de la campagne. <Anchor target="_blank" href="/marketers/fr/docs/campaign-properties-in-cost-etl-reports">En savoir plus</Anchor> | Non | Chaîne | - |
| af\_bid\_strategy | Stratégie d'enchères mappée et normalisée par AppsFlyer. Composant des propriétés de campagne. <Anchor target="_blank" href="/marketers/fr/docs/campaign-properties-in-cost-etl-reports">En savoir plus</Anchor> | Non | Chaîne | - |
| bid\_amount | Composant des propriétés de la campagne. <Anchor target="_blank" href="/marketers/fr/docs/campaign-properties-in-cost-etl-reports">En savoir plus</Anchor> | Non | Entier | - |
| original\_bid\_amount | Composant des propriétés de la campagne. <Anchor target="_blank" href="/marketers/fr/docs/campaign-properties-in-cost-etl-reports">En savoir plus</Anchor> | Non | Entier | - |

<div id="metrics" />

#### Métriques

<table><thead><tr><th><p><strong>Champ</strong></p></th><th><p><strong>Remarques</strong></p></th><th><p><strong>Toujours rempli</strong></p></th><th><p><strong>Format</strong></p></th><th><p><strong>Inclus dans le fichier bilan</strong></p></th></tr></thead><tbody><tr><td><p><span>impressions</span></p></td><td><ul><li><span>Comptabilisé par AppsFlyer.</span></li><li><span>Inclut à la fois l’UA et le retargeting.</span></li></ul></td><td rowspan="13"><p>Oui.</p><p>Si aucune valeur n’est disponible pour une métrique donnée, elle affiche 0.</p></td><td><p><span>Entier</span></p></td><td><p><span><span>✓</span></span></p></td></tr><tr><td><p><span>Clics</span></p></td><td><ul><li><span>Comptabilisé par AppsFlyer.</span></li><li><span>Inclut à la fois l’UA et le retargeting.</span></li></ul></td><td><p><span>Entier</span></p></td><td><p><span><span>✓</span></span></p></td></tr><tr><td><p><span>reported_impressions</span></p></td><td><p><span>Comptabilisé par la source média</span></p></td><td><p><span>Entier</span></p></td><td><p><span><span>✓</span></span></p></td></tr><tr><td><p><span>reported_clicks</span></p></td><td><p><span>Comptabilisé par la source média</span></p></td><td><p><span>Entier</span></p></td><td><p><span><span>✓</span></span></p></td></tr><tr><td><p><span>installs</span></p></td><td><p><span>Comptabilisé par AppsFlyer</span></p></td><td><p><span>Entier</span></p></td><td><p><span><span>✓</span></span></p></td></tr><tr><td><p><span>reported_conversions</span></p></td><td><p><span>Comptabilisé par la source média</span></p></td><td><p><span>Entier</span></p></td><td></td></tr><tr><td><p><span>re_engagements</span></p></td><td><p><span>Comptabilisé par AppsFlyer</span></p></td><td><p><span>Entier</span></p></td><td><p><span><span>✓</span></span></p></td></tr><tr><td><p><span>re_attributions</span></p></td><td><p><span>Comptabilisé par AppsFlyer</span></p></td><td><p><span>Entier</span></p></td><td><p><span><span>✓</span></span></p></td></tr><tr><td><p><span>cost</span></p></td><td><p><span>Montant des dépenses (dont les éventuels frais d'agence)</span></p></td><td><p><span>Valeur</span></p></td><td><p><span><span>✓</span></span></p></td></tr><tr><td><p><span>original_cost</span></p></td><td><p><span>Coût rapporté par le réseau, dans la devise indiquée par le réseau et avant toute conversion de devise (avec frais d'agence calculés par AppsFlyer si applicables)</span></p></td><td>Valeur </td><td><p><span>-</span></p></td></tr><tr><td><p><span>impressions_discrepancy</span></p></td><td><ul><li><span>Différence entre le coût comptabilisé par le réseau publicitaire et AppsFlyer</span></li><li> <span>Ignorez cette métrique si :</span><ul><li><span>Il n'y a pas de match entre le coût et l'attribution.</span></li><li><span>Le réseau publicitaire ne prend pas en charge <a href="./roi360-cost-aggregation-overview#ad-networks-supporting-cost-api" target="_blank">les impressions rapportées.</a></span></li></ul></li></ul></td><td><span>Entier</span></td><td><p><span>-</span></p></td></tr><tr><td><p><span>clicks_discrepancy</span></p></td><td><ul><li><span>Différence entre le coût comptabilisé par le réseau publicitaire et AppsFlyer</span></li><li> <span>Ignorez cette métrique si :</span><ul><li><span>Il n'y a pas de match entre le coût et l'attribution.</span></li><li><span>Le réseau publicitaire ne prend pas en charge <a href="./roi360-cost-aggregation-overview#ad-networks-supporting-cost-api" target="_blank">les clics rapportés.</a></span></li></ul></li></ul></td><td><span>Entier</span></td><td><p><span>-</span></p></td></tr><tr><td><p><span>installs_discrepancy</span></p></td><td><ul><li><span>Différence entre le coût comptabilisé par le réseau publicitaire et AppsFlyer</span></li><li> <span>Ignorez cette métrique si :</span><ul><li><span>Il n'y a pas de match entre le coût et l'attribution.</span></li><li><span>Le réseau publicitaire ne prend pas en charge <a href="./roi360-cost-aggregation-overview#ad-networks-supporting-cost-api" target="_blank">les conversions rapportées.</a></span></li></ul></li></ul></td><td><span>Entier</span></td><td><p><span>-</span></p></td></tr><tr><td><p><span>fees</span></p></td><td><p><span>Les frais qu'une agence facture en plus du coût de base d’une publicité. </span><span></span><span><span>Comptabilisé par AppsFlyer</span></span></p></td><td><p>Oui</p></td><td><p><span>Entier</span></p></td><td><p><span>-</span></p></td></tr><tr><td><p><span>cost_without_fees</span></p></td><td><p><span>Le coût moins les frais d'agence. Comptabilisé par AppsFlyer</span><span></span></p></td><td><p>Oui</p></td><td><p><span>Entier</span></p></td><td><p><span><span><span>-</span></span></span></p></td></tr><tr><td><p><span>original_cost_without_fees</span></p></td><td>Coût d'origine tel que rapporté par le réseau publicitaire, frais d'agence non compris</td><td><p>Oui</p></td><td><p><span>Entier</span></p></td><td><p><span><span><span>-</span></span></span></p></td></tr><tr><td><p><span>ctr</span></p></td><td><ul><li><span>Taux post-clic Comptabilisé par AppsFlyer</span></li><li><span>Formule : Clics/impressions</span></li></ul></td><td rowspan="12"><p>Non</p></td><td><span>Entier</span></td><td><p><span>-</span></p></td></tr><tr><td><p><span>cvr</span></p></td><td><ul><li><span>Taux de conversion. Comptabilisé par AppsFlyer</span></li><li><span>Formule : Installations / clics</span></li></ul></td><td><span>Entier</span></td><td><p><span>-</span></p></td></tr><tr><td><p><span>eCPM</span></p></td><td><ul><li><span>Comptabilisé par AppsFlyer</span></li><li><span>Formule : (Coût / impressions) x 1000 </span></li></ul></td><td><span>Entier</span></td><td><p><span>- </span></p></td></tr><tr><td><p><span>cpi</span></p></td><td><ul><li><span>Comptabilisé par AppsFlyer</span></li><li><span>Formule : Coût/Installations</span></li></ul></td><td><span>Entier</span></td><td><p><span>- </span></p></td></tr><tr><td><p><span>ccvr</span></p></td><td><ul><li><span>Coût par conversion</span></li><li><p><span>Formule : Coût / (installations + réattributions + ré-engagements)</span></p></li></ul></td><td><span>Entier</span></td><td><p><span>- </span></p></td></tr><tr><td><p><span>cvvr</span></p></td><td><ul><li><span>Nombre de vidéos visualisées entièrement. Comptabilisé par AppsFlyer</span></li><li><span>Formule : Vidéos complètes/impressions</span></li></ul></td><td><span>Entier</span></td><td><p><span>-</span></p></td></tr><tr><td><p><span>reported_cvr</span></p></td><td><ul><li><span>Taux de conversion rapporté</span></li><li><span>Formule : Conversions rapportées/clics rapportés</span></li></ul></td><td><span>Entier</span></td><td><p><span>- </span></p></td></tr><tr><td><p><span>ecpc</span></p></td><td><ul><li><span>Comptabilisé par AppsFlyer</span></li><li><span>Formule : Coût/clics</span></li></ul></td><td><span>Entier</span></td><td><p><span>-</span></p></td></tr><tr><td><p><span>video_25p_views</span></p></td><td><p><span>Vidéo lue à 25 %. Rapporté par le réseau publicitaire</span></p></td><td><span>Entier</span></td><td><p><span>- </span></p></td></tr><tr><td><p><span>video_50p_views</span></p></td><td><p><span>Vidéo lue à 50 %. Rapporté par le réseau publicitaire</span></p></td><td><span>Entier</span></td><td><p><span>- </span></p></td></tr><tr><td><p><span>video_75p_views</span></p></td><td><p><span>Vidéo lue à 75 %  Rapporté par le réseau publicitaire</span></p></td><td><span>Entier</span></td><td><p><span>- </span></p></td></tr><tr><td><p><span>video_completions</span></p></td><td><p><span>Rapporté par le réseau publicitaire</span></p></td><td><span>Entier</span></td><td><p><span>- </span></p></td></tr></tbody></table>

</Accordion>

<div id="set-up-cost-etl-for-aws-s3" />

<Accordion title="Configurer l’ETL des coûts pour AWS S3">

Cette action de configuration doit être réalisée par un utilisateur admin.

**Avant de démarrer** :

* La configuration de l’ETL des coûts consiste à paramétrer votre compartiment AWS (et à donner à AppsFlyer l'autorisation d'y inscrire des données), puis à configurer l’ETL des coûts dans AppsFlyer.
* Vous aurez besoin des privilèges d'admin AWS et d'un accès à l'interface utilisateur AppsFlyer pour configurer l’ETL des coûts.
* Gardez les onglets AWS et AppsFlyer ouverts tout au long de la configuration.
* **Remarque** : la prise en charge du chiffrement du compartiment KMS est pour l’instant en bêta.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/4256ee1b617bf6f8fe1597e3a0d194b2d20b85b4cb8be41e0c9dee9396710605-4404934404753.png) Pour configurer votre compartiment AWS et votre ETL des coûts :**

1. Connectez-vous à la console AWS.
2. Ouvrez le service S3.
3. Pour créer le compartiment :
   1. Cliquez sur **Créer un compartiment**.
   2. Saisissez le**nom du compartiment** comme suit : Commencez par le préfixe (obligatoire) `af-xpend-cost-etl-acc--` puis ajoutez la suite en texte libre.
      * Votre `af-account-id` se trouve dans l'interface utilisateur d'AppsFlyer, comme le stipulent les étapes 7 à 9 ci-dessous.
      * Consultez les <Anchor target="_blank" href="https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html">Critères à suivre pour nommer les compartiments Amazon S3</Anchor>.
   3. Cliquez sur **Créer un compartiment**.
4. Dans AppsFlyer, dans le menu latéral, sélectionnez **Exporter** > **ETL des coûts**.
5. Activez **ETL des coûts**.
6. Dans **Calendrier des rapports**, sélectionnez le moment où vous souhaitez recevoir le premier rapport. Les rapports qui suivront arriveront environ toutes les 6 heures.
7. Ouvrez les **paramètres Amazon S3**.  

   [![](https://support.appsflyer.com/hc/article_attachments/360019202837)](https://support.appsflyer.com/hc/article_attachments/360019202837)
8. Sélectionnez la région de votre compartiment S3 dans la liste déroulante.  
   Si votre région n'est pas listée, contactez votre CSM.
9. Saisissez le nom de votre compartiment Amazon S3.
10. Cliquez sur **Suivant**.  
    L'extrait de code des règles du compartiment s'affiche.  

    [![](https://support.appsflyer.com/hc/article_attachments/360019263058)](https://support.appsflyer.com/hc/article_attachments/360019263058)
11. Copiez l'extrait de code des règles du compartiment et collez-le dans vos paramètres AWS.
    1. Dans AWS, sélectionnez le compartiment que vous avez créé pour l’ETL des coûts.
    2. Allez dans l'onglet **Autorisations**.
    3. Dans la section **Règles du compartiment**, cliquez sur **Modifier**.
    4. La fenêtre des règles du compartiment s'ouvre.
    5. Collez le code des règles du compartiment dans la fenêtre.
12. Dans vos paramètres ETL des coûts AppsFlyer, cliquez sur **Suivant**.  
    L'étape **Valider le compartiment** s'affiche.
13. Cliquez sur **Valider.**  
    Vérifiez que le message **Validation réussie** s'affiche.
14. Cliquez sur **Suivant**.
15. Sélectionnez une, plusieurs, ou l'ensemble des apps. Sélectionnez tout pour inclure automatiquement les apps que vous ajouterez par la suite.
16. Cliquez sur **Appliquer**.
17. Sélectionnez au moins une **dimension garantie** : Canal et/ou Géo.
18. Sélectionnez au moins une dimension supplémentaire.  

    [![](https://files.readme.io/dbbea34c466b2263638a0937392ab004eab471a9e44d4c3713d6487507cef14b-4476081988241.png)](https://files.readme.io/dbbea34c466b2263638a0937392ab004eab471a9e44d4c3713d6487507cef14b-4476081988241.png)
19. Sélectionnez au moins une mesure à inclure dans les rapports.   

    [![](https://files.readme.io/2b865bb9cdb355287d99e81278fed5fd374da80a9f93499bd7b75777c8d5d11e-360019263038.jpg)](https://files.readme.io/2b865bb9cdb355287d99e81278fed5fd374da80a9f93499bd7b75777c8d5d11e-360019263038.jpg)
20. Cliquez sur **Appliquer**.

</Accordion>

<div id="set-up-cost-etl-for-gcs" />

<Accordion title="Configurer l'ETL des coûts pour GCS">

Cette action de configuration doit être réalisée par un utilisateur admin.

**Avant de démarrer** :

* La configuration de l’ETL des coûts consiste à paramétrer votre compartiment GCS (et à donner à AppsFlyer l'autorisation d'y inscrire des données), puis à configurer l’ETL des coûts dans AppsFlyer.
* Vous aurez besoin des privilèges d'admin GCS et d'un accès à l'interface utilisateur AppsFlyer pour configurer l’ETL des coûts.
* Gardez les onglets GCS et AppsFlyer ouverts tout au long de la configuration.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/4256ee1b617bf6f8fe1597e3a0d194b2d20b85b4cb8be41e0c9dee9396710605-4404934404753.png) Pour configurer votre compartiment GCS et votre ETL des coûts :**

1. Connectez-vous à la console GCS.
2. Créez un compartiment.  
   Nommez le compartiment comme indiqué ci-après :
   * Commencez par le préfixe (obligatoire) `af-xpend-cost-etl-acc--` puis ajoutez la suite en texte libre.
   * Votre `af-account-id` se trouve dans l'IU d'AppsFlyer, comme le stipulent les étapes 6 à 8 ci-dessous.
   * Consultez les <Anchor target="_blank" href="https://cloud.google.com/storage/docs/naming-buckets">Critères à suivre pour nommer les compartiments GCS</Anchor>.
3. Dans AppsFlyer, dans le menu latéral, sélectionnez **Exporter** > **ETL des coûts**.
4. Activez **ETL des coûts**.
5. Dans **Calendrier des rapports**, sélectionnez le moment où vous souhaitez recevoir le premier rapport. Les rapports qui suivront arriveront environ toutes les 6 heures.
6. Ouvrez **Destination des données** et sélectionnez **Compartiment Google Cloud Storage (GCS)**.
7. Saisissez le nom de votre compartiment GCS.
8. Cliquez sur **Suivant**.  
   Le compte de service AppsFlyer s'affiche, il sert à définir les autorisations GCS.
9. Dans votre console GCS, définissez les <Anchor target="_blank" href="https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-iam">autorisations IAM</Anchor> pour le compartiment :
   1. Ajoutez le compte de service AppsFlyer comme principal compartiment ETL des coûts.
   2. Attribuez le rôle « Admin de stockage objet ».
10. Dans vos paramètres ETL des coûts AppsFlyer, cliquez sur **Suivant**.  
    L'étape **Valider le compartiment** s'affiche.
11. Cliquez sur **Valider.**  
    Vérifiez que le message **Validation réussie** s'affiche.
12. Cliquez sur **Suivant**.
13. Sélectionnez une, plusieurs, ou l'ensemble des apps. Sélectionnez tout pour inclure automatiquement les apps que vous ajouterez par la suite.
14. Cliquez sur **Appliquer**.
15. Sélectionnez au moins une **dimension garantie** : Canal et/ou Géo.
16. Sélectionnez au moins une dimension supplémentaire.  

    [![](https://files.readme.io/dbbea34c466b2263638a0937392ab004eab471a9e44d4c3713d6487507cef14b-4476081988241.png)](https://files.readme.io/dbbea34c466b2263638a0937392ab004eab471a9e44d4c3713d6487507cef14b-4476081988241.png)
17. Sélectionnez au moins une mesure à inclure dans les rapports.   

    [![](https://files.readme.io/2b865bb9cdb355287d99e81278fed5fd374da80a9f93499bd7b75777c8d5d11e-360019263038.jpg)](https://files.readme.io/2b865bb9cdb355287d99e81278fed5fd374da80a9f93499bd7b75777c8d5d11e-360019263038.jpg)
18. Cliquez sur **Appliquer**.

</Accordion>

<div id="aws-object-ownership" />

<Accordion title="Propriété des objets AWS">

Par Défaut, lorsque AppsFlyer écrit des objets dans votre compartiment AWS, le propriétaire de l'objet est AppsFlyer. En fonction de la manière dont sont chargées vos données, vous devrez peut-être remplacer le propriétaire par défaut le propriétaire du compartiment, c’est à dire vous.

**Pour modifier le propriétaire des objets de votre compartiment** :

1. Connectez-vous à la console de gestion AWS et ouvrez la console Amazon S3 à l'adresse <Anchor target="_blank" href="https://console.aws.amazon.com/s3/">https://console.aws.amazon.com/s3/</Anchor>.
2. Dans la liste **Compartiments**, choisissez le nom du compartiment pour lequel vous souhaitez activer le propriétaire des objets S3.
3. Allez dans l'onglet **Autorisations**.
4. Dans **Propriétaire des objets,** cliquez sur **Modifier**.
5. Sélectionnez **Propriétaire du compartiment préféré.**
6. Cliquez sur **Enregistrer**.

</Accordion>

<div id="best-practices" />

## Recommandations

<div id="override-data" />

<Accordion title="Remplacement des données">

Lors de l'extraction et de l'analyse de vos données, il est recommandé d'extraire les données pour une date et un lot précis, ou de remplacer toutes les données précédentes par celles des jours du lot en cours. Si vous ne le faites, vous risquez de voir les mêmes données se répéter.

Par exemple, le lot 1 du 20 février contient les données concernant la période du 14 au 20 février. Cependant, les lots inscrits le 19 février contenaient également les données allant du 14 au 19 février. Il vaut mieux remplacer les données reçues le 19 février pour les jours précédents par les données reçues dans le lot le plus récent (celui du 20 février).

</Accordion>

<div id="geo-versus-channel" />

<Accordion title="Géo et canal">

Tous les réseaux ne fournissent pas les données pour l’ensemble des dimensions. Les données géo et de canal dans les meta ads en sont les exemples les plus courants. C'est pourquoi deux ensembles de données séparés sont générés. L'ensemble des données géo contient forcément les données géo, et l'ensemble des données de canal contient forcément les données de canal.

Dans de nombreux cas, et pour beaucoup de sources média, les données des ensembles géo et de canal sont les mêmes. En les séparant vous pouvez donc utiliser au choix l’un des ensembles de données (soit géo, soit canal), en fonction de vos besoins.

Si l'accord d'intégration avec une source média n'inclut pas le canal, donnant comme résultat un canal vide, nous traitons les données comme si elles contenaient le canal.

</Accordion>

<div id="aggregate-data" />

<Accordion title="Données agrégées">

L’ETL des coûts offre des données flexibles et granulaires aussi précises que celles qui sont extraites d’un réseau publicitaire. Pour tirer les meilleures informations d’un ensemble de données souvent énorme, nous vous conseillons de regrouper les données en fonction des besoins de votre entreprise. Par exemple, si vous avez besoin de comprendre les données de coûts au niveau d’une campagne et d’un pays, utilisez ces dimensions.

</Accordion>

<div id="standardization-across-networks" />

<Accordion title="Standardisation entre les réseaux">

Tous les réseaux ne fournissent pas des données avec la même granularité. Par exemple, les Meta ads ne fournissent pas les données de coût d'ID de site, et les X Ads n’offrent pas de données de coût géo. Prenez ces éléments en considération pour agréger les données de l’ETL des coûts, et pensez à analyser les données correspondantes lorsque vous comparez les réseaux.

</Accordion>

<div id="compare-data" />

<Accordion title="Comparer les données">

l’ETL des coûts fournit des informations sur toutes vos données de coûts. Certaines campagnes de l’ETL des coûts n'apparaissent pas dans certains tableaux de bord AppsFlyer, par exemple les données des campagnes inactives (les campagnes sans aucune installation enregistrée). Pour comparer les données, recherchez un ID de campagne spécifique dans le tableau de bord général, puis comparez-le avec ses données de coût dans l’ETL des coûts. <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports">En savoir plus sur la disponibilité des données de coûts</Anchor>

</Accordion>

<div id="additional-information" />

## Informations supplémentaires

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique | Remarques |
| --- | --- |
| Fuseau horaire | Si le fuseau horaire est modifié, les données de coût sont dupliquées le jour du changement, ainsi que le jour suivant. <Anchor target="_blank" href="/marketers/fr/docs/changing-app-time-zone-settings">En savoir plus</Anchor> |
| Actualisation des données | <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">Dans la journée</Anchor> Lors de la configuration de l’ETL des coûts, vous devez définir le calendrier des rapports, c'est-à-dire le moment où vous souhaitez que les rapports arrivent. **Remarque** : Une fois que les données de coûts sont arrivées dans votre compartiment, le temps de transfert de ces données vers vos systèmes BI peut varier considérablement, et ce en fonction du rapport et de la taille du fichier Parquet, qui peut aller de quelques Ko à plusieurs Go. |

</Accordion>

<div data-zendesk-anchors="cost-etl-principles=fonctionnement-de-letl-des-co%C3%BBts h_01HA29GW8PVZJ8MP23K7QVR40J=fonctionnement-de-letl-des-co%C3%BBts implementation=mise-en-place h_01HA29GW8PZPME9GVCFDW4YJA6=mise-en-place h_01HA29GW8PBGSNK06ATZMRRV2K=report-dimensions h_01HA29GW8PWN30BCQCK29V0FTA=directory-and-filename-structure directory-structure=structure-du-r%C3%A9pertoire h_01HA29GW8P99TFVPPXECB3NA2F=structure-du-r%C3%A9pertoire h_01HA29GW8P0B1JJTGYDW863D7Z=file-fields fieldsdimensions=champsdimensions h_01HA29GW8PQATB4K5VJP1HD4NW=champsdimensions metrics=m%C3%A9triques h_01HA29GW8PZTS7XDWGYWXFZPYG=m%C3%A9triques h_01HA29GW8QJ13G4FX7PD3WXXCQ=set-up-cost-etl-for-aws-s3 h_01HA29GW8QYD8WST6NVG5AS298=set-up-cost-etl-for-gcs h_01HA29GW8Q6D630E8SDVSFYVG7=aws-object-ownership best-practices=recommandations h_01HA29GW8QKPQXE4GHECAC5R5X=recommandations h_01HA29GW8QHX8AMK4T7E85H7RS=override-data h_01HA29GW8QT5FNNYSWHCT99D68=geo-versus-channel h_01HA29GW8QA3FP46EMZVYDEZF3=aggregate-data h_01HA29GW8QPW0NXEMF1WGJMKSF=standardization-across-networks h_01HA29GW8Q3FNS0W7SKTG7S9R1=compare-data additional-information=informations-suppl%C3%A9mentaires h_01HA286GA6WPYVNN7KCXK7DGFM=informations-suppl%C3%A9mentaires h_01HA282W8WHHNDG75XZNSV2QQF=traits-and-limitations" />
