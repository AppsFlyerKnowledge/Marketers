---
title: Ikhtisar pelaporan gabungan dan analitik
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
    - Ad Networks
  created_at: '2020-02-04T09:38:14Z'
  edited_at: '2023-10-27T14:54:59Z'
  id: 360005437257
  locale: id
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/id/articles/360005437257
---
> **Sekilas:** Deskripsi dan perbandingan laporan gabungan dan atribusi analitik, alat, dan API tersedia.

## Pelaporan kinerja gabungan dan analitik—alat dan laporan

Alat analitik gabungan di platform memberikan pemasang iklan metrik yang memungkinkan mereka menilai kinerja aplikasi, kampanye, dan pengguna mereka.

Alat berbeda dalam cara data disajikan. Misalnya, dashboard Ikhtisar memberikan metrik nilai periode retensi kampanye (LTV), sedangkan Kelompok digunakan untuk menganalisis interaksi pengguna dari waktu ke waktu.

Alat yang dirinci dalam artikel ini terkait dengan data yang dapat diekspor dari platform. Gunakan tabel perbandingan alat berikut untuk memahami fungsi utama dan perbedaan antara alat-alat tersebut.

<div id="toolapi-comparison" />

<Accordion title="Perbandingan metode pelaporan">

Tabel berikut menjelaskan berbagai metode pelaporan dan dashboard untuk mendapatkan data gabungan.

**[Unduh tabel sebagai file CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vSICicxcvD0996RT59fTLDJvdGUKxqPqr47f5SMD8BmsbZtrWIoxRxJEo7tAXTBBmnIbiH097VtK6L9/pub?output=xlsx) untuk melihat bidang tambahan yang menjelaskan berbagai spesifikasi dan batasan untuk membantu Anda membandingkan dan membedakan berbagai metode pelaporan.**

Bidang spesifikasi tambahan dalam file CSV yang dapat diunduh meliputi:

* <Anchor target="_blank" href="/marketers/id/docs/about-data-freshness-and-timezone-support">Keaktualan data</Anchor>:Periode waktu antara terjadinya event dan data menjadi tersedia melalui metode pelaporan.
* <Anchor target="_blank" href="/marketers/id/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV/aktivitas</Anchor>: Apakah data adalah LTV atau aktivitas.
* <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide">Penargetan Ulang</Anchor>: Apakah data penargetan ulang (interaksi ulang dan atribusi ulang) ditampilkan.
* <Anchor target="_blank" href="/marketers/id/docs/measure-reinstalls#attributed-to-the-first-install">Atribusi event penginstalan ulang ke penginstalan pertama</Anchor>: Apakah event setelah penginstalan ulang dapat dikaitkan dengan penginstalan asli.
* <Anchor target="_blank" href="/partners/id/docs/about-agency-accounts#transparansi-agensi">Transparansi agensi</Anchor>: Apakah pemasar dapat melihat identitas sumber media asli untuk lalu lintas yang berasal dari agensi.
* <Anchor target="_blank" href="/marketers/id/docs/about-data-freshness-and-timezone-support#date-and-timezone-principles">Zona waktu</Anchor>: Zona waktu apa (UTC atau pilihan aplikasi) yang digunakan untuk menampilkan data.
* <Anchor target="_blank" href="/marketers/id/docs/measure-reinstalls#unattributed-organic-inapps">Event yang tidak diatribusikan</Anchor>: Apakah event yang tidak diatribusikan setelah penginstalan ulang ditampilkan.
* <Anchor target="_blank" href="/marketers/id/docs/campaign-name-changes?">Perubahan nama kampanye</Anchor>: Anda dapat mengubah nama kampanye tanpa membuat tampilan duplikat.

