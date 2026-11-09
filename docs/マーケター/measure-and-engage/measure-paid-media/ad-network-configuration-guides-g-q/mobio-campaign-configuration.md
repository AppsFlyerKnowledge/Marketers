---
title: Awinキャンペーン設定
metadata:
  keywords:
    - mobio
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
  created_at: '2016-06-20T13:07:24Z'
  edited_at: '2026-10-14T09:33:23Z'
  id: 209587526
  locale: ja
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/ja/articles/209587526
---
> **概要：** クリックに基づくモバイル計測に加えて、ironSourceでは、AppsFlyerで計測できるコスト、広告収益、リターゲティング、ビュースルー計測を提供しています。

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobio.png?v=1" />


**<span id="setting-up-mobio"></span>前提条件:** **連携を設定する前に、必ず<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーに連絡して</Anchor>アカウントを開設してください。**

**連携を有効化または編集する方法：**

1. **有効にする：** AppsFlyer のサイドメニューから**共同作業** > **パートナー・マーケットプレイス**の順で選択します。  
   **編集方法：** AppsFlyer のサイドメニューから、 **共同作業** > **連携を有効にする**の順で選択します。
2. パートナーを検索し選択してください。
3. **連携設定** をクリックして、連携設定ページに移動します。
4. **連携**タブで、連携アプリを選択し、**パートナーの有効化**をオンにします。  
   **注意：** トグルは、パートナーと作業している間、オン<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">（有効）</Anchor>にしておく必要があります。
5. 以下の手順に従い、各タブの設定を完了してください。

次の項目をクリックすると各タブの設定に関する説明が表示されます。

連携済みパートナーの設定画面のヘッダーについての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>をクリックしてください。

<div id="tip" />

> 👍 **ヒント**
>
> * 連携タブでの<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#d-general-settings">一般的な設定</Anchor>の項目は、全てのパートナーにおいて**必須**です。
> * その他すべてのステップは、説明的または**任意**の設定です。

<div id="integration-tab" />

<Accordion title="連携タブ">

連携タブは次のセクションに分かれています。General Settings（一般的な設定）

<div id="activate-partner" />

### パートナーの有効化

この画面を**最初に開く**際には、以下のトグルをオンにする必要があります。[***パートナーを有効にする***] トグルをオンにして、連携タブのパラメーター設定を有効にします。このパートナーと連携を続ける限り、トグルをオンにしておく必要があります。  
パートナーの有効化についての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>をご覧ください。

<div id="default-postbacks" />

### デフォルトのポストバック

ユーザーのインストールおよびリエンゲージメント後に、自動ポストバックを送信します。このセクションでは、これらのポストバックの**送信を許可するユーザー**を定義してください。

AppLovinに紐づくユーザーからのイベントのみにするには、**このパートナーに紐づくイベントのみ**を選択します。

<div id="in-app-events-settings" />

### アプリ内イベントの設定

このセクションでは、ポストバックを介して、AppsFlyerイベントをYouAppiとマッピングできます。

1. アプリ内イベントのポストバックのトグルをONにしてください。
2. SDK に定義済みの全てのイベントに対して、送信オプションを選択してください。  
   **- このパートナーに紐づけられたイベントのみ**：このパートナーに紐づけられたユーザー**のみ**から発生したイベント  
   **- いずれかのパートナーまたはオーガニックに紐づけられたイベント**：ユーザーベース全体をパートナーに報告できるようにする場合に選択
3. **イベントを追加**をクリックして、SDKイベントをリストに追加してください。
4. 次のパラメーターを入力してください:

| パラメータ名 | 説明 |
| --- | --- |
| **SDKイベント名** | アプリと連携済みの SDK から、またはサーバー間（S2S）イベントから AppsFlyer が受信したイベント名  <br />**ヒント** - アプリ内イベント名がリストに表示されない場合、デバイス上で非オーガニックインストールによってアプリ内イベントが発生しているかを確認してください。 |
| **パートナー側のイベント名** | Apple側で定義されている各イベントの一意の名前またはID。   <br />対応するEvent IDをironSourceから取得してこのテキストフィールドに設定してください。 |
| **収益値を送信** | **チェックなしの場合** - リッチアプリ内イベントのすべてのパラメーターをパートナーに送りますが、**af\_revenue** パラメーターに含まれる収益パラメーターは送信しません。  <br />**チェックありの場合：** 収益値（イベントに存在する場合）を含むすべてのパラメーターをパートナーに送ります。 |

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

