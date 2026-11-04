---
title: Laporan pemasang iklan Data Locker
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2021-11-11T09:48:51Z'
  edited_at: '2023-11-04T15:04:02Z'
  id: 4410643856657
  locale: id
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/id/articles/4410643856657
---
> **Sekilas:** Laporan data agregat dan lengkap tersedia melalui Data Locker

<div id="reports-available-via-data-locker-for-advertisers" />

## Laporan tersedia melalui Data Locker untuk pemasang iklan

<table><thead><tr><th>Jenis data</th><th>Kelompok laporan</th><th>Diperlukan langganan Data Locker</th></tr></thead><tbody><tr><td>Lengkap</td><td>Perjalanan pengguna—data lengkap</td><td>Ya (2)</td></tr><tr><td>Lengkap</td><td>Protect360</td><td>Ya</td></tr><tr><td>Lengkap</td><td>Atribusi berbasis orang (PBA) </td><td>No (1)</td></tr><tr><td>Lengkap</td><td>Inkrementalitas</td><td>No (1)</td></tr><tr><td>Lengkap</td><td>SKAN</td><td>No (1)</td></tr><tr><td>Lengkap</td><td>Pendapatan Iklan</td><td>Ya</td></tr><tr><td>Lengkap</td><td>CTV</td><td>Ya</td></tr><tr><td>Teragregasi</td><td>Analisis kelompok</td><td>No (1)</td></tr><tr><td colspan="3"><p>(1) Jika Anda tidak berlangganan Data Locker, Anda harus menyediakan <a href="./data-locker-for-marketers#storage-options" target="_blank">penyimpanan yang Anda miliki</a>.</p><p>(2) Kecuali untuk interaksi lintas platform</p></td></tr></tbody></table>

<div id="data-freshness-explanations" />

<Accordion title="Penjelasan keaktualan data">

Berikut ini penjelasan tentang istilah-istilah keaktualan data yang dirujuk dalam tubuh artikel. 

| Istilah | Detail |
| --- | --- |
| 1-3 jam | <ul><li>Kesiapan laporan:<ul><li>95% laporan siap dan tersedia di bucket dalam waktu 1 jam setelah event terjadi.</li><li>99% laporan siap dan tersedia di bucket dalam waktu 3 jam setelah event terjadi.</li></ul></li></ul> |
| Uninstall-Harian | <ul><li>Data uninstall disiapkan setiap hari.</li><li>Biasanya tersedia pada pukul 10:00-12:00 UTC.</li><li>Biasanya ditulis ke folder h=2. Artinya folder h=2 berisi uninstall yang dilaporkan pada hari sebelumnya. Namun, data dapat ditulis ke folder berikutnya; oleh karena itu proses impor harus membaca data semua folder yang ada di folder uninstall. Artinya h=1–24 dan h=terlambat. Misalnya, laporan untuk data yang dihasilkan selama hari Senin ada di folder Selasa h=2. Data tersedia setelah pukul 10:00 UTC pada hari Selasa.</li></ul> |
| Harian+1 | Data pendapatan iklan tersedia setelah 1 hari, artinya data yang dihasilkan selama hari Senin akan tersedia di folder Senin h=23 setelah pukul 20.00 UTC pada hari Selasa. Lihat <Anchor target="_blank" href="/marketers/id/docs/roi360-guide-ad-revenue-attribution#data-freshness">keaktualan data pendapatan iklan</Anchor> |

</Accordion>

<div id="h_01K9CROSSPLATFORMREPORT" />

<div id="conversion-report" />

<div id="advanced-reports" />

<div id="note-1" />

<div id="note" />

<div id="advanced-raw-data-reports-beta" />

<div id="raw-data-reports" />

## Laporan Data Lengkap

<div id="user-journey" />

<Accordion title="Perjalanan pengguna">

Untuk deskripsi jenis laporan, lihat <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">laporan perjalanan pengguna</Anchor>.

