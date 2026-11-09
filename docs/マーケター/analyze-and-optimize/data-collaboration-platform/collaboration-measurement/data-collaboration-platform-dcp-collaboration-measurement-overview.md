---
title: Data Collaboration Platform（DCP）｜コラボレーション計測の概要
metadata:
  keywords:
    - Marketers
    - Retail Media Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Retail Media Measurement
  created_at: '2025-01-27T08:21:27Z'
  edited_at: '2026-10-14T09:31:26Z'
  id: 32143318560017
  locale: ja
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/ja/articles/32143318560017
---
> **概要：** コラボレーション計測の基本的な考え方とデータフローについて説明しています。

<div id="the-three-data-sources-of-measurement" />

## 計測に使用する3つのデータソース

DCPの計測モデルでは、コラボレーションの中で発生したエンゲージメントイベントにコンバージョンイベントを紐づけ、アトリビューションを行います。このプロセスでは、コンバージョン、エンゲージメント、キャンペーンマッピングという3つの主要なデータソースを使用します。それぞれのデータソースが、アトリビューションの過程で重要な役割を担います。

<div id="conversions" />

<Accordion title="コンバージョン">

コンバージョンデータには、購入などのユーザーアクションと、それに関連するSKU（Stock Keeping Unit）やCPG（Consumer Packaged Goods）などの情報が含まれます。各レコードは1件のコンバージョンイベントを表し、SKU、ユーザーID、イベント発生時刻などの情報を保持します。

**コンバージョンパラメーターの例**

| **フィールド** | **値** |
| --- | --- |
| `app_id` | FoodDelivery |
| `user_id` | 5abe2ddccca43000af58f0b |
| `event_time` | 2024-08-21T16:06:32.393Z |
| `event_name` | purchase |
| `sku` | 8711327623057 |
| `sku_revenue` | 6.94 |
| `sku_quantity` | 1 |

アプリのコンバージョンデータは、AppsFlyer SDKを使ってアプリと連携する方法、またはコラボレーターが提供するカスタムデータソースを通じてAppsFlyerに取り込めます。Webや実店舗で発生したコンバージョンイベントも、カスタムデータソースを使用して取り込むことができます。

</Accordion>

<div id="engagements" />

<Accordion title="エンゲージメント">

エンゲージメントのデータソースには、クリックやインプレッションなど、ユーザーと広告との接点に関する情報が含まれます。各レコードは1件のエンゲージメントイベントを表し、キャンペーンID、メディアソース、タッチタイプ（クリックやインプレッションなど）といった情報を保持します。

**エンゲージメントパラメーターの例**

| **フィールド** | **値** |
| --- | --- |
| `appsflyer_id` | 1727548724223 |
| `media_source` | google |
| `campaign` | grc\_web\_ftu\_seq |
| `attributed_touch_time` | 2024-09-28T17:05:34 |
| `attributed_touch_type` | impression |
| `event_name` | start\_game |

