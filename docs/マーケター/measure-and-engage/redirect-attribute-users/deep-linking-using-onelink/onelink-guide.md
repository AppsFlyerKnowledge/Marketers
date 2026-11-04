---
title: OneLink｜利用ガイド
metadata:
  keywords:
    - Marketers
    - start
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2017-10-19T08:53:16Z'
  edited_at: '2026-10-28T09:18:36Z'
  id: 115005248543
  locale: ja
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ja/articles/115005248543
---
> **概要：** アトリビューション、リダイレクト、ディープリンクの機能を備えたリンクを作成し、デバイス、OS、チャネル、プラットフォームを問わず、オウンドメディアや有料メディアのユーザーをアプリユーザーに転換します。 Webサイト、バナー、ソーシャルメディアの投稿、メール、テキストメッセージなど、どのオウンドメディアがコンバージョンにつながった場合でも、これらのリンクを使用して最適なユーザー体験を提供できます。

<div id="introduction-video" />

## 紹介動画

<Embed title="OneLink｜利用ガイド" typeOfEmbed="youtube" url="https://www.youtube.com/embed/golT4p9D8MA" providerUrl="https://www.youtube.com" />

<div id="benefits" />

## メリット

AppsFlyerの顧客体験・ディープリンクスイートを支えるOneLinkでは、あらゆる主要チャネルのモバイルマーケティングキャンペーンを計測するリンクを作成できます。作成したリンクでは、次のことが可能です。

* オンラインとオフラインのさまざまな接点で、顧客にアプローチできます。
* どの接点から流入したユーザーにも、クリックからアプリのインストールまで、その状況に合った最適な体験を提供し、コンバージョンを増やせます。
* キャンペーンの成果について、正確なアトリビューションと計測が可能です。
* アプリをインストールしていない新規ユーザーを、デバイス、OS、チャネル、プラットフォームを問わず、適切なアプリストアやWebのURLへ誘導できます。
* アプリをインストール済みの既存ユーザーを、App Links、Universal Links、URIスキームを使用してアプリへ直接誘導できます。
* ディープリンクで、ユーザーを特定のアプリ内ページや体験へ誘導できます。

OneLinkの機能は<Anchor target="_blank" href="/marketers/ja/docs/account-management-plans-payments-and-billing#appsflyer-plans">AppsFlyerのサブスクリプションプラン</Anchor>で利用できます。 OneLinkによるユーザー体験を継続して提供できるよう、プランの契約を有効に保ってください。

<div id="experiences" />

## ユーザー体験

AppsFlyerの顧客体験・ディープリンクスイートを支えるOneLinkでは、ユーザーの流入元を問わず、最適な体験を提供するリンクを作成できます。次のようなユーザー体験を設定できます。

* **Social-to-app**：ソーシャルメディア上でユーザーの関心を引き、フィードからアプリへ誘導します。
* **App-to-app**：他のアプリ内から自社アプリへユーザーを誘導します。
* <Anchor target="_blank" href="/marketers/ja/docs/convert-your-mobile-web-visitors-to-app-users">**Web-to-app**</Anchor>：Smart BannersとSmart Scriptを使用し、モバイルWebサイトの訪問者を新規モバイルアプリユーザーに転換します。
* <Anchor target="_blank" href="/marketers/ja/docs/qr-to-app-conversion">**QR-to-app**</Anchor>：QRコードを活用して、オフラインでの顧客体験の要所でユーザーにコードを読み取ってもらい、アプリのインストールを促進します。また、デスクトップサイトやテレビ・CTV広告にQRコードを掲載して、ユーザーをアプリへ誘導することもできます。
* **Email-to-app**：メール配信サービスプロバイダー（ESP）を利用してメールでユーザーの関心を引き、受信トレイからアプリへ誘導します。
* **Text-to-app**：SMSやメッセージ配信キャンペーン用のリンクを作成し、テキストメッセージを通じてユーザーのエンゲージメントを促進します。
* **Referral-to-app**：ユーザーやインフルエンサーが他のユーザーをアプリに招待したり、記事などの特定のアプリ内コンテンツを共有したりできるユーザー招待リンクを作成します。
* **Custom**：デスクトップ／モバイル、オンライン／オフライン、オウンドメディア／有料メディアを問わず、OneLinkを使って、あらゆる流入元のユーザーを適切な遷移先へ簡単に誘導できます。

<div id="setting-up-onelink" />

## OneLinkの設定

AppsFlyerのUIを使用し、リンクからアプリのインストールまで、意図した顧客体験を提供するには、次の対応が必要です。

* 組織内のマーケターと開発者が連携して作業します。
* すべてのリンクに共通する振り分けルールを定義した<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template">OneLinkテンプレートを作成</Anchor>し、次のようにリダイレクトします。
  * アプリをインストールしていない新規ユーザーを、適切なアプリストアやWebのURLへ誘導します。
  * アプリをインストール済みの既存ユーザーを、Android App Links、iOS Universal Links、URIスキームを使用してアプリへ誘導します。

    * これらが未設定の場合は、アプリをインストールしていない新規ユーザーと同じ設定（WebのURLまたはアプリストア）が適用されます。

    **注意**：OneLinkテンプレートはユーザーが実際にクリックするリンクではなく、多数のカスタムリンクを作成するための土台です。テンプレートをもとに、ユーザーがクリックするOneLinkカスタムリンクを多数作成できます。テスト目的を除けば、アプリの運用期間全体を通じて、OneLinkテンプレートが1～2個を超えて必要になることはほとんどありません。
