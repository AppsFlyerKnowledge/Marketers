---
title: CTV、PC、コンソールプラットフォームのダイレクト計測リンク
metadata:
  keywords:
    - Advertiser
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2023-05-10T10:21:14Z'
  edited_at: '2026-10-14T09:36:24Z'
  id: 15199908310801
  locale: ja
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/ja/articles/15199908310801
---
> **概要：**  CTV、PC、コンソールプラットフォーム向けのAppsFlyer計測リンクの構造とパラメーターについて説明します。　**注意：** Android および iOSアプリ（Android PCゲームを含む）の場合は、 <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">モバイル計測リンクの手順</Anchor>を使用します。

## 概要

CTV、PC、コンソール プラットフォームのダイレクト計測リンクを使用すると、広告主はユーザーをリダイレクトし、クリック後のデータを収集できます。ダイレクト計測リンクは、**一度に1つのプラットフォーム上の1つのリンク先を持つアプリ**に対するリダイレクトとアトリビューションをサポートする、AppsFlyer のリンクです。リダイレクト先は、リンクに含まれる af\_r パラメーターの値です。

**注意：** Android および iOSアプリ（Android PCゲームを含む）の場合は、 <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">モバイル計測リンクの手順</Anchor>を使用します。

計測リンクは、直接作成して広告の背後に配置することができます。このようなリンクを作成するには、この記事の手順に従ってください。

あるいは、 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_click-app-platform-app-id">エンゲージメントAPI</Anchor>を使用してS2S経由でリンクを作成することもできます。これには開発者の作業が必要です。　**注意：** S2S経由で作成されたリンクでもインプレッションデータを収集できます。

### 計測リンク

<table><thead><tr><th colspan="2">計測リンクの構造</th></tr></thead><tbody><tr><td>ベースURL</td><td>engagements.appsflyer.com/v1.0/c2s/click/app/</td></tr><tr><td>必須のpathパラメーター</td><td><ul><li>platform<br/>例：steam</li><li>app_id<br/>例：123456</li></ul></td></tr><tr><td>必須のクエリパラメーター</td><td><ul><li>af_media_source</li><li>af_campaign_id</li></ul></td></tr><tr><td>その他のパラメーター</td><td><a href="./ctv-pc-and-console-platform-direct-attribution-links#パラメーター">すべてのパラメーターはこちら</a></td></tr><tr><td>URLの構造</td><td><code>https://engagements.appsflyer.com/v1.0/c2s/click/app/`{platform}/{app_id}?af_media_source={media_source}&amp;af_campaign_id={campaign_id}&amp;af_r={app_store_url}`</code></td></tr><tr><td>サンプルURL</td><td><code>https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=aloha&amp;af_campaign_id=1234&amp;af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello</code></td></tr></tbody></table>

### パラメーター

| パラメーター | ローデータ出力とPull APIでの表示名 | 説明 | 項目タイプ |
| --- | --- | --- | --- |
| platform | Platform | <ul><li>アプリケーションプラットフォームを指定するパスパラメーター。</li><li>含まれる値：<ul><li>smartcast</li><li>tizen</li><li>roku</li><li>webos</li><li>vidaa</li><li>playstation</li><li>steam</li><li>quest</li><li>battlenet</li><li>epic</li><li>switch</li><li>xbox</li><li>nativepc</li></ul></li></ul> | 文字列 |
| app\_id | App ID | <ul><li>投稿するアプリのアプリIDを指定するパスパラメーター。</li><li>例： `ap123456`</li><li>アプリIDの値にプラットフォームプレフィックスを追加しないでください。例えば、アプリIDが `ap123456` で、プラットフォームが `platformX` の場合、`platformX_ap123456` を `app_id` の値として使用しないでください。</li></ul> | 文字列 |
| af\_media\_source | Media Source | これは、AppsFlyer プラットフォームで定義されている一意のパートナー識別子です。  <br />次の文字は使用できません： ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, &lt;, /, \{, \}, % | 文字列 |
| af\_campaign | Campaign | キャンペーン名 | 文字列 |
| af\_campaign\_id | Campaign ID | キャンペーンID | 文字列 |
| af\_request\_id | N/A | パートナーによるリクエストを一意に識別する識別子。 | 文字列 |
| af\_adset | Adset | 広告セット名 | 文字列 |
| af\_adset\_id | Adset ID | 広告セットID | 文字列 |
| af\_ad | Ad | 広告名 | 文字列 |
| af\_ad\_id | Ad ID | 広告ID | 文字列 |
| af\_campaign\_type | Campaign Type | 以下いずれか：<ul><li>user\_acquisition</li><li>retargeting</li></ul> | 文字列 |
| af\_prt | Partner | <ul><li>代理店運用のトラフィックと識別するための代理店識別子</li><li>**注意**：**代理店権限**が有効になっていることを確認する前に、このパラメーターを使用しないでください。</li></ul> | 文字列 |
| af\_siteid | Site ID | <span id="query-getImpressionAppPlatformApp_id_af_siteid__description"></span>広告を表示しているパブリッシャーを識別する一意のID。 | 文字列 |
| af\_sub\_siteid | Sub Site ID | <span id="query-getImpressionAppPlatformApp_id_af_sub_siteid__description"></span>アドネットワークのサブネットワーク/パブリッシャーID | 文字列 |
| af\_click\_id | 該当無し | <span id="query-getImpressionAppPlatformApp_id_af_click_id__description"></span>アドネットワーク固有のトランザクション識別子 | 文字列 |
| af\_lookback\_window | 該当なし | <ul><li>ルックバック期間は、IDマッチングによるアトリビューションのみに関連します。</li><li>ルックバック期間のアトリビューション期間に設定可能な日数/時間数。使用可能なパラメーター値：1d-30d（日数）または 1h-23h（時間）</li><li>妥当性：上記のスキームを使用すると、最大3文字になります。</li><li>デフォルト値は、インプレッションの場合は24時間、クリックの場合は7日です。</li></ul> | 文字列 |
| af\_ad\_placement | 該当なし | <span id="query-getImpressionAppPlatformApp_id_af_ad_placement__description"></span>アドネットワーク固有のトランザクション識別子 | 文字列 |
| af\_ad\_type | Ad Type | <ul><li>広告タイプ。以下の命名規則を利用してください：<ul><li>**text:** テキストのみを含む広告ユニット（例：検索結果など）</li><li>**banner:** 画面の上部または下部に表示される基本フォーマット</li><li>**interstitial:** 画面閲覧中に差し込まれる、インターステシャル広告</li><li>**video:** リワード広告ではない通常の動画広告</li><li>**rewarded\_video:** 動画視聴と引き換えにアプリ内報酬を提供するリワード動画広告</li><li>**playable:** 実際のアプリ操作が一部可能な、インタラクティブな広告</li><li>**audio:** 音声広告</li></ul></li><li>大文字と小文字の区別を強制しています。</li></ul> | 文字列 |
| af\_channel | Channel | <span id="query-getImpressionAppPlatformApp_id_af_channel__description"></span>広告が配信されるメディアソースチャネル (例：UAC\_Search、UAC\_Display、Instagram、Meta Audience Networkなど)。 | 文字列 |
| af\_model | Device Model | デバイスモデル | String型 64文字 |
| af\_os\_version | 該当なし | <ul><li>デバイス／OSバージョン</li><li>数字とドットのみ使用可能</li><li>例：8.1.0</li></ul> | 文字列 |
| af\_device\_id\_type | 該当なし | <span id="query-getImpressionAppPlatformApp_id_af_device_id_type__description"></span>デバイス識別子のタイプ。以下いずれか：<ul><li>vida</li><li>tifa</li><li>rida</li><li>lgudid</li><li>fire</li><li>advertising\_id</li><li>fire</li><li>custom</li></ul> | 文字列 |
| af\_device\_id\_value | 該当なし | <span id="query-getImpressionAppPlatformApp_id_af_device_id_value__description"></span>デバイス識別子のタイプ | 文字列 |
| af\_r | 該当なし | <ul><li>正しいアプリストアまたはランディングページへのリンクが含まれています</li><li>af\_r パラメーター内の文字列すべてをエンコードする必要があります。これには、UTMパラメーター値（追加されている場合）も含まれます。</li></ul>**注記：** あなたの<Anchor target="_blank" href="/marketers/ja/docs/set-up-your-domain-redirect-allowlist">リダイレクト許可リスト</Anchor>に af\_r のURLドメインが含まれていることを確認してください。 | 文字列 |

## 特性と制限

| ルックバック期間 | 確率論的モデリングでは、クリックとインプレッションに対して24時間の固定ルックバック期間が使用されます。af\_lookback\_window 値は無視されます。 |
| --- | --- |
| 代理店計測 | <ul><li>CTV、PC、コンソールからモバイル：対応しています。</li><li>モバイルからCTV、PC、コンソール：対応していません。</li></ul> |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 01H7Z1003GTTMRY072BXWDFNP0=%E6%A6%82%E8%A6%81 attribution-link=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF 01H7Z1003G0WYBCK3530064WM1=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF attribution-link-parameters=%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC 01H7Z1003GNC551PDCKKFQMPVN=%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC traits-and-limitations=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01HVED5DJPFR5XCWYDSYCHMCR6=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01J6S6HS0H0M6GQ81WGZ3XT0P9=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90" />
