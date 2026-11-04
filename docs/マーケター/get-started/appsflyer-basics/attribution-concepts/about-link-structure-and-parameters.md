---
title: 計測リンクの構造とパラメータについて
metadata:
  keywords:
    - pid
    - Marketers
    - af_
    - af
    - c
    - af_mp
    - clickid
    - af_siteid
    - af_sub_siteid
    - af_c_id
    - af_adset_id
    - af_ad_type
    - af_viewthrough
    - af_cost_model
    - af_cost_value
    - af_web_dp
    - af_ref
    - af_ip
    - af_os_version
    - deep_link_sub
    - deep_link_value
    - af_og_title
    - af_og_description
    - af_og_image
    - af_prt
    - af_adset
    - af_ad
    - af_ad_id
    - af_channel
    - af_keywords
    - af_cost_currency
    - af_sub
    - af_r
    - af_dp
    - af_force_deeplink
    - is_incentivized
    - af_param_forwarding
    - af_partner_account_id
    - af_ua
    - af_os
    - af_model
    - af_media_type
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-12-24T11:50:00Z'
  edited_at: '2026-10-28T09:07:25Z'
  id: 207447163
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/207447163
---
> **概要：** AppsFlyerの計測リンクの構造とパラメータを説明します。

<div id="overview" />

## 概要

計測リンクを使用すると、広告主はユーザーの広告接触に関するデータを収集できます。広告に計測リンクを設定することで、ユーザーが広告に反応した際にAppsFlyerに通知されます。広告接触には、広告のクリックと、広告が表示されるインプレッションがあります。 計測URLのコピーがAppsFlyerに送信されます。

計測リンクは、**OneLink**または**単一プラットフォーム向けリンク**を使用して作成します。

