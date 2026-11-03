---
title: Integrasi Amplitude dengan AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Amplitude
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2016-08-02T05:18:03Z'
  edited_at: '2023-10-08T11:40:09Z'
  id: 211200306
  locale: id
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/id/articles/211200306
---
> **Sekilas:** Amplitude, mitra terintegrasi AppsFlyer, menyediakan analitik produk untuk membantu perusahaan seluler dan web memahami perilaku pengguna. Tim produk, pemasaran, dan pertumbuhan menggunakan Amplitude untuk menemukan dan berbagi wawasan tentang keterlibatan pengguna, retensi, dan pendapatan.

> 🚧 **Penting!**
>
> <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions#pembatasan-sumber-media">Beberapa sumber media</Anchor> membatasi pembagian data dengan pihak ketiga. Oleh karena itu, postback untuk event yang dibatasi tidak akan dikirim ke mitra ini, terlepas dari pilihan yang dikonfigurasi untuk mengirim postback.

## Menyiapkan Amplitude

Pengaturan dilakukan dari halaman **Integrasi Aktif** , tetapi untuk menemukan partner, Anda harus pergi ke <Anchor target="_blank" href="/marketers/id/docs/partner-integrations">pasarterlebih</Anchor> dahulu.

> 📘 **Catatan**
>
> Sebelum mengatur integrasi, pastikan Anda <Anchor target="_blank" href="/marketers/id/docs/partner-integrations#contact-details">menghubungi mitra</Anchor> dan membuka akun dengan mereka.

**Untuk mengaktifkan integrasi:**

1. Dari menu atas halaman AppsFlyer mana pun, klik **Marketplace**.
2. Cari mitra dan pilih itu.
3. Klik **Atur integrasi**. Anda diarahkan ke halaman pengaturan integrasi.
4. Di tab **Integrasi** , pilih aplikasi untuk integrasi dan nyalakan **Aktiivasi mitra** .  
   **Catatan:** Sakelar harus aktif <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">(diaktifkan)</Anchor> selama Anda bekerja dengan mitra.
5. Selesaikan konfigurasi menggunakan tab yang relevan, seperti yang dijelaskan di bawah ini.

Untuk deskripsi terperinci dari Partner Configuration Window (Jendela Konfigurasi Mitra), klik di <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">sini</Anchor> .

<div id="integration-tab" />

<Accordion title="Tab Integration">

***Integration tab (Tab integrasi)*** dibagi menjadi beberapa bagian seperti dijelaskan di bawah ini.

### Aktifkan mitra

Pada **kunjungan pertama** ke sini, Anda harus mengaktifkan **Aktivasi Mitra** untuk mengaktifkan penyiapan parameter tab integrasi. Sakelar harus aktif selama Anda bekerja dengan mitra.  
Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">aktivasi mitra</Anchor>.

### Pengaturan Umum

#### Berbagi data tingkat lanjutan

Untuk berbagi informasi penginstalan tambahan dengan Amplitude, aktifkan **Berbagi data tingkat lanjut**. Saat diaktifkan, Amplitude menerima data berikut untuk instalasi (bukan in-app event) yang dipetakan ke Properti Amplitude yang tercantum:

| Properti Amplitude | Poin Data AppsFlyer |
| --- | --- |
| sub\_publisher | af\_siteid |
| network\_name | pid |
| adgroup\_name | af\_adset |
| creative\_name | af\_ad\_id |
| installed\_at | install\_timestamp |
| search\_term | af\_keywords |
| channel | af\_channel |
| user\_id | af\_customer\_user\_id |
| af\_sub1 | af\_sub1 |
| af\_sub2 | af\_sub2 |
| app\_version | app\_version |

#### Pusat Data Amplitude UE

Jika **Pusat Data Amplitude UE** tidak aktif, postback penginstalan dikirim ke pusat data AS.  
Untuk mengirim postback penginstalan ke pusat data Amplitude UE, aktifkan Pusat Data Amplitude UE.

#### Kunci API

Amplitude terhubung dengan AppsFlyer melalui Kunci API unik. Jika Anda belum memilikinya, Anda harus mendapatkannya dari Amplitude untuk melanjutkan integrasi atau mengikuti langkah-langkah di bawah ini.

<span id="obtaining-the-api-key-from-amplitude"></span>**Memperoleh kunci API dari Amplitude**

**Catatan**: Hanya pengguna yang memiliki peran Admin atau Manajer di Amplitude yang dapat mengakses Kunci API.

1. Masuk ke akun Amplitude Anda.
2. Dari kanan atas halaman, klik ikon setelan > **Setelan Organisasi**.  

   <Image alt="Amplitude" src="https://files.readme.io/214df773c045239924b65a4a1e6b0a1957f6b7ea09e225af80d83ffa0a469c26-16258070772625.png" width="240px" />
3. Klik **Proyek** dan pilih proyek untuk mengirim data ke AppsFlyer.   

   ![amplitude](https://files.readme.io/eaf158e4505f47f8da0fdae4f97be773ab32910352b50cab5ca5d4de3e8782ac-16335170399505.png)
4. Dari tab **Proyek** , salin kunci API Anda.  

   <Image alt="Amplitude" src="https://files.readme.io/cf65648a9a8c122febe2b36fd4bd0b9f7f436cac49cfeec7f41870f614a16c6c-16258070773649.png" width="648px" />
5. Lanjutkan untuk mengonfigurasi Amplitude di Dashboard AppsFlyer.

### Postback Default

AppsFlyer mengirimkan postback otomatis ke penginstalan pengguna Amplitude hanya ketika mereka diatribusikan ke Amplitude.

### Pengaturan in-app event

* Masukkan Kunci API.
* Saat **Pusat Data Amplitude** nonaktif, postback peristiwa dalam aplikasi dikirim ke pusat data AS.  
  **Untuk mengirimkan postback in-app event ke pusat data UE Amplitude, aktifkan Pusat Data Amplitude.**

Setelah Anda menyimpan konfigurasi, AppsFlyer mengirimkan data berikut ke Amplitude:

* ID Perangkat (IDFV/ID Iklan Google)
* Media Source
* Nama kampanye

Mengirim IDFA untuk perangkat iOS tunduk pada <Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework">persetujuan ATT oleh pengguna dan setelan Privasi Lanjutan</Anchor>.

### Postback in-app event

<Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#g">Konfigurasikan pengiriman postback in-app event</Anchor> ke Amplitude.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Tab Link Atribusi">

Tautan Atribusi tidak tersedia untuk Amplitude.

</Accordion>

<div id="cost-tab" />

<Accordion title="Tab Cost">

Data biaya tidak didukung dalam integrasi dengan mitra ini.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Tab Ad Revenue">

Pendapatan Iklan tidak didukung di integrasi dengan mitra ini.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Tab Permissions">

Izin tidak tersedia untuk Amplitude.

</Accordion>

## Melihat data atribusi di konsol Amplitude

Data atribusi yang dikirim dari AppsFlyer ke Amplitude ditampilkan di dashboard Anda sebagai peristiwa dan properti yang diawali dengan **[AppsFlyer]**:

![amplitude-properties.png](https://files.readme.io/bf52831ea6060172ce251136f47962ffb7f1ec9ffce13b9e35c614c4178e77f1-360009623597.png)

> 🚧 **Penting!**
>
> * Untuk mencegah masalah penginstalan dan pencocokan in-app event, aktifkan **API HTTP Amplitude** untuk postback penginstalan. Sebaliknya, jika in-app event pertama setelah penginstalan terjadi 72 jam setelah penginstalan, Amplitude tidak mencocokkan penginstalan dengan in-app event berikut. Dalam kasus ini, Amplitude membuang event penginstalan tetapi menampilkan in-app event (semua terjadi setelah 72 jam).
> * Dalam beberapa kasus, Amplitude menampilkan data yang berasal dari AppsFlyer sebagai "Diblokir". Jika Anda tidak dapat melihat data AppsFlyer di Amplitude, periksa apakah data tersebut didefinisikan sebagai peristiwa yang diblokir.![amplitude-blocked-data.png](https://files.readme.io/61312c421d4baff8126676f7b579489a6ba7580f7cdff71020c1bc68cf71fe42-4409532783889.png)

<div data-zendesk-anchors="01H8KPA9JJDP2945TQJT1Z3EY2=penting setting-up-amplitude=menyiapkan-amplitude 01H8KPA9JJXHMEYD8HD9DKK6D1=menyiapkan-amplitude 01H8KPA9JJG0MNK2EK75XVZBHX=catatan 01H8KPA9JK6XTFR0XW91XZB5XR=integration-tab activate-partner=aktifkan-mitra 01H8KPA9JKDRA680Y0WPZ172EM=aktifkan-mitra general-settings=pengaturan-umum 01H8KPA9JKF4VCA4S22SYT40WT=pengaturan-umum advanced-data-sharing=berbagi-data-tingkat-lanjutan 01H8KPA9JKJ2XN1AEPV74QVJYZ=berbagi-data-tingkat-lanjutan amplitude-data-center=pusat-data-amplitude-ue 01H8KPA9JKP0T0FDND97VA23EY=pusat-data-amplitude-ue api-key=kunci-api 01H8KPA9JKDYDPDGRXZSH2BAV8=kunci-api 01H8KPA9JK510YKV47816DT7E7=obtaining-the-api-key-from-amplitude default-postbacks=postback-default 01H8KRBGYQ973CT3H8GHZ8R0BH=postback-default inapp-event-settings=pengaturan-in-app-event 01H8KPA9JKM4S79160BEYN3B6V=pengaturan-in-app-event inapp-event-postbacks=postback-in-app-event 01H8KSQ76XE9Z191P1RMANF6EQ=postback-in-app-event 01H8KPA9JK4D6XX55Q55TBF4QN=attribution-link-tab 01H8KPA9JKK04NNDZA0XTSSWM5=cost-tab 01H8KPA9JK6X04T661D6YBHTVC=ad-revenue-tab 01H8KPA9JKG1VQJJBNFM6Q985X=permissions-tab viewing-attribution-data-in-the-amplitude-console=melihat-data-atribusi-di-konsol-amplitude 01H8KPA9JK75TA0H8T4P65BMSE=melihat-data-atribusi-di-konsol-amplitude 01H8KPA9JK2B4MR26GJZEZJSVT=penting-1" />
