---
title: Data lengkap Pull API
metadata:
  keywords:
    - Premium
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2020-04-14T18:24:00Z'
  edited_at: '2023-11-02T12:44:39Z'
  id: 360007530258
  locale: id
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/id/articles/360007530258
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Sekilas:** Gunakan API ini untuk mendapatkan laporan data lengkap dalam file CSV.

<Image align="center" alt="PullAPIRaw_us-en.png" src="https://files.readme.io/1e68c85ee7d41a275ac6e09b35f6913fc10d974fc51c7c9c1357d3fd4d6d561c-33379479618705.png" />

<div id="pull-api-raw-data" />

## Data lengkap Pull API

* Pull API memungkinkan Anda mendapatkan laporan data lengkap dalam file CSV. <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">Pelajari lebih lanjut tentang laporan data lengkap</Anchor>
* Filter berdasarkan opsi yang tersedia: Sumber media, rentang tanggal, nama peristiwa dalam aplikasi, dan geo.
* Keunggulan tambahan dalam Pull API adalah:
  * Pilih mata uang
  * Pilih zona waktu

<div id="raw-data-reports-nonorganic" />

<div id="protect360-fraud" />

<div id="ad-revenue-raw-data" />

<div id="retargeting" />

<div id="raw-data-reports-organic" />

<div id="raw-data-reports-available-via-pull-api" />

#### Laporan data lengkap tersedia melalui Pull API

<table><tbody><tr><th><span>Laporan</span></th><th><span>Deskripsi</span></th><th><span>Tingkat penyegaran</span></th></tr><tr><td colspan="3"><strong>Laporan data lengkap (non-organik)</strong></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-installs-report-v5" target="_blank">Instal</a></td><td><span>Mencatat penginstalan non-organik. Catatan dibuat saat pengguna membuka aplikasi untuk pertama kalinya.</span><br/></td><td><span>Waktu sebenarnya</span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-report-v5" target="_blank">In-App Event</a></td><td><span>Mencatat event yang dilakukan pengguna.</span><br/></td><td><span>Waktu sebenarnya</span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-uninstall-events-report-v5" target="_blank">mencopot pemasangan</a></td><td><span>Mencatat saat pengguna meng-uninstall aplikasi.</span><br/></td><td><span>Harian</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-v5" target="_blank">Penginstalan ulang</a></span><br/></td><td><span>Mencatat pengguna yang setelah meng-uninstall aplikasi, berinteraksi dengan sumber media UA, dan menginstal ulang aplikasi selama jendela atribusi ulang.</span></td><td><span>Waktu sebenarnya</span></td></tr><tr><td colspan="3"> <span><strong>Laporan data lengkap (organik)</strong></span><span></span><br/> </td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-installs-report-v5" target="_blank">Penginstalan Organik</a></span><br/></td><td><span>Mencatat saat aplikasi dibuka oleh pengguna untuk pertama kalinya.</span><br/></td><td><span>Berkelanjutan</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-in-app-events-report-v5" target="_blank">In-app event organik</a></span><br/></td><td><span>Mencatat detail tentang event yang dilakukan pengguna.</span><br/></td><td><span>Berkelanjutan</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-uninstall-events-report-v5" target="_blank">Uninstall organik</a></span><br/></td><td><span>Mencatat pengguna yang meng-uninstall aplikasi.</span><br/></td><td><span>Harian</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-organic-v5" target="_blank">Penginstalan organik</a></span><br/></td><td><span>Mencatat pendapatan iklan untuk pengguna yang diatribusikan ke sumber media penargetan ulang selama jendela interaksi ulang.</span><br/></td><td><span>Harian</span><br/></td></tr><tr><td colspan="3"> <span><strong>Data lengkap pendapatan iklan</strong></span><span></span><br/> </td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-raw-v5" target="_blank">Pendapatan iklan yang diatribusikan</a><span></span><br/> </td><td>Mencatat pendapatan iklan untuk pengguna yang diatribusikan ke sumber media.</td><td>Harian</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-organic-raw-v5" target="_blank">Pendapatan iklan organik</a></td><td>Mencatat pendapatan iklan untuk pengguna yang tidak diatribusikan ke sumber media.</td><td>Harian</td></tr><tr><td colspan="3"><span><strong>Penipuan Protect360</strong></span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-installs-report-v5" target="_blank">Install</a></td><td>Catatan penginstalan diidentifikasi sebagai penipuan dan oleh karena itu tidak diatribusikan ke sumber media apa pun.</td><td><span>Waktu sebenarnya</span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-detection-v5" target="_blank">Instalasi pasca atribusi</a></td><td>Mencatat in-app event dari penginstalan palsu dan oleh karena itu tidak diatribusikan sama sekali.</td><td>Waktu sebenarnya</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-in-app-events-report-v5" target="_blank">In-App Event</a></td><td>Mencatat in-app event yang diidentifikasi sebagai penipuan oleh Protect360.</td><td>Harian</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-fraud-post-inapps-v5" target="_blank">In-app event pasca atribusi</a></td><td>Mencatat in-app event untuk penginstalan yang diidentifikasi sebagai penipuan setelah diatribusikan ke sumber media atau dinilai curang tanpa memperhatikan penginstalan itu sendiri.</td><td>Harian</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-clicks-report-v5" target="_blank">Klik</a></td><td>Mencatat klik yang dilakukan pengguna yang diblokir oleh Protect360.</td><td>Harian</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-install-postbacks-v5" target="_blank">Postback instalasi yang diblokir</a></td><td>Mencatat salinan postback yang dikirim ke sumber media yang mengakibatkan penginstalan yang diblokir.</td><td>Waktu sebenarnya</td></tr><tr><td colspan="3"><strong>Postback (postingan balik)</strong></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-postbacks-v5" target="_blank">Postback penginstalan</a></td><td>Mencatat event penginstalan yang dihasilkan saat pengguna membuka aplikasi untuk pertama kalinya.</td><td>Harian</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-postbacks-v5" target="_blank">Postback in-app event</a></td><td>Mencatat postback in-app event yang dikirim ke sumber media.</td><td>Harian</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-retarget-in-app-events-postbacks-v5" target="_blank">Penargetan ulang postback in-app event</a></td><td>Mencatat in-app event yang dilakukan pengguna selama jendela interaksi ulang.</td><td>Waktu sebenarnya</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-retarget-install-postbacks-v5" target="_blank">Postback konversi penargetan ulang</a></td><td>Mencatat in-app event yang dilakukan pengguna selama jendela interaksi ulang.</td><td>Waktu sebenarnya</td></tr></tbody></table>

