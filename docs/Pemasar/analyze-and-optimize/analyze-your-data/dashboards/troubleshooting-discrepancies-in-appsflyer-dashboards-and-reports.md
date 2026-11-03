---
title: LTV vs. Aktivitas
metadata:
  keywords:
    - dashboard
    - activity
    - Advertisers
    - ltv
    - life time value
    - lifetime value
    - lifetime
    - Agencies
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
  created_at: '2017-11-07T12:42:27Z'
  edited_at: '2021-06-10T23:15:46Z'
  id: 115005600889
  locale: id
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/id/articles/115005600889
---
> **Sekilas** : Data di AppsFlyer bisa berupa Lifetime Value (Nilai Seumur Hidup/LTV) atau Activity (Aktivitas). Data LTV terkait dengan penginstalan yang terjadi selama rentang tanggal yang ditentukan. Data aktivitas adalah semua event yang terjadi selama rentang tanggal tertentu.

## LTV vs. Aktivitas

Ada dua metode untuk menganalisis  data event  pengguna. Data event terkait dengan tindakan yang dilakukan oleh pengguna pasca instalasi, seperti, pembelian dalam aplikasi, pendaftaran, dan penyelesaian level. Di AppsFlyer data event tersedia dikelompokkan berdasarkan tanggal akuisisi pengguna atau tanggal kronologis event.

* Data yang dikelompokkan berdasarkan tanggal akuisisi pengguna disebut sebagai Lifetime Value/Nilai Seumur Hidup (LTV).
* Data yang dikelompokkan secara kronologis disebut sebagai aktivitas.

Penting untuk memahami apa arti dan di mana data tersebut ditemukan. Perhatikan bahwa Instalasi bukanlah data aktivitas atau data LTV.

#### **Data aktivitas**

* Data aktivitas adalah event yang dilakukan olehpengguna aplikasi aktifselama rentang tanggal yang ditentukan.
* Data aktivitas menunjukkan rincian peristiwa kronologis. Hal ini bermanfaat untuk mengukur kinerja keseluruhan sumber media selama rentang tanggal tertentu.
* Misalnya, gunakan data aktivitas untuk melihat berapa banyak event pembelian yang dilakukan oleh semua pengguna aplikasi selama bulan Januari.
* Gunakan data aktivitas untuk membandingkan perilaku pengguna di bulan berjalan dibandingkan dengan bulan sebelumnya.

#### **Data LTV**

* Data LTV adalah event yang dilakukan selama lifetime pengguna yang menginstalasi aplikasi dalam rentang tanggal tertentu.
* Event yang dilakukan oleh user yang meng-install aplikasi sebelum rentang tanggal yang ditentukan tidak ditampilkan dalam data LTV, meskipun event tersebut terjadi dalam rentang waktu yang ditentukan.
* Misalnya, gunakan data LTV untuk melihat ROI hingga hari ini, dari pengguna yang memasang aplikasi Anda selama bulan Januari.

**Data LTV** adalah alat yang menunjukkan **kualitas pengguna** dari berbagai sumber media. Optimisasi kampanye tergantung pada data LTV.

Pengiklan, memahami bahwa kedua metode tersebut berguna tetapi untuk tujuan berbeda. Untuk alasan ini, keduanya tersedia.

* Data apa yang dapat Anda gunakan untuk membandingkan sumber media?
* Halaman dan laporan mana yang dapat Anda bandingkan di AppsFlyer?
* Bagaimana Anda dapat membandingkan data LTV dan aktivitas?

### Analogi kereta

**Kegiatan** : Bayangkan Anda menyaksikan kereta yang lewat. Saat kereta lewat, Anda hanya melihat tindakan yang dilakukan oleh penumpang di kereta saat mereka lewat. Ini adalah data aktivitas.

<Image alt="activity_data.jpg" src="https://files.readme.io/70a37d5dc16f0817d137f9011be9af5360bd7c4d2469a8abf9430fe69b2671c3-360002436957.jpg" width="400px" />

**LTV**: Sekarang bayangkan, bahwa Anda naik kereta sebagai pengamat. Kereta dibagi menjadi gerbong kereta.

