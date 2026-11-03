---
title: Configuration du service cloud pour Data Locker
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2021-02-10T17:35:25Z'
  edited_at: '2023-11-06T08:35:34Z'
  id: 360017603577
  locale: fr
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/fr/articles/360017603577
---
> **En bref**  : configurez votre service cloud pour recevoir les données de Data Locker, avec GCS, AWS, BigQuery ou Snowflake.

Data Locker vous permet de diffuser des données vers la solution de stockage que vous avez choisie et dont vous êtes propriétaire, qu'il s'agisse d'un compartiment ou d'un entrepôt de données. Configurez votre service cloud via l'une des procédures suivantes.

## Stockage cloud en compartiment

<div id="gcs-storage" />

<Accordion title="Stockage GCS">

* La procédure décrite dans cette section doit être effectuée par votre admin Google Cloud.
* Vous pouvez supprimer n'importe quel fichier de Data Locker dans les 25 heures qui suivent son enregistrement. Ne supprimez aucun fichier avant ce délai.

**Informations pour l'admin GCS**

Data Locker est la solution AppsFlyer permettant d'envoyer les données vers un stockage.

**Exigences**

* Créez un compartiment GCS réservé à l'utilisation de Data Locker. «Réservé» signifie qu'aucun autre service n'inscrit de données dans ce compartiment.
* Nom de compartiment suggéré : `af-datalocker`.
* Accordez des autorisations Data Locker à l'aide de la procédure suivante.

**Pour accorder des autorisations Data Locker :**

Dans cette procédure, remplacez `data-locker-example` par le nom du compartiment que vous avez précédemment créé pour Data Locker.

