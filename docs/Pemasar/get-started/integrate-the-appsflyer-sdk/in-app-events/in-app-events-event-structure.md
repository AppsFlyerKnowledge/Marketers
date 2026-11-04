---
title: Rich in-app event—Struktur event
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
  edited_at: '2023-10-27T13:22:31Z'
  id: 4410481112081
  locale: id
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/id/articles/4410481112081
---
> **Sekilas:** Lihat daftar nama event dan parameter event yang telah ditentukan sebelumnya untuk mencatat rich in-app event setelah penginstalan (seperti login, pendaftaran, atau pembelian dalam aplikasi).

## Overview

In-app event yang ingin Anda kirim mewajibkan pengembang untuk menerapkan kode jika berlaku untuk aplikasi Anda. Artikel ini menjelaskan nama event yang ditentukan sebelumnya dan parameter event yang ditentukan sebelumnya.

Untuk membantu Anda menentukan event dan parameter apa yang akan dicatat, lihat <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#recommended-events-by-business-vertical">artikel kami yang menyertakan contoh dan alur</Anchor> menurut vertikal bisnis.

<div id="predefined-event-names" />

## Nama event yang telah ditentukan sebelumnya

Bagian berikut memberikan daftar nama event yang telah ditentukan sebelumnya dan pemetaan event yang digunakan untuk Meta ads, Google Ads, TikTok, Snap, Twitter, dan Criteo.

Setiap nama event juga menyertakan parameter event umum yang telah ditentukan terkait dengan event tersebut. Anda dapat memilih untuk menyertakan parameter event apa pun yang memenuhi kebutuhan bisnis Anda.

<div id="achievement-unlocked-af_achievement_unlocked" />

<Accordion title="Pencapaian dibuka (af_achievement_unlocked)">

**Deskripsi**: Digunakan untuk mencatat event pembuka pencapaian

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_achievement\_unlocked | fb\_mobile\_achievement\_unlocked | unlock\_achievement | UnlockAchievement | ACHIEVEMENT\_UNLOCKED | ACHIEVEMENT\_UNLOCKED | pencapaian |

**Parameter umum:**

Klik tautan untuk melihat pemetaan ke SRN.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="ad-click-af_ad_click" />

<Accordion title="Klik iklan (af_ad_click)">

**Deskripsi**: Digunakan untuk mencatat klik iklan pada iklan yang ditampilkan di aplikasi

**Pemetaan event**:

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_ad\_click | AdClick | - | InAppADClick | AD\_CLICK | - | - |

**Parameter umum:**

Klik tautan untuk melihat pemetaan ke SRN.