* Anda naik mobil dengan penumpang lain di stasiun keberangkatan. Ini adalah instalasi.
* Selama perjalanan, Anda dapat mengamati semua tindakan yang dilakukan oleh penumpang di dalam mobil. Anda dapat mengamati tindakan semua penumpang di dalam mobil sampai seorang penumpang menaiki kereta, ini adalah penghapusan instalasi.
* Anda tidak dapat melihat tindakan penumpang di gerbong kereta api lain karena mereka naik kereta sebelum atau setelah Anda. Maka ini adalah LTV.

<Image alt="ltv_data.jpg" src="https://files.readme.io/78925644f263b6d5ea5630a09e0b2155d153ce2c4b3060be5c8d7cb9ba0ce4e6-360002436977.jpg" width="400px" />

## Dashboard AppsFlyer — LTV atau aktivitas?

Dashboard memungkinkan pemasar untuk mengoptimalkan lalu lintas non-organik mereka. Sebagian besar dashboard dan laporan di platform berbasis LTV karena pemasar biasanya mengukur kinerja berdasarkan LTV.

Mari kita cari tahu data mana yang merupakan LTV dan mana yang merupakan Aktivitas.

<Accordion title="Dashboard Ikhtisar">

* Tampilan dashboard Ikhtisar adalah LTV.
* Metrik tersedia: Titik sentuh, instal, tingkat konversi, dan pendapatan LTV
* Bagan: Gunakan tren akuisisi, instal, pengguna setia seumur hidup, dan pendapatan seumur hidup

