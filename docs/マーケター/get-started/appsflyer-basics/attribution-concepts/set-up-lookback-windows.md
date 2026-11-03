---
title: ルックバック期間の設定
metadata:
  keywords:
    - Advertisers
    - look back
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-07T09:27:55Z'
  edited_at: '2026-10-28T09:08:07Z'
  id: 208338403
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/208338403
---
> **概要：** メディアソースとの合意内容に合わせて、クリックスルーとビュースルーのルックバック期間を設定します。

## ルックバック期間

アトリビューションのルックバック期間は、メディアソースとの合意内容に合わせて設定できます。

メディアソースごとにルックバック期間を設定すると、AppsFlyerは合意した条件に従ってアトリビューションを行います。

**ルックバック期間の種類**：

* **クリックのルックバック期間**：広告クリック後に発生したインストールを、その広告の成果として計測できる最長の期間です。ルックバック期間を過ぎてから発生したインストールは、オーガニックとして扱われます。
* **エンゲージクリックのルックバック期間：** エンゲージクリック後に発生したインストールを、そのエンゲージクリックの成果として計測できる最長の期間です。  ルックバック期間を過ぎてから発生したインストールは、オーガニックとして扱われます。
* **エンゲージビューのルックバック期間：** エンゲージビュー後に発生したインストールを、そのエンゲージビューの成果として計測できる最長の期間です。  ルックバック期間を過ぎてから発生したインストールは、オーガニックとして扱われます。
* **ビュースルーのルックバック期間**：広告表示後に発生したインストールを、その広告の成果として計測できる最長の期間です。ルックバック期間を過ぎてから発生したインストールは、オーガニックとして扱われます。

#### アトリビューションの種類別に設定できるルックバック期間

<table><thead><tr><th rowspan="2"><p><strong>アトリビューションの種類</strong></p></th><th rowspan="2"><p><strong>アトリビューション方法</strong></p></th><th colspan="2"><strong>ルックバック期間</strong> </th></tr><tr><th><strong>設定範囲</strong></th><th><strong>デフォルト</strong></th></tr></thead><tbody><tr><td rowspan="3"><p>クリックスルー</p><p>（すべてのメディアソース）</p></td><td>リファラ、IDマッチング</td><td>1～30日、または<br/>1～23時間</td><td>7日</td></tr><tr><td>確率論的モデリング（モバイル）</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">状況に応じて自動調整</a></td><td>最大24時間</td></tr><tr><td>確率論的モデリング（CTV・PC・コンソール：単一プラットフォーム向けリンク）</td><td>最大7日。（リンクの<code>af_lookback_window</code>パラメータで設定します。）</td><td>7日</td></tr><tr><td rowspan="2"><p>エンゲージクリックスルー</p><p>（SRN以外の、対応する一部の<a href="./about-enriched-engagement-types#エンゲージビューとエンゲージクリックを報告できるアドネットワーク" target="_blank">メディアソース</a>\*）</p></td><td>IDマッチング</td><td>1～7日、または1～23時間</td><td>2日</td></tr><tr><td>確率論的モデリング（モバイル）</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">状況に応じて自動調整</a></td><td>最大24時間</td></tr><tr><td rowspan="2"><p>エンゲージビュースルー</p><p>（SRN以外の、対応する一部の<a href="./about-enriched-engagement-types#エンゲージビューとエンゲージクリックを報告できるアドネットワーク" target="_blank">メディアソース</a>\*）</p></td><td>IDマッチング</td><td>1～7日、または1～23時間</td><td>2日</td></tr><tr><td>確率論的モデリング（モバイル）</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">状況に応じて自動調整</a></td><td>最大24時間</td></tr><tr><td rowspan="4"><p>ビュースルー</p><p>（対応している一部の<a href="./measure-view-through-engagements#view-vta-partner-list" target="_blank">メディアソース</a>）</p></td><td>IDマッチング</td><td><p>1～24時間</p><p>［2021年12月15日までは、上限は7日でした］</p></td><td>24時間</td></tr><tr><td>確率論的モデリング（モバイル）</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">状況に応じて自動調整</a></td><td>最大24時間</td></tr><tr><td>確率論的モデリング（CTV・PC・コンソール：単一プラットフォーム向けリンク）</td><td>最大7日。（リンクの<code>af_lookback_window</code>パラメータで設定します。）</td><td>24時間</td></tr><tr><td>確率論的モデリング（CTV・PC・コンソール：<a href="./set-up-cross-platform-links-for-multi-device-campaigns#特性と制限" target="_blank">クロスプラットフォーム向けOneLink計測リンク</a>）</td><td>最大72時間。（リンクの<code>af_xplatform_vt_lookback</code>パラメータで設定します。）</td><td>24時間</td></tr></tbody></table>

