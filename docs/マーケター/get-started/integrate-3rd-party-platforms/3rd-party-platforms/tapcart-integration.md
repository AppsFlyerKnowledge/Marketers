---
title: Tapcartとの連携
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-24T09:21:54Z'
  edited_at: '2026-10-28T09:03:55Z'
  id: 4411720533905
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/4411720533905
---
> **概要：** Tapcartを使用して、アプリでAppsFlyerの機能を活用します。

<div id="introduction" />

## はじめに

Tapcartでは、AppsFlyerへのデータ送信と機能の活用を簡単に行えます。 Tapcartでアプリを開発すると、AppsFlyer SDKが標準でアプリに組み込まれます。 Tapcartでデータを記録すると、オーガニックと非オーガニックのインストールを含むデータがAppsFlyerに表示されます。

<div id="integrating-tapcart-with-appsflyer" />

## TapcartとAppsFlyerを連携する

AppsFlyer SDKでは、インストール、アンインストール、紹介、プッシュ通知へのユーザーの反応の計測、ディープリンクの実行、ユーザーのプライバシー設定への対応などができます。

連携方法は、<Anchor target="_blank" href="https://tapcart.com/integrations/appsflyer">Tapcartのページ</Anchor>を参照してください。

<div id="default-in-app-events-configured-in-the-appsflyer-sdk" />

## AppsFlyer SDKで標準設定されているアプリ内イベント

TapcartがアプリにAppsFlyer SDKを組み込むと、ユーザーの操作に応じて次のアプリ内イベントが記録されます。

* 登録完了
* ログイン
* 検索
* コンテンツの閲覧
* リストの閲覧
* ウィッシュリストへの追加
* カートへの追加
* 購入手続きの開始
* 購入
* 購入完了
* カートからの削除
* 初回購入

<div id="enable-deep-linking-with-appsflyer" />

## AppsFlyerでディープリンクを有効にする

**AppsFlyerでディープリンクを有効にするには、次のパラメータをTapcartに提供します。**

1. **Devキー：** 一意の識別子であり認証トークンでもあるこのキーは、SDKの設定、メッセージの暗号化、クライアントアカウントやAPIを呼び出すプログラムの認証に使用します。  
   通常、同じアカウント内のアプリは同じDevキーを使用します。 <Anchor target="_blank" href="/marketers/ja/docs/app-settings#sdk-authentication-dev-key">Devキー</Anchor>の詳細を確認してください。
2. **OneLinkテンプレートID：** OneLink URLの生成に使用するOneLinkテンプレートのIDです。 <Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレートの作成</Anchor>の詳細を確認してください。  
   **特定のテンプレートのIDを取得するには、次の手順に従います。**  
   1. AppsFlyerで<strong>［エクスペリエンスとディープリンク］</strong>＞<strong>［OneLinkカスタムリンク］</strong>に移動します。
   2. <strong>［OneLinkテンプレート］</strong>メニューで、対象のテンプレートを選択します。
   3. 右側に表示されるIDをコピーします。  
       [![OneLink-template-id.png](https://files.readme.io/bb9524b5aecacba00c7f4801f7c854567119c032fa99a6d39122079e3f7956d1-small-4631542470673.png)](https://files.readme.io/bb9524b5aecacba00c7f4801f7c854567119c032fa99a6d39122079e3f7956d1-small-4631542470673.png)
3. **OneLink URL：** 特定のキャンペーン向けにAppsFlyerで生成した、個別のOneLink URLです。 <Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLinkの生成方法</Anchor>の詳細を確認してください。

<div data-zendesk-anchors="introduction=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB h_01JQ6D9NCM8K3E6GS12V2CR1CH=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB integrating-tapcart-with-appsflyer=tapcart%E3%81%A8appsflyer%E3%82%92%E9%80%A3%E6%90%BA%E3%81%99%E3%82%8B h_01JQ6D9NCM95VJB19G2F7SDRG1=tapcart%E3%81%A8appsflyer%E3%82%92%E9%80%A3%E6%90%BA%E3%81%99%E3%82%8B default-inapp-events-configured-in-the-appsflyer-sdk=appsflyer-sdk%E3%81%A7%E6%A8%99%E6%BA%96%E8%A8%AD%E5%AE%9A%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%82%8B%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01JQ6D9NCMYBNJ6WJ09R1EHXH4=appsflyer-sdk%E3%81%A7%E6%A8%99%E6%BA%96%E8%A8%AD%E5%AE%9A%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%82%8B%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 enable-deep-linking-with-appsflyer=appsflyer%E3%81%A7%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E6%9C%89%E5%8A%B9%E3%81%AB%E3%81%99%E3%82%8B h_01JQ6D9NCMC97JQ759B44M9TDJ=appsflyer%E3%81%A7%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E6%9C%89%E5%8A%B9%E3%81%AB%E3%81%99%E3%82%8B" />
