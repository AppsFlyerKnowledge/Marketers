---
title: Smart Banners｜Webサイトへのコード実装（マーケター向け）
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Developer
    - Developers
    - Smart Banner
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2022-01-10T11:25:54Z'
  edited_at: '2026-10-28T09:20:13Z'
  id: 4416119954705
  locale: ja
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/ja/articles/4416119954705
---
> **概要：** WebサイトにSmart Bannersのコードを追加し、訪問者をモバイルアプリのユーザーへ誘導します。

<div id="note" />

> 📘 **注意**
>
> AppsFlyerのSmart Banners Web SDK v1は、2023年11月8日をもって非推奨となりました。 WebサイトにSmart Bannersを表示するには、v2へのアップグレードが必要です。<Anchor target="_blank" href="/marketers/ja/docs/bulletin-deprecation-of-appsflyer-smart-banner-web-sdk-v1">詳細はこちら</Anchor>

<div id="website-code-implementation" />

## Webサイトへのコード実装

この記事では、以下のいずれかを使用して自社サイトにSmart Bannersのコードを実装したいマーケター向けに、手順を説明します。

* Googleタグマネージャー（GTM）
* Adobe Launch Tag Manager
* Shopify
* Wix
* Squarespace
* WordPress

他のプラットフォームでの実装や、要件に合わせたコードの変更（パラメータの追加、ディープリンク、バナーの非表示、PBAとSmart Bannersの連携など）については、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2">Smart Banners｜Webサイトへのコード実装（開発者向け）</Anchor>を参照してください。

**自社サイトにSmart Bannersのコードを実装するには：**

1. <Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers#1-website-workplace-setup">Webサイトのワークスペースの設定手順</Anchor>に従い、Smart Bannersのコードを取得します。
2. 以下のプラットフォーム別の手順に従って、Webサイトにコードを実装します。

<div id="google-tag-manager" />

<Accordion title="Googleタグマネージャー">

**Googleタグマネージャーでコードを実装するには：**

1. GTMで新しいタグを作成します。
2. タグに名前を付け、<strong>［タグの設定］</strong>をクリックし、<strong>［カスタムHTML］</strong>を選択します。
3. HTMLの入力欄に、Smart Bannersのコードスニペットを貼り付けます。スニペット内のYOUR-BANNER-KEYを、実際のバナーキーに置き換えます。
4. <strong>［トリガー］</strong>をクリックし、画面右上の＋アイコンをクリックして新しいトリガーを作成します。
5. トリガーに名前を付け、<strong>［トリガーの設定］</strong>で<strong>［ページビュー］</strong>を選択します。
6. すべてのページでバナーを表示する場合は、<strong>［すべてのページビュー］</strong>を選択します。特定のページでのみバナーを表示する場合は、<strong>［一部のページビュー］</strong>を選択し、タグを発火させる条件を設定します。トリガーの詳細は、<Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7679319?hl=en&ref_topic=7679108">GTMのドキュメント</Anchor>を参照してください。
7. 右上の<strong>［保存］</strong>をクリックします。
8. タグの設定画面に戻ります。設定内容を確認し、右上の<strong>［保存］</strong>をクリックします。
9. GTMのコンテナを公開します。

</Accordion>

<div id="adobe-launch-tag-manager" />

<Accordion title="Adobe Launch Tag Manager">

**Adobe Launch Tag Managerでコードを実装するには：**

<div id="step-1-create-a-property-in-adobe-experience-cloud" />

<Accordion title="手順1：Adobe Experience Cloudでプロパティを作成する">

**Smart Bannersのコードを配置するプロパティ（タグ）を作成するには：**

1. **［Adobe Experience Cloud］** > <strong>［Launch］</strong>に移動します。
2. <strong>［Adobe Experience Cloud Launch］</strong>で、<strong>［Go to Launch］</strong>をクリックします。
3. <strong>［New Property］</strong>をクリックします。
4. プロパティに名前を付けます。
5. <strong>［Platform］</strong>で<strong>［Web］</strong>を選択します。
6. Webサイトのドメインを入力します。
7. <strong>［Save］</strong>をクリックします。

</Accordion>

<div id="step-2-add-smart-banners-code-to-the-adobe-launch-property" />

