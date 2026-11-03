---
title: Panduan dasar integrasi SDK
metadata:
  keywords:
    - sdk
    - iOS
    - Android
    - Integration
    - Advertisers
    - appuid
    - anonymous
    - kakao
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2013-08-22T16:09:08Z'
  edited_at: '2023-11-28T04:51:33Z'
  id: 207032066
  locale: id
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/id/articles/207032066
---
> **Sekilas:** Bekerja samalah dengan pengembang aplikasi seluler atau CTV Anda untuk mengintegrasikan dan menginstal SDK ke aplikasi Android atau iOS. Setelah tugas integrasi dasar selesai, aplikasi Anda siap untuk atribusi instalasi dan pengukuran in-app event.

## **Mengambil kode pengembang**

Sebelum pengembang Anda dapat menginstal dan mengintegrasikan SDK, Anda harus mengambil kode pengembang. AppsFlyer menggunakan kode pengembang untuk mengidentifikasi akun Anda secara unik. Kode pengembang bersifat wajib karena memungkinkan SDK mengirim dan mengambil data milik akun Anda dengan aman.

**Untuk mengambil kode pengembang Anda:**

1. Di AppsFlyer, buka **Konfigurasi** > **Pengaturan Aplikasi**.
2. Salin kode pengembang, dan kirimkan ke pengembang seluler Anda.

   [![](https://files.readme.io/5078fdabbcce4d3977f3d32351b61bacbc8af406a68911f2c6b4cdca458712a5-30603573703057.png)](https://files.readme.io/5078fdabbcce4d3977f3d32351b61bacbc8af406a68911f2c6b4cdca458712a5-30603573703057.png)
3. Berikan instruksi kepada pengembang seluler Anda untuk <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">menginstal</Anchor> dan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-integration">mengintegrasikan SDK</Anchor>.

## **Di mana memulai SDK?**

Saat merencanakan integrasi SDK AppsFlyer, keputusan pertama yang harus Anda buat adalah di mana menginisialisasi dan memulai SDK dalam alur peluncuran aplikasi Anda.

Aturan dasarnya adalah agar SDK mulai mengirim data sesegera mungkin setelah meluncurkan aplikasi.**Hal ini memastikan bahwa SDK menangkap kejadian penginstalan dan semua kejadian dalam aplikasi lainnya yang terjadi dalam sesi tersebut.**

Namun, untuk mematuhi peraturan menjaga privasi seperti GDPR dan CCPA, sering kali pengiriman data ke AppsFlyer perlu ditunda hingga pengguna menyetujui untuk membagikan informasi mereka.

<Tabs>
<Tab title="Android asli">

### Memulai SDK di Android asli

#### PILIH DI KELAS APA UNTUK MEMULAI SDK

Pilih apakah akan memulai SDK di kelas `Application` global atau kelas `Activity`:

* **Memulai SDK di kelas** `Application` **global:** Secara umum, menginisialisasi SDK di kelas/subkelas `Aplikasi` global adalah praktik yang baik karena kelas `Application` dimuat dan diinisialisasi sebelum UI aplikasi apa pun ditampilkan. Hal ini memastikan bahwa SDK dapat dimulai dalam skenario apa pun, termasuk deep linking.
* **Mulai SDK di** kelas`Activity`**(awal tertunda)** untuk memungkinkan pengguna ikut serta dalam berbagi data. Hal ini karena untuk mendapatkan izin pengguna memerlukan antarmuka pengguna (UI) yang dirender dalam kelas `Activity` .

#### INSTRUKSI PENGEMBANG ANDROID

* Beri tahu pengembang tentang keputusan Anda tentang hal-hal berikut:
  * Di kelas apa - `Application` atau `Activity` - untuk memulai SDK?
  * Skenario opt-in/opt-out mana yang akan digunakan?

* Kirimkan tautan referensi berikut kepada pengembang Anda:
  * [Bagaimana melakukan awal yang ditangguhkan](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#starting-the-android-sdk)
  * <Anchor target="_blank" href="/marketers/id/docs/apply-privacy-preserving-sdk-methods#tidak-ikut-serta-di-penginstalan">Skenario opt-out dan opt-in yang umum</Anchor>
  * [Contoh kode opt-out](https://github.com/AppsFlyerSDK/SampleApp-Examples/tree/master/AndroidOptOutSampleApp/app/src/main/java/com/appsflyer/optoutsamples)

</Tab>

<Tab title="iOS asli">

<div id="starting-the-sdk-in-ios" />

### Memulai SDK di iOS asli

<div id="delay-the-sdk-start-in-ios" />

#### TUNDA MULAI SDK DI IOS

Pertimbangan penting saat merencanakan cara memulai SDK adalah apakah akan menunda `start` hingga izin pengguna diberikan.

SDK menyediakan metode `waitForATTUserAuthorization`  , yang memungkinkan Anda untuk **mengonfigurasi berapa lama SDK harus menunggu persetujuan pengguna sebelum mengirim data ke server AppsFlyer**.

Untuk informasi selengkapnya tentang aliran data metode dan interaksinya dengan kerangka kerja ATT iOS, lihat bagian [dukungan Konfigurasikan Transparansi Pelacakan Aplikasi (ATT)](/docs/basic-sdk-integration-guide#ikhtisar-waitforattuserauthorization) .

<div id="ios-developer-instructions" />

#### INSTRUKSI PENGEMBANG IOS

Bagikan dengan pengembang Anda informasi berikut:

* Berapa lama waktu tunggu sebelum mengirimkan data ke AppsFlyer dalam hitungan detik?
* Skenario opt-in/opt-out mana yang akan digunakan?
* Tautan Pengembang:
  * [Memulai iOS SDK](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#starting-the-ios-sdk) untuk panduan pengembang dan referensi tentang cara memulai SDK.
  * [Konfigurasikan dukungan Transparansi Pelacakan Aplikasi (ATT)](/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support) untuk informasi tentang aliran data metode `waitForATTUserAuthorization` dan cara interaksinya dengan kerangka kerja ATT iOS
  * [Mengaktifkan dukungan Transparansi Pelacakan Aplikasi (ATT)](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support) untuk panduan pengembang dan referensi pada `waitForATTUserAuthorization`

</Tab>

<Tab title="Unity">

<div id="starting-the-sdk-in-Unity" />

### Memulai SDK di Unity

Kirimkan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#manual-integration">artikel Dev Hub ini</Anchor> kepada pengembang Anda tentang cara memulai SDK.

</Tab>

<Tab title="React asli">

<div id="starting-the-sdk-in-react" />

### Memulai SDK di React asli

Kirimkan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#startsdk">artikel Dev Hub ini</Anchor> kepada pengembang Anda tentang cara memulai SDK.

</Tab>
</Tabs>

## Pilih strategi untuk menjaga privasi Anda

Pilih **cara menjaga privasi pengguna.** Misalnya, pilih antara menghentikan SDK saat instalasi, mencegah berbagi data dengan pihak ketiga, menganonimkan data pengguna, atau menonaktifkan pengidentifikasi tertentu.

Untuk informasi selengkapnya tentang berbagai skenario penyisihan yang tersedia, lihat <Anchor target="_blank" href="/marketers/id/docs/apply-privacy-preserving-sdk-methods#skenario-ikut-serta-dan-tidak-ikut-serta">Skenario Keikutsertaan dan Ketidakikutsertaan</Anchor>.

## **Atribusi**

SDK mengumpulkan <Anchor target="_blank" href="/marketers/id/docs/about-device-identifiers">pengidentifikasi</Anchor> untuk tujuan atribusi. Untuk memastikan bahwa instalasi dicatat dan diatribusikan dengan benar, tinjau dan ikuti pedoman berikut.

**Semua platform**

<div id="unique-identifier-for-installs" />

<Accordion title="Pengenal unik untuk penginstalan">

ID AppsFlyer dibuat secara otomatis untuk setiap penginstalan aplikasi baru. Tidak ada tindakan yang diperlukan oleh pemasar.

Anda dapat menggunakan pengenal ini untuk melakukan tindakan berikut:

* Mengirim <Anchor target="_blank" href="/marketers/id/docs/server-to-server-events-api-for-mobile-s2s-mobile">in-app event server-ke-server</Anchor>.
* Mencocokkan ID AppsFlyer dengan catatan pengguna di sistem back end
* Unduh <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">laporan in-app event data lengkap</Anchor> dan gunakan **appsflyer\_id** untuk menganalisis perilaku dan perjalanan pengguna.

</Accordion>

<div id="integrate-unique-identifiers-from-your-bi-system-with-appsflyer" />

<Accordion title="Mengintegrasikan pengenal unik dari sistem BI Anda dengan AppsFlyer">

Menetapkan ID pengguna Pelanggan (CUID) Anda sendiri di SDK AppsFlyer untuk referensi silang ID unik dari sistem BI Anda dengan ID AppsFlyer dan pengidentifikasi lainnya. CUID tersedia di laporan <Anchor target="_blank" href="/marketers/id/docs/raw-data-field-dictionary">data lengkap</Anchor> AppsFlyer. Anda juga dapat menggunakannya dalam API postback untuk referensi silang dengan ID internal Anda.

Untuk mempelajari lebih lanjut tentang CUID, lihat <Anchor target="_blank" href="/marketers/id/docs/customer-user-id-field-cuid">artikel ini.</Anchor>

</Accordion>

**Khusus Android**

Bagian berikut menjelaskan pertimbangan atribusi untuk Google Play Store atau toko aplikasi pihak ketiga.

<div id="attribute-apps-published-on-google-play" />

<Accordion title="Aplikasi atribut yang dipublikasikan di Google Play">

#### PERUJUK INSTALASI GOOGLE PLAY

[API Perujuk Instalasi Google Play](https://developer.android.com/google/play/installreferrer) meningkatkan  <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#metode-atribusi">akurasi atribusi</Anchor> , melindungi dari penipuan penginstalan, dan memungkinkan pengambilan data rujukan yang aman dari Google Play (misalnya, versi aplikasi pada saat aplikasi pertama kali diinstal).

Sebaiknya Anda memberikan [instruksi kepada pengembang Anda untuk menambahkan Google Play Install Referrer API](https://developer.android.com/google/play/installreferrer/library).

#### GAID

Mulai SDK V4.8.0, AppsFlyer secara otomatis mengumpulkan pengenal perangkat ini.

</Accordion>

<div id="attribute-apps-in-thirdparty-app-stores" />

<Accordion title="Atribusikan aplikasi di toko aplikasi pihak ketiga">

Dengan AppsFlyer, Anda dapat <Anchor target="_blank" href="/marketers/id/docs/set-up-multi-store-android-attribution">mengatribusikan instalasi yang berasal dari app store pihak ketiga</Anchor>, seperti Amazon, Opera, GetJar, Baidu, dan Huawei. Hal ini memungkinkan Anda untuk mempromosikan aplikasi Anda dan menjangkau audiens yang lebih besar di pasar yang tidak menyediakan Google Play Store.

AppsFlyer mendukung atribusi dalam konteks toko aplikasi pihak ketiga sebagai berikut:

* **IMEI atau ID Android:** SDK tidak secara otomatis mengumpulkan IMEI atau ID Android. Namun, jika ada kebutuhan untuk mengumpulkan pengidentifikasi ini (misalnya, untuk <Anchor target="_blank" href="/marketers/id/docs/measure-attribution-in-the-chinese-domestic-market#attribution-android-apps-in-the-chinese-domestic-market">aplikasi di pasar domestik Tiongkok</Anchor>) pengembang Anda dapat menerapkan salah satu jenis pengumpulan berikut:
  * Pengumpulan manual: Aplikasi meneruskan IMEI atau ID Android ke SDK menggunakan `setImeiData` atau `setAndroidIdData` API (lihat referensi fungsi pada tab di bawah). SDK mengirimkan data ke server AppsFlyer.

    <Tabs>
    <Tab title="Android asli">

    Lihat referensi Android SDK untuk:

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setimeidata">`setImeiData`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setandroididdata">`setAndroidIdData`</Anchor>

    </Tab>

    <Tab title="Unity">

    Lihat referensi Unity SDK untuk:

    * `setImeiData`
    * `setAndroidIdData`

    </Tab>
    </Tabs>

  * Ikut serta dalam pengumpulan ID perangkat: Memaksa SDK mengumpulkan  IMEI  atau  ID Android menggunakan setCollectIMEI dan setCollectAndroidID (lihat referensi fungsi pada tab di bawah).

    <Tabs>
    <Tab title="Android asli">

    Lihat referensi Android SDK untuk:

    * `setCollectIMEI`
    * `setCollectAndroidID`

    </Tab>

    <Tab title="Unity">

    Lihat referensi Unity SDK untuk:

    * `setCollectIMEI`
    * `setCollectAndroidID`

    </Tab>

    <Tab title="React asli">

    Lihat referensi React asli untuk:

    * `setCollectIMEI`
    * `setCollectAndroidID`

    </Tab>
    </Tabs>

* **OAID:** Mengatribusikan penginstalan dari app store Android pihak ketiga. Untuk informasi lebih lanjut, lihat <Anchor target="_blank" href="/marketers/id/docs/android-oaid-implementation-in-the-sdk">panduan penerapan OAID</Anchor>.
* **Perujuk instalasi:** SDK mendukung pengambilan data rujukan dari Samsung Gallery dan Huawei AppGallery.

</Accordion>

**Khusus iOS**

Bagian berikut mencakup informasi penting tentang dukungan untuk perangkat iOS 14+.

<div id="configure-app-tracking-transparency-att-support" />

<Accordion title="Mengonfigurasi dukungan App Tracking Transparency (ATT)">

**LATAR BELAKANG**

Dimulai dari iOS 14.5, pengumpulan IDFA memerlukan persetujuan pengguna. Secara praktis, ini berarti akses IDFA diatur oleh kerangka kerja [**Transparansi Pelacakan Aplikasi**](https://developer.apple.com/documentation/apptrackingtransparency) (ATT). Pada perangkat iOS 14+, SDK menggunakan kerangka kerja ATT untuk mendapatkan akses ke IDFA perangkat. Untuk pengenalan ATT, lihat <Anchor target="_blank" href="/marketers/id/docs/about-att-and-skan#att-principles">Prinsip ATT</Anchor>.

<Tabs>
<Tab title="iOS asli">

Lihat Dev Hub untuk <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support">petunjuk pengembang dalam mengimplementasikan ATT</Anchor>.

</Tab>

<Tab title="Unity">

Lihat Dev Hub untuk <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#collect-idfa-with-attrackingmanager">petunjuk pengembang dalam mengimplementasikan ATT</Anchor>.

</Tab>
</Tabs>

Ketika atribusi terjadi menggunakan IDFA, penting agar IDFA dikirim pada **peluncuran pertama.** Karena alasan ini, SDK menyediakan metode `waitForATTUserAuthorization` .

#### Ikhtisar waitForATTUserAuthorization

> 🚧 **Penting!**
>
> Jangan panggil metode `waitForATTUserAuthorization` jika Anda tidak ingin menjalankan prompt ATT.

`waitForATTUserAuthorization` memungkinkan Anda untuk mengonfigurasi berapa lama SDK harus ditangguhkan dan menunggu status ATT sebelum mengirim data ke server AppsFlyer.

[![](https://files.readme.io/a41e66c5aa23d2c673aba5b06589dcc24d34175e90900a8232343272ecca427c-30603573710993.png)](https://files.readme.io/a41e66c5aa23d2c673aba5b06589dcc24d34175e90900a8232343272ecca427c-30603573710993.png)

Saat pengguna meluncurkan aplikasi, status ATT **notDetermined.** Selama waktu `waitForATTUserAuthorization` , SDK mengantrekan event peluncuran dan in-app event berturut-turut dalam memori, serupa dengan cara [event offline dicatat](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#offline-in-app-events):

* Jika pengguna **menyetujui** prompt ATT (pengumpulan IDFA):
  * SDK menambahkan IDFA ke event yang disimpan dalam cache.
  * SDK memulai dan mengirim event yang disimpan dalam cache dengan IDFA (tanpa menunggu waktu tunggu berakhir).

* Jika pengguna **menolak** prompt ATT: SDK akan memulai dan mengirimkan event yang di-cache tanpa IDFA (tanpa menunggu batas waktu berakhir).
* Jika batas waktu berakhir dan status ATT tetap **notDetermined:** SDK akan memulai dan mengirimkan event yang di-cache tanpa IDFA.

**Pertimbangan**

* Memanggil [`requestTrackingAuthorization`](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/3547037-requesttrackingauthorization) tanpa mengatur `waitForATTUserAuthorization` akan mengakibatkan peluncuran dan event dikirim tanpa IDFA untuk perangkat iOS 14+.
* Jika pengguna memindahkan aplikasi ke latar belakang selama waktu tunggu:
  * Timer dijeda hingga aplikasi kembali ke latar depan.
  * Event disimpan dalam cache in-memory.

* Jika pengguna mematikan aplikasi, aplikasi akan dimatikan selama waktu tunggu:
  * Timer direstart pada peluncuran aplikasi berikutnya.
  * Event yang disimpan dalam cache akan hilang.

</Accordion>

<div id="customize-att-consent-dialog" />

<Accordion title="Menyesuaikan dialog persetujuan ATT">

Anda dapat menyesuaikan prompt ATT. Pesan yang menyatakan dengan jelas tujuan permintaan dapat membantu meningkatkan tingkat keikutsertaan pengguna.

Pertimbangkan hal berikut saat membuat pesan Anda:

* Gunakan kata-kata terbaik untuk menjelaskan kepada pengguna Anda mengapa aplikasi meminta persetujuan pengguna.
* Memberi tahu pengguna tentang bagaimana data mereka akan digunakan. [Pelajari lebih lanjut tentang privasi pengguna dan penggunaan data.](https://developer.apple.com/app-store/user-privacy-and-data-use/)

Setelah pesan Anda selesai, berikan teks dan instruksi penerapan kepada pengembang Anda.

<Tabs>
<Tab title="iOS asli">

Lihat Dev Hub untuk <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#customizing-the-att-consent-dialog">instruksi pengembang dalam menyesuaikan dialog izin ATT</Anchor>.

</Tab>

<Tab title="Unity">

Lihat Dev Hub untuk [instruksi pengembang dalam menyesuaikan dialog izin ATT](https://dev.appsflyer.com/hc/docs/basicintegration#collect-idfa-with-attrackingmanager).

</Tab>
</Tabs>

[Lihat beberapa contoh eksternal dari prompt ATT.](https://www.attprompts.com/)

</Accordion>

<div id="support-for-skan-attribution" />

<Accordion title="Dukungan untuk atribusi SKAN">

> 📘 **Catatan**
>
> Untuk sepenuhnya mendukung atribusi SKAN, upgrade ke iOS SDK V6.2.3+.

SKAN adalah kelas yang digunakan oleh iOS untuk memvalidasi penginstalan aplikasi yang diarahkan pemasang iklan. Proses validasi penginstalan aplikasi melibatkan aplikasi sumber dan aplikasi yang diiklankan.

Aplikasi sumber adalah aplikasi yang berpartisipasi dalam kampanye iklan dengan menampilkan iklan dari jaringan iklan. Mengonfigurasi aplikasi Anda untuk menampilkan iklan tidak berada dalam cakupan SDK AppsFlyer. Untuk mengonfigurasi, ikuti [instruksi Apple](https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app).

Untuk aplikasi yang diiklankan (aplikasi dengan AppsFlyer SDK), <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide">solusi SKAN AppsFlyer</Anchor> menggunakan SKAN untuk menyediakan postback atribusi sementara AppsFlyer mengumpulkan, menerjemahkan, dan menggabungkan data dengan tetap menjaga privasi pengguna. Saat aplikasi diluncurkan untuk pertama kalinya, platform AppsFlyer menggunakan konfigurasi yang ditetapkan oleh pemasar untuk menginstruksikan SDK tentang cara menetapkan nilai konversi SKAN.

Untuk menggunakan solusi SKAN:

* Pemasar perlu mengonfigurasi pengukuran SKAN di AppsFlyer. Pengembang tidak perlu melakukan tugas apa pun.
* AppsFlyer SDK secara otomatis memanggil SKAN API yang diperlukan.
* Pastikan untuk menonaktifkan panggilan SKAN di SDK lain jika Anda mengandalkan AppsFlyer untuk atribusi SKAN.
* Tidak ada tindakan atau proses pendaftaran lain yang diperlukan oleh pengembang atau pemasar di App Store.

Untuk menonaktifkan atribusi SKAN, instruksikan pengembang Anda untuk menonaktifkannya di SDK.

<Tabs>
<Tab title="iOS asli">

Untuk menonaktifkan atribusi SKAN, gunakan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableskadnetwork">`disableSKAdNetwork`</Anchor>

</Tab>

<Tab title="Unity">

Untuk menonaktifkan atribusi SKAN, gunakan `disableSKAdNetwork`

</Tab>

<Tab title="React asli">

Untuk menonaktifkan atribusi SKAN gunakan `disableSKAd`

</Tab>
</Tabs>

</Accordion>

## **Merekam in-app event**

In-app event (IAE) menyediakan wawasan tentang aktivitas yang terjadi di aplikasi Anda. Merekam in-app event membantu Anda mengukur KPI seperti Return on Investment (ROI) dan Lifetime Value (LTV). Sebaiknya luangkan waktu untuk menentukan event yang ingin Anda rekam.

Setelah Anda menentukan in-app event yang ingin Anda ukur, kirim nama event dan parameter ke pengembang Anda, dan sertakan tautan ke [petunjuk penerapan](http://dev.appsflyer.com/hc/docs/in-app-events-sdk).

Untuk mempelajari lebih lanjut tentang in-app event, lihat panduan  <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview">Rich in-app event kami</Anchor> .

**Semua platform**

<div id="record-revenue" />

<Accordion title="Rekam pendapatan">

Anda dapat mengirimkan pendapatan dengan in-app event mana pun. Pastikan Anda menggunakan parameter **af\_revenue** untuk menyertakan pendapatan. Ini adalah satu-satunya parameter event yang dihitung oleh AppsFlyer sebagai pendapatan nyata di dashboard dan dalam laporan data lengkap. <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#revenue-events">Pelajari lebih lanjut</Anchor>.

<Tabs>
<Tab title="Android native">

Untuk instruksi pengembang tentang menentukan event pendapatan, lihat [di sini](https://dev.appsflyer.com/hc/docs/in-app-events-android#logging-revenue).

</Tab>

<Tab title="iOS native">

Untuk instruksi pengembang tentang menentukan event pendapatan, lihat [di sini](https://dev.appsflyer.com/hc/docs/in-app-events-ios#logging-revenue).

</Tab>

<Tab title="Unity">

* Untuk instruksi pengembang tentang in-app event secara umum, lihat [di sini](https://dev.appsflyer.com/hc/docs/inappevents#send-event).
* Untuk instruksi spesifik mengenai pendapatan di iOS dan Android, lihat tab Android dan iOS.

</Tab>
</Tabs>

</Accordion>

<div id="validate-inapp-purchases" />

<Accordion title="Validasi pembelian in-app">

SDK AppsFlyer menyediakan verifikasi server untuk pembelian in-app. Memvalidasi pembelian in-app secara otomatis mengirimkan event pembelian in-app ke AppsFlyer. Mengirim event ini sendiri membuat salinan pelaporan event.

</Accordion>

<div id="industry-verticals" />

<Accordion title="Industri vertikal">

Lihat <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#recommended-events-by-business-vertical">daftar in-app event yang direkomendasikan per vertikal</Anchor>, misalnya: perjalanan, gaming, atau eCommerce.

</Accordion>

## **Tautan langsung (deep linking) dengan OneLink**

OneLink adalah solusi AppsFlyer untuk atribusi multi-platform, **pengarahan, dan deep linking**.

**Semua platform**

<div id="device-detection-and-redirection" />

<Accordion title="Deteksi dan pengarahan perangkat">

Untuk pengguna yang tidak menginstal aplikasi Anda, OneLink mendeteksi jenis perangkat dan mengarahkan mereka ke tujuan yang benar (misalnya, Google Play, Apple App Store, app store pihak ketiga, atau halaman web). Ini berdasarkan pada pengaturan templat OneLink Anda. <Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template">Pelajari lebih lanjut</Anchor>

</Accordion>

<div id="deep-linking" />

<Accordion title="Penautan Langsung">

Untuk pengguna yang menginstal aplikasi Anda, OneLink akan membuka aplikasi. Selain membuka aplikasi, Anda juga dapat menautkan langsung pengguna ke aktivitas atau halaman tertentu di dalam aplikasi. Ini mewajibkan pengembang Anda untuk menerapkan [Tautan Langsung Terpadu (UDL)](https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl).

**Catatan**:

* UDL mewajibkan SDK V6.1+.
* Pelanggan yang telah menggunakan OneLink untuk deep linking dapat menggunakan [metode lama](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking), bukan UDL.

Lihat panduan kami tentang mengatur <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">Deep linking dan deferred deep linking</Anchor>.

</Accordion>

<div id="deferred-deep-linking" />

<Accordion title="Deferred deep linking (tautan langsung tertunda) :">

Bagi pengguna yang tidak menginstal aplikasi Anda, OneLink mendeteksi jenis perangkat dan mengarahkan mereka ke tujuan yang benar: Google Play, Apple App Store, toko aplikasi pihak ketiga, atau laman web. Setelah pengguna meluncurkan aplikasi, Anda dapat menggunakan deferred deep linking (tautan langsung tertunda) untuk mengarahkan mereka ke aktivitas atau laman tertentu di dalam aplikasi.

Hal ini mengharuskan pengembang Anda untuk menerapkan [penautan langsung tertunda dan diperluas](https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking).

**Catatan**:

* UDL mewajibkan SDK V6.1+.
* Pelanggan yang telah menggunakan OneLink untuk deferred deep linking (tautan langsung tertunda) dapat menggunakan [metode lama](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking), bukan UDL.

Lihat panduan kami tentang mengatur <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">Deep linking dan deferred deep linking</Anchor>.

</Accordion>

## **Mengakses data atribusi dan deep linking**

Tabel berikut menjelaskan metode yang tersedia untuk mengambil data atribusi dan deep linking:

| Metode | Siapa saja yang terlibat? | Kembalikan hasil | Metode pengambilan | Data atribusi | Data deep linking | Ketersediaan |
| --- | --- | --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/id/docs/push-api-streaming-raw-data">**Push API**</Anchor> | • Pemasar • Pengembang back-end | Biasanya dalam beberapa menit | Backend | Y | N | Premium |
| <Anchor target="_blank" href="/marketers/id/docs/pull-api-raw-data">**Pull API**</Anchor> | • Pemasar • Pengembang back-end | Periodik (tidak dalam waktu nyata). Anda dapat menjadwalkan unduhan laporan data lengkap. | Backend | Y | Y | Premium untuk laporan data lengkap |
| <Anchor target="_blank" href="/marketers/id/docs/data-locker-for-marketers">**Data Locker**</Anchor> | • Pemasar • Pengembang back-end | Laporan per jam tersedia dalam 1 - 3 jam | Penyimpanan cloud melalui salah satu opsi berikut: • Bucket milik AppsFlyer di AWS • Penyimpanan milik Anda (AWS atau GCS) | Y | Y | Premium |
| <Anchor target="_blank" href="/marketers/id/docs/conversion-data-payloads-and-scenarios#ringkasan">**Dapatkan data konversi (GCD)**</Anchor> | • Pemasar • Pengembang  seluler <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking">Lihat dokumentasi pengembang</Anchor> | Hingga 5 detik | SDK | Y | Y | Semua akun |
| <Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template">**Deep Linking Terpadu (Unified Deep Linking/UDL)**</Anchor> | • Pemasar • Pengembang seluler <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">Lihat dokumentasi pengembang</Anchor> | Hingga 1 detik | SDK | N | Y | Semua akun |

Perhatikan hal berikut untuk pengguna iOS 14.5+ yang tidak memberikan persetujuan:

* Ketika menggunakan UDL untuk media berbayar dan milik sendiri, data deep linking tersedia.
* Ketika menggunakan GCD untuk media berbayar, datanya terbatas dan tidak termasuk rincian atribusi dan deep linking.

> 👍 **Tips**
>
> Kami menyarankan hal berikut:
>
> * Gunakan Push API saat mengambil data atribusi dan mengirimkannya ke server Anda untuk diproses lebih lanjut. Metode ini menunggu data tersedia, dan karena itu sangat akurat dan mendekati waktu aktual. GCD mengembalikan data secara waktu aktual, tetapi mungkin tidak akurat saat keputusan atribusi akhir ditentukan setelah lebih dari 5 detik.
> * Gunakan Pull API untuk secara periodik (misalnya, setiap hari) melengkapi data atribusi waktu aktual, dan untuk mengompensasi kesalahan komunikasi yang mungkin terjadi.

## **Menguji integrasi SDK Anda**

Setelah integrasi SDK selesai, Anda dapat membuka dashboard AppsFlyer, dan dari halaman Uji Integrasi SDK, uji penginstalan organik dan non-organik, in-app event, dan deep linking (penargetan ulang). Ini memastikan bahwa penginstalan dan in-app event dicatat dan diatribusikan dengan benar.

Jika Anda memerlukan pengembang untuk menguji integrasi SDK, tambahkan pengembang sebagai  <Anchor target="_blank" href="/marketers/id/docs/user-management">pengguna</Anchor> di akun Anda, sehingga mereka dapat mengakses dashboard.

Untuk skenario dan instruksi pengujian, lihat <Anchor target="_blank" href="/marketers/id/docs/testing-the-sdk-integration-for-marketers">pengujian integrasi SDK</Anchor>.

**Catatan:** Saat melakukan pengujian atribusi, <Anchor target="_blank" href="/marketers/id/docs/registering-test-devices">daftarkan perangkat pengujian</Anchor> (Android atau iOS) untuk memastikan setiap penginstalan dicatat sebagai penginstalan baru. Perangkat uji yang terdaftar mencegah penginstalan agar tidak dicatat sebagai penginstalan ulang.

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-platform-attribution-concepts">Ikhtisar platform CTV, PC, dan konsol</Anchor>

<div data-zendesk-anchors="retrieving-the-dev-key=mengambil-kode-pengembang h_01HAWCK9K4QBRE74JAS8Q7MEXW=mengambil-kode-pengembang where-to-start-the-sdk=di-mana-memulai-sdk h_01HAWCK9K4MBS0F0HE6QE1W1AN=di-mana-memulai-sdk starting-the-sdk-in-android=memulai-sdk-di-android-asli h_01HAWCK9K45HCJEDRW761WHKES=memulai-sdk-di-android-asli select-in-what-class-to-start-the-sdk=pilih-di-kelas-apa-untuk-memulai-sdk h_01HAWCK9K428SDFBFCCSZ15X9J=pilih-di-kelas-apa-untuk-memulai-sdk android-developer-instructions=instruksi-pengembang-android h_01HAWCK9K4XR1HZHP7Y15Q2Q4N=instruksi-pengembang-android h_01HAWCK9K4693729EX1WYFR6XT=starting-the-sdk-in-ios h_01HAWCK9K4QSBP874RX2ZRA7EB=delay-the-sdk-start-in-ios h_01HAWCK9K4VHDFB9CYHC144BZN=ios-developer-instructions select-the-optoutin-scenario::ae4c6e25=pilih-strategi-untuk-menjaga-privasi-anda h_01HAWCK9K4EXBA2F0BPVBXFAMG=pilih-strategi-untuk-menjaga-privasi-anda attribution=atribusi h_01HAWCK9K41T5GGWDB3ABYGRHW=atribusi h_01HAWCK9K4HY8NZC0VM3NBF4H9=unique-identifier-for-installs h_01HAWCK9K44GRVGBB1P3FWBX4A=integrate-unique-identifiers-from-your-bi-system-with-appsflyer h_01HAWCK9K4SE4YWTQYF3R1WH2Z=attribute-apps-published-on-google-play google-play-install-referrer=perujuk-instalasi-google-play h_01HAWCK9K4V91MPQHXDZBD0HKR=perujuk-instalasi-google-play h_01HAWCK9K4YD8CYQDB2YRA8W1F=gaid h_01HAWCK9K4EFCGWJ45K8VRAFFM=attribute-apps-in-thirdparty-app-stores h_01HAWCK9K5VKBZS5MSF27WNG1G=configure-app-tracking-transparency-att-support waitforattuserauthorization-overview=ikhtisar-waitforattuserauthorization h_01HAWCK9K5JHDWS8KTBTTGSS9G=ikhtisar-waitforattuserauthorization h_01HAWCK9K5X4Z9DWRT1VDSFEPH=penting h_01HAWCK9K5FY2H211JFQQDSXHK=customize-att-consent-dialog h_01HAWCK9K5HV3SBY82A28ZD4KN=support-for-skan-attribution h_01HAWCK9K5HS9Y836X33YMV21C=catatan recording-inapp-events=merekam-in-app-event h_01HAWCK9K5ZZYQR8KPCWANZEA5=merekam-in-app-event h_01HAWCK9K50T438WCG0PKP5M3G=record-revenue h_01HAWCK9K5Z0N6DP38VCB3K3B2=validate-inapp-purchases h_01HAWCK9K5A3W2XKCM7XRNGKQK=industry-verticals deep-linking-with-onelink=tautan-langsung-deep-linking-dengan-onelink h_01HAWCK9K5PK9RE7WZQVCY97KC=tautan-langsung-deep-linking-dengan-onelink h_01HAWCK9K593KCJ9QQQV0E0E71=device-detection-and-redirection h_01HAWCK9K5SNBFHNFXYBBC20HN=deep-linking h_01HAWCK9K5YJSB78Z4RJSAP1KM=deferred-deep-linking accessing-attribution-and-deep-linking-data=mengakses-data-atribusi-dan-deep-linking h_01HAWCK9K5ACPZ2WKBTVR3VVTD=mengakses-data-atribusi-dan-deep-linking h_01HAWCK9K6N405V344RDEGC0QJ=tips testing-your-sdk-integration=menguji-integrasi-sdk-anda h_01HAWCK9K6JQ33T32RYKYH20P1=menguji-integrasi-sdk-anda h_01H9FHRVKE88CXGH8G7E26ZXT2=lihat-juga" />
