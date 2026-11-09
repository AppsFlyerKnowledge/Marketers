---
title: Panduan solusi SKAdNetwork (SKAN)
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - SKAD
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-07-25T21:19:42Z'
  edited_at: '2023-11-03T12:15:56Z'
  id: 360011420698
  locale: id
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/id/articles/360011420698
---
> **Sekilas**: Mengatribusikan penginstalan aplikasi menggunakan SKAN.

<Image align="center" alt="5754" src="https://files.readme.io/a970d7b0e8da300ded2138f941bf2e891f32d396c8500292534992a4b4449d71-30757780264337.png" />

## SKAN

SKAdNetwork (SKAN), bagian dari Apple iOS, memungkinkan pengiklan mengukur kinerja kampanye sekaligus menjaga privasi pengguna.. SKAN beroperasi tanpa IDFA atau ID iklan lainnya. SKAN berfungsi tanpa perlu persetujuan ATT.

<div id="tip" />

> 👍 **Tips**
>
> * Mulai iOS 15, kami menyarankan agar Anda mengirim <Anchor target="_blank" href="/marketers/id/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">salinan postback SKAN</Anchor> ke AppsFlyer. Melakukan hal tersebut memungkinkan AppsFlyer untuk memverifikasi bahwa Nilai Konversi di postback belum dimanipulasi.
> * Mau mengetahui lebih banyak tentang solusi SKAN AppsFlyer? Lihat kursus singkat, informatif <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7810/play/18638/ios14-and-skadnetwork-part-1">di Portal Pembelajaran AppsFlyer</Anchor>.

**Definisi**

* <Anchor target="_blank" href="/marketers/id/docs/sdk-integration-overview">SDK</Anchor>: Versi terbaru dari AppsFlyer iOS SDK terintegrasi dalam sebuah aplikasi.
* **Periode waktu pengukuran SKAN**: Relevan untuk SKAN 4+. Ada 3 periode waktu (jendela) saat aktivitas setelah penginstalan pengguna diukur:
  * Jendela 1: 1-2 hari
  * Jendela 2: 3-7 hari
  * Jendela 3: 8-35 hari
* **Nilai Konversi (Conversion Value - CV)**: Pengukuran kualitas pengguna dilaporkan di postback yang dikirimkan oleh iOS di akhir jendela SKAN 4 atau untuk SKAN 3 dan di bawahnya pada akhir Jendela Aktivitas. SDK AppsFlyer mengatur CV untuk Anda. Namun, jika Anda ingin mengatur CV menggunakan <Anchor target="_blank" href="/marketers/id/docs/skan-cv-decode-map-your-cv-to-events">Decode</Anchor> untuk mengunggah file pemetaan CV Anda.
  * Untuk SKAN 4+, ada nilai konversi halus dan kasar.
* **Studio Konversi**: Solusi AppsFlyer untuk memetakan Nilai Konversi (CV) infrastruktur ke event
* **Solusi:** SDK, Infrastruktur, Studio Konversi, dan platform AppsFlyer bekerja sama. Solusi AppsFlyer SKAN memberi pemasang iklan dan jaringan iklan dengan data LTV melalui analitik dashboard, laporan, dan postback.
* **Jendela Aktivitas:** Relevan untuk SKAN 3 dan di bawahnya. Memiliki durasi yang sudah diatur, default-nya 24 jam, dimulai dengan aplikasi pertama yang dibuka. Jika Anda menggunakan SKAN 4+ tetapi perangkat pengguna atau jaringan iklan belum mendukung SKAN 4, Jendela Aktivitas adalah 48 jam.

Artikel ini menjelaskan karakteristik yang relevan dari infrastruktur dan solusinya. Untuk menyiapkan pengukuran, lihat <Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.

<div id="about-apple-skan" />

<Accordion title="Tentang Apple SKAN">

