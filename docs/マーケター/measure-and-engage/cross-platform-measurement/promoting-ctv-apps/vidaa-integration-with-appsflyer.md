---
title: VidaaとAppsFlyerの連携
metadata:
  keywords:
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2022-11-06T08:13:09Z'
  edited_at: '2026-10-14T09:30:55Z'
  id: 10400222972433
  locale: ja
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/ja/articles/10400222972433
---
> **概要： 概要：Vidaa Connected TV (CTV) アプリにAppsFlyerを実装して、Vidaaのキャンペーンに関するアトリビューションとイベントデータを受取りましょう。**

## Vidaa CTVの計測について

ストリーミング用のVidaa OSは、すべてのVidaa TVで動作します。

マーケターは、これらのインサイトを活用してマーケティング活動を測定および最適化できます。

Vidaa API連携では以下をサポートしています。

* Vidaa Smart TV
* CTV-to-CTVのアトリビューションとイベントの計測：つまり、ユーザーのVidaaデバイスの計測と記録）

## 連携手順

次の表では、Vidaa CTVアプリにAppsFlyerを実装するために必要なタスクを記載しています。進捗状況を記録するために、この<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSFsuk9liZ_z34w3kHMyOFzASh5PBDtdn_HxgMqxAYY0wEt5RxCdrXeyLvteC5Cp-x-6ESwO5YbJ0n-/pub?output=xlsx">スプレッドシート</Anchor>をダウンロードしてください。

| タスク | アクション | 作業担当者 |
| --- | --- | --- |
| アプリ設定 | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">AppsFlyerアカウントを作成</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/user-management">適切な権限を持つアカウントユーザーを追加します。</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer">AppsFlyerにVidaa CTVアプリを追加</Anchor></li></ul> | マーケティング担当者 |
| アプリとAPIの連携（S2SまたはSDK経由） | 以下のイベントをAppsFlyerにレポートするコマンドを使用して、AppsFlyer CTV APIをCTVアプリに実装してください。<ul><li>初回起動</li><li>In-app events</li><li>セッション</li></ul>**注意：**<ul><li>インストールは、アプリ内イベントやセッションの前にレポートする必要があります。</li><li>APIを使用してイベントを送信する必要があります。デベロッパーにどのイベントを送信したいかを伝えてください。 APIを設定する際、AppsFlyerに送信するイベントを設定しマッピングしていることを確認してください。/span></li></ul>オウンドメディアエンゲージメントをレポートするには、 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">インプレッションエンゲージメントAPI</Anchor> を連携してください。 | アプリ開発者 |
| リンクの設定 | 詳細：ダイレクトアトリビューションリンクの作成方法 | マーケティング担当者 |
| レポートの設定 / データの表示 | <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts#データの可用性">詳細：管理画面とレポートでのデータの可用性</Anchor> | マーケター / データエンジニア |

<div id="traits-and-limitations" />

<Accordion title="特性と制限">

| 特性 | 備考 |
| --- | --- |
| 非オーガニックソース | 近日リリース予定 |
| リターゲティング | 現在サポートされていません |
| コストデータ | コストデータは、メールメソッドによるアップロードファイルを使用して、<Anchor target="_blank" href="/marketers/ja/docs/import-cost-data">コストインポート</Anchor>経由で送信する必要があります。 |

</Accordion>

> 📄 **参照：**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts">CTV、PC、コンソールプラットフォームの概要</Anchor>

<div data-zendesk-anchors="about-vidaa-ctv-attribution=vidaa-ctv%E3%81%AE%E8%A8%88%E6%B8%AC%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 01H7Z180QRR77E1GBQ0P0RHVN5=vidaa-ctv%E3%81%AE%E8%A8%88%E6%B8%AC%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 integration-procedures=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 01H7Z180QR6HT4R3N9DYSM8WB9=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 01H7Z180QR0QQ0HK3N5N1G4ENZ=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%E5%8F%82%E7%85%A7" />
