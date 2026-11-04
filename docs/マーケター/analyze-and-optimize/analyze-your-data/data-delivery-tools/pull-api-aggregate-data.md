---
title: Pull API aggregated data（集計データのPull API）
metadata:
  keywords:
    - Performance
    - raw data
    - Pull API
    - Reports
    - API
    - Parameters
    - API Policy
    - Advertisers
    - facebook rawdata
    - facebook raw data
    - Developers
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2013-04-24T15:08:25Z'
  edited_at: '2026-10-14T09:38:54Z'
  id: 207034346
  locale: ja
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/ja/articles/207034346
---
> **概要：** 概要： 集計データ用のPull APIを使用して、AppsFlyerの集計レポートをCSVファイルで取得します。

[![PullAPIAverage_us-en.png](https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png)](https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png)

<div id="looking-for-pull-api-raw-data" />

> 👍 **Pull API ローデータをお探しですか？**
>
> <Anchor target="_blank" href="/marketers/ja/docs/pull-api-raw-data">こちらの記事 - Pull API ローデータ</Anchor>をご覧ください。

<div id="pull-api-aggregate-data" />

## Pull API aggregated data（集計データのPull API）

* Pull APIを使用すると、ユーザー獲得 (UA) とリターゲティングの集計データレポートを CSV ファイルで取得できます。
* <Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#data-freshness-rates-and-timezone-support">データ更新頻度</Anchor> は、「データエクスポート」画面および「オーバービュー」ダッシュボード画面の同等レポートと同じです。コストデータを提供するパートナーによっては、数時間の遅延でコストが更新される可能性があることを考慮してください。
* 利用可能なオプションでフィルター:
* Pull APIの追加機能は次のとおりです：
  * アトリビューションタッチタイプを追加
  * タイムゾーンを選択

<div id="aggregate-performance-reports-available-via-pull-api" />

#### Pull APIで利用できる集計パフォーマンスレポート

<table><tbody><tr><th>カテゴリ</th><th> UA（非オーガニックインストール）</th><th>リターゲティング</th></tr><tr><td>パートナー（メディアソース）</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>パートナー（日付別）</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>毎日</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>地理</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>Geo by Date Report（地域/日付別レポート）</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="3"></td></tr></tbody></table>

<div id="using-pull-api-aggregate-data" />

<Accordion title="Pull API集計データの使用">

**Pull API 集計データを使用する：**

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) APIトークンを取得します。管理者はトークンを取得する必要があります。
2. 認証ヘッダーで使用するためにAPIトークンをデベロッパーに渡します。
3. 次のセクションで説明するように、APIコールを行うときに入力する[パラメーター](/docs/pull-api-aggregate-data#parameters) を開発者へ渡してください。パラメーターは、レポートが何に焦点を当て、どのように編成されるかを決定し、レポートの時間枠を定義します。
4. AppsFlyer公式デベロッパーハブの <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-11">Pull API 集計データの指示</Anchor> に従うように開発者に伝えてください。

</Accordion>

<div id="parameters" />

<Accordion title="パラメーター">

| パラメータ | 説明 |
| --- | --- |
| app\_id | アプリID |
| 開始 | <ul><li>日付範囲はおよびパラメータで構成されています。</li><li>形式：</li><li>例：2010-01-01</li></ul> |
| 終了 | 終了日。`fromfrom`について |
| media\_source | 特定のメディアソースに制限（フィルタ）するために使用します。<ul><li>例：`media_source=facebook`</li></ul> |
| attribution\_touch\_type | このパラメーターを例に示すように設定して、[ビュースルーアトリビューション](/docs/pull-api-aggregate-data) (VTA) のKPI を取得します。<br /><br />例：`attribution_touch_type=impression`<br /><br />クリック数、インプレッション数、コスト API など、一部のビュースルーKPI には値が関連付けられていないため、代わりにN/Aという値が表示されます。 |
| currency | 収益とコストの通貨<br /><br />集計Pull APIレポートは常にアプリ固有の通貨を使用します。 |
| リターゲティング | リターゲティングのコンバージョンデータを取得します。<ul><li>[デフォルト] false の場合、ユーザー獲得データ (UA) キャンペーンが返されます。</li><li>true の場合は、リターゲティングコンバージョンデータが返されます。</li><li>**例**:</li></ul> |
| timezone | [デフォルト] データはUTCが使用されます。<ul><li>テンプレートURIには、アプリケーション固有のタイムゾーンに設定されたタイムゾーンパラメーターが入力されます。</li><li>[デフォルト]パラメーターが送信されない場合は、UTC を使用してデータが返されます。</li></ul>タイムゾーンの選択に関する注意点<ul><li>Joda-Timeタイムゾーンは、夏時間が考慮されます。</li><li>2. Joda-Time値は、アプリ設定ページと一致にしてください。</li><li>選択したタイムゾーンのデータを取得することは、タイムゾーン設定が行われた日付から可能です。変更日以前のデータでは、タイムゾーンとしてUTCが使用されます。</li></ul> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特性と制限">

| 特性 | 備考 |
| --- | --- |
| 必要なAPIトークンタイプ | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens">V2.0トークン</Anchor> |
| アドネットワークのアクセス | いいえ |
| 代理店によるデータアクセス | Y |
| 代理店の運用媒体の開示設定 | Y |
| App-specific currency | Y |
| アプリ固有のタイムゾーン | Y |
| コスト | コストデータはユーザー獲得キャンペーンのみで、リターゲティングまたはアクティブではない（インストールが無い）キャンペーンは対象外です。 |
| データ更新頻度 | <Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">継続的</Anchor> |
| 過去データ | 5年 |
| 非オーガニックデータ | Y |
| オーガニックデータ | Y |
| レート制限 | <Anchor target="_blank" href="/marketers/ja/docs/report-generation-quotas-rate-limitations">制限事項</Anchor> |
| サイズ制限 | <ul><li>APIコールは、最大20万行のデータを返します。<ul><li>もしレポートにちょうど20万行含まれている場合、追加の行のデータが不足していると考えてください。</li><li>時刻を含むfrom/toパラメータを使用して、複数のAPIコールに分けてデータを取得してください。</li></ul></li></ul> |
| キャンペーン名の変更 | Pull APIレポートはキャンペーン名の変更をサポートしていません。 |

</Accordion>

<div id="see-also" />

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/aggregated-and-analytics-reporting-overview">集計レポートの説明と例</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/aggregated-and-analytics-reporting-overview">集計データのレポーティングに適したツールの選択</Anchor>

<div data-zendesk-anchors="h_01HE0YP82966QHRAEW979ABCTP=pull-api-%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E3%81%8A%E6%8E%A2%E3%81%97%E3%81%A7%E3%81%99%E3%81%8B pull-api-aggregate-data=pull-api-aggregated-data%E9%9B%86%E8%A8%88%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AEpull-api h_01HE0YP829WD5TDFHTPYAV30QN=pull-api-aggregated-data%E9%9B%86%E8%A8%88%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AEpull-api aggregate-performance-reports-available-via-pull-api=pull-api%E3%81%A7%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%82%8B%E9%9B%86%E8%A8%88%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HE0YP829EQ7N6CST352X917H=pull-api%E3%81%A7%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%82%8B%E9%9B%86%E8%A8%88%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HE0YP82954F1ACVR2K4AFD5W=using-pull-api-aggregate-data h_01HE0YP8292131Q2561A4E1GYZ=parameters h_01HE0YP829ZPJAPHPDR9H4HMRT=traits-and-limitations h_01HE0Y2KTXS06WHN57MQ91AD09=%E5%8F%82%E7%85%A7" />
