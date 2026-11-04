---
title: Bermigrasi ke AppsFlyer dari vendor lain
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2019-07-01T13:11:37Z'
  edited_at: '2023-08-23T02:36:04Z'
  id: 360001923697
  locale: id
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/id/articles/360001923697
---
> **Sekilas:** Rencanakan migrasi Anda ke AppsFlyer dari vendor atribusi lain. Pahami cara menghindari tagihan ganda, duplikasi data, dan kehilangan data selama periode migrasi.

![alur migrasi](https://files.readme.io/31d67493ae3ae6912b4da3163ebb731a8d58494c3007ef1d08cb7332226d9e81-360017326677.png)

<div id="about-migrating-to-appsflyer-from-other-vendors" />

## Overview

Bermigrasi ke AppsFlyer dari vendor lain mencakup tugas-tugas utama berikut:

* [Integrasi SDK](/docs/migration-to-appsflyer-from-other-vendors#integrasi-sdk)
* [Migrasi perangkat](/docs/migration-to-appsflyer-from-other-vendors#migrasi-perangkat---opsional)
* [Migrasi kampanye](/docs/migration-to-appsflyer-from-other-vendors#migrasi-kampanye)
* [Penyiapan laporan data](/docs/migration-to-appsflyer-from-other-vendors#penyiapan-laporan-data)

Anda dapat mengerjakan tugas ini secara bersamaan. Namun, kami menyarankan Anda:

* Selesaikan semua tugas sebelum merilis aplikasi Anda yang telah diperbarui dengan AppsFlyer SDK.
* Hentikan dulu kampanye pemasaran yang ada sebelum melakukan migrasi ID perangkat.

> 📘 **Catatan**
>
> Jika Anda ingin membandingkan pengukuran atribusi antara MMP Anda saat ini dan AppsFlyer untuk kampanye dan sumber media yang sama, lihat <Anchor target="_blank" href="/marketers/id/docs/measuring-attribution-with-multiple-mmps">artikel ini</Anchor>.

<div id="tasks" />

## Tugas

Tabel berikut menjelaskan ruang lingkup pekerjaan yang diperlukan untuk setiap tugas. Untuk melihat perincian tugas-tugas umum secara tepat sesuai urutan yang harus Anda selesaikan, serta untuk mencatat kemajuan Anda, unduh <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/1x6kdhfnfKLYHJgsROPUv7pQYC6i-Q5H3DdejBr8jKjw/export?format=xlsx">spreadsheet ini</Anchor>

<div id="scope-of-work" />

#### Lingkup kerja

<table><thead><tr><th>Tugas</th><th>Tindakan yang diperlukan</th><th>Siapa saja yang terlibat</th><th>Perkiraan waktu</th><th>Catatan</th></tr></thead><tbody><tr><td>Prasyarat</td><td><ol><li> <a href="https://www.appsflyer.com/get-started" target="_blank">Buat akun AppsFlyer</a> .</li><li> <a href="./adding-an-app-to-appsflyer" target="_blank">Tambahkan aplikasi</a> di AppsFlyer</li><li>[Opsional] Ubah <a href="./set-up-re-attribution-window" target="_blank">jendela atribusi ulang</a> 90 hari default agar sesuai <span>dengan definisi Anda tentang pengguna aktif.</span> </li></ol></td><td>Pengguna dashboard Marketer/AppsFlyer</td><td><p>2 jam</p></td><td> </td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#integrasi-sdk">Integrasi SDK</a></td><td><ul><li>Integrasikan AppsFlyer SDK di aplikasi Anda.</li><li>Memetakan in-app event S2S atau SDK.</li><li>Perbarui versi aplikasi pada app store.</li></ul></td><td>Pengembang aplikasi:</td><td><p>1-2 minggu</p></td><td><ul><li> <strong>Direkomendasikan</strong>: Integrasikan SDK AppsFlyer dalam aplikasi pra-produksi untuk pengujian.</li><li>Aplikasi produksi harus diperbarui di app store setelah semua tugas lainnya selesai.</li></ul></td></tr><tr><td> <a href="./migration-to-appsflyer-from-other-vendors#migrasi-perangkat---opsional">Migrasi perangkat</a> [opsional]</td><td>Migrasikan ID perangkat untuk menghindari atribusi ganda dari pengguna yang sudah ada.</td><td>Data engineer</td><td>1-2 minggu</td><td rowspan="2"><ul><li>Pertimbangkan untuk menjeda kampanye saat ini sebelum migrasi, dan melanjutkannya setelah versi aplikasi diperbarui. </li><li>Pertimbangkan untuk mengulangi migrasi perangkat pada tanggal migrasi terakhir untuk memastikan cakupan yang lengkap. </li></ul></td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#migrasi-kampanye">Migrasi kampanye</a></td><td><ul><li>Integrasikan jaringan iklan Anda di AppsFlyer</li><li>Migrasikan kampanye yang ada dari:  <ul><li>SRN</li><li>Jaringan iklan non-SRN</li><li>Media yang Dimiliki Sendiri</li></ul></li></ul></td><td>Pemasar/manajer UA</td><td>1-3 minggu</td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#penyiapan-laporan-data">Penyiapan laporan data</a></td><td><ul><li>Adaptasi/petakan struktur laporan Anda saat ini ke struktur laporan AppsFlyer.</li><li>Bersiaplah untuk menerima laporan AppsFlyer.</li></ul></td><td>Data engineer</td><td>2-4 minggu</td><td> </td></tr></tbody></table>

<div id="sdk-integration" />

### Integrasi SDK

<div id="sdk-integration::c763138b" />

<Accordion title="Integrasi SDK">

SDK AppsFlyer yang terintegrasi ke dalam aplikasi adalah penghubung antara aplikasi dan platform AppsFlyer. Ini melaporkan penginstalan aplikasi, pembukaan aplikasi, in-app event, dan sebagainya.

**Untuk mengintegrasikan SDK AppsFlyer** :

1. Integrasikan SDK AppsFlyer ke dalam aplikasi.  
   Lihat panduan untuk integrasi SDK <Anchor target="_blank" href="/marketers/id/docs/sdk-integration-overview">Android</Anchor> dan <Anchor target="_blank" href="/marketers/id/docs/sdk-integration-overview">iOS</Anchor> .
2. Petakan in-app event yang ingin Anda rekam, menggunakan skema AppsFlyer.  
   Ini dapat dilakukan melalui <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview">SDK</Anchor> atau <Anchor target="_blank" href="/marketers/id/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor> .
3. Hapus SDK kompetitor vendor atribusi.  
   Anda dapat melakukannya segera dan beralih secara eksklusif ke AppsFlyer, atau menjalankan kedua SDK secara bersamaan selama beberapa minggu. Lihat rincian opsi ini pada tabel di bawah.  

| Opsi | Apa yang terjadi setelah  <br /> rilis versi aplikasi yang diperbarui | Dampak |
| --- | --- | --- |
| Hapus  SDK kompetitor (disarankan) | Hanya AppsFlyer yang mencatat penginstalan baru dan memperbarui pengguna.  <br />Kompetitor masih menampilkan event yang dilakukan oleh pengguna, sampai pengguna memperbarui aplikasinya juga. | <ul><li>Transisi cepat.</li><li>Tidak ada atribusi ganda.</li></ul> |
| Pertahankan SDK kompetitor  untuk masa transisi | AppsFlyer dan kompetitor mengatribusikan penginstalan baru dan melaporkan event. Hapus SDK kompetitor nanti. | <ul><li>Validasi data dimungkinkan. Artinya, Anda dapat membandingkan data dari AppsFlyer dan vendor lainnya.</li><li>Atribusi ganda, yang dapat menyebabkan tagihan ganda dengan jaringan iklan. Lihat contoh berikut ini.</li><li>Beban kerja lebih tinggi.</li></ul> |

4. Setelah semua tugas lain dalam lingkup pekerjaan diselesaikan, perbarui versi aplikasi dengan SDK AppsFlyer ke market. Pengguna baru diatribusikan oleh AppsFlyer.   
   **Catatan** :
   * Pastikan untuk memperbarui aplikasi untuk iOS, Google Play, dan market selain play store Android yang relevan.
   * Aplikasi Android Anda mungkin ada di situs APK tidak resmi, meskipun Anda tidak mengetahuinya (telusuri nama paket aplikasi Anda di web untuk mengetahuinya). Situs APK membutuhkan beberapa waktu untuk memperbarui ke versi terbaru, sehingga mereka mungkin membawa pengguna organik, yang memasang versi lama tanpa SDK AppsFlyer.
   * Peluncuran pembaruan aplikasi pada app store dapat membutuhkan waktu beberapa hari hingga selesai sepenuhnya. Pengguna yang menginstal selama fase ini mungkin masih mendapatkan versi sebelumnya.

</Accordion>

<div id="device-migrationoptional" />

### Migrasi perangkat - opsional

<div id="about-device-migration" />

<Accordion title="Tentang migrasi perangkat">

Migrasi perangkat adalah proses mengunggah daftar ID perangkat pengguna Anda yang sudah ada (IDFA, IDFV, GAID, CUID) ke AppsFlyer. Anda harus melakukan proses ini sebelum merilis versi aplikasi baru, yang akan menyertakan SDK AppsFlyer. Ada dua opsi saat memigrasi perangkat, migrasi yang [diatribusikan](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration) atau yang [tidak diatribusikan](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration) .

Migrasi perangkat memecahkan masalah data yang terkait dengan pengguna aplikasi yang sudah ada yang mengunduh aplikasi, dan diatribusi oleh vendor Anda sebelumnya. Misalnya, biaya ganda SRN, yang terjadi ketika pengguna awalnya diatribusi ke SRN di bawah vendor sebelumnya, dan yang masih dalam jendela lookback, diklaim oleh SRN lagi di bawah AppsFlyer.

<div id="example" />

> 📄 **Contoh**
>
> * Pengguna baru mengeklik iklan di aplikasi Facebook dan menginstal aplikasi Anda pada tanggal 15 Juni.
> * Pada tanggal 24 Juni, pengguna memperbarui aplikasi ke versi dengan SDK AppsFlyer, dan meluncurkannya. Untuk AppsFlyer, ini adalah pengguna baru, yang perlu diatribusikan secara real-time.
> * AppsFlyer menanyakan Meta ads dengan ID perangkat pengguna. Karena pengguna masih berada dalam jendela lookback 28 hari Meta ads, Meta ads mengatribusikan pengguna secara mandiri. Ini menyebabkan tagihan ganda kepada pemilik aplikasi untuk pengguna yang sama.

Setelah Anda bermigrasi perangkat, data ditampilkan di AppsFlyer sebagai berikut:

* **Penginstalan data**: Mirip dengan <Anchor target="_blank" href="/marketers/id/docs/set-up-re-attribution-window#reinstall">Penginstalan ulang</Anchor>, perangkat yang dimigrasi tidak memiliki data penginstalan. Penginstalan perangkat yang dimigrasi tidak ditampilkan di AppsFlyer.
* **Data sesi dan in-app event**: Direkam dan ditampilkan sebagai organik untuk [metode migrasi perangkat yang tidak diatribusikan](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration), atau diatribusikan ke sumber media dan kampanye, jika menggunakan [metode atribusi](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration).
* **Penargetan ulang**: Atribusi ulang dan interaksi ulang ditampilkan secara normal.
* **Data aktivitas:** Ditampilkan secara normal.
* **Retensi dan data kohort:** Perangkat yang dimigrasikan tidak memiliki catatan penginstalan. Dengan demikian, mereka tidak dikaitkan kohort apa pun, dan tidak dapat ditampilkan di laporan Retensi dan kohort.

</Accordion>

<div id="how-to-migrate-devices" />

<Accordion title="Cara memigrasi perangkat">

**Untuk memigrasi perangkat:**

1. Tentukan populasi pengguna yang akan dimigrasi. Anda dapat memigrasi semua pengguna yang sudah ada (yang mungkin mencegah Anda mendapatkan data atribusi ulang yang akurat dari AppsFlyer), atau pengguna yang baru saja menginstal aplikasi Anda (yang dapat menyebabkan tagihan ganda untuk pengguna yang lebih lama).  
   **Kami merekomendasikan memigrasi pengguna yang aktif selama periode jendela atribusi ulang Anda saat ini.** Misalnya, jika aplikasi Anda memiliki jendela atribusi ulang 90 hari, migrasikan pengguna yang memiliki setidaknya satu sesi selama 90 hari sebelumnya.
2. [Opsional] Beri tahu pemasar / manajer UA untuk menjeda kampanye pemasaran yang ada (dari SRN, jaringan iklan non-SRN, media yang dimiliki, dll.) hingga migrasi perangkat selesai.  
   Jika Anda memutuskan untuk tidak menjeda kampanye, migrasikan ID perangkat yang tersisa dari vendor lain segera setelah versi aplikasi yang diperbarui dengan SDK AppsFlyer dirilis ke app store.
3. Siapkan file CSV berdasarkan populasi pengguna yang dipilih, menggunakan struktur migrasi yang [diatribusikan](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration) atau [tidak diatribusikan](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration) . <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?output=csv">Lihat sampel CSV</Anchor>
4. Kirim CSM AppsFlyer Anda CSV.  
   CSM Anda akan memigrasi ID perangkat ke AppsFlyer.

</Accordion>

<div id="attributed-migration" />

<Accordion title="Migrasi yang diatribusikan">

Perangkat yang dimigrasikan ke AppsFlyer dengan metode ini memiliki in-app event dan sesi yang dicatat serta ditampilkan sesuai dengan sumber media yang dilaporkan oleh vendor atribusi sebelumnya, dan menurut kebijakan penyimpanan data jaringan iklan.

<div id="attributed-device-migration-csv-structure" />

#### Struktur CSV migrasi perangkat yang teratribusi

| Nama   <br />kolom | Deskripsi | Wa-jib | Contoh |
| --- | --- | --- | --- |
| app\_id | ID Aplikasi seperti yang terlihat di dashboard AppsFlyer | Ya | <ul><li>Android: com.great.app1</li><li>iOS: id123456789</li></ul> |
| platform | Platform perangkat: iOS atau Android | Ya | <ul><li>ios</li><li>android</li></ul> |
| device\_id | <ul><li>Android: gaid</li><li>iOS: IDFV (direkomendasikan, jika tersedia) atau IDFA</li><li>Jangan menduplikasi kombinasi ID perangkat dan ID aplikasi yang sama di beberapa baris. Jika terjadi duplikasi, kemunculan terakhir dalam file akan digunakan.</li></ul> | Ya | <ul><li>**gaid** (huruf kecil): 9c9a82fb-d5de-4cd1-90c3-527441c11828</li><li>**IDFV** (huruf besar): A7328D98-A973-402A-8B87-D22A8611F2AF</li><li>**IDFA** (huruf besar): 9876F1SS-2983-3855-27RR-2R626772VFNB</li></ul> |
| id\_type | <ul><li>Android: advertiserId (juga mendukung amazon\_aid)</li><li>iOS:idfa or idfv</li><li>Saat ini, identifier lain, OAID, IMEI, dan ID Android tidak didukung.<br />Gunakan migrasi yang tidak diatribusikan untuk pengguna Android, yang bukan dari Google Play.</li></ul> | Ya | <ul><li>advertiserId</li><li>idfa</li><li>idfv</li></ul> |
| install\_time | Waktu instal aplikasi asli dengan <Anchor target="_blank" href="http://joda-time.sourceforge.net/cal_iso.html">format ISO 8601</Anchor> UTC:<br />**yyyy-mm-ddTHH:MM:SS.SSS**<ul><li>**Praktik terbaik** : Biarkan bidang ini kosong. Dalam hal ini, waktu migrasi digunakan sebagai gantinya.</li><li>Jika Anda mengisi tanggal, ini harus berupa tanggal yang valid, tidak lebih lama dari jendela atribusi ulang.<ul><li>Dalam beberapa kasus, perangkat yang dimigrasikan pada peluncuran pertama diperlakukan sebagai penginstalan baru.<br />Contoh 1: Perangkat dengan waktu penginstalan sebelum tanggal pembuatan file dikurangi jendela atribusi ulang aplikasi tidak dimigrasikan dengan atribusi. Pada peluncuran pertama, perangkat diperlakukan sebagai penginstalan baru (kemungkinan besar organik).<br />Contoh 2: Perangkat dimigrasikan dengan waktu penginstalan, tetapi peluncuran pertama hanya terjadi setelah migrasi dan di luar jendela atribusi ulang. Dalam hal ini, penginstalan baru dicatat.</li></ul></li></ul> | Tidak | 2018-01-22T08:45:33.412 |
| media\_source | <ul><li>Antara:<ul><li>ID mitra AppsFlyer seperti yang muncul di dashboard AppsFlyer</li><li>Sumber media khusus (tidak boleh menjadi ID mitra).</li></ul></li><li>Untuk mendapatkan daftar ID mitra seperti yang dibutuhkan oleh AppsFlyer:<ul><li><Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner">Aktifkan semua mitra terintegrasi yang relevan.</Anchor></li><li>Jalankan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_v1-integrations">API Dapatkan integrasi aktif</Anchor> untuk daftar semua integrasi aktif.</li><li>Gunakan **media\_source\_name** dari API sebagai nilai **media\_source** di CSV.</li><li>Pengecualian:<ul><li>Untuk Iklan Penelusuran Apple gunakan **Iklan Penelusuran Apple**.</li><li>Untuk Twitter, gunakan **twitter**.</li></ul></li></ul></li><li>Format: Nilai peka huruf besar/kecil</li></ul> | Ya | Non-organik: facebook\_int, googleadwords\_int<br /><br />Organik: organic |
| integrated\_partner | <ul><li>Menunjukkan apakah sumber media merupakan mitra terintegrasi atau bukan. Artinya sumber media organik atau khusus.</li><li>Format: Nilai peka huruf besar/kecil</li></ul> | Ya | <ul><li>ya</li><li>tidak (jika media\_source adalah khusus)</li></ul> |
| kampanye | Untuk detail atribusi yang lebih terperinci, berikan nama kampanye asli.<br /><br />Format: String | Tidak |  |
| campaign\_id | Untuk detail atribusi yang lebih terperinci, berikan ID kampanye asli.<br /><br />Format: String tanpa spasi | Tidak |  |

**Aturan file CSV:**

* File CSV dapat berisi perangkat pengguna dari beberapa aplikasi.
* Jangan menduplikasi kombinasi ID perangkat dan ID aplikasi yang sama di beberapa baris. Jika terjadi duplikasi, kemunculan terakhir dalam file akan digunakan.
* Semua header kolom harus menyertakan: app\_id, platform, device\_id, id\_type, install\_time, media\_source, integrated\_partner, campaign, campaign\_id **Catatan**: Urutan bidang penting dan harus dijaga.
* Anda dapat menambahkan IDFV dan IDFA untuk perangkat yang sama, namun keduanya harus berada di baris terpisah. Semua bidang di baris terpisah harus sama, kecuali device\_id.
* Setiap baris harus berisi tepat 9 bidang yang dipisahkan dengan koma.
* Biarkan bidang tidak wajib kosong (kosong).
* File dapat berisi hingga 20 juta baris.
* Jika Anda memiliki banyak file, berikan nama yang unik untuk setiap file.
* Enkode data menggunakan UTF-8.
* [Opsional] Kompres file menggunakan ZIP atau GZIP.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=0&single=true&output=csv">Lihat sampel CSV</Anchor>

</Accordion>

<div id="nonattributed-migration" />

<Accordion title="Migrasi tanpa atribusi">

Perangkat yang dimigrasikan ke AppsFlyer dengan metode ini dicatat (tetapi tidak ditampilkan) sebagai pengguna organik. In-app event dan sesi-nya juga dicatat dan ditampilkan sebagai organik.

<div id="non-attributed-device-migration-csv-file-structure" />

#### Struktur file CSV migrasi perangkat yang tidak diatribusikan

| Kolom | Kapan digunakan | Contoh |
| --- | --- | --- |
| App ID + IDFA/GAID/IDFV | <ul><li>Jika semua pengguna Android Anda memiliki identifier GAID.</li><li>Pengguna khusus iOS</li></ul> | [<Image alt="device_migration_file_option_1.png" src="https://files.readme.io/e4902c1fd33dc348d636f0c9a571bddad966c37aa1f8fad19cf6160c8c1b7dfb-360003138317.png" width="244px" />](https://files.readme.io/e4902c1fd33dc348d636f0c9a571bddad966c37aa1f8fad19cf6160c8c1b7dfb-360003138317.png) |
| ID Aplikasi + ID Perangkat + Jenis ID Perangkat | <ul><li>Jika beberapa pengguna Android Anda hanya memiliki IMEI atau ID Android, tetapi tidak GAID (toko aplikasi selain play store, versi Android di bawah 4.4.2).</li><li>ID Android harus memiliki format heksadesimal.</li></ul>**Catatan**:<ul><li>Gunakan string yang tepat untuk kolom **tipe ID** : advertiserId (juga mendukung amazon\_aid), idfa, idfv, android\_id, imei.</li><li>Jika Anda menggunakan android\_id atau imei, dan kemudian AppsFlyer menerima pengidentifikasi yang lebih baik, atribusi baru mungkin dicatat.</li></ul> | [<Image alt="device_migration_file_option_2.png" src="https://files.readme.io/a85463bc7fd8f08e9c5e20d09b3b39f951547f18402c225ef3d952b18923b648-360003224698.png" width="244px" />](https://files.readme.io/a85463bc7fd8f08e9c5e20d09b3b39f951547f18402c225ef3d952b18923b648-360003224698.png) |

**Aturan file CSV:**

* File CSV dapat berisi perangkat pengguna dari beberapa aplikasi.
* Setiap baris berisi satu ID perangkat per aplikasi.
* File harus menyertakan semua header kolom sebagai berikut:
  * Opsi1: File harus menyertakan semua header kolom sebagai berikut: app\_id, device\_id
  * Opsi 2: app\_id, device\_id, id\_type
* ID Aplikasi dalam huruf kecil
* Identifier Android dalam huruf kecil
* IDFA/IDFV dalam huruf besar
* Hingga 25 juta baris diizinkan

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=935533759&single=true&output=csv">Lihat sampel CSV</Anchor>

</Accordion>

<div id="campaign-migration" />

### Migrasi kampanye

Alihkan kampanye pemasaran yang ada ke AppsFlyer untuk mengaktifkan atribusi AppsFlyer, dan hindari tagihan ganda dan hilangnya data atribusi.

**Catatan** : Anda dapat memilih untuk hanya memigrasi beberapa kampanye pemasaran dalam satu waktu. Dalam kasus ini, Anda dapat menyegmentasikan kampanye yang ingin Anda migrasikan menurut sumber media (misalnya, jaringan atau agensi iklan), geo, atau kampanye.

<div id="srns" />

<Accordion title="SRN">

SRN merespons Mitra Pengukuran Seluler (MMP) ketika diminta tentang interaksi perangkat tertentu. Jika dua MMP, misalnya AppsFlyer dan vendor atribusi yang berkompetisi, meminta SRN yang sama tentang penginstalan perangkat yang sama, mungkin dikenakan biaya ganda.

**Untuk memigrasi kampanye SRN** :

* Aktifkan dan konfigurasikan <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns#srn-diintegrasikan-dengan-appsflyer">SRN</Anchor> yang relevan di AppsFlyer.

<div id="note-1" />

> 📘 **Catatan**
>
> * SRN dapat menjalankan beberapa MMP (kecuali Meta ads dan Twitter).
> * Meta ads tidak dapat menghapus duplikat in-app event.

</Accordion>

<div id="nonsrn-ad-networks" />

<Accordion title="Jaringan iklan non-SRN">

Tautan atribusi jaringan iklan mencatat interaksi pengguna dan selanjutnya digunakan untuk mengatribusikan interaksi yang menjadi penginstalan sebenarnya.

**Untuk memigrasi kampanye jaringan iklan non-SRN** :

1. <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner">Aktifkan</Anchor> jaringan iklan yang relevan di AppsFlyer.
2. <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#attribution-link-tab">Buat tautan atribusi AppsFlyer</Anchor> untuk setiap jaringan iklan.
3. Ganti tautan yang ada di setiap kampanye Anda dengan tautan atribusi AppsFlyer.

</Accordion>

<div id="owned-media" />

<Accordion title="Media yang Dimiliki Sendiri">

Media yang dimiliki mengacu pada tautan atribusi yang Anda gunakan di:

* Berbagi konten
* Web-to-App
* Email
* SMS
* Postingan media sosial
* Blog
* Komunitas internet (Quora, dll.)
* dan lebih ...

Untuk kampanye ini, AppsFlyer menggunakan <Anchor target="_blank" href="/marketers/id/docs/onelink-guide">tautan khusus OneLink</Anchor> . Tautan khusus OneLink mengarahkan pengguna berdasarkan perangkat mereka ke app store yang benar, langsung ke aplikasi, atau ke URL web / laman arahan.

**Untuk mengubah tautan Anda untuk vendor lain menjadi AppsFlyer OneLinks:**

* Hubungi CSM Anda, yang akan membantu Anda dengan migrasi massal dari semua tautan Anda.

</Accordion>

<div id="skan" />

<Accordion title="SKAN">

Untuk atribusi SKAdNetwork (SKAN), Anda hanya dapat meminta satu SDK yang memperbarui nilai konversi. Jika tidak, data SKAN menjadi tidak berarti. Oleh karena itu, pastikan setelah migrasi, hanya AppsFlyer SDK yang memperbarui nilai konversi SKAN.

<Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio">Pelajari tentang mengatur nilai konversi SKAN di AppsFlyer.</Anchor>

</Accordion>

<div id="data-report-setup" />

### Penyiapan laporan data

<div id="adapt-and-map-report-structures" />

<Accordion title="Adaptasi dan petakan struktur laporan">

Sebelum migrasi, sistem Anda menyimpan data atribusi dari vendor Anda saat ini sesuai dengan struktur pelaporan, bidang, dan parameter yang telah Anda atur. Agar AppsFlyer dapat melaporkan data dengan benar, Anda harus menyesuaikan dan memetakan struktur laporan Anda saat ini ke struktur laporan, bidang, dan parameter AppsFlyer.

**Untuk mengadaptasi/memetakan struktur laporan Anda:**

* Hubungi CSM AppsFlyer Anda untuk mendapatkan bantuan dalam mengadaptasi/memigrasi struktur data laporan Anda dengan cepat dari Adjust, Branch/Tune, atau Kochava ke AppsFlyer.

</Accordion>

<div id="prepare-report-methods" />

<Accordion title="Siapkan metode laporan">

Anda bisa mendapatkan <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-apis">data laporan lengkap</Anchor> dan <Anchor target="_blank" href="/marketers/id/docs/analytics-and-aggregate-reporting-apis">gabungan</Anchor>  dari AppsFlyer menggunakan beberapa metode. Biasakan diri Anda dengan metode dan atur metode yang relevan untuk Anda.

Metode pelaporan meliputi:

* Ekspor CSV
* Push API
* Pull API
* Data Locker

</Accordion>

<div data-zendesk-anchors="01H8EDSTP8N4GZJQ5J609C3DHM=overview 01H8EDZ8C5F06701DKT71D8T5P=catatan tasks=tugas 01H8EDSTP8YGDZBPEY1976JP8C=tugas scope-of-work=lingkup-kerja 01H8EDSTP8HGCVHYX49GQQEHBB=lingkup-kerja sdk-integration=integrasi-sdk h_01F0RDXJ4F34DDKRFV5G6WZQX0=integrasi-sdk 01H8EDSTP97C85X2E9EKBSVFQJ=sdk-integration::c763138b device-migration%E2%80%94optional=migrasi-perangkat---opsional h_01F0RDXVSQ13R9Q2KT7PK1KSCQ=migrasi-perangkat---opsional 01H8EDSTP9NDF6611MVEMWQSMZ=about-device-migration 01H8EDSTP93QJA4XZB6TDWWH1V=contoh 01H8EDSTP9M2MDMGZ8QBQGPM6S=how-to-migrate-devices h_01F0RPWKQ4B0T1TXRGPVTYPPFB=attributed-migration attributed-device-migration-csv-structure=struktur-csv-migrasi-perangkat-yang-teratribusi 01H8EDSTP9HABKEZJXMB84CDDE=struktur-csv-migrasi-perangkat-yang-teratribusi h_01F0RPX3SJ391M8SPNNN50DDA8=nonattributed-migration nonattributed-device-migration-csv-file-structure=struktur-file-csv-migrasi-perangkat-yang-tidak-diatribusikan 01H8EDSTP9AFDMQS6BPQJY19ZH=struktur-file-csv-migrasi-perangkat-yang-tidak-diatribusikan campaign-migration=migrasi-kampanye h_01F0RDY9WPSBZVP3B7XN3ZEJKK=migrasi-kampanye 01H8EDSTP94KSE1J4J5B7HX96Z=srns 01H8EDSTP9ZGMHSM44BWGF1FJN=catatan-1 01H8EDSTP981XVWVM2NE0A45RM=nonsrn-ad-networks 01H8EDSTP9XNJA80Z5XR7WR9QN=owned-media 01H8EDSTP9Q8JAPNXSQWSHSK32=skan data-report-setup=penyiapan-laporan-data h_01F0RDYKYHAEZ65GZBZ3MWTB5Z=penyiapan-laporan-data 01H8EDSTP91E934EDXTPXW2ARJ=adapt-and-map-report-structures 01H8EDSTPAF8H5ESHDVK42M0RB=prepare-report-methods" />
