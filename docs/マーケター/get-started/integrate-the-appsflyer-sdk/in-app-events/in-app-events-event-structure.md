---
title: アプリ内イベントの構造
metadata:
  keywords:
    - iOS
    - Android
    - In-App Events
    - In-App
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:09:16Z'
  edited_at: '2026-10-29T07:44:24Z'
  id: 4410481112081
  locale: ja
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ja/articles/4410481112081
---
> **概要：** ログイン、登録、アプリ内購入など、インストール後に発生するアプリ内イベントを記録するための、定義済みイベント名とイベントパラメータの一覧を確認できます。

## 概要

アプリ内イベントを送信するには、開発者がアプリ内の該当箇所にコードを実装する必要があります。この記事では、定義済みのイベント名とイベントパラメータについて説明します。

記録するイベントやパラメータを決める際は、業種別に<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#recommended-events-by-business-vertical">推奨イベントとその発生の流れを紹介する記事</Anchor>を参照してください。

## 定義済みのイベント名

以下では、定義済みイベント名と、Meta ads、Google Ads、TikTok、Snap、X Ads、Amazon Ads、Criteo側のイベント名との対応付けを一覧で示します。

各イベント名には、関連する代表的な定義済みイベントパラメータも記載しています。ビジネス要件に合うイベントパラメータを自由に追加できます。

<div id="achievement-unlocked-af_achievement_unlocked" />

<Accordion title="実績の解除（af_achievement_unlocked）">

**説明**：実績の解除を記録します。

**イベントのマッピング：**

| AppsFlyer | af\_achievement\_unlocked |
| --- | --- |
| Meta ads | fb\_mobile\_achievement\_unlocked |
| Google Ads | unlock\_achievement |
| TikTok | UnlockAchievement |
| Snap | ACHIEVEMENT\_UNLOCKED |
| X Ads | ACHIEVEMENT\_UNLOCKED |
| Amazon Ads | - |
| Criteo | achievement |
| Roku Ads | UNLOCK\_ACHIEVEMENT |

**代表的なパラメータ：**

リンクをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="ad-click-af_ad_click" />

<Accordion title="広告クリック（af_ad_click）">

**説明**：アプリ内に表示された広告のクリックを記録するイベントです。

**イベントのマッピング**：

| AppsFlyer | af\_ad\_click |
| --- | --- |
| Meta ads | AdClick |
| Google Ads | - |
| TikTok | InAppADClick |
| Snap | AD\_CLICK |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

**代表的なパラメータ：**

各リンクをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_adrev\_ad\_type](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="ad-view-af_ad_view" />

<Accordion title="広告表示（af_ad_view）">

**説明**：アプリ内に表示された広告が閲覧されたことを記録します。

**イベントのマッピング：**

| AppsFlyer | af\_ad\_view |
| --- | --- |
| Meta ads | AdImpression |
| Google Ads | - |
| TikTok | InAppADImpr |
| Snap | AD\_VIEW |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

**代表的なパラメータ：**

各リンクをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_adrev\_ad\_type](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="支払い情報の追加（af_add_payment_info）">

**説明**：支払い情報の設定状況を記録します。

**関連する業種：** <Anchor target="_blank" href="/marketers/ja/docs/recommended-ride-hailing-app-events#add-payment-info-af_add_payment_info">配車</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-flight-booking-app-events#add-payment-info-af_add_payment_info">フライト予約</Anchor>

**イベントのマッピング**：

| AppsFlyer | af\_add\_payment\_info |
| --- | --- |
| Meta ads | fb\_mobile\_add\_payment\_info |
| Google Ads | add\_payment\_info |
| TikTok | AddPaymentInfo |
| Snap | ADD\_BILLING |
| X Ads | ADDED\_PAYMENT\_INFO |
| Amazon Ads | - |
| Criteo | ADD\_BILLING |
| Roku Ads | ADD\_PAYMENT\_INFO |

**代表的なパラメータ：**

リンクをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_success](/docs/in-app-events-event-structure#af_success)

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="カートへの追加（af_add_to_cart）">

**説明**：特定の商品をカートに追加したことを記録するイベントです。複数の商品を含むイベントを送信する方法は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">こちら</Anchor>を参照してください。

**関連する業種：** <Anchor target="_blank" href="/marketers/ja/docs/recommended-ecommerce-app-events#add-to-cart-af_add_to_cart">eコマース</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-healthcare-app-events#add-to-cart-af_add_to_cart">ヘルスケア</Anchor>

**イベントのマッピング：**

| AppsFlyer | af\_add\_to\_cart |
| --- | --- |
| Meta ads | fb\_mobile\_add\_to\_cart |
| Google Ads | add\_to\_cart |
| TikTok | AddToCart |
| Snap | ADD\_CART |
| X Ads | ADD\_TO\_CART |
| Amazon Ads | ADD\_TO\_SHOPPING\_CART |
| Criteo | viewBasket |
| Roku Ads | ADD\_TO\_CART |

**代表的なパラメータ：**

各リンクをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="ウィッシュリストへの追加（af_add_to_wishlist）">

**説明**：特定の商品をウィッシュリストに追加したことを記録するイベントです。複数の商品を含むイベントを送信する方法は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">こちら</Anchor>を参照してください。

**関連する業種：** <Anchor target="_blank" href="/marketers/ja/docs/recommended-ecommerce-app-events#add-to-wishlist-af_add_to_wishlist">eコマース</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-hotel-booking-app-events#add-to-wishlist-af_add_to_wishlist">ホテル予約</Anchor>

**イベントのマッピング：**

| AppsFlyer | af\_add\_to\_wishlist |
| --- | --- |
| Meta ads | fb\_mobile\_add\_to\_wishlist |
| Google Ads | add\_to\_wishlist |
| TikTok | AddToWishlist |
| Snap | ADD\_TO\_WISHLIST |
| X Ads | ADD\_TO\_WISHLIST |
| Amazon Ads | - |
| Criteo | - |
| Roku Ads | ADD\_TO\_WISHLIST |

**代表的なパラメータ：**

各リンクをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="app-open-af_app_opened" />

<Accordion title="アプリ起動（af_app_opened）">

Roku Adsイベントのマッピング：

| AppsFlyer | af\_app\_opened |
| --- | --- |
| Roku Ads | SESSION\_START |

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="登録完了（af_complete_registration）">

**説明**：ユーザーの登録方法を記録します。

**関連する業種：** <Anchor target="_blank" href="/marketers/ja/docs/recommended-gaming-app-events#complete-registration-af_complete_registration">ゲーム</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-ecommerce-app-events#complete-registration-af_complete_registration">eコマース</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-entertainment-app-events#complete-registration-af_complete_registration">エンターテインメント</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-finance-and-banking-app-events#complete-registration-af_complete_registration">金融・銀行</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-p2p-lending-app-events#complete-registration-af_complete_registration">P2Pレンディング</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-online-education-app-events#complete-registration-af_complete_registration">オンライン教育</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-ride-hailing-app-events#complete-registration-af_complete_registration">配車</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-hotel-booking-app-events#complete-registration-af_complete_registration">ホテル予約</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-healthcare-app-events#complete-registration-af_complete_registration">ヘルスケア</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-telecommunication-app-events#complete-registration-af_complete_registration">通信サービス</Anchor>

**イベントのマッピング：**

| AppsFlyer | af\_complete\_registration |
| --- | --- |
| Meta ads | fb\_mobile\_complete\_registration |
| Google Ads | sign\_up |
| TikTok | Registration |
| Snap | SIGN\_UP |
| X Ads | SIGN\_UP |
| Amazon Ads | SIGN\_UP |
| Criteo | - |
| Roku Ads | COMPLETE\_REGISTRATION |

**代表的なパラメータ：**

リンクをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_registration\_method](/docs/in-app-events-event-structure#af_registration_method)

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="コンテンツの閲覧（af_content_view）">

**説明**：コンテンツの閲覧を記録するイベントです。複数の商品を含むイベントを送信する方法は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">こちら</Anchor>を参照してください。

**関連する業種：** <Anchor target="_blank" href="/marketers/ja/docs/recommended-ecommerce-app-events#content-view-af_content_view">eコマース</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-flight-booking-app-events#content-view-af_content_view">フライト予約</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-hotel-booking-app-events#content-view-af_content_view">ホテル予約</Anchor>

**イベントのマッピング：**

| AppsFlyer | af\_content\_view |
| --- | --- |
| Meta ads | fb\_mobile\_content\_view |
| Google Ads | view\_item |
| TikTok | ViewContent |
| Snap | VIEW\_CONTENT |
| X Ads | CONTENT\_VIEW |
| Amazon Ads | PAGE\_VIEW |
| Criteo | viewProduct |
| Roku Ads | VIEW\_CONTENT |

**代表的なパラメータ：**

ビジネス要件に合うパラメータをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
* [af\_suggested\_hotels](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_hotel\_score](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="購入手続きの開始（af_initiated_checkout）">

**説明**：購入手続きのイベントを記録します。複数の商品を含むイベントを送信する方法は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">こちら</Anchor>を参照してください。

**関連する業種：** <Anchor target="_blank" href="/marketers/ja/docs/recommended-ecommerce-app-events#initiated-checkout-af_initiated_checkout">eコマース</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-hotel-booking-app-events#initiated-checkout-af_initiated_checkout">ホテル予約</Anchor>

**イベントのマッピング：**

| AppsFlyer | af\_initiated\_checkout |
| --- | --- |
| Meta ads | fb\_mobile\_initiated\_checkout |
| Google Ads | begin\_checkout |
| TikTok | Checkout |
| Snap | START\_CHECKOUT |
| X Ads | CHECKOUT\_INITIATED |
| Amazon Ads | CHECKOUT |
| Criteo | viewBasket |
| Roku Ads | INITIATE\_CHECKOUT |

**代表的なパラメータ：**

ビジネス要件に合うパラメータをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)
* [af\_payment\_info\_available](/docs/in-app-events-event-structure#af_payment_info_available)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
* [af\_suggested\_hotels](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_hotel\_score](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="invite-af_invite" />

<Accordion title="招待（af_invite）">

**説明**：ソーシャル機能を使った招待を記録します。

**関連する業種：** <Anchor target="_blank" href="/marketers/ja/docs/recommended-gaming-app-events#invite-af_invite">ゲーム</Anchor>

**イベントのマッピング：**

| AppsFlyer | af\_invite |
| --- | --- |
| Meta ads | - |
| Google Ads | invite |
| TikTok | - |
| Snap | INVITE |
| X Ads | INVITE |
| Amazon Ads | - |
| Criteo | - |

**代表的なパラメータ：**

リンクをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="lead-lead" />

<Accordion title="見込み顧客の獲得（lead）">

Roku Adsイベントのマッピング：

| AppsFlyer | lead |
| --- | --- |
| Roku Ads | LEAD |

</Accordion>

<div id="level-achieved-af_level_achieved" />

<Accordion title="レベル達成（af_level_achieved）">

**説明**：ゲームのレベルに関するイベントを記録します。

**関連する業種：** <Anchor target="_blank" href="/marketers/ja/docs/recommended-gaming-app-events#level-achieved-af_level_achieved">ゲーム</Anchor>

**イベントのマッピング：**

| AppsFlyer | af\_level\_achieved |
| --- | --- |
| Meta ads | fb\_mobile\_level\_achieved |
| Google Ads | level\_up |
| TikTok | AchieveLevel |
| Snap | LEVEL\_COMPLETE |
| X Ads | LEVEL\_ACHIEVED |
| Amazon Ads | - |
| Criteo | userLevel |
| Roku Ads | ACHIEVE\_LEVEL |

**代表的なパラメータ：**

各リンクをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_level](/docs/in-app-events-event-structure#af_level)
* [af\_score](/docs/in-app-events-event-structure#af_score)

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="一覧の閲覧（af_list_view）">

**説明**：一覧の閲覧イベントを記録します。

**関連する業種：** <Anchor target="_blank" href="/marketers/ja/docs/recommended-ecommerce-app-events#list-view-af_list_view">eコマース</Anchor>

**イベントのマッピング：**

| AppsFlyer | af\_list\_view |
| --- | --- |
| Meta ads | - |
| Google Ads | view\_item\_list |
| TikTok | - |
| Snap | LIST\_VIEW |
| X Ads | - |
| Amazon Ads | - |
| Criteo | viewListing |

**代表的なパラメータ：**

各リンクをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)

</Accordion>

<div id="login-af_login" />

<Accordion title="ログイン（af_login）">

**説明**：ユーザーのログインイベントを記録します。

**関連する業種：** <Anchor target="_blank" href="/marketers/ja/docs/recommended-gaming-app-events#login-af_login">ゲーム</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-ecommerce-app-events#login-af_login">eコマース</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-entertainment-app-events#login-af_login">エンターテインメント</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-finance-and-banking-app-events#login-af_login">金融・銀行</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-online-education-app-events#login-af_login">オンライン教育</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-hotel-booking-app-events#login-af_login">ホテル予約</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-healthcare-app-events#login-af_login">ヘルスケア</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-telecommunication-app-events#login-af_login">通信サービス</Anchor>

**イベントのマッピング：**

| AppsFlyer | af\_login |
| --- | --- |
| Meta ads | - |
| Google Ads | login |
| TikTok | Login |
| Snap | LOGIN |
| X Ads | LOGIN |
| Amazon Ads | - |
| Criteo | - |

</Accordion>

<div id="opened-from-push-notification-af_opened_from_push_notification" />

<Accordion title="プッシュ通知からの起動（af_opened_from_push_notification）">

**説明**：プッシュ通知からのアプリ起動を記録するイベントです。

**イベントのマッピング：**

| AppsFlyer | af\_opened\_from\_push\_notification |
| --- | --- |
| Meta ads | - |
| Google Ads | notification\_open |
| TikTok | - |
| Snap | - |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="購入（af_purchase）">

**説明**：購入を記録し、収益を紐づけるイベントです。

* AppsFlyerが対応する通貨記号の一覧は、<Anchor target="_blank" href="https://docs.openexchangerates.org/docs/supported-currencies">こちら</Anchor>を参照してください。
* 複数の商品を含むイベントを送信する方法は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">こちら</Anchor>を参照してください。
* このイベントの記録と検証については、<Anchor target="_blank" href="/marketers/ja/docs/purchase-and-subscription-validation-overview">購入とサブスクリプションの検証</Anchor>を参照してください。

**関連する業種：** <Anchor target="_blank" href="/marketers/ja/docs/recommended-gaming-app-events#purchase-af_purchase">ゲーム</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-ecommerce-app-events#purchase-af_purchase">eコマース</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-online-education-app-events#purchase-af_purchase">オンライン教育</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-healthcare-app-events#purchase-af_purchase">ヘルスケア</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-telecommunication-app-events#purchase-af_purchase">通信サービス</Anchor>

**イベントのマッピング：**

| AppsFlyer | af\_purchase |
| --- | --- |
| Meta ads | fb\_mobile\_purchase |
| Google Ads | in\_app\_purchase |
| TikTok | Purchase |
| Snap | PURCHASE |
| X Ads | PURCHASE |
| Amazon Ads | OFF\_AMAZON\_PURCHASES |
| Criteo | transactionConfirmation |
| Roku Ads | PURCHASE |

**代表的なパラメータ：**

ビジネス要件に合うパラメータをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_revenue](/docs/in-app-events-event-structure#af_revenue)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)
* [af\_validated](/docs/in-app-events-event-structure#af_validated)
* [af\_receipt\_id](/docs/in-app-events-event-structure#af_receipt_id)
* [af\_order\_id](/docs/in-app-events-event-structure#af_order_id)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
* [af\_suggested\_hotels](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_hotel\_score](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="rate-af_rate" />

<Accordion title="評価（af_rate）">

**説明**：アプリや商品の評価を記録するイベントです。複数の商品を含むイベントを送信する方法は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">こちら</Anchor>を参照してください。

**イベントのマッピング：**

| AppsFlyer | af\_rate |
| --- | --- |
| Meta ads | fb\_mobile\_rate |
| Google Ads | submit\_rating |
| TikTok | Rate |
| Snap | RATE |
| X Ads | RATED |
| Amazon Ads | - |
| Criteo | - |

**代表的なパラメータ：**

各リンクをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_rating\_value](/docs/in-app-events-event-structure#af_rating_value)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_max\_rating\_value](/docs/in-app-events-event-structure#af_max_rating_value)

</Accordion>

<div id="reengage-af_re_engage" />

<Accordion title="リエンゲージメント（af_re_engage）">

**説明**：ユーザーのリエンゲージメントイベントを記録します。

**イベントのマッピング：**

| AppsFlyer | af\_re\_engage |
| --- | --- |
| Meta ads | - |
| Google Ads | custom\_event |
| Snap | - |
| X Ads | RE\_ENGAGE |
| Amazon Ads | - |
| Criteo | - |

**代表的なパラメータ：**

リンクをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="search-af_search" />

<Accordion title="検索（af_search）">

**説明**：検索イベントを記録します。

**関連する業種：** <Anchor target="_blank" href="/marketers/ja/docs/recommended-ecommerce-app-events#search-af_search">eコマース</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-flight-booking-app-events#search-af_search">フライト予約</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-hotel-booking-app-events#search-af_search">ホテル予約</Anchor>

**イベントのマッピング：**

| AppsFlyer | af\_search |
| --- | --- |
| Meta ads | fb\_mobile\_search |
| Google Ads | view\_search\_results |
| TikTok | Search |
| Snap | SEARCH |
| X Ads | SEARCH |
| Amazon Ads | SEARCH |
| Criteo | viewSearch |
| Roku Ads | SEARCH |

**代表的なパラメータ：**

ビジネス要件に合うパラメータをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_search\_string](/docs/in-app-events-event-structure#af_search_string)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
* [af\_suggested\_hotels](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_hotel\_score](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="share-af_share" />

<Accordion title="共有（af_share）">

**説明**：共有イベントを記録します。

**関連する業種：** <Anchor target="_blank" href="/marketers/ja/docs/recommended-gaming-app-events#share-af_share">ゲーム</Anchor>

**イベントのマッピング：**

| AppsFlyer | af\_share |
| --- | --- |
| Meta ads | - |
| Google Ads | share |
| TikTok | - |
| Snap | SHARE |
| X Ads | SHARE |
| Amazon Ads | - |
| Criteo | - |

**代表的なパラメータ：**

リンクをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="spent-credits-af_spent_credits" />

<Accordion title="クレジットの使用（af_spent_credits）">

**説明**：クレジット（アプリ内のポイントなど）の使用を記録するイベントです。複数の商品を含むイベントを送信する方法は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">こちら</Anchor>を参照してください。

**関連する業種：** <Anchor target="_blank" href="/marketers/ja/docs/recommended-ride-hailing-app-events#spent-credits-af_spent_credits">配車</Anchor>

**イベントのマッピング：**

| AppsFlyer | af\_spent\_credits |
| --- | --- |
| Meta ads | fb\_mobile\_spent\_credits |
| Google Ads | spend\_virtual\_currency |
| TikTok | SpendCredits |
| Snap | SPENT\_CREDITS |
| X Ads | SPENT\_CREDITS |
| Amazon Ads | - |
| Criteo | transactionConfirmation |

**代表的なパラメータ：**

各リンクをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="start-trial-af_start_trial" />

<Accordion title="トライアル開始（af_start_trial）">

**説明**：商品の無料トライアルの開始を記録するイベントです。このイベントの記録と検証については、<Anchor target="_blank" href="/marketers/ja/docs/purchase-and-subscription-validation-overview">購入とサブスクリプションの検証</Anchor>を参照してください。

**関連する業種：** <Anchor target="_blank" href="/marketers/ja/docs/recommended-entertainment-app-events#start-trial-af_start_trial">エンターテインメント</Anchor>

**イベントのマッピング：**

| AppsFlyer | af\_start\_trial |
| --- | --- |
| Meta ads | StartTrial |
| Google Ads | - |
| TikTok | StartTrial |
| Snap | START\_TRIAL |
| X Ads | - |
| Amazon Ads | - |
| Criteo | - |
| Roku Ads | START\_TRIAL |

**代表的なパラメータ：**

各リンクをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

> 📘 **注意**
>
> このイベントをMeta adsのStartTrialイベントに対応付け、収益を紐づける場合は、af\_revenueの代わりにaf\_priceパラメータを使用してください。

</Accordion>

<div id="subscription-af_subscribe" />

<Accordion title="サブスクリプション登録（af_subscribe）">

**説明**：有料サブスクリプションの購入を記録するイベントです。このイベントの記録と検証については、<Anchor target="_blank" href="/marketers/ja/docs/purchase-and-subscription-validation-overview">購入とサブスクリプションの検証</Anchor>を参照してください。

**関連する業種：** <Anchor target="_blank" href="/marketers/ja/docs/recommended-entertainment-app-events#subscription-af_subscribe">エンターテインメント</Anchor>

**イベントのマッピング：**

| AppsFlyer | af\_subscribe |
| --- | --- |
| Meta ads | Subscribe |
| Google Ads | - |
| TikTok | Subscribe |
| Snap | SUBSCRIBE |
| X Ads | - |
| Amazon Ads | SUBSCRIBE |
| Criteo | SUBSCRIBE |
| Roku Ads | SUBSCRIBE |

**代表的なパラメータ：**

各リンクをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_revenue](/docs/in-app-events-event-structure#af_revenue)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="旅行予約（af_travel_booking）">

**説明**：旅行の予約を記録し、収益を紐づけるイベントです。複数の商品を含むイベントを送信する方法は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">こちら</Anchor>を参照してください。

**関連する業種：** <Anchor target="_blank" href="/marketers/ja/docs/recommended-flight-booking-app-events#travel-booking-af_travel_booking">フライト予約</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-hotel-booking-app-events#travel-booking-af_travel_booking">ホテル予約</Anchor>

**イベントのマッピング：**

| AppsFlyer | af\_travel\_booking |
| --- | --- |
| Meta ads | fb\_mobile\_purchase |
| Google Ads | ecommerce\_purchase |
| TikTok | Purchase |
| Snap | RESERVE |
| X Ads | PURCHASE |
| Amazon Ads | - |
| Criteo | transactionConfirmation |

**代表的なパラメータ：**

ビジネス要件に合うパラメータをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_revenue](/docs/in-app-events-event-structure#af_revenue)
* [af\_customer\_user\_id](/docs/in-app-events-event-structure#af_customer_user_id)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_class](/docs/in-app-events-event-structure#af_class)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
* [af\_suggested\_hotels](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_hotel\_score](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)
* [af\_order\_id](/docs/in-app-events-event-structure#af_order_id)

</Accordion>

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="チュートリアル完了（af_tutorial_completion）">

**説明**：チュートリアルの完了を記録するイベントです。複数の商品を含むイベントを送信する方法は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">こちら</Anchor>を参照してください。

**関連する業種：** <Anchor target="_blank" href="/marketers/ja/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">ゲーム</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">オンライン教育</Anchor>

**イベントのマッピング：**

| AppsFlyer | af\_tutorial\_completion |
| --- | --- |
| Meta ads | fb\_mobile\_tutorial\_completion |
| Google Ads | tutorial\_complete |
| TikTok | CompleteTutorial |
| Snap | COMPLETE\_TUTORIAL |
| X Ads | TUTORIAL\_COMPLETE |
| Amazon Ads | - |
| Criteo | - |

**代表的なパラメータ：**

各リンクをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="update-af_update" />

<Accordion title="更新（af_update）">

**説明**：更新を記録するイベントです。複数の商品を含むイベントを送信する方法は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">こちら</Anchor>を参照してください。

**イベントのマッピング：**

| AppsFlyer | af\_update |
| --- | --- |
| Meta ads | - |
| Google Ads | app\_update |
| Snap | - |
| X Ads | UPDATE |
| Amazon Ads | - |
| Criteo | - |

**代表的なパラメータ：**

リンクをクリックすると、SRN側のパラメータとの対応付けを確認できます。

* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)

</Accordion>

> 📘 **注意**
>
> このセクションの定義済みイベント名のほかに、<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-in-app-event-mapping#定義済みイベントのマッピング">Meta ads独自のイベント</Anchor>もあります。これらのイベントは属性を含めずに送信されます。

## 定義済みのイベントパラメータ

以下では、定義済みイベントパラメータを一覧で示します。各イベントパラメータには、Meta ads、Google Ads、Snap、X Ads、Criteo側のパラメータとの対応付けを記載しています。任意のイベントパラメータをイベントに追加できます。

> 📘 **注意**
>
> イベントパラメータは、<Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">ローデータレポート</Anchor>（有料オプション機能）のイベント値（Event Value）列で確認できます。

<div id="af_adrev_ad_type" />

<Accordion title="af_adrev_ad_type">

**説明**：広告の種類（バナーやインタースティシャルなど）

**パラメータのマッピング：**

| AppsFlyer | af\_adrev\_ad\_type |
| --- | --- |
| Meta ads | ad\_type |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_city" />

<Accordion title="af_city">

**説明**：配車を予約した都市

**パラメータのマッピング：**

| AppsFlyer | af\_city |
| --- | --- |
| Meta ads | fb\_city |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | flight\_city |
| Criteo | - |

</Accordion>

<div id="af_class" />

<Accordion title="af_class">

**説明**：予約した航空券の搭乗クラス

**パラメータのマッピング：**

| AppsFlyer | af\_class |
| --- | --- |
| Meta ads | fb\_travel\_class |
| Google Ads | travel\_class |
| Snap | - |
| X Ads | - |
| TikTok | flight\_class |
| Criteo | - |

</Accordion>

<div id="af_content" />

<Accordion title="af_content">

**説明**：コンテンツのタイトル（曲名、テレビ番組のタイトルとエピソードなど）

**パラメータのマッピング：**

| AppsFlyer | af\_content |
| --- | --- |
| Meta ads | fb\_content |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_content_id" />

<Accordion title="af_content_id">

**説明**：アイテムのID

**注意：** 定義済みのパラメータ`af_content_list`と`af_content_id`は、Snapchat側では同じイベントパラメータに対応付けられます。両方のパラメータを同じイベントに含めた場合、Snapchatに送信されるのは`af_content_list`の値のみです。

**パラメータのマッピング：**

| AppsFlyer | af\_content\_id |
| --- | --- |
| Meta ads | fb\_content\_id |
| Google Ads | item\_id |
| Snap | item\_ids |
| X Ads | content\_id |
| TikTok | content\_id |
| Criteo | id |

</Accordion>

<div id="af_content_list" />

<Accordion title="af_content_list">

**説明**：コンテンツIDの一覧

**注意：**`af_content_list`を使用すると、AppsFlyerはリスト全体を1つの値として扱います。 AppsFlyerのオーディエンス分類ツールでは、リスト内の個々のコンテンツIDを条件に絞り込むことはできません。たとえば、`af_content_list`が`["ID1","ID2","ID3"]`の場合、オーディエンス分類ツールで`ID1`だけを取り出して条件に一致するかどうかを判定することはできません。

**パラメータのマッピング：**

| AppsFlyer | af\_content\_list |
| --- | --- |
| Meta ads | fb\_content\_id |
| Google Ads | item\_id |
| Snap | item\_ids |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_content_type" />

<Accordion title="af_content_type">

**説明**：商品のカテゴリ

**パラメータのマッピング：**

| AppsFlyer | af\_content\_type |
| --- | --- |
| Meta ads | fb\_content\_type |
| Google Ads | item\_category |
| Snap | item\_category |
| X Ads | content\_type |
| TikTok | content\_type |
| Criteo | - |

</Accordion>

<div id="af_country" />

<Accordion title="af_country">

**説明**：配車を予約した国

**パラメータのマッピング：**

| AppsFlyer | af\_country |
| --- | --- |
| Meta ads | fb\_country |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | flight\_country |
| Criteo | - |

</Accordion>

<div id="af_currency" />

<Accordion title="af_currency">

**説明**：通貨コード

**パラメータのマッピング：**

| AppsFlyer | af\_currency |
| --- | --- |
| Meta ads | fb\_currency |
| Google Ads | currency\_code |
| Snap | currency |
| X Ads | price\_currency |
| TikTok | currency |
| Amazon Ads | currency |
| Criteo | currency |

</Accordion>

<div id="af_customer_user_id" />

<Accordion title="af_customer_user_id">

**説明**：顧客のID

**パラメータのマッピング：**

| AppsFlyer | af\_customer\_user\_id |
| --- | --- |
| Meta ads | - |
| Google Ads | customer\_user\_id |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | cid |

</Accordion>

<div id="af_date_a" />

<Accordion title="af_date_a">

**説明**：チェックイン日

**パラメータのマッピング：**

| AppsFlyer | af\_date\_a |
| --- | --- |
| Meta ads | fb\_checkin\_date |
| Google Ads | start\_date |
| Snap | - |
| X Ads | - |
| TikTok | checkin\_date |
| Criteo | din |

</Accordion>

<div id="af_date_b" />

<Accordion title="af_date_b">

**説明**：チェックアウト日

**パラメータのマッピング：**

| AppsFlyer | af\_date\_b |
| --- | --- |
| Meta ads | fb\_checkout\_date |
| Google Ads | end\_date |
| Snap | - |
| X Ads | - |
| TikTok | checkout\_date |
| Criteo | dout |

</Accordion>

<div id="af_departing_arrival_date" />

<Accordion title="af_departing_arrival_date">

**説明**：往路の到着日

**パラメータのマッピング：**

| AppsFlyer | af\_departing\_arrival\_date |
| --- | --- |
| Meta ads | fb\_departing\_arrival\_date |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_departing_departure_date" />

<Accordion title="af_departing_departure_date">

**説明**：往路の出発日

**パラメータのマッピング：**

| AppsFlyer | af\_departing\_ departure\_date |
| --- | --- |
| Meta ads | fb\_departing\_ departure\_date |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | departing\_date |
| Criteo | - |

</Accordion>

<div id="af_description" />

<Accordion title="af_description">

**説明**：簡単な説明（文字列）

**パラメータのマッピング：**

| AppsFlyer | af\_description |
| --- | --- |
| Meta ads | fb\_description |
| Google Ads | description |
| Snap | description |
| X Ads | description |
| TikTok | description |
| Criteo | ui\_achievement |

</Accordion>

<div id="af_destination_a" />

<Accordion title="af_destination_a">

**説明**：最初の地点（出発地など）

**パラメータのマッピング：**

| AppsFlyer | af\_destination\_a |
| --- | --- |
| Meta ads | fb\_origin\_airport |
| Google Ads | origin |
| Snap | - |
| X Ads | - |
| TikTok | departing\_airport |
| Criteo | - |

</Accordion>

<div id="af_destination_b" />

<Accordion title="af_destination_b">

**説明**：2番目の地点（到着地など）

**パラメータのマッピング：**

| AppsFlyer | af\_destination\_b |
| --- | --- |
| Meta ads | fb\_destination\_airport |
| Google Ads | destination |
| Snap | - |
| X Ads | - |
| TikTok | destination\_airport |
| Criteo | - |

</Accordion>

<div id="af_destination_list" />

<Accordion title="af_destination_list">

**説明**：目的地カタログに含まれる目的地のリスト（ホテル周辺の博物館やレストランのリストなど）

**パラメータのマッピング：**

| AppsFlyer | af\_destination\_list |
| --- | --- |
| Meta ads | fb\_destination\_ids |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_hotel_score" />

<Accordion title="af_hotel_score">

**説明**：ホテルのレビュー評価

**パラメータのマッピング：**

| AppsFlyer | af\_hotel\_score |
| --- | --- |
| Meta ads | fb\_hotel\_score |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_level" />

<Accordion title="af_level">

**説明**：ユーザーが達成したレベル

**パラメータのマッピング：**

| AppsFlyer | af\_level |
| --- | --- |
| Meta ads | fb\_level |
| Google Ads | level\_up |
| Snap | level |
| X Ads | level |
| TikTok | - |
| Criteo | ui\_level |

</Accordion>

<div id="af_max_rating_value" />

<Accordion title="af_max_rating_value">

**説明**：評価尺度の最大値（5段階評価の5など）

**パラメータのマッピング：**

| AppsFlyer | af\_max\_rating\_value |
| --- | --- |
| Meta ads | fb\_max\_rating\_value |
| Google Ads | max\_rating |
| Snap | - |
| X Ads | max\_rated\_value |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="h_01NEWAFNETREVENUE0001" />

<Accordion title="af_net_revenue">

**説明**：イベントで送信する純収益。自社のビジネスロジックに基づく純収益を表す値で、AppsFlyerは計算方法を指定せず、送信された値を集計します。代表的な例：アプリストアの手数料や税金を差し引いた収益、売上総利益、銀行やサービスの手数料を差し引いた収益（eコマース、金融など）。<Anchor target="_blank" href="/marketers/ja/docs/my-dashboards">マイダッシュボード</Anchor>の純収益ベースの指標（純収益［Net revenue］、純収益ベースのROI［Net ROI］・ROAS［Net ROAS］・ARPU［Net ARPU］、純利益［Net profit］）に使用されます。

値はaf\_currencyで指定する取引通貨で表します（デフォルトはUSD）。書式のルールはaf\_revenueと同じです。桁区切りのカンマ、通貨記号、特殊文字、テキストは含めず（例：1234.56）、小数点以下は最大5桁です。

**注意：** このパラメータには定義済みのSDK定数がないため、キーをaf\_net\_revenueとするカスタムパラメータとして送信してください。

> 📘 **注意**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-roi360-store-revenue">ROI360のストア収益</Anchor>を有効にしたアプリでは、AppsFlyerが記録するアプリ内購入とサブスクリプションのイベントに、af\_net\_revenueが自動で設定されます。総収益からアプリストアの手数料と税金を差し引いた金額です（純収益＝総収益－ストア手数料－税金）。

</Accordion>

<div id="af_num_adults" />

<Accordion title="af_num_adults">

**説明**：旅行する大人の人数

**パラメータのマッピング：**

| AppsFlyer | af\_num\_adults |
| --- | --- |
| Meta ads | fb\_num\_adults |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | num\_people |
| Criteo | - |

</Accordion>

<div id="af_num_children" />

<Accordion title="af_num_children">

**説明**：旅行する子どもの人数

パラメータのマッピング：

| AppsFlyer | af\_num\_children |
| --- | --- |
| Meta ads | fb\_num\_children |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | num\_children |
| Criteo | - |

</Accordion>

<div id="af_num_infants" />

<Accordion title="af_num_infants">

**説明**：旅行する乳児の人数

**パラメータのマッピング：**

| AppsFlyer | af\_num\_infants |
| --- | --- |
| Meta ads | fb\_num\_infants |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_order_id" />

<Accordion title="af_order_id">

**説明**：取引のID

**パラメータのマッピング：**

| AppsFlyer | af\_order\_id |
| --- | --- |
| Meta ads | fb\_order\_id |
| Google Ads | order\_id |
| Snap | transaction\_id |
| X Ads | - |
| TikTok | order\_id |
| Criteo | transaction\_id |

</Accordion>

<div id="af_payment_info_available" />

<Accordion title="af_payment_info_available">

**説明**：ユーザーの支払い情報が登録されているかどうか

**パラメータのマッピング：**

| AppsFlyer | af\_payment\_info\_available |
| --- | --- |
| Meta ads | fb\_payment\_info\_ available |
| Google Ads | payment\_info\_available |
| Snap | payment\_info\_available |
| X Ads | user\_payment\_info |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_neighborhoods" />

<Accordion title="af_preferred_neighborhoods">

**説明**：ホテルがある地域

**パラメータのマッピング：**

| AppsFlyer | af\_preferred\_neighborhoods |
| --- | --- |
| Meta ads | fb\_preferred\_neighborhoods |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_num_stops" />

<Accordion title="af_preferred_num_stops">

**説明**：ユーザーが希望する経由地の数（ノンストップ便や直行便など）

**パラメータのマッピング：**

| AppsFlyer | af\_preferred\_num\_stops |
| --- | --- |
| Meta ads | fb\_preferred\_num\_stops |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_price_range" />

<Accordion title="af_preferred_price_range">

**説明**：希望するホテルの価格帯

パラメータのマッピング：

| AppsFlyer | af\_preferred\_price\_range |
| --- | --- |
| Meta ads | fb\_preferred\_price\_range |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_star_ratings" />

<Accordion title="af_preferred_star_ratings">

**説明**：希望するホテルの星評価

**パラメータのマッピング：**

| AppsFlyer | af\_preferred\_star\_ratings |
| --- | --- |
| Meta ads | fb\_preferred\_star\_ratings |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_price" />

<Accordion title="af_price">

**説明**：商品の価格。 af\_priceは、収益に計上しない金額を送信するパラメータとして使用できます（カートへの追加イベントなど）。このパラメータは、個々の商品の価格を示します。購入全体の合計金額は、[af\_revenue](/docs/in-app-events-event-structure#af_revenue)パラメータで示します。

**パラメータのマッピング：**

| AppsFlyer | af\_price |
| --- | --- |
| Meta ads | fb\_price |
| Google Ads | price |
| Snap | price |
| X Ads | price\_micro |
| TikTok | price |
| Criteo | price |

</Accordion>

<div id="af_projected_revenue" />

<Accordion title="af_projected_revenue">

実際の収益が発生する前に、ユーザーの初期の操作や行動に基づいて、広告主がそのユーザーから得られると予測した収益です。

</Accordion>

<div id="af_quantity" />

<Accordion title="af_quantity">

**説明**：アイテム数

**パラメータのマッピング：**

| AppsFlyer | af\_quantity |
| --- | --- |
| Meta ads | fb\_num\_items |
| Google Ads | quantity |
| Snap | number\_items |
| X Ads | number\_items |
| TikTok | quantity |
| Criteo | quantity |

</Accordion>

<div id="af_rating_value" />

<Accordion title="af_rating_value">

**説明**：選択した評価値

**パラメータのマッピング：**

| AppsFlyer | af\_rating\_value |
| --- | --- |
| Meta ads | \_valueToSum |
| Google Ads | value |
| Snap | - |
| X Ads | price\_micro |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_receipt_id" />

<Accordion title="af_receipt_id">

**説明**：レシートのID

**パラメータのマッピング：**

| AppsFlyer | af\_receipt\_id |
| --- | --- |
| Meta ads | - |
| Google Ads | transaction\_id |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | transaction\_id |

</Accordion>

<div id="af_region" />

<Accordion title="af_region">

**説明**：配車を予約した地域

**パラメータのマッピング：**

| AppsFlyer | af\_region |
| --- | --- |
| Meta ads | fb\_region |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | flight\_region |
| Criteo | - |

</Accordion>

<div id="af_registration_method" />

<Accordion title="af_registration_method">

**説明**：登録方法の種類

**パラメータのマッピング：**

| AppsFlyer | af\_registration\_method |
| --- | --- |
| Meta ads | fb\_registration\_method |
| Google Ads | registration\_method |
| Snap | sign\_up\_method |
| X Ads | registration\_method |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_returning_arrival_date" />

<Accordion title="af_returning_arrival_date">

**説明**：復路の到着日時

**パラメータのマッピング：**

| AppsFlyer | af\_returning\_arrival\_ date |
| --- | --- |
| Meta ads | fb\_returning\_arrival\_ date |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_returning_departure_date" />

<Accordion title="af_returning_departure_date">

**説明**：復路の出発日時

**パラメータのマッピング：**

| AppsFlyer | af\_returning\_departure\_date |
| --- | --- |
| Meta ads | fb\_returning\_departure\_date |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | returning\_date |
| Criteo | - |

</Accordion>

<div id="af_revenue" />

<Accordion title="af_revenue">

**説明**：購入の合計金額。 af\_revenueで送信した金額は、AppsFlyerプラットフォームで収益として計上されます。キャンセルや返金による<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">マイナスの収益</Anchor>も計上します。

> 🚧 **重要**
>
> 収益値に桁区切りのカンマ、通貨、特殊文字、テキストを含めないでください。たとえば、収益値は1234.56のように指定します。 AppsFlyerは、収益値を小数点以下最大5桁の精度で提供します。

収益パラメータの使用方法については、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">こちら</Anchor>を参照してください。

**純収益：** 総収益とともに純収益も送信する場合は、[af\_net\_revenue](/docs/in-app-events-event-structure#h_01NEWAFNETREVENUE0001)をカスタムイベントパラメータとして送信します。純収益の算出方法は、自社のビジネスに合わせて定義します（ストア手数料や税金を差し引いた収益、売上総利益、サービス手数料を差し引いた収益など）。 ROI360のストア収益を有効にしたアプリでは、記録された購入とサブスクリプションのイベントに、総収益からアプリストアの手数料と税金を差し引いた値が自動で設定されます。

**パラメータのマッピング：**

| AppsFlyer | af\_revenue |
| --- | --- |
| Meta ads | \_valueToSum |
| Google Ads | value |
| Snap | price |
| X Ads | price\_micro |
| TikTok | value |
| Amazon Ads | eventValue |
| Criteo | ui\_revenue |

</Accordion>

<div id="af_score" />

<Accordion title="af_score">

**説明**：ユーザーの実績に対するスコア

**パラメータのマッピング：**

| AppsFlyer | af\_score |
| --- | --- |
| Meta ads | - |
| Google Ads | - |
| Snap | - |
| X Ads | score |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_search_string" />

<Accordion title="af_search_string">

**説明**：検索語句

**パラメータのマッピング：**

| AppsFlyer | af\_search\_string |
| --- | --- |
| Meta ads | fb\_search\_string |
| Google Ads | search\_string |
| Snap | search\_string |
| X Ads | search\_string |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_subscription_id" />

<Accordion title="af_subscription_id">

**説明**：ユーザーのサブスクリプションID

**パラメータのマッピング：**

| AppsFlyer | af\_subscription\_id |
| --- | --- |
| Meta ads | subscription\_id |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_success" />

<Accordion title="af_success">

**説明**：操作が正常に完了したかどうか

**パラメータのマッピング：**

| AppsFlyer | af\_success |
| --- | --- |
| Meta ads | fb\_success |
| Google Ads | success |
| Snap | success |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_suggested_destinations" />

<Accordion title="af_suggested_destinations">

**説明**：提案された目的地の一覧

**パラメータのマッピング：**

| AppsFlyer | af\_suggested\_ destinations |
| --- | --- |
| Meta ads | fb\_suggested\_ destinations |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_suggested_hotels" />

<Accordion title="af_suggested_hotels">

**説明**：提案されたホテルの一覧

**パラメータのマッピング：**

| AppsFlyer | af\_suggested\_ hotels |
| --- | --- |
| Meta ads | fb\_suggested\_hotels |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_travel_end" />

<Accordion title="af_travel_end">

**説明**：旅行の終了日

**パラメータのマッピング：**

| AppsFlyer | af\_travel\_end |
| --- | --- |
| Meta ads | fb\_travel\_end |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_travel_start" />

<Accordion title="af_travel_start">

**説明**：旅行の開始日

**パラメータのマッピング：**

| AppsFlyer | af\_travel\_start |
| --- | --- |
| Meta ads | fb\_travel\_start |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_user_score" />

<Accordion title="af_user_score">

**説明**：広告主にとってのユーザーの相対的な重要度

**パラメータのマッピング：**

| AppsFlyer | af\_user\_score |
| --- | --- |
| Meta ads | fb\_user\_score |
| Google Ads | - |
| Snap | - |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

<div id="af_validated" />

<Accordion title="af_validated">

**説明**：購入の検証結果

**パラメータのマッピング：**

| AppsFlyer | af\_validated |
| --- | --- |
| Meta ads | - |
| Google Ads | validated |
| Snap | success |
| X Ads | - |
| TikTok | - |
| Criteo | - |

</Accordion>

以下は、SRNとの対応付けを含まない定義済みイベントパラメータの一覧です。

* af\_achievement\_id
* af\_coupon\_code
* af\_customer\_segment
* af\_deep\_link
* af\_event\_end
* af\_event\_start
* af\_lat
* af\_long
* af\_new\_version
* af\_old\_version
* af\_param\_1
* af\_param\_2
* af\_param\_3
* af\_param\_4
* af\_param\_5
* af\_param\_6
* af\_param\_7
* af\_param\_8
* af\_param\_9
* af\_param\_10
* af\_review\_text
* af\_tutorial\_id
* af\_virtual\_currency\_name
* af\_duration\_seconds

> 📄 **関連情報**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration">アプリ内イベントのポストバック設定</Anchor>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01H9HT8C713A4NV9WCB0FJZJ4R=%E6%A6%82%E8%A6%81 predefined-event-names=%E5%AE%9A%E7%BE%A9%E6%B8%88%E3%81%BF%E3%81%AE%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E5%90%8D h_01H9HT8C7189W1JXAR3J3KT8KV=%E5%AE%9A%E7%BE%A9%E6%B8%88%E3%81%BF%E3%81%AE%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E5%90%8D h_01H9HT8C71MV7V7C75MB6ESHMM=achievement-unlocked-af_achievement_unlocked h_01H9HT8C7171PB7KAC83MYBWQ8=ad-click-af_ad_click h_01H9HT8C72KJ6ZA663SH7HJ7MP=ad-view-af_ad_view h_01H9HT8C72HSM88DJG0PDV5140=add-payment-info-af_add_payment_info h_01H9HT8C72BWFSPKWDVQW926WG=add-to-cart-af_add_to_cart h_01H9HT8C7228B57XKAACPZG8NK=add-to-wishlist-af_add_to_wishlist h_01K0PJ4C3HP9DMJT1DFZ848WF0=app-open-af_app_opened h_01H9HT8C72DX0DXBDHRJFG19G2=complete-registration-af_complete_registration h_01H9HT8C72SPY9VQ9AD648AKZK=content-view-af_content_view h_01H9HT8C722T2VH6A9257Q7T4P=initiated-checkout-af_initiated_checkout h_01H9HT8C72F0RZ4JS9929SE465=invite-af_invite h_01K0PJ4C3H72BDTRH7WAYW4V7S=lead-lead h_01H9HT8C72VFGC08Q858EX7XTN=level-achieved-af_level_achieved h_01H9HT8C72DZW77YTQ9KB0XEVG=list-view-af_list_view h_01H9HT8C720W10QEBCTPAGMRFB=login-af_login h_01H9HT8C72QC4WV10Z4JZTZM7D=opened-from-push-notification-af_opened_from_push_notification h_01H9HT8C7263J0YSX5K10R497N=purchase-af_purchase h_01H9HT8C73MPYMG8KSYE04DKDZ=rate-af_rate h_01H9HT8C734DAC6GPJE58DB5JD=reengage-af_re_engage h_01H9HT8C73YSYBK0YSDPRWDBNW=search-af_search h_01H9HT8C734GJ07V67QC9V3TVC=share-af_share h_01H9HT8C73H4VT2M0P3M1SYG88=spent-credits-af_spent_credits h_01H9HT8C73YWDCKAZPY0BVRS6F=start-trial-af_start_trial h_01H9HT8C736BF2VNRCFSJSVXWS=%E6%B3%A8%E6%84%8F h_01H9HT8C73N69S45H82NWQ5FN1=subscription-af_subscribe h_01H9HT8C73CD6HNT5GA6B4CHQ9=travel-booking-af_travel_booking h_01H9HT8C73NFDPS1P5AVXXZEX7=tutorial-completion-af_tutorial_completion h_01H9HT8C73JPH6Q9XFKA3GNYT8=update-af_update h_01H9HT8C74SGGK2FW92JH4BJPZ=%E6%B3%A8%E6%84%8F-1 predefined-event-parameters=%E5%AE%9A%E7%BE%A9%E6%B8%88%E3%81%BF%E3%81%AE%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_01H9HT8C74N4TJZ5ZVBTKAX810=%E5%AE%9A%E7%BE%A9%E6%B8%88%E3%81%BF%E3%81%AE%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_01H9HT8C74VQ9ZWF079V50E5HE=%E6%B3%A8%E6%84%8F-2 h_01H9HT8C74Y0BWS565DFTY75KJ=af_adrev_ad_type h_01H9HT8C742NHGXFKWSS4P07K2=af_city h_01H9HT8C7442PFZEK7QC6R0K67=af_class h_01H9HT8C7462KG3030WWZ2XGZW=af_content h_01H9HT8C74ZX07907NXFHKGJ91=af_content_id h_01H9HT8C744CMWSYHJB74JFSS5=af_content_list h_01H9HT8C74GKGG5V4X54BCAADC=af_content_type h_01H9HT8C74RD08Z9EBZTKY5KSD=af_country h_01H9HT8C75BJYK4R3WYSN4BF43=af_currency h_01H9HT8C752E2PK6QKTA2GNGH5=af_customer_user_id h_01H9HT8C75BN0A92X9BRY4A74T=af_date_a h_01H9HT8C75406KV9264ZZT9DKM=af_date_b h_01H9HT8C7526AEHJAA7FM7442E=af_departing_arrival_date h_01H9HT8C75W9X61ZH0849EPDBY=af_departing_departure_date h_01H9HT8C75VEV3C8CJBDN6X5HW=af_description h_01H9HT8C75Z8TBZEPEY9EGSR4Y=af_destination_a h_01H9HT8C751G216VB6GYTPEPE1=af_destination_b h_01H9HT8C75CVM0MHSKTK2CZ8HD=af_destination_list h_01H9HT8C75CVVDFABSTN5R4MWT=af_hotel_score h_01H9HT8C75GEMHE2NHEFK9J7NT=af_level h_01H9HT8C7505H4CMY70EMDQWSF=af_max_rating_value af_net_revenue=h_01NEWAFNETREVENUE0001 h_01NEWAFNETREVENUENOTE0001=%E6%B3%A8%E6%84%8F-3 h_01H9HT8C75ST9XBDC3SR6XFDPB=af_num_adults h_01H9HT8C75NNZ5NP6PRPXDSKP8=af_num_children h_01H9HT8C757X70AAGNWFV0CKRY=af_num_infants h_01H9HT8C75A0HESE5FD10VD1P8=af_order_id h_01H9HT8C75B488VKY8SW9M4GG4=af_payment_info_available h_01H9HT8C75W7SRB0KF4E5FB2YF=af_preferred_neighborhoods h_01H9HT8C75GC61D1A0P6P42TMR=af_preferred_num_stops h_01H9HT8C76XRY6CD1TJEPCJJTR=af_preferred_price_range h_01H9HT8C76Y9ZQQ2X4EJT2DC14=af_preferred_star_ratings h_01H9HT8C76KCDRJKBWSM9JKFE1=af_price 01J9XHWVFHXPN6N3EZF1P8XWYM=af_projected_revenue h_01H9HT8C76Y5VXBKF3TBVVJG1C=af_quantity h_01H9HT8C768WXZ126Q425PHDWX=af_rating_value h_01H9HT8C76XX9J6FZ6RWQB6B6R=af_receipt_id h_01H9HT8C760S0F7QZMFYW1BKRD=af_region h_01H9HT8C76N4S3SGES5SQ2J4AC=af_registration_method h_01H9HT8C76ZR36A4CM2PY6PJ10=af_returning_arrival_date h_01H9HT8C760JPVXYC5WH9ZSDPX=af_returning_departure_date h_01H9HT8C76PYB14WPCQKSEK69J=af_revenue h_01H9HT8C762BGPRHFX228APEHR=%E9%87%8D%E8%A6%81 h_01H9HT8C76P55HN8K6D7PHFS2J=af_score h_01H9HT8C76TB4KNTZVD6JVPEYQ=af_search_string h_01H9HT8C762R2PJ573W8TJFJHG=af_subscription_id h_01H9HT8C76VZ6FA20K471V0EKK=af_success h_01H9HT8C76029H94AY5EHCZX6X=af_suggested_destinations h_01H9HT8C76N6C694TCPVCK4EC3=af_suggested_hotels h_01H9HT8C765EM1SAEJ67FNXZDE=af_travel_end h_01H9HT8C76YP8VEM5E6WB9NQ7T=af_travel_start h_01H9HT8C771SYQWQ8VBTPA2V2E=af_user_score h_01H9HT8C771XFSQJX42QVBNZAJ=af_validated h_01HDNZ30NH2QXSHD7B4EMFG4T5=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />
