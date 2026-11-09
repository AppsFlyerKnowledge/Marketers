---
title: RockerboxとAppsFlyerの連携
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
  created_at: '2020-11-23T14:55:00Z'
  edited_at: '2026-10-28T09:03:41Z'
  id: 360015760757
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/360015760757
---
> **概要：** AppsFlyerのデータを、モバイルアプリとWebアプリ向けのマーケティング・分析プラットフォームであるRockerboxに自動共有する方法を説明します。

<Image align="center" alt="rockerbox-logo_en-us.png" src="https://cdn.appsflyer.com/marketplace/static/logo/rockerbox.png" />

<div id="important" />

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。 そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

<div id="setting-up-rockerbox" />

## Rockerboxの設定

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

**RockerboxアカウントID**

**RockerboxアカウントをAppsFlyerに接続するには、Rockerbox account ID**にアカウントIDを入力します。   
RockerboxのアカウントIDは、Rockerboxの**Settings**＞**Account**＞**General**で確認できます。

<div id="default-postbacks" />

### デフォルトポストバック

AppsFlyerは、ユーザーのインストール後にRockerboxへポストバックを自動送信できます。このセクションでは、イベントごとに、ポストバック送信の対象とするユーザーの流入元を設定します。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#default-postbacks">デフォルトポストバック</Anchor>を参照してください。

アプリをダウンロードしたすべてのユーザーのポストバックをRockerboxに送信するには、<strong>［オーガニックを含むすべてのメディアソース］</strong>を選択します。

<div id="in-app-events-settings" />

### アプリ内イベントの設定

<Image align="center" alt="rockerbox-in-app-events_en-us.png" src="https://files.readme.io/3fc74bb16d6a1222d1d244bbb1083ff247e3315d0fc7060e0ec3e8ad30a07233-360013891517.png" />

このセクションでは、ポストバックを介してAppsFlyerのイベントをパートナーのイベントに対応付けます。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">アプリ内イベントポストバック</Anchor>を参照してください。

**アプリ内イベントポストバックを設定するには、以下の手順を実施します。**

1. **RockerboxアカウントID**を入力します。
2. ［**アプリ内イベントポストバック**］を有効にします。
3. ［**イベントを追加**］をクリックし、SDKイベントをリストに追加します。
4. ドロップダウンメニューから［**SDKイベント名**］を選択します。
5. ［収益の送信］のドロップダウンメニューから、送信するデータを選択します。
   * **値も収益も送信しない：** イベント値を含めず、イベント自体のみを送信します。
   * **値のみ送信し、収益は送信しない：** 収益値を除くすべてのパラメータを送信します。
   * **値と収益を送信する**：収益値を含むすべてのイベントパラメータを送信します（イベントに収益値がある場合）。
6. ［**連携を保存**］をクリックして、連携の設定を完了します。

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

<div data-zendesk-anchors="h_01H9HWJW82HZ9FR31VHHRBZ3EM=%E9%87%8D%E8%A6%81 setting-up-rockerbox=rockerbox%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWJW83BKP8DSYTV6YGPHK7=rockerbox%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWJW83WDGQKKMM942NPA1S=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9HWJW83Z4NGT000091AHX0Z=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9HWJW832NQBPK2VS6TS1QK7=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9HWJW83CGMBADDBP7EJTR9N=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-events-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWJW84H4SDVRNZAG1D6N0D=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWJW84G6GXMBTGMHTDPM6R=attribution-link-tab h_01H9HWJW84BZNHN4DRKA33WCVK=cost-tab h_01H9HWJW848DRTKBF3AKR5KYC5=ad-revenue-tab h_01H9HWJW84NTZWKP2FP2WK4FZD=permissions-tab" />
