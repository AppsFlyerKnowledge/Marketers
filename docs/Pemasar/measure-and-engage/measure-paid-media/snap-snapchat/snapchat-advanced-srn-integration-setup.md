---
title: Snapchat—Pengaturan integrasi SRN tingkat lanjut
metadata:
  keywords:
    - configuration
    - snapchat measurement partner
    - snapchat
    - measurement
    - snapchat measurement analytics
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-06-13T12:28:59Z'
  edited_at: '2023-12-18T17:40:26Z'
  id: 211011983
  locale: id
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/id/articles/211011983
---
> **Sekilas:** Mulai pertengahan September 2023, Snapchat telah menjadi SRN Tingkat Lanjut. Pelajari cara mengatur integrasi antara AppsFlyer dan Snapchat untuk mengaktifkan pengukuran atribusi.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/snapchat.png?v=1" width="52px" />

## Ringkasan

Integrasi SRN Tingkat Lanjut berarti semua lalu lintas<Anchor target="_blank" href="/marketers/id/docs/appsflyer-knowledge-base-glossary?query=glossar#dual-consent">dengan izin ganda</Anchor> diatribusikan dan dilaporkan sebagai lalu lintas SRN reguler. Untuk lalu lintas yang tidak mendapat izin, AppsFlyer dapat mengatribusikan dan mengukur atribusi berdasarkan klik dan tayangan yang berasal dari Snapchat menggunakan <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns#bagaimana-cara-kerja-pengaitan-dengan-srn-tingkat-lanjut">metode atribusi lain</Anchor>, sesuai dengan batasan privasi.

## Menyiapkan integrasi Snapchat

Penyiapan dilakukan dari halaman **Integrasi aktif** , namun untuk mencari mitra baru Anda harus mengunjungi <Anchor target="_blank" href="/marketers/id/docs/partner-integrations">pasar</Anchor> terlebih dahulu.

**Untuk mengonfigurasi kampanye Anda dengan Snapchat:**

1. Di AppsFlyer, di bawah **Konfigurasi**, buka **Pasar Mitra**.
2. Temukan **Snapchat** dan pilih.
3. Tinjau Syarat dan Ketentuan Snapchat untuk Pengukuran Konversi Aplikasi Seluler (MAST), klik **Terima** untuk menerima syarat.
4. Selesaikan persiapan menggunakan tab yang relevan.
5. Klik **Save Integration**.

Untuk deskripsi terperinci dari header partner confuration window (jendela konfigurasi mitra), klik di <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">sini</Anchor>.

> 📘 **Catatan**
>
> * Beberapa setelan berbeda untuk perangkat iOS dan Android
> * Pelajari lebih lanjut cara <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner">mengatur integrasi mitra</Anchor>

<div id="integration-tab" />

<Accordion title="Tab Integrasi">

Integrasi tersebut mendukung atribusi klik dan tayangan, biaya, pendapatan iklan, dan audiens.

#### Aktifkan mitra

Pada **kunjungan pertama** di sini, Anda harus mengaktifkan **Aktifkan Mitra** untuk mengaktifkan pengaturan.  
Untuk detail lebih lanjut tentang aktivasi mitra klik <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">di sini</Anchor>.

#### Pengaturan umum

**Aktifkan atribusi**

Aktifkan **Aktivasi Mitra**untuk mengizinkan atribusi ke Snapchat.

![mceclip0.png](https://files.readme.io/cf4e73fec951e4e9d2c1919ca20adff88fc0d49d7fea9b033ab9c39194ce2702-360003259638.png)

**ID Aplikasi Snap**

1. Di Manajer Bisnis Snap, buka Apps dan salin ID Aplikasi Snap (baca panduan Snapchat tentang <Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/a/snap-app-id">cara menghasilkan ID Aplikasi Snap</Anchor>).
2. Salin ID di bidang ID Aplikasi Snap di AppsFlyer.

![snapchat-app-id.png](https://files.readme.io/2e5f53240893e2a80ba36065f67f4504f69e1167d96ef35bd7a4ab874d5a7bb9-360008280878.png)

**Jika aplikasi dipromosikan oleh agensi**,

* ID Aplikasi Snap dapat ditambahkan hanya oleh pemasang iklan.
* Jika agensi berada di bawah organisasi yang sama dengan Anda di platform iklan Snapchat, gunakan hanya satu ID Aplikasi Snap.
* Jika agensi berada di bawah organisasi berbeda di platform iklan Snapchat, permintaan dari mereka untuk memberikan ID Aplikasi Snap untuk aplikasi ini dan memasukannya ke bidang ini. Beberapa ID dapat dimasukkan. Tekan Enter setelah setiap ID.

#### Atribusi Click-Through

Slider ini memungkinkan Anda untuk mengatur **waktu maksimum dari klik ke penginstalan**. Hanya penginstalan (peluncuran pertama) yang berlangsung dalam jendela lookback yang dapat diatribusikan ke Snapchat.

Anda dapat menyesuaikan nilai ini ke 1-23 jam atau 1-30 hari. Kami merekomendasikan untuk mengatur jendela lookback Klik-tayang ke 28 hari, agar sesuai dengan Snapchat.

Detail lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/set-up-lookback-windows">click lookback window di sini</Anchor>.

<Image alt="snap-click-window.png" src="https://support.appsflyer.com/hc/article_attachments/360011563618" width="552px" />

#### Lookback Window Atribusi View-Through

Slider ini memungkinkan Anda untuk mengatur **waktu maksimum dari tayangan ke penginstalan**. Hanya penginstalan (peluncuran pertama) yang terjadi di dalam jendela lookback, setelah tayangan iklan, yang dapat diatribusikan ke Snapchat, dengan syarat tidak ada klik iklan relevan lainnya.

Anda dapat mengkustomisasi nilai ini ke 1-23 jam atau 1-7 hari. Kami merekomendasikan untuk mengatur jendela lookback view-through ke 1 hari, agar sesuai dengan Snapchat.

Detail lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/set-up-lookback-windows">atribusi view-through di sini</Anchor>.

<Image alt="snap-viewthrough-window.png" src="https://support.appsflyer.com/hc/article_attachments/360011482617" width="663px" />

#### Atribusi interaksi ulang

Aktifkan atribusi interaksi ulang untuk mulai mengatribusi interaksi ulang untuk Snapchat.  
Jika Anda adalah agensi, minta pemasang iklan untuk melakukannya untuk Anda dari pihak mereka.

#### Jendela lihat balik click-through interaksi ulang

Tetapkan durasi **jendela lihat balik click-through Re-engagement (Interaksi Ulang)** (jangka waktu maksimum setelah iklan diklik, di mana pengguna yang ditargetkan ulang dapat diatribusikan ke iklan tersebut). Anda dapat menyetel nilai dalam jam (hingga 23) atau hari (1-30):

<Image alt="snap-reengagement-activate.png" src="https://files.readme.io/318deeab0432870035a163a7b8a5b8c03be7d683bfc369104c8577674fde0036-36433422309905.png" width="642px" />

#### Jendela lihat balik view-through interaksi ulang

Untuk mulai mengatribusikan tayangan iklan penargetan ulang, aktifkan **Re-engagement view-through attribution (atribusi lihat tayang interaksi ulang)**.  
Tetapkan durasi Re-engagement view-through lookback window (jendela lookback klik-tayang interaksi ulang) (jangka waktu maksimum setelah iklan diklik, di mana pengguna yang ditargetkan ulang dapat diatribusikan ke iklan tersebut). Anda dapat menyetel nilai dalam jam (hingga 23) atau hari (1-7):

![snap-reengagement-view-through.png](https://files.readme.io/4faf93b6d8a8e45043eb9440d8f56a70eba2da51f3a572ea6cd698e072f033c6-36433415112849.png)

#### Periode Waktu Re-engagement

Tetapkan durasi jendela **Re-engagement window (jendela interaksi ulang)** (periode ketika in-app event pengguna dikaitkan ke sumber media retargeting (penargetan ulang). Anda dapat mengatur nilai dalam hari (1-90), jam (hingga 23), atau bahkan selamanya:

<Image alt="snap-reengagement-window.png" src="https://support.appsflyer.com/hc/article_attachments/360008512418" width="557px" />

#### Pengaturan postback in-app event

Petakan event AppsFlyer dengan mitra melalui postback. Jika pengiriman postback diaktifkan, ini termasuk in-app event yang ditolak (event yang diblokir oleh Protect360 atau event yang ditemukan tidak sesuai dengan aturan validasi target)

[![In-app_event_postbacks_en-us.png](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)

**Untuk mengonfigurasi postback in-app event:**

1. Atur **ID Mitra** (jika diperlukan).
2. Aktifkan  **Postback in-app event.**
3. Atur ***Jendela postback In-app event***, jika diperlukan (baca lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#periode-waktu-postback-in-app-event">konfigurasi jendela postback in-app event</Anchor>).
4. Jika tersedia, pilih apakah akan mengirim acara secara otomatis atau manual. Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped">mengirimkan semua acara sebagaimana adanya</Anchor>.
5. Klik **Add event** untuk menambahkan SDK atau event server-ke-server ke daftar.
6. Lengkapi parameter yang diperlukan.
7. [Opsional] Klik<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/6524810d15f08b4b85deab9c2cbfb8fd7880126b3c3180e3ecf4ead5f1f0a9ae-17798909160465.png" width="30px" /> untuk menyetel ketentuan pengiriman in-app-event tertentu ke mitra.  
   Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#postback-in-app-event-bersyarat">postback in-app event bersyarat</Anchor>.

| Nama Parameter | Deskripsi |
| --- | --- |
| **Event AppsFlyer** | Nama event yang diterima oleh AppsFlyer, baik yang berasal dari SDK yang terintegrasi di aplikasi Anda, atau dari event server ke server.<br />**Tip**:Tidak menemukan event yang Anda cari?<ul><li>Pastikan untuk mengaktifkan event di perangkat dengan penginstalan non-organik dan periksa kembali.</li><li>Ketik di **event AppsFlyer**, lalu klik **Create custom**. Baca lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#event-khusus">pemetaan event kustom</Anchor>.</li></ul> |
| **dipetakan ke event mitra** | Nama atau ID unik setiap event sebagaimana didefinisikan di pihak mitra. Kemungkinan konfigurasi pemetaannya adalah:<ul><li>**Bidang teks:** Dapatkan ID event terkait dari mitra.</li><li>**Kotak drop-down:** Pilih event AppsFlyer yang telah ditentukan sebelumnya yang paling sesuai.</li><li>**Apa adanya**: kirim event apa adanya, tanpa pemetaan nama.</li></ul> |
| **untuk pengguna dari** | Pilih opsi pengiriman untuk event:<ul><li>**Khusus mitra ini**: kirim postback hanya jika event ini diatribusikan ke mitra ini.</li><li>**Semua sumber media termasuk organik**: mengirimkan postback untuk event yang diatribusikan ke mitra dan event organik mana pun.</li></ul> |
| **termasuk** | <ul><li>**Tanpa data (default)**: hanya mengirim event itu sendiri tanpa nilai event.</li><li>**Nilai dan pendapatan**: mengirimkan semua parameter event, **termasuk** nilai pendapatan (jika terdapat dalam event).</li><li>**Nilai tanpa pendapatan**: kirim semua parameter **kecuali** nilai pendapatan.</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Tab tautan atribusi">

Tautan atribusi tidak tersedia untuk Snapchat.

> 📘 **Catatan**
>
> Untuk semua SRN, seperti Facebook, Apple Search Ads (Iklan Pencarian Apple), Adwords, Snapchat, dll. Tab ini tidak berfungsi karena tidak menggunakan tautan atribusi eksternal.

</Accordion>

<div id="cost-tab" />

<Accordion title="Tab Biaya">

Integrasi biaya menyediakan data teragregasi berikut ini:

* Data biaya untuk tingkat kampanye, ad set, iklan, dan kanal Anda. Lihat <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabel integrasi biaya jaringan iklan</Anchor> untuk detail selengkapnya tentang dimensi, metrik, dan fitur yang didukung.   
  **Catatan:** Data biaya memerlukan langganan <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor> .
* Data klik dan impresi.

**Untuk mengaktifkan API Biaya**:

* Ikuti <Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">petunjuk integrasi ini</Anchor>.

<div id="cost-data-sync-status" />

<Accordion title="Status sinkronisasi data biaya">

<Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Lihat status API biaya</Anchor> dan terakhir kali AppsFlyer berhasil menarik data biaya yang cocok di dashboard status integrasi biaya (dan pendapatan iklan), atau di dashboard jaringan iklan individual.

</Accordion>

<div id="stop-snapchat-cost-sync" />

<Accordion title="Menghentikan sinkronisasi biaya Snapchat">

**Berhenti mendapatkan biaya Snapchat dan menghapus akun Snapchat yang terhubung:**

* <Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">Di kolom tindakan, arahkan kursor ke sebuah akun, klik **Hapus koneksi**</Anchor>   
  Setelah dihapus, AppsFlyer berhenti mendapatkan biaya. Menghapus koneksi tidak memengaruhi data historis.

</Accordion>

> 📘 **Catatan**
>
> * Pastikan pengaturan kampanye di Snapchat adalah untuk aplikasi iOS atau Android, bukan keduanya. Jika kampanye ditujukan untuk kedua aplikasi, AppsFlyer tidak dapat memecah biaya setiap aplikasi dan biaya tidak ditampilkan di AppsFlyer.
> * Untuk menghindari perbedaan dalam data biaya, atur zona waktu yang sama di kedua <Anchor target="_blank" href="/marketers/id/docs/changing-app-time-zone-settings#changing-the-time-zone">pengaturan aplikasi</Anchor> dan akun iklan Snapchat Anda.
> * Setelah Anda mengatur biaya Snap, jangan mengubah nama dari kampanye, set iklan, atau iklan yang sedang berjalan karena dapat menyebabkan ketidaksesuaian atau hilangnya data biaya.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Tab Pendapatan Iklan">

Pendapatan Iklan tidak didukung di integrasi dengan mitra ini.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Tab Izin">

Di tab ini, Anda dapat memilih izin untuk diberikan kepada Snapchat. Catat bahwa bahkan jika atribusi dinonaktifkan untuk Snapchat, tab izin aktif dan Anda dapat memberikan kontrol ke Snapchat.

Mengaktifkan ***Izin Jaringan Iklan*** untuk memulai konfigurasi.

Setelah Anda mengaktifkan **Izin Jaringan Iklan** di:

* Aplikasi muncul di dashboard jaringan iklan
* Hak akses diberikan hanya untuk jaringan iklan ini
* Admin jaringan iklan dapat <Anchor target="_blank" href="/marketers/id/docs/manage-data-access-permissions">melihat data dasar tentang aplikasi</Anchor>

#### Memberikan hak akses ke anggota tim jaringan iklan

Admin Snapchat memiliki akses ke aplikasi Anda secara default, tetapi Anda dapat memberikan karyawan Snapchat secara spesifik izin untuk mengelola aplikasi Anda. Untuk melakukan hal tersebut, karyawan tersebut harus ditambahkan oleh admin Snapchat sebagai **anggota tim** ke AppsFlyer.

Lalu, minta alamat email dari anggota tim Snapchat yang relevan.

Untuk menambahkan anggota tim yang dapat memiliki hak akses untuk mengelola aplikasi Anda:

1. Klik **Add team member**
2. Masukkan email anggota tim jaringan iklan.
3. Klik **Add**.
4. Ulangi proses untuk menambahkan lebih banyak anggota tim jika diperlukan.

Setelah Anda mengaktifkan hak akses untuk jaringan iklan, pilih akses yang ingin Anda berikan.

Gunakan tombol ini untuk memberikan izin jaringan iklan untuk menangani konfigurasinya sendiri bagi aplikasi Anda:

#### Izin jaringan iklan

* **Allow to configure integration** (Izinkan untuk mengonfigurasi integrasi) - mengizinkan mitra untuk mengatur tab integrasi (kecuali pada postback in-app event)
* **Allow to configure in-app event postbacks** (Izinkan untuk mengonfigurasi postback in-app event) - mengizinkan mitra untuk mengatur mapping postback in-app event ke sistemnya sendiri pada tab integrasi
* **Allow access to your retention report** (Izinkan akses ke laporan retensi) - hanya ke data retensi milik mitra
* **Allow access to your aggregate loyal user data** (Izinkan akses ke data pengguna setia agregat Anda) - hanya ke data pengguna setia milik mitra
* **Allow access to your aggregate in-app events data** (Izinkan akses ke data in-app event agregat) - hanya ke data in-app event milik mitra
* **Allow access to your aggregate revenue data** (Izinkan akses ke data pendapatan agregat) - hanya ke data pendapatan yang terkait mitra
* **Allow spend ingestion** (Izinkan pengeluaran konsumsi) - di tingkat aplikasi
* **Allow access to your Protect360 dashboard** (Izinkan akses ke dashboard Protect360 Anda) - hanya ke data Protect360 milik mitra dan dengan syarat fitur ini diaktifkan untuk pemasang iklan

Pelajari lebih lanjut tentang memberikan <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#permissions-tab">izin jaringan iklan</Anchor>.

</Accordion>

## Deep linking dengan Snapchat

Deep linking dengan Snapchat didasarkan pada tautan langsung asli di platform Snapchat dengan menambahkan parameter AppsFlyer ke dalamnya.

Untuk melakukan deep linking dengan Snapchat:

1. Memverifikasi bahwa **deep linking** untuk [penargetan ulang diaktifkan untuk Snapchat.](/docs/snapchat-advanced-srn-integration-setup#bagaimana-cara-mengatur-tautan-langsung-di-platform-snap)
2. Verifikasi bahwa <Anchor target="_blank" href="/marketers/id/docs/app-settings#reengagement-attribution">atribusi interaksi ulang diaktifkan di AppsFlyer.</Anchor>
3. Ambil URI skema tautan langsung aplikasi dan tambahkan **setidaknya** parameter berikut ini:

* **PID** - Sumber media di kasus ini selalu **snapchat\_int**. Ini mengaktifkan semua data yang muncul di dashboard AppsFlyer di bawah sumber media **Snapchat\_int**.
* **C -** nama kampanye yang relevan
* **is\_retargeting=true -** bidang ini mendefinisikan kampanye ini sebagai kampanye penargetan ulang. Keterlibatan pengguna yang sudah ada dengan kampanye penargetan ulang ditandai sebagai interaksi ulang karena keberadaan bidang ini di URI. Hal ini memastikan bahwa data pengguna muncul di dashboard penargetan ulang.

> 📄 **Contoh URI**
>
> klien://home?pid=snapchat\_int&c=TEST&is\_retargeting=true

### Bagaimana cara mengatur tautan langsung di platform Snap?

1. Buka jenis peluang **Drive traffic to app**.
2. Tambahkan URI Deeplink:  
     
    [![](https://files.readme.io/428258bbc5eb2fc7332ea07356e098eb66ac2cfdd0955117a14666eb76a20f79-360001717778.png)](https://files.readme.io/428258bbc5eb2fc7332ea07356e098eb66ac2cfdd0955117a14666eb76a20f79-360001717778.png)

### Deferred deep linking dengan Snapchat

Anda dapat mengakses data konversi pengguna Snapchat secara aktual dan langsung pada level SDK menggunakan <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">deferred deep linking</Anchor>.

<Anchor target="_blank" href="/marketers/id/docs/conversion-data-payloads-and-scenarios#snapchat-conversion-data">Data konversi Snapchat</Anchor> termasuk parameter **af\_dp**, yang memungkinkan ANda untuk menautkan secara langsung dan menyajikan konten terkustomisasi, berdasarkan keterlibatan pengguna dengan iklan Anda di Snapchat.

Sebagai tambahan, Anda dapat menggunakan parameter data konversi lain, seperti **af\_adset** atau **af\_channel**.

## Mengatur Snapchat untuk agensi

Persiapan atribusi Snapchat agensi mirip dengan persiapan pemasang iklan.

Agensi tidak dapat mengatur pengaturan Privasi Lebih Lanjut—hal ini terbatas pada pemasang iklan.

Untuk menyelesaikan pengaturan, dua langkah diperlukan:

1. Pemasang iklan harus mengaktifkan **Activate Partner** untuk Snapchat untuk mengaktifkan pengaturan parameter tab integrasi.  
   Untuk detail lebih lanjut tentang aktivasi mitra, silakan klik <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">di sini</Anchor>.
2. Pada dashboard agensi, di halaman konfigurasi Snapchat, area teks ID akun Snapchat diaktifkan seperti yang dilihat di bawah ini. Agensi dapat memasukkan hingga 50 ID akun Snapchat yang berbeda di area teks. Semua data atribusi konsekuen datang dari akun yang hanya tampak di bawah dashboard agensi setelah itu.[![snapchat-agency-integration.png](https://files.readme.io/261a0246bb7da0899e653a776eb25e17ce3ae8bff1efef33acac0ef0bf99abcf-21074932431505.png)](https://files.readme.io/261a0246bb7da0899e653a776eb25e17ce3ae8bff1efef33acac0ef0bf99abcf-21074932431505.png)

> ❗️
>
> <span id="01H7WQ47EDPEDQHX9XRDKYKB1W"></span>ID akun Snapchat tidak boleh dibagikan kepada pemasang iklan atau agensi. Jika ID dibagikan maka SEMUA penginstalan pemasang iklan secara otomatis teratribusi di dashboard agensi.

## Pembatasan data lengkap

* Mulai 1 Maret 2023, Uninstall Snapchat tidak disertakan dalam laporan data lengkap
* Mulai 12 September 2023, Snapchat menyediakan data atribusi lihat-tayang terbatas kepada pemasang iklan di tingkat perangkat. Untuk sumber tingkat pengguna, seperti laporan data lengkap, pesan Push API, laporan Pull API, halaman Ekspor data, dan Data Locker, hanya kolom berikut yang diisi:

* * Sumber media (snapchat\_int)
  * Saluran
  * Jenis sentuhan yang diatribusikan (tayangan)
  * Waktu sentuh yang dikaitkan (dilaporkan sebagai tanggal saja - "hh/bb/tttt")
  * Kampanye dilaporkan sebagai "terbatas"

## Menyimpan data Snapchat

Snapchat mewajibkan pengguna atribusi untuk menghapus data tingkat pengguna 12 bulan setelah penginstalan. Ini berarti bahwa event yang dilakukan oleh pengguna 12 bulan setelah mereka menginstal aplikasi dianggap sebagai organik.

Data agregat sebelumnya tetap sama.

> 📄 **Lihat juga**
>
> <Anchor target="_blank" href="/marketers/id/docs/skan-interoperation-with-snapchat">Interoperasi Snapchat dan AppsFlyer SKAdNetwork</Anchor>

<div data-zendesk-anchors="overview=ringkasan 01H8F1RWVPTHBDGF3830DY7G7M=ringkasan setting-up-snapchat-integration=menyiapkan-integrasi-snapchat 01H7WQ47ECTZHPKMG5Z5ZPAND5=menyiapkan-integrasi-snapchat 01H88VAJH3BYZSXQGGZZJQ9N0C=catatan 01H7WQ47ECD76GFNM7VVV7C9RG=integration-tab activate-partner=aktifkan-mitra 01H7WQ47ECZB5GNCQ0XH68N1DK=aktifkan-mitra general-settings=pengaturan-umum 01H7WQ47ECQSQPP63H398NTQ6M=pengaturan-umum clickthrough-attribution=atribusi-click-through 01H7WQ47ECP56VNB2MY0WYE420=atribusi-click-through viewthrough-attribution-lookback-window=lookback-window-atribusi-view-through 01H7WQ47EC7S1SPVV70SR04CPY=lookback-window-atribusi-view-through reengagement-attribution=atribusi-interaksi-ulang 01H7WQ47ECHGMWS35VEM8MD2F2=atribusi-interaksi-ulang reengagement-clickthrough-lookback-window=jendela-lihat-balik-click-through-interaksi-ulang 01H7WQ47ECSP3H6202PAR816CX=jendela-lihat-balik-click-through-interaksi-ulang reengagement-viewthrough-lookback-window=jendela-lihat-balik-view-through-interaksi-ulang 01H7WQ47ECEW3QBCA65DVGGB7E=jendela-lihat-balik-view-through-interaksi-ulang reengagement-window=periode-waktu-re-engagement 01H7WQ47ECDVE76A1TA81SJAYZ=periode-waktu-re-engagement inapp-event-postback-settings=pengaturan-postback-in-app-event 01H7WQ47ECYF4XW9F657WRJWFW=pengaturan-postback-in-app-event 01H7WQ47EDWX9TGAD4X0E41RQ8=attribution-link-tab 01H7WQ47ED5N4REX0SFVY5ZG2K=catatan-1 01H7WQ47EDCKQ1T4NVFD3C1KV0=cost-tab 01H7WQ47ED1HYEBHFJDHTB6HJH=cost-data-sync-status 01H7WQ47ED3P53B269W93Z341E=stop-snapchat-cost-sync 01H7WQ47EDQ0253RY37PX67REV=catatan-2 01H7WQ47EDC3YB1BKNG2C7AD6J=ad-revenue-tab 01H7WQ47EDXRE05R6M1YVD9DK7=permissions-tab grant-permissions-to-ad-network-team-members=memberikan-hak-akses-ke-anggota-tim-jaringan-iklan 01H7WQ47ED0KXZ1ACV2ER2B0GJ=memberikan-hak-akses-ke-anggota-tim-jaringan-iklan ad-network-permissions=izin-jaringan-iklan 01H7WQ47ED6YSJ5Q64578A9RF8=izin-jaringan-iklan deep-linking-with-snapchat=deep-linking-dengan-snapchat 01H7WQ47EDC973V7CPE38QAQE7=deep-linking-dengan-snapchat 01H7WQ47EDXS702A9TZ7DJ8MPG=contoh-uri how-to-set-up-deep-links-on-snap-platform=bagaimana-cara-mengatur-tautan-langsung-di-platform-snap 01H7WQ47EDJAX2DW7A2JJ4XVJN=bagaimana-cara-mengatur-tautan-langsung-di-platform-snap deferred-deep-linking-with-snapchat=deferred-deep-linking-dengan-snapchat 01H7WQ47EDS3MYRN9A9ZPHXG9Z=deferred-deep-linking-dengan-snapchat setting-up-snapchat-for-agencies=mengatur-snapchat-untuk-agensi 01H7WQ47EDARK9SSP47V5MGX18=mengatur-snapchat-untuk-agensi raw-data-restrictions=pembatasan-data-lengkap h_01HA3XZPWSKVRX7VTRXT1WQ1EZ=pembatasan-data-lengkap keeping-snapchat-data=menyimpan-data-snapchat 01H7WQ47ED9STKS1CVW5EXYX0Z=menyimpan-data-snapchat h_01HE7RP6VPPAY2CCSNTJ0RVSXM=lihat-juga" />
