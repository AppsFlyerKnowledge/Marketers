---
title: Domain Bermerek
metadata:
  keywords:
    - Marketers
    - cname
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-08-26T09:00:09Z'
  edited_at: '2023-11-20T15:15:08Z'
  id: 360002329137
  locale: id
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/id/articles/360002329137
---
> **Sekilas:** Pengiklan yang menggunakan tautan OneLink dapat memberi merek dengan domain mereka sendiri. Ini meningkatkan kinerja kampanye dan meningkatkan eksposur merek.

![Branded_1__3_.jpg](https://files.readme.io/20d0a59aa3e896960c9a0faaacad51a58e314073368452e07a7507e0770ca817-30192959736465.png)

<div id="branded-domains" />

## Domain Bermerek

* Domain Bermerek digunakan untuk tautan atribusi merek dengan merek dan domain Anda. Misalnya, seperti yang diilustrasikan pada gambar sebelumnya:
  * OneLink: abcdef.onelink.me
  * Merek abcdef.com
  * Subdomain: Misalnya, aplikasi
  * Terapkan Domain Bermerek dan gunakan domain lengkap Anda, dengan tautan atribusi menjadi click.abcdef.com
* Domain Bermerek meningkatkan kinerja kampanye karena domain ini:
  * Mendorong kepercayaan: Manfaatkan pencitraan merek, memastikan identitas yang konsisten, menghilangkan hambatan dari perjalanan pengguna, dan meningkatkan CTR (Rasio Klik Tayang).
  * Izinkan deep linking menggunakan merek Anda.
  * Mudah diterapkan dan berperilaku sama seperti OneLinks.
  * Mempromosikan kesadaran merek: Merek Anda menandai kampanye Anda, bukan tautan umum.
  * Mengaktifkan email agar tidak ditandai sebagai spam karena tautan tidak cocok dengan email pengirim.

<div id="principles-of-implementation" />

### Prinsip implementasinya

Domain Bermerek diimplementasikan dengan mengaitkan domain lengkap yang ditentukan dalam Domain Name System (DNS) dengan subdomain OneLink (tujuan CNAME AppsFlyer). Ini dilakukan dengan menggunakan pengaturan standar di DNS Anda dan menyiapkan Domain Bermerek di AppsFlyer. Selain itu, Anda perlu membuat beberapa perubahan kecil pada aplikasi Anda untuk mendukung Domain Bermerek .

Anda akan memerlukan bantuan admin DNS, biasanya anggota tim IT atau penyedia hosting DNS dan pengembang aplikasi.

Beberapa domain lengkap dapat dikaitkan dengan satu subdomain OneLink. Ini berarti Anda dapat memiliki beberapa merek menggunakan subdomain OneLink yang sama.

<div id="setting-up-branded-domains" />

### Menyiapkan Domain Bermerek

Lengkapi daftar tindakan untuk menyiapkan Domain Bermerek.

|  | Tanggung jawab | Tindakan | Catatan |
| --- | --- | --- | --- |
| 1 | Pemasar dibantu oleh admin DNS | [Menyiapkan Tautan Bermerek di AppsFlyer](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer) | Admin DNS, biasanya anggota tim IT atau penyedia hosting DNS, harus menentukan domain lengkap (alias host) dan menetapkan catatan CNAME seperti yang dijelaskan dalam prosedur. |
| 2 | Pengembang | [Menyiapkan Domain Bermerek di aplikasi](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app) | Membuat perubahan kecil pada kode aplikasi. |
| 3 | Pemasar | [Menggunakan dan menguji Domain Bermerek](/docs/brand-onelink-with-your-domain#using-and-testing-branded-domains) |  |
| Sesuai kebutuhan | Pemasar | [Mengedit dan menghapus Domain Bermerek](/docs/brand-onelink-with-your-domain#editing-and-deleting-branded-domains) |  |

<div id="procedures" />

### Prosedur

<div id="set-up-a-branded-domain-in-appsflyer" />

<Accordion title="Menyiapkan Domain Bermerek di AppsFlyer">

Menyiapkan Domain Bermerek terdiri dari mengasosiasikan satu set domain lengkap di DNS Anda dengan subdomain OneLink di AppsFlyer seperti yang diilustrasikan pada gambar berikut.

**Domain Bermerek yang mengarah ke server AppsFlyer**

![Branded2__3_.jpg](https://files.readme.io/43bcdbe50ec58af434f404f0216f90ad345b7b1e034cb7d7c80e3c3c4307c1d2-30192946333713.png)

**Sebelum Anda mulai:**

* Pilih nama domain lengkap, misalnya app.abcdef.com yang mana abcdef.com adalah merek Anda.
  * Subdomain, misalnya, aplikasi, juga dapat disesuaikan.
* Meminta admin DNS membuat domain lengkap (alias host).
* Minta agar admin DNS mengatur catatan CNAME sedemikian rupa sehingga domain lengkap (Domain bermerek) mengarah ke URL yang ditentukan (alias host AppsFlyer). Ini diilustrasikan pada gambar Tautan Bermerek yang mengarah ke server AppsFlyer (di atas).

**Untuk memetakan domain lengkap Anda ke subdomain OneLink**:

1. Buka **Experiences & Deep Linking** > **Branded Domain**.
2. Klik **+ New Branded Domain**.
3. Di bidang **Domain Merek**, masukkan domain lengkap Anda seperti yang diatur dalam DNS Anda. Misalnya, **click.abcdef.com**  
   Jangan meletakkan tanda titik setelah domain.
4. Pilih subdomain OneLink dari daftar yang ditampilkan. Jika tidak ada daftar yang ditampilkan, Anda perlu membuat template OneLink, yang akan menyediakan subdomain default.
5. Klik **Next**.
6. Setel data CNAME:
   * Jika domain Anda diarahkan dengan benar ke tujuan AppsFlyer CNAME, "AppsFlyer CNAME ditemukan" akan ditampilkan.
   * Jika CNAME tidak ditemukan, salin tujuan CNAME AppsFlyer, kirimkan ke admin DNS Anda, dan minta mereka untuk memastikan domain lengkap Anda mengarah ke tujuan CNAME. Anda harus mengarahkan domain lengkap Anda ke tujuan AppsFlyer CNAME. Jika tidak, domain bermerek dibuat tetapi tidak berfungsi.  Jika Anda menggunakan domain bermerek untuk ESP, sebelum menyalin tujuan CNAME, pilih **Gunakan domain bermerek untuk konfigurasi ESP**.
7. Klik **Finish**.  
   Anda sekarang dapat membuat tautan baru berdasarkan templat OneLink dengan domain bermerek Anda.

**Catatan**:

* Jika Anda sudah membuat tautan berdasarkan templat OneLink tanpa domain bermerek, tautan tersebut tetap berfungsi.
* Diperlukan waktu hingga 24 jam agar domain bermerek baru mulai berfungsi.
* Jika Anda tidak menyetel data CNAME dalam 7 hari, domain bermerek Anda akan kedaluwarsa. Kemudian Anda perlu menyegarkan domain bermerek Anda sebelum dapat digunakan. Untuk menyegarkan: 
  1. Buka **Experiences & Deep Linking** > **Branded Domain.**
  2. Buka domain bermerek yang ingin Anda segarkan.
  3. Klik **Refresh.**
  4. Setel data CNAME.

</Accordion>

<div id="set-up-branded-domains-in-the-app" />

<Accordion title="Menyiapkan Domain Bermerek di aplikasi">

* Gunakan versi SDK berikut:  
  * Android V4.10.1 dan yang lebih baru
  * iOS V4.10.1 dan yang lebih baru
  * Referensi undangan pengguna (undang teman) memerlukan SDK versi V5.2.0 dan yang lebih baru untuk iOS dan Android

**Pertimbangan penerapan Domain Bermerek SDK**

* Saat deep linking dilakukan menggunakan Domain Bermerek, SDK AppsFlyer tidak bisa mendapatkan data konversi untuk penginstalan dan deep linking.
* Untuk mengatasi hal ini, pengembang menggunakan  `setOneLinkCustomDomain` dan SDK API `oneLinkCustomDomains` untuk Android dan iOS.
* API ini meminta domain bermerek, mendapatkan domain OneLink yang dipetakan, dan menyelesaikan OneLink.

<Tabs>
<Tab title="Android">

Pastikan Anda memperbarui <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">filter-intent</Anchor> dari manifes untuk menyertakan domain merek Anda dengan mengatur android:host.

Gunakan API ini sebelum menginisialisasi SDK <Anchor target="_blank" href="https://developer.android.com/reference/android/app/Application">kelas aplikasi global Android.</Anchor>

**Contoh**

```java
AFApplication kelas publik memperluas Aplikasi {

   @Override
   public void onCreate() {
    super.onCreate();

      // Set branded link domain. Don't include https:// as part of the domain. 
      AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com");
      AppsFlyerLib.getInstance().init(AF_DEV_KEY, conversionListener, this);
      AppsFlyerLib.getInstance().start(this, AF_DEV_KEY);

    }
}
```

Jika Anda memiliki beberapa domain bermerek, berikan semuanya ke API untuk memastikan bahwa Anda selalu mendapatkan data konversi dan dapat melakukan deep link ke aplikasi.

**Contoh**

```java
AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com", 
                                                        "click.greatapp.com", 
                                                        "deals.greatapp.com");
```

</Tab>

<Tab title="iOS">

<Tabs>
<Tab title="Tujuan C">

Gunakan API di AppDelegate.m, dalam metode didFinishLaunchingWithOptions:

```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    /** APPSFLYER INIT **/
    [AppsFlyerLib shared].appsFlyerDevKey = @"SED_DEV_KEY";
    [AppsFlyerLib shared].appleAppID = @"123456789";
    [AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com"];
    //...
    //...
  }
```

Jika Anda memiliki beberapa domain bermerek, berikan semuanya ke API untuk memastikan bahwa Anda selalu mendapatkan data konversi dan dapat melakukan deep link ke aplikasi.

**Contoh**

```objectivec
[AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com", @"click.greatapp.com"];
```

</Tab>

<Tab title="Swift">

API harus digunakan di AppDelegate.swift, dalam metode didFinishLaunchingWithOptions:

```swift
   func application(_ application: UIApplication, didFinishLaunchingWithOptions 
        launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {
          AppsFlyerLib.shared().appsFlyerDevKey = "6CQi4Be6Zs9oNLsCusPbUL"
          AppsFlyerLib.shared().appleAppID = "340954504"
          AppsFlyerLib.shared().oneLinkCustomDomains = ["example.com"]
          //...
          //...
   }
```

Jika Anda memiliki beberapa domain bermerek, Anda dapat memberikannya ke API sebagai larik string. Ini memastikan bahwa apa pun tautan bermerek yang digunakan, Anda selalu mendapatkan data konversi dan dapat melakukan deep link ke aplikasi.

**Contoh**

```objectivec
AppsFlyerLib.shared().oneLinkCustomDomains = ["promotion.greatapp.com", "click.greatapp.com"]
```

</Tab>
</Tabs>

</Tab>
</Tabs>

</Accordion>

<div id="using-and-testing-branded-domains" />

<Accordion title="Menggunakan dan menguji Domain Bermerek">

**Prasyarat**:

Sebelum menggunakan dan melakukan pengujian, Domain Bermerek menyelesaikan langkah-langkah di [alur kerja Domain Bermerek](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app).

**Untuk membuat dan menguji domain bermerek:**

1. <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#buat-tautan-onelink">Buat tautan OneLink</Anchor> menggunakan templat OneLink yang dipetakan ke domain bermerek.
2. Salin tautan atribusi kustom ke editor teks.
3. Tautan atribusi kustom terdiri dari subdomain OneLink, ID OneLink, dan ID Tautan kustom. Ganti subdomain OneLink dengan domain lengkap Domain Bermerek. Contoh:  

| Tautan atribusi kustom | Domain Bermerek |
| --- | --- |
| **abcdef.onelink.me**/A1bc/dc1234ef | **click.abcdef.com**/A1bc/dc1234ef |

4. Gunakan tautan bermerek untuk <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">menguji penginstalan dan deep linking</Anchor>.
5. Jika Anda menggunakan laporan data lengkap sebagai bagian dari pengujian, bidang URL Aslinya diisi oleh tautan bermerek.

</Accordion>

<div id="editing-and-deleting-branded-domains" />

<Accordion title="Mengedit dan menghapus Domain Bermerek">

Pengeditan memungkinkan Anda mengubah pemetaan domain lengkap yang ada ke subdomain OneLink lainnya. Tidak perlu mengatur CNAME.

> ❗️ **Perhatian**
>
> Mengubah Domain Bermerek kampanye aktif dapat mengubah atau menonaktifkan fungsi tautan.

**Untuk mengedit pemetaan domain bermerek:**

1. Buka **Experiences & Deep Linking** > **Branded Domain.**
2. Buka domain bermerek yang ingin Anda edit.
3. Klik **Edit**.

**Untuk menghapus pemetaan domain bermerek:**

* Hubungi CSM AppsFlyer Anda atau <Anchor target="_blank" href="hello@appsflyer.com">hello@appsflyer.com</Anchor>.

</Accordion>

<div id="troubleshooting-traits-and-limitations" />

## Penyelesaian masalah, karakteristik, dan batasan

<div id="troubleshooting" />

<Accordion title="Pemecahan Masalah">

| Tanda peringatan | Penyebab/solusi |
| --- | --- |
| Domain Bermerek tidak dapat dipetakan ke template OneLink | <ul><li>**Nama domain tidak valid:** Saat memetakan Domain Bermerek ke template OneLink, AppsFlyer mencoba memverifikasi bahwa tautan bermerek memiliki nama domain yang valid. Nama domain yang valid memiliki format click.abdef.com</li><li>**Domain Bermerek telah dipetakan**: Domain lengkap hanya dapat dipetakan satu kali.</li></ul> |
| Domain Bermerek tidak melakukan deep linking ke aplikasi | <ul><li>[Verifikasi bahwa Domain Bermerek berfungsi](/docs/brand-onelink-with-your-domain#troubleshooting)</li><li>**Verifikasi CNAME**: Pastikan bahwa catatan CNAME mengarah dari Domain Bermerek Anda ke AppsFlyer.</li><li>**Verifikasi pengaturan deep linking untuk templat**: Mungkin ada masalah dengan pengaturan deep linking OneLink. Pastikan untuk menyiapkan deep linking dengan OneLink.</li><li>**Pemetaan OneLink berubah**: Anda dapat mengedit Domain Bermerek dan memetakannya ke OneLink lainnya. Jika OneLink yang baru dipetakan memiliki pengaturan deep linking yang berbeda atau tidak ada pengaturan deep linking, deep linking mungkin tidak berfungsi.</li></ul> |
| Tidak ada penginstalan yang diukur dari Domain Bermerek | <ul><li>**Periksa pengaturan templat OneLink**: Pastikan subdomain OneLink yang digunakan untuk memetakan ke domain bermerek dikaitkan dengan aplikasi yang benar.</li><li>**Subdomain OneLink berubah:** Jika Anda memetakan domain bermerek ke templat OneLink dan subdomain OneLink berubah, hal itu dapat memengaruhi atribusi.</li><li>**Memastikan penerapan API:** Of setOneLinkCustomDomain di aplikasi.</li></ul> |
| Tidak ada interaksi ulang ulang yang direkam dari domain bermerek | Pastikan yang berikut ini aktif dan dikonfigurasi:<ul><li>Konfigurasikan deep linking menggunakan OneLink.</li><li>Aplikasi ini menggunakan [setOneLinkCustomDomain SDK API khusus](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer) .</li><li><Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide#retargeting-settings">Penargetan ulang diaktifkan di pengaturan aplikasi</Anchor>.</li></ul> |
| Selama penyiapan Domain Bermerek, muncul pesan **Domain tidak ada** | <ol><li>Hubungi admin DNS Anda dan minta mereka untuk menyelidiki.</li><li>Tunggu admin DNS untuk mengonfirmasi bahwa domain telah terdaftar.</li><li>Klik **Reverify** (Verifikasi Ulang).</li></ol> |
| Selama penyiapan Domain Bermerek, muncul pesan **AppsFlyer CNAME tidak ditemukan** | <ol><li>Minta agar admin DNS mengatur catatan CNAME sedemikian rupa sehingga domain lengkap (Domain bermerek) mengarah ke URL yang ditentukan (alias host AppsFlyer). Ini diilustrasikan pada gambar Tautan Bermerek yang mengarah ke server AppsFlyer di bagian ini.</li><li>Tunggu hingga admin DNS mengonfirmasi bahwa CNAME aktif.</li></ol> |
| kesalahan **route\_not\_found** saat memuat halaman domain bermerek | Domain bermerek tidak menyertakan tempat atau parameter apa pun. Ketika menggunakan domain bermerek, Anda harus menambahkan tempat atau parameter di akhir URL domain bermerek.<br /><br />Misalnya, jika 'click.abcdef.com' adalah domain bermerek Anda, menggunakan hanya '**click.abcdef.com'**, akan mengarah ke **route\_not\_found\_error**.<br /><br />Anda harus menambahkan parameter atau templat di akhir. Contohnya, click.abcdef.com **/A1bc/dc1234ef** |
| kesalahan **err\_cert\_authority\_invalid** saat memuat halaman domain bermerek | Kesalahan ini menunjukkan bahwa domain bermerek Anda tidak memiliki sertifikat HTTPS yang valid karena Otoritas Sertifikat tidak dikenali. Karena AppsFlyer mensertifikasi domain Bermerek Anda dengan Let's Encrypt, kesalahan tersebut kemungkinan disebabkan oleh Let's Encrypt yang tidak diakui sebagai Otoritas Sertifikat (CA) yang valid menurut catatan DNS CAA (Certification Authority Authorization) domain Anda.<br /><br />**Solusi** Silakan lakukan hal berikut:<ol><li>Tentukan apakah domain Anda mengenali Let's Encrypt sebagai CA menggunakan layanan seperti <Anchor target="_blank" href="https://www.entrust.com/resources/certificate-solutions/tools/caa-lookup">ini</Anchor>.</li><li>Minta administrator sistem Anda untuk memperbarui catatan CAA domain Anda untuk menyertakan Let's Encrypt sebagai CA resmi.</li></ol> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Sifat | Ya ✓ / Tidak **x** | Catatan |
| --- | --- | --- |
| Akses jaringan iklan | **x** |  |
| Akses agensi | **x** | Agensi tidak dapat mengakses bagian Domain Bermerek untuk membuat Domain Bermerek. Namun, agensi dapat membuat tautan personalisasi OneLinks menggunakan subdomain Branded Links (Tautan Bermerek). |
| Transparansi agensi | **x** |  |
| Zona waktu khusus aplikasi | N/A |  |
| Mata uang khusus aplikasi | N/A |  |
| Batasan karakter | N/A | Saat memasukkan domain bermerek Anda, karakter terakhir tidak boleh berupa tanda titik ("."). |
| Keterbatasan ukuran | N/A |  |
| Batasan tingkat | ✓ | Sertifikat SSL/HTTP Domain Bermerek diatur oleh AppsFlyer menggunakan <Anchor target="_blank" href="https://letsencrypt.org/">Let's Encrypt</Anchor>, dengan batas permintaan 50 sertifikat baru per minggu, per domain. |
| Data organik | ✓ |  |
| Data non-organik | ✓ |  |
| Kesegaran data | N/A |  |
| Data historis | ✓ |  |
| Akses pengguna akun | ✓ |  |
| HTTP | **x** | Protokol HTTP tidak didukung oleh tautan bermerek. HTTPS harus digunakan. |

</Accordion>

<div data-zendesk-anchors="branded-domains=domain-bermerek h_01HFM51V4PE53FQAED68V8Q834=domain-bermerek principles-of-implementation=prinsip-implementasinya h_01HFM51V4PPJXMCSV5ZVDPT49M=prinsip-implementasinya setting-up-branded-domains=menyiapkan-domain-bermerek h_01HFM51V4PH58ZA4ZXHP5J6K2W=menyiapkan-domain-bermerek procedures=prosedur h_01HFM51V4PWWX7TBCHFMPR3QVB=prosedur h_01HFM51V4PA23K6HR2Y1D6D31Q=set-up-a-branded-domain-in-appsflyer h_01HFM51V4PP0NQHVHTKB86250R=set-up-branded-domains-in-the-app h_01HFM51V4PN0FPEDNAF0Q1QS8P=using-and-testing-branded-domains h_01HFM51V4PFFXZ8RFBZNMZGXXK=editing-and-deleting-branded-domains h_01HFM51V4PVZE7FAFN2EYS7P6E=perhatian troubleshooting-traits-and-limitations=penyelesaian-masalah-karakteristik-dan-batasan h_01HFM51V4PH4YM13DVXENRWF2E=penyelesaian-masalah-karakteristik-dan-batasan h_01HFM51V4PJNHZTD97X75WPN98=troubleshooting h_01HFM51V4QQ2TZQMJ2ATNDG91F=traits-and-limitations" />
