---
title: Awinキャンペーン設定
metadata:
  keywords:
    - Advertisers
    - aarki
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-03-12T06:15:54Z'
  edited_at: '2026-10-14T09:28:10Z'
  id: 360000423105
  locale: ja
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/ja/articles/360000423105
---
> 概要：  Pinterestは、クリックベースのモバイルアトリビューションとビュースルーモバイルアトリビューションの両方を提供しています。さらに、Pinterestは、AppsFlyerで計測できるクリックベースのリターゲティングも提供しています。

<Image alt="Aarki-logo.png" src="https://files.readme.io/f3c0366b10049471106e18218c4ee668d656970768f7fba642e125a3c17ffda0-27311413456657.png" width="207px" />


**<span id="setting-up-aarki"></span>前提条件：** 連携を設定する前に、必ず<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーに連絡し</Anchor>、アカウントを開設してください。

**統合をアクティブ化または編集するには：**

1. **有効にする：** AppsFlyer管理画面左メニュー **コラボレーション**> **Partner Marketplace**を選択します。  
   **編集方法**：AppsFlyer管理画面左メニュー **コラボレーション** > **連携を有効にする**を選択します。
2. パートナーを検索し選択してください。
3. **連携の設定**をクリックします。連携の設定ページに移動します。
4. **連携**タブにて連携したいアプリを選択し、**パートナーを有効にする**をオンにしてください。  
   **注：パートナーと作業している間、トグルはオン**（有効）/strong>のままにしておく必要があります。
5. 以下の手順に従い、各タブの設定を完了してください。

次の項目をクリックすると各タブの設定に関する説明が表示されます。

連携済みパートナーの設定画面のヘッダーについての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>をクリックしてください。

> 👍 **ヒント**
>
> * 連携タブでの<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#d-general-settings">一般的な設定</Anchor>の項目は、全てのパートナーにおいて**必須**です。
> * その他すべてのステップは、説明的または**任意**の設定です。

<div id="integration-tab" />

<Accordion title="連携タブ">

### パートナーの有効化

<span id="01ECJ9TJKEFXN53XDEBJ5Z92SS"></span>このタブを**初めて**開く場合、連携タブのパラメーター設定を有効にするために**パートナーを有効にする**のトグルをオンにする必要があります。このパートナーと連携を続ける限り、トグルをオンにしておく必要があります。パートナーの有効化についての詳細は、 <Anchor target="_blank" href="/marketers/ja/docs/user-level-data-retention"><span id="01ECJ9TJKFY5Q8P4QS57HD44T3"></span>こちら</Anchor>をご覧ください。

> 📘 **注意**
>
> 全てのインストールデータを受信できるネットワークであるLINEは、オーガニックを含む全てのメディアソースに紐づく新規インストールのポストバック受信を希望しています。**All media sources, including organic** を選択し、全てのインストールポストバックをLINEに送信することを推奨します。

### 一般的な設定

<span id="01ECJ9TJKF9QBT98Z7XJM3H8F1"></span>**Partner ID（パートナーID）**

<span id="01ECJ9TJKFZN0WVXXS0B89CMBY"></span>**<span id="01ECJ9TJKF6R5F2K8VGMR7KFHN"></span>ビュースルー計測の有効化**

<span id="01ECJ9TJKFE4E8GZQ2EN3Z1SM4"></span>YouAppiでビュースルーインストールを計測したい場合は、このトグルをオンにしてください。ビュースルールックバック期間は、計測リンクタブ（下記参照）にて設定できます。

### デフォルトのポストバック

<span id="01ECJ9TJKFT13WB1T328ET3PGC"></span>ユーザーのインストールおよびリエンゲージメント後に、自動ポストバックを送信します。このセクションでは、これらのポストバックの**送信を許可するユーザー**を定義してください。

