---
title: SDKの追加機能実装ガイド
metadata:
  keywords:
    - iOS
    - Android
    - Integration
    - Advertisers
    - firetv
    - Advertiser
    - appuid
    - anonymous
    - kakao
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2021-10-10T11:54:14Z'
  edited_at: '2026-10-28T09:09:27Z'
  id: 4408735106193
  locale: ja
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/ja/articles/4408735106193
---
> **At a glance:** 利用可能なSDKの追加機能を確認し、開発者と協力して、アンインストール計測、ユーザー招待のアトリビューション、プッシュ通知、プライバシー設定などのAPIを実装します。

## 追加のアトリビューション計測方法

テレビ広告、アンインストール、プリインストールアプリの計測を予定している場合は、以下の追加のアトリビューション計測方法をご検討ください。

**すべてのプラットフォーム**

<Accordion title="CTVアトリビューション">

特定の地域・時間帯に配信された<Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts">CTV広告からモバイルユーザーへのアトリビューション</Anchor>を計測します。

</Accordion>

<Accordion title="アンインストールの計測">

流入元ごとのユーザーのアンインストール率を計測します。アンインストール計測は、この重要なKPIに基づくキャンペーンの分析と最適化に役立ちます。

<Anchor target="_blank" href="/marketers/ja/docs/measure-uninstalls">アンインストール計測の設定方法</Anchor>をご確認ください。

</Accordion>

**Androidのみ**

<Accordion title="プリインストールアプリ">

<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-factory-preinstall-using-manifest-android">プリインストールキャンペーン</Anchor>では、アプリの所有者が端末メーカー（OEM）と契約し、端末にアプリをあらかじめインストールします。

AppsFlyerを使用すると、プリインストールアプリのインストールを簡単にアトリビューション計測できます。ユーザーが初めてアプリを起動すると、AppsFlyerはプリロードパートナーをメディアソースとしてインストールをアトリビューションします。

</Accordion>

## セッション

一定期間内のユーザーセッション数を集計し、アプリの利用状況を計測します。

**すべてのプラットフォーム**

<Accordion title="セッション間隔のカスタム設定">

デフォルトでは、2回のアプリ起動を別々のセッションとしてカウントするには、起動間隔が5秒以上必要です。<Anchor target="_blank" href="/marketers/ja/docs/measure-sessions#session-reporting-by-the-app-sdk">セッションのカウント方法</Anchor>について詳しくはこちらをご確認ください。

アプリ起動間隔のカスタム設定値を**大きくしすぎると、ディープリンクなど、セッションデータに依存するAPIの動作に影響する可能性があります**。

</Accordion>

**Androidのみ**

<Accordion title="ユーティリティアプリのバックグラウンドセッション">

<Anchor target="_blank" href="/marketers/ja/docs/measure-sessions#session-reporting-by-the-app-sdk">ユーザーセッションを手動でレポート</Anchor>できます。バックグラウンドで動作するユーティリティアプリなどで役立ちます。

</Accordion>

## オウンドメディア

OneLinkを使用すると、ウェブサイト、ソーシャルメディア、ユーザー招待などのオウンドメディア経由の流入をアトリビューション計測できます。

**すべてのプラットフォーム**

<Accordion title="ラップされたディープリンクURLの解決">

<Anchor target="_blank" href="/marketers/ja/docs/email-service-provider-esp-integration-guide">メール配信サービス（ESP）</Anchor>などの一部の外部サービスでは、メール内のリンクが独自のクリック計測ドメインでラップされます。独自のクリック記録用ドメインを設定できるサービスもあります。 OneLinkがこうしたドメインでラップされると、一部の機能が制限される可能性があります。

この問題を回避するには、開発者が以下のAPIを使用してアプリを設定する必要があります。

<Tabs>
<Tab title="Androidネイティブ">

