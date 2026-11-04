---
title: Laporan data lengkap Protect360
metadata:
  keywords:
    - Advertisers
    - Protect360
    - protect
    - protect 360
    - '360'
    - Raw Data
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-11-09T13:03:45Z'
  edited_at: '2023-11-03T12:15:57Z'
  id: 360015179337
  locale: id
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/id/articles/360015179337
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Sekilas:** Laporan data lengkap menjelaskan penginstalan dan in-app event yang diblokir oleh mesin Protect360, serta dari Aturan Validasi yang ditambahkan secara manual.

<div id="note" />

<div id="about-protect360-raw-data-reports" />

## Tentang laporan data lengkap Protect360

Laporan data lengkap:

* Menampilkan data tentang:
  * Klik, penginstalan, dan in-app event yang teridentifikasi sebagai penipuan oleh mesin Protect360.
  * Penginstalan dan in-app event yang teridentifikasi melalui Validation Rules (Aturan Validasi).
* Sertakan alasan pemblokiran untuk setiap klik, penginstalan, atau in-app event.
* Digunakan oleh pemasang iklan untuk merekonsiliasi akun jaringan iklan untuk pengoptimalan, dan untuk menyesuaikan dashboard untuk penipuan pasca-atribusi.
* Mungkin ada <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions">beberapa bidang yang dibatasi atau tidak tersedia</Anchor> jika <Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework">AppsFlyer Aggregated Advanced Privacy (AAP)</Anchor>.
* Jenis laporan dan ketersediaannya melalui unduhan, API, dan Data Locker (S3 bucket) dideskripsikan pada bagian berikut.
* Retensi laporan data lengkap historis hingga 90 hari, bergantung pada alat pelaporan dan asal data lengkap.

<div id="report-types" />

<Accordion title="Jenis laporan">

<div id="blocked-install-postbacks" />

<div id="clicks" />

<div id="postattribution-inapp-events" />

<div id="blocked-inapp-events" />

<div id="postattribution-installs" />

<div id="installs" />

<div id="protect360-raw-data-report-types" />

#### Jenis laporan data lengkap Protect 360

