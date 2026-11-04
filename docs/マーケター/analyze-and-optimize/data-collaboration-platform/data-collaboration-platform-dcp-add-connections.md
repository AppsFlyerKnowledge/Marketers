---
title: Data Collaboration Platform（DCP）｜接続の追加
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2024-04-28T13:26:59Z'
  edited_at: '2026-10-19T18:49:18Z'
  id: 24603890457617
  locale: ja
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/ja/articles/24603890457617
---
> **概要：** DCPの接続を設定してデータソースを接続し、データをエンリッチしたり、オーディエンスをクラウドストレージやメディアパートナーへエクスポートしたりできます。

<div id="about-dcp-connections" />

## DCPの接続について

接続では、DCPがどのようにデータを取り込み、オーディエンスをエクスポートするかを定義します。<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">クラウドサービスの設定</Anchor>が完了したら、**接続を管理**モーダルからDCPへ接続します。利用できる接続タイプは以下のとおりです。

* [**ソース接続**](#create-source-connections)：クラウドストレージまたはデータウェアハウスからファーストパーティデータをDCPへ取り込むための接続。
* [**クラウドストレージ接続**](#create-cloud-storage-connections)：オーディエンスをAmazon S3またはGoogle Cloud Storage（GCS）のバケットへエクスポートするための接続。
* [**メディアパートナー接続**](#create-media-partner-connections)：アクティベーションのためにオーディエンスを広告プラットフォームへ送信する接続。
* [**Data & Identity接続**](#create-data-identity-connections)：分散したユーザーデータを統合し、マッチ率を高め、パートナー側のオーディエンスを拡大するための接続。

DCPで利用できるクラウドサービスは、接続の方向によって異なります。各接続タイプで利用できるサービスは、以下の表で確認できます。

| クラウドサービス | ソース（受信） | クラウドストレージへのエクスポート（送信） |
| --- | --- | --- |
| Amazon S3 | ✓ | ✓ |
| Google Cloud Storage（GCS） | ✓ | ✓ |
| BigQuery | ✓ | - |
| Snowflake | ✓ | - |
| Salesforce Cloud／CRM | ✓ | - |

Amazon S3とGoogle Cloud Storageでは、1つの接続をソース（受信）とクラウドストレージのエクスポート先（送信）の両方として使用します。 S3またはGCSへのソース接続を作成すると、対応するクラウドストレージ（エクスポート）接続も自動的に作成されます。その逆も同様です。

<div id="create-source-connections" />

<Accordion title="ソース接続の作成">

ファーストパーティデータをDCPへ取り込むためのソース接続を作成します。

**ソース接続を作成するには：**

1. AppsFlyerで、**Collaborate** > **Data Clean Room**の順に進みます。
2. 右上の**接続を管理**をクリックします。
3. **ソース**タブを開き、**＋新しい接続**をクリックします。
4. 以下の[ソースデータ向けクラウドサービス接続の手順](#ソースデータ向けクラウドサービス接続)に進みます。

ソースの設定時に、ソース接続を直接作成することもできます。手順については、<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-and-manage-sources">ソースの作成と管理</Anchor>を参照してください。

<div id="note" />

> 📘 **注意**
>
> Amazon S3またはGCSへの受信ソース接続を作成すると、対応する送信クラウドストレージ接続も自動的に作成されます（その逆も同様です）。 Amazon S3またはGCSの接続を削除すると、対応するもう一方の接続も自動的に削除されます。実際には同じ1つの接続を共有しているため、どちらかのタブから削除すると、その接続を使用しているすべての箇所から削除されます。

<div id="cloud-service-connections-for-source-data" />

#### ソースデータ向けクラウドサービス接続

ソース接続は、データソースをDCPへ安全に接続するために使用します。**新しい接続**ダイアログでクラウドサービスを選択し、利用するプロバイダーに応じて必要な情報を入力します。

**BigQuery：新しい接続**ダイアログで、ソースデータを含むプロジェクトのBigQuery **project ID**を入力します。このIDは、Google Cloud ConsoleのBigQueryページで確認できます。

**Snowflake：新しい接続**ダイアログで、ソースデータを含むアカウントの**Snowflake account ID**と**region**を入力します。確認するには、Snowflakeコンソール左下のアカウント名をクリックします。

**ACCOUNTADMIN** > **Account** > 対象アカウントにカーソルを合わせる > **Copy account identifier**の順に進みます。詳細は<Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/admin-account-identifier#finding-the-organization-and-account-name-for-an-account">Snowflakeのドキュメント</Anchor>を参照してください。

<div id="important" />

> 🚧 **重要**
>
> **Locator**と表示されているIDを確認してください。これは、Snowflakeの送信接続を作成する際に使用するIDとは**異なります**。

**Amazon S3およびGCS：新しい接続**ダイアログに、AppsFlyer Data Clean Room（DCR）専用として<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#cloud-storage-buckets-inbound">作成したバケット</Anchor>の名前を入力します。

**Salesforce Cloud／CRM：** <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-integration-with-salesforce-data-cloud">Salesforce接続の設定方法</Anchor>を参照してください。

<div id="local-file-connection" />

#### ローカルファイル接続

ローカルファイルシステム接続を使用すると、PCからDCPへデータファイルを直接アップロードできます。通常はテスト用途で使用する方法であり、継続的なデータ取り込みや大規模なデータ取り込みには推奨されません。

<div id="set-up-a-local-file-connection" />

<Accordion title="ローカルファイル接続の設定">

ローカルファイル接続は、サンプルファイルを使ってプラットフォームをテストするために使用します。実際にデータ共有を開始する前に、DCPの機能や操作に慣れることができます。データ共有用途には推奨されないこと、データ保持期間は14日間に制限されること、自動化プロセスには対応していないことに注意してください。

ローカルファイル接続は、<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-and-manage-sources#ローカルファイルをソースとして使用する">ソースの作成時に設定</Anchor>できます。

</Accordion>

</Accordion>

<div id="create-cloud-storage-connections" />

<Accordion title="クラウドストレージ接続の作成">

クラウドストレージ接続を使用すると、オーディエンスが更新されるたびに、DCPのオーディエンスをAmazon S3またはGoogle Cloud Storage（GCS）のバケットへ自動的にエクスポートできます。

**クラウドストレージ接続を作成するには：**

1. AppsFlyerで、**Collaborate** > **Data Clean Room**の順に進みます。
2. 右上の**接続を管理**をクリックします。
3. **クラウドストレージ**タブを開き、**＋新しい接続**をクリックします。
4. **新しいクラウドストレージ接続**モーダルが開きます。
5. **新しいクラウドストレージ接続**モーダルで、クラウドプロバイダーとして**Google Cloud Storage**または**Amazon Simple Storage**を選択します。
6. バケット名を入力します。
   * **GCS：** GCSバケット名を`gs://my-bucket`の形式で入力します。
   * **S3：** S3バケット名を入力します。
7. **接続をテスト**をクリックし、DCPからバケットへ接続できることを確認します。
8. **保存**をクリックします。新しい接続が、**クラウドストレージ**タブの**クラウドストレージ接続**に表示されます。

オーディエンスビルダーからクラウドストレージ接続を直接作成することもできます。手順については、<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-build-and-activate-audiences">オーディエンスの作成とアクティベーション</Anchor>を参照してください。

<div id="understand-export-path" />

<Accordion title="エクスポート先パスの構成">

オーディエンスをエクスポートするたびに、DCPは以下の固定された予測可能なパス構造でバケットへ書き込みます。

```
<bucket>/dcp-output/audiences/<collaboration-id>/t=<audience_name>_<id>/dt=<YYYY-MM-DD>/v=<version>/<file>.csv
```

**1回の配信で作成されるフォルダ内容の例：**

```
s3://af-dcr-example-bucket/dcp-output/audiences/8f3a1c02-44b1-4e9a-9c7d-2b6e1a0f5d3e/t=example_audience_6148a3/dt=2026-07-18/v=1/
  ├── part-00000-a1b2c3d4-e5f6-47a8-9b0c-1d2e3f4a5b6c-c000.csv
  ├── part-00001-a1b2c3d4-e5f6-47a8-9b0c-1d2e3f4a5b6c-c000.csv
  └── _SUCCESS
```

| パス要素 | 意味 |
| --- | --- |
|  | 接続済みのS3またはGCSバケット。 |
| dcp-output/audiences/ | すべてのオーディエンスエクスポート用としてDCPが自動作成する固定フォルダ。 |
|  | このオーディエンスが属するコラボレーションの一意のID。 DCPのコラボレーションURLで確認できます。 |
| t=\_ | オーディエンス名（スペースや特殊文字はアンダースコアに置換）と一意のID。これにより、同じ名前のオーディエンスを削除後に再作成しても、以前のファイルを上書きしたり、競合したりすることはありません。 |
| dt= | 配信日。 |
| v= | このオーディエンスのエクスポートに付与されるバージョン番号。新しい配信が行われるたびに増加します。 |
| part-NNNNN--c000.csv | この配信で出力されるファイルの1つ。詳細は以下の「ファイル形式と分割」を参照してください。 |
| \_SUCCESS | すべてのpartファイルの書き込みが完了すると作成される、空のマーカーファイル。 |

<div id="note-1" />

> 📘 **注意**
>
> このフォルダ構造は自動的に作成・管理されます。手動で名前変更や構成変更を行わないでください。これらのファイルを読み取る自動処理は、このパスパターンに従うよう実装し、途中までしか配信されていないファイルを読み込まないよう、partファイルを処理する前に\_SUCCESSが作成されるのを待つ必要があります。

**ファイル形式と分割**

* オーディエンスは常に、非圧縮のCSVファイルとしてエクスポートされます。列は、`value`（識別子）と`taxonomy`（識別子の種類）の2つです。
* オーディエンスの規模が大きい場合は、1つのファイルではなく、`part-00000`、`part-00001`のように番号が付いた複数ファイルに分割して配信されることがあります。デフォルトでは、各ファイルに最大約500,000行が含まれます。
* 1つのファイル内で、行ごとに異なる種類の識別子が混在する場合があります。必要な識別子は`taxonomy`列を使用して絞り込んでください。一般的なtaxonomy値には、`customer_id`、`mobile_ad_id`、`hashed_email`、`hashed_phone_number_without_plus_sha256`などがあります。

**例：**

```
value,taxonomy
6f1a2b3c4d5e6f7a8b9c0d1e2f3a4b5c,customer_id
1a2b3c4d-5e6f-4a7b-8c9d-0e1f2a3b4c5d,mobile_ad_id
b7e2c9a1f4d6e8b0a2c4d6e8f0a1b3c5d7e9f1a3b5c7d9e0f2a4b6c8d0e2f4a6,hashed_email
c1d3e5f7a9b1c3d5e7f9a1b3c5d7e9f1a3b5c7d9e1f3a5b7c9d1e3f5a7b9c1d3,hashed_phone_number_without_plus_sha256
```

</Accordion>

</Accordion>

<div id="create-media-partner-connections" />

<Accordion title="メディアパートナー接続の作成">

送信メディアパートナー接続を使用すると、DCPのオーディエンスを対応するメディアパートナーへ安全に接続し、そのプラットフォーム上で目的に合わせたキャンペーンをアクティベーションできます。メディアパートナーは、オーディエンスをアクティベーションする際の主な送信先です。メディアパートナーごとの接続方法については、<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-media-partner-connections">メディアパートナー接続の設定</Anchor>を参照してください。

**メディアパートナー接続を作成するには：**

1. AppsFlyerで、**Collaborate** > **Data Clean Room**の順に進みます。
2. 右上の**接続を管理**をクリックします。
3. **メディアパートナー**タブを開き、**＋新しい接続**をクリックします。既存の接続がある場合は、**メディアパートナー**に一覧表示されます。
4. **新しいメディアパートナー接続**ダイアログで、対象のメディアパートナーを選択します。
5. 接続名を入力します。
6. 認証情報を使用してメディアパートナーのアカウントにログインし、パートナー側の手順に従ってAppsFlyerからのアクセスを許可します。
7. **アカウントIDを選択**をクリックし、この接続で使用するアカウントを選択します。
8. **保存**をクリックします。新しい接続がパートナー一覧に追加されます。

オーディエンスビルダーからメディアパートナー接続を直接作成することもできます。手順については、<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-build-and-activate-audiences">オーディエンスの作成とアクティベーション</Anchor>を参照してください。

</Accordion>

<div id="create-data-identity-connections" />

<Accordion title="Data & Identity接続の作成">

Data & Identity接続では、分散したユーザーデータを統合し、アクティベーションパートナーとのマッチ率を高めます。これにより、パートナー側のオーディエンスを拡大し、キャンペーンの効果を高めることができます。

#### ID5

ファーストパーティデータを<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-enrich-sources-with-id5">ID5識別子でエンリッチ</Anchor>することで、分散したユーザーデータを統合し、アクティベーションパートナーとのマッチ率を高め、パートナー側のオーディエンス規模を拡大できます。

<div id="see-also" />

> 📄 **関連情報**
>
> * DCP - クラウドサービスの設定
> * DCP - オーディエンスの作成とアクティベーション
> * DCP - メディアパートナー接続
> * DCP - ID5によるソースのエンリッチ
> * Data Collaboration Platform（DCP）ガイド

</Accordion>

<div data-zendesk-anchors="about-dcp-connections=dcp%E3%81%AE%E6%8E%A5%E7%B6%9A%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KXX80P91T92MH8KEGHVG3QP1=dcp%E3%81%AE%E6%8E%A5%E7%B6%9A%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KXX80P913HRREW60M6S316PP=create-source-connections h_01KY4HCGBBCD5FZD9RYNNVDYRC=%E6%B3%A8%E6%84%8F source-cloud-service-connections=%E3%82%BD%E3%83%BC%E3%82%B9%E3%83%87%E3%83%BC%E3%82%BF%E5%90%91%E3%81%91%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E6%8E%A5%E7%B6%9A cloud-service-connections-for-source-data=%E3%82%BD%E3%83%BC%E3%82%B9%E3%83%87%E3%83%BC%E3%82%BF%E5%90%91%E3%81%91%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E6%8E%A5%E7%B6%9A h_01KXX80P914VFMH1T6FQF9KC31=%E9%87%8D%E8%A6%81 local-file-connection=%E3%83%AD%E3%83%BC%E3%82%AB%E3%83%AB%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E6%8E%A5%E7%B6%9A h_01KXX80P91EFCGH3MYV729TGTH=%E3%83%AD%E3%83%BC%E3%82%AB%E3%83%AB%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E6%8E%A5%E7%B6%9A h_01KXX80P91HG17YTWE15ZWTBZ8=set-up-a-local-file-connection h_01KXX80P91F8TG9FR1XQ7QVNCY=create-cloud-storage-connections h_01KYEP2MX3KQ3BAP7VRSGYTFBB=understand-export-path h_01KYEP2MX3SHFCECTSTHV9RMS4=%E6%B3%A8%E6%84%8F-1 h_01KXX80P91BMB45ETZQSKWJWZB=create-media-partner-connections h_01KXX80P91PS35EG5P5YJB9EHC=create-data-identity-connections h_01KXX80P92BXD3B7ZVT1FC5HCF=id5 h_01KXX80P92WMPPRGD7321TBS7Y=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />
