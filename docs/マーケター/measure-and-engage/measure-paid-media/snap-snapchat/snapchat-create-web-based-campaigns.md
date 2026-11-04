---
title: Snapchat向けのウェブキャンペーンを作成する
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
  created_at: '2025-11-27T14:39:44Z'
  edited_at: '2026-10-14T09:23:51Z'
  id: 41365000854161
  locale: ja
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/ja/articles/41365000854161
---
> **概要：** Snapchat広告のウェブキャンペーンを使って、Snapchat広告からのウェブからアプリへのコンバージョンを帰属させましょう

<div id="overview" />

## 概要

AppsFlyerでは、WebキャンペーンにおけるTikTok Ads（`snapweb_int`）との連携をサポートしており、TikTokのイベントAPIを使ってキャンペーンのアトリビューション情報とコンバージョンデータへTikTokへレポートすることができます。このデータを、TikTokは広告ターゲティングの最適化、パフォーマンスの計測、カスタムオーディエンスの作成に活用できます。

<div id="important" />

> 🚧 **【重要】**
>
> 現在、TikTok Webとの連携において、CAPIへのリエンゲージメントCVのポストバック送信はサポートしていません。

<div id="prerequisites" />

### 前提条件

Snapchatのウェブ連携を有効にする前に、必ずビジネスアカウントを登録してください。

<div id="how-to-create-a-snapchat-ads-web-campaign" />

### Snapchat広告のウェブキャンペーンの作り方

この記事では、AppsFlyerを使用してモバイルアプリ、PCアプリ、コンソールアプリ向けにTikTok AdsでWebキャンペーンを設定するために必要な手順を記載しています。セットアップには、TikTok AdsとAppsFlyerの連携設定の内容、両プラットフォームでのキャンペーン設定、OneLinkスマートスクリプトまたはOneLinkスマートバナーによるランディングページの作成が含まれます。

設定プロセスには、次の必須手順が含まれます：

