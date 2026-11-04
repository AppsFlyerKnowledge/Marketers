---
title: Web Performance Measurementの実装
metadata:
  keywords:
    - Attribution
    - Agencies
    - Web Attribution
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T19:35:31Z'
  edited_at: '2026-10-14T09:22:23Z'
  id: 43529798016401
  locale: ja
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ja/articles/43529798016401
---
> **概要：** このガイドの導入手順に従って、Web Performance Measurementを設定します。設定が完了すると、Webサイトへの訪問やWebイベントをマーケティングソースに紐づけて計測およびアトリビューションできるようになります。これにより、Webサイト上で価値ある成果につながっている要因を把握し、クロスプラットフォーム計測に活用できます。

<div id="about-web-performance-measurement" />

## Web Performance Measurementについて

Web Performance Measurementを使用すると、Webサイト上で発生した訪問やWebイベントと、それらをもたらしたマーケティングソースを紐づけることができます。つまり、どのメディアソースやキャンペーンがユーザーをWebサイトへ誘導し、その後の行動に影響を与えているかを把握できるため、パフォーマンスを計測し、ROIを最適化できます。

<div id="create-a-web-app-in-appsflyer" />

### AppsFlyerでWebアプリを作成する

<Embed title="Web Performance Measurementの実装" typeOfEmbed="youtube" url="https://www.youtube.com/embed/MOn_UsirYCU" providerUrl="https://www.youtube.com" />

<div id="set-up-network-integrations-postbacks-and-cost-measurement" />

### アドネットワーク連携、ポストバック、コスト計測を設定する

<Embed title="Web Performance Measurementの実装" typeOfEmbed="youtube" url="https://www.youtube.com/embed/-sYIv3YQEwo" providerUrl="https://www.youtube.com" />

AppsFlyerでWebサイトへの訪問とWebイベントの計測を開始するには、以下の「Web Performance Measurement設定チェックリスト」に記載されている導入手順に従ってください。

<div id="web-performance-measurement-setup-checklist" />

## Web Performance Measurement設定チェックリスト

以下の表を使用して、AppsFlyerでWebサイトへの訪問とWebイベントの収集を開始するために必要な主要な設定作業、各担当者が行う作業、作業の実施順序を確認してください。

