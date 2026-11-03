---
title: ピープルベースドアトリビューション (PBA)—概要
metadata:
  keywords:
    - People Based Analysis
    - People Based Attribution
    - People Based Attribution SDK
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-08-19T11:53:56Z'
  edited_at: '2026-10-14T09:39:23Z'
  id: 360002274017
  locale: ja
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ja/articles/360002274017
---
> **概要：概要： People-Based Attribution (PBA)は、チャネル、プラットフォーム、デバイスを横断したカスタマージャーニーを統合した1つのビューで見ることを可能にします。**

![PBANoSilos_us-en.gif](https://files.readme.io/1ac3614eb1b9d4c01bffbe904f1a060d1facd681ff32c274b12f0a15612a2e4a-360009359798.gif)

## PBAの原理原則

* PBAのデータ (PBAの管理画面及びローデータ) は、マーケティング分析とキャンペーンの最適化に使用可能です。
* Webサイト訪問とユーザーイベントのデータは、 <Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide">SDKおよび/またはAPIを使用して取得されます。</Anchor>
* ウェブサイトへの訪問ごと：訪問をもたらすメディアソースが決定されます。結果のイベント（コンバージョン）<Anchor target="_blank" href="/marketers/ja/docs/pba-media-source-attribution-rules">は、</Anchor> 訪問の要因となったメディアソースに紐づけられます。

### PBAの管理画面とローデータ

* PBAデータは、分析ダッシュボードとレポートを介して表示されます。
  * Webサイト計測
  * Webアシストインストール
  * ローデータレポート
* 管理画面内のデータは、モバイルプラットフォーム、メディアチャネル、メディアタイプなどの項目を使用して<Anchor target="_blank" href="/marketers/ja/docs/using-pba-dashboards">フィルタリング＆グループ化されるので、</Anchor>任意のデータをドリルダウンして分析してください。

### <Anchor target="_blank" href="/marketers/ja/docs/pba-website-attribution-dashboard">Webサイト計測</Anchor>

[![WebsiteAttributionTable_us-en.jpg](https://files.readme.io/46f03ee216dc23f3f184663aeef7d6b64ae6fb9a64e7a161ff0482e4d2eab204-360013057757.jpg)](https://files.readme.io/46f03ee216dc23f3f184663aeef7d6b64ae6fb9a64e7a161ff0482e4d2eab204-360013057757.jpg)

Webトラフィックソースとマーケティングキャンペーンを分析して、Webサイトでのユーザー訪問とコンバージョンを促進します。広告レベルまでパフォーマンスの違いを明らかにします。リンク内のすべてのAppsFlyerクエリパラメータをサポートし、ユーザーをAppsFlyerサーバーにリダイレクトする必要はありません。

### <Anchor target="_blank" href="/marketers/ja/docs/pba-web-assisted-installs">Webアシストインストール</Anchor>

[![AppsFlyer-Web-to-App_us.en.gif](https://files.readme.io/4a278b57379c999d80fd7f1dfea750049f56c03ed32051f9af92577b2a51742a-360009705058.gif)](https://files.readme.io/4a278b57379c999d80fd7f1dfea750049f56c03ed32051f9af92577b2a51742a-360009705058.gif)

ウェブアシストインストールを使用すると、モバイルアプリのインストール促進に対するウェブマーケティング活動の影響と結果を調べることができます。

* さまざまなメディアタイプ（有料、オウンド、アーンド）やメディアチャンネル（ダイレクト、ソーシャルメディア、オーガニック検索）、メディアソースが、どのように相互作用し、全体的なユーザー獲得の取り組みに貢献しているかについての洞察を提供します。
* Webマーケティングによって促進されたオーガニックインストールを可視化します。
* Webマーケティングと非オーガニックインストールの関連性を表示します。

### <Anchor target="_blank" href="/marketers/ja/docs/pba-raw-data-reports">ローデータ</Anchor>

ローデータレポートはData Lockerで入手可能ですローデータは、Webサイトへユーザーを誘導したメディアソースなどの詳細なインサイトを提供します。

* ウェブ訪問：ウェブサイトへのアクセス
* Web events: 購読申し込みや購入など、Webサイト上で行われたアクション
* BIツールは追加のインサイトのためにデータを分析するときに使用されます。

<div data-zendesk-anchors="pba-principles=pba%E3%81%AE%E5%8E%9F%E7%90%86%E5%8E%9F%E5%89%87 01ECF26CMJ8TB4ADT6VN277EMQ=pba%E3%81%AE%E5%8E%9F%E7%90%86%E5%8E%9F%E5%89%87 pba-analytics-dashboards-and-raw-data=pba%E3%81%AE%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%A8%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF 01ECF26CMJDA1HBC22DGRWY2EA=pba%E3%81%AE%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%A8%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF website-attribution=web%E3%82%B5%E3%82%A4%E3%83%88%E8%A8%88%E6%B8%AC 01ECF26CMK0T5C9JKQ0SYMXQVM=web%E3%82%B5%E3%82%A4%E3%83%88%E8%A8%88%E6%B8%AC webassisted-installs=web%E3%82%A2%E3%82%B7%E3%82%B9%E3%83%88%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB 01ECF26CMKDS16XWRBQ1SDAX2Q=web%E3%82%A2%E3%82%B7%E3%82%B9%E3%83%88%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB raw-data=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF 01ECF26CMM4KHX9W94DND4BY8C=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF h_01HE0Y2KTXS06WHN57MQ91AD09=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF" />
