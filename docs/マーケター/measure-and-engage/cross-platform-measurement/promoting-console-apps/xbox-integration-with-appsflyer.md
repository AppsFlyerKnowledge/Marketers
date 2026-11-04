---
title: Xbox連携設定
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-04-13T08:28:00Z'
  edited_at: '2026-10-14T09:38:11Z'
  id: 14504812967057
  locale: ja
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/ja/articles/14504812967057
---
> **概要： 概要 ：AppsFlyerへ自身のXboxアプリを追加し、Xbox上のキャンペーンの計測とイベントデータを取得しましょう。**

<div id="about-xbox-attribution" />

## Xboxアトリビューションについて

コンソールおよびCTVアプリ用のXbox OSは、全てのXboxで動作します。

PC上で稼働するアプリは、S2S APIまたはSDKを介してAppsFlyerと連携し、どのソースやキャンペーンがアプリ起動イベントやアプリ内イベントを促進したかに関するアトリビューションデータやパフォーマンス測定値を受け取ることができます。マーケターは、これらのインサイトを活用してマーケティング活動を測定および最適化できます。

Xbox API連携では、以下がサポートされています：

* Xbox。
* Xboxアプリのアトリビューションとイベントの記録（ユーザーのXbox端末の計測と記録）

<div id="integration-procedures" />

## 連携手順

次の表では、CTVアプリにAppsFlyerを実装するために必要なタスクを記載しています。

| タスク | アクション | 作業担当者 |
| --- | --- | --- |
| アプリ設定 | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">AppsFlyerアカウントを作成</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/user-management">適切な権限を持つアカウントユーザーを追加します。</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer">AppsFlyer管理画面にXboxアプリを追加する</Anchor></li></ul> | マーケティング担当者 |
| アプリとAPIの連携（S2SまたはSDK経由） | AppsFlyerへ以下のイベントをレポートするコマンドを使用して、AppsFlyer Epic APIをアプリに実装してください。<ul><li>初回起動</li><li>In-app events</li><li>セッション</li></ul>**注意**：<ul><li>アプリの初回起動は、アプリ内イベントやセッションの前にレポートする必要があります。</li><li>APIを使用してイベントを送信する必要があります。デベロッパーにどのイベントを送信したいかを伝えてください。 APIを設定する際、AppsFlyerに送信するイベントを設定しマッピングしていることを確認してください。/span></li></ul>オウンドメディアエンゲージメントをレポートするには、 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">インプレッションエンゲージメントAPI</Anchor> を連携してください。 | アプリ開発者 |
| レポートの設定 | <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts#データの可用性">詳細：管理画面とレポートでのデータの可用性</Anchor> | マーケター / データエンジニア |

<div id="traits-and-limitations" />

<Accordion title="特性と制限">

| 特性 | 備考 |
| --- | --- |
| リターゲティング | 現在サポートされていません |
| コストデータ | コストデータは、メールメソッドによるアップロードファイルを使用して、<Anchor target="_blank" href="/marketers/ja/docs/import-cost-data">コストインポート</Anchor>経由で送信する必要があります。 |

</Accordion>

<div id="see-also" />

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts">CTV、PC、コンソールプラットフォームの概要</Anchor>

<div data-zendesk-anchors="about-playstation-attribution=xbox%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 01H7Z1NEAJMRWKHS4K168V0753=xbox%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 integration-procedures=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 01H7Z1NEAJJY4ZRVKY74ACXAAR=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 01H7Z1NEAJRA11P7NG05KRKR8Q=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%E5%8F%82%E7%85%A7" />