<div id="using-pull-api-raw-data" />

<Accordion title="Menggunakan data lengkap Pull API">

**Untuk menggunakan data lengkap Pull API**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Dapatkan token API. Admin perlu mengambil token.
2. Berikan token API kepada pengembang Anda untuk digunakan di header autentikasi.
3. Beri programmer Anda parameter untuk diinput saat mereka melakukan panggilan API, seperti yang dijelaskan di bagian berikut. Parameter menentukan fokus laporan dan cara pengaturannya serta memberikan jangka waktu pelaporan.
4. Beri tahu pengembang Anda untuk mengikuti mereka <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">instruksi data lengkap Pull API</Anchor> di hub programmer.

<div id="parameters" />

#### Parameter

| Parameter | Deskripsi |
| --- | --- |
| from | <ul><li>Rentang tanggal terdiri dari parameter `dari`dan `hingga` . Tanggal terkait dengan tanggal aktivitas.</li><li>Format: `yyyy-mm-dd`, `yyyy-mm-dd hh:mm`, atau `yyyy-mm-dd hh:mm:ss` **Catatan**: Ruang perlu dikodekan seperti yang ditunjukkan di sini `from=2020-04-01%2001:00:00` - Secara umum, browser akan menyandikan ruang.</li><li>Contoh: 01-01-2010 atau 01-01-2010 20:15 (Parameter jam dan menit tersedia untuk laporan data lengkap).</li></ul> |
| ke | Tanggal selesai. Seperti untuk `dari` |
| media\_source | `media_source`: Untuk membatasi (menyaring) panggilan ke sumber media tertentu.<br /><br />Tetapkan parameter `media_source` dan `category (kategori)` sebagai berikut:<ul><li>Untuk Meta ads, atur kategori dan sumber media ke *facebook*</li><li>Untuk Twitter, atur kategori dan sumber media ke *twitter*</li><li>Untuk semua sumber media lainnya, atur kategori ke *standar* dan sumber media ke nama sumber media.</li></ul><ul><li>Contoh<ul><li>`media_source=facebook&category=facebook`</li><li>`media_source=abc_example&category=standard`</li></ul></li></ul> |
| maximum\_rows | Jumlah maksimum baris yang dikembalikan oleh satu API call.<ul><li>[Default] jika tidak ada nilai yang dikirim, hingga 200 ribu baris</li><li>200000: Hingga 200 ribu baris yang kembali</li><li>1000000: Hingga 1 juta baris yang kembali</li><li>Contoh: `maximum_rows=1000000` mengaktifkan hingga 1 juta baris.</li></ul> |
| event\_name | Memfilter in-app event berdasarkan event tertentu. Pilih beberapaevent dengan menggunakan daftar yang dipisahkan tanda koma.<br /><br />**Contoh**: `event_name=af_purchase,ftd` |
| atribusi ulang | Atur data atribusi penargetan ulang<ul><li>[Default] Jika salah, kampanye data akuisisi pengguna (UA) kembali.</li><li>Jika benar, data atribusi penargetan ulang kembali.</li><li>**Contoh**:`reattr=true`</li></ul> |
| additional\_fields | Untuk mendapatkan kolom tambahan selain kolom default. <br /><br />**Contoh**: `additional_fields=device_download_time,deeplink_url` |
| currency | Mata uang pendapatan dan biaya<ul><li>[Default] Jika parameter tidak dikirim, data kembali menggunakan USD. Artinya, tidak melakukan apa-apa dan hasilnya kembali dalam USD.</li><li>Jika Anda mengirimkan, `currency=preferred`Mata uang <Anchor target="_blank" href="/marketers/id/docs/app-settings#localization-time-zone">khususaplikasi</Anchor> digunakan. Artinya mata uang diatur di pengaturan aplikasi.</li></ul>**Contoh**: Jika mata uang khusus aplikasi adalah EUR, dengan mengirimkan `currency=preferred`nilainya kembali dalam EUR. |
| zona waktu | [Default] Data kembali menggunakan UTC.<ul><li>Untuk mendapatkan data dalam <Anchor target="_blank" href="/marketers/id/docs/app-settings#localization-time-zone">zona waktu</Anchor> khusus aplikasi, tambahkan `zona waktu` seperti yang ditampilkan di bagian ini ke panggilan:</li></ul><ul><li>`zona waktu=[Numerical value]`</li><li>Contoh: Untuk zona waktu UTC+10:00 gunakan`zonawaktu=+10:00` **Catatan**: Tanda `+`,`-`, dan `:` harus dikodekan. Contoh: +10:00 dikodekan ke `%2B10% 3A00`</li></ul> |
| geo | Filter data berdasarkan kode negara.<br /><br />Batasan: Anda hanya dapat menyetel satu filter kode negara per API call. <br /><br />Contoh: `geo=ZA` |
| from\_install time | <ul><li>Rentang tanggal terdiri dari parameter `dari`dan `hingga` . Tanggal terkait dengan tanggal aktivitas.</li><li>Format: `hh-bb-tttt`</li><li>Contoh: 01-01-2010</li></ul> |
| to\_install\_time | Tanggal selesai. Untuk `from_install time` |
| agency | Untuk membatasi (memfilter) panggilan ke agensi tertentu. |

