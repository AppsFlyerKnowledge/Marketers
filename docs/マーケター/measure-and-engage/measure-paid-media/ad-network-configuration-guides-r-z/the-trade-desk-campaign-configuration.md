---
title: The Trade Deskのキャンペーン設定
metadata:
  keywords:
    - Advertisers
    - The Trade Desk
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-05-13T07:34:13Z'
  edited_at: '2026-10-14T09:20:24Z'
  id: 360000894849
  locale: ja
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ja/articles/360000894849
---
> **概要：** 概要：AppsFlyerの連携パートナーであるThe Trade Deskは、強化されたモバイル広告ソリューションを使用して、クロスデバイスユーザーのニーズを満たす戦略的でスケーラブルなスマートなキャンペーンを提供しています。The Trade Deskは、クリックベースのモバイルアトリビューションと、ビュースルーモバイルアトリビューション、そしてクリックベースのリターゲティングを提供しており、これらすべてをAppsFlyerで記録することができます。

<div id="setting-up-the-trade-desk-ttd" />

## The Trade Desk (TTD) の設定

AppsFlyerでキャンペーンの計測を有効にするには、次の手順に従いご設定ください。

<div id="step-1-define-conversion-events-in-ttd" />

<Accordion title="ステップ1:ステップ 1: TTD でコンバージョンイベントを定義する">

1. TTD広告主画面の左側のメニューで **データ** をクリックします。
2. 上部のメニューで **アプリデータの追加** をクリックします。
3. **アプリデータの作成** 画面で次の項目を入力します：
   * App name
   * オペレーティングシステム   
     **注記：** Note: TTDは、AndroidとiOSの両方のオプションでCTV計測をサポートしています。
   * **AppsFlyer**を選択します。
   * eventsイベント： **イベントを追加** をクリックしてコンバージョンイベントを追加し、以下項目を入力します：
     * EVENT\_NAME  
       **注記：** Note: 名前が大文字、スペース、記号を含め、AppsFlyerとまったく同じように入力されていることを確認してください。
     * このオプションには、アトリビューションとリターゲティングの両方が含まれます。
     * さらにイベントを追加するには、**イベントの追加** をクリックして手順を繰り返します。
   * **注記：**

     * キャンペーン中はこの選択を変更しないでください。
4. **アプリデータの作成** をクリックします。

</Accordion>

<div id="step-2-define-conversion-events-in-appsflyer" />

<Accordion title="ステップ2:ステップ2：AppsFlyerでコンバージョンイベントを定義する">