計測リンクに他のパラメーターを追加するには、新しいパラメーター項目に入力入力してください。詳細は、**<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">AppsFlyer計測リンクの構造とパラメーター</Anchor>** をご覧ください。

<div id="click-through-attribution" />

### クリックスルーアトリビューション

このスライダーでは**クリックからインストールまでの最大有効期間**を設定できます。ルックバック期間内に発生するインストール（初回起動）のみがGMPの成果に紐づきます。

**計測リンクのパラメータ：** af\_click\_lookback

クリックルックバック期間の詳細については<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">こちら</Anchor>を参照してください。

<div id="click-attribution-link" />

### クリックアトリビューションリンク

このリンクは、あなたが設定したすべての情報が含まれる計測リンクです。ユーザーが広告をクリックしたときに有効になるように、Liftoffへ入稿してください。

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

<Accordion title="権限タブ">

このタブでは、パートナーがアドネットワークの場合、代理店の場合、または両方の場合に、MoPub に付与する権限を選択できます。MoPubのアトリビューションが無効になっている場合でも、権限タブはアクティブであり、MoPub に権限を付与することができます。

<div id="ad-network-permissions" />

### アドネットワークへの権限付与

* ***パートナー連携の設定を許可する*** - パートナーに連携タブの設定（アプリ内イベントのポストバックを除く）を許可します。
* ***アプリ内イベントのポストバック設定を許可する*** - 連携タブでアプリ内イベントのポストバックをマッピングする設定をパートナーに許可します。
* ***リテンションレポートへのアクセスを許可*** - パートナーのリテンションデータへのアクセスを許可します。
* ***リテンションレポートへのアクセスを許可する***  - このパートナー経由のロイヤルユーザーデータのみへアクセスを許可します。
* ***アプリ内イベント集計データへのアクセスを許可する** -* このパートナー経由のアプリ内イベントデータのみへアクセスを許可します。
* ***収益集計データへのアクセス権限を許可する***‐ このパートナーに紐づく収益データのみへアクセスを許可します。
* ***Protect360管理画面へのアクセスを許可する*** - Protect360のデータへのアクセスを許可します（パートナーのデータのみ）。＜広告主がProtect360に申込みしている場合のみ＞

詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">アドネットワークへの権限付与</Anchor>をご覧ください。

<div id="agency-permissions" />

### 代理店の許可

これらのトグルを使用して、アプリごとに代理店への権限付与を設定してください。

* ***代理店権限付与*** - このメイントグルをオンにすると、代理店への権限に関する追加設定が表示されます。
* ***リテンションレポートへのアクセスを許可*** - リテンションデータへのアクセスを許可します（代理店のデータのみ）。
* オーガニック集計データへのアクセスを許可します。
* ***アプリ内イベントのポストバック設定を許可する*** - 連携タブでアプリ内イベントのポストバックをマッピングする権限を許可します。

<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#代理店の許可">代理店への権限</Anchor>付与についての詳細は、こちらをご確認ください。

</Accordion>

<div data-zendesk-anchors="h_01HKW34PW1Y7S78Z05CNZPGV7J=setting-up-mobio h_01HKW34PW12V6JMYTFG61324AG=%E3%83%92%E3%83%B3%E3%83%88 h_01HKW34PW18K29N92EAC2Q3D9E=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HKW34PW1HDFQ8YEF9XR8HFG9=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HKW34PW1SJPB24MBD9BXBDJ9=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-events-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKW34PW178WVKP0M3032R2H9=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKW34PW20BNZYP8KAZA6B0CG=attribution-link-tab attribution-link-parameters=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC h_01HKW34PW212DPA337Y60HB979=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC clickthrough-attribution=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HKW34PW2ZV9BGDD5Q9E48ABA=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 click-attribution-link=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF h_01HKW34PW2ASJ1Q12SKDYH1EPV=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF h_01HKW34PW2MVBPEE4KXCCZ1V1J=cost-tab h_01HKW34PW2M447QXS82266Y497=ad-revenue-tab h_01HKW34PW28TK2Z5Y8817E16D1=permissions-tab ad-network-permissions=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E h_01HKW34PW2A8FKTCR03WXDTPZ2=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E agency-permissions=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AE%E8%A8%B1%E5%8F%AF h_01HKW34PW2HPQJ5047R02AWX97=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AE%E8%A8%B1%E5%8F%AF" />
