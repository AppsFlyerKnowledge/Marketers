---
title: Pengenal perangkat
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2021-10-12T14:16:09Z'
  edited_at: '2023-11-24T08:30:02Z'
  id: 4408847686161
  locale: id
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/id/articles/4408847686161
---
> **Sekilas:** Memahami pengidentifikasi perangkat yang didukung di SDK AppsFlyer.

<div id="overview" />

## Ringkasan

SDK AppsFlyer mengumpulkan pengidentifikasi perangkat untuk <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#atribusi">tujuan atribusi</Anchor>. Pengidentifikasi dapat membantu Anda memetakan perjalanan pengguna dan memahami preferensi mereka.

SDK secara otomatis mengumpulkan pengidentifikasi seperti ID AppsFlyer dan ID Google Advertising (GAID). Mengumpulkan pengidentifikasi lain untuk aplikasi Anda bergantung pada kebutuhan Anda (misalnya, mengumpulkan app store Android pihak ketiga atau aplikasi yang dipasarkan di Tiongkok).

## Pengidentifikasi perangkat untuk semua platform

SDK mendukung pengidentifikasi perangkat berikut untuk semua platform:

| Pengenal perangkat | Tujuan |
| --- | --- |
| <span id="appsflyer-id"></span>AppsFlyer ID | ID AppsFlyer secara otomatis dibuat untuk setiap penginstalan aplikasi. Anda dapat menggunakan pengidentifikasi ini untuk melakukan tindakan berikut:<ul><li>Mengirim <Anchor target="_blank" href="/marketers/id/docs/server-to-server-events-api-for-mobile-s2s-mobile">in-app event server ke server</Anchor> .</li><li>Cocokkan ID AppsFlyer dengan catatan pengguna di sistem back end</li><li>Memetakan entri saat menggabungkan data dari pull dan push API.</li></ul> |
| <span id="customer-user-id"></span>ID User Pelanggan | Bidang <Anchor target="_blank" href="/marketers/id/docs/customer-user-id-field-cuid">ID pengguna Pelanggan (CUID)</Anchor> adalah pengidentifikasi unik yang ditetapkan oleh pemilik aplikasi dan situs web. Mengatur CUID Anda sendiri di SDK AppsFlyer memungkinkan Anda melakukan referensi silang ID unik Anda dengan ID AppsFlyer dan pengidentifikasi lainnya. CUID tersedia di laporan <Anchor target="_blank" href="/marketers/id/docs/raw-data-field-dictionary">data lengkap</Anchor> AppsFlyer. Anda juga dapat menggunakannya di API postback untuk melakukan referensi silang dengan ID internal Anda. |

<div id="android-device-identifiers" />

## Pengidentifikasi perangkat Android

SDK mendukung pengidentifikasi perangkat berikut untuk platform Android:

<div id="apps-published-on-google-play" />

#### Aplikasi dipublikasikan di Google Play

| Pengenal perangkat | Tujuan |
| --- | --- |
| <span id="gaid"></span>GAID | Pengidentifikasi **yang dapat diatur ulang pengguna** untuk pengguna Google Play Android.<br /><br />Mulai SDK V4.8.0, AppsFlyer secara otomatis mengumpulkan identifier perangkat ini. |

<div id="apps-published-in-third-party-app-stores" />

#### Aplikasi yang diterbitkan di app store pihak ketiga

| Pengenal perangkat | Tujuan |
| --- | --- |
| <span id="amazon-advertising-id"></span>ID Amazon Advertising | Pengidentifikasi unik **yang dapat diatur ulang pengguna** yang digunakan oleh Amazon Fire TV. <Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-platform-attribution-concepts">Lihat tinjauan CTV</Anchor> |
| <span id="oaid"></span>OAID | Pengidentifikasi **yang dapat diatur ulang pengguna** yang digunakan oleh beberapa pasar Android di luar store.  Untuk informasi lebih lanjut, lihat <Anchor target="_blank" href="/marketers/id/docs/android-oaid-implementation-in-the-sdk">Panduan penerapan OAID</Anchor>. |
| <span id="imei"></span>IMEI | Pengidentifikasi perangkat seluler unik dan **tidak dapat diatur ulang** yang digunakan di pasar non-Google Play. SDK tidak secara otomatis mengumpulkan IMEI. Namun, jika ada kebutuhan untuk mengumpulkan pengidentifikasi ini, pengembang Anda dapat mengimplementasikan pengumpulan.<br /><br />**Catatan:**<ul><li>Dimulai dengan Android 10, akses ke IMEI <Anchor target="_blank" href="https://developer.android.com/about/versions/10/privacy/changes#non-resettable-device-ids">dibatasi</Anchor>.</li><li>IMEI tidak dapat digunakan bersamaan dengan GAID.</li></ul> |
| <span id="android-id"></span>ID Android | Pengidentifikasi perangkat seluler unik dan **tidak dapat diatur ulang** yang digunakan di app store pihak ketiga. SDK tidak secara otomatis mengumpulkan ID Android. Namun, jika ada kebutuhan untuk mengumpulkan pengidentifikasi ini, pengembang Anda dapat mengimplementasikan pengumpulan.<br /><br />**Catatan:** ID Android tidak dapat digunakan bersama dengan GAID. |