<span id="01ECJ9TJKFQH37DQZ3V3NAESRF"></span>AppLovinに紐づくユーザーからのイベントのみにするには、**このパートナーに紐づくイベントのみ**を選択します。[オーガニックを含む全メディアソース] を選択して、ユーザーベース全てをYouAppiにレポートできるようにします。

### アプリ内イベントの設定

<span id="01ECJ9TJKF6QKF23NRTA5VS8Y9"></span>このセクションでは、ポストバックを介して、AppsFlyerイベントをYouAppiとマッピングできます。

**アプリ内イベントポストバックを設定する：**

1. **アプリ内イベントポストバック**をオンにします。
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

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

<span id="01ECSMR3VTP3SVSP9YXGW526PA"></span>このタブでは、YouAppiのキャンペーン、広告セット、単一の広告レベルで計測したい計測リンクを作成できます。AppsFlyerでは作成された計測リンクは保存されませんのでご注意ください。

<span id="01ECJ9TJKFTGNEZ68AR6DGXJNA"></span>このタブは複数のセクションに分かれています。

### 計測リンクパラメーター

<span id="01ECJ9TJKFJRJ2BYN069CK80C8"></span>このセクションでは、計測リンクに追加したいパラメータを選択できます。

<span id="01ECJ9TJKG144FJ8R72S2XDKQS"></span>計測リンクにパラメータを追加すると、後でドリルダウン分析を実行できます。アトリビューションリンクですでに定義されているパラメーターは、それらと新しい値をここで追加することで編集できます。

* <span id="01ECJ9TJKGTPN4NF8CC66XBRRS"></span>**<span id="01ECJ9TJKGZP0D1TYCB5R8XJ80"></span>キャンペーン** - これを追加すると、YouAppiの成果をキャンペーン別に比較できます。**計測リンクパラメーター：c**
* <span id="01ECJ9TJKGSVH0XGW2R8HRDA4T"></span>**広告セット** - これを追加すると、特定のYouAppiのキャンペーンを広告セット別に比較できます。**計測リンクパラメーター： af\_adset**
* <span id="01ECJ9TJKGC25XCE8GEB04ZE0P"></span>**Ad Name**：特定のironSourceキャンペーンの特定の広告セット内の広告別に比較するために広告名を追加します。**計測リンクパラメーター： af\_ad**
* <span id="01ECJ9TJKGWG1QBKJ9MVW4Q5FG"></span>**Site ID**（サイトID）および **Sub Site ID**（サブサイトID）：サイトIDパラメータを設定すると、特定のパブリッシャーにインストールを紐づけられます。
* <span id="01ECJ9TJKGQPS0GAY5SY562VFS"></span>**Subscriber Parameter**（サブスクライバーパラメーター）：5つのサブスクライバーパラメーターに値を追加できます。

<span id="01ECJ9TJKGQN0Y1H6F2WNHRBCV"></span>計測リンクに他のパラメーターを追加するには、新しいパラメーター項目に入力入力してください。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">**<span id="01ECJ9TJKG3AQCMW2FDDZ7HWWB"></span>AppsFlyer計測リンクの構造とパラメーター**</Anchor>をご覧ください。

### リターゲティング設定

<span id="01ECJ9TJKG820HKXXZTS89ES65"></span>リターゲティングの設定が有効化されると、AppsFlyerではクリック計測リンクに<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">&<span id="01ECJ9TJKGRTSNR53S5XX76K61"></span>is\_retargeting=true</Anchor>を追加することで、リンクを新規ユーザー獲得用ではなく、リターゲティング 用の計測リンクとして認識します。

<span id="01ECJ9TJKGPRH6P36208EH0C44"></span>リターゲティングの設定が有効化されると、次の設定ページが表示されます。

<span id="01ECJ9TJKH63B6KS5WE93F0SMM"></span>1.OneLink

<span id="01ECJ9TJKHH7YZCNS0P0TT0B45"></span>次の場合は***スタンダート計測リンク***を選択します：