* <Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLinkリンクを作成</Anchor>します。これは、広告に表示するクリック可能なリンク、または読み取り可能なQRコードです。リンクの設定時に、提供する顧客体験を定義し、必要なパラメータを追加します。

以下の表に、マーケターと開発者の作業内容、および関連資料へのリンクを示します。

| タスク | 詳細 | 関連資料 |
| --- | --- | --- |
| OneLinkテンプレートの作成 | <ul><li>マーケター／プロダクトマネージャーが、AppsFlyerでテンプレートを設定します。</li><li>Android開発者が、既存ユーザー向けにアプリを開く方法（Android App LinksとURIスキーム）を設定します。</li><li>iOS開発者が、既存ユーザー向けにアプリを開く方法（iOS Universal LinksとURIスキーム）を設定します。</li></ul> | <ul><li>AppsFlyer管理画面</li><li><Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template">マーケター向けの手順</Anchor></li><li>開発者向けの手順：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#app-opening-methods">Android</Anchor>／<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup">iOS</Anchor></li></ul> |
| OneLinkリンクの作成 | <ul><li>マーケター／プロダクトマネージャーがAppsFlyerでリンクを設定し、提供する顧客体験の選択や、必要なアトリビューション・ディープリンク用パラメータの追加を行います。</li><li>Android／iOS開発者が、ディープリンク用のUDLメソッドを実装します（ディープリンクが必要な場合）。</li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">マーケター向けの手順</Anchor></li><li>開発者向けの手順：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_unified_deep_linking">Android</Anchor>／<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_unified_deep_linking">iOS</Anchor></li><li>サンプルアプリ（GitHub）</li></ul> |

<div id="additional-options" />

## 追加オプション

UIで設定の一部またはすべてを完了したら、以下の追加機能の導入もご検討ください。

* <Anchor target="_blank" href="/marketers/ja/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor>と<Anchor target="_blank" href="/marketers/ja/docs/perform-onelink-bulk-actions-via-csv">リンクの一括作成</Anchor>：複数のキャンペーンを同時に大規模に展開し、数千ものOneLinkリンクをすばやく簡単に作成できます。時間と手間を節約し、キャンペーンやマーケティング施策に集中できます。
* <Anchor target="_blank" href="/marketers/ja/docs/export-onelink-urls">OneLink URLのエクスポート</Anchor>：AppsFlyerのUIで作成したすべてのOneLink URLをダウンロードします（SDK、OneLink API、一括アップロードで作成したOneLink URLは含まれません）。
* <Anchor target="_blank" href="/marketers/ja/docs/measuring-push-notification-re-engagement-campaigns">プッシュ通知によるリエンゲージメントキャンペーンの計測</Anchor>：OneLinkを使用したプッシュ通知で、モバイルユーザーのリエンゲージメントを計測します。
* <Anchor target="_blank" href="/marketers/ja/docs/cross-promotion-attribution-for-marketers">クロスプロモーションのアトリビューション</Anchor>：既存のアプリユーザーは、自社の別の新しいアプリをインストールしてくれる可能性が高いユーザーです。 SDKのメソッドを使用してクロスプロモーションキャンペーンを簡単に作成し、計測する方法をご確認ください。
* <Anchor target="_blank" href="/marketers/ja/docs/understand-onelink-short-vs-long-urls">ロングURL</Anchor>：OneLinkカスタムリンクにパラメータを追加したり、スプレッドシートで独自の簡単な数式を使用して多数のOneLinkカスタムリンクを生成したりできます。
* <Anchor target="_blank" href="/marketers/ja/docs/redirect-app-users-to-a-website">アプリからWebへのリダイレクト</Anchor>：ユーザーをアプリからWebサイトやソーシャルメディアのページへ誘導します。

<div id="troubleshooting-and-faq" />

## トラブルシューティングとよくある質問

OneLinkカスタムリンクのリダイレクトや動作に関する問題をテスト・デバッグする際は、<Anchor target="_blank" href="/marketers/ja/docs/onelink-troubleshooting-and-faq">OneLinkトラブルシューティングガイド</Anchor>で解決策をすばやく確認できます。

<div id="limitations" />

## 制限事項

* OneLinkはMetaのモバイルアプリのインストール目的に対応していません。この目的で利用できるのはMeta App Linksのみです。
* 有料サブスクリプションプランの契約が失効すると、一部のOneLinkリンクや機能が利用できなくなります。 ESPのリンクやブランドドメインのリンクに影響が生じる可能性があり、SDK・APIによるリンク作成とリクエストが無効になり（別途購入している場合を除く）、Web-to-appとリンクの一括作成も利用できなくなります。

<div data-zendesk-anchors="introduction-video=%E7%B4%B9%E4%BB%8B%E5%8B%95%E7%94%BB h_01HGE1D5JZ4Y603BD55W2P7DPW=%E7%B4%B9%E4%BB%8B%E5%8B%95%E7%94%BB benefits=%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 h_01HGE1D5JZJGY8BZX8ZTSXQ635=%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 experiences=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E4%BD%93%E9%A8%93 h_01HGE1D5JZV65E9YWG424HYRNW=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E4%BD%93%E9%A8%93 setup=onelink%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HGE1D5K0RKHHV9SVH4VREMXQ=onelink%E3%81%AE%E8%A8%AD%E5%AE%9A additional-options=%E8%BF%BD%E5%8A%A0%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3 h_01HGE1D5K2VCKYJY3Y8MKYVT2V=%E8%BF%BD%E5%8A%A0%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3 troubleshooting-and-faq=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%A8%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HGE1D5K24FG3F8G54DYTK599=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%A8%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F limitations=%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HGE1D5K2M0VMJPMP4EJ0QGPY=%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />
