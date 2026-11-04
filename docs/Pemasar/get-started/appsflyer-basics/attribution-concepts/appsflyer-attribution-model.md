---
title: Model Atribusi AppsFlyer
metadata:
  keywords:
    - Attribution
    - NativeTrack
    - Look-Back
    - Twiiter
    - Multi-Channel
    - Re-Install
    - Facebook
    - media source
    - Advertisers
    - Ad Networks
    - reinstall
    - branch
    - attribution determination
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T10:54:37Z'
  edited_at: '2023-11-13T14:54:32Z'
  id: 207447053
  locale: id
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/id/articles/207447053
---
> **Sekilas:** AppsFlyer menentukan sumber media yang memotivasi pengguna untuk menginstal atau berinteraksi ulang dengan aplikasi dan mengatribusikan tindakan pengguna ke sumber tersebut menggunakan model atribusi AppsFlyer.

[![Mobile_user_journey.png](https://support.appsflyer.com/hc/article_attachments/19544107641105)](https://support.appsflyer.com/hc/article_attachments/19544107641105)

<div id="what-is-attribution" />

## Apa itu atribusi?

**Atribusi** adalah tindakan untuk menentukan apa yang memotivasi (menyebabkan) pengguna menginstal aplikasi atau melakukan tindakan pasca-penginstalan seperti interaksi ulang dan atribusi ulang. Hasil atribusinya adalah:

* **Sumber media non-organik** : Pengguna berinteraksi (biasanya melalui tayangan atau klik) dengan sumber media.
* **Organik** : Pengguna tidak berinteraksi dengan sumber media. Perhatikan! Untuk memudahkan pemahaman, kami sering menyebut pengguna sebagai *diatribusi secara organik* . Kami tahu bahwa ini tidak sepenuhnya benar, karena pengguna yang menginstal secara organik sama sekali tidak diatribusikan.

Atribusi penting untuk mengoptimalkan akuisisi pengguna, upaya interaksi ulang, dan hasil.

> 👍 **Tips**
>
> Ingin tahu lebih banyak tentang atribusi? Lihat <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7766/play/18609/attribution-101-part-1">kursus singkat dan informatif ini di Portal Pembelajaran AppsFlyer</Anchor>.

<div id="what-is-an-app-install" />

## Apa itu penginstalan aplikasi?

**Model Atribusi** adalah sekumpulan aturan, yang menentukan bagaimana kredit untuk suatu event ditetapkan ke poin kontak di jalur konversi. Setiap pemain di ekosistem pemasaran aplikasi, Google Play, App Store, Apple, platform CTV, PC, dan konsol , jaringan iklan seperti Meta ads dan Twitter, serta perusahaan pengukuran seluler, memiliki model atribusinya sendiri. Masing-masing menghitung penginstalan dan event secara berbeda.

Yang penting bukanlah perbedaan antar model tetapi aturannya jelas dan diterapkan dengan cara yang tidak memihak. Memungkinkan pengiklan untuk mengoptimalkan kampanye dan membandingkan kualitas kinerja pengguna.

Penting untuk memahami model dan aturan pemain yang bekerja sama dengan Anda. Yang terpenting adalah memahami model dan pola metode yang didukung oleh AppsFlyer.

Di AppsFlyer, event yang dapat diatribusikan terjadi ketika salah satu dari hal berikut ini terjadi:

* Dalam konteks akuisisi pengguna : **Install** dicatat dan diatribusikan setelah pengguna mengunduh dan meluncurkan aplikasi seluler. Ini berarti bahwa di AppsFlyer, **stempel waktu dari penginstalan aplikasi adalah peluncuran pertama**. Sebaliknya, jaringan iklan menggunakan waktu interaksi dan app store menggunakan waktu unduh.
* Dalam konteks [retargeting (penargetan ulang)](/docs/appsflyer-attribution-model#retargeting-attribution) :
  * **Re-engagement**
  * **Atribusi ulang**

<div id="attribution-method-priorities-attribution-waterfall" />

<div id="attribution-methods" />

## Metode Atribusi

AppsFlyer menggunakan sejumlah metode atribusi yang tercantum dalam tabel berikut:

<table><thead><tr><th>Metode</th><th>Menggunakan ID</th><th>Teknik</th><th><p>Diatribusikan oleh</p></th><th><p>Android (1)</p></th><th>iOS </th><th>Platform Universal Window</th><th>Platform CTV, PC, dan konsol (3)</th></tr></thead><tbody><tr><td><a href="#install-referrer-android-only">Referrer (Pengarah)</a></td><td>Tidak</td><td>Deterministik</td><td>AppsFlyer</td><td>Ya (2)</td><td>Tidak</td><td>Ya</td><td>Tidak</td></tr><tr><td><a href="./appsflyer-attribution-model#device-id-matching">Pencocokan ID Device</a></td><td>Ya</td><td>Deterministik</td><td>AppsFlyer</td><td>Ya </td><td>Ya</td><td>Ya</td><td>Ya</td></tr><tr><td><a href="./appsflyer-attribution-model#probabilistic-modeling">Pemodelan probabilistik</a></td><td>Tidak</td><td>Probabilistik</td><td>AppsFlyer</td><td>Ya </td><td>Ya </td><td>Tidak</td><td>Ya</td></tr><tr><td><a href="./appsflyer-attribution-model#aggregated-advanced-privacy-aap">Privasi Tingkat Lanjut Gabungan (Aggregated Advanced Privacy/AAP)</a></td><td>Tidak</td><td>Teragregasi</td><td>AppsFlyer</td><td>Tidak</td><td>Ya</td><td>Tidak</td><td>Tidak</td></tr><tr><td><a href="./appsflyer-attribution-model#preload-campaigns">Pramuat</a></td><td>Tidak</td><td>Deterministik</td><td>AppsFlyer</td><td>Ya</td><td>Tidak</td><td>Ya</td><td>Tidak</td></tr><tr><td> <a href="./skadnetwork-skan-solution-guide" target="_blank">SKAdNetwork</a> (SKAN)</td><td>Tidak</td><td>Deterministik</td><td>Apple</td><td>Tidak</td><td>Ya</td><td>Tidak</td><td>Tidak</td></tr><tr><td><a href="./apple-ads-integration-setup" target="_blank">Apple Search Ads</a></td><td>Tidak</td><td>Deterministik</td><td>Apple</td><td>Tidak</td><td>Ya</td><td>Tidak</td><td>Tidak</td></tr><tr><td><a href="./appsflyer-attribution-model#deep-link">Tautan langsung</a></td><td>Tidak</td><td>Deterministik</td><td>AppsFlyer</td><td>Ya</td><td>Ya</td><td>Ya</td><td>Tidak</td></tr><tr><td colspan="7"><p>(1) Google Play dan toko aplikasi pihak ketiga</p><p>(2) Didukung oleh beberapa toko aplikasi pihak ketiga</p><p>(3) Lihat <a href="./ctv-pc-and-console-platform-attribution-concepts#platform-yang-didukung" target="_blank">daftar lengkap platform <span>CTV, PC, dan konsol</span></a> </p></td><td></td></tr></tbody></table>

Metode atribusi digunakan sesuai dengan prioritas yang ditunjukkan pada grafik. Pada penginstalan baru, jika ada lebih dari satu interaksi yang valid, **AppsFlyer memprioritaskan klik daripada tayangan, dan deterministik daripada metode probabilistik**.

![Attribution method priorities 23.png](https://support.appsflyer.com/hc/article_attachments/19910400460561)

Temukan penjelasan rinci tentang model atribusi AppsFlyer di bawah ini.

<div id="install-referrer-android-only" />

<Accordion title="install Referrer (khusus Android)">

Aplikasi Android yang diunduh dari Google Play dan beberapa toko aplikasi lain biasanya diatribusikan dengan metode pengarah penginstalan/install referrer. Referrer memberikan URL asli, diklik sebelum diarahkan ke Android store. Ini adalah metode utama untuk atribusi Android. Saat ini, Google Play, Huawei app store, Samsung Galaxy Store, dan Xiaomi GetApps Store, mendukung atribusi install referrer. <Anchor target="_blank" href="/marketers/id/docs/set-up-multi-store-android-attribution#referrer-implementation-thirdparty-android-app-stores">Atribusi app store alternatif menggunakan referrer.</Anchor>

</Accordion>

<div id="device-id-matching" />

<Accordion title="Pencocokan ID Device">

Ad network yang memiliki akses ke perangkat pengguna mengirimkan ID perangkat ke AppsFlyer saat URL diklik, atau ketika memberi tahu AppsFlyer bahwa impresi telah dilakukan. Ini memungkinkan AppsFlyer untuk mencocokkan ID perangkat klik dengan ID perangkat yang diperoleh oleh SDK AppsFlyer.

Pencocokan ID Device adalah metode atribusi utama pada iOS.

ID yang tersedia adalah:

* **Perangkat iOS** : IDFA, IDFV
* **Perangkat Android: memiliki layanan Google Play:** GAID
* **Perangkat Android tanpa layanan Google Play**: OAID, Android ID, IMEI, Fire ID

ID perangkat dapat dilakukan hash menggunakan SHA1 atau MD5 pada tautan atribusi.

</Accordion>

<div id="device-id-matching-using-idfv-ios" />

<Accordion title="Pencocokan ID perangkat menggunakan IDFV (iOS)">

* Pengenal untuk vendors (IDFV) tersedia di iOS 6.0+. IDFV ini tidak tunduk pada Apple <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor> dan mekanisme LAT. IDFV selalu tersedia dan dapat digunakan untuk iklan lintas promosi untuk aplikasi dari vendor yang sama.
* SDK AppsFlyer mengumpulkan IDFV secara default.
* <Anchor target="_blank" href="https://developer.apple.com/documentation/uikit/uidevice/1620059-identifierforvendor">Menurut Apple,</Anchor> *Nilai properti ini sama untuk aplikasi yang berasal dari vendor yang sama yang berjalan di perangkat yang sama.*
* IDFV dibuat oleh Apple saat pengguna menginstal aplikasi pertama dari vendor tertentu. Artinya, Apple memeriksa bahwa tidak ada aplikasi lain dari vendor yang sama di perangkat tersebut. Akibatnya, menghapus semua aplikasi dari vendor tertentu dan kemudian menginstal aplikasi dari vendor yang sama menghasilkan IDFV baru.
* Anda harus mengirimkan IDFV jika tersedia. IDFV meningkatkan atribusi. Kami menggunakan IDFV dalam sejumlah skenario, termasuk:
  * Atribusi promosi silang.
  * Penginstalan ulang atribusi di perangkat yang sama.
  * Pelaporan data lengkap.
  * Audiens.

</Accordion>

<div id="device-id-matching-for-selfreporting-networks" />

<Accordion title="Pencocokan ID Perangkat untuk jaringan pelaporan Mandiri">

Setelah peluncuran aplikasi pertama, AppsFlyer memeriksa pengaturan aplikasi apakah lalu lintas diharapkan dari salah satu <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns#srn-diintegrasikan-dengan-appsflyer">jaringan pelaporan mandiri</Anchor> (SRN), seperti Meta ads, Snapchat, dan Google Ads.

AppsFlyer meminta SRN yang relevan menggunakan ID perangkat unik untuk instalasi baru. Kueri menggunakan API Mobile Measurmenet Partners (MMP) seperti yang didefinisikan oleh SRN. Berdasarkan respons, AppsFlyer dapat mengatribusi penggunaan baru dengan sebuah SRN.

</Accordion>

<div id="probabilistic-modeling" />

<Accordion title="Pemodelan probabilistik">

Pemodelan probabilistik adalah teknik statistik yang memanfaatkan pembelajaran mesin untuk memperkirakan kinerja kampanye. Parameter pemodelan probabilistik dikumpulkan:

* Awalnya pada tampilan klik atau iklan (jika diaktifkan)
* sekali lagi saat aplikasi diluncurkan

#### **Catatan untuk aplikasi iOS:**

Memulai pemodelan probabilistik iOS 14.5+ terbatas pada konteks media yang dimiliki, promosi silang, dan alur web-to-app yang disetujui. Dalam konteks lain, [Gabungan Privasi Lanjutan](/docs/appsflyer-attribution-model#aggregated-advanced-privacy-aap) digunakan.

**Karakteristik penerapan**

* Menggunakan statistik dan tidak berdasarkan ID unik.
* Adalah metode fallback, digunakan jika tidak ada ID pengarah atau iklan. Metode atribusi deterministik, yaitu, klik dengan pengarah atau pencocokan ID, diprioritaskan jika terjadi dalam jendela lookback (lihat balik).
* Jendela atribusi ditentukan oleh AppsFlyer secara dinamis, berdasarkan jaringan pengguna. Durasi jendela bersifat adaptif tetapi lebih singkat daripada jendela metode lain (hingga 24 jam).
* Pemodelan probabilistik click-through (klik-tayang) selalu diaktifkan.
* Pemodelan probabilistik lihat-tayang harus diaktifkan di halaman pengaturan aplikasi dan di tab integrasi non-SRN. Untuk aplikasi CTV, PC, dan konsol , ini diaktifkan secara default.

#### Parameter pemodelan probabilistik untuk jaringan iklan

Jaringan iklan yang menerapkan atribusi Pemodelan probabilistik harus mengirimkan parameter berikut melalui  tautan atribusi atau melalui header permintaan HTTP:

* <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#af_ua">af\_ua</Anchor>
* <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#af_os_version">af\_os\_version</Anchor>
* <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#af_model">af\_model</Anchor>
* <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#af_ip">af\_ip</Anchor>

</Accordion>

<div id="aggregated-advanced-privacy-aap" />

<Accordion title="Privasi Tingkat Lanjut Gabungan (Aggregated Advanced Privacy/AAP)">

Privasi Tingkat Lanjut Gabungan (Agregated Advanced Privacy/AAP) memperlihatkan hasil kinerja kampanye gabungan, mencegah opsi apa pun untuk melacak pengguna di seluruh aplikasi dan situs web yang dimiliki oleh perusahaan yang berbeda, dan kemampuan untuk mengidentifikasi pengguna atau perangkat secara unik.

AAP menggunakan tingkat privasi SKAdNetwork Apple sebagai patokan minimum untuk ambang batas perlindungan privasi. AAP adalah model atribusi default untuk perangkat Apple yang beroperasi pada ios 14.5+, kecuali dalam kasus yang secara eksplisit diizinkan oleh Apple, seperti media milik sendiri dan pengguna yang disetujui ATT.

Tidak seperti metode atribusi lain yang dijelaskan, tujuan algoritme pembelajaran mesin AAP adalah memaksimalkan keakuratan kinerja kampanye gabungan, bukan keakuratan atribusi pengguna akhir.

</Accordion>

<div id="preload-campaigns" />

<Accordion title="Kampanye pramuat">

Dalam kampanye pramuat, aplikasi diinstal di perangkat pengguna oleh mitra pramuat, di pabrik atau setelah aktivasi perangkat. Mitra pramuat dapat berupa:

* Produsen Peralatan Asli (OEM)
* Platform penemuan aplikasi
* Operator seluler

Ada 3 metode untuk mengatribusikan kampanye pramuat. Ketiga metode tersebut dapat digunakan secara bersamaan; mereka tidak mengganggu mekanisme satu sama lain.

3 metode dan beberapa spesifikasi utama diuraikan dalam tabel berikut. Klik tautan untuk mempelajari lebih lanjut tentang setiap metode pramuat.

<table><thead><tr><th>Metode atribusi pramuat</th><th>Kasus penggunaan</th><th>Info peluncuran aktivasi perangkat ke aplikasi\*</th><th>Periode waktu lookback\*\*</th><th>Jenis pencocokan dalam data lengkap</th></tr></thead><tbody><tr><td> <a href="./set-up-appsflyer-preload-referrer-attribution" target="_blank">Perujuk AppsFlyer</a>\*</td><td><ul><li>Dimuat sebelumnya di pabrik</li><li>Dimuat sebelumnya saat aktivasi perangkat</li></ul></td><td>Ya</td><td><ul><li>Hingga 180 hari</li><li>Defaultnya adalah 90 hari</li></ul></td><td><ul><li>Pramuat: preload_rfr</li><li>Klik untuk mengunduh: af_referrer</li></ul></td></tr><tr><td> <a href="./measure-preload-campaigns-with-google-play-install" target="_blank">Instal otomatis Google Play</a>\*\*</td><td><p>Dimuat sebelumnya saat aktivasi perangkat (untuk aplikasi Google Play)</p></td><td>Tidak</td><td><ul><li>Hingga 180 hari</li><li>Defaultnya adalah 90 hari</li></ul></td><td>preload_pai</td></tr><tr><td> <a href="./appsflyer-factory-preinstall-using-manifest-android" target="_blank">Pramuat di pabrik melalui System Property (Android)</a>\*\*</td><td><ul><li>Dimuat sebelumnya di pabrik</li><li>Dimuat sebelumnya saat aktivasi perangkat</li></ul></td><td>Tidak</td><td><p>Tidak ada batas</p></td><td><p>preload_conf</p></td></tr><tr><td colspan="5"><p>\* Solusi pramuat perujuk AppsFlyer memberikan visibilitas dan kemampuan pengukuran antara aktivasi perangkat pertama dan peluncuran aplikasi pertama. Hal ini memungkinkan Anda melihat berapa banyak perangkat yang diaktifkan dengan aplikasi yang dimuat sebelumnya di perangkat oleh mitra tertentu, lalu melihat kapan aplikasi diluncurkan untuk pertama kalinya.</p><p>Untuk dua metode lainnya, atribusi ditentukan hanya setelah pengguna meluncurkan aplikasi untuk pertama kalinya, jumlah perangkat yang menginstal aplikasi sebelum peluncuran pertama tidak tersedia.</p><p>\*\* Proses ini dapat memakan waktu berhari-hari atau berminggu-minggu, mulai dari pertama kali pengguna menyalakan perangkat hingga meluncurkan aplikasi yang sudah dimuat sebelumnya untuk pertama kalinya. Oleh karena itu, AppsFlyer memberikan prioritas tertinggi pada kampanye pramuat dalam menentukan atribusi, dengan periode lihat balik yang lebih panjang.</p></td></tr></tbody></table>

</Accordion>

<div id="deep-link" />

<Accordion title="Tautan langsung">

Hanya untuk interaksi ulang, pengguna tidak diarahkan ke app store untuk mengunduh aplikasi. Maka, informasi di URL dapat dihubungkan secara langsung ke klik (dan aplikasi selanjutnya terbuka). Metode atribusi ini disebut sebagai tautan langsung karena URL tautan langsung membawa informasi yang digunakan untuk menghubungkan interaksi ulang.

</Accordion>

<div id="attribution-methods-per-media-source-and-appsflyer-feature" />

### Metode atribusi per sumber media dan fitur AppsFlyer

Lihat bagian berikut untuk rincian lengkap tentang kapan metode atribusi tertentu tersedia, bergantung pada:

* Sumber media: dimiliki atau dibayar
* Fitur AppsFlyer digunakan
* Perangkat pengguna: Android atau iOS

<div id="owned-media" />

<Accordion title="Media yang Dimiliki Sendiri">

<table><thead><tr><th rowspan="2">Media Source</th><th rowspan="2">Fitur</th><th colspan="2">Metode Atribusi</th></tr><tr><th>Android</th><th>iOS</th></tr></thead><tbody><tr><td>Media milik sendiri: email (termasuk penyedia layanan email/email service provider (ESP)), SMS, postingan media sosial, influencer/affiliate, media cetak, dll.</td><td><a href="./onelink-guide" target="_blank"><span>OneLink</span></a></td><td><ul><li>Install Referrer</li><li>Pemodelan probabilistik</li></ul></td><td><p>Pemodelan probabilistik</p></td></tr><tr><td rowspan="2">Situs web/laman arahan seluler milik sendiri dengan lalu lintas masuk berbayar atau organik</td><td><a href="./smart-banners-mobile-web-to-app-for-marketers" target="_blank">Smart Banner (Spanduk Cerdas)</a></td><td>Pemodelan probabilistik</td><td>Pemodelan probabilistik</td></tr><tr><td><a href="./onelink-smart-script-overview" target="_blank">OneLink Smart Script</a></td><td><ul><li>Install Referrer</li><li>Pemodelan probabilistik</li></ul></td><td>Pemodelan probabilistik</td></tr><tr><td rowspan="2">Aplikasi seluler milik sendiri</td><td><a href="./user-invite-attribution" target="_blank">Undangan/rujukan pengguna</a></td><td><p>Pemodelan probabilistik</p></td><td><p>Pemodelan probabilistik</p></td></tr><tr><td><a href="./cross-promotion-attribution-for-marketers" target="_blank">Promosi silang</a></td><td>Pencocokan ID Device</td><td>Pencocokan ID Device</td></tr></tbody></table>

</Accordion>

<div id="paid-media" />

<Accordion title="Media berbayar">

<table><thead><tr><th rowspan="2">Media Source</th><th colspan="3">Metode Atribusi</th></tr><tr><th>Android</th><th>iOS</th><th><strong>Platform CTV, PC, dan konsol</strong></th></tr></thead><tbody><tr><td><a href="./self-reporting-networks-srns" target="_blank">SRN</a></td><td><p>Pencocokan ID Device</p></td><td><ul><li>Pencocokan ID Device</li><li>AAP (iOS 14.5+)</li><li>SKAdNetwork (iOS 14+)</li></ul></td><td><p>Pencocokan ID Device</p></td></tr><tr><td><ul><li>Jaringan iklan (non-SRN) melalui <a href="./set-up-an-integrated-partner#attribution-link-tab" target="_blank">tautan atribusi untuk mitra</a> </li><li><span>Platform CTV, PC, dan konsol</span></li></ul></td><td><ul><li>Install Referrer</li><li>Pencocokan ID Device</li><li>Pemodelan probabilistik</li></ul></td><td><ul><li>Pencocokan ID Device</li><li>Pemodelan probabilistik (sebelum iOS 14.5)</li><li>AAP (iOS 14.5+)</li><li>SKAdNetwork (iOS 14+)</li></ul></td><td> </td></tr><tr><td><p><a href="./appsflyer-factory-preinstall-using-manifest-android" target="_blank">Pra-penginstalan pada perangkat</a></p></td><td>Pra-install</td><td>--</td><td> </td></tr></tbody></table>

</Accordion>

<div id="engaged-view-attribution" />

<div id="engaged-click-attribution" />

<div id="user-engagement-attribution-types" />

## Jenis Atribusi Interaksi User

Atribusi dilakukan berdasarkan interaksi klik-tayang dan lihat-tayang. Atribusi sumber media dicapai dengan memanfaatkan pencocokan ID perangkat dan teknik pemodelan probabilistik.

<div id="clickthrough-attribution" />

<Accordion title="Atribusi Click-Through">

Sebagian besar penginstalan adalah hasil dari klik pengguna pada iklan, seperti spanduk, video, dan perantara.

Setelah iklan diklik, jendela lookback klik terbuka dengan durasi default 7 hari. Penginstalan yang terjadi selama durasi jendela lookback adalah non-organik dan diatribusikan ke sumber media. Penginstalan yang terjadi setelah durasi jendela lookback dianggap sebagai penginstalan organik. Sering disebut sebagai diatribusikan secara organik.

* Jendela lihat-balik klik tujuh hari dianggap sebagai standar industri. Atur durasi jendela sesuai persetujuan Anda dengan sumber media.
* Sejajarkan jendela lihat-balik SRN dengan durasi yang ditentukan oleh SRN.

<table><thead><tr><th rowspan="2"><p><strong>Jenis Atribusi</strong></p></th><th rowspan="2"><p><strong>Metode Atribusi</strong></p></th><th rowspan="2"><p>Jangkauan</p></th><th rowspan="2">Default</th></tr></thead><tbody><tr><td rowspan="2"><p>Click-Through</p><p>(Semua Mitra Terintegrasi)</p></td><td><p>Referrer, Pencocokan ID</p></td><td><p>1 – 30 Hari</p></td><td><p>7 Hari</p></td></tr><tr><td><p>Pemodelan probabilistik</p></td><td><p>0–24 Jam</p></td><td><ul><li>Adaptif</li><li>Ditentukan oleh AppsFlyer</li></ul></td></tr></tbody></table>

<Anchor target="_blank" href="/marketers/id/docs/set-up-lookback-windows">Pelajari lebih lanjut tentang periode lihat balik</Anchor>

</Accordion>

<div id="viewthrough-attribution" />

<Accordion title="Atribusi View-Through">

Pengguna yang melihat iklan seluler tetapi tidak mengkliknya, dapat diatribusi ke jaringan iklan yang menayangkan iklan.

Jendela lookback untuk atribusi lihat-tayang:

* lebih singkat daripada atribusi klik-tayang
* dapat dikonfigurasi.

Untuk mengaktifkan atribusi lihat-tayang, atur jendela lookback di jendela konfigurasi AppsFlyer.

Hal ini sangat membantu untuk ad network video yang biasanya memiliki CTRs rendah pada iklan-iklan video mereka, juga untuk ad network biasa yang melayani iklan-iklan reguler.

<table><thead><tr><th><strong>Jenis Atribusi</strong></th><th><p><strong>Metode Atribusi</strong></p></th><th><p><strong>Jangkauan</strong></p></th><th><p><strong>Default<br/></strong></p></th></tr></thead><tbody><tr><td rowspan="2"><p>View-Through</p><p>(<a href="./measure-view-through-engagements#view-vta-partner-list" target="_blank">Mitra Terintegrasi yang Dipilih</a>)</p></td><td><p>Pencocokan ID</p></td><td><p>0-24 jam</p></td><td><p>1 Hari</p></td></tr><tr><td><p>Pemodelan probabilistik</p></td><td><p>0-24 jam</p></td><td><ul><li>Adaptif</li><li>Ditentukan oleh AppsFlyer</li></ul></td></tr></tbody></table>

Pada kasus di mana terjadi sebuah klik dan tayangan iklan, klik selalu mendahului, karena klik merupakan interaksi aktif.

<Anchor target="_blank" href="/marketers/id/docs/measure-view-through-engagements">Pelajari lebih lanjut tentang atribusi lihat-tayang</Anchor>

</Accordion>

<div id="advanced-attribution-topics" />

## Topik Atribusi Tingkat Lanjut

<div id="in-app-events" />

<Accordion title="In-App Event">

AppsFlyer membuat ID AppsFlyer unik untuk penginstalan aplikasi yang dikaitkan dengan detail atribusi. Hal ini memungkinkan platform **mengatribusikan in-app event ke sumber media asli**. Pemasang iklan dapat menggunakan informasi ini untuk mengikuti perjalanan pengguna pada data lengkap aplikasi mereka.

Untuk informasi selengkapnya tentang atribusi event, klik <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview?query=in%20app%20event#how-does-appsflyer-attribute-events">di sini</Anchor>.

</Accordion>

<div id="assisted-installs" />

<Accordion title="Assisted Installs">

AppsFlyer sepenuhnya hanya menghubungkan satu media sumber setiap instalasi, biasanya menggunakan klik iklan terakhir atau tayangan iklan terakhir (jika tidak ada klik).

Assisted Installs (Penginstalan dengan Bantuan) (alias atribusi multi-sentuh) adalah penginstalan di mana sumber media/kampanye bukan merupakan titik kontak terakhir, tetapi menyentuh pengguna sebelum penginstalan dan sentuhan terjadi dalam periode waktu lookback atribusi.

Jaringan yang membantu ditampilkan sebagai kontributor untuk instalasi di AppsFlyer.

Untuk informasi lebih lanjut, klik <Anchor target="_blank" href="/marketers/id/docs/measure-assisted-installs">di sini</Anchor>.

</Accordion>

<div id="reinstalls" />

<Accordion title="Instalasi ulang">

Penginstalan ulang terjadi ketika pengguna menginstal aplikasi, menghapus penginstalan, lalu kemudian menginstal ulang. Atribusi penginstalan ulang diatur oleh <Anchor target="_blank" href="/marketers/id/docs/set-up-re-attribution-window">re-attribution window (jendela atribusi ulang)</Anchor> sebagai berikut:

* Jika penginstalan ulang terjadi setelah berakhirnya jendela atribusi ulang: dicatat sebagai penginstalan baru.
* Jika penginstalan ulang terjadi selama jendela atribusi ulang, berlaku salah satu dari yang berikut:
  * Jika pengguna berinteraksi dengan kampanye penargetan ulang sebelum penginstalan ulang: dicatat sebagai <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide">retargeting reinstall (penginstalan ulang penargetan ulang)</Anchor> (atau atribusi ulang).
  * Jika pengguna tidak berinteraksi dengan kampanye atau berinteraksi dengan kampanye UA: tidak ada penginstalan yang tercatat. Tergantung pada status <Anchor target="_blank" href="/marketers/id/docs/measure-reinstalls#ringkasan">**Atribusi Event Pasca Penginstalan Ulang**</Anchor> , in-app event dari pengguna yang menginstal ulang ini diatribusikan penginstalan organik atau penginstalan awalnya.

Untuk pengujian perangkat dan beberapa penginstalan, <Anchor target="_blank" href="/marketers/id/docs/registering-test-devices">daftarkan</Anchor> perangkat di AppsFlyer. Jika Anda tidak mendaftarkan perangkat, hanya penginstalan pertama yang dicatat.

Perhatikan bahwa AppsFlyer memungkinkan akurasi yang lebih baik untuk mengatribusikan penginstalan ulang iOS tanpa ID pengiklan. Anda dapat mengaktifkan fitur ini di <Anchor target="_blank" href="/marketers/id/docs/app-settings#reinstall-detection-using-ondevice-storage-ios-only">halaman Pengaturan Aplikasi</Anchor>.

<div id="reinstalling-ios-apps-that-are-backed-up-in-icloud" />

#### Menginstal ulang aplikasi iOS yang dicadangkan di iCloud

Ketika suatu aplikasi dicadangkan menggunakan iCloud dan kemudian dipulihkan (pada perangkat yang sama atau pada perangkat lain), AppsFlyer tidak menghitungnya sebagai instalasi baru atau instalasi ulang. Seorang Pengguna yang memulihkan aplikasi dari iCloud menyimpan ID AppsFlyer dan data atribusi mereka.

</Accordion>

<div id="retargeting-attribution" />

<Accordion title="Atribusi Retargeting">

![Retargeting_-_Flow__2_.png](https://files.readme.io/64b8d9f5040daa281ae13f0855749ab4a88a2e7e8616d6ada37975899db92c80-31937591646097.png)

Pengguna yang menginstal ulang aplikasi selama <Anchor target="_blank" href="/marketers/id/docs/set-up-re-attribution-window">re-attribution window (jendela atribusi ulang)</Anchor> (90 hari secara default) dianggap sebagai atribusi ulang. Jika penginstalan ini terjadi setelah berinteraksi dengan kampanye penargetan ulang, penginstalan ini dicatat sebagai penargetan ulang penginstalan ulang ATAU atribusi ulang dan dilaporkan dalam <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide">retargeting (penargetan ulang)</Anchor>.

</Accordion>

<div id="app-updates" />

<Accordion title="Pembaruan App">

* Ketika pengguna yang sudah ada memperbarui aplikasi ke versi berikutnya, ini tidak diperlakukan sebagai event atribusi yang dapat dihitung, jika pengguna sebelumnya telah diatribusi oleh AppsFlyer. Perhatikan! Jika Anda bermigrasi ke AppsFlyer dari pengguna MMP lain yang sudah ada pada pembukaan aplikasi pertama, setelah migrasi, akan diatribusi ke organik.
* Metrik yang berkaitan dengan jumlah pengguna per versi aplikasi tersedia di <Anchor target="_blank" href="/marketers/id/docs/sdk-information-version-consent-dashboard">dasbor Informasi SDK.</Anchor>

</Accordion>

<div data-zendesk-anchors="what-is-attribution=apa-itu-atribusi 01H8GG9XPSS8KA9CHPD6ECNR2J=apa-itu-atribusi 01H8GG9XPSA15N5CSHGZNBWSAV=tips what-is-an-app-install=apa-itu-penginstalan-aplikasi 01EDRHGMTXK94Y97DPKFAMCJ5B=apa-itu-penginstalan-aplikasi attribution-methods=metode-atribusi 01EDRHGMTXCRNVXS9JGHQ1JAQT=metode-atribusi 01H8GG9XPS6P3CXX5AN2KY8WN4=install-referrer-android-only 01H8GG9XPSGVK90FV0K9HZARH7=device-id-matching 01H8GG9XPSQZPWJZ0BC0EAMB97=device-id-matching-using-idfv-ios 01H8GG9XPSV247F3JRCR870JK0=device-id-matching-for-selfreporting-networks 01EDRHGMTXHAKWZK99Q2X86BND=probabilistic-modeling note-for-ios-apps=catatan-untuk-aplikasi-ios 01H8GG9XPSE1H8F9TCCXSZSW9W=catatan-untuk-aplikasi-ios probabilistic-modeling-parameters-for-ad-networks=parameter-pemodelan-probabilistik-untuk-jaringan-iklan h_01HEMSHXKGNW2DF41094BXY0FY=parameter-pemodelan-probabilistik-untuk-jaringan-iklan 01H8GG9XPSZ5CPKNSCV7NF1MKW=preload-campaigns attribution-methods-per-media-source-and-appsflyer-feature=metode-atribusi-per-sumber-media-dan-fitur-appsflyer 01H8GG9XPTXDR41QANF4XVSZMM=metode-atribusi-per-sumber-media-dan-fitur-appsflyer 01H8GG9XPT65G88DE8548HZREE=owned-media 01H8GG9XPTADWMQ37WBB6P9WVS=paid-media user-engagement-attribution-types=jenis-atribusi-interaksi-user 01EDRHGMTX7851H14R20F9KNAN=jenis-atribusi-interaksi-user 01EDRHGMTXJ7WKTWQXFCHTD9AV=clickthrough-attribution 01EDRHGMTXN0Y0ZRVBX7HHW7NN=viewthrough-attribution advanced-attribution-topics=topik-atribusi-tingkat-lanjut 01EDRHGMTYYXBSCDPKXCDK1641=topik-atribusi-tingkat-lanjut 01EDRHGMTYMH3SVNBTQ28D4F42=in-app-events 01EDRHGMTY2CF0B70T3RAGPCJ1=reinstalls reinstalling-ios-apps-that-are-backed-up-in-icloud=menginstal-ulang-aplikasi-ios-yang-dicadangkan-di-icloud 01EDRHGMTYDSNJKQNPNYFXJPAZ=menginstal-ulang-aplikasi-ios-yang-dicadangkan-di-icloud 01EDRHGMTYYB9XVM5CBWSPJGMN=retargeting-attribution 01EDRHGMTYTQRMG1W7ZBW4G6W4=app-updates" />