1. Connectez-vous à votre console GCS.
2. Rendez-vous dans **Stockage** > **Navigateur** **de stockage**.  

   [![mceclip0.png](https://files.readme.io/933df60c2073a7eba97429f3cf95967ae04513a50a14e8c22ec9ee0a94f480d7-360016875898.png)](https://files.readme.io/933df60c2073a7eba97429f3cf95967ae04513a50a14e8c22ec9ee0a94f480d7-360016875898.png)
3. Sélectionnez le compartiment que vous avez précédemment créé, par exemple `data-locker-example`.
4. Allez dans l'onglet **Permissions**.
5. Cliquez sur **+ Ajouter**.  
   La fenêtre Ajouter des membres s'ouvre.
6. Renseignez les champs de la façon suivante :
   1. **Nouveaux membres**, collez l'extrait de code qui suit.

      ```http
      af-data-delivery@af-raw-data.iam.gserviceaccount.com
      ```
   2. **Sélectionnez un rôle** : **Stockage Cloud** > **Admin des objets de stockage**.  

      [![mceclip0.png](https://files.readme.io/925501e1f16f4276d4a7aa0be8a78c94057fbdf07d48929e55bafe489f01cd42-360017059798.png)](https://files.readme.io/925501e1f16f4276d4a7aa0be8a78c94057fbdf07d48929e55bafe489f01cd42-360017059798.png)
7. Cliquez sur **Enregistrer**.

</Accordion>

<div id="aws-storage" />

<Accordion title="Stockage AWS">

* La procédure décrite dans cette section doit être effectuée par votre admin AWS.
* Vous pouvez supprimer n'importe quel fichier de Data Locker dans les 25 heures qui suivent son enregistrement. Ne supprimer rien avant ce délai.

**Informations pour l'admin AWS**

Data Locker est la solution AppsFlyer permettant d'envoyer les données vers un stockage.

**Exigences**

* Créez un compartiment AWS portant le nom af-datalocker-mybucket. Le préfixe af-datalocker- est obligatoire. Le suffixe est libre.
* Nous vous suggérons af-datalocker-aaaa-mm-jj-hh-mm-texte-libre. aaaa-mm-jj-hh-mm correspond à la date et à l'heure actuelles, et vous ajoutez tout autre texte tel qu'indiqué dans la figure suivante.

**Interface utilisateur dans la console AWS**

![MyBucket.jpg](https://files.readme.io/b8a16d185279200026388e146cfb3eb03ae3c7737ac26da3aa0d116a0cf9c078-4403551836305.jpg)

Après avoir créé le compartiment, accordez les autorisations AppsFlyer en suivant la procédure ci-dessous.

**Pour créer un compartiment et accorder des autorisations à AppsFlyer :**

1. Connectez-vous à la console AWS.
2. Accédez au service S3.
3. **Pour créer le compartiment**:
   1. Cliquez sur **Créer un compartiment**.
   2. Complétez le **nom du compartiment** comme suit : commencez par `af-datalocker-`, puis ajoutez tout autre texte tel que décrit précédemment.
   3. Cliquez sur **Créer un compartiment**.
4. **Pour accorder les autorisations AppsFlyer :**
   1. Sélectionnez le compartiment.
   2. Allez dans l'onglet **Permissions**.
   3. Dans la section **Politique relative aux compartiments**, cliquez sur **Modifier**.   
      La fenêtre de la politique du compartiment s'ouvre.
   4. Collez l'extrait suivant dans la fenêtre.

      ```json
      {
        "Version": "2012-10-17",
        "Statement": [
          {
            "Sid": "AF_DataLocker_Direct",
            "Effect": "Allow",
            "Principal": {
              "AWS": "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
            },
            "Action": [
              "s3:GetObject",
              "s3:ListBucket",
              "s3:DeleteObject",
              "s3:PutObject"
            ],
            "Resource": [
              "arn:aws:s3:::af-datalocker-my-bucket",
              "arn:aws:s3:::af-datalocker-my-bucket/*"
            ]
          }
        ]
      }
      ```
5. Dans l'extrait de code, remplacez `af-data-locker-my-bucket` par le nom du compartiment que vous avez créé.
6. [Facultatif] Ajoutez la prise en charge des compartiments chiffrés KMS. Pour ce faire, dans la section **Politique de clé** , choisissez **Passer à l'affichage des politiques** et collez l'extrait suivant dans le tableau **de déclarations.**

   ```json
   {
         "Sid": "Allow use of the key",
         "Effect": "Allow",
         "Principal": {
             "AWS": "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
         },
         "Action": "kms:GenerateDataKey*",
         "Resource": "*"
     }
   ```
7. Cliquez sur **Enregistrer les modifications**.
8. Effectuez la <Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers#set-up-data-locker">procédure d'installation du Data Locker.</Anchor>

</Accordion>

<div id="beta--azure-storage" />

<Accordion title="[Beta] Stockage Azure">

* La procédure décrite dans cette section doit être effectuée par votre admin Azure Cloud.
* Vous pouvez supprimer n'importe quel fichier de Data Locker dans les 25 heures qui suivent son enregistrement. Ne supprimez aucun fichier avant ce délai.

**Informations pour l'admin Azure**

Data Locker est la solution AppsFlyer permettant d'envoyer les données vers un de vos comptes de stockage.

**Pour définir un compte de stockage pour Data Locker :**

1. Allez dans [Comptes de stockage Azure](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Storage%2FStorageAccounts)
2. Créez un nouveau compte de stockage pour récupérer vos données Appsflyer
3. Facultatif : créez un nouveau groupe de ressources (si aucun n'existe déjà)
4. Choisissez un abonnement, donnez un nom à votre nouveau compte de stockage et choisissez la région qui convient.
5. Activez l'espace de noms Hierarchical
6. Contactez votre CSM pour activer Azure dans Data Locker (une fois activé, vous aurez besoin du nom du compte de stockage ci-dessus et de sa clé pour entrer dans l'assistant de nouvelle connexion Data Locker).

</Accordion>

<div id="yandex" />

<Accordion title="[Beta] Stockage Yandex Cloud">

* La procédure décrite dans cette section doit être effectuée par votre admin Yandex Cloud.
* Vous pouvez supprimer n'importe quel fichier de Data Locker dans les 25 heures qui suivent son enregistrement. Ne supprimez aucun fichier avant ce délai.

**Infos pour l'admin Yandex**

Data Locker est la solution AppsFlyer permettant d'envoyer les données vers un stockage.

**Pour créer un compartiment et accorder des autorisations à Data Locker :**

1. Dans votre console <Anchor target="_blank" href="https://console.cloud.yandex.com/">Yandex Cloud</Anchor>, allez dans l'onglet **Comptes de service** et cliquez sur **Créer un compte de service**.
2. Donnez un nom au compte de service, ex. `af-datalocker`.
3. Créez une clé d'accès statique pour le compte de service. Dans le compte de service :
   1. Cliquez sur **Créer une nouvelle clé**.
   2. Sélectionnez **Créer une clé d'accès statique**.
   3. Enregistrez l'**ID de clé** ainsi que la **clé secrète**.
4. Donnez à votre nouveau compte de service l'autorisation **storage.editor** .
   1. Dans les paramètres de votre compartiment, allez dans **Combinaisons d'accès** et cliquez sur **Assigner une combinaison**.
   2. Pour votre nouveau compte de service, ajoutez le rôle **storage.editor** puis cliquez sur **Enregistrer**.
5. Contactez votre CSM AppsFlyer pour activer Yandex dans Data Locker.
6. Une fois l'option activée, utilisez l'ID de clé et la clé secrète pour configurer <Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers#set-up-data-locker">Data Locker</Anchor>.

</Accordion>

## Stockage cloud en entrepôt de données

<div id="bigquery" />

<Accordion title="BigQuery">

La procédure décrite dans cette section doit être effectuée par votre admin BigQuery.

**Informations destinées à l'admin BigQuery**

Data Locker est la solution AppsFlyer permettant d'envoyer les données vers un stockage.

**Exigences**

* <span id="step-1-create-a-bigquery-dataset"></span>Créez un ensemble de données BigQuery

**Pour créer un ensemble de données BigQuery :**

1. Dans BigQuery, créez un projet ou utilisez un projet existant.
2. Dans le projet, cliquez sur  **CRÉER UN ENSEMBLE DE DONNÉES**.

   [![GCSCreateDataSEt_1_.png](https://files.readme.io/702b81dcff4185ce98ad82afd0a9b545f99ef49e3f6292709f3b00330821472c-4405548469521.png)](https://files.readme.io/702b81dcff4185ce98ad82afd0a9b545f99ef49e3f6292709f3b00330821472c-4405548469521.png)
3. Donnez un ID approprié à l'ensemble de données.
4. Accordez à AppsFlyer l'accès à l'ensemble de données. <Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/control-access-to-resources-iam#grant_access_to_a_resource">Voir les instructions de Big Query</Anchor>
   * Pour **ajouter l'utilisateur principal**, utilisez l'utilisateur AppsFlyer suivant : [datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com](mailto:datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com)
   * Pour **assigner des rôles**, sélectionnez BigQuery Data Editor.
5. Renseignez les paramètres restants selon les besoins.

</Accordion>

<div id="snowflake" />

<Accordion title="Snowflake">

Connectez Data Locker à votre compte Snowflake. Les données sont envoyées à Snowflake et restent disponibles dans le stockage Cloud de votre choix.

**À l'attention des développeurs BI**

* Le taux d'actualisation des données est le même que celui des données présentes dans le compartiment.
* La structure des tableaux et des colonnes de données est la même que pour les données issues directement d'un compartiment Data Locker.
* Au fur et à mesure que les lignes s'ajoutent au partage Snowflake, la colonne `_ingestion_time` se remplit. Pour qu'aucune ligne ne se retrouve en double et pour éviter l'ingestion d'une même ligne plusieurs fois vous devez :
  1. Enregistrer un `max_ingestion_time` pour chaque tableau ingéré.
  2. Pour chaque processus d'ingestion, n'ingérez que les lignes qui suivent la règle suivante : `_ingestion_time > max_ingestion_time`

Effectuez les opérations suivantes pour connecter Snowflake à Data Locker.

#### **Procédure pour connecter Snowflake**

**Pour obtenir votre ID de compte et votre région Snowflake** :

1. Dans Snowflake, <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">connectez-vous à votre compte Snowflake</Anchor>.
2. Dans la barre des menus, sélectionnez votre nom.  
   Votre ID de compte et votre région s'affichent.  

   [![SnowflakeAccountId.png](https://files.readme.io/146dc699865a8a72780ba409d37ca1206767943e27221bec635b9fb49ffc7223-4412207884433.png)](https://files.readme.io/146dc699865a8a72780ba409d37ca1206767943e27221bec635b9fb49ffc7223-4412207884433.png)

**Pour connecter Data Locker à Snowflake** :

1. Dans AppsFlyer, allez dans **Integration** > **Data Locker.**
2. Sélectionnez Snowflake.
3. Saisissez la **région Snowflake** et l **'ID du compte Snowflake** à l'aide des éléments fournis par Snowflake.
4. Cliquez sur ***Enregistrer***.

**Pour** **créer une base de données à partir d'un partage Snowflake** :

1. Dans Snowflake, <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">connectez-vous à votre compte Snowflake</Anchor>.
2. Passez au rôle **Accountadmin** (admin de compte). Cf <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/data-share-consumers.html#creating-a-database-from-a-share.">Créer une base de données à partir d'un partage.</Anchor>
3. Sélectionnez **Partages**.
4. Sélectionnez le partage AppsFlyer. Ex : APPSFLYER\_ACC\_XXX\_DATA\_LOCKER.
5. Cliquez sur **Créer une base de données depuis un partage sécurisé** et renseignez les infos telles que demandées. **Important** ! Vous devez importer les données de la base de données partagée dans vos tableaux, en effet les éléments de la base de données partagée ne sont accessibles que sur une période restreinte (actuellement : 14 jours).
6. Dans votre base de données, les tableaux importés s'affichent. Le nom et la structure des tableaux sont les mêmes que dans Data Locker.

</Accordion>

<div data-zendesk-anchors="bucket-cloud-storage=stockage-cloud-en-compartiment h_01HE2SPKYZWFXA63YD5NK4KJRD=stockage-cloud-en-compartiment h_01HE2SPKYZM9QQCGFN86J7FNDY=gcs-storage h_01HE2SPKYZK4F9E22MG3K8SJE8=aws-storage %5Bbeta%5D-azure-storage=beta--azure-storage h_01HE2SRAJA94R8ZKHRBEFNKX8D=beta--azure-storage h_01HE2SPKYZXAXMKPH5DQV40X1W=yandex data-warehouse-cloud-storage=stockage-cloud-en-entrep%C3%B4t-de-donn%C3%A9es h_01HE2SPKYZ77X8WP9ZNRB1D05B=stockage-cloud-en-entrep%C3%B4t-de-donn%C3%A9es h_01HE2SPKYZMNW776CZRZAFVV5H=bigquery step-1%E2%80%94create-a-bigquery-dataset=step-1-create-a-bigquery-dataset h_01HE2SPKYZC3W4G3YXFM10H9D3=snowflake snowflake-connector-procedures=proc%C3%A9dure-pour-connecter-snowflake h_01HE2SPKYZ11B1MJYX2HRCS07D=proc%C3%A9dure-pour-connecter-snowflake" />
