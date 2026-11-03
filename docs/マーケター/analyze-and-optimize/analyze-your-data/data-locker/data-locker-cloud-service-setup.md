---
title: Data Locker｜クラウドサービスの設定
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
  edited_at: '2026-10-14T09:32:57Z'
  id: 360017603577
  locale: ja
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/ja/articles/360017603577
---
> **概要**：Data Lockerからデータを受信するためのクラウドサービスを設定します。GCS、AWS、BigQuery、Snowflakeに対応しています。

Data Lockerでは、お客様が選択・所有するストレージ環境にデータをストリーミングできます。保存先として、バケットまたはデータウェアハウスを利用できます。利用するクラウドサービスに応じて、以下の手順で設定してください。

## バケット型クラウドストレージ

<div id="gcs-storage" />

<Accordion title="GCSストレージ">

開始する前に、以下を確認してください：

* このセクションの手順は、Google Cloud管理者が実施する必要があります。
* Data Lockerに書き込まれたファイルは、書き込みから25時間以上経過した後に削除できます。それ以前には削除しないでください。

**GCS管理者向け情報**

Data Lockerは、ストレージにデータをストリーミングするためのAppsFlyerソリューションです。

**要件**

* Data Locker専用のGCSバケットを作成してください。「専用」とは、他のサービスからそのバケットへデータを書き込まないことを意味します。
* 推奨バケット名：`af-datalocker`
* 以下の手順に従って、Data Lockerに必要な権限を付与してください。

**Data Lockerに権限を付与するには：**

以下の手順では、`data-locker-example`を、事前にData Locker用として作成したバケット名に置き換えてください。