*`engaged_click`と`engaged_view`のルックバック期間を個別に設定できるのは、SRN以外のアドネットワークのみです。 SRNでは、`engaged_click`と`engaged_view`にクリックと同じルックバック期間が適用されるため、**Install Click-Through Attribution Lookback**のスライダーで設定します。

### 確率論的モデリングのルックバック期間

アトリビューションの精度を維持するために使用する、確率論的モデリングのルックバック期間には、以下の特徴があります。

* クリックとインプレッションの両方に適用されます。
* 期間は状況に応じて自動調整され、最長24時間です。
* 計測リンクで送信された期間の設定は適用されません。
* 決定論的モデルで使用するルックバック期間よりも短くなります。

詳細は、<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#probabilistic-modeling">AppsFlyerの確率論的モデリングによる計測方法</Anchor>をご覧ください。

## ルックバック期間の設定方法

以下では、SRNと計測リンクのルックバック期間の設定手順を説明します。

<Tabs>
<Tab title="SRNのルックバック期間">

### SRNのアトリビューションのルックバック期間

> 🚧 **重要**
>
> ルックバック期間のデフォルト値は、SRNごとに異なります。データの差異を最小限に抑えるため、AppsFlyerのルックバック期間をSRN側の設定値と一致させることをおすすめします。期間を変更すると、データに差異が生じる可能性があります。詳細は、[SRNとのデータの差異の例](#シナリオと設定例)をご覧ください。

1. AppsFlyerのサイドメニューで、**連携**＞**Partner Marketplace**を選択します。
2. SRNを検索して選択します。<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns#srn媒体">対応しているSRNの一覧</Anchor>をご覧ください。
3. ビュースルー計測は、デフォルトで有効になっています。
4. 「**連携**」タブで、「**クリックスルー計測**」と「**ビュースルー計測**」の設定までスクロールします。
5. スライダーを使用して、アトリビューションの対象期間を設定します。

各SRNのルックバック期間は、以下のとおりです。

| SRN | クリックスルーのルックバック期間のデフォルト値（日） | ビュースルーのルックバック期間のデフォルト値（時間） |
| --- | --- | --- |
| Google | 30 | 24 |
| Meta ads | 7 | 24 |
| Snapchat | 28 | 24 |
| X Ads | 14 | 24 |
| Apple Search Ads | 30 | 24 |
| Oath (YahooGemini) | 7 | 24 |

</Tab>

<Tab title="SRN以外のルックバック期間">

<div id="attribution-lookback-window-with-attribution-links" />

### SRN以外のクリックスルー・ビュースルーのルックバック期間

1. AppsFlyerのサイドメニューで、**連携**＞**有効な連携**を選択します。
2. パートナーを検索して選択します。
3. ビュースルー計測は、デフォルトで有効になっています。
4. 「**計測リンク**」タブをクリックします。
5. 期間の単位を、日または時間から選択します。
6. 「**クリックスルー計測**」（`af_click_lookback`パラメータ）と「**ビュースルー計測**」（`af_viewthrough_lookback`パラメータ）のスライダーを使用して、アトリビューションの対象期間を設定します。  
   設定した期間は、計測リンクに自動的に反映されます。
7. キャンペーン名や広告セットなど、キャンペーンに対応するパラメータを選択します。
8. リンクをコピーして保存します。このリンクをアドネットワークに共有してください。

<div id="h_01JKWVQB6TTA24VAZ9WVJMGY4X" />

### SRN以外のエンゲージクリックスルー・エンゲージビュースルーのルックバック期間

1. AppsFlyerのサイドメニューで、**連携**＞**有効な連携**を選択します。
2. パートナーを検索して選択します。
3. 「連携」タブで、「**エンゲージクリックによるインストールのルックバック期間**」または「**エンゲージビューによるインストールのルックバック期間**」のスライダーまでスクロールします。
4. スライダーを使用して、ルックバック期間を設定します。

> 👍 **ヒント**
>
> * ルックバック期間の設定に関するヒントや活用方法を知りたい場合は、 AppsFlyerラーニングポータルの<Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks">短時間で学べる実践的なコース</Anchor>をご覧ください。
> * アトリビューションの対象期間を時間単位で設定すべきケースについては、[こちら](/docs/set-up-lookback-windows#lookback-in-hours-for-flash-campaigns)をご覧ください。

<div id="lookback-window-in-onelink" />

### OneLink™のルックバック期間

OneLinkでもルックバック期間を設定できます。

1. <Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template">OneLinkを設定します。</Anchor>
2. <Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#onelinkリンクの作成">カスタム計測リンクを作成します。</Anchor>
3. 「**詳細設定**」で「**ルックバック期間のカスタマイズ**」をオンにし、ルックバック期間を設定します。

</Tab>
</Tabs>

## アプリの初回起動までにかかる時間の分布

以下のグラフは、広告接触からアプリの初回起動までにかかる時間の分布を示しています。

[![](https://files.readme.io/8fdc8b23ba9a1b78bdea7bacad99d6ed5e59d57de32f395cb2fd9e5451483962-360001666918.png)](https://files.readme.io/8fdc8b23ba9a1b78bdea7bacad99d6ed5e59d57de32f395cb2fd9e5451483962-360001666918.png)

このグラフから、ルックバック期間の長さによって、アプリをインストールするユーザー数がどのように変わるかを把握できます。

アプリを起動するユーザーの大多数、97%強は、広告接触から7日以内に起動しています。残りの2%は、7日目からルックバック期間の終了日（30日目）までに起動しています。

実際には、アプリを起動するユーザーの62%近くが広告接触から15分以内、72%が1時間以内に起動しています。

## シナリオと設定例

以下では、ルックバック期間の利用に関するシナリオと設定例を紹介します。

<div id="srn-discrepancy-srn-lookback-longer-than-appsflyer" />

<Accordion title="SRNとのデータの差異：SRNのルックバック期間がAppsFlyerより長い場合">

X Adsでキャンペーンを設定し、クリックスルーのルックバック期間を7日に設定したとします。一方、X Adsのルックバック期間のデフォルト値は14日です。

[![srn-discrepancy-srn-lookback-larger-than-appsflyer.png](https://files.readme.io/a0a60df2c1b142c9b2871c2083168ef5d88922001f1e5ab6a95c7ffbdcc178a5-360001586637.png)](https://files.readme.io/a0a60df2c1b142c9b2871c2083168ef5d88922001f1e5ab6a95c7ffbdcc178a5-360001586637.png)

</Accordion>

<div id="srn-lookback-smaller-than-appsflyer" />

<Accordion title="SRNのルックバック期間がAppsFlyerより短い場合">

X Adsでキャンペーンを設定し、クリックスルーのルックバック期間を28日に設定したとします。一方、X Adsのルックバック期間のデフォルト値は14日です。

[![srn-lookback-smaller-than-appsflyer.png](https://files.readme.io/9111035d903bfb35be2ab4bff27c16e527b401b12225b71316a7e36ed68ffb0c-360001586697.png)](https://files.readme.io/9111035d903bfb35be2ab4bff27c16e527b401b12225b71316a7e36ed68ffb0c-360001586697.png)

</Accordion>

<div id="attribution-link-without-a-lookback-window-parameter" />

<Accordion title="ルックバック期間のパラメータがない計測リンク">

計測リンクに、ルックバック期間のパラメータが含まれていない場合があります。その場合、AppsFlyerはクリックには7日、インプレッションには1日のデフォルトのルックバック期間を適用します。

</Accordion>

<div id="lookback-in-hours-for-flash-campaigns" />

<Accordion title="短期キャンペーンでの時間単位のルックバック期間">

短期キャンペーンは、短いプロモーション期間中に、できるだけ早くアプリをインストールしてもらうことを目的としたキャンペーンです。

SuperShoppingというEコマースアプリが、短期キャンペーンを実施するとします。このキャンペーンでは、1時間以内にアプリをインストールしたユーザーに特典が提供されます。

SuperShoppingのマーケティング責任者であるJohnnyは、計測リンクを作成し、ルックバック期間を1時間に設定します。これにより、Johnnyはキャンペーンに反応したユーザー数を把握できます。

また、アプリの開発者は、この短期キャンペーン経由のユーザーを識別し、キャンペーンで案内している特典を提供できます。

</Accordion>

> 👍 **ヒント**
>
> ルックバック期間やアトリビューションに関するヒントや活用方法を知りたい場合は、短時間で実践的な知識を学べる<Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks">AppsFlyerラーニングポータルのコース</Anchor>をご覧ください。

<div data-zendesk-anchors="lookback-windows=%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01HGFQVP7QZACJ3EGSWEP4HPFV=%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 configurable-lookback-windows-per-attribution-type=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E7%A8%AE%E9%A1%9E%E5%88%A5%E3%81%AB%E8%A8%AD%E5%AE%9A%E3%81%A7%E3%81%8D%E3%82%8B%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01HGFQVP7QM0J507CFQ753YS5X=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E7%A8%AE%E9%A1%9E%E5%88%A5%E3%81%AB%E8%A8%AD%E5%AE%9A%E3%81%A7%E3%81%8D%E3%82%8B%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 probabilistic-modeling-lookback-window=%E7%A2%BA%E7%8E%87%E8%AB%96%E7%9A%84%E3%83%A2%E3%83%87%E3%83%AA%E3%83%B3%E3%82%B0%E3%81%AE%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01JKWV7S7J5B4YA84VGEB478TT=%E7%A2%BA%E7%8E%87%E8%AB%96%E7%9A%84%E3%83%A2%E3%83%87%E3%83%AA%E3%83%B3%E3%82%B0%E3%81%AE%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 lookback-window-setup=%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 h_01HGFQVP7QCCN7CHRCAFSNJVHA=%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 attribution-lookback-window-for-srns=srn%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01HGFQVP7QP61C2K0P7C7YM56Z=srn%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01HGFQVP7QXTQKGVQJEZ0NEW0M=%E9%87%8D%E8%A6%81 h_01HGFQVP7QDBFP85A9DJFZE38S=attribution-lookback-window-with-attribution-links h_01HGFQVP7Q69H5621GXMYZ441N=%E3%83%92%E3%83%B3%E3%83%88-1 lookback-window-in-onelink%E2%84%A2=lookback-window-in-onelink h_01HGFQVP7QSJEE8D7TCWZMSXGK=lookback-window-in-onelink distribution-of-first-app-launches=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E5%88%9D%E5%9B%9E%E8%B5%B7%E5%8B%95%E3%81%BE%E3%81%A7%E3%81%AB%E3%81%8B%E3%81%8B%E3%82%8B%E6%99%82%E9%96%93%E3%81%AE%E5%88%86%E5%B8%83 h_01HGFQVP7Q96827N7Q9Q0363SR=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E5%88%9D%E5%9B%9E%E8%B5%B7%E5%8B%95%E3%81%BE%E3%81%A7%E3%81%AB%E3%81%8B%E3%81%8B%E3%82%8B%E6%99%82%E9%96%93%E3%81%AE%E5%88%86%E5%B8%83 scenarios-and-examples=%E3%82%B7%E3%83%8A%E3%83%AA%E3%82%AA%E3%81%A8%E8%A8%AD%E5%AE%9A%E4%BE%8B h_01HGFQVP7Q02NS8MXF7WKYQ8V1=%E3%82%B7%E3%83%8A%E3%83%AA%E3%82%AA%E3%81%A8%E8%A8%AD%E5%AE%9A%E4%BE%8B h_01HGFQVP7Q1CYRAHAKY3WK8BK0=srn-discrepancy-srn-lookback-longer-than-appsflyer h_01HGFQVP7QAWDP40H89YBN66GV=srn-lookback-smaller-than-appsflyer h_01HGFQVP7QYE3V2DKW7T4171MX=attribution-link-without-a-lookback-window-parameter h_01HGFQVP7Q7CXSK5G8A0937H5Z=lookback-in-hours-for-flash-campaigns h_01HGFQVP7QM3R973QS99661VPG=%E3%83%92%E3%83%B3%E3%83%88-1" />
