---
title: Panduan atribusi pendapatan iklan
metadata:
  keywords:
    - ad revenue
    - ad monetization
    - monetization
    - Advertisers
    - adrevenue
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2016-12-12T10:53:27Z'
  edited_at: '2023-12-18T14:41:56Z'
  id: 217490046
  locale: id
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/id/articles/217490046
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Sekilas:** Atribusikan pendapatan iklan untuk melengkapi tampilan kinerja LTV.

[![Attributes_ad_revenue.png](https://files.readme.io/e512531f0363fcda600fbad8ca8e5081d882b5721fb35fc9c449f8774859a5da-small-15734558614033.png)](https://files.readme.io/e512531f0363fcda600fbad8ca8e5081d882b5721fb35fc9c449f8774859a5da-small-15734558614033.png)

## Atribusi pendapatan iklan

* Tampilan iklan di aplikasi pada spanduk, offer wall, interstisial, dll., dan menghasilkan pendapatan iklan.
* Pendapatan iklan, digabungkan dengan in-app purchase, dan pendapatan langganan memberikan Anda gambaran LTV lengkap tentang pengguna. Dengan mencocokkan LTV pengguna dengan kampanye belanja media, ROI ditentukan dan tersedia untuk analisis lebih lanjut di platform.

**Data pendapatan iklan yang diatribusikan**:

* Diperoleh dari jaringan mediasi dan/atau monetisasi iklan melalui API server atau dengan SDK pelaporan tersemat di aplikasi (termasuk iOS 14).
* Dikaitkan dengan sumber media yang awalnya membawa pengguna. Contoh:
  * Pengguna melihat iklan dari Jaringan A dan mengunduh aplikasi Anda.
  * Tampilan iklan di dalam aplikasi.
  * Pendapatan iklan diatribusikan ke Jaringan A (bertanggung jawab atas akuisisi pengguna), siapa pun yang mempublikasikan iklan.
* Perincian pelaporan bergantung pada integrasi jaringan monetisasi dan jenis atribusi pendapatan iklan.

<div id="integration-types-for-ad-revenue-attribution" />

<Accordion title="Jenis integrasi untuk atribusi pendapatan iklan">

Atribusi pendapatan iklan mendukung berbagai metode perincian. Perinciannya bergantung pada jaringan monetisasi.

| Jenis integrasi atribusi pendapatan iklan | Deskripsi |
| --- | --- |
| [Tingkat agregat](/docs/roi360-guide-ad-revenue-attribution#aggregate-granularity-using-app-open-or-inapp-events) melalui S2S API | <ul><li>AppsFlyer mendapatkan pendapatan setiap hari yang dikelompokkan berdasarkan geo.</li><li>Pendapatan efektif per tindakan (eRPA) diperoleh dengan membagi pendapatan dengan jumlah event pemicu.</li><li>Peristiwa pemicu adalah event terbuka aplikasi atau in-app event spesifik yang diatur dalam aplikasi.</li><li>Jika Anda menggunakan jaringan mediasi, pastikan untuk menonaktifkan integrasi pendapatan iklan untuk mitra monetisasi yang dimediasi melalui jaringan mediasi sebelum mengaktifkan integrasi pendapatan iklan dengan jaringan mediasi. Kegagalan untuk melakukannya mengakibatkan data duplikat.</li></ul> |
| [Tingkat perangkat](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data) melalui S2S API | <ul><li>Jaringan mediasi atau monetisasi melaporkan pendapatan menurut pengguna di tingkat perangkat. Tidak semua jaringan mendukung perincian tingkat perangkat.</li><li>Pendapatan ini dikaitkan dengan sumber media yang membawa pengguna. Artinya, atribusi pendapatan iklan AppsFlyer mematuhi aturan atribusi yang ditemukan di platform, termasuk aturan atribusi penargetan ulang.</li><li>Jika Anda menggunakan jaringan mediasi, pastikan untuk menonaktifkan integrasi pendapatan iklan untuk mitra monetisasi yang dimediasi melalui jaringan mediasi sebelum mengaktifkan integrasi pendapatan iklan dengan jaringan mediasi. Kegagalan untuk melakukannya mengakibatkan data duplikat.</li><li>Tingkat perangkat melalui S2S API menyertakan 100% pendapatan iklan dan memiliki akurasi data terbesar dari jenis integrasi pendapatan iklan.</li><li>Data tersedia dalam <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">laporan data lengkap</Anchor>. Kami tidak mengirimkan postback data tingkat perangkat ke mitra terintegrasi.</li></ul> |
| Tingkat impresi melalui SDK | <ul><li>Tingkat impresi mengacu pada cara AppsFlyer menerima data. Data mungkin akan dilaporkan pada tingkat perincian lainnya (seperti tingkat perangkat).</li><li>Jaringan mediasi atau monetisasi melaporkan pendapatan menurut pengguna di tingkat impresi. Tidak semua jaringan mendukung perincian tingkat impresi.</li><li>Pendapatan ini dikaitkan dengan sumber media yang membawa pengguna. Artinya, atribusi pendapatan iklan AppsFlyer mematuhi aturan atribusi yang ditemukan di platform, termasuk aturan atribusi penargetan ulang.</li><li>Jika Anda menggunakan jaringan mediasi, pastikan untuk menonaktifkan integrasi pendapatan iklan untuk mitra monetisasi yang dimediasi melalui jaringan mediasi sebelum mengaktifkan integrasi pendapatan iklan dengan jaringan mediasi. Kegagalan untuk melakukannya mengakibatkan data duplikat.</li><li>Tingkat impresi melalui SDK memiliki keaktualan data terbaik dari semua jenis integrasi pendapatan iklan.</li><li>Mendukung SKAN.</li></ul> |
| Tingkat impresi (melalui SDK) dengan tingkat perangkat (melalui S2S API) | <ul><li>Mengizinkan data tingkat impresi yang diterima melalui SDK untuk diatribusikan dan dilaporkan pada Hari X, dan dialihkan dengan data tingkat perangkat yang diterima melalui API pada Hari 1 dan seterusnya. **Catatan**: Untuk Android, data yang dilaporkan melalui SDK dari perangkat yang tidak dikenal (tanpa ID perangkat yang tersedia) tidak digantikan oleh data yang masuk melalui API.</li><li>Mengaktifkan keaktualan data untuk akurasi. Artinya, Anda mendapatkan manfaat keaktualan data untuk Hari X dengan keakuratan data untuk Hari X+1 dan seterusnya.</li><li>Mendukung SKAN.</li></ul> |

</Accordion>

## Implementasi

Bagian berikut menjelaskan jenis atribusi pendapatan iklan yang tersedia, serta alur kerja dan langkah-langkah yang diperlukan untuk implementasi dan pemeliharaan.

<div id="connect-to-ad-revenue-integrated-partners" />

<Accordion title="Terhubung ke mitra terintegrasi pendapatan iklan">

**Sebelum Anda memulai**:

* Permintaan agar mitra terintegrasi pendapatan iklan memberikan kredensial API kepada Anda.

**Untuk mengaktifkan integrasi pendapatan iklan dengan jaringan pendapatan iklan**:

1. Di AppsFlyer, buka **ROI360** > **Pengaturan Pendapatan** > **Pendapatan iklan**.
2. Di Integrasi pendapatan iklan, klik **Integrasi pendapatan iklan baru**.
3. Pilih mitra pendapatan iklan dan klik **Berikutnya**.  
   ![ad_revenue_ui.png](https://files.readme.io/d91b886ed5b9715a508a481afbb86a7dd8381894322455214674ba68b483e91b-13751596101649.png)
4. Pilih jenis data pendapatan iklan yang ingin Anda terima. **Catatan**: Tidak semua jaringan iklan menyediakan semua opsi yang tercantum di bawah ini.
   * Pendapatan yang diatribusikan. Berarti pendapatan berdasarkan sumber akuisisi pengguna. Laporan pendapatan yang diatribusikan dapat berupa:
     * [Tingkat agregat](/docs/roi360-guide-ad-revenue-attribution#aggregate-granularity-using-app-open-or-inapp-events) melalui S2S API. 
       * Pilih event yang menjadi dasar pendapatan iklan. Misalnya, jika Anda memilih peristiwa af\_app\_opened, total pendapatan iklan dibagi antara semua event yang membuka aplikasi, yang memberi Anda pendapatan iklan per aplikasi yang terbuka.
     * Tingkat perangkat melalui S2S API.
       * **Catatan**: Jika Anda mengaktifkan API pendapatan iklan tingkat perangkat dari jaringan mediasi, Anda harus menonaktifkan integrasi pendapatan iklan dari jaringan monetisasi yang dimediasinya. Kegagalan untuk melakukannya mengakibatkan data duplikat.
     * Tingkat impresi melalui SDK.
     * Beritahu pengembang aplikasi Anda untuk mengintegrasikan konektor SDK pendapatan iklan AppsFlyer. Opsi tersedia untuk <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-2">iOS</Anchor>, dan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad_revenue_unity_connector">Unity</Anchor>.* Tingkat impresi (melalui SDK) dengan tingkat perangkat (melalui API S2S).
     * Beritahu pengembang aplikasi Anda untuk mengintegrasikan konektor SDK pendapatan iklan AppsFlyer. Opsi tersedia untuk <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-2">iOS</Anchor>, dan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad_revenue_unity_connector">Unity</Anchor>.* **Catatan** : Jika Anda menggunakan jaringan mediasi, pastikan untuk menonaktifkan integrasi pendapatan iklan untuk mitra monetisasi yang dimediasi melalui jaringan mediasi sebelum mengaktifkan integrasi pendapatan iklan dengan jaringan mediasi. Kegagalan untuk melakukannya mengakibatkan duplikat data.
5. Lengkapi kredensial API, atau masuk, seperti yang diminta oleh mitra terintegrasi. Ini tidak relevan untuk integrasi SDK.
6. Klik **Simpan**.
7. Jika muncul tombol Test Connection (Tes Koneksi) , seperti pada gambar di atas, klik **Test Connection (Tes Koneksi)** .
   * Jika kunci API memverifikasi tampilan, Anda telah berhasil menyelesaikan prosedur.
   * Jika muncul pesan lainnya, lihat [status dan pengujian API pendapatan iklan](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-api-status-and-testing) lalu ulangi prosedurnya.
8. Jika tidak ada tombolKoneksi Tes , Anda telah menyelesaikan prosedur.   
   AppsFlyer mengumpulkan data dari mitra beberapa kali per hari<Anchor target="_blank" href="/marketers/id/docs/about-data-freshness-and-timezone-support#ad-revenue">.</Anchor>
9. [Opsional] QA dan bandingkan data pendapatan iklan yang Anda lihat di AppsFlyer dengan data pendapatan iklan yang Anda lihat di dashboard mitra mediasi dan mitra UA. <Anchor target="_blank" href="/marketers/id/docs/compare-roi360-ad-revenue-data-with-partner-data">Pelajari lebih lanjut</Anchor>
10. [Opsional] Bagikan data pendapatan iklan dengan mitra Anda melalui <Anchor target="_blank" href="/marketers/id/docs/compare-roi360-ad-revenue-data-with-partner-data">sinyal UA</Anchor> dan [postback event pendapatan iklan](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks).

**Catatan**: Jika Anda mengubah dari satu jenis integrasi ke jenis lainnya, perubahan akan berlaku pada pukul 12.00 UTC di hari berikutnya.

</Accordion>

<div id="view-edit-and-delete-ad-revenue-integrated-partners" />

<Accordion title="Lihat, edit, dan hapus mitra terintegrasi pendapatan iklan">

![delete_edit_adi.png](https://support.appsflyer.com/hc/article_attachments/13751607197713)

**Untuk melihat, mengedit, atau menghapus integrasi jaringan pendapatan iklan**:

1. Di AppsFlyer, buka **ROI360** > **Pengaturan Pendapatan** > **Pendapatan iklan** dan pilih aplikasi Anda.  
   Daftar semua tampilan integrasi mitra Anda, beserta informasi tentang jenis produk dan integrasi, status integrasi, dan nama event pendapatan iklan.
2. Arahkan kursor ke integrasi dan klik **Edit** atau **Hapus** sesuai kebutuhan.

</Accordion>

<div id="deduplicate-cross-referenced" />

<Accordion title="Menghapus duplikat pendapatan iklan referensi silang">

Duplikasi sebagian dari data pendapatan iklan dapat terjadi jika aplikasi menggunakan dua <Anchor target="_blank" href="/marketers/id/docs/appsflyer-knowledge-base-glossary#platform-mediasi">platform mediasi</Anchor>, keduanya dikaitkan dengan <Anchor target="_blank" href="/marketers/id/docs/appsflyer-knowledge-base-glossary#jaringan-monetisasi">jaringan monetisasi</Anchor> yang sama. Dalam kasus tersebut, setiap platform mediasi melaporkan semua pendapatan iklan yang dihasilkan oleh jaringan monetisasi terkait, terlepas dari apakah pendapatan tersebut dihasilkan saat dimediasi oleh salah satu jaringan saja.

**Untuk menghindari duplikasi sebagian data pendapatan ketika dua platform mediasi saling melakukan referensi silang**:

1. Di AppsFlyer, buka **ROI360** > **Pengaturan Pendapatan** > **Pendapatan Iklan**.
2. Di **Pengaturan Umum**, klik **Hapus duplikat pendapatan iklan saat dua mitra mediasi saling melakukan referensi silang**. **Catatan**: Jangan hapus duplikat jika 2 platform mediasi memediasi format iklan yang berbeda. Misalnya, ketika platform 1 menampilkan Spanduk dan Interstisial, dan platform 2 menampilkan iklan AppOpen dan Native.

[![dedup.png](https://support.appsflyer.com/hc/article_attachments/17299804281361)](https://support.appsflyer.com/hc/article_attachments/17299804281361)

</Accordion>

<div id="aggregate-granularity-using-app-open-or-inapp-events" />

<Accordion title="Perincian gabungan menggunakan event terbuka aplikasi atau in-app event">

Perincian agregat untuk pendapatan iklan berfungsi sebagai berikut:

* Jaringan terintegrasi melaporkan total pendapatan per hari yang dikelompokkan berdasarkan lokasi.
* AppsFlyer memperoleh pendapatan efektif per tindakan/ effective revenue per action (eRPA) dengan membagi pendapatan iklan dengan jumlah terjadinya event pemicu.
* AppsFlyer membuat acara yang dimonetisasi, yang menyertakan total eRPA untuk setiap perangkat yang diatribusikan. Misalnya, ad\_matched\_monetized.
* Menggunakan eRPA, pendapatan diatribusikan ke sumber media.
* Anda dapat menggunakan salah satu dari jenis event berikut ini:
  * **Monetisasi unik dari in-app event** memerlukan modifikasi pada aplikasi.
  * event ***af\_app\_opened*** yang tersedia secara default,
* Jangan laporkan jumlah pendapatan iklan dalam in-app event secara paralel dengan integrasi pendapatan iklan. Hal itu menyebabkan pendapatan iklan terduplikasi di dashboard karena AppsFlyer mendapatkan data pendapatan dari jaringan monetisasi melalui integrasi.

#### Gabungkan pendapatan iklan menggunakan event

| Metode event | Cara implementasi | Pertimbangan |
| --- | --- | --- |
| Monetisasi unik dari in-app event | <ul><li>In-app event diatur pada saat iklan ditampilkan</li><li>Ini memberikan jumlah tindakan pengguna yang berbeda yang memungkinkan perhitungan eRPA yang unggul</li><li>Ini dapat disempurnakan lebih lanjut dengan memiliki in-app event yang berbeda untuk setiap jaringan monetisasi, sehingga memungkinkan Anda untuk membagi pendapatan dengan jaringan monetisasi<br />Lihat tabel berikut untuk pembahasan lengkapnya.</li></ul> | <ul><li>Mengharuskan pengembang untuk memodifikasi aplikasi</li><li>Pendapatan dapat diperinci berdasarkan jaringan monetisasi di Dashboard</li></ul> |
| af\_app\_opened event | <ul><li>Event af\_app\_opened dikirim oleh SDK Appsflyer secara default</li><li>Ini dipicu oleh setiap sesi pengguna</li></ul> | <ul><li>Tidak diperlukan modifikasi aplikasi</li><li>Cepat diimplementasikan</li><li>Nilai eRPA terdistorsi secara signifikan kecuali jika Anda hanya menampilkan satu aplikasi per sesi</li><li>Tidak ada perincian pendapatan berdasarkan jaringan monetisasi</li><li>Acara terkait dengan semua pengguna yang meluncurkan aplikasi dan Anda tidak memiliki indikasi kesediaan pengguna untuk menonton iklan</li></ul> |

#### Perbandingan metode in-app event

| Metode | Pro | Kontra | Pertimbangan |
| --- | --- | --- | --- |
| Gunakan event yang sama untuk semua jaringan. Misalnya, ad\_watched. Ini secara otomatis menghasilkan event ad\_watched\_monetized yang berisi detail monetisasi | Paling sederhana untuk diimplementasikan | Tidak ada informasi berkualitas, seperti jumlah klik dan pendapatan iklan per jaringan | <ul><li>Paling cocok jika tujuan utamanya adalah mencari sumber/kampanye yang membuat pengguna dengan kecenderungan terbesar untuk mengeklik iklan.</li><li>Itu tidak cocok untuk membandingkan kinerja jaringan monetisasi.</li></ul> |
| **(praktik terbaik)** Setiap jaringan dialokasikan event unik untuk menonton iklan. Contoh:  ad\_watch\_admob,<br /><br />iklan\_watch\_vungle. | Visibilitas penuh dan kemampuan untuk membandingkan jaringan yang dimonetisasi di dashboard selain data lengkap. | Pendapatan iklan tidak terakumulasi dalam satu event. Jumlah event setara dengan jumlah jaringan | Memungkinkan perbandingan jaringan yang dimonetisasi di dashboard. Pendapatan iklan dipisahkan berdasarkan jaringan menggunakan in-app event per jaringan. |

</Accordion>

<div id="ad-revenue-api-status-and-testing" />

<Accordion title="Status dan pengujian API pendapatan iklan">

* Status operasional integrasi pendapatan iklan tersedia sebagai berikut:

  * <Anchor target="_blank" href="/marketers/id/docs/dashboard-cost-and-ad-revenue-status">Dashboard status integrasi biaya dan pendapatan iklan</Anchor>: Daftar mitra terpusat yang integrasi pendapatan iklannya diaktifkan untuk satu atau beberapa aplikasi yang ada di akun Anda.
  * Beberapa mitra memungkinkan Anda menguji koneksi API. Jika tersedia, tombol  **Test connection (Tes Koneksi)** ditampilkan. <Image alt="mceclip0.png" src="https://support.appsflyer.com/hc/article_attachments/360006975517" width="104px" />
  * Untuk memverifikasi bahwa koneksi API beroperasi:
  * Klik  **Test connection (Tes koneksi).** Pesan **kode API terverifikasi ditampilkan.** Jika tidak demikian, ikuti panduan tindakan korektif dalam tabel berikut.

| Status | Artinya | Keterangan/diperlukan tindakan |
| --- | --- | --- |
| Kunci API diverifikasi | <ul><li>Sambungan aktif dan dapat menarik data.</li><li><Anchor target="_blank" href="/marketers/id/docs/about-data-freshness-and-timezone-support#ad-revenue">Data ditarik sekali sehari.</Anchor></li></ul> | Tidak ada |
| Kredensial tidak valid | Satu atau lebih kredensial yang diberikan salah. | Dapatkan kredensial yang benar dari mitra pendapatan iklan |
| Detail konfigurasi tidak ada | Satu atau beberapa bidang kredensial tidak lengkap | Ambil kredensial di dashboard mitra pendapatan iklan atau hubungi partner dan minta kredensial. |

</Accordion>

## Data pendapatan iklan

Data pendapatan iklan tersedia melalui dashboard AppsFlyer dan laporan data lengkap.

<div id="ad-revenue-aggregate-data" />

<Accordion title="Data agregat pendapatan iklan">

Pendapatan iklan menunjukkan kualitas pengguna dari berbagai sumber dari waktu ke waktu. Saat pengguna terus meluncurkan aplikasi dan berinteraksi dengan iklan, LTV mereka meningkat.

**Catatan**: Mungkin ada perbedaan antara data pendapatan iklan di berbagai dashboard dan laporan. [Pelajari lebih lanjut](#is-there-discrepency).

Atribusi pendapatan iklan tersedia sebagai berikut:

* Berbasis LTV:
  * Dashboard menjadi: Ikhtisar, event
  * Laporan LTV
  * Dashboard dan laporan kelompok
  * Master API
* Berbasis aktivitas:
  * Dashboard: Aktivitas
  * Data lengkap pendapatan iklan

#### **Dashboard ikhtisar - laporan kinerja gabungan**

[![](https://support.appsflyer.com/hc/article_attachments/360002239229)](https://support.appsflyer.com/hc/article_attachments/360002239229)

Di dashboard Ikhtisar:

* Nilai, termasuk pendapatan, adalah LTV. Lihat <Anchor target="_blank" href="/marketers/id/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV vs. data aktivitas</Anchor>.
* Kolom ***Revenue (Pendapatan)*** mencakup semua pendapatan, termasuk pendapatan iklan dan pembelian in-app.
* Telusuri hierarki periklanan (sumber media, kampanye, set iklan, geo) untuk melihat **event yang dimonetisasi** dalam laporan.

**Dashboard event**[![](https://support.appsflyer.com/hc/article_attachments/360002218905)](https://support.appsflyer.com/hc/article_attachments/360002218905)

Di dashboard Aktivitas:

* Nilai termasuk pendapatan didasarkan pada tanggal aktivitas. Lihat  <Anchor target="_blank" href="/marketers/id/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV vs. data aktivitas</Anchor> .
* Tindakan **Rata-rata per Pengguna** menunjukkan kecenderungan pengguna untuk berinteraksi dengan iklan yang disajikan dalam aplikasi.

> 📄 **Contoh**
>
> Tiga pengguna memasang aplikasi pada 31 Desember 2017. Mereka dikaitkan sebagai berikut:
>
> * Pengguna A: Jaringan A
> * Pengguna B: Jaringan B
> * Pengguna C: Organik
>
> Aplikasi ini terintegrasi dengan lima platform monetisasi yang berbeda. Setiap platform menggunakan in-app event unik menggunakan AppsFlyer SDK sebagai berikut:
>
> * Jaringan Audiens Meta: fb\_ad\_view
> * Chartboost: chartboost\_ad\_view
> * Admob: admob\_ad\_view
> * Applovin: applovin\_ad\_view
> * IronSource: is\_ad\_view
>
> Setelah penginstalan selama empat hari, pengguna diperlihatkan iklan sebagai berikut:
>
>
>
> | User | Jaringan UA | fb\_  <br />ad\_view | chartboost\_  <br />ad\_view | admob\_  <br />ad\_view | applovin\_  <br />ad\_view | is\_ad\_view | Total |
> | --- | --- | --- | --- | --- | --- | --- | --- |
> | A | Jaringan A<br /><br />31-12-2017 | 01-01-2018<br /><br />$1 | 02-01-2018<br /><br />$1 | 03-01-2018<br /><br />$1 | 04-01-2018<br /><br />$1 |  | $4 |
> | B | Jaringan B<br /><br />31-12-2017 | 02-01-2018<br /><br />$1 |  | 04-01-2018<br /><br />$1 |  |  | $2 |
> | C | Organik<br /><br />31-12-2017 | 01-01-2018<br /><br />$1 |  |  |  | 02-01-2018<br /><br />$1 | $2 |
>
>
>
> Melihat datanya, sekarang kita dapat meringkas pendapatan yang dikumpulkan per pengguna, per hari (dan per in-app event):
>
>
>
> | User | 01-01-2018 | 02-01-2018 | 03-01-2018 | 04-01-2018 | Total LTV |
> | --- | --- | --- | --- | --- | --- |
> | A | $1 | $1 | $1 | $1 | $4 |
> | B |  | $1 |  | $1 | $2 |
> | C | $1 | $1 |  |  | $2 |
> | Total | $2 | $3 | $1 | $2 | $8 |
>
>
>
> **Memahami Laporan:**
>
> Seperti yang disebutkan, pendapatan iklan terkait dengan LTV pengguna. Oleh karena itu, jangka waktu yang Anda pilih di Dashboard menunjukkan kelompok penginstalan yang pendapatannya digabungkan hingga waktu dan hari saat ini. Mari kita periksa laporan dengan dua pilihan tanggal yang berbeda:
>
> Laporan Agregat : Tanggal Terpilih: 31-12-2017-05-01-2018
>
>
>
> | Jaringan | Pendapatan LTV |
> | --- | --- |
> | Organik | $2 |
> | Jaringan A | $4 |
> | Jaringan B | $2 |
> | Jaringan C | $2 |
>
>
>
> Dalam hal ini, kelompoknya adalah pengguna yang menginstal aplikasi dari 31-12-2017 hingga hari ini, 05-01-2018. Semua pendapatan yang dihasilkan oleh pengguna tersebut terikat kembali ke sumber perolehan dan diwakilkan oleh LTV pengguna.

</Accordion>

<div id="ad-revenue-raw-data" />

<Accordion title="Data lengkap pendapatan iklan">

<Image alt="PremiumFeature.jpg" src="https://files.readme.io/674e5d0c9efde9d12008bd705b3ba95f04e133fec3f39d4278612675123d4de4-360007173877.jpg" width="78px" />

Laporan data lengkap pendapatan iklan berisi data yang disediakan oleh jaringan monetisasi yang memiliki integrasi tingkat perangkat atau tingkat impresi dengan AppsFlyer.

**Prinsip data lengkap pendapatan iklan**

* Data digabungkan menurut jumlah tayangan unik per pengguna. Tayangan unik berasal dari kombinasi jaringan monetisasi iklan, unit iklan, dan penempatan.
* Data lengkap tingkat impresi adalah:
  * Digabungkan ke tingkat perangkat dan tersedia dalam laporan tingkat perangkat.
  * Tersedia seperti dalam laporan tingkat impresi di Data Locker.
  * [Keaktualan data lengkap](/docs/roi360-guide-ad-revenue-attribution#data-freshness) identik dengan pendapatan iklan tingkat perangkat di dashboard Aktivitas.

<table><tbody><tr><th>Laporan</th><th><p>Halaman ekspor data</p></th><th>Pull API </th><th>Data Locker</th></tr><tr><td>Pendapatan iklan yang diatribusikan (non-organik)</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Pendapatan iklan organik</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Penargetan ulang pendapatan iklan </td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Data lengkap tingkat impresi </td><td><span>-</span></td><td><span>-</span></td><td><span>✓ </span></td></tr><tr><td colspan="4">\* Laporan berversi juga tersedia, diperbarui beberapa kali per hari, dengan data yang dikumpulkan di tingkat perangkat. Laporan Data Locker tidak berversi tersedia setiap hari.</td></tr></tbody></table>

**Karakteristik dan bidang data**

Bidang dalam laporan pendapatan iklan diisi:

* Berdasarkan event pendapatan iklan itu sendiri dan tercantum dalam tabel berikut. Bidang-bidang ini dibagi menjadi:
  * **Spesifik:** Bidang khusus untuk pendapatan iklan. Misalnya tayangan dan penempatan. **Catatan**! Kolom yang diisi berbeda menurut mitra monetisasi, seperti yang ditampilkan di tabel Bidang menurut tabel jaringan di bagian ini.
  * **Konteks:** Bidang yang memiliki arti serupa dalam laporan data lengkap lainnya. Misalnya, nama acara, nilai acara, mata uang.
* Sebagai hasil dari mengatribusikan event tersebut ke sumber media yang menghadirkan pengguna. Artinya bidang ini disalin dari event konversi yang membawa pengguna. Misalnya, sumber media dan kampanye. Bidang ini tidak tercantum dalam tabel berikut.

#### Bidang yang diisi oleh pendapatan iklan

| api\_name | Nama kolom | Jenis kolom | Deskripsi |
| --- | --- | --- | --- |
| event\_time | Event Time | Context | Tanggal pendapatan diatribusikan ke |
| event\_name | eventName | Context | <ul><li>Default disetel ke af\_ad\_revenue</li><li>Bisa juga event custom</li></ul> |
| event\_revenue | Mata Uang Pendapatan Event | Context | <ul><li>Jumlah pendapatan menggunakan mata uang pendapatanevent</li><li>Nilai nol menunjukkan tayangan tanpa pendapatan</li></ul> |
| event\_revenue\_currency | Mata Uang Event | Context | Mata uang pendapatan event |
| event\_revenue\_XXX | Pendapatan Event XXX | Context | <ul><li>Di halaman ekspor: Pendapatan dikonversikan ke mata uang khusus aplikasi</li><li>Di Data Locker selalu USD</li><li>Di Pull API menurut mata uang Pull.</li></ul> |
| country | Negara | Context | Instal negara tempat konversi penginstalan |
| ad\_unit | Ad unit | Spesifik | Jenis iklan |
| segmen | Segmen | Spesifik | Nama penempatan iklan |
| monetization\_network | Jaringan Monetisasi | Spesifik | Jaringan mengirimkan iklan |
| Tayangan | Tayangan | Spesifik | Berapa kali pengguna melihat iklan |
| mediation\_network | Jaringan Mediasi | Spesifik | Jaringan mediasi melaporkan event tersebut ke AppsFlyer |

#### Bidang berdasarkan jaringan

<table><tbody><tr><th>Nama tampilan</th><th>Admob</th><th>ironSource</th><th>AppLovin MAX</th><th>Appodeal</th><th>Fyber</th></tr><tr><td>Unit iklan</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Segmen</td><td>-</td><td>(1)</td><td>-</td><td>-</td><td>-</td></tr><tr><td>Penempatan</td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Jaringan Monetisasi</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Tayangan </td><td><span>-</span></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td>Jaringan Mediasi</td><td><span>-</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td colspan="6">(1) Pemasang iklan perlu mengkonfigurasi ini di ironSource</td></tr></tbody></table>

[Laporan sampel data lengkap pendapatan iklan](https://docs.google.com/spreadsheets/d/e/2PACX-1vRm_1tevWFdzdj6JgdxYawLBtYAJj-ubDeY4g1QfbdSkd2-Adi18oemPMdd7m7cM2e3fzm7VH0w6lhD/pub?output=xlsx)

</Accordion>

<div id="data-freshness" />

<Accordion title="Kesegaran data">

Keaktualan data bergantung pada jenis integrasi dan metode pelaporan. 

Untuk integrasi API S2S, waktu paling awal untuk tanggal tersedia adalah:

* Dashboard dan laporan (melalui Data Locker) mulai Hari X+1, pukul 08.00 UTC, kira-kira 4 kali sehari, setiap 6 jam. Dan Untuk pelanggan ROI360, Hari 2, 3, 7, dan 14, sekali per hari.

Untuk integrasi SDK tingkat impresi, waktu paling awal data tersedia adalah:

* Dashboard dan laporan (melalui Data Locker) skenario kasus terbaik, mulai Hari X dari pukul 05.00 UTC, diperbarui kira-kira 6 kali per hari, setiap 4 jam.
* Laporan data lengkap tingkat impresi (melalui Data Locker) pada Hari X mulai pukul 01.00 UTC, diperbarui setiap jam.

Untuk tingkat tayangan (melalui SDK) dengan tingkat perangkat (melalui S2S API), Anda mendapatkan keaktualan data untuk Hari X dengan akurasi data untuk Hari X+1, sebagai berikut:

* Untuk data tingkat impresi yang tiba melalui SDK:
  * Dashboard dan laporan (melalui Data Locker) skenario kasus terbaik, mulai Hari X dari pukul 05.00 UTC, diperbarui kira-kira 6 kali per hari, setiap 4 jam.
  * Laporan data lengkap tingkat impresi (melalui Data Locker) pada Hari X mulai pukul 01.00 UTC, diperbarui setiap jam.
* Untuk data tingkat perangkat yang tiba melalui S2S API:
  * Dashboard dan laporan (melalui Data Locker) mulai Hari X+1, pukul 08.00 UTC, kira-kira 4 kali sehari, setiap 6 jam. Dan Untuk pelanggan ROI360, Hari 2, 3, 7, dan 14, sekali per hari.

Untuk integrasi lama (pra-ROI360), keaktualan data paling cepat adalah Hari X+1, pukul 17.00 UTC.

**Catatan:** Saat mengubah jenis integrasi, data yang diterima melalui jenis integrasi sebelumnya untuk tanggal yang lalu tidak akan diisi ulang oleh jenis integrasi yang baru.  Misalnya, jika pada hari X jenis integrasi diubah dari SDK ke S2S, data akan ditarik dari hari X+1 dan seterusnya dan tidak ditarik untuk hari sebelum hari X.

<div id="ad-revenue-data-locker-reports" />

<Accordion title="Laporan Data Locker Pendapatan Iklan">

| Nama | Keaktualan | Bagian Laporan |
| --- | --- | --- |
| ***Pendapatan Iklan Harian (digabungkan pada tingkat perangkat)*** | Pendapatan iklan untuk hari tertentu (hari X) dilaporkan pada hari berikutnya (X+1), pukul 20.00 UTC.<br /><br />Misalnya, Pendapatan iklan dari tanggal 1 Mei akan dilaporkan pada tanggal 2 Mei. | Laporan tersebut mencakup bagian AdRevenue yang Dikaitkan, Organik, dan Penargetan Ulang. |
| ***Laporan Pendapatan Iklan Harian Berversi*** ***(digabungkan pada tingkat perangkat)*** | Laporan harian terdiri dari:<ul><li>Versi harian dibuat setiap 4 jam selama hari pendapatan (hari X). Data harian dikumpulkan oleh konektor SDK ROI.</li><li>Versi sehari penuh dibuat pada hari ke-2,3,7, dan 13, berdasarkan data yang berasal dari laporan S2S API.</li></ul>Dengan kata lain, kumpulan versi laporan harian menyertakan versi berikut:<ul><li>00:00 — 04.00 pada hari X.</li><li>00.00 — 08.00 pada hari X [konektor SDK ROI]</li><li>00:00 — 12.00 pada hari X [konektor SDK ROI]</li></ul>…* 00.00 — 24.00 pada hari X [konektor SDK ROI]<ul><li>00.00 — 24.00 pada hari x+1 [S2S]</li><li>00.00 — 24.00 pada hari x+2 [S2S]</li><li>00.00 — 24.00 pada hari x+6 [S2S]</li><li>00.00 s/d 24.00 pada hari x+13 [S2S]</li></ul> | Setiap versi laporan menyertakan bagian Pendapatan Iklan yang Diatribusikan, Organik, dan Ditargetkan Ulang. |
| ***Laporan Pendapatan Iklan tingkat impresi (tingkat impresi)*** | Catatan pendapatan iklan tingkat impresi ditulis ke file terpisah setiap jam. |  |

</Accordion>

</Accordion>

## Informasi Tambahan

<div id="migrating-from-aggregate-to-userlevel-granularity" />

<Accordion title="Bermigrasi dari perincian agregat ke tingkat perangkat">

* Migrasi tidak memengaruhi data pendapatan iklan historis. Data ini tetap tidak berubah.
* Data pendapatan iklan ditarik sekali sehari pada pukul 14.00 UTC menggunakan opsi perincian yang dipilih pada waktu itu.
* Perincian tingkat perangkat tidak mewajibkan Anda untuk mendefinisikan in-app event (seperti yang Anda lakukan untuk pelaporan tingkat gabungan). Anda dapat terus mengirimkan event ini, tetapi event ini tidak memengaruhi pelaporan perincian tingkat perangkat di AppsFlyer.

</Accordion>

<div id="closed-beta--ua-signals-for-ad-networks" />

<Accordion title="Sinyal UA untuk jaringan iklan">

Anda mungkin ingin bekerja dengan jaringan iklan yang dapat menerima sinyal UA. Ini artinya jaringan iklan yang bertanggung jawab atas akuisisi pengguna dapat menerima data dari jaringan mediasi terkait pendapatan iklan dan menggunakannya untuk mengoptimalkan kampanye UA pelanggan mereka.

Untuk memberikan sinyal ke jaringan iklan UA, mitra mediasi harus memiliki integrasi tingkat impresi atau tingkat perangkat.

* Untuk mempelajari apa yang perlu dilakukan **mitra** untuk menerima laporan, lihat <Anchor target="_blank" href="/partners/id/docs/ad-revenue-signals-for-ua-ad-networks#enable-the-ad-revenue-report">di sini</Anchor>.
* Untuk mempelajari apa yang perlu dilakukan **pemasang iklan** untuk memberikan izin kepada mitra atas laporan tersebut, lihat [di sini.](#permission-to-get-ad-revenue-data)

**Daftar mitra mediasi yang dapat mengirimkan sinyal UA ke jaringan iklan UA:**

* Applovin Max
* Google AdMob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* Mediasi Unity LevelPlay (dahulu ironSource)
* Admost
* Tradplusad
* Yandex

**Daftar jaringan iklan UA yang dapat menerima sinyal UA:**

* AdAction
* Adamobi
* Adjoe
* Adonco
* Adshow
* Appier
* Apprainbow
* Aura dari Unity
* Betop
* Bidswave
* Brandscale
* Chameleostudios
* Chartboost
* Datawave
* DLab
* Ecomonline
* Etusdigital
* Foregon
* GNA Company
* Happimobi
* Hybrid
* Inflecto
* Irismedia
* Lambadapp
* Leadidadmonster
* Lifestreet
* Liftoff
* Melodong
* Mintegral
* Mobrand
* Moloco
* Motive
* Mpnd
* Msla
* Muvmobile
* Nexamob
* Nftdroper
* Nsofmedia
* Performadlive
* Personalyrtb
* Pitatroas
* Rebornads
* RTBhouse
* Runfuns
* Scmobi
* Shalltry
* Shareit
* Smadex
* Tapjoy
* Targetmedia
* Thepurpleline
* TikTok untuk Bisnis
* Trademob
* Truemoney
* Unity Ads
* Yandex
* Yeahmobi
* Z2A Digital
* Zoyo

</Accordion>

<div id="permission-to-get-ad-revenue-data" />

<Accordion title="Izinkan jaringan iklan untuk mendapatkan data lengkap pendapatan iklan">

Sebelum jaringan iklan yang bertanggung jawab atas akuisisi pengguna dapat menerima data dari jaringan mediasi, mereka harus mendapatkan izin Anda.

**Prasyarat**:

* Langganan ROI360 Lanjutan diperlukan.
* hubungi jaringan iklan untuk mengonfirmasi bahwa jaringan tersebut memiliki alur penyerapan dan logika pengoptimalan untuk memproses data Anda.

**Untuk mengizinkan jaringan iklan mendapatkan data pendapatan iklan:**

1. Buka **Konfigurasi** > **Integrasi aktif**.
2. Pilih mitra terintegrasi.
3. Buka **tab Integrasi**.
4. Verifikasi bahwa **Aktifkan Mitra** aktif. Jika tidak, data tidak akan dibagikan.
5. Buka tab **Izin**.
6. Hidupkan **Izin jaringan iklan**.
7. Aktifkan **Akses data lengkap pendapatan iklan**.
8. Pada **opsi Pengiriman**, pilih apakah akan mengirimkan data untuk pendapatan iklan hanya dari mitra ini (**Hanya mitra ini**), atau untuk pendapatan iklan dari semua sumber media (**Semua sumber media, termasuk organik**).
9. Klik **Simpan Pengaturan**.
10. Hubungi jaringan iklan untuk memberi tahu bahwa Anda telah memberikan izin.
11. Pastikan <Anchor target="_blank" href="/partners/id/docs/ad-revenue-signals-for-ua-ad-networks#enable-the-ad-revenue-report">jaringan iklan mengaktifkan laporan di Data Locker mereka dan mengonfigurasi pengaturan keluarannya</Anchor>

</Accordion>

<div id="ad-revenue-event-postbacks-for-ad-networks" />

<Accordion title="Postback event pendapatan iklan untuk jaringan iklan">

Anda dapat mengonfigurasi postback pendapatan iklan untuk jaringan iklan. Artinya, jaringan iklan yang bertanggung jawab atas akuisisi pengguna dapat menerima data waktu aktual dari jaringan mediasi mengenai pendapatan iklan dan menggunakannya untuk mengoptimalkan kampanye UA pelanggannya. 

Untuk mengirimkan postback ke jaringan iklan UA, Anda harus memiliki integrasi tingkat impresi melalui SDK dengan jaringan mediasi. AppsFlyer secara otomatis menghasilkan event af\_ad\_revenue per impresi. Event ini dapat dipilih dari daftar event yang akan dikirim melalui <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration">postback in-app event</Anchor> ke jaringan iklan UA.

> 🚧 **Penting!**
>
> Meskipun Anda dapat mengirimkan postback pendapatan iklan ke mitra tertentu, Anda harus memastikan untuk memvalidasi cara mitra menggunakan data sebelum memulai integrasi.

**Untuk menyiapkan postback event pendapatan iklan**:

1. Cari dan pilih mitra Anda, baik <Anchor target="_blank" href="/marketers/id/docs/partner-integrations#manage-existing-integrations">dari pasar</Anchor> atau dari halaman**Konfigurasi** > **Integrasi**Aktif.
2. Di tab **Integrasi** , gulir ke bawah dan aktifkan **Postback in-app event**.
3. Pilih event AppsFlyer af\_ad\_revenue.
4. Petakan ke event jaringan iklan UA sebagai berikut:

| Jaringan iklan UA | event untuk memetakan af\_ad\_revenue ke | Tangkapan layar |
| --- | --- | --- |
| ironSource | adRevenue | [![](https://files.readme.io/fd902115e177e02ad96e20f2e0a81bbebbc324f5cc02b7e504e26ddd4f840897-17566964074257.png)](https://files.readme.io/fd902115e177e02ad96e20f2e0a81bbebbc324f5cc02b7e504e26ddd4f840897-17566964074257.png) |
| Unity Ads | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Moloco | Tidak perlu pemetaan |  |
| Mintegral | Tidak perlu pemetaan |  |
| Smadex | Tidak perlu pemetaan |  |
| Meta Ads | fb\_mobile\_purchase | [![](https://files.readme.io/fa62ae03002f9989482f8cb2b2d1628529110dbb8d17041d6ad865e381ee0361-17566964080145.png)](https://files.readme.io/fa62ae03002f9989482f8cb2b2d1628529110dbb8d17041d6ad865e381ee0361-17566964080145.png) |
| TikTok untuk Bisnis - SRN Lanjutan | ImpressionLevelAdRevenue | [![](https://files.readme.io/8beed93895ac3e9d52049bea06b89388e8f32ca12d404c3461a3dcc493aed26f-24100803659665.png)](https://files.readme.io/8beed93895ac3e9d52049bea06b89388e8f32ca12d404c3461a3dcc493aed26f-24100803659665.png) |
| Aura dari Unity | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |

5. Klik **Simpan integrasi**.

**Daftar mitra mediasi yang dapat mengirimkan event pendapatan iklan tingkat impresi ke jaringan iklan UA:**

* Applovin Max
* Google AdMob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* ironSource
* Admost
* Tradplusad
* Yandex

**Daftar jaringan iklan UA yang dapat menerima postback event pendapatan iklan:**

* ironSource
* Unity Ads
* Moloco
* Mintegral
* Meta Ads
* Smadex
* TikTok untuk Bisnis - SRN Lanjutan

</Accordion>

<div id="faq" />

<Accordion title="Pertanyaan Umum">

<span id="01ECF1PZ38DM24YCZPVH104FP4"></span>| **Bagaimana saya bisa mendapatkan total pendapatan iklan dari setiap platform?**<ul><li>Atribusi pendapatan iklan ditautkan dan ditampilkan terkait dengan sumber akuisisi pengguna.</li><li>Ini memberikan tampilan LTV dari ROI dan KPI Anda.</li><li>Untuk melihat total pendapatan dari setiap platform monetisasi [, gunakan in-app event yang berbeda untuk setiap jaringan](/docs/roi360-guide-ad-revenue-attribution#aggregate-granularity-using-app-open-or-inapp-events) dan gunakan prosedur berikut:<ol><li>Di dasbor Ikhtisar, buka **tabel laporan kinerja gabungan.**</li><li>Pilih hingga empat  event yang dimonetisasi yang mewakili platform yang ingin Anda kueri.</li></ol></li></ul>![selecting_monetized_events.png](https://support.appsflyer.com/hc/article_attachments/360002218865)<ol><li>Unduh laporan dengan, klik **Ekspor CSV.**</li><li>Ringkas **kolom Pendapatan** dari acara monetisasi platform yang diminta</li></ol>![revenue_sum_up.png](https://support.appsflyer.com/hc/article_attachments/360002218885)<br /><br />Catatan: Total pendapatan iklan ini adalah data LTV, artinya ini adalah seluruh pendapatan yang dihasilkan oleh jaringan yang memonetisasi aplikasi Anda dari pengguna yang menginstal selama rentang tanggal yang ditentukan. |
| --- |
| **Apakah pendapatan iklan tersedia di halaman aktivitas?**<br /><br />Ya. Halaman Aktivitas melaporkan pendapatan gabungan dari pembelian in-app dan pendapatan iklan. **Catatan** : Data pendapatan iklan dikirim ke AppsFlyer setiap hari, sehari setelah event. |
<span id="01ECF1PZ39C7CG3R7H9P64QF51"></span>| **Apakah saya perlu mengaktifkan mitra di tab Integrasi?**<br /><br />Jika Anda berinteraksi dengan mitra hanya untuk monetisasi iklan (pendapatan iklan): jangan aktifkan **Aktifkan Mitra** di tab integrasi. Aktifkan hanya  **Dapatkan data Pendapatan Iklan** di tab Pendapatan Iklan. |
<span id="01ECF1PZ39KCKY2BC3ZGK3CA0V"></span>| **Bagaimana pendapatan iklan tingkat perangkat diatribusikan jika pengguna memiliki versi aplikasi tanpa SDK AppsFlyer?**<br /><br />Pendapatan iklan diatribusikan sebagai organik. |
<span id="is-there-discrepency"></span>| **Apakah ada perbedaan antara data pendapatan iklan di berbagai dasbor dan laporan?**<br /><br />Mungkin ada perbedaan antara data pendapatan iklan di dasbor Ikhtisar dan laporan data lengkap, serta di dasbor Aktivitas atau Kelompok. Hal ini karena:<ul><li>Data pendapatan iklan di dasbor Kelompok dan Aktivitas, serta data melalui API Master dan API Kelompok diperbarui secara retroaktif; di dasbor Ikhtisar, dan melalui ekspor data lengkap dan Pull API, tidak.</li><li>Data terkadang ditampilkan di dasbor Aktivitas dan Kelompok sebelum dasbor Ikhtisar.</li><li>dasbor menyertakan event yang ditandai sebagai `af_ad_revenue` dan `_monetized`, sedangkan data lengkap hanya mencakup event `af_ad_revenue` .</li></ul> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Sifat | Catatan |
| --- | --- |
| Batasan | Event pendapatan iklan tidak tersedia untuk:<ul><li>Push API</li><li>Dashboard penargetan ulang</li></ul>Batasan perincian tingkat perangkat:<ul><li>Event af\_ad\_revenue tidak tersedia untuk kelompok di Pivot dan Master API.</li><li>Event ini tersedia di analitik Kelompok.</li><li><Anchor target="_blank" href="/marketers/id/docs/applovin-max-ad-revenue-configuration#best-practice">Perbedaan dapat terjadi saat menerapkan pendapatan tawaran **dalam aplikasi** Meta ads.</Anchor></li></ul>Penghitungan jumlah pengguna unik yang memicu peristiwa af\_ad\_revenue tidak didukung di dasbor AppsFlyer. |
| Akses jaringan iklan | Tidak dapat mengakses laporan Kohort |
| Akses agensi | Agensi:<ul><li>Tidak dapat mengakses konfigurasi pendapatan iklan.</li><li>Dapat melihat semua dashboard dan data terkait.</li></ul> |
| Transparansi agensi | Tidak didukung |
| zona waktu | Pendapatan iklan ditampilkan di dasbor AppsFlyer dan laporan hanya dalam zona waktu UTC. Artinya, jika data dilaporkan pada pukul 14.00 UTC+2, di AppsFlyer akan ditampilkan sebagai pukul 14.00 UTC. diproses setiap hari.<br /><br />Ini karena AppsFlyer perlu menormalkan data yang dikumpulkan dari berbagai sumber dan mitra, yang sebagian besar melaporkan datanya dalam UTC. |
| Mata uang | Di AppsFlyer:<ul><li>Dashboard menampilkan mata uang khusus aplikasi pengiklan.</li><li>Laporan data lengkap menampilkan mata uang awal dan juga mengonversikannya ke mata uang khusus aplikasi pengiklan.</li></ul> |
| Jenis data | Data organik dan non-organik didukung |
| Kesegaran data | [Pendapatan Iklan](/docs/roi360-guide-ad-revenue-attribution#data-freshness) |
| Data historis/retroaktif | <ul><li>Data diambil dan tersedia sejak hari dilakukannya integrasi. Ini berarti data historis tidak tersedia sebelum tanggal integrasi (hari 0).</li><li>Data pendapatan iklan yang diterima melalui S2S API untuk hari tertentu diperbarui pada hari 1, 2, dan 3.</li><li>Data pendapatan iklan di dasbor Kelompok dan Aktivitas, serta data melalui API Master dan API Kelompok diperbarui secara retroaktif; di dasbor Ikhtisar, dan melalui ekspor data lengkap dan Pull API, tidak. Jika Anda memiliki paket pendapatan lanjutan, data juga diperbarui di Data Locker.</li></ul> |
| Akses pengguna akun | Didukung |
| SKAN | Didukung oleh konektor SDK pendapatan iklan tingkat impresi. |
| Geo/negara | Di dasbor Kelompok, saat geo tidak diketahui (T/A), data T/A tidak ditampilkan saat digabungkan menurut geo. |
| Postback in-app event | Postback ke mitra adalah untuk data yang berkaitan dengan in-app event yang diatribusikan ke mitra tersebut; mereka tidak menyertakan data yang berkaitan dengan sumber media lain. |
| Aplikasi CTV, PC, dan konsol | Tidak didukung. Hanya aplikasi Android dan iOS yang didukung. |

</Accordion>

<div id="list-of-ad-revenue-integrated-partners" />

<Accordion title="Daftar Mitra terintegrasi pendapatan iklan">

| Partner | Parameter kredensial diperlukan | Perincian data |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/id/docs/adcolony-campaign-configuration">AdColony</Anchor> | <ul><li>Kunci API</li><li>ID Aplikasi</li></ul> | Gabungkan tingkat dengan geo |
| Admost | <ul><li>ID aplikasi jaringan</li><li>Token</li></ul> | Tingkat perangkat dengan geo |
| <Anchor target="_blank" href="/marketers/id/docs/applovin-campaign-configuration">AppLovin</Anchor> | <ul><li>Kunci Laporan</li><li>Nama Paket Aplikasi</li></ul> | Gabungkan tingkat dengan geo |
| <Anchor target="_blank" href="/marketers/id/docs/applovin-max-ad-revenue-configuration">AppLovin MAX</Anchor> | <ul><li>Kunci Laporan</li><li>Nama Paket Aplikasi</li></ul> | <ul><li>Tingkat perangkat dengan geo</li><li>Tingkat impresi (melalui SDK)</li></ul> |
| <Anchor target="_blank" href="/marketers/id/docs/appodeal-campaign-configuration">Appodeal</Anchor> | <ul><li>Kunci Aplikasi</li><li>Kunci API</li><li>ID Pengguna</li></ul> | <ul><li>Gabungkan tingkat dengan geo</li><li>Tingkat perangkat</li></ul> |
| <Anchor target="_blank" href="/marketers/id/docs/bytedance-ads-china-campaign-configuration">Bytedance Ads - lalu lintas China</Anchor> | <ul><li>Kunci yang aman</li><li>ID Aplikasi</li><li>ID Akun</li></ul> | Gabungkan tingkat dengan geo |
| <Anchor target="_blank" href="/marketers/id/docs/chartboost-campaign-configuration">Chartboost</Anchor> | <ul><li>ID Pengguna</li><li>Tanda Tangan Pengguna</li><li>ID Aplikasi</li></ul> | Gabungkan tingkat dengan geo |
| <Anchor target="_blank" href="/marketers/id/docs/meta-ads-integration-setup">Iklan Meta</Anchor> | <ul><li>Login ke Meta ads</li></ul> | Gabungkan tingkat dengan geo |
| <Anchor target="_blank" href="/marketers/id/docs/fyber-campaign-configuration#ad-revenue-tab">Fyber</Anchor> | <ul><li>Rahasia klien</li><li>ID API</li><li>ID Klien</li></ul> | <ul><li>Tingkat perangkat dengan geo</li><li>Tingkat impresi (melalui SDK)</li></ul> |
| Platform Google Marketing -DV360/CM (DoubleClick) | <ul><li>Masuk ke Google Marketing Platform - DV360/CM</li></ul> | Gabungkan tingkat dengan geo |
| <Anchor target="_blank" href="/marketers/id/docs/google-admob-ad-revenue-attribution-configuration">Google Admob</Anchor> | <ul><li>ID pengguna AdMob</li></ul> | <ul><li>Gabungkan tingkat dengan geo</li><li>Tingkat impresi (melalui SDK)</li></ul> |
| <Anchor target="_blank" href="/marketers/id/docs/google-ads-adwords-cost-and-ad-revenue#mencatat-pendapatan-iklan-dengan-google-ads">Google Ads</Anchor> | <ul><li>Otentikasi API oleh OAuth</li></ul> | Gabungkan tingkat dengan geo |
| <Anchor target="_blank" href="/marketers/id/docs/ironsource-campaign-configuration#ad-revenue-tab">ironSource</Anchor> | <ul><li>Kunci Rahasia</li><li>Nama Pengguna</li><li>ID Aplikasi</li></ul> | <ul><li>Gabungkan tingkat dengan geo</li><li>Tingkat perangkat</li><li>Tingkat impresi (melalui SDK)</li></ul> |
| Mintegral | <ul><li>ID Aplikasi</li><li>Kunci Rahasia</li><li>Kunci API</li></ul> | Gabungkan tingkat dengan geo |
| Tapjoy | <ul><li>ID Aplikasi</li><li>Kunci API pemasaran</li></ul> | Tingkat perangkat dengan geo |
| TikTok untuk Bisnis | <ul><li>Kunci yang Aman</li><li>ID Aplikasi</li><li>ID Akun</li></ul> | Gabungkan tingkat dengan geo |
| TopOn | <ul><li>ID aplikasi jaringan</li><li>Kunci penerbit</li></ul> | Tingkat perangkat dengan geo |
| Mediasi Tradplus | <ul><li>Kunci API</li><li>ID aplikasi jaringan</li></ul> | Tingkat perangkat dengan geo |
| <Anchor target="_blank" href="/marketers/id/docs/unity-ads-campaign-configuration">Unity Ads</Anchor> | <ul><li>Kunci API</li><li>ID Aplikasi</li></ul> | <ul><li>Gabungkan tingkat dengan geo</li><li>Tingkat impresi (melalui SDK)</li></ul> |
| Voodoo Ads | <ul><li>ID Bundel</li><li>Token akses</li></ul> | Gabungkan tingkat dengan geo |
| <Anchor target="_blank" href="/marketers/id/docs/vungle-campaign-configuration">Vungle</Anchor> | <ul><li>Kunci API</li><li>ID Aplikasi</li></ul> | Gabungkan tingkat dengan geo |
| Yandex | N/A | <ul><li>Tingkat impresi (melalui SDK)</li></ul> |

</Accordion>

<div data-zendesk-anchors="ad-revenue-attribution=atribusi-pendapatan-iklan 01ECF1PZ2XNCHR4QPATTBV0VMV=atribusi-pendapatan-iklan 01ECF1PZ2Y6ZBAWSNQPEXGJWX3=integration-types-for-ad-revenue-attribution implementation=implementasi 01ECF1PZ2Y9ERT5C50ZD4CDJET=implementasi 01ECF1PZ31TBRGG7GW3404Y1HN=connect-to-ad-revenue-integrated-partners 01H8V10BKK6TVY9G1KWC273K0S=deduplicate-cross-referenced aggregate-ad-revenue-using-events=gabungkan-pendapatan-iklan-menggunakan-event 01H8V10BKK06Z3E823G6GNTPKH=gabungkan-pendapatan-iklan-menggunakan-event comparison-of-inapp-event-methods=perbandingan-metode-in-app-event 01H8V10BKKMG2A704NZC2VFSJM=perbandingan-metode-in-app-event 01ECF1PZ32Z4C20NADJ2SF3EPC=ad-revenue-api-status-and-testing ad-revenue-data=data-pendapatan-iklan 01ECF1PZ3315R242DC78HV60YC=data-pendapatan-iklan 01ECF1PZ33EJHN1YY0DMFKWY7N=ad-revenue-aggregate-data overview-dashboard-aggregated-performance-report=dashboard-ikhtisar---laporan-kinerja-gabungan 01ECF1PZ348365STFGE3136WEJ=dashboard-ikhtisar---laporan-kinerja-gabungan 01ECF1PZ348P0JCBASS4QBD56W=contoh 01ECF1PZ36R9W7A0X4WBR95JDS=ad-revenue-raw-data fields-populated-by-ad-revenue=bidang-yang-diisi-oleh-pendapatan-iklan 01H8V10BKK7BHC31W27G22D23K=bidang-yang-diisi-oleh-pendapatan-iklan fields-by-network=bidang-berdasarkan-jaringan 01H8V10BKKW6NERRYCRD6BVZ54=bidang-berdasarkan-jaringan 01H8V10BKK6N5XJ6GHKC201E3Y=data-freshness 01H8V10BKKG50X5RZR8T2YB092=ad-revenue-data-locker-reports additional-information=informasi-tambahan 01H8V10BKMX7H9H04ZBF3HRJVY=informasi-tambahan 01H8V10BKMH781GR6GHFSD5N50=migrating-from-aggregate-to-userlevel-granularity %5Bclosed-beta%5D-ua-signals-for-ad-networks=closed-beta--ua-signals-for-ad-networks 01H8V10BKM7MMM63JHGCF2DYMC=closed-beta--ua-signals-for-ad-networks 01H8V10BKMGBZ6APJ8A9G7XDKS=informasi-tambahan h_01H5W1BP1CA6F3HDX1F5TS98P1=permission-to-get-ad-revenue-data 01H8V10BKMED8J73G22CFVH6GJ=ad-revenue-event-postbacks-for-ad-networks h_01HFAAC1J9KQ6ZNSCRSRKE9GA3=penting 01H8V10BKM75W6YZ59S6FHFY93=faq 01ECF1PZ39PTEPWJDQA4XPBR4R=traits-and-limitations 01ECF1PZ3A2E5GVNC6D6XDC6WW=list-of-ad-revenue-integrated-partners" />
