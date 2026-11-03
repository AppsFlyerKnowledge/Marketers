---
title: Panduan tambahan integrasi SDK
metadata:
  keywords:
    - iOS
    - Android
    - Integration
    - Advertisers
    - firetv
    - Advertiser
    - appuid
    - anonymous
    - kakao
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2021-10-10T11:54:14Z'
  edited_at: '2023-10-31T15:15:31Z'
  id: 4408735106193
  locale: id
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/id/articles/4408735106193
---
> **Sekilas:** Pertimbangkan fungsionalitas SDK tambahan yang tersedia dan bekerja sama dengan programmer Anda untuk mengimplementasikan API seperti pengukuran uninstal, atribusi undangan pengguna, notifikasi push, dan pengaturan privasi.

## Metode atribusi tambahan

Pertimbangkan metode atribusi tambahan ini jika Anda berencana untuk mengukur TV, uninstal, atau aplikasi yang sudah diinstal sebelumnya.

**Semua platform**

<div id="tv-attribution" />

<Accordion title="Atribusi TV">

Mengatribusikan <Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-platform-attribution-concepts">pengguna seluler dengan iklan TV yang</Anchor> ditayangkan di lokasi dan waktu tertentu.

</Accordion>

<div id="measure-uninstalls" />

<Accordion title="Mengukur Uninstall">

Ukur tingkat penghapusan pengguna yang berasal dari berbagai sumber. Pengukuran uninstall dapat membantu Anda menganalisis dan mengoptimalkan kampanye Anda sesuai dengan tingkat KPI yang signifikan ini.

<Anchor target="_blank" href="/marketers/id/docs/measure-uninstalls">Pelajari cara menyiapkan pengukuran uninstall</Anchor>.

</Accordion>

**Khusus Android**

<div id="preinstalled-apps" />

<Accordion title="Aplikasi pra-instal">

Dalam <Anchor target="_blank" href="/marketers/id/docs/appsflyer-factory-preinstall-using-manifest-android">kampanye pra-penginstalan</Anchor>, pemilik aplikasi membuat kontrak dengan produsen perangkat (OEM) untuk melakukan pra-penginstalan aplikasi mereka.

Dengan AppsFlyer, Anda dapat dengan mudah mengatribusikan penginstalan aplikasi pra-penginstalan. Saat pengguna meluncurkan aplikasi Anda untuk pertama kalinya, AppsFlyer mengaitkan instalasi tersebut ke mitra pramuat sebagai sumber media.

</Accordion>

## Sesi

Ukur interaksi pengguna dengan aplikasi Anda dengan menghitung jumlah sesi pengguna selama periode tertentu. 

**Semua platform**

<div id="custom-time-between-sessions" />

<Accordion title="Waktu Antar Sesi Kustom">

Secara default, setidaknya ada jeda selama 5 detik antara dua peluncuran aplikasi agar dapat dihitung sebagai dua sesi terpisah. Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/measure-sessions#session-reporting-by-the-app-sdk">menghitung sesi</Anchor> .

Menyetel **nilai tinggi** **ke waktu khusus antar-peluncuran dapat mengganggu API** yang mengandalkan data sesi, seperti deep linking.

</Accordion>

**Khusus Android**

<div id="background-sessions-for-utility-apps" />

<Accordion title="Sesi Latar Belakang untuk Aplikasi Utilitas">

Anda dapat <Anchor target="_blank" href="/marketers/id/docs/measure-sessions#session-reporting-by-the-app-sdk">melaporkan sesi pengguna secara manual</Anchor> . Ini dapat berguna untuk aplikasi utilitas yang berjalan di latar belakang.

</Accordion>

## Media yang Dimiliki Sendiri

Gunakan OneLink untuk mengatribusikan sumber media yang Anda miliki seperti situs web, media sosial, dan undangan pengguna.

**Semua platform**

<div id="resolve-wrapped-deep-link-urls" />

<Accordion title="Menyelesaikan URL deep-link tergabung">

Beberapa layanan pihak ke-3 seperti <Anchor target="_blank" href="/marketers/id/docs/email-service-provider-esp-integration-guide">penyedia layanan email</Anchor> menggabungkan link di dalam email dengan domain pencatatan klik mereka sendiri. Beberapa bahkan memungkinkan Anda untuk mengatur domain pencatatan klik Anda sendiri. Jika OneLink digabungkan dalam domain seperti itu, fungsinya mungkin terbatas.

Untuk mengatasi masalah ini, pengembang Anda perlu mengonfigurasi aplikasi menggunakan API ini:

<Tabs>
<Tab title="AndroidNative">

