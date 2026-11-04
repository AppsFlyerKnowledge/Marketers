---
title: Tinjauan integrasi SDK
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Integration
    - Advertisers
    - firetv
    - fire tv
    - Advertiser
    - Developer
    - appuid
    - anonymous
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2012-12-26T14:34:58Z'
  edited_at: '2023-11-13T14:55:05Z'
  id: 207032126
  locale: id
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/id/articles/207032126
---
> **Sekilas:** Pelajari tentang fungsionalitas SDK AppsFlyer yang tersedia dan tentukan API mana yang Anda inginkan untuk digunakan oleh aplikasi Android atau iOS Anda.

Tonton video ini untuk mendapatkan gambaran besar tentang integrasi SDK.

<Embed title="Tinjauan integrasi SDK" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/4iybquc6q3" providerUrl="https://fast.wistia.com" />

<div id="about-the-sdk" />

## Tentang SDK

SDK menyediakan fungsi penginstalan aplikasi dan perekaman event. Anda dapat merekam penginstalan, sesi, dan peristiwa dalam aplikasi. In-app event mencakup, misalnya, pembelian dalam aplikasi atau naik level dalam game. Merekam event ini dapat membantu Anda mengevaluasi ROI dan kualitas pengguna. 

Artikel ini menjelaskan proses integrasi SDK V6+ dan membantu manajer produk pengiklan (pemilik aplikasi) merencanakan integrasi SDK AppsFlyer dengan aplikasi Android atau iOS mereka.

Dokumentasi tambahan mencakup hal-hal berikut:

<Tabs>
<Tab title="Android native,">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk">Dokumentasi penginstalan SDK untuk pengembang</Anchor>
* <Anchor target="_blank" href="/marketers/id/docs/appsflyer-android-sdk-release-notes">Catatan rilis</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference">Dokumentasi referensi SDK untuk programmer</Anchor>
* <Anchor target="_blank" href="/marketers/id/docs/fill-out-google-safety-section-form">Bagian keamanan data di Google Play</Anchor>

</Tab>

<Tab title="iOS native,">

* <Anchor target="_blank" href="/marketers/id/docs/updating-to-ios-sdk-v6-and-plugins">Pembaruan ke SDK iOS V6</Anchor>. Perhatikan bahwa SDK iOS V5.4.4 beroperasi secara penuh dengan iOS 14. Namun, sebaiknya adopsi SDK V6.X untuk memastikan kompatibilitas dengan rilis iOS di masa mendatang.
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">Dokumentasi penginstalan SDK untuk pengembang</Anchor>
* <Anchor target="_blank" href="/marketers/id/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes">Catatan rilis</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference">Dokumentasi referensi SDK untuk programmer</Anchor>
* <Anchor target="_blank" href="/marketers/id/docs/preparing-for-the-app-store-review-nutrition-labels">Mempersiapkan peninjauan App Store — label nutrisi</Anchor>

</Tab>

<Tab title="Unity">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">Dokumentasi penginstalan SDK untuk pengembang</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api">Dokumentasi referensi SDK untuk programmer</Anchor>

</Tab>

<Tab title="React Native">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">Dokumentasi penginstalan SDK untuk pengembang</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api">Dokumentasi referensi SDK untuk programmer</Anchor>

</Tab>
</Tabs>

<div id="sdk-compatibility" />

## Kompatibilitas SDK

SDK iOS AppsFlyer kompatibel dengan platform berikut:

<Tabs>
<Tab title="Android">

* Memulai Android V4.0
* Platform berbasis Android non-seluler seperti Smart TV, (termasuk Amazon Fire TV). <Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-platform-attribution-concepts">Lihat tinjauan CTV</Anchor>
* <Anchor target="_blank" href="/marketers/id/docs/set-up-multi-store-android-attribution">Toko aplikasi selain Play Store</Anchor> untuk aplikasi Android, seperti Amazon dan Baidu

</Tab>

<Tab title="iOS">