</Accordion>

<div id="protect360-fields" />

<Accordion title="Bidang Protect360">

<Anchor target="_blank" href="/marketers/id/docs/protect360-raw-data-reports#postattribution-reports">Lihat panduan data lengkap Protect360</Anchor>

</Accordion>

<div id="time-frame-fields" />

<Accordion title="Bidang rentang waktu">

Jika hasil API melebihi batas maksimum, pisahkan laporan menggunakan jam dan menit. Terapkan hal berikut ini:

* **dari**/**hingga:** **yyyy-mm-dd hh:mm**
* **dari:** 
  * Hanya tanggal = dari awal (00:00) tanggal yang dipilih
  * Tanggal dan waktu = dari dan termasuk 00:00
* Parameter **hingga:** 
  * Hanya tanggal = hingga akhir (24:00) hari yang dipilih
  * Tanggal dan waktu = hingga, tetapi tidak termasuk, waktu yang ditampilkan

**Contoh:** Pemilik aplikasi memiliki 1,3 juta penginstalan harian dari semua sumber. Untuk mengatasi batas baris 1 juta, pemilik aplikasi membagi hari menjadi dua URI call 12 jam. Lihat tabel berikut untuk pilihan.

<table><tbody><tr><th>Panggilan API</th><th>Dari </th><th>Hingga </th></tr><tr><td><strong>Panggilan API pertamal</strong> </td><td><p><span><strong>dari</strong> =hh-bb-tttt</span></p><p><span><strong>Contoh:</strong></span></p><ul><li><span><strong>dari</strong>=<code>29-12-2019</code></span></li><li><span>Dimulai pada tanggal ini di awal hari pukul 00:00</span></li></ul></td><td><p><span><strong>hingga</strong>=h</span><span>h-bb-tttt 12:00</span></p><p><strong>Contoh:</strong> </p><ul><li><span><strong>hingga</strong>=<code>29-12-2019 12:00</code></span></li><li> <span>Dilanjutkan hingga 11:59:59, bukan 12:00</span><span> </span> </li></ul></td></tr><tr><td><p><strong>Opsi A:</strong> <strong>Panggilan API kedua</strong> </p><p><span><strong>Contoh:</strong></span><span> </span></p><p><span><strong><kbd><code><kbd>&amp;dari=29-12-2019 12:00&amp;hingga=29-12-2019</kbd></code></kbd></strong></span></p><ul><li><span>Mulai tengah hari 29 Des 2019</span></li><li><span>Berakhir tengah malam 29 Des 2019</span></li></ul></td><td> <p><span><strong>dari</strong>=hh-bb-tttt 12:00</span></p><p><strong>Contoh:</strong> </p><ul><li> <strong>dari</strong>=<span><code>29-12-2019 12:00</code></span> </li><li><span>Mulai dari dan termasuk pukul 12:00</span></li></ul></td><td><p><span> </span></p><p><span><strong>hingga</strong>=yyy</span><span>y-mm-dd </span></p><p><span><strong>Contoh:</strong> </span></p><ul><li><span><strong>sampai</strong>=<code>29-12-2019</code></span></li><li><span>Berakhir pada tengah malam</span></li></ul><p><span> </span></p></td></tr><tr><td><strong>Opsi B: Panggilan API kedua</strong></td><td><p><span><strong>dari</strong>=hh-bb-tttt 12:00</span></p><p><strong>Contoh:</strong> </p><ul><li> <strong>dari</strong>=<span><code>29-12-2019 12:00</code></span> </li><li><span>Mulai dari dan termasuk pukul 12:00</span></li></ul></td><td><p><span><strong>hingga</strong>=hh-bb-tttt+1 00:00</span></p><p><span><strong>+1</strong> = esok harinya pada pukul 00:00</span></p><p><strong>Contoh:</strong> </p><ul><li><span><strong>to= <code>30-12-2019 00:00</code></strong></span></li><li>Artinya sebelum waktu berlalu pada 30 Des.</li></ul></td></tr><tr><td colspan="3"><p><span><strong>Catatan!:</strong>Gunakan opsi A atau B karena hasilnya sama. </span></p></td></tr></tbody></table>

</Accordion>

<div id="additional-fields" />

<Accordion title="Kolom Tambahan">

Bidang laporan tambahan tidak ditambahkan ke daftar bidang default sehingga bidang baru tidak berdampak pada proses impor dan penyerapan yang ada. Gunakan parameter `additional_fields` untuk mendapatkan bidang non-default.

* Hanya sekali mencantumkan bidang.
* Lihat <Anchor target="_blank" href="/marketers/id/docs/raw-data-field-dictionary">daftar bidang yang tersedia</Anchor>.
* Contoh: `additional_fields=device_download_time,deeplink_url`

</Accordion>

<div id="default-fields" />

<Accordion title="Bidang default">

| Kolom Pull API default |
| --- |
| Attributed Touch Time |
| Install Time |
| Event Time |
| eventName |
| nilai event |
| Pendapatan Event |
| Mata Uang Pendapatan Event |
| Penghasilan Event USD |
| Sumber Event |
| Apakah Tanda Terima Divalidasi |
| Partner |
| Media Source |
| Channel |
| Keywords |
| Kampanye |
| ID kampanye |
| adset |
| ID adset |
| ad |
| ID iklan |
| Jenis Iklan |
| ID situs |
| ID Sub Situs |
| Sub Param 1 |
| Sub Param 2 |
| Sub Param 3 |
| Sub Param 4 |
| Sub Param 5 |
| Model Biaya |
| Nilai Biaya |
| Mata Uang Biaya |
| Partner Kontributor 1 |
| Sumber Media Kontributor 1 |
| Kampanye Kontributor 1 |
| Waktu Sentuh Kontributor 1 |
| Waktu Sentuh Kontributor 1 |
| Partner Kontributor 2 |
| Sumber Media Kontributor 2 |
| Kampanye Kontributor 2 |
| Waktu Sentuh Kontributor 2 |
| Waktu Sentuh Kontributor 2 |
| Partner Kontributor 3 |
| Sumber Media Kontributor 3 |
| Kampanye Kontributor 3 |
| Waktu Sentuh Kontributor 3 |
| Waktu Sentuh Kontributor 3 |
| Wilayah |
| Kode Negara |
| Negara |
| city |
| Kode Pos |
| DMA |
| ip |
| wifi |
| Operator |
| Carrier |
| bahasa |
| AppsFlyer ID |
| ID Iklan |
| idfa |
| ID Android |
| ID User Pelanggan |
| imei |
| IDFV |
| platform |
| Jenis perangkat |
| Versi OS |
| Versi aplikasi |
| Versi SDK |
| ID Aplikasi |
| Nama aplikasi |
| ID Bundle |
| Is Retargeting |
| Jenis Konversi Penargetan Ulang |
| Attribution Lookback |
| Reengagement Window |
| Is Primary Attribution |
| Agen User |
| HTTP Referrer |
| Original URL |

</Accordion>

<div id="additional-information" />

## Informasi Tambahan

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Sifat | Komentar |
| --- | --- |
| Jenis token API diperlukan | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)<Anchor target="_blank" href="/marketers/id/docs/managing-appsflyer-tokens">Token V2.0</Anchor> |
| Akses jaringan iklan | Tidak |
| Akses agensi | Ya |
| Transparansi agensi | Ya. Namun, perhatikan bahwa jika Anda menggunakan filter agensi dan filter sumber media, filter sumber media tidak berlaku untuk agensi yang tidak transparan. Artinya, untuk instansi yang tidak transparan, semua data disertakan; bukan hanya data dari sumber media yang difilter. |
| Mata uang khusus aplikasi | Ya |
| Zona waktu khusus aplikasi | Ya |
| Kesegaran data | <ul><li>Setara dengan ketersediaan data di dashboard ikhtisar.</li><li>Laporan diperbarui dengan jeda beberapa jam:<ul><li>In-app event organik</li></ul></li><li>Laporan diperbarui Setiap Hari:<ul><li>mencopot pemasangan</li><li>In-app event pasca atribusi</li><li>Pendapatan Iklan</li></ul></li></ul> |
| Data historis | Ya.  Menurut kebijakan <Anchor target="_blank" href="/marketers/id/docs/user-level-data-retention">retensi</Anchor> dan <Anchor target="_blank" href="/marketers/id/docs/report-generation-quotas-rate-limitations">batasan tarif</Anchor> . |
| Data non-organik | Ya |
| Data organik | Ya |
| Batasan tingkat | Batasan API untuk <Anchor target="_blank" href="/marketers/id/docs/report-generation-quotas-rate-limitations">data lengkap</Anchor>. |
| Keterbatasan ukuran | <ul><li>Maksimal pengembalian API call 200 ribu/1 juta baris.</li><li>Jika laporan memiliki tepat 200 ribu/1 juta baris, maka anggaplah ada baris yang hilang.</li><li>Gunakan parameter maximum\_rows untuk memilih jumlah maksimal baris.</li><li>Lakukan beberapa API call, menggunakan parameter dari/hingga yang menyertakan waktu.</li></ul> |
| Install\_date from dan install\_date\_to | Rentang tanggal penginstalan harus lebih awal dari rentang tanggal aktivitas. |

</Accordion>

<div id="troubleshooting" />

<Accordion title="Pemecahan Masalah">

| Petunjuk/pesan | Solusi |
| --- | --- |
| Laporan tidak berisi data yang diharapkan menurut rentang waktu yang dipilih atau terdapat perbedaan antara laporan data lengkap dan laporan data teragregasi. | Pastikan Anda telah menetapkan parameter `zona waktu`. Jika tidak, data dikirim menggunakan UTC dan bukan zona waktu aplikasi Anda. |

</Accordion>

<div id="see-also" />

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Memilih alat pengiriman data yang tepat/API pelaporan</Anchor>

<div data-zendesk-anchors="pull-api-raw-data=data-lengkap-pull-api h_01HE7S6WDVJD2XFW498P8FPY7W=data-lengkap-pull-api aggregate-performance-reports-available-via-pull-api=laporan-data-lengkap-tersedia-melalui-pull-api h_01HE7S6WDV59VTP6Z4X790QDRD=laporan-data-lengkap-tersedia-melalui-pull-api h_01HE7S6WDVYJ5MAK04VWB4MF6A=using-pull-api-raw-data parameters=parameter h_01HE7S6WDVF8T4719HWDJH8JN1=parameter h_01HE7S6WDVGSS0F116ZB6QVG1N=protect360-fields h_01HE7S6WDVP47A3Q8J7NPH54T5=time-frame-fields h_01HE7S6WDWZ8FR6GRJ40B4CJAV=additional-fields h_01HE7S6WDWMXYF0RHYPF058A9K=default-fields additional-information=informasi-tambahan h_01HE7S6WDW9V8XC3CJ0F96EHN0=informasi-tambahan h_01HE7S6WDWV87YVJMN76STX7A1=traits-and-limitations h_01HE7S6WDWMZPPTR41VHJQ8MWC=troubleshooting h_01HE7S8S8QCSKRA62A2HVK2MYJ=lihat-juga" />
