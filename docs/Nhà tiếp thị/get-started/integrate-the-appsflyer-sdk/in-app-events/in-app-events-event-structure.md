---
title: Sự kiện phong phú trong ứng dụng—Cấu trúc sự kiện
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
  edited_at: '2023-10-30T04:51:14Z'
  id: 4410481112081
  locale: vi
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/vi/articles/4410481112081
---
> **Tổng quan:** Xem danh sách các tên sự kiện và thông số sự kiện được xác định trước để ghi nhận các sự kiện phong phú trong ứng dụng sau khi cài đặt (chẳng hạn như đăng nhập, đăng ký hoặc mua hàng trong ứng dụng).

<div id="overview" />

## Tổng quan

Các sự kiện trong ứng dụng mà bạn muốn gửi yêu cầu nhà phát triển của bạn phải triển khai mã, nếu có, trong ứng dụng của bạn. Bài viết này mô tả các tên sự kiện được xác định trước và thông số sự kiện được xác định trước.

Để giúp bạn xác định những sự kiện và thông số nào cần ghi nhận, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#recommended-events-by-business-vertical">các bài viết của chúng tôi bao gồm các ví dụ và quy trình</Anchor> theo ngành dọc kinh doanh.

<div id="lead-lead" />

<div id="app-open-af_app_opened" />

<div id="predefined-event-names" />

## Tên sự kiện được xác định trước

Phần sau cung cấp danh sách các tên sự kiện được xác định trước và ánh xạ sự kiện được sử dụng cho quảng cáo Meta, Google Ads, TikTok, Snap, Twitter và Criteo.

Mỗi tên sự kiện cũng bao gồm các thông số sự kiện được xác định trước điển hình được liên kết với sự kiện đó. Bạn có thể chọn đưa vào bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của mình.

<div id="achievement-unlocked-af_achievement_unlocked" />

<Accordion title="Thành tựu đã mở khóa (af_achievement_unlocked)">

**Mô tả**: Được dùng để ghi nhận các sự kiện mở khóa thành tích

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_achievement\_unlocked | fb\_mobile\_achievement\_unlocked | unlock\_achievement | UnlockAchievement | ACHIEVEMENT\_UNLOCKED | ACHIEVEMENT\_UNLOCKED | achievement |

**Thông số điển hình:**

Nhấp vào liên kết để xem ánh xạ tới SRN.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="ad-click-af_ad_click" />

<Accordion title="Nhấp vào quảng cáo (af_ad_click)">

**Mô tả**: Được dùng để ghi nhận các lượt nhấp quảng cáo hiển thị trong ứng dụng

**Ánh xạ sự kiện**:

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_ad\_click | Lượt nhấp quảng cáo | - | InAppADClick | AD\_CLICK | - | - |

**Các thông số điển hình:**

Nhấp vào liên kết để xem ánh xạ tới SRN.

