---
title: ローデータのコンテンツ制限—メディアソースまたはユーザー識別子
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
  created_at: '2020-03-23T08:29:01Z'
  edited_at: '2026-10-14T09:33:46Z'
  id: 360006868017
  locale: ja
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ja/articles/360006868017
---
> **概要：** 一部のローデータレポートのデータ項目は、プライバシーの制限により制限されています。また、サードパーティのプラットフォームとポストバックを共有する際、パートナーがメディアソースの再編集を要求する場合もあります。この記事では、制限事項とその影響について説明します。

<div id="raw-data-restriction" />

## ローデータの制限

AppsFlyerは、広告主の<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">AAP（高プライバシー一括設定）</Anchor>設定またはデータを提供する広告媒体のデータ共有ポリシーに基づいて、特定のローデータレポートフィールドへのアクセスを制限します。これらの制限は、レポートの種類や制限の理由によって異なります。

<div id="media-source-restrictions" />

### メディアソースの制限

コンバージョン、クリック、インプレッションにおけるメディアソースごとの制限について以下の表をご覧ください。

<div id="note" />

> 📘 **注記：**
>
> * 集計レポートとアナリティクスのデータは、制限なくご利用いただけます。ただし、すべてのポストバックとデバイスレベルのレポートは、以下に示す制限の対象となります。
> * <Anchor target="_blank" href="/marketers/ja/docs/discrepancies-between-appsflyer-and-third-party-platforms#サードパーティプラットフォームへのポストバックの制限">サードパーティプラットフォームでのポストバックの制限：</Anchor>
>   * 以下の表に記載されている制限は、分析やマーケティングプラットフォームなどのサードパーティプラットフォームに送信されるポストバックに含まれるイベントに適用されます。
>   * 他のイベントには、さらにポストバックの制限が適用されることがあります

| メディアソース | アトリビューションタイプの制限 |
| --- | --- |
| <span id="amazon-ads"></span>Amazon Ads | Amazon Adsのローデータは、AppsFlyerプラットフォームでは制限されています。その結果、メディアソースは "restricted "とレポートされ、キャンペーンの詳細は空白となります。<br /><br />他のSRNと同様に、Amazon Adsのクリックとインプレッションはローデータレポートに含まれません。 |
| <span id="meta-ads"></span>Meta広告 | <ul><li>クリックスルーとビュースルーのアトリビューションデータが制限されています。</li><li>AEMディープリンクソリューション（iOS）からのデータ、およびGoogle PlayインストールリファラーとMetaインストールリファラー（Androidのみ）からのデータは、デバイスレベルのレポートで制限なく利用できます。</li></ul><ul><li>他のSRNと同様に、Meta広告のクリックとインプレッションはローデータレポートに含まれません。</li></ul> |
| <span id="pinterest"></span>Pinterest | <ul><li>クリックスルーとビュースルーのアトリビューションデータが制限されています。</li><li>Pinterestのクリックとインプレッションはローデータレポートには含まれません。</li></ul> |
| <span id="reddit"></span>Reddit | <ul><li>2024年10月22日以降、RedditのローデータはAppsFlyerプラットフォーム上で制限されます。その結果、ローデータにおいてメディアソースは "restricted "とレポートされます。Pinterestのクリックとインプレッションはローデータレポートには含まれません。</li></ul> |
| <span id="roku-oneview"></span>Roku OneView | <ul><li>Roku OneViewからのクリックとインプレッションは、ローデータレポートには含まれません。</li></ul> |
| <span id="samsung-dsp"></span>Samsung DSP | <ul><li>Samsung DSPのクリックとインプレッションは、ローデータレポートには含まれません。</li></ul> |
| <span id="snapchat"></span>Snapchat | <ul><li>2023年3月1日以降、Snapchatのアンインストールはローデータレポートに含まれません。</li><li>ビュースルーCVのローデータが制限されています。以下項目はローデータ配信ツールには含まれません：<ul><li>Media source (snapchat\_int)</li><li>チャネル</li><li>Attributed touch type (impression)</li><li>Attributed touch time (日付のみ "dd/mm/yyyy" と記録されます)</li><li>キャンペーン名の項目は "*restricted*"と記録されます。</li></ul></li><li>Pinterestのクリックとインプレッションはローデータレポートには含まれません。</li></ul> |
| <span id="tiktok-for-business"></span>TikTok for Business | <ul><li>Media source (bytedanceglobal\_int および tiktokglobal\_int)<ul><li>Channel</li><li>Attributed touch type (impression)</li><li>Attributed touch time (日付のみ "dd/mm/yyyy" と記録されます)</li><li>キャンペーン名の項目は "*restricted*"と記録されます。</li></ul></li><li>bytedanceglobal\_intからのインプレッションはローデータレポートには含まれません。</li><li>tiktokglobal\_intからのData Locker経由のクリックとインプレッションのローデータレポートは制限されています。</li></ul> |
| <span id="x-ads-formerly-twitter"></span>X Ads（旧：Twitter Ads） | <ul><li>X Adsでは、AppsFlyerプラットフォームでローデータを利用できない場合があります。このような場合、イベントはローデータレポートには表示されません。</li><li>X Adsのクリックとインプレッションはローデータレポートには含まれません。</li></ul> |