<Accordion title="手順2：Adobe LaunchのプロパティにSmart Bannersのコードを追加する">

**タグにSmart Bannersのコードを追加するには：**

1. <strong>［My web property］</strong>ページで<strong>［Rules］</strong>タブを選択します。
2. ルールに名前を付けます。推奨名：**AppsFlyer Smart Banners**。
3. <strong>［If］</strong>セクションの<strong>［Events］</strong>で、<strong>［＋Add］</strong>をクリックします。
   * <strong>［Event Type］</strong>で<strong>［Core - DOM Ready］</strong>を選択します。
   * <strong>［Keep Changes］</strong>をクリックします。
4. <strong>［Then］</strong>セクションの<strong>［Actions］</strong>で、<strong>［＋Add］</strong>をクリックします。
   * **［Action Type］** > <strong>［Custom Code］</strong>を選択します。
   * **［JavaScript］** > <strong>［Open Editor］</strong>を選択し、**&lt;script>タグを除いた**Smart Banners SDKのスニペットを貼り付けます。
   * <strong>［Keep Changes］</strong>をクリックして、コードエディターを閉じます。
5. <strong>［Save］</strong>をクリックします。

</Accordion>

<div id="step-3-add-the-adobe-launch-tag-to-your-website" />

<Accordion title="手順3：WebサイトにAdobe Launchのタグを追加する">

**Smart Bannersのコードを読み込むAdobe Launchのタグを、Webサイトに追加するには：**

1. <strong>［My web property］</strong>ページで<strong>［Environments］</strong>タブを選択します。
2. 公開する環境（開発環境または本番環境）の行を探します。
   * 対象の行の<strong>［Install］</strong>列にあるボックスのアイコンをクリックします。通常は、本番環境の行を選択します。
   * **Adobe Launch**の環境の公開について説明するセクションを参照してください。
3. <strong>［Web Install Instructions］</strong>ダイアログで、次の操作を行います。
   * スクリプトのコードスニペットをコピーします。
   * ダイアログを閉じます。
4. Webサイトの&lt;head>タグ内にコードスニペットを貼り付けます。

</Accordion>

<div id="step-4-publish-the-adobe-launch-environment" />

<Accordion title="手順4：Adobe Launchの環境を公開する">

**環境を公開してAdobe Launchのタグを有効にするには：**

1. <strong>［My web property］</strong>ページで<strong>［Publishing］</strong>タブに移動します。
2. <strong>［Development］</strong>セクションで<strong>［Add New Library］</strong>をクリックします。
   1. ライブラリに名前を付け、環境を選択します。
   2. <strong>［Resource Changes］</strong>で<strong>［Add a Resource］</strong>をクリックします。
   3. **［Rules］** > **［Load Smart Banners］** > **［Latest］** > <strong>［Select & Create a New Revision］</strong>をクリックします。
   4. <strong>［Save］</strong>をクリックします。
3. <strong>［Development］</strong>セクションで、次の操作を行います。
   1. 新しく作成したライブラリの横にある操作メニュー（3点アイコン）をクリックし、<strong>［Build for Development］</strong>を選択します。
   2. もう一度操作メニューをクリックし、<strong>［Submit for Approval］</strong>を選択します。
4. <strong>［Submitted］</strong>セクションで、次の操作を行います。
   1. 操作メニューをクリックし、<strong>［Build for Staging］</strong>を選択します。
   2. もう一度操作メニューをクリックし、<strong>［Approve for Publishing］</strong>を選択します。
5. <strong>［Approved］</strong>セクションで操作メニューをクリックし、［Build & Publish to Production］  
   を選択します。これで手順は完了です。

</Accordion>

モバイルでWebサイトを読み込むと、有効なバナークリエイティブが表示されます。特定のページやユーザー操作に応じてのみバナーを表示するには、<Anchor target="_blank" href="https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html">Adobe Launchのルール</Anchor>を参照してください。

</Accordion>

<div id="shopify" />

<Accordion title="Shopify">

**ShopifyのWebサイトにコードを実装するには：**

1. Shopifyの管理画面で、**［販売チャネル］** > **［オンラインストア］** > <strong>［テーマ］</strong>に移動します。  
   現在のテーマが表示されます。
2. **［アクション］** > <strong>［コードを編集］</strong>をクリックします。  
   テーマのコード編集ページが開きます。
3. Layoutフォルダーで、**`{/}` theme**で始まるファイルをクリックします。  
   Webページのコードが表示されます。
4. コード内の **&lt;head>** の直下に、Smart Bannersのコードを貼り付けます。

</Accordion>

<div id="wix" />

<Accordion title="Wix">

**WixのWebサイトにコードを実装するには**：

1. Wixの管理画面で<strong>［設定］</strong>をクリックします。
2. 設定ページの詳細設定セクションで<strong>［カスタムコード］</strong>をクリックします。
3. <strong>［＋カスタムコードを追加］</strong>をクリックします。
4. <strong>［コードスニペットをここに貼り付け］</strong>欄に、Smart Bannersのコードを貼り付けます。
5. 名前の入力欄に、コードの名前を入力します。 **推奨名**：AppsFlyer Smart Banners。
6. <strong>［コードを追加するページ］</strong>で、バナーを表示するページを選択します。次のいずれかを選択します。
   * すべてのページ
   * 特定のページを選択
7. <strong>［適用］</strong>をクリックします。  
   カスタムコードのページに、追加したコードが表示されます。 **Head**セクションに配置されていることを確認します。

</Accordion>

<div id="squarespace" />

<Accordion title="Squarespace">

**SquarespaceのWebサイトにコードを実装するには**：

1. Squarespaceの管理画面で<strong>［Website］</strong>をクリックします。
2. <strong>［Settings］</strong>をクリックします。
3. <strong>［Advanced］</strong>をクリックします。
4. <strong>［Code Injection］</strong>をクリックします。
5. <strong>［Header］</strong>セクションに、Smart Bannersのコードを貼り付けます。
6. <strong>［Save］</strong>をクリックします。

</Accordion>

<div id="wordpress" />

<Accordion title="WordPress">

**WordPressのWebサイトにコードを実装するには**：

1. WordPressの管理画面で、**［外観］** ><strong>［テーマエディター］</strong>をクリックします。  
   テーマの編集ページが開き、WebサイトのCSSコードが表示されます。
2. <strong>［テーマファイル］</strong>で<strong>［テーマヘッダー（header.php）］</strong>をクリックします。
3. 表示されたコードの **&lt;head>** の下に、Smart Bannersのコードを貼り付けます。
4. <strong>［ファイルを更新］</strong>をクリックします。

</Accordion>

<div id="see-also" />

> 📄 **関連情報**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide#installation-and-integration">Smart BannersとPBAの連携</Anchor>

<div data-zendesk-anchors="h_01HBT97B1ZGKKTD0TN2J2W56ZQ=%E6%B3%A8%E6%84%8F website-code-implementation=web%E3%82%B5%E3%82%A4%E3%83%88%E3%81%B8%E3%81%AE%E3%82%B3%E3%83%BC%E3%83%89%E5%AE%9F%E8%A3%85 h_01HBT97B1Z0F4B8E9GQWJEE6BH=web%E3%82%B5%E3%82%A4%E3%83%88%E3%81%B8%E3%81%AE%E3%82%B3%E3%83%BC%E3%83%89%E5%AE%9F%E8%A3%85 h_01HBT97B1ZKW36W9F0XQKM323P=google-tag-manager h_01HBT97B1ZX6VM1YER2HXTYQJ2=adobe-launch-tag-manager h_01HBT97B1ZPP0AKB5E31W36VC2=step-1-create-a-property-in-adobe-experience-cloud h_01HBT97B1ZK4T23MF4D6VGP4B8=step-2-add-smart-banners-code-to-the-adobe-launch-property h_01HBT97B1Z0W9VJ5FCW4605RDC=step-3-add-the-adobe-launch-tag-to-your-website h_01HBT97B1Z1W33DTT6NR4PQHQ0=step-4-publish-the-adobe-launch-environment h_01HBT97B1Z0NTYJKB2YFMX62P9=shopify h_01HBT97B1ZYVJ6PW7F811V5TAX=wix h_01HBT97B1ZS0FDM60M1GA04PRT=squarespace h_01HBT97B1ZKYB7XPGFG00PB2BT=wordpress h_01HE7SG3MJ4WTPMTXF0DA0M07D=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />
