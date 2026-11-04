---
title: Amazon Adsキャンペーン連携設定
metadata:
  keywords:
    - Wechat Ads
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
  created_at: '2017-06-18T06:41:29Z'
  edited_at: '2026-10-14T09:34:00Z'
  id: 115003044106
  locale: ja
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/ja/articles/115003044106
---
> **概要：**

<div id="setting-up-your-campaign-on-wechat" />

<div id="introduction" />

## はじめに

YouAppi を使ったキャンペーンを設定するには、以下の手順に従ってください。


2. * インストール
   * 登録
   * 購入
   * カート追加

![wechat-configuration.png](https://files.readme.io/228ee10ef3dc113ae8af8de0f283b144206db1857f6d1f9169355f294155b8f8-50900431174033.png)

![wechat-keys.png](https://files.readme.io/cd7a2406ae9981eaabb4089813c9a1b847f0e6f750b9c0c0a0ac5e726dfe44be-50900431177361.png)



<span id="setting-up-wechat-on-appsflyer"></span><span id="setting-up-wechat-campaign-as-an-agency"></span>設定は**連携済みパートナー** ページから行われますが、新しく連携する際には、まず <Anchor target="_blank" href="/marketers/ja/docs/partner-integrations">Partner Marketplace</Anchor>にアクセスする必要があります。

> 📘 **注意**
>
> 連携を設定する前に、<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーへ連絡</Anchor>して広告運用のためのアカウントを開設してください。

**連携を有効にする方法：**

1. AppsFlyerのサイドメニューから**Collaborate** > **Partner Marketplace**を選択します。
2. パートナーを検索し選択してください。
3. **連携の設定**をクリックします。 連携の設定ページに移動します。
4. **連携**タブで、**パートナーを有効にする**トグルをオンにします。  
   <strong>注：このトグルは、このパートナーの連携を続ける限り、</strong>オン（有効）/strong>のままにしておく必要があります。
5. 以下の手順に従い、各タブの設定を完了してください。

AppLovinの設定画面には5つのタブがあります：次の項目をクリックすると各タブの設定に関する説明が表示されます。

連携済みパートナーの設定画面のヘッダーについての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>をクリックしてください。

> 👍 **ヒント**
>
> * 連携タブでの<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#d-general-settings">一般的な設定</Anchor>の項目は、全てのパートナーにおいて**必須**です。
> * その他すべてのステップは、説明的または**任意**の設定です。

<div id="integration-tab" />

<Accordion title="連携タブ">

連携タブは次のセクションに分かれています。

<div id="activate-partner" />

### パートナーの有効化

この画面を**最初に開く**際には、以下のトグルをオンにする必要があります。[***パートナーを有効にする***] トグルをオンにして、連携タブのパラメーター設定を有効にします。このパートナーと連携を続ける限り、トグルをオンにしておく必要があります。  
パートナーの有効化についての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>をご覧ください。

<div id="note" />

> 📘 **注意**
>
> 全てのインストールデータを受信できるネットワークであるLINEは、オーガニックを含む全てのメディアソースに紐づく新規インストールのポストバック受信を希望しています。**All media sources, including organic** を選択し、全てのインストールポストバックをLINEに送信することを推奨します。

<div id="general-settings" />

### 一般的な設定

**Partner ID（パートナーID）**

<Image alt="wechat-integration-general-settings.png" src="https://files.readme.io/f1e0675a26116b628629b07616a7b9b86e8413ee36d7504f415207cb1590cb82-50900431178001.png" width="390px" />

<div id="default-postbacks" />

### デフォルトのポストバック

AppsFlyerは、ユーザーインストールとリエンゲージメント後に、自動でYouAppiにポストバックを送信します。このセクションでは、これらのポストバックの**送信を許可するユーザー**を定義してください。

![wechat-default-postbacks.png](https://files.readme.io/1a2703b97a71bf82bcc77f5393459bc94b5443b83a4c4965d2624eda0e9f166f-50900402778129.png)

AppLovinに紐づくユーザーからのイベントのみにするには、**このパートナーに紐づくイベントのみ**を選択します。 [オーガニックを含む全メディアソース]**を選択して、ユーザーベース全てをYouAppiにレポートできるようにします。**

<div id="in-app-events-settings" />

### アプリ内イベントの設定

このセクションでは、ポストバックを介して、AppsFlyerイベントをYouAppiとマッピングできます。

![wechat_in_app_event_postbacks.png](https://files.readme.io/cd6234df4809b27044e361ad8835d4ae92100c491e0aa7c8f003336cdf2ad49d-50900431180561.png)

4. アプリ内イベントのポストバックのトグルをONにしてください。
5. SDK に定義済みの全てのイベントに対して、送信オプションを選択してください。  
   **- このパートナーに紐づけられたイベントのみ**：このパートナーに紐づけられたユーザー**のみ**から発生したイベント  
   **- いずれかのパートナーまたはオーガニックに紐づけられたイベント**：ユーザーベース全体をパートナーに報告できるようにする場合に選択
6. **イベントを追加**をクリックして、SDKイベントをリストに追加してください。
7. 次のパラメーターを入力してください:

| パラメータ名 | 説明 |
| --- | --- |
| **SDKイベント名** | アプリと連携済みのSDKから、またはサーバー間（S2S）イベントからAppsFlyerが受信したイベント名  <br />**ヒント** - アプリ内イベント名がリストに表示されない場合、デバイス上で非オーガニックインストールによってアプリ内イベントが発生しているかを確認してください。 |
| **パートナー側のイベント名** | Apple側で定義されている各イベントの一意の名前またはID。   <br />対応するイベントIDをAppleから取得して、テキストフィールドに設定してください。 |
| **収益値を送信** | **チェックなしの場合** - AppsFlyerはリッチアプリ内イベントのすべてのパラメーターをパートナーに送りますが、**af\_revenue**パラメーターに含まれるrevenueパラメータは送信しません。  <br />**チェックありの場合：** AppsFlyerは収益値（イベントに存在する場合）を含むすべてのパラメーターをパートナーに送ります。 |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

このタブでは、YouAppiのキャンペーン、広告セット、単一の広告レベルで計測したい計測リンクを作成できます。AppsFlyerでは作成された計測リンクは保存されませんのでご注意ください。

このタブは複数のセクションに分かれています。

<div id="attribution-link-parameters" />

### 計測リンクパラメーター

このセクションでは、計測リンクに追加したいパラメータを選択できます。

計測リンクにパラメータを追加すると、後でドリルダウン分析を実行できます。アトリビューションリンクですでに定義されているパラメーターは、それらと新しい値をここで追加することで編集できます。

* **キャンペーン** - これを追加すると、YouAppiの成果をキャンペーン別に比較できます。  
  **計測リンクパラメーター**：c
* **広告セット** - これを追加すると、特定のYouAppiのキャンペーンを広告セット別に比較できます。  
  **計測リンクパラメーター**： af\_adset
* **Ad Name**：特定のironSourceキャンペーンの特定の広告セット内の広告別に比較するために広告名を追加します。  
  **計測リンクパラメーター**： af\_ad
* **Site ID**（サイトID）および **Sub Site ID**（サブサイトID）：サイトIDパラメータを設定すると、特定のパブリッシャーにインストールを紐づけられます。パブリッシャー数が多い場合、サイトIDの制限を越えないように、サイトIDの使用数を控えて、サブサイトIDパラメーターを使用することをおすすめします。  
  **計測リンクパラメーター**： af\_siteid、af\_sub\_siteid
* **Subscriber Parameter**（サブスクライバーパラメーター）：5つのサブスクライバーパラメーターに値を追加できます。これらのパラメーターは解析されローデータレポートに表示されるため、データの集約やフィルタリングに非常に便利です。  
  **計測リンクパラメーター**： af\_sub1、af\_sub2、af\_sub3、af\_sub4、af\_sub5

![attribution-link-parameters.png](https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png)

計測リンクに他のパラメーターを追加するには、新しいパラメーター項目に入力入力してください。詳細は、**<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">AppsFlyer計測リンクの構造とパラメーター</Anchor>** をご覧ください。

<div id="click-through-attribution" />

### クリックスルーアトリビューション

このスライダーでは**クリックからインストールまでの最大有効期間**を設定できます。ルックバック期間内に発生するインストール（初回起動）のみがGMPの成果に紐づきます。

**計測リンクのパラメータ：** af\_click\_lookback

クリックルックバック期間の詳細については<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">こちら</Anchor>を参照してください。

[![](https://files.readme.io/86114a765dea30da658a676d1a7506c6ba385bdf8ebcf7241a1ce85f8c413077-50900402782737.png)](https://files.readme.io/86114a765dea30da658a676d1a7506c6ba385bdf8ebcf7241a1ce85f8c413077-50900402782737.png)

<div id="click-attribution-link" />

### クリックアトリビューションリンク

このリンクは、あなたが設定したすべての情報が含まれる計測リンクです。ユーザーが広告をクリックしたときに有効になるように、Liftoffへ入稿してください。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

Twitterでは、広告収益の連携はサポートしておりません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

</Accordion>

<div data-zendesk-anchors="introduction=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB h_01HKW6Z36NGCWC0R6EQX49S34J=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB setting-up-your-campaign-on-wechat=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB h_01HKW6Z36NTSGCDQM553YMHHDH=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB setting-up-wechat-on-appsflyer=setting-up-wechat-campaign-as-an-agency h_01HKW6Z36N8S8KSBNMR8A54RRN=setting-up-wechat-campaign-as-an-agency h_01HKW6Z36N3JSYEWJZH74M5WWJ=setting-up-wechat-campaign-as-an-agency h_01HKW6Z36NPKQGH2E3ZZJFVTHH=%E6%B3%A8%E6%84%8F h_01HKW6Z36NHHDW13B7K24D18H6=%E3%83%92%E3%83%B3%E3%83%88 h_01HKW6Z36PDGTT3EERY8F4VA79=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HKW6Z36P0EQF829NW3GDXKEN=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HKW6Z36P806MHV6N3D1N9HW3=%E6%B3%A8%E6%84%8F-1 general-settings=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A h_01HKW6Z36P51EG4BW7WA3JGSKN=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HKW6Z36P3D4EPKC6ZZK94YVF=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-events-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKW6Z36PA90WEJMFH7BZMD72=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKW6Z36PRBT2X6F5BHYW06E1=attribution-link-tab attribution-link-parameters=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC h_01HKW6Z36P73H79MVFXQ29K2M6=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC clickthrough-attribution=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HKW6Z36P95C7CT1J6YS5CQN8=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 click-attribution-link=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF h_01HKW6Z36PEAPM8RAKB0RM9RES=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF h_01HKW6Z36PEG0T9WQQRNY19EVG=cost-tab h_01HKW6Z36WE1SDC7KZHCMTPA0T=ad-revenue-tab h_01HKW6Z36W6QKR583X4Q4BNBZ4=permissions-tab" />