* [af\_adrev\_ad\_type](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="ad-view-af_ad_view" />

<Accordion title="Tampilan iklan (af_ad_view)">

**Deskripsi**: Digunakan untuk mencatat tampilan iklan pada iklan yang ditampilkan di app

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_ad\_view | AdImpression | - | InAppADImpr | AD\_VIEW | - | - |

**Parameter umum:**

Klik tautan untuk melihat pemetaan ke SRN.

* [af\_adrev\_ad\_type](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="Tambahkan info pembayaran (af_add_payment_info)">

**Deskripsi**: Digunakan untuk mencatat status konfigurasi info pembayaran

**Muncul pada vertikal berikut:** <Anchor target="_blank" href="/marketers/id/docs/recommended-ride-hailing-app-events#add-payment-info-af_add_payment_info">Ride-hailing</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-flight-booking-app-events#add-payment-info-af_add_payment_info">Pemesanan penerbangan</Anchor>

**Pemetaan event**:

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_add\_payment\_info | fb\_mobile\_add\_payment\_info | add\_payment\_info | AddPaymentInfo | ADD\_BILLING | ADDED\_PAYMENT\_INFO | ADD\_BILLING |

**Parameter umum:**

Klik tautan untuk melihat pemetaan ke SRN.

* [af\_success](/docs/in-app-events-event-structure#af_success)

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="Tambahkan ke keranjang (af_add_to_cart)">

**Deskripsi**: Digunakan untuk mencatat event tambah ke keranjang dari item tertentu. Untuk melaporkan event yang berisi banyak item, klik <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">di sini</Anchor>.

**Muncul di vertikal berikut:** <Anchor target="_blank" href="/marketers/id/docs/recommended-ecommerce-app-events#add-to-cart-af_add_to_cart">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-healthcare-app-events#add-to-cart-af_add_to_cart">Perawatan Kesehatan</Anchor>

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_add\_to\_cart | fb\_mobile\_add\_to\_cart | add\_to\_cart | AddToCart | ADD\_CART | ADD\_TO\_CART | viewBasket |

**Parameter umum:**

Klik tautan untuk melihat pemetaan ke SRN.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="Tambahkan ke wishlist (af_add_to_wishlist)">

**Deskripsi**: Digunakan untuk mencatat event add to wishlist dari item tertentu. Untuk melaporkan event yang berisi banyak item, klik <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">di sini</Anchor>.

**Muncul di vertikal berikut:** <Anchor target="_blank" href="/marketers/id/docs/recommended-ecommerce-app-events#add-to-wishlist-af_add_to_wishlist">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-hotel-booking-app-events#add-to-wishlist-af_add_to_wishlist">Pemesanan hotel</Anchor>

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_add\_to\_wishlist | fb\_mobile\_add\_to\_wishlist | add\_to\_wishlist | AddToWishlist | ADD\_TO\_WISHLIST | ADD\_TO\_WISHLIST | - |

**Parameter umum:**

Klik tautan untuk melihat pemetaan ke SRN.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Selesaikan pendaftaran (af_complete_registration)">

**Deskripsi**: Digunakan untuk mencatat metode registrasi pengguna

**Muncul di vertikal berikut:** <Anchor target="_blank" href="/marketers/id/docs/recommended-gaming-app-events#complete-registration-af_complete_registration">Gaming</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-ecommerce-app-events#complete-registration-af_complete_registration">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-entertainment-app-events#complete-registration-af_complete_registration">Hiburan</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-finance-and-banking-app-events#complete-registration-af_complete_registration">Keuangan dan perbankan</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-p2p-lending-app-events#complete-registration-af_complete_registration">Pinjaman P2P</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-online-education-app-events#complete-registration-af_complete_registration">Pendidikan online</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-ride-hailing-app-events#complete-registration-af_complete_registration">Ride-hailing</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-hotel-booking-app-events#complete-registration-af_complete_registration">Pemesanan hotel</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-healthcare-app-events#complete-registration-af_complete_registration">Perawatan kesehatan</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-telecommunication-app-events#complete-registration-af_complete_registration">Telekomunikasi</Anchor>

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_complete\_registration | fb\_mobile\_complete\_registration | sign\_up | Registration | SIGN\_UP | SIGN\_UP | - |

**Parameter umum:**

Klik tautan untuk melihat pemetaan ke SRN.

* [af\_registration\_method](/docs/in-app-events-event-structure#af_registration_method)

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Tampilan konten (af_content_view)">

**Deskripsi**: Digunakan untuk mencatat event tampilan konten. Untuk melaporkan event yang berisi banyak item, klik <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">di sini</Anchor>.

**Muncul di vertikal berikut:** <Anchor target="_blank" href="/marketers/id/docs/recommended-ecommerce-app-events#content-view-af_content_view">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-flight-booking-app-events#content-view-af_content_view">Pemesanan penerbangan</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-hotel-booking-app-events#content-view-af_content_view">Pemesanan hotel</Anchor>

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_content\_view | fb\_mobile\_content\_view | view\_item | ViewContent | VIEW\_CONTENT | CONTENT\_VIEW | viewProduct |

**Parameter umum:**

Klik parameter yang relevan dengan kebutuhan bisnis Anda untuk melihat pemetaan ke SRN.

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

<Accordion title="Pembayaran yang dimulai (af_initiated_checkout)">

**Keterangan**: Digunakan untuk mencatat kejadian checkout. Untuk melaporkan event yang berisi banyak item, klik <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">di sini</Anchor>.

**Muncul dalam vertikal:** <Anchor target="_blank" href="/marketers/id/docs/recommended-ecommerce-app-events#initiated-checkout-af_initiated_checkout">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-hotel-booking-app-events#initiated-checkout-af_initiated_checkout">Pemesanan hotel</Anchor>

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_initiated\_checkout | fb\_mobile\_initiated\_checkout | begin\_checkout | Checkout | START\_CHECKOUT | CHECKOUT\_INITIATED | viewBasket |

**Parameter umum:**

Klik parameter yang relevan dengan kebutuhan bisnis Anda untuk melihat pemetaan ke SRN.

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

<Accordion title="Undang (af_invite)">

**Deskripsi**: Digunakan untuk mencatat event mengundang (sosial media)

**Muncul di vertikal berikut:** <Anchor target="_blank" href="/marketers/id/docs/recommended-gaming-app-events#invite-af_invite">Gaming</Anchor>

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_invite | - | invite | - | INVITE | INVITE | - |

**Parameter umum:**

Klik tautan untuk melihat pemetaan ke SRN.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="level-achieved-af_level_achieved" />

<Accordion title="Level tercapai (af_level_achieved)">

**Deskripsi**: Digunakan untuk mencatat event level game

**Muncul di vertikal berikut:** <Anchor target="_blank" href="/marketers/id/docs/recommended-gaming-app-events#level-achieved-af_level_achieved">Gaming</Anchor>

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_level\_achieved | fb\_mobile\_level\_achieved | level\_up | AchieveLevel | LEVEL\_COMPLETE | LEVEL\_ACHIEVED | userLevel |

**Parameter umum:**

Klik tautan untuk melihat pemetaan ke SRN.

* [af\_level](/docs/in-app-events-event-structure#af_level)
* [af\_score](/docs/in-app-events-event-structure#af_score)

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="Tampilan daftar (af_list_view)">

**Deskripsi**: Digunakan untuk mencatat event tampilan daftar

**Muncul di vertikal berikut:** <Anchor target="_blank" href="/marketers/id/docs/recommended-ecommerce-app-events#list-view-af_list_view">eCommerce</Anchor>

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_list\_view | - | view\_item\_list | - | LIST\_VIEW | - | viewListing |

**Parameter umum:**

Klik tautan untuk melihat pemetaan ke SRN.

* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)

</Accordion>

<div id="login-af_login" />

<Accordion title="Masuk (af_login)">

**Deskripsi**: Digunakan untuk mencatat event login pengguna

**Muncul di vertikal berikut:** <Anchor target="_blank" href="/marketers/id/docs/recommended-gaming-app-events#login-af_login">Gaming</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-ecommerce-app-events#login-af_login">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-entertainment-app-events#login-af_login">Hiburan</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-finance-and-banking-app-events#login-af_login">Keuangan dan perbankan</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-online-education-app-events#login-af_login">Pendidikan online</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-hotel-booking-app-events#login-af_login">Pemesanan hotel</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-healthcare-app-events#login-af_login">Perawatan kesehatan</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-telecommunication-app-events#login-af_login">Telekomunikasi</Anchor>

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_login | - | login | Login | - | LOGIN | - |

</Accordion>

<div id="opened-from-push-notification-af_opened_from_push_notification" />

<Accordion title="Dibuka dari notifikasi push (af_opened_from_push_notification)">

**Deskripsi**: Digunakan untuk mencatat aplikasi yang dibuka dari event notifikasi push

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_opened\_from\_push\_notification | - | notification\_open | - | - | - | - |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Pembelian (af_purchase)">

**Deskripsi**: Digunakan untuk mencatat event pembelian (dan mengaitkan pendapatan dengannya). Untuk daftar simbol mata uang yang didukung oleh AppsFlyer, klik <Anchor target="_blank" href="https://docs.openexchangerates.org/docs/supported-currencies">di sini</Anchor>. Untuk melaporkan event yang berisi banyak item, klik <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">di sini</Anchor>.

**Muncul dalam vertikal:** <Anchor target="_blank" href="/marketers/id/docs/recommended-gaming-app-events#purchase-af_purchase">Gaming</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-ecommerce-app-events#purchase-af_purchase">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-online-education-app-events#purchase-af_purchase">Pendidikan online</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-healthcare-app-events#purchase-af_purchase">Perawatan Kesehatan</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-telecommunication-app-events#purchase-af_purchase">Telekomunikasi</Anchor>

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_purchase | fb\_mobile\_purchase | in\_app\_purchase | Purchase | PURCHASE | PURCHASE | transactionConfirmation |

**Parameter umum:**

Klik parameter yang relevan dengan kebutuhan bisnis Anda untuk melihat pemetaan ke SRN.

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

<Accordion title="Nilai (af_rate)">

**Deskripsi**: Digunakan untuk merekam event rating aplikasi/item. Untuk melaporkan event yang berisi banyak item, klik <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">di sini</Anchor>.

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_rate | fb\_mobile\_rate | submit\_rating | Rating | RATE | RATED | - |

**Parameter umum:**

Klik tautan untuk melihat pemetaan ke SRN.

* [af\_rating\_value](/docs/in-app-events-event-structure#af_rating_value)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_max\_rating\_value](/docs/in-app-events-event-structure#af_max_rating_value)

</Accordion>

<div id="reengage-af_re_engage" />

<Accordion title="Interaksi Ulang (af_re_engage)">

**Deskripsi**: Digunakan untuk mencatat event interaksi ulang pengguna

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_re\_engage | - | custom\_event | - | RE\_ENGAGE | - |

**Parameter umum:**

Klik tautan untuk melihat pemetaan ke SRN.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="search-af_search" />

<Accordion title="Cari (af_search)">

**Deskripsi**: Digunakan untuk mencatat event pencarian

**Muncul di vertikal berikut:** <Anchor target="_blank" href="/marketers/id/docs/recommended-ecommerce-app-events#search-af_search">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-flight-booking-app-events#search-af_search">Pemesanan penerbangan</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-hotel-booking-app-events#search-af_search">Pemesanan hotel</Anchor>

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_search | fb\_mobile\_search | view\_search\_results | Pencarian | - | SEARCH | viewSearch |

**Parameter umum:**

Klik parameter yang relevan dengan kebutuhan bisnis Anda untuk melihat pemetaan ke SRN.

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

<Accordion title="Bagikan (af_share)">

**Deskripsi**: Digunakan untuk mencatat event berbagi

**Muncul di vertikal berikut:** <Anchor target="_blank" href="/marketers/id/docs/recommended-gaming-app-events#share-af_share">Gaming</Anchor>

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_share | - | share | - | SHARE | SHARE | - |

**Parameter umum:**

Klik tautan untuk melihat pemetaan ke SRN.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="spent-credits-af_spent_credits" />

<Accordion title="Kredit yang dihabiskan (af_spent_credits)">

**Deskripsi**: Digunakan untuk mencatat event pengeluaran kredit. Untuk melaporkan event yang berisi banyak item, klik <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">di sini</Anchor>.

**Muncul secara vertikal:** <Anchor target="_blank" href="/marketers/id/docs/recommended-ride-hailing-app-events#spent-credits-af_spent_credits">Ride-hailing</Anchor>

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_spent\_credits | fb\_mobile\_spent\_credits | spend\_virtual\_currency | SpendCredits | SPENT\_CREDITS | SPENT\_CREDITS | transactionConfirmation |

**Parameter umum:**

Klik tautan untuk melihat pemetaan ke SRN.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="start-trial-af_start_trial" />

<Accordion title="Mulai uji coba (af_start_trial)">

**Deskripsi**: Digunakan untuk mencatat awal uji coba gratis suatu produk

**Muncul di vertikal berikut:** <Anchor target="_blank" href="/marketers/id/docs/recommended-entertainment-app-events#start-trial-af_start_trial">Hiburan</Anchor>

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_start\_trial | StartTrial | - | StartTrial | START\_TRIAL | - | - |

**Parameter umum:**

Klik tautan untuk melihat pemetaan ke SRN.

* [af\_price](/docs/in-app-events-event-structure#af_price)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

<div id="note" />

> 📘 **Catatan**
>
> Jika Anda memetakan event ini ke event StartTrial Meta ads dan ingin mengaitkan pendapatan, gunakan parameter af\_price, bukan parameter af\_revenue.

</Accordion>

<div id="subscription-af_subscribe" />

<Accordion title="Berlangganan (af_subscribe)">

**Deskripsi**: Digunakan untuk mencatat pembelian langganan berbayar

**Muncul di vertikal berikut:** <Anchor target="_blank" href="/marketers/id/docs/recommended-entertainment-app-events#subscription-af_subscribe">Hiburan</Anchor>

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_subscribe | Subscribe | - | Subscribe | - | - | SUBSCRIBE |

**Parameter umum:**

Klik tautan untuk melihat pemetaan ke SRN.

* [af\_revenue](/docs/in-app-events-event-structure#af_revenue)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="Pemesanan travel (af_travel_booking)">

**Deskripsi**: Digunakan untuk mencatat event pemesanan travel (dan mengaitkan pendapatan ke pemesanan travel) Untuk melaporkan event yang berisi banyak item, klik <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">di sini</Anchor>.

**Muncul di vertikal berikut:** <Anchor target="_blank" href="/marketers/id/docs/recommended-flight-booking-app-events#travel-booking-af_travel_booking">Pemesanan penerbangan</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-hotel-booking-app-events#travel-booking-af_travel_booking">Pemesanan hotel</Anchor>

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_travel\_booking | fb\_mobile\_purchase | ecommerce\_purchase | Purchase | RESERVE | PURCHASE | transactionConfirmation |

**Parameter umum:**

Klik parameter yang relevan dengan kebutuhan bisnis Anda untuk melihat pemetaan ke SRN.

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

<Accordion title="Penyelesaian tutorial (af_tutorial_completion)">

**Deskripsi**: Digunakan untuk mencatat penyelesaian tutorial. Untuk melaporkan event yang berisi banyak item, klik <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">di sini</Anchor>.

**Muncul di vertikal berikut:** <Anchor target="_blank" href="/marketers/id/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">Game</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">Pendidikan online</Anchor>

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | TikTok | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- | --- |
| af\_tutorial\_completion | fb\_mobile\_tutorial\_completion | tutorial\_complete | CompleteTutorial | COMPLETE\_TUTORIAL | TUTORIAL\_COMPLETE | - |

**Parameter umum:**

Klik tautan untuk melihat pemetaan ke SRN.

* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="update-af_update" />

<Accordion title="Pembaruan (af_update)">

**Deskripsi**: Digunakan untuk mencatat event pembaruan. Untuk melaporkan event yang berisi banyak item, klik <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">di sini</Anchor>.

**Pemetaan event:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_update | - | app\_update | - | UPDATE | - |

**Parameter umum:**

Klik tautan untuk melihat pemetaan ke SRN.

* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)

</Accordion>

<div id="note-1" />

> 📘 **Catatan**
>
> Selain nama event yang telah ditentukan yang dijelaskan di bagian ini, <Anchor target="_blank" href="/marketers/id/docs/meta-ads-in-app-event-mapping#pemetaan-event-yang-telah-ditentukan-sebelumnya">Meta ads menawarkan event tambahan</Anchor> yang dikirim tanpa atribut.

<div id="predefined-event-parameters" />

## Parameter event yang telah ditentukan sebelumnya

Bagian berikut menyediakan daftar parameter event yang telah ditentukan sebelumnya. Setiap parameter peristiwa menyertakan pemetaan yang digunakan untuk Meta ads, Google Ads, Snap, Twitter, dan Criteo. Anda dapat memilih untuk menyertakan salah satu parameter peristiwa dalam suatu event.

<div id="note-2" />

> 📘 **Catatan**
>
> Anda dapat melihat parameter event di kolom Nilai Event di <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">laporan data lengkap</Anchor> (fitur premium).

<div id="af_adrev_ad_type" />

<Accordion title="af_adrev_ad_type">

**Deskripsi**: Jenis iklan (misalnya, spanduk atau interstitial)

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_adrev\_ad\_type | ad\_type | - | - | - | - |

</Accordion>

<div id="af_city" />

<Accordion title="af_city">

**Deskripsi**: Kota tempat perjalanan dipesan

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_city | fb\_city | - | - | - | - |

</Accordion>

<div id="af_class" />

<Accordion title="af_class">

**Deskripsi**: Kelas perjalanan dipesan untuk penerbangan

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_class | fb\_travel\_class | travel\_class | - | - | - |

</Accordion>

<div id="af_content" />

<Accordion title="af_content">

**Deskripsi**: Judul konten (misalnya, nama lagu atau judul dan episode acara TV)

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_content | fb\_content | - | - | - | - |

</Accordion>

<div id="af_content_id" />

<Accordion title="af_content_id">

**Deskripsi**: ID item

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_content\_id | fb\_content\_id | item\_id | item\_ids | content\_id | id |

</Accordion>

<div id="af_content_list" />

<Accordion title="af_content_list">

**Deskripsi**: Daftar ID konten

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_content\_list | - | item\_id | - | - | - |

</Accordion>

<div id="af_content_type" />

<Accordion title="af_content_type">

**Deskripsi**: Kategori produk

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_content\_type | fb\_content\_type | item\_category | item\_category | content\_type | - |

</Accordion>

<div id="af_country" />

<Accordion title="af_country">

**Deskripsi**: Negara tempat perjalanan dipesan

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_country | fb\_country | - | - | - | - |

</Accordion>

<div id="af_currency" />

<Accordion title="af_currency">

**Deskripsi**: Kode mata uang

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_currency | fb\_currency | currency\_code | currency | price\_currency | currency |

</Accordion>

<div id="af_customer_user_id" />

<Accordion title="af_customer_user_id">

**Deskripsi**: ID pelanggan

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_customer\_user\_id | - | customer\_user\_  <br />id | - | - | cid |

</Accordion>

<div id="af_date_a" />

<Accordion title="af_date_a">

**Deskripsi**: Tanggal masuk

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_date\_a | fb\_checkin\_date | start\_date | - | - | din |

</Accordion>

<div id="af_date_b" />

<Accordion title="af_date_b">

**Deskripsi**: Tanggal keluar

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_date\_b | fb\_checkout\_date | end\_date | - | - | dout |

</Accordion>

<div id="af_departing_arrival_date" />

<Accordion title="af_departing_arrival_date">

**Deskripsi**: Tanggal kedatangan

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_departing\_arrival\_date | fb\_departing\_arrival\_date | - | - | - | - |

</Accordion>

<div id="af_departing_departure_date" />

<Accordion title="af_departing_departure_date">

**Deskripsi**: Tanggal keberangkatan

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_departing\_departure\_date | fb\_departing\_departure\_date | - | - | - | - |

</Accordion>

<div id="af_description" />

<Accordion title="af_description">

**Deskripsi**: Deskripsi singkat (string)

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_description | fb\_description | deskripsi | deskripsi | deskripsi | ui\_achievement |

</Accordion>

<div id="af_destination_a" />

<Accordion title="af_destination_a">

**Deskripsi**: Tujuan pertama

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_destination\_a | fb\_origin\_airport | asal | - | - | - |

</Accordion>

<div id="af_destination_b" />

<Accordion title="af_destination_b">

**Deskripsi**: Tujuan kedua

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_destination\_b | fb\_tujuan\_  <br />Bandara | destination | - | - | - |

</Accordion>

<div id="af_destination_list" />

<Accordion title="af_destination_list">

**Deskripsi**: Daftar tujuan yang masuk dalam katalog tujuan (misalnya, daftar museum atau restoran yang ada di dekat hotel)

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_destination\_list | fb\_destination\_ids | - | - | - | - |

</Accordion>

<div id="af_hotel_score" />

<Accordion title="af_hotel_score">

**Deskripsi**: Skor hotel berdasarkan ulasan

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_hotel\_score | fb\_hotel\_score | - | - | - | - |

</Accordion>

<div id="af_level" />

<Accordion title="af_level">

**Deskripsi**: Level yang dicapai pengguna

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_level | fb\_level | level\_up | level | level | ui\_level |

</Accordion>

<div id="af_max_rating_value" />

<Accordion title="af_max_rating_value">

**Deskripsi**: Ujung atas skala peringkat (misalnya, 5 dari 5)

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_max\_rating\_value | fb\_max\_rating\_value | max\_rating | - | max\_rated\_value | - |

</Accordion>

<div id="af_num_adults" />

<Accordion title="af_num_adults">

**Deskripsi**: Jumlah orang dewasa yang bepergian

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_num\_adults | fb\_num\_adults | - | - | - | - |

</Accordion>

<div id="af_num_children" />

<Accordion title="af_num_children">

**Deskripsi**: Jumlah anak yang bepergian

Pemetaan parameter:

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_num\_children | fb\_num\_children | - | - | - | - |

</Accordion>

<div id="af_num_infants" />

<Accordion title="af_num_infants">

**Deskripsi**: Jumlah bayi yang bepergian

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_num\_infants | fb\_num\_infants | - | - | - | - |

</Accordion>

<div id="af_order_id" />

<Accordion title="af_order_id">

**Deskripsi**: ID transaksi

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_order\_id | fb\_order\_id | order\_id | transaction\_id | - | transaction\_id |

</Accordion>

<div id="af_payment_info_available" />

<Accordion title="af_payment_info_available">

**Deskripsi**: Apakah informasi pembayaran pengguna tersedia atau tidak

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_payment\_info\_available | fb\_payment\_info\_available | payment\_info\_  <br />available | payment\_info\_available | user\_payment\_  <br />info | - |

</Accordion>

<div id="af_preferred_neighborhoods" />

<Accordion title="af_preferred_neighborhoods">

**Deskripsi**: Area di mana hotel berada

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_preferred\_neighborhoods | fb\_preferred\_neighborhoods | - | - | - | - |

</Accordion>

<div id="af_preferred_num_stops" />

<Accordion title="af_preferred_num_stops">

**Deskripsi**: Jumlah perhentian yang dicari pengguna (misalnya, penerbangan nonstop atau langsung)

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_preferred\_num\_stops | fb\_preferred\_num\_stops | - | - | - | - |

</Accordion>

<div id="af_preferred_price_range" />

<Accordion title="af_preferred_price_range">

**Deskrips**: Kisaran harga hotel yang lebih disukai

Pemetaan parameter:

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_preferred\_price\_range | fb\_preferred\_price\_range | - | - | - | - |

</Accordion>

<div id="af_preferred_star_ratings" />

<Accordion title="af_preferred_star_ratings">

**Deskripsi**: Peringkat bintang hotel yang lebih disukai

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_preferred\_star\_ratings | fb\_preferred\_star\_ratings | - | - | - | - |

</Accordion>

<div id="af_price" />

<Accordion title="af_price">

**Deskripsi**: Harga produk. Anda dapat menggunakan af\_price sebagai parameter moneter yang tidak dihitung sebagai pendapatan (seperti event Tambahkan ke keranjang). Parameter ini mengacu pada harga masing-masing item. Jumlah total semua pembelian ditampilkan di bawah parameter [af\_revenue](/docs/in-app-events-event-structure#af_revenue) .

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_price | fb\_price | price | price | price\_micro | price |

</Accordion>

<div id="af_purchase_currency" />

<Accordion title="af_purchase_currency">

**Deskripsi**: Mata uang yang digunakan untuk pembelian

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_purchase\_currency | fb\_purchase\_currency | - | - | - | - |

</Accordion>

<div id="af_quantity" />

<Accordion title="af_quantity">

**Deskripsi**: Jumlah item

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_quantity | fb\_num\_items | jumlah | number\_items | number\_items | jumlah |

</Accordion>

<div id="af_rating_value" />

<Accordion title="af_rating_value">

**Deskripsi**: Nilai peringkat yang dipilih

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_rating\_value | \_valueToSum | value | - | price\_micro | - |

</Accordion>

<div id="af_receipt_id" />

<Accordion title="af_receipt_id">

**Deskripsi**: ID kuitansi

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_receipt\_id | - | transaction\_id | - | - | transaction\_id |

</Accordion>

<div id="af_region" />

<Accordion title="af_region">

**Deskripsi**: Wilayah tempat perjalanan dipesan

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_region | fb\_region | - | - | - | - |

</Accordion>

<div id="af_registration_method" />

<Accordion title="af_registration_method">

**Deskripsi**: Jenis metode pendaftaran

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_registration\_method | fb\_registration\_method | registration\_method | sign\_up\_method | registration\_method | - |

</Accordion>

<div id="af_returning_arrival_date" />

<Accordion title="af_returning_arrival_date">

**Deskripsi**: Tanggal dan waktu perjalanan pulang selesai

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_returning\_arrival\_date | fb\_returning\_arrival\_date | - | - | - | - |

</Accordion>

<div id="af_returning_departure_date" />

<Accordion title="af_returning_departure_date">

**Deskripsi**:  Tanggal dan waktu perjalanan pulang dimulai

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_returning\_departure\_date | fb\_returning\_departure\_date | - | - | - | - |

</Accordion>

<div id="af_revenue" />

<Accordion title="af_revenue">

**Deskripsi**: Total jumlah pembelian. af\_revenue dihitung sebagai pendapatan di platform AppsFlyer. Ini juga menghitung <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#revenue-events">pendapatan negatif</Anchor>, dari pembatalan atau pengembalian dana.

<div id="important" />

> 🚧 **Penting!**
>
> Nilai pendapatan tidak boleh berisi pemisah koma, mata uang, karakter khusus, atau teks. Misalnya, nilai pendapatan seharusnya, 1234,56. AppsFlyer memberikan nilai pendapatan dengan akurasi hingga lima desimal.

Untuk mempelajari lebih lanjut tentang cara menggunakan parameter pendapatan, klik <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#revenue-events">di sini</Anchor>.

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_revenue | \_valueToSum | value | price | price\_micro | ui\_revenue |

</Accordion>

<div id="af_score" />

<Accordion title="af_score">

**Deskripsi**: Skor yang terkait dengan pencapaian pengguna

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_score | - | - | - | score | - |

</Accordion>

<div id="af_search_string" />

<Accordion title="af_search_string">

**Deskripsi**: Istilah pencarian

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_search\_string | fb\_search\_string | search\_string | search\_string | search\_string | - |

</Accordion>

<div id="af_subscription_id" />

<Accordion title="af_subscription_id">

**Deskripsi**: ID Langganan untuk pengguna

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_subscription\_id | subscription\_id | - | - | - | - |

</Accordion>

<div id="af_success" />

<Accordion title="af_success">

**Deskripsi**: Apakah penyelesaian tindakan berhasil

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_success | fb\_success | success | success | - | - |

</Accordion>

<div id="af_suggested_destinations" />

<Accordion title="af_suggested_destinations">

**Deskripsi**: Daftar tujuan yang disarankan

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_suggested\_destinations | fb\_suggested\_destinations | - | - | - | - |

</Accordion>

<div id="af_suggested_hotels" />

<Accordion title="af_suggested_hotels">

**Deskripsi**: Daftar hotel yang disarankan

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_suggested\_hotels | fb\_suggested\_hotels | - | - | - | - |

</Accordion>

<div id="af_travel_end" />

<Accordion title="af_travel_end">

**Deskripsi**: Tanggal akhir perjalanan

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_travel\_end | fb\_travel\_end | - | - | - | - |

</Accordion>

<div id="af_travel_start" />

<Accordion title="af_travel_start">

**Deskripsi**: Tanggal mulai perjalanan

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_travel\_start | fb\_travel\_start | - | - | - | - |

</Accordion>

<div id="af_user_score" />

<Accordion title="af_user_score">

**Deskripsi**: Signifikansi relatif dari pengguna terhadap pemasang iklan

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_user\_score | fb\_user\_score | - | - | - | - |

</Accordion>

<div id="af_validated" />

<Accordion title="af_validated">

**Deskripsi**: Memvalidasi pembelian

**Pemetaan parameter:**

| AppsFlyer | Iklan Meta | Google Ads | Snap | Twitter | Criteo |
| --- | --- | --- | --- | --- | --- |
| af\_validated | - | validated | success | - | - |

</Accordion>

Berikut adalah daftar parameter event yang telah ditentukan sebelumnya yang tidak menyertakan pemetaan SRN:

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

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration">Konfigurasi postback in-app event</Anchor>

<div data-zendesk-anchors="h_01H9HT8C713A4NV9WCB0FJZJ4R=overview predefined-event-names=nama-event-yang-telah-ditentukan-sebelumnya h_01H9HT8C7189W1JXAR3J3KT8KV=nama-event-yang-telah-ditentukan-sebelumnya h_01H9HT8C71MV7V7C75MB6ESHMM=achievement-unlocked-af_achievement_unlocked h_01H9HT8C7171PB7KAC83MYBWQ8=ad-click-af_ad_click h_01H9HT8C72KJ6ZA663SH7HJ7MP=ad-view-af_ad_view h_01H9HT8C72HSM88DJG0PDV5140=add-payment-info-af_add_payment_info h_01H9HT8C72BWFSPKWDVQW926WG=add-to-cart-af_add_to_cart h_01H9HT8C7228B57XKAACPZG8NK=add-to-wishlist-af_add_to_wishlist h_01H9HT8C72DX0DXBDHRJFG19G2=complete-registration-af_complete_registration h_01H9HT8C72SPY9VQ9AD648AKZK=content-view-af_content_view h_01H9HT8C722T2VH6A9257Q7T4P=initiated-checkout-af_initiated_checkout h_01H9HT8C72F0RZ4JS9929SE465=invite-af_invite h_01H9HT8C72VFGC08Q858EX7XTN=level-achieved-af_level_achieved h_01H9HT8C72DZW77YTQ9KB0XEVG=list-view-af_list_view h_01H9HT8C720W10QEBCTPAGMRFB=login-af_login h_01H9HT8C72QC4WV10Z4JZTZM7D=opened-from-push-notification-af_opened_from_push_notification h_01H9HT8C7263J0YSX5K10R497N=purchase-af_purchase h_01H9HT8C73MPYMG8KSYE04DKDZ=rate-af_rate h_01H9HT8C734DAC6GPJE58DB5JD=reengage-af_re_engage h_01H9HT8C73YSYBK0YSDPRWDBNW=search-af_search h_01H9HT8C734GJ07V67QC9V3TVC=share-af_share h_01H9HT8C73H4VT2M0P3M1SYG88=spent-credits-af_spent_credits h_01H9HT8C73YWDCKAZPY0BVRS6F=start-trial-af_start_trial h_01H9HT8C736BF2VNRCFSJSVXWS=catatan h_01H9HT8C73N69S45H82NWQ5FN1=subscription-af_subscribe h_01H9HT8C73CD6HNT5GA6B4CHQ9=travel-booking-af_travel_booking h_01H9HT8C73NFDPS1P5AVXXZEX7=tutorial-completion-af_tutorial_completion h_01H9HT8C73JPH6Q9XFKA3GNYT8=update-af_update h_01H9HT8C74SGGK2FW92JH4BJPZ=catatan-1 predefined-event-parameters=parameter-event-yang-telah-ditentukan-sebelumnya h_01H9HT8C74N4TJZ5ZVBTKAX810=parameter-event-yang-telah-ditentukan-sebelumnya h_01H9HT8C74VQ9ZWF079V50E5HE=catatan-2 h_01H9HT8C74Y0BWS565DFTY75KJ=af_adrev_ad_type h_01H9HT8C742NHGXFKWSS4P07K2=af_city h_01H9HT8C7442PFZEK7QC6R0K67=af_class h_01H9HT8C7462KG3030WWZ2XGZW=af_content h_01H9HT8C74ZX07907NXFHKGJ91=af_content_id h_01H9HT8C744CMWSYHJB74JFSS5=af_content_list h_01H9HT8C74GKGG5V4X54BCAADC=af_content_type h_01H9HT8C74RD08Z9EBZTKY5KSD=af_country h_01H9HT8C75BJYK4R3WYSN4BF43=af_currency h_01H9HT8C752E2PK6QKTA2GNGH5=af_customer_user_id h_01H9HT8C75BN0A92X9BRY4A74T=af_date_a h_01H9HT8C75406KV9264ZZT9DKM=af_date_b h_01H9HT8C7526AEHJAA7FM7442E=af_departing_arrival_date h_01H9HT8C75W9X61ZH0849EPDBY=af_departing_departure_date h_01H9HT8C75VEV3C8CJBDN6X5HW=af_description h_01H9HT8C75Z8TBZEPEY9EGSR4Y=af_destination_a h_01H9HT8C751G216VB6GYTPEPE1=af_destination_b h_01H9HT8C75CVM0MHSKTK2CZ8HD=af_destination_list h_01H9HT8C75CVVDFABSTN5R4MWT=af_hotel_score h_01H9HT8C75GEMHE2NHEFK9J7NT=af_level h_01H9HT8C7505H4CMY70EMDQWSF=af_max_rating_value h_01H9HT8C75ST9XBDC3SR6XFDPB=af_num_adults h_01H9HT8C75NNZ5NP6PRPXDSKP8=af_num_children h_01H9HT8C757X70AAGNWFV0CKRY=af_num_infants h_01H9HT8C75A0HESE5FD10VD1P8=af_order_id h_01H9HT8C75B488VKY8SW9M4GG4=af_payment_info_available h_01H9HT8C75W7SRB0KF4E5FB2YF=af_preferred_neighborhoods h_01H9HT8C75GC61D1A0P6P42TMR=af_preferred_num_stops h_01H9HT8C76XRY6CD1TJEPCJJTR=af_preferred_price_range h_01H9HT8C76Y9ZQQ2X4EJT2DC14=af_preferred_star_ratings h_01H9HT8C76KCDRJKBWSM9JKFE1=af_price h_01H9HT8C767ZNWCBYC3X680PGQ=af_purchase_currency h_01H9HT8C76Y5VXBKF3TBVVJG1C=af_quantity h_01H9HT8C768WXZ126Q425PHDWX=af_rating_value h_01H9HT8C76XX9J6FZ6RWQB6B6R=af_receipt_id h_01H9HT8C760S0F7QZMFYW1BKRD=af_region h_01H9HT8C76N4S3SGES5SQ2J4AC=af_registration_method h_01H9HT8C76ZR36A4CM2PY6PJ10=af_returning_arrival_date h_01H9HT8C760JPVXYC5WH9ZSDPX=af_returning_departure_date h_01H9HT8C76PYB14WPCQKSEK69J=af_revenue h_01H9HT8C762BGPRHFX228APEHR=penting h_01H9HT8C76P55HN8K6D7PHFS2J=af_score h_01H9HT8C76TB4KNTZVD6JVPEYQ=af_search_string h_01H9HT8C762R2PJ573W8TJFJHG=af_subscription_id h_01H9HT8C76VZ6FA20K471V0EKK=af_success h_01H9HT8C76029H94AY5EHCZX6X=af_suggested_destinations h_01H9HT8C76N6C694TCPVCK4EC3=af_suggested_hotels h_01H9HT8C765EM1SAEJ67FNXZDE=af_travel_end h_01H9HT8C76YP8VEM5E6WB9NQ7T=af_travel_start h_01H9HT8C771SYQWQ8VBTPA2V2E=af_user_score h_01H9HT8C771XFSQJX42QVBNZAJ=af_validated h_01HDNZ30NH2QXSHD7B4EMFG4T5=lihat-juga" />
