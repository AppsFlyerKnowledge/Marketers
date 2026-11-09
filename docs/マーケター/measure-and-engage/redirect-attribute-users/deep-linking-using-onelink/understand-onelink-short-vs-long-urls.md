---
title: OneLink｜ショートURLとロングURLの違い
metadata:
  keywords:
    - Marketers
    - parameters
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2021-01-26T09:39:19Z'
  edited_at: '2026-10-28T09:18:51Z'
  id: 360017132597
  locale: ja
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ja/articles/360017132597
---
> **概要：** OneLinkのショートURLとロングURLの違い、およびAppsFlyer以外でロングURLを作成する方法を説明します。

<div id="about-onelink-links" />

## **OneLinkリンクについて**

* あらゆるマーケティングチャネルで利用でき、ユーザーを次のいずれかへ誘導します。 
  * 適切なURLまたはアプリストアへリダイレクトします。
  * アプリを開き、さらにディープリンクでアプリ内の特定の操作へ誘導します。
* 自社ブランドに合わせたカスタマイズが可能です。つまり、URLにOneLinkのサブドメインではなく、自社の<Anchor target="_blank" href="/marketers/ja/docs/brand-onelink-with-your-domain">ブランドドメイン</Anchor>を使用できます。
* ショートURLとロングURLのいずれも使用できます。
  * ショートURLは、AppsFlyerで作成します（<Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">UI</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/user-invite-attribution">SDK</Anchor>のいずれかを使用）。
  * ロングURL：
    * AppsFlyerのUIでも、AppsFlyer以外でも作成できます。
    * 任意のパラメータを含められます。
    * スプレッドシートで独自の簡単な数式を使用し、多数のOneLinkカスタムリンクを生成できます。   
      **注意**：
      * スプレッドシートで作成したリンクは、AppsFlyerのどのUIにも表示されず、編集もできません。
      * このスプレッドシートを使う方法は、ショートURLを一括作成する<Anchor target="_blank" href="/marketers/ja/docs/perform-onelink-bulk-actions-via-csv">OneLink｜CSVによるリンクの一括操作</Anchor>とは異なります。
    * 有効期限はなく、有効期間（TTL）による制限もありません。  
      **ロングURLに関する注意事項：**
    * ロングURLはすべてのリンクパラメータが外部から見えるため、改ざんされる可能性があります。
    * ブラウザ、SMSなど、URLの文字数に制限がある場所では、ロングURLが上限を超える場合があります。

<div id="advantages-of-a-short-onelink-url-compared-to-a-long-url" />

### ロングURLと比較したOneLinkショートURLのメリット

* AppsFlyer管理画面でOneLinkショートURLのパラメータを更新しても、ショートリンクIDは変わりません。そのため、URLや関連するQRコードをすでに使用している場合でも、差し替えや再配布は不要です。
* 更新したパラメータは、AppsFlyerのアトリビューションとレポートにそのまま適用されます。QRコードは引き続き機能し、変更内容が自動的に反映されます。

<div id="procedures" />

## 手順

**AppsFlyerのUI以外でOneLinkのロングURLを作成するには：**

1. <Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレート</Anchor>を作成します。
2. OneLinkテンプレートのドメインとテンプレートIDを組み合わせた、OneLinkのベースURLを控えます。  
   例：
   * OneLinkテンプレートのドメイン：`yourbrand.onelink.me`
   * テンプレートID：`1a6f`
   * OneLinkのベースURL：`yourbrand.onelink.me/1a6f`
   * ブランドドメインの例：`yourbrand.com/1a6f`
3. `?`を URLの末尾に追加し、その後に必要なパラメータを指定します。
   * <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">AppsFlyerのパラメータ一覧</Anchor>を参照してください。
   * 複数のパラメータを追加する場合は、`&`で区切ります。  
     例：`yourbrand.onelink.me/1a6f?pid=email&c=freestuff`

**AppsFlyerのUIで作成したOneLinkカスタムリンクのロングURLを取得するには：**

1. AppsFlyerで［**OneLinkカスタムリンク**］に移動します。  
   OneLinkの一覧が表示されます。  
   <Image align="center" alt="" src="https://files.readme.io/53bd68c390389e48eb55802418c601e7523ab7d816d21c1ae672ed55d7ade365-360016243798.jpg" />
2. ロングURLを取得するリンクの［**アクション**］列で、［**URLを取得**］をクリックします。  
   ロングURLが表示されます。

<div data-zendesk-anchors="onelink-long-urls=onelink%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 01JBXQENR6QHQ1HXQQQ5NBBMKN=onelink%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 advantages-of-a-short-onelink-url-compared-to-a-long-url=%E3%83%AD%E3%83%B3%E3%82%B0url%E3%81%A8%E6%AF%94%E8%BC%83%E3%81%97%E3%81%9Fonelink%E3%82%B7%E3%83%A7%E3%83%BC%E3%83%88url%E3%81%AE%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 h_01JGXTFWS509NW0ESM1CZZ1KZM=%E3%83%AD%E3%83%B3%E3%82%B0url%E3%81%A8%E6%AF%94%E8%BC%83%E3%81%97%E3%81%9Fonelink%E3%82%B7%E3%83%A7%E3%83%BC%E3%83%88url%E3%81%AE%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 procedures=%E6%89%8B%E9%A0%86 h_01JBXQTQ3DXPTP9BY06QKXN3NP=%E6%89%8B%E9%A0%86" />
