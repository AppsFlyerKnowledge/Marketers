---
title: 应用内事件 — 事件结构
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
  edited_at: '2026-10-14T10:02:36Z'
  id: 4410481112081
  locale: zh-cn
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/zh-cn/articles/4410481112081
---
> **概要：** 本文列出了广告主可以选择的预定义事件名称和参数，用于记录激活后的应用内事件（如登录、注册、应用内购买等）。

## 速览

您的开发人员需要在应用中的相关位置添加代码后您才能发送对应的应用内事件。本文对各种预定义事件名称和及其对应参数做了详细说明。

如果您不确定需要记录哪些事件和参数，请参考我们按垂类梳理的<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#recommended-events-by-business-vertical">推荐事件（含示例和流程）</Anchor>。

## 预定义事件名称

下表列出了用于Meta ads、Google Ads、TikTok、Snap、X Ads和Criteo的预定义事件名称和事件映射。

每个事件名称都包含了与该事件有关的常用预定义事件参数。您可根据自己的业务需求，选择任何适用的事件参数。

<div id="achievement-unlocked-af_achievement_unlocked" />

<Accordion title="成就解锁（af_achievement_unlocked）">

**说明**: 用于记录成就解锁事件

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_achievement\_unlocked | fb\_mobile\_achievement\_unlocked | unlock\_achievement | UnlockAchievement | ACHIEVEMENT\_UNLOCKED | ACHIEVEMENT\_UNLOCKED | - | achievement |

**常用参数：**

点击链接查看对SRN的映射。

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="ad-click-af_ad_click" />

<Accordion title="广告点击（af_ad_click）">

**说明**: 用于记录应用中的广告点击和广告展示

**事件映射**：

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_ad\_click | AdClick | - | InAppADClick | AD\_CLICK | - | - | - |

**常用参数：**

请点击以下链接，查看各SRN的映射事件。

