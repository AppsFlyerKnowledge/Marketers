---
title: Pengujian integrasi SDK untuk pemasar
metadata:
  keywords:
    - Testing
    - SDK
    - Advertisers
    - Debug
    - Debugging
    - redirects test
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-11-12T14:15:08Z'
  edited_at: '2023-10-31T10:51:35Z'
  id: 360001559405
  locale: id
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/id/articles/360001559405
---
> **Sekilas:** Uji integrasi aplikasi Android atau iOS Anda dengan AppsFlyer.

<div id="note-1" />

<div id="perform-the-integration-tests" />

<div id="prepare-a-test-device" />

<div id="note" />

<div id="testing-using-the-sdk-integration-tests-page" />

## Overview

Integrasi yang diuji dengan cermat memastikan pengumpulan data yang akurat dan komprehensif. Dengan menguji integrasi SDK, Anda dapat memverifikasi bahwa SDK berhasil berkomunikasi dengan server AppsFlyer, penginstalan, in-app event, dan penargetan ulang dicatat dan diatribusikan dengan benar.

Setelah integrasi SDK selesai, setiap anggota tim yang memiliki akses ke dashboard AppsFlyer dapat melakukan [pengujian dasar](/docs/testing-the-sdk-integration-for-marketers#pengujian-dari-dashboard). Pengembang dapat menggunakan log debug di <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integration-testing">lingkungan pengembangan</Anchor>.

Artikel ini menjelaskan prosedur pengujian dari dashboard dan menyediakan tautan ke dokumentasi yang harus disediakan pemasar kepada pengembang.

## Metode pengujian

Bagian berikut menjelaskan berbagai pengujian yang harus dilakukan dan metode yang tersedia.

### Pengujian dari dashboard

Untuk menguji integrasi SDK dari dashboard, Anda harus terlebih dahulu <Anchor target="_blank" href="/marketers/id/docs/registering-test-devices">mendaftarkan perangkat uji</Anchor> (Android atau iOS). Ini memungkinkan Anda untuk menggunakan perangkat yang sama berulang kali dan mencegah penginstalan dicatat sebagai penginstalan ulang.

Anda harus melakukan hal berikut:

* Menguji penginstalan organik.
* Menguji fungsionalitas integrasi dasar (penginstalan non-organik, in-app event, dan penargetan ulang).  
  Metode yang tersedia meliputi:
  * **[Halaman pengujian integrasi SDK:](/docs/testing-the-sdk-integration-for-marketers#test-using-the-sdk-integration-tests-page)** Wizard di dashboard AppsFlyer yang memandu Anda melalui proses untuk menjalankan setiap pengujian.
  * [**Pengujian menggunakan tautan atribusi:**](/docs/testing-the-sdk-integration-for-marketers#menguji-menggunakan-tautan-atribusi) Semua jaringan iklan non-SRN dan sumber media yang dimiliki bergantung pada tautan atribusi AppsFlyer; oleh karena itu, sangat disarankan untuk melakukan pengujian menggunakan tautan atribusi. Anda membuat tautan atribusi, lalu kemudian menjalankan pengujian untuk memverifikasi bahwa SDK mengatribusikan penginstalan non-organik dan in-app event ke sumber media yang tepat. Selain itu, Anda harus menjalankan pengujian untuk memastikan bahwa [penargetan ulang](/docs/testing-the-sdk-integration-for-marketers#menguji-penargetan-ulang-mengggunakan-tautan-atribusi) (atribusi ulang dan interaksi ulang) dicatat dan diatribusikan ke sumber media yang tepat.

<div id="ios-14-testing-consideration" />

<Accordion title="Pertimbangan pengujian iOS 14+">

Mulai iOS 14.5, IDFA hanya tersedia jika persetujuan pengguna melalui prompt AppTransparency Tracking (ATT). Jika prompt ATT diterapkan di aplikasi, Anda dapat menjalankan pengujian sebagai pengguna yang memberikan izin atau tidak.  Untuk informasi lebih lanjut, lihat <Anchor target="_blank" href="/marketers/id/docs/registering-test-devices#mendaftarkan-perangkat-uji-ios">panduan</Anchor> untuk mendaftarkan perangkat uji Anda dengan IDFA atau IDFV.

</Accordion>

### Pengujian di lingkungan pengembangan

Pengembang dapat melakukan hal berikut:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-integration#debug-mode">**Mengaktifkan dan memeriksa log debug**</Anchor>, serta menguji skenario seperti validasi pembelian, data konversi, dan deep linking.

  > 📘 **Catatan**
  >
  > Jika pengembang Anda mendapatkan pesan 403 di log, ini mungkin karena Anda memiliki paket Zero. Paket ini tidak termasuk data atribusi, hanya data tentang klik dan tayangan. Untuk informasi lebih lanjut tentang paket kami, hubungi tim CEM di [hello@appsflyer.com](mailto:hello@appsflyer.com) atau kunjungi <Anchor target="_blank" href="https://www.appsflyer.com/pricing/">harga AppsFlyer</Anchor>.

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integration-testing#debug-apps">**Membuat aplikasi debug**</Anchor> untuk menguji integrasi SDK. Saat melakukan pengujian, data dicatat dan ditampilkan di dashboard. Setelah data tersimpan, data ini tidak dapat dihapus. Jika Anda tidak ingin data pengujian dicatat sebagai bagian dari aplikasi produksi, Anda dapat meminta pengembang untuk menguji integrasi SDK menggunakan aplikasi debug. Aplikasi debug berbeda dari aplikasi produksi karena memiliki ID Aplikasi AppsFlyer berbeda, dashboard sendiri, dan tidak dipublikasikan di app store.

#### **Tambahkan aplikasi debug ke dashboard**

Jika pengembang Anda membuat aplikasi debug, Anda harus menambahkan aplikasi tersebut ke dashboard. Setelah pengembang mulai menjalankan pengujian menggunakan aplikasi, data akan ditampilkan di dashboard aplikasi.

Lakukan salah satu prosedur berikut untuk menambahkan aplikasi debug:

<Tabs>
<Tab title="Tambahkan aplikasi debug (Android)">

**Untuk menambahkan aplikasi debug ke dashboard:**

1. Dapatkan nama paket aplikasi debug dari pengembang Anda, lalu <Anchor target="_blank" href="/marketers/id/docs/adding-an-app-to-appsflyer">tambahkan aplikasi</Anchor> ke dashboard AppsFlyer Anda.
2. Atur status aplikasi ke salah satu dari yang berikut:
   * **Menunggu persetujuan**
   * **Tidak dipublikasikan**

</Tab>

<Tab title="Tambahkan aplikasi debug (iOS)">

**Untuk menambahkan aplikasi debug ke dashboard:**

1. <Anchor target="_blank" href="/marketers/id/docs/adding-an-app-to-appsflyer">Tambahkan aplikasi</Anchor> ke dashboard AppsFlyer Anda. ID aplikasi adalah ID yang diberikan ke aplikasi setelah dipublikasikan ke app store. Namun, karena ini adalah aplikasi debug, Anda dapat memberikan ID apa pun selama ID tersebut belum dipakai oleh aplikasi lain. Pastikan ID-nya 9 digit dan dimulai dengan angka 1 sebanyak empat kali, misalnya, 111167538. Digit yang lainnya harus acak.
2. Atur status aplikasi ke salah satu dari yang berikut:
   * **Menunggu persetujuan**
   * **Tidak dipublikasikan**
3. Berikan ID aplikasi kepada pengembang Anda.

</Tab>
</Tabs>

<div id="traits-and-limitations" />

<div id="note-5" />

<div id="testing-ctv" />

### Kasus uji khusus

Kasus uji khusus meliputi:

* **Android TV:** SDK kompatibel dengan TV pintar berbasis Android. Pemasar atau setiap anggota tim dapat menguji aplikasi TV ini dengan mengikuti prosedur dalam artikel ini.
* **Apple TV (tvOS):** SDk kompatibel dengan Apple TVs (tvOS). Pemasar atau setiap anggota tim dapat menguji aplikasi TV ini dengan mengikuti prosedur dalam artikel ini.
* **Aplikasi tvOS yang tidak dipublikasikan:** Mewajibkan pemasar dan pengembang untuk bekerja sama (lihat <Anchor target="_blank" href="/marketers/id/docs/testing-tvos-integration-before-publishing">Menguji integrasi tvOS sebelum mempublikasikan</Anchor>).
* **Amazon Fire TV:** Pemasar dapat [menguji integrasi](/docs/testing-the-sdk-integration-for-marketers#pengujian-dari-dashboard) menggunakan metode pengujian SDK Android di dashboard AppsFlyer. (Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/setting-up-amazon-fire-tv-ad-attribution">atribusi Amazon Fire TV</Anchor>).
* **PBA web event:** Mewajibkan pemasar dan pengembang untuk bekerja sama (lihat <Anchor target="_blank" href="/marketers/id/docs/test-pba-web-sdk-integration">Menguji integrasi SDK web PBA</Anchor>).

<div id="testing-organic-installs" />

## Menguji fungsionalitas SDK dasar

Bagian berikut menjelaskan prosedur yang harus Anda ikuti untuk menguji integrasi SDK dasar.

<div id="test-organic-installs" />

<Accordion title="Menguji penginstalan organik">

Kami menyarankan Anda memulai dengan menguji penginstalan organik.

**Untuk menguji penginstalan organik:**

1. Instal aplikasi di <Anchor target="_blank" href="/marketers/id/docs/registering-test-devices">perangkat uji terdaftar</Anchor>.
2. Luncurkan aplikasi.

Dashboard aplikasi menampilkan penginstalan organik yang baru. Tunggu hingga 30 menit hingga penginstalan muncul.

<Image align="center" alt="Test_SDK_Organic_install" src="https://files.readme.io/49c242957324516ba93d6c5ebfa338ec19b05820bcf619d8c39d6f7e4ada9bae-31828925882001.png" />

</Accordion>

<div id="test-using-the-sdk-integration-tests-page" />

<Accordion title="Uji menggunakan halaman Uji Integrasi SDK">

Gunakan halaman Uji Integrasi SDK untuk menguji penginstalan non-organik, in-app event, dan deep linking (penargetan ulang), dan menemukan masalah integrasi apa pun di proyek Anda.

**Khusus iOS**: Halaman pengujian integrasi SDK hanya berlaku untuk aplikasi iOS yang menerapkan ATT. Anda dapat menguji aplikasi non-ATT menggunakan prosedur yang ditentukan [di sini.](https://dev.appsflyer.com/hc/docs/testing-ios#apps-that-dont-implement-att)

**Sebelum Anda mulai:**

1. Siapkan perangkat (Android atau iOS) yang tidak menginstal aplikasi. Jika perlu, uninstal aplikasi dari perangkat.
2. <Anchor target="_blank" href="/marketers/id/docs/registering-test-devices">Daftarkan perangkat sebagai perangkat uji.</Anchor>

#### **Langkah 1: Uji penginstalan non-organik**

1. Di dashboard, pilih aplikasi.
2. Buka halaman **Uji Integrasi SDK Integrasi.**   
   Halaman pengujian integrasi SDK akan terbuka.   
   <Image align="center" alt="" src="https://files.readme.io/7b2af46dc66530db91c31466b08121673f067ea9188d5bbf7e5f4a4137cbc6e4-115011326025.png" />
3. Jalankan pengujian **Penginstalan Non-Organik**.
4. Pilih perangkat uji yang terdaftar.
5. Pilih toko tempat menginstal aplikasi:
   * Untuk Android:
     * **Google play**
     * **Lainnya** (misalnya, Toko aplikasi selain Play Store, Android Studio, APK file)
   * Untuk iOS:
     * **App Store**
     * **Lainnya** (misalnya, XCode, TestFlight)
6. Pindai kode QR dengan perangkat uji terdaftar dan ikuti petunjuk di perangkat.

   Perhatikan bahwa untuk perangkat Android, pengujian ini menggunakan <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#install-referrer-android-only">install referrer method</Anchor> (metode pengarah penginstalan), dan oleh karena itu, tautan atribusi tidak menyertakan GAID.
7. Jika Anda memilih **Lainnya**, instal aplikasi dari lingkungan pengembangan Anda.
8. Tunggu hingga penginstalan non-organik terdaftar di laman **SDK Integration Tests** (Pengujian Integrasi SDK) mengindikasikan bahwa pengujian berhasil. Ini dapat memerlukan waktu hingga 2 menit.

   <Image align="center" alt="NonOrganic_install" src="https://files.readme.io/3faf784b3d6014e223fdce7b703c6d328ba09af0ea1dde77a8a1f366529e1e00-4406213597585.png" />

   Jika aplikasi tidak mencatat penginstalan non-organik, kemungkinan alasannya adalah:
   * IDFA tersedia tetapi perangkat uji tidak <Anchor target="_blank" href="/marketers/id/docs/registering-test-devices#mendaftarkan-perangkat-uji-ios">terdaftar dengan pengenal ini di halaman Perangkat uji</Anchor>.
   * Anda memiliki lebih dari 1 aplikasi, selain aplikasi uji, yang diinstal pada perangkat uji tetapi perangkat uji tidak<Anchor target="_blank" href="/marketers/id/docs/registering-test-devices#mendaftarkan-perangkat-uji-ios">terdaftar dengan IDFV pada halaman Perangkat uji</Anchor>.
   * Penginstalan organik yang tercatat.
   * Pengujian dilakukan pada versi aplikasi yang tidak menyertakan SDK.

Untuk kesalahan integrasi, hubungi pengembang Anda.

#### **Langkah 2: Uji in-app event**

**Sebelum Anda mulai:**

* Pastikan Anda menggunakan perangkat uji yang sama dengan yang digunakan untuk mencatat penginstalan non-organik.

1. Jalankan pengujian **In-app Events** .
2. Pilih perangkat uji yang terdaftar, lalu kemudian klik **Berikutnya**.
3. Luncurkan aplikasi Anda dan mulai hasilkan in-app events.
4. Anda akan melihat log event ini saat terdaftar secara real time.

   <Image align="center" alt="Test_SDK_Integration_Inapp_events" src="https://files.readme.io/c501389bcbffd2859a2cb20e5232d57218fc0b75875f9425934c56bc13c12968-4406219047825.png" />

#### **Langkah 3: Uji deep link (penargetan ulang)**

**Sebelum Anda mulai:**

* Pastikan Anda menggunakan perangkat uji yang sama dengan yang digunakan untuk mencatat penginstalan non-organik.
* Luncurkan aplikasi pengujian setidaknya 3 kali.
* Untuk menguji deep linking (penargetan ulang), OneLink harus ditentukan untuk aplikasi Anda. Untuk informasi lebih lanjut, lihat <Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template">Panduan Pengaturan OneLink</Anchor>.
* Pastikan bahwa <Anchor target="_blank" href="/marketers/id/docs/app-settings#reengagement-attribution">penargetan ulang</Anchor> diaktifkan.

1. Jalankan pengujian **Deep linking**.
2. Pilih perangkat uji yang terdaftar.
3. Pilih jenis pengujian:
   * **OneLink:** Pilih OneLink.
   * **Skema URI:** Masukkan skema URI (misalnya, greatapps://cars).
4. Klik **Berikutnya**.
5. Pindai kode QR dengan perangkat uji terdaftar Anda dan ikuti petunjuk di perangkat Anda. Setelah pengujian selesai, Pengujian Deep Linking terdaftar sebagai berhasil.

   <Image align="center" alt="TestSDK_DeepLinks_en-us.png" src="https://files.readme.io/40c26ce173d14bd34771164fa32f6f26e8035fc26d4043fb9c78eef52d6451fa-4406221370385.png" />

</Accordion>

<div id="tip" />

<div id="note-3" />

<div id="note-2" />

<div id="testing-using-attribution-links" />

## Menguji menggunakan tautan atribusi

Bagian berikut menjelaskan prosedur yang harus Anda ikuti untuk menguji penginstalan dengan tautan atribusi. Anda dapat melakukan pengujian ini meskipun aplikasi masih tertunda (artinya, tidak terdaftar di Google Play Store atau Apple App Store).

<div id="test-install-attribution" />

<Accordion title="Menguji atribusi penginstalan">

Menguji penginstalan memungkinkan Anda unuk memastikan bahwa SDK AppsFlyer mengatribusikan penginstalan dengan benar ke berbagai sumber media.

**Untuk menguji atribusi penginstalan:**

1. Salin tautan berikut (Android atau iOS), dan lakukan perubahan ini:
   1. **app\_id** value: Tambahkan ID aplikasi Anda di AppsFlyer.
   2. **pid** parameter: Tentukan nama sumber media tempat penginstalan diatribusikan.
   3. **c** parameter: Tentukan nama kampanye.
   4. Jika Anda menguji aplikasi yang tersedia melalui app store Android pihak ketiga: tambahkan <Anchor target="_blank" href="/marketers/id/docs/set-up-multi-store-android-attribution#single-dashboard-attribution-links">af\_r parameter</Anchor> ke tautan atribusi.
   5. Ganti GAID, IDFA, atau IDFV dengan pengenal perangkat khusus Anda.

   <Tabs>
   <Tab title="Android">

   ```http
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&advertising_id=<GAID>
   ```

   </Tab>

   <Tab title="iOS">

   idfa

   ```http
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&idfa=<IDFA>
   ```

   IDFV

   ```http
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&idfv=<IDFV>
   ```

   </Tab>
   </Tabs>

   Berikut ini adalah contoh tautan atribusi dengan nilai khusus:

   <Tabs>
   <Tab title="Android">

   ```http
   https://app.appsflyer.com/com.my.app?pid=Test&c=Test&advertising_id=12345f9*-eba*-421*-876*-7654ac67876*
   ```

   </Tab>

   <Tab title="iOS">

   ```http
   https://app.appsflyer.com/id123456789?pid=Test&c=Test&idfa=1A2B****-9128-4***-123*-04E***654321
   ```

   </Tab>
   </Tabs>

2. Salin tautan yang diperbarui, kirim tautan ini ke perangkat uji, lalu kemudian klik tautan tersebut.

   > 📘 **Catatan**
   >
   > Di iOS, gunakan iMessage atau email untuk mengirim tautan ke perangkat. Jangan merekatkan tautan di aplikasi iOS Notes dan mengklik tautan tersebut. Tindakan ini dapat merusak tautan tersebut.

3. Lakukan salah satu dari berikut ini:
   * Jika aplikasi aktif, lanjutkan untuk menginstalnya.
   * Jika aplikasi tertunda, muncul pesan berikut: "*Aplikasi yang Anda cari belum tersedia di market.*" Ini merupakan hasil yang diperkirakan. Karena aplikasi tidak aktif, tautan atribusi tidak mengarah ke app store mana pun. Namun, tautan atribusi masih valid untuk tujuan atribusi dan Anda harus menginstal aplikasi sebagai berikut:
     * **Untuk Android:** Dari file APK (atau Android Studio untuk pengembang)
     * **Untuk iOS:** Dari TestFlight (atau Xcode untuk pengembang)

   Anda akan melihat penginstalan yang diatribusikan ke kampanye pengujian dengan sumber media yang disebut **Pengujian**. Tunggu hingga 30 menit hingga penginstalan muncul di dashboard aplikasi. [![Test_Install_Attribution_Link](https://files.readme.io/1771da27f7b8c5334d68c3d7c8361e91e0e35a3a08abf60e3d711f83de9ad22d-31828925861265.png)](https://files.readme.io/1771da27f7b8c5334d68c3d7c8361e91e0e35a3a08abf60e3d711f83de9ad22d-31828925861265.png)

> 👍 **Tips**
>
> Berikut ini menjelaskan cara alternatif untuk memverifikasi hasil pengujian Anda:
>
> * Jika Anda memiliki akses ke laporan data lengkap, unduh <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">Installs raw data report</Anchor> (laporan data lengkap penginstalan). Pengunduhan laporan ini membutuhkan waktu beberapa menit.
>
>   **Untuk mengunduh laporan ini:**
>
>   1. Di dashboard, buka **Reports (Laporan)** > **Export Data (Ekspor Data).**
>   2. Dari daftar **User acquisition (non-organic)** (Akuisisi pengguna non-organik), klik **Installs** (Penginstalan), lalu unduh laporannya.
> * Jika Anda memiliki akses ke log debug, Anda dapat menggunakan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_app-id-2">API pengujian integrasi SDK</Anchor> untuk mengambil hasil atribusi untuk penginstalan tertentu.

</Accordion>

<div id="test-inapp-events-attribution" />

<Accordion title="Uji atribusi in-app event">

Menguji in-app event memungkinkan Anda untuk memastikan bahwa pendapatan terkait event ditampilkan dan in-app event diatribusikan ke sumber media yang menghasilkan penginstalan.

**Untuk menguji atribusi in-app event:**

1. Luncurkan aplikasi; lalu kemudian buat beberapa in-app event.
2. Buka dashboard aplikasi, lalu klik **Events (Event)**.

   Anda akan melihat event, pendapatan event (jika pendapatan terkait dengan event tersebut), dan sumber media yang terkait dengan event tersebut. Tunggu hingga 60-70 menit sampai event muncul di dashboard.

   <Image align="center" alt="Testing_InAppEvents_Attribution" src="https://support.appsflyer.com/hc/article_attachments/4406219144593" />

**Tips!** Pertimbangkan untuk mengunduh <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">laporan data lengkap in-app event</Anchor> untuk memastikan bahwa event tersebut diatribusikan dengan benar. Pengunduhan laporan ini membutuhkan waktu beberapa menit.

**Untuk mengunduh laporan ini:**

1. Di dashboard, buka **Reports (Laporan)** > **Export Data (Ekspor Data)**.
2. Di bagian **Raw Data Reports (Laporan Data Lengkap),** unduh laporan data lengkap in-app event.

</Accordion>

<div id="test-onelink" />

<Accordion title="Uji OneLink">

OneLink memungkinkan Anda untuk mengatur satu tautan atribusi untuk Android dan iOS. OneLink mengenali perangkat user dan mengarahkan pengguna ke app store yang sesuai.

Selain itu, OneLink mengaktifkan deep linking. Deep linking memungkinkan Anda untuk membuka app dalam aktivitas app spesifik sambil menyajikan konten yang disesuaikan.

Untuk informasi lebih lanjut, lihat panduan tentang <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">pengujian URL OneLink</Anchor>.

</Accordion>

<div id="note-4" />

<div id="testing-retargeting-using-attribution-links" />

## Menguji penargetan ulang mengggunakan tautan atribusi

Bagian berikut menjelaskan prosedur yang harus Anda ikuti untuk menguji atribusi penargetan ulang.

<div id="about-retargeting-tests" />

<Accordion title="Tentang pengujian penargetan ulang">

Atribusi penargetan ulang muncul ketika pengguna berinteraksi dengan kampanye penargetan ulang dengan mengklik tautan atribusi penargetan ulang. Ini menghasilkan atribusi ulang atau event interaksi ulang. Untuk informasi lebih lanjut, lihat <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide">Panduan atribusi penargetan ulang</Anchor>.

Pengujian penargetan ulang meliputi :

* **[Untuk atribusi ulang:](/docs/testing-the-sdk-integration-for-marketers#test-reattribution)** Uninstal dan instal ulang aplikasi. Kemudian, pastikan di dashboard bahwa penginstalan telah tercatat.
* **[Untuk interaksi ulang:](/docs/testing-the-sdk-integration-for-marketers#test-reengagement)** Klik tautan atribusi penargetan ulang atau deep link, lalu kemudian memastikan bahwa interaksi ulang diatribusikan ke sumber media yang tepat.

</Accordion>

<div id="prerequisites-to-run-retargeting-tests" />

<Accordion title="Prasyarat untuk menjalankan pengujian penargetan ulang">

Sebelum menjalankan pengujian penargetan ulang, diperlukan pengaturan berikut:

* Penargetan ulang harus diaktifkan untuk perangkat yang diuji.
* Buat tautan khusus aplikasi atau dapatkan tautan khusus OneLink. Tautan ini harus menyertakan parameter penargetan ulang.

**Untuk mengatur pengujian penargetan ulang:**

1. Mengaktifkan penargetan ulang di pengaturan aplikasi.

   Di dashboard aplikasi, klik **App Settings (Pengaturan Aplikasi)** dan aktifkan **Enable retargeting attribution (Aktifkan atribusi penargetan ulang)**.

   <Image align="center" alt="Set_Reattribution_window" src="https://files.readme.io/1fe0c8c4add90c75237b0c5c97b6ff26d8f08ff95bd952912ef746fdec2e9f3d-31828933628561.png" />
2. Lakukan salah satu dari hal berikut: 
   * Buat tautan atribusi khusus aplikasi. Pastikan untuk menyertakan parameter penargetan ulang `is_retargeting=true`, dan ID iklan. Untuk melihat GAID, IDFA, atau IDFV, ikuti petunjuk <Anchor target="_blank" href="/marketers/id/docs/registering-test-devices">Mendaftarkan perangkat uji</Anchor>.    
     Berikut adalah contoh tautan atribusi yang menyertakan parameter khusus Android sebagai pengenal perangkat (GAID). Untuk informasi selengkapnya tentang menambahkan parameter pengenal perangkat lainnya, seperti IDFA atau IDFV, lihat <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#parameter-spesifik-ios">Struktur tautan atribusi dan parameter</Anchor>.

     ```http
     https://app.appsflyer.com/<app_id>?pid=Test&c=Test&is_retargeting=true&advertising_id=<GAID>
     ```
   * Dapatkan <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#buat-tautan-onelink">URL panjang tautan khusus</Anchor> dari <Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template#prosedur">templat OneLink</Anchor>. Pastikan untuk mengaktifkan <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">Kampanye penargetan ulang</Anchor>. Gambar berikut menunjukkan contoh URL panjang khusus:

     <Image align="center" alt="Testing_LongLink_en-us.png" src="https://files.readme.io/19c706b0cc11b83a5cb08d51b3418654c6fa1e597ee7ff9e631db21c33c00b82-31828933632401.png" />

Anda sekarang dapat melanjutkan untuk menguji atribusi ulang dan interaksi ulang.

</Accordion>

<div id="test-reattribution" />

<Accordion title="Uji atribusi ulang">

**Sebelum Anda mulai:**

* Ikuti [petunjuk](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) untuk mengatur pengujian penargetan ulang.
* Pastikan perangkat uji Anda **tidak** terdaftar.

**Untuk menguji atribusi ulang:**

1. Uninstal aplikasi dari perangkat. Jika Anda baru saja menginstal aplikasi, tunggu beberapa menit.
2. Salin [tautan atribusi](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) yang Anda buat sebelumnya, baik tautan atribusi khusus aplikasi atau tautan panjang khusus dari templat OneLink, kirim tautan tersebut ke perangkat uji, lalu kemudian klik tautan tersebut.

   > 📘 **Catatan**
   >
   > Di iOS, gunakan iMessage atau email untuk mengirim tautan ke perangkat. Jangan merekatkan tautan di aplikasi iOS Notes dan mengklik tautan tersebut. Tindakan ini dapat merusak tautan tersebut.

3. Lakukan salah satu dari berikut ini:
   * Jika aplikasi aktif, lanjutkan untuk menginstalnya.
   * Jika aplikasi tertunda, instal aplikasi sebagai berikut:
     * **Untuk Android**: Instal dari Android Studio atau file APK.
     * **Untuk iOS:** Instal dari TestFlight.
4. Buka dasbor aplikasi, dan di kotak **View type** (Jenis tampilan), pilih **Retargeting** (Penargetan ulang) .
5. Di kotak **Attribution type** (Jenis atribusi), pilih **Re-attributions** (Atribusi ulang) .

   Anda akan melihat penginstalan yang diatribusikan ke sumber media dan kampanye. Tunggu hingga 30 menit hingga penginstalan yang ditargetkan muncul di dasbor.

   <Image align="center" alt="Testing_SDK_Reattribution" src="https://files.readme.io/c5c59709b199262cbefd5cd70ee9fe0db2c788612a8ae6b598c7b2188b696345-small-31828925870609.png" />

<div id="tip-1" />

> 👍 **Tips**
>
> Berikut ini menjelaskan cara alternatif untuk memverifikasi hasil pengujian Anda:
>
> * Jika Anda memiliki akses ke laporan data lengkap, unduh <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">Conversions raw-data report</Anchor> (laporan data lengkap konversi). Pengunduhan laporan ini membutuhkan waktu beberapa menit.
>
>   **Untuk mengunduh laporan ini:**
>
>   1. Di dashboard, buka **Reports (Laporan)** > **Export Data (Ekspor Data).**
>   2. Dari daftar **Retargeting** (Penargetan Ulang), klik **Konversi (interaksi ulang & atribusi ulang)** (Konversi `{interaksi ulang & atribusi ulang}`, lalu unduh laporannya.
> * Jika Anda memiliki akses ke log debug, Anda dapat menggunakan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_app-id-2">API pengujian integrasi SDK</Anchor> untuk mengambil hasil atribusi untuk penginstalan tertentu.

</Accordion>

<div id="test-reengagement" />

<Accordion title="Uji interaksi ulang">

**Sebelum Anda mulai:**

* Ikuti [petunjuk](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) untuk mengatur pengujian penargetan ulang.
* Untuk tujuan pengujian, atur waktu minimum antar konversi menjadi **None (Tidak Ada)**. Ini memungkinkan semua konversi interaksi ulang dicatat dan diatribusikan selama pengujian.

  <Image align="center" alt="Testing_Reattribution_window" src="https://files.readme.io/ec8c7c923093dbed0e99aa5ef57d0239217ead5a9db41f42fe4af8a70eb04551-4406211661841.png" />
* Pastikan aplikasi sudah di-instal di perangkat pengujian dan telah diluncurkan beberapa kali. Jika Anda baru saja menginstal aplikasi, tunggu beberapa menit.

**Untuk menguji interaksi ulang (deep linking langsung):**

Pastikan aplikasi Anda dikonfigurasi untuk <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">deep linking</Anchor>, lalu kemudian ikuti <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">prosedur ini</Anchor> untuk pengujian.

**Untuk menguji interaksi ulang (deep linking tidak langsung):**

1. Salin [tautan atribusi](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) yang Anda buat sebelumnya, baik tautan atribusi khusus aplikasi atau tautan panjang khusus dari templat OneLink.
2. Kirim tautan tersebut ke perangkat uji Anda, lalu kemudian klik tautan tersebut.
3. Untuk membuka aplikasi, lakukan salah satu hal berikut:
   * Di app store, klik **Buka**.
   * Luncurkan aplikasi dari perangkat Anda.

   Di dasbor, Anda akan melihat interaksi ulang yang diatribusikan ke sumber media dan kampanye. Tunggu hingga 30 menit hingga interaksi ulang muncul.

   <Image align="center" alt="Testing_SDK_Re-engagement" src="https://files.readme.io/5b64b671c8071f871d9835e8df4d89c18d06c85fe996f7227b6ddf429552fccd-small-31828933643153.png" />

**Tips!** Pertimbangkan untuk mengunduh laporan data lengkap konversi untuk memastikan bahwa interaksi ulang diatribusikan ke sumber media yang tepat. Pengunduhan laporan ini membutuhkan waktu beberapa menit.

**Untuk mengunduh laporan ini:**

1. Di dashboard, buka **Reports (Laporan) >** **Export Data (Ekspor Data)**.
2. Di bagian **Retargeting (Penargetan Ulang)** , unduh **laporan Konversi (interaksi ulang & atribusi ulang)**.

</Accordion>

> 📄 **Lihat juga**
>
> * Pengujian integrasi jaringan iklan <Anchor target="_blank" href="/partners/id/docs/getting-started-onboarding-guide-for-ad-networks">Pengujian integrasi jaringan iklan</Anchor>

<div data-zendesk-anchors="01H88X11QS2VYFXJGC95TXC6PN=overview testing-methods=metode-pengujian 01H88X11QT88941QB4HAZCSW88=metode-pengujian testing-from-the-dashboard=pengujian-dari-dashboard 01H88X11QTD9F2QZKV6DWDBQW5=pengujian-dari-dashboard 01H88X11QTMRBY15M52GRSTFCG=ios-14-testing-consideration testing-in-the-development-environment=pengujian-di-lingkungan-pengembangan 01H88X11QTAGR4ETNB7ACWY0TV=pengujian-di-lingkungan-pengembangan 01H88X11QT93QAD1KHA64VPFDC=catatan add-debug-apps-to-the-dashboard=tambahkan-aplikasi-debug-ke-dashboard 01H88X11QTVQK5QV767MX0QFC2=tambahkan-aplikasi-debug-ke-dashboard special-test-cases=kasus-uji-khusus 01H88X11QT72F71N49G65BAEAE=kasus-uji-khusus testing-basic-sdk-functionality=menguji-fungsionalitas-sdk-dasar 01H88X11QTAQ85WBE8RJQK9D74=menguji-fungsionalitas-sdk-dasar 01H88X11QTPS13PVCVRHZ1TN50=test-organic-installs 01H88X11QT1ZMAV8JY2840NXM7=test-using-the-sdk-integration-tests-page step-1-test-nonorganic-installs=langkah-1-uji-penginstalan-non-organik 01H88X11QT7RZYYE0EXTPV559P=langkah-1-uji-penginstalan-non-organik step-2-test-inapp-events=langkah-2-uji-in-app-event 01H88X11QTQMZSD152VGEXGK1Z=langkah-2-uji-in-app-event step-3-test-deep-links-retargeting=langkah-3-uji-deep-link-penargetan-ulang 01H88X11QTEQZK675X3MF4P9GY=langkah-3-uji-deep-link-penargetan-ulang testing-using-attribution-links=menguji-menggunakan-tautan-atribusi 01H88X11QT0WDRW5GZDCR7MZ3D=menguji-menggunakan-tautan-atribusi 01H88X11QT6YVB3TQ6JEM4G92G=test-install-attribution 01H88X11QTG2NZ3VGMQXJR7368=catatan-2 01H88X11QT5TY25HRTX4RD06C7=tips 01H88X11QTRBQQ11C8SAK7DCTC=test-inapp-events-attribution 01H88X11QTJE6HNPDHBMKQMDCP=test-onelink testing-retargeting-using-attribution-links=menguji-penargetan-ulang-mengggunakan-tautan-atribusi 01H88X11QTQ94BAJGEE1V11F6X=menguji-penargetan-ulang-mengggunakan-tautan-atribusi 01H88X11QT4DR3WA6RGB8HDZB3=about-retargeting-tests 01H88X11QTR3AGQHN674ZYEYF7=prerequisites-to-run-retargeting-tests 01H88X11QVFQ6552C272ST108D=test-reattribution 01H88X11QVYBPJPYSPZH2HS308=catatan-2 01H88X11QV5YVR7HCFTGD9BEFJ=tips-1 01H88X11QVKAG3JWRQ6KXESTQA=test-reengagement h_01H9FHRVKE88CXGH8G7E26ZXT2=lihat-juga" />
