---
title: ［旧方式］オーガニック検索のアトリビューション設定
deprecated: true
metadata:
  keywords:
    - Android
    - organic
    - keyword
    - search
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-28T06:35:08Z'
  edited_at: '2026-10-28T09:07:10Z'
  id: 210195193
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/210195193
---
> **概要：** オーガニック検索の詳細なアトリビューションデータを取得して、オーガニックのコンバージョンを最適化できます。<Anchor target="_blank" href="/marketers/ja/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">新しいオーガニック検索の計測方法を確認する</Anchor>。

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">新しいオーガニック検索の計測方法</Anchor>の導入を推奨します。

## オーガニック検索のアトリビューション

オーガニック検索のアトリビューションは、すでにモバイルアプリをインストールしているユーザーのアプリ起動を、オーガニック検索に紐付けて計測できる革新的なソリューションです。

Webのオーガニック検索を経由してアプリを再利用した既存ユーザーを、この機能で計測できます。

#### 処理の流れ

![Organic_SEO_attribution_flow.png](https://files.readme.io/1772808df9d9e521204153d9f0689b3f9f156dd8c0ab8555673b1d321f28aece-15320495862545.png)

1. ユーザーがモバイルブラウザの検索エンジン（Google、Bingなど）で、検索語句（「メンズシューズ」など）を入力して検索します。検索エンジンに、クリックできる検索結果が複数表示されます。
2. Web開発者が、検索結果の一部をAndroid App LinksやiOSのユニバーサルリンクでモバイルアプリを開くように設定します。アプリをインストール済みのユーザーが検索結果をクリックすると、アプリストアを経由せずにアプリが開きます。
3. アプリの起動時にAppsFlyerが必要な情報を収集し、その起動を設定済みのメディアソース（search\_engineなど）に紐付けて計測します。
4. アプリをインストールしていないユーザーは、Webのランディングページに移動します。そこからSmart Banners、Smart Script、QRコードなどのAppsFlyerのWeb-to-appソリューションを使用して、ユーザーの誘導と計測を行えます。

**アトリビューションの設定手順**：

1. AndroidとiOSのアプリ開発者に、アプリに関連付けられたドメインを共有します。 Androidでは、既存ユーザーがアプリを開くためのAndroid App Linksを設定したドメインです。 iOSでは、既存ユーザーがアプリを開くためのユニバーサルリンクを設定したドメインです。
2. メディアソース（`pid`）パラメータに使用する値を開発者に伝えます。例：search\_engine。
3. 開発者に、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_organic_search_attr">Android</Anchor>および<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_organic_search_attr">iOS</Anchor>のオーガニック検索のアトリビューション手順に従って実装するよう依頼します。  
   オーガニック検索経由のインストールは、指定したメディアソースの値で表示されます。例：search\_engine。

**ヒント**<Anchor target="_blank" href="https://gs.statcounter.com/search-engine-market-share">国・地域別の検索エンジンの利用状況</Anchor>を確認できます。

<div data-zendesk-anchors="organic-search-attribution=%E3%82%AA%E3%83%BC%E3%82%AC%E3%83%8B%E3%83%83%E3%82%AF%E6%A4%9C%E7%B4%A2%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 flow=%E5%87%A6%E7%90%86%E3%81%AE%E6%B5%81%E3%82%8C" />
