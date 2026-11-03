---
title: SDKを使用したコンバージョンデータの取得｜概要
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:06:52Z'
  edited_at: '2026-10-29T07:38:29Z'
  id: 4410481069969
  locale: ja
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/ja/articles/4410481069969
---
> **概要：** コンバージョンデータを活用すると、さまざまなコンバージョンの発生パターンの把握や、ユーザーに合わせた体験の提供などが可能です。

コンバージョンデータを活用すると、次のことが可能です。

* ユーザーをアプリ内の特定の画面に誘導する
* ユーザーに合わせたコンテンツを表示する

> 🚧 **重要**
>
> **SDKで取得するコンバージョンデータの制限事項**
>
> AppsFlyer SDKのコールバック`onConversionDataSuccess`は、アトリビューション処理が完了する前に呼び出される場合があります。そのため、SDKが返すデータは、AppsFlyerのレポートやAPIのデータと一致しない場合があります。
>
> **推奨事項：**
> アトリビューションデータの収集や検証には、Get Conversion Data（GCD）メソッドを使用しないでください。
> 正確かつ完全なアトリビューション結果を取得するには、AppsFlyerのダッシュボード、レポート、APIを使用してください。

## コンバージョンデータの取得

AppsFlyer SDKは、次のメソッドを通じてコンバージョンデータを返します。

* * `onConversionDataSuccess`：ユーザー獲得（UA）とリアトリビューションのコンバージョン
    * Android: &lt;0>onConversionDataSuccess0>
    * iOS: &lt;0>onConversionDataSuccess0>
    * Unity: &lt;0>loadConversionData0>
  * `onAppOpenAttribution`：リエンゲージメントのコンバージョン

<div data-zendesk-anchors="h_01K9KSQQDVDEACFRXS0M4JNW9M=%E9%87%8D%E8%A6%81 get-conversion-data=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97 h_01HTZ6M409RPZAQM66R0H5HA16=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97" />
