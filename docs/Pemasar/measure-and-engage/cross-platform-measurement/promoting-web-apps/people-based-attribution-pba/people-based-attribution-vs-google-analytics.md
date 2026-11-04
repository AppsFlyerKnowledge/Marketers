---
title: Atribusi berbasis orang vs. Google Analytics
metadata:
  keywords:
    - Google Analytics
    - People Based Analysis
    - People Based Attribution
    - People Based Attribution SDK
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-03-28T07:22:04Z'
  edited_at: '2023-02-15T13:15:05Z'
  id: 360001305617
  locale: id
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/id/articles/360001305617
---
> **Sekilas**: Perbedaan antara Atribusi Berbasis Orang (PBA) dan Google Analytics

<div id="pba-compared-to-google-analytics" />

## PBA dibandingkan dengan Google Analytics

PBA dan Google Analytics adalah analitik web dan solusi pengukuran konversi. Masing-masing berfokus pada aspek pengukuran yang berbeda. PBA juga menawarkan manfaat tambahan.

* PBA adalah otoritas atribusi independen yang tidak memihak yang berfokus pada pengukuran atribusi. PBA mengaitkan konversi dan pendapatan dengan sumber media dan kampanye yang membawa pengguna ke situs web Anda.
* Google Analytics lebih berfokus pada analisis web. Google Analytics mengumpulkan, menganalisis dan mengumpulkan data yang terkait dengan perilaku pengguna. Dengan Google Analytics Anda dapat menganalisis, misalnya, perilaku pengguna, perjalanan, event web.

<div id="benefits-of-pba-over-google-analytics" />

### Manfaat PBA dibandingkan Google Analytics

Berikut ini adalah manfaat PBA dibandingkan Google Analytics:

* PBA meliputi:
  * Pengukuran web-ke-aplikasi. Metrik ini memberi tahu Anda berapa banyak pengguna yang pindah dari situs web Anda ke aplikasi Anda. Metrik ini juga memberi tahu Anda sumber media dan kampanye mana yang membawa pengguna ke situs web Anda yang kemudian menginstal aplikasi Anda.
  * <Anchor target="_blank" href="/marketers/id/docs/pba-raw-data-reports">Data lengkap untuk konversi dan event</Anchor> yang dapat Anda tarik ke sistem BI Anda sendiri. Data ini memberi Anda kemampuan dan dukungan untuk menjalankan analisis Anda.

<div id="reasons-for-differences" />

### Alasan perbedaan

Jika Anda membandingkan data dari PBA dan Google Analytics, lihat alasan perbedaan data berikut.

<div id="sdk-implementation" />

#### Implementasi SDK

Cara Anda menerapkan PBA dan Google Analytics dapat memengaruhi pengumpulan data.

<div id="google-analytics-shows-more-sessions-and-visitors" />

<Accordion title="Google Analytics menunjukkan lebih banyak sesi dan pengunjung">

<div id="cause" />

#### Penyebab

Jika Google Analytics dimuat sebelum pengguna SDK Web yang pindah ke situs web lain atau pengguna yang menghabiskan waktu singkat di situs web Anda tidak dihitung dalam PBA. Hal tersebut menyebabkan perbedaan data untuk sesi dan pengunjung.

<div id="solution" />

#### Solusi

Kami sangat menyarankan memosisikan SDK Web sedemikian rupa sehingga memuat sedini mungkin.

Apakah Anda <Anchor target="_blank" href="/marketers/id/docs/pba-web-sdk-integration-guide#integrating-the-web-sdk-into-the-website">memuat SDK secara langsung atau melalui Manajer Google Tag</Anchor>, pemuatan SDK yang terlambat dapat menyebabkan perbedaan yang signifikan.

</Accordion>

<div id="google-analytics-shows-more-data-for-sessions-campaign-and-conversions" />

<Accordion title="Google Analytics menunjukkan lebih banyak data untuk sesi, kampanye, dan konversi">

<div id="cause-1" />

#### Penyebab

SDK Web hanya ada pada halaman tertentu. Google Analytics muncul di semua halaman. Akibatnya, Google Analytics mengumpulkan data dari seluruh situs web Anda sedangkan SDK Web mengumpulkan data hanya dari halaman tertentu. Hal ini menyebabkan perbedaan data untuk sesi, pengunjung, kampanye, dan konversi.

<div id="solution-1" />

#### Solusi

Terapkan SDK Web di semua halaman situs web Anda.

</Accordion>

<div id="dashboard-settings" />

### Pengaturan dasbor

Pengaturan dasbor seperti zona waktu dan filter data dapat memengaruhi cara data disajikan kepada Anda.

<div id="timezone-settings-discrepancies-in-data" />

<Accordion title="Pengaturan zona waktu - perbedaan data">

<div id="cause-2" />

#### Penyebab

Jika pengaturan zona waktu di Google Analytics Anda berbeda dari yang ada di dasbor PBA Anda, Anda mungkin menemukan perbedaan.

<div id="example" />

> 📄 **Contoh**
>
> Dasbor AppsFlyer Anda dikonfigurasikan ke UTC dan dasbor GA Anda dikonfigurasikan ke UTC +13. Ini berarti bahwa dasbor GA Anda lebih cepat satu hari dari dasbor AppsFlyer Anda.
>
> Karena itu, data yang muncul di dasbor AppsFlyer untuk 2 Maret hanya muncul di dashboard GA Anda jika Anda memilih 3 Maret di filter rentang tanggal.

<div id="solution-2" />

#### Solusi

Pastikan pengaturan zona waktu sama di AppsFlyer dan Google Analytics.

</Accordion>

<div id="data-filters--discrepancies-in-data" />

<Accordion title="Filter data - perbedaan dalam data">

<div id="issue" />

#### Berita

AppsFlyer dan Google Analytics memungkinkan Anda memfilter data berdasarkan tanggal, sumber media, kampanye, dan event yang dikaitkan. Filter berbeda di AppsFlyer dan Google Analytics dapat menghasilkan tampilan berbeda untuk data yang sama.

<div id="solution-3" />

#### Solusi

Saat Anda membandingkan data dari dua dasbor, pastikan tidak ada filter yang diterapkan ke kumpulan data.

</Accordion>

<div id="conversions-and-events" />

### Konversi dan event

Berbagai model atribusi, jendela lookback, cara Anda mengirim event, dan pengaturan kuki, semuanya dapat mempengaruhi pengumpulan dan pemrosesan data.

<div id="lookback-window-discrepancies-in-conversion-measurement" />

<Accordion title="Jendela Lookback - perbedaan dalam pengukuran konversi">

<div id="cause-3" />

#### Penyebab

Jika Anda memiliki jendela lookback berbeda di Google Analytics dan PBA, perbedaan mungkin terjadi pada data atribusi.

<div id="solution-4" />

#### Solusi

Jendela lookback PBA selalu 30 hari. Pastikan untuk menetapkan jendela lookback 30 hari di Google Analytics ketika Anda <Anchor target="_blank" href="https://support.google.com/analytics/answer/1665189">memilih model atribusi Anda</Anchor>.

</Accordion>

<div id="attribution-model--discrepancies-in-conversion-measurement" />

<Accordion title="Model atribusi -perbedaan dalam pengukuran konversi">

<div id="cause-4" />

#### Penyebab

Berbagai model atribusi dalam PBA dan Google Analytics dapat menyebabkan perbedaan dalam data atribusi.

<div id="solution-5" />

#### Solusi

Google Analytics menawarkan <Anchor target="_blank" href="https://support.google.com/analytics/answer/1665189?hl=en">model atribusi default</Anchor> yang dapat Anda pilih. Namun, PBA beroperasi dalam model atribusi jendela lookback 30-hari sentuhan secara tidak langsung yang terakhir. Pastikan untuk memilih model atribusi sentuhan non-langsung terakhir di Google Analytics.

</Accordion>

<div id="sending-events" />

<Accordion title="Mengirim event">

<div id="issue-1" />

#### Berita

Kedua SDK Google Analytics dan SDK Web memungkinkan Anda mengirim event. Jika Anda menerapkan satu logika untuk mengirim event ke Google Analytics dan yang lain untuk mengirim event ke PBA, perbedaan mungkin timbul.

<div id="solution-6" />

#### Solusi

Saat Anda mengirim event, verifikasi hal-hal berikut:

* Pastikan pemicu yang sama berlaku untuk keduanya
* Pastikan Anda mengirim event ke Google Analytics dan PBA

Klik <Anchor target="_blank" href="/marketers/id/docs/pba-web-sdk-integration-guide#principles-of-event-recording">di sini</Anchor> untuk mempelajari cara mengirim event menggunakan SDK Web.

