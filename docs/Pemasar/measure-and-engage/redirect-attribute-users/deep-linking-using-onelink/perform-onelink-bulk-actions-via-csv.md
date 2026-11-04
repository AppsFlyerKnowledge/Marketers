---
title: Tautan Massal
metadata:
  keywords:
    - Marketers
    - bulk
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2023-04-13T11:31:43Z'
  edited_at: '2023-12-27T02:41:08Z'
  id: 14511403892369
  locale: id
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/id/articles/14511403892369
---
> **Sekilas:** Halaman tautan massal OneLink memungkinkan Andamembuat sejumlah besar tautan khusus OneLink secara instan dan melihatnya di satu lokasi untuk digunakan di masa mendatang.

Tautan massal memungkinkan Anda membuat dan melihat tautan yang dibuat secara massal. Tautan massal ini dikelompokkan dalam format koleksi yang mudah digunakan yang memungkinkan Anda melakukan tindakan pada seluruh koleksi seperti menambahkan tautan baru atau mengunduhnya.

<div id="getting-started" />

## Persiapan

1. Di AppsFlyer, buka **Pengalaman & Deep Linking** > **Tautan Massal OneLink**.
2. Anda akan melihat halaman intro dengan salah satu tombol berikut:
   1. **Memulai** - (kirim untuk membuat koleksi pertama Anda).
   2. **Membuat templat OneLink** - Templat OneLink diperlukan untuk membuat koleksi. Lihat <Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template">Templat OneLink</Anchor>.
   3. **Upgrade** - Tautan massal tidak tersedia dengan paket Anda saat ini. Hubungi CSM Anda atau kirim pesan ke [hello@appsflyer.com](mailto:hello@appsflyer.com) tentang meng-upgrade paket Anda.

<div id="creating-your-first-collection" />

## Membuat koleksi pertama Anda

1. Klik **Mulai.**
2. Masukkan nama untuk koleksi Anda.  
   Pilih nama yang mencerminkan tujuan koleksi Anda, sehingga nantinya Anda dapat dengan mudah mengidentifikasinya.
3. Pilih templat OneLink Catatan: semua tautan koleksi akan didasarkan pada templat ini
4. Klik **Simpan & lanjutkan.**
5. Unggah file CSV Anda. Anda dapat menggunakan yang berikut ini <Anchor target="_blank" href="https://cdn.appsflyer.com/onelink-bulk-links-mgmt/sample_file.csv">Contoh CSV</Anchor> sebagai panduan.  
   Lihat [Format unggahan](/docs/perform-onelink-bulk-actions-via-csv#upload-format) untuk memastikan CSV Anda kompatibel dan unggahan berhasil. Setelah file CSV diunggah, file tersebut akan divalidasi. Jika ada baris yang tidak valid, CSV laporan validitas akan tersedia untuk diunduh guna membantu memperbaiki file Anda. Ikuti instruksi di UI dan upload file yang telah diperbaiki.
6. Klik **Buat koleksi.**

## Mengelola tautan massal Anda dengan koleksi

Tautan massal dikelola dalam koleksi.

* Di bagian atas halaman, **Widget penggunaan link massal bulan ini** menunjukkan jumlah permintaan tautan (yang mencakup pembuatan dan pembaruan tautan) dari kuota bulanan untuk bulan ini.
  * Saat ini, batas default adalah 20.000 pembuatan tautan per bulan
* Bagian **Koleksi** memungkinkan Anda membuat koleksi baru dan melakukan tindakan lain ke koleksi tautan Anda saat ini.
* Jika ada lebih dari tujuh koleksi, Anda dapat mencari dan memfilter daftar koleksi Anda.

<div id="other-actions" />

## Tindakan lainnya

Berikut adalah tindakan lain yang dapat dilakukan pada koleksi:

<div id="creating-a-new-collection" />

<Accordion title="Membuat koleksi baru">

Membuat koleksi baru tersedia bila [penggunaan bulanan](/docs/perform-onelink-bulk-actions-via-csv#mengelola-tautan-massal-anda-dengan-koleksi) belum terlampaui.

1. Klik **Koleksi baru**.
2. Ikuti petunjuk.
   1. Prosesnya mengikuti langkah yang sama seperti [Membuat koleksi pertama Anda](/docs/perform-onelink-bulk-actions-via-csv#membuat-koleksi-pertama-anda).

</Accordion>

<div id="downloading-a-collection" />

<Accordion title="Mengunduh koleksi">

Opsi unduh koleksi tersedia saat:

* Ada tautan aktif dalam koleksi itu.
* Anda memiliki izin akses aplikasi ke setidaknya salah satu aplikasi seluler templat OneLink yang terkait dengan koleksi.

Untuk Mengunduh koleksi:

1. Klik ikon unduh pada baris koleksi.
2. Pilih domain untuk keluaran URL pendek.
3. Klik **Unduh**.

> 🚧 **Penting!**
>
> AppsFlyer merekomendasikan penggunaan Domain Bermerek karena dapat meningkatkan kinerja kampanye dengan mendorong kepercayaan dan mempromosikan kesadaran merek. <Anchor target="_blank" href="/marketers/id/docs/brand-onelink-with-your-domain">Pelajari lebih lanjut di sini.</Anchor>

</Accordion>

<div id="adding-links-to-a-collection" />

<Accordion title="Menambahkan tautan ke koleksi">

Opsi penambahan tautan tersedia saat:

* Anda memiliki izin akses aplikasi ke setidaknya salah satu aplikasi seluler templat OneLink yang terkait dengan koleksi.
* Ada kurang dari 2000 tautan aktif dalam koleksi.
* [Penggunaan bulanan](/docs/perform-onelink-bulk-actions-via-csv#mengelola-tautan-massal-anda-dengan-koleksi) belum terlampaui.

Untuk menambahkan tautan ke koleksi, klik **opsi menu** > **Tambahkan tautan ke koleksi.**

* Tautan akan ditambahkan menggunakan metode yang sama seperti yang dijelaskan dalam [Membuat koleksi pertama Anda](/docs/perform-onelink-bulk-actions-via-csv#membuat-koleksi-pertama-anda) dari poin 5 dan seterusnya.

</Accordion>

<div id="editing-links-in-a-collection" />

<Accordion title="Mengedit tautan dalam koleksi">

Opsi tautan pengeditan tersedia saat:

* Ada tautan aktif dalam koleksi itu.
* Anda memiliki izin akses aplikasi ke setidaknya salah satu aplikasi seluler templat OneLink yang terkait dengan koleksi.
* [Penggunaan bulanan](/docs/perform-onelink-bulk-actions-via-csv#mengelola-tautan-massal-anda-dengan-koleksi) belum terlampaui.

**Untuk mengedit tautan dalam koleksi:**

1. Klik **opsi menu** > **Edit tautan**.
2. Unduh CSV basis koleksi. File ini berisi semua tautan dalam koleksi yang dapat Anda edit.
3. Ikuti instruksi di langkah pertama untuk mengedit parameter tautan. Untuk setiap tautan yang ingin Anda perbarui, pastikan **Tandai untuk pembaruan** disetel sebagai **true**.
4. Klik **Berikutnya**.
5. Unggah CSV Anda yang telah diedit. Lihat [Format unggahan](/docs/perform-onelink-bulk-actions-via-csv#upload-format) untuk memastikan CSV Anda kompatibel dan unggahan berhasil.
   * Setelah file CSV diunggah, itu akan divalidasi.
   * Jika ada baris yang tidak valid, CSV laporan validitas tersedia untuk diunduh untuk membantu memperbaiki file Anda. Ikuti petunjuk di UI dan upload file yang telah diperbaiki.
6. Klik **Perbarui tautan**.

</Accordion>

<div id="viewing-the-collection-history" />

<Accordion title="Melihat riwayat koleksi">

Untuk melihat riwayat koleksi, klik **opsi menu** > **Lihat riwayat koleksi.**

Jendela riwayat akan menampilkan tindakan berikut serta tanggal dan waktu tindakan dilakukan dan oleh siapa:

* **Perubahan nama:** Perubahan nama koleksi.
* **Tautan ditambahkan:** Saat tautan ditambahkan ke koleksi.
* **Tautan diperbarui**: Saat tautan dalam koleksi diedit dan diperbarui.
* **Koleksi** **dibuat**:  Saat koleksi dibuat.

<span id="page-components"></span>**Tautan yang ditambahkan dan diperbarui** juga menunjukkan kepada Anda bagaimana perubahan memengaruhi [jumlah penggunaan](/docs/perform-onelink-bulk-actions-via-csv#mengelola-tautan-massal-anda-dengan-koleksi) Anda dan memungkinkan Anda mengunduh laporan tindakan tentang perubahan itu.

* * Laporan tindakan hanya dapat diunduh jika Anda memiliki izin akses aplikasi ke setidaknya salah satu aplikasi seluler templat OneLink yang terkait dengan koleksi.

</Accordion>

<div id="editing-the-collection-name" />

<Accordion title="Mengedit nama koleksi">

Opsi pengeditan nama koleksi tersedia saat:

* Anda memiliki izin akses aplikasi ke setidaknya salah satu aplikasi seluler templat OneLink yang terkait dengan koleksi.

Untuk mengedit nama koleksi:

1. Arahkan kursor ke nama koleksi yang ingin Anda ubah.
2. Klik ikon edit di samping nama koleksi.
3. Setelah Anda mengedit nama, klik enter atau klik di tempat lain di layar.

</Accordion>

<div id="deleting-empty-collections" />

<Accordion title="Menghapus koleksi kosong">

Jika koleksi kosong, dan Anda memiliki izin akses aplikasi ke setidaknya salah satu aplikasi seluler templat OneLink yang terkait dengan koleksi, koleksi dapat dihapus dengan mengeklik **opsi menu -> Hapus koleksi**.

Koleksi dapat menjadi kosong karena:

* <Anchor target="_blank" href="/marketers/id/docs/bulletin-onelink-short-url-ttls-automatically-extend">TTL (waktu hidup)</Anchor> dari semua tautan dalam koleksi telah kedaluwarsa.
* Proses pengumpulan Baru dibatalkan atau gagal diselesaikan sebelum tautan dibuat. Ini menciptakan koleksi kosong.

</Accordion>

<div id="general-information" />

## Informasi umum

> 📘 **Catatan**
>
> Tautan massal yang dibuat sebelum April 2023 tidak akan ditampilkan atau dikelola di halaman tautan massal.

<div id="upload-format" />

<Accordion title="Format unggahan">

Untuk memastikan file CSV Anda diunggah tanpa kesalahan, pastikan file Anda memenuhi standar berikut.

* File harus dalam format CSV
* File tidak boleh lebih besar dari 4 MB
* File hanya boleh berisi konten untuk tautan yang Anda buat/perbarui
* Setiap tautan harus berada di barisnya masing-masing
* Setiap kolom mewakili satu parameter
  * Maksimum 35 kolom parameter
* Hanya penyandian karakter UTF-8 yang diterima
* Maksimal 2000 tautan per koleksi

</Accordion>

<div id="csv-parameters" />

<Accordion title="Parameter CSV">

* Parameter dalam CSV dapat berupa parameter apa pun yang dapat diterima di tautan AppsFlyer. Ini dapat berupa parameter yang dicadangkan untuk atribusi (mis.: c, af\_channel, af\_adset, dll.), untuk pengalihan & penautan langsung (mis.: af\_ios\_url, af\_dp, deep\_link\_value, dll.), atau parameter khusus.
* Parameter sumber media (pid) adalah wajib.
* Agensi perlu menambahkan parameter `af_prt` secara manual ke tautan mereka.
* Bahkan jika skema URI diatur dalam templat OneLink, untuk tautan yang dibuat secara massal, parameter af\_dp dengan skema URI harus ditentukan di file CSV Anda.

</Accordion>

<div data-zendesk-anchors="getting-started=persiapan h_01HJJRRJCD2F57FE0A4Z5BCMTE=persiapan creating-your-first-collection=membuat-koleksi-pertama-anda h_01HJJRRJCDSTTR2FQ53J86RGSJ=membuat-koleksi-pertama-anda collection-features=mengelola-tautan-massal-anda-dengan-koleksi h_01HJJRRJCDCF830CCFCV3HQSJY=mengelola-tautan-massal-anda-dengan-koleksi other-actions=tindakan-lainnya h_01HJJRRJCD2XE454G11WMY5AK9=tindakan-lainnya h_01HJJRRJCDZVFG9STE7PA38D4D=creating-a-new-collection h_01HJJRRJCDHMCWFBVRHYBS1D1N=downloading-a-collection h_01HJJRRJCDJ1201WPSMPMAJ6Q9=penting h_01HJJRRJCDPRV1DVSAGQRD4ANG=adding-links-to-a-collection h_01HJJRRJCDW88HYY4W7M2W5BD8=editing-links-in-a-collection h_01HJJRRJCDANN18DS1CEZS8001=viewing-the-collection-history h_01HJJRRJCDKAVCD4M8R187XER9=editing-the-collection-name h_01HJJRRJCD47RM4VYGN8TRJPHJ=deleting-empty-collections general-information=informasi-umum h_01HJJRRJCDR7MA544ZX324B4Y2=informasi-umum h_01HJJRRJCD2CHGKVSG22TKFMM9=catatan h_01HJJRRJCDCZ0ZBPZ2AH77JJTJ=upload-format h_01HJJRRJCDN5MWX72S9P37E69N=csv-parameters" />
