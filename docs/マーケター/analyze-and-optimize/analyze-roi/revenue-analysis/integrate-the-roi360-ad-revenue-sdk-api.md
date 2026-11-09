---
title: ROI360の広告収益SDK APIの実装
metadata:
  keywords:
    - ROI
    - ad revenue
    - Advertisers
    - Advertiser
    - Developer
    - Developers
    - ad revenue SDK
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-01-12T09:09:07Z'
  edited_at: '2026-10-28T08:49:49Z'
  id: 4416353506833
  locale: ja
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/ja/articles/4416353506833
---
> **概要：** AppsFlyerの広告収益SDK APIは、アドネットワークと連携し、広告表示1回ごとの広告収益を報告します。

<Image align="center" alt="mceclip1__1_.png" src="https://files.readme.io/202ded6950dfbf370bb48738876224936d28ecfae0c0aba09d1c49892b774cb5-31202279100177.png" />

<div id="impression-level-ad-revenue-reporting-by-sdk-api" />

## SDK APIによる広告表示単位の広告収益の報告

**広告収益の報告方法**

広告収益は、集計済みデータ（API経由）または広告表示単位のデータ（SDK経由）としてAppsFlyerに報告されます。 SDK経由の広告表示単位データには、次の特徴があります。

* データの反映が早く、AppsFlyerでより早い段階から収益を確認できます。
* SKANに対応しています。
* AppsFlyer SDK V6.15以降が対象です。それより前のSDKでは、APIの代わりにSDK Connectorを使用します。この記事では、必要に応じて開発者向けの実装手順へのリンクを案内しています。

**注意：**

* 広告収益のインプレッションはAppsFlyerで収集・処理されますが、アプリ内イベントの契約枠には計上されません。
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/gs-ad-revenue">広告収益SDK APIに対応するSDKプラグインの全一覧</Anchor>を参照してください。

<div id="reporting-ad-revenue-using-the-sdk-api" />

### SDK APIを使った広告収益の報告

**SDKの仕組み**

広告収益SDK APIが、広告表示ごとの収益データをAppsFlyer SDKに送信します。 AppsFlyerがこれらのインプレッションイベントを収集・処理し、広告収益イベント`af_ad_revenue`を生成します。収益は、ユーザー獲得元に紐づけられます。

**データの表示**

広告収益の識別には、`af_ad_revenue`イベントを使用します。このイベントは、ダッシュボードや各種データ配信ツールなど、AppsFlyer全体で使用されます。

**対応するアドネットワーク**

広告収益SDK APIによるデータ送信に対応するメディエーションプラットフォームと広告収益化ネットワークは、次のとおりです。

* <Anchor target="_blank" href="/marketers/ja/docs/ironsource-campaign-configuration#ad-revenue-tab">Unity LevelPlayメディエーション</Anchor>（旧ironSource）
* <Anchor target="_blank" href="/marketers/ja/docs/applovin-max-ad-revenue-configuration">Applovin Max</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/google-admob-ad-revenue-attribution-configuration">Google AdMob</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/fyber-campaign-configuration">Fyber</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/appodeal-campaign-configuration">Appodeal</Anchor>
* Admost
* Topon
* Topon Pte.
* Tradplus
* <Anchor target="_blank" href="/marketers/ja/docs/yandex-direct-campaign-configuration">Yandex</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/chartboost-campaign-configuration">Chartboost</Anchor>
* customMediation（使用するメディエーションが、対応パートナーの一覧にない場合）
* directMonetizationNetwork（メディエーションを使わず、アプリが広告収益化ネットワークと直接連携する場合）

**データの更新・反映**

広告が表示された時点で、**SDK APIがAppsFlyerに収益データを送信します。 ROI360の有料プランをご利用のお客様は、次のタイミングでデータを利用できます。**

* **Data Lockerの広告表示単位のトピック：午前1時から、1時間ごと。**
* **AppsFlyerのアクティビティ・コホートレポート：UTC午前5時から、4時間ごと。**

<div id="implementing-appsflyer-ad-revenue-sdk-api" />

## AppsFlyer広告収益SDK APIの実装

**AppsFlyerの広告収益SDK APIを実装するには**：

1. 接続するパートナーについて、<Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">AppsFlyerでSDK経由の広告収益を有効にします</Anchor>。**注意**：アプリごとに個別の設定が必要です。
2. 開発者に、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/gs-ad-revenue">こちらの手順</Anchor>に従ってAppsFlyerの広告収益SDK APIを実装するよう依頼します。
3. SKAdNetworkダッシュボードで広告収益を記録するには、<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">SKANの広告収益の設定手順</Anchor>に従ってください。
4. 連携をテストします。実装後、次のいずれかの方法で広告収益イベントを受信していることを確認してください。
   * <Anchor target="_blank" href="/marketers/ja/docs/testing-the-sdk-integration-for-marketers#view-live-events">ライブイベントビューアー</Anchor>で、広告収益イベントがリアルタイムで表示されることを確認します。ライブイベントビューアーに表示されるのは、登録済みのテスト端末から送信されたイベントのみです。
   * <strong>［収益設定］</strong>ページで対象の広告収益連携を編集し、<strong>［接続をテスト］</strong>をクリックして、有効な広告収益イベントが最近処理されていることを確認します。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">広告収益パートナーとの連携</Anchor>を参照してください。

<div id="traits-and-limitations" />

## 仕様と制限事項

| 項目 | 補足 |
| --- | --- |
| Admob | <ul><li>AdmobのiLTVを有効にするには、<Anchor target="_blank" href="https://support.google.com/admob/answer/11322405#getstarted">こちらのリンク</Anchor>を参照してください。</li><li>AndroidとUnityでは、Admob iLTV SDKが広告表示ごとの収益を<Anchor target="_blank" href="https://developers.google.com/android/reference/com/google/android/gms/ads/AdValue#public-long-getvaluemicros">マイクロ単位</Anchor>で報告します。 AppsFlyerに正しい米ドルの広告収益を表示するには、iLTVイベントハンドラーから取得した金額を100万で割ってから、AppsFlyerに送信してください。</li></ul> |
| 広告収益の値 | SDK APIでは、収益が$10（他の通貨では相当額）を超えるインプレッションイベントは処理されません。 |

<div data-zendesk-anchors="impressionlevel-ad-revenue-reporting-by-sdk-API=sdk-api%E3%81%AB%E3%82%88%E3%82%8B%E5%BA%83%E5%91%8A%E8%A1%A8%E7%A4%BA%E5%8D%98%E4%BD%8D%E3%81%AE%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%81%AE%E5%A0%B1%E5%91%8A 01H8HHAQHK6CDK8X2Y6N4GANNC=sdk-api%E3%81%AB%E3%82%88%E3%82%8B%E5%BA%83%E5%91%8A%E8%A1%A8%E7%A4%BA%E5%8D%98%E4%BD%8D%E3%81%AE%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%81%AE%E5%A0%B1%E5%91%8A reporting-ad-revenue-using-the-sdk-API=sdk-api%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%81%AE%E5%A0%B1%E5%91%8A 01H8HHAQHKQ3H3R21Z1JYNJ2EE=sdk-api%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%81%AE%E5%A0%B1%E5%91%8A implementing-generic-appsflyer-ad-revenue-sdk-API=appsflyer%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8Asdk-api%E3%81%AE%E5%AE%9F%E8%A3%85 01H8HHAQHKCXKPJJE8EDT1J9CR=appsflyer%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8Asdk-api%E3%81%AE%E5%AE%9F%E8%A3%85 traits-and-limitations=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 01H8HHAQHMCSVQ2ZAT3G7XJKAN=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />
