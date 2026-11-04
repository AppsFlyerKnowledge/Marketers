---
title: Meta広告｜Webキャンペーンの作成
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
  created_at: '2024-06-04T16:08:28Z'
  edited_at: '2026-10-28T09:16:42Z'
  id: 25646834966033
  locale: ja
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ja/articles/25646834966033
---
> **概要：** Meta広告のWebキャンペーンを使用して、Meta広告経由のWebからアプリへのコンバージョンを計測します。

<div id="overview" />

## 概要

AppsFlyerは、ユーザー獲得を目的とするWebキャンペーン向けに、Meta広告（`metaweb_int`）との連携をサポートしています。MetaのコンバージョンAPI（CAPI）を通じて、アトリビューションデータとコンバージョンデータを直接報告できます。 Metaは、このデータを広告ターゲティングの最適化、パフォーマンスの計測、カスタムオーディエンスの作成に利用できます。

<div id="note" />

> 📘 **注意**
>
> 現在、Meta Web連携では、CAPIへのリエンゲージメントポストバックの送信はサポートされていません。

<div id="prerequisites" />

### 前提条件

Meta広告連携を有効にする前に、[Metaビジネスマネージャのビジネスアカウント](https://www.facebook.com/business/help/1710077379203657?id=180505742745347)があることを確認してください。

<div id="how-to-create-a-meta-web-ads-campaign" />

### Meta広告のWebキャンペーンの作成方法

この記事では、AppsFlyerを使用して、モバイル、PC、コンソールアプリ向けのMeta広告のWebキャンペーンを設定する方法と手順を説明します。設定では、Meta広告とAppsFlyerの連携を定義し、両プラットフォームでキャンペーンを設定したうえで、OneLink Smart ScriptまたはOneLink Smart Bannersを使用したランディングページを作成します。  
以下の設定手順は必須です。

* [AppsFlyerでMeta広告のWeb連携を設定する](#h_01HZKNS17J284R2MAN42WV7F0S)（必須）
* [Meta広告でAppsFlyer連携を設定する](#h_01HZKNS17JJWX7N9W6BN05B57C)（必須）

以下の手順は任意です。

* [OneLink Smart Scriptを使用したランディングページを作成する](#h_01HZKNS17KPJMP74HQKWY022T2)（任意）
* [OneLink Smart Bannersを使用したランディングページを作成する](#h_01HZKNS17KH8NQ68RPZGMEAQTV)（任意）

<div id="set-up-meta-web-ads-integration-in-appsflyer" />

## AppsFlyerでのMeta広告のWeb連携の設定

まず、Meta広告連携を有効にし、AppsFlyerからCAPIに送信するポストバックを設定します。

<div id="a-activate-the-meta-ads-integration" />

<Accordion title="1. Meta広告のWeb連携の有効化">

Meta広告のWeb連携を有効にするには、以下の手順に従ってください。

1. AppsFlyerのサイドメニューから、**［連携］**>**［パートナー連携］**><strong>［パートナーマーケットプレイス］</strong>に移動します。
2. **Meta Web**を検索し、選択します。設定ページが表示されます。
3. <strong>［連携］</strong>タブで、<strong>［パートナーを有効にする］</strong>をオンにします。**注意：** このパートナーとの連携を継続する間は、トグルをオン（<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">有効</Anchor>）のままにしてください。
4. iOSアプリの連携を設定する場合は、<strong>［高度なプライバシー］</strong>をオフにします。
5. **詳細マッチングデータの共有：** オンにすると、AppsFlyerに送信されたイベント情報に、ハッシュ化したメールアドレス、電話番号、名、姓、FacebookログインIDなどの詳細マッチング用の項目が含まれる場合、それらがMetaと共有されます。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/advanced-matching-data-sharing">詳細マッチングデータの共有</Anchor>を参照してください。
6. <strong>［ピクセルID］</strong>欄に入力します。ピクセルIDは、Meta広告マネージャで取得できます。
   1. <span class="af-ol-a"></span> [広告マネージャ](https://www.facebook.com/ads/manager)のサイドメニューから、**［すべてのツール］**><strong>［イベントマネージャ］</strong>に移動します。 **注意：** 右上のドロップダウンで、対象のビジネスが選択されていることを確認してください。
   2. **イベントマネージャ**のサイドメニューで、<strong>［データソース］</strong>を選択します。ピクセルの一覧が表示されます。 選択したビジネスのピクセルがない場合は、同じ画面から作成できます。
   3. ピクセル名の下に表示されるピクセルIDをコピーします。  
      AppsFlyerの<strong>［ピクセルID］</strong>欄に貼り付けます。
7. <strong>［アクセストークン］</strong>欄に入力します。アクセストークンの取得方法は、[こちらの手順](https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token)を参照してください。
8. <Anchor target="_blank" href="/marketers/ja/docs/send-opendsr-api-requests">データ保護法</Anchor>に対応するには、<strong>［Meta広告によるユーザーの個人情報の利用を制限（CCPA）］</strong>をオンにします。**注意：** CCPAのプライバシー規制に対応すると、カリフォルニア州のMeta広告ユーザーから取得するデータが制限されます。

</Accordion>

<div id="d-enable-view-through-attribution-for-meta-web" />

<Accordion title="2. ビュースルーアトリビューションの有効化">

AppsFlyerは、[Smart Script](#set-up-smart-script-crossplatform-landing-page)または[Smart Banner](#set-up-smart-banners-landing-page)を実装したランディングページを使用するMeta Webキャンペーンのビュースルーアトリビューションに対応しています。これにより、ユーザーが広告を直接クリックしなくても、広告表示をきっかけに発生したアプリインストールを、確率論的モデリング（PMOD）で計測できます。

ユーザーがMeta Web広告をクリックし、[Smart Script](#set-up-smart-script-crossplatform-landing-page)または[Smart Banner](#set-up-smart-banners-landing-page)を実装したランディングページに到達すると、AppsFlyerは、その後に発生したアプリのインストールをアトリビューションできます。 `fbclid`を取得できる場合は、Metaへのポストバックに含めることで、アトリビューションの精度を高めます。

**Meta Webのビュースルーアトリビューションを有効にするには、以下の手順に従ってください。**

1. AppsFlyerのサイドメニューから、**［連携］**>**［パートナー連携］>［連携済みパートナー］**><strong>［Meta web ads］</strong>を開きます。
2. <strong>［連携］</strong>タブで、<strong>［インストールアトリビューション］</strong>セクションまでスクロールします。
3. <strong>［インストールのビュースルーアトリビューション］</strong>をオンにします。
4. <strong>［任意］［クロスプラットフォームのアトリビューション優先度を同等にする］</strong>をオンにし、ルックバック期間を設定します。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">クロスプラットフォームのインプレッションへの同等の優先度の設定</Anchor>を参照してください。
5. <strong>［計測リンク］</strong>タブを開きます。
6. <strong>［ビュースルーアトリビューション］</strong>セクションまでスクロールし、**ビュースルールックバック期間**を設定します（最大24時間）。
7. <strong>［連携を保存］</strong>をクリックして、設定を適用します。

</Accordion>

<div id="b-set-inapp-event-postbacks" />

<Accordion title="3. アプリ内イベントポストバックの設定">

現在、Meta広告へのデフォルトポストバックが自動的に送信されるイベントは、インストールのみです。その他の種類のイベントについては、AppsFlyerのイベントをMeta広告のイベントにマッピングして、カスタムポストバックを作成できます。これらは[Metaイベントマネージャ](https://www.facebook.com/business/help/1541268312717919?id=818859032317965)で確認できます。  
アプリ内イベントポストバックを設定するには、以下の手順に従ってください。

1. <strong>［アプリ内イベントポストバック］</strong>をオンにします。
2. 必要に応じて、アプリ内イベントポストバック期間を設定します（設定の一般的な説明は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#アプリ内イベントポストバック期間">こちらの記事</Anchor>を参照してください）。
3. <strong>［イベントを追加］</strong>をクリックし、リストにイベントを追加します。
4. <strong>［AppsFlyerイベント］</strong>列のドロップダウンから、イベント名を選択します。 AppsFlyerは、アプリに実装されたSDKまたはサーバー間イベントからイベント名を受信します。
5. <strong>［マッピング先のパートナーイベント］</strong>列のドロップダウンから、最適な定義済みパートナーイベントを選択するか、CUSTOMを選択します。
6. <strong>［送信対象ユーザー］</strong>列で、イベントの送信対象を選択します。
   * **このパートナーのみ**：このイベントがMeta広告にアトリビューションされた場合にのみ、ポストバックを送信します。
   * **オーガニックを含むすべてのメディアソース**：いずれかのパートナーにアトリビューションされたイベントと、オーガニックのイベントについてポストバックを送信します。
7. <strong>［送信データ］</strong>列で、イベントに収益値を含めて送信するかどうかを選択します。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#ポストバックに含めるデータ">ポストバックに含めるデータ</Anchor>を参照してください。

   <div id="note-1" />

   > 📘 **注意**
   >
   > 購入イベントを設定する場合は、<strong>［送信データ］</strong>列で<strong>［イベント値と収益］</strong>を選択してください。それ以外の選択肢を選ぶと、ポストバックが失敗します。

8. ［任意］<strong>［条件を追加］</strong>アイコンをクリックして、イベントの<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">条件を設定します</Anchor>。
9. <strong>［連携を保存］</strong>をクリックします。
10. ［任意］連携を保存した後、設定ページを開いたまま、同じパートナーに他のアプリも連携できます。
    1. <span class="af-ol-a"></span>左上のパートナー名の下にあるアプリ名をクリックし、アプリの一覧を開きます。
    2. ドロップダウンリストから、別のアプリを選択します。
    3. 選択したアプリで連携手順を繰り返します。

<div id="note-2" />

> 📘 **注意**
>
> `metaweb_int`にS2Sイベントを送信する場合、S2Sペイロードには`ua`（ユーザーエージェント）と`ip`（IPアドレス）のパラメータを必ず含めてください。これらの値は、Meta CAPIによるキャンペーン最適化に必要です。 SDKイベントの場合、AppsFlyerが自動的にこれらの値を含めます。 S2Sイベントの場合は、広告主が明示的に送信する必要があります。<Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">モバイル向けサーバー間イベントAPI</Anchor>を参照してください。

</Accordion>

<div id="set-up-appsflyer-integration-in-meta-ads" />

## Meta広告でのAppsFlyer連携の設定

以下の手順は、Meta広告マネージャで行います。

<div id="a-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. キャンペーンの種類、目的、目標の設定">

1. Meta広告にログインし、キャンペーンを作成します。
2. <strong>［キャンペーンの目的］</strong>で、以下のいずれかを選択します。 [![](https://files.readme.io/a0cdd42ddf3bc69106de5137e5c842468178bd1dcd76805ea77ead750ba1e9bb-25646834955921.png)](https://files.readme.io/a0cdd42ddf3bc69106de5137e5c842468178bd1dcd76805ea77ead750ba1e9bb-25646834955921.png)
   * **売上**：特定のイベント（主要なKPI）に向けてMetaが最適化します。
   * **トラフィック**：広告クリックに向けてMetaが最適化します。他にKPIがない場合、または他のKPIイベントの件数が少なすぎる場合にのみ使用してください。
3. ［任意］上記の選択肢にカスタムの目的を追加する場合は、以下の手順に従ってください。
   1. <span class="af-ol-a"></span>Meta広告で、キャンペーンの目的に設定するカスタムイベントを選択し、コンバージョンアクションとして指定します。
   2. AppsFlyerの**Meta Web連携**ページで、<strong>［アプリ内イベントポストバック］</strong>の<strong>［マッピング先のパートナーイベント］</strong>列から、AppsFlyerのイベントをカスタムパートナーイベントにマッピングし、Meta広告のコンバージョンアクションと同じ名前を付けます。

      <div id="note-3" />

      > 📘 **注意**
      >
      > Metaのキャンペーン目的の詳細は、[Metaのドキュメント](https://www.facebook.com/business/help/175683976191028)を参照してください。

4. <strong>［コンバージョンの場所］</strong>で<strong>［Webサイト］</strong>を選択します。 [![](https://files.readme.io/32e4dcb4ced7e2011728ed709069b78cffffc4090f09a33c729a2b2e7e882e8b-25646834954257.png)](https://files.readme.io/32e4dcb4ced7e2011728ed709069b78cffffc4090f09a33c729a2b2e7e882e8b-25646834954257.png)
5. <strong>［ピクセル］</strong>には、AppsFlyerのパートナーマーケットプレイスで`metaweb_int`に入力したものと同じピクセルIDを指定します。 Metaピクセルの詳細は、[Metaのドキュメント](https://www.facebook.com/business/help/742478679120153)を参照してください（ログインが必要です）。
6. <strong>［次へ］</strong>をクリックします。

</Accordion>

<div id="b-set-destination-url" />

<Accordion title="2. 遷移先URLの設定">

1. <strong>［遷移先］</strong>の<strong>［WebサイトURL］</strong>欄に、広告の遷移先となるURLを入力します。以下のいずれかのURLを指定してください。

   [![](https://files.readme.io/aec9109f2f3000f669799093460e70198de1934e483314b6cd7f95d8209f361d-25646834955537.png)](https://files.readme.io/aec9109f2f3000f669799093460e70198de1934e483314b6cd7f95d8209f361d-25646834955537.png)

   * **Webランディングページ：** 以下の場合は、ランディングページの使用を推奨します。

     * 複数のプラットフォームでアプリを提供している場合。
     * 広告で宣伝する商品について、ランディングページで詳しく説明したい場合。
     * ランディングページでより多くのデータを収集したい場合。

     これらの用途では、[Smart Script](#h_01HZKNS17KPJMP74HQKWY022T2)または[Smart Banner](#h_01HZKNS17KH8NQ68RPZGMEAQTV)を実装したランディングページを作成してください。
   * **AF計測リンク：** ランディングページを経由せず、ユーザーをストアに直接リダイレクトしてアプリをダウンロードさせたい場合は、AF計測リンク（OneLink、単一プラットフォーム、クロスプラットフォーム）の使用を推奨します。

     <div id="important" />

     > 🚧 **重要！**
     >
     > AF計測リンクを使用すると、エラーが発生する場合があります。その場合は、Metaの担当者に解決方法を問い合わせるか、遷移先URLとしてWebランディングページを使用してください。

2. <strong>［URLパラメータを作成］</strong>をクリックし、URLにパラメータを追加します。ランディングページURL、AF計測リンクのどちらの場合も同様です。
3. <strong>［カスタムパラメータ］</strong>で、<strong>［パラメータを追加］</strong>をクリックします。

   [![4.png](https://files.readme.io/bbce415e16d3442f8959bf7a0c23825035d7d4740d5bf3570306c3684c8764d4-25722672143633.png)](https://files.readme.io/bbce415e16d3442f8959bf7a0c23825035d7d4740d5bf3570306c3684c8764d4-25722672143633.png)
4. AppsFlyerのパラメータを、対応するMetaの値にマッピングします。

   * 遷移先URLが**ランディングページ、OneLink計測リンク、単一プラットフォーム計測リンク**の場合は、以下のAFパラメータを、対応するMetaの値にマッピングします。

| AFのパラメータ | マッピングするMetaの値 |
| --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#pid">`pid`</Anchor> | `metaweb_int` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#c">`c`</Anchor> | `{{campaign.name}}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | `{{campaign.id}}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adset.name}}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{ad.name}}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}` |

     生成されるURLの例：

     ```http
     https://app.appsflyer.com/{app_id}?pid=metaweb_int&c={{campaign.name}}&af_siteid={{site_source_name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r={https://Add-your-store-url.com}
     ```

     * アプリのAPKをGoogle Playストアで配信していない場合は、<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_r">`af_r`</Anchor>パラメータを追加し、ストアURL（例：`https://Add-your-store-url.com`）を指定します。
   * 遷移先URLが**PCまたはコンソールのストア**の場合は、以下の表の説明に従ってリンクを作成します。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-direct-attribution-links">CTV、PC、コンソールプラットフォームの直接計測リンク</Anchor>を参照してください。

<table><thead><tr><th colspan="2">計測リンクの構造</th></tr></thead><tbody><tr><td>ベースURL</td><td>engagements.appsflyer.com/v1.0/c2s/click/app/</td></tr><tr><td>必須のパスパラメータ</td><td><ul><li>platform<br/>例：steam</li><li>app_id<br/>例：123456</li></ul></td></tr><tr><td>必須のクエリパラメータ</td><td><ul><li>af_media_source</li><li>af_campaign_id</li><li>af_r</li></ul></td></tr><tr><td>その他のパラメータ</td><td><a href="./ctv-pc-and-console-platform-direct-attribution-links#パラメーター" target="_blank">すべてのパラメータを確認</a></td></tr><tr><td>URLの構造</td><td><code>https://engagements.appsflyer.com/v1.0/c2s/click/app/`{platform}/{app_id}?af_media_source={media_source}&amp;af_campaign_id={campaign_id}&amp;af_r={app_store_url}`</code></td></tr></tbody></table>

     以下のAppsFlyerパラメータを、対応するMetaの値にマッピングします。

| AFのパラメータ | マッピングするMetaの値 |
| --- | --- |
| `af_media_source` | `metaweb_int` |
| `af_campaign` | `{{campaign.name}}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_c_id">`af_campaign_id`</Anchor> | `{{campaign.id}}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adset.name}}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{ad.name}}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}` |

     クロスプラットフォームURLの例：

     ```http
     https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
     ```

   <div id="note-4" />

   > 📘 **注意**
   >
   > Metaは、広告がクリックされると遷移先URLに`fbclid={{fbclid}}`を自動的に追加します。


   <div id="tip" />

   > 👍 **ヒント**
   >
   > キャンペーンの分析を容易にするため、キャンペーン名の先頭または末尾に、Webやモバイルなどのキャンペーンの種類を付けてください（例：campaign-name\_web）。


<div id="note-5" />

> 📘 **注意**
>
> AF計測リンクのパラメータの詳しい説明は、<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#計測リンクのパラメータ">計測リンクのパラメータ</Anchor>を参照してください。

</Accordion>

<div id="c-select-tracked-events" />

<Accordion title="3. 計測対象イベントの選択">

［トラッキング］セクションで、広告で促進するコンバージョンイベントを選択します（イベント自体は[イベントマネージャ](https://www.facebook.com/business/help/898185560232180?id=1205376682832142)で設定します）。

[![](https://files.readme.io/75b6136fdf3fd9790e39aeec735ccd2e1ff0b8a5f302c85f0ed3b05926fcc435-25646834958481.png)](https://files.readme.io/75b6136fdf3fd9790e39aeec735ccd2e1ff0b8a5f302c85f0ed3b05926fcc435-25646834958481.png)

<div id="important-1" />

> 🚧 **重要！**
>
> は選択しないでください。選択すると、MetaがSRN APIを通じてこれらのコンバージョンのアトリビューションを申告するため、レポートと最適化に不整合が生じる可能性があります。

</Accordion>

<div id="create-a-landing-page-with-onelink-smart-script" />

## OneLink Smart Scriptを使用したランディングページの作成

**ユーザーの遷移：** ユーザーがMeta広告をクリックすると、モバイルWebサイトに移動します。ランディングページには、1つまたは複数のプラットフォームでアプリのダウンロードを促すCTAボタンが表示されます。ボタンをクリックすると、ユーザーはストアにリダイレクトされます。

<div id="end-to-end-data-flow" />

<Accordion title="データ連携の全体の流れ">

[![](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)

1. Meta広告のURLには、`pid=metaweb_int`パラメータが含まれます。ユーザーが広告をクリックすると、クリックしたURLに`fbclid`パラメータが自動的に追加されます。
2. ユーザーは、URLの遷移先である、Smart Scriptを実装したランディングページにリダイレクトされます。
3. ランディングページが読み込まれると、Smart Scriptは受信URLのパラメータを含むインプレッションをAppsFlyerに送信します。このインプレッションにより、Webランディングページからのビュースルーアトリビューションが可能になります。インプレッションとビュースルーアトリビューションの詳細は、<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">こちら</Anchor>を参照してください。
4. Smart Scriptは、`fbclid`を含む受信URLのパラメータに基づいて、ページ上のCTAボタンの送信URLを生成します。ボタンには、以下の遷移先や動作を設定できます。
   * OneLink計測リンクを介したGoogle PlayまたはApp Storeへの遷移。
   * 複数のプラットフォームのストア（CTV、Epic、Steamなど）への遷移。この場合、Smart Scriptはプラットフォームごとに単一プラットフォーム計測リンクを生成し、それぞれのストアに誘導します。
   * ユーザーのデバイスへのAPKファイルのダウンロード。
5. ユーザーがCTAボタンをクリックすると、クリックが送信され、AppsFlyerに記録されます。
6. ユーザーはストアにリダイレクトされ、アプリをダウンロードします。
7. ユーザーがアプリを開くと、AppsFlyerにインストールイベントが記録されます。
8. AppsFlyerは、確率論的モデリングに基づいてインストールをアトリビューションします。[インストールリファラ](https://www.appsflyer.com/glossary/install-referrer/)を取得できる場合は、確定的な手法でアトリビューションします。
9. `fbclid`とその他のイベントパラメータを含むポストバックが生成され、CAPIを介してMetaに送信されます。 Metaは`fbclid`パラメータで個々のクリックを識別し、その他のパラメータをキャンペーンの最適化に利用します。

</Accordion>

<div id="set-up-smart-script-landing-page" />

<Accordion title="Smart Scriptを使用したランディングページの設定">

Smart Scriptを使用するMeta広告キャンペーンを設定するには、以下の手順に従ってください。

1. キャンペーンのOneLink計測リンクに使用するテンプレートを設定します。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレートの作成方法</Anchor>を参照してください。
2. Smart Scriptを作成します。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink Smart Scriptの作成方法</Anchor>を参照してください。

   <div id="note-6" />

   > 📘 **注意**
   >
   > 以下では、Smart Scriptを使用するMeta広告キャンペーンに固有の設定手順を説明します。 Smart Scriptキャンペーンの設定全般については、<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">「OneLink Smart Script V2の設定」</Anchor>の記事内の<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">「OneLink Smart Scriptの作成方法」</Anchor>セクションを参照してください。

3. 必要なURLパラメータがすべて受信URLに追加されていることを確認します。追加されたパラメータを確認するには、Meta広告マネージャを開き、遷移先URLの作成時に設定したURLパラメータを確認してください。詳細は、[遷移先URLの設定](#h_01HZKNS17KT8TRD2TGDBRGKBZ3)を参照してください。
4. Meta広告キャンペーンに必要な受信URLのパラメータを、ユーザーがCTAボタンをクリックしたときにAppsFlyerへ送信される送信URLのパラメータにマッピングします。
   * **PID**：Smart Scriptが受信URLから`pid=metaweb_int`の値を取得し、送信URLの対応するパラメータにマッピングすることを確認してください。
   * **FBCLID**：`fbclid`パラメータは、Metaへのアプリ内イベントポストバックを正常に送信するために必須です。送信URLのFBCLIDパラメータのマッピング方法は、Smart Scriptのバージョンによって異なります。

     * V2.8.1以降：受信URLに`fbclid`パラメータがある場合は、送信URLのパラメータに自動的に引き継がれるため、手動のマッピングは不要です。
     * V2.8.0以前：**Smart Script**ページの<strong>［URLパラメータのマッピング］</strong>セクションで、`fbclid`パラメータを手動でマッピングする必要があります。
       1. <strong>［マッピング対象］</strong>で、<strong>［カスタムパラメータ］</strong>を選択します。
       2. <strong>［送信URLパラメータ］</strong>と<strong>［受信URLパラメータ］</strong>の両方に、**fbclid**を入力します。

     <div id="note-7" />

     > 📘 **注意**
     >
     > AppsFlyerのローデータレポートに表示するには、受信URLの`fbclid`パラメータを、送信URLの`fbclid`パラメータに加えて、送信URLの`af_sub[1-5]`パラメータのいずれかにもマッピングする必要があります。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#facebook-click-id">Facebook FBCLID</Anchor>を参照してください。


</Accordion>

<div id="set-up-smart-script-crossplatform-landing-page" />

<Accordion title="Smart Scriptを使用したクロスプラットフォーム向けランディングページの設定">

クロスプラットフォーム向けランディングページでSmart Scriptを使用するMeta広告キャンペーンを設定するには、以下の手順に従ってください。

1. キャンペーンのOneLink計測リンクに使用するテンプレートを設定します。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレートの作成方法</Anchor>を参照してください。
   * OneLinkテンプレートでクロスプラットフォームアトリビューションを有効にします。<Anchor target="_blank" href="/marketers/ja/docs/set-up-cross-platform-links-for-multi-device-campaigns#クロスプラットフォーム計測用のonelinkテンプレートの作成">こちら</Anchor>を参照してください。
2. 必要なURLパラメータがすべて受信URLに追加されていることを確認します。追加されたパラメータを確認するには、Meta広告マネージャを開き、遷移先URLの作成時に設定したURLパラメータを確認してください。詳細は、[遷移先URLの設定](#h_01HZKNS17KT8TRD2TGDBRGKBZ3)を参照してください。
3. 受信URLの各パラメータを、送信URLのどのパラメータにマッピングするか決めます。たとえば、受信URLの`af_site_id`を送信URLの`af_site_id`にマッピングします。
4. 空欄にできない送信URLの必須パラメータについて、デフォルト値を決めます。
5. 開発者に以下の情報を渡します。
   * 受信URLと送信URLのパラメータのマッピング。開発者は、このマッピングに基づいて送信先の直接URLを生成するスクリプトを作成します。
   * 各パラメータのデフォルト値。対応する受信URLパラメータに値がない場合、スクリプトは送信URLのパラメータにデフォルト値を設定します。
   * OneLink計測リンクを使用する場合は、ドメインとテンプレートIDを開発者に渡します。開発者は、これらを使用して送信先のOneLink URLを作成します。例：`yourbrand.onelink.me/A1b2`。ブランドドメインの場合の例：`click.yourbrand.com/A1b2`。
   * 以下のDev Hubのリンクを開発者に共有します。
     * モバイル以外のプラットフォームへの直接の送信URLを作成するための[手順とコード例](https://dev.appsflyer.com/hc/docs/create-direct-click-url)。
     * クロスプラットフォーム向けランディングページを作成するための[デモと手順](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/)。
   * 受信URLの`fbclid`パラメータを送信URLに含めるよう、開発者に伝えてください。

     <div id="note-8" />

     > 📘 **注意**
     >
     > AppsFlyerのローデータレポートに表示するには、受信URLの`fbclid`パラメータを、送信URLの`fbclid`パラメータに加えて、送信URLの`af_sub[1-5]`パラメータのいずれかにもマッピングする必要があります。


</Accordion>

<div id="create-a-landing-page-with-onelink-smart-banners" />

## OneLink Smart Bannersを使用したランディングページの作成

**ユーザーの遷移：** ユーザーがMeta広告をクリックすると、モバイルWebサイトに移動します。ランディングページには、アプリストアからアプリをダウンロードするよう促すCTA付きのSmart Bannerが表示されます。

<div id="end-to-end-data-flow::4f887e1c" />

<Accordion title="データ連携の全体の流れ">

1. Meta広告のURLには、`pid=metaweb_int`パラメータが含まれます。ユーザーが広告をクリックすると、クリックしたURLに`fbclid`パラメータが自動的に追加されます。
2. ユーザーは、URLの遷移先である、Smart Bannerを実装したランディングページにリダイレクトされます。
3. ランディングページが読み込まれると、Smart Bannerは受信URLのパラメータを含む<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">インプレッション</Anchor>イベントをAppsFlyerに送信します。このインプレッションにより、ランディングページのビュースルーアトリビューションが可能になります。インプレッションとビュースルーアトリビューションの詳細は、<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">こちら</Anchor>を参照してください。
4. Smart Bannerは、バナー上のCTAボタンの送信URLを生成します。送信URLは、`fbclid`を含む受信URLのパラメータに基づいて生成されます。 Smart Bannerで生成できるのは、OneLinkベースのリンクのみです。
5. ユーザーがSmart BannerのCTAボタンをクリックすると、クリックが送信され、AppsFlyerに記録されます。
6. ユーザーはストアにリダイレクトされ、アプリをダウンロードします。
7. ユーザーがアプリを開くと、AppsFlyerにインストールイベントが記録されます。
8. AppsFlyerは、確率論的モデリングに基づいてインストールをアトリビューションします。インストールリファラを取得できる場合は、確定的な手法でアトリビューションします。
9. `fbclid`とその他のイベントパラメータを含むポストバックが生成され、CAPIを介してMetaに送信されます。 Metaは`fbclid`パラメータで個々のクリックを識別し、その他のパラメータをキャンペーンの最適化に利用します。

</Accordion>

<div id="set-up-smart-banners-landing-page" />

<Accordion title="Smart Bannersを使用したランディングページの設定">

Smart Bannersを使用するMeta広告キャンペーンを設定するには、以下の手順に従ってください。

1. キャンペーンのOneLink計測リンクに使用するテンプレートを設定します。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレートの作成方法</Anchor>を参照してください。
2. Smart Bannerを作成します。

   <div id="note-9" />

   > 📘 **注意**
   >
   > 以下では、Smart Bannersを使用するMeta広告キャンペーンに固有の設定手順を説明します。 Smart Bannersキャンペーンの設定全般については、<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers">「Smart Banners｜モバイルWebからアプリへの誘導（マーケター向け）」</Anchor>の記事内の<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers#設定">設定セクション</Anchor>を参照してください。

3. Meta広告キャンペーン用のSmart Bannerのパラメータを設定します。
   * 必要なURLパラメータがすべて受信URLに追加されていることを確認します。特に、Smart Bannerが取得できるよう、受信URLに`pid=metaweb_int`と`fbclid`が含まれていることを確認してください。この2つのパラメータは、アトリビューションとMeta広告へのポストバック送信に必要です。受信URLに追加されたパラメータを確認するには、Meta広告マネージャを開き、遷移先URLの作成時に設定したURLパラメータを確認してください。[遷移先URLの設定](#h_01HZKNS17KT8TRD2TGDBRGKBZ3)を参照してください。

</Accordion>

<div id="view-web-to-app-attribution-data" />

## Webからアプリへのアトリビューションデータの確認

Web経由のコンバージョンイベントは、元のPIDである`metaweb_int`を使ってMetaに送信されますが、AppsFlyerのダッシュボードとローデータレポートでは、`Facebook Ads`のPIDで報告されます。これは、プライマリコンバージョンイベントと、コンバージョンをアシストしたイベントの両方に適用されます。

この統合レポートにより、Webとモバイルのコストレポート全体を含め、Webとアプリのキャンペーンのパフォーマンスを1か所で分析できます。

<div id="view-in-the-dashboard" />

### ダッシュボードでの確認

Meta経由のWebからアプリへのアトリビューションはすべて、Overview dashboardとアクティビティダッシュボードで`Facebook Ads`の下に表示されます。これにより、プラットフォームを横断したキャンペーンの成果を、1つの統合ビューで確認できます。標準のフィルターと内訳を使用して、Meta広告のデータ内でアプリとWebのトラフィックを比較できます。

<div id="view-in-raw-data-and-api-reports" />

### ローデータとAPIレポートでの確認

* MetaのWeb上のアクティビティについて、**ローデータのエクスポートとAPIレスポンス**では、`media_source`フィールドに`Facebook Ads`のPIDが含まれます。 Webキャンペーンの設定内容を確認するには、`original_url`フィールドを参照してください。Webキャンペーンの作成時に使用したPIDとして、`metaweb_int`が表示されます。
* **ポストバックレポート**には、ポストバックの送信先である元のメディアソースとして`metaweb_int`が表示されます。

<div id="traits-and-limitations" />

## 仕様と制限事項

| 項目 | 補足 |
| --- | --- |
| コスト、クリック、インプレッションのデータ | Meta広告のWebキャンペーン（`metaweb_int`）のコスト、クリック、インプレッションのデータは、Meta広告連携（`Facebook Ads`）を通じて取得できます。<ul><li>データを取得するには、必ずメインのPID（`Facebook Ads`）にアドネットワークアカウントを接続してください。<ul><li>ROI360を契約している場合：<strong>［コスト設定］</strong>ページで接続します。</li><li>ROI360を契約していない場合：<strong>［連携済みパートナー］</strong>ページの<strong>［コスト］</strong>タブで接続します。</li></ul></li><li>Meta広告のWebキャンペーンのコスト、クリック、インプレッションのデータを表示するには、計測リンクにキャンペーンID（<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_c_id">af\_c\_id</Anchor>）が含まれていることを確認してください。</li><li>アトリビューションに紐づくコスト、クリック、インプレッションのデータを最も細かい単位で表示するには、計測リンクにキャンペーンのすべての階層の情報を含める必要があります。</li></ul> |