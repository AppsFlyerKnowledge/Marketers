---
title: SDK情報（バージョン＆同意）管理画面
metadata:
  keywords:
    - SDK Information
    - Advertisers
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
  created_at: '2017-02-15T09:32:15Z'
  edited_at: '2026-10-14T09:29:50Z'
  id: 115000805366
  locale: ja
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/ja/articles/115000805366
---
> **概要：** 概要：SDK、オペレーティングシステム（iOS、Android）の普及率、そしてiOSのATT同意率を確認できる管理画面です。

## バージョン普及率とATTオプトイン管理画面

ダッシュボードのデータは af\_open (session) イベントを基に集計した数値であり、インストールデータに紐づくデータではありません。ダッシュボードには、主に以下の項目があります。

* SDKバージョン情報 - 全てのプラットフォーム（Android & iOS）が対象
* ATT同意メトリックとiOS 16.1 +の導入率（SKAN 4データの可能性を提供します）

SDK情報ページを確認する方法：

2. アクティビティの日付範囲を設定してください。   
   表示されるメトリクスについては、この後のセクションで説明します。

<div id="sdk-information-ios-and-android" />

<Accordion title="SDK情報（iOS / Android）">

以下は、最新のアプリ起動日を使用してiOSおよびAndroidアプリで使用できるバージョンメトリックを示しています。

| ユーザー数 | 例 |
| --- | --- |
| App version | 2021年5月20日にアプリバージョンV1.4.28が導入されたことが分かります。<br /><br />[![UsersByAppVersion__1_.png](https://files.readme.io/87bbf8aba8295e44430098c7c6fe4dc290cafca229e271a4185c763c609e9833-4402595560337.png)](https://files.readme.io/87bbf8aba8295e44430098c7c6fe4dc290cafca229e271a4185c763c609e9833-4402595560337.png) |
| SDKバージョン | SDKバージョンV6.1.4が2021年5月20日に導入されたことが分かります。<br /><br />[![UsersBySDKVersion.png](https://files.readme.io/df7b4a1f380cd10162b3a13efc5da1ccc4b96e47d994e4c42b2674bfd4930bb6-4402589094033.png)](https://files.readme.io/df7b4a1f380cd10162b3a13efc5da1ccc4b96e47d994e4c42b2674bfd4930bb6-4402589094033.png) |
| 端末OSのバージョン | [![UsersByOsVersion.png](https://files.readme.io/d56f8b43155bb226adaa1a276e00634fe721a01b74b5114d273ae66e74034dd9-4402589093521.png)](https://files.readme.io/d56f8b43155bb226adaa1a276e00634fe721a01b74b5114d273ae66e74034dd9-4402589093521.png) |
| Device type | [![UsersByDevice.png](https://files.readme.io/2f320f91d6a5a9f4bca0e3715cd33dfff2ac971af29e961592b4494bafe721f0-4402595560977.png)](https://files.readme.io/2f320f91d6a5a9f4bca0e3715cd33dfff2ac971af29e961592b4494bafe721f0-4402595560977.png) |

</Accordion>

<div id="att-metrics-ios-14" />

<Accordion title="iOS および ATT指標">

ユーザーが採用するiOSバージョンによって、利用可能なデータの種類に違いが生じる可能性があります。例：ユーザーが iOS 16.1+を使用している場合、SKAN 4データが利用可能になる可能性があります。

<Anchor target="_blank" href="/marketers/ja/docs/att-implications-ios-14-and-deprecation-of-lat">ATTステータス</Anchor>は、iOS によって設定され、アプリによってAppsFlyerに報告されます。指定されるATTステータスの値は次のとおりです。

* 承認Authorized（許可）：ユーザーがトラッキングされることを明示的に許可しました
* deniedDenied（拒否）：ユーザーがトラッキングされることを明示的に拒否したか、ユーザーがiOS 14以降にアップグレードする前にLATが有効でした
* Not determined
* Restricted（制限有り）

**次の点を考慮してください：**

* グラフのデータは、指定された日付のユニークユーザーのアプリ起動イベントを基に計算されています。つまり、選択した期間内にユーザーがアプリを起動しなかった場合、そのユーザーはその日の指標にカウントされません。

#### iOSアプリにおけるATTとiOSの導入指標

| Chart（グラフ） | 例 / 備考 |
| --- | --- |
| アプリ起動時のATTステータス | [![AttStatusByDate.png](https://files.readme.io/8e41e1602125903267e91a71b49305d43ca018aec77a2a991d0af08cb396825a-4402691807377.png)](https://files.readme.io/8e41e1602125903267e91a71b49305d43ca018aec77a2a991d0af08cb396825a-4402691807377.png)<br /><br />iOS 14以降の端末で、かつ指定された日付にアプリを起動したユーザーのデータです。これは、指定された日付におけるユーザーのATTステータスがメトリクスに表示されることを意味します。 |
| アプリバージョン別の同意 | [![ATTAppVersion.png](https://files.readme.io/1f19917998f142180d0fdfb5448c90b280b2d6536844c63ce630d3656719f656-4402589092113.png)](https://files.readme.io/1f19917998f142180d0fdfb5448c90b280b2d6536844c63ce630d3656719f656-4402589092113.png) |
| 同意トレンド | [![ConsentTrend.png](https://files.readme.io/bae0c55c603e83b87fa50ba6d16c628443d565417c1aceee4536a5b96dd9435e-4402589093265.png)](https://files.readme.io/bae0c55c603e83b87fa50ba6d16c628443d565417c1aceee4536a5b96dd9435e-4402589093265.png) |
| iOS 14.5 普及率 | [![iso_user_adoption_rate.png](https://files.readme.io/2a29749fd968354f9836595cf20f07954be1aedce97df140d1d14452eb7306b3-15478514320529.png)](https://files.readme.io/2a29749fd968354f9836595cf20f07954be1aedce97df140d1d14452eb7306b3-15478514320529.png) |

</Accordion>

<div data-zendesk-anchors="version-adoption-and-att-consent-dashboard=%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E6%99%AE%E5%8F%8A%E7%8E%87%E3%81%A8att%E3%82%AA%E3%83%97%E3%83%88%E3%82%A4%E3%83%B3%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2 h_01HGX98Q4FRVS2B35BVT683D5W=%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E6%99%AE%E5%8F%8A%E7%8E%87%E3%81%A8att%E3%82%AA%E3%83%97%E3%83%88%E3%82%A4%E3%83%B3%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2 h_01HGX98Q4F8PQYRSC0J2WE4RQX=sdk-information-ios-and-android h_01HGX98Q4FKWD5496P446FB31B=att-metrics-ios-14 att-and-ios-adoption-metrics-for-ios-apps=ios%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8Batt%E3%81%A8ios%E3%81%AE%E5%B0%8E%E5%85%A5%E6%8C%87%E6%A8%99 h_01HGX98Q4G0C4XTC1DSVP96M19=ios%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8Batt%E3%81%A8ios%E3%81%AE%E5%B0%8E%E5%85%A5%E6%8C%87%E6%A8%99" />
