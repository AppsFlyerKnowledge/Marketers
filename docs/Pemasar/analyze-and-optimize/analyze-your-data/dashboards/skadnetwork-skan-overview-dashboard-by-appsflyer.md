---
title: Dasbor ikhtisar SKAdNetwork (SKAN) oleh AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-07-25T21:27:38Z'
  edited_at: '2024-09-12T12:26:16Z'
  id: 360011307357
  locale: id
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/id/articles/360011307357
---
> **Sekilas:** Dasbor SKAdNetwork (SKAN) menampilkan metrik kampanye yang dilaporkan melalui postback SKAN iOS dan titik data tambahan selama jendela pengukuran pengguna awal. Metrik model yang mempertimbangkan konversi null juga tersedia. Data ditampilkan menggunakan tanggal kedatangan penginstalan atau postback.

![SKAdHeadling8_us-en.png](https://files.readme.io/72c2eb452741cbd77c5828197f827f238c71c5097b8703528fa180dcafe2364c-360011831017.png)

<div id="dashboard-principles" />

## Prinsip dasbor

Dasbor berisi data kinerja kampanye SKAN dan mematuhi prinsip-prinsip berikut:

* Pertimbangkan bahwa Apple, karena <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork">mekanisme ambang privasi</Anchor>, tidak selalu mengisi nilai konversi (CV). Ini disebut sebagai CV null. Dalam kasus CV nol, hanya instalasi yang direkam.
* Metrik dihitung sebagai berikut:
  * Metrik non-organik di dasbor dihitung menggunakan data postback SKAN yang diterima oleh AppsFlyer. Beberapa metrik seperti pengunduhan ulang, ID aplikasi sumber, dan metrik jenis kesetiaan mengharuskan Anda mengonfigurasi aplikasi untuk <Anchor target="_blank" href="/marketers/id/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">mengirim salinan postback langsung ke</Anchor> AppsFlyer.
  * Metrik organik dihitung sebagai data atribusi AppsFlyer dikurangi data atribusi non-organik SKAN. **Catatan**: Metrik organik tidak selalu tersedia. [Pelajari lebih lanjut](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations).
    * Pastikan Anda memfilter berdasarkan **Instalasi baru** di bidang jenis instalasi.
  * Beberapa metrik, seperti pendapatan dan ROAS, memiliki nilai asli yang berasal dari postback dan [nilai model yang mempertimbangkan](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) tingkat CV nol.
* Lalu lintas yang digerakkan oleh agensi diperlakukan sebagai berasal dari agensi transparan.
* Keaktualan data
  * Harian.
  * Postback yang diterima pada hari tertentu diproses pada akhir hari UTC. Data tersedia pada pukul 08:00 UTC pada hari berikutnya. Artinya postback yang diterima pada hari Senin tersedia di dasbor pada Selasa pagi.
  * Lihat <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">waktu pembaruan dasbor yang diharapkan.</Anchor>

<div id="skan-dashboard-view-options" />

## Opsi tampilan dasbor SKAN

Menampilkan data menggunakan tanggal [instal atau tanggal kedatangan postback](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#filter-options).

**Untuk memilih opsi tampilan tanggal**, di AppsFlyer, dari menu samping, pilih **Analisis** > **Ikhtisar SKAN.** Di bilah filter, pilih opsi **Tampilan berdasarkan** tanggal.

Filter tambahan dan opsi tampilan dijelaskan di bagian berikut.

<div id="dashboard-use" />

## Penggunaan dasbor

<div id="dashboard-settings" />

<Accordion title="Pengaturan dasbor">

Pengaturan dasbor tersedia saat aplikasi Anda menggunakan <Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio#fixed-modes">pengukuran konversi mode tetap lama</Anchor> untuk memilih event konversi.

**Untuk memilih event konversi**:

1. Di sisi kanan atas dasbor, klik Pengaturan das **bor**.
2. Pilih event konversi.
3. Klik terapkan.  
   Metrik konversi dihitung menggunakan event ini.  
   Perhatikan! Pengaturan ini berkaitan dengan tampilan di dasbor dan tidak memengaruhi pengaturan CV di aplikasi.

</Accordion>

<div id="filter-options" />

<Accordion title="Pilihan filter">

Gunakan filter untuk menyempurnakan informasi yang ditampilkan.

| **Filter** | **Catatan** |
| --- | --- |
| Tampilan oleh | <ul><li>Tanggal penginstalan Berasal dari waktu kedatangan postback sebagai berikut:<ul><li>Jika postback SKAN adalah SKAN V4, rumus tanggal instal adalah: Tanggal instal = waktu kedatangan postback - [panjang jendela akumulasi] - [rata-rata penundaan postback].<ul><li>Postback 1: tanggal penginstalan = waktu kedatangan postback - 48j - 36j</li><li>Postback 2: tanggal penginstalan = waktu kedatangan postback - 168j - 84j</li><li>Postback 3: tanggal penginstalan = waktu kedatangan postback - 840j - 84j</li></ul></li><li>Jika postback SKAN adalah SKAN V3 atau sebelumnya, rumus tanggal instal adalah: Tanggal instal = waktu kedatangan postback - 36 jam - [rentang aktif terakhir rata-rata].<ul><li>Defaultnya [rata-rata rentang aktif terakhir] adalah 12 jam.</li><li>Untuk nilai konversi 0, rata-rata rentang aktif terakhir ditetapkan ke 0.</li></ul></li></ul></li><li>**Tanggal kedatangan Postback**:<ul><li>Tanggal postback diterima oleh AppsFlyer.</li><li>Saat membandingkan metrik di dasbor SKAN AppsFlyer dengan metrik yang disediakan oleh jaringan iklan, pertimbangkan bahwa jaringan iklan biasanya menyediakan data menggunakan tanggal kedatangan postback.</li><li>Metrik organik tidak tersedia saat memilih opsi ini.</li><li>Dalam kasus Google Ads, tanggal kedatangan dan instal tidak berbeda.</li></ul></li></ul> |
| Rentang tanggal | <ul><li>Tanggal instal yang dikaitkan. Tanggal ini diturunkan menggunakan waktu kedatangan postback.</li><li>Jika ada sejumlah besar penginstalan, ketidaktepatan karena masalah waktu tidak signifikan.</li><li>Penginstalan termasuk pengunduhan ulang.</li><li>Rentang tanggal dibatasi hingga 90 hari.</li></ul> |
| Sumber media | <ul><li>Jaringan iklan yang dikaitkan dengan penginstalan</li><li>Lalu lintas yang digerakkan oleh agensi: Sumber media aktual ditampilkan terlepas dari status transparansi agensi. Akibatnya, Anda mungkin melihat sumber media yang tidak Anda kenal.</li></ul> |
| Kampanye | <ul><li>Nama dan ID kampanye sebagaimana ditetapkan oleh jaringan iklan.</li><li>AppsFlyer menerjemahkan ID kampanye postback ke ID jaringan iklan.</li><li>Jika ID kampanye tertentu memiliki beberapa nama kampanye yang terkait dengannya, maka semua nama akan ditampilkan di dasbor. Perhatikan! Jaringan iklan menyediakan ID kampanye dan nama per postback. ID kampanye dan nama kampanye tersedia dalam data mentah dan laporan SKAN agregat.</li></ul> |
| ID Situs | <ul><li>Aplikasi sumber yang menampilkan iklan Anda.</li><li>Gunakan untuk menganalisis aplikasi yang paling bermanfaat bagi Anda.</li></ul> |
| Geo | <ul><li>Wilayah atau negara</li><li>Geo diturunkan menggunakan data yang disediakan oleh jaringan iklan atau menggunakan alamat IP perangkat.</li><li>Dengan  menggunakan iOS 14.6 alamat IP perangkat ditutupi oleh server proxy Apple. Artinya geolokasi server Apple tercermin dan bukan perangkat itu sendiri.</li></ul> |
| Jenis penginstalan | <ul><li>Penginstalan</li><li>Pengunduhan ulang dilaporkan oleh app store</li></ul> |
| Adset | Tersedia jika jaringan iklan menyediakan titik data ini |
| Iklan | Tersedia jika jaringan iklan menyediakan titik data ini |
| Versi | Versi SKAN |

</Accordion>

<div id="headline-metrics" />

<Accordion title="Metrik headline">

| Metrik | Catatan |
| --- | --- |
| Penginstalan | SKAN tidak melaporkan penginstalan jika pengguna tidak terlibat dengan iklan sebelum penginstalan. AppsFlyer menghitung metrik organik menggunakan penginstalan yang dikaitkan AppsFlyer (dasbor LTV.)<ul><li>Non-organik: Penginstalan yang dikaitkan dengan sumber media dalam konteks kampanye aplikasi-ke-aplikasi berbayar dan dilaporkan oleh SKAN.</li><li>Organik yang dihitung oleh AppsFlyer meliputi yang berikut:<ul><li>Penginstalan yang tidak dikaitkan oleh SKAN atau tidak ada postback yang diterima dari jaringan iklan.</li><li>Klip App</li><li>Iklan Cari Apple.</li></ul></li></ul> |
| Titik sentuh | Jaringan iklan melaporkan tayangan dan klik berdasarkan klik atau API. |
| Total Pendapatan | <ul><li>Tersedia saat mode pendapatan aktif.</li><li>Menampilkan dalam USD atau dalam mata uang lokal khusus aplikasi seperti yang ditetapkan pada halaman <Anchor target="_blank" href="/marketers/id/docs/app-settings">pengaturan aplikasi</Anchor>.</li><li>Dibagi antara pendapatan organik dan non-organik.</li><li>Pendapatan organik dihitung sebagai pendapatan dari semua sumber dikurangi pendapatan non-organik.</li><li>Untuk mengaktifkan perbandingan yang menyukainya, durasi jendela pasca-instalasi pemasangan organik dan non-organik adalah sama.</li><li>Termasuk data <Anchor target="_blank" href="/marketers/id/docs/skan-modeled-data#null-conversion-values">yang dimodelkan</Anchor></li></ul>**Catatan**: Metrik organik tidak selalu tersedia. [Pelajari lebih lanjut](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations). |
| Biaya | <ul><li>Biaya yang dilaporkan oleh jaringan iklan. Data biaya dilaporkan ke AppsFlyer menggunakan ROI360/Cost API. Biaya ditampilkan dalam USD atau dalam mata uang lokal khusus aplikasi seperti yang ditetapkan pada halaman <Anchor target="_blank" href="/marketers/id/docs/app-settings">pengaturan aplikasi</Anchor>.</li><li>Jika nama kampanye berubah, biaya ditampilkan di bawah nama kampanye terbaru yang digunakan. (Jika ada beberapa nama kampanye)</li><li>Metrik biaya hanya tersedia untuk filter Install Type=ALL yang mencakup penginstalan dan pengunduhan ulang.</li></ul> |
| Tingkat klik untuk menginstal | Tingkat klik untuk menginstal |
| Tren periode yang berdekatan | Nilai tren dalam% menunjukkan perubahan metrik saat ini relatif terhadap metrik periode ekuivalen sebelumnya. Misalnya, jika periode saat ini adalah 1-10 Mei, periode sebelumnya adalah 21-30 April. |

</Accordion>

<div id="charts" />

<Accordion title="Grafik">

Bagan yang tersedia tergantung pada jenis pengukuran yang dipilih.

<Table>
  <thead>
    <tr>
      <th>
        Metrik grafik
      </th>
      <th>
        Catatan
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Tren akuisisi pengguna
      </td>
      <td>
        Dimensi yang tersedia:

        * Organik
        * Non-organik

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer2_us-en.png" src="https://files.readme.io/5c46dc05b4df07f3f60ff6015f115b4bc89106a6eb594f43d777af2100fdf460-360010368477.png" width="201px" />](https://files.readme.io/e30781379f0acb50d73e18e6c59ff76f8c91fa4cda6b92064310050555f826a3-360010359738.png)
      </td>
    </tr>
    <tr>
      <td>
        Sentuh untuk konversi
      </td>
      <td>
        Tampilan tersedia:

        * Dimensi titik sentuh:
          * Tayangan
          * Klik
        * Tingkat klik untuk menginstal

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer3_us-en.png" src="https://files.readme.io/3e134f9411b356c8879dad8185b1762e6e039ed277da60fa9f67af351d8ab76d-360010368497.png" width="223px" />](https://files.readme.io/3e134f9411b356c8879dad8185b1762e6e039ed277da60fa9f67af351d8ab76d-360010368497.png)
      </td>
    </tr>
    <tr>
      <td>
        Instal per hari dikelompokkan berdasarkan elemen hierarki iklan
      </td>
      <td>
        Elemen yang tersedia: Sumber media, Kampanye, ID Situs, Iklan, Iklan, Versi

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer4_us-en.png" src="https://files.readme.io/a9b80aaeb0f34a3054bfb97bb72ff2ab549ff88ae4f6af43bf1c5e1ab604d3d3-360010368537.png" width="206px" />](https://files.readme.io/a9b80aaeb0f34a3054bfb97bb72ff2ab549ff88ae4f6af43bf1c5e1ab604d3d3-360010368537.png)
      </td>
    </tr>
    <tr>
      <td>
        Rincian metrik berdasarkan elemen hierarki periklanan
      </td>
      <td>
        Elemen yang tersedia: Sumber media, Kampanye, ID Situs, Iklan, Iklan, Versi

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer5_us-en.png" src="https://files.readme.io/f201592b110b3137329f7ad3c48c53e20639fb664383d76ceba2a347e969f6e4-360010368657.png" width="198px" />](https://files.readme.io/f201592b110b3137329f7ad3c48c53e20639fb664383d76ceba2a347e969f6e4-360010368657.png)
      </td>
    </tr>
    <tr>
      <td>
        Event Teratas
      </td>
      <td>
        Acara teratas berisi pengguna organik dan non-organik. Gunakan filter sumber media, di bagian atas halaman, untuk membedakan antara pengguna organik dan non-organik atau per sumber media yang dipilih.

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer6_us-en.png" src="https://files.readme.io/1a569224cec155b54a96433d6b2e36918c9c6f7924629cb09dcfc859358199c3-360010454658.png" width="245px" />](https://files.readme.io/1a569224cec155b54a96433d6b2e36918c9c6f7924629cb09dcfc859358199c3-360010454658.png)
      </td>
    </tr>
    <tr>
      <td>
        Negara-negara teratas
      </td>
      <td>
        [<Image alt="mceclip1.png" src="https://files.readme.io/aba8db1a2aa7a90d5fd5c07e184eebd6d09762c5564f87f87f584d91686a59c6-360011169298.png" width="181px" />](https://files.readme.io/aba8db1a2aa7a90d5fd5c07e184eebd6d09762c5564f87f87f584d91686a59c6-360011169298.png)

        Catatan:  Bagan ini tersedia untuk agensi dan bukan untuk pemasang iklan
      </td>
    </tr>
    <tr>
      <td>
        Salinan postback
      </td>
      <td>
        Bagan ini tersedia setelah Anda mengonfigurasi aplikasi untuk mengirim <Anchor target="_blank" href="/marketers/id/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">salinan postback</Anchor> iOS 15+ ke AppsFlyer. Jika tidak ada grafik yang ditampilkan, pertimbangkan bahwa:

        * Kami tidak menerima postback dari aplikasi atau belum menerimanya. Verifikasi dengan pengembang aplikasi Anda, bahwa titik akhir AppsFlyer telah disetel di aplikasi dan versi aplikasi yang diperbarui ada di App Store.
        * Tidak ada postback yang diterima (artinya tidak ada instalasi SKAN) untuk tanggal yang dipilih atau Anda memilih tanggal lebih awal dari 1 Januari 2022.

        Catatan:

        * Semua metrik lain di dasbor dihitung menggunakan postback iOS yang diteruskan oleh jaringan iklan ke AppsFlyer atau dari data yang disediakan langsung oleh SRN. Harapkan perbedaan antara metrik salinan postback dan metrik lainnya.
        * Bagan salinan postback tidak tersedia untuk agensi.

        [<Image alt="PostbackCopy.png" src="https://files.readme.io/0f2d290817650c87b3719ce2cdd107fdf66f62f575d3b4b75fcdd1f8330a04a9-4417816656657.png" width="207px" />](https://files.readme.io/0f2d290817650c87b3719ce2cdd107fdf66f62f575d3b4b75fcdd1f8330a04a9-4417816656657.png)

        | Dimensi | Catatan |
        | --- | --- |
        | Sumber media | Sumber media dikaitkan dengan penginstalan. <br /><br />* Metrik:<br />  * **Tingkat pengunduhan ulang:** Metrik berhubungan dengan postback menggunakan SKAdNetwork V2.0+.<br />  * Attributed touch-type Keterlibatan, tampilan, atau klik, yang mengarah ke penginstalan. Metrik terkait dengan postback menggunakan SKAdNetwork V2.2+<br />* Catatan: Jika ID sumber media ditampilkan, saat ini kami tidak memiliki nama yang terkait dengan ID tersebut. Minta sumber media untuk memperbarui ID SKAdNetwork mereka di AppsFlyer. |
        | Aplikasi sumber | Nama penerbit iklan, dengan kata lain, nama aplikasi tempat pengguna terlibat dengan iklan Anda.<br /><br />* Metrik<br />  * **Jumlah instal**: Jumlah penginstalan yang dibawa oleh aplikasi penerbit.<br />* Catatan:<br />  * Jika Apple menahan ID aplikasi sumber, karena ambang privasi, aplikasi sumber ditampilkan sebagai tidak *dikenal*.<br />  * Jika nama aplikasi tidak dapat ditemukan, ID aplikasi akan ditampilkan |
        | ID aplikasi sumber | ID penerbit iklan, dengan kata lain, ID aplikasi tempat pengguna terlibat dengan iklan Anda.<br /><br />* Metrik<br />  * **Jumlah instal**: Jumlah penginstalan yang dibawa oleh ID aplikasi penerbit. |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="metrics" />

<Accordion title="Metrik">

* Pilih metrik dari yang tersedia. [Metrik yang dimodel](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) kan mempertimbangkan tingkat CV nol.
* Tetapkan grup primer dan sekunder berdasarkan dimensi untuk menelusuri metrik kinerja.

[![SKAdNetwork_Dashboard_AppsFlyer7_us-en.png](https://files.readme.io/434a848c7a33c052c80101788b066f4bdb90ef36423ea140f85c1cc59ace2ebf-360010368617.png)](https://files.readme.io/434a848c7a33c052c80101788b066f4bdb90ef36423ea140f85c1cc59ace2ebf-360010368617.png)

Tentang tabel metrik:

* Gunakan tabel untuk membandingkan kinerja kampanye dan sumber media.
* Awalnya, 20 sumber media teratas ditampilkan, diurutkan berdasarkan jumlah pemasangan dalam urutan menurun.
* Untuk mengurutkan tabel, klik pada header kolom. Klik lagi untuk membalikkan urutan pengurutan.
* Metrik terkait biaya (biaya, tayangan, dan klik) tersedia jika setidaknya 1 penginstalan dikaitkan dengan kampanye tertentu. Catatan:
  * Kampanye dengan 0 penginstalan tidak ditampilkan sama sekali.
  * Beberapa jaringan iklan melaporkan metrik terkait biaya di tingkat iklan dan iklan, tetapi melaporkan penginstalan di tingkat kampanye. Dalam hal ini, metrik terkait iklan dan biaya iklan ditampilkan dengan metrik penginstalan 0.
* Batasan dimensi tipe sentuh yang diatribusikan: Metrik terkait biaya tidak dapat dipecah dan ditampilkan sebagai Tidak Diketahui.

Metrik tabel:

<table><tbody><tr><th>Metrik</th><th>Formula/komentar</th></tr><tr><td><p><span>Penginstalan</span></p></td><td><ul><li>Total instalasi</li><li>Klik-tayang <ul><li><p>Pengguna dibawa melalui atribusi klik-tayang</p></li><li><p>Tersedia untuk pemasangan yang direkam mulai 22 Desember 2021</p></li></ul></li><li>Lihat-Tayang (View-Through) <ul><li>Tersedia untuk pemasangan yang direkam mulai 22 Desember 2021</li><li>Berlaku untuk jaringan iklan yang menerapkan SKAdNetwork V2.2+</li></ul></li></ul><p>Data ini berasal dari bidang fidelity_type di postback</p></td></tr><tr><td><p>Nilai konversi null</p></td><td>Postback memiliki nilai konversi nul/Install \* 100 </td></tr><tr><td><p><span>Tayangan</span></p></td><td></td></tr><tr><td><p><span>Klik</span></p></td><td> </td></tr><tr><td><p><span>Tingkat klik untuk menginstal</span></p></td><td>Penginstalan / Klik \*100 </td></tr><tr><td><p><span>Pengguna yang dikonversi</span></p></td><td><p><span>Jumlah pengguna unik yang melakukan event pengukuran yang ditentukan.</span></p><ul><li><span>Modus kustom: Mode kustom: Selalu af_skad_revenue (jika ada hal lain yang dipilih, pengguna yang dikonversi tetap kosong)</span></li><li><span>Modus SKAN 4: Mode kustom: Selalu af_skad_revenue (jika ada hal lain yang dipilih, pengguna yang dikonversi tetap kosong)</span></li><li><span>Mode pendapatan: Always af_skad_revenue</span></li><li><span>Mode konversi: Acara dalam aplikasi dipilih di pengaturan dasbor</span></li><li> <span>Mode interaksi: In-app event seperti yang ditetapkan di Conversion Studio</span><span></span> </li></ul></td></tr><tr><td>Pengguna yang dikonversi / Penginstalan</td><td> </td></tr><tr><td><p><span>Total pendapatan</span></p></td><td>Pendapatan, termasuk data model dari nilai null. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Pelajari lebih lanjut</a> </td></tr><tr><td><p><span>Total pendapatan (tidak dimodelkan)</span></p></td><td>Pendapatan dilaporkan melalui nilai konversi. Data yang dimodelkan tidak termasuk</td></tr><tr><td><p><span>Revenue D1-D2</span></p></td><td>Pendapatan untuk jendela SKAN 1 (hari 1-2 kecuali dimodifikasi), termasuk data model dari nilai nol. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Pelajari lebih lanjut</a> </td></tr><tr><td><p><span>Pendapatan D1-D2 (tidak dimodelkan)</span></p></td><td>Pendapatan diterima di jendela SKAN 1 (hari 1-2 kecuali diubah). Data yang dimodelkan tidak termasuk</td></tr><tr><td><p><span>Pendapatan D3-D7</span></p></td><td><span>Pendapatan untuk jendela SKAN 2 (hari 3-7 kecuali diubah)</span></td></tr><tr><td><p><span>Pendapatan D8-D35</span></p></td><td><span>Pendapatan untuk jendela SKAN 3 (hari 8-35 kecuali diubah)</span></td></tr><tr><td><p><span>Biaya</span></p></td><td><ul><li><span>Seperti yang dilaporkan oleh jaringan iklan</span></li><li>Jika nama kampanye berubah, biaya ditampilkan di bawah nama kampanye terbaru yang digunakan. (Jika ada beberapa nama kampanye)</li></ul></td></tr><tr><td>ARPU</td><td><ul><li>Pendapatan rata-rata per pengguna, termasuk data model dari nilai null. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Pelajari lebih lanjut</a> </li><li>Rumus: Pendapatan ($) (dimodelkan) / Penginstalan</li></ul></td></tr><tr><td>ARPU (tanpa model)</td><td><p>Pendapatan rata-rata per pengguna, data model tidak termasuk</p></td></tr><tr><td>ROI</td><td><ul><li>Pengembalian investasi, termasuk data model dari nilai null. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Pelajari lebih lanjut</a> </li><li>Rumus: (Pendapatan ($) (dimodelkan) - Biaya) /Biaya \* 100</li></ul></td></tr><tr><td>ROI (tanpa model)</td><td><p>Pengembalian investasi, data model tidak termasuk</p></td></tr><tr><td>ROAS</td><td><ul><li>Pengembalian pengeluaran iklan, termasuk data model dari nilai null. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Pelajari lebih lanjut</a> </li><li>Rumus: (Pendapatan ($) (dimodelkan) /Biaya\* 100</li></ul></td></tr><tr><td>ROAS (tanpa model)</td><td><p>Pengembalian pengeluaran iklan, data model tidak termasuk</p></td></tr><tr><td>eCPI</td><td> </td></tr><tr><td colspan="2"><strong>Metrik in-app event</strong></td></tr><tr><td>Nama in-app event</td><td> </td></tr><tr><td>eCPA</td><td><ul><li>Biaya efektif per tindakan, termasuk data model dari nilai null. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Pelajari lebih lanjut</a> </li><li>Rumus: Biaya/Pengguna unik yang melakukan acara (dimodelkan)</li></ul></td></tr><tr><td>eCPA (unmodeled)</td><td><p>Biaya efektif per tindakan, data yang dimodelkan tidak termasuk</p></td></tr><tr><td>Jumlah total event</td><td>Total kejadian event di semua jendela, termasuk data model dari nilai null. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Pelajari lebih lanjut</a> </td></tr><tr><td>Jumlah total peristiwa (tidak dimodelkan)</td><td>Total kejadian peristiwa di semua jendela, data yang dimodelkan tidak termasuk</td></tr><tr><td>Jumlah event <span>D1-D2</span> </td><td>Kemunculan event untuk jendela 1 (hari 1-2 kecuali diubah), termasuk data model dari nilai null. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Pelajari lebih lanjut</a> </td></tr><tr><td>Jumlah peristiwa <span>D1-D2 (tanpa model)</span> </td><td>Kemunculan event untuk jendela 1 (hari 1-2 kecuali diubah), data yang dimodelkan tidak termasuk</td></tr><tr><td>Jumlah event <span>D3-D7</span> </td><td>Kemunculan event untuk jendela 2 (hari 3-7 kecuali dimodifikasi), termasuk data model dari nilai null.<span> <span>Pelajari lebih lanjut</span>.</span> </td></tr><tr><td>Jumlah event <span>D8-D35</span> </td><td>Kemunculan event untuk jendela 3 (hari 8-35 kecuali diubah), termasuk data model dari nilai null.<span> <span>Pelajari lebih lanjut</span>.</span> </td></tr></tbody></table>

</Accordion>

<div id="modeled-metrics-and-null-cv" />

<Accordion title="Metrik yang dimodelkan dan CV nol">

Pelaporan SKAdNetwork (SKAN) dapat dibatasi karena:

* SKAN bergantung pada nilai konversi (CV) yang dibatasi hingga 6 bit, menghasilkan 64 kemungkinan nilai (0-63).
* Apple terkadang menahan CV yang sebenarnya (dan mengembalikan data sebagai "null") untuk menjaga privasi pengguna.
* Data hanya tersedia dari dalam jendela pengukuran dan nilai seumur hidup penuh (LTV) tidak diketahui.

Data model SKAN memecahkan masalah ini:

* Nilai konversi yang dimodelkan alih-alih nilai null.
* Pendapatan yang dimodelkan dan kejadian event.
* Pemasang iklan mendapatkan gambaran yang lebih lengkap terkait performa LTV aplikasi dan kampanye

Metrik model yang tersedia meliputi:

* Pendapatan
* Hitungan event
* eCPA
* ARPU
* ROI
* ROAS

<Anchor target="_blank" href="/marketers/id/docs/skan-modeled-data">Pelajari lebih lanjut tentang data SKAN yang dimodelkan</Anchor>

</Accordion>

<div id="appsflyer-attribution-vs-skan-attribution" />

<Accordion title="Atribusi AppsFlyer vs. Atribusi SKAN">

Metrik SKAN berbeda dari yang tersedia menggunakan model atribusi AppsFlyer. Tabel berikut menyebutkan penyebab utama.

Definisi:

* **Waktu:** Asumsikan jendela aktivitas default 24 jam (48 jam setelah Anda meningkatkan ke SKAN 4).
* **SDK:** AppsFlyer SDK tertanam di aplikasi.
* **Peraturan**: <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model">Model Atribusi AppsFlyer</Anchor>

<div id="attribution-framework-differences" />

#### Perbedaan kerangka atribusi

| Konsep | SKAN | AppsFlyer |
| --- | --- | --- |
| Metodologi atribusi didukung | Apple SKAN untuk atribusi klik dan tampilan melalui. Berisi lalu lintas kampanye aplikasi-ke-aplikasi dari jaringan iklan dan SRN yang mendukung SKAN. | **<Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model">Model atribusi AppsFlyer mendukung beberapa metode</Anchor> dan skenario atribusi:**<ul><li>Web seluler</li><li>View-Through (Lihat-Tayang)</li><li>Klik-tayang</li><li>Klip App</li><li>Atribusi web</li><li>Apple Search Ads</li><li>Media yang Dimiliki Sendiri</li><li>Lalu lintas SRN (pengguna yang menyetujui)</li><li>Dan banyak lagi</li></ul> |
| Sumber data utama | <ul><li>Postingan SKAN</li><li>SDK</li></ul> | SDK dan solusi terkait.  Contoh: Event Server ke Server |
| Keaktualan data | <Anchor target="_blank" href="/marketers/id/docs/about-data-freshness-and-timezone-support#skan">Kesegaran data SKAN.</Anchor> | Real-time saat pengguna meluncurkan dan menggunakan aplikasi. |
| zona waktu | UTC | Zona waktu khusus aplikasi |
| Install time | Berasal dari waktu kedatangan postback iOS. | Dilaporkan oleh SDK. |
| Jendela aktivitas | Aktivitas pengguna selama jendela pengukuran tetap, dimulai dengan aplikasi terbuka. | Berisi data LTV dari tanggal pemasangan hingga saat ini.<br /><br />Gunakan Kohort untuk melihat data terbatas pada kohort hari 0 atau kohort hari 1, atau keduanya bersama-sama untuk melihat periode pengukuran yang sebanding.<br /><br />Pertimbangkan, kohort hari 0 terdiri dari kurang dari 24 jam aktivitas. Misalnya, pengguna yang menginstal pada pukul 18:00 pada hari tertentu memiliki 6 jam aktivitas pada hari kohort 0. |
| Penginstalan dilaporkan oleh | <ul><li>SKAN Terbatas untuk penginstalan non-organik dan unduhan ulang non-organik.</li><li>**SDK**: Semua instalasi dilaporkan. Hanya penginstalan pertama yang dihitung untuk tujuan metrik. Artinya reatribusi diabaikan.</li></ul> | SDK melaporkan semua penginstalan yang dikategorikan menggunakan Aturan ke dalam penginstalan pertama kali dan penargetan ulang penginstalan ulang (atribusi ulang). |
| Tingkat perincian iklan | Kampanye, set iklan, ID iklan, iklan, dan ID iklan. | Hirarki penuh: Kampanye, ID kampanye, adset, parameter tambahan seperti saluran dan mitra. |
| Pengunduhan ulang vs. penginstalan ulang | Pengunduhan ulang terkait dengan tindakan pengguna ID Apple tertentu. Mereka tidak paralel dengan atribusi ulang. | Penargetan ulang (atribusi ulang interaksi ulang) tercermin di dasbor Penargetan Ulang. Mereka tidak sejajar dengan unduhan ulang. |

<div id="metric-differences" />

#### Perbedaan metrik

| Metrik | SKAN | Atribusi tradisional |
| --- | --- | --- |
| Install Non-Organik | Hitungan postback iOS valid yang diterima oleh AppsFlyer.<br /><br />Pertimbangkan, AppsFlyer tidak mendapatkan postback dari jaringan iklan yang belum menyelesaikan integrasi SKAN dengan AppsFlyer.<br /><br />Hal ini dapat menyebabkan kurangnya jumlah pemasangan non-organik dan peningkatan pemasangan organik. | <ul><li>Dilaporkan oleh SDK.</li><li>Dikaitkan dengan sumber media.</li><li>Dihitung menggunakan Aturan.</li></ul> |
| Organic installs (Instalasi organik) | Penginstalan SDK dikurangi instalasi SKAN. | <ul><li>Dilaporkan oleh SDK.</li><li>Tidak dikaitkan dengan sumber media mana pun.</li><li>Dihitung menggunakan Aturan.</li></ul> |
| Pendapatan | Non-organik* Pendapatan dilaporkan oleh postbacks SKAN.<br /><br />organik Pendapatan yang dilaporkan oleh acara dalam aplikasi SDK dikurangi pendapatan non-organik. **Catatan** : Metrik organik tidak selalu tersedia. [Pelajari lebih lanjut](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations). | <ul><li>Dilaporkan oleh SDK dan API server-to-server.</li></ul> |
| Pendapatan Iklan | Tersedia: | Pendapatan iklan tingkat pengguna dikaitkan berdasarkan IDFV |
| ROS/RED | Pendapatan selama jendela pengukuran. | <ul><li>LTV</li><li>Metrik UA dan kampanye penargetan ulang.</li></ul> |

</Accordion>

<div id="faq-skan-discrepancies" />

<Accordion title="Perbedaan FAQ—SKAN">

| Alasan | Perbedaan |
| --- | --- |
| A | **Q: Mengapa nomor konversi di dasbor AppsFlyer berbeda dengan dasbor jaringan iklan?**<br /><br />**A**: Alasan perbedaan<ul><li>**Tanggal pemasangan vs. tanggal kedatangan postback:**<ul><li>AppsFlyer: Tanggal pemasangan diturunkan menggunakan rumus yang memperhitungkan waktu kedatangan postback iOS, panjang jendela, dan waktu tunda postback.</li><li>Jaringan iklan  Biasanya hanya menggunakan waktu kedatangan postback iOS sebagai tanggal pemasangan, tanpa penyesuaian.</li><li>Gunakan opsi **tampilan dengan tanggal kedatangan postback** di dasbor untuk menghilangkan perbedaan ini.</li></ul></li><li>**Validasi postback:** AppsFlyer memvalidasi postback iOS yang diterima dan memastikan bahwa tanda tangan Apple valid. Jaringan iklan dapat mengirim postback yang tidak valid yang diabaikan oleh AppsFlyer.</li><li>**Postback yang hilang**: Postback iOS harus dikirim oleh jaringan iklan ke AppsFlyer. AppsFlyer tidak mendapatkan postback langsung dari perangkat. Jika postback hilang, AppsFlyer tidak memiliki cara untuk mengetahui hal ini.</li></ul> |
| B | **Q**: **Perbedaan antara <Anchor target="_blank" href="/marketers/id/docs/skan-aggregated-performance-report-api">API kinerja SKAN dan dasbor versus API</Anchor> <Anchor target="_blank" href="/marketers/id/docs/skan-aggregated-postback-arrival-date-api">postback agregat SKAN?</Anchor>**<br /><br />**A**: Rentang tanggal API postback berhubungan dengan tanggal di mana AppsFlyer menerima postback. Rentang tanggal API kinerja berhubungan dengan tanggal pemasangan yang diturunkan seperti yang dijelaskan dalam alasan A. |
| C | **Q: Apakah semua jaringan iklan melaporkan Geo?**<br /><br />**A:** No. |
| D | **Q: Mengapa ada perbedaan antara dasbor Ikhtisar dan dasbor SKAN.**<br /><br />**A:** Lihat bagian sebelumnya untuk ikhtisar tentang alasan perbedaan. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Karakteristik | Catatan |
| --- | --- |
| Kejadian peristiwa yang dimodelkan | <ul><li>Peristiwa yang dimodelkan didasarkan pada rumus yang dijelaskan dalam [metrik yang dimodelkan dan CV nol](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv).</li><li>Rumus diterapkan per baris data. Hal ini dapat menyebabkan perbedaan antara jumlah event yang dimodelkan untuk sumber media tertentu dan jumlah jumlah event yang dimodelkan dari kampanyenya.</li></ul> |
| Tanggal kedatangan Postback | Tanggal akhir dalam rentang tanggal terbatas pada hari ketika instalasi terakhir direkam. |
| Data organik | <ul><li>Untuk <Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio#skan-4">SKAN 4</Anchor> dan <Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio#custom">mode kustom</Anchor>, data organik tersedia untuk penginstalan, bukan untuk acara dalam aplikasi dan pendapatan keseluruhan.</li><li>Untuk <Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio#fixed-modes">mode tetap</Anchor>, data organik tersedia untuk penginstalan dan acara dalam aplikasi.</li><li>Pertimbangkan untuk menggunakan SSOT untuk melihat data organik, karena SSOT menduplikasi event yang dikaitkan dengan model SKAN dan AppsFlyer.</li><li>Jika data atribusi AppsFlyer (penginstalan baru untuk organik dan non-organik) dikurangi data atribusi SKAN (pemasangan non-organik) sama dengan angka negatif, dasbor SKAN menampilkan 0 di bawah penginstalan organik.</li></ul> |
| Data historis | Data konversi paling awal didukung: 1 November 2020 |
| Mata Uang | Menampilkan dalam USD atau dalam mata uang lokal khusus aplikasi seperti yang ditetapkan pada halaman <Anchor target="_blank" href="/marketers/id/docs/app-settings">pengaturan aplikasi</Anchor>. |
| Zona waktu | Untuk data yang dilaporkan SKAN, penginstalan dan tampilan event menggunakan UTC, dengan pengecualian data Meta dan Google SKAN, yang zona waktunya didasarkan pada zona waktu yang dikonfigurasi di akun Meta dan Google Anda masing-masing. |

</Accordion>

<div id="see-also" />

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide">Panduan Solusi AppsFlyer SKAN</Anchor>
> * <Anchor target="_blank" href="/marketers/id/docs/about-att-and-skan">Apa beda—Pembaruan terkait AppsFlyer iOS 14</Anchor>

<div data-zendesk-anchors="dashboard-principles=prinsip-dasbor 01H81P8JPZM24J0536GKBPNFMJ=prinsip-dasbor skan-dashboard-view-options=opsi-tampilan-dasbor-skan 01H81P8JPZC5K0KZR64P084N4W=opsi-tampilan-dasbor-skan dashboard-use=penggunaan-dasbor 01H81P8JPZGSHQVMG27YEJPARH=penggunaan-dasbor 01H81P8JPZ93G4EQY343SV2B1Q=dashboard-settings 01H81P8JPZV5F4VCZHR537HREH=filter-options 01H81P8JQ0KRGXWCVT82YW30CS=headline-metrics 01H81P8JQ0ETB0W3SGS56CBCX8=charts 01H81P8JQ0KK1NMRGFR0GBX4EK=metrics 01H81P8JQ0ZKGTRWNW95D015Z7=modeled-metrics-and-null-cv 01H81P8JQ18NGP8Z74D02DMQ7P=appsflyer-attribution-vs-skan-attribution attribution-framework-differences=perbedaan-kerangka-atribusi 01H81P8JQ1VTYX3382WDXDMVT3=perbedaan-kerangka-atribusi metric-differences=perbedaan-metrik 01H81P8JQ1M8M9TSHF0C12Z2QE=perbedaan-metrik faq%E2%80%94skan-discrepancies=faq-skan-discrepancies 01H81P8JQ157YYNX9C527ES4C8=faq-skan-discrepancies 01H81P8JQ1T3DE29Y14VARKASK=traits-and-limitations h_01HE7SWGPWNWG26CEN40VSTA9J=lihat-juga" />
