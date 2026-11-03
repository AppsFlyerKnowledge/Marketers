---
title: Pemecahan masalah dan Pertanyaan umum OneLink
metadata:
  keywords:
    - faq
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2020-10-27T11:26:30Z'
  edited_at: '2024-03-11T12:36:22Z'
  id: 360014821438
  locale: id
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/id/articles/360014821438
---
> **Sekilas:** Temukan solusi dengan cepat untuk menguji dan men-debug masalah pengalihan/perilaku tautan khusus OneLink.

## Panduan pemecahan masalah OneLink

## OneLink pertanyaan yang sering diajukan

### Pertanyaan umum Templat OneLink

<div id="which-method-should-i-use-for-opening-apps-universal-links-app-links-or-uri-schemes" />

<Accordion title="Metode mana yang harus saya gunakan untuk membuka aplikasi—Tautan Universal, Tautan Aplikasi, atau skema URI?">

**Tautan Universal:** Diperlukan untuk lebih dari 98% pengguna iOS

**Tautan Aplikasi** Untuk pengguna Android dengan versi 6.0+. **Catatan**: Samsung OS tidak dapat membuka aplikasi menggunakan Tautan Aplikasi Android.

> 📘 **Catatan**
>
> Tautan Universal dan Tautan Aplikasi memerlukan bukti bahwa domain di URL yang diklik (dengan kata lain, domain tautan khusus OneLink atau domain bermerek) dimiliki dan diasosiasikan dengan aplikasi spesifik yang dicoba untuk dibuka. Asosiasi domain ini dilakukan melalui **file Apple App Site Association (AASA)** untuk iOS dan file **Assetlinks** untuk Android.
>
> File-file ini di-hosting oleh AppsFlyer atau oleh pemasang iklan di situs webnya. Secara default, saat Anda membuat templat OneLink dan menyiapkan Tautan Universal dan Tautan Aplikasi, file ini dibuat dan di-hosting oleh AppsFlyer.

**Skema URI:** Metode utama untuk membuka aplikasi di perangkat Samsung. Jika tidak, ini adalah metode lawas dan mundur untuk membuka aplikasi. Dapat digunakan:

* Untuk pengguna Android dengan versi sebelum 6.0 (kurang dari 15% pengguna Android)
* Sebagai cadangan saat Tautan Universal dan Tautan Aplikasi tidak membuka aplikasi karena tidak berfungsi atau tidak disiapkan.

  **Catatan:** Menggunakan skema URI sebagai cadangan untuk Tautan Universal tunduk pada batasan berbasis iOS. <Anchor target="_blank" href="/marketers/id/docs/uri-scheme-fallback-for-ios">Pelajari lebih lanjut</Anchor>.

#### Penautan Langsung

Tautan Universal, Tautan Aplikasi, dan skema URI adalah metode aman untuk **membuka** aplikasi. Untuk menautkan secara langsung dan mengalihkan pengguna ke aktivitas atau halaman tertentu di aplikasi, ikuti <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">petunjuk tautan langsung OneLink</Anchor>.

</Accordion>

<div id="which-operating-systems-allow-uri-schemes-to-open-the-app" />

<Accordion title="Sistem operasi mana yang mengizinkan skema URI untuk membuka aplikasi?">

| OS | Apakah skema URI berfungsi untuk membuka aplikasi? |
| --- | --- |
| iOS | **Ya.** Gunakan sebagai cadangan untuk kegagalan Tautan Universal.<br /><br />**Catatan penting:**<ul><li>Menggunakan skema URI sebagai cadangan tunduk pada batasan berbasis iOS.</li><li>Untuk banyak browser, termasuk Safari, Anda harus menambahkan `af_force_deeplink=true` parameter ke URL untuk menggunakan skema URI sebagai cadangan. <Anchor target="_blank" href="/marketers/id/docs/uri-scheme-fallback-for-ios">Pelajari lebih lanjut</Anchor>.</li></ul> |
| Android | **Ya.** Gunakan untuk perangkat Samsung, versi Android sebelum 6.0 dan sebagai cadangan saat App Links gagal pada versi Android yang lebih baru. |
| Amazon | **Tidak** |
| Windows Mobile | **Tidak** |

</Accordion>

<div id="do-i-need-to-update-the-app-after-ios-universal-links-and-android-app-links-setup" />

<Accordion title="Apakah saya perlu memperbarui aplikasi setelah penyiapan Tautan Universal iOS dan Tautan Aplikasi Android?">

**Ya.** Setiap kali Tautan Universal atau Tautan Aplikasi diterapkan untuk membuka aplikasi bagi pengguna yang sudah ada, Domain Terasosiasi iOS atau AndroidManifest.xml diperbarui. Artinya, Anda harus mengunggah versi baru aplikasi ke app store yang relevan. **Tips:** Untuk meminimalkan kebutuhan akan pembaruan aplikasi, buat semua perubahan terkait pengembang yang diperlukan untuk <Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">membuka aplikasi</Anchor> dan <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">menautkan langsung</Anchor> sekaligus.

</Accordion>

<div id="can-i-redirect-existing-users-to-a-web-page-instead-of-the-app" />

<Accordion title="Dapatkah saya mengalihkan pengguna yang sudah ada ke halaman web, bukan ke aplikasi?">

**Ya.** Namun, mengonfigurasi templat Anda untuk melakukan hal tersebut memengaruhi semua pengguna (baru dan yang sudah ada), dan mengarahkan semua orang ke halaman arahan/URL web. Artinya, pengguna baru tidak dikirim ke app store.

Untuk mengirim pengguna ke halaman web:

1. Di templat Anda, jangan siapkan Tautan Universal, Tautan Aplikasi, atau skema URI.
2. Siapkan pengalihan untuk saat aplikasi tidak diinstal ke halaman arahan/URL web.
   * Halaman arahan/URL web ditambahkan sebagai nilai untuk parameter af\_android\_url dan af\_ios\_url.
   * Pengalihan kemudian diterapkan secara otomatis saat aplikasi diinstal (untuk pengguna yang sudah ada) juga.

**Catatan** : Jika Anda ingin mengalihkan pengguna yang sudah ada ke halaman web seluler hanya setelah peluncuran aplikasi, pengembang aplikasi Anda harus mengonfigurasi perilaku tersebut.

</Accordion>

<div id="can-i-redirect-tablet-users-to-a-different-app-or-url-then-mobile-app-users" />

<Accordion title="Bisakah saya mengalihkan pengguna tablet ke aplikasi atau URL yang berbeda lalu ke pengguna aplikasi seluler?">

Anda dapat mengatur pengalihan khusus untuk:

* telepon Windows
* iPad
* Amazon Kindle Fire.

Tablet lain saat ini tidak didukung untuk pengalihan terpisah.

</Accordion>

<div id="can-i-assign-an-app-to-multiple-onelink-templates" />

<Accordion title="Bisakah saya menetapkan aplikasi ke beberapa templat OneLink?">

**Ya.** Meskipun Anda dapat menggunakan satu templat OneLink untuk membuat URL OneLink dalam jumlah tak terbatas, dalam beberapa kasus, mungkin perlu untuk menetapkan aplikasi ke lebih dari satu templat OneLink. Misalnya, jika Anda memiliki beberapa versi aplikasi Android untuk pasar di luar toko, Anda mungkin memerlukan templat OneLink terpisah untuk setiap versi Android dengan aplikasi iOS yang sama yang ditetapkan untuk semuanya.

**Penting**:

Untuk templat yang menggunakan Tautan Universal iOS dan Tautan Aplikasi Android untuk membuka aplikasi, **jika templat Anda memiliki subdomain yang berbeda**, Anda perlu mengonfigurasi dan memperbarui aplikasi iOS dan Android untuk masing-masing:

* **Tautan Universal iOS:** Setelah membuat templat OneLink baru dan memperbarui domain terkait di aplikasi, kirimkan versi baru ke App Store. Hanya pengguna iOS yang telah memperbarui ke versi baru yang dapat mengaktifkan URL OneLink yang dibangun di atas templat baru.
* **Tautan Aplikasi Android:**
  1. Setelah membuat templat OneLink baru, salin cuplikan XML di bagian bawah bagian Tautan Aplikasi dan tambahkan ke file **AndroidManifest.xml** di dalam maksud yang ingin Anda tautkan secara langsung, selain maksud sebelumnya.
  2. Rilis versi baru ke toko. Hanya pengguna Android yang telah memperbarui ke versi baru yang dapat mengaktifkan URL OneLink yang dibangun di atas templat baru.

</Accordion>

