---
title: Snapchat— アドバンスSRNの連携設定
metadata:
  keywords:
    - configuration
    - snapchat measurement partner
    - snapchat
    - measurement
    - snapchat measurement analytics
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
  created_at: '2016-06-13T12:28:59Z'
  edited_at: '2026-10-14T09:39:10Z'
  id: 211011983
  locale: ja
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/ja/articles/211011983
---
> **概要：** 2023年9月中旬より、SnapchatはAdvanced SRNとなりました。Snapchatとの連携設定、およびアトリビューション測定に関する情報をこのページでご確認いただけます。

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/snapchat.png?v=1" width="52px" />

<div id="overview" />

## 概要

アドバンスSRN連携では、広告配信面アプリと広告主アプリの<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-knowledge-base-glossary?query=glossar#dual-consent">両方でATTの同意が得られている</Anchor>成果については通常のSRNのトラフィックとしてレポート・計測されます。同意のないトラフィックについては、AppsFlyerはプライバシー制限に従い、<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns#アドバンスsrnのアトリビューションはどのように機能しますか">他のアトリビューション方法</Anchor>を使用してSnapchatからのクリックとインプレッションに基づいてアトリビューションを付与および計測できます。

<div id="set-up-snapchat-integration" />

## Snapchat連携設定

**前提条件：** 連携を設定する前に、 <Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーへ連絡</Anchor>し、アカウントを開設してください。

**連携を有効化または編集する：**

1. **有効化するには：** AppsFlyer管理画面 左メニュー **連携** > **Partner Marketplace**へ移動します。  
   **編集するには：** AppsFlyerのサイドメニューから、 **[コラボレーション]** > **[アクティブ統合]** を選択します。
2. **Snapchat**を検索して選択します。
3. **連携の設定**をクリックします。連携の設定ページに移動します。
4. **連携**タブにて連携したいアプリを選択し、 **パートナーを有効にする**をオンにしてください。  
   **注：** パートナーと作業している間、トグルはオン<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">（有効）</Anchor>のままにしておく必要があります。
5. 以下の手順に従い、各タブの設定を完了してください。

連携設定ウィンドウのヘッダーの詳細については、 <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>をクリックしてください。

> 📘 **注記：**
>
> * 一部の設定項目は、iOSとAndroidで異なります。
> * 詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">パートナー連携の設定</Anchor>のページをご確認ください。

<div id="integration-tab" />

<Accordion title="連携タブ">

この連携では、クリックとインプレッションのアトリビューション、費用、広告収益、オーディエンスがサポートされています。

<div id="activate-partner" />

#### パートナーの有効化

ここへの**初回の訪問**では、セットアップを有効にするために**パートナーの有効化**をオンにします。  
パートナーのライセンス認証の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>をクリックしてください。

**アトリビューションを有効にする**

**パートナー連携を有効にする**を有効にして、Snapchatへのアトリビューションを許可します。

![mceclip0.png](https://files.readme.io/cf4e73fec951e4e9d2c1919ca20adff88fc0d49d7fea9b033ab9c39194ce2702-360003259638.png)

<div id="general-settings" />

#### 一般的な設定

**Snap App ID**

1. Snapビジネスマネージャーで、[アプリ]　に移動し、Snap App IDをコピーします（Snap App IDの生成方法については、<Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/a/snap-app-id">Snapchatのガイド</Anchor>をお読みください）。
2. AppsFlyerのSnap App ID項目にIDを貼り付けます。

![snapchat-app-id.png](https://files.readme.io/2e5f53240893e2a80ba36065f67f4504f69e1167d96ef35bd7a4ab874d5a7bb9-360008280878.png)

**代理店によってキャンペーン配信する場合**

* Snap アプリ ID を追加できるのは広告主のみです。
* 代理店がSnapchat広告管理画面で広告主と同じ組織の下にある場合は、Snap App IDを1つだけ使用します。
* 代理店がSnapchat広告管理画面の別の組織の下にある場合は、このアプリのSnap App IDを提供するように代理店に依頼し、この項目に入力します。複数のIDを入力できます。各IDを入力後、Enter キーを押して複数のIDを入力できます。

<div id="install-attribution" />

#### インストール計測

広告を表示した、クリックした、または携わっているユーザーの新規インストール（初回起動）をアトリビューションするために、さまざまなアトリビューション期間を設定します。ルックバック期間内のインストールのみがSnapchatに起因する可能性があることに注意してください。

**注記：** 再インストール（デバイスの初期セットアップ以外のインストール）のアトリビューションはサポートされていません。

1. **インストール クリックスルー ルックバック期間**を 1～23 時間または 1～30 日に設定します。**注記：** Snapchatはインストールのクリックスルー ルックバック期間を7日に設定することを推奨しています。

   > 📘 **注記：**
   >
   > クリックスルーのルックバック期間を設定すると、エンゲージ ビューとエンゲージされたクリックのルックバックウィンドウも決定されます。

2. [オプション] **インストールビュースルーアトリビューション**をオンにして、ルックバックウィンドウを設定します。
   * **インストールビュースルールックバック期間**は1～24時間の範囲です。**注：** Snapchatはインストール ビュースルー ルックバック期間を1日に設定することを推奨しています。

<div id="re-engagement-attribution" />

#### リエンゲージメントアトリビューション

さまざまなアトリビューション期間を設定して、広告を表示した、クリックした、または携わっている既存のユーザーのリエンゲージメントをアトリビューションします。ルックバック期間内のリエンゲージメントのみがSnapchatに起因する可能性があることに注意してください。

1. **リエンゲージメントクリックスルールックバック期間**を1～23時間または1～30日に設定します。**注記：** Snapchat では、リエンゲージメントクリックスルールックバック期間を7日に設定することを推奨しています。

   > 📘 **注記：**
   >
   > リエンゲージメントクリックスルーのルックバック期間を設定すると、エンゲージ ビューとエンゲージされたクリックのリエンゲージメントルックバックウィンドウも決定されます。

2. [オプション] **リエンゲージメントビュースルーアトリビューション**を有効にし、ルックバック期間を設定します。
   * **リエンゲージメントビュースルールックバック期間**は1～24時間の間です。**注：** Snapchat では、リエンゲージメントビュースルールックバック期間を1日に設定することを推奨しています。
3. **リエンゲージメント期間**を1～23時間、1～90日間、または**全期間**に設定します。

<div id="ignore-active-users-for-retargeting" />

#### リターゲティングでアクティブユーザーを無視する

直近アプリを起動したユーザーの、<Anchor target="_blank" href="/marketers/ja/docs/set-retargeting-inactivity-window#休眠期間">リエンゲージメントとリアトリビューションを計測しない</Anchor>期間を設定します。したがって、この期間中のアクティビティはAppsFlyerに記録されません。

> 📘 **注記：**
>
> 設定された期間中に**休眠状態**だったユーザーのリエンゲージメントと再アトリビューションのコンバージョンは**記録されます**。

1. リターゲティングで**アクティブユーザーを無視する**をオンにします。
2. 非アクティブ期間を設定します。

<div id="in-app-event-postbacks" />

#### アプリ内イベントのポストバック

ポストバック経由でAppsFlyerイベントとパートナーをマッピングします。ポストバックの送信が有効になっている場合、これは拒否されたアプリ内イベント（Protect360によりブロックされたイベント、またはターゲット検証ルールにより条件を満たしていないと判断されたイベント）を含んでいます。

[![mceclip0.png](https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png)](https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png)

**アプリ内イベントのポストバックを設定する：**

1. **パートナーID**を設定します（必要な場合）。
2. **アプリ内イベントポストバック**を有効にします。
3. 必要に応じて、**アプリ内イベントポストバック期間**を設定してください（詳細については、<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#アプリ内イベントポストバック期間">アプリ内イベントポストバック期間の設定</Anchor>を参照してください）。
4. 利用可能な場合は、イベントを自動的に送信するか、手動で送信するかを選択します。すべてのイベントをそのまま送信する方法については<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped">こちら</Anchor>をご参照ください。
5. **イベントを追加**をクリックし、SDKまたはS2Sイベントをリストに追加してください。
6. 必要なパラメーターを完了してください。
7. [オプション] <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> をクリックして、特定のアプリ内イベントをパートナーに送信するための条件を設定します。  
   <Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">条件付きアプリ内イベントポストバック</Anchor>について詳細はこちら。

| パラメーター名 | 説明 |
| --- | --- |
| **AppsFlyerイベント** | これは、アプリに連携されたSDKまたはサーバー間イベントからAppsFlyerが受信したイベントの名前です。<br />**ヒント：** お探しのイベントが見つかりませんか？<ul><li>デバイス上で非オーガニックインストールによってアプリ内イベントが発生しているかを確認し、再度チェックしてください。</li><li>**AppsFlyerイベント**にイベントを入力し、**カスタムイベントを作成**をクリックしてください。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">カスタムイベントマッピングの詳細をお読みください。</Anchor></li></ul> |
| **パートナー側のイベント名** | パートナー側で定義されている各イベントの固有の名前またはID。オプションは以下の通りです：<ul><li>**テキストフィールド：** 対応するイベントIDをパートナーから取得します。</li><li>**ドロップダウンボックス：** 最適な事前定義されたAppsFlyerイベントを選択します。</li><li>**そのまま**：イベント名のマッピングなしで、イベントをそのまま送信します。</li></ul> |
| **送信オプション** | 最適なイベントの送信オプションを選択します。<ul><li>**このパートナーのみ**: このイベントがこのパートナーに紐付いている場合にのみポストバックを送信します。</li><li>**オーガニックを含むすべてのメディアソース**: すべてのパートナーとオーガニックイベントに紐付くイベントのポストバックを送信します。</li></ul> |
| **送信データ** | <ul><li>**データなし（デフォルト）：** イベント値なしでイベント自体のみを送信します。</li><li>**イベント値と収益：** 収益を**含む**アプリ内イベントに付随する全てのイベント値を送信します。</li><li>**イベント値のみ ：** 収益額**を除く**、すべてのパラメーターを送信します。</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

計測リンクはSnapchatでは使用しません。

> 📘 **注意**
>
> Meta、Apple search ads、Adwords、Snapchatなど、すべてのSRN媒体では外部計測リンクを使用しないため、このタブは機能しません。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

コスト連携では、以下の集計データを提供します。

* キャンペーン、広告セット、広告、チャネルレベルのコストデータを提供します。サポートされているディメンション、指標、機能の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">アドネットワークコスト連携に関する表</Anchor>を参照してください。  
  **注記：** コストデータには<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>サブスクリプションが必要です。
* クリックとインプレッションに関するデータ。

**コストAPIを有効にするには**:

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">これらの連携手順</Anchor>に従ってください。

<div id="cost-data-sync-status" />

<Accordion title="コストデータ同期ステイタス">

<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiのステータス">コストAPIのステータスを表示</Anchor>と一致するコストデータを引き出すことができた最後の時刻を、AppsFlyerがコスト（および広告収益）連携ステータス管理画面、または個別のアドネットワーク管理画面のいずれかで確認してください。

</Accordion>

<div id="stop-snapchat-cost-sync" />

<Accordion title="Snapchatのコストデータ連携を停止する">

**Snapchatのコストデータ取得を停止 / 接続されているSnapchatアカウントを削除：**

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">アクション列で、アカウントにカーソルを合わせて[**接続を削除**]をクリックします。</Anchor>  
  削除すると、AppsFlyerはコストの取得を停止します。接続を削除しても過去のデータには影響しません。

</Accordion>

> 📘 **備考**
>
> * Snapchatでのキャンペーン設定がiOSまたはAndroidアプリ用であることを確認してください。両方ではありません。キャンペーンが両方のアプリを対象としている場合、AppsFlyerはアプリあたりのコストを分類できず、コストはAppsFlyerに表示されません。
> * コストデータの不整合を避けるために、<Anchor target="_blank" href="/marketers/ja/docs/changing-app-time-zone-settings#タイムゾーンの変更方法">アプリ設定</Anchor>とSnapchat広告アカウントで同じタイムゾーンを設定してください。
> * Snapの費用を設定した後は、重大な不一致や費用データの欠落の原因となる可能性があるため、実行中のキャンペーン、広告セット、または単一の広告の名前を変更しないでください。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

このパートナーとの連携では、広告収益はサポートされていません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

Snapchatがあなたのデータにアクセスし、様々なアクションを行うために<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">付与する権限</Anchor> を選択します。

> 📘 **注記：**
>
> 権限トグルがオンの状態で連携が<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">非アクティブ化</Anchor>された場合でも、権限は付与されたままです。

</Accordion>

<div id="web-to-app-measuring-app-activity-for-non-app-campaigns" />

## Web to app：非アプリキャンペーンの計測

AppsFlyerとTikTokの連携により、TikTok for Businessに紐づくアプリ以外のキャンペーンのインストール、リエンゲージメント、アプリ内イベントなどのアプリアクティビティを包括的に計測できます。

たとえば、広告の遷移先がWebランディングページであってもアプリのインストールを計測できるため、Web-to-App（W2A）のユーザージャーニーを計測できます。

<div id="deep-linking-with-snapchat" />

## Snapchatとのディープリンク

Snapchatとのディープリンクは、Snapchatのプラットフォームでネイティブのディープリンクを使用し、AppsFlyerパラメーターを追加することに基づいています。

Snapchatでディープリンクを実行するには：

1. [Snapchatでリターゲティングのディープリンクが有効になっていることを確認](/docs/snapchat-advanced-srn-integration-setup#snapプラットフォームでディープリンクを設定)します。
2. AppsFlyer管理画面で<Anchor target="_blank" href="/marketers/ja/docs/app-settings#reengagement-attribution">リエンゲージメントCV計測設定が有効になっていることを確認</Anchor>します。
3. アプリのディープリンクスキームURIを取得し、 **少なくとも** 次のパラメーターを追加します：

* **PID** - メディアソース名は常に **snapchat\_int**です。これにより、すべてのデータがAppsFlyerダッシュボードの **snapchat\_int** メディアソースの下に表示されます。
* **C -** 関連するキャンペーン名
* **is\_retargeting=true -** この項目は、キャンペーンをリターゲティングキャンペーンとして定義します。リターゲティングキャンペーンでの既存のユーザーのエンゲージメントは、URIにこの項目が存在するため、リエンゲージメントとしてマークされます。これにより、ユーザーのデータがリターゲティングダッシュボードに表示されます。

> 📄 **URIの例**
>
> client://home?pid=snapchat\_int&c=TEST&is\_retargeting=true

<div id="set-up-deep-links-on-the-snap-platform" />

### Snapプラットフォームでディープリンクを設定

1. **Drive traffic to app** オポチュニティタイプへ移動します。
2. ディープリンクURIを追加します。  
     
   [![](https://files.readme.io/428258bbc5eb2fc7332ea07356e098eb66ac2cfdd0955117a14666eb76a20f79-360001717778.png)](https://files.readme.io/428258bbc5eb2fc7332ea07356e098eb66ac2cfdd0955117a14666eb76a20f79-360001717778.png)

<div id="deferred-deep-linking-with-snapchat" />

### Snapchatでのディファードディープリンク

<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">ディファードディープリンク</Anchor>を利用することで、SDKレベルで直接、Snapchatユーザーのコンバージョンデータに実際の時間でアクセスできます。

<Anchor target="_blank" href="/marketers/ja/docs/conversion-data-payloads-and-scenarios#snapchat-conversion-data">Snapchatコンバージョンデータ</Anchor>には**af\_dp**パラメータが含まれており、Snapchatでの広告に対するユーザーのエンゲージメントに基づいて、カスタマイズされたコンテンツをディープリンクして提供できます。

さらに、**af\_adset**や**af\_channel**などの他のコンバージョンデータパラメーターも利用できます。

広告主の代理で作業する代理店は、Snapchatの連携を有効にして、キャンペーンのアトリビューションを取得することができます。ただし、この統合には、代理店に関してはいくつかの制限があります。

<div id="set-up-snapchat-for-agencies" />

## 代理店向けのSnapchatのセットアップ

広告主の代理で作業する代理店は、Snapchatの連携を有効にして、キャンペーンのアトリビューションを取得することができます。ただし、この統合には、代理店に関してはいくつかの制限があります。

<div id="agency-limitations" />

### エージェンシーの制限

* 代理店は、働いている広告主がその側でSnapchatの統合を有効にした後にのみ、Snapchat連携にアクセスできます。
* 代理店の統合ページに表示されるアトリビューションパラメーターは、**表示専用**モードにおける広告主の統合から引き継がれます。これは、代理店が広告主のアトリビューション期間の設定を見ることはできても、自身で設定することはできないことを意味します。
* ポストアトリビューションイベントに関しては、広告主からの許可があれば、代理店はアプリ内イベントポストバックを設定できます。
* 代理店は、（許可があっても）高度なプライバシー設定をオンにすることはできません。これは広告主のみに限定されます。

**代理店向けにSnapchatを設定するには:**

1. AppsFlyerの[**構成**]で[**パートナーマーケットプレイス**]に移動します。
2. **Snapchat**を見つけて選択します。
3. 代理店の**SnapchatアカウントID**を入力します。これにより、代理店のトラフィックが識別され、広告主のトラフィックと区別されます。最大50個の異なるSnapchatアカウントIDを入力できます。入力したアカウントからのすべてのアトリビューションデータは、代理店の管理画面に表示されます。
4. **連携を保存** をクリックします。

![snapchat-agency-integration.png](https://files.readme.io/261a0246bb7da0899e653a776eb25e17ce3ae8bff1efef33acac0ef0bf99abcf-21074932431505.png)

> ❗️ **要注意**
>
> SnapchatアカウントIDは、広告主または代理店の間で共有することはできません。共有されている場合、広告主のすべてのインストールは代理店のダッシュボードに自動的に紐付けられます。

<div id="raw-data-restrictions" />

## ローデータの制限

* 2023年3月1日以降、Snapchatのアンインストールはローデータレポートに含まれません
* 2023年9月12日以降、Snapchatは広告主にデバイスレベルのビュースルーアトリビューションデータの提供を停止しました。ローデータレポート、Push API、Pull APIレポート、Data Lockerを介して提供されるユーザーレベルのローデータの場合、以下の項目のみが提供されます：
* * メディアソース (snapchat\_int)
  * チャネル
  * Attributed touch type (impression)
  * 起因するタッチ時間 (日付のみ "dd/mm/yyyy" 記録されます)
  * キャンペーンは 「制限あり」として報告されます

<div id="snapchat-data-retention" />

## Snapchatのデータ保持期間

Pinterestは、インストール後12か月でユーザーレベルのデータを削除するようアトリビューションプロバイダーに要請しています。つまり、これらのユーザーがアプリをインストールしてから12か月後に行ったイベントは、オーガニック経由の成果としてカウントされます。

過去の集計データは変わりません。

> 📄 **参照：**
>
> <Anchor target="_blank" href="/marketers/ja/docs/skan-interoperation-with-snapchat">SnapchatとAppsFlyerのSKAdNetwork相互運用</Anchor>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 01H8F1RWVPTHBDGF3830DY7G7M=%E6%A6%82%E8%A6%81 setting-up-snapchat-integration=snapchat%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A 01H7WQ47ECTZHPKMG5Z5ZPAND5=snapchat%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A 01H88VAJH3BYZSXQGGZZJQ9N0C=%E6%B3%A8%E8%A8%98 01H7WQ47ECD76GFNM7VVV7C9RG=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 01H7WQ47ECZB5GNCQ0XH68N1DK=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A 01H7WQ47ECQSQPP63H398NTQ6M=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A install-attribution=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC 01H8VVCC8GK8VFPBEPAMVHCAWM=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC 01JE5ZMSXK5Q9KWKY8C6ZXEGD9=%E6%B3%A8%E8%A8%98-1 reengagement-attribution=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 01H8VVCC8HHG5290PYF0BT29QA=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01JJMAPTYDYVS5RDGQZA4J0DJ6=%E6%B3%A8%E8%A8%98-2 ignore-active-users-for-retargeting=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%A7%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%92%E7%84%A1%E8%A6%96%E3%81%99%E3%82%8B h_01HNWSTJZPFQVQ5C8M0JA1J0T5=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%A7%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%92%E7%84%A1%E8%A6%96%E3%81%99%E3%82%8B h_01HMXNJVHK9C3FT8E04RE0TH99=%E6%B3%A8%E8%A8%98-3 inapp-event-postback-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H8VVCC8HHZRFQ2T1X478YZMP=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H7WQ47EDWX9TGAD4X0E41RQ8=attribution-link-tab 01H7WQ47ED5N4REX0SFVY5ZG2K=%E6%B3%A8%E6%84%8F 01H7WQ47EDCKQ1T4NVFD3C1KV0=cost-tab 01H7WQ47ED1HYEBHFJDHTB6HJH=cost-data-sync-status 01H7WQ47ED3P53B269W93Z341E=stop-snapchat-cost-sync 01H7WQ47EDQ0253RY37PX67REV=%E5%82%99%E8%80%83 01H7WQ47EDC3YB1BKNG2C7AD6J=ad-revenue-tab h_01HJ1BJTNNVYCVWY61NW07PY5J=permissions-tab h_01HJ1BJTNPG7NN3XZNP5XBE3XQ=%E6%B3%A8%E8%A8%98-4 web-to-app-measuring-app-activity-for-nonapp-campaigns=web-to-app%E9%9D%9E%E3%82%A2%E3%83%97%E3%83%AA%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%88%E6%B8%AC h_01JJMAS0W9WMEPJCQWD9BXAEZ2=web-to-app%E9%9D%9E%E3%82%A2%E3%83%97%E3%83%AA%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%88%E6%B8%AC deep-linking-with-snapchat=snapchat%E3%81%A8%E3%81%AE%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF 01H7WQ47EDC973V7CPE38QAQE7=snapchat%E3%81%A8%E3%81%AE%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF 01H7WQ47EDXS702A9TZ7DJ8MPG=uri%E3%81%AE%E4%BE%8B how-to-set-up-deep-links-on-snap-platform=snap%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%A7%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E8%A8%AD%E5%AE%9A 01H7WQ47EDJAX2DW7A2JJ4XVJN=snap%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%A7%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E8%A8%AD%E5%AE%9A deferred-deep-linking-with-snapchat=snapchat%E3%81%A7%E3%81%AE%E3%83%87%E3%82%A3%E3%83%95%E3%82%A1%E3%83%BC%E3%83%89%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF 01H7WQ47EDS3MYRN9A9ZPHXG9Z=snapchat%E3%81%A7%E3%81%AE%E3%83%87%E3%82%A3%E3%83%95%E3%82%A1%E3%83%BC%E3%83%89%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF setting-up-snapchat-for-agencies=%E4%BB%A3%E7%90%86%E5%BA%97%E5%90%91%E3%81%91%E3%81%AEsnapchat%E3%81%AE%E3%82%BB%E3%83%83%E3%83%88%E3%82%A2%E3%83%83%E3%83%97 01H7WQ47EDARK9SSP47V5MGX18=%E4%BB%A3%E7%90%86%E5%BA%97%E5%90%91%E3%81%91%E3%81%AEsnapchat%E3%81%AE%E3%82%BB%E3%83%83%E3%83%88%E3%82%A2%E3%83%83%E3%83%97 agency-limitations=%E3%82%A8%E3%83%BC%E3%82%B8%E3%82%A7%E3%83%B3%E3%82%B7%E3%83%BC%E3%81%AE%E5%88%B6%E9%99%90 h_01HHVGS94CB9XC0T63VFDZ18JS=%E3%82%A8%E3%83%BC%E3%82%B8%E3%82%A7%E3%83%B3%E3%82%B7%E3%83%BC%E3%81%AE%E5%88%B6%E9%99%90 01H7WQ47EDPEDQHX9XRDKYKB1W=%E8%A6%81%E6%B3%A8%E6%84%8F raw-data-restrictions=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%B6%E9%99%90 h_01HA3XZPWSKVRX7VTRXT1WQ1EZ=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%B6%E9%99%90 keeping-snapchat-data=snapchat%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E4%BF%9D%E6%8C%81%E6%9C%9F%E9%96%93 01H7WQ47ED9STKS1CVW5EXYX0Z=snapchat%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E4%BF%9D%E6%8C%81%E6%9C%9F%E9%96%93 h_01HE7RP6VPPAY2CCSNTJ0RVSXM=%E5%8F%82%E7%85%A7" />
