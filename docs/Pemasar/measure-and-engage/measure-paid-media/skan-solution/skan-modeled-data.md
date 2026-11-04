---
title: Data yang dimodelkan SKAN
metadata:
  keywords:
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2022-06-23T12:02:02Z'
  edited_at: '2023-10-26T14:41:17Z'
  id: 7086372479505
  locale: id
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/id/articles/7086372479505
---
> **Sekilas**: Model AppsFlyer mengumpulkan data yang tidak dapat disediakan oleh pelaporan SKAdNetwork dasar.

## Overview

Pelaporan SKAdNetwork (SKAN) dapat dibatasi karena:

* SKAN bergantung pada nilai konversi (CV) yang dibatasi hingga 6 bit, menghasilkan 64 kemungkinan nilai (0-63).
* Apple terkadang menahan CV yang sebenarnya (dan mengembalikan data sebagai "null") untuk menjaga privasi pengguna.
* Data hanya tersedia dari dalam jendela aktivitas antara 12-72 jam dan nilai umur penuh (LTV) tidak diketahui.

Data model SKAN memecahkan masalah ini:

* AppsFlyer menggunakan pembelajaran mesin, statistik Bayesian, data yang dilaporkan AppsFlyer, dan data SKAN untuk memodelkan titik data tersembunyi.
* Pemasang iklan mendapatkan gambaran yang lebih lengkap terkait performa LTV aplikasi dan kampanye

**Catatan**: Saat Anda mengubah skema nilai konversi, perlu waktu 2 hari agar data sesuai model tersedia.

<div id="inapp-event-ltv" />

<div id="modeled-data-types-and-availability" />

## Jenis dan ketersediaan data yang dimodelkan

| Jenis data | Ketersediaan | Catatan |
| --- | --- | --- |
| Nilai konversi null | <ul><li>Dasbor Ikhtisar Single Source of Truth</li><li>Dashboard SKAN:</li><li>API laporan kinerja gabungan SKAN</li><li>API tanggal kedatangan postback gabungan SKAN</li></ul> |  |
| LTV Pendapatan | Dasbor Ikhtisar Single Source of Truth | Pemodelan LTV pendapatan saat ini dibatasi hingga 7 hari |
| Geo | Dasbor Ikhtisar Single Source of Truth |  |

<div id="null-conversion-values" />

<Accordion title="Nilai konversi null">

Terkadang nilai konversi (CV) memiliki nilai null karena Apple menahan CV yang sebenarnya untuk menjaga privasi pengguna. Di AppsFlyer, CV null dihitung sebagai penginstalan. Pertimbangkan:

* Null dan nol memiliki arti yang berbeda:
  * Nol: Pengguna memasang aplikasi tetapi tidak melakukan tindakan terukur apa pun selama jendela aktivitas. Akibatnya, metriknya akurat dan tidak dimodelkan.
  * Null: Kita tidak tahu apa yang dilakukan pengguna; Apple menahan CV.
* CV null dapat mendistorsi metrik kinerja Anda. Untuk mengatasi distorsi dan memberikan ukuran performa aplikasi yang lebih benar, nilai konversi null dimodelkan ke nilai konversi antara 0-63.

Nilai konversi sesuai model:

* Gunakan distribusi penginstalan SKAN dengan nilai konversi untuk memodelkan penginstalan null. Algoritma yang digunakan untuk memodelkan data bersifat dinamis dan memperhitungkan beberapa variabel. Lihat contoh berikut tentang cara kerjanya:
  * Ada 100 penginstalan, 60 null, 10 dengan CV=1, 5 dengan CV=3, dan 25 dengan CV=5.
  * Artinya, dari 40 penginstalan dengan nilai konversi, 25% memiliki CV=1, 12,5% memiliki CV=3, dan 62,5% memiliki CV=5.
  * 60 penginstalan null mendapatkan distribusi model yang sama: 15 mendapatkan CV=1, 7 mendapatkan CV=3, dan 38 mendapatkan CV=5.
* Termasuk dalam dashboard SKAN dan metrik API. Metrik asli yang tidak diubah, yang tidak menyertakan data sesuai model, tersedia bersama metrik ini dan ditandai sebagai *tidak sesuai model*.
* Gunakan data dari tingkat granularitas berikut ini: Aplikasi, sumber media, kampanye, dan adset. Jika data yang dimodelkan menggunakan level tersebut tidak tersedia, nilai T/A akan ditampilkan.

Metrik sesuai model tersedia berdasarkan nilai konversi:

