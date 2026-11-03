---
title: Data Lockerでのコホート分析
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2021-10-14T08:46:00Z'
  edited_at: '2026-10-14T09:25:21Z'
  id: 4408945472529
  locale: ja
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ja/articles/4408945472529
---
> **概要：** Data Lockerのコホート分析機能では、広告階層の全ての要素を含んだ集計データが利用可能です。レポートには、過去365日間のアトリビューションユーザーのデータが含まれています。このレポートは、ローデータまたはコホートAPI、あるいはその両方をご契約の一部として契約している広告主が利用できます。つまり、このレポート機能はData Locker自体の有料契約は必要ありません。

## Data Lockerでのコホート分析

場合によっては、メディアソースのデータ共有ポリシーや広告主側の<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">プライバシー保護ポリシーにより、AppsFlyerのアトリビューションのローデータが</Anchor><Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">制限</Anchor>されることがあります。この制限は、キャンペーンや広告セットなどのアトリビューションに関連するすべてのフィールドを含みます。コホートレポートは、ローデータの代わりに集計データを提供します。

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQ8q_4xv83wHkl4fs6jndEffRu-RHsPobBRfxDG-bUNXb0pOnvJH4QT0nXKdWvi3JPtVUBegTFbxIEe/pub?output=xlsx">サンプルレポートをダウンロード</Anchor>

<div id="enable-data-locker" />

<Accordion title="Data Lockerの有効化">

この機能を利用できるのは、Data Locker、コホートAPI、またはローデータレポートを利用している広告主です。<Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers">Data Locker</Anchor>でレポートを有効にするには、以下の手順のいずれかを完了してください。

| 既にData Lockerでデータを取得していますか？ | 手順 |
| --- | --- |
| はい | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)コホートレポートをData Lockerに追加するために：<ol><li>AppsFlyer管理画面 左メニュー **エクスポート > Data Locker**へ移動します。</li><li>**コホート分析**セクションのすべてのレポートを選択します。</li><li>**設定を保存**をクリックしてください。<br />レポートは翌日午前10:00 UTCまでに利用可能になります。</li></ol> |
| いいえ | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)**Data Lockerの設定：**<ol><li>Data Lockerの初期設定（<Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers#set-up-data-locker">広告主向け</Anchor> \| <Anchor target="_blank" href="/partners/ja/docs/data-locker-for-partners">パートナー向け</Anchor>）を完了してください。</li><li>コホートレポートをData Lockerに追加してください：<ol><li>AppsFlyer管理画面 左メニュー **エクスポート > Data Locker**へ移動します。</li><li>**コホート分析**セクションのすべてのレポートを選択します。</li><li>**設定を保存**をクリックしてください。<br />レポートは翌日午前10:00 UTCまでに利用可能になります。</li></ol></li></ol> |

</Accordion>

データはBIシステムにロードし、キャンペーンパフォーマンスと最適化プロセスの一部として使用できます。

**利用可能な指標**

利用可能な指標は、収益、イベントを行ったユニークユーザー数、イベントの発生回数です。※ROIやROASといったコスト関連の指標を算出するには、収益とコストの両方の指標が必要です。収益指標はコホートに存在し、コスト指標は<Anchor target="_blank" href="/marketers/ja/docs/set-up-and-use-roi360-cost-etl-reports">ROI360コストETL</Anchor>に存在します。

<div id="facts" />

<Accordion title="コホート分析について">

| 利用できるレポート | 以下のレポートをダウンロードできます。レポートの種類の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/cohort-and-retention-dashboard#cohort-principles">コホートダッシュボード</Anchor>で説明されています。<ul><li>**ユーザー獲得：** リエンゲージメント期間中のLTVを含む、ユーザー獲得メディアソースに紐づきます：</li><li>**リターゲティング：** 発生したイベントのリターゲティングメディアソースに紐づきます：<ul><li>リエンゲージメント計測後、リエンゲージメント期間中に発生したアプリ内イベント</li><li>リアトリビューション後に発生したアプリ内イベント</li></ul></li><li>**統合：** AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/resolve-retargeting-double-attribution">二重アトリビューションルール</Anchor>に基づき、ユーザーを導いた最後のタッチメディアソースの傘下にデータを表示します。つまり、リエンゲージメント期間中に発生したLTVは、ユーザー獲得メディアソースではなく、リターゲティングメディアソースに紐づきます。</li></ul> |
| --- | --- |
| レポート期間 | 過去365日の間にコンバージョンしたユーザー。つまり、毎日、過去365日間のユーザーのコンバージョン状況がレポートされます。 |
| レポート構成 | 各レポートのスキーマ（含まれるディメンションと指標）は固定されており、編集することはできません。[レポート構造](/docs/cohort-analytics-via-data-locker#report-structure)をご覧ください。 |
| レポート配信 | [Data Lockerでコホートレポートを有効にする](/docs/cohort-analytics-via-data-locker#enable-data-locker)をご確認ください。 |
| データ更新頻度 | <ul><li>毎日</li><li>各指標は、日本時間午前9時（UTC時間 0:00）までのデータを用いて算出されます。言い換えれば、UTC時間ベースでその日の終わりまでのデータです。</li><li>レポートは、Data Lockerの日時 (dt) フォルダーで 10:00 UTC（日本時間19時）には利用可能になります。たとえば、月曜日のデータは火曜日の 10:00 UTC（日本時間で火曜の19時）に 月曜日のフォルダで使用できます。</li></ul> |
| パートナーのデータ保持ポリシーの影響 | 一部の広告媒体は、データ保存期間ポリシーを設けていることを考慮してください。この場合、データ保存期間の終了後に発生したイベントは、コホートレポートでは無視されます。<br /><br />例：SRN媒体 "A" は180日間のデータ保存期間ポリシーを設けているとします。このとき、インストール日から180日目までのイベントは媒体"A"に紐づきますが、180日以降に発生したイベントは全てオーガニックに紐づけられます。 |

</Accordion>

<div id="report-structure" />

<Accordion title="レポート構成">

レポートは、ディメンションと指標で構成されます。

項目の形式は次のとおりです。

* **ディメンション：** 文字列- 文字列の最大長は動的であり、広告階層の要素をどのように設定するかによって異なります。
* **指標：** 数値　/ **注：** selected\_currency 項目の形式は文字列です。

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
        --
      </td>
    </tr>
    <tr>
      <td>
        media\_source
      </td>
      <td>
        --
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
        * 注意！ event\_name が af\_conversionの場合、event\_dateとconversion\_dateは同じ値になります。
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
        agency
      </td>
      <td>
        * 代理店による運用媒体の開示設定もサポートしています。
        * 運用詳細を開示していない代理店の場合、広告主と代理店の両方が同じ名前のキャンペーンを行っていると、同じキャンペーン名を持つ複数の行が表示される可能性があります。ご心配はいりません。行は重複していません。
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
        ユーザーがオンライン検索の際に使用した単語。 アドネットワークからレポートされたもの
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        [2022年4月27日から利用可能なフィールド] アドネットワークから返されるキーワードIDです。
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

</Accordion>

<div id="bi-developer-considerations" />

<Accordion title="データ分析担当者向けの考慮事項">

**レポート内のデータ範囲**

レポートには、ユーザー獲得、インストール、リターゲティング、リアトリビューション、リエンゲージメント、およびそれらに紐づくアプリ内イベントが含まれます。

統合レポート、ユーザー獲得レポート、リターゲティングレポートを別々に、またはまとめてBIにロードする場合。これらをまとめてロードし、独自に表示タイプをフィルターする場合は、次のようにします：

* 統合の場合：is\_primary\_attribution=true または null 項目を使用します。
* ユーザー獲得の場合：conversion\_type=Install を使用します。
* リターゲティングの場合：conversion\_type=re-engagement または re-attribution を使用します。

データ読み込みプロセスにおいて新規獲得媒体のデータとリターゲティング媒体のデータを統合する場合には、新規獲得 (インストール) とリターゲティング (リエンゲージメント) のデータの重複を除外するロジックを実装する必要があります。これを行うには、conversion\_type=install、install-unified、re-engagement、またはre-attributionを使用します。<Anchor target="_blank" href="/marketers/ja/docs/resolve-retargeting-double-attribution">リターゲティングイベントの二重アトリビューション</Anchor>についてご覧ください。

**フィールドレベルの考慮事項**

* 継続率の指標を簡単に計算するには、days\_post\_attributionのカラムを活用しましょう。
* キャンペーン名とキャンペーン ID ディメンションを使用したユニークユーザー数の計算：キャンペーン名の細分性を無視できる場合は、キャンペーン ID のユニークカウントを合計すれば指標は正確です。
* キャンペーン階層の項目を使用することでデータを集計可能です。
* revenue\_usd (USD換算の収益金額) は、イベント発生日のUSDの為替レートを使用して計算されているので注意してください。
* 広告収益イベントは利用可能な場合にはデータに含まれますが、更新されるまでに最大3日間の遅れが生じることがあります。

**一般的な考慮事項**

すべてのアプリのデータを1つのファイルにまとめて提供します。App IDの項目を使用してアプリ毎にデータを分割するか、Data Locker上でアプリ毎に分割するよう設定してください。

</Accordion>

<div id="use-cases" />

<Accordion title="使用事例">

以下は、BI開発者が Data Lockerを介して抽出できるコホートデータの一般的で実用的なアプリケーションの例です。各例は、SQLステートメントとサンプルの Excel ビジュアルで示されています。

#### **1.リテンションの計算**

次の例では、次のことを行います：

* 1日目と7日目のリテンション、およびキャンペーンと広告ごとのインストールの合計数を計算します。
* コンバージョンイベントごとのイベント数を合計するには、`event_name` を `af_conversion` でフィルターしてください。
* 具体的には、`conversion_type IN (install, install_unified)` となるようにデータをフィルターして、Unified（統合）レポートでユーザー獲得キャンペーンを分析します。

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

#### **2.複数のアプリ内イベントのARPUを計算する**

次の例では、次のことを行います：

* キャンペーンごとに複数のアプリ内イベントのARPUを計算します。
* リターゲティングキャンペーン分析する場合は、`conversion_type=re-engagement` および `conversion_type=re-attribution` とデータをフィルターします。
* コンバージョンイベントごとのイベント数を合計するには、`event_name` を `af_conversion` とフィルターしてください。
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
| 07315466 | Re-attribution | 7.41 | 6.79 | 5.29 |

#### **3.特定のコホート日のアプリ内イベントコンバージョン率を計算する**

次の例では、次のことを行います：

* 複数のディメンション（この場合は、コンバージョン日、地域、キャンペーン、広告、サイトID）の Day 0 アプリ内イベントのコンバージョン率を計算します。
* 統合データ（UAとリターゲティングキャンペーンの両方）を分析する場合は、`is_primary_attribution=true` とフィルターします。
* コンバージョンイベントごとのイベント数を合計するには `event_name` を `af_conversion` とフィルターします。
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

| コンバージョン日 | 国 | キャンペーンID | 広告ID | サイトID | Day 0 af\_complete\_tutorial |
| --- | --- | --- | --- | --- | --- |
| 2022-11-07 | US | 12345678 | 123456 | site\_123 | 45% |
| 2022-11-05 | UK | 98765432 | null | site\_654 | 70% |
| 2022-10-31 | KR | 07315466 | null | null | 63% |

#### **4.日次インストールの計算**

次の例では、次のことを行います：

* アプリID、コンバージョン日、メディアソース、イベント名、コンバージョンタイプごとのインストール数を計算します。
* 全体レポートで、`conversion_type` を`install` または `install_unified` に設定して、ユーザー獲得インストール（リターゲティングではない）を表示するようにデータをフィルターします。
* `event_name` を `af_conversion` に設定してインストールを合計します。

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

#### **5.Facebook広告からの収益を計算する**

次の例では、次のことを行います：

* Facebookからの3日目の収益をコンバージョン日とアプリIDで計算します。
* `media_source='Facebook Ads'` とフィルターしてFacebookデータを分析します。
* データ処理の負荷を最小限に抑えるには、`days_post_attribution` を必要最低限の値（この場合は3）に設定します。

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

#### **6.最大365コホート日のASAキーワードIDごとのARPU計算**

次の例では、次のことを行います：

* キーワードIDごとの Apple Search Ads経由のコホート365日目までの ARPUを計算します。
* `media_source='Apple Search Ads'`をフィルターしてApple Search Adsデータを分析します。
* コンバージョンイベントごとのイベント数を合計するには、`event_name` を `af_conversion`とフィルターします。

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
* `conversion_type='install'` とフィルターします。
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

| 国 | 総コンバージョン数 | ARPU 7日目（2023年7月11日） | ARPU 7日目（2023年7月12日） | ARPU 7日目（2023年7月13日） | ARPU 7日目（2023年7月14日） | ARPU 7日目（2023年7月15日） | ARPU 7日目（2023年7月16日） |
| --- | --- | --- | --- | --- | --- | --- | --- |
| South Korea | 120,660 | $7,798.89 | $6,997.37 | $8,258.95 | $9,050.21 | $10,018.04 | $13,765.73 |
| Canada | 35,099 | $64,867.84 | $7,050.19 | $5,656.33 | $9,553.75 | $8,632.41 | $11,308.06 |
| Chile | 26,750 | $48,160.02 | $21,249.55 | $22,584.57 | $24,033.07 | $31,118.91 | $41,145.22 |

</Accordion>

## 追加情報

<div id="traits-and-limitations" />

<Accordion title="特性と制限">

| 特性 |  |
| --- | --- |
| コストデータ | <ul><li>利用できません。<Anchor target="_blank" href="/marketers/ja/docs/set-up-and-use-roi360-cost-etl-reports">コストETLを使用</Anchor>します。</li><li><Anchor target="_blank" href="/marketers/ja/docs/combine-cost-etl-and-cohort-reports-via-data-locker">コストETLとコホートレポートを組み合わせる方法</Anchor>も参照してください。</li></ul> |
| キャンペーン名の変更 | いいえ： |
| データ更新頻度 | UTCベースで毎日更新されます。レポートは、翌日の日本時間19時（UTC時間 10:00）までにレポート日の Data Locker日時 (dt) フォルダーに格納されます。 |
| 広告収益 | <ul><li>利用可能</li><li>af\_ad\_revenue イベントの場合、ユニークユーザー数の指標は 2022年10月5日から 2023年2月16日までの日付には使用できません。</li></ul> |
| 通貨 | 行ごとに、USDとアプリ個別の通貨設定のデータが確認可能です。 |
| タイムゾーン | <ul><li>UTC</li><li>アプリ固有のタイムゾーンは、<Anchor target="_blank" href="/marketers/ja/docs/advanced-aggregated-reports-in-data-locker">アドバンス集計コホートレポート（タイムゾーンバージョン）</Anchor>で確認できます。</li></ul> |
| オーガニックデータ | 利用可能 |
| コンバージョン (インストール、リアトリビューション、リエンゲージメント) 後の日数 | <ul><li>インストール後 365日間のデータが利用可能です。</li><li><Anchor target="_blank" href="/marketers/ja/docs/advanced-aggregated-reports-in-data-locker">アドバンス集計レポート</Anchor>で1,095日間が利用可能です。</li></ul> |
| 代理店の運用媒体の開示設定 | <ul><li>サポート対象</li><li>X広告とMeta広告のデータは常に開示されています。</li></ul> |
| アプリ毎のデータ分割 | サポート対象 |
| SKAN計測データ | 含まれていません。つまり、iOSのポストバックで提供されるデータです。 |
| 再インストール | <ul><li>再インストール後のイベントが未アトリビューションのオーガニックイベントと見なされる場合：<ul><li>2024年5月26日現在のみ含まれています。<Anchor target="_blank" href="/marketers/ja/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">詳細はこちら</Anchor></li><li>インストール時間は<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor>フィールドに基づいています。</li><li>ユニークユーザーやリテンション測定にはカウントされません。</li></ul></li><li>再インストール後のイベントが最初のインストールに起因する場合、常に含まれます。<Anchor target="_blank" href="/marketers/ja/docs/unique-users">詳細はこちら</Anchor></li></ul> |

</Accordion>

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/combine-cost-etl-and-cohort-reports-via-data-locker">コストETLとコホートレポートを組み合わせる</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/cohort-and-retention-dashboard">コホートダッシュボード</Anchor>

<div data-zendesk-anchors="cohort-analytics-in-data-locker=data-locker%E3%81%A7%E3%81%AE%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E5%88%86%E6%9E%90 01H7WG3CA1DDAN79D1PBPE0RJ3=data-locker%E3%81%A7%E3%81%AE%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E5%88%86%E6%9E%90 01H7WG3CA1ZMNTGZ5B8FNXNC4A=enable-data-locker 01H7WG3CA179D6VCWYPCJ1G49M=facts 01H7WG3CA1R3PZCKSGWC90E7RC=report-structure dimensions=%E3%83%87%E3%82%A3%E3%83%A1%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3 01H7WG3CA14PQ2PJ58FX8TE6ZH=%E3%83%87%E3%82%A3%E3%83%A1%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3 metrics=%E6%8C%87%E6%A8%99 01H7WG3CA24VQKFVP99S82GCXZ=%E6%8C%87%E6%A8%99 01H7WG3CA2C3HV8YT5ZMP9E0QY=bi-developer-considerations 01H7WG3CA2YF03SC6RBMCJYYVX=use-cases 1-calculating-retention=1%E3%83%AA%E3%83%86%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E8%A8%88%E7%AE%97 h_01HMTZ0DZWN54HBQ0ZTY0VFNFM=1%E3%83%AA%E3%83%86%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E8%A8%88%E7%AE%97 2-calculating-arpu-of-multiple-inapp-events=2%E8%A4%87%E6%95%B0%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AEarpu%E3%82%92%E8%A8%88%E7%AE%97%E3%81%99%E3%82%8B h_01HMTZ0DZWHZ77RYWYAQEJV7X5=2%E8%A4%87%E6%95%B0%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AEarpu%E3%82%92%E8%A8%88%E7%AE%97%E3%81%99%E3%82%8B 3-calculating-inapp-event-conversion-rate-for-a-specific-cohort-day=3%E7%89%B9%E5%AE%9A%E3%81%AE%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E6%97%A5%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E7%8E%87%E3%82%92%E8%A8%88%E7%AE%97%E3%81%99%E3%82%8B h_01HMTZ0DZW7VA6T6MQY7BY1JZT=3%E7%89%B9%E5%AE%9A%E3%81%AE%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E6%97%A5%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E7%8E%87%E3%82%92%E8%A8%88%E7%AE%97%E3%81%99%E3%82%8B 4-calculating-daily-installs=4%E6%97%A5%E6%AC%A1%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E8%A8%88%E7%AE%97 h_01HMTZ0DZWARZFAQ9R4VF56YN3=4%E6%97%A5%E6%AC%A1%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E8%A8%88%E7%AE%97 5-calculating-revenue-from-facebook-ads=5facebook%E5%BA%83%E5%91%8A%E3%81%8B%E3%82%89%E3%81%AE%E5%8F%8E%E7%9B%8A%E3%82%92%E8%A8%88%E7%AE%97%E3%81%99%E3%82%8B h_01HMTZ0DZW74HWW6Z3VDWDMGRF=5facebook%E5%BA%83%E5%91%8A%E3%81%8B%E3%82%89%E3%81%AE%E5%8F%8E%E7%9B%8A%E3%82%92%E8%A8%88%E7%AE%97%E3%81%99%E3%82%8B 6-calculating-arpu-per-asa-keyword-id-for-up-to-365-cohort-days=6%E6%9C%80%E5%A4%A7365%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E6%97%A5%E3%81%AEasa%E3%82%AD%E3%83%BC%E3%83%AF%E3%83%BC%E3%83%89id%E3%81%94%E3%81%A8%E3%81%AEarpu%E8%A8%88%E7%AE%97 h_01HMTZ0DZWSN83V0TEHVM2H5XS=6%E6%9C%80%E5%A4%A7365%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E6%97%A5%E3%81%AEasa%E3%82%AD%E3%83%BC%E3%83%AF%E3%83%BC%E3%83%89id%E3%81%94%E3%81%A8%E3%81%AEarpu%E8%A8%88%E7%AE%97 calculating-arpu-days-0-7-by-attribution-time-per-geo=7%E5%9C%B0%E5%9F%9F%E3%81%94%E3%81%A8%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%99%82%E9%96%93%E3%81%AB%E3%82%88%E3%82%8Barpu-7%E6%97%A5%E7%9B%AE%E3%81%AE%E8%A8%88%E7%AE%97 01H8XYTJVQ1YFBHPWVPP9D7MJ8=7%E5%9C%B0%E5%9F%9F%E3%81%94%E3%81%A8%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%99%82%E9%96%93%E3%81%AB%E3%82%88%E3%82%8Barpu-7%E6%97%A5%E7%9B%AE%E3%81%AE%E8%A8%88%E7%AE%97 additional-information=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 01H7WG3CA255TG9HW150RW1QTX=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 01H7WG3CA2Y59D2EVMN3YFFY1W=traits-and-limitations h_01HDNZ8A0QH74CGSEG6TKKARJP=%E5%8F%82%E7%85%A7" />
