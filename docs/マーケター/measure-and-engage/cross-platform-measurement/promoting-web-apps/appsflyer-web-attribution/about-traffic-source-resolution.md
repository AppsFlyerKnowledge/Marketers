---
title: ［Beta機能］トラフィックソース判定について
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T13:46:22Z'
  edited_at: '2026-10-14T09:23:06Z'
  id: 43518064765201
  locale: ja
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ja/articles/43518064765201
---
概要：

トラフィックソース判定を利用すると、ランディングページの読み込み時点で取得可能なURLパラメータやリファラーデータをもとに、各Web訪問の流入元メディアソース、キャンペーン、およびチャネルを特定できます。これにより、その後発生するユーザー獲得イベントを含むWebイベントを正確にアトリビューションするために必要な流入元情報を取得できます。

<div id="what-is-traffic-source-resolution" />

## トラフィックソース判定とは

Webアトリビューションにおいて、ランディングページの読み込み（**Web訪問**）は、ユーザーがWebサイトと最初に接触するタイミングです。AppsFlyerは、その時点で利用可能なURLパラメータやリファラー情報をもとに、ユーザーのメディアソース、キャンペーン、およびチャネルを特定します。

このプロセスは**トラフィックソース判定**と呼ばれ、URLパラメータからメディアソースおよびキャンペーン情報を特定・解決します。AppsFlyerはこれらのパラメータを取得し、優先順位付けを行うことで、その訪問における初期の流入元情報を決定します。

トラフィックソース判定は、**アトリビューション前に実行されるプロセス**です。そのため、この段階で判定されたパラメータは、後続の<Anchor target="_blank" href="/marketers/ja/docs/web-performance-measurement-overview#web-performance-measurementのフロー">アトリビューション処理</Anchor>によって上書きされる場合があります。

また、トラフィックソース判定の役割は訪問時点だけにとどまりません。その結果は、その後のアトリビューション処理で利用される流入元情報として保持され、ユーザー獲得イベントを含む後続のWebイベントのアトリビューションに利用されます。

正確なURLを構築するためには、トラフィックソース判定の仕組みを理解することが重要です。適切なランディングページURLの作成方法については、<Anchor target="_blank" href="/marketers/ja/docs/choose-attribution-parameters-for-landing-page-urls">Choose attribution parameters for landing page URLs</Anchor> を参照してください。

<div id="the-traffic-source-resolution-flow" />

## トラフィックソース判定の流れ

トラフィックソース判定は、Web訪問ごとのアトリビューション情報を段階的に構築する、複数ステップからなるプロセスです。各ステップでは、訪問の記録から始まり、流入元の特定、キャンペーン情報の解決、レポート用チャネル分類まで、それぞれ異なる役割を担います。トラフィックソース判定で利用されるデータは、Web SDKまたはWeb S2Sによって取得されます。

このプロセスは以下のステップで構成されています：

