---
title: モバイルWebサイトの訪問者をアプリユーザーへ誘導
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Smart Banner
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2019-03-19T08:54:10Z'
  edited_at: '2026-10-28T09:19:58Z'
  id: 360001237818
  locale: ja
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/ja/articles/360001237818
---
> **概要：** モバイルWebサイトを活用して、訪問者をモバイルアプリの新規ユーザーへとつなげます。

<div id="mobile-web-to-app-attribution-solutions" />

## モバイルWebからアプリへのアトリビューションソリューション

![Web_to_app_.png](https://files.readme.io/deb9ba0dfd18671666e9f06dc27440759844ea365988f80e05ce7ac2817a7299-46646996021777.png)

<div id="benefits-of-web-to-app-campaigns" />

### Web-to-appキャンペーンのメリット

Web-to-appキャンペーンには、次のメリットがあります。

* モバイルWebサイトの訪問者をアプリユーザーへ誘導できます。 [「Web訪問が貢献したインストール」も参照してください。](/docs/convert-your-mobile-web-visitors-to-app-users#web訪問が貢献したインストール)
* アプリのダウンロード前に、Webページやランディングページで製品・サービスへの理解を深めてもらえます。
* コンバージョン率が最も高いWebページやランディングページと、最も低いページを特定できます。
* アプリも利用しているモバイルWebユーザーに対し、より対象を絞ったオファーでリターゲティングできます。
* ディープリンクで、Webサイトからアプリ内の特定のページへスムーズに誘導できます。

<div id="attribution-solutions" />

### アトリビューションソリューション

<Embed title="モバイルWebサイトの訪問者をアプリユーザーへ誘導" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/kv67fa3rvn" providerUrl="https://fast.wistia.com" />

モバイルWebからアプリに移動する経路では、Webページに移動するクリックと、Webページからアプリストアに移動するクリックの2回が発生するため、アトリビューションやディープリンクに課題が生じます。最初のクリックがアドネットワーク、Google、オウンドメディアからのものであっても、最終的にアプリをダウンロードしたユーザーが誤った流入元に紐づいたり、オーガニックとして扱われたりする可能性があります。 

AppsFlyerは、Webからアプリへの成果を正確に紐づけるために、以下のソリューションを提供しています。

<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners</Anchor>：

* WebサイトにSmart BannersのWeb SDKを追加し、AppsFlyerの管理画面で動的なバナーを作成します。
* ユーザーがURLをクリックしてモバイルWebサイトに移動すると、アプリストアからのダウンロードを促すCTA付きのSmart Bannerが表示されます。
* Smart BannerのURLには受信リンクのパラメータやUTMパラメータに基づく値が設定され、アトリビューションに使用されます。

<Anchor target="_blank" href="/marketers/ja/docs/onelink-smart-script-overview">OneLink Smart Script</Anchor>：

* モバイルWebサイト上でスクリプトを実行します。
* ユーザーがURLをクリックしてモバイルWebサイトに移動すると、アプリのダウンロードを促すボタンがあるページに到達します。
* Webページ上のスクリプトは、受信URLに基づき、これらのボタンに設定する送信URLを動的に生成して、アトリビューションに使用します。
* 従来のモバイルランディングページ用アトリビューション<Anchor target="_blank" href="/marketers/ja/docs/deprecated-mobile-landing-page-attribution-script">スクリプト</Anchor>を置き換えるものです。従来のスクリプトを使用している場合は、移行してください。

どちらのソリューションも、Webサイトへの流入に使われたキャンペーンの受信URLと、アプリへの誘導に使うOneLinkの送信URLをつなぎます。これにより、モバイルWebサイトの訪問者の成果を正確に紐づけ、ディープリンクで誘導できます。

以下の比較表を参考に、要件に最も合うソリューションを選び、実装してください。**注意**：両方のソリューションを実装し、併用することもできます。

<div id="smart-banner-vs-onelink-smart-script" />

#### Smart BannersとOneLink Smart Scriptの比較

| 比較項目 | Smart Banners | OneLink Smart Script |
| --- | --- | --- |
| 対応するメディアソース | すべてのメディアソースに対応：<ul><li>pidまたはUTMパラメータを含む受信リンク（SRNを含む）</li><li>オーガニック訪問者</li></ul> | すべてのメディアソースに対応：<ul><li>受信リンク（SRNを含む）</li><li>オーガニック訪問者</li></ul> |
| アトリビューションリンクのパラメータ変更 | AppsFlyerの管理画面やウィザードですばやく変更できます。 | 開発者によるスクリプトへの実装が必要ですが、柔軟に変更できます。 |
| デスクトップユーザー | 非対応 | 対応 |
| マーケターの設定作業 | ウィザードを使用してSmart Bannersを設定します。 | 受信URLと送信URLに設定するパラメータと値を決めます（デフォルト値も用意されています）。 |
| 開発者の設定作業 | <ul><li>Web SDKを実装します。</li><li>代わりに、<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-website-code-implementation-for-marketers">マーケターが実装する</Anchor>こともできます。</li></ul> | <ul><li>送信URLを生成する<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator">スクリプトを実装します</Anchor>。</li><li>代わりに、マーケターが<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#onelink-smart-scriptの設定">タグマネージャー</Anchor>を使って実装することもできます。</li></ul> |
| 運用時のキャンペーン設定 | クリックの計測に対応するアドネットワークでは、Webキャンペーンからアプリへ誘導するリンクを設定します。 | メディアソースの種類に応じた手順に従います。 |
| 利用条件 | 有料のサブスクリプションプランで利用できます。 | 有料のサブスクリプションプランで利用できます。 |

**注意：** Smart BannersとOneLink Smart Scriptは、対象の有料<Anchor target="_blank" href="/marketers/ja/docs/account-management-plans-payments-and-billing#appsflyer-plans">サブスクリプションプラン</Anchor>でのみ利用できます。利用できる機能は、ご契約のAppsFlyerプランによって異なります。

<div id="web-assisted-installs" />

### Web訪問が貢献したインストール

Web訪問が貢献したインストールとは、必ずしも特定のキャンペーンが直接のきっかけではないものの、Webサイトへの訪問後にアプリがダウンロードされたケースを指します。ユーザーはダウンロード前に、何らかの理由でWebサイトを訪問しています。その訪問は数日前、あるいは数週間前の場合もあります。 <Anchor target="_blank" href="/marketers/ja/docs/people-based-attribution-pba-overview">PBA</Anchor>の「Web訪問が貢献したインストール」では、最終的なアプリのインストールに*貢献した*接点の内訳を確認できます。  

<div id="web-to-app-solutions-vs-web-assisted-installs" />

#### Web-to-appソリューションと「Web訪問が貢献したインストール」の比較

| 比較項目 | モバイルWeb-to-appソリューション | Web訪問が貢献したインストール（PBA） |
| --- | --- | --- |
| 目的 | Web訪問者を直接アプリユーザーへ誘導するキャンペーンを実施し、Web訪問につながったメディアソースに成果を紐づけるためのツールを提供します。 | インストール前にWeb訪問があったケースの内訳を確認します。 |
| ユーザーの経路 | Webからアプリのダウンロードへ直接進む経路。 | 直接進む経路、時間を置いて進む経路、連続していない経路。インストールの最大30日前までのWeb訪問を対象にできます。 |
| ユーザーのデバイス | 同一デバイス | 同一デバイスまたは複数のデバイス |

| 項目 | 説明 |
| --- | --- |
| SDKバージョン |  |
| マッチタイプ | `preload_rfr` |
| Overview dashboard | 接触は、集計レポートとダッシュボードでクリックとしてカウントされます。プリロードパートナー（メディアソース）とキャンペーンの単位で集計されます。 |
| ローデータレポート | <ul><li>接触データは、Data Locker経由のクリックレポートでのみ取得できます。</li><li>Samsungのプライバシー制限により、インストールレポートの元のURLにはプリロードイベントが含まれません。</li><li>`af_engagement_type`パラメータの値が`preload`であることで識別できます。</li></ul> |

<div data-zendesk-anchors="mobile-webtoapp-attribution-solutions=%E3%83%A2%E3%83%90%E3%82%A4%E3%83%ABweb%E3%81%8B%E3%82%89%E3%82%A2%E3%83%97%E3%83%AA%E3%81%B8%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%BD%E3%83%AA%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01KFAFC9DFAES0JGPVCQQV3GAR=%E3%83%A2%E3%83%90%E3%82%A4%E3%83%ABweb%E3%81%8B%E3%82%89%E3%82%A2%E3%83%97%E3%83%AA%E3%81%B8%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%BD%E3%83%AA%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 benefits-of-webtoapp-campaigns=web-to-app%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 h_01KFAFC9DFJ7QWJ6JN60NKVPZ3=web-to-app%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 attribution-solutions=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%BD%E3%83%AA%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01KFAFC9DFH4JH6DE4KZE424Q3=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%BD%E3%83%AA%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 smart-banner-vs-onelink-smart-script=smart-banners%E3%81%A8onelink-smart-script%E3%81%AE%E6%AF%94%E8%BC%83 h_01KFAFC9DFGCYRS1C5SVX1ZSCC=smart-banners%E3%81%A8onelink-smart-script%E3%81%AE%E6%AF%94%E8%BC%83 webassisted-installs=web%E8%A8%AA%E5%95%8F%E3%81%8C%E8%B2%A2%E7%8C%AE%E3%81%97%E3%81%9F%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB h_01KFAFC9DG4MCVQ5YRGVRQ6K5P=web%E8%A8%AA%E5%95%8F%E3%81%8C%E8%B2%A2%E7%8C%AE%E3%81%97%E3%81%9F%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB webtoapp-solutions-vs-webassisted-installs=web-to-app%E3%82%BD%E3%83%AA%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%A8web%E8%A8%AA%E5%95%8F%E3%81%8C%E8%B2%A2%E7%8C%AE%E3%81%97%E3%81%9F%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E6%AF%94%E8%BC%83 h_01KFAFC9DG4YJ55BYQH9TQ2YPQ=web-to-app%E3%82%BD%E3%83%AA%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%A8web%E8%A8%AA%E5%95%8F%E3%81%8C%E8%B2%A2%E7%8C%AE%E3%81%97%E3%81%9F%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E6%AF%94%E8%BC%83" />
