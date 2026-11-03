---
title: Data Collaboration Platform（DCP）｜クラウドサービスの設定
metadata:
  keywords:
    - Marketers
    - Audience Activation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Audience Activation
  created_at: '2024-04-28T14:01:34Z'
  edited_at: '2026-10-19T18:52:38Z'
  id: 24604528827921
  locale: ja
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/ja/articles/24604528827921
---
> **概要：** ソースデータをDCPへ接続し、オーディエンスをクラウドストレージバケットへエクスポートできるよう、クラウドサービスを設定します。

## クラウドサービス設定について

DCPでは、クラウドサービスとプラットフォーム間でデータをやり取りするために、2種類の接続を使用します。

* **ソース接続：** ファーストパーティデータをDCPに接続し、コラボレーションやオーディエンス作成に利用できます。
* **クラウドストレージ接続：** オーディエンスが更新されるたびに、オーディエンスをクラウドストレージバケットへエクスポートできます。

接続の設定は、以下の2つのステップで行います。

* **ステップ1：** クラウドサービス側のインターフェースで、DCPから利用できるように準備します。
* **ステップ2：** AppsFlyerプラットフォームでDCPに接続します。 <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-add-connections">Data Collaboration Platform（DCP）— 接続の追加</Anchor>を参照してください。

接続タイプごとに対応しているサービスは、以下の表のとおりです。

| クラウドサービス | ソース（受信） | クラウドストレージ（送信） |
| --- | --- | --- |
| Amazon S3 | ✓ | ✓ |
| Google Cloud Storage（GCS） | ✓ | ✓ |
| BigQuery | ✓ | - |
| Snowflake | ✓ | - |
| Salesforce Cloud/CRM | ✓ | - |

Amazon S3とGCSでは、ソース接続とクラウドストレージ接続のどちらにも同じバケット設定と権限が適用されるため、方向ごとに個別の設定は必要ありません。ソース接続を作成すると対応するクラウドストレージ接続も自動的に作成され、その逆も同様です。また、一方を削除するともう一方も削除されます。これは、両方のタブで同じ基盤接続を共有しているためです。

## クラウドサービスの設定

以下からクラウドサービスを選択し、設定手順を確認してください。

<div id="amazon-s3" />

<Accordion title="Amazon S3">

以下の手順に従って、DCPで使用するAmazon S3バケットを準備します。

> 📘 **注意**
>
> 以下の手順は、AWS管理者が実施する必要があります。

**バケットの作成：**

