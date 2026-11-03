---
title: Awinキャンペーン設定
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-08-02T05:47:59Z'
  edited_at: '2026-10-14T09:31:36Z'
  id: 360002152957
  locale: ja
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/ja/articles/360002152957
---
> **概要：**


<span id="setting-up-360-ads"></span>設定は**連携済みパートナー** ページから行われますが、新しく連携する際には、まず <Anchor target="_blank" href="/marketers/ja/docs/partner-integrations">Partner Marketplace</Anchor>にアクセスする必要があります。

> 📘 **注意**
>
> 連携を設定する前に、<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーへ連絡</Anchor>して広告運用のためのアカウントを開設してください。

**連携を有効にする方法：**

1. AppsFlyerのサイドメニューから**Collaborate**> **Partner Marketplace**を選択します。
2. パートナーを検索し選択してください。
3. **連携の設定**をクリックします。
4. 連携の設定ページに移動します。
5. **連携タブ**にて、**パートナーを有効にする**をオンにします。

次の項目をクリックすると各タブの設定に関する説明が表示されます。

連携済みパートナーの設定画面のヘッダーについての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>をクリックしてください。

> 👍 **ヒント**
>
> * 連携タブでの<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#d-general-settings">一般的な設定</Anchor>の項目は、全てのパートナーにおいて**必須**です。
> * その他すべてのステップは、説明的または**任意**の設定です。

<div id="integration-tab" />

<Accordion title="Integration（連携）タブ">

### パートナーの有効化

この画面を**最初に開く**際には、以下のトグルをオンにする必要があります。[***パートナーを有効にする***] トグルをオンにして、連携タブのパラメーター設定を有効にします。このパートナーと連携を続ける限り、トグルをオンにしておく必要があります。  
パートナーの有効化についての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>をご覧ください。

### 一般的な設定

**ビュースルー計測の有効化**

YouAppiでビュースルーインストールを計測したい場合は、このトグルをオンにしてください。ビュースルールックバック期間は、計測リンクタブ（下記参照）にて設定できます。

### Default Postback（デフォルトのポストバック）

<Image alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="506px" />

### アプリ内イベントの設定

このセクションでは、ポストバックを介して、AppsFlyerイベントをYouAppiとマッピングできます。

<Image alt="mceclip2.png" src="https://files.readme.io/0d52eb93f8cba6ec283cdf844cc6fa891499884de0c93689653f4d356078dd85-50900375408017.png" width="412px" />

2. アプリ内イベントのポストバックのトグルをONにしてください。
3. **イベントを追加**をクリックして、SDKイベントをリストに追加してください。
4. 次のパラメータを設定します。

| パラメータ名 | 説明 |
| --- | --- |
| **SDKイベント名** | アプリと連携済みのSDKから、またはサーバー間（S2S）イベントからAppsFlyerが受信したイベント名  <br />**ヒント** - アプリ内イベント名がリストに表示されない場合、デバイス上で非オーガニックインストールによってアプリ内イベントが発生しているかを確認してください。 |
| **パートナー側のイベント名** | Meta広告で定義されている各イベントの一意の名前またはID。  <br />対応するイベントIDをAppleから取得して、テキストフィールドに設定してください。 |
| **収益値を送信** | **チェックなしの場合** - AppsFlyerはリッチアプリ内イベントのすべてのパラメーターをパートナーに送りますが、**af\_revenue**パラメーターに含まれるrevenueパラメータは送信しません。  <br />**チェックありの場合：** AppsFlyerは収益値（イベントに存在する場合）を含むすべてのパラメーターをパートナーに送ります。 |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

このタブでは、YouAppiのキャンペーン、広告セット、単一の広告レベルで計測したい計測リンクを作成できます。AppsFlyerでは作成された計測リンクは保存されませんのでご注意ください。

このタブは複数のセクションに分かれています。

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

<Image alt="attribution-link-parameters.png" src="https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png" width="588px" />

計測リンクに他のパラメーターを追加するには、新しいパラメーター項目に入力入力してください。詳細は、**<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">AppsFlyer計測リンクの構造とパラメーター</Anchor>** をご覧ください。

### Click-Through Attribution（クリックスルーアトリビューション）

このスライダーでは**クリックからインストールまでの最大有効期間**を設定できます。ルックバック期間内に発生するインストール（初回起動）のみがGMPの成果に紐づきます。

