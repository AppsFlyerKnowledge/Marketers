---
title: X広告（旧Twitter広告）連携設定
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:33:40Z'
  edited_at: '2026-10-14T09:24:55Z'
  id: 4410472471825
  locale: ja
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/ja/articles/4410472471825
---
> **概要：** X広告アカウントをAppsFlyerと連携して、X広告キャンペーンのアトリビューションデータを反映します。

<div id="overview" />

## 概要

X広告はアドバンスSRNであり、AppsFlyerは、広告IDを取得できないユーザーも含めて、すべてのユーザーのコンバージョンイベントを計測できます。

<div id="x-ads-attribution-flow-in-appsflyer" />

### AppsFlyerでのX広告の計測フロー

**X広告におけるAppsFlyer計測フロー：**

1. AppsFlyerは、サーバー間（S2S）連携を経由してX広告からすべてのエンゲージメント（広告接触）データを受け取り、次のようにアトリビューションします：
   * インストールイベントとエンゲージメント（広告接触）の両方にモバイル端末IDが含まれている場合、AppsFlyerは決定論的（ID）マッチングを実行します。
   * インストールまたはエンゲージメント（広告接触）のいずれかに端末IDがない場合、AppsFlyerは確率論的モデリング（PMOD）を適用してアトリビューションを行います。