[![](https://files.readme.io/5e9d7025c7d8b3ca11270cabd348cba3ffa166df674548803b84efb4b11ab6ab-115014844503.png)](https://files.readme.io/5e9d7025c7d8b3ca11270cabd348cba3ffa166df674548803b84efb4b11ab6ab-115014844503.png)

Bagian bawah dashboard ikhtisar berisi data acara tambahan, yang juga ada di LTV.

Dalam tabel **Laporan Performa Agregat**, kolom berikut ini adalah semua event yang terkait dengan data LTV:

* Sesi
* Loyal user (jumlah dan tingkat)
* Pendapatan
* ROI
* ARPU
* Uninstall (jumlah dan tingkat)
* Semua kolom in-app event

[![](https://files.readme.io/508f2388e5671fe00181a050a7a7cce1064e3a68470fea1b91b89647c76a9e2d-115014673026.png)](https://files.readme.io/508f2388e5671fe00181a050a7a7cce1064e3a68470fea1b91b89647c76a9e2d-115014673026.png)

Widget **Top Event** juga merupakan data LTV.

</Accordion>

<Accordion title="Dashboard event">

Semua data di halaman ini, baik yang diakses dari widget **Top Event** atau dari link **Event** di bar sebelah kiri, adalah data event LTV. Untuk penjelasan lebih detail tentang Halaman Event, klik sini.

[![](https://files.readme.io/5d144a104c8bb0bdd287e916534f619fc2f8ad76f895803f61b69dc36a581fd2-115014673046.png)](https://files.readme.io/5d144a104c8bb0bdd287e916534f619fc2f8ad76f895803f61b69dc36a581fd2-115014673046.png)

</Accordion>

<Accordion title="Dashboard penargetan ulang">

<Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide#retargeting-dashboard">Dashboard Penargetan Ulang</Anchor>  berfungsi bersama dengan dashboard Ikhtisar. Data event yang ditampilkan adalah  **berbasis LT V** dan berhubungan dengan atribusi ulang dan interaksi ulang yang terjadi selama rentang tanggal.

</Accordion>

<Accordion title="Laporan retensi dan kohort">

Bahkan jika Anda memilih satu hari data retensi, Anda dapat mengambil data sesi beberapa hari atau minggu yang relevan hanya untuk instalasi dari hari itu, yang merupakan KPI yang digunakan untuk kualitas pengguna. LTV klasik. Klik tautan untuk deskripsi Laporan Retensi dan <Anchor target="_blank" href="/marketers/id/docs/cohort-and-retention-dashboard">Laporan Kohort</Anchor> yang lebih rinci.

[![](https://files.readme.io/e72add1e5b77439f0ba744cbf739846e4de8a03f3923dfd9b256c50b526402ae-115014673066.png)](https://files.readme.io/e72add1e5b77439f0ba744cbf739846e4de8a03f3923dfd9b256c50b526402ae-115014673066.png)

Laporan Kohort mirip dengan laporan retensi tetapi memiliki lebih dari metrik sesi. Metrik, seperti pendapatan, sesi, dan in-app event semuanya merupakan LTV.

[![CohortForLTV_us-en.jpg](https://support.appsflyer.com/hc/article_attachments/360008407377/CohortForLTV_us-en.jpg)](https://support.appsflyer.com/hc/article_attachments/360008407377/CohortForLTV_us-en.jpg)

</Accordion>

<Accordion title="Dashboard aktivitas">

Data event di laman <Anchor target="_blank" href="/marketers/id/docs/activity-dashboard">laman Aktivitas</Anchor> didasarkan pada sesi dan pendapatan dan merupakan **basis aktivitas**. Berarti kronologis dan relevan bagi pengguna aplikasi yang aktif selama rentang tanggal yang ditentukan.

[![Activity_us-en.jpg](https://support.appsflyer.com/hc/article_attachments/360008510978/Activity_us-en.jpg)](https://support.appsflyer.com/hc/article_attachments/360008510978/Activity_us-en.jpg)

</Accordion>

<Accordion title="Laporan yang dapat diunduh">

* <Anchor target="_blank" href="/marketers/id/docs/aggregated-and-analytics-reporting-overview">**Laporan kinerja**</Anchor> : Mirip dengan tabel Laporan Kinerja Agregat pada dashboard Ikhtisar, laporan kinerja adalah LTV.
* **<Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">Laporan data lengkap</Anchor>:** Laporan data lengkap adalah sumber utama untuk data aktivitas. Laporan semacam ini seperti instalasi, in-app event, postback, dan uninstal didefinisikan dan diurutkan berdasarkan tanggal aktivitas.

#### Laporan Retargeting

Tersedia laporan penargetan ulang, termasuk laporan kinerja dan data lengkap yang serupa dengan laporan UA. Dalam hal laporan data lengkap, berikut ini tersedia:

* Menargetkan ulang event dalam aplikasi
* Konversi (atribusi ulang, interaksi ulang)

#### Laporan pencegahan kecurangan

Laporan In-App Event yang ditolak adalah data **berbasis aktivitas**.

</Accordion>

<Accordion title="Widget dashboard kustom">

Sehubungan dengan halaman Garis Besar pada dashboard, semua data event pada halaman <Anchor target="_blank" href="/marketers/id/docs/custom-dashboards">Dashboard Kustom</Anchor> adalah data **berbasis LTV**.

[![](https://files.readme.io/c9ee8de9a03e8ed64ec305b6de3ab235f7b1ca6a996478837d4c4d323ed911dc-115014844623.png)](https://files.readme.io/c9ee8de9a03e8ed64ec305b6de3ab235f7b1ca6a996478837d4c4d323ed911dc-115014844623.png)

</Accordion>

<Accordion title="Pivot dan master API">

<Anchor target="_blank" href="/marketers/id/docs/pivot-table-user-metrics">AppsFlyer Pivot</Anchor> didasarkan pada <Anchor target="_blank" href="/marketers/id/docs/master-api-user-acquisition-metrics-via-api">Master API,</Anchor> yang dapat memasok data dari 3 grup data yang berbeda: LTV, Aktivitas, dan Retensi. Saat Anda membuat URL Master API baru atau tampilan Pivot baru, Anda memilih KPI terkait event yang Anda inginkan sebagai LTV, aktivitas, atau keduanya.

</Accordion>

<Accordion title="Dashboard Protect360">

Protect360 memiliki dashboard penginstalan dan in-app event.

Data dashboard penginstalan memberikan berbasis LTV  wawasan tentang penipuan penginstalan, diblokir dalam waktu aktual, dan teridentifikasi pasca-atribusi.   Anda dapat menelusuri untuk memeriksa lebih lanjut event penipuan dengan menggunakan opsi pemfilteran dan pengelompokan.

Data dashboard In-app event (CPA) memberikan wawasan berbasis aktivitas   tentang penipuan in-app event, diblokir secara waktu aktual, dan teridentifikasi pasca-atribusi. Anda dapat menelusuri untuk memeriksa lebih lanjut event penipuan dengan menggunakan opsi pemfilteran dan pengelompokan.

</Accordion>

## Ringkasan sumber data

Tabel berikut merangkum jenis data event yang tersedia pada halaman dan laporan yang berbeda di dashboard AppsFlyer.

| Sumber | LTV | Aktivitas |
| --- | --- | --- |
| Dashboard Ikhtisar | Y | T |
| Dashboard event | Y | T |
| Dashboard penargetan ulang | Y | T |
| Laporan Retensi | Y | T |
| Laporan kohort | Y | T |
| Dashboard aktivitas | T | Y |
| Laporan Performa | Y | T |
| Laporan Data Lengkap | T | Y |
| Laporan Retargeting | Y | Y |
| Laporan pencegahan kecurangan | T | Y |
| Push API | T | Y |
| Master API — KPI kinerja kampanye | Y | Y |
| Tabel Pivot | Y | Y |
| Penginstalan Protect360 | Y | T |
| In-app event Protect360 | T | Y |

### Menggunakan tabel sumber data

Jika Anda ingin membandingkan data dari berbagai bagian platform, pastikan gunakan laporan yang berbasis LTE atau berbasis aktivitas

## Membandingkan sumber data

### Membandingkan data AppsFlyer dengan sumber data eksternal

**Sebagian besar dari sumber data** termasuk **data aktivitas layar** Google dan Apple, bukan merupakan data LTV.

Oleh karena itu, **untuk membandingkan data sumber eksternal dengan data AppsFlyer, Anda biasanya akan menggunakan data aktivitas AppsFlyer,** yang tersedia di laporan data lengkap.

Perlu diketahui bahwa Facebook menawarkan data LTV parsial, terbatas hingga 28 hari setelah install.

### Membandingkan data LTV dan aktivitas di dashboard AppsFlyer

Ada dua perbedaan antara data LTV dan aktivitas saat melihat pada rentang tanggal yang sama. Perbedaannya adalah:

* Data aktivitas mencakup event dari **install yang terjadi sebelum**rentang tanggal.
* Data LTV mencakup **event yang terjadi setelah** rentang tanggal.

Untuk dapat membandingkan dua jenis data dengan benar, kita perlu menetralkan perbedaan. Hal ini dapat dicapai dengan mengambil data LTV dari data aktivitas atau sebaliknya.

> 📘 **Catatan**
>
> Perbedaan kecil antara sumber yang sama masih memungkinkan karena perbedaan waktu pembuatan laporan.

### Mengambil data LTV dari data aktivitas lengkap

1. Buka laman **Export Data (Ekspor Data)**
2. Atur **hari ini sebagai hari terakhir** rentang tanggal (perbedaan 2 terselesaikan)
3. Unduh laporan in-app event lengkap
4. Gunakan kolom **Install Time** untuk memfilter install sebelum hari pertama rentang tanggal (perbedaan A teratasi).

> 📘 **Catatan**
>
> Sementara data aktivitas tetap konstan dari waktu ke waktu, data LTV berubah ketika user yang ada melakukan in-app event baru. Data LTV yang Anda lihat hari ini mungkin berbeda dengan yang Anda lihat besok untuk rentang tanggal yang sama.

### Mengambil data aktivitas dari data LTV

Untuk membandingkan halaman garis besar berbasis LTV dengan sumber eksternal, yang berbasis aktivitas, Anda harus mengatasi dua perbedaan.

Anda hanya dapat melakukan ini dengan:

1. **Memilih sumber yang mulai mengirimkan install dalam rentang tanggal yang ditentukan pada AppsFlyer** (perbedaan 1 teratasi).  
    Hal ini memastikan data aktivitas tidak menyertakan event yang dilakukan dalam rentang tanggal yang merupakan bagian dari install yang terjadi sebelum rentang tanggal tersebut.
2. **Mengatur hari ini sebagai hari terakhir rentang tanggal** (perbedaan 2 teratasi).  
    Hal ini memastikan data LTV tidak menyertakan event yang dilakukan setelah rentang tanggal yang merupakan bagian dari install yang terjadi dalam rentang tanggal tersebut.

## Kesimpulan

Saat membandingkan dua sumber data, baik keduanya atau hanya salah satunya ada di AppsFlyer, pastikan untuk membandingkan data aktivitas dengan data aktivitas, dan LTV dengan LTV.