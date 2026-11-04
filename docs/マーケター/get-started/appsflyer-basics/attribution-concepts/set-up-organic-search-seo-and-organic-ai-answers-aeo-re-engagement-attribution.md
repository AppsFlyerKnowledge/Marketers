---
title: オーガニック検索（SEO）・AI回答（AEO）経由のリエンゲージメント計測の設定
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
  created_at: '2023-05-07T13:34:36Z'
  edited_at: '2026-10-28T09:08:10Z'
  id: 15123194526353
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/15123194526353
---
> **At a glance:** オーガニック検索エンジンやAI回答エンジン経由のリエンゲージメント（アプリをインストール済みのユーザーによるアプリの起動）の詳細なアトリビューションデータを取得し、オーガニック検索やAI経由のコンバージョンを最適化できます。

<div id="overview" />

## 概要

オーガニック検索（SEO）・AI回答（AEO）経由のリエンゲージメント計測は、アプリをインストール済みのユーザーによるモバイルアプリの起動を、流入元の検索エンジンやAI回答エンジンに紐付けて計測するソリューションです。AppsFlyerのお客様が利用できます。

この独自のデータは、SEO（検索エンジン最適化）やAEO（回答エンジン最適化）の担当チームが、施策の効果を把握するうえで非常に役立ちます。

<div id="flow" />

### 計測の流れ

