---
title: data teragregasi Pull API
metadata:
  keywords:
    - Performance
    - raw data
    - Pull API
    - Reports
    - API
    - Parameters
    - API Policy
    - Advertisers
    - facebook rawdata
    - facebook raw data
    - Developers
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2013-04-24T15:08:25Z'
  edited_at: '2023-10-31T03:07:17Z'
  id: 207034346
  locale: id
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/id/articles/207034346
---
> **Sekilas:** Gunakan Pull API ini untuk mendapatkan laporan agregat AppsFlyer Anda dalam file CSV.

[![PullAPIAverage_us-en.png](https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png)](https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png)

> 👍 **Mencari data lengkap API Pull?**
>
> Pelajari semuanya di <Anchor target="_blank" href="/marketers/id/docs/pull-api-raw-data">sini</Anchor>.

## data teragregasi Pull API

* Pull API memungkinkan Anda mendapatkan laporan data gabungan untuk akuisisi pengguna (UA) dan penargetan ulang dalam file CSV.
* <Anchor target="_blank" href="/marketers/id/docs/about-data-freshness-and-timezone-support#data-freshness-rates-and-timezone-support">Tingkat keaktualan data</Anchor> sama dengan laporan yang setara di halaman Ekspor Data dan halaman dasbor Ikhtisar. Pertimbangkan bahwa biaya dapat diperbarui dengan penundaan selama beberapa jam, bergantung pada mitra yang menyediakan data biaya.
* Filter menurut opsi yang tersedia: Sumber media dan rentang tanggal.
* Keunggulan tambahan dalam Pull API adalah:
  * Tambahkan jenis sentuh atribusi
  * Pilih zona waktu

#### Laporan kinerja agregat tersedia melalui Pull API

<table><tbody><tr><th>ketegori</th><th> UA</th><th>Penargetan Ulang\*</th></tr><tr><td>Partners (media source)</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>Partners by date</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>Harian</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>Geo</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>Lokasi Berdasarkan Laporan Tanggal</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="3"><p>\* Untuk laporan penargetan ulang, tambahkan <code><span>&amp;reattr=true</span></code> ke URI. </p></td></tr></tbody></table>

<div id="using-pull-api-aggregate-data" />

<Accordion title="Menggunakan data agregat Pull API">