| Karakteristik | Deskripsi |
| --- | --- |
| Prasyarat | Untuk mengaktifkan penggunaan SKAN di aplikasi:<ul><li>Aplikasi pengiklan (aplikasi Anda) artinya aplikasi yang diiklankan menerapkan SDK AppsFlyer untuk mengatur CV. Atau, Anda dapat mengatur CV menggunakan <Anchor target="_blank" href="/marketers/id/docs/skan-cv-decode-map-your-cv-to-events">Mode Decode</Anchor>.</li><li>Aplikasi penayang (aplikasi yang menampilkan iklan): harus <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app">mengonfigurasi aplikasi sumber</Anchor>.</li><li><Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/registering_an_ad_network">Jaringan iklan harus terdaftar ke Apple</Anchor></li></ul> |
| Didukung | <ul><li>Versi SKAdNetwork yang didukung bergantung pada versi iOS:<ul><li>iOS 11-13: V1 (hanya menginstal tanpa CV)</li><li>iOS 14-14.5: V2+ (memiliki CV)</li><li>iOS 14.6-16: V3 (memiliki CV)</li><li>iOS 16.1+: V4+ (memiliki CV untuk 3 periode waktu, dan nilai halus dan kasar)</li></ul></li><li>Atribusi aplikasi-ke-aplikasi</li></ul> |
| Batasan | <ul><li>Iklan Penelusuran Apple tidak didukung</li><li>Web seluler tidak didukung</li><li>Hingga SKAN, 4 penomoran ID kampanye <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skstoreproductparameteradnetworkcampaignidentifier">dibatasi antara 1-100</Anchor>; berarti 100 nilai unik per jaringan iklan per aplikasi. Jaringan iklan memberi AppsFlyer ID dan nama kampanye mereka. Ini ditunjukkan pada dasbor dan laporan AppsFlyer.</li><li>Dari SKAN 4, pengenal sumber adalah dari 1-10.000.</li><li>Penginstalan organik: SKAN tidak mendukung penginstalan organik.</li><li>Interaksi ulang</li></ul> |
| Prinsip Atribusi SKAN | <ul><li>Atribusi SKAN menggunakan <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions">model atribusiberikut</Anchor><ul><li>Pengguna mengklik iklan, dalam waktu 30 hari menginstal (mengunduh aplikasi), dan setelah itu dalam 60 hari, membuka aplikasi untuk pertama kalinya.</li><li>Pengguna melihat iklan, dalam waktu 24 jam menginstal (mengunduh) aplikasi, dan setelah itu dalam 60 hari, membuka aplikasi untuk pertama kalinya.</li><li>Mulai SKAdNetwork V2.2, atribusi klik-tayang lebih diprioritaskan daripada atribusi lihat-tayang. Versi SKAN bergantung pada versi iOS.</li><li>iOS mengirimkan postback ke jaringan iklan yang diatribusikan. Mulai iOS 15, pengiklan dapat mengirim salinan postback langsung ke AppsFlyer.</li></ul></li></ul> |
| Anonimitas Crowd | Apple mengirimkan beberapa postback dengan data terbatas untuk melindungi privasi pengguna di malam hari. Menurut Apple, postback tidak akan menyertakan CV halus atau kasar, atau ID aplikasi sumber atau pengidentifikasi sumber lengkap jika hal itu melanggar batas tingkat privasi Apple. <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows">Pelajari lebih lanjut</Anchor> |

</Accordion>

<div id="appsflyer-skan-solution" />

## Solusi AppsFlyer SKAN

AppsFlyer memberikan hasil atribusi iOS teragregasi menggunakan postback SKAN dari iOS. Postback ini dikirim oleh iOS ke jaringan iklan yang kemudian meneruskannya ke AppsFlyer. Postback berisi catatan atribusi anonim yang diperkaya dengan nilai konversi (CV) yang ditetapkan oleh pemasang iklan. CV adalah ukuran kualitas pengguna selama periode waktu setelah penginstalan awal.

Solusi SKAN AppsFlyer memberi pemasang iklan:

* Data SKAN di dashboard dan laporan yang diperoleh dengan menggabungkan postback dari semua jaringan iklan yang diperkaya dengan titik data lain seperti biaya.
* Kemampuan untuk mengontrol, melalui AppsFlyer Conversion Studio, apa yang diukur oleh CV tanpa perlu melakukan perubahan pada kode aplikasi. CV dapat digunakan untuk mengukur pendapatan, interaksi, atau event konversi.

<div id="principles-and-flow" />

<Accordion title="Prinsip dan alur">

<div id="skan-attribution-flow" />

#### **Alur atribusi SKAN**

<Image align="center" alt="SKAN_flow_-_Affinity_diagram_2.png" src="https://files.readme.io/2e29f01cf9cf3689777bbd42044e42c0b9f1d4fb719ed75413d29dd84489686d-13112278947601.png" />

1. Pemasang iklan menetapkan pengaturan pengukuran SKAN di AppsFlyer Conversion Studio.
2. 2. Pengguna membuka aplikasi untuk pertama kalinya.
3. Selama setiap periode waktu, AppsFlyer menetapkan CV berdasarkan tindakan pengguna dan skema CV yang ditentukan.
4. Setelah periode waktu ditutup, iOS mengirimkan postback ke jaringan iklan dan salinan postback ke AppsFlyer. Postback tiba dengan beberapa penundaan:
   * Untuk periode waktu pengukuran SKAN 4 1: 24-48 jam
   * Untuk periode waktu pengukuran SKAN 4 2-3: 24-144 jam
   * Untuk SKAN 3: 24-48 jam setelah kenaikan nilai CV terbaru.
5. Salinan postback yang dikirim langsung dari perangkat iOS ke AppsFlyer diteruskan ke titik akhir yang ditentukan pemasang iklan. Lihat <Anchor target="_blank" href="/marketers/id/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">mengirim salinan postback SKAN ke AppsFlyer.</Anchor>
6. Jaringan iklan meneruskan postback yang diperkaya ke AppsFlyer atau SRN mengomunikasikan data postback melalui API.
7. 6. AppsFlyer memvalidasi dan menyandikan CV. Data yang disandikan dicatat dan diatribusikan sebelum tersedia di AppsFlyer melalui dashboard, laporan, dan API.

Untuk mengatasi keterbatasan fungsional dan struktural infrastruktur SKAdNetwork, Solusi SKAN Appsflyer mempertimbangkan karakteristik dalam tabel berikut.

| Karakteristik | Deskripsi |
| --- | --- |
| <span id="data-collection"></span>Pengumpulan data | <ul><li>Untuk pengiklan, postback SKAdNetwork dikumpulkan dari beberapa jaringan iklan.</li><li>Pengiklan tidak perlu berintegrasi satu per satu dengan setiap jaringan iklan—tugas yang rumit dan membosankan.</li></ul> |
| <span id="data-validation"></span>Validasi data | <ul><li>Memastikan postback ditandatangani oleh Apple; ini mengurangi kemungkinan manipulasi postback.</li><li>Menggunakan bidang ID transaksi untuk memvalidasi bahwa postback tersebut unik.</li></ul> |
| <span id="data-enrichment"></span>Memperkaya data | <ul><li>Memperkaya data postback SKAdNetwork dengan titik data lainnya untuk memberikan analisis ROI yang lengkap. Misalnya, nama kampanye yang disediakan oleh jaringan iklan, dan sebagainya.</li><li>Poin data mencakup tayangan, klik, biaya, dan lainnya.</li></ul> |
| <span id="data-delivery"></span>Pengiriman data | Data SKAdNetwork yang diperkaya tersedia menggunakan berikut ini:<ul><li><Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">Dashboard solusi SKAdNetwork</Anchor></li><li>[Laporan yang dapat diunduh](/docs/skadnetwork-skan-solution-guide#reporting-options)</li></ul> |
| <span id="seamless-integration"></span>Integrasi yang mulus | <ul><li>Enkapsulasi penuh memungkinkan pengiklan tak perlu melakukan apa pun melalui halaman pengaturan aplikasi.</li><li>Tidak diperlukan penyandian. Aplikasi ini memerlukan versi SDK terbaru.</li><li>Termasuk dukungan untuk perubahan yang diharapkan oleh Apple dalam infrastruktur SKAdNetwork.</li></ul> |
| <span id="agility"></span>Fitur | Pemasang iklan dapat mengubah konfigurasi pengukuran sesuai kebutuhan di dasbor. |

</Accordion>

<div id="conversion-studio" />

<Accordion title="Conversion Studio">

<Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio">Conversion Studio</Anchor> AppsFlyer merupakan inti dari solusi SKAN. Ini memberi Anda fleksibilitas maksimum untuk menghitung setiap bit nilai konversi. Anda menentukan dengan tepat data pengukuran apa yang harus dikodekan dalam CV—termasuk aktivitas apa dan untuk berapa lama mengukur selama periode pasca-penginstalan. Terdapat beberapa mode pengukuran yang dapat Anda gunakan untuk mengonfigurasi pengaturan CV Anda.

| Jenis | Mode pengukuran | Deskripsi | Jendela aktivitas |
| --- | --- | --- | --- |
| Fleksibel | SKAN 4.0<br /><br />[Praktik terbaik] | Tetapkan kombinasi pendapatan, konversi (in-app event), dan pengukuran interaksi selama 3 jendela pengukuran yang dapat dikonfigurasi. | <ul><li>Jendela 1: 1-2 hari</li><li>Jendela 2: 3-7 hari</li><li>Jendela 3: 8-35 hari</li></ul> |
| Fleksibel | <Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio#custom">Kustom</Anchor> | Tetapkan kombinasi pendapatan, konversi (in-app event), dan pengukuran interaksi selama jendela aktivitas yang dapat dikonfigurasi. | 12 j-63 hari |
| Tetap | Pendapatan<br /><br />[Default]<br /><br />[Legasi] | Ukur pendapatan menggunakan salah satu rentang berikut:<ul><li>$1-$630 dalam kelipatan $10</li><li>$1-$63 dalam kelipatan $1</li><li>$0.01-$0.63 dalam kelipatan $0.01</li></ul> | 24 j |
| Tetap | Konversi<br /><br />[Legasi] | Pilih 1-6 in-app event. | 24 j |
| Tetap | Interaksi<br /><br />[Legasi] | Berapa kali pengguna melakukan suatu event | 24 j |
| Fleksibel | <Anchor target="_blank" href="/marketers/id/docs/skan-cv-decode-map-your-cv-to-events">Decode</Anchor> | <ul><li>Buat CV Anda sendiri untuk pemetaan event dan atur CV di aplikasi sendiri. Gunakan opsi ini jika Anda tidak dapat mengintegrasikan AppsFlyer SDK ke aplikasi Anda. Untuk menggunakan Decode, buka **SKAN Conversion Studio,** klik opsi (⋮), pilih **Upload custom decode mapping file**.</li><li>SKAN 4 tidak didukung</li></ul> | 12-1512j (63 hari) |

</Accordion>

<div id="additional-skadnetwork-information" />

## Informasi SKAdNetwork tambahan

<div id="reporting-options" />

<Accordion title="Opsi pelaporan">

Laporan SKAdNetwork tidak berisi pengenal tingkat pengguna.

| Nama laporan | Jenis | Diperkaya oleh AppsFlyer | Metode Pengiriman | Fitur premium |
| --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/id/docs/skan-aggregated-performance-report-api">Laporan kinerja teragregasi SKAN.</Anchor><br /><br />Kumpulan dari penginstalan, in-app event, dan pendapatan. Datanya mirip dengan yang ditemukan di dasbor SKAN. | Dikumpulkan menggunakan tanggal kedatangan penginstalan atau postback | Ya | API | Tidak |
| <Anchor target="_blank" href="/marketers/id/docs/skan-aggregated-postback-arrival-date-api">Laporan postback gabungan SKAN</Anchor>.<br /><br />Postback SKAN dikumpulkan ke tingkat yang paling terperinci. | Kumpulan postback menggunakan tanggal kedatangan postback | Tidak | API | Tidak |
| <Anchor target="_blank" href="/marketers/id/docs/skan-raw-data-reports#raw-data-report-types">Laporan data lengkap SKAN (tingkat baris) melalui Data Locker</Anchor> (dengan contoh).<br /><br />Laporan yang tersedia:<ul><li>Postback yang dikirim oleh iOS dengan memperkaya data yang disediakan oleh mitra jaringan iklan</li><li>Install</li><li>Mengunduh ulang</li><li>In-App Event</li><li>Dimensi iklan SRN</li></ul> |  | Ya | Data Locker | Ya. Data lengkap diperlukan. Tidak diwajibkan berlangganan Data Locker. |
| Data SKAN melalui Push API |  | Ya | Push API | Ya |

</Accordion>

<div id="skadnetwork-solution-implementation-checklist" />

<Accordion title="Daftar periksa implementasi solusi SKAdNetwork">

| No. | Tindakan | Deskripsi | Tanggung jawab |
| --- | --- | --- | --- |
| 1 | Persiapkan | <ul><li>Baca <Anchor target="_blank" href="https://www.appsflyer.com/resources/prepare-your-app-ios14/">Panduan solusi SKAdNetwork</Anchor></li><li>Bacaan tambahan: <Anchor target="_blank" href="https://www.appsflyer.com/resources/prepare-your-app-ios14/">Siapkan aplikasi Anda untuk iOS 14</Anchor></li></ul> | Pemasar, Pengembang |
| 2 | Konfigurasikan | Di AppsFlyer, konfigurasikan solusi SKAdNetwork di <Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio">Studio Konversi SKAN</Anchor>. | Pemasar |
| 3 | Siapkan aplikasinya | Migrasikan aplikasi ke AppsFlyer <Anchor target="_blank" href="/marketers/id/docs/sdk-integration-overview">V6 SDK</Anchor><ul><li>Tidak diperlukan perubahan pada logika aplikasi atau kode aplikasi.</li><li>Solusi SKAN Appsflyer mengandalkan in-app event untuk mengatur in-app event CV Send dengan cara biasa. Tidak diperlukan pengujian khusus solusi SKAN.</li><li>Kirim aplikasi ke App Store</li><li>Tidak diperlukan pendaftaran atau proses SKAdNetwork di app store.</li></ul> | Pengembang |
| 4 | Integrasi mitra | Mitra jaringan iklan harus berintegrasi dengan AppsFlyer menggunakan integrasi SKAdNetwork. Perhatikan! Simulasi AppsFlyer SKAdNetwork berisi data semua mitra Anda, apa pun status integrasi mereka saat ini. Ini tidak akan terjadi pada data langsung yang dilaporkan oleh postback SKAdNetwork.<br /><br />Terkait mitra yang menjalankan kampanye Anda, lengkapi hal-hal berikut seperti yang diperlukan:<br /><br />**Non-SRN**:<ol><li>Verifikasi bahwa mitra memiliki <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#c">lencana kemampuan SKAdNetwork AppsFlyer</Anchor> dan bahwa di UI mitra, pelaporan kampanye SKAdNetwork diaktifkan.</li><li>Verifikasi bahwa [nama in-app event Anda dipetakan](#sending-postbacks-to-integrated-partners) ke nama in-app event mitra.</li></ol>**Meta ads**:<ul><li><Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-interoperation-with-meta-ads">Konfigurasikan interoperasi AppsFlyer SKAdNetwork dengan Meta ads</Anchor></li></ul> | Pemasar |

</Accordion>

<div id="troubleshooting-guide" />

<Accordion title="Panduan penyelesaian masalah">

| Tanda peringatan | Deskripsi |
| --- | --- |
| Dasbor tidak berisi penginstalan non-organik. | <ol><li>Pastikan bahwa **Pengukuran SKAdNetwork** aktif.<ol><li>Buka **Configuration** > **SKAN Conversion Studio.**</li><li>Klik opsi (⋮), periksa pengaturan pengukuran SKAN.</li></ol></li><li>Pastikan bahwa versi SDK Anda adalah 6.2.6+.<ul><li>Untuk melakukan hal tersebut, buka **Integration** > **SDK Information > Users by SDK version.**</li></ul></li><li>Jika Anda menggunakan plugin SDK, pastikan Anda menerapkan versi yang mendukung AppsFlyer SKAdNetwork.</li><li>Pastikan bahwa mitra jaringan iklan Anda terintegrasi dengan AppsFlyer dan mereka meneruskan postback iOS ke AppsFlyer.</li></ol> |
| Dasbor berisi penginstalan non-organik tetapi tidak ada in-app event sama sekali. | <ol><li>Pastikan bahwa versi SDK Anda adalah 6.2.6+.<ul><li>Untuk melakukan hal tersebut, buka **Integration** > **SDK Information > Users by SDK version.**</li></ul></li><li>Jika Anda menggunakan plugin SDK, pastikan Anda menerapkan versi yang mendukung AppsFlyer SKAdNetwork.</li><li>Apakah Anda mengirim event menggunakan S2S? Jika demikian, pastikan bahwa **Rekam in-app event yang dikirim oleh API server-ke-server** aktif.<ol><li>Buka **Configuration** > **SKAN Conversion Studio.**</li><li>**Klik opsi (⋮), pastikan konfigurasi S2S aktif.** Catatan: Dalam mode pengukuran Kustom dan Dekode, pengaturan ini selalu aktif dan tidak dapat diubah.</li></ol></li></ol> |
| Dasbor berisi penginstalan dan beberapa in-app event. Beberapa in-app event tidak ada. | <ol><li>Apakah Anda mengirim event menggunakan S2S? Jika demikian, pastikan bahwa **Rekam in-app event yang dikirim oleh API server-ke-server** aktif.<ol><li>Buka **Configuration** > **SKAN Conversion Studio.**</li><li>**Klik opsi (⋮), pastikan konfigurasi S2S aktif.** Catatan: Dalam mode pengukuran Kustom dan Dekode, pengaturan ini selalu aktif dan tidak dapat diubah.</li></ol></li><li>Periksa <Anchor target="_blank" href="/marketers/id/docs/skan-raw-data-reports#raw-data-report-types">data lengkap postback</Anchor> untuk melihat apakah semua event dilaporkan.</li></ol> |
| Lokasi geo (negara) salah | Data lokasi diambil sebagai berikut:<ul><li>Berdasarkan negara yang terkait dengan kampanye dan dilaporkan ke AppsFlyer oleh jaringan iklan.</li><li>Menggunakan alamat IP perangkat. Mulai iOS 14.6, alamat ini adalah alamat proxy dan tidak benar-benar mewakili geolokasi pengguna.</li></ul> |

</Accordion>

<div id="timing-from-app-install-until-dashboard-and-reports-update" />

<Accordion title="Pengaturan waktu dari penginstalan aplikasi hingga pembaruan dashboard dan laporan">

| Kode | Nama elemen | Deskripsi | Contoh A | Contoh B | Contoh C | Contoh D | Contoh E |
| --- | --- | --- | --- | --- | --- | --- | --- |
| A | Periode waktu pengukuran SKAN 4 1 | <ul><li>Selama periode waktu, CV diatur oleh aplikasi</li><li>0-2 hari</li><li>Periode waktu dapat dikunci sebelum 2 hari di Conversion Studio</li></ul> | - | - | 2 hari | - | - |
| B | Periode waktu pengukuran 2 SKAN 4 | <ul><li>Selama jendela aktif, CV diatur oleh aplikasi.</li><li>3-7 hari</li><li>Periode waktu dapat dikunci sebelum 7 hari di Conversion Studio</li></ul> | - | - | - | 7 hari | - |
| C | Periode waktu pengukuran SKAN 4 3 | <ul><li>Selama jendela aktif, CV diatur oleh aplikasi.</li><li>8-35 hari</li><li>Periode waktu dapat dikunci sebelum 35 hari di Conversion Studio</li></ul> | - | - |  | - | 35 hari |
| D | SKAN 4 jendela pengukuran 1 penundaan postback | 24-48 jam | - | - | 24-48jam | - | - |
| E | Periode waktu pengukuran SKAN 4 penundaan 2-3 | 24-144 jam | - | - | - | 24-144jam | 24-144jam |
| F | Jendela Aktivitas<br /><br />(Tidak relevan untuk SKAN 4) | <ul><li>Selama jendela aktif, CV diatur oleh aplikasi.</li><li>Jendela dimulai saat aplikasi dibuka untuk pertama kalinya.</li><li>Durasi 12 jam - 63 hari.</li></ul> | 24 j | 72j | - | - | - |
| G | Timer SKAdNetwork<br /><br />(Tidak relevan untuk SKAN 4) | <ul><li>Penghitung waktu mundur: 24 jam</li><li>Setiap kali CV meningkat, timer diatur ulang. Ini berarti mulai menghitung mundur dari 24 jam.</li></ul> | 0-24j | 0-24j | - | - | - |
| H | Penundaan acak SKAdNetwork<br /><br />(Tidak relevan untuk SKAN 4) | Waktu tunda postback acak. Hitungan mundur dimulai pada akhir periode yang ditentukan oleh F+G. | 0-24j | 0-24j | - | - | - |
| I | Pemrosesan AppsFlyer | Postback yang diterima pada hari tertentu diproses pada akhir hari UTC mulai pukul 00:01 pada hari berikutnya. Data tersedia 8 jam kemudian. Pemrosesan makna membutuhkan waktu 8-32 jam. Rata-rata waktu tunda 20 jam. Misalnya, postback yang diterima pada hari Senin diproses pada hari Selasa. Dashboard diperbarui pada pukul 08:00 UTC. | 8-32j | 8-32j | 8-32j | 8-32j | 8-32j |
| J | Ringkasan | Total waktu yang diperbolehkan | 32 jam-104 jam | 80-152j | 80-128 jam | 200-344 jam | 872-1016 jam |

</Accordion>

<div id="organic-metrics-in-the-context-of-skadnetwork" />

<Accordion title="Metrik organik dalam konteks SKAdNetwork">

Metrik organik di dasbor SKAdNetwork dihitung menggunakan mekanisme berikut:

* Metrik organik untuk peristiwa dalam aplikasi tidak tersedia jika mode pengukuran yang Anda pilih adalah <Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio#dasar-dasar-skan-conversion-studio">SKAN 4, Kustom, atau Dekode.</Anchor>
* Apple SKAdNetwork mengirimkan postback terkait dengan pengguna yang menginstal setelah berinteraksi dengan sumber media. Ini memberikan metrik non-organik.
* Dasbor atribusi AppsFlyer berisi metrik semua penginstalan, apa pun sumbernya.  Lihat<Anchor target="_blank" href="/marketers/id/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side">lihat atribusi AppsFlyer berdampingan dengan atribusi SKAN</Anchor> .
* Dengan menggunakan data ini, metrik organik dihitung sebagai A-B di mana:
  * A = Total semua pengguna berdasarkan dasbor ikhtisar tradisional
  * B = Pengguna non-organik seperti yang dilaporkan oleh postback SKAdNetwork

**Peringatan terkait dengan Iklan Pencarian Apple** : Penginstalan yang dibawa oleh Iklan Pencarian Apple di dasbor tradisional non-organik. Namun, dalam konteks SKAdNetwork, mereka merupakan bagian dari metrik organik.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Sifat | Catatan |
| --- | --- |
| Akses jaringan iklan | Jaringan iklan disediakan dengan postback |
| Agensi | Tidak didukung. Ini berarti agensi tidak boleh mengaktifkan jaringan iklan yang menjalankan kampanye SKAdNetwork. Agensi! Minta pengiklan untuk mengaktifkan Jaringan iklan, jangan lakukan sendiri. Agensi dapat menunjukkan bahwa mereka membawa pengguna dengan menerapkan <Anchor target="_blank" href="/partners/id/docs/getting-started-agency-onboarding#skadnetwork-agency-campaigns">Pengenal Agensi SKAN</Anchor>. |
| Transparansi agensi | N/A |
| zona waktu | UTC |
| Mata uang | USD |
| Data organik | Berdasarkan data event SDK. Misalnya, metrik penginstalan organik dihitung sebagai berikut: Data semua penginstalan yang dilaporkan oleh SDK dikurangi penginstalan non-organik yang dilaporkan oleh SKAdNetworks. |
| Data non-organik | Berdasarkan postback SKAdNetwork |
| Kesegaran data | Harian |
| Data historis | Tanggal paling awal, ketersediaan iOS 14 (16 September 2020) |
| Akses pengguna | Pengguna akun harus memiliki <Anchor target="_blank" href="/marketers/id/docs/user-management">izin yang diperlukan</Anchor> |
| App clip | App clip diatribusikan ke organik di dasbor SKAdNetwork. Gunakan dasbor Tinjauan untuk melihat sumber media pemanggilan. |

</Accordion>

<div id="skan-integrated-partners" />

## Mitra terintegrasi SKAN

<div id="recording-ad-revenue" />

<Accordion title="Mencatat pendapatan iklan">

Atribusikan pendapatan iklan yang dihasilkan selama periode waktu pengukuran SKAdNetwork ke kampanye yang mendatangkan pengguna. Saat ini, ini terbatas pada pengiklan yang terintegrasi dengan pendapatan iklan tingkat tayangan umum dan Admob melalui SDK.

Untuk mencatat pendapatan iklan di dashboard SKAN Anda:

* Integrasikan <Anchor target="_blank" href="/marketers/id/docs/integrate-the-roi360-ad-revenue-sdk-api">SDK pendapatan iklan tingkat impresi umum</Anchor> ke dalam aplikasi Anda.
* Jika Anda menggunakan mode tetap SKAN Conversion Studio, <Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio#report-events-by-servertoserver-api">aktifkan dukungan server-ke-server SKAdNetwork</Anchor>.

**Catatan**: Lihat dokumentasi <Anchor target="_blank" href="/marketers/id/docs/integrate-the-roi360-ad-revenue-sdk-api">konektor SDK umum</Anchor> untuk informasi tentang sumber iklan yang tersedia untuk mediasi.

</Accordion>

<div id="sending-postbacks-to-integrated-partners" />

<Accordion title="Mengirim postback ke mitra terintegrasi">

AppsFlyer mengirimkan postback mitra terintegrasi yang terkait dengan atribusi SKAN (untuk SKAN 4, postback dikirim hanya untuk jendela 1).

Perhatikan berbagai opsi dan persyaratan dalam tabel berikut

| Perihal | Deskripsi |
| --- | --- |
| <span id="transaction-id-sharing"></span>Berbagi ID transaksi | **Diperlukan tindakan** : Periksa dengan mitra terintegrasi jika mereka memerlukan <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/verifying_an_install_validation_postback">ID transaksi</Anchor> dan konfigurasikan pengaturan yang sesuai.<br /><br />AppsFlyer mengirimkan postback mitra jaringan iklan yang diatribusikan. Artinya postback yang didekodekan, bukan salinan postback SKAdNetwork yang diterima dari iOS. Postback ini berisi data CV yang didekodekan terkait dengan penginstalan dan data in-app event terkait tindakan yang dilakukan oleh pengguna selama Jendela Aktivitas.<br /><br />Karena ID transaksi dapat digunakan untuk membaca kode CV Anda, kami tidak membagikannya tanpa izin Anda.<br /><br />**Berbagi ID transaksi**<br /><br />Pemasang iklan <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#b">mengaktifkan berbagi ID transaksi</Anchor> sebagai berikut: Di AppsFlyer, buka **Konfigurasi** > **Integrasi Aktif** > pilih mitra > **tab Integrasi** > **Berbagi data**. |
| <span id="inapp-event-mapping-verification"></span>Verifikasi pemetaan in-app event | **<span id="1611499069.009700"></span>Diperlukan tindakan** : Anda harus <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#metode-pemetaan">memetakan in-app event</Anchor> ke nama event mitra yang sesuai sehingga mitra dapat mencatat postback dengan benar.<br /><br />Untuk setiap mitra yang menjalankan kampanye SKAdNetwork, verifikasi bahwa in-app event disetel sesuai dengan jenis pengukuran aplikasi yang dipilih.<br /><br />**Untuk memverifikasi dan mengubah pemetaan in-app event mitra**:<ol><li>Di AppsFlyer, Buka **Konfigurasi** > **Integrasi Aktif**.</li><li>Pilih mitra.</li><li>Buka tab **Integration** .</li><li>Verifikasi dan, jika perlu, buat perubahan pengaturan sebagai berikut:<ol><li>Aktifkan **Postback in-app event**.</li><li>Pastikan bahwa in-app event,  **nama event SDK yang** Anda tetapkan dalam pengukuran SKAdNetwork dipetakan ke **pengenal event Mitra** .</li></ol></li><li>Klik **Save integration**.</li></ol> |

</Accordion>

<div id="see-also" />

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/about-att-and-skan">Panduan memulai cepat & Pertanyaan Umum (FAQ) untuk iOS 14, ATT, dan SKAN</Anchor>
> * <Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio">Siapkan pengukuran menggunakan SKAN Conversion Studio (pengaturan SKAdNetwork)</Anchor>
> * <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">Dasbor SKAN AppsFlyer</Anchor>
> * <Anchor target="_blank" href="/marketers/id/docs/skan-integrated-partners-list">Daftar mitra terintegrasi SKAN</Anchor>
> * Interoperasi mitra SKAN yang memerlukan penyiapan di AppsFlyer:
>   * <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-interoperation-with-meta-ads">Iklan Meta</Anchor>
>   * <Anchor target="_blank" href="/marketers/id/docs/get-skan-postback-data-from-google-ads">Google Ads</Anchor>
>   * <Anchor target="_blank" href="/marketers/id/docs/skan-interoperation-with-tiktok-for-business">TikTok untuk Bisnis</Anchor>
>   * <Anchor target="_blank" href="/marketers/id/docs/skan-interoperation-with-snapchat">Snapchat</Anchor>

<div data-zendesk-anchors="01H7Z06Z03AQY25A3E45Z47A9G=skan 01H7Z06Z03CSKH1ZB9RQP6SHA8=tips 01H7Z06Z03MRE6BCSG1AEXN947=about-apple-skan appsflyer-skan-solution=solusi-appsflyer-skan 01H7Z06Z04G479NAKBEA33SGSZ=solusi-appsflyer-skan 01H7Z06Z05CAVK3CR7F5FBKFC5=principles-and-flow skan-attribution-flow=alur-atribusi-skan 01H7Z06Z05EGK5QBDK6G7BJQJK=alur-atribusi-skan 01H7Z06Z053M2H3CJ6SV4VDZPZ=conversion-studio additional-skadnetwork-information=informasi-skadnetwork-tambahan 01H7Z06Z05556NQ35HMR4E2TRY=informasi-skadnetwork-tambahan 01H7Z06Z05G0YB56GDG5E196QM=reporting-options 01H7Z06Z05M3BPSBTCMJ3NHK5D=skadnetwork-solution-implementation-checklist 01H7Z06Z05YF4J0MPMJ40EG7BX=troubleshooting-guide 01H7Z06Z0502NW8KFJ7XRZFWJR=timing-from-app-install-until-dashboard-and-reports-update 01H7Z06Z068462E4QTGTSMNS7H=organic-metrics-in-the-context-of-skadnetwork 01H7Z06Z0615QHCY6JZ4MAMTJ8=traits-and-limitations skadnetwork-integrated-partners=mitra-terintegrasi-skan 01H7Z06Z06KGT6ESN42XTJSK2F=mitra-terintegrasi-skan 01H7Z06Z06NWJQ6W50MCD3P352=recording-ad-revenue 01H7Z06Z06K2ZB949GGTJV6MJP=sending-postbacks-to-integrated-partners h_01HE7TC49KRRX1RVGX1FY7C52T=lihat-juga" />