* iOS 9+ (iPhone, iPod, iPad)
* tvOS 9+ (Apple TV)
* Sesuai dengan jaringan Apple <Anchor target="_blank" href="https://developer.apple.com/library/content/documentation/NetworkingInternetWeb/Conceptual/NetworkingOverview/UnderstandingandPreparingfortheIPv6Transition/UnderstandingandPreparingfortheIPv6Transition.html#//apple_ref/doc/uid/TP40010220-CH213-SW1">IPv6 DNS64/NAT64</Anchor>.

SDK mendukung <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model">beberapa metode atribusi</Anchor>. Metode atribusi yang digunakan bergantung pada hal-hal berikut:

* Versi iOS yang diinstal di perangkat pengguna
* Versi SDK iOS yang diinstal di aplikasi

<table><thead><tr><th><span>Metode atribusi yang didukung</span></th><th><span>Versi iOS</span></th><th><span>Dukungan SDK iOS</span></th><th><span>Catatan</span></th></tr></thead><tbody><tr><td rowspan="2"><span>Pemodelan probabilistik</span></td><td><p><span>8 – 14.4</span></p></td><td>5.0.0+</td><td> </td></tr><tr><td><p><span>14.5+</span></p></td><td><span> 6.0.3+</span></td><td><span>Pemodelan probabilistik terbatas pada konteks media yang dimiliki, promosi silang, serta alur web-ke-aplikasi yang disetujui.</span></td></tr><tr><td rowspan="2"> <span>Pencocokan ID</span><br/><span><br/></span> </td><td><span>8 - 13</span></td><td>5.0.0+</td><td><span>Pengguna dapat menonaktifkan Batas Pelacakan Iklan/Limit Ad Tracking (LAT).</span></td></tr><tr><td><span>14.5+</span></td><td><span>6.0.3+</span></td><td><p>Transparansi Pelacakan Aplikasi (ATT) dan persetujuan pengguna diperlukan. Untuk informasi lebih lanjut, lihat <a href="./basic-sdk-integration-guide#configure-app-tracking-transparency-att-support" target="_blank">mengonfigurasi SDK iOS untuk mendukung ATT</a>.</p></td></tr><tr><td rowspan="2"><p><a href="./skadnetwork-skan-solution-guide" target="_blank"><span>SKAdNetwork</span></a></p></td><td><p><span>11.3 - 13</span></p></td><td rowspan="2"><p><span>6.2.3</span><br/><span><br/></span></p></td><td><p>Solusi SKAdNetwork (SKAN) <span>sebatas memasang atribusi sesuai dengan </span> <a href="https://developer.apple.com/documentation/storekit/skadnetwork" target="_blank">spesifikasi SKAN</a> <span>, artinya tidak ada nilai konversi.</span></p></td></tr><tr><td><p><span>14+</span></p></td><td><ul><li>SKAN selalu tersedia di level iOS dan SDK, apa pun pengaturan ATT-nya.</li><li>Pemasar mengaktifkan SKAN di dashboard AppsFlyer.</li></ul></td></tr></tbody></table>

Mulai dari SDK V6.0.8, <Anchor target="_blank" href="/marketers/id/docs/apple-app-clips-integration-guide">Atribusi Apple App Clips</Anchor> tersedia. Anda juga dapat membaca <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/apple-app-clips">postingan blog</Anchor> kami tentang Apple App Clips.

</Tab>
</Tabs>

<div id="sdk-integration" />

## Integrasi SDK

Proses menginstal dan mengintegrasikan SDK memerlukan kerja sama antara manajer produk dan pengembang aplikasi seluler.  **Sebelum** mengintegrasikan SDK dengan aplikasi Anda, tinjau semua tugas integrasi dan pertimbangkan fungsionalitas yang Anda inginkan untuk digunakan oleh aplikasi Anda.

<div id="sdk-planning-checklist" />

### Daftar periksa perencanaan SDK

Untuk memulai, kami telah menyiapkan <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTD4OimHC93iw2AJCcAY45yAc9lOBfJe8PskI_0NFZTnWnrIq1hjPBvCztkbom9acMDDd4d1d5mMFfi/pub?output=xlsx">daftar periksa</Anchor> untuk membantu memandu Anda melalui proses perencanaan. Untuk setiap tugas, ada tautan ke dokumentasi pemasar dan programmer.

<div id="sdk-integration-tasks" />

### Tugas integrasi SDK

Integrasi SDK dasar mencakup tugas-tugas berikut. Perkiraan waktu dimaksudkan sebagai panduan umum saja.

| Tugas integrasi SDK dasar | Waktu perencanaan |
| --- | --- |
| Ambil <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#mengambil-kode-pengembang">kode pengembang AppsFlyer</Anchor> dan kirimkan tautan beserta petunjuk penginstalan dan integrasi ke pengembang Anda. | 15 menit |
| Tinjau <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#atribusi">pertimbangan atribusi</Anchor> , dan tentukan pengenal perangkat mana yang akan dikumpulkan. | 30 menit |
| Tentukan <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#merekam-in-app-event">in-app event</Anchor> yang ingin Anda ukur, dan kirimkan nama event dan parameter event ke pengembang. | 1 jam |
| Tentukan metode <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#tautan-langsung-deep-linking-dengan-onelink">deep linking yang</Anchor> akan digunakan. | 30 menit |
| Tentukan metode untuk <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#mengakses-data-atribusi-dan-deep-linking">mengakses data atribusi</Anchor>. | 30 menit |
| Setelah integrasi dasar selesai, setiap pengguna akun dengan akses ke dasbor AppsFlyer dapat melakukan <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#menguji-integrasi-sdk-anda">pengujian dasar</Anchor> .<br /><br />Pengembang dapat memanfaatkan log debug di <Anchor target="_blank" href="/marketers/id/docs/testing-the-sdk-integration-for-marketers#pengujian-di-lingkungan-pengembangan">lingkungan pengembangan</Anchor>. | 1 jam |

Anda dapat bekerja sama dengan pengembang seluler untuk menerapkan API tambahan berikut di SDK:

| Tugas integrasi SDK tambahan | Waktu perencanaan |
| --- | --- |
| Tentukan apakah aplikasi Anda memerlukan <Anchor target="_blank" href="/marketers/id/docs/additional-sdk-integration-guide#metode-atribusi-tambahan">penyiapan atribusi tambahan</Anchor> (misalnya, uninstal pengukuran atau instal atribusi untuk toko aplikasi pihak ketiga). | 30 menit |
| Tentukan <Anchor target="_blank" href="/marketers/id/docs/additional-sdk-integration-guide#sesi">pelaporan sesi pengguna</Anchor> . | 30 menit |
| Tentukan metode atribusi yang akan digunakan untuk <Anchor target="_blank" href="/marketers/id/docs/additional-sdk-integration-guide#media-yang-dimiliki-sendiri">sumber media yang dimiliki</Anchor> . | 1 jam |
| Kelola <Anchor target="_blank" href="/marketers/id/docs/additional-sdk-integration-guide#privasi-pengguna">kebijakan privasi pengguna</Anchor> untuk memastikan aplikasi Anda mematuhi peraturan privasi (GDPR, CCPA). | 1 jam |

<div id="note" />

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-platform-attribution-concepts">Ikhtisar platform CTV, PC, dan konsol</Anchor>

<div data-zendesk-anchors="about-the-sdk=tentang-sdk h_01H9FHRVKE6BHGW05G6YMKF737=tentang-sdk sdk-compatibility=kompatibilitas-sdk h_01H9FHRVKEQ837Q0GFECNPPAN2=kompatibilitas-sdk sdk-integration=integrasi-sdk h_01H9FHRVKEN0MMGTSD362FTWPS=integrasi-sdk sdk-planning-checklist=daftar-periksa-perencanaan-sdk h_01H9FHRVKE468M1RTMF7VTYV1R=daftar-periksa-perencanaan-sdk sdk-integration-tasks=tugas-integrasi-sdk h_01H9FHRVKERHXY19R97EN86EGP=tugas-integrasi-sdk h_01H9FHRVKE88CXGH8G7E26ZXT2=lihat-juga" />