| ketegori | Jenis laporan (topik) | Kesegaran data | Organik/Non-organik | Unik untuk Data Locker |
| --- | --- | --- | --- | --- |
| Akuisisi User | Klik | 1-3 jam | N/A | ✓ |
| Retargeting | Klik | 1-3 jam | N/A | ✓ |
| Akuisisi User | Tayangan | 1-3 jam | N/A | ✓ |
| Retargeting | Tayangan | 1-3 jam | N/A | ✓ |
| Akuisisi User | Install | 1-3 jam | Keduanya |  |
| Akuisisi User | In-App Event | 1-3 jam | Keduanya |  |
| Akuisisi User | Pendapatan iklan teratribusi | Harian+1 | Non-organik |  |
| Akuisisi User | Pendapatan iklan organik | Harian+1 | Organik |  |
| Retargeting | Penargetan ulang pendapatan iklan | Harian+1 | Non-organik |  |
| Retargeting | Konversi | 1-3 jam | Non-organik |  |
| Retargeting | In-App Event | 1-3 jam | Non-organik |  |
| Retargeting | Sesi | 1-3 jam | Keduanya | ✓ |
| Akuisisi User | Sesi | 1-3 jam | Keduanya | ✓ |
| Akuisisi User | mencopot pemasangan | Uninstall-Harian | Non-organik |  |
| Akuisisi User | Pencopotan pemasangan organik | Uninstall-Harian | Organik |  |
| Instalasi ulang | Instalasi ulang | 1-3 jam | Non-organik |  |
| Instalasi ulang | Penginstalan ulang organik | 1-3 jam | Organik |  |
| Akuisisi User | Interaksi lintas platform | Per Jam | Keduanya | ✓ |

</Accordion>

<div id="protect360" />

<Accordion title="Protect360">

Lihat <Anchor target="_blank" href="/marketers/id/docs/protect360-raw-data-reports">tentang laporan Protect360</Anchor>

| Jenis laporan (topik) | Kesegaran data |
| --- | --- |
| Instalasi yang diblokir | 1-3 jam |
| In-app event yang diblokir | 1-3 jam |
| Klik terblokir | 1-3 jam |
| Instalasi pasca atribusi | Harian<br /><br />Laporan setiap hari berisi penginstalan setelah atribusi yang dilaporkan pada hari sebelumnya. Misalnya, laporan untuk data yang dihasilkan pada hari Senin ada di laporan Selasa. |

</Accordion>

<div id="peoplebased-attribution" />

<Accordion title="Atribusi Berbasis Orang">

**Kesegaran data**

Setiap hari tersedia 10-12 jam setelah akhir hari sebelumnya UTC. Misalnya, data yang diterima pada hari Senin diproses setelah akhir hari dan tersedia di folder Senin h=23. Data tersedia pada pukul 12:00 UTC pada hari Selasa

**Pertimbangan**

* Data semua bundel merek PBA di akun selalu disediakan tanpa mempertimbangkan filter aplikasi.
* Pemisahan data menurut aplikasi tidak tersedia.

| Jenis laporan (topik) |
| --- |
| <Anchor target="_blank" href="/marketers/id/docs/pba-raw-data-reports#website-visits-and-website-events">Kunjungan situs web</Anchor> |
| <Anchor target="_blank" href="/marketers/id/docs/pba-raw-data-reports#website-visits-and-website-events">Event situs web</Anchor> |
| <Anchor target="_blank" href="/marketers/id/docs/pba-raw-data-reports#websiteassisted-installs::7e12586d">Penginstalan dengan bantuan situs web</Anchor> |
| <Anchor target="_blank" href="/marketers/id/docs/pba-raw-data-reports#conversion-paths">Jalur Konversi</Anchor> |

</Accordion>

<div id="incrementality" />

<Accordion title="Inkrementalitas">

Lihat <Anchor target="_blank" href="/marketers/id/docs/incrementality-for-remarketing-overview#available-reports">Laporan inkrementalitas</Anchor>

</Accordion>

<div id="skan" />

<Accordion title="SKAN">

Tentang <Anchor target="_blank" href="/marketers/id/docs/skan-raw-data-reports">laporan data lengkap SKAN</Anchor>

**Keaktualan data**

* Data tersedia pada hari setelah hari postback diterima oleh AppsFlyer atau data dilaporkan ke AppsFlyer oleh API
* Data terdapat dalam folder h=23 pada tanggal data diterima oleh AppsFlyer. Contoh: Jika postback diterima pada hari Senin, maka diproses setelah akhir hari. Pemrosesan selesai, pada hari Selasa pukul 12.00 UTC, data tersedia di folder Senin h=23.

| Jenis laporan (topik) |
| --- |
| Postback (postingan balik) |
| Salinan postback (dikirim langsung oleh iOS ke AppsFlyer) |
| Install |
| Mengunduh ulang |
| In-app event |
| Dimensi iklan SRN |

</Accordion>

<div id="ad-revenue" />

<Accordion title="Pendapatan Iklan">

Lihat <Anchor target="_blank" href="/marketers/id/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">data lengkap pendapatan iklan</Anchor>

</Accordion>

<div id="ctv" />

<Accordion title="Data platform CTV, PC, dan konsol">

Lihat <Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-data-via-data-locker">data platform CTV, PC, dan konsol melalui Data Locker</Anchor>

</Accordion>

<div id="creative-optimization-etl" />

<div id="advanced-aggregated-reports" />

<div id="aggregated-reports" />

## Laporan agregat

<div id="cohort-analytics" />

<Accordion title="Analisis kelompok">

**Kesegaran data**

* Laporan ditulis ke folder h=23.
* Laporan ini biasanya tersedia pada pukul 10.00-12.00 UTC di folder h=23 pada hari sebelumnya.
* Pemrosesan selesai, pada hari Selasa pukul 12.00 UTC, data tersedia di folder Senin dan tidak ditempatkan di folder h

| Jenis laporan (topik) |
| --- |
| <Anchor target="_blank" href="/marketers/id/docs/cohort-analytics-via-data-locker">Kelompok bersatu</Anchor> |
| <Anchor target="_blank" href="/marketers/id/docs/cohort-analytics-via-data-locker">Akuisisi pengguna kelompok</Anchor> |
| <Anchor target="_blank" href="/marketers/id/docs/cohort-analytics-via-data-locker">Penargetan ulang kelompok</Anchor> |

</Accordion>

<div data-zendesk-anchors="reports-available-via-data-locker-for-advertisers=laporan-tersedia-melalui-data-locker-untuk-pemasang-iklan 01H7WFZN6P1S49NYX8Q0W55P0B=laporan-tersedia-melalui-data-locker-untuk-pemasang-iklan 01H7WFZN6PQWASTMXM9V72QZER=data-freshness-explanations raw-data-reports=laporan-data-lengkap 01H7WFZN6P94YW1V79NT3HV5G4=laporan-data-lengkap 01H7WFZN6PD75S557PDB5PSFFR=user-journey 01H7WFZN6QY2GV69N464EE196M=protect360 01H7WFZN6QW72FDBTMW2ZD7NZQ=peoplebased-attribution 01H7WFZN6QZ1B7BS6E59RVAF30=incrementality 01H7WFZN6Q0P99DCFA7MZQTVSX=skan 01H7WFZN6Q717F9Z1HG38JVBG3=ad-revenue 01H7WFZN6QMJGSAJR00MHYJB6Z=ctv aggregated-reports=laporan-agregat 01H7WFZN6Q90AT8N0VY5PKQ407=laporan-agregat 01H7WFZN6QNKXTRM7G6VFANSZ7=cohort-analytics" />
