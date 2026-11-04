---
title: デバイス識別子について
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2021-10-12T14:16:09Z'
  edited_at: '2026-10-28T09:07:18Z'
  id: 4408847686161
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/4408847686161
---
> **概要：** AppsFlyer SDKが対応するデバイス識別子を説明します。

<div id="overview" />

## 概要

AppsFlyer SDKでは、アプリの<Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#アトリビューション">アトリビューション</Anchor>や分析に使用するデバイス識別子を設定できます。

アプリの要件、適用されるプラットフォームのポリシー、ユーザーの同意に基づいて、GAID、IDFA、IDFVなどの広告識別子を取得するようSDKを設定できます。（例：サードパーティのAndroidアプリストアや、中国で提供されるアプリ）。

<div id="android-device-identifiers" />

## Androidのデバイス識別子

SDKは、Androidプラットフォームで以下のデバイス識別子に対応しています。

<div id="apps-published-on-google-play" />

#### Google Playで公開するアプリ

| デバイス識別子 | 用途 |
| --- | --- |
| <span id="gaid"></span>GAID | Google PlayのAndroidユーザー向けの、**ユーザーがリセットできる**識別子です。<br /><br />SDK V4.8.0以降、AppsFlyerはこのデバイス識別子を自動収集します。 |

<div id="apps-published-in-third-party-app-stores" />

#### サードパーティのアプリストアで公開するアプリ

| デバイス識別子 | 用途 |
| --- | --- |
| <span id="amazon-advertising-id"></span>Amazon Advertising ID | Amazon Fire TVで使用する、**ユーザーがリセットできる**一意の識別子です。 <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts">CTVの概要を参照</Anchor> |
| <span id="oaid"></span>OAID | Google Play以外の一部のAndroidマーケットで使用する、**ユーザーがリセットできる**識別子です。  詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/android-oaid-implementation-in-the-sdk">OAIDの実装ガイド</Anchor>を参照してください。 |
| <span id="android-id"></span>Android ID | サードパーティのアプリストアで使用する、**リセットできない**一意のモバイルデバイス識別子です。 SDKはAndroid IDを自動収集しません。収集が必要な場合は、開発者が収集処理を実装できます。<br /><br />**注意：** Android IDとGAIDは併用できません。 |

<div id="apple-device-identifiers" />

## Appleのデバイス識別子

SDKは、iOSプラットフォームで以下のデバイス識別子に対応しています。

| デバイス識別子 | 用途 |
| --- | --- |
| <span id="idfa"></span>IDFA | AppleのiOSまたはtvOS（Apple TV）ユーザー向けの、**ユーザーがリセットできる**一意の識別子です。 iOS 14.5以降、IDFAを取得できるのは、ユーザーが<Anchor target="_blank" href="/marketers/ja/docs/about-att-and-skan#att-principles">ATTの同意画面</Anchor>で同意した場合のみです。 |
| <span id="idfv"></span>IDFV | デバイス上の**同一ベンダー**のすべてのアプリで共有するデバイス識別子です。最初のアプリをインストールするとIDFVが割り当てられ、同じベンダーの他のアプリにも同じIDFVが割り当てられます。別のベンダーのアプリには、異なるIDFVが割り当てられます。<br /><br />また、特定のベンダーのアプリをすべて削除すると、そのベンダーのIDFVも削除されます。その後、新たにアプリをインストールすると、新しいIDFVが割り当てられます。 |

<div id="ctv--pc-and-console-app-device-identifiers" />

## CTV、PC、コンソールアプリのデバイス識別子

SDKは、CTV、PC、コンソールの各プラットフォームで以下のデバイス識別子に対応しています。

| プラットフォーム | デバイスID |
| --- | --- |
| Android TV | advertising\_id |
| tvOS (Apple TV) | idfa |
| Amazon Fire TV | amazon\_fire\_id |
| Chromecast | advertising\_id |
| Roku | rida |
| Vizio | vida |
| Samsung | tifa |
| LG | LG Ads=lg\_adid |
| Xbox | custom |
| Vidaa | vidaaid |
| Steam | steamid |
| Meta Quest (Oculus) | custom |
| Epic Games | epicid |
| PlayStation | psid |
| ネイティブPCアプリ | custom |
| Google Play Games on PC | [Androidの識別子](/docs/about-device-identifiers#androidのデバイス識別子)を参照してください。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01H9YXEYC3PA271B3G3Y3GM9PS=%E6%A6%82%E8%A6%81 android-device-identifiers=android%E3%81%AE%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E8%AD%98%E5%88%A5%E5%AD%90 h_01H9YXEYC3D95A6G70EGNR8ENK=android%E3%81%AE%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E8%AD%98%E5%88%A5%E5%AD%90 apps-published-on-google-play=google-play%E3%81%A7%E5%85%AC%E9%96%8B%E3%81%99%E3%82%8B%E3%82%A2%E3%83%97%E3%83%AA h_01H9YXEYC3RG2XCVVW8MJ5VZSC=google-play%E3%81%A7%E5%85%AC%E9%96%8B%E3%81%99%E3%82%8B%E3%82%A2%E3%83%97%E3%83%AA apps-published-in-thirdparty-app-stores=%E3%82%B5%E3%83%BC%E3%83%89%E3%83%91%E3%83%BC%E3%83%86%E3%82%A3%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B9%E3%83%88%E3%82%A2%E3%81%A7%E5%85%AC%E9%96%8B%E3%81%99%E3%82%8B%E3%82%A2%E3%83%97%E3%83%AA h_01H9YXEYC3JA3DPN6P43J1ZXR9=%E3%82%B5%E3%83%BC%E3%83%89%E3%83%91%E3%83%BC%E3%83%86%E3%82%A3%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B9%E3%83%88%E3%82%A2%E3%81%A7%E5%85%AC%E9%96%8B%E3%81%99%E3%82%8B%E3%82%A2%E3%83%97%E3%83%AA apple-device-identifiers=apple%E3%81%AE%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E8%AD%98%E5%88%A5%E5%AD%90 h_01H9YXEYC3733B1A85TEF35EAY=apple%E3%81%AE%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E8%AD%98%E5%88%A5%E5%AD%90 ctv-device-identifiers=ctvpc%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E8%AD%98%E5%88%A5%E5%AD%90 h_01H9YXEYC3DFPWVXA5Y3XANQ3P=ctvpc%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E8%AD%98%E5%88%A5%E5%AD%90" />
