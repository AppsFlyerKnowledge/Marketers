---
title: Catatan rilis SDK iOS AppsFlyer
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
  created_at: '2017-03-09T19:49:54Z'
  edited_at: '2023-11-21T02:50:34Z'
  id: 115001224823
  locale: id
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/id/articles/115001224823
---
> **Sekilas:** Catatan rilis untuk iOS SDK `V4+`.

<div id="ios-sdk-release-notes" />

## iOS SDK V6

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk">Panduan integrasi SDK iOS bagi pengembang</Anchor>

| Versi | Tanggal rilis | Hanya pemeliharaan | Catatan |
| --- | --- | --- | --- |
| 6.12.2 | 24-08-2023 | Ya |  |
| 6.12.1 | 20-07-2023 |  | <ul><li>Memperbaiki masalah di SKAdNetwork 4.0 yang menyebabkan nilai konversi Kasar dilaporkan sebagai "Tidak Ada"</li><li>Memperbaiki kerusakan pada implementasi tvOS</li></ul> |
| 6.12.0 | 28-06-2023 |  | Menghapus dukungan bitcode dari SDK |
| 6.11.2 | 13-06-2023 |  | Memperbaiki masalah yang diperkenalkan di v6.11.0, ketika memanggil  `validateAndLogInAppPurchase`  (API lama untuk Validasi Pembelian dan pencatatan) tidak mencatat event pembelian.   <br />  <br />**Penting:** Jika Anda menggunakan `v6.11.0`atau `v6.11.1`, dan API `validateAndLogInAppPurchase` , harap tingkatkan ke versi ini. |
| 6.11.1 | 24-05-2023 | Ya |  |
| 6.11.0 | 25-04-2023 |  | <ul><li>Nama domain AppsFlyer baru di URL yang digunakan oleh SDK untuk mengirim permintaan ke server AppsFlyer.</li><li>Mengubah perilaku setHost API ketika nilai kosong atau null dikirim. [Pelajari lebih lanjut](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#sethost)</li></ul> |
| 6.10.1 | 02-04-2023 |  | Menambahkan parameter `link` ke payload UDL skenario Direct Deep Linking |
| 6.10.0 | 15-02-2023 |  | Dukungan SKAdNetwork 4.0. <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide">Pelajari lebih lanjut tentang solusi AppsFlyer SKAdNetwork</Anchor> |
| 6.9.2 | 31-01-2023 |  | Memperbarui struktur permintaan internal untuk Mendapatkan Data Konversi (GCD). **Catatan**: Data respons tetap sama. |
| 6.9.1 | 28-11-2022 |  | Memperbarui struktur permintaan internal untuk Mendapatkan Data Konversi (GCD). **Catatan**: Data respons tetap sama. |
| 6.9.0 | 06-11-2022 |  | Memperbarui API internal untuk pelaporan AdRevenue. Mulai versi ini, hanya [Konektor Generik untuk AdRevenue](https://dev.appsflyer.com/hc/docs/ad-revenue-2) yang didukung.<br /><br />Versi SDK ini kompatibel dengan AdRevenue Connector `V6.9.0`. |
| 6.8.1 | 09-08-2022 |  | **Deteksi Penginstalan Ulang**: Meningkatkan kemampuan untuk mendeteksi dan melaporkan penginstalan ulang aplikasi menggunakan penyimpanan di perangkat. Kemampuan ini dapat dikontrol di dashboard AppsFlyer dari <Anchor target="_blank" href="/marketers/id/docs/app-settings">halaman Pengaturan Aplikasi</Anchor>. |
| 6.8.0  <br />(Tidak Digunakan Lagi) | 19-07-2022 |  | Untuk Deteksi Instal Ulang, silakan gunakan SDK V6.8.1+ |
| 6.7.0 | 19-06-2022 |  | Perbarui implementasi SKAdNetwork agar menggunakan API Apple `updatePostbackConversionValue`, yang diperkenalkan di iOS 15.4.<br /><br />Hal ini tidak berpengaruh pada data yang dikirim dari SKAdNetwork, dan tidak memerlukan perubahan apa pun pada kode aplikasi. |
| 6.6.1 | 16-05-2022 | Ya |  |
| 6.6.0 | 01-05-2022 |  | Menambahkan lebih banyak parameter ke callback UDL `didResolveDeepLink` untuk alur Direct Deep Linking (pengguna yang sudah ada). <Anchor target="_blank" href="/marketers/id/docs/bulletin-additional-parameters-available-for-deep-linking-existing-users">Untuk informasi lebih lanjut</Anchor>. |
| 6.5.4 | 23-03-2022 | Ya |  |
| 6.5.3 | 02-03-2022 |  | **Perbaikan Bug:** Memperbaiki masalah pemanggilan ganda `didResolveDeepLink` pada tautan berdasarkan skema URI. |
| 6.5.2 | 26-01-2022 | Ya |  |
| 6.5.1 | 03-01-2022 | Ya |  |
| 6.5.0 | 22-12-2021 |  | Pemfaktoran ulang dan perubahan internal. |
| 6.4.4 | 12-12-2021 | Ya |  |
| 6.4.3 | 30-11-2021 |  | Perbaikan stabilitas untuk MacOS 10.14.6 dengan xcframework. |
| 6.4.2 | 28-10-2021 | Ya |  |
| 6.4.1 | 24-10-2021 |  | Stabilitas teratasi di aplikasi Unity. |
| 6.4.0 | 12-09-2021 |  | **API yang Ditambahkan:** `setSharingFilterForPartners` memungkinkan Anda untuk mengonfigurasi mitra mana yang SDK harus kecualikan dari pembagian data.<br /><br />Pada versi ini, `setSharingFilter` dan `setSharingFilterForAllPartners` tidak dapat digunakan lagi. |
| 6.3.5 | 19-08-2021 |  | **API yang Ditambahkan**: `setCurrentDeviceLanguage`<br /><br />Mulai versi ini, bahasa tidak lagi dikumpulkan secara otomatis oleh SDK. |
| 6.3.4 | 21-07-2021 |  | <ul><li>**Perbaikan Bug:** Memperbaiki masalah menjalankan SDK pada Simulator XCode 12.5</li><li>Perbaikan dan pembaruan kecil.</li></ul> |
| 6.3.2 | 2021-06-17 |  | Log debug yang ditingkatkan. |
| 6.3.1 | 2021-06-02 | Ya | Stabilitas yang ditingkatkan di plugin Unity. |
| 6.3.0 | 13-05-2021 |  | <ul><li>Dukungan Apple Silicon: Menambahkan dukungan untuk menjalankan SDK pada simulator menggunakan mesin Mac dengan chipset M1</li><li>Mulai versi ini, SDK mendukung iOS `9`+. iOS `8` tidak lagi didukung.</li><li>SDK Mode Ketat iOS: Menambahkan dukungan untuk manajer ketergantungan Carthage</li><li>Pembaruan teknis ke API OneLink</li></ul> |
| 6.2.6 | 25-04-2021 |  | <ul><li>Perbaikan bug: Aturan SKAdNetwork tidak dimuat ketika inisialisasi SDK terjadi setelah `didFinishLaunchingWithOptions`</li><li>Perbaikan bug: kasus ekstrem `waitForATTUserAuthorization` menyebabkan event peluncuran dikirim tanpa IDFA, bahkan jika persetujuan pengguna diberikan</li><li>Izinkan SDK berjalan di perangkat iOS 8</li><li>Pembersihan dan penghapusan kode dan data yang tidak digunakan</li></ul> |
| 6.2.5 | 06-04-2021 |  | Memfaktorkan ulang, membersihkan, menghapus data yang tidak digunakan dari SDK.<br /><br />Memulai versi ini:<ul><li>Metode `setShouldCollectDeviceName` tidak digunakan lagi dan tidak akan mengembalikan nama perangkat</li><li>Parameter `wifi` yang dikirim dari SDK disetel ke `False`</li></ul> |
| 6.2.4 | 15-03-2021 |  | Perbaikan bug terkait mode pengukuran pendapatan SKAdNetwork dan in-app event yang berisi parameter `AF_REVENUE`  .<br /><br />Mulai versi ini, dalam hal pengukuran pendapatan: event apa pun yang mencakup `AF_REVENUE` memengaruhi nilai konversi. Sebelum perubahan ini, nilai konversi ditetapkan hanya jika berada dalam kerangka event`AF_PURCHASE` . <br /><br />**Catatan:** Jika Anda menerapkan pengukuran Pendapatan SKAdNetwork, Anda harus melakukan upgrade ke versi ini. |
| 6.2.3 | 07-03-2021 |  | Perbaikan bug terkait dengan pemanggilan `updateConversionValue` SKAdNetwork. |
| 6.2.2 | 18-02-2021 | Ya |  |
| 6.2.1 | 15-02-2021 |  | Dukungan <Anchor target="_blank" href="/marketers/id/docs/server-to-server-events-api-for-mobile-s2s-mobile">Pelaporan Event oleh S2S</Anchor> |
| 6.2.0 | 07-02-2021 |  | API tambahan: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setpartnerdata">setPartnerData</Anchor> |
| 6.1.4 | 12-01-2021 | Ya |  |
| 6.1.3 | 24-12-2020 |  | <ul><li>API Tambahan: <Anchor target="_blank" href="/marketers/id/docs/additional-sdk-integration-guide#record-push-notifications">`addPushNotificationDeepLinkPath`</Anchor> (mendukung Movable Ink)</li><li>Dukungan <Anchor target="_blank" href="https://developer.apple.com/documentation/adservices">Kerangka Kerja Apple AdServices</Anchor></li></ul> |
| 6.1.2 | 03-12-2020 | Ya |  |
| 6.1.1 | 17-11-2020 |  | Perkenalkan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">SDK mode Ketat</Anchor> |
| 6.1.0 | 09-11-2020 |  | Dukungan <Anchor target="_blank" href="https://dev.appsflyer.com/docs/ios-unified-deep-linking">API tautan langsung terpadu</Anchor> |
| 6.0.8 | 28-10-2020 |  | Dukungan atribusi <Anchor target="_blank" href="/marketers/id/docs/apple-app-clips-integration-guide">Apple App Clips</Anchor> |
| 6.0.7 | 21-10-2020 | Ya |  |
| 6.0.6 | 20-10-2020 | Ya |  |
| 6.0.5 | 08-10-2020 | Ya |  |
| 6.0.4 | 30-09-2020 |  | Mendukung beberapa pengalihan dari ESP |
| 6.0.3 | 06-09-2020 |  | <ul><li>Perubahan nama API:<br />waitForAdvertisingIdentifier --> waitForATTUserAuthorization</li><li>SDK mengumpulkan IDFA secara default untuk iOS 14 (seperti untuk versi iOS sebelumnya)</li></ul> |
| 6.0.2 [tidak digunakan lagi] | 27-08-2020 |  | <ul><li>Perubahan nama API:<br />deviceLoggingDisabled --> anonymizeUser</li><li>Dialog AppTrackingTransparency (ATT) diperlukan untuk mengumpulkan IDFA untuk iOS 14</li><li>Dukungan yang ditambahkan untuk atribusi lintas promosi IDFV</li></ul> |
| 6.0.1 beta<br /><br />[tidak digunakan lagi] | 06-08-2020 |  | <ul><li>Dukungan ditambahkan untuk <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide">atribusi SKAdNetwork</Anchor>, untuk membantu pemasang iklan untuk mengukur keberhasilan kampanye sekaligus menjaga privasi pengguna</li></ul> |
| 6.0.0 beta<br /><br />[tidak digunakan lagi] | 04-08-2020 |  | <ul><li>Kemampuan debugging yang diperluas</li><li>Perubahan besar pada fungsionalitas SDK dan API. [Pelajari lebih lanjut](/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes)</li></ul> |

<div id="ios-v600-release-notes" />

<Accordion title="Catatan rilis iOS V6.0.0">

### Metode ditambahkan, dihapus, atau diganti namanya

#### Metode ditambahkan

Metode berikut telah ditambahkan ke SDK:

* waitForAdvertisingIdentifier

#### Metode dihapus

Metode berikut ini sudah dihapus dari SDK:

* disableAppleAdSupportTracking

#### Metode diganti namanya

| Nama API (sebelum V6) | Nama API saat ini (V6 dan versi lebih baru) |
| --- | --- |
| AppsFlyerTracker | AppsFlyerLib |
| disableIAdTracking | disableCollectASA |
| trackAppLaunchWithCompletionHandler | startWithCompletionHandler |
| trackLocation | logLocationEvent |
| trackAppLaunch | start |
| trackEvent | logEvent |
| disableAppleAdSupportTracking | disableAdvertiserIdentifier |
| validateAndTrackInAppPurchase | validateAndLogInAppPurchase |
| isStopTracking | isStopped |
| deviceTrackingDisabled | deviceLoggingDisabled |
| sharedTracker (Objective C) | shared |

### Dukungan Transparasi Pelacakan Aplikasi (ATT)

iOS SDK mendukung pengumpulan IDFA di iOS 14+ melalui kerangka kerja Transparansi Pelacakan Aplikasi. Untuk detail lebih banyak:

* <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">Mengonfigurasi dukungan ATT di iOS SDK</Anchor>
* <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#customize-att-consent-dialog">Kustomisasi dialog persetujuan ATT</Anchor>

</Accordion>

## iOS SDK V5

<div id="ios-sdk-v5::7a4821ba" />

<Accordion title="iOS SDK V5">

| Versi | Tanggal rilis | Catatan |
| --- | --- | --- |
| 5.4.4 | 23-08-2020 | Perbaikan bug dan pemeliharaan |
| 5.4.3 | 30-07-2020 | <ul><li>Kapabilitas logging dan debugging yang diperluas</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 5.4.1 | 30-06-2020 | <ul><li>Mengizinkan pemasang iklan untuk mengontrol pembagian data dengan mitra/jaringan terintegrasi. <Anchor target="_blank" href="/marketers/id/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">Pelajari lebih lanjut</Anchor></li><li>Metode onAppOpenAttribution ditingkatkan untuk URL panjang Tautan Universal: Parameter tautan yang dikembalikan sudah diuraikan</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 5.4.0 | 03-06-2020 | Dukungan proyek MAC Catalyst |
| 5.3.0 | 27-04-2020 | <ul><li>Mengakses data konversi deep linking langsung yang terbaru kapan pun, melalui metode onAppOpenAttribution</li><li>Parameter tambahan tersedia untuk tayangan promosi silang</li><li>Aplikasi utama dan ekstensi aplikasi mendapatkan ID AppsFlyer yang sama, sehingga in-app event dikelompokkan dengan cara yang mirip</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 5.2.0 | 10-03-2020 | <ul><li>Kapabilitas logging dan debugging yang diperluas</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 5.1.0 | 23-12-2019 | <ul><li>Peningkatan Obj-C - Interoperabilitas cepat</li><li>Perbaikan bug dan pemeliharaan</li></ul> |

</Accordion>

<div id="ios-v500-release-notes" />

<Accordion title="Catatan rilis iOS V5.0.0">

### Waktu respons SDK yang sudah ditingkatkan

Dimulai dengan SDK V5.0.0 waktu respons GCD yang sudah ditingkatkan untuk penginstalan organik.

### Metode dihapus atau diubah namanya

#### Nama metode berubah

Nama metode data konversi penginstalan sekarang sama untuk Android dan iOS. Hal ini berdampak pada metode yang menangani:

* Data konversi diinstal
* Kesalahan jika data tidak tersedia

| Nama Android sebelum SDK V5 | Nama iOS sebelum SDK V5 | Nama standar |
| --- | --- | --- |
| `onInstallConversionDataLoaded` | `onConversionDataReceived` | `onConversionDataSuccess` |
| `onInstallConversionFailure` | `onConversionDataRequestFailure` | `onConversionDataFail` |

#### Metode dihapus

Metode-metode berikut ini tidak digunakan lagi di versi SDK sebelumnya. Metode-metode tersebut sekarang telah dihapus dari SDK.

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

Dimulai dengan versi ini, semua parameter dikembalikan, termasuk yang tanpa nilai. Parameter tanpa nilai memiliki nilai null.

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
>       "is_first_launch": true,
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
>       "is_first_launch": true,
>       "retargeting_conversion_type": "none"
>   }
> ```
>
> </Tab>
> </Tabs>
>

GCD mengembalikan struktur yang sama terlepas dari datanya. Jika sebuah parameter kosong,  itu termasuk dalam GCD dengan nilai null. Hal ini memudahkan pengembang untuk memproses GCD tanpa harus menyesuaikan logika pemrosesan GCD, terlepas dari apakah parameter tertentu disertakan atau tidak. Untuk mempelajari lebih lanjut tentang data konversi dalam berbagai skenario, lihat <Anchor target="_blank" href="/marketers/id/docs/conversion-data-payloads-and-scenarios">di sini</Anchor>.

</Accordion>

<div id="deprecated-versions" />

<Accordion title="Versi yang sudah tidak digunakan">

Bacaan terkait: <Anchor target="_blank" href="/marketers/id/docs/appsflyer-sdk-version-control-policy">Kebijakan kontrol versi SDK AppsFlyer</Anchor>

| Versi | Tanggal Rilis | Catatan |
| --- | --- | --- |
| 5.0.0 | 12-11-2019 | <ul><li>Perbaikan bug dan pemeliharaan</li><li>Perubahan besar pada fungsionalitas SDK dan API. [Pelajari lebih lanjut](/docs/appsflyer-ios-sdk-release-notes#ios-v500-release-notes)</li></ul> |
| 4.11.2 | 07-11-2019 | Perbaikan bug dan pemeliharaan |
| 4.11.1 | 31-10-2019 | Perbaikan bug dan pemeliharaan |
| 4.11.0 | 17-10-2019 | <ul><li>Dukungan yang dihentikan untuk iOS 7. iOS 8 adalah versi minimum yang didukung saat ini.</li><li>Peningkatan logging untuk kemampuan debug yang lebih baik, penyelesaian ESP dan Tautan Bermerek serta untuk onInstallConversionData dan onAppOpenAttribution.</li><li>Peningkatan pengambilan Apple Search Ads.</li></ul> |
| 4.10.4 | 12-09-2019 | <ul><li>Pembaruan untuk pengambilan token push iOS 13 diperlukan untuk Pengukuran Penghapusan Instalasi</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 4.10.3 | 16-07-2019 | Perbaikan bug dan pemeliharaan |
| 4.10.2 | 02-07-2019 | Perbaikan bug dan pemeliharaan |
| 4.10.1 | 01-07-2019 | Perbaikan bug dan pemeliharaan |
| 4.10.0 | 14-05-2019 | <ul><li>API trackAppLaunchWithCompletionHandler untuk menangani keberhasilan atau kegagalan peluncuran pelacakan aplikasi</li><li>API completionHandler untuk menangani keberhasilan atau kegagalan pencatatan in-app event</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 4.9.0 | 18-03-2019 | <ul><li>setResolveDeepLinkURLs API untuk menyelesaikan OneLink yang dibungkus dengan Tautan Universal lainnya</li><li>Menghapus penggunaan UIPasteboard untuk atribusi Meta ads untuk iOS 7 dan yang lebih lama</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 4.8.12 | 13-02-2019 | <ul><li>Peningkatan kemampuan peringkat nol untuk penyedia seluler</li><li>Peningkatan kemampuan peringkat nol untuk penyedia seluler</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 4.8.11 | 09-01-2019 | <ul><li>API waitForCustomerUserId() merusak generateLink yang tetap</li></ul> |
| 4.8.10 | 31-10-2018 | <ul><li>Memperbaiki kondisi balapan ketika continueUserActivity dipanggil setelah applicationDidBecomeActive menyebabkan onAppOpenAttribution tidak dipanggil</li><li>validasiDan ValidasiTrackInAppPurchase mengabaikan perbaikan parameter tambahan</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 4.8.9 | 27-08-2018 | <ul><li>Event SDK baru: Berlangganan, Mulai Uji Coba, Klik Iklan, Tampilan Iklan</li><li>Perbaikan bug dan pemeliharaan</li></ul> |
| 4.8.8 | 30-07-2018 | <ul><li>Memperbaiki masalah saat menggunakan is\_first\_launch melalui JSONSerialiser dikembalikan sebagai bilangan bulat, bukan boolean</li><li>Perbaikan bug dan pemeliharaan 4.8.7</li></ul> |
| 4.8.7 | 22-07-2018 | Perbaikan bug dan pemeliharaan |
| 4.8.6 | 18-06-2018 | Perbaikan bug dan pemeliharaan |
| 4.8.5 | 29-05-2018 | Perbaikan bug dan pemeliharaan |
| 4.8.4 | 03-05-2018 | Perbaikan bug dan pemeliharaan |
| 4.8.3 | 25-01-2018 | <ul><li>Perbaikan bug dan pemeliharaan</li><li>API shouldCollectDeviceName</li><li>parameter event af\_content</li><li>API shouldCollectDeviceName</li><li>parameter event af\_content</li></ul> |

</Accordion>

## Checksum SDK iOS

AppsFlyer menggunakan checksum md5:

<div id="v6-checksums" />

<Accordion title="checksum V6">

| Versi SDK iOS | Static Lib | Static Framework |
| --- | --- | --- |
| 6.6.1 | ff41a3dfeb9fe7579f8f706f3c62bbbc | 7acf1f10de7602b363a70d4a710b050d |
| 6.6.0 | ba2d2d0b64f3b0f6476b818c1b8faf5f | 544c7c7e4af29afa4100b6c43affcf8f |
| 6.5.4 | 5a1146a95abc84b20940b43cacc8b42a | 3a0a22a28b4082a5b2f0931104b0a9c8 |
| 6.5.3 | b33008f83f5eafa864902db97c003c06 | 3ff6754c8c238dd13e4c6251ffb4aedf |
| 6.5.2 | 3083df065d14553fb1b4e34f3f7fb381 | 3ce0ea75e4fe3cf6313fde27d57d20ed |
| 6.5.1 | 8d91f52cc2df073d1bca9919b44aeeeb | c9353bdfa71ff9b4acc9097eee83d35e |
| 6.5.0 | 4b72dcf125430d3d374967df5e084c6a | 5d6ac0e9f7a1430e106685da117a7716 |
| 6.4.4 | 86586acda674d95f5661a613dccea3dd | 7f4c431de13b84fd0926132c2154f0a8 |
| 6.4.3 | dd5fcf42065ba2ad28f6311153fd4752 | 178274e63a6aa604682a3095ddf59ac5 |
| 6.4.2 | 2341911e4f34d17560b85409b86528c4 | 46df5badc29ee983a872d7859cedd59a |
| 6.4.1 | 4ef6e6d424bc9b95a1ee8ebda0d5c639 | 0efc4140b47cbaf65b24a9087c61c434 |
| 6.4.0 | 9210f7064a7692c8dff7a779043e97fc | f103763da687fef88db60ca6b395dc41 |
| 6.3.5 | b61193ab28a601ec0dfaf4aa641a7834 | 9fbbf0f4cb865c95d919396d2af9a053 |
| 6.3.4 | 9cca998fde11c473e60bee3854f0c0da | c47a02177c28290ed8c934a6428dc0dc |
| 6.3.2 | c563e2b8ee4bf6647e496d1b0ad31285 | 5c474247d3ce607fca43af9c9faf1fbc |
| 6.3.1 | e04a567680676b3784079d35ca32b5fe | 36b808db3952803c929188ca57fe88c6 |
| 6.3.0 | baa5e6d82a363e636740d6c5494e107d | f2ebe86a93a2fd5122ad11224f17736c |
| 6.2.6 | 9b989e131fe596b51223b6f47efac3c6 | 6396371abf0f66f0e6aeccd8303eeb0a |
| 6.2.5 | 5b23262cb4b15230e262005b648aff0d | 85ec7457b36de4402ce2c4b591fa87ab |
| 6.2.4 | f61648cd99d94c05d50a6e3213329779 | 3b20d45695f5e196e78d3db6c2bd738d |
| 6.2.3 | 51eaa0654ec83db7da31511092312f00 | d540bdc543a06ff5ccd40f90b2078557 |
| 6.2.2 | 9e5ceb08a3121f42b3315da87c698af3 | 08917804e4fe48bcb797f391d5a111f6 |
| 6.2.1 | cbfe915e31bc06bb28227cb33ed22304 | abfa9d9dc81fd90b0ca65de973fb1ab8 |
| 6.2.0 | 652ee1362af8c93119335a337deba1a5 | 91bb64493b344b010ebc277c849e9234 |
| 6.1.4 | 7e2e74d3cc186807d73c1fcf57f8b117 | 6c9b4ed760c9c1139681f61e6a508c8e |
| 6.1.3 | 749e6c3de91afdfcddec91d290c46807 | ab5884cb0c1ea00c3b3fe9a1d26a4511 |
| 6.1.2 | 940da06a6f8f7e3931a2a80f4e8defc9 | 4d39c9e6d46c49b5bde2c5ff19781957 |
| 6.1.1 | 7d259bd1cc5e5d2c3fea4909953375ba | 09a273cf0300656ed995405e41eced58 |
| 6.1.0 | e95e509d48e7b87e0213c7f12ea253e4 | 2c87f3a79c9318a4ed49ad8c377b007f |
| 6.0.8 | d903e6c145492488e126e46b3a233444 | 3237e91d12ee0871ceb0f6a0829dd43b |
| 6.0.7 | 2d83f856d8d34c4f2e0e4e8561ddee05 | bbb742ded1e49eae0622deb40c3becc3 |
| 6.0.6 | 1dd3bfc9919db8ccb7c0de8cf6505d47 | 5d5e5fe1624123f8316c6bdc020aa47b |
| 6.0.5 | e8afac7ef0bc7e38432bf5187fcbde7d | 41966239e783ce0bbba852471a439caa |
| 6.0.4 | a88278fdb8c2f504ecb4406b8fbc1fe4 | a7bba01c6484baf721f5be51242c492b |
| 6.0.3 | 9f0cfed3c889ba3e334857c6d81e26be | 13b07e2da8316759a8f84efb2476e854 |
| 6.0.2 |  | 13936cb4e05221e134ae1539971b9317 |
| 6.0.1 beta |  | 6167276b56ac3b1fbdad2a4858b17bf3 |

</Accordion>

<div id="v5-checksums" />

<Accordion title="checksum V5">

| Versi SDK iOS | Static Lib | Static Framework |
| --- | --- | --- |
| 5.4.4 | 47d90cbc4ed48dd1c5d6f42a8d419e8b | 93716e13258fce87c81c0fc604bfd6fd |
| 5.4.3 | e5691c3ae1f20726168b4eb221937d98 | dbfa30607f44fa2819191c7a8d7a3fe4 |
| 5.4.1 | 61564250f26ab0693255e002873d1674 | fc86776f0ffcdf65cc49f33f7d943258 |
| 5.4.0 | fa835b3577f389a12ef635eea0b000bb | 0bd6a7b4441dc8f397831533e719a833 |
| 5.3.0 | e787da7334e6c68e0098fd53ebea285e | 2f160176b1c011f9aca558543cd63190 |
| 5.2.0 | 057c18bb7485e1c06f2b452d80ee5b22 | 736b50840b8c08093401f3bba2c4389b |
| 5.1.0 | f39819c11b06f98ff24e39cbd0f0f6ce | 39889a253dafcfb2d53151523c1c1d80 |
| 5.0.0 | 5ac9e35af65fbfcaf81c1f63a36542b9 | 1727be9fa19906f0c1e1907b4b160086 |

</Accordion>

<div id="v4-checksums" />

<Accordion title="checksum V4">

| Versi SDK iOS | Static Lib | Static Framework |
| --- | --- | --- |
| 4.11.2 | f5415c2014402a03b8ca2c9901ddf12d | 3fcf5afd6a20f353f7f88f1fbb4d4410 |
| 4.11.1 | 716394142df4d8e7a98e2c11cfe92ed1 | e6521d8216d3aa8d681ac74e279dab34 |
| 4.11.0 | e7238410372dfa7ca65e5839a31b1c2e | c6d3283bf69adb75aa9ed6c43195a3d6 |
| 4.10.0 | 4d5c01129b80d7ad182e32cf3b47faa4 | da926eeb09d61f68f2076a9b31c30d7a |
| 4.9.0 | d283ace3237479d1aabc2a81271ea5ba | bad6d9b8c627d7450e7acc8165b05618 |
| 4.8.9 | e9640a7f95257a89c3e99215df79f1df | fb0975064d2b93cedb71ce248cf3afb9 |
| 4.8.4 | b7748ea6b86afbc295e17bac3d5bdda6 | 4cd7a95f49cfb79ecd9a0ce0c73750a3 |
| 4.8.3 | 51d38c4b77f39c75c5fc5734165fedc2 | 23096a32726a9def3e215a761bf7ad30 |
| 4.8.2 | 0908336d4e9bcf4de1d5f4f2e37ad0cb | a386cfadd76fd783e6a10d0cd8fcb685 |
| 4.8.1 |  | 3b8a7d70b96bd7c5718feafeb31296b9 |
| 4.8.0 | bb1358226bd3ca70d70f4717b62ca38b | 3d81144bb653e91cb624778c87641051 |
| 4.7.9 | e9183f23954a3f42a9fa6ae3eeebb6df | 03905309048e26e9be7ee02895532d11 |
| 4.7.8 | 5595fa7dfc4c13b4a955638ba1da062e | 61c30629f3dcb5ae48da10a458e80d28 |
| 4.7.7 | 3a8d0be3b304de5e81c967ab8a465de3 | b8dd0ee60c75aa30884f56569068f32e |
| 4.7.6 | 6cc80a31cf9daae5709a22258f434c6d | 3d4607b13b6f138264db703e36f5452e |
| 4.7.3 | 73db4e0173fcfdb758644b08fdbbd7bf | 06572392afe0ae28a814601642963469 |
| 4.7.2 | 14a79e4ecffad264bc62b307d2db23a7 | 0aae1d0ace09e5b092f9906747119cfd |
| 4.7.11 | 27e228c921f560205c0ad2c7962e83b2 | d94cdab5734a88598cfcc078573e5b21 |
| 4.7.10 | 5cb1275b488369fee4713d21812186a0 |  |
| 4.7.1 | b121dfdf8d0dc53d031481114eba0c18 | 74ac06d17f167a0e22c361e06f4a2554 |
| 4.7.0 | c3c0a453caa9971492ef8acd8bee04ae | cadeab0479c4a723173943d77d253051 |

</Accordion>

<div id="see-also" />

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/about-att-and-skan">Panduan memulai cepat untuk iOS 14, ATT, dan SKAdNetwork</Anchor>

<div data-zendesk-anchors="01H8W3DDM1BYRSPMFTA3TCY8EQ=ios-sdk-v6 01EEYC8A6FEW8WN28KQ9CKX0G7=ios-v600-release-notes methods-added-removed-or-renamed=metode-ditambahkan-dihapus-atau-diganti-namanya 01EEYC8A6FD7JZK1A63EF675HJ=metode-ditambahkan-dihapus-atau-diganti-namanya methods-added=metode-ditambahkan 01EEYC8A6FKPYQ35EKVW7X0EC0=metode-ditambahkan methods-removed=metode-dihapus 01EEYC8A6FNJ91R15X633BHSXF=metode-dihapus methods-renamed=metode-diganti-namanya 01EEYC8A6F8PB4C94Z14KXYD68=metode-diganti-namanya app-tracking-transparency-att-support=dukungan-transparasi-pelacakan-aplikasi-att 01EEYC8A6G19ER7FGWQ51XPGJF=dukungan-transparasi-pelacakan-aplikasi-att 01EEYC8A6GYYRK4F7CVT7YMTHJ=ios-sdk-v5 01H8W3DDM19M6R8AV62WKZ931G=ios-sdk-v5::7a4821ba 01EEYC8A6GR18M6KN5D2ZV2573=ios-v500-release-notes improved-sdk-response-time=waktu-respons-sdk-yang-sudah-ditingkatkan 01EEYC8A6GF3MF7GJZWCE9TY88=waktu-respons-sdk-yang-sudah-ditingkatkan methods-removed-or-renamed=metode-dihapus-atau-diubah-namanya 01EEYC8A6G3KWSZ3FGKF904QM1=metode-dihapus-atau-diubah-namanya method-name-changes=nama-metode-berubah 01EEYC8A6G1EFHXBMW229RTKYA=nama-metode-berubah methods-removed::92ba13cc=metode-dihapus-1 01EEYC8A6GE57XWGHTNQSAN516=metode-dihapus-1 changes-to-get-conversion-data-format=perubahan-untuk-mendapatkan-format-data-konversi 01EEYC8A6HVPFA5K349KHT5B3T=perubahan-untuk-mendapatkan-format-data-konversi 01EEYC8A6HG072RP472KEQ74S8=contoh 01H8W3DDM1G62RTK2S3XEG3KGT=deprecated-versions ios-sdk-checksums=checksum-sdk-ios 01EEYC8A6J6VF2WEPFEC9JRVA9=checksum-sdk-ios 01EEYC8A6J77PYMCNDEGWZD3FJ=v6-checksums 01EEYC8A6JGHWTNJY0C06PD7H6=v4-checksums h_01HE7RE2EPQX872DKNDBJ2G2QE=lihat-juga" />
