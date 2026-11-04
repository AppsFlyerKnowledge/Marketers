---
title: Unity Adsキャンペーン連携設定
metadata:
  keywords:
    - Unity Ads
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
  created_at: '2016-03-06T10:05:52Z'
  edited_at: '2026-10-14T09:36:32Z'
  id: 208005086
  locale: ja
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ja/articles/208005086
---
> **概要：** 概要： Unity Adsは、iOSおよびAndroid向けの動画広告ネットワークで、AppsFlyerの連携済みパートナーです。クリックベースのモバイルアトリビューションに加えて、Unity Adsはコスト、広告収益、ビュースルーアトリビューションを提供し、AppsFlyerで計測することができます。

Unity Adsでキャンペーンを設定するには、以下の手順に従ってください。

<div id="setting-up-unity-ads" />

## Unity Ads 連携設定

**前提条件：** 連携を設定する前に、 <Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーへ連絡</Anchor>し、アカウントを開設してください。

**連携を有効化または編集する：**

1. **有効化するには：** AppsFlyer管理画面 左メニュー **連携** > **Partner Marketplace**へ移動します。  
   **編集するには：** AppsFlyer管理画面左メニュー **連携** > **連携済みパートナー**を選択します。
2. パートナーを検索し選択してください。
3. **連携の設定**をクリックします。 連携の設定ページに移動します。
4. **連携**タブで、**パートナーを有効にする**トグルをオンにします。  
   <strong>注：このトグルは、このパートナーの連携を続ける限り、</strong>オン（有効）/strong>のままにしておく必要があります。
5. 以下の手順に従い、各タブの設定を完了してください。

連携、計測リンク、コスト、広告収益、および権限。次の項目をクリックすると各タブの設定に関する説明が表示されます。

連携済みパートナーの設定画面のヘッダーについての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>をクリックしてください。

> 👍 **ヒント**
>
> * 連携タブでの<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#d-general-settings">全般的な設定</Anchor>項目は、全てのパートナーにおいて**必須**です。
> * その他すべてのステップは、説明的または**任意**の設定です。

<div id="integration-tab" />

<Accordion title="連携タブ">

<div id="activate-partners" />

### パートナーの有効化

最初にこの画面を開く際に、連携を設定するには、まず**パートナーの有効化**トグルをオンにする必要があります。このパートナーと連携を続ける限り、トグルをオンにしておくして必要があります。  
パートナーの有効化についての詳細は、 <Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>をご覧ください。

<div id="general-settings" />

### 一般的な設定

**端末ID（広告ID）をUnityに送信する**

[連携] タブの上部には、「Unity Adsではインストールごとに端末IDを送信する必要がある」というメモがありますが、これは自動的に行われ、ユーザー側で何もする必要はありません。