**計測リンクのパラメータ：** af\_click\_lookback

クリックルックバック期間の詳細については<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">こちら</Anchor>を参照してください。

![netease-click-through.png](https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png)

### 計測リンク

このリンクは、あなたが設定したすべての情報が含まれる計測リンクです。ユーザーが広告をクリックしたときに有効になるように、Liftoffへ入稿してください。

### ビュースルーアトリビューションルックバック期間

このスライダーでは、 **インプレッションからインストールまでの最大有効期間**を設定できます。広告のインプレッション後、ほかに関連する広告がクリックされなかった場合、このルックバック期間内に発生したインストール（初回起動）のみが YouAppi に紐付けられます。

この値は1～23時間または1～7日間で設定できます。

**計測リンクパラメータ**： af\_viewthrough\_lookback

ビュースルー計測の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">こちら</Anchor>を参照してください。

[![](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)

### インプレッションのアトリビューションリンク

インプレッションアトリビューションリンクは、異なるルックバック期間を除いて、クリック記録リンクと同様のアトリビューションデータを含んでいます。このリンクをYouAppi に入稿すると、媒体によりますが、通常、該当する広告を1秒以上見た時に有効になります。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

このパートナーとの連携では、コストデータはサポートされていません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

このパートナーとの連携では、広告収益はサポートされていません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions（権限）タブ">

このタブでは、パートナーがアドネットワークの場合、代理店の場合、または両方の場合に、MoPub に付与する権限を選択できます。MoPubのアトリビューションが無効になっている場合でも、権限タブはアクティブであり、MoPub に権限を付与することができます。

![rtb_house-permissions-new.png](https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png)

### Ad Network Permissions（アドネットワークへの権限）

これらのトグルを使用して、アプリごとにアドネットワークへの権限付与を設定してください：

* ***パートナー連携の設定を許可する*** - パートナーに連携タブの設定（アプリ内イベントのポストバックを除く）を許可します。
* ***アプリ内イベントのポストバック設定を許可する*** - 連携タブでアプリ内イベントのポストバックをマッピングする設定をパートナーに許可します。
* ***リテンションレポートへのアクセスを許可*** - パートナーのリテンションデータへのアクセスを許可します。
* ***Protect360管理画面へのアクセスを許可する*** - Protect360のデータへのアクセスを許可します（パートナーのデータのみ）。＜広告主がProtect360に申込みしている場合のみ＞

詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">アドネットワークへの権限付与</Anchor>をご覧ください。

</Accordion>

<div data-zendesk-anchors="h_01HKW6S90SZY55XRP6YN8B3QTJ=setting-up-360-ads h_01HKW6S90SYCB1GGTC4PMS5C9X=%E6%B3%A8%E6%84%8F h_01HKW6S90SNHXZC9AMNFX4S8PJ=%E3%83%92%E3%83%B3%E3%83%88 h_01HKW6S90TSD0WKZ4ZT7701DX7=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HKW6S90TVP4K2XFP5EEFWDC4=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A h_01HKW6S90T9ABAX8E7DK02N538=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A default-postbacks=default-postback%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HKW6S90TEJ68RG9B3S5KD63Y=default-postback%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-events-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKW6S90TN3J07GXS8C7NTETR=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKW6S90T7P66TMWFA4T4C350=attribution-link-tab attribution-link-parameters=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC h_01HKW6S90TCMRFHFXBEJBCP9C6=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC clickthrough-attribution=click-through-attribution%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HKW6S90TQW75T0HCCC38ETWB=click-through-attribution%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 attribution-link=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF h_01HKW6S90T0SVWCEV905DC2VTW=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF viewthrough-attribution-lookback-window=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01HKW6S90T813FYKMGDAF935YJ=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 impressions-attribution-link=%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF h_01HKW6S90T4TS5EHK8M7E4QV8G=%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF h_01HKW6S90TXR07SQJW3DTD9VS4=cost-tab h_01HKW6S90T489CVTQXQPRM0M8B=ad-revenue-tab h_01HKW6S90VWKHEWNY7AYKRWGBH=permissions-tab ad-network-permissions=ad-network-permissions%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90 h_01HKW6S90V1ZV766FZ20EKJR0N=ad-network-permissions%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90" />