* [AppsFlyerでSnapchat Adsのウェブ連携を設定してください](#appsflyerでsnapchat-adsのウェブ連携を設定してください) (必須)
* [Snapchat広告でAppsFlyer連携を設定する](#snapchat広告でappsflyer連携を設定する) (必須)

以下は必要に応じて行う任意の設定項目です：

* [OneLink Smart Scriptを使ったランディングページを作成する](#onelink-smart-scriptを使ったランディングページの作成)（任意）
* [OneLink Smart Bannerを使用したランディングページの作成](#onelink-smart-bannerを使ったランディングページの作成)（任意）

<div id="set-up-snapchat-ads-web-integration-in-appsflyer" />

## AppsFlyerでSnapchat Adsのウェブ連携を設定してください

まずはSnapchat広告のウェブ連携を有効にしてください。次に、AppsFlyerがEvents APIに送信するポストバックを設定しましょう。

<div id="1-activate-the-snapchat-ads-web-integration" />

<Accordion title="1.Snapchat Adsのウェブ連携を有効化してください">

Snapchat広告のウェブ連携を有効にするには:

1. AppsFlyer管理画面左メニュー **連携** > **パートナーマーケットプレイス**へ移動します。
2. 検索**Snapchatウェブ**そして選択します。
3. **連携設定**をクリックしてください。**連携設定画面**へ移動してください。
4. **連携**タブにて、**パートナーを有効にする**をオンにしてください。 このトグルは、このパートナーとの連携を続ける限り、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">オン（有効）</Anchor>のままにしておく必要があります。
5. （iOSのみ）**高プライバシー一括設定**をオフに設定してください。
6. **Pixel ID：** Pixel ID を入力してください。Snapchat広告マネージャーから、以下の指示に従って生成または取得できます [Snapchat広告の公式ドキュメント](https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US)
7. **Access Token：** Access Tokenを入力してください。生成または取得するには、次の通りに従います。[Snapchat広告の公式ドキュメントに記載されている指示](https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted)

</Accordion>

<div id="2-enable-viewthrough-attribution" />

<Accordion title="2.ビュースルー計測の有効化">

AppsFlyerは、Snapchatのウェブキャンペーンに対してビュースルーアトリビューションをサポートしています。[スマートスクリプト](#onelink-smart-scriptを使ったランディングページの作成)または[スマートバナー](#set-up-smart-banners-landing-page)-ランディングページを有効にしました。これにより、ユーザーが広告をクリックしなくても、広告インプレッションによってトリガーされるアプリインストールに対して確率的モデリング(PMOD)の帰属が可能になります。

また、利用可能な場合には、`ScCid` が計測精度を高めるためにTikTokへのポストバックに含まれます。

**Snapchatのウェブビュースルー帰属を有効にするには:**

1. AppsFlyerのサイドバーから開きます**アクティブインテグレーション**>**Snapchat広告のウェブ**.
2. **連携**のタブで、**インストール計測**セクションまでスクロールしてください。
3. **ビュースルーのインストール計測**を有効にしてください。
4. **［任意］** 必要に応じて**クロスプラットフォームの同等アトリビューション優先度**をオンに変更してください。詳細については、 <Anchor target="_blank" href="/marketers/ja/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">クロスプラットフォームのインプレッションに対して同等の優先度を有効にする</Anchor>をご覧ください。
5. **計測リンク**のタブをクリックしてください。
6. **ビュースルー計測**のセクションまでスクロールして、**ビュースルーのルックバック期間**（最大24時間）を設定してください。
7. 設定を適用するには、画面右下の**連携を保存**をクリックしてください。

</Accordion>

<div id="3-set-inapp-event-postbacks" />

<Accordion title="3.アプリ内イベントのポストバック設定">

現在、TikTokへ自動的に送付されるデフォルトポストバックの項目はインストールのみです。その他のイベントタイプについては、AppsFlyerのイベントをSnapchat広告のイベントにマッピングしてカスタムポストバックを作成できます。これらのポストバックはSnapchat広告マネージャーで確認できます。

アプリ内イベントのポストバックを設定するには、次の手順に従ってください：

1. **アプリ内イベントポストバック**を有効にしてください。
2. 必要に応じて、アプリ内イベントのポストバックウィンドウを設定します(アプリ内イベントのポストバックウィンドウの設定については詳しくはこちらをご覧ください<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#アプリ内イベントポストバック期間">アプリ内イベントポストバック設定</Anchor>).
3. **イベントを追加**をクリックして、SDKイベントをリストに追加してください。
4. **AppsFlyer側のSDKイベント名**の列で、ドロップダウンのリストからイベント名を選択してください。（アプリに実装されているSDKまたはS2Sイベントのうち、AppsFlyerが既に受信しているイベント名が表示されます。）
5. では**パートナーイベントにマッピング**柱,リストから最も適したあらかじめ定義されたパートナーイベントを選択します。
6. **送信オプション**の項目で、**このパートナーのみ**を選択すると、このパートナーから発生したユーザーが実行したイベントのみを対象に、アプリ内イベントのポストバックが送信されるようになります。
7. では**含まれます**カラムで、収益値付きのイベントを送信するかどうかを選択します。詳細：<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#ポストバックに含めるデータ">ポストバックに含めるデータ</Anchor>

   <div id="note" />

   > 📘 **注意**
   >
   > * 購入イベントを設定する場合は、**送信データ**項目は**イベント値と収益を送信**に設定してください。他のオプションを選択するとポストバックが失敗します。
   > * 現在は、購入イベントのみを収益に含める設定が可能です。

8. ［任意］**条件を追加**アイコンをクリックして、ポストバックする<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">イベントの条件を設定可能です。</Anchor>
9. 最後に、**連携の保存**をクリックして完了です。
10. [任意]統合を保存した後、設定ページに留まったまま、パートナーと追加のアプリを統合できます:
    1. 左上のパートナー名の下にある、アプリ名をクリックしてアプリ一覧を開いてください。
    2. リストから別のアプリを選択してください。
    3. 選択したアプリに対して上記の手順を繰り返します。

</Accordion>

<div id="set-up-appsflyer-integration-in-snapchat-ads" />

## Snapchat広告でAppsFlyer連携を設定する

Snapchat広告マネージャーで次のステップを実行してください。

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1.キャンペーンの種類、目的、目標の設定">

Appsflyerから送信される任意のアプリ内イベントをキャンペーンの目標として選択するか、アプリのインストールを最適化したい場合は「ダウンロード」を選択できます。

<div id="warning" />

> ❗️ **注意**
>
> 選ばないことを確認してください**アプリイベント;** そうでなければ、SnapchatはSRN APIを使ってこれらのコンバージョンを主張し、報告や最適化のミスライメントを引き起こす可能性があります。

</Accordion>

<div id="2-set-destination-url" />

<Accordion title="2.遷移先URLの設定">

1. **遷移先(Destination)** 内にある**WebサイトURL**の項目に広告からの遷移先となるURLを入力してください。なお、入力するURLは次のいずれかである必要があります：
   * **［１］Webランディングページ：** ランディングページは、次のような場合に使用することをお勧めします：

     * 複数のプラットフォームでアプリをリリースしている場合
     * ランディングページを使用して、対象の商品に関する詳細な情報を提供したい場合
     * ランディングページを使用して、より多くのデータを収集したい場合

     これらすべてのユースケースについて、 [スマートスクリプトを使用したランディングページ](#onelink-smart-scriptを使ったランディングページの作成) 又は [スマートバナー](#onelink-smart-bannerを使ったランディングページの作成)を作成してください。
   * **［２］AppsFlyerの計測リンク：** AppsFlyerの計測リンク（OneLink、シングルプラットフォーム用の計測リンク、クロスプラットフォーム用の計測リンク）は、ランディングページを経由せずに直接ストアに遷移させ、アプリダウンロードを促したい場合にオススメです。
2. **URLパラメーターを作成する**をクリックして、パラメーターをランディングページURL もしくは AppsFlyer計測リンクに対してに追加してください。
3. **カスタムパラメータ**の項目で、**パラメータを追加**をクリックしてください。

   [<Image alt="" src="https://files.readme.io/cb3ceba75974f7a57d7f26c3587fd0d0c401427d26fcacff40f2514981b9b02f-small-41366139737873.png" width="2810px" />Screenshot 2023-07-19 at 13.54.21.png](https://files.readme.io/cb3ceba75974f7a57d7f26c3587fd0d0c401427d26fcacff40f2514981b9b02f-small-41366139737873.png)
4. AppsFlyerのパラメータをSnapchatの値にマッピングします。
   * 遷移先URLが**ランディングページ、OneLinkの計測リンク、または単一プラットフォームの計測リンク**の場合、次のAppsFlyerのパラメータをTikTokの対応するパラメータにマッピングしてください。

| AppsFlyerパラメータ | マッピングされたSnapchatの価値 |
| --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#pid">`pid`</Anchor> | `snapweb_int` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#c">`c`</Anchor> | `{{campaign.name}}`* |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | `{{campaign.id}}`* |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adSet.name }}`* |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adSet.id}}`* |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{creative.name }}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}`* |
| <Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#attribution::1d1e08b5">`af_channel`</Anchor> | `{{site_source_name}}` |

     最終的なURLのサンプルは以下のような形になります：

     ```
     https://app.appsflyer.com/{app_id}?pid=snapweb_int&c=__campaign_name__&af_c_id=__campaign_id__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__&af_r={https://Add-your-store-url.com}
     ```

     * ※アプリのAPKファイルがGoogle Playストアに公開されていない場合には、 <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_r">`af_r`</Anchor> のパラメータを追加して、ストアのURLを記載してください。（例：`https://Add-your-store-url.com` ）

* 遷移先URLが **PC・コンソールストア**の場合は、次の表の指示に従ってリンクを作成してください。詳細については、以下を参照してください： <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-direct-attribution-links">CTV、PC、コンソールプラットフォームのダイレクト計測リンク</Anchor>

| 計測リンクの構造 |  |
| --- | --- |
| ベースURL | engagements.appsflyer.com/v1.0/c2s/click/app/ |
| 必須のpathパラメータ | ▪ platform：(例) steam  <br />▪ app\_id：(例) 123456 |
| 必須パラメータ | ▪ af\_media\_source  <br />▪ af\_campaign\_id  <br />▪ af\_r |
| その他パラメータ | <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-direct-attribution-links#パラメーター">すべてのパラメータ一覧</Anchor> |
| URL例： | `https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source={media_source}&af_campaign_id={campaign_id}&af_r={app_store_url}` |

  次のAppsFlyerパラメータをTikTokのパラメータにマッピングしてください：

| AppsFlyerパラメータ | マッピングされたSnapchatの価値 |
| --- | --- |
| `af_media_source` | `snapweb_int` |
| `af_campaign` * | `{{campaign.name}}`* |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_c_id">`af_campaign_id`</Anchor> | `{{campaign.id}}`* |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adSet.name }}`* |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adSet.id}}`* |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{creative.name }}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}`* |
| <Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#attribution::1d1e08b5">`af_channel`</Anchor> | `{{site_source_name}}` |

  * キャンペーン分析を簡素化するために、キャンペーン名の冒頭または末尾にキャンペーンタイプを示す\_webまたは\_mobileを追加してください。（例：campaign-name\_web）

  クロスプラットフォームURLの例：

  ```
  https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=snapweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
  ```

  <div id="note-1" />

  > 📘 **注意**
  >
  > TikTokは、広告がクリックされると遷移先URLに`ScCid={{ScCid}}`を自動的に追加します。


  > 📄
  >
  > AppsFlyerリンクのパラメータの包括的なガイドについては、<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#計測リンクのパラメータ">計測リンクのパラメータ</Anchor>を参照してください。


</Accordion>

<div id="create-a-landing-page-with-onelink-smart-script" />

## OneLink Smart Scriptを使ったランディングページの作成

**ユーザージャーニー：** ユーザーがMeta広告をクリックすると、モバイルWebサイトに誘導されます。そのWebサイトには、複数プラットフォームのどれかからアプリをダウンロードするように促すCTAボタンが設置されています。いずれかのCTAボタンをクリックすると、ユーザーは任意のストアへ遷移します。

<div id="endtoend-data-flow" />

<Accordion title="データフロー">

[![](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)

1. Snapchatの広告URLには以下が含まれます。`pid=snapweb_int`パラメータ。ユーザーが広告をクリックすると、`ScCid`のパラメータがクリックURLに自動的に追加されます。
2. ユーザーは、遷移先URL（Smart Scriptを実装したランディングページ）へリダイレクトされます。
3. ランディングページが読み込まれると、Smart Scriptは受信URLパラメーターを含むインプレッションをAppsFlyerへ記録します。このインプレッションの計測により、ランディングページからのビュースルー計測が可能になります。（詳細：<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">インプレッションとビュースルーの計測の詳細について</Anchor>）
4. Smart Scriptは、`ScCid`パラメータが追加されているランディングページURL（受信URL）のパラメータ内容に基づいて、ページ内のストアへの遷移ボタンに設定されているURL（送信URL）を自動生成します。遷移ボタンの遷移先としては、以下の候補があります：
   * OneLink経由でGoogle Play / App Storeへ遷移
   * 複数のプラットフォームストア（CTV、Epic、Steamなど）：この場合、Smart Scriptはプラットフォームごとに単一プラットフォーム用の計測リンクを生成し、指定したプラットフォームのストアへ遷移させます。
   * クリック後にユーザー端末にAPKファイルをダウンロード
5. ユーザーがCTAボタンをクリックすると、クリックがAppsFlyerに記録されます。
6. ユーザーはストアにリダイレクトされ、アプリをダウンロードします。
7. ユーザーがアプリを開くと、AppsFlyerにインストールイベントが登録されます。
8. AppsFlyerは、確率論的モデリングに基づいて、または[インストールリファラー](https://www.appsflyer.com/glossary/install-referrer/)が利用可能な場合は決定論的手法でインストールを計測します。
9. `ScCid`パラメータと他のイベントパラメータを含むポストバックが生成され、Events APIを介してTikTokに送信されます。TikTokは、この  のパラメータを使用して個々のクリックを判別し、他の各種パラメータはキャンペーンの最適化に役立ちます。

</Accordion>

<div id="set-up-a-smart-script-landing-page" />

<Accordion title="ランディングページへのSmart Scriptの実装">

Smart Scriptを使用してTikTok Adsのキャンペーンを設定するには、以下の手順に沿ってください：

1. キャンペーンのOneLink計測リンク用に、OneLinkテンプレートを設定してください。詳細は<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレートの作成方法</Anchor>をご覧ください。
2. Smart Scriptのコードを作成してください。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink Smart Scriptの作成方法</Anchor>をご覧ください。

   <div id="note-5" />

   <div id="note-2" />

   > 📘 **注意**
   >
   > 以下の手順は、Smart ScriptでSnapchat広告キャンペーンを設定するために必要な具体的な手順を説明しています。Smart Scriptを使ったキャンペーンの設定方法に関する包括的なガイドについては、<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink Smart Script V2の設定</Anchor>ページ内の<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink Smart Scriptの作成方法</Anchor>のセクションを参照してください。

3. 関連するURLパラメータがすべてランディングページ内のURL（受信URL）に追加されていることを確認してください。受信URLに付随するパラメータを確認するには、Snapchat Ads Managerを開き、宛先URL作成時に設定したURLパラメータを確認してください。詳細は、[遷移先URLの設定](#2-set-destination-url)をご覧ください。
4. Snapchat広告キャンペーンに必要な受信URLパラメータを送信URLパラメータにマッピングします。ユーザーがCTAボタンをクリックすると、これらのパラメータはAppsFlyerに送信されます:
   * **PID：** Smart Scriptが `pid=snapweb_int`のパラメータ値を受信URLから取得し、送信URLの対応するパラメータへマッピングします。
   * **シド**:その`ScCid`パラメータは、アプリ内イベントのポストバックをSnapchatに正常に送信するために必要です。`ScCid` パラメータは、**Smart Script**のページで、**URLパラメータのマッピング**を行う際に手動で追加する必要があるので注意してください：

     1. **マッピング：** 項目で、**カスタムパラメータ**を選択してください。
     2. では **送信URLパラメータ**および <strong>URLパラメータの受信、</strong>入場**シド**.

     <div id="note-3" />

     > 📘 **注意**
     >
     > AppsFlyerの生データレポートに表示するには、受信データもマッピングする必要があります `ScCid` パラメータは、出て行くものとは別に `ScCid` パラメータを、出て行くものの一つに変換します `af_sub[1–5]` パラメータ。


</Accordion>

<div id="set-up-a-smart-script-crossplatform-landing-page" />

<Accordion title="クロスプラットフォーム向けランディングページでのSmart Scriptの実装">

TikTok Adsのキャンペーン向けにSmart Scriptをクロスプラットフォームのランディングページに設定するには、次の手順に沿ってください：

1. キャンペーンのOneLink計測リンク用に、OneLinkテンプレートを設定してください。詳細は<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレートの作成方法</Anchor>をご覧ください。
   * OneLinkテンプレートでクロスプラットフォーム計測を有効にしてください。（詳細）詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-cross-platform-links-for-multi-device-campaigns#クロスプラットフォーム計測用のonelinkテンプレートの作成">クロスプラットフォームの帰属のためのOneLinkテンプレートを作成する</Anchor>.
2. 関連するURLパラメータがすべてランディングページ内のURL（受信URL）に追加されていることを確認してください。受信URLに追加されたパラメータを確認するには、TikTok Ads Managerを開き、遷移先URLの作成時に設定したURLパラメータを確認してください。詳細は、[遷移先URLの設定](#2-set-destination-url)をご覧ください。
3. 各受信URLパラメータに対して、マッピングする送信URLパラメータを決定してください。たとえば、受信URLの`af_site_id`パラメータを、送信URLの`af_site_id`パラメータにマッピングするといった形です。
4. 空の値を渡すことができない必須の［送信パラメータ］については、デフォルト値を決定してください。
5. 開発者に次の情報を共有してください：
   * ［受信パラメータ］と［送信パラメータ］のマッピング一覧：開発者は、受信/送信パラメータのマッピング一覧に基づいて、送信URLを生成するスクリプトを作成する必要があります。
   * 各パラメータのデフォルト値：スクリプトは、対応する受信URLパラメータの値がない場合に、送信URLパラメータにデフォルト値を挿入します。
   * OneLink計測リンクを使用している場合は、そのドメインとテンプレートIDを開発者に共有してください。開発者はこれを使用して、送信用のOneLink URLを作成します。（例： `yourbrand.onelink.me/A1b2`｜ブランドドメインの場合： `click.yourbrand.com/A1b2`）
   * 開発者に以下の Dev Hubリンクを共有してください：
     * [モバイルアプリ以外のプラットフォームへの送信URLの作成方法とコードサンプル](https://dev.appsflyer.com/hc/docs/create-direct-click-url)
     * [クロスプラットフォーム向けのランディングページを作成するためのデモと手順](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/)

* 送信URLに、受信パラメータ `ScCid` を含めるよう、開発者に忘れずに依頼してください。

  <div id="note-4" />

  > 📘 **注意**
  >
  > AppsFlyerのローデータレポートのカラムに表示するには、受信URLの `ScCid` パラメータを（送信URLの`ScCid` パラメータに追加で）送信URLパラメータの `af_sub[1-5]` のいずれかにもマッピングする必要があります。


</Accordion>

<div id="create-a-landing-page-with-onelink-smart-banners" />

## OneLink Smart Bannerを使ったランディングページの作成

**ユーザージャーニー：** ユーザーがMeta広告をクリックすると、モバイルWebサイトに誘導されます。ページにアクセスすると、Smart BannerとアプリストアからアプリをダウンロードするためのCTAボタンが表示されます。

<div id="endtoend-data-flow::b905b9a5" />

<Accordion title="データフロー">

1. Snapchatの広告URLには以下が含まれます。`pid=snapweb_int`パラメータ。ユーザーが広告をクリックすると、`ScCid`のパラメータがクリックURLに自動的に追加されます。
2. ユーザーが、遷移先URL（Smart Bannerを実装したランディングページ）にリダイレクトされます。
3. ランディングページが読み込まれると、Smart BannerからAppsFlyerへ、受信URLパラメータを含んだ状態で<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">インプレッション</Anchor>のイベントが送信されます。このインプレッションの計測を行うことで、ランディングページでのビュースルー計測が可能になります。インプレッションやビュースルー帰属について知りたい方は、こちらをご覧ください。<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">カスタムインプレッションURLを作成する</Anchor>.
4. Smart Bannerは、バナーのCTAボタンの送信URLを生成します。送信URLは、`ScCid` パラメータを含む受信URLパラメータに基づいて生成されます。Smart Bannerでは、OneLinkベースのリンクのみを生成できます。
5. ユーザーがSmart Bannerのクリックすると、クリックがAppsFlyerに記録されます。
6. ユーザーはストアにリダイレクトされ、アプリをダウンロードします。
7. ユーザーがアプリを開くと、AppsFlyerにインストールイベントが登録されます。
8. AppsFlyerは、確率論的モデリングに基づいて、またはインストールリファラーが利用可能な場合は決定論的手法でインストールを計測します。
9. `ScCid`パラメータと他のイベントパラメータを含むポストバックが生成され、Events APIを介してTikTokに送信されます。TikTokは、この  のパラメータを使用して個々のクリックを判別し、他の各種パラメータはキャンペーンの最適化に役立ちます。

</Accordion>

<div id="set-up-a-smart-banners-landing-page" />

<Accordion title="ランディングページへのSmart Bannerの実装">

Smart BannerをTikTok Adsキャンペーンを設定するには、以下の手順に従ってください：

1. キャンペーンのOneLink計測リンク用に、OneLinkテンプレートを設定してください。詳細は<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレートの作成方法</Anchor>をご覧ください。
2. Smart Bannerを作成してください。

   > 📘 **注意**
   >
   > 以下の手順には、スマートバナーを使ったSnapchat広告キャンペーンを設定するために必要な具体的な手順が説明されています。Smart Bannerの設定方法に関する包括的なガイドについては、<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banner（マーケター向け）</Anchor>の<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers#設定">設定セクション</Anchor>をご覧ください。

3. Snapchat広告キャンペーンのスマートバナーパラメータを設定する:

   * 関連するURLパラメータがすべてランディングページ内のURL（受信URL）に追加されていることを確認してください。
   * 受信URLに付随するパラメータを確認するには、Snapchat広告マネージャーを開き、設定したURLパラメータを確認してください。 [宛先URLの作成](#2-set-destination-url).

   <div id="note-6" />

   > 📘 **注意**
   >
   > 最も重要なのは、受信URLにおいて `pid=snapweb_int` と `ScCid` が含まれており、Smart Bannerがそれらを収集可能な状態にあることです。これら2つのパラメータは、計測とTikTokへのポストバックの送信に必要です。


</Accordion>

<div id="view-web-to-app-attribution-data" />

## **Web to Appの計測データの確認方法**

Webキャンペーンの各種イベントは、元々の`snapweb_int`のPIDでMetaへ送信されますが、AppsFlyerの管理画面上およびローデータレポートでは`snapchat_int`のPIDの下に記録されます。これはプライマリーコンバージョンイベントとコンバージョンアシストイベントの両方に当てはまります。

この統一されたレポートビューにより、Webとアプリのキャンペーンパフォーマンスを、包括的なWebとモバイルのコスト情報を含んだ状態で分析できるようになります。

<div id="view-in-the-dashboard" />

### **管理画面上でのデータ表示について**

MetaのWeb-to-Appキャンペーンの計測データは、オーバービューとアクティビティダッシュボードにおいてすべて`snapchat_int`の下に紐づく形で表示されます。これにより、プラットフォーム全体でのキャンペーンの結果を確認できるようになります。標準フィルタとブレークダウンを使用して、Meta広告のデータにおけるアプリとWebのトラフィックを比較してください。

<div id="view-in-raw-data-and-api-reports" />

### **ローデータとAPIレポート内でのデータ表示**

* ローデータエクスポートと各種API経由のデータでは、`snapchat_int`のカラムにおける**のPIDのデータに、MetaのWebキャンペーンのデータが含まれます。Webキャンペーンの設定詳細を確認するには、Webキャンペーン作成時に使用されたPIDとしてを表示するフィールドを参照してください。**
* **ポストバックレポート**は、ポストバックが送信された元のメディアソースとして`snapweb_int`を示します。

<div id="traits-and-limitations" />

## 特性と制約事項

| 特性 | 備考 |
| --- | --- |
| （コスト連携・収益管理） | Snapchat広告のコストデータ(`snapweb_int`)ウェブベースのキャンペーンは自動的に取得されるわけではありません。代わりに、<Anchor target="_blank" href="/marketers/ja/docs/import-cost-data#procedures">メールでのファイルアップロード、もしくはAppsFlyerの管理画面上で手動アップロード</Anchor>のいずれかを使用して、手動でコストをインポートする必要があります。これは、ROI360のご契約者されている場合でも同様です。 |
| クリック数とインプレッション数(一時的な制限) | ウェブキャンペーンのクリック数やインプレッションはSnapchat SRNから一時的に利用できません(`snapchat_int`). |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01KB2W28THC55F0AJ0KZJPQ6S5=%E6%A6%82%E8%A6%81 h_01KB2W28THSST3148Y5Y07PJ7S=%E9%87%8D%E8%A6%81 prerequisites=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01KB2W28THW7E6TRVTTHJZ9BP4=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 how-to-create-a-snapchat-ads-web-campaign=snapchat%E5%BA%83%E5%91%8A%E3%81%AE%E3%82%A6%E3%82%A7%E3%83%96%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E4%BD%9C%E3%82%8A%E6%96%B9 h_01KB2W28THTST7HWTJA9TTGPGG=snapchat%E5%BA%83%E5%91%8A%E3%81%AE%E3%82%A6%E3%82%A7%E3%83%96%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E4%BD%9C%E3%82%8A%E6%96%B9 set-up-snapchat-ads-web-integration-in-appsflyer=appsflyer%E3%81%A7snapchat-ads%E3%81%AE%E3%82%A6%E3%82%A7%E3%83%96%E9%80%A3%E6%90%BA%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%97%E3%81%A6%E3%81%8F%E3%81%A0%E3%81%95%E3%81%84 h_01KB2W28THQJF8K4AWTRXNA3RX=appsflyer%E3%81%A7snapchat-ads%E3%81%AE%E3%82%A6%E3%82%A7%E3%83%96%E9%80%A3%E6%90%BA%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%97%E3%81%A6%E3%81%8F%E3%81%A0%E3%81%95%E3%81%84 h_01KB2W28TH6NZCGCJAN8K3WFGA=1-activate-the-snapchat-ads-web-integration h_01KB2W28TJ6XY7WKR4VC5XS7DS=2-enable-viewthrough-attribution h_01KB2W28TJGRKP3C50ZPQAWAS9=3-set-inapp-event-postbacks h_01KB2W28TJ14KC606KE82Q7BB7=%E6%B3%A8%E6%84%8F set-up-appsflyer-integration-in-snapchat-ads=snapchat%E5%BA%83%E5%91%8A%E3%81%A7appsflyer%E9%80%A3%E6%90%BA%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01KB2W28TJVZ1BX94SZYH1K5EM=snapchat%E5%BA%83%E5%91%8A%E3%81%A7appsflyer%E9%80%A3%E6%90%BA%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01KB2W28TJ2R95JK7C1PQE644C=1-set-the-campaign-type-objective-and-goals h_01KB2W28TJ4BK88DVYJG4XYE0S=%E6%B3%A8%E6%84%8F-1 h_01KB2W28TJB1V382HD09M9Y0C3=2-set-destination-url h_01KB2W28TJT7QZ2P7AZ5X61ZXV=%E6%B3%A8%E6%84%8F-2 create-a-landing-page-with-onelink-smart-script=onelink-smart-script%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BD%9C%E6%88%90 h_01KB2W28TJQA1TBXXQ7MA1F0CB=onelink-smart-script%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BD%9C%E6%88%90 h_01KB2W28TJ4J426HD3ZFHXAV4J=endtoend-data-flow h_01KB2W28TJR8S029FJ3Y81MG8Y=set-up-a-smart-script-landing-page h_01KB2W28TJBYHKYNQRMJ4ZGWYD=%E6%B3%A8%E6%84%8F-3 h_01KB2W28TJZMQEDSNVWRZCNXYD=%E6%B3%A8%E6%84%8F-4 h_01KB2W28TJT0TEFB97RXEGDVRM=set-up-a-smart-script-crossplatform-landing-page h_01KB2W28TJ6XWR7GW4SQQAKZH9=%E6%B3%A8%E6%84%8F-5 create-a-landing-page-with-onelink-smart-banners=onelink-smart-banner%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BD%9C%E6%88%90 h_01KB2W28TJM0X7K5Z7M2120MT9=onelink-smart-banner%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BD%9C%E6%88%90 h_01KB2W28TKJZBNFR335SXKY6FC=endtoend-data-flow::b905b9a5 h_01KB2W28TKKA9NTQEC7ZA9E6EA=set-up-a-smart-banners-landing-page h_01KB2W28TKW8B6H4W0R9YJM3ZE=%E6%B3%A8%E6%84%8F-6 h_01KB2W28TKRH3NC73J2JHNSMWD=%E6%B3%A8%E6%84%8F-7 view-webtoapp-attribution-data=web-to-app%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D%E6%96%B9%E6%B3%95 h_01KB2W28TKDAV34JGYJKF2VT43=web-to-app%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D%E6%96%B9%E6%B3%95 view-in-the-dashboard=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E4%B8%8A%E3%81%A7%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E8%A1%A8%E7%A4%BA%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KB2W28TKNWYXJX189EP2HPN2=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E4%B8%8A%E3%81%A7%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E8%A1%A8%E7%A4%BA%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 view-in-raw-data-and-api-reports=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%A8api%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E5%86%85%E3%81%A7%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E8%A1%A8%E7%A4%BA h_01KB2W28TKJ1MAMM00KY3M3S2W=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%A8api%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E5%86%85%E3%81%A7%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E8%A1%A8%E7%A4%BA traits-and-limitations=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E7%B4%84%E4%BA%8B%E9%A0%85 h_01KB2W28TKFY74YBXHD91QP9V0=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E7%B4%84%E4%BA%8B%E9%A0%85" />
