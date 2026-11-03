---
title: 'Menyiapkan atribusi Android multi-toko '
metadata:
  keywords:
    - Android
    - Google
    - Google Play
    - Add App
    - amazon
    - Advertisers
    - Agencies
    - baidu
    - Developers
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
  created_at: '2015-12-24T10:48:17Z'
  edited_at: '2023-07-29T10:11:52Z'
  id: 207447023
  locale: id
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/id/articles/207447023
---
> **Sekilas:** Atribusikan aplikasi Anda di beberapa toko Android dan lihat datanya di satu dashboard aplikasi atau di dashboard aplikasi per toko.

## Atribusi Android multi-toko

AppsFlyer mengatribusikan aplikasi, terlepas dari app store. Artinya Google Play store dan toko aplikasi Android pihak ketiga seperti Amazon, Opera, GetJar, Baidu, dan Huawei. (Toko di luar pasar AKA atau toko aplikasi Android alternatif.) Pemilik aplikasi, yang memasarkan aplikasi melalui beberapa toko, dapat memilih antara **satu** **dashboard** yang memiliki data semua toko secara bersamaan atau satu **dashboard per toko.**

> 📘 **Catatan**
>
> * Atribusi Android AppsFlyer mendukung semua jenis pengidentifikasi perangkat termasuk GAID dan <Anchor target="_blank" href="/marketers/id/docs/android-oaid-implementation-in-the-sdk">OAID</Anchor>
> * Untuk aplikasi yang dipasarkan di China, lihat <Anchor target="_blank" href="/marketers/id/docs/measure-attribution-in-the-chinese-domestic-market">Mengatribusikan aplikasi Android di pasar domestik China</Anchor>

