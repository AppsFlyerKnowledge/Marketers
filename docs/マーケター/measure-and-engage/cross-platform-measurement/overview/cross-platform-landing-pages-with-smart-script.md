---
title: Smart Script｜クロスプラットフォーム向けランディングページ
metadata:
  keywords:
    - CTV
    - Marketers
    - gaming
    - cross-platform
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2023-09-10T07:17:21Z'
  edited_at: '2026-10-21T19:04:30Z'
  id: 18440789126289
  locale: ja
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/ja/articles/18440789126289
---
> **概要：** AppsFlyer Smart Scriptを実装したクロスプラットフォーム向けランディングページを使用して、Web-to-appアトリビューションを行います。つまり、任意のメディアソースのWeb広告を見たユーザーを、CTV、PC、コンソール、モバイルなどのプラットフォーム上のアプリユーザーへ転換できます。

<div id="overview" />

## 概要

AppsFlyer Smart Scriptを実装したクロスプラットフォーム向けランディングページを使用すると、Web-to-appアトリビューションを行えます。これにより、Web上に表示された広告から、任意のプラットフォーム上のインストールをアトリビューションできます。

クロスプラットフォーム向けランディングページ内のSmart Scriptは、受信リンク（Web広告上のリンク）を使用して、元のメディアソースとWeb広告をインストールに正しくアトリビューションするため、次の2つの処理を行います。

* AppsFlyerへインプレッションを送信するクロスプラットフォームOneLinkリンクを作成する。
* 各アプリ／プラットフォーム向けのダイレクトアトリビューションリンクを作成する。

<div id="setup" />

## 設定

<div id="scope-of-work" />

#### 作業範囲

| **関係者**<ul><li>**広告主**：<ul><li>Smart Script内の[クロスプラットフォームインプレッション](#create-crossplatform-impression-link)および[ダイレクトアトリビューションリンク](#create-direct-attribution-links)に含める内容を、Smart Script内の<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#arguments">引数</Anchor>に基づいて決定します。受信URLの値を操作する、または特定の値を強制的に設定することで、送信URLに追加されるアトリビューションデータを決定します。</li><li>Webサイトへ流入するすべてのキャンペーンで、Smart Scriptが処理できるパラメータを含む受信URLが使用されていることを確認します。</li><li><Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html">Smart Scriptをテスト</Anchor>します。</li></ul></li><li>**Web開発者**：<ul><li>スクリプトに引数を追加し、クロスプラットフォーム向けランディングページにSmart Scriptを実装します。</li><li>Smart Scriptをテストします。</li></ul></li></ul> |
| --- |
| **前提条件**<ul><li>少なくとも1つのアプリが登録されているAppsFlyerアカウント。</li><li>インプレッションURL用： <Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレート</Anchor>でクロスプラットフォームアトリビューションが有効になっていること。</li></ul> |

<div id="create-crossplatform-impression-link" />

<Accordion title="クロスプラットフォームインプレッションリンクの作成">

**AppsFlyerへインプレッションを送信するクロスプラットフォームOneLinkリンクを作成するには**：

1. 受信リンクのパラメータを、インプレッションリンクに含めるパラメータ（メディアソース、キャンペーン、広告名など）へマッピングします。
   * 受信URLを処理するスクリプト内の<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#arguments">引数</Anchor>について詳しくは、こちらを参照してください。
   * <Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#arguments">OneLinkURL引数</Anchor>には、クロスプラットフォームアトリビューションを有効にしたOneLinkテンプレートのドメイン＋IDを指定します。
2. 開発者に、Smart Scriptの引数を初期化し、Smart Scriptの`generateOneLinkURL`メソッドを呼び出すよう依頼します。<Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">開発者向けデモと手順</Anchor>を参照してください。  
   **注意：** クロスプラットフォームアトリビューションを有効にするには、`af_xplatform=true`パラメータが必須です。

</Accordion>

<div id="create-direct-attribution-links" />

<Accordion title="ダイレクトアトリビューションリンクの作成">

1. 受信リンクのパラメータを、送信するダイレクトアトリビューションリンクに含めるパラメータ（メディアソース、キャンペーン、広告名など）へマッピングします。受信URLを処理するスクリプト内の<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#arguments">引数</Anchor>について詳しくは、こちらを参照してください。
2. 開発者にSmart Scriptの引数を初期化し、Smart Scriptの`generateDirectClickURL`メソッドを実行するよう依頼します。これにより、各プラットフォーム／アプリ向けのリンクを作成します。開発者向けの<Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">デモ</Anchor>と<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/create-direct-click-url">手順</Anchor>を参照してください。  
   **注意：** 開発者は、以下のパラメータを追加する必要があります。  

| パラメータ／引数 | 備考 | 回答の記入欄（ご自身または開発者向け） |
| --- | --- | --- |
| platform | プラットフォームを示す文字列です。以下のいずれかを指定する必要があります。<ul><li>smartcast</li><li>tizen</li><li>roku</li><li>webos</li><li>vidaa</li><li>playstation</li><li>android</li><li>ios</li><li>steam</li><li>quest</li><li>battlenet</li><li>nativepc</li></ul> |  |
| app\_id | <ul><li>アプリID</li><li>例：123456</li></ul> |  |
| redirectURL | <ul><li>プラットフォーム／アプリのユーザーをリダイレクトするURL。</li><li>例：`https://store.steampowered.com/app/123456/Team_Fortress_2/`</li></ul> |  |

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 01H8V0RV7X8JEVEJ36TJB1X43D=%E6%A6%82%E8%A6%81 setup=%E8%A8%AD%E5%AE%9A 01H8V0RV7X0K157JTDQMJSQYKF=%E8%A8%AD%E5%AE%9A scope-of-work=%E4%BD%9C%E6%A5%AD%E7%AF%84%E5%9B%B2 h_01H95PGMNWPBRHSZBPMKNJ2PS6=%E4%BD%9C%E6%A5%AD%E7%AF%84%E5%9B%B2 01H8EQ4KS75Q62Z7WVNSTDXBZX=create-crossplatform-impression-link 01H8EQ4KS7C6HADNKQZYNTTFMF=create-direct-attribution-links" />
