---
title: ROI360のコストETLレポートの設定と利用方法
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
  edited_at: '2026-10-28T08:43:31Z'
  id: 360008849238
  locale: ja
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/ja/articles/360008849238
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** AppsFlyer ROI360のコストETLでは、メディアソースごとに取得できる最も詳細なキャンペーン広告費データを、広告主に提供します。データは1日最大4回更新され、広告主のBIシステムに取り込める形式でクラウドサービスに配信されます。

<Image align="center" alt="5896_CostETL_graphic__2_.png" src="https://files.readme.io/3c9b8721fa4aba170c1ed7b7b365b4a5fe1cd74080469b3020d395352cede674-11178721788817.png" />

AppsFlyer ROI360のコストETLでは、メディアソースごとに取得できる最も詳細なキャンペーン広告費データを、広告主に提供します。データは1日最大4回更新され、広告主のBIシステムに取り込める形式で、Data Lockerの配信先クラウドサービスに送信されます。

複数のクラウド配信先に、同時にレポートを送信することも簡単にできます。複数のサービスでデータを同時に利用できるため、クラウドサービスを移行する際にも役立ちます。

コストETLレポートには、AppsFlyerのアトリビューションに紐づく広告費データと、インストール数、リアトリビューション数、リエンゲージメント数などのアトリビューション指標が含まれます。

<div id="four-types-of-cost-etl-reports" />

## 4種類のコストETLレポート

分析の目的に応じて、4種類のコストETLレポートを利用できます。

* **サマリーレポート：** （デフォルト）メディアソース別に集計した、広告費の概要データ。広告費と成果指標の全体的な傾向を分析する場合に推奨します。
* **国別レポート：** （任意）US、CA、FRなど、2文字の国コードで国別に分類した広告費データ。地域ごとの成果と広告費の分析に推奨します。
* **チャネル別レポート：** （任意）YouTubeやショッピングなど、チャネル別に分類した広告費データ。チャネルごとの成果と広告費の分析に適しています。  
  <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRqyHRTiLq8KUtELHqdaF6yVTfNE22X5UmUqXX89oOK5ZpS6lksXD0401G8MFmsaEzg2Csvf-d3y08Z/pub?single=true&output=csv">サンプルファイルを確認</Anchor>
* **全広告費レポート**：アドネットワークから直接取得した、モバイルおよびモバイル以外の広告費データをまとめたレポートです。アトリビューションデータは含まれません。現在は、Google広告、Meta広告、TikTokに対応しています。  
  <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSdjA_4tdWBxxbI_ZM7mcZzCKhrWxQ-0m1DPIig-gMTpnDyLBDE_RGJ5zskNFpbsg/pub?gid=559626950&single=true&output=csv">サンプルファイルを確認</Anchor>

  <div id="note" />

  > 📘 **注意**
  >
  > 全広告費レポートでGoogle広告とMeta広告のデータを受信するには、AppsFlyerの担当者にお問い合わせください。


<div id="cost-etl-report-types-overview-table" />

### コストETLレポートの種類と概要

<table><thead><tr><th> </th><th>サマリー</th><th>国別</th><th>チャネル別</th><th><strong>全広告費レポート</strong></th></tr></thead><tbody><tr><td><strong>レポートの取得方法</strong></td><td>コストETLを有効にします。サマリーレポートはデフォルトで選択されています。</td><td>コストETLを有効にし、国別レポートを選択します。</td><td>コストETLを有効にし、チャネル別レポートを選択します。</td><td>コストETLを有効にし、<strong>国別</strong>レポートを選択します。（コストETLページに、全広告費レポート専用の選択項目はありません）</td></tr><tr><td><strong>レポートの保存先</strong></td><td>選択したクラウド接続サービスによって異なります。 Summaryフォルダー、または専用のテーブルに保存されます。</td><td>選択したクラウド接続サービスによって異なります。 Geoフォルダー、または専用のテーブルに保存されます。</td><td>選択したクラウド接続サービスによって異なります。 Channelフォルダー、または専用のテーブルに保存されます。</td><td>選択したクラウド接続サービスによって異なります。 All Costフォルダー、または専用のテーブルに保存されます。</td></tr><tr><td><strong>対象となる広告費の種類</strong></td><td><p>モバイルの広告費：制限なし。<br/>CTVとWebの広告費：次の条件を満たすものに限定されます。<br/> </p><ol><li>コンバージョンが1件以上あるキャンペーン</li><li>広告費の取得元がInCost API、コストインポート、CPIのいずれかであること</li></ol></td><td>サマリーと同じ。</td><td>サマリーと同じ。</td><td>Google広告、Meta広告、TikTokのモバイル、Web、CTV、PC、ゲーム機の広告費。</td></tr><tr><td><strong>対応するメディアソース</strong></td><td>制限なし</td><td>制限なし</td><td>制限なし</td><td><ul><li> <strong>TikTok：</strong>データが自動的に追加されます。</li><li> <strong>GoogleとMeta：</strong>有効化するには担当のCSMにお問い合わせください。</li></ul></td></tr><tr><td><strong>スキーマの詳細度</strong></td><td>コストETLの設定内容によって異なります。</td><td><p>コストETLの設定内容によって異なります。</p><p><br/>Metaでは、channelディメンションに値が入りません。</p></td><td><p>コストETLの設定内容によって異なります。</p><p><br/>Metaでは、geoディメンションに値が入りません。</p></td><td><p>コストETLの設定内容によって異なります。</p><p>Metaでは、channelディメンションは非対応です。<br/><strong>プラットフォーム：</strong>キャンペーンの配信先（モバイル、デスクトップ、タブレットなど）を表す、アドネットワークから取得する新しいディメンション。</p></td></tr><tr><td><strong>アトリビューションデータ</strong></td><td>対応</td><td>対応</td><td>対応</td><td><p>非対応。</p><p><br/>コストETLスキーマにアトリビューション指標を含めるよう設定している場合、その値は0と表示されます。</p></td></tr><tr><td><strong>アプリID</strong></td><td>アドネットワークがアプリID単位のデータに対応していない場合、アトリビューションデータからアプリIDを取得します。</td><td>サマリーと同じ。</td><td>サマリーと同じ。</td><td><p>アドネットワークから取得します。</p><p><br/>アプリIDが報告されていない場合、値はunknownになります。</p></td></tr><tr><td><strong>広告費の取得元</strong></td><td>API連携（広告費API＋InCost）、コストインポート、CPI</td><td>サマリーと同じ。</td><td>サマリーと同じ。</td><td>API連携のみ。</td></tr><tr><td><strong>CNC</strong></td><td>対応</td><td>対応</td><td>対応</td><td>非対応。</td></tr><tr><td><strong>代理店データ</strong></td><td>対応</td><td>対応</td><td>対応</td><td><ul><li> <strong>FacebookとMeta：</strong>非対応。</li><li> <strong>TikTok：</strong>AppsFlyerにアプリIDがあるキャンペーンのみ対応。</li></ul></td></tr><tr><td><strong>代理店手数料</strong></td><td>対応</td><td>対応</td><td>対応</td><td>非対応。値は常に0です。</td></tr><tr><td><strong>更新頻度</strong></td><td colspan="4">アドネットワークから1日6回データを収集します。<br/>レポートは、設定に応じて1日最大4回配信できます。</td></tr></tbody></table>

