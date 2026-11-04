---
title: LGとAppsFlyerの連携
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
  created_at: '2022-07-03T10:31:42Z'
  edited_at: '2026-10-21T19:05:30Z'
  id: 7341725624081
  locale: ja
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/ja/articles/7341725624081
---
> **概要：** LGのコネクテッドTV（CTV）アプリをAppsFlyerと連携し、LG上のキャンペーンに関するアトリビューションデータやイベントデータを取得します。

<div id="about-lg-ctv-attribution" />

## LG CTVアトリビューションについて

ストリーミング向けのLG webOSは、すべてのLG TVで利用されています。

LGで配信されるCTVアプリは、APIを介してAppsFlyerと連携することで、どのメディアソース（オーガニック／非オーガニック）やキャンペーンがアプリ起動やアプリ内イベントにつながったかを示すアトリビューションデータやパフォーマンス計測データを取得できます。マーケティング担当者は、これらのインサイトをもとにマーケティング施策の効果を計測し、最適化します。

LG API連携では、以下をサポートしています。

* LG Smart TV
* CTV-to-CTVのアトリビューションとイベント記録つまり、ユーザーのLG端末上でのアトリビューションとイベント記録に対応します。

<div id="integration-procedures" />

## 連携手順

以下の表に、LG CTVアプリをAppsFlyerと連携するために必要な作業をまとめています。

| タスク | 対応内容 | 担当者 |
| --- | --- | --- |
| アプリ設定 | <ul><li>AppsFlyerアカウントを作成</li><li>適切な権限を持つアカウントユーザーを追加</li><li>AppsFlyerにLG CTVアプリを追加</li></ul> | マーケティング担当者 |
| アプリとのAPI連携（S2SまたはSDK） | 連携方法は、S2SとSDKの2種類があります。<br /><br />S2S方式では、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">AppsFlyer APIをアプリに連携</Anchor>し、以下のイベントをAppsFlyerへ送信するよう実装します。<ul><li>初回起動</li><li>アプリ内イベント</li><li>セッション</li></ul>**注意**：<ul><li>インストールは、アプリ内イベントやセッションより先にレポートする必要があります。</li><li>イベントはAPIを使用して送信します。送信するイベントを開発者に共有します。 APIの設定時に、AppsFlyerへ送信するイベントを設定し、正しくマッピングしていることを確認してください。</li></ul>オウンドメディアでのエンゲージメントをレポートするには、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">インプレッションエンゲージメントAPI</Anchor>を連携します。<br /><br />SDK方式については、Developer Hubの<Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-html5-ctv-sdk">LG向けドキュメント</Anchor>を参照してください。 | アプリ開発者 |
| パートナー連携 | AppsFlyerでLG Adsを広告ネットワーク（連携済みパートナー）として追加します。<ol><li>パートナーの有効化</li><li>［任意］<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#e-install-attribution">**ビュースルーアトリビューション**</Anchor>**を有効にします。**</li></ol> | マーケティング担当者 |
| リンク設定 | ダイレクトアトリビューションリンクの作成方法 | マーケティング担当者 |
| レポート設定／データ確認 | ダッシュボードとレポートで利用できるデータについて | マーケティング担当者／データエンジニア |

<div id="traits-and-limitations" />

<Accordion title="特性と制限事項">

| 特性 | 備考 |
| --- | --- |
| リターゲティング | 現在はサポートされていません |
| コストデータ | コストデータは、メールによるファイルアップロード方式を使用し、<Anchor target="_blank" href="/marketers/ja/docs/import-cost-data">Cost Import</Anchor>経由で送信する必要があります。 |
| アトリビューション | LG Adsでは、アトリビューションに確率論的モデリングを使用します。現在、IDマッチングは利用できません。 |
| カスタマーID | LG Adsから取得したLGカスタマーID（`cust_id`）を、このパラメータに設定します。 |
| 決定論的アトリビューション | 広告IDを用いた決定論的なアトリビューションを有効にすることもできます。有効にするには、以下の要件を満たす必要があります。<ul><li>コンテンツパートナーのアプリでAD IDを取得できるようにする前に、LGによる法務レビューが必要です。</li><li>この法務レビューでは、コンテンツパートナーがLG Electronicsと直接連携し、両社で法的契約を締結する必要があります。</li><li>コンテンツパートナーのアプリには、LG AD IDを収集・送信する機能を実装する必要があります。さらに、AppsFlyerへAD IDを送信できるようにするため、ユーザー操作によるアプリ更新をリリースする必要があります。</li><li>詳細については、AppsFlyerのCSMおよび[partnerships@lgads.tv](mailto:partnerships@lgads.tv)までお問い合わせください。</li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **関連情報**
>
> * CTV、PC、コンソールプラットフォームの概要

<div data-zendesk-anchors="about-lg-ctv-attribution=lg-ctv%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 01H7Z17N0YAAGTDPMGZ89F7AVB=lg-ctv%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 integration-procedures=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 01H7Z17N0Y8RE5PS15N2JG5NRH=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 01H7Z17N0YCX89SYYJ1AMPM6W4=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />
