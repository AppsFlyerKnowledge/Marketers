---
title: Menambahkan aplikasi baru
metadata:
  keywords:
    - Add App
    - adding an app
    - Advertisers
    - could not add app
    - security reasons
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2016-01-20T08:57:00Z'
  edited_at: '2021-03-05T23:49:02Z'
  id: 207377436
  locale: id
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/id/articles/207377436
---
> **Sekilas:** Tambahkan aplikasi Anda ke AppsFlyer untuk mencatat penginstalan dan in-app event-nya serta mengatribusikannya ke sumber media yang tepat.

## Menambahkan aplikasi

Jika Anda belum menambahkan aplikasi ke dashboard, layar pertama yang muncul akan meminta Anda untuk menambahkannya. Untuk menambahkan aplikasi tambahan, buka laman **My Apps (Aplikasi Saya)**, dan klik tombol **Add app (tambahkan aplikasi)**. Kemudian ikuti saja langkah-langkah wizard seperti yang dijelaskan pada tab berikut.

**Catatan:** Hanya admin akun dan anggota tim yang telah diberikan izin add app (menambahkan aplikasi) yang dapat menambahkan aplikasi.

<Accordion title="1 – Pilih status aplikasi">

![tambahkan aplikasi langkah 1](https://support.appsflyer.com/hc/article_attachments/360016229417/add_app_wizard_step1.png)

| Status | Di mana menggunakannya |
| --- | --- |
| Di store | Aplikasi Anda saat ini tersedia di app store berpemilik: iOS App Store, Google Play, Windows Phone Store. |
| Tertunda | Aplikasi Anda belum dipublikasikan atau belum disetujui oleh store. (Ini berguna saat Anda men-debug aplikasi untuk menguji AppsFlyer SDK).<br /><br />Setelah aplikasi Anda yang tertunda dipublikasikan, AppsFlyer secara otomatis akan memperbarui statusnya, sehingga Anda tidak perlu menambahkannya lagi. |
| App store pihak ketiga | Aplikasi Anda ada di app store Android selain di Google Play<br /><br /><br /><br />**Penting!**<br />Jika aplikasi Anda tersedia di lebih dari satu app store Android (yaitu, kombinasi antara di Google Play dan/atau app store pihak ketiga, sangat penting untuk mempertimbangkan opsi untuk <Anchor target="_blank" href="/marketers/id/docs/set-up-multi-store-android-attribution">mengatur atribusi Android multi-store</Anchor>. Penerapan yang tepat dari awalnya akan memastikan bahwa Anda dapat mengakses data yang diperlukan sesuai format yang Anda butuhkan.<br /><br /> |

</Accordion>

<Accordion title="2 – Tambahkan informasi store">

![tambahkan aplikasi langkah 2.png](https://support.appsflyer.com/hc/article_attachments/360016229397/add_app_wizard_step2.png)

<table><thead><tr><th>Status aplikasi<br/>(dari langkah 1)</th><th>Store</th><th>Detail</th></tr></thead><tbody><tr><td rowspan="3">Di store</td><td>App Store iOS</td><td> <strong>URL App Store</strong> (disalin dari App Store) <ul><li> <strong>Misalnya:</strong> https://apps.apple.com/us/app/partner-integrations/id1543229303<br/><br/>Aplikasi yang ditambahkan ke App Store sebelum 14 Juni 2019 dapat berisi <em>itunes.apple.com</em> di dalam URL-nya (bukan <em>apps.apple.com</em>).</li></ul></td></tr><tr><td><p>Google play</p></td><td><p><strong>URL Google Play</strong> (disalin dari Google Play)</p><ul><li> <strong>Misalnya:</strong> https://play.google.com/store/apps/details?id=com.appsflyer.adNetworkTest</li></ul></td></tr><tr><td><p>Windows Phone Store</p></td><td><p><strong>URL Windows Phone Store</strong> (disalin dari Windows Phone Store)</p><ul><li> <strong>Misalnya:</strong> https://www.microsoft.com/en-us/p/wordament/9wzdncrfhwfg</li></ul></td></tr><tr><td rowspan="3">Tertunda</td><td><p>App Store iOS</p></td><td><p><strong>Negara</strong>  App Store di mana aplikasi dikirimkan</p><p><strong>App ID (ID Aplikasi)</strong> ditetapkan oleh App Store, tanpa awalan <em>id</em></p><ul><li> <strong>Misalnya:</strong> 1543229303</li></ul></td></tr><tr><td><p>Google play</p></td><td><p><strong>Nama paket Android</strong></p><ul><li> <strong>Misalnya:</strong> com.appsflyer.adNetworkTest</li><li> <strong>Catatan:</strong> Nama paket peka huruf besar-kecil</li></ul></td></tr><tr><td><p>Windows Phone Store</p></td><td><p><strong>App ID (ID Aplikasi)</strong> ditetapkan oleh Windows Phone Store</p><ul><li> <strong>Misalnya:</strong> 9wzdncrfhwfg</li><li> <strong>Catatan:</strong> App ID (ID Aplikasi) peka huruf besar-kecil</li></ul></td></tr><tr><td colspan="2">App store pihak ketiga</td><td><p><strong>Nama paket Android</strong></p><ul><li> <strong>Misalnya:</strong> com.appsflyer.adNetworkTest</li><li> <strong>Catatan:</strong> Nama paket peka huruf besar-kecil</li></ul><p><strong>Nama kanal</strong> (misalnya, Amazon)</p><p><strong>App URL (URL Aplikasi)</strong> (disalin dari app store pihak ketiga)</p></td></tr></tbody></table>

</Accordion>

<Accordion title="3 – Atur zona waktu dan mata uang">

![tambahkan aplikasi langkah 3](https://support.appsflyer.com/hc/article_attachments/360016229457/add_app_wizard_step3.png)

**Zona waktu:** Sesuaikan zona waktu yang Anda pilih di sini dengan zona waktu yang Anda tetapkan dengan mitra atribusi lainnya (seperti Facebook dan Google Ads). Ini memastikan kecocokan sempurna antara data yang dilaporkan di dashboard AppsFlyer dan data yang Anda terima dari mitra ini. <Anchor target="_blank" href="/marketers/id/docs/changing-app-time-zone-settings">Pelajari lebih lanjut</Anchor> tentang pengaturan zona waktu aplikasi dan dampaknya.

**Mata uang:** Pilih dalam mata uang apa data aplikasi akan ditampilkan di dashboard. Event pendapatan dan pengeluaran dikonversi ke mata uang ini dengan menggunakan kurs yang berlaku pada waktu event. <Anchor target="_blank" href="/marketers/id/docs/app-settings#localization-currency-8">Pelajari lebih lanjut</Anchor> tentang pengaturan mata uang aplikasi dan dampaknya.

> 🚧 **Penting!**
>
> Berhati-hatilah dalam memilih mata uang yang ingin Anda gunakan untuk aplikasi ini. Anda tidak dapat mengubahnya lagi setelah biaya dan pendapatan dicatat.

</Accordion>

## Troubleshooting

Temukan solusi untuk beberapa masalah umum:

<Accordion title="Aplikasi tidak ditambahkan">

Jika terjadi kesalahan ini, hubungi CSM Anda atau kirimkan email ke [hello@appsflyer.com](mailto:hello@appsflyer.com).

</Accordion>

<Accordion title="Aplikasi tidak ada di store">

Pastikan bahwa Anda telah menyalin URL store dengan benar, menggunakan nama/ID aplikasi yang sesuai.

</Accordion>

<Accordion title="Tidak dapat mengakses marketplace">

Kesalahan ini kadang terjadi saat menambahkan aplikasi Android dari store non-AS. Ikuti langkah-langkah ini untuk menyelesaikannya:

1. Tambahkan aplikasi dengan status **Pending (Tertunda)**, seperti yang dijelskan di atas.
2. Buka laman **App settings (Pengaturan aplikasi)** AppsFlyer.
3. Ubah **negara App store** menjadi negara yang benar (misalnya, Jepang).

Setelah aplikasi ditambahkan, AppsFlyer secara otomatis akan mendeteksi bahwa aplikasi dipublikasikan dan memperbarui statusnya.

</Accordion>