* <span id="01ECJ9TJKHCZFTSWGGC2XHW6N5"></span><span id="01ECJ9TJKHP90T48TJPV80AP2T"></span>URLにディープリンクを使う必要がない
* <span id="01ECJ9TJKHYPT6RQ5NTVPV8FA2"></span>ディープリンクに<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page"><span id="01ECSNC07ND552HVWJD2GF8YSD"></span>URI スキーム</Anchor>のみを使用する予定である

<span id="01ECJ9TJKH6GTCN390D87MYPHV"></span>次の場合は***Use OneLink* （OneLinkを使用）**を選択します。

* <span id="01ECJ9TJKHVJCE2XM6X6AJS4YY"></span><span id="01ECJ9TJKHSJAC8HW8YERAKDVC"></span>AndroidとiOSの両方のアプリで1つのリンクを共用する
* <span id="01ECJ9TJKH0W7PXF4EJKM20ZRQ"></span>ユニバーサルリンクまたはapp linksを使用したディープリンク

<span id="01ECJ9TJKHEDATPHFM1EN5NZFQ"></span>OneLinkを選択すると、計測リンクがアプリのリンクから <Anchor target="_blank" href="/marketers/ja/docs/onelink-guide"><span id="01ECJ9TJKHQTEYP3PPXHVWYF9V"></span>OneLink URL</Anchor> に変わりますので注意ください。

<span id="01ECJ9TJKH59CKTD3ZNMZ37W09"></span>2. Deeplink URL

<span id="01ECJ9TJKHKQMJFN1Z3G7JTN5V"></span>この項目は、ディープリンクを使用してユーザーをアプリの特定のアクティビティに遷移させる場合に使用してください。**<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">計測リンクのパラメータ：</Anchor> af\_dp AppsFlyerのディープリンクソリューションの詳細については、こちらのガイドを参照してください。**

<span id="01ECJ9TJKH1QVW9NG1P4JY165N"></span>3.リエンゲージメント期間

<span id="01ECJ9TJKHAZ5N1Y7NACJPMT4S"></span>リエンゲージメント後に、ユーザーのアプリ内イベントがリターゲティングメディアソースに紐付けされる期間を設定します。値は、日数 (1-90)、時間 (最大23)、またはライフタイムで設定できます。

<span id="01ECJ9TJKH449C02X1Y3ESR48Y"></span>**計測リンクパラメータ**：af\_reengagement\_window

### クリックスルーアトリビューション

<span id="01ECJ9TJKHGWANE9EGZZ0KKEX9"></span>このスライダーでは**クリックからインストールまでの最大有効期間**を設定できます。ルックバック期間内に発生するインストール（初回起動）のみがGMPの成果に紐づきます。

<span id="01ECJ9TJKHF1JQM37P7SAYP8G6"></span><span id="01ECJ9TJKHK7S19JDRMS3Z318C"></span>**計測リンクのパラメータ：** af\_click\_lookback

<span id="01ECJ9TJKHY557S7J91YTE5VH8"></span>クリックルックバック期間の詳細については<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows"><span id="01ECJ9TJKHWEDC7RP2ZHHPFDNV"></span>こちら</Anchor>を参照してください。

### クリックアトリビューションリンク

<span id="01ECJ9TJKJ6TJBPEP5JNEPYTVB"></span>このリンクは、あなたが設定したすべての情報が含まれる計測リンクです。ユーザーが対応する広告をクリックした際にアクティベートされるように、この計測リンクをYouAppiに入稿してください。

### ビュースルーアトリビューションルックバック期間

<span id="01ECJ9TJKJVDX13ZVFH8T5BVG7"></span>このスライダーでは、 **インプレッションからインストールまでの最大有効期間**を設定できます。広告のインプレッション後、ほかに関連する広告がクリックされなかった場合、このルックバック期間内に発生したインストール（初回起動）のみが YouAppi に紐付けられます。

<span id="01ECJ9TJKJ1JEA3HME63V9EWA0"></span>この値は1～23時間または1～7日間で設定できます。

