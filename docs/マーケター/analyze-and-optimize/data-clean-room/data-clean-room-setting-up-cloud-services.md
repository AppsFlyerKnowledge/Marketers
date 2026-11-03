---
title: Data Clean Room — クラウドサービスの設定
metadata:
  keywords:
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
  created_at: '2022-03-06T08:23:55Z'
  edited_at: '2026-10-14T09:34:56Z'
  id: 4591167507217
  locale: ja
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/ja/articles/4591167507217
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 1つまたは複数のデータウェアハウス（BigQuery、Snowflake）やクラウドストレージバケット（Amazon S3、GCS）を設定し、Data Clean Roomとデータを共有し、レポートを受け取ります。

## 概要

Data Clean Room(DCR)を使用する準備として以下の設定が含まれます：

* DCRがシステム（カスタムソース）からファーストパーティデータを読み取るクラウドサービス / ロケーション。これらのロケーションは、**受信接続**を作成するために使用されます。
* 処理後にDCRがレポートを配信するクラウドサービス / ロケーション。これらのロケーションは、**送信接続**を作成するために使用されます。

受信接続または送信接続の作成は、次の2段階の手順になります：

* **ステップ#1 –** 選択したクラウドサービスのインターフェイスを使用して、DCRで使用する準備をします（本記事）。
* **ステップ#2 –** AppsFlyerプラットフォームを使用してそれらをDCRに接続します。（参照：<Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-working-with-connections">Data Clean Room — ソースの管理</Anchor>）

> 📘 **注意**
>
> ソースデータ要件の完全な情報については、<Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-working-with-sources#source-format">Data Clean Room — ソースの操作</Anchor>を参照してください：
>
> * データ形式（*すべてのソース*）
> * 表の列（*データウェアハウスのソース*）
> * ファイル名と形式（*クラウドストレージバケット内のソースの場合*）

### サポートされているクラウドサービス

DCRへの受信接続と送信接続には次の2種類のクラウドサービスがサポートされています。

* **データウェアハウス：** BigQueryとSnowflake
* **クラウドストレージバケット：** Amazon S3（AWS）とGCS

これらのサービスの1つまたは任意の組み合わせを、受信および送信接続に使用できます。

