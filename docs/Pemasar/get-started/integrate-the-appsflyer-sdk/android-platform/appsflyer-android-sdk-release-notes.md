---
title: Catatan rilis Android SDK AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Release Notes
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2017-03-09T20:17:19Z'
  edited_at: '2023-10-27T14:54:40Z'
  id: 115001256006
  locale: id
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/id/articles/115001256006
---
> **Sekilas:** catatan rilis Android SDK mulai dari V4.x.

## Android SDK V6

<Anchor target="_blank" href="/marketers/id/docs/sdk-integration-overview">Panduan integrasi Android SDK untuk pemasar</Anchor>

| Versi | Tanggal rilis | Hanya pemeliharaan | Catatan |
| --- | --- | --- | --- |
| 6.12.4 | 25-10-2023 |  | <ul><li>Dexguard diperbarui ke versi 9.4.16 untuk meningkatkan stabilitas SDK.</li></ul> |
| 6.12.3 | 31-08-2023 | Ya |  |
| 6.12.2 | 02-08-2023 |  | <ul><li>Memperbaiki bug yang dapat menyebabkan aplikasi mogok di beberapa perangkat di Android 8.1.0 dan Android 11.</li></ul> |
| 6.12.1 | 29-06-2023 |  | <ul><li>Memperbaiki masalah peluncuran Play Store yang tertunda dalam promosi silang.</li><li>Memperbaiki bug yang menyebabkan aplikasi mogok di beberapa perangkat.</li></ul> |
| 6.12.0 | 28-06-2023 |  | <ul><li>Tidak digunakan lagi - harap gunakan versi 6.12.1.</li></ul> |
| 6.11.2 | 29-06-2023 |  | <ul><li>Memperbaiki bug yang menyebabkan aplikasi mogok di beberapa perangkat.</li></ul> |
| 6.11.1 | 06-06-2023 |  | <ul><li>Tidak digunakan lagi - harap gunakan versi 6.12.1.</li><li>Memperbaiki bug yang membuat aplikasi terkadang mogok setelah melakukan inisialisasi SDK.</li></ul> |
| 6.11.0 | 16-05-2023 |  | <ul><li>Memperbaiki masalah yang terkadang menyebabkan aplikasi macet di beberapa perangkat saat SDK berusaha mendapatkan Perujuk Google Play</li></ul> |
| 6.10.3 | 25-04-2023 | Ya |  |
| 6.10.1 | 01-03-2023 |  | <ul><li>Memperbaiki masalah yang terkadang menyebabkan aplikasi di perangkat Samsung tertutup saat menginisialisasi SDK. Masalah ini memengaruhi aplikasi dengan SDK V6.6.0 dan yang lebih baru.</li></ul> |
| 6.10.0 | 13-02-2023 |  | <ul><li>Domain AppsFlyer baru untuk komunikasi antara server SDK dan AppsFlyer.</li><li>Mengubah API setHost ketika nilai kosong atau null dikirimkan. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#sethost">Pelajari lebih lanjut</Anchor></li></ul> |
| 6.9.4 | 6-12-2022 |  | <ul><li>Memperbaiki masalah ketika mengirimkan event pendapatan iklan dari konektor SDK pendapatan iklan memicu panggilan ke pendengar konversi.</li><li>Memperbaiki masalah yang kadang menyebabkan aplikasi terhenti ketika event pendapatan iklan dikirim dari konektor SDK pendapatan iklan.</li></ul> |
| 6.9.3 | 28-11-2022 |  | <ul><li>Memperbarui struktur permintaan internal untuk Mendapatkan Data Konversi (GCD). **Catatan**: Data respons tetap sama.</li><li>Memperbaiki masalah ketika SDK memicu permintaan GCD saat aplkasi mengatur ConversionListener ke null.</li></ul> |
| 6.9.2 | 02-10-2022 |  | <ul><li>Memperbaiki masalah terkait keterlambatan dalam meminta validasi pembelian menggunakan API validateAndLogInAppPurchase.</li></ul> |
| 6.9.1 | 19-09-2022 | Ya |  |
| 6.9.0 | 12-09-2022 |  | <ul><li>Menambahkan dukungan untuk Perujuk GetApps Store Xiaomi.</li><li>Memperbarui API internal untuk pelaporan pendapatan iklan. Mulai versi ini, hanya <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">konektor SDK pendapatan iklan generik</Anchor> yang didukung.</li></ul> |
| 6.8.2 | 29-08-2022 |  | <ul><li>Memperbaiki masalah kritis pada mekanisme caching SDK yang diperkenalkan di V6.70, yang menyebabkan peristiwa yang disimpan dalam cache dikirim beberapa kali.</li></ul> |
| 6.8.1  <br />(Tidak Digunakan Lagi) | 24-08-2022 | Ya | <ul><li>**Tidak Digunakan Lagi.** Silakan gunakan V6.8.2.</li></ul> |
| 6.8.1  <br />(Tidak Digunakan Lagi) | 18-07-2022 |  | <ul><li>**Tidak Digunakan Lagi.** Silakan gunakan V6.8.2.</li><li>Menghapus API `enableLocationCollection`dari SDK. Aplikasi masih dapat melaporkan data lokasi pengguna dengan meneruskannya ke SDK secara langsung lewat API `logLocation`.</li><li>Menambahkan izin `com.google.android.gms.permission.AD_ID` ke `AndroidManifest.xml` SDK. Baca lebih lanjut tentang hal tersebut <Anchor target="_blank" href="/marketers/id/docs/bulletin-the-android-sdk-adds-the-ad-id-permission">di sini</Anchor>.</li><li>Memperbaiki masalah terkait optimisasi dan kebingungan menggunakan R8.</li></ul> |
| 6.7.0  <br />(Tidak Digunakan Lagi) | 19-06-2022 |  | <ul><li>**Tidak Digunakan Lagi.** Silakan gunakan V6.8.2.</li><li>Mengubah bagaimana SDK menangani permintaan ke server AppsFlyer. Mengikuti perubahan ini, permintaan untuk melaporkan aplikasi pertama (konversi) akan diprioritaskan daripada in-app event dan jenis permintaan lainnya. Baca lebih lanjut tentang hal tersebut <Anchor target="_blank" href="/marketers/id/docs/bulletin-adding-a-priority-queue-to-the-android-sdk">di sini</Anchor>.</li><li>**API baru:** `setDisableNetworkData` untuk memilih keluar dari pengumpulan informasi mengenai jaringan seluler (nama operator).</li></ul> |
| 6.6.1 | 16-05-2022 | Ya |  |
| 6.6.0 | 01-05-2022 |  | <ul><li>Menambahkan lebih banyak parameter ke callback `onDeepLinking` UDL untuk aliran Deep Linking Langsung (pengguna yang sudah ada). <Anchor target="_blank" href="/marketers/id/docs/bulletin-additional-parameters-available-for-deep-linking-existing-users">Untuk informasi lebih lanjut</Anchor>.</li></ul> |
| 6.5.4 | 23-03-2022 | Ya |  |
| 6.5.3 | 09-03-2022 |  | <ul><li>**Perbaikan Bug:** Memperbaiki masalah pembuatan tautan undangan pengguna yang berisi karakter non-Inggris.</li></ul> |
| 6.5.2 | 26-01-2022 |  | <ul><li>Memperbaiki masalah ketika menyelesaikan URL untuk deferred deep linking di UDL.</li><li>Diperbarui ke DexGuard 9.2</li><li>Refactoring dan perubahan internal.</li></ul> |
| 6.5.1 | 29-12-2021 |  | <ul><li>Resolusi deeplink (tautan langsung) dengan UDL untuk aplikasi yang menggunakan <Anchor target="_blank" href="/marketers/id/docs/set-up-multi-store-android-attribution#channel-name">opsi di luar Toko dengan Kanal</Anchor></li></ul> |
| 6.5.0 | 07-12-2021 |  | <ul><li>Refactoring dan perubahan internal.</li></ul> |
| 6.4.3 | 14-11-2021 |  | <ul><li>Memperbaiki bug yang diperkenalkan di  `V6.4.2`dengan `LinkGenerator` menyebabkan pembuatan tautan dengan parameter URL yang hilang.</li></ul> |
| 6.4.2 | 24-10-2021 |  | Berikut ini telah diselesaikan:<ul><li>`pid` parameter ditambahkan dua kali ke URK kustom yang dihasilkan oleh `LinkGenerator`.</li><li>Tambahan `/` ditambahkan ke nilai `af_dp` ketika menggunakan `LinkGenerator` untuk membuat skema URI kustom.</li><li>Baik IMEI maupun AndroidID dikumpulkan jika aplikasi hanya memicu pengumpulan salah satunya.</li></ul> |
| 6.4.1 | 17-10-2021 |  | Menyelesaikan kesalahan kompilasi ketika menggunakan versi Gradle lebih lama dari V3.5.4. |
| 6.4.0 | 12-09-2021 |  | **API Baru:** `setSharingFilterForPartners` memungkinkan Anda untuk mengonfigurasi mitra mana yang SDK harus kecualikan dari pembagian data.<br /><br />Pada versi ini, `setSharingFilter` dan `setSharingFilterForAllPartners` tidak dapat digunakan lagi. |
| 6.3.2 | 06-06-2021 |  | **API Baru**: [`setDisableAdvertisingIdentifiers`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers) |
| 6.3.1 | 26-05-2021 |  | <ul><li>**API Baru**: [`performOnDeepLinking`](https://dev.appsflyer.com/hc/docs/conversion-data)</li><li>Menambahkan kemampuan untuk memicu <Anchor target="_blank" href="/marketers/id/docs/user-invite-attribution#prosedur">API User Invite</Anchor> sebelum memanggil `mulai/setelah memanggil stop`</li><li>**Perbaikan Bug**: Memperbaiki masalah di mana panggilan ke `waitForCustomerUserId` tidak dirilis, bahkan setelah memanggil `setCustomerUserId`</li></ul> |
| 6.3.0 | 29-04-2021 |  | <ul><li>**Perbaikan Bug**: Pemanggilan `onConversionDataFail` yang salah setelah kegagalan permintaan pengiriman in-app event</li><li>**Perbaikan Bug**: koleksi metrik sensor gerak (untuk deteksi penipuan)</li><li>**Perbaikan Bug**: Perbaikan terkait kebingungan ke <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl">UDL</Anchor></li><li>Pembaruan teknis ke API OneL</li></ul> |
| 6.2.3 | 04-03-2021 | Ya |  |
| 6.2.0 | 07-02-2021 |  | <ul><li>**API Baru**: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setpartnerdata">`setPartnerData`</Anchor></li></ul> |
| 6.1.4 | 12-01-2021 |  | <ul><li>Dukungan tambahan untuk DexGuard V9</li></ul> |
| 6.1.3 | 24-12-2020 |  | <ul><li>**API Baru**: <Anchor target="_blank" href="/marketers/id/docs/additional-sdk-integration-guide#record-push-notifications">`addPushNotificationDeepLinkPath`</Anchor> (mendukung Movable Ink)</li></ul> |
| 6.1.1 | 03-12-2020 |  | <ul><li>Dukungan tambahan untuk referrer Samsung Galaxy Store</li><li>Perbaikan bug kecil dan peningkatan kinerja.</li></ul> |
| 6.1.0 | 09-11-2020 |  | <ul><li>Dukungan tambahan untuk <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl">API deep linking terpadu</Anchor></li></ul> |
| 6.0.1 | 28-10-2020 | Ya |  |
| 6.0.0 | 14-10-2020 |  | <ul><li>Perubahan besar ke fungsionalitas SDK dan API, termasuk deprekasi dan perubahan nama metode. [Pelajari lebih lanjut](/docs/appsflyer-android-sdk-release-notes#android-v600-release-notes)</li></ul> |

<div id="android-v600-release-notes" />

<Accordion title="Catatan rilis Android V6.0.0">

### Metode dihapus/tidak digunakan lagi atau diganti namanya

#### Metode dihapus/tidak digunakan lagi

Metode berikut ini sudah dihapus dari SDK:

* sendDeepLinkData
* trackAppLaunch
* setPluginDeepLinkData
* setConsumeAFDeepLinks
* setHostName

#### Metode diganti namanya

| Nama API (sebelum V6) | Nama API saat ini (V6 dan versi lebih baru) |
| --- | --- |
| stopTracking | stop |
| setCustomerIdAndTrack | setCustomerIdAndLogSession |
| startTracking | start |
| trackLocation | logLocation |
| reportTrackSession | logSession |
| trackEvent | logEvent |
| setDeviceTrackingDisabled | anonymizeUser (anonimkan pengguna) |
| validateAndTrackInAppPurchase | validateAndLogInAppPurchase |
| isStopTracking | isStopped |
| trackAndOpenStore | logAndOpenStore |
| trackCrossPromoteImpression | logCrossPromoteImpression |
| trackInvite | logInvite |

### Antarmuka yang diganti namanya

| Nama antarmuka (sebelum V6) | Nama antarmuka saat ini (V6 dan versi lebih baru) |
| --- | --- |
| AppsFlyerTrackingRequestListener | AppsFlyerRequestListener |

</Accordion>

## Android SDK V5

<div id="android-sdk-v5-release-notes" />

<Accordion title="Catatan rilis Android SDK V5">

| Versi | Tanggal rilis | Hanya pemeliharaan | Catatan |
| --- | --- | --- | --- |
| 5.4.6 | 09-11-2020 |  | <ul><li>Dukungan tambahan untuk referrer Huawei AppGallery</li></ul> |
| 5.4.4 | 01-10-2020 |  | <ul><li>Dukungan tambahan untuk SDK dalam menangani beberapa pengalihan dari ESP</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 5.4.3 | 30-07-2020 |  | <ul><li>Kapabilitas logging dan debugging yang diperluas</li><li>Perbaikan bug dan pemeliharaan</li><li>Dukungan untuk install referrer V2 Google</li></ul> |
| 5.4.1 | 30-06-2020 |  | <ul><li>Mengizinkan pemasang iklan untuk mengontrol pembagian data dengan mitra/jaringan terintegrasi. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">Pelajari lebih lanjut</Anchor></li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 5.4.0 | 03-06-2020 |  | <ul><li>Dukungan penuh untuk mengumpulkan OAID secara otomatis</li><li>Dukungan beberapa referrer: SDK dapat mengumpulkan referrer Huawei dan Google</li><li>Perbaikan kinerja SDK</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 5.3.0 | 27-04-2020 |  | <ul><li>Mengakses data konversi deep linking langsung yang terbaru kapan pun, melalui metode onAppOpenAttribution</li><li>Parameter tambahan tersedia untuk tayangan promosi silang</li><li>Perbaikan bug: memperbaiki masalah dengan a. dan b. nama file di Windows</li><li>metode sendDeepLinkData ke mendapatkan data atribusi bahkan jika pengguna ditautkan lansung ke aktivitas spesifik yang sudah tidak digunakan lagi sebagai ganti metode startTracking()</li></ul> |
| 5.2.0 | 10-03-2020 |  | <ul><li>Izinkan inisialisasi SDK di aktivitas mana pun</li><li>Kapabilitas keamanan, logging, dan debugging</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 5.1.2 | 19-02-2020 | Ya |  |
| 5.1.1 | 23-01-2020 | Ya |  |
| 5.1.0 | 06-01-2020 |  | <ul><li>Target ke Android 9 (API tingkat 28) berdasarkan persyaratan level API target Google</li><li>Peningkatan untuk perlindungan anti penipuan - untuk klien Protect360</li><li>Modul opsional untuk mengumpulkan OAID (relevan untuk domestik Tiongkok) - Xiaomi dan Huawei (lihat <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-oaid">https://github.com/AppsFlyerSDK/appsflyer-oaid</Anchor>).</li><li>Peningkatan stabilitas ketika menggunakan setOneLinkCustomDomain untuk ESP</li></ul> |

</Accordion>

<div id="android-v500-release-notes" />

<Accordion title="Catatan rilis Android V5.0.0">

#### **Waktu respons SDK yang sudah ditingkatkan**

Dimulai dengan SDK V5.0.0 waktu respons GCD yang sudah ditingkatkan untuk penginstalan organik.

#### **Metode dihapus atau diubah namanya**

**Nama metode berubah**

Nama metode data konversi penginstalan sekarang sama untuk Android dan iOS. Hal ini berdampak pada metode yang menangani:

* data konversi diinstal
* eror jika data tidak tersedia

| Nama Android sebelum SDK V5 | Nama iOS sebelum SDK V5 | Nama standar |
| --- | --- | --- |
| `onInstallConversionDataLoaded` | `onConversionDataReceived` | `onConversionDataSuccess` |
| `onInstallConversionFailure` | `onConversionDataRequestFailure` | `onConversionDataFail` |

**Metode dihapus**

Metode berikut ini tidak digunakan lagi di versi SDK sebelumnya. Mereka sekarang telah dihapus dari SDK.

**Android**

* setGCMProjectID (String projectNumber)
* setGCMProjectNumber (String projectNumber)
* setGCMProjectNumber (Context context, String projectNumber)
* enableUninstallTracking (String senderId)
* setAppUserId (String id)
* setUserEmail (String email)
* setCollectFingerPrint (boolean isCollect)
* getAttributionId (ContentResolver contentResolver)
* FirebaseInstanceIdListener class (instance of FirebaseInstanceIdService)

**iOS**

* loadConversionDataWithDelegate: (id`<AppsFlyerTrackerDelegate>`) delegate
* setHost:(NSString *) host

#### Perubahan untuk mendapatkan format data konversi

Dalam versi ini, untuk setiap penginstalan atau aplikasi yang dibuka, SDK mengembalikan objek peta yang berisi data konversi (GCD) seperti sumber media dan nama kampanye. Di versi SDK sebelumnya, GCD hanya mengembalikan parameter yang memiliki nilai

Dimulai dengan versi ini, semua parameter dikembalikan, termasuk yang tanpa nilai. Parameter tanpa nilai memiliki nilai nol.

> 📄 **Contoh**
>
> Penginstalan mengikuti klik pada URL berikut:
>
> ```http
> https://app.appsflyer.com/com.sample.app?pid=super_media_source&c=awesome_campaign
>   &campaign_id=1234&af_sub1=promo
> ```
>
> Respons adalah sebagai berikut:
>
>
> <Tabs>
> <Tab title="Respons GCD sebelum SDK V5">
>
> ```json
>    {
>       "install_time": "2019-11-11 15:00:59.828",
>       "media_source": "super_media_source",
>       "orig_cost": "0.0",
>       "advertising_id": "215d8172-c61e-4d0c-9eb2-aa4d0971ed8c",
>       "af_status": "Non-organic",
>       "is_first_launch": "true",
>       "af_sub1": "promo",
>       "af_click_lookback": "7d",
>       "cost_cents_USD": "0",
>       "iscache": "true",
>       "click_time": "2019-11-11 15:00:35.102",
>       "campaign": "awesome_campaign",
>       "campaign_id": "1234",
>   }
> ```
>
> </Tab>
>
> <Tab title="Respons GCD memulai SDK V5">
>
> ```json
>    {
>       "adgroup": null,
>       "campaign": "awesome_campaign",
>       "media_source": "super_media_source",
>       "adset_id": null,
>       "campaign_id": 1234,
>       "iscache": true,
>       "install_time": "2019-11-11 15:00:59.828",
>       "adgroup_id": null,
>       "af_sub5": null,
>       "click_time": "2019-11-11 15:00:35.102",
>       "agency": null,
>       "cost_cents_USD": "0",
>       "advertising_id": "215d8172-c61e-4d0c-9eb2-aa4d0971ed8",
>       "adset": null,
>       "af_sub3": null,
>       "af_siteid": null,
>       "http_referrer": null,
>       "orig_cost": "0.0",
>       "af_sub4": null,
>       "af_cpi": null,
>       "af_sub1": "promo",
>       "af_click_lookback": "7d",
>       "af_sub2": null,
>       "af_status": "Non-organic",
>       "is_first_launch": "true",
>       "retargeting_conversion_type": "none"
>   }
> ```
>
> </Tab>
> </Tabs>
>

GCD mengembalikan struktur yang sama terlepas dari datanya. Jika sebuah parameter kosong, itu termasuk dalam GCD dengan nilai nol. Hal ini memudahkan developer untuk memproses GCD tanpa harus menyesuaikan logika pemrosesan GCD, terlepas dari apakah parameter tertentu disertakan atau tidak. Untuk mempelajari lebih lanjut tentang data konversi dalam berbagai skenario, lihat <Anchor target="_blank" href="/marketers/id/docs/conversion-data-payloads-and-scenarios">di sini</Anchor>.

</Accordion>

<div id="deprecated-versions" />

<Accordion title="Versi usang">

| Versi | Tanggal Rilis | Catatan |
| --- | --- | --- |
| 5.0.2 | 23-12-2019 |  |
| 5.0.1 | 12-12-2019 |  |
| 5.0.0 | 12-11-2019 | <ul><li>Perbaikan bug dan pemeliharaan</li><li>Perubahan besar ke fungsionalitas SDK dan API, termasuk deprekasi dan perubahan nama metode. [Pelajari lebih lanjut](/docs/appsflyer-android-sdk-release-notes#android-v500-release-notes)</li></ul> |
| 4.11.0 | 22-10-2019 | <ul><li>Logging yang ditingkatkan untuk kemampuan debug yang lebih baik untuk hal-hal berikut ini:<ul><li>ESP</li><li>Penyelesaian Tautan Bermerek</li><li>onInstallConversionData dan onAppOpenAttribution.</li></ul></li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 4.10.3 | 15-09-2019 | <ul><li>Perbaikan bug dan pemeliharaan</li><li>Dukungan untuk ID Pemasang Iklan Terbuka (OAID)</li></ul>4.10.2 |
| 4.10.1 | 01-07-2019 | Perbaikan bug dan pemeliharaan |
| 4.10.0 | 14-05-2019 | <ul><li>Peningkatan SDK untuk pengembang yang menggunakan ProGuard.</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 4.9.0 | 17-03-2019 | <ul><li>setResolveDeepLinkURLs API untuk menyelesaikan OneLink yang dibungkus dengan Tautan Universal lainnya</li><li>Perbaikan untuk perekaman notifikasi push saat rekaman notifikasi push yang dibuang dari payload sebelumnya berisi pid yang sama dan masih ada di memori.</li><li>Perbaikan kesalahan ketik dari af\_county ke af\_country</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 4.8.20 | 13-02-2019 | <ul><li>Peningkatan kemampuan peringkat nol untuk penyedia seluler</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 4.8.19 | 26-12-2018 | <ul><li>Memperbaiki masalah saat metode `waitForCustomerUserId()` merusak `generateLink`</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 4.8.18 | 11-11-2018 | <ul><li>Memperbaiki masalah deep linking dari aktivitas trampolin</li><li>Peningkatan akurasi interaksi ulang saat berpindah antara latar belakang dan latar depan</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 4.8.17 | 02-11-2018 | Memperbaiki masalah terkait konflik di ProGuard yang menyebabkan hilangnya data peluncuran aplikasi dalam beberapa kasus. Masalah ini hanya memengaruhi SDK versi 4.8.16 |
| 4.8.16 | 31-10-2018 | Perbaikan bug dan pemeliharaan |
| 4.8.15 | 27-08-2018 | <ul><li>Acara SDK Tambahan: Langganan, Mulai Trial, Klik Iklan, Tampilan Iklan</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 4.8.14 | 31-07-2018 | <ul><li>Added setOutOfStore and getOutOfStore APIs for dynamically setting the AF\_STORE value</li><li>Menambahkan API `onTrackingRequestFailure` dan `onTrackingRequestSuccess` untuk menerima konfirmasi bahwa AppsFlyer berhasil menerima server permintaan pelacakan</li></ul> |
| 4.8.13 | 20-06-2018 | <ul><li>Memperbaiki bug dalam kasus ekstrem di mana IMEI hilang saat diteruskan secara eksplisit melalui setImeiData API</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 4.8.12 | 27-05-2018 | <ul><li>Memperbaiki aplikasi yang crash saat menggunakan pengujian JUnit yang menggunakan Robolectric</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 4.8.11 | 02-05-2018 | Perbaikan bug dan pemeliharaan |
| 4.8.10 | 26-04-2018 | <ul><li>Menambahkan API `setPreinstallAttribution`</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 4.8.9 | 02-04-2018 | <ul><li>Kumpulkan IMEI hanya jika GooglePlayServices tidak ada di perangkat, dan GAID tidak dapat diambil di perangkat tersebut</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 4.8.8 | 11-03-2018 | <ul><li>Menambahkan API untuk inisialisasi SDK yang tertunda hingga customerUserID disediakan</li><li>Perbaikan bug dan pemeliharaan.</li></ul> |
| 4.8.7 | 25-01-2018 | <ul><li>API `isStopTracking` untuk mematikan semua aktivitas SDK</li><li>parameter event `af_content`</li></ul> |
| 4.8.5 | 29-11-2017 | <ul><li>Dukungan untuk API referrer Google baru</li><li>Metode init baru yang menerima konteks</li></ul> |
| 4.8.4 | 14-11-2017 | <ul><li>Menambahkan flag ke getConversionData `is_first_launch` yang menunjukkan apakah ini adalah peluncuran pertama aplikasi. Tanda ini memungkinkan developer mengidentifikasi peluncuran pertama aplikasi dengan mudah dalam respons callback getConversionData yang dikembalikan di setiap peluncuran. Nilai yang mungkin untuk is\_first\_launch adalah "true" atau "false"</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 4.8.3 | 27-09-2017 | Menambahkan dukungan untuk data perujuk HTTP di getConersionData |
| 4.8.2 | 19-09-2017 | Perbaiki di sendDeepLinkData(this) untuk aplikasi yang memiliki tautan langsung ke beberapa aktivitas |
| 4.8.1 | 17-09-2017 | Peningkatan perlindungan terhadap in-app event yang dipanggil sebelum inisialisasi SDK |
| 4.8.0 | 03-09-2017 | <ul><li>API Undangan Pengguna</li><li>API Promosi Silang</li><li>Waktu khusus antar sesi</li><li>Dukungan untuk Peringkat Nol bagi Penyedia Seluler</li><li>Parameter event tambahan af\_projected\_revenue</li><li>Perbaikan bug dan pemeliharaan</li><li>Metode init tambahan diperkenalkan - AppsFlyerLib.getInstance().init(AF\_DEV\_KEY,conversionDataListener);</li></ul> |
| 4.7.4 | 28-06-2017 | Peningkatan penanganan beberapa penonaktifan ScheduledExecutorSerice |
| 4.7.3 | 06-06-2017 | Peningkatan untuk integrasi mParticle |
| 4.7.2 | 22-05-2017 | <ul><li>Memperbaiki masalah kebocoran memori kecil</li><li>Peningkatan akurasi pengukuran Uninstal (Pencopotan Pemasangan)</li><li>Memperbaiki peringatan ProGaurd yang memengaruhi pengukuran uninstal (pencopotan pemasangan)</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 4.7.1 | 22-02-2017 | Memperbaiki peringatan yang dipicu oleh ProGuard |
| 4.7.0 | 13-02-2017 | <ul><li>Parameter Event Tambahan</li><li>Dukungan untuk pengukuran uninstal berbasis Firebase</li><li>Perbaikan bug dan pemeliharaan</li></ul> |

</Accordion>

## Checksum Android SDK

AppsFlyer menggunakan checksum md5:

<div id="v6-checksums" />

<Accordion title="checksum V6">

| Versi Android SDK | Checksum |
| --- | --- |
| 6.6.1 | 1ec98047f8cb4145137f3c97459d052c |
| 6.6.0 | 6f5aef27ea407c7fc1691b52ff800c61 |
| 6.5.4 | c71aacbf201449dd5ef1158b55bd2ad0 |
| 6.5.3 | 7db44f0852be1c94fe36cc535b7c61f7 |
| 6.5.2 | 71e3a16c4278f857cd86b7b05aedd066 |
| 6.5.1 | 261928cfc55b27a6c2ab19cf9081d705 |
| 6.5.0 | 2a6d500fd4939a8faa47bbbba97288b6 |
| 6.4.3 | c62f9359d6b5497d54e248c526c5f547 |
| 6.4.2 | dc385fb62eaf68aff2e7f9c1c0ed19ea |
| 6.4.1 | 94945db2c0e81baab79535393f210f1b |
| 6.4.0 | d7910a35901d4299b54259f1c1bbe2d6 |
| 6.3.2 | 46bc92bb2eed1416de28ccccb3a28620 |
| 6.3.1 | ca47af77ffbcd7525e82d0bdaaef5b91 |
| 6.3.0 | f969bb5a62885e8084794d5334787275 |
| 6.2.3 | bab1309f77acd1f0453372150c82694a |
| 6.2.0 | fc727698c7b8bfb1ca448726492931b4 |
| 6.1.4 | 983785b1c30a15e8fac029e370bb3b73 |
| 6.1.3 | c0392a091659dc445a1014e14da6a31a |
| 6.1.1 | 0a18fafb2826c90b3388b371a3cbdeec |
| 6.1.0 | e8d6df04ac2642b2d7b16efb57f315e9 |
| 6.0.1 | 9ebeb6f4f49476667c07d0e8eb1aa2e8 |
| 6.0.0 | cff3d453ea94e67182f5b1b023aeb1c1 |

</Accordion>

<div id="v5-checksums" />

<Accordion title="checksum V5">

| Versi Android SDK | Checksum |
| --- | --- |
| 5.4.6 | 4f1bdc33ac0d6dd3f9b75411c3c0a06c |
| 5.4.4 | 13a04913cf61276238f54e5e2d73e88d |
| 5.4.3 | 7b1caef46942c70edcd2e59cad69e439 |
| 5.4.1 | e4eb21c0030f376857b53e2e30022fc8 |
| 5.4.0 | 8c0270f6c3e7e58b1db42be82cc341d8 |
| 5.3.0 | d602dd28d9ee807855e5426d6a9b7ebf |
| 5.2.0 | 64fe94447def6d99549d3274ce908f09 |
| 5.1.2 | 1a7dbb23aad32d697835f3ec29337ca9 |
| 5.1.1 | dfea6a49e6ae57fc2c700f6dcd904bc1 |
| 5.1.0 | 89cc7e08a0430180e64f3cccf955768f |
| 5.0.2 | c113618ea379531cba6ce42bc4c79d72 |
| 5.0.1 | db0502faa5b02102dd99ac6cec666d04 |
| 5.0.0 | 98f1f78ae5f63cb4f40ba838d3d1be22 |

</Accordion>

<div id="v4-checksums" />

<Accordion title="checksum V4">

| Versi Android SDK | Checksum |
| --- | --- |
| 4.10.3 | 855186d68912810fa47897262a9ba0a0 |
| 4.10.2 | 13ed5716d5a8583eeee527f01bd2a69d |
| 4.10.1 | ab3e49bb4640990267466b7852cd3de7 |
| 4.10.0 | b5fb55ee76cd6a742d9bd25b910745a1 |
| 4.9.0 | afa49524ddceda28ca1648946489a6b0 |
| 4.8.20 | 2f59d0f8db09b92f8261475a1d0807d0 |
| 4.8.19 | baf8fa419f38de52cef6091de32aca86 |
| 4.8.18 | 3a0641720811a25542449f1927daf13e |
| 4.8.17 | 3a0641720811a25542449f1927daf13e |
| 4.8.16 | 501be427b0c2a831e148649131ce3fc0 |
| 4.8.15 | 7b6759a006d72d3a7c78ec80160c3502 |
| 4.8.14 | bc4facd80958d0600b4d000104e524d9 |
| 4.8.13 | bc4facd80958d0600b4d000104e524d9 |
| 4.8.12 | 171569002d93fb8d49787b363192973f |
| 4.8.11 | 4419af159a42e4ee7a218ef8615e2abb |
| 4.8.10 | 468ad04e4a2088ba7af9c45d42f4ed6d |
| 4.8.9 | 9a923bbbf3f6c7cc19b900e49644da2c |
| 4.8.8 | 6dee4814986061a0723cc9f844796e2e |
| 4.8.7 | ca13997ccb781a5935e91983b7be81ea |
| 4.8.6 | da117a3e9e05df7dd28297df762cfbfa |
| 4.8.5 | f8ea07b8a60d664541686ba7064730f5 |
| 4.8.4 | b10f185c1094cf283b11339810a47c87 |
| 4.8.3 | 7f94ec175b948c5009bfbfe2fb25b2b0 |
| 4.8.2 | 3e34b55e13cd3f8d387b1a33c20105eb |
| 4.8.1 | 6c2930d2997a7b2b6ab7b3ecf0e3135b |
| 4.8.1 | 468ad04e4a2088ba7af9c45d42f4ed6d |
| 4.8.1 | 4419af159a42e4ee7a218ef8615e2abb latest |
| 4.8.0 | 32d67577ce59b2072475e509579baece |
| 4.7.4 | 7e649e6a1cf8999ca39b05402946b3d6 |
| 4.7.3 | e30c020f8ee5dd3af274fa94ef414a38 |
| 4.7.2 | 945aaaca554aa8b2f96219f25eed9777 |
| 4.7.1 | 862c349025e4725d4e5044a190c60337 |
| 4.7.0 | b060ad140ffd0c8f2b3febb26122d173 |

</Accordion>

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/appsflyer-sdk-version-control-policy">Kebijakan kontrol versi AppsFlyer SDK</Anchor>

<div data-zendesk-anchors="h_01H9ZPCP8RWF24WAZ6YYMA1GS0=android-sdk-v6 h_01H9ZPCP8S2P9Z93ZDENDHKJHD=android-v600-release-notes methods-removeddeprecated-or-renamed=metode-dihapustidak-digunakan-lagi-atau-diganti-namanya h_01H9ZPCP8SCYTEYJG9J1SANGVJ=metode-dihapustidak-digunakan-lagi-atau-diganti-namanya methods-removeddeprecated=metode-dihapustidak-digunakan-lagi 01EEYC8A6FNJ91R15X633BHSXF=metode-dihapustidak-digunakan-lagi methods-renamed=metode-diganti-namanya 01EEYC8A6F8PB4C94Z14KXYD68=metode-diganti-namanya renamed-interface=antarmuka-yang-diganti-namanya h_01H9ZPCP8SV4VPEZA39VDTMCZ7=antarmuka-yang-diganti-namanya h_01H9ZPCP8S37W1456YQN6RQDM7=android-sdk-v5 h_01H9ZPCP8SZ3QVX773J2X3QEGX=android-sdk-v5-release-notes h_01H9ZPCP8SAMFHXZW0T6CPEEYZ=android-v500-release-notes improved-sdk-response-time=waktu-respons-sdk-yang-sudah-ditingkatkan h_01H9ZPCP8SN7NRGH3FZBEGCB3E=waktu-respons-sdk-yang-sudah-ditingkatkan methods-removed-or-renamed=metode-dihapus-atau-diubah-namanya h_01H9ZPCP8SY1HYDNR6HEZHXN37=metode-dihapus-atau-diubah-namanya changes-to-get-conversion-data-format=perubahan-untuk-mendapatkan-format-data-konversi h_01H9ZPCP8S6Q97DNCZ8ANVMVT8=perubahan-untuk-mendapatkan-format-data-konversi h_01H9ZPCP8TAWT16MR1TVZVEVJ8=contoh h_01H9ZPCP8TFSA3SXDGTAZYC00V=deprecated-versions android-sdk-checksums=checksum-android-sdk h_01H9ZPCP8T7DJFPXGYX5EQ3BVB=checksum-android-sdk h_01H9ZPCP8TWG0ZXGFJG4GQ4E0F=v6-checksums h_01H9ZPCP8TS9CE2B55511H8JBY=v5-checksums h_01H9ZPCP8TKSJB1X4YT3W83EVJ=v4-checksums h_01HDNZ774ME3SVT89JS7R4MSKE=lihat-juga" />
