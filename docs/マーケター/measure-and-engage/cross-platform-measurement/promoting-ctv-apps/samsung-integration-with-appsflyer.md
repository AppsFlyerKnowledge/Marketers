---
title: Samsung連携ガイド
metadata:
  keywords:
    - Advertisers
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
  created_at: '2022-05-03T09:19:48Z'
  edited_at: '2026-10-14T09:21:29Z'
  id: 5860544738065
  locale: ja
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/ja/articles/5860544738065
---
> **概要： 概要：SamsungコネクテッドTV（CTV）アプリにAppsFlyerを実装し、Samsungキャンペーンにおけるアトリビューションとイベントデータを受取りましょう。**

<div id="about-samsung-ctv-attribution" />

## Samsung CTVアトリビューションについて

ストリーミング用のSamsung Tizen OSは、すべてのSamsung TVで動作します。

マーケティング施策の効果を測定し最適化するためのインサイトを取得しましょう。

Samsung API連携は以下をサポートしています：

* Samsung Smart TV
* CTV-to-CTVのアトリビューションとイベントの計測：（ユーザーのSamsung端末の計測と記録）

<div id="samsung-attribution-flow" />

### Samsungアトリビューションフロー

![CTV_attribution_flow_-_Samsung__1_.png](https://files.readme.io/a1031878e8aced81da5762d06ae0163770cd73b9a7c91224ea7665aa142d2ce8-7215151128209.png)

<div id="integration-procedures" />

## 実装の手順

次の表では、CTVアプリにAppsFlyerを実装するために必要なタスクを記載しています。

| タスク | アクション | 作業担当者 |
| --- | --- | --- |
| アプリ設定 | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">AppsFlyerアカウントの作成</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/user-management">適切なアクセス権限を持つアカウントユーザーを追加する</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer">AppsFlyer管理画面にSamsung CTVアプリを追加する</Anchor></li></ul> | マーケティング担当者 |
| アプリとAPIの連携（S2SまたはSDK経由） | 連携には、次の2つの方法があります：S2S および SDK<br /><br /><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">S2Sメソッドの場合、</Anchor>以下のイベントを AppsFlyer にレポートするコマンドを使用して、AppsFlyer APIをアプリに連携します。<ul><li>初回起動</li><li>アプリ内イベント</li><li>セッション</li></ul>**注：**<ul><li>インストールは、アプリ内イベントやセッションの前にレポートする必要があります。</li><li>APIを使用してイベントを送信する必要があります。開発担当者にどのイベントを送信したいかを伝えてください。 APIを設定する際、AppsFlyerに送信するイベントを設定しマッピングしていることを確認してください。</li></ul>オウンドメディア接触を計測するには、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">インプレッションエンゲージメントAPI</Anchor>を実装してください。 | アプリ開発者 |
| パートナー連携 | AppsFlyerでSamsungをアドネットワーク（連携済みパートナー）として追加します。<ol><li><Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#a-activate-partner">パートナーの有効化</Anchor></li><li>[オプション] <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#e-install-attribution">ビュースルーアトリビューション</Anchor>をオンにします。</li></ol> | マーケティング担当者 |
| リンクの設定 | <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-direct-attribution-links">詳細：ダイレクト計億リンクの作成方法</Anchor> | マーケティング担当者 |
| レポートの設定 / データの表示 | <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts#データの可用性">詳細：管理画面とレポートでのデータの可用性</Anchor> | マーケター / データエンジニア |

<div id="traits-and-limitations" />

<Accordion title="特性と制限">

| 特性 | 備考 |
| --- | --- |
| リターゲティング | 現在サポートされていません |
| コストデータ | <Anchor target="_blank" href="/marketers/ja/docs/import-cost-data">コストデータは、メールメソッドによるアップロードファイルを使用して、</Anchor>コストインポート経由で送信する必要があります。 |
| 展開地域 |  |

</Accordion>

> 📄 **参照：**
>
> <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts">CTV、PC、コンソールプラットフォームの概要</Anchor>

<div data-zendesk-anchors="about-samsung-ctv-attribution=samsung-ctv%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 01H7Z17A1QPJQH9R5MRBVTMG37=samsung-ctv%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 samsung-attribution-flow=samsung%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%95%E3%83%AD%E3%83%BC 01H7Z17A1Q03CEJT848FRFHDPQ=samsung%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%95%E3%83%AD%E3%83%BC integration-procedures=%E5%AE%9F%E8%A3%85%E3%81%AE%E6%89%8B%E9%A0%86 01H7Z17A1QQN4FYJXZFS5FP2NY=%E5%AE%9F%E8%A3%85%E3%81%AE%E6%89%8B%E9%A0%86 01H7Z17A1QVW58B2FZE7SDJHHJ=traits-and-limitations h_01HE7RG1GE2E37NN4WT1XYG9YX=%E5%8F%82%E7%85%A7" />