AppsFlyerがコンバージョンイベントを定義しイベントポストバックをTTDに送信するには、まず[AppsFlyerをTTDと連携](/docs/the-trade-desk-campaign-configuration#ttdとappsflyerの連携)し、以下の設定をセットアップしてください。

* 連携設定（イベントポストバックの構成を含む）
* 計測リンク
* 権限

</Accordion>

<div id="step-3-map-defined-conversion-events-from-appsflyer" />

<Accordion title="ステップ3:ステップ3：AppsFlyerから定義されたコンバージョンイベントをマッピングする">

1. TTDの左側のメニューで **キャンペーン** をクリックします。
2. **キャンペーン** まで下にスクロールし、リストからキャンペーンを選択します。
3. **レポートとアトリビューションの編集** をクリックします。
4. **コンバージョンデータソースを追加** をクリックします。
5. **コンバージョンデータソース** で **AppsFlyer** を選択または入力します。AppsFlyerイベントがTTDイベントにマッピングされるようになりました。
6. **クロスデバイスの概念：**
   * [ステップ 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd)（コンバージョンクレジットソース）でコンバージョンを TTDでアトリビューションすることを選択した場合は、ここで **世帯** （Household）を選択すると、利用可能なすべてのチャネル（モバイルアプリ内広告や CTV など）のコンバージョンが表示されます。
   * [ステップ 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd)でAppsFlyer を選択した場合は、ここで **なし**（None）を選択します。
7. **保存**をクリックします。

</Accordion>

<div id="step-4-add-click-and-impression-trackers-to-campaign-creatives" />

<Accordion title="ステップ4：ステップ 4：クリックトラッカーとインプレッショントラッカーをキャンペーンクリエイティブに追加する">

このステップでは、AppsFlyerで作成したクリックトラッカーとインプレッショントラッカーを TTD の各クリエイティブに追加します。

1. TTDの左側のメニューの **キャンペーン** で、上部のタブから **クリエイティブ** をクリックします。
2. 現在のキャンペーン紐付けられているクリエイティブのリストからクリエイティブを選択します。
3. **トラッキング** まで下にスクロールします。
4. AppsFlyerから[計測リンク](/docs/the-trade-desk-campaign-configuration#attribution-link-tab)（クリックスルーとビュースルー）をコピーし、**1x1 Pixel Impression Tracking**の各URL項目に貼り付けます。
5. **変更の保存** をクリックします。
6. キャンペーンに紐付けられているクリエイティブごとにこの手順を繰り返します。

</Accordion>

<div id="note" />

> 📘 **注意**
>
> [ステップ 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd) でコンバージョンを TTD でアトリビューションすることを選択した場合は、アトリビューション期間を編集できます：
>
> 1. TTDページの右側にあるアイコンのメニューから歯車をクリックして、 **広告主設定**を開きます。
> 2. **アトリビューション期間** まで下にスクロールし、右側の編集ボタンをクリックします。
> 3. **アトリビューションウィンドウの管理**ページで、アトリビューション期間を編集します：
> 4. **保存**をクリックします。

<div id="integrating-ttd-with-appsflyer" />

## TTDとAppsFlyerの連携

**前提条件:** **連携を設定する前に、必ず<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーに連絡して</Anchor>アカウントを開設してください。**

**連携を有効化または編集する方法：**

1. **有効にする：** AppsFlyer管理画面左メニュー **コラボレーション**> **Partner Marketplace**を選択します。  
   **編集するには：** AppsFlyer管理画面 左メニュー 連携 > **連携済みパートナー**を選択します。
2. パートナーを検索し選択してください。
3. **連携設定** をクリックして、 連携の設定ページに移動します。
4. **連携**タブにて、**パートナーを有効にする**トグルをオンにしてください。  
   **注: このトグルは、このパートナーの連携を続ける限り、オン（有効）のままにしておく必要があります。**
5. 以下の手順に従い、各タブの設定を完了してください。

次の項目をクリックすると、各タブの設定に関する説明が表示されます。

連携済みパートナーの設定画面のヘッダーについての詳細は、こちらをクリックしてください。

<div id="integration-tab" />

<Accordion title="連携タブ">

<div id="activate-partner" />

#### パートナーの有効化

最初にこの画面を開く際に、連携を設定するには、まず**パートナーの有効化**トグルをオンにする必要があります。TTDで配信している間、トグルはオンのままにしておく必要があります。  
パートナーの有効化についての詳細は、 <Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>をご覧ください。

<div id="advanced-privacy" />

#### 高プライバシーポストバック

iOS アプリの場合、<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">高度なプライバシーを有効にする</Anchor>トグルが表示されます。オンにすると、パートナーとのユーザー識別子の共有が制限されます。

<div id="general-settings" />

#### 一般的な設定

**トラッカーと広告主ID**

The Trade Deskは、一意のネットワークIDを介してAppsFlyerに接続します。Tracker\_ID と advertiserid をまだお持ちでない場合は、連携を続行するためにThe Trade Deskから入手する必要があります。

![TTD_General_Settings_.png](https://files.readme.io/f7f2b66556f2713ff56a3bd2fcfe6fe8fe8d346a9b322904f93670ee55cf94c3-50612291000849.png)

**ビュースルーアトリビューションの有効化：**

The Trade Deskからのビュースルーインストールを計測するには、**ビュースルーアトリビューションを有効にする** トグルをオンにします。ビュースルールックバック期間は、計測リンクタブ（下記参照）にて設定できます。

<div id="default-postbacks" />

#### デフォルトのポストバック

![default_postbacks_en-us.png](https://files.readme.io/b291c9fd4ac858723f3071bf271a041403639d49bfb1984030fc7c7306c40c16-50612291002385.png)

ユーザーインストールおよびリエンゲージメント後に、ポストバックをThe Trade Deskに自動送信します。このセクションでは、これらのポストバックの送信を許可するユーザーを定義してください：

* **このパートナーのみ**：The Trade Deskに成果が紐づくユーザーからのみのイベント向けです。
* **オーガニックを含むすべてのメディアソース：** ユーザーベース全体をThe Trade Deskにレポートできるようにします。

<div id="note-1" />

> 📘 **注意**
>
> すべてのインストールネットワークとして、The Trade Deskは、任意のソースからアプリのすべての新規インストールのポストバックを受信することを好み、すべてのインストールポストバックを The Trade Deskに送信するには、**オーガニックを含むすべてのメディアソース** を選択することをお勧めします。

<div id="in-app-events-settings" />

#### アプリ内イベントの設定

ポストバックを介してTTDを使用してAppsFlyerイベントをマッピングします。ポストバック送信が有効な場合、これには拒否されたアプリ内イベント（Protect360 によってブロックされたイベントや、ターゲット検証ルールに準拠していないと判断されたイベント）が含まれます。

![the_trade_desk_in_app_event_settings_en-us.png](https://files.readme.io/a72231e1f7d21eeb6ffd0b8e0ce056872ec7ef4670470a86e93eb7094ff9cea8-50612307447185.png)

**アプリ内イベントポストバックを設定する：**

1. advertiserid と **Tracker\_ID**を入力してください。
2. **アプリ内イベントポストバックを有効にします。**
3. 必要に応じて**アプリ内イベントポストバック期間**を設定してください（詳細は<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#アプリ内イベントポストバック期間">アプリ内イベントポストバック期間の設定</Anchor>を参照）。
4. 利用可能な場合は、イベントを自動的に送信するか、手動で送信するかを選択します。すべてのイベントをそのまま送信する方法についてはこちらをご参照ください。
5. **イベントを追加をクリックし、SDKまたはS2Sイベントをリストに追加してください。**
6. 必要なパラメーターを完了してください。
7. [オプション] <Image alt="" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />conditional-iae-postbacks-icon.png をクリックして、特定のアプリ内イベントをパートナーに送信するためのalt条件altを設定します。  
   <Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">アプリ内イベントポストバックの条件設定</Anchor>の詳細について。

| パラメータ名 | 説明 |
| --- | --- |
| **AppsFlyerイベント** | これは、アプリに連携されたSDKまたはサーバー間イベントからAppsFlyerが受信したイベントの名前です。<br />ヒントお探しのイベントが見つかりませんか？<ul><li>デバイス上で非オーガニックインストールによってアプリ内イベントが発生しているかを確認し、再度チェックしてください。</li><li>AppsFlyerイベントにイベントを入力し、**カスタムイベントを作成**をクリックしてください。カスタムイベントマッピングの詳細をお読みください。</li></ul> |
| **送信オプション** | イベントの送信オプションを選択してください:<ul><li>**このパートナーのみ**: このイベントがこのパートナーに紐付いている場合にのみポストバックを送信します。</li><li>**オーガニックを含む全メディアソース**：イベントがオーガニックを含む全てパートナーに紐づく場合にポストバックを送信します。</li></ul> |
| **送信データ** | <ul><li>**データなし（デフォルト）**： イベント値なしでイベント自体のみを送信します。</li><li>**値と収益**：**収益値を**含むすべてのイベントパラメーターを送信します。</li><li>**収益を含まない値**：収益値を**含まない全てのパラメーターを送信します。**</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

計測リンクを生成して保存し、TTD側に入稿することで、特定のキャンペーン、広告セット、または単一の広告（UAおよびリターゲティングキャンペーンの両方）をアトリビューションできます。シングルプラットフォームリンクまたは<Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLink</Anchor>のいずれかを使用できます。

<div id="attribution-link-parameters" />

#### 計測リンクパラメーター

アトリビューションリンクにパラメーターを追加すると、詳細なドリルダウン分析を実行できます。アトリビューションリンクですでに定義されているパラメーターは、それらと新しい値をここで追加することで編集できます。 アトリビューションリンクを保存すると、このタブで設定したすべてのパラメーターが保存されます。

アトリビューションリンクに追加するパラメーターを選択します。

![ttd_attribution_link_parameters_en-us.png](https://files.readme.io/2658797286fd7d922c68a9c2f1705166672066d4179d72cf4fe0039ac3ede212-50612291012625.png)

<div id="default-parameters" />

#### デフォルトのパラメーター

| 名前 | 説明 | パラメータ |
| --- | --- | --- |
| Site ID | サイトの ID パラメータを設定して、インストールを特定のパブリッシャーに結び付けます。パブリッシャー数が多い場合、<Anchor target="_blank" href="/marketers/ja/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">サイトIDの制限</Anchor>を越えないように、サイトIDの使用数を控えて、サブサイトIDパラメーターを使用することをおすすめします。 | af\_siteid |
| Campaign Name | キャンペーン名を追加して、TTDで実施されているさまざまなキャンペーンを比較します。 | c |
| Campaign ID | キャンペーン ID を追加します。 | af\_c\_id |
| Adset ID | 広告セットIDを追加して、広告セットごとのすべての広告のパフォーマンスを比較します。 | af\_adset |
| Ad ID | 広告 ID を追加します。 | af\_ad\_id |

計測リンクのパラメータはさらに追加できます。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">計測リンクの設定</Anchor>と<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">計測リンクの構造とパラメータ</Anchor>をご覧ください。

<div id="parameters-for-measuring-ctv" />

#### CTV計測のためのパラメータ

以下のパラメータと値を追加することで、AppsFlyerでCTVトラフィックを計測できます。

| パラメータ | 値 | 備考 |
| --- | --- | --- |
| リダイレクト | false |  |
| af\_xplatform\_vt\_lookback | 1h-72h | 1 - 72時間の間の任意の値を入力できます |

<div id="click-through-attribution" />

#### クリックスルーアトリビューション

![click-through_attribution_ttd_en-us.png](https://files.readme.io/9d8c4aed6aa5d8b3cba5b4e32a5245f4bd8b6d9cf50e8cc800dce66842487355-50612291014673.png)

スライダーを使用して、クリックからインストールまでの最大時間を設定してください。ルックバック期間内に行われたインストール（初回起動）のみがアトリビューションされます。

1〜23時間または1〜30日。

計測リンクパラメータ： af\_click\_lookback

<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">ルックバック期間</Anchor>の詳細をご覧ください。

クリックスルーアトリビューションリンクをコピーしてパートナーに送信し、リードが対応する広告をクリックしたときにアクティブにすることができます。

<div id="view-through-attribution" />

#### ビュースルーアトリビューション

![view-through_attribution_ttd_en-us.png](https://files.readme.io/7435384719e46f0534149ef41612db6ee54c930bab8e8eadc1fd86ae84d5d777-50612307451921.png)

スライダーを使用して、 インプレッションからインストールまでの最大時間を設定します。このルックバック期間内で、広告インプレッション後に他の関連広告がクリックされなかった場合のみ、インストール（初回起動）がパートナーにアトリビュートされます。

0 - 24時間

計測リンクパラメータ： af\_viewthrough\_lookback

ビュースルー計測についてご参照ください。

ビュースルーの計測フローリンクをコピーしてパートナーに送信し、リードが対応する広告をクリックしたときにアクティブにすることができます。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

The Trade Deskではコスト連携をサポートしていません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

The Trade Deskでは広告収益をサポートしていません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

このタブでは、The Trade Deskに付与する権限を、広告ネットワーク、代理店、またはその両方として機能するかどうかを選択できます。The Trade Deskのアトリビューションがオフになっている場合でも、権限タブはアクティブで、The Trade Deskに権限を付与することができます。

![](https://files.readme.io/8d8c3d5eb38384d92e52afdc01b0631d8fe5c9590dd618386cbf6ce90fc978f3-50612307452817.png)

これらのトグルを使用して、アプリごとにアドネットワークへの権限付与を設定してください：

<div id="ad-network-permissions" />

#### **アドネットワークへの権限付与**

* パートナー連携の設定を許可するアプリ内イベントのポストバックを除き、パートナーにインテグレーションタブの設定を許可します。
* アプリ内イベントのポストバックを許可する
* リテンションレポートへのアクセスを許可する
* 集計レベルのロイヤルユーザーデータへのアクセスを許可
* アプリ内イベントの集計データへのアクセス権限を付与する
* 集計収益データへのアクセス権限を付与する
* Protect360管理画面へのアクセスを許可する

詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">アドネットワークへの権限付与</Anchor>をご覧ください。

</Accordion>

<div data-zendesk-anchors="setting-up-the-trade-desk-ttd=the-trade-desk-ttd-%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HH2DHQWXTB9K2R07SJP1AXER=the-trade-desk-ttd-%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HH2DHQWX9Y6R1J3HPYWTAC2Z=step-1-define-conversion-events-in-ttd h_01HH2DHQWXTZ5EMJNYRGJMY7QA=step-2-define-conversion-events-in-appsflyer h_01HH2DHQWXCWF0H1GJGJS2YYDA=step-3-map-defined-conversion-events-from-appsflyer step-4-add-click-and-impression-trackers%C2%A0to-campaign-creatives=step-4-add-click-and-impression-trackers-to-campaign-creatives h_01HH2DHQWX1Z10PTRM8S7538YX=step-4-add-click-and-impression-trackers-to-campaign-creatives h_01HH2DHQWXX1EEARNBC61W3CDK=%E6%B3%A8%E6%84%8F integrating-ttd-with-appsflyer=ttd%E3%81%A8appsflyer%E3%81%AE%E9%80%A3%E6%90%BA h_01GFNDH51M6KYE39C7DJW3BJ8W=ttd%E3%81%A8appsflyer%E3%81%AE%E9%80%A3%E6%90%BA h_01GF8CKQYVDW5Z7141MJDGGW4C=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HH2DHQWYME21J7JV176N71P2=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 advanced-privacy=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HH2DHQWYFJB3ZCWVZZ048AQP=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF general-settings=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A h_01HH2DHQWYN3CZZCFT9X2R2N9J=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HH2DHQWY1GPVP5W5R4XV2H9C=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HH2DHQWY284121FR8HSFGH45=%E6%B3%A8%E6%84%8F-1 inapp-events-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HH2DHQWY0XM70BPE7222XE78=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HH2DHQWY7X522JKKC4A45BHN=attribution-link-tab attribution-link-parameters=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC h_01HH2DHQWY4GXPMCV5JEBFERG6=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC default-parameters=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC h_01HH2DHQWYZSECQWRQEKDB9KZH=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC parameters-for-measuring-ctv=ctv%E8%A8%88%E6%B8%AC%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_01HH2DHQWYZPKCY947MWK7GEAP=ctv%E8%A8%88%E6%B8%AC%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF clickthrough-attribution=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HH2DHQWYCFGJK4ZT9CXFX3X3=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 viewthrough-attribution=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HH2DHQWYP6S95MRAS39Q4RTT=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HH2DHQWYP5GYN2GH3C839P3N=cost-tab h_01HH2DHQWYG3KZTE0HH7QV4H6X=ad-revenue-tab h_01HH2DHQWYA9HAWT5PV092T6E9=permissions-tab ad-network-permissions=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E h_01HH2DHQWYCWYQFBDA19Z9BA8W=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E" />
