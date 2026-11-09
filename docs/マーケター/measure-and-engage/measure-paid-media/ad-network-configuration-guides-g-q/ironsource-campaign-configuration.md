---
title: ironSourceキャンペーンの設定
metadata:
  keywords:
    - Supersonic
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
  created_at: '2016-03-06T10:47:23Z'
  edited_at: '2026-10-14T09:30:22Z'
  id: 208005096
  locale: ja
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/ja/articles/208005096
---
> **概要**：AppsFlyerの連携パートナーであるironSourceは、アプリ開発者やデバイスメーカー、モバイル通信業者、広告主向けに、収益化、エンゲージメント、アナリティクス、ディスカバリーツールを構築しています。クリックに基づくモバイル計測に加えて、ironSourceでは、AppsFlyerで計測できるコスト、広告収益、リターゲティング、ビュースルー計測を提供しています。

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/ironsource.png?v=1" width="213px" />

<div id="note-1" />

<div id="note" />

> 📘 **注意**
>
> 全てのインストールデータを受信できるネットワークとして、ironSourceはオーガニックを含む全てのメディアソースに紐づく新規インストールについてポストバックを受信することを希望しています。そのためには、**全てのパートナーに紐づくイベント**を選択し、全てのインストールポストバックをironSourceに送信することを推奨します。

**前提条件:** **連携を設定する前に、必ず<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーに連絡して</Anchor>アカウントを開設してください。**

**連携を有効化または編集する方法：**

1. **有効にする：** AppsFlyer のサイドメニューから**共同作業** > **パートナー・マーケットプレイス**の順で選択します。  
   **編集方法：** AppsFlyer のサイドメニューから、 **共同作業** > **連携を有効にする**の順で選択します。
2. パートナーを検索し選択してください。
3. **連携設定** をクリックして、連携設定ページに移動します。
4. **連携**タブで、連携アプリを選択し、**パートナーの有効化**をオンにします。  
   **注意：** トグルは、パートナーと作業している間、オン<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">（有効）</Anchor>にしておく必要があります。
5. 以下の手順に従い、各タブの設定を完了してください。

連携、計測リンク、コスト、広告収益、および権限。次の項目をクリックすると各タブの設定に関する説明が表示されます。

連携済みパートナーの設定画面のヘッダーについての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>をクリックしてください。

> 👍 **ヒント**
>
> * 連携タブでの<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#d-general-settings">一般的な設定</Anchor>の項目は、全てのパートナーにおいて**必須**です。
> * その他すべてのステップは、説明的または**任意**の設定です。

<div id="integration-tab" />

<Accordion title="連携タブ">

<div id="activate-partners" />

### パートナーの有効化

この**最初の訪問** では、**パートナーのアクティブ化**トグルをオンにして、連携タブパラメーターの設定を有効にする必要があります。このパートナーと連携を続ける限り、トグルをオンにしておく必要があります。  
パートナーの有効化についての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>をご覧ください。

<div id="advanced-privacy" />

#### 高プライバシーポストバック

iOSアプリの場合のみ、 **高度なプライバシー(iOS 14.5+以降)** がオンになっている場合 、 ポストバックとレポートを介してironSource<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#b-advanced-privacy">と共有するデータを制御できます</Anchor> 。

<div id="transaction-id" />

### トランザクションID

<div id="note-2" />

> 📘 **注意**
>
> AppsFlyerとのSKAN相互運用については、ironSourceアカウントマネージャーに連絡して、 <Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/general/universal-skan-reporting/#step-1">MMPへのSKANデータの送信を有効にしてください</Anchor>。

<div id="general-settings" />

### 一般的な設定

**Advertiser ID**

ironSourceは、ユニークなadvertiser ID (6桁の数値) を使用してAppsFlyerと接続します。Advertiser ID持ちでない場合は、連携作業を続けるためにこのIDをironSourceから取得してください。それ以外の場合は、ID とパスワードをコピーして、それぞれの項目に貼り付けます。

<div id="install-and-re-engagement-attribution" />

### インストールとリエンゲージメントのアトリビューション

これら2つの切り替えにより、ironSourceの新規インストールへのアトリビューションと、広告を**閲覧** したが **クリックしなかった** ユーザーのアトリビューションが可能になります。<Anchor target="_blank" href="/marketers/ja/docs/measure-view-through-engagements">ビュースルーアトリビューション</Anchor>の詳細はこちら。

**新規インストールをアトリビューションするには：**