| Metode pelaporan | Deskripsi |
| --- | --- |
| Dashboard Ikhtisar | Nilai periode retensi (LTV) pengguna yang menginstal, melibatkan ulang, atau mengatribusikan ulang selama rentang tanggal yang dipilih. |
| <Anchor target="_blank" href="/marketers/id/docs/master-api-user-acquisition-metrics-via-api">API Master</Anchor>  <br />(Fitur premium) | LTV, aktivitas, retensi, kelompok, dan KPI performa kampanye Protect360 yang dipilih berdasarkan API, dalam format CSV atau JSON. |
| <Anchor target="_blank" href="/marketers/id/docs/pull-api-aggregate-data">Pull API - laporan gabungan</Anchor> | Nilai periode retensi (LTV) pengguna yang menginstal, melibatkan ulang, atau mengatribusikan ulang dalam file CSV. Data UA dan penargetan ulang terpisah; tidak ada opsi terpadu. |
| <Anchor target="_blank" href="/marketers/id/docs/aggregated-data-export-page">Halaman data ekspor - laporan gabungan</Anchor> | Nilai periode retensi (LTV) pengguna yang menginstal, melibatkan ulang, atau mengatribusikan ulang dalam file CSV. Data UA dan penargetan ulang terpisah; tidak ada opsi terpadu. |
| <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN</Anchor>  <br /><Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">ringkasan</Anchor> | Metrik dilaporkan melalui postback SKAN iOS dan titik data tambahan selama jendela pengukuran pengguna awal. |
| <Anchor target="_blank" href="/marketers/id/docs/skan-aggregated-performance-report-api">SKAN</Anchor>  <br /><Anchor target="_blank" href="/marketers/id/docs/skan-aggregated-performance-report-api">API data gabungan</Anchor> | Metrik dilaporkan melalui postback SKAN iOS dan titik data tambahan selama jendela pengukuran pengguna awal. |
| <Anchor target="_blank" href="/marketers/id/docs/protect360-dashboard">Dashboard Protect360</Anchor> | Metrik dan wawasan yang berkaitan dengan lalu lintas penipuan.  <br />Data berbasis LTV untuk penginstalan, dan data berbasis aktivitas untuk in-app event. |
| <Anchor target="_blank" href="/marketers/id/docs/activity-dashboard">Dashboard aktivitas</Anchor> | Aktivitas aplikasi, interaksi, dan metrik dalam aplikasi selama rentang tanggal yang dipilih. |
| Dashboard event | Metrik kinerja in-app event di seluruh sumber media berdasarkan data LTV pengguna yang menginstal aplikasi selama rentang tanggal yang dipilih. |
| dasbor retensi | Metrik keterlibatan pengguna (sesi) unik untuk setiap hari setelah penginstalan. |
| <Anchor target="_blank" href="/marketers/id/docs/cohort-and-retention-dashboard">Dashboard kohort</Anchor> | Berbagai metrik pengguna untuk setiap hari setelah penginstalan. |
| <Anchor target="_blank" href="/marketers/id/docs/cohort-api">API kelompok</Anchor>  <br />(Fitur premium) | Berbagai metrik pengguna untuk setiap hari setelah penginstalan. |
| <Anchor target="_blank" href="/marketers/id/docs/cohort-analytics-via-data-locker">Data Locker Kelompok</Anchor>  <br />(Fitur premium) | Berbagai metrik pengguna untuk setiap hari setelah penginstalan. |
| <Anchor target="_blank" href="/marketers/id/docs/custom-dashboards">Dashboard Personalisasi</Anchor> | dasbor yang disesuaikan dengan metrik akuisisi pengguna LTV. |
| <Anchor target="_blank" href="/marketers/id/docs/pivot-table-user-metrics">Laporan pivot</Anchor>  <br />(Fitur premium) | LTV, aktivitas, retensi, dan KPI performa kampanye Protect360 yang dipilih, di dasbor atau melalui CSV. |
| <Anchor target="_blank" href="/marketers/id/docs/set-up-and-use-roi360-cost-etl-reports">ETL Biaya</Anchor> | Data biaya kampanye dengan perincian terbaik yang tersedia per sumber media. |
| Laporan penggunaan | Kombinasi dari semua fitur berbasis penggunaan di AppsFlyer yang memengaruhi kewajiban kontrak selama jangka waktu siklus penagihan. |