![オーガニック検索の計測フローを示す図。ユーザーが検索結果をクリックしてから、アプリが起動するか、Webページに遷移するまでの流れを示しています。](https://files.readme.io/4b33060cfa30a4e2786c4a3a213ca41223ae276d63c97ab7c2cb5a997a4b010c-16540659217809.png)

オーガニック検索の計測は、以下の流れで行われます。

1. ユーザーがモバイルブラウザの検索エンジン（GoogleやBingなど）でキーワードを検索します。検索エンジンに、クリック可能な検索結果が表示されます。
2. Web開発者は、Android App LinksとiOSのユニバーサルリンクを使用して、一部の検索結果からモバイルアプリを起動するよう設定します。アプリをインストール済みのユーザーが検索結果をクリックすると、アプリストアを経由せずにアプリが起動します。
3. アプリ起動時にAppsFlyerが必要な情報を収集し、その起動を、ユーザーが利用した検索エンジンの成果として計測できます。
4. アプリをインストールしていないユーザーは、Webのランディングページに移動します。そこでSmart Banners、Smart Script、QRコードなどのAppsFlyerのWeb-to-Appソリューションを使い、ユーザーの誘導と計測を行えます。

<div id="setup" />

## 設定方法

**前提条件**：

* AppsFlyer Android SDK V6.12.1
* AppsFlyer iOS SDK V6.12.1

**オーガニック検索の計測を設定するには、以下の手順に従います**。

1. 開発者に、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#app-opening-methods">Android App Links</Anchor>と<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#app-opening-methods">iOSのユニバーサルリンク</Anchor>の手順に従い、アプリのトップレベルドメインを使用してアプリの起動を有効にするよう依頼します。
2. AppsFlyerのサイドメニューで、**設定**＞<Anchor target="_blank" href="/marketers/ja/docs/app-settings">アプリ設定</Anchor>を選択し、以下をオンにします。
   * **SEO（オーガニック検索）とAEOのモバイルアプリリエンゲージメント計測。**
   * **リエンゲージメント計測**。

> 📘 **Note**
>
> **開発者向けの注意事項**
>
> performOnDeepLinkingは、呼び出されるとディープリンクURLを強制的に処理し、解決します。この処理によってSEO計測機能が正常に動作しなくなり、正しいSEOメディアソースへのアトリビューションがレポートされなくなります。

<div id="data-availability" />

## 取得できるデータ

以下のデータを取得できます。

* ダッシュボードやレポートの集計データでは、`media_source`フィールドに、ユーザーの流入元の検索エンジンが表示されます。例：`google_organic_seo`。
* ローデータレポートでは、以下の情報を確認できます。
  * `media_source`フィールドには、ユーザーの流入元の検索エンジンが表示されます。例：`google_organic_seo`。
  * `http_referrer`フィールドには、ユーザーがアプリやモバイル向けランディングページに遷移する前の検索結果ページのベースURLが含まれます。
  * `channel`フィールドの値は、オーガニック検索エンジン経由のトラフィックでは`seo`、AI回答エンジン経由のトラフィックでは`aeo`です。

<div id="additional-information" />

## 補足情報

<Accordion title="対応している検索エンジン一覧">

オーガニック検索の計測は、以下の検索エンジンに対応しています。

* Google
* Bing
* Yahoo
* Ask
* DuckDuckGo
* Yandex
* Naver
* Daum
* Baidu
* Ecosia
* Coccoc
* Sogou
* Yahoo Japan

> 📘 **Note**
>
> その他の検索エンジンについては、従来のオーガニック検索計測ソリューションを使用してください（開発者による対応が必要です）。
>
> ダッシュボードやデータレポートでは、検索エンジンが`<search engine>`\_organic\_seoの形式で表示されます。例：google\_organic\_seo。

</Accordion>

<Accordion title="対応しているAI回答エンジン一覧">

オーガニック検索の計測は、以下のAI回答エンジンにも対応しています。

* ChatGPT
* Claude
* Perplexity
* Manus
* Copilot
* Gemini
* Grok
* Deepseek

> 📘 **Note**
>
> ダッシュボードやデータレポートでは、AI回答エンジンが`<AI engine>`\_organic\_aeoの形式で表示されます。例：chatgpt\_organic\_aeo。

</Accordion>

<Accordion title="よくある質問">

<Accordion title="オーガニック検索（SEO）の計測には追加料金がかかりますか？">

いいえ。この機能はご契約プランに含まれています。

</Accordion>

<Accordion title="オーガニック検索（SEO）のコンバージョンも、契約プランの計測件数に含まれますか？">

はい。ノンオーガニックのコンバージョンと同様に含まれます。

</Accordion>

<Accordion title="SEOメディアソースの名前をカスタマイズできますか？">

いいえ。オーガニック検索（SEO）のメディアソース名はAppsFlyerが設定しており、現時点ではカスタマイズできません。

</Accordion>

<Accordion title="検索エンジンのオーガニック検索結果の横にあるインストールボタンから、ユーザーがアプリストアに移動した場合、そのインストールは検索エンジンの成果として計測されますか？">

いいえ。この場合、AppsFlyerはアトリビューションに必要な情報を収集できません。オーガニック検索の計測には、アプリがすでにインストールされている必要があります。

</Accordion>

<Accordion title="キーワードデータを取得できますか？">

このオーガニック検索計測ソリューションでは、キーワードデータを取得できません。ただし、Androidでは、まれにキーワードデータを取得できる場合があります。 <Anchor target="_blank" href="/marketers/ja/docs/evaluate-keyword-data#androidのキーワード">Androidのキーワードデータの取得条件</Anchor>をご覧ください。

</Accordion>

<Accordion title="インストールのフローでも、オーガニック検索の計測に対応していますか？">

はい。アプリをインストールしたユーザーが、どのページから自社のWebサイトに流入したかを確認できます。

Smart Scriptは、以下の方法でこの情報を取得します。

* Webリファラと呼ばれる、流入元ページのURLのドメインを収集します。
* ユーザーの具体的な流入元に基づいて、適切な`pid`を作成します（後でメディアソースとして表示されます）。
* 送信URL内の`af_sub1`など、任意のパラメータキーに設定します。

Webリファラを収集するためのSmart Scriptの設定方法は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#seo-referrer-mapping">OneLink Smart Script V2設定ガイド</Anchor>をご覧ください。

</Accordion>

</Accordion>

<Accordion title="仕様と制限事項">

| 項目 | 説明 |
| --- | --- |
| ブラウザ | オーガニック検索の計測は、以下のブラウザには対応していません。<ul><li>AndroidのFirefox</li><li>iOSのSafari以外のすべてのブラウザ。</li></ul> |
| SwiftUIアプリ（iOS） | SwiftUIで開発されたiOSアプリでは、オーガニック検索の計測に対応していません。 |
| リエンゲージメント期間 | オーガニック検索のリエンゲージメント期間は、30日で固定されています。期間の長さは変更できません。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide#計測期間">リターゲティング計測ガイド</Anchor>をご覧ください。 |

</Accordion>

<div data-zendesk-anchors="organic-search-attribution=%E6%A6%82%E8%A6%81 h_01H9G0W21SRDC6ZSR1E8AQFZFC=%E6%A6%82%E8%A6%81 flow=%E8%A8%88%E6%B8%AC%E3%81%AE%E6%B5%81%E3%82%8C h_01H9G0W21S4RB56PNV9DAYZPB2=%E8%A8%88%E6%B8%AC%E3%81%AE%E6%B5%81%E3%82%8C setup=%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 h_01H9G0W21S6Z0A5QXC52KSYVQS=%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 data-availability=%E5%8F%96%E5%BE%97%E3%81%A7%E3%81%8D%E3%82%8B%E3%83%87%E3%83%BC%E3%82%BF h_01H9G0W21S7KVJ2Z5DRPCHZF4Z=%E5%8F%96%E5%BE%97%E3%81%A7%E3%81%8D%E3%82%8B%E3%83%87%E3%83%BC%E3%82%BF additional-information=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 h_01H9G0W21SERW2HC44KD77FNCG=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1" />