* [af\_adrev\_ad\_type](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="ad-view-af_ad_view" />

<Accordion title="Lượt xem quảng cáo (af_ad_view)">

**Mô tả**: Được dùng để ghi nhận các lượt xem quảng cáo hiển thị trong ứng dụng

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_ad\_view | AdImpression | - | InAppADImpr | AD\_VIEW | - | - |

**Các thông số điển hình:**

Nhấp vào liên kết để xem ánh xạ tới SRN.

* [af\_adrev\_ad\_type](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="Thêm thông tin thanh toán (af_add_payment_info)">

**Mô tả**: Được dùng để ghi nhận trạng thái cấu hình thông tin thanh toán

**Xuất hiện trong các ngành này:** <Anchor target="_blank" href="/marketers/vi/docs/recommended-ride-hailing-app-events#add-payment-info-af_add_payment_info">Gọi xe</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-flight-booking-app-events#add-payment-info-af_add_payment_info">Đặt vé máy bay</Anchor>

**Ánh xạ sự kiện**:

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_add\_payment\_info | fb\_mobile\_add\_payment\_info | add\_payment\_info | AddPaymentInfo | ADD\_BILLING | ADDED\_PAYMENT\_INFO | ADD\_BILLING |

**Thông số điển hình:**

Nhấp vào liên kết để xem ánh xạ tới SRN.

* [af\_success](/docs/in-app-events-event-structure#af_success)

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="Thêm vào giỏ hàng (af_add_to_cart)">

**Mô tả**: Được dùng để ghi nhận các sự kiện thêm vào giỏ hàng các mặt hàng cụ thể. Để báo cáo một sự kiện gồm nhiều mặt hàng, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">đây</Anchor>.

**Xuất hiện trong các ngành này:** <Anchor target="_blank" href="/marketers/vi/docs/recommended-ecommerce-app-events#add-to-cart-af_add_to_cart">Thương mại điện tử</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-healthcare-app-events#add-to-cart-af_add_to_cart">Chăm sóc sức khỏe</Anchor>

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_add\_to\_cart | fb\_mobile\_add\_to\_cart | add\_to\_cart | AddToCart | ADD\_CART | ADD\_TO\_CART | viewBasket |

**Các thông số điển hình:**

Nhấp vào liên kết để xem ánh xạ tới SRN.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="Thêm vào danh sách yêu thích (af_add_to_wishlist)">

**Mô tả**: Được dùng để ghi nhận các sự kiện thêm vào danh sách mong muốn các mặt hàng cụ thể. Để báo cáo một sự kiện gồm nhiều mặt hàng, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">đây</Anchor>.

**Xuất hiện trong các ngành này:** <Anchor target="_blank" href="/marketers/vi/docs/recommended-ecommerce-app-events#add-to-wishlist-af_add_to_wishlist">Thương mại điện tử</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-hotel-booking-app-events#add-to-wishlist-af_add_to_wishlist">Đặt phòng khách sạn</Anchor>

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_add\_to\_wishlist | fb\_mobile\_add\_to\_wishlist | add\_to\_wishlist | AddToWishlist | ADD\_TO\_WISHLIST | ADD\_TO\_WISHLIST | - |

**Các thông số điển hình:**

Nhấp vào liên kết để xem ánh xạ tới SRN.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Hoàn tất đăng ký (af_complete_registration)">

**Mô tả**: Được dùng để ghi nhận phương thức đăng ký người dùng

**Xuất hiện trong các ngành này:** <Anchor target="_blank" href="/marketers/vi/docs/recommended-gaming-app-events#complete-registration-af_complete_registration">Trò chơi</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-ecommerce-app-events#complete-registration-af_complete_registration">Thương mại điện tử</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-entertainment-app-events#complete-registration-af_complete_registration">Giải trí</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-finance-and-banking-app-events#complete-registration-af_complete_registration">Tài chính và ngân hàng</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-p2p-lending-app-events#complete-registration-af_complete_registration">Cho vay P2P</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-online-education-app-events#complete-registration-af_complete_registration">Đào tạo trực tuyến</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-ride-hailing-app-events#complete-registration-af_complete_registration">Gọi xe</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-hotel-booking-app-events#complete-registration-af_complete_registration">Đặt phòng khách sạn</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-healthcare-app-events#complete-registration-af_complete_registration">Chăm sóc sức khỏe</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-telecommunication-app-events#complete-registration-af_complete_registration">Viễn thông</Anchor>

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_complete\_registration | fb\_mobile\_complete\_registration | sign\_up | Đăng ký | SIGN\_UP | SIGN\_UP | - |

**Thông số điển hình:**

Nhấp vào liên kết để xem ánh xạ tới SRN.

* [af\_registration\_method](/docs/in-app-events-event-structure#af_registration_method)

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Khung hiển thị nội dung (af_content_view)">

**Mô tả**: Được dùng để ghi nhận các sự kiện xem nội dung Để báo cáo một sự kiện gồm nhiều mặt hàng, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">đây</Anchor>.

**Xuất hiện trong các ngành này:** <Anchor target="_blank" href="/marketers/vi/docs/recommended-ecommerce-app-events#content-view-af_content_view">Thương mại điện tử</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-flight-booking-app-events#content-view-af_content_view">Đặt vé máy bay</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-hotel-booking-app-events#content-view-af_content_view">Đặt phòng khách sạn</Anchor>

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_content\_view | fb\_mobile\_content\_view | view\_item | ViewContent | VIEW\_CONTENT | CONTENT\_VIEW | viewProduct |

**Các thông số điển hình:**

Nhấp vào các thông số có liên quan đến nhu cầu kinh doanh của bạn để xem ánh xạ tới SRN.

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

<Accordion title="Bắt đầu thanh toán (af_initiated_checkout)">

**Mô tả**: Được dùng để ghi nhận các sự kiện thanh toán. Để báo cáo một sự kiện gồm nhiều mặt hàng, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">đây</Anchor>.

**Xuất hiện trong các ngành:** <Anchor target="_blank" href="/marketers/vi/docs/recommended-ecommerce-app-events#initiated-checkout-af_initiated_checkout">Thương mại điện tử</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-hotel-booking-app-events#initiated-checkout-af_initiated_checkout">Đặt phòng khách sạn</Anchor>

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_initiated\_checkout | fb\_mobile\_initiated\_checkout | begin\_checkout | Checkout | START\_CHECKOUT | CHECKOUT\_INITIATED | viewBasket |

**Các thông số điển hình:**

Nhấp vào các thông số có liên quan đến nhu cầu kinh doanh của bạn để xem ánh xạ tới SRN.

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

<Accordion title="Mời (af_invite)">

**Mô tả**: Được dùng để ghi nhận các sự kiện mời (xã hội)

**Xuất hiện trong các ngành này:** <Anchor target="_blank" href="/marketers/vi/docs/recommended-gaming-app-events#invite-af_invite">Trò chơi</Anchor>

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_invite | - | invite | - | INVITE | INVITE | - |

**Thông số điển hình:**

Nhấp vào liên kết để xem ánh xạ tới SRN.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="level-achieved-af_level_achieved" />

<Accordion title="Cấp độ đạt được (af_level_achieved)">

**Mô tả**: Được dùng để ghi nhận sự kiện cấp độ trò chơi

**Xuất hiện trong các ngành này:** <Anchor target="_blank" href="/marketers/vi/docs/recommended-gaming-app-events#level-achieved-af_level_achieved">Trò chơi</Anchor>

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_level\_achieved | fb\_mobile\_level\_achieved | level\_up | AchieveLevel | LEVEL\_COMPLETE | LEVEL\_ACHIEVED | userLevel |

**Các thông số điển hình:**

Nhấp vào liên kết để xem ánh xạ tới SRN.

* [af\_level](/docs/in-app-events-event-structure#af_level)
* [af\_score](/docs/in-app-events-event-structure#af_score)

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="Xem danh sách (af_list_view)">

**Mô tả**: Được dùng để ghi nhận các sự kiện xem danh sách

**Xuất hiện trong các ngành này:** <Anchor target="_blank" href="/marketers/vi/docs/recommended-ecommerce-app-events#list-view-af_list_view">Thương mại điện tử</Anchor>

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_list\_view | - | view\_item\_list | - | LIST\_VIEW | - | viewListing |

**Các thông số điển hình:**

Nhấp vào liên kết để xem ánh xạ tới SRN.

* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)

</Accordion>

<div id="login-af_login" />

<Accordion title="Đăng nhập (af_login)">

**Mô tả**: Được dùng để ghi nhận các sự kiện đăng nhập của người dùng

**Xuất hiện trong các ngành này:** <Anchor target="_blank" href="/marketers/vi/docs/recommended-gaming-app-events#login-af_login">Trò chơi</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-ecommerce-app-events#login-af_login">Thương mại điện tử</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-entertainment-app-events#login-af_login">Giải trí</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-finance-and-banking-app-events#login-af_login">Tài chính và ngân hàng</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-online-education-app-events#login-af_login">Đào tạo trực tuyến</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-hotel-booking-app-events#login-af_login">Đặt phòng khách sạn</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-healthcare-app-events#login-af_login">Chăm sóc sức khỏe</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-telecommunication-app-events#login-af_login">Viễn thông</Anchor>

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_login | - | login | Đăng nhập | - | LOGIN | - |

</Accordion>

<div id="opened-from-push-notification-af_opened_from_push_notification" />

<Accordion title="Được mở từ thông báo đẩy (af_opened_from_push_notification)">

**Mô tả**: Được dùng để ghi nhận các sự kiện mở ứng dụng từ thông báo đẩy

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_opened\_from\_push\_notification | - | notification\_open | - | - | - | - |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Mua hàng (af_purchase)">

**Mô tả**: Được dùng để ghi nhận các sự kiện mua hàng (và liên kết doanh thu với sự kiện). Để biết danh sách các ký hiệu tiền tệ được AppsFlyer hỗ trợ, hãy nhấp vào <Anchor target="_blank" href="https://docs.openexchangerates.org/docs/supported-currencies">đây</Anchor>. Để báo cáo một sự kiện gồm nhiều mặt hàng, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">đây</Anchor>.

**Xuất hiện trong các ngành:** <Anchor target="_blank" href="/marketers/vi/docs/recommended-gaming-app-events#purchase-af_purchase">Trò chơi</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-ecommerce-app-events#purchase-af_purchase">Thương mại điện tử</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-online-education-app-events#purchase-af_purchase">Đào tạo trực tuyến</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-healthcare-app-events#purchase-af_purchase">Chăm sóc sức khỏe</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-telecommunication-app-events#purchase-af_purchase">Viễn thông</Anchor>

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_purchase | fb\_mobile\_purchase | in\_app\_purchase | Mua | PURCHASE | PURCHASE | transactionConfirmation |

**Các thông số điển hình:**

Nhấp vào các thông số có liên quan đến nhu cầu kinh doanh của bạn để xem ánh xạ tới SRN.

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

<Accordion title="Xếp hạng (af_rate)">

**Mô tả**: Được dùng để ghi nhận các sự kiện xếp hạng ứng dụng/mặt hàng. Để báo cáo một sự kiện gồm nhiều mặt hàng, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">đây</Anchor>.

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_rate | fb\_mobile\_rate | submit\_rating | Xếp hạng | RATE | RATED | - |

**Các thông số điển hình:**

Nhấp vào liên kết để xem ánh xạ tới SRN.

* [af\_rating\_value](/docs/in-app-events-event-structure#af_rating_value)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_max\_rating\_value](/docs/in-app-events-event-structure#af_max_rating_value)

</Accordion>

<div id="reengage-af_re_engage" />

<Accordion title="Thu hút lại (af_re_engage)">

**Mô tả**: Được dùng để ghi nhận các sự kiện tương tác lại người dùng

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_re\_engage | - | custom\_event | - | RE\_ENGAGE | - |

**Thông số điển hình:**

Nhấp vào liên kết để xem ánh xạ tới SRN.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="search-af_search" />

<Accordion title="Tìm kiếm (af_search)">

**Mô tả**: Được dùng để ghi nhận các sự kiện tìm kiếm

**Xuất hiện trong các ngành này:** <Anchor target="_blank" href="/marketers/vi/docs/recommended-ecommerce-app-events#search-af_search">Thương mại điện tử</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-flight-booking-app-events#search-af_search">Đặt vé máy bay</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-hotel-booking-app-events#search-af_search">Đặt phòng khách sạn</Anchor>

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_search | fb\_mobile\_search | view\_search\_results | Tìm kiếm | - | SEARCH | viewSearch |

**Các thông số điển hình:**

Nhấp vào các thông số có liên quan đến nhu cầu kinh doanh của bạn để xem ánh xạ tới SRN.

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

<Accordion title="Chia sẻ (af_share)">

**Mô tả**: Được dùng để ghi nhận các sự kiện chia sẻ

**Xuất hiện trong các ngành này:** <Anchor target="_blank" href="/marketers/vi/docs/recommended-gaming-app-events#share-af_share">Trò chơi</Anchor>

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_share | - | share | - | SHARE | SHARE | - |

**Thông số điển hình:**

Nhấp vào liên kết để xem ánh xạ tới SRN.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="spent-credits-af_spent_credits" />

<Accordion title="Tín dụng đã chi tiêu (af_spent_credits)">

**Mô tả**: Được dùng để ghi nhận các sự kiện chi tiêu tín dụng. Để báo cáo một sự kiện gồm nhiều mặt hàng, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">đây</Anchor>.

**Xuất hiện trong các ngành:** <Anchor target="_blank" href="/marketers/vi/docs/recommended-ride-hailing-app-events#spent-credits-af_spent_credits">Gọi xe</Anchor>

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_spent\_credits | fb\_mobile\_spent\_credits | spend\_virtual\_currency | SpendCredits | SPENT\_CREDITS | SPENT\_CREDITS | transactionConfirmation |

**Các thông số điển hình:**

Nhấp vào liên kết để xem ánh xạ tới SRN.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="start-trial-af_start_trial" />

<Accordion title="Bắt đầu dùng thử (af_start_trial)">

**Mô tả**: Được dùng để ghi nhận việc bắt đầu dùng thử một sản phẩm

**Xuất hiện trong các ngành này:** <Anchor target="_blank" href="/marketers/vi/docs/recommended-entertainment-app-events#start-trial-af_start_trial">Giải trí</Anchor>

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_start\_trial | Bắt đầu dùng thử | - | Bắt đầu dùng thử | START\_TRIAL | - | - |

**Các thông số điển hình:**

Nhấp vào liên kết để xem ánh xạ tới SRN.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

<div id="note" />

> 📘 **Lưu ý**
>
> Nếu bạn đang ánh xạ sự kiện này với sự kiện StartTrial của quảng cáo Meta và muốn liên kết doanh thu, hãy sử dụng thông số af\_price thay vì thông số af\_revenue.

</Accordion>

<div id="subscription-af_subscribe" />

<Accordion title="Đăng ký (af_subscribe)">

**Mô tả**: Được sử dụng để ghi nhận các giao dịch đăng ký trả tiền

**Xuất hiện trong các ngành này:** <Anchor target="_blank" href="/marketers/vi/docs/recommended-entertainment-app-events#subscription-af_subscribe">Giải trí</Anchor>

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_subscribe | Subscribe | - | Subscribe | - | - | SUBSCRIBE |

**Các thông số điển hình:**

Nhấp vào liên kết để xem ánh xạ tới SRN.

* [af\_revenue](/docs/in-app-events-event-structure#af_revenue)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="Đặt vé du lịch (af_travel_booking)">

**Mô tả**: Được dùng để ghi nhận các sự kiện đặt vé đi lại (và liên kết doanh thu với sự kiện) Để báo cáo một sự kiện gồm nhiều mặt hàng, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">đây</Anchor>.

**Xuất hiện trong các ngành này:** <Anchor target="_blank" href="/marketers/vi/docs/recommended-flight-booking-app-events#travel-booking-af_travel_booking">Đặt vé máy bay</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-hotel-booking-app-events#travel-booking-af_travel_booking">Đặt phòng khách sạn</Anchor>

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_travel\_booking | fb\_mobile\_purchase | ecommerce\_purchase | Mua | RESERVE | PURCHASE | transactionConfirmation |

**Các thông số điển hình:**

Nhấp vào các thông số có liên quan đến nhu cầu kinh doanh của bạn để xem ánh xạ tới SRN.

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

<Accordion title="Hoàn thành hướng dẫn (af_tutorial_completion)">

**Mô tả**: Được dùng để ghi nhận việc hoàn thành hướng dẫn. Để báo cáo một sự kiện gồm nhiều mặt hàng, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">đây</Anchor>.

**Xuất hiện trong các ngành này:** <Anchor target="_blank" href="/marketers/vi/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">Trò chơi</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">Đào tạo trực tuyến</Anchor>

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_tutorial\_completion | fb\_mobile\_tutorial\_completion | tutorial\_complete | CompleteTutorial | COMPLETE\_TUTORIAL | TUTORIAL\_COMPLETE | - |

**Các thông số điển hình:**

Nhấp vào liên kết để xem ánh xạ tới SRN.

* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="update-af_update" />

<Accordion title="Cập nhật (af_update)">

**Mô tả**: Được dùng để ghi nhận các sự kiện cập nhật. Để báo cáo một sự kiện gồm nhiều mặt hàng, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">đây</Anchor>.

**Ánh xạ sự kiện:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_update | - | app\_update | - | UPDATE | - |

**Thông số điển hình:**

Nhấp vào liên kết để xem ánh xạ tới SRN.

* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)

</Accordion>

<div id="note-1" />

> 📘 **Lưu ý**
>
> Ngoài các tên sự kiện xác định trước được mô tả trong phần này, <Anchor target="_blank" href="/marketers/vi/docs/meta-ads-in-app-event-mapping#ánh-xạ-sự-kiện-được-xác-định-trước">quảng cáo Meta còn cung cấp các sự kiện bổ sung</Anchor> được gửi đi mà không phân bổ.

<div id="predefined-event-parameters" />

## Các thông số sự kiện được xác định trước

Phần sau cung cấp danh sách các thông số sự kiện được xác định trước. Mỗi thông số sự kiện bao gồm ánh xạ được sử dụng cho quảng cáo Meta, Google Ads, Snap, Twitter và Criteo. Bạn có thể chọn đưa bất kỳ thông số sự kiện nào vào một sự kiện.

<div id="af_projected_revenue" />

<div id="h_01NEWAFNETREVENUE0001" />

<div id="note-3" />

<div id="note-2" />

> 📘 **Lưu ý**
>
> Bạn có thể xem các thông số sự kiện trong cột Giá trị Sự kiện trong <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">báo cáo dữ liệu thô</Anchor> (tính năng cao cấp).

<div id="af_adrev_ad_type" />

<Accordion title="af_adrev_ad_type">

**Mô tả**: Loại quảng cáo (ví dụ: biểu ngữ hoặc quảng cáo xen kẽ)

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_adrev\_ad\_type | ad\_type | - | - | - | - |

</Accordion>

<div id="af_city" />

<Accordion title="af_city">

**Mô tả**: Thành phố nơi hành khách đặt chuyến xe

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_city | fb\_city | - | - | - | - |

</Accordion>

<div id="af_class" />

<Accordion title="af_class">

**Mô tả**: Hạng đã đặt cho chuyến bay

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_class | fb\_travel\_class | travel\_class | - | - | - |

</Accordion>

<div id="af_content" />

<Accordion title="af_content">

**Mô tả**: Tiêu đề của nội dung (ví dụ: tên bài hát hoặc tiêu đề và tập của một chương trình truyền hình)

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_content | fb\_content | - | - | - | - |

</Accordion>

<div id="af_content_id" />

<Accordion title="af_content_id">

**Mô tả**: ID của mặt hàng

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_content\_id | fb\_content\_id | item\_id | item\_ids | content\_id | id |

</Accordion>

<div id="af_content_list" />

<Accordion title="af_content_list">

**Mô tả**: Danh sách các ID nội dung

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_content\_list | - | item\_id | - | - | - |

</Accordion>

<div id="af_content_type" />

<Accordion title="af_content_type">

**Mô tả**: Danh mục sản phẩm

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_content\_type | fb\_content\_type | item\_category | item\_category | content\_type | - |

</Accordion>

<div id="af_country" />

<Accordion title="af_country">

**Mô tả**: Quốc gia nơi hành khách đặt chuyến xe

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_country | fb\_country | - | - | - | - |

</Accordion>

<div id="af_currency" />

<Accordion title="af_currency">

**Mô tả**: Mã tiền tệ

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_currency | fb\_currency | currency\_code | tiền tệ | price\_currency | tiền tệ |

</Accordion>

<div id="af_customer_user_id" />

<Accordion title="af_customer_user_id">

**Mô tả**: ID của khách hàng

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_customer\_user\_id | - | customer\_user\_  <br />id | - | - | cid |

</Accordion>

<div id="af_date_a" />

<Accordion title="af_date_a">

**Mô tả**: Ngày nhận phòng

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_date\_a | fb\_checkin\_date | start\_date | - | - | din |

</Accordion>

<div id="af_date_b" />

<Accordion title="af_date_b">

**Mô tả**: Ngày trả phòng

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_date\_b | fb\_checkout\_date | end\_date | - | - | dout |

</Accordion>

<div id="af_departing_arrival_date" />

<Accordion title="af_departing_arrival_date">

**Mô tả**: Ngày đến

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_departing\_arrival\_date | fb\_departing\_arrival\_date | - | - | - | - |

</Accordion>

<div id="af_departing_departure_date" />

<Accordion title="af_departing_departure_date">

**Mô tả**: Ngày khởi hành

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_departing\_departure\_date | fb\_departing\_departure\_date | - | - | - | - |

</Accordion>

<div id="af_description" />

<Accordion title="af_description">

**Mô tả**: Mô tả ngắn (chuỗi)

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_description | fb\_description | description | description | description | ui\_achievement |

</Accordion>

<div id="af_destination_a" />

<Accordion title="af_destination_a">

**Mô tả**: Điểm đến đầu tiên

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_destination\_a | fb\_origin\_airport | origin | - | - | - |

</Accordion>

<div id="af_destination_b" />

<Accordion title="af_destination_b">

**Mô tả**: Điểm đến thứ hai

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_destination\_b | fb\_destination\_  <br />airport | destination | - | - | - |

</Accordion>

<div id="af_destination_list" />

<Accordion title="af_destination_list">

**Mô tả**: Danh sách các điểm đến có trong danh mục điểm đến (ví dụ: danh sách các viện bảo tàng hoặc nhà hàng gần khách sạn)

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_destination\_list | fb\_destination\_ids | - | - | - | - |

</Accordion>

<div id="af_hotel_score" />

<Accordion title="af_hotel_score">

**Mô tả**: Điểm số của khách sạn theo đánh giá

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_hotel\_score | fb\_hotel\_score | - | - | - | - |

</Accordion>

<div id="af_level" />

<Accordion title="af_level">

**Mô tả**: Cấp độ mà người dùng đạt được

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_level | fb\_level | level\_up | level | level | ui\_level |

</Accordion>

<div id="af_max_rating_value" />

<Accordion title="af_max_rating_value">

**Mô tả**: Điểm tốt nhất của thang đánh giá (ví dụ: 5 trên 5)

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_max\_rating\_value | fb\_max\_rating\_value | max\_rating | - | max\_rated\_value | - |

</Accordion>

<div id="af_num_adults" />

<Accordion title="af_num_adults">

**Mô tả**: Số lượng người lớn đi

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_num\_adults | fb\_num\_adults | - | - | - | - |

</Accordion>

<div id="af_num_children" />

<Accordion title="af_num_children">

**Mô tả**: Số lượng trẻ em đi

Ánh xạ thông số:

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_num\_children | fb\_num\_children | - | - | - | - |

</Accordion>

<div id="af_num_infants" />

<Accordion title="af_num_infants">

**Mô tả**: Số lượng trẻ sơ sinh đi

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_num\_infants | fb\_num\_infants | - | - | - | - |

</Accordion>

<div id="af_order_id" />

<Accordion title="af_order_id">

**Mô tả**: ID của giao dịch

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_order\_id | fb\_order\_id | order\_id | transaction\_id | - | transaction\_id |

</Accordion>

<div id="af_payment_info_available" />

<Accordion title="af_payment_info_available">

**Mô tả**: Có thông tin thanh toán của người dùng không

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_payment\_info\_available | fb\_payment\_info\_available | payment\_info\_  <br />available | payment\_info\_available | user\_payment\_  <br />info | - |

</Accordion>

<div id="af_preferred_neighborhoods" />

<Accordion title="af_preferred_neighborhoods">

**Mô tả**: Khu vực vị trí của khách sạn

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_preferred\_neighborhoods | fb\_preferred\_neighborhoods | - | - | - | - |

</Accordion>

<div id="af_preferred_num_stops" />

<Accordion title="af_preferred_num_stops">

**Mô tả**: Số điểm dừng mà người dùng đang tìm kiếm (ví dụ: bay không điểm dừng hay bay thẳng)

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_preferred\_num\_stops | fb\_preferred\_num\_stops | - | - | - | - |

</Accordion>

<div id="af_preferred_price_range" />

<Accordion title="af_preferred_price_range">

**Mô tả**: Khoảng giá ưu tiên của khách sạn

Ánh xạ thông số:

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_preferred\_price\_range | fb\_preferred\_price\_range | - | - | - | - |

</Accordion>

<div id="af_preferred_star_ratings" />

<Accordion title="af_preferred_star_ratings">

**Mô tả**: Xếp hạng sao khách sạn được ưu tiên

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_preferred\_star\_ratings | fb\_preferred\_star\_ratings | - | - | - | - |

</Accordion>

<div id="af_price" />

<Accordion title="af_price">

**Mô tả**: Giá của sản phẩm. Bạn có thể dùng af\_price như một thông số tiền tệ mà không được xem là doanh thu (ví dụ như sự kiện Thêm vào giỏ hàng). Thông số này đề cập đến giá của từng mặt hàng. Tổng số tiền của tất cả các giao dịch mua hiển thị trong thông số [af\_revenue](/docs/in-app-events-event-structure#af_revenue).

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_price | fb\_price | price | price | price\_micro | price |

</Accordion>

<div id="af_purchase_currency" />

<Accordion title="af_purchase_currency">

**Mô tả**: Đơn vị tiền tệ được sử dụng để mua hàng

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_purchase\_currency | fb\_purchase\_currency | - | - | - | - |

</Accordion>

<div id="af_quantity" />

<Accordion title="af_quantity">

**Mô tả**: Số lượng mặt hàng

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_quantity | fb\_num\_items | quantity | number\_items | number\_items | quantity |

</Accordion>

<div id="af_rating_value" />

<Accordion title="af_rating_value">

**Mô tả**: Giá trị xếp hạng đã chọn

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_rating\_value | \_valueToSum | value | - | price\_micro | - |

</Accordion>

<div id="af_receipt_id" />

<Accordion title="af_receipt_id">

**Mô tả**: ID của biên lai

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_receipt\_id | - | transaction\_id | - | - | transaction\_id |

</Accordion>

<div id="af_region" />

<Accordion title="af_region">

**Mô tả**: Khu vực nơi hành khách đặt chuyến xe

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_region | fb\_region | - | - | - | - |

</Accordion>

<div id="af_registration_method" />

<Accordion title="af_registration_method">

**Mô tả**: Loại phương thức đăng ký

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_registration\_method | fb\_registration\_method | registration\_method | sign\_up\_method | registration\_method | - |

</Accordion>

<div id="af_returning_arrival_date" />

<Accordion title="af_returning_arrival_date">

**Mô tả**: Ngày và giờ kết thúc hành trình về

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_returning\_arrival\_date | fb\_returning\_arrival\_date | - | - | - | - |

</Accordion>

<div id="af_returning_departure_date" />

<Accordion title="af_returning_departure_date">

**Mô tả**:  Ngày và giờ bắt đầu hành trình về

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_returning\_departure\_date | fb\_returning\_departure\_date | - | - | - | - |

</Accordion>

<div id="af_revenue" />

<Accordion title="af_revenue">

**Mô tả**: Tổng số tiền mua hàng. af\_revenue được xem là doanh thu trong nền tảng AppsFlyer. Thông số này cũng gồm cả <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#revenue-events">doanh thu âm</Anchor>, do việc hủy hoặc hoàn lại tiền.

<div id="important" />

> 🚧 **Quan trọng!**
>
> Giá trị doanh thu không được chứa dấu phẩy phân tách, đơn vị tiền tệ, ký tự đặc biệt hoặc văn bản. Ví dụ: giá trị doanh thu phải là 1234.56. AppsFlyer cung cấp giá trị doanh thu với độ chính xác lên đến năm chữ số sau dấu thập phân.

Để tìm hiểu thêm về cách sử dụng thông số doanh thu, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#revenue-events">đây</Anchor>.

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_revenue | \_valueToSum | value | price | price\_micro | ui\_revenue |

</Accordion>

<div id="af_score" />

<Accordion title="af_score">

**Mô tả**: Điểm số liên quan đến thành tựu của người dùng

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_score | - | - | - | score | - |

</Accordion>

<div id="af_search_string" />

<Accordion title="af_search_string">

**Mô tả**: Cụm từ tìm kiếm

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_search\_string | fb\_search\_string | search\_string | search\_string | search\_string | - |

</Accordion>

<div id="af_subscription_id" />

<Accordion title="af_subscription_id">

**Mô tả**: ID đăng ký cho người dùng

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_subscription\_id | subscription\_id | - | - | - | - |

</Accordion>

<div id="af_success" />

<Accordion title="af_success">

**Mô tả**: Hành động có thành công hay không

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_success | fb\_success | success | success | - | - |

</Accordion>

<div id="af_suggested_destinations" />

<Accordion title="af_suggested_destinations">

**Mô tả**: Danh sách các điểm đến được đề xuất

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_suggested\_destinations | fb\_suggested\_destinations | - | - | - | - |

</Accordion>

<div id="af_suggested_hotels" />

<Accordion title="af_suggested_hotels">

**Mô tả**: Danh sách các khách sạn được đề xuất

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_suggested\_hotels | fb\_suggested\_hotels | - | - | - | - |

</Accordion>

<div id="af_travel_end" />

<Accordion title="af_travel_end">

**Mô tả**: Ngày kết thúc chuyến đi

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_travel\_end | fb\_travel\_end | - | - | - | - |

</Accordion>

<div id="af_travel_start" />

<Accordion title="af_travel_start">

**Mô tả**: Ngày bắt đầu chuyến đi

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_travel\_start | fb\_travel\_start | - | - | - | - |

</Accordion>

<div id="af_user_score" />

<Accordion title="af_user_score">

**Mô tả**: Ý nghĩa tương đối của người dùng đối với nhà quảng cáo

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_user\_score | fb\_user\_score | - | - | - | - |

</Accordion>

<div id="af_validated" />

<Accordion title="af_validated">

**Mô tả**: Xác thực giao dịch mua

**Ánh xạ thông số:**

| AppsFlyer | Quảng cáo Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_validated | - | đã xác thực | success | - | - |

</Accordion>

Sau đây là danh sách các thông số sự kiện được xác định trước không bao gồm ánh xạ SRN:

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

<div id="see-also" />

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration">Cấu hình đăng lại sự kiện trong ứng dụng</Anchor>

<div data-zendesk-anchors="overview=t%E1%BB%95ng-quan h_01H9HT8C713A4NV9WCB0FJZJ4R=t%E1%BB%95ng-quan predefined-event-names=t%C3%AAn-s%E1%BB%B1-ki%E1%BB%87n-%C4%91%C6%B0%E1%BB%A3c-x%C3%A1c-%C4%91%E1%BB%8Bnh-tr%C6%B0%E1%BB%9Bc h_01H9HT8C7189W1JXAR3J3KT8KV=t%C3%AAn-s%E1%BB%B1-ki%E1%BB%87n-%C4%91%C6%B0%E1%BB%A3c-x%C3%A1c-%C4%91%E1%BB%8Bnh-tr%C6%B0%E1%BB%9Bc h_01H9HT8C71MV7V7C75MB6ESHMM=achievement-unlocked-af_achievement_unlocked h_01H9HT8C7171PB7KAC83MYBWQ8=ad-click-af_ad_click h_01H9HT8C72KJ6ZA663SH7HJ7MP=ad-view-af_ad_view h_01H9HT8C72HSM88DJG0PDV5140=add-payment-info-af_add_payment_info h_01H9HT8C72BWFSPKWDVQW926WG=add-to-cart-af_add_to_cart h_01H9HT8C7228B57XKAACPZG8NK=add-to-wishlist-af_add_to_wishlist h_01H9HT8C72DX0DXBDHRJFG19G2=complete-registration-af_complete_registration h_01H9HT8C72SPY9VQ9AD648AKZK=content-view-af_content_view h_01H9HT8C722T2VH6A9257Q7T4P=initiated-checkout-af_initiated_checkout h_01H9HT8C72F0RZ4JS9929SE465=invite-af_invite h_01H9HT8C72VFGC08Q858EX7XTN=level-achieved-af_level_achieved h_01H9HT8C72DZW77YTQ9KB0XEVG=list-view-af_list_view h_01H9HT8C720W10QEBCTPAGMRFB=login-af_login h_01H9HT8C72QC4WV10Z4JZTZM7D=opened-from-push-notification-af_opened_from_push_notification h_01H9HT8C7263J0YSX5K10R497N=purchase-af_purchase h_01H9HT8C73MPYMG8KSYE04DKDZ=rate-af_rate h_01H9HT8C734DAC6GPJE58DB5JD=reengage-af_re_engage h_01H9HT8C73YSYBK0YSDPRWDBNW=search-af_search h_01H9HT8C734GJ07V67QC9V3TVC=share-af_share h_01H9HT8C73H4VT2M0P3M1SYG88=spent-credits-af_spent_credits h_01H9HT8C73YWDCKAZPY0BVRS6F=start-trial-af_start_trial h_01H9HT8C736BF2VNRCFSJSVXWS=l%C6%B0u-%C3%BD h_01H9HT8C73N69S45H82NWQ5FN1=subscription-af_subscribe h_01H9HT8C73CD6HNT5GA6B4CHQ9=travel-booking-af_travel_booking h_01H9HT8C73NFDPS1P5AVXXZEX7=tutorial-completion-af_tutorial_completion h_01H9HT8C73JPH6Q9XFKA3GNYT8=update-af_update h_01H9HT8C74SGGK2FW92JH4BJPZ=l%C6%B0u-%C3%BD-1 predefined-event-parameters=c%C3%A1c-th%C3%B4ng-s%E1%BB%91-s%E1%BB%B1-ki%E1%BB%87n-%C4%91%C6%B0%E1%BB%A3c-x%C3%A1c-%C4%91%E1%BB%8Bnh-tr%C6%B0%E1%BB%9Bc h_01H9HT8C74N4TJZ5ZVBTKAX810=c%C3%A1c-th%C3%B4ng-s%E1%BB%91-s%E1%BB%B1-ki%E1%BB%87n-%C4%91%C6%B0%E1%BB%A3c-x%C3%A1c-%C4%91%E1%BB%8Bnh-tr%C6%B0%E1%BB%9Bc h_01H9HT8C74VQ9ZWF079V50E5HE=l%C6%B0u-%C3%BD-2 h_01H9HT8C74Y0BWS565DFTY75KJ=af_adrev_ad_type h_01H9HT8C742NHGXFKWSS4P07K2=af_city h_01H9HT8C7442PFZEK7QC6R0K67=af_class h_01H9HT8C7462KG3030WWZ2XGZW=af_content h_01H9HT8C74ZX07907NXFHKGJ91=af_content_id h_01H9HT8C744CMWSYHJB74JFSS5=af_content_list h_01H9HT8C74GKGG5V4X54BCAADC=af_content_type h_01H9HT8C74RD08Z9EBZTKY5KSD=af_country h_01H9HT8C75BJYK4R3WYSN4BF43=af_currency h_01H9HT8C752E2PK6QKTA2GNGH5=af_customer_user_id h_01H9HT8C75BN0A92X9BRY4A74T=af_date_a h_01H9HT8C75406KV9264ZZT9DKM=af_date_b h_01H9HT8C7526AEHJAA7FM7442E=af_departing_arrival_date h_01H9HT8C75W9X61ZH0849EPDBY=af_departing_departure_date h_01H9HT8C75VEV3C8CJBDN6X5HW=af_description h_01H9HT8C75Z8TBZEPEY9EGSR4Y=af_destination_a h_01H9HT8C751G216VB6GYTPEPE1=af_destination_b h_01H9HT8C75CVM0MHSKTK2CZ8HD=af_destination_list h_01H9HT8C75CVVDFABSTN5R4MWT=af_hotel_score h_01H9HT8C75GEMHE2NHEFK9J7NT=af_level h_01H9HT8C7505H4CMY70EMDQWSF=af_max_rating_value h_01H9HT8C75ST9XBDC3SR6XFDPB=af_num_adults h_01H9HT8C75NNZ5NP6PRPXDSKP8=af_num_children h_01H9HT8C757X70AAGNWFV0CKRY=af_num_infants h_01H9HT8C75A0HESE5FD10VD1P8=af_order_id h_01H9HT8C75B488VKY8SW9M4GG4=af_payment_info_available h_01H9HT8C75W7SRB0KF4E5FB2YF=af_preferred_neighborhoods h_01H9HT8C75GC61D1A0P6P42TMR=af_preferred_num_stops h_01H9HT8C76XRY6CD1TJEPCJJTR=af_preferred_price_range h_01H9HT8C76Y9ZQQ2X4EJT2DC14=af_preferred_star_ratings h_01H9HT8C76KCDRJKBWSM9JKFE1=af_price h_01H9HT8C767ZNWCBYC3X680PGQ=af_purchase_currency h_01H9HT8C76Y5VXBKF3TBVVJG1C=af_quantity h_01H9HT8C768WXZ126Q425PHDWX=af_rating_value h_01H9HT8C76XX9J6FZ6RWQB6B6R=af_receipt_id h_01H9HT8C760S0F7QZMFYW1BKRD=af_region h_01H9HT8C76N4S3SGES5SQ2J4AC=af_registration_method h_01H9HT8C76ZR36A4CM2PY6PJ10=af_returning_arrival_date h_01H9HT8C760JPVXYC5WH9ZSDPX=af_returning_departure_date h_01H9HT8C76PYB14WPCQKSEK69J=af_revenue h_01H9HT8C762BGPRHFX228APEHR=quan-tr%E1%BB%8Dng h_01H9HT8C76P55HN8K6D7PHFS2J=af_score h_01H9HT8C76TB4KNTZVD6JVPEYQ=af_search_string h_01H9HT8C762R2PJ573W8TJFJHG=af_subscription_id h_01H9HT8C76VZ6FA20K471V0EKK=af_success h_01H9HT8C76029H94AY5EHCZX6X=af_suggested_destinations h_01H9HT8C76N6C694TCPVCK4EC3=af_suggested_hotels h_01H9HT8C765EM1SAEJ67FNXZDE=af_travel_end h_01H9HT8C76YP8VEM5E6WB9NQ7T=af_travel_start h_01H9HT8C771SYQWQ8VBTPA2V2E=af_user_score h_01H9HT8C771XFSQJX42QVBNZAJ=af_validated h_01HDNZ30NH2QXSHD7B4EMFG4T5=xem-th%C3%AAm" />
