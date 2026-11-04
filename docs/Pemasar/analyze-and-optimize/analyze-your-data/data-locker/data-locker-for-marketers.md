---
title: Data Locker untuk pemasar
metadata:
  keywords:
    - Reports
    - Data Locker
    - Advertisers
    - Raw Data
    - Developers
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2019-02-03T12:20:08Z'
  edited_at: '2023-11-20T08:41:06Z'
  id: 360000877538
  locale: id
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/id/articles/360000877538
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Sekilas:** Data Locker mengirimkan data laporan Anda ke penyimpanan cloud untuk dimuat di sistem BI Anda. Anda dapat memilih di antara berbagai tujuan penyimpanan: Bucket milik AppsFlyer di AWS, atau penyimpanan yang Anda miliki di AWS, GCS, Yandex, BigQuery, dan Snowflake. Data Locker mendukung [banyak tujuan](/docs/data-locker-for-marketers#multipleconnections-principles-more-than-one-destination). Itu berarti Anda dapat mengirim semua data ke beberapa tujuan, memisahkan data berdasarkan tujuan, atau kombinasi keduanya.

## Data Locker

![6133DataLockerForAdvertisers.png](https://files.readme.io/820fee89515ccdcdfac2043bcb9fde722ddc8ec852a140ec250378c581d9c375-32966274469649.png)

Di Data Locker, pilih aplikasi, sumber media, event, dan laporan Anda untuk disertakan dalam data yang dikirimkan AppsFlyer ke opsi penyimpanan cloud yang Anda pilih. Kemudian, muat data secara terprogram dari penyimpanan ke dalam sistem Anda.

<div id="data-locker-features" />

<Accordion title="Data Locker—fitur">

| Fitur | Deskripsi |
| --- | --- |
| [Opsi penyimpanan (cloud)](/docs/data-locker-for-marketers#storage-options) | Data Locker dapat mengirim data Anda ke salah satu penyedia layanan cloud berikut:<ul><li>Penyimpanan milik AppsFlyer di AWS</li><li><Anchor target="_blank" href="/marketers/id/docs/data-locker-cloud-service-setup">Penyimpanan milik Anda</Anchor> di:<ul><li>AWS</li><li>GCS</li><li>[Beta] Azure Blob</li><li>[Beta] Yandex</li><li>BigQuery</li><li>Snowflake</li></ul></li></ul>Anda dapat mengatur lebih dari 1 tujuan di Data Locker. Ini berarti Anda dapat mengirim semua atau sebagian data Anda ke beberapa tujuan.<br /><br />**Contoh**<ul><li>Pisahkan data menurut jenis laporan. Kirim data lengkap ke GCS dan data gabungan ke Snowflake.</li><li>Pisahkan data menurut aplikasi dan kirim data per grup aplikasi ke bucket yang berbeda.</li></ul> |
| Multi-aplikasi | Streaming data dari 1, lebih, atau semua aplikasi di akun Anda. Saat Anda menambahkan aplikasi ke akun, aplikasi tersebut dapat ditambahkan secara otomatis. |
| Jendela ketersediaan | 14 hari |
| [Pemisahan data](/docs/data-locker-for-marketers#app-segregation) | Opsi pemisahan data yang tersedia (relevan untuk penyimpanan cloud bucket):<ul><li>[Default] **Terpadu:** Gabungan data dari semua aplikasi. Bidang ID aplikasi tingkat baris digunakan untuk mengidentifikasi aplikasi dalam file data.</li><li>**Dipisahkan berdasarkan aplikasi:** Data dari masing-masing aplikasi ada di folder terpisah. Nama folder terdiri dari ID aplikasi.</li></ul> |
| Opsi format data | <ul><li>Untuk penyimpanan cloud bucket:<ul><li>CSV</li><li>Parquet</li><li><Anchor target="_blank" href="/marketers/id/docs/adobe-experience-platform-aep-integration-with-appsflyer-data-locker">Adobe</Anchor></li></ul></li><li>Gudang data</li></ul> |
| Kesegaran data | Kesegaran data tergantung dari jenis laporan<ul><li>**Setiap Jam:** Data yang dihasilkan terus menerus; misalnya, data instal dan in-app event ditulis dalam beberapa jam setelah event tiba di AppsFlyer.</li><li>**Harian:** Laporan seperti uninstall, dibuat setiap hari dan siap pada hari berikutnya.</li><li>**Versioned (Berversi):** Jika laporan yang sama dibuat beberapa kali untuk periode waktu yang sama, mekanisme pembuatan versi akan diterapkan.</li></ul> |

</Accordion>

<div id="reports-available-via-data-locker" />

<Accordion title="Laporan tersedia melalui Data Locker">

<Anchor target="_blank" href="/marketers/id/docs/data-locker-advertiser-reports">Laporan tersedia melalui Data Locker</Anchor>

</Accordion>

<div id="data-storage-architecture" />

## Arsitektur penyimpanan data

<div id="zd-overview" />

<div id="overview" />

<Accordion title="Overview">

Struktur data Anda dalam penyimpanan bergantung pada apakah data dikirim ke penyimpanan cloud atau gudang data. Struktur folder yang dijelaskan di sini berlaku untuk penyimpanan (bukcet). Dalam kasus penyimpanan gudang data,   pertimbangkan bahwa referensi ke folder berlaku untuk tampilan. Lihat <Anchor target="_blank" href="/partners/id/docs/data-locker-for-partners">Snowflake</Anchor>.

Data ditulis ke opsi penyimpanan yang Anda pilih. Dalam hal penyimpanan cloud, penyimpanan dimiliki oleh AppsFlyer di AWS atau dimiliki oleh Anda di AWS, GCS, atau Yandex. Anda dapat mengganti opsi penyimpanan kapan saja atau mengirim sebagian atau semua data Anda ke beberapa opsi penyimpanan.

Data di penyimpanan cloud bucket diatur dalam struktur folder hierarki, menurut jenis laporan, tanggal, dan waktu. Gambar berikut berisi contoh struktur ini:

![DLFolderOVerview.png](https://files.readme.io/78f360ec1df72253e5b2cd725f3eecf4e17548a7f06b544a94a75a2c319d77a0-18107910420369.png)

Data laporan tertentu ada di dalam folder hour (h) yang terkait dengan laporan tersebut:

* Jumlah folder jam bergantung pada keaktualan data laporan (per jam, harian, atau versioned (berversi)).
* Data disediakan dalam file terkompresi Snappy atau GZIP, atau file tidak terkompresi dengan format Parquet atau CSV.
* File data terdiri dari kolom (bidang).
* Struktur skema (bidang) <Anchor target="_blank" href="/marketers/id/docs/data-locker-advertiser-reports#user-journey">laporan perjalanan pengguna</Anchor> identik satu sama lain dan bergantung pada bidang yang dipilih oleh Anda. Laporan lain masing-masing memiliki bidang eksplisitnya sendiri, laporan tanpa skema AKA. Lihat <Anchor target="_blank" href="/marketers/id/docs/data-locker-advertiser-reports#user-journey">Laporan pemasang iklan Data Locker</Anchor> untuk laporan yang tersedia dan tautan ke spesifikasi laporan.

</Accordion>

<div id="folder-structure" />

<Accordion title="Struktur folder">

| Folder | Deskripsi |
| --- | --- |
| ID Berlangganan | <Image alt="DataLockerFolders.png" src="https://files.readme.io/0cda5728e48dab772878cad13ed3b81168f152e1bf01604ac45b700af804dd16-32966264039185.png" width="439px" /><ul><li>Folder tingkat atas di dalam bucket bergantung pada pemilik dan penyedia penyimpanan. Secara umum, folder tingkat atas adalah ID Langganan Anda, tetapi dalam beberapa kasus, misalnya, jika Anda menggunakan Cyberduck, ID diatur di bookmark dan tidak ditampilkan dalam struktur folder.</li><li>Folder *data-locker-hourly* berisi topik laporan. Folder di atas level ini bergantung pada kepemilikan bucket dan penyedia layanan cloud.</li></ul>**Contoh struktur folder berdasarkan pemilik bucket dan penyedia layanan cloud**<ul><li>**AppsFlyer bucket**: &lt;af-ext-reports>/&lt;unique\_identifier>/&lt;data-locker-hourly></li><li>**Bucket AWS Anda** : *&lt;af-datalocker-your bucket prefix>/&lt;generated-home-folder>&lt;subscription-id>*</li><li>**Bucket GCS Anda:** &lt;nama bucket Anda>/&lt;generated-home-folder>/&lt;subscription-id></li></ul> |
| Topik (t) | Jenis laporan berkaitan dengan perihal laporan. |
| Tanggal (dt) | Ini adalah tanggal data terkait. Dalam kasus data lengkap, itu berarti tanggal terjadinya event. Dalam hal data agregat, tanggal pelaporan itu sendiri. |
| Waktu (h/jam atau versi) | Folder tanggal dibagi menjadi folder **per jam (h)** atau **versi** tergantung pada jenis laporan.<br /><br />**<span id="hourly-folders"></span>Folder per jam**<br /><br />Folder h berkaitan dengan waktu data diterima oleh AppsFlyer. Misalnya, event penginstalan diterima antara pukul 14:00-15:00 UTC ditulis ke file h=14. Perhatikan! Ada jeda sekitar 1-3 jam antara waktu data tiba di AppsFlyer hingga folder h ditulis ke Data Locker. Misalnya, folder h=14 ditulis 1 jam kemudian pada pukul 15:00 UTC.<br /><br />**Karakteristik folder per jam**:<ul><li>Ada folder 24 h (jam) bernomor 0–23. Misalnya, h=0, h=1, dan seterusnya.</li><li>Folder telat, h=late, berisi event hari sebelumnya yang tiba setelah tengah malam. Artinya event yang tiba pukul 00:00–02:00 UTC pada hari berikutnya. Misalnya, jika pengguna menginstal aplikasi pada hari Senin 08:00 UTC dan event tiba pada hari Selasa pukul 01:00 UTC, event tersebut ditulis ke folder telat hari Senin.</li><li>Data yang tiba setelah pukul 02:00 UTC ditulis ke folder tanggal dan waktu kedatangan aktual.</li><li>Pastikan bahwa data di folder h=late (telat) digunakan. Data ini tidak ada di folder lainnya.</li><li>\_temporary folder: Pada beberapa kasus, kami membuat folder sementara di dalam folder h. Abaikan folder dan sub-folder sementara. Misalnya: /t=impressions/dt=2021-04-11/h=18/**\_temporary**.</li><li>**Catatan**:<ul><li>Laporan data lengkap yang memiliki kesegaran data harian disimpan di folder h=23. Laporan uninstall biasanya ada di folder h=2 tapi bisa di folder mana saja.</li><li>Laporan Kohort dan Inkrementalitas disimpan langsung di folder dt.</li><li>Laporan versioned (berversi) mematuhi konvensi berbeda yang dijelaskan di bagian ini.</li></ul></li></ul>**Pertimbangan laporan per jam untuk aplikasi yang tidak menggunakan waktu UTC.**<br /><br />Untuk memastikan bahwa Anda mendapatkan semua data untuk hari kalender tertentu, Anda harus menggunakan folder sesuai dengan hari yang ditentukan oleh zona waktu aplikasi seperti yang dirinci:<ul><li>**Zona waktu belahan bumi timur** : Untuk mendapatkan semua data dari tanggal kalender tertentu, Anda harus menggunakan folder menurut waktu dan tanggal UTC. Contoh: Zona waktu aplikasi Anda adalah UTC+10 (Sydney, Australia). Untuk mendapatkan semua data per jam yang terkait dengan selasa (Sydney), Anda harus menggunakan folder berikut: Senin h=14–23 dan akhir, Selasa h=0–13 dan 14-15 Mengapa Anda harus memakai Selasa h=14-15? Beberapa data bisa datang terlambat. Jadi folder h=14–15 dapat berisi event yang datang terlambat. Anda harus memfilter event\_time untuk menyelaraskan dengan hari kalender aplikasi relatif terhadap UTC.</li><li>**Zona waktu belahan bumi barat** : Untuk mendapatkan semua data dari tanggal kalender tertentu, Anda harus menggunakan folder menurut waktu dan tanggal UTC. Contoh: Zona waktu aplikasi Anda adalah UTC-7 (Los Angeles). Untuk mendapatkan semua data per jam yang terkait dengan hari Selasa (Los Angeles), Anda harus menggunakan folder berikut: Selasa h=7–23 dan akhir, Rabu h=0–6 dan 7-8 Mengapa Anda harus menggunakan hari Rabu h=7-8? Ada data bisa datang terlambat. Jadi folder h=7–8 dapat berisi event yang datang terlambat. Anda harus memfilter event\_time untuk menyelaraskan dengan hari kalender aplikasi relatif terhadap UTC.</li></ul>**<span id="version-folders"></span>folder versi**<br /><br />Beberapa laporan memiliki opsi versioned (berversi). Ini berarti bahwa data terbaru untuk hari tertentu diberikan beberapa kali. Karena data dapat terus diperbarui karena data yang datang terlambat atau data yang lebih akurat, laporan yang sama memiliki beberapa versi di mana versi terbaru adalah yang paling akurat.<br /><br />Laporan untuk hari tertentu terdapat dalam folder versi hari itu. Setiap versi terdapat dalam folder terpisah yang namanya diatur menggunakan stempel waktu Epoch yang mengidentifikasi laporan secara unik.<br /><br />Proses impor data Anda harus mempertimbangkan bahwa data dapat ditulis secara surut. Misalnya, pada 14 Januari, data dapat ditulis ke folder 1 Januari. Jika bucket adalah milik Anda, pertimbangkan untuk menggunakan pemberitahuan layanan cloud untuk memicu proses impor Anda (<Anchor target="_blank" href="https://docs.aws.amazon.com/AmazonS3/latest/userguide/NotificationHowTo.html">AWS</Anchor> \| <Anchor target="_blank" href="https://cloud.google.com/storage/docs/pubsub-notifications">GCS</Anchor>) |

</Accordion>

<div id="app-segregation" />

<Accordion title="Pemisahan aplikasi">

Untuk penyimpanan cloud bucket, data disediakan dalam file data terpadu yang berisi data semua aplikasi yang dipilih atau dipisahkan ke dalam folder berdasarkan aplikasi. Pemisahan ada di dalam folder h seperti yang dijelaskan dalam tabel berikut. 

| Jenis pemisahan | Deskripsi |
| --- | --- |
| [Default] Terpadu | Data untuk semua aplikasi tersedia di file data terpadu. Saat menggunakan data ini, gunakan bidang app\_id tingkat baris untuk membedakan diantara aplikasi.<br /><br />**Contoh file data ada di folder h=2**<br /><br />![UnifiedByApp.png](https://files.readme.io/dbc39c2ce99c1ff607fd553b9c9034e55728c102f31fd18a501cc00910267b28-18107874522513.png)<br /><br />Konvensi penamaan file data adalah unique\_id.gz.<ul><li>Proses pemuatan data Anda harus:<ul><li>Memuat data setelah \_SUCCESS flag disetel.</li><li>Memuat semua file di folder yang memiliki ekstensi *.gz*. Jangan melakukan proses impor Anda menggunakan logika penomoran bagian.</li></ul></li></ul> |
| Dipisahkan berdasarkan aplikasi | Folder tersebut berisi sub-folder per aplikasi. File data untuk aplikasi tertentu ada di dalam folder aplikasi. Pada gambar berikut, folder h=19 berisi folder aplikasi. Setiap folder aplikasi berisi file data terkait. Perhatikan! File data tidak berisi app\_id Anda harus menentukan app\_id menggunakan folder.<br /><br />![DLSegregateByApp.png](https://files.readme.io/90639507da82f7dafacfa5bfb67fa96a8277747cd0eee226d74498bf5ff16869-32966264040977.png)<br /><br />Di setiap folder aplikasi, konvensi penamaannya adalah unique\_id.gz:<ul><li>Proses pemuatan data Anda harus:<ul><li>Memuat data setelah \_SUCCESS flag disetel.</li><li>Memuat semua file di folder yang memiliki ekstensi *.gz*. Jangan melakukan proses impor Anda menggunakan logika penomoran bagian.</li></ul></li></ul>Batasan: Opsi ini tidak tersedia untuk laporan Atribusi Berbasis Orang (Peopled-Based Attribution/PBA). |

</Accordion>

<div id="data-files" />

<Accordion title="File data">

File data bergantung pada jenis pemisahan

<table><thead><tr><th>Konten</th><th colspan="2">Detail</th></tr></thead><tbody><tr><td>Flag penyelesaian</td><td colspan="2"><p>Flag (penyelesaian) file terakhir ditetapkan saat semua data untuk folder h tertentu telah ditulis. </p><ul><li><p>Jangan membaca data dalam folder sebelum memastikan bahwa flag _SUCCESS ada.</p></li><li><p>Flag _SUCCESS diatur bahkan dalam hal tidak ada data yang ditulis ke folder tertentu dan folder tersebut kosong. </p></li><li>Perhatikan! Dalam opsi pemisahan berdasarkan aplikasi, flag disetel di folder h dan bukan folder aplikasi individual. Lihat gambar di bagian sebelumnya. </li></ul></td></tr><tr><td>Jenis file</td><td colspan="2"><ul><li>Data disediakan dalam file terkompresi Snappy atau GZIP, atau file tidak terkompresi dengan format Parquet atau CSV.</li><li>Setelah mengekstrak file, file data dalam format Parquet atau CSV sesuai dengan pengaturan Anda.</li></ul></td></tr><tr><td>Urutan kolom (file CSV) </td><td colspan="2"><p>Dalam hal file CSV, urutan kolom dalam laporan selalu sama. Saat kita menambahkan kolom baru, kolom ini ditambahkan di sebelah kanan dari kolom yang ada. </p><p>Dalam hal ini: </p><ul><li>Struktur kolom laporan perjalanan pengguna identik. Ini berarti Anda dapat memiliki prosedur pemuatan data yang serupa untuk jenis laporan yang berbeda-beda. Anda memilih bidang yang ada dalam laporan. Penjelasan bidang diperinci di <a href="./raw-data-field-dictionary" target="_blank">kamus data lengkap</a>. </li><li>Laporan yang memiliki notasi FF di bagian ketersediaan laporan tidak mengikuti struktur kolom umum. </li></ul></td></tr><tr><td>Pertimbangan dalam pengisian bidang</td><td colspan="2"><p><strong>Bidang kosong:</strong> Beberapa bidang diisi dengan <em>null</em> atau kosong. Artinya bahwa dalam konteks laporan tertentu tidak ada data untuk dilaporkan. Biasanya <em>null</em> berarti bahwa bidang ini tidak diisi dalam konteks laporan dan jenis aplikasi tertentu. Blank (Kosong) "" artinya bidang ini relevan dengan konteksnya tetapi tidak ada data yang ditemukan untuk diisi. </p><p>Dalam hal sumber media terbatas, konten bidang terbatas disetel ke null. </p><p>Secara keseluruhan, anggap null dan kosong sebagai satu kesatuan dan hal yang sama; tidak ada data yang tersedia. </p><p><strong>Zona Waktu dan Mata Uang</strong></p><p>Pengaturan zona waktu dan mata uang khusus aplikasi tidak memengaruhi data yang ditulis ke Data Locker. Berlaku hak berikut: </p><ul><li> <strong>Zona waktu</strong>: Data tanggal dan jam dalam UTC.</li><li> <strong>Mata uang</strong> : Bidang event_revenue_usd adalah dalam USD.</li></ul><p><strong>Nilai dengan koma</strong>: Koma ini berada di antara tanda petik dua `"`, misalnya, <code>`"iPhone6,1"`</code>.</p></td></tr></tbody></table>

</Accordion>

<div id="storage-options" />

<Accordion title="Opsi penyimpanan">

<div id="caution" />

> ❗️ **Perhatian!**
>
> Jika Anda menggunakan opsi penyimpanan milik pemasar:
>
> * Pastikan Anda mematuhi peraturan data privasi seperti GDPR dan kebijakan penyimpanan data jaringan iklan/SRN.
> * Jangan gunakan solusi penyimpanan milik pemasar untuk mengirim data ke pihak ketiga.

* Data ditulis ke pemilik penyimpanan pilihan Anda sebagai berikut:
  * Penyimpanan AppsFlyer
  * Penyimpanan pelanggan—AWS, GCS, Azure, Yandex, BigQuery, dan Snowflake
* Anda dapat mengubah opsi penyimpanan kapan saja.
* Jika Anda mengubah penyimpanan, terjadi hal berikut:
  * Kami mulai menulis data ke penyimpanan yang baru dipilih dalam waktu 1 jam.
  * Kami terus menulis ke bucket yang ada selama masa transisi 7 hari. Waktu kedaluwarsa periode transisi ditampilkan di antarmuka pengguna. Gunakan masa transisi untuk memperbarui proses pemuatan data Anda.  Anda dapat memulai kembali periode transisi atau kembali ke bucket AppsFlyer jika diperlukan.
  * **Mengubah penyimpanan** : Anda dapat bermigrasi dari satu opsi penyimpanan ke opsi penyimpanan lainnya dengan menggunakan opsi multi-penyimpanan dan mengirim data ke beberapa tujuan secara bersamaan. Setelah Anda menyelesaikan migrasi dan pengujian, hapus opsi penyimpanan yang tidak lagi Anda perlukan.

|  | Penyimpanan milik AppsFlyer (AWS) | Penyimpanan milik pemasar (GCS, AWS, Azure, Yandex, BigQuery, Snowflake) |
| --- | --- | --- |
| Nama bucket | Ditetapkan oleh AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/id/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor>: Tidak ada batasan</li><li><Anchor target="_blank" href="/marketers/id/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>: Diatur oleh Anda. Harus memiliki awalan af-.</li></ul>Misalnya: `af-datalocker-your-bucket-name` |
| Kepemilikan penyimpanan | AppsFlyer | Pemasar |
| Platform penyimpanan | AWS | AWS, GCS, Azure, Yandex, BigQuery, Snowflake |
| Kredensial agar Anda dapat mengakses data | Tersedia di antarmuka pengguna Data Locker untuk admin akun AppsFlyer Anda | Tidak dikenal oleh AppsFlyer. Gunakan kredensial yang disediakan oleh penyedia cloud. |
| Retensi data | Data dihapus setelah 14 hari | Tanggung jawab pemasar |
| Permintaan penghapusan data | Tanggung jawab AppsFlyer | Tanggung jawab pemasar |
| Keamanan | AppsFlyer mengontrol penyimpanan. Pelanggan memiliki akses baca. | Pemasar mengontrol penyimpanan.<ul><li>**AWS**: AppsFlyer memerlukan izin GetObject, ListBucket, DeleteObject, PutObject ke bucket. Bucket harus ditujukan khusus untuk penggunaan AppsFlyer. Jangan gunakan bucket untuk tujuan lain.</li><li>**GCS**: Lihat <Anchor target="_blank" href="/marketers/id/docs/data-locker-cloud-service-setup">Artikel konfigurasi GCS</Anchor>.</li></ul> |
| Kapasitas penyimpanan | Dikelola oleh AppsFlyer | Dikelola oleh pemasar |
| Akses kontrol menggunakan titik akhir VPC dengan kebijakan bucket | Tidak Berlaku | [Opsional] Di AWS, jika Anda menerapkan keamanan titik akhir pada tingkat bucket, Anda harus mengizinkan server AppsFlyer. |

<div id="notice-to-security-officers-in-the-case-of-customer-controlled-storage" />

#### **Pemberitahuan kepada petugas keamanan dalam hal penyimpanan yang dikontrol pelanggan**

Pertimbangkan:

* Bucket atau tujuan khusus untuk penggunaan AppsFlyer. Tidak ada entitas lain yang menulis ke tujuan tertentu.
* Anda dapat menghapus data di tempat tujuan 25 jam setelah kami menulis data.
* Data yang ditulis ke tujuan adalah salinan data yang sudah ada di server kami. Data tetap berada di server kami sesuai dengan kebijakan penyimpanan data kami.
* Untuk alasan teknis, terkadang kami menghapus dan menulis ulang data. Untuk alasan ini, kami memerlukan izin hapus dan daftar. Tidak ada izin yang merupakan risiko keamanan bagi Anda. Dalam hal daftar, kami adalah satu-satunya entitas yang menulis ke bucket. Dalam hal penghapusan, kami dapat membuat ulang data.
* Untuk informasi tambahan, Anda dapat menghubungi tim keamanan kami melalui [hello@appsflyer.com](mailto:hello@appsflyer.com) atau CSM Anda.

</Accordion>

<div id="multipleconnections-principles-more-than-one-destination" />

<Accordion title="Prinsip multi-koneksi (lebih dari satu tujuan)">

Di Data Locker, Anda dapat mengirim sebagian atau semua data Anda ke 2 tujuan (ditentukan di pengaturan koneksi). Misalnya, Anda dapat mengirim data Aplikasi A ke AWS, dan data Aplikasi B ke GCS.

Setiap koneksi terdiri dari satu set lengkap pengaturan Data Locker, termasuk tujuan. Pengaturan koneksi tidak tergantung satu sama lain.

Dalam mengelola koneksi Anda, pertimbangkan:

* Dalam pengaturan Data Locker, koneksi ditampilkan di tab. Setiap koneksi memiliki tab pengaturan sendiri dari mana Anda dapat mengelola koneksi. Ikon setiap tab mewakili jenis penyimpanan.
* Untuk melihat detail koneksi, menggandakan koneksi, atau menghapus koneksi, klik (options).

</Accordion>

## Prosedur

<div id="set-up-data-locker" />

<Accordion title="Pengaturan Data Locker">

Gunakan prosedur ini untuk mengatur Data Locker. Perubahan pada pengaturan Data Locker membutuhkan waktu 3 jam untuk diterapkan.

**Prasyarat**

**Untuk mengatur penyimpanan milik pemasar:**

Jika Anda mengatur Data Locker menggunakan layanan penyimpanan cloud milik pemasar, selesaikan satu atau beberapa prosedur berikut sekarang.

* Mengatur:
  * Bucket<Anchor target="_blank" href="/marketers/id/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>
  * Bucket<Anchor target="_blank" href="/marketers/id/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor>
  * [Beta] <Anchor target="_blank" href="/marketers/id/docs/data-locker-cloud-service-setup#beta--azure-storage">Azure</Anchor> Blob
  * [Beta] bucket <Anchor target="_blank" href="/marketers/id/docs/data-locker-cloud-service-setup#yandex">Yandex</Anchor>
  * Gudang data<Anchor target="_blank" href="/marketers/id/docs/data-locker-cloud-service-setup#bigquery">BigQuery</Anchor>
  * Gudang <Anchor target="_blank" href="/marketers/id/docs/data-locker-cloud-service-setup#snowflake">Snowflake</Anchor>

**Catatan**! Jika Anda tidak memiliki langganan Data Locker dan mengakses analitik Cohorts atau data SKAN, Anda tetap harus menyelesaikan prosedur layanan penyimpanan cloud milik pemasar.

**![AppsFlyerAdmin_us-en.png](https://support.appsflyer.com/hc/article_attachments/16581340456849) Untuk mengatur Data Locker:**

1. Admin perlu melakukan pengaturan.
2. Di AppsFlyer, buka **Integrasi** > **Data Locker**.
3. [Opsional] Jika Anda sudah memiliki tujuan Data Locker aktif dan ingin menambahkan tujuan, klik **Tambahkan koneksi.** Beri nama koneksi Anda.
4. **Pilih tujuan data layanan cloud** . Lakukan salah satu dari hal berikut:  
   * Pilih **bucket AWS AppsFlyer** (opsi hanya tersedia untuk pelanggan Data Locker). Klik **Simpan** dan lanjutkan ke langkah 5.
   * Pilih **S3**.
     1. Masukkan nama bucket AWS S3 Anda. Awalan`af-` adalah wajib, dan harus dimasukkan secara manual.
     2. Klik **Tes koneksi**.
     3. Pastikan bahwa tidak ada pesan kesalahan yang menunjukkan bahwa bucket path tidak valid.
     4. Pilih apakah **Buat koneksi ini kompatibel dengan Adobe Experience Platform**. Jika dipilih, klik **Simpan** dan lanjutkan ke Langkah 6.
     5. Klik **Save**.
   * Pilih **GCS**.
     1. Masukkan **nama bucket GCS** Anda .
     2. Klik **Tes koneksi**.
     3. Pastikan bahwa tidak ada pesan kesalahan yang menunjukkan bahwa bucket path tidak valid.
     4. Pilih apakah **Buat koneksi ini kompatibel dengan Adobe Experience Platform**. Jika dipilih, klik **Simpan** dan lanjutkan ke Langkah 6.
     5. Klik **Save**.
   * [Beta] Pilih **Azure**.
     1. Masukkan **Nama koneksi** Anda, **Nama akun penyimpanan**, dan **Kunci**.
     2. Pastikan bahwa tidak ada pesan kesalahan yang menunjukkan bahwa bucket path tidak valid.
     3. Pilih apakah **Buat koneksi ini kompatibel dengan Adobe Experience Platform**. Jika dipilih, klik **Simpan** dan lanjutkan ke Langkah 6.
     4. Klik **Save**.
   * [Beta] Pilih **Yandex**.
     1. Masukkan **nama Bucket**Anda, **Kunci akses**, dan **Kunci rahasia**.
     2. Pastikan bahwa tidak ada pesan kesalahan yang menunjukkan bahwa bucket path tidak valid.
     3. Pilih apakah **Buat koneksi ini kompatibel dengan Adobe Experience Platform**. Jika dipilih, klik **Simpan** dan lanjutkan ke Langkah 6.
     4. Klik **Save**.
   * Pilih **BigQuery**.
     1. Masukkan ID project BigQuery dan nama set data Anda.
     2. Klik **Tes koneksi**.
     3. Pastikan bahwa tidak ada pesan kesalahan yang menunjukkan bahwa bucket path tidak valid.
     4. Klik **Simpan** dan lanjutkan ke Langkah 6.
   * Pilih **Snowflake**.
     1. Masukkan wilayah Snowflake dan ID akun Anda.
     2. Klik **Tes koneksi**.
     3. Pastikan bahwa tidak ada pesan kesalahan yang menunjukkan bahwa bucket path tidak valid.
     4. Klik **Simpan** dan lanjutkan ke Langkah 6.
5. Lengkapi bagian **setelan Data**:
   1. Pilih format file yang Anda inginkan:
      * [Default] **Parquet**.
      * **CSV**
   2. Pilih jenis kompresi file yang Anda inginkan:
      * Snappy (hanya tersedia untuk file Parket)
      * GZIP
      * Tidak terkompresi
   3. Pilih baris maksimal yang Anda inginkan dalam file Anda: 10k, 25k, 50, 100k, 200k, atau 500k. Lebih banyak baris dalam file berarti lebih sedikit file tetapi ukuran file lebih besar.
   4. Pilih struktur folder ([pemisahan data](/docs/data-locker-for-marketers#app-segregation)):
      * [Default] **Terpadu**
      * **Dipisahkan berdasarkan aplikasi**
6. Lengkapi bagian **konten Data Locker** :
7. Pilih satu atau beberapa **Aplikasi** untuk disertakan dalam laporan. Pilih **semua** untuk menyertakan aplikasi yang ditambahkan di masa mendatang secara otomatis.
8. Klik **Terapkan** .
9. [Opsional] Pilih satu atau beberapa **Sumber Media** untuk disertakan dalam laporan.
   * Default=Semua. Ini artinya sumber media yang ditambahkan di masa mendatang ditambahkan secara otomatis.
10. Klik **Terapkan** .
11. [Opsional] Pilih **Bidang** untuk disertakan dalam laporan. **Catatan**: Terkadang kami menyediakan kolom tambahan. Pertimbangkan hal ini dalam proses impor data Anda.
12. Klik **Terapkan** .
13. Pilih [jenis laporan](/docs/data-locker-for-marketers#data-locker). Anda harus memilih minimal 1.
14. [Opsional] Untuk laporan **In-app event** , pilih in-app event yang akan disertakan. Jika Anda memiliki lebih dari 100 jenis in-app event, Anda tidak dapat menelusurinya. Masukkan nama mereka dengan tepat untuk memilihnya.
    * Default=Semua. Ini artinya in-app event yang ditambahkan di masa mendatang ditambahkan secara otomatis.
15. Klik **Terapkan** .
16. Klik **Simpan koneksi**. Terjadi salah satu yang berikut:  
    * Jika Anda memilih **bucket AppsFlyer AWS**:
      * Bucket AWS khusus dibuat. Kredensial bucket ditampilkan.
      * Bucket dapat diakses menggunakan kredensial. Kredensial memberi Anda akses hanya-baca ke bucket.
    * Jika Anda memilih salah satu layanan penyimpanan cloud Anda: Data akan ditulis ke layanan Anda dalam waktu 3 jam.

</Accordion>

<div id="reset-credentials" />

<Accordion title="Reset kredensial">

Admin dapat mereset kredensial bucket AppsFlyer kapan saja. Perhatikan! Jika Anda mereset kredensial, Anda harus memperbarui skrip impor data dengan kredensial yang diperbarui.

**![AppsFlyerAdmin_us-en.png](https://support.appsflyer.com/hc/article_attachments/16581340456849) Untuk mereset kredensial penyimpanan yang dimiliki AppsFlyer:**

1. Di AppsFlyer, buka **Integrasi** > **Data Locker**.
2. Pilih tujuan yang dimiliki AppsFlyer.
3. Di bagian Credential (Kredensial), klik **Reset credentials (Reset kredensial).**  
   Muncul jendela konfirmasi.
4. Klik **Reset**.
5. Tunggu (sekitar 20 detik) hingga muncul pesan **Credentials successfully reset (Kredensial berhasil direset)**.  
   Tersedia pembaruan kredensial.

</Accordion>

<div id="additional-information" />

## Informasi Tambahan

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan Batasan">

| **Sifat** | Catatan |
| --- | --- |
| Jaringan iklan | Tidak untuk digunakan oleh jaringan iklan |
| Agensi | Tidak untuk digunakan oleh agensi |
| Zona waktu khusus aplikasi | Tidak Berlaku. Folder Data Locker dibagi-bagi berdasarkan jam menggunakan UTC. Event aktual berisi waktu dalam UTC. Konversi waktu ke zona waktu lainnya sesuai kebutuhan. Apa pun zona waktu aplikasi Anda, penundaan dari terjadinya event hingga direkam di Data Locker tetap sama. |
| Mata uang khusus aplikasi | Tidak didukung |
| Keterbatasan ukuran | Tak dapat diterapkan |
| Kesegaran data | Data diperbarui sesuai pembaruan data laporan spesifik yang dirinci dalam <Anchor target="_blank" href="/marketers/id/docs/data-locker-advertiser-reports#laporan-data-lengkap">artikel ini</Anchor>. |
| Data historis | Tidak didukung. Jika Anda memerlukan data historis, beberapa laporan, tetapi tidak semua, tersedia melalui Pull API. |
| Data yang dibatasi | Bidang dalam beberapa laporan dibatasi karena batasan privasi. <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions">Pelajari lebih lanjut</Anchor> |
| Akses pengguna | Hanya <Anchor target="_blank" href="/marketers/id/docs/user-management">pengguna akun dengan izin yang diperlukan</Anchor> yang dapat mengonfigurasi Data Locker. |
| Aplikasi tunggal/multi aplikasi | Dukungan multi-aplikasi. Data locker ada di tingkat akun |

</Accordion>

<div id="troubleshooting" />

<Accordion title="Pemecahan Masalah">

* **Tanda-tanda**: Tidak dapat mengambil data menggunakan AWS CLI
* **Pesan kesalahan**: Terjadi kesalahan (AccessDenied) saat memanggil operasi ListObjectsV2: Akses Ditolak
* **Alasan**: Kredensial AWS yang digunakan bukan kredensial yang benar untuk bucket AppsFlyer. Ini dapat disebabkan karena memiliki beberapa kredensial atau tidak valid di perangkat Anda.
* Solusi:
  1. Gunakan metode lain, seperti [Cyberduck](/docs/data-locker-for-marketers#cyberduck) untuk mengakses bucket, artinya bukan CLI. Lakukan ini untuk memverifikasi bahwa kredensial yang Anda gunakan berfungsi. Jika Anda dapat terhubung menggunakan Cyberduck, ini menunjukkan adanya masalah dengan cache kredensial.
  2. <Anchor target="_blank" href="https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-role.html">Segarkan cache kredensial AWS</Anchor>.  
     **Tangkapan layar dari AWS**

     ![mceclip0.png](https://files.readme.io/e6608b196c39cb71e0a02e0eabe95378f24659a1578a16fd381bfd0053ca309e-32966264043537.png)

</Accordion>

<div id="aws-data-retrieval" />

## Pengambilan data AWS

Gunakan alat pengambil data S3 pilihan Anda, AWS CLI, atau salah satu alat yang dijelaskan di bagian berikut. Perhatikan! Instruksi yang tepat cocok untuk bucket milik AppsFlyer. Sesuaikan instruksi sesuai kebutuhan jika Anda terhubung ke bucket.

<div id="aws-cli" />

<Accordion title="AWS CLI">

Sebelum Anda mulai:

* Instal AWS CLI di komputer Anda.
* Di AppsFlyer, buka Data Locker, ambil informasi yang tersedia di panel kredensial.

**Untuk menggunakan AWS CLI**:

1. Buka terminal. Untuk melakukannya di Windows, &lt;Windows> + &lt;R> , klik **OK**.  
   Jendela baris perintah terbuka.
2. Masukkan **konfigurasi aws**
3. Masukkan AWS Access Key seperti yang muncul di panel kredensial.
4. Masukkan Kunci Rahasia AWS Anda seperti yang muncul di panel kredensial.
5. Masukkan **eu-west-1**
6. Tekan Enter (Tidak Ada)

Gunakan perintah CLI yang mengikuti sesuai kebutuhan.

Dalam perintah berikut, nilai `{home-folder}` dapat ditemukan

**Untuk membuat daftar folder di bucket Anda:**

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/
```

<div id="listing-files-and-folders" />

### Mendaftar file dan folder

Ada tiga jenis folder di keranjang Data Locker Anda:

* Jenis Laporan `t=`
* Tanggal `dt=`
* Waktu `h=`

Untuk membuat daftar semua laporan dari jenis laporan tertentu:

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/ t=installs /
```

Untuk membuat daftar semua laporan dari jenis laporan tertentu untuk hari tertentu:

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/dt=2019-01-17
```

Untuk membuat daftar semua laporan dari laporan tertentu, dalam jam tertentu dari hari tertentu:

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/dt=2019-01-17/h=23
```

Untuk mengunduh file untuk tanggal tertentu:

```bash
aws s3 cp s3://af-ext-reports/<home-folder>/data-locker-hourly/t=installs/dt=2020-08-01/h=9/part-00000.gz ~/Downloads/
```

</Accordion>

<div id="cyberduck" />

<Accordion title="Cyberduck">

Sebelum Anda mulai:

* Instal klien Cyberduck.
* Di AppsFlyer, buka Data Locker dan ambil informasi yang tersedia di panel kredensial.

**Untuk mengonfigurasi Cyberduck**:

1. Di Cyberduck, klik Tindakan.
2. Pilih **Bookmark Baru**. Jendela terbuka.
3. Di bidang pertama (ditandai [1] pada tangkapan layar di bawah) pilih **Amazon S3.**

   [![DataDuckSmall2.png](https://files.readme.io/a2aba523ca9489315260f34c6c42571f67d37f7985d0f18b1eb0ed2a95b4b4ad-32966274482705.png)](https://files.readme.io/a2aba523ca9489315260f34c6c42571f67d37f7985d0f18b1eb0ed2a95b4b4ad-32966274482705.png)
4. Isi bidang-bidang sebagai berikut:
   * **Nama Panggilan:** Teks bebas
   * **Server:** s3.amazonaws.com
   * **ID Kode Akses:** Salin Kode Akses AWS seperti yang muncul di panel kredensial di AppsFlyer
   * **Kode Akses Rahasia:** Salin kode Rahasia Bucket seperti yang muncul di panel kredensial di AppsFlyer.
   * ***Jalur*** : `{Bucket Name}/{Home Folder}` Misalnya: **af-ext-report / 1234-abc-ffffffff**
5. Menutup jendela. Untuk melakukannya, klik X di sudut kanan atas jendela.
6. Pilih koneksi.   
    Direktori data ditampilkan.

</Accordion>

<div id="amazon-s3-browser" />

<Accordion title="Browser Amazon S3">

Sebelum Anda mulai:

* Pasang Browser Amazon S3.
* Di AppsFlyer, buka Data Locker dan ambil informasi yang tersedia di panel kredensial.

**Untuk mengonfigurasi Browser Amazon S3** :

1. Di browser S3, Klik ***Akun*** **Tambahkan**   **Akun Baru** .  
   Jendela Tambah Akun Baru terbuka.

   [![mceclip0.png](https://files.readme.io/f7ea8b02f27a5e7eaf89b578b177a9e1a9f34273eaa41d41652156a6dbb23d5c-32966274485009.png)](https://files.readme.io/f7ea8b02f27a5e7eaf89b578b177a9e1a9f34273eaa41d41652156a6dbb23d5c-32966274485009.png)
2. Isi bidang-bidang sebagai berikut:
   * **Nama Akun** : teks bebas.
   * **ID Kunci Akses**: salin Kunci Akses AWS seperti yang muncul di panel kredensial.
   * **Kunci Akses Rahasia**: salin kunci Rahasia Bucket seperti yang muncul di panel kredensial.
   * Pilih **Enkripsi Kunci Akses** dengan kata sandi dan masukkan kata sandi. Catat kata sandi ini.
   * Pilih **Gunakan transfer aman.**
3. Klik **Simpan perubahan**.
4. Klik ***Bucket **>** Tambahkan Eksternal*** **Bucket** .  
   Jendela Tambah Bucket Eksternal terbuka.   

   <Image alt="mceclip2.png" src="https://files.readme.io/88dd43f62dbd68d0295b52a7f7b9b09449bd915e6a6d52703c24a50583e05a6e-32966264054929.png" width="433px" />
5. Masukkan **Nama bucket.** Nama Bucket memiliki format berikut: `{Bucket Name}/{Home Folder}`. Nilai yang diperlukan untuk nama bucket dan folder beranda muncul di jendela kredensial.
6. Klik **Tambahkan bucket eksternal.** Bucket dibuat dan ditampilkan di panel kiri jendela.   
   Anda sekarang dapat mengakses file Data Locker.

</Accordion>

<div id="see-also" />

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/data-locker-advertiser-reports">Laporan tersedia melalui Data Locker</Anchor>
> * <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Memilih alat pengiriman data yang tepat</Anchor>

<div data-zendesk-anchors="h_01HE2S6FANNTNB580CMHNX34YA=data-locker data-locker%E2%80%94features=data-locker-features h_01HE2S6FANQH2GZ11S8S87H0YH=data-locker-features h_01HE2S6FAN6BFPJSZJBEE9P5VK=reports-available-via-data-locker data-storage-architecture=arsitektur-penyimpanan-data h_01HE2S6FAN4H9DQ5HBTKSNJ72B=arsitektur-penyimpanan-data h_01HE2S6FANY1FWEY6Y34T85GHM=overview h_01HE2S6FANDJ65MZ2H2FBAZYJR=folder-structure h_01HE2S6FAN7PBZ8M86FQVSN5KQ=hourly-folders h_01HE2S6FAN366V8HNCY4PFNTFG=version-folders h_01HE2S6FANHFZMCY3WZBZB9QMP=app-segregation h_01HE2S6FANVDFH9S9JN8E9J7ES=data-files h_01HE2S6FAN8ZDF5N4ECKKN1D1H=storage-options h_01HE2S6FAN2HY7V3G9NS9XCVE1=perhatian notice-to-security-officers-in-the-case-of-customercontrolled-storage=pemberitahuan-kepada-petugas-keamanan-dalam-hal-penyimpanan-yang-dikontrol-pelanggan h_01HE2S6FANRVGYPRWWFA50JAQ4=pemberitahuan-kepada-petugas-keamanan-dalam-hal-penyimpanan-yang-dikontrol-pelanggan h_01HE2S6FANBRXA0NS4E8SP3618=multipleconnections-principles-more-than-one-destination procedures=prosedur h_01HE2S6FANEGZC1SAPSEK0EJJQ=prosedur h_01HE2S6FAN9ZQKVYH9PBN5GCB4=set-up-data-locker h_01HE2S6FANG1NGEDPXEKF5RNBD=reset-credentials additional-information=informasi-tambahan h_01HE2S6FAP4SA77B0SX7R8JMTY=informasi-tambahan h_01HE2S6FAP6FKAJCW92JVWD828=traits-and-limitations h_01HE2S6FAPJC20G7YZSRWP5E34=troubleshooting aws-data-retrieval=pengambilan-data-aws h_01HE2S6FAPJMKX567HSAR16TCN=pengambilan-data-aws h_01HE2S6FAPB5MW09Y4HKFV3RM8=aws-cli listing-files-and-folders=mendaftar-file-dan-folder h_01HE2S6FAP31H9NK6V870FGXZF=mendaftar-file-dan-folder h_01HE2S6FAP2E2TW4F5PJ4226Q0=cyberduck h_01HE2S6FAP74NG5VNEWKWXXJX2=amazon-s3-browser h_01HE7RB5N99WJ3XP69Z69H81AD=lihat-juga" />
