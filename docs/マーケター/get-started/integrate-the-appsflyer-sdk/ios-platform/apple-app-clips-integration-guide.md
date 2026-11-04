---
title: Apple App Clipsの実装ガイド
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2020-10-09T00:42:10Z'
  edited_at: '2026-10-28T09:11:26Z'
  id: 360014262358
  locale: ja
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/ja/articles/360014262358
---
> **概要：** App Clipsを使うと、iOS 14以降のユーザーが、すぐにアプリにアクセスし、その機能を体験できます。 AppsFlyerはApp Clipのアトリビューションに対応し、AndroidユーザーなどApp Clipsを利用できないユーザーを、必要に応じて適切なページにリダイレクトします。

![app_clip_flow_3.png](https://files.readme.io/1a5ec7a6b8a061955742d8e79ba78fa0262c0609e1e801decc92300d6c24a774-360012832058.png)

<div id="app-clip-integration" />

## App Clipの連携

* App Clipsは、アプリ本体をダウンロードせずに、iOS 14のユーザーが手軽にアプリの機能を体験できる仕組みです。
* App Clipsは、QRコードやNFCタグなどからの呼び出しによって、インストール・起動されます。**注意**：SafariのSmart App Bannerと「メッセージ」アプリ内のリンクには対応していません。
* App Clipのクリック、インストール、アプリ内イベント、App Clipからアプリ本体へのインストールを紐付けるには、AppsFlyer SDKが必要です。
* OneLinkはSDKとは独立して、必要に応じてユーザーをリダイレクトします。
  * アプリ本体をインストールしていないユーザー：
    * iOS 14以降の場合は、App Clipに移動します。
    * iOS 13以前またはAndroidの場合は、OneLinkの設定に基づいて、アプリストアなどにリダイレクトされます。
  * アプリ本体をインストールしているユーザーは、OneLinkのUniversal LinkまたはApp Linkの設定に基づいて、アプリ本体に移動します。

<div id="considerations" />

### 留意事項

* App Clipsのサイズは、最大10 MBです。 AppsFlyer SDKのサイズは、約1.5 MBです。
* 広告識別子は利用できません。
* App Clipsは、30日間利用されないと、OSによって自動的に削除されます。

<div id="example" />

> 📄 **例**
>
> マークは、コーヒーチェーンのマーケターです。お客様が列に並ばず、数秒で注文できるApp Clipを作成するよう、iOS開発者に依頼します。お客様は、<Anchor target="_blank" href="https://developer.apple.com/sign-in-with-apple/">Appleでサインイン</Anchor>を使ってログインし、コーヒーを注文して、<Anchor target="_blank" href="https://developer.apple.com/apple-pay/">Apple Pay</Anchor>で支払うだけです。開発者はAppsFlyer SDKを追加し、アプリ本体とApp Clipの両方で動作することを確認します。
>
> マークはOneLinkを作成し、「並ばず注文！」という案内とともに、店内にQRコードを掲示します。
>
> お客様がQRコードを読み取ると、次のように動作します。
>
> * iOS 14以降のデバイスを使用している場合、App Clipが開きます。該当する店舗の情報と割引クーポンが表示されます。
> * アプリ本体をすでにインストールしている場合は、アプリのコーヒー注文画面が開きます。
> * アプリ本体をインストールしておらず、iOS 13以前またはAndroidのデバイスを使用している場合は、コーヒーチェーンのアプリのストアページが開きます。
>
> マークは、AppsFlyerのダッシュボードとレポートで、App Clipのクリック数・インストール数と、最終的にアプリ本体をダウンロードしたユーザー数を確認します。

<div id="metrics-and-reporting" />

## 指標とレポート

以下の表のユーザー行動に基づき、App Clipsの分析データとローデータをプラットフォーム上で確認できます。

| ユーザーの行動 | AppsFlyerのイベント | オーバービューダッシュボードと分析ツール | ローデータ |
| --- | --- | --- | --- |
| 呼び出し（例：QRコード） | イベントなし | イベントなし | イベントなし |
| App ClipカードをクリックしてApp Clipが開く | クリックとインストールが呼び出し元に紐付けられる | <ul><li>クリック</li><li>インストール</li></ul> | <Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=app\_clip</Anchor> |
| App Clipを使用する | <ul><li>［任意］開発者がアプリ内イベントを送信</li><li>App Clipの初回起動後、以降の起動はセッションとしてカウントされます。</li></ul> | <ul><li>アプリ内イベント</li><li>セッション</li></ul> | <ul><li>開発者が送信したアプリ内イベント</li><li><Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=app\_clip</Anchor></li></ul> |
| アプリ本体をダウンロードして起動する | アプリ内イベント | アプリ内イベント名＝af\_app\_clip\_to\_full\_app | <ul><li>アプリ内イベント名＝af\_app\_clip\_to\_full\_app</li><li><Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=full\_app</Anchor></li></ul> |
| アプリ本体を継続的に使用する | ［任意］開発者がアプリ内イベントを送信 | アプリ内イベント | <ul><li>開発者が送信したアプリ内イベント</li><li><Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=full\_app</Anchor></li></ul> |

**コホートダッシュボード**

<Anchor target="_blank" href="/marketers/ja/docs/cohort-and-retention-dashboard#trend-type%E2%80%94user-lifetime-performance">コホートダッシュボード</Anchor>では、App Clipの成果について、次のことを確認できます。

* App Clipの利用からアプリ本体のインストールまでにかかった時間。
* アプリ内コンバージョンの指標を使った、呼び出し元のキャンペーン間の成果比較。

<div id="app-clip-implementation" />

## App Clipの実装

以下では、App Clipsを開発・実装するために、お客様とiOS開発者が行う作業を説明します。

<div id="scope-of-work" />

#### 作業の範囲

| **担当者と役割**<ul><li>**広告主**：<ul><li>OneLinkテンプレートでApple App Clipsを設定します。</li><li>AppleのApp Store ConnectにOneLinkのリンクを登録します。</li><li>AppsFlyerのダッシュボードとレポートで指標を確認します。</li></ul></li><li>**iOS開発者**：<ul><li>App Clipを作成します。</li><li>App ClipにAppsFlyer SDKを実装します。</li></ul></li></ul> |
| --- |
| **事前準備**<ul><li>1つ以上のアプリが登録されているAppsFlyerアカウント。</li><li>Universal Linksが設定されたOneLinkテンプレートと、アプリ本体のユーザーを誘導するよう設定されたOneLinkのリンク。<br />**推奨事項**：App Clipの呼び出しに使用するテンプレートとリンクは、アプリ本体をインストールしていないすべてのユーザーをApp Clipに誘導します。そのため、App ClipではなくApp Storeに誘導したい場合に備えて、別のテンプレートとカスタムリンクを用意することを検討してください。 0></li></ul> |

<div id="develop-app-clip" />

<Accordion title="App Clipの開発">

アプリのApp Clipを作成する詳しい手順は、Appleの<Anchor target="_blank" href="https://developer.apple.com/app-clips/">開発者向けApp Clipガイド</Anchor>を参照してください。

App Clipsの利用方法やアプリ本体との連携を紹介する簡単なサンプルアプリは、<Anchor target="_blank" href="https://www.appsflyer.com/resources/others/apple-app-clips/">AppsFlyerのApp Clipガイド</Anchor>を参照してください。

</Accordion>

<div id="integrate-sdk" />

<Accordion title="SDKの実装">

* クリック、インストール、アプリ内イベント、App Clipからアプリ本体へのインストールをAppsFlyerで紐付けるには、SDKが必要です。
* OneLinkによるユーザーのリダイレクトは、SDKの実装とは独立して動作します。

**SDKの導入とアプリ本体のSDKの設定方法**：

次のリンクをiOS開発者に共有し、各手順に従って対応するよう依頼してください。

* <Anchor target="_blank" href="https://dev.appsflyer.com/docs/app-clip-sdk-integration">App ClipへのSDK実装</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/docs/app-clip-to-full-app-install">App Clipからアプリ本体へのインストールのアトリビューション設定</Anchor>
* ［任意］アプリ本体のアプリ内イベントをまだ計測していない場合や、App Clipで別のアプリ内イベントを使用したい場合は、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events">アプリ内イベントを設定</Anchor>します。

</Accordion>

<div id="configure-onelink" />

<Accordion title="OneLinkの設定">

**事前準備**：

* アプリ本体用の、iOS Universal Linksが設定された<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレート</Anchor>。
* <Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#onelinkリンクの作成">OneLinkのリンク</Anchor>。
* **推奨事項**：App Clipの呼び出しに使用するテンプレートとリンクは、アプリ本体をインストールしていないすべてのユーザーをApp Clipに誘導します。そのため、App ClipではなくApp Storeに誘導したい場合に備えて、別のテンプレートとカスタムリンクを用意することを検討してください。

**App Clip用のOneLinkテンプレートの設定方法**：

1. AppsFlyerダッシュボードで、**［エンゲージ］**＞<strong>［OneLink管理］</strong>に移動します。
2. アプリ本体にユーザーを誘導するための**OneLinkテンプレート**を選択します。
3. OneLinkテンプレートにUniversal Linksが設定されていることを確認します。 Universal Linksを追加する<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">手順</Anchor>を参照してください。
4. <strong>［保存］</strong>をクリックします。  
   App Clipに対応するよう、AASAファイルが更新されます。
5. AppsFlyerダッシュボードで、**［エンゲージ］**＞<strong>［OneLink管理］</strong>に移動します。
6. 手順1～4で設定したテンプレートに基づく、App Clipにユーザーを誘導するための**OneLinkカスタムリンク**を選択します。
7. メディアソース（pid）が指定されていることを確認します。  
   メディアソースは、URL内で指定する（例：**pid=chartboost\_int**）か、リンク内に含める必要があります。

**AppsFlyerのOneLinkでApp Clipsが有効になっていることを確認する方法：**

1. アプリとの関連付けを確認するファイルを取得するためのURLを作成します。 OneLinkテンプレートのドメインに`/.well-known/apple-app-site-association`を追加して、URLを作成します。   
   例：`coffee.onelink.me/.well-known/apple-app-site-association`。
2. 関連付けファイルのURLにアクセスします。  
   apple-app-site-association ファイルが自動的にダウンロードされます。
3. apple-app-site-associationファイルを、メモ帳などのテキストエディターで開きます。
4. ファイルに「**appclips**」という文字列が含まれていることを確認します。また、バンドルIDの末尾が「**.Clip**」になっていることを確認します。例：  

   ```java
   "appclips": {
       "apps": [
         "ABCD1234.id.your.app.Clip",
         ...
       ]
   ...
   }
   ```

   この内容が確認できれば、AppsFlyer側でApp Clipsの設定が完了しています。同じサブドメインを持つすべてのOneLinkテンプレートで、App Clipが実装された状態になります。

</Accordion>

<div id="configure-app-store-connect" />

<Accordion title="App Store Connectの設定">

**事前準備**：[App Clips用のOneLinkテンプレートの設定](/docs/apple-app-clips-integration-guide#configure-onelink)が完了していること。

**App ClipをOneLinkと連携させる設定方法**：

1. App Store Connectのアプリのページで、**［ビルド（Build）］**＞<strong>［ドメインの状態（Domain Status）］</strong>に移動します。
2. <strong>［ビルドのドメイン（Build domains）］</strong>にOneLinkのドメインが表示され、<strong>［キャッシュの状態（Cache status）］</strong>と<strong>［デバッグの状態（Debug status）］</strong>が、どちらも「検証済み（validated）」になっていることを確認します。
3. AppsFlyerダッシュボードで、**［エンゲージ］**＞<strong>［OneLink管理］</strong>に移動します。
4. 使用するリンクの<strong>［操作］</strong>アイコンにカーソルを合わせ、<strong>［URLを取得］</strong>をクリックします。
5. ショートURL、またはロングURLの先頭部分を控えておきます。
6. App Store Connectのアプリのページで、**［App Clip］**＞**［高度な体験を編集］**＞**［＋追加］**＞<strong>［次へ］</strong>に移動します。
7. <strong>［App Clip体験URL］</strong>に、手順5で控えたOneLinkのカスタムURLを貼り付けます。  
   **注意**：カスタムURLの後ろにクエリパラメータを追加できますが、パスは変更できません。
8. <strong>［次へ］</strong>をクリックします。  
   これで、App ClipとOneLinkの連携設定が完了します。 App Store Connectの設定について詳しくは、<Anchor target="_blank" href="https://developer.apple.com/documentation/app_clips/configuring_your_app_clip_s_launch_experience">Appleの開発者向けガイド</Anchor>を参照してください。

</Accordion>

<div id="testing" />

<Accordion title="テスト">

**事前準備**：アプリ本体がインストールされていない、iOS 14の<Anchor target="_blank" href="/marketers/ja/docs/registering-test-devices">登録済みテストデバイス</Anchor>。

**OneLinkとApp Clipの連携をテストする方法：**

1. AppsFlyerダッシュボードで、**［エンゲージ］**＞<strong>［OneLink管理］</strong>に移動します。
2. テストするリンクの<strong>［操作］</strong>アイコンにカーソルを合わせ、<strong>［URLを取得］</strong>をクリックします。
3. デバイスでQRコードを読み取ります。  
   デバイスにApp Clipカードが表示されれば、OneLinkとApp Clipの連携が正しく設定されています。

</Accordion>

<div id="traits-and-limitations" />

## 仕様と制限事項

<div id="traits-and-limitations::26141033" />

<Accordion title="仕様と制限事項">

| 仕様／制限事項 | 説明 |
| --- | --- |
| 呼び出し方法 | <ul><li>QRコードとNFCタグに対応しています。</li><li>SafariのSmart App Bannerと「メッセージ」アプリ内のリンクには対応していません。</li></ul> |
| SKAdNetwork | SKAdNetworkの機能は利用できません。そのため、App Clipのインストールは、SKAdNetworkダッシュボードにオーガニックとして表示されます。 |
| OneLink | OneLinkカスタムリンクごとに設定できる高度なApp Clip体験は、1つだけです。つまり、App Store ConnectでOneLinkに追加のパスを設定することはできません。 |
| Protect360 | Protect360はApp Clipsに対応していません。 |

</Accordion>

<div id="see-also" />

> 📄 **関連記事**
>
> * <Anchor target="_blank" href="https://www.appsflyer.com/resources/guides/ios-14-app-clips/">AppsFlyerによるApple App Clipsのアトリビューションソリューション</Anchor>

<div data-zendesk-anchors="app-clip-integration=app-clip%E3%81%AE%E9%80%A3%E6%90%BA h_01HDNZQTCBXY0Y3QYCBNVH7EAW=app-clip%E3%81%AE%E9%80%A3%E6%90%BA considerations=%E7%95%99%E6%84%8F%E4%BA%8B%E9%A0%85 h_01HDNZQTCBPJWY6H2M452QH644=%E7%95%99%E6%84%8F%E4%BA%8B%E9%A0%85 h_01HDNZQTCB7NB682YTSMNCJSDP=%E4%BE%8B metrics-and-reporting=%E6%8C%87%E6%A8%99%E3%81%A8%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HDNZQTCBNG3TYRAA7GVPF39P=%E6%8C%87%E6%A8%99%E3%81%A8%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 app-clip-implementation=app-clip%E3%81%AE%E5%AE%9F%E8%A3%85 h_01HDNZQTCBJK7SB96G8A4DHR34=app-clip%E3%81%AE%E5%AE%9F%E8%A3%85 scope-of-work=%E4%BD%9C%E6%A5%AD%E3%81%AE%E7%AF%84%E5%9B%B2 h_01HDNZQTCB1AKW9QFRRM9VVN4D=%E4%BD%9C%E6%A5%AD%E3%81%AE%E7%AF%84%E5%9B%B2 h_01HDNZQTCBN04J3GA8H64V70YY=develop-app-clip h_01HDNZQTCBHHENFYJK7MFJTZ14=integrate-sdk h_01HDNZQTCBN9QV4MZAAWMV164Y=configure-onelink h_01HDNZQTCC6F8TTM2FRQK6DB2E=configure-app-store-connect h_01HDNZQTCCN2BX9NZ4027ZCEFB=testing traits-and-limitations=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HDNZQTCCMW2YNK1G34EBM7DM=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HDNZQTCCV0S78NRK00PK4S0J=traits-and-limitations::26141033 h_01HDNZS83EKJNZGG1QEVS9RMCA=%E9%96%A2%E9%80%A3%E8%A8%98%E4%BA%8B" />