</Accordion>

<div id="cookies" />

<Accordion title="Kuki">

Kedua PBA dan Google Analytics menggunakan kuki untuk mengenali pengguna.

<div id="cookie-settings-in-google-analytics" />

#### Pengaturan kuki di Google Analytics

Meskipun disarankan untuk mengizinkan Google Analytics SDK secara otomatis menangani pengaturan cookie, Anda masih dapat  <Anchor target="_blank" href="https://developers.google.com/analytics/devguides/collection/analyticsjs/cookies-user-id">mengonfigurasi dan mengubah pengaturan kuki</Anchor> . Setiap perubahan dalam pengaturan kuki dapat menyebabkan perbedaan.

<div id="setting-cookie-expiration" />

#### Mengatur Kedaluwarsa Kuki

Google Analytics memungkinkan Anda untuk mengatur kedaluwarsa kuki. Jika Anda mengatur kuki Google Analytics untuk kedaluwarsa sebelum kuki SDK Web tersebut kedaluwarsa, ini dapat menyebabkan perbedaan.

<div id="example-1" />

> 📄 **Contoh**
>
> Mark adalah pengunjung tetap ke situs web Anda selama lebih dari setahun sekarang dan mempertimbangkan untuk berlangganan konten premium.
>
> Pengembang Anda mengatur kuki Google Analytics untuk kedaluwarsa setelah satu tahun. SDK Web, bagaimanapun, mengatur kuki untuk kedaluwarsa setelah dua tahun.
>
> Ketika Mark akhirnya berlangganan dan konversi didaftarkan, kuki Google Analytics tidak lagi berlaku dan yang lain ditetapkan sebagai penggantinya.
>
> Hasil akhirnya adalah bahwa Google Analytics menunjukkan dua pengguna, keduanya adalah Mark, dengan hanya satu dari mereka yang memiliki konversi yang terkait dengannya. Namun PBA, menunjukkan satu pengguna untuk Mark dan pengguna yang sama yang memiliki konversi yang terkait dengannya.
>
> Hal tersebut berarti bahwa tingkat konversi Anda di Google Analytics lebih rendah daripada di PBA.

<div id="setting-cookie-subdomain" />

#### Pengaturan Subdomain Kuki

Google Analytics memungkinkan Anda untuk mengatur kuki untuk subdomain sedangkan PBA hanya menetapkan kuki pada domain tingkat atas.

<div id="example-2" />

> 📄 **Contoh**
>
> Anda menetapkan kuki ke subdomain **store.mywebsite.com** . Sharon mengunjungi situs web Anda dan kemudian buka toko online Anda di **store.mywebsite.com** . Google Analytics menganggapnya **sebagai dua pengguna yang berbeda** .
>
> Karena PBA hanya menetapkan kuki pada domain tingkat atas **mywebsite.com** , itu menganggap Sharon di **mywebsite.com** dan **store.mywebsite.com** sebagai pengguna yang sama.
>
> Hasil akhirnya adalah dua pengguna di Google Analytics dan satu pengguna di PBA.

</Accordion>

<div data-zendesk-anchors="pba-compared-to-google-analytics=pba-dibandingkan-dengan-google-analytics benefits-of-pba-over-google-analytics=manfaat-pba-dibandingkan-google-analytics reasons-for-differences=alasan-perbedaan sdk-implementation=implementasi-sdk cause=penyebab solution=solusi cause::49d3e519=penyebab-1 solution::447e7ac9=solusi-1 dashboard-settings=pengaturan-dasbor cause::30244d2c=penyebab-2 solution::f1a0e066=solusi-2 data-filters-%C2%A0discrepancies-in-data=data-filters--discrepancies-in-data issue=berita solution::df8f3921=solusi-3 conversions-and-events=konversi-dan-event cause::b346571c=penyebab-3 solution::4bb14ac9=solusi-4 attribution-model%C2%A0-discrepancies-in-conversion-measurement=attribution-model--discrepancies-in-conversion-measurement cause::2296f6c1=penyebab-4 solution::b2be4a33=solusi-5 issue::b412f5ba=berita-1 solution::39b4d7d6=solusi-6 cookie-settings-in-google-analytics=pengaturan-kuki-di-google-analytics setting-cookie-expiration=mengatur-kedaluwarsa-kuki setting-cookie-subdomain=pengaturan-subdomain-kuki" />
