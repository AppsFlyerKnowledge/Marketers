---
title: Jaringan pelaporan mandiri (SRN)
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Agencies
    - Ad Networks
    - srn
    - Self-reporting
    - networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2018-10-22T05:21:45Z'
  edited_at: '2023-11-20T06:55:02Z'
  id: 360001546905
  locale: id
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/id/articles/360001546905
---
> **Sekilas:** Pelajari tentang jaringan pelaporan mandiri (SRN)—atribusi, tautan dalam, implikasi iOS, dan FAQ.

## SRN diintegrasikan dengan AppsFlyer

| **SRN** | **Logo** |
| --- | --- |
| <Anchor target="_blank" href="/marketers/id/docs/apple-ads-integration-setup">Apple Search Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/iossearchads.png" width="131px" /> |
| <Anchor target="_blank" href="/marketers/id/docs/google-ads-adwords-integration-setup-for-advertisers">Google Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/googleadwords.png?v=1" width="47px" /> |
| Platform GoogleMarketing | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png?v=1" width="45px" /> |
| <Anchor target="_blank" href="/marketers/id/docs/meta-ads-integration-setup">Iklan Meta</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/facebook.png?v=1" width="67px" /> |
| <Anchor target="_blank" href="/marketers/id/docs/snapchat-advanced-srn-integration-setup">Snapchat</Anchor> | <Image alt="snapchat_logo.png" src="https://files.readme.io/c9b62d55d5c1497011d7411a21dca6f1668308bbe2806ab238b71742c421b182-32259457816209.png" width="41px" /> |
| Tencent Social Ads | <Image alt="blobid0.jpg" src="https://files.readme.io/6d6e9661c9d81f80ffeedfdf4850a84f3cc183faa49a514d1d3bb116641738da-32259428896017.jpg" width="80px" /> |
| <Anchor target="_blank" href="/marketers/id/docs/tiktok-for-business-advanced-srn-integration-setup">TikTok for Business—SRN Lanjutan</Anchor> | <Image alt="tiktok_logo.png" src="https://files.readme.io/307a95d0d848bd9e692b9a1996dffc11449a25cac1c7deeb7573b566506aeb73-15166720478993.png" width="106px" /> |
| <Anchor target="_blank" href="/marketers/id/docs/x-ads-formerly-twitter-ads-setup-guide-overview">Twitter</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/twitter.png?v=1" width="40px" /> |
| <Anchor target="_blank" href="/marketers/id/docs/yahoo-integration-setup">Yahoo (Oath: Platform Iklan / Yahoo Gemini)</Anchor> | <Image alt="verizonmedia.png" src="https://files.readme.io/36291ff556d07a5dbf2ae8ff693ea33d21dae9e0518a94b251202634a24049cf-32259428916369.png" width="76px" /> |
| <Anchor target="_blank" href="/marketers/id/docs/yahoo-japan-search-ads-campaign-configuration">Yahoo! Search Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yahoojapansearch.png" width="139px" /> |

**Catatan:** SRN memiliki <Anchor target="_blank" href="/marketers/id/docs/user-level-data-retention">batasan penggunaan dan retensi data tingkat pengguna.</Anchor>

## Atribusi

Tidak seperti non-SRN (jaringan iklan), yang menggunakan tautan atribusi untuk melaporkan event ke AppsFlyer, SRN mengatribusikan sendiri menggunakan ID perangkat saat diberi tahu tentang penginstalan oleh AppsFlyer.

Atribusi AppsFlyer untuk SRN dan non-SRN didasarkan pada:

* Metodologi sentuhan terakhir dan multisentuh.
* Logika atribusi standar AppsFlyer untuk mengurutkan data impresi dan klik yang relevan.

### Bagaimana cara kerja atribusi dengan SRN?

SRN melaporkan kejadian, seperti penginstalan baru dan kejadian dalam aplikasi, ke AppsFlyer dengan cara berikut:

* Menggunakan API untuk berkomunikasi dengan penyedia atribusi dan pengukuran.
* Saat penyedia atribusi pihak ketiga mendeteksi penginstalan, mereka melakukan kueri jaringan menggunakan ID iklan.
* Melaporkan detail klik atau impresi iklan yang relevan.

Setelah AppsFlyer melakukan atribusi, postback dalam aplikasi dikirim ke SRN selama durasi <Anchor target="_blank" href="/marketers/id/docs/user-level-data-retention#partner-data-retention-periods">periode retensi data mitra</Anchor>.

