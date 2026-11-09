---
title: Perbedaan Meta ads
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-11-09T10:10:54Z'
  edited_at: '2023-12-31T08:41:48Z'
  id: 4410481130641
  locale: id
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/id/articles/4410481130641
---
> **Sekilas:** Pelajari tentang perbedaan model atribusi antara Iklan Meta ads dan AppsFlyer.

<div id="meta-ads-discrepancies-with-appsflyer" />

## Perbedaan Meta ads dengan AppsFlyer

Sebagai dua pemain utama dalam ekosistem akuisisi user seluler, AppsFlyer dan Meta ads memiliki model atribusi yang berbeda. Hal ini dapat menyebabkan perbedaan antara dasbor Meta ads dan AppsFlyer.

Sementara kami bekerja sama dengan Meta ads untuk meminimalkan perbedaan ini, pemasang iklan harus mengetahui penyebab-penyebab berikut.

<div id="detect-a-discrepancy-between-appsflyer-and-meta-ads" />

### Mendeteksi perbedaan antara AppsFlyer dan Meta ads

Bandingkan event yang tercantum di **Event Manager** Meta ads dengan yang ada di laporan AppsFlyer. Jika jumlah event sangat bervariasi, mungkin ada perbedaan.

<div id="differences-in-attribution-models" />

## Perbedaan Model Attribution

<table><thead><tr><th>Penyebab</th><th>Iklan Meta</th><th>AppsFlyer</th></tr></thead><tbody><tr><td><span id="click-attribution-lookback-window"></span><p><strong>Lookback Window Atribusi Klik</strong></p></td><td><p>7 hari (Perhatikan <a href="https://www.facebook.com/business/help/395050428485124?id=428636648170202" target="_blank">bahwa ada beberapa kasus tertentu di mana default-nya berbeda</a> ).</p></td><td><p>1-30 hari. Pastikan untuk mengatur ke 7 hari dengan Meta ads.</p></td></tr><tr><td><span id="viewthrough-attribution-lookback-window"></span><p><strong>Lookback Window Atribusi View-Through</strong></p></td><td><p>1 hari (Perhatikan bahwa <a href="https://www.facebook.com/business/help/395050428485124?id=428636648170202" target="_blank">ada beberapa kasus tertentu di mana default-nya berbeda</a>).</p></td><td><p>1 hari secara default, tetapi dapat dikonfigurasi hingga 1-48 jam (biarkan nilai default ini)</p></td></tr><tr><td><span id="multichannel-sourceattribution"></span><p><strong>Atribusi<br/>Sumber Multi Channel</strong></p></td><td><p>Pemasangan atribut mandiri Meta ads terlepas dari sumber media lainnya.</p></td><td><p>AppsFlyer menggunakan atribusi klik terakhir (informasi lebih lanjut tentang atribusi AppsFlyer dapat dilihat <a href="./appsflyer-attribution-model" title="Model Atribusi AppsFlyer" target="_blank">di sini</a>).</p></td></tr><tr><td><span id="crossdevice-attribution"></span><p><strong>Atribusi Cross-device</strong></p></td><td><p>Meta ads mengatribusi penggunanya yang mengeklik dan menginstal di perangkat berbeda, misalnya, iOS/Android/desktop.</p></td><td><p>AppsFlyer mengatribusi device tunggal yang melakukan interaksi dan install</p></td></tr><tr><td><span id="different-time-zones"></span><p><strong>Zona Waktu yang Berbeda</strong></p></td><td><p>Zona waktu pelaporan default Meta ads adalah PST. Pastikan untuk <a href="https://www.facebook.com/business/help/754049591334898" target="_blank">mengubahnya di Meta Ads Manager</a> agar sesuai dengan zona waktu aplikasi yang ditentukan dalam pengaturan aplikasi di AppsFlyer.</p></td><td><p>Zona waktu aplikasi default AppsFlyer adalah UTC+0. Anda dapat mengubah zona waktu yang ditetapkan untuk aplikasi di <a href="./app-settings#localization-time-zone" target="_blank">halaman pengaturan aplikasi</a> agar cocok dengan zona waktu yang ditentukan dalam Meta ads Manager.</p></td></tr><tr><td><span id="google-install-referrer"></span><p><strong>Perujuk penginstalan Google</strong></p></td><td colspan="2"><p>Saat penginstalan tanpa ID pemasang iklan diatribusikan ke Meta ads menggunakan perujuk penginstalan Google Play, AppsFlyer tidak melaporkannya kembali ke Meta ads. Ini akan menyebabkan perbedaan karena akan ditampilkan di AppsFlyer dan bukan di Meta ads.  </p></td></tr><tr><td><span id="AEM-for-data-sharing"></span><p><strong>AEM untuk berbagi data</strong></p></td><td colspan="2"><p><span>Untuk <a href="./meta-ads-aggregate-event-measurement-aem-for-ios#aem-data-sharing" target="_blank">berbagi data AEM</a>, Meta ads menerima semua event konversi. Atribusi tambahan ini tidak ditampilkan di AppsFlyer. Oleh karena itu, terdapat peningkatan perbedaan data antara platform untuk penginstalan (dalam banyak kasus) dan peristiwa dalam aplikasi, termasuk sesi</span>.</p></td></tr></tbody></table>

<div id="click-through-and-view-through-attribution" />

## Atribusi Click-Through dan View-Through

AppsFlyer mendukung atribusi click-through (klik-tayang) dan view-through (lihat-tayang). Untuk meminimalkan perbedaan antara Meta ads dan AppsFlyer, pastikan bahwa jendela Lookback Click-Through (Klik-Tayang) dan View-Through (Lihat-Tayang) konsisten dengan jendela default yang ditentukan oleh Meta ads.

Jendela lookback klik-tayang default dari Meta ads ditentukan hingga 7 hari. Meskipun [ada beberapa kasus tertentu di mana default-nya berbeda](https://www.facebook.com/business/help/395050428485124?id=428636648170202) , disarankan untuk menyetel jendela lookback klik-tayang di AppsFlyer menjadi 7 hari untuk mencakup semua opsi default Meta ads.

Untuk membandingkan jendela atribusi klik-tayang dan lihat-tayang pada Meta ads dengan yang ada di AppsFlyer, kunjungi Meta ads. Kami menyarankan untuk mengonfigurasi jendela atribusi di AppsFlyer sesuai nilai Meta ads seperti yang ditunjukkan pada tangkapan layar berikut:

<Image align="center" alt="Facebook_Discrepancies.png" src="https://files.readme.io/e8caa7986ffa66c5bfdbef7457de5630899043256ca484f0cfdfdda8ac481c7e-4411036047505.png" />

<div id="example" />

> 📄 **Contoh**
>
> Misalkan jendela lookback klik Meta ads dikonfigurasi di AppsFlyer menjadi 1 hari untuk aplikasi com.greatapp Anda, sedangkan di Meta ads jendela tersebut memiliki nilai default 7 hari. Pengguna yang mengeklik iklan Greatapp di Facebook, namun meluncurkan aplikasi untuk pertama kalinya setelah jangka waktu 2-7 hari, akan diatribusikan sebagai pengguna organik di AppsFlyer, sedangkan Meta ads melaporkan pengguna ini secara mandiri.

## Perbedaan media terbatas

Hingga 28 Oktober 2021, data atribusi pengguna yang berasal dari atribusi lihat-tayang (view-through attribution/VTA) <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions">dibatasi dan tidak tersedia bagi pemasang iklan</Anchor>.Mulai 29 Oktober 2021, pembatasan berlaku bagi pengguna yang berasal dari atribusi lihat-tayang dan klik-tayang. Ini tidak memengaruhi laporan gabungan.

Karena Meta ads tidak mengirimkan data tingkat pengguna, AppsFlyer mungkin tidak mengatribusikan impresi dan klik yang membantu konversi ke Meta ads.

> 📄 **Contoh**
>
> * Seorang pengguna melihat atau mengeklik iklan AwesomeApp di Facebook. Lalu kemudian, pengguna melihat dan mengeklik iklan GreatAdNetwork untuk AwesomeApp dan menginstalnya.
> * Meta ads mengklaim konversi karena terjadi dalam jendela lookback mereka.
> * AppsFlyer mengatribusikan konversi ke GreatAdNetwork karena memiliki interaksi terakhir sebelum penginstalan.
> * AppsFlyer tidak akan menganggap Meta ads sebagai jaringan pendukung konversi karena data lengkap Meta ads dibatasi.

Namun, untuk atribusi klik-tayang, jika iklan mengarahkan pengguna ke Google Play Store, bidang atribusi tersedia untuk pengiklan di Google Install Referrer. Bidang ini tersedia melalui referrer yang mengisi laporan data lengkap AppsFlyer yang tersedia untuk Anda dan mengaktifkan AppsFlyer untuk mengatribusikan pengguna yang tidak memiliki ID iklan (LAT diaktifkan).

<div id="different-event-count" />

<div id="in-app-events-differences" />

## Perbedaan In-App Event

Perbedaan antar platform dapat juga ditampilkan sebagai event setelah penginstalan (misalnya, pembelian in-app), yang ditampilkan di Meta ads dan di AppsFlyer. Tabel berikut menjelaskan alasan paling umum atas perbedaan ini serta saran untuk meminimalkannya:

| Penyebab | Deskripsi | Tips AppsFlyer |
| --- | --- | --- |
| <span id="selfattribution"></span>**Self-attribution (Atribusi mandiri)** | Meta ads selalu mengatribusi event ke kampanye yang mendorongnya, sedangkan AppsFlyer mengatribusi event ini ke sumber akuisisi. | Penginstalan dan event, yang salah diatribusikan mandiri oleh Meta ads, diindikasikan sebagai <Anchor target="_blank" href="/marketers/id/docs/measure-assisted-installs#pelaporan-assisted-installs-penginstalan-berbantuan">bantuan di AppsFlyer</Anchor>.  <br />Gabungkan data lengkap dari konversi yang diatribusikan Meta ads dengan data lengkap di mana Meta ads adalah kontributornya. |
| <span id="different-lifetime-definition"></span>**Perbedaan definisi lifetime** | Seumur hidup pengguna pada Meta ads didefinisikan hingga 7 hari, artinya Meta ads tidak menampilkan event jika terjadi lebih dari 7 hari setelah iklan diklik.  <br />Di AppsFlyer, masa hidup pengguna Meta ads ditentukan hingga 180 hari. | Saat menilai nilai pengguna dari kampanye Meta ads yang terjadi setelah 7 hari, gunakan data AppsFlyer untuk mendapatkan gambaran yang lebih luas. |
| <span id="unmapped-events"></span>**Event tidak terpetakan** | AppsFlyer mendapatkan event yang berasal dari SDK, tetapi tidak dipetakan ke Meta ads, dan karenanya tidak dikirim. | Pastikan untuk <Anchor target="_blank" href="/marketers/id/docs/meta-ads-in-app-event-mapping">memetakan dengan Meta ads</Anchor> semua in-app event yang menandakan kualitas pengguna. |
| <span id="unsent-revenue"></span>**Pendapatan Tidak Terkirim** | AppsFlyer mendapatkan pendapatan dari event yang berasal dari SDK, tetapi tidak dikirimkan ke Meta ads. | Pastikan kotak **Send Revenue (Kirim Pendapatan)** in-app event selalu dicentang, misalnya event pembelian pada gambar screenshot di bawah ini. |
| <span id="missing-event-values-on-facebook"></span>**Nilai peristiwa tidak ada di Meta ads** | AppsFlyer mengirimkan parameter dan nilai ke Meta ads sebagai bagian pemetaan event jika keduanya memiliki struktur yang tepat. | Buat in-app event SDK sesuai dengan <Anchor target="_blank" href="/marketers/id/docs/in-app-events-event-structure">struktur rekomendasi AppsFlyer</Anchor> untuk sepenuhnya memetakan nilai event dengan Meta ads. |

<div id="installs-from-re-engagement-campaigns-in-my-ua-dashboard" />

## Install dari Kampanye Re-Engagement di Dashboard My UA?

Kampanye re-engagement dapat menyebabkan user membuka app yang sudah diinstall(**re-engagement**). Sebagai alternatif, saat AppsFlyer mengenali install app yang sebelumnya sudah ada pada perangkat yang sama, AppsFlyer dapat mengartikan konversi tersebut sebagai **re-attribution**.

Jika pada kampanye keterlibatan ulang, Meta ads menargetkan **pengguna baru** atau pengguna yang telah menginstal aplikasi untuk pertama kali **setelah** **melebihi <Anchor target="_blank" href="/marketers/id/docs/set-up-re-attribution-window">periode waktu atribusi ulang</Anchor> yang sudah ditetapkan** setelah penginstalan asli, maka para pengguna ini dicatat sebagai **penginstalan akuisisi pengguna baru di AppsFlyer**, yang merupakan bagian dari kampanye keterlibatan ulang di Meta ads.

Di sisi lain, penginstalan yang terjadi **dalam jendela atribusi ulang yang telah ditentukan** dan mengikuti penginstalan aslinya, dianggap sebagai atribusi ulang dan muncul pada halaman penargetan ulang AppsFlyer, sementara penginstalan tersebut mungkin muncul sebagai penginstalan baru oleh Meta ads.

<div id="note" />

> 📘 **Catatan**
>
> Jika Meta ads menampilkan semua penginstalan dari kampanye penargetan ulang di tempat yang sama, penginstalan pada dasbor AppsFlyer dibagi menjadi halaman Ikhtisar dan halaman Penargetan Ulang (atribusi ulang dan interaksi ulang).

<div id="cross-device-attribution" />

## Atribusi Cross-device

Meta ads melaporkan atribusi lintas perangkat. Hal ini kadang dapat menyebabkan masalah di mana kampanye untuk satu platform (iOS/Android) menampilkan instalasi di platform lain.

<div id="example-1" />

> 📄 **Contoh**
>
> Linda mengeklik iklan seluler GreatApp pada Facebook menggunakan ponsel Android-nya. Meta ads mencatat klik yang dilakukan Linda di bawah kampanye bertarget Android "Android Female". Linda memutuskan untuk menginstal GreatApp di iPad di rumahnya. Saat peluncuran pertama, AppsFlyer menanyakan Meta ads untuk asal penginstalan iOS ini, dan Meta ads menjawab dengan kampanye "Android Female".

<div id="validation-rules-and-protect360" />

## Validation Rules dan Protect360

Jika Anda menggunakan <Anchor target="_blank" href="/marketers/id/docs/implement-validation-rules-to-prevent-fraud">Aturan Validasi AppsFlyer</Anchor>, hasilnya mungkin berbeda antara AppsFlyer dan Meta ads ketika ada penginstalan yang ditolak yang berasal dari Meta ads. Dalam hal ini, Meta ads melaporkan mandiri adanya penginstalan ke dirinya sendiri, sementara AppsFlyer menolak penginstalan yang sama.

Demikian pula, jika Anda menggunakan solusi anti-penipuan AppsFlyer, Protect360, mungkin ada penginstalan karena Meta ads melaporkan sendiri, sedangkan AppsFlyer menolak.

<div id="example-2" />

> 📄 **Contoh**
>
> Jeff, manajer UA GreatApp, membuat kampanye yang disebut SPNA, yang hanya menargetkan penutur bahasa Spanyol di Amerika Utara. Untuk melakukan verifikasi hal ini, Jeff menetapkan aturan validasi, yang hanya menerima pengguna dari Kanada dan AS.
> Saat pengguna iklan Meta dari Spanyol mengeklik dan menginstal aplikasi, Meta ads melaporkan sendiri penginstalan tersebut, sementara AppsFlyer menolak penginstalan yang tidak lulus aturan validasi.

<div id="meta-probabilistic-modeling-aem-discrepancies-in-ios-apps" />

<div id="sdk-related-discrepancies" />

## Perbedaan terkait SDK

Mungkin ada <Anchor target="_blank" href="/marketers/id/docs/meta-ads-faq#who-needs-facebooks-sdk">beberapa kesempatan ketika pemasang iklan menerapkan SDK AppsFlyer dan Facebook</Anchor>. Hal ini dapat menyebabkan perbedaan untuk in-app event. Meta ads tidak membatalkan duplikasi in-app event yang dilaporkan dari kedua SDK. Ini berarti bahwa Meta ads dapat melaporkan secara palsu pendapatan dan event lainnya.

* Gunakan salah satu metode berikut untuk menghindari duplikat pelaporan in-app event di Meta ads:
  * Jangan konfigurasikan event di SDK Facebook.
  * Nonaktifkan <Anchor target="_blank" href="/marketers/id/docs/meta-ads-in-app-event-mapping">pemetaan in-app event Meta ads</Anchor> dari AppsFlyer.

<div data-zendesk-anchors="facebook-ads-discrepancies-with-appsflyer=perbedaan-meta-ads-dengan-appsflyer 01H890CZSXPMK0BDMC4202HNYM=perbedaan-meta-ads-dengan-appsflyer detect-a-discrepancy-between-appsflyer-and-facebook=mendeteksi-perbedaan-antara-appsflyer-dan-meta-ads 01H890CZSXGHVBH21SQA0671JQ=mendeteksi-perbedaan-antara-appsflyer-dan-meta-ads differences-in-attribution-models=perbedaan-model-attribution 01H890CZSX8M6VGGREYX4W2X37=perbedaan-model-attribution clickthrough-and-viewthrough-attribution=atribusi-click-through-dan-view-through 01H890CZSX40JDGY8P8AQ4CYGS=atribusi-click-through-dan-view-through 01H890CZSXRD7PCZBK52GW7QE9=contoh restricted-media-discrepancies=perbedaan-media-terbatas 01H890CZSX5WFX5Q0RNSG01GFH=perbedaan-media-terbatas 01H890CZSX567CQ3ZWZS5F05XW=contoh-1 inapp-events-differences=perbedaan-in-app-event 01H890CZSXKC5JKK9051MC0VY6=perbedaan-in-app-event installs-from-reengagement-campaigns-in-my-ua-dashboard=install-dari-kampanye-re-engagement-di-dashboard-my-ua 01H890CZSYE21K7PBQK4PNMGJR=install-dari-kampanye-re-engagement-di-dashboard-my-ua 01H890CZSY7TRCA4NVKSVPY7DB=catatan crossdevice-attribution::77a37a1f=atribusi-cross-device 01H890CZSYS8QKEAF6799SBS8J=atribusi-cross-device 01H890CZSY2Z3S6E9R5MYC1CHX=contoh-2 validation-rules-and-protect360=validation-rules-dan-protect360 01H890CZSYDHZE4V0ZWTT8V0EJ=validation-rules-dan-protect360 01H890CZSYCTQZCAYAZP9TCBBF=contoh-3 sdk-related-discrepancies=perbedaan-terkait-sdk 01H890CZSYVFPQP0SKNPWMPB1R=perbedaan-terkait-sdk" />
