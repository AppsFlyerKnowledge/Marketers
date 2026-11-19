---
title: Meta広告｜Webキャンペーンの作成
metadata:
  keywords:
    - マーケター
    - モバイルアトリビューション
x-zendesk:
  category: マーケター
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - マーケター
    - モバイルアトリビューション
  created_at: '2024-06-04T16:08:28Z'
  edited_at: '2026-09-15T10:56:07Z'
  id: 25646834966033
  locale: ja
  section: Meta広告
  section_id: 6551109855761
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/25646834966033-Meta-Ads-Create-web-based-campaigns
---
> **概要：** Meta広告のWebキャンペーンを使用して、Meta広告経由のWebからアプリへのコンバージョンを計測します

<div id="overview" />

## まずはじめに

AppsFlyerは、ユーザー獲得を目的とするWebキャンペーン向けに、Meta広告（`metaweb_int`）との連携をサポートしています。MetaのコンバージョンAPI（CAPI）を通じて、アトリビューションデータとコンバージョンデータを直接報告できます。このデータは、Metaが広告ターゲティングの最適化、パフォーマンスの測定、カスタムオーディエンスの構築に活用できます。

<div id="note" />

> 📘 **注意**
>
> 現在、Meta Webとの連携において、CAPIへのリエンゲージメントCVポストバックの送信をサポートしていません。

<div id="prerequisites" />

### 前提条件