![dasborType_us-en-new.jpg](https://files.readme.io/10fdd08c4e57f799756f46922b5f8dc45c67f7550f9105e65076652f459c98f7-9545756936593.jpg)

### Dashboard tunggal vs. dashboard per toko

* **Dashboard tunggal:** Satu dashboard yang menggabungkan data dari semua toko, termasuk Google Play Store
* **Dashboard per toko:** Beberapa dashboard—setiap toko memiliki dashboardnya sendiri. Ini berarti Anda memiliki dashboard sebanyak toko yang menyediakan aplikasi.

<table><thead><tr><th> </th><th><p>Satu dashboard<br/>[Praktik terbaik]</p></th><th> Dashboard per toko</th></tr></thead><tbody><tr><td><span id="android-package-name"></span>Nama paket Android</td><td colspan="2">Gunakan nama paket yang sama (identik) terlepas dari opsi yang dipilih. </td></tr><tr><td><span id="channel-name"></span>Nama kanal</td><td>Tidak ada yang disetel</td><td><ul><li><span>Saat menambahkan Aplikasi di dashboard AppsFlyer menggunakan opsi <strong>Toko aplikasi Android selain Play Store APK</strong>, atur channelnya.</span></li><li><span>Kanal yang mengidentifikasi toko. </span></li><li>Kombinasi nama paket dan channel Android secara unik mengidentifikasi setiap dashboard AppsFlyer. </li><li>Misalnya: Nama paket Android-nya adalah com.abc.def dan channelnya adalah xyz_device_store. Pengenal dashboard uniknya adalah com.abc.def-xyz_device_store. </li><li>Jika APK memiliki pengaturan kanal tetapi tidak ada aplikasi dengan pengaturan ini, trafik diatribusikan ke aplikasi default, menjadi aplikasi dengan pengaturan kanal yang kosong menjadi Google Play Store. </li></ul></td></tr><tr><td><span id="populating-the-install_app_store-field"></span>Mengisi bidang install_app_store</td><td><ul><li>Secara unik mengidentifikasi toko yang menyediakan aplikasi melalui unduhan.</li><li>Dalam kasus Google Play Store, ini kosong. </li><li>Nama toko diatur dalam <a href="./set-up-multi-store-android-attribution#single-dashboard-apk-preparation">manifes/APK</a>.</li></ul></td><td><p>N/A</p></td></tr><tr><td><span id="onelink-template"></span><a href="./create-a-onelink-template#prosedur" target="_blank">Templat OneLink</a></td><td>Saat bekerja dengan OneLink, metode ini disarankan. </td><td>N/A </td></tr><tr><td><span id="measurementattribution-links"></span>Tautan Pengukuran/Atribusi </td><td><ul><li>Tautannya sama terlepas dari tokonya.</li><li>Untuk mengalihkan ke toko yang benar, gunakan <a href="./set-up-multi-store-android-attribution#single-dashboard-attribution-links">af_r</a> untuk menyetel URL pengalihan</li></ul></td><td><ul><li>Tautan unik diperlukan untuk setiap toko.</li><li>Buat ini menggunakan halaman <strong>Integrasi aktif</strong> .</li><li>ID aplikasi adalah nama kanal yang ditambahkan ke nama paket android. Contoh: com.abc.def-def_store.<br/>Karenanya tautan atribusi akan berbeda.</li></ul></td></tr><tr><td><span id="reporting-options-available-having-install_app_store-field"></span>Opsi pelaporan tersedia dengan bidang install_app_store</td><td><p>Ikhtisar, Laporan kelompok, dan data lengkap mencakup bidang tersebut. Hubungi CSM Anda untuk meminta mereka menambahkan bendera fitur SFDC yang diperlukan. </p></td><td>N/A </td></tr><tr><td><span id="considerations"></span><p>Pertimbangan</p></td><td><ul><li>Akurasi atribusi: Penginstalan ulang dari toko yang berbeda tidak menghasilkan jumlah penginstalan yang meningkat. </li><li><span>Penginstalan organik akan mencerminkan penginstalan organik APK dari semua toko di bawah satu dashboard.</span></li><li><span>Opsi pelaporan, yang diperinci per toko,  saat ini terbatas pada Gambaran Umum, Kelompok, dan data lengkap.</span></li></ul></td><td><ul><li>Akurasi atribusi: Penginstalan ulang dihitung, yang menghasilkan atribusi yang kurang akurat.</li><li> <span>Lihat </span>penginstalan<span>organik</span><span> dan </span><span>non-organik</span><span> serta data in-app event per toko (kanal) pada dashboard aplikasi terpisah di AppsFlyer.</span> </li><li><span>Gunakan Kelompok untuk menampilkan laporan gabungan dari semua toko secara bersamaan</span></li><li>Pastikan mitra yang bekerja sama dengan Anda <strong>aktif</strong> (<a href="./partner-activation-deactivation" target="_blank">Aktifkan partner</a> diaktifkan) di <strong>semua</strong> dashboard. Ini <span>untuk menghindari perbedaan (lebih umum saat membandingkan data dengan SRN).</span><span></span> </li></ul></td></tr></tbody></table>

## Mengatur tugas

Alur kerja berikut mencantumkan aktivitas yang diperlukan untuk menyiapkan opsi yang diinginkan. Tugas dibagi antara pemasar dan pengembang.

Untuk opsi Dashboard-per-toko, ulangi tugas untuk setiap toko.

Sebelum Anda mulai:

* Tentukan konvensi penamaan untuk channel dan parameter install\_app\_store.
* Gunakan tabel penamaan berikut untuk memetakan kanal dan toko.
* Tabel tersebut digunakan oleh developer untuk menyiapkan APK.

<table><thead><tr><th>Parameter</th><th><p>Instruksi</p></th><th><p>Satu dashboard<br/>[Praktik terbaik]</p></th><th>Dashboard per store</th></tr></thead><tbody><tr><td>Nama paket Android</td><td>Nama paket yang identik untuk semua opsi dashboard</td><td colspan="2">Jika aplikasi sudah ada di Google Play Store, gunakan nama paket yang ada. Contoh: comb.abc.def</td></tr><tr><td>Nama kanal</td><td>Nilai unik untuk setiap toko.</td><td><p>Tidak diatur. Biarkan kosong. </p></td><td><p>Unik untuk setiap toko. Tetapkan nilai dalam APK individual yang disiapkan untuk toko dan saat menambahkan aplikasi di AppsFlyer. </p><p>Jangan mengatur channel untuk Google Play Store APK. </p></td></tr><tr><td>Instal toko aplikasi AF_STORE</td><td>Nilai unik yang mengidentifikasi toko</td><td><p><span>Unik untuk setiap toko. Tetapkan di APK melalui manifes. Setiap toko memiliki APK sendiri. </span></p></td><td> Tidak diatur</td></tr></tbody></table>

Tugas

| Langkah | Tanggung jawab | Dasbor tunggal | Dashboard per store |
| --- | --- | --- | --- |
| 1 | Pengembang | [persiapan APK](/docs/set-up-multi-store-android-attribution#single-dashboard-apk-preparation) | [persiapan APK](/docs/set-up-multi-store-android-attribution#dashboard-per-store-apk-preparation) |
| 2 | Pemasar | Tidak diperlukan tindakan. Asumsinya adalah aplikasi tersebut sudah aktif di AppsFlyer. | [Tambahkan aplikasi](/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app) di AppsFlyer. |
| 3 | Pemasar | [Siapkan tautan atribusi](/docs/set-up-multi-store-android-attribution#single-dashboard-attribution-links) | Persiapkan tautan atribusi dengan ID aplikasi yang digabungkan dengan nama kanal. Lakukan melalui halaman **Integrasi aktif** dengan cara biasa. |
| 4 | Pengembang dan pemasar | [Pengujian](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) | [Pengujian](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) |

## Prosedur

<div id="single-dashboard-apk-preparation" />

<Accordion title="Dashboard tunggal—penyiapan APK">

Nama paket Android menentukan dashboard mana yang akan berisi data atribusi. Dalam metode dashboard tunggal, semua toko memiliki nama paket Android yang identik. Tidak ada konsep parameter kanal di sini.

Identifikasi toko unduhan adalah melalui parameter AF\_STORE yang diatur pada SDK, seperti yang dijelaskan di bagian ini.  Parameter AF\_STORE tidak peka huruf besar-kecil. Misalnya, ABC, abc, Abc.

**Untuk menyiapkan APK:**

1. Buat salinan build Aplikasi. **Catatan**: Jangan mengubah nama paket Android.
2. Untuk mengidentifikasi masing-masing toko, gunakan salah satu metode berikut:
   * **Metode manifes:** Tambahkan kode berikut di dalam tag `<application>` AndroidManifest.xml untuk mengidentifikasi toko. Setel parameter AF\_STORE ke nama app store.

     ```xml
     <application>
        ...
        <meta-data android:name="AF_STORE" android:value="enter_store_name_here"/>
        ...
     </application>
     ```

     **--ATAU--**
   * **Metode API:** Siapkan APK terpisah untuk masing-masing toko aplikasi alternatif. Panggil metode setOutOfStore API untuk mengatur nilai AF\_STORE. Tetapkan nilai unik untuk masing-masing toko aplikasi.  

     ```java
     AppsFlyerLib.getInstance().setOutOfStore("enter_store_name_here")
     ```

Nilai yang ditetapkan di sini muncul di bidang data lengkap install\_app\_store. Bidang ini tersedia di:

* Dashboard Ikhtisar
* Dashboard kohort
* <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Laporan data lengkap</Anchor> (Laporan data lengkap adalah fitur premium AppsFlyer)

</Accordion>

<div id="single-dashboard-attribution-links" />

<Accordion title="Dashboard tunggal—tautan atribusi">

1. Buka **Konfigurasi** > **Integrasi Aktif** dan pilih jaringan iklan.
2. Di tab **Tautan Atribusi** , tetapkan parameter **URL Luar Toko** . Ini mengisi makro `af_r` pada tautan atribusi untuk mengarahkan ulang pengguna ke halaman landas app store yang benar. Misalnya, `&af_r=http://www.destinationurl.com` URL default diatur di halaman <Anchor target="_blank" href="/marketers/id/docs/app-settings">Pengaturan Aplikasi</Anchor> . Jika opsi tidak tersedia di halaman Pengaturan Aplikasi, minta CSM Anda untuk mengaktifkannya untuk Anda.
3. Isi macro af\_r dengan URL laman arahan toko aplikasi.
4. Tetapkan <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#parameter-link-atribusi">parameter tautan atribusitambahan</Anchor> .
5. Sumber media di luar toko **menggunakan pencocokan ID untuk atribusi** dan <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#probabilistic-modeling">pemodelan Probabilistik</Anchor> AppsFlyer berfungsi sebagai metode fallback.
6. Tambahkan satu atau beberapa placeholder ID pengguna ke URL tautan:
   * android\_id
   * advertising\_id
   * OAID
7. Salin tautan atribusi dan berikan ke mitra jaringan iklan.

</Accordion>

<div id="dashboard-per-store-apk-preparation" />

<Accordion title="Dashboard per toko—Persiapan APK">

Nama paket Android yang digabungkan dengan parameter kanal yang disetel dalam manifes menentukan dashboard toko mana yang akan berisi data atribusi.

**Untuk menyiapkan APK/manifes terpisah untuk setiap penyimpanan:**

* Tambahkan yang berikut di dalam tag `<application>` AndroidManifest.xml untuk mengidentifikasi toko. Atur parameter CHANNEL ke nama app store.

  ```xml
  <application>
       ...
       <meta-data android:name="CHANNEL" android:value="enter_store_name_here"/>
       ...
  </application>
  ```

  **Catatan:** Parameter peka huruf besar-kecil.

</Accordion>

<div id="dashboard-per-store-adding-the-app" />

<Accordion title="Dashboard per toko—menambahkan aplikasi">

Tambahkan dashboard (aplikasi) yang diidentifikasi dengan kombinasi nama paket Android dan pengaturan channel di APK/manifest. Misalnya: Nama paket Android-nya adalah com.myapp dan nama channnel-nya adalah abcstore lalu nama dashboard uniknya adalah com.myapp—abcstore.

**Untuk menambahkan dashboard per toko di AppsFlyer**:

1. Buka, **My apps (Aplikasi saya)**, klik **Add app (Tambahkan aplikasi)**.
2. Pilih **Android > Di toko pihak ketiga.**
3. Menyelesaikan:
   * **Nama paket Android:** Nama paket persis seperti yang ditampilkan di paket aplikasi.
   * **Nama kanal:** Pengidentifikasi unik (nama toko) untuk membedakan antara dashboard yang memiliki nama paket yang sama. Pastikan Anda menggunakan nilai yang sama di APK yang disiapkan untuk penyimpanan.  
     **Catatan:** Untuk nama kanal harus menggunakan huruf besar atau huruf kecil saja (a-z atau A-Z). Tidak ada karakter lain, seperti tanda hubung (-) atau garis bawah (\_), yang diizinkan.
   * **URL aplikasi:**
     * Berisi alamat unduhan URL default yang mengisi makro af\_r di tautan atribusi. Masukkan URL tempat APK dihosting atau URL halaman arahannya.
     * Anda dapat mengubah ini per tautan atribusi saat Anda membuatnya.
     * Jika Anda mengosongkan bidang ini, Anda tidak akan dapat mengatur halaman default di masa mendatang.
4. Klik **Berikutnya**.
5. Ikuti petunjuk di antarmuka untuk menyelesaikan penambahan aplikasi.

</Accordion>

<div id="testing-both-dashboard-options" />

<Accordion title="Pengujian—kedua opsi dashboard">

#### **Install Non-Organik**

**Untuk menguji penginstalan non-organik:**

1. Gunakan perangkat Android yang tidak memiliki penginstalan aplikasi Anda atau <Anchor target="_blank" href="/marketers/id/docs/registering-test-devices">daftarkan perangkat Anda</Anchor>.
2. Hasilkan tautan atribusi pengujian menggunakan <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">tautan OneLink</Anchor>. Gunakan test sebagai nama sumber Media ("&pid=test").
3. Tambahkan ID iklan menjadi GAID, OAID, atau ID Android ke URL klik.

   ```http
   http://app.appsflyer.com/com.greatapp?pid=test
   &af_r=http://www.destinationurl.com&advertising_id=b5a3-78d9b5-0f12345-xxxx
   ```

   Kirim tautan atribusi ke diri Anda sendiri melalui email dan klik. **Setelah dialihkan, jangan instal dari toko**. Sebagai gantinya, instal aplikasi versi beta yang diperbarui dengan SDK atribusi AppsFlyer yang disematkan dan luncurkan.

| Dashboard tunggal | Dashboard per store |
| --- | --- |
| <ol><li>Periksa laporan data lengkap penginstalan aplikasi Anda di halaman Ekspor Data.</li><li>Anda akan melihat satu konversi penginstalan dengan sumber media uji. Di bawah kolom berjudul **Instal App Store,** Anda akan melihat nama toko seperti yang muncul di file manifest.xml.</li><li>Anda juga dapat melihat param "af\_installstore": "STORE\_NAME" di log penginstalan.</li></ol> | <ol><li>Buka aplikasi yang diperlukan per dashboard toko.</li><li>Periksa laporan data lengkap penginstalan aplikasi di bawah halaman Data Ekspor atau lihat halaman ikhtisar aplikasi.</li><li>Anda akan melihat satu konversi penginstalan dengan sumber media "test".</li></ol> |

#### **Organic installs (Instalasi organik)**

**Untuk menguji penginstalan organik:**

1. Gunakan perangkat Android yang tidak memiliki penginstalan aplikasi Anda atau yang <Anchor target="_blank" href="/marketers/id/docs/registering-test-devices">terdaftar</Anchor>.
2. Instal aplikasi versi beta yang diperbarui dengan SDK atribusi AppsFlyer yang disematkan dan luncurkan.
3. Periksa hasilnya:

#### Hasil yang diharapkan

| Dashboard tunggal | Dashboard per store |
| --- | --- |
| Periksa halaman ikhtisar untuk penginstalan organik baru (di bawah sumber media "organik"). Saat ini, dengan metode aplikasi tunggal, tidak ada indikasi asal penginstalan organik. | <ol><li>Buka halaman dasbor dan ikhtisar aplikasi yang khusus untuk toko yang diuji.</li><li>Anda akan melihat satu konversi penginstalan di bawah sumber media "organik".</li></ol> |

</Accordion>

## Fitur tambahan

<div id="migrating-from-dashboard-per-store-to-single-dashboard" />

<Accordion title="Bermigrasi dari dasbor per toko ke dasbor tunggal">

**Untuk bermigrasi dari multi-dasbor ke dasbor tunggal**:

Persiapkan APK baru untuk toko dengan menggunakan instruksi metode dasbor tunggal yang terdapat dalam artikel ini.

</Accordion>

<div id="driving-users-to-the-amazon-app-store-from-facebook" />

<Accordion title="Mendorong pengguna dari Facebook ke app store Amazon">

1. Konfigurasikan tautan URL ke aplikasi di pengaturan aplikasi Meta Anda, di bawah bagian**Android**.
2. Masuk ke Meta sebagai admin aplikasi, buka <Anchor target="_blank" href="https://developers.facebook.com/apps/">https://developers.facebook.com/apps/</Anchor>, dan pilih aplikasi.
3. Buka pengaturan dan temukan pengaturan Android Anda, atau jika Anda belum mengonfigurasi Android, tambahkan platformnya.
4. Isi detail yang diperlukan, termasuk URL Amazon app store khusus untuk aplikasi Anda.  

    [![outofstore_1.png](https://files.readme.io/1e8c365176ac9e0e55360a8a5db1dd549518e477f3fba43206491bcf9a3023da-115010742229.png)](https://files.readme.io/1e8c365176ac9e0e55360a8a5db1dd549518e477f3fba43206491bcf9a3023da-115010742229.png)
5. Di dasbor AppsFlyer, di bawah Integrasi Aktif, pilih Meta ads, dan masukkan ID Aplikasi Facebook yang sama dengan yang Anda gunakan saat mencatat Iklan Penginstalan Aplikasi Seluler In-Store Meta dengan AppsFlyer.

</Accordion>

<div id="getting-the-data-appsflyer-reports" />

<Accordion title="Mendapatkan data - Laporan AppsFlyer tambahan">

Selain dasbor Ikhtisar, Anda dapat menggunakan metode pelaporan berikut di AppsFlyer.

* Kelompok:
  * Gabungkan beberapa dasbor (aplikasi) dalam satu laporan
  * Lihat kinerja setiap dashboard dengan mengelompokkannya dengan install\_app\_store
* Pull API (untuk metode satu aplikasi): <Anchor target="_blank" href="/marketers/id/docs/pull-api-aggregate-data">Pull API</Anchor> Data lengkap penginstalan tidak berisi **Install App Store (Penginstalan App Store)** secara default. Untuk menyertakan kolom, tambahkan yang berikut ke panggilan metode Pull API: `&additional_fields=install_app_store`
* dasbor khusus (untuk beberapa metode aplikasi): Jika Anda menggunakan pendekatan multi-dasbor, gunakan <Anchor target="_blank" href="/marketers/id/docs/custom-dashboards">dasbor khusus</Anchor> untuk menggabungkan data kinerja dari beberapa aplikasi di satu tempat.

</Accordion>

<div id="referrer-implementation-thirdparty-android-app-stores" />

<Accordion title="Implementasi Referrer (Perujuk)—Toko aplikasi pihak ketiga Android">

* Atribusi referrer didukung dalam kaitannya dengan Google Play dan toko aplikasi pihak ketiga yang tercantum di sini.
* Untuk sebagian besar toko aplikasi pihak ketiga, tidak diperlukan pengaturan atau konfigurasi lain. Untuk Xiaomi, ketergantungan ekstra perlu dikonfigurasikan. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#xiaomi-getapps-store-referrer">Pelajari lebih lanjut</Anchor>
* Atribusi oleh referrer toko aplikasi pihak ketiga ditampilkan dalam laporan data lengkap sebagai berikut:
  * Jenis pencocokan: nama toko aplikasi pihak ketiga yang diatribusikan. Misalnya, huawei\_referrer.
  * Kontributor: Jika pengguna terlibat dengan beberapa toko aplikasi sebelum menginstal aplikasi, AppsFlyer menganggap keterlibatan ini sebagai kontributor. Penginstalan diberikan ke interaksi klik terakhir. Contoh:
    * Pengguna mengeklik iklan yang ditayangkan oleh Google dan dialihkan ke Play Store. Pengguna tidak mengunduh aplikasi.
    * Pengguna mengeklik iklan lain dan dialihkan ke Samsung Galaxy store. Pengguna mengunduh dan menginstal aplikasi.
    * Atribusi diberikan ke jaringan iklan yang menyebabkan pengguna dialihkan ke Samsung Galaxy store; Google diakui sebagai kontributor.

Toko Android pihak ketiga memiliki integrasi atribusi perujuk dengan AppsFlyer

| Toko aplikasi pihak ketiga | Mulai dari | Versi SDK |
| --- | --- | --- |
| <span id="huawei-app-store"></span>Huawei App Store | Juli 2020 | 5.4.6+, 6.1.1 + |
| <span id="samsung-galaxy-store"></span>Samsung Galaxy Store | Desember 2020 | 6.1.1 + |
| <span id="xiaomi-getapps-store"></span>Xiaomi GetApps Store | September 2022 | 6.9.0 + |

<div id="troubleshooting" />

<Accordion title="Pemecahan Masalah">

### Install yang diatribusikan ke aplikasi default

Jika Anda membuat APK aplikasi dengan pengaturan kanal tetapi tidak membuat dashboard untuknya di akun AppsFlyer: Penginstalan diatribusikan ke aplikasi default, biasanya aplikasi Google Play Store di akun Anda. Jika tidak ada aplikasi default, tidak ada data yang dicatat untuk aplikasi tersebut.

</Accordion>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Sifat | Catatan |
| --- | --- |
| Pengalihan OneLink ke beberapa app store | Beberapa app store dapat diatur pada <Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template#prosedur">templat OneLink</Anchor> jika nama paket aplikasi sama untuk semua app store dan Anda menerapkan opsi dasbor tunggal. |
| Instal app store | Parameter ini tidak tersedia untuk agensi atau jaringan iklan. |

</Accordion>

<div data-zendesk-anchors="multistore-android-attribution=atribusi-android-multi-toko single-dashboard-vs-dashboard-per-store=dashboard-tunggal-vs-dashboard-per-toko reporting-options-available-having%C2%A0install_app_store-field=reporting-options-available-having-install_app_store-field setup-tasks=mengatur-tugas procedures=prosedur single-dashboard%E2%80%94apk-preparation=single-dashboard-apk-preparation single-dashboard%E2%80%94attribution-links=single-dashboard-attribution-links dashboard-per-store%E2%80%94apk-preparation=dashboard-per-store-apk-preparation dashboard-per-store%E2%80%94adding-the-app=dashboard-per-store-adding-the-app testing%E2%80%94both-dashboard-options=testing-both-dashboard-options nonorganic-installs=install-non-organik organic-installs=organic-installs-instalasi-organik expected-results=hasil-yang-diharapkan additional-features=fitur-tambahan referrer-implementation%E2%80%94thirdparty-android-app-stores=referrer-implementation-thirdparty-android-app-stores installs-attributed-to-the-default-app=install-yang-diatribusikan-ke-aplikasi-default" />
