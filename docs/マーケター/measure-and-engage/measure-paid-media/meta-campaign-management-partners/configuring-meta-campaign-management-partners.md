---
title: Metaキャンペーン管理パートナーの設定
metadata:
  keywords:
    - Facebook
    - FMP
    - Advertisers
    - Partners
    - facebook marketing partner
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2018-03-18T12:43:51Z'
  edited_at: '2026-10-14T09:32:20Z'
  id: 360000562569
  locale: ja
  section: Meta campaign management partners
  section_id: 6551188365457
  url: https://support.appsflyer.com/hc/ja/articles/360000562569
---
> **概要：** Kenshoo、Bidalgo、SmartlyなどMetaキャンペーン管理パートナー(旧称:Facebookマーケティングパートナー) を使用したMeta広告キャンペーンを最適化します。設定すると、AppsFlyerはポストバックを送信します。

<div id="configure-meta-campaign-management-partners" />

## 構成 Metaキャンペーン管理パートナー

**前提条件:** **連携を設定する前に、必ず<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーに連絡して</Anchor>アカウントを開設してください。**

**連携を有効化または編集する方法：**

1. **有効にする：** AppsFlyer管理画面左メニュー **コラボレーション** > **Partner Marketplace**を選択します。  
   **編集方法**：AppsFlyer管理画面左メニュー **コラボレーション** > **連携を有効にする**を選択します。
2. パートナーを検索し選択してください。
3. **連携設定** をクリックして、連携設定ページに移動します。
4. **連携**タブで、連携アプリを選択し、**パートナーの有効化**をオンにします。  
   **注意：** トグルは、パートナーと作業している間、オン<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">（有効）</Anchor>にしておく必要があります。
5. 以下の手順に従い、各タブの設定を完了してください。

<div id="in-app-event-postback-setup" />

## アプリ内イベントのポストバック設定

**前提条件：**

パートナーがポストバックを取得するために、キャンペーン名には**必ず**先頭にMetaキャンペーン管理パートナー名が付きます。たとえば、Metaキャンペーン管理パートナー名が *Mcmpexample* で、セグメントが *Young\_Segment* の場合、キャンペーン名を *mcmpexample\_Young\_Segment*を設定します。  
**注記：** Metaキャンペーン管理パートナー名は **大文字と小文字が区別されます。**

**アプリ内イベントのポストバックを設定します**:

[![in-app_event_mapping.png](https://files.readme.io/ced254c1aa0ad454c1876cfc0bc85de20d275824efb34c9665ca144dabffaa2a-14050539243793.png)](https://files.readme.io/ced254c1aa0ad454c1876cfc0bc85de20d275824efb34c9665ca144dabffaa2a-14050539243793.png)

1. **アプリ内イベントポストバック**を有効にします。
2. <Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#マッピング方法">マッピング方法</Anchor>に従って必要なパラメーターを全て入力してください。  
   

| パラメーター名 | 説明 |
| --- | --- |
| <span id="appsflyer-event"></span>**AppsFlyerイベント** | これは、アプリに連携されたSDKまたはサーバー間イベントからAppsFlyerが受信したイベントの名前です。<br />**ヒント**:探しているイベントが見つかりませんか？<ul><li>必ず、非オーガニックインストールのデバイスでイベントを起動して、再確認してください。</li><li>**AppsFlyerイベント**にイベントを入力し、**カスタムイベントを作成**をクリックしてください。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">カスタムイベントマッピングの詳細をお読みください。</Anchor></li></ul> |
| <span id="mapped-to-partner-event"></span>**パートナー側のイベント名** | パートナー側で設定された各イベントの一意の名前またはID。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#マッピング方法">可能なマッピング構成</Anchor>は次のとおりです。<ul><li>**テキストフィールド:** 対応するイベントIDをパートナーから取得します。</li><li>**ドロップダウンボックス:** 最も適切な事前定義されたパートナーイベントを選択します。</li><li>**そのまま**:イベント名をマッピングせずに、イベントをそのまま送信します。</li></ul> |
| <span id="for-users-from"></span>**ユーザー元** | イベントの送信オプションを選択します。<ul><li>**このパートナーのみ**:イベントがこのパートナーに起因する場合、つまりイベントを実行したユーザーがこのパートナーから来た場合にのみポストバックを送信します。</li><li>**オーガニックを含む全メディアソース**:あらゆるパートナーに起因するイベントやオーガニックイベント、つまり実行したユーザーが任意のメディアソースから来た場合にポストバックを送信します。</li></ul> |
| <span id="including"></span>**を含む** | ポストバックでパートナーと共有する<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#ポストバックに含めるデータ">イベントデータ</Anchor>を選択します。<ul><li>**値も収益もない**:パラメーター（値または収益）なしでイベント自体のみを送信します。</li><li>**値有りで収益なし**:収益値**以外**のすべてのパラメーターを送信します。</li><li>**Values & revenue（値も収益も送信する）**：収益の額を**含む**（存在する場合）、すべてのイベント値を送信します。</li></ul> |

3. [オプション] ![conditional-iae-postbacks-icon.png](https://files.readme.io/5345c5ebe95b3f1a0d0858b88ce29f9965178ce750df86c04cb131a93d006a5e-14050481317393.png) をクリックして特定のアプリ内イベントをパートナーに送信するための<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">条件を設定</Anchor> します。
4. [オプション] **イベントを追加** をクリックして、別の SDK またはサーバー間イベントをリストに追加します。
5. **連携を保存** をクリックします。

<div id="important-notes" />

> 📘 **重要！**
>
> * Meta広告のアトリビューションを無効にすると、Metaのキャンペーン管理パートナーにポストバックが送信されなくなります
> * Metaキャンペーン管理パートナーとのアプリ内イベントのマッピングの有無にかかわらず、広告主のアカウントから直接Meta広告にアプリ内イベントを送信することには影響しません。
> * アプリ内イベントのマッピングには、Metaキャンペーン管理パートナーによって異なる設定パラメーターが必要になる場合があります。
> * Meta広告とX Adsのキャンペーン名は、AppsFlyerプラットフォームで定義されているMetaキャンペーン管理パートナーアカウント名で始まり、その後にアンダースコア「\_」が続く必要があります。前述の名前が付いていないキャンペーンは、広告主には表示されますが、Metaキャンペーン管理パートナーには表示されません。Metaキャンペーン管理パートナー名は **大文字と小文字を区別します**。

<div data-zendesk-anchors="configuring-facebook-marketing-partners=%E6%A7%8B%E6%88%90-meta%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E7%AE%A1%E7%90%86%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC h_01HGFQCBT217ZV0R6E2YHTV88N=%E6%A7%8B%E6%88%90-meta%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E7%AE%A1%E7%90%86%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC inapp-event-postback-setup=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E8%A8%AD%E5%AE%9A h_01HGFQCBT3R7HH8M5SQJK1EPSP=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E8%A8%AD%E5%AE%9A h_01HGFQCBT3HGZVFHCC1S04MVQW=%E9%87%8D%E8%A6%81" />
