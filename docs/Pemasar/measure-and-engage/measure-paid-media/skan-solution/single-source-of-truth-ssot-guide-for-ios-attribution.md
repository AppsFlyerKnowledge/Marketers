---
title: 'Panduan Source of Truth (SSOT) untuk atribusi iOS '
metadata:
  keywords:
    - iOS
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
  created_at: '2021-11-11T09:28:42Z'
  edited_at: '2024-01-15T10:40:45Z'
  id: 4410634145425
  locale: id
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/id/articles/4410634145425
---
> **Sekilas**:Dalam konteks lingkungan iOS 14+, AppsFlyer menyatukan data dari beberapa metode pencocokan atribusi seperti IDFA, IDFV, SKAN, Apple Search Ads, dan sebagainya, serta memberikan gambaran lengkap tentang kinerja kampanye aplikasi. Tidak ada metode atribusi yang memberikan gambaran kinerja aplikasi lengkap. Tantangannya adalah menghitung satu pengguna tertentu karena pengguna yang sama dapat diatribusikan dengan dua metode. Mekanisme AppsFlyer Single Source of Truth (SSOT) melakukan hal itu. Laporan dan metrik SSOT benar dan akurat serta menghitung pengguna yang sama hanya sekali.

<Embed title="Panduan Source of Truth (SSOT) untuk atribusi iOS" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/545isomgo1" providerUrl="https://fast.wistia.com" />

## Cara mendapatkan data kinerja iOS 14+ yang sebenarnya

Bacaan terkait: <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide">panduan solusi SKAN</Anchor> |  <Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio">Studio konversi SKAN</Anchor> | Dasbor ikhtisar

Mulai iOS 14, AppsFlyer mengatribusikan pengguna iOS menggunakan data dari beberapa aliran data, termasuk SKAdNetwork, pengguna yang menyetujui ATT, pemodelan probabilistik, wawasan berbasis inkremental, dan API khusus untuk Apple Search Ads. Tidak adanya IDFA membuat hampir tidak mungkin untuk menyatukan metode atribusi bersama-sama tanpa menyertakan data duplikat.

Mekanisme SSOT menghilangkan data penginstalan duplikat dan memperbaiki atribusi pengguna yang salah atribusi. Dengan kata lain, pengguna yang diatribusikan sebagai organik yang seharusnya diatribusikan ke sumber media non-organik. Akibatnya, jumlah penginstalan yang diatribusikan ke kampanye dikoreksi dan metrik terkait biaya dan pendapatan terkait, seperti eCPI, ROI, dan ROAS, juga dihitung dengan benar.

Sederhananya, mekanisme SSOT menandai penginstalan SKAN yang juga diatribusikan menggunakan jenis pencocokan lain. Flag dipertimbangkan dalam menghitung metrik gabungan untuk menghindari penghitungan pengguna yang sama dua kali. Demikian pula, Anda menggunakan flag saat memproses data lengkap SKAN.

Untuk menyertakan tanda SSOT dalam data Anda, Anda harus mengaktifkan SSOT di Studio Konversi.

<div id="turn-on-single-source-of-truth" />

<Accordion title="Aktifkan Single Source of Truth">

![SSOTControl.png](https://files.readme.io/fd99117e9278ebda3b1f0cc137afb266643e5e45325345ec51aeb58c16d4f13c-31247514683153.png)

**Untuk mengaktifkan SSOT:**

1. Sebelum Anda mulai, pertimbangkan kebijakan penagihan <Anchor target="_blank" href="https://content.appsflyer.com/ios-hub/billing/">Single Source of Truth</Anchor> Appsflyer.
2. Di AppsFlyer, buka **Configuration**  >  **SKAN Conversion Studio** .
3. Pilih mode **Custom** .
4. Aktifkan **Single Source of Truth.**
5. Selesaikan pengaturan sesuai kebutuhan.

Lihat <Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio">Studio Konversi SKAN</Anchor>

</Accordion>

## Dasbor Ikhtisar Single Source of Truth

![SSOTisNowOn.png](https://files.readme.io/8e21fd0c64bb85fb94af752eb037472726d68cd55bf028dc5306b0acb398d199-31247490958225.png)

Tampilan Single Source of Truth yang tersedia melalui dasbor Ikhtisar memberikan gambaran lengkap tentang metrik kinerja non-organik. Dalam tampilan:

* Metrik penginstalan benar.
* Metrik terkait biaya dan pendapatan, yang bergantung pada metrik penginstalan, termasuk eCPI, ARPU, dan ROAS, dihitung dengan benar.
* Metrik organik disesuaikan setelah memperhitungkan penginstalan yang salah.

Bagian ini menyoroti perbedaan dan fitur unik dari tampilan SSOT. Ini mengasumsikan bahwa Anda sudah familiar dengan dasbor Ikhtisar.

<div id="turn-on-single-source-of-truth-view" />

<Accordion title="Aktifkan tampilan Single Source of Truth">

Data dalam tampilan SSOT tersedia 3-5 hari setelah Anda mengaktifkan Single Source of Truth di Conversion Studio (Studio Konversi).

**Untuk mengaktifkan tampilan Single Source of Truth**:

1. Sebelum Anda mulai, pastikan bahwa di Conversion Studio (Studio Konversi) <Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio#single-source-of-truth">Single Source of Truth</Anchor> diaktifkan.
2. Di AppsFlyer, buka **Dashboard** > **Overview.**   

   <Image alt="SelectSavedReport.png" src="https://files.readme.io/863a9c66c37e031a1f1b2a7fb3e0c68eb9c29405283214e68a432357c35524dd-31247514684177.png" width="243px" />
3. Klik ▼.
4. Pilih **Ikhtisar Lite** .  
   Tombol Single Source of Turth ditampilkan.  

   <Image alt="SSOTviewon.png" src="https://files.readme.io/7b0a664f0882dad46e7239b5363592717358a79d920377dde13aa9c5dfbe84c3-31247514684433.png" width="246px" />
5. Aktifkan Single Source of Truth.
6. Terjadi salah satu berikut ini:
   * Metrik dasbor dan tampilan grafik.  
     Bagian berikut menjelaskan data yang tersedia. Lihat bagian berikutnya tentang data yang ditampilkan.  
     Simpan tampilan SSOT sebagai laporan baru. Untuk melakukannya:  
     1. Klik ▼.
     2. Klik **+ Save new report.**
     3. Masukkan nama laporan.
     4. Klik **Simpan**.
   * Data tidak ditampilkan. Pertimbangkan bahwa diperlukan waktu 3-5 hari setelah mengaktifkan SSOT hingga data ditampilkan. Tunggu hingga periode ini berlalu dan kunjungi dashboard lagi.

Nonaktifkan tombol SSOT kapan saja untuk melihat data biasa dengan dimensi yang tidak tersedia dalam tampilan SSOT.  Melakukan hal tersebut memungkinkan Anda melihat data yang lebih terperinci.

</Accordion>

<div id="ssot-view-considerations" />

<Accordion title="pertimbangan tampilan SSOT">

Dalam tampilan SSOT:

* **Nilai konversi null (CV)**: Sesuai model. Pembelajaran mesin tingkat lanjutan digunakan untuk memberi contoh nilai null yang diatribusikan oleh AppsFlyer atau SKAN menggunakan [flag af\_attribution](/docs/single-source-of-truth-ssot-guide-for-ios-attribution#bidang-flag-atribusi). Jika dikaitkan dengan SKAN, semua pengukuran SKAN setelah penginstalan disertakan dalam dashboard SSOT. <Anchor target="_blank" href="/marketers/id/docs/skan-modeled-data">Pelajari lebih lanjut</Anchor>
* **Pengunduhan ulang**: Disertakan dalam metrik penginstalan. Tidak ada pemisahan antara penginstalan vs pengunduhan ulang.
* **Zona Waktu**: Penginstalan yang dilaporkan AppsFlyer dan event yang ditampilkan dalam UTC atau dalam zona waktu lokal khusus aplikasi sebagaimana diatur pada <Anchor target="_blank" href="/marketers/id/docs/app-settings">halaman pengaturan aplikasi</Anchor>. Untuk data yang dilaporkan SKAN, penginstalan dan tampilan event menggunakan UTC, dengan pengecualian data Meta dan Google SKAN, yang zona waktunya didasarkan pada zona waktu yang dikonfigurasi di akun Meta dan Google Anda masing-masing.
* **Mata Uang**: Ditampilkan dalam USD atau mata uang lokal khusus aplikasi sebagaimana diatur di <Anchor target="_blank" href="/marketers/id/docs/app-settings">halaman pengaturan aplikasi</Anchor>.

#### Pertimbangan filter

Pertimbangkan dampak filter pada tampilan data dan metrik seperti yang dijelaskan dalam tabel berikut.

| Filter | Pertimbangan |
| --- | --- |
| Single Source of Truth | Untuk melihat metrik Single Source of Truth, pastikan kontrolnya aktif. |
| Lihat jenis | <ul><li>**Akuisisi Pengguna:** Tampilan pilihan untuk data SSOT.</li><li>**Penargetan ulang** : SKAN tidak mendukung penargetan ulang.</li><li>**Terpadu** : Instal kampanye berisi data SSOT. Kampanye penargetan ulang tidak terpengaruh oleh SSOT.</li></ul> |
| Tanggal | <ul><li>[Praktik terbaik] Pilih rentang tanggal 7+ hari yang tidak termasuk 3 hari terakhir untuk mendapatkan hasil yang akurat.</li><li>Pertimbangkan:<ul><li>Periode kurang dari 7 hari telah mengurangi akurasi karena perbedaan zona waktu dan estimasi waktu penginstalan SKAN.</li><li>Penginstalan Google SKAN dapat dilaporkan dengan penundaan hingga 13 hari.</li></ul></li><li>Tanggal paling awal yang tersedia biasanya 3 hari setelah Anda mengaktifkan SSOT. AppsFlyer menentukan tanggal ini.</li><li>Contoh pemilihan tanggal yang optimal:<ul><li>Jika tanggal saat ini adalah 10 Februari dan Anda mengubah SSOT pada  29 Januari. Anda dapat memilih 1-7 Februari.</li></ul></li></ul> |
| Filter kampanye | Filter hierarki kampanye tersedia:<ul><li>Media Source</li><li>Kampanye</li></ul> |
| KPI Judul | KPI judul yang tersedia di dasbor SSOT memungkinkan Anda melihat:<ul><li>Akuisisi pengguna: Baik non-organik maupun organik</li><li>Duplikat SKAN</li><li>Penargetan ulang: Interaksi ulang dan atribusi ulang</li><li>Biaya</li><li>eCPI</li><li>Jumlah (in-app) event palsu</li></ul>Ada nilai persentase untuk masing-masing KPI. Nilai ini menunjukkan keterkaitan KPI yang disajikan dengan rentang tanggal paralel sebelumnya. Misalnya, minggu ini dibandingkan dengan minggu lalu, atau hari apa pun yang dipilih dalam rentang tanggal dibandingkan dengan jumlah hari yang sama sebelumnya: Misalnya, jika menunjukkan peningkatan X% dalam penginstalan, berarti penginstalan pada tanggal paralel sebelumnya lebih rendah X%. |
| Grafik | **Dimensi yang tersedia:**<ul><li>Metode atribusi:<ul><li>Model AF: Penginstalan yang cocok dengan lebih dari satu metode termasuk SKAN. Di dashboard, catatan SKAN diabaikan untuk menghindari penghitungan ganda untuk penginstalan yang sama. Dalam data lengkap SKAN, af\_attribuiton\_flag dari penginstalan disetel ke true.</li><li>Keunikan SKAN: Penginstalan hanya cocok dengan SKAN dan tidak dengan metode lain. Dalam data lengkap SKAN, af\_attribution\_flag dari penginstalan disetel ke false.</li></ul></li><li>Jenis Atribusi</li><li>Attributed touch-type</li><li>Kampanye</li><li>ID kampanye</li><li>Media Source</li><li>Sumber</li><li>ID Aplikasi (untuk beberapa diagram)</li><li>Geo (geo SKAN <Anchor target="_blank" href="/marketers/id/docs/skan-modeled-data#geo">dimodelkan</Anchor>)</li><li>Nama in-app event (artinya nama in-app event tertentu seperti yang dikonfigurasi di SKAN Conversion Studio).</li></ul>**Metrik:**<br /><br />Seperti yang dijelaskan di bagian metrik. |
| Tabel | **Pengelompokan:**<ul><li>[Default] Tabel dikelompokkan berdasarkan sumber Media dan kampanye.</li><li>Opsi pengelompokan termasuk: Sumber media, jenis atribusi, metode atribusi, kampanye, ID kampanye, Jenis sentuhan yang diatribusikan, tanggal, sumber, dan kombinasinya. **Catatan**: Geo SKAN <Anchor target="_blank" href="/marketers/id/docs/skan-modeled-data#geo">dimodelkan</Anchor>.</li><li>Jika Anda memilih pengelompokan dengan dimensi yang hanya berlaku untuk lalu lintas non-organik, tabel akan menampilkan N/A untuk sumber media organik.</li></ul>**Metrik:**<br /><br />Seperti yang dijelaskan di bagian metrik. |

</Accordion>

<div id="metrics" />

<Accordion title="Metrik">

Metrik tersedia di dashboard SSOT:

| Metrik | Deskripsi dan pertimbangan |
| --- | --- |
| Grouping | <ul><li>[Default] Tabel dikelompokkan berdasarkan sumber Media dan kampanye.</li><li>Opsi pengelompokan meliputi: Sumber media, jenis atribusi, metode atribusi, kampanye, ID kampanye, Jenis sentuhan yang diatribusikan, tanggal, sumber, dan kombinasinya.</li><li>Jika Anda memilih pengelompokan dengan dimensi yang hanya berlaku untuk lalu lintas non-organik, tabel akan menampilkan T/A untuk sumber media organik.</li></ul> |
| **Atribusi SSOT** | **Perincian judul penginstalan SSOT, atribusi ulang, dan interaksi ulang selama tanggal yang dipilih.**<ul><li>**Non-organik: Kampanye yang mendatangkan pengguna. Mekanisme SSOT memastikan bahwa penginstalan yang sama hanya dihitung sekali.**</li><li>**Metrik organik.**</li></ul> |
| Total | Jumlah penginstalan, atribusi ulang, dan interaksi ulang. |
| Install | Jumlah pengguna unik yang menginstal aplikasi. Dihitung sebagai penginstalan yang diatribusikan oleh AppsFlyer dalam konteks kampanye UA ditambah jumlah penginstalan baru dan unduhan ulang yang dilaporkan oleh SKAN setelah menghapus duplikat. |
| Re-attribution (Atribusi ulang) | Metrik penargetan ulang tersedia dalam jenis tampilan Terpadu dan Penargetan Ulang. Pertimbangkan bahwa SKAN tidak mendukung penargetan ulang. |
| Interaksi ulang | Metrik penargetan ulang tersedia dalam jenis tampilan Terpadu dan Penargetan Ulang. Pertimbangkan bahwa SKAN tidak mendukung penargetan ulang. |
| **Metrik lainnya** | **Berbagai metrik lain yang berkaitan dengan SSOT dan kinerja periklanan** |
| Duplikat SKAN | Jumlah penginstalan SKAN dengan af\_attribution\_flag=true |
| Klik | Data klik dan tayangan dilaporkan oleh jaringan iklan melalui API. Mekanisme SSOT tidak mempengaruhi metrik titik kontak. |
| Tayangan | Data klik dan tayangan dilaporkan oleh jaringan iklan melalui API. Mekanisme SSOT tidak mempengaruhi metrik titik kontak. |
| Rasio konversi | Klik untuk menginstal |
| Biaya ($) | Data <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview">biaya kampanye</Anchor> dilaporkan oleh jaringan iklan melalui API. Data ditampilkan untuk kampanye dengan setidaknya satu penginstalan. Mekanisme SSOT tidak mempengaruhi total biaya yang dilaporkan. Hal ini hanya mempengaruhi metrik yang dihitung menggunakan jumlah penginstalan. |
| AVG eCPI ($) | Metrik biaya per penginstalan efektif menggunakan metrik penginstalan tampilan SSOT. Ini tidak termasuk penginstalan organik. |
| Klik-tayang | Jumlah atribusi yang terjadi setelah pengguna mengklik iklan (CTA). |
| Tingkat uninstal/penghapusan instalasi | Nilai (%) pengguna yang meng-uninstall aplikasi, sebagai proporsi pengguna yang mengatribusikan. Berarti menginstal, berinteraksi ulang, atau mengatribusi ulang. Rumus: Uninstall / Atribusi *100 (Relevan untuk Akuisisi Pengguna saja) |
| mencopot pemasangan | <span id="simple-tabpanel-2"></span>Jumlah pengguna aplikasi yang menginstal aplikasi yang kemudian meng-uninstall (menghapus) aplikasi (Relevan untuk Akuisisi Pengguna saja) |
| Lihat-Tayang (View-Through) | Jumlah atribusi yang terjadi setelah pengguna melihat iklan (VTA). |
| Pendapatan (D2) | SKAN dan AF melaporkan pendapatan (termasuk pendapatan iklan) untuk periode waktu pengukuran SKAN pertama (D2):<ul><li>Pendapatan SKAN: Pendapatan untuk penginstalan SKAN (dengan af\_attribution\_flag=false/null). Berdasarkan setelan nilai konversi untuk <Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio#revenue-component">pendapatan di Conversion Studio</Anchor>, dan kerangka periode waktu pengukuran.</li><li>**Pendapatan yang dilaporkan AF:** Pendapatan yang dihasilkan oleh pengguna aplikasi setelah penginstalan yang diatribusikan oleh AppsFlyer dan dalam periode waktu pengukuran SKAN.</li><li>Bagi yang menggunakan SKAN 4 di Conversion Studio, ini data untuk 2 hari setelah penginstalan. Bagi mereka yang menggunakan SKAN 3 di Conversion Studio, data berdasarkan pada periode waktu aktivitas SKAN yang ditentukan, baik itu lebih atau kurang dari 2 hari.</li><li>Tidak termasuk data dari penginstalan organik.</li><li>**Contoh**:<ul><li>Jendela aktivitas adalah 24 jam.</li><li>Event pendapatan terjadi pada hari setelah penginstalan (Hari X+1), tetapi dalam jendela aktivitas 24 jam.<ul><li>Untuk pendapatan yang dilaporkan SKAN dan AF, pendapatan dihitung, karena terjadi dalam jendela 24 jam (meskipun pada hari yang berbeda dari penginstalan).</li></ul></li></ul></li></ul>**Catatan**:<ul><li>Jika pendapatan SKAN dikonfigurasi hanya untuk event tertentu, metrik pendapatan SSOT hanya mempertimbangkan event pendapatan yang dilaporkan AF terkait.</li></ul>**Tips** : Untuk meningkatkan akurasi pendapatan SKAN:<ul><li>Ikuti <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">petunjuk pendapatan iklan SKAN</Anchor> .</li><li>Gunakan rekomendasi Pendapatan. [Segera hadir]</li></ul> |
| Pendapatan D7 | <ul><li>Termasuk data yang dimodelkan, di luar periode waktu pengukuran SKAN, hingga 7 hari setelah penginstalan. <Anchor target="_blank" href="/marketers/id/docs/skan-modeled-data#revenue-ltv">Pelajari lebih lanjut</Anchor></li><li>Tidak termasuk data dari penginstalan organik.</li></ul> |
| ARPU D2 | Pendapatan rata-rata per Pengguna.<br /><br />Rumus: Pendapatan/Pengguna Unik<br /><br />Bagi yang menggunakan SKAN 4 di Conversion Studio, ini data untuk 2 hari setelah penginstalan. Bagi mereka yang menggunakan SKAN 3 di Conversion Studio, data berdasarkan pada periode waktu aktivitas SKAN yang ditentukan, baik itu lebih atau kurang dari 2 hari. |
| ARPU D7 | Termasuk data yang dimodelkan, di luar periode waktu pengukuran SKAN, hingga 7 hari setelah penginstalan. <Anchor target="_blank" href="/marketers/id/docs/skan-modeled-data#revenue-ltv">Pelajari lebih lanjut</Anchor> |
| ROAS D2 | Laba Atas Belanja Iklan/Return On Ad Spend (%).<br /><br />Rumus: Pendapatan/Biaya * 100<br /><br />Bagi yang menggunakan SKAN 4 di Conversion Studio, ini data untuk 2 hari setelah penginstalan. Bagi mereka yang menggunakan SKAN 3 di Conversion Studio, data berdasarkan pada periode waktu aktivitas SKAN yang ditentukan, baik itu lebih atau kurang dari 2 hari. |
| ROAS D7 | Termasuk data yang dimodelkan, di luar periode waktu pengukuran SKAN, hingga 7 hari setelah penginstalan. <Anchor target="_blank" href="/marketers/id/docs/skan-modeled-data#revenue-ltv">Pelajari lebih lanjut</Anchor> |
| ROI D2 | Laba atas Investasi/Return On Investment (%).<br /><br />Rumus: (Pendapatan - Biaya)/Biaya * 100<br /><br />Bagi yang menggunakan SKAN 4 di Conversion Studio, ini data untuk 2 hari setelah penginstalan. Bagi mereka yang menggunakan SKAN 3 di Conversion Studio, data berdasarkan pada periode waktu aktivitas SKAN yang ditentukan, baik itu lebih atau kurang dari 2 hari. |
| ROI D7 | Termasuk data yang dimodelkan, di luar periode waktu pengukuran SKAN, hingga 7 hari setelah penginstalan. <Anchor target="_blank" href="/marketers/id/docs/skan-modeled-data#revenue-ltv">Pelajari lebih lanjut</Anchor> |
| Laba kotor D2 | Laba setelah dikurangi biaya kampanye.<br /><br />Rumus: Pendapatan - Biaya<br /><br />Bagi yang menggunakan SKAN 4 di Conversion Studio, ini data untuk 2 hari setelah penginstalan. Bagi mereka yang menggunakan SKAN 3 di Conversion Studio, data berdasarkan pada periode waktu aktivitas SKAN yang ditentukan, baik itu lebih atau kurang dari 2 hari. |
| Laba kotor D7 | Termasuk data yang dimodelkan, di luar periode waktu pengukuran SKAN, hingga 7 hari setelah penginstalan. <Anchor target="_blank" href="/marketers/id/docs/skan-modeled-data#revenue-ltv">Pelajari lebih lanjut</Anchor> |
| **Metrik in-app event** | **Metrik yang berkaitan dengan in-app event (IAE) tertentu** |
| Pengguna unik event (D2) | Pengguna unik yang melakukan event tersebut, diukur dengan kombinasi AppsFlyer dan SKAN, termasuk data nilai nol yang dimodelkan. Bagi yang menggunakan SKAN 4, data ini diakumulasikan selama 2 hari pertama setelah instalasi. Bagi mereka yang menggunakan SKAN 3, datanya merupakan akumulasi hari setelah instalasi berdasarkan Jendela Aktivitas yang ditentukan. |
| eCPA event (D2) | Biaya per tindakan efektif: Biaya/pengguna unik yang melakukan event |
| Konversi event (D2) | Tingkat (%) pengguna unik yang melakukan event, sebagai proporsi pengguna yang mengatribusi (artinya menginstal, berinteraksi ulang, atau melakukan atribusi ulang). Rumus: Pengguna/atribusi unik *100 |
| Pendapatan event (D2) | Pendapatan yang dihasilkan dari event ini, dalam hari yang ditentukan setelah penginstalan |

</Accordion>

## Bagaimana cara kerja SSOT?

<div id="understanding-skanaf-modeled-attribution-duplication" />

<Accordion title="Memahami duplikasi atribusi model SKAN-AF">

Atribusi SKAN dan atribusi model AF bekerja secara berbeda dan memiliki sifat dan batasan yang berbeda. Oleh karena itu, setiap penginstalan dapat diatribusikan ke sumber media non-organik:

* Melalui SKAN atau model AF secara eksklusif (atribusi unik).
* Melalui SKAN dan model AF secara bersamaan (duplikat). Dalam hal ini, [mekanisme SSOT](/docs/single-source-of-truth-ssot-guide-for-ios-attribution#ssot-mechanism-workings) menandakan penginstalan duplikat SKAN dengan flag: af\_attribution\_flag=TRUE. Dan di dasbor SSOT, hanya satu tampilan penginstalan, bukan dua.
* Baik model SKAN maupun AF, artinya penginstalannya organik.

Skenario atribusi model SKAN-AF yang mungkin diilustrasikan dalam diagram Venn berikut.

![skan_af_model_diagram.png](https://files.readme.io/1b305d053044f79d12b9190d0b6c24dcc7e0bd17e17ef29029ad0b1c3c7d84c0-31247514684689.png)

Tabel berikut menjelaskan alasan untuk setiap skenario atribusi.

| Khusus SKAN | Khusus model AF | Baik model SKAN maupun AF | Baik model SKAN maupun AF |
| --- | --- | --- | --- |
| <ul><li>Sumber media adalah SRN, versi perangkat pengguna iOS 14.5+, pengguna tidak memberikan persetujuan ATT ganda.</li><li>Sumber media adalah non-SRN, perangkat pengguna memiliki iOS 14.5+, pemodelan probabilistik tidak tersedia, pengguna tidak memberikan persetujuan ATT ganda.</li></ul> | <ul><li>Versi perangkat pengguna adalah iOS 14.4 dan lebih rendah.</li><li>Sumber media tidak mendukung SKAN.</li><li>Penginstalan dilakukan melalui alur web-to-app (SKAN hanya mendukung app-to-app).</li><li>Instal melalui penargetan ulang (tidak didukung oleh SKAN)</li></ul> | Tidak ada batasan dan baik SKAN maupun model AF mengatribusikan penginstalan.<br /><br />Ini membuat penginstalan duplikat, dan saat itulah SSOT diperlukan untuk menghapus duplikat. | Pengguna organik |

</Accordion>

<div id="ssot-mechanism-workings" />

<Accordion title="Mekanisme kerja SSOT">

SSOT bekerja seperti yang dijelaskan dalam visual berikut.

![SingleSourceOfTruth.png](https://files.readme.io/882527d4828cf3c7156caf183652368de33463a440715c69f7ec39bfd0f655fa-31247514685329.png)

**Bagaimana cara kerja mekanisme SSOT?**

Mekanisme SSOT ada di AppsFlyer SDK di aplikasi Anda di perangkat pengguna dan di platform AppsFlyer sebagai berikut:

**Perangkat pengguna:**

* Seorang pengguna membuka aplikasi untuk pertama kalinya. Platform AppsFlyer berusaha untuk menghubungkan pengguna. Kemampuan untuk mengatribusikan bergantung pada jenis kampanye dan status izin pengguna (ATT).
* Jika atribusi berhasil, SDK menetapkan bit atribusi dalam Nilai Konversi (CV)
* Alur SKAdNetwork reguler tetap, tidak berubah. Artinya, aktivitas pengguna terus diukur dan CV diatur hingga periode waktu pengukuran berakhir.
* Selanjutnya, iOS mengirimkan postback.

**Platform AppsFlyer**

* AppsFlyer menerima postback iOS, mendekode nilai konversi, dan mengekspos nilai bit atribusi melalui af\_attribution\_flag seperti yang dirinci dalam tabel berikut.

**Pertimbangan**

* Secara umum, AppsFlyer tidak menghitung penginstalan ulang. Dalam konteks SSOT, status penginstalan ulang tidak dipertimbangkan. Ini berarti SSOT tidak menghapus penginstalan SKAN duplikat yang berasal dari penginstalan ulang dalam konteks analitik SSOT dan mereka tidak mempengaruhi pengaturan tanda af\_attribution.

#### **Bidang flag atribusi**

| Indikator SSOT dalam Nilai Konversi | Artinya | bidang af\_attribution\_flag |
| --- | --- | --- |
| Aktif | SSOT aktif di Conversion Studio dan AppsFlyer berhasil menghubungkan pengguna. | True |
| Nonaktif | SSOT aktif di Conversion Studio (Studio Konversi) dan AppsFlyer tidak mengatribusikan pengguna. | False |
| -- | SSOT tidak aktif di Conversion Studio (Studio Konversi). | Null |

**Bagaimana pengaruh af\_attribution\_flag (bit atribusi) pada alat pelaporan?**

* Dasbor SKAN: Hanya mencerminkan kinerja yang dilaporkan oleh postback SKAN. Dengan demikian, tanda af\_attribution tidak dipertimbangkan dan duplikat tidak dihapus.
* <Anchor target="_blank" href="/marketers/id/docs/skan-aggregated-performance-report-api">Laporan kinerja teragregasi SKAN dan laporan</Anchor> <Anchor target="_blank" href="/marketers/id/docs/skan-raw-data-reports">data lengkap</Anchor> : af\_attribution\_flag tersedia dalam laporan ini. Gunakan sesuai dengan kebutuhan pelaporan Anda. Jika Anda menggabungkan data SKAN dengan data AppsFlyer, gunakan flag untuk menghapus data duplikat. Ini berlaku untuk laporan data lengkap dan gabungan.
* Tampilan SSOT di dasbor Ikhtisar: Data dari semua metode atribusi, SKAN, IDFA, IDFV, Apple Search Ads, dan sebagainya digabungkan dalam satu tampilan setelah menghapus data SKAN duplikat.

</Accordion>

<div id="metrics-derived-by-combining-data-from-multiple-attribution-methods" />

<Accordion title="Metrik yang diperoleh dengan menggabungkan data dari beberapa metode atribusi">

Saat Anda menggabungkan data SKAN dengan data metode atribusi lainnya, gunakan af\_attribution\_flag untuk menghapus data duplikat dari data. Ini berlaku untuk laporan data lengkap dan gabungan.

Contoh metrik berikut dapat dihitung menggunakan af\_attribution\_flag:

* Install Non-Organik
* Organic installs (Instalasi organik)
* eCPI
* Pendapatan kohort

Formula untuk menghitung metrik contoh:

| Deskripsi metrik | Penamaan | Formula |
| --- | --- | --- |
| Penginstalan AppsFlyer non-organik | A | Penginstalan non-organik dilaporkan oleh AppsFlyer |
| Penginstalan unik SKAN | B | SKAN menginstal di mana af\_attribution\_flag=false |
| Semua penginstalan non-organik | C | A + B |
| Organic installs (Instalasi organik) | D | Total penginstalan - C<br /><br />**Catatan** : Total penginstalan berarti semua penginstalan yang dicatat oleh AppsFlyer SDK, apa pun atribusinya. |
| eCPI kampanye | E | Biaya / C |
| Pendapatan kohort | F | Tambahkan bersama-sama berikut ini:<ul><li>Pendapatan pengguna yang ditentukan oleh A. Sertakan event yang dihasilkan selama periode pasca-penginstalan awal yang setara dengan jendela pengukuran SKAN Anda.</li><li>Pendapatan SKAN dengan af\_attribution\_flag = false</li></ul> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Sifat | Catatan |
| --- | --- |
| Tampilan SSOT | SSOT hanya tersedia jika ada paling sedikit satu postback SKAN untuk setiap hari dalam 5 hari terakhir yang memuat `af_attribution_flag=true`. |
| Total instalasi | Dalam beberapa kasus, bisa terdapat lebih banyak penginstalan yang ditampilkan saat SSOT diaktifkan dibandingkan saat tidak aktif. Salah satu alasannya adalah pemodelan nilai konversi null dapat memengaruhi penghitungan tanggal penginstalan, dan menyebabkan perbedaan saat membandingkan penginstalan pada tanggal yang sama. |
| Pendapatan | Pendapatan dan metrik terkait pendapatan lainnya (ARPU, ROAS, ROI, laba kotor) tersedia mulai 1 September 2022. |
| Agensi | Pengguna agensi dapat melihat tampilan SSOT di dasbor Ikhtisar. |
| Jaringan iklan | <ul><li>Jaringan iklan dapat mengakses tampilan SSOT di dashboard Ikhtisar untuk melihat data yang diatribusikan ke sumber medianya. Untuk melihat tampilan SSOT:<ul><li>Pemasang iklan harus mengaktifkan SSOT di Conversion Studio.</li><li>Jaringan iklan harus menjalankan kampanye SKAN.</li><li>Jaringan iklan harus memiliki <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#permissions-tab">izin yang diperlukan</Anchor> dari pemasang iklan untuk mengakses data agregat.</li></ul></li><li>Jaringan iklan dapat menerima sinyal SSOT melalui postback SKAN.</li></ul> |
| Metrik D7 | Metrik D7 mungkin tidak ada atau kurang dari metrik D2, jika:<ul><li>Rentang tanggal berisi tanggal yang belum lewat 8 hari.</li><li>Data sesuai model tidak tersedia. Misalnya, jika tidak ada data pendapatan selama 14 hari. <Anchor target="_blank" href="/marketers/id/docs/skan-modeled-data#revenue-ltv">Pelajari lebih lanjut</Anchor></li><li>Konfigurasi SKAN Conversion Studio telah diubah dalam 14 hari terakhir.</li><li>Ada kurang dari 10 penginstalan pada tanggal tertentu.</li></ul> |
| Perubahan konfigurasi SKAN Conversion Studio | Saat Anda mengubah konfigurasi SKAN Conversion Studio, mungkin ada ketidakakuratan pada data SSOT selama kurang lebih 84 jam. Hal ini karena AppsFlyer segera mulai melakukan dekode postback SKAN dengan skema baru, namun postback masih datang dari instalasi yang dikodekan dengan skema sebelumnya. |
| Data yang dilaporkan AF | <ul><li>Data yang dilaporkan AF, terkadang disebut sebagai data model AF, mengacu pada data dari instalasi atau peristiwa lain yang diatribusikan melalui metode atribusi AppsFlyer lain, bukan SKAN.</li><li>Tujuan dashboard SSOT adalah untuk mencegah duplikasi instalasi dan event yang diatribusikan melalui SKAN dan metode AppsFlyer lainnya.</li><li>Jika Anda mengaktifkan SSOT, namun ingin melihat data sebelum SSOT diaktifkan, dashboard SSOT hanya menampilkan data yang dilaporkan AF.</li></ul> |
| In-App Event | In-app event (sebagai dimensi) dan metriknya hanya tersedia untuk:<ul><li>Event yang dikonfigurasi di SKAN Conversion Studio tersedia.</li><li>Event yang terjadi selama periode Jendela 1 tersedia.</li></ul> |

</Accordion>

> 📄 **Lihat juga**
>
> * Dashboard Ikhtisar

<div data-zendesk-anchors="how-to-get-true-ios-14-performance-data=cara-mendapatkan-data-kinerja-ios-14-yang-sebenarnya 01H8TZV6P41Z3ZEZ8VS86DK1J9=cara-mendapatkan-data-kinerja-ios-14-yang-sebenarnya 01H8TZV6P4G5AF2MJDQB8J6W2M=turn-on-single-source-of-truth overview-dashboard-single-source-of-truth-view=dasbor-ikhtisar-single-source-of-truth 01H8TZV6P4ZBJTDH0FQ6F5D6Q9=dasbor-ikhtisar-single-source-of-truth 01H8TZV6P47ZE6PMPF7S9GCJ16=turn-on-single-source-of-truth-view 01H8TZV6P4VCC5NRKBRQNJ4NX3=ssot-view-considerations filter-considerations=pertimbangan-filter 01H8TZV6P4QXEXYWSXKDB7B5SV=pertimbangan-filter 01H8TZV6P4YNTFBX5RXVKK8J0F=metrics how-does-ssot-work=bagaimana-cara-kerja-ssot 01H8TZV6P4K8VXNKDR7JHM8PFW=bagaimana-cara-kerja-ssot 01H8TZV6P4QYQJ177E2ZG676MH=understanding-skanaf-modeled-attribution-duplication 01H8TZV6P58E502Y1FDFHC3KHM=ssot-mechanism-workings attribution-flag-field=bidang-flag-atribusi 01H8TZV6P5SSKDTKV4BV3TTA7D=bidang-flag-atribusi 01H8TZV6P5AHZD8VRWRS4SPBYW=metrics-derived-by-combining-data-from-multiple-attribution-methods 01H8TZV6P5KN4F24ZN33V0TK7K=traits-and-limitations h_01HE182N43SSBX051E4GK7NFQ8=lihat-juga" />