<div id="can-i-delete-a-onelink-template" />

<Accordion title="Dapatkah saya menghapus templat OneLink">

**Ya,** tetapi hanya dengan menghubungi CSM Anda atau dengan mengirimkan email ke tim Interaksi Pelanggan (Customer Engagement) kami di [hello@appsflyer.com](mailto:hello@appsflyer.com).

**Catatan:** Jika Anda memiliki URL OneLink berdasarkan templat yang dihapus, **URL tersebut tidak akan berfungsi bahkan untuk membawa pengguna ke app store.** Untuk alasan ini, sangat penting bagi Anda untuk tidak menghapus templat tanpa terlebih dahulu memastikan bahwa tidak ada URL OneLink yang menggunakannya. Sebagai alternatif, pertimbangkan apakah mungkin untuk mencapai hasil yang Anda perlukan dengan mengubah konfigurasi templat yang ada alih-alih menghapusnya.

</Accordion>

<div id="can-i-change-the-subdomain-in-a-onelink-template" />

<Accordion title="Bisakah saya mengubah subdomain di templat OneLink?">

**Ya, selama belum ada tautan khusus di AppsFlyer berdasarkan templat.**

Jika sudah ada tautan khusus di AppsFlyer berdasarkan templat OneLink, maka subdomain tidak dapat diubah. Pembatasan ini dirancang untuk mencegah pemutusan pengalihan/perilaku penautan langsung dari tautan live.

Jika Anda perlu mengubah subdomain dalam templat dengan tautan khusus yang sudah ada, Anda dapat:

* Buat templat OneLink baru dengan subdomain yang baru, dan buat tautan berdasarkan subdomain tersebut.
* Hapus semua tautan khusus yang ada berdasarkan templat yang subdomainnya perlu diubah. Setelah semua tautan berdasarkan templat sudah dihapus, subdomain menjadi dapat diedit.

</Accordion>

<div id="can-the-domainsubdomain-of-a-onelink-template-be-applied-to-the-template-id-of-another-template" />

<Accordion title="Bisakah domain/subdomain dari templat OneLink diterapkan ke ID templat dari templat lain?">

**No.** Mengambil subdomain/domain yang dikonfigurasi ke templat dan ID templat tertentu dan menggabungkannya secara manual ke ID templat yang berbeda merusak fungsionalitas Tautan Universal dan Tautan Aplikasi, dan menimbulkan ancaman keamanan.

**Contoh:**

* Templat 1ABC dikonfigurasikan dengan subdomain **bank.onelink.me**.
* Templat D123 dikonfigurasi dengan subdomain **game.onelink.me**.
* Tautan **bank.onelink.me/1ABC/shorturl** dibuat berdasarkan template 1ABC dan berfungsi.
* Tautan **game.onelink.me/D123/exampleurl** dibuat berdasarkan templat D123 dan berfungsi.
* Tautan **game.onelink.me/1ABC/shorturl** tidak bekerja
* **Tautan bank.onelink.me/D123/exampleurl** tidak bekerja

</Accordion>

<div id="can-i-use-the-same-subdomain-for-more-than-one-template" />

<Accordion title="Bisakah saya menggunakan subdomain yang sama untuk lebih dari satu templat?">

**Ya.** Namun, pastikan Anda membuat templat terpisah dengan subdomain; jangan hanya menambahkan subdomain secara manual ke ID templat.

</Accordion>

<div id="how-can-i-redirect-desktop-users" />

<Accordion title="Bagaimana saya bisa mengalihkan pengguna desktop?">

Pengguna desktop dapat terlibat dengan tautan khusus OneLink Anda, misalnya, melalui kampanye email. Namun, saat pengguna desktop mengeklik tautan ini, mereka tidak dapat dialihkan ke situs seluler, app store, atau aplikasi.

**Jadi, bagaimana saya dapat memberikan pengguna desktop pengalaman pengguna yang baik dan mengubah mereka menjadi pengguna seluler?**

Di URL atau templat OneLink, Anda dapat mengalihkan pengguna desktop (Windows atau Mac) ke URL lain. URL web ini ditambahkan ke tautan di parameter `af_web_dp`. **Catatan:** Jika tautan Anda berisi `af_web_dp`, AppsFlyer tidak mendaftarkan klik ketika tautan berasal dari desktop.

> 👍 **Tip**
>
> Coba alihkan pengguna desktop ke URL web yang berisi formulir web khusus yang mengirimkan URL OneLink ke perangkat seluler pengguna desktop melalui SMS atau email. Pelajari selengkapnya tentang opsi ini sebagai bagian dari solusi <Anchor target="_blank" href="/marketers/id/docs/set-up-smart-script-to-convert-web-visitors#desktop">OneLink Smart Script</Anchor> .

</Accordion>

<div id="how-can-i-redirect-chrome-os-users" />

<Accordion title="Bagaimana cara mengalihkan pengguna Chrome OS?">

Aplikasi di Chromebook dianggap sebagai aplikasi Android.

Untuk Chromebook, untuk mengalihkan pengguna baru tanpa menginstal aplikasi Anda ke URL web lain:

1. Di pengaturan templat OneLink, di bawah **Setel perilaku tautan** > **Saat aplikasi tidak diinstal** > **Android**, klik **Ubah ke URL berbeda**.  
   ATAU  
   Di pengaturan tautan OneLink, di bawah **Tautan langsung & pengalihan** > **Pengalihan** > **Saat aplikasi tidak diinstal** > **Android**, pilih URL Web.
2. Masukkan URL tersebut.  
   Ketika ditambahkan melalui pengaturan tautan, URL tersebut ditambahkan ke tautan Anda di parameter `af_android_url`.

</Accordion>

### Pertanyaan umum tautan OneLink

<div id="does-onelink-work-without-the-appsflyer-sdk" />

<Accordion title="Dapatkah OneLink bekerja tanpa SDK AppsFlyer?">

**Ya, tapi hanya sebagian.**

Jika Anda perlu mengonversi pengunjung web seluler menjadi pengguna seluler dengan cepat dan tidak dapat mengintegrasikan SDK AppsFlyer, Anda dapat melakukannya.

Pengalihan pengguna dasar dan peluncuran aplikasi bekerja bahkan jika SDK AppsFlyer belum terintegrasi ke aplikasi. Spanduk Cerdas juga tidak memerlukan SDK dan juga berfungsi dengan baik tanpanya.

Namun, ketiadaan SDK berarti:

* Pengguna yang mengeklik tidak dapat ditautkan secara langsung setelah peluncuran awal aplikasi.
* Data atribusi tidak dicatat.
* In-app event tidak dicatat.

</Accordion>

<div id="what-methods-are-available-for-creating-onelink-custom-links" />

<Accordion title="Metode apa yang tersedia untuk membuat tautan khusus OneLink?">

Tabel berikut membandingkan berbagai metode yang tersedia untuk membuat tautan khusus OneLink.

| Metode pembuatan tautan | Penggunaan | URL pendek/panjang | Fitur premium | Terlihat di UI? | Atribusi TTL (Time to Live) maks dan default |
| --- | --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">UI AppsFlyer</Anchor> | Buat templat OneLink dan tautan khusus | Keduanya | -- | ✓ | Tanpa TTL |
| <Anchor target="_blank" href="/marketers/id/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor> | Buat ribuan OneLink dengan cepat | Pendek | ✓ | -- | 31 hari |
| Pembuatan tautan massal OneLink | Buat ribuan URL pendek OneLink dengan cepat menggunakan parameter yang ditentukan dalam CSV | Pendek | -- | -- | 365 hari |
| <Anchor target="_blank" href="/marketers/id/docs/user-invite-attribution">SDK</Anchor> | Kampanye undangan (rujukan) pengguna | Pendek | -- | -- | 60 hari |
| <Anchor target="_blank" href="/marketers/id/docs/onelink-smart-script-overview">OneLink Smart Script</Anchor> | Kampanye web-ke-aplikasi seluler | Panjang | -- | -- | Tanpa TTL |
| <Anchor target="_blank" href="/marketers/id/docs/understand-onelink-short-vs-long-urls">Spreadsheet</Anchor> | Buat ribuan tautan khusus OneLink dengan menerapkan rumus Anda sendiri | Panjang | -- | -- | Tanpa TTL |

</Accordion>

<div id="can-onelink-custom-links-open-the-app-from-a-browser" />

<Accordion title="Bisakah tautan khusus OneLink membuka aplikasi dari browser?">