**Untuk menggunakan data agregat Pull API** :

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/5dd980a707877c2ab26826170f7f1313bffba1fed8ab3eacb59954770c302932-19754884868369.png) Dapatkan token API. Admin perlu mengambil token.
2. Berikan token API kepada pengembang Anda untuk digunakan di header autentikasi.
3. Beri programmer Anda [parameter](/docs/pull-api-aggregate-data#parameters) untuk diinput saat mereka melakukan panggilan API, seperti yang dijelaskan di bagian berikut. Parameter menentukan fokus laporan dan cara pengaturannya serta memberikan jangka waktu pelaporan.
4. Beri tahu pengembang Anda untuk mengikuti <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-11">petunjuk data agregat Pull API</Anchor> mereka di hub pengembang.

</Accordion>

<div id="parameters" />

<Accordion title="Parameter">

| Parameter | Deskripsi |
| --- | --- |
| app\_id | ID aplikasi |
| from | <ul><li>Rentang data terdiri dari `dari parameter`dan `to` . Rentang adalah rentang tanggal LTV (instalasi).</li><li>Format: `yyyy-mm-dd`,</li><li>Contoh: 01-01-2010</li></ul> |
| ke | Tanggal selesai. Seperti untuk `dari` |
| media\_source | Gunakan untuk membatasi (filter) ke sumber media tertentu.<ul><li>Contoh: `media_source=facebook`</li></ul> |
| attribution\_touch\_type | Atur parameter ini seperti yang ditunjukkan pada contoh untuk mendapatkan [atribusi lihat-tayang](/docs/pull-api-aggregate-data) (VTA) KPI.<br /><br />Contoh:  `attribution_touch_type=impression`<br /><br />Beberapa VTA KPI, seperti klik, tayangan iklan, dan API biaya, tidak memiliki nilai terkait dengannya dan menampilkan nilai N/A. |
| currency | Mata uang pendapatan dan biaya<br /><br />Laporan Pull API agregat selalu menggunakan mata uang khusus aplikasi. |
| atribusi ulang | Dapatkan data konversi penargetan ulang.<ul><li>[Default] Jika salah, kampanye data akuisisi pengguna (UA) kembali.</li><li>Jika benar, penargetan ulang konversi akan menghasilkan.</li><li>**Contoh**:`reattr=true`</li></ul> |
| zona waktu | [Default] Data kembali menggunakan UTC.<ul><li>Templat URI diisi dengan parameter zona waktu yang diatur ke zona waktu khusus aplikasi.</li><li>[Default] Jika parameter tidak dikirim, data kembali menggunakan.</li><li>Jika Anda mengirim `timezone=[Joda-Time]`, data akan dikembalikan menggunakan zona waktu khusus aplikasi.</li></ul>Catatan tentang pemilihan zona waktu<ul><li>Format zona waktu Joda-Time memperhitungkan waktu musim panas.</li><li>Nilai Waktu Joda harus identik dengan nilai di halaman pengaturan aplikasi. Contohnya, jika pengaturan zona waktunya adalah paris, nilai zona waktu di URL Pull API harus `timezone=Europe%2fParis`.</li><li>Menarik data di zona waktu yang dipilih hanya tersedia dari tanggal saat pengaturan zona waktu dibuat. Data apa pun sebelum tanggal perubahan menggunakan YTC sebagai zona waktu.</li></ul> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Sifat | Komentar |
| --- | --- |
| Jenis token API diperlukan | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/5dd980a707877c2ab26826170f7f1313bffba1fed8ab3eacb59954770c302932-19754884868369.png)<Anchor target="_blank" href="/marketers/id/docs/managing-appsflyer-tokens">Token V2.0</Anchor> |
| Akses jaringan iklan | N |
| Akses agensi | Y |
| Transparansi agensi | Y |
| Mata uang khusus aplikasi | Y |
| Zona waktu khusus aplikasi | Y |
| Biaya | Data biaya hanya untuk kampanye UA; bukan untuk penargetan ulang atau kampanye tidak aktif (kampanye tanpa penginstalan apa pun). |
| Kesegaran data | <Anchor target="_blank" href="/marketers/id/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">Berkelanjutan</Anchor> |
| Data historis | 5 tahun |
| Data non-organik | Y |
| Data organik | Y |
| Batasan tingkat | <Anchor target="_blank" href="/marketers/id/docs/report-generation-quotas-rate-limitations">Batasan</Anchor> |
| Keterbatasan ukuran | <ul><li>Maksimal pengembalian panggilan API 200 ribu baris.</li><li>Jika laporan memiliki tepat 200 ribu baris, maka anggaplah baris tidak ada.</li><li>Lakukan beberapa panggilan API, menggunakan parameter dari/hingga yang mencakup waktu dalam satu hari.</li></ul>Perhatikan! Pull API untuk data lengkap mendukung 1 juta baris. Laporan data gabungan dibatasi hingga 200 ribu baris. |
| Perubahan nama kampanye | Laporan Pull API tidak mendukung perubahan nama kampanye |

</Accordion>

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/aggregated-and-analytics-reporting-overview">Deskripsi dan contoh laporan agregat</Anchor>
> * <Anchor target="_blank" href="/marketers/id/docs/aggregated-and-analytics-reporting-overview">Memilih alat pengiriman data yang tepat untuk data gabungan</Anchor>

<div data-zendesk-anchors="h_01HE0YP82966QHRAEW979ABCTP=mencari-data-lengkap-api-pull pull-api-aggregate-data=data-teragregasi-pull-api h_01HE0YP829WD5TDFHTPYAV30QN=data-teragregasi-pull-api aggregate-performance-reports-available-via-pull-api=laporan-kinerja-agregat-tersedia-melalui-pull-api h_01HE0YP829EQ7N6CST352X917H=laporan-kinerja-agregat-tersedia-melalui-pull-api h_01HE0YP82954F1ACVR2K4AFD5W=using-pull-api-aggregate-data h_01HE0YP8292131Q2561A4E1GYZ=parameters h_01HE0YP829ZPJAPHPDR9H4HMRT=traits-and-limitations h_01HE0Y2KTXS06WHN57MQ91AD09=lihat-juga" />
