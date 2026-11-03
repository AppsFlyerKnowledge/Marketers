---
title: Rich in-app event—Tinjauan
metadata:
  keywords:
    - ios
    - Rich
    - In-App
    - android
    - Advertisers
    - In app events
    - Marketers
    - inapp events
    - attribution
    - inapp
    - inapp events attribution
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2017-11-02T08:12:51Z'
  edited_at: '2023-11-20T06:30:05Z'
  id: 115005544169
  locale: id
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/id/articles/115005544169
---
> **Sekilas:** Rekam rich in-app event pasca penginstalan (seperti login, pendaftaran, atau pembelian dalam aplikasi) yang diatribusikan dengan sumber media dan kampanye.

## Mengapa merekam in-app event?

In-app event memberikan wawasan tentang apa yang terjadi di aplikasi Anda dan merupakan alat yang ideal untuk menentukan nilai pengguna aplikasi dan **kualitas lalu lintas yang berasal dari sumber media yang berbeda** . Merekam in-app event membantu Anda mengukur KPI seperti ROI (Laba atas Investasi) dan LTV (Nilai Periode Retensi).

Jika pengguna melakukan registrasi, menyelesaikan tutorial, menambahkan item ke keranjang belanja, atau melakukan pembelian, maka data in-app event dapat mencatat event beserta detailnya. Implementasi in-app event adalah wajib untuk semua tujuan analisis pasca penginstalan.

## Tentang in-app events

In-app event terdiri dari nama event dan dapat menyertakan parameter event. Saat Anda menambahkan parameter event ke in-app event, ini disebut sebagai rich in-app event. Parameter event memberi Anda lebih banyak konteks dan informasi tentang event yang terjadi. Misalnya, meskipun parameter ini membantu mengetahui bahwa pengguna melakukan pemesanan, parameter event dapat memberi Anda detail seperti jenis pembelian, tujuan, dan pendapatan.

![travel.png](https://files.readme.io/0ebe64e7aa3ccc40ef014c55ee3a91edf678e21b2d00a7f8be1298d6b494e925-30858351609617.png)

> 👍 **Tips**
>
> Ingin tahu lebih banyak tentang in-app event? Lihat <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7774/play/18613/in-app-events-and-integrated-partners-part-1">kursus singkat dan informatif ini di Portal Pembelajaran AppsFlyer</Anchor>.

<div id="predefined-and-custom-events" />

<Accordion title="Event kustom dan yang telah ditentukan sebelumnya">

In-app event yang ingin Anda kirim mewajibkan pengembang menerapkan kode jika berlaku di aplikasi Anda. Nama event dan parameter event diklasifikasikan sebagai berikut:

* **Predefined (Telah ditentukan sebelumnya)** : Ini adalah nama event dan parameter event yang biasanya digunakan di antara berbagai aplikasi. Kami sangat menyarankan untuk menggunakan <Anchor target="_blank" href="/marketers/id/docs/in-app-events-event-structure#nama-event-yang-telah-ditentukan-sebelumnya">nama</Anchor> <Anchor target="_blank" href="/marketers/id/docs/in-app-events-event-structure#parameter-event-yang-telah-ditentukan-sebelumnya">event dan parameter event</Anchor> yang telah ditentukan sebelumnya sebanyak mungkin karena alasan berikut:
  * Penamaan yang telah ditentukan sebelumnya memungkinkan pemetaan event secara otomatis ke mitra.
  * Jika AppsFlyer memutuskan untuk mengubah nama event atau parameter event apa pun, implementasi Anda kompatibel dengan versi sebelumnya.
* **Kustom:** Ini adalah nama event dan parameter yang Anda tetapkan untuk skenario pengguna tertentu yang terjadi di aplikasi Anda. Anda dapat menggunakan nama event kustom atau string nama parameter, tetapi perlu diingat bahwa event kustom memerlukan pemeliharaan oleh pengembang Anda. Lihat [Tips](/docs/in-app-events-overview#zd-tips) dan [Batasan](/docs/in-app-events-overview#limitations).

</Accordion>

<div id="revenue-events" />

<Accordion title="Event pendapatan">

Setiap kali Anda mengirim in-app event seperti pembelian atau pemesanan penerbangan, Anda mengirimkannya dengan pendapatan terkait. Satu-satunya parameter yang menghasilkan pendapatan dalam in-app event adalah `af_revenue`

* <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#record-revenue">Mencatat pendapatan di SDK</Anchor>
* Mencatat Pendapatan di Unity

Anda juga dapat mencatat pendapatan negatif jika pengguna membatalkan pembelian atau jika Anda melakukan pengembalian dana. Untuk mencatat pendapatan negatif, yang harus Anda lakukan adalah menambahkan tanda minus (-) ke nilai pendapatan yang Anda berikan ke `af_revenue`

**af\_revenue**adalah satu-satunya parameter yang mengakumulasi pendapatan pengguna Anda. Selalu gunakan bersama event in-app yang mewakili penghasil pendapatan sebenarnya dalam logika bisnis Anda.

**af\_revenue**juga dapat menghasilkan nilai pendapatan negatif jika Anda perlu mencatat event seperti transaksi yang dibatalkan atau pengembalian dana.

Nilai pendapatan hanya boleh berisi angka (dan koma desimal, jika diperlukan):

* **Jangan** sertakan karakter lain atau format nilai pendapatan dengan cara lain mana pun. Artinya tidak boleh ada koma, tanda mata uang f(atau contoh $), karakter khusus, atau teks.
* AppsFlyer memberikan nilai pendapatan dengan **presisi hingga lima desimal**.
* Kisaran nilai ini harus -10.000 hingga 10.000 dalam dolar atau jumlah mata uang asli yang setara. Nilai di luar rentang ini disertakan dalam laporan data lengkap, namun tidak dalam laporan teragregasi.
* Contoh: 1234.56
* Jika pendapatan dikirim sebagai string, nilai di dalam tanda kutip harus valid. Misalnya: "1234.56".

**Catatan**:

* AppsFlyer menampilkan pendapatan persis seperti yang dikirim dari SDK. Nilai ini tidak termasuk penghitungan untuk PPN atau komisi toko aplikasi, dll., kecuali ini disertakan oleh pengembang di sisi SDK sebelum dikirim ke AppsFlyer.

**af\_currency** mewakili mata uang yang dinyatakan dalam af\_revenue (atau af\_price). Jika af\_currency tidak ada di parameter event, AppsFlyer mengirimkannya dengan nilai default "USD".

Anda dapat menggunakan**af\_price**sebagai parameter moneter yang tidak dihitung sebagai pendapatan (seperti di event “Tambah ke Keranjang Belanja”). Parameter ini mengacu pada harga barang individual. Jumlah total semua pembelian muncul di bawah parameter af\_revenue.

### Mata uang pendapatan

Penting untuk memahami cara AppsFlyer menangani pengaturan mata uang dan konversi mata uang.

AppsFlyer menangani selisih antara mata uang pengaturan aplikasi dan mata uang in-app event menggunakan konversi mata uang.

![revenue_normalization_flow.png](https://files.readme.io/f890d34168f92202c94da4bfa548bd0f471c98dec9c8d4282b2549f5878e9321-46334674326033.png)

Diagram di atas menunjukkan proses berikut:

1. In-app event dikirim - mata uang berbeda untuk setiap event
2. AppsFlyer menormalkan semua mata uang ke USD
3. AppsFlyer memproses data pendapatan
4. Data pendapatan di dasbor ditampilkan dalam mata uang pengaturan aplikasi
5. AppsFlyer mengisi data pendapatan dalam laporan data lengkap dalam mata uang pengaturan event dan aplikasi

AppsFlyer menggunakan <Anchor target="_blank" href="https://openexchangerates.org/">Open Exchange Rates</Anchor> untuk konversi mata uang. Nilai tukar ini diperbarui setiap jam. Kapan pun AppsFlyer melakukan konversi mata uang, AppsFlyer menggunakan nilai tukar pembaruan per jam terakhir.

#### Konversi mata uang

> 📄 **Contoh**
>
> Di pengaturan aplikasi Anda, Anda menyetel mata uang ke GBP. Seorang pengguna dari Prancis membeli produk menggunakan aplikasi Anda. Harga dinyatakan dalam EUR (€). In-app event yang Anda kirim ke AppsFlyer terlihat seperti ini:
>
> ```java
> Map<String, Object> eventValue = new HashMap<String, Object>();
> eventValue.put(AFInAppEventParameterName.REVENUE,200);
> eventValue.put(AFInAppEventParameterName.CONTENT_TYPE,"category_a");
> eventValue.put(AFInAppEventParameterName.CONTENT_ID,"1234567");
> eventValue.put(AFInAppEventParameterName.CURRENCY,"EUR");
> AppsFlyerLib.getInstance().trackEvent(getApplicationContext() , AFInAppEventType.PURCHASE , eventValue);
> ```
>
> Dalam hal ini, AppsFlyer mengonversi pendapatan dari EUR ke USD, lalu ke GBP. Mari kita asumsikan nilai tukarnya adalah €1 = $1,13. Jadi €200 menjadi $226,85. Selanjutnya, AppsFlyer mengonversi dari USD ke GBP. Mari kita asumsikan nilai tukarnya adalah $1 = £0,78. Jadi $226,85 menjadi £176,92.

#### Tampilan mata uang

<Anchor target="_blank" href="/marketers/id/docs/app-settings#localization-currency">Mata uang ditetapkan dalam pengaturan aplikasi</Anchor>. Mata uang yang Anda tetapkan di pengaturan aplikasi, adalah mata uang yang muncul di dasbor. Mata uang apa pun yang Anda kirimkan untuk in-app event, pendapatan di dasbor selalu muncul dalam mata uang yang Anda tetapkan di pengaturan aplikasi.

> 📄 **Contoh**
>
> Misalnya Anda mengirim in-app event dengan mata uang yang berbeda dari yang ditetapkan di pengaturan aplikasi, atau tanpa mata uang sama sekali. Dalam contoh ini, mata uang di pengaturan aplikasi disetel ke **GBP** .
>
> Anda mengirimkan tiga in-app event ke AppsFlyer.
>
> 1. Event A memiliki pendapatan **234** dan **GBP** sebagai mata uang
> 2. Event B memiliki pendapatan **171** dan **EUR** sebagai mata uang
> 3. Event C memiliki pendapatan **171** tetapi **tidak ada mata uang** yang ditentukan
>
> #### Data pendapatan di dasbor
>
> Pendapatan yang muncul di dasbor adalah **nilai yang dikonversi** dari mata uang in-app event ke USD, lalu ke mata uang pengaturan aplikasi.
>
> Jika tidak ada mata uang yang ditentukan dalam event tersebut, **AppsFlyer akan menetapkan default ke USD**. Dasbor menampilkan event dan pendapatan sebagai berikut:
>
>
>
> | In-App Event | User Unik | Jumlah Tindakan | Pendapatan |
> | --- | --- | --- | --- |
> | A | 1 | 1 | £234 |
> | B | 1 | 1 | £149,4 - dikonversi dari EUR ke USD dan kemudian ke GBP. |
> | C | 1 | 1 | £132,9 - default ke USD karena tidak ada mata uang yang ditentukan. Dikonversi dari USD ke GBP secara langsung. |
>
>
>
> #### Data pendapatan dalam laporan data lengkap
>
> Jika Anda menyetel mata uang ke **GBP** di pengaturan aplikasi, tetapi mengirim in-app event dengan mata uang berbeda, laporan data lengkap menunjukkan pendapatan dalam mata uang pengaturan aplikasi dan mata uang in-app event.
>
> Jika Anda menyetel mata uang ke **GBP** di pengaturan aplikasi, tetapi mengirim in-app event tanpa mata uang, laporan data lengkap menunjukkan pendapatan dalam mata uang pengaturan aplikasi dan dalam USD.
>
> Laporan data lengkap in-app event menampilkan event dan pendapatan sebagai berikut:
>
>
>
> | Event | Pendapatan Event | Mata Uang Pendapatan Event | Pendapatan Event GBP |
> | --- | --- | --- | --- |
> | A | 234 | GBP | 234 |
> | B | 171 | EUR | 149,4 - dikonversi dari EUR ke USD dan kemudian ke GBP. |
> | C | 171 | USD | £132,9 - default ke USD karena tidak ada mata uang yang ditentukan. Dikonversi dari USD ke GBP secara langsung. |

</Accordion>

## Mengirim event

Ada beberapa cara untuk mengirim in-app event ke AppsFlyer:

* <Anchor target="_blank" href="/marketers/id/docs/sdk-integration-overview">**SDK AppsFlyer:**</Anchor> Ini adalah cara paling umum untuk mengirim event. Anda dapat mengirimkan rich in-app event yang merekam tindakan pengguna di aplikasi menggunakan API in-app event AppsFlyer pada level SDK.
* **<Anchor target="_blank" href="/marketers/id/docs/server-to-server-events-api-for-mobile-s2s-mobile">API server-ke-server:</Anchor>** Gunakan API server-ke-server untuk mengirim event yang terjadi di luar aplikasi seluler, langsung ke AppsFlyer. Misalnya, jika Anda memiliki pengguna yang aktif di antarmuka web dan seluler, Anda dapat mencatat event dari kedua sumber dan mengatribusikannya ke pengguna yang sama di AppsFlyer. Ini bisa berupa in-app event atau event lainnya, seperti event situs web, event pusat panggilan, atau pembelian di toko fisik Anda.
* **<Anchor target="_blank" href="/marketers/id/docs/legacy-receipt-validation-for-in-app-purchases">Validasi tanda terima</Anchor>** Ini adalah mekanisme aman di mana platform pembayaran, misalnya, Apple dan Google, memvalidasi bahwa pembelian dalam aplikasi terjadi seperti yang dilaporkan. Memvalidasi pembelian adalah alat utama untuk mencegah penipuan event pendapatan. Fitur ini juga membantu Anda untuk melihat pendapatan sebenarnya, dan menyaring pembelian dalam aplikasi yang belum selesai.
* **<Anchor target="_blank" href="/marketers/id/docs/in-app-events-for-hybrid-apps">Aplikasi hybrid:</Anchor>** Aplikasi ini menggabungkan tampilan asli dan konten HTML dan juga dapat merekam in-app event. Namun, karena SDK hanya dapat mengirim event dari sisi native, pengembang harus meneruskan semua data event ke kode native.

## Mengatur in-app event

Proses penyiapan in-app event mengharuskan pemasar dan pengembang bekerja sama sebagai berikut:

| Langkah | Peran | Tugas | Detail |
| --- | --- | --- | --- |
| 1 | Pemasar | Tentukan in-app event yang ingin Anda ukur. [Tentukan](/docs/in-app-events-overview#defining-an-inapp-event) dan komunikasikan <Anchor target="_blank" href="/marketers/id/docs/in-app-events-event-structure#nama-event-yang-telah-ditentukan-sebelumnya">nama event</Anchor> dan <Anchor target="_blank" href="/marketers/id/docs/in-app-events-event-structure#parameter-event-yang-telah-ditentukan-sebelumnya">parameter event</Anchor> kepada pengembang Anda. | Disarankan untuk memulai dengan 3-5 event yang dapat Anda gunakan sebagai KPI untuk mengukur kualitas pengguna Anda (misalnya, pembelian, pendaftaran, dan berbagi). Parameter event bersifat opsional, dan Anda dapat menggunakan parameter event apa pun dengan nama event apa pun.<br /><br />Lihat [Event yang direkomendasikan menurut bisnis vertikal](/docs/in-app-events-overview#recommended-events-by-business-vertical) untuk in-app event yang umum. |
| 2 | Pengembang | Terapkan kode di aplikasi Anda jika berlaku. | Lihat dokumentasi pengembang <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk">di sini</Anchor>. |
| 3 [Opsional] | Pemasar | Bekerja samalah dengan pengembang untuk mengatur <Anchor target="_blank" href="/marketers/id/docs/customer-user-id-field-cuid">Bidang ID Pengguna Pelanggan/Customer User ID field (CUID)</Anchor>. | Bidang ini membantu memperkaya data in-app event dengan merujuk silang data atribusi AppsFlyer dengan data Anda yang lain menggunakan kode CUID. |
| 4 [Opsional] | Pemasar | <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#pemetaan-event">Petakan event</Anchor> ke mitra yang relevan di dasbor. | Ini adalah tugas yang berkelanjutan, tergantung pada mitra yang Anda integrasikan. |

<div id="defining-an-inapp-event" />

<Accordion title="Menentukan in-app event">

Setelah Anda menentukan in-app event yang ingin Anda ukur, gunakan <Anchor target="_blank" href="https://evgen.appsflyer.com/">Pembuat in-app event</Anchor> kami untuk menentukan event dan parameter sebagai berikut:

1. Pilih nama event yang paling sesuai dengan skenario yang ingin Anda rekam.
2. Pilih parameter event yang ingin Anda kaitkan dengan event. Pilih parameter yang akan memberikan konteks tambahan pada event dan memperkaya data.
3. Unduh file yang telah selesai dari pembuat in-app event, lalu bagikan dengan pengembang Anda.

> 📄 **Contoh**
>
> Seorang pemasar untuk aplikasi eCommerce ingin merekam jenis konten yang dilihat pengguna untuk lebih memahami kategori apa yang paling populer dan menghubungkan tampilan produk dengan penjualan produk.
>
> Tabel berikut menunjukkan contoh struktur event yang diberikan pemasar kepada pengembang:
>
> <table><thead><tr><th>eventName</th><th>Parameter event</th><th>Nilai parameter</th><th>Kapan event tersebut dipicu?</th></tr></thead><tbody><tr><td rowspan="3">af_content_view</td><td>af_price</td><td>Harga produk</td><td rowspan="3"><p><span>Saat pengguna melihat halaman rincian produk tertentu</span></p></td></tr><tr><td><span>af_content_type</span></td><td><span>Nama kategori produk, misalnya, sepatu </span></td></tr><tr><td><span>af_content_id</span></td><td><p><span>ID produk, misalnya, SKU</span></p></td></tr></tbody></table>

</Accordion>

<div id="recommended-events-by-business-vertical" />

<Accordion title="Event yang direkomendasikan oleh bisnis vertikal">

Tabel berikut menyediakan tautan ke artikel yang menyertakan contoh dan alur kejadian dalam aplikasi umum yang kami sarankan untuk direkam per bisnis vertikal.

| Bisnis vertikal | Judul artikel |
| --- | --- |
| <Image alt="InApp_Events_games.png" src="https://files.readme.io/ee2d46ddf11a6a6cacc95399ffd778d6613ecdd905d237cd971073e095cada5b-20659444711953.png" width="38px" /> | <Anchor target="_blank" href="/marketers/id/docs/recommended-gaming-app-events">Event aplikasi game yang direkomendasikan</Anchor> |
| <Image alt="InApp_Events_ecommerce.png" src="https://files.readme.io/c6497d250c22c7de5c13f01278ac72d8b3117bc60712ba3fe40ad24efcdc4947-360019350097.png" width="37px" /> | <Anchor target="_blank" href="/marketers/id/docs/recommended-ecommerce-app-events">Event aplikasi eCommerce yang direkomendasikan</Anchor> |
| <Image alt="InApp_Events_streaming.png" src="https://files.readme.io/27f2f38b0ce7d242580c60edeff730079a3801f98ff0d7cb8a605380ed11071f-20659453813905.png" width="39px" /> | <Anchor target="_blank" href="/marketers/id/docs/recommended-entertainment-app-events">Event aplikasi hiburan yang direkomendasikan</Anchor> |
| <Image alt="banking.png" src="https://files.readme.io/260638f807a43f42c6ff99bb72b8d4113b2df09436b9322a820888ad3f8a01ae-20659476893969.png" width="36px" /> | <Anchor target="_blank" href="/marketers/id/docs/recommended-finance-and-banking-app-events">Event aplikasi keuangan dan perbankan yang direkomendasikan</Anchor> |
| <Image alt="InApp_Events_lending.png" src="https://files.readme.io/e3465ee913a65a215f1c224db20d4f1fd61fd0bf488b798073c94b4e8387d252-20659507679889.png" width="36px" /> | <Anchor target="_blank" href="/marketers/id/docs/recommended-p2p-lending-app-events">Event aplikasi pinjaman P2P yang direkomendasikan</Anchor> |
| <Image alt="education.png" src="https://files.readme.io/fb036c8f3b0cb4cc06a5284c26089bbb361273ab628bc5b740692bc49e7a2c40-20659493109393.png" width="37px" /> | <Anchor target="_blank" href="/marketers/id/docs/recommended-online-education-app-events">Event aplikasi pendidikan online yang direkomendasikan</Anchor> |
| <Image alt="InApp_Events_ride.png" src="https://files.readme.io/3901cfcc0cc821cc9c93edbe806bc2d570698be366b76b3710cb60e9aa190d91-20659532208401.png" width="37px" /> | <Anchor target="_blank" href="/marketers/id/docs/recommended-ride-hailing-app-events">Event aplikasi jasa transportasi online (ride-hailing) yang direkomendasikan</Anchor> |
| <Image alt="InApp_Events_flight.png" src="https://files.readme.io/7a09c4a641dd5e797bffc41a6e66b20efe5660721f37abac3dd12ac83688b37b-20659533911697.png" width="38px" /> | <Anchor target="_blank" href="/marketers/id/docs/recommended-flight-booking-app-events">Event aplikasi pemesanan penerbangan yang direkomendasikan</Anchor> |
| <Image alt="InApp_Events_hotel.png" src="https://files.readme.io/ffc23cc65b6b6cfe99c12e988cca3df6667058b7e3a672db3639472a17602546-20659548553745.png" width="37px" /> | <Anchor target="_blank" href="/marketers/id/docs/recommended-hotel-booking-app-events">Event aplikasi pemesanan hotel yang direkomendasikan</Anchor> |
| <Image alt="5669_Healthcare_icon_3.png" src="https://files.readme.io/bb4bb46d842d1f2d08da548724e7d69910b0a050302fcdbd1500a8ebef325516-20659200427281.png" width="37px" /> | <Anchor target="_blank" href="/marketers/id/docs/recommended-healthcare-app-events">Event aplikasi perawatan kesehatan yang direkomendasikan</Anchor> |
| <Image alt="telecommunications_icon.png" src="https://files.readme.io/42f1aac3b825957d9d0584d83480c441b9d53665cc6cf1a6b8cd1803bb9b6121-20659194885393.png" width="39px" /> | <Anchor target="_blank" href="/marketers/id/docs/recommended-telecommunication-app-events">Event aplikasi telekomunikasi yang direkomendasikan</Anchor> |
| <Image alt="InApp_Events_eWallet.png" src="https://files.readme.io/4d2ed4994bbe8e8eca7009b8ec8f5dbf22a626421a7a1efb213ddb4a12c7b487-4402543191825.png" width="39px" /> | <Anchor target="_blank" href="/marketers/id/docs/recommended-ewallet-app-events">Event aplikasi eWallet yang direkomendasikan</Anchor> |
| <Image alt="soccer_ball.png" src="https://files.readme.io/2c5150b2c50ec166878cd976154dc81c0dc8a1e710fa8869aa582b535313b464-4413968925585.png" width="39px" /> | <Anchor target="_blank" href="/marketers/id/docs/recommended-sports-betting-events">Acara taruhan olahraga yang direkomendasikan</Anchor> |

</Accordion>

<div id="view-inapp-event-data" />

<Accordion title="Lihat data in-app event">

In-app event diatribusikan ke sumber media yang bertanggung jawab atas penginstalan di sepanjang masa pakai pengguna. Data event ditampilkan sebagai <Anchor target="_blank" href="/marketers/id/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">Life Time Value (Nilai Masa Pakai) atau Activity data (data Aktivitas)</Anchor>.

Anda dapat melihat data in-app event di lokasi berikut:

* Halaman ikhtisar dasbor: Menampilkan performa akuisisi pengguna (UA) LTV secara real-time. **Catatan** : Ini mencakup pendapatan yang dibagi antara pengguna organik dan non-organik yang dilaporkan melalui in-app event, dan penargetan ulang pendapatan yang <Anchor target="_blank" href="/marketers/id/docs/resolve-retargeting-double-attribution">diatribusikan dua kali.</Anchor>
* Halaman event: Menampilkan kinerja acara dalam aplikasi LTV di seluruh sumber media
* <Anchor target="_blank" href="/marketers/id/docs/activity-dashboard">Laman aktivitas</Anchor> : Menampilkan aktivitas dalam aplikasi untuk rentang tanggal yang dipilih.
* <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">Laporan in-app event data lengkap</Anchor>: Menampilkan data aktivitas, artinya, daftar kronologis tindakan yang dilakukan oleh seluruh basis pengguna Anda. Laporan ini menyertakan nilai parameter event, misalnya:

  ```json
  {
    "af_level":"10",
    "af_score":"3387",
    "arena":"7",
    "char_type":"paladin"
  }
  ```

  Perhatikan bahwa pelaporan data lengkap adalah fitur premium.

</Accordion>

<div id="zd-tips" />

<Accordion title="Tips">

Ingat hal berikut ini saat menentukan nama dan parameter event di aplikasi:

* Untuk konsistensi data dalam pelaporan data lengkap, sebaiknya tentukan dan gunakan nama dan struktur in-app event yang sama di semua platform.
* Gunakan jumlah event minimal untuk mempermudah dalam membandingkan kualitas pengguna yang berasal dari sumber yang berbeda.
* **Penting bagi Anda untuk memastikan privasi pengguna Anda.** **Jangan mengisi nilai in-app event dengan data terbatas yang dapat mengidentifikasi mereka secara langsung**. **Misalnya alamat email, nama, nomor identitas, dan di beberapa lokasi kode pos. Untuk informasi selengkapnya tentang data yang dibatasi, baca <Anchor target="_blank" href="https://www.appsflyer.com/legal/services-privacy-policy/">kebijakan privasi layanan</Anchor>.**
* Perhatikan bahwa AppsFlyer mengumpulkan alamat IP perangkat selama <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy/#engagementinformation">interaksi</Anchor>. Dalam beberapa yurisdiksi atau skenario penggunaan, alamat IP dapat dianggap sebagai informasi pribadi (PII). Kami menggunakan alamat IP untuk mendapatkan lokasi geografis yang luas (kota, tingkat kecamatan) perangkat tetapi bukan alamat spesifik. Jika perlu, Anda dapat memilih untuk <Anchor target="_blank" href="/marketers/id/docs/apply-ip-masking-to-user-data">menyembunyikan alamat IP</Anchor> agar tidak muncul dalam laporan data lengkap.
* Event in-app adalah satu-satunya sumber data pendapatan di AppsFlyer. Anda dapat melampirkan nilai pendapatan tertentu untuk setiap event dan melihatnya di dashboard aplikasi. Pelajari lebih lanjut tentang [parameter monetisasi](/docs/in-app-events-overview#revenue-events).

  ![revenue_data.png](https://support.appsflyer.com/hc/article_attachments/360020607037)

</Accordion>

<div id="limitations" />

<Accordion title="Batasan">

Ingat hal berikut ini saat menentukan nama dan parameter event di aplikasi:

* Sebaiknya gunakan hanya karakter alfanumerik huruf kecil (az dan 0-9) untuk nama in-app event Anda. Nama peristiwa peka huruf besar/kecil, artinya af\_purchase dan af\_PURCHASE adalah dua peristiwa berbeda dalam data lengkap. Namun, dalam laporan gabungan (misalnya, Ikhtisar, atau event), laporan tersebut dapat ditampilkan sebagai satu event.
* Ada batas kardinalitas 300 event unik per hari. <Anchor target="_blank" href="/marketers/id/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_events_limit">Pelajari lebih lanjut</Anchor>
* Pengguna unik hanya dihitung untuk 100 event pertama setelah mereka menginstal aplikasi.
* Nama event tidak boleh diawali dengan karakter berikut: " = + -
* Nilai event tidak boleh berisi karakter + , kecuali dalam URL yang disandikan atau disandikan sesuai <Anchor target="_blank" href="https://www.w3schools.com/tags/ref_urlencode.ASP">ASCII</Anchor>.
* Nama event tidak boleh berisi spasi kosong. Anda dapat gunakan spasi yang digarisbawahi (tanda hubung bawah) sebelum atau sesudah nama event.
* Nilai event tidak boleh melebihi 2000 karakter karena nilai mungkin akan dipersingkat dalam laporan data lengkap.
* Jika Anda menyertakan URL pengarah sebagai nilai event, itu harus berupa <Anchor target="_blank" href="https://www.w3schools.com/tags/ref_urlencode.ASP">URL yang disandikan</Anchor> .
* Meta ads memiliki beberapa batasan mengenai nama peristiwa dan parameter. Baca tentang batasan <Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/faq#limits">di sini</Anchor>.

</Accordion>

## Pertanyaan Umum

Bagian berikut mencakup berbagai Pertanyaan yang Sering Diajukan (FAQ) tentang in-app event.

<div id="how-do-i-use-the-revenue-parameter" />

<Accordion title="Bagaimana cara menggunakan parameter pendapatan?">

Anda dapat mengirim nilai pendapatan dengan nama parameter dan event apa pun. Namun, untuk mendaftarkan pendapatan (termasuk [pendapatan negatif](/docs/in-app-events-overview#revenue-events)) di data lengkap dan gabungan AppsFlyer, Anda HARUS menggunakan parameter ***af\_revenue***. Selalu gunakan parameter tersebut bersama in-app event yang mewakili penghasil pendapatan sebenarnya dalam logika bisnis Anda.

**af\_currency** mewakili mata uang yang dinyatakan dalam **af\_revenue** (atau **af\_price** ). Jika **af\_currency** tidak ada di parameter event, AppsFlyer mengirimkannya dengan nilai default "USD".

Untuk informasi selengkapnya tentang parameter ***af\_revenue*** , lihat [panduan Atribusi Pendapatan](/docs/in-app-events-overview#revenue-events) .

</Accordion>

<div id="how-does-appsflyer-attribute-events" />

<Accordion title="Bagaimana cara AppsFlyer mengatribusikan event?">

In-app event diatribusikan ke sumber media asli penginstalan aplikasi.

Saat menginstal aplikasi (peluncuran aplikasi pertama) AppsFlyer menggunakan berbagai <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#metode-atribusi">metode atribusi</Anchor> untuk menentukan atribusi penginstalan. Pada saat yang sama, AppsFlyer SDK membuat <Anchor target="_blank" href="/marketers/id/docs/about-device-identifiers#appsflyer-id">ID AppsFlyerunik</Anchor> yang baru, yang dikaitkan dengan rincian atribusi.

Setiap in-app event yang dilakukan oleh perangkat yang sama dalam aplikasi memiliki ID ini. Hal ini memungkinkan AppsFlyer untuk mengatribusikan event tersebut ke sumber media asli. Pengiklan dapat menggunakan ini untuk mengikuti perjalanan pengguna lengkap di aplikasi mereka.

Event pengguna yang baru-baru ini ditargetkan ulang dapat memiliki <Anchor target="_blank" href="/marketers/id/docs/resolve-retargeting-double-attribution">atribusi ganda</Anchor>.

AppsFlyer mengatribusikan event penginstalan yang diatribusikan sebagai **organik** jika:

* Sudah lebih dari 24 bulan sejak tanggal penginstalan
* Persyaratan sumber media [menginstruksikan penghapusan data tingkat pengguna](/docs/in-app-events-overview#how-long-does-appsflyer-retain-userlevel-data-and-what-are-the-deletion-obligations)
* Pengguna menghapus data aplikasi yang tersimpan di perangkat, memaksa pembuatan ID AppsFlyer yang baru.

</Accordion>

<div id="are-events-recorded-if-a-device-is-offline" />

<Accordion title="Apakah event direkam jika perangkat sedang offline?">

Jika pengguna menginisiasi event (aktivitas) saat koneksi internet tidak tersedia, AppsFlyer tetap dapat merekamnya. Ini cara kerjanya:

1. SDK mengirimkan event ke server AppsFlyer dan menunggu respons yang berhasil.
2. Jika SDK tidak menerima respons yang berhasil, event tersebut disimpan dalam cache.
3. Setelah respons berhasil berikutnya diterima, event yang disimpan dikirim ke server lagi.
4. Jika ada beberapa event dalam cache, mereka akan dikirim ke server, satu demi satu.

> 📘 **Catatan**
>
> Cache SDK dapat menyimpan hingga 40 event, yang berarti bahwa hanya 40 event pertama yang dilakukan secara offline yang disimpan. Yang berikutnya, hingga respons sukses berikutnya, akan dihapus.
>
> Waktu event yang muncul dalam data lengkap adalah waktu event dikirim ke AppsFlyer setelah perangkat online kembali. Ini bukanlah waktu aktual berlangsungnya event.

</Accordion>

<div id="what-are-complex-inapp-events-and-how-do-i-set-them-up" />

<Accordion title="Apa yang dimaksud dengan in-app event yang kompleks dan bagaimana cara mengaturnya?">

Event In-App Kompleks memungkinkan pengiriman beberapa event dalam satu panggilan API.

Ini berguna saat Anda ingin melihat beberapa tindakan pengguna yang terkait erat dikelompokkan bersama (misalnya, menambahkan beberapa produk ke keranjang dalam satu sesi).  
Contoh:

```json
{
  "af_revenue":"50.87",
  "af_currency":"USD",
  "af_receipt_id":"57601333",
  "product":[ 
   { 
	 "af_content_id":"1164_8186",
	 "af_price":"8.97",
	 "af_quantity":"1"
   },
   { 
	 "af_content_id":"1164_8186",
	 "af_price":"8.97",
	 "af_quantity":"1"
   },
   { 
	 "af_content_id":"1164_8186",
	 "af_price":"8.97",
	 "af_quantity":"1"
   },
   { 
	 "af_content_id":"1177_8185",
	 "af_price":"8.97",
	 "af_quantity":"1"
   },
   { 
	 "af_content_id":"0153_9077",
	 "af_price":"14.99",
	 "af_quantity":"1"
   }
  ]
}
```

> ❗️ **Perhatian**
>
> Peristiwa dalam aplikasi yang kompleks menyebabkan masalah postback dengan Meta ads dan Criteo. Jika Anda memerlukan event untuk dipetakan sepenuhnya dengan Meta ads dan Criteo, kirim masing-masing event per tindakan pengguna (misalnya, kirim event Add to cart (Tambahkan ke keranjang) per setiap item yang ditambahkan). Gunakan data lengkap in-app event untuk mengelompokkan event ini bersama-sama.

</Accordion>

<div id="can-i-add-multiple-items-to-a-single-transaction" />

<Accordion title="Bisakah saya menambahkan beberapa item ke satu transaksi?">

Anda dapat menambahkan beberapa item dalam satu transaksi. Alih-alih satu nilai per parameter event, Anda dapat memiliki array item yang menjelaskan transaksi, dipisahkan dengan koma. Formatnya harus berupa string JSON.

> 📄 **Contoh**
>
> Pada transaksi yang sama, Mr A. Flyer membeli dua baju yang sama, sepasang sepatu, dan sebuah topi dari toko online yang berbasis di AS. Urutan di mana setiap item terdaftar harus identik untuk setiap parameter.
>
> ```json
> "{\"af_content_id\": [\"123\",\"988\",\"399\"], \"af_quantity\": [\"2\",\"1\",\"1\"], \"af_price\": [\"25\",\"50\",\"10\"], \"af_revenue\": \"110\", \"af_currency\": \"USD\"}"
> ```
>
> Beberapa item dikirim berikutnya sebagai larik di <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration">postback</Anchor> . Saat ini, Meta ads dan Twitter tidak dapat mengurai parameter array dengan tepat. Untuk membantu masalah ini, AppsFlyer menjumlahkan jumlah item (af\_quantity) alih-alih mengirimkannya ke SRN ini sebagai larik. Di contoh kita, Meta ads akan mendapatkan **af\_quantity=4**.
>
> **<span id="h_01HDBZW9XFJ68WSM3066NVRATS"></span>Catatan**
>
> Penggunaan item berganda dapat dilakukan dengan event in-app berikut:
>
> af\_add\_to\_cart, af\_add\_to\_wishlist, af\_tutorial\_completion, af\_initiated\_checkout, af\_purchase, af\_rate, af\_spent\_credits, af\_content\_view, af\_travel\_booking, af\_update



</Accordion>

<div id="how-does-appsflyer-handle-event-deduplication" />

<Accordion title="Bagaimana AppsFlyer menangani deduplikasi event?">

Kami memiliki mekanisme deduplikasi in-app event. Ini memeriksa semua in-app event untuk melihat apakah ada in-app event yang identik yang berasal dari appsflyer\_id yang sama kurang dari 10 detik sebelumnya. Jika event tersebut ditemukan, mekanisme menghapus duplikat tersebut.

Dua event dianggap identik jika kolom berikut di kedua event itu sama:

* eventName
* nilai event
* ID Aplikasi
* AppsFlyer ID

> 📘 **Catatan**
>
> Deduplikasi hanya berfungsi untuk in-app event yang dikirim dari SDK.
>
> In-app event S2S tidak diduplikasi.

</Accordion>

<div id="how-long-does-appsflyer-retain-userlevel-data-and-what-are-the-deletion-obligations" />

<Accordion title="Berapa lama AppsFlyer menyimpan data tingkat pengguna dan apa kewajiban penghapusannya?">

AppsFlyer mempertahankan data tingkat pengguna (data lengkap) selama 24 bulan kecuali jika diatur, diwajibkan, atau diizinkan oleh undang-undang. Beberapa SRN/mitra memerlukan penyedia atribusi, termasuk AppsFlyer, untuk menghapus data tingkat pengguna terkait SRN/mitra sebelum berakhirnya periode 24 bulan.

Setelah dihapus, event yang terkait dengan pengguna yang dihapus ditampilkan sebagai organik. Data agregat sebelumnya tidak diubah. Untuk informasi lebih lanjut, lihat <Anchor target="_blank" href="/marketers/id/docs/user-level-data-retention#data-retention-and-deletion-obligations">Kewajiban penyimpanan dan penghapusan data</Anchor>.

</Accordion>

<div id="do-i-need-to-add-the-os-operating-system-parameter-to-my-events" />

<Accordion title="Apakah saya perlu menambahkan parameter OS (sistem operasi) ke event saya?">

* SDK Android dan SDK iOS secara otomatis menambahkan parameter OS (sistem operasi).
* Untuk <Anchor target="_blank" href="/marketers/id/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S API</Anchor>, mulai 1 Juli 2021, Anda harus mengirimkan parameter OS (sistem operasi) untuk aplikasi iOS. Jika Anda tidak mengirim parameter ini, data dianggap berasal dari pengguna iOS 14.5, dan ini memengaruhi cara <Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework">penyediaan data lengkap</Anchor>.

</Accordion>

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration">Konfigurasi postback in-app event</Anchor>

<div data-zendesk-anchors="why-record-inapp-events=mengapa-merekam-in-app-event h_01HDBZW9XEBTY13MG4AN93RNCD=mengapa-merekam-in-app-event about-inapp-events=tentang-in-app-events h_01HDBZW9XEBDSDA9T5X5B6KGTG=tentang-in-app-events h_01HDBZW9XE3Z40JE9576C4XSF4=tips h_01HDBZW9XEMV1EFY7CEE7N1GZV=predefined-and-custom-events h_01HDBZW9XEZWDDHFATKY6KDN25=revenue-events revenue-currency=mata-uang-pendapatan h_01HDBZW9XEMPVG76PJQN7WDAT6=mata-uang-pendapatan currency-conversion=konversi-mata-uang h_01HDBZW9XEMGA5RAW0DBBPV3FQ=konversi-mata-uang h_01HDBZW9XERK3VN1GS8GHM911W=contoh currency-display=tampilan-mata-uang h_01HDBZW9XE85YC3JHG58YYAB8F=tampilan-mata-uang h_01HDBZW9XEQNG1RDH7A8H002ZD=contoh-1 revenue-data-in-the-dashboard=data-pendapatan-di-dasbor h_01HDBZW9XEVWB9045N0YEVWE6Z=data-pendapatan-di-dasbor revenue-data-in-raw-data-reports=data-pendapatan-dalam-laporan-data-lengkap h_01HDBZW9XEGYFD3W9FT1N3ZGQW=data-pendapatan-dalam-laporan-data-lengkap sending-events=mengirim-event h_01HDBZW9XFESG6MP9QF1XCJKE6=mengirim-event setting-up-inapp-events=mengatur-in-app-event h_01HDBZW9XF13AGRCN2HJ18RHS2=mengatur-in-app-event h_01HDBZW9XF6X9H4WCFWC28W1CD=defining-an-inapp-event h_01HDBZW9XFN2B8AC18VW99G8Z6=contoh-2 h_01HDBZW9XFM33BYF90EJPQ35V9=recommended-events-by-business-vertical h_01HDBZW9XF6G2R6Y6S5GFNDM6W=view-inapp-event-data tips=zd-tips h_01HDBZW9XF1Q1NB1YS8Q0HKA6K=zd-tips h_01HDBZW9XFFNWCJ18NETEM2287=limitations faq=pertanyaan-umum h_01HDBZW9XF5H24H2HCJKKHCRTE=pertanyaan-umum h_01HDBZW9XF5ZNGVEMND08137PR=how-do-i-use-the-revenue-parameter h_01HDBZW9XFZ144ND2FXW2AMGRW=how-does-appsflyer-attribute-events h_01HDBZW9XFDBFY580P939ZP0D4=are-events-recorded-if-a-device-is-offline h_01HDBZW9XFCDMKNWJ75AWHC2Y0=catatan h_01HDBZW9XF8Q57JZPD8J2Y25SB=what-are-complex-inapp-events-and-how-do-i-set-them-up h_01HDBZW9XF33FHR418MNVH6BS2=perhatian h_01HDBZW9XFRAFSXJE5N5ZPRW2R=can-i-add-multiple-items-to-a-single-transaction h_01HDBZW9XFB9TAT8W4CGNP1892=contoh-3 h_01HDBZW9XFGMG5B5FG2785ERAM=how-does-appsflyer-handle-event-deduplication h_01HDBZW9XFWKN7W90PSVMX73FS=catatan-1 h_01HDBZW9XFFXXBYY14A3QGENSF=how-long-does-appsflyer-retain-userlevel-data-and-what-are-the-deletion-obligations h_01HDBZW9XFH80JK748PAPG09B5=do-i-need-to-add-the-os-operating-system-parameter-to-my-events h_01HDNZ708FN0N286R5HDQGMNGZ=lihat-juga" />