|  | OneLink（複数プラットフォーム向けリンク） | 単一プラットフォーム向けリンク |
| --- | --- | --- |
| 概要と利用場面 | 以下の場合に使用します。<ul><li>すべてのプラットフォームで1つのリンクを使用したい場合。</li><li>ディープリンク機能が必要な場合。</li><li>Android App LinksまたはiOSのユニバーサルリンクでアプリを開きたい場合。</li></ul><Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLinkについて詳しく見る</Anchor> | 以下の場合に使用します。<ul><li>単一のプラットフォームのみを使用する場合。たとえば、Androidのみを使用し、iOSは使用しない場合です。</li><li>URIスキームのみでアプリを開く場合。</li></ul><Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">連携済みパートナーの設定方法について詳しく見る</Anchor> |
| 前提条件 | <Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template">OneLinkテンプレート</Anchor> | なし |
| 含める情報 | <ul><li>[メディアソース](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)</li><li>[キャンペーン](#c)</li><li>[サイトID／サブサイトID](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> | <ul><li>[メディアソース](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)</li><li>[キャンペーン](#c)</li><li>[サイトID／サブサイトID](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> |
| ベースURL | `{subdomain}`.onelink.me | app.appsflyer.com |
| 一意の識別子 | テンプレートID | app\_id |
| URLの構造 | `https://{subdomain}.onelink.me/`<br />`{templateid}?pid={media_source}`<br />`&af_siteid={ApplicationID}`<br />`&c={CampaignName}` | `https://app.appsflyer.com/{app_id}?pid={media_source}&af_siteid={ApplicationID}&c={CampaignName}` |
| 例 | `https://yourbrand.onelink.me/aAB1?pid=greatnetwork_int`<br />`&c=GreatCampaign&af_siteid=A1b1` | `https://app.appsflyer.com/com.greatapp?pid=greatnetwork_int&`<br />`c=GreatCampaign&af_siteid=A1b1` |

<div id="important" />

> 🚧 **重要**
>
> AppsFlyerが受信する広告接触のトラフィック（クリックとインプレッション）は、HTTPSプロトコルのみに対応しています。

<div id="attribution-link-parameters" />

## 計測リンクのパラメータ

* 以下のパラメータを計測リンクで使用できます。
* **フィールドの型**の列の数値は、パラメータ値の文字数上限です。パラメータ値の長さに関する制限は、<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary">こちら</Anchor>を参照してください。

<div id="attribution-link-parametersua-and-retargeting" />

### 計測リンクのパラメータ｜UAとリターゲティング

以下の表は、[`.csv`ファイルとしてダウンロード](https://docs.google.com/spreadsheets/d/e/2PACX-1vTZQnoDdFo2NxBuWXBs5gGgvkGU2pr_hn58H9Dtf5uHBAHv4Io89Wd44rRtL24pRsOXHthnBitaOyfp/pub?gid=0&single=true&output=csv)できます。

<div id="attribution-parameters" />

| パラメータ | ローデータでの表示名 | 説明 | フィールドの型と長さ |
| --- | --- | --- | --- |
| <span id="pid"></span>pid | メディアソース | AppsFlyerの連携済みパートナーを一意に識別します。変更しないでください。[詳細を見る](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)。 | <span id="PID"></span>文字列・150文字 |
| <span id="c"></span>c | キャンペーン | 広告主またはパブリッシャーが指定します。[キャンペーン名の制限](/docs/about-link-structure-and-parameters#what-limits-are-there-on-campaign-names)を参照してください。 | <span id="Campaign"></span>文字列 |
| <span id="af_prt"></span>af\_prt | パートナー | <ul><li>代理店アカウント名を指定することで、インストールを代理店に紐付けられます。</li><li>**注意**：このパラメータを使用する前に、**代理店の権限**が有効になっていることを必ず確認してください。</li></ul> | 文字列・50文字 |
| <span id="af_mp"></span>af\_mp | N/A | <ul><li>インストールごとに、パブリッシャーのマーケティングパートナーへのポストバック送信を有効にします。</li><li>**注意**：現在、このパラメータはPinterestのマーケティングパートナーにのみ適用されます。</li></ul> |  |
| <span id="clickid"></span>clickid | N/A | アドネットワークが発行する一意のクリック識別子 |  |
| <span id="af_siteid"></span>af\_siteid | サイトID | <ul><li>広告を表示するパブリッシャーを識別する一意のIDです。[詳しく見る](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> | <span id="Site_id"></span>文字列・24文字 |
| <span id="af_sub_siteid"></span>af\_sub\_siteid | サブサイトID | <ul><li>広告のサブネットワーク／パブリッシャーIDです。</li><li>主要なパブリッシャー（サイトID）に加えてサブパブリッシャーがある場合や、バナー、インタースティシャル、動画などの広告タイプやアプリ内の掲載位置に関する情報を含めたい場合は、af\_sub\_siteidを使用します。例：af\_sub\_siteid =ABCD\_4567</li></ul> | 文字列 |
| <span id="af_c_id"></span>af\_c\_id | キャンペーンID | 広告主またはパブリッシャーが指定します。 | 文字列・24文字 |
| <span id="af_adset"></span>af\_adset | 広告セット | <ul><li>広告主またはパブリッシャーが指定します。</li><li>広告セットは、キャンペーンと広告の間に位置する階層です。[詳しく見る](/docs/about-link-structure-and-parameters#データの詳細度の階層)</li></ul> | 文字列・100文字 |
| <span id="af_adset_id"></span>af\_adset\_id | 広告セットID | 広告主またはパブリッシャーが指定します。 | 文字列・24文字 |
| <span id="af_ad"></span>af\_ad | 広告 | 広告主またはパブリッシャーが指定する広告名です（[詳しく見る](/docs/about-link-structure-and-parameters#データの詳細度の階層)）。 | 文字列・100文字 |
| <span id="af_ad_id"></span>af\_ad\_id | 広告ID | 広告主またはパブリッシャーが指定します。 | 文字列・24文字 |
| <span id="af_ad_type"></span>af\_ad\_type | 広告タイプ | 以下の値を使用します。<ul><li>**native**：メディアソースのコンテンツになじむよう設計された有料広告です。通常のコンテンツと見た目や機能を合わせて設計され、おすすめ動画のフィードなどに表示されます。</li><li>**banner**：一般に小さな長方形のディスプレイ広告で、Webページやアプリ画面のさまざまな場所に表示されます。</li><li>**interstitial**：掲載先アプリの画面全体を覆う全画面広告です。コンテンツの合間に配置する広告で、通常はアクティビティ間、ゲームのレベル間、一時停止中など、アプリ操作の区切りに表示されます。</li><li>**rewarded\_video**：ユーザーがアプリ内報酬と引き換えに、最後まで視聴することを選べる広告です。たとえば、動画視聴の報酬としてゲーム内のライフ、記事の閲覧権、空港のWi-Fi利用権などを提供します。このようなリワード広告は、ユーザーの参加を促し、アプリ全体の体験を向上させます。</li><li>**audio**：オンラインのポッドキャストや音楽配信プラットフォームで配信される音声形式の広告です。</li><li>**offerwall**：開発者がアプリの収益化に使用するアプリ内広告枠です。アプリ内の小さなストアのように複数の「オファー」を一覧表示し、ユーザーは条件を達成することでアプリ内報酬を得られます。</li></ul> | 文字列・24文字 |
| <span id="af_ad_format"></span>af\_ad\_format | 広告フォーマット | 以下の値を使用します。<ul><li>**text**：通常、短いテキストで表示される文字主体の広告です。見出し、説明文、リンクやCTAなどを含め、関心を引いてWebサイトやランディングページへのクリックを促します。</li><li>**image**：画像や写真を使って商品、サービス、ブランドを紹介するビジュアル広告です。通常は目を引く画像と簡潔なテキストを組み合わせ、CTAを含めることもあります。</li><li>**video**：映像と音声を使用してマーケティングメッセージを伝えるデジタル広告です。長さはさまざまで、オンライン動画の再生前・途中・終了後に表示されるほか、各種プラットフォームで独立した動画として配信されます。</li><li>**playable**：ダウンロードや購入の前に、ゲームやアプリの簡易版を操作できるインタラクティブ広告です。ユーザーは実際のゲームプレイやアプリ機能の一部を体験できます。</li><li>**interactive**：ユーザーの操作や参加を促す、動きのある魅力的な広告です。クイズ、投票などの双方向的な要素を使い、ユーザーの関心を引いて積極的な参加を促します。</li><li>**dynamic\_product**：ユーザーの行動、好み、閲覧履歴に基づき、商品情報や詳細を動的に表示するパーソナライズ広告形式です。一人ひとりに関連性の高い、最適な商品広告を表示できます。</li><li>**carousel**：1つの広告内に複数のスライドやカードを配置する形式です。カードごとに異なる画像、見出し、説明文を設定し、複数の商品や機能を1つの広告で紹介できます。</li></ul> |  |
| <span id="af_click_lookback"></span>af\_click\_lookback | アトリビューションのルックバック期間 | <ul><li>クリックによるアトリビューションのルックバック期間です。広告やリンクを掲載したメディアソースに新規ユーザーを紐付けられる、クリックからインストールまでの最大時間（CTIT）を定めます。</li><li>クリックによるアトリビューションのルックバック期間を日数で設定できます。指定可能な値：1d～30d（日）または1h～23h（時間）。デフォルト値は7dです。</li><li><Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows#ルックバック期間の設定方法">OneLinkおよびSRN</Anchor>のルックバック期間は変更できます。</li></ul>**注意**：クリックURLにのみ適用され、インプレッションURLには適用されません。 | 最大3文字 |
| <span id="af_viewthrough_lookback"></span>af\_viewthrough\_lookback | N/A | <ul><li>ビュースルーアトリビューションのルックバック期間を時間単位で設定できます。指定可能な値：1h～24h（時間）。デフォルト値は24hです。</li><li><Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows#ルックバック期間の設定方法">SRN</Anchor>のルックバック期間は変更できます。</li></ul>**注意**：インプレッションURLにのみ適用され、クリックURLには適用されません。 | 最大3文字 |
| <span id="af_channel"></span>af\_channel | チャネル | 広告が配信されるメディアソース内のチャネルです。例：UAC\_Search、UAC\_Display、Instagram、Meta Audience Networkなど。 | 動的な列挙型。文字列・20文字 |
| <span id="af_engagement_destination"></span>af\_engagement\_destination | 広告のリンク先 | 広告のリンク先のカテゴリを示します。**Web**のランディングページ、**モバイル**アプリ（ディープリンクまたはアプリストア経由）、**CTV**、**PC**、**コンソール**などがあります。 | 文字列・50文字 |
| <span id="af_keywords"></span>af\_keywords | キーワード | テキストターゲティングキャンペーンのキーワード一覧です。 | 文字列・100文字 |
| <span id="af_cost_model"></span>af\_cost\_model | コストモデル | <ul><li>コストモデルです。クリック経由でコストを報告し、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports">AppsFlyerの集計データ</Anchor>レポートにコスト値を反映する場合、現在対応しているモデルはCPI（デフォルト）のみです。</li><li>可能な場合は、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#cost-aggregation-methods">API</Anchor>でコストを報告してください。リンクとAPIの両方でコストが報告された場合は、APIの値が優先されます。</li></ul> | 文字列・20文字 |
| <span id="af_cost_currency"></span>af\_cost\_currency | コスト通貨 | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#cost-aggregation-methods">ISO-4217</Anchor>に準拠した3文字の通貨コードです。 例：USD、ZAR、EUR。</li><li>［デフォルト］：USD</li></ul> | 列挙型。 3文字 |
| <span id="af_cost_value"></span>af\_cost\_value | コスト値 | <ul><li>指定したコスト通貨でのコスト値です。</li><li>小数点以下4桁まで指定できます。</li><li>数値のみを指定してください（必要に応じて小数点を使用）。例："56"、"2.85"。</li></ul> | 数値 |
| <span id="af_sub-n-n15-example-af_sub1"></span>af\_sub[n]<br /><br />（n=1～5）例：af\_sub1 | サブパラメータ[n] | 広告主が任意で定義するカスタムパラメータです。使用方法について詳しくは、[仕様と制限事項](/docs/about-link-structure-and-parameters#仕様と制限事項)を参照してください。 | 文字列・100文字 |
| <span id="af_r"></span>af\_r | N/A | **すべてのプラットフォーム**（Android、iOS、PC）で、ユーザーを指定したURLにリダイレクトするために使用します。<br /><br />複数プラットフォーム向けリンク（OneLink）では、このパラメータは以下のように動作します。<ul><li>テンプレート単位のリダイレクト設定より優先されます。</li><li>ただし、以下のリンク単位のパラメータが、このパラメータより優先されます。<ul><li>[`af_android_url`](/docs/about-link-structure-and-parameters#af_android_url)</li><li>[`af_ios_url`](/docs/about-link-structure-and-parameters#af_ios_url)</li><li>[`af_web_dp`](/docs/about-link-structure-and-parameters#af_web_dp)</li></ul></li></ul>**注意：** リダイレクトパラメータに関するその他の[仕様と制限事項](/docs/about-link-structure-and-parameters#special-characters)も参照してください。 |  |
| <span id="af_web_dp"></span>af\_web\_dp | N/A | PC（WindowsやMacなど）のユーザーを、OneLinkテンプレートで設定したページとは別のWebページにリダイレクトするためのURLです。 PCユーザーのアトリビューションデータを、Google AnalyticsやOmnitureなどの他のプラットフォームで保持する場合に使用します。<br /><br />**注意：** リダイレクトパラメータに関するその他の[仕様と制限事項](/docs/about-link-structure-and-parameters#special-characters)も参照してください。 |  |
| <span id="af_dp"></span>af\_dp | N/A | ユニバーサルリンクやAndroid App Linksでアプリを開けない場合、またはAndroid 6.0未満の場合に使用する、アプリ起動用のURIスキームのフォールバック値です。<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">ベースパス</Anchor>（デフォルトのアクティビティ）のみを指定してください。<br /><br />**注意：** このパラメータにWeb URLを指定する場合（非推奨）は、必ずリダイレクトパラメータの[仕様と制限事項](/docs/about-link-structure-and-parameters#special-characters)を確認してください。 |  |
| <span id="af_force_deeplink"></span>af\_force\_deeplink | N/A | af\_dpの値で指定したアクティビティへの<Anchor target="_blank" href="/marketers/ja/docs/onelink-troubleshooting-and-faq">ディープリンクを強制します</Anchor>。 |  |
| <span id="af_ref"></span>af\_ref | N/A | S2Sクリックを使用するアドネットワークは、&af\_ref=**ReferrerValue**パラメータで一意のリファラ値を送信できます。<br /><br />af\_refには、以下の形式の一意の値を**必ず**指定してください。<br /><br />**NetworkName\_UniqueClickValueForEachClick**<br /><br />例：af\_ref=networkname\_123456789ABCDEF<br /><br />ネットワーク名には、有効な任意の文字列を使用できます。 networkname\_intでも、ネットワーク名だけでもかまいません。<br /><br />AppsFlyerは、Androidデバイスのアトリビューションにこのパラメータを使用する場合があります。 iOSおよびWindowsデバイスのアトリビューションには、このパラメータを使用しません。 |  |
| <span id="is_incentivized"></span>is\_incentivized | N/A | ブール値：true/false<br /><br />インセンティブ付き、またはインセンティブなしのキャンペーン |  |
| <span id="af_param_forwarding"></span>af\_param\_forwarding | N/A | <ul><li>falseに設定すると、計測リンクのパラメータがリダイレクト先のページに転送されなくなります。</li><li>リダイレクト先のURLを簡潔にしたい場合や、リダイレクト先のクエリパラメータの処理で計測リンクのパラメータが問題を起こす可能性がある場合に使用します。</li></ul> |  |
| <span id="af_base_params_forward"></span>af\_base\_params\_forward | N/A | <ul><li>falseに設定すると、計測リンクのAppsFlyerのPIDおよびCパラメータがリダイレクト先のページに転送されなくなります。</li><li>PCでクリックされるURLで、CRMに必要なパラメータは残しつつ、AppsFlyerのPIDおよびCパラメータを除外したい場合に使用します。これにより、URLに複数のPIDが含まれることを防げます。</li></ul> |  |
| <span id="af_partner_account_id"></span>af\_partner\_account\_id | アドネットワークのアカウントID | パートナー側の広告主アカウントIDです。 | 文字列・100文字 |
| <span id="af_redirect"></span>redirect | N/A | `&redirect=false`を指定すると、S2Sクリックであり、クリックしたユーザーのリダイレクトはパートナーが行うことをAppsFlyerに通知します。 |  |
| <span id="af_ua"></span>af\_ua | ユーザーエージェント | クリックやインプレッションを<Anchor target="_blank" href="/partners/ja/docs/redirecting-users-to-the-app-store">サーバー間（S2S）</Anchor>で送信するアドネットワーク向けのパラメータです。<br /><br />**重要：** クライアントからサーバー（C2S）へのリンクでは、`af_ua`を使用しないでください。 C2Sリンクで`af_ua`を使用すると、アトリビューションに影響する場合があります。<br /><br />ユーザーエージェント文字列は、以下の方法で送信します。<ol><li>URLパラメータ（URLエンコード済み）</li><li>HTTPリクエストヘッダー（エンコードなし）</li></ol>User-Agentは、**URLパラメータとHTTPヘッダーで同じ値**にしてください。<br /><br />**Androidでは**、Client Hintsによってユーザーエージェントが簡略化される場合があります。その場合も送信してください。<ul><li>**完全なユーザーエージェントの例：**`Mozilla/5.0 (Linux; Android 12; Pixel 5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.16 Mobile Safari/537.36`</li><li>**簡略化されたユーザーエージェントの例：**`Mozilla/5.0 (Linux; Android 10; K) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.0.0 Mobile Safari/537.36`</li></ul>**iOSでは**、iOS 26以降、バージョン情報が末尾に追加されます。<br />以下に例を示します。<ul><li>**追加される部分の例：**`Version/26.0.1 Mobile/15E148 Safari/604.1`</li><li>**完全なユーザーエージェントの例：**<br />`Mozilla/5.0 (iPhone; CPU iPhone OS 16_4_1 like Mac OS X) AppleWebKit/8615.1.26.10.24 (KHTML, like Gecko) Mobile/20E252 Version/26.0.1 Mobile/15E148 Safari/604.1`</li></ul> |  |
| <span id="af_ip"></span>af\_ip | IP | クリックやインプレッションを<Anchor target="_blank" href="/partners/ja/docs/redirecting-users-to-the-app-store">サーバー間</Anchor>で送信するアドネットワーク向けのパラメータです。<br /><br />**重要：** クライアントからサーバー（C2S）へのリンクでは、`af_ip`を使用しないでください。 C2Sリンクで`af_ip`を使用すると、アトリビューションに影響する場合があります。<br /><br />**デバイスのIPアドレス**<br /><br />**推奨：** 取得可能な場合は、`af_ip`パラメータにデバイスのIPアドレスを指定してください。<br /><br />**次の選択肢：** 利用可能な場合、AppsFlyerはX-Forwarded-For内のIPアドレスを使用します。 |  |
| <span id="deprecated--af_os"></span>［非推奨］af\_os | OSバージョン | ［iOSのみ］デバイスのOSバージョンです。<br /><br />このパラメータは非推奨ですが、AppsFlyerは引き続き対応しています。推奨：代わりにaf\_os\_versionパラメータを使用してください。 |  |
| <span id="af_os_version"></span>af\_os\_version | OSバージョン | <ul><li>クリックやインプレッションを<Anchor target="_blank" href="/partners/ja/docs/redirecting-users-to-the-app-store">サーバー間</Anchor>で送信するアドネットワーク向けのパラメータです。</li><li>デバイスのOSバージョンです。<ul><li>Android：<ul><li>例：12</li><li>ユーザーエージェントが簡略化されている場合（PCまたはAndroidでChrome 110以降のエンジンを使用するブラウザの場合）、アドネットワークは<Anchor target="_blank" href="https://web.dev/migrate-to-ua-ch/">Client Hints API</Anchor>でこの値を取得する必要があります。</li><li>ユーザーエージェントが簡略化されて**いない**場合は、以下の正規表現で文字列からAndroidのOSバージョンを抽出します：`(\d+(?:\.\d+)*);(?:\s..-..;)?\s(.+?(?=\)\|\s\w*\/))`。</li></ul></li><li>iOS：<ul><li>正確に計測するため、OSバージョンは省略せずに指定してください。例：18.6.2</li></ul></li></ul></li></ul> |  |
| <span id="af_model"></span>af\_model | デバイスモデル | <ul><li>クリックやインプレッションを<Anchor target="_blank" href="/partners/ja/docs/redirecting-users-to-the-app-store">サーバー間</Anchor>で送信するアドネットワーク向けのパラメータです。</li><li>デバイスのモデルです。<ul><li>Android：<ul><li>例：Pixel 5</li><li>ユーザーエージェントが簡略化されている場合（PCまたはAndroidでChrome 110以降のエンジンを使用するブラウザの場合）、アドネットワークは<Anchor target="_blank" href="https://web.dev/migrate-to-ua-ch/">Client Hints API</Anchor>でこの値を取得する必要があります。</li><li>ユーザーエージェントが簡略化されて**いない**場合は、以下の正規表現で文字列からAndroidのモデルを抽出します：`(\d+(?:\.\d+)*);(?:\s..-..;)?\s(.+?(?=\)\|\s\w*\/))`。</li></ul></li><li>iOS：<ul><li>正確に計測するため、デバイスモデルの識別子は省略せずに指定してください。例：`iphone15,1`または`ipad14,2`。</li></ul></li></ul></li></ul> |  |
| <span id="af_media_type"></span>af\_media\_type | メディアタイプ | リンクを設定した広告の掲載場所を、以下の値で指定します。<ul><li>app：アプリ内のリンク</li><li>web：モバイルWebサイト内のリンク</li></ul> |  |
| <span id="deep_link_sub110"></span>deep\_link\_sub1-10 | N/A | 追加のディープリンク値です。開発者は、値に応じた動作をコードに実装します。 |  |
| <span id="deep_link_value"></span>deep\_link\_value | N/A | ユーザーの移動先となる、アプリ内の特定のコンテンツを示す名前です。開発者は、deep\_link\_valueに応じた動作をコードに実装します。 |  |
| <span id="af_og_title"></span>af\_og\_title | N/A | SNSにリンクを投稿した際、Open Graph（OG）タイトルの値がタイトルのプレビューに使用されます。 | 文字列・40文字 |
| <span id="af_og_description"></span>af\_og\_description | N/A | SNSにリンクを投稿した際、Open Graph（OG）説明文の値が説明文のプレビューに使用されます。 | 文字列・300文字 |
| <span id="af_og_image"></span>af\_og\_image | N/A | SNSにリンクを投稿した際、Open Graph（OG）画像の値が画像のプレビューに使用されます。 |  |

<div id="attribution-link-parametersretargeting-only" />

### 計測リンクのパラメータ｜リターゲティング専用

| パラメータ | ローデータでの表示名 | 説明 | フィールドの型と長さ |
| --- | --- | --- | --- |
| <span id="is_retargeting"></span>is\_retargeting | リターゲティングの有無（キャンペーン） | すべてのリターゲティングキャンペーンのクリックURLに、`&is_retargeting=true`を含める必要があります。  <br />このパラメータがない場合や値が"false"の場合、通常のユーザー獲得キャンペーンとして扱われます。 | 列挙型・5文字 |
| <span id="af_reengagement_window"></span>af\_reengagement\_window | リエンゲージメント期間 | 計測リンクにこのパラメータを追加して、<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide#reengagement-rules-and-windows">リエンゲージメント期間</Anchor>を変更できます。<br /><br />指定可能な期間は以下のとおりです。<ul><li>日数：1～90日、または時間：1～36時間</li><li>Lifetime：リエンゲージメント期間を無期限にします。例：`&af_reengagement_window=lifetime`</li></ul>デフォルト値：30日<br /><br />例：`&af_reengagement_window=30d`を指定すると、リエンゲージメント期間は30日になります。 | N/A |

<div id="viewability-parameters" />

### ビューアビリティのパラメータ

広告タイプに応じて、広告接触の詳細を示すビューアビリティのパラメータも送信できます。

| パラメータ | 値の形式 | 説明 |
| --- | --- | --- |
| <span id="af_video_total_length"></span>af\_video\_total\_length | 秒 | 動画全体の再生時間 |
| <span id="af_video_played_length"></span>af\_video\_played\_length | 秒 | 動画の視聴時間 |
| <span id="af_playable_played_length"></span>af\_playable\_played\_length | 秒 | プレイアブル要素の読み込み完了後に操作された時間 |
| <span id="af_ad_time_viewed"></span>af\_ad\_time\_viewed | 秒 | 広告が画面に表示されていた時間 |
| <span id="af_ad_displayed_percent"></span>af\_ad\_displayed\_percent | % | デバイスの画面に表示された広告領域の割合の最大値 |
| <span id="af_audio_total_length"></span>af\_audio\_total\_length | 秒 | 音声全体の再生時間 |
| <span id="af_audio_played_length"></span>af\_audio\_played\_length | 秒 | 音声の聴取時間 |

<div id="android-specific-parameters" />

### Android専用のパラメータ

| パラメータ | ローデータでの表示名 | 説明 | フィールドの型 |
| --- | --- | --- | --- |
| <span id="advertising_id"></span>advertising\_id | 広告ID | Google広告ID。アドネットワーク側の対応が必要です。 | 最大40文字 |
| <span id="sha1_advertising_id"></span>sha1\_advertising\_id | N/A | SHA1でハッシュ化したGoogle広告ID。アドネットワーク側の対応が必要です。 |  |
| <span id="md5_advertising_id"></span>md5\_advertising\_id | N/A | MD5でハッシュ化したGoogle広告ID。アドネットワーク側の対応が必要です。 | インストールとリアトリビューションにのみ対応しています。 |
| <span id="android_id"></span>android\_id | Android ID | デバイスのAndroid\_id。アドネットワーク側の対応が必要です。 | 最大20文字 |
| <span id="sha1_android_id"></span>sha1\_android\_id | N/A | SHA1でハッシュ化したデバイスのAndroid\_id。アドネットワーク側の対応が必要です。 |  |
| <span id="md5_android_id"></span>md5\_android\_id | N/A | MD5でハッシュ化したデバイスのAndroid\_id。アドネットワーク側の対応が必要です。 | インストールとリアトリビューションにのみ対応しています。 |
| <span id="imei"></span>imei | IMEI | デバイスのIMEI ID。 |  |
| <span id="sha1_imei"></span>sha1\_imei | N/A | SHA1でハッシュ化したデバイスのIMEI ID。アドネットワーク側の対応が必要です。 |  |
| <span id="md5_imei"></span>md5\_imei | N/A | MD5でハッシュ化したデバイスのIMEI ID。アドネットワーク側の対応が必要です。 |  |
| <span id="oaid"></span>oaid | OAID | Open Anonymous Device Identifier（匿名のデバイス識別子） | Android SDK V4.10.3以降で利用できます。 |
| <span id="sha1_oaid"></span>sha1\_oaid | N/A | SHA1でハッシュ化したOpen Anonymous Device Identifier。アドネットワーク側の対応が必要です。 | Android SDK V4.10.3以降で利用できます。 |
| <span id="md5_oaid"></span>md5\_oaid | N/A | MD5でハッシュ化したOpen Anonymous Device Identifier。アドネットワーク側の対応が必要です。 | Android SDK V4.10.3以降で利用できます。 |
| <span id="af_android_url"></span>af\_android\_url | N/A | Androidユーザーを、Google Playのアプリページとは別のURLにリダイレクトします。<Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution#単一管理画面-vs-ストアごとの管理画面">サードパーティのアプリストア</Anchor>への誘導に使用します。<br /><br />**注意：** リダイレクトパラメータに関するその他の[仕様と制限事項](/docs/about-link-structure-and-parameters#special-characters)も参照してください。 |  |
| <span id="sha1_el"></span>sha1\_el | N/A | PCからモバイルへのアトリビューションに使用する、SHA1でハッシュ化したメールアドレスです。アドネットワーク側の対応が必要です。 |  |
| <span id="fire_advertising_id"></span>fire\_advertising\_id | N/A | Amazon Fire広告ID |  |
| <span id="af_android_store_csl"></span>af\_android\_store\_csl | store\_product\_page | Google Consoleのカスタムストア掲載情報 | 文字列 |

<div id="ios-specific-parameters" />

### iOS専用のパラメータ

| パラメータ | 表示名 | 説明 |
| --- | --- | --- |
| <span id="idfa"></span>idfa | IDFA | 大文字を使用してください。アドネットワーク側の対応が必要です。<br /><br />フィールドの長さ：最大40文字 |
| <span id="idfv"></span>idfv | IDFV | 大文字を使用してください。 |
| <span id="af_ios_url"></span>af\_ios\_url |  | iOS（iPhoneまたはiPad）ユーザーを、iTunesのアプリページとは別のURLへ誘導する、ランディングページへのリダイレクトに使用します。<br /><br />**注意：** リダイレクトパラメータに関するその他の[仕様と制限事項](/docs/about-link-structure-and-parameters#special-characters)も参照してください。 |
| <span id="af_ios_store_cpp"></span>af\_ios\_store\_cpp | store\_product\_page | カスタムプロダクトページID（ppid）<br /><br />**注意：** ローデータと集計レポートでは、af\_ios\_store\_cpp（カスタムプロダクトページID）の値はクリックには記録されますが、インプレッションには記録されません。 |
| <span id="af_ios_fallback--deprecated"></span>af\_ios\_fallback［非推奨］ | N/A | **非推奨**：ユーザーは<Anchor target="_blank" href="/marketers/ja/docs/uri-scheme-fallback-for-ios">iOSのURIスキームのフロー</Anchor>に基づいてリダイレクトされます。 |
| <span id="sha1_idfa"></span>sha1\_idfa | N/A | SHA1でハッシュ化したIDFAです。アドネットワーク側の対応が必要です。 |
| <span id="sha1_idfv"></span>sha1\_idfv | N/A | SHA1でハッシュ化したIDFVです。 |
| <span id="mac"></span>mac | N/A | デバイスのMACアドレスです。アドネットワーク側の対応が必要です。 |
| <span id="md5_idfa"></span>md5\_idfa | N/A | MD5でハッシュ化したIDFAです。 |
| <span id="md5_idfv"></span>md5\_idfv | N/A | MD5でハッシュ化したIDFVです。 |
| <span id="sha1_mac"></span>sha1\_mac | N/A | SHA1でハッシュ化したデバイスのMACアドレスです。アドネットワーク側の対応が必要です。 |

<div id="example" />

> 📄 **例**
>
> ```http
> https://app.appsflyer.com/{app_id}/?pid=airpush_int&c=RedBanner&
> 	  af_siteid={publisher_id}&af_sub1=1.5&af_sub2=USD&af_sub3=burst_campaign
> ```

すべてのパラメータは、<Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">インストールレポート</Anchor>および<Anchor target="_blank" href="/marketers/ja/docs/analytics-and-aggregate-reporting-apis">分析、レポート、API</Anchor>で確認できます。

<div id="custom-parameters" />

### カスタムパラメータ

Android専用およびiOS専用の標準パラメータに加えて、カスタムパラメータも指定できます。カスタムパラメータを使用すると、インストールにつながった計測リンクに応じて、ユーザー体験やコンテンツをカスタマイズできます。

`parameter=value`の形式で、計測リンクにカスタムパラメータを追加できます。例：

```http
https://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&af_adset=coats&af_ad=cashmere&my_custom_param=my_custom_value
```

カスタムパラメータには、以下の2つの注意点があります。

* カスタムパラメータはローデータには表示されません。
* カスタムパラメータは、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">コンバージョンデータを取得するSDK API</Anchor>から取得できます。

<div id="partner-id-pid-parameter" />

<Accordion title="パートナーID（PID）パラメータ">

計測リンクで使用できるパラメータのうち、PIDは必須です。 PIDは、AppsFlyerがメディアソースに割り当てる一意の識別子です。

各<Anchor target="_blank" href="http://appsflyer.com/partners">連携済みパートナー</Anchor>には、末尾が*{"_int"}* の一意のPIDが割り当てられています。 <Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLinkリンク</Anchor>では、連携済みパートナー用に予約されていない値であれば、PIDを任意に設定できます。

<div id="note" />

> 📘 **注意**
>
> メールやSMSなどのカスタムメディアソースで、予約済みの<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns#srn媒体">SRN</Anchor>名をPIDに使用した計測リンクは、AppsFlyerによってブロックされます。 この制限は、アドバンスSRNには適用**されません**。

主な予約済みのパブリッシャーIDには、organic、googleadwords\_int（Google AdWords）、facebook\_int（Meta広告）、twitter\_int（X広告）などがあります。メール、SMS、伝書鳩などの未連携の流入元には、任意の名前を使用できます。

<div id="avoid-common-pid-issues" />

#### PIDでよくある問題の防止

* **計測リンクには必ずPIDを含めてください。** 計測リンクにPIDがない場合、ユーザーのメディアソースは自動的に「None」となり、元のインストールの流入元を把握できなくなります。
* **連携済みの流入元では**、インストールを正しく計測するため、その流入元に指定されたPIDのみを使用してください。
* **カスタムの流入元では、連携済みパートナーのPIDを使用しないでください。** メール、SMS、Facebookで自然拡散した無償の投稿などのカスタムメディアソースには、連携済みパートナーと異なるPID値を使用してください。たとえば、owned\_email、sms\_pushなど、連携済みパートナーの名前と一致しない独自の識別子を使用します。
* <strong>使用可能な文字のみを指定してください。</strong>計測リンクのPIDパラメータに、/&lt;>*&?\のいずれかが含まれる場合、以下のようになります。
  * クリックやインストールが、ダッシュボードで***af\_invalid\_param***として表示されます。
  * 計測リンクによるアトリビューションが行われません。
  * クリック時にディープリンクが機能しません。

<div id="tip" />

> 👍 **ヒント**
>
> PID値にスペースを含めないでください。含める場合は、計測リンクを使用する前に必ずURLエンコードしてください。

</Accordion>

<div id="site-id-parameter" />

<Accordion title="サイトIDパラメータ">

サイトIDは、広告を配信するパブリッシャーを識別する一意のIDです。つまり、広告を表示するWebサイトやアプリを示します。アドネットワークは、パブリッシャーごとに一意のサイトIDを割り当てます。

このIDは、計測リンクの`af_siteid`パラメータでAppsFlyerに送信され、各種ダッシュボード、レポート、ポストバックで確認できます。

以下の理由から、計測リンクでサイトIDをAppsFlyerに送信する必要があります。

* 広告の掲載先を明確にし、透明性を確保するため。
* AppsFlyerによる、不正なパブリッシャーやその他のトラフィックのグループの特定・排除に使用するため。

サイトIDパラメータには、広告を配信するパブリッシャーのIDのみを含めます。

バナー、インタースティシャル、動画などの広告タイプや、アプリ内の掲載位置に関する追加情報には、サブサイトIDパラメータを使用してください。

<div id="example-1" />

> 📄 **例**
>
> 以下の計測リンクには、次の情報が含まれます。
>
> * `af_siteid`（サイトID）：パブリッシャーID
> * `af_sub_siteid`（サブサイトID）：追加のID情報（この例では、アフィリエイトの流入元と広告タイプ・掲載位置）
>
> `https://app.appsflyer.com/com.yourapp?pid=mediaName_int&clickid={clickid}&advertising_id={gaid}&af_siteid=1234&af_sub_siteid=ABCD_4567`
>
> リンク例の各値の意味は、以下のとおりです。
>
> * 1234＝パブリッシャーID
> * ABCD＝パブリッシャーが提携するアフィリエイトの流入元（サブパブリッシャー）
> * 4567＝バナー、インタースティシャル、動画など、アプリ内の広告タイプ・掲載位置

<div id="faq-why-does-traffic-result-in-many-blocked-installs" />

#### **よくある質問：インストールが大量にブロックされるのはなぜですか？**

以下の理由で、インストールがブロックされる場合があります。

* **サイトIDがない：** クリックURLの`af_siteid`パラメータが空です。サイトIDが空の広告接触の送信は、技術的な問題、または不正検知の仕組みを意図的に回避しようとしている可能性を示します。
* **複数のサイトIDを使用している：** 同じパブリッシャーについて、複数のクリックURLで異なるサイトIDが送信されています。これは、パブリッシャーの実際の活動を隠す不正行為とみなされ、多くの場合、<Anchor target="_blank" href="https://www.appsflyer.com/blog/click-flooding-detection-false-positive-challenge/">クリック洪水</Anchor>に関連しています。
* **サイトIDの形式が不適切：** 不適切な形式での送信に他の不正の兆候が重なると、特定のパブリッシャーだけでなく、より上位のグループ単位でブロックされ、パートナーのトラフィックの広い範囲に影響する場合があります。

インストールのブロックを防ぐため、例に示すとおり、パブリッシャーごとに単一のサイトIDを送信してください。

</Accordion>

<div id="levels-of-data-granularity" />

## データの詳細度の階層

最大4つのURLパラメータを使用して、広告のパフォーマンスを詳しく分析できます。

使用中のすべての計測リンクに4つのパラメータをすべて含めると、以下が可能になります。

* すべてのユーザーのインストールとイベントを、個々の広告に紐付ける。
* 集計レポートで広告セット別、キャンペーン別、メディアソース別に掘り下げ、各広告のパフォーマンスを比較して、それぞれの階層で最適化する。
* ローデータレポートと<Anchor target="_blank" href="/marketers/ja/docs/pivot-table-user-metrics">ピボットテーブル</Anchor>で、すべてのメディアソースの広告を比較する。

対象のパラメータは以下のとおりです。

* `メディアソース（pid=）`
* `キャンペーン名（c=）`
* `広告セット（af_adset=）`
* `広告名（af_ad=）`

<div id="example-2" />

> 📄 **例**
>
> 以下の計測リンクでは、連携済みメディアソース「network」の「winter」キャンペーンにある「coats」広告セット内の「cashmere」広告を、4階層の情報で記録しています。
>
> ```http
> https://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&
> af_adset=coats&af_ad=cashmere
> ```

<div id="frequently-asked-questions" />

## よくある質問

<div id="should-i-use-lower-or-upper-case-letters-for-parameters" />

<Accordion title="パラメータでは大文字と小文字のどちらを使用すべきですか？">

どちらも使用できますが、表記を統一する必要があります。カスタムパラメータで大文字・小文字を指定した場合は、常に同じ表記で使用してください。

たとえば、pid=MyMediaSourceと設定した場合は、常にその表記を使用します。ある計測リンクでpid=MyMediaSource、別のリンクでpid=mymediasourceを使用すると、データに差異が生じる場合があります。計測リンクに設定する他のパラメータも同様です。

</Accordion>

<div id="is-the-appsflyer-attribution-link-dynamic-or-static" />

<Accordion title="AppsFlyerの計測リンクは動的ですか、それとも静的ですか？">

計測リンクには、動的なものと静的なものがあります。  
動的か静的かは、どのように見分けられますか？  
**パラメータを含む計測リンク**は、値があらかじめ定められた長いリンクであり、**静的**です。  
カスタム計測リンクで使用する**短縮URLのみ**（例：`yourbrand.onelink.me/HaT8/r5c2b371`）が**動的**です。  
つまり、連携済みパートナー用の計測リンクやオウンドメディア用の長いURLは、使用を開始した後にAppsFlyerの管理画面で設定値を変更しても、そのリンクを利用するユーザーに適用される値は変わりません。変更を反映するには、それ以降、新しい長いURLを使用する必要があります。  
一方、オウンドメディア用の短縮URLは、パラメータを直接含みません。見込みユーザーがAppsFlyerの短縮URLに反応すると、AppsFlyerにリダイレクトされ、その時点で設定されているパラメータが動的に適用されます。

</Accordion>

<div id="what-is-this-play-store-error-message" />

<Accordion title="Playストアでこのエラーメッセージが表示されるのはなぜですか？">

計測リンクを開いた後、Playストアで以下のエラーメッセージが表示される場合があります。

![TL_error_message.png](https://files.readme.io/03e509d3cbe68aa0621bb0f43ab113c25a8427e70826c5af5258f1fc9e3f3d36-360000002485.png)

これは、計測リンクに#が含まれているためです。例：

```http
https://app.appsflyer.com/com.travelco?pid=globalwide_int&clickid=#reqid#
```

通常、これらの文字はマクロとしてリンクに含まれ、実際には値に動的に置き換えられるため、大きな問題はなく、メッセージは無視できます。

</Accordion>

<div id="what-are-subscriber-parameters-good-for" />

<Accordion title="サブパラメータは何に役立ちますか？">

サブパラメータ（af\_sub1、af\_sub2、…、af\_sub\_5）を使って、必要なKPIを記録できます。これらのパラメータは解析されてローデータレポートに表示されるため、データの集計や絞り込みに便利です。

<div id="example-3" />

> 📄 **例**
>
> 配車アプリのLuberでは、青、黄、赤の3色のテンプレートを使ったクリエイティブを配信しています。 Luberのモバイルマーケティング担当者Lindaは、最も多くのインストールにつながる色を検証したいと考えています。そこで、すべての非SRNメディアソースで配信している青い広告の計測リンクに、`&af_sub3=blue`を追加します。黄色と赤の広告にも、同様に対応します。この情報が解析されてローデータレポートに表示されるため、Lindaは色別の広告の成果を分析し、コンバージョン率が最も高い色を選べます。

</Accordion>

<div id="what-limits-are-there-on-campaign-names" />

<Accordion title="キャンペーン名にはどのような制限がありますか？">

* 計測リンクのURLで指定するキャンペーン名は、最大100文字です。上限を超えると、キャンペーン名は`c_name_exceeded_max_length`に変更されます。
* ダッシュボードやレポートに差異が生じる場合があるため、キャンペーン名の先頭や末尾にスペースを含めないでください。

</Accordion>

<div id="traits-and-limitations" />

## 仕様と制限事項

| 項目 | 備考 |
| --- | --- |
| <span id="special-characters"></span>特殊文字 | パラメータのキーと値には、以下の特殊文字を使用できません（redirectとaf\_dpパラメータを除く）： ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, &lt;, /, \{, \}, %, ),( |
| <span id="redirection-parameters"></span>リダイレクトパラメータ | <ul><li>リダイレクト先URLのドメインが、<Anchor target="_blank" href="/marketers/ja/docs/set-up-your-domain-redirect-allowlist">リダイレクト許可リスト</Anchor>に追加されていることを確認してください。</li><li>リダイレクト先には、<Anchor target="_blank" href="https://datatracker.ietf.org/doc/html/rfc1738">RFC 1738</Anchor>に準拠した、外部からアクセスできる完全な有効なWeb URL（https://[domain][optional-path]）を指定する必要があります。</li><li>リダイレクトURLでは、<Anchor target="_blank" href="https://en.wikipedia.org/wiki/URI_fragment">URIフラグメント識別子</Anchor>（記事内の特定のセクションへスクロールする#webpagesectionなど）には**対応していません**。</li></ul> |
| <span id="url-characteravailable"></span>URLの文字数上限 | URL全体の長さは2,000文字以内にしてください。 |
| <span id="agencies"></span>AndroidのSNSアプリのWebViewでのディープリンクによるリダイレクト | 制限の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#android-social-apps-webview-deep-linking-redirection">こちら</Anchor>を参照してください。 |
| <span id="deep-linking-is-not-supported-in-the-android-naver-blog-app"></span>AndroidのNaver Blogアプリではディープリンクに非対応 | AndroidのNaver Blogアプリでは、ディープリンクに対応していません。ユーザーは、リンクの設定に応じてGoogle PlayストアまたはWebにリダイレクトされます。 |
| <span id="a-popup-appears-when-clicking-on-a-uri-scheme-link-from-chrome-browser-on-ios"></span>iOSのChromeでURIスキームのリンクをクリックするとポップアップが表示される | iOS版Chromeの仕様変更により、ユーザーがURIスキームのリンクをクリックすると、アプリを開くか、App Storeに移動するかを確認するポップアップが表示されます。 |
| <span id="uri-scheme-validity-requirements"></span>URIスキームの有効性に関する要件 | <Anchor target="_blank" href="https://www.rfc-editor.org/rfc/rfc3986#section-3.1">RFC 3986</Anchor>に準拠した有効なURIスキームの使用を推奨します。準拠していないスキームは、WebViewなどのWeb環境からクリックした際、アプリを開けず、エラーになる場合があります。 |
| <span id="telegram-webview-attribution"></span>TelegramのWebViewでのアトリビューション | 制限の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#telegram-webview">こちら</Anchor>を参照してください。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 01H8GN1XXC5T2ENFHBK0G4WQ1P=%E6%A6%82%E8%A6%81 01JENAANV4KTRF882JMEM5N91A=%E9%87%8D%E8%A6%81 attribution-link-parameters=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF 01H8GN1XXDX1XMQ1GJTHCP425D=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF attribution-link-parameters%E2%80%94ua-and-retargeting=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BFua%E3%81%A8%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 01H8GN1XXDEWPB2MPP3KJVPRJV=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BFua%E3%81%A8%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 af_sub%5Bn%5D%C2%A0%0An15-example-af_sub1=af_sub-n-n15-example-af_sub1 %5Bdeprecated%5D-af_os=deprecated--af_os attribution-link-parameters%E2%80%94retargeting-only=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E5%B0%82%E7%94%A8 01H8GN1XXD9X7CWZJN43PSS94R=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E5%B0%82%E7%94%A8 viewability-parameters=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%A2%E3%83%93%E3%83%AA%E3%83%86%E3%82%A3%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF 01H8GN1XXETQEYT39F05ZYX4E2=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%A2%E3%83%93%E3%83%AA%E3%83%86%E3%82%A3%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF androidspecific-parameters=android%E5%B0%82%E7%94%A8%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF 01H8GN1XXEE9RGSB1H72H025Z4=android%E5%B0%82%E7%94%A8%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF iosspecific-parameters=ios%E5%B0%82%E7%94%A8%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF 01H8GN1XXESJ9VE3W8CYKRFFYX=ios%E5%B0%82%E7%94%A8%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF af_ios_fallback-%5Bdeprecated%5D=af_ios_fallback--deprecated 01H8GN1XXEFRSQSERTB6ARC773=%E4%BE%8B custom-parameters=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF 01H8GN1XXEB58JN4SV9HX1ZV6S=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF 01H8GN1XXE8EXMMKDZMJ2WNNH5=partner-id-pid-parameter h_01JRX48BX8W9V9XWPB1DSG4H8Y=%E6%B3%A8%E6%84%8F avoid-common-pid-issues=pid%E3%81%A7%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E5%95%8F%E9%A1%8C%E3%81%AE%E9%98%B2%E6%AD%A2 01H8GN1XXEXTGC4M8AMJ256Q9G=pid%E3%81%A7%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E5%95%8F%E9%A1%8C%E3%81%AE%E9%98%B2%E6%AD%A2 01H8GN1XXEGNVX9GM5JYBMBGCF=%E3%83%92%E3%83%B3%E3%83%88 01H8GN1XXEVG65YP782CM37RES=site-id-parameter 01H8GN1XXED2MVSNRXN11KZ955=%E4%BE%8B-1 faq-why-does-traffic-result-in-many-blocked-installs=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%8C%E5%A4%A7%E9%87%8F%E3%81%AB%E3%83%96%E3%83%AD%E3%83%83%E3%82%AF%E3%81%95%E3%82%8C%E3%82%8B%E3%81%AE%E3%81%AF%E3%81%AA%E3%81%9C%E3%81%A7%E3%81%99%E3%81%8B 01H8GN1XXEK0G9TDW8WHWM17HK=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%8C%E5%A4%A7%E9%87%8F%E3%81%AB%E3%83%96%E3%83%AD%E3%83%83%E3%82%AF%E3%81%95%E3%82%8C%E3%82%8B%E3%81%AE%E3%81%AF%E3%81%AA%E3%81%9C%E3%81%A7%E3%81%99%E3%81%8B levels-of-data-granularity=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E8%A9%B3%E7%B4%B0%E5%BA%A6%E3%81%AE%E9%9A%8E%E5%B1%A4 01H8GN1XXE4RF9J0APAAKD1WEG=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E8%A9%B3%E7%B4%B0%E5%BA%A6%E3%81%AE%E9%9A%8E%E5%B1%A4 01H8GN1XXEHPFKX7V0RRW2MH2G=%E4%BE%8B-2 frequently-asked-questions=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HN0JW166VHR33T8VVVY47F9P=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F 01H8GN1XXEND9X8YVRQE1YFA5W=should-i-use-lower-or-upper-case-letters-for-parameters 01H8GN1XXER749PH4Z14A7AJ0F=is-the-appsflyer-attribution-link-dynamic-or-static 01H8GN1XXEPQTY0XNW6EZSA9ZN=what-is-this-play-store-error-message 01H8GN1XXFYAFYFX9MNBP6D35B=what-are-subscriber-parameters-good-for 01H8GN1XXFEFA498J22GRF5F8G=%E4%BE%8B-3 01H8GN1XXFS1DFS3HAHVTVG93A=what-limits-are-there-on-campaign-names traits-and-limitations=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HN0JW166WH76A5SM293PGKX6=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />
