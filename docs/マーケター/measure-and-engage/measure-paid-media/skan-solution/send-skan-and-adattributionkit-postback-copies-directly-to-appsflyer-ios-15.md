---
title: SKANとAdAttributionKitのポストバックコピーをAppsFlyerに直接送信する方法（iOS15以降）
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-06-08T12:09:25Z'
  edited_at: '2026-10-28T09:17:21Z'
  id: 4402320969617
  locale: ja
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ja/articles/4402320969617
---
> **概要：** iOS15以降では、アドネットワークに加えてAppsFlyerにもポストバックのコピーを送信するようにアプリを設定できます。これにより、AppsFlyerはコンバージョン値（CV）が正しいか、ポストバックが改ざんされていないかを検証できます。 AppsFlyer Push APIを設定すると、指定した別のエンドポイントにもポストバックのコピーを転送できます。

<div id="note" />

> 📘 **注意**
>
> この記事の**SKAN**という表記は、**SKAdNetwork**と最新の<strong>AdAttributionKit（AAK）</strong>フレームワークの両方を指します。

<div id="why-send-postback-copies-to-appsflyer" />

## ポストバックのコピーをAppsFlyerに送信する理由

* すべてのポストバックを1か所に集約：ポストバックには、ユーザーの質を計測するCVなど、広告主にとって重要な情報が含まれています。ポストバック内のCVは暗号化されておらず、ポストバックの署名対象にも含まれていません。そのため、アドネットワークから報告されるCVは検証できず、改ざんされる可能性があります。 AppsFlyerは、Push APIを使用して、指定されたエンドポイントにポストバックのコピーを転送します。
  * Apple Adsでは必須：Apple AdsのSKANレポートを利用するには、ポストバックの転送が必要です（iOS15以降）。
* 再ダウンロードの指標を確認：一部のアドネットワークは、再ダウンロードのデータをAppsFlyerと共有していません。ポストバックのコピーによって、不足するデータを補えます。
* 広告掲載元アプリのデータを確認
* 接点の種類別にエンゲージメントを確認

<strong>注意！</strong>アドネットワークからのポストバックも、引き続きAppsFlyerで受信する必要があります。キャンペーン名など、アドネットワークが追加する情報が含まれているためです。

<div id="configure-your-app-to-send-postback-copies-to-appsflyer" />

## ポストバックのコピーをAppsFlyerに送信するための設定

Appleのドキュメントによると、SKANポストバックの送信先エンドポイントは1つ設定できます。

**AppsFlyerのエンドポイントを登録する手順：**

1. iOS開発者に依頼し、次のアプリバージョンで、SKANとAdAttributionKitのポストバック送信先エンドポイントとして<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#sending-skan-postback-copies-to-appsflyer">AppsFlyerを追加</Anchor>してください。
2. iOSアプリを申請します。
3. 新バージョンが公開されると、AppsFlyerにポストバックが送信されます。TestFlightからは送信されません。
4. 受信したポストバックは、<Anchor target="_blank" href="/marketers/ja/docs/skan-raw-data-reports">ポストバックコピーレポート</Anchor>で確認できます。

<div id="important" />

> 🚧 **重要！**
>
> SKANトラフィックがないアプリでは、設定完了後も次のメッセージが表示されます。「このアプリは、iOSポストバックのコピー（iOS15以降）をAppsFlyerに送信するように設定されていません。 SKAN計測の完全性を確保するには、この設定が必要です。」

<div id="common-misconceptions" />

## よくある誤解

<div id="dont-believe-everything-you-hear" />

> 📘 **聞いた情報が、必ずしも正しいとは限りません。**
>
> 次の説明は正しいでしょうか？
>
> ![TrueOrFalse.png](https://files.readme.io/77212d5a12ce2af35b0a4c87ca9e58213b4f9fd88c775007793e7abb5aaa3f04-35682597298577.png)
>
> * 広告主は、ポストバックの取得をアドネットワークに頼る必要がなくなる。
>   * **誤りです。** 重要な情報を読み解くには、引き続きアドネットワークからの情報が必要です。たとえば、SKANキャンペーンIDとキャンペーン名を対応付けられるのは、アドネットワークだけです。
> * 追加のエンドポイントを設定すると、すぐにすべてのポストバックのコピーがそこに送信される。
>   * **誤りです。** 追加のエンドポイントへの送信は、iOS15以降のデバイスでのみ利用できます。それより前のバージョンのデバイスからは、ポストバックのコピーは送信されません。

<div id="traits-and-limitations" />

## 仕様と制限事項

ポストバックのコピーをAppsFlyerに送信する設定をしてから、ダッシュボードに表示されるまでに数日かかる場合があります。

<div id="see-also" />

> 📄 **関連情報**
>
> * <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_an_advertised_app?changes=latest_minor#see-also">Appleの開発者向けドキュメント</Anchor>

<div data-zendesk-anchors="h_01KDSTGH21EG5MT0KFXZ40VMW1=%E6%B3%A8%E6%84%8F why-send-postback-copies-to-appsflyer=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E3%82%B3%E3%83%94%E3%83%BC%E3%82%92appsflyer%E3%81%AB%E9%80%81%E4%BF%A1%E3%81%99%E3%82%8B%E7%90%86%E7%94%B1 h_01HE7SV29Y7DNSKAAR91MJX986=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E3%82%B3%E3%83%94%E3%83%BC%E3%82%92appsflyer%E3%81%AB%E9%80%81%E4%BF%A1%E3%81%99%E3%82%8B%E7%90%86%E7%94%B1 configure-your-app-to-send-postback-copies-to-appsflyer=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E3%82%B3%E3%83%94%E3%83%BC%E3%82%92appsflyer%E3%81%AB%E9%80%81%E4%BF%A1%E3%81%99%E3%82%8B%E3%81%9F%E3%82%81%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HE7SV29YDFA5Z0X4WS87YK0Y=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E3%82%B3%E3%83%94%E3%83%BC%E3%82%92appsflyer%E3%81%AB%E9%80%81%E4%BF%A1%E3%81%99%E3%82%8B%E3%81%9F%E3%82%81%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HH9WCVH4C37ZGMRZRB7EQT6B=%E9%87%8D%E8%A6%81 common-misconceptions=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%AA%A4%E8%A7%A3 h_01HE7SV29YC855TGCXTCT4KHRN=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%AA%A4%E8%A7%A3 h_01HE7SV29YMMTPH6EKYF3GQYEN=%E8%81%9E%E3%81%84%E3%81%9F%E6%83%85%E5%A0%B1%E3%81%8C%E5%BF%85%E3%81%9A%E3%81%97%E3%82%82%E6%AD%A3%E3%81%97%E3%81%84%E3%81%A8%E3%81%AF%E9%99%90%E3%82%8A%E3%81%BE%E3%81%9B%E3%82%93 traits-and-limitations=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HHH74CC5X0T5M1F86XWMNH9V=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HE7SX466CMCC03K99H68ZRBN=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />
