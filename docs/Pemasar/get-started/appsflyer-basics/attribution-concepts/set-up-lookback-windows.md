---
title: Jendela lookback dijelaskan
metadata:
  keywords:
    - Advertisers
    - look back
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-07T09:27:55Z'
  edited_at: '2023-08-01T11:48:42Z'
  id: 208338403
  locale: id
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/id/articles/208338403
---
> **Sekilas:** Sesuaikan jendela lookback klik-tayang dan lihat-tayang, berdasarkan perjanjian Anda dengan sumber media.

<div id="lookback-windows" />

## Jendela lookback

Jendela lookback atribusi yang dapat dikonfigurasi memungkinkan Anda untuk menyesuaikan periode atribusi berdasarkan perjanjian Anda dengan sumber media.

Dengan mengatur jendela lookback atribusi per sumber media, AppsFlyer mengatribusikan sesuai dengan ketentuan yang disepakati.

**Jenis jendela lookback**:

* **Jendela lookback klik**: Jangka waktu maksimal setelah iklan diklik di mana penginstalan dapat diatribusikan ke iklan. Penginstalan yang terjadi setelah jendela lookback dianggap Organik.
* **Jendela lookback lihat-tayang**: Jangka waktu maksimal setelah iklan dilihat di mana penginstalan dapat diatribusikan ke iklan. Penginstalan yang terjadi setelah jendela lookback dianggap Organik.

<div id="configurable-lookback-windows-per-attribution-type" />

#### Jendela lookback yang dapat dikonfigurasi per jenis atribusi

<table><thead><tr><th rowspan="2"><p><strong>Jenis Atribusi</strong></p></th><th rowspan="2"><p><strong>Metode Atribusi</strong></p></th><th colspan="2"><p><strong>Klik jendela lookback</strong> </p></th></tr><tr><th><p><strong>Jangkauan</strong></p></th><th><p><strong><strong>Default</strong></strong></p></th></tr></thead><tbody><tr><td rowspan="2"><p>Klik-tayang</p><p>(Semua sumber media)</p></td><td><p>Perujuk, Pencocokan ID</p></td><td><p>1-30 Hari ATAU<br/>1-23 Jam</p></td><td><p>7 Hari</p></td></tr><tr><td><p>Pemodelan probabilistik</p></td><td><p><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">Adaptif</a></p></td><td><p>Hingga 24 jam</p></td></tr><tr><td rowspan="3"><p>View-Through (Lihat-Tayang)</p><p>(<a href="./measure-view-through-engagements#view-vta-partner-list" target="_blank">Sumber media</a> yang dipilih)</p></td><td><p>Pencocokan ID</p></td><td><p>1-24 jam</p><p>[Hingga 15 Des 2021, batas atas adalah 7 hari]</p></td><td><p>24 jam</p></td></tr><tr><td><p>Pemodelan probabilistik</p></td><td><p><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">Adaptif</a></p></td><td><p>Hingga 24 jam</p></td></tr><tr><td><p>Pemodelan probabilistik (lintas platform)</p></td><td><p>1-72 jam</p></td><td><p>24 jam</p></td></tr></tbody></table>

<div id="probabilistic-modeling-lookback-window" />

### Jendela lookback pemodelan probabilistik

Jendela lookback pemodelan probabilistik, yang digunakan untuk mempertahankan akurasi atribusi, memiliki karakteristik berikut:

* Berlaku baik untuk klik dan impresi
* Memiliki durasi adaptif hingga 24 jam
* Mengabaikan pengaturan durasi jendela yang dikirim pada tautan atribusi
* Memiliki durasi yang lebih pendek dari jendela yang digunakan oleh model deterministik

Untuk mempelajari lebih lanjut, baca tentang <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#probabilistic-modeling">metode pemodelan Probabilistik AppsFlyer</Anchor>.

<div id="lookback-window-setup" />

## Pengaturan jendela lookback

Selanjutnya, kami mencantumkan proses pengaturan jendela lookback untuk SRN dan Tautan Atribusi

<Tabs>
<Tab title="Jendela Lookback SRN">

<div id="h_01JKWVQB6TTA24VAZ9WVJMGY4X" />

<div id="non-srn-attribution-lookback-window-for-engaged-click-through-and-engaged-view-through" />

<div id="non-srn-attribution-lookback-window-for-click-through-and-view-through" />

<div id="important" />

<div id="attribution-lookback-window-for-srns" />

### Jendela lookback atribusi untuk SRN

> 🚧 **Penting!**
>
> Setiap SRN memiliki lookback default-nya sendiri. Kami menyarankan untuk mencocokkan nilai jendela lookback di AppsFlyer dengan nilai SRN untuk meminimalkan perbedaan. Mengubahnya dapat mengakibatkan perbedaan. Untuk mempelajari lebih lanjut, lihat [contoh perbedaan SRN](#skenario-dan-contoh).

1. Dari dashboard AppsFlyer Anda, buka **Integrasi Aktif.**
2. Cari dan pilih SRN - lihat <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns#srn-diintegrasikan-dengan-appsflyer">daftar SRN yang didukung</Anchor>.
3. Secara default, atribusi Lihat-Tayang diaktifkan.
4. Di tab **Integrasi** , gulir ke bawah ke konfigurasi **Atribusi klik-tayang** dan **Atribusi lihat-tayang** .
5. Gunakan penggeser untuk menyetel jendela atribusi

Lihat di bawah setiap jendela lookback SRN:

| SRN | Jendela Lookback Klik-Tayang Default (hari) | Jendela Lookback Lihat-Tayang Default (jam) |
| --- | --- | --- |
| Google | 30 | 24 |
| Iklan Meta | 7 | 24 |
| Snapchat | 28 | 24 |
| Twitter | 14 | 24 |
| Apple Search Ads | 30 | N/A |
| Oath (YahooGemini) | 7 | 24 |

</Tab>

<Tab title="Jendela Lookback Tautan Atribusi">

<div id="attribution-lookback-window-with-attribution-links" />

### Jendela lookback atribusi dengan tautan atribusi

1. Dari dashboard AppsFlyer Anda, buka **Integrasi Aktif.**
2. Cari dan pilih mitra.
3. Secara default, atribusi Lihat-Tayang diaktifkan.
4. Klik tab **Tautan atribusi** .
5. Pilih apakah Anda ingin menyetel waktu dalam hari atau jam.
6. Gunakan penggeser di bawah **Atribusi klik-tayang** ( parameter `af_click_lookback` ) dan **Atribusi lihat-tayang** ( parameter `af_viewthrough_lookback` ) untuk menyetel jendela atribusi.  
   Waktu yang dipilih secara otomatis tercermin dalam tautan atribusi.
7. Pilih parameter yang sesuai dengan kampanye, yaitu nama kampanye, ad set, dll.
8. Salin dan simpan tautan - ini adalah tautan yang Anda berikan ke jaringan iklan.

<div id="tip" />

> 👍 **Tips**
>
> * Ingin beberapa tips dan trik untuk konfigurasi jendela lookback? Lihat <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks">kursus singkat dan informatif</Anchor> ini di Portal Pembelajaran AppsFlyer.
> * [Klik di sini](/docs/set-up-lookback-windows#lookback-in-hours-for-flash-campaigns) untuk mempelajari kapan Anda harus menggunakan jam untuk jendela atribusi.

<div id="lookback-window-in-onelink" />

### Jendela lookback di OneLink™

Anda juga dapat mengatur jendela lookback di OneLink.

1. <Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template">Konfigurasikan OneLink</Anchor>
2. <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#buat-tautan-onelink">Buat Tautan Atribusi Khusus</Anchor>
3. Di bagian **Lanjutan**, aktifkan **Sesuaikan Jendela Lookback** dan atur jendela lookback.

</Tab>
</Tabs>

<div id="distribution-of-first-app-launches" />

## Distribusi peluncuran aplikasi pertama

Di bawah ini adalah grafik yang menunjukkan distribusi peluncuran aplikasi pertama sejak hari interaksi.

[![](https://files.readme.io/8fdc8b23ba9a1b78bdea7bacad99d6ed5e59d57de32f395cb2fd9e5451483962-360001666918.png)](https://files.readme.io/8fdc8b23ba9a1b78bdea7bacad99d6ed5e59d57de32f395cb2fd9e5451483962-360001666918.png)

Grafik tersebut dapat memberikan gambaran yang lebih baik tentang jumlah pengguna yang menginstal aplikasi sebagai fungsi jendela lookback.

Mayoritas pengguna, sedikit di atas 97%, yang meluncurkan aplikasi melakukannya dalam waktu 7 hari setelah berinteraksi dengan iklan. 2% sisanya melakukannya dalam rentang antara hari ke-7 dan akhir jendela lookback (hari ke-30).

Faktanya, hampir 62% pengguna yang meluncurkan aplikasi melakukannya dalam waktu 15 menit setelah berinteraksi dengan iklan. 72% pengguna melakukannya dalam satu jam pertama.

<div id="tip-1" />

<div id="scenarios-and-examples" />

## Skenario dan contoh

Di bawah ini adalah daftar kemungkinan skenario dan contoh penggunaan jendela lookback.

<div id="srn-discrepancy-srn-lookback-longer-than-appsflyer" />

<Accordion title="Perbedaan SRN: Lookback SRN lebih lama dari AppsFlyer">

Anda mengatur kampanye di Twitter dan mengonfigurasi jendela lookback klik-tayang menjadi 7 hari. Twitter, di sisi lain, memiliki jendela lookback default selama 14 hari.

[![srn-discrepancy-srn-lookback-larger-than-appsflyer.png](https://files.readme.io/a0a60df2c1b142c9b2871c2083168ef5d88922001f1e5ab6a95c7ffbdcc178a5-360001586637.png)](https://files.readme.io/a0a60df2c1b142c9b2871c2083168ef5d88922001f1e5ab6a95c7ffbdcc178a5-360001586637.png)

</Accordion>

<div id="srn-lookback-smaller-than-appsflyer" />

<Accordion title="Lookback SRN lebih kecil dari AppsFlyer">

Anda menetapkan kampanye di Twitter dan mengonfigurasi jendela lookback klik-tayang menjadi 28 hari. Twitter, di sisi lain, memiliki jendela lookback default selama 14 hari.

[![srn-lookback-smaller-than-appsflyer.png](https://files.readme.io/9111035d903bfb35be2ab4bff27c16e527b401b12225b71316a7e36ed68ffb0c-360001586697.png)](https://files.readme.io/9111035d903bfb35be2ab4bff27c16e527b401b12225b71316a7e36ed68ffb0c-360001586697.png)

</Accordion>

<div id="attribution-link-without-a-lookback-window-parameter" />

<Accordion title="Tautan atribusi tanpa parameter jendela lookback">

Mungkin untuk memiliki tautan atribusi yang tidak memiliki parameter jendela lookback. Dalam kasus seperti itu, AppsFlyer secara default menggunakan jendela lookback 7 hari untuk klik, dan jendela lookback 1 hari untuk impresi.

</Accordion>

<div id="lookback-in-hours-for-flash-campaigns" />

<Accordion title="Lookback dalam hitungan jam untuk kampanye flash">

Kampanye flash adalah kampanye yang bertujuan untuk meminta pengguna menginstal aplikasi secepat mungkin dan dalam jendela promosi singkat.

Aplikasi eCommerce bernama SuperShopping menjalankan kampanye flash. Dalam kampanye ini, pengguna yang menginstal aplikasi dalam waktu satu jam mendapatkan penawaran khusus.

Johnny, pemasar utama SuperShopping, membuat Tautan atribusi dan menyetel jendela lookback ke 1 jam. Dengan cara ini, Johnny mengetahui berapa banyak pengguna yang menanggapi kampanye tersebut.

Selain itu, pengembang aplikasi dapat mengidentifikasi pengguna yang berasal dari kampanye flash ini dan menyampaikan promosi yang diiklankan oleh kampanye tersebut.

</Accordion>

> 👍 **Tips**
>
> Ingin beberapa tips dan trik tentang jendela lookback dan atribusi? Lihat kursus singkat dan informatif <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks">ini di Portal Pembelajaran AppsFlyer</Anchor>.

<div data-zendesk-anchors="lookback-windows=jendela-lookback configurable-lookback-windows-per-attribution-type=jendela-lookback-yang-dapat-dikonfigurasi-per-jenis-atribusi probabilistic-modeling-lookback-window=jendela-lookback-pemodelan-probabilistik lookback-window-setup=pengaturan-jendela-lookback attribution-lookback-window-for-srns=jendela-lookback-atribusi-untuk-srn lookback-window-in-onelink%E2%84%A2=lookback-window-in-onelink distribution-of-first-app-launches=distribusi-peluncuran-aplikasi-pertama scenarios-and-examples=skenario-dan-contoh" />