1. [サイト訪問の記録](#ステップ１サイト訪問の計測)：ユーザーのWebサイトへの流入を検知し、流入元がまだ判明していない場合でも訪問イベントを記録します。これにより、アトリビューションロジックが適用される前に、対象となるすべての流入を計測できます。
2. [メディアソース判定](#ステップ２メディアソースの判定)：URLパラメータおよびリファラー情報を分析し、訪問を発生させた広告プラットフォームまたはパートナーを特定します。該当する流入元がない場合はオーガニック流入と判定します。
3. [キャンペーン判定](#ステップ３キャンペーン情報の判定)：特定されたメディアソースに紐づく詳細なキャンペーン情報を判定し、詳細なパフォーマンス分析を可能にします。
4. [チャネル分類](#ステップ4チャネル分類)：判定されたメディアソースに基づき、訪問を上位レベルのトラフィックチャネルへ分類します。これにより、レポートや分析において統一された分類軸を利用できます。

<div id="step-1-visit-recording" />

## ステップ１：サイト訪問の計測

サイト訪問の記録は、Webパフォーマンスの計測フローにおける最初のステップです。この処理はメディアソース判定およびアトリビューション処理より前に実行され、生のユーザーアクティビティを取得する前処理レイヤーとして機能します。

このロジックは2段階で構成されています。まず、**リファラー**（ユーザーがサイトへ訪問する前にいたドメイン）を分類します。次に、リファラーの種類に応じて、ユーザーセッションの状態およびメディアソース情報の有無を評価し、訪問を記録するかどうかを判断します。

<div id="stage-1-referrer-classification" />

#### ステージ１：リファラーの分類

AppsFlyerはリファラーを以下の3種類に分類します：

* **外部除外リファラー**（例：決済代行サービスや、除外した任意のドメインなど）
* **内部除外リファラー**（例：独自のサブドメインやログインフローなど）
* **その他**（上記以外のすべてのリファラー）

<div id="stage-2-session-evaluation-and-visit-recording" />

#### ステージ２：セッション評価と訪問記録

リファラーの種類に基づいて、AppsFlyerはセッション状態を評価し、訪問を記録するかどうかを判断します。

* **外部除外リファラー：** 訪問は記録されません。
* **内部除外リファラー：** リファラーは実際の獲得元ではないため、リファラーに基づくアトリビューションは無効化されます。
  * アクティブなセッションが存在する場合（セッションは30分間アクティビティがないと非アクティブとみなされ、それ以外はアクティブとみなされます）、訪問は記録されません。
  * アクティブなセッションが存在しない場合、訪問は記録されます。ただし、リファラーは自己リファラルとして扱われ、無視されます。URLにアトリビューションパラメータ（UTM、PID、クリックIDなど）が含まれていない限り、この訪問はオーガニックとして記録されます。
* **その他：**
  * アクティブなセッションが存在しない場合、訪問を記録します。新しいセッションは、他の条件に関係なく新規訪問として扱われます。
  * アクティブなセッションが存在し、かつダイレクト流入以外のメディアソース情報（UTM、PID、クリックIDなど）が存在する場合、訪問を記録します。この再訪問はリターゲティングコンバージョン（リエンゲージメント）を発生させる可能性があり、その後のイベントのアトリビューションに利用されます。
  * アクティブなセッションが存在し、かつメディアソース情報が存在しない場合、そのセッション内では新しい訪問は記録されません。

<Image align="center" alt="traffic resolution flow" src="https://files.readme.io/d5f807d5ced5ed9a90a41cda0f38fe7ffef0b81c321bae90ad410076b484c810-47195479783953.png" width="1494px" />

<div id="step-2-media-source-resolution" />

## ステップ２：メディアソースの判定

メディアソース判定では、サイト訪問を以下のいずれかに分類します。

* **非オーガニック：** 特定のアトリビューション元が特定された場合
* **オーガニック：** アトリビューション元が特定できなかった場合（例：ユーザーがURLを直接入力した場合や、ブックマークからアクセスした場合）

メディアソース判定では、AppsFlyerはランディングページURLのパスおよびクエリ文字列から取得したパラメータを評価し、Web訪問の流入元を特定します。

最も詳細かつ柔軟な計測を行うには、`pid`や`af_campaign`などのAppsFlyerの専用パラメータを使用することを推奨します。また、AppsFlyerはUTMパラメータやクリックIDなどの業界標準パラメータにも対応しているため、既存の広告計測設定を変更することなく利用を開始できます。

AppsFlyerは、あらかじめ定義された優先順位に従ってメディアソースを判定します。メディアソースが特定された時点で、それ以降の判定処理は実行されません。メディアソース判定は、以下の手順で行われます：

<Accordion title="1. 除外ドメイン">

最初に、AppsFlyerは訪問元ドメインが**除外ドメインリスト**に登録されているか確認します。ドメインが除外対象（例：自社ドメインやPayPalなどの決済サービス）である場合、その訪問は自動的に無視されるか、**オーガニック**として分類されます。

Webアプリ追加時の除外ドメイン設定については、<Anchor target="_blank" href="/marketers/ja/docs/configure-web-performance-measurement-settings#除外ドメイン">除外ドメインのページ</Anchor>を参照してください。

</Accordion>

<Accordion title="2. AppsFlyer PID（パートナーID）">

ドメインが除外対象でない場合、AppsFlyerはURL内の`pid=`パラメータを確認します。

* 見つかった場合は、その値をメディアソースとして使用します。
* <span id="social-media-partners"></span>なお、以下のSNSパートナーについては、URLパラメータの値ではなく、専用の表示名が使用されます。

| URLパラメーター（PID） | メディアソース表示名 |
| --- | --- |
| `pid=iossearchads_int` | Apple Search Ads |
| `pid=facebook_int` | Facebook Ads |
| `pid=metaweb_int` | Facebook Ads |
| `pid=twitter_int` | Twitter |
| `pid=twitterweb_int` | Twitter |
| `pid=googleads_int` | googleadwords\_int |
| `pid=tiktokweb_int` | tiktokglobal\_int |
| `pid=snapweb_int` | snapchat\_int |

</Accordion>

<Accordion title="3.UTMパラメーター">

URLにPIDが存在しない場合、AppsFlyerは `utm_source` および `utm_medium` を評価してメディアソースを判定します。判定結果は、この2つのパラメータの組み合わせによって決まります。

<div id="how-utm-logic-works" />

#### **UTM判定の仕組み**

* 通常、AppsFlyerは`utm_source`の値をそのままメディアソースとして使用します。
* `utm_medium` が `email` 、 `mail` 、または `e-mail` の場合、メディアソースは自動的に `e-mail` となります。
* `utm_medium` が存在し、email以外の値である場合は、以下のマッピングルールと照合されます。
* `utm_medium` が存在しない場合、またはマッピングルールに一致しない場合は、`utm_source` の値がメディアソースとして使用されます。

<div id="utm-mapping-rules" />

#### **UTMマッピングルール**

| utm\_source | utm\_medium | メディアソース |
| --- | --- | --- |
| Google | cpc / ppc / paidsearch / paid\_search / paid-search / search / paid | googleadwords\_int |
| Google | cpm / display / banner / video / listing | dv360\_int |
| dfa / dbm / dcm / doubleclick | cpm | dv360\_int |
| Facebook/FB/Meta | cpc / ppc / cpm / cpa / paidsocial / paid-social / paid\_social / paid | Facebook Ads |
| Bing/microsoft/ms | cpc / ppc / paidsearch / paid\_search / paid-search / search / paid | bingsearch\_int |
| Yahoo / gemini | cpm / display / listing | yahoogemini\_int |
| Twitter | cpc / ppc / paid / paidsocial / paid-social / paid\_social | Twitter |
| Snapchat / snap | swipe / cpc / ppc / paid / paidsocial / paid-social / paid\_social | snapchat\_int |
| pinterest | cpc / ppc / paid / paidsocial / paid-social / paid\_social | pinterest\_int |
| tiktok | cpc / ppc / paid / paidsocial / paid-social / paid\_social | tiktokglobal\_int |

</Accordion>

<Accordion title="4.クリックID">

URLにPIDもUTMパラメータも含まれていない場合、AppsFlyerは**クリックID**を使用してメディアソースの特定を試みます。クリックIDは、特定の広告ネットワークがURLへ自動的に付与する一意の識別子です。

AppsFlyerは、以下のクリックIDマッピングを使用してサイト訪問のアトリビューションを行います。

| Click ID パラメータ | 判定されるメディアソース |
| --- | --- |
| `gclid`, `wbraid`, または `gbraid` | googleadwords\_int |
| `msclkid` | bingsearch\_int |
| `twclid` | Twitter |
| `vmcid` | yahoogemini\_int |
| `sccid` | snapchat\_int |
| `li_fat_id` | linkedin\_int |
| `ttclid` | tiktokglobal\_int |
| `tbclid` | taboola\_int |
| `ob_click_id` | outbrain\_int |
| `dicbo` | outbrain\_int |
| `yclid` | yandex\_int |
| `rdt_cid` | reddit\_int |
| `epik` | pinterest\_int |
| `oppref` | openai\_int |

> 📘 **Note**
>
> * AppsFlyerは、トラフィックソース判定に fbclid を使用しません。これは、Metaが有料クリックとオーガニッククリックの両方にfbclidを付与するためです。Metaからのトラフィックをアトリビューションするには、pid=facebook\_int をURLに含めるか、utm\_sourceに該当するMetaのソース値を設定してください。
> * また、dclid パラメータもメディアソース判定には使用されません。dclid はCampaign Manager 360（CM360）の識別子であり、CM360を利用している場合は、fbclid （Facebook）や ttclid（TikTok）など、他のクリックIDと併せて付与されることがありまdclid のみを使用すると、誤ったメディアソースとして判定される可能性があります。

</Accordion>

<Accordion title="5.HTTPリファラ">

URLにPID、UTMパラメータ、クリックIDのいずれも含まれていない場合、AppsFlyerは`http_referrer`を使用してトラフィックソースを特定します。この処理では、リファラからドメインホストを抽出し、内部マッピングに基づいてメディアソースを判定します。

<div id="the-parsing-mechanism" />

#### **判定の仕組み**

AppsFlyerは、リファラの文字列に対して以下の処理を行います：

1. URLから**ホスト名**のみを抽出する
2. **ドメインサフィックス**（`.com`、`.org`、`.co.uk`など）を削除する
3. **ドメインプレフィックス**（`www.`、`m.`、`l.`、`lm.`など）を削除する

*例：*`www.mywebsite.com?param=example`*のリファラの場合、メディアソースは`mywebsite`*に変換されます。

<div id="referrer-mapping-rules" />

#### **リファラマッピングルール**

| ドメインホストに以下が含まれる場合： | 判定されるメディアソース |
| --- | --- |
| `mail.` または `outlook.` | Email |
| `t.co` | twitter |
| `googleads.g.doubleclick.net` | googleadwords\_int |
| `tpc.googlesyndication.com` | dv360\_int |

<div id="ai-answer-engine-referrer-mapping" />

<div id="search-engine-mapping" />

#### **検索エンジンのマッピング**

| ドメインホストに以下が含まれる場合： | 判定されるメディアソース |
| --- | --- |
| `google.` | Google Search |
| `search.yahoo` | Yahoo Search |
| `bing.com` | Bing Search |

<div id="android-app-referrers" />

#### **Androidアプリからのリファラ**

訪問元がAndroidアプリの場合は、リファラホストは以下のように判定されます。

| アプリのリファラ文字列 | 判定されるメディアソース |
| --- | --- |
| `com.google.android.googlequicksearchbox` | Google Search |
| `com.google.android.gm` | Email |
| `com.linkedin.android` | LinkedIn |
| `com.twitter.android` | twitter |
| `org.telegram.messenger` | telegram |

</Accordion>

<div id="step-3-campaign-resolution" />

## ステップ３：キャンペーン情報の判定

ステップ2でメディアソースが確定すると、AppsFlyerはキャンペーンの詳細情報を特定します。

AppsFlyerは、以下のURLパラメータから優先順位に従ってキャンペーン情報を取得します。

| URLパラメータ | 対応する項目 | 優先順位 |
| --- | --- | --- |
| `c`、 `af_campaign`、 `utm_campaign` | キャンペーン名 | <ol><li>`c`</li><li>`af_campaign`</li><li>`utm_campaign`</li></ol> |
| `af_c_id`、 `af_campaign_id` | キャンペーンID | <ol><li>`af_c_id`</li><li>`af_campaign_id`</li></ol> |
| `af_adset` | 広告セット名 | — |
| `af_adset_id` | 広告セットID | — |
| `af_ad` | 広告名 | — |
| `af_ad_id` | 広告ID | — |
| `af_keywords` | キーワード | — |

<div id="step-4-channel-classification" />

## ステップ4：チャネル分類

AppsFlyerは、メディアソースを特定するだけでなく、各訪問をチャネルへ分類します。この分類により、ローデータレポートやダッシュボードでトラフィックの種類を大まかに把握できます。

<div id="overriding-the-channel-with-af_channel" />

### af\_channelによるチャネルの上書き

任意のチャネル値を指定するには、ランディングページURLに `af_channel` パラメータを追加します。たとえば、`af_channel=ig` と指定すると、チャネルが `ig` に設定されます。これにより、広告の掲載位置など、標準のカテゴリではカバーできない粒度でトラフィックを分類・分析できます。

`af_channel` が適用されるのは、その訪問についてメディアソースも特定されている場合のみです。訪問がオーガニック（メディアソースが特定されていない）の場合は、`af_channel` の有無にかかわらず、チャネルは常に `Direct` として判定されます。

<div id="default-channel-classification" />

### デフォルトのチャネル分類

`af_channel`l が指定されていない場合、または訪問が上記の条件を満たしていない場合、AppsFlyerは特定されたメディアソースに基づいて、以下のとおり自動的にチャネルを分類します。

* **DIRECT：** ユーザーがURLを直接入力するか、ブックマークからアクセスした場合です。アトリビューション元は特定されません。
* **ORGANIC\_SEARCH：** Google、Yahoo、Bingなどの検索エンジンからの自然検索による流入です。
* **SOCIAL MEDIA：** ソーシャルメディアプラットフォームからの流入です。
* **メールアドレス：** メールキャンペーンまたはメール配信サービスからの流入です。
* Ad有料広告による流入です。
* **REFERRAL：** リファラによって識別された他のWebサイトからの流入です。
* **OTHER：** 上記のいずれにも該当しない流入です。

**注意：** すべての訪問はいずれか1つのチャネルに分類されます。チャネル分類は、`af_channel`によって上書きされない限り、特定されたメディアソースおよびアトリビューション方法に基づいて、自動かつ一意に決定されます。

<div data-zendesk-anchors="what-is-traffic-source-resolution=%E3%83%88%E3%83%A9%E3%83%95%E3%82%A3%E3%83%83%E3%82%AF%E3%82%BD%E3%83%BC%E3%82%B9%E5%88%A4%E5%AE%9A%E3%81%A8%E3%81%AF h_01KGMEER6DX8W3ECBEBYP4DQV1=%E3%83%88%E3%83%A9%E3%83%95%E3%82%A3%E3%83%83%E3%82%AF%E3%82%BD%E3%83%BC%E3%82%B9%E5%88%A4%E5%AE%9A%E3%81%A8%E3%81%AF the-traffic-source-resolution-flow=%E3%83%88%E3%83%A9%E3%83%95%E3%82%A3%E3%83%83%E3%82%AF%E3%82%BD%E3%83%BC%E3%82%B9%E5%88%A4%E5%AE%9A%E3%81%AE%E6%B5%81%E3%82%8C h_01KGMEER6DA4HMSZ3TVEAG84WZ=%E3%83%88%E3%83%A9%E3%83%95%E3%82%A3%E3%83%83%E3%82%AF%E3%82%BD%E3%83%BC%E3%82%B9%E5%88%A4%E5%AE%9A%E3%81%AE%E6%B5%81%E3%82%8C step-1-visit-recording=%E3%82%B9%E3%83%86%E3%83%83%E3%83%97%EF%BC%91%E3%82%B5%E3%82%A4%E3%83%88%E8%A8%AA%E5%95%8F%E3%81%AE%E8%A8%88%E6%B8%AC h_01KGMEER6DV02F44C5ZPSBEQEX=%E3%82%B9%E3%83%86%E3%83%83%E3%83%97%EF%BC%91%E3%82%B5%E3%82%A4%E3%83%88%E8%A8%AA%E5%95%8F%E3%81%AE%E8%A8%88%E6%B8%AC stage-1-referrer-classification=%E3%82%B9%E3%83%86%E3%83%BC%E3%82%B8%EF%BC%91%E3%83%AA%E3%83%95%E3%82%A1%E3%83%A9%E3%83%BC%E3%81%AE%E5%88%86%E9%A1%9E h_01KSSEM5P8RX29CD6C6ZD2DVAT=%E3%82%B9%E3%83%86%E3%83%BC%E3%82%B8%EF%BC%91%E3%83%AA%E3%83%95%E3%82%A1%E3%83%A9%E3%83%BC%E3%81%AE%E5%88%86%E9%A1%9E stage-2-session-evaluation-and-visit-recording=%E3%82%B9%E3%83%86%E3%83%BC%E3%82%B8%EF%BC%92%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E8%A9%95%E4%BE%A1%E3%81%A8%E8%A8%AA%E5%95%8F%E8%A8%98%E9%8C%B2 h_01KSSEM5P8KBYDBCB7PAPGPX5M=%E3%82%B9%E3%83%86%E3%83%BC%E3%82%B8%EF%BC%92%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E8%A9%95%E4%BE%A1%E3%81%A8%E8%A8%AA%E5%95%8F%E8%A8%98%E9%8C%B2 step-2-media-source-resolution=%E3%82%B9%E3%83%86%E3%83%83%E3%83%97%EF%BC%92%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E5%88%A4%E5%AE%9A h_01KGMEER6D082QTZGZYEXT6726=%E3%82%B9%E3%83%86%E3%83%83%E3%83%97%EF%BC%92%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E5%88%A4%E5%AE%9A how-utm-logic-works=utm%E5%88%A4%E5%AE%9A%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF h_01KGMF0E1XBSJCVDWGC4R8XMPX=utm%E5%88%A4%E5%AE%9A%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF utm-mapping-rules=utm%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%83%AB%E3%83%BC%E3%83%AB h_01KGMF0JSBZ3WYM65R55BCDAMN=utm%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%83%AB%E3%83%BC%E3%83%AB the-parsing-mechanism=%E5%88%A4%E5%AE%9A%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF h_01KGMEZA9ETGK6Z89GM111E64Z=%E5%88%A4%E5%AE%9A%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF referrer-mapping-rules=%E3%83%AA%E3%83%95%E3%82%A1%E3%83%A9%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%83%AB%E3%83%BC%E3%83%AB h_01KGMEZESC451HVJT139BSXEA5=%E3%83%AA%E3%83%95%E3%82%A1%E3%83%A9%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%83%AB%E3%83%BC%E3%83%AB search-engine-mapping=%E6%A4%9C%E7%B4%A2%E3%82%A8%E3%83%B3%E3%82%B8%E3%83%B3%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 h_01KGMEZKCTASMNXZG13VTVECVH=%E6%A4%9C%E7%B4%A2%E3%82%A8%E3%83%B3%E3%82%B8%E3%83%B3%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 android-app-referrers=android%E3%82%A2%E3%83%97%E3%83%AA%E3%81%8B%E3%82%89%E3%81%AE%E3%83%AA%E3%83%95%E3%82%A1%E3%83%A9 h_01KGMEZQYCDS23MVW3MQH9Q5JQ=android%E3%82%A2%E3%83%97%E3%83%AA%E3%81%8B%E3%82%89%E3%81%AE%E3%83%AA%E3%83%95%E3%82%A1%E3%83%A9 step-3-campaign-resolution=%E3%82%B9%E3%83%86%E3%83%83%E3%83%97%EF%BC%93%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E6%83%85%E5%A0%B1%E3%81%AE%E5%88%A4%E5%AE%9A h_01KGMEER6ES1AYT24MC4HZCX9X=%E3%82%B9%E3%83%86%E3%83%83%E3%83%97%EF%BC%93%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E6%83%85%E5%A0%B1%E3%81%AE%E5%88%A4%E5%AE%9A step-4-channel-classification=%E3%82%B9%E3%83%86%E3%83%83%E3%83%974%E3%83%81%E3%83%A3%E3%83%8D%E3%83%AB%E5%88%86%E9%A1%9E h_01KGMEER6ETWGFFM3E17KHMDAF=%E3%82%B9%E3%83%86%E3%83%83%E3%83%974%E3%83%81%E3%83%A3%E3%83%8D%E3%83%AB%E5%88%86%E9%A1%9E h_01_overriding-the-channel-with-af-channel=af_channel%E3%81%AB%E3%82%88%E3%82%8B%E3%83%81%E3%83%A3%E3%83%8D%E3%83%AB%E3%81%AE%E4%B8%8A%E6%9B%B8%E3%81%8D overriding-the-channel-with-af_channel=af_channel%E3%81%AB%E3%82%88%E3%82%8B%E3%83%81%E3%83%A3%E3%83%8D%E3%83%AB%E3%81%AE%E4%B8%8A%E6%9B%B8%E3%81%8D h_01_default-channel-classification=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%81%E3%83%A3%E3%83%8D%E3%83%AB%E5%88%86%E9%A1%9E default-channel-classification=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%81%E3%83%A3%E3%83%8D%E3%83%AB%E5%88%86%E9%A1%9E" />