| Laporan | Deskripsi |
| --- | --- |
| Install | Laporan termasuk:<ul><li>**Penginstalan palsu**: Penginstalan yang teridentifikasi sebagai kecurangan oleh mesin Protect360. Penginstalan ini tidak muncul di dashboard AppsFlyer atau data lengkap, kecuali untuk dasbor Protect360 dan data lengkap.</li><li>**Pemasangan yang dibajak**: Penginstalan pengguna sebenarnya di mana atribusi dicuri, tetapi Protect360 [mengoreksi atribusi tersebut](/docs/protect360-raw-data-reports#koreksi-atribusi-penginstalan-yang-dibajak).</li><li>**Aturan Validasi** : Ini memblokir penginstalan atau memblokir atribusi (Protect360 [mengoreksi atribusi](/docs/protect360-raw-data-reports#koreksi-atribusi-penginstalan-yang-dibajak)).</li></ul> |
| Instalasi pasca atribusi | Laporan termasuk penginstalan yang diatribusikan ke sumber media, tetapi kemudian terdeteksi sebagai kecurangan.Protect360 [mengoreksi atribusi](/docs/protect360-raw-data-reports#koreksi-atribusi-penginstalan-yang-dibajak) . |
| In-app event yang diblokir | Laporan termasuk in-app event dari:<ul><li>**Penginstalan palsu**: IAEs diblokir.</li><li>**In-app event**: Teridentifikasi sebagai penipuan terlepas dari penginstalan aslinya.</li><li>**Validation Rules (Aturan Validasi)**:<ul><li>IAEs dari aturan yang memblokir penginstalan atau memblokir atribusi.</li><li>IAEs dari aturan yang memblokir in-app event.</li></ul></li></ul> |
| In-app event pasca atribusi | Laporan termasuk in-app event:<ul><li>Teridentifikasi pasca-atribusi</li><li>Penginstalan diatribusikan ke media source, tetapi kemudian terdeteksi sebagai penipuan.</li></ul> |
| Klik | Laporan termasuk klik yang diblokir dengan alasan pemblokirannya. |
| Postback instalasi yang diblokir | Laporan termasuk salinan dari postback penolakan yang dikirim ke sumber media yang membawa penginstalan yang diblokir. |

</Accordion>

<div id="postattribution-reports" />

<Accordion title="Laporan pasca atribusi">

* Laporan kecurangan data lengkap pasca-atribusi memiliki struktur yang sama dengan laporan penipuan yang diblokir.
* Laporan pasca-atribusi bulan ini (menurut tanggal instalasi) terus diperbarui hingga hari ketujuh bulan berikutnya (tanggal deteksi).
* Laporan data lengkap pasca-atribusi terbatas untuk pengiklan. Agensi memerlukan <Anchor target="_blank" href="/partners/id/docs/protect360-for-integrated-partners">izin</Anchor> aktif untuk mengaksesnya.
* Laporan berisi event penipuan setelah atribusi yang diidentifikasi oleh Protect360 dan termasuk semua sumber media dalam satu laporan. **Catatan**: Jika tidak ada event penipuan setelah atribusi yang teridentifikasi untuk rentang tanggal yang dipilih, laporan akan dikembalikan dalam keadaan kosong,
* Laporan data lengkap kecurangan pasca-atribusi tersedia sebagai berikut:

  * Dashboard antarmuka pengguna: terbatas pada satu sumber media selama satu bulan kalender.
  * Pull API: memuat semua sumber media.  (Pembatasan: Hanya tersedia bagi pemilik aplikasi)

<div id="using-post-attribution-reports" />

#### **Menggunakan laporan pasca-atribusi**

* Pilih semua kombinasi penginstalan/IAE dan deteksi rentang tanggal sesuai kebutuhan.
* Mempertimbangkan bahwa Protect360 melakukan deteksi pasca-atribusi selama bulan kalender instalasi dan hingga hari ketujuh bulan berikutnya. Ini berarti, contohnya, bahwa untuk instalasi di bulan November, Protect360 memeriksa indikasi kecurangan hingga tanggal 7 Desember.
* Praktik terbaik untuk menggunakan Pull API adalah sebagai berikut:
  * Asumsikan bahwa Anda menarik laporan setiap harinya.
  * Atur rentang tanggal instalasi menjadi 60 hari sebelum hari ini.
  * Atur rentang tanggal deteksi dari/deteksi hingga ke hari sebelum hari ini.  
    Ini berarti bahwa Anda akan mendapatkan daftar kecurangan pasca-atribusi yang terdeteksi kemarin. Jika Anda tidak menarik laporan selama beberapa hari, sesuaikan rentang tanggal deteksi dan tarik laporan.

<div id="example" />

> 📄 **Contoh**
>
> **Contoh A**: Selama Desember (tanggal instalasi) 15 instalasi diatribusikan ke example\_media. Pada tanggal 3 Januari (tanggal deteksi), Protect360 mengidentifikasi example\_media sebagai penipu. Hasilnya, 15 instalasi yang diatribusikan ke *example\_media* dimasukkan dalam daftar laporan kecurangan pascaatribusi untuk ditindaklanjuti oleh pemilik aplikasi.
>
> **Contoh B**: Selama Desember, 15 instalasi diatribusikan ke example\_media. Pada tanggal 9 Januari, Protect360 mengidentifikasi example\_media sebagai penipu. Dalam hal ini, tidak ada tindakan yang diambil Protect360 karena penipu diidentifikasi setelah penutupan bulan pada tanggal 7 Januari.

</Accordion>

<div id="raw-data-availability-by-tool-type" />

<Accordion title="Ketersediaan data lengkap berdasarkan jenis alat">

<div id="protect360-raw-data-availability-by-tool-type" />

#### Ketersediaan data lengkap Protect 360 berdasarkan jenis alat

<table><thead><tr><th>Laporan</th><th>Kesegaran data</th><th>Pull API</th><th>Halaman Export Data</th><th>Data Locker</th></tr></thead><tbody><tr><td>Install</td><td>Waktu sebenarnya</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>In-app event yang diblokir </td><td>Waktu sebenarnya</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Klik</td><td>Waktu sebenarnya</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Postback instalasi yang diblokir</td><td>Waktu sebenarnya</td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Instalasi pasca atribusi</td><td><p>Setiap Hari 10:00 UTC</p></td><td><p><span>✓</span></p></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>In-app event pasca atribusi</td><td><p>Setiap Hari 10:00 UTC</p></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr></tbody><tfoot><tr><td colspan="5"><p>\* Batasan untuk melaporkan melalui Data Locker:</p><ul><li>Transparansi agensi tidak didukung. Artinya, lalu lintas yang didorong agensi tidak berisi nama sumber media yang mengirimkan penginstalan. </li><li>Laporan tersebut memiliki sekumpulan bidang unik yang terkait dengan laporan Data Locker lainnya. Daftar ini tidak dapat diubah. </li><li>Data penargetan ulang tidak tersedia di laporan Penginstalan; hanya di laporan penginstalan pasca-atribusi. </li></ul></td></tr></tfoot></table>

</Accordion>

<div id="getting-raw-data-reports" />

## Mendapatkan laporan data lengkap

Laporan data lengkap tersedia dengan mengunduh, Pull API, dan Data Locker (S3 bucket). Anda juga dapat <Anchor target="_blank" href="/partners/id/docs/protect360-for-integrated-partners">memberi mitra akses ke laporan</Anchor> .

<div id="download" />

<Accordion title="Unduh">

**Untuk mengunduh:**

1. Di dashboard Protect360, buka **Laporan data lengkap** >  **Diblokir** atau **Pasca atribusi.**
   * Untuk laporan pasca-atribusi, pilih sumber media dan bulan.
2. Pilih laporan **Protect360 & Aturan Validasi** untuk diunduh.

**ATAU**

1. Di dashboard AppsFlyer, buka **Export Data (Ekspor Data)** .
2. Pilih laporan **Protect360 & Aturan Validasi** untuk diunduh.

**Catatan** : Laporan yang diunduh dari laman Ekspor Data berisi semua sumber media.

</Accordion>

<div id="pull-api" />

<Accordion title="Pull API">

**Untuk mengunduh laporan data lengkap yang tersedia oleh Pull API:**

**Sebelum Anda mulai:**

Anda memerlukan token Pull API. Dapatkan token dari <Anchor target="_blank" href="/marketers/id/docs/managing-appsflyer-tokens">pengguna admin</Anchor>.

1. Buka **Integration > API Access**.  
   Laman <Anchor target="_blank" href="/marketers/id/docs/pull-api-raw-data">Pull API</Anchor> dibuka.
2. Di bagian laporan penipuan Protect360, pilih panggilan Pull API yang diperlukan.
3. Isi parameter sesuai kebutuhan. Tabel berikut mencantumkan parameter.
4. Tarik laporan.

<div id="pull-api-raw-data-report-parameters" />

#### Parameter laporan data lengkap Pull API

| Parameter | Deskripsi | Format | Wajib |
| --- | --- | --- | --- |
| id\_aplikasi | ID Aplikasi seperti yang muncul di AppsFlyer | String | Ya |
| api\_token | Ambil kode dari Dashboard. Buka **Integrasi** > **Akses API.** Hanya pengguna admin yang dapat mengambil token API. | String | Ya |
| from | Awal rentang tanggal:<ul><li>Untuk instalasi, ini adalah tanggal instalasi.</li><li>Untuk in-app event, ini adalah tanggal event.</li></ul> | DD-MM-YYYY | Ya |
| ke | Akhir rentang tanggal:<ul><li>Untuk instalasi, ini adalah tanggal instalasi.</li><li>Untuk in-app event, ini adalah tanggal event.</li></ul> | DD-MM-YYYY | Ya |
| event\_name | [Opsional untuk penipuan in-app event Pasca atribusi]<br /><br />Filter event berdasarkan in-app event. Batasi laporan untuk event tertentu.  Salah satu event atau lebih dapat disertakan.<br /><br />Contoh penggunaan: `&event_name=af_purchase,af_login` | String | Tidak |
| additional\_fields=rejected\_reason\_value | [Opsional untuk penipuan in-app event Pasca atribusi]<br /><br />**<Anchor target="_blank" href="/marketers/id/docs/raw-data-field-dictionary#protect360">blocked\_reason\_rule</Anchor>** menampilkan kontributor valid (sumber media) untuk penginstalan/in-app event yang dibajak. Diisi dengan <Anchor target="_blank" href="/marketers/id/docs/raw-data-field-dictionary#attribution::2a6fd501">**kontributor[1-3]**</Anchor> atau **organik**. | String | Tidak |
| mendeteksi dari | [Opsional untuk instalasi Pasca atribusi]<br /><br />Awal rentang tanggal deteksi penipuan. (Defaultnya adalah dari.) (Digunakan dalam penipuan instalasi Pasca atribusi.) (Digunakan dalam penipuan instalasi Pasca atribusi.) | DD-MM-YYYY | Tidak |
| mendeteksi hingga | [Opsional untuk instalasi Pasca atribusi]<br /><br />Akhir rentang tanggal deteksi penipuan. (Defaultnya adalah hingga.) | DD-MM-YYYY | Tidak |

</Accordion>

<div id="data-locker" />

<Accordion title="Data Locker">

Data Locker menulis  data lengkap ke bucket AWS S3.

<Anchor target="_blank" href="/marketers/id/docs/data-locker-advertiser-reports#protect360">Lihat daftar laporan Protect360 yang tersedia</Anchor>. 

<Anchor target="_blank" href="/marketers/id/docs/data-locker-for-marketers#aws-cli">Lihat petunjuk konfigurasi Data Locker</Anchor>.

</Accordion>

<div id="protect360-report-structure" />

## Struktur laporan Protect360

Laporan Protect360 memiliki struktur umum yang sama seperti bidang laporan akuisisi pengguna.

Selain <Anchor target="_blank" href="/marketers/id/docs/raw-data-field-dictionary">bidang laporan data lengkap</Anchor>, Laporan Protect360 juga memiliki bidang penargetan ulang dan alasan pemblokiran sebagai berikut:

<div id="blocked-reasons" />

### Alasan Pemblokiran

<div id="click-level-blocked-reasons" />

<Accordion title="Alasan pemblokiran level klik">

Pada level klik, klik diblokir, dan proses atribusi mengabaikannya.

| Alasan Pemblokiran | Deskripsi |
| --- | --- |
| ip\_blacklist | Berdasarkan daftar yang dibuat secara dinamis (<Anchor target="_blank" href="/marketers/id/docs/protect360-anti-fraud-guide#ip-denylists">detail</Anchor>) |
| invalid\_fingerprint | Khusus klik S2S: parameter tidak valid yang dikirim oleh sumber (untuk pencocokan probabilistik) |
| click\_capping | Tingkat kecurangan yang sangat tinggi terdeteksi dari jaringan iklan tersebut. <Anchor target="_blank" href="/partners/id/docs/protect360-for-integrated-partners#impression-capping">Pelajari lebih lanjut</Anchor> |
| click\_signing | Autentikasi pada klik tidak divalidasi. <Anchor target="_blank" href="/partners/id/docs/click-signing-for-ad-networks">Pelajari lebih lanjut</Anchor> |
| input\_validation | Nama sumber media tidak valid |

</Accordion>

<div id="install-level-blocked-reasons" />

<Accordion title="Alasan pemblokiran level instalasi">

Pada level instalasi, kami mengidentifikasi informasi yang cukup pada saat instalasi untuk menentukan apakah:

* Instalasi palsu, artinya pengguna yang menginstal aplikasi bukan orang yang nyata. Dalam hal ini, atribusi diblokir sepenuhnya.
* Pembajakan atribusi, di mana pengguna itu nyata tetapi interaksinya dipalsukan. Dalam hal ini, interaksi palsu diblokir dan atribusi ditetapkan ulang ke jaringan iklan kontributor pertama yang valid.

Tabel berikut mencantumkan kemungkinan alasan pemblokiran pada level instalasi:

<div id="install-level-fake-install-block-sub-reasons" />

#### Level instalasi: Alasan pemblokiran instalasi palsu

| Alasan Pemblokiran | Sub Alasan Pemblokiran | Deskripsi |
| --- | --- | --- |
| Bot | fake\_device\_parameters | Perilaku non-manusia terdeteksi pada parameter terkait perangkat selama proses penginstalan aplikasi |
| Bot | fake\_install\_parameters | Perilaku non-manusia terdeteksi pada parameter terkait penginstalan selama proses penginstalan aplikasi |
| Bot | bayesian\_network | Identifikasi jaringan bayesian dari pola kecurangan |
| install\_store\_validation | - | Validasi tanda terima penginstalan Apple App Store  gagal |
| validasi\_bot | invalid\_device\_parameters | Ketidaksesuaian ekspektasi bidang perangkat tertentu, ditentukan oleh pelanggan |
| validasi\_bot | aturan\_validasi | Aturan yang hasilnya berupa penginstalan yang diblokir berdasarkan aturan validasi yang ditetapkan secara manual |

<div id="install-level-attribution-hijacking-block-sub-reasons" />

#### Level instalasi: Alasan pemblokiran pembajakan atribusi

| Alasan Pemblokiran | Sub Alasan Pemblokiran | Deskripsi |
| --- | --- | --- |
| ctit\_anomalies | short\_ctit | Instalasi diblokir karena CTIT yang pendek: ditentukan Protect360 |
| install\_hijacking | referrer\_hijack | Upaya pembajakan yang diblokir berdasarkan GooglePlay API dan parameter AppsFlyer SDK |
| install\_hijacking | integration\_temporarily\_blocked | Penginstalan diblokir karena mitra (pid) memiliki tingkat penipuan yang sangat tinggi dan anomali yang signifikan di semua lalu lintas mereka |
| validasi\_peretasan | short\_ctit | Instalasi diblokir karena CTIT yang pendek: ditentukan Pelanggan |
| validasi\_peretasan | empty\_site\_id | Instalasi diblokir karena ID situs yang tidak diisi. Penerapan aturan dilakukan secara bertahap |
| validasi\_peretasan | aturan\_validasi | Aturan yang hasilnya berupa atribusi yang diblokir berdasarkan aturan validasi yang ditetapkan secara manual |

</Accordion>

<div id="cluster-level-blocked-reasons" />

<Accordion title="Alasan pemblokiran level kluster">

Ketika pola penipuan terdeteksi, sumber penipuan dimasukkan ke dalam daftar hitam. Instalasi dari sumber daftar hitam ini diblokir karena:

* Instalasi palsu, artinya pengguna yang menginstal aplikasi bukan orang yang nyata. Dalam hal ini, atribusi diblokir sepenuhnya.
* Pembajakan atribusi, di mana pengguna itu nyata tetapi interaksinya dipalsukan. Dalam hal ini, interaksi palsu diblokir dan atribusi ditetapkan ulang ke jaringan iklan kontributor pertama yang valid.

Tabel berikut mencantumkan kemungkinan alasan pemblokiran pada level kluster:

<div id="cluster-level-fake-install-block-reasons" />

#### Level kluster: Alasan pemblokiran instalasi palsu

| Alasan Pemblokiran | Sub Alasan Pemblokiran | Deskripsi |
| --- | --- | --- |
| Bot | timestamp\_anomalies | Anomali yang terkait ke waktu klik alur atribusi danstempel waktu lainnya yang dikumpulkan dari perangkat |
| bot, site\_blacklist | device\_emulators | Instalasi dihasilkan pada skala besar dengan skrip otomatis yang bekerja pada lingkungan virtual. |
| site\_blacklist | device\_farms | Tingkat perangkat tidak dikenal (baru) yang tinggi |
| behavioral\_anomalies | behavioral\_anomalies | Perilaku in-app yang mencurigakan dibandingkan dengan pola perilaku pengguna aplikasi umum |

<div id="cluster-level-attribution-hijacking-block-reasons" />

#### Level kluster: Alasan pemblokiran pembajakan atribusi

| Alasan Pemblokiran | Sub Alasan Pemblokiran | Deskripsi |
| --- | --- | --- |
| ctit\_anomalies, install\_hijacking | ctit\_anomalies | Pola CTIT abnormal per standar aplikasi |
| click\_flood | click\_flood | Volume klik tinggi secara abnormal di sepanjang distribusi CTIT yang panjang |
| install\_hijacking | click\_clusters | Klik dihasilkan oleh malware tingkat perangkat |

</Accordion>

<div id="inapp-level-blocked-reasons" />

<Accordion title="Alasan pemblokiran tingkat in-app">

In-app event dapat diblokir karena alasan berikut:

* Instalasi awal diidentifikasi sebagai instalasi palsu.
* Karena aturan validasi yang ditentukan.
* Karena algoritma kami mendeteksi kecurangan.

Tabel berikut mencantumkan kemungkinan alasan pemblokiran tingkat in-app.

<div id="in-app-level-block-reasons" />

#### Alasan pemblokiran in-app

| Alasan Pemblokiran | Sub Alasan Pemblokiran | Deskripsi |
| --- | --- | --- |
| Bawaan dari instalasi | Bawaan dari instalasi | Instalasi awal diidentifikasi sebagai [instalasi](/docs/protect360-raw-data-reports#install-level-blocked-reasons) palsu berdasarkan alasan tingkatinstalasi atau [daftar hitam](/docs/protect360-raw-data-reports#cluster-level-blocked-reasons) |
| inapps\_bots | fake\_device\_parameters | Algoritma AppsFlyer mendeteksi kecurangan |
| in\_app\_store\_validation | - | <Anchor target="_blank" href="/marketers/id/docs/legacy-receipt-validation-for-in-app-purchases">Receipt validation (validasi tanda terima)</Anchor> untuk in-app purchase gagal. |
| validation\_inapps | aturan\_validasi | Berdasarkan aturan validasi yang ditetapkan secara manual |

</Accordion>

### Retargeting

Data lengkap Protect360 mencakup penginstalan dan sesi penipuan dari kampanye penargetan ulang (masing-masing disebut sebagai atribusi ulang dan interaksi ulang). Data ditampilkan menggunakan bidang <Anchor target="_blank" href="/marketers/id/docs/raw-data-field-dictionary#event">nama event</Anchor> dan <Anchor target="_blank" href="/marketers/id/docs/raw-data-field-dictionary#attribution::e9c68f6c">jenis konversi penargetan ulang</Anchor>. Ini ditandai sebagai:

* Penginstalan (berlaku untuk nama event, tetapi bukan jenis konversi penargetan ulang)
* Re-attribution
* Re-engagement
* Penginstalan ulang

Data lengkap penargetan ulang Protect360 tersedia untuk pemblokiran waktu aktual dan kecurangan yang teridentifikasi pasca-atribusi sebagai berikut:

<table><thead><tr><th>Laporan </th><th>Ekspor data</th><th>Pull API</th><th>Data Locker</th></tr></thead><tbody><tr><td>Install</td><td><span>✓\*</span></td><td><span>✓\*</span></td><td>-</td></tr><tr><td>Instalasi pasca atribusi</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="4"> <span>\* Data interaksi ulang tidak tersedia</span><span></span><br/> </td></tr></tbody></table>

<div id="traits-and-limitations" />

<div id="hijacked-installs-attribution-correction" />

### Koreksi atribusi penginstalan yang dibajak

Untuk penginstalan yang dibajak, AppsFlyer memblokir atribusi ke jaringan penipuan dan sebagai gantinya mengatribusikan sumber kontributor terakhir yang sah. 

Untuk penginstalan yang dibajak gunakan bidang  <Anchor target="_blank" href="/marketers/id/docs/raw-data-field-dictionary#protect360"> rejected\_reason\_value</Anchor>   untuk mengidentifikasi  kontributor yang valid (sumber media), artinya kontributor yang seharusnya menerima atribusi.

* **Rejected\_reason\_value**  yang diisi dengan <Anchor target="_blank" href="/marketers/id/docs/raw-data-field-dictionary#attribution::2a6fd501">**kontributor [1-3]**</Anchor> atau **organik**Periksa **kontributornya[1-3]** **bidang sumber media/mitra**untuk melihat detail kontributor dan merekonsiliasi.
* Jika bidang kontributor tidak ditampilkan di laporan Anda, bidang ini tersedia untuk ditambahkan dari laman **Export data (Ekspor data)**.

Saat penginstalan yang dibajak diblokir secara waktu aktual, atribusi yang benar ditampilkan di dashboard dan laporan AppsFlyer (bukan hanya Protect360). Saat penginstalan yang dibajak diidentifikasi setelah atribusi, atribusi yang benar hanya ditampilkan di data lengkap Protect360.

<div data-zendesk-anchors="about-protect360-raw-data-reports=tentang-laporan-data-lengkap-protect360 h_01HE7S55TCE60A34T6RCNTCQK8=tentang-laporan-data-lengkap-protect360 h_01HE7S55TC4G31R9EANMKCZ7V5=report-types protect360-rawdata-report-types=jenis-laporan-data-lengkap-protect-360 h_01HE7S55TCKQYTXPV6J54SHM0D=jenis-laporan-data-lengkap-protect-360 h_01HE7S55TC4F5S243BSGN74RDK=postattribution-reports using-postattribution-reports=menggunakan-laporan-pasca-atribusi h_01HE7S55TC7KCF75KFXHCE3K2K=menggunakan-laporan-pasca-atribusi h_01HE7S55TCR8BKZ0PQ5B14X3X4=contoh h_01HE7S55TC95YC1BJJ0ZERCQ14=raw-data-availability-by-tool-type protect360-rawdata-availability-by-tool-type=ketersediaan-data-lengkap-protect-360-berdasarkan-jenis-alat h_01HE7S55TCH4CES29C5J3QXQK4=ketersediaan-data-lengkap-protect-360-berdasarkan-jenis-alat getting-raw-data-reports=mendapatkan-laporan-data-lengkap h_01HE7S55TC3MRT6E9QV0J0X6FC=mendapatkan-laporan-data-lengkap h_01HE7S55TCBVFQ1DH06G53BNEN=download h_01HE7S55TCMT81J4SWBFQFYV2C=pull-api pull-api-raw-data-report-parameters=parameter-laporan-data-lengkap-pull-api h_01HE7S55TCRRD95D0QPCXBRF8T=parameter-laporan-data-lengkap-pull-api h_01HE7S55TCMAY86J1HKYB0APZ6=data-locker protect360-report-structure=struktur-laporan-protect360 h_01HE7S55TCS91ZC9V3K0VDSVXK=struktur-laporan-protect360 blocked-reasons=alasan-pemblokiran h_01HE7S55TC1ZEDD5ABD21FCPY2=alasan-pemblokiran h_01HE7S55TDMDSVQCVSV5YS3CZN=click-level-blocked-reasons h_01HE7S55TD754T07FWHFK5P71K=install-level-blocked-reasons install-level-fake-install-block-reasons=level-instalasi-alasan-pemblokiran-instalasi-palsu h_01HE7S55TDHTE5P47N1CCREGZX=level-instalasi-alasan-pemblokiran-instalasi-palsu install-level-attribution-hijacking-block-reasons=level-instalasi-alasan-pemblokiran-pembajakan-atribusi h_01HE7S55TDFA6WGAHE80ECV8CA=level-instalasi-alasan-pemblokiran-pembajakan-atribusi h_01HE7S55TDCHG0CVJA3JRSAW3G=cluster-level-blocked-reasons cluster-level-fake-install-block-reasons=level-kluster-alasan-pemblokiran-instalasi-palsu h_01HE7S55TDBES0BY0FF3WKSSVG=level-kluster-alasan-pemblokiran-instalasi-palsu cluster-level-attribution-hijacking-block-reasons=level-kluster-alasan-pemblokiran-pembajakan-atribusi h_01HE7S55TD3M45TH4PY2W805W7=level-kluster-alasan-pemblokiran-pembajakan-atribusi h_01HE7S55TDGB05PEZX8KS3J3QJ=inapp-level-blocked-reasons inapp-level-block-reasons=alasan-pemblokiran-in-app h_01HE7S55TD661EHCV50S9BW5MS=alasan-pemblokiran-in-app h_01HE7S55TDSYDC8BWZ8D8DF9JE=retargeting hijacked-installs-attribution-correction=koreksi-atribusi-penginstalan-yang-dibajak h_01HE7S55TD8SDCQJCCYQC0MNES=koreksi-atribusi-penginstalan-yang-dibajak" />