<span id="01ECJ9TJKJB20VJH63A8NK3KGB"></span>**計測リンクパラメータ**： af\_viewthrough\_lookback

<span id="01ECJ9TJKJNTQ7AJVYKVWYMJNZ"></span>ビュースルー計測の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows"><span id="01ECJ9TJKJX8GHDCAW0QQYD4BV"></span>こちら</Anchor>を参照してください。

### インプレッションのアトリビューションリンク

<span id="01ECJ9TJKJ34K4MSK1BK687Q9Y"></span>インプレッションアトリビューションリンクは、異なるルックバック期間を除いて、クリック記録リンクと同様のアトリビューションデータを含んでいます。このリンクをYouAppi に入稿すると、媒体によりますが、通常、該当する広告を1秒以上見た時に有効になります。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

AppsFlyerはコストの詳細をAPIで取得します。サポートされているディメンション、指標、機能の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">アドネットワークのコスト連携に関する表</Anchor>を参照してください。　**注意**：コストデータの取得にはROI360のご契約が必要です。

**コストAPIを有効にする方法**：

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">これらの連携手順</Anchor>に従ってください。

<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiのステータス">コストAPIのステータス</Anchor>と一致するコストデータを引き出すことができた最後の時刻を、AppsFlyerがコスト（および広告収益）連携ステータス管理画面、または個別のアドネットワーク管理画面のいずれかで確認してください。

#### 要注意

<span id="01ECJ9TJKQX7K80360QJ9RACV1"></span>Snapの費用を設定した後は、重大な不一致や費用データの欠落の原因となる可能性があるため、実行中のキャンペーン、広告セット、または単一の広告の名前を変更しないでください。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

</Accordion>

<div id="01ECJ9TJKQNQBY77FTTFRZ0PGS" />

<div id="permissions-tab" />

<Accordion title="権限タブ">

<span id="01ECJ9TJKQ8FK7KPD84RHW11HQ"></span>このタブでは、パートナーがアドネットワークの場合、代理店の場合、または両方の場合に、MoPub に付与する権限を選択できます。MoPubのアトリビューションが無効になっている場合でも、権限タブはアクティブであり、MoPub に権限を付与することができます。

<span id="01ECJ9TJKQFJM45QTAMC6AJQW3"></span>これらのトグルを使用して、アプリごとにアドネットワークへの権限付与を設定してください：

### アドネットワークへの権限付与

* <span id="01ECJ9TJKQAHY9CZ2H3W09GQPZ"></span>***<span id="01ECJ9TJKQXT4HNE0HKH13F4SX"></span>パートナー連携の設定を許可する*** - パートナーに連携タブの設定（アプリ内イベントのポストバックを除く）を許可します。
* <span id="01ECJ9TJKQKZVDT6A960BMPW5Q"></span>***アプリ内イベントのポストバック設定を許可する*** - 連携タブでアプリ内イベントのポストバックをマッピングする設定をパートナーに許可します。
* <span id="01ECJ9TJKQYN16W3C8YYFM14XP"></span>***リテンションレポートへのアクセスを許可*** - パートナーのリテンションデータへのアクセスを許可します。
* <span id="01ECJ9TJKQQSP4G7H71AZBQMXW"></span>***リテンションレポートへのアクセスを許可する***  - このパートナー経由のロイヤルユーザーデータのみへアクセスを許可します。
* <span id="01ECJ9TJKQXG55YJGYJV9AZFNH"></span>**アプリ内イベント集計データへのアクセスを許可する** - このパートナー経由のアプリ内イベントデータのみへアクセスを許可します。
* <span id="01ECJ9TJKQ9809CG0G2QK43RGQ"></span>**収益集計データへのアクセス権限を許可する**‐ このパートナーに紐づく収益データのみへアクセスを許可します。
* <span id="01ECJ9TJKQZJGSVZMKFDHE2ACJ"></span>***Protect360管理画面へのアクセスを許可する*** - Protect360のデータへのアクセスを許可します（パートナーのデータのみ）。＜広告主がProtect360に申込みしている場合のみ＞

