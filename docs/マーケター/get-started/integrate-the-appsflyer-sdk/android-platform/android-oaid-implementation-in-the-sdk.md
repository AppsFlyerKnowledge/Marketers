---
title: Android SDKへのOAIDの実装
metadata:
  keywords:
    - China
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2020-02-27T20:21:05Z'
  edited_at: '2026-10-20T13:00:30Z'
  id: 360006278797
  locale: ja
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/ja/articles/360006278797
---
> **概要：** AndroidのOAIDを収集し、サードパーティのAndroidアプリストアからのインストールをアトリビューションします。

<div id="about-oaid" />

## OAIDについて

Open Anonymous Device Identifier（OAID）は、ユーザーがリセットできるAndroidデバイスの一意の識別子です。 IMEIなどのリセットできないデバイス識別子に代わる、プライバシーに配慮した識別子として、Mobile Security Alliance（MSA）、中国情報通信研究院、デバイスメーカーによって導入されました。

OAIDは通常、Google Play開発者サービスを利用できないデバイス（Google広告IDが存在しないデバイス）での広告計測やインストールアトリビューションに使用されます。

<span id="supported-devices"></span>MSAが提供するSDKを使用すると、すべてのデバイスでOAIDを読み取れます。Huaweiデバイスでは、Huawei Mobile Service（HMS）Core SDKを使用して読み取ることもできます。

<div id="integration" />

## 実装

OAIDの実装は、次の3つのステップで行います。

1. OAIDを生成・提供するSDK（MSA SDKまたはHuawei HMS SDK）を実装します。
2. AppsFlyer OAIDプラグインモジュールを実装します。
3. AppsFlyer SDKを実装します。

**注意**：

* 中国での利用を想定したアプリでは、MSA SDKを使用する必要があります。
* 世界各国のHuaweiデバイスでの利用を想定したアプリでは、Huawei HMSライブラリを使用してください。

<div id="msa-sdk" />

<Accordion title="MSA SDK">

**MSA SDKの実装と利用手順**：

1. [MSAのWebサイト](http://www.msa-alliance.cn/col.jsp?id=120)の手順に従って、アプリを登録します。
   * 登録すると、SDKをダウンロードできます。
   * 登録手続きで受け取る証明書ファイルを、アプリに追加する必要があります。
2. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#msa-sdk-integration">実装手順</Anchor>に従って対応するよう、開発者に依頼してください。

</Accordion>

<div id="huawei-hms-sdk" />

<Accordion title="Huawei HMS SDK">

**Huawei HMS SDKの実装と利用手順**：

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#huawei-hms-sdk-integration">実装手順</Anchor>に従って対応するよう、開発者に依頼してください。

</Accordion>

<div id="additional-information" />

## 補足情報

<div id="opting-out-of-oaid-collection" />

<Accordion title="OAIDの収集の停止">

OAIDの実装が完了すると、SDKは自動的にOAIDの収集を試みます。特定のユーザーのOAIDを収集しないようにする場合は、次のいずれかを使用するよう開発者に依頼してください。

&lt;0>Android0> &lt;1>Unity1>

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectoaid">setCollectOAID(false) API</Anchor>または<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers">setDisableAdvertisingIdentifiers</Anchor>

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectoaid">setCollectOAID(false) API</Anchor>または<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setdisableadvertisingidentifiers">setDisableAdvertisingIdentifiers</Anchor>

<div id="setting-oaid-manually" />

<Accordion title="OAIDの手動設定">

アプリですでにOAIDを収集している場合は、AppsFlyer OAIDプラグインの実装を省略できます。<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#setting-oaid-manually">setOaidData API</Anchor>を使用して、AppsFlyer SDKにOAIDの値を手動で設定してください。

</Accordion>

</Accordion>

<div data-zendesk-anchors="about-oaid=oaid%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HG8PXBZS1SN3SY3AAH1EKMNP=oaid%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 integration=%E5%AE%9F%E8%A3%85 h_01HG8PXBZS26P9X1TQ7J4WQNF5=%E5%AE%9F%E8%A3%85 h_01HG8PXBZSM0QYQE4C9S1FBFB1=msa-sdk h_01HG8PXBZS3HP9X1AZ7HQ8C34Y=huawei-hms-sdk additional-information=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 h_01HG8PXBZSW5HNTTDRQ7DFFF4D=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 h_01HG8PXBZS8Z3MTQWFN5R6FFA8=opting-out-of-oaid-collection h_01HG8PXBZSYNS8R1PCW4YXHFBA=setting-oaid-manually" />
