---
title: Optimisasi Materi Iklan—pelaporan ETL
metadata:
  keywords:
    - Premium
    - Marketers
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2023-10-10T14:33:17Z'
  edited_at: '2023-12-11T08:22:13Z'
  id: 19253873174801
  locale: id
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/id/articles/19253873174801
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Sekilas:** Gunakan Data Locker untuk mengalirkan laporan Optimisasi Materi Iklan secara otomatis dan terus-menerus ke penyimpanan cloud untuk pemuatan terprogram dan efisien ke dalam sistem BI Anda.

## Tentang Optimisasi Materi Iklan ETL

Creative Optimization Extract Transform Load (Muatan Transformasi Ekstrak Optimisasi Materi Iklan/ETL) melengkapi analis data Anda dengan semua informasi yang mereka perlukan untuk analisis kinerja materi iklan. Hal ini dicapai dengan mengalirkan laporan Optimisasi Materi Iklan secara otomatis ke penyimpanan cloud untuk dimuat secara terprogram ke dalam sistem BI Anda.

Pelaporan kinerja tingkat aset lengkap disediakan, termasuk semua indikator kinerja utama (KPI), KPI corong atas dan bawah, data atribusi, dan data aset materi iklan.

Optimisasi Materi Iklan ETL menggunakan <Anchor target="_blank" href="/marketers/id/docs/data-locker-for-marketers">Data Locker</Anchor> untuk mengirimkan data pelaporan Optimisasi Materi Iklan Anda ke penyimpanan cloud. Anda dapat memilih dari berbagai tujuan penyimpanan, seperti bucket milik AppsFlyer di Amazon Web Services (AWS) atau penyimpanan Anda sendiri di AWS, GCS, Yandex, BigQuery, Snowflake, dan banyak lagi. Data Locker mendukung banyak tujuan, yang berarti Anda dapat mengirim semua data ke satu atau beberapa tujuan, mengirim data spesifik ke tujuan tertentu, dan menyesuaikan pengiriman data sesuai kebutuhan Anda. Creative Optimization ETL **tersedia dengan paket berlangganan Creative Optimization Premium.**

## Memulai

Bagian ini menjelaskan cara menyiapkan Data Locker untuk pelaporan Pengoptimalan Materi Iklan.

<div id="set-up-data-locker" />

<Accordion title="Atur Data Locker">

Pertama, Anda harus berlangganan paket Creative Optimization Premium dan Data Locker melalui AppsFlyer CSM Anda. Setelah berlangganan, Anda kemudian dapat mengatur Data Locker.

**Untuk mengatur Data Locker:**

1. Ikuti <Anchor target="_blank" href="/marketers/id/docs/data-locker-for-marketers#set-up-data-locker">instruksi</Anchor> berikut.

2. Saat mengatyr Data Locker, pilih **Materi Iklan** (di bawah **Pilih laporan**), di halaman konfigurasi Data Locker.

![Data Locker - pilih Creative.jpg](https://files.readme.io/bd1528ac5419f1bbf033a4a96c028f5a1bf7ff798c452371ac906ea650255d31-19276693230353.jpg)

</Accordion>

<div id="edit-data-locker-configuration" />

<Accordion title="Edit konfigurasi Data Locker">

Bagian ini menjelaskan cara mengedit konfigurasi Data Locker yang sudah ada untuk menambahkan pelaporan Optimisasi  Materi Iklan.

**Untuk menambahkan pelaporan Optimisasi Materi Iklan ke Data Locker:**

1. Dari **Integrasi** di menu samping utama AppsFlyer, klik **Data Locker**.

<Image alt="dari Integrasi pilih Data Locker.jpg" src="https://files.readme.io/797989d738fddcce1de7a45a98e13b898d53817c285c839ff1fbb5a92522ccf0-19284078965009.jpg" width="200px" />

2. Pilih **Materi Iklan** (di bawah **Pilih laporan**) di halaman konfigurasi Data Locker.

![Data Locker - pilih Creative.jpg](https://files.readme.io/bd1528ac5419f1bbf033a4a96c028f5a1bf7ff798c452371ac906ea650255d31-19276693230353.jpg)

</Accordion>

## Data

Bagian ini menjelaskan ketersediaan data di ETL Pengoptimalan Kreatif.

<div id="data-freshness" />

<Accordion title="Keaktualan data">

Setelah dikonfigurasi, laporan Optimisasi  Materi Iklan dialirkan ke Data Locker setiap hari, menyediakan data selama 30 hari terakhir. Ekspor data akan tersedia setiap hari pada UTC + 12. <Anchor target="_blank" href="/marketers/id/docs/data-locker-advertiser-reports#data-freshness-explanations">Pelajari lebih lanjut</Anchor>

</Accordion>

<div id="available-data" />

<Accordion title="Data yang tersedia">

Data Materi Iklan berikut tersedia di Data Locker.

| Bidang | Jenis |
| --- | --- |
| date | string |
| asset\_link | string |
| creative | string |
| media\_source | string |
| campaign | string |
| campaign\_id | string |
| ad | string |
| ad\_id | string |
| adset | string |
| adset\_id | string |
| app\_name | string |
| app\_id | string |
| creative\_first\_seen | string |
| creative\_type | string |
| duration | string |
| end\_card\_type | string |
| geo | string |
| platform | string |
| orientation | string |
| resolution | string |
| impressions | string |
| clicks | string |
| installs | string |
| ctr | string |
| cvr | string |
| ipm | string |
| cost | string |
| ecpi | string |
| reattributions | string |
| reengagements | string |
| cpm | string |
| roas\_d1 | string |
| roas\_d7 | string |
| roas\_d14 | string |
| roas\_d30 | string |
| roas\_d60 | string |
| roas\_d90 | string |
| retention\_d1 | string |
| retention\_d7 | string |
| retention\_d14 | string |
| retention\_d30 | string |
| retention\_d60 | string |
| retention\_d90 | string |
| revenue\_d1 | string |
| revenue\_d14 | string |
| revenue\_d30 | string |
| revenue\_d60 | string |
| revenue\_d7 | string |
| Revenue\_d90 | string |
| partner\_cpm | string |
| partner\_ctr | string |
| partner\_cvr | string |
| partner\_clicks | string |
| partner\_cost | string |
| partner\_ipm | string |
| partner\_impressions | string |
| partner\_installs | string |
| partner\_ecpi | string |
| partner\_ecpi | string |

> 📘 **Catatan**
>
> **Data berikut tidak tersedia:**
>
> * Dimensi khusus
> * Metrik khusus
> * In-app event
> * Data AI (elemen dan adegan)
> * Menargetkan ulang data

</Accordion>

<div data-zendesk-anchors="about-creative-etl=tentang-optimisasi-materi-iklan-etl h_01HCF5ZDDGTN52MZ9DX2MDKJV7=tentang-optimisasi-materi-iklan-etl get-started=memulai h_01HCF65RS2NKHEDHFE9TN78ES8=memulai h_01HCFF8BWHGFX5KEZWKVDYXKKA=set-up-data-locker h_01HCFF8BWJCQHNN17N8G555FP9=edit-data-locker-configuration h_01HCF8C8S392WJMYYHV6ECMNCW=data h_01HCFC87EDDD3X0ZXNCAQAHTZB=data-freshness h_01HCFBYBBMNZ52TH4M3G3YB3YM=available-data h_01HF44ZFSHJ8MX9ZNBF7SWB5JN=catatan" />
