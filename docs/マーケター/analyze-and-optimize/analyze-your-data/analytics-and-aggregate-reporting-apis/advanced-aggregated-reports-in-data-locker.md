---
title: Data Lockerアドバンス集計レポート
metadata:
  keywords:
    - Premium
    - Premium Feature
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2024-03-06T10:46:12Z'
  edited_at: '2026-10-14T09:25:37Z'
  id: 23127074968721
  locale: ja
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ja/articles/23127074968721
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** Data Lockerのアドバンス集計レポートには、最適なデータの鮮度、正確性、細分性、および無制限の量の集計データが含まれます。

## Data Lockerアドバンス集計レポート

Data Lockerアドバンス集計レポートとは：

* 集計データに基づいて社内BIシステムを構築するための効率的でプライバシーを保護する方法を提供します。アトリビューション、イベント、収益データ、および考えられるすべてのディメンションと指標が含まれます。
* データをBIシステムに読み込み、キャンペーンのパフォーマンスや最適化のプロセスの一部として利用することができます。
* 最高のデータ鮮度を正確に保ちましょう：データは<Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">1日に複数回</Anchor>格納され、その日に利用可能なすべてのデータを含むレポートの後続バージョンごとに更新されます。
* <Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">メディアソースのデータ共有ポリシー</Anchor>やプライバシー保護ポリシーによって制限されたり制限されたりする可能性のある未加工データを補うのに役立ちます。制限はキャンペーンや広告セットなどのアトリビューション関連のフィールドに影響します。

## 設定方法

アドバンス集計レポートを取得するには、次のいずれかの手順を実行します。

| 既にData Lockerでデータを取得していますか？ | 手順 |
| --- | --- |
| はい | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) レポートをData Lockerに追加：<ol><li>AppsFlyer管理画面 左メニュー **エクスポート > Data Locker**へ移動します。</li><li>取得したいレポートをすべて選択します。</li><li>**設定を保存**をクリックします。<br />レポートは翌日から格納されます。</li></ol> |
| いいえ | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) **Data Lockerの設定**：<ol><li>Data Lockerの初回設定を完了してください。( <Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers#set-up-data-locker">広告主向け</Anchor> \| <Anchor target="_blank" href="/partners/ja/docs/data-locker-for-partners">パートナー向け</Anchor> )</li><li>レポートをData Lockerに追加します：<ol><li>AppsFlyer管理画面 左メニュー **エクスポート > Data Locker**へ移動します。</li><li>取得したいレポートをすべて選択します。</li><li>**設定を保存**をクリックします。<br />レポートは翌日から格納されます。</li></ol></li></ol> |

## 利用できるレポート

<div id="cohort-versioned-report" />

<Accordion title="アドバンス集計レポート（バージョン管理コホート）">

### レポートの仕様

| 概要 | コホートバージョン対応レポートには、すべての集計データがコホートされ、すべてのキャンペーンディメンションが細かく表示されます。レポートは、データの鮮度と正確性を最大化するために数時間ごとに更新されます。<br /><br /><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vT8NQKO287TxXpdTYpIASL55t4muIt9G3lnkEE436FQhNn5_14DfYgf0ztbm1VVZXI4ecPaGktdixS7/pub?output=xlsx">サンプルレポートをダウンロード</Anchor> |
| --- | --- |
| 利用できるレポート | 以下のレポートをダウンロードできます。各レポートの詳細については、コホートダッシュボードを確認してください。<ul><li>**ユーザー獲得：** リエンゲージメント期間中のLTVを含む、ユーザー獲得メディアソースにアトリビューションします。</li><li>**リターゲティング：** 発生したイベントのリターゲティングメディアソースにアトリビューションします：<ul><li>リエンゲージメント計測後、リエンゲージメント期間中に発生したアプリ内イベント</li><li>リアトリビューション後に発生したアプリ内イベント</li></ul></li><li>**統合：** AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/resolve-retargeting-double-attribution">二重アトリビューション</Anchor>ルールに基づき、ユーザーを導いた最後のタッチメディアソースの下にデータを表示します。つまり、リエンゲージメント期間中に発生したLTVは、ユーザー獲得メディアソースではなく、リターゲティングメディアソースに紐づきます。</li></ul> |
| レポート期間 | 過去 1,095日間にコンバージョンしたユーザーつまり、レポートには毎日、過去 1,095日間にコンバージョンしたユーザーのイベントが含まれます。 |
| レポート構成 | レポートのスキーマ（含まれているディメンションと指標）は固定されており、編集できません。 |
| データ更新頻度 | <ul><li>Intraday：レポートは数時間ごとに送信されます。</li><li>レポートはその日のデータです。つまり、4月18日のすべてのレポートバージョンには、4月18日の最新データがすべて含まれています。[詳細はこちら](/docs/advanced-aggregated-reports-in-data-locker#レポートのバージョンとデータの鮮度)</li></ul> |
| タイムゾーン | UTC |
| ディレクトリとファイル名の構造 | [詳細はこちら](/docs/advanced-aggregated-reports-in-data-locker#レポート構成) |
| パートナーのデータ保持ポリシーの影響 | 一部の広告媒体は、データ保存期間ポリシーを設けていることを考慮してください。この場合、データ保存期間の終了後に発生したイベントは、コホートレポートでは無視されます。<br /><br />例：SRN媒体 "A" は180日間のデータ保存期間ポリシーを設けているとします。インストール後180日目までのユーザーイベントは SRN「A」に紐づきます。180日後に発生したイベントはオーガニックへ紐づきます。 |

### レポート構成

レポートは、ディメンションとメトリックで構成されます。

項目の形式は次のとおりです。

* **ディメンション**：文字列- 文字列の最大長は動的であり、広告階層の要素をどのように設定するかによって異なります。
* **指標**：数値 / **注：** selected\_currency 項目の形式は文字列です。  
  利用できる指標は、収益、イベントを実行したユニークユーザー数、イベントの発生数です。※ROIやROASといったコスト関連の指標を算出するには、収益とコストの両方の指標が必要です。収益指標はコホートにあり、コスト指標はROI360コストETLから提供されます。

#### ディメンション

<Table>
  <thead>
    <tr>
      <th>
        フィールド名
      </th>
      <th>
        説明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        app\_id
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        media\_source
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        conversion\_type
      </td>
      <td>
        含まれる値：install, install-unified（統合レポートでのインストール数を表します）, re-engagement, re-attribution
      </td>
    </tr>
    <tr>
      <td>
        attributed\_touch\_type
      </td>
      <td>
        含まれる値：click, impressions, pre-install, unknown, tv, null
      </td>
    </tr>
    <tr>
      <td>
        days\_post\_attribution
      </td>
      <td>
        * コンバージョン日からの経過日数（特定のコンバージョンのタイムスタンプではありません）。
        * ヒント！この値を使用して、リテンションや〇日後時点でのKPIなどを計算しましょう。
      </td>
    </tr>
    <tr>
      <td>
        event\_date
      </td>
      <td>
        * ユーザーが特定のイベントを実行した日付です。
        * 形式： yyyy-mm-dd
        * 例：ユーザーが特定のアプリ内イベントを実行した日付。（CVの場合）
        * 注意!event\_name が af\_conversionの場合、event\_dateとconversion\_dateは同じ値になります。
      </td>
    </tr>
    <tr>
      <td>
        conversion\_date
      </td>
      <td>
        * 各種コンバージョンを計測した日付です。
        * 形式： yyyy-mm-dd
        * 例：インストール日
      </td>
    </tr>
    <tr>
      <td>
        event\_name
      </td>
      <td>
        イベントを特定します。特定の意味を持つイベント名もあれば、アプリ内で広告主が設定したアプリ内イベントに関連するイベント名もあります。 

        | event\_name | 計測内容 |
        | --- | --- |
        | af\_conversion | コンバージョンしたユーザー。conversion\_type を使用して、インストール、リエンゲージメント、リアトリビューションなどのCVタイプを区別してください。 |
        | af\_session | アプリ起動 |
        | cohort\_uninstall | アプリのアンインストール |
        | 広告主が定義したアプリ内イベント | そのアプリ内イベントを実行 |
      </td>
    </tr>
    <tr>
      <td>
        campaign
      </td>
      <td>
        キャンペーン階層の情報です。

        次の点を考慮してください：キャンペーン名の変更はサポートされていません。そのため、1つのキャンペーンIDに複数の名前が紐付けられる場合があります。
      </td>
    </tr>
    <tr>
      <td>
        campaign\_id
      </td>
      <td>
        キャンペーン階層の情報です。
      </td>
    </tr>
    <tr>
      <td>
        adset
      </td>
      <td>
        キャンペーン階層の情報です。
      </td>
    </tr>
    <tr>
      <td>
        adset\_id
      </td>
      <td>
        キャンペーン階層の情報です。
      </td>
    </tr>
    <tr>
      <td>
        ad
      </td>
      <td>
        キャンペーン階層の情報です。
      </td>
    </tr>
    <tr>
      <td>
        ad\_id
      </td>
      <td>
        キャンペーン階層の情報です。
      </td>
    </tr>
    <tr>
      <td>
        channel
      </td>
      <td>
        （キャンペーン階層の情報です）

        [2021年10月27日更新] 現在、MetaはGoogle Install Referrerの機能を介して提供するデータにチャネルの情報を含んでいません。
      </td>
    </tr>
    <tr>
      <td>
        site\_id
      </td>
      <td>
        キャンペーン階層の情報です。
      </td>
    </tr>
    <tr>
      <td>
        is\_primary\_attribution
      </td>
      <td>
        リターゲティングデータを特定し重複排除するために使用してください。
      </td>
    </tr>
    <tr>
      <td>
        geo
      </td>
      <td>
        ユーザーのIPアドレスから生成したISOの国コードです。
      </td>
    </tr>
    <tr>
      <td>
        代理店
      </td>
      <td>
        * 代理店による運用媒体の開示設定もサポートしています。
        * 非透明な代理店の場合、広告主と代理店の両方が同じ名前のキャンペーンを実行していると、同じキャンペーン名の行が複数存在することがあります。ご心配はいりません。行は重複していません。
      </td>
    </tr>
    <tr>
      <td>
        install\_app\_store
      </td>
      <td>
        Androidアプリのみ：アプリのダウンロード元のAndroidストア。<Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution">マルチストアAndroidアトリビューション</Anchor>を実装している広告主によって埋められます。空欄の場合は、Google Play Storeを意味します。
      </td>
    </tr>
    <tr>
      <td>
        keywords
      </td>
      <td>
        ユーザーがオンライン検索の際に使用した単語。アドネットワークからレポートされた値が入ります。
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        アドネットワークから返されたキーワードID。
      </td>
    </tr>
  </tbody>
</Table>

#### 指標

| フィールド名 | 説明 | 形式 |
| --- | --- | --- |
| unique\_users | イベントを実行したユニークユーザー数 | 数値 |
| revenue\_usd | <ul><li>USD換算での収益額です。例：$100.56 は100.56 と反映されます。</li><li>小数点以下は最大で2桁です。</li></ul> | 数値 |
| event\_count | イベントの実行回数 | 数値 |
| selected\_currency | アプリ設定で指定した3文字の通貨コード (USD、EUR)。フォーマットは<Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor>です。これは、管理画面上でコホートの収益を表示する際に使用される通貨設定と同じです。 | 文字列 |
| revenue\_selected\_currency | <ul><li>選択された通貨単位での収益の金額です。例えば、選択した通貨がEURの場合€1234.56 は 1234.56 と反映されます。</li><li>小数点以下2桁まで</li></ul> | 数値 |
| first\_inapp | <ul><li>コンバージョン後に初めてイベントを実行したユーザーの数。</li><li>first\_inapp 指標を合計すると、そのイベントの累積ユニークユーザー数がわかります。</li></ul> | 数値 |

#### ディレクトリとファイル名の構造

レポートへのパスは、次のフォルダー階層で構成されます：

形式：`/t=cohort_unified_versioned/dt=/version=/`

#### レポートのフォルダ階層

広告主バケットのコホートバージョン対応レポートフォルダ階層の例：

```
bucket
|
└── t=cohort_unified_versioned
    |
    ├── dt=2024-05-05
    |   |
    |   └── version=1714890235
    |   |    |
    |   |    ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    |
    |   |    ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    │
    |   |    └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |
    |   |
    |   └── version=1714890286
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |   |
    .   . 
    .   .
```

**説明：**

* **dt**：レポートに含まれるイベントが発生した日付
* **t**： レポートタイプ
* **version：** バージョンが作成されたときの Unixタイムスタンプ

### レポートのバージョンとデータの鮮度

* Intraday：レポートは数時間ごとに送信されます。
* レポートは、その日に現在利用可能なすべてのデータに関するものです。つまり、4月18日のすべてのレポートバージョンには、その時点の4月18日までに入手可能なすべてのデータが含まれます。
* **入手可能な最新のレポートバージョンのみを取り込んでください。**

| バージョン | レポートには、AppsFlyerが受信したデータ（UTC）が含まれます | 使用例 | 時間レポートの利用可能時期（UTC） |
| --- | --- | --- | --- |
| 1 | 0日目の午前4時 | 0日目の部分データ | 0日目の午前8時 |
| 2 | 0日目の午前8時 | 0日目の部分データ | 0日目の午後1時 |
| 3 | 0日目の午後12時 | 0日目の部分データ | 0日目の午後6時 |
| 4 | 0日目の午後4時 | 0日目の部分データ | 0日目の午後9時 |
| 5 | 0日目の午後8時 | 0日目の部分データ | 0日目の午後11時59分 |
| 6 | 0日目の午後11時59分 | 0日目のコンバージョンとアプリ内イベントの完全なデータ（AppsFlyerが0日目の午後11時59分から1日目の午前2時の間に受信したS2Sイベントを除く） | 1日目の午前4時 |
| 7 | 1日目の午前3時 | 0日目の完全なコンバージョンとアプリ内イベントデータ、およびS2S経由で送信された現在利用可能な広告収益データ | 1日目の午前8時 |
| 8 | 1日目の午前11時 | 0日目の完全なコンバージョンとアプリ内イベントデータ、およびS2S経由で送信された現在利用可能な広告収益データ | 1日目の午後6時 |
| 9 | 1日目の午後5時 | 0日目の完全なコンバージョンとアプリ内イベントデータ、およびS2S経由で送信された現在利用可能な広告収益データ | 1日目の午後11時59分 |
| 10 | 8日目の午前7時 | 広告収益ネットワーク側で発生した可能性のある潜在的な問題を考慮して、0日目のコンバージョンとアプリ内イベントデータ、およびS2S経由で送信される完全な広告収益データ | 8日目の午後1時 |

</Accordion>

<div id="cohort-timezone-versioned-report" />

<Accordion title="アドバンス集計（コホート タイムゾーン / バージョン対応）レポート">

### レポートの仕様

| 概要 | コホートタイムゾーンバージョン対応レポートには、ローカライズされたタイムゾーンに従って、すべての集計データがコホートされ、キャンペーンディメンションの粒度がすべて含まれます。レポートは、データの鮮度と正確性を最大化するために数時間ごとに更新されます。<br /><br /><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQk1cZkeJhlx3trW13SjGbD4aWX3LmXZJRDJRApuAJkjB7XAg4nSFUyN0_YoirX-QMHkhFeMHwEmiVj/pub?output=xlsx">サンプルレポートをダウンロード</Anchor> |
| --- | --- |
| 利用できるレポート | 以下のレポートをダウンロードできます。レポートの種類の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/cohort-and-retention-dashboard#cohort-principles">コホートダッシュボード</Anchor>で説明されています。<ul><li>**ユーザー獲得：** リエンゲージメント期間中のLTVを含む、ユーザー獲得メディアソースにアトリビューションします。</li><li>**リターゲティング：** 発生したイベントのリターゲティングメディアソースにアトリビューションします：<ul><li>リエンゲージメント計測後、リエンゲージメント期間中に発生したアプリ内イベント</li><li>リアトリビューション後に発生したアプリ内イベント</li></ul></li><li>**統合：** AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/resolve-retargeting-double-attribution">二重アトリビューション</Anchor>ルールに基づき、ユーザーを導いた最後のタッチメディアソースの下にデータを表示します。つまり、リエンゲージメント期間中に発生したLTVは、ユーザー獲得メディアソースではなく、リターゲティングメディアソースに紐づきます。</li></ul> |
| レポート期間 | 過去 1,095日間にコンバージョンしたユーザーつまり、レポートには毎日、過去 1,095日間にコンバージョンしたユーザーのイベントが含まれます。<br /><br />**注：** ローカルタイムゾーンで 1日目がまだ始まっていない場合、タイムゾーンバージョンのレポートはデータなしで届きます。 |
| レポート構成 | レポートのスキーマ（含まれているディメンションと指標）は固定されており、編集できません。 |
| データ更新頻度 | <ul><li>Intraday：レポートは数時間ごとに送信されます。</li><li>レポートはその日のデータです。つまり、4月18日のすべてのレポートバージョンには、4月18日の最新データがすべて含まれています。[詳細はこちら](/docs/advanced-aggregated-reports-in-data-locker#レポートのバージョンとデータの鮮度-1)</li></ul> |
| タイムゾーン | UTCを除くすべてのタイムゾーン。つまり、レポートには、AppsFlyerでUTCタイムゾーンが設定されているすべてのアプリのデータが除外されます。 |
| ディレクトリとファイル名の構造 | [詳細はこちら](/docs/advanced-aggregated-reports-in-data-locker#レポート構成-1) |
| パートナーのデータ保持ポリシーの影響 | 一部の広告媒体は、データ保存期間ポリシーを設けていることを考慮してください。この場合、データ保存期間の終了後に発生したイベントは、コホートレポートでは無視されます。<br /><br />例：SRN媒体 "A" は180日間のデータ保存期間ポリシーを設けているとします。インストール後180日目までのユーザーイベントは SRN「A」に紐づきます。180日後に発生したイベントは無視されます。<br /><br />**注：** イベントはオーバービューダッシュボードにオーガニックとして表示されます。 |

### レポート構成

レポートは、ディメンションとメトリックで構成されます。

項目の形式は次のとおりです。

* **ディメンション**：文字列- 文字列の最大長は動的であり、広告階層の要素をどのように設定するかによって異なります。
* **指標**：数値 / **注：** selected\_currency 項目の形式は文字列です。  
  利用できる指標は、収益、イベントを実行したユニークユーザー数、イベントの発生数です。※ROIやROASといったコスト関連の指標を算出するには、収益とコストの両方の指標が必要です。収益指標はコホートにあり、コスト指標はROI360コストETLから提供されます。

#### ディメンション

<Table>
  <thead>
    <tr>
      <th>
        フィールド名
      </th>
      <th>
        説明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        app\_id
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        media\_source
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        conversion\_type
      </td>
      <td>
        含まれる値：install, install-unified（統合レポートでのインストール数を表します）, re-engagement, re-attribution
      </td>
    </tr>
    <tr>
      <td>
        attributed\_touch\_type
      </td>
      <td>
        含まれる値：click, impressions, pre-install, unknown, tv, null
      </td>
    </tr>
    <tr>
      <td>
        days\_post\_attribution
      </td>
      <td>
        * コンバージョン日からの経過日数（特定のコンバージョンのタイムスタンプではありません）。
        * ヒント！この値を使用して、リテンションや〇日後時点でのKPIなどを計算しましょう。
      </td>
    </tr>
    <tr>
      <td>
        event\_date
      </td>
      <td>
        * ユーザーが特定のイベントを実行した日付です。
        * 形式： yyyy-mm-dd
        * 例：ユーザーが特定のアプリ内イベントを実行した日付。（CVの場合）
        * 注意!event\_name が af\_conversionの場合、event\_dateとconversion\_dateは同じ値になります。
      </td>
    </tr>
    <tr>
      <td>
        conversion\_date
      </td>
      <td>
        * 各種コンバージョンを計測した日付です。
        * 形式： yyyy-mm-dd
        * 例：インストール日
      </td>
    </tr>
    <tr>
      <td>
        event\_name
      </td>
      <td>
        イベントを特定します。特定の意味を持つイベント名もあれば、アプリ内で広告主が設定したアプリ内イベントに関連するイベント名もあります。 

        | event\_name | 計測内容 |
        | --- | --- |
        | af\_conversion | コンバージョンしたユーザー。conversion\_type を使用して、インストール、リエンゲージメント、リアトリビューションなどのCVタイプを区別してください。 |
        | af\_session | アプリ起動 |
        | cohort\_uninstall | アプリのアンインストール |
        | 広告主が定義したアプリ内イベント | そのアプリ内イベントを実行 |
      </td>
    </tr>
    <tr>
      <td>
        event\_timezone
      </td>
      <td>
        タイムゾーン：

        * days\_post\_atribution
        * event\_date
        * conversion\_date
      </td>
    </tr>
    <tr>
      <td>
        campaign
      </td>
      <td>
        キャンペーン階層の情報です。

        次の点を考慮してください：キャンペーン名の変更はサポートされていません。そのため、1つのキャンペーンIDに複数の名前が紐付けられる場合があります。
      </td>
    </tr>
    <tr>
      <td>
        campaign\_id
      </td>
      <td>
        キャンペーン階層の情報です。
      </td>
    </tr>
    <tr>
      <td>
        adset
      </td>
      <td>
        キャンペーン階層の情報です。
      </td>
    </tr>
    <tr>
      <td>
        adset\_id
      </td>
      <td>
        キャンペーン階層の情報です。
      </td>
    </tr>
    <tr>
      <td>
        ad
      </td>
      <td>
        キャンペーン階層の情報です。
      </td>
    </tr>
    <tr>
      <td>
        ad\_id
      </td>
      <td>
        キャンペーン階層の情報です。
      </td>
    </tr>
    <tr>
      <td>
        channel
      </td>
      <td>
        （キャンペーン階層の情報です）

        [2021年10月27日更新] 現在、MetaはGoogle Install Referrerの機能を介して提供するデータにチャネルの情報を含んでいません。
      </td>
    </tr>
    <tr>
      <td>
        site\_id
      </td>
      <td>
        キャンペーン階層の情報です。
      </td>
    </tr>
    <tr>
      <td>
        is\_primary\_attribution
      </td>
      <td>
        リターゲティングデータを特定し重複排除するために使用してください。
      </td>
    </tr>
    <tr>
      <td>
        geo
      </td>
      <td>
        ユーザーのIPアドレスから生成したISOの国コードです。
      </td>
    </tr>
    <tr>
      <td>
        代理店
      </td>
      <td>
        * 代理店による運用媒体の開示設定もサポートしています。
        * 非透明な代理店の場合、広告主と代理店の両方が同じ名前のキャンペーンを実行していると、同じキャンペーン名の行が複数存在することがあります。ご心配はいりません。行は重複していません。
      </td>
    </tr>
    <tr>
      <td>
        install\_app\_store
      </td>
      <td>
        Androidアプリのみ：アプリのダウンロード元のAndroidストア。<Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution">マルチストアAndroidアトリビューション</Anchor>を実装している広告主によって埋められます。空欄の場合は、Google Play Storeを意味します。
      </td>
    </tr>
    <tr>
      <td>
        keywords
      </td>
      <td>
        ユーザーがオンライン検索の際に使用した単語。アドネットワークからレポートされた値が入ります。
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        アドネットワークから返されたキーワードID。
      </td>
    </tr>
  </tbody>
</Table>

#### 指標

| フィールド名 | 説明 | 形式 |
| --- | --- | --- |
| unique\_users | イベントを実行したユニークユーザー数 | 数値 |
| revenue\_usd | <ul><li>USD換算での収益額です。例：$100.56 は100.56 と反映されます。</li><li>小数点以下は最大で2桁です。</li></ul> | 数値 |
| event\_count | イベントの実行回数 | 数値 |
| selected\_currency | アプリ設定で指定した3文字の通貨コード (USD、EUR)。フォーマットは<Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor>です。これは、管理画面上でコホートの収益を表示する際に使用される通貨設定と同じです。 | 文字列 |
| revenue\_selected\_currency | <ul><li>選択された通貨単位での収益の金額です。例えば、選択した通貨がEURの場合€1234.56 は 1234.56 と反映されます。</li><li>小数点以下2桁まで</li></ul> | 数値 |
| first\_inapp | <ul><li>コンバージョン後に初めてイベントを実行したユーザーの数。</li><li>first\_inapp 指標を合計すると、そのイベントの累積ユニークユーザー数がわかります。</li></ul> | 数値 |

#### ディレクトリとファイル名の構造

レポートへのパスは、次のフォルダー階層で構成されます：

形式：`/t=cohort_unified_timezone_versioned/dt=/version=/`

#### レポートのフォルダ階層

広告主バケットのコホートタイムゾーンバージョン対応レポートフォルダ階層の例：

```
bucket
|
└── t=cohort_unified_timezone_versioned
    |
    ├── dt=2024-05-05
    |   |
    |   └── version=1714890235
    |   |    |
    |   |    ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    |
    |   |    ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    │
    |   |    └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |
    |   |
    |   └── version=1714890286
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |   |
    .   . 
    .   .
```

**説明：**

* **dt**：レポートに含まれるイベントが発生した日付
* **t**： レポートタイプ
* **version：** バージョンが作成されたときの Unixタイムスタンプ

### レポートのバージョンとデータの鮮度

* Intraday：レポートは数時間ごとに送信されます。
* レポートは、その日に現在利用可能なすべてのデータに関するものです。つまり、4月18日のすべてのレポートバージョンには、その時点の4月18日までに入手可能なすべてのデータが含まれます。
* レポートのユースケースは、地域やタイムゾーンによって異なる場合があります。[詳細はこちら](/docs/advanced-aggregated-reports-in-data-locker#timezone-geos)
* **入手可能な最新のレポートバージョンのみを取り込んでください。**

| バージョン | レポートには、AppsFlyerが受信したデータ（UTC）が含まれます | 使用例 | 時間レポートの利用可能時期（UTC） |
| --- | --- | --- | --- |
| 1 | 1日目の午前4時 | 東部（Eastern）地域：0日目の部分データ | 1日目の午前8時 |
| 2 | 1日目の午前8時 | 東部（Eastern）地域：0日目の部分データ | 1日目の午後1時 |
| 3 | 1日目の午後12時 | 東部（Eastern）地域：0日目の部分データ | 1日目の午後6時 |
| 4 | 1日目の午後4時 | 東部（Eastern）地域：0日目の部分データ | 1日目の午後9時 |
| 5 | 1日目の午後8時 | 東部（Eastern）地域：0日目の部分データ | 1日目の午後11時59分 |
| 6 | 1日目の午後11時59分 | 東部（Eastern）と中部（Central）の地域：0日目の部分データ | 0日目の午前4時 |
| 7 | 0日目の午前4時 | すべての地域：0日目の部分データ | 0日目の午前8時 |
| 8 | 0日目の午前8時 | すべての地域：0日目の部分データ | 0日目の午後1時 |
| 9 | 0日目の午後12時 | すべての地域：0日目の部分データ | 0日目の午後6時 |
| 10 | 0日目の午後4時 | すべての地域：0日目の部分データ | 0日目の午後9時 |
| 11 | 0日目の午後8時 | <ul><li>東部（Eastern）地域：0日目のコンバージョンとアプリ内イベントの完全なデータ</li><li>中西部（Central / Western）地域：0日目の部分データ</li></ul> | 0日目の午後11時59分 |
| 12 | 0日目の午後11時59分 | 中西部（Central / Western）地域：0日目の部分データ | 1日目の午前4時 |
| 13 | 1日目の午前4時 | <ul><li>中部（Central）地域：0日目のコンバージョンとアプリ内イベントの完全なデータ</li><li>西部（Western）地域：0日目の部分データ</li><li>S2S経由で送信された、現在入手可能なすべての広告収益データ</li></ul> | 1日目の午前8時 |
| 14 | 1日目の午前8時 | 西部（Western）地域：0日目の一部のデータと、S2S経由で送信された現在利用可能なすべての広告収益データ | 1日目の午後1時 |
| 15 | 1日目の午後12時 | 西部（Western）地域：0日目の一部のデータと、レポートが処理された時点でS2S経由で送信された現在利用可能なすべての広告収益データ | 1日目の午後6時 |
| 16 | 1日目の午後12時 | 西部地域 - 0日目の部分的なデータと、S2S経由で送信された更新された広告収益データ（レポートは広告収益データの処理が完了した後にのみ処理されます） | 1日目の午後6時 |
| 17 | 1日目の午後4時 | 西部（Western）地域：0日目の一部のデータと、S2S経由で送信された現在利用可能なすべての広告収益データ | 1日目の午後9時 |
| 18 | 1日目の午後6時 | 西部（Western）地域：0日目の一部のデータと、S2S経由で送信された現在利用可能なすべての広告収益データ | 1日目の午後11時59分 |
| 19 | 1日目の午後8時 | 西部（Western）地域：コンバージョン全体、0日目のアプリ内イベントデータ、広告収益データ一式をS2S経由で送信 | 1日目の午後11時59分 |
| 20 | 1日目の午後11時59分 | 広告収益ネットワーク側で発生した可能性のある潜在的な問題を考慮して、0日目のコンバージョンとアプリ内イベントデータ、およびS2S経由で送信される完全な広告収益データ | 2日目の午前4時 |
| 21 | 8日目の午前0時 | 広告収益ネットワーク側で発生した可能性のある潜在的な問題を考慮して、0日目のコンバージョンとアプリ内イベントデータ、およびS2S経由で送信される完全な広告収益データ | 8日目の午前6時 |

</Accordion>

## 追加情報

<div id="timezone-geos" />

<Accordion title="タイムゾーンの地域">

レポートのユースケースは、地域やタイムゾーンによって異なる場合があります。次の表を参考にして、どの地域がどのタイムゾーンに一致するかを調べてください。

| 地域 | タイムゾーン |
| --- | --- |
| 東部 | UTC+12 - UTC+3 |
| 中部 | UTC+2.5 - UTC-3 |
| 西部 | UTC-3.5 - UTC-12 |

</Accordion>

<div id="bi-developer-considerations" />

<Accordion title="データ分析担当者向けの考慮事項">

**レポート内のデータ範囲**

レポートには、ユーザー獲得、インストール、リターゲティング、リアトリビューション、リエンゲージメント、およびそれらに紐づくアプリ内イベントが含まれます。

統合レポート、ユーザー獲得レポート、リターゲティングレポートを別々に、またはまとめてBIにロードする場合。これらをまとめてロードし、独自にビューをフィルターする場合は、次のようにします：

* 統合ビューの場合：is\_primary\_attribution=true または null 項目を使用します。
* ユーザー獲得の場合：conversion\_type=Install を使用します。
* リターゲティングの場合：conversion\_type=re-engagement または re-attribution を使用します。

データ読み込みプロセスにおいて新規獲得媒体のデータとリターゲティング媒体のデータを統合する場合には、新規獲得 (インストール) とリターゲティング (リエンゲージメント) のデータの重複を除外するロジックを実装する必要があります。これを行うには、conversion\_type=install、install-unified、re-engagement、またはre-attributionを使用します。<Anchor target="_blank" href="/marketers/ja/docs/resolve-retargeting-double-attribution">リターゲティングイベントの二重アトリビューション</Anchor>についてご覧ください。

**フィールドレベルの考慮事項**

* 継続率の指標を簡単に計算するには、days\_post\_attributionのカラムを活用しましょう。
* キャンペーン名とキャンペーンIDディメンションを使用したユニークユーザー数の計算：キャンペーン名の細分性を無視できる場合は、キャンペーン ID のユニークカウントを合計すれば指標は正確です。
* キャンペーン階層の項目を使用することでデータを集計可能です。
* revenue\_usd (USD換算の収益金額) は、イベント発生日の為替レートを使用して計算されます。

**一般的な考慮事項**

すべてのアプリのデータは設定可能です。単一のファイルで提供することも、アプリごとに個別のファイルで提供することもできます。

</Accordion>

<div id="use-cases" />

<Accordion title="使用事例">

以下は、BI開発者が Data Lockerを介して抽出できるコホートデータの一般的で実用的なアプリケーションの例です。各例は、SQL ステートメントとサンプルの Excel ビジュアルで示されています。

#### **1. リテンションの計算**

次の例では、次のことを行います：

* 1日目と7日目のリテンション、およびキャンペーンと広告ごとのインストールの合計数を計算します。
* コンバージョンイベントごとのイベント数を合計するには、`event_name` を`af_conversion` とフィルターします。
* 具体的には、「統合」レポートでユーザー獲得キャンペーンを分析する際、データフィルターを設定し、conversion\_type が （install， install\_unified） に一致するレコードを抽出します： `conversion_type IN (install, install_unified)`

**SQLステートメント**

```sql
select
    campaign_id, ad_id,
    sum(if(event_name = 'af_conversion', event_count,0)) as installs,
    sum(if(event_name = 'af_session' and days_post_attribution = 1, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day1,
    sum(if(event_name = 'af_session' and days_post_attribution = 7, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08' 
    and app_id = YOUR_APP
group by 1,2
```

**Excelの例**

| キャンペーンID | 広告ID | インストール | リテンション D1 | リテンション D7 |
| --- | --- | --- | --- | --- |
| 12345678 | 987654 | 100 | 30% | 10% |
| 98765432 | 123456 | 200 | 25% | 15% |
| 07315466 | 613770 | 300 | 20% | 12% |

#### **2. 複数のアプリ内イベントのARPUを計算する**

次の例では、次のことを行います：

* キャンペーンごとに複数のアプリ内イベントのARPUを計算します。
* データをフィルターして、`conversion_type=re-engagement`と`conversion_type=re-attribution`、リターゲティングキャンペーンを分析します。
* コンバージョンイベントごとのイベント数を合計するには、`event_name` を`af_conversion` とフィルターします。
* 複数のイベントの収益を合計します。この場合、`af_purchase`と`af_coins`。
* データ処理の負荷を最小限に抑えるには、`days_post_attribution`を必要最低限の値（この場合は7）に設定します。

**SQLステートメント**

```sql
select
    campaign_id,
    sum(if(days_post_attribution <= 1 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day1,
    sum(if(days_post_attribution <= 3 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day3,
    sum(if(days_post_attribution <= 7 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and days_post_attribution <= 7
    and conversion_type in ('re-engagement', 're-attribution')
    and app_id = YOUR_APP
group by 1
```

**Excelの例**

| キャンペーンID | コンバージョンタイプ | ARPU<br /><br />1日目 | ARPU<br /><br />3日目 | ARPU<br /><br />7日目 |
| --- | --- | --- | --- | --- |
| 12345678 | Re-engagement | 6.23 | 5.11 | 2.34 |
| 98765432 | Re-engagement | 3.57 | 1.34 | 4.86 |
| 07315466 | 再アトリビューション | 7.41 | 6.79 | 5.29 |

#### **3. 特定のコホート日のアプリ内イベントコンバージョン率を計算する**

次の例では、次のことを行います：

* 複数のディメンション（この場合は、コンバージョン日、地域、キャンペーン、広告、サイトID）の Day 0 アプリ内イベントのコンバージョン率を計算します。
* データをフィルターして、`is_primary_attribution=true`、統合データ（UAとリターゲティングキャンペーン）の両方を分析します。
* コンバージョンイベントごとのイベント数を合計するには、`event_name` を`af_conversion` とフィルターします。
* データ処理の負荷を最小限に抑えるには、`days_post_attribution`を必要最低限の値（この場合は7）に設定します。

**SQLステートメント**

```sql
select
    conversion_date, geo, campaign_id, ad_id, site_id,
    sum(if(days_post_attribution = 0 and event_name = 'af_complete_tutorial', unique_users, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as day0_af_tutorial_conversion
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and is_primary_attribution = true
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Excelの例**

| コンバージョン日 | 地理 | キャンペーンID | 広告ID | サイトID | Day 0 af\_complete\_tutorial |
| --- | --- | --- | --- | --- | --- |
| 2022-11-07 | US | 12345678 | 123456 | site\_123 | 45% |
| 2022-11-05 | イギリス | 98765432 | ヌル | site\_654 | 70% |
| 2022-10-31 | 韓国 | 07315466 | ヌル | ヌル | 63% |

#### **4.日次インストールの計算**

次の例では、次のことを行います：

* アプリ ID、コンバージョン日、メディアソース、イベント名、コンバージョンタイプごとのインストール数を計算します。
* 全体レポートで、`conversion_type` を `install` または `install_unified` に設定して、ユーザー獲得インストール（リターゲティングではない）を表示するようにデータをフィルターします。
* `event_name`を`af_conversion`に設定してインストールを合計します。

**SQLステートメント**

```sql
select
    app_id,
    conversion_date,
    media_source,
    event_name,
    conversion_type,
    sum(events_count) as total
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    // If you're querying data from unified reports, edit the line below to: and conversion_type IN ('install', 'install_unified')
    and conversion_type = 'install'
    and event_name = 'af_conversion'
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Excelの例**

| App ID | コンバージョン日 | メディアソース | イベント名 | 合計 |
| --- | --- | --- | --- | --- |
| id123456789 | 2022-11-07 | adnet1\_int | af\_conversion | 105 |
| id123456789 | 2022-11-05 | adnet2\_int | af\_conversion | 216 |
| id123456789 | 2022-10-31 | adnet3\_int | af\_conversion | 327 |

#### **5. Meta広告からの収益の計算**

次の例では、次のことを行います：

* Facebookからの3日目の収益をコンバージョン日とアプリIDで計算します。
* `media_source='Facebook Ads'` とフィルターしてFacebookデータを分析します。
* データ処理の負荷を最小限に抑えるには、`days_post_attribution`を必要最低限の値（この場合は3）に設定します。

**SQLステートメント**

```sql
select
    conversion_date,
    app_id,
    media_source,
    sum(if(days_post_attribution <= 3, revenue_usd, 0)) as revenue_day3
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and days_post_attribution <= 3
    and media_source = 'Facebook Ads'
    and app_id in (APP_ID1, APP_ID2, ...)
group by 1,2,3
```

**Excelの例**

| コンバージョン日 | App ID | メディアソース | 収益<br /><br />3日目 |
| --- | --- | --- | --- |
| 2022-11-07 | id123456789 | adnet1\_int | 400.45 |
| 2022-11-05 | id123456789 | adnet2\_int | 99.23 |
| 2022-10-31 | id123456789 | adnet3\_int | 13.34 |

#### **6. 最大365コホート日のASAキーワードIDごとのARPU計算**

次の例では、次のことを行います：

* キーワードIDごとの Apple Search Ads経由のコホート365日目までの ARPUを計算します。
* `media_source='Apple Search Ads'` とフィルターしてApple Search Adsデータを分析します。
* コンバージョンイベントごとのイベント数を合計するには、`event_name` を`af_conversion` とフィルターします。

**SQLステートメント**

```sql
select
    media_source,
    keyword_id,
    sum(if(days_post_attribution <= 365, revenue_usd,0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day365
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and media_source = 'Apple Search Ads'
    and app_id = YOUR_APP
group by 1
```

**Excelの例**

| メディアソース | Keyword ID | ARPU<br /><br />Day 365 |
| --- | --- | --- |
| adnet1\_int | 123456 | 57,019.93 |
| adnet2\_int | 987654 | 64,867.84 |
| adnet3\_int | 666854 | 48,160.02 |

#### **7.地域ごとのアトリビューション時間によるARPU 7日目の計算**

次の例は、<Anchor target="_blank" href="/marketers/ja/docs/cohort-and-retention-dashboard#trend-type%E2%80%94kpi-by-attribution-time">アトリビューション時間別のKPI</Anchor>の使用方法を示しています。この例では、次のことを行います：

* ARPU 7日目を国ごとのアトリビューション計測日で計算します。
* 結果はコンバージョン数で並べ替えられ、上位20の地域が表示されます。
* デーを `conversion_type='install'` とフィルターします。
* 最初の列には geo（国）が表示されます。2番目の列には、合計コンバージョン数が表示されます。その後の列には、クエリの行として指定された各日の7日目の収益が表示されます。

**SQLステートメント**

```sql
select
    geo,
    sum(if(event_name = 'af_conversion', event_count, 0)) total_conversions,
    sum(if(cohort_day = '2023-07-11' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-11' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_11,
    sum(if(cohort_day = '2023-07-12' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-12' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_12,
    sum(if(cohort_day = '2023-07-13' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-13' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_13,
    sum(if(cohort_day = '2023-07-14' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-14' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_14,
    sum(if(cohort_day = '2023-07-15' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-15' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_15,
    sum(if(cohort_day = '2023-07-16' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-16' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_16
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-07-11' and '2023-07-16'
    and days_post_attribution <= 7
    // If you're querying data from unified reports, edit the line below to: and conversion_type IN ('install', 'install_unified')    
    and conversion_type = 'install'
    and app_id = 'YOUR_APP'
group by 1
order by 2 desc
limit 20
```

**Excelの例**

| 地理 | 総コンバージョン数 | ARPU 7日目（2023年7月11日） | ARPU 7日目（2023年7月12日） | ARPU 7日目（2023年7月13日） | ARPU 7日目（2023年7月14日） | ARPU 7日目（2023年7月15日） | ARPU 7日目（2023年7月16日） |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 韓国 | 120,660 | $7,798.89 | $6,997.37 | $8,258.95 | $9,050.21 | $10,018.04 | $13,765.73 |
| カナダ | 35,099 | $64,867.84 | $7,050.19 | $5,656.33 | $9,553.75 | $8,632.41 | $11,308.06 |
| チリ | 26,750 | $48,160.02 | $21,249.55 | $22,584.57 | $24,033.07 | $31,118.91 | $41,145.22 |

#### **8. コンバージョン後7日目の購入データの計算**

次の例では、次のことを行います：

* コンバージョンから 7日後に af\_purchase イベントを実行した累積ユニークユーザー数を（統合ビューで）計算します。
* イベントへのコンバージョン率、つまりコンバージョン後 7日以内に購入を行ったコンバージョンの割合を計算します。
* デーを `conversion_type='install'` とフィルターします。
* データは、アプリ、コンバージョン日、メディアソース、キャンペーン、広告セットごとにグループ化されています。

**SQLステートメント**

```sql
select
    app_id, conversion_date, media_source, campaign, adset,
    sum(if(event_name = 'af_conversion', event_count,0)) as unified_conversions,
    sum(if(event_name = 'af_purchase', first_inapp, 0)) as af_purchase_day_7_cumulative_unique_users,
    concat(
        cast(
            round(
                sum(if(event_name = 'af_purchase', first_inapp, 0)) /
                sum(if(event_name = 'af_conversion', event_count, 0)) * 100.0
            ,2)
        as varchar),
    '%') as af_purchase_day_7_cumulative_unique_users_conversion_rate
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-12-01' and '2023-12-31'
    and is_primary_attribution = true
    and days_post_attribution <= 7
    and app_id in (APP_ID1, APP_ID2, ...)
group by 1,2,3,4,5
```

**Excelの例**

| App ID | コンバージョン日 | メディアソース | キャンペーン | 広告セット | 統合コンバージョン | 7日目 af\_purchase 累計 | 7日目 af\_purchase CV率 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| id123456789 | 2024-03-05 | adnet1\_int | campaign\_1 | adset\_1 | 100 | 20 | 20% |
| id123456789 | 2024-03-07 | adnet2\_int | campaign\_2 | adset\_2 | 200 | 10 | 5% |
| id123456789 | 2024-03-31 | adnet3\_int | campaign\_3 | adset\_3 | 150 | 15 | 10% |

#### **9. DAUの計算**

次の例では、次のことを行います：

* メディアソース、キャンペーン、広告別にグループ化された選択した期間内の各日のDAUを計算します。
* デーを `event_name = 'af_session'` とフィルターします。
* 一度に1日のユニークユーザーを合計します。各日は独自のディメンション（列）です。

**注：**

* 複数の日を合計することはできません（例：WAUまたはMAUを取得するため）。
* DAUは、過去1,095日間のコンバージョンユーザーのアクティビティに基づいています。これは、アクティビティ管理画面やレポートに表示されるデータとは異なり、この制限はありません。[特性と制限](/docs/advanced-aggregated-reports-in-data-locker#traits-and-limitations)のセクションの「コンバージョン後の日数」を参照してください。

**SQLステートメント**

```sql
select
media_source,campaign_id, ad_id,
sum(case when event_date = '2024-08-06' then unique_users end) as dau_2024_08_06,
sum(case when event_date = '2024-08-07' then unique_users end) as dau_2024_08_07,
sum(case when event_date = '2024-08-08' then unique_users end) as dau_2024_08_08
from YOUR_DATA_LOCKER_REPORT
where event_date between '2024-08-06' and '2024-08-08'
and event_name = 'af_session'
and app_id = YOUR_APP
group by 1,2,3
```

**Excelの例**

| Media source | Campaign | Ad | DAU 8月6日 | DAU 8月7日 | DAU 8月8日 |
| --- | --- | --- | --- | --- | --- |
| adnet1\_int | campaign\_1 | adset\_1 | 475,250 | 420,485 | 463,912 |
| adnet2\_int | campaign\_2 | adset\_2 | 380,987 | 355,665 | 401,232 |
| adnet3\_int | campaign\_3 | adset\_3 | 290,042 | 570,322 | 489,787 |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特性と制限">

| 特性 |  |
| --- | --- |
| コストデータ | <ul><li>利用できません。<Anchor target="_blank" href="/marketers/ja/docs/set-up-and-use-roi360-cost-etl-reports">コストETLを使用する</Anchor>。</li><li><Anchor target="_blank" href="/marketers/ja/docs/combine-cost-etl-and-cohort-reports-via-data-locker">コストETLとコホートレポートを組み合わせる方法</Anchor>も参照してください。</li></ul> |
| キャンペーン名の変更 | 対応していません。キャンペーン名が変更された場合は、キャンペーン IDを使用してグループ化とフィルターを行います。 |
| データ更新頻度 | 日中（平均4時間毎の更新） |
| 広告収益 | 利用可能 |
| 通貨設定 | 行ごとに、USDとアプリ個別の通貨設定のデータが確認可能です。 |
| タイムゾーン | アプリ固有のタイムゾーンは、タイムゾーンバージョン対応レポートで確認できます。 |
| オーガニックデータ | 利用可能 |
| コンバージョン (インストール、リアトリビューション、リエンゲージメント) 後の日数 | 1,095日間ご利用いただけます。 |
| 代理店の運用媒体の開示設定 | <ul><li>サポート対象</li><li>X広告とMeta広告のデータは常に開示されています。</li></ul> |
| アプリ毎のデータ分割 | サポート対象 |
| SKAN計測データ | 含まれていません。つまり、データはData Lockerレポートではなく、iOSポストバックによって提供されます。 |
| アンインストールデータ | アンインストールは毎日処理されます。そのため、1日の完全なデータを含むレポートにのみ表示されます（部分的なデータではありません）。 |
| 再インストールについて | <ul><li>再インストール後のイベントが未アトリビューションのオーガニックイベントと見なされる場合：<ul><li>2024年5月26日現在のみ含まれている。<Anchor target="_blank" href="/marketers/ja/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">詳細を知る</Anchor></li><li>インストール時間は<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor>フィールドに基づいています。</li><li>ユニークユーザーやリテンション測定にはカウントされません。</li></ul></li><li>再インストール後のイベントが最初のインストールに起因する場合、それらは常に含まれる。<Anchor target="_blank" href="/marketers/ja/docs/unique-users">詳細を知る</Anchor></li></ul> |

</Accordion>

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/combine-cost-etl-and-cohort-reports-via-data-locker">コストETLとアドバンス集計コホートレポートを組み合わせるクエリ</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/cohort-and-retention-dashboard">コホートダッシュボード</Anchor>

<div data-zendesk-anchors="advanced-aggregated-reports-in-data-locker=data-locker%E3%82%A2%E3%83%89%E3%83%90%E3%83%B3%E3%82%B9%E9%9B%86%E8%A8%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HWWH83KNSF4BRGTDJ0JD271G=data-locker%E3%82%A2%E3%83%89%E3%83%90%E3%83%B3%E3%82%B9%E9%9B%86%E8%A8%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 setup=%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 h_01HWWH83KN9CM7ZY43W01AV6TA=%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 reports-available=%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%82%8B%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HWWNY76W6RFKX33MXHE4GSBD=%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%82%8B%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HWWNR256DRMBNFX3NV8ATNAY=cohort-versioned-report report-facts=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E4%BB%95%E6%A7%98 h_01HVRBVXS47K91A6KVV33S1BY6=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E4%BB%95%E6%A7%98 report-structure=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E6%A7%8B%E6%88%90 h_01HWWH83KNE46SPK1MS99XX64D=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E6%A7%8B%E6%88%90 dimensions=%E3%83%87%E3%82%A3%E3%83%A1%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3 01H7WG3CA14PQ2PJ58FX8TE6ZH=%E3%83%87%E3%82%A3%E3%83%A1%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3 metrics=%E6%8C%87%E6%A8%99 01H7WG3CA24VQKFVP99S82GCXZ=%E6%8C%87%E6%A8%99 directory-and-filename-structure=%E3%83%87%E3%82%A3%E3%83%AC%E3%82%AF%E3%83%88%E3%83%AA%E3%81%A8%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E5%90%8D%E3%81%AE%E6%A7%8B%E9%80%A0 h_01HVRDKKQA17SMJFFAEDG7A2X2=%E3%83%87%E3%82%A3%E3%83%AC%E3%82%AF%E3%83%88%E3%83%AA%E3%81%A8%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E5%90%8D%E3%81%AE%E6%A7%8B%E9%80%A0 the-report-folder-hierarchy-in-aws=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E9%9A%8E%E5%B1%A4 h_01HETBAQVVA750VTE1ABSM2M47=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E9%9A%8E%E5%B1%A4 report-versions-and-data-freshness=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%81%A8%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E9%AE%AE%E5%BA%A6 h_01HWWH83KN51RR2VJ2F5N8YQ3J=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%81%A8%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E9%AE%AE%E5%BA%A6 h_01HWWNVFCWJ7DZCKKKSBMH9NM5=cohort-timezone-versioned-report report-facts::15e071f=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E4%BB%95%E6%A7%98-1 h_01HWWH83KNPZETHR2TQS2E4QNT=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E4%BB%95%E6%A7%98-1 report-structure::43ffff28=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E6%A7%8B%E6%88%90-1 h_01HWWH83KNG0V2ZMZZ7CTV2GE7=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E6%A7%8B%E6%88%90-1 01HWSX3FA0K39D9M5RQ7J36Q23=%E3%83%87%E3%82%A3%E3%83%A1%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3-1 01HWSX3FA035Z8W6EPV4Q6E3JP=%E6%8C%87%E6%A8%99-1 01HWSX3FA189EMBJZ1P21YHC45=%E3%83%87%E3%82%A3%E3%83%AC%E3%82%AF%E3%83%88%E3%83%AA%E3%81%A8%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E5%90%8D%E3%81%AE%E6%A7%8B%E9%80%A0-1 01HX97NC4F2WCJABSM2NBSBEDN=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E9%9A%8E%E5%B1%A4-1 report-versions-and-data-freshness::e0755e26=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%81%A8%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E9%AE%AE%E5%BA%A6-1 h_01HWWH83KPS2ANCQKS2B3V529Z=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%81%A8%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E9%AE%AE%E5%BA%A6-1 additional-information=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01HWWH83KPK8535X9EBZVJ9SQK=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01HWWN6GAAD75HPC5GTE40QA37=timezone-geos 01H7WG3CA2C3HV8YT5ZMP9E0QY=bi-developer-considerations 01H7WG3CA2YF03SC6RBMCJYYVX=use-cases 1-Calculate-retention=1-%E3%83%AA%E3%83%86%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E8%A8%88%E7%AE%97 h_01HMTZ0DZWN54HBQ0ZTY0VFNFM=1-%E3%83%AA%E3%83%86%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E8%A8%88%E7%AE%97 2-Calculate-arpu-of-multiple-inapp-events=2-%E8%A4%87%E6%95%B0%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AEarpu%E3%82%92%E8%A8%88%E7%AE%97%E3%81%99%E3%82%8B h_01HMTZ0DZWHZ77RYWYAQEJV7X5=2-%E8%A4%87%E6%95%B0%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AEarpu%E3%82%92%E8%A8%88%E7%AE%97%E3%81%99%E3%82%8B 3-Calculate-inapp-event-conversion-rate-for-a-specific-cohort-day=3-%E7%89%B9%E5%AE%9A%E3%81%AE%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E6%97%A5%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E7%8E%87%E3%82%92%E8%A8%88%E7%AE%97%E3%81%99%E3%82%8B h_01HMTZ0DZW7VA6T6MQY7BY1JZT=3-%E7%89%B9%E5%AE%9A%E3%81%AE%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E6%97%A5%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E7%8E%87%E3%82%92%E8%A8%88%E7%AE%97%E3%81%99%E3%82%8B 4-Calculate-daily-installs=4%E6%97%A5%E6%AC%A1%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E8%A8%88%E7%AE%97 h_01HMTZ0DZWARZFAQ9R4VF56YN3=4%E6%97%A5%E6%AC%A1%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E8%A8%88%E7%AE%97 5-Calculate-revenue-from-facebook-ads=5-meta%E5%BA%83%E5%91%8A%E3%81%8B%E3%82%89%E3%81%AE%E5%8F%8E%E7%9B%8A%E3%81%AE%E8%A8%88%E7%AE%97 h_01HMTZ0DZW74HWW6Z3VDWDMGRF=5-meta%E5%BA%83%E5%91%8A%E3%81%8B%E3%82%89%E3%81%AE%E5%8F%8E%E7%9B%8A%E3%81%AE%E8%A8%88%E7%AE%97 6-Calculate-arpu-per-asa-keyword-id-for-up-to-365-cohort-days=6-%E6%9C%80%E5%A4%A7365%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E6%97%A5%E3%81%AEasa%E3%82%AD%E3%83%BC%E3%83%AF%E3%83%BC%E3%83%89id%E3%81%94%E3%81%A8%E3%81%AEarpu%E8%A8%88%E7%AE%97 h_01HMTZ0DZWSN83V0TEHVM2H5XS=6-%E6%9C%80%E5%A4%A7365%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E6%97%A5%E3%81%AEasa%E3%82%AD%E3%83%BC%E3%83%AF%E3%83%BC%E3%83%89id%E3%81%94%E3%81%A8%E3%81%AEarpu%E8%A8%88%E7%AE%97 Calculate-arpu-days-0-7-by-attribution-time-per-geo=7%E5%9C%B0%E5%9F%9F%E3%81%94%E3%81%A8%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%99%82%E9%96%93%E3%81%AB%E3%82%88%E3%82%8Barpu-7%E6%97%A5%E7%9B%AE%E3%81%AE%E8%A8%88%E7%AE%97 01H8XYTJVQ1YFBHPWVPP9D7MJ8=7%E5%9C%B0%E5%9F%9F%E3%81%94%E3%81%A8%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%99%82%E9%96%93%E3%81%AB%E3%82%88%E3%82%8Barpu-7%E6%97%A5%E7%9B%AE%E3%81%AE%E8%A8%88%E7%AE%97 8-calculate-purchases-day-7-after-conversion=8-%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E5%BE%8C7%E6%97%A5%E7%9B%AE%E3%81%AE%E8%B3%BC%E5%85%A5%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E8%A8%88%E7%AE%97 h_01J7N4VB83T4KZ6G0Q634ASMHV=8-%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E5%BE%8C7%E6%97%A5%E7%9B%AE%E3%81%AE%E8%B3%BC%E5%85%A5%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E8%A8%88%E7%AE%97 9-calculate-dau=9-dau%E3%81%AE%E8%A8%88%E7%AE%97 h_01J55D2FFW0XSH3G6AXRS06RPV=9-dau%E3%81%AE%E8%A8%88%E7%AE%97 01H7WG3CA2Y59D2EVMN3YFFY1W=traits-and-limitations h_01HDNZ8A0QH74CGSEG6TKKARJP=%E5%8F%82%E7%85%A7" />
