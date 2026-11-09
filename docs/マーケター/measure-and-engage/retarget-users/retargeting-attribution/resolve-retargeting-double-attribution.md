---
title: リターゲティングの二重計測
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2020-12-13T07:35:18Z'
  edited_at: '2026-10-14T09:30:26Z'
  id: 360016371077
  locale: ja
  section: Retargeting attribution
  section_id: 6551326229265
  url: https://support.appsflyer.com/hc/ja/articles/360016371077
---
> **概要：** リターゲティングキャンペーンのリエンゲージメント期間中のパフォーマンスにおいて、アプリ内イベントとセッションデータは、ユーザー獲得（新規インストール）とリターゲティングメディアソースの両方に紐づきます。

<Image align="center" alt="" src="https://files.readme.io/fce514999471aa7bfced06fa0e1c7d6fa7363a8d30119bd20d0b5d7e56eb1f7d-9479192551825.png" />

<div id="overview" />

## 概要

リターゲティングキャンペーンにおけるダブルアトリビューションとは、アプリ内イベントがオリジナルインストールの動機となるメディアソースと、リエンゲージメントやリアトリビューションイベントの動機となるメディアソースの両方に紐づくことを意味します。

ダブルアトリビューションの適用は、リエンゲージメントとリアトリビューションで異なります。

* **リエンゲージメントCV：** すべてのリエンゲージメントCVにダブルアトリビューションが適用されます。
* **リアトリビューションCV：** ダブルアトリビューションは、「初回インストールメディアソースへの紐付け」設定がオンのアプリに適用されます。「初回インストールメディアソースへの紐付け」設定がオンでないアプリでは、ダブルアトリビューションは適用されません。（再インストールによって生成されたすべてのアプリ内イベントは、オリジナルの初回インストールに紐付けられます。「初回インストールメディアソースへの紐付け」設定の詳細については、「<Anchor target="_blank" href="/marketers/ja/docs/measure-reinstalls#attributed-to-the-first-install">初回インストールへの紐付け</Anchor>」を参照してください。）AppsFlyerに連絡して、既存のアプリを「初回インストールメディアソースへの紐付け」設定に移行することをお勧めします。

下の図では、新規インストールに紐づくイベントは「green\_network」に紐づきます。ここで、1つのイベントデータが生成されます。対照的に、「blue\_network」のリターゲティング広告に接触後に、2つのイベントデータが生成されます。各イベントの紐付け先：

* blue\_network：リエンゲージメントCVを促したプライマリメディアソース
* green\_network：元のインストールを促したセカンダリメディアソース

さらに詳しく説明するために、以下の表ではリエンゲージメント期間前、期間中、および期間後に、アプリ内イベントの成果が紐づけられるシナリオを示しています。表では、重複イベントを特定するために使用するローデータの項目を示しています。

* is\_primary\_attribution：trueの場合、メディアソースはプライマリメディアソースである
* context：以下のいずれかの項目を使用してください -
  * [ベストプラクティス] **conversion\_type**： install もしくは re-engagement
  * is\_retargeting：true の場合、データはリターゲティングキャンペーンのものです。

<div id="attribution-relative-to-the-re-engagement-window" />

#### リエンゲージメント期間における計測内容

| メディアソース | リエンゲージメント期間前 | リエンゲージメント期間中 | リエンゲージメント期間後 |
| --- | --- | --- | --- |
| ユーザー獲得 | プライマリ<br /><br />is\_primary\_attribution：True<br /><br />conversion\_type: install<br /><br />(is\_retargeting: False) | セカンダリ<br /><br />is\_primary\_attribution：False<br /><br />conversion\_type: re-engagement<br /><br />(is\_retargeting: False) | プライマリ<br /><br />is\_primary\_attribution：True<br /><br />conversion\_type: install<br /><br />(is\_retargeting: False) |
| リターゲティング | N/A | プライマリ<br /><br />is\_primary\_attribution：True<br /><br />conversion\_type: re-engagement<br /><br />(is\_retargeting: True) | N/A |

<div id="support-for-dashboard-view-types" />

## 管理画面での表示オプションの選択

ダッシュボードやコホートレポートの中には、統合、ユーザー獲得、リターゲティングといった複数の表示タイプオプションが含まれているものがあります。これらの表示タイプは、ローデータで使用されるものと同様のロジックを採用しています。

<Image align="center" alt="" src="https://files.readme.io/738bf91c1a12671b32b088993c43d4103498907a8bbe15821ddc53a0b071b876-32127949500305.png" />

<div id="data-filtering-by-view-type-using-the-conversion_type-field" />

#### conversion\_type の項目を使用した表示タイプ別のデータのフィルター

<table><thead><tr><th>表示タイプ</th><th>conversion_type</th><th>is_primary</th><th>アトリビューション</th></tr></thead><tbody><tr><td rowspan="2">ユーザー獲得</td><td>install</td><td>True もしくは Fales</td><td>UAイベントは新規獲得メディアソースに紐づきます</td></tr><tr><td>re-engagement</td><td>False</td><td>リターゲティングイベントは新規獲得メディアソースに紐づきます</td></tr><tr><td>リターゲティング</td><td>re-engagement または re-attribution</td><td>True</td><td>リターゲティングイベントはリターゲティングメディアソースに紐づきます</td></tr><tr><td>統合</td><td>install または re-engagement</td><td>True</td><td>全てのイベントはラストタッチのメディアソースに紐づきます</td></tr></tbody></table>

<div id="how-do-i-identify-double-attributed-retargeting-events-in-user-acquisition-in-app-reports" />

## ユーザー獲得に紐づくアプリ内イベントレポートで、リターゲティングイベントの重複計測を特定するにはどうすればよいですか？

**ユーザー獲得 アプリ内イベントレポート**では、重複計測としてレポートされるイベントは、次のように識別されます：

* is\_primary\_attribution 項目で、プライマリおよびセカンダリメディアソースを識別します。これが false の場合、成果は主にリターゲティングキャンペーンによるもので、新規獲得メディアソースはセカンダリであることを示しています。
* is\_retargeting 項目は、常に false となります。

リエンゲージメント期間中のリターゲティングアプリ内イベントレポートに紐づくデータは、次のように入力されます：

* is\_primary\_attribution 項目は、常に true となります。
* is\_retargeting 項目は、常に true です。
* つまり、リエンゲージメント期間中にイベントが発生しなかった場合、記録は一切残りません。

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01J8FJW0TE4DV5BFHGARS4ERT6=%E6%A6%82%E8%A6%81 attribution-relative-to-the-reengagement-window=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E6%9C%9F%E9%96%93%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E8%A8%88%E6%B8%AC%E5%86%85%E5%AE%B9 h_01J8FJW0TEJH716NXMM2RDN4J1=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E6%9C%9F%E9%96%93%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E8%A8%88%E6%B8%AC%E5%86%85%E5%AE%B9 support-for-dashboard-view-types=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%A7%E3%81%AE%E8%A1%A8%E7%A4%BA%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E9%81%B8%E6%8A%9E h_01J8FJW0TEDFGFPPYZEAREKY4Q=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%A7%E3%81%AE%E8%A1%A8%E7%A4%BA%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E9%81%B8%E6%8A%9E data-filtering-by-view-type-using-the-conversion_type-field=conversion_type-%E3%81%AE%E9%A0%85%E7%9B%AE%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9F%E8%A1%A8%E7%A4%BA%E3%82%BF%E3%82%A4%E3%83%97%E5%88%A5%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF%E3%83%BC h_01J8FJW0TETSV5X6D7NJ4EQHGC=conversion_type-%E3%81%AE%E9%A0%85%E7%9B%AE%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9F%E8%A1%A8%E7%A4%BA%E3%82%BF%E3%82%A4%E3%83%97%E5%88%A5%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF%E3%83%BC how-do-i-identify-doubleattributed-retargeting-events-in-user-acquisition-inapp-reports=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97%E3%81%AB%E7%B4%90%E3%81%A5%E3%81%8F%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%A7%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%87%8D%E8%A4%87%E8%A8%88%E6%B8%AC%E3%82%92%E7%89%B9%E5%AE%9A%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF%E3%81%A9%E3%81%86%E3%81%99%E3%82%8C%E3%81%B0%E3%82%88%E3%81%84%E3%81%A7%E3%81%99%E3%81%8B h_01J8FJW0TED4T9JN89PCRA3M9R=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97%E3%81%AB%E7%B4%90%E3%81%A5%E3%81%8F%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%A7%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%87%8D%E8%A4%87%E8%A8%88%E6%B8%AC%E3%82%92%E7%89%B9%E5%AE%9A%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF%E3%81%A9%E3%81%86%E3%81%99%E3%82%8C%E3%81%B0%E3%82%88%E3%81%84%E3%81%A7%E3%81%99%E3%81%8B" />
