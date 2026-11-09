---
title: Kerangka Privasi Lanjutan Gabungan
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Agencies
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2021-03-15T11:32:31Z'
  edited_at: '2023-11-15T15:23:20Z'
  id: 360018515798
  locale: id
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/id/articles/360018515798
---
> **Sekilas:** Dimulai dengan ketersediaan umum iOS 14.5+ dan pemberlakuan ATT oleh Apple, pemasang iklan menggunakan kerangka kerja Privasi Lanjutan Gabungan (AAP) untuk mengontrol ketersediaan data atribusi tingkat pengguna dari platform.

<div id="aggregated-advanced-privacy-aap-framework" />

## Kerangka Privasi Lanjutan Gabungan (AAP).

Kerangka kerja Privasi Lanjutan Gabungan (AAP) AppsFlyer mencegah pelacakan di seluruh aplikasi dan situs web yang dimiliki oleh berbagai perusahaan dan kemampuan untuk mengidentifikasi pengguna atau perangkat secara unik. AAP menggunakan tingkat privasi Transparansi Pelacakan Aplikasi Apple sebagai tolok ukur minimum untuk ambang perlindungan privasinya.

Framework ini memberi pemasang iklan kemampuan untuk mengontrol ketersediaan data atribusi tingkat pengguna melalui platform AppsFlyer.

Mulai dari  ketersediaan umum iOS 14.5 dan pemberlakuan ATT oleh  Apple, jika AAP aktif, data atribusi tingkat pengguna untuk pengguna yang tidak menyetujui yang menjalankan iOS 14.5+ tidak akan tersedia untuk pemasang iklan atau mitra. 

AAP tidak memengaruhi ketersediaan data atribusi gabungan dan laporan analitik untuk pemasang iklan dan mitra.

<div id="aap-impacted-features" />

### Fitur yang terpengaruh AAP

Jika AAP aktif, data yang diberikan oleh data lengkap akan terpengaruh dan beberapa kolom dibatasi atau tidak tersedia. Ini memengaruhi data yang disediakan oleh alat berikut:

* Data Locker
* API Pull data lengkap
* Push API
* Halaman ekspor dashboard
* Postback ke jaringan
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/deferred-deep-linking">Dapatkan API data konversi (GCD)</Anchor> dalam konteks API data tingkat pengguna sisi klien.

Ketersediaan data terpengaruh saat AAP aktif sebagai berikut:

* **Data atribusi dan penipuan (Protect360):** <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions">Beberapa bidang atribusi dibatasi atau tidak tersedia.</Anchor>
* **Data klik, impresi, dan klik yang diblokir (penipuan):** <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions#identifier-restriction">ID terkait pengguna dan perangkat</Anchor> tidak tersedia.
* **Deferred deep linking**: Jika Anda mengimplementasikan deferred deep linking di media berbayar, gunakan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unifieddeeplink">unified deep linking API (UDL).</Anchor> API lama, yang menggunakan GCD, tidak dapat digunakan dalam konteks pengguna yang tidak menyetujui. Dalam kasus media yang dimiliki, deferred deep linking untuk media yang dimiliki didukung melalui GCD dan deferred deep linking API terbaru.

<div id="data-availability-principles-in-aggregated-advanced-privacy" />

## Prinsip ketersediaan data dalam Privasi Lanjutan Gabungan

Saat AAP berlaku untuk data pengguna tertentu, ketersediaan data bergantung pada status ATT pengguna tersebut dan sumber media yang membawa pengguna tersebut.

**Definisi:**

* **Data atribusi tingkat pengguna:** Catatan data yang berisi pengidentifikasi tingkat perangkat yang terkait dengan atribusi di tingkat pengguna
* **Data atribusi terbatas untuk pemasang iklan:**

  * Tersedia: Pengidentifikasi tingkat perangkat. (IDFA tersedia jika izin pengguna diberikan.)
  * Tidak tersedia: Data atribusi diterima melalui tautan atribusi penerbit (misalnya, sumber media dan kampanye). <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions">Daftar bidang yang dibatasi dan tidak tersedia untuk pemasang iklan</Anchor> Sumber media terbatas AKA.
* **Data atribusi terbatas untuk mitra:**

  * Tersedia: Detail kampanye gabungan.
  * Tidak tersedia: Data tingkat pengguna yang dapat membantu mengidentifikasi pengguna seperti ID AppsFlyer, Data khusus, ID pengguna pelanggan (CUID), ID Klik, IDFA, IDFV, IMEI, Agen pengguna, dan alamat IP.

Istilah yang didefinisikan digunakan dalam gambar dan bagian berikut untuk mendeskripsikan data yang tersedia bagi pemasang iklan dan mitra.

<Image align="center" alt="Advanced Privacy Framework - Advertisers (4).png" src="https://files.readme.io/0291fe2eea5f6efc41f2338824a0017be3e265f502e0d3999d52ac87b1ee7719-35847850634897.png" />

Privasi Tingkat Lanjut berperilaku berbeda saat ditayangkan di web dan parameter af\_media\_type=web atau af\_media\_type=app harus digunakan. Lihat <Anchor target="_blank" href="/partners/id/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web-campaigns">di sini</Anchor> untuk informasi lebih lanjut.

<div id="paid-and-owned-media-data-availability" />

### Ketersediaan data media berbayar dan yang dimiliki

<div id="paid-media" />

<Accordion title="Media berbayar">

Media berbayar mencakup jaringan iklan seluler dengan integrasi di platform AppsFlyer tempat pemasang iklan menjalankan kampanye. 

<div id="paid-media-data-availability-by-att-status" />

#### Ketersediaan data media berbayar berdasarkan status ATT

<table><tbody><tr><th rowspan="2"><p><span>Jenis media:</span></p></th><th colspan="2"><p><span>Status ATT</span></p></th><th colspan="2"><p><span>Data tersedia untuk:</span></p></th></tr><tr><th><p><span>Aplikasi penerbit</span></p></th><th><p><span>Aplikasi pemasang iklan</span></p></th><th><p><span>Pemasang iklan</span></p></th><th><p><span>Ad Network</span></p></th></tr><tr><td rowspan="4"><p><span>Aplikasi</span></p></td><td><p><span>Diotorisasi</span></p></td><td><p><span>Diotorisasi</span></p></td><td><p><span>Data atribusi tingkat pengguna</span></p></td><td><p><span>Data atribusi tingkat pengguna</span></p></td></tr><tr><td><p><span>Tidak diotorisasi</span></p></td><td><p><span>Diotorisasi</span></p></td><td><p><span>Data atribusi terbatas untuk pemasang iklan </span></p></td><td><p><span>Data atribusi terbatas untuk mitra</span></p></td></tr><tr><td><p><span>Diotorisasi</span></p></td><td><p><span>Tidak diotorisasi</span></p></td><td><p><span>Data atribusi terbatas untuk pemasang iklan </span></p></td><td><p><span>Data atribusi terbatas untuk mitra</span></p></td></tr><tr><td><p><span>Tidak diotorisasi</span></p></td><td><p><span>Tidak diotorisasi</span></p></td><td><p><span>Data atribusi terbatas untuk pemasang iklan </span></p></td><td><p><span>Data atribusi terbatas untuk mitra</span></p></td></tr><tr><td rowspan="2"> <br/><p><span>Web</span></p></td><td><p><span>N/A</span></p></td><td><p><span>Diotorisasi</span></p></td><td><p><span>Data atribusi tingkat pengguna</span></p></td><td><p><span>Data atribusi tingkat pengguna</span></p></td></tr><tr><td><p><span>N/A</span></p></td><td><p><span>Tidak diotorisasi</span></p></td><td><p><span>Data atribusi terbatas untuk pemasang iklan </span></p></td><td><p><span>Data atribusi terbatas untuk mitra</span></p></td></tr></tbody></table>

</Accordion>

<div id="owned-media" />

<Accordion title="Media yang Dimiliki Sendiri">

Kerangka Apple AppTrackingTransparency hanya berlaku untuk data yang dikumpulkan dari berbagai perusahaan. Oleh karena itu, data atribusi tingkat pengguna media yang dimiliki tersedia untuk pemasang iklan terlepas dari status persetujuan ATT pengguna.

Media yang dimiliki termasuk kampanye pemasaran digital yang digunakan oleh pemasang iklan untuk menjangkau pelanggan. Ini termasuk kampanye email, promosi silang, pemberitahuan push, dan sebagainya. Di AppsFlyer, kampanye yang menggunakan jaringan iklan tidak dianggap sebagai media yang dimiliki.

</Accordion>

<div id="controlling-advanced-aggregated-privacy" />

## Mengontrol AAP

<div id="aap-central-switch" />

<Accordion title="Privasi Lanjutan Gabungan—pengaktifan tingkat aplikasi">

AAP adalah sakelar tingkat aplikasi yang mengontrol pengaturan Privasi Lanjutan untuk semua mitra aplikasi yang dipilih. Sakelar AAP terletak di halaman **Pengaturan Aplikasi** . Saat sakelar AAP aktif, sakelar **Privasi Lanjutan** untuk semua mitra aplikasi yang dipilih secara otomatis diaktifkan dan tidak dapat dimodifikasi. Saat nonaktif, pemasang iklan dapat membuka setiap integrasi mitra satu per satu dan mengaktifkan **Privasi Lanjutan**.

<Image align="center" alt="AAPcontrol.png" src="https://files.readme.io/ddc8140ada9278eab447ecdfa4d88c56e07a0ed54b10b71de1cc2352f9590d40-35847850639121.png" />

<div id="advanced-aggregated-privacy-implications-for-your-partners" />

<div id="aap-disabled" />

<div id="aap-enabled" />

#### **AAP diaktifkan**

* Atribusi gabungan tersedia. Ini mencakup, misalnya, dashboard Ikhtisar dan alat pelaporan seperti API Kelompok dan Master.
* [Sakelar mitra Privasi Lanjutan](/docs/apply-aggregated-advanced-privacy-framework#partner-advanced-privacy-switch) diaktifkan dan tidak dapat diubah. Catatan! Mereka terkunci dalam posisi.
* Ketersediaan data tingkat pengguna terhadap pemasang iklan dan mitra terbatas, seperti yang dijelaskan di [bagian sebelumnya](/docs/apply-aggregated-advanced-privacy-framework#prinsip-ketersediaan-data-dalam-privasi-lanjutan-gabungan).

**AAP dinonaktifkan**

* Atribusi gabungan tersedia. Ini mencakup, misalnya, dashboard Ikhtisar dan alat pelaporan seperti API Kelompok dan Master.
* Data atribusi tingkat pengguna tersedia untuk pemasang iklan.
* Pengaturan Privasi Tingkat Lanjut per mitra dapat diatur secara individual.

*Sebelum menonaktifkan AAP, pertimbangkan apakah dengan melakukan itu Anda akan membuat data atribusi tingkat pengguna tersedia untuk pihak ketiga dan bagaimana mereka akan menggunakan data tersebut. Anda harus bekerja sama dengan penasihat hukum Anda dan penasihat profesional lainnya sehubungan dengan cara Apple mendefinisikan pelacakan. Tidak ada yang dinyatakan di sini adalah nasihat hukum. Ini disediakan untuk informasi dan kenyamanan Anda.*

**Untuk menyetel setelan Privasi Lanjutan Gabungan**:

1. Di AppsFlyer, buka **Pengaturan** > **Pengaturan Aplikasi**.
2. Aktifkan atau nonaktifkan**Privasi Lanjutan Gabungan**  sesuai kebutuhan.
3. Klik **Simpan**.

</Accordion>

<div id="partner-advanced-privacy-switch" />

<Accordion title="Privasi Lanjutan—pengaktifan tingkat mitra">

Jika AAP dinonaktifkan, pemasang iklan dapat menyetel setelan Privasi Lanjutan untuk setiap jaringan iklan satu per satu.

<Image align="center" alt="APControl.png" src="https://files.readme.io/8e5a005cbadb5665cf255d39d6fa425298510f719b166c2013a2dfe57d4e982b-35847865312657.png" />

**Untuk menonaktifkan Privasi Lanjutan mitra:**

1. Verifikasi bahwa sakelar pusat untuk AAP tidak aktif, di halaman **Pengaturan Aplikasi** .
2. Buka **Konfigurasi** > **Integrasi Aktif**. Pilih jaringan iklan.
3. Di tab**Integrasi** , nonaktifkan **Privasi Tingkat Lanjut.**

**Mengubah pengaturan AAP dan dampaknya pada pengaturan Privasi Lanjutan mitra**

Seperti yang dinyatakan sebelumnya, pengaturan AAP menggantikan pengaturan Privasi Tingkat Lanjut (AP) di tingkat mitra. Namun, jika nanti Anda menonaktifkan AAP (sakelar pusat), setelan Privasi Lanjutan tingkat mitra individu akan kembali ke status sebelumnya. Artinya sebagai berikut:

* Sebelumnya, Anda menonaktifkan AAP dan beberapa setelan AP mitra.
* Kemudian Anda menyalakan AAP. Ingat, saat AAP aktif, setelan mitra akan diganti dan semua mitra dianggap aktif.
* Sekarang Anda mematikan AAP lagi. Artinya, setelan mitra individual berlaku. Jadi untuk beberapa mitra, pengaturannya sudah tidak aktif.

</Accordion>

## Implikasi AAP untuk mitra Anda

<div id="ad-networks" />

<Accordion title="Jaringan iklan">

<div id="postbacks-to-ad-network-partners" />

#### **Postback ke mitra jaringan iklan**

<Anchor target="_blank" href="/partners/id/docs/advanced-privacy-guide-postback-macros-for-ad-networks">AAP memengaruhi jaringan iklan</Anchor> sehubungan dengan data yang dibagikan kepada mereka dan selaras dengan prinsip AAP yang berlaku bagi pemasang iklan dalam konteks jaringan iklan. Data yang dibagikan dengan jaringan iklan dilakukan melalui postback yang berbeda antara jaringan iklan yang diatribusikan dan jaringan iklan yang tidak diatribusikan.

Aturan berbagi data yang dijelaskan berlaku untuk jaringan iklan tertentu jika salah satu sakelar berikut aktif:

* AAP: Sakelar tingkat aplikasi
* AP: Sakelar tingkat mitra

<div id="postbacks-for-attributed-ad-networks" />

#### **Postback untuk jaringan iklan yang dikaitkan**

Dalam kasus jaringan yang dikaitkan, jenis postback yang digunakan untuk berbagi data bergantung pada status persetujuan pengguna sebagai berikut:

* **Mengizinkan pengguna:** Postback reguler yang berisi data atribusi tingkat pengguna termasuk pengidentifikasi.
* **Pengguna yang tidak menyetujui:** Postback Privasi Tingkat Lanjut (AP) yang berisi data atribusi terbatas. Ini berisi detail kampanye dan tidak ada pengidentifikasi.
  * **Prasyarat:** Agar jaringan iklan mendapatkan postback AP, mereka harus memiliki integrasi AP dengan AppsFlyer. Tanpa integrasi, tidak ada postback yang dikirim untuk pengguna yang tidak memberikan persetujuan.
  * **Pengecualian:** Untuk penginstalan yang diatribusikan ke Apple Search Ads (ASA), saat jaringan iklan yang tidak mendukung Privasi Lanjutan menyetel postback penginstalan ke **Semua sumber media, termasuk organik**, Apple Search Ads (ASA) tetap mengirimkan postback penginstalan ke jaringan iklan terlepas dari status Privasi Lanjutan di pihak pemasang iklan.

Berbagai skenario izin pengguna dan jenis postback yang digunakan diilustrasikan dalam gambar berikut.

<Image align="center" alt="AAP - Attributed ad networks.png" src="https://files.readme.io/d776c77115beb4c6b6ada1850077f186aa2feb809a8b69af8cf0ec760cd02b39-35847865314961.png" />

Privasi Lanjutan berperilaku berbeda saat disajikan di web dan parameter af\_media\_type=web atau af\_media\_type=app harus digunakan. Lihat <Anchor target="_blank" href="/partners/id/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web-campaigns">di sini</Anchor> untuk informasi lebih lanjut.

<div id="postbacks-for-unattributed-partners" />

#### **Postback untuk mitra yang belum diatribusikan**

Postback tanpa atribusi dikirim ke jaringan saat opsi pengiriman di tab integrasi mitra terintegrasi diatur ke *semua sumber media, termasuk organik* dan mitra tersebut tidak diatribusikan ke acara seperti yang diilustrasikan dalam gambar berikut.

<Image align="center" alt="InAppEventAll.png" src="https://files.readme.io/e24037f75b2b82797031eb13d5e063b8c2006812491e69674ff066ac830919f7-35847850644881.png" />

Berbagai skenario izin pengguna dan jenis postback yang digunakan diilustrasikan dalam bagan alur berikut.

<Image align="center" alt="AAP - Unattributed ad networks.png" src="https://files.readme.io/bb8a5d192e2120f8df90b9be044c0b4abf48c2250f5128fbbce76c60c89718cc-35847850645649.png" />

Privasi Tingkat Lanjut berperilaku berbeda saat disajikan di web dan parameter af\_media\_type=web atau af\_media\_type=app harus digunakan. Lihat <Anchor target="_blank" href="/partners/id/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web-campaigns">di sini</Anchor> untuk informasi lebih lanjut.

</Accordion>

<div id="analytics-partners" />

<Accordion title="Mitra analitik">

AAP memengaruhi mitra analitik sehubungan dengan data yang dibagikan dengan mereka dan selaras dengan prinsip AAP yang berlaku untuk pemasang iklan dalam konteks mitra analitik.  Data yang dibagikan dengan mitra dilakukan melalui postback.

Aturan berbagi data yang dijelaskan berlaku untuk mitra tertentu jika salah satu sakelar berikut aktif:

* AAP: Sakelar tingkat aplikasi
* AP: Sakelar tingkat mitra

Postback yang berisi data atribusi tingkat pengguna termasuk ID pengguna dikirim untuk pengguna yang memberikan persetujuan. Tidak ada postback yang dikirim untuk pengguna yang tidak memberikan persetujuan.

Berbagai skenario izin pengguna dan jenis postback yang digunakan diilustrasikan dalam gambar berikut.

<Image align="center" alt="AAP - Analytics partner.png" src="https://files.readme.io/4bb77720f9e0be093e325f989987f5b5ba2dba5aa26e2f32df5f1bd5b99161eb-35847865320593.png" />

Privasi Tingkat Lanjut berperilaku berbeda saat disajikan di web dan parameter af\_media\_type=web atau af\_media\_type=app harus digunakan. Lihat <Anchor target="_blank" href="/partners/id/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web-campaigns">di sini</Anchor> untuk informasi lebih lanjut.

</Accordion>

<div id="agencies" />

<Accordion title="Agensi">

**Ketersediaan data**: Dampak AAP pada agensi mirip dengan pemasang iklan. Jika data lengkap tersedia untuk agensi untuk aplikasi tertentu dan AAP berlaku untuk data pengguna tertentu, data tersebut tersedia menurut aturan [data atribusi terbatas untuk pemasang iklan](/docs/apply-aggregated-advanced-privacy-framework#prinsip-ketersediaan-data-dalam-privasi-lanjutan-gabungan). 

**Agensi mengubah setelan Privasi Lanjutan jaringan iklan:**

* Jika AAP nonaktif, pengaturan Privasi Lanjutan dari setiap mitra terintegrasi dapat diatur.
* Secara default, hanya pemasang iklan yang dapat mengubah pengaturan Privasi Lanjutan; namun, pengiklan dapat secara eksplisit memberikan izin kepada agensi untuk menyetel setelan Privasi Lanjutan jaringan iklan yang diaktifkan oleh agensi.

**Berikan izin agensi untuk menyetel Privasi Lanjutan**

<Image align="center" alt="agency_advanced_privacy.png" src="https://files.readme.io/ac4a1aae41e9e39b9759006db84ea14df7495d0a14c02df7dbfb8dd93a2d2c23-35847865322129.png" />

**Untuk mengizinkan agensi menyetel Privasi Lanjutan**:

1. Buka **Konfigurasi** > **Integrasi Aktif**. Pilih agensi.
2. Di tab**Izin** , aktifkan **Ubah** **pengaturan Privasi Lanjutan.**
3. Klik ***Save***.

</Accordion>

<div id="see-also" />

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/partners/id/docs/advanced-privacy-guide-postback-macros-for-ad-networks">Panduan Privasi Tingkat Lanjut & makro postback untuk jaringan iklan</Anchor>

<div data-zendesk-anchors="aggregated-advanced-privacy-framework=kerangka-privasi-lanjutan-gabungan-aap h_01HDPDE0H3SYFWBHK59HBV2P6N=kerangka-privasi-lanjutan-gabungan-aap aapimpacted-features=fitur-yang-terpengaruh-aap h_01HDPDE0H339BPACN235V70MWW=fitur-yang-terpengaruh-aap data-availability-principles-in-aggregated-advanced-privacy=prinsip-ketersediaan-data-dalam-privasi-lanjutan-gabungan h_01HDPDE0H3QBE60DVBZ1MWNB9N=prinsip-ketersediaan-data-dalam-privasi-lanjutan-gabungan paid-and-owned-media-data-availability=ketersediaan-data-media-berbayar-dan-yang-dimiliki h_01HDPDE0H326EXNCQHPVJWXK3H=ketersediaan-data-media-berbayar-dan-yang-dimiliki h_01HDPDE0H3TBDSXCNW5Q3E1Q7P=paid-media paid-media-data-availability-by-att-status=ketersediaan-data-media-berbayar-berdasarkan-status-att h_01HDPDE0H3SACYAV19WQD9TCQ3=ketersediaan-data-media-berbayar-berdasarkan-status-att h_01HDPDE0H4M4XPE1C54K284BGW=owned-media controlling-aap=mengontrol-aap h_01HDPDE0H4VQC2DWAV68Q9VDVQ=mengontrol-aap h_01HDPDE0H4BHG114REGTWCDBP9=aap-central-switch aap-enabled=aap-diaktifkan h_01HDPDE0H4SC810EBK7ZGQ02K0=aap-diaktifkan h_01HDPDE0H4FRDXWRCYAWTPZZWE=partner-advanced-privacy-switch aap-implications-for-your-partners=implikasi-aap-untuk-mitra-anda h_01HDPDE0H4GJG05FEJP1YM06AP=implikasi-aap-untuk-mitra-anda h_01HDPDE0H4PDJ4TC02TED0DB8P=ad-networks postbacks-to-ad-network-partners=postback-ke-mitra-jaringan-iklan h_01HDPDE0H47ENYTWRVFPX0VTZC=postback-ke-mitra-jaringan-iklan postbacks-for-attributed-ad-networks=postback-untuk-jaringan-iklan-yang-dikaitkan h_01HDPDE0H4B01YG577QZCG7TA7=postback-untuk-jaringan-iklan-yang-dikaitkan postbacks-for-unattributed-partners=postback-untuk-mitra-yang-belum-diatribusikan h_01HDPDE0H63ZMV255SN7EKDRMV=postback-untuk-mitra-yang-belum-diatribusikan h_01HDPDE0H67T1XFTEB2N0NN6YN=analytics-partners h_01HDPDE0H6AM91W49W2G2Z94DM=agencies h_01HDPDMX05ZZCAMW4TTWF4M4YN=lihat-juga" />