| タスク | 必要な作業 | 詳細情報 | 担当者 |
| --- | --- | --- | --- |
| 1. Webアプリを作成 | 「**アプリ設定**」ページで以下を実施します:<ul><li>**Web SDK ID** をコピーし、開発者に共有する</li><li>レポート用の**タイムゾーン**および**通貨単位**を設定する</li><li>**除外ドメイン**を選択する</li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer#web">Webアプリ設定の構成</Anchor></li></ul> | マーケター |
| 2. （任意）クロスプラットフォームLTV計測用のプロダクトラインを作成する | クロスプラットフォームアトリビューションと、ユーザージャーニー全体にわたる顧客生涯価値（LTV）の計測を有効にするには、プロダクトラインエンティティを作成し、関連するアプリやWebプロパティを紐づけます。または、既存のプロダクトラインにWebアプリを追加します。 | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/product-line-group-apps-for-cross-platform-attribution">プロダクトラインの作成</Anchor></li></ul> | マーケター |
| 3. Web SDKのインストールと設定 | AppsFlyer Web SDK をWebサイトに実装します。 | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/integrate-appsflyer-web-sdk">Web SDKのWebサイト実装</Anchor></li></ul> | 開発者 |
| 4.  S2S API を使用してWebデータを送信する | Server-to-Server（S2S）APIを使用して、Webサイトへの訪問とイベントをサーバーからAppsFlyerへ直接送信します。Web SDKと併用することで計測範囲を広げ、イベントデータを拡充できます。また、完全なサーバーサイド連携として、S2S APIを単独で使用することもできます。 | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/server-to-server-s2s-api-for-web-performance-measurement">Web Performance Measurement向けS2S APIを設定する</Anchor></li></ul> | BIエンジニア |
| 5.Webアプリのアトリビューション設定の構成 | 「**アプリ設定**」ページで、ルックバック期間やユーザー獲得イベントなど、Webアプリのアトリビューション設定を構成します。   <br />**注記：** カスタムユーザー獲得イベントは、Web SDK をWebサイトへ実装した後にのみ選択できます。 | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/configure-web-performance-measurement-settings">Webアプリのアトリビューション設定の構成</Anchor></li></ul> | マーケター |
| 6. Web Performance Measurement用のURLを作成する | 正確かつ詳細なアトリビューション結果を取得するため、適切なアトリビューションパラメーターを使用してURLを作成します。 | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/choose-attribution-parameters-for-landing-page-urls">ランディングページURL用のアトリビューションパラメータの選択</Anchor></li></ul> | マーケター |
| 7. 対応パートナーとの連携を設定する | パートナーを有効化し、パートナーへ送信するポストバックを設定します。<br />サポートしているパートナー：<ul><li>Google広告</li><li>Meta広告</li><li>TikTok広告</li><li>Snapchat広告</li></ul> | 以下のプラットフォームを使用して、Webアプリ向けのWebキャンペーンを作成します。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-create-web-campaigns-for-website-apps">Google広告</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/meta-ads-create-web-campaigns-for-website-apps">Meta広告</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/tiktok-for-business-create-web-campaigns-for-website-apps">TikTok広告</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/snapchat-create-web-campaigns-for-website-apps">Snapchat広告</Anchor></li></ul> | マーケター |
| 8.Web Performance MeasurementデータをData Lockerからエクスポートする | Web Performance Measurementのローデータレポート用に**Data Locker**を設定し、ビジネスインテリジェンス（BI）チームやアナリティクスチームがWeb上のユーザージャーニーを分析できるようにします。 | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/export-web-performance-measurement-report-data-from-data-locker">Web Performance MeasurementデータをData Lockerからエクスポートする</Anchor></li></ul> | マーケター / BIエンジニア |
| 9.クロスプラットフォームダッシュボードでWebデータを確認する | Webセッションとイベントがクロスプラットフォームダッシュボードにどのように表示されるかを確認します。 | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/my-dashboards#クロスプラットフォームダッシュボードでのwebアトリビューション">クロスプラットフォームダッシュボードのWebアトリビューション</Anchor></li></ul> | マーケター |
| 10.Webサイトキャンペーンのコストを計測する<br /><br />**（ROI360のみ）** | **コスト設定**で、Webアプリを対応するセルフレポーティングネットワーク（SRN）のコスト連携に接続します。対応しているSRNは、Google、Meta（Facebook）、Snapchat、TikTokです。  <br />  <br />接続すると、AppsFlyerはWebキャンペーンのコスト、クリック、インプレッションをほぼリアルタイムでCost ETLレポートとマイダッシュボードに反映します。  <br />  <br />**ROI360 Advancedパッケージ**を利用している場合は、Cost ETLの設定ページで、対象となるアプリのリストにWebアプリを追加します。  <br />  <br />**注意：** アトリビューションリンクのランディングページURLには、キャンペーンIDを含める必要があります。 | Webアプリをコスト連携に接続します：<ul><li><Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-create-web-campaigns-for-website-apps#webコストを利用したweb-performance-measurementのデータ分析">Google広告</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/meta-ads-create-web-campaigns-for-website-apps#webのコストデータとアトリビューションデータを組み合わせた計測">Meta広告</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/snapchat-create-web-campaigns-for-website-apps#ウェブコストでウェブ帰属データを測定する">Snapchat広告</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">コストETLの設定</Anchor></li></ul> | マーケター / BIエンジニア |

<div data-zendesk-anchors="about-appsflyer-web-attribution=web-performance-measurement%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KGN43TYPKCQ7H3SRRHHPT387=web-performance-measurement%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 how-to-create-a-web-app-in-appsflyer=appsflyer%E3%81%A7web%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B h_01KVSNN9H462X8DVYBS6TJ8JXQ=appsflyer%E3%81%A7web%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B how-to-set-up-network-integrations-postbacks-and-cost-measurement=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E9%80%A3%E6%90%BA%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%82%B3%E3%82%B9%E3%83%88%E8%A8%88%E6%B8%AC%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01KVSNSSZ7QY090JVWVTRF88ND=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E9%80%A3%E6%90%BA%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%82%B3%E3%82%B9%E3%83%88%E8%A8%88%E6%B8%AC%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B appsflyer-web-attribution-setup-checklist=web-performance-measurement%E8%A8%AD%E5%AE%9A%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%88 h_01KGN43TYP1EV5KFQ37FC4SM0C=web-performance-measurement%E8%A8%AD%E5%AE%9A%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%88" />
