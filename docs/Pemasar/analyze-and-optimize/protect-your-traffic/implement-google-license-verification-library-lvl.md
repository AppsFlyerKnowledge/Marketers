---
title: Mengatur Google License Verification Library ( (LVL)
metadata:
  keywords:
    - Premium
    - Premium Feature
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2023-07-27T14:45:46Z'
  edited_at: '2024-07-08T13:52:32Z'
  id: 17329535522961
  locale: id
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/id/articles/17329535522961
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Sekilas:** Lindungi app Anda dari penggunaan yang tidak sah dengan menambahkan Google License Verification Library (LVL) untuk menangani semua komunikasi terkait lisensi dengan Google Play.

<div id="overview" />

## Ringkasan

License Verification Library (LVL) merupakan pustaka yang dapat Anda tambahkan ke app Anda (dapat diunduh dari Android SDK) yang menangani semua komunikasi terkait lisensi dengan layanan lisensi Google Play.

Hal ini menambahkan lapisan perlindungan lain, di atas algoritme Protect360, dengan mengaktifkan verifikasi bahwa penginstalan berasal dari pengguna Google Play yang sebenarnya. Hal ini membantu mengurangi perbedaan antara jumlah penginstalan yang terlihat di Google Play dan dasbor AppsFlyer.

Layanan Lisensi Google Play menentukan apakah pengguna memiliki lisensi untuk menggunakan app atau tidak. Google Play menganggap pengguna memiliki lisensi jika mereka tercatat sebagai pembeli aplikasi. Lisensi ini unik untuk setiap app dan dapat digunakan untuk perlindungan yang lebih baik. <Anchor target="_blank" href="https://developer.android.com/google/play/licensing">Pelajari lebih lanjut</Anchor>

SDK AppsFlyer mengumpulkan data dari sisi pelanggan dan Protect360 melakukan verifikasi lisensi sisi server, memblokir penginstalan palsu yang gagal diverifikasi baik untuk penginstalan organik maupun non-organik. "Alasan pemblokiran" yang akan Anda lihat di dasbor dan laporan Protect360 adalah "Bot".

<div id="note" />

<div id="set-up-lvl" />

## Mengatur LVL

<div id="add-lvl" />

<Accordion title="Tambahkan LVL">

Saat ini, ini adalah proses manual di mana Anda harus memberikan informasi di bawah ini ke CSM AppsFlyer Anda sehingga mereka dapat menambahkannya secara manual.

**Untuk menambah LVL:**

1. Pastikan Anda memiliki SDK versi 5.4.3 atau lebih tinggi untuk menambahkan SDK terbaru ke implementasi build.gradle. **Catatan:** direkomendasikan versi 6.12.3 atau yang lebih tinggi.   

   ```http
   com.appsflyer:af-android-sdk:6.12.3
   ```
2. Menambahkan pustaka LVL ke implementasi build.gradle  

   ```http
   com.appsflyer:lvl:6.12.3
   ```
3. Dapatkan Lisensi app & penagihan dalam app:  
   Dari Konsol Pengembang Google Play (Pilih app -> Alat Pengembangan -> Layanan dan API).  

   ```http
   Base64-encoded RSA public key
   ```
4. Teruskan informasi di atas ke AppsFlyer CSM Anda.

</Accordion>

<div id="test-and-troubleshoot" />

<Accordion title="Menguji dan memecahkan masalah">

Ketika men-debug app, Anda seharusnya bisa melihat informasi LVL pada muatan yang dikirim ke AppsFlyer, seperti contoh di bawah ini:

```json
"lvl":{
      "ttr":,<ttr>,
      "signature":"<signature>",
      "signedData":"<signedData>"
   }
```

Bekerjasamalah dengan tim dukungan/SDK Anda jika tidak ada informasi LVL pada pesan penginstalan.

Harap berikan informasi berikut ini kepada CSM Anda:

* kunci publik
* app-id
* versi minimum app yang diintegrasikan dengan LVL

</Accordion>

<div id="setup-process" />

<Accordion title="Proses pengaturan">

Setelah kami menerima permintaan Anda, tim Protect360 akan mengonfigurasi verifikasi LVL dalam mode STAGING. Pada tahap ini, sistem hanya akan melaporkan hasil verifikasi LVL secara internal untuk AppsFlyer. Beberapa hari kemudian, kami akan memeriksa data kami.

**Jika semuanya terlihat baik:**

* Kami akan mengatur verifikasi LVL ke mode PRODUKSI dan akan mulai memblokir lalu lintas.
* Tim Protect360 akan memberi tahu CSM.

**Jika ada sesuatu** yang tidak beres (seperti jika kita tidak melihat informasi LVL pada event penginstalan):

* Kami akan membiarkan verifikasi LVL dalam mode STAGING.
* CSM Anda akan memberi tahu Anda dan membantu Anda memecahkan masalah implementasi di aplikasi.

</Accordion>

<div id="faq" />

## Pertanyaan Umum

<div id="what-if-an-app-is-installed-from-a-store-other-than-google-play" />

<Accordion title="Bagaimana jika aplikasi diinstal dari toko selain Google Play?">

Validasi LVL tidak akan memverifikasi dan tidak memblokir penginstalan yang berasal dari toko selain Google Play.

</Accordion>

<div id="how-much-time-does-it-take-to-get-lvl-set-up" />

<Accordion title="Berapa lama waktu yang dibutuhkan untuk menyiapkan LVL?">

Setelah kami mendapatkan informasi, diperlukan beberapa hari kerja untuk menyiapkan LVL dan melakukan verifikasi data. Lihat detail tentang [proses pengaturan](/docs/implement-google-license-verification-library-lvl#setup-process).

</Accordion>

<div id="does-lvl-affect-app-functionality" />

<Accordion title="Apakah LVL memengaruhi fungsionalitas aplikasi?">

Tidak, fungsionalitas aplikasi tidak terpengaruh.

</Accordion>

<div id="what-is-the-difference-between-lvl-and-gpreferrer" />

<Accordion title="Apa perbedaan antara LVL dan GP-referer?">

Verifikasi lisensi menggunakan LVL, berbeda dengan algoritme verifikasi GP-referrer karena LVL menangani verifikasi lisensi untuk aplikasi itu sendiri (lisensi per aplikasi), sedangkan GP-referrer digunakan untuk mendapatkan sumber pengalihan penginstalan ke Google Play Store dengan URL perujuk paket yang diinstal (cap waktu kapan klik referrer terjadi, kapan penginstalan dimulai, versi app, dan lain-lain). Singkatnya, sementara LVL digunakan untuk memeriksa apakah pengguna memiliki lisensi untuk menggunakan aplikasi, GP-referrer digunakan untuk memverifikasi bahwa detail penginstalan tidak dipalsukan.

</Accordion>

<div data-zendesk-anchors="overview=ringkasan 01H7YJ35YKDHJ2MDZSSYKMDCJ4=ringkasan set-up-lvl=mengatur-lvl 01H7YJ35YKDW0CB9TWRBKFBCDJ=mengatur-lvl 01H7YJ35YK585NA5F4HZN8C74K=add-lvl 01H7YJ35YKX1CVYMRZ1W8NRH7Y=test-and-troubleshoot 01H7YJ35YKMCN2E2BDWA5DD5M3=setup-process faq=pertanyaan-umum 01H7YJ35YMR8PBTTSHD77WZ4AE=pertanyaan-umum 01H7YJ35YMRZ8KRSVND1JT6JGH=what-if-an-app-is-installed-from-a-store-other-than-google-play 01H7YJ35YM11J0EG0B8PBMSPAC=how-much-time-does-it-take-to-get-lvl-set-up 01H7YJ35YMH0NM73Y1R90JDMEA=does-lvl-affect-app-functionality 01H7YJ35YM6RHCA6QP3MK0Y9J0=what-is-the-difference-between-lvl-and-gpreferrer" />
