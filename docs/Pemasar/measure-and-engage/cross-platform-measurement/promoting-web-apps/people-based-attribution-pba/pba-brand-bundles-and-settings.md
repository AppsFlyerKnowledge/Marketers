---
title: Bundel dan pengaturan merek PBA
metadata:
  keywords:
    - Advertisers
    - Bundles
    - Web Attribution
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
  created_at: '2018-12-09T11:42:52Z'
  edited_at: '2025-05-08T09:17:30Z'
  id: 360000646498
  locale: id
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/id/articles/360000646498
---
> **Sekilas:** Bundel merek menggabungkan atribusi, event, kunjungan, dan pendapatan aplikasi dan situs web terkait merek. Gunakan halaman pengaturan paket merek untuk menandai event konversi, berintegrasi dengan Google Ads, dan banyak lagi.

<Image align="center" alt="BrandBundles.png" src="https://files.readme.io/eab9447f0bdd225ab7915724f996555057fa7f2840ec6e69a89465a90af6181e-360017356617.png" />

<div id="about-brand-bundles" />

## Tentang bundel merek

Merek beroperasi dalam ekosistem yang mencakup properti web dan seluler. Sebagai pemasang iklan, gambaran lengkap tentang kinerja merek di seluruh platform–web dan seluler–diperlukan. Di PBA, bundel merek menggabungkan data properti seluler dan web menjadi satu kesatuan untuk tujuan analitik dan data lengkap.

<div id="what-is-a-web-app" />

> 📘 **Apa itu aplikasi web?**
>
> Aplikasi web adalah <Anchor target="_blank" href="/marketers/id/docs/adding-an-app-to-appsflyer">entitas yang Anda buat di AppsFlyer</Anchor> yang menentukan situs web yang ingin Anda ukur kinerjanya.
>
> * Entitas aplikasi web telah ditambahkan ke AppsFlyer pada tanggal 9 Februari 2022. Sebelum tanggal tersebut, Anda memasukkan domain bundel merek sebagai pengaturan terpisah saat membuat bundel merek. Sekarang, pertama-tama Anda membuat aplikasi web yang mendefinisikan domain, lalu menyertakan aplikasi web tersebut saat membuat bundel.
> * Jika Anda sudah memiliki bundel merek pada tanggal 9 Februari 2022, Anda akan melihat bahwa Anda sekarang memiliki aplikasi web di halaman **Aplikasi saya** yang sesuai dengan masing-masing bundeltersebut. **Yakinlah!** Lalu lintas web Anda diatribusikan seperti sebelumnya, dan tidak ada perubahan lain pada dashboard PBA atau laporan data lengkap.

**Dasar-dasar bundel merek:**

* Bundel merek berisi 1 aplikasi web *(wajib)* dan 1 atau lebih aplikasi seluler *(opsional).*
* Sebuah aplikasi (web atau seluler) hanya dapat dimiliki oleh 1 bundel.
* Aplikasi tidak dapat dihapus dari suatu bundel atau dipindahkan dari satu bundel ke bundel lainnya tanpa [menghapus bundel aslinya](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle).
  * Saat bundel dihapus, AppsFlyer berhenti mengatribusikan data PBA untuk bundel tersebut, dan akses ke data historisnya tidak lagi tersedia.

<div id="accessing-brand-bundles" />

## Mengakses bundel merek

Akses halaman **Bundel Merek** untuk mengelola bundel merek dan pengaturannya:

* Buka **Aplikasi saya** > **Lihat bundel merek.**  
                           - atau -
* Dari pohon navigasi sebelah kiri di dashboard, buka **Konfigurasi** > **Bundel Merek.**

<div id="managing-brand-bundles" />

## Mengelola bundel merek

Untuk menambah, menghapus, atau mengelola bundel merek, pilih salah satu opsi berikut dari halaman **Bundel Merek** :

| Opsi | Detail |
| --- | --- |
| Tambahkan bundel merek | Membuka halaman **Buat bundel**   <br />Ikuti [instruksi di bawah ini](/docs/pba-brand-bundles-and-settings#add-brand-bundle) untuk membuat bundel baru. |
| Dashboard PBA | Membuka dashboard merek |
| ID bundel merek | Menyalin ID bundel merek ke papan klip |
| Kode pengembang web | Menyalin kunci pengembang web ke papan klip |
| Pilih paket yang ada untuk memperbarui pengaturan dan opsi bundel merek | Opsi yang tersedia:<ul><li>Tandai event sebagai event konversi:<ul><li>[Pengaturan event web](/docs/pba-brand-bundles-and-settings#web-event-settings)</li><li>[Pengaturan in-app event](/docs/pba-brand-bundles-and-settings#inapp-event-settings)</li></ul></li><li>[Pengecualian domain](/docs/pba-brand-bundles-and-settings#domain-exclusion)</li><li><Anchor target="_blank" href="/marketers/id/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">Integrasi Google Ads</Anchor></li></ul> |
| Hapus ikon | [Hapus bundel merek yang dipilih](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) (setelah Anda mengonfirmasi keputusan Anda untuk melakukannya) |

<div id="add-brand-bundle" />

<Accordion title="Tambahkan bundel merek">

Sebelum melanjutkan, pastikan semua aplikasi yang ingin Anda sertakan dalam bundel telah ditambahkan ke akun Anda. Setelah bundel merek dibuat, aplikasi yang disertakan di dalamnya tidak dapat diubah tanpa [menghapus bundel](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) dan membuatnya kembali.

**Untuk menambahkan bundel merek:**

1. Dari halaman [Bundel Merek](/docs/pba-brand-bundles-and-settings#mengakses-bundel-merek) , klik **Tambahkan bundel merek.**
2. Masukkan **Nama bundel merek** (nama apa pun yang ingin Anda gunakan untuk mengidentifikasi bundel).
3. Pilih aplikasi yang akan disertakan dalam bundel.

   **Catatan:** Aplikasi yang disertakan dalam bundel lain tidak tersedia untuk dipilih.

   * Aplikasi web *[wajib]*: Pilih 1 aplikasi web yang tersedia.
   * Aplikasi seluler *[opsional]:* Pilih aplikasi seluler yang tersedia yang ingin Anda sertakan dalam bundel.
     * Aplikasi seluler tidak diperlukan untuk membuat bundel.
     * Tidak ada batasan jumlah aplikasi seluler yang dapat Anda sertakan dalam satu bundel.
4. Klik Buat bundel.

<div id="important" />

> 🚧 **Penting!**
>
> Bundel merek tidak dapat dibuat dalam kondisi berikut:
>
> * Aplikasi web yang dipilih untuk disertakan dalam bundel tidak mengarah ke URL yang valid.
> * Aplikasi web dan aplikasi seluler Android yang dipilih untuk disertakan dalam bundel memiliki ID aplikasi yang sama.

</Accordion>

<div id="web-event-settings" />

<Accordion title="Pengaturan event web">

Ada dua jenis event web: **standar** dan **konversi**. Untuk memfokuskan dan memprioritaskan upaya pengoptimalan Anda, tetapkan beberapa event sebagai event konversi.

* PBA mengatribusikan event standar dan konversi dengan cara yang sama.
* Laporan <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">data lengkap</Anchor> mencakup event standar dan konversi.
* Dashboard PBA hanya menyertakan event konversi.
* Jenis event dapat diubah kapan saja; namun, perubahan tersebut tidak bersifat retroaktif.

**Untuk menetapkan event konversi:**

1. Dari halaman [Bundel Merek](/docs/pba-brand-bundles-and-settings#mengakses-bundel-merek) , pilih bundel merek tersebut.  
   Halaman **Perbarui Bundel merek** terbuka.
2. Buka tab **Pengaturan event web** .
3. Aktifkan **Tandai sebagai event konversi** sesuai kebutuhan.
4. Klik **Perbarui bundel.**

</Accordion>

<div id="inapp-event-settings" />

<Accordion title="Pengaturan in-app event">

Jalur Konversi mempertimbangkan in-app event yang ditandai dan web event yang ditandai sebagai event konversi. Seperti event web, pemasar menetapkan in-app event tertentu sebagai event konversi.

[Default] In-app event yang memiliki pendapatan ditandai sebagai event konversi. **Perhatikan!** Jika Anda mengubah event default, Anda harus menandai sendiri event pendapatan dalam aplikasi secara eksplisit.

**Untuk menandai in-app event sebagai event konversi:**

1. Dari halaman [Bundel Merek](/docs/pba-brand-bundles-and-settings#mengakses-bundel-merek) , pilih bundel merek tersebut.  
   Halaman **Perbarui Bundel merek** terbuka.
2. Buka tab **Pengaturan in-app event** .
3. Aktifkan **Tandai sebagai event konversi** sesuai kebutuhan.
4. Klik **Perbarui bundel.**

</Accordion>

<div id="domain-exclusion" />

<Accordion title="Pengecualian domain">

Mekanisme pengecualian domain, yang merupakan bagian dari <Anchor target="_blank" href="/marketers/id/docs/pba-media-source-attribution-rules">aturan sumber media PBA,</Anchor> diterapkan untuk mencegah:

* Atribusi mandiri: Dengan kata lain, AppsFlyer tidak akan mengatribusikan event ke situs web yang ditentukan dalam aplikasi web itu sendiri dan ke domain yang Anda tentukan terkait dengan situs web tersebut.
* Mengatribusikan atau mencatat event yang terkait dengan domain yang bukan bagian dari merek Anda namun berpartisipasi dalam alur pengguna (misalnya, gateway pembayaran).

| Jenis domain | Deskripsi | Dampak pengecualian |
| --- | --- | --- |
| Utama | Domain **aplikasi web** yang disertakan dalam bundel merek. Ini termasuk subdomain.<br /><br />Misalnya, jika domain Anda adalah mydomain.co.za maka subdomain seperti a.mydomain.co.za, b.mydomain.co.za akan dikecualikan secara otomatis. <br /><br />Domain aplikasi web tidak dapat diubah tanpa [menghapus](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) dan membuat ulang aplikasi web. (Ini juga berarti menghapus bundel yang menyertakan aplikasi web). | Tidak ada atribusi diri |
| Internal | Cantumkan domain lain yang menjadi bagian dari merek Anda, misalnya, mydomain.com, mydomain.in, mydomain.co.ng, abc.com | Tidak ada atribusi diri |
| Eksternal (didaftarkan oleh Anda) | Domain yang digunakan langsung oleh situs web Anda, namun bukan bagian dari merek. Ini termasuk gateway pembayaran, situs pemrosesan pembayaran, dll. | <Anchor target="_blank" href="/marketers/id/docs/pba-media-source-attribution-rules#visit-recognition-rules">Kunjungan diabaikan</Anchor> |
| Eksternal (didaftarkan oleh AppsFlyer) | Domain terdaftar oleh AppsFlyer dan selalu dikecualikan.<ul><li>PayPal</li><li>Stripe</li><li>Adyen</li></ul>Daftar domain otomatis tidak dapat diedit. | <Anchor target="_blank" href="/marketers/id/docs/pba-media-source-attribution-rules#visit-recognition-rules">Kunjungan diabaikan</Anchor> |

**Untuk mengecualikan domain internal atau eksternal:**

1. Dari halaman [Bundel Merek](/docs/pba-brand-bundles-and-settings#mengakses-bundel-merek) , pilih bundel merek tersebut.  
   Halaman **Perbarui Bundel merek** terbuka.
2. Buka tab **Pengecualian domain** .
3. Klik **Tambahkan domain.**
4. Masukkan nama domain.
5. Pilih jenis domain: **Internal** atau **Eksternal.**
6. Klik **Tambahkan domain.**  
   Diperlukan waktu satu jam agar pengecualian diterapkan.

</Accordion>

<div id="faq" />

## Pertanyaan Umum

<div id="can-i-include-the-same-app-in-more-than-one-bundle" />

<Accordion title="Dapatkah saya menyertakan aplikasi yang sama di lebih dari satu bundel?">

**Tidak.** Setelah aplikasi ditambahkan ke bundel, aplikasi tersebut tidak dapat ditambahkan ke bundel lain.

</Accordion>

<div id="can-i-add-or-remove-apps-after-creating-a-bundle" />

<Accordion title="Bisakah saya menambah atau menghapus aplikasi setelah membuat bundel?">

**Tidak.** Setelah bundel dibuat, aplikasi yang disertakan di dalamnya tidak dapat diubah.

**Mengapa?** Setiap aplikasi memiliki datanya sendiri, dan AppsFlyer menggunakan data ini untuk menganalisis perjalanan pengguna di seluruh platform (web dan aplikasi). Jika suatu aplikasi diubah, hal ini akan melibatkan set data berbeda yang tidak kompatibel dengan data sebelumnya.

</Accordion>

<div id="how-do-i-add-or-remove-delete-apps-from-a-bundle" />

<Accordion title="Bagaimana cara menambah atau menghilangkan (menghapus) aplikasi dari bundel?">

Untuk mengubah bundel yang menyertakan suatu aplikasi, hapus bundel asli dan buat bundel baru yang menyertakan aplikasi tersebut.

</Accordion>

<div id="what-happens-if-i-delete-a-bundle" />

<Accordion title="Apa yang terjadi jika saya menghapus bundel?">

<div id="page-404" />

<div id="faqs-what-happens-if-i-delete-a-bundle" />

#### FAQ apa yang terjadi jika saya menghapus bundel

Jika Anda menghapus bundel:

* AppsFlyer berhenti mengatribusikan bundel tersebut.
* Data bundel dipertahankan (dengan kata lain, tidak dihapus secara permanen), namun bundel itu sendiri tidak dapat dipulihkan untuk dilihat datanya.

  **Mengapa?** Bundel baru menggunakan kode pengembang web yang berbeda sehingga, meskipun berisi aplikasi yang sama, bundel asli tidak dipulihkan.

</Accordion>

<div id="why-are-certain-apps-not-available-for-me-to-add-to-a-bundle" />

<Accordion title="Mengapa aplikasi tertentu tidak tersedia untuk saya tambahkan ke bundel?">

* **Admin:** Jika Anda tidak dapat memilih suatu aplikasi saat membuat bundel, pastikan aplikasi tersebut telah ditambahkan ke akun AppsFlyer Anda dan tidak disertakan dalam bundel lain.
* **Pengguna akun lain:** Hubungi admin akun untuk memastikan Anda memiliki peran dan izin yang diperlukan untuk mengakses aplikasi yang ingin Anda tambahkan.

</Accordion>

<div id="see-also" />

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/onboarding-guide-to-people-based-attribution">Panduan orientasi ke PBA</Anchor>
> * <Anchor target="_blank" href="/marketers/id/docs/people-based-attribution-pba-overview">PBA untuk memulai</Anchor>

<div data-zendesk-anchors="about-brand-bundles=tentang-bundel-merek h_01HE0Y2A3A5W86YY44RWCTKM1Y=tentang-bundel-merek h_01HE0Y2A3AYAFFSPRSH2BQ00Z3=apa-itu-aplikasi-web accessing-brand-bundles=mengakses-bundel-merek h_01HE0Y2A3A7265NYM7GVBZVXEN=mengakses-bundel-merek managing-brand-bundles=mengelola-bundel-merek h_01HE0Y2A3A272QJ4ZQH7VXJWCC=mengelola-bundel-merek h_01HE0Y2A3ATX4ZDYZSRQGSJ4G7=add-brand-bundle h_01HE0Y2A3AQC5MMNQA0AV34MZ3=penting h_01HE0Y2A3ATN6DEQ2KHCGT6VPQ=web-event-settings h_01HE0Y2A3A76VBZ17W4P1D0K2A=inapp-event-settings h_01HE0Y2A3A7F2YEW2SK0PSXXE4=domain-exclusion faq=pertanyaan-umum h_01HE0Y2A3AB24NCNPAYFC0J4YH=pertanyaan-umum h_01HE0Y2A3A5E816CYG2TMZ37DA=can-i-include-the-same-app-in-more-than-one-bundle h_01HE0Y2A3BENKY1AM51VM76TVS=can-i-add-or-remove-apps-after-creating-a-bundle h_01HE0Y2A3BK4JKMTND0JFCB179=how-do-i-add-or-remove-delete-apps-from-a-bundle h_01HE0Y2A3BKJTQZJXV49X32N1E=what-happens-if-i-delete-a-bundle faqs-what-happens-if-i-delete-a-bundle=faq-apa-yang-terjadi-jika-saya-menghapus-bundel h_01HE0Y2A3B276FV92EYBCZRA6C=faq-apa-yang-terjadi-jika-saya-menghapus-bundel h_01HE0Y2A3BEB2JG8CPSX3DA1V9=why-are-certain-apps-not-available-for-me-to-add-to-a-bundle h_01HE0Y2KTXS06WHN57MQ91AD09=lihat-juga" />
