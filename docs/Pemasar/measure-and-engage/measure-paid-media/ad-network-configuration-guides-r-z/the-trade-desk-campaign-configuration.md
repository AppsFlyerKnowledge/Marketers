---
title: Konfigurasi kampanye The Trade Desk
metadata:
  keywords:
    - Advertisers
    - The Trade Desk
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-05-13T07:34:13Z'
  edited_at: '2023-12-07T17:40:56Z'
  id: 360000894849
  locale: id
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/id/articles/360000894849
---
> **Sekilas:** The Trade Desk, mitra terintegrasi jaringan iklan AppsFlyer, menggunakan solusi periklanan seluler yang disempurnakan untuk mengembangkan kampanye yang strategis, terukur, dan cerdas untuk memenuhi kebutuhan pengguna lintas perangkat. The Trade Desk menawarkan atribusi seluler berbasis klik, atribusi seluler lihat-tayang, dan penargetan ulang berbasis klik, semuanya dapat dicatat melalui AppsFlyer.

<div id="setting-up-the-trade-desk-ttd" />

## Menyiapkan The Trade Desk (TTD)

Ikuti langkah-langkah ini untuk mengaktifkan pengukuran kampanye AppsFlyer.

<div id="step-1-define-conversion-events-in-ttd" />

<Accordion title="Langkah 1: Tentukan event konversi di TTD">

1. Di menu kiri halaman pemasang iklan TTD, klik **DATA**.
2. Dari menu atas, klik **Tambahkan Data Aplikasi**.
3. Masukkan kolom berikut di halaman **Buat Data Aplikasi** :
   * **Nama Aplikasi:** Masukkan nama aplikasi.
   * **Sistem Operasi:** Pilih **Android** atau **iOS**.   
     **Catatan:** TTD mendukung CTV di bawah opsi Android dan iOS.
   * **Melacak Vendor:** Pilih **AppsFlyer**.
   * **Event:** Klik **TAMBAHKAN EVENT** untuk menambahkan event konversi dan masukkan bidang:
     * **NAMA EVENT**: Masukkan nama event.  
       **Catatan:** Pastikan nama ditulis persis seperti di AppsFlyer, termasuk kapitalisasi, spasi, dan simbol.
     * [Opsional] **DESKRIPSI**: Tambahkan deskripsi.
     * [Opsional] **PENGGUNAAN DATA YANG DIKUMPULKAN**: Pilih **Atribusi**. Opsi ini mencakup atribusi dan penargetan ulang.
     * Untuk menambahkan lebih banyak event, klik **TAMBAHKAN EVENT** dan ulangi prosesnya.
   * **Sumber Kredit Konversi**: Pilih sumber mana yang akan dikaitkan dengan konversi, baik AppsFlyer atau The Trade Desk.   
     **Catatan:**
     * Untuk mengukur pembelian lintas perangkat dan TTD, pilih **The Trade Desk**.   
       Untuk tampilan holistik pengukuran tidak hanya di TTD, pilih **AppsFlyer**.
     * Jangan pernah mengubah pilihan ini selama kampanye.
     * Pastikan untuk memilih sumber yang benar sebelum mengeklik **BUAT DATA APLIKASI**. Anda tidak dapat mengubah sumber kredit konversi selama kampanye.
4. Klik **BUAT DATA APLIKASI**.

</Accordion>

<div id="step-2-define-conversion-events-in-appsflyer" />

<Accordion title="Langkah 2: Tentukan event konversi di AppsFlyer">

Agar AppsFlyer dapat menentukan peristiwa konversi dan memungkinkan Anda mengirimkan postback event ke TTD, Anda harus terlebih dahulu [mengintegrasikan TTD dengan AppsFlyer](/docs/the-trade-desk-campaign-configuration#mengintegrasikan-ttd-dengan-appsflyer) dan menyiapkan konfigurasi berikut:

* Pengaturan integrasi (termasuk konfigurasi postback event)
* Link Atribusi
* Hak Akses

</Accordion>

<div id="step-3-map-defined-conversion-events-from-appsflyer" />

<Accordion title="Langkah 3: Event konversi yang ditentukan oleh peta dari AppsFlyer">

1. Dari menu sebelah kiri TTD, klik **KAMPANYE**.
2. Gulir ke bawah ke **Kampanye** dan pilih kampanye dari daftar.
3. Klik **Edit Pelaporan & Atribusi**.
4. Klik **TAMBAHKAN SUMBER DATA KONVERSI**.
5. Di bawah **SUMBER DATA KONVERSI**, pilih atau ketik **AppsFlyer**. Event AppsFlyer sekarang dipetakan ke acara TTD.
6. **KONSEP LINTAS PERANGKAT**:
   * Jika Anda memilih di [Langkah 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd) (Sumber Kredit Konversi) agar konversi diatribusikan oleh TTD, pilih di sini **Rumah Tangga** untuk melihat konversi di semua kanal yang tersedia (seperti dalam aplikasi seluler dan CTV).
   * Jika Anda memilih AppsFlyer di [Langkah 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd), pilih di sini **Tidak ada**.
7. Klik **SIMPAN**.

</Accordion>

<div id="step-4-add-click-and-impression-trackers-to-campaign-creatives" />

<Accordion title="Langkah 4: Tambahkan pelacak klik dan impresi ke materi iklan kampanye">

Pada langkah ini, Anda akan menambahkan pelacak klik dan impresi yang dibuat di AppsFlyer ke setiap materi iklan di TTD.

1. Di bawah **KAMPANYE** di menu kiri TTD, klik **KREATIF** dari tab atas.
2. Pilih materi iklan dari daftar materi iklan yang terkait dengan kampanye saat ini.
3. Gulir ke bawah ke **Pelacakan**.
4. Salin [tautan atribusi](/docs/the-trade-desk-campaign-configuration#attribution-link-tab) (klik-tayang dan lihat-tayang) dari AppsFlyer, dan tempelkan ke masing-masing bidang **URL Pelacakan Impresi Piksel 1x1** .
5. Klik **SIMPAN PERUBAHAN**.
6. Ulangi langkah ini untuk setiap materi iklan yang terkait dengan kampanye.

</Accordion>

<div id="note" />

> 📘 **Catatan**
>
> Jika Anda telah memilih agar konversi diatribusikan oleh TTD (pada [Langkah 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd)), Anda dapat mengedit jendela atribusi:
>
> 1. Dari menu ikon di sebelah kanan halaman TTD mana pun, klik roda gigi untuk membuka **Preferensi Pengiklan**.
> 2. Gulir ke bawah ke **Jendela Atribusi** dan klik tombol edit di sebelah kanan.
> 3. Dari halaman **Kelola Jendela Atribusi** , edit jendela atribusi:
>    * **Menghapus duplikasi Windows:** Jumlah konversi yang dapat Anda lihat dalam jangka waktu tertentu.
>    * **Jendela Atribusi Kampanye:** Jangka waktu dari paparan iklan hingga konversi.
> 4. Klik **SIMPAN**.

<div id="integrating-ttd-with-appsflyer" />

## Mengintegrasikan TTD dengan AppsFlyer

Pengaturan dilakukan dari halaman **Integrasi** **Aktif** , tetapi untuk menemukan mitra, Anda harus pergi ke <Anchor target="_blank" href="/marketers/id/docs/partner-integrations">pasarterlebih</Anchor> dahulu.

**Untuk mengaktifkan integrasi:**

1. Pergi ke Marketplace: Dari menu atas halaman AppsFlyer mana pun, klik **Marketplace**.
2. Cari mitra dan pilih itu.
3. Klik **Atur integrasi**. Anda diarahkan ke halaman pengaturan integrasi.
4. Di tab **Integrasi**, aktifkan tombol **Aktifkan partner**.  
   **Catatan:** Toggle harus tetap nyala (<Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">diaktifkan</Anchor>) selama Anda bekerja dengan partner.
5. Selesaikan konfigurasi menggunakan tab yang relevan, seperti yang dijelaskan di bawah ini.

Jendela konfigurasi TTD mencakup tiga tab aktif: Integrasi, Tautan atribusi, dan Izin. Klik pada item di bawah ini untuk membaca tentang pengaturan tab.

Untuk deskripsi terperinci dari Partner Configuration Window (Jendela Konfigurasi Mitra), klik di <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">sini</Anchor> .

<div id="integration-tab" />

<Accordion title="Tab Integration">

<div id="activate-partner" />

#### Aktifkan mitra

Pada kunjungan pertama, Anda harus mengaktifkan sakelar **Aktifkan mitra** untuk menyiapkan integrasi. Sakelar harus tetap aktif selama Anda bekerja dengan TTD.  
Untuk detail lebih lanjut tentang aktivasi mitra, silakan klik <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">di sini</Anchor>.

<div id="advanced-privacy" />

#### Privasi Lanjutan

Untuk aplikasi iOS, sakelar <Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework">Aktifkan Privasi Lanjutan</Anchor> muncul. Saat diaktifkan, ini membatasi pembagian pengidentifikasi pengguna dengan mitra. Perhatikan bahwa ketika sakelar <Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework">Privasi Lanjutan Gabungan</Anchor> diaktifkan di Pengaturan Aplikasi, **Aktifkan Privasi Lanjutan** diaktifkan dan dikunci secara default. 

<div id="general-settings" />

#### Pengaturan Umum

**ID pelacak dan pemasang iklan**

The Trade Desk terhubung dengan AppsFlyer melalui ID jaringan unik. Jika Anda belum memiliki Tracker\_ID dan advertiserid, Anda harus mendapatkannya dari The Trade Desk untuk melanjutkan integrasi.

<Image align="center" alt="TTD_General_Settings_.png" src="https://files.readme.io/f7f2b66556f2713ff56a3bd2fcfe6fe8fe8d346a9b322904f93670ee55cf94c3-50612291000849.png" />

**Mengaktifkan atribusi Lihat-Tayang**

Nyalakan **Aktifkan atribusi Lihat-Tayang** untuk mengaitkan penginstalan lihat-tayang dari The Trade Desk. Slider lookback lihat-tayang tersedia di tab tautan atribusi  (dideskripsikan di bawah).

<div id="default-postbacks" />

#### Postback Default

<Image align="center" alt="default_postbacks_en-us.png" src="https://files.readme.io/b291c9fd4ac858723f3071bf271a041403639d49bfb1984030fc7c7306c40c16-50612291002385.png" />

Kirim postback otomatis ke The Trade Desk setelah penginstalan dan interaksi ulang pengguna. Gunakan bagian ini untuk menentukan sumber pengguna yang mengizinkan pengiriman postback ini:

* **Mitra ini saja**: untuk event yang datang hanya dari pengguna yang dikaitkan dengan The Trade Desk.
* **Semua sumber media termasuk organik**: agar seluruh basis pengguna Anda tersedia untuk dilaporkan ke The Trade Desks.

<div id="note-1" />

> 📘 **Catatan**
>
> Sebagai jaringan semua penginstalan, The Trade Desk lebih suka menerima postback untuk semua penginstalan baru aplikasi Anda dari sumber mana pun, dan mereka merekomendasikan untuk memilih **Semua sumber media termasuk organik** untuk mengirim semua postback penginstalan ke The Trade Desk.

<div id="in-app-events-settings" />

#### Pengaturan In-App Event

Petakan event AppsFlyer dengan TTD melalui postback. Jika pengiriman postback diaktifkan, ini termasuk in-app event yang ditolak (event yang diblokir oleh Protect360 atau event yang ditemukan tidak sesuai dengan aturan validasi target).

<Image align="center" alt="the_trade_desk_in_app_event_settings_en-us.png" src="https://files.readme.io/a72231e1f7d21eeb6ffd0b8e0ce056872ec7ef4670470a86e93eb7094ff9cea8-50612307447185.png" />

**Untuk mengonfigurasi postback in-app event:**

1. Masukkan **advertiserid** dan **Tracker\_ID**.
2. Aktifkan **Postback in-app event**.
3. Atur **Jendela postback in-app event**, jika diperlukan (baca lebih lanjut tentang<Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#periode-waktu-postback-in-app-event"> konfigurasi jendela postback in-app event</Anchor>).
4. Jika tersedia, pilih apakah akan mengirim event secara otomatis atau manual. Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped">mengirim semua event apa adanya</Anchor>.
5. Klik **Tambahkan event**  untuk menambahkan SDK atau event server-ke-server ke daftar.
6. Lengkapi parameter yang diperlukan.
7. [Opsional] Klik<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />untuk menyetel ketentuan pengiriman peristiwa dalam aplikasi tertentu ke TTD.  
   Pelajari lebih lanjut <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#postback-in-app-event-bersyarat">postback peristiwa dalam aplikasi bersyarat</Anchor>.

| Nama Parameter | Deskripsi |
| --- | --- |
| **Event AppsFlyer** | Nama event yang diterima oleh AppsFlyer, baik yang berasal dari SDK yang terintegrasi di aplikasi Anda, maupun dari event server ke server.<br />**Tip**: Tidak menemukan event yang Anda cari?<ul><li>Pastikan untuk melakukan testing dengan install non-organic dan periksa kembali.</li><li>Ketik di **acara AppsFlyer**, lalu klik **Buat khusus**. Baca selengkapnya tentang <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#event-khusus">pemetaan event khusus.</Anchor></li></ul> |
| **untuk pengguna dari** | Pilih opsi pengiriman untuk event:<ul><li>**Khusus mitra ini**: kirim postback hanya jika event ini diatribusikan ke mitra ini.</li><li>**Semua sumber media termasuk organik**kirim postback untuk event yang diatribusikan ke mitra mana pun, serta event organik.</li></ul> |
| **termasuk** | <ul><li>**Tanpa data (default)**: hanya mengirim event itu sendiri tanpa nilai event.</li><li>**Nilai dan pendapatan**: mengirimkan semua parameter event, **termasuk** nilai pendapatan (jika ada dalam event).</li><li>**Nilai tanpa pendapatan**: kirim semua parameter  **kecuali**  nilai pendapatan.</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Tab Link Atribusi">

Hasilkan dan simpan tautan atribusi dan kirim ke TTD untuk mengatribusikan kampanye, ad set, atau iklan tunggal tertentu - baik untuk UA maupun kampanye penargetan ulang. Anda dapat menggunakan tautan platform tunggal atau <Anchor target="_blank" href="/marketers/id/docs/onelink-guide">OneLink</Anchor>.

<div id="attribution-link-parameters" />

#### Parameter tautan atribusi

Menambahkan parameter ke tautan atribusi memungkinkan Anda melakukan analisis penelusuran secara menyeluruh. Parameter yang sudah ditentukan pada tautan atribusi dapat diedit dengan menambahkannya dan nilai barunya di sini.  Saat menyimpan tautan atribusi, semua parameter yang dikonfigurasikan di tab ini disimpan.

Pilih parameter mana yang ingin Anda tambahkan ke tautan atribusi.

<Image align="center" alt="ttd_attribution_link_parameters_en-us.png" src="https://files.readme.io/2658797286fd7d922c68a9c2f1705166672066d4179d72cf4fe0039ac3ede212-50612291012625.png" />

<div id="default-parameters" />

#### Parameter default

| Nama | Deskripsi | Parameter |
| --- | --- | --- |
| ID situs | Tetapkan parameter ID situs Anda untuk mengatribusikan penginstalan ke penerbit tertentu. Jika ada banyak penerbit, kami menyarankan untuk membatasi jumlah ID situs yang digunakan, dan menggunakan parameter ID sub situs guna menghindari <Anchor target="_blank" href="/marketers/id/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">kelebihan batasan ID situs</Anchor>. | af\_siteid |
| Nama Kampanye | Tambahkan nama kampanye Anda untuk membandingkan berbagai kampanye yang berjalan dengan TTD. | c |
| ID kampanye | Tambahkan ID kampanye Anda. | af\_c\_id |
| ID adset | Tambahkan ID adset Anda untuk membandingkan kinerja semua iklan Anda per adset. | af\_adset |
| ID iklan | Tambahkan ID iklan Anda. | af\_ad\_id |

Anda dapat menambahkan lebih banyak parameter untuk tautan atribusi. Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#attribution-link-tab">menyiapkan tautan atribusi</Anchor> dan tentang <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters">struktur dan parameter</Anchor> tautan atribusi .

<div id="parameters-for-measuring-ctv" />

#### Parameter untuk mengukur CTV

Anda dapat mengukur lalu lintas CTV dengan AppsFlyer dengan menambahkan parameter dan nilai berikut:

| Parameter | Nilai | Komentar |
| --- | --- | --- |
| redirect | false |  |
| af\_xplatform\_vt\_lookback | 1h-72h | Nilai apa pun antara 1-72 jam dapat dimasukkan |

<div id="click-through-attribution" />

#### Atribusi Click-Through

<Image align="center" alt="click-through_attribution_ttd_en-us.png" src="https://files.readme.io/9d8c4aed6aa5d8b3cba5b4e32a5245f4bd8b6d9cf50e8cc800dce66842487355-50612291014673.png" />

Gunakan slider untuk mengatur waktu maksimal dari klik hingga penginstalan. Hanya penginstalan (peluncuran pertama) yang terjadi dalam jendela lihat balik yang diatribusikan.

Kisaran jendela lookback: 1-23 jam atau 1-30 hari.

Parameter tautan atribusi: af\_click\_lookback

Pelajari selengkapnya tentang <Anchor target="_blank" href="/marketers/id/docs/set-up-lookback-windows">jendela lookback klik</Anchor>.

**Tautan atribusi klik-tayang:** Berisi semua parameter yang Anda sertakan dalam penyiapan tautan atribusi. Anda dapat menyalin tautan dan mengirimkannya ke mitra untuk diaktifkan saat prospek Anda mengeklik iklan yang sesuai. 

<div id="view-through-attribution" />

#### Atribusi lihat-tayang

<Image align="center" alt="view-through_attribution_ttd_en-us.png" src="https://files.readme.io/7435384719e46f0534149ef41612db6ee54c930bab8e8eadc1fd86ae84d5d777-50612307451921.png" />

Gunakan slider untuk mengatur waktu maksimal dari impresi ke penginstalan. Hanya penginstalan (peluncuran pertama) yang terjadi di dalam jendela lookback ini, dilanjutkan dari impresi iklan, yang diatribusikan ke mitra, dengan syarat tidak ada klik iklan relevan lainnya.

Kisaran jendela lookback: 1-24 jam.

Parameter tautan atribusi: af\_viewthrough\_lookback

Pelajari selengkapnya tentang <Anchor target="_blank" href="/marketers/id/docs/set-up-lookback-windows">atribusi lihat-tayang (view-through)</Anchor>.

**Tautan atribusi lihat-tayang:** Berisi semua parameter yang Anda sertakan dalam pengaturan tautan atribusi. Anda dapat menyalin tautan dan mengirimkannya ke mitra untuk diaktifkan saat prospek Anda mengeklik iklan yang sesuai.

</Accordion>

<div id="cost-tab" />

<Accordion title="Tab Cost">

Integrasi biaya tidak tersedia untuk The Trade Desk.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Tab Ad Revenue">

Pendapatan iklan tidak tersedia untuk The Trade Desk.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Tab Permissions">

Di tab ini, Anda dapat memilih izin untuk diberikan kepada The Trade Desk, baik bertindak sebagai jaringan iklan, agensi, atau bahkan keduanya. Perhatikan bahwa meskipun atribusi dinonaktifkan untuk The Trade Desk, tab izin dapat aktif dan Anda dapat memberikan kontrol kepada The Trade Desk.

<Image align="center" alt="" src="https://files.readme.io/8d8c3d5eb38384d92e52afdc01b0631d8fe5c9590dd618386cbf6ce90fc978f3-50612307452817.png" />

Gunakan tombol ini untuk memberikan izin pada jaringan iklan untuk menangani konfigurasinya sendiri bagi aplikasi Anda:

<div id="ad-network-permissions" />

#### **Hak Akses Ad Network**

* **Izinkan untuk mengonfigurasi integrasi:** Izinkan TTD untuk mengatur tab integrasi, kecuali untuk postback in-app event
* **Izinkan untuk mengonfigurasi postback in-app event:** Izinkan TTD untuk mengatur pemetaan postback in-app event ke dirinya sendiri, pada tab integrasi
* **Izinkan akses ke laporan retensi Anda:** Hanya untuk data retensi TTD sendiri
* **Izinkan akses ke data pengguna setia gabungan Anda:** Hanya untuk data pengguna setia TTD sendiri
* **Izinkan akses ke data in-app event gabungan Anda:** Hanya untuk data in-app event TTD sendiri
* **Izinkan akses ke data pendapatan gabungan Anda:** Hanya untuk data pendapatan yang diatribusikan ke TTD
* **Izinkan akses ke dashboard Protect360 Anda:** Hanya untuk data Protect360 milik TTD, dan asalkan Anda mengaktifkan fitur ini

Pelajari lebih lanjut tentang memberikan <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#permissions-tab">izin jaringan iklan</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-the-trade-desk-ttd=menyiapkan-the-trade-desk-ttd h_01HH2DHQWXTB9K2R07SJP1AXER=menyiapkan-the-trade-desk-ttd h_01HH2DHQWX9Y6R1J3HPYWTAC2Z=step-1-define-conversion-events-in-ttd h_01HH2DHQWXTZ5EMJNYRGJMY7QA=step-2-define-conversion-events-in-appsflyer h_01HH2DHQWXCWF0H1GJGJS2YYDA=step-3-map-defined-conversion-events-from-appsflyer step-4-add-click-and-impression-trackers%C2%A0to-campaign-creatives=step-4-add-click-and-impression-trackers-to-campaign-creatives h_01HH2DHQWX1Z10PTRM8S7538YX=step-4-add-click-and-impression-trackers-to-campaign-creatives h_01HH2DHQWXX1EEARNBC61W3CDK=catatan integrating-ttd-with-appsflyer=mengintegrasikan-ttd-dengan-appsflyer h_01GFNDH51M6KYE39C7DJW3BJ8W=mengintegrasikan-ttd-dengan-appsflyer h_01GF8CKQYVDW5Z7141MJDGGW4C=integration-tab activate-partner=aktifkan-mitra h_01HH2DHQWYME21J7JV176N71P2=aktifkan-mitra advanced-privacy=privasi-lanjutan h_01HH2DHQWYFJB3ZCWVZZ048AQP=privasi-lanjutan general-settings=pengaturan-umum h_01HH2DHQWYN3CZZCFT9X2R2N9J=pengaturan-umum default-postbacks=postback-default h_01HH2DHQWY1GPVP5W5R4XV2H9C=postback-default h_01HH2DHQWY284121FR8HSFGH45=catatan-1 inapp-events-settings=pengaturan-in-app-event h_01HH2DHQWY0XM70BPE7222XE78=pengaturan-in-app-event h_01HH2DHQWY7X522JKKC4A45BHN=attribution-link-tab attribution-link-parameters=parameter-tautan-atribusi h_01HH2DHQWY4GXPMCV5JEBFERG6=parameter-tautan-atribusi default-parameters=parameter-default h_01HH2DHQWYZSECQWRQEKDB9KZH=parameter-default parameters-for-measuring-ctv=parameter-untuk-mengukur-ctv h_01HH2DHQWYZPKCY947MWK7GEAP=parameter-untuk-mengukur-ctv clickthrough-attribution=atribusi-click-through h_01HH2DHQWYCFGJK4ZT9CXFX3X3=atribusi-click-through viewthrough-attribution=atribusi-lihat-tayang h_01HH2DHQWYP6S95MRAS39Q4RTT=atribusi-lihat-tayang h_01HH2DHQWYP5GYN2GH3C839P3N=cost-tab h_01HH2DHQWYG3KZTE0HH7QV4H6X=ad-revenue-tab h_01HH2DHQWYA9HAWT5PV092T6E9=permissions-tab ad-network-permissions=hak-akses-ad-network h_01HH2DHQWYCWYQFBDA19Z9BA8W=hak-akses-ad-network" />
