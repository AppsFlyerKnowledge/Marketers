---
title: Panduan integrasi konektor SDK pendapatan iklan tingkat tayangan umum ROI360
metadata:
  keywords:
    - ROI
    - ad revenue
    - Advertisers
    - Advertiser
    - Developer
    - Developers
    - ad revenue SDK
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-01-12T09:09:07Z'
  edited_at: '2024-07-01T13:48:47Z'
  id: 4416353506833
  locale: id
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/id/articles/4416353506833
---
> **Sekilas:** Konektor SDK pendapatan iklan AppsFlyer generik bekerja dengan jaringan iklan untuk melaporkan pendapatan iklan dengan perincian tingkat tayangan.

<Image align="center" alt="mceclip1__1_.png" src="https://files.readme.io/202ded6950dfbf370bb48738876224936d28ecfae0c0aba09d1c49892b774cb5-31202279100177.png" />

<div id="impression-level-ad-revenue-reporting-by-sdk-api" />

## Pelaporan pendapatan iklan tingkat tayangan oleh konektor SDK

**Opsi pelaporan pendapatan iklan**

Pendapatan iklan dilaporkan ke AppsFlyer berdasarkan perincian agregat (melalui API) atau perincian tingkat tayangan (melalui SDK). Data tingkat tayangan melalui SDK:

* Data lebih aktual dan tersedia lebih cepat di AppsFlyer.
* Mendukung SKAN.

**Catatan:**

* Tayangan ini dikumpulkan dan diproses di AppsFlyer, tetapi tidak dihitung terhadap paket dalam aplikasi Anda.
* Ada <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad_revenue_unity_connector">plugin pendapatan iklan AppsFlyer untuk Unity</Anchor>.

<div id="reporting-ad-revenue-using-the-sdk-api" />

### Melaporkan pendapatan iklan menggunakan konektor SDK

**Prinsip operasi SDK**

Konektor SDK pendapatan iklan mengirimkan data pendapatan tayangan ke SDK AppsFlyer. Event tayangan ini dikumpulkan dan diproses di AppsFlyer dan peristiwa pendapatan iklan, `af_ad_revenue` dihasilkan di platform dengan pendapatan yang diatribusikan ke sumber UA asli.

**Tampilan data**

Event `af_ad_revenue` ini digunakan untuk mengidentifikasi pendapatan iklan. Event ini digunakan di seluruh platform termasuk dasbor dan alat pengiriman data lainnya.

**Jaringan yang didukung**

Daftar mediasi pendapatan iklan dan jaringan monetisasi yang didukung yang dapat mengirimkan data kepada kami melalui konektor SDK pendapatan iklan generik adalah sebagai berikut:

* <Anchor target="_blank" href="/marketers/id/docs/ironsource-campaign-configuration#ad-revenue-tab">Mediasi Unity LevelPlay</Anchor> (dahulu ironSource)
* <Anchor target="_blank" href="/marketers/id/docs/applovin-max-ad-revenue-configuration">Applovin Max</Anchor>
* <Anchor target="_blank" href="/marketers/id/docs/google-admob-ad-revenue-attribution-configuration">Google AdMob</Anchor>
* <Anchor target="_blank" href="/marketers/id/docs/fyber-campaign-configuration">Fyber</Anchor>
* <Anchor target="_blank" href="/marketers/id/docs/appodeal-campaign-configuration">Appodeal</Anchor>
* Admost
* Topon
* Tradplus
* <Anchor target="_blank" href="/marketers/id/docs/yandex-direct-campaign-configuration">Yandex</Anchor>
* <Anchor target="_blank" href="/marketers/id/docs/chartboost-campaign-configuration">Chartboost</Anchor>
* customMediation (jika solusi mediasi tidak ada dalam daftar mitra mediasi yang didukung)
* directMonetizationNetwork (ketika aplikasi terintegrasi langsung dengan jaringan monetisasi tanpa mediasi)

**Keaktualan data**

Konektor **SDK mengirimkan data pendapatan ke platform pada saat iklan ditampilkan. Untuk pelanggan premium ROI360, data tersedia di:**

* **Topik tingkat tayangan DataLocker pada pukul 1 pagi dan setiap 1 jam setelahnya,**
* **Laporan Aktivitas dan Kelompok AppsFlyer pada pukul 5 pagi UTC dan setiap 4 jam setelahnya.**

<div id="implementing-appsflyer-ad-revenue-sdk-api" />

## Menerapkan konektor SDK pendapatan iklan AppsFlyer generik

**Untuk menerapkan konektor SDK pendapatan iklan AppsFlyer generik**:

1. <Anchor target="_blank" href="/marketers/id/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">Aktifkan pendapatan iklan tingkat SDK di AppsFlyer</Anchor> untuk mitra yang ingin Anda hubungkan. **Catatan**: Ini perlu dilakukan untuk setiap aplikasi secara individual.
2. Beri tahu pengembang Anda untuk mengintegrasikan konektor SDK pendapatan iklan AppsFlyer generik menggunakan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue">instruksi ini</Anchor>.
3. Untuk mencatat pendapatan iklan di dasbor SKAdNetwork, ikuti <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">instruksi pendapatan iklan SKAN</Anchor>.

<div id="traits-and-limitations" />

## Karakteristik dan batasan

| Karakteristik | Catatan |
| --- | --- |
| Admob | <ul><li>Untuk mengaktifkan iLTV bagi Admob, ikuti <Anchor target="_blank" href="https://support.google.com/admob/answer/11322405#getstarted">tautan ini</Anchor></li><li>Untuk Android dan Unity, pendapatan tayangan dilaporkan oleh SDK Admob iLTV dalam <Anchor target="_blank" href="https://developers.google.com/android/reference/com/google/android/gms/ads/AdValue#public-long-getvaluemicros">unit mikro</Anchor>. Agar jumlah pendapatan iklan yang tepat dalam USD dapat ditampilkan di AppsFlyer, sebelum mengirim jumlah pendapatan iklan ke AppsFlyer, bagi jumlah yang diambil dari penanganan event iLTV dengan 1 juta.</li></ul> |
| Nilai pendapatan iklan | Peristiwa tayangan dengan nilai pendapatan di atas $10 (dan setara dalam mata uang lainnya) tidak diproses oleh konektor SDK. |
| Saluran | Saluran tidak didukung untuk aplikasi di luar toko, kecuali Amazon. |
| Jenis iklan | Tidak didukung. |

<div data-zendesk-anchors="impressionlevel-ad-revenue-reporting-by-sdk-connector=pelaporan-pendapatan-iklan-tingkat-tayangan-oleh-konektor-sdk 01H8HHAQHK6CDK8X2Y6N4GANNC=pelaporan-pendapatan-iklan-tingkat-tayangan-oleh-konektor-sdk reporting-ad-revenue-using-the-sdk-connector=melaporkan-pendapatan-iklan-menggunakan-konektor-sdk 01H8HHAQHKQ3H3R21Z1JYNJ2EE=melaporkan-pendapatan-iklan-menggunakan-konektor-sdk implementing-generic-appsflyer-ad-revenue-sdk-connector=menerapkan-konektor-sdk-pendapatan-iklan-appsflyer-generik 01H8HHAQHKCXKPJJE8EDT1J9CR=menerapkan-konektor-sdk-pendapatan-iklan-appsflyer-generik traits-and-limitations=karakteristik-dan-batasan 01H8HHAQHMCSVQ2ZAT3G7XJKAN=karakteristik-dan-batasan" />
