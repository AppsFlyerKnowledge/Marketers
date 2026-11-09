---
title: キーワードデータの分析
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2023-07-25T08:19:25Z'
  edited_at: '2026-10-28T09:07:50Z'
  id: 17255366785553
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/17255366785553
---
> **概要：** 詳細なキーワードデータで、よく使われる検索語句を把握し、オーガニックのコンバージョンを最適化できます。

<div id="keyword-data" />

## キーワードデータ

オーガニック検索は、アプリにとって価値の高い流入元です。オーガニックユーザーは獲得コストがかからず、通常、エンゲージメントの高いコホートの1つです。

アプリページを少し調整することで、新規のオーガニックインストールを増やせる可能性があります。オーガニック検索を最適化するには、アプリのオーガニック検索のキーワードデータを取得する必要があります。

<div id="ios-keywords" />

### iOSのキーワード

Apple Adsを利用している場合、Apple Adsに紐付く**ノンオーガニック**ユーザーの<Anchor target="_blank" href="/marketers/ja/docs/apple-ads-integration-setup#get-keyword-data">詳細なキーワードデータ</Anchor>を取得できます。 iOSでは、**オーガニック検索**のキーワードデータは取得できません。

<div id="android-keywords" />

### Androidのキーワード

Googleは、以下の行動を取ったユーザーのオーガニック検索のキーワードデータを、リファラURLで共有します。

* Androidデバイスを使用する。
* Chromeブラウザを使用する。
* Google.comにアクセスして検索する。
* Googleの検索結果ページからアプリをインストールする。
* アプリを起動する。

Google Playへのリンクの一部として、Googleがリファラの*&utm\_term*パラメータでキーワードを提供した場合、SDKがそのキーワードを抽出します。取得できた場合、値はAppsFlyerの以下のローデータフィールドに含まれます：*http\_referrer*、g*p\_broadcast\_referrer*、*keywords。*

**この経路をたどり、オーガニック検索のキーワードデータを取得できるAndroidのオーガニックユーザーは、1％未満と見込まれます**。

それ以外の場合、Googleはオーガニック検索のキーワードデータを共有しません。たとえば、Google Play内で検索したユーザーのオーガニック検索キーワードデータは取得できません。

<div id="note" />

> 📘 **注意**
>
> この制限は、すべてのアトリビューション事業者を含む、すべての外部事業者に対してGoogleが適用しています。

<div id="using-thekeyworddata" />

### キーワードデータの活用

オーガニック検索のキーワードデータは、以下で確認できます。

* **オーガニックのローデータレポート**  
  AppsFlyerのサイドメニューで、**エクスポート**＞**ローデータエクスポート**を選択し、オーガニック検索で使われたキーワードの内訳を確認します。
* **詳細レポート**  
  <Anchor target="_blank" href="/marketers/ja/docs/pivot-table-user-metrics">ピボット</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/cohort-and-retention-dashboard">リテンション、コホート</Anchor>のレポートに移動し、キーワードでグループ化します。  
  キーワードごとにオーガニックユーザーの質を比較します。
* <Anchor target="_blank" href="/marketers/ja/docs/push-api-streaming-raw-data">Push API</Anchor>のメッセージ

<div id="testing-organickeyworddata" />

### オーガニック検索のキーワードデータのテスト

1. <Anchor target="_blank" href="/marketers/ja/docs/registering-test-devices">許可リストに登録したAndroid</Anchor>デバイスを使用します。
2. Chromeブラウザを開き、Google.comにアクセスします。
3. アプリを見つけやすいキーワードで検索します。   
   この例では「**hotels tonight**」を使用します。  
     
   <Image align="center" alt="organic_keywords_search.jpg" src="https://files.readme.io/b06db96b53df1502939b86cefd7217991d842f1c7e736cab6ba2c6e0de691400-32966747169425.jpg" width="426px" />
4. ***インストール***をクリックすると、Google Playストアに移動します。
5. アプリをインストールして起動します。  
   <Image align="center" alt="Hotels_Tonight_3.png" src="https://files.readme.io/c455f8229ba7879157eec6782d0eb2d94a91e1080a3c081f5452cc7e92608047-205710046.png" width="373px" />
6. 前述のAppsFlyerのレポートやAPIで、キーワードを探します。

<div data-zendesk-anchors="keyword-data=%E3%82%AD%E3%83%BC%E3%83%AF%E3%83%BC%E3%83%89%E3%83%87%E3%83%BC%E3%82%BF h_01HKA1D1TW1R20X6K05Q9GX904=%E3%82%AD%E3%83%BC%E3%83%AF%E3%83%BC%E3%83%89%E3%83%87%E3%83%BC%E3%82%BF ios-keywords=ios%E3%81%AE%E3%82%AD%E3%83%BC%E3%83%AF%E3%83%BC%E3%83%89 h_01HKA1D1TW9YXBMGERHW4EHZZN=ios%E3%81%AE%E3%82%AD%E3%83%BC%E3%83%AF%E3%83%BC%E3%83%89 android-keywords=android%E3%81%AE%E3%82%AD%E3%83%BC%E3%83%AF%E3%83%BC%E3%83%89 h_01HKA1D1TWT1VQ6NZ789BTCZJX=android%E3%81%AE%E3%82%AD%E3%83%BC%E3%83%AF%E3%83%BC%E3%83%89 h_01HKA1D1TW7E2RM7SXC9R5SA99=%E6%B3%A8%E6%84%8F using-the%C2%A0keyword%C2%A0data=%E3%82%AD%E3%83%BC%E3%83%AF%E3%83%BC%E3%83%89%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E6%B4%BB%E7%94%A8 h_01HKA1D1TWRPGTNGJKF7T1R71B=%E3%82%AD%E3%83%BC%E3%83%AF%E3%83%BC%E3%83%89%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E6%B4%BB%E7%94%A8 testing-organic%C2%A0keyword%C2%A0data=%E3%82%AA%E3%83%BC%E3%82%AC%E3%83%8B%E3%83%83%E3%82%AF%E6%A4%9C%E7%B4%A2%E3%81%AE%E3%82%AD%E3%83%BC%E3%83%AF%E3%83%BC%E3%83%89%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 h_01HKA1D1TW5W9A72V2NMPX932H=%E3%82%AA%E3%83%BC%E3%82%AC%E3%83%8B%E3%83%83%E3%82%AF%E6%A4%9C%E7%B4%A2%E3%81%AE%E3%82%AD%E3%83%BC%E3%83%AF%E3%83%BC%E3%83%89%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88" />