Meta広告との連携を有効にする前に、[Meta Business Managerのビジネスアカウント](https://www.facebook.com/business/help/1710077379203657?id=180505742745347)をお持ちであることを確認してください。

<div id="how-to-create-a-meta-web-ads-campaign" />

### Metaウェブキャンペーンの作成方法について

この記事では、AppsFlyerを使用してモバイルアプリ、PCアプリ、コンソールアプリ向けにMeta広告でWebキャンペーンを設定するための情報と手順を紹介します。セットアップには、Meta AdsとAppsFlyerの連携設定の内容、両プラットフォームでのキャンペーン設定、OneLinkスマートスクリプトまたはOneLinkスマートバナーによるランディングページの作成が含まれます。  
設定プロセスには、次の必須手順が含まれます：

- [AppsFlyerでMeta Web広告連携を設定](#set-up-meta-web-ads-integration-in-appsflyer)（必須）
- [Meta広告でAppsFlyer連携を設定](#set-up-appsflyer-integration-in-meta-ads)（必須）

以下は必要に応じて行う任意の設定項目です：

- [OneLink Smart Scriptを使用してランディングページを作成](#create-a-landing-page-with-onelink-smart-script)（任意）
- [OneLink Smart Bannersを使用してランディングページを作成](#create-a-landing-page-with-onelink-smart-banners)（任意）

<div id="set-up-meta-web-ads-integration-in-appsflyer" />

## AppsFlyerでMeta Web広告連携を設定

まず、Meta Ads連携を有効にし、AppsFlyerがCAPI経由で送信するポストバックを設定します。

<div id="a-activate-the-meta-ads-integration" />

<Accordion title="1. Activate the Meta Web Ads integration">

Meta Web Adsの連携を有効にするには：

1. AppsFlyerのサイドメニューから、**連携** > **パートナー連携** > **パートナーマーケットプレイス**に移動します。
2. **Meta Web**を検索し、選択します。設定ページが表示されます。
3. **連携**タブで、**パートナーを有効にする**をオンにします。\*\*注意：\*\*パートナーを利用している間は、トグルをオン（<Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">有効</Anchor>）にしておく必要があります。
4. （iOSアプリとの連携を設定する場合は、**高プライバシー一括設定**をオフにします。）。
5. \*\*詳細マッチングデータの共有：\*\*オンにすると、AppsFlyerに送信されるイベント情報に、ハッシュ化されたメールアドレス、電話番号、名、姓、FacebookログインIDなどの詳細マッチング用の項目が含まれる場合、それらの項目がMetaと共有されます。詳しくは、<Anchor target="_blank" href="/marketers/docs/advanced-matching-data-sharing">詳細マッチングデータの共有</Anchor>を参照してください。
6. **Pixel ID**の項目を入力します。ピクセルIDは、Meta広告マネージャー画面から取得できます：
   1. <span class="af-ol-a"></span>[広告マネージャー](https://www.facebook.com/ads/manager) のサイドメニューから、下にスクロールして **すべてのツール** > **イベントマネージャー** に移動します。**注意：** 右上のドロップダウンで、対象のビジネスが選択されていることを確認してください。
   2. **イベントマネージャー** のサイドメニューから、 **データソース** を選択します。ピクセルのリストが表示されます。選択したビジネスのピクセルがない場合は、同じ画面から作成できます。
   3. ピクセル名の下に表示されているピクセルIDをコピーします。  
      そして、AppsFlyerの  
      **Pixel ID** フィールドに貼り付けます。
7. **アクセストークン**欄に入力します。アクセストークンを取得するには、 [こちらの手順](https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token)に従ってください
8. <Anchor target="_blank" href="/marketers/docs/send-opendsr-api-requests">データ保護法</Anchor>に対応するには、**Meta広告によるユーザーの個人情報の利用を制限（CCPA）** をオンにします。**注意：** CCPAのプライバシー規制に対応すると、カリフォルニア州のMeta広告ユーザーから取得するデータが制限されます。

</Accordion>

<div id="d-enable-view-through-attribution-for-meta-web" />

<Accordion title="2. Enable view-through attribution">

AppsFlyerは、[Smart Script](#set-up-smart-script-crossplatform-landing-page)または[Smart Banner](#set-up-smart-banners-landing-page)を導入したランディングページを使用するMeta Webキャンペーンのビュースルーアトリビューションをサポートしています。これにより、ユーザーが広告を直接クリックしなくても、広告表示をきっかけに発生したアプリインストールを、確率論的モデリング（PMOD）で計測できます。

ユーザーがMeta Web広告をクリックして[Smart Script](#set-up-smart-script-crossplatform-landing-page)または[Smart Banner](#set-up-smart-banners-landing-page)を導入したランディングページに到達すると、AppsFlyerはその後のアプリインストールをアトリビューションできます。 `fbclid`を取得できる場合は、Metaへのポストバックに含めることで、アトリビューションの精度を高めます。

**Meta Webのビュースルーアトリビューションを有効にするには、以下の手順に従ってください。**

1. AppsFlyerのサイドメニューから、**連携** > **パートナー連携 > アクティブな連携** > **Meta Web広告**を開きます。
2. **連携**タブで、**インストールアトリビューション**セクションまでスクロールします。
3. **インストールのビュースルーアトリビューション**をオンにします。
4. **［任意］** **クロスプラットフォームの同等アトリビューション優先度**をオンにし、ルックバック期間を設定します。詳細は、<Anchor target="_blank" href="/marketers/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">クロスプラットフォームのインプレッションに同等の優先度を設定する方法</Anchor>を参照してください。
5. **アトリビューションリンク**タブを開きます。
6. **ビュースルーアトリビューション**セクションまでスクロールし、**ビュースルーのルックバック期間**（最大24時間）を設定します。
7. 設定を適用するには、**連携を保存**をクリックしてください。

</Accordion>

<div id="b-set-inapp-event-postbacks" />

<Accordion title="3. Set in-app event postbacks">

現在、Meta Adsへのデフォルトのポストバックを自動的にトリガーするイベントはインストールのみです。その他の種類のイベントについては、AppsFlyerのイベントをMeta広告のイベントにマッピングして、カスタムポストバックを作成できます。Meta広告のイベントは [Metaイベントマネージャ](https://www.facebook.com/business/help/1541268312717919?id=818859032317965)で確認できます。  
アプリ内イベントのポストバックを設定するには、次の手順に従ってください：

1.  **アプリ内イベントポストバック**を有効にしてください。
2. 必要に応じて、 アプリ内イベントのポストバック期間を設定します（設定の詳細は、 <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#in-app-event-postback-window">こちらの記事</Anchor>を参照してください）。
3.  **イベントを追加** をクリックして、イベントをリストに追加してください。
4. **AppsFlyerイベント**列で、ドロップダウンリストからイベント名を選択してください。 AppsFlyerは、アプリに実装されているSDK、またはサーバー間（S2S）イベントからイベント名を受信します。
5. **パートナーイベントへのマッピング**列で、ドロップダウンリストから最も適切な定義済みのパートナーイベントを選択するか、**カスタム**を選択します。
6. **対象ユーザー**列で、イベントの送信オプションを選択してください：
   - **このパートナーのみ**：このイベントがMeta広告にアトリビューションされた場合にのみ、ポストバックを送信します。
   - **オーガニックを含むすべてのメディアソース**：すべてのパートナーに紐づくイベントとオーガニックイベントのポストバックを送信します。
7. **送信データ**列で、イベントの収益値を送信するかどうかを選択します。<Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#data-to-include-in-the-postbacks">ポストバックに含めるデータ</Anchor>を参照してください。

   <div id="note-1" />

   > 📘 **注意**
   >
   > 購入イベントを設定する場合は、**送信データ**列を**値と収益**に設定します。他のオプションを選択した場合はポストバックに失敗します。

8. ［任意］ **条件を追加** icon をクリックして、 <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks">条件を設定</Anchor> します。
9.  **連携を保存**をクリックします。
10. ［任意］連携設定を保存したあとも、設定ページから他のアプリをこのパートナーと連携できます：
    1. <span class="af-ol-a"></span>左上のパートナー名の下にあるアプリ名をクリックし、アプリ一覧を開きます。
    2. ドロップダウンリストから別のアプリを選択します。
    3. 選択したアプリで、連携ステップを再度実施してください。

<div id="note-2" />

> 📘 **注意**
>
> `metaweb_int`にS2Sイベントを送信する場合、S2Sペイロードには`ua`（ユーザーエージェント）と`ip`（IPアドレス）のパラメーターを必ず含めてください。これらの値は、Meta CAPIによるキャンペーン最適化に必要です。 SDKイベントの場合、AppsFlyerが自動的にこれらの値を含めます。 S2Sイベントの場合は、広告主が明示的に送信する必要があります。<Anchor target="_blank" href="/marketers/docs/server-to-server-events-api-for-mobile-s2s-mobile">モバイル向けサーバー間イベントAPI</Anchor>を参照してください。

</Accordion>

<div id="set-up-appsflyer-integration-in-meta-ads" />

## Meta AdsでAppsFlyerの連携を設定する

Meta広告マネージャで次の手順を実行します。

<div id="a-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Set the campaign type, objective, and goals">

1. Meta Adsにログインし、キャンペーンを作成します。
2. **キャンペーンの目的**で、次のいずれかを選択します。 [![](https://files.readme.io/a0cdd42ddf3bc69106de5137e5c842468178bd1dcd76805ea77ead750ba1e9bb-25646834955921.png)](https://files.readme.io/a0cdd42ddf3bc69106de5137e5c842468178bd1dcd76805ea77ead750ba1e9bb-25646834955921.png)
   - **売上**：これにより、Metaは特定のイベント（メインKPI）に最適化します。
   - **トラフィック**：広告クリックに向けてMetaが最適化します。他にKPIがない場合、または他のKPIイベントの件数が少なすぎる場合にのみ使用してください。
3. [オプション] 上記の選択肢にカスタム目標を追加する場合は、次の手順を実行します：
   1. <span class="af-ol-a"></span>Meta広告で、キャンペーンの目的に設定するカスタムイベントを選択し、コンバージョンアクションとして指定します。
   2. AppsFlyerの**Meta Web連携**ページの**アプリ内イベントポストバック**で、AppsFlyerイベントをカスタムパートナーイベントにマッピングし（**パートナーイベントにマッピング**列）、Meta Adsのコンバージョンアクションと同じ名前を付けます。

      <div id="note-3" />

      > 📘 **注意**
      >
      > Metaキャンペーンの目的について、詳しくは[Metaのドキュメント](https://www.facebook.com/business/help/175683976191028)をご覧ください。

4. **コンバージョンロケーション**で**ウェブサイト**を選択します。 [![](https://files.readme.io/32e4dcb4ced7e2011728ed709069b78cffffc4090f09a33c729a2b2e7e882e8b-25646834954257.png)](https://files.readme.io/32e4dcb4ced7e2011728ed709069b78cffffc4090f09a33c729a2b2e7e882e8b-25646834954257.png)
5. ［ピクセル］には、AppsFlyerのパートナーマーケットプレイスで`metaweb_int`に入力したものと同じピクセルIDを指定します。 Metaピクセルの詳細は、[Metaのドキュメント](https://www.facebook.com/business/help/742478679120153)をご覧ください（ログインが必要です）。
6. **次へ**をクリックします。

</Accordion>

<div id="b-set-destination-url" />

<Accordion title="2. Set destination URL">

1. **遷移先**の**WebサイトのURL**欄に、広告の遷移先となるURLを入力します。なお、入力するURLは次のいずれかである必要があります：

   <Image align="center" alt="" src="https://files.readme.io/aec9109f2f3000f669799093460e70198de1934e483314b6cd7f95d8209f361d-25646834955537.png" />

   - \*\*Webランディングページ：\*\*以下の場合は、ランディングページの使用を推奨します。

     - 複数のプラットフォームでアプリをリリースしている場合。
     - ランディングページを使用して、対象の商品に関する詳細な情報を提供したい場合。
     - ランディングページを使用して、より多くのデータを収集したい場合。

     いずれの場合も、[Smart Scriptを使用したランディングページ](#create-a-landing-page-with-onelink-smart-script)または[Smart Bannerを使用したランディングページ](#create-a-landing-page-with-onelink-smart-banners)を作成してください。
   - **AF計測リンク：** ランディングページを経由せず、ユーザーをストアに直接リダイレクトしてアプリをダウンロードさせたい場合は、AF計測リンク（OneLink、単一プラットフォーム、クロスプラットフォーム）の使用を推奨します。

     <div id="important" />

     > 🚧 **重要!**
     >
     > AppsFlyer計測リンクを使用すると、エラーが発生する場合があります。このような場合は、Metaの担当者に解決策を依頼するか、リンク先URLとしてWebランディングページを使用してください。

2. **URLパラメーターを作成する**をクリックして、URL（ランディングページのURLまたはAFアトリビューションリンク）にURLパラメーターを追加します。
3. **カスタムパラメーター**で、**パラメーターを追加**をクリックします

   <Image align="center" alt="4.png" src="https://files.readme.io/bbce415e16d3442f8959bf7a0c23825035d7d4740d5bf3570306c3684c8764d4-25722672143633.png" />
4. AppsFlyerのパラメーターをMetaの値にマッピングします。

   - リンク先URLが**ランディングページ、OneLinkアトリビューションリンク、または単一プラットフォームアトリビューションリンク**の場合、次のAFパラメーターをMetaの対応するパラメーターにマッピングします：

| AppsFlyerパラメータ                                                                                                        | マッピングされたMetaの値         |
| --------------------------------------------------------------------------------------------------------------------- | ---------------------- |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#pid">`pid`</Anchor>                 | `metaweb_int`          |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#c">`c`</Anchor>                     | `{{campaign.name}}`    |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor>     | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor>         | `{{campaign.id}}`      |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor>       | `{{adset.name}}`       |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}`         |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor>             | `{{ad.name}}`          |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor>       | `{{ad.id}}`            |

     生成されるURLの例は次のとおりです:
    
     ```http
     https://app.appsflyer.com/{app_id}?pid=metaweb_int&c={{campaign.name}}&af_siteid={{site_source_name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r={https://Add-your-store-url.com}
     ```
    
     * アプリのAPKがGoogle Playストアでホストされていない場合は、<Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_r">`af_r`</Anchor>パラメーターを追加し、ストアURL（例: `https://Add-your-store-url.com`）を設定します
- リンク先URLが**PCまたはコンソールストア**の場合は、次の表の指示に従ってリンクを作成します。詳細は、<Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-platform-direct-attribution-links">CTV、PC、コンソールプラットフォームの直接計測リンク</Anchor>を参照してください

<table><thead><tr><th colspan="2">アトリビューションリンク構造</th></tr></thead><tbody><tr><td>ベースURL</td><td>engagements.appsflyer.com/v1.0/c2s/click/app/</td></tr><tr><td>必須のpathパラメーター</td><td><ul><li>platform<br/>例：steam</li><li>app_id<br/>例：123456</li></ul></td></tr><tr><td>必須のクエリパラメーター</td><td><ul><li>af_media_source</li><li>af_campaign_id</li><li>af_r</li></ul></td></tr><tr><td>その他のパラメーター</td><td><a href="./ctv-pc-and-console-platform-direct-attribution-links#parameters" target="_blank">すべてのパラメータを見る</a></td></tr><tr><td>URL例</td><td><code>https://engagements.appsflyer.com/v1.0/c2s/click/app/`{platform}/{app_id}?af_media_source={media_source}&amp;af_campaign_id={campaign_id}&amp;af_r={app_store_url}`</code></td></tr></tbody></table>

     以下のAppsFlyerパラメーターを、対応するMetaの値にマッピングします。

| AppsFlyerパラメータ                                                                                                        | マッピングされたMetaの値         |
| --------------------------------------------------------------------------------------------------------------------- | ---------------------- |
| `af_media_source`                                                                                                     | `metaweb_int`          |
| `af_campaign`                                                                                                         | `{{campaign.name}}`    |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor>     | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_c_id">`af_campaign_id`</Anchor>  | `{{campaign.id}}`      |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor>       | `{{adset.name}}`       |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}`         |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor>             | `{{ad.name}}`          |
| <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor>       | `{{ad.id}}`            |

     クロスプラットフォームURLの例：
    
     ```http
     https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
     ```

<div id="note-4" />

> 📘 **注意**
>
> Metaは、広告がクリックされると、遷移先URLに `fbclid={{fbclid}}`を自動的に追加します

<div id="tip" />

> 👍 **ヒント**
>
> キャンペーンを分析しやすくするため、キャンペーン名の先頭または末尾に種類（Webまたはモバイル）をプレフィックスまたはサフィックスとして含めてください (e.g., campaign-name\_web)

<div id="note-5" />

> 📘 **注意**
>
> AFリンクのパラメーターについて詳しくは、<Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#attribution-link-parameters">アトリビューション リンク パラメーター</Anchor>を参照してください。

</Accordion>

<div id="c-select-tracked-events" />

<Accordion title="3. Select tracked events">

［トラッキング］セクションで、広告で促進するコンバージョンイベントを選択します（イベントの設定は[イベントマネージャー](https://www.facebook.com/business/help/898185560232180?id=1205376682832142)で行います）。

<Image align="center" alt="" src="https://files.readme.io/75b6136fdf3fd9790e39aeec735ccd2e1ff0b8a5f302c85f0ed3b05926fcc435-25646834958481.png" />

<div id="important-1" />

> 🚧 **重要!**
>
> **アプリイベント**を選択しないでください。選択すると、MetaがSRN APIを使用してこれらのコンバージョンを自社の成果として計上し、レポートと最適化の結果にずれが生じる可能性があります。

</Accordion>

<div id="create-a-landing-page-with-onelink-smart-script" />

## OneLink スマートスクリプトを使ったランディングページの作成

\*\*ユーザージャーニー：\*\*ユーザーがMeta広告をクリックすると、モバイルWebサイトに移動します。移動先のページには、1つ以上のプラットフォームからアプリをダウンロードするよう促すCTAボタンがあります。ボタンをクリックすると、ユーザーはストアに遷移します。

<div id="end-to-end-data-flow" />

<Accordion title="End-to-end data flow">

<Image align="center" alt="" src="https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png" />

1. Meta広告のURLには、`pid=metaweb_int`パラメーターが含まれます。ユーザーが広告をクリックすると、クリックしたURLに`fbclid`パラメーターが自動的に追加されます。
2. ユーザーは、URLの宛先 - Smart Scriptを含むランディングページにリダイレクトされます。
3. ランディングページが読み込まれると、Smart Scriptは受信URLパラメーターを含むインプレッションをAppsFlyerへ記録します。このインプレッションにより、Webのランディングページからのビュースルーアトリビューションが可能になります。インプレッションとビュースルーアトリビューションの詳細は、<Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">こちら</Anchor>を参照してください。
4. Smart Scriptは、`fbclid`パラメーターを含む流入時のURLパラメーターに基づいて、ページ上のCTAボタンの遷移先URLを生成します。遷移ボタンの遷移先としては、以下の候補があります：
   - OneLinkの計測リンク経由のGoogle Play / App Store。
   - 複数のプラットフォームストア（CTV、Epic、Steamなど）。この場合、Smart Scriptはプラットフォームごとに単一プラットフォーム用のアトリビューションリンクを生成し、指定したプラットフォームのストアへ遷移させます。
   - クリック後にユーザー端末にAPKファイルをダウンロード。
5. ユーザーがCTAボタンをクリックすると、そのクリックがAppsFlyerに記録されます。
6. ユーザーはストアにリダイレクトされ、アプリをダウンロードします。
7. ユーザーがアプリを開くと、AppsFlyerにインストールイベントが登録されます。
8. AppsFlyerは、確率論的モデリングに基づいて、または[インストールリファラ](https://www.appsflyer.com/glossary/install-referrer/)が利用可能な場合は決定論的手法でインストールをアトリビューションします。
9. `fbclid`パラメーターとその他のイベントパラメーターを含むポストバックが生成され、CAPI API経由でMetaに送信されます。 Metaは`fbclid`パラメーターを使用して個々のクリックを識別し、その他のパラメーターをキャンペーンの最適化に利用します。

</Accordion>

<div id="set-up-smart-script-landing-page" />

<Accordion title="Set up a Smart Script landing page">

スマートスクリプトを使用してMeta Adsキャンペーンを設定するには、次の手順を実行します：

1. キャンペーンのOneLink計測リンクに使用するテンプレートを設定します。詳細は、<Anchor target="_blank" href="/marketers/docs/create-a-onelink-template#create-a-onelink-template">OneLinkテンプレートの作成方法</Anchor>を参照してください。
2. スマートスクリプトのコードを作成してください。詳細は、<Anchor target="_blank" href="/marketers/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink Smart Scriptの作成方法</Anchor>を参照してください。

   <div id="note-6" />

   > 📘 **注意**
   >
   > 以下では、Smart Scriptを使用してMeta広告キャンペーンを設定するために必要な具体的な手順を説明します。 Smart Scriptキャンペーンの設定全般については、<Anchor target="_blank" href="/marketers/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">「OneLink Smart Script V2の設定」</Anchor>の記事内の<Anchor target="_blank" href="/marketers/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">「OneLink Smart Scriptの作成方法」</Anchor>セクションを参照してください。

3. 関連するURLパラメーターがすべて受信URLに追加されていることを確認してください。受信URLに追加されたパラメーターを確認するには、Meta広告マネージャを開き、リンク先URLの作成時に設定したURLパラメーターを確認します。詳細は、 [リンク先URLの設定](#b-set-destination-url)を参照してください。
4. Meta Adsキャンペーンに必要な受信URLパラメーターを、ユーザーがCTAボタンをクリックしたときにAppsFlyerに送信される送信URLパラメーターにマッピングします：
   - **PID**：Smart Scriptが受信URLから `pid=metaweb_int` パラメーターの値を取得し、送信URLの対応するパラメーターにマッピングすることを確認してください。
   - **FBCLID**： `fbclid`パラメーターは、Metaへのアプリ内イベントのポストバックを正常に送信するために必須です。送信 URL FBCLID パラメーターのマッピングは、Smart Scriptのバージョンによって異なります：

     - V2.8.1以降：受信URLに`fbclid`パラメーターがある場合は、送信URLのパラメーターに自動的に引き継がれるため、手動でのマッピングは不要です。
     - V2.8.0以前：**Smart Script**ページの**URLパラメータのマッピング**セクションで、`fbclid`パラメータを手動でマッピングする必要があります：
       1. In **Mapping for**で、 **Custom parameter**を選択してください。
       2. **Outgoing URL parameter** と **Incoming URL parameters** に **fbclid** と入力します。

     <div id="note-7" />

     > 📘 **注意**
     >
     > AppsFlyerのローデータレポートに表示するには、受信URLの`fbclid`パラメーターを、（送信URLの`fbclid`パラメーターに加えて）送信URLの`af_sub[1-5]`パラメーターのいずれかにもマッピングする必要があります。詳細は、<Anchor target="_blank" href="/marketers/docs/set-up-smart-script-to-convert-web-visitors#facebook-click-id">Facebook FBCLID</Anchor>を参照してください。

</Accordion>

<div id="set-up-smart-script-crossplatform-landing-page" />

<Accordion title="Set up a Smart Script cross-platform landing page">

Smart Script Meta Adsキャンペーンをクロスプラットフォームのランディングページ向けに設定するには、次の手順を実行します：

1. キャンペーンのOneLink計測リンクに使用するテンプレートを設定します。詳細は、<Anchor target="_blank" href="/marketers/docs/create-a-onelink-template#create-a-onelink-template">OneLinkテンプレートの作成方法</Anchor>を参照してください。
   - OneLinkテンプレートでクロスプラットフォーム計測を有効にします。詳しくは<Anchor target="_blank" href="/marketers/docs/set-up-cross-platform-links-for-multi-device-campaigns#create-a-onelink-templatefor-cross-platform-attribution">こちら</Anchor>を参照してください。
2. 関連するURLパラメーターがすべて受信URLに追加されていることを確認してください。受信URLに追加されたパラメーターを確認するには、Meta広告マネージャを開き、リンク先URLの作成時に設定したURLパラメーターを確認します。詳細は、[リンク先URLの設定](#b-set-destination-url)を参照してください。
3. 各受信パラメーターにおいて、マッピングする送信パラメーターを決定します。たとえば、受信URLの`af_site_id`を送信URLの`af_site_id`にマッピングします。
4. 空欄にできない必須の送信パラメーターのデフォルト値を決定します。
5. 開発者に次の情報を共有してください：
   - 受信 - 送信パラメーターのマッピングリスト。開発者は、受信パラメーターと送信パラメーターのマッピングに基づいて送信ダイレクトURLを生成するスクリプトを作成します。
   - パラメーターのデフォルト値。対応する受信URLのパラメーターに値がない場合、スクリプトは送信URLのパラメーターにデフォルト値を設定します。
   - OneLink計測リンクを使用している場合は、そのドメインとテンプレートIDを開発者に共有してください。開発者はこの情報を使ってOneLinkの送信URLを作成します。例：`yourbrand.onelink.me/A1b2`。ブランドドメインの場合の例： `click.yourbrand.com/A1b2`
   - 開発者に以下のDev Hubのリンクを共有してください：
     - モバイル以外のプラットフォーム向けの送信ダイレクトURLを作成するための[手順とコード例](https://dev.appsflyer.com/hc/docs/create-direct-click-url)。
     - クロスプラットフォームのランディングページを作成するための[デモと手順](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/)。
   - 受信URLの`fbclid`パラメーターを送信URLに含めるよう、開発者に伝えてください。

     <div id="note-8" />

     > 📘 **注意**
     >
     > AppsFlyerのローデータレポートに表示するには、受信URLの`fbclid`パラメーターを（送信URLの`fbclid`パラメーターに加えて）、送信URLの`af_sub[1-5]`パラメーターのいずれかにもマッピングする必要があります。

</Accordion>

<div id="create-a-landing-page-with-onelink-smart-banners" />

## OneLinkスマートバナーでランディングページを作成

**ユーザーの遷移：** ユーザーがMeta広告をクリックすると、モバイルWebサイトに移動します。移動先のページには、アプリストアからのアプリのダウンロードを促すCTA付きのスマートバナーが表示されます。

<div id="end-to-end-data-flow::4f887e1c" />

<Accordion title="End-to-end data flow">

1. Meta広告のURLには、`pid=metaweb_int`パラメーターが含まれます。ユーザーが広告をクリックすると、クリックしたURLに`fbclid`パラメーターが自動的に追加されます。
2. ユーザーが、遷移先のURL（スマートバナーを含むランディングページ）にリダイレクトされます。
3. ランディングページが読み込まれると、Smart Bannerは受信URLのパラメーターを含む<Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">インプレッション</Anchor>イベントをAppsFlyerに送信します。このインプレッションの計測を行うことで、ランディングページでのビュースルー計測が可能になります。インプレッションとビュースルーアトリビューションについては、 <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">こちら</Anchor>をご覧ください。
4. Smart Bannerは、バナーのCTAボタンの送信URLを生成します。送信URLは、`fbclid`パラメーターを含む受信URLのパラメーターに基づいて生成されます。 Smart Bannerでは、OneLinkベースのリンクのみを生成できます。
5. ユーザーがSmart BannerのCTAボタンをクリックすると、AppsFlyerにもクリックが計測されます。
6. ユーザーはストアにリダイレクトされ、アプリをダウンロードします。
7. ユーザーがアプリを開くと、AppsFlyerにインストールイベントが登録されます。
8. AppsFlyerは、確率論的モデリングに基づいて、またはインストールリファラーが利用可能な場合は決定論的手法でインストールを計測します。
9. `fbclid`パラメータとその他のイベントパラメータを含むポストバックが生成され、CAPI APIを介してMetaに送信されます。 Metaはfbclidパラメータで個々のクリックを識別し、その他のパラメータをキャンペーンの最適化に利用します。

</Accordion>

<div id="set-up-smart-banners-landing-page" />

<Accordion title="Set up a Smart Banners landing page">

スマートバナーのMeta広告キャンペーンを設定するには、以下の手順に従ってください：

1. キャンペーンのOneLink計測リンクに使用するテンプレートを設定します。詳細は、<Anchor target="_blank" href="/marketers/docs/create-a-onelink-template#create-a-onelink-template">OneLinkテンプレートの作成方法</Anchor>を参照してください。
2. Smart Bannerを作成してください。

   <div id="note-9" />

   > 📘 **注意**
   >
   > 以下の手順では、スマートバナーを使用したMeta広告キャンペーンの設定に必要な具体的な手順に焦点を当てています。 Smart Bannersキャンペーンの設定全般については、<Anchor target="_blank" href="/marketers/docs/smart-banners-mobile-web-to-app-for-marketers">「Smart Banners｜モバイルWebからアプリへの誘導（マーケター向け）」</Anchor>の記事内の<Anchor target="_blank" href="/marketers/docs/smart-banners-mobile-web-to-app-for-marketers#setup">設定セクション</Anchor>を参照してください。

3. Meta広告キャンペーンのスマートバナーパラメータを設定します。
   - 関連するURLパラメータがすべて受信URLに追加されていることを確認してください。特に、Smart Bannerが取得できるよう、受信URLにpid=metaweb_intとfbclidが含まれていることを確認してください。これらの2つのパラメーターは、アトリビューションとMeta広告へのポストバックの送信に必要です。受信URLに追加されたパラメータを確認するには、Meta広告マネージャを開き、遷移先URLの作成時に設定したURLパラメータを確認してください。[遷移先URLの設定](#b-set-destination-url)を参照してください。

</Accordion>

<div id="view-web-to-app-attribution-data" />

## Web-to-appのアトリビューションデータを確認する

Web経由のコンバージョンイベントは、元のPIDである`metaweb_int`を使ってMetaに送信されますが、AppsFlyerのダッシュボードとローデータレポートでは、`Facebook Ads`のPIDで報告されます。この仕様は、主要なコンバージョンイベントとコンバージョンアシストイベントの両方に適用されます。

この統合レポートビューを使えば、Webとアプリのキャンペーン成果を一元的に分析できます。Web／モバイル双方のコストデータも含め、まとめて把握することが可能です。

<div id="view-in-the-dashboard" />

### 管理画面上でのデータ表示について

MetaのWeb-to-appのアトリビューションはすべて、オーバービューとアクティビティの管理画面で`Facebook Ads`の下に表示されます。これにより、プラットフォーム全体でのキャンペーンの結果を確認できるようになります。標準フィルタとブレークダウンを使用して、Meta広告のデータにおけるアプリとWebのトラフィックを比較してください。

<div id="view-in-raw-data-and-api-reports" />

### ローデータとAPIレポート内でのデータ表示

- **ローデータのエクスポートとAPIレスポンス**では、MetaのWeb上のアクティビティについて、`media_source`フィールドに`Facebook Ads`のPIDが含まれます。 Webキャンペーンの設定内容を確認するには、`original_url`フィールドを参照してください。Webキャンペーンの作成時に使用したPIDとして、`metaweb_int`が表示されます。
- **ポストバックレポート**には、ポストバックの送信先である元のメディアソースとして`metaweb_int`が表示されます。

<div id="traits-and-limitations" />

## 特徴と制限事項

| 特性                    | 補足                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| コスト、クリック、インプレッションのデータ | Meta広告のWebキャンペーン（`metaweb_int`）のコスト、クリック、インプレッションのデータは、Meta広告連携（`Facebook Ads`）を通じて取得できます。<ul><li>データを取得するには、アドネットワークのアカウントをメインのPID（`Facebook Ads`）に接続してください。接続する場所は次のとおりです。<ul><li>ROI360の契約者：**コスト設定**ページ</li><li>ROI360の非契約者：**アクティブな連携**ページ（**コスト**タブ）。</li></ul></li><li>Meta広告のWebキャンペーンのコスト、クリック、インプレッションのデータを表示するには、アトリビューションリンクにキャンペーンID（<Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#af_c_id">af\_c\_id</Anchor>）が含まれていることを確認してください。</li><li>アトリビューションに紐づくコスト、クリック、インプレッションのデータを最も粒度の細かいレベルで表示するには、アトリビューションリンクにキャンペーンの完全な階層を含める必要があります。</li></ul> |

<div data-zendesk-anchors="h_01HZKNS17JYFQ3F5TKNE5Q5TJ4=overview h_01J8CYG29BETYPZ03A1X54M3ZF=note prerequisite=prerequisites h_01HZKNS17JTCXE4JMZ64NEVPS6=prerequisites how-to-create-a-meta-ads-campaign=how-to-create-a-meta-web-ads-campaign h_01HZKNS17JERCAKZHK43ZQWARJ=how-to-create-a-meta-web-ads-campaign set-up-meta-ads-integration-in-appsflyer=set-up-meta-web-ads-integration-in-appsflyer h_01HZKNS17J284R2MAN42WV7F0S=set-up-meta-web-ads-integration-in-appsflyer h_01HZKNS17JGQBENY2X8S5PHFVH=a-activate-the-meta-ads-integration h_01ZXVWB1ZYKK4DP38QY1RMEY6M=d-enable-view-through-attribution-for-meta-web h_01HZKNS17JH2ZJKATV1AP6JDWP=b-set-inapp-event-postbacks 01JJ4MGS84WXEVG4FWQ0YQ7GN6=note-1 h_01_s2s_metaweb_ua_ip=note-2 h_01HZKNS17JJWX7N9W6BN05B57C=set-up-appsflyer-integration-in-meta-ads h_01HZKNS17JTVX8N5CKTKVGH0QB=a-set-the-campaign-type-objective-and-goals h_01HZKNS17JHHS7GYPBT441ND7A=note-3 h_01HZKNS17KT8TRD2TGDBRGKBZ3=b-set-destination-url h_01HZKNS17KCNKS4YY4JHMQRM1Z=important h_01J2V9WF300WDY0PWV68TDR9TT=note-4 h_01K88MSNRX9QFQ49FN2MXPMADX=tip 01J2V903C36X5K6VRPGQQGWFMW=note-5 h_01HZKNS17K07CENP8GG7MQRKHK=c-select-tracked-events h_01HZKNS17KARAENYPMVJSM1ARQ=important-1 create-landing-page-with-onelink-smart-script=create-a-landing-page-with-onelink-smart-script h_01HZKNS17KPJMP74HQKWY022T2=create-a-landing-page-with-onelink-smart-script h_01HZKNS17K5PRRXSD2JMJ54NTN=end-to-end-data-flow h_01HZKNS17KA8VAK5TDFG1NV9YN=set-up-smart-script-landing-page h_01HZKNS17K6DPA6E9CTM5F3X1A=note-9 h_01HZKNS17K2W4XJB0BH87RZYTJ=note-8 h_01HZKNS17K5RRAFFTNA6QT7AKJ=set-up-smart-script-crossplatform-landing-page h_01HZKNS17K03S4B3ZRQ62TRFRE=note-8 create-landing-page-with-onelink-smart-banners=create-a-landing-page-with-onelink-smart-banners h_01HZKNS17KH8NQ68RPZGMEAQTV=create-a-landing-page-with-onelink-smart-banners h_01HZKNS17K4Y7WSM14EEJ2G5NC=end-to-end-data-flow::4f887e1c h_01HZKNS17KZ3YKS5R52SRKR9P2=set-up-smart-banners-landing-page h_01HZKNS17K3W3GPV6TM5RQS1WP=note-9 meta%20view=view-web-to-app-attribution-data view-webtoapp-attribution-data-from-november-2-2025=view-web-to-app-attribution-data h_01K88J8JFNEYBZNR18133NMRP9=view-web-to-app-attribution-data h_01K88J8JFNMHCVZ0C34E3D7AST=view-in-the-dashboard h_01K88J8JFN8W2572N92466YFZQ=view-in-raw-data-and-api-reports 01JEZXJNF1C932KGAEFS4P5D51=traits-and-limitations" />