<div id="report-details" />

## レポートの詳細

<div id="data-freshness" />

<Accordion title="データの更新・反映">

キャンペーン広告費のデータは、以下の条件で書き込まれます。

* 広告費データの確認、転送、自社システムへの読み込みに使用できるよう、クラウドサービスまたはバケットに書き込まれます。
* コストETLの対象に選択したすべてのアプリについて、日付別・バージョン別に書き込まれます。
* 1日最大4回書き込まれます（データは<Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">1日に複数回更新</Anchor>）。
* 当日と過去6日分（この記事では「7日間」と表記）に加え、14日前・29日前・88日前のデータが対象です。データの読み込み処理を設計する際は、この点を考慮してください。
  * 例：2024年10月14日のファイルには、10月14日（当日）、10月13日（1日前）、10月12日（2日前）、10月11日（3日前）、10月10日（4日前）、10月9日（5日前）、10月8日（6日前）、9月30日（14日前）、9月15日（29日前）、7月18日（88日前）のデータが含まれます。
  * 過去のデータも対象に含めることで、広告費レポートの更新や修正を反映できます。
* アトリビューション、クリック、インプレッションのいずれかと一致する広告費が対象です。  
  **注意**：
  * 直近7日分のデータは、メディアソースから改めて取得します。 14日前・29日前・88日前のデータは、再処理されます。
  * 過去にさかのぼって更新されるのは広告費データのみで、アトリビューションデータは更新されません。

</Accordion>

<div id="directory-and-filename-structure" />

<Accordion title="ディレクトリとファイル名の構造">

クラウドサービスまたはバケットに書き込まれるデータのディレクトリ・ファイル構造は、以下のとおりです。

* コストETLがディレクトリへの書き込みを完了すると、*success*ファイルを作成し、完了を示します。このファイルのタイムスタンプが、常にそのディレクトリ内で最も新しいものになります。
* フォルダー・ファイルの数は、以下のとおりです。
  * サマリー：1日あたり最大4つのバージョンフォルダー。
    * 各バージョンフォルダーには、7日分のデータを含むParquetファイルが保存されます。
  * 国別・チャネル別レポート：各レポートにつき、1日あたり最大4つのバージョンフォルダー。
    * 各バージョンフォルダーには、1から始まる番号が付いたParquet形式のデータファイルが保存されます。
  * 全広告費：geoディメンションに基づき、1日あたり最大4ファイル。

<div id="data-locker-connection-directory-structure" />

#### Data Locker接続のディレクトリ構造

`<client-bucket>/<DL-generated-partition>/<connection-name>/t=<report-name>/dt=<YYYY-MM-DD>/v=<1/2/3/4>/<parquet file number>`

| **変数** | **内容** |
| --- | --- |
| client-bucket | クラウドサービスで設定したバケット名 |
| DL-generated-partition | 顧客ごとに一意となる、自動生成されたパーティション |
| connection-name | Data Lockerの設定時に指定した接続名 |
| t | 対象レポートの名前。次のいずれか：<ul><li>cost\_etl\_summary</li><li>cost\_etl\_geo</li><li>cost\_etl\_channel</li><li>cost\_etl\_all\_cost\_geo</li></ul> |
| dt | <ul><li>レポートの日付、つまりレポートが送信された日付。</li><li>YYYY-MM-DD</li></ul> |
| v | <ul><li>その日に配信されたレポートの順番を表すバージョン番号（1日最大4回）。</li><li>1～4の整数</li></ul> |
| Parquetファイル番号 | <ul><li>00000から始まる連番</li><li>例：`part-<number>`</li></ul> |

<div id="cost-etl-connection-directory-structure" />

#### コストETL接続のディレクトリ構造

`<advertiser bucket name>/cost_etl/version/dt=<yyyy-mm-dd>/b=<n>/<dimension>/<file name/<parquet file number>`

| **変数** | **内容** |
| --- | --- |
| advertiser\_bucket\_name | コストETLの設定で指定した形式：af-xpend-cost-etl-&lt;af-account-id>-[your bucket name suffix] |
| cost\_etl | 常にcost\_etl |
| version | コストETLのバージョン |
| date | 広告費の日付<br /><br />形式：yyyy-mm-dd |
| batch | 1～4の数値 |
| dimension | データのディメンション：<ul><li>geo</li><li>channel</li></ul> |
| file\_name | <ul><li>summary</li><li>all-cost</li></ul> |
| Parquetファイル番号 | <ul><li>00000から始まる連番</li><li>例：`part-<number>`</li></ul> |

**例：** 2020年6月23日の初回のデータ取得では、ディレクトリとファイル名は次の構造になります：`/bucket-name/cost_etl/v1/dt=2020-06-23/b=1/geo/part-00001`

</Accordion>

<div id="file-fields" />

<Accordion title="ファイルのフィールド">

<div id="fieldsdimensions" />

#### フィールド／ディメンション

| **フィールド** | **補足** | **常に値が入るか** | **形式** | **サマリーファイルに含まれるか** |
| --- | --- | --- | --- | --- |
| ad | 広告階層を構成する項目 | いいえ | 文字列 | - |
| ad\_account | <ul><li>広告費データの取得元の広告アカウント</li><li>oAuth（認証情報でログインする方法）で接続するアドネットワークが対象です。例：Google、Meta広告。</li></ul> | いいえ | 文字列 | - |
| ad\_id | 広告階層を構成する項目 | いいえ | 文字列 | - |
| adset | 広告階層を構成する項目 | いいえ | 文字列 | - |
| adset\_id | 広告階層を構成する項目 | いいえ | 文字列 | - |
| af\_bid\_strategy | AppsFlyerが対応関係に基づいて共通表記に統一した入札戦略。キャンペーン設定情報を構成する項目。<Anchor target="_blank" href="/marketers/ja/docs/campaign-properties-in-cost-etl-reports">詳細はこちら</Anchor> | いいえ | 文字列 | - |
| af\_cost\_model | AppsFlyerが対応関係に基づいて共通表記に統一した課金モデル。キャンペーン設定情報を構成する項目。<Anchor target="_blank" href="/marketers/ja/docs/campaign-properties-in-cost-etl-reports">詳細はこちら</Anchor> | いいえ | 文字列 | - |
| agency | 広告配信を担当する代理店 | いいえ | 文字列 | - |
| app\_id | AppsFlyer上のアプリID | はい | 文字列 | ✓ |
| bid\_amount | キャンペーン設定情報を構成する項目。<Anchor target="_blank" href="/marketers/ja/docs/campaign-properties-in-cost-etl-reports">詳細はこちら</Anchor> | いいえ | 整数 | - |
| bid\_strategy | キャンペーン設定情報を構成する項目。<Anchor target="_blank" href="/marketers/ja/docs/campaign-properties-in-cost-etl-reports">詳細はこちら</Anchor> | いいえ | 文字列 | - |
| campaign | 広告階層を構成する項目 | いいえ | 文字列 | - |
| campaign\_id | 広告階層を構成する項目 | いいえ | 文字列 | - |
| campaign\_objective | キャンペーン設定情報を構成する項目。<Anchor target="_blank" href="/marketers/ja/docs/campaign-properties-in-cost-etl-reports">詳細はこちら</Anchor> | いいえ | 文字列 | - |
| channel | 広告階層のディメンション | いいえ | 文字列 | - |
| cost\_model | キャンペーン設定情報を構成する項目。<Anchor target="_blank" href="/marketers/ja/docs/campaign-properties-in-cost-etl-reports">詳細はこちら</Anchor> | いいえ | 文字列 | - |
| currency | AppsFlyerでアプリに設定した、広告主の広告費の通貨 | はい | ISO-4217に準拠した3文字の文字列 | ✓ |
| date | メディアソースが報告した広告費の発生日 | はい | 文字列：yyyy-mm-dd | ✓ |
| geo | 広告階層のディメンション | いいえ | ISO 3166に準拠した2文字の文字列 | ✓ |
| keyword\_id | ASAのキーワードID | はい | 文字列 | - |
| keyword\_term | ユーザーがオンライン検索で使用した語句 | はい | 文字列 | - |
| media\_source | 広告を表示したメディアソース | はい | 文字列 | ✓ |
| original\_bid\_amount | キャンペーン設定情報を構成する項目。<Anchor target="_blank" href="/marketers/ja/docs/campaign-properties-in-cost-etl-reports">詳細はこちら</Anchor> | いいえ | 整数 | - |
| original\_currency | 通貨換算前の、アドネットワークが報告した広告費の通貨 | いいえ | ISO-4217に準拠した3文字の文字列 | - |
| os | 端末のOS。設定される値：<ul><li>android</li><li>windowsphone</li><li>ios</li></ul> | はい | 文字列 | - |
| platform | キャンペーンを配信するプラットフォーム（モバイル、タブレット、デスクトップ、CTV） | 全広告費レポートのみ | 文字列 | - |
| site\_id | パブリッシャーID | いいえ | 文字列 | - |
| timezone | <ul><li>AppsFlyerにデータが保存されているタイムゾーン</li><li>アドネットワークが、AppsFlyerで設定したものとは異なるタイムゾーンでデータを報告することがあります。このフィールドは、AppsFlyerとアドネットワークの広告費に差異が生じる理由を把握するのに役立ちます。</li></ul> | はい | 文字列 | - |

<div id="metrics" />

#### 指標

| **フィールド** | **補足** | **常に値が入るか** | **形式** | **サマリーファイルに含まれるか** |
| --- | --- | --- | --- | --- |
| ccvr | <ul><li>コンバージョン単価</li><li>計算式：広告費／（インストール数＋リアトリビューション数＋リエンゲージメント数）</li></ul> |  | 整数 | - |
| clicks | <ul><li>AppsFlyerによる計測値。</li><li>ユーザー獲得とリターゲティングの両方を含みます。</li><li>クリック総数から、<Anchor target="_blank" href="/marketers/ja/docs/about-enriched-engagement-types#engaged_click">Engaged click</Anchor>を差し引きます。</li></ul> |  | 整数 | ✓ |
| clicks\_discrepancy | <ul><li>アドネットワークとAppsFlyerの計測値の差</li><li>次の場合、この指標は参照しないでください。<ul><li>広告費とアトリビューションが一致していない場合。</li><li>アドネットワークが<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">クリック数の報告</Anchor>に対応していない場合。</li></ul></li></ul> |  | 整数 | - |
| cost | 広告費の金額（該当する場合は代理店手数料を含む） |  | 数値 | ✓ |
| cost\_without\_fees | 代理店手数料を除いた広告費。 AppsFlyerによる計測値 | はい | 整数 | - |
| cpi | <ul><li>AppsFlyerによる計測値</li><li>計算式：広告費／インストール数</li></ul> |  | 整数 | - |
| ctr | <ul><li>クリック率。 AppsFlyerによる計測値</li><li>計算式：クリック数／インプレッション数</li></ul> | いいえ | 整数 | - |
| cvr | <ul><li>コンバージョン率。 AppsFlyerによる計測値</li><li>計算式：インストール数／クリック数</li></ul> |  | 整数 | - |
| cvvr | <ul><li>動画の完全視聴率。 AppsFlyerによる計測値</li><li>計算式：動画の完全視聴数／インプレッション数</li></ul> |  | 整数 | - |
| ecpc | <ul><li>AppsFlyerによる計測値</li><li>計算式：広告費／クリック数</li></ul> |  | 整数 | - |
| ecpm | <ul><li>AppsFlyerによる計測値</li><li>計算式：（広告費／インプレッション数）×1000</li></ul> |  | 整数 | - |
| fees | 通常の広告費に加えて代理店が請求する手数料。 AppsFlyerによる計測値 | はい | 整数 | - |
| impressions | <ul><li>AppsFlyerによる計測値。</li><li>ユーザー獲得とリターゲティングの両方を含みます。</li><li>インプレッション総数から、<Anchor target="_blank" href="/marketers/ja/docs/about-enriched-engagement-types#engaged_view">Engaged view</Anchor>を差し引きます。</li></ul> | はい。<br /><br />対象の指標に値がない場合は、0が設定されます。 | 整数 | ✓ |
| impressions\_discrepancy | <ul><li>アドネットワークとAppsFlyerの計測値の差</li><li>次の場合、この指標は参照しないでください。<ul><li>広告費とアトリビューションが一致していない場合。</li><li>アドネットワークが<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">インプレッション数の報告</Anchor>に対応していない場合。</li></ul></li></ul> |  | 整数 | - |
| installs | AppsFlyerによる計測値 |  | 整数 | ✓ |
| installs\_discrepancy | <ul><li>アドネットワークとAppsFlyerの計測値の差</li><li>次の場合、この指標は参照しないでください。<ul><li>広告費とアトリビューションが一致していない場合。</li><li>アドネットワークが<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">コンバージョン数の報告</Anchor>に対応していない場合。</li></ul></li></ul> |  | 整数 | - |
| original\_cost | アドネットワークが報告した、通貨換算前の通貨による広告費（該当する場合は、AppsFlyerが計算した代理店手数料を加算） |  | 数値 | - |
| original\_cost\_without\_fees | アドネットワークが報告した、代理店手数料を含まない元の広告費 | はい | 整数 | - |
| re\_attributions | AppsFlyerによる計測値 |  | 整数 | ✓ |
| re\_engagements | AppsFlyerによる計測値 |  | 整数 | ✓ |
| reported\_clicks | メディアソースによる計測値 |  | 整数 | ✓ |
| reported\_conversions | メディアソースによる計測値 |  | 整数 |  |
| reported\_cvr | <ul><li>報告されたコンバージョン率</li><li>計算式：報告されたコンバージョン数／報告されたクリック数</li></ul> |  | 整数 | - |
| reported\_impressions | メディアソースによる計測値 |  | 整数 | ✓ |
| video\_25p\_views | 動画が25%まで再生された回数。アドネットワークの報告値 |  | 整数 | - |
| video\_50p\_views | 動画が50%まで再生された回数。アドネットワークの報告値 |  | 整数 | - |
| video\_75p\_views | 動画が75%まで再生された回数。アドネットワークの報告値 |  | 整数 | - |
| video\_completions | アドネットワークの報告値 |  | 整数 | - |

</Accordion>

<div id="procedures" />

## 手順

<div id="set-up-cost-etl" />

<Accordion title="コストETLの設定">

この設定は、管理者が行う必要があります。

**事前準備**：

コストETLの設定には、以下が必要です。

* AppsFlyerによるデータの書き込みを許可した、設定済みのクラウドサービス。以下のクラウドサービスのうち、1つ以上を設定する必要があります。
  * <Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>バケット
  * <Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor>バケット
  * ［ベータ版］<Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#beta--azure-storage">Azure</Anchor> Blob
  * ［ベータ版］<Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#yandex">Yandex</Anchor>バケット
  * <Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#bigquery">BigQuery</Anchor>データウェアハウス
  * <Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#snowflake">Snowflake</Anchor>ウェアハウス
* コストETLの設定を完了するための、AppsFlyerの管理者権限と管理画面へのアクセス権。

[**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)**](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) **コストETLを設定するには：**

1. AppsFlyerのサイドメニューから<strong>［エクスポート］</strong>＞<strong>［コストETL］</strong>に移動します。
2. <strong>［データ接続］</strong>を選択または設定します。
   * データ接続を設定済みの場合は、<strong>［接続］</strong>ドロップダウンから、コストETLで使用する接続を選択します。  
     <Image align="center" alt="" src="https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png" width="700px" />
   * まだデータ接続がない場合は、<strong>［＋Data Lockerで新しい接続を作成］</strong>をクリックし、以下の手順で接続を作成します。  
     <Image align="center" alt="" src="https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png" width="700px" />
     1. 接続に名前を付けます。  
        <Image align="center" alt="" src="https://files.readme.io/734060321cf14a4ebbce66fe2abc71ff299218f7c52cb64dc5b8e71c42d3632d-31233921530001.png" width="2100px" />
     2. **配信先となるクラウドサービスを選択します**。次のいずれかの操作を行います。
        * <strong>［S3］</strong>を選択します。  
          <Image align="center" alt="" src="https://files.readme.io/1a78090f00407d44a5b74f3cb3b94e3a28064bc9b991b1cecf506fa0b9053842-31233961351441.png" width="945px" />
          1. AWS S3のバケット名を入力します。先頭の`af-`は必須です。手動で入力してください。
          2. <strong>［接続をテスト］</strong>をクリックします。
          3. バケットのパスが無効であるというエラーメッセージが表示されないことを確認します。
          4. <strong>［この接続をAdobe Experience Platformに対応させる］</strong>かどうかを選択します。
          5. <strong>［保存］</strong>をクリックします。
          6. コストETLの設定画面で、<strong>［接続］</strong>ドロップダウンから、作成したクラウドサービスの接続を選択します。
        * <strong>［GCS］</strong>を選択します。  
          <Image align="center" alt="" src="https://files.readme.io/6da526f43131887270136e9fcfa9434ad88c2ce8cebdb896c07dac4a0652d683-31233921536913.png" width="944px" />
          1. **GCSバケット名**を入力します。
          2. <strong>［接続をテスト］</strong>をクリックします。
          3. バケットのパスが無効であるというエラーメッセージが表示されないことを確認します。
          4. <strong>［この接続をAdobe Experience Platformに対応させる］</strong>かどうかを選択します。
          5. <strong>［保存］</strong>をクリックします。
          6. コストETLの設定画面で、<strong>［接続］</strong>ドロップダウンから、作成したクラウドサービスの接続を選択します。
        * ［ベータ版］<strong>［Azure］</strong>を選択します。  
          <Image align="center" alt="" src="https://files.readme.io/cd718eeebc5965d24a2d38457d4fa22c5691d6a186464187bea12199fb96671b-31233921550481.png" width="943px" />
          1. **接続名**、**ストレージアカウント名**、**キー**を入力します。
          2. バケットのパスが無効であるというエラーメッセージが表示されないことを確認します。
          3. <strong>［この接続をAdobe Experience Platformに対応させる］</strong>かどうかを選択します。
          4. <strong>［保存］</strong>をクリックします。
          5. コストETLの設定画面で、<strong>［接続］</strong>ドロップダウンから、作成したクラウドサービスの接続を選択します。
        * ［ベータ版］<strong>［Yandex］</strong>を選択します。  
          <Image align="center" alt="" src="https://files.readme.io/230e0d9c0b56b4c9f85da8c97f1ab91818c16ecfbabbf81ecb35f12d41716888-31233961360273.png" width="944px" />
          1. **バケット名**、**アクセスキー**、**シークレットキー**を入力します。
          2. バケットのパスが無効であるというエラーメッセージが表示されないことを確認します。
          3. <strong>［この接続をAdobe Experience Platformに対応させる］</strong>かどうかを選択します。
          4. <strong>［保存］</strong>をクリックします。
          5. コストETLの設定画面で、<strong>［接続］</strong>ドロップダウンから、作成したクラウドサービスの接続を選択します。
        * <strong>［BigQuery］</strong>を選択します。  
          <Image align="center" alt="" src="https://files.readme.io/6989fa8c869c08440da757b3ebb385754a4f23dbe4e2d38c50837448c08ab03b-31233921555857.png" width="945px" />
          1. BigQueryのプロジェクトIDとデータセット名を入力します。
          2. <strong>［接続をテスト］</strong>をクリックします。
          3. バケットのパスが無効であるというエラーメッセージが表示されないことを確認します。
          4. <strong>［保存］</strong>をクリックします。
          5. コストETLの設定画面で、<strong>［接続］</strong>ドロップダウンから、作成したクラウドサービスの接続を選択します。
        * <strong>［Snowflake］</strong>を選択します。  
          <Image align="center" alt="" src="https://files.readme.io/b0e5f5ece797f46006d6e29a6afd01bc120b035590bd2ee87a54daa8c36bb0ed-31233961363985.png" width="944px" />
          1. SnowflakeのリージョンとアカウントIDを入力します。
          2. <strong>［接続をテスト］</strong>をクリックします。
          3. バケットのパスが無効であるというエラーメッセージが表示されないことを確認します。
          4. <strong>［保存］</strong>をクリックします。
          5. コストETLの設定画面で、<strong>［接続］</strong>ドロップダウンから、作成したクラウドサービスの接続を選択します。
