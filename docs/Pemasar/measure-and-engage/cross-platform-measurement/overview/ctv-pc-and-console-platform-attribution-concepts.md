---
title: Konsep atribusi platform CTV, PC, dan konsol
metadata:
  keywords:
    - Attribution
    - Advertisers
    - Developers
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2021-07-15T11:30:45Z'
  edited_at: '2024-03-17T12:02:07Z'
  id: 4404083608849
  locale: id
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/id/articles/4404083608849
---
> **Sekilas:** Pelajari tentang cara kerja atribusi untuk platform CTV, PC, dan konsol agar AppsFlyer dapat menerima atribusi dan data acara untuk kampanye Anda di perangkat lintas platform ini.

<Image alt="7435_CTV_image.png" src="https://files.readme.io/7fc57fd80ad86bb173bcf81581b9fe8b4625ed2a044d302a6d72194560019e81-4410336840977.png" width="471px" />

<div id="the-appsflyer-cross-platform-solution" />

## Solusi lintas platform AppsFlyer

Dalam lanskap digital saat ini, para profesional yang sedang berkembang menghadapi tantangan untuk menjangkau konsumen di berbagai perangkat dan platform. Pendekatan pengukuran tradisional gagal dalam menangkap cakupan penuh perjalanan pengguna yang menjangkau berbagai platform. Pengukuran lintas platform sangat penting untuk memahami dampak aktivitas pemasaran dan membuat keputusan yang tepat.

AppsFlyer menawarkan solusi lintas platform yang luas yang melengkapi alat atribusi seluler konvensional. Ini membantu para profesional pertumbuhan dalam mengukur dan mengaitkan upaya pemasaran secara akurat ketika pengguna berinteraksi di berbagai platform dan perangkat. Solusi ini berfokus pada platform CTV, PC, dan konsol.

Pengiklan dapat mempromosikan aplikasi pada platform yang sama atau berbeda dengan yang ditampilkan iklan. Misalnya, pengiklan dapat menampilkan iklan untuk aplikasi Steam di platform Steam. Atau, mereka dapat menampilkan iklan untuk aplikasi Steam di web desktop, misalnya melalui Google Ads. Apa pun strategi pemasaran mereka, pengiklan berintegrasi dengan AppsFlyer untuk menerima data atribusi dan pengukuran kinerja tentang sumber (non-organik atau organik) dan kampanye yang mendorong penginstalan aplikasi CTV, PC, dan platform konsol serta acara pasca-penginstalan. Pemasar menggunakan wawasan ini untuk menghitung nilai seumur hidup pengguna (LTV) dan mengukur serta mengoptimalkan aktivitas pemasaran. <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model">Pelajari lebih lanjut tentang atribusi AppsFlyer</Anchor>

<div id="supported-platforms" />

### Platform yang didukung

<table><thead><tr><th>platform</th><th colspan="2">Metode integrasi AppsFlyer</th></tr><tr><th> </th><th>S2S</th><th>SDK</th></tr></thead><tbody><tr><td>Android TV</td><td><span>-</span></td><td><span><span>✓</span></span></td></tr><tr><td>tvOS (Apple TV)</td><td><span>-</span></td><td><span><span>✓</span></span></td></tr><tr><td>MacOS</td><td><span><span>-</span></span></td><td><span><span>✓</span></span></td></tr><tr><td>Amazon Fire TV</td><td><span><span>-</span></span></td><td><span><span>✓</span></span></td></tr><tr><td>Chromecast</td><td><span><span>-</span></span></td><td><span><span>✓</span></span></td></tr><tr><td>Roku</td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td></tr><tr><td>Vizio</td><td><span><span>✓</span></span></td><td><span>-</span></td></tr><tr><td>Samsung</td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td></tr><tr><td>LG</td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td></tr><tr><td>PlayStation</td><td><span><span>✓</span></span></td><td><span>-</span></td></tr><tr><td>Vidaa</td><td><span><span>✓</span></span></td><td><span>-</span></td></tr><tr><td>Steam</td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td></tr><tr><td>PC asli</td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td></tr><tr><td>Meta Quest (Oculus)</td><td><span><span>✓</span></span></td><td><span><span><span>✓</span></span></span></td></tr><tr><td>Epic Games</td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td></tr><tr><td>Nintendo Switch</td><td><span><span>✓</span></span></td><td><span>-</span></td></tr><tr><td>Xbox</td><td><span><span>✓</span></span></td><td><span>-</span></td></tr></tbody></table>

<div id="cross-platform-attribution-flows" />

## Aliran atribusi lintas platform

Saat memasarkan aplikasi di platform CTV, PC, dan konsol, ada beberapa alur- mulai dari tampilan iklan (tayangan atau klik) hingga atribusiAppsFlyer - yang berlaku untuk semua platform:

* Tautan atribusi langsung
* Tautan OneLink lintas platform
* SRN (jaringan pelaporan mandiri, juga dikenal sebagai SAN, jaringan pelaporan mandiri)
* Halaman arahan lintas platform

Setiap aplikasi, pengiklan, dan platform dapat memiliki satu atau lebih dari alur ini yang diimplementasikan secara bersamaan. Bagian berikut ini menjelaskan berbagai jenis aliran yang berbeda dan kapan masing-masing digunakan.

<div id="direct-attribution-link" />

<Accordion title="Tautan atribusi langsung">

Tautan atribusi langsung adalah tautan AppsFlyer yang mendukung pengalihan dan atribusi untuk satu aplikasi tujuan pada satu platform pada satu waktu. Mereka biasanya digunakan untuk:

* Platform yang sama untuk iklan platform yang sama. Artinya, platform yang menampilkan iklan dan platform yang mendukung aplikasi tersebut identik. Misalnya, pengiklan dapat menampilkan iklan untuk aplikasi Samsung TV di Samsung TV.
* Iklan platform apa pun ke platform apa pun, dengan tujuan/platform yang telah ditentukan sebelumnya. Misalnya, halaman arahan web desktop menampilkan iklan dengan 1 tombol atau lebih, dengan setiap tombol mengarahkan ke toko/pasar platform tertentu.

Tautan atribusi langsung mendukung pemodelan probabilistik dan pencocokan deterministik (ketika ID disediakan dalam tautan) metode atribusi, di mana satu penginstalan oleh satu pengguna dicocokkan dengan klik atau tayangan iklan. Alur atribusi diilustrasikan dalam diagram berikut ini.

![Aliran atribusi CTV - Aliran tautan atribusi langsung.png](https://files.readme.io/2af32b096faa381843040314c9c183056256d03a7e2e6095e72a59bb7211727f-19374976446225.png)

Karena tautan atribusi langsung ditujukan untuk aplikasi di platform tertentu yang telah ditentukan dan mengarah ke satu tujuan tertentu, tautan ini selalu berisi ID aplikasi dan informasi platform dalam URL.

Contoh tautan atribusi langsung: `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/1234561?&af_media_source=game_media_source&af_campaign=campaign_yellow&af_campaign_id=1234&af_ad=game_ad_name&af_adset=game_adset_name&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F1176160%2FSpace_Wars%2F`

<Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-platform-direct-attribution-links#attribution-link">Pelajari cara menyiapkan tautan atribusi langsung</Anchor>.

</Accordion>

<div id="crossplatform-onelink" />

<Accordion title="Tautan OneLink lintas platform">

Tautan OneLink lintas platform mendukung pengalihan dan atribusi ketika platform iklan dan platform tujuan berbeda. Mereka digunakan ketika berbagai pilihan platform tersedia. Misalnya, dalam aliran CTV-ke-mobile, iklan ditampilkan pada platform/perangkat Roku, tetapi tujuannya bisa berupa aplikasi Android/iOS. Contoh lainnya adalah aliran web-ke-konsol desktop, di mana iklan ditampilkan di web desktop, tetapi game tersedia di PC dan beberapa platform konsol, seperti PlayStation, Xbox, dan Steam.

Tautan OneLink lintas platform hanya mendukung metode atribusi pemodelan probabilistik (berdasarkan alamat IP). Karena alasan ini, beberapa penginstalan oleh beberapa pengguna dapat dikaitkan dengan kesan yang sama. Alur atribusi diilustrasikan dalam diagram berikut ini.

![Alur atribusi CTV - Alur atribusi tautan Onelink lintas platform (1).png](https://files.readme.io/d1d92c740510435582dbfe6e736493a4e5f132d8987fde4c95593ea5e7de1662-19374961369873.png)

Semua tujuan/platform aplikasi yang memungkinkan dikonfigurasikan dalam templat OneLink. Untuk itu, tautan OneLink lintas platform tidak mengandung ID aplikasi tertentu atau informasi platform tertentu dalam URL. Sebagai gantinya, URL menyertakan ID templat tempat semua tujuan/platform aplikasi yang mungkin dikonfigurasi.

Contoh tautan OneLink lintas platform: `https://impressions.onelink.me/ch/AG7A?pid=game_media_source&c=game_landing_page&af_ad=game_ad_name&af_adset=game_adset_name&af_xplatform=true`

<Anchor target="_blank" href="/marketers/id/docs/set-up-cross-platform-links-for-multi-device-campaigns">Pelajari cara menyiapkan tautan OneLink lintas platform</Anchor>

</Accordion>

<div id="srn" />

<Accordion title="SRN">

Dengan tautan atribusi langsung dan tautan OneLink lintas platform, penginstalan atribut AppsFlyer dilakukan melalui data yang terdapat dalam URL. Sebaliknya, jaringan pelaporan mandiri (SRN), kadang-kadang juga dikenal sebagai jaringan pengatribusian mandiri (SAN), mengatribusikan diri sendiri menggunakan ID perangkat saat diberitahu tentang penginstalan oleh AppsFlyer.

Atribusi ke SRN dilakukan melalui pencocokan deterministik. Saat pengiklan mengintegrasikan SRN, atribusi berfungsi seperti yang diilustrasikan dalam diagram berikut ini.

![Aliran atribusi CTV - Aliran atribusi SRN (1).png](https://files.readme.io/ba0d84643aefd6a20e95c8aca9424affea8169c95ccc428ddf3d35bb8787a67c-19374961372945.png)

Saat ini, atribusi SRN hanya berfungsi untuk iklan dari platform yang sama ke platform yang sama. Artinya, ketika titik sentuh (klik atau tayangan) terjadi pada platform yang sama dengan penginstalan. Misalnya, jika penginstalan Roku CTV diperiksa dengan Roku Endemic Media (SRN untuk Roku) dan tayangan ditemukan terjadi pada perangkat Roku. Jika tayangan tersebut terjadi pada platform yang berbeda, seperti seluler, maka tidak akan dipertimbangkan untuk atribusi.

Di masa mendatang, atribusi SRN dapat tersedia untuk iklan platform apa pun ke platform mana pun, sehingga memungkinkan atribusi lintas platform yang lebih komprehensif.

</Accordion>

<div id="landing-page" />

<Accordion title="Halaman arahan lintas platform">

Laman landas lintas platform dirancang untuk mendukung perjalanan pengguna lintas platform dan alur pemasaran yang umum. Mereka paling sering digunakan untuk aplikasi game. Halaman arahan menjalankan Skrip Cerdas AppsFlyer untuk melakukan atribusi web-ke-aplikasi. Ini berarti mereka mengaitkan penginstalan di platform apa pun (seperti CTV, PC, konsol, dan platform seluler) dengan iklan yang ditampilkan di web.

Smart Script di halaman arahan lintas platform menggunakan tautan masuk (tautan di iklan web) untuk melakukan 2 hal yang memastikan sumber media asli dan iklan web diatribusikan dengan pemasangan:

* Buat tautan OneLink lintas platform yang mengirimkan impresi ke AppsFlyer. Hal ini memungkinkan AppsFlyer mencatat impresi yang nantinya dapat digunakan untuk mengaitkan penginstalan pengguna. Tayangan dikirim saat halaman arahan terbuka. Bahkan jika pengguna meninggalkan halaman arahan tanpa mengklik tombol apa pun, dan kemudian mengunduh dan menginstal aplikasi sendiri, kesan tersebut masih dikaitkan.
* Buat tautan atribusi langsung untuk setiap aplikasi/platform. Ketika pengguna mengklik tautan ini, mereka akan diarahkan ke platform/toko aplikasi yang benar. Dan ketika mereka kemudian mengunduh dan menginstal aplikasi, penginstalan tersebut dikaitkan dengan klik.

Laman landas mendukung pemodelan probabilistik dan pencocokan deterministik (ketika ID disediakan dalam tautan) metode atribusi. Dengan pemodelan probabilistik, ada kemungkinan bahwa beberapa penginstalan oleh beberapa pengguna dapat dikaitkan dengan kesan yang sama. Alur atribusi diilustrasikan dalam diagram berikut ini.

![Alur atribusi CTV - Alur atribusi halaman arahan.png](https://files.readme.io/28e4d14d14532332027e5d429ac3f95c8d4d451d94125e399cfb9ad04727b278-19374961376529.png)

Contoh:

1. Anda memiliki aplikasi game yang dapat diunduh dan dimainkan di platform desktop, seluler, Epic, atau Steam.
2. Anda beriklan di web.
3. Seorang pengguna melihat iklan di web, baik dari hasil pencarian berbayar atau promosi media sosial.
4. Pengguna mengklik iklan tersebut dan diarahkan ke halaman arahan, yang memiliki tombol unduhan terpisah untuk setiap platform: desktop, seluler, Epic, dan Steam.
5. Halaman arahan menjalankan Skrip Cerdas AppsFlyer itu:
6. Menangkap poin data penting dari tautan masuk (tautan yang membawa pengguna dari web ke halaman arahan), seperti parameter kueri atau UTM, atau nilai default, yang mengidentifikasi sumber media, kampanye, iklan, dan lainnya.
7. Menggunakan poin data di atas untuk menghasilkan impresi dan mengirimkannya ke AppsFlyer.
8. Menghasilkan tautan keluar untuk setiap tombol unduhan platform.
9. Pengguna mengklik salah satu tombol unduh, dibawa ke toko aplikasi platform, mengunduh dan membuka aplikasi.
10. Penginstalan/pembukaan aplikasi pertama kali disesuaikan dengan tayangan dan dikaitkan dengan sumber media yang menayangkan iklan asli di web.

Informasi Tambahan

* <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">Lihat contoh halaman arahan lintas platform</Anchor>
* <Anchor target="_blank" href="/marketers/id/docs/cross-platform-landing-pages-with-smart-script">Pelajari cara menyiapkan laman landas lintas platform dengan Smart Script</Anchor>

</Accordion>

<div id="data-availability" />

## Ketersediaan data

Data platform CTV, PC, dan konsol mencakup data penginstalan, serta data acara dalam aplikasi yang memberikan wawasan kepada pengiklan mengenai nilai seumur hidup (LTV) pengguna non-organik dan organik, bberdasarkan langganan, pembelian dalam aplikasi, dan monetisasi iklan. Metrik LTV dihitung dari tanggal atribusi hingga saat ini.

Data tersedia sebagai berikut:

* Mengagregasi data melalui dasbor Ikhtisar.
* Data mentah melalui:
  * Data Locker
  * <Anchor target="_blank" href="/marketers/id/docs/raw-data-export-page">Ekspor</Anchor>
  * Pull API

**Catatan** : Untuk platform dengan sistem operasi Android dan iOS, ketersediaan laporan <Anchor target="_blank" href="/marketers/id/docs/aggregated-and-analytics-reporting-overview">agregat</Anchor> dan <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">data mentah</Anchor> sama dengan aplikasi seluler.

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Sifat | Catatan |
| --- | --- |
| Periode Waktu Re-attribution | Untuk platform CTV, PC, dan konsol, jendela atribusi ulang didasarkan pada periode ketidakaktifan yang ditentukan (default 90 hari). |
| Peristiwa pasca-penginstalan ulang | Dikaitkan dengan penginstalan pertama <Anchor target="_blank" href="/marketers/id/docs/measure-reinstalls#attributed-to-the-first-install">Pelajari lebih lanjut</Anchor> |
| Retargeting | <ul><li>Re-attribution Didukung untuk lintas platform-ke-mobile. Tidak untuk platform lain.</li><li>Re-engagement Tidak didukung</li></ul> |
| Metode Atribusi | <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#metode-atribusi">Lihat metode atribusi CTV, PC, dan platform konsol</Anchor> |
| Mata Uang | USD atau sebagaimana ditentukan dalam pengaturan aplikasi AppsFlyer |
| Zona waktu | UTC |
| Data biaya | Untuk aplikasi di platform CTV, PC, dan konsol, data biaya harus dikirim melalui <Anchor target="_blank" href="/marketers/id/docs/import-cost-data">Ad Spend Ingestion</Anchor> menggunakan metode unggah file melalui email. |

</Accordion>

<div data-zendesk-anchors="about-ctv-attribution=solusi-lintas-platform-appsflyer 01H7ZRK7PCNZG54ZQ0804HMR38=solusi-lintas-platform-appsflyer list-of-supported-ctv-and-gaming-device-types=platform-yang-didukung 01H7ZRK7PCP1KWRX1A5K81F4KR=platform-yang-didukung crossplatform-attribution=aliran-atribusi-lintas-platform 01H8EHHJNBA8NKMX2C8RSV7P31=aliran-atribusi-lintas-platform 01H8EQ4KS75Q62Z7WVNSTDXBZX=direct-attribution-link 01H8EQ4KS7C6HADNKQZYNTTFMF=crossplatform-onelink 01H8EQ4KS7NVYAD6MQ6MM26AVW=srn data-availability=ketersediaan-data h_01H9G52NKMQG9QD9S3N537BM7N=ketersediaan-data 01H7ZRK7PCJ6BRQZ2AKQTV5Q5E=traits-and-limitations" />
