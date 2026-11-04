---
title: PC版Google PlayゲームとAppsFlyerとの連携
metadata:
  keywords:
    - Marketers
    - cross-platform
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-09-05T13:06:17Z'
  edited_at: '2026-10-14T09:25:29Z'
  id: 18315431772817
  locale: ja
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/ja/articles/18315431772817
---
> **概要：** PCまたはAndroidのGoogle PlayゲームやアプリをAppsFlyerと連携し、これらのアプリマーケティングを行うキャンペーンのパフォーマンスを計測します。

<div id="about-google-play-games-for-pc-attribution" />

## PC版Google Playゲームのアトリビューション

Google Play Gamesは、Windowsのデスクトップやラップトップ上でAndroidモバイルゲームを閲覧、ダウンロード、プレイできるPC用アプリケーションです。Google Play GamesはWindows PCデバイスで動作します。

Google Playゲーム上で動作するアプリは、他のAndroidアプリと同じです。これらは基本的に、PCで利用可能なモバイルAndroidゲームになります。また、他のモバイルAndroidアプリと同様に、AppsFlyer Android SDKを使用してAppsFlyerとすぐに統合することができ、どのソースやキャンペーンがアプリのオープンやアプリ内イベントをうながすかについて、アトリビューションデータやパフォーマンス測定を 受け取ることができます。マーケターは、これらのインサイトを活用してマーケティング活動を測定および最適化できます。

AppsFlyerは、Google Play Games上で動作するアプリに対しても、モバイルAndroidアプリと同じアトリビューションフローを使用します。

<div id="integration-procedures" />

## 連携手順

次の表は、Google PlayゲームアプリとAppsFlyerを連携するために必要なタスクの一覧です。

| タスク | アクション | 作業担当者 |
| --- | --- | --- |
| アプリ設定 | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">AppsFlyerアカウントを作成</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/user-management">適切な権限を持つアカウントユーザーを追加します。</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer">AndroidアプリをAppsFlyerに追加する</Anchor></li></ul> | マーケティング担当者 |
| アプリにAPIを実装 | AppsFlyer <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk">Android SDK</Anchor>を実装します。 | アプリ開発者 |
| クロスプラットフォームのランディングページ設定 | **推奨：**  AppsFlyer Smart Scriptを実行するクロスプラットフォームのランディングページでは、ウェブからアプリへのアトリビューションを実行できます。EpicやSteamのような、他のプラットフォームでも利用可能なアプリをキャンペーンで宣伝する場合に最もおすすめです。<br /><br /><Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">詳細：クロスプラットフォームのランディングページについて</Anchor><br /><br /><Anchor target="_blank" href="/marketers/ja/docs/cross-platform-landing-pages-with-smart-script">詳細：クロスプラットフォームのランディングページの設定方法</Anchor> | マーケター（開発者の支援が必要な場合があります） |
| リンクの設定 | クロスプラットフォームのランディングページを使用しない場合は、ダイレクト計測リンクを作成し、広告からの遷移先URLとして入稿できます。Google Play Games アプリのマーケティング キャンペーンでは、モバイルアプリの AppsFlyerで作成された計測リンクと同様のリンクが使用されます。<br /><br /><Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">リンクの作り方を学ぶ</Anchor> | マーケター |
| レポートの設定 / データの表示 | Google Play ゲームアプリ向けAppsFlyerのダッシュボードとレポートは、モバイルアプリのダッシュボードとレポートに似ています。<br /><br /><Anchor target="_blank" href="/marketers/ja/docs/analyze-your-data">AppsFlyerのダッシュボードとレポートの詳細はこちら</Anchor> | マーケター / データエンジニア |

<div id="see-also" />

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts">CTV、PC、コンソールプラットフォームのコンセプト</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/google-ads-web-integration-for-pc-and-console-apps">PCアプリおよびコンソールアプリ向け：Google Adsウェブキャンペーンの連携設定ガイド</Anchor>

<div data-zendesk-anchors="about-steam-attribution=pc%E7%89%88google-play%E3%82%B2%E3%83%BC%E3%83%A0%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 01H7Z1DJRW1KPJQ4CZ6T85ASRK=pc%E7%89%88google-play%E3%82%B2%E3%83%BC%E3%83%A0%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 integration-procedures=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 01H7Z1DJRWX54DN2SNS21GPGXB=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 h_01HDP2XBSEJVQ5G0MD0V5R05CM=%E5%8F%82%E7%85%A7" />