<span id="01ECJ9TJKQJ0Y1QQK4EM92C06V"></span>詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab"><span id="01ECJ9TJKQZ5ADC4QSTHP0KN95"></span>アドネットワークへの権限付与</Anchor>をご覧ください。

### 代理店の許可

<span id="01ECJ9TJKRNETK1FH4ZRSNE1V4"></span>これらのトグルを使用して、アプリごとに代理店への権限付与を設定してください。

* <span id="01ECJ9TJKRADJZ8B7KNZH0HSQQ"></span>***<span id="01ECJ9TJKR3ZRZX5W0KD91BFV3"></span>代理店権限付与*** - このメイントグルをオンにすると、代理店への権限に関する追加設定が表示されます。
* <span id="01ECJ9TJKRMQDVQV6EJAEC8DPG"></span>***アプリ内イベントのポストバック設定を許可する*** - 連携タブでアプリ内イベントのポストバックをマッピングする権限を許可します。
* <span id="01ECJ9TJKRF7NMH6E1NDZ57S0E"></span>オーガニック集計データへのアクセスを許可します。
* <span id="01ECJ9TJKRKVWZG0WYVK1533A9"></span>***リテンションレポートへのアクセスを許可*** - リテンションデータへのアクセスを許可します（代理店のデータのみ）。

<span id="01ECJ9TJKRMD549KXA59E682CH"></span><Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#代理店の許可"><span id="01ECJ9TJKRS878CPXQYSBAJCA1"></span>代理店への権限</Anchor>付与についての詳細は、こちらをご確認ください。

</Accordion>

<div data-zendesk-anchors="h_01HJR5M5C0P759S4X5SSJCY501=setting-up-aarki 01ECJ9SX6M89JYPTV72JMWYVFP=%E3%83%92%E3%83%B3%E3%83%88 h_01J4KVYPZMZWJKV6KZQHNBZV0T=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 01ECJ9TJKE15MJE7WS26VP52A0=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01J4KWRE6ECKEWEG4WP10N3BF7=%E6%B3%A8%E6%84%8F general-settings=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A 01ECJ9TJKFGQQVWA7SA3PRS690=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01ECJ9TJKF7G9KMGMGMAD414ZF=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-events-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A 01ECJ9TJKFWH38NKYPDEZR4FRV=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01J4KVYPZMF0CZMR1PTS97JNNJ=attribution-link-tab attribution-link-parameters=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC 01ECJ9TJKFD91X9DQXB8PV3840=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC retargeting-settings=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E8%A8%AD%E5%AE%9A 01ECJ9TJKGJF1FS642MEM6WX4A=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E8%A8%AD%E5%AE%9A clickthrough-attribution=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 01ECJ9TJKHWMXAZYWNMVPDS8NY=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 click-attribution-link=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF 01ECJ9TJKJ0EQE45TB9S0WS2ZB=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF viewthrough-attribution-lookback-window=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 01ECJ9TJKJ72AN26F2FQ8VVKQ4=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 impressions-attribution-link=%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF 01ECJ9TJKJZV9PADNEETA6GFRZ=%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF h_01J4KVYPZMEDPXBXYFVT85AJ67=cost-tab warning=%E8%A6%81%E6%B3%A8%E6%84%8F 01ECJ9TJKQ8A7BFZR3MJ5H35CA=%E8%A6%81%E6%B3%A8%E6%84%8F h_01J4KVYPZMQHGHDPEE1Q5M1KX8=ad-revenue-tab h_01J4KVYPZMRFMNCR61M4Z4388Y=permissions-tab ad-network-permissions=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E 01ECJ9TJKQ9E3A5863Z3TRVAWZ=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E agency-permissions=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AE%E8%A8%B1%E5%8F%AF 01ECJ9TJKQ0SAV4ZJB8DFRTE5C=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AE%E8%A8%B1%E5%8F%AF" />
