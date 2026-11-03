---
title: Panduan mulai cepat &amp; Pertanyaan Umum (FAQ) untuk iOS 14, ATT, dan SKAN
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Agencies
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-08-11T09:19:23Z'
  edited_at: '2024-09-18T17:30:48Z'
  id: 360011890298
  locale: id
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/id/articles/360011890298
---
> **Sekilas**: Mulai iOS 14.5, Apple mengharuskan Anda untuk menerapkan dan mematuhi persyaratan <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency">Transparansi AppTracking</Anchor> (ATT). ATT berarti bahwa *jika aplikasi Anda mengumpulkan data tentang pengguna akhir dan membagikannya dengan perusahaan lain untuk tujuan pelacakan di seluruh aplikasi dan situs web,* Anda harus menggunakan perintah persetujuan ATT dan mendapatkan persetujuan pengguna di aplikasi penerbit dan pemasang iklan. Jika Anda tidak melacak, tidak perlu menampilkan perintah.

![iOS14-consent-pre-ATT-enforcement-6522_Cover-image_917x480.jpg](https://files.readme.io/622b57cf6b6b7ad9472b3d072f44d9b451e82fec6b0c918427e39e9e6700602e-360019478118.jpg)

## Pengukuran atribusi di lingkungan ATT

AppsFlyer menyediakan untuk Anda beberapa metode atribusi yang memberikan Anda berbagai solusi atribusi yang lengkap. Persyaratan persetujuan [ATT](/docs/about-att-and-skan#att-principles) memengaruhi atribusi dalam konteks kampanye aplikasi-ke-aplikasi berbayar. Dengan demikian, pemasang iklan perlu menggunakan campuran solusi atribusi dan pelaporan. 

Dalam kasus kampanye aplikasi-ke-aplikasi berbayar, [SKAN](/docs/about-att-and-skan#skan-solution-principles) memberikan hasil atribusi deterministik. Jenis kampanye lain seperti media yang dimiliki, web-ke-aplikasi, dan Apple Search Ads menggunakan alat atribusi tradisional AppsFlyer. Alat tradisional menyediakan pengukuran LTV jangka panjang, sedangkan SKAN mengukur kinerja pengguna selama postingan pasca-penginstalan yang singkat. 

Singkatnya, untuk mendapatkan gambaran lengkap, gunakan solusi tradisional AppsFlyer dan SKAN karena keduanya saling melengkapi.

Artikel ini memberikan pengantar kepada pemasang iklan tentang SKAN dan ATT. Ini ditujukan untuk pemasang iklan yang akrab dengan platform AppsFlyer.

<div id="skan-solution-principles" />

<Accordion title="Prinsip Solusi SKAN">

AppsFlyer memberikan hasil atribusi iOS teragregasi menggunakan postback SKAN dari iOS. Postback ini dikirim oleh iOS ke jaringan iklan yang kemudian meneruskannya ke AppsFlyer. Postback berisi catatan atribusi anonim yang diperkaya dengan nilai konversi (CV) yang ditetapkan oleh pemasang iklan. CV adalah ukuran kualitas pengguna selama periode waktu setelah penginstalan awal.

<Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide">Solusi SKAN</Anchor> AppsFlyer memberi pemasang iklan:

* Data SKAN di dashboard dan laporan yang diperoleh dengan menggabungkan postback dari semua jaringan iklan yang diperkaya dengan titik data lain seperti biaya.
* Kemampuan untuk mengontrol, melalui AppsFlyer Conversion Studio,apa yang diukur oleh CV tanpa perlu melakukan perubahan pada kode aplikasi. CV dapat digunakan untuk mengukur pendapatan, interaksi, atau event konversi.

**Keterbatasan SKAN**

* **Kampanye:** Tidak mendukung, Apple Search Ads, kampanye promosi silang, dan penginstalan yang dibantu web seluler.
* **Periode pengukuran:** Periode pengukuran efektif dibatasi menjadi beberapa hari.

**Aliran SKAN**

![SKAN_flow_-_Affinity_diagram_2.png](https://files.readme.io/2e29f01cf9cf3689777bbd42044e42c0b9f1d4fb719ed75413d29dd84489686d-13112278947601.png)

1. Pemasang iklan menetapkan pengaturan pengukuran SKAN di AppsFlyer Conversion Studio.
2. 2. Pengguna membuka aplikasi untuk pertama kalinya.
3. Selama setiap periode waktu, AppsFlyer menetapkan CV berdasarkan tindakan pengguna dan skema CV yang ditentukan.
4. Setelah periode waktu ditutup, iOS mengirimkan postback ke jaringan iklan dan salinan postback ke AppsFlyer. Postback tiba dengan beberapa penundaan:
   * Untuk periode waktu pengukuran SKAN 4: 24-48 jam
   * Untuk periode waktu pengukuran SKAN 4 2-3: 24-144 jam
   * Untuk SKAN 3: 24-48 jam setelah peningkatan nilai CV terbaru.
5. Salinan postback yang dikirim langsung dari perangkat iOS ke AppsFlyer diteruskan ke titik akhir yang ditentukan pemasang iklan. Lihat <Anchor target="_blank" href="/marketers/id/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">mengirim salinan postback SKAN ke AppsFlyer.</Anchor>
6. Jaringan iklan meneruskan postback yang diperkaya ke AppsFlyer atau SRN mengomunikasikan data postback dengan API.
7. AppsFlyer memvalidasi dan mendekode CV. Data yang didekodekan dicatat dan diatribusikan sebelum tersedia di AppsFlyer melalui dashboard, laporan, dan API.

</Accordion>

<div id="att-principles" />

<Accordion title="Prinsip ATT">

Perintah ATT memberikan pemasang iklan cara untuk mendapatkan persetujuan pengguna secara eksplisit yang memungkinkan pemasang iklan untuk mengumpulkan dan membagikan data mereka. Mulai iOS 14.5, IDFA hanya tersedia jika pengguna menyetujui melalui perintah tersebut.

Aplikasi penayang dan pemasang iklan menampilkan perintah tersebut. Jika pengguna memberikan persetujuan di kedua aplikasi, itu berarti pengguna setuju untuk *dilacak* dan pemasang iklan diizinkan oleh Apple untuk melacak pengguna di antara aplikasi yang dimiliki oleh perusahaan yang berbeda.

**Mengatur ATT**

ATT diatur ke salah satu nilai yang tercantum dalam tabel berikut. Awalnya, iOS mengatur ATT menjadi tidak ditentukan atau dibatasi.

Pertimbangkan bahwa penggunaan perintah persetujuan untuk mengonversi pengguna dari *tidak ditentukan* ke *diotorisasi* adalah opsional. Tapi, jika Anda tidak menampilkan perintah tersebut, Anda tidak bisa mendapatkan *otorisasi.*

| Nilai ATT | Persetujuan  <br />(IDFA tersedia) | Catatan |
| --- | --- | --- |
| Dibatasi | Tidak | <ul><li>Ditentukan oleh Apple berdasarkan usia pengguna dan kriteria lainnya. Tidak dapat diubah oleh pengguna perangkat.</li><li>Perintah tidak dapat ditampilkan kepada pengguna ini.</li></ul> |
| Tidak ditentukan (hingga iOS 14.4) | Ya | Nilai default |
| Tidak ditentukan<br /><br />(mulai iOS 14.5) | Tidak | Nilai default |
| Ditolak | Tidak | Terjadi jika salah satu dari berikut ini benar:<ul><li>Atur setelah menampilkan perintah</li><li>Pengguna dinonaktifkan *Izinkan Aplikasi untuk Meminta untuk Melacak* (sakelar utama di tingkat perangkat)</li><li>Sebelum menginstal iOS 14 di perangkat, LAT aktif</li></ul> |
| Diotorisasi | Ya | Atur setelah menampilkan perintah |

**Implikasi ATT**

Karena ATT, banyak pengguna tidak akan menyetujui, IDFA tidak akan tersedia, dan pelacakan tidak diizinkan. Akibatnya, pemasang iklan yang hingga iOS 14.5 mengandalkan laporan atribusi tingkat pengguna harus mengalihkan beberapa analisis ke metode dan pelaporan atribusi yang digabungkan. <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model">Model atribusi AppsFlyer</Anchor>.

Data terkait atribusi untuk suatu aplikasi berasal dari sejumlah sumber. Pengidentifikasi yang tersedia dan digunakan oleh masing-masing berbeda. Sebagian besar data ditampilkan menggunakan alat atribusi tradisional. Namun, untuk penginstalan yang diatribusikan menggunakan SKAN, pelaporan dilakukan melalui dashboard SKAN.

</Accordion>

<div id="which-dashboard-has-the-install" />

<Accordion title="Dashboard mana yang memiliki penginstalan?">

Di iOS 14, penginstalan dapat dikaitkan dengan dashboard tradisional dan SKAN. Selain itu, tergantung pada konteks sumber media, penginstalan dapat dikaitkan sebagai organik di satu dashboard dan sebagai non-organik di dashboard lainnya.

</Accordion>

## Pengetahuan penting iOS 14

#### Artikel dan tautan iOS 14 dan SKAN

| Area | Artikel | Minat khusus: FAQ, perbedaan, perbandingan |
| --- | --- | --- |
| SKAN | <Anchor target="_blank" href="/marketers/id/docs/skan-raw-data-reports">Bidang data lengkap SKAN</Anchor> | Data lengkap tambahan bidang SKAN yang mendukung did\_win dan SKAN 3.0 |
| SKAN | <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide">Solusi SKAN</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">Waktu dari penginstalan aplikasi hingga pembaruan dashboard</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide#organic-metrics-in-the-context-of-skadnetwork">Metrik organik dalam konteks SKAN</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#appsflyer-attribution-vs-skan-attribution">Atribusi AppsFlyer versus atribusi SKAN</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#faq-skan-discrepancies">FAQ Perbedaan SKAN</Anchor></li></ul> |
| SKAN | <Anchor target="_blank" href="/marketers/id/docs/skan-interoperation">Interoperabilitas mitra SKAN</Anchor> (bagian artikel) | <Anchor target="_blank" href="/marketers/id/docs/skan-integrated-partners-list">Daftar mitra terintegrasi SKAN</Anchor> |
| SKAN | <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-interoperation-with-meta-ads">Integrasi Meta ads dan SKAN AppsFlyer</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-interoperation-with-meta-ads#troubleshooting-discrepancies-and-faq">Pemecahan masalah dan perbedaan</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-interoperation-with-meta-ads#measurement-and-timing-differences-between-appsflyer-and-facebook">Perbedaan pengukuran dan waktu</Anchor></li></ul> |
| SKAN | Interoperasi Snapchat dan AppsFlyer SKAN | <Anchor target="_blank" href="/marketers/id/docs/skan-interoperation-with-snapchat#discrepancies-guide">Panduan perbedaan</Anchor> |
| Privasi | <Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework">Privasi Tingkat Lanjut Gabungan (Aggregated Advanced Privacy-AAP)</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework#fitur-yang-terpengaruh-aap">Fitur yang terdampak AAP</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework#aap-central-switch">Menonaktifkan dan mengaktifkan AAP</Anchor></li></ul> |
| Privasi | <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions">Sumber media yang dibatasi</Anchor> | <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields">Bidang data lengkap yang dibatasi</Anchor> |
| iOS 14 | <Anchor target="_blank" href="/marketers/id/docs/preparing-for-the-app-store-review-nutrition-labels">Label nutrisi—persiapkan untuk tinjauan App Store</Anchor> |  |
| iOS 14 | <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">Mengonfigurasi ATT di aplikasi</Anchor> (Pengembang panduan SDK) |  |
| iOS 14 | <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns">Tentang jaringan pelaporan mandiri (SRN) seperti Google, Meta ads, dan sebagainya</Anchor> | <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns#ios-145-srn-attribution">Di mana penginstalan SRN dilaporkan?</Anchor> |
| Penagihan | <Anchor target="_blank" href="https://content.appsflyer.com/ios-14-hub/billing/">Tagihan untuk aplikasi iOS</Anchor> |  |

<div id="ios-14-impact-on-attribution-and-measurement" />

<Accordion title="Dampak iOS 14 pada atribusi dan pengukuran">

#### **Metrik**

Pertimbangkan bahwa karena ATT, metrik yang berkaitan dengan pengguna yang tidak menyetujui ATT dapat terdampak sebagai berikut:

| Metrik | Tambah | Kurang | Catatan |
| --- | --- | --- | --- |
| Non-organik vs. organik | Organik | Non-organik |  |
| Penginstalan ulang vs. penginstalan | Penginstalan | Penginstalan ulang |  |
| Penargetan ulang | Penginstalan organik dan in-app event | Keterlibatan ulang, Atribusi ulang |  |
| Apple Search Ads | -- | -- | Tidak Berubah. Pengguna yang menyetujui dan tidak menyetujui diatribusikan dengan benar. |

#### **Penautan Langsung**

Penautan langsung yang ditangguhkan menggunakan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-legacy-apis#deferred-deep-linking">metode lama onConversionDataSuccess</Anchor> mungkin tidak berfungsi untuk iOS 14.5+ karena memerlukan data atribusi yang mungkin tidak tersedia karena perlindungan privasi.

Kami merekomendasikan penggunaan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl-1">penautan langsung terpadu (Unified Deep Linking-UDL)</Anchor>. UDL sesuai dengan standar privasi iOS 14.5+ dan hanya menampilkan parameter yang relevan dengan penautan langsung dan penautan langsung yang ditangguhkan: `deep_link_value` dan `deep_link_sub1`. Parameter atribusi seperti `media_source`, `campaign`, dan `af_sub1-5`menampilkan null dan tidak dapat digunakan untuk tujuan penautan langsung. <Anchor target="_blank" href="https://content.appsflyer.com/ios-14-hub/deep-linking-deferred-deep-linking/">Pelajari lebih lanjut</Anchor>

</Accordion>

## FAQ—iOS 14+

<div id="what-happens-to-an-app-using-an-sdk-version-before-v6" />

<Accordion title="Apa yang terjadi dengan aplikasi yang menggunakan versi SDK sebelum V6+?">

Untuk aplikasi yang menggunakan versi SDK yang lebih lama dari V6.0:

* SKAdNetwork dan Apple Search Ads tidak akan berfungsi.
* Jika Anda mengirimkan aplikasi ke App Store, perkirakan bahwa aplikasi tersebut akan ditolak.

Untuk aplikasi yang menggunakan SDK yang lebih lama dari V6.10: SKAN 4 tidak akan berfungsi.

</Accordion>

<div id="is-it-mandatory-to-display-the-att-prompt" />

<Accordion title="Apakah wajib untuk menampilkan perintah ATT?">

Tidak. Anda hanya perlu meminta persetujuan ATT jika Anda mau *melacak* pengguna, mengumpulkan IDFA, atau keduanya.

</Accordion>

## PERTANYAAN UMUM—SKAN

<div id="how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4" />

<Accordion title="Bagaimana saya tahu kapan saya akan menerima postback dan apakah postback tersebut adalah SKAN 3 atau SKAN 4?">

Jenis postback SKAN yang Anda terima ditentukan oleh berbagai faktor, termasuk mode apa yang Anda gunakan di Conversion Studio, jaringan iklan apa yang Anda gunakan, dan versi iOS yang dimiliki pengguna Anda.

Faktor-faktor ini berdampak pada:

* Versi postback: SKAN 3 atau SKAN 4. <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide#principles-and-flow">Pelajari lebih lanjut</Anchor>
* Window 1 (AW): Untuk SKAN 4, ini adalah 48 jam. Untuk SKAN 3, ini didasarkan pada periode waktu aktivitas. Catatan: Jika Conversion Studio bukan SKAN 4, tetapi tanda tangan jaringan iklan adalah SKAN 4, periode waktu didasarkan pada periode waktu aktivitas atau 48 jam, mana saja yang lebih rendah.
* Penundaan postback: Beberapa jam setelah penginstalan ketika postback SKAN tiba. Ini tergantung pada kapan periode waktu ditutup. <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide?query=skan%20faq#timing-from-app-install-until-dashboard-and-reports-update">Pelajari lebih lanjut</Anchor>
* Pengatur waktu bergulir: Untuk SKAN 3, periode waktu aktivitas dapat diperpanjang hingga 63 hari. Postback hanya tiba setelah periode waktu ditutup.

Diagram alur berikut menjelaskan hal ini secara lebih rinci.

![SKAN_4_matrix_-_Page_8__1_.png](https://files.readme.io/0dbd4cae34d9f9fed80dbe835485789dab75d46dbb38de055f454d01efb97350-13756140934545.png)

</Accordion>

<div id="in-skan-am-i-limited-to-100-campaign-ids-per-ad-network" />

<Accordion title="Di SKAN, apakah saya dibatasi pada sejumlah ID pengidentifikasi sumber/kampanye per jaringan iklan?">

Ya. Sebelumnya, batasnya adalah 100 ID kampanye. Namun, dari SKAN 4, ID kampanye disebut pengidentifikasi sumber hierarkis, dan batasnya adalah 10.000. Pengidentifikasi sumber adalah bilangan bulat 4 digit.

Jaringan iklan memetakan pengidentifikasi sumber SKAN ke ID kampanye mereka.

</Accordion>

<div id="what-is-the-use-case-for-skan-raw-data" />

<Accordion title="Apa kasus penggunaan untuk data lengkap SKAN?">

* Gunakan data lengkap untuk menggabungkan dimensi yang tidak tersedia melalui API yang digabungkan.
* Sesuaikan proses impor data lengkap yang ada dengan mudah untuk mengonsumsi data lengkap SKAN.

</Accordion>

<div id="why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio" />

<Accordion title="Mengapa nilai konversi yang saya terima tidak sesuai dengan konfigurasi saya di AppsFlyer Conversion Studio?">

Biasanya, ini karena SDK lain di aplikasi Anda yang memiliki kemampuan untuk menetapkan nilai konversi, dan yang bertentangan dengan SDK AppsFlyer Anda dan nilai konversi yang telah Anda konfigurasikan di AppsFlyer. Pastikan Anda tidak memiliki SDK lain yang menetapkan nilai konversi yang terintegrasi ke dalam aplikasi Anda.

</Accordion>

<div id="why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports" />

<Accordion title="Mengapa data yang digabungkan di dashboard SKAN saya tidak cocok dengan angka data lengkap di laporan SKAN Data Locker saya?">

Seringkali, perbedaan ini disebabkan karena melihat laporan Data Locker di tempat yang salah. Data dari Google dapat memakan waktu hingga 13 hari untuk diterima. Dan dalam laporan data lengkap, data ditulis pada hari diterima, bukan secara kumulatif. Oleh karena itu, untuk mendapatkan metrik yang benar untuk penginstalan yang berkaitan dengan tanggal tertentu, Anda juga perlu melihat semua laporan 13 hari setelah tanggal tersebut.

Contoh: Dalam laporan 12 Juni, laporan ini menampilkan 100 penginstalan dari Google yang terjadi pada 11 Juni. Dalam laporan 24 Juni, dikatakan 100 penginstalan YANG LEBIH BANYAK terjadi pada 11 Juni. Anda harus melihat semua laporan selama 13 hari terakhir (dari 12 Juni-24 Juni) dan menggabungkan berdasarkan waktu penginstalan atau stempel waktu jaringan iklan untuk mendapatkan pembacaan yang akurat dari total 200 penginstalan yang terjadi pada 11 Juni.

</Accordion>

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/getting-started-onboarding-for-marketers#langkah-3-pengaturan-atribusi">Langkah demi langkah untuk memulai AppsFlyer</Anchor>

<div data-zendesk-anchors="attribution-measurement-in-an-att-environment=pengukuran-atribusi-di-lingkungan-att h_01HE0C8YXSXSX003X0671Z97KZ=pengukuran-atribusi-di-lingkungan-att h_01HE0C8YXSCA8M57F1RG4CJ7HK=skan-solution-principles h_01HE0C8YXSSCTQJAPDE27FB1H8=att-principles h_01HE0C8YXS0BFA2M16D1Q2PQYW=which-dashboard-has-the-install ios-14-important-knowledge=pengetahuan-penting-ios-14 h_01HE0C8YXS3BH109DF1Y1KNK5P=pengetahuan-penting-ios-14 ios-14-and-skan-articles-and-links=artikel-dan-tautan-ios-14-dan-skan h_01HE0C8YXSPZKBWXC51Z2636R0=artikel-dan-tautan-ios-14-dan-skan h_01HE0C8YXSTCVA8YYR4BQVHVXS=ios-14-impact-on-attribution-and-measurement metrics=metrik h_01HE0C8YXSJMYN81FKPCA8ATK7=metrik deep-linking=penautan-langsung h_01HE0C8YXS6ADG1SQCMVP0W69B=penautan-langsung faq%E2%80%94ios-14=faqios-14 h_01HE0C8YXSV9VSK1NPG9RCTQW1=faqios-14 h_01HE0C8YXS1FFYQJ8YZXP9W9ZV=what-happens-to-an-app-using-an-sdk-version-before-v6 h_01HE0C8YXSKA0325YJSXV81ZB9=is-it-mandatory-to-display-the-att-prompt faq%E2%80%94skan=pertanyaan-umumskan h_01HE0C8YXSQKH8ER1Q5VS6Z0NM=pertanyaan-umumskan how-do-i-know-when-i%E2%80%99ll-receive-postbacks-and-if-they%E2%80%99ll-be-skan-3-or-skan-4=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXS44YXAN2DV2ZR03GE=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXSCWM892QH0N7YQ8HP=in-skan-am-i-limited-to-100-campaign-ids-per-ad-network h_01HE0C8YXSSWHV45M6P7SQGCRD=what-is-the-use-case-for-skan-raw-data h_01HE0C8YXS8GJKFC23S1R9TWW0=why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio why-doesn%E2%80%99t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE0C8YXS1VW1T50ARJE0MP62=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE7SNR02VQDKG55QP06ECNAR=lihat-juga" />
