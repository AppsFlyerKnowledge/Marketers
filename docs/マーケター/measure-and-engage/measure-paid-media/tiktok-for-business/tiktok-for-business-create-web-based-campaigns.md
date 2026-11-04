---
title: TikTokにおけるWebキャンペーンの作成・計測
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
  created_at: '2025-10-31T12:09:51Z'
  edited_at: '2026-10-14T09:24:48Z'
  id: 40496161157521
  locale: ja
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/ja/articles/40496161157521
---
> **概要：** TikTok AdsのWebキャンペーンを使用した、TikTok AdsにおけるWebからアプリへのコンバージョン計測について記載しています。

<div id="overview" />

## 概要

AppsFlyerでは、WebキャンペーンにおけるTikTok Ads（`tiktokweb_int`）との連携をサポートしており、TikTokのイベントAPIを使ってキャンペーンのアトリビューション情報とコンバージョンデータへTikTokへレポートすることができます。このデータを、TikTokは広告ターゲティングの最適化、パフォーマンスの計測、カスタムオーディエンスの作成に活用できます。

<div id="important" />

> 🚧 **重要**
>
> 現在、TikTok Webとの連携において、CAPIへのリエンゲージメントCVのポストバック送信はサポートしていません。

<div id="prerequisites" />

### 前提条件

TikTok Webの連携を有効にする前に、[TikTok Ads Manager](https://getstarted.tiktok.com/grow-your-business-gb?lang=en&attr_source=google&attr_source=google&attr_medium=search-br-ad&attr_medium=search-br-ad&attr_adgroup_id=155057567247&attr_adgroup_id=155057567247&attr_term=tiktok%20ads%20manager&attr_term=tiktok%20ads%20manager&no_parent_redirect=1&no_parent_redirect=1&creative=%7BGenZCopy%7D&matchtype=e&gad_source=1&gad_campaignid=20368896948&gbraid=0AAAAACeGRgRdqveOjiUJwxN0-j9g7VjPg&gclid=Cj0KCQjwmYzIBhC6ARIsAHA3IkTKsL0d1xAZLIO_9GIkDDIJR-jZs9jDGVa1hTDbsLzcxZl2j6p7ITcaAhf1EALw_wcB)のビジネスアカウントを所有していることを確認してください。

<div id="how-to-create-a-tiktok-web-ads-campaign" />

### TikTok AdsのWebキャンペーンの作成方法

この記事では、AppsFlyerを使用してモバイルアプリ、PCアプリ、コンソールアプリ向けにTikTok AdsでWebキャンペーンを設定するために必要な手順を記載しています。セットアップには、TikTok AdsとAppsFlyerの連携設定の内容、両プラットフォームでのキャンペーン設定、OneLinkスマートスクリプトまたはOneLinkスマートバナーによるランディングページの作成が含まれます。

設定プロセスには、次の必須手順が含まれます：

* [AppsFlyer管理画面でTikTok Web広告の連携を設定する](#appsflyer上でのtiktok-web-adsの連携設定)（必須）
* [TikTok AdsでAppsFlyerの連携を設定する](#tiktok-ads上におけるappsflyerとの連携設定) (必須)

以下は必要に応じて行う任意の設定項目です：

* <Anchor target="_blank" href="/marketers/ja/docs/meta-ads-create-web-based-campaigns#h_01HZKNS17KPJMP74HQKWY022T2">OneLink Smart Scriptを使用したランディングページの作成</Anchor>（任意）
* [OneLink Smart Bannerを使用したランディングページの作成](#onelink-smart-bannerを使ったランディングページの作成)（任意）

<div id="set-up-tiktok-web-ads-integration-in-appsflyer" />

## AppsFlyer上でのTikTok Web Adsの連携設定

まず、TikTokのWeb連携を有効にし、AppsFlyerがEvents APIへ送信するポストバックの内容を設定してください。

<div id="1-activate-the-tiktok-web-ads-integration" />

<Accordion title="1. TikTok Ads Web連携の有効化">

TikTok Ad Web連携を有効にするには：

1. AppsFlyer管理画面 左メニュー **連携** > **Partner Marketplace** へ移動します。
2. **TikTok Web**（または`tiktokweb_int`）を検索して選択してください。
3. **連携設定**をクリックしてください。**連携設定画面**へ移動してください。
4. **連携**タブにて、**パートナーを有効にする**をオンにしてください。 このトグルは、このパートナーとの連携を続ける限り、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">オン（有効）</Anchor>のままにしておく必要があります。
5. （iOSのみ）**高プライバシー一括設定**をオフに設定してください。
6. **Pixel ID：** Pixel ID を入力してください。TikTok Ads Manager内で作成もしくは取得できます。詳細は<Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">こちら</Anchor>を参照してください。
7. **Access Token：** Access Tokenを入力してください。TikTok Ads Manager内で作成もしくは取得できます。詳細は<Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">これらの指示</Anchor>に従ってください。
8. **ユーザーの個人情報のTikTok Adsでの使用を制限する（CCPA）：** このトグルをオンにすると、<Anchor target="_blank" href="/marketers/ja/docs/send-opendsr-api-requests">CCPAに沿ったデータ保護の遵守</Anchor>が可能になります。

   <div id="note" />

   > 📘 **注意**
   >
   > CCPAのプライバシー規制に準拠することで、カリフォルニア州や米国の他のデータの率扱いに慎重な州にいるTikTok Adsユーザーからのデータが制限されます。


</Accordion>

<div id="2-enable-viewthrough-attribution" />

<Accordion title="2.ビュースルー計測の有効化">

AppsFlyerでは、[Smart Script](#onelink-smart-scriptを使ったランディングページの作成)または[Smart Banner](#onelink-smart-bannerを使ったランディングページの作成)を使用して、TikTok Webキャンペーンの「ビュースルーCV」の計測をサポートしています。つまり、ユーザーが最終的にアプリストアへ遷移するボタンをクリックしなくても、広告表示によって発生したアプリインストールの確率的モデリングでの計測が可能になります。

ユーザーがTikTokのWebキャンペーンをクリックして[Smart Script](#onelink-smart-scriptを使ったランディングページの作成)または[Smart Banner](#onelink-smart-bannerを使ったランディングページの作成)対応のランディングページに到達すれば、AppsFlyerはその後に発生したインストールを計測することが可能です。また、利用可能な場合には、`ttclid` が計測精度を高めるためにTikTokへのポストバックに含まれます。

**TikTok Webでのビュースルー計測を有効にするには：**

1. AppsFlyer管理画面 左メニュー 連携 > **連携済みパートナー** > **TikTok Web Ads**へ移動します。
2. **連携**のタブで、**インストール計測**セクションまでスクロールしてください。
3. **ビュースルーのインストール計測**を有効にしてください。
4. **［任意］** 必要に応じて**クロスプラットフォームの同等アトリビューション優先度**をオンに変更してください。詳細については、 <Anchor target="_blank" href="/marketers/ja/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">クロスプラットフォームのインプレッションに対して同等の優先度を有効にする</Anchor>をご覧ください。
5. **計測リンク**のタブをクリックしてください。
6. **ビュースルー計測**のセクションまでスクロールして、**ビュースルーのルックバック期間**（最大24時間）を設定してください。
7. 設定を適用するには、画面右下の**連携を保存**をクリックしてください。

</Accordion>

<div id="3-set-inapp-event-postbacks" />

<Accordion title="3.アプリ内イベントのポストバック設定">

現在、TikTokへ自動的に送付されるデフォルトポストバックの項目はインストールのみです。その他のアプリ内イベントについては、AppsFlyer イベントをTikTok Adsイベントにマッピングしてカスタム ポストバックを作成することで、TikTok Ads Managerで表示できます。

アプリ内イベントのポストバックを設定するには、次の手順に従ってください：

1. **アプリ内イベントポストバック**を有効にしてください。
2. 必要に応じて、アプリ内イベントのポストバック期間を設定してください（アプリ内イベントのポストバック期間の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#アプリ内イベントポストバック期間">こちらの記事</Anchor>をご確認ください）。
3. **イベントを追加**をクリックして、SDKイベントをリストに追加してください。
4. **AppsFlyer側のSDKイベント名**の列で、ドロップダウンのリストからイベント名を選択してください。（アプリに実装されているSDKまたはS2Sイベントのうち、AppsFlyerが既に受信しているイベント名が表示されます。）
5. **パートナー側のイベント**列で、ドロップダウンボックスから最も適切なパートナーイベントを選択するか、[CUSTOM] を選択します。
6. **送信オプション**の項目で、**このパートナーのみ**を選択すると、このパートナーから発生したユーザーが実行したイベントのみを対象に、アプリ内イベントのポストバックが送信されるようになります。
7. **送信データ**の項目で、収益値を送信するかどうかを選択します。詳細：<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#ポストバックに含めるデータ">ポストバックに含めるデータ</Anchor>

   <div id="note-1" />

   > 📘 **注意**
   >
   > * 購入イベントを設定する場合は、**送信データ**項目は**イベント値と収益を送信**に設定してください。他の選択肢を選んだ場合はポストバックが正しく送付されません。
   > * また、現在収益の値を含めることができるのは購入(Purchase)イベントのみです。

8. ［任意］**条件を追加**アイコンをクリックして、ポストバックする<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">イベントの条件を設定可能です。</Anchor>
9. 最後に、**連携の保存**をクリックして完了です。
10. ［任意］連携設定を保存したあとに、他のアプリのこのパートナーとの連携設定を編集することも可能です：
    1. 左上のパートナー名の下にある、アプリ名をクリックしてアプリ一覧を開いてください。
    2. ドロップダウンリストから別のアプリを選択してください。
    3. 選択したアプリで、連携ステップを再度実施してください。

</Accordion>

<div id="set-up-appsflyer-integration-in-tiktok-ads" />

## TikTok Ads上におけるAppsFlyerとの連携設定

TikTok Ads Manager上で以下の作業を行ってください。

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. キャンペーンの種類、目的、目標の設定">

Appsflyerから送信される任意のアプリ内イベントをキャンペーンの目標として選択するか、アプリのインストールを最適化したい場合は「ダウンロード」を選択できます。

<div id="warning" />

> ❗️ **要注意**
>
> Web-to Appのキャンペーン経由で発生したコンバージョンイベントが、TikTok Events API経由でTikTokへ送信されていることを確認したい場合は、キャンペーンを作成する際、<Anchor target="_blank" href="/marketers/ja/docs/tiktok-for-business-advanced-srn-integration-setup#web-to-app非アプリキャンペーンの計測">こちらに記載されている手順</Anchor>をスキップしてください。設定してしまった場合、TikTokはSRN APIを通じてそれらのコンバージョンの成果を報告してくる可能性があり、レポートや最適化の不整合を引き起こす可能性があります。

</Accordion>

<div id="2-set-destination-url" />

<Accordion title="2.遷移先URLの設定">

1. **遷移先(Destination)** 内にある**WebサイトURL**の項目に広告からの遷移先となるURLを入力してください。なお、入力するURLは次のいずれかである必要があります：
   * **［１］Webランディングページ：** ランディングページは、次のような場合に使用することをお勧めします：
     * 複数のプラットフォームでアプリをリリースしている場合
     * ランディングページを使用して、対象の商品に関する詳細な情報を提供したい場合
     * ランディングページを使用して、より多くのデータを収集したい場合

       上に挙げた例の場合には、[Smart Script](#onelink-smart-scriptを使ったランディングページの作成)または[Smart Banner](#onelink-smart-bannerを使ったランディングページの作成)を実装したランディングページを作成する必要があります。
   * **［２］AppsFlyerの計測リンク：** AppsFlyerの計測リンク（OneLink、シングルプラットフォーム用の計測リンク、クロスプラットフォーム用の計測リンク）は、ランディングページを経由せずに直接ストアに遷移させ、アプリダウンロードを促したい場合にオススメです。
2. **URLパラメーターを作成する**をクリックして、パラメーターをランディングページURL もしくは AppsFlyer計測リンクに対してに追加してください。
3. **カスタムパラメータ**の項目で、**パラメータを追加**をクリックしてください。
4. AppsFlyerのパラメータをTikTokの値にマッピングしてください。マッピングするパラメータは、遷移先URLがランディングページ、AppsFlyerの計測リンク、PC・コンソールのストアかによって異なります。

   <div id="landing-page-or-attribution-link" />

   #### ■ ランディングページまたはAppsFlyerの計測リンクの場合：

   遷移先URLが**ランディングページ、OneLinkの計測リンク、または単一プラットフォームの計測リンク**の場合、次のAppsFlyerのパラメータをTikTokの対応するパラメータにマッピングしてください。

| AppsFlyerパラメータ | TikTokのマップする値 |
| --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#pid">`pid`</Anchor> | `tiktokweb_int` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#c">`c`</Anchor>* | **\_\_campaign\_name\_\_** |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | **\_\_campaign\_id\_\_** |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | **\_\_aid\_name\_\_** |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | **\_\_aid\_\_** |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | **\_\_cid\_name\_\_** |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | **\_\_cid\_\_** |

   * キャンペーン分析を簡素化するために、キャンペーン名の冒頭または末尾にキャンペーンタイプを示す\_webまたは\_mobileを追加してください。（例：campaign-name\_web）

   最終的なURLのサンプルは以下のような形になります：

   ```
   https://app.appsflyer.com/{app_id}?pid=tiktokweb_int&c=__campaign_name__&af_c_id=__campaign_id__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__&af_r={https://Add-your-store-url.com}
   ```

   ※アプリのAPKファイルがGoogle Playストアに公開されていない場合には、 <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_r">`af_r`</Anchor> のパラメータを追加して、ストアのURLを記載してください。（例：`https://Add-your-store-url.com` ）

   <div id="pc-or-console-store" />

   #### ■ PC・コンソールストアの場合：

   遷移先URLが **PC・コンソールストア**の場合は、次の表の指示に従ってリンクを作成してください。詳細については、以下を参照してください： <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-direct-attribution-links">CTV、PC、コンソールプラットフォームのダイレクト計測リンク</Anchor>

| リンクコンポーネント | 値 |
| --- | --- |
| ベースURL | engagements.appsflyer.com/v1.0/c2s/click/app/ |
| 必須のpathパラメータ | ▪ platform：(例) steam  <br />▪ app\_id：(例) 123456 |
| 必須パラメータ | ▪ af\_media\_source  <br />▪ af\_campaign\_id  <br />▪ af\_r |
| その他パラメータ | <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-direct-attribution-links#パラメーター">すべてのパラメータ一覧</Anchor> |
| URL例： | `https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source={media_source}&af_campaign_id={campaign_id}&af_r={app_store_url}` |

   次のAppsFlyerパラメータをTikTokのパラメータにマッピングしてください：

| AppsFlyerパラメータ | TikTokのマップする値 |
| --- | --- |
| `af_media_source` | `tiktokweb_int` |
| `af_campaign` * | **\_\_campaign\_name\_\_** |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_c_id">`af_campaign_id`</Anchor> | **\_\_campaign\_id\_\_** |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | **\_\_aid\_name\_\_** |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | **\_\_aid\_\_** |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | **\_\_cid\_name\_\_** |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | **\_\_cid\_\_** |

   * キャンペーン分析を簡素化するために、キャンペーン名の冒頭または末尾にキャンペーンタイプを示す\_webまたは\_mobileを追加してください。（例：campaign-name\_web）

   クロスプラットフォームURLの例：

   ```
   https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=tiktokweb_int&af_campaign_id=__campaign_id__&af_campaign=__campaign_name__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
   ```

   <div id="note-2" />

   > 📘 **注意**
   >
   > TikTokは、広告がクリックされると遷移先URLに`ttclid={{ttclid}}`を自動的に追加します。


</Accordion>

<div id="note-3" />

<div id="create-a-landing-page-with-onelink-smart-script" />

## OneLink Smart Scriptを使ったランディングページの作成

**ユーザージャーニー：** ユーザーがTikTok広告をクリックすると、Webサイトに遷移します。そのWebサイトには、複数プラットフォームのどれかからアプリをダウンロードするように促すCTAボタンが設置されています。いずれかのCTAボタンをクリックすると、ユーザーは任意のストアへ遷移します。

<div id="endtoend-data-flow" />

<Accordion title="データフロー">

[![](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)

1. TikTokの広告URLには`pid=tiktokweb_int`パラメータが含まれた状態です。ユーザーが広告をクリックすると、`ttclid`のパラメータがクリックURLに自動的に追加されます。
2. ユーザーは、遷移先URL（Smart Scriptを実装したランディングページ）へリダイレクトされます。
3. ランディングページが読み込まれると、Smart Scriptは受信URLパラメーターを含むインプレッションをAppsFlyerへ記録します。このインプレッションの計測により、ランディングページからのビュースルー計測が可能になります。（詳細：<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">インプレッションとビュースルーの計測の詳細について</Anchor>）
4. Smart Scriptは、`ttclid`パラメータが追加されているランディングページURL（受信URL）のパラメータ内容に基づいて、ページ内のストアへの遷移ボタンに設定されているURL（送信URL）を自動生成します。遷移ボタンの遷移先としては、以下の候補があります：
   * OneLink経由でGoogle Play / App Storeへ遷移
   * 複数のプラットフォームストア（CTV、Epic、Steamなど）：この場合、Smart Scriptはプラットフォームごとに単一プラットフォーム用の計測リンクを生成し、指定したプラットフォームのストアへ遷移させます。
   * クリック後にユーザー端末にAPKファイルをダウンロード
5. ユーザーがCTAボタンをクリックすると、クリックがAppsFlyerに記録されます。
6. ユーザーはストアにリダイレクトされ、アプリをダウンロードします。
7. ユーザーがアプリを開くと、AppsFlyerにインストールイベントが登録されます。
8. AppsFlyerは、確率論的モデリングに基づいて、もしくは[インストールリファラー](https://www.appsflyer.com/glossary/install-referrer/)が利用可能な場合には決定論的手法でインストールを計測します。
9. `ttclid` パラメータおよびその他のイベントパラメータを含むポストバックが、Events APIを介して生成され、TikTokへ送信されます。TikTokは、この `ttclid` のパラメータを使用して個々のクリックを判別し、他の各種パラメータはキャンペーンの最適化に役立ちます。

</Accordion>

<div id="set-up-a-smart-script-landing-page" />

<Accordion title="ランディングページへのSmart Scriptの実装">

Smart Scriptを使用してTikTok Adsのキャンペーンを設定するには、以下の手順に沿ってください：

1. キャンペーンのOneLink計測リンク用に、OneLinkテンプレートを設定してください。詳細は<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレートの作成方法</Anchor>をご覧ください。
2. Smart Scriptのコードを作成してください。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink Smart Scriptの作成方法</Anchor>をご覧ください。

   <div id="note-6" />

   > 📘 **注意**
   >
   > 以下の手順では、Smart Scriptを使用してTikTokの広告キャンペーンを設定するために必要な手順だけに特化しています。Smart Scriptを使ったキャンペーンの設定方法に関する包括的なガイドについては、<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink Smart Script V2の設定</Anchor>ページ内の<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink Smart Scriptの作成方法</Anchor>のセクションを参照してください。

3. 関連するURLパラメータがすべてランディングページのURL（受信URL）に追加されていることを確認してください。受信URLに追加されたパラメーターを確認するには、TikTokの広告マネージャを開き、遷移先URLの作成時に設定したURLパラメーターを確認してください。詳細は、[遷移先URLの設定](#2-set-destination-url)をご覧ください。
4. TikTok Adsキャンペーンに必要な受信URLパラメーターを、ユーザーがCTAボタンをクリックしたときにAppsFlyerに送信される、送信URLパラメーターにマッピングしてください。
   * **PID：** Smart Scriptが `pid=tiktokweb_int`のパラメータ値を受信URLから取得し、送信URLの対応するパラメータへマッピングします。
   * **TTCLID**:`ttclid` パラメータは、アプリ内イベントのポストバックをTikTokへ正しく送信するために必須です。`ttclid` パラメータは、**Smart Script**のページで、**URLパラメータのマッピング**を行う際に手動で追加する必要があるので注意してください：

     1. **マッピング：** 項目で、**カスタムパラメータ**を選択してください。
     2. **送信URLパラメーター**と**受信URLパラメーター**に**ttclid**を入力してください。

     <div id="note-4" />

     > 📘 **注意**
     >
     > AppsFlyerのローデータレポートのカラムに表示するには、受信URLの `ttclid` パラメータを（送信URLの`ttclid` パラメータに追加で）送信URLパラメータの `af_sub[1-5]` のいずれかにもマッピングする必要があります。


</Accordion>

<div id="set-up-a-smart-script-crossplatform-landing-page" />

<Accordion title="クロスプラットフォーム向けランディングページでのSmart Scriptの実装">

TikTok Adsのキャンペーン向けにSmart Scriptをクロスプラットフォームのランディングページに設定するには、次の手順に沿ってください：

1. キャンペーンのOneLink計測リンク用に、OneLinkテンプレートを設定してください。詳細は<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレートの作成方法</Anchor>をご覧ください。
   * OneLinkテンプレートでクロスプラットフォーム計測を有効にしてください。（<Anchor target="_blank" href="/marketers/ja/docs/set-up-cross-platform-links-for-multi-device-campaigns#クロスプラットフォーム計測用のonelinkテンプレートの作成">詳細</Anchor>）
2. 関連するURLパラメータがすべてランディングページのURL（受信URL）に追加されていることを確認してください。受信URLに追加されたパラメータを確認するには、TikTok Ads Managerを開き、遷移先URLの作成時に設定したURLパラメータを確認してください。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-create-web-based-campaigns#h_01HZKNS17KT8TRD2TGDBRGKBZ3">遷移先URLの設定</Anchor>をご覧ください。
3. 各受信URLパラメータに対して、マッピングする送信URLパラメータを決定してください。たとえば、受信URLの`af_site_id`パラメータを、送信URLの`af_site_id`パラメータにマッピングするといった形です。
4. 空の値を渡すことができない必須の［送信パラメータ］については、デフォルト値を決定してください。
5. 開発者に次の情報を共有してください：
   * ［受信パラメータ］と［送信パラメータ］のマッピング一覧：開発者は、受信/送信パラメータのマッピング一覧に基づいて、送信URLを生成するスクリプトを作成する必要があります。
   * 各パラメータのデフォルト値：スクリプトは、対応する受信URLパラメータの値がない場合に、送信URLパラメータにデフォルト値を挿入します。
   * OneLink計測リンクを使用している場合は、そのドメインとテンプレートIDを開発者に共有してください。開発者はこれを使用して、送信用のOneLink URLを作成します。（例： `yourbrand.onelink.me/A1b2`｜ブランドドメインの場合： `click.yourbrand.com/A1b2`）
   * 開発者に以下の Dev Hubリンクを共有してください：
     * [モバイルアプリ以外のプラットフォームへの送信URLの作成方法とコードサンプル](https://dev.appsflyer.com/hc/docs/create-direct-click-url)
     * [クロスプラットフォーム向けのランディングページを作成するためのデモと手順](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/)

* 送信URLに、受信パラメータ `ttclid` を含めるよう、開発者に忘れずに依頼してください。

  <div id="note-5" />

  > 📘 **注意**
  >
  > AppsFlyerのローデータレポートのカラムに表示するには、受信URLの `ttclid` パラメータを（送信URLの`ttclid` パラメータに追加で）送信URLパラメータの `af_sub[1-5]` のいずれかにもマッピングする必要があります。


</Accordion>

<div id="create-a-landing-page-with-onelink-smart-banners" />

## OneLink Smart Bannerを使ったランディングページの作成

**ユーザージャーニー：** ユーザーがTikTok広告をクリックすると、Webサイトに遷移します。ページにアクセスすると、Smart BannerとアプリストアからアプリをダウンロードするためのCTAボタンが表示されます。

<div id="endtoend-data-flow::e62b5c1b" />

<Accordion title="データフロー">

1. TikTokの広告URLには`pid=tiktokweb_int`パラメータが含まれた状態です。ユーザーが広告をクリックすると、`ttclid`のパラメータがクリックURLに自動的に追加されます。
2. ユーザーが、遷移先URL（Smart Bannerを実装したランディングページ）にリダイレクトされます。
3. ランディングページが読み込まれると、Smart BannerからAppsFlyerへ、受信URLパラメータを含んだ状態で<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">インプレッション</Anchor>のイベントが送信されます。このインプレッションの計測を行うことで、ランディングページでのビュースルー計測が可能になります。（詳細：<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">インプレッションとビュースルーの計測の詳細について</Anchor>）
4. Smart Bannerは、バナーのCTAボタンの送信URLを生成します。送信URLは、`ttclid` パラメータを含む受信URLパラメータに基づいて生成されます。Smart Bannerでは、OneLinkベースのリンクのみを生成できます。
5. ユーザーがSmart BannerのCTAボタンをクリックすると、AppsFlyerにもクリックが計測されます。
6. ユーザーはストアにリダイレクトされ、アプリをダウンロードします。
7. ユーザーがアプリを開くと、AppsFlyerにインストールイベントが登録されます。
8. AppsFlyerは、確率論的モデリングに基づいて、またはインストールリファラーが利用可能な場合は決定論的手法でインストールを計測します。
9. `ttclid`パラメータと他のイベントパラメータを含むポストバックが生成され、Events APIを介してTikTokに送信されます。TikTokは、この `ttclid` のパラメータを使用して個々のクリックを判別し、他の各種パラメータはキャンペーンの最適化に役立ちます。

</Accordion>

<div id="set-up-a-smart-banners-landing-page" />

<Accordion title="ランディングページへのSmart Bannerの実装">

Smart BannerをTikTok Adsキャンペーンを設定するには、以下の手順に従ってください：

1. キャンペーンのOneLink計測リンク用に、OneLinkテンプレートを設定してください。詳細は<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレートの作成方法</Anchor>をご覧ください。
2. Smart Bannerを作成してください。

   > 📘 **注意**
   >
   > 以下の手順では、Smart Bannerを使用してTikTokの広告キャンペーンを設定するために必要な手順だけに特化しています。Smart Bannerの設定方法に関する包括的なガイドについては、<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banner（マーケター向け）</Anchor>の<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers#設定">設定セクション</Anchor>をご覧ください。

3. TikTok Adsキャンペーン向けにSmart Bannerのパラメータを設定してください。
   * 関連するURLパラメータがすべてランディングページ内のURL（受信URL）に追加されていることを確認してください。最も重要なのは、受信URLにおいて `pid=tiktokweb_int` と `ttclid` が含まれており、Smart Bannerがそれらを収集可能な状態にあることです。これら2つのパラメータは、計測とTikTokへのポストバックの送信に必要です。受信URLに追加されるパラメータを確認するには、TikTok Ads Managerを開いて、遷移先URLの作成時に設定したURLパラメータを確認してください。 参照：<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-create-web-based-campaigns#h_01HZKNS17KT8TRD2TGDBRGKBZ3">遷移先URLの設定</Anchor>

</Accordion>

<div id="view-web-to-app-attribution-data" />

## Web to Appの計測データの確認方法

Webキャンペーンの各種イベントは、元々の`tiktokweb_int`のPIDでTikTokへ送信されますが、AppsFlyerの管理画面上およびローデータレポートでは`tiktokglobal_int`のPIDの下に記録されます。この仕様は、主要なコンバージョンイベントとコンバージョンアシストイベントの両方に適用されます。

この統一されたレポートビューにより、Webとアプリのキャンペーンパフォーマンスを、包括的なWebとモバイルのコスト情報を含んだ状態で分析できるようになります。

<div id="view-in-the-dashboard" />

### 管理画面上でのデータ表示について

すべてのTikTokのWeb-to-Appキャンペーンの計測データは、オーバービューとアクティビティダッシュボードにおいて`tiktokglobal_int`の下に紐づく形で表示されます。これにより、プラットフォーム全体でのキャンペーンの結果を確認できるようになります。標準フィルタとブレークダウンを使用して、TikTok AdsのデータにおけるアプリとWebのトラフィックを比較してください。

<div id="note-7" />

<div id="measure-cost-clicks-and-impressions" />

<div id="view-in-raw-data-and-api-reports" />

### ローデータとAPIレポート内でのデータ表示

ローデータエクスポートとAPIレスポンスでは、`media_source`のカラムにおける`tiktokglobal_int`のPIDのデータに、TikTokのWebキャンペーンのデータも含まれます。Webキャンペーンの詳細を確認するには、Webキャンペーン作成中に使用した`tiktokweb_int` PIDを示している`original_url`のカラムを参照してください。

## 特性と制約事項

| 特性 | 備考 |
| --- | --- |
| コストデータ | TikTok Ads (`tiktokweb_int`) のWebキャンペーンのコストデータは、自動取得されません。代わりに、<Anchor target="_blank" href="/marketers/ja/docs/import-cost-data#procedures">メールでのファイルアップロード、もしくはAppsFlyerの管理画面上で手動アップロード</Anchor>のいずれかを使用して、手動でコストをインポートする必要があります。これは、ROI360のご契約者されている場合でも同様です。 |
| クリック数とインプレッション（一時的な制限） | ウェブキャンペーンのクリック数とインプレッションは、TikTok SRN (`tiktokglobal_int`) から一時的に利用できません。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01K8X2TS8CYRY1XVQNEABWHVF4=%E6%A6%82%E8%A6%81 h_01K8X2TS8C356J1VSAG70EB8HF=%E9%87%8D%E8%A6%81 prerequisites=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01K8X2TS8CEFSS92A9MRE7MQD1=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 how-to-create-a-tiktok-web-ads-campaign=tiktok-ads%E3%81%AEweb%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E4%BD%9C%E6%88%90%E6%96%B9%E6%B3%95 h_01K8X2TS8CXP0R5WQN14W8S8G3=tiktok-ads%E3%81%AEweb%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E4%BD%9C%E6%88%90%E6%96%B9%E6%B3%95 set-up-tiktok-web-ads-integration-in-appsflyer=appsflyer%E4%B8%8A%E3%81%A7%E3%81%AEtiktok-web-ads%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01K8X2TS8CQDNNX59WDW38V24X=appsflyer%E4%B8%8A%E3%81%A7%E3%81%AEtiktok-web-ads%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01K8X2TS8CYNWESDXCCFCE4TTA=1-activate-the-tiktok-web-ads-integration h_01K8X2TS8C4HNWR2Z3MTMKQ92Q=%E6%B3%A8%E6%84%8F h_01K8X2TS8C3RDCEX0R8HJGCARH=2-enable-viewthrough-attribution h_01K8X2TS8CP915Y7C5WSEYAJQV=3-set-inapp-event-postbacks h_01K8X2TS8CYD41E31EJ0ES76HP=%E6%B3%A8%E6%84%8F-1 set-up-appsflyer-integration-in-tiktok-ads=tiktok-ads%E4%B8%8A%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8Bappsflyer%E3%81%A8%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01K8X2TS8CNQEQCB9SBVESBJ9H=tiktok-ads%E4%B8%8A%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8Bappsflyer%E3%81%A8%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01K8X2TS8CZCGK55A71SVDRFXJ=1-set-the-campaign-type-objective-and-goals h_01K8X2TS8C8AFR6M3ME0SPP4QN=%E8%A6%81%E6%B3%A8%E6%84%8F h_01K8X2TS8CC4ZTST3Y5Q2RRVTC=2-set-destination-url landing-page-or-attribution-link=-%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%BE%E3%81%9F%E3%81%AFappsflyer%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E5%A0%B4%E5%90%88 h_01K8X5E9VSFTD53NCA03KYT80P=-%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%BE%E3%81%9F%E3%81%AFappsflyer%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E5%A0%B4%E5%90%88 pc-or-console-store=-pc%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB%E3%82%B9%E3%83%88%E3%82%A2%E3%81%AE%E5%A0%B4%E5%90%88 h_01K8X5XC69TDW2DNFWFYRN9TMF=-pc%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB%E3%82%B9%E3%83%88%E3%82%A2%E3%81%AE%E5%A0%B4%E5%90%88 h_01K8X2TS8DQ70RSFHBGM7ZHRYE=%E6%B3%A8%E6%84%8F-2 create-a-landing-page-with-onelink-smart-script=onelink-smart-script%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BD%9C%E6%88%90 h_01K8X2TS8DZ62VHY2W7SCBSWEN=onelink-smart-script%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BD%9C%E6%88%90 h_01K8X2TS8D7X7YT9FBDPZPVAH3=endtoend-data-flow h_01K8X2TS8DJ54M3H11PTXVE2JF=set-up-a-smart-script-landing-page h_01K8X2TS8DFS70S7YNA89R6N95=%E6%B3%A8%E6%84%8F-3 h_01K8X2TS8DZT5GG7BW41A3FA4B=%E6%B3%A8%E6%84%8F-5 h_01K8X2TS8DMTGJNQX3B3VXAM0W=set-up-a-smart-script-crossplatform-landing-page h_01K8X2TS8DZEY18AMT5J14VW42=%E6%B3%A8%E6%84%8F-5 create-a-landing-page-with-onelink-smart-banners=onelink-smart-banner%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BD%9C%E6%88%90 h_01K8X2TS8DAAN8JGJNJGJKD6PP=onelink-smart-banner%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BD%9C%E6%88%90 h_01K8X2TS8DC94419514NK8Y98S=endtoend-data-flow::e62b5c1b h_01K8X2TS8E5EHDFX6RW34TQN4A=set-up-a-smart-banners-landing-page h_01K8X2TS8EC16VZXC9JZJ9Y3VG=%E6%B3%A8%E6%84%8F-6 TikTok-view=web-to-app%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D%E6%96%B9%E6%B3%95 view-webtoapp-attribution-data-from-november-2-2025=web-to-app%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D%E6%96%B9%E6%B3%95 h_01K88J8JFNEYBZNR18133NMRP9=web-to-app%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D%E6%96%B9%E6%B3%95 view-in-the-dashboard=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E4%B8%8A%E3%81%A7%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E8%A1%A8%E7%A4%BA%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01K88J8JFNMHCVZ0C34E3D7AST=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E4%B8%8A%E3%81%A7%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E8%A1%A8%E7%A4%BA%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 view-in-raw-data-and-api-reports=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%A8api%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E5%86%85%E3%81%A7%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E8%A1%A8%E7%A4%BA h_01K88J8JFN8W2572N92466YFZQ=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%A8api%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E5%86%85%E3%81%A7%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E8%A1%A8%E7%A4%BA traits-and-limitations=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E7%B4%84%E4%BA%8B%E9%A0%85 h_01K8X2TS8E2S90VKP7GS7KHW4C=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E7%B4%84%E4%BA%8B%E9%A0%85" />
