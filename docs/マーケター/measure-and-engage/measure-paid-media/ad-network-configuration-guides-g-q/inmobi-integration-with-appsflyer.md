---
title: Roku連携設定ガイド
metadata:
  keywords:
    - Campaign
    - SDK
    - Configure
    - InMobi
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
  created_at: '2014-11-20T10:29:22Z'
  edited_at: '2026-10-14T09:32:15Z'
  id: 207033896
  locale: ja
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/ja/articles/207033896
---
> **概要：** クリックに基づくモバイル計測に加えて、ironSourceでは、AppsFlyerで計測できるコスト、広告収益、リターゲティング、ビュースルー計測を提供しています。

<Image alt="inmobi_icon.png" src="https://files.readme.io/cbe0e88492041fc8e1781b397b67a3c8c3a09591974f2cf4fa145a18ca9e6a8d-10602685724817.png" width="128px" />


**<span id="setting-up-inmobi"></span><span id="setting-up-glispa"></span>前提条件：** 連携を設定する前に、 <Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーへ連絡</Anchor>し、アカウントを開設してください。

**連携を有効化または編集する：**

1. **有効化するには：** AppsFlyer管理画面 左メニュー **連携** > **Partner Marketplace**へ移動します。  
   **編集方法：** AppsFlyer管理画面左メニュー **連携** > **連携済みパートナー**を選択します。
2. パートナーを検索し選択してください。
3. **連携の設定**をクリックします。連携の設定ページに移動します。
4. **連携**タブにて連携したいアプリを選択し、 **パートナーを有効にする**をオンにしてください。  
   **注：** パートナーと作業している間、トグルはオン<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">（有効）</Anchor>のままにしておく必要があります。
5. 以下の手順に従い、各タブの設定を完了してください。

連携済みパートナーの設定画面のヘッダーについての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>をクリックしてください。

<div id="tip" />

> 👍 **ヒント**
>
> * 連携タブでの<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#d-general-settings">一般的な設定</Anchor>の項目は、全てのパートナーにおいて**必須**です。
> * その他すべてのステップは、説明的または**任意**の設定です。

<div id="integration-tab" />

<Accordion title="連携タブ">

<div id="activate-partners" />

### パートナーの有効化

このタブを**初めて**開く場合、連携タブのパラメーター設定を有効にするために**パートナーを有効にする**のトグルをオンにする必要があります。このパートナーと連携を続ける限り、トグルをオンにしておく必要があります。  
パートナーの有効化についての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>をご覧ください。

<div id="note" />

> 📘 **注意**
>
> 全てのインストールデータを受信できるネットワークであるLINEは、オーガニックを含む全てのメディアソースに紐づく新規インストールのポストバック受信を希望しています。そのためには、**全てのパートナーに紐づくイベント**を選択して、全てのインストールポストバックをLINEに送信してください。

<div id="general-settings" />

### 一般的な設定

**gpm\_ID**