1. **ビュースルーアトリビューションのインストール計測**をオンにします。
2. **ビュースルー**ルックバック期間の長さは、[計測リンクタブ](/docs/ironsource-campaign-configuration#attribution-link-tab)で設定します。

**既存のユーザーの新しいリエンゲージメントを計測するには：**

1. **リエンゲージメント ビュースルー計測** をオンにします。
2. **ビュースルー**ルックバック期間の長さは、[計測リンクタブ](/docs/ironsource-campaign-configuration#attribution-link-tab)で設定します。

<div id="default-postbacks" />

### デフォルトのポストバック

ユーザーのインストールとリエンゲージメント後に、自動でironSourceにポストバックを送信します。このセクションでは、これらのポストバックの**送信を許可するユーザー**を定義してください。

**このパートナーのみ**を選択して、ironSourceの成果に紐づくユーザーのイベントのみを選択してください。  
**オーガニックを含む全メディアソースに紐づくイベント**を選択して、ironSourceにレポートできる全ユーザーベースを選択してください。

<div id="note-3" />

> 📘 **注意**
>
> 全てのインストールデータを受信できるネットワークとして、ironSourceはオーガニックを含む全てのメディアソースに紐づく新規インストールについてポストバックを受信することを希望しています。これを行うには、**オーガニックを含む全メディアソースに紐づくイベント もしくは オーガニック** を選択して、すべてのインストールポストバックを ironSource に送信します。

<div id="in-app-event-postbacks" />

### アプリ内イベントポストバック

ポストバック経由で送信されるBideaseイベントと一緒にアプリ内イベントのマッピングを設定します。

1. **アプリ内イベントポストバック**を有効にします。
2. **イベントを追加**をクリックして、SDK または サーバー間イベントをリストに追加してください。各項目の説明は以下を参照してください。  

| パラメーター名 | 説明 |
| --- | --- |
| **AppsFlyerイベント** | これは、アプリに連携されたSDKまたはサーバー間イベントからAppsFlyerが受信したイベントの名前です。<br />**ヒント：** お探しのイベントが見つかりませんか？<ul><li>非オーガニックインストールとして計測された端末上で、そのアプリ内イベントが発生しているかを確認し、再度チェックしてください。</li><li>**AppsFlyerイベント**にイベントを入力し、**カスタムイベントを作成**をクリックしてください。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">カスタムイベントマッピングの詳細をお読みください。</Anchor></li></ul> |
| **パートナー側のイベント名** | パートナー側で定義されている各イベントの固有の名前またはID。オプションは以下の通りです：<ul><li>**テキストフィールド：** 対応するイベントIDをパートナーから取得します。</li><li>**ドロップダウンボックス：** 最適な事前定義されたAppsFlyerイベントを選択します。</li><li>**そのまま**：イベント名のマッピングなしで、イベントをそのまま送信します。</li></ul> |
| **送信オプション** | イベントの送信オプションを選択します。<ul><li>**このパートナーのみ**:このイベントがこのパートナーに起因する場合にのみポストバックを送信します。</li><li>**オーガニックを含む全メディアソース**:すべてのイベントを送信：オーガニックを含む全てパートナーに紐づくイベントに対してポストバックを送信します。</li></ul> |
| **送信データ** | <ul><li>**データなし（デフォルト）：** イベント値なしでイベント自体のみを送信します。</li><li>**イベント値と収益：** 収益値を含む全てのイベントパラメーターを送信します（イベント内にある場合）。</li><li>**収益を除いたイベント値：** 収益値以外のすべてのパラメーターを送信します。</li></ul> |

3. [オプション] イベントの<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">条件を設定</Anchor>するには、<Image alt="conditional-iae-postbacks-icon.png条件を追加" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />アイコンをクリックします。
4. **連携を保存**をクリックします。
5. [オプション] 連携を保存した後、設定画面に留まりつつ、ほかのアプリ / OSの設定へ進みます。
   1. 左上隅のパートナー名下にあるアプリ名をクリックし、アプリ一覧を開きます。
   2. ドロップダウンリストから別のアプリを選択してください。
   3. 選択したアプリで、連携ステップを再度実施してください。

<div id="note-4" />

> 📘 **注意**
>
> * iOS アプリの場合のみ:ポストバックや<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">レポート</Anchor>を介してパートナーと共有されるデータのコントロールは、**高度なプライバシー（ iOS 14.5 以降）**<Anchor target="_blank" href="/marketers/ja/docs/tiktok-for-business-advanced-srn-integration-setup#高プライバシーポストバック">の切り替え状態</Anchor>によって異なります。
> * Meta広告に広告収益のポストバックを送信すると、 <Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">広告収益</Anchor> データを使用してキャンペーンを最適化できます。
>   * **イベント名：** af\_ad\_revenue

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

アトリビューションリンクを生成して保存し、特定のキャンペーン、広告セット、または単一の広告（UAおよびリターゲティングキャンペーンの両方）のためにパートナーに送信できます。シングルプラットフォームリンクまたは<Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLink</Anchor>のいずれかを使用できます。  
詳細：<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">計測リンクの構成とパラメーター</Anchor>

**計測リンクを作成**するには、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">次の手順</Anchor>に従ってください。  
参照：ironSourceのクリックとビューの定義

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

AppsFlyerはコストの詳細をAPIで取得します。サポートされているディメンション、指標、機能の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">アドネットワークコスト連携に関する表</Anchor>を参照してください。　**注：** コストデータの取得にはROI360のご契約が必要です。

**コストAPIを有効にするには**:

* これらの連携手順に従ってください。

<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiのステータス">コストAPIのステータスを表示</Anchor>と一致するコストデータを引き出すことができた最後の時刻を、AppsFlyerがコスト（および広告収益）連携ステータス管理画面、または個別のアドネットワーク管理画面のいずれかで確認してください。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

* S2S API連携での集計レベルレポート
* S2S APIによるデバイスレベル
* SDKによるインプレッションレベル
* S2S API経由のデバイスレベル + SDK経由のインプレッションレベル

詳細は、<Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution">広告収益の計測</Anchor>をご覧ください。

* <Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">これらの連携手順</Anchor>に従ってください。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

このタブでは、パートナーがアドネットワークの場合、代理店の場合、または両方の場合に、ironSourceに付与する権限を選択できます。ironSourceでの計測が無効になっている場合でも、権限タブはアクティブであり、ironSourceへの権限を管理できます。

これらのトグルを使用して、アプリごとにアドネットワークへの権限付与を設定してください：

<div id="ad-network-permissions" />

### アドネットワークへの権限付与

* **パートナー連携の設定を許可する** - パートナーに連携タブの設定（アプリ内イベントのポストバックを除く）を許可します。
* **アプリ内イベントのポストバック設定を許可する** - 連携タブでアプリ内イベントのポストバックをマッピングする設定をパートナーに許可します。
* **リテンションレポートへのアクセスを許可** - パートナーのリテンションデータへのアクセスを許可します。
* **リテンションレポートへのアクセスを許可する**  - このパートナー経由のロイヤルユーザーデータのみへアクセスを許可します。
* **アプリ内イベント集計データへのアクセスを許可する** - このパートナー経由のアプリ内イベントデータのみへアクセスを許可します。
* **収益集計データへのアクセス権限を許可する**‐ このパートナーに紐づく収益データのみへアクセスを許可します。
* **Protect360管理画面へのアクセスを許可する** - 広告主がProtect360機能を利用している場合、パートナーのProtect360データへアクセスを許可します。

詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">アドネットワークへの権限付与</Anchor>をご覧ください。

<div id="agency-permissions" />

### 代理店の許可

これらのトグルを使用して、アプリごとに代理店への権限付与を設定してください。

* **メインのトグル** - オンにすると、代理店への権限に関する追加設定が表示されます。
* **リテンションレポートへのアクセスを許可する** - 代理店の独自のリテンションレポートにのみアクセスできるようになります。
* **オーガニック集計データへのアクセスを許可します。**
* **アプリ内イベントのポストバック設定を許可する**：代理店に連携タブでアプリ内イベントのポストバックをマッピングする権限を許可します。

<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#代理店の許可">代理店への権限</Anchor>付与についての詳細は、こちらをご確認ください。

</Accordion>

</Accordion>

<div data-zendesk-anchors="h_01HKW1E1KBG121H7YJBW2SZS6E=%E6%B3%A8%E6%84%8F h_01HCFHXQQ8FRF8D22A85PDN1B1=%E3%83%92%E3%83%B3%E3%83%88 h_01HCFHXQQ8XYCKWPVTMK8HF165=integration-tab activate-partners=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HCFHXQQ8HCXPEWR4CWY55M2H=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 advanced-privacy=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HCFHXQQ8ABQYRSBGC7Z1F1SV=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF transaction-id=%E3%83%88%E3%83%A9%E3%83%B3%E3%82%B6%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3id h_01HCFHXQQ8Q3BX7GSGD5MH4QT8=%E3%83%88%E3%83%A9%E3%83%B3%E3%82%B6%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3id h_01HCFHXQQ8D26KT5E6YEQ50DA4=%E6%B3%A8%E6%84%8F-1 general-settings=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A h_01HCFHXQQ8J0ZC9FGCNTPMKHK6=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A install-and-reengagement-attribution=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%A8%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HCFHXQQ8V2E8982XRSY4G50F=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%A8%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HCFHXQQ8Q27JXG2V7G4XZX43=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HCFHXQQ8XZ6H3733GPR3ZFYE=%E6%B3%A8%E6%84%8F-2 inapp-event-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HCFHXQQ891GH196XFRXY8MYS=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HCFHXQQ8VF25W10CWQHTEAYW=%E6%B3%A8%E6%84%8F-3 h_01HCFHXQQ8AYNTCH9GHZJG594E=attribution-link-tab h_01HCFHXQQ87EBRW9NBY58XYFGP=cost-tab h_01HCFHXQQ8XZ8XQFH3XRFVHRZV=ad-revenue-tab h_01HCFHXQQ891P7ET9Q4BSQWJXT=permissions-tab ad-network-permissions=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E h_01HCFHXQQ86VNX9WRFEZECYV7R=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E agency-permissions=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AE%E8%A8%B1%E5%8F%AF h_01HCFHXQQ936CQ1FVHCRC58H4C=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AE%E8%A8%B1%E5%8F%AF" />
