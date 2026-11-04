---
title: Pengalaman pelanggan dan ikhtisar deep linking
metadata:
  keywords:
    - Marketers
    - start
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2017-10-19T08:53:16Z'
  edited_at: '2023-07-06T08:40:21Z'
  id: 115005248543
  locale: id
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/id/articles/115005248543
---
> **Sekilas:** Buat tautan dengan kemampuan atribusi, pengalihan, dan deep linking yang mengubah pengguna media milik sendiri atau berbayar menjadi pengguna aplikasi, terlepas dari perangkat, sistem operasi, saluran, atau platform.Tautan ini membantu memberikan pengalaman terbaik bagi pengguna Anda, apa pun sumber media milik asal konversi mereka: situs web, spanduk, postingan media sosial, email, teks, dan banyak lagi.

<div id="introduction-video" />

## Video pengantar

<Embed title="Pemutar video YouTube" typeOfEmbed="youtube" url="https://www.youtube.com/embed/golT4p9D8MA" providerUrl="https://www.youtube.com" />

<div id="benefits" />

## Manfaat

Pengalaman pelanggan AppsFlyerdan rangkaian deep linking yang didukung oleh OneLinkmemungkinkan Anda membuat tautan untuk mengukur kampanye pemasaran seluler di setiap saluran utama. Tautan yang Anda buat memungkinkan Anda untuk:

* Berinteraksi dengan pelanggan Anda di banyak titik kontak online dan offline yang berbeda.
* Tingkatkan konversi dengan memberikanpengalaman kontekstual terbaik kepada pengguna dari titik kontak mana pun, mulai dari klik hingga penginstalan aplikasi.
* Dapatkan atribusi dan pengukuran yang akurat terkait hasil kampanye Anda.
* Kirim pengguna baru tanpa aplikasi Anda ke toko aplikasi atau URL web yang benar, apa pun perangkat, sistem operasi, saluran, atau platformnya.
* Kirim pengguna yang ada dengan aplikasi Anda yang diinstal langsung ke aplikasi (menggunakan Tautan Aplikasi, Tautan Universal, dan skema URI).
* Deep link pengguna ke halaman atau pengalaman in-app tertentu.

Suite ini i gratis untuk semua paket akun.

<div id="experiences" />

## Pengalaman

Pengalaman pelangganAppsflyerdan suite deep linking yang didukung oleh OneLinkmemungkinkan Anda membuat tautan yang memberikan pengalaman optimal bagi pengguna Anda, dari mana pun mereka berasal. Pengalaman pelanggan yang dapat Anda konfigurasikan meliputi:

* **Sosial-ke-aplikasi**: Libatkan pengguna Anda di media sosial dan kirim mereka dari umpan media sosial ke aplikasi Anda.
* **Aplikasi-ke-aplikasi** : Arahkan pengguna ke aplikasi Anda dari dalam aplikasi lain.
* <Anchor target="_blank" href="/marketers/id/docs/convert-your-mobile-web-visitors-to-app-users">**Web-ke-aplikasi**</Anchor>: Ubah pengunjung situs web seluler Anda menjadi pengguna aplikasi seluler menggunakan Smart Banner atau Smart Script.
* **QR-ke-aplikasi**: Gunakan kode QR untuk mendorong penginstalan aplikasi dengan meminta pengguna  memindai kode QR di titik-titik penting selama pengalaman pelanggan secara offline mereka. Anda juga dapat menempatkan kode QR di situs desktop, atau di iklan TV dan CTV untuk mengarahkan pengguna ke aplikasi Anda.
* **Email-ke-aplikasi**: Gunakan penyedia layanan email/email service providers (ESP) untuk berinteraksi dengan pengguna melalui email dan arahkan mereka dari kotak masuk ke aplikasi Anda.
* **Teks-ke-aplikasi**:Buat tautan untuk SMS dan kampanye pesan Anda dan libatkan pengguna melalui pesan teks.
* **Referral-ke-aplikasi** : Buat tautan undangan pengguna yang memungkinkan pengguna atau pemberi pengaruh mengundang orang lain ke aplikasi Anda atau berbagi konten dalam aplikasi tertentu, misalnya, sebuah artikel.
* **Lainnya**: Dari mana pun asal pengguna Anda, baik melalui desktop atau seluler, online atau offline, media milik sendiri atau berbayar, gunakan OneLink untuk mengarahkan pengguna Anda ke tempat yang tepat dengan mudah.

<div id="setting-up-onelink" />

## Pengaturan

Memberikan pengalaman pelanggan yang diinginkan dari tautan ke penginstalan aplikasi untuk pengguna Anda menggunakan UI AppsFlyer memerlukan:

* Dua peran berbeda dalam sebuah organisasi (pemasar dan pengembang) bekerja sama.
* <Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template">Membuat templat OneLink</Anchor> yang mewakili logika perutean sebagai inti dari semua tautan Anda, untuk mengarahkan:
  * Pengguna baru yang tidak menginstal aplikasi Anda ke toko aplikasi atau URL web yang benar.
  * Pengguna yang sudah ada dengan aplikasi Anda yang sudah diinstal ke aplikasi lewat Tautan Aplikasi Android, Tautan Universal iOS, dan skema URI.
    * Jika ini tidak ditentukan, pengguna akan menggunakan setelan default sebagai pengguna baru tanpa memasang aplikasi Anda (URL web atau app store).**Catatan**: Templat OneLink bukanlah tautan yang dapat diklik untuk pengguna akhir Anda; ini adalah dasar untuk menghasilkan banyak tautan kustom. Berdasarkan templat, Anda dapat membuat banyak tautan kustom OneLink untuk diklik pengguna. Jarang diperlukan lebih dari satu atau dua templat OneLink selama masa pakai aplikasi (di luar pengujian).
* <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Membuat tautan OneLink</Anchor>. Ini adalah tautan yang dapat diklik atau kode QR yang dapat dipindai yang ditampilkan di iklan Anda. Selama penyiapan tautan, Anda menentukan pengalaman pelanggan yang diinginkan dan menambahkan parameter apa pun yang diinginkan.

Tabel berikut menjelaskan detail tugas pemasar dan pengembang dan menyediakan tautan ke sumber daya mereka.

| Tugas | Detail | Sumber daya |
| --- | --- | --- |
| Buat templat OneLink | <ul><li>Pemasar/manajer produk menyiapkan templat di AppsFlyer.</li><li>Pengembang Android mengonfigurasi metode pembukaan aplikasi untuk pengguna yang ada (Tautan Aplikasi Android dan skema URI).</li><li>Pengembang iOS mengonfigurasi metode pembukaan aplikasi untuk pengguna yang ada (Tautan Universal iOS dan skema URI).</li></ul> | <ul><li>Dashboard AppsFlyer</li><li><Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template">Instruksi pemasar</Anchor></li><li>Petunjuk pengembang untuk <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#app-opening-methods">Android</Anchor> dan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup">iOS</Anchor></li></ul> |
| Buat tautan OneLink | <ul><li>Pemasar/manajer produk menyiapkan tautan di AppsFlyer, termasuk memilih pengalaman pelanggan yang diinginkan dan menambahkan atribusi atau parameter deep linking yang diinginkan.</li><li>Pengembang Android dan iOS menerapkan metode UDL untuk deep linking (jika deep linking diperlukan).</li></ul> | <ul><li><Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Instruksi pemasar</Anchor></li><li>Petunjuk pengembang untuk <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_unified_deep_linking">Android</Anchor> dan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_unified_deep_linking">iOS</Anchor></li><li>Aplikasi sampel (Github)</li></ul> |

<div id="additional-options" />

## Opsi tambahan

Setelah menyelesaikan beberapa atau semua penyiapan di UI, pertimbangkan untuk menerapkan fitur tambahan yang dijelaskan di bawah ini.

**Catatan** : Semua fitur disertakan sebagai bagian dari rencana AppsFlyer <Anchor target="_blank" href="/marketers/id/docs/account-management-plans-payments-and-billing">Zero and Growth</Anchor> , kecuali OneLink API, yang merupakan fitur premium.

* <Anchor target="_blank" href="/marketers/id/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API OneLink</Anchor> dan <Anchor target="_blank" href="/marketers/id/docs/perform-onelink-bulk-actions-via-csv">pembuatan tautan massal</Anchor>: Memperbesar dan menjalankan beberapa kampanye sekaligus, dan membuat ribuan tautan OneLink dengan cepat dan mudah, menghemat waktu dan tenaga Anda, dan memungkinkan Anda untuk fokus pada upaya kampanye dan pemasaran Anda.
* <Anchor target="_blank" href="/marketers/id/docs/export-onelink-urls">Ekspor URL OneLink</Anchor> : Unduh semua URL OneLink yang dibuat di antarmuka pengguna AppsFlyer (URL OneLink yang dibuat melalui SDK, OneLink API, atau unggahan massal tidak disertakan).
* <Anchor target="_blank" href="/marketers/id/docs/measuring-push-notification-re-engagement-campaigns">Ukur kampanye interaksi ulang notifikasi push</Anchor>: Gunakan notifikasi push dengan OneLink untuk mengukur interaksi ulang pengguna seluler.
* <Anchor target="_blank" href="/marketers/id/docs/cross-promotion-attribution-for-marketers">Atribusi promosi silang</Anchor>: Pengguna yang sudah ada adalah kandidat sempurna untuk instalasi aplikasi baru Anda lainnya. Pelajari cara menggunakan metode SDK untuk dengan mudah membuat dan mengukur kampanye promosi silang.
* <Anchor target="_blank" href="/marketers/id/docs/understand-onelink-short-vs-long-urls">URL panjang</Anchor> : Tambahkan parameter ke tautan khusus OneLink Anda atau buat tautan khusus OneLink dalam jumlah besar dengan menerapkan rumus sederhana Anda sendiri dalam spreadsheet.
* <Anchor target="_blank" href="/marketers/id/docs/redirect-app-users-to-a-website">Pengarahan aplikasi-ke-web</Anchor> : Mengarahkan pengguna dari aplikasi Anda ke situs web atau halaman media sosial.

<div id="troubleshooting-and-faq" />

## Pemecahan masalah dan Pertanyaan Umum (FAQ)

Temukan solusi dengan cepat untuk menguji dan men-debug masalah pengarahan/perilaku tautan kustom OneLink dengan <Anchor target="_blank" href="/marketers/id/docs/onelink-troubleshooting-and-faq">panduan pemecahan masalah OneLink</Anchor> kami.

<div id="limitations" />

## Batasan

* OneLink tidak didukung oleh tujuan penginstalan aplikasi seluler Meta, di mana hanya Tautan Aplikasi Meta yang diterima.

<div data-zendesk-anchors="introduction-video=video-pengantar benefits=manfaat experiences=pengalaman setup=pengaturan additional-options=opsi-tambahan troubleshooting-and-faq=pemecahan-masalah-dan-pertanyaan-umum-faq limitations=batasan" />