1. AWSコンソールにログインします。
2. S3サービスへ移動します。
3. バケットを作成します。
   1. **Create bucket**をクリックします。
   2. **Bucket name**に、`af-dcr-`で始まる名前を入力します。

       続けて、[DCRの命名要件](#dcr-naming-requirements)に従って任意の文字列を入力します。
   3. **Create bucket**をクリックします。

**AppsFlyerにバケット権限を付与するには：**

1. 作成したバケットを選択します。
2. **Permissions**タブへ移動します。
3. **Bucket policy**セクションで、**Edit**をクリックします。 **Edit bucket policy**ウィンドウが開きます。
4. 以下のコードスニペットをウィンドウに貼り付けます。

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "AF-DCR-DL",
         "Effect": "Allow",
         "Principal": {
           "AWS": [
             "arn:aws:iam::195229424603:user/product=dcr-reporter__envtype=prod__ns=default",
             "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
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
5. コードスニペット内の`af-dcr-mybucket`（2か所）を、作成したバケット名に置き換えます。
6. **Save changes**をクリックします。

> 🚧 **重要**
>
> コードスニペットのバケット名を置き換える際は、2か所目のバケット名の後ろにある`/*`を上書きしないでください。

</Accordion>

<div id="google-cloud-storage-gcs" />

<Accordion title="Google Cloud Storage（GCS）">

以下の手順に従って、DCPで使用するGCSバケットを準備します。

> 📘 **注意**
>
> 以下の手順は、Google Cloud管理者が実施する必要があります。

**バケットの作成：**

1. GCSコンソールにログインします。
2. Cloud Storage Browserページへ移動します。
3. バケットを作成します。
   1. **Create bucket**をクリックします。
   2. **Create a bucket**ページでバケット情報を入力します。バケット名は`af-dcr-`で始めます。

       続けて、[DCRの命名要件](#dcr-naming-requirements)に従って任意の文字列を入力します。
   3. **Continue**をクリックします。
   4. **Create**をクリックします。

**AppsFlyerにバケット権限を付与するには：**

1. 作成したバケットを選択します。
2. **Permissions**タブへ移動します。
3. **Permissions**セクションで、**+ Add**をクリックします。 **Add members**ウィンドウが開きます。
4. **New members**ボックスに、以下のアカウントを入力します。
5. **Role**リストから、**Cloud storage** > **Storage Admin**を選択します。
6. **Save**をクリックします。

</Accordion>

<div id="bigquery" />

<Accordion title="BigQuery">

BigQueryはソース接続のみサポートしています。以下の手順に従ってデータセットを作成し、AppsFlyerに権限を付与します。

> 📘 **注意**
>
> 以下の手順は、Google Cloud管理者が実施する必要があります。

**データセットの作成：**

1. Google Cloudコンソールにログインします。
2. BigQueryページへ移動します。
3. 新規または既存のGoogle Cloudプロジェクトで、DCP専用のデータセットを作成します。
   1. 左側のパネルで、プロジェクトIDの右にある三点メニューアイコン（**View actions**）をクリックします。
   2. **Create dataset**を選択します。
   3. 右側に開くパネルでデータセット名を入力し、必要に応じてその他のオプションを選択します。
      * 名前は任意に設定できますが、使用できるのは英字、数字、アンダースコアのみです。
        * **推奨：** ソース接続用のデータセットであることが分かる名前を使用してください。
      * **Enable table expiration**は使用しないでください。テーブルの有効期限が切れると、DCPからデータを読み取れなくなります。
   4. **Create dataset**をクリックします。

**AppsFlyerにデータセットへの権限を付与するには：**

1. 左側のパネルで、作成したデータセットの右にある三点メニューアイコン（**View actions**）をクリックします。
2. **Share**を選択します。
3. 右側に開くパネルで、**Add principal**をクリックします。
4. **Add principals**セクションの**New principals**フィールドに、以下のアカウントを入力します。
5. **Assign roles**セクションで、**BigQuery** > **BigQuery Data Viewer**を選択します。
6. **Save**をクリックします。
7. **Close**をクリックして右側のパネルを閉じます。

</Accordion>

<div id="snowflake" />

<Accordion title="Snowflake">

Snowflakeはソース接続のみサポートしています。以下の手順に従って、DCPで使用するプライベート共有を作成します。

> 📘 **注意**
>
> 以下の手順は、Snowflakeの**Accountadmin**が実施する必要があります。

**プライベート共有の作成：**

1. DCPと共有するデータが保存されている<Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">Snowflakeアカウントにログイン</Anchor>します。
2. ロールを**Account admin**に切り替えます。
3. 左側のパネルから**Private Sharing**を選択します。
4. 開いたページで、**Shared By Your Account**タブを選択します。
5. **Share**をクリックします。表示されたリストから**Create a Direct Share**を選択します。
6. DCPと共有するテーブルやビューを選択し、**Done**をクリックします。
7. **Secure Share Identifier**を変更し、必要に応じて説明を追加します。
8. **Add accounts in your region by name**フィールドに、利用リージョンに対応するAppsFlyerのSnowflakeアカウントを入力します。

| リージョン | AppsFlyerアカウント |
| --- | --- |
| EU West (eu-west-1) | QL63117 |
| US East - N. Virginia (us-east-1) | MWB70410 |
| US East - Ohio (us-east-2) | BM15378 |

9. **Create Share**をクリックします。

</Accordion>

<div id="salesforce-cloudcrm" />

<Accordion title="Salesforce Cloud/CRM">

Salesforce Cloud/CRMはソース接続のみサポートしています。設定手順については、<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-integration-with-salesforce-data-cloud">DCP — Salesforce Data Cloudとの連携</Anchor>を参照してください。

</Accordion>

## 特性と制限事項

| 特性 | 説明 |
| --- | --- |
| 対応クラウドサービス | Amazon S3とGCSは、ソース接続とクラウドストレージ接続の両方をサポートしています。 BigQuery、Snowflake、Salesforce Cloud/CRMは、ソース接続のみサポートしています。 |
| バケットの使用 | S3およびGCSのバケットは、DCP専用で使用する必要があります。他のサービスからバケットへデータを書き込むことはできません。 |
| <span id="dcr-naming-requirements"></span>DCRの命名要件 | 以下の命名要件は、バケット、フォルダ、ファイルを含むすべてのDCRデータエンティティに適用されます。<ul><li>**最大文字数：** 200文字</li><li>**使用可能な文字：** 英字（A-Z、a-z）、数字（0-9）、ハイフン（-）</li><li>**使用できない文字：** スペース、およびその他すべての記号や特殊文字</li><li>数字とハイフンを名前の先頭に使用することはできません。</li><li>**以下の文字は、指定された用途でのみ使用できます。**<ul><li>等号（=）：<Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version">日付およびバージョンのフォルダ名</Anchor>でのみ使用可能</li><li>アンダースコア（{"_"}）：<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-and-manage-sources#file-format">マルチパートGZIPファイル名</Anchor>または<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-and-manage-sources#_success-files">{"_SUCCESS"}ファイル</Anchor>でのみ使用可能</li><li>ドット（.）：ファイル名拡張子（.csv、.gzip）の直前でのみ使用可能</li></ul></li></ul> |
| バケットの命名 | バケット名は`af-dcr-`で始め、その後に任意の文字列を続ける必要があります。例：`af-dcr-example-bucket` |

> 📄 **関連情報**
>
> * DCP — 接続の追加
> * DCP — オーディエンスの構築と有効化
> * DCP — ソースの作成と管理
> * Data Collaboration Platform（DCP）ガイド

<div data-zendesk-anchors="about-cloud-service-setup=%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E8%A8%AD%E5%AE%9A%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KY1VRHDTX2W1YC4QX1N093GF=%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E8%A8%AD%E5%AE%9A%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 set-up-your-cloud-services=%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KY1VRHDT63WWBPNNN3QC9N49=%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KY1VRHDT2GRP2MMYTKFNRN3P=amazon-s3 h_01KY1VRHDTYMG39CRENZC971RS=%E6%B3%A8%E6%84%8F h_01KY1VRHDVV1ZHTVV5SXGXRZ59=%E9%87%8D%E8%A6%81 h_01KY1VRHDVS3S0F22T0EQ5MCKY=google-cloud-storage-gcs h_01KY1VRHDVX4KYCT627NN92TCT=%E6%B3%A8%E6%84%8F-1 h_01KY1VRHDVR3CZAZK0PGXDBWRC=bigquery h_01KY1VRHDV8Q3TRG7TBM5TRDYM=%E6%B3%A8%E6%84%8F-2 h_01KY1VRHDVSE9WJSDFXYV7W2R3=snowflake h_01KY1VRHDVDDK9B8Y7DKA5GA75=%E6%B3%A8%E6%84%8F-3 h_01KY1VRHDV9PJQMAGBY52G9RS8=salesforce-cloudcrm traits-and-limitations=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01KY1VRHDVT3PYP5QVKNKQ803G=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01KY1VRHDVEWNCDKZYCGWD1SRM=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />
