---
title: ROI360—data biaya dan pendapatan
metadata:
  keywords:
    - cost
    - Advertisers
    - Premium
    - Marketers
    - revenue
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-11-10T13:52:03Z'
  edited_at: '2023-04-02T14:40:09Z'
  id: 10515748254609
  locale: id
  section: Overview
  section_id: 15173289016593
  url: https://support.appsflyer.com/hc/id/articles/10515748254609
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Sekilas**: Dapatkan data biaya dan pendapatan untuk memahami total ROI dan ROAS Anda.

<Image align="center" alt="M_emptyState.png" src="https://files.readme.io/5eec5be77bf0b72afdd95b1957642cc67ba509000bc756ac68d87da5e96ed08e-11832563913489.png" />

<div id="overview" />

## Ringkasan

ROI360 adalah rangkaian alat pelaporan biaya dan pendapatan unik yang memberikan Anda data paling akurat, secepat mungkin.

Dengan menggabungkan analisis biaya dan pendapatan, Anda mendapatkan gambaran lengkap tentang laba atas belanja iklan (ROAS) dan laba atas investasi (ROI).

<div id="cost-tools" />

### Alat biaya

Sebelumnya dikenal sebagai Xpend, alat biaya ROI360 menggabungkan dan melaporkan data biaya. Rangkaian lengkap alat dan fitur biaya diuraikan dalam tabel berikut. Klik tautan untuk mempelajari lebih lanjut tentang setiap fitur.

<table><thead><tr><th>Alat</th><th>Deskripsi</th></tr></thead><tbody><tr><td><a href="./roi360-cost-aggregation-overview" target="_blank">Biaya yang dikaitkan</a></td><td><p><span>Data biaya terkait dengan atribusi, klik, dan tayangan pada tingkat paling terperinci yang tersedia.</span></p><p><span>Hal ini termasuk akes ke lebih dari 80 integrasi API, yang membuat Anda dapat terhubung secara mudah ke jaringan iklan global atau lokal.</span></p></td></tr><tr><td><a href="./import-cost-data" target="_blank">Penyerapan file</a></td><td><p><span>Penyerapan pembelanjaan iklan untuk mencatat data biaya yang tidak diterima lewat API.</span></p></td></tr><tr><td><a href="./incorporate-agency-fees-into-campaign-costs" target="_blank">Biaya agensi</a></td><td><p><span>Kalkulasi biaya agensi dimasukkan ke dalam biaya Anda.</span></p></td></tr><tr><td><a href="./set-up-and-use-roi360-cost-etl-reports" target="_blank">Biaya ETL\*</a></td><td><span>Mengirimkan data biaya kampanye, diperbarui 4 kali sehari ke AWS S3 atau bucket GCS siap untuk dimuat ke sistem BI pemasang iklan.</span></td></tr><tr><td colspan="2"><span>\* Tersedia dengan paket lanjutan ROI360</span></td></tr></tbody></table>

**Catatan**: Anda juga dapat menggabungkan <Anchor target="_blank" href="/marketers/id/docs/view-aggregated-cost-data-for-attribution-links">data biaya dengan mengeklik</Anchor> tanpa ROI360. Akan tetapi, metode ini hanya untuk model biaya CPI, bukan untuk model lain, seperti CPA, CPC, dan CPM.

<div id="revenue-tools" />

### Alat pendapatan

Alat pendapatan ROI360 menggabungkan dan melaporkan data pendapatan, dengan mempertimbangkan pembelian dalam aplikasi, langganan, dan pendapatan iklan. Pajak dan komisi app store juga dimasukkan ke metrik pendapatan. Rangkaian lengkap alat dan fitur pendapatan diuraikan di tabel berikut. Klik tautan untuk belajar lebih banyak tentang setiap fitur.

<table><thead><tr><th>Alat</th><th>Deskripsi</th></tr></thead><tbody><tr><td>Pembelian dalam aplikasi</td><td><p><span>Laporan otomatis dari pembelian dalam aplikasi yang divalidasi, termasuk data untuk transaksi lanjutan, seperti pengembalian dana atau pembatalan.</span></p></td></tr><tr><td>Pendapatan langganan</td><td><p><span>Pelaporan otomatis untuk langganan, termasuk perubahan, pembatalan, dan untuk berbagi dengan keluarga.</span></p></td></tr><tr><td><a href="./roi360-guide-ad-revenue-attribution" target="_blank">Pendapatan Iklan</a></td><td><p>Akses ke lebih dari 20 mitra pendapatan iklan yang terhubung lewat API atau SDK yang menyediakan akurasi tingkat tinggi dan kesegaran data.</p></td></tr><tr><td>[Segera hadir] Pendapatan ETL\*</td><td><span>Mengirimkan data pendapatan ke AWS S3 atau bucket GCS Anda yang siap dimuat ke sistem BI pemasang iklan.</span></td></tr><tr><td colspan="2"><span>\* Tersedia dengan paket lanjutan ROI360</span></td></tr></tbody></table>

**Catatan**: Ada juga alat pengukuran pendapatan dasar yang tidak dimasukkan dalam ROI360. Tidak seperti alat yang termasuk dalam ROI 360, alat-alat ini membutuhkan banyak konfigurasi oleh programmer Anda:

* <Anchor target="_blank" href="/marketers/id/docs/legacy-receipt-validation-for-in-app-purchases">Validasi tanda terima pembelian dalam aplikasi</Anchor>
* Pengukuran pendapatan langganan
* <Anchor target="_blank" href="/marketers/id/docs/roi360-revenue-attribution-overview">Pencatatan pendapatan lewat in-app event yang disesuaikan</Anchor>

<div data-zendesk-anchors="overview=ringkasan cost-tools=alat-biaya revenue-tools=alat-pendapatan" />
