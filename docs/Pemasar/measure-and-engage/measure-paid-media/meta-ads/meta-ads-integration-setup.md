---
title: Pengaturan integrasi Meta ads
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Facebook
    - App Install
    - View-Through
    - integrated partner
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
  created_at: '2013-01-24T20:13:58Z'
  edited_at: '2024-10-12T18:01:39Z'
  id: 207033826
  locale: id
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/id/articles/207033826
---
> **Sekilas:** Pelajari tentang mengintegrasikan Meta ads dengan AppsFlyer.

<div id="meta-ads-setup-guide" />

## Panduan pengaturan Meta ads

Berapa lama waktu yang diperlukan untuk mulai menghubungkan iklan aplikasi seluler Meta ads Anda dengan AppsFlyer?

Jika Anda sudah memiliki <Anchor target="_blank" href="/marketers/id/docs/integrate-the-appsflyer-sdk">AppsFlyer SDK yang terintegrasi ke dalam aplikasi Anda</Anchor>, dan telah menetapkan aplikasi Anda di Meta ads, jawabannya kurang dari satu menit!

Anda tidak perlu mengimplementasikan Facebook Login atau mengintegrasikan aplikasi Anda dengan SDK Facebook untuk atribusi seluler. Cukup ikuti petunjuk [pengaturan langkah demi langkah dasar](/docs/meta-ads-integration-setup#pengaturan-atribusi-meta-ads-dasar) di bawah ini. Setelah itu, lihat [opsi pengaturan lanjutan](/docs/meta-ads-integration-setup#pengaturan-atribusi-meta-ads-lanjutan) untuk Meta ads.

### ID Aplikasi Facebook

Untuk mengintegrasikan Meta ads dengan AppsFlyer, pertama, buat <Anchor target="_blank" href="https://developers.facebook.com/docs/apps/register">ID Aplikasi Facebook</Anchor>, lalu buka kembali.

**Untuk membuat** ID Aplikasi Facebook :

1. Pada **Meta ads**, buka <Anchor target="_blank" href="https://developers.facebook.com/apps">Dashboard Aplikasi Anda.</Anchor>
2. Di bawah **Apps (Aplikasi)**, klik **Buat Aplikasi Baru.**
3. Lengkapi nama aplikasi Anda dan masukkan namespace (ruang nama) unik Pastikan untuk menambahkan platform yang tepat untuk aplikasi Anda, jika tidak, penginstalan mungkin tidak diatribusikan dengan benar.

**Untuk membuka kembali ID Aplikasi Facebook** :

1. Pada **Meta ads**, buka <Anchor target="_blank" href="https://developers.facebook.com/apps">Dashboard Aplikasi Anda.</Anchor>
2. Klik aplikasi yang diperlukan.
3. Klik ID Aplikasi, yang muncul di kiri atas layar, untuk menyalinnya.  
   ![meta-ads-for-developters.jpg](https://files.readme.io/86ef4cdfbb965a362c77527a532af2bb7e7eb2b39b477e4a93a2d2f22e19f377-30354101851793.jpg)

AppsFlyer mengatribusikan data per ID Aplikasi. ID Aplikasi Facebook yang sama dapat digunakan untuk [aplikasi Android dan iOS Anda](https://developers.facebook.com/docs/app-ads/app-setup/). Perhatikan bahwa untuk iOS 14+, Meta ads membatasi akun iklan hingga sembilan akun per aplikasi.

<div id="basic-meta-ads-attribution-setup" />

## Pengaturan atribusi Meta ads dasar

Untuk mulai mengatribusikan kampanye Meta ads dengan AppsFlyer, ikuti langkah-langkah berikut:

<Accordion title="Tonton">

<Embed title="Pengaturan integrasi Meta ads" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/mrwnab4x7r" providerUrl="https://fast.wistia.com" />

</Accordion>

<Accordion title="Baca">

1. **Untuk mengaktifkan integrasi dengan Meta ads:**
   1. Buka aplikasi Anda di [Meta untuk pengembang](https://developers.facebook.com/apps).
   2. Pilih aplikasi.  

      ![find-fb-app-id.jpg](https://support.appsflyer.com/hc/article_attachments/25899320112017)
   3. Untuk menyalin ID aplikasi Anda, klik di bagian atas halaman layar.  

      ![meta-ads-copy-app-id.jpg](https://support.appsflyer.com/hc/article_attachments/25899342893585)
   4. Di AppsFlyer, dari menu samping, pilih **Berkolaborasi** > **Pasar Mitra**
   5. Cari Meta ads dan pilih.
   6. Klik **Atur integrasi**. Anda diarahkan ke halaman pengaturan integrasi.
   7. Di **tab Integrasi**: Hidupkan Aktifkan mitra .  
       **Catatan:** Tombol harus tetap pada (<Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">diaktifkan</Anchor>) selama Anda bekerja dengan mitra<Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">.</Anchor>
   8. Di bawah **Pengaturan Umum**:  

      ![meta_ads_general_settings2.png](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)

      * Rekatkan ID aplikasi Anda di **ID Aplikasi Facebook** Bidang
      * Rekatkan pengarah pemasangan [kunci dekripsi dari iklan Meta](#data-terenkripsi-dari-google-play-referrer-api-atau-meta-install-referrer).
   9. Mengaktifkan atau menonaktifkan **Berbagi data tingkat lanjut**, lihat [Berbagi data tingkat lanjut](#advanced_data_sharing) di bawah ini. (Secara bertahap tersedia untuk semua akun pada bulan Oktober 07-2024-14
   10. Klik **Simpan Integrasi**.
2. [opsional] **Konfigurasikan pengaturan yang disarankan:**  

   ![meta_ads_install_attribution.png](https://files.readme.io/82b59d3460ea0487de932b7e49be7de10a8f4eaca151afaca281724f85d0c325-30354145601681.png)

   * Untuk mencocokkan dengan jendela tampilan balik klik-tayang dari Iklan Meta, atur ke 7 hari.  
      Perhatikan bahwa: (Perhatikan bahwa [ada beberapa kasus tertentu di mana *default*-nya berbeda](https://www.facebook.com/business/help/395050428485124?id=428636648170202)).
   * Untuk mencocokkan *lookback window* lihat-tayang (*view-through*) dari Meta ads, atur ke satu hari. atur ke satu hari.
   * Untuk mengaitkan pengguna yang menginstal ulang aplikasi selama Periode Waktu Re-attribution Aktifkan Reinstall attribution (atribusi penginstalan ulang).  
      Anda tidak perlu mengaktifkan atribusi penelusuran atau mengonfigurasi jendela lihat kembali untuk menginstal ulang atribusi, karena mengambil konfigurasinya dari atribusi instalasi Pengaturan:

Masih belum melihat hasilnya di AppsFlyer? Lihat Pemecahan masalah integrasi Meta ads

</Accordion>

<div id="advanced-meta-ads-attribution-setup" />

## Pengaturan atribusi Meta ads lanjutan

Setelah mengatur atribusi dasar untuk Meta ads, kini waktunya untuk mengatur atribusi lanjutan cepat.

<Accordion title="Tonton">

<Embed title="Pengaturan integrasi Meta ads" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/slxtvp2pcs" providerUrl="https://fast.wistia.com" />

</Accordion>

<Accordion title="Baca">

<div id="userlevel-data" />

<Accordion title="Data level pengguna">

#### Meta ads membatasi data atribusi

Efektif 29 Oktober 2021, hanya pelaporan agregat tersedia untuk pengiklan. Ini berarti bahwa kedua data atribusi tampilan-tayang dan klik-tayang muncul sebagai "dibatasi" dalam laporan data mentah. Bidang lainnya yang terkait dengan sumber media tidak diisi. Lihat: <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions#pembatasan-data-lengkap">Pembatasan konten data mentah</Anchor>.

Ini berlaku untuk semua pemasang iklan, sistem operasi, dan MMP. Ini terkait data tingkat perangkat untuk semua pengguna iOS dan Android, apa pun status izin ATT atau personalisasi iklannya.

AppsFlyer terus menerima data tingkat perangkat dari Meta ads, yang berarti bahwa kemampuan atribusi dan pelaporan kami (termasuk atribusi multi-sentuh, LTV, ROI, kohort, laporan retensi, perlindungan penipuan, Audiens, dan layanan lainnya) tetap tidak berubah. Lihat <Anchor target="_blank" href="/marketers/id/docs/aggregated-and-analytics-reporting-overview">alat pelaporan gabungan dan analitik</Anchor>.

<div id="getting-userlevel-data-for-android-installs" />

#### Mendapatkan data tingkat pengguna untuk penginstalan Android dan in-app event

**Google Play *Install Referrer* API**

Meskipun data tingkat pengguna dibatasi, Meta ads membagikan metadata kampanye dengan pemasang iklan untuk iklan aplikasi Android yang mengarahkan pengguna ke Google Play Store. Dalam hal ini, bidang atribusi tersedia bagi pemasang iklan di Google Play *Install Referrer* API, yang harus <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">diintegrasikan ke dalam aplikasi Anda</Anchor>. Bidang, yang tersedia melalui Google Play *install referrer* API, mengisi laporan data lengkap AppsFlyer dengan jenis kesesuaian `gp_referrer`. Ini hanya tersedia setelah kode dekripsi dikirimkan dan penginstalan diatrbusikan dengan Meta ads. Hal ini membuat AppsFlyer dapat mengatribusikan pengguna yang tidak memiliki ID iklan (LAT diaktifkan).

**Meta *Install referrer***

Untuk Google Play *Install Referrer* API: Pengarah penginstal Meta memungkinkan AppsFlyer untuk menerima metadata kampanye iklan dari penyimpanan lokal perangkat. Data ini digunakan untuk pengukuran atribusi. The perbedaan utama antara Penginstalan Google Play API perujuk dan perujuk instalasi Meta adalah:

* Perujuk penginstal Meta dapat menyertakan kesan dan klik data, sedangkan Google Play Install API perujuk terbatas pada data klik
* Perujuk pemasangan Meta berpotensi mencakup data dari beberapa sesi, sedangkan Google Play Install Referrer API terbatas pada data dari sesi terakhir saja (perangkat harus menginstal aplikasi dalam sesi yang sama dengan klik yang terjadi)

Akibatnya, Anda mungkin melihat peningkatan Meta-attributed menginstal dalam laporan data mentah. Saat penginstalan adalah Untuk Google Play *Install Referrer* API: atau pengarah penginstal Meta, data tersedia dalam laporan data mentah. Bidang yang mungkin tersedia untuk atribusi melalui populasi pengarah pemasangan Meta Laporan data mentah AppsFlyer dengan jenis pertandingan `fb_referrer` untuk atribusi dari aplikasi Facebook dan `ig_referrer` untuk atribusi dari aplikasi Instagram. Ini hanya tersedia satu kali kunci dekripsi dikirimkan dan penginstalan dilakukan dikaitkan dengan iklan Meta. Perujuk penginstal Meta Kunci dekripsi adalah kunci yang sama Untuk Google Play *Install Referrer* API: dan tidak perlu diberikan kepada AppsFlyer sedetik pun Waktu.

**Bidang atribusi kampanye tersedia melalui *referrer*:**

* ID Iklan
* Nama iklan
* ID adset
* Nama adset
* ID kampanye
* Nama kampanye
* ID akun
* Saluran

> 📘 **Catatan**
>
> * **Untuk Google Play *Install Referrer* API:**
>   * AppsFlyer SDK harus **V5.4.0+** agar data perujuk dapat diteruskan dengan benar. Data perujuk memiliki prioritas atas data yang disediakan oleh API dan tidak Dibatasi* Solusi ini berlaku untuk Atribusi Click-Through Atribusi lihat-tayang
>   * Bidang Saluran ditentukan oleh nilai saluran yang diterima dari Google Play *Referrer* API (dikirim ke Google Play oleh Meta). Jika string kosong diterima, bidang Saluranl menunjukkan "Tidak Ada".
> * **Untuk Meta *install referrer*:** Merujuk ke <Anchor target="_blank" href="/marketers/id/docs/bulletin-get-meta-ads-attribution-in-raw-data-reports-with-the-meta-install-refe">prasyarat dan tindakan yang diperlukan</Anchor> dijelaskan dalam buletin.

#### Meta *install referrer*—FAQ

**Dalam kasus apa saja Meta *install referrer* berlaku untuk atribusi?**

* Untuk menginstal atribusi:
  * Atribusi *click-through*, untuk semua kampanye
  * Atribusi melalui tampilan didukung untuk semua Kampanye Aplikasi Advantage+ dan Kampanye Promosi Aplikasi Manual dengan jangkauan luas penargetan (misalnya, di mana usia dan jenis kelamin diatur ke Default).
* Kompatibilitas Google Play Store dan non-Google Memutar toko aplikasi Android
* Pengecualian: Ini tidak termasuk pengalihan kampanye ke halaman arahan

**Untuk apa "penargetan luas" digunakan dalam Meta ads?**

Penargetan yang luas diperlukan untuk menerima data penginstalan *view-through*. menginstal data. Konfigurasi kampanye yang didukung Termasuk

* Usia: Pengaturan *default* (18-65+) diterapkan
* Jenis kelamin: Pengaturan *default* (Semua jenis kelamin) diterapkan
* Lokasi: Kelompok negara dan negara didukung. **Catatan:** Untuk lokasi yang lebih ditargetkan (seperti kota atau kode pos) yang memanfaatkan kampanye penargetan inklusi dengan ini perlu ditetapkan Atur sebagai relaks.
* Penargetan Terperinci: Segmen minat, perilaku, dan demografi lanjut usia ditetapkan sebagai santai.
* Audiens Khusus: Atur sebagai relaks.
* Untuk "santai", "Penargetan terperinci yang menguntungkan" untuk kampanye iklan harus dipilih:  

  <Image alt="" src="https://support.appsflyer.com/hc/article_attachments/22950622532497" width="569px" />

#### Data terenkripsi dari Google Play Referrer API atau Meta install referrer

Data dari Google Play Referrer API atau pengarah instalasi Meta dienkripsi oleh Meta. Data ini dapat didekripsi menggunakan kunci yang tersedia untuk Anda di akun pengembang Meta. Anda harus memberi kami kode dekripsi seperti yang dijelaskan pada baris tindakan yang diwajibkan. Kode dekripsi hanya perlu dikirimkan sekali per aplikasi.

Perhatikan bahwa jika kode tidak diberikan atau dihapus, ada beberapa kasus di mana Meta ads masih diatribusikan untuk penginstalan berdasarkan *referrer* - bahkan tanpa bidang atribusi kampanye (disebutkan dalam daftar di atas). Ini terjadi ketika:

* Meta ads tidak mengeklaim penginstalan
* Data yang diterima dari Google Play *Install Referrer* API diterima tetapi tidak didekode
* Dan ini adalah klik terakhir

**Untuk mendapatkan kode dekripsi Anda dari Meta:**

1. Masuk ke portal pengembang Meta Anda.
2. Buka ***My Apps* (Aplikasi Saya)** di pojok kanan atas.
3. Pilih aplikasi yang ingin Anda akses kode dekripsinya.
4. Arahkan ke **Pengaturan** > **Dasar** di bagian kiri halaman.  

   [![](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)
5. Gulir ke bawah ke bagian Android dan Anda akan lihat kunci dekripsi Anda yang berlabel Instal Perujuk kunci dekripsi di bawah bidang Nama Paket. Catatan: Ini adalah bagian yang sama dengan tempat Anda mengonfigurasi nama paket Anda dan Google Play Store.

**Untuk mengatur kode dekripsi di AppsFlyer:**

1. [Wajib] Verifikasi bahwa AppsFlyer SDK V5.4+ adalah diadopsi dalam aplikasi Anda. Jangan gunakan versi sebelumnya.
2. Di AppsFlyer, dari menu samping, pilih **Kolaborasi** > **Integrasi Aktif**.
3. Pilih **Meta ads.** [![meta_ads_general_settings2.png](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)
4. Di tab **Integrasi**, tempelkan Tetapkan kunci dekripsi perujuk penginstalan Ini hanya perlu dilakukan sekali untuk setiap aplikasi.
5. Klik **Simpan integrasi**.

</Accordion>

<div id="cost-clicks-and-impressions" />

<Accordion title="Biaya, klik, dan tayangan">

[![meta_cost_tab.png](https://files.readme.io/5c840dbce9c019a8655e8b7b54b8d8e29f3128a8e7115065d0f4083b703b80c0-30354101895185.png)](https://files.readme.io/5c840dbce9c019a8655e8b7b54b8d8e29f3128a8e7115065d0f4083b703b80c0-30354101895185.png)  

Integrasi ini menyediakan data agregat mengenai biaya, klik, dan tayangan untuk kampanye dan set iklan Anda, iklan, dan geografis/negara. Lihat <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabel integrasi biaya jaringan iklan</Anchor> untuk detail lengkap tentang dimensi dan metrik yang didukung, dan fitur.

**Catatan:** Data klik dan impresi. sudah termasuk dalam integrasi. Namun: Data biaya memerlukan langganan ROI360.

**Untuk mengaktifkan API biaya**:

1. Pastikan Anda masuk ke pengguna iklan Meta akun, yang diaktifkan untuk menangani akun kampanye di iklan Meta. Pengguna yang masuk harus memiliki izin untuk menjalankan semua kampanye di Meta Manajer Bisnis.
2. Buka tab **Biaya** .
3. Aktifkan **Dapatkan Data Biaya, Klik, dan Tayangan**.
4. Klik tombol **login f** . Anda dapat masuk dengan bisnis atau admin iklan Meta akun.
5. Saat diminta, izinkan AppsFlyer untuk mengakses Data kampanye iklan Meta.  
    **Catatan**: Dalam sinkronisasi data pertama setelah integrasi, serta sinkronisasi berikutnya, AppsFlyer menerima data biaya iklan Meta untuk naik hingga 7 hari terakhir secara retroaktif.

Baca lebih lanjut tentang bagaimana iklan Meta mendefinisikan klik dan tampilan.

**Untuk menghapus akun Meta ads yang terhubung: IN pada kolom tindakan, arahkan kursor ke akun dan klik Hapus koneksi**

<div id="notes" />

> 📘 **Catatan**
>
> * Jika Anda sudah masuk ke iklan Meta, ketika Anda mengklik **f login** tombol, jendela akan segera terbuka dan menutup. Ini adalah perilaku normal.
> * Jika Anda memiliki beberapa pengguna dengan izin untuk iklan Meta, praktik terbaik adalah melakukan login untuk mereka semua, untuk <Anchor target="_blank" href="/marketers/id/docs/meta-ads-faq#why-doesnt-cost-data-include-data-from-all-campaigns">hindari mendapatkan data parsial</Anchor>.

<div id="cost-data-sync-status" />

#### Status sinkronisasi data biaya

<Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Lihat status API biaya</Anchor> dan terakhir kali AppsFlyer berhasil menarik data biaya yang cocok di *dashboard* status integrasi biaya (dan pendapatan iklan), atau di *dashboard* jaringan iklan individual.

Anda dapat menyinkronkan beberapa akun untuk menarik data biaya. Untuk setiap akun yang disinkronkan, AppsFlyer menunjukkan status integrasi biaya dan terakhir kali AppsFlyer dikelola untuk menarik data biaya yang sesuai.

Pelajari lebih banyak tentang memperkaya data Anda dengan <Anchor target="_blank" href="/marketers/id/docs/meta-ads-faq#faq-biaya-meta-ads">data biaya, klik, dan tayang</Anchor>.

</Accordion>

<div id="inapp-event-mapping" />

<Accordion title="Pemetaan In-App Event">

[![meta_iae_postbacks.png](https://files.readme.io/8f2fd671a067684738964d245a9e80873bbb28f33a55c61ee0cb00a32ac9815e-30354145614865.png)](https://files.readme.io/8f2fd671a067684738964d245a9e80873bbb28f33a55c61ee0cb00a32ac9815e-30354145614865.png)

**Untuk memetakan *in-app event*:**

1. Aktifkan***in-app event postback*.**  
    Saat mengaktifkan pemetaan peristiwa dalam aplikasi iklan Meta untuk sebuah aplikasi untuk **pertama kalinya**, **af\_app\_open** secara otomatis dipetakan ke **fb\_mobile\_activate\_app**.
2. Isi parameter berikut: 

| Nama Parameter | Deskripsi |
| --- | --- |
| ***event* AppsFlyer** | Ketik nama event. yang diterima oleh AppsFlyer baik dari SDK yang diintegrasikan ke dalam aplikasi Anda atau dari server ke server event<br />**Tips**: Jangan Tidak menemukan event yang Anda cari? Untuk:<ul><li>Pastikan untuk mengaktifkan acara pada perangkat dengan instalasi non-organik dan periksa kembali.</li><li>Ketik di AppsFlyer event lalu klik **Buat kustom**. Baca lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#event-khusus">pemetaan acara khusus.</Anchor></li></ul> |
| **dipetakan ke *event* mitra** | Nama atau ID unik dari setiap acara, sebagaimana didefinisikan pada Meta ads: Kemungkinan pemetaan konfigurasi tersebut:<ul><li>**Bidang teks:** Dapatkan yang sesuai ID acara dari iklan Meta</li><li>**Kotak tarik-turun:** Pilih yang paling sesuai AppsFlyer yang telah ditentukan sebelumnya Event</li><li>**Seperti itu**: Kirimkan acara sebagaimana adanya adalah, tanpa pemetaan nama.</li></ul> |
| **untuk pengguna dari** | Pilih opsi pengiriman untuk *event*:<ul><li>**Hanya mitra ini**: kirim *postback* hanya jika *event* ini diatribusikan ke Meta ads.</li><li>**Semua sumber media, termasuk organik**: kirim *postback* untuk *event* yang diatribusikan ke mitra dan *event* organik mana pun.</li></ul> |
| **termasuk** | <ul><li>**Tidak ada data (default)**: hanya mengirim acara itu sendiri tanpa nilai peristiwa.</li><li>**Nilai dan pendapatan**: mengirim semua parameter peristiwa, **including** nilai pendapatan (jika yang ada dalam acara tersebut).</li><li>**Nilai tanpa pendapatan**: kirim semua parameter **excluding** nilai pendapatan.</li></ul> |

3. Untuk menambahkan SDK atau peristiwa server-ke-server  ke dalam daftar, klik **Tambah acara**.

**Batasan terkait nama *event*:**

* Batasan panjang nama *event*: 2-40 karakter
* Karakter berikut tidak diizinkan:
  * Titik dua (:)
  * Titik (.)
  * Set karakter non-Latin (Inggris): Sebagai tanggal 12 Januari 2020, iklan Meta menolak Karakter Cina. AppsFlyer belum menguji set karakter lain dan Anda harus gunakan ini hanya setelah memverifikasi dengan Meta iklan jika mereka mendukung set karakter ini di postback.
* Nama *event* peka huruf besar-kecil. Untuk menghindari perbedaan, pastikan Anda menggunakan huruf besar yang benar dalam acara tersebut nama untuk semua sumber media dan versi aplikasi.

<div id="note-2" />

> 📘 **Catatan**
>
> * Anda dapat mengirim <Anchor target="_blank" href="/marketers/id/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">pengembalian pendapatan iklan</Anchor> ke iklan Meta sehingga mereka dapat mengoptimalkan kampanye menggunakan data pendapatan iklan:
>   * **Nama *event*:** af\_ad\_revenue
>   * **Dipetakan ke:** fb\_mobile\_purchase
> * Pelajari lebih lanjut tentang SSOT Pemetaan in-app event iklan Meta

</Accordion>

<div id="retargeting-attribution" />

<Accordion title="Atribusi Penargetan Ulang">

Atribusi penargetan ulang AppsFlyer untuk iklan Meta memungkinkan pengiklan mengaitkan keterlibatan pengguna yang sudah ada dengan iklan Facebook, dan mengukur kualitas iklan pengguna, keterlibatan posting, menggunakan laporan AppsFlyer. Ini harus digunakan hanya jika Anda secara aktif berlari yang ditargetkan untuk pengguna Facebook Anda sendiri.

1. <Anchor target="_blank" href="/marketers/id/docs/app-settings#reengagement-attribution">Aktifkan penargetan ulang di halaman Pengaturan Aplikasi (*App Settings*)</Anchor> .
2. Pada halaman mitra iklan Meta, aktifkan Atribusi interaksi ulang
3. Mengatur Jendela lihat balik click-through interaksi ulang  
    Jendela peninjauan kembali adalah periode waktu, mulai dari klik iklan, di mana aplikasi harus diluncurkan agar klik menjadi dicatat sebagai keterlibatan kembali.  
    Pilih unit jendela kilas balik (jam atau hari), dan atur slider ke nilai yang diinginkan.  

   ![re-engagement_attribution_toggle.png](https://files.readme.io/86e0bb7d4dfa8e55720ed67d1ff8ea34f0e71df9df12382996bb7ea8817da4ba-30354101904785.png)
4. Aktifkan **Atribusi *view-through* interaksi ulang**.
5. Atur ***Slider* *re-engagement view-through lookback window* (jendela lihat balik lihat-tayang interaksi ulang)** ke nilai yang diinginkan (sampai 24 jam). Ini merupakan periode waktu yang dimulai dari tayangan iklan, saat aplikasi harus diluncurkan agar tayangan dapat dicatat sebagai interaksi ulang.

   ![re-engagement_view-through_toggle.png](https://support.appsflyer.com/hc/article_attachments/13880480985489)
6. Atur **Jendela interaksi ulang**.  
    Ini adalah periode ketika peristiwa dalam aplikasi pengguna dikaitkan dengan sumber media penargetan ulang, sebagai sumber utama.  
    Anda dapat mengatur nilai dalam hari (1-90), jam (ke atas) hingga 23), atau bahkan seumur hidup. Nilai *default*-nya adalah 30 hari.  

   ![re-engagement_window.png](https://files.readme.io/6f589562cd6248697ffa8d5ebb4a72e2fdad118df6abf517e43b4fa23c3332ec-30354101914385.png)

Pelajari lebih lanjut tentang SSOT <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide">Atribusi penargetan ulang AppsFlyer</Anchor>.

Pelajari lebih lanjut tentang SSOT Pelajari lebih banyak tentang <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns#deep-linking-dengan-srn">pengguna *deep linking* dari SRN, seperti Meta ads</Anchor>.

</Accordion>

<div id="advanced_data_sharing" />

<Accordion title="Berbagi data tingkat lanjutan">

Saat **Berbagi data tingkat lanjut** diaktifkan aktif, Meta menerima balasan dan peristiwa dengan tingkat perangkat pengidentifikasi untuk semua perangkat, termasuk perangkat yang belum menyediakan ID Iklan (IDFA) mereka. Selain itu, ketika **Berbagi Data Tingkat Lanjut** diaktifkan, peristiwa ini mungkin disebabkan oleh AppsFlyer. Saat dimatikan, hanya postback dan acara dari perangkat dengan IDFA dikirim dan diatribusikan.

Metode ini dapat digunakan untuk opt-out tunggal dan ganda Perangkat: Acara akan dibatasi hingga klik terakhir atribusi, dengan jendela atribusi maksimum 24 jam.

Catatan: Tersedia secara bertahap untuk semua akun pada tanggal 14 Oktober 2024

</Accordion>

<div id="comply-with-california-consumer-privacy-act-ccpa" />

<Accordion title="Mematuhi Undang-Undang Privasi Konsumen California ( California Consumer Privacy Act - CCPA)">

Mematuhi peraturan privasi CCPA membatasi data yang berasal dari pengguna iklan Meta yang berbasis di California, USA.

**Untuk memungkinkan kepatuhan terhadap CCPA:** Nyalakan **Batasi penggunaan informasi pribadi pengguna oleh iklan Meta (CCPA)** Di tab Integrasi:

Pelajari lebih lanjut tentang SSOT <Anchor target="_blank" href="/marketers/id/docs/send-opendsr-api-requests">undang-undang perlindungan data</Anchor>.

</Accordion>

<div id="ad-revenue-recording" />

<Accordion title="Catatan Pendapatan Iklan">

![meta_ads_ad_revenue.png](https://files.readme.io/5c27f2adf0e4515a7ad0efac4776eb296874273e2af71e14c9be8bd65a983757-30354101917201.png)

Jika aplikasi Anda menggunakan Pendapatan Iklan Meta Audience Network untuk monetisasi iklan, Anda dapat mencatat pendapatan Anda dari iklan Meta di AppsFlyer. Ini, dengan atau tanpa data pendapatan pembelian dalam aplikasi, memberi Anda **gambaran lengkap tentang pendapatan pengguna Anda.**

<div id="record-meta-audience-network-ad-revenue" />

#### Catat Pendapatan Iklan Jaringan Audiens Meta

1. Pada tab **Pendapatan Iklan** dan Aktifkan Dapatkan data pendapatan iklan.
2. Pilih jenis data pendapatan iklan yang dikumpulkan yang ingin Anda terima: **Pendapatan yang Diatribusikan**: dan/atau **pendapatan monetisasi agregat**:
   * **Pendapatan yang Diatribusikan**: Pendapatan berdasarkan akuisisi pengguna Sumber  
      Mengatur **Sumber Peristiwa**, yang merupakan acara yang mewakili model pendapatan iklan yang terbaik jalan. Misalnya, jika pendapatan Anda adalah berdasarkan tayangan, direkomendasikan untuk mengirim AppsFlyer sebuah acara yang dilihat iklan. Acara terbaik dapat dikonfigurasi untuk setiap platform monetisasi secara terpisah. Namun demikian, Anda juga dapat menggunakan fitur Event IN dalam hal ini, pendapatan iklan diatribusikan untuk setiap aplikasi yang dibuka oleh pengguna.
   * **Pendapatan monetisasi gabungan**: Pendapatan berdasarkan sumber iklan.
3. ***Event* Pendapatan Iklan** ditampilkan. Ini adalah bidang hanya-baca yang menampilkan iklan baru peristiwa pendapatan yang disebut [peristiwa sumber]\_monetisasi (misalnya, Ad\_Watched\_Monetized seperti yang ditampilkan di atas). Acara pendapatan iklan disajikan dalam dasbor sebagai acara tambahan.
4. Klik **Hubungkan ke iklan Meta** untuk mengaktifkan pengumpulan Meta Audience Network Pendapatan Iklan pada iklan Meta. Masuk dengan Meta Anda kredensial iklan untuk mengotorisasi Meta Audience Network Pendapatan Iklan
5. Masuk ke bagian Masukkan **ID Aplikasi Jaringan Audiens ([ID Aplikasi Facebook](/docs/meta-ads-integration-setup#id-aplikasi-facebook))**. Dapatkan ini dari Jaringan Audiens Meta.
   * Dapatkan ID Aplikasi Facebook
   * Salin ID ke **ID Aplikasi Jaringan Audiens** bidang di AppsFlyer.
6. Klik **Simpan pendapatan iklan**.

</Accordion>

<div id="permissions" />

<Accordion title="Hak Akses">

Mengaktifkan iklan Meta untuk melakukan berbagai tindakan dan untuk mengakses data Anda sesuai dengan izin yang tersedia.

Pelajari lebih lanjut tentang SSOT <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#permissions-tab">memberikan izin kepada mitra terintegrasi.</Anchor>

</Accordion>

</Accordion>

<div id="aggregate-event-measurement-aem-for-ios" />

## Pengukuran Event Gabungan (AEM) untuk iOS

<Anchor target="_blank" href="/marketers/id/docs/meta-ads-aggregate-event-measurement-aem-for-ios">AppsFlyer mendukung Pengukuran Event Gabungan Meta ads (AEM). Solusi ini membantu mengoptimalkan konversi iOS dan *in-app event* sekaligus mengatribusikan interaksi ulang iOS pada Meta ads.</Anchor>

<div id="meta-ads-integration-troubleshooting" />

## Pemecahan masalah integrasi Meta ads

Jika Anda telah menyelesaikan integrasi dasar dan belum melihat hasil dari Meta ads di *dashboard* AppsFlyer, pastikan terlebih dahulu bahwa Anda telah memperoleh penginstalan baru dari Meta ads sejak integrasi.

Jika Anda sudah mencobanya, silakan baca ulasan penyebab utama di bawah ini untuk menyelesaikan masalah tersebut:

<div id="no-idfa-collection" />

<Accordion title="Tidak ada pengumpulan IDFA">

Sebagaimana dinyatakan dalam Panduan Integrasi SDK - iOS, Anda harus menambahkan AdSupport.framework ke proyek Anda agar pengumpulan IDFA dapat dilakukan. Periksa laporan Data Lengkap Penginstalan untuk melihat apakah kolom IDFA benar-benar kosong atau tidak. Disarankan untuk mengaktifkan aplikasi Anda untuk mengumpulkan IDFA dalam hal aplikasi iOS dan GAID untuk aplikasi Android.  
Mulai iOS 14.5, Anda harus menampilkan *prompt* ATT Apple dan mendapatkan persetujuan pengguna sebelum Anda dapat mengumpulkan IDFA.

**Catatan:** Atribusi SKAdNetwork tidak terpengaruh oleh ketersediaan IDFA. Namun, pastikan Anda sudah mengaktifkan tombol Kampanye iOS 14 di Meta ads saat mengatur kampanye iOS 14.

</Accordion>

<div id="wrong-facebook-app-id" />

<Accordion title="ID Aplikasi Facebook Salah">

ID Aplikasi Facebook dikonfigurasikan secara kurang tepat di AppsFlyer.  
Pastikan bahwa ID aplikasi sudah benar dan cocok dengan nilai di *dashboard* Meta ads.  

Catatan - Anda juga dapat menggunakan <Anchor target="_blank" href="https://developers.facebook.com/tools/explorer/?method=GET&path=&version=v6.0">API Grafik Facebook</Anchor> untuk memvalidasi ID Aplikasi Facebook Anda.

</Accordion>

<div id="app-status-on-meta-ads" />

<Accordion title="Status aplikasi di Meta ads">

Aplikasi harus ditentukan di Meta ads sebagai **Langsung (*Live*)** daripada **Dalam pengembangan** agar atribusi berfungsi.

![fb-app-status.png](https://files.readme.io/b982355eb0d3d858988866673d3f9ee4f081c43042221d11ebfb93afe05c36a4-30354101922577.png)

</Accordion>

<div id="wrong-type-of-meta-ads-campaign" />

<Accordion title="Jenis kampanye Meta ads yang salah">

Pastikan kampanye Meta ads adalah **Iklan penginstalan aplikasi seluler** atau **Interaksi Aplikasi Seluler**. Untuk tujuan kampanye lainnya (misalnya, Klik Tautan (*Link Click*) untuk halaman arahan), untuk mengukur penginstalan aplikasi seluler, pemasang iklan harus memeriksa opsi pencatatan *Event* Aplikasi saat menentukan kampanye Meta ads.

</Accordion>

<div id="meta-ads-app-install" />

<Accordion title="Penginstalan aplikasi Meta ads">

Ketika mengatur kampanye penginstalan aplikasi Meta ads, Anda dapat memilih aplikasi dari daftar tarik-turun atau merekatkan seluruh URL toko ke aplikasi. Walaupun keduanya bekerja untuk Anda di Meta ads, metode kedua gagal untuk atribusi AppsFlyer.

Pengaturan benar - atribusi berfungsi.

<Image alt="fb-app-install.png" src="https://files.readme.io/5cb735144128035d752281f7d94e2015478c62049a2e96fc5a42400513f7fad3-30354101926033.png" width="496px" />

Pengaturan salah - atribusi gagal.

![fb-app-incorrect_setup.png](https://files.readme.io/77d508b62d5445cac071262cb35e4a89a6dfa5be439325254c0b8f6c5f51606c-30354145644561.png)

</Accordion>

## Pembaruan Meta ads

> 🚧 **Penting!**
>
> Mulai 29 Oktober 2021, hanya laporan gabungan dari Meta ads (iklan Meta) yang tersedia bagi pemasang iklan. Ini termasuk penginstalan dan *in-app event*. Perubahan ini berlaku untuk semua pemasang iklan, sistem operasi, dan MMP. Ini terkait data tingkat perangkat untuk semua pengguna iOS dan Android, apa pun status izin ATT atau personalisasi iklan.
> Data lengkap untuk penginstalan dan *in-app event* yang diambil sebelum perubahan (29 Oktober 2021) tetap tersedia.
> Perhatikan bahwa data tingkat pengguna bisa didapatkan melalui Google *Install Referrer*.
> Lihat <Anchor target="_blank" href="/marketers/id/docs/bulletin-action-required-get-meta-ads-raw-data-using-google-install-referrer">buletin beritauntuk</Anchor> informasi selengkapnya.

<div id="ios-14-updates-relating-to-meta-ads" />

### Pembaruan iOS 14 terkait Meta ads

AppsFlyer mengonfirmasi bahwa integrasi MMP kami dengan Meta ads selalu menerapkan tanda *Pengukuran Efektivitas Iklan (Advertiser Tracking) Diaktifkan*. Artinya, Anda tidak perlu melakukan tindakan apa pun di AppsFlyer. Informasi ini diberikan sesuai dengan daftar periksa iOS 14 panduan aplikasi Meta ads untuk Februari 2021.

<div id="see-also-1" />

> 📄 **Lihat juga**
>
> * Untuk pertimbangan terkait iOS 14, lihat <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-interoperation-with-meta-ads">Interoperasi SKAN Meta ads</Anchor>
> * <Anchor target="_blank" href="/marketers/id/docs/configuring-meta-campaign-management-partners">Konfigurasi mitra manajemen kampanye Meta</Anchor> (<Anchor target="_blank" href="/marketers/id/docs/bidalgo-meta-campaign-management-partner-configuration">Bidalgo</Anchor> / <Anchor target="_blank" href="/marketers/id/docs/kenshoo-meta-campaign-management-partner-configuration">Kenshoo</Anchor> / <Anchor target="_blank" href="/marketers/id/docs/adquant-meta-campaign-management-partner-configuration">Adquant</Anchor> / <Anchor target="_blank" href="/marketers/id/docs/webpals-mobile-meta-campaign-management-partner-configuration">Webpals</Anchor>)

<div data-zendesk-anchors="facebook-ads-setup-guide=panduan-pengaturan-meta-ads 01H7YJVNMSZ4WG4HWBZF648HZN=panduan-pengaturan-meta-ads facebook-app-id=id-aplikasi-facebook 01H7YJVNMTP8PP2S88Q70E082G=id-aplikasi-facebook basic-facebook-attribution-setup=pengaturan-atribusi-meta-ads-dasar 01H7YJVNMTFW076FAJZGJWT4R9=pengaturan-atribusi-meta-ads-dasar advanced-facebook-attribution-setup=pengaturan-atribusi-meta-ads-lanjutan 01H7YJVNMTHF800PD5CEWPFS49=pengaturan-atribusi-meta-ads-lanjutan 01H7YJVNMTP2CA09QPEQ4DV37C=userlevel-data meta-ads-restricted-attribution-data=meta-ads-membatasi-data-atribusi h_01HNW0B77CQ4HS6ERHBD8YV28E=meta-ads-membatasi-data-atribusi getting-userlevel-data-for-android-installs=mendapatkan-data-tingkat-pengguna-untuk-penginstalan-android-dan-in-app-event 01H7YJVNMTYJV5H1FSM5HBD3N7=mendapatkan-data-tingkat-pengguna-untuk-penginstalan-android-dan-in-app-event 01H7YJVNMTAQKG7YDS72125HFP=catatan meta-install-referrer%E2%80%94faq=meta-install-referrerfaq h_01HQR6QZKDEWXXMGFXXMG2VZ7F=meta-install-referrerfaq encrypted-data-from-the-referrer=data-terenkripsi-dari-google-play-referrer-api-atau-meta-install-referrer 01H7YJVNMTZGQFEGJD9QEEVZHR=data-terenkripsi-dari-google-play-referrer-api-atau-meta-install-referrer 01H7YJVNMTBN9RJ6Q7TJ1AJ0XX=cost-clicks-and-impressions 01H7YJVNMTGRBQG54DVMJDHDKS=catatan-1 cost-data-sync-status=status-sinkronisasi-data-biaya 01H7YJVNMTRQAYG7TY29AX4MZS=status-sinkronisasi-data-biaya 01H7YJVNMTNRREKWY96CK9JJKV=inapp-event-mapping 01H7YJVNMT2DRVR26F8CDDTWHP=catatan-2 01H7YJVNMV5AZ9G2KCKEFF1CSV=retargeting-attribution 01H7YJVNMVSA4Y33MW6Q8Y777Y=advanced_data_sharing 01H7YJVNMVWRG10SZY1B33H5EA=ad-revenue-recording record-meta-audience-network-ad-revenue=catat-pendapatan-iklan-jaringan-audiens-meta 01H7YJVNMV1TTHKMMX4TFB2BF3=catat-pendapatan-iklan-jaringan-audiens-meta 01H7YJVNMVMW5BXWEP8BPX4D7E=permissions aggregate-event-measurement-aem-for-ios=pengukuran-event-gabungan-aem-untuk-ios 01H7YJVNMVGFYMHE5FACTD9NS0=pengukuran-event-gabungan-aem-untuk-ios meta-ads-integration-troubleshooting=pemecahan-masalah-integrasi-meta-ads 01H7YJVNMVCAQ6ETKBGCAM31B9=pemecahan-masalah-integrasi-meta-ads 01H7YJVNMV3YRF59RX87TJCT8D=no-idfa-collection 01H7YJVNMVHCYVWKDW5WWPX1A5=wrong-facebook-app-id 01H7YJVNMVE9QJAXQBD4P14C88=app-status-on-meta-ads 01H7YJVNMVBRVTT9HH7KM8P33B=wrong-type-of-meta-ads-campaign 01H7YJVNMV4G3VP40E6VFD7SJD=meta-ads-app-install facebook-ads-updates=pembaruan-meta-ads 01H7YJVNMV5MQX81Z9NP3X5KJM=pembaruan-meta-ads 01H7YJVNMVS2A95Z20R1ENQYPR=penting ios-14-updates-relating-to-facebook=pembaruan-ios-14-terkait-meta-ads 01H7YJVNMVQP5PR6XDHTCPXVDC=pembaruan-ios-14-terkait-meta-ads h_01HDP0Y4CZBZEK5VZ6FG3T31JB=lihat-juga" />
