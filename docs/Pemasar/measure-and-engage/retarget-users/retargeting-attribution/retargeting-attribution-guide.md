---
title: Pedoman Atribusi Penargetan Ulang
metadata:
  keywords:
    - Attribution
    - Re-targeting
    - retargeting
    - Advertisers
    - reatribution
    - re-atribution
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-09-30T13:18:26Z'
  edited_at: '2023-11-08T15:16:04Z'
  id: 207033786
  locale: id
  section: Retargeting attribution
  section_id: 6551326229265
  url: https://support.appsflyer.com/hc/id/articles/207033786
---
> **Sekilas:** Kampanye penargetan ulang (pemasaran ulang) memotivasi pengguna untuk membuka dan berinteraksi ulang dengan aplikasi atau mendorong pengguna yang telah menghapus aplikasi untuk menginstalnya kembali.

<div id="retargeting-fundamentals" />

## Dasar-dasar penargetan ulang

Atribusi penargetan ulang terjadi ketika pengguna berinteraksi dengan kampanye penargetan ulang dengan mengklik [tautan atribusi penargetan ulang](/docs/retargeting-attribution-guide#retargeting-attribution-links) atau <Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template">deep link (tautan langsung)</Anchor>. Atribusi penargetan ulang ini menghasilkan salah satu event atribusi berikut:

* **Interaksi ulang:** Jika aplikasi ada di perangkat, sumber media yang memotivasi pengguna untuk membuka aplikasi dikreditkan dengan interaksi ulang.
* **Atribusi ulang (alias retargeting reinstall (penginstalan ulang penargetan ulang)**: Jika aplikasi tidak ada di perangkat pengguna (artinya pengguna meng-uninstal aplikasi), maka interaksi dengan kampanye penargetan ulang mendorong pengguna untuk menginstal ulang dan membuka aplikasi. Jika ini terjadi selama <Anchor target="_blank" href="/marketers/id/docs/set-up-re-attribution-window">re-attribution window (jendela atribusi ulang)</Anchor>, sumber media penargetan ulang dikreditkan dengan atribusi ulang.  Bacaan terkait: <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#reinstalls">Penginstalan ulang.</Anchor>

![](https://files.readme.io/64b8d9f5040daa281ae13f0855749ab4a88a2e7e8616d6ada37975899db92c80-31937591646097.png)

Sebelum menjalankan kampanye penargetan ulang, tinjau aturan interaksi dan contoh kasus di bagian berikut, lalu atur penargetan ulang seperti yang dijelaskan di bagian prosedur penargetan ulang. Untuk lebih mudahnya, Anda harus terbiasa dengan <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model">model atribusi</Anchor> AppsFlyer dan jendela atribusi terkait.

<div id="tip" />

> 👍 **Tips**
>
> Ingin tahu lebih banyak tentang penargetan ulang? Lihat <Anchor target="_blank" href="https://elevate.appsflyer.com/pages/142/remarketing">kursus singkat dan informatif ini di Portal Pembelajaran AppsFlyer</Anchor>.

<div id="reengagement-rules-and-windows" />

<Accordion title="Aturan dan jendela interaksi ulang">

* Aturan atribusi penargetan ulang menentukan apakah suatu event merupakan event penargetan ulang dan diatribusikan ke sumber media penargetan ulang.
* Mirip dengan kampanye atribusi akuisisi pengguna, interaksi ulang penargetan ulang SRN dilaporkan oleh API dan non-SRN melalui tautan atribusi.
* Aturannya, berdasarkan perjalanan pengguna, terdiri dari :
  * [Inclusion windows (jendela inklusi)](/docs/retargeting-attribution-guide#jendela-inklusi), periode waktu di mana interaksi ulang dapat terjadi.
  * [Exclusion windows (jendela eksklusi)](/docs/retargeting-attribution-guide#jendela-eksklusi), periode waktu di mana interaksi ulang tidak dapat terjadi.
* Jika interaksi ulang diatribusikan, in-app event selama durasi jendela interaksi ulang <Anchor target="_blank" href="/marketers/id/docs/resolve-retargeting-double-attribution">diatribusikan dua kali.</Anchor> Artinya, interaksi ulang diatribusikan ke sumber media penargetan ulang dan ke sumber media UA aslinya jika diketahui.

Diagram berikut berisi sekumpulan aturan interaksi ulang. Gunakan aturan tersebut untuk menentukan apakah interaksi dengan kampanye penargetan ulang akan diatribusikan sebagai interaksi ulang.

**Aturan interaksi ulang**

![](https://files.readme.io/e6643112f3e9969242c0dd394f6401406fbc837a9494cc4bb3825cff6365f36d-33563511578513.png) **Referensi—jendela inklusi dan eksklusi**

Tabel berikut berisi informasi referensi terkait jendela yang terkait dengan atribusi penargetan ulang.

<div id="inclusion-windows" />

#### Jendela inklusi

| Jenis jendela | Deskripsi |
| --- | --- |
| View-Through (Lihat-Tayang) | Durasi maksimum dimulai saat pengguna melihat iklan hingga mereka membuka aplikasi.<br /><br />**Lokasi konfigurasi**: Tautan atribusi<br /><br />**Durasi**:<ul><li>Default: 1 hari</li><li>Rentang: 1-23 jam/1-7 hari</li></ul> |
| Klik lookback (lihat-balik) | Durasi maksimum dimulai saat pengguna mengklik iklan hingga mereka membuka aplikasi.<br /><br />**Lokasi konfigurasi**: Tautan atribusi<br /><br />**Durasi** :<ul><li>Default: 7 hari</li><li>Rentang: 1-23 jam/1-30 hari</li></ul>**Catatan SRN:** Periksa dengan SRN, apa saja kebijakan khusus mereka tentang jendela lookback. |
| Re-engagement | Pertimbangkan hal berikut sehubungan dengan jendela re-engagement (interaksi ulang):<ul><li>Jendela dimulai saat pengguna membuka aplikasi untuk pertama kalinya setelah berinteraksi dengan sumber media penargetan ulang.</li><li>In-app event <Anchor target="_blank" href="/marketers/id/docs/resolve-retargeting-double-attribution">diatribusikan dua kali</Anchor> pada pernargetan ulang dan sumber media akuisisi pengguna selama durasi jendela</li><li>Durasi jendela ditentukan oleh pengaturan aplikasi atau oleh SRN.</li><li>Jika pengguna berinteraksi dengan kampanye penargetan ulang lainnya selama jendela interaksi ulang yang tidak diblokir oleh jendela eksklusi, jendela interaksi ulang segera berakhir dan jendela interaksi ulang yang baru dimulai.</li><li>Dalam konteks atribusi ulang: Durasi **jendela atribusi** tidak terbatas dalam waktu (mirip dengan penginstalan). Namun, jendela ini berakhir jika ada penginstalan baru, penginstalan ulang, atau karena batas penyimpanan data.</li></ul>**Di mana disetel:** Tautan atribusi<ul><li>Default: 30 hari</li><li>Rentang: 1-23 jam/1-90 hari/seumur hidup</li></ul>**Catatan SRN**: Dapat dikonfigurasi untuk SRN<br /><br />Jika Anda mengubah pengaturan jendela, perubahan tersebut berdampak pada interaksi ulang di masa mendatang. Ini tidak berdampak pada interaksi ulang yang ada. |

<div id="exclusion-windows" />

#### Jendela eksklusi

| Jenis jendela | Deskripsi |
| --- | --- |
| Waktu minimal antara konversi re-engagement | Jangan merekam interaksi ulang selama jendela eksklusi.<br /><br />**Waktu minimal antara konversi re-engagement**<ul><li>Saat interaksi ulang, jendela saat in-app event diatribusikan ke kampanye penargetan ulang (utama) dan UA (non-utama) dibuka.</li><li>Hal ini memungkinkan pengukuran kinerja kampanye penargetan ulang.</li><li>Jika jaringan atau kampanye lain menghasilkan interaksi ulang selama jendela ini:<ul><li>[Default] jendela interaksi ulang yang ada ditutup, interaksi ulang lainnya dicatat, dan in-app event berikutnya diatribusikan ke interaksi ulang terbaru.</li><li>Untuk mencegah hal ini, atur waktu Minimum antar konversi interaksi ulang. Dalam hal ini, hanya setelah waktu berlalu minimum, interaksi ulang lebih lanjut dapat direkam.</li></ul></li><li>Pengaturan ini tidak berdampak jika re-engagement window (jendela interaksi ulang) lebih singkat dari durasi pengaturan ini. Contoh: Jika re-engagement windows (jendela interaksi ulang) adalah 1 hari, dan pengaturan ini adalah 4 hari, maka pengaturan ini tidak memiliki pengaruh apa pun.</li><li>Pengaturan ini tidak mempengaruhi waktu antara instalasi dan re-engagement (interaksi ulang).</li></ul>**Lokasi pengaturan**: Laman pengaturan aplikasi<br /><br />**Durasi**:<ul><li>Default: Tidak ada</li><li>Rentang: 1-23 jam/1-30 hari</li></ul> |
| <Anchor target="_blank" href="/marketers/id/docs/set-retargeting-inactivity-window">Periode ketidakaktifan minimum</Anchor> | Jangan rekam keterlibatan ulang atau atribusi ulang selama periode pengecualian.<br /><br />**Tempat pengaturan** Halaman pengaturan mitra terintegrasi di tab Integrasi.<br /><br />**Durasi**:<ul><li>Default: Tidak ada</li><li>0-30 hari</li></ul>**Catatan SRN** : Pertimbangkan bahwa SRN biasanya memiliki aturan periode tidak aktifnya sendiri. Jika pengaturan Anda berbeda dari SRN, ini dapat menyebabkan perbedaan. |
| <Anchor target="_blank" href="/marketers/id/docs/set-up-re-attribution-window">Re-attribution</Anchor> | Jendela atribusi ulang memengaruhi atribusi ulang tetapi tidak memengaruhi interaksi ulang.<br /><br />Pengguna yang menginstal ulang selama jendela atribusi ulang setelah berinteraksi dengan kampanye penargetan ulang diatribusikan ke sumber media penargetan ulang. Bacaan terkait: <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#reinstalls">Reinstalls (penginstalan ulang)</Anchor><br /><br />**Lokasi pengaturan:** Pengaturan aplikasi |

<div id="example-flow-implementing-the-rules" />

#### **Contoh alur penerapan aturan**

![](https://files.readme.io/f4b53c27319370434863c156bf29051db9c2c12fda2128d0faf0f8a6ca6b7002-33563511579537.png)

Daftar periksa aturan interaksi ulang untuk atribusi klik-tayang dan lihat-tayang:

| Aturan | Aturan |
| --- | --- |
| A | Pengguna berinteraksi dengan kampanye penargetan ulang, artinya pengguna yang melihat atau mengklik iklan didefinisikan sebagai iklan penargetan ulang. |
| B | Interaksi terjadi **selama** jendela click-lookback (klik-lihat balik) atau view-through (lihat-tayang). |
| C | Periode ketidakaktifan pengguna melebihi periode ketidakaktifan minimum. |
| D | Dalam hal in-app event, ini terjadi selama jendela interaksi ulang. |
| E | Periode antar interaksi ulang sebelumnya lebih besar dari waktu minimum antar interaksi ulang. |

</Accordion>

<div id="example-retargeting-scenarios" />

<Accordion title="Contoh skenario penargetan ulang">

| **Skenario 1: Pembelian sebelum, selama, dan setelah jendela interaksi ulang**<br /><br />Perjalanan pengguna:<ul><li>Berinteraksi dengan iklan dari jaringan Z, menginstal aplikasi, dan melakukan pembelian (A).</li><li>Berinteraksi dengan iklan penargetan ulang dari jaringan Y, membuka aplikasi, dan melakukan pembelian (B).</li><li>Melakukan pembelian (C).</li></ul>![](https://files.readme.io/f4b53c27319370434863c156bf29051db9c2c12fda2128d0faf0f8a6ca6b7002-33563511579537.png)<br /><br />Kolom P/S: Primer atau Sekunder seperti dijelaskan di <Anchor target="_blank" href="/marketers/id/docs/resolve-retargeting-double-attribution">atribusi ganda dari event penargetan ulang</Anchor> |
| --- |
| **Skenario 2: Beberapa konversi selama jendela atribusi interaksi ulang**<br /><br />Perjalanan pengguna:<ul><li>Berinteraksi dengan iklan dari jaringan Z, menginstal aplikasi, dan melakukan pembelian (A).</li><li>Berinteraksi dengan iklan penargetan ulang dari jaringan Y, membuka aplikasi, dan melakukan pembelian (B).</li><li>Melakukan pembelian (C).</li></ul>![](https://files.readme.io/bf57f8a9597bd56a89bb3f1be3700195e1b153b548cb11ee3d37c65d5382e711-33563474530321.png)<br /><br />Kolom P/S: Primer atau Sekunder seperti dijelaskan di <Anchor target="_blank" href="/marketers/id/docs/resolve-retargeting-double-attribution">atribusi ganda dari event penargetan ulang</Anchor> |

</Accordion>

<div id="retargeting-operations" />

## Operasi penargetan ulang

<div id="retargeting-settings" />

<Accordion title="Pengaturan Retargeting">

Pengaturan berikut diperlukan tergantung pada skenario.

| Jenis konversi | SRN | Non-SRN |
| --- | --- | --- |
| Re-engagement | <ol><li>Buka **Konfigurasi** > **Pengaturan aplikasi.**</li><li>Pastikan bahwa **atribusi** **interaksi ulang**aktif.</li><li>Per SRN: Buka **Konfigurasi** > **Integrasi aktif,** pilih SRN.</li><li>Aktifkan **Atribusi interaksi ulang**.</li></ol> | <ol><li>Buka **Konfigurasi** > **Pengaturan aplikasi.**</li><li>Pastikan bahwa **atribusi interaksi ulang** aktif.</li><li>Per non-SRN: Tambahkan parameter penargetan ulang ke tautan atribusi seperti yang dijelaskan di bagian ini</li></ol> |
| Re-attribution | <ol><li>Buka **Konfigurasi** > **Integrasi aktif,** pilih SRN.</li><li>Aktifkan **Reinstall attribution (atribusi penginstalan ulang).**</li></ol> | <ol><li>Tidak diperlukan pengaturan eksplisit.</li><li>Tambahkan parameter penargetan ulang ke tautan atribusi seperti yang dijelaskan di bagian ini.</li></ol> |

<div id="non-srn-settings" />

#### **Pengaturan Non-SRN**

**Untuk menyiapkan mitra penargetan ulang jaringan iklan (non-SRN)**:

1. Di AppsFlyer, buka **Konfigurasi** >  **Integrasi Aktif**.
2. Pilih jaringan iklan.
3. Hidupkan **Aktifkan** **pengaturan penargetan ulang**. Ini mengubah tautan atribusi ke URL penargetan ulang, dengan menambahkan `is_retargeting=true` ke tautan.   

   [![](https://files.readme.io/68b8939885439a4f0e6d1ec6601552185905d1afc817da9fb88ccfe043a83364-33563511582609.png)](https://files.readme.io/68b8939885439a4f0e6d1ec6601552185905d1afc817da9fb88ccfe043a83364-33563511582609.png)
4. Pilih salah satu dari berikut:
   * **Gunakan tautan atribusi standar** untuk tautan platform tunggal (khusus aplikasi).
   * **Gunakan OneLink**.
     * Masukkan **URL deep link**, jika diperlukan (lihat panduan <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Deep Linking</Anchor>).
5. Salin URL yang dihasilkan dan berikan URL tersebut ke jaringan iklan untuk digunakan bersama dengan kampanye penargetan ulang.  
   **Catatan**: URL tidak persisten dan tidak dapat disimpan.

</Accordion>

<div id="retargeting-dashboard" />

<Accordion title="Dashboard penargetan ulang">

Dasbor Tinjauan (Overview) berisi metrik penargetan ulang serta metrik akuisisi pengguna. Metrik ini berbasis LTV dan berhubungan dengan pengguna yang berinteraksi dengan kampanye penargetan ulang.

**Untuk melihat data penargetan ulang** :

1. Di AppsFlyer, buka **Dashboard**(Dasbor) > **Overview**(Tinjauan) .
2. Klik **View type**(Jenis tampilan) , lalu pilih **Retargeting**(Penargetan ulang) .  
   Data penargetan ulang ditampilkan.  
   Perhatikan! Anda juga dapat melihat data penargetan ulang dalam tampilan terpadu. Lihat Dashboard view types (Jenis tampilan dasbor).

</Accordion>

<div id="retargeting-attribution-links" />

<Accordion title="Tautan atribusi penargetan ulang">

* Link penargetan ulang serupa dengan link akuisisi user reguler.
* Buat untuk:
  * Non-SRN yang mendukung penargetan ulang.
  * Media milik sendiri, gunakan laman <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">link management (manajemen tautan)</Anchor>.

Penargetan ulang parameter tautan atribusi

| Parameter | Deskripsi | Wajib |
| --- | --- | --- |
| `is_retargeting` | Atur ke: `is_retargeting=true` | Ya |
| ID Iklan | Jika memungkinkan, kirimkan ID iklan seperti IDFA, OAID, IDFV, dan sebagainya. <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#probabilistic-modeling">Batasan Pemodelan Probabilistik untuk aplikasi iOS.</Anchor> | Tidak |
| Penargetan ulang click lookback window (jendela lookback klik) | <ul><li>Penargetan ulang<Anchor target="_blank" href="/marketers/id/docs/set-up-lookback-windows">jendela lookback klik</Anchor> bekerja persis seperti kampanye akuisisi user.</li><li>Penargetan ulang ini menentukan periode maksimum waktu berlalu antara saat pengguna mengklik iklan hingga pengguna diatribusikan.</li><li>Jendela lookback diatur menggunakan parameter `&af_click_lookback`.</li><li>Pengaturan defaultnya adalah 7 hari.</li></ul>**<span id="01ECF12NKTFH6Q2NH4B1WKSYF9"></span>Contoh**<br />Untuk menetapkan lookback window click-through 14 hari, tambahkan parameter berikut ke link atribusi kampanye retargeting: `&af_click_lookback=14d` | Tidak |
| Penargetan ulang timer lookback lihat-tayang (view-through lookback timer) | <ul><li>Penargetan ulang <Anchor target="_blank" href="/marketers/id/docs/set-up-lookback-windows">jendela lookback lihat-tayang</Anchor> bekerja persis seperti kampanye akuisisi pengguna.</li><li>Penargetan ulang ini menentukan periode maksimum waktu berlalu setelah pengguna melihat iklan hingga pengguna diatribusikan.</li><li>Defaultnya adalah 1 hari.</li><li>Jendela lookback diatur menggunakan</li></ul>`af_viewthrough_lookback = {time}`<br /><br /><br /><br />**<span id="01ECF12NKTE8W4K72VATN9RM2X"></span>Contoh**<br />Untuk menetapkan jendela lookback lihat-tayang 5 jam, tambahkan berikut ini ke tautan atribusi kampanye penargetan ulang: `& af_viewthrough_lookback = 5j` | Tidak |
| Periode Waktu Re-engagement | <ul><li>Jendela **interaksi ulang** dapat diatur pada antarmuka pengguna tautan atribusi. Ini mengatur parameter **af\_reengagement\_window** ke tautan atribusi. Parameter ini dapat ditambahkan secara manual.</li><li>Default-nya adalah 30 hari.</li><li>Nilai untuk re-engagement window tersedia sebagai berikut:</li><li>Jam:1- 23 jam</li><li>Hari: 1-90 hari</li><li>Masa pakai selamanya: Tetap ada sampai pengguna mencopot penginstalan (uninstall) atau melakukan interaksi ulang lainnya, misalnya, af\_reengagement\_window=lifetime</li></ul>Misalnya, **af\_reengagement\_window=60d** artinya event yang dilaporkan dalam 60 hari setelah interaksi ulang diatribusikan ke sumber media penargetan ulang. | Tidak |

<div id="retargeting-view-through-lookback-period" />

#### Penargetan ulang periode lookback lihat-tayang

```http
https://app.appsflyer.com/id123456789?pid=remerge_int&af_dp=mydeeplink%3A%2F%2F&
clickid={clickid}&af_siteid={publisher}&idfa={device_id_raw}&sha1_idfa={device_id}
&af_sub1={creative_name}&is_retargeting=true&af_reengagement_window=60d
```

</Accordion>

<div id="retargeting-reports-and-raw-data" />

<Accordion title="Penargetan ulang laporan dan data lengkap">

* Laporan penargetan ulang, sama seperti laporan UA <Anchor target="_blank" href="/marketers/id/docs/aggregated-and-analytics-reporting-overview">gabungan</Anchor> dan <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">data lengkap</Anchor>, tersedia menggunakan alat pelaporan.
* Penargetan ulang in-app event dan sesi <Anchor target="_blank" href="/marketers/id/docs/resolve-retargeting-double-attribution">diatribusikan dua kali.</Anchor>

**Laporan Konversi Penargetan Ulang**

* Laporan Retargeting Conversions berisi data lengkap re-engagement dan re-attribution.
* Beberapa bidang memiliki arti berbeda dengan yang digunakan dalam laporan akuisisi pengguna dalam konteks penargetan ulang.

Interpretasi laporan data lengkap dalam konteks penargetan ulang

| Kolom | **Deskripsi** |
| --- | --- |
| eventName | <ul><li>Pengisian bidang bergantung pada jenis laporan.</li><li>Laporan in-app event: Nama in-app event.</li><li>Laporan konversi penargetan ulang: interaksi ulang atau atribusi ulang. **Perhatikan!** Dalam hal Data Locker, nilainya adalah sebagai berikut:<ul><li>penginstalan artinya atribusi ulang</li><li>penargetan ulang artinya interaksi ulang</li></ul></li></ul> |
| Attributed touch-type | Jenis Interaksi:<ul><li>Klik</li><li>Impresi</li></ul> |
| Waktu sentuh yang diatribusikan | Waktu interaksi penargetan ulang |
| Install time | Peluncuran aplikasi pertama setelah interaksi ulang atau atribusi ulang. |
| Event Time | Waktu event tersebut terjadi |
| AppsFlyer ID | <ul><li>Atribusi ulang: ID AppsFlyer baru</li><li>Interaksi ulang: Tetap tidak berubah</li></ul> |
| Is retargeting | TRUE untuk penargetan ulang konversi dan event |
| Is primary attribution | TRUE untuk penargetan ulang konversi dan event |
| Jenis konversi penargetan ulang | Bidang ini akan ditiadakan di masa mendatang (tanggalnya akan diumumkan.) Gunakan conversion\_type dan campaign\_type untuk menentukan konteks konversi.<ul><li>Re-engagement</li><li>Re-attribution</li></ul> |
| Tipe konversi | Jenis konversi:<ul><li>Install</li><li>Penginstalan ulang (1)</li><li>Re-engagement</li><li>Tidak dikenal (2)</li></ul>(1) If conversion\_type= reinstall and campaign\_type=retargeting is equivalent to retargeting\_conversion\_type=re-attribution<br /><br />(2) In-app event/sesi tidak diatribusikan ke sumber media apa pun. |
| Jenis kampanye | Sumber membawa pengguna:<ul><li>UA</li><li>Organik</li><li>Retargeting</li><li>Tidak dikenal</li></ul> |
| Attribution Lookback | Lookback Windows Click-Through Penargetan Ulang |
| Original URL | Berisi salah satu dari yang berikut:<ul><li>Tautan penargetan ulang</li><li>Data deep linking</li><li>Kosong untuk SRN</li></ul> |
| Bidang kontribusi | Tidak tersedia untuk interaksi ulang |

</Accordion>

<div id="additional-information" />

## Informasi Tambahan

<div id="probabilistic-modeling" />

<Accordion title="Pemodelan probabilistik">

Mulai 17 Februari 2021, Pemodelan Probabilistik didukung dalam penargetan ulang. Dalam hal <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#catatan-untuk-aplikasi-ios">batasan iOS 14.5+</Anchor> berlaku. Lookback window yang digunakan dalam retargeting Probabilistic Modeling diatur secara dinamis oleh AppsFlyer dan bergantung pada sistem operasi. 

Verifikasi bahwa klik yang dikirim menyertakan <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#parameter-pemodelan-probabilistik-untuk-jaringan-iklan">parameter Pemodelan Probabilistik</Anchor> yang diperlukan.

</Accordion>

<div id="app-requirements" />

<Accordion title="Persyaratan aplikasi">

Untuk menjalankan kampanye penargetan ulang, aplikasi harus memenuhi persyaratan minimum berikut.

* iOS
  * Selain integrasi AppsFlyer SDK standar, Anda harus menambahkan kode tambahan ke app delegate, lihat artikel (bagian tautan atribusi) <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#tautan-langsung-deep-linking-dengan-onelink">SDK Integration (Integrasi SDK)</Anchor>.
  * Untuk iOS 9, Kode terbuka Aplikasi Tautan Universal harus diterapkan. <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">Tautan Universal dengan iOS 9</Anchor>.
* Android:

  * Jika deep link (tautan langsung) membuka aktivitas selain aktivitas utama, lihat artikel (bagian tautan atribusi) <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#deep-linking">SDK Integration (Integrasi SDK)</Anchor> .

</Accordion>

<div id="retargeting-limitations" />

<Accordion title="Batasan penargetan ulang">

* Mulai 17 Februari 2021, penargetan ulang mendukung Pemodelan Probabilistik.
* Data biaya kampanye untuk penargetan ulang tersedia di dasbor dan tinjauan Kohort serta Laporan dalam tampilan terpadu.

</Accordion>

<div id="faq" />

<Accordion title="Pertanyaan Umum">

| **Penargetan ulang klik (retargeting click):**<ul><li>Penargetan ulang klik berisi semua pengguna yang berinteraksi dengan tautan atribusi AppsFlyer.</li><li>Klik dari SRN atau dari <Anchor target="_blank" href="/marketers/id/docs/measuring-push-notification-re-engagement-campaigns">notifikasi push</Anchor> tidak diperhitungkan.</li><li>Beberapa klik menghasilkan penginstalan baru yang diatribusikan sebagai akuisisi pengguna. Hal ini terjadi ketika non-pengguna, atau pengguna terakhir setelah berakhirnya<Anchor target="_blank" href="/marketers/id/docs/set-up-re-attribution-window">jendela atribusi ulang</Anchor>, berinteraksi dengan tautan penargetan ulang dan penginstalan.</li></ul> |
| --- |
| **Kapan waktu interaksi teratribusi sama dengan waktu penginstalan?**<ul><li>Ketika user klik universal link atau app link dan melakukan deep linking, mereka diarahkan ke app tanpa melalui AppsFlyer terlebih dahulu.</li><li>Ketika app diluncurkan dan SDK melaporkan re-engagement baru, AppsFlyer akan mereproduksi data klik, menggunakan label waktu yang sama dengan peluncuran app. Hal ini membuat waktu interaksi dan peluncuran sama.</li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model">Model Atribusi AppsFlyer</Anchor>
> * <Anchor target="_blank" href="/marketers/id/docs/audiences-guide">Panduan audiens</Anchor>

<div data-zendesk-anchors="retargeting-fundamentals=dasar-dasar-penargetan-ulang h_01HCFJHC85VK0A05X5F69E2WKT=dasar-dasar-penargetan-ulang h_01HCFJHC851PV0VR42H07VQAXF=tips h_01HCFJHC85EW8MBQ8MBXBVPF03=reengagement-rules-and-windows inclusion-windows=jendela-inklusi h_01HCFJHC85FRFJ531Y08DW03Y2=jendela-inklusi exclusion-windows=jendela-eksklusi h_01HCFJHC85ECS3PJV80D943TVY=jendela-eksklusi example-flow-implementing-the-rules=contoh-alur-penerapan-aturan h_01HCFJHC8529NW0ABMQ0RB3E8R=contoh-alur-penerapan-aturan h_01HCFJHC85E1SWGYN0BH603BV9=example-retargeting-scenarios retargeting-operations=operasi-penargetan-ulang h_01HCFJHC863XPHNWRHJ60JPSRF=operasi-penargetan-ulang h_01HCFJHC86XNCT5AQP48R9ZDC4=retargeting-settings nonsrn-settings=pengaturan-non-srn h_01HCFJHC865V36R3H58D5PWXYY=pengaturan-non-srn h_01HCFJHC860BS9YJM99G437G24=retargeting-dashboard h_01HCFJHC860Y5HZN66DRNN2Q89=retargeting-attribution-links retargeting-viewthrough-lookback-period=penargetan-ulang-periode-lookback-lihat-tayang h_01HCFJHC863CSP03AYBXFSNC37=penargetan-ulang-periode-lookback-lihat-tayang h_01HCFJHC86MNFRGYMN776FYHJV=retargeting-reports-and-raw-data additional-information=informasi-tambahan h_01HCFJHC86RKKPPMBYEZV4Q3X9=informasi-tambahan h_01HCFJHC8690EN19DDX7P24AD0=probabilistic-modeling h_01HCFJHC862E6C46Q7645VJ6CZ=app-requirements h_01HCFJHC86SMKZ1HT5KHQNQS1N=retargeting-limitations h_01HCFJHC86BVSVRNAGJEKZFCJP=faq h_01HE7TPR7928SF2W8ZJS55Y5BG=lihat-juga" />
