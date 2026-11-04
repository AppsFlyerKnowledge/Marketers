---
title: Web SDKのトラブルシューティング
metadata:
  keywords:
    - People Based Attribution
    - People Based Attribution SDK
    - Developers
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2019-07-22T13:55:15Z'
  edited_at: '2026-10-14T09:28:51Z'
  id: 360002075858
  locale: ja
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ja/articles/360002075858
---
> **概要：** 概要： AppsFlyer ウェブSDKのトラブルシューティングガイドは、ウェブサイトに直接追加されるか、Google タグマネージャーを介して実装されます。

<div id="sdk-added-directly" />

## SDKを直接追加

SDKをWebサイトに直接追加できます。

<div id="no-data-or-partial-data-in-the-pba-dashboard" />

### PBA管理画面にデータが表示されない、または部分的にしかデータが表示されない

| 原因 | 解決策 |
| --- | --- |
| SDK を実装した後、 <Anchor target="_blank" href="/marketers/ja/docs/pba-website-attribution-dashboard">PBAダッシュボード</Anchor> にデータが表示されるまでに最大 24時間かかります。 | 24時間待ちます。それでもデータが利用できない場合は、このドキュメントのその他の原因を参照してください。 |
| 不正なWeb開発キー | <ul><li>Web SDK は、ウェブ開発キーを使用して、データの紐付け先となるバンドルを知るために送信されたウェブイベントを識別します。</li><li><Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide#ensure-that-the-sdk-is-working">正しいWeb開発キー</Anchor> を使用していることを確認します。</li></ul><Anchor target="_blank" href="/marketers/ja/docs/pba-brand-bundles-and-settings#add-brand-bundle">ブランドバンドルページ</Anchor> |
| ページの本文にWeb SDKを配置した | <ul><li>Web SDKはページの本文にを配置できますが、これはAppsFlyerに送信されるデータに影響を与える可能性があります。</li><li>ページのヘッドセクションに配置することをお勧めします。</li></ul> |
| Web SDKがWebサイトのすべてのページに配置されていない | Web SDKをWebサイトのすべてのページに配置することをお勧めします。 |

<div id="events-are-not-sent" />

### イベントは送信されない

| 原因 | 解決策 |
| --- | --- |
| Web SDKがロードされる前にイベントが送信されている | イベントを送信するコードの前に Web SDKが読み込まれていることを確認します。 |
| 不正なWeb開発キー | <ul><li>PBAは、データをどのバンドルに紐付けるかを知るために、Web開発キーを必要とします。正しいWeb開発キーが使用されていることを確認してください。</li><li><Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide#ensure-that-the-sdk-is-working">正しいWeb開発キー</Anchor> を使用していることを確認します。</li></ul> |
| 不正な形式のイベント | イベントの形式が正しいことを確認してください。<br /><br />正しい形式のイベントの詳細については、<Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide#web-sdk-event-parameters">利用可能なイベントパラメータ</Anchor>をご参照ください。 |
| SDKが2回呼び出される |  |

<div id="conflicting-sdks-and-libraries" />

### 競合するSDKおよびライブラリ

多くのWeb SDKは、一般的なJavaScriptライブラリを利用しています。そのようなSDKは、グローバルスコープの名前も占めます。例えば、Web SDKはWeb SDKを有効にするメインオブジェクトとして**AF**を占めています。

* 一部のSDKがライブラリXバージョン1.2を使用し、AppsFlyer SDKがライブラリX 2.1を使用する場合、2つのライブラリが競合する可能性があります。
* 別のSDKまたはライブラリが**AF**（グローバルスコープ内）をオブジェクト名として使用する場合、2つのSDKが競合し、1つのSDKが他をオーバーライドする可能性があります。

<div id="sdk-added-using-google-tag-manager" />

## Googleタグマネージャーを使用して追加されたSDK

* Googleタグマネージャー（GTM）を使用してWeb SDKを実装すると、時間を大幅に節約できます。
* 単独で実装でき、Web開発者にWebサイトへの追加を依頼する必要はありません。

問題が発生した場合、[SDKのネイティブ実装](/docs/troubleshooting-the-web-sdk#sdkを直接追加)で説明されている問題以外にも、GTMに固有の問題がいくつかあります。

<div id="calling-the-sdk" />

### SDKの呼び出し

| 原因 | 解決策 |
| --- | --- |
| <ul><li>Web SDKガイドは、タグを使用してWeb SDKを追加する方法を示しています。</li></ul><ul><li>一部のユーザーは、イベントを呼び出すタグを作成するときに、SDKタグも再度呼び出すようにタグを設定します。しかし、これは問題を引き起こす可能性があります。</li></ul>![mceclip0.png](https://files.readme.io/77be12759c5ec5a04a517ee1b99109e8952b97d1d4280b71c51fa36304f5adbf-360003756558.png) | 最善の方法は、1つのタグを設定してSDKをロードし、このタグをすべてのページで配信するように設定することです。イベントを送信するタグの場合、SDKタグを再度呼び出すことはできません。 |

<div id="tag-priority" />

### タグの優先度

GTMでは、<Anchor target="_blank" href="https://support.google.com/tagmanager/answer/2772421?hl=en">タグの優先度</Anchor>が設定できます。つまり、最初に配信されるタグを制御することができます。

| 原因 | 解決策 |
| --- | --- |
| SDKをロードするタグは、ページのロード時にイベントを送信するタグよりも優先度が低く設定されています。その結果、SDKはイベントの送信に間に合うように初期化されません。 | SDKを読み込むタグは、イベントを送信したりユーザーを識別したりするタグよりも常に優先度を高く設定してください。 |

<div id="triggering-tags" />

### トリガータグ

GTMでは、すべてのタグに、このタグを配信するタイミングを決定するトリガーがあります。

| 原因 | 解決策 |
| --- | --- |
| SDKをロードするタグの配信を担当するトリガーはすべてのページに設定されているわけではありません。その結果、すべてのページ訪問が記録されるわけではなく、一部のイベントが送信されません。 | 最善の方法は、SDKを読み込むタグに<Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7679319?hl=en">すべてのページビュー</Anchor>トリガーを設定することです。 |
| イベントを送信するタグの配信を担当するトリガーが正しく構成されていない。その結果、一部のイベントは送信されません。 | トリガーの条件を決定します。例：<ul><li>ボタンのクリックなどのDOM要素との相互作用</li><li>**/thank-you-page**または **/confirmation-page**などの特定のパスを持つページへのページ訪問</li></ul> |

<div id="publishing-gtm-containers" />

### GTMコンテナの公開

タグやトリガーの追加や編集など、GTMのすべての変更は、変更を有効にするためにGTMコンテナを公開する必要があります。GTMを使用してウェブSDKを使用しても、SDKが読み込まれないか、イベントが送信されない場合は、[GTMコンテナ1を公開](https://support.google.com/tagmanager/answer/6107163?hl=en)してください。

<div data-zendesk-anchors="sdk-added-directly=sdk%E3%82%92%E7%9B%B4%E6%8E%A5%E8%BF%BD%E5%8A%A0 no-data-or-partial-data-in-the-pba-dashboard=pba%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%AB%E3%83%87%E3%83%BC%E3%82%BF%E3%81%8C%E8%A1%A8%E7%A4%BA%E3%81%95%E3%82%8C%E3%81%AA%E3%81%84%E3%81%BE%E3%81%9F%E3%81%AF%E9%83%A8%E5%88%86%E7%9A%84%E3%81%AB%E3%81%97%E3%81%8B%E3%83%87%E3%83%BC%E3%82%BF%E3%81%8C%E8%A1%A8%E7%A4%BA%E3%81%95%E3%82%8C%E3%81%AA%E3%81%84 events-are-not-sent=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AF%E9%80%81%E4%BF%A1%E3%81%95%E3%82%8C%E3%81%AA%E3%81%84 conflicting-sdks-and-libraries=%E7%AB%B6%E5%90%88%E3%81%99%E3%82%8Bsdk%E3%81%8A%E3%82%88%E3%81%B3%E3%83%A9%E3%82%A4%E3%83%96%E3%83%A9%E3%83%AA sdk-added-using-google-tag-manager=google%E3%82%BF%E3%82%B0%E3%83%9E%E3%83%8D%E3%83%BC%E3%82%B8%E3%83%A3%E3%83%BC%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%A6%E8%BF%BD%E5%8A%A0%E3%81%95%E3%82%8C%E3%81%9Fsdk calling-the-sdk=sdk%E3%81%AE%E5%91%BC%E3%81%B3%E5%87%BA%E3%81%97 tag-priority=%E3%82%BF%E3%82%B0%E3%81%AE%E5%84%AA%E5%85%88%E5%BA%A6 triggering-tags=%E3%83%88%E3%83%AA%E3%82%AC%E3%83%BC%E3%82%BF%E3%82%B0 publishing-gtm-containers=gtm%E3%82%B3%E3%83%B3%E3%83%86%E3%83%8A%E3%81%AE%E5%85%AC%E9%96%8B" />
