---
title: Awinキャンペーン設定
metadata:
  keywords:
    - Advertisers
    - Tyroo
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-03T11:32:42Z'
  edited_at: '2026-10-14T09:28:40Z'
  id: 208270836
  locale: ja
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ja/articles/208270836
---
> **概要：**

YouAppi を使ったキャンペーンを設定するには、以下の手順に従ってください。


**<span id="setting-up-tyroo"></span>前提条件:** **連携を設定する前に、必ず<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーに連絡して</Anchor>アカウントを開設してください。**

**連携を有効化または編集する方法：**

1. **有効にする：** AppsFlyer管理画面左メニュー **コラボレーション**> **Partner Marketplace**を選択します。  
   **編集方法**：AppsFlyer管理画面左メニュー **コラボレーション** > **連携を有効にする**を選択します。
2. パートナーを検索し選択してください。
3. **連携の設定**をクリックします。連携済みパートナー設定画面に移動します。
4. **連携**タブにて、**パートナーを有効にする**トグルをオンにしてください。  
   **注: このトグルは、このパートナーの連携を続ける限り、オン（有効）のままにしておく必要があります。詳細は、パートナーの有効化をご覧ください。**
5. 以下の手順に従い、各タブの設定を完了してください。

次の項目をクリックすると各タブの設定に関する説明が表示されます。

連携済みパートナーの設定画面のヘッダーについての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>をクリックしてください。

> 👍 **ヒント**
>
> * 連携タブでの<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#d-general-settings">一般的な設定</Anchor>の項目は、全てのパートナーにおいて**必須**です。
> * その他すべてのステップは、説明的または**任意**の設定です。

<div id="integration-tab" />

<Accordion title="連携タブ">

連携タブは次のセクションに分かれています。

### パートナーの有効化

この**最初の訪問** では、*パートナーのアクティブ化*トグルをオンにして、連携タブパラメーターの設定を有効にする必要があります。このパートナーと連携を続ける限り、トグルをオンにしておく必要があります。  
パートナーの有効化についての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>をご覧ください。

> 📘 **注意**
>
> 全てのインストールデータを受信できるネットワークであるLINEは、オーガニックを含む全てのメディアソースに紐づく新規インストールのポストバック受信を希望しています。そのためには、**全てのパートナーに紐づくイベント**を選択して、全てのインストールポストバックをLINEに送信してください。

### 一般的な設定

**Partner ID（パートナーID）**

**ビュースルー計測の有効化**

YouAppiでビュースルーインストールを計測したい場合は、このトグルをオンにしてください。ビュースルールックバック期間は、計測リンクタブ（下記参照）にて設定できます。

### デフォルトのポストバック

ユーザーのインストールおよびリエンゲージメント後に、自動ポストバックを送信します。このセクションでは、これらのポストバックの**送信を許可するユーザー**を定義してください。

AppLovinに紐づくユーザーからのイベントのみにするには、**このパートナーに紐づくイベントのみ**を選択します。 [オーガニックを含む全メディアソース]**を選択して、ユーザーベース全てをYouAppiにレポートできるようにします。**

### アプリ内イベントの設定

このセクションでは、TwitterへポストバックするAppsFlyerのイベントをマッピングできます。

1. アプリ内イベントポストバックを有効にしてください。
2. SDK に定義済みの全てのイベントに対して、送信オプションを選択してください。  
   **- このパートナーに紐づけられたイベントのみ**：このパートナーに紐づけられたユーザー**のみ**から発生したイベント  
   **- いずれかのパートナーまたはオーガニックに紐づけられたイベント**：ユーザーベース全体をパートナーに報告できるようにする場合に選択
3. **イベントを追加**をクリックして、SDKイベントをリストに追加してください。
4. 次のパラメーターを入力してください:

| パラメータ名 | 説明 |
| --- | --- |
| **SDKイベント名** | アプリと連携済みのSDKから、またはサーバー間（S2S）イベントからAppsFlyerが受信したイベント名  <br />**ヒント** - アプリ内イベント名がリストに表示されない場合、デバイス上で非オーガニックインストールによってアプリ内イベントが発生しているかを確認してください。 |
| **パートナー側のイベント名** | Apple側で定義されている各イベントの一意の名前またはID。   <br />対応するEvent IDをironSourceから取得してこのテキストフィールドに設定してください。 |
| **収益値を送信** | **チェックなしの場合** - リッチアプリ内イベントのすべてのパラメーターをパートナーに送りますが、**af\_revenue**パラメーターに含まれる収益パラメーターは送信しません。  <br />**チェックありの場合：** 収益値（イベントに存在する場合）を含むすべてのパラメーターをパートナーに送ります。 |

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
* **計測リンクパラメーター**： af\_adset
* **広告名** - これを追加すると、YouAppiの特定のキャンペーン内の特定の広告セット内で、クリエイティブ別に成果を比較できます。  
  **計測リンクパラメーター**： af\_ad
* **Site ID**（サイトID）および **Sub Site ID**（サブサイトID）：サイトIDパラメータを設定すると、特定のパブリッシャーにインストールを紐づけられます。パブリッシャー数が多い場合、<Anchor target="_blank" href="/marketers/ja/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">サイトIDの制限</Anchor>を越えないように、サイトIDの使用数を控えて、サブサイトIDパラメーターを使用することをおすすめします。  
  **計測リンクパラメーター**： af\_siteid、af\_sub\_siteid