3. <strong>［次へ］</strong>をクリックします。  
   <Image align="center" alt="" src="https://files.readme.io/4237ca8e7e70e0c04e924b61839d47d88e42075b4c257fcdf5e78870712d3582-31233921563153.png" width="746px" />
4. <strong>［レポート配信スケジュール（UTC）］</strong>を設定します。  
   <Image align="center" alt="" src="https://files.readme.io/427b18043c0ab53ea559d53094efb6f04ad7505659c08ba7345b3a647f78d64d-31233961369105.png" width="607px" />
   1. 1日に受信するレポート数（1～4回）を選択します。
   2. レポートを受信する時刻を選択します。[詳細はこちら](/docs/set-up-and-use-roi360-cost-etl-reports#report-schedule)
   3. <strong>［次へ］</strong>をクリックします。
5. レポートの詳細を設定します。
   1. レポートに含めるアプリを1つ以上選択します。今後追加するアプリも自動的に含めるには、<strong>［今後追加するすべてのアプリを含める］</strong>を選択します。  
      <Image align="center" alt="" src="https://files.readme.io/a5d453f40a7c5318f6a4c6cdfc5cf4d645c540c4b684362a796cda41d3c058c6-31233961373585.png" width="566px" />
   2. 分析の目的に合ったレポートを選択します。各レポートの説明は、[レポートの種類](#report-types)を参照してください。
      * **サマリーレポート**はデフォルトで選択されています。
      * 全広告費レポートを受信するには、**国別レポート**を選択する必要があります。  
        <Image align="center" alt="" src="https://files.readme.io/3662c55c71f3390ac651c9269eac519f846b53ad675dab224b62fb09f81d4578-31233921571345.png" width="1921px" />
   3. レポートに含めるディメンションを選択します。**注意**：国別レポートを選択した場合、geoディメンションはデフォルトで含まれます。チャネル別レポートを選択した場合、channelディメンションはデフォルトで含まれます。   
      <Image align="center" alt="" src="https://files.readme.io/dbbea34c466b2263638a0937392ab004eab471a9e44d4c3713d6487507cef14b-4476081988241.png" width="1921px" />
   4. レポートに含める指標を選択します。  
      <Image align="center" alt="" src="https://files.readme.io/2b865bb9cdb355287d99e81278fed5fd374da80a9f93499bd7b75777c8d5d11e-360019263038.jpg" width="1863px" />
6. <strong>［適用］</strong>をクリックします。

</Accordion>

<div id="edit-or-change-connection" />

<Accordion title="接続の編集・変更">

接続を編集・変更して、データの配信先を変更したり追加したりできます。

**注意**：既存の接続に切り替えると、以前のコストETL接続には戻せません。

<div id="edit-connection" />

#### 接続の編集

**接続の詳細を編集するには**：

1. AppsFlyerのサイドメニューから<strong>［エクスポート］</strong>＞<strong>［コストETL］</strong>に移動します。
2. <strong>［データ接続］</strong>セクションで、次のいずれかの操作を行います。
   * Data Locker接続の場合、<strong>［接続］</strong>ドロップダウンで、編集する接続にカーソルを合わせます。接続の詳細が表示されます。 <strong>［Data Lockerで編集］</strong>をクリックします。  
     <Image align="center" alt="" src="https://files.readme.io/95c76d3bfc4a4db4bb9b4e67e4460680e0039e91dd930903515771e52c00ac7a-31233961377937.png" width="695px" />
   * コストETL接続の場合、<strong>［接続の詳細］</strong>ドロップダウンをクリックします。接続の詳細が表示されます。  
     <Image align="center" alt="" src="https://files.readme.io/67a1fb2ce45a49fc75d12eba4d1c3e67875b83883b0fc05307c080c6050be0f2-31233961380369.png" width="651px" />
3. 画面の案内に従い、接続の詳細を編集します。
4. 表示される案内に従って、<strong>［変更を保存］</strong>または<strong>［適用］</strong>をクリックします。

<div id="change-data-locker-connection" />

#### Data Locker接続の変更

**別のData Locker接続に切り替えるには**：

1. AppsFlyerのサイドメニューから<strong>［エクスポート］</strong>＞<strong>［コストETL］</strong>に移動します。
2. <strong>［データ接続］</strong>セクションで、次のいずれかの操作を行います。
   * 使用するData Locker接続が設定済みの場合は、<strong>［接続］</strong>ドロップダウンから、コストETLで使用する接続を選択します。  
     <Image align="center" alt="" src="https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png" width="700px" />
   * まだ設定していない場合は、<strong>［＋Data Lockerで新しい接続を作成］</strong>をクリックし、接続を作成します。その後、コストETLの設定画面に戻り、<strong>［接続］</strong>ドロップダウンから選択します。  
     <Image align="center" alt="" src="https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png" width="700px" />
3. <strong>［変更を保存］</strong>をクリックします。

<div id="change-from-cost-etl-to-data-locker-connection" />

#### コストETL接続からData Locker接続への変更

**事前の確認事項**：

* Data Locker接続に切り替えると、以前のコストETL接続には戻せません。
* Data Locker接続に切り替えると、フォルダーのパス構造が以下の形式に変わります。レポートのデータには影響しません。

  `<client-bucket>/<DL-generated-partition>/<connection-name>/t=<report-name>/dt=<YYYY-MM-DD>/v=<1/2/3/4>/`

**非推奨のコストETL接続からData Locker接続に切り替えるには**：

1. AppsFlyerのサイドメニューから<strong>［エクスポート］</strong>＞<strong>［コストETL］</strong>に移動します。
2. <strong>［データ接続］</strong>セクションで、<strong>［Data Locker接続］</strong>をクリックします。  
   <Image align="center" alt="" src="https://files.readme.io/2608d88368579c9fd3aa7648905484a56a7f0d989a96582cee51303409ce427c-31233961382289.png" width="631px" />
3. 次のいずれかの方法で、Data Locker接続を設定します。
   * 使用するデータ接続が設定済みの場合は、<strong>［接続］</strong>ドロップダウンから、コストETLで使用する接続を選択します。  
     <Image align="center" alt="" src="https://files.readme.io/da486f6399e92c49923527da3348f4535691768cebd7a776ec84f7a2a739c204-31233961385617.png" width="501px" />
   * まだ設定していない場合は、<strong>［＋Data Lockerで新しい接続を作成］</strong>をクリックし、接続を作成します。その後、コストETLの設定画面に戻り、<strong>［接続］</strong>ドロップダウンから選択します。  
     <Image align="center" alt="" src="https://files.readme.io/0d48f83f30954f5f68efecf7e6c4cf2b39b295e0b893711bd2e2756406c42461-31233921587985.png" width="631px" />
4. <strong>［変更を保存］</strong>をクリックします。

</Accordion>

<div id="aws-object-ownership" />

<Accordion title="AWSのオブジェクト所有権の変更">

AWSでは、AppsFlyerがバケットに書き込んだオブジェクトの所有者は、デフォルトでAppsFlyerになります。データの読み込み処理によっては、所有者をバケット所有者であるお客様に変更する必要があります。

**バケット内のオブジェクトの所有権を変更するには**：

1. AWS Management Consoleにログインし、<Anchor target="_blank" href="https://console.aws.amazon.com/s3/">https://console.aws.amazon.com/s3/</Anchor>からAmazon S3コンソールを開きます。
2. <strong>［バケット］</strong>一覧で、S3 Object Ownershipを有効にするバケットの名前を選択します。
3. <strong>［アクセス許可］</strong>タブを開きます。
4. <strong>［オブジェクト所有者］</strong>で、<strong>［編集］</strong>をクリックします。
5. <strong>［希望するバケット所有者］</strong>を選択します。
6. <strong>［保存］</strong>をクリックします。

</Accordion>

<div id="best-practices" />

## 推奨事項

<div id="report-schedule" />

<Accordion title="レポート配信スケジュール">

配信スケジュールを設定すると、必要なタイミングで最新のデータを取得できます。

レポート配信スケジュールを決める際は、以下を考慮してください。

* BIシステムでのデータ処理を開始する時刻に、できるだけ近い受信時刻を選択します。
* 他の媒体より前日分のデータの提供が遅いアドネットワークがある場合は、そのデータが利用可能になる時刻にレポートの配信を追加します。

</Accordion>

<div id="override-data" />

<Accordion title="既存データの上書き">

データを取得・分析する際は、特定の日付とバッチのデータを取得するか、現在のバッチに含まれる日付の既存データをすべて上書きすることを推奨します。そうしないと、同じデータが重複して表示される場合があります。

例えば、2月20日のバッチ1には、2月14日～20日のデータが含まれます。一方、2月19日に書き込まれたバッチにも、2月14日～19日のデータが含まれています。 2月19日に受信した過去の日付のデータを、2月20日の最新バッチで受信したデータで上書きしてください。

</Accordion>

<div id="geo-versus-channel" />

<Accordion title="国別データとチャネル別データ">

すべてのディメンションを組み合わせたデータを提供しているとは限らず、対応状況はアドネットワークによって異なります。代表的な例が、Meta広告の地域データとチャネルデータです。このため、2つのデータセットを個別に提供しています。国別データセットには必ず地域データが含まれ、チャネル別データセットには必ずチャネルデータが含まれます。

多くのメディアソースでは、国別とチャネル別のデータセットの内容は同じになります。そのため、目的に適した方のデータセット（国別またはチャネル別）を使用してください。

メディアソースとの連携契約にチャネルが含まれず、channelが空欄の場合も、チャネルを含むデータとして扱います。

</Accordion>

<div id="aggregate-data" />

<Accordion title="データの集計">

コストETLは、アドネットワークから取得できる最も詳細な単位まで、柔軟にデータを提供します。大量になる可能性があるデータから施策に役立つ知見を得るため、ビジネスの目的に合った単位で集計することを推奨します。例えば、キャンペーン別・国別に広告費を把握したい場合は、そのディメンションで集計します。

</Accordion>

<div id="standardization-across-networks" />

<Accordion title="アドネットワーク間でのデータの統一">

取得できるデータの詳細度は、アドネットワークによって異なります。例えば、Meta広告はサイトID別の広告費を提供せず、X広告は地域別の広告費を提供しません。コストETLデータを集計する際は、こうした違いを考慮し、アドネットワーク間で比較するデータの条件を揃えてください。

</Accordion>

<div id="compare-data" />

<Accordion title="データの比較">

コストETLでは、すべての広告費データを確認できます。コストETLに含まれるキャンペーンでも、一部のAppsFlyerダッシュボードには表示されないことがあります。例えば、インストールが記録されていない非アクティブなキャンペーンなどです。比較するには、Overview dashboardで特定のキャンペーンIDを探し、その広告費をコストETLのデータと比較してください。<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports">広告費データの利用条件について詳しくはこちら</Anchor>

</Accordion>

<div id="combine-geo-report-and-all-cost-report" />

<Accordion title="国別レポートと全広告費レポートの結合">

Google、Meta、TikTok（モバイルとモバイル以外）およびその他のメディアソース（モバイルのみ）の、アトリビューションに紐づく広告費データを漏れなく取得するには、以下のクエリを使用します。

```sql
with etl as (
    select *
    from etl
    where media_source = 'Facebook Ads'
      and date = '2025-07-16'
),

allcost as (
    select *
    from allcost
    where media_source = 'Facebook Ads'
      and date = '2025-07-16'
),

main as (
    select
        case when etl.date is null then 'all cost' else 'cost etl' end as report,
        coalesce(etl.date, allcost.date) as date,
        coalesce(etl.app_id, allcost.app_id) as app_id,
        etl.os,
        allcost.platform,
        coalesce(etl.media_source, allcost.media_source) as media_source,
        coalesce(etl.agency, allcost.agency) as agency,
        coalesce(etl.campaign_id, allcost.campaign_id) as campaign_id,
        coalesce(etl.campaign, allcost.campaign) as campaign,
        coalesce(etl.adset_id, allcost.adset_id) as adset_id,
        coalesce(etl.adset, allcost.adset) as adset,
        coalesce(etl.ad_id, allcost.ad_id) as ad_id,
        coalesce(etl.ad, allcost.ad) as ad,
        coalesce(etl.geo, allcost.geo) as geo,
        coalesce(etl.channel, allcost.channel) as channel,
        coalesce(etl.site_id, allcost.site_id) as site_id,
        coalesce(etl.ad_account, allcost.ad_account) as ad_account,
        coalesce(etl.keyword_id, allcost.keyword_id) as keyword_id,
        coalesce(etl.keywords, allcost.keywords) as keywords,
        coalesce(etl.campaign_objective, allcost.campaign_objective) as campaign_objective,
        coalesce(etl.af_cost_model, allcost.af_cost_model) as af_cost_model,
        coalesce(etl.bid_strategy, allcost.bid_strategy) as bid_strategy,
        coalesce(etl.af_bid_strategy, allcost.af_bid_strategy) as af_bid_strategy,
        coalesce(etl.currency, allcost.currency) as currency,
        coalesce(etl.cost, allcost.cost) as cost,
        coalesce(etl.impressions, allcost.impressions) as impressions,
        coalesce(etl.clicks, allcost.clicks) as clicks,
        coalesce(etl.installs, allcost.installs) as installs,
        coalesce(etl.re_attributions, allcost.re_attributions) as re_attributions,
        coalesce(etl.re_engagements, allcost.re_engagements) as re_engagements,
        coalesce(etl.original_cost, allcost.original_cost) as original_cost,
        coalesce(etl.reported_impressions, allcost.reported_impressions) as reported_impressions,
        coalesce(etl.reported_clicks, allcost.reported_clicks) as reported_clicks,
        coalesce(etl.reported_conversions, allcost.reported_conversions) as reported_conversions,
        coalesce(etl.ctr, allcost.ctr) as ctr,
        coalesce(etl.cvr, allcost.cvr) as cvr,
        coalesce(etl.ecpm, allcost.ecpm) as ecpm,
        coalesce(etl.cpi, allcost.cpi) as cpi,
        coalesce(etl.ccvr, allcost.ccvr) as ccvr,
        coalesce(etl.cvvr, allcost.cvvr) as cvvr,
        coalesce(etl.reported_cvr, allcost.reported_cvr) as reported_cvr,
        coalesce(etl.install_diff, allcost.install_diff) as install_diff,
        coalesce(etl.click_diff, allcost.click_diff) as click_diff,
        coalesce(etl.impression_diff, allcost.impression_diff) as impression_diff,
        coalesce(etl.ecpc, allcost.ecpc) as ecpc,
        coalesce(etl.video_25p_views, allcost.video_25p_views) as video_25p_views,
        coalesce(etl.video_50p_views, allcost.video_50p_views) as video_50p_views,
        coalesce(etl.video_75p_views, allcost.video_75p_views) as video_75p_views,
        coalesce(etl.video_completions, allcost.video_completions) as video_completions
    from etl
    full join allcost
        on etl.date = allcost.date
        and etl.app_id = allcost.app_id
        and etl.media_source = allcost.media_source
        and etl.campaign_id = allcost.campaign_id
        and etl.adset_id = allcost.adset_id
        and etl.ad_id = allcost.ad_id
        and etl.channel = allcost.channel
        and etl.geo = allcost.geo
        and etl.agency = allcost.agency
        and etl.site_id = allcost.site_id
        and etl.keyword_id = allcost.keyword_id
),

dedup as (
    select *,
           row_number() over (
               partition by date, media_source, agency, campaign_id, adset_id, ad_id, geo, channel, site_id, keyword_id
               order by report desc, cost desc
           ) as rank_for_dedup
    from main
)

select *
from dedup
where rank_for_dedup = 1;
```

</Accordion>

<div id="combine-cost-etl-and-cohort-reports" />

<Accordion title="コストETLレポートとコホートレポートの結合">

BIシステム上で、コストETLレポートと詳細集計コホートレポート（またはData Locker経由の通常のコホートレポート）を結合することをご検討ください。クリック、インプレッション、広告費、収益、アプリ内イベントなどの最新かつ正確なデータを組み合わせることで、マーケティング成果の全体像を把握できます。結合したデータで、ROASやCPAなどを算出できます。<Anchor target="_blank" href="/marketers/ja/docs/combine-cost-etl-and-cohort-reports-via-data-locker">詳細はこちら</Anchor>

</Accordion>

<div id="additional-information" />

## 補足情報

<div id="traits-and-limitations" />

<Accordion title="仕様と制限事項">

| 項目 | 補足 |
| --- | --- |
| タイムゾーン | タイムゾーンを変更すると、変更当日と翌日に広告費データが重複します。<Anchor target="_blank" href="/marketers/ja/docs/changing-app-time-zone-settings">詳細はこちら</Anchor> |
| データの更新・反映 | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">1日に複数回更新</Anchor>。コストETLの設定時に、レポートを受信する時刻をスケジュールで指定します。</li><li>データは通常、指定した時刻の1時間前から、その時刻までの間に届きます。例えば、午前6時までに届くよう設定した場合、午前5時～6時に届きます。</li></ul>**注意**：広告費データがバケットに届いた後、BIシステムへの転送にかかる時間は、レポートやParquetファイルのサイズによって大きく異なります。ファイルサイズは数KBから数GB以上までさまざまです。 |
| 全広告費レポート | <ul><li>Google Performance Maxキャンペーンの広告費データは含まれません。</li><li>キャンペーン名の変更には対応していません。</li></ul> |
| SKANキャンペーンの広告費データ | <ul><li>コストETLでSKANキャンペーンの広告費を取得するには、そのキャンペーンに従来方式のコンバージョンが1件以上ある必要があります。</li><li>SKANコンバージョンのみのキャンペーンでは、次のいずれかの条件を満たす場合にのみ広告費データを取得できます。<ul><li>対象のアドネットワークがTwitter（X）またはMetaである場合。</li><li>対象のアドネットワークの連携が、非アクティブキャンペーンに対応すると指定されている場合（<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">この一覧</Anchor>のM列が「Yes」）。</li></ul></li></ul> |
| CTV・PCアプリへの対応 | コストETLレポートは、PCアプリとCTVアプリに対応していません。 |
| Google Web・Meta Webの広告費データの利用条件 | 全広告費レポートに<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-create-web-based-campaigns#appsflyerでのgoogle-ads連携の設定">Google Web（`pid=googleads_int`</Anchor>）と<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-create-web-based-campaigns#how-to-create-a-meta-ads-campaign">Meta Web（`pid=metaweb_int`）</Anchor>の広告費データを含めるには、有効な連携にある<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">Google広告（`pid=googleadwords_int`）</Anchor>と<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Meta広告（`pid=facebook_int`）</Anchor>の広告費タブで、広告費の接続を作成する必要があります。これらの接続がない場合、GoogleとMetaのWeb広告費データはレポートに表示されません。 |

</Accordion>

<div data-zendesk-anchors="four-types-of-cost-etl-reports=4%E7%A8%AE%E9%A1%9E%E3%81%AE%E3%82%B3%E3%82%B9%E3%83%88etl%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01K4WKGHP4S2B23R0Z57NFESPE=4%E7%A8%AE%E9%A1%9E%E3%81%AE%E3%82%B3%E3%82%B9%E3%83%88etl%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01JZJVXY0BA25QM9PK4YRT8DZ6=%E6%B3%A8%E6%84%8F cost-etl-report-comparison-table=%E3%82%B3%E3%82%B9%E3%83%88etl%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E7%A8%AE%E9%A1%9E%E3%81%A8%E6%A6%82%E8%A6%81 h_01K4WN2VMPZYA6273EDW7CSJZ9=%E3%82%B3%E3%82%B9%E3%83%88etl%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E7%A8%AE%E9%A1%9E%E3%81%A8%E6%A6%82%E8%A6%81 report-details=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E8%A9%B3%E7%B4%B0 h_01JYXKJFYG6FKM8S6C8GYHPK6T=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E8%A9%B3%E7%B4%B0 h_01JYXKJFYGE8SHR071RNXW5V97=data-freshness h_01HA29GW8PWN30BCQCK29V0FTA=directory-and-filename-structure data-locker-connection-directory-structure=data-locker%E6%8E%A5%E7%B6%9A%E3%81%AE%E3%83%87%E3%82%A3%E3%83%AC%E3%82%AF%E3%83%88%E3%83%AA%E6%A7%8B%E9%80%A0 h_01JD4P98XF9S47EDHP38VXW1XS=data-locker%E6%8E%A5%E7%B6%9A%E3%81%AE%E3%83%87%E3%82%A3%E3%83%AC%E3%82%AF%E3%83%88%E3%83%AA%E6%A7%8B%E9%80%A0 cost-etl-connection-directory-structure=%E3%82%B3%E3%82%B9%E3%83%88etl%E6%8E%A5%E7%B6%9A%E3%81%AE%E3%83%87%E3%82%A3%E3%83%AC%E3%82%AF%E3%83%88%E3%83%AA%E6%A7%8B%E9%80%A0 h_01JKWMF6V57C35F1A0BVH18CY1=%E3%82%B3%E3%82%B9%E3%83%88etl%E6%8E%A5%E7%B6%9A%E3%81%AE%E3%83%87%E3%82%A3%E3%83%AC%E3%82%AF%E3%83%88%E3%83%AA%E6%A7%8B%E9%80%A0 h_01HA29GW8P0B1JJTGYDW863D7Z=file-fields fieldsdimensions=%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%83%87%E3%82%A3%E3%83%A1%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3 h_01HA29GW8PQATB4K5VJP1HD4NW=%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%83%87%E3%82%A3%E3%83%A1%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3 metrics=%E6%8C%87%E6%A8%99 h_01HA29GW8PZTS7XDWGYWXFZPYG=%E6%8C%87%E6%A8%99 procedures=%E6%89%8B%E9%A0%86 01JCZDRERADNNX04RT752793PG=%E6%89%8B%E9%A0%86 01JCZP8A5W67W66N886KHNRR4A=set-up-cost-etl 01JCZME67YK848NM0RJTM1J5ZG=edit-or-change-connection edit-connection=%E6%8E%A5%E7%B6%9A%E3%81%AE%E7%B7%A8%E9%9B%86 h_01JCZMGC8J41Y7H4JGZDVWYDJS=%E6%8E%A5%E7%B6%9A%E3%81%AE%E7%B7%A8%E9%9B%86 change-data-locker-connections=data-locker%E6%8E%A5%E7%B6%9A%E3%81%AE%E5%A4%89%E6%9B%B4 h_01JCZNQF3QE7P8PBQPKXZK1SA2=data-locker%E6%8E%A5%E7%B6%9A%E3%81%AE%E5%A4%89%E6%9B%B4 change-from-cost-etl-to-data-locker-connection=%E3%82%B3%E3%82%B9%E3%83%88etl%E6%8E%A5%E7%B6%9A%E3%81%8B%E3%82%89data-locker%E6%8E%A5%E7%B6%9A%E3%81%B8%E3%81%AE%E5%A4%89%E6%9B%B4 h_01JKWMF6V70W9FA90SSKJ77R2Z=%E3%82%B3%E3%82%B9%E3%83%88etl%E6%8E%A5%E7%B6%9A%E3%81%8B%E3%82%89data-locker%E6%8E%A5%E7%B6%9A%E3%81%B8%E3%81%AE%E5%A4%89%E6%9B%B4 h_01HA29GW8Q6D630E8SDVSFYVG7=aws-object-ownership best-practices=%E6%8E%A8%E5%A5%A8%E4%BA%8B%E9%A0%85 h_01HA29GW8QKPQXE4GHECAC5R5X=%E6%8E%A8%E5%A5%A8%E4%BA%8B%E9%A0%85 h_01J0NRD227RQR50CMNW60SF7SK=report-schedule h_01HA29GW8QHX8AMK4T7E85H7RS=override-data h_01HA29GW8QT5FNNYSWHCT99D68=geo-versus-channel h_01HA29GW8QA3FP46EMZVYDEZF3=aggregate-data h_01HA29GW8QPW0NXEMF1WGJMKSF=standardization-across-networks h_01HA29GW8Q3FNS0W7SKTG7S9R1=compare-data h_01K4WNM1ZFSMFZEV3V2HQ5PYQE=combine-geo-report-and-all-cost-report h_01J582E5JNR5DJ9T8HKDG2XSRR=combine-cost-etl-and-cohort-reports additional-information=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 h_01HA286GA6WPYVNN7KCXK7DGFM=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 h_01HA282W8WHHNDG75XZNSV2QQF=traits-and-limitations" />
