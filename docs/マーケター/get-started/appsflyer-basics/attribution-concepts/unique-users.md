---
title: ユニークユーザー
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2024-08-11T09:52:33Z'
  edited_at: '2026-10-28T09:08:18Z'
  id: 27435981457553
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/27435981457553
---
> **概要：** AppsFlyerのダッシュボードやレポートで、ユニークユーザーをどのように数え、各指標に使用するかを説明します。

<div id="about-unique-users" />

## ユニークユーザーについて

本記事でいうユニークユーザーは、アトリビューションの対象となったデバイスを単位として数えます。同じデバイスでユーザーが何回操作しても、1ユーザーとして数えます。

この計算方法は、以下をはじめとするさまざまなマーケティング指標で使用します。

* インストール数：アプリをダウンロードしてインストールしたユニークユーザー数。
* リテンション率：対象日にセッションがあったユニークユーザーの割合。
* イベントのユニークユーザー数：イベントを実行したユニークユーザー数（アトリビューション数）。
* 日次アクティブユーザー数（DAU）：その日に1回以上アプリを起動したユニークユーザー数。同じユーザーは1回だけ数えます。
* このほかにも、多くの指標で使用します。

ユニークユーザーの算出には、IDFAやGAIDなどのデバイスIDを使用します。 iOSのSKANなど、デバイスIDを利用できない場合は、代わりにAppsFlyer IDを使用します。すべてのアクションで同じデバイスIDまたはAppsFlyer IDを使用するため、セッションやアクションの回数に関係なく、ユーザーを1回だけ数えられます。

<div id="use-cases" />

## ケース別の集計方法

通常、ユニークユーザーの計算方法は単純ですが、特定の行動や操作では、数え方が分かりにくい場合があります。以下では、そうした少し複雑なケースでの集計方法を説明します。

<div id="install-and-reinstall" />

<Accordion title="インストールと再インストール">

<Image align="center" alt="" src="https://files.readme.io/8b9f3c442f98c056069b4449c7e5115cbea828a64ace3a98e0090fb0d8d1d8d6-27455116159889.png" />

インストールと再インストールは、同じデバイスID／AppsFlyer IDを持ちます。そのため、ユニークユーザーは1人として計上されます。両方のアプリ内イベントは、初回インストールと同じユニークユーザーに紐付けられます。

**注意**：

* 再インストールにデバイスID／AppsFlyer IDが含まれていない場合、初回インストールに紐付けられず、「元のインストールに紐付かないオーガニック」として扱われます。このような再インストール後のイベントは、ユニークユーザー数に含まれません。
* 他の理由で、イベントが元のインストールに紐付かないオーガニックとなる場合もあります。その場合も、ユニークユーザー数に含まれません。

</Accordion>

<div id="install-and-reattribution" />

<Accordion title="インストールとリアトリビューション">

<Image align="center" alt="" src="https://files.readme.io/40420c5ea201ba7cf13d03e5968d20c2fffaa31b74c47ae36cd917cccbaae353-27453973190289.png" />

インストールとリアトリビューションは、同じデバイスIDを持ちます（AppsFlyer IDも同じです）。ただし、この場合は`is_retargeting=true`も考慮されるため、リアトリビューション後のイベントは、追加のユニークユーザーとして計上されます。そのため、ユニークユーザーは2人として計上されます。

* Overview dashboardのUA表示には、リターゲティングのリアトリビューションが含まれないため、ユニークユーザーは1人と表示されます。 UAレポートも同様です。
* Overview dashboardのリターゲティング表示には、UAのインストールが含まれないため、ユニークユーザーは1人と表示されます。リターゲティングレポートも同様です。
* Overview dashboardの統合表示では、初回インストールに紐付く1人と、リアトリビューションに紐付く1人を合わせて、ユニークユーザーは2人と表示されます。統合レポートも同様です。

</Accordion>

<div id="install-and-reengagement" />

<Accordion title="インストールとリエンゲージメント">

<Image align="center" alt="" src="https://files.readme.io/a49b8278816429295138e6c6a154194f423512ba2b7ba78fd756d346430dbd12-51444293138065.png" />

インストールとリエンゲージメントは、同じデバイスID／AppsFlyer IDを持ちます。ただし、リアトリビューションと同様に、`is_retargeting=true`も考慮されるため、リエンゲージメント後のイベントは、追加のユニークユーザーとして計上されます。そのため、ユニークユーザーは2人として計上されます。

* Overview dashboardのUA表示には、リターゲティングのリエンゲージメントが含まれないため、ユニークユーザーは1人と表示されます。 UAレポートも同様です。
* Overview dashboardのリターゲティング表示には、UAのインストールが含まれないため、ユニークユーザーは1人と表示されます。リターゲティングレポートも同様です。
* Overview dashboardの統合表示では、初回インストールに紐付く1人と、リエンゲージメントに紐付く1人を合わせて、ユニークユーザーは2人と表示されます。統合レポートも同様です。

</Accordion>

<div id="unattributed-inapp-events" />

<Accordion title="元のインストールに紐付かないアプリ内イベント">

<Image align="center" alt="" src="https://files.readme.io/94bf078bcf4ba26a1dc4ca323a1b4a7543cfb4e3fc8b780d0d29713c4266aa95-27455116170001.png" />

再インストール後のアプリ内イベントが、何らかの理由で初回インストールに紐付かない場合、ユニークユーザー数には一切含まれません。再インストール時にデバイスIDを取得できない場合などに発生しますが、**他の理由でも発生する場合があります**。<Anchor target="_blank" href="/marketers/ja/docs/measure-reinstalls#unattributed-organic-inapps">詳細を見る</Anchor>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="仕様と制限事項">

| 項目 | 詳細 |
| --- | --- |
| 広告収益イベント<br /><br />（af\_ad revenue） | <ul><li>広告収益イベントのユニークユーザー数は、以下の指標で利用できます。<ul><li>コホートの当日指標</li><li>アクティビティの指標</li><li>SKANの指標</li></ul></li><li>広告収益イベントのユニークユーザー数は、以下の指標では利用できません。<ul><li>コホートの累計指標</li><li>従来のアトリビューション方法によるLTV指標。**注意**：ダッシュボードのSSOT表示では、広告収益イベントのユニークユーザー数を確認できるのはSKANデータのみです。従来のアトリビューションのデータでは確認できません。</li></ul></li></ul> |

</Accordion>

<div data-zendesk-anchors="overview=%E3%83%A6%E3%83%8B%E3%83%BC%E3%82%AF%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 01H7Z1003GTTMRY072BXWDFNP0=%E3%83%A6%E3%83%8B%E3%83%BC%E3%82%AF%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 use-cases=%E3%82%B1%E3%83%BC%E3%82%B9%E5%88%A5%E3%81%AE%E9%9B%86%E8%A8%88%E6%96%B9%E6%B3%95 h_01J52T4MT63JVJEQ050E2BXMVQ=%E3%82%B1%E3%83%BC%E3%82%B9%E5%88%A5%E3%81%AE%E9%9B%86%E8%A8%88%E6%96%B9%E6%B3%95 h_01J52T9B4ZZH1TBW98YM5MY675=install-and-reinstall h_01J52T9B4ZYWQAGS3QHG99G3AS=install-and-reattribution h_01J531V2AKW8QP33B6K8QFH72R=install-and-reengagement h_01J52WPCZEBFP4RR0Y4ZC5TABK=unattributed-inapp-events h_01J52ZHXKYDG77PE70QZV63KY3=traits-and-limitations" />
