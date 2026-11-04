---
title: 'Mendaftarkan perangkat uji '
metadata:
  keywords:
    - whitelisting
    - Testing
    - device
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2015-03-10T08:19:35Z'
  edited_at: '2023-11-28T04:51:47Z'
  id: 207031996
  locale: id
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/id/articles/207031996
---
> **Sekilas:** Saat melakukan pengujian atribusi, daftarkan perangkat pengujian Anda untuk memastikan setiap penginstalan dicatat sebagai penginstalan baru. Perangkat uji yang terdaftar mencegah penginstalan agar tidak dicatat sebagai penginstalan ulang.

<div id="why-register-a-test-device" />

## Mengapa mendaftarkan perangkat uji

Saat melakukan uji atribusi, jendela atribusi ulang membatasi penginstalan atribusi menjadi satu atribusi per jendela 90 hari. Oleh karena itu, jika Anda berulang kali menggunakan perangkat yang sama untuk menguji atribusi penginstalan, tidak ada yang dicatat. Mendaftarkan perangkat sebagai perangkat uji mencegah penginstalan berulang pada perangkat terdaftar agar tidak direkam sebagai penginstalan ulang.

<div id="methods-for-registering-a-test-device" />

## Metode untuk mendaftarkan perangkat uji

Mendaftarkan perangkat uji termasuk memilih sistem operasi perangkat (Android, iOS, atau Windows), dan menambahkan pengenal perangkat.

Anda dapat menggunakan salah satu metode berikut untuk mendaftar:

* [Unduh dan instal aplikasi My Device ID by AppsFlyer:](#register-a-device-using-the-appsflyer-device-id-app-admin-only) Setelah Anda menginstal aplikasi pada perangkat uji, Anda dapat mendaftarkan perangkat secara otomatis dan membagikan detail ID perangkat ke akun AppsFlyer Anda. Perangkat akan terdaftar secara otomatis di halaman **Perangkat uji** .

  <div id="note" />

  > 📘 **Catatan**
  >
  > Di perangkat uji iOS 14+, Anda dapat menggunakan metode pendaftaran ini hanya jika AppTransparency Tracking (ATT) diterapkan di aplikasi Anda dan Anda ingin menjalankan pengujian sebagai pengguna yang menyetujui. Jika tidak demikian, gunakan metode manual.

* [Tambahkan perangkat uji secara manual:](#register-a-device-manually) Setiap pengguna akun dapat langsung mendaftarkan perangkat uji dengan menambahkan pengidentifikasi perangkat ke halaman **Perangkat uji** .

Ingatlah hal berikut:

* Perangkat uji terdaftar tersedia untuk semua aplikasi yang dimiliki akun tersebut.
* Jaringan iklan harus meminta pengiklan untuk menambah perangkat; agensi dapat menambahkan perangkat mereka sendiri.

<div id="supported-device-identifiers" />

<Accordion title="Pengenal perangkat yang didukung">

Pengenal perangkat termasuk hal-hal berikut:

* **Android:** BANTUAN (GAID atau OAID), IMEI, ID Android

  <div id="note-1" />

  > 📘 **Catatan**
  >
  > Saat mendaftarkan perangkat uji, Anda hanya boleh menambahkan pengenal perangkat IMEI atau ID Android jika aplikasi Anda mengumpulkan dan menggunakan pengenal ini.

* **iOS:** IDFA, IDFV
* **Windows Phone:** ID iklan Windows

</Accordion>

<div id="android::7db075c7" />

<div id="ios::41efa11e" />

<div id="windows::6c6af14b" />

<div id="ios::80f176b3" />

<div id="android::db8cc168" />

<div id="windows" />

<div id="ios" />

<div id="android" />

<div id="managing-test-device-registration" />

## Mengelola pendaftaran perangkat uji

<div id="register-a-device-using-the-appsflyer-device-id-app-admin-only" />

<Accordion title="Daftarkan perangkat menggunakan aplikasi ID perangkat AppsFlyer">

**Untuk mengunduh aplikasi ID perangkat AppsFyer:**

1. Unduh dan instal aplikasi menggunakan kode QR (Google Play store) atau salah satu tautan yang disediakan.

   <Tabs>
   <Tab title="Android">

   [<Image alt="" src="https://support.appsflyer.com/hc/article_attachments/360005641117" width="233px" />](https://support.appsflyer.com/hc/article_attachments/360005641117)

   **Tautan:** [Google Play](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid&hl=en) dan [Toko di luar pasar](https://apkpure.com/my-device-id-by-appsflyer/com.appsflyer.android.deviceid)

   </Tab>

   <Tab title="iOS">

   [<Image alt="" src="https://support.appsflyer.com/hc/article_attachments/360001988157" width="233px" />](https://support.appsflyer.com/hc/article_attachments/360001988157)

   </Tab>

   <Tab title="Windows">

   [<Image alt="" src="https://files.readme.io/6e60bf0e69c0055c5946d111a0a5a2a04dddb268ba777b52097ab0650327d280-31773660950673.png" width="233px" />](https://files.readme.io/6e60bf0e69c0055c5946d111a0a5a2a04dddb268ba777b52097ab0650327d280-31773660950673.png)

   </Tab>
   </Tabs>

2. Di perangkat iOS 14.5+, jika Anda ingin mengizinkan pengumpulan IDFA, ketuk **Izinkan** saat perintah ATT ditampilkan.

   [![](https://files.readme.io/3be1b8f24bf558d022c45913b393cf8c8011639354d8b11d9c591e58024f1c8d-31773660957329.png)](https://files.readme.io/3be1b8f24bf558d022c45913b393cf8c8011639354d8b11d9c591e58024f1c8d-31773660957329.png)
3. Pada layar Android/iOS/Windows, ketuk **Daftar** untuk mendaftarkan perangkat.

   <Tabs>
   <Tab title="Android">

   [![](https://files.readme.io/b6deed582cc87925576b893fb8f021e4aa254c15a99ec532fd456e146769a125-31773630607889.png)](https://files.readme.io/b6deed582cc87925576b893fb8f021e4aa254c15a99ec532fd456e146769a125-31773630607889.png)

   </Tab>

   <Tab title="iOS">

   [![](https://files.readme.io/f06f609433b8ce483e5281cc2a0d062ab71a150318d7892879f3defb706f5429-31773660968081.png)](https://files.readme.io/f06f609433b8ce483e5281cc2a0d062ab71a150318d7892879f3defb706f5429-31773660968081.png)

   </Tab>

   <Tab title="Windows">

   [![](https://files.readme.io/6bbfb8680a3f6ea507a7d011d3140fbcc11173f4ef091f7c5f7c3cc863598ab8-31773660972817.jpg)](https://files.readme.io/6bbfb8680a3f6ea507a7d011d3140fbcc11173f4ef091f7c5f7c3cc863598ab8-31773660972817.jpg)

   </Tab>
   </Tabs>

4. Masukkan kredensial masuk AppsFlyer Anda. Perangkat sekarang terdaftar.
5. Ketuk **Bagikan** detail untuk membagikan informasi ID Perangkat.

</Accordion>

<div id="register-a-device-manually" />

<Accordion title="Daftarkan perangkat secara manual">

Pengguna akun dapat mendaftarkan perangkat secara manual:

1. Di AppsFlyer, di klik kanan atas alamat email Anda.
2. Pilih **Perangkat** **uji**.
3. Klik **+ Tambahkan perangkat**.

   [![](https://files.readme.io/e28ef06002e423d4cf7863d4c7fd2b269a0ede5c4b996a50cee25ffbedfcd9d1-31773630618769.png)](https://files.readme.io/e28ef06002e423d4cf7863d4c7fd2b269a0ede5c4b996a50cee25ffbedfcd9d1-31773630618769.png)
4. Lakukan hal berikut:
   * **Nama (hanya menggunakan huruf bahasa Inggris):** Masukkan nama identifikasi unik untuk perangkat.
   * **OS:** Pilih sistem operasi.
   * **Jenis ID perangkat:** Pilih pengidentifikasi perangkat.
   * **ID Perangkat:** Berikan ID perangkat sesuai dengan sistem operasi:

     <Tabs>
     <Tab title="iOS">

     Cara mendapatkan pengidentifikasi IDFA atau IDFV:

     * **IDFA:** Untuk mendapatkan IDFA, instal aplikasi ID perangkat AppsFlyer di perangkat uji Anda. Untuk mempelajari caranya, lihat: [Tambahkan perangkat](#register-a-device-manually) menggunakan aplikasi ID perangkat AppsFlyer (khusus admin) di atas.
     * **IDFV:** Untuk mendapatkan IDFV, minta pengembang Anda untuk menginstal aplikasi alat uji IDFV di perangkat uji Anda. Setelah diinstal dan diluncurkan, aplikasi alat akan menampilkan IDFV. **Catatan:** Alat uji hanya dapat diinstal setelah pengembang melakukan langkah awal di X-Code.

     Untuk mengetahui kapan menggunakan IDFA atau IDFV, lihat [Mendaftarkan perangkat uji iOS](#mendaftarkan-perangkat-uji-ios).

     </Tab>

     <Tab title="Android">

     Dapatkan pengidentifikasi dengan menggunakan aplikasi ID Perangkat AppsFlyer atau dengan menekan kode ke perangkat:

     | Pengenal | Metode pengambilan | Google play | Lainnya |
     | --- | --- | --- | --- |
     | AID (GAID atau OAID) | Gunakan [Aplikasi ID Perangkat AppsFlyer](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid) | Wajib | Dapat digunakan untuk mendaftarkan perangkat |
     | imei | *#06#* | Tak dapat diterapkan | Dapat digunakan untuk mendaftarkan perangkat |
     | ID Android | *#*#8255#*#* (mungkin tidak berfungsi pada perangkat yang lebih baru) | Tak dapat diterapkan | Dapat digunakan untuk mendaftarkan perangkat |

     </Tab>

     <Tab title="Windows">

     **ID Iklan Windows** [Dapatkan ID iklan Windows](https://www.microsoft.com/en-us/p/my-ad-device-id/9nn69nbsj9xw?activetab=pivot:overviewtab)

     </Tab>
     </Tabs>

5. Klik **Simpan**. Perangkat ditampilkan dalam daftar perangkat terdaftar. **Catatan**: Meskipun perangkat segera ditampilkan dalam daftar perangkat yang terdaftar, mungkin perlu waktu beberapa menit untuk mendaftar di sistem dan berfungsi sebagaimana mestinya.

<div id="note-2" />

> 📘 **Catatan**
>
> **Menambahkan lebih dari satu pengidentifikasi**
>
> Mungkin ada kasus di mana Anda ingin menambahkan lebih dari satu pengidentifikasi ke perangkat uji, misalnya, Anda ingin IDFA dan IDFV di perangkat yang sama.
>
> **Untuk menambahkan pengenal tambahan:**
>
> 1. Klik **Tambahkan perangkat**.
> 2. Gunakan nama yang sama untuk perangkat uji, dan tambahkan pengenal ke-2.
> 3. Klik **Simpan**.

</Accordion>

<div id="unregister-a-device" />

<Accordion title="Batalkan pendaftaran perangkat">

Maksimal 200 perangkat dapat didaftarkan per akun. Hanya pengguna admin yang dapat menghapus perangkat uji.

**Untuk menghapus perangkat dari daftar:**

1. Di AppsFlyer, di klik kanan atas alamat email Anda.
2. Pilih **Perangkat** **uji**.
3. Klik ikon hapus untuk menghapus perangkat.

</Accordion>

<div id="registering-an-ios-test-device" />

## Mendaftarkan perangkat uji iOS

Bagan alur di bawah ini menggambarkan kemungkinan tindakan saat mendaftarkan perangkat uji iOS Anda.

[![](https://files.readme.io/214818cd73ebc8cd5d3479d27e3074fec55ec7f9e3d4702b17f3c8811270f54e-31773630621585.png)](https://files.readme.io/214818cd73ebc8cd5d3479d27e3074fec55ec7f9e3d4702b17f3c8811270f54e-31773630621585.png)

Pilih di antara opsi berikut saat mendaftarkan perangkat uji iOS Anda:

<div id="register-your-testing-device-with-idfa" />

<Accordion title="Daftarkan perangkat uji Anda dengan IDFA">

<div id="when-to-use-idfa-for-test-device-registration" />

#### **Kapan menggunakan IDFA untuk pendaftaran perangkat uji?**

Anda dapat mendaftar dengan IDFA jika Pelacakan Transparansi Aplikasi (ATT) diterapkan di aplikasi Anda dan Anda ingin menjalankan pengujian sebagai pengguna yang menyetujui. Saat meluncurkan aplikasi yang diuji untuk pertama kali, pastikan untuk mengeklik **Izinkan** di perintah ATT.

<div id="how-to-register-your-test-device-with-an-idfa" />

#### **Bagaimana cara mendaftarkan perangkat uji Anda dengan IDFA?**

Untuk mendaftar dengan IDFA, daftarkan perangkat menggunakan aplikasi ID perangkat AppsFlyer.

</Accordion>

<div id="register-your-testing-device-with-idfv" />

<Accordion title="Daftarkan perangkat uji Anda dengan IDFV">

<div id="when-to-use-idfv-for-test-device-registration" />

#### **Kapan menggunakan IDFV untuk pendaftaran perangkat uji?**

Saat IDFA tidak dapat diakses, IDFV adalah satu-satunya pilihan Anda. Dalam skenario berikut, Anda **harus menggunakan IDFV**:

* **ATT diterapkan** tetapi Anda ingin menjalankan pengujian sebagai pengguna yang tidak menyetujui. Saat meluncurkan aplikasi untuk pertama kali, pastikan untuk mengeklik **Jangan Izinkan** di perintah ATT.
* **ATT tidak diterapkan** sama sekali.

<div id="how-to-register-your-device-with-idfv" />

#### **Cara mendaftarkan perangkat Anda dengan IDFV**

1. Sebelum Anda dapat mendaftarkan perangkat pengujian dengan IDFV, pengembang Anda harus menginstal aplikasi alat uji IDFV di perangkat uji Anda. Untuk instruksi pengembang, Anda dapat merujuk pengembang Anda ke <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-the-idfv-test-tool-app">artikel ini</Anchor>.
2. Setelah pengembang Anda menginstal aplikasi alat uji IDFV, luncurkan dan salin IDFV yang ditampilkan.
3. [Daftarkan perangkat uji secara manual](#register-a-device-manually) menggunakan IDFV.

<div id="note-3" />

> 📘 **Catatan**
>
> **Apa alasan untuk menginstal aplikasi alat uji IDFV?**
>
> * Alat uji IDFV digunakan untuk mengekstrak IDFV yang Anda perlukan untuk mendaftarkan perangkat uji.
> * Bila Anda tidak memiliki aplikasi lain yang dimiliki oleh akun pengembang Anda terinstal di perangkat uji Anda. Dalam hal ini iOS memberikan ID vendor baru setiap kali Anda menginstal ulang aplikasi. Karena pengujian dalam banyak kasus melibatkan penginstalan ulang aplikasi, setiap penginstalan ulang memicu iOS untuk mengatur ulang IDFV. **Aplikasi utilitas dengan berpura-pura menjadi milik vendor, mencegah iOS membuat IDFV baru setiap kali aplikasi diinstal ulang di perangkat uji.**

</Accordion>

<div id="dont-register-a-testing-device" />

<Accordion title="Jangan mendaftarkan perangkat uji">

Gunakan opsi ini hanya jika Anda tidak dapat mendaftarkan perangkat uji dengan IDFA atau IDFV. Dalam hal ini, pemodelan probabilistik digunakan untuk atribusi. Setiap penginstalan dicatat sebagai penginstalan baru di perangkat uji. Metode ini dapat membantu mendaftarkan penginstalan pengujian berulang untuk perangkat yang sama jika setidaknya salah satu dari hal berikut terjadi:

* SDK iOS AppsFlyer adalah v6.8.0 atau lebih rendah.
* Deteksi penginstalan ulang dinonaktifkan untuk aplikasi (tidak disarankan untuk aplikasi aktif).
* Tautan atribusi pengujian berisi "is\_retargeting=true". Dalam hal ini, penginstalan dicatat sebagai atribusi ulang dan tersedia di dasbor penargetan ulang dan penargetan ulang laporan data lengkap.

</Accordion>

<div data-zendesk-anchors="why-register-a-testing-device=mengapa-mendaftarkan-perangkat-uji 01H7W9EA7RQDB69QS339XFHAFZ=mengapa-mendaftarkan-perangkat-uji methods-for-registering-a-testing-device=metode-untuk-mendaftarkan-perangkat-uji 01H7W9EA7RRRJBFSXW3KY53R9K=metode-untuk-mendaftarkan-perangkat-uji 01H7W9EA7RTTQ1FHZZ6GBGV0WP=catatan 01H7W9EA7RWWNACKSEETMCP90W=supported-device-identifiers 01H7W9EA7R9A8KCNRD0BTPPQTH=catatan-1 managing-testingdevice-registration=mengelola-pendaftaran-perangkat-uji 01H7W9EA7R7SJVVQCST3WA6YBM=mengelola-pendaftaran-perangkat-uji h_01H6V7FQFF10E4C82ZQ97PEEZA=register-a-device-using-the-appsflyer-device-id-app-admin-only h_01H6V7GM8KKXF8VS5ZRA4NV592=register-a-device-manually 01H7W9EA7R190M9DH7GPY1VJ77=catatan-2 01H7W9EA7R0KGH3YXZ9SMAFESZ=unregister-a-device registering-an-ios-testing-device=mendaftarkan-perangkat-uji-ios h_01H6S2AKDH181MBDFGPBP1BQPV=mendaftarkan-perangkat-uji-ios 01H7W9EA7SPA47GR1X0S9WZKDH=register-your-testing-device-with-idfa when-to-use-idfa-for-testing-device-registration=kapan-menggunakan-idfa-untuk-pendaftaran-perangkat-uji 01H7W9EA7SRD5V5134H2BRZ2AF=kapan-menggunakan-idfa-untuk-pendaftaran-perangkat-uji how-to-register-your-testing-device-with-an-idfa=bagaimana-cara-mendaftarkan-perangkat-uji-anda-dengan-idfa 01H7W9EA7SBBCAP3Y24FFCCGJW=bagaimana-cara-mendaftarkan-perangkat-uji-anda-dengan-idfa 01H7W9EA7SNZ3ER02MBV8VJGH3=register-your-testing-device-with-idfv when-to-use-idfv-for-testing-device-registration=kapan-menggunakan-idfv-untuk-pendaftaran-perangkat-uji 01H7W9EA7S3103TSHSH4XHTP1R=kapan-menggunakan-idfv-untuk-pendaftaran-perangkat-uji how-to-register-your-device-with-idfv=cara-mendaftarkan-perangkat-anda-dengan-idfv 01H7W9EA7SGTDQCRVJKKRH0EVT=cara-mendaftarkan-perangkat-anda-dengan-idfv 01H7W9EA7SHVSDPJN8P2WBSFN1=catatan-3 01H7W9EA7S3KJ89AN9ZBMHFGRR=dont-register-a-testing-device" />