</Accordion>

<div id="cohort-flavors" />

<Accordion title="Rasa kelompok">

Kelompok tersedia dalam beberapa *rasa* yang berbeda menjadi <Anchor target="_blank" href="/marketers/id/docs/cohort-and-retention-dashboard">dasbor Kelompok</Anchor>, <Anchor target="_blank" href="/marketers/id/docs/cohort-api">API Kelompok</Anchor>, dan <Anchor target="_blank" href="/marketers/id/docs/cohort-analytics-via-data-locker">analitik Kelompok melalui Data Locker.</Anchor> Tabel berikut mencantumkan perbedaannya.

| Karakteristik | Analitik kohort di Data Locker | dasbor Kohort | API Kelompok |
| --- | --- | --- | --- |
| Aplikasi multi atau tunggal | Multi. Data dikelompokkan per aplikasi dalam satu file atau dipisahkan menjadi file terpisah per aplikasi. | Multi. Performa gabungan atau dikelompokkan berdasarkan opsi aplikasi. | Tunggal |
| Grouping | Hierarki kampanye lengkap dan nama event. Kira-kira 20 pengelompokan | 4 pengelompokan | 7 pengelompokan |
| Metrik yang tersedia | Semua metrik | 1 metrik yang dapat dipilih dan 4 metrik tetap per tampilan | 1 metrik yang dapat dipilih dan 4 metrik tetap per panggilan |
| Hari setelah atribusi tersedia (hari kelompok) | 365 | 180 | 180 |
| Batasan ekspor data | Seluruh kumpulan data tersedia | Pengunduhan dan pengaturan manual | Nilai dan ukuran respons terbatas |
| Permintaan yang dapat disesuaikan | Tidak | Ya | Ya |

</Accordion>

### Laporan perjalanan pengguna

* Uraian laporan tersedia via laman data Ekspor atau dengan menggunakan agregat Pull API.
* Ini adalah <Anchor target="_blank" href="/marketers/id/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">Nilai periode retensi (LTV)</Anchor> sehingga rentang tanggal pelaporan terkait dengan tanggal atribusi menjadi:
  * Tanggal instalasi untuk laporan UA dan Protect360
  * Tanggal atribusi ulang atau interaksi ulang dalam hal penargetan ulang laporan
* Tanggal pelaporan paling awal yang tersedia adalah tanggal instalasi aplikasi pertama.

<div id="ua-ltv-aggregate-data-reports-containing-nonorganic-and-organic-users" />

<Accordion title="Laporan data agregat UA LTV yang berisi pengguna non-organik dan organik">

<table><tbody><tr><th>Nama laporan</th><th>Dikelompokkan berdasarkan</th></tr><tr><td>Partners (media source)</td><td>Agensi, sumber media, kampanye</td></tr><tr><td>Partners by date</td><td>Tanggal, agensi, sumber media, kampanye</td></tr><tr><td>Aktivitas sehari-hari</td><td>Tanggal, agensi, sumber media, kampanye</td></tr><tr><td>Geo</td><td>Negara, agensi, sumber media, kampanye</td></tr><tr><td>Geo berdasarkan tanggal</td><td>Tanggal, negara, agensi, sumber media, kampanye</td></tr><tr><td>Atribusi view-through (VTA) KPI</td><td><p><a href="./pull-api-aggregate-data" target="_blank">Laporan VTA disediakan oleh Pull API</a></p></td></tr><tr><td colspan="2"> <strong>Catatan</strong>: Jika Meta ads adalah <em>sumber media</em> yang dipilih, maka kolom tambahan termasuk: ID Kelompok Data, Nama Kelompok Data, ID Kumpulan Data, Nama Kumpulan Data</td></tr></tbody></table>