* **Subscriber Parameter**（サブスクライバーパラメーター）：5つのサブスクライバーパラメーターに値を追加できます。これらのパラメーターは解析されローデータレポートに表示されるため、データの集約やフィルタリングに非常に便利です。  
  **計測リンクパラメーター**： af\_sub1、af\_sub2、af\_sub3、af\_sub4、af\_sub5

計測リンクに他のパラメーターを追加するには、新しいパラメーター項目に入力入力してください。詳細は、**<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">AppsFlyer計測リンクの構造とパラメーター</Anchor>** をご覧ください。

### クリックスルーアトリビューション

このスライダーでは**クリックからインストールまでの最大有効期間**を設定できます。ルックバック期間内に発生するインストール（初回起動）のみがGMPの成果に紐づきます。

**計測リンクのパラメータ：** af\_click\_lookback

クリックルックバック期間の詳細については<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">こちら</Anchor>を参照してください。

### クリックアトリビューションリンク

このリンクは、あなたが設定したすべての情報が含まれる計測リンクです。ユーザーが広告をクリックしたときに有効になるように、Liftoffへ入稿してください。

### ビュースルーアトリビューションルックバック期間

このスライダーでは、 **インプレッションからインストールまでの最大有効期間**を設定できます。広告のインプレッション後、ほかに関連する広告がクリックされなかった場合、このルックバック期間内に発生したインストール（初回起動）のみがTwitterの成果に紐づきます。

この値は1～23時間または1～7日間で設定できます。

**計測リンクパラメータ**： af\_viewthrough\_lookback

ビュースルー計測の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">こちら</Anchor>を参照してください。

### インプレッションのアトリビューションリンク

インプレッションアトリビューションリンクは、異なるルックバック期間を除いて、クリック記録リンクと同様のアトリビューションデータを含んでいます。このリンクをYouAppi に入稿すると、媒体によりますが、通常、該当する広告を1秒以上見た時に有効になります。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

このパートナーとの連携では、広告収益はサポートされていません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

このタブでは、パートナーがアドネットワークの場合、代理店の場合、または両方の場合に、MoPub に付与する権限を選択できます。MoPubのアトリビューションが無効になっている場合でも、権限タブはアクティブであり、MoPub に権限を付与することができます。

これらのトグルを使用して、アプリごとにアドネットワークへの権限付与を設定してください：Ad Network Permissions（アドネットワークへの権限）

* ***パートナー連携の設定を許可する*** - パートナーに連携タブの設定（アプリ内イベントのポストバックを除く）を許可します。
* *アプリ内イベントのポストバック設定を許可する* - 連携タブでアプリ内イベントのポストバックをマッピングする設定をパートナーに許可します。
* ***リテンションレポートへのアクセスを許可*** - パートナーのリテンションデータへのアクセスを許可します。
* ***リテンションレポートへのアクセスを許可する***  - このパートナー経由のロイヤルユーザーデータのみへアクセスを許可します。
* ***アプリ内イベント集計データへのアクセスを許可する** -* このパートナー経由のアプリ内イベントデータのみへアクセスを許可します。
* ***収益集計データへのアクセス権限を許可する***‐ このパートナーに紐づく収益データのみへアクセスを許可します。
* ***Protect360管理画面へのアクセスを許可する*** - Protect360のデータへのアクセスを許可します（パートナーのデータのみ）。＜広告主がProtect360に申込みしている場合のみ＞

詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">アドネットワークへの権限付与</Anchor>をご覧ください。

</Accordion>

<div data-zendesk-anchors="h_01HJZTZ361TE694SVPQTN8Q4C1=setting-up-tyroo h_01HJZTZ361YQ2J53C0HEJ4QRB4=%E3%83%92%E3%83%B3%E3%83%88 h_01HJZTZ361V5G81NBA1G0ZBXJG=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HJZTZ361FKYED35K4E57DEJ4=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HJZTZ361QM6Z3N693N3PJ1Z9=%E6%B3%A8%E6%84%8F general-settings=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A h_01HJZTZ362XG66Q54JRATHJW9X=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HJZTZ3621ZWG5TZD76Z80DHE=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-events-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HJZTZ362WMPD0C1HMG8HC2HD=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HJZTZ3627FHZS6J5FABPJJ1Q=attribution-link-tab attribution-link-parameters=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC h_01HJZTZ362TG648JZEXWX3MK5P=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC clickthrough-attribution=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HJZTZ362TCHGN0MGRA0B9Z7P=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 click-attribution-link=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF h_01HJZTZ36282E6VNNH740AF9EW=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF viewthrough-attribution-lookback-window=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01HJZTZ362V11V157Q2NFN550W=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 impressions-attribution-link=%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF h_01HJZTZ362ZF2FY83NMD5ZJ89J=%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF h_01HJZTZ362JBBAZ5RDWJ03EE2X=cost-tab h_01HJZTZ36323B1PET2X3FPD1H1=ad-revenue-tab h_01HJZTZ3637M1AMNTWXV9NPNGV=permissions-tab" />
