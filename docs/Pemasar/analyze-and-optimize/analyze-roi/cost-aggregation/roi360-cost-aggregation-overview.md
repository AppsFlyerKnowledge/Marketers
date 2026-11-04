---
title: ROI360—ringkasan agregasi biaya
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Premium
    - Premium Feature
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2015-12-24T10:45:16Z'
  edited_at: '2023-11-10T07:36:33Z'
  id: 207040526
  locale: id
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/id/articles/207040526
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Sekilas:** Pelajari metode bagi pemasang iklan untuk mengumpulkan dan melihat data biaya pemasaran.

![roi360_image.png](https://files.readme.io/1eaf922de9a1174c1971582dd32f53b995de014c8c2bf288b52a93c83334374e-11245891045777.png)

<div id="cost-aggregation" />

## Agregasi biaya

**ROI360**:

* Menyediakan data biaya iklan gabungan, dan metrik kinerja LTV terkait biaya. Ini tersedia melalui dashboard dan laporan kinerja. Metrik terkait biaya yang tersedia termasuk ROI, ROAS, klik, impresi, ROI kampanye, dan rata-rata biaya efektif per penginstalan (eCPI) dari waktu ke waktu.
* Mendukung berbagai model biaya yang digunakan oleh mitra, misalnya CPI, CPA, CPC, dan CPM.
* Mencatat biaya iklan berdasarkan API, penyerapan belanja iklan (unggahan file CSV), dan <Anchor target="_blank" href="/marketers/id/docs/view-aggregated-cost-data-for-attribution-links">biaya berdasarkan klik</Anchor>.
* Agensi dapat mengakses data biaya ROI360 untuk pemasang iklan dengan langganan ROI360.

Metrik berikut tersedia bagi pemasang iklan tanpa langganan ROI360:

* <Anchor target="_blank" href="/marketers/id/docs/view-aggregated-cost-data-for-attribution-links">Data biaya berdasarkan klik</Anchor>.
* Data klik dan impresi SRN, dikonfigurasi melalui tab **Biaya** mitra terintegrasi SRN.

<div id="principles-of-cost-data-aggregation" />

## Prinsip agregasi data biaya

Bagian ini menjelaskan prinsip-prinsip utama pengumpulan data biaya kampanye.

<div id="cost-aggregation-methods" />

<Accordion title="Metode agregasi biaya">

Data biaya diperoleh dari mitra dengan menggunakan satu atau lebih metode. Jika biaya dilaporkan dengan lebih dari satu metode, maka [mekanisme prioritas biaya](/docs/roi360-cost-aggregation-overview#cost-prioritization-mechanism) menentukan data mana yang digunakan. Hal ini memastikan bahwa data biaya tidak membengkak.

Setelah AppsFlyer memproses data, data akan ditampilkan dalam zona waktu UTC (default) atau sesuai pengaturan <Anchor target="_blank" href="/marketers/id/docs/changing-app-time-zone-settings">zona waktu spesifik aplikasi</Anchor> Anda.

<table><thead><tr><th>Metode agregasi biaya</th><th>Model biaya yang didukung</th><th>Perincian data</th><th>Keaktualan data</th><th>Catatan</th></tr></thead><tbody><tr><td> <a href="./set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api" target="_blank">API</a>\*</td><td>Semua</td><td><p>Tingkatannya tergantung pada integrasi</p></td><td><a href="./about-data-freshness-and-timezone-support#intraday-during-the-day" target="_blank">Dalam satu hari</a></td><td>Data dapat berubah setelah event biaya saat kami mencoba menerima data hingga 30 hari yang lalu (bergantung pada jaringan iklan). Hal ini memungkinkan kami memperhitungkan perubahan retroaktif yang dilakukan oleh jaringan iklan. </td></tr><tr><td><a href="./import-cost-data" target="_blank">Penyerapan Pembelanjaan Iklan (unggahan file)</a></td><td>Semua</td><td> <span>Levelnya </span><span>tergantung pada file yang diunggah</span> </td><td>Hingga 4 jam setelah penyerapan</td><td>Biaya yang dilaporkan dapat dikembalikan dan data yang dikirimkan dikoreksi hingga 90 hari.</td></tr><tr><td> <a href="./view-aggregated-cost-data-for-attribution-links" target="_blank">Klik</a> (tautan atribusi)</td><td>CPI</td><td>Tingkat pengguna</td><td><p>Minimal: waktu real</p><p>Maksimal: Hingga 4 jam setelah klik</p></td><td>Tidak ada perubahan yang mungkin terjadi</td></tr><tr><td colspan="5">\* Integrasi API antara mitra dan AppsFlyer dilakukan dengan Cost API atau InCost API (tidak pernah keduanya). API yang digunakan dan rincian data yang diberikan bergantung pada mitra.</td></tr></tbody></table>

</Accordion>

<div id="cost-data-availability-and-reports" />

<Accordion title="Ketersediaan dan laporan data biaya">

Tabel berikut menunjukkan di mana data biaya tersedia.

Untuk keperluan pemahaman tabel, penjelasan berikut berlaku, kecuali dinyatakan lain dalam keterangan tabel:

* UA: Data biaya untuk kampanye akuisisi pengguna dengan paling sedikit 1 penginstalan yang tercatat baru-baru ini (artinya dalam sekitar 7 hari terakhir).
* Terpadu: Data biaya semua kampanye, termasuk kampanye yang tidak mencatat instalasi baru-baru ini (artinya dalam sekitar 7 hari terakhir). Tabel ini menunjukkan kapan data hanya tersedia untuk kampanye dengan setidaknya 1 penginstalan yang tercatat baru-baru ini.
* Jika perubahan nama kampanye tidak didukung, kedua nama kampanye akan ditampilkan, satu dengan data atribusi, dan satu lagi dengan data biaya. Nama kampanye yang ditampilkan tidak akan menyertakan gambaran data lengkap.

<div id="cost-data-availability-and-reports-table" />

#### Ketersediaan dan laporan data biaya

| Metode pelaporan | Tampilan/tipe data | Dukungan perubahan nama kampanye | Catatan |
| --- | --- | --- | --- |
| Dashboard Ikhtisar | <ul><li>UA</li><li>Terpadu</li></ul> | Ya | Tampilan penargetan ulang tidak menampilkan biaya. Biaya untuk penargetan ulang ditampilkan dalam tampilan terpadu. |
| Dashboard aktivitas | UA | Ya |  |
| Dashboard kohort | <ul><li>UA</li><li>Terpadu</li></ul> | Ya | <ul><li>Tampilan penargetan ulang tidak menampilkan biaya</li><li>Data terpadu ini hanya untuk kampanye dengan setidaknya 1 penginstalan yang tercatat baru-baru ini.</li></ul> |
| API Kelompok | <ul><li>UA</li><li>Terpadu</li></ul> | Ya | Data terpadu ini hanya untuk kampanye dengan setidaknya 1 penginstalan yang tercatat baru-baru ini. |
| Dashboard SKAN: | SKAN | Tidak | Tampilan penginstalan SKAN, beserta data biaya untuk **semua** penginstalan (termasuk penginstalan non-SKAN). |
| API Kinerja Gabungan SKAN | SKAN | Tidak | Tampilan penginstalan SKAN, beserta data biaya untuk **semua** penginstalan (termasuk penginstalan non-SKAN). |
| Dashboard pivot | UA | Tidak |  |
| Master API | UA | Tidak |  |
| Dashboard Personalisasi | UA | Tidak |  |
| ETL Biaya | Terpadu | Ya | Semua data biaya yang tersedia ditampilkan. |
| API Pull Teragregasi | UA | Tidak |  |
| Push API | Data klik lengkap (tidak digabungkan) | Tidak relevan |  |
| API Pull data lengkap | Data klik lengkap (tidak digabungkan) | Tidak relevan |  |
| Data Locker | Data klik lengkap (tidak digabungkan) | Tidak relevan | Kelompok Data Locker tidak mendukung biaya. |

**Catatan**:

* Perincian data dapat berbeda berdasarkan jenis dashboard/laporan. Alat pelaporan<Anchor target="_blank" href="/marketers/id/docs/set-up-and-use-roi360-cost-etl-reports">Biaya ETL</Anchor> berisi kumpulan data lengkap. Ini mencakup detail hierarki kampanye (sumber media, nama kampanye, adset, dan dimensi yang disediakan oleh jaringan iklan, termasuk geo, saluran, ID situs, dan kata kunci).
* Data biaya klik tersedia dalam laporan data lengkap.

</Accordion>

<div id="cost-prioritization-mechanism" />

<Accordion title="Mekanisme prioritas biaya">

Untuk sumber media tertentu, biaya dapat diperoleh melalui lebih dari satu metode agregasi. Untuk menghindari inflasi biaya, mekanisme prioritas biaya kampanye memutuskan data biaya mana yang tersedia di platform. Prioritas diberikan sesuai dengan metode agregasi. Prioritas dari tertinggi hingga terendah adalah: API > Penyerapan Belanja Iklan > Klik. Jika tersedia, gunakan API karena ini yang paling akurat.

**Prioritas metode agregasi biaya kampanye**

![CostPriority.jpg](https://files.readme.io/052420655410713b39c3869a4670465e88d8f7c15a43afc56f11821940fa7c5e-360014470078.jpg)

* Mekanisme ini berdampak pada laporan data agregat dan dashboard.
* Data biaya klik yang tersedia dalam laporan data lengkap tidak terdampak oleh mekanisme penentuan prioritas.

<div id="example-1" />

> 📄 **Contoh**
>
> **Skenario:** Jaringan iklan melaporkan biaya per klik, namun Anda memutuskan untuk mengaktifkan API Biaya jaringan iklan.
>
> **Hasil:** Biaya dikumpulkan berdasarkan klik dan API Biaya. Karena API Biaya diprioritaskan, biaya klik diabaikan.
>
> **Hasil:**
>
> * Kemungkinan untuk menerapkan beberapa metode agregasi biaya. Biaya sebenarnya yang dilaporkan dipengaruhi oleh **aturan prioritas metode agregasi biaya** yang ditetapkan dalam tabel di bawah.
> * Perubahan memengaruhi lalu lintas yang dihasilkan agensi dengan cara yang sama. Ini mencakup lembaga yang transparan dan tidak transparan.
> * Perubahan tersebut mempunyai dampak retroaktif. Data biaya agregat historis dapat berubah.

#### Aturan prioritas metode agregasi biaya

| Metode | Deskripsi |
| --- | --- |
| API | <ul><li>Prioritas utama</li><li>[Praktik terbaik] yang paling tepat</li><li>API Biaya vs. Penyerapan Pembelanjaan Iklan: Jika mitra terintegrasi memiliki API pengumpulan biaya iklan, maka Penyerapan Pembelanjaan Iklan dinonaktifkan. **Perhatikan!** Hal ini terjadi meskipun API itu tidak diaktifkan.</li><li>Aktifkan API:<ul><li>Kapan pun API Biaya diaktifkan, biaya klik diabaikan.</li><li>Pada hari Anda mengaktifkan API, API tersebut mendapatkan data biaya sepanjang hari; tidak masalah pada jam berapa API itu diaktifkan. Biaya klik diabaikan sepanjang hari.</li><li>Mungkin diperlukan waktu beberapa jam agar data tersedia setelah Anda mengaktifkan API.</li></ul></li><li>Nonaktifkan API: Pada hari Anda menonaktifkan API itu, biaya klik diabaikan hingga awal hari berikutnya. **Contoh**: Pada hari Senin pukul 14.00 waktu Tokyo, API itu dinonaktifkan. Pada hari Selasa mulai pukul 00.00 waktu Tokyo, klik tidak lagi diabaikan.</li></ul> |
| Penyerapan Pembelanjaan Iklan | <ul><li>Pada tingkat ID situs dan kata kunci, memiliki prioritas dibandingkan data biaya klik.</li><li>Penyerapan Pembelanjaan Iklan vs. biaya klik pada hari kampanye tertentu:<ul><li>Prioritas diberikan pada biaya yang dicatat berdasarkan penyerapan pada hari itu; biaya klik diabaikan.</li><li>**Contoh: abc\_campaign pada tanggal 5 dan 10 Desember**<ul><li>Catat penyerapan biaya kampanye.</li><li>Biaya klik diabaikan.</li><li>Tidak ada kampanye atau tanggal lain yang terdampak.</li></ul></li></ul></li><li>Jika jaringan iklan memiliki API pengumpulan biaya iklan, maka Penyerapan Pembelanjaan Iklan dinonaktifkan untuk jaringan iklan yang sama.</li></ul> |
| Klik | Prioritas terendah |

</Accordion>

<div id="additional-information" />

## Daftar jaringan iklan

<div id="ad-networks-supporting-cost-api" />

<Accordion title="Jaringan iklan yang mendukung API Biaya">

Tabel berikut mencantumkan semua jaringan iklan yang mendukung API Biaya, dengan rincian data yang tersedia untuk masing-masing jaringan iklan:

* Dimensi
* Fitur yang didukung dan karakteristiknya
* Metrik (seperti yang dilaporkan oleh jaringan iklan)

Unduh file: [CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=csv), <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=xlsx">XLS</Anchor>

<Embed title="ROI360—ringkasan agregasi biaya" typeOfEmbed="iframe" url="https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pubhtml?widget=true&amp;headers=false" providerUrl="https://docs.google.com" height="500px" />

</Accordion>

<div id="traits-and-limitations" />

## Karakteristik dan batasan

| Sifat | Catatan |
| --- | --- |
| Agensi | <ul><li>Agensi dapat mengakses data biaya ROI360 untuk pemasang iklan dengan langganan ROI360.</li><li>Saat agensi transparan menjalankan kampanye, pemasang iklan dapat melihat biaya yang ditampilkan di dashboard dan laporan yang mendukung tampilan terpadu. [Pelajari lebih lanjut](/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports)</li><li>Jika pemasang iklan mengakhiri hubungannya dengan agensi, dan menonaktifkan izin agensi di tingkat aplikasi, jika agensi tersebut telah mengonfigurasi biaya untuk aplikasi tersebut, data biaya tetap diambil. Jika pemasang iklan ingin menghentikan pengambilan data ini, mereka harus meminta agensi untuk menonaktifkan integrasi biaya mereka di AppsFlyer.</li><li>Untuk beberapa jaringan iklan, agensi harus menghubungi pemasang iklan untuk mengaktifkan integrasi dan diminta di UI AppsFlyer untuk melakukan hal tersebut. Untuk jaringan ini, agensi dan pemasang iklan harus memastikan bahwa ketika jaringan iklan mengirimkan data, jaringan tersebut menyertakan parameter `af_prt` , yang diperlukan untuk atribusi biaya agensi.</li></ul> |
| Keaktualan data API | <ul><li><Anchor target="_blank" href="/marketers/id/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">Harian</Anchor> (kecuali Moloco)</li><li>Data Mintegral tersedia melalui API pada hari berikutnya, kira-kira 4 jam setelah hari sebelumnya berakhir (tergantung pada pengaturan zona waktu Mintegral Anda). Artinya, jika event terjadi pada Hari ke-1, data biaya tersedia pada Hari ke-2, sekitar pukul 04.00.</li></ul> |
| Perubahan nama kampanye | Data belanja iklan ditampilkan menggunakan nama kampanye terbaru yang dilaporkan.**Catatan**: Ini untuk tampilan data agregat/gabungan; bukan data lengkap itu sendiri. |
| zona waktu | Jika jaringan iklan hanya mendukung satu zona waktu, dan ada perbedaan antara zona waktu yang didukung jaringan iklan dan zona waktu yang ditetapkan di pengaturan aplikasi Anda, zona waktu yang didukung jaringan iklan akan digunakan. |
| Platform CTV, PC, dan konsol | Untuk aplikasi pada platform ini, data biaya harus dikirim melalui <Anchor target="_blank" href="/marketers/id/docs/import-cost-data">Penyerapan Belanja Iklan</Anchor> menggunakan file unggahan melalui metode email. |

<div data-zendesk-anchors="cost-aggregation=agregasi-biaya h_01HC7K2Y627P56F5JH9QT47GB2=agregasi-biaya principles-of-cost-data-aggregation=prinsip-agregasi-data-biaya h_01HC7K2Y62ZC932EDX00YP7DAW=prinsip-agregasi-data-biaya h_01HC7K2Y62K78M02ZN034N99T0=cost-aggregation-methods h_01HC7K2Y62YPM3A6Z0HBY58J00=cost-data-availability-and-reports cost-data-availability-and-reports::865c5bcd=ketersediaan-dan-laporan-data-biaya h_01HC7K2Y62ZY6HWG5TJDEPHZKH=ketersediaan-dan-laporan-data-biaya h_01HC7K2Y62112X308A0Y7DDDRM=cost-prioritization-mechanism h_01HC7K2Y62SZKXD4W0EJGYF6RS=contoh cost-aggregation-method-priority-rules=aturan-prioritas-metode-agregasi-biaya h_01HC7K2Y62ZW7QEGM5BCATF4Q7=aturan-prioritas-metode-agregasi-biaya list-of-ad-networks=daftar-jaringan-iklan h_01HC7K2Y63T9GK0WW95YM39B5C=daftar-jaringan-iklan h_01HC7K2Y63MG10M4Z66VHY5WYW=ad-networks-supporting-cost-api traits-and-limitations=karakteristik-dan-batasan h_01HC7K2Y63798GYV1M0VQMFDJV=karakteristik-dan-batasan" />
