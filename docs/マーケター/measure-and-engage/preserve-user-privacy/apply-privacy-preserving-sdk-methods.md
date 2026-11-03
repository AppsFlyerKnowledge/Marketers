---
title: SDKのプライバシー保護メソッド
metadata:
  keywords:
    - Advertisers
    - coppa
    - opt-out
    - opt out
    - consent management
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
  created_at: '2018-08-20T11:14:36Z'
  edited_at: '2026-10-14T09:30:37Z'
  id: 360001422989
  locale: ja
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ja/articles/360001422989
---
> **概要：** AppsFlyer SDKで利用できるユーザーのプライバシー保護が可能な複数のメソッドに関して説明します。

> 📘 **注意**
>
> 本記事で紹介する情報は、アプリ開発者が、アプリ所有者、アドネットワーク、ソーシャルネットワークとのユーザー関連データの共有を制御するために利用可能な方法についての知見を提供することのみを目的としています。**記事には、COPPAやGDPRなどのプライバシー規制や、特定のプライバシー保護規制の遵守に関するガイダンスは含まれていません。**

AppsFlyer SDKは、ユーザーのプライバシーを保護し、データを管理するためのいくつかの方法をアプリ所有者に提供します。この記事では、これらの方法を探り、ユーザーデータにどのような影響を与えるか、また、アトリビューションを許可しながらユーザーのプライバシーを保護するために使用する方法を検証します。

使用したいオプションを検討し、Dev Hubの実装情報を開発者と共有してください。

それではここからそれぞれの方法について説明します。

## 初期化と停止メソッドの仕様

SDKは、初期化（`start`）メソッドが呼び出された後にのみ、インストールとアプリ内イベントをAppsFlyerに送信します。`start` の呼び出しに先行するイベントは、SDKによってレポートされません。同様に、`start` の呼び出しが、`stop` メソッドの呼び出しによって取り消された場合、それ以降イベントは送信されません。

### アトリビューションへの影響

アトリビューションは、次の場合には発生**しません**：

* `start` メソッドがコールされていない場合
* `stop` メソッドが、前の [start] を元に戻すために呼び出される場合

### 一般的な使用例

| 使用例 | 説明 |
| --- | --- |
| 起動時のオプトインまたはオプトアウト | 初回起動時にユーザーがデータ共有に同意した後、`start` をコールします。  <br />ユーザーがデータ共有に同意しない場合は、  <br />`start` をコールしません。 |
| セッションのオプトアウト | すべてのアプリセッションで同意を求め、それに応じて `start` を呼び出すか、呼び出さないかを選びます。 |
| ワンタイムオプトアウト（ユーザーがオプトインした後、オプトアウトすることを決定した場合） | `stop` を呼び出して、SDKが今後のイベントを送信するのを停止します。 |

### 開発者向けリファレンス

開始 / 停止メソッドの使用方法に関する開発者リファレンスとドキュメントは、以下を参照してください：

<Tabs>
<Tab title="Android">

