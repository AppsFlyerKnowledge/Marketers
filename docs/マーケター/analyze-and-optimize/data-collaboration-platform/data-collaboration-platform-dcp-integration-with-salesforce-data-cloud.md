---
title: データコラボレーションプラットフォーム(DCP) - Salesforce Data Cloudとの統合
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2024-02-29T14:30:51Z'
  edited_at: '2026-10-14T09:28:13Z'
  id: 22977208909969
  locale: ja
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/ja/articles/22977208909969
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** Salesforceデータクラウドの統合により、ボタン一つでファーストパーティデータをAppsFlyerデータコラボレーションプラットフォームに取り込むことができます。

<div id="before-you-begin" />

> 🚧 **始める前に：**
>
> Salesforce Data Cloudを統合する前に、 **AppsFlyerアプリ拡張機能をインストールしてください** Salesforce AppExchangeより。これは、AppExchangeパッケージをダウンロードする権限を持つSalesforce管理者が行う必要があります。
>
> 1. 行って <Anchor target="_blank" href="https://appexchange.salesforce.com/appxListingDetail?listingId=6c756ddf-777c-42fc-9eaf-d96ca36ed2e3">AppsFlyerの一覧</Anchor> Salesforce AppExchangeで。
> 2. カチッ **今すぐ入手**.
> 3. 以下に記載された手順に従ってください。 <Anchor target="_blank" href="https://developer.salesforce.com/docs/atlas.en-us.appExchangeInstallGuide.meta/appExchangeInstallGuide/appexchange_install_installation.htm">アプリケーションインストールガイド</Anchor>.
>
> インストールが成功すれば、プロセスは完了し、追加のパッケージ構成は不要です。

<div id="set-up-the-integration" />

## 連携設定方法：

統合にはSalesforceデータクラウド接続を作成し、その後ソースを作成することが含まれます。Salesforceアカウントの認証には接続が1つだけで十分です。この接続を使うことで、Salesforceのテーブルに基づいて複数のソースを作成できます。

<div id="note" />

> 📘 **注意**
>
> すでにSalesforce Data Cloudとの接続を設定している場合、新しい接続を作成することはできません。

<div id="create-a-salesforce-data-cloud-connection" />

### Salesforceデータクラウド接続を作成する

1. AppsFlyerのサイドメニューから選択 **協力しましょう** > **データクリーンルーム**.
2. ページ右上からクリック **接続管理**> **+ 新しい接続**.
3. では **新しい接続** ダイアログ、選択 **データプロバイダー**> **Salesforce Data Cloud**.  

   <Image align="center" alt="salesforce-data-cloud-new-connection.jpg" src="https://files.readme.io/6b240e0cff3f0bc9e6b7f6eaf45520a78252e1619769a696855e8d68d322ce60-23301617982353.jpg" width="517px" />
4. カチッ **Salesforceにログイン**.
5. 認証プロセスを進め、SalesforceにAppsFlyerへのアクセスを許可してください。   
   **注記：** 認証が失敗した場合、次のサイトに戻されます。 **新しい接続** ダイアログで再挑戦してください。
6. 認証が成功すると、あなたは **新しい接続** Salesforceとアクティブな接続があることを示して会話をします。これで情報源を作成できます。
7. カチッ **ソースを作成** そして [以下の指示](#salesforceデータクラウドソースの作成) Salesforceのデータクラウドソースを作成するために。

<div id="create-a-salesforce-data-cloud-source" />

### Salesforceデータクラウドソースの作成

Salesforceアカウントを認証し、Salesforce Data Cloudとの接続を設定したら、次のステップはソースの作成です。これらのソースは、アップデートを行うたびにAppsFlyerに必要なデータを提供します。

アクセス **出典** 以下の方法でタブを使います:

* 前のステップを完了したら、クリック **ソースを作成**.
* AppsFlyerのサイドメニューから **協力しましょう** > **データクリーンルーム** > **+ 新しい情報源** ページの右上隅に表示されます。

<div id="note-1" />

> 📘 **注意**
>
> ソースを作成する際は、制限されたデータがAppsFlyerに送信されていないことを確認してください。

**ソースを作成するには:**

1. ソース名ここで <Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-working-with-sources#1-name-the-source">源の名称</Anchor>、そしてクリック **次**.
2. ソースのロケーションを設定する
   * 接続の選択接続を追加した後、Salesforce Data Cloudは自動で登録されます。もしなければ、接続リストから選択してください。
   * *テーブルまたはビューSalesforce Data Cloud接続を選択すると、Salesforceアカウントのテーブル名やビューが自動で入力されます。テーブルまたはビューを選択し、クリック **次**.  

     <Image align="center" alt="create-source-sf-3-steps.jpg" src="https://files.readme.io/44549ef1cd59b99610944c604c1cdfd4d598352cd106877fab3a301ce14650f8-23306070497169.jpg" />
3. **ソーススキーマの設定:** テーブルやビューを選択すると、フィールド名とタイプは自動的に入力されます。フィールドの列の最後にあるビンアイコンを選択することで、フィールドタイプを編集したり不要なフィールドを削除したりできます。  
   **注記：** 少なくとも1種類のフィールドタイプが識別子として使われるようにしてください。例えば、CUID、Platform ID、AppsFlyer ID、SHA256ハッシュIDなどです。
4. **保存**をクリックしてください。新しいソースは既存のすべてのソースのリストに表示されます。

<div data-zendesk-anchors="h_01HPKB2ERPGD2PS4JBSDGYW3MC=%E5%A7%8B%E3%82%81%E3%82%8B%E5%89%8D%E3%81%AB set-up-the-integration=%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 01HRW9TK3YZV32CXRM6Q2HCHS4=%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 01HRSFKVQNJ264M16A9X9AEP53=%E6%B3%A8%E6%84%8F create-a-salesforce-data-cloud-connection=salesforce%E3%83%87%E3%83%BC%E3%82%BF%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E6%8E%A5%E7%B6%9A%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B h_01HRSDCVMHQ6C5R6R4S5XRT5KQ=salesforce%E3%83%87%E3%83%BC%E3%82%BF%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E6%8E%A5%E7%B6%9A%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B create-a-salesforce-data-cloud-source=salesforce%E3%83%87%E3%83%BC%E3%82%BF%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E4%BD%9C%E6%88%90 h_01HRSG0P4Q38WHGQWBY3S3D11W=salesforce%E3%83%87%E3%83%BC%E3%82%BF%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E4%BD%9C%E6%88%90 h_01HRVPJ801B0VC879APZCGKDNE=%E6%B3%A8%E6%84%8F-1" />
