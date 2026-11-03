---
title: Data Clean Room — 接続の操作
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
  created_at: '2023-03-20T13:18:17Z'
  edited_at: '2026-10-14T09:28:39Z'
  id: 13886278812817
  locale: ja
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/ja/articles/13886278812817
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 概要： クラウドサービスをデータクリーンルームに接続し、データをアップロードしてレポートを受信します。

## 概要

データクリーンルーム (DCR) で使用するクラウドサービス設定が完了すれば、次にそれらをDCRに接続します。

* DCR がシステムからファーストパーティデータを読み取る接続を**受信接続**といいます。これらの接続は、カスタムソースを設定する際に使用します。
* DCRが処理後にレポートを配信する際に経由する接続を**送信接続**といいます。これらの接続は、レポートを設定する際に使用します。

## 受信接続を作成します

受信接続は、次のいずれかにおいて作成することができます。

* それらを使用してソースを作成する前。***又は***
* ソース作成プロセスの一部として。

どちらの方法でもプロセスは同じであり、作成した接続をまったく同じ方法で使用できます。唯一の違いは、プロセスを開始するタイミングと方法です。

**ソース作成プロセス以外の受信接続の新規作成**

1. AppsFlyerのメインDCRページ上部の <strong>[Manage connections]（接続管理）</strong>ボタンをクリックします。

   [![dcr_manage_connections_button.png](https://files.readme.io/773e9568a1e9e642f127806fa3b80932699e0db6cc6a124d5a09898577ade645-13909932760593.png)](https://files.readme.io/773e9568a1e9e642f127806fa3b80932699e0db6cc6a124d5a09898577ade645-13909932760593.png)

   * アカウントに既存の受信接続がある場合は、接続の管理ダイアログが表示されます。
   * アカウントの初めての受信接続を作成する場合は、新規接続ダイアログが自動的に開きます。
2. 以下の「接続を完了します」の手順に進みます。

ソース作成プロセスの一部としての受信接続の新規作成

1. <Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-working-with-sources#2-specify-the-source-location">ソースの場所を指定する</Anchor>ときに接続を作成します。
   * アカウントに接続が定義されていない場合は、 <strong>New connection（新規接続）</strong>ダイアログが開き、接続を作成するように求められます。
2. 以下の[「接続を完了します」](#接続を完了します)の手順に進みます。

#### 接続を完了します

新規接続ダイアログで、DCRに接続するクラウドサービスを選択し、以下の関連項目の手順に進みます。

<Image alt="dcr_create_inbound_connection.png" src="https://files.readme.io/b30606026761528f4a0d3efcc1a3207e8b9c99ca8202f76b2d698a86efaa21ee-13913809617297.png" width="457px" />

<div id="bigquery-inbound" />

<Accordion title="BigQuery">

**新規接続**ダイアログで、カスタムソースデータを含むプロジェクトのBigQuery **プロジェクト ID**を入力します。

* この情報は、Google Cloud ConsoleのBig Queryページから取得できます。

  <Image alt="BQ_project_ID.png" src="https://files.readme.io/de295dfc0224ff90f041b1aeaf2996828ec1920a715ba668b46a2f50489fd15b-13910856739857.png" width="457px" />

</Accordion>

<div id="snowflake-inbound" />

<Accordion title="Snowflake">

**新規接続**ダイアログで、カスタムソースデータを含むアカウントの**SnowflakeアカウントID**および**地域**を入力します。この情報は、Snowflakeコンソールの左下隅にあるアカウント名をクリックすると取得できます。

![ui-snowsight-account-identifier.png](https://files.readme.io/9995c3fd523548de93bafc7c575203e7d38be3b6be2a5e876d7a0a8495ca04c9-24698313004433.png)

</Accordion>

<div id="s3-gcs-inbound" />

<Accordion title="Amazon S3 および GCS">

**新規接続**ダイアログで、DCR専用に<Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-setting-up-cloud-services#クラウドストレージバケット--amazon-s3-および-gcs">作成したバケット</Anchor>の名前を入力します。

</Accordion>

## 送信接続を作成します

DCRは<Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers">AppsFlyer Data Locker</Anchor>を使用して、選択したクラウドサービスにレポートを配信します。レポートはData Locker経由で配信されるため、送信DCR接続は実際にはData Locker接続です。接続は、次のいずれかにおいて作成できます。

* レポート作成に使用する前（AppsFlyerのData Lockerページから開始します）。 ***または***
* レポート作成プロセスの一部として（AppsFlyerのDCRページから開始します）。

どちらの方法でもプロセスはほぼ同じであり、作成した接続をまったく同じ方法で使用できます。

> 📘 **注意**
>
> DCRレポートの受信にData Lockerのプレミアムサブスクリプションは必要ありません。Data Lockerによるその他のAppsFlyerレポートの受信についての詳細は、CSMにお問い合わせいただくか、 [hello@appsflyer.com](mailto:hello@appsflyer.com) にメールを送信してください。

**レポート作成プロセス以外の送信接続の新規作成**

1. AppsFlyerの左側のナビゲーションメニューから、**レポート > データロッカー**を選択します。  
   * アカウントに既存のData Locker接続がある場合は、メインData Lockerページに移動します。
   * アカウントの最初のData Locker接続を作成する場合は、Data Lockerのはじめに のページが表示されます。
2. 以下の「接続を完了します」の手順に進みます。

レポート作成プロセスの一部としての送信接続の新規作成

1. <Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-creating-attribution-data-reports#set-the-report-destination-and-save-the-report">レポートの宛先を設定する</Anchor>際に接続を作成します。
   * アカウントに接続が定義されていない場合：
     * ブラウザに新規タブが開きます（AppsFlyerのData Lockerページが表示されます）。
     * **新規接続** ダイアログが開きます。
   * 既存の接続があるが新しい接続を使用したい場合は、  ![dcr_new_connection_data_locker_button.png](https://files.readme.io/9850a4b8ea4f40f6320903c545c51add7b90207538a27c83a3b02a41197ba567-14995870859281.png) ボタンをクリックします：
     * ブラウザに新規タブが開きます（AppsFlyerのData Lockerページが表示されます）。
     * **新規接続** ダイアログが開きます。
2. 以下の「接続を完了します」の手順に進みます。
3. 接続の作成後、ブラウザのDCRタブに戻り、Data Locker接続一覧から新しく作成した接続を選択します。

#### 接続を完了します

> 🚧 **重要！**
>
> **AppsFlyer AWS Bucket** オプションをDCRレポートに使用しないでください。

新規接続ダイアログで、接続するクラウドサービスを選択し、以下の関連する項目の手順に進みます。

[![dcr_dl_new_connection_dialog.png](https://files.readme.io/fe77a008f036e15f6e192a7a2dc660efd54c92fb3bcceb0be9625420f66893e3-13928181611025.png)](https://files.readme.io/fe77a008f036e15f6e192a7a2dc660efd54c92fb3bcceb0be9625420f66893e3-13928181611025.png)

<div id="bigquery-outbound" />

<Accordion title="BigQuery">

1. **新規接続**ダイアログで、接続の名前を入力します。次に**BigQuery**を選択します。
2. Data Lockerに**作成したデータセット**を含む BigQuery プロジェクトの **プロジェクト ID** および <Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-setting-up-cloud-services#bigquery-outbound">データセット名</Anchor>を入力します。  
   * この情報は、Google Cloud ConsoleのBig Queryページから取得できます。

     <Image alt="BQ_project_ID_dataset_name.png" src="https://files.readme.io/c784b0369c51a6e123279fdc5b2fa1fba255ae371d436e9247cb5e4685387983-13928683779089.png" width="457px" />
4. **[Save]（保存）** をクリックして接続を作成します。

</Accordion>

<div id="snowflake-outbound" />

<Accordion title="Snowflake">

Snowflakeをデータロッカーに接続する手順は、2段階のプロセスです。

* **[ステップ#1](/docs/data-clean-room-working-with-connections#step-1) –** AppsFlyerで、最初の接続を作成します。
  * これにより、SnowflakeアカウントはAppsFlyer Snowflake共有にアクセスできるようになります。
* **[ステップ#2](/docs/data-clean-room-working-with-connections#step-2) –** Snowflakeアカウントで、共有からデータベースを作成します。
  * これにより、AppsFlyer共有内の表を参照するデータベースがアカウントに作成されます。

**注記：** 注意：次の手順は、Snowflakeの**アカウント管理者**が実行する必要があります。

<span id="step-1"></span>**ステップ#1 （初期接続の作成）**

1. **新規接続**ダイアログで、接続の名前を入力します。次に**Snowflake**を選択します。
2. Snowflakeのアカウント地域とアカウントIDを入力します。
   * この情報を取得するには、Snowflakeコンソールの左下隅にあるアカウント名をクリックし、ポップアップのアカウント名にカーソルを合わせます。**重要！**[Locator]（ロケーター） というID を探します。これは、受信のSnowflake接続作成に使用されるものと同じIDではありません 。  

     <Image alt="snowflake_account_locator.png" src="https://files.readme.io/23495b3209129f48ed1ca3442a1e96fac791d46df6f87050ac036893a050e427-13930022354961.png" width="536px" />
4. **[Save]（保存）** をクリックして接続を作成します。

<span id="step-2"></span>**ステップ#2（共有からデータベースを作成します）**

1. <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">Snowflakeアカウントにログインします</Anchor>。
2. Accountadminに**ロールを切り替えます**。
3. 左パネルにある [Private Sharing]（プライベート共有）を選択します。
4. 開いたページで、 [Shared With You]（あなたと共有） タブを選択します。
6. オプション：<strong>[Get Data]（データの取得）</strong>ダイアログで、必要に応じて既定のデータベース名を変更し、Accountadmin に加えてデータベースにアクセスできるロールを選択します。
7. <strong>[Get Data]（データの取得）</strong>をクリックしてデータベースを作成します。

</Accordion>

<div id="s3-gcs-outbound" />

<Accordion title="Amazon S3 および GCS">

1. Data Lockerの**新規接続**ダイアログで、接続の名前を入力します。次に、**Amazon S3**または **GCS**オプションを選択します。
2. DCR専用に<Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-setting-up-cloud-services#クラウドストレージバケット--amazon-s3-および-gcs">作成したバケット</Anchor>の名前を入力します。

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01HKA1AS2QGDTPW85WA07K35M0=%E6%A6%82%E8%A6%81 creating-inbound-connections=%E5%8F%97%E4%BF%A1%E6%8E%A5%E7%B6%9A%E3%82%92%E4%BD%9C%E6%88%90%E3%81%97%E3%81%BE%E3%81%99 h_01HKA1AS2QRRBJAYNKSWWZXE3N=%E5%8F%97%E4%BF%A1%E6%8E%A5%E7%B6%9A%E3%82%92%E4%BD%9C%E6%88%90%E3%81%97%E3%81%BE%E3%81%99 complete-the-connection-inbound=%E6%8E%A5%E7%B6%9A%E3%82%92%E5%AE%8C%E4%BA%86%E3%81%97%E3%81%BE%E3%81%99 h_01HKA1AS2Q06F07RDD8W384RE2=%E6%8E%A5%E7%B6%9A%E3%82%92%E5%AE%8C%E4%BA%86%E3%81%97%E3%81%BE%E3%81%99 h_01HKA1AS2QXP5H2HBJ911F3TPZ=bigquery-inbound h_01HKA1AS2QCPC6515FZ45E8Q67=snowflake-inbound h_01HKA1AS2QQZWFMRQD0T0FNQM5=s3-gcs-inbound creating-outbound-connections=%E9%80%81%E4%BF%A1%E6%8E%A5%E7%B6%9A%E3%82%92%E4%BD%9C%E6%88%90%E3%81%97%E3%81%BE%E3%81%99 h_01HKA1AS2QAV9DJWZQ2703TS0Z=%E9%80%81%E4%BF%A1%E6%8E%A5%E7%B6%9A%E3%82%92%E4%BD%9C%E6%88%90%E3%81%97%E3%81%BE%E3%81%99 h_01HKA1AS2Q76NP9FY7S4H0QP4D=%E6%B3%A8%E6%84%8F complete-the-connection-outbound=%E6%8E%A5%E7%B6%9A%E3%82%92%E5%AE%8C%E4%BA%86%E3%81%97%E3%81%BE%E3%81%99-1 h_01HKA1AS2RKTWNY2ZR7VYAJC90=%E6%8E%A5%E7%B6%9A%E3%82%92%E5%AE%8C%E4%BA%86%E3%81%97%E3%81%BE%E3%81%99-1 h_01HKA1AS2R7RFWKM2W89QSEH3V=%E9%87%8D%E8%A6%81 h_01HKA1AS2RJXZPCBKE7ST0SA63=bigquery-outbound h_01HKA1AS2R7TV495V39N35CWAR=snowflake-outbound h_01HKA1AS2RBTK8NZF09BYWDX2G=s3-gcs-outbound" />