Lihat [`setResolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setresolvedeeplinkurls) di referensi SDK Android

</Tab>

<Tab title="iOSNative">

Lihat [`resolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#resolvedeeplinkurls) di referensi SDK iOS

</Tab>

<Tab title="Unity">

Lihat [`setMinTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/api#setresolvedeeplinkurls) di referensi SDK Unity

</Tab>
</Tabs>

</Accordion>

<div id="record-push-notifications" />

<Accordion title="Catat pemberitahuan push">

AppsFlyer mendukung pengukuran kampanye notifikasi push dari semua vendor, termasuk Google Cloud Messaging dan layanan notifikasi push Apple.

<Anchor target="_blank" href="/marketers/id/docs/measuring-push-notification-re-engagement-campaigns">Pelajari lebih lanjut tentang pengukuran notifikasi push</Anchor>.

</Accordion>

<div id="user-invite-attribution" />

<Accordion title="Atribusi Undangan Pengguna">

Mengizinkan user yang ada untuk mengundang teman dan kontak mereka sebagai user baru bagi app Anda akan menjadi faktor pertumbuhan utama untuk app Anda.   

 Dengan AppsFlyer, Anda dapat mengatribusi dan mencatat install yang berasal dari undangan user dalam aplikasi Anda.

<Anchor target="_blank" href="/marketers/id/docs/user-invite-attribution">Pelajari lebih lanjut tentang atribusi undangan pengguna</Anchor>.

</Accordion>

<div id="crosspromotion-attribution" />

<Accordion title="Atribusi Promosi Silang">

Promosi silang aplikasi dapat menjadi faktor pertumbuhan utama dalam mendorong instalasi tambahan untuk aplikasi Anda. AppsFlyer memungkinkan Anda untuk mengatribusikan dan mencatat penginstalan yang berasal dari promosi silang dari aplikasi yang dimiliki pengguna saat ini, ke aplikasi Anda yang lain.  

<Anchor target="_blank" href="/marketers/id/docs/cross-promotion-attribution-for-marketers">Pelajari lebih lanjut tentang atribusi lintas-promosi</Anchor> .

</Accordion>

<div id="attribute-app-sessions-initiated-from-owned-websites-domains" />

<Accordion title="Atribusikan sesi aplikasi yang dimulai dari situs web yang dimiliki (domain)">

Pemilik aplikasi yang menggunakan Tautan Aplikasi atau Tautan Universal untuk deep linking (tanpa OneLink), dapat mengonfigurasi SDK ke sesi atribut yang dimulai melalui domain yang terkait dengan aplikasi mereka ( <Anchor target="_blank" href="https://developer.android.com/studio/write/app-link-indexing#associatesite">Android</Anchor>/<Anchor target="_blank" href="https://developer.apple.com/documentation/xcode/supporting-associated-domains?preferredLanguage=occ">iOS</Anchor> ).

Contoh:

* Seorang pengguna menelusuri Google dan mengklik domain Anda, **www.example.com** .
* Jika pengguna tidak memiliki aplikasi yang terinstal, mereka akan diarahkan ke situs web (www.example.com).
* Jika pengguna tersebut memiliki aplikasi yang terinstal di perangkat, pengguna akan ditautkan langsung (deep linked) ke aplikasi yang terkait dengan www.example.com. Sesi diatribusikan ke sumber media ( `pid` ) yang dikonfigurasi di SDK.

Dokumentasi pengembang tersedia sebagai berikut:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl">Referensi Android SDK</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl">Referensi SDK iOS</Anchor>

**Tips!** <Anchor target="_blank" href="/marketers/id/docs/convert-your-mobile-web-visitors-to-app-users#attribution-solutions">OneLink Smart Script</Anchor> dapat membantu pemilik aplikasi mengonversi pengunjung situs web menjadi pengguna aplikasi.

</Accordion>

## Privasi pengguna

Tinjau peraturan seperti GDPR dan CCPA serta persyaratan bisnis Anda, dan pertimbangkan kebijakan aktivasi dan penonaktifan mana yang akan diterapkan.

**Semua platform**

<div id="optout-policy" />

<Accordion title="Kebijakan penonaktifan">

Dalam beberapa kasus, Anda mungkin perlu menginstruksikan pengembang Anda untuk mengatur SDK AppsFlyer untuk menghentikan atau membatasi pengumpulan data, (misalnya, untuk mematuhi peraturan GDPR dan CCPA). Penonaktifan dapat terjadi di berbagai tingkatan tergantung pada peraturan dan persyaratan pengguna. Untuk informasi selengkapnya tentang berbagai skenario, lihat <Anchor target="_blank" href="/marketers/id/docs/apply-privacy-preserving-sdk-methods#skenario">Pengguna yang menonaktifkan</Anchor> .

</Accordion>

<div id="exclude-partners-from-getting-data" />

<Accordion title="Kecualikan mitra dari mendapatkan data">

Pada beberapa kasus, pengiklan mungkin ingin berhenti berbagi data tingkat pengguna dengan jaringan iklan/mitra untuk pengguna tertentu. Alasannya mencakup: 

* Kebijakan privasi seperti CCPA atau GDPR
* Mekanisme data pengguna tidak terlacak
* Kompetisi dengan beberapa mitra (jaringan iklan, pihak ketiga)

Berbagi data dengan mitra dikontrol melalui metode`setSharingFilterForPartners`:

<Tabs>
<Tab title="Android native">

Lihat [`setSharingFilterForPartners`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners) di referensi SDK Android

</Tab>

<Tab title="iOS native">

Lihat [`resolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforpartners) di referensi SDK iOS

</Tab>

<Tab title="Unity">

Lihat [`setSharingFilterForPartners`](https://dev.appsflyer.com/hc/docs/api#setsharingfilterforpartners) di referensi SDK Unity

</Tab>
</Tabs>

</Accordion>

**Khusus iOS**

<div id="strictmode-sdk" />

<Accordion title="SDK mode terperinci (strict mode)">

Gunakan SDK mode ketat untuk sepenuhnya menghapus fungsionalitas pengumpulan IDFA dan dependensi kerangka kerja AdSupport (misalnya, saat mengembangkan <Anchor target="_blank" href="https://developer.apple.com/app-store/review/guidelines/#kids-category">aplikasi untuk anak-anak</Anchor>).

Jika Anda memasarkan aplikasi untuk anak-anak, pengembang Anda perlu menginstal <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">SDK mode ketat</Anchor> , bukan SDK biasa. **Catatan:** IDFV tetap tersedia.

</Accordion>

<div id="disable-ad-frameworks" />

<Accordion title="Nonaktifkan framework iklan">

Untuk menonaktifkan framework AdSupport dan iAd, SDK menyediakan pengatur berikut:

<Tabs>
<Tab title="iOS native">

* [`disableCollectASA`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disablecollectasa) untuk tidak menerima atribusi Iklan Penelusuran Apple.
* [`disableAdvertisingIdentifier`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableadvertisingidentifier) untuk tidak mengumpulkan `advertisingIdentifier` Apple

</Tab>

<Tab title="Unity">

* [`setDisableCollectIAd`](https://dev.appsflyer.com/hc/docs/api#setdisablecollectiad) untuk tidak menerima atribusi Iklan Penelusuran Apple.
* [`setDisableCollectAppleAdSupport`](https://dev.appsflyer.com/hc/docs/api#setdisablecollectappleadsupport) untuk tidak mengumpulkan `advertisingIdentifier` Apple

</Tab>
</Tabs>

</Accordion>

<div data-zendesk-anchors="additional-attribution-methods=metode-atribusi-tambahan 01H8W01DRHQHJKNMJA24PR5S2T=metode-atribusi-tambahan 01H8W01DRHXR0BRCB9RECH7KS1=tv-attribution 01H8W01DRHMZN2P0FKADM0NQ96=measure-uninstalls 01H8W01DRH2HM3N06YAGRZ030F=preinstalled-apps sessions=sesi 01H8W01DRHD3EZBQT0ZKDMM1QB=sesi 01H8W01DRH2SR3NBQSMSQ6QR6K=custom-time-between-sessions 01H8W01DRH4NGYYABE274DJ1A5=background-sessions-for-utility-apps owned-media=media-yang-dimiliki-sendiri 01H8W01DRHV8H3QFJX5QKABK5E=media-yang-dimiliki-sendiri 01H8W01DRHJS8MM3ZQX2RX4JJG=resolve-wrapped-deep-link-urls 01H8W01DRHHDEEXP8GDFX9134R=record-push-notifications 01H8W01DRHZDB82AB63JKE1B6V=user-invite-attribution 01H8W01DRHVR8JHZCJ6SW8TAA6=crosspromotion-attribution 01H8W01DRHXSYWCS6RW2ZVDKXT=attribute-app-sessions-initiated-from-owned-websites-domains user-privacy=privasi-pengguna 01H8W01DRHJFB71DVJ64QWJME4=privasi-pengguna 01H8W01DRHD7FDERJZFJP9GG0T=optout-policy 01H8W01DRHYNYYFTF82XZ21J3P=exclude-partners-from-getting-data 01H8W01DRJD0XRX4VX03T3YEKX=strictmode-sdk 01H8W01DRJKJFFMBMJ4KNTXPXE=disable-ad-frameworks" />