**Ya,** tetapi ketahuilah bahwa Tautan Universal dan Tautan Aplikasi hanya berfungsi saat diklik (misalnya, saat mengeklik tautan di halaman web atau email). **Merekatkan tautan di bilah alamat browser tidak akan meluncurkan aplikasi.** Uji tautan Anda dengan mengeklik URL; bukan dengan merekatkannya di kotak URL browser.

</Accordion>

<div id="why-doesnt-the-onelink-url-open-the-app-or-deep-link-existing-users" />

<Accordion title="Mengapa URL OneLink tidak membuka aplikasi atau menautkan langsung pengguna yang sudah ada?">

Terlepas dari niat terbaiknya, dalam beberapa kasus, URL OneLink Anda mungkin tidak melakukan penautan langsung yang dimaksud. Saat ini terjadi, alih-alih membuka aplikasi atau menautkan langsung ke aktivitas tertentu di dalam aplikasi, pengguna dialihkan ke app store atau ke halaman kesalahan.

Ada beberapa kemungkinan alasan untuk hal ini:

* **Aplikasi host:** Aplikasi tempat tautan atribusi Anda dibagikan (misalnya, WhatsApp, Gmail, WeChat) menggunakan metode yang berbeda untuk mengaktifkan tautan yang diklik, seperti browser internal berpemilik. Beberapa di antaranya diketahui memblokir semua tautan atribusi.
* **Browser:** Browser dan platform OS tertentu berperilaku berbeda dengan tautan. Di browser tertentu, misalnya, merekatkan tautan tidak akan berfungsi. Tautan tersebut harus benar-benar diklik.
* **Pembaruan OS:** Pembaruan OS baru (baik iOS maupun Android) dapat memperkenalkan bug tak terduga yang menghambat penautan langsung.
* **Perangkat:** Ponsel cerdas, tablet, laptop, dan perangkat lain yang menjalankan versi berbeda dari iOS, Android, Windows Mobile, dan sistem operasi lainnya dapat sangat bervariasi dalam menangani tautan atribusi.
* **Kesalahan konfigurasi:** Penggunaan <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#traits-and-limitations">karakter khusus</Anchor> dalam nilai penautan langsung memutus tautan.

Dua solusi untuk meningkatkan pengalaman pengguna adalah Fallback URL dan penautan langsung paksa.

#### URL fallback

URL fallback mengarahkan pengguna ke halaman web tertentu jika membuka aplikasi atau penautan langsung gagal karena alasan apa pun. **Peringatan!** Mereka juga mengirim pengguna tanpa aplikasi Anda terinstal ke URL fallback, bukan ke toko aplikasi yang benar. Jadi, pastikan untuk hanya menggunakan opsi ini jika Anda menargetkan ulang pengguna dengan aplikasi yang sudah terinstal.

Untuk menerapkan URL fallback, di templat OneLink atau pengaturan link khusus, atur perilaku tautan saat aplikasi tidak diinstal untuk mengalihkan ke URL lain.

[![different_url.png](https://files.readme.io/6e15b343cb778a0ab4e76c1be4a6bf3cd21ad675f9a64c521a61a4756a580a01-30192900484625.png)](https://files.readme.io/6e15b343cb778a0ab4e76c1be4a6bf3cd21ad675f9a64c521a61a4756a580a01-30192900484625.png)

Menggunakan pengaturan ini menambah `af_ios_url` dan `af_android_url` sebagai parameter tujuan untuk fallback, yang akan menyebabkan pengguna iOS dialihkan ke halaman yang ditentukan oleh `af_ios_url` dan pengguna Android diarahkan ke halaman yang ditentukan oleh`af_android_url`.

> 📄 **Contoh**
>
> Pertimbangkan, misalnya, URL OneLink berikut:
>
> ```http
> https://go.onelink.ly/qwerty?pid=source&af_dp=greatapp%3A%2F%2F&af_ios_url=www.yoursite.com/ios-bonus
> &af_android_url=www.yoursite.com/android-bonus
> ```
>
> Pengguna iOS dan Android yang mengeklik tautan ini harus ditautkan langsung ke dalam aplikasi. Namun, saat penautan langsung gagal, pengguna dialihkan sebagai berikut:
>
> * iOS: www.yoursite.com/ios-bonus
> * Android: www.yoursite.com/android-bonus

> 📘 **Catatan**
>
> * Jika Anda menyertakan simbol tagar (#) sebagai bagian dari nilai parameter di URL, Anda perlu menyandikannya.
> * Saat pengalihan terjadi, parameter URL OneLink melewati halaman tujuan yang ditentukan oleh `af_ios_url` atau `af_android_url`. Untuk mencegah perilaku ini, tambahkan parameter `af_param_forwarding=false` ke OneLink.

#### Penautan langsung yang dipaksakan

Tautan langsung paksa memungkinkan Anda menggunakan skema URI sebagai cadangan untuk membuka aplikasi dan menautkan pengguna secara langsung.

Solusi ini berfungsi dengan baik untuk sebagian besar pengguna yang telah menginstal aplikasi. Namun, untuk iOS, menggunakan skema URI untuk membuka aplikasi memiliki keterbatasan dan Anda mungkin perlu menambahkan `af_force_deeplink=true` ke URL OneLink untuk memaksa penautan langsung ke aktivitas yang ditentukan dalam skema URI (parameter `af_dp`). Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/uri-scheme-fallback-for-ios">cadangan skema URI untuk iOS.</Anchor>

</Accordion>

<div id="why-does-my-onelink-url-open-a-blank-page-in-chrome" />

<Accordion title="Mengapa URL OneLink saya membuka halaman kosong di Chrome?">

Pastikan Anda tidak menggunakan tag  HTML yang menyertakan atribut `target`. Jika URL OneLink ditempatkan di dalam tag  dengan atribut `target="_blank"`, itu membuka halaman kosong di Chrome (di iOS dan Android) dan pengguna tidak diarahkan ke App Store atau ke Google Play.

</Accordion>

<div id="can-i-use-onelink-for-redirection-on-brave" />

<Accordion title="Bisakah saya menggunakan OneLink untuk pengalihan di Brave?">

Ya. Namun, di Android, saat pengguna mengeklik tautan OneLink di browser Brave, penautan langsung yang ditunda tidak berfungsi. Dan di iOS, setelah pengguna mengeklik, mereka melihat layar kosong, dan penautan langsung yang ditunda hanya berfungsi jika mereka kemudian melakukan sesuatu di layar kosong, misalnya, menggulir, atau mengetuk.

</Accordion>

<div id="do-onelink-custom-links-take-longer-to-load-than-other-links" />

<Accordion title="Apakah tautan khusus OneLink membutuhkan waktu lebih lama untuk dimuat daripada tautan lainnya?">

**Tidak.** Tautan khusus OneLink tidak menambahkan pemrosesan atau waktu muat tambahan untuk berfungsi dengan baik dan mengarahkan pengguna sesuai kebutuhan. Mereka sama cepatnya dengan tautan AppsFlyer lainnya.

</Accordion>

<div id="how-can-i-record-the-cost-per-install-when-using-onelink" />

<Accordion title="Bagaimana cara mencatat biaya per penginstalan saat menggunakan OneLink?">

Mengaktifkan **Aktifkan biaya per penginstalan** (di bawah **Parameter lanjutan**) memungkinkan Anda untuk menerapkan nilai CPI tertentu ke setiap penginstalan yang berasal dari tautan.

Pilih mata uang, kemudian**nilai yang HANYA berisi angka** (hingga 4 digit angka desimal) untuk mewakili CPI.  Ini menambahkan parameter af\_cost\_currency dan af\_cost\_value ke tautan.

> 📄 **Contoh**
>
> Biaya kampanye SMS adalah $20 per 1000 pesan (CPM). Pengalaman menunjukkan bahwa kampanye Anda mencapai rasio konversi 5%, yang berarti CPI turunannya adalah $0,40. Menetapkan biaya per penginstalan ke 0,40 USD memungkinkan Anda untuk mengukur ROI akhir dari kampanye SMS.

Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview">mengukur biaya dan ROI</Anchor>.

</Accordion>

<div id="how-can-i-prevent-parameter-forwarding-on-redirections" />

<Accordion title="Bagaimana saya bisa mencegah penerusan parameter pada pengalihan?">

`af_r`,`af_ios_url`,`af_android_url`, dan `af_web_dp` transfer parameter dari tautan atribusi atau OneLink ke halaman yang dialihkan. Untuk mencegah perilaku ini, tambahkan `af_param_forwarding=false` ke tautan atribusi.

</Accordion>

<div id="how-can-i-remove-appsflyer-pid-and-c-parameters-when-forwarding-while-keeping-all-other-parameters-on-redirection-urls" />

<Accordion title="Bagaimana cara menghapus parameter PID dan C AppsFlyer saat meneruskan sambil menyimpan semua parameter lain di URL pengalihan?">

Dalam beberapa kasus, Anda mungkin memiliki URL dengan beberapa PID. Ini terjadi karena AppsFlyer menambahkan parameter PID dan C ke URL pengalihan dan klien juga dapat menambahkan parameter PID mereka sendiri. Misalnya, 'ID produk' mungkin 'pid' di URL situs web klien.

Biasanya, menambahkan `af_param_forwarding=false` ke tautan atribusi menghapus semua parameter.

Namun, jika tautan diklik dari desktop, klien mungkin menginginkan parameter CRM penting tetap ada. Untuk menghapus hanya parameter AppsFlyer PID dan C dan menyimpan semua parameter lainnya, tambahkan `af_base_params_forward=false` ke tautan atribusi.

</Accordion>

<div id="are-singleplatform-custom-links-still-available" />

<Accordion title="Apakah tautan khusus platform tunggal masih tersedia?">

OneLink sekarang menjadi satu-satunya metode yang didukung untuk membuat tautan atribusi khusus untuk media yang dimiliki.

Sebelumnya, pemilik aplikasi juga dapat menggunakan tautan khusus platform tunggal (khusus aplikasi) tanpa menggunakan OneLink. Metode ini sudah tidak digunakan lagi, dan tautan khusus baru hanya dapat dibuat berdasarkan templat OneLink.

Namun, jika Anda memiliki tautan khusus platform tunggal versi lawas, tautan tersebut masih berfungsi seperti biasa. Anda juga dapat melihat dan mengedit tautan lawas dengan mengeklik **Lihat tautan platform tunggal lawas** di sudut kanan atas halaman tautan khusus OneLink.

</Accordion>

<div id="can-i-change-the-short-url-id-after-saving-a-link" />

<Accordion title="Bisakah saya mengubah ID URL pendek setelah menyimpan tautan?">

**Tidak,** ID URL pendek hanya dapat disetel pada saat tautan dibuat.

</Accordion>

<div id="can-i-wrap-and-shorten-onelink-custom-links" />

<Accordion title="Bisakah saya membungkus dan memperpendek tautan khusus OneLink?">

**Pemendek tautan eksternal atau membungkus tautan khusus OneLink Anda akan merusak fungsi pembuka aplikasi dari Tautan Universal dan Tautan Aplikasi.**

Untuk mengaktifkan Tautan Universal atau Tautan Aplikasi, OS perlu mengenali domain URL yang terkait dengan aplikasi, dan segala jenis pembungkus eksternal, pemendekan, atau pengalihan ke tautan yang menghadap pengguna membuat hal ini tidak mungkin. Ini termasuk menggunakan bit.ly, tautan bermerek non-AppsFlyer, atau Penyedia Layanan Email (ESP) dengan pencatatan klik yang diaktifkan.

**Untuk menggabungkan atau menyingkat tautan dengan cara yang memungkinkan pengarahan berfungsi dengan baik:**

* Gunakan URL singkat yang dibuat oleh AppsFlyer saat Anda membuat tautan khusus OneLink (bukan penyingkat eksternal seperti bit.ly).  
  **Tip**! Buat URL lebih pendek lagi dengan membuat domain bermerek pendek di tautan Anda. Dan jika Anda membuat tautan di UI AppsFlyer, Anda dapat mengedit ID URL menjadi sesingkat mungkin. Contoh: https://brand.com/a1b2/a (di mana **brand.com** adalah domain bermerek Anda, **a1b2** adalah ID templat yang selalu 4 karakter, dan **a** adalah ID URL, yang dapat diedit hingga 1 karakter.   
  Manfaat:
  * Metode ini berfungsi karena menggunakan subdomain OneLink yang dikonfigurasi di templat OneLink.
  * Hal ini memungkinkan Anda untuk mengubah parameter dengan cepat, termasuk pengaturan penautan langsung, bahkan setelah mendistribusikan tautan atribusi ke calon pelanggan Anda.
  * Hal ini menghitung semua klik dari perangkat seluler di dashboard AppsFlyer, sehingga Anda tidak perlu memeriksa layanan lain.
  * Bagian terakhir dari URL singkat dapat disesuaikan untuk menjadikannya <Anchor target="_blank" href="/marketers/id/docs/brand-onelink-with-your-domain">domain bermerek</Anchor>.
* Gunakan <Anchor target="_blank" href="https://dev.appsflyer.com/docs/initial-setup-2#procedures-for-uri-scheme">skema URI</Anchor> sebagai cadangan untuk membuka aplikasi saat Tautan Universal dan Tautan Aplikasi gagal, dan tambahkan parameter berikut ke tautan: `af_force_deeplink=true`.
* Lihat opsi untuk [bekerja dengan ESP](/docs/onelink-troubleshooting-and-faq#can-i-use-onelink-custom-links-in-emails).

</Accordion>

<div id="can-i-use-onelink-custom-links-in-emails" />

<Accordion title="Bisakah saya menggunakan tautan khusus OneLink di email?">

**Ya,** tetapi pertimbangan khusus diperlukan saat Anda bekerja dengan Penyedia Layanan Email (ESP). Untuk menghitung klik yang dilakukan, ESP membungkus semua tautan yang ditempatkan di dalam email. Ini merusak alur pembukaan/penautan langsung aplikasi untuk pengguna yang mengeklik URL.

Untuk mencegahnya, gunakan salah satu solusi opsional berikut:

* Nonaktifkan pencatatan klik di konfigurasi ESP Anda.  
  **(Tip: Ini umumnya merupakan solusi termudah.)**
* Paksa aplikasi terbuka dengan skema URI yang ditentukan dalam parameter `af_dp` dengan menambahkan tanda `af_esp=true` ke tautan atribusi. Solusi ini berfungsi dengan baik untuk pengguna yang telah menginstal aplikasi.
* Gunakan ESP yang mendukung solusi Appsflyer  untuk pembukaan aplikasi dan penautan langsung dengan Tautan Universal. <Anchor target="_blank" href="/marketers/id/docs/email-service-provider-esp-integration-guide">Pelajari lebih lanjut</Anchor>.

</Accordion>

<div id="how-do-users-get-redirected-to-their-regional-app-store" />

<Accordion title="Bagaimana cara pengguna dialihkan ke app store regional mereka?">

OneLink mengalihkan pengguna ke app store regional yang benar berdasarkan alamat IP mereka.

</Accordion>

<div id="why-isnt-my-onelink-url-redirecting-users-to-the-specified-domain" />

<Accordion title="Mengapa URL OneLink saya tidak mengalihkan pengguna ke domain yang ditentukan?">

Periksa apakah Anda telah mengaktifkan Alihkan daftar yang diizinkan di AppsFlyer. Jika Anda telah mengaktifkannya, domain atau subdomain URL web yang diinginkan harus dicantumkan. <Anchor target="_blank" href="/marketers/id/docs/set-up-your-api-allowlist#redirect-allowlists">Pelajari lebih lanjut Alihkan daftar yang diizinkan</Anchor>

</Accordion>

<Accordion title="Mengapa saya mendapatkan eror 'Aplikasi yang Anda cari tidak tersedia'?">

Munculnya eror 'Aplikasi yang Anda cari tidak tersedia' alih-alih dialihkan ke Google Play karena:

* Aplikasi Anda saat ini dalam status 'Tertunda' di Google Play. Untuk menghindari pesan eror yang disebutkan di atas, atur pengalihan tautan agar mengarah ke URL web, bukan ke Google Play. Setelah aplikasi disetujui, pengalihan dapat diubah kembali ke Google Play. Perubahan konfigurasi ini dilakukan pada <Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template#create-a-onelink-template-with-redirection-logic-for-new-app-users">halaman templat tautan</Anchor>.
* Jika aplikasi Anda tersedia secara eksklusif melalui toko pihak ketiga, masalah mungkin timbul karena aplikasi ditugaskan ke status Google Play yang salah di AppsFlyer. Untuk mengatasi masalah ini, Anda <Anchor target="_blank" href="/marketers/id/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app">harus mengatur status Google Play-nya ke Diterbitkan di luar toko</Anchor> di halaman Pengaturan Aplikasi Saya.

</Accordion>

<div id="can-i-manually-switch-between-the-branded-domain-and-its-onelink-subdomain-in-an-existing-link" />

<Accordion title="Bisakah saya beralih secara manual antara domain bermerek dan subdomain OneLink-nya di tautan yang sudah ada?">

Ya - Jika domain bermerek dan subdomain OneLink dipetakan dengan benar. Lihat: <Anchor target="_blank" href="/marketers/id/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer">Menyiapkan Domain Bermerek di AppsFlyer</Anchor>

**Contoh**:  
Subdomain OneLink: **demo.onelink.me**  
ID Templat: **A1r4**  
Domain bermerek yang dipetakan ke subdomain [**demo.onelink.me**](http://demo.onelink.me) adalah:

* **app.simulatorapp.com**
* **click.simulatorapp.com**

Anda membuat tautan bermerek berikut di UI OneLink:  
**app.simulatorapp.com/A1r4/simulationlink**  
Anda dapat mengganti tautan bermerek di atas dengan tautan domain bermerek lainnya atau tautan subdomain OneLink.  
Tautan berikut secara fungsional identik dan berfungsi sama di mana saja:

* app.simulatorapp.com/A1r4/simulationlink
* demo.onelink.me/A1r4/simulationlink
* click.simulatorapp.com/A1r4/simulationlink

</Accordion>

### Pertanyaan umum parameter OneLink

<div id="what-parameters-are-mandatory-for-onelink-custom-links" />

<Accordion title="Parameter apa yang wajib untuk tautan khusus OneLink?">

Hanya parameter sumber media (**pid**) yang wajib.

</Accordion>

<div id="can-parameters-be-appended-to-the-short-url" />

<Accordion title="Bisakah parameter ditambahkan ke URL pendek?">

**Ya,** parameter apa pun dapat ditambahkan ke URL pendek.

**Penting!** Parameter yang ditambahkan ke URL pendek tidak menggantikan parameter di dalam tautan.

> 📄 **Contoh**
>
> * Anda membuat tautan khusus OneLink dengan output berikut:
>   * **URL Panjang:** https://onelink-sim.onelink.me/Il2C?pid=training&c=peaches
>   * **URL Pendek:** https://onelink-sim.onelink.me/Il2C/70e6d165
> * Anda menambahkan parameter berikut ke URL pendek: https://onelink-sim.onelink.me/Il2C/70e6d165?c=bananas&af_adset=fruits
> * Parameter **af\_adset=fruits** yang ditambahkan ke URL pendek berfungsi efektif untuk atribusi. Namun, parameter c=banana **tidak efektif**  karena sudah ada parameter **c** di URL panjang.

</Accordion>

<div id="what-custom-media-source-names-can-i-use" />

<Accordion title="Apa nama sumber media khusus yang dapat saya gunakan?">

Untuk media yang dimiliki, nama sumber media khusus dapat berupa apa saja. Namun, disarankan untuk tidak menggunakan *organik* sebagai nama sumber media khusus karena dapat memengaruhi integritas data atribusi.

Jika Anda menggunakan OneLink untuk media berbayar:

* Gunakan nilai **PID** cadangan mitra terintegrasi (yang diakhiri dengan **\_int**), sebagai nilai sumber media di tautan khusus OneLink. Jangan gunakan sumber media SRN seperti *googleadwords*atau*facebook*sebagai nama sumber media khusus. Hal ini dapat mempengaruhi integritas data atribusi.
* Pastikan mitra terintegrasi dengan AppsFlyer dan aktif (tombol **Aktifkan mitra** diaktifkan) untuk semua aplikasi yang diatur dalam templat OneLink.

</Accordion>

<div id="what-attribution-parameters-can-be-added-to-a-onelink" />

<Accordion title="Parameter atribusi apa yang dapat ditambahkan ke OneLink?">

Anda dapat menambahkan banyak parameter atribusi untuk memungkinkan Anda melakukan analisis penelusuran secara lebih mendetail.

| **Parameter atribusi** | **Deskripsi** | **Nama tautan parameter** |
| --- | --- | --- |
| **Kampanye** | Tetapkan nama kampanye untuk membandingkan kampanye berbeda di dalam sumber media yang dimiliki | c |
| **Adset** | Atur nama ad set untuk membandingkan ad set berbeda di dalam kampanye khusus dari sumber media yang dimiliki | af\_adset |
| **Nama Iklan** | Atur nama iklan untuk membandingkan materi iklan yang berbeda dalam pengaturan iklan/kampanye tertentu dari sumber media yang dimiliki | af\_ad |
| **Saluran** | Tetapkan nama kanal jika Anda ingin membandingkan lebih dari satu kanal distribusi untuk media milik Anda.<br /><br />Contoh: Jika Anda membagi pesan SMS antara dua penyedia layanan SMS, tentukan penyedia menggunakan parameter saluran. Nantinya, Anda bisa membandingkan tingkat konversi kedua penyedia tersebut. | af\_channel |
| **Parameter Pelanggan** | Gunakan salah satu dari 5 parameter pelanggan yang tersedia untuk memasukkan nilai yang berguna untuk analisis Anda.<br /><br />**Catatan:** Parameter ini diurai dan muncul dalam laporan data lengkap, yang membuatnya berguna untuk melakukan agregasi atau pemfilteran data. | af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5 |
| **Parameter Khusus** | Mirip dengan parameter pelanggan, Anda dapat menentukan bidang dengan nama dan nilai parameter apa pun. dan nama apa pun.<br /><br />Tidak seperti parameter pelanggan, parameter khusus tidak diuraikan dalam data lengkap; mereka muncul di laporan data lengkap hanya di kolom **url asli** . | Khusus  <br />(seperti yang Anda tentukan) |

Lihat informasi selengkapnya tentang  <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters">Parameter dan struktur tautan atribusi AppsFlyer</Anchor>.

</Accordion>

<div id="are-custom-parameters-added-to-onelink-custom-links-available-in-raw-data" />

<Accordion title="Apakah parameter khusus ditambahkan ke tautan khusus OneLink tersedia dalam data lengkap?">

**Ya.** Parameter khusus diteruskan ke kolom **url asli** dalam data lengkap dan dapat dilihat di sana. Mereka tidak memiliki kolom sendiri dalam data lengkap.

Untuk data yang diurai, gunakan parameter pelanggan `af_sub1-5`, yang masing-masing memiliki kolom terpisah dalam laporan data lengkap.

</Accordion>

<div id="are-parameter-names-case-sensitive" />

<Accordion title="Apakah nama parameter peka huruf besar/kecil?">

**Ya.** Pastikan Anda hanya menggunakan huruf kecil untuk parameter dan nilai Anda. Huruf besar atau kapitalisasi nama dan nilai parameter yang Tidak konsisten dapat menyebabkan kesalahan atau ketidaksesuaian data, baik di dashboard maupun di data lengkap.

</Accordion>

### Pertanyaan umum mitra terintegrasi

<div id="can-i-use-onelink-in-social-apps-unpaid" />

<Accordion title="Bisakah saya menggunakan OneLink di aplikasi media sosial (tidak berbayar)?">

Anda mungkin ingin menggunakan OneLink dalam postingan tidak berbayar di aplikasi media sosial karena pengguna potensial yang terpapar postingan semacam itu tidak dapat ditargetkan terlebih dahulu menurut perangkat mereka.

Sayangnya, batasan dan pembatasan Tautan Universal iOS yang ditetapkan oleh beberapa aplikasi media sosial memperumit penggunaan OneLink untuk pengenalan perangkat dasar, pengalihan dan atribusi, serta penautan langsung. Dalam kasus tertentu, Anda mungkin perlu menyiapkan halaman awal aplikasi media Sosial atau skema URI untuk mengalihkan atau menautkan langsung pengguna.

Tabel berikut merangkum kapan OneLinks dapat digunakan di aplikasi media sosial populer saat ini:

<table><thead><tr><th>Aplikasi Media Sosial</th><th>Pengguna Android tanpa aplikasi terinstal</th><th>penautan langsung Android</th><th>Pengguna iOS tanpa aplikasi terinstal</th><th>penautan langsung iOS</th></tr></thead><tbody><tr><td> <strong>Facebook</strong> (termasuk posting yang ditingkatkan)</td><td><span>✓\*\*<span>†</span><span>† </span></span></td><td><span>✓\*\*</span></td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Facebook Messenger</strong></td><td><span>✓\*\*<span>†</span><span>† </span></span></td><td> <span>✓\*\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Snapchat</strong></td><td><span>✓<span>†</span><span>† </span></span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Instagram</strong></td><td><span>✓<span>†</span><span>† </span></span></td><td><span>✓</span></td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>LinkedIn</strong></td><td><span>✓</span></td><td><span>✓\*\*</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td><strong>Reddit</strong></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td><strong>Slack</strong></td><td><span>✓</span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>X (sebelumnya Twitter)</strong></td><td><span>✓</span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>WeChat</strong></td><td><span>✓<span>† </span></span></td><td><span>✓<span>† </span> </span></td><td><span>✓\*</span></td><td><span>✓\*<span>† </span></span></td></tr><tr><td><strong>WhatsApp</strong></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="5"><p>\* Jika <a href="./onelink-troubleshooting-and-faq#which-operating-systems-allow-uri-schemes-to-open-the-app">skema URI</a>, atau halaman awal aplikasi media Sosial disiapkan. <strong>Catatan</strong>: Untuk Facebook dan Facebook Messenger, jika skema URI dan halaman arahan aplikasi Media Sosial diatur, halaman arahan aplikasi Media Sosial tidak ditampilkan.</p><p>\*\* Harus memiliki skema URI.</p><p><span>†</span> Pengguna mungkin diminta untuk membuka tautan dalam browser eksternal.</p><p><span>†</span><span>† </span><span><span>Batasan pengalihan tautan mendalam WebView aplikasi media sosial Android. Lihat detail <a href="./create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#android-social-apps-webview-deep-linking-redirection" target="_blank">di sini</a>.</span></span></p></td></tr></tbody></table>

</Accordion>

<div id="can-i-use-onelink-with-ad-networks-paid" />

<Accordion title="Dapatkah saya menggunakan OneLink dengan jaringan iklan (berbayar)?">

**Ya,** tetapi perhatikan bahwa OneLink terutama digunakan dengan media yang dimiliki, bukan dengan jaringan iklan.  Ini karena jaringan iklan biasanya beriklan di aplikasi (yang berarti mereka mengetahui platform pengguna, ID perangkat, dan sebagainya), tautan atribusi khusus aplikasi dan platform sudah cukup, jadi menggunakan OneLink tidak diperlukan. Namun, untuk kasus di mana jaringan iklan tidak mengetahui platform pengguna sebelumnya (misalnya, ketika mereka sendiri menjalankan kampanye email atau SMS), OneLink dapat menjadi solusinya.

> 🚧 **Penting!**
>
> Saat Anda menggunakan OneLink dengan jaringan iklan, Anda harus menggunakan URL panjang OneLink.

**Untuk menyiapkan OneLink untuk jaringan iklan mitra:**

* Ikuti <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#attribution-link-tab">instruksi tautan atribusi jaringan iklan</Anchor>, dan pilih **Gunakan OneLink** saat diminta.

Setelah semua parameter untuk Android dan iOS ditambahkan dengan benar, saat tautan khusus OneLink diklik dan pengguna dialihkan ke platform yang tepat, parameter yang diperlukan dikirim ke jaringan dalam postback setelah pengguna menginstal.

> 📄 **Contoh**
>
> ```http
> https://greatapp.onelink.me/3287867539?pid=network_int&c=email&
> idfa{$IDFA}&gaid={$GAID}&clickid=$SITEID&
> af_sub1=[pixel_code]&af_sub2=[creative]
> ```
>
> Jaringan tersebut menggunakan parameter IDFA atau GAID sesuai dengan platform perangkat klien dan mengabaikan parameter lainnya.

</Accordion>

<div id="how-can-i-solve-the-ios-applaunching-issue-from-social-media-apps" />

<Accordion title="Bagaimana saya bisa mengatasi masalah peluncuran aplikasi iOS dari aplikasi media sosial?">

Facebook dan aplikasi media sosial lainnya terkadang memblokir Tautan Universal iOS dari membuka aplikasi. <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Halaman arahan aplikasi sosial</Anchor> adalah solusi yang disarankan untuk masalah peluncuran aplikasi ini.

Jika Anda tidak ingin menggunakan halaman arahan aplikasi Media Sosial, Anda dapat menggunakan skema URI sebagai metode cadangan. Catatan, bagaimanapun:

* Menggunakan skema URI sebagai cadangan tunduk pada batasan berbasis iOS.
* Untuk banyak browser, termasuk Safari, Anda harus menambahkan `af_force_deeplink=true` parameter ke URL untuk menggunakan skema URI sebagai cadangan. <Anchor target="_blank" href="/marketers/id/docs/uri-scheme-fallback-for-ios">Pelajari lebih lanjut</Anchor>.

</Accordion>

<div id="can-i-use-onelink-on-instagram" />

<Accordion title="Bisakah saya menggunakan OneLink di Instagram?">

**Ya,** tetapi perhatikan batasan berikut:

* Dikarenakan cara Instagram merender teks pada postingan halaman, tautan menjadi tidak dapat diklik saat dimasukkan ke dalam caption postingan.
* Pembukaan aplikasi dan penautan langsung ke aplikasi Android didukung tanpa pertimbangan khusus. Namun, Instagram tidak mendukung pembukaan aplikasi dan penautan langsung ke aplikasi iOS. Untuk mengatasi masalah ini, Anda dapat memilih salah satu dari dua pendekatan:

  * **Disarankan:** Mengonfigurasi <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">halaman arahanl aplikasi Media Sosial</Anchor>. Templat Clustered Poster dan ShowAndTell berfungsi paling baik. Selain halaman awal media Sosial, kami merekomendasikan pengaturan skema URI di templat OneLink Anda.
  * Gunakan skema URI dan [tautan langsung paksa](/docs/onelink-troubleshooting-and-faq#penautan-langsung-yang-dipaksakan) saat menggunakan OneLink di Instagram. Pastikan untuk mengingat pertimbangan berikut ini saat menggunakan `af_force_deeplink=true` dengan OneLink di Instagram:  

| Aplikasi terpasang? | Klik memiliki  af\_force\_deeplink=true? | Hasil |
| --- | --- | --- |
| Tidak | Ya | Klik membuka app store |
| Tidak | Tidak | Klik membuka app store |
| Ya | Ya | Klik membuka aplikasi |
| Ya | Tidak | Klik membuka app store |

</Accordion>

<div id="can-i-use-onelink-for-redirection-on-wechat" />

<Accordion title="Bisakah saya menggunakan OneLink untuk pengalihan di WeChat?">

WeChat mengganti tautan langsung Android dan iOS dan mengalihkan pengguna ke halaman web. Dari halaman web, pengguna harus mengeklik tombol **Opsi** dan memilih untuk membuka halaman di browser. Akibatnya, pengguna akan mengalami pengalaman yang kurang bagus yang meningkatkan kemungkinan mereka berhenti di corong konversi.

Untuk mengatasi ini, OneLink mengenali klik di WeChat dan memuat halaman awal khusus dengan menginstruksikan pengguna untuk mengeklik tombol opsi lalu mengeklik **Buka di Browser**. Ini, pada gilirannya, membuka URL pengalihan yang ditentukan dalam pengaturan templat OneLink.

![WeChat_a.jpg](https://files.readme.io/49c03a10d458f6ce71fd6448e922294682ac9239775534c6264c29151ec1ea6d-30192900489105.jpg)

Jika bahasa WeChat pengguna yang didaftarkan adalah bahasa Tionghoa, OneLink akan menghasilkan versi laman awal yang dilokalkan:

![WeChat_b.jpg](https://files.readme.io/502ef821a122459ab991f2a507c720f25fcac7129eb647a01290e8cabfa7a34e-30192887085841.jpg)

</Accordion>

<div id="why-are-android-users-with-the-app-installed-being-redirected-to-a-web-url-and-not-into-the-app-when-they-click-a-link-on-facebook-webview" />

<Accordion title="Mengapa pengguna Android dengan aplikasi terinstal dialihkan ke URL web dan bukan ke aplikasi saat mereka mengeklik tautan di tampilan web Facebook?">

Membuka aplikasi dan menautkannya langsung dari iklan di Facebook biasanya dimungkinkan. Namun, jika kondisi berikut berlaku, Facebook tidak dapat membuka aplikasi untuk pengguna aplikasi yang ada dari URL OneLink. Sebagai gantinya, semua pengguna, termasuk yang memiliki aplikasi, dikirim ke URL yang ditentukan dalam templat OneLink atau dalam nilai parameter **af\_android\_url**, **af\_r**, atau **af\_custom\_android\_url** :

* Pengguna memiliki perangkat seluler Android.
* Tautan diklik pada aplikasi Facebook.
* Tautan mengarah ke halaman HTML yang terbuka di tampilan web Facebook (situs atau halaman awal aplikasi media sosial).
* Halaman HTML berisi tautan dengan parameter**af\_dp**(dengan skema URI) dan pengaturan pengalihan URL di templat OneLink atau di parameter (salah satu dari **af\_android\_url**, **af\_r**, atau **af\_custom\_android\_url**).

</Accordion>

### Pertanyaan Umum tentang Pengujian

<div id="how-can-i-ab-test-the-social-app-landing-page" />

<Accordion title="Bagaimana cara saya melakukan pengujian A/B terhadap halaman awal aplikasi media sosial?">

<Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Halaman awal aplikasi media Sosial</Anchor> memberi pengguna pengalaman peluncuran aplikasi yang mulus saat menggunakan OneLink di aplikasi jaringan sosial. Anda mungkin khawatir menambahkan langkah ke perjalanan akan menurunkan rasio konversi. Namun kenyataannya, tanpa halaman awal, perjalanan pengguna umumnya terputus-putus, menghasilkan tingkat konversi yang sangat rendah.

Jika Anda tidak yakin sepenuhnya, mengapa tidak mengujinya?

<Anchor target="_blank" href="/marketers/id/docs/create-a-b-tests">Lakukan Pengujian A/B</Anchor> pada tautan khusus Anda di aplikasi media sosial, dengan dan tanpa halaman awal aplikasi media Sosial.

**Untuk melakukan pengujian A/B pada halaman awal aplikasi media Sosial:**

1. <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Buat tautan OneLink</Anchor> (disebut Link1) untuk digunakan dengan aplikasi media sosial. Jangan mengatur halaman awal aplikasi media Sosial untuk tautan ini.
2. Tambahkan parameter atribusi**af\_adset**.
3. Tambahkan parameter atribusi **af\_ad** dengan nilai "no lp".
4. Uji link1 di luar aplikasi media sosial, dan verifikasi kerja tautan dan luncurkan aplikasi Anda dengan baik.
5. Gandakan Link1 dan beri nama Link2.
6. Ubah nilai parameter atribusi **af\_ad** ke "using lp".
7. <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Buat halaman awal aplikasi media Sosial</Anchor> hanya untuk Link2.
8. Publikasikan 2 postingan berbeda dalam aplikasi media sosial yang **sama**, menggunakan Link1 dan Link2.  
   Jangan khawatir tentang perbedaan jumlah klik yang dihasilkan setiap tautan. KPI yang penting adalah rasio konversi akhir dari setiap tautan.
9. **Periksa hasil pengujian A/B setelah lalu-lintas cukup dibuat.**
   1. Buka dashboard ikhtisar AppsFlyer dan gulir ke bawah ke tabel **Aggregated performance report** (Laporan kinerja agregat).
   2. Link1 dan Link2 memiliki media source, kampanye, dan nama adset yang sama. Telusuri lebih detail ke adset tertentu.
   3. Bandingkan rasio konversi (dan KPI lain) dari pengguna yang mengklik Link1 atau Link2.

</Accordion>

<div id="how-can-i-bypass-the-app-selection-dialog" />

<Accordion title="Bagaimana saya bisa melewati dialog pemilihan aplikasi?">

Jika Anda melihat dialog pilihan aplikasi saat menguji OneLink, pastikan Anda <Anchor target="_blank" href="https://developer.android.com/studio/publish/app-signing">menandatangani aplikasi Anda</Anchor> bahkan jika aplikasi ini merupakan <Anchor target="_blank" href="https://developer.android.com/studio/publish/app-signing#debug-mode">aplikasi debug.</Anchor> Sertifikat yang Anda gunakan untuk menandatangani aplikasi adalah sertifikat yang sama dengan yang Anda gunakan untuk <Anchor target="_blank" href="https://dev.appsflyer.com/docs/initial-setup-for-deep-linking-and-deferred-deep-linking#generating-a-sha256-fingerprint">membuat sidik jari SHA256</Anchor> saat mengonfigurasi OneLink untuk Tautan Aplikasi.

</Accordion>

### Pertanyaan umum tentang tautan langsung

<div id="what-deep-linking-methods-should-be-implemented" />

<Accordion title="Metodepenautan langsung apa yang harus diterapkan?">

Pengembang Anda harus menerapkan metode unified deep linking (UDL) untuk penautan langung. Lihat <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">instruksi lengkap kami untuk penautan langsung</Anchor>.

Tautan Universal iOS dan Tautan Aplikasi Android adalah **metode peluncuran aplikasi, yang sebenarnya bukan pengguna tautan langsung** (mengirim mereka ke konten tertentu dalam aplikasi). Metode skema URI dapat meluncurkan aplikasi dan menautkan langsung pengguna (melalui parameter tautan khusus **af\_dp**), tetapi ini hanya boleh dikonfigurasikan untuk peluncuran aplikasi. Penggunaan utamanya adalah sebagai metode cadangan untuk Tautan Universal dan Tautan Aplikasi dan untuk pengguna yang meluncurkan aplikasi dengan versi OS Android sebelum 6.0.

Setelah aplikasi diluncurkan menggunakan salah satu metode ini, SDK AppsFlyer menyediakan **deep\_link\_value** yang ditentukan di tautan atribusi khusus. Nilai ini harus dikirimkan melalui metode UDL yang diterapkan oleh pengembang Anda.

</Accordion>

<div id="can-a-uri-scheme-af_dp-parameter-be-used-for-deep-linking" />

<Accordion title="Dapatkah skema URI (af_dp parameter) digunakan untuk penautan langsung?">

**Ya,** tetapi ini tidak direkomendasikan. Idealnya, Anda harus menggunakan **deep\_link\_value** untuk penautan langsung, dan skema URI sebagai metode cadangan untuk meluncurkan aplikasi tanpa penautan langsung (melalui parameter **af\_dp**). Namun, jika Anda sudah menyiapkan skema URI untuk menautkan langsung, dengan parameter tambahan yang digabungkan sebagai bagian dari jalur URI (misalnya, greatapp://param1/param2), Anda tidak perlu mengubah konfigurasi atau kode Anda yang sudah ada; skema URI akan terus bekerja. 

**Praktik terbaik untuk menambahkan parameter khusus, adalah melalui halaman pengaturan tautan khusus**.

</Accordion>

### Pertanyaan umum iOS 14

<div id="does-onelink-deep-linking-work-for-ios-14" />

<Accordion title="Apakah tautan langsung OneLink berfungsi untuk iOS 14?">

Tidak ada dampak pengalaman pengguna terhadap pengguna iOS 14 yang ditautkan secara langsung dari kampanye di jaringan iklan dan media yang dimiliki menggunakan metode UDL. Metode lawas dapat menghambat penautan langsung.

Untuk tujuan atribusi/pelaporan, AppsFlyer menggunakan IDFA atau IDFV jika tersedia. Jika tidak ada IDFA atau IDFV, pemodelan probabilistik dapat digunakan. Dimulai dari iOS 14.5+, pemodelan probabilistik terbatas pada konteks media yang dimiliki, promosi silang, dan alur web-ke-aplikasi yang disetujui.

</Accordion>

<div id="does-onelink-deferred-deep-linking-work-for-ios-14" />

<Accordion title="Apakah penautan langsung yang tertunda OneLink berfungsi untuk iOS 14?">

Tidak ada dampak pengalaman pengguna terhadap pengguna iOS 14 yang ditunda dalam tautan langsung dari kampanye di jaringan iklan dan media yang dimiliki menggunakan metode UDL. Metode lawas dapat menghambat penautan langsung yang tertunda.

Untuk tujuan atribusi/pelaporan, AppsFlyer menggunakan IDFA atau IDFV jika tersedia. Jika tidak ada IDFA atau IDFV, pemodelan probabilistik dapat digunakan. Dimulai dari iOS 14.5+, pemodelan probabilistik terbatas pada konteks media yang dimiliki, promosi silang, dan alur web-ke-aplikasi yang disetujui. Kami menyarankan pelanggan yang ingin menerapkan penautan langsung yang tertunda dari jaringan iklan dan media yang dimiliki untuk menggunakan AppsFlyer iOS SDK V6.1.0+ untuk memungkinkan persetujuan ATT (jika diperlukan), mengurangi dampak atribusi, dan mendapatkan keuntungan dari waktu respons yang lebih cepat.

</Accordion>

<div data-zendesk-anchors="onelink-troubleshooting-guide=panduan-pemecahan-masalah-onelink 01H7WPYJV9CQ1J6J3PFCEQFGB0=panduan-pemecahan-masalah-onelink onelink-frequently-asked-questions=onelink-pertanyaan-yang-sering-diajukan 01H7WPYJV9H52P659N8JPRX2TY=onelink-pertanyaan-yang-sering-diajukan onelink-template-faq=pertanyaan-umum-templat-onelink 01H7WPYJV9TJRKHFZ77DFMKDDG=pertanyaan-umum-templat-onelink which-method-should-i-use-for-opening-apps%E2%80%94universal-links-app-links-or-uri-schemes=which-method-should-i-use-for-opening-apps-universal-links-app-links-or-uri-schemes 01H7WPYJV9JQG66S3K7TRHMFHA=which-method-should-i-use-for-opening-apps-universal-links-app-links-or-uri-schemes 01H7WPYJV9TV402AGAAGYARATW=catatan deep-linking=penautan-langsung 01H7WPYJV9JSQ5FV73YCE3H5AF=penautan-langsung 01H7WPYJV9CMQAQZ56P5P2MDBV=which-operating-systems-allow-uri-schemes-to-open-the-app 01H7WPYJV975A2YS61MQM1WX4W=do-i-need-to-update-the-app-after-ios-universal-links-and-android-app-links-setup 01H7WPYJV9GPXDP0KSQEPZXJCH=can-i-redirect-existing-users-to-a-web-page-instead-of-the-app 01H7WPYJV9A266QMK2J1K2AQXR=can-i-redirect-tablet-users-to-a-different-app-or-url-then-mobile-app-users 01H7WPYJV9DCVNRR3NNF7JMR0D=can-i-assign-an-app-to-multiple-onelink-templates 01H7WPYJV90RVHSAWA2YHBNNHA=can-i-delete-a-onelink-template 01H7WPYJV9RPNG3Z94630B789K=can-i-change-the-subdomain-in-a-onelink-template 01H7WPYJV9C0H3ZH6F6F3E43WH=can-the-domainsubdomain-of-a-onelink-template-be-applied-to-the-template-id-of-another-template 01H7WPYJV9246X8821B943N9AD=can-i-use-the-same-subdomain-for-more-than-one-template 01H7WPYJVAFBS0Y56NWN8M979B=how-can-i-redirect-desktop-users 01H7WPYJVA6PWA88VD8V0B3M74=tip 01H7WPYJVAB57R0VQAS7C0D9NK=how-can-i-redirect-chrome-os-users onelink-link-faq=pertanyaan-umum-tautan-onelink 01H7WPYJVAPNYAQ1SH4FBX4Z9F=pertanyaan-umum-tautan-onelink 01H7WPYJVAEQQDSJ298M8JV361=does-onelink-work-without-the-appsflyer-sdk 01H7WPYJVA8XASRX9X3QVAWYS9=what-methods-are-available-for-creating-onelink-custom-links 01H7WPYJVATBVVMEPNAVBW9ZFZ=can-onelink-custom-links-open-the-app-from-a-browser 01H7WPYJVAWJ9BFYBXM6DJ3V22=why-doesnt-the-onelink-url-open-the-app-or-deep-link-existing-users fallback-urls=url-fallback 01H7WPYJVACCGVJD1Z7ZPVG2SQ=url-fallback 01H7WPYJVAHXE4M12X94T9C7A5=contoh 01H7WPYJVAEMX54GZAX166FPS7=catatan-1 forced-deep-linking=penautan-langsung-yang-dipaksakan 01H7WPYJVA1W3HYYJJFQM01136=penautan-langsung-yang-dipaksakan 01H7WPYJVAWSD03E141SZEN2J9=why-does-my-onelink-url-open-a-blank-page-in-chrome 01H7WPYJVAV93G4EGDH2A91XMP=can-i-use-onelink-for-redirection-on-brave 01H7WPYJVAJQ6FKWDK8MNZAZT3=do-onelink-custom-links-take-longer-to-load-than-other-links 01H7WPYJVAX7P2YCBV1K1DCGEJ=how-can-i-record-the-cost-per-install-when-using-onelink 01H7WPYJVAEFX5306YA4GA45FW=contoh-1 01H7WPYJVAQZJQYX3H5V8YTC27=how-can-i-prevent-parameter-forwarding-on-redirections 01H7WPYJVAYVK3A77Q35H1ENKF=how-can-i-remove-appsflyer-pid-and-c-parameters-when-forwarding-while-keeping-all-other-parameters-on-redirection-urls 01H7WPYJVA89118V5Y2DSM67Y4=are-singleplatform-custom-links-still-available 01H7WPYJVANDKXGFKYXZ6CKHSF=can-i-change-the-short-url-id-after-saving-a-link 01H7WPYJVAC2WXXY43WEYKVPYP=can-i-wrap-and-shorten-onelink-custom-links 01H7WPYJVANTMSMGZ6VP36DTV1=can-i-use-onelink-custom-links-in-emails 01H7WPYJVAE0TSRPPTD21X9Q4V=how-do-users-get-redirected-to-their-regional-app-store 01H7WPYJVA4W7YFMQD4HEE313P=why-isnt-my-onelink-url-redirecting-users-to-the-specified-domain h_01HAKSWWMSHVW9KFWA34XGXWN2=can-i-manually-switch-between-the-branded-domain-and-its-onelink-subdomain-in-an-existing-link onelink-parameter-faq=pertanyaan-umum-parameter-onelink 01H7WPYJVAGRVWHRVMZVQG1ZVE=pertanyaan-umum-parameter-onelink 01H7WPYJVBCS3JZ98FYMAPY2YT=what-parameters-are-mandatory-for-onelink-custom-links 01H7WPYJVBCD7GG37JZTF919YQ=can-parameters-be-appended-to-the-short-url 01H7WPYJVB15Q3YAVJ8M7EQ1FW=contoh-2 01H7WPYJVBNTKJM3F72ZEZG32Z=what-custom-media-source-names-can-i-use 01H7WPYJVB25VGB37D3DZ2J786=what-attribution-parameters-can-be-added-to-a-onelink 01H7WPYJVBSQBR8E9NY0GJ3APT=are-custom-parameters-added-to-onelink-custom-links-available-in-raw-data 01H7WPYJVB3CCB838A7N6K932G=are-parameter-names-case-sensitive integrated-partner-faq=pertanyaan-umum-mitra-terintegrasi 01H7WPYJVB8ZZSKFT1V01EN6QF=pertanyaan-umum-mitra-terintegrasi 01H7WPYJVBCQNPTEZPM8KFE6YX=can-i-use-onelink-in-social-apps-unpaid 01H7WPYJVBTBQKK50JR179S7MW=can-i-use-onelink-with-ad-networks-paid 01H7WPYJVBJ0DX0MZPGXYF76EP=penting 01H7WPYJVBB9KJRZQTFZDG7NDK=contoh-3 01H7WPYJVB60DFMHN8PCVFC5S9=how-can-i-solve-the-ios-applaunching-issue-from-social-media-apps 01H7WPYJVB94NGD94MW4HYDB5S=can-i-use-onelink-on-instagram 01H7WPYJVBT5PJHVAFD1TY6CDY=can-i-use-onelink-for-redirection-on-wechat 01H7WPYJVB05C8BXKRG0WGBJ8P=why-are-android-users-with-the-app-installed-being-redirected-to-a-web-url-and-not-into-the-app-when-they-click-a-link-on-facebook-webview testing-faq=pertanyaan-umum-tentang-pengujian 01H7WPYJVC1PJJDA0GGT1DVVCF=pertanyaan-umum-tentang-pengujian 01H7WPYJVCQ89S3R4X1111TRGZ=how-can-i-ab-test-the-social-app-landing-page 01H7WPYJVC20TXWKRB89XFTK1N=how-can-i-bypass-the-app-selection-dialog deep-linking-faq=pertanyaan-umum-tentang-tautan-langsung 01H7WPYJVCTM39HKCG9JN03BN6=pertanyaan-umum-tentang-tautan-langsung 01H7WPYJVCZMRN53QG5JNSB8MP=what-deep-linking-methods-should-be-implemented 01H7WPYJVC6BXRJGTJBY6KG8JX=can-a-uri-scheme-af_dp-parameter-be-used-for-deep-linking ios-14-faq=pertanyaan-umum-ios-14 01H7WPYJVCVCVWHJW4RH85KC40=pertanyaan-umum-ios-14 01H7WPYJVCFANQQ9T27M2YGGBD=does-onelink-deep-linking-work-for-ios-14 01H7WPYJVCBC9YMBQ6TV1B2SBV=does-onelink-deferred-deep-linking-work-for-ios-14" />
