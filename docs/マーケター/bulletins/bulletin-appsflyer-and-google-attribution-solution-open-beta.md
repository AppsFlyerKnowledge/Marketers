---
title: お知らせ：AppsFlyerとGoogleのICM計測ソリューション［オープンβ］
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2025-08-06T13:24:32Z'
  edited_at: '2026-10-14T09:21:57Z'
  id: 37857301293457
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/37857301293457
---
<Embed title="YouTube video player" typeOfEmbed="youtube" url="https://www.youtube.com/embed/VilMr6T0Yd0?si=p7FezQwuKkBtwkaB" providerUrl="https://www.youtube.com" />

| セクション | 詳細 |
| --- | --- |
| **更新情報** | GoogleのIntegrated Conversions Measurement（ICM）ソリューションは、インストールとリアトリビューション（再インストール）を計測するためにGoogle Adsを使用するすべてのクライアントが利用できるようになります。 |
| **一般提供（オープンβ）予定日** | <ul><li>**iOS** - オープンβ（2025年11月12日時点） - すべてのアプリで利用可能</li><li>**Android** - オープンβ（2025年12月5日時点） - すべてのアプリで利用可能</li></ul> |
| **知っておくべきこと** | <ul><li>ICMを使用すると、AppsFlyerはプライバシー保護の方法を使用して、デバイスIDを必要とせずにインストールをGoogle広告に紐づけることができます。</li><li>Googleは、AppsFlyerに非決定論的インストールの成果主張を送信します。<br />AppsFlyerのデータによって検証された場合、これらの主張はアトリビューションに使用されます。詳細については、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers#高度なデータ共有を使用したgoogle-adsの計測フロー">アドバンスデータ共有を使用したGoogle Ads計測フロー</Anchor>を参照してください。</li></ul> |
| **必要な対応** | <ul><li>**SDKの要件：**<ul><li>**iOS：** AppsFlyer <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-release-notes">iOS SDK バージョン6.17.7</Anchor>以降に*加え*、Google <Anchor target="_blank" href="https://github.com/firebase/firebase-ios-sdk/releases">Firebase SDK バージョン11.14.0</Anchor>以降、またはスタンドアローンの<Anchor target="_blank" href="https://support.google.com/google-ads/answer/16384720">Google ODM SDK</Anchor>の実装が必要です。</li><li>**Android：** SDKの更新は必要ありません。</li></ul></li><li>**アドバンスデータ共有のトグル：** iOSとAndroid両方の `googleadwords_int` 連携での新しい設定：<ul><li>**有効**の場合：AppsFlyerは、デバイスIDがなくても、すべてのインストールイベントをGoogleに送信します。</li><li>**無効**の場合：デバイスIDまたはGCLIDが利用可能なインストールイベントのみが共有され、ICMの有効性が制限されます。</li></ul></li><li>**重要（iOSのみ）：** ICMは、欧州経済領域（EEA）、英国、スイスのユーザーから発生するトラフィックには対応していません。</li></ul> |