---
title: コンバージョン率について
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
  created_at: '2017-02-01T09:59:23Z'
  edited_at: '2026-10-28T09:07:15Z'
  id: 115000610363
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/115000610363
---
> **概要：** AppsFlyerでコンバージョン率に関するKPIを確認し、マーケティングファネルの各段階の強みと課題を把握できます。

## マーケティングファネルの各段階

新規ユーザーは、最初の広告閲覧から収益の発生に至るまで、マーケティングファネルの各段階を進みます。各段階で、次の段階に進む割合は異なります。ユーザーが先の段階まで進むほど、モバイル広告主にとっての成果が高まります。マーケティングファネルの各段階を以下の図に示します。

![ua_funnel_2_en-us.png](https://files.readme.io/3275b1abdc29dc2fccb32024b9243f11c71c947bb591f57356598e63d6a7b32e-360008715658.png)

## マーケティングファネルの各段階とコンバージョン率

コンバージョン率を確認することで、広告主はマーケティングファネルの各段階の強みと課題を把握できます。その結果に基づいて、**課題のある部分を改善し、より多くのユーザーをファネルの次の段階へ進めることができます。**

以下の表で、次の内容を確認できます。

* マーケティングファネルの各段階とコンバージョン率の説明
* 指標を確認できる場所。以下の表記で示しています。
  * **AppsFlyer**：Overview dashboard、<Anchor target="_blank" href="/marketers/ja/docs/aggregated-and-analytics-reporting-overview">集計レポートと分析</Anchor>
  * **アプリストア**：データはアプリストアでのみ確認可能
* 指標を活用してマーケティング成果を改善する方法

#### マーケティングファネルの各段階とコンバージョン率

| 段階 | 名称 | 説明 | 確認できる場所 | コンバージョン率の最適化方法 |
| --- | --- | --- | --- | --- |
| 1 | インプレッション | ユーザーがWeb広告またはモバイル広告を閲覧します。 | AppsFlyer |  |
| 2 | クリック | <ul><li>ユーザーが広告をクリックし、広告対象のページやアプリ内画面に移動します。</li><li>または、広告をクリックせずにアプリのストアページを訪れます。</li></ul> | AppsFlyer |  |
| コンバージョン率 | **クリック率＝（クリック数÷インプレッション数）×100** | <ul><li>広告を見た後にクリックしたユーザーの割合を計測します。</li><li>AppsFlyerのインプレッション数とクリック数の指標を使用して算出します。</li></ul> |  | <ul><li>ビジュアル、広告文、ローカライズ、ターゲティングを見直し、クリエイティブとターゲットオーディエンスの相性を改善します。</li><li>新しいオーディエンスやメディアソースを試します。</li></ul> |
| 3 | アプリストア | ユーザーがアプリストアのアプリページにアクセスします。 | アプリストア |  |
| コンバージョン率 | **クリックからストア訪問への転換率＝（アプリストア訪問数÷クリック数）×100** | 広告をクリックした後、アプリストアのアプリページの読み込みが完了するまで待ったユーザーの割合を計測します。 | アプリストア | アプリストアのページ読み込み時間を短縮します。 読み込みを遅くする大きな要素を削除します。 |
| 4 | ダウンロード | ユーザーがアプリストアからアプリをダウンロードします。 | アプリストア |  |
| コンバージョン率 | **ストア訪問からダウンロードへの転換率＝（ダウンロード数÷アプリストア訪問数）×100** | アプリストアのアプリページを訪れた後、アプリをダウンロードしたユーザーの割合を計測します。 | アプリストア | <ul><li>アプリストアのページに掲載する訴求内容を改善します。</li><li>行動を促す文言（CTA）を変えて試します。</li></ul> |
| 5 | インストール | ユーザーがデバイスにアプリをインストールして起動します。<ul><li>インストール数はダウンロード数より約10％少なくなります。</li><li>例：AppsFlyerにキャンペーンのインストール数が200件と表示されている場合、ダウンロードしたユーザーは約220人です。</li></ul> | AppsFlyer |  |
| コンバージョン率 | **クリックからインストールへの転換率＝（インストール数÷クリック数）×100** | 広告をクリックした後、アプリをインストールしたユーザーの割合を計測します。 | AppsFlyer | <ul><li>オーディエンスのターゲティングを改善します。</li><li>アプリのインストール時間を短縮します。</li></ul> |
| 6 | アプリ内イベント | ユーザーが、購入などのアプリ内アクションを実行します。 | AppsFlyer |  |
| コンバージョン率 | **イベントコンバージョン率（イベントCVR）**<br /><br />**（アプリ内イベント数÷インストール数）×100** | <ul><li>インストール後にアプリ内イベントを実行したユーザーの割合を計測します。<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-knowledge-base-glossary#イベントcvr">［関連記事］</Anchor></li><li>例：会員登録、購入、レベルクリアなど。</li><li>アクション単価（CPA）の算出に使用できます。</li></ul> | AppsFlyer | <ul><li>適切なタイミングでメッセージや行動を促す文言（CTA）を表示します。</li><li>ユーザーインターフェースを改善します。</li><li>ディープリンクを使用したリターゲティングキャンペーンを実施します。 <Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">［関連記事］</Anchor></li></ul> |

> 📄 **関連情報**
>
> * <Anchor target="_blank" href="https://www.appsflyer.com/blog/measurement-analytics/mobile-app-metrics/">アプリマーケティングのKPIの基礎知識</Anchor>

<div data-zendesk-anchors="marketing-funnel-stages=%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%95%E3%82%A1%E3%83%8D%E3%83%AB%E3%81%AE%E5%90%84%E6%AE%B5%E9%9A%8E h_01HE0CXZY2STAERN0SYZJ2QY4K=%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%95%E3%82%A1%E3%83%8D%E3%83%AB%E3%81%AE%E5%90%84%E6%AE%B5%E9%9A%8E marketing-funnel-stages-and-conversion-rates=%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%95%E3%82%A1%E3%83%8D%E3%83%AB%E3%81%AE%E5%90%84%E6%AE%B5%E9%9A%8E%E3%81%A8%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E7%8E%87 h_01HE0CXZY2PZH6WAEEZFNFVT45=%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%95%E3%82%A1%E3%83%8D%E3%83%AB%E3%81%AE%E5%90%84%E6%AE%B5%E9%9A%8E%E3%81%A8%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E7%8E%87 marketing-funnel-stages-and-conversion-rates::74b1530a=%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%95%E3%82%A1%E3%83%8D%E3%83%AB%E3%81%AE%E5%90%84%E6%AE%B5%E9%9A%8E%E3%81%A8%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E7%8E%87-1 h_01HE0CXZY24CB2YHT4ZQEKQAXX=%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%95%E3%82%A1%E3%83%8D%E3%83%AB%E3%81%AE%E5%90%84%E6%AE%B5%E9%9A%8E%E3%81%A8%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E7%8E%87-1 h_01HE0CYPNSBRP4JYZV4NDV2HX8=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />
