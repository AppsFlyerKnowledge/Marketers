---
title: IBM UBXとAppsFlyerの連携ガイド
metadata:
  keywords:
    - Analytics
    - IBM
    - UBX
    - integrated partner
    - Advertisers
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
  created_at: '2016-07-03T09:06:26Z'
  edited_at: '2026-10-28T09:03:07Z'
  id: 210093266
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/210093266
---
> **概要：** AppsFlyerの連携済みパートナーであるIBM UBX（Universal Behavior Exchange）は、IBM Marketing Cloudやその他のIBM Commerce製品の機能です。使いやすいコンソールから、顧客データの連携を一元管理できます。オープンなデータ交換機能により、チャネル、デバイス、接点を横断して顧客の購買行動を把握できます。効果的なキャンペーンをすばやく設計・実行し、その場で顧客に適した体験を提供してROIの向上につなげられます。

<div id="important" />

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

<div id="setting-up-ibm" />

## IBMの設定

**前提条件：** パートナーのアカウントが必要です。アカウントがない場合は、連携を設定する前にパートナーに連絡し、アカウントを開設してください。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。  
   （**既存の連携を編集する場合：** ［**連携＞パートナー連携＞有効な連携**］タブに移動します。）
2. 対象のアプリを選択します。
3. パートナーを検索し、［**連携する**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。   
   注意：パートナーとの連携を利用している間は、**このトグルをオン（有効）にしておく必要があります**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳しく見る</Anchor>
5. 以下の説明に従い、該当するタブで設定を完了します。

IBMの設定で使用するのは、<strong>［連携］</strong>タブのみです。

パートナー設定画面のヘッダーについて詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>を参照してください。

<div id="integration-tab" />

<Accordion title="連携タブ">

［連携］タブは、以下のセクションで構成されています。

<div id="activate-partner" />

### パートナーを有効化

**初めてこの画面を開いたとき**は、下にあるトグルをオンにする必要があります。［***パートナーを有効化***］をオンにすると、［連携］タブのパラメータを設定できるようになります。パートナーとの連携を利用している間は、このトグルをオンにしておく必要があります。  
パートナーの有効化について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>を参照してください。

<div id="general-settings" />

### 一般設定

**認証キー**

IBMとAppsFlyerの接続には、固有の認証キーを使用します。まだ取得していない場合は、連携の設定を進める前にIBMから取得するか、以下の手順で取得してください。