<div id="apple-device-identifiers" />

## Pengidentifikasi perangkat Apple

SDK mendukung pengidentifikasi perangkat berikut untuk platform iOS:

| Pengenal perangkat | Tujuan |
| --- | --- |
| <span id="idfa"></span>idfa | Pengidentifikasi unik **yang dapat diatur ulang pengguna** untuk pengguna Apple iOS atau tvOS (Apple TV). Sejak rilis iOS 14.5, IDFA hanya tersedia jika pengguna menyetujui melalui <Anchor target="_blank" href="/marketers/id/docs/about-att-and-skan#att-principles">perintah ATT</Anchor>. |
| <span id="idfv"></span>IDFV | Pengidentifikasi perangkat bersama digunakan oleh semua aplikasi dari **vendor yang sama** di perangkat. Setelah aplikasi pertama diinstal, ID ditetapkan padanya, dan aplikasi lain dari vendor yang sama diberi IDFV yang sama. Aplikasi dari vendor lain diberi IDFV berbeda.<br /><br />Selain itu, ketika semua aplikasi dari vendor tertentu dihapus, IDFV untuk vendor tersebut akan dihapus, dan setelah penginstalan baru, IDFV baru akan ditetapkan. |

<div id="ctv--pc-and-console-app-device-identifiers" />

## Pengidentifikasi perangkat CTV

SDK mendukung pengidentifikasi perangkat berikut untuk platform CTV:

| Pengenal perangkat | Tujuan |
| --- | --- |
| <span id="rida"></span>RIDA | Untuk perangkat Roku CTV. <Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-platform-attribution-concepts">Lihat ikhtisar CTV</Anchor> |
| <span id="vida"></span>VIDA | Untuk perangkat Vizio CTV. <Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-platform-attribution-concepts">Lihat ikhtisar CTV</Anchor> |
| <span id="tifa"></span>TIFA | Untuk perangkat Samsung CTV. <Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-platform-attribution-concepts">Lihat ikhtisar CTV</Anchor> |
| <span id="lgudid"></span>LGUDID | Untuk perangkat LG CTV. <Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-platform-attribution-concepts">Lihat ikhtisar CTV</Anchor> |

<div data-zendesk-anchors="overview=ringkasan h_01H9YXEYC3PA271B3G3Y3GM9PS=ringkasan device-identifiers-for-all-platforms=pengidentifikasi-perangkat-untuk-semua-platform h_01H9YXEYC3RCB3RDBKRW19WYQD=pengidentifikasi-perangkat-untuk-semua-platform android-device-identifiers=pengidentifikasi-perangkat-android h_01H9YXEYC3D95A6G70EGNR8ENK=pengidentifikasi-perangkat-android apps-published-on-google-play=aplikasi-dipublikasikan-di-google-play h_01H9YXEYC3RG2XCVVW8MJ5VZSC=aplikasi-dipublikasikan-di-google-play apps-published-in-thirdparty-app-stores=aplikasi-yang-diterbitkan-di-app-store-pihak-ketiga h_01H9YXEYC3JA3DPN6P43J1ZXR9=aplikasi-yang-diterbitkan-di-app-store-pihak-ketiga apple-device-identifiers=pengidentifikasi-perangkat-apple h_01H9YXEYC3733B1A85TEF35EAY=pengidentifikasi-perangkat-apple ctv-device-identifiers=pengidentifikasi-perangkat-ctv h_01H9YXEYC3DFPWVXA5Y3XANQ3P=pengidentifikasi-perangkat-ctv" />
