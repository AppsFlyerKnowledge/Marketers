---
title: SpoteffectsとAppsFlyerの連携
metadata:
  keywords:
    - Advertisers
    - Webeffects
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2017-09-06T14:38:15Z'
  edited_at: '2026-10-28T09:03:49Z'
  id: 115004574426
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/115004574426
---
> **概要：** AppsFlyerの連携済みパートナーであるSpoteffectsは、SaaSソリューションを開発・提供しています。メディアプランナーは、広告の放映直後に発生した訪問数とコンバージョン数に基づいて、オンラインショップやWebサイトのテレビ広告キャンペーンを最適化できます。

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。 そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

## Spoteffectsの設定

**前提条件：** パートナーのアカウントが必要です。アカウントがない場合は、連携を設定する前にパートナーに連絡し、アカウントを開設してください。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。  
   （**既存の連携を編集する場合：** ［**連携＞パートナー連携＞有効な連携**］タブに移動します。）
2. 対象のアプリを選択します。
3. パートナーを検索し、［**連携する**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。   
   注意：パートナーとの連携を利用している間は、**このトグルをオン（有効）にしておく必要があります**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳しく見る</Anchor>
5. 以下の説明に従い、該当するタブで設定を完了します。

Spoteffectsの設定で使用するのは、<strong><em>［連携］</em></strong>タブのみです。

パートナー設定画面のヘッダーについて詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>を参照してください。

<div id="integration-tab" />

<Accordion title="連携タブ">

［連携］タブは、以下のセクションで構成されています。

### パートナーを有効化

**初めてこの画面を開いたとき**は、下にあるトグルをオンにする必要があります。［***パートナーを有効化***］をオンにすると、［連携］タブのパラメータを設定できるようになります。パートナーとの連携を利用している間は、このトグルをオンにしておく必要があります。  
パートナーの有効化について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>を参照してください。

### デフォルトポストバック

AppsFlyerは、ユーザーのインストール後にSpoteffectsへポストバックを自動送信できます。このセクションで、ポストバックの送信を設定します。

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

アプリをダウンロードしたすべてのユーザーのポストバックをSpoteffectsに送信するには、<strong>［すべてのパートナーまたはオーガニックのイベント］</strong>を選択します。送信しない場合は、<strong>［オフ］</strong>を選択します。

［**保存**］をクリックします。

### アプリ内イベントの設定

[![](https://files.readme.io/97da1d47ab9bfa3855d18dcd60f3a263b8a631c477b354dc32486170b7708e96-360002201165.png)](https://files.readme.io/97da1d47ab9bfa3855d18dcd60f3a263b8a631c477b354dc32486170b7708e96-360002201165.png)

このセクションでは、ポストバックを介してAppsFlyerのイベントをSpoteffectsのイベントに対応付けます。

1. ［アプリ内イベントポストバック］をオンにします。
2. SDKで定義されたすべてのイベントについて、送信対象を選択します。  
   **- このパートナーのイベントのみ**：このパートナーの成果として計測されたユーザーのイベント**のみ**を送信します。  
   **- すべてのパートナーまたはオーガニックのイベント**：すべてのユーザーのデータをパートナーに送信できます。
3. ［**イベントを追加**］をクリックし、SDKイベントをリストに追加します。
4. 以下のパラメータを設定します。

| パラメータ名 | 説明 |
| --- | --- |
| **SDKイベント名** | アプリに実装したSDKまたはサーバー間（S2S）イベントからAppsFlyerが受信したイベント名です。  <br />**ヒント**：リストに目的のイベントがない場合は、非オーガニックでインストールしたデバイスでそのイベントを発生させ、もう一度確認してください。 |
| **パートナーイベント識別子** | Spoteffect側で定義されている各イベントの一意の名前またはIDです。  <br />Spoteffectから対応するイベントIDを取得し、テキストフィールドに入力します。 |
| **収益を送信** | **オフの場合**：**af\_revenue**で指定した収益値を除き、リッチアプリ内イベントのすべてのパラメータをパートナーに送信します。  <br />**オンの場合**：収益値を含むすべてのパラメータを送信します（イベントに収益値がある場合）。 |

［**保存**］をクリックします。

設定を保存すると、AppsFlyerは、オーガニックと非オーガニックの各インストールについて、以下のデータをSpoteffectsに送信します。

* デバイスID（IDFA／Google広告ID）
* メディアソース
* キャンペーン名

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

Spoteffectsでは、計測リンクは利用できません。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

このパートナーとの連携では、コストデータには対応していません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

このパートナーとの連携では、広告収益データには対応していません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

Spoteffectsでは、権限の設定は利用できません。

</Accordion>

<div data-zendesk-anchors="h_01H9HWJYD7AZTFXKESY1KHW52S=%E9%87%8D%E8%A6%81 setting-up-spoteffects=spoteffects%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWJYD75MTKJBMSZRFAG66Q=spoteffects%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWJYD7MAWK9S226YWPZJ8G=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9HWJYD7X6KEFF3VEZEP4PGM=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9HWJYD7PW2TCYJRA815YNQE=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-event-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWJYD7SK47G91GF9J9Q2ZB=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWJYD8RJM9BDX9RKSCC4RY=attribution-link-tab h_01H9HWJYD81VXJPT5D2TKQQN9C=cost-tab h_01H9HWJYD8XBV0V0KDNY955JCT=ad-revenue-tab h_01H9HWJYD8B9AQMVVMT16EH602=permissions-tab" />