![IBM_msc_new_2.png](https://files.readme.io/d6dddd7232ba7ecba2ed5bd944f98669902689fc0953afc558fbc6586be8b5cf-360002219269.png)

<div id="obtaining-the-authorization-key" />

### 認証キーの取得

汎用のAppsFlyerイベント発行エンドポイントを設定するには、まずUBXの画面で空のエンドポイントを作成します。

UBXアカウントにログインし、**Endpoints**タブに移動します。

![](https://files.readme.io/8c0833f890c5e2ed2df1c0a8904e1764b341a82f3381c0a1a3fb6effe4f76673-205128323.png)

次に、**Register new endpoint**をクリックします。

![](https://files.readme.io/23c8d4a88eda765fce1b42f9eb2e74b1325160e6d0602dc65a8ab05488598b9e-205053206.png)

**AppsFlyer**を選択し、**Next**をクリックします。

![IBM_1.png](https://files.readme.io/f30b7b27d2ffecf3e562cbe651367306a581d1881325dd141c950b39efac016c-115002600286.png)

**Next**をクリックします。

![Pasted_image_at_2017_02_23_02_48_PM.png](https://files.readme.io/11a94c4d9f4c9282c230e4cf69f31e0d39f4eb88196313b3cfc103a5bbaba9a4-115002600326.png)

新しく作成されたAppsFlyerエンドポイントの右側にある3点メニューをクリックし、**endpoint details**をクリックします。

![IBM_3.png](https://files.readme.io/70edd2e14c6c344188dcc65b65b3a8d92081401dd34909f5a4e0dd6bd137b8df-115002599203.png)

認証キーをコピーします。

![IBM_Endpoint_details.png](https://files.readme.io/3706f4dd665d8d2a26de9013b03c0e6575d051f2fa5500033e172312a63f09ea-115002601006.png)

<div id="default-postbacks" />

### デフォルトポストバック

AppsFlyerは、ユーザーのインストール後にIBMへポストバックを自動送信できます。このセクションで、ポストバックの送信を設定します。

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

アプリをダウンロードしたすべてのユーザーのポストバックをIBMに送信するには、<strong>［すべてのパートナーまたはオーガニックのイベント］</strong>を選択します。送信しない場合は、<strong>［オフ］</strong>を選択します。

［**保存**］をクリックします。

<div id="in-app-event-settings" />

### アプリ内イベントの設定

[![](https://files.readme.io/c945ee3c04f49076e54c9966389506aea441406e01daa49d737a86da9f5bd2bc-360002219429.png)](https://files.readme.io/c945ee3c04f49076e54c9966389506aea441406e01daa49d737a86da9f5bd2bc-360002219429.png)

このセクションでは、ポストバックを介してAppsFlyerのイベントをIBMのイベントに対応付けます。

1. 認証キーを再度入力します。
2. ［アプリ内イベントポストバック］をオンにします。
3. SDKで定義されたすべてのイベントについて、送信対象を選択します。  
   **- このパートナーのイベントのみ**：このパートナーの成果として計測されたユーザーのイベント**のみ**を送信します。  
   **- すべてのパートナーまたはオーガニックのイベント**：すべてのユーザーのデータをパートナーに送信できます。
4. ［**イベントを追加**］をクリックし、SDKイベントをリストに追加します。
5. 以下のパラメータを設定します。

| パラメータ名 | 説明 |
| --- | --- |
| **SDKイベント名** | アプリに実装したSDKまたはサーバー間（S2S）イベントからAppsFlyerが受信したイベント名です。  <br />**ヒント**：リストに目的のイベントがない場合は、非オーガニックでインストールしたデバイスでそのイベントを発生させ、もう一度確認してください。 |
| **パートナーイベント識別子** | IBM側で定義されている各イベントの一意の名前またはIDです。  <br />IBMから対応するイベントIDを取得し、テキストフィールドに入力します。 |
| **収益を送信** | **オフの場合**：**af\_revenue**で指定した収益値を除き、リッチアプリ内イベントのすべてのパラメータをパートナーに送信します。  <br />**オンの場合**：収益値を含むすべてのパラメータを送信します（イベントに収益値がある場合）。 |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

IBMでは、計測リンクは利用できません。

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

IBMでは、権限の設定は利用できません。

</Accordion>

<div data-zendesk-anchors="h_01H9FK8FS5T9KZ30N87B76QVT5=%E9%87%8D%E8%A6%81 setting-up-ibm=ibm%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK8FS5QPJYSA7JVY4QNB3S=ibm%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK8FS5J30GZS634NMG62BQ=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9FK8FS5SYTBF8A3QX4QGESM=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9FK8FS5YXRCN83RHG6QBAKS=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A obtaining-the-authorization-key=%E8%AA%8D%E8%A8%BC%E3%82%AD%E3%83%BC%E3%81%AE%E5%8F%96%E5%BE%97 h_01H9FK8FS5ZVGX5RK7K72SH6K6=%E8%AA%8D%E8%A8%BC%E3%82%AD%E3%83%BC%E3%81%AE%E5%8F%96%E5%BE%97 default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FK8FS5SVF4YQC8AG2V6N8D=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-event-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK8FS54N196VQ0XCXJ763Q=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK8FS50TB7TZH9JKEH3Y7H=attribution-link-tab h_01H9FK8FS54P1MYVXGR46TXN7D=cost-tab h_01H9FK8FS600SP0MS1T6PTBMH4=ad-revenue-tab h_01H9FK8FS65VMZK13D2BE5DT09=permissions-tab" />