[開始を使用して、インストールイベントのみを共有する](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#use-start-to-share-only-the-install-event)

</Tab>

<Tab title="iOS">

[開始を使用して、インストールイベントのみを共有する](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#use-start-to-share-only-the-install-event)

</Tab>
</Tabs>

## ネットワークとのデータ共有を防ぐ

アドネットワークまたはセルフレポーティングネットワーク（SRN媒体）との連携時に、そのパートナーとユーザーレベルの情報を共有するかどうかを選択できます。SDKでは、この `setSharingFilterForPartners` メソッドを使用して、**エンドユーザーの好みに応じて**、すべてまたは一部のパートナーとのデータ共有をさらにフィルター処理できます。

この方法を使用すると、AppsFlyerは、ポストバック、API、ローデータレポートなど、いかなる手段によっても、除外されたパートナーとのユーザーデータの共有を無効にします。

### アトリビューションへの影響

* **除外されたアドネットワーク** <strong>（SRN以外）</strong>からのインストールはAppsFlyerにアトリビューションされますが、アドネットワークにはいかなる形式や方法でも通知されません。
* **除外されたSRN**からのインストールはアトリビューションされず、そのデータは連携済みパートナーと共有されません。

  > 📘 **注意**
  >
  > AppsFlyerは、お客様のデータ取得から除外されたSRNのエンゲージメントデータをアトリビューションすることはできません。


### 開発者向けリファレンス

サードパーティとのデータ共有を防ぐ方法に関する開発者向けリファレンスとドキュメントは、以下を参照してください：

<Tabs>
<Tab title="Android">

[第三者とのデータ共有の防止](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#prevent-sharing-data-with-third-parties)

</Tab>

<Tab title="iOS">

[第三者とのデータ共有の防止](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#prevent-sharing-data-with-third-parties)

</Tab>
</Tabs>

## ユーザー情報の匿名化

`anonymizeUser` メソッドを使用して、すべてのユーザー識別情報の削除をAppsFlyerに指示するようにSDKを設定できます。この場合、SDKはインストールイベントとアプリ内イベントをAppsFlyerに送信し、そこですべての識別情報が削除またはハッシュ化されます。

* **削除：** 個人識別子 (GAID、IDFA、IDFV、CUID)
* **暗号化：** AppsFlyer IDおよびIPアドレス

次の図は、匿名化（削除とハッシュ）後のローデータの行の例を示しています。

[![](https://files.readme.io/5cae15ee0e38c84b2f9876d0dca2145543e83e624933ca138017da5206e7a834-35847868223633.png)](https://files.readme.io/5cae15ee0e38c84b2f9876d0dca2145543e83e624933ca138017da5206e7a834-35847868223633.png)

### アトリビューションへの影響

`start` を呼び出す前に `anonymizeUser` を呼び出すと、アトリビューション計測はされません。すべてのアプリ内イベントは、ダッシュボードに応じてオーガニックとしてカウントされるか、完全に無視され表示されません。

> 👍 **ヒント**
>
> インストールイベントをアトリビューションするには、SDKがインストールイベントをAppsFlyerに送信したことを確認してから、`anonymizeUser` ファンクションをコールします。このフローにより、インストール後に発生したアプリ内イベントは識別子なしで送信され、その結果、アトリビューションされません。

### 開発者向けリファレンス

ユーザー情報を匿名化する方法については、開発者向けリファレンスとドキュメントを参照してください：

<Tabs>
<Tab title="Android">

[ユーザー情報の匿名化](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#anonymize-user-information)

</Tab>

<Tab title="iOS">

[ユーザー情報の匿名化](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#anonymize-user-information)

</Tab>
</Tabs>

## 特定のデバイス識別子を削除

SDKが特定のデバイス識別子を収集してAppsFlyerに送信するのを防ぐことができます。この `anonymizeUser` メソッドの使用とは対照的に、特定の識別子を無効にすると、保持したい識別子を決定できます。

SDK APIには、識別子を無効にする次のメソッドが含まれています。

### Android識別子

| メソッド | 無効になる識別子 |
| --- | --- |
| `setdisableadvertisingIdentifiers` | <ul><li>Google Advertising ID (GAID)</li><li>Open Anonymous Device Identifier (OAID)</li><li>Amazon Advertising ID (AAID)</li></ul> |
| [`setcollectoaid`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectoaid) | Open Anonymous Device Identifier (OAID) |

### iOS識別子

| メソッド | 無効になる識別子 |
| --- | --- |
| `disableAdvertisingIdentifier` | IDFA (iOS 13 以下) |
| `disableIDFVCollection` | IDFV |

### 開発者向けリファレンス

特定のデバイス識別子を削除する方法に関して、開発者向けリファレンスとドキュメントについては、以下をご参照ください：

<Tabs>
<Tab title="Android">

[識別子の無効化](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#disable-ids)

</Tab>

<Tab title="iOS">

[識別子の無効化](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#disable-ids)

</Tab>
</Tabs>

> 📘 **AppsFlyerのプライバシーについて質問がありますか?**
>
> お客様とAppsFlyerの間のプライバシー関係は、 [データ処理に関するAppsFlyer Statement](https://www.appsflyer.com/legal/processing-customer-data/)に準拠します。本声明に関するご質問、または当社のデータ保護責任者へのお問い合わせは、 [dpo@appsflyer.com](mailto:dpo@appsflyer.com) までEメールでお問い合わせください。

<div data-zendesk-anchors="h_01HKD1N2C8G348DPPG41HMC15J=%E6%B3%A8%E6%84%8F use-start-and-stop-methods=%E5%88%9D%E6%9C%9F%E5%8C%96%E3%81%A8%E5%81%9C%E6%AD%A2%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AE%E4%BB%95%E6%A7%98 h_01HKD1N2C8V0SP1NG8W2EJPRQZ=%E5%88%9D%E6%9C%9F%E5%8C%96%E3%81%A8%E5%81%9C%E6%AD%A2%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AE%E4%BB%95%E6%A7%98 impact-on-attribution=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%B8%E3%81%AE%E5%BD%B1%E9%9F%BF h_01HKD1N2C80QAJSNE83SD45DJA=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%B8%E3%81%AE%E5%BD%B1%E9%9F%BF common-use-cases=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E4%BD%BF%E7%94%A8%E4%BE%8B h_01HKD1N2C8YHWYARRAGX1TD6DM=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E4%BD%BF%E7%94%A8%E4%BE%8B developer-reference=%E9%96%8B%E7%99%BA%E8%80%85%E5%90%91%E3%81%91%E3%83%AA%E3%83%95%E3%82%A1%E3%83%AC%E3%83%B3%E3%82%B9 h_01HKM6VNJFCW77F2268XXDF65Q=%E9%96%8B%E7%99%BA%E8%80%85%E5%90%91%E3%81%91%E3%83%AA%E3%83%95%E3%82%A1%E3%83%AC%E3%83%B3%E3%82%B9 prevent-sharing-data-with-networks=%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%A8%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E5%85%B1%E6%9C%89%E3%82%92%E9%98%B2%E3%81%90 h_01HKD1N2C8ASV10XWY33R972MC=%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%A8%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E5%85%B1%E6%9C%89%E3%82%92%E9%98%B2%E3%81%90 impact-on-attribution::aa0a9f9e=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%B8%E3%81%AE%E5%BD%B1%E9%9F%BF-1 h_01HKD1N2C8RA34M4TSWYCW3A9F=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%B8%E3%81%AE%E5%BD%B1%E9%9F%BF-1 h_01HKD1N2C809Y9HE99WGXZYE39=%E6%B3%A8%E6%84%8F-1 developer-reference::f2007ab7=%E9%96%8B%E7%99%BA%E8%80%85%E5%90%91%E3%81%91%E3%83%AA%E3%83%95%E3%82%A1%E3%83%AC%E3%83%B3%E3%82%B9-1 h_01HKM6VNJFP8C7KCFSV1046H0B=%E9%96%8B%E7%99%BA%E8%80%85%E5%90%91%E3%81%91%E3%83%AA%E3%83%95%E3%82%A1%E3%83%AC%E3%83%B3%E3%82%B9-1 anonymize-user-information=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E6%83%85%E5%A0%B1%E3%81%AE%E5%8C%BF%E5%90%8D%E5%8C%96 h_01HKD1N2C8CWSWK0VSXZ39MQ3D=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E6%83%85%E5%A0%B1%E3%81%AE%E5%8C%BF%E5%90%8D%E5%8C%96 impact-on-attribution::601baa93=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%B8%E3%81%AE%E5%BD%B1%E9%9F%BF-2 h_01HKD1N2C8BFVCKD3BQS4HE75P=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%B8%E3%81%AE%E5%BD%B1%E9%9F%BF-2 h_01HKD1N2C80WW9JVBBFS5QDY7T=%E3%83%92%E3%83%B3%E3%83%88 developer-reference::e4cacf1f=%E9%96%8B%E7%99%BA%E8%80%85%E5%90%91%E3%81%91%E3%83%AA%E3%83%95%E3%82%A1%E3%83%AC%E3%83%B3%E3%82%B9-2 h_01HKM6VNJF7XPZ9ME61JG4KM9Z=%E9%96%8B%E7%99%BA%E8%80%85%E5%90%91%E3%81%91%E3%83%AA%E3%83%95%E3%82%A1%E3%83%AC%E3%83%B3%E3%82%B9-2 remove-specific-device-identifiers=%E7%89%B9%E5%AE%9A%E3%81%AE%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E8%AD%98%E5%88%A5%E5%AD%90%E3%82%92%E5%89%8A%E9%99%A4 h_01HKD1N2C8S3Y73AZ9J7JFDKQE=%E7%89%B9%E5%AE%9A%E3%81%AE%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E8%AD%98%E5%88%A5%E5%AD%90%E3%82%92%E5%89%8A%E9%99%A4 android-identifiers=android%E8%AD%98%E5%88%A5%E5%AD%90 h_01HKD1N2C8HZ61XHMBC0JNTK7S=android%E8%AD%98%E5%88%A5%E5%AD%90 ios-identifiers=ios%E8%AD%98%E5%88%A5%E5%AD%90 h_01HKD1N2C8AHK4EYANG6N6ST06=ios%E8%AD%98%E5%88%A5%E5%AD%90 developer-reference::4e0971d1=%E9%96%8B%E7%99%BA%E8%80%85%E5%90%91%E3%81%91%E3%83%AA%E3%83%95%E3%82%A1%E3%83%AC%E3%83%B3%E3%82%B9-3 h_01HKM6VNJFV0YJWV8KT23VTKKH=%E9%96%8B%E7%99%BA%E8%80%85%E5%90%91%E3%81%91%E3%83%AA%E3%83%95%E3%82%A1%E3%83%AC%E3%83%B3%E3%82%B9-3 h_01HKD1N2C8ZZX549W0KP3V16YQ=appsflyer%E3%81%AE%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6%E8%B3%AA%E5%95%8F%E3%81%8C%E3%81%82%E3%82%8A%E3%81%BE%E3%81%99%E3%81%8B" />