<div id="raw-data-context" />

### ローデータのコンテキスト

ローデータの項目レベルの制限は、次の表に示すデータのコンテキストによって異なります。

| 制限タイプ | 影響があるレポート |
| --- | --- |
| [メディアソースの制限：](/docs/about-raw-data-identifier-restrictions#メディアソースの制限)ユーザーがどこから来たか | <ul><li>アトリビューション：インストール、リターゲティングコンバージョン、アンインストール</li><li>アプリ内イベント、セッション</li><li>Protect360レポート</li></ul> |
| 完全に制限 | <ul><li>クリック</li><li>インプレッション</li><li>ブロック済みクリック（Protect360）</li></ul> |

**ローデータの取得ツール**

AppsFlyerのユーザーレベルの計測データは、次のローデータ配信ツールで利用できます：

* Data Locker
* Pull APIのローデータ
* Push API
* 管理画面のローデータ出力画面
* アドネットワークへのポストバック
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">コンバージョンデータ取得 (GCD) API</Anchor>（クライアント側でのユーザーレベルデータAPI）

<div id="unavailable-attribution-fields" />

<Accordion title="利用できないアトリビューション項目">

次の項目は、メディアソースが制限されている場合は使用できません：

| 項目 | API名 |
| --- | --- |
| Ad | af\_ad |
| Ad ID | af\_ad\_id |
| Ad type | af\_ad\_type |
| Adset | af\_adset |
| Adset ID | af\_adset\_id |
| Attribution lookback window | af\_attribution\_lookback |
| Campaign ID | af\_c\_id |
| Channel | af\_channel |
| Cost Currency | af\_cost\_currency |
| Cost Model | af\_cost\_model |
| Cost Value | af\_cost\_value |
| Keywords | af\_keywords |
| Partner | af\_prt |
| Site ID | af\_siteid |
| Subsite ID | af\_sub\_siteid |
| Sub param [n] (n=1-5) | af\_sub[n] (n=1-5) |
| Attributed touch time | attributed\_touch\_time |
| Attributed touch type | attributed\_touch\_type |
| Campaign | campaign |
| Contributor [n] media source (n=1-3) | contributor[n]\_media\_source (n=1-3) |
| Contributor [n] partner (n=1-3) | contributor[n]\_af\_prt (n=1-3) |
| Contributor [n] campaign (n=1-3) | contributor[n]\_campaign (n=1-3) |
| Contributor [n] match type (n=1-3) | contributor[n]\_match\_type (n=1-3) |
| Contributor [n] touch time (n=1-3) | contributor[n]\_touch\_time (n=1-3) |
| Contributor [n] touch type (n=1-3) | contributor[n]\_touch\_type (n=1-3) |
| Deeplink URL | deeplink\_url |
| HTTP referrer | http\_referrer |
| Install app store | install\_app\_store |
| Keyword ID | keyword\_id |
| Keyword match type | keyword\_match\_type |
| Match type | match\_type |
| Network account ID | network\_account\_id |
| Original URL | original\_url |
| Re-engagement window | af\_reengagement\_window |
| Store product page | store\_product\_page |

</Accordion>

<div id="identifier-restriction" />

<Accordion title="識別子の制限">

識別子の制限が適用される場合、ローデータレポートで使用できる項目は、次の表に示す項目のみです。

| API名 |
| --- |
| <span id="event_time"></span>event\_time |
| <span id="event_name"></span>event\_name |
| <span id="event_revenue"></span>event\_revenue |
| <span id="event_revenue_currency"></span>event\_revenue\_currency |
| <span id="event_revenue_usd"></span>event\_revenue\_usd |
| <span id="af_cost_model"></span>af\_cost\_model |
| <span id="af_cost_value"></span>af\_cost\_value |
| <span id="af_cost_currency"></span>af\_cost\_currency |
| <span id="event_source"></span>event\_source |
| <span id="media_source"></span>media\_source |
| <span id="af_channel"></span>af\_channel |
| <span id="campaign"></span>campaign |
| <span id="af_c_id"></span>af\_c\_id |
| <span id="af_adset"></span>af\_adset |
| <span id="af_adset_id"></span>af\_adset\_id |
| <span id="af_ad"></span>af\_ad |
| <span id="af_ad_id"></span>af\_ad\_id |
| <span id="af_ad_type"></span>af\_ad\_type |
| <span id="af_siteid"></span>af\_siteid |
| <span id="af_sub_siteid"></span>af\_sub\_siteid |
| <span id="app_id"></span>app\_id |
| <span id="app_name"></span>app\_name |
| <span id="bundle_id"></span>bundle\_id |
| <span id="is_retargeting"></span>is\_retargeting |
| <span id="retargeting_conversion_type"></span>retargeting\_conversion\_type |
| <span id="is_primary_attribution"></span>is\_primary\_attribution |
| <span id="af_attribution_lookback"></span>af\_attribution\_lookback |
| <span id="af_reengagement_window"></span>af\_reengagement\_window |
| <span id="country_code"></span>country\_code |
| <span id="blocked_reason"></span>blocked\_reason |
| <span id="blocked_reason_value"></span>blocked\_reason\_value |
| <span id="blocked_reason_rule"></span>blocked\_reason\_rule |
| <span id="blocked_sub_reason"></span>blocked\_sub\_reason |
| <span id="platform"></span>platform |
| <span id="is_paid_media"></span>is\_paid\_media |

</Accordion>

<div id="faq" />

## よくある質問

<div id="what-events-are-restricted" />

<Accordion title="どのようなイベントが制限されていますか？">

制限されたイベントには、 [上の表](/docs/about-raw-data-identifier-restrictions#メディアソースの制限)のとおり、コンバージョン（インストールとリエンゲージメント）および制限されたアドネットワークがアトリビューションされる関連アプリ内イベントが含まれる場合があります。

</Accordion>

<div id="how-does-the-restricted-media-source-impact-raw-data-reports" />

<Accordion title="「restricted」メディアソースがローデータレポートに与える影響は？">

* *media source* 項目に *restricted* と入力されます。
* この記事に記載されている計測項目には、空白または *null* のいずれかが入力されます。

**レポートの例：** <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vScXJznEex0WwdCy78Bm8LtrhbCk1jNy14O_t7etrq5ab5v4CIEiInfFD4B1EsZCE-_w-dVRAxl_cu4/pub?output=csv">制限ありのメディアソースのインストールローデータサンプルCSV</Anchor> /その他のローデータレポートも同様に入力されます。

</Accordion>

<div id="how-does-the-restricted-media-source-impact-postbacks-sent-to-partners" />

<div id="what-is-the-impact-on-postbacks-to-partners-when-the-media-source-is-restricted" />

<Accordion title="制限されたメディアソースは、パートナーに送信されるポストバックにどのような影響を与えますか？">

パートナーに送信されるポストバックにアトリビューション項目は含まれません。

</Accordion>

<div id="how-do-restricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="制限されたイベントは、サードパーティプラットフォームへのポストバックにどのような影響を与えますか？">

[上の表](#メディアソースの制限)にあるアトリビューションされたアドネットワークへのポストバックは、サードパーティプラットフォームに送信されません。

</Accordion>

<div id="do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="制限されないイベントは、サードパーティプラットフォームに影響を与えますか？">

<Anchor target="_blank" href="/marketers/ja/docs/discrepancies-between-appsflyer-and-third-party-platforms#サードパーティプラットフォームへのポストバックの制限">サードパーティプラットフォームに送信される非制限イベントのポストバックには、メディアソースが含まれないケース</Anchor>があります。つまり、アトリビューションはオーガニックとしてクレジットされます。

</Accordion>

<div id="what-about-the-data-of-assists-that-form-part-of-the-attribution" />

<Accordion title="計測の一部であるアシストデータへの影響は？">

アシストに関するデータは、計測データとみなされ利用できません。

</Accordion>

<div id="see-also" />

> 📄 **参照：**
>
> <Anchor target="_blank" href="/marketers/ja/docs/user-level-data-retention">ユーザーレベルのデータ保持</Anchor>

<div data-zendesk-anchors="raw-data-restriction=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%B6%E9%99%90 01H7WQHTV9RM2JF2BV45XF626H=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%B6%E9%99%90 media-source-restrictions=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E5%88%B6%E9%99%90 01H7WQHTV9HJEHHH1N8VN6APX6=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E5%88%B6%E9%99%90 01H7WQHTV90YFRP3Z9AEP7ACRD=%E6%B3%A8%E8%A8%98 raw-data-context=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%86%E3%82%AD%E3%82%B9%E3%83%88 01H7WQHTVA8H9FTBJ1FB6BJQ2A=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%86%E3%82%AD%E3%82%B9%E3%83%88 01H7WQHTVA0XP6B2H95EEM7EYD=unavailable-attribution-fields 01H7WQHTVA7ERWW1PC3DF5H0NP=identifier-restriction faq=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F 01H7WQHTVA5439QPE6GNXNKJ63=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HDBND48E05P1WV51ZJGD072N=what-events-are-restricted 01H7WQHTVAHCK7QDZ5P25YRQ2D=how-does-the-restricted-media-source-impact-raw-data-reports 01H7WQHTVABKATP6B6XN4NRC54=what-is-the-impact-on-postbacks-to-partners-when-the-media-source-is-restricted h_01HDBND48EDTAFBFXTADGWJADM=how-do-restricted-events-impact-postbacks-to-thirdparty-platforms h_01HE5TK3WSNBPM6W5D1Y9S6PDX=do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms 01H7WQHTVA60PWZ017WJMRTKVP=what-about-the-data-of-assists-that-form-part-of-the-attribution h_01HE7SCVN3VJ4Y6KF2QZSNBEMZ=%E5%8F%82%E7%85%A7" />