2. AppsFlyerは、インストールがX広告の成果に紐づいているかどうかに関係なく、連携を通じてすべてのインストールポストバックをX広告に送信できます。
3. ユーザーがApp Tracking Transparency（ATT）の同意を拒否し、高プライバシーポストバック（AP）が有効になっている場合、X広告に送信されるポストバック内の特定のデータ項目が制限されます。制限されるデータ項目：

   * X広告のエンゲージメントID
   * ハッシュ化されたデバイスID
   * IPアドレス
   * ユーザーエージェント

   [![_- visual selection.png](https://files.readme.io/8c17755d275e732f88cf93e8e7e33df891911dd640d2dbfc2637313a9d59d43e-small-36433399199249.png)](https://files.readme.io/8c17755d275e732f88cf93e8e7e33df891911dd640d2dbfc2637313a9d59d43e-small-36433399199249.png)

<div id="connecting-your-x-ads-account-to-appsflyer" />

## X広告アカウントをAppsFlyerに接続する

<div id="h_01HDJVBAEZATGM580CNC7BCVTN" />

<div id="note" />

> 📘 **注**
>
> 開始する前に、X広告アカウントに<Anchor target="_blank" href="https://business.X%20Ads.com/en/help/account-setup/billing-basics.html">支払い方法</Anchor>が追加されていることを確認してください。これが完了していない場合はAppsFlyerでパートナー連携をアクティベートできません。

1. <Anchor target="_blank" href="https://business.x.com/en/advertising">X広告</Anchor>管理画面から、X広告アカウントにログインしてください。  
   [広告] ページが自動的に表示されない場合は、左上の [広告] ボタンをクリックします。
2. **Simple (NEW)** または **Advanced** キャンペーンのいずれかを選択するように求められたら、**Advaned** を選択します。
3. **キャンペーンの目的**で、**アプリインストール**または**アプリエンゲージメント**を選択し、**次へ**をクリックします。

   ![X-Ads-campaign-objective.png](https://files.readme.io/44e5aca3895fc5aefa22f91542b9c23f9798b246ac8086e97a3994244fc2c5a8-36433415100561.png)
4. アプリを選択し、**モバイル測定パートナー**をクリックします。
5. **コンバージョントラッキング**画面で、**AppsFlyerへ移動**をクリックします。

   ![X-Ads-mmp-selection.png](https://files.readme.io/718bc93d2fcf606a8c165aed70364659ba23b74891b22775c5522ee9e4c7901a-36433422307345.png)
6. X広告からAppsFlyerのウェブサイトに移動することを知らせるメッセージが表示されます。**AppsFlyerに移動**をクリックしてAppsFlyer管理画面にログインします。
7. AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー**へ移動します。
8. **X広告**を検索して選択します。
9. **連携**タブで、モバイルアプリコンバージョン計測（MACT）に関するX広告の利用規約に同意し、**設定を保存**をクリックします。
10. **パートナーを有効にする**をオンにし、**X広告でログイン**をクリックしてください。
11. **アプリを認証**をクリックして、AppsFlyerがTwitter広告アカウントを使用することを承認します。
12. **パートナー連携の有効化**をもう一度オンにして、**連携**タブの設定を表示し、アトリビューションを有効にします。  
    **注：** このトグルは、このパートナーとの作業を続ける限りオン（有効）のままにしておく必要があります。詳細は<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">パートナーの有効化</Anchor>を参照してください。
13. X広告アカウントを選択して有効化し、**保存して閉じる**をクリックします。

<div id="x-ads-attribution-setup" />

## X広告における計測の設定

連携済みパートナーの設定画面のヘッダーについての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">こちら</Anchor>をクリックしてください。

<div id="integration-tab" />

<Accordion title="連携タブ">

**連携タブ**は以下のセクションに分かれています。設定を有効にするために、初回訪問時に<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">パートナーを有効にする</Anchor>必要があります。

<div id="ad-account-connected" />

### 広告アカウントとの連携

アトリビューションを有効にする広告アカウントを選択してください。

![X-Ads_msc_new_4.png](https://files.readme.io/8b8ecdfd79bc87d4a65766ce67e48a06524d825e04d5e642eb5e9741069a2f6c-36433422308241.png)

**注記：** AppsFlyerでは最大200個の広告アカウントを接続できます。この上限に達しないようにし、すべてのアクティブなアカウントのアトリビューションを継続するために、使用されていない広告アカウントを削除することをお勧めします。

<div id="advanced-privacy" />

### 高プライバシーポストバック

iOSアプリのみ：<strong>高プライバシーポストバック（AP）</strong>のトグルを使用すると、ポストバックを介してX広告と共有するユーザーデータのレベルを制御できます。この設定は、iOS 14.5以降のプライバシー要件に準拠しています。  
高プライバシーポストバックがオンの場合：

* ポストバックは、<Anchor target="_blank" href="/partners/ja/docs/advanced-privacy-guide-postback-macros-for-ad-networks">高プライバシーポストバックテンプレート</Anchor>に従います。
* <Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">集計データと匿名データ</Anchor>のみが共有されます。デバイスレベルの識別子は含まれません。

<div id="note-1" />

> 📘 **注意**
>
> * 高プライバシーポストバックのトグルは、X広告の連携を有効にすると**デフォルトでオンに**なります。
> * X広告によると、高プライバシーポストバックを**オン**にすると、キャンペーンイベントが**過少にレポート**され、X広告のパフォーマンス最適化が制限される可能性があります。

<div id="click-through-attribution" />

### クリックスルー計測

スライダーを使用して、**クリックからインストールまでの最大時間**を設定してください。ルックバック期間内に発生するインストール（初回起動）のみがX広告の成果に紐づきます。

この値は、1～23時間または1～30日間のいずれかに設定できます。X広告管理画面の設定に合わせて、クリックスルーのルックバック期間を14日に設定することをお勧めします。

![X-Ads_msc_new_6.png](https://files.readme.io/359f6145751f45d38c151572f1ba0c525d232d16ffaee6b68453da0bc1826a69-36433422308369.png)

<div id="view-through-attribution-lookback-window" />

### ビュースルー計測のルックバック期間

スライダーを使用して、**インプレッションからインストールまでの最大時間**を設定できます。広告のインプレッション後、ほかに関連する広告がクリックされなかった場合、このルックバック期間内に発生したインストール（初回起動）のみが X広告に紐付けられます。

この値は1～23時間または1～7日間で設定できます。  X広告管理画面の設定に合わせて、ビュースルーのルックバック期間を1日に設定することをお勧めします。

![X-Ads_msc_new_7.png](https://files.readme.io/15c9d815b05c03dfdf8578ed5af297c411991ab74accc5539fc1dbca178c3336-36433422308497.png)

<div id="reinstall-settings" />

### 再インストール設定

再インストールのアトリビューションを有効にするには、**再インストール計測**トグルをオンにします。

再インストールアトリビューションには、インストールアトリビューション設定から値が適用されるため、ルックバック期間を設定する必要はありません。

<div id="re-engagement-settings" />

### リエンゲージメントCVの計測設定

Xでのリターゲティングキャンペーンの場合、AppsFlyerは**リエンゲージメントCV**計測のみをサポートしています。これは、アプリをすでにインストールしているユーザーによるリターゲティングキャンペーンとの接触を意味します。

<div id="important" />

> 🚧 **重要！**
>
> アプリ設定画面で、[リエンゲージメントCV計測] が有効になっていることを確認してください。詳細：<Anchor target="_blank" href="/marketers/ja/docs/app-settings#reengagement-attribution">こちら</Anchor>

X広告のリターゲティング計測は、リエンゲージメントコンバージョンのみが含まれます。

**リエンゲージメントCV計測**のトグルを有効にして、Xのリエンゲージメント計測を開始します。

<div id="re-engagement-click-through-lookback-window" />

#### リエンゲージメントCV：クリックスルーのルックバック期間

**リエンゲージメントCVのクリックスルー ルックバック期間**を設定します（広告がクリックされてからの最大期間。この期間内に、リターゲティングされたユーザーを広告に紐づけることができます）。値は、時間数（最大23時間）または日数（1～30日）を設定できます。

![X-Ads-reengagement-activate.png](https://files.readme.io/318deeab0432870035a163a7b8a5b8c03be7d683bfc369104c8577674fde0036-36433422309905.png)

<div id="re-engagement-view-through-lookback-window" />

#### リエンゲージメントCV - ビュースルー：ルックバック期間

リターゲティング広告のインプレッション計測を開始するには、**リエンゲージメントCV ビュースルーCV計測**の設定を有効にします。

**リエンゲージメントCV - ビュースルー：ルックバック期間**を設定します（広告が閲覧されてからの最大期間。この期間内に、リターゲティングされたユーザーを広告に紐づけることができます）。値は、時間数（最大23）または日数（1～7）を設定できます。

![X-Ads-reengagement-view-through.png](https://files.readme.io/4faf93b6d8a8e45043eb9440d8f56a70eba2da51f3a572ea6cd698e072f033c6-36433415112849.png)

<div id="re-engagement-window" />

#### リエンゲージメント期間

**リエンゲージメント期間**（アプリ内イベントをリターゲティング媒体の成果に紐づける期間）の長さを設定します。値は、日数（1～90）、時間数（最大23）または lifetime（ライフタイム）を設定できます。

<Image alt="X-Ads-reengagement-window.png" src="https://files.readme.io/5bc42bd967929a88fd38f8bdd9cc36046a6f0381d1883ab1f26f5c680185a74c-36433415113105.png" width="628px" />

<div id="ignore-active-users-for-retargeting" />

#### リターゲティング計測における休眠期間の設定

指定された期間内にアクティブユーザーのリターゲティングコンバージョンが記録されないように、非アクティブ期間を設定します。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-retargeting-inactivity-window">リターゲティング向けの休眠期間</Anchor>をご覧ください。

<div id="in-app-event-postback-settings" />

### アプリ内イベントのポストバック設定

このセクションでは、パートナーへポストバックするAppsFlyerのイベントをマッピングできます。

[![In-app_event_postbacks_en-us.png](https://files.readme.io/d89725172c53c309b5b58227ce53812e12f9cd4ee7611a6c375970b395122b15-36433415113361.png)](https://files.readme.io/d89725172c53c309b5b58227ce53812e12f9cd4ee7611a6c375970b395122b15-36433415113361.png)

**アプリ内イベントのポストバックを設定する：**

1. **パートナーID**を設定します（必要な場合）。
2. **アプリ内イベントポストバック**を有効にします。
3. **イベントを追加**をクリックし、SDKまたはS2Sイベントをリストに追加してください。
4. 以下の表に従って、必要なパラメータを入力します。  

| パラメータ | 説明 |
| --- | --- |
| **AppsFlyerイベント** | これは、アプリに連携されたSDKまたはサーバー間イベントからAppsFlyerが受信したイベントの名前です。<br />**ヒント：** お探しのイベントが見つかりませんか？<ul><li>デバイス上で非オーガニックインストールによってアプリ内イベントが発生しているかを確認し、再度チェックしてください。</li><li>**AppsFlyerイベント**にイベントを入力し、**カスタムイベントを作成**をクリックしてください。詳細：カスタムイベントマッピング</li></ul> |
| **このパートナーに紐づくCV** | パートナー側で定義されている各イベントの固有の名前またはID。ドロップダウンボックスから、最も適切な事前定義されたAppsFlyerイベントを選択してください。 |
| **送信オプション** | イベントの送信オプションを選択してください：<br /><br /><br /><br />**注**<br />Xが代理店運用（経由）のCVのポストバックを受け取るには、**オーガニックを含むすべてのメディアソース**を選択する必要があります。そうでなければ、X広告はX経由でCVしたポストバックのみを受け取ります。<ul><li>**このパートナーのみ：** このイベントがこのパートナーに紐付いている場合にのみポストバックを送信します。</li><li>**オーガニックを含むすべてのメディアソース：** すべてのパートナーとオーガニックイベントに紐付くイベントのポストバックを送信します。</li></ul> |
| **送信データ** | <ul><li>**データなし（デフォルト）：** イベント値なしでイベント自体のみを送信します。</li><li>**イベント値と収益：** 収益を**含む**アプリ内イベントに付随する全てのイベント値を送信します。</li><li>**イベント値のみ ：** 収益額**を除く**、すべてのパラメーターを送信します。</li></ul> |

5. [オプション] <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> をクリックして、特定のアプリ内イベントをパートナーに送信するための条件を設定します。  
   詳細：<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">アプリ内イベントポストバックの条件設定</Anchor>

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

X広告はアトリビューションに計測リンクを使用しません。

<div id="note-2" />

> 📘 **注意**
>
> Meta広告, Apple Search Ads, Adwords, X広告などのすべての<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns">セルフレポーティングネットワーク（SRN）</Anchor>では、外部計測リンクを使用しないため、このタブは機能しません。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

コスト連携では、以下の集計データを提供します：

* キャンペーン、広告セット、広告、チャネル、地域 / 国別のコストデータ。サポートされているディメンション、指標、機能の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">アドネットワークコスト連携に関する表</Anchor>を参照してください。  
  **注記：** コストデータの連携には<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>機能のご契約が必要です。
* クリック、インプレッションに関するデータ、及びキーワードやキャンペーン名、広告セットなどの補足データ。

**コストAPIを有効にするには：**

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">これらの連携手順</Anchor>に従ってください。

<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiのステータス">コストAPIのステータスを表示</Anchor>と一致するコストデータを引き出すことができた最後の時刻を、AppsFlyerがコスト（および広告収益）連携ステータス管理画面、または個別のアドネットワーク管理画面のいずれかで確認してください。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

X広告では広告収益計測はご利用いただけません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

このタブでは、パートナーがアドネットワークの場合、代理店の場合、または両方の場合に、X広告のメンバーに付与する権限を選択できます。X広告のアトリビューションが無効になっている場合でも、権限タブはアクティブであり、X広告に権限を付与することができます。

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

詳細：<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">アドネットワークへの権限付与</Anchor>

<div id="agency-permissions" />

### 代理店権限

<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#代理店の許可">代理店へアクセス許可を付与する</Anchor>方法をご覧ください。

</Accordion>

<div id="x-ads-features" />

## X広告の機能

<div id="mobile-app-promotion-on-x-ads" />

<Accordion title="X広告を使用したモバイルアプリのプロモーション">

X広告モバイルアプリプロモーションは、X上でアプリの広告を掲載する方法です。広告主は、インストールやアプリエンゲージメント、ディープリンクを促す魅力的なデザインのアプリカードを使用して、モバイルアプリをプロモーションできます。アプリユーザーは、Xタイムラインから直接手軽にアプリをインストールし、使い始めることができます。

</Accordion>

<div id="webtoapp-measuring-app-activity-for-nonapp-campaigns-android-only" />

<Accordion title="Web-to-App：非アプリキャンペーンのアプリアクティビティの計測（Androidのみ）">

AppsFlyerとX広告の連携では、Androidでの**非アプリキャンペーン**のインストール、リエンゲージメント、アプリ内イベントなどのアプリアクティビティを計測できます。

たとえば、広告のリンク先が**ウェブのランディングページ**であっても、アプリのインストールやその他のインストール後のアクティビティを計測できるため、Web-to-App（W2A）のユーザージャーニーを計測できます。

Xの非アプリキャンペーンからのアプリアクティビティを測定し、ユーザー行動に関する貴重なインサイトを取得するには、X広告マネージャーで次の手順を実行します：

1. X Ads Managerでキャンペーン作成フォームを開きます。
2. **配信**セクションで、**アプリコンバージョン**計測を有効にして、キャンペーンの結果発生したインストールとアプリ内コンバージョンの計測を有効にします。詳細については、<Anchor target="_blank" href="https://business.x.com/en/help/campaign-setup/create-an-app-installs-campaign/mobile-app-measurement-and-attribution">X Adsのドキュメント</Anchor>（*Measuring app conversions on non-app objectives*セクション）を参照してください。

<div id="important-1" />

> 🚧 **重要！**
>
> この機能は現在、**Android でのみ**サポートされています。

</Accordion>

<div id="twitter-ads-and-appsflyer-skan-interoperation" />

<Accordion title="X広告とAppsFlyerのSKAN相互運用">

X Adsは、SKAdNetworkのポストバックデータを専用のAPIで送信します。X AdsからのSKANデータは<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN計測数値</Anchor>に表示されます。

X Adsは、次のデータ項目を使用してSKANポストバックを強化します。

* Campaign name
* Campaign ID
* Adset name
* Adset ID

</Accordion>

<div id="twitter-user-privacy" />

<Accordion title="X広告のエンドユーザープライバシー">

X Adsの広告主とユーザーは、広告主やビジネスパートナーと情報を共有する方法を管理できます。

* **2021年7月31日**以降、Twitter Advanced Mobile Measurement（AMM）プログラムに参加していない広告主は、全てのTwitter MACTユーザーレベルデータの受信を停止します。結果として、AppsFlyerローデータにおいて、**すべてのX広告データが制限されます**。詳細：<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#x-ads-formerly-twitter">X広告のデータ制限</Anchor>
* 広告主がAMMプログラムに参加しており、ユーザーがプライバシー通知を承認している場合、**ローデータ制限は適用**されません。
* AMMステータスに関係なく、ユーザーがEUに在住し、ビジネスパートナーとのデータ共有に同意している場合は、**ローデータ制限は適用されません**。
* AMMステータスに関係なく、ユーザーがEUに在住し、ビジネスパートナーとのデータ共有に同意しない場合は、**ローデータ制限は適用されます**。
* 集計アトリビューションデータは、AppsFlyerに正しく反映され、X Adsポリシーには影響されません。

AMMプログラムを通じて、広告主はX Adsに監査を行う権利を付与することで、より完全なユーザーレベルデータを受け取ることができます。この監査により、X Adsのデータは、業界標準およびデータ保護法に準拠し、測定目的にのみ使用されることが保証されます。

詳細：<Anchor target="_blank" href="https://business.x.com/en/help/campaign-setup/create-an-app-installs-campaign/mobile-app-measurement-and-attribution">FAQセクション - AMMプログラム</Anchor>詳細なガイダンスは、X広告の担当者へお問い合わせください。

</Accordion>

<div id="advanced-srn-parameter-names" />

## アドバンスSRNパラメーター名

X広告のアドバンスSRN連携において、以下のデータ項目は AppsFlyer ダッシュボード、集計レポート、およびイベントレベルのローデータにおいて、従来の対応するデータ項目と置き換えられます。

| **AppsFlyerの**  <br />**データ列** | **レガシーSRN** | アドバンスSRN |
| --- | --- | --- |
| **PID** | Twitter | Twitter |
| **Campaign Name** | Campaign Name | Campaign name |
| **Campaign ID** | Campaign ID  <br />（base36：X管理画面とは異なる値。例：21I3V9） | Campaign ID  <br />（base10：X管理画面と同じ値。例：123456789） |
| **Adset Name** | Line Item ID  <br />（base36：X管理画面とは異なる値。例：21I3V9） | Line Item Name |
| **Adset ID** | Line Item ID  <br />（base36：X管理画面とは異なる値。例：21I3V9） | Line Item ID  <br />（base10：X管理画面と同じ値。例：123456789） |
| **Ad Name** | Tweet ID | Ad Name  <br />（利用可能な場合） |
| **Ad ID** | Tweet ID | Tweet ID |
| **Match Type** | srn | id\_matching / probabilistic |

<div id="traits-and-limitations" />

## 特性と制限

| 特性 | 備考 |
| --- | --- |
| プリロール計測 | X広告は、プリロールキャンペーンのMMPアトリビューションをサポートしていません。 |
| 広告名 "Untitled" | Ad Name（広告名）はX広告データモデルにおいて必須ではないため、反映されません。X Ads Managerで広告名が定義されていない場合、AppsFlyerでは<strong>「Untitled」</strong>と表示されます |
| コスト | X広告の場合、SKANのみのキャンペーン（SKANインストールのみ、他のインストールなし）のコストデータは代理店で利用できません。コスト連携は広告主が設定する必要があります。コストデータは広告主のみが閲覧できます。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01JV7CGQNZNEM3P98K6KSYKB0D=%E6%A6%82%E8%A6%81 xads-attribution-flow-in-appsflyer=appsflyer%E3%81%A7%E3%81%AEx%E5%BA%83%E5%91%8A%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%95%E3%83%AD%E3%83%BC h_01JZG83EKX39SF8355EW62C462=appsflyer%E3%81%A7%E3%81%AEx%E5%BA%83%E5%91%8A%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%95%E3%83%AD%E3%83%BC connecting-your-X-Ads-ads-account-to-appsflyer=x%E5%BA%83%E5%91%8A%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%82%92appsflyer%E3%81%AB%E6%8E%A5%E7%B6%9A%E3%81%99%E3%82%8B h_01HDJVCRYQESA17XZ83GS81YZ3=x%E5%BA%83%E5%91%8A%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%82%92appsflyer%E3%81%AB%E6%8E%A5%E7%B6%9A%E3%81%99%E3%82%8B h_01JV7D6AWYQ981HY6C130B021B=%E6%B3%A8 X-Ads-ads-attribution-setup=x%E5%BA%83%E5%91%8A%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E8%A8%88%E6%B8%AC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HDJVBAEZ5W3JH1BN7WXJ08P6=x%E5%BA%83%E5%91%8A%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E8%A8%88%E6%B8%AC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HDJVBAEZSFKRXAKQJP58N550=integration-tab ad-account-connected=%E5%BA%83%E5%91%8A%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%A8%E3%81%AE%E9%80%A3%E6%90%BA h_01HDJVBAEZD89BSGHQTPR84HSC=%E5%BA%83%E5%91%8A%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%A8%E3%81%AE%E9%80%A3%E6%90%BA xads_advanced_privacy_toggle=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF advanced-privacy=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01JV7HVQJ2GTP74G6JYB300E71=%E6%B3%A8%E6%84%8F clickthrough-attribution=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC h_01HDJVBAEZFJWQ6FD4Q4GSPD76=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC viewthrough-attribution-lookback-window=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC%E3%81%AE%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01HDJVBAEZ2H91WBHNSMRQYQ7H=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC%E3%81%AE%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 reinstall-settings=%E5%86%8D%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%AD%E5%AE%9A h_01HDJVBAF0XRWRZJQSS4STH7YN=%E5%86%8D%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%AD%E5%AE%9A reengagement-settings=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88cv%E3%81%AE%E8%A8%88%E6%B8%AC%E8%A8%AD%E5%AE%9A h_01HDJVBAEZZR1W06YH4XJSBKHV=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88cv%E3%81%AE%E8%A8%88%E6%B8%AC%E8%A8%AD%E5%AE%9A h_01JV9YQ7ZHRDD2NA5ENQXJQ31V=%E9%87%8D%E8%A6%81 reengagement-clickthrough-lookback-window=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88cv%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%81%AE%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01HDJVBAEZ59ERYD2WQQYK6T37=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88cv%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%81%AE%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 reengagement-viewthrough-lookback-window=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88cv---%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01HDJVBAEZSCK7430NJ8AMQYVY=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88cv---%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 reengagement-window=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E6%9C%9F%E9%96%93 h_01HDJVBAEZCMWY5X47FEEFXTBX=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E6%9C%9F%E9%96%93 ignore-active-users=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E8%A8%88%E6%B8%AC%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E4%BC%91%E7%9C%A0%E6%9C%9F%E9%96%93%E3%81%AE%E8%A8%AD%E5%AE%9A h_01JVC3PWDR9KHEFBQF5NWHCQJN=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E8%A8%88%E6%B8%AC%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E4%BC%91%E7%9C%A0%E6%9C%9F%E9%96%93%E3%81%AE%E8%A8%AD%E5%AE%9A inapp-event-postback-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E8%A8%AD%E5%AE%9A h_01HDJVBAEZ5ZM9RDXPWTJPPYVA=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E8%A8%AD%E5%AE%9A h_01HDJVBAEZATGM580CNC7BCVTN=%E6%B3%A8 h_01HDJVBAEZR1Q2SVE9MEQ9EXKP=attribution-link-tab h_01HDJVBAEZ7R7BKFAZYXXBGS5Y=%E6%B3%A8%E6%84%8F-1 h_01HDJVBAEZYSWN59VNXTDEWX93=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab h_01HDJVBAF0KEVSWJ0EW54AEAWV=permissions-tab ad-network-permissions=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E h_01HDJVBAF0BMSCKF6J9NJ019YJ=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E agency-permissions=%E4%BB%A3%E7%90%86%E5%BA%97%E6%A8%A9%E9%99%90 h_01HDJVBAF0W3ZE7J93CRE8EBRP=%E4%BB%A3%E7%90%86%E5%BA%97%E6%A8%A9%E9%99%90 x-ad-features=x%E5%BA%83%E5%91%8A%E3%81%AE%E6%A9%9F%E8%83%BD h_01JZWQA6DXRZ17SRVT4HM2MQSH=x%E5%BA%83%E5%91%8A%E3%81%AE%E6%A9%9F%E8%83%BD h_01JZWQA6DX3BRNG8B5CJGA57AM=mobile-app-promotion-on-x-ads h_01JZWQA6DX7W9102P5S6KWJ1WB=webtoapp-measuring-app-activity-for-nonapp-campaigns-android-only h_01JZWQA6DX8AX5XG3W4A6XB53S=%E9%87%8D%E8%A6%81-1 h_01H9QR6TH74PKBGM5RC4M118GE=twitter-ads-and-appsflyer-skan-interoperation h_01H9QR6TH74R50K00H7FYN61KC=twitter-user-privacy x-ads-data-differences=%E3%82%A2%E3%83%89%E3%83%90%E3%83%B3%E3%82%B9srn%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC%E5%90%8D advanced-srn-parameter-names=%E3%82%A2%E3%83%89%E3%83%90%E3%83%B3%E3%82%B9srn%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC%E5%90%8D traits-and-limitations=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01JYGPBHHNQARG3GRMQJA95JKD=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90" />
