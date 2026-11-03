---
title: Pengaturan integrasi Google Ads (AdWords)
metadata:
  keywords:
    - Integration
    - Google AdWords
    - Configuration
    - google
    - migration
    - Advertisers
    - google ads configuration
    - ads
    - google ads
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2017-05-17T19:16:15Z'
  edited_at: '2024-04-02T09:52:01Z'
  id: 115002504686
  locale: id
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/id/articles/115002504686
---
> **Sekilas:** Integrasikan akun Google Ads Anda dengan AppsFlyer untuk menampilkan data atribusi dari semua kampanye Anda.

> 🚧 **Penting!**
>
> Lihat buletin tentang <Anchor target="_blank" href="/marketers/id/docs/bulletin-supporting-the-new-google-eu-consent-policy">dukungan kebijakan persetujuan Google Uni Eropa yang baru</Anchor>.

## Menggunakan Google Ads

UI Google Ads hanya memungkinkan Anda untuk mengonfigurasi <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6247380?hl=en">Kampanye Aplikasi</Anchor>, untuk perangkat iOS dan Android.

Untuk mengatribusi pengguna dari platform lainnya, mis. Pengguna Windows Phone, Anda harus menggunakan <Anchor target="_blank" href="/marketers/id/docs/set-up-smart-script-to-convert-web-visitors#google-ads-gclid">solusi halaman arahan</Anchor> untuk menuju Google Ads.

Untuk mengonfigurasi jenis kampanye spesifik lainnya selain Kampanye Aplikasi, hubungi perwakilan Google Anda.

## Mengonfigurasi atribusi Google Ads untuk pemasang iklan

Untuk mulai mengatribusi kampanye Google Ads dengan AppsFlyer, ikuti langkah-langkah berikut:

> 📘 **Catatan**
>
> Sebagai prasyarat untuk integrasi dengan Google Ads, aplikasi Anda harus mengumpulkan IDFA / GAID. Untuk informasi lebih lanjut, lihat <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">Panduan integrasi SDK</Anchor>.

<Accordion title="Tonton">

<Embed title="Pengaturan integrasi Google Ads (AdWords)" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/f3i7cti7r5" providerUrl="https://fast.wistia.com" />

<Accordion title="Baca">

<div id="step-1-create-the-google-ads-link-id-mandatory" />

<Accordion title="Langkah 1: Buat ID Tautan Google Ads (wajib)">

Membuat ID tautan memerlukan **akses administratif Google** pada akun.

1. Masuk ke akun admin Google Ads Anda.
2. Dari menu atas, klik **Alat dan pengaturan**.
3. Di bawah menu **Setup (Pengaturan)** , pilih **Data manager (Pengelola data)** dan klik **+ Connect Product (Hubungkan Produk)**.
4. Pada bilah pencarian **Sumber data**, ketik "Analitik aplikasi pihak ketiga", pilih, dan klik **Lanjutkan**.
5. Klik **Buat ID tautan**.
6. Pilih **AppsFlyer** sebagai penyedia analitik aplikasi Anda.
7. Pilih platform, Android atau iOS.
8. Temukan aplikasi Anda dan pilih.
9. Klik **Buat ID tautan**.

</Accordion>

<div id="step-2-set-up-google-ads-on-appsflyer-mandatory" />

<Accordion title="Langkah 2: Siapkan Google Ads di AppsFlyer (wajib)">

**(Setiap anggota di akun AppsFlyer)**

1. Di AppsFlyer, dari menu samping, pilih **Berkolaborasi** > **Pasar Mitra**.
2. Cari **Google Ads** dan pilih.
3. Klik **Atur integrasi**. Anda diarahkan ke halaman pengaturan integrasi.
4. Dari tab **Integrasi** , nyalakan **Aktifkan mitra**.  
   **Catatan:** Tombol harus tetap nyala (<Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">diaktifkan</Anchor>) selama Anda bekerja dengan mitra<Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">.</Anchor>
5. Tempel **ID Tautan** yang Anda salin di langkah sebelumnya.
6. Putuskan untuk mengaktifkan atau tidak <Anchor target="_blank" href="/marketers/id/docs/support-google-eu-consent-policy#do-i-have-control-over-consent-data-for-nonue-users">**Pengguna non Uni Eropa**</Anchor>.  

   <Image alt="non eu usrs.png" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="557px" />
7. Mengonfigurasi **Instal atribusi**:
   1. Mengatur **Instal jendela lookback klik-tayang**.  
      Pilih unit jendela lookback (jam atau hari) dan atur slider ke nilai yang diinginkan. Kami merekomendasikan untuk mengatur jendela lookback menjadi 30 hari agar sesuai dengan Google Ads.
   2. [Opsional] jika Anda menjalankan kampanye pra-pendaftaran untuk aplikasi Android, atur **Jendela lookback kampanye pra-pendaftaran** (defaultnya adalah 90 hari). Slider ini menentukan jendela lookback untuk mengatribusikan penginstalan ke kampanye pra-pendaftaran.
   3. Mengaktifkan **Instal atribusi lihat-tayang.**
   4. Pilih unit jendela lookback (jam atau hari) dan atur slider ke nilai yang diinginkan. Kami merekomendasikan pengaturan jendela lookback lihat-tayang menjadi 1 hari agar sesuai dengan Google Ads.  
      **Catatan:** Google tidak mengirimkan klaim untuk tayangan aplikasi iOS. Tombol atribusi lihat-tayang penginstalan dan slider jendela lookback tidak lagi relevan untuk aplikasi iOS.  

      [![](https://files.readme.io/a6f05b9f92abf6dfdbaafc248c0381bfe063086daa10727dc088d484c1b38f0b-30759221879825.png)](https://files.readme.io/a6f05b9f92abf6dfdbaafc248c0381bfe063086daa10727dc088d484c1b38f0b-30759221879825.png)
8. Untuk mengaktifkan atribusi penginstalan ulang, aktifkan **Reinstall attribution (Atribusi penginstalan ulang)**.  
   Tidak perlu mengonfigurasi jendela lookback untuk atribusi penginstalan ulang, karena nilainya diambil dari pengaturan atribusi penginstalan.  

   > 🚧 **Penting!**
   >
   > Data konversi penginstalan ulang **disajikan sebagai session\_start** di dashboard Google Ads. Di AppsFlyer, hal ini diatribusikan dan dilihat sebagai atribusi ulang.

9. Konfigurasikan **Atribusi interaksi ulang**:  
   1. <Anchor target="_blank" href="/marketers/id/docs/app-settings#reengagement-attribution">Mengaktifkan penargetan ulang di Pengaturan Aplikasi</Anchor>.
   2. Aktifkan **Atribusi interaksi ulang.**
   3. Atur **Jendela lookback klik-tayang interaksi ulang**, yang merupakan periode waktu, dimulai dari klik iklan, saat aplikasi harus dibuka agar klik dicatat sebagai interaksi ulang. Pilih lookback window dalam satuan jam atau hari dan atur slider ke nilai yang diinginkan.
   4. Aktifkan **Atribusi lihat-tayang interaksi ulang**.  
      **Catatan:** Google tidak mengirimkan klaim untuk tayangan aplikasi iOS. Tombol atribusi lihat-tayang penginstalan dan slider jendela lookback tidak lagi relevan untuk aplikasi iOS.
   5. Mengatur **Jendela lookback lihat-tayang interaksi ulang**, yang merupakan periode waktu, dimulai dari tayangan iklan, saat aplikasi harus dibuka agar tayangan dicatat sebagai interaksi ulang. Pilih lookback window dalam satuan jam atau hari dan atur slider ke nilai yang diinginkan.
   6. Atur **Jendela interaksi ulang**. Ini adalah periode ketika in-app event pengguna diatribusikan ke sumber media yang ditargetkan ulang, melalui klik atau tayangan. Anda dapat mengatur nilai dalam satuan hari (1-90), jam (hingga 23), atau bahkan selamanya. Nilai default-nya adalah 30 hari.  

      [![](https://files.readme.io/221a5489e91a15f1d9e4db9ab8f7cbff9e47dc1b50b0f7b43323096b26008870-30759261966225.png)](https://files.readme.io/221a5489e91a15f1d9e4db9ab8f7cbff9e47dc1b50b0f7b43323096b26008870-30759261966225.png)
10. Jika Anda memiliki ekstensi aplikasi Google Ads iOS:  
    Untuk mendapatkan atribusi dari tautan iklan, buka halaman tab **<Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#attribution-link-tab">Tautan atribusi</Anchor>** , buat tautan atribusi platform tunggal AppsFlyer, dan masukkan ke dalam ekstensi aplikasi Google Ads.  
    **Catatan:** Pastikan untuk menambahkan nama kampanye statis (wajib).  

    [![](https://files.readme.io/6b7513829fb3abbaab75942e3612760f39f6ae6502064eac1f31b0783a63e95b-30759221884561.png)](https://files.readme.io/6b7513829fb3abbaab75942e3612760f39f6ae6502064eac1f31b0783a63e95b-30759221884561.png)
11. Buka tab **Cost (Biaya)**.
12. Aktifkan **Dapatkan data biaya, klik, dan tayangan**.
13. Klik tombol **Hubungkan Google Ads**dan masuk ke akun Google Anda untuk menampilkan semua biaya kampanye Google Ads Anda di AppsFlyer.  <Anchor target="_blank" href="/marketers/id/docs/google-ads-adwords-cost-and-ad-revenue">Detail selengkapnya di sini</Anchor>.
14. Klik **Simpan**.

> ❗️ **Berhenti!**
>
> Anda HARUS **[melalui langkah 4](/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory) untuk melihat penginstalan Google Ads di AppsFlyer.** Jika Anda juga perlu memetakan in-app event Anda ke Google Ads, ikuti [langkah 3](/docs/google-ads-adwords-integration-setup-for-advertisers#step-3-map-your-inapp-events-recommended) terlebih dahulu.

</Accordion>

<div id="step-3-map-your-inapp-events-recommended" />

<Accordion title="Langkah 3: Memetakan in-app event Anda (direkomendasikan)">

**(Setiap anggota yang diasosiasikan dengan akun AppsFlyer)**

[![In-app_event_postbacks_en-us.png](https://files.readme.io/fbeef1b9d6f4462750d849878045d31b4a6614a9f36d20cd9c6f69d91a34f65a-30759221886609.png)](https://files.readme.io/fbeef1b9d6f4462750d849878045d31b4a6614a9f36d20cd9c6f69d91a34f65a-30759221886609.png)

1. Buka tab **Integrasi** lalu gulir ke bawah ke bagian **Postback in-app event**.

   > 📘 **Catatan**
   >
   > Saat mengaktifkan pemetaan in-app event Google Ads untuk aplikasi **pertama kalinya:**
   >
   > * Event **af\_app\_opened** secara otomatis ditentukan dan dipetakan ke **session\_start** (jika tidak, tambahkan secara manual).
   > * Di bagian **for users from**, Anda harus memilih **Semua sumber media, termasuk organik** untuk setiap event agar Google Ads dapat menerima event ini. Setelah integrasi berhasil diatur, Anda dapat mengubah pilihan ini untuk event apa pun.

2. Aktifkan **Postback in-app event**.
3. Klik **Tambahkan event** untuk menambahkan SDK atau event server-to-server ke daftar.
4. Isi parameter berikut: 

| Nama Parameter | Deskripsi |
| --- | --- |
| **AppsFlyer event** | Nama event yang diterima oleh AppsFlyer, baik yang berasal dari SDK yang terintegrasi ke aplikasi Anda maupun dari event server ke server.<br />**Tips**: Tidak menemukan event yang Anda cari?<ul><li>Pastikan untuk mengaktifkan event di perangkat dengan penginstalan non-organik dan periksa kembali.</li><li>Ketik di **AppsFlyer event**, lalu klik **Create custom (Buat khusus)**. Baca lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#event-khusus">pemetaan event khusus.</Anchor></li></ul> |
| **mapped to partner event** | Nama atau ID unik dari setiap event, seperti yang ditentukan di Google Ads. Kemungkinan konfigurasi pemetaannya adalah:<ul><li>**Bidang teks:** Dapatkan ID event yang sesuai dari Google Ads.</li><li>**Kotak tarik-turun:** Pilih event AppsFlyer yang telah ditentukan sebelumnya yang paling sesuai.</li><li>**Seperti itu**: Kirimkan event apa adanya, tanpa pemetaan nama.</li></ul> |
| **for users from** | Pilih opsi pengiriman untuk event:<ul><li>**Mitra ini saja**: Kirimkan postback hanya jika event ini diatribusikan ke Google Ads.</li><li>**Semua sumber media, termasuk organik**: Kirimkan postback untuk event yang diatribusikan ke mitra dan event organik.</li></ul> |
| **including** | <ul><li>**Tidak ada data (default)**: Kirimkan hanya event tersebut saja tanpa nilai event.</li><li>**Nilai dan pendapatan**: Kirimkan semua parameter event, **termasuk** nilai pendapatan (jika ada dalam event).</li><li>**Nilai tanpa pendapatan**: Kirimkan semua parameter **kecuali** nilai pendapatan.</li></ul> |

5. Klik **Simpan integrasi**.
6. Setelah menyimpan integrasi, sambil tetap berada di halaman konfigurasi, Anda dapat mengintegrasikan lebih banyak aplikasi Anda dengan mitra.
   1. Dari pojok kiri atas, di bawah nama mitra, klik nama aplikasi untuk membuka daftar aplikasi.
   2. Pilih aplikasi lainnya dari daftar tarik-turun.
   3. Ulangi langkah integrasi untuk aplikasi yang dipilih.

</Accordion>

<div id="step-4-measure-your-app-conversions-mandatory" />

<Accordion title="Langkah 4: Mengukur konversi aplikasi Anda (wajib)">

> 🚧 **Penting!**
>
> Agar dapat mendaftarkan konversi baru di Google Ads, Anda harus **meluncurkan aplikasi Anda dan melakukan in-app event yang dipetakan**minimal satu kali. Untuk menguji aplikasi iOS, Anda harus mengumpulkan IDFA untuk melihat event tersebut. Mungkin diperlukan waktu hingga 6 jam hingga konversi event ditambahkan ke antrean. Setelah ditambahkan, Anda dapat mengimpornya atau konversi baru tersebut akan berubah status dari “No recent conversion (Tidak ada konversi baru)” menjadi “recording conversion (mencatat konversi)".

Langkah ini memerlukan **akses administratif Google** ke akun untuk membuat ID tautan.

Ikuti langkah-langkah yang dijelaskan dalam <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7382633?sjid=11699141105296914680-EU">dokumentasi Bantuan Google Ads</Anchor>. Perhatikan hal-hal berikut ini:

* Pada Langkah 7, centang kotak di samping **first\_open** untuk semua aplikasi Anda, dan untuk setiap event yang ingin Anda impor. Jika pengenal Event Mitra di Google Ads telah diubah atau diberi label CUSTOM, sementara nama event terkait telah dimodifikasi di AppsFlyer, Anda perlu mengimpor ulang data.
* Setelah menyelesaikan prosesnya, Anda dapat melihat event konversi pihak ketiga di halaman **Konversi** > **Ringkasan**. Jika sebuah event tidak muncul dalam daftar atau telah dihapus dari daftar konversi Google Ads
  1. Klik **Lihat semua tindakan konversi**. Filter **Status** muncul.
  2. Klik **Status** dan pilih **Semua** untuk melihat semua event, termasuk event yang dinonaktifkan dan dihapus.
* Pastikan pengaturan "sertakan dalam konversi" Anda selaras dengan sasaran kampanye Anda di Google Ads. Untuk informasi lebih lanjut, konsultasikan dengan perwakilan Google Anda atau lihat dokumentasi Google <Anchor target="_blank" href="https://support.google.com/google-ads/answer/4677036?hl=en&co=ADWORDS.IsAWNCustomer=false">di sini</Anchor>.

Selamat! Anda sekarang mengukur kampanye seluler Google Ads dengan AppsFlyer!

</Accordion>

</Accordion>

</Accordion>

> 👍 **Tips**
>
> Integrasi API Google Ads secara otomatis menyertakan fitur pemasaran ulang Google Ads. Dengan melengkapi integrasi ini dan mengirimkan event ke Google Ads, Anda dapat membuat daftar audiens pemasaran ulang di Google Ads tanpa integrasi tambahan apa pun.

## Memberikan izin kepada anggota tim Google Ads

Anda dapat memberikan Google Ads <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#permissions-tab">izin untuk mengakses data tertentu dalam akun Anda.</Anchor> Anda dapat melakukannya di halaman konfigurasi Google Ads di bawah tab Izin untuk masing-masing aplikasi Anda.

Agar dapat memperoleh izin ini dan mengakses aplikasi Anda, perwakilan Google Ads harus merupakan anggota tim mitra akun Google Ads di AppsFlyer.

Karena persyaratan privasi Google, Google hanya dapat menambahkan anggota tim baru ke akun mitra Apps Flyer-nya hanya jika diminta secara eksplisit oleh pemasang iklan.

Untuk memberikan akses ke aplikasi Anda kepada anggota tim Google Ads, lakukan hal berikut:

1. Isi dan kirim <Anchor target="_blank" href="https://docs.google.com/forms/d/e/1FAIpQLSfJmwEPxy4bXw0mEsKfJ3D5dZmRZgHS3LCiyoEFsZRos0jWIQ/viewform">formulir ini</Anchor> untuk meminta manajer akun Anda untuk ditambahkan ke mitra akun Google di AppsFlyer.
2. Tunggu konfirmasi dari Google Ads yang menyatakan bahwa manajer akun GA Anda telah ditambahkan.
3. Buka **Konfigurasi** > **Integrasi Aktif** > **Google Ads** > **Izin**, dan tambahkan email manajer akun Anda ke daftar anggota tim.
4. Aktifkan izin yang ingin Anda berikan kepada manajer akun Google Ads Anda.

Baca lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#permissions-tab">memberikan izin kepada Jaringan iklan</Anchor>.

## Mengaktifkan atribusi Google Ads untuk agensi

AppsFlyer mendukung konfigurasi agensi dengan Google Ads. Sangatlah penting bagi pemasang iklan dan agensi untuk memiliki akun Google Ads terpisah agar AppsFlyer dapat mengatribusikan data dengan tepat. Untuk detail selengkapnya, klik <Anchor target="_blank" href="/marketers/id/docs/google-ads-adwords-integration-setup-for-agencies">di sini</Anchor>.

## Mengunakan beberapa akun Google Ads

AppsFlyer mendukung penggunaan beberapa akun Google Ads dengan aplikasi yang sama. Hal ini dilakukan dengan cara membagikan ID Tautan di Google Ads dan mengimpor event ke setiap akun Google Ads.

Untuk detail selengkapnya tentang cara membagikan ID Tautan Google Ads, klik <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001">di sini</Anchor>.

## Kampanye Aplikasi iOS

**Catatan**: Bagian ini berlaku untuk kampanye aplikasi untuk penginstalan dan **tidak untuk** kampanye aplikasi untuk interaksi.

Pada 27 Januari 2021, <Anchor target="_blank" href="https://blog.google/products/ads-commerce/preparing-developers-and-advertisers-for-policy-updates/">Google mengumumkan pembaruan kebijakan</Anchor> untuk mengakomodasi rilis iOS 14.

Sejak penerapan ATT dimulai, aplikasi Google iOS tidak meminta ATT, dan oleh karena itu produk Google Ads <Anchor target="_blank" href="https://support.google.com/google-ads/answer/10417364">berhenti menggunakan</Anchor> pengenal perangkat (IDFA) yang termasuk dalam ATT.

Untuk mempertahankan pelaporan dan pengoptimalan kampanye, Google memperluas konversi yang dimodelkan ke lalu lintas iOS 14+.

Karena konversi yang dimodelkan tidak bergantung pada ID perangkat, mulai dari rilis iOS14.5, logika inventaris kampanye aplikasi penginstalan iOS yang digunakan oleh Google adalah sebagai berikut:

* Saluran/inventaris penelusuran ACI iOS tidak diatribusikan (sesuai kebijakan sebelumnya pada 24 Januari 2020).
* Saluran/inventaris YouTube ACI iOS tidak diatribusikan, karena aplikasi YouTube tidak meminta ATT sehingga IDFA tidak dapat digunakan.
* Saluran/inventaris Tampilan ACI iOS dapat diatribusikan, hanya jika ada ID perangkat, jika ada persetujuan pada aplikasi pemasang iklan dan penerbit.

## Menggunakan penautan langsung yang ditangguhkan di Kampanye aplikasi

<Anchor target="_blank" href="https://support.google.com/google-ads/answer/9959794?hl=en&ref_topic=10011599">Google feed di Kampanye aplikasi</Anchor> memungkinkan Anda untuk menciptakan pengalaman konten khusus yang lancar untuk pengguna seluler baru.

Saat calon pengguna mengeklik feed, mereka dialihkan ke halaman aplikasi. Setelah pengguna menginstal aplikasi dan meluncurkannya, SDK memasok detail produk tertentu (misalnya sepatu lari) dengan penautan langsung yang ditangguhkan. Pengembang aplikasi menggunakan data ini untuk memberikan pengalaman pengguna yang relevan dalam aplikasi.

**Untuk mengaktifkan penautan langsung yang ditangguhkan dengan Google Ads:**

1. Pastikan untuk menggunakan <Anchor target="_blank" href="/marketers/id/docs/conversion-data-payloads-and-scenarios#atribusi-ulang-dengan-deferred-deep-linking">GCD</Anchor> untuk menerima parameter `af_dp` di SDK AppsFlyer.
2. Di Google, <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9958973?hl=en&ref_topic=10011599">atur feeds</Anchor>.
3. Di AppsFlyer, buka **Konfigurasi** > **Integrasi Aktif**. Pilih **Google Ads (Adwords)**.
4. Di tab **Integration (Integrasi)**, aktifkan **Deferred deep linking (Penautan langsung yang ditangguhkan) dengan Google Ads.**
5. Klik **Simpan integrasi**.

## Pemetaan parameter Google Ads

Tabel berikut menjelaskan pemetaan parameter antara Google Ads dan AppsFlyer. Perhatikan bahwa pemasang iklan tidak dapat menambahkan parameter yang dipersonalisasi ke kampanye Google Ads mana pun.

<table><thead><tr><th><p><strong>Jenis jaringan</strong></p></th><th><strong>Pencarian</strong></th><th><strong>Tampilan</strong></th><th><strong>YouTube</strong></th></tr></thead><tbody><tr><td>Channel (af_channel)</td><td>Lihat tabel di bawah, <a href="./google-ads-adwords-integration-setup-for-advertisers#cara-mengisi-parameter-channel">Cara mengisi parameter <kbd>Channel</kbd></a> </td></tr><tr><td>Campaign (c)</td><td>Ya</td><td>Ya</td><td>Ya</td></tr><tr><td><p>Campaign id (af_c_id)</p></td><td>Ya</td><td>Ya</td><td>Ya</td></tr><tr><td>Adset (af_adset)<br/>Diisi oleh parameter ad_group_name.<br/>Jika parameter ini null, AF mengisi af_adset dengan ad_group_id.</td><td>Ya</td><td>Ya</td><td>Ya</td></tr><tr><td>Adset ID (af_adset_id) diisi oleh parameter ad_group_id Google</td><td>Ya</td><td>Ya</td><td>Ya</td></tr><tr><td><p>Ad (af_ad)</p></td><td>T/A</td><td>T/A</td><td>T/A</td></tr><tr><td>Ad ID (af_ad_id)</td><td>T/A</td><td>T/A</td><td>T/A</td></tr><tr><td>Ad Type (af_ad_type)</td><td>Ya\*</td><td>Ya\*</td><td>Ya\*</td></tr><tr><td>Site ID (af_siteid)</td><td>GoogleSearch/<br/>SearchPartners</td><td>T/A</td><td>YouTubeVideos/<br/>VideoPartners</td></tr><tr><td>Kata Kunci</td><td>T/A</td><td>T/A</td><td>T/A</td></tr></tbody></table>

### Cara mengisi parameter `Channel`

Google Ads tidak mengirimkan parameter `Channel(af_channel)` . AppsFlyer menentukan cara mengisi parameter ini untuk jenis kampanye yang diterima dari Google Ads, sesuai aturan berikut:

<table><thead><tr><th colspan="2">Jenis kampanye <strong>DAN</strong> Logika jenis jaringan:</th><th rowspan="2"> Parameter <kbd>Channel</kbd> </th><th rowspan="2">Contoh</th></tr><tr><th>campaign_type</th><th>network_type</th></tr></thead><tbody><tr><td> <kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>Shopping</kbd>, atau <kbd>Hotel</kbd> </td><td><p>Semua jenis jaringan</p></td><td><kbd>campaign_type_network_type</kbd></td><td>channel = <kbd>ACI_Search</kbd> </td></tr><tr><td><p><strong>Bukan:</strong></p><kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>Shopping</kbd>, atau <kbd>Hotel</kbd> </td><td><kbd>Tampilan</kbd></td><td><kbd>network_subtype</kbd></td><td>channel = <kbd>mGDN</kbd> </td></tr><tr><td><p><strong>Bukan:</strong></p><kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>Shopping</kbd>, atau <kbd>Hotel</kbd> </td><td><p><strong>Bukan:</strong></p><kbd>Tampilan</kbd> </td><td><kbd>network_type</kbd></td><td>channel = <kbd>Search</kbd> </td></tr></tbody></table>

Untuk informasi lebih lanjut tentang jenis iklan apa yang tersedia di tanggapan Google, lihat <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">di sini</Anchor>.

### Jenis kampanye: kampanye aplikasi

#### Perubahan nama kampanye oleh Google Ads

| Hingga 15 Februari 2021 | Mulai 23 Februari 2021 |
| --- | --- |
| UAC | ACI |
| UACE | ACE |
| UACPre | ACPRE |

**Catatan:** Jenis nama kampanye diatur sesuai dengan tanggal klik atau tayangan, bukan tanggal penginstalan.

### Parameter tampilan yang berinteraksi dalam laporan data lengkap

Engaged view adalah tayangan pengguna dari iklan video yang berlangsung lebih dari 10 detik. Ini dihitung sebagai satu klik. Untuk Android, ini ditampilkan dalam laporan data lengkap yang mengisi “sub param 5”.  
Parameter ini ditampilkan jika tampilan interaksi terjadi dalam jendela lookback klik yang ditentukan di AppsFlyer, tetapi durasi maksimalnya adalah 3 hari.

> 🚧 **Penting!**
>
> * Google adalah SRN (Self Reporting Network). Untuk informasi lebih lanjut tentang cara kerja alur atribusi untuk jaringan tersebut, klik <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns">di sini</Anchor>.
> * AppsFlyer dapat menampilkan informasi kampanye apa pun yang disediakan oleh Google. Jenis kampanye (Penelusuran, Video, Tampilan) dan informasi terkait ditentukan oleh Google. Untuk informasi lebih lanjut, klik <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">di sini</Anchor>.

## Optimalkan kampanye Google Ads untuk konversi tanpa ID perangkat

Dimulai dengan iOS14.5+ dan Android 12+, Google Ads memperkenalkan beberapa pengenal. Pengenal ini digunakan untuk atribusi deterministik dari konversi tanpa ID perangkat:

| Pengenal | Tersedia dari | Sumber | Sistem operasi | Digunakan untuk | Perincian data |
| --- | --- | --- | --- | --- | --- |
| gclid | Desember 2021 | Pengenal Google Play | Android | Penginstalan | Tingkat pengguna |
| gclid | Desember 2021 | URL Deep Link | Android + iOS | Interaksi ulang | Tingkat pengguna |
| gbraid | Maret 2021 | URL Deep Link | iOS | Interaksi ulang | Teragregasi |

Saat AppsFlyer menerima pengenal ini dan mengirimkannya dalam postback Google Ads, Google Ads dapat mengklaim konversi berdasarkan pengenal tersebut. AppsFlyer menggunakan klaim tersebut dan mempertimbangkan parameter untuk atribusi dan untuk mengaitkan event LTV.  
**Tidak diperlukan tindakan dari pemasang iklan untuk mengaktifkan penerimaan parameter ini.**

### Visibilitas data menurut sistem operasi

**Aplikasi Android:**

Di AppsFlyer dan Google Ads, pemasang iklan dapat menerima data kampanye lengkap untuk lalu lintas tanpa ID perangkat – untuk penginstalan dan interaksi ulang.

**Aplikasi iOS:**

Di Google Ads dan AppsFlyer, pemasang iklan dapat menerima data kampanye lengkap untuk lalu lintas tanpa ID perangkat bagi aktivitas interaksi ulang mereka.

> 📄 **Lihat juga**
>
> * Untuk pertimbangan terkait iOS 14, lihat <Anchor target="_blank" href="/marketers/id/docs/get-skan-postback-data-from-google-ads">interoperabilitas Google Ads SKAdNetwork dengan AppsFlyer</Anchor>.

<div data-zendesk-anchors="h_01HMEH8VW3PYCZ6GC4T5BYBS3V=penting using-google-ads=menggunakan-google-ads h_01HACTC1H575PKYKRH4T4NVKH1=menggunakan-google-ads configuring-google-ads-attribution-for-advertisers=mengonfigurasi-atribusi-google-ads-untuk-pemasang-iklan h_01HACTC1H5MANBCRWYQPNW5CC2=mengonfigurasi-atribusi-google-ads-untuk-pemasang-iklan h_01HACTC1H5XXGREE80GFHGZY7N=catatan h_01HACTC1H5XEJEPMZ4C7GP8GG6=step-1-create-the-google-ads-link-id-mandatory h_01HACTC1H5HEP9759J2PCPPZSW=step-2-set-up-google-ads-on-appsflyer-mandatory h_01HACTC1H5R995RXYRFQBFHRF1=penting-1 h_01HACTC1H5EFJKV6AXNSTNFZA4=berhenti h_01HACTC1H50DDS3WCZ9DCHKN0P=step-3-map-your-inapp-events-recommended h_01HACTC1H58WHJDBN2DRQAZKGB=catatan-1 h_01HACTC1H5GV04KFM29NCCK8J2=step-4-measure-your-app-conversions-mandatory h_01HSX7TJC7PQ0ATM1J86Z4HMYJ=penting-2 h_01HACTC1H5Z3XXS1MGBS4WYJBV=tips granting-permissions-to-google-ads-team-members=memberikan-izin-kepada-anggota-tim-google-ads h_01HACTC1H5PAY95M4H1A6WTSEF=memberikan-izin-kepada-anggota-tim-google-ads enabling-google-ads-attribution-for-agencies=mengaktifkan-atribusi-google-ads-untuk-agensi h_01HACTC1H5QE93EAYYVVDQV2WC=mengaktifkan-atribusi-google-ads-untuk-agensi running-with-multiple-google-ads-accounts=mengunakan-beberapa-akun-google-ads h_01HACTC1H5Z8B15RHQ75HVV2RP=mengunakan-beberapa-akun-google-ads ios-app-campaigns=kampanye-aplikasi-ios h_01HACTC1H5X567H6A8M3FWCTAN=kampanye-aplikasi-ios using-deferred-deep-linking-in-app-campaigns=menggunakan-penautan-langsung-yang-ditangguhkan-di-kampanye-aplikasi h_01HACTC1H57HJZNAGDKSQD6MVC=menggunakan-penautan-langsung-yang-ditangguhkan-di-kampanye-aplikasi google-ads-parameter-mapping=pemetaan-parameter-google-ads h_01HACTC1H6P1A2E160Z6GAGZZS=pemetaan-parameter-google-ads how-to-populate-the-channel-parameter=cara-mengisi-parameter-channel h_01HACTC1H6TPTDDFSMPQ9YVMDY=cara-mengisi-parameter-channel campaign-type-app-campaigns=jenis-kampanye-kampanye-aplikasi h_01HACTC1H6CEGD2E3HXHWFWBRB=jenis-kampanye-kampanye-aplikasi changes-to-campaign-names-by-google-ads=perubahan-nama-kampanye-oleh-google-ads h_01HACTC1H6A028HKVXJ66MCF6M=perubahan-nama-kampanye-oleh-google-ads engaged-view-parameter-in-raw-data-reports=parameter-tampilan-yang-berinteraksi-dalam-laporan-data-lengkap h_01HACTC1H6Q6WCTK4Z9RGV6PA4=parameter-tampilan-yang-berinteraksi-dalam-laporan-data-lengkap h_01HACTC1H62HC36C08ZBFZ05XS=penting-3 optimize-google-ads-campaigns-for-conversions-without-device-id=optimalkan-kampanye-google-ads-untuk-konversi-tanpa-id-perangkat h_01HACTC1H6EFDVN9N89Y17HDFR=optimalkan-kampanye-google-ads-untuk-konversi-tanpa-id-perangkat data-visibility-by-operating-system=visibilitas-data-menurut-sistem-operasi h_01HACTC1H6WZNMVJK479M5KJYF=visibilitas-data-menurut-sistem-operasi h_01HDP0SBEE75MAT4A4S9E7Y7FF=lihat-juga" />
