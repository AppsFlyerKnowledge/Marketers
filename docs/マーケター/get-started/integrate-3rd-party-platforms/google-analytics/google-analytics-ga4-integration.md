---
title: Google Analytics（GA4）との連携
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2024-06-06T15:26:00Z'
  edited_at: '2026-10-28T09:04:16Z'
  id: 25707682812561
  locale: ja
  section: Google Analytics
  section_id: 6551226043793
  url: https://support.appsflyer.com/hc/ja/articles/25707682812561
---
> **At a glance:** AppsFlyerとGoogle Analytics（GA4）を連携すると、AppsFlyerのアトリビューションデータと、選択したアプリ内イベントをGA4に送信できます。この連携は、[Google Analytics for Firebase SDK](https://firebase.google.com/docs/analytics)をすでに実装しているiOSアプリとAndroidアプリで利用できます。

> 🚧 **Important**
>
> **重要**
>
> この連携は、[Google Analytics for Firebase SDKをすでに実装しているiOS](https://firebase.google.com/docs/analytics)アプリとAndroidアプリで利用できます。連携を正しく動作させるには、AppsFlyer SDKでFirebase SDKの`app_instance_id`の値を収集する必要があります。 [Firebase SDKからアプリインスタンスIDを取得する方法](#5-retrieve-app-instance-id-in-appsflyer-sdk)を確認してください。

<div id="how-does-it-work" />

## 連携の仕組み

* 新規インストールが発生すると、AppsFlyerはタッチポイントの詳細（メディアソース、キャンペーン名、キャンペーンID）をGA4に送信します。さらに、Firebase SDKの`app_instance_id`も送信し、そのユーザーのタッチポイントとしてGA4に記録されるようにします。
* アプリ内イベントが発生すると、GA4は最後のタッチポイントにそのイベントを紐付けます。

<div id="set-up-google-analytics-ga4-integration" />

## Google Analytics（GA4）連携の設定

以下の手順でGoogle Analytics（GA4）との連携を設定します。

<Accordion title="1. パートナーマーケットプレイスでGoogle Analytics（GA4）を選択する">

**前提条件：** 連携の設定を始める前に、<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーに問い合わせて</Anchor>アカウントを作成してください。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。  
   （**既存の連携を編集する場合：** ［**連携＞パートナー連携＞有効な連携**］タブに移動します。）
2. 対象のアプリを選択します。
3. Google Analytics（GA4）を検索し、<strong>［連携する］</strong>を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。   
   注意：Google Analytics（GA4）と連携している間は、**オン（有効）のままにしてください**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳細を見る</Anchor>
5. 以下の説明に従い、該当するタブで設定を完了します。

Google Analyticsの設定で使用するのは、<strong>［連携］</strong>タブのみです。

パートナー設定画面のヘッダーについて詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>を参照してください。

</Accordion>

<Accordion title="2. AppsFlyerでのGA4連携の設定">

次の項目を設定します。

1. <strong>［連携］</strong>タブで連携するアプリを選択し、<strong>［パートナーを有効化］</strong>をオンにします。

   **注意：** このパートナーと連携している間は、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">オン（有効）</Anchor>のままにしてください。

   パートナーの有効化について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>を参照してください。
2. **Firebase App ID**に、Firebaseアプリの識別子を入力します。 Firebase App IDの確認方法は、<Anchor target="_blank" href="https://firebase.google.com/support/faq#find-app-id">Firebaseのドキュメント</Anchor>を参照してください。
3. **API Secret**に、Google Analyticsへのポストバックの認証に使用するAPIシークレットを入力します。 APIシークレットは、Google Analyticsの画面から生成します。シークレットの表示、編集、作成については、<Anchor target="_blank" href="https://support.google.com/analytics/answer/9814495?sjid=5179426966283787649-EU">Googleのドキュメント</Anchor>の手順に従ってください。 **Webデータストリームを選択するよう記載されている手順では、代わりにAndroidまたはiOSのデータストリームを選択してください。**
4. 広告ID（IDFA）の代わりにカスタマーユーザーID（CUID）を送信するには、<strong>［カスタマーユーザーID］</strong>をオンにします。
5. <strong>［デフォルトポストバック］</strong>セクションの<strong>［対象ユーザーの流入元］</strong>で、<strong>［オーガニックを含むすべてのメディアソース］</strong>を選択します。

> 📘 **Note**
>
> **注意**
>
> インストールポストバックには、タッチポイントの詳細（メディアソース、キャンペーン名、キャンペーンID）のみが含まれます。

</Accordion>

<Accordion title="3. デフォルトポストバックの設定">

AppsFlyerは、ユーザーのインストール後にGA4へポストバックを自動送信できます。インストールとリエンゲージメント（リアトリビューションを含む）が対象です。リエンゲージメントとは、すでにアプリをインストールしているユーザーが、キャンペーンリンクをクリックした後にアプリを開くことです。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#default-postbacks">デフォルトポストバック</Anchor>を参照してください。

</Accordion>

<Accordion title="4. アプリ内イベントポストバックの設定">

<strong>［連携］</strong>タブで、ポストバックで送信するAppsFlyerのアプリ内イベントをGoogle Analytics（GA4）のイベントに対応付けます。

> 📘 **Note**
>
> **注意**
>
> * S2Sで送信されたモバイルのアプリ内イベントのポストバックには対応していません。
> * GA4では、Firebase SDKとAppsFlyerの両方から送信されたイベントの重複は排除されません。 Firebase SDK経由ですでにGA4に送信しているイベントには、アプリ内イベントポストバックを設定しないことを推奨します。

1. ［**アプリ内イベントポストバック**］をオンにします。
2. <strong>［イベントを追加］</strong>をクリックし、SDKイベントをリストに追加します。設定するフィールドを以下の表で説明します。

| パラメータ名 | 説明 |
| --- | --- |
| **AppsFlyerイベント** | アプリに組み込んだAppsFlyer SDKから受信したイベント名です。<br /><br />**ヒント**：目的のイベントが表示されない場合は、<ul><li>非オーガニックインストールのデバイスで対象イベントを発生させてから、もう一度確認してください。</li><li><strong>［AppsFlyerイベント］</strong>に名前を入力し、<strong>［カスタムイベントを作成］</strong>をクリックします。</li></ul>詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">カスタムイベントのマッピング</Anchor>を参照してください。 |
| **パートナー側のイベント名／ID** | パートナー側で定義されている各イベントの一意の名前またはIDです。次の方法で対応付けることができます。<ul><li>**テキストフィールド：** 対応するイベントIDをパートナーから取得します。</li><li>**ドロップダウン：** 最も適切なAppsFlyerの定義済みイベントを選択します。</li><li>**そのまま**：名前を対応付けず、イベントをそのまま送信します。</li></ul> |
| **対象ユーザーの流入元** | イベントの送信対象を選択します。<ul><li>**オーガニックを含むすべてのメディアソース**：すべてのパートナーのイベントとオーガニックイベントのポストバックを送信します。</li></ul> |
| **送信するデータ** | <ul><li>**データなし（デフォルト）**：イベント値を含めず、イベントそのものだけを送信します。</li><li>**値と収益を送信する**：収益値を**含む**すべてのイベントパラメータを送信します（イベントに収益値がある場合）。</li><li>**値のみ送信し、収益は送信しない**：収益値を**除く**すべてのパラメータを送信します。</li></ul> |

3. ［任意］<strong>［条件を追加］</strong>アイコン（<Image alt="condition-2.png" src="https://files.readme.io/959329be2b1286507b5c87b033785e91ab135592ae37cf3200539400832490c0-25709762755857.png" width="19px" />）をクリックし、イベントの<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">条件を設定</Anchor>します。
4. ［**連携を保存**］をクリックします。
5. イベントポストバックのマッピングの共有

</Accordion>

<Accordion title="5. 開発者へのポストバックイベントのマッピングの共有">

アプリ内イベントのマッピングを設定したら、対応付けたイベントを1行ずつ記載し、次の列を含む表を開発者に共有します。

* **AF event：** AppsFlyerのイベント名。
* **Mapped to Google event：** Google Analyticsのイベント名。

> 🚧 **Important**
>
> **重要**
>
> Google Analyticsのカスタムイベント名に、[Googleの予約済みイベント名](#googleの予約済みイベント名)を使用しないでください。

* **AF event parameters（必須）：** Google Analyticsに送信するイベントポストバックに必ず含める、AppsFlyerの定義済みイベントパラメータ。

> 🚧 **Important**
>
> **重要**
>
> イベントの定義には、表に記載されている定義済みのAFイベントパラメータをすべて、記載どおりに含める必要があります。不足や相違があると、Google Analyticsがポストバックを拒否します。

<div id="the-event-mapping-table" />

#### イベントマッピング表

次の表には、Google Analyticsのすべてのイベントと、対応するAppsFlyerの定義済みパラメータが記載されています。対応付けたイベントのみを含む表を、開発者に共有してください。

| AppsFlyerの推奨名（任意） | Google広告のイベント名 | AppsFlyerの定義済みイベントパラメータ（必須） |
| --- | --- | --- |
| af\_add\_payment\_info | [add\_payment\_info](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_payment_info) | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [add\_shipping\_info](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_shipping_info) | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
| af\_add\_to\_cart | [add\_to\_cart](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_to_cart) | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
| af\_add\_to\_wishlist | [add\_to\_wishlist](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_to_wishlist) | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
| af\_initiated\_checkout | [begin\_checkout](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#begin_checkout) | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [campaign\_details](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#campaign_details) | キャンペーンID、キャンペーン名 |
| af\_spent\_credits | [earn\_virtual\_currency](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#earn_virtual_currency) | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |
|  | [generate\_lead](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#generate_lead) | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>,<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |
|  | [join\_group](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#join_group) |  |
| af\_level\_achieved | [level\_up](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#level_up) |  |
| af\_login | [login](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#login) |  |
|  | [post\_score](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#post_score) | af\_user\_score |
| af\_purchase | [purchase](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#purchase) | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content">af\_content</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_receipt_id">af\_receipt\_id</Anchor> |
|  | [refund](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#refund) | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content">af\_content</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_receipt_id">af\_receipt\_id</Anchor> |
|  | [remove\_from\_cart](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#remove_from_cart) | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [screen\_view](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#screen_view) |  |
| af\_search | [search](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#search) |  |
|  | [select\_content](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_content) |  |
|  | [select\_item](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_item) | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [select\_promotion](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_promotion) | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [share](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#share) |  |
|  | [sign\_up](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#sign_up) |  |
|  | [spend\_virtual\_currency](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#spend_virtual_currency) | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |
|  | [tutorial\_begin](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#tutorial_begin) |  |
| af\_tutorial\_completion | [tutorial\_complete](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#tutorial_complete) |  |
| af\_achievement\_unlocked | [Unlock\_achievement](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#unlock_achievement) | af\_achievement\_id |
|  | [view\_cart](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_cart) | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_item](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_item) | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_item\_list](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_item_list) | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_promotion](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_promotion) | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_search\_results](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_search_results) |  |
| af\_ad\_view | [ad\_impression](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#ad_impression) | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |

<div id="reserved-google-event-names" />

#### Googleの予約済みイベント名

次のイベント名は予約済みのため、カスタムイベント名には使用できません。

* `ad_activeview`
* `ad_click`
* `ad_exposure`
* `ad_query`
* `ad_reward`
* `adunit_exposure`
* `app_clear_data`
* `app_exception`
* `app_install`
* `app_remove`
* `app_store_refund`
* `app_update`
* `app_upgrade`
* `dynamic_link_app_open`
* `dynamic_link_app_update`
* `dynamic_link_first_open`
* `error`
* `firebase_campaign`
* `firebase_in_app_message_action`
* `firebase_in_app_message_dismiss`
* `firebase_in_app_message_impression`
* `first_open`
* `first_visit`
* `in_app_purchase`
* `notification_dismiss`
* `notification_foreground`
* `notification_open`
* `notification_receive`
* `notification_send`
* `os_update`
* `session_start`
* `user_engagement`

</Accordion>

<Accordion title="6. AppsFlyer SDKでのアプリインスタンスIDの取得">

`app_instance_id`はFirebaseアプリのインストールを、`ga_session_id`はFirebaseアプリのセッションを、それぞれ一意に識別します。これらの値をFirebase SDKから取得し、`setAdditionalData` APIを使ってGA4に送信します。

開発者に、以下の処理を実装するよう依頼します。

1. Firebaseから`app_instance_id`と`ga_session_id`のフィールドを取得します。
2. 初回起動前に`setAdditionalData`を呼び出し、インストール、セッション、アプリ内イベントにアプリインスタンスIDと`ga_session_id`を含めます。

> 🚧 **Important**
>
> **重要**
>
> `setAdditionalData`（Android／Unity／React Native）と`customData`（iOS）は、**キーと値の組み合わせをまとめたマッピング**を受け取ります。両方の値が含まれるように、`app_instance_id`と`ga_session_id`を**同じマッピングにまとめて送信します**。**別々の**`setAdditionalData`呼び出しで送信すると、後の呼び出しで先の値が上書きされます。

<Tabs>
<Tab title="Android native">

**Kotlin**

```kotlin
FirebaseAnalytics.getInstance(this).appInstanceId.addOnCompleteListener { task ->
   if (task.isSuccessful) {
       AppsFlyerLib.getInstance().setAdditionalData("app_instance_id", task.result)
    }
}
```

**Java**

```java
FirebaseAnalytics.getInstance(this).getAppInstanceId().addOnCompleteListener(task -> {
       if (task.isSuccessful()) {
           AppsFlyerLib.getInstance().setAdditionalData("app_instance_id", task.getResult());
       }
  });
```

APIリファレンス：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">setAdditionalData</Anchor>

</Tab>

<Tab title="iOS native">

**iOS native**

```swift
let appInstanceId = Analytics.appInstanceID()
    AppsFlyerLib.shared().customData = ["app_instance_id": appInstanceId]
```

**Objective C**

```objectivec
(void) fetchAnalyticsInstanceId {
           NSString *instanceID = [FIRAnalytics appInstanceID];
           [[AppsFlyerLib shared] setAdditionalData:@{@"app_instance_id": instanceID}];
}
```

APIリファレンス：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata">customData</Anchor>

</Tab>

<Tab title="Unity">

```csharp
using Firebase.Analytics;
    public class AnalyticsManager : MonoBehaviour
    {
        private async void Start()
        {
           AppsFlyer.initSDK(devKey, appID, this);
           string appInstanceId = await FirebaseAnalytics.GetAnalyticsInstanceIdAsync();
           Dictionary <string, string> customData = new Dictionary<string, string>();
           customData.Add("app_instance_id", appInstanceId);
           AppsFlyer.setAdditionalData(appInstanceId);
           AppsFlyer.startSDK();
        }
}
```

APIリファレンス：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setadditionaldata">setAdditionalData</Anchor>

</Tab>

<Tab title="React native">

APIリファレンス：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setadditionaldata">setAdditionalData</Anchor>

</Tab>
</Tabs>

</Accordion>

<Accordion title="7. AppsFlyer SDKでのGA4セッションIDの取得">

`ga_session_id`は、Firebaseアプリのセッションを一意に識別します。この値をFirebase SDKから取得し、`setAdditionalData` APIを使ってGA4に送信する必要があります。

開発者に、以下の処理を実装するよう依頼します。

1. Firebaseから`ga_session_id`フィールドを取得します。
2. 初回起動前に`setAdditionalData`を呼び出し、セッションIDと、使用する場合は`app_instance_id`を含めます。
3. APIの呼び出し時には、キーとして`ga_session_id`を使用します。

> 🚧 **Important**
>
> **重要**
>
> `setAdditionalData`（Android／Unity／React Native）と`customData`（iOS）は、**キーと値の組み合わせをまとめたマッピング**を受け取ります。アプリから`app_instance_id`と`ga_session_id`の両方を送信する場合（[手順5](#5-retrieve-app-instance-id-in-appsflyer-sdk)を参照）は、両方の値が含まれるように、**同じマッピングにまとめて送信してください**。**別々の**`setAdditionalData`呼び出しで送信すると、後の呼び出しで先の値が上書きされます。

<Tabs>
<Tab title="Android native">

**Kotlin**

```kotlin
FirebaseAnalytics.getInstance(this).sessionId.addOnCompleteListener { task ->
    if (task.isSuccessful) {
        AppsFlyerLib.getInstance().setAdditionalData("ga_session_id", task.result)
    }
}
```

**Java**

```java
FirebaseAnalytics.getInstance(this).getSessionId().addOnCompleteListener(task -> {
    if (task.isSuccessful()) {
        AppsFlyerLib.getInstance().setAdditionalData("ga_session_id", task.getResult());
    }
});
```

APIリファレンス：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">setAdditionalData</Anchor>

</Tab>

<Tab title="iOS native">

**Swift**

```swift
if #available(iOS 14.0, *) {
    Analytics.sessionID { sessionID, error in
        if let sessionID = sessionID {
            AppsFlyerLib.shared().customData = ["ga_session_id": sessionID]
        }
    }
}
```

**Objective-C**

```objectivec
- (void)fetchAnalyticsSessionId {
    if (@available(iOS 14.0, *)) {
        [FIRAnalytics sessionIDWithCompletion:^(NSString * _Nullable sessionID, NSError * _Nullable error) {
            if (sessionID) {
                [[AppsFlyerLib shared] setAdditionalData:@{@"ga_session_id": sessionID}];
            }
        }];
    }
}
```

APIリファレンス：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata">customData</Anchor>

</Tab>

<Tab title="Unity">

```csharp
using Firebase.Analytics;
using System.Threading.Tasks;
using AppsFlyerSDK;
using UnityEngine;
using System.Collections.Generic;

public class AnalyticsManager : MonoBehaviour
{
    private async void Start()
    {
        AppsFlyer.initSDK("yourDevKey", "yourAppID", this);

        // Get session ID
        string sessionId = await FirebaseAnalytics.GetSessionIdAsync();

        Dictionary<string, string> customData = new Dictionary<string, string>();
        customData.Add("ga_session_id", sessionId);
        AppsFlyer.setAdditionalData(customData);

        AppsFlyer.startSDK();
    }
}
```

APIリファレンス：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setadditionaldata">setAdditionalData</Anchor>

</Tab>
</Tabs>

</Accordion>

<Accordion title="8. GA4連携の検証">

GA4に送信するポストバックのイベントが、Google Analyticsに登録され、認識されていることを確認します。広告主がデータを確認する方法は、2つあります。

* [GA4の探索](https://support.google.com/analytics/answer/7579450?hl=en&ref_topic=12153537,12153943,2986333,&sjid=20462331341270448-EU&visit_id=638532662145815538-1056226594&rd=1#access-analysis&zippy=%2Cin-this-article)では、関連するすべてのパラメータを含む、イベントのローデータを詳しく確認できます。**前提条件：** プロパティで[BigQueryエクスポート](https://support.google.com/analytics/answer/9823238)を設定していること。
* **イベントレポート**では、ポストバックのイベントを確認できます。このレポートは、1つ以上のレポートコレクションに含まれています。  
  たとえば、[ライフサイクル](https://support.google.com/analytics/answer/12924233?hl=en)または[ゲームレポート](https://support.google.com/analytics/answer/12925133?hl=en&sjid=5454549956257318969-NC)コレクションの、**エンゲージメント**＞**イベント**からアクセスできます。   
  イベントレポートの詳細は、[Googleのドキュメント](https://support.google.com/analytics/answer/12926615?sjid=5454549956257318969-NC)を参照してください。

  <Image align="center" alt="GA4のイベントレポート" src="https://files.readme.io/01625878b13a46b8a87c34bf465c0ef6494a0f528960d62ce5535b69b29e7d0a-25707728713745.png" />
* **トラフィック獲得レポート**では、Webサイトやアプリの訪問者の流入元を把握できます。

  [ライフサイクルコレクション](https://support.google.com/analytics/answer/12924233?hl=en)で、**集客**＞**トラフィック獲得**に移動します。

  トラフィック獲得レポートの詳細は、[Googleのドキュメント](https://support.google.com/analytics/answer/12923437?hl=en&sjid=5454549956257318969-NC#zippy=%2Chow-do-i-filter-out-traffic-sources-from-the-report)を参照してください。

  <Image align="center" alt="GA4のトラフィック獲得レポート" src="https://files.readme.io/fa51e22d1a7941666224eb668efcbfc5a3bb8cce42cf373a82f3b1e096d2a9db-25707770926353.png" />

</Accordion>

<div data-zendesk-anchors="set-up-google-analytics-ga4-integration=%E9%80%A3%E6%90%BA%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF h_01HZXY8R12MQWKNHX2BXA68MR3=%E9%80%A3%E6%90%BA%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF h_01J35AP3FF599P0XA8VPWTS5R9=google-analyticsga4%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A the-event-mapping-table=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E8%A1%A8 h_01HZQ4ABBN0YEVFJXBNS0HTSQ5=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E8%A1%A8 reserved-google-event-names=google%E3%81%AE%E4%BA%88%E7%B4%84%E6%B8%88%E3%81%BF%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E5%90%8D h_01HZQ4ABBN6ZEB7RJQMFS0AB73=google%E3%81%AE%E4%BA%88%E7%B4%84%E6%B8%88%E3%81%BF%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E5%90%8D" />
