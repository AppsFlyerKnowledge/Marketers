---
title: Konfigurasi kampanye Unity Ads
metadata:
  keywords:
    - Unity Ads
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-06T10:05:52Z'
  edited_at: '2023-11-02T09:33:33Z'
  id: 208005086
  locale: id
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/id/articles/208005086
---
> **Sekilas:** Unity Ads, mitra terintegrasi jaringan iklan AppsFlyer, adalah jaringan iklan video untuk iOS dan Android. Selain atribusi seluler berbasis klik, Unity Ads menawarkan biaya, pendapatan iklan, dan atribusi view-through, yang dapat dicatat di AppsFlyer.

Untuk mengonfigurasi kampanye Anda dengan Unity Ads, ikuti langkah-langkah di bawah ini.

<div id="setting-up-unity-ads" />

## Menyiapkan Unity Ads

Pengaturan dilakukan dari halaman **Integrasi Aktif** , tetapi untuk menemukan partner, Anda harus pergi ke <Anchor target="_blank" href="/marketers/id/docs/partner-integrations">pasarterlebih</Anchor> dahulu.

> 📘 **Catatan**
>
> Sebelum mengatur integrasi, pastikan Anda <Anchor target="_blank" href="/marketers/id/docs/partner-integrations#contact-details">menghubungi mitra</Anchor> dan membuka akun dengan mereka.

**Untuk mengaktifkan integrasi:**

1. Pergi ke Marketplace: Dari menu atas halaman AppsFlyer mana pun, klik **Marketplace**.
2. Cari mitra dan pilih itu.
3. Klik **Atur integrasi**. Anda diarahkan ke halaman pengaturan integrasi.
4. Di tab **Integrasi**, aktifkan tombol **Aktifkan mitra**.  
   **Catatan:** Sakelar harus tetap nyala (<Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">diaktifkan</Anchor>) selama Anda bekerja dengan mitra.
5. Selesaikan konfigurasi menggunakan tab yang relevan, seperti yang dijelaskan di bawah ini.

Jendela konfigurasi Unity Ads mencakup 5 tab: Integrasi, Tautan atribusi, Biaya, Pendapatan Iklan, dan Izin. Klik pada item di bawah ini untuk membaca tentang pengaturan tab.

Untuk deskripsi terperinci dari Header Partner Configuration Window (Periode Waktu Konfigurasi Mitra), klik di <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">sini</Anchor>.

> 👍 **Tips**
>
> * Langkah <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#d">Pengaturan Umum</Anchor> di tab Integrasi bersifat **wajib** untuk semua mitra.
> * Semua langkah lainnya bersifat deskriptif atau **opsional**.

<div id="integration-tab" />

<Accordion title="Tab Integrasi">

<div id="activate-partners" />

### Aktifkan partner

Pada kunjungan pertama, Anda harus mengaktifkan tombol **Aktifkan partner** untuk mengatur integrasi. Sakelar harus tetap aktif selama Anda bekerja dengan partner.  
Untuk detail lebih lanjut tentang aktivasi partner, silakan klik <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">di sini</Anchor>.

<div id="general-settings" />

### Pengaturan umum

**Mengirimkan ID Perangkat (ID Iklan) ke Unity**

Di bagian atas tab Integrasi, ada catatan yang mengatakan bahwa Unity Ads mengharuskan mengirimkan ID perangkat kepada mereka untuk setiap penginstalan—ini dilakukan secara otomatis, tidak perlu melakukan apa pun di pihak Anda.

<Image align="center" alt="Unity_msc_new_2.png" src="https://files.readme.io/4291f0b69f8231f6644872f2dfaec84e7c93047e81f653e76ff7266387fa10a9-360002583918.png" />

**ID Game Unity Ads**

Unity Ads memerlukan koneksi dengan AppsFlyer melalui ID game unik. Jika Anda tidak mengetahui milik Anda, Anda dapat memperolehnya langsung dari Unity Ads atau Anda dapat menemukannya setelah mengunggah game, di bawah **Aplikasi** > **Kampanye**, seperti yang ditunjukkan pada tangkapan layar di bawah.

<Image align="center" alt="" src="https://files.readme.io/c3315765f33e957b82c39b638bb8113e207bfe80f242bf2e6dde3dce30287a6f-8109147574673.png" />

Unity Ads Platform memetakan satu aplikasi ke satu ID Game Unity Ads ID, per tingkat akun (pemasang iklan dan agensi akan memiliki ID Game yang berbeda untuk aplikasi yang sama). Beberapa akun di Unity Ads Platform tidak dapat menjalankan aplikasi yang sama dengan ID Game yang berbeda.

**Mengaktifkan atribusi View-Through**

Aktifkan opsi ini untuk mengaitkan penginstalan view-through dari Unity Ads. Slider lookback view-through tersedia di tab tautan atribusi (dideskripsikan di bawah).

<Image align="center" alt="Unity_ads_msc_new_3.png" src="https://files.readme.io/fab459ace7e8f1354d3bbfbca8ddefcd11376b7426a8e361abfab1b42b623880-360001875405.png" />

<div id="default-postbacks" />

### Postback Default

<Image align="center" alt="Screen_Shot_2022-07-28_at_13.07.25.png" src="https://files.readme.io/a571ddc49e490373b34144e34626a18c6c18908cec3345cd7ac70c49aa855c05-7975491293329.png" />

Kirim postback otomatis ke Unity Ads setelah penginstalan dan interaksi ulang pengguna. Gunakan bagian ini untuk menentukan sumber pengguna yang mengizinkan pengiriman postback ini:

* **Partner ini saja**: untuk acara yang datang hanya dari pengguna yang diatribusikan ke Unity Ads.
* **Semua sumber media termasuk organik**: agar seluruh basis pengguna Anda tersedia untuk dilaporkan ke Unity Ads.

<div id="note" />

> 📘 **Catatan**
>
> Sebagai jaringan semua penginstalan, Unity Ads lebih suka menerima postback untuk semua penginstalan baru aplikasi Anda dari sumber mana pun, dan mereka merekomendasikan untuk memilih **Semua sumber media termasuk organik** untuk mengirimkan semua postback penginstalan ke Unity Ads.

<div id="in-app-events-settings" />

### Pengaturan In-App Event

Petakan event AppsFlyer dengan mitra melalui postback. Jika pengiriman postback diaktifkan, ini termasuk in-app event yang ditolak (event yang diblokir oleh Protect360 atau event yang ditemukan tidak sesuai dengan aturan validasi target).

<Image align="center" alt="" src="https://files.readme.io/e0d0af3c57c8452b646dfede7b4899215825ef8455d4e41293088f98ecc026eb-7975565240337.png" />

<div id="to-configure-in-app-event-postbacks" />

#### Untuk mengonfigurasi postback in-app event:

1. Masukkan **game\_id**. Pastikan game\_id benar dan sama dengan yang digunakan untuk atribusi penginstalan.
2. Aktifkan **Postback in-app event**.
3. Atur **Jendela postback in-app event**, jika diperlukan (baca lebih lanjut tentang<Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#periode-waktu-postback-in-app-event"> konfigurasi jendela postback in-app event</Anchor>).
4. Klik **Tambahkan acara** untuk menambahkan SDK atau event server-ke-server ke daftar.
5. Isi parameter berikut:

| Nama Parameter | Deskripsi |
| --- | --- |
| **event AppsFlyer** | Nama event yang diterima oleh AppsFlyer, baik yang berasal dari SDK yang terintegrasi di aplikasi Anda, maupun dari event server ke server.<br />**Tip**: Tidak menemukan event yang Anda cari?<ul><li>Pastikan untuk mengaktifkan event di perangkat dengan penginstalan non-organik dan periksa kembali.</li><li>Ketik di **acara AppsFlyer**, lalu klik **Buat khusus**. Baca selengkapnya tentang <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#event-khusus">pemetaan event khusus.</Anchor></li></ul> |
| **dipetakan ke event mitra** | Nama atau ID unik setiap event sebagaimana didefinisikan di pihak mitra. Kemungkinan konfigurasi pemetaannya adalah:<ul><li>**Bidang teks:** Dapatkan ID event terkait dari partner.</li><li>**Kotak drop-down:**  Pilih event AppsFlyer yang telah ditentukan sebelumnya yang paling sesuai.</li><li>**Apa adanya**: Kirim event apa adanya, tanpa pemetaan nama.</li></ul> |
| **untuk pengguna dari** | Pilih opsi pengiriman untuk event:<ul><li>**Khusus mitra ini**: kirim postback hanya jika event ini diatribusikan ke mitra ini.</li><li>**Semua sumber media, termasuk organik**: mengirimkan postback untuk event yang diatribusikan ke mitra mana pun, serta event organik. Menurut Unity Ads, opsi ini direkomendasikan.</li></ul> |
| **termasuk** | <ul><li>**Tanpa data (default)**: hanya mengirim event itu sendiri tanpa nilai event.</li><li>**Nilai dan pendapatan**: mengirimkan semua parameter event, **termasuk** nilai pendapatan (jika ada dalam event). Menurut Unity Ads, opsi ini direkomendasikan.</li><li>**Nilai tanpa pendapatan**: kirim semua parameter  **kecuali**  nilai pendapatan.</li></ul> |

<div id="important" />

> 🚧 **Penting!**
>
> Pilih event SDK/server-ke-server yang benar dan pengidentifikasi event partner yang sesuai. Jangan menduplikasi acara (jangan meneruskan acara yang sama dengan nama acara SDK/server-ke-server yang berbeda).

<div id="note-1" />

> 📘 **Catatan**
>
> Anda dapat mengirimkan <Anchor target="_blank" href="/marketers/id/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">postback pendapatan iklan</Anchor> ke Unity Ads sehingga mereka dapat mengoptimalkan kampanye menggunakan data pendapatan iklan:
>
> * **Nama event:** af\_ad\_revenue
> * **Dipetakan ke:** ad\_revenue

<div id="attribution-link-tab" />

<Accordion title="Tab tautan atribusi">

Buat dan simpan tautan atribusi dan kirimkan ke mitra untuk mengatribusikan kampanye, set iklan, atau iklan tunggal tertentu - baik untuk kampanye UA maupun kampanye penargetan ulang. Anda dapat menggunakan tautan platform tunggal atau <Anchor target="_blank" href="/marketers/id/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters">Selengkapnya tentang struktur dan parameter tautan atribusi</Anchor>.  

**Untuk membuat tautan atribusi,** ikuti <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#attribution-link-tab">petunjuk ini</Anchor>.

**Catatan:**

* Saat audiens target dari aplikasi Android mencakup anak-anak, Unity mengirimkan ID iklan yang ditiadakan.
* Baca selengkapnya tentang bagaimana Unity Ads menentukan klik dan tampilan.

</Accordion>

<div id="cost-tab" />

<Accordion title="Tab Biaya">

Biaya per klik tidak didukung. AppsFlyer mendapatkan rincian biaya melalui API. Lihat <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabel integrasi biaya jaringan iklan</Anchor> untuk detail lengkap tentang dimensi, metrik, dan fitur yang didukung. 

**Catatan**:

* Data biaya memerlukan langganan ROI360.
* Data biaya dari Unity Ads hanya dapat diterima untuk unduhan yang berasal dari Google Play atau Apple App Store. Untuk Android, data biaya toko aplikasi Android pihak ketiga tidak didukung.
* Biaya agensi tidak didukung melalui biaya per klik atau API. Pemasang iklan dapat mengirimkan data biaya biro iklan melalui <Anchor target="_blank" href="/marketers/id/docs/import-cost-data">Penyerapan Pembelanjaan Iklan</Anchor>.

**Untuk mengaktifkan API Biaya**:

* Ikuti <Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">instruksi integrasi ini</Anchor>. **Catatan**:Untuk integrasi biaya Unity, semua aplikasi dengan kunci API yang sama harus berisi ID Organisasi yang sama. Jika tidak, data biaya penarikan akan terpengaruh.

<Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Lihat status API biaya</Anchor> dan terakhir kali AppsFlyer berhasil menarik data biaya yang cocok di dashboard status integrasi biaya (dan pendapatan iklan), atau di dashboard jaringan iklan individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Tab Pendapatan Iklan">

Bagian ini hanya relevan jika Anda berperan sebagai penerbit yang menampilkan iklan partner kepada pengguna Anda. Dengan demikian, Anda tentu ingin mengukur interaksi pengguna Anda yang diperoleh dari beberapa sumber, agar dapat mengetahui sumber mana yang paling menguntungkan bagi Anda.

**Untuk mengaktifkan API pendapatan iklan**:

* Ikuti <Anchor target="_blank" href="/marketers/id/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">petunjuk integrasi ini</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Tab Hak Akses">

Di tab ini, Anda dapat memilih izin untuk diberikan ke Unity Ads untuk melakukan tindakan tertentu. Perhatikan bahwa meskipun atribusi dinonaktifkan untuk Unity Ads, tab izin aktif dan Anda dapat memberikan izin kepada Unity Ads.  
Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#permissions-tab">izin yang dapat Anda berikan</Anchor>.

</Accordion>

</Accordion>

<div data-zendesk-anchors="setting-up-unity-ads=menyiapkan-unity-ads h_01HAPVZ510GTJRY1NXE0T3SMR6=menyiapkan-unity-ads h_01HAPVZ5105TY4Q4V32GPYAEER=catatan h_01HAPVZ5109NKD8GHD36EDN810=tips h_01HAPVZ510KPB0HQS9X6R4BCWT=integration-tab activate-partners=aktifkan-partner h_01HAPVZ510BGQ4KZ3S6ZP0QRE8=aktifkan-partner general-settings=pengaturan-umum h_01HAPVZ510EZ3HKJQVPMKHV5FH=pengaturan-umum default-postbacks=postback-default h_01HAPVZ511MRQXKPC78HR61X9P=postback-default h_01HAPVZ511CCXS93Y714STGQ67=catatan-1 inapp-events-settings=pengaturan-in-app-event h_01HAPVZ511CJ6JP49HYG9T6RPF=pengaturan-in-app-event to-configure-inapp-event-postbacks=untuk-mengonfigurasi-postback-in-app-event h_01HAPVZ511RMEVNASSTJNXKCJG=untuk-mengonfigurasi-postback-in-app-event h_01HAPVZ511AV30DEKMZ0YB5ZBD=penting h_01HAPVZ511PC45Q5FEXQMZ4MFC=catatan-2 h_01HAPVZ5110QVYGGCGQDHRJEQM=attribution-link-tab h_01HAPVZ511DSKFAKKNWTKV9522=cost-tab h_01HAPVZ5111WPRRMPF6GZJTRJS=ad-revenue-tab h_01HAPVZ511RBNY3HHSHJHJDPWG=permissions-tab" />
