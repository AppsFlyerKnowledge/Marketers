---
title: MoEngageキャンペーンの設定
metadata:
  keywords:
    - MoEngage
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
  created_at: '2017-06-25T07:50:18Z'
  edited_at: '2026-10-28T09:03:33Z'
  id: 115003139643
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/115003139643
---
> **概要：** AppsFlyerと連携するサードパーティプラットフォームのMoEngageは、モバイルファーストの時代に向けて開発された、AIエージェントを活用した顧客エンゲージメントプラットフォームです。

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。 そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

## MoEngageの設定

**前提条件：** パートナーのアカウントが必要です。アカウントがない場合は、連携を設定する前にパートナーに連絡し、アカウントを開設してください。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。  
   （**既存の連携を編集する場合：** ［**連携＞パートナー連携＞有効な連携**］タブに移動します。）
2. 対象のアプリを選択します。
3. パートナーを検索し、［**連携する**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。   
   注意：パートナーとの連携を利用している間は、**このトグルをオン（有効）にしておく必要があります**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳しく見る</Anchor>
5. 以下の説明に従い、該当するタブで設定を完了します。

詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">パートナーページのヘッダーの設定</Anchor>を参照してください。

<div id="integration-tab" />

<Accordion title="連携タブ">

<strong>［連携］</strong>タブは、以下のセクションで構成されています。

### パートナーを有効化

初回の設定時は、［**パートナーを有効化**］をオンにして、連携を設定できるようにします。このパートナーと連携している間は、オンにしておく必要があります。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">パートナーの有効化</Anchor>を参照してください。

### 一般設定

MoEngageとAppsFlyerの接続には、固有のApp ID、App Key、およびMoEngageのデータセンターを使用します。 App IDとApp Keyをまだ取得していない場合は、連携の設定を進める前に取得してください。

* **APP\_ID：** アプリIDを入力します。取得するには、MoEngageアカウントにログインし、左側のメニューから**Settings**＞**App Settings**に移動します。
* **MoEngage Data Center：** 登録したMoEngageのデータセンターを指定します。 <Anchor target="_blank" href="https://help.moengage.com/hc/en-us/articles/360057030512-Data-Centers-in-MoEngage">MoEngageのデータセンター</Anchor>の詳細を確認してください。
* **APP\_KEY：** アプリのAPIキーを入力します。取得するには、MoEngageアカウントにログインし、**Settings**＞**Analytics**に移動します。

![moengage_general_settings_en-us.png](https://files.readme.io/0180fb4ad22857320200b1f53a01c72c87fc6cc4a3f4aabcd585b2cfb0f7596a-8179576817809.png)

### デフォルトポストバック

AppsFlyerは、ユーザーのインストール後にMoEngageへポストバックを自動送信できます。次のいずれかのオプションを選択します。

* **オフ**：インストールポストバックを送信しません。
* **オーガニックを含むすべてのメディアソース**：すべてのパートナーの成果として計測されたイベントと、オーガニックのイベントのポストバックを送信します。

![web_mo_engage_default_postbacks_en-us.png](https://files.readme.io/9be309d681904a015fc0295b2ee463411f5c8fbaf450145b132e8ab37bda7665-17028057319697.png)

> 📘 **注意**
>
> すべてのインストールを受信するネットワークであるMoEngageは、オーガニックを含むすべての流入元からの新規インストールのポストバックを受信することを推奨しています。 MoEngageは、<strong>［オーガニックを含むすべてのメディアソース］</strong>の選択を推奨しています。

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

<div data-zendesk-anchors="h_01H9HWJPMX1TXBZY6C94HQ7J85=%E9%87%8D%E8%A6%81 setting-up-moengage=moengage%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWJPMXN58VV9SQQPY4T5HZ=moengage%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWJPMX946NS52DTPAZWVEK=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9HWJPMX46NV79HHGRRD6D56=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9HWJPMXPZ5QV9D08CJMHMHS=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9HWJPMX0TZ496PP8EY3H336=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9HWJPMX4CHJ9MADEQBSDMGY=%E6%B3%A8%E6%84%8F h_01H9HWJPMXJVWPK67W5X88GYHZ=attribution-link-tab h_01H9HWJPMXQ07XNN8Y79P5DCAN=cost-tab h_01H9HWJPMX8MC1GSD2VD3QQ82Y=ad-revenue-tab h_01H9HWJPMXKYXVCH3HRA2FCPSQ=permissions-tab" />
