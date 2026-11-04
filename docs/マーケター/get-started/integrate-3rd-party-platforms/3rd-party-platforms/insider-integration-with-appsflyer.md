---
title: InsiderとAppsFlyerの連携
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
  created_at: '2021-01-03T11:23:45Z'
  edited_at: '2026-10-28T09:03:10Z'
  id: 360016827838
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/360016827838
---
> **概要：** AppsFlyerの連携済みパートナーであるInsiderは、モバイルアプリとWebアプリ向けのマーケティング・分析プラットフォームです。 Insiderは、Web、モバイルWeb、モバイルアプリ、広告の各チャネルで、リアルタイムの予測に基づくセグメント分けとパーソナライズを実現します。

![rockerbox-logo_en-us.png](https://cdn.appsflyer.com/marketplace/static/logo/useinsider.png?v=1)

<div id="important" />

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。 そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

<div id="setting-up-insider" />

## Insiderの設定

**前提条件：** パートナーのアカウントが必要です。アカウントがない場合は、連携を設定する前にパートナーに連絡し、アカウントを開設してください。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。  
   （**既存の連携を編集する場合：** ［**連携＞パートナー連携＞有効な連携**］タブに移動します。）
2. 対象のアプリを選択します。
3. パートナーを検索し、［**連携する**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。   
   注意：パートナーとの連携を利用している間は、**このトグルをオン（有効）にしておく必要があります**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳しく見る</Anchor>
5. 以下の説明に従い、該当するタブで設定を完了します。

<div id="integration-tab" />

<Accordion title="連携タブ">

［連携］タブは、以下のセクションで構成されています。

<div id="activate-partner" />

### パートナーを有効化

パートナーとの連携を利用している間は、このトグルを有効にしておく必要があります。  
詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation#パートナー統合を有効にする">パートナーの有効化</Anchor>を参照してください。

<div id="general-settings" />

### 一般設定

InsiderとAppsFlyerの接続には、固有のパートナー識別子を使用します。

**識別子を取得するには、Insider**にログインし、管理画面の右上にある識別子をコピーします。

![insider-partner-ID_en-us.png](https://files.readme.io/5755dcc63db5714eb651c74b89e24bee769f792190d9aad0bfc0a742d321eb47-360015601658.png)

<div id="default-postbacks" />

### デフォルトポストバック

AppsFlyerは、ユーザーのインストール後にInsiderへポストバックを自動送信できます。このセクションでは、イベントごとに、ポストバック送信の対象とするユーザーの流入元を設定します。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#default-postbacks">デフォルトポストバック</Anchor>を参照してください。

**アプリをダウンロードしたすべてのユーザーのポストバックをInsiderに送信するには**、<strong>［オーガニックを含むすべてのメディアソース］</strong>を選択します。

<div id="in-app-events-settings" />

### アプリ内イベントの設定

![insider-partner-field.png](https://files.readme.io/ad4b4a5e9d688be93b20ccf645c779c361390cc95e2a2acbab7299408b7478bf-4403354160785.png)

このセクションでは、ポストバックを介してAppsFlyerのイベントをパートナーのイベントに対応付けます。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">アプリ内イベントポストバック</Anchor>を参照してください。

**アプリ内イベントポストバックを設定するには、以下の手順を実施します。**

1. **Insider**管理画面の右上にある**Insider partner**を入力します。

   ![insider-partner-ID_en-us.png](https://files.readme.io/5755dcc63db5714eb651c74b89e24bee769f792190d9aad0bfc0a742d321eb47-360015601658.png)
2. AppsFlyerで<strong>［アプリ内イベントポストバック］</strong>を有効にします。
3. ［**イベントを追加**］をクリックし、SDKイベントをリストに追加します。
4. ドロップダウンメニューから［**SDKイベント名**］を選択します。
5. <strong>［パートナーイベント識別子］</strong>を入力します。
6. <strong>［送信オプション］</strong>を選択します。
7. ［収益の送信］のドロップダウンメニューから、送信するデータを選択します。
   * **値も収益も送信しない：** イベント値を含めず、イベント自体のみを送信します。
   * **値のみ送信し、収益は送信しない：** 収益値を除くすべてのパラメータを送信します。
   * **値と収益を送信する**：収益値を含むすべてのイベントパラメータを送信します（イベントに収益値がある場合）。
8. ［**連携を保存**］をクリックして、連携の設定を完了します。

<div id="note" />

> 📘 **注意**
>
> ポストバックを有効にするには、InsiderIDをCUIDに設定します。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

このパートナーでは、計測リンクは利用できません。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

このパートナーとの連携では、コストデータは利用できません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

このパートナーとの連携では、広告収益は利用できません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

このパートナーでは、権限の設定は利用できません。

</Accordion>

<div data-zendesk-anchors="h_01H9FK8YZMFS4XHX69CG90A18K=%E9%87%8D%E8%A6%81 setting-up-insider=insider%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK8YZM63N7HF514RVFPMJY=insider%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK8YZN7D4R6TBABMDB3K3K=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9FK8YZNMN9QBRS33WPZQWPB=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9FK8YZNAFP5G2B277YPNY68=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FK8YZNZWSD64K3R2TVHCE2=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-events-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK8YZN15KPHHA58XRABRD4=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01K88DMNP3SKDE93SXGXJXTE0C=%E6%B3%A8%E6%84%8F h_01H9FK8YZNJ86KQT59H9RD5CJA=attribution-link-tab h_01H9FK8YZN99ZBQQFBZF26HJZJ=cost-tab h_01H9FK8YZNAJ1XW7TSQWT7PYPW=ad-revenue-tab h_01H9FK8YZQTKN1SFMN9M0CKVYM=permissions-tab" />
