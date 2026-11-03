---
title: コンバージョンデータの内容と発生パターン
metadata:
  keywords:
    - Conversion
    - Retargeting
    - Installs
    - Re-attribution
    - Re-engagement
    - Developers
    - SRN
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-12-31T13:05:33Z'
  edited_at: '2026-10-28T09:12:08Z'
  id: 360000726098
  locale: ja
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/ja/articles/360000726098
---
> **At a glance:** コンバージョンデータを活用すると、さまざまなコンバージョンの発生パターンの把握や、ユーザーに合わせた体験の提供などが可能です。

## 概要

このガイドでは、ユーザーのさまざまなコンバージョンの発生パターンと、それぞれに対応するコンバージョンデータの内容（ペイロード）を紹介します。

* [ユーザー獲得（UA）](#srn経由のユーザー獲得uaのコンバージョンデータ)
* [リターゲティング](#リターゲティングのコンバージョンデータ)

AppsFlyerでは、次のいずれかを通じてコンバージョンデータを取得できます。

* <Anchor target="_blank" href="/marketers/ja/docs/raw-data-export-page">ローデータレポート</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/push-api-streaming-raw-data">Push API</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">AppsFlyer SDK</Anchor>

データの正確さと取得までの時間の兼ね合いにより、同じデバイスIDのコンバージョンデータでも、APIによって内容が異なる場合があります。

### ノンオーガニックのコンバージョンデータに含まれるフィールド

#### 常に含まれるフィールド

次の表は、**ノンオーガニック**のコンバージョンデータに常に含まれるフィールドを示しています。コンバージョンの`media_source`にかかわらず、これらのフィールドが含まれます。

| 返却データのフィールド名 | ローデータのフィールド名 | 補足 |
| --- | --- | --- |
| `media_source` | メディアソース | 成果が紐づいた広告配信元です。アトリビューションリンクの`pid`パラメータに相当します。 |
| `install_time` | インストール日時 |  |
| `click_time` | 成果が紐づいた広告接触の日時 | クリックまたはインプレッションが発生した日時（UTC）です。 |
| `is_first_launch` | 該当なし | &lt;0>true0>, &lt;0>false0> |
| `af_status` | ローデータは、オーガニックとノンオーガニックの別々のレポートに分かれています。 | `"Non-organic"` |
| `af_siteid` | サイトID |  |
| `adgroup_id` | 広告ID |  |
| `adset` | 広告セット |  |
| `adset_id` | 広告セットID |  |
| `agency` | パートナー | `null`、または代理店名（代理店が運用するキャンペーンの場合） |
| `campaign` | キャンペーン |  |
| `campaign_id` | キャンペーンID |  |
| `http_referrer` | HTTPリファラ |  |
| `retargeting_conversion_type` | リターゲティングのコンバージョン種別 | "none"、またはretargeting\_conversion\_type |
| `af_sub[n] (n=1—5)` | サブパラメータ[n]（n=1～5） |  |

#### 条件によって含まれるフィールド

次の表のフィールドは、SRNが各イベントのデータをどのように設定するかによって、コンバージョンデータに含まれる場合があります。

<table><thead><tr><th>返却データのフィールド名</th><th>ローデータのフィールド名</th><th>補足</th><th> </th></tr></thead><tbody><tr><td><code>af_channel</code></td><td>チャネル</td><td><p>このパラメータに値を設定するSRN：</p><ul><li>AppLovin</li><li>Google広告</li><li>Meta広告</li><li>Snapchat</li><li>TikTok for Business</li><li>X広告</li></ul><p>例：Facebookの場合はInstagram、Googleの場合はYouTube </p></td><td> </td></tr><tr><td><code>orig_cost</code></td><td> </td><td>注意（1）</td><td> </td></tr><tr><td><code>cost_cents_USD</code></td><td> </td><td>注意（1）</td><td> </td></tr><tr><td><code>af_cpi</code></td><td> </td><td>注意（1）</td><td> </td></tr><tr><td colspan="4"><p><strong>注意</strong></p><p>（1）コストのフィールドには、アドネットワークから共有された値が設定されます。アドネットワークからAppsFlyerにコストデータを共有するには、<a href="./roi360-cost-aggregation-overview#ad-networks-supporting-cost-api" target="_blank"><strong>有効な連携</strong></a>ページでコスト連携を有効にする必要があります。一部のSRNは、コストデータの一括共有に対応しています。この場合、イベント単位のコストのフィールドには0が返されます。 </p></td></tr></tbody></table>

### 追加のフィールド

* <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#計測リンクのパラメータ">AppsFlyerのパラメータ一覧</Anchor>
* アトリビューションリンクにパラメータを追加すると、そのパラメータが返却データに含まれます。

詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#data-fields-dictionary">ローデータのフィールド一覧</Anchor>をご覧ください。

### 制限事項

<div id="custom-parameter-names" />

<Accordion title="カスタムパラメータの名前">

カスタムパラメータには、先頭の「n」が小文字の`name`という名前を使用できません。 `Name`は使用できます。

`name`という名前のパラメータは、返却データから削除されます。

</Accordion>

---

## SRN経由のユーザー獲得（UA）のコンバージョンデータ

<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns">セルフレポーティングネットワーク</Anchor>（SRN）は、独自のアトリビューションの仕組みを持つアドネットワークです。Meta広告やGoogleなどが該当します。

SRNはアトリビューションリンクを使用しません。そのため、次の制限があります。

* 返却データに含まれるフィールドは、あらかじめ定義されています。
* アトリビューションリンクにパラメータを追加して、返却データのフィールドを増やすことはできません。

SRNはAppsFlyerにコンバージョンを報告します。そのコンバージョンデータは、アプリ内で取得できます。取得できるフィールドはSRNによって異なります。詳しくは、以下の各SRNのタブをご覧ください。

#### Meta広告に関する注意

Meta広告でキャンペーンを実施する場合、Metaの利用規約に同意していなくても、AppsFlyerはインストールのアトリビューションを行います。ただし、利用できるレポートには次の制限があります。

* **利用可能：** 集計・分析用のダッシュボードとレポート
* **利用不可：** ローデータ

<Tabs>
<Tab title="Meta広告">

### Meta広告のコンバージョンデータ

| フィールド名 | 補足 | データの取得元 |
| --- | --- | --- |
| `match_type` | &lt;0>srn0>, &lt;0>gp\_referrer0>, &lt;0>probabilistic0> | AF |
| `media_source` | 常に`Facebook Ads` | AF |
| `agency` | `null`、または<Anchor target="_blank" href="/partners/ja/docs/about-agency-accounts#srn-構成">Meta広告のキャンペーンを代理店が運用する場合</Anchor>は代理店名 | Meta広告 |
| `http_referrer` | 常に`null` | Meta広告 |
| `retargeting_conversion_type` |  | AF |
| `af_channel` |  | Meta広告（publisher\_platform） |
| `af_status` | 常に`Non-organic` | AF |
| `ad_id` | Meta広告の内部処理でのみ使用されます。 | Meta広告（ad\_id） |
| `click_time` |  | AF |
| `install_time` |  | AF |
| `is_first_launch` | &lt;0>true0>, &lt;0>false0> | デバイス |
| `adset_id` | ローデータでは「広告セットID」として取得できます。 | Meta広告（campaign\_id） |
| `is_fb` | 常に`true` | AF |
| `campaign` | ローデータでは「キャンペーン名」として取得できます。 | Meta広告（campaign\_group\_name） |
| `campaign_id` | ローデータでは「キャンペーンID」として取得できます。 | Meta広告（campaign\_group\_id） |
| `is_paid` | 常に`true` | Meta広告 |
| `adgroup` | ローデータでは「広告」として取得できます。 | Meta広告（adgroup\_name） |
| `adgroup_id` | ローデータでは「広告ID」として取得できます。 | Meta広告（adgroup\_id） |
| `adset` | ローデータでは「広告セット」として取得できます。 | Meta広告（campaign\_name） |
| `af_siteid` | **af\_siteidの対応関係：**  <br />  <br />***publisher\_platform*** → ***af\_siteid***  <br />Facebook → ""  <br />Instagram → Instagram  <br />AudienceNetwork → AudienceNetwork  <br />Messenger → Messenger  <br />unknown → unknown  <br />"" + is\_instagram=true → Instagram  <br />"" + is\_external=true → AudienceNetwork | Meta広告 |
| `af_sub[1-5]` | 常に`null` | 広告主 |

**注意：** Meta広告はコンバージョン発生時にコストデータを共有しないため、コスト関連のフィールドは取得できません。<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-integration-setup#cost-clicks-and-impressions">コストデータの共有</Anchor>が有効な場合、Meta広告は1日に数回、AppsFlyerにコストデータを共有します。

</Tab>

<Tab title="Google広告">

<div id="google-ads-conversion-data" />

### Google広告のコンバージョンデータ

<table><thead><tr><th>フィールド名</th><th>補足</th></tr></thead><tbody><tr><td><code>match_type</code></td><td> &lt;0&gt;srn0&gt;, &lt;0&gt;probabilistic0&gt; </td></tr><tr><td><code>media_source</code></td><td>常に<code>googleadwords_int</code> </td></tr><tr><td><code>agency</code></td><td> <code>none</code>、または<code>af_prt</code>の値 </td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr><tr><td><code>af_channel</code></td><td>注意（1）</td></tr><tr><td><code>af_status</code></td><td>常に<code>Non-organic</code> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> &lt;0&gt;true0&gt;, &lt;0&gt;false0&gt; </td></tr><tr><td><code>adgroup_name</code></td><td> </td></tr><tr><td><code>adset_id</code></td><td>常に<code>null</code> </td></tr><tr><td><code>campaign</code></td><td>注意（3）</td></tr><tr><td><code>campaign_id</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>adset</code></td><td>注意（3）</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>ad_event_id</code></td><td> </td></tr><tr><td><code>af_ad</code></td><td>空の文字列</td></tr><tr><td><code>af_ad_id</code></td><td>Googleから<code>creative_id</code>の値が返された場合、ローデータで取得できます。</td></tr><tr><td><code>af_ad_type</code></td><td><span>AdWordsの広告タイプ</span></td></tr><tr><td><code>af_adset</code></td><td>ローデータでは「広告セット」として取得できます。</td></tr><tr><td><code>af_adset_id</code></td><td>ローデータでは「広告セットID」として取得できます。</td></tr><tr><td><code>af_c_id</code></td><td>ローデータでは「キャンペーンID」として取得できます。</td></tr><tr><td><code>af_click_lookback</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>注意（2）</td></tr><tr><td><code>af_dp</code></td><td> <a href="./google-ads-adwords-integration-setup-for-advertisers#アプリキャンペーンでのディファードディープリンクの使用" target="_blank">フィードに配信されるGoogleアプリキャンペーン</a>にのみ適用されます。</td></tr><tr><td><code>af_keywords</code></td><td>ローデータでは「キーワード」として取得できます。</td></tr><tr><td><code>af_prt</code></td><td> <code>none</code>、または<code>af_prt</code>の値 </td></tr><tr><td><code>af_reengagement_window</code></td><td>ローデータでは「リエンゲージメント期間」として取得できます。 </td></tr><tr><td><code>af_viewthrough_lookback</code></td><td>ローデータでは「ビュースルーアトリビューションのルックバック期間」として取得できます。</td></tr><tr><td><code>click_url</code></td><td>ローデータでは「HTTPリファラ」として取得できます。</td></tr><tr><td><code>click-timestamp</code></td><td>取得元：AppsFlyer</td></tr><tr><td><code>cost_cents_USD</code></td><td>注意（2）</td></tr><tr><td><code>external_account_id</code></td><td>AdWordsのアカウントID</td></tr><tr><td><code>gclid</code></td><td> </td></tr><tr><td><code>lat</code></td><td> </td></tr><tr><td><code>network</code></td><td>注意（1）</td></tr><tr><td><code>orig_cost</code></td><td>注意（2）</td></tr><tr><td><code>video_id</code></td><td>常に<code>null</code> </td></tr><tr><td colspan="2"> <strong>注意</strong><br/>（1）Googleは複数のアドネットワークを使用します。 <code>af_channel</code>と<code>network</code>を組み合わせて、インストールの流入元を特定してください。<br/>（2）これらのフィールドには0が返されます。広告主がコストデータの共有を有効にすると、Googleは1日に数回、AppsFlyerにコストデータを送信します。<br/>（3）<code>campaign</code>と<code>af_adset</code>を使用して、ユーザーに合わせたコンテンツを表示できます。</td></tr></tbody></table>

</Tab>

<Tab title="ASA">

<div id="apple-search-ads-conversion-data" />

### Apple Search Adsのコンバージョンデータ

<table><thead><tr><th>フィールド名</th><th>補足</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>常に<code>srn</code> </td></tr><tr><td><code>media_source</code></td><td>常に<code>Apple Search Ads</code> </td></tr><tr><td><code>{"&lt;0>adset0>"}</code></td><td>注意（2）</td></tr><tr><td><code>adset_id</code></td><td> </td></tr><tr><td><code>{"&lt;0>af_adset0>"}</code></td><td>注意（2）</td></tr><tr><td><code>af_adset_id</code></td><td> </td></tr><tr><td><code>af_c_id</code></td><td> </td></tr><tr><td><code>af_click_lookback</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>注意（1）</td></tr><tr><td><code>{"&lt;0>af_keywords0>"}</code></td><td>注意（2）：キーワードIDを使用してください。</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_status</code></td><td>常に<code>Non-organic</code> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>agency</code></td><td> <code>null</code>、または<code>af_prt</code>の値 </td></tr><tr><td><code>{"&lt;0>campaign0>"}</code></td><td>注意（2）</td></tr><tr><td><code>campaign_id</code></td><td> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> &lt;0&gt;true0&gt;, &lt;0&gt;false0&gt; </td></tr><tr><td><code>cost_cents_USD</code></td><td>注意（1）</td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>orig_cost</code></td><td>注意（1）</td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr><tr><td colspan="3"> <strong>注意</strong><br/>（1）Apple Search Adsはコストデータの一括共有に対応していますが、コンバージョンデータにはコストデータを含めません。<br/>（2）Apple Search AdsによるAdServices APの採用に伴い、2021年2月15日以降、これらのフィールドは非推奨となりました。 </td></tr></tbody></table>

</Tab>

<Tab title="Snapchat">

<div id="snapchat-conversion-data" />

### Snapchatのコンバージョンデータ

| フィールド名 | 補足 |
| --- | --- |
| `match_type` | `srn`、`gp_referrer`、`id_matching`、`probabilistic`   <br />アドバンスSRNのため、すべてのマッチング方式に対応しています。 |
| `media_source` | `snapchat_int` |
| `adset` |  |
| `adset_id` |  |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_c_id` |  |
| `af_channel` |  |
| `af_cpi` |  |
| `af_siteid` |  |
| `af_status` | 常に`Non-organic` |
| `af_sub[1-5]` |  |
| `af_viewthrough_lookback` |  |
| `agency` |  |
| `campaign` |  |
| `campaign_id` |  |
| `click_time` |  |
| `cost_cents_USD` |  |
| `http_referrer` |  |
| `install_time` |  |
| `is_first_launch` |  |
| `adgroup` |  |
| `adgroup_id` |  |
| `orig_cost` |  |
| `retargeting_conversion_type` |  |

</Tab>

<Tab title="X広告">

### X広告のコンバージョンデータ

| フィールド名 | 補足 |
| --- | --- |
| `match_type` | 常に`srn` |
| `media_source` | 常に`Twitter` |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_channel` |  |
| `af_siteid` |  |
| `af_status` | 常に`Non-organic` |
| `af_sub[1-5]` |  |
| `agency` | 常に`null` |
| `campaign` |  |
| `campaign_id` | `null`、またはキャンペーンID |
| `click_time` |  |
| `http_referrer` |  |
| `install_time` |  |
| `is_first_launch` | &lt;0>true0>, &lt;0>false0> |
| `adgroup` |  |
| `adgroup_id` |  |
| `retargeting_conversion_type` | 常に`none` |

**注意：** X広告はコストデータの共有に対応していないため、返却データにコストのフィールドは含まれません。

</Tab>

<Tab title="TikTok">

<div id="tiktok-conversion-data" />

### TikTok for Businessのコンバージョンデータ

| フィールド名 | 補足 |
| --- | --- |
| `match_type` | `srn`、`gp_referrer`、`id_matching`、`probabilistic`   <br />アドバンスSRNのため、すべてのマッチング方式に対応しています。 |
| `media_source` | `tiktokglobal_int` |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_channel` | &lt;0>tiktok0>, &lt;0>pangle0> |
| `af_siteid` |  |
| `af_status` | 常に`Non-organic` |
| `af_sub[1-5]` |  |
| `agency` |  |
| `campaign` |  |
| `campaign_id` |  |
| `click_time` |  |
| `http_referrer` |  |
| `install_time` |  |
| `is_first_launch` |  |
| `adgroup` |  |
| `adgroup_id` |  |
| `retargeting_conversion_type` |  |

**注意：** TikTokはコストデータの共有に対応していないため、返却データにコストのフィールドは含まれません。

</Tab>

<Tab title="Oath">

<div id="oath-ad-platforms-conversion-data" />

### Oath Ad Platformsのコンバージョンデータ

<table><thead><tr><th>フィールド名</th><th>補足</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>常に<code>srn</code> </td></tr><tr><td><code>media_source</code></td><td>常に<code>yahoogemini_int</code> </td></tr><tr><td><code>adset</code></td><td> </td></tr><tr><td><code>adset_id</code></td><td> </td></tr><tr><td><code>af_ad</code></td><td> </td></tr><tr><td><code>af_ad_id</code></td><td> </td></tr><tr><td><code>af_c_id</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>注意（1）</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_status</code></td><td>常に<code>Non-organic</code> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>agency</code></td><td> </td></tr><tr><td><code>campaign</code></td><td> </td></tr><tr><td><code>campaign_id</code></td><td> </td></tr><tr><td><code>campaign_type</code></td><td> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>cost_cents_USD</code></td><td>注意（1）</td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>orig_cost</code></td><td>注意（1）</td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr><tr><td colspan="2"> <strong>注意</strong><br/>（1）Oathはコストデータの共有に対応していますが、コスト関連のデータはコンバージョンデータに含めず、一括で送信します。</td></tr></tbody></table>

</Tab>
</Tabs>

## SRN以外のアドネットワーク経由のユーザー獲得（UA）のコンバージョン

SRN以外のアドネットワークでは、返却データの内容は<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">アトリビューションリンクのパラメータ</Anchor>によって直接決まります。

以下のJSON形式の返却データをご覧ください。

**注意：** コンバージョンデータは、キーと値の組み合わせを格納するマップ形式のデータ構造で返されます。開発者がJSONデータを直接扱う**わけではありません**。

<div id="applovin" />

<Accordion title="AppLovin">

#### アトリビューションリンク：

```http HTTPS
https://app.appsflyer.com/com.company.app?af_ad=ad_name&af_ad_type=INTER
  &af_channel=video&af_siteid=123_site_id&af_c_id=b8******************************&
  af_adset=_DEFAULT&pid=applovin_int&c=campaign_name
  &af_click_lookback=7d&clickid=10****************
  &advertising_id=50********************************&af_ip=
```

#### 返却データ：

```json
{
      "adgroup": null,
      "campaign": "campaign_name",
      "media_source": "applovin_int",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "install_time": "2018-12-30 23:49:54.186",
      "adgroup_id": null,
      "orig_cost": "0.0",
      "click_time": "2018-12-24 14:29:33.738",
      "agency": null,
      "cost_cents_USD": "0",
      "af_ad_type": "INTER",
      "af_c_id": "b8******************************",
      "adset": null,
      "advertising_id": "50********************************",
      "af_sub1": null,
      "clickid": "10****************",
      "af_click_lookback": "7d",
      "af_siteid": "123_site_id",
      "af_ad": "ad_name",
      "http_referrer": null,
      "af_channel": "video",
      "af_adset": "_DEFAULT",
      "af_sub5": null,
      "af_sub4": null,
      "af_cpi": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

* アトリビューションリンクのパラメータは、返却データにフィールドとして含まれます。
* 返却データのうち、**アトリビューションリンクに含まれていない**その他のフィールドの値はnullになります。
* AppLovinは広告コストデータの共有に対応していますが、コストデータはAppsFlyerに一括で送信します。コスト関連のフィールドには0が返されます。

</Accordion>

<div id="ironsource" />

<Accordion title="ironSource">

#### アトリビューションリンク：

```http HTTPS
https://app.appsflyer.com/id123456789?
  af_ua=Mozilla/5.0+(iPhone;+CPU+iPhone+OS+12_1_2+like+Mac+OS+X)+AppleWebKit/605.1.15+(KHTML,+like+Gecko)+Mobile/16C101
  &clickid=ab***************&redirect=false
  &ua=Mozilla/5.0+(iPhone;+CPU+iPhone+OS+12_1_2+like+Mac+OS+X)+AppleWebKit/605.1.15+(KHTML,+like+Gecko)+Mobile/16C101
  &af_lang=pt&imei=&af_sub1=&advertising_id=&af_ip=192.168.0.1&pid=ironsource_int
  &device_ip=192.168.0.1&c=campaign_name
  &idfa=01**********************************&af_siteid=123_site_id&
  af_enc_data=cN*********************************************************************
```

#### 返却データ：

```json
{
      "adgroup": null,
      "af_enc_data": "cN*************************************************************************************",
      "campaign": "campaign_name",
      "media_source": "ironsource_int",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "install_time": "2018-12-30 23:59:32.194",
      "adgroup_id": null,
      "redirect": "false",
      "orig_cost": "0.75",
      "click_time": "2018-12-30 23:58:54.517",
     "agency": null,
      "cost_cents_USD": "75",
      "adset": null,
      "advertising_id": "35****************************",
      "af_sub1": null,
      "af_ip": "192.168.0.1",
      "clickid": "ab*******************",
      "af_sub3": null,
      "af_cost_value": "0.75",
      "af_ref": "ironsource_5f******************************************",
      "af_siteid": "123_site_id",
      "http_referrer": null,
      "af_cost_model": "cpi",
      "af_ua": "Mozilla/5.0 (Linux; Android 8.0.0; SM-N950F Build/R16NW; wv) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/71.0.3578.99 Mobile Safari/537.36",
      "af_cost_currency": "USD",
      "af_sub5": null,
      "af_sub4": null,
      "af_lang": "en",
      "af_cpi": null,
      "af_click_lookback": "7d",
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

ironSourceは、コンバージョン発生時に`orig_cost`、`cost_cents_USD`、`af_cost_value`の各フィールドを使用して、コスト関連のデータをAppsFlyerに共有します。

ただし、コスト関連のデータは**アトリビューションリンクには含まれません**。 ironSourceはコストデータを暗号化し、`af_enc_data`フィールドに格納します。

</Accordion>

## リターゲティングのコンバージョンデータ

リターゲティングのコンバージョンには、リアトリビューションとリエンゲージメントの2種類があります。

> 👍 **Tip**
>
> **ヒント**
>
> リターゲティングのコンバージョンデータだけでは、コンバージョンの種別を明確に判断できない場合があります。[コンバージョンデータを取得するその他の方法](#コンバージョンデータを取得するその他の方法)をご覧ください。

### SRN経由のリアトリビューション

SRN経由でユーザーがリアトリビューションされた場合、コンバージョンデータの内容からは、リターゲティングキャンペーン経由であることを確認できません。 SRNはアトリビューションリンクを使用しないため、アトリビューションリンクに`is_retargeting=true`パラメータを設定できません。**リターゲティングに対応しているSRN**では、AppsFlyerがユーザーをリアトリビューションの対象とするかどうかを判断します。

つまり、SDKのデータだけでは、そのインストールがリターゲティングキャンペーン経由かどうかを判断できません。判別するには、リターゲティングキャンペーンであることが分かるキャンペーン名を設定するしかありません。

> 📘 **Note**
>
> **注意**
>
> ただし、リターゲティングであることが分かるキャンペーン名を設定しても、**確実に判別できるとは限りません**。詳しくは、[具体例](#ユーザー獲得とリアトリビューションが混在する例)をご覧ください。

### SRN以外のアドネットワーク経由のリアトリビューション

アドネットワークへのアトリビューションには、アトリビューションリンクを使用します。リターゲティングの場合、通常のアトリビューションリンクとOneLinkのどちらにも、必ず`is_retargeting=true`パラメータを設定します。

<div id="retargeting-campaign-with-criteo" />

<Accordion title="Criteoのリターゲティングキャンペーン">

#### アトリビューションリンク

```http
https://app.appsflyer.com/id1234567895?pid=criteo_int&af_click_lookback=30d&
  c=campaign_name&is_retargeting=true&redirect=false&idfa=68**********************************
  &af_reengagement_window=30d
```

#### コンバージョンデータの内容

```json
{
      "adgroup": null,
      "campaign": "campaign_name",
      "media_source": "criteo_int",
      "retargeting_conversion_type": "re-attribution",
      "adset_id": null,
      "campaign_id": null,
      "af_reengagement_window": "30d",
      "install_time": "2018-12-01 23:13:03.126",
      "adgroup_id": null,
      "redirect": "false",
      "af_sub5": null,
      "click_time": "2018-11-18 20:02:31.559",
      "agency": null,
      "cost_cents_USD": "0",
      "is_retargeting": "true",
      "af_cpi": null,
      "af_click_lookback": "30d",
      "af_siteid": null,
      "idfa": "68**********************************",
      "http_referrer": null,
      "orig_cost": "0.0",
      "af_sub4": null,
      "adset": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

* `retargeting_conversion_type`パラメータ：リターゲティングの種別を示します。値はre-attribution、re-engagement、noneのいずれかです。
* `is_retargeting: true`パラメータ：そのインストールがリアトリビューションされたインストールであることを示します。
* `af_reengagement_window`：リエンゲージメント期間は、**リエンゲージメントしたユーザー**のイベントをリエンゲージメントに紐づけられる日数です。この例はリアトリビューションのコンバージョンのため、このパラメータは不要です。

</Accordion>

### ディファードディープリンクを使用したリアトリビューション

リアトリビューションの対象となるユーザーは、その定義上、アプリをインストールしていない状態です。このようなユーザーを、ディープリンクでアプリ内の画面に誘導したい場合があります。例えば、アプリをアンインストールしたユーザーに再び利用してもらうためのキャンペーンを設定する場合です。このキャンペーンで商品やサービスを宣伝する際には、その商品やサービスに関連するコンテンツをユーザーに表示したいと考えられます。

このような誘導を「ディファードディープリンク」と呼びます。ディファードディープリンクのコンバージョンデータは、`onConversionDataSuccess`メソッドから取得します。

<div id="deferred-deep-linking-with-srns" />

<Accordion title="SRNでのディファードディープリンク">

SRNのキャンペーンで定義されたディープリンクのパラメータは、そのSRN以外では取得できません。これには、アプリ内のスキームパスを格納する`af_dp`パラメータも含まれます。唯一の例外は、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers#アプリキャンペーンでのディファードディープリンクの使用">フィードに配信されるGoogleアプリキャンペーン</Anchor>を使用する場合です。 SRNのキャンペーンでディファードディープリンクを実装するには、追加の処理が必要です。 `onConversionSuccess`の応答に含まれるcampaign、adset、adgroupなどのデータを使用して、プログラムでユーザーの遷移先を制御してください。

#### Meta広告でのディファードディープリンクのコンバージョンデータ

<Tabs>
<Tab title="Android">

```json
{
     "adset":"Adidas Running Shoes Women",
       "adgroup": null,
     "campaign_id":"6**********",
     "af_status":"Non-organic",
     "retargeting_conversion_type": "none",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,
     "is_first_launch":true,
     "click_time":"2017-07-18 12:55:05",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "campaign":"running shoes summer collection",
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "media_source":"Meta ads",
     "install_time":"2017-07-19 08:06:56.189",
     "af_sub2":null
  }
```

</Tab>

<Tab title="iOS">

```json
  {
     "media_source":"Meta ads",
     "campaign":"running shoes summer collection",
     "adset":"Running Shoes Women",
     "adgroup":null,
     "campaign_id":"6**********",
     "retargeting_conversion_type": "none",
     "af_status":"Non-organic",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,
   "is_first_launch":true,
     "click_time":"2017-07-17 16:23:18",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "install_time":"2017-07-18 15:10:50.190",
     "af_sub2":null
  }
```

</Tab>
</Tabs>

getConversionDataの応答に含まれるcampaign、adsetなどのデータを使用して、プログラムでユーザーの遷移先を制御し、関連するコンテンツを表示できます。

> 📘 **Note**
>
> **例**
>
> スポーツウェア専門のECアプリを例に説明します。アプリをインストールしていないユーザーが広告に反応し、アプリをインストールします。アプリを起動すると、SDKがコンバージョンデータを返します。開発者は、ストア内の**夏のランニングシューズコレクション**（campaign）の画面を開き、**女性用ランニングシューズ**のカテゴリ（adset）を表示するようにアプリを実装します。

</Accordion>

<div id="deferred-deep-linking-with-attribution-links" />

<Accordion title="アトリビューションリンクを使用したディファードディープリンク">

ディープリンクでユーザーを誘導する方法は3つあります。

#### URIスキーム

URIスキームを使用する場合、アトリビューションリンクとOneLink、および返却データは次のようになります。

**アトリビューションリンク**

```http
http://app.appsflyer.com/com.appsflyer.nivisampleapp?pid=media_source_name
  &c=campaign_name&af_dp=superapp%3A%2F%2deeplink-activity
```

**OneLink**

```http
/ short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  / /long OneLink
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true&af_dp=superapp%3A%2F%2deeplink-activity
```

**返却データ**

```json
{
      "af_deeplink": true,
      "campaign": "campaign_name",
      "media_source": "media_source_name",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "orig_cost": "0.0",
      "click_time": "2018-12-30 23:59:09",
      "install_time": "2018-12-30 23:59:39.330",
      "agency": null,
      "cost_cents_USD": "0",
      "adset": "AD_SET_NAME",
      "ad_id": "AD_ID",
      "af_siteid": null,
      "http_referrer": null,
      "af_cpi": null,
      "af_sub5": null,
      "af_sub4": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic",
      "scheme": "superapp",
      "host": "deeplink_activity"
  }
```

* `af_deeplink: true`：このパラメータが含まれ、値がtrueの場合は、`scheme`と`host`の各フィールドを確認してください。
* `scheme`と`host`：これらのフィールドは、アトリビューションリンクの`af_dp`パラメータから取得され、ディープリンクに使用するスキームと遷移先の画面を示します。

#### iOSのUniversal LinksとAndroidのApp Links

これらが、ディープリンクを実現する3つの方法のうち、残りの2つです。

Universal LinksまたはApp Linksを使用する場合、OneLinkと返却データは次のようになります。

**OneLink**

```http
/ short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //long OneLink
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true
```

**返却データ**

```json
{
      "install_time": "2019-01-08 16:24:49.853",
      "cost_cents_USD": "0",
      "campaign": "campaign_name",
      "retargeting_conversion_type": "none",
      "is_first_launch": true,
      "click_time": "2019-01-08 16:24:14.322",
      "af_click_lookback": "7d",
      "orig_cost": "0.0",
      "af_status": "Non-organic",
      "iscache": "true",
      "shortlink": "71ba577e",
      "media_source": "media_source_name",
      "is_retargeting": true
  }
```

* `shortlink`フィールド：ユーザーの流入元となったOneLinkを特定するフィールドです。開発者はこのフィールドを参照することで、どの画面を開き、どのコンテンツを表示するかを判断できます。 `campaign`など、その他のフィールドも同じ目的で使用できます。

  > 🚧 **Important**
  >
  > **重要**
  >
  > 長い形式のOneLinkを使用した場合、返却データに`shortlink`フィールドは含まれません。
  >
  > 短縮形式・長い形式のどちらのOneLinkでも、遷移先の画面を示すカスタムパラメータを追加することを推奨します。例：`&deep_link_activity=shoes_cateogry`


> 📘 **Note**
>
> **注意**
>
> Universal LinksとApp Linksは、OneLinkでのみ使用できます。

</Accordion>

### SRN経由のリエンゲージメント

リアトリビューションのキャンペーンと同様に、SRN経由でユーザーがリエンゲージメントした場合も、コンバージョンデータからは、リエンゲージメントキャンペーン経由であることを確認できません。リエンゲージメントキャンペーンであることが分かるキャンペーン名を設定できます。

### SRN以外のアドネットワーク経由のリエンゲージメント

この場合も、コンバージョンデータの内容からは、ユーザーがリエンゲージメントキャンペーン経由であることを確認できません。この制限に対処するには、リエンゲージメントであることが分かるキャンペーン名を設定します。

### ディープリンクを使用したリエンゲージメント

リエンゲージメントでは、ユーザーをアプリ内の特定の画面に誘導することが主な目的の1つです。例えば、商品やセールを宣伝する場合が挙げられます。このような場合、広告をクリックしたユーザーを、その商品やセールのアプリ内の画面に直接誘導したいと考えられます。

これを実現するには、ディープリンクを使用します。ディープリンクでは、コンバージョンデータが非常に重要です。ユーザーに合わせた体験を提供し、適切な画面へ誘導するために開発者が必要とする情報が含まれているためです。

<div id="reengagement-deep-linking-with-srns" />

<Accordion title="リエンゲージメント：SRNでのディープリンク">

SRN経由でユーザーがリエンゲージメントした場合、コンバージョンデータは取得できません。開発者は、アプリの起動時にSRNが提供するメソッドを使用して、このデータを取得する必要があります。

</Accordion>

<div id="reengagement-deep-linking-with-ad-networks" />

<Accordion title="リエンゲージメント：アドネットワークでのディープリンク">

ユーザーがリエンゲージメントしてアプリを起動すると、`onAppOpenAttribution`メソッドで次のコンバージョンデータを取得できます。

iOSとAndroidのどちらでも、短縮形式のOneLinkを使用した場合、コンバージョンデータはリンク上のすべてのパラメータを格納したマップ形式で返されます。

例：

```json
{
     af_dp: "superapp://Deeplink",
     pid: "media_source_name"
     c: "campaign_name",
     link: "https://abcd.onelink.me/12ab/12ab34c"
     is_retargeting: true
  }
```

* アプリ開発者は、`af_dp`やキャンペーン名などのパラメータを使用して、ユーザーをアプリ内の特定の画面へ誘導し、関連するコンテンツを表示できます。

> 🚧 **Important**
>
> **重要**
>
> 短縮形式のOneLinkを使用することを推奨します。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/understand-onelink-short-vs-long-urls">こちら</Anchor>をご覧ください。

短縮形式のOneLinkを推奨するもう1つの理由は、長い形式のOneLinkで返されるコンバージョンデータの構造にあります。長い形式を使用した場合、コンバージョンデータは`link`という単一のフィールドを持つマップ形式で返されます。このフィールドには、長い形式のOneLink全体が格納されます。

```json
{
     "link": "https://abcd.onelink.me/12ab?pid=media_source&c=campaign_name&is_retargeting=true&af_dp=superapp%3A%2F%2FDeepLink"
  }
```

</Accordion>

### コンバージョンデータを取得するその他の方法

* Push APIでは、リアトリビューションまたはリエンゲージメントを判別できる、詳細なコンバージョンデータを取得できます。 Push APIの返却データには、`re_targeting_conversion_type`というフィールドが含まれます。このフィールドは、コンバージョンの種別がリアトリビューションかリエンゲージメントかを示します。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/push-api-streaming-raw-data">Push APIガイド</Anchor>をご覧ください。
* ローデータレポートにも、コンバージョンの種別を示す情報が含まれます。リターゲティングのコンバージョンを扱うローデータレポートには、***イベント名***という列があります。この列の値は、コンバージョンの種別に応じて***re-engagemen*t**または***re-attribution*** になります。

### ユーザー獲得とリアトリビューションが混在する例

> 📘 **Note**
>
> **例**
>
> 1. ユーザーがアプリをインストールした後、アンインストールします。インストールした時点から、このユーザーには<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window">リアトリビューション期間</Anchor>が適用されます。 Meta広告で、リターゲティングではなくユーザー獲得のキャンペーンを設定します。また、AppsFlyerとMeta広告の連携設定で、リターゲティングを有効にします。
>
>    リアトリビューション期間内に、ユーザーが広告を見てクリックし、アプリを再インストールします。 AppsFlyerでは、このユーザーをリアトリビューションされたユーザーとして扱います。
>
>    これは、次の2つの条件を満たしているためです。
>
>    1. Meta広告との連携設定でリターゲティングが有効になっている
>    2. ユーザーがリアトリビューション期間内にいる
>
>    この場合、キャンペーン名からはリアトリビューションであることを判断できません。
> 2. 同じ例で、ユーザーがリアトリビューション期間外にいる場合を考えてみましょう。この場合、インストールは新規のノンオーガニックインストールとして扱われます。
> 3. 別の例を見てみましょう。 Meta広告でリターゲティングキャンペーンを設定します。そのキャンペーンを見た一部のユーザーが、アプリをインストールします。ただし、これらのユーザーは初めてアプリをインストールしています。このようなユーザーは、リアトリビューションされたユーザーとは見なされません。 AppsFlyerでは、ユーザー獲得キャンペーン経由のユーザーとして扱います。

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01HCY86CKDJK9TNHPAZB0QX2ZX=%E6%A6%82%E8%A6%81 nonorganic-conversion-data-payload-fields=%E3%83%8E%E3%83%B3%E3%82%AA%E3%83%BC%E3%82%AC%E3%83%8B%E3%83%83%E3%82%AF%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AB%E5%90%AB%E3%81%BE%E3%82%8C%E3%82%8B%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 h_01HCY86CKDEMB3428YHCNJQA5R=%E3%83%8E%E3%83%B3%E3%82%AA%E3%83%BC%E3%82%AC%E3%83%8B%E3%83%83%E3%82%AF%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AB%E5%90%AB%E3%81%BE%E3%82%8C%E3%82%8B%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 fields-always-available=%E5%B8%B8%E3%81%AB%E5%90%AB%E3%81%BE%E3%82%8C%E3%82%8B%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 h_01HCY86CKDBQRGAY7GHNBJE4WK=%E5%B8%B8%E3%81%AB%E5%90%AB%E3%81%BE%E3%82%8C%E3%82%8B%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 fields-available-in-some-cases=%E6%9D%A1%E4%BB%B6%E3%81%AB%E3%82%88%E3%81%A3%E3%81%A6%E5%90%AB%E3%81%BE%E3%82%8C%E3%82%8B%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 h_01HCY86CKDYQMYB9BQ4MXWP8A5=%E6%9D%A1%E4%BB%B6%E3%81%AB%E3%82%88%E3%81%A3%E3%81%A6%E5%90%AB%E3%81%BE%E3%82%8C%E3%82%8B%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 additional-fields=%E8%BF%BD%E5%8A%A0%E3%81%AE%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 h_01HCY86CKD47M85AZVEA5C4JH7=%E8%BF%BD%E5%8A%A0%E3%81%AE%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 limitations=%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HCY86CKEFX646H9BSKSFGZ36=%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HCY86CKEZ2483XB461M2C9EC=custom-parameter-names ua-conversion-data-with-srns=srn%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97ua%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF h_01EGKTQN6XDYHA60P2WKHBBVFT=srn%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97ua%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF a-note-about-facebook=meta%E5%BA%83%E5%91%8A%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E6%B3%A8%E6%84%8F h_01HCY86CKENFEGX53G9G4SGPSK=meta%E5%BA%83%E5%91%8A%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E6%B3%A8%E6%84%8F facebook-conversion-data=meta%E5%BA%83%E5%91%8A%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF h_01HCY86CKE658H36F3VJQMATQK=meta%E5%BA%83%E5%91%8A%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF h_01HCY86CKF6FY96PAWB5Y7YXSQ=google-ads-conversion-data h_01HCY86CKFMNNNJZTPGK4870YN=apple-search-ads-conversion-data h_01HCY86CKF26JRT64JR9JZEAKJ=snapchat-conversion-data h_01HSQRQSK8W9K6871K0EWHDF76=tiktok-conversion-data h_01HCY86CKFS5SJBECSY42VRJWP=oath-ad-platforms-conversion-data ua-conversion-with-other-ad-networks=srn%E4%BB%A5%E5%A4%96%E3%81%AE%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97ua%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3 h_01HCY86CKFB0GEJRTYSXN9YZ08=srn%E4%BB%A5%E5%A4%96%E3%81%AE%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97ua%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3 h_01HCY86CKFY787RD4BHQDVEVFV=applovin attribution-link=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF h_01HCY86CKFXM5XXJZSPXPB6397=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF payload=%E8%BF%94%E5%8D%B4%E3%83%87%E3%83%BC%E3%82%BF h_01HCY86CKFDDXWT2KKFTKKBGHM=%E8%BF%94%E5%8D%B4%E3%83%87%E3%83%BC%E3%82%BF h_01HCY86CKFV55GYY7C51D7F72S=ironsource attribution-link::a45a1b4a=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF-1 h_01HCY86CKFYGEYR2TRPSD87KDA=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF-1 payload::81867f5c=%E8%BF%94%E5%8D%B4%E3%83%87%E3%83%BC%E3%82%BF-1 h_01HCY86CKFKKFQDG1P42R1FSDJ=%E8%BF%94%E5%8D%B4%E3%83%87%E3%83%BC%E3%82%BF-1 retargeting-conversion-data=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF h_01EHQ74JS84509GT6M93SZA4HX=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF reattribution-with-srns=srn%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HCY86CKFAVWP1W0ZNEN5P30A=srn%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 reattribution-with-regular-ad-networks=srn%E4%BB%A5%E5%A4%96%E3%81%AE%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HCY86CKF1PV8MRR902RAHQGW=srn%E4%BB%A5%E5%A4%96%E3%81%AE%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HCY86CKF1RGK01VTV3EEHQVM=retargeting-campaign-with-criteo attribution-link::c16e96bb=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF-2 h_01HCY86CKFSKBBMFKA8NN8XTPC=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF-2 conversion-data-payload=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%86%85%E5%AE%B9 h_01HCY86CKG2YQQC629SC3RAFKE=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%86%85%E5%AE%B9 reattribution-with-deferred-deep-linking=%E3%83%87%E3%82%A3%E3%83%95%E3%82%A1%E3%83%BC%E3%83%89%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9F%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HCY86CKGXV50H79R0YH1GB2C=%E3%83%87%E3%82%A3%E3%83%95%E3%82%A1%E3%83%BC%E3%83%89%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9F%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HCY86CKG12YRGFEEJ27DQART=deferred-deep-linking-with-srns conversion-data-for-deferred-deep-linking-with-facebook=meta%E5%BA%83%E5%91%8A%E3%81%A7%E3%81%AE%E3%83%87%E3%82%A3%E3%83%95%E3%82%A1%E3%83%BC%E3%83%89%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF h_01HCY86CKGX9VHSV3ASKXMFM0X=meta%E5%BA%83%E5%91%8A%E3%81%A7%E3%81%AE%E3%83%87%E3%82%A3%E3%83%95%E3%82%A1%E3%83%BC%E3%83%89%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF h_01HCY86CKG3XWM4X0YH7WYCEH4=deferred-deep-linking-with-attribution-links uri-schemes=uri%E3%82%B9%E3%82%AD%E3%83%BC%E3%83%A0 h_01HCY86CKGDM2NE1FCRC92K8R0=uri%E3%82%B9%E3%82%AD%E3%83%BC%E3%83%A0 ios-universal-links-and-android-app-links=ios%E3%81%AEuniversal-links%E3%81%A8android%E3%81%AEapp-links h_01HCY86CKGY1NE4214DES0Y2AV=ios%E3%81%AEuniversal-links%E3%81%A8android%E3%81%AEapp-links reengagement-with-srns=srn%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88 h_01HCY86CKG4TRYR6TWYYVB0FJE=srn%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88 reengagement-with-regular-ad-networks=srn%E4%BB%A5%E5%A4%96%E3%81%AE%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88 h_01HCY86CKGM2JS7C9T71R6GPH1=srn%E4%BB%A5%E5%A4%96%E3%81%AE%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88 reengagement-with-deep-linking=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9F%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88 h_01HCY86CKG0NPQAA2ZRWWNKGQD=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9F%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88 h_01HCY86CKGEBHQVFRGJH96KDFJ=reengagement-deep-linking-with-srns h_01HCY86CKGJ9HG7AGB5MFP33RK=reengagement-deep-linking-with-ad-networks alternative-conversion-data-sources=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E5%8F%96%E5%BE%97%E3%81%99%E3%82%8B%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E6%96%B9%E6%B3%95 h_01HCY86CKG3N6ZXV70G4VMZ0X5=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E5%8F%96%E5%BE%97%E3%81%99%E3%82%8B%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E6%96%B9%E6%B3%95 examples-of-mixed-user-acquisition-and-reattribution=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97%E3%81%A8%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%8C%E6%B7%B7%E5%9C%A8%E3%81%99%E3%82%8B%E4%BE%8B h_01HCY86CKGK9DVVB7T6CVNB8ZN=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97%E3%81%A8%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%8C%E6%B7%B7%E5%9C%A8%E3%81%99%E3%82%8B%E4%BE%8B" />
