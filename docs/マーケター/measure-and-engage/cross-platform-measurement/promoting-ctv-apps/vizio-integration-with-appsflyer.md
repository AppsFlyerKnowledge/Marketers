---
title: VizioとAppsFlyerの連携
metadata:
  keywords:
    - Developers
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
  created_at: '2022-03-27T15:48:04Z'
  edited_at: '2026-10-14T09:29:46Z'
  id: 5045234293777
  locale: ja
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/ja/articles/5045234293777
---
> **概要： 概要：Vizio コネクテッドTV（CTV）アプリにAppsFlyerを実装し、Vizioキャンペーンについてのアトリビューションとイベントデータを受取りましょう。**

<div id="about-vizio-ctv-attribution" />

## Vizio CTVアトリビューションについて

ストリーミング用のVizio SmartCast OSは、すべてのVizio TVで動作します。

マーケターは、これらのインサイトを活用してマーケティング活動を測定および最適化できます。

Vidaa API連携では以下をサポートしています：

* Vizio Smart TV
* CTV-to-CTVのアトリビューションとイベントの計測：Vizioアプリの初回起動（インストールに相当）のアトリビューションと記録、およびユーザーのVizioデバイスで発生するイベントを意味します。

<div id="vizio-attribution-flow" />

### Vizioアトリビューションフロー

![CTV_attribution_flow_-_Vizio__1_.png](https://files.readme.io/f4ab4b6c9e045fe00b537814fa9f10746b525a5512e5805e62eb0c2e4c9a8615-6318406872337.png)

<div id="integration-procedures" />

## 連携手順

次の表では、Vizio CTVアプリにAppsFlyerを実装するために必要なタスクを記載しています。

| タスク | アクション | 作業担当者 |
| --- | --- | --- |
| アプリ設定 | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">AppsFlyerアカウントを作成</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/user-management">適切な権限を持つアカウントユーザーを追加します。</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer">AppsFlyer管理画面にVizio CTVアプリを追加する</Anchor></li></ul> | マーケティング担当者 |
| アプリとAPIの連携（S2SまたはSDK経由） | 以下のイベントをAppsFlyerにレポートするコマンドを使用して、AppsFlyer CTV APIをCTVアプリに実装してください。<ul><li>初回起動</li><li>In-app events</li><li>セッション</li></ul>**注意：**<ul><li>インストールは、アプリ内イベントやセッションの前にレポートする必要があります。</li><li>APIを使用してイベントを送信する必要があります。デベロッパーにどのイベントを送信したいかを伝えてください。 APIを設定する際、AppsFlyerに送信するイベントを設定しマッピングしていることを確認してください。/span></li></ul>オウンドメディアエンゲージメントをレポートするには、 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">インプレッションエンゲージメントAPI</Anchor> を連携してください。 | アプリ開発者 |
| パートナー連携 | AppsFlyer管理画面でVizioをアドネットワーク（連携済みパートナー）として追加します。<ol><li><Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#a-activate-partner">パートナーの有効化</Anchor></li><li>[オプション] **ビュースルーアトリビューション**をオンにします。</li></ol> | マーケティング担当者 |
| リンクの設定 | <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-direct-attribution-links">詳細：ダイレクトアトリビューションリンクの作成方法</Anchor> | マーケティング担当者 |
| レポートの設定 / データの表示 | <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts#データの可用性">詳細：管理画面とレポートでのデータの可用性</Anchor> | マーケター / データエンジニア |

<div id="traits-and-limitations" />

<Accordion title="特性と制限">

| 特性 | 備考 |
| --- | --- |
| リターゲティング | 現在サポートされていません |
| ビュースルーアトリビューション | デフォルト：24時間 |
| コストデータ | コストデータは、メールメソッドによるアップロードファイルを使用して、<Anchor target="_blank" href="/marketers/ja/docs/import-cost-data">コストインポート</Anchor>経由で送信する必要があります。 |

</Accordion>

<div id="see-also" />

> 📄 **参照：**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts">CTV、PC、コンソールプラットフォームの概要</Anchor>

<div data-zendesk-anchors="about-vizio-ctv-attribution=vizio-ctv%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 01H7Z16QWWCPR309JDKV7H0469=vizio-ctv%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 vizio-attribution-flow=vizio%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%95%E3%83%AD%E3%83%BC 01H7Z16QWW3GJEAGV0F3JHTKE1=vizio%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%95%E3%83%AD%E3%83%BC integration-procedures=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 01H7Z16QWW1WX5F947WPH9HBQX=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 01H7Z16QWX24K8QCEJVBX1SQEA=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%E5%8F%82%E7%85%A7" />