Bidang tanggal dalam file CSV memiliki format yyyy-mm-dd. Saat Anda membuka file CSV di Excel, bidang tanggal diformat menggunakan pengaturan tanggal dan waktu komputer Anda. Pastikan untuk memilih tampilan tanggal yang sesuai di <Anchor target="_blank" href="https://support.office.com/en-us/article/format-a-date-the-way-you-want-8e10019e-d5d8-47a1-ba95-db95123d273e#ID0EAACAAA=Windows">Excel.</Anchor>

#### Contoh laporan agregat

[Contoh laporan dalam lembar kerja](https://docs.google.com/spreadsheets/d/e/2PACX-1vQmzRons779Dk5QWVoPsOF8E7yJLwNPB1IF87shZr6rcMJLjszlSNIbAMVcdeQLysr8Bc4QAby5QB4u/pub?output=xlsx)

#### Bidang dalam laporan agregat UA

<table><thead><tr><th rowspan="2">Kolom</th><th rowspan="2">Deskripsi</th><th colspan="5"><p><strong>Nama laporan</strong></p></th></tr><tr><th><p><strong>Partners (media source)</strong></p></th><th><p><strong>Mitra berdasarkan tanggal</strong></p></th><th><p><strong>Harian</strong></p></th><th><p><strong>Geo</strong></p></th><th><p><strong>Geo berdasarkan tanggal</strong></p></th></tr></thead><tbody><tr><td><p>Negara</p></td><td>Instal negara</td><td> </td><td> </td><td> </td><td><p>✓</p></td><td> ✓</td></tr><tr><td><p>Tanggal</p></td><td><p>Tanggal atribusi</p></td><td> </td><td><p>✓</p></td><td> </td><td> </td><td><p>✓</p></td></tr><tr><td><p>Agensi/PMD (af_prt)</p></td><td><p>Agensi/nama mitra</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Sumber Media (pid)</p></td><td><p>Sumber media membawa pengguna (pid=sumber media)</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Kampanye</p></td><td><p>Nama kampanye</p><p>(c= nama kampanye)</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>ID kampanye</p></td><td><p>ID kampanye Meta </p></td><td>Hanya Meta ads</td><td>Hanya Meta ads</td><td>Hanya Meta ads</td><td>Hanya Meta ads</td><td>Hanya Meta ads</td></tr><tr><td><p>ID Adgroup</p></td><td><p>ID kelompok Meta ad atau ID Iklan</p></td><td>Hanya Meta ads</td><td>Hanya Meta ads</td><td>Hanya Meta ads</td><td>Hanya Meta ads</td><td>Hanya Meta ads</td></tr><tr><td><p>Nama Adgroup</p></td><td><p>Kelompok Meta ad</p></td><td>Hanya Meta ads</td><td>Hanya Meta ads</td><td>Hanya Meta ads</td><td>Hanya Meta ads</td><td>Hanya Meta ads</td></tr><tr><td><p>ID adset</p></td><td><p>ID kumpulan iklan Meta</p></td><td>Hanya Meta ads</td><td>Hanya Meta ads</td><td>Hanya Meta ads</td><td>Hanya Meta ads</td><td>Hanya Meta ads</td></tr><tr><td><p>Nama Adset</p></td><td><p>Nama kumpulan iklan Meta</p></td><td>Hanya Meta ads</td><td>Hanya Meta ads</td><td>Hanya Meta ads</td><td>Hanya Meta ads</td><td>Hanya Meta ads</td></tr><tr><td><p>ARPU</p></td><td><p>Pendapatan rata-rata per pengguna</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td>✓</td><td><p>✓</p></td></tr><tr><td><p>eCPI Rata-Rata</p></td><td><p>eCPI Rata-Rata</p></td><td> </td><td><p>✓</p></td><td> </td><td> </td><td> </td></tr><tr><td><p>Klik</p></td><td><p>Jumlah klik</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Rasio Konversi</p></td><td><p>Jumlah instalasi/jumlah klik</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>CTR</p></td><td><p>Rasio Click-through (klik-tayang)</p></td><td> </td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td> </td></tr><tr><td><p>`{your event name}(Pengguna unik)</p></td><td><p>Jumlah pengguna unik yang melakukan event tersebut</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>{your event name} (Penghitung event)</p></td><td><p>Penghitung Event</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>{your event name}` (Penjualan di XXX)</p></td><td><p>Event penjualan di XXX di mana XXX adalah mata uang pilihan aplikasi</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Tayangan </p></td><td><p>Jumlah impresi</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td> </td><td> </td></tr><tr><td><p>Install</p></td><td><p>Jumlah Install</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Pengguna Setia</p></td><td><p>[default] Pengguna yang membuka aplikasi lebih dari 3 kali</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Pengguna Setia/Instalasi</p></td><td><p>Rasio pengguna setia</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td> </td><td> </td></tr><tr><td><p>ROI</p></td><td><p>Tingkat pengembalian investasi</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td> </td><td> </td></tr><tr><td><p>Sesi</p></td><td><ul><li>Jumlah aplikasi non-organik yang dibuka</li><li>Sesi organik dan non-organik tersedia di analisis Kohort</li></ul></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Total Biaya</p></td><td><p>-</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td> </td><td> </td></tr><tr><td><p>Total pendapatan</p></td><td><p>Total pendapatan yang dihasilkan dari sumber media dan kampanye</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td colspan="7"><p> <strong>Catatan:</strong> Kolom yang menampilkan "Hanya Meta ads" disertakan saat memilih Meta ads sebagai satu-satunya sumber media.</p></td></tr></tbody></table>

</Accordion>

<div id="retargeting" />

<Accordion title="Retargeting">

* Laporan penargetan ulang terdiri dari pengguna yang berinteraksi dengan <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide#retargeting-reports-and-raw-data">kampanye penargetan ulang</Anchor> dan melakukan interaksi ulang atau atribusi ulang
* Dalam laporan penargetan ulang, tidak ada perbedaan antara pengguna organik dan non-organik.
* Untuk mendapatkan laporan penargetan ulang melalui Pull API, tambahkan  parameter *& reattr = true* ke URI laporan kinerja.

#### Laporan penargetan ulang LTV agregat

| Nama laporan | Dikelompokkan berdasarkan |
| --- | --- |
| Partners (media source) | Agensi, sumber media, kampanye |
| Partners by date | Tanggal, agensi, sumber media, kampanye |
| Aktivitas berdasarkan tanggal | Tanggal, agensi, sumber media, kampanye |
| Negara | Negara, agensi, sumber media, kampanye |
| Negara berdasarkan tanggal | Tanggal, negara, agensi, sumber media, kampanye |

#### Laporan penargetan ulang LTV agregat

| Kolom | Deskripsi | Mitra | Harian | Partners by date | Geo berdasarkan tanggal | Geo |
| --- | --- | --- | --- | --- | --- | --- |
| Tanggal | Tanggal konversi | - | - | ✓ | ✓ | - |
| Negara |  | - | ✓ |  | ✓ | ✓ |
| Agensi/PMD (af\_prt) | Agensi/nama mitra | ✓ | ✓ | ✓ | ✓ | ✓ |
| Sumber Media (pid) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Campaign (c) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Klik |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Konversi |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Tipe konversi | Atribusi ulang atau interaksi ulang | ✓ | ✓ | ✓ | ✓ | ✓ |
| Rasio Konversi | Konversi/klik | ✓ | ✓ | ✓ | ✓ | ✓ |
| Sesi |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Pengguna Setia |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Pengguna Setia/Instalasi |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Total Biaya |  | - | - | - | - | - |
| eCPI Rata-Rata |  | - | - | - | - | - |
| Total Pendapatan |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| ROI |  | - | - | - | - | - |
| ARPU |  | ✓ | ✓ | ✓ | - | ✓ |

</Accordion>

## Laporan fitur

<div id="skadnetwork" />

<Accordion title="SKAdNetwork">

<Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide#reporting-options">Pelaporan agregasi SKAdNetwork</Anchor>

</Accordion>

<div id="protect360-blocked-fraud" />

<Accordion title="Protect360—penipuan yang diblokir">

![](https://theme.zdassets.com/theme_assets/245528/ffbbc473bb0e74b9fb636ed735f69e9af6a25a18.png)

* Laporan agregat penipuan yang diblokir memberikan rincian event yang diblokir oleh <Anchor target="_blank" href="/marketers/id/docs/protect360-anti-fraud-guide">Protect360</Anchor> .
* Laporan tersedia via Pull API. Laporan ini tidak tersedia melalui halaman Data Ekspor.
* Rentang tanggal terkait dengan tanggal instalasi.

#### Laporan Protect360 agregat tersedia melalui Pull API

| Nama laporan |
| --- |
| Partners (media source) |
| Partners by date |
| Geo |
| Geo berdasarkan tanggal |
| Laporan kampanye mitra |

**Batasan:** Alasan pemblokiran **Bot** muncul bahkan dalam kasus di mana alasannya seharusnya **versi aplikasi** atau **id pengguna pelanggan tidak ada**.

</Accordion>

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/configuring-meta-campaign-management-partners">Konfigurasi mitra pengelolaan kampanye Meta</Anchor>
> * <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">Ikhtisar pelaporan data lengkap</Anchor>

<div data-zendesk-anchors="aggregated-and-analytics-performance-reporting%E2%80%94tools-and-reports=pelaporan-kinerja-gabungan-dan-analitikalat-dan-laporan 01EWA9VQ2HH93525BMK6WN0P6S=pelaporan-kinerja-gabungan-dan-analitikalat-dan-laporan 01ED4D7W8B53Q81G7PXQH8ADE2=toolapi-comparison h_01HDNYFR9KBX2KP75K1FAZC2Q7=cohort-flavors user-journey-reports=laporan-perjalanan-pengguna 01ED4D7W8CVAQ9V2GCEX1G6KD7=laporan-perjalanan-pengguna h_01HDNYFR9KBMWAFXDNNJN8VA2X=ua-ltv-aggregate-data-reports-containing-nonorganic-and-organic-users examples-of-aggregate-reports=contoh-laporan-agregat 01ED4D7W8C3ZNBYR3CMHJF3QSE=contoh-laporan-agregat fields-in-ua-aggregate-reports=bidang-dalam-laporan-agregat-ua h_01HDNYFR9KTQ7ZF35C7E7M7AF1=bidang-dalam-laporan-agregat-ua 01ED4D7W8FCW3QTV08MWWA8FDT=retargeting aggregate-ltv-retargeting-reports=laporan-penargetan-ulang-ltv-agregat h_01HDNYFR9MSJWCP3JA4M1WXN1H=laporan-penargetan-ulang-ltv-agregat aggregate-ltv-retargeting-reports::b2093953=laporan-penargetan-ulang-ltv-agregat-1 h_01HDNYFR9MSK9VQQ0Q889Z55TN=laporan-penargetan-ulang-ltv-agregat-1 feature-reports=laporan-fitur h_01HDNYFR9MYXVZ5BA9FDZ6D82M=laporan-fitur 01ED4D7W8CBH7Q8D31VX5313WP=skadnetwork protect360%E2%80%94blocked-fraud=protect360-blocked-fraud h_01HDNYFR9MJNKGR7XFCACVP6KT=protect360-blocked-fraud aggregate-protect360-reports-available-via-pull-api=laporan-protect360-agregat-tersedia-melalui-pull-api h_01HDNYFR9MSZ9K8F283J0WBHCZ=laporan-protect360-agregat-tersedia-melalui-pull-api h_01HDNYYJXVY9XHX87K06NXYQNS=lihat-juga" />