> 🚧 **重要！**
>
> * 1つのレポートに複数のカスタムソースを使用する場合は、クラウドストレージバケットに配置する必要があります。
> * Amazon S3 または GCS で同じクラウドストレージバケットを受信・送信接続の両方に使用することは非常に一般的です。これを設定する場合は、[特別な指示](/docs/data-clean-room-setting-up-cloud-services#同じクラウドストレージバケットを受信送信接続の両方に設定)に必ず従ってください。

## 受信接続にクラウドサービスの設定

次の項目の指示に従って、DCR受信接続で使用するために、選択したクラウドサービスを準備します。

### データウェアハウス – BigQuery および Snowflake

<div id="bigquery-inbound" />

<Accordion title="BigQuery">

**注記：** 次の手順は、Google Cloudの管理者が実行する必要があります。

**データセットの作成とDCRの権限付与：**

1. Google Cloudコンソールにログインします。
2. BigQuery ページにアクセスします。
3. 新規または既存の Google Cloudプロジェクトで、DCR専用データセットを作成します。
   1. **左側**のパネルで、プロジェクトIDの右側にある**アクション表示**ボタン<Image alt="BQ_view_actions_button.png" src="https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png" width="22px" /> をクリックします。
   2. **Create dataset**を選択します。

      <Image alt="BQ_create_dataset.png" src="https://files.readme.io/4f6b9e613b3fd83e0b461fdfae5d986f6eac003be5c3dfae78c42eae7b2c92bb-13879858009105.png" width="457px" />
   3. 開いた**右側**のパネルで、データセットの名前を入力します。必要に応じて他のオプションを選択します。
      * 文字、数字、アンダースコア (\_) のみを使用して任意の名前を使用できます。
        * **推奨：** データセットが受信接続に使用されていることを示す名前にします。
      * テーブルの期限が切れるとDCRはソースを読み取れなくなるため、**Enable table expiration**オプションを使用**しない**ことを強くお勧めします。
   4. <Image alt="BQ_create_dataset_button.png" src="https://files.readme.io/242c16aaa7e7f1f96b3392452260fa1c1987a8ebfd276c36630a028baa245b16-13879858133137.png" width="88px" /> ボタンをクリックします。
4. DCRにデータセットへのアクセス許可を付与します：
   1. **左側**のパネルで、プロジェクトIDの右側にある**アクション表示**ボタン<Image alt="BQ_view_actions_button.png" src="https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png" width="22px" /> をクリックします。
   2. **Share**を選択します。
   3. 開いた**右側**のパネルで、![BQ_add_principal_button.png](https://files.readme.io/77179cb4b9c81faa7cdc13397920699186df15fd1722247ccd8cbecb0cc43bce-13879857984017.png) ボタンをクリックします。
   4. **Add principals**項目で、**New principals**項目に次のアカウントを入力します：  
      `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
   5. **Assign roles**で **BigQuery> BigQuery Data Viewer**を選択します。

      <Image alt="BQ_data_viewer.png" src="https://files.readme.io/beec60ee830957ff265f8046875d1b8fa006a2c0cb60427ac969d7d45efa8b5b-14964740088721.png" width="311px" />
   6. **Save**をクリックしてください。
   7. **CLOSE**をクリックして、右側のパネルを閉じます。

</Accordion>

<div id="snowflake-inbound" />

<Accordion title="Snowflake">

**注記：** 次の手順は、Snowflakeの**アカウント管理者**が実行する必要があります。

**DCRで使用するプライベート共有の作成：**

1. DCRと共有するデータを含む<Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">Snowflakeアカウントにログイン</Anchor>します。
2. Account adminに**ロールを切り替え**ます。
3. 左パネルにある **Private Sharing**を選択します。
4. 開いたページで、**Shared By Your Account**タブを選択します。

   <Image alt="snowflake_private_sharing.png" src="https://files.readme.io/e99ddd6acf3a3714ea1818fc1d28489b0ea458abac3519d6e4fe67ab643de5bb-13879858362257.png" width="609px" />
5. **Share**ボタンをクリックしてください。 開いたリストから、**Create a Direct Share**を選択します。

   <Image alt="snowflake_create_direct_share.png" src="https://files.readme.io/0a33cddd326d03a13da19a1e1b4d75a7f6a9c5479dad2fdcad52f111bc5b4e14-13879858320913.png" width="219px" />
6. DCRと共有するテーブルやビューを選択し、**Done**をクリックします。
7. 必要に応じて、 **Secure Share Identifier**を変更し、オプションの説明を追加します。
8. **Add accounts in your region by name**項目に、Snowflakeアカウントの地域に応じて次のいずれかのAppsFlyer Snowflakeアカウントを入力します：

| 地域 | AppsFlyerアカウント |
| --- | --- |
| EU West (eu-west-1) | QL63117 |
| US East - N. Virginia (us-east-1) | MWB70410 |
| US East - Ohio (us-east-2) | BM15378 |

9. **Create Share**ボタンをクリックしてください。

</Accordion>

### クラウドストレージバケット – Amazon S3 および GCS

（Amazon S3、GCS、またはその両方での）DCRへのデータアップロードに、1つ以上のバケットを使用できます。ただしほとんどの場合、最も管理しやすい構造に含まれるのは、1つのクラウドサービスにバケット1つです。

* [この手順](/docs/data-clean-room-setting-up-cloud-services#同じクラウドストレージバケットを受信送信接続の両方に設定)に従い、受信・送信接続の両方の使用に同じバケットを設定できます。

<span id="both-cloud-services"></span>次の要件は、両方のクラウドサービスのバケットに関連しています：

* **利用：** バケットは、AppsFlyerのData Clean Room専用のものである必要があります。つまり、他のサービスはバケットにデータを書き込むことができません。
* **権限：** AppsFlyerのDCRサービスには、バケット権限を付与する必要があります。これらのアクセス許可を付与する手順については、以下の各クラウドサービスのタブを参照してください。
* **名前：** バケット名は必ず `af-dcr-` もしくは `af-datalocker-` で始まる必要があります。
  * 例： `af-dcr-example-bucket`
* <span id="dcr-naming-requirements"></span>**DCRの名称設定の要件：** 次の名称設定要件は、すべてのDCRデータエンティティ（バケット、フォルダ、およびファイル）に適用されます：
  * 最大文字数：200文字
  * 利用可能な有効文字：
    * 文字 `(A-Z, a-z)`
    * 数字 `(0-9)` - *最初の文字には使用できません*
    * ハイフン `(-)` - *名前の最初の文字にすることはできません*
    * 無効な文字：
      * スペース
      * その他すべての記号または特殊文字
    * 特別な目的にのみ使用される文字：
      * * 等号 `(=)` - *日付およびバージョンフォルダ名*<Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version">で必要な場合のみ</Anchor>
        * アンダースコア `(_)` - *multi-part GZIPファイル*<Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-working-with-sources#file-format">のパーツを識別するため</Anchor>*、または*<Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-working-with-sources#_success-files">\_SUCCESSファイル</Anchor>の命名に使用される場合のみ
        * ドット `(.)` - *ファイル名拡張子の直前のみ* `(.csv, .gzip)`

<div id="amazon-s3-inbound" />

<Accordion title="Amazon S3">

**注記：** 次の手順は、AWS管理者が実行する必要があります。

**バケットの作成とAppsFlyerへの権限付与：**

1. AWSコンソールにログインします。
2. S3サービスへ進みます。
3. バケットを作成します：
   1. **Create Bucket**をクリックします。
   2. **バケット名**を完成させ、`af-dcr-` または `af-datalocker-` で開始して、その後に（上記の [DCR命名要件](/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements)に従って）テキストを続けます。
   3. **Create Bucket**をクリックします。
4. <span id="step-4"></span>AppsFlyerバケットのアクセス許可を付与します：
   1. 作成したバケットを選択します。
   2. **権限**タブへ進んでください。
   3. **Bucket policy**セクションで <strong>Editをクリックしてください。</strong>バケットポリシーの編集/strong>画面が開きます。
   4. 次のコードスニペットをウィンドウに貼り付けます。

      ```json
      {
        "Version": "2012-10-17",
        "Statement": [
          {
            "Sid": "AF-DCR-DL",
            "Effect": "Allow",
            "Principal": {
              "AWS": [         "arn:aws:iam::195229424603:user/product=dcr-reporter__envtype=prod__ns=default",   "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
              ]
            },
            "Action": [
              "s3:GetObject",
              "s3:ListBucket",
              "s3:DeleteObject",
              "s3:PutObject"
            ],
            "Resource": [
              "arn:aws:s3:::af-dcr-mybucket",
              "arn:aws:s3:::af-dcr-mybucket/*"
            ]
          }
        ]
      }
      ```
5. スニペットで、（表示される2行にある）*`af-dcr-mybucket`* と作成したバケットの名前とを置き換えます。  
   **警告！スニペット内のバケット名を置き換えるときは、*バケット名が表示される 2 行目にある `/*` を上書きしないようご注意ください。***
6. **変更を保存**をクリックしてください。

</Accordion>

<div id="gcs-inbound" />

<Accordion title="GCS">

**注記：** 次の手順は、Google Cloudの管理者が実行する必要があります。

**バケットの作成とAppsFlyerへの権限付与：**

1. GCSコンソールにログインします。
2. クラウドストレージブラウザページに移動します。
3. バケットを作成します：
   1. **バケットを作成**をクリックします。
   2. **バケット作成**ページでバケット情報を入力します。バケット名を完成し、`af-dcr-` または `af-datalocker-` で始め、その後に（上記の[DCR命名要件](/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements)に従って）テキストを続けます。
   3. **次へ**をクリックします。
   4. **作成**をクリックします。
4. AppsFlyerバケットのアクセス許可を付与します：
   1. 作成したバケットを選択します。
   2. **権限**タブへ進んでください。
   3. アクセス許可セクションで、 **+ 追加** をクリックします。 **メンバーの追加画面が開きます。**
   4. ボックスに、次のアカウントを入力します：**New members** ボックスに、次のアカウントを入力します：  
      `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
   5. **役割**リストから、**クラウドストレージ** > **ストレージ管理者**を選択します。  

      ![dcr_gcs_permissions.png](https://files.readme.io/18c05537d96220c6a5b17f3f8344a5774193da68a30195bf3f4c1f660749f9b2-4726630155153.png)
   6. **Save**をクリックしてください。

</Accordion>

## 送信接続のクラウドサービスの設定

DCRは<Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers">AppsFlyer Data Locker</Anchor>を使用して、選択したクラウドサービスにレポートを配信します。

* **注記：** DCRレポートの受信にData Lockerの有料契約は必要ありません。Data Lockerによるその他のAppsFlyerレポートの受信についての詳細は、CSMにお問い合わせいただくか、 [hello@appsflyer.com](mailto:hello@appsflyer.com) にメールを送信してください。

DCRレポートは、（受信接続に同じサービスを使用するかどうかに関係なく）クラウドサービス上の1か所以上に配信できます。次の項目の指示に従って、送信接続に使用する準備をします。

### データウェアハウス – BigQuery および Snowflake

<div id="bigquery-outbound" />

<Accordion title="BigQuery">

**注記：** 次の手順は、Google Cloudの管理者が実行する必要があります。

**データセットの作成とData Lockerへの権限付与：**

1. Google Cloudコンソールにログインします。
2. BigQuery ページにアクセスします。
3. 新規または既存の Google Cloudプロジェクトで、Data Locker専用データセットを作成します。
   1. **左側**のパネルで、プロジェクトIDの右側にある**アクション表示**ボタン<Image alt="BQ_view_actions_button.png" src="https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png" width="22px" /> をクリックします。
   2. **Create dataset**を選択します。

      <Image alt="BQ_create_dataset.png" src="https://files.readme.io/4f6b9e613b3fd83e0b461fdfae5d986f6eac003be5c3dfae78c42eae7b2c92bb-13879858009105.png" width="457px" />
   3. 開いた**右側**のパネルで、データセットの名前を入力します。必要に応じて他のオプションを選択します。
      * 文字、数字、アンダースコア (\_) のみを使用して任意の名前を使用できます。
        * **推奨：** データセットが送信接続に使用されていることを示す名前にします。
      * 表の期限が切れるとData Lockerはデータセットにレポートを書き込めなくなるため、**Enable table expiration**オプションを使用**しない**ことを強くお勧めします。
   4. <Image alt="BQ_create_dataset_button.png" src="https://files.readme.io/242c16aaa7e7f1f96b3392452260fa1c1987a8ebfd276c36630a028baa245b16-13879858133137.png" width="88px" /> ボタンをクリックします。
4. Data Lockerにデータセットへのアクセス許可を付与します：
   1. **左側**のパネルで、プロジェクトIDの右側にある**アクション表示**ボタン<Image alt="BQ_view_actions_button.png" src="https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png" width="22px" /> をクリックします。
   2. **Share**を選択します。
   3. 開いた**右側**のパネルで、![BQ_add_principal_button.png](https://files.readme.io/77179cb4b9c81faa7cdc13397920699186df15fd1722247ccd8cbecb0cc43bce-13879857984017.png) ボタンをクリックします。
   4. **Add principals**項目で、**New principals**項目に次のアカウントを入力します：  
      `datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com`
   5. **Assign roles**で **BigQuery > BigQuery Data Editor**を選択します。

      <Image alt="BQ_data_editor.png" src="https://files.readme.io/cc26288d02f10805c971167d42d77efc9c7702f7fe231724b66eddd9b1b0e252-13879852726929.png" width="323px" />
   6. **Save**をクリックしてください。
   7. **CLOSE**をクリックして、右側のパネルを閉じます。

</Accordion>

<div id="snowflake-outbound" />

<Accordion title="Snowflake">

送信接続にSnowflakeを準備する手順は、<Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-working-with-connections#snowflake-outbound">送信接続の作成手順</Anchor>と組み合わせて完了させます。

</Accordion>

### クラウドストレージバケット – Amazon S3 および GCS

送信接続にクラウドストレージバケットを準備する手順は、[受信接続](/docs/data-clean-room-setting-up-cloud-services#受信接続にクラウドサービスの設定)にバケットを準備する手順と非常によく似ています（両方のクラウドストレージサービスに関する手順を含みます）。

以下の項目の手順は **送信接続にのみ**バケットを使用している場合に適用されます。

* 受信・送信接続の両方に同じバケットを使用する場合は、[セットアップの特別な手順](/docs/data-clean-room-setting-up-cloud-services#同じクラウドストレージバケットを受信送信接続の両方に設定)に従います。

<div id="amazon-s3-outbound" />

<Accordion title="Amazon S3">

[受信接続にAmazon S3バケット](/docs/data-clean-room-setting-up-cloud-services#amazon-s3-inbound)を作成する手順に従います（手順に変更はありません）。

</Accordion>

<div id="gcs-outbound" />

<Accordion title="GCS">

[受信接続用のGCSバケット](/docs/data-clean-room-setting-up-cloud-services#gcs-inbound)を作成する手順に従います。この手順のステップ 4 で、**New members**ボックスに次のアカウントを入力します：  
`af-data-delivery@af-raw-data.iam.gserviceaccount.com`

</Accordion>

## 同じクラウドストレージバケットを受信・送信接続の両方に設定

前述のように、Amazon S3 または GCS で同じバケットを受信・送信接続の両方に使用することは一般的です。

この設定の手順は[受信接続の手順](/docs/data-clean-room-setting-up-cloud-services#受信接続にクラウドサービスの設定)とほんの少し違うだけです。 ただし、以下を行っているかどうかによっては異なります：

* DCR受信および送信接続で使用する新規バケットを作成している - ***または***
* これまでData Lockerでのみ使用されていたバケットを、受信DCR接続および送信DCR接続の両方に使用されるバケットに変更している

これら両方のシナリオの手順は、以下のタブに含まれています：

<div id="amazon-s3-inbound-outbound" />

<Accordion title="Amazon S3">

#### 受信 / 送信接続用の新しいバケットを作成

[受信接続にAmazon S3バケット](/docs/data-clean-room-setting-up-cloud-services#amazon-s3-inbound)を作成する手順に従います（手順に変更はありません）。

#### これまでData Lockerにのみ使用されていた既存のバケットを変更

これまでData Lockerにのみ使用していた既存のバケットを変更するには、バケットのアクセス許可を変更する必要があります（DCRとData Lockerの両方によるアクセスを許可します）。

**バケットのアクセス許可を変更：**

1. AWSコンソールにログインします。
2. S3サービスへ進みます。
3. これまでData Lockerにのみ使用していたバケットを選択します。
4. **権限**タブへ進んでください。
5. **Bucket policy**セクションで <strong>Editをクリックしてください。</strong>バケットポリシーの編集/strong>画面が開きます。
6. ウィンドウの内容を次のコードスニペットに**置き換えます**。

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "AF-DCR-DL",
         "Effect": "Allow",
         "Principal": {
           "AWS": [         "arn:aws:iam::195229424603:user/product=dcr-reporter__envtype=prod__ns=default",   "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
           ]
         },
         "Action": [
           "s3:GetObject",
           "s3:ListBucket",
           "s3:DeleteObject",
           "s3:PutObject"
         ],
         "Resource": [
           "arn:aws:s3:::af-dcr-mybucket",
           "arn:aws:s3:::af-dcr-mybucket/*"
         ]
       }
     ]
   }
   ```

   * スニペットで、（表示される2行にある）*`af-dcr-mybucket`* と作成したバケットの名前とを置き換えます。
   * **警告！スニペット内のバケット名を置き換えるときは、*バケット名が表示される 2 行目にある `/*` を上書きしないようご注意ください。***
7. **変更を保存**をクリックしてください。

</Accordion>

<div id="gcs-inbound-outbound" />

<Accordion title="GCS">

#### 受信 / 送信接続用の新しいバケットを作成

[受信接続用のGCSバケット](/docs/data-clean-room-setting-up-cloud-services#gcs-inbound)を作成する手順に従います。この手順のステップ 4 を変更して、**New members** ボックスに次の**2つのアカウント**を入力します：  
`appsflyer-dcr@dcr-report.iam.gserviceaccount.com`  
`af-data-delivery@af-raw-data.iam.gserviceaccount.com`

#### これまでData Lockerにのみ使用されていた既存のバケットを変更

これまでData Lockerにのみ使用していた既存のバケットを変更するには、バケットのアクセス許可を変更する必要があります（DCRとData Lockerの両方によるアクセスを許可します）。

**バケットのアクセス許可を変更：**

1. GCSコンソールにログインします。
2. クラウドストレージブラウザのページに移動します。
3. これまでData Lockerにのみ使用していたバケットを選択します。
4. **権限**タブへ進んでください。
5. アクセス許可セクションで、 **+ 追加** をクリックします  
   **メンバーの追加**画面が開きます。
6. ボックスに、次のアカウントを入力します：**New members** ボックスに、次のアカウントを入力します：  
   `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
7. **役割**リストから、**クラウドストレージ** > **ストレージ管理者**を選択します。  

   ![dcr_gcs_permissions.png](https://files.readme.io/18c05537d96220c6a5b17f3f8344a5774193da68a30195bf3f4c1f660749f9b2-4726630155153.png)
8. **Save**をクリックしてください。

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01J6Y2P4CKMZ3R8WZ4X76DZ6ZY=%E6%A6%82%E8%A6%81 h_01J6Y2P4CMJ4CXJZ3EDDXQG4Y3=%E6%B3%A8%E6%84%8F supported-cloud-services=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%82%8B%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9 h_01J6Y2P4CMNMTSPWDK9GGSDYMJ=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%82%8B%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9 h_01J6Y2P4CM8VDWCD5XH91DJPYX=%E9%87%8D%E8%A6%81 setting-up-cloud-services-inbound=%E5%8F%97%E4%BF%A1%E6%8E%A5%E7%B6%9A%E3%81%AB%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E3%81%AE%E8%A8%AD%E5%AE%9A h_01J6Y2P4CM61DEXMWB626X25TT=%E5%8F%97%E4%BF%A1%E6%8E%A5%E7%B6%9A%E3%81%AB%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E3%81%AE%E8%A8%AD%E5%AE%9A data-warehouses-inbound=%E3%83%87%E3%83%BC%E3%82%BF%E3%82%A6%E3%82%A7%E3%82%A2%E3%83%8F%E3%82%A6%E3%82%B9--bigquery-%E3%81%8A%E3%82%88%E3%81%B3-snowflake h_01J6Y2P4CMDX64XXGNS7ZP3GKZ=%E3%83%87%E3%83%BC%E3%82%BF%E3%82%A6%E3%82%A7%E3%82%A2%E3%83%8F%E3%82%A6%E3%82%B9--bigquery-%E3%81%8A%E3%82%88%E3%81%B3-snowflake h_01J6Y2P4CMY5DHFEFGHQQPAPK9=bigquery-inbound h_01J6Y2P4CMMZFYDZWK82F5J65W=snowflake-inbound cloud-storage-buckets-inbound=%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8%E3%83%90%E3%82%B1%E3%83%83%E3%83%88--amazon-s3-%E3%81%8A%E3%82%88%E3%81%B3-gcs h_01J6Y2P4CMCJDT2W6C52MF71TB=%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8%E3%83%90%E3%82%B1%E3%83%83%E3%83%88--amazon-s3-%E3%81%8A%E3%82%88%E3%81%B3-gcs h_01J6Y2P4CMS2JF9Z7F13XW485F=amazon-s3-inbound code-snippet=%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8%E3%83%90%E3%82%B1%E3%83%83%E3%83%88--amazon-s3-%E3%81%8A%E3%82%88%E3%81%B3-gcs h_01J6Y2P4CM9Y9114CH1ESY0QPJ=gcs-inbound setting-up-cloud-services-outbound=%E9%80%81%E4%BF%A1%E6%8E%A5%E7%B6%9A%E3%81%AE%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E3%81%AE%E8%A8%AD%E5%AE%9A h_01J6Y2P4CMEEG6PNM2PMEYGQ3A=%E9%80%81%E4%BF%A1%E6%8E%A5%E7%B6%9A%E3%81%AE%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E3%81%AE%E8%A8%AD%E5%AE%9A data-warehouses-outbound=%E3%83%87%E3%83%BC%E3%82%BF%E3%82%A6%E3%82%A7%E3%82%A2%E3%83%8F%E3%82%A6%E3%82%B9--bigquery-%E3%81%8A%E3%82%88%E3%81%B3-snowflake-1 h_01J6Y2P4CMNWQ0D3EZXJZZM1EY=%E3%83%87%E3%83%BC%E3%82%BF%E3%82%A6%E3%82%A7%E3%82%A2%E3%83%8F%E3%82%A6%E3%82%B9--bigquery-%E3%81%8A%E3%82%88%E3%81%B3-snowflake-1 h_01J6Y2P4CM8MVS3SZAYE2YDV2T=bigquery-outbound h_01J6Y2P4CN97P8GCV314TQ91EE=snowflake-outbound cloud-storage-buckets-outbound=%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8%E3%83%90%E3%82%B1%E3%83%83%E3%83%88--amazon-s3-%E3%81%8A%E3%82%88%E3%81%B3-gcs-1 h_01J6Y2P4CNZ61PG9BTCVRFZ20K=%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8%E3%83%90%E3%82%B1%E3%83%83%E3%83%88--amazon-s3-%E3%81%8A%E3%82%88%E3%81%B3-gcs-1 h_01J6Y2P4CN4ZRAMQ2E3R4Q4KHS=amazon-s3-outbound h_01J6Y2P4CN39GT0QT6THFAA3ZY=gcs-outbound setting-up-cloud-services-inbound-outbound=%E5%90%8C%E3%81%98%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E3%82%92%E5%8F%97%E4%BF%A1%E9%80%81%E4%BF%A1%E6%8E%A5%E7%B6%9A%E3%81%AE%E4%B8%A1%E6%96%B9%E3%81%AB%E8%A8%AD%E5%AE%9A h_01J6Y2P4CN2ARMJKRSAFZNN59G=%E5%90%8C%E3%81%98%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E3%82%92%E5%8F%97%E4%BF%A1%E9%80%81%E4%BF%A1%E6%8E%A5%E7%B6%9A%E3%81%AE%E4%B8%A1%E6%96%B9%E3%81%AB%E8%A8%AD%E5%AE%9A h_01J6Y2P4CNKC9P1FKECHZJ6AXP=amazon-s3-inbound-outbound creating-a-new-bucket-for-inboundoutbound-connections=%E5%8F%97%E4%BF%A1--%E9%80%81%E4%BF%A1%E6%8E%A5%E7%B6%9A%E7%94%A8%E3%81%AE%E6%96%B0%E3%81%97%E3%81%84%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E3%82%92%E4%BD%9C%E6%88%90 h_01J6Y2P4CN216K0VZSWRP699TF=%E5%8F%97%E4%BF%A1--%E9%80%81%E4%BF%A1%E6%8E%A5%E7%B6%9A%E7%94%A8%E3%81%AE%E6%96%B0%E3%81%97%E3%81%84%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E3%82%92%E4%BD%9C%E6%88%90 modifying-an-existing-bucket-previously-used-only-for-data-locker=%E3%81%93%E3%82%8C%E3%81%BE%E3%81%A7data-locker%E3%81%AB%E3%81%AE%E3%81%BF%E4%BD%BF%E7%94%A8%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%81%9F%E6%97%A2%E5%AD%98%E3%81%AE%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E3%82%92%E5%A4%89%E6%9B%B4 h_01J6Y2P4CNDW888XTMKAMZAFCS=%E3%81%93%E3%82%8C%E3%81%BE%E3%81%A7data-locker%E3%81%AB%E3%81%AE%E3%81%BF%E4%BD%BF%E7%94%A8%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%81%9F%E6%97%A2%E5%AD%98%E3%81%AE%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E3%82%92%E5%A4%89%E6%9B%B4 h_01J6Y2P4CN0MEEKG0D2SKMDZVY=gcs-inbound-outbound creating-a-new-bucket-for-inboundoutbound-connections::e1cda9c8=%E5%8F%97%E4%BF%A1--%E9%80%81%E4%BF%A1%E6%8E%A5%E7%B6%9A%E7%94%A8%E3%81%AE%E6%96%B0%E3%81%97%E3%81%84%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E3%82%92%E4%BD%9C%E6%88%90-1 h_01J6Y2P4CN336CRH1CWRJVCHHY=%E5%8F%97%E4%BF%A1--%E9%80%81%E4%BF%A1%E6%8E%A5%E7%B6%9A%E7%94%A8%E3%81%AE%E6%96%B0%E3%81%97%E3%81%84%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E3%82%92%E4%BD%9C%E6%88%90-1 modifying-an-existing-bucket-previously-used-only-for-data-locker::ba0d4803=%E3%81%93%E3%82%8C%E3%81%BE%E3%81%A7data-locker%E3%81%AB%E3%81%AE%E3%81%BF%E4%BD%BF%E7%94%A8%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%81%9F%E6%97%A2%E5%AD%98%E3%81%AE%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E3%82%92%E5%A4%89%E6%9B%B4-1 h_01J6Y2P4CNYCTVGN6CH0748S24=%E3%81%93%E3%82%8C%E3%81%BE%E3%81%A7data-locker%E3%81%AB%E3%81%AE%E3%81%BF%E4%BD%BF%E7%94%A8%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%81%9F%E6%97%A2%E5%AD%98%E3%81%AE%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E3%82%92%E5%A4%89%E6%9B%B4-1" />
