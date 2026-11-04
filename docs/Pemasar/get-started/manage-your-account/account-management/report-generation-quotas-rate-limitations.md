---
title: Kuota pembuatan laporan (batasan tarif)
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2014-05-01T12:55:30Z'
  edited_at: '2023-11-03T08:08:29Z'
  id: 207034366
  locale: id
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/id/articles/207034366
---
> **Sekilas:** Mekanisme kuota (batasan tarif) membatasi jumlah laporan yang dapat dihasilkan per hari oleh Pull API dan halaman ekspor data.

<div id="rate-limits-for-reports" />

## Batas tarif untuk laporan

Kuota membatasi jumlah laporan yang dapat dihasilkan per hari per jenis laporan. Kuota bervariasi sesuai dengan paket langganan Anda.

**Prinsip-prinsip:**

* **Agensi**: Laporan Pull API yang dibuat oleh agensi dihitung sebagai bagian dari kuota pemasang iklan untuk laporan Pull API. Jika Anda sering mencapai batas kuota, hubungi Account Executive Anda. Untuk laporan dari halaman data ekspor, agensi dan pemasang iklan memiliki kuota terpisah.
* **Jaringan iklan**: Laporan yang dihasilkan oleh jaringan iklan tidak dihitung sebagai bagian dari kuota pemasang iklan.
* **Hari**: Kuota adalah per hari kalender mulai pukul 00.00 UTC

<div id="aggregated-and-analytics-reports" />

### Laporan gabungan dan analitik

| Alat pengiriman data | Kuota |
| --- | --- |
| Gabungan Pull API | <ul><li>Hingga 2 hari dalam rentang tanggal:<ul><li>Maksimal 1 panggilan per menit per aplikasi per laporan</li></ul></li><li>Rentang tanggal 3+ hari, panggilan dibatasi sebagai berikut:<ul><li>Maksimal 120 panggilan per hari, per akun</li><li>24 panggilan per hari, per aplikasi</li></ul></li></ul> |
| Halaman data ekspor gabungan | Tidak terbatas |
| Master API | Tidak terbatas |
| API Kelompok | 60 panggilan per menit per akun |
| Laporan gabungan SKAN | 10 panggilan per menit per akun |

<div id="raw-data" />

### Data Lengkap

* Kuota terpisah berlaku untuk setiap alat pelaporan, yaitu Pull API dan halaman ekspor data lengkap.
* Untuk Pull API, laporan yang dibuat oleh agensi dihitung sebagai bagian dari kuota pemasang iklan. Untuk laporan dari halaman data ekspor, agensi dan pemasang iklan memiliki kuota terpisah.
* Kuota penarikan API diterapkan per:
  * Laporan
  * Hari
  * Tingkat aplikasi
  * Tingkat akun
* Untuk pemasang iklan, kuota bergantung pada langganan AppsFlyer Anda. **Catatan**: Kuota juga berlaku untuk laporan yang membutuhkan langganan premium.
* Laporan yang dihasilkan agensi dapat mengurangi kuota pemasang iklan.
* Kuota harian jaringan iklan seperti yang ditunjukkan pada tabel berikut.

Untuk kemudahan pemahaman, lihat FAQ yang mengikuti tabel.

<div id="ad-network-postback-reports-daily-quota" />

#### Kuota harian data lengkap jaringan iklan

| Grup | Jenis laporan  <br />(setiap jenis laporan memiliki kuota terpisah) | Kuota tingkat aplikasi | Kuota tingkat akun |
| --- | --- | --- | --- |
| Atribusi | <ul><li>Organic installs (Instalasi organik)</li><li>Install Non-Organik</li><li>Konversi penargetan ulang</li><li>mencopot pemasangan</li><li>Pendapatan iklan teratribusi</li><li>Pendapatan iklan organik</li><li>Pendapatan iklan penargetan ulang</li></ul> | 24 | Tak dapat diterapkan |
| In-App Event | <ul><li>Organic installs (Instalasi organik)</li><li>Install Non-Organik</li><li>Konversi penargetan ulang</li><li>mencopot pemasangan</li></ul> | 12 | Tak dapat diterapkan |

<div id="faq" />

#### **Pertanyaan Umum**

* P: Untuk aplikasi tertentu, dapatkah saya membuat 24 laporan penginstalan organik menggunakan Pull API dan 24 laporan lainnya menggunakan halaman ekspor data lengkap?  
  J: Ya. Kuota per alat pelaporan terpisah.
* P: Untuk aplikasi tertentu, dengan menggunakan halaman ekspor data lengkap, dapatkah saya membuat 24 laporan penginstalan organik, 24 laporan penginstalan non-organik, dan 24 laporan konversi penargetan ulang?  
  J: Ya. Kuota per jenis laporan terpisah.
* P: Saya memiliki 25 aplikasi di akun saya. Dapatkah saya membuat 10 laporan penginstalan organik untuk setiap aplikasi?  
  J: Tidak. Ini menghasilkan total 250 laporan yang melebihi kuota tingkat akun sebesar 120.

<div id="see-also" />

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/data-availability-windows">Periode waktu ketersediaan data</Anchor>

<div data-zendesk-anchors="rate-limits-for-reports=batas-tarif-untuk-laporan h_01H9JNZFPSVXPKMEVR1ZR6PSYG=batas-tarif-untuk-laporan aggregated-and-analytics-reports=laporan-gabungan-dan-analitik h_01H9JNZFPS62A5CFWSXVPN8XM5=laporan-gabungan-dan-analitik raw-data=data-lengkap h_01H9JNZFPSPYWBB2MCZV2R2KX1=data-lengkap ad-network-raw-data-daily-quota=kuota-harian-data-lengkap-jaringan-iklan h_01H9JNZFPSYXZNW81BZTRDS576=kuota-harian-data-lengkap-jaringan-iklan faq=pertanyaan-umum h_01H9JNZFPT76RAV8JBTY2K75V4=pertanyaan-umum h_01HE7SW3VWRNVY1WFB4YCSAVY6=lihat-juga" />
