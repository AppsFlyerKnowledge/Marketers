---
title: 収益ETLレポート
metadata:
  keywords:
    - Marketers
    - revenue
    - etl
    - revenueetl
    - revenue etl
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2023-06-25T16:57:02Z'
  edited_at: '2026-10-28T08:49:51Z'
  id: 16464765619985
  locale: ja
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/ja/articles/16464765619985
---
> **概要：** ROI360の収益レポートについて、データの取得元、生成の仕組み、利用可能になるタイミング、アクセス方法を説明します。フィールドや構造の詳細は、データサンプルをダウンロードして確認できます。

<div id="revenue-etl" />

## 収益ETL

ROI360の収益ETLは、収益データをBIシステムに取り込めるよう、Data Locker経由でクラウドストレージに配信します。

利用できる収益レポートを、以下の表に示します。**注意**：旧版の広告収益レポート［単一バージョン］を除き、すべてのレポートにROI360 Advancedパッケージの契約が必要です。

| レポート | 連携方式 | 説明 | データの更新・反映 |
| --- | --- | --- | --- |
| [旧版の広告収益［単一バージョン］](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level)：<ul><li>アトリビューション済み広告収益［単一バージョン、x＋1日］</li><li>オーガニック広告収益［単一バージョン、x＋1日］</li><li>リターゲティング広告収益［単一バージョン、x＋1日］</li></ul> | <ul><li>広告表示単位（SDK経由）</li><li>端末単位（S2S API経由）</li><li>広告表示単位（SDK経由）と端末単位（S2S API経由）の併用</li></ul> | <ul><li>広告収益データを含みます。</li><li>単一バージョン。配信後のデータ更新はありません。</li><li>APIとSDKの両方で連携している場合、レポートにはAPIのデータのみが含まれます。</li></ul> | <ul><li>1日1回（x＋1日に利用可能）。<Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#data-freshness">詳細はこちら</Anchor></li></ul> |
| [広告収益［更新版あり］](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level)：<ul><li>アトリビューション済み広告収益［更新版あり］</li><li>オーガニック広告収益［更新版あり］</li><li>リターゲティング広告収益［更新版あり］</li></ul> | <ul><li>広告表示単位（SDK経由）</li><li>端末単位（S2S API経由）</li><li>広告表示単位（SDK経由）と端末単位（S2S API経由）の併用</li></ul> | <ul><li>最新の広告収益データを含みます。</li><li><Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers#version-folders">更新版あり</Anchor></li></ul> | <ul><li>1日に複数回更新。 <Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#data-freshness">詳細はこちら</Anchor></li><li>広告表示の4時間後から14日後まで、データを更新します。</li></ul> |
| [広告収益［SDK広告表示単位］](/docs/revenue-etl-reports#impression-level-report) | <ul><li>広告表示単位（SDK経由）</li><li>広告表示単位（SDK経由）と端末単位（S2S API経由）の併用</li></ul> | <ul><li>広告収益SDKのデータを含みます。</li><li>最も早いタイミングで、最も細かい単位のデータを提供します。</li></ul> | 1時間ごと。<Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#data-freshness">詳細はこちら</Anchor> |
| [取引単位のストア収益](/docs/revenue-etl-reports#transactionlevel-stores-revenue-report) | ROI360のIAP・サブスクリプション収益連携 | <ul><li>ROI360で検証したアプリ内購入・サブスクリプションのローデータを、取引単位で提供します。</li><li>最も早いタイミングで、最も細かい単位のデータを提供します。</li><li>ROI360独自の収益化関連データと純収益を含みます。</li></ul> | 1時間ごと |
| [端末単位のストア収益［更新版あり］](/docs/revenue-etl-reports#devicelevel-stores-revenue-report) | ROI360のIAP・サブスクリプション収益連携 | <ul><li>ROI360で検証したアプリ内購入・サブスクリプションのローデータを、端末単位で提供します。</li><li>ROI360独自の純収益データを含みます。</li></ul> | 8時間ごと |

<div id="reports" />

## レポート

以下では、各レポートの詳細、仕組み、配信の設定方法、アクセス方法を説明します。

<div id="ad-revenue-single-version-report-device-level" />

<Accordion title="［旧版］広告収益（単一バージョン）">

1日分の広告収益データを端末単位に集計し、1つのバージョンとして提供するレポートです。レポートはX＋1日に利用できます（Xは収益イベントの発生日）。

**注意：** オーガニックとリターゲティングの収益データは、別々のレポートで提供されます。これらのレポートは、構造と利用可能になるタイミングが同じです。

<span id="download-the-report-data-sample"></span>[単一バージョンの広告収益レポートのデータサンプルをダウンロード](https://docs.google.com/spreadsheets/d/e/2PACX-1vSuZYSPuAWIG-MappxQDIT3sl8UmN6MLKP2SKsbREekVAvKSHuUAUAtUE6JapanANJbKsTzCOID8z7G/pub?output=xlsx)。

<div id="data-sources" />

#### データの取得元

広告収益パートナーとの連携方式に応じて、レポートのデータは次のいずれかから取得します。

* **SDK**：ROI360の広告収益SDK Connectorから送信される、広告表示単位のデータ。
* **S2S：** パートナー（メディエーションまたは広告収益化ネットワーク）にAPIリクエストを送り、取得した端末単位のレポート。

連携方式の設定方法は、広告収益パートナーとの連携を参照してください。

<div id="data-flow" />

#### データ処理の流れ

1. **データの取り込み：** 広告収益SDK ConnectorまたはS2S APIリクエストからデータを取得します（上記を参照）。
2. **データの処理**：AppsFlyer ROI360の広告収益機能が、次の処理を行います。

   1. データの表記・形式の統一。
   2. インストール元への紐づけと、関連情報の追加。
   3. 広告収益イベントの生成。
   4. イベントの端末単位への集計。

   **注意：** 同じ端末について、端末単位の集計データが複数行含まれる場合があります。端末単位の集計には、広告収益化ネットワーク、広告の掲載位置、広告の種類など、収益化に関するディメンションも使われるためです。例えば、アプリ内の2つの異なる位置に広告を表示する場合、端末単位の収益イベントは掲載位置ごとに別々に集計されます。
3. **データの配信**：端末単位のデータを、単一バージョンのレポートに書き込みます。

<div id="when-is-the-report-data-available" />

#### レポートデータを利用できるタイミング

| 連携方式 | バージョンの配信日（X＝収益イベントの発生日） | バージョンの利用開始時刻 | バージョンに含まれる収益イベントの発生期間 |
| --- | --- | --- | --- |
| SDK | X＋1日 | 20:00 | 00:00 — 24:00 |
| SDK＋S2S | X＋1日 | 17:00 | 00:00 — 24:00 |

<div id="how-to-subscribe-to-the-report" />

#### レポートの配信設定

1. AppsFlyerのサイドメニューから<strong>［レポート］</strong>＞<strong>［Data Locker］</strong>を選択します。
2. <strong>［Data Lockerのコンテンツ］</strong>ペインを下にスクロールし、<strong>［ROI360収益ETL］</strong>タイルを探します。
3. <strong>［アトリビューション済み収益（単一バージョン）］</strong>を選択します。

**注意：** リターゲティングとオーガニックについても、同じ種類のレポート（リターゲティング／オーガニック広告収益［単一バージョン］）を選択できます。

<div id="how-to-access-the-report-in-your-bucket" />

#### バケット内のレポートへのアクセス方法

レポートのパスは、次のフォルダー階層で構成されます。

形式：`<bucket-name>/t=attributed_ad_revenue/dt=<dt=yyyy-mm-dd>/h=23/`

<div id="report-folder-hierarchy" />

#### レポートのフォルダー階層

広告主のバケットに保存される、アトリビューション済み広告収益の単一バージョンレポートのフォルダー階層の例：

```
bucket
|
└── t=attributed_ad_revenue
    |
    ├── dt=2023-06-02
    |   |
    |   └── h=23
    |        |
    |        ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |        |
    |        ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |        │
    |        └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |
    ├── dt=2023-06-01
    |   |
    |   └── h=23
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |
    ├── dt=2023-05-31
    |   |
    .   . 
    .   .
```

**凡例：**

* **dt**：レポートに含まれる収益イベントの発生日。
* **t：** レポートの種類
* **h：** 単一バージョンを作成した時刻

</Accordion>

<div id="ad-revenue-versioned-report-device-level" />

<Accordion title="広告収益（更新版あり）">

同じ日付の収益データを、複数のバージョンで提供するレポートです。例えば、6月21日に発生した収益は、6月21日、22日、23日、24日、28日、7月5日に報告されます。

同じ日付のデータを複数のバージョンで取得することで、時間の経過とともに条件が変わり、収益の計算結果が変動した場合も反映できます。例えば、広告表示時に計上された収益額が、翌日には変わる場合があります。

**注意：** オーガニックとリターゲティングの収益データは、別々のレポートで提供されます。これらのレポートは、構造と利用可能になるタイミングが同じです。

[更新版を含む広告収益レポートのデータサンプルをダウンロード](https://docs.google.com/spreadsheets/d/e/2PACX-1vQek1x3rYnYQq3jctSz5hnWG_Nk_LQk2ixMTQFVMb8K6w-UmeNKvKOif3-nudAyIqp9tyuoq9R-FhVz/pub?output=csv)。

<div id="data-sources-1" />

#### データの取得元

パートナーとの連携方式に応じて、レポートのデータは次のいずれかから取得します。

* **SDK**：ROI360の広告収益SDK Connectorから送信される、広告表示単位のデータ。
* **S2S：** パートナー（メディエーションまたは広告収益化ネットワーク）にAPIリクエストを送り、取得した端末単位のレポート。
* **S2S＋SDK：** SDKとS2Sの両方から送信されるデータ。

連携方式の設定方法は、広告収益パートナーとの連携を参照してください。

<div id="data-flow-1" />

#### データ処理の流れ

1. **データの取り込み：** SDKまたはS2S APIリクエストからデータを取得します（上記を参照）。
2. **データの処理：** AppsFlyer ROI360の広告収益機能が、次の処理を行います。

   1. データの表記・形式の統一。
   2. インストール元への紐づけと、関連情報の追加。
   3. 広告収益イベントの生成。
   4. イベントの端末単位への集計。

   **注意：** 同じ端末について、端末単位の集計データが複数行含まれる場合があります。端末単位の集計には、広告収益化ネットワーク、広告の掲載位置、広告の種類など、収益化に関するディメンションも使われるためです。例えば、アプリ内の2つの異なる位置に広告を表示する場合、端末単位の収益イベントは掲載位置ごとに別々に集計されます。
3. **データの配信**：以下に示す所定のスケジュールに従って、端末単位のデータをレポートの各バージョンに書き込みます。

<div id="when-are-the-report-versions-available" />

#### 各バージョンを利用できるタイミング

以下の表に、S2S版とSDK版の生成スケジュールを示します。 ROI360の広告収益機能「Freshness to Accuracy」では、両方のバージョンを受信することで、データの速報性と正確性を両立できます。

**注意：** S2Sのデータに基づくバージョンは、生成されない場合があります。 前回の取得以降、パートナーのデータに変更がない場合、新しいバージョンは生成されません。

| 連携方式 | バージョンの配信日（X＝収益イベントの発生日） | バージョンの利用開始時刻 | バージョンに含まれる収益イベントの発生期間 |
| --- | --- | --- | --- |
| SDK | X日 | 03:00-04:00 | 00:00 — 24:00 |
| SDK | X日 | 07:00-08:00 | 00:00 — 07:00 |
| SDK | X日 | 11:00-12:00 | 00:00 — 11:00 |
| SDK | X日 | 15:00-16:00 | 00:00 — 15:00 |
| SDK | X日 | 19:00-20:00 | 00:00 — 19:00 |
| SDK | X日 | 23:00-24:00 | 00:00 — 23:00 |
| SDK | X＋1日 | 04:00-05:00 | 00:00 — 24:00 |
| S2S | X＋1日 | 10:00-11:00 | 00:00 — 24:00 |
| S2S | X＋1日 | 16:00-17:00 | 00:00 — 24:00 |
| S2S | X＋2日 | 00:00-01:00 | 00:00 — 24:00 |
| S2S | X＋2日 | 13:00-14:00 | 00:00 — 24:00 |
| S2S | X＋3日 | 06:00-07:00 | 00:00 — 24:00 |
| S2S | X＋7日 | 08:00-09:00 | 00:00 — 24:00 |
| S2S | X＋14日 | 11:00-12:00 | 00:00 — 24:00 |
| SDK＋S2S | 上記のSDK版とS2S版のすべて |  |  |

<div id="how-to-subscribe-to-the-report-1" />

#### レポートの配信設定

1. AppsFlyerのサイドメニューから<strong>［レポート］</strong>＞<strong>［Data Locker］</strong>を選択します。
2. <strong>［Data Lockerのコンテンツ］</strong>ペインを下にスクロールし、<strong>［ROI360収益ETL］</strong>タイルを探します。
3. <strong>［アトリビューション済み広告収益（更新版あり）］</strong>を選択します。

**注意：** リターゲティングとオーガニックについても、同じ種類のレポート（リターゲティング／オーガニック広告収益［更新版あり］）を選択できます。

<div id="how-to-access-the-report-in-your-bucket-2" />

<div id="how-to-access-the-report-in-your-bucket-1" />

#### バケット内のレポートへのアクセス方法

レポートのパスは、次のフォルダー階層で構成されます。

`<bucket-name>/t=attributed_ad_revenue_v2/dt=<dt=yyyy-mm-dd>/version=<9999999>/`

<div id="report-folder-hierarchy-2" />

<div id="report-folder-hierarchy-1" />

#### レポートのフォルダー階層

広告主のバケットに保存される、レポートのフォルダー構造の例：

```
bucket
|
└── t=attributed_ad_revenue_v2
    |
    └── dt=2023-06-01
        |
        ├── version=1685588879
        |   |
        │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   |
        │   ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   │
        |   └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |
        ├── version=1685603326
        |   |
        │   ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   |
        │   ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   │
        |   └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |
        ├── version=1685617877
        .
                .
                .
```

* **凡例：**
  * **t：** レポートの種類
  * **dt**：レポートに含まれる収益イベントの発生日。
  * **version：** バージョン名は、そのバージョンが作成された日時のエポックタイムスタンプです。例：**version=1685588879**。
* バージョンの作成時刻から、SDKとS2Sのどちらのデータをもとに作成されたかを確認できます。最初のSDK版は、SDKのデータをもとに作成されます。それ以外は、S2Sのデータをもとに作成されます。

| 連携方式 | バージョンの配信日（X＝収益イベントの発生日） | バージョンの利用開始時刻 | バージョンに含まれる収益イベントの発生期間 |
| --- | --- | --- | --- |
| SDK | X日 | 03:00-04:00 | 00:00 — 24:00 |
| SDK | X日 | 07:00-08:00 | 00:00 — 07:00 |
| SDK | X日 | 11:00-12:00 | 00:00 — 11:00 |
| SDK | X日 | 15:00-16:00 | 00:00 — 15:00 |
| SDK | X日 | 19:00-20:00 | 00:00 — 19:00 |
| SDK | X日 | 23:00-24:00 | 00:00 — 23:00 |
| SDK | X＋1日 | 04:00-05:00 | 00:00 — 24:00 |
| S2S | X＋1日 | 10:00-11:00 | 00:00 — 24:00 |
| S2S | X＋1日 | 16:00-17:00 | 00:00 — 24:00 |
| S2S | X＋2日 | 00:00-01:00 | 00:00 — 24:00 |
| S2S | X＋2日 | 13:00-14:00 | 00:00 — 24:00 |
| S2S | X＋3日 | 06:00-07:00 | 00:00 — 24:00 |
| S2S | X＋7日 | 08:00-09:00 | 00:00 — 24:00 |
| S2S | X＋14日 | 11:00-12:00 | 00:00 — 24:00 |

</Accordion>

<div id="impression-level-report" />

<Accordion title="広告収益（SDK広告表示単位）">

広告表示単位のデータを、発生時刻ごとのフォルダーに分けて提供するレポートです。各フォルダーには、**その1時間に発生したインプレッションのみ**が含まれます。

[広告表示単位の広告収益レポートのデータサンプルをダウンロード](https://docs.google.com/spreadsheets/d/e/2PACX-1vR5zVxFGaCMNZMbCCYPae6f7MmbtelxrqXb-A5DBENuyTFCN4deRfICvbL0_dNeYVipojmAeUdrGbKI/pub?output=csv)

<div id="data-source" />

#### データの取得元

ROI360の広告収益SDK Connectorから送信された広告表示単位のデータを使用するため、SDK方式の連携が必要です。

連携方式の設定方法は、広告収益パートナーとの連携を参照してください。

<div id="data-flow-2" />

#### データ処理の流れ

1. **データの取り込み：** ROI360の広告収益SDK Connectorから送信された広告表示単位のデータを使用します。SDK方式の連携が必要です。
2. **データの処理**：AppsFlyer ROI360の広告収益機能が、次の処理を行います。
   1. データの表記・形式の統一。
   2. インストール元への紐づけと、関連情報の追加。
   3. 広告表示単位の広告収益イベントの生成。
3. **データの配信**：インプレッションイベントを発生時刻ごとのフォルダーに分け、ファイルに書き込みます。各フォルダーには、その1時間に発生したインプレッションのみが含まれます。

<div id="when-is-the-report-data-available-1" />

#### レポートデータを利用できるタイミング

| 連携方式 | バージョンの配信日（X＝収益イベントの発生日） | バージョンの利用開始時刻 |
| --- | --- | --- |
| SDK | X日 | 各レポート対象時間の終了時 |

<div id="how-to-subscribe-to-the-report-2" />

#### レポートの配信設定

1. AppsFlyerのサイドメニューから<strong>［レポート］</strong>＞<strong>［Data Locker］</strong>を選択します。
2. <strong>［Data Lockerのコンテンツ］</strong>ペインを下にスクロールし、<strong>［ROI360収益ETL］</strong>タイルを探します。
3. <strong>［広告収益（SDK広告表示単位）］</strong>を選択します。

<div id="how-to-access-the-report-in-your-bucket-3" />

#### バケット内のレポートへのアクセス方法

レポートのパスは、次のフォルダー階層で構成されます。

`<bucket-name>/t=attributed_adrevenue_sdk_impression_level/dt=<dt=yyyy-mm-dd>/h=<hh>`

#### レポートのフォルダー階層

広告主のバケットに保存される、レポートのフォルダー構造の例：

```
bucket
|
└── t=attributed_adrevenue_sdk_impression_level/
    |
    ├── dt=2023-06-01
    |   |
    |   ├── h=0
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=1
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=2
    |   .   |
    |   .   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   .   .
    |   ├── h=23
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   └── h=24
    |       |
    |       └── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |    
    ├── dt=2023-06-02
    |   |  
    |   ├── h=0
        .   .
        .   .
```

**凡例：**

* **t：** レポートの種類
* **dt**：レポートに含まれる収益イベントの発生日。
* **h**：その1時間に発生したインプレッションのCSVファイルを含む、時間別フォルダー。

</Accordion>

<div id="transactionlevel-stores-revenue-report" />

<Accordion title="取引単位のストア収益">

当日発生した取引のローデータを、取引単位で提供するレポートです。時間別フォルダーに分かれ、各フォルダーにはその1時間の取引のみが含まれます。

[取引単位のストア収益レポートのデータサンプルをダウンロード](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGlRSg_Xrp2EsqK2uaisjhlqeSuZsypqKqSSRGX3AQBwBLlNdG_5LOOKCM9f9gCcLguMQgQwT--Dz7/pub?output=csv)

<div id="data-sources-3" />

<div id="data-sources-2" />

#### データの取得元

ROI360 Purchase SDK Connectorとストアのサーバー間通知を通じて収集した取引データを使用します。

<div id="data-flow-3" />

#### データ処理の流れ

1. ROI360 Purchase SDK Connectorから送信されたデータ、またはストアのS2S通知から収集した取引データを使用します。
2. AppsFlyer ROI360のVIAP／サブスクリプション機能がデータを処理して獲得元に紐づけ、取引単位のイベントと値を生成します。
3. 取引単位のイベントを、時間別フォルダーに分けてレポートに書き込みます。

<div id="when-is-the-report-data-available-2" />

#### レポートデータを利用できるタイミング

| バージョンの配信日（X＝収益イベントの発生日） | バージョンの利用開始時刻 |
| --- | --- |
| X日 | 各レポート対象時間の終了時 |

<div id="how-to-subscribe-to-the-report-3" />

#### レポートの配信設定

1. AppsFlyerのサイドメニューから<strong>［レポート］</strong>＞<strong>［Data Locker］</strong>を選択します。
2. <strong>［Data Lockerのコンテンツ］</strong>ペインを下にスクロールし、<strong>［ROI360収益ETL］</strong>タイルを探します。
3. <strong>［取引単位のストア収益レポート］</strong>を選択します。

<div id="how-to-access-the-report-in-your-bucket-4" />

#### バケット内のレポートへのアクセス方法

レポートのパスは、次のフォルダー階層で構成されます。

`<bucket-name>/t=stores_rawdata/dt=<dt=yyyy-mm-dd>/h=<hh>`

<div id="report-folder-hierarchy-3" />

#### レポートのフォルダー階層

広告主のバケットに保存される、レポートのフォルダー構造の例：

```
bucket
|
└── t=stores_rawdata
    |
    ├── dt=2023-06-01
    |   |
    |   ├── h=0
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=1
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=2
    |   .   |
    |   .   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   .   .
    |   ├── h=23
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   └── h=24
    |       |
    |       └── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |    
    ├── dt=2023-06-02
    |   |  
    |   ├── h=0
        .   .
        .   .
```

**凡例：**

* **t：** レポートの種類
* **dt**：レポートに含まれる収益イベントの発生日。
* **h**：その1時間に発生した取引のCSVファイルを含む、時間別フォルダー。

</Accordion>

<div id="devicelevel-stores-revenue-report" />

<Accordion title="端末単位のストア収益（更新版あり）">

端末単位のストア収益レポートには、ROI360の各機能で記録したアプリ内購入と自動更新サブスクリプションのイベントが含まれます。これらのイベントには、ROI360独自の収益化関連ディメンションが含まれます。お客様が送信したアプリ内イベントは、このレポートには含まれません。

<span id="download-the-report-data-sample::8cbba4e3"></span>[端末単位のストア収益レポートのデータサンプルをダウンロード](https://docs.google.com/spreadsheets/d/e/2PACX-1vSpomvcf2axYeSFcCh0kEx3ShYYRGVfF9WYZXG1UYBkeymeVfh8mcypAOpq2drqE3zhdmbcmrMtahsl/pub?output=csv)

#### データの取得元

レポートには、次の方法で収集した取引データを使用します。

1. ROI360 Purchase SDK Connector。
2. ストア（App Store、Google Playなど）からのサーバー間通知。

<div id="data-flow-4" />

#### データ処理の流れ

1. ROI360 Purchase SDK Connectorから送信されたデータ、またはストアのS2S通知から収集した取引データを使用します。
2. AppsFlyer ROI360のVIAP／サブスクリプション機能がデータを処理して獲得元に紐づけ、アプリ内イベントを生成します。
3. アプリ内イベントを端末単位で集計し、4時間ごとにレポートの各バージョンに書き込みます。

<div id="when-are-the-report-versions-available-1" />

#### 各バージョンを利用できるタイミング

| バージョンの配信日（X＝収益イベントの発生日） | バージョンの利用開始時刻 | バージョンに含まれる収益イベントの発生期間 |
| --- | --- | --- |
| X日 | 04:00 - 05:00 | 00:00 — 04:00 |
| X日 | 12:00 - 13:00 | 00:00 — 12:00 |
| X日 | 20:00 - 21:00 | 00:00 — 20:00 |
| X＋1日 | 05:00 - 06:00 | 00:00 — 24:00 |

<div id="how-to-subscribe-to-the-report-4" />

#### レポートの配信設定

1. AppsFlyerのサイドメニューから<strong>［レポート］</strong>＞<strong>［Data Locker］</strong>を選択します。
2. <strong>［Data Lockerのコンテンツ］</strong>ペインを下にスクロールし、<strong>［ROI360収益ETL］</strong>タイルを探します。
3. <strong>［端末単位のストア収益レポート（更新版あり）］</strong>を選択します。

#### バケット内のレポートへのアクセス方法

レポートのパスは、次のフォルダー階層で構成されます。

`<bucket-name>/t=stores_devicedata/dt=<dt=yyyy-mm-dd>/version=<999999999>`

<div id="report-folder-hierarchy-4" />

#### レポートのフォルダー階層

広告主のバケットに保存される、レポートのフォルダー構造の例：

```
bucket
|
└── t=stores_devicedata
    |
    └── dt=2023-06-01
        |
        ├── version=1685588879
        |   |
        │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   |
        │   ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   │
        |   └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |
        ├── version=1685603326
        |   |
        │   ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   |
        │   ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   │
        |   └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |
        ├── version=1685617877
        .
                .
                .
```

**凡例：**

* **t：** レポートの種類
* **dt**：レポートに含まれる収益イベントの発生日。
* **version**：バージョン名は、そのバージョンが作成された日時のエポックタイムスタンプです。例：**version=1685588879**。

</Accordion>

<div data-zendesk-anchors="revenue-etl=%E5%8F%8E%E7%9B%8Aetl h_01HMBTDD8TASZ2NEBXP7CZ3Q81=%E5%8F%8E%E7%9B%8Aetl reports=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HME0BBF2M47M2AV437RYQ070=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HETBAQVVYW14END06HBPBQSN=ad-revenue-single-version-report-device-level h_01HETBAQVVZB87JNT0JVYSP80D=download-the-report-data-sample the-report-data-sources=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97%E5%85%83 h_01HETBAQVVSKVDM4J90A0WGFJW=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97%E5%85%83 the-report-data-flow=%E3%83%87%E3%83%BC%E3%82%BF%E5%87%A6%E7%90%86%E3%81%AE%E6%B5%81%E3%82%8C h_01HETBAQVV97R7G6F67RM6K62K=%E3%83%87%E3%83%BC%E3%82%BF%E5%87%A6%E7%90%86%E3%81%AE%E6%B5%81%E3%82%8C when-is-the-report-data-available=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%82%8B%E3%82%BF%E3%82%A4%E3%83%9F%E3%83%B3%E3%82%B0 h_01HETBAQVVKDAWW2S98TG6682S=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%82%8B%E3%82%BF%E3%82%A4%E3%83%9F%E3%83%B3%E3%82%B0 how-to-subscribe-to-the-report=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E9%85%8D%E4%BF%A1%E8%A8%AD%E5%AE%9A h_01HETBAQVVFSDRW778VQSSE107=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E9%85%8D%E4%BF%A1%E8%A8%AD%E5%AE%9A how-to-access-the-report-in-dl=%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E5%86%85%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%96%B9%E6%B3%95 h_01HETBAQVV15T92VXRHG2CP2KJ=%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E5%86%85%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%96%B9%E6%B3%95 the-report-folder-hierarchy-in-aws=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E3%83%BC%E9%9A%8E%E5%B1%A4 h_01HETBAQVVA750VTE1ABSM2M47=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E3%83%BC%E9%9A%8E%E5%B1%A4 h_01HETBAQVVCB2SYMW9876HPE7N=ad-revenue-versioned-report-device-level data-sources=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97%E5%85%83-1 h_01HMTZ9VQ5WE6D7E5NEBYH71SZ=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97%E5%85%83-1 data-flow=%E3%83%87%E3%83%BC%E3%82%BF%E5%87%A6%E7%90%86%E3%81%AE%E6%B5%81%E3%82%8C-1 h_01HMTZ9VQ5PS8G9JTQ2YXF1G7X=%E3%83%87%E3%83%BC%E3%82%BF%E5%87%A6%E7%90%86%E3%81%AE%E6%B5%81%E3%82%8C-1 when-are-the-report-versions-available=%E5%90%84%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%92%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%82%8B%E3%82%BF%E3%82%A4%E3%83%9F%E3%83%B3%E3%82%B0 h_01HETBAQVVP1M40KHB66AW545S=%E5%90%84%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%92%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%82%8B%E3%82%BF%E3%82%A4%E3%83%9F%E3%83%B3%E3%82%B0 how-to-subscribe-to-the-report::cae4aa15=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E9%85%8D%E4%BF%A1%E8%A8%AD%E5%AE%9A-1 h_01HMTZ9VQ5BBFNNE7Z8EP084CF=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E9%85%8D%E4%BF%A1%E8%A8%AD%E5%AE%9A-1 how-to-access-the-report-in-your-bucket=%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E5%86%85%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%96%B9%E6%B3%95-1 h_01HMTZ9VQ5FGBC56AP4R49P4BX=%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E5%86%85%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%96%B9%E6%B3%95-1 report-folder-hierarchy=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E3%83%BC%E9%9A%8E%E5%B1%A4-1 h_01HMTZ9VQ5HCKP7T3JQ2RHZV50=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E3%83%BC%E9%9A%8E%E5%B1%A4-1 h_01HETBAQVVR90NJC522WNAG190=impression-level-report the-source-of-the-report-data=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97%E5%85%83-2 h_01HETBAQVV3KBEW4VV4RY9VRA2=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97%E5%85%83-2 data-flow::c7ffb834=%E3%83%87%E3%83%BC%E3%82%BF%E5%87%A6%E7%90%86%E3%81%AE%E6%B5%81%E3%82%8C-2 h_01HMTZ9VQ5J837PGG99S8ARAGV=%E3%83%87%E3%83%BC%E3%82%BF%E5%87%A6%E7%90%86%E3%81%AE%E6%B5%81%E3%82%8C-2 when-is-the-report-data-available::272621c9=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%82%8B%E3%82%BF%E3%82%A4%E3%83%9F%E3%83%B3%E3%82%B0-1 h_01HMTZ9VQ5YQKBQ779YWBWESDZ=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%82%8B%E3%82%BF%E3%82%A4%E3%83%9F%E3%83%B3%E3%82%B0-1 how-to-subscribe-to-the-report::67646c99=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E9%85%8D%E4%BF%A1%E8%A8%AD%E5%AE%9A-2 h_01HMTZ9VQ5ZST1M7JYKFC3DA62=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E9%85%8D%E4%BF%A1%E8%A8%AD%E5%AE%9A-2 how-to-access-the-report-in-aws-the-bucket=%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E5%86%85%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%96%B9%E6%B3%95-2 h_01HETBAQVVHE80MH3SM3GX21V1=%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E5%86%85%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%96%B9%E6%B3%95-2 report-folder-hierarchy::26ec73c6=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E3%83%BC%E9%9A%8E%E5%B1%A4-2 h_01HMTZ9VQ5FFSA1XF7YSATM6WH=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E3%83%BC%E9%9A%8E%E5%B1%A4-2 h_01HETBAQVWZKYBAG5E71KVB9PM=transactionlevel-stores-revenue-report data-sources::68e71455=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97%E5%85%83-3 h_01HMTZ9VQ5SWTWTSNW5M9KJ1XN=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97%E5%85%83-3 data-flow::bde19643=%E3%83%87%E3%83%BC%E3%82%BF%E5%87%A6%E7%90%86%E3%81%AE%E6%B5%81%E3%82%8C-4 h_01HMTZ9VQ6XVHDHBKV86F3Q9DJ=%E3%83%87%E3%83%BC%E3%82%BF%E5%87%A6%E7%90%86%E3%81%AE%E6%B5%81%E3%82%8C-4 when-is-the-report-data-available::87d17fc2=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%82%8B%E3%82%BF%E3%82%A4%E3%83%9F%E3%83%B3%E3%82%B0-2 h_01HMTZ9VQ64AJQM861M6ENHVWC=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%82%8B%E3%82%BF%E3%82%A4%E3%83%9F%E3%83%B3%E3%82%B0-2 how-to-subscribe-to-the-report::6569d202=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E9%85%8D%E4%BF%A1%E8%A8%AD%E5%AE%9A-3 h_01HMTZ9VQ60HMM6TXAPYSZG5CT=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E9%85%8D%E4%BF%A1%E8%A8%AD%E5%AE%9A-3 how-to-access-the-report-in-your-bucket::b136ba80=%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E5%86%85%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%96%B9%E6%B3%95-3 h_01HMTZ9VQ67ZEX3KM6CV32SNBD=%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E5%86%85%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%96%B9%E6%B3%95-3 report-folder-hierarchy::805d4d8=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E3%83%BC%E9%9A%8E%E5%B1%A4-3 h_01HMTZ9VQ68VRJRHXSNAE38A0E=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E3%83%BC%E9%9A%8E%E5%B1%A4-3 h_01HETBAQVVWAFEMK8ENWN7DYEY=devicelevel-stores-revenue-report h_01HETBAQVV9PSDJNS76SNX522C=download-the-report-data-sample::8cbba4e3 the-report-data-sources::af31e5d1=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97%E5%85%83-4 h_01HETBAQVWE2R75D034VCYMTR1=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97%E5%85%83-4 the-report-data-processing-flow=%E3%83%87%E3%83%BC%E3%82%BF%E5%87%A6%E7%90%86%E3%81%AE%E6%B5%81%E3%82%8C-4 h_01HETBAQVWZRBE84NV403BCZ9F=%E3%83%87%E3%83%BC%E3%82%BF%E5%87%A6%E7%90%86%E3%81%AE%E6%B5%81%E3%82%8C-4 when-are-the-report-versions-available::2f1bc55f=%E5%90%84%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%92%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%82%8B%E3%82%BF%E3%82%A4%E3%83%9F%E3%83%B3%E3%82%B0-1 h_01HETBAQVWQFCKHMT6PJNPXX7D=%E5%90%84%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%92%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%82%8B%E3%82%BF%E3%82%A4%E3%83%9F%E3%83%B3%E3%82%B0-1 how-to-subscribe-to-the-report::a624afde=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E9%85%8D%E4%BF%A1%E8%A8%AD%E5%AE%9A-4 h_01HETBAQVW54MD9Q09RNC673PE=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E9%85%8D%E4%BF%A1%E8%A8%AD%E5%AE%9A-4 how-to-access-the-report-in-the-aws-bucket=%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E5%86%85%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%96%B9%E6%B3%95-4 h_01HETBAQVWYDR81WS9Q9G20ZND=%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E5%86%85%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%96%B9%E6%B3%95-4 the-report-folder-hierarchy-in-aws::45c0d598=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E3%83%BC%E9%9A%8E%E5%B1%A4-4 h_01HETBAQVWXHK6DXFA90GJQWPV=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E3%83%BC%E9%9A%8E%E5%B1%A4-4" />
