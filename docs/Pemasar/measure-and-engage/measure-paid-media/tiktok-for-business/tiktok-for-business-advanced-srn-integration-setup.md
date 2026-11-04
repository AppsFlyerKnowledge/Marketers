---
title: 'TikTok for Business—Pengaturan integrasi SRN tingkat lanjut '
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-06-09T16:49:57Z'
  edited_at: '2023-12-27T14:41:40Z'
  id: 6722785184913
  locale: id
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/id/articles/6722785184913
---
> **Sekilas:** TikTok untuk Business (tiktokglobal\_int), adalah Jaringan Pelaporan Mandiri canggih (<Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns">SRN</Anchor>) yang memberikan pemilik aplikasi kemampuan untuk mengukur atribusi seluler berbasis klik dan tampilan dengan AppsFlyer.

> 📘 **Catatan**
>
> Pada tanggal 30 Januari 2023, integrasi **TikTok untuk Bisnis—SRN Lanjutan** `tiktokglobal_int` yang baru telah ditambahkan, sedangkan integrasi**TikTok untuk Bisnis [Versi Lama]**  `bytedanceglobal_int` secara bertahap dihentikan dan tidak digunakan lagi pada bulan Maret 2024. Transisi ini ditangani oleh TikTok dan mereka akan memberi tahu Anda kapan Anda dapat menghapus integrasi lama. **Untuk menghindari kehilangan data, pastikan kedua integrasi tetap aktif selama fase transisi**. Pelajari lebih lanjut di <Anchor target="_blank" href="/marketers/id/docs/bulletin-tiktok-for-business-advanced-srn">buletin</Anchor>.

<Image alt="TikTok_logo__2_.png" src="https://files.readme.io/3a081755b08fcf19b60ff178506a083449890cb900821f7f1e4b7ef85426dd45-11844735832081.png" width="193px" />

<div id="overview" />

## Ringkasan

Integrasi SRN Lanjutan berarti bahwa semua lalu lintas <Anchor target="_blank" href="/marketers/id/docs/appsflyer-knowledge-base-glossary?query=glossar#dual-consent">persetujuan ganda</Anchor> diatribusikan dan dilaporkan sebagai lalu lintas SRN reguler. Untuk lalu lintas yang tidak disetujui, AppsFlyer dapat mengatribusikan dan mengukur atribusi berdasarkan klik dan impresi yang berasal dari TikTok, sesuai dengan batasan privasi. Integrasi tersebut mendukung atribusi klik dan impresi, biaya, pendapatan iklan, dan audiens.

## Aktifkan mitra

**Prasyarat:** Sebelum menyiapkan integrasi, pastikan Anda <Anchor target="_blank" href="/marketers/id/docs/partner-integrations#contact-details">menghubungi mitra</Anchor> dan membuka akun dengan mereka.

Penyiapan dilakukan dari laman **Integrasi aktif** , tetapi untuk menemukan mitra baru, Anda harus pergi ke <Anchor target="_blank" href="/marketers/id/docs/partner-integrations">Pasar Mitraterlebih</Anchor> dahulu.

**Untuk mengaktifkan integrasi mitra:**

1. Di AppsFlyer, di bawah **Konfigurasi** buka **Pasar Mitra**.
2. Pencarian untuk **TikTok untuk Bisnis** dan pilih.
3. Klik **Siapkan integrasi**. Anda diarahkan ke halaman pengaturan integrasi.
4. Dalam tab **Integrasi** , aktifkan **Aktifkan mitra**.  
   **Catatan:** Tombol harus tetap aktif (<Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">diaktifkan</Anchor>) selama Anda bekerja dengan mitra<Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">.</Anchor>
5. Klik **Simpan Integrasi**.
6. Selesaikan konfigurasi menggunakan tab yang relevan, seperti yang dijelaskan di bagian berikutnya.

<div id="set-up-tiktok-for-business" />

## Menyiapkan TikTok untuk Bisnis

Periode waktu konfigurasi mencakup tab berikut: Integrasi, Tautan Atribusi, Biaya, Pendapatan iklan, dan Izin. Tab **tautan Atribusi** tidak tersedia untuk TikTok untuk Bisnis, tab lainnya bersifat opsional.

<div id="note-1" />

> 📘 **Catatan**
>
> * Beberapa setelan berbeda untuk perangkat iOS dan Android
> * Saat menyiapkan kampanye, nama kampanye tidak boleh diawali atau diakhiri dengan spasi, karena dapat menyebabkan perbedaan di dashboard dan laporan. Pelajari lebih lanjut tentang <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=9535">cara menyiapkan kampanye di TikTok</Anchor>
> * Iklan yang berasal dari <Anchor target="_blank" href="https://www.tiktok.com/business/en/blog/introducing-tiktok-search-ads-toggle">Toggle Iklan Pencarian TikTok</Anchor> disertakan di dalam semua atribusi TikTok. AppsFlyer tidak menerima data mengenai istilah pencarian atau kata kunci tertentu.

<div id="integration-tab" />

<Accordion title="Tab Integrasi">

Tab **Integrasi** mencakup sejumlah bagian, seperti yang dijelaskan di bawah ini.

<div id="activate-partner" />

#### Aktifkan mitra

Untuk mengonfigurasi integrasi, Anda harus [mengaktifkan](#aktifkan-mitra) sakelar **Aktifkan mitra** terlebih dahulu. Pelajari lebih lanjut cara <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation#mengaktifkan-integrasi-mitra">mengaktifkan dan menonaktifkan integrasi mitra</Anchor> .

<div id="advanced-matching-data-sharing" />

<div id="note-2" />

<div id="advanced-data-sharing" />

#### Privasi Lanjutan

Hanya untuk aplikasi iOS: Kontrol Anda atas data yang dibagikan kepada mitra melalui postback dan <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions">laporan</Anchor> bergantung pada status peralihan **<Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework">Privasi Lanjutan</Anchor> (untuk iOS 14.5+ dan lebih baru)**:

| Privasi Tingkat Lanjut: Aktif | Privasi Tingkat Lanjut: Nonaktif |
| --- | --- |
| Postback dikirim hanya untuk event yang diatribusikan ke mitra | Postback dikirim sesuai dengan konfigurasi Anda:<ul><li>**Semua sumber media, termasuk organik.**</li><li>**Mitra ini saja**</li></ul> |
| Postback dikirim sesuai dengan <Anchor target="_blank" href="/partners/id/docs/advanced-privacy-guide-postback-macros-for-ad-networks">templat Privasi Tingkat Lanjut</Anchor> |  |
| <Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework">Data gabungan dan anonim</Anchor> dibagikan dengan mitra, artinya tidak ada data tingkat pengguna (ID perangkat) yang dibagikan. |  |

> 📘 **Catatan**
>
> * Saat mengaktifkan integrasi (`tiktokglobal_int`), sakelar **Privasi Lanjutan** diaktifkan secara default.
> * Saat bermigrasi dari integrasi lama(`bytedanceglobal_int`) dan mengaktifkan integrasi baru (`tiktokglobal_int`), sakelar **Privasi Lanjutan** diaktifkan secara default, apa pun statusnya sebelum migrasi.
> * Menurut TikTok untuk Bisnis, tetap **mengaktifkan** sakelar **Privasi Lanjutan** dapat menyebabkan event kampanye yang tidak dilaporkan dan membatasi peningkatan kinerja kampanye selanjutnya di TikTok

<div id="note-3" />

<div id="general-settings" />

#### Pengaturan umum

**ID Aplikasi TikTok**

Kode unik yang dihasilkan di Pengelola Iklan TikTok dan digunakan oleh TikTok untuk mengonfirmasi kepemilikan pemasang iklan atas aplikasi mereka. Meskipun tidak wajib, disarankan untuk memasukkan ID aplikasi untuk setiap aplikasi Anda. Ini membantu Anda mengontrol data Anda dengan lebih baik di TikTok untuk Bisnis dan membuka produk tambahan.

**Untuk menambahkan ID aplikasi Anda:**

1. [Opsional] Masukkan <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10001060">ID Aplikasi TikTokAnda</Anchor>, tersedia di dashboard Iklan TikTok Anda.
2. [Opsional] Untuk menambahkan lebih banyak ID aplikasi:
   1. Setelah memasukkan ID aplikasi pertama, tekan enter.
   2. Masukkan ID Aplikasi TikTok Anda selanjutnya.

> 📘 **Catatan**
>
> * Mengonfigurasi ID Aplikasi TikTok tidak memengaruhi data Anda di AppsFlyer
> * Saat bermigrasi ke integrasi baru (`tiktokglobal_int`), nilai apa pun dari integrasi lama (`bytedanceglobal_int`) diisi secara otomatis di kolom ini.
> * <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10001070">Pelajari lebih banyak tentang persyaratan ID Aplikasi TikTok untuk iOS 14</Anchor>

<div id="note-4" />

<div id="default-postbacks" />

#### Postback Default

**Bagian ini hanya relevan untuk** **lalu lintas tanpa izin**. Lalu lintas yang disetujui dikirim langsung ke TikTok untuk Bisnis melalui <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns?query=about%20srn">mode SRN</Anchor>.

Konfigurasikan cara mengirim postback untuk **penginstalan**, **penginstalan yang ditolak**, dan **keterlibatan kembali**, yang terjadi sebelum peluncuran aplikasi:

* **Hanya mitra ini** [Default]: Kirim postback hanya jika event diatribusikan ke mitra ini—artinya, pengguna yang melakukannya berasal dari mitra ini.
* **Semua sumber media termasuk organik**: Kirim postback untuk acara yang diatribusikan ke mitra mana pun dan untuk acara organik—artinya, jika pengguna yang melakukannya berasal dari sumber media mana pun. TikTok for Business merekomendasikan untuk mengubah pilihan ke **Semua sumber media termasuk organik** untuk pengoptimalan yang lebih baik

> 📘 **Catatan**
>
> * Hanya untuk aplikasi iOS: Kontrol Anda atas data yang dibagikan dengan mitra melalui postback dan <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions">laporan</Anchor> bergantung pada status sakelar **Privasi Lanjutan (untuk iOS 14.5+ dan yang lebih baru)** .
> * Saat bermigrasi dari integrasi lama (`bytedanceglobal_int`) dan mengaktifkan integrasi baru (`tiktokglobal_int`), status penginstalan postback default yang dipilih adalah **Hanya mitra ini**, terlepas dari statusnya sebelum migrasi.

<div id="note-7" />

<div id="reinstall-attribution" />

<div id="note-6" />

<div id="note-5" />

<div id="install-attribution" />

#### Instal atribusi

Tetapkan atribusi klik-tayang dan lihat-tayang untuk penginstalan (peluncuran pertama). Perlu diperhatikan bahwa hanya penginstalan dalam periode waktu lihat balik yang dapat diatribusikan ke TikTok untuk Bisnis.

1. Atur **Instal periode waktu lihat balik klik-tayang** ke 1-23 jam atau 1-30 hari.  
   **Catatan:** TikTok untuk Bisnis merekomendasikan untuk menyelaraskannya dengan mengatur periode waktu lihat balik klik-tayang menjadi 7 hari.
2. [Opsional] Aktifkan **Instal atribusi lihat-tayang** dan atur **Instal periode waktu atribusi lihat-tayang** antara 1-23 jam.  
   **Catatan:** TikTok untuk Bisnis merekomendasikan untuk menyelaraskannya dengan mengatur periode waktu lihat balik lihat-tayang menjadi 1 hari.

> 📘 **Catatan**
>
> * TikTok untuk Bisnis menggunakan langkah-langkah privasi data tingkat lanjut untuk melindungi orang-orang yang menggunakan layanan mereka. Mulai tanggal 23 Oktober 2021, TikTok untuk Bisnis menyediakan data atribusi lihat-tayang terbatas kepada pemasang iklan di tingkat perangkat. Untuk sumber tingkat pengguna, seperti laporan data lengkap, pesan Push API, laporan Pull API, halaman Ekspor data, dan Data Locker, hanya kolom berikut yang diisi:
>
> * * Sumber media (bytedanceglobal\_int)
>   * Kanal
>   * Jenis sentuhan yang diatribusikan (tayangan)
>   * Waktu sentuh yang dikaitkan (dilaporkan sebagai tanggal saja - "hh/bb/tttt")
>   * Kampanye dilaporkan sebagai "dibatasi"
>     Data ini tidak tersedia di GCD.Laporan data gabungan terus menampilkan konversi lihat-tayang.
> * Saat bermigrasi dari integrasi lama (`bytedanceglobal_int`) dan mengaktifkan integrasi baru (`tiktokglobal_int`), setelan jendela lookback (klik-tayang dan lihat-tayang) disetel ke **nilai default**, terlepas dari statusnya sebelum migrasi. Anda dapat memperbarui pengaturan ini.

<div id="note-9" />

<div id="ignore-active-users-for-retargeting" />

<div id="warning" />

<div id="note-8" />

<div id="re-engagement-attribution" />

#### Atribusi interaksi ulang

Atur jendela interaksi ulang, termasuk atribusi klik-tayang dan lihat-tayang:

1. [Opsional] Aktifkan **Atribusi interaksi ulang**, lalu atur **Jendela lookback klik-tayang interaksi ulang**.
2. [Opsional] Aktifkan **Atribusi lihat-tayang interaksi ulang**, lalu setel **Jendela lookback lihat-tayang interaksi ulang**.
3. [Opsional] Atur **Jendela interaksi ulang**.

> 🚧 **Penting!**
>
> Saat bermigrasi dari integrasi lawas (`bytedanceglobal_int`) dan mengaktifkan integrasi baru (`tiktokglobal_int`), sakelar **Interaksi Ulang** **dinonaktifkan secara default**, terlepas dari statusnya sebelum migrasi. Jika integrasi lawas Anda memiliki <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide">kampanye penargetan ulang</Anchor>, **untuk memastikan kesinambungan, pastikan untuk** **mengaktifkannya** di integrasi baru.

Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide#reengagement-rules-and-windows">aturan dan jendela interaksi ulang</Anchor>.

<div id="in-app-event-postbacks" />

#### Postback in-app event

**Bagian ini hanya relevan untuk lalu lintas yang tidak disetujui.** Lalu lintas yang disetujui dikirim langsung ke TikTok untuk Bisnis melalui <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns?query=about%20srn">mode SRN</Anchor>.

Konfigurasikan pemetaan in-app event dengan event TikTok untuk Bisnis, yang dikirim melalui postback:

1. Aktifkan **Postback in-app event**.
2. Klik **Tambahkan event** untuk menambahkan SDK atau event server-ke-server ke daftar. Tabel berikut ini menjelaskan bidang-bidang yang harus diisi:  

| Nama parameter | Deskripsi |
| --- | --- |
| **event AppsFlyer** | Nama event, seperti yang diterima oleh AppsFlyer baik dari SDK yang terintegrasi ke dalam aplikasi Anda atau dari event server-ke-server.<br />**Tip**: Tidak melihat event yang Anda cari?<ul><li>Pastikan untuk mengaktifkan event di perangkat dengan instalasi non-organik dan periksa kembali.</li><li>Ketik di **event AppsFlyer**, lalu klik **Buat kustom**. Baca lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#event-khusus">pemetaan event kustom</Anchor>.</li></ul> |
| **dipetakan ke event mitra** | Nama atau ID unik setiap event sebagaimana didefinisikan di pihak mitra. Kemungkinan konfigurasi pemetaannya adalah:<ul><li>**Bidang teks:** Dapatkan ID event terkait dari mitra.</li><li>**Kotak drop-down:** Pilih event AppsFlyer yang telah ditentukan sebelumnya yang paling sesuai.</li><li>**Apa adanya**: Kirim event apa adanya, tanpa pemetaan nama.</li></ul> |
| **untuk pengguna dari** | Pilih opsi pengiriman untuk event:<ul><li>**Mitra ini saja** (default): Kirim postback hanya jika event ini diatribusikan ke mitra ini.</li><li>**Semua sumber media termasuk organik**: Kirim postback ke event yang diatribusikan ke mitra mana pun, serta acara organik. TikTok for Business merekomendasikan untuk memilih **Semua sumber media termasuk organik** untuk pengoptimalan yang lebih baik.</li></ul> |
| **termasuk** | <ul><li>**Tidak ada nilai & tidak ada pendapatan** (default): Kirim hanya event itu sendiri tanpa nilai event apa pun.</li><li>**Nilai & tanpa pendapatan**: Kirim semua parameter **kecuali** nilai pendapatan.</li><li>**Nilai & pendapatan**: Kirim semua parameter event, **termasuk** nilai pendapatan (jika terdapat dalam event). TikTok for Business merekomendasikan pemilihan **Nilai & pendapatan** untuk pengoptimalan yang lebih baik.</li></ul> |

3. [Opsional] Klik **Tambahkan ketentuan**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />ikon untuk <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#postback-in-app-event-bersyarat">mengatur kondisi</Anchor> suatu event.
4. Klik **Save Integration (Simpan Integrasi)**.
5. [Opsional] Setelah menyimpan integrasi, sambil tetap membuka halaman konfigurasi, Anda dapat mengintegrasikan lebih banyak aplikasi dengan mitra:
   1. Dari pojok kiri atas, di bawah nama mitra, klik nama aplikasi untuk membuka daftar aplikasi.
   2. Pilih aplikasi lainnya dari daftar drop-down.
   3. Ulangi  langkah integrasi untuk aplikasi yang dipilih.

<div id="note-11" />

<div id="note-10" />

> 📘 **Catatan**
>
> * Hanya untuk aplikasi iOS: Kontrol Anda atas data yang dibagikan dengan mitra melalui postback dan <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions">laporan</Anchor> bergantung pada status sakelar **Privasi Lanjutan (untuk iOS 14.5+ dan yang lebih baru)** .
> * Saat bermigrasi ke integrasi baru (`tiktokglobal_int`), semua event postback yang dikonfigurasi pada integrasi lama (`bytedanceglobal_int`) diisi secara otomatis dengan konfigurasi yang sama.
>   * Jika suatu event dipetakan ke event TikTok for Business **Bayar**, saat bermigrasi ke integrasi baru, nama event ini otomatis diubah menjadi **Beli**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Tab tautan atribusi">

Tautan atribusi tidak relevan untuk <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns">SRN</Anchor> atau SRN Lanjutan.

SRN melakukan atribusi di platform mereka sendiri. Atribusi untuk SRN Lanjutan dilakukan dengan menggabungkan data interaksi mereka dengan data dari AppsFlyer—menggunakan pengaturan atribusi yang Anda tentukan di [tab Integrasi](#integration-tab).

</Accordion>

<div id="cost-tab-for-cost-clicks-and-impressions" />

<Accordion title="Tab biaya (untuk biaya, klik, dan tayangan)">

Integrasi ini memberikan data teragregasi untuk biaya, klik, dan tayangan untuk kampanye, adset, iklan, dan negara Anda. Lihat <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabel integrasi biaya jaringan iklan</Anchor> untuk detail lengkap tentang dimensi, metrik, dan fitur yang didukung.

**Catatan:** Data pada klik dan tayangan termasuk dalam integrasi. Namun, **data biaya memerlukan langganan <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>** .

**Untuk mengaktifkan koneksi API untuk biaya, klik, dan impresi dengan TikTok for Business**:

1. Buka tab **Biaya** dan aktifkan **Dapatkan data biaya**.
2. Klik **Masuk ke Iklan TikTok**.
3. Dari jendela TikTok yang terbuka, masuk ke akun TikTok Anda dan konfirmasikan izin yang diperlukan.
4. Setelah pesan sukses muncul di jendela TikTok, tutuplah. Detail akun TikTok Anda sekarang muncul di bawah **Akun terhubung**.
5. Dari **ID akun pemasang iklan** > **ID Pemasang Iklan**: Masukkan ID akun pemasang iklan TikTok, dan klik **Tambah**.  

   > 📘 **Catatan**
   >
   > * Untuk mendapatkan **ID Pemasang Iklan** dari akun bisnis TikTok Anda: Buka **Pengguna** > **Anggota**, dan di bawah akun Pemasang Iklan, Anda dapat melihat ID tersebut.
   > * Pastikan**ID Pemasang Iklan** yang Anda tambahkan dikaitkan dengan **akun TikTok** yang Anda hubungkan di langkah 2, karena ini adalah akun tempat data akan dikumpulkan.
   > * Hubungkan setidaknya satu **ID Pemasang Iklan**. Anda dapat menambahkan hingga 30.

6. Klik **Hemat Biaya**.

<div id="web-to-app-measure-app-activity-for-non-app-campaigns" />

<div id="access-tiktok-conversion-data-via-appsflyers-gcd-api-for-deep-linking" />

<div id="deep-linking-with-tiktok-for-business" />

<div id="for-roi360-subscribers" />

#### Untuk pelanggan ROI360

* Pemasang iklan dan agensi yang mengaktifkan API biaya di integrasi `bytedanceglobal_int` lama dan integrasi `tiktokglobal_int` saat ini mungkin melihat data biaya duplikat. Untuk menghindari hal ini, buka tab integrasi `bytedanceglobal_int` > **Biaya** , dan matikan tombolnya.   
  Namun, saat mengaktifkan integrasi biaya baru, data biaya dari 5 hari sebelum hari transisi dikumpulkan secara otomatis. Artinya, integrasi baru diharapkan menampilkan duplikat data biaya selama 5 hari tersebut. **Misalnya**, jika integrasi biaya lama dinonaktifkan pada tanggal 15 Januari dan integrasi biaya baru diaktifkan pada hari yang sama, duplikat data biaya akan terlihat dalam integrasi biaya baru antara tanggal 10 hingga 14 Januari, meskipun baru diaktifkan pada tanggal 15 Januari.
* Lihat <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabel integrasi biaya jaringan iklan</Anchor> untuk detail lengkap tentang dimensi, metrik, dan fitur yang didukung.
* <Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Lihat status API biaya</Anchor> dan terakhir kali AppsFlyer berhasil menarik data biaya yang cocok di dashboard status integrasi biaya (dan pendapatan iklan), atau di dashboard jaringan iklan individual.
* Pelajari lebih banyak tentang <Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">mengaktifkan Cost API</Anchor>.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Tab Pendapatan Iklan">

Bagian ini relevan jika Anda bertindak sebagai penerbit—menampilkan iklan mitra kepada pengguna Anda. Anda dapat mengukur keterlibatan pengguna yang diperoleh dari berbagai sumber dan mencari tahu sumber mana yang lebih menguntungkan.

**Untuk mengaktifkan API pendapatan iklan**:

* Ikuti <Anchor target="_blank" href="/marketers/id/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">petunjuk integrasi ini</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Tab Hak Akses">

Di bagian ini, Anda dapat memilih izin untuk memberikan TikTok untuk Bisnis akses ke data Anda dan melakukan berbagai tindakan.

Perhatikan bahkan setelah integrasi <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">dinonaktifkan</Anchor>, ketika tombol **izin TikTok untuk Bisnis** aktif, izin tetap diberikan. 

Pelajari lebih banyak tentang <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#permissions-tab">pemberian izin</Anchor>.

</Accordion>

<div id="set-up-tiktok-for-business-for-agencies" />

## Mengatur TikTok untuk Bisnis untuk agensi

Agensi yang bekerja atas nama pemasang iklan dapat mengaktifkan integrasi TikTok untuk Bisnis dan mulai mendapatkan atribusi untuk kampanye mereka. Namun, integrasi ini memiliki beberapa keterbatasan jika menyangkut agensi.

<div id="note-12" />

<div id="how-smart-plus-data-is-reported-in-appsflyer" />

<div id="how-smart-plus-campaigns-are-structured" />

<div id="smart-plus-campaigns-reporting" />

<div id="send-complex-in-app-events-to-tiktok" />

<div id="important" />

<div id="agency-limitations" />

### Keterbatasan agensi

* Sebuah agensi dapat mengakses integrasi TikTok untuk Bisnis hanya setelah pemasang iklan yang bekerja sama dengan mereka telah mengaktifkannya di pihak mereka.
* Mulai 1 Januari 2024, parameter atribusi yang ditampilkan di halaman integrasi agensi diwarisi dari integrasi pemasang iklan dalam mode **hanya lihat** . Artinya agensi dapat melihat cara pemasang iklan mengonfigurasi periode waktu lihat balik atribusi, namun tidak dapat mengonfigurasinya sendiri.
* Untuk event setelah atribusi, jika diberikan izin oleh pemasang iklan, agensi dapat mengonfigurasi postback in-app event.
* Agensi tidak dapat mengaktifkan pengaturan Privasi Lanjutan (meskipun telah diberikan izin)—ini terbatas pada pemasang iklan saja.

**Untuk mengatur TikTok untuk Bisnis untuk agensi:**

1. Di AppsFlyer, di bawah **Konfigurasi** buka **Pasar Mitra**.
2. Temukan **TikTok untuk Bisnis** dan pilih itu.
3. Masukkan **ID Aplikasi TikTok**.
4. Masukkan **ID Akun TikTok** agensi Anda. Ini mengidentifikasi lalu lintas agensi dan membedakannya dari lalu lintas pemasang iklan.
5. Klik **Simpan Integrasi**.  

   <Image alt="tiktok_agency_account_id.png" src="https://support.appsflyer.com/hc/article_attachments/15195630638609" width="442px" />

> ❗️ **Peringatan**
>
> ID akun TikTok untuk Bisnis TIDAK BOLEH dibagikan antara pemasang iklan atau agensi. Jika ID dibagikan, maka SEMUA penginstalan pemasang iklan secara otomatis teratribusi di dashboard agensi.

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/bytedance-ads-china-campaign-configuration">Iklan ByteDance (Mesin Laut)</Anchor> untuk trafik China (bytedance\_int)
> * <Anchor target="_blank" href="/marketers/id/docs/skan-interoperation-with-tiktok-for-business">Interoperasi SKAN dengan TikTok untuk Bisnis</Anchor>

<div data-zendesk-anchors="01H8VVCC8GW5AZ3M475XFZY9JW=catatan overview=ringkasan 01H8VVCC8G3ZXZJMHSMJ67GMG4=ringkasan activate-partner=aktifkan-mitra 01H8VVCC8GH1MNRAY9HC9P6JR0=aktifkan-mitra setting-up-tiktok-for-business%C2%A0integration=menyiapkan-tiktok-untuk-bisnis 01H8VVCC8GPY4SEFGK30Q1BJZ6=menyiapkan-tiktok-untuk-bisnis 01H8VVCC8G6P25R0N5A7S3NGY7=catatan-1 01H8VVCC8GY6WTH0404RH2AR9F=integration-tab activate-partner::e4f2f638=aktifkan-mitra-1 01H8VVCC8G0KR4AA2HD9S8QBKD=aktifkan-mitra-1 advanced-privacy=privasi-lanjutan 01H8VVCC8G0Z6ZHC10KVY9CGGQ=privasi-lanjutan 01H8VVCC8GC57YTDWA9EB2VP87=catatan-2 general-settings=pengaturan-umum 01H8VVCC8GSDPSNN0AJPVZPR8P=pengaturan-umum 01H8VVCC8G2JB115XW49HJQFHA=catatan-3 default-postbacks=postback-default 01H8VVCC8GW677RN6R6CV35KGG=postback-default 01H8VVCC8G6M8D3WQ2CM10ZNZX=catatan-6 install-attribution=instal-atribusi 01H8VVCC8GK8VFPBEPAMVHCAWM=instal-atribusi 01H8VVCC8G3YFDZVV9X9709F9M=catatan-5 reengagement-attribution=atribusi-interaksi-ulang 01H8VVCC8HHG5290PYF0BT29QA=atribusi-interaksi-ulang 01H8VVDWH85M34K7Z75BAT7BQW=penting inapp-event-postbacks=postback-in-app-event 01H8VVCC8HHZRFQ2T1X478YZMP=postback-in-app-event 01H8VVCC8HDMTY1P2SG31HD61K=catatan-6 01H8VVCC8H53ZRMDBNK1436NAX=attribution-link-tab 01H8VVCC8H74GDVCNAXT0741MG=cost-tab-for-cost-clicks-and-impressions 01H8VVCC8HFJF62TC7DNXRH22A=catatan-7 for-xpend-subscribers=untuk-pelanggan-roi360 01H8VVCC8HWDC9A03FRY5BC87Y=untuk-pelanggan-roi360 01H8VVCC8H90ANM70QAHKTQQ1S=ad-revenue-tab 01H8VVCC8HAG0XVWE2T9PRDHTK=permissions-tab setting-up-tiktok-for-business-for-agencies=mengatur-tiktok-untuk-bisnis-untuk-agensi 01H8VVCC8HVNNQ9PJS4ZQCVDNS=mengatur-tiktok-untuk-bisnis-untuk-agensi agency-limitations=keterbatasan-agensi h_01HHVGS94CB9XC0T63VFDZ18JS=keterbatasan-agensi 01H8VVCC8HWJ2WQ83E0CZMEHH1=peringatan h_01HE7RY8K7HV2CTZ2S537YRCNQ=lihat-juga" />
