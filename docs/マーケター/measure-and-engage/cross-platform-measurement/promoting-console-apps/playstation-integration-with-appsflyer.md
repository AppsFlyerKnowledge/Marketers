---
title: AppsFlyerでのPlayStation連携・計測ガイド
metadata:
  keywords:
    - CTV
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2022-11-03T15:12:14Z'
  edited_at: '2026-10-14T09:33:38Z'
  id: 10342860530961
  locale: ja
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/ja/articles/10342860530961
---
> **概要： 概要 ：AppsFlyerにご自身のPlayStationアプリを追加し、PlayStation上のキャンペーンの計測とイベントデータを取得しましょう。**

## PlayStationのアトリビューション計測について

コンソールおよびCTVアプリ用のPlayStation OSは、すべてのPlayStationで動作します。

PC上で稼働するアプリは、S2S APIまたはSDKを介してAppsFlyerと連携し、どのソースやキャンペーンがアプリ起動イベントやアプリ内イベントを促進したかに関するアトリビューションデータやパフォーマンス測定値を受け取ることができます。マーケターは、これらのインサイトを活用してマーケティング活動を測定および最適化できます。

PlayStation APIの連携は以下をサポートします：

* PlayStation
* PlayStationアプリのアトリビューションとイベントの計測（ユーザーのPlayStation端末の計測と記録）

### アトリビューションフローの例

**注意**：

![User_windows.jpg](https://files.readme.io/33c9138ef2064832a0bd5d08d52c84bea3e70efb674af362a8ef0d3e5d505db1-small-16332549715217.jpg)

1. <span id="marketing-touchpoint"></span>マーケティングタッチポイント
2. ゲームのランディングページこの手順は、UTM およびその他の URLパラメータを収集して、クリック / インストールしたユーザーを元のメディアソースまたはオウンドメディアソースに結び付けるために重要です。  
   たとえば、ランディングページにXbox、マイクロソフトストア、およびSteamページへのリンクを含めることができます。
4. ゲームのインストールゲームのインストール： ユーザーがゲームをインストールし、アトリビューションをトリガーし、アプリ内イベントとセッションを記録します。

## 連携手順

次の表に、PlayStationアプリをAppsFlyerと連携するために必要なタスクを記載しています。

| タスク | アクション | 作業担当者 |
| --- | --- | --- |
| アプリ設定 | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">AppsFlyerアカウントを作成</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/user-management">適切な権限を持つアカウントユーザーを追加します。</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer">AppsFlyerの管理画面にPlayStationアプリを追加する</Anchor></li></ul> | マーケティング担当者 |
| アプリとAPIの連携（S2SまたはSDK経由） | AppsFlyerへ以下のイベントをレポートするコマンドを使用して、AppsFlyer Epic APIをアプリに実装してください。<ul><li>初回起動</li><li>In-app events</li><li>セッション</li></ul>**注意**：<ul><li>アプリの初回起動は、アプリ内イベントやセッションの前にレポートする必要があります。</li><li>`custom`初回起動custom時に生成される<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">custom</Anchor> IDは、 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">アプリ内イベント</Anchor>と <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">セッション</Anchor>計測時のIDと一致させる必要があります。<ul><li>APIを使用してイベントを送信する必要があります。デベロッパーにどのイベントを送信したいかを伝えてください。 APIを設定する際、AppsFlyerに送信するイベントを設定しマッピングしていることを確認してください。/span></li></ul></li></ul>オウンドメディアエンゲージメントをレポートするには、 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">インプレッションエンゲージメントAPI</Anchor> を連携してください。 | アプリ開発者 |
| クロスプラットフォームのランディングページ設定 | **推奨：**  AppsFlyer Smart Scriptを実行するクロスプラットフォームのランディングページでは、ウェブからアプリへのアトリビューションを実行できます。EpicやSteamのような、他のプラットフォームでも利用可能なアプリをキャンペーンで宣伝する場合に最もおすすめです。<br /><br /><Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">詳細：クロスプラットフォームのランディングページについて</Anchor><br /><br /><Anchor target="_blank" href="/marketers/ja/docs/cross-platform-landing-pages-with-smart-script">詳細：クロスプラットフォームのランディングページの設定方法</Anchor><br /><br />**注意**：<ul><li>**app-id**</li><li>**media\_source**</li></ul>次のパラメーターは必須ではありませんが、推奨です：<ul><li>**campaign**</li><li>**ad**</li><li>**ad\_set**</li></ul> | マーケター（開発者の支援が必要な場合があります） |
| リンクの設定 | クロスプラットフォームのランディングページを使用しない場合は、ダイレクト計測リンクを作成し、広告からの遷移先URLとして入稿できます。<br /><br /><Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-direct-attribution-links">詳細：ダイレクトアトリビューションリンクの作成方法</Anchor> | マーケティング担当者 |
| レポートの設定 / データの表示 | <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts#データの可用性">詳細：管理画面とレポートでのデータの可用性</Anchor> | マーケター / データエンジニア |

<div id="traits-and-limitations" />

<Accordion title="特性と制限">

| 特性 | 備考 |
| --- | --- |
| リターゲティング | 現在サポートされていません |
| コストデータ | コスト（広告費）データは、メールによるアップロードファイルを使用して、<Anchor target="_blank" href="/marketers/ja/docs/import-cost-data">広告費用の取り込み</Anchor>で送信する必要があります。 |

</Accordion>

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts">CTV、PC、コンソールプラットフォームの概要</Anchor>

<div data-zendesk-anchors="about-playstation-attribution=playstation%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 01H7Z1HPD0AB0VP6REMBF2HCR8=playstation%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 example-attribution-flow=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%95%E3%83%AD%E3%83%BC%E3%81%AE%E4%BE%8B h_01HP1Q8B11P0Q8F2Z2FRDSPNDE=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%95%E3%83%AD%E3%83%BC%E3%81%AE%E4%BE%8B 01H7Z19FJ54WZ7XV91Y36EKYQ6=marketing-touchpoint integration-procedures=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 01H7Z1HPD0VAMPEHBPN8MAT3ST=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 01H7Z1HPD0CS7CTX2KS2RVD3VA=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%E5%8F%82%E7%85%A7" />
