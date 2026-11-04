---
title: Konfigurasi postback in-app event
metadata:
  keywords:
    - In-App Events
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-11T08:47:14Z'
  edited_at: '2024-01-16T11:41:58Z'
  id: 208439256
  locale: id
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/id/articles/208439256
---
> **Sekilas:** Ukur interaksi aplikasi dan kualitas pengguna Anda, dan optimalkan kampanye menggunakan data in-app event.

<div id="overview" />

## Ringkasan

In-app event memungkinkan pemasar untuk mengukur interaksi aplikasi dan kualitas pengguna dari berbagai sumber berbeda dan untuk membangun strategi akuisisi pengguna yang tepat. Jaringan iklan menggunakan informasi in-app event untuk mengoptimalkan kampanye dan menjalankan kampanye biaya per tindakan/event. Jaringan iklan menerima data in-app event melalui postback—yang dikirim dalam waktu aktual. <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview">Pelajari lebih banyak tentang rich in-app event</Anchor>.

<div id="postback-in-app-event-selection" />

## Pemilihan in-app event postback

Pemasar dapat memilih untuk in-app event mana yang ingin mereka kirimkan postback ke jaringan iklan, menggunakan setelan yang dijelaskan dalam artikel ini.

<div id="note" />

> 📘 **Catatan**
>
> * In-app event mencakup **event yang ditolak**, artinya in-app event diblokir oleh Protect360 atau event ditemukan tidak sesuai dengan aturan validasi target.
> * Jika bagian **Postback in-app event** tidak ada di tab **Integrasi** , itu berarti mitra belum menyiapkan catatan in-app event dengan AppsFlyer dalam konfigurasi awalnya. Mitra dapat menghubungi AppsFlyer menggunakan <Anchor target="_blank" href="https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif">widget asisten mitra</Anchor> untuk menyelesaikan integrasi.

<div id="in-app-event-postback-window" />

## Periode waktu postback in-app event

Periode waktu postback in-app event memungkinkan pemasar yang bekerja dengan jaringan berbasis CPA (biaya per tindakan) untuk mengonfigurasi jendela setelah konversi yang tidak lagi dikirim oleh postback event.

Misalnya, jika Anda ditagih untuk event yang terjadi dalam 15 hari sejak penginstalan pengguna, tetapkan periode waktu sebagai berikut:

<Image alt="15-day_in_app_event_postback_setting.png" src="https://files.readme.io/6ffcd335b85334015f518895b317d3a5e273f4e00c31e3694c0f95a22ba6d4fb-33379700644497.png" width="529px" />

Postback setelah periode ini tidak dikirim, dan jaringan tidak diberi tahu, tetapi event  tersebut tetap dicatat di AppsFlyer dan diatribusikan ke jaringan.

Postback selalu dikirim berdasarkan pengaturan jendela **saat ini** . Lihat contoh berikut:

| 1 Januari | Periode waktu 15 hari.<br /><br />Seorang pengguna menginstal aplikasi. |
| --- | --- |
| 2 Januari | Periode waktu berubah ke 10 hari |
| 14 Januari | Pengguna melakukan pembelian.<br /><br />Postback tidak dikirim ke jaringan iklan karena event tidak termasuk dalam periode waktu saat ini (10 hari). |
| 15 Januari | Periode waktu diubah menjadi 20 hari. |
| 18 Januari | Pengguna melakukan pembelian lagi.<br /><br />Kali ini postback dikirim—karena event tersebut termasuk dalam periode waktu saat ini (20 hari). |

<div id="default-postback-window" />

### Periode waktu postback default

Saat mulai menyiapkan postback in-app event, periode waktu default secara otomatis diatur ke enam bulan.

<div id="note-2" />

> 📘 **Catatan**
>
> Jika Anda sudah mulai menggunakan postback in-app event dengan mitra tertentu sebelum 30 Juli 2019, pengaturan default untuk periode waktu tersebut adalah Seumur Hidup. Artinya, postback in-app event selalu dikirim.

<div id="who-can-configure-postback-windows" />

### Siapa yang dapat mengonfigurasi periode waktu postback

* Pemasar
* Agensi, jika mereka diberi izin untuk **Izinkan untuk mengonfigurasi postback in-app event** .  
  **Catatan:** Pemasar dan agensi yang bekerja dengan jaringan iklan yang sama dapat mengonfigurasi periode waktu postback secara terpisah satu sama lain, berdasarkan kontrak mereka dengan jaringan.
* Mitra, jika mereka diberi izin untuk **Izinkan untuk mengonfigurasi postback in-app event** .

<div id="event-mapping" />

## Pemetaan event

Setiap pemasar dapat memberikan nama yang berbeda untuk event dengan jenis yang sama. Nama event semacam itu juga mungkin berbeda dari nama mitra.

Misalnya, saat pengguna membeli sesuatu melalui aplikasi, pemasar dapat menamainya `purchase`, atau ID yang kurang informatif, seperti `event5`, dan mitra dapat menamainya `purchase_event`.

Untuk memastikan event pemasar cocok dengan event yang sama dengan mitra, nama event harus dipetakan.

<div id="note-3" />

> 📘 **Catatan**
>
> Event yang dipetakan di tab Integrasi untuk mitra tertentu berlaku untuk <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">postback standar dan SKAN.</Anchor>

<div id="mapping-methods" />

### Metode pemetaan

Setiap mitra memutuskan metode mana yang akan digunakan untuk memetakan in-app event mereka:

* [Masukkan ID event mitra](/docs/in-app-event-postback-configuration#h_c513e6d4-d46f-4070-a98d-1888a5ea939d)
* [Pilih ID event dari daftar](/docs/in-app-event-postback-configuration#select-an-event-id-from-the-list)
* [Kirim event apa adanya (belum dipetakan)](/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped)

<div id="note-4" />

> 📘 **Catatan**
>
> * Tidak semua metode pemetaan muncul untuk semua mitra
> * Anda dapat [memberikan izin kepada mitra](/docs/in-app-event-postback-configuration#pemetaan-event-oleh-jaringan-iklan) untuk melakukan pemetaan sendiri

<div id="h_c513e6d4-d46f-4070-a98d-1888a5ea939d" />

<Accordion title="Masukkan ID event mitra">

* **Event AppsFlyer**: Dari daftar event aplikasi Anda, pilih event.
* **dipetakan ke event mitra**: Di bidang teks, masukkan ID event yang diterima dari mitra, yang sesuai dengan event aplikasi Anda (event AppsFlyer)

<div id="note-5" />

> 📘 **Catatan**
>
> * Nama event peka huruf besar-kecil. Untuk menghindari perbedaan, pastikan Anda menggunakan nama event yang benar untuk semua sumber media dan versi aplikasi.
> * Saat mengetik nama event, Anda dapat menggunakan spasi bergaris bawah (tanda hubung rendah) sebelum atau sesudah nama event. Pastikan untuk menggunakan spasi bergaris bawah hanya jika nama event yang dikirim dari AppsFlyer memiliki spasi bergaris bawah yang sama persis.

[![enter_event_name.png](https://files.readme.io/b9d65d3a6b4c1ab4d3f7e83cc2226af5c5a83e1e83cfbfa3df36d295ae568a45-33379700646545.png)](https://files.readme.io/b9d65d3a6b4c1ab4d3f7e83cc2226af5c5a83e1e83cfbfa3df36d295ae568a45-33379700646545.png)

</Accordion>

<div id="select-an-event-id-from-the-list" />

<Accordion title="Pilih ID event dari daftar">

* **Event AppsFlyer**: Dari daftar event aplikasi Anda, pilih event.
* **dipetakan ke event mitra**: Dari daftar event mitra yang telah ditentukan sebelumnya, pilih event yang sesuai dengan event aplikasi Anda (event AppsFlyer).

[![In-app_event_postbacks_en-us.png](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)

</Accordion>

<div id="send-events-as-they-are-unmapped" />

<Accordion title="Kirim event apa adanya (belum dipetakan)">

Beberapa mitra lebih suka menerima postback in-app event yang belum dipetakan—artinya nama event dikirim sesuai namanya di aplikasi Anda. Tidak masalah jika event tersebut disebut `purchase`, `acquisition`, atau `event5`.

Anda dapat memilih event mana yang belum dipetakan untuk dikirim ke mitra:

* **Tambahkan secara manual:** Pilih event tertentu.
* **Kirim semua event (tidak termasuk uninstal dan sesi)**: Kirim semua event Anda. Ini tidak termasuk uninstal, sesi (peluncuran aplikasi), dan event `af_app_opened` .

<div id="note-6" />

> 📘 **Catatan**
>
> Untuk mencegah pemasang iklan membagikan terlalu banyak informasi secara tidak sengaja dengan platform analisis pihak ketiga, kami telah menghapus opsi **Kirim semua event (tidak termasuk uninstal dan sesi)** untuk platform ini, mulai Maret 2019. Platform Analisis yang dikonfigurasi sebelum tanggal ini masih mempertahankan opsi penyiapan ini.

**Untuk menambahkan event secara manual:**

1. Klik **Tambahkan event**.
2. Pilih opsi postback:
   * **Event AppsFlyer**: Dari daftar event aplikasi Anda, pilih event.
   * **untuk pengguna dari**: Pilih <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#for-users-from">opsi pengiriman</Anchor> untuk event tersebut.
   * **termasuk**: Pilih [data mana yang akan disertakan](/docs/in-app-event-postback-configuration#data-untuk-disertakan-dalam-postback) dalam postback.
3. Ulangi prosedur ini untuk lebih banyak event.

![send_postbacks_as_is_en-us.png](https://files.readme.io/cc6b2bb1a381d88add035b9f369b0ba68dee8744aa3c2ee2f8f6f054b365a0dd-33379684962705.png)

**Untuk mengirim semua event:**

1. Pilih **Kirim semua event (tidak termasuk uninstal dan sesi)**.
2. Pilih opsi postback:  
   * **untuk pengguna dari**: Pilih [opsi pengiriman](/docs/in-app-event-postback-configuration#pilihan-untuk-mengirim-postback) untuk semua event.
   * **termasuk**: Pilih [data mana yang akan disertakan](/docs/in-app-event-postback-configuration#data-untuk-disertakan-dalam-postback) untuk semua event di postback.

![send_postbacsk_as_is_no_mapping.png](https://files.readme.io/458ca832d4176ccd306236cf10f211499e841dc9f550558987dff3ee683bd2d1-33379700651665.png)

</Accordion>

Untuk informasi selengkapnya tentang event pemetaan, lihat <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">postback in-app event</Anchor>.

<div id="options-for-sending-postbacks" />

### Pilihan untuk mengirim postback

Untuk setiap event, Anda dapat memilih kapan akan mengirim postback (dalam periode waktu postback):

* **Khusus mitra ini**: Kirim postback hanya jika event diatribusikan ke mitra ini—artinya, pengguna yang melakukannya berasal dari mitra ini.
* **Semua sumber media termasuk organik**: Kirim postback ke semua sumber media untuk event yang diatribusikan ke mitra mana pun dan untuk event organik—artinya, jika pengguna yang melakukannya berasal dari sumber media mana pun.

<div id="data-to-include-in-the-postbacks" />

### Data untuk disertakan dalam postback

Anda dapat memilih jenis data event yang dapat Anda bagikan dengan mitra di postback. Pilih salah satu opsi berikut:

* **Tidak ada nilai & tidak ada pendapatan**: Kirim hanya event tersebut tanpa parameter apa pun (nilai atau pendapatan).
* **Nilai dan tanpa pendapatan**: Mengirim semua parameter **tidak termasuk** nilai pendapatan.
* **Nilai dan pendapatan**: Mengirimkan semua parameter event, **termasuk** nilai pendapatan (jika ada dalam event).

Disarankan untuk berbagi pendapatan jika Anda ingin jaringan iklan mengoptimalkan kampanye Anda dan meningkatkan hasil kampanye. Akan tetapi, berbagi pendapatan tidak wajib. Pastikan untuk mengaktifkan berbagi pendapatan hanya untuk event dengan `af_revenue` yang ditentukan di nilai event mereka. Jika tidak, jaringan iklan mendapatkan event dengan nilai pendapatan kosong.

Dalam postback, `af_revenue` dan `af_currency` ditulis di luar event\_value JSON sebagai **moneter** dan **mata uang** dan dapat dikirim secara terpisah. Contoh struktur postback: `https://appsflyer.com/push?event_value=(event-value)&monetary=(monetary)&content_id=(af_content_id)`

**Catatan**: Saat memilih opsi dengan **Tanpa nilai & Tanpa pendapatan** atau **Nilai & tanpa pendapatan**, masing-masing parameter ditutupi dengan T/A.

<div id="h_01HBZCRNKGBEDSBZEY87KYQ60G" />

> 📄 **Contoh**
>
> Seorang pemasar mengirimkan event pembelian dengan event\_value sebagai berikut:
> `{af_revenue: 50.87, af_currency: USD, af_level=2,af_receipt_id=57601333}`
>
> Tabel di bawah menunjukkan bagaimana parameter dikirimkan:
>
>
>
> | Nama kolom | event\_value | moneter | currency |
> | --- | --- | --- | --- |
> | **Tidak ada nilai & tidak ada pendapatan** | T/A | N/A | N/A |
> | **Nilai & tidak ada pendapatan** | `{"af_currency":"N/A","af_content_id":"1234567",`<br /><br />`"af_revenue":"N/A","af_content_type":"category_a"}`<br /><br />`&monetary=N/A&content_id=1234567` | N/A | N/A |
> | **Nilai & pendapatan** | `"af_currency":"USD","af_content_id":"1234567",`<br /><br />`"af_revenue":200,"af_content_type":"category_a"}`<br /><br />`&monetary=1.856918&content_id=1234567` | 50,87 | USD |

<div id="conditional-in-app-event-postbacks" />

### Postback in-app event bersyarat

Filter postback in-app event menggunakan beberapa kondisi yang dapat dipetakan ke berbagai event. Hanya event yang memenuhi ketentuan filter yang dikirim ke mitra, termasuk SRN dan mitra Analisis. Gunakan fitur ini untuk:

* Mengoptimalkan segmentasi, personalisasi, dan retensi pengguna
* Meminimalkan data
* Melindungi privasi pengguna

<div id="h_01HBZCRNKHRTMHP3JPFVCS8D6N" />

> 📄 **Contoh**
>
> Pemasar dengan aplikasi game ingin mengoptimalkan kampanye yang dijalankan melalui jaringan iklan, tetapi hanya untuk pengguna yang lulus level 10 atau level 50, atau untuk pengguna yang membelanjakan $3 untuk pembelian aplikasi.
>
> [![in_app_event_condition__1_.png](https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png)](https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png)
>
> **Beginilah persyaratan untuk event ini ditetapkan:**
>
> * Saat ***level*** sama dengan ***10***, petakan ke ***`fb_mobile_level_acheived`***
>   Jika tidak (**ATAU**),
> * Saat ***level*** sama dengan ***50***, petakan ke ***`fb_mobile_level_acheived`***
>   Jika tidak (**ATAU**),
> * Ketika ***cost*** sama dengan ***3***, petakan ke ***`fb_mobile_purchase`***

**Untuk mengatur kondisi untuk event:**

1. Di halaman integrasi mitra, <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">tentukan dan petakan</Anchor> in-app event yang diperlukan untuk dikirim ke mitra.
2. Klik ikon![image.png](https://files.readme.io/8e650caf6472b316bd49bc25c45cc4c9d63b67770dd1c920fb873118b82ff868-17023682954385.png) Tambahkan persyaratan dari event yang diperlukan.
3. Masukkan bidang kondisi, seperti yang muncul di <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview#event-values">nilai event</Anchor>:
   * Nama properti
   * value
   * Event mitra untuk memetakan persyaratan (menggunakan salah satu dari [opsi pemetaan](/docs/in-app-event-postback-configuration#metode-pemetaan) ini)
4. Anda dapat menambahkan lebih banyak persyaratan, pastikan Anda memasukkan semua bidang persyaratan yang ada terlebih dahulu.
5. Klik **Save Integration (Simpan Integrasi)**.

<div id="considerations" />

#### Pertimbangan

Saat mengonfigurasi persyaratan, pastikan pertimbangan berikut dipenuhi untuk event agar dapat dikirim ke mitra:

<div id="condition-structure" />

<Accordion title="Struktur persyaratan">

* Baik properti maupun nilai dalam persyaratan harus cocok dengan data pada event tersebut.
* Saat ini, kondisi hanya dapat disetel ke "sama".
* Struktur kompleks seperti larik tidak didukung.

</Accordion>

<div id="multiple-conditions-for-an-event" />

<Accordion title="Berbagai persyaratan untuk suatu event">

* Jumlah maksimal persyaratan per event adalah 5.
* Setidaknya satu persyaratan harus dipenuhi agar postback dapat dikirim, tetapi hanya satu persyaratan yang dijalankan.
* Setiap kondisi diperiksa berdasarkan urutan kemunculan—persyaratan pertama yang harus dipenuhi akan dijalankan.
* Setiap persyaratan dipetakan secara terpisah. Nama event mitra diubah menjadi **Berdasarkan persyaratan**.
* Lebih dari satu kondisi dapat memiliki properti yang sama atau nilai yang sama, tetapi tidak ada dua kondisi yang dapat memiliki properti dan nilai yang sama.
* Lebih dari satu persyaratan dapat dipetakan ke event yang sama.

</Accordion>

<div id="note-9" />

> 📘 **Catatan**
>
> * Direkomendasikan untuk menguji fitur ini dengan aplikasi pengujian atau untuk event minor guna memahami dampaknya terhadap pengoptimalan kampanye.
> * Untuk melihat <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">konten postback</Anchor>, Anda dapat mengunduh laporan postback data lengkap.

<div id="editing-multiple-events" />

### Mengedit beberapa event

Saat memetakan event, nilai di bidang **untuk pengguna dari** dan **termasuk** dapat diedit untuk beberapa event dalam satu tindakan.

**Untuk mengedit beberapa event:**

1. Pilih event yang akan diperbarui.
2. Klik **Tindakan massal.**
3. Pilih pengaturan baru untuk diterapkan ke semua event yang dipilih:
   * **untuk pengguna dari** (pilih satu opsi saja)
     * Mitra ini saja
     * Semua sumber media, termasuk organik.
   * **termasuk** (pilih salah satu pilihan saja)
     * Tidak ada data (default)
     * Nilai tanpa pendapatan
     * Nilai dan pendapatan

[![In-app_event_postbacks_en-us.png](https://files.readme.io/559265d0e12e9e2ef62e0a19c5833465ee758821654877cffa4e75f6ff3f99b9-33379700657169.png)](https://files.readme.io/559265d0e12e9e2ef62e0a19c5833465ee758821654877cffa4e75f6ff3f99b9-33379700657169.png)

<div id="custom-events" />

### Event khusus

Daftar event yang tersedia untuk pemetaan hanya menampilkan event yang telah dilaporkan oleh SDK atau dari event server-ke-server ke AppsFlyer. Jika event yang ingin Anda petakan tidak muncul di daftar tarik-turun, hal ini dapat terjadi karena alasan berikut:

* Belum ada pengguna yang melakukan event tersebut
* Terakhir kali event itu terjadi waktunya lebih dari dua minggu lalu
* Anda memiliki banyak daftar event aktif

**Dalam salah satu kasus berikut, untuk memetakan event ke ID mitra:**

1. Ketik nama event.
2. Klik **Buat kustom**

   [![In-app_event_postbacks_en-us.png](https://files.readme.io/73ad7c6a34a292056ddd750901ce1e0a2975d6ce6f235610f0bee28aecd05d53-7901768117905.png)](https://files.readme.io/73ad7c6a34a292056ddd750901ce1e0a2975d6ce6f235610f0bee28aecd05d53-7901768117905.png)
3. Petakan event ke pengidentifikasi mitra.
4. Klik **Simpan Integrasi** untuk memastikan pemetaan direkam.

<div id="note-10" />

> 📘 **Catatan**
>
> * Saat event khusus ditambahkan di bawah mitra tertentu, event tersebut ditambahkan ke daftar event untuk semua mitra. Artinya, Anda dapat melihat event ini di bawah daftar tarik-turun event mitra mana pun.
> * Lihat <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#zd-tips">tips</Anchor> dan <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#limitations">batasan</Anchor> untuk menentukan nama dan parameter peristiwa.

**Agensi dan jaringan iklan:**

* Tidak dapat menambahkan event khusus
* Hanya dapat melihat dan/atau memetakan event setelah pemasar menambahkan event dan memberikan <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#permissions-tab">izinyang</Anchor> diperlukan

<div id="event-mapping-by-ad-networks" />

## Pemetaan event oleh jaringan iklan

Pemasar dapat mengizinkan jaringan iklan untuk memetakan event dan menonaktifkan postback sendiri. Untuk melakukannya, pemasar harus memberikan izin yang relevan ke jaringan iklan:

1. Di halaman **Integrasi Aktif** , temukan mitra yang ingin Anda beri izin.
2. Di bawah tab Izin, alihkan tombol **Izinkan untuk mengonfigurasi postback in-app event** ke **ON**.

![adnetwork-permissions-postbacks.png](https://files.readme.io/f8369f6a0a60d3c48ef66b51f61b3c81f00f6c88511f5f69b2c927788a64f018-33379700661265.png)

Setelah jaringan iklan menerima izin, mereka dapat memetakan event dengan mengikuti instruksi di [Ketikkan ID Event Ke Bidang Teks](/docs/in-app-event-postback-configuration#metode-pemetaan).

<div id="event-mapping-by-agencies" />

## Pemetaan event oleh agensi

Pemasar dapat mengizinkan agensi untuk mengonfigurasi postback in-app event.

**Untuk memberikan izin kepada agensi untuk mengonfigurasi postback dalam aplikasi:**

1. Temukan agensi di halaman **Integrasi aktif** .
2. Pilih apakah agensi dapat membagikan semua event atau hanya event yang diatribusikan ke jaringan iklan tertentu.
3. Pilih apakah agensi diizinkan untuk mengirimkan pendapatan event.
4. Pilih event tertentu yang boleh dibagikan oleh agensi.

![agency-events.png](https://files.readme.io/194b9a18f7721d4cc159f6385140cbb989108b70110e2e0d0f29f90d6115b10a-33379684973969.png)

<div id="h_01HDP3XHBPA5GZEVERMBN43JH0" />

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview">Rich in-app event—Tinjauan</Anchor>
> * <Anchor target="_blank" href="/marketers/id/docs/in-app-events-event-structure">Rich in-app event—Struktur event</Anchor>

<div data-zendesk-anchors="overview=ringkasan h_01HE0FQ1AB6NQCTKFTDW22SRYC=ringkasan postback-inapp-event-selection=pemilihan-in-app-event-postback h_01HBZCRNKGH1PAK8RC846PPRTS=pemilihan-in-app-event-postback h_01HBZCRNKGQTJ4VJ00TVTS14N2=catatan inapp-event-postback-window=periode-waktu-postback-in-app-event h_01HBZCRNKGS71QGK5506N07K84=periode-waktu-postback-in-app-event default-postback-window=periode-waktu-postback-default h_01HBZCRNKGV5CREN5K0RBDMBH6=periode-waktu-postback-default h_01HBZCRNKGVXN233AFFHG42NW9=catatan-1 who-can-configure-postback-windows=siapa-yang-dapat-mengonfigurasi-periode-waktu-postback h_01HBZCRNKG7AECFSBXV2WDD9AR=siapa-yang-dapat-mengonfigurasi-periode-waktu-postback event-mapping=pemetaan-event h_01HBZCRNKG7SZ4T41BY60BAJZN=pemetaan-event h_01HBZCRNKGT64TE2XYK9VS4ATD=catatan-2 mapping-methods=metode-pemetaan h_01HBZCRNKG4EF9MSY696SD5VQ9=metode-pemetaan h_01HBZCVAGPSNDJMWRWENEP45N7=catatan-3 enter-the-partner-event-id=h_c513e6d4-d46f-4070-a98d-1888a5ea939d h_01HBZCRNKG1E63DZRSDWTB8CJN=catatan-4 h_01HBZCRNKGWQBNY8RP4MTW3DXV=select-an-event-id-from-the-list h_01HBZCRNKG4981T00N70X2GP0J=send-events-as-they-are-unmapped h_01HBZCRNKGXJ683VHFTE277ER9=catatan-5 options-for-sending-postbacks=pilihan-untuk-mengirim-postback h_01HBZCRNKG1VN7E6TVCPDW7M73=pilihan-untuk-mengirim-postback data-to-include-in-the-postbacks=data-untuk-disertakan-dalam-postback h_01HBZCRNKGESY50NSZGTVPT25M=data-untuk-disertakan-dalam-postback h_01HBZCRNKGBEDSBZEY87KYQ60G=contoh conditional-inapp-event-postbacks=postback-in-app-event-bersyarat h_01HBZCRNKG5X3B2NJZZP6ER2CX=postback-in-app-event-bersyarat h_01HBZCRNKHRTMHP3JPFVCS8D6N=contoh-1 considerations=pertimbangan h_01HBZCRNKHBR57YVHZQP7NJBAP=pertimbangan h_01HBZCRNKHJGBYNP9JN24CQ3CC=condition-structure h_01HBZCRNKH1R0FR61C6TA0MCTN=multiple-conditions-for-an-event h_01HBZCRNKHF6TFP0N302D7DCMD=catatan-6 editing-multiple-events=mengedit-beberapa-event h_01HBZCRNKHHD3WC4GTJT9NSJ4C=mengedit-beberapa-event custom-events=event-khusus h_01HBZCRNKH754PANWSZ4FMXJVQ=event-khusus h_01HBZCRNKH4PVR3FEMTMERW3M1=catatan-7 event-mapping-by-ad-networks=pemetaan-event-oleh-jaringan-iklan h_01HBZCRNKH1GCZY17R04WTZ0MQ=pemetaan-event-oleh-jaringan-iklan event-mapping-by-agencies=pemetaan-event-oleh-agensi h_01HBZCRNKHHF3E6CZNQQG0Q4VS=pemetaan-event-oleh-agensi h_01HDP3XHBPA5GZEVERMBN43JH0=lihat-juga" />