1. GCSコンソールにログインします。
2. **Storage** > **Storage browser**の順に移動します。

   [![mceclip0.png](https://files.readme.io/933df60c2073a7eba97429f3cf95967ae04513a50a14e8c22ec9ee0a94f480d7-360016875898.png)](https://files.readme.io/933df60c2073a7eba97429f3cf95967ae04513a50a14e8c22ec9ee0a94f480d7-360016875898.png)
3. 事前に作成したバケット（例：`data-locker-example`）を選択します。
4. **Permissions**タブを開きます。
5. **+Add**をクリックします。  
   メンバーの追加画面が開きます。
6. 以下のように設定します：
   1. **New members**に、以下を貼り付けます：

      ```http
      af-data-delivery@af-raw-data.iam.gserviceaccount.com
      ```
   2. **Select a role**で、**Cloud storage** > **Storage Object Admin**を選択します。

      [![mceclip0.png](https://files.readme.io/925501e1f16f4276d4a7aa0be8a78c94057fbdf07d48929e55bafe489f01cd42-360017059798.png)](https://files.readme.io/925501e1f16f4276d4a7aa0be8a78c94057fbdf07d48929e55bafe489f01cd42-360017059798.png)
7. **Save**をクリックしてください。

</Accordion>

<div id="aws-storage" />

<Accordion title="AWSストレージ">

開始する前に、以下を確認してください：

* このセクションの手順は、AWS管理者が実施する必要があります。
* Data Lockerに書き込まれたファイルは、書き込みから25時間以上経過した後に削除できます。それ以前には削除しないでください。

**AWS管理者向け情報**

Data Lockerは、ストレージにデータをストリーミングするためのAppsFlyerソリューションです。

**要件**

* af-datalocker-mybucketのような名前のAWSバケットを作成します。バケット名の先頭には、必ずaf-datalocker-を付ける必要があります。af-datalocker-以降の文字列は任意です。
* 推奨形式は、af-datalocker-yyyy-mm-dd-hh-mm-free-textです。yyyy-mm-dd-hh-mmには現在の日時を入力し、その後に任意の文字列を追加します。

**AWSコンソール上の表示例**

![MyBucket.jpg](https://files.readme.io/b8a16d185279200026388e146cfb3eb03ae3c7737ac26da3aa0d116a0cf9c078-4403551836305.jpg)

バケットを作成したら、以下の手順でAppsFlyerに必要な権限を付与します。

**バケットを作成し、AppsFlyerに権限を付与するには：**

1. AWSコンソールにログインします。
2. S3サービスを開きます。
3. **バケットの作成方法**：
   1. **Create bucket**をクリックします。
   2. **Bucket name**に、`af-datalocker-`から始まる名前を入力します。その後に、前述のとおり任意の文字列を追加します。
   3. [サポート対象のAWSリージョン](#サポート対象のawsリージョン)のいずれかを指定します。
   4. **Create Bucket**をクリックします。
4. **AppsFlyerに権限を付与するには：**
   1. 作成したバケットを選択します。
   2. **Permissions**タブを開きます。
   3. **Bucket policy** セクションにて、**Edit**をクリックします。   
      Bucket policyウィンドウが開きます。
   4. 以下の内容を貼り付けます。

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
5. 上記のコード内にある`af-datalocker-my-bucket`を、実際に作成したバケット名に置き換えます。
6. ［任意］KMSで暗号化されたバケットをサポートする場合：**Key Policy**セクションで**Switch to policy view**を選択し、以下を**Statement配列**内に貼り付けます。

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
7. **変更を保存**をクリックします。
8. <Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers#data-lockerのレポート設定">Data Lockerの設定手順</Anchor>を完了します。

#### **サポート対象のAWSリージョン**

Data Lockerでは、以下のAWSリージョンをサポートしています。

* Asia Pacific (Tokyo)：`ap-northeast-1`
* Asia Pacific (Seoul)：`ap-northeast-2`
* Asia Pacific (Mumbai)：`ap-south-1`
* Asia Pacific (Singapore)：`ap-southeast-1`
* Asia Pacific (Sydney)：`ap-southeast-2`
* Canada (Central)：`ca-central-1`
* EU (Frankfurt)：`eu-central-1`
* EU (Ireland)：`eu-west-1`
* EU (London)：`eu-west-2`
* South America (São Paulo)：`sa-east-1`
* US East (N. Virginia)：`us-east-1`
* US East (Ohio)：`us-east-2`
* US West (N. California)：`us-west-1`
* US West (Oregon)：`us-west-2`

</Accordion>

<div id="beta--azure-storage" />

<Accordion title="Azureストレージ">

開始する前に、以下を確認してください：

* このセクションの手順は、Azure Cloud管理者が実施する必要があります。
* Data Lockerに書き込まれたファイルは、書き込みから25時間以上経過した後に削除できます。それ以前には削除しないでください。

**Azure管理者向けの情報**

Data Lockerは、ストレージアカウントにデータをストリーミングするためのAppsFlyerソリューションです。

**Data Locker用のストレージアカウントを設定するには：**

1. Azureポータルで[Azure storage accounts](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Storage%2FStorageAccounts)を開き、<Image alt="predict_dashboard_plus_symbol.png" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />**Create**をクリックして、AppsFlyerデータを受信するためのストレージアカウントを作成します。
2. **Basic**タブ > **Project details**で、ドロップダウンから以下を選択します。
   1. **Subscription**
   2. **Resource Group**  
      任意：Resource Groupが存在しない場合は、**Create new**をクリックして作成します。
3. **Instance details**で以下を設定します。
   1. **Storage account name**を入力します。
   2. ドロップダウンから**Region**を選択します。
4. **次に、Advanced** をクリックします。
5. **Security**タブで、**Enable Hierarchical namespace**を選択します。
6. **Review > Create**をクリックします。
7. デプロイが完了したら、[Azure storage accounts](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Storage%2FStorageAccounts)に戻り、新しく作成したアカウントを選択します。
8. **Access keys**を開き、以下をコピーします。 ・**Storage account name** ・いずれか1つの**key**
9. **Storage browser > Blob containers**に移動し、<Image alt="predict_dashboard_plus_symbol.png" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />**Add container**をクリックします。
   1. 新しいコンテナの**名称**を入力します。
   2. **Create**をクリックします。
10. 設定が完了したら、AppsFlyerで<Anchor target="_blank" href="https://hq1.appsflyer.com/datalocker/overview">**Data Locker**</Anchor> **> <Image alt="predict_dashboard_plus_symbol.png" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />新規接続**に移動します。
11. 新規接続のページで、以下を設定します。
    1. 接続名を入力します。
    2. **Azure Blob**を選択します。
    3. **Bucket Name**のフィールドに、手順9で作成したAzureの**Container name**を入力します。
    4. 手順8でコピーした**Storage account name**を入力します。
    5. 手順8でコピーした**Key**を入力します。
    6. **接続テスト**をクリックします。
    7. **保存**をクリックします。

</Accordion>

<div id="yandex" />

<Accordion title="［ベータ版］Yandex Cloudストレージ">

開始する前に、以下を確認してください：

* このセクションの手順は、ご利用のYandex Cloudの管理者が実行する必要があります。
* Data Lockerに書き込まれたファイルは、書き込みから25時間以上経過した後に削除できます。それ以前には削除しないでください。

**Yandex管理者向けの情報**

Data Lockerは、ストレージにデータをストリーミングするためのAppsFlyerソリューションです。

**バケットを作成し、Data Lockerの権限を付与する：**

1. <Anchor target="_blank" href="https://console.cloud.yandex.com/">Yandex Cloudコンソール</Anchor>で**Service Accounts**タブを開き、**Create service account**をクリックします。
2. サービスアカウントに名前を付けます。（例：`af-datalocker`）
3. サービスアカウント用のStatic Access Keyを作成します。サービスアカウントで
   1. **Create a new key**をクリックします。
   2. **Create static access key**を選択します。
   3. **Key ID**と**Secret Key**を保存します。
4. 新しく作成したサービスアカウントに、**storage.editor**権限を付与します。
   1. バケット設定で**Access Bindings**を開き、**Assign bindings**をクリックします。
   2. 新しいサービスアカウントに**storage.editor**ロールを追加し、**Save**をクリックします。
5. Data LockerでYandexを有効にするには、AppsFlyerのCSMにお問い合わせください。
6. 有効化後、<Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers#set-up-data-locker">Data Lockerの設定時</Anchor>に、Key IDとSecret Keyを使用します。

</Accordion>

## データウェアハウス型クラウドストレージ

<div id="bigquery" />

<Accordion title="BigQuery">

このセクションの手順は、BigQuery管理者が実行する必要があります。

**BigQuery管理者向けの情報**

Data Lockerは、ストレージにデータをストリーミングするためのAppsFlyerソリューションです。

**要件**

* BigQuery Datasetの作成

**BigQuery Datasetを作成するには：**

1. BigQueryで、新しいProjectを作成するか、既存のProjectを使用します。
2. Project内で**CREATE DATASET**をクリックします。[![GCSCreateDataSEt_1_.png](https://files.readme.io/702b81dcff4185ce98ad82afd0a9b545f99ef49e3f6292709f3b00330821472c-4405548469521.png)](https://files.readme.io/702b81dcff4185ce98ad82afd0a9b545f99ef49e3f6292709f3b00330821472c-4405548469521.png)
3. Datasetに適切なIDを設定します。

   > 📘 **注意**
   >
   > 送信先となるProjectまたはDatasetが、有効なBilling Accountに紐づいていることを確認してください。Billing Accountが設定されていない場合、Data LockerはBigQueryの送信先にテーブルを作成したり、データを書き込んだりできないため、接続設定に失敗する場合があります。

4. AppsFlyerにDatasetへのアクセス権を付与します。（<Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/control-access-to-resources-iam#grant_access_to_a_resource">参考：BigQueryの手順</Anchor>）
   * **Add principal**には、以下のAppsFlyerユーザーを指定してください：[datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com](mailto:datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com)
   * **役割の割り当て**では、BigQuery Data Editorを選択します。
5. 必要に応じて、残りの設定を完了します。

</Accordion>

<div id="snowflake" />

<Accordion title="Snowflake">

Data LockerをSnowflakeアカウントに接続できます。接続すると、データがSnowflakeへ送信されると同時に、選択したクラウドストレージでも引き続き利用できます。

**BI開発者向けの考慮事項**

* データの更新頻度は、バケットに提供されるデータと同じです。
* データのテーブル構造およびカラム構造は、Data Lockerバケットから直接取得できるデータと同等です。
* Snowflake Shareに行が追加される際、`_ingestion_time`カラムには、UTCではなくシステムのローカルタイムゾーンで値が設定されます。行の一意性を確保し、同じ行を複数回取り込まないようにするには、以下の対応を行ってください。
  1. 取り込んだテーブルごとに`max_ingestion_time`を保存します。
  2. 取り込み処理を実行するたびに、以下の条件を満たす行のみを取り込みます：`_ingestion_time > max_ingestion_time`

以下の手順に従って、SnowflakeをData Lockerに接続してください。

#### **Snowflakeコネクタの設定手順**

**SnowflakeのAccount IDとRegionを確認するには**：

1. Snowflakeで、<Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">Snowflakeアカウントにログイン</Anchor>します。
2. メニューバーから自分の名前を選択します。  
   Account IDとRegionが表示されます。

   [<Image alt="Snowflake account details" src="https://files.readme.io/6f508a5c2c6cd5dd84dd2639c73e62ff819e0a06ea3323d7a999a6b4fc717009-40394499797393.png" width="875px" />](https://files.readme.io/6f508a5c2c6cd5dd84dd2639c73e62ff819e0a06ea3323d7a999a6b4fc717009-40394499797393.png)

**Data LockerをSnowflakeに接続するには：**

1. AppsFlyerで、**Reports** > **Data Locker**に移動します。
2. Snowflakeを選択します。
3. Snowflakeから取得した情報を使用して、Snowflake RegionとAccount Locatorを入力します。
4. **Save**をクリックしてください。

**SnowflakeのShareからDatabaseを作成するには**：

1. Snowflakeで、<Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">Snowflakeアカウントにログイン</Anchor>します。
2. **Accountadmin**にロールを切り替えてください。<Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/data-share-consumers.html#creating-a-database-from-a-share">シェアからデータベースを作成</Anchor>を参照してください。
3. **Shares** を選択してください。
4. AppsFlyerのShareを選択します。（例：APPSFLYER\_ACC\_XXX\_DATA\_LOCKER）
5. **Create Database from Secure Share**をクリックし、必要な情報を入力します。**注意**Shared Database内のデータは一定期間（現在は14日間）のみ利用可能です。そのため、Shared Databaseからお客様自身のテーブルへデータを取り込む必要があります。
6. Database内に、取り込まれたテーブルが表示されます。テーブル名と構造は、Data Lockerバケット内のものと同等です。

</Accordion>

## 特性と制限

| 特性 | 説明 |
| --- | --- |
| AppsFlyerクラウド接続 | レポートを非圧縮の状態で保存することはできません。 |
| BigQuery DatasetのLocation変更 | BigQueryでDatasetのLocationを変更した場合、AppsFlyer側で接続を再保存する必要があります。AppsFlyerの接続設定自体を変更する必要がないため、そのままでは**Save**ボタンが無効になっています。一時的に設定を変更して接続を保存した後、その変更を元に戻し、もう一度接続を保存してください。 |
| サポート対象のSnowflake Region | **AWSでサポートされるRegion：**<ul><li>us-east-1</li><li>us-east-2</li><li>us-west-2</li><li>eu-west-1</li><li>eu-west-2</li><li>eu-west-3</li><li>eu-central-1</li><li>eu-north-1</li><li>ca-central-1</li><li>sa-east-1</li><li>ap-south-1</li><li>ap-southeast-1</li><li>ap-southeast-2</li><li>ap-northeast-1</li><li>ap-northeast-2</li><li>ap-northeast-3</li></ul>**AzureでサポートされるRegion：**<ul><li>australia-east</li><li>east-us-2</li><li>central-us</li><li>southcentral-us</li><li>west-europe</li><li>west-us-2</li></ul>**GCPでサポートされるRegion：**<ul><li>サポート対象は限定されています。利用するRegionがサポートされているかどうかについては、AppsFlyerサポートへお問い合わせください。</li></ul> |

<div data-zendesk-anchors="bucket-cloud-storage=%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E5%9E%8B%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8 h_01HE2SPKYZWFXA63YD5NK4KJRD=%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E5%9E%8B%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8 h_01HE2SPKYZM9QQCGFN86J7FNDY=gcs-storage h_01HE2SPKYZK4F9E22MG3K8SJE8=aws-storage supported-aws-regions=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E5%AF%BE%E8%B1%A1%E3%81%AEaws%E3%83%AA%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3 h_01J2DSZ4NVVMTTNSXP2Z9DAS0Q=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E5%AF%BE%E8%B1%A1%E3%81%AEaws%E3%83%AA%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3 %5Bbeta%5D-azure-storage=beta--azure-storage h_01HE2SRAJA94R8ZKHRBEFNKX8D=beta--azure-storage h_01HE2SPKYZXAXMKPH5DQV40X1W=yandex data-warehouse-cloud-storage=%E3%83%87%E3%83%BC%E3%82%BF%E3%82%A6%E3%82%A7%E3%82%A2%E3%83%8F%E3%82%A6%E3%82%B9%E5%9E%8B%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8 h_01HE2SPKYZ77X8WP9ZNRB1D05B=%E3%83%87%E3%83%BC%E3%82%BF%E3%82%A6%E3%82%A7%E3%82%A2%E3%83%8F%E3%82%A6%E3%82%B9%E5%9E%8B%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8 h_01HE2SPKYZMNW776CZRZAFVV5H=bigquery h_01JXQM7DAHD40DJYERY106H826=%E6%B3%A8%E6%84%8F h_01HE2SPKYZC3W4G3YXFM10H9D3=snowflake snowflake-connector-procedures=snowflake%E3%82%B3%E3%83%8D%E3%82%AF%E3%82%BF%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%89%8B%E9%A0%86 h_01HE2SPKYZ11B1MJYX2HRCS07D=snowflake%E3%82%B3%E3%83%8D%E3%82%AF%E3%82%BF%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%89%8B%E9%A0%86 traits-and-limitations=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01J6S6HS0H0M6GQ81WGZ3XT0P9=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01KYVRP8CVMD01EZY5561W2RCJ=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90" />