* Pendapatan
* Jumlah terjadinya event
* eCPA
* ARPU
* ROI
* ROAS

</Accordion>

<div id="revenue-ltv" />

<Accordion title="LTV Pendapatan">

[![modeled_d7.png](https://files.readme.io/ec175800b52164844c56743a33fe412eef02c3b76975ca572819535bb5e5eff9-12183780248081.png)](https://files.readme.io/ec175800b52164844c56743a33fe412eef02c3b76975ca572819535bb5e5eff9-12183780248081.png)

Pelaporan SKAN sendiri hanya dapat memberikan pendapatan berdasarkan jendela pengukuran SKAN dan konfigurasi CV untuk pendapatan di Studio Konversi. Pemodelan SKAN mampu memodelkan pendapatan hingga 7 hari (168 jam) setelah penginstalan.

**Manfaat**:

Untuk SKAN versi 3 dan sebelumnya, data yang dimodelkan melampaui jangka waktu jendela aktivitas.

Untuk SKAN versi 4+:

* Kesegaran data: LTV Pendapatan tersedia sebelum postback SKAN kedua tiba (penundaan postback adalah antara 24-144 jam).
* Ukur lebih banyak: Anda dapat menggunakan konfigurasi nilai kasar dari postback kedua dan ketiga untuk metrik lainnya, seperti event dan retensi, dan tetap mendapatkan data LTV pendapatan melalui pemodelan.
* Pengayaan data: Jika Anda menggunakan postback kedua untuk mengukur pendapatan, data dari postback digunakan untuk meningkatkan model data LTV pendapatan dan memberikan data pendapatan pada tingkat yang lebih terperinci daripada 3 level yang disediakan oleh postback.

**Pertimbangan**:

* Metrik LTV pendapatan ditampilkan untuk aplikasi dengan konfigurasi pendapatan di SKAN Conversion Studio, untuk pendapatan yang berasal dari pembelian dalam aplikasi dan pendapatan iklan.
* LTV pendapatan memerlukan setidaknya 14 hari data pendapatan. Artinya, jika Anda mengonfigurasi Pendapatan keseluruhan pada 1 November 2022, tanggal penginstalan pertama yang menyediakan data sesuai model adalah 14 November 2022. Data ditampilkan 8 hari setelah itu (22 November 2022).
* LTV Pendapatan (saat ini dibatasi hingga 7 hari) dan metrik turunan lainnya tersedia di dashboard SSOT (di widget, bagan, dan tabel) pada hari ke-8 setelah penginstalan sebagai berikut:
  * Pendapatan D7
  * ARPU D7
  * Laba kotor D7
  * ROI D7
  * ROAS D7

</Accordion>

<div id="geo" />

<Accordion title="Geo">

Postback SKAN tidak menyertakan dimensi geo.Oleh karena itu, data SKAN tidak dapat dikelompokkan berdasarkan geo hanya dengan menggunakan postback SKAN. Namun, AppsFlyer dapat memodelkan geo instalasi SKAN untuk memberikan dimensi geo dan pengelompokan untuk data SKAN.

Geo yang dimodelkan:

* Gunakan alat pembelajaran mesin yang mempertimbangkan distribusi geo untuk penginstalan kampanye yang diatribusikan melalui metode AppsFlyer lainnya.
* Tersedia melalui dimensi Geo di dashboard SSOT.  
  **Catatan**: Jika Anda mengelompokkan data dengan metode Geo\ dan Pengaitan, Anda dapat melihat data untuk setiap pemisahan geo antara model AF dan keunikan SKAN. Keunikan SKAN dimodelkan.

Pertimbangan:

* Keakuratan pemodelan geo AppsFlyer adalah sekitar 90%. Jika geo tidak dapat dimodelkan, penginstalan SKAN dikelompokkan di dalam Tidak Ada. Tidak Ada berarti geo tidak diketahui.

</Accordion>

<div data-zendesk-anchors="01H8TZR38AC6P264CGF4PX4SJ5=overview modeled-data-types-and-availability=jenis-dan-ketersediaan-data-yang-dimodelkan 01H8TZR38A2V9ZSSGKHF3XCX0P=jenis-dan-ketersediaan-data-yang-dimodelkan 01H8TZR38A4RDX42B7J5X9SPMQ=null-conversion-values 01H8TZR38BG9XEM2FTJADJ27VK=revenue-ltv 01H8TZR38BSFVDSQCH915ACSYH=geo" />