Android SDKリファレンスの [`setResolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setresolvedeeplinkurls) を参照してください。

</Tab>

<Tab title="iOSネイティブ">

iOS SDKリファレンスの [`resolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#resolvedeeplinkurls) を参照してください。

</Tab>

<Tab title="Unity">

Unity SDKリファレンスの [`setResolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/api#setresolvedeeplinkurls) を参照してください。

</Tab>
</Tabs>

</Accordion>

<Accordion title="プッシュ通知の計測">

AppsFlyerでは、Google Cloud MessagingやAppleのプッシュ通知サービスを含む、あらゆるプロバイダーのプッシュ通知キャンペーンを計測できます。

<Anchor target="_blank" href="/marketers/ja/docs/measuring-push-notification-re-engagement-campaigns">プッシュ通知の計測について詳しくはこちら</Anchor>。

</Accordion>

<Accordion title="ユーザー招待のアトリビューション">

既存ユーザーが友人や連絡先の相手をアプリに招待できる仕組みは、アプリの成長を促す重要な要素となります。 AppsFlyerでは、アプリ内のユーザー招待をきっかけとするインストールをアトリビューションし、記録できます。

<Anchor target="_blank" href="/marketers/ja/docs/user-invite-attribution">ユーザー招待のアトリビューションについて詳しくはこちら</Anchor>。

</Accordion>

<Accordion title="クロスプロモーションのアトリビューション">

アプリ間のクロスプロモーションは、アプリのインストール数を増やすうえで重要な施策となります。 AppsFlyerでは、ユーザーが現在利用しているアプリから自社の別のアプリへ誘導するクロスプロモーション経由のインストールをアトリビューションし、記録できます。

<Anchor target="_blank" href="/marketers/ja/docs/cross-promotion-attribution-for-marketers">クロスプロモーションのアトリビューションについて詳しくはこちら</Anchor>。

</Accordion>

<Accordion title="自社Webサイト（ドメイン）から開始されたアプリセッションのアトリビューション">

OneLinkを使用せず、App LinksまたはUniversal Linksでディープリンクを実装しているアプリ事業者は、アプリに関連付けられたドメイン（<Anchor target="_blank" href="https://developer.android.com/studio/write/app-link-indexing#associatesite">Android</Anchor>／<Anchor target="_blank" href="https://developer.apple.com/documentation/xcode/supporting-associated-domains?preferredLanguage=occ">iOS</Anchor>）経由で開始されたセッションをアトリビューションするよう、SDKを設定できます。

例：

* ユーザーがGoogleで検索し、自社ドメインの **[www.example.com](https://www.example.com)** をクリックします。
* アプリがインストールされていない場合は、Webサイト（[www.example.com](https://www.example.com)）に遷移します。
* アプリが端末にインストールされている場合は、[www.example.com](https://www.example.com) に関連付けられたアプリがディープリンクで開きます。このセッションは、SDKで設定されたメディアソース（`pid` パラメータ）にアトリビューションされます。

開発者向けドキュメントは以下を参照してください。

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl">Android SDKリファレンス</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl">iOS SDKリファレンス</Anchor>

**ヒント：** <Anchor target="_blank" href="/marketers/ja/docs/convert-your-mobile-web-visitors-to-app-users#アトリビューションソリューション">OneLink Smart Script</Anchor> を利用すると、Webサイト訪問者をアプリユーザーへ転換しやすくなります。

</Accordion>

## ユーザーのプライバシー

GDPRやCCPAなどの規制と自社のビジネス要件を確認し、どのようなオプトイン・オプトアウトの方針を実装するか検討してください。

**すべてのプラットフォーム**

<Accordion title="オプトアウトポリシー">

GDPRやCCPAなどの規制に対応するため、AppsFlyer SDKによるデータ収集を停止または制限するよう開発者に依頼する必要がある場合があります。 SDKには、ユーザーのプライバシーを保護するための複数の方法が用意されています。各方法について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/apply-privacy-preserving-sdk-methods">SDKにおけるプライバシー保護の方法</Anchor>をご覧ください。

</Accordion>

<Accordion title="パートナーへのデータ共有の除外">

広告主によっては、特定のユーザーについてアドネットワークやパートナーへのユーザーレベルデータの共有を停止したい場合があります。主な理由は以下のとおりです。

* CCPAやGDPRなどのプライバシー規制
* ユーザーによるオプトアウトの仕組み
* 一部のパートナー（アドネットワークや第三者）との競合関係

パートナーへのデータ共有は、`setSharingFilterForPartners` メソッドで制御します。

<Tabs>
<Tab title="Androidネイティブ">

Android SDKリファレンスの <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor> を参照してください。

</Tab>

<Tab title="iOSネイティブ">

iOS SDKリファレンスの <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforpartners">`resolveDeepLinkURLs`</Anchor> を参照してください。

</Tab>

<Tab title="UnityReact Native">

Unity SDKリファレンスの <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor> を参照してください。

React Native SDKリファレンスの <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor> を参照してください。

</Tab>
</Tabs>

</Accordion>

<Accordion title="DMAへの準拠に必要な同意情報の送信">

EUの[デジタル市場法](https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en)（DMA）では、大手テクノロジー企業が第三者サービスから取得した個人データを広告に利用する際、欧州のエンドユーザーから同意を得ることが義務付けられています。

この法律に対応するため、GoogleはAppsFlyerの顧客に対し、EUのエンドユーザーに由来するイベントをGoogleへ送信する際に、所定の同意情報フィールドを含めるよう求めています。 AppsFlyer SDK（Android v6.13.0以降、iOS v6.13.1以降）は、この要件に対応するため、各イベントとともに必要な同意データを送信できます。

SDKでは、同意データを取得する方法として次の2つを用意しています。

* **同意管理プラットフォーム（CMP）経由：** アプリが[Transparency and Consent Framework（TCF）v2.2](https://iabeurope.eu/tcf-supporting-resources/)に準拠したCMPを利用している場合、SDKは同意情報を自動的に取得できます。

  または
* **専用SDK API経由：** 開発者は、この目的のために用意された専用APIを使用して、Googleが必要とする同意データをSDKに直接渡すことができます。

DMA対応のユーザー同意データの取得方法については、Dev Hubの以下のガイドをご覧ください。

<Tabs>
<Tab title="Androidネイティブ">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-send-consent-for-dma-compliance">DMA準拠のための同意情報の送信</Anchor>

</Tab>

<Tab title="iOSネイティブ">

[DMA準拠のための同意情報の送信](https://dev.appsflyer.com/hc/docs/ios-send-consent-for-dma-compliance)

</Tab>
</Tabs>

</Accordion>

**iOSのみ**

<Accordion title="厳格モードSDK">

IDFAの収集機能とAdSupportフレームワークへの依存を完全に取り除くには、厳格モードSDKを使用してください（<Anchor target="_blank" href="https://developer.apple.com/app-store/review/guidelines/#kids-category">子ども向けアプリ</Anchor>を開発する場合など）。

子ども向けアプリを提供する場合、開発者は通常のSDKではなく<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">厳格モードSDK</Anchor>をインストールする必要があります。**注意：** IDFVは引き続き利用できます。

</Accordion>

<Accordion title="広告関連フレームワークの無効化">

AdSupportおよびiAdフレームワークを無効にするため、SDKには以下のsetterが用意されています。

<Tabs>
<Tab title="iOSネイティブ">

* Apple Search Adsのアトリビューションをオプトアウトするには、[`disableCollectASA`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disablecollectasa) を使用します。
* Appleの `advertisingIdentifier` を収集しないようにするには、[`disableAdvertisingIdentifier`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableadvertisingidentifier) を使用します。

</Tab>

<Tab title="Unity">

* Apple Search Adsのアトリビューションをオプトアウトするには、[`setDisableCollectIAd`](https://dev.appsflyer.com/hc/docs/api#setdisablecollectiad) を使用します。
* Appleの `advertisingIdentifier` を収集しないようにするには、[`setDisableCollectAppleAdSupport`](https://dev.appsflyer.com/hc/docs/api#setdisablecollectappleadsupport) を使用します。

</Tab>
</Tabs>

</Accordion>

<div data-zendesk-anchors="additional-attribution-methods=%E8%BF%BD%E5%8A%A0%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC%E6%96%B9%E6%B3%95 01H8W01DRHQHJKNMJA24PR5S2T=%E8%BF%BD%E5%8A%A0%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC%E6%96%B9%E6%B3%95 sessions=%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3 01H8W01DRHD3EZBQT0ZKDMM1QB=%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3 owned-media=%E3%82%AA%E3%82%A6%E3%83%B3%E3%83%89%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2 01H8W01DRHV8H3QFJX5QKABK5E=%E3%82%AA%E3%82%A6%E3%83%B3%E3%83%89%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2 user-privacy=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC 01H8W01DRHJFB71DVJ64QWJME4=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC" />
