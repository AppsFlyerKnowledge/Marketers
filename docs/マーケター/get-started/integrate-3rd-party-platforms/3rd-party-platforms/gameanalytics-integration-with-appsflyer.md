---
title: GameAnalyticsとAppsFlyerの連携
metadata:
  keywords:
    - GameAnalytics
    - integrated partner
    - Advertisers
    - Ad Networks
    - game
    - game analytics
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
  created_at: '2015-12-24T11:42:56Z'
  edited_at: '2026-10-28T09:03:04Z'
  id: 207447143
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/207447143
---
> **概要：** AppsFlyerの連携済みパートナーであるGame Analyticsは、プレイヤーの行動を把握し、エンゲージメントの向上、離脱の抑制、収益化の改善に役立つ、開発者向けの高機能な無料ツールです。ゲームの主要KPIを1つの画面で確認でき、14,000以上の類似タイトルと指標を比較するベンチマーク機能も備えています。

設定は数分で完了し、利用は完全無料です。利用量の上限や、追加料金が必要な隠れた機能もありません。ゲームに導入する前に機能を試したい場合は、登録するだけで、データがあらかじめ用意されたデモゲームを確認できます。

個人開発者から世界的に有名なスタジオまで、世界中の40,000以上のゲーム開発者に利用され、20億台以上のデバイスで発生する、1日50億件以上のユニークイベントを処理しています。 GameAnalyticsは、主要なゲームエンジンとプラットフォーム向けのSDKを提供し、幅広い連携に対応しています。 https://gameanalytics.com/ で無料登録できます。

<div id="important" />

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

<div id="setting-up-gameanalytics" />

## GameAnalyticsの設定

**前提条件：** パートナーのアカウントが必要です。アカウントがない場合は、連携を設定する前にパートナーに連絡し、アカウントを開設してください。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。  
   （**既存の連携を編集する場合：** ［**連携＞パートナー連携＞有効な連携**］タブに移動します。）
2. 対象のアプリを選択します。
3. パートナーを検索し、［**連携する**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。   
   注意：パートナーとの連携を利用している間は、**このトグルをオン（有効）にしておく必要があります**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳しく見る</Anchor>
5. 以下の説明に従い、該当するタブで設定を完了します。

Game Analyticsの設定で使用するのは、<strong><em>［連携］</em></strong>タブのみです。

<div id="integration-tab" />

<Accordion title="連携タブ">

［連携］タブは、以下のセクションで構成されています。

<div id="activate-partner" />

### パートナーを有効化

<strong>初めて設定する場合</strong>は、<strong><em>［パートナーを有効化］</em></strong>をオンにすると、［連携］タブのパラメータを設定できます。パートナーとの連携を利用している間は、このトグルをオンにしておく必要があります。  
パートナーの有効化について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>を参照してください。

<div id="general-settings" />

### 一般設定

**ゲームキー**

Game AnalyticsとAppsFlyerの接続には、固有のゲームキーを使用します。まだ取得していない場合は、連携の設定を進める前にGame Analyticsから取得してください。

![Game_Analytics_msc_new_2.png](https://files.readme.io/0c629a74c16d6d8a861ee3ec344de68516a6224e9d6f5afb4b7d89fe78baa49f-360002199865.png)

<div id="default-postbacks" />

### デフォルトポストバック

AppsFlyerは、ユーザーのインストール後にGame Analyticsへポストバックを自動送信できます。このセクションで、ポストバックの送信を設定します。

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

アプリをダウンロードしたすべてのユーザーのポストバックをGame Analyticsに送信するには、<strong>［すべてのパートナーまたはオーガニックのイベント］</strong>を選択します。送信しない場合は、<strong>［オフ］</strong>を選択します。

<div id="in-app-event-settings" />

### アプリ内イベントの設定

[![](https://files.readme.io/64dd102e95aacda70cb8c0cde471c5c31d6b744543089a2d00a1ab1640fbb1c3-360002219789.png)](https://files.readme.io/64dd102e95aacda70cb8c0cde471c5c31d6b744543089a2d00a1ab1640fbb1c3-360002219789.png)

このセクションでは、ポストバックを介してAppsFlyerのイベントをGame Analyticsのイベントに対応付けます。

1. ゲームキーを再度入力します。
2. ［アプリ内イベントポストバック］をオンにします。
3. SDKで定義されたすべてのイベントについて、送信対象を選択します。  
   **- このパートナーのイベントのみ**：このパートナーの成果として計測されたユーザーのイベント**のみ**を送信します。  
   **- すべてのパートナーまたはオーガニックのイベント**：すべてのユーザーのデータをパートナーに送信できます。
4. ［**イベントを追加**］をクリックし、SDKイベントをリストに追加します。
5. 以下のパラメータを設定します。

| パラメータ名 | 説明 |
| --- | --- |
| **SDKイベント名** | アプリに実装したSDKまたはサーバー間（S2S）イベントからAppsFlyerが受信したイベント名です。  <br />**ヒント**：リストに目的のイベントがない場合は、非オーガニックでインストールしたデバイスでそのイベントを発生させ、もう一度確認してください。 |
| **パートナーイベント識別子** | Game Analytics側で定義されている各イベントの一意の名前またはIDです。  <br />Game Analyticsから対応するイベントIDを取得し、テキストフィールドに入力します。 |
| **収益を送信** | **オフの場合**：**af\_revenue**で指定した収益値を除き、リッチアプリ内イベントのすべてのパラメータをパートナーに送信します。  <br />**オンの場合**：収益値を含むすべてのパラメータを送信します（イベントに収益値がある場合）。 |

［**保存**］をクリックします。

この設定を保存すると、AppsFlyerはすべての非オーガニックインストールについて、次のデータをGame Analyticsに送信し始めます。

* game\_key
* メディアソース
* キャンペーン名

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

Game Analyticsでは、計測リンクは利用できません。

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

Game Analyticsでは、権限の設定は利用できません。

</Accordion>

<div data-zendesk-anchors="h_01H9FK7ZH27GNEHRZ5KKVH5CHY=%E9%87%8D%E8%A6%81 setting-up-gameanalytics=gameanalytics%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK7ZH24E9AD7Z0J94NS0JJ=gameanalytics%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK7ZH3VPBE965Z8MCVXSMQ=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9FK7ZH3D2H5AWW0DMBQP9R3=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9FK7ZH3E32TT8EGAYWPRWBE=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FK7ZH3P0HSQGR2409BFA2F=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-event-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK7ZH366RDSY36QVVWJMJN=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK7ZH39J4Q7W5XSFZAEZWH=attribution-link-tab h_01H9FK7ZH37FQ6RN80E90TH4K9=cost-tab h_01H9FK7ZH3GE3G69AA03KJK499=ad-revenue-tab h_01H9FK7ZH3RQJQPAYSZBR208H7=permissions-tab" />