![Inmobi_msc_new_3.png](https://files.readme.io/9c2efaed833211582a33b3a2bbd7d07336bc78d6e2d4e3a7645b5ca14be2fd73-360001865845.png)

**ビュースルー計測の有効化**

YouAppiでビュースルーインストールを計測したい場合は、このトグルをオンにしてください。ビュースルールックバック期間は、計測リンクタブ（下記参照）にて設定できます。

<div id="default-postbacks" />

### デフォルトのポストバック

ユーザーのインストールおよびリエンゲージメント後に、自動ポストバックを送信します。このセクションでは、これらのポストバックの**送信を許可するユーザー**を定義してください。

AppLovinに紐づくユーザーからのイベントのみにするには、**このパートナーに紐づくイベントのみ**を選択します。  
[**オーガニックを含む全メディアソース**] を選択して、ユーザーベース全てをYouAppiにレポートできるようにします。

<div id="in-app-events-settings" />

### アプリ内イベントの設定

このセクションでは、ポストバックを介して、AppsFlyerイベントをYouAppiとマッピングできます。

2. アプリ内イベントのポストバックのトグルをONにします。
3. SDK に定義済みの全てのイベントに対して、送信オプションを選択してください。  
   **- このパートナーに紐づけられたイベントのみ**：このパートナーに紐づけられたユーザー**のみ**から発生したイベント  
   [**オーガニックを含む全メディアソース**] は、利用可能な全てのユーザーベースをこのパートナーに送信したい場合に選択します。
4. **イベントを追加**をクリックして、SDKイ ベントをリストに追加します。
5. 次のパラメータを設定します：

| パラメータ名 | 説明 |
| --- | --- |
| **SDKイベント名** | これは、アプリに連携されたSDKまたはサーバー間イベントからAppsFlyerが受信したイベントの名前です。  <br />**ヒント** - アプリ内イベント名がリストに表示されない場合、デバイス上で非オーガニックインストールによってアプリ内イベントが発生しているかを確認してください。 |
| **パートナー側のイベント名** | YouAppi 側で定義されている各イベントの一意の名前またはID。  <br />対応するイベントIDをYouAppiから取得して、テキストフィールドに設定してください。 |
| **収益値を送信** | **チェックなしの場合** - リッチアプリ内イベントのすべてのパラメーターをパートナーに送りますが、**af\_revenue** パラメーターに含まれる収益パラメーターは送信しません。  <br />**チェックありの場合：** 収益値（イベントに存在する場合）を含むすべてのパラメーターをパートナーに送ります。 |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

このタブでは、YouAppiのキャンペーン、広告セット、単一の広告レベルで計測したい計測リンクを作成できます。AppsFlyerでは作成された計測リンクは保存されませんのでご注意ください。

[![](https://files.readme.io/03371cdc64826e77cee3bd0adb90280aa59ebddd34ec85d8946ae9646ce86ce8-360001866409.png)](https://files.readme.io/03371cdc64826e77cee3bd0adb90280aa59ebddd34ec85d8946ae9646ce86ce8-360001866409.png)

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

[![](https://files.readme.io/f026eec1923611f33be47d7ad3b1a8654f697145be30f552cef5578fe895944c-360002234165.png)](https://files.readme.io/f026eec1923611f33be47d7ad3b1a8654f697145be30f552cef5578fe895944c-360002234165.png)

計測リンクに他のパラメーターを追加するには、新しいパラメーター項目に入力入力してください。詳細は、**<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">AppsFlyer計測リンクの構造とパラメーター</Anchor>** をご覧ください。

<div id="retargeting-settings" />

### リターゲティング設定

リターゲティングの設定が有効化されると、AppsFlyerではクリック計測リンクに<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">&is\_retargeting=true</Anchor>を追加することで、リンクを新規ユーザー獲得用ではなく、`&is_retargeting=true`リターゲティング&is\_retargeting=true 用の計測リンクとして認識します。注: リターゲティング機能は現在クリックスルーアトリビューションでのみサポートされており、ビュースルーには対応していません。  
**計測リンクのパラメーター：** is\_retargeting

リターゲティングの設定が有効化されると、次の設定ページが表示されます。

![msc_new_7.png](https://files.readme.io/b90bbd6e3bea9dd862808343896b005071b7d9e564d31039c188c3ebf8e81077-360002254489.png)

1.OneLink

次の場合は**スタンダート計測リンク**を選択します：

* URLにディープリンクを使う必要がない
* ディープリンクに<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">URI スキーム</Anchor>のみを使用する予定である

次の場合は**OneLinkの使用**を選択してください。

* AndroidとiOSの両方のアプリで1つのリンクを共用する
* ユニバーサルリンクまたはapp linksを使用したディープリンク

OneLinkを選択すると、計測リンクがアプリのリンクから <Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLink URL</Anchor> に変わりますので注意ください。

2. Deeplink URL

この項目は、ディープリンクを使用してユーザーをアプリの特定のアクティビティに遷移する場合に使用します。  
**計測リンクパラメータ**： af\_ad

3.リエンゲージメント期間

リエンゲージメント後に、ユーザーのアプリ内イベントがリターゲティングメディアソースに紐付けされる期間を設定します。値は、日数 (1-90)、時間 (最大23)、またはライフタイムで設定できます。

**計測リンクパラメータ**：af\_reengagement\_window

<div id="click-through-attribution" />

### クリックスルーアトリビューション

このスライダーでは**クリックからインストールまでの最大有効期間**を設定できます。ルックバック期間内に発生するインストール（初回起動）のみがGMPの成果に紐づきます。

**計測リンクのパラメータ：** af\_click\_lookback

クリックルックバック期間の詳細については<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">こちら</Anchor>を参照してください。

[![](https://files.readme.io/930deba7817e7ede9504624111c3190dcd01a1f6dfb626463a844fcaa2d66930-360002254509.png)](https://files.readme.io/930deba7817e7ede9504624111c3190dcd01a1f6dfb626463a844fcaa2d66930-360002254509.png)

<div id="click-attribution-link" />

### クリックアトリビューションリンク

このリンクは、あなたが設定したすべての情報が含まれる計測リンクです。ユーザーが対応する広告をクリックした際にアクティベートされるように、この計測リンクをYouAppiに入稿してください。

<div id="view-through-attribution-lookback-window" />

### ビュースルーアトリビューションルックバック期間

このスライダーでは、 **インプレッションからインストールまでの最大有効期間**を設定できます。広告のインプレッション後、ほかに関連する広告がクリックされなかった場合、このルックバック期間内に発生したインストール（初回起動）のみが YouAppi に紐付けられます。

この値は1～23時間または1～7日間で設定できます。

**計測リンクパラメータ**： af\_viewthrough\_lookback

ビュースルー計測の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">こちら</Anchor>を参照してください。

[![](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)

<div id="impressions-attribution-link" />

### インプレッションのアトリビューションリンク

インプレッションアトリビューションリンクは、異なるルックバック期間を除いて、クリック記録リンクと同様のアトリビューションデータを含んでいます。このリンクをYouAppi に入稿すると、媒体によりますが、通常、該当する広告を1秒以上見た時に有効になります。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

AppsFlyerはコストの詳細をAPIで取得します。サポートされているディメンション、指標、機能の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">アドネットワークのコスト連携に関する表</Anchor>を参照してください。　**注意**：コストデータの取得にはROI360のご契約が必要です。

**コストAPIを有効にする方法**：

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">これらの連携手順</Anchor>に従ってください。

<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiのステータス">コストAPIのステータス</Anchor>と一致するコストデータを引き出すことができた最後の時刻を、AppsFlyerがコスト（および広告収益）連携ステータス管理画面、または個別のアドネットワーク管理画面のいずれかで確認してください。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

広告収益データはこのパートナーではサポートしていません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

データにアクセスし、さまざまなアクションを実行するためにAwinに付与するアクセス許可を選択します。

<div id="note-1" />

> 📘 **注**
>
> 権限トグルがオンの状態で連携が<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">非アクティブ化</Anchor>された場合でも、権限は付与されたままです。

</Accordion>

<div data-zendesk-anchors="h_01HKA0TGE08PJDBQHFER5ZZ785=setting-up-glispa h_01HHVXZ7FSGDRCECE93ZF69VMS=%E3%83%92%E3%83%B3%E3%83%88 h_01HHVXZ7FSZ7W855TSN5TSPD0G=integration-tab activate-partners=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HHVXZ7FSJ0PS5KQ0YZHVSFKF=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HHVXZ7FSM5PT4VJRGVWDBRDK=%E6%B3%A8%E6%84%8F general-settings=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A h_01HHVXZ7FSDF06G1848W0YH8W6=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HHVXZ7FS0DEZPEEH7D68SH0B=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-events-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HHVXZ7FS47Y4T3KDR732WCE6=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HHVXZ7FSX2TJC13GT3TGR7ZK=attribution-link-tab attribution-link-parameters=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC h_01HHVXZ7FSCE4NP1XC0ZJ81858=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC retargeting-settings=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E8%A8%AD%E5%AE%9A h_01HHVXZ7FSAVKE25TSS98RMK8V=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E8%A8%AD%E5%AE%9A clickthrough-attribution=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HHVXZ7FTE8EZYBA4HS45MFAR=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 click-attribution-link=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF h_01HHVXZ7FTP962PWNMEEDB31H5=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF viewthrough-attribution-lookback-window=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01HHVXZ7FT8HVSEXB5YWABPXNA=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 impressions-attribution-link=%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF h_01HHVXZ7FT7V6M8VC69EYRK700=%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF h_01HHVXZ7FT9W1RN6P06JE53S7X=cost-tab h_01HHVXZ7FTGSKZCB57RT9GPYC9=ad-revenue-tab h_01HHVY4WHSM3B33KYACR9DJ5ZW=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=%E6%B3%A8" />
