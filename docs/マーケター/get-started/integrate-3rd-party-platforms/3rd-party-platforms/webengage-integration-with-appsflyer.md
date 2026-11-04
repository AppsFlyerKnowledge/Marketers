---
title: WebEngageとAppsFlyerの連携
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-07-25T13:44:42Z'
  edited_at: '2026-10-28T09:04:00Z'
  id: 7898288493841
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/7898288493841
---
> **概要：** AppsFlyerの連携済みパートナーであるWebEngageは、モバイルファーストの時代に向けて開発されたインテリジェントなマーケティングクラウドです。

<div id="important" />

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。 そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

<div id="setting-up-webengage" />

## WebEngageの設定

**前提条件：** パートナーのアカウントが必要です。アカウントがない場合は、連携を設定する前にパートナーに連絡し、アカウントを開設してください。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。  
   （**既存の連携を編集する場合：** ［**連携＞パートナー連携＞有効な連携**］タブに移動します。）
2. 対象のアプリを選択します。
3. パートナーを検索し、［**連携する**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。   
   注意：パートナーとの連携を利用している間は、**このトグルをオン（有効）にしておく必要があります**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳しく見る</Anchor>
5. 以下の説明に従い、該当するタブで設定を完了します。

WebEngageの設定で使用するのは、<strong>［連携］</strong>タブのみです。

詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">パートナーページのヘッダーの設定</Anchor>を参照してください。

<div id="integration-tab" />

<Accordion title="連携タブ">

［連携］タブは、以下のセクションで構成されています。

<div id="activate-partner" />

### パートナーを有効化

初回の設定時は、［**パートナーを有効化**］をオンにして、連携を設定できるようにします。このパートナーと連携している間は、オンにしておく必要があります。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">パートナーの有効化</Anchor>を参照してください。

<div id="general-settings" />

### 一般設定

WebEngageとAppsFlyerの接続には、APIキーとWebEngageのデータセンターのリージョンを使用します。

* **api\_key：** APIキーを入力します。取得するには、WebEngageアカウントにログインし、<Anchor target="_blank" href="https://docs.webengage.com/docs/appsflyer#step-3-add-webengage-api-key--data-center-region">手順</Anchor>に従ってください。
* **Region：** データを保管するリージョンを入力します。米国のデータセンターは**US**、インドのデータセンターは**IN**です。デフォルトでは、すべてのデータを米国のデータセンターに保存します。

![web_mo_engage_general_settings_en-us.png](https://files.readme.io/1297a02a9e280b238a222b14972dc657acffe4566dc49d607178ea43fdc01a77-8089123842705.png) 

<div id="default-postbacks" />

### デフォルトポストバック

AppsFlyerは、インストールやリエンゲージメントの発生時に、WebEngageへポストバックを自動送信できます。

* **オフ**：インストールポストバックを送信しません。
* **オーガニックを含むすべてのメディアソース**：すべてのパートナーの成果として計測されたイベントと、オーガニックのイベントのポストバックを送信します。

![web_mo_engage_default_postbacks_en-us.png](https://files.readme.io/9be309d681904a015fc0295b2ee463411f5c8fbaf450145b132e8ab37bda7665-17028057319697.png)

<div id="note" />

> 📘 **注意**
>
> すべてのインストールを受信するネットワークであるWebEngageは、オーガニックを含むすべての流入元からの新規インストールのポストバックを受信することを推奨しています。 WebEngageは、<strong>［オーガニックを含むすべてのメディアソース］</strong>の選択を推奨しています。

<div id="in-app-event-settings" />

### アプリ内イベントの設定

ポストバックを使用して、AppsFlyerのイベントをWebEngageのイベントに対応付けます。ポストバック送信を有効にしている場合は、拒否されたアプリ内イベントも含まれます。これには、Protect360でブロックされたイベントと、ターゲット検証ルールで不適合と判定されたイベントが該当します。

<div id="to-configure-in-app-event-postbacks" />

#### アプリ内イベントポストバックを設定するには、以下の手順を実施します。

1. **api\_key**と**Region**を入力します。
2. <strong>［アプリ内イベントポストバック］</strong>を有効にします。
3. <strong>［イベントを追加］</strong>をクリックし、SDKまたはサーバー間イベントをリストに追加します。
4. 必要なパラメータを設定します。
5. ［任意］<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />をクリックし、パートナーに特定のアプリ内イベントを送信する条件を設定します。  
   <Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">条件付きアプリ内イベントポストバック</Anchor>の詳細を確認してください。

| パラメータ名 | 説明 |
| --- | --- |
| **AppsFlyerイベント** | アプリに組み込んだSDK、またはサーバー間イベントからAppsFlyerが受信したイベント名です。<br />**ヒント**：目的のイベントが表示されない場合は、<ul><li>非オーガニックインストールのデバイスで対象イベントを発生させてから、もう一度確認してください。</li><li>［**AppsFlyerイベント**］に名前を入力し、［**カスタムイベントを作成**］をクリックします。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">カスタムイベントのマッピング</Anchor>を参照してください。</li></ul> |
| **対象ユーザーの流入元** | イベントの送信対象を選択します。<ul><li>**このパートナーのみ**：このパートナーの成果として計測されたイベントのみ、ポストバックを送信します。</li><li>**オーガニックを含むすべてのメディアソース**：オーガニックを含む、すべてのパートナーのイベントのポストバックを送信します。</li></ul> |
| **送信するデータ** | <ul><li>**データなし（デフォルト）**：イベント値を含めず、イベントそのものだけを送信します。</li><li>**値と収益を送信する**：収益値を**含む**すべてのイベントパラメータを送信します（イベントに収益値がある場合）。</li><li>**値のみ送信し、収益は送信しない**：収益値を**除く**すべてのパラメータを送信します。</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

このパートナーとの連携では、［**計測リンク**］は利用できません。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

このパートナーとの連携では、［**コストデータ**］は利用できません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

このパートナーとの連携では、［**広告収益**］は利用できません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

このパートナーとの連携では、［**権限**］は利用できません。

</Accordion>

<div data-zendesk-anchors="h_01H9HWK7APBFK7RWVFH79VW0ME=%E9%87%8D%E8%A6%81 setting-up-webengage=webengage%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWK7AP6Z398NP3G2BQQBTF=webengage%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWK7AP3ERT0TM39E6S5M79=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9HWK7AP3FMR5RMANZCMQ6M0=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9HWK7APG1STZ4Q19QVX4KRY=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9HWK7AP23GK6WWJTB543FEQ=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9HWK7APMBSZ1PG8MK88HZFS=%E6%B3%A8%E6%84%8F inapp-event-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWK7APFNAFE9YM2484DDHD=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A to-configure-inapp-event-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF%E4%BB%A5%E4%B8%8B%E3%81%AE%E6%89%8B%E9%A0%86%E3%82%92%E5%AE%9F%E6%96%BD%E3%81%97%E3%81%BE%E3%81%99 h_01H9HWK7APZM8328V0EV4B5QDN=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF%E4%BB%A5%E4%B8%8B%E3%81%AE%E6%89%8B%E9%A0%86%E3%82%92%E5%AE%9F%E6%96%BD%E3%81%97%E3%81%BE%E3%81%99 h_01H9HWK7AQTZXE7GPX5E9X2ZYN=attribution-link-tab h_01H9HWK7AQ8SXED5KHVD5T4DZZ=cost-tab h_01H9HWK7AQ2JG4BRS784M85Z6E=ad-revenue-tab h_01H9HWK7AQ5YJDY2M96CA05H6P=permissions-tab" />
