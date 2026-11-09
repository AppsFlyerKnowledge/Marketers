---
title: Meta広告｜PC・コンソールアプリ向けWeb連携の設定
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-09-20T09:54:52Z'
  edited_at: '2026-10-28T09:16:54Z'
  id: 18704273772689
  locale: ja
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ja/articles/18704273772689
---
> **概要：** PC・コンソールアプリ向けにMeta WebとAppsFlyerを連携し、Meta Webでキャンペーンを設定する方法を説明します。

<div id="important" />

> 🚧 **重要！**
>
> この連携は、Steam、Epic、Native PCなどのPC・コンソールアプリでのみ利用できます。モバイルアプリについては、<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-integration-setup">Meta広告の連携設定</Anchor>を参照してください。

<div id="overview" />

## 概要

この記事では、AppsFlyerでPC・コンソールアプリ向けのMeta Web連携を設定し、利用する方法と手順を説明します。以下の内容が含まれます。

* [AppsFlyerでのパートナー連携の有効化](#appsflyerでのパートナーの有効化)。
* [AppsFlyerでのMeta Webの設定](#appsflyerでのmeta-webの設定)。
* [MetaでのPC・コンソールアプリ向けキャンペーンの設定](/docs/meta-ads-web-integration-setup-for-pc-and-console-apps#meta-webでのpcコンソールアプリ向けキャンペーンの設定)。

<div id="prerequisite" />

### 前提条件

Meta Web連携を有効にする前に、[Metaビジネスマネージャのビジネスアカウント](https://www.facebook.com/business/help/1710077379203657?id=180505742745347)があることを確認してください。

<div id="activating-partner-in-appsflyer" />

## AppsFlyerでのパートナーの有効化

**パートナー連携を有効にするには、以下の手順に従ってください。**

1. AppsFlyerのサイドメニューから、<strong>［連携］</strong>><strong>［パートナー連携］>［マーケットプレイス］</strong>タブに移動します。
2. **Meta Web**を検索します。
3. <strong>［連携する］</strong>をクリックします。設定ページが表示されます。
4. <strong>［連携］</strong>タブで、<strong>［パートナーを有効にする］</strong>をオンにします。  
   **注意：** このパートナーとの連携を継続する間は、トグルをオン（<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">有効</Anchor>）のままにしてください。
5. 次のセクションの説明に従い、各タブで設定を完了します。

<div id="setting-up-meta-web-in-appsflyer" />

## AppsFlyerでのMeta Webの設定

この設定では、Meta Webへのポストバックも設定できます。 Meta Web（metaweb\_int）連携では、Meta広告が提供するコンバージョンAPIを使用して、広告主の**PC・コンソールアプリ**からMetaのサーバーへ直接データを送信します。このデータには、モバイル以外のプラットフォーム（Webサイトやアプリケーション）で発生した購入、登録、その他のコンバージョンなど、ユーザーの操作が含まれます。 Meta広告は、このデータを広告ターゲティングの最適化、広告パフォーマンスの計測、リターゲティング用カスタムオーディエンスの作成に利用します。

Meta Web連携で送信できるポストバックは、インストールとアプリ内イベントのみです。

<div id="integration-tab" />

<Accordion title="連携タブ">

<strong>［連携］</strong>タブには、以下のセクションがあります。

<div id="activate-partner" />

#### パートナーの有効化

連携を設定するには、まず<strong>［パートナーを有効にする］</strong>をオンにする必要があります。

<div id="general-settings" />

#### 一般設定

* **ピクセルID：** ピクセルIDを入力します。ピクセルIDは、Meta広告マネージャで取得できます。
  1. <Anchor target="_blank" href="https://www.facebook.com/ads/manager">広告マネージャ</Anchor>のサイドメニューから、**［すべてのツール］**><strong>［イベントマネージャ］</strong>に移動します。   
     **注意：** 右上のドロップダウンで、対象のビジネスが選択されていることを確認してください。
  2. **イベントマネージャ**のサイドメニューで、<strong>［データソース］</strong>を選択します。ピクセルの一覧が表示されます。選択したビジネスのピクセルがない場合は、同じ画面から作成できます。
  3. ピクセル名の下に表示されるピクセルIDをコピーし、AppsFlyerの連携設定の［ピクセルID］欄に貼り付けます。  
     <Image align="center" alt="pixel id3.png" src="https://files.readme.io/77969160b04357d056f2eee435a61314b95225f43e03cb31dd21a80dceef0dae-20748699506193.png" width="283px" />
* **アクセストークン：** アクセストークンを入力します。取得方法は、[こちらの手順](https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token)を参照してください。
* **Meta広告によるユーザーの個人情報の利用を制限（CCPA）：** このトグルをオンにすると、<Anchor target="_blank" href="/marketers/ja/docs/send-opendsr-api-requests">データ保護法</Anchor>への対応が有効になります。  
  **注意：** CCPAのプライバシー規制に対応すると、カリフォルニア州のMeta広告ユーザーから取得するデータが制限されます。

<div id="enable-view-through-attribution" />

#### ビュースルーアトリビューションの有効化

AppsFlyerは、確率論的モデリング（PMOD）と、<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-create-web-based-campaigns#set-up-smart-script-crossplatform-landing-page">Smart Script</Anchor>または<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-create-web-based-campaigns#set-up-smart-banners-landing-page">Smart Banner</Anchor>を実装したランディングページを使用して、Meta Webキャンペーンのビュースルーアトリビューションに対応します。これにより、ユーザーが広告を閲覧した後にアプリをインストールした場合、直接クリックしていなくても、プラットフォームをまたいだインストールも含めてアトリビューションできます。

ユーザーがMeta Web広告をクリックし、<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-create-web-based-campaigns#set-up-smart-script-crossplatform-landing-page">Smart Script</Anchor>または<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-create-web-based-campaigns#set-up-smart-banners-landing-page">Smart Banner</Anchor>を実装したランディングページに到達すると、AppsFlyerは、その後に発生したアプリのインストールをアトリビューションできます。 `fbclid`を取得できる場合は、Metaへのポストバックに含めることで、アトリビューションの精度を高めます。

**ビュースルーアトリビューションを有効にするには、以下の手順に従ってください。**

1. AppsFlyerのサイドメニューから、**［連携済みパートナー］**><strong>［Meta web ads］</strong>を開きます。
2. <strong>［連携］</strong>タブで、<strong>［インストールアトリビューション］</strong>セクションまでスクロールします。
3. <strong>［インストールのビュースルーアトリビューション］</strong>をオンにします。
4. <strong>［任意］［クロスプラットフォームのアトリビューション優先度を同等にする］</strong>をオンにし、ルックバック期間を設定します。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">クロスプラットフォームのインプレッションへの同等の優先度の設定</Anchor>を参照してください。
5. <strong>［計測リンク］</strong>タブを開きます。
6. <strong>［ビュースルーアトリビューション］</strong>セクションまでスクロールし、**ビュースルールックバック期間**を設定します（最大24時間）。
7. <strong>［連携を保存］</strong>をクリックして、設定を適用します。

<div id="default-postbacks" />

#### デフォルトポストバック

インストールのポストバックは、自動的にMeta Webに送信されます。<strong>［送信対象ユーザー］</strong>欄で、以下のいずれかを選択します。

* **このパートナーのみ**：このパートナー経由のユーザーが行ったイベントについてのみ、アプリ内イベントポストバックを送信します。
* **オーガニックを含むすべてのメディアソース**：このパートナー、他のパートナー、オーガニック経由のユーザーが行ったイベントについて、アプリ内イベントポストバックを送信します。

<div id="in-app-event-postbacks" />

#### アプリ内イベントポストバック

Meta Webに送信するアプリ内イベントポストバックのマッピングを設定します。これらのイベントは、<Anchor target="_blank" href="https://www.facebook.com/business/help/1541268312717919?id=818859032317965">Metaイベントマネージャ</Anchor>で確認できます。

1. <strong>［アプリ内イベントポストバック］</strong>をオンにします。
2. <strong>［イベントを追加］</strong>をクリックして、SDKまたはサーバー間のイベントをリストに追加します。設定する項目は、以下の表のとおりです。

| パラメータ名 | 説明 |
| --- | --- |
| **AppsFlyerイベント** | アプリに実装されたSDK、またはサーバー間イベントからAppsFlyerが受信したイベント名です。<ul><li><strong>［項目を追加］</strong>をクリックし、イベント名を入力して、![check.png](https://files.readme.io/66d595d0ac8a01489ce810bbd3865fca2556342086dc6b20f26fa3d7b7e3afc2-19124971382289.png)をクリックします。</li></ul> |
| **マッピング先のパートナーイベント** | パートナー側で定義されている、各イベントの一意の名前またはIDです。<ul><li>ドロップダウンから、最適な定義済みパートナーイベントを選択するか、CUSTOMを選択します。</li></ul> |
| **送信対象ユーザー** | <ul><li>**このパートナーのみ**：このパートナー経由のユーザーが行ったイベントについてのみ、アプリ内イベントポストバックを送信します。</li><li>**オーガニックを含むすべてのメディアソース**：このパートナー、他のパートナー、オーガニック経由のユーザーが行ったイベントについて、アプリ内イベントポストバックを送信します。</li></ul> |
| **送信データ** | **イベント値と収益：** 収益値がイベントに含まれる場合、その収益値を含むすべてのイベントパラメータをポストバックで送信します。 |

3. ［任意］**［条件を追加］**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />アイコンをクリックして、イベントの<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">条件を設定します</Anchor>。
4. 必要に応じて、**アプリ内イベントポストバック期間**を設定します（詳細は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#アプリ内イベントポストバック期間">アプリ内イベントポストバック期間の設定</Anchor>を参照してください）。
5. <strong>［連携を保存］</strong>をクリックします。
6. ［任意］連携を保存した後、設定ページを開いたまま、同じパートナーに他のアプリも連携できます。
   1. 左上のパートナー名の下にあるアプリ名をクリックし、アプリの一覧を開きます。
   2. ドロップダウンリストから、別のアプリを選択します。
   3. 選択したアプリで連携手順を繰り返します。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

現在、AppsFlyerの管理画面では計測リンクを生成できません。ただし、Smart Scriptを実装したクロスプラットフォーム向けランディングページを使用するか、アプリ用の直接計測リンクを作成できます（以下の表を参照）。

| 選択肢 | 対応内容 | 担当者 |
| --- | --- | --- |
| クロスプラットフォーム向けランディングページ | **推奨**：EpicとSteamなど、複数のプラットフォームで提供するアプリのキャンペーンに適しています。<br /><br /><Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">クロスプラットフォーム向けランディングページについて</Anchor><br /><br /><Anchor target="_blank" href="/marketers/ja/docs/cross-platform-landing-pages-with-smart-script">クロスプラットフォーム向けランディングページの設定方法</Anchor><ul><li>後でSmart Scriptが取得する、必要なURLパラメータがすべて広告URLに追加されていることを確認してください。</li><li>スクリプトが受信URLからFBCLIDを取得し、生成するリンクに追加することを確認してください。つまり、送信URLのFBCLIDパラメータ`fbclid`を、受信URLのパラメータ`fbclid`にマッピングします。**注意**！ AppsFlyerのローデータレポートに表示するには、受信URLの`fbclid`パラメータを、送信URLの`af_sub[1-5]`パラメータのいずれかにもマッピングする必要があります。</li><li>任意：値を手動で直接指定する代わりに、Metaの動的URLマクロを使用できます。<Anchor target="_blank" href="https://www.facebook.com/business/help/2360940870872492">詳細はこちら</Anchor></li></ul> | マーケター（開発者の支援が必要な場合があります） |
| 直接計測リンク | 1つのプラットフォームで1つのアプリのみを提供しており、クロスプラットフォーム向けランディングページを使用しない場合は、広告に設定する直接計測リンクを作成できます。<br /><br /><Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-direct-attribution-links">直接計測リンクの作成方法</Anchor><ul><li>以下の必須パラメータが、リンクに含まれていることを確認してください。<ul><li>af\_media\_source</li><li>af\_campaign\_id</li><li>af\_r</li></ul></li></ul>Meta Web広告のリンクテンプレート：<br /><br />`https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r={encoded landing page and URL params}`<br /><br />Steamに遷移するMeta Web広告リンクの例：`https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello`<br /><br />**注意**：テンプレートには、Metaがサポートする動的URLパラメータの一部が含まれています。必要に応じて、実際の値に手動で置き換えることもできます。 <Anchor target="_blank" href="https://www.facebook.com/business/help/2360940870872492">Metaの動的URLパラメータの詳細</Anchor> | マーケター |

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

Meta Webでは、コストは利用できません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

Meta Webでは、広告収益は利用できません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

現在、Meta Webへの権限付与は行われていません。

</Accordion>

<div id="setting-up-campaigns-in-meta-web-for-pc-and-console-apps" />

## Meta WebでのPC・コンソールアプリ向けキャンペーンの設定

**新しいキャンペーンを設定する際は、以下を行ってください**。

* キャンペーンの目的を選択します。以下のいずれかを選択することを推奨します。
  * **売上**：特定のイベント（主要なKPI）に向けてMetaが最適化します。
  * **トラフィック**：広告クリックに向けてMetaが最適化します。他にKPIがない場合、または他のKPIイベントの件数が少なすぎる場合にのみ使用してください。
  * **カスタム**：カスタムイベントをキャンペーンの目的に設定する場合に選択します。**注意：** カスタムイベントをMetaのダッシュボードでキャンペーンの目的として選択できるようにするには、先にAppsFlyerでカスタムイベントを設定してください。
* コンバージョンの場所として、<strong>［Webサイト］</strong>を選択します。
* Facebookコンバージョンピクセルの名前を設定する際、AppsFlyerのパートナーマーケットプレイスでmetaweb\_intに入力したものと同じピクセルIDを指定します。
* 広告の遷移先としてWebサイトURLを入力する際は、以下のいずれかのURLを指定してください。
  * Webランディングページ（複数のプラットフォームでアプリを提供している場合に推奨）
  * ストアURL（1つのプラットフォームの1つのアプリストアでアプリを提供している場合に推奨）

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

| 項目 | 説明 |
| --- | --- |
| クリックとインプレッション（一時的な制限） | PC・コンソールアプリ向けキャンペーンのクリックとインプレッションは、現在、Meta SRN（`Facebook Ads`）から一時的に取得できません。 |

<div data-zendesk-anchors="h_01HE2XD0FSY0QMJSKVC0FHHK5P=%E9%87%8D%E8%A6%81 overview=%E6%A6%82%E8%A6%81 h_01HK4QHRJG6WTN9P6ZG83XQ6AY=%E6%A6%82%E8%A6%81 prerequisite=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01HFXV8HPGCRGYPEW0NPJ0NR0S=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 activate-partner=appsflyer%E3%81%A7%E3%81%AE%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HFXV8HPH3N4DBKKTQE6DK7FK=appsflyer%E3%81%A7%E3%81%AE%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 setting-up-metaweb-in-appsflyer=appsflyer%E3%81%A7%E3%81%AEmeta-web%E3%81%AE%E8%A8%AD%E5%AE%9A 01H88VAJH3VENKYVRQY5RXN63P=appsflyer%E3%81%A7%E3%81%AEmeta-web%E3%81%AE%E8%A8%AD%E5%AE%9A 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::1ca30957=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HFXV8HPH6X92YETNAGZ910AV=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 transaction-id=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01HARQDVEDA206D0BBXBC6WEHH=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A enable-viewthrough-attribution=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01ZXVWB1ZYKK4DP38QY1RMEY6M=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H88VAJH3WE9Z0971WMBRBJRS=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-event-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H88VAJH3AS37MVF75GANWX4B=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab setting-up-campaigns-in-meta-web-for-pc-and-console-apps=meta-web%E3%81%A7%E3%81%AEpc%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB%E3%82%A2%E3%83%97%E3%83%AA%E5%90%91%E3%81%91%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HK4S03KVAN99YKXTHAKCT420=meta-web%E3%81%A7%E3%81%AEpc%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB%E3%82%A2%E3%83%97%E3%83%AA%E5%90%91%E3%81%91%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%AD%E5%AE%9A meta%20view=web%E3%81%8B%E3%82%89%E3%82%A2%E3%83%97%E3%83%AA%E3%81%B8%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D view-webtoapp-attribution-data-from-november-2-2025=web%E3%81%8B%E3%82%89%E3%82%A2%E3%83%97%E3%83%AA%E3%81%B8%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D h_01K88J8JFNEYBZNR18133NMRP9=web%E3%81%8B%E3%82%89%E3%82%A2%E3%83%97%E3%83%AA%E3%81%B8%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D view-in-the-dashboard=%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%A7%E3%81%AE%E7%A2%BA%E8%AA%8D h_01K88J8JFNMHCVZ0C34E3D7AST=%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%A7%E3%81%AE%E7%A2%BA%E8%AA%8D view-in-raw-data-and-api-reports=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%A8api%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%A7%E3%81%AE%E7%A2%BA%E8%AA%8D h_01K88J8JFN8W2572N92466YFZQ=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%A8api%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%A7%E3%81%AE%E7%A2%BA%E8%AA%8D traits-and-limitations=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01KB503RDVWPSFBAPAPW4CNZXM=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />
