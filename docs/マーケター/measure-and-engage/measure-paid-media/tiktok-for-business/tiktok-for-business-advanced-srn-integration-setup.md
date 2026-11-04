---
title: TikTok For Business — アドバンスSRNの連携設定
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-06-09T16:49:57Z'
  edited_at: '2026-10-14T09:38:06Z'
  id: 6722785184913
  locale: ja
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/ja/articles/6722785184913
---
> **概要：** TikTok for Business（tiktokglobal\_int）は、AppsFlyerを通じてクリックとビューに基づいたモバイルアトリビューションを計測できる、アドバンスセルフレポーティングネットワーク（<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns">SRN</Anchor>）です。アプリおよび非モバイルのTikTokキャンペーンからのアプリインストールの計測もサポートしています。

<div id="note" />

> 📘 **注意**
>
> * 2023年1月30日に、新しい**TikTok for Business — アドバンスSRN**連携（`tiktokglobal_int`）が追加されました。**[レガシー] TikTok for Business**連携 `bytedanceglobal_int`は段階的に廃止され、2024年3月20日に公式に廃止されました。移行はTikTokによって管理され、旧連携を削除できるようになった際に通知されます。**データの損失を防ぐために、移行期間中は両方の連携を有効に保ってください**。詳細は<Anchor target="_blank" href="/marketers/ja/docs/bulletin-tiktok-for-business-advanced-srn">お知らせ</Anchor>をご覧ください。
> * AppsFlyerは、[アプリ外のキャンペーン](#web-to-app非アプリキャンペーンの計測)のアプリアクティビティの計測をサポートしています。

<Image alt="TTFB_logo__4C_stacked_black_1.png" src="https://files.readme.io/f876dca1810a33266ad93de7822354d3a9aeb41a1e064a1f85f7120f713e699d-23689976309905.png" width="218px" />

<div id="overview" />

## 概要

Advanced SRN連携では、広告IDを含むすべてのトラフィックが通常のSRNトラフィックとしてアトリビューション・レポートされます。広告IDを利用できない場合は、AppsFlyerがプライバシー制限に準拠した形で、TikTokから提供されるクリックおよびインプレッションデータを基にアトリビューションを計測します。

<div id="set-up-tiktok-for-business" />

## TikTok For Businessの連携設定

**前提条件：** 連携を設定する前に、 <Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーへ連絡</Anchor>し、アカウントを開設してください。

**連携を有効化または編集する：**

1. **有効化：** AppsFlyer管理画面 左メニュー **連携** > **パートナーマーケットプレイス**へ移動します。  
   **編集**：AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー**へ移動します。
2. **TikTok for Business**を検索して選択します。
3. **連携の設定**をクリックします。連携の設定ページに移動します。
4. **連携**タブにて連携したいアプリを選択し、 **パートナーを有効にする**をオンにしてください。  
   **注：** >トグルは、パートナーと作業している間、オン（<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">アクティブ</Anchor>）のままにしておく必要があります。
5. 以下の手順に従い、各タブの設定を完了してください。

設定ウィンドウには次のタブが含まれます：連携、計測リンク、コスト、広告収益、権限。**計測リンク**タブはTikTok For Businessでは使用しません。また、その他のタブは任意です。

<div id="note-1" />

> 📘 **注意**
>
> * 一部の設定項目は、iOSとAndroidで異なります。
> * キャンペーンを設定する際、キャンペーン名を空白で開始したり、空白で終わらせたりすると、ダッシュボードとレポートに不一致が生じる可能性があるため、空白にしないでください。TikTokでキャンペーンを設定する方法について詳しくは<Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=9535">こちらのページ</Anchor>をご覧ください。
> * <Anchor target="_blank" href="https://www.tiktok.com/business/en/blog/introducing-tiktok-search-ads-toggle">TikTok検索広告トグル</Anchor>からの広告は、すべてのTikTokアトリビューションに含まれます。 AppsFlyerは特定の検索用語やキーワードに関するデータを受け取りません。

<div id="integration-tab" />

<Accordion title="連携タブ">

**連携**タブには、以下の設定項目があります。

<div id="activate-partner" />

#### パートナーの有効化

連携を有効にするには、最初に必ず**パートナーを有効にする**のトグルをONにしてください。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation#パートナー統合を有効にする">パートナーの有効化と無効化</Anchor>に関する詳細情報は、連携タブを参照してください。

<div id="advanced-matching-data-sharing" />

<div id="note-2" />

<div id="advanced-data-sharing" />

#### 高プライバシーポストバック

iOSアプリのみ：ポストバックや<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">レポート</Anchor>を通じてパートナーと共有するデータのコントロールは、 <Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">**高プライバシーポストバック**</Anchor><strong>（iOS 14.5以降）</strong>のトグル状態によって決まります。

| 高プライバシー設定：オン | 高プライバシー設定：オフ |
| --- | --- |
| そのパートナーに紐付いているイベントのみのポストバックが送付されます。 | ご自身で設定された以下の内容に沿った形でポストバックが送付されます：<ul><li>**オーガニックを含む全メディアソース**</li><li>**このパートナーのみ**</li></ul> |
| ポストバックは、<Anchor target="_blank" href="/partners/ja/docs/advanced-privacy-guide-postback-macros-for-ad-networks">高プライバシーポストバック向けに設定されたテンプレート</Anchor>を使って送信されます。 |  |
| 顧客によって、<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">集計・匿名化されたデータ</Anchor>がパートナーへ共有されます。つまり、ユーザーレベルデータ（デバイスIDなど）は含まれません。 |  |

> 📘 **注意**
>
> * 連携（`tiktokglobal_int`）を有効にすると、**高プライバシーポストバック**トグルがデフォルトでオンになります。
> * レガシー連携（`bytedanceglobal_int`）から移行し、新しい連携（`tiktokglobal_int`）をアクティブ化すると、移行前の状態に関係なく、**高プライバシーポストバック**トグルがデフォルトでオンになります。

<div id="note-3" />

<div id="general-settings" />

#### 一般的な設定

**TikTok App ID**

このIDはTikTok Ads Manager上で生成されるユニークIDで、TikTokが広告主のアプリの所有権を確認するために使用されるものです。必須ではありませんが、アプリごとに正しくTikTok App IDを入力することを推奨しています。TikTok For Businessのデータをより効率的に管理でき、追加製品の利用も可能になります。

**アプリIDの設定：**

1. TikTok Adsの管理画面上で取得した<Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10001060">TikTok App ID</Anchor>を入力してください。
2. さらにApp IDを追加したい場合：
   1. 最初のIDを入力したら、Enterキーを押してください。
   2. 次のTikTok App IDを入力してください。

> 📘 **注意**
>
> * TikTok App IDを設定しても、AppsFlyer上での計測データには何も影響しません。
> * 新しい連携（`tiktokglobal_int`）に移行すると、レガシー連携（`bytedanceglobal_int`）の値がすべてこのフィールドに自動的に入力されます。
> * <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10001070">iOS14におけるTikTok App IDの要件について</Anchor>も参照してください。

<div id="note-4" />

<div id="default-postbacks" />

#### デフォルトのポストバック

アプリの**インストール**に関するポストバックの送信方法を設定します。**拒否されたインストール**と**リエンゲージメント**の場合、ポストバックはTikTok for Businessのみに送信されます。

* **このパートナーのみ [デフォルト]：** イベントがこのパートナーに起因する場合、つまり、イベントを実行したユーザーがこのパートナーから来た場合にのみ、ポストバックを送信します。
* **オーガニックを含む全メディアソース：** あらゆるパートナーに起因するイベントや、オーガニックなイベント、つまり実行したユーザーがあらゆるメディアソースから来た場合にポストバックを送信します。TikTok for Businessでは、最適化のために選択を**オーガニックを含むすべてのメディアソース**に変更することを推奨しています。

> 📘 **注意**
>
> * iOSアプリのみ：ポストバックや<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">レポート</Anchor>を通じてパートナーと共有するデータのコントロールは、 **[高プライバシー](#高プライバシーポストバック)** （iOS 14.5以降）のトグル状態によって決まります。
> * レガシー連携（`bytedanceglobal_int`）から移行し、新しい連携（`tiktokglobal_int`）をアクティブにすると、移行前の状態に関係なく、ポストバックインストールのデフォルトの選択状態は**このパートナーのみ**になります。

<div id="note-6" />

<div id="note-5" />

<div id="install-attribution" />

#### インストール計測

広告を表示した、クリックした、または携わっているユーザーの新規インストール（初回起動）をアトリビューションするために、さまざまなアトリビューション期間を設定します。ルックバック期間内のインストールのみがTikTok for Businessにアトリビューションされることに注意してください。

1. **インストール：クリックスルールックバック期間**を 1～23 時間または 1～30 日に設定します。**注記：** TikTok for Business では、インストールのクリックスルー ルックバック期間を7 日間に設定して、これらの要件に合わせることを推奨しています。

   > 📘 **注意**
   >
   > クリックスルーのルックバック期間を設定すると、エンゲージビューとエンゲージクリックのルックバック期間も決定されます。

2. [オプション] **インストール：ビュースルー計測**をオンにして、ルックバック期間を設定します。
   * **インストールビュースルールックバック期間**は1～24時間の範囲です。**注：** TikTok for Business では、インストールビュースルールックバック期間を1日に設定し、推奨される基準に合わせることをお勧めします。

> 📘 **注意**
>
> * TikTok For Businessでは、サービスを利用するユーザーを保護するためにデータプライバシー対策を強化しています。2021年10月23日より、TikTok For Businessではビュースルーの端末レベルの計測データ（ローデータ）を、一部制限をかけた状態で広告主へ提供しています。ローデータレポート、Push API、Pull APIレポート、Data Lockerを介して提供されるユーザーレベルのローデータの場合、以下の項目のみが提供されます：
> * * メディアソース（bytedanceglobal\_int）
>   * チャネル
>   * Attributed touch type (impression)
>   * 起因するタッチ時間 (日付のみ "dd/mm/yyyy" 記録されます)
>   * キャンペーンは "restricted" と記録されます
>     このデータはGCDでは利用できません。集計データレポートでは引き続きビュースルーコンバージョンを利用できます。
> * レガシー連携 (`bytedanceglobal_int`) から移行し、新規連携 (`tiktokglobal_int`) をアクティブ化すると、移行前の状態に関係なく、ルックバック期間の設定 (クリックスルーおよびビュースルー) は**デフォルト値**になっています。これらの設定は更新できます。

<div id="note-7" />

<div id="reinstall-attribution" />

#### リインストール計測

リインストール計測を使用すると、リアトリビューション期間中にアプリを再インストールしたユーザーを計測し、対象となるTikTokのクリックやインプレッションへ成果を紐付けられます。

設定をオンにすると、リインストールはTikTokキャンペーンで新しいコンバージョンとしてカウントされ、既存のインストール計測の設定を用いてレポートされます。リインストールに関する詳細は、<Anchor target="_blank" href="/marketers/ja/docs/measure-reinstalls">リインストールの計測</Anchor>を参照してください。

* リインストールのアトリビューションを有効にするには、**連携**タブで**リインストールのアトリビューション**をオンにします。

> 📘 **注意**
>
> * リインストール専用のルックバック期間の設定は不要です。リインストール計測では、インストールのアトリビューション設定と同じクリックスルーおよびビュースルーのステータスとルックバック期間を使用します。
> * 有効化すると、対象となるリインストールのポストバックがTikTokへ送信されます。

<div id="warning" />

<div id="note-8" />

<div id="re-engagement-attribution" />

#### リエンゲージメントCVの計測

さまざまなアトリビューション期間を設定して、広告を表示した、クリックした、または携わっている既存のユーザーのリエンゲージメントをアトリビューションします。ルックバック期間内のリエンゲージメントのみが TikTok for Businessに起因すると見なされることに注意してください。

1. **リエンゲージメントCV：クリックスルールックバック期間**を1～23時間または1～30日に設定します。**注記：** TikTok for Business では、リエンゲージメントのクリックスルールックバック期間を7日に設定し、推奨される基準に合わせることをお勧めします。

   > 📘 **注意**
   >
   > リエンゲージメントクリックスルーのルックバック期間を設定すると、エンゲージビューとエンゲージクリックのリエンゲージメントCVのルックバック期間も適用されます。

2. [オプション] **リエンゲージメントビュースルーアトリビューション**を有効にし、ルックバック期間を設定します：
   * **リエンゲージメントCV：ビュースルールックバック期間** - 1～24時間の間。**注：** TikTok for Businessは、リエンゲージメントCVのビュースルールックバック期間を1日に設定することを推奨しています。
3. **リエンゲージメント期間**を1～23時間、1～90日間、または**全期間**に設定します。

> 🚧 **重要**
>
> レガシー連携（`bytedanceglobal_int`）から移行し、新しい連携（`tiktokglobal_int`）をアクティブ化すると、移行前の状態に関係なく、**高プライバシーポストバック**トグルがデフォルトでオンになります。レガシー連携で<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">リターゲティングキャンペーン</Anchor>を使用している場合は、**新しい連携でオン**にすることを確認してください。

参考：<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide#reengagement-rules-and-windows">リエンゲージメント計測の仕様と期間設定について</Anchor>

<div id="note-9" />

<div id="ignore-active-users-for-retargeting" />

#### アクティブユーザーをリターゲティング計測から除外する

直近アプリを起動したユーザーの、<Anchor target="_blank" href="/marketers/ja/docs/set-retargeting-inactivity-window#休眠期間">リエンゲージメントCVとリアトリビューションCVを計測しない</Anchor>期間を設定します。つまり、この期間のアクティビティはAppsFlyerに記録されません。

> 📘 **注意**
>
> 設定された期間中に**休眠状態**だったユーザーのリエンゲージメントとリアトリビューションのコンバージョンのみが**記録されます**。

1. **リターゲティングでアクティブユーザーを無視する**をオンにします。
2. 休眠期間を設定します。

<div id="in-app-event-postbacks" />

#### アプリ内イベントのポストバック

ポストバック経由で送信されるTikTok for Businessイベントとアプリ内イベントのマッピングを設定します：

1. **アプリ内イベントポストバック**を有効にします。
2. **イベントを追加**をクリックして、SDKまたは サーバー間イベントをリストに追加してください。各項目の説明は以下を参照してください：

| パラメーター名 | 説明 |
| --- | --- |
| **AppsFlyerイベント** | これは、アプリに連携されたSDKまたはサーバー間イベントからAppsFlyerが受信したイベントの名前です。<br />**ヒント：** お探しのイベントが見つかりませんか？<ul><li>非オーガニックインストールとして計測された端末上で、そのアプリ内イベントが発生しているかを確認し、再度チェックしてください。</li><li>**AppsFlyerイベント**にイベントを入力し、**カスタムイベントを作成**をクリックしてください。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">カスタムイベントマッピングの詳細をお読みください。</Anchor></li></ul> |
| **パートナー側のイベント名** | パートナー側で定義されている各イベントの固有の名前またはID。オプションは以下の通りです：<ul><li>**ドロップダウンボックス：** 最も適切な事前定義されたパートナーイベントを選択します。</li><li>**そのまま**：ドロップダウンから**カスタム**を選択すると、AppsFlyerはTikTokの規定イベントにマッピングすることなく、イベントをそのまま送信します。TikTokは最適化のためにカスタムイベントを使用しませんが、レポートのみを目的としており、最適化には使用しません。そのため、この設定はTikTokでは推奨されません。TikTokの標準イベントとカスタムイベントの詳細については、<Anchor target="_blank" href="https://ads.tiktok.com/help/article/standard-events-parameters">TikTokドキュメント</Anchor>を参照してください。</li></ul> |
| **送信オプション** | 最適なイベントの送信オプションを選択します。<ul><li>**このパートナーのみ**（デフォルト）：このイベントがこのパートナーに紐づいた場合にのみポストバックを送信します。</li><li>**オーガニックを含む全メディアソース：** オーガニックを含む全てパートナーに紐づくイベントに対してポストバックを送信します。 TikTok for Business では、最適化を強化するために**オーガニックを含むすべてのメディアソース**を選択することをお勧めします。</li></ul> |
| **送信データ** | <ul><li>**付随データなし**（デフォルト）：イベント値なしでイベント自体のみを送信します。</li><li>**イベント値のみ：** 収益値**以外**のすべてのパラメーターを送信します。</li><li>**イベント値と収益**：収益値を**含む**全てのイベントパラメーターを送信します（イベント内にある場合）。TikTok for Business では、最適化を強化するために**価値あり、収益あり**を選択することをお勧めします。</li></ul> |

3. [オプション] イベントの<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">条件を設定</Anchor>するには、**条件を追加**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />をクリックします。
4. **連携を保存**をクリックします。
5. ［任意］連携設定を保存したあとに、他のご自身のアプリのこのパートナーとの連携設定を編集することも可能です：
   1. 左上のパートナー名の下にある、アプリ名をクリックしてアプリ一覧を開いてください。
   2. ドロップダウンリストから別のアプリを選択してください。
   3. 選択したアプリで、連携ステップを再度実施してください。

<div id="note-11" />

<div id="note-10" />

> 📘 **注意**
>
> * iOSアプリのみ：ポストバックや<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">レポート</Anchor>を通じてパートナーと共有するデータのコントロールは、 **[高プライバシー](#高プライバシーポストバック)** （iOS 14.5以降）のトグル状態によって決まります。
> * 新しい連携（`tiktokglobal_int`）に移行すると、レガシー連携（`bytedanceglobal_int`）の値がすべてこのフィールドに自動的に入力されます。
>   * イベントがレガシー連携のTikTok for Business **Pay**イベントにマッピングされている場合、新しい連携に移行すると、このイベント名は自動的に**購入**に変更されます。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns">SRN</Anchor>やアドバンスSRNの場合、計測リンクは使用しません。

SRNは、自身のプラットフォーム上でアトリビューションを行います。アドバンスSRNの計測は、[連携タブ](#integration-tab)で設定したアトリビューション設定した内容を元にしたAppsFlyer側のデータと媒体側の広告接触データを組み合わせることで行われます。

</Accordion>

<div id="cost-tab-for-cost-clicks-and-impressions" />

<Accordion title="コストタブ（コスト、クリック数、インプレッション数の取得）">

この連携により、キャンペーン、広告セット、地域／国のコスト、クリック、インプレッションに関する集計データが提供されます。サポートされているディメンション、指標、機能の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">アドネットワークコスト連携に関する表</Anchor>を参照してください。

**注意：** クリックとインプレッションに関するデータは、この連携に含まれます。**コストデータの連携**には、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview?query=xpend">**ROI360**</Anchor>の**ご契約**が必要です。

**TikTok For Businessとのコスト、クリック数、インプレッション数のAPI接続を有効にするには**：

1. **コスト**タブに移動し、**コストデータの取得**をオンにします。
2. **TikTok広告にログイン**をクリックします。
3. 開いたTikTokの画面からTikTokアカウントにログインして、必要な権限を確認してください。
4. TikTokのウィンドウで成功メッセージが表示されたら、画面を閉じます。TikTokアカウントの詳細が**接続済みアカウント**の下に表示されます。
5. **広告主アカウントID** > **広告主ID**：TikTok広告主アカウントIDを入力し、**追加**をクリックします。

   > 📘 **注意**
   >
   > * TikTokビジネスアカウントから**広告主ID**を取得するには：TikTokビジネスアカウントで **ユーザー** > **メンバー**に移動し、広告主アカウントでIDを確認できます。
   > * 追加する**広告主ID**が、手順2で接続した**TikTokアカウント**に紐付けられていることを確認してください。このアカウントからデータが収集されます。
   > * 必ずつ以上の**広告主ID**を設定してください。最大30個まで広告主IDを追加できます。

6. **コストを保存**をクリックします。

<div id="for-roi360-subscribers" />

#### ROI360をご契約のお客様向け

* 従来の `bytedanceglobal_int` と新しい `tiktokglobal_int` の両方の連携においてコストAPIを広告主や代理店が有効にしている場合、重複したコストデータが表示される可能性があることにでご注意ください。これを回避するには、`bytedanceglobal_int`の連携設定画面において、**コスト**タブでコスト取得の連携をOFFにしてください。  
  ただし、新しいコスト連携を有効にすると、移行日の5日前からコストデータが自動的に収集されます。つまり、新しい連携では、その5日間のコストデータが重複して表示されることになります。**例えば**、古いコスト連携が1月15日に無効化され、新しいコスト連携が同日に有効化された場合、新しいコスト連携は1月15日のみ有効だったにもかかわらず、1月10日から14日までの期間に重複したコストデータを表示します。
* サポートされているディメンション、指標、機能の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">アドネットワークコスト連携に関する表</Anchor>を参照してください。
* <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiのステータス">コストAPIのステータスを表示</Anchor>と一致するコストデータを引き出すことができた最後の時刻を、AppsFlyerがコスト（および広告収益）連携ステータス管理画面、または個別のアドネットワーク管理画面のいずれかで確認してください。
* 詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">コストAPIの有効化</Anchor>を参照してください。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

広告収益データをUA最適化のためにTikTokに送信するには、<Anchor target="_blank" href="/marketers/ja/docs/share-ad-revenue-data-with-partners">広告収益ポストバックまたはUAシグナル</Anchor>を設定することができます。

Pangleから広告収益データを取得する場合には、別途Pangle（広告収益）のパートナー連携を使用してください。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

このセクションでは、TikTok for Businessにデータへのアクセスを許可し、さまざまなアクションを実行するための権限を選択できます。

連携が<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">無効化</Anchor>された後でも、**TikTok for Businessの権限**トグルがオンになっていると、権限が付与され続けることに注意してください。

詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">権限付与</Anchor>のページを参照してください。

</Accordion>

<div id="deep-linking-with-tiktok-for-business" />

## TikTok for Businessとのディープリンク

<Anchor target="_blank" href="https://ads.tiktok.com/help/article/understanding-deeplinks-and-deferred-deeplinks?lang=en">TikTokは、キャンペーン、広告グループ、広告を作成するときに、広告レベルで複数のキャンペーン目標に対してディープリンクとディファードディープリンクをサポートしています</Anchor>。ユーザーが特定のコンテンツに移動するためのディープリンクを作成することで、TikTok広告へのユーザーのエンゲージメントに基づいてカスタマイズされたコンテンツを提供することが可能になります。

<div id="access-tiktok-conversion-data-via-appsflyers-gcd-api-for-deep-linking" />

### ディープリンク用AppsFlyerのGCD APIを使ってTikTokコンバージョンデータにアクセス

AppsFlyerは、ディファードディープリンクのためにさまざまなソリューションを提供しています。

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">**ユニファイドディープリンク(UDL)**</Anchor>：TikTokクリックには <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#deep_link_value">deep\_link\_value</Anchor> フィールドが含まれます（広告側でディープリンクが設定されている場合）。この方式はUDLソリューションでサポートされています。
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking">**GCD（コンバージョンデータ取得）API**</Anchor>：これは、SDKレベルで直接、TikTokユーザーのコンバージョンデータにリアルタイムでアクセスするための推奨オプションです。GCD APIから返却されるデータには <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_dp">`af_dp`</Anchor> パラメータが含まれており、実際のディープリンク先（アプリ内遷移先）が格納されます。
* **コンバージョンデータパラメーターの使用：** キャンペーン名、広告セット名、またはTikTokインストールのアトリビューションデータの一部として返されるその他のフィールドを使用して、ユーザーをコンテンツに誘導するカスタムロジックを作成できます。

<div id="web-to-app-measure-app-activity-for-non-app-campaigns" />

## Web to app：非アプリキャンペーンの計測

AppsFlyerとTikTokの連携により、TikTok for Businessに紐づくアプリ以外のキャンペーンのインストール、リエンゲージメント、アプリ内イベントなどのアプリアクティビティを包括的に計測できます。

たとえば、広告の遷移先がWebランディングページであってもアプリのインストールを計測できるため、Web-to-App（W2A）のユーザージャーニーを計測できます。   
  
TikTok Ads Managerで次のステップに従うと、TikTok非アプリキャンペーンからのアプリアクティビティを効果的に計測し、ユーザー行動に関する貴重なインサイトを得ることができます。参照：<Anchor target="_blank" href="https://ads.tiktok.com/help/article/how-to-measure-app-activity-for-non-app-promotion-campaigns?lang=en">TikTokのドキュメント</Anchor>

1. TikTok広告キャンペーンページに移動し、**広告を編集**をクリックします。
2. **トラッキング** > **アプリイベント**でアプリを選択します。
3. **保存**をクリックしてください。
4. これらの手順は、キャンペーンに関連するすべての広告に適用されます。

<div id="set-up-tiktok-for-business-for-agencies" />

## 代理店向け：Tiktok for Businessとの連携

広告主の代理店は、TikTok for Businessの連携をオンにして、キャンペーンのアトリビューションの取得を開始できます。ただし、この連携には、代理店に関してはいくつかの制限があります。

<div id="send-complex-in-app-events-to-tiktok" />

<div id="important" />

<div id="agency-limitations" />

### 代理店の制限

* 代理店は、提携している広告主がTikTok for Businessをアクティベートした後にのみ、TikTok for Business連携にアクセスできます。
* 2024年1月1日以降、代理店アカウントの連携画面に表示されるアトリビューションパラメータは、**表示専用**モードで広告主アカウント側の連携から継承されます。これは、代理店が広告主のアトリビューション期間の設定を見ることはできても、自身で設定することはできないことを意味します。
* 代理店は、（許可があっても）高プライバシー設定をオンにすることはできません。これは広告主のみに限定されます。
* <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#configure-inapp-event-postbacks::8743ba60">広告主から許可</Anchor>が付与されると、代理店はアプリ内イベントのポストバックを設定できます。
* アプリ内イベントのポストバックをマッピングする際には、代理店とマーケティング担当者の両方でマッピング設定が一致していることを確認することをお勧めします。

**代理店アカウントのTiktok for Businessの連携設定：**

1. AppsFlyer管理画面左メニュー > **設定**から、**パートナーマーケットプレイス**へ移動します。
2. **TikTok for Business**を見つけて選択します。
3. **TikTokアプリID**を入力します。
4. 代理店の**TikTokアカウントID**を入力します。これにより、代理店のトラフィックが識別され、広告主のトラフィックと区別されます。
5. **連携を保存**をクリックします。

   <Image alt="tiktok.png" src="https://files.readme.io/b13ee9cd005b97c37019154a0caa10e03b846e7405777d9fc0e3db11bfb233b4-33379202036369.png" width="60.92%" />

> ❗️ **要注意**
>
> TikTok for BusinessのアカウントIDは、広告主または代理店の間で共有してはなりません。共有されている場合、広告主のすべてのインストールは代理店のダッシュボードに自動的に紐付けられます。

<div id="smart-plus-campaigns-reporting" />

## Smart Plusキャンペーンのレポート

Smart Plusは、複数のクリエイティブを同一広告ユニット内でテストできる新しいTikTokキャンペーンタイプです。自動クリエイティブテストを通じて、パフォーマンス最適化を支援します。

<Anchor target="_blank" href="https://ads.tiktok.com/help/article/about-smart-plus-campaign?lang=en">Smart Plusキャンペーンの詳細はこちら</Anchor>

<div id="how-smart-plus-campaigns-are-structured" />

### Smart Plusキャンペーンの構造

通常のTikTokキャンペーンは、キャンペーン、アドグループ、アドの3階層構造ですが、Smart Plusキャンペーンではクリエイティブレイヤーが追加され、4階層構造になります。

1. キャンペーン
2. アドセット
3. アド
4. クリエイティブ

<div id="note-12" />

<div id="how-smart-plus-data-is-reported-in-appsflyer" />

### AppsFlyerにおけるSmart Plusデータのレポート方法

AppsFlyerでは、TikTok Smart Plusキャンペーンデータを以下のようにマッピングしています。

| TikTok側の階層 | AppsFlyer上の対応階層 | 備考 |
| --- | --- | --- |
| キャンペーン | キャンペーン | そのままマッピング |
| アドグループ | アドセット | そのままマッピング |
| アド | — | AppsFlyerではマッピングされません |
| クリエイティブ | アド | AppsFlyer上のアド階層としてマッピング |

> 📘 **注意**
>
> Smart PlusキャンペーンにおけるAppsFlyerのマッピング構造は、TikTok Ads Managerとは異なります。TikTok Ads Managerでは、レポートはアドレベルまでしか表示されず、クリエイティブ単位の専用ブレイクダウンは存在しません。一方、AppsFlyerではTikTokのクリエイティブデータを直接アド階層へマッピングします。そのため、AppsFlyerとTikTok間でパフォーマンスデータを比較した際に、差異が発生する場合があります。

## トラブルシューティング

### TikTokアプリのステータスが「Pending Verification（検証待ち）」と表示される

AppsFlyerで、アプリレベルまたはTikTokパートナーレベルのいずれかで高プライバシー一括設定（AAP）が有効になっている場合、インストールおよびアプリ内イベントのポストバックは、広告ネットワークへアトリビューションされたインストールに対してのみ送信されます。その結果、TikTokはオーガニックソースから必要なポストバックを受け取れず、「保留中の確認」ステータスになる可能性があります。

#### 推奨アクション

1. 検証目的に限り、一時的にAppsFlyer側で高プライバシー設定を無効化し、TikTokがオーガニックポストバックを受信できるようにしてください。高プライバシー一括設定を無効にすると、ユーザーレベルのデータが広告主やパートナーに利用可能になる場合があります。詳細は「<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework#高プライバシー一括設定aapが無効の場合">高プライバシー一括設定の無効化</Anchor>」を参照してください。
   1. <span class="af-ol-a"></span><Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework#aap-central-switch">アプリ設定</Anchor>に移動して高プライバシー一括を無効にします。
   2. [TikTokのパートナー連携設定](#高プライバシーポストバック)に移動し、高プライバシーポストバックを無効にします。
2. [ポストバックセクション](#デフォルトのポストバック)で、ポストバック内容を設定します：[オーガニックを含むすべてのメディアソース：](#デフォルトのポストバック)
3. TikTokが少なくとも1回のインストールまたはアプリ内イベントのポストバックを受信するのを待ってください。受信後、アプリは自動的にTikTokダッシュボードで「認証済み」に更新されるべきです。
4. 確認後、プライバシー設定に基づいて、再度[高プライバシー一括設定を有効にする](#高プライバシーポストバック)ことができます。

> 📄 **参照：**
>
> * 中国トラフィックのための<Anchor target="_blank" href="/marketers/ja/docs/bytedance-ads-china-campaign-configuration">Bytedance Ads (Ocean Engine)</Anchor> (bytedance\_int)
> * <Anchor target="_blank" href="/marketers/ja/docs/skan-interoperation-with-tiktok-for-business">TikTok for BusinessとSKANの相互運用</Anchor>

<div data-zendesk-anchors="01H8VVCC8GW5AZ3M475XFZY9JW=%E6%B3%A8%E6%84%8F overview=%E6%A6%82%E8%A6%81 01H8VVCC8G3ZXZJMHSMJ67GMG4=%E6%A6%82%E8%A6%81 setting-up-tiktok-for-business%C2%A0integration=tiktok-for-business%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A 01H8VVCC8GPY4SEFGK30Q1BJZ6=tiktok-for-business%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A 01H8VVCC8G6P25R0N5A7S3NGY7=%E6%B3%A8%E6%84%8F-1 01H8VVCC8GY6WTH0404RH2AR9F=integration-tab activate-partner::e4f2f638=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 01H8VVCC8G0KR4AA2HD9S8QBKD=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 advanced-privacy=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H8VVCC8G0Z6ZHC10KVY9CGGQ=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H8VVCC8GC57YTDWA9EB2VP87=%E6%B3%A8%E6%84%8F-2 general-settings=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A 01H8VVCC8GSDPSNN0AJPVZPR8P=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A 01H8VVCC8G2JB115XW49HJQFHA=%E6%B3%A8%E6%84%8F-3 default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H8VVCC8GW677RN6R6CV35KGG=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H8VVCC8G6M8D3WQ2CM10ZNZX=%E6%B3%A8%E6%84%8F-10 install-attribution=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC 01H8VVCC8GK8VFPBEPAMVHCAWM=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC 01JE5ZMSXK5Q9KWKY8C6ZXEGD9=%E6%B3%A8%E6%84%8F-5 01H8VVCC8G3YFDZVV9X9709F9M=%E6%B3%A8%E6%84%8F-6 reinstall-attribution=%E3%83%AA%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC h_01K6D37PG96P2MG99BETK25GYA=%E3%83%AA%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC h_01K6D43X96RNY6H2RJEYW4KPCY=%E6%B3%A8%E6%84%8F-7 reengagement-attribution=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88cv%E3%81%AE%E8%A8%88%E6%B8%AC 01H8VVCC8HHG5290PYF0BT29QA=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88cv%E3%81%AE%E8%A8%88%E6%B8%AC h_01JJM8MPX2HMWBZSSAAC4YCZ3Q=%E6%B3%A8%E6%84%8F-8 01H8VVDWH85M34K7Z75BAT7BQW=%E9%87%8D%E8%A6%81 ignore-active-users-for-retargeting=%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%92%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E8%A8%88%E6%B8%AC%E3%81%8B%E3%82%89%E9%99%A4%E5%A4%96%E3%81%99%E3%82%8B h_01HNWSTJZPFQVQ5C8M0JA1J0T5=%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%92%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E8%A8%88%E6%B8%AC%E3%81%8B%E3%82%89%E9%99%A4%E5%A4%96%E3%81%99%E3%82%8B h_01HMXNJVHK9C3FT8E04RE0TH99=%E6%B3%A8%E6%84%8F-9 inapp-event-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H8VVCC8HHZRFQ2T1X478YZMP=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H8VVCC8HDMTY1P2SG31HD61K=%E6%B3%A8%E6%84%8F-10 01H8VVCC8H53ZRMDBNK1436NAX=attribution-link-tab 01H8VVCC8H74GDVCNAXT0741MG=cost-tab-for-cost-clicks-and-impressions 01H8VVCC8HFJF62TC7DNXRH22A=%E6%B3%A8%E6%84%8F-11 for-xpend-subscribers=roi360%E3%82%92%E3%81%94%E5%A5%91%E7%B4%84%E3%81%AE%E3%81%8A%E5%AE%A2%E6%A7%98%E5%90%91%E3%81%91 01H8VVCC8HWDC9A03FRY5BC87Y=roi360%E3%82%92%E3%81%94%E5%A5%91%E7%B4%84%E3%81%AE%E3%81%8A%E5%AE%A2%E6%A7%98%E5%90%91%E3%81%91 01H8VVCC8H90ANM70QAHKTQQ1S=ad-revenue-tab 01H8VVCC8HAG0XVWE2T9PRDHTK=permissions-tab deep-linking-with-tiktok-for-business=tiktok-for-business%E3%81%A8%E3%81%AE%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF h_01JJM8MPX2X37WVR86S7786S06=tiktok-for-business%E3%81%A8%E3%81%AE%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF accessing-tiktok-conversion-data-via-appsflyers-gcd-api-for-deep-linking=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E7%94%A8appsflyer%E3%81%AEgcd-api%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%A6tiktok%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AB%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9 h_01HVQR1TC5WVRDS24R9ZKD2HW2=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E7%94%A8appsflyer%E3%81%AEgcd-api%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%A6tiktok%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AB%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9 measuring-app-activity-for-nonapp-campaigns=web-to-app%E9%9D%9E%E3%82%A2%E3%83%97%E3%83%AA%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%88%E6%B8%AC h_01J7MYAMBQ8M0JN005FSXQDZNS=web-to-app%E9%9D%9E%E3%82%A2%E3%83%97%E3%83%AA%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%88%E6%B8%AC setting-up-tiktok-for-business-for-agencies=%E4%BB%A3%E7%90%86%E5%BA%97%E5%90%91%E3%81%91tiktok-for-business%E3%81%A8%E3%81%AE%E9%80%A3%E6%90%BA 01H8VVCC8HVNNQ9PJS4ZQCVDNS=%E4%BB%A3%E7%90%86%E5%BA%97%E5%90%91%E3%81%91tiktok-for-business%E3%81%A8%E3%81%AE%E9%80%A3%E6%90%BA agency-limitations=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AE%E5%88%B6%E9%99%90 h_01HHVGS94CB9XC0T63VFDZ18JS=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AE%E5%88%B6%E9%99%90 01H8VVCC8HWJ2WQ83E0CZMEHH1=%E8%A6%81%E6%B3%A8%E6%84%8F smart-campaigns=smart-plus%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 smart-plus-campaigns-reporting=smart-plus%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01K9AGYS6XCDS3193ZAK7Z208F=smart-plus%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 how-smart-plus-campaigns-are-structured=smart-plus%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E6%A7%8B%E9%80%A0 h_01K9AGYS6XSXJ9DD6XYDHVYMYK=smart-plus%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E6%A7%8B%E9%80%A0 how-smart-plus-data-is-reported-in-appsflyer=appsflyer%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8Bsmart-plus%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E6%96%B9%E6%B3%95 h_01K9AGYS6XYT763ST1H1T4SXT8=appsflyer%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8Bsmart-plus%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E6%96%B9%E6%B3%95 h_01K9AGYS6X12RC8245TY1RGVNX=%E6%B3%A8%E6%84%8F-12 troubleshooting=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 h_01JQBGSDV84TBJGXGBSFWN6C4D=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 my-app-status-on-tiktok-is-%E2%80%98pending-verification%E2%80%99=tiktok%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9%E3%81%8Cpending-verification%E6%A4%9C%E8%A8%BC%E5%BE%85%E3%81%A1%E3%81%A8%E8%A1%A8%E7%A4%BA%E3%81%95%E3%82%8C%E3%82%8B h_01JQBGSKBY6C3289G3NY3WN74K=tiktok%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9%E3%81%8Cpending-verification%E6%A4%9C%E8%A8%BC%E5%BE%85%E3%81%A1%E3%81%A8%E8%A1%A8%E7%A4%BA%E3%81%95%E3%82%8C%E3%82%8B recommended-resolution=%E6%8E%A8%E5%A5%A8%E3%82%A2%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3 h_01JQBGWA8ASV6MBA5FKGD56DKZ=%E6%8E%A8%E5%A5%A8%E3%82%A2%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3 h_01HE7RY8K7HV2CTZ2S537YRCNQ=%E5%8F%82%E7%85%A7" />