* [af\_adrev\_ad\_type](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="ad-view-af_ad_view" />

<Accordion title="广告浏览（af_ad_view）">

**说明**: 用于记录应用中展示广告的观看

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_ad\_view | AdImpression | - | InAppADImpr | AD\_VIEW | - | - | - |

**常用参数：**

请点击以下链接，查看各SRN的映射事件。

* [af\_adrev\_ad\_type](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="添加付款信息（af_add_payment_info）">

**说明**: 用于记录付款信息配置状态

**常见于以下垂类：** <Anchor target="_blank" href="/marketers/zh/docs/recommended-ride-hailing-app-events#add-payment-info-af_add_payment_info">打车</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-flight-booking-app-events#add-payment-info-af_add_payment_info">机票预订</Anchor>

**事件映射**：

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_add\_payment\_info | fb\_mobile\_add\_payment\_info | add\_payment\_info | AddPaymentInfo | ADD\_BILLING | ADDED\_PAYMENT\_INFO | - | ADD\_BILLING |

**常用参数：**

点击链接查看对SRN的映射。

* [af\_success](/docs/in-app-events-event-structure#af_success)

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="添加到购物车（af_add_to_cart）">

**说明**: 用于记录具体商品的加购事件。如需在单个事件中包含多件商品，请点击<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">此处</Anchor>查看指南。

**常见于以下垂类：** <Anchor target="_blank" href="/marketers/zh/docs/recommended-ecommerce-app-events#add-to-cart-af_add_to_cart">电商</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-healthcare-app-events#add-to-cart-af_add_to_cart">医疗</Anchor>

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_add\_to\_cart | fb\_mobile\_add\_to\_cart | add\_to\_cart | AddToCart | ADD\_CART | ADD\_TO\_CART | ADD\_TO\_SHOPPING\_CART | viewBasket |

**常用参数：**

请点击以下链接，查看各SRN的映射事件。

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="添加到种草清单（af_add_to_wishlist）">

**说明**: 用于记录具体商品的种草清单收藏事件。如需在单个事件中包含多件商品，请点击<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">此处</Anchor>查看指南。

**常见于以下垂类：** <Anchor target="_blank" href="/marketers/zh/docs/recommended-ecommerce-app-events#add-to-wishlist-af_add_to_wishlist">电商</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-hotel-booking-app-events#add-to-wishlist-af_add_to_wishlist">酒店预订</Anchor>

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_add\_to\_wishlist | fb\_mobile\_add\_to\_wishlist | add\_to\_wishlist | AddToWishlist | ADD\_TO\_WISHLIST | ADD\_TO\_WISHLIST | - | - |

**常用参数：**

请点击以下链接，查看各SRN的映射事件。

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="完成注册（af_complete_registration）">

**说明**: 用于记录用户的注册方式

**常见于以下垂类：** <Anchor target="_blank" href="/marketers/zh/docs/recommended-gaming-app-events#complete-registration-af_complete_registration">游戏</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-ecommerce-app-events#complete-registration-af_complete_registration">电商</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-entertainment-app-events#complete-registration-af_complete_registration">娱乐</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-finance-and-banking-app-events#complete-registration-af_complete_registration">金融与银行服务</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-p2p-lending-app-events#complete-registration-af_complete_registration">P2P贷款</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-online-education-app-events#complete-registration-af_complete_registration">在线教育</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-ride-hailing-app-events#complete-registration-af_complete_registration">打车</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-hotel-booking-app-events#complete-registration-af_complete_registration">酒店预订</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-healthcare-app-events#complete-registration-af_complete_registration">医疗</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-telecommunication-app-events#complete-registration-af_complete_registration">电信</Anchor>

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_complete\_registration | fb\_mobile\_complete\_registration | sign\_up | Registration | SIGN\_UP | SIGN\_UP | SIGN\_UP | - |

**常用参数：**

点击链接查看对SRN的映射。

* [af\_registration\_method](/docs/in-app-events-event-structure#af_registration_method)

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="内容浏览（af_content_view）">

**说明**: 用于记录内容浏览事件。如需在单个事件中包含多件商品，请点击<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">此处</Anchor>查看指南。

**常见于以下垂类：** <Anchor target="_blank" href="/marketers/zh/docs/recommended-ecommerce-app-events#content-view-af_content_view">电商</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-flight-booking-app-events#content-view-af_content_view">机票预订</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-hotel-booking-app-events#content-view-af_content_view">酒店预订</Anchor>

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_content\_view | fb\_mobile\_content\_view | view\_item | ViewContent | VIEW\_CONTENT | CONTENT\_VIEW | PAGE\_VIEW | viewProduct |

**常用参数：**

点击与您的业务需求相关的参数，查看这些参数在各SRN中的对应字段。

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
* [af\_purchase\_currency](/docs/in-app-events-event-structure#af_purchase_currency)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="发起结帐（af_initiated_checkout）">

**说明**: 用于记录结账事件。如需在单个事件中包含多件商品，请点击<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">此处</Anchor>查看指南。

**常见于以下垂类：** <Anchor target="_blank" href="/marketers/zh/docs/recommended-ecommerce-app-events#initiated-checkout-af_initiated_checkout">电商</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-hotel-booking-app-events#initiated-checkout-af_initiated_checkout">酒店预订</Anchor>

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_initiated\_checkout | fb\_mobile\_initiated\_checkout | begin\_checkout | Checkout | START\_CHECKOUT | CHECKOUT\_INITIATED | CHECKOUT | viewBasket |

**常用参数：**

点击与您的业务需求相关的参数，查看这些参数在各SRN中的对应字段。

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
* [af\_purchase\_currency](/docs/in-app-events-event-structure#af_purchase_currency)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="invite-af_invite" />

<Accordion title="邀请（af_invite）">

**说明**: 用于记录邀请 (社交) 事件

**常见于以下垂类：** <Anchor target="_blank" href="/marketers/zh/docs/recommended-gaming-app-events#invite-af_invite">游戏</Anchor>

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_invite | - | invite | - | INVITE | INVITE | - | - |

**常用参数：**

点击链接查看对SRN的映射。

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="level-achieved-af_level_achieved" />

<Accordion title="通关级别(af_level_achieved)">

**说明**: 用于记录游戏等级事件

**常见于以下垂类：** <Anchor target="_blank" href="/marketers/zh/docs/recommended-gaming-app-events#level-achieved-af_level_achieved">游戏</Anchor>

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_level\_achieved | fb\_mobile\_level\_achieved | level\_up | AchieveLevel | LEVEL\_COMPLETE | LEVEL\_ACHIEVED | - | userLevel |

**常用参数：**

请点击以下链接，查看各SRN的映射事件。

* [af\_level](/docs/in-app-events-event-structure#af_level)
* [af\_score](/docs/in-app-events-event-structure#af_score)

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="列表浏览（af_list_view）">

**说明**: 用于记录浏览列表事件

**常见于以下垂类：** <Anchor target="_blank" href="/marketers/zh/docs/recommended-ecommerce-app-events#list-view-af_list_view">电商</Anchor>

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_list\_view | - | view\_item\_list | - | LIST\_VIEW | - | - | viewListing |

**常用参数：**

请点击以下链接，查看各SRN的映射事件。

* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)

</Accordion>

<div id="login-af_login" />

<Accordion title="登录（af_login）">

**说明**: 用于记录用户登录事件

**常见于以下垂类：** <Anchor target="_blank" href="/marketers/zh/docs/recommended-gaming-app-events#login-af_login">游戏</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-ecommerce-app-events#login-af_login">电商</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-entertainment-app-events#login-af_login">娱乐</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-finance-and-banking-app-events#login-af_login">金融与银行服务</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-online-education-app-events#login-af_login">在线教育</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-hotel-booking-app-events#login-af_login">酒店预订</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-healthcare-app-events#login-af_login">医疗</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-telecommunication-app-events#login-af_login">电信</Anchor>

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_login | - | login | Login | LOGIN | LOGIN | - | - |

</Accordion>

<div id="opened-from-push-notification-af_opened_from_push_notification" />

<Accordion title="从推送消息打开应用（af_opened_from_push_notification）">

**说明**: 用于记录从推送通知打开应用的事件

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_opened\_from\_push\_notification | - | notification\_open | - | - | - | - | - |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="购买（af_purchase）">

**说明**: 用于记录购买事件 (并将收入关联到这些事件)请点击<Anchor target="_blank" href="https://docs.openexchangerates.org/docs/supported-currencies">此处</Anchor>查看AppsFlyer支持的货币符号列表。如需在单个事件中包含多件商品，请点击<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">此处</Anchor>查看指南。

**常见于以下垂类**：<Anchor target="_blank" href="/marketers/zh/docs/recommended-gaming-app-events#purchase-af_purchase">游戏</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-ecommerce-app-events#purchase-af_purchase">电商</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-online-education-app-events#purchase-af_purchase">在线教育</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-healthcare-app-events#purchase-af_purchase">医疗</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-telecommunication-app-events#purchase-af_purchase">电信</Anchor>

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_purchase | fb\_mobile\_purchase | in\_app\_purchase | Purchase | PURCHASE | PURCHASE | OFF\_AMAZON\_PURCHASES | transactionConfirmation |

**常用参数：**

点击与您的业务需求相关的参数，查看这些参数在各SRN中的对应字段。

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
* [af\_purchase\_currency](/docs/in-app-events-event-structure#af_purchase_currency)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="rate-af_rate" />

<Accordion title="评分（af_rate）">

**说明**: 用于记录应用/商品的评价事件。如需在单个事件中包含多件商品，请点击<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">此处</Anchor>查看指南。

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_rate | fb\_mobile\_rate | submit\_rating | Rate | Rate | RATED | - | - |

**常用参数：**

请点击以下链接，查看各SRN的映射事件。

* [af\_rating\_value](/docs/in-app-events-event-structure#af_rating_value)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_max\_rating\_value](/docs/in-app-events-event-structure#af_max_rating_value)

</Accordion>

<div id="reengage-af_re_engage" />

<Accordion title="再互动（af_re_engage）">

**说明**: 用于记录用户再互动事件

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_re\_engage | - | custom\_event | - | RE\_ENGAGE | - | - |

**常用参数：**

点击链接查看对SRN的映射。

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="search-af_search" />

<Accordion title="搜索（af_search）">

**说明**: 用于记录搜索事件

**常见于以下垂类：** <Anchor target="_blank" href="/marketers/zh/docs/recommended-ecommerce-app-events#search-af_search">电商</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-flight-booking-app-events#search-af_search">机票预订</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-hotel-booking-app-events#search-af_search">酒店预订</Anchor>

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_search | fb\_mobile\_search | view\_search\_results | Search | SEARCH | SEARCH | SEARCH | viewSearch |

**常用参数：**

点击与您的业务需求相关的参数，查看这些参数在各SRN中的对应字段。

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
* [af\_purchase\_currency](/docs/in-app-events-event-structure#af_purchase_currency)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="share-af_share" />

<Accordion title="分享（af_share）">

**说明**: 用于记录分享事件

**常见于以下垂类：** <Anchor target="_blank" href="/marketers/zh/docs/recommended-gaming-app-events#share-af_share">游戏</Anchor>

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_share | - | share | - | SHARE | SHARE | - | - |

**常用参数：**

点击链接查看对SRN的映射。

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="spent-credits-af_spent_credits" />

<Accordion title="积分消费（af_spent_credits）">

**说明**: 用于记录虚拟币/积分支出事件如需在单个事件中包含多件商品，请点击<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">此处</Anchor>查看指南。

**常见于以下垂类：** <Anchor target="_blank" href="/marketers/zh/docs/recommended-ride-hailing-app-events#spent-credits-af_spent_credits">打车</Anchor>

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_spent\_credits | fb\_mobile\_spent\_credits | spend\_virtual\_currency | SpendCredits | SPENT\_CREDITS | SPENT\_CREDITS | - | transactionConfirmation |

**常用参数：**

请点击以下链接，查看各SRN的映射事件。

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="start-trial-af_start_trial" />

<Accordion title="开始试用（af_start_trial）">

**说明**: 用于记录产品免费试用的开始

**常见于以下垂类：** <Anchor target="_blank" href="/marketers/zh/docs/recommended-entertainment-app-events#start-trial-af_start_trial">娱乐</Anchor>

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_start\_trial | StartTrial | - | StartTrial | START\_TRIAL | - | - | - |

**常用参数：**

请点击以下链接，查看各SRN的映射事件。

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

> 📘 **注意**
>
> 如果您要让这个事件对应到Meta ads的StartTrial（开始试用）事件，并关联收入，请把参数设为af\_price，而不是af\_revenue。

</Accordion>

<div id="subscription-af_subscribe" />

<Accordion title="订阅（af_subscribe）">

**说明**: 用于记录付费订阅购买

**常见于以下垂类：** <Anchor target="_blank" href="/marketers/zh/docs/recommended-entertainment-app-events#subscription-af_subscribe">娱乐</Anchor>

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_subscribe | Subscribe | - | Subscribe | SUBSCRIBE | - | SUBSCRIBE | SUBSCRIBE |

**常用参数：**

请点击以下链接，查看各SRN的映射事件。

* [af\_revenue](/docs/in-app-events-event-structure#af_revenue)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="行程预订（af_travel_booking）">

**说明**: 用于记录行程预定事件（并将收入关联到这些事件）。如需在单个事件中包含多件商品，请点击<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">此处</Anchor>查看指南。

**常见于以下垂类：** <Anchor target="_blank" href="/marketers/zh/docs/recommended-flight-booking-app-events#travel-booking-af_travel_booking">机票预订</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-hotel-booking-app-events#travel-booking-af_travel_booking">酒店预订</Anchor>

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_travel\_booking | fb\_mobile\_purchase | ecommerce\_purchase | Purchase | RESERVE | PURCHASE | - | transactionConfirmation |

**常用参数：**

点击与您的业务需求相关的参数，查看这些参数在各SRN中的对应字段。

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
* [af\_purchase\_currency](/docs/in-app-events-event-structure#af_purchase_currency)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)
* [af\_order\_id](/docs/in-app-events-event-structure#af_order_id)

</Accordion>

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="完成新手教学（af_tutorial_completion）">

**说明**: 用于记录用户完成新手教学。如需在单个事件中包含多件商品，请点击<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">此处</Anchor>查看指南。

**常见于以下垂类：** <Anchor target="_blank" href="/marketers/zh/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">游戏</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">在线教育</Anchor>

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | TikTok | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_tutorial\_completion | fb\_mobile\_tutorial\_completion | tutorial\_complete | CompleteTutorial | COMPLETE\_TUTORIAL | TUTORIAL\_COMPLETE | - | - |

**常用参数：**

请点击以下链接，查看各SRN的映射事件。

* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="update-af_update" />

<Accordion title="更新（af_update）">

**说明**: 用于记录更新事件。如需在单个事件中包含多件商品，请点击<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">此处</Anchor>查看指南。

**事件映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_update | - | app\_update | - | UPDATE | - | - |

**常用参数：**

点击链接查看对SRN的映射。

* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)

</Accordion>

> 📘 **注意**
>
> 除了本章中提到的预定义事件名称以外，<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-in-app-event-mapping#预定义事件的映射">Meta ads还提供额外的预定义事件选项</Anchor> ，这些事件是不能设置参数的。

## 预定义事件参数

本章为您列举了预定义事件参数，并针对每个事件参数都列出了Meta ads、Google Ads、Snap、X Ads和Criteo的相应字段，用于事件映射。您可以在一个事件中添加任意事件参数。

> 📘 **注意**
>
> 您可以在<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">原始数据报告</Anchor>（高阶付费功能）的“Event Value”（事件值）一列查看事件参数。

<div id="af_adrev_ad_type" />

<Accordion title="af_adrev_ad_type">

**说明**: 广告类型（如横幅或插屏广告）

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_adrev\_ad\_type | ad\_type | - | - | - | - | - |

</Accordion>

<div id="af_city" />

<Accordion title="af_city">

**说明**: 预订乘车的城市

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_city | fb\_city | - | - | - | flight\_city | - |

</Accordion>

<div id="af_class" />

<Accordion title="af_class">

**说明**: 预订的机票舱位

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_class | fb\_travel\_class | travel\_class | - | - | flight\_class | - |

</Accordion>

<div id="af_content" />

<Accordion title="af_content">

**说明**: 内容标题（如歌曲名称或电视节目名称和剧集标题）

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_content | fb\_content | - | - | - | - | - |

</Accordion>

<div id="af_content_id" />

<Accordion title="af_content_id">

**说明**: 相关商品的ID

**请注意：** 对于预定义事件`af_content_list`和`af_content_id`，Snapchat侧只有一个对应的事件。同时记录到两个事件时，AppsFlyer仅向Snapchat发送`af_content_list`事件。

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_content\_id | fb\_content\_id | item\_id | item\_ids | content\_id | content\_id | id |

</Accordion>

<div id="af_content_list" />

<Accordion title="af_content_list">

**说明**: 内容ID列表

**请注意：** 对于预定义事件`af_content_list`和`af_content_id`，Snapchat侧只有一个对应的事件。同时记录到两个事件时，AppsFlyer仅向Snapchat发送`af_content_list`事件。

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_content\_list | - | item\_id | item\_ids | - | - | - |

</Accordion>

<div id="af_content_type" />

<Accordion title="af_content_type">

**说明**: 产品类别

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_content\_type | fb\_content\_type | item\_category | item\_category | content\_type | content\_type | - |

</Accordion>

<div id="af_country" />

<Accordion title="af_country">

**说明**: 预订乘车的国家

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_country | fb\_country | - | - | - | flight\_country | - |

</Accordion>

<div id="af_currency" />

<Accordion title="af_currency">

**说明**: 货币代码

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_currency | fb\_currency | currency\_code | currency | price\_currency | currency | currency | currency |

</Accordion>

<div id="af_customer_user_id" />

<Accordion title="af_customer_user_id">

**说明**: 客户用户ID（即CUID）

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_customer\_user\_id | - | customer\_user\_  <br />id | - | - | - | cid |

</Accordion>

<div id="af_date_a" />

<Accordion title="af_date_a">

**说明**: 入住日期

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_date\_a | fb\_checkin\_date | start\_date | - | - | checkin\_date | din |

</Accordion>

<div id="af_date_b" />

<Accordion title="af_date_b">

**说明**: 退房日期

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_date\_b | fb\_checkout\_date | end\_date | - | - | checkout\_date | dout |

</Accordion>

<div id="af_departing_arrival_date" />

<Accordion title="af_departing_arrival_date">

**说明**: 到达日期

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_departing\_arrival\_date | fb\_departing\_arrival\_date | - | - | - | - | - |

</Accordion>

<div id="af_departing_departure_date" />

<Accordion title="af_departing_departure_date">

**说明**: 出发日期

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_departing\_departure\_date | fb\_departing\_ departure\_date | - | - | - | departing\_date | - |

</Accordion>

<div id="af_description" />

<Accordion title="af_description">

**说明**: 简要描述（字符串）

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_description | fb\_description | description | description | description | description | ui\_achievement |

</Accordion>

<div id="af_destination_a" />

<Accordion title="af_destination_a">

**说明**: 第一个目的地

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_destination\_a | fb\_origin\_airport | origin | - | - | departing\_airport | - |

</Accordion>

<div id="af_destination_b" />

<Accordion title="af_destination_b">

**说明**: 第二个目的地

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_destination\_b | fb\_destination\_  <br />airport | destination | - | - | destination\_airport | - |

</Accordion>

<div id="af_destination_list" />

<Accordion title="af_destination_list">

**说明**: 包含在目的地类别中的目的地列表（如酒店附近的博物馆或餐厅列表）

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_destination\_list | fb\_destination\_ids | - | - | - | - | - |

</Accordion>

<div id="af_hotel_score" />

<Accordion title="af_hotel_score">

**说明**: 用户评价中对酒店的评分

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_hotel\_score | fb\_hotel\_score | - | - | - | - | - |

</Accordion>

<div id="af_level" />

<Accordion title="af_level">

**说明**: 用户达到的等级

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_level | fb\_level | level\_up | level | level | - | ui\_level |

</Accordion>

<div id="af_max_rating_value" />

<Accordion title="af_max_rating_value">

**说明**: 评分较高（如5星好评）

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_max\_rating\_value | fb\_max\_rating\_value | max\_rating | - | max\_rated\_value | - | - |

</Accordion>

<div id="af_num_adults" />

<Accordion title="af_num_adults">

**说明**: 成人旅客人数

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_num\_adults | fb\_num\_adults | - | - | - | num\_people | - |

</Accordion>

<div id="af_num_children" />

<Accordion title="af_num_children">

**说明**: 儿童旅客人数

参数映射：

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_num\_children | fb\_num\_children | - | - | - | num\_children | - |

</Accordion>

<div id="af_num_infants" />

<Accordion title="af_num_infants">

**说明**: 婴儿旅客人数

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_num\_infants | fb\_num\_infants | - | - | - | - | - |

</Accordion>

<div id="af_order_id" />

<Accordion title="af_order_id">

**说明**: 相关交易的ID

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_order\_id | fb\_order\_id | order\_id | transaction\_id | - | order\_id | transaction\_id |

</Accordion>

<div id="af_payment_info_available" />

<Accordion title="af_payment_info_available">

**说明**: 用户的付款信息是否可用

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_payment\_info\_available | fb\_payment\_info\_ available | payment\_info\_  <br />available | PAYMENT\_INFO\_AVAILABLE | user\_payment\_  <br />info | - | - |

</Accordion>

<div id="af_preferred_neighborhoods" />

<Accordion title="af_preferred_neighborhoods">

**说明**: 酒店所在的区域

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_preferred\_neighborhoods | fb\_preferred\_neighborhoods | - | - | - | - | - |

</Accordion>

<div id="af_preferred_num_stops" />

<Accordion title="af_preferred_num_stops">

**说明**: 用户想要的经停站点数量（如直飞航班）

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_preferred\_num\_stops | fb\_preferred\_num\_stops | - | - | - | - | - |

</Accordion>

<div id="af_preferred_price_range" />

<Accordion title="af_preferred_price_range">

**说明**: 用户首选的酒店价位

参数映射：

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_preferred\_price\_range | fb\_preferred\_price\_range | - | - | - | - | - |

</Accordion>

<div id="af_preferred_star_ratings" />

<Accordion title="af_preferred_star_ratings">

**说明**: 用户首选的酒店星级

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_preferred\_star\_ratings | fb\_preferred\_star\_ratings | - | - | - | - | - |

</Accordion>

<div id="af_price" />

<Accordion title="af_price">

**说明**: 产品价格。您可以使用af\_price作为货币参数，将其与加购等计入收入的事件区分开。该参数代表商品单价，而[af\_revenue](/docs/in-app-events-event-structure#af_revenue)参数则显示所有订单金额的总和。

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_price | fb\_price | price | price | price\_micro | price | price |

</Accordion>

<div id="af_projected_revenue" />

<Accordion title="af_projected_revenue">

在相关用户产生实际收入前，广告主根据其早前的互动或行为模式预计的收入金额。如需进一步了解预计收入的相关信息，请参考<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#projected-revenue">此文档</Anchor>。

</Accordion>

<div id="af_purchase_currency" />

<Accordion title="af_purchase_currency">

**说明**: 购买时支付的货币

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_purchase\_currency | fb\_purchase\_currency | - | - | - | - | - |

</Accordion>

<div id="af_quantity" />

<Accordion title="af_quantity">

**说明**: 商品数量

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_quantity | fb\_num\_items | quantity | number\_items | number\_items | quantity | quantity |

</Accordion>

<div id="af_rating_value" />

<Accordion title="af_rating_value">

**说明**: 用户评分的分值

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_rating\_value | \_valueToSum | value | - | price\_micro | - | - |

</Accordion>

<div id="af_receipt_id" />

<Accordion title="af_receipt_id">

**说明**: 相关收据的ID

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_receipt\_id | - | transaction\_id | - | - | - | transaction\_id |

</Accordion>

<div id="af_region" />

<Accordion title="af_region">

**说明**: 预订乘车的地区

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_region | fb\_region | - | - | - | flight\_region | - |

</Accordion>

<div id="af_registration_method" />

<Accordion title="af_registration_method">

**说明**: 注册方式的类型

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_registration\_method | fb\_registration\_method | registration\_method | sign\_up\_method | registration\_method | - | - |

</Accordion>

<div id="af_returning_arrival_date" />

<Accordion title="af_returning_arrival_date">

**说明**: 回程结束的日期和时间

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_returning\_arrival\_date | fb\_returning\_arrival\_ date | - | - | - | - | - |

</Accordion>

<div id="af_returning_departure_date" />

<Accordion title="af_returning_departure_date">

**说明**:  回程开始的日期和时间

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_returning\_departure\_date | fb\_returning\_departure\_date | - | - | - | returning\_date | - |

</Accordion>

<div id="af_revenue" />

<Accordion title="af_revenue">

**说明**: 购买事件的总体金额。在AppsFlyer平台中，af\_revenue是记录收入的参数。该参数也能统计取消订单或退款等事件造成的<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#revenue-events">负收入</Anchor>。

> 🚧 **重要提示！**
>
> 收入值中不能包含逗号分隔符、货币、特殊字符或文字。比如1234.56就是一个有效的收入值。AppsFlyer能支持精确到小数点后五位的收入值。

请点击<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#revenue-events">这里</Anchor>查看收入参数的使用方法。

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Amazon Ads | Criteo |
| --- | --- | --- | --- | --- | --- | --- | --- |
| af\_revenue | \_valueToSum | value | price | price\_micro | value | Event value | ui\_revenue |

</Accordion>

<div id="af_score" />

<Accordion title="af_score">

**说明**: 与用户成就相关的分数

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_score | - | - | - | score | - | - |

</Accordion>

<div id="af_search_string" />

<Accordion title="af_search_string">

**说明**: 搜索词

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_search\_string | fb\_search\_string | search\_string | search\_string | search\_string | - | - |

</Accordion>

<div id="af_subscription_id" />

<Accordion title="af_subscription_id">

**说明**: 用户的订阅ID

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_subscription\_id | subscription\_id | - | - | - | - | - |

</Accordion>

<div id="af_success" />

<Accordion title="af_success">

**说明**: 是否成功完成操作

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_success | fb\_success | success | success | - | - | - |

</Accordion>

<div id="af_suggested_destinations" />

<Accordion title="af_suggested_destinations">

**说明**: 推荐的目的地列表

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_suggested\_destinations | fb\_suggested\_ destinations | - | - | - | - | - |

</Accordion>

<div id="af_suggested_hotels" />

<Accordion title="af_suggested_hotels">

**说明**: 推荐的酒店列表

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_suggested\_hotels | fb\_suggested\_hotels | - | - | - | - | - |

</Accordion>

<div id="af_travel_end" />

<Accordion title="af_travel_end">

**说明**: 行程结束日期

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_travel\_end | fb\_travel\_end | - | - | - | - | - |

</Accordion>

<div id="af_travel_start" />

<Accordion title="af_travel_start">

**说明**: 行程开始日期

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_travel\_start | fb\_travel\_start | - | - | - | - | - |

</Accordion>

<div id="af_user_score" />

<Accordion title="af_user_score">

**说明**: 用户对广告主的相对重要性

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_user\_score | fb\_user\_score | - | - | - | - | - |

</Accordion>

<div id="af_validated" />

<Accordion title="af_validated">

**说明**: 用于说明购买事件的验证结果

**参数映射：**

| AppsFlyer | Meta ads | Google Ads | Snap | X Ads | TikTok | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_validated | - | validated | success | - | - | - |

</Accordion>

下列预定义参数没有SRN侧的映射事件：

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

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration">应用内事件回传配置</Anchor>

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 h_01H9HT8C713A4NV9WCB0FJZJ4R=%E9%80%9F%E8%A7%88 predefined-event-names=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E5%90%8D%E7%A7%B0 h_01H9HT8C7189W1JXAR3J3KT8KV=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E5%90%8D%E7%A7%B0 h_01H9HT8C71MV7V7C75MB6ESHMM=achievement-unlocked-af_achievement_unlocked h_01H9HT8C7171PB7KAC83MYBWQ8=ad-click-af_ad_click h_01H9HT8C72KJ6ZA663SH7HJ7MP=ad-view-af_ad_view h_01H9HT8C72HSM88DJG0PDV5140=add-payment-info-af_add_payment_info h_01H9HT8C72BWFSPKWDVQW926WG=add-to-cart-af_add_to_cart h_01H9HT8C7228B57XKAACPZG8NK=add-to-wishlist-af_add_to_wishlist h_01H9HT8C72DX0DXBDHRJFG19G2=complete-registration-af_complete_registration h_01H9HT8C72SPY9VQ9AD648AKZK=content-view-af_content_view h_01H9HT8C722T2VH6A9257Q7T4P=initiated-checkout-af_initiated_checkout h_01H9HT8C72F0RZ4JS9929SE465=invite-af_invite h_01H9HT8C72VFGC08Q858EX7XTN=level-achieved-af_level_achieved h_01H9HT8C72DZW77YTQ9KB0XEVG=list-view-af_list_view h_01H9HT8C720W10QEBCTPAGMRFB=login-af_login h_01H9HT8C72QC4WV10Z4JZTZM7D=opened-from-push-notification-af_opened_from_push_notification h_01H9HT8C7263J0YSX5K10R497N=purchase-af_purchase h_01H9HT8C73MPYMG8KSYE04DKDZ=rate-af_rate h_01H9HT8C734DAC6GPJE58DB5JD=reengage-af_re_engage h_01H9HT8C73YSYBK0YSDPRWDBNW=search-af_search h_01H9HT8C734GJ07V67QC9V3TVC=share-af_share h_01H9HT8C73H4VT2M0P3M1SYG88=spent-credits-af_spent_credits h_01H9HT8C73YWDCKAZPY0BVRS6F=start-trial-af_start_trial h_01H9HT8C736BF2VNRCFSJSVXWS=%E6%B3%A8%E6%84%8F h_01H9HT8C73N69S45H82NWQ5FN1=subscription-af_subscribe h_01H9HT8C73CD6HNT5GA6B4CHQ9=travel-booking-af_travel_booking h_01H9HT8C73NFDPS1P5AVXXZEX7=tutorial-completion-af_tutorial_completion h_01H9HT8C73JPH6Q9XFKA3GNYT8=update-af_update h_01H9HT8C74SGGK2FW92JH4BJPZ=%E6%B3%A8%E6%84%8F-1 predefined-event-parameters=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E5%8F%82%E6%95%B0 h_01H9HT8C74N4TJZ5ZVBTKAX810=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E5%8F%82%E6%95%B0 h_01H9HT8C74VQ9ZWF079V50E5HE=%E6%B3%A8%E6%84%8F-2 h_01H9HT8C74Y0BWS565DFTY75KJ=af_adrev_ad_type h_01H9HT8C742NHGXFKWSS4P07K2=af_city h_01H9HT8C7442PFZEK7QC6R0K67=af_class h_01H9HT8C7462KG3030WWZ2XGZW=af_content h_01H9HT8C74ZX07907NXFHKGJ91=af_content_id h_01H9HT8C744CMWSYHJB74JFSS5=af_content_list h_01H9HT8C74GKGG5V4X54BCAADC=af_content_type h_01H9HT8C74RD08Z9EBZTKY5KSD=af_country h_01H9HT8C75BJYK4R3WYSN4BF43=af_currency h_01H9HT8C752E2PK6QKTA2GNGH5=af_customer_user_id h_01H9HT8C75BN0A92X9BRY4A74T=af_date_a h_01H9HT8C75406KV9264ZZT9DKM=af_date_b h_01H9HT8C7526AEHJAA7FM7442E=af_departing_arrival_date h_01H9HT8C75W9X61ZH0849EPDBY=af_departing_departure_date h_01H9HT8C75VEV3C8CJBDN6X5HW=af_description h_01H9HT8C75Z8TBZEPEY9EGSR4Y=af_destination_a h_01H9HT8C751G216VB6GYTPEPE1=af_destination_b h_01H9HT8C75CVM0MHSKTK2CZ8HD=af_destination_list h_01H9HT8C75CVVDFABSTN5R4MWT=af_hotel_score h_01H9HT8C75GEMHE2NHEFK9J7NT=af_level h_01H9HT8C7505H4CMY70EMDQWSF=af_max_rating_value h_01H9HT8C75ST9XBDC3SR6XFDPB=af_num_adults h_01H9HT8C75NNZ5NP6PRPXDSKP8=af_num_children h_01H9HT8C757X70AAGNWFV0CKRY=af_num_infants h_01H9HT8C75A0HESE5FD10VD1P8=af_order_id h_01H9HT8C75B488VKY8SW9M4GG4=af_payment_info_available h_01H9HT8C75W7SRB0KF4E5FB2YF=af_preferred_neighborhoods h_01H9HT8C75GC61D1A0P6P42TMR=af_preferred_num_stops h_01H9HT8C76XRY6CD1TJEPCJJTR=af_preferred_price_range h_01H9HT8C76Y9ZQQ2X4EJT2DC14=af_preferred_star_ratings h_01H9HT8C76KCDRJKBWSM9JKFE1=af_price 01J9XHWVFHXPN6N3EZF1P8XWYM=af_projected_revenue h_01H9HT8C767ZNWCBYC3X680PGQ=af_purchase_currency h_01H9HT8C76Y5VXBKF3TBVVJG1C=af_quantity h_01H9HT8C768WXZ126Q425PHDWX=af_rating_value h_01H9HT8C76XX9J6FZ6RWQB6B6R=af_receipt_id h_01H9HT8C760S0F7QZMFYW1BKRD=af_region h_01H9HT8C76N4S3SGES5SQ2J4AC=af_registration_method h_01H9HT8C76ZR36A4CM2PY6PJ10=af_returning_arrival_date h_01H9HT8C760JPVXYC5WH9ZSDPX=af_returning_departure_date h_01H9HT8C76PYB14WPCQKSEK69J=af_revenue h_01H9HT8C762BGPRHFX228APEHR=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01H9HT8C76P55HN8K6D7PHFS2J=af_score h_01H9HT8C76TB4KNTZVD6JVPEYQ=af_search_string h_01H9HT8C762R2PJ573W8TJFJHG=af_subscription_id h_01H9HT8C76VZ6FA20K471V0EKK=af_success h_01H9HT8C76029H94AY5EHCZX6X=af_suggested_destinations h_01H9HT8C76N6C694TCPVCK4EC3=af_suggested_hotels h_01H9HT8C765EM1SAEJ67FNXZDE=af_travel_end h_01H9HT8C76YP8VEM5E6WB9NQ7T=af_travel_start h_01H9HT8C771SYQWQ8VBTPA2V2E=af_user_score h_01H9HT8C771XFSQJX42QVBNZAJ=af_validated h_01HDNZ30NH2QXSHD7B4EMFG4T5=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