### Bagaimana cara kerja pengaitan dengan SRN tingkat lanjut?

SRN tingkat lanjut beratribusi dengan cara yang sama seperti SRN. Namun, SRN tingkat lanjut juga dapat mengatribusikan interaksi ketika tidak ada ID perangkat (IDFA)—menggunakan kerangka kerja <Anchor target="_blank" href="/marketers/id/docs/appsflyer-knowledge-base-glossary#privasi-gabungan-lanjutan">Privasi Lanjutan Teragregasi</Anchor> dan menggunakan <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#device-id-matching">pencocokan ID</Anchor> dan <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#probabilistic-modeling">pemodelan probabilistik</Anchor> melalui tautan atribusi.

### Instal atribusi

Calon pengguna aplikasi melihat dan berinteraksi dengan beberapa iklan sebelum mereka menginstal aplikasi. Secara umum, penyedia atribusi menawarkan atribusi sentuhan terakhir kepada pemasang iklan—ini mengatribusikan penginstalan ke klik terakhir yang dilakukan sebelum penginstalan sebenarnya.

Saat aplikasi pertama kali diluncurkan:

* AppsFlyer memeriksa bahwa:
  * Aplikasi diatur untuk menerima lalu lintas dari SRN.
  * Pengguna memiliki ID iklan.
* Jika kedua kondisi tersebut benar, AppsFlyer melakukan kueri SRN menggunakan ID iklan.
* AppsFlyer melakukan atribusi setelah mempertimbangkan klaim SRN.

#### Instal contoh atribusi

<div id="example-a-assisted-attribution" />

<Accordion title="Contoh A: Atribusi terbantu">

![SRN_1.png](https://files.readme.io/8e244c99f54b36a4e88b03bf05bb7ca0da2db5c7c601882ea9f68c191c38981b-32259428920337.png)

**Senin:** Jaringan A melaporkan klik pengguna.

**Selasa:** Jaringan B melaporkan interaksi video.

**Rabu:** Jaringan C melaporkan klik pada iklan yang dapat diputar dan, 30 menit kemudian, ada penginstalan.

**AppsFlyer** mengatribusikan penginstalan ke Jaringan C dan memberikan kredit kepada Jaringan A dan B karena telah membantu penginstalan.

AppsFlyer memberikan data bantuan kepada pemasang iklan (interaksi tanpa atribut yang terjadi sebelum penginstalan). Hal ini memungkinkan pemasang iklan menyesuaikan model atribusi multisentuh atau fraksional mereka. Lihat <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model">penjelasan singkat</Anchor> ini.

</Accordion>

<div id="example-b-last-click-attribution" />

<Accordion title="Contoh B: Atribusi klik terakhir">

![SRN_2.png](https://files.readme.io/6817d8235acfdbbb5324d07ea8a31ace21cf2306e8e099129d9802e3e0d58b0c-32259457863825.png)

**Jaringan D** (SRN) melaporkan klik beberapa menit sebelum Jaringan C.

**Jaringan C** menggunakan integrasi atribusi standar.

**AppsFlyer** mengaitkan penginstalan ke Jaringan C karena mereka memiliki klik terakhir.

</Accordion>

### Jendela atribusi

Jendela atribusi mencakup lookback dan lihat-tayang. Beberapa SRN menagih pemasang iklan untuk penginstalan berdasarkan Biaya per Impresi (CPM) dan Biaya per Tindakan (CPA)—ini didasarkan pada klik atau impresi yang terjadi dalam periode 1-28 hari.

**AppsFlyer** mengaitkan penginstalan, aktivitas, Biaya per Penginstalan Efektif (eCPI), dan Biaya per Tindakan Efektif (eCPA) berdasarkan metodologi atribusi pilihan pemasang iklan dan jendela lookback.

**Pemasang Iklan** mungkin harus membayar penginstalan berdasarkan jendela lookback atribusi SRN dan model lihat-tayang.

* Pemasang iklan mengharapkan metodologi atribusi universal pihak ketiga AppsFlyer untuk mengoptimalkan dan mengalokasikan pengeluaran iklan mereka.
* Mengapa? Karena AppsFlyer melaporkan eCPI dan eCPA aktual berdasarkan persyaratan yang ditetapkan pemasang iklan.
* SRN mungkin mendapat manfaat dalam jangka pendek karena mereka sering menentukan ketentuan pembayarannya sendiri. Namun, pemasang iklan memperbaikinya dengan menggunakan penyedia atribusi pihak ketiga.

## Deep Linking dengan SRN

Agar pengguna membuka aplikasi Anda saat tautan diklik, Anda hanya perlu menyiapkan skema Tautan Aplikasi/Tautan Universal/URI. Namun, untuk melakukan deep linking atau deferred deep linking ke halaman atau aktivitas tertentu di aplikasi Anda, SRN menggunakan metodenya sendiri—tanpa melibatkan metode deep linking AppsFlyer.

Jadi, bagaimana Anda dapat menautkan langsung user Anda dan mendapatkan data yang relevan dari SRN?

<div id="direct-deep-linking" />

<Accordion title="Deep linking langsung">

Saat perangkat pengguna melakukan deep linking, deep linking langsung dengan SRN dilakukan tanpa memanggil metode deep linking AppsFlyer. Pada contoh di bawah ini, pengguna lama yang mengeklik iklan dialihkan ke aktivitas secara langsung menggunakan metode Facebook, sementara pengguna baru mendapatkan pengalaman yang sama menggunakan data konversi AppsFlyer. Pelajari cara <Anchor target="_blank" href="/marketers/id/docs/meta-ads-faq#who-needs-facebooks-sdk">iklan Meta menggunakan OneLink untuk deep linking</Anchor>

> 📄 **Contoh**
>
> Jill, pemasar seluler "greatapp", memutuskan untuk menjalankan kampanye deep linking di Meta ads, yang ditargetkan untuk khalayak umum. Kampanye mengalihkan setiap pengguna yang mengeklik ke aktivitas "bonus".
> Jack, developer seluler, menambahkan logika ini setelah mendapatkan data konversi:
>
> 1. Apakah ini berasal dari Facebook ("is\_fb=true")?
> 2. Jika benar, dapatkan nilai parameter grup iklan.
> 3. Jika nilainya berisi kata "bonus", arahkan pengguna ke aktivitas "bonus".

</Accordion>

<div id="deferred-deep-linking" />

<Accordion title="Deferred deep linking (tautan langsung tertunda) :">

Berbeda dengan deep linking, deferred deep linking dengan SRN dimungkinkan menggunakan AppsFlyer GCD API.   
AppsFlyer menerima data konversi dan membuatnya tersedia untuk aplikasi pada peluncuran pertama.  
Pengguna baru yang menginstal setelah mengeklik kampanye deep linking/penargetan ulang di SRN dapat dialihkan di dalam aplikasi saat diluncurkan, dengan menggunakan data konversi.

Namun, dengan SRN, parameter deep linking AppsFlyer biasa tidak ada sebagai bagian dari data deep link. Untuk menggunakan data ini dalam aplikasi, pengembang perlu menggunakan logika lebih lanjut berdasarkan parameter yang tersedia, seperti kampanye, ad set, atau nama iklan tunggal.

**Catatan**: Untuk <Anchor target="_blank" href="/marketers/id/docs/meta-ads-faq#who-needs-facebooks-sdk">iklan Meta</Anchor>, penautanlangsung tertundamelalui GCD tersedia untuk aplikasi Android menggunakan mekanisme Perujuk Pemasangan Google. Ini tidak tersedia untuk aplikasi iOS.

</Accordion>

## implikasi iOS

Sebagian besar SRN mendukung SKAdNetwork dan memiliki integrasi yang diperlukan dengan AppsFlyer.

<div id="ios-145-srn-attribution" />

<Accordion title="Atribusi SRN iOS 14.5">

Mulai iOS 14.5, saat pengguna memberikan persetujuan ATT di aplikasi pengiklan dan penerbit (<Anchor target="_blank" href="/marketers/id/docs/appsflyer-knowledge-base-glossary#persetujuan-ganda">persetujuan ganda</Anchor>), penginstalan SRN, yang dicatat di <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">dasbor SKAdNetwork</Anchor>, juga ditampilkan di  dasbor tradisional.

> 📘 **Catatan**
>
> * Dasbor tradisional menunjukkan pengurangan pemasangan yang dikaitkan dengan SRN. Saat mempertimbangkan kinerja SRN, gunakan <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">dasbor SKAdNetwork</Anchor>. Secara keseluruhan diharapkan terjadi penurunan atribusi SRN dari penginstalan, dengan peningkatan yang sesuai dalam penginstalan organik. Namun, untuk SRN tingkat lanjut, dampaknya lebih rendah karena SRN juga mengatribusikan keterlibatan saat tidak ada ID perangkat.
> * <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">Dasbor SKAdNetwork</Anchor> diperbarui dengan jeda 48-72 jam setelah penginstalan.
> * Penginstalan yang dibawa oleh Apple Search Ads (ASA) tidak diatribusikan di dashboard SKAdNetwork.

</Accordion>

<div id="sending-event-postbacks-to-srns" />

<Accordion title="Mengirim postback acara ke SRN">

SRN yang menerima postback event bergantung pada penyertaan ID perangkat di postback. Hal ini memungkinkan SRN untuk mengatribusikan sendiri tindakan pengguna yang dilaporkan. Banyak pengguna iOS 14 tidak menyetujui, artinya mereka tidak mengizinkan akses ke ID perangkat (IDFA) mereka. Dalam hal ini, Anda harus mengharapkan:

* Penurunan jumlah postback peristiwa yang dikirim ke SRN
* Perbedaan jumlah postback event antara SRN dan AppsFlyer—yang mencatat semua event.

> 📘 **Catatan**
>
> * Jika tidak ada IDFA, postback untuk penginstalan, pembukaan aplikasi, atau in-app event tidak dikirim ke SRN ([kecuali untuk skenario ini di Google ads](/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid)). Namun, beberapa SRN tingkat lanjut mendapatkan postback gabungan juga saat tidak ada IDFA.
> * Jaringan iklan klik tidak terpengaruh, karena mereka menggunakan ID transaksinya sendiri, dan bukan ID perangkat, untuk mengatribusikan sendiri informasi postback event.

</Accordion>

## Pertanyaan Umum

<div id="how-does-retargeting-work-with-srns" />

<Accordion title="Bagaimana cara kerja penargetan ulang dengan SRN?">

Klik penargetan ulang dari non-SRN mudah diidentifikasi dengan adanya parameter `is_retargeting=true` di tautan atribusi penargetan ulang.  
Dengan SRN, tidak ada indikasi serupa. Alih-alih, untuk mengaktifkan atribusi interaksi ulang dari SRN, AppsFlyer menggunakan logika lain:

* Prasyarat:
  * Di halaman **Pengaturan Aplikasi** , nyalakan **Aktifkan penargetan ulang.**
  * Di halaman **Integrasi Aktif** , pilih SRN, dan aktifkan **Penargetan Ulang**.
* Dengan setiap peluncuran aplikasi, AppsFlyer menanyakan SRN tentang interaksi ID perangkat baru-baru ini dengan iklan kampanye untuk aplikasi tersebut.
  * Jika SRN membalas dengan detail keterlibatan, AppsFlyer memvalidasi keterlibatan dalam jendela lookback dan melebihi waktu minimal antara keterlibatan kembali.
  * Interaksi yang divalidasi dicatat sebagai interaksi ulang dan diatribusikan ke SRN.

</Accordion>

<div id="what-is-srn-mistargeting" />

<Accordion title="Apa itu salah penargetan SRN?">

Kampanye SRN harus menargetkan audiens tertentu, tetapi ini tidak selalu terjadi: Non-pengguna dalam kampanye akuisisi pengguna dan pengguna yang ada dalam kampanye penargetan ulang.

Jika satu SRN digunakan untuk menjalankan kampanye akuisisi pengguna dan penargetan ulang, hal ini dapat menyebabkan kesalahan penargetan pengguna. Akibatnya, Anda membayar lalu lintas yang tidak diinginkan.

**Skenario:** SRN di platform AppsFlyer diaktifkan untuk kampanye akuisisi pengguna.

* Setelah setiap peluncuran aplikasi, AppsFlyer menanyakan SRN untuk memeriksa apakah ID iklan (pengguna) memiliki interaksi baru-baru ini.
* Jika ya,
  * SRN membalas dengan nama kampanye.
  * AppsFlyer menentukan apakah ini peluncuran pertama (atau bukan) dan mengatribusikan yang sesuai:  
    **Peluncuran pertama**: Penginstalan baru diatribusikan ke kampanye.  
     **Peluncuran kedua atau lebih baru**: Event penargetan ulang diatribusikan ke kampanye.

**Kesimpulan:** Mendapatkan event penargetan ulang dari kampanye akuisisi pengguna adalah pemborosan.

#### Apakah salah sasaran merupakan masalah?

Analis data AppsFlyer memeriksa kampanye **akuisisi pengguna** Meta ads selama bulan tertentu.

* Penargetan ulang diaktifkan.
* Dalam 30% kampanye, setidaknya 15% dari pengguna yang ditargetkan adalah pengguna aplikasi yang sudah ada.
* Dalam 5% kampanye, setidaknya 40% adalah pengguna aplikasi yang sudah ada.
* **Kesimpulan: Dalam kampanye akuisisi pengguna SRN, 1 dari 10 pengguna yang ditargetkan sudah menjadi pengguna yang sudah ada.**

[![mistargeted_users.png](https://files.readme.io/e135e9fc9ccda47a5d06c9595f171a60f9892f4c63212b4e459eeec897b16a3b-32259428927505.png)](https://files.readme.io/e135e9fc9ccda47a5d06c9595f171a60f9892f4c63212b4e459eeec897b16a3b-32259428927505.png)

#### Memecahkan masalah salah sasaran

**Solusi dasar:** Jangan sertakan pengguna aplikasi yang sudah ada dalam kampanye akuisisi pengguna.

* SRN hanya akan menargetkan pengguna baru yang potensial.
* **Memaksimalkan hasil akuisisi pengguna baru dengan anggaran yang sama**.
* Perbarui kampanye secara berkala (dan manual), misalnya, sebulan sekali.
* Namun, kesenjangan waktu berarti bahwa pengguna yang sudah ada dapat ditargetkan dalam kampanye akuisisi pengguna selama bulan pertama setelah mereka menginstal aplikasi.

**<Anchor target="_blank" href="/marketers/id/docs/audiences-guide">Audiens</Anchor>**, fitur premium AppsFlyer, memungkinkan Anda secara otomatis mengirim, setiap hari, segmen mana pun dari basis pengguna Anda ke banyak jaringan iklan.

Riset AppsFlyer menunjukkan bahwa mengatasi kesalahan penargetan dapat berdampak dramatis pada upaya pemasaran dan akuisisi pengguna Anda.

</Accordion>

<div id="why-is-the-original-url-field-empty-in-raw-data-reports" />

<Accordion title="Mengapa bidang URL Asli kosong di laporan data mentah?">

Klik dilakukan di lingkungan SRN tetapi tanpa tautan atribusi AppsFlyer. Oleh karena itu, data URL Asli terkait klik tidak tersedia untuk AppsFlyer.

</Accordion>

<div id="dashboard-doesnt-show-srn-clicks-and-impressions" />

<Accordion title="Dashboard tidak menampilkan klik dan impresi SRN">

Klik dilakukan di lingkungan SRN tetapi tanpa tautan atribusi AppsFlyer. Oleh karena itu, beberapa SRN tidak memberikan data klik dan impresi ke AppsFlyer.

<Anchor target="_blank" href="/marketers/id/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Meta ads</Anchor> dan <Anchor target="_blank" href="/marketers/id/docs/google-ads-adwords-cost-and-ad-revenue">Google</Anchor> memberikan beberapa data gabungan ke AppsFlyer.

</Accordion>

<div id="can-agencies-configure-srn-campaigns" />

<Accordion title="Bisakah agensi mengonfigurasi kampanye SRN?">

Ya, <Anchor target="_blank" href="/partners/id/docs/about-agency-accounts#jaringan-iklan-pelaporan-mandiri">lihat di sini tentang konfigurasi SRN oleh Agensi</Anchor>.

</Accordion>

<div id="does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid" />

<Accordion title="Apakah AppsFlyer mengirimkan postback untuk ID iklan yang hilang (IDFA/GAID)?">

Ketika ID iklan berisi string kosong (“”) atau menampilkan nilai '00000000-0000-0000-0000-000000000000' (IDFA nol), AppsFlyer tidak mengirimkan postback untuk penginstalan, pembukaan aplikasi, atau peristiwa dalam aplikasi, kecuali untuk skenario berikut:

* Sebagai bagian dari integrasi untuk pengukuran pemasaran ulang dengan Google Ads, saat pengguna iOS yang tidak memberikan izin membuka aplikasi atau melakukan peristiwa dalam aplikasi, AppsFlyer mengirimkan `gbraid` dan info event ke Google Ads (untuk event `additional_data_json` ).
* Di Android, jika tidak ada ID perangkat tetapi nilai perujuk berisi `gclid` (untuk penginstalan) atau event interaksi ulang berisi tautan langsung dengan `parameter gclid` , AppsFlyer mengirimkan`info event gclid` ke Google Ads.

**Google Ads** `gbraid` **parameter:** Pengidentifikasi gabungan yang dibuat oleh Google yang mengidentifikasi sekelompok perangkat dan direferensikan oleh tautan langsung.

**ID Klik Google (parameter`gclid` ):** Parameter yang diteruskan di URL dengan klik iklan, yang mengidentifikasi kampanye dan atribut klik lainnya yang terkait dengan iklan. Ini digunakan untuk pelacakan iklan dan atribusi kampanye.

</Accordion>

<div data-zendesk-anchors="srns-integrated-with-appsflyer=srn-diintegrasikan-dengan-appsflyer h_01HFM2MET40AFB84AW5N8GKWF3=srn-diintegrasikan-dengan-appsflyer attribution=atribusi h_01HFM2MET4ZNKEZBT3S74N8CMC=atribusi how-does-attribution-work-with-srns=bagaimana-cara-kerja-atribusi-dengan-srn h_01HFM2MET42R6C87XB5RWX9ABJ=bagaimana-cara-kerja-atribusi-dengan-srn how-does-attribution-work-with-advanced%E2%80%94srns=bagaimana-cara-kerja-pengaitan-dengan-srn-tingkat-lanjut h_01HFM2MET4Q6WCSANH18VTGBQX=bagaimana-cara-kerja-pengaitan-dengan-srn-tingkat-lanjut install-attribution=instal-atribusi h_01HFM2MET4YQGN3GZKTTBRQ4HK=instal-atribusi install-attribution-examples=instal-contoh-atribusi h_01HFM2MET40Y9V8YGA20CCGVNN=instal-contoh-atribusi h_01HFM2MET47BP3T07NTRVDWSJ3=example-a-assisted-attribution h_01HFM2MET4FY6SRS534NEA25WV=example-b-last-click-attribution attribution-windows=jendela-atribusi h_01HFM2MET4ZJF290QNE3TPXQMA=jendela-atribusi deep-linking-with-srns=deep-linking-dengan-srn h_01HFM2MET4ZA6WD6HX92JNFW7X=deep-linking-dengan-srn h_01HFM2MET4VZX943736W52V0ZJ=direct-deep-linking h_01HFM2MET4HSVHM0Q1C8D5Z279=contoh h_01HFM2MET4WGVMRJW7NJ7TF8GQ=deferred-deep-linking ios-implications=implikasi-ios h_01HFM2MET4DGERZJ18A7CEFDS9=implikasi-ios h_01HFM2MET4SRX0YRZRMHBY6DKT=ios-145-srn-attribution h_01HFM2MET471M5J2XFE7G2Z6J3=catatan h_01HFM2MET42KNAMWE9S9BSF4PK=sending-event-postbacks-to-srns h_01HFM2MET4WJ6TMTXM03NFFCAG=catatan-1 faq=pertanyaan-umum h_01HFM2MET49FZ8QHDMA7H92BTE=pertanyaan-umum h_01HFM2MET4VYGPWR98HMAWK4YP=how-does-retargeting-work-with-srns h_01HFM2MET4JGYTW6P1VGYMYGFS=what-is-srn-mistargeting is-mistargeting-a-problem=apakah-salah-sasaran-merupakan-masalah h_01HFM2MET4C1HMWH715XP42ZAQ=apakah-salah-sasaran-merupakan-masalah solving-the-mistargeting-problem=memecahkan-masalah-salah-sasaran h_01HFM2MET41CDCP8VNGR39YMCK=memecahkan-masalah-salah-sasaran h_01HFM2MET4DETEHT8PACHS6C6B=why-is-the-original-url-field-empty-in-raw-data-reports h_01HFM2MET48Y4ATGB1HNDGSFEP=dashboard-doesnt-show-srn-clicks-and-impressions h_01HFM2MET4JEA8BBGN564CQPYX=can-agencies-configure-srn-campaigns h_01HFM2MET42V7AVV2BPZGDRARV=does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid" />
