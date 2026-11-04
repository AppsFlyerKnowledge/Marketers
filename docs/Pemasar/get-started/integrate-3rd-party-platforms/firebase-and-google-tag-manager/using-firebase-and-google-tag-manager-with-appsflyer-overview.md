---
title: Menggunakan Firebase dan Google Tag Manager dengan AppsFlyer—Ikhtisar
metadata:
  keywords:
    - GTM
    - Google Tag Manager
    - firebase
    - Advertisers
    - datalayer
    - data layer
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-05-13T19:42:23Z'
  edited_at: '2023-11-03T08:08:26Z'
  id: 210353513
  locale: id
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/id/articles/210353513
---
> **Sekilas:** Tentang pengiriman event yang dilaporkan melalui Firebase SDK ke AppsFlyer menggunakan Google Tag Manager.

<Image alt="gtm.png" src="https://files.readme.io/fbb4e0f83baf6f5f7f8dc83e02986ca011f5cb919b9870768da1606798211dcc-360002517245.png" width="289px" />

Integrasi AppsFlyer dengan Google Tag Manager (GTM) dan Firebase memungkinkan pengembang mengirimkan kejadian dalam aplikasi ke Firebase menggunakan Firebase SDK, dan mengirimkan kejadian ke AppsFlyer melalui SDK menggunakan Google Tag Manager. Hal ini menghindari keharusan mengirim acara yang sama dua kali.

Event yang dikirim menggunakan GTM dimodelkan pada in-app event AppsFlyer. Nama event, parameter, dan strukturnya sama. Jika Anda sudah memiliki GTM di aplikasi Anda, menggunakannya untuk mengirim acara ke AppsFlyer sangatlah mudah.

Gunakan langkah-langkah dan instruksi dalam panduan ini untuk mengirimkan event. 

<div id="considerations" />

### Pertimbangan

* **Sumber event pada data lengkap:** Event yang dihasilkan oleh GTM menetapkan sumbernya ke S2S dalam laporan data lengkap. Hal ini dapat menimbulkan kebingungan karena event tersebut dilaporkan oleh SDK.
* **Memperbarui nilai konversi SKAdNetwork**: Event yang dihasilkan oleh GTM dan dilaporkan ke SDK seperti yang dijelaskan dalam panduan ini menyebabkan SDK memperbarui nilai konversi dengan cara yang serupa dengan event SDK reguler. Anda hanya perlu mengaktifkan dan mengatur <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide">pengaturan pengukuran SKAdNetwork</Anchor> Anda.

<div id="note" />

> 📘 **Catatan**
>
> * Saat ini, integrasi Google Tag Manager tidak mendukung pengiriman parameter berikut ke AppsFlyer:
>   * <Anchor target="_blank" href="/marketers/id/docs/customer-user-id-field-cuid">ID Pengguna Pelanggan</Anchor>
>   * `att`
>   * `os`Perhatikan bahwa:
>   * Saat mengirim postback in-app event ke SRN, parameter `att` diperlukan.
>   * Saat mengirimkan postback in-app event ke Meta ads, parameter `att` dan `os` diperlukan.

<div id="prerequisites" />

### Prasyarat

Sebelum Anda dapat mulai mengirim event ke AppsFlyer menggunakan GTM, Anda perlu mengimplementasikan GTM SDK di aplikasi Anda. Anda membutuhkan:

1. Anda membutuhkan [akun GTM.](https://www.google.com/analytics/tag-manager/)
2. Anda harus menyiapkan integrasi GTM + Firebase untuk aplikasi Anda (instruksi untuk [Android](https://developers.google.com/tag-manager/android) dan [iOS](https://developers.google.com/tag-manager/ios/)).
3. <Anchor target="_blank" href="/marketers/id/docs/integrate-the-appsflyer-sdk">Integrasikan SDK AppsFlyer</Anchor> jika Anda belum melakukannya.

Setelah semuanya siap, lanjutkan ke <Anchor target="_blank" href="/marketers/id/docs/using-firebase-and-google-tag-manager-with-appsflyer-google-tag-manager-setup">penyiapan GTM</Anchor>.

<div id="see-also" />

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/migrate-from-firebase-dynamic-links-to-appsflyer">Bermigrasi dari Firebase Dynamic Links ke AppsFlyer</Anchor>

<div data-zendesk-anchors="considerations=pertimbangan h_01HE7SKSCBH47YYFTKBWY3JVSV=pertimbangan h_01HE7SKSCBBTTWATRZ87BYRW6G=catatan prerequisites=prasyarat h_01HE7SKSCB9QHA4WEERVSWMF0P=prasyarat h_01HE7SQQG2VJW9179Q77PTZFPH=lihat-juga" />