[オンサイトキャンペーン](/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#onsite-and-offsite-campaign-measurement)でエンゲージメントデータを利用するには、AppsFlyer SDKを使用し、`event_value` パラメーターにアトリビューションデータを含めた新しいアプリ内イベントを設定するか、カスタムソース経由でデータを共有します。

[オフサイトキャンペーンでは、エンゲージメントデータを外部プラットフォームから取得し](/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#onsite-and-offsite-campaign-measurement)、アプリ内イベントやカスタムソースは使用しません。

</Accordion>

<div id="campaign-mapping" />

<Accordion title="キャンペーンマッピング">

キャンペーンマッピングのデータソースを使うことで、各コンバージョンのきっかけとなったエンゲージメントを特定できます。キャンペーンマッピングの各レコードでは、SKUまたはCPGとキャンペーンIDを対応付けることで、コンバージョンイベントとエンゲージメントイベントを紐づけます。DCPはこのマッピングを使用して、特定のSKUを含むコンバージョンイベントを、対応するキャンペーンIDを持つエンゲージメントイベントに紐づけます。

**キャンペーンマッピングパラメーターの例**

| **フィールド** | **値** |
| --- | --- |
| `collaborator_name` | fashion\_site |
| `collaborator_id` | 10079 |
| `campaign_id` | 49fd77a2-8b64-4c9d... |
| `campaign_name` | off\_season\_25\_1 |
| `conversion_targets` | 8711327621978, 8711327622289, 8711327623057 |

キャンペーンマッピングの情報は、カスタムデータソースとしてAppsFlyerに提供されます。

</Accordion>

<div id="on-site-vs-off-site-campaigns" />

## オンサイトキャンペーンとオフサイトキャンペーン

DCPでは、キャンペーンがコラボレーター自身のサイト（オンサイト）で実施されるか、メディアパートナーのプラットフォーム（オフサイト）で実施されるかによって、計測方法が異なります。この違いによって、オーディエンスへのリーチ方法、データの収集方法、アトリビューションの実行方法も変わります。

<div id="offsite-campaigns" />

<Accordion title="オフサイトキャンペーン">

オフサイトキャンペーンでは、MetaやGoogleなどの外部プラットフォーム上でユーザーとのエンゲージメントが発生し、コンバージョンはコラボレーター自身のサイトやアプリ内で発生します。これらのコンバージョンは、オフサイトでのエンゲージメントにアトリビューションされます。

* **例：** ブランドが、CMNでセグメント化された顧客データをもとに、Facebook広告を配信します。ユーザーがFacebook上で広告を見てクリックすると、CMNの商品ページへ遷移します。
* **アトリビューション：** DCPはコンバージョンイベントを外部プラットフォームと共有し、外部プラットフォーム側でアトリビューションを実行します。その後、DCPが各プラットフォームのレポートAPI経由で集計結果を取得します。

</Accordion>

<div id="onsite-campaigns" />

<Accordion title="オンサイトキャンペーン">

オンサイトキャンペーンでは、ユーザーとのエンゲージメントとコンバージョンの両方が、コラボレーター自身のアプリやWebサイトなどで発生し、コンバージョンはオンサイトでのエンゲージメントにアトリビューションされます。

* **例：** ブランドがCommerce Media NetworkのWebサイト上で商品をプロモーションします。オーディエンスには、カテゴリへの関心や購入履歴などの条件でセグメント化された、CMNプラットフォームの過去の購入者が含まれます。ユーザーがキャンペーンバナーを見てクリックすると、同じサイト内の商品詳細ページへ遷移します。
* **アトリビューション：** DCPは、コラボレーターのWebサイトやアプリから取得したファーストパーティのエンゲージメントデータを使用して、コンバージョンをオンサイトキャンペーンに直接アトリビューションします。

<div id="combined-onsite-and-offsite-campaigns" />

<Accordion title="オンサイトとオフサイトを組み合わせたキャンペーン">

オンサイトとオフサイトを組み合わせたキャンペーンでは、両方の環境でユーザーとのエンゲージメントが発生します。コンバージョンはコラボレーター自身のサイトやアプリ内で発生し、統合計測と重複排除によって、いずれかのエンゲージメントにアトリビューションされます。

* **例：** ブランドがCMNのWebサイト上で商品をプロモーションすると同時に、CMNの顧客を対象としたFacebook広告も配信します。オンサイトキャンペーンとFacebookキャンペーンの両方から発生したエンゲージメントとコンバージョンを取得し、重複を排除したうえで一元的に計測します。
* **アトリビューション：** DCPはオンサイトとオフサイトの両方のチャネルから得られたコンバージョンデータを共通のアトリビューションテーブルに統合し、重複排除を行ったうえで、キャンペーンおよびSKU単位の統合指標を提供します。

</Accordion>

</Accordion>

<div id="the-dcp-measurement-process" />

## DCPの計測プロセス

DCPの計測プロセスでは、SDKのアプリ内イベントやカスタムソースファイルから取得したコンバージョンレコードを検証・標準化し、[オンサイトとオフサイトのキャンペーン](https://www.notion.so/Collaboration-measurement-Overview-255b7b13af5f80fa83d2dc77e337c960?pvs=21)におけるエンゲージメントと照合します。

<div id="onsite-measurement-flow" />

<Accordion title="オンサイト計測フロー">

DCPのオンサイト計測フローでは、CMNまたは広告主のモバイルアプリやWebサイトから収集したアプリ内イベントとカスタムソースレコードを処理します。DCPは、AppsFlyerのアトリビューションロジックを使用して、これらのコンバージョンを内部でアトリビューションします。

オンサイト計測では、主に以下2つのデータソースから取得したコンバージョンデータとエンゲージメントデータを処理します。

* **アプリ内イベント（IAE）**：コラボレーターのモバイルアプリに実装されたAppsFlyer SDKを通じて収集されます。
* **カスタムソースのイベントファイル**：コラボレーターからAppsFlyerへ送信されます。

どちらのイベントも共通の形式に標準化され、同じアトリビューションエンジンで処理されます。

<div id="1-configure-measurement-sources" />

### 1.計測ソースを設定する

コラボレーターは、DCPのオンライン計測プロセスを以下のように設定します。

* **アプリ内イベント：** 購入やサインアップなど、どのアプリ内イベントをコンバージョンまたはエンゲージメントとして計測するかを指定します。対象イベントはAppsFlyer SDKですでに収集されている必要があり、DCPの設定画面でアプリ名とイベント名を明示的に選択します。
* **カスタムソースのイベントファイル：** BigQuery、S3、Snowflakeなどの外部データファイルへのアクセスを設定し、user\_id、campaign\_id、SKUなどの主要フィールドをDCPスキーマにマッピングして、アトリビューションに利用できるようにします。

<div id="2-prepare-and-map-conversion-data" />

### 2.コンバージョンデータを準備・マッピングする

コンバージョンイベントには、キャンペーンによって生じたアクションをDCPが判定するために使用するSKUやユーザー識別子が含まれます。

* DCPは、キャンペーンマッピングのデータソースとコンバージョンイベント内のSKUを照合し、計測対象キャンペーンによって発生したコンバージョンを特定します。
* どのキャンペーンにも一致しないコンバージョンは、**オーガニック**として扱われます。

<div id="3-link-conversions-to-engagements" />

### 3.コンバージョンをエンゲージメントに紐づける

DCPは、以下の条件を使用して、一致したコンバージョンをエンゲージメントに紐づけます。

* 共通の**ユーザーID**
* 同一の**キャンペーンID**

これにより、キャンペーンとエンゲージメントのメタデータが付加された、アトリビューション済みのコンバージョンレコードが作成されます。

<div id="4-split-multi-sku-conversions" />

### 4.複数SKUを含むコンバージョンを分割する

コンバージョンイベントに複数のSKUが含まれる場合：

* DCPは、そのレコードを複数の**単一SKU**レコードに分割します。
* 各レコードには、1つの**コンバージョン対象**に対するアトリビューション結果が含まれます。

<div id="5-filter-non-target-skus" />

### 5.対象外のSKUを除外する

関連するコンバージョンだけを残すため、以下の処理を行います。

* DCPは、関連するキャンペーンのコンバージョン対象として定義されていないSKUのレコードを除外します。

<div id="6-deduplicate-conversion-events" />

### 6.コンバージョンイベントの重複を排除する

アトリビューションを行う前に、DCPは重複データを除外します。

* 同じカスタムソースに重複レコードがある場合（同じファイルが繰り返しアップロードされた場合など）は、重複分を破棄します。
* 一致するアプリ内イベント（IAE）が存在する場合は、カスタムソースのレコードよりもIAEが優先されます。

<div id="7-apply-attribution-logic" />

### 7.アトリビューションロジックを適用する

DCPは、AppsFlyerのラストタッチアトリビューションモデルを以下のルールで適用します。

* **1件のコンバージョンに複数のエンゲージメントがある場合**：AppsFlyerの優先順位に基づいて、**ラストタッチ**を選択します。
* **1件のエンゲージメントに複数のコンバージョンが紐づく場合**：そのエンゲージメントには**最初**のコンバージョンのみがアトリビューションされ、それ以降のコンバージョンは未アトリビューションとして扱われます。

> 詳しくは、「アトリビューション方法の優先順位（アトリビューションウォーターフォール）」を参照してください。

<div id="8-output-attributed-conversion-dataset" />

### 8.出力：アトリビューション済みコンバージョンデータセット

最終的に、以下のデータが出力されます。

* 各コンバージョンについて、1つのキャンペーンエンゲージメントへのアトリビューション結果
* クレンジングおよび検証済みのSKU単位のコンバージョンレコード
* DCPはアトリビューション済みのコンバージョンを集計し、総コンバージョン数などのインサイトを生成します。
* 分析ダッシュボードやエクスポートに利用できるコンバージョンレコード

</Accordion>

<div id="offsite-measurement-flow" />

<Accordion title="オフサイト計測フロー">

**オフサイトのコンバージョンイベント**は、コラボレーターから**カスタムソースファイル**を通じて提供され、Google Click ID（`gclid`）やFacebook Click ID（`fbclid`）など、アトリビューションに必要な識別子を含める必要があります。これらのイベントはGoogleやMetaなどの外部プラットフォームと共有されます。各プラットフォームは自社のキャンペーンレコードとデータを照合し、キャンペーン、広告セット、クリエイティブの識別子などを含む**拡張メタデータ**を返します。

<div id="1-prepare-conversion-data" />

### 1.コンバージョンデータを準備する

コラボレーションの設定に基づいて、コンバージョンレコードを標準化します。

* コラボレーターは、カスタムフィールドをDCP共通のコンバージョンスキーマにマッピングします。
* Google AdsとMeta Adsではそれぞれ固有のフィールドが必要です。検証ルールによって、処理を進める前に各パートナーの要件を満たしているかを確認します。

<div id="2-deduplicate-conversion-events" />

### 2.コンバージョンイベントの重複を排除する

アトリビューションを行う前に、同じカスタムソースに含まれる重複レコード（同じファイルが繰り返しアップロードされた場合など）をDCPが除外します。

<div id="3-filter-for-sharing-eligibility" />

### 3.共有対象のコンバージョンを絞り込む

DCPは、オフサイトのコンバージョンが共有条件を満たしているかを確認します。

* チャネルごとの有効な識別子（GCLID、FBCLIDなど）が含まれていること。
* コンバージョンが、定義済みのキャンペーンアクションまたはSKUと一致していること。
* コンバージョンがルックバック期間内に発生していること。
  * Meta：クリックとビュースルーのどちらも1日、7日、または28日。
  * Google：プラットフォーム上で設定します。APIからの上書きはサポートされていません。

いずれかの条件を満たさないコンバージョンは、パートナーへの共有対象から除外されます。

<div id="4-filter-according-to-last-touch-attribution" />

### 4.ラストタッチアトリビューションに基づいて絞り込む

最も新しいタッチポイントに基づいて、アトリビューション先を決定します。

* 有効なGoogleまたはMetaのクリックIDが最新のタッチポイントである場合、そのパートナーにアトリビューションし、該当するパートナーにのみ共有します。
* コンバージョンに両方のクリックIDが含まれている場合は、より新しいものが優先されます。

<div id="5-share-with-google-and-meta" />

### 5.GoogleとMetaに共有する

共有条件を満たしたコンバージョンは、パートナーAPIを通じて安全に共有されます。

* **Meta：** Conversions API（CAPI）
* **Google：** Offline Conversion API（OCI）

各コンバージョンは、いずれか1つのパートナーにのみ送信されます。コラボレーターは、送信先アカウント（Meta Dataset IDまたはGoogle Conversion Action ID）を設定する必要があります。

<div id="6-google-and-meta-response-enrichment" />

### 6.GoogleとMetaから返されたデータで情報を補完する

GoogleとMetaは、Insights API経由で以下のようなアトリビューション情報を返します。

* Campaign ID
* Ad Set ID
* Ad ID
* Creative ID

AppsFlyerは、補完されたレコードをもとにアトリビューションを行います。

<div id="7-output-attributed-conversion-dataset" />

### 7.出力：アトリビューション済みコンバージョンデータセット

最終的に、以下のデータが出力されます。

* クレンジングおよび検証済みのSKU単位のコンバージョンレコード
* DCPはアトリビューション済みのコンバージョンを集計し、総コンバージョン数などのインサイトを生成します。
* 分析ダッシュボードやエクスポートに利用できるコンバージョンレコード

</Accordion>

<div id="combined-onsite-and-offsite-measurement-flow" />

<Accordion title="オンサイトとオフサイトを組み合わせた計測フロー">

このフローでは、AppsFlyerのData Collaboration Platform（DCP）が、以下を含む複数のソースから取得したコンバージョンデータをどのように処理するかを説明します。

* **オンサイトコンバージョン**：CMNまたは広告主のモバイルアプリやWebサイトから収集したアプリ内イベントとカスタムソースレコードが含まれます。DCPは、AppsFlyerのアトリビューションロジックを使用して、これらのコンバージョンを内部でアトリビューションします。
* **オフサイトコンバージョン**：カスタムソースから取得したコンバージョンデータを、GoogleやMetaなどの外部プラットフォームと共有します。これらのプラットフォームは、自社のキャンペーンレコードとデータを照合し、キャンペーン、広告セット、クリエイティブの識別子などを含む拡張メタデータを返します。

DCPのオンサイト／オフサイトのアトリビューションフローでは、すべてのコンバージョンデータに対して重複排除、アトリビューション、情報の補完、統合を行い、1つの統合パフォーマンスデータセットを生成します。

<Image align="center" alt="Notion 2025-08-25 16.10.35.png" src="https://files.readme.io/1552e0c84bf4ca98ef0fd9f96096f68bbf1a1f846f3fcc995e1aa0afe065a651-38422017654929.png" width="1622px" />

<div id="1-on-site-and-off-site-record-processing-is-performed" />

### 1.オンサイトとオフサイトのレコードを処理する

コラボレーションの設定に基づいて、コンバージョンレコードを標準化します。

* オンサイトでは、オンサイトアトリビューションのステップ6までを実行します。
* オフサイトでは、オフサイトアトリビューションのステップ4までを実行します。

<div id="2-apply-last-touch-attribution" />

### 2.ラストタッチアトリビューションを適用する

最も新しいタッチポイントに基づいて、アトリビューション先を決定します。

* CMN（オンサイト）イベントが最新のタッチポイントである場合、コンバージョンはCMNにアトリビューションされ、MetaやGoogleには共有されません。
* 有効なGoogleまたはMetaのクリックIDが最新のタッチポイントである場合、そのパートナーにアトリビューションし、該当するパートナーにのみ共有します。
* コンバージョンに両方のクリックIDが含まれている場合は、より新しいものが優先されます。

<div id="3-share-with-google-and-meta" />

### 3.GoogleとMetaに共有する

共有条件を満たしたコンバージョンは、パートナーAPIを通じて安全に共有されます。

* **Meta：** Conversions API（CAPI）
* **Google：** Offline Conversion API（OCI）

各コンバージョンは、いずれか1つのパートナーにのみ送信されます。広告主は、送信先アカウント（Meta Dataset IDまたはGoogle Conversion Action ID）を設定する必要があります。

<div id="4-off-site-response-enrichment" />

### 4.オフサイト側から返されたデータで情報を補完する

GoogleとMetaは、Insights API経由で以下のようなアトリビューション情報を返します。

* Campaign ID
* Ad Set ID
* Ad ID
* Creative ID

<div id="5-on-site-and-off-site-conversion-merge" />

### 5.オンサイトとオフサイトのコンバージョンを統合する

DCPは、オフサイトのコンバージョンとオンサイトのコンバージョンを統合し、各コンバージョンについて以下の情報を含む最終データセットを生成します。

* 1つのソースにアトリビューション：Google、Meta、またはCMN
* キャンペーンメタデータを付加
* ダッシュボード、エクスポート、パフォーマンス分析に利用可能

</Accordion>

<div id="set-up-collaboration-measurement" />

## コラボレーション計測の設定ステップ

計測の設定は以下のステップで進めます。各ステップについて、詳しい手順を説明する記事が用意されています。

1. <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-determine-your-collaboration-measurement-use-cas">自社に適したコラボレーション計測のユースケースを検討する</Anchor>
2. <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement">アトリビューションに使用するデータソースを準備する</Anchor>
3. <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-configure-collaboration-measurement">DCPからデータソースへアクセスし、アトリビューションを実行できるよう設定する</Anchor>
4. <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-view-measurement-dashboard">アトリビューション済みの計測データをダッシュボードで確認する</Anchor>
5. <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-view-measurement-reports">アトリビューション済みの計測データをレポートで確認する</Anchor>

<div data-zendesk-anchors="the-three-data-sources-of-measurement=%E8%A8%88%E6%B8%AC%E3%81%AB%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B3%E3%81%A4%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BD%E3%83%BC%E3%82%B9 h_01K3GNC7NFJV6W4NPEXJ4SKSKA=%E8%A8%88%E6%B8%AC%E3%81%AB%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B3%E3%81%A4%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BD%E3%83%BC%E3%82%B9 h_01K3GNC7NF2ZASWHYZJCPYHF2D=conversions h_01K3GNC7NFMAQ8S8A0YN79YRM8=engagements h_01K3GNC7NG2QYKV3ZTGYEHMDYT=campaign-mapping onsite-vs-offsite-campaigns=%E3%82%AA%E3%83%B3%E3%82%B5%E3%82%A4%E3%83%88%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%A8%E3%82%AA%E3%83%95%E3%82%B5%E3%82%A4%E3%83%88%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3 h_01K3GNC7NGP2FXZXQRAS5H8DE1=%E3%82%AA%E3%83%B3%E3%82%B5%E3%82%A4%E3%83%88%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%A8%E3%82%AA%E3%83%95%E3%82%B5%E3%82%A4%E3%83%88%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3 h_01K3GNC7NGDDSBGTPD7WVH1H2N=offsite-campaigns h_01K3GNC7NGKHSC7W6B5GG3M10Y=onsite-campaigns h_01K3GNC7NGMG4CCSWVJAVEN24E=combined-onsite-and-offsite-campaigns the-dcp-measurement-process=dcp%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%97%E3%83%AD%E3%82%BB%E3%82%B9 h_01K3GNC7NG1S37JPMH31A6RRSR=dcp%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%97%E3%83%AD%E3%82%BB%E3%82%B9 h_01K3GNC7NGKJNH3BX53PJ9HQ90=onsite-measurement-flow 1-configure-measurement-sources=1%E8%A8%88%E6%B8%AC%E3%82%BD%E3%83%BC%E3%82%B9%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01K3GPJQJC29ZJJTMM9BHA97H1=1%E8%A8%88%E6%B8%AC%E3%82%BD%E3%83%BC%E3%82%B9%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B 2-prepare-and-map-conversion-data=2%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E6%BA%96%E5%82%99%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%81%99%E3%82%8B h_01K3GNC7NGMSPQTGNNCRYVWWW4=2%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E6%BA%96%E5%82%99%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%81%99%E3%82%8B 3-link-conversions-to-engagements=3%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%92%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%81%AB%E7%B4%90%E3%81%A5%E3%81%91%E3%82%8B h_01K3GNC7NGJPNZ3EEMHQP5E04V=3%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%92%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%81%AB%E7%B4%90%E3%81%A5%E3%81%91%E3%82%8B 4-split-multisku-conversions=4%E8%A4%87%E6%95%B0sku%E3%82%92%E5%90%AB%E3%82%80%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%92%E5%88%86%E5%89%B2%E3%81%99%E3%82%8B h_01K3GNC7NG6DX2B825C5B6TVS0=4%E8%A4%87%E6%95%B0sku%E3%82%92%E5%90%AB%E3%82%80%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%92%E5%88%86%E5%89%B2%E3%81%99%E3%82%8B 5-filter-nontarget-skus=5%E5%AF%BE%E8%B1%A1%E5%A4%96%E3%81%AEsku%E3%82%92%E9%99%A4%E5%A4%96%E3%81%99%E3%82%8B h_01K3GNC7NGSED134G0PGDZGPDB=5%E5%AF%BE%E8%B1%A1%E5%A4%96%E3%81%AEsku%E3%82%92%E9%99%A4%E5%A4%96%E3%81%99%E3%82%8B 6-deduplicate-conversion-events=6%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%87%8D%E8%A4%87%E3%82%92%E6%8E%92%E9%99%A4%E3%81%99%E3%82%8B h_01K3GNC7NGBDJ2JCY0HQ61412X=6%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%87%8D%E8%A4%87%E3%82%92%E6%8E%92%E9%99%A4%E3%81%99%E3%82%8B 7-apply-attribution-logic=7%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AD%E3%82%B8%E3%83%83%E3%82%AF%E3%82%92%E9%81%A9%E7%94%A8%E3%81%99%E3%82%8B h_01K3GNC7NG7Y8XZ9VH3SK47DAR=7%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AD%E3%82%B8%E3%83%83%E3%82%AF%E3%82%92%E9%81%A9%E7%94%A8%E3%81%99%E3%82%8B 8-output-attributed-conversion-dataset=8%E5%87%BA%E5%8A%9B%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%B8%88%E3%81%BF%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BB%E3%83%83%E3%83%88 h_01K3GNC7NGFY21QVJY8QRNHGVK=8%E5%87%BA%E5%8A%9B%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%B8%88%E3%81%BF%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BB%E3%83%83%E3%83%88 h_01K3GNC7NHG5GBRC0X4M5DZ6PP=offsite-measurement-flow 1-prepare-conversion-data=1%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E6%BA%96%E5%82%99%E3%81%99%E3%82%8B h_01K3GNC7NH3CP2HMZTFDK050FA=1%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E6%BA%96%E5%82%99%E3%81%99%E3%82%8B 2-deduplicate-conversion-events=2%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%87%8D%E8%A4%87%E3%82%92%E6%8E%92%E9%99%A4%E3%81%99%E3%82%8B h_01K3GNC7NHD0REAV4Q4EMEXPPX=2%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%87%8D%E8%A4%87%E3%82%92%E6%8E%92%E9%99%A4%E3%81%99%E3%82%8B 3-filter-for-sharing-eligibility=3%E5%85%B1%E6%9C%89%E5%AF%BE%E8%B1%A1%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%92%E7%B5%9E%E3%82%8A%E8%BE%BC%E3%82%80 h_01K3GNC7NHX6VN5XV5ADTH92CT=3%E5%85%B1%E6%9C%89%E5%AF%BE%E8%B1%A1%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%92%E7%B5%9E%E3%82%8A%E8%BE%BC%E3%82%80 4-filter-according-to-lasttouch-attribution=4%E3%83%A9%E3%82%B9%E3%83%88%E3%82%BF%E3%83%83%E3%83%81%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E5%9F%BA%E3%81%A5%E3%81%84%E3%81%A6%E7%B5%9E%E3%82%8A%E8%BE%BC%E3%82%80 h_01K3GNC7NH598P4G6VVSBQNVTF=4%E3%83%A9%E3%82%B9%E3%83%88%E3%82%BF%E3%83%83%E3%83%81%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E5%9F%BA%E3%81%A5%E3%81%84%E3%81%A6%E7%B5%9E%E3%82%8A%E8%BE%BC%E3%82%80 5-share-with-google-and-meta=5google%E3%81%A8meta%E3%81%AB%E5%85%B1%E6%9C%89%E3%81%99%E3%82%8B h_01K3GNC7NHAQMGXH6JJKEWHGV5=5google%E3%81%A8meta%E3%81%AB%E5%85%B1%E6%9C%89%E3%81%99%E3%82%8B 6-google-and-meta-response-enrichment=6google%E3%81%A8meta%E3%81%8B%E3%82%89%E8%BF%94%E3%81%95%E3%82%8C%E3%81%9F%E3%83%87%E3%83%BC%E3%82%BF%E3%81%A7%E6%83%85%E5%A0%B1%E3%82%92%E8%A3%9C%E5%AE%8C%E3%81%99%E3%82%8B h_01K3GNC7NHVWVZ10A1Y4DW5M6G=6google%E3%81%A8meta%E3%81%8B%E3%82%89%E8%BF%94%E3%81%95%E3%82%8C%E3%81%9F%E3%83%87%E3%83%BC%E3%82%BF%E3%81%A7%E6%83%85%E5%A0%B1%E3%82%92%E8%A3%9C%E5%AE%8C%E3%81%99%E3%82%8B 7-output-attributed-conversion-dataset=7%E5%87%BA%E5%8A%9B%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%B8%88%E3%81%BF%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BB%E3%83%83%E3%83%88 h_01K3GNC7NHFTD0CKQ2GSNNCE25=7%E5%87%BA%E5%8A%9B%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%B8%88%E3%81%BF%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BB%E3%83%83%E3%83%88 h_01K3GNC7NHM6HAYCJ9Q1CX359B=combined-onsite-and-offsite-measurement-flow 1-onsite-and-offsite-record-processing-is-performed=1%E3%82%AA%E3%83%B3%E3%82%B5%E3%82%A4%E3%83%88%E3%81%A8%E3%82%AA%E3%83%95%E3%82%B5%E3%82%A4%E3%83%88%E3%81%AE%E3%83%AC%E3%82%B3%E3%83%BC%E3%83%89%E3%82%92%E5%87%A6%E7%90%86%E3%81%99%E3%82%8B h_01K3GNC7NHW2M399S909QZE9H9=1%E3%82%AA%E3%83%B3%E3%82%B5%E3%82%A4%E3%83%88%E3%81%A8%E3%82%AA%E3%83%95%E3%82%B5%E3%82%A4%E3%83%88%E3%81%AE%E3%83%AC%E3%82%B3%E3%83%BC%E3%83%89%E3%82%92%E5%87%A6%E7%90%86%E3%81%99%E3%82%8B 2-apply-lasttouch-attribution=2%E3%83%A9%E3%82%B9%E3%83%88%E3%82%BF%E3%83%83%E3%83%81%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%92%E9%81%A9%E7%94%A8%E3%81%99%E3%82%8B h_01K3GNC7NH3XJRK6N0PC8BWPXT=2%E3%83%A9%E3%82%B9%E3%83%88%E3%82%BF%E3%83%83%E3%83%81%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%92%E9%81%A9%E7%94%A8%E3%81%99%E3%82%8B 3-share-with-google-and-meta=3google%E3%81%A8meta%E3%81%AB%E5%85%B1%E6%9C%89%E3%81%99%E3%82%8B h_01K3GNC7NHXMDC2CQQN8Q95DNH=3google%E3%81%A8meta%E3%81%AB%E5%85%B1%E6%9C%89%E3%81%99%E3%82%8B 4-offsite-response-enrichment=4%E3%82%AA%E3%83%95%E3%82%B5%E3%82%A4%E3%83%88%E5%81%B4%E3%81%8B%E3%82%89%E8%BF%94%E3%81%95%E3%82%8C%E3%81%9F%E3%83%87%E3%83%BC%E3%82%BF%E3%81%A7%E6%83%85%E5%A0%B1%E3%82%92%E8%A3%9C%E5%AE%8C%E3%81%99%E3%82%8B h_01K3GNC7NHVGQNNVWMKZTAQ03D=4%E3%82%AA%E3%83%95%E3%82%B5%E3%82%A4%E3%83%88%E5%81%B4%E3%81%8B%E3%82%89%E8%BF%94%E3%81%95%E3%82%8C%E3%81%9F%E3%83%87%E3%83%BC%E3%82%BF%E3%81%A7%E6%83%85%E5%A0%B1%E3%82%92%E8%A3%9C%E5%AE%8C%E3%81%99%E3%82%8B 5-onsite-and-offsite-conversion-merge=5%E3%82%AA%E3%83%B3%E3%82%B5%E3%82%A4%E3%83%88%E3%81%A8%E3%82%AA%E3%83%95%E3%82%B5%E3%82%A4%E3%83%88%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%92%E7%B5%B1%E5%90%88%E3%81%99%E3%82%8B h_01K3GNC7NH2PZ2KFBJHTG1ZZTE=5%E3%82%AA%E3%83%B3%E3%82%B5%E3%82%A4%E3%83%88%E3%81%A8%E3%82%AA%E3%83%95%E3%82%B5%E3%82%A4%E3%83%88%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%92%E7%B5%B1%E5%90%88%E3%81%99%E3%82%8B set-up-collaboration-measurement-in-four-steps=%E3%82%B3%E3%83%A9%E3%83%9C%E3%83%AC%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%82%B9%E3%83%86%E3%83%83%E3%83%97 h_01K3GNC7NHSCW4C2845N0MVQZM=%E3%82%B3%E3%83%A9%E3%83%9C%E3%83%AC%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%82%B9%E3%83%86%E3%83%83%E3%83%97" />