[![Unity_msc_new_2.png](https://files.readme.io/4291f0b69f8231f6644872f2dfaec84e7c93047e81f653e76ff7266387fa10a9-360002583918.png)](https://files.readme.io/4291f0b69f8231f6644872f2dfaec84e7c93047e81f653e76ff7266387fa10a9-360002583918.png)

**Unity Ads Game ID**

Unity Adsでは、一意のゲームIDを介してAppsFlyerに接続する必要があります。**ゲームIDが分からない場合は、Unity Adsから直接入手するか、以下のスクリーンショットに示すように、ゲームをアップロードした後、** アプリ **> キャンペーンで見つけることができます。**

[![](https://files.readme.io/c3315765f33e957b82c39b638bb8113e207bfe80f242bf2e6dde3dce30287a6f-8109147574673.png)](https://files.readme.io/c3315765f33e957b82c39b638bb8113e207bfe80f242bf2e6dde3dce30287a6f-8109147574673.png)

Unity Adsプラットフォームは、アカウントレベルごとに 1つのアプリを 1つの Unity Ads ゲーム ID にマッピングします（広告主と代理店は同じアプリに対して異なるゲーム IDを持ちます）。Unity Adsプラットフォームの複数のアカウントで、同じアプリを異なるゲーム IDで実行することはできません。

**ビュースルー計測の有効化**

このオプションをオンにすると、Unity Adsからのビュースルーインストールを計測できます。ビュースルールックバック期間は、計測リンクタブ（下記参照）にて設定できます。

![Unity_ads_msc_new_3.png](https://files.readme.io/fab459ace7e8f1354d3bbfbca8ddefcd11376b7426a8e361abfab1b42b623880-360001875405.png)

<div id="default-postbacks" />

### デフォルトのポストバック

![Screen_Shot_2022-07-28_at_13.07.25.png](https://files.readme.io/a571ddc49e490373b34144e34626a18c6c18908cec3345cd7ac70c49aa855c05-7975491293329.png)

このセクションでは、これらのポストバックの送信を許可するユーザーを定義してください：

* **このパートナーのみ：** Unity Adsにアトリビューションされたユーザーからのイベントのみを送信
* **オーガニックを含むすべてのメディアソース：** ユーザーベース全体を Unity Adsに送信

<div id="note" />

> 📘 **注意**
>
> すべてのインストールネットワークとして、Unity Ads はアプリのすべての新規インストールのポストバックを任意のソースから受信することを好み、すべてのインストールポストバックを Unity Ads に送信するには [ **オーガニックを含むすべてのメディアソース** ] を選択することを推奨しています。

<div id="in-app-events-settings" />

### アプリ内イベントの設定

ポストバック経由でAppsFlyerイベントとパートナーをマッピングします。ポストバック送信が有効な場合、これには拒否されたアプリ内イベント（Protect360 によってブロックされたイベントや、ターゲット検証ルールに準拠していないと判断されたイベント）が含まれます。

[![](https://files.readme.io/e0d0af3c57c8452b646dfede7b4899215825ef8455d4e41293088f98ecc026eb-7975565240337.png)](https://files.readme.io/e0d0af3c57c8452b646dfede7b4899215825ef8455d4e41293088f98ecc026eb-7975565240337.png)

<div id="important" />

<div id="to-configure-in-app-event-postbacks" />

#### アプリ内イベントポストバックの設定方法

1. **game\_id**を入力してください。-game\_idが正しく、インストールアトリビューションに使用されているものと同じであることを確認してください。
2. **アプリ内イベントポストバック**を有効にします。
3. 必要に応じて、**アプリ内イベントポストバック期間**を設定してください（詳細については、<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#アプリ内イベントポストバック期間">アプリ内イベントポストバック期間の設定</Anchor>を参照してください）。
4. **イベントを追加**をクリックし、SDKまたはS2Sイベントをリストに追加してください。
5. 次のパラメーターを入力してください:

| パラメータ名 | 説明 |
| --- | --- |
| AppsFlyerイベント: | これは、アプリに連携されたSDKまたはサーバー間イベントからAppsFlyerが受信したイベントの名前です。<br />**ヒント：** お探しのイベントが見つかりませんか？<ul><li>デバイス上で非オーガニックインストールによってアプリ内イベントが発生しているかを確認し、再度チェックしてください。</li><li>**AppsFlyerイベント**にイベントを入力し、**カスタムイベントを作成**をクリックしてください。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">カスタムイベントのマッピング</Anchor>についてご参照ください。</li></ul> |
| **パートナー側のイベント名** | パートナー側で定義されている各イベントの固有の名前またはID。オプションは以下の通りです：<ul><li>**テキストフィールド：** 対応するイベントIDをパートナーから取得します。</li><li>**ドロップダウンボックス：** 最適な事前定義されたAppsFlyerイベントを選択します。</li><li>**そのまま**：イベント名のマッピングなしで、イベントをそのまま送信します。</li></ul> |
| **送信オプション** | 最適なイベントの送信オプションを選択します。<ul><li>**このパートナーのみ**: このイベントがこのパートナーに紐付いている場合にのみポストバックを送信します。</li><li>**オーガニックを含む全てのメディアソース**：オーガニックを含む全てパートナーに紐づいているイベントのポストバックを送信します。</li></ul> |
| **送信データ** | <ul><li>**データなし（デフォルト）：** イベント値なしでイベント自体のみを送信します。</li><li>**イベント値と収益：** 収益を**含む**アプリ内イベントに付随する全てのイベント値を送信します。</li><li>**イベント値のみ ：** 収益額**を除く**、すべてのパラメーターを送信します。</li></ul> |

<div id="note-1" />

> 📘 **注**
>
> Meta広告に広告収益のポストバックを送信すると、 <Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">広告収益</Anchor> データを使用してキャンペーンを最適化できます。
>
> * **イベント名：af\_ad\_revenue**

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

計測リンクを生成して保存し、特定のキャンペーン、広告セット、または単一の広告（UA およびリターゲティングキャンペーンの両方）のためにパートナーに送信できます。シングルプラットフォームリンクまたはOneLinkのいずれかを使用できます。  
詳細：<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">計測リンクの構成とパラメーター</Anchor>

**計測リンクを作成**するには、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">次の手順</Anchor>に従ってください。

**注：**

* Androidアプリのターゲットオーディエンスに子どもが含まれている場合、Unity はゼロにされた広告ID を送信します。
* 詳しくは、Unity Adsがクリック数とビューを定義する方法をご覧ください。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

AppsFlyerはコストの詳細をAPIで取得します。サポートされているディメンション、指標、機能の詳細は、アドネットワークのコスト連携に関する表/span><Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">を参照してください。</Anchor>

注意

* コストデータの取得にはROI360のご契約が必要です。
* 代理店コストは、クリック単価やAPIでサポートされていません。広告主はAd Spend Ingestionから代理店コストのデータを送信することができます。

**コストAPIを有効にする方法**：

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">これらの連携手順</Anchor>に従ってください。  
  **注記:**

<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiのステータス">コストAPIのステータス</Anchor>と、AppsFlyerがコスト（および広告収入）統合ステータスのダッシュボード、または個々の広告ネットワークのダッシュボードのいずれかで、一致するコストデータを引き出すことができた最終時刻が表示されます。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

この設定は、パブリッシャーとしてパートナーの広告をアプリ内で表示している場合のみ該当します。この設定を行うことにより、ユーザーの流入元別に広告とのエンゲージメントを測定することができ、最も収益性の高いソースを見つけることができます。

**広告収益APIを有効にする方法**：

* <Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">これらの連携手順</Anchor>に従ってください。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

このタブでは、特定のアクションを実行するための Unity Adsに付与する権限を選択できます。Unity Adsでアトリビューションが無効になっている場合でも、[権限] タブはアクティブであり、Unity Ads の権限を付与できます。  
詳細：<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">付与できる権限の詳細</Anchor>

</Accordion>

</Accordion>

<div data-zendesk-anchors="setting-up-unity-ads=unity-ads-%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01HAPVZ510GTJRY1NXE0T3SMR6=unity-ads-%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01HAPVZ5109NKD8GHD36EDN810=%E3%83%92%E3%83%B3%E3%83%88 h_01HAPVZ510KPB0HQS9X6R4BCWT=integration-tab activate-partners=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HAPVZ510BGQ4KZ3S6ZP0QRE8=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A h_01HAPVZ510EZ3HKJQVPMKHV5FH=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HAPVZ511MRQXKPC78HR61X9P=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HAPVZ511CCXS93Y714STGQ67=%E6%B3%A8%E6%84%8F inapp-events-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HAPVZ511CJ6JP49HYG9T6RPF=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A to-configure-inapp-event-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 h_01HAPVZ511RMEVNASSTJNXKCJG=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 h_01HAPVZ511AV30DEKMZ0YB5ZBD=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 h_01HAPVZ511PC45Q5FEXQMZ4MFC=%E6%B3%A8 h_01HAPVZ5110QVYGGCGQDHRJEQM=attribution-link-tab h_01HAPVZ511DSKFAKKNWTKV9522=cost-tab h_01HAPVZ5111WPRRMPF6GZJTRJS=ad-revenue-tab h_01HAPVZ511RBNY3HHSHJHJDPWG=permissions-tab" />
