---
title: Pengaturan integrasi Salesforce Marketing Cloud MobilePush
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
  created_at: '2022-11-14T06:37:05Z'
  edited_at: '2023-09-10T12:42:31Z'
  id: 10590769196817
  locale: id
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/id/articles/10590769196817
---
> **Sekilas:** Salesforce Marketing Cloud MobilePush, mitra terintegrasi AppsFlyer, adalah platform interaksi pengguna untuk tim pemasaran, pertumbuhan, dan interaksi.

<div id="overview" />

## Ringkasan

Salesforce Marketing Cloud MobilePush memungkinkan Anda membuat dan mengirim pesan push yang ditargetkan berdasarkan data konsumen cross-channel (lintas kanal). Ini membantu mendorong penggunaan aplikasi dan menghasilkan ROI yang bertambah. Dengan MobilePush, Anda dapat melihat bagaimana pengguna menavigasi aplikasi Anda, mulai dari produk yang mereka lihat hingga waktu yang dihabiskan di setiap halaman. Mengintegrasikan MobilePush memungkinkan Anda untuk:

* Dorong interaksi dan mCommerce
* Dapatkan insight pengguna yang berharga
* Buat kampanye cross-channel (lintas kanal) dengan mudah
* Segmentasikan dan jadwalkan pesan

<div id="important" />

> 🚧 **Penting!**
>
> <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions#pembatasan-sumber-media">Beberapa sumber media</Anchor> membatasi pembagian data dengan pihak ketiga. Oleh karena itu, postback untuk event terbatas tidak akan dikirim ke mitra ini, terlepas dari pilihan yang dikonfigurasi untuk mengirim postback.

<div id="setting-up-salesforce-marketing-cloud-mobilepush" />

## Mengatur Salesforce Marketing Cloud MobilePush

Sebagian besar pengaturan dilakukan di Salesforce (langkah 1-4). Langkah 5 dilakukan di AppsFlyer.

<div id="step-1-set-up-mobilepush-sdk" />

### Langkah 1: Siapkan MobilePush SDK

* <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_get_started.htm&type=5">Terapkan pengaturan MobilePush SDK</Anchor>

<div id="step-2-provision-for-push-notifications" />

### Langkah 2: Menyediakan notifikasi push

* <Anchor target="_blank" href="https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-provision.html">Buat `.p12` sertifikat</Anchor>

<div id="step-3-enable-app-push-notifications" />

### Langkah 3: Aktifkan notifikasi push aplikasi

* <Anchor target="_blank" href="https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-configureforpush.html">Terapkan notifikasi push</Anchor>

<div id="step-4-set-up-app-push-notifications" />

### Langkah 4: Siapkan notifikasi push aplikasi

* <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_outbound_message.htm&type=5">Buat dan kirim pesan push ke perangkat seluler</Anchor>

<div id="note" />

> 📘 **Catatan**
>
> Saat membuat notifikasi push di cloud pemasaran Salesforce, <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_custom_keys.htm&type=5">kunci khusus</Anchor> perlu ditambahkan agar AppsFlyer dapat mengatribusikan PID dan atribut kampanye dengan tepat. Gunakan `AF_xxxxxxxxx` sebagai kunci personalisasi.

<div id="step-5-set-up-push-notifications-in-appsflyer" />

### Langkah 5: Siapkan notifikasi push di AppsFlyer

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications-ios#addpushnotificationdeeplinkpath-recommended">Konfigurasikan iOS SDK menggunakan OneLink (langkah 3 di tautan ini)</Anchor>

<div id="note-1" />

> 📘 **Catatan**
>
> Pastikan kunci personalisasi `AF_xxxxxxxxx` yang Anda masukkan di [langkah 4](/docs/salesforce-marketing-cloud-mobilepush-integration-setup#langkah-4-siapkan-notifikasi-push-aplikasi) memiliki nilai yang sama dengan yang dimasukkan di fungsi `addPushNotificationDeepLinkPath` .

<div data-zendesk-anchors="overview=ringkasan h_01H9HWK3F5TQZ8YQZBHGBZACPG=ringkasan h_01H9HWK5DM87JTDVFND0KB965G=penting setting-up-salesforce-marketing-cloud-mobilepush=mengatur-salesforce-marketing-cloud-mobilepush h_01H9HWK3F52YGQPX4B82N40PPD=mengatur-salesforce-marketing-cloud-mobilepush step-1-set-up-mobilepush-sdk=langkah-1-siapkan-mobilepush-sdk h_01H9HWK3F5HCVZ0225MFRYRW5Q=langkah-1-siapkan-mobilepush-sdk step-2-provision-for-push-notifications=langkah-2-menyediakan-notifikasi-push h_01H9HWK3F5RNCZG340E0CT5XJC=langkah-2-menyediakan-notifikasi-push step-3-enable-app-push-notifications=langkah-3-aktifkan-notifikasi-push-aplikasi h_01H9HWK3F5E4W8FG35V4JTFN7F=langkah-3-aktifkan-notifikasi-push-aplikasi step-4-set-up-app-push-notifications=langkah-4-siapkan-notifikasi-push-aplikasi h_01H9HWK3F5K8V8AVADXNNG25GY=langkah-4-siapkan-notifikasi-push-aplikasi h_01H9HWK3F5VG2GBCE93B69AADH=catatan step-5-set-up-push-notifications-in-appsflyer=langkah-5-siapkan-notifikasi-push-di-appsflyer h_01H9HWK3F5YJ71YCWHV4B02VYP=langkah-5-siapkan-notifikasi-push-di-appsflyer h_01H9HWK3F5T67NSPE9CVPS1KTA=catatan-1" />
