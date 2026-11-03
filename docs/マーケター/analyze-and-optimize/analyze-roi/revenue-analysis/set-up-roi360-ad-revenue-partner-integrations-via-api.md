---
title: APIによるROI360広告収益パートナー連携の設定
metadata:
  keywords:
    - ad revenue
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-10-16T14:53:47Z'
  edited_at: '2026-10-28T08:50:02Z'
  id: 9901416616465
  locale: ja
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/ja/articles/9901416616465
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** APIを使い、AppsFlyerアカウント全体または個別のアプリの広告収益パートナー連携を設定します。

## 広告収益パートナー連携API

広告収益パートナー連携APIでは、次のことができます。

* アカウント内の各アプリについて、広告収益パートナー連携を設定する。
* アカウント全体で現在設定されている広告収益パートナー連携を一覧で取得する。

<div id="set-api" />

<Accordion title="連携設定API">

**APIで広告収益パートナー連携を設定するには**：

1. AppsFlyerのダッシュボードで<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens">API V2トークンを取得します</Anchor>。 APIの認証に必要です。**注意**：アカウントの管理者が行う必要があります。
2. 以下の表に従い、APIリクエストに含めるパラメータを準備します。
3. パラメータの値を開発者に渡し、DevHubの<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_integrations">連携設定APIの手順</Anchor>に従って実装するよう依頼します。  
   連携は、UTCの翌日00:00に有効になります。

#### リクエストパラメータ

| パラメータ | 説明 |
| --- | --- |
| integrations | <ul><li>最上位のオブジェクト。app\_id、network、およびproducts（以下を参照）が必須です。</li><li>その他に、credentials、event\_name、source\_eventを含めることもできます。</li></ul> |
| app\_id | 連携するアプリのアプリID。 |
| network | <ul><li>連携するパートナー。</li><li>対応するアドネットワークは、<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">広告収益パートナーAPIのパラメータ一覧</Anchor>のnetwork列を参照してください。</li></ul> |
| credentials | <ul><li>アドネットワークとの連携に必要な、1つ以上の認証情報。</li><li>認証情報の一覧は、<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">広告収益パートナーAPIのパラメータ一覧</Anchor>のcred列を参照してください。</li></ul> |
| event\_name | <ul><li>デフォルト値：af\_ad\_revenue</li><li>カスタムイベント名も指定できます［ベータ版］。</li><li>enabledがfalseの場合、event\_nameは不要です。</li></ul> |
| products | <ul><li>連携で有効になっている製品の一覧。製品ごとにname、enabledと、該当する場合はsource\_eventを含みます（以下を参照）。</li><li>各networkで使用できる製品は、<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">広告収益パートナーAPIのパラメータ一覧</Anchor>のbulk API products列を参照してください。</li></ul> |
| name | <ul><li>連携方式の名前。</li><li>連携方式の名前の一覧は、<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">広告収益パートナーAPIのパラメータ一覧</Anchor>のbulk API products列を参照してください。</li></ul> |
| enabled | <ul><li>設定される値：<ul><li>true</li><li>false</li></ul></li><li>アプリ単位の連携方式では、source-eventが必須です。</li><li>値がfalseの場合、source\_eventもevent\_nameも不要です。</li></ul> |
| source\_event | <ul><li>S2S APIによる集計データ方式のパートナー連携のみが対象です。</li><li>アプリ単位の連携方式でenabledがtrueの場合、source\_eventが必須です。</li></ul> |

</Accordion>

<div id="get-api" />

<Accordion title="連携一覧取得API">

**APIで広告収益パートナー連携の一覧を取得するには**：

1. AppsFlyerのダッシュボードで<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens">API V2トークンを取得します</Anchor>。 APIの認証に必要です。
2. 開発者に、DevHubの<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_integrations">連携一覧取得APIの手順</Anchor>に従うよう依頼します。

</Accordion>

### 仕様と制限事項

| **項目** | **補足** |
| --- | --- |
| 呼び出しの上限 | 1回の呼び出しで、最大1,000件の連携を処理できます。 |
| OAuth | GoogleやFacebookなど、OAuthで連携するパートナーには対応していません。 |

<div data-zendesk-anchors="ad-revenue-partner-integration-api=%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E9%80%A3%E6%90%BAapi h_01HYD2M7E1PH0ARZRF0P17K80J=%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E9%80%A3%E6%90%BAapi h_01HYD2M7E1DX9FAJ0MGN500NZV=set-api request-parameters=%E3%83%AA%E3%82%AF%E3%82%A8%E3%82%B9%E3%83%88%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_01HYD2M7E1FYY96HNM6DSHXPQ5=%E3%83%AA%E3%82%AF%E3%82%A8%E3%82%B9%E3%83%88%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_01HYD2M7E19XCCFF1NT40VBWH7=get-api specs-and-limitations=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HYD2M7E1X2PEQ616PWMTWCH7=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />
