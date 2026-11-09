---
title: Unity Adsキャンペーン連携設定
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
  created_at: '2019-08-29T08:24:47Z'
  edited_at: '2026-10-14T09:37:10Z'
  id: 360002358897
  locale: ja
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/ja/articles/360002358897
---
>


<span id="setting-up-vivo-ads"></span>設定は**連携済みパートナー** ページから行われますが、新しく連携する際には、まず <Anchor target="_blank" href="/marketers/ja/docs/partner-integrations">Partner Marketplace</Anchor>にアクセスする必要があります。

> 📘 **注意**
>
> 連携を設定する前に、<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーへ連絡</Anchor>して広告運用のためのアカウントを開設してください。

**連携を有効にする方法：**

1. AppsFlyerのサイドメニューから**Collaborate** > **Partner Marketplace**を選択します。
2. パートナーを検索し選択してください。
3. **連携の設定**をクリックします。
4. 連携の設定ページに移動します。
5. **連携タブ**にて、**パートナーを有効にする**をオンにします。

連携とアトリビューションリンク。次の項目をクリックすると、各タブの設定に関する説明が表示されます。

連携済みパートナーの設定画面のヘッダーについての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>をクリックしてください。

> 👍 **ヒント**
>
> * 連携タブでの<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#d-general-settings">一般的な設定</Anchor>の項目は、全てのパートナーにおいて**必須**です。
> * その他すべてのステップは、説明的または**任意**の設定です。

<div id="integration-tab" />

<Accordion title="Integration（連携）タブ">

<div id="activate-partner" />

### パートナーの有効化

この画面を**最初に開く**際には、以下のトグルをオンにする必要があります。[***パートナーを有効にする***] トグルをオンにして、連携タブのパラメーター設定を有効にします。このパートナーと連携を続ける限り、トグルをオンにしておく必要があります。  
パートナーの有効化についての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>をご覧ください。

<div id="enable-view-through-attribution" />

### ビュースルー計測の有効化

AppLovinでビュースルーインストールを計測したい場合は、このトグルをオンにしてください。ビュースルールックバック期間は、計測リンクタブ（下記参照）にて設定できます。

<div id="default-postbacks" />

### Default Postback（デフォルトのポストバック）

<Image align="center" alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="456px" />

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

<Image align="center" alt="attribution-link-parameters.png" src="https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png" width="479px" />

計測リンクに他のパラメーターを追加するには、新しいパラメーター項目に入力入力してください。詳細は、**<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">AppsFlyer計測リンクの構造とパラメーター</Anchor>** をご覧ください。

<div id="click-through-attribution" />

### クリックスルーアトリビューション

このスライダーでは**クリックからインストールまでの最大有効期間**を設定できます。設定したルックバック期間内に発生したインストール（初回起動）のみYouAppi の成果として計測されます。

**計測リンクのパラメータ：** af\_click\_lookback

クリックルックバック期間の詳細については<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">こちら</Anchor>を参照してください。

<Image align="center" alt="viewthrough_en-us.png" src="https://files.readme.io/47ff5d900d8edfdc30f2d2c0588f5e06fc3b44e71aeab630d1b5df2ea8c2db47-50900334036625.png" />

<div id="attribution-link" />

### 計測リンク

このリンクは、あなたが設定したすべての情報が含まれる計測リンクです。ユーザーが広告をクリックしたときに有効になるように、Liftoffへ入稿してください。

<div id="view-through-attribution-lookback-window" />

### ビュースルーアトリビューションルックバック期間

このスライダーでは、 **インプレッションからインストールまでの最大有効期間**を設定できます。広告のインプレッション後、ほかに関連する広告がクリックされなかった場合、このルックバック期間内に発生したインストール（初回起動）のみが YouAppi に紐付けられます。

この値は1～23時間または1～7日間で設定できます。

**計測リンクパラメータ**： af\_viewthrough\_lookback

ビュースルー計測の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">こちら</Anchor>を参照してください。

<Image align="center" alt="" src="https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png" />

<div id="impressions-attribution-link" />

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

</Accordion>

<div data-zendesk-anchors="h_01HKW6Y9CJED5RV97WWSYQNBDG=setting-up-vivo-ads h_01HKW6Y9CJ747R6F84H6XEVHRC=%E6%B3%A8%E6%84%8F h_01HKW6Y9CJXAR3YQ1RM3VTE0CF=%E3%83%92%E3%83%B3%E3%83%88 h_01HKW6Y9CJZ1YPFBQH1W0QV21G=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HKW6Y9CJC0EWH84B7GW29VJM=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 enable-viewthrough-attribution=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HKW6Y9CJ8PNMN2ANR3E3WK1H=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 default-postbacks=default-postback%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HKW6Y9CJDY5XHWXN3CK0YGK8=default-postback%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HKW6Y9CKQXSWXNK1VEXQFEPA=attribution-link-tab attribution-link-parameters=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC h_01HKW6Y9CKSHBWNBH0RY3X3RR3=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC clickthrough-attribution=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HKW6Y9CKE86Z1Z4QZH0M665T=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 attribution-link=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF h_01HKW6Y9CKNB685ZYXB8RM1P41=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF viewthrough-attribution-lookback-window=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01HKW6Y9CKV48NRWSXD0ZKY3M0=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 impressions-attribution-link=%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF h_01HKW6Y9CKV6XY1BCD9XX42XZ7=%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF h_01HKW6Y9CKZ0TMJ1F3H8X2W733=cost-tab h_01HKW6Y9CKB65QFDTKX4AW3P23=ad-revenue-tab h_01HKW6Y9CKV3KJ5X5ECEF2JJ8N=permissions-tab" />
