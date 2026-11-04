---
title: Mempersiapkan peninjauan App Store — label nutrisi
metadata:
  keywords:
    - iOS
    - iTunes
    - Apple
    - IDFA
    - Guidelines
    - IFA
    - Ad Tracking
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2014-04-12T13:28:26Z'
  edited_at: '2023-11-03T08:08:06Z'
  id: 207032086
  locale: id
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/id/articles/207032086
---
> **Sekilas**: Saat memulai iOS 14 pengembang aplikasi harus menyediakan informasi App Store terkait dengan Praktik Privasi mereka saat mengirimkan aplikasi. App Store menerbitkan praktik dalam format *label nutrisi.*

**Sepatah kata dari pengacara kami:** *Tidak ada yang dinyatakan di sini adalah nasihat hukum. Ini disediakan untuk informasi dan kenyamanan Anda. Anda harus bekerja sama dengan penasihat hukum dan profesional lainnya untuk menentukan dengan tepat bagaimana kebijakan Apple berlaku untuk Anda.*

<div id="nutrition-labels-and-the-app-store-review" />

## Label nutrisi dan tinjauan App Store

* Untuk membuat label privasi, pengembang aplikasi harus menjawab kuesioner saat mengirimkan aplikasi mereka ke App Store Connect yang meliputi bagian berikut:
  * Jenis data yang dikumpulkan
  * [Tujuan pengumpulan data](/docs/preparing-for-the-app-store-review-nutrition-labels#tujuan-penggunaan-data)
  * [Jika jenis data terhubung ke identitas](/docs/preparing-for-the-app-store-review-nutrition-labels#data-terhubung-ke-identitas)
  * Jika data digunakan untuk pengukuran (termasuk kaitannya dengan layanan pihak ketiga mana pun atau SDK yang termasuk dalam aplikasi).
* Pengembang aplikasi:
  * Memiliki kontrol penuh terkait cara menerapkan dan mengonfigurasi software AppsFlyer, data apa yang dikumpulkan, dan bagaimana data digunakan.
  * Mungkin memiliki jawaban berbeda untuk kuesioner berdasarkan cara mereka mengonfigurasi software AppsFlyer dan poin data yang mereka pilih untuk dikumpulkan.
* Menurut pemahaman AppsFlyer tentang kebijakan Apple, AppsFlyer tidak melakukan *pengukuran.* Oleh karena itu, pengembang Aplikasi harus menjawab kuesioner sesuai dengan penggunaan khusus dan integrasi mitranya.
* Jika Anda menggunakan data yang dikumpulkan untuk tujuan pengukuran, Anda harus menerapkan prompt ATT.
* Berikut ini asumsi konfigurasi default perangkat lunak AppsFlyer. Pengembang aplikasi bertanggung jawab memastikan bahwa software tersebut beradaptasi sesuai dengan konfigurasi dan penggunaan spesifik mereka.

<div id="data-types-collected" />

#### Tipe data yang dikumpulkan

| **Jenis data** | **Pengumpulan data AppsFlyer** | **Catatan** |
| --- | --- | --- |
| **Informasi kontak**<ul><li>Nama</li><li>Alamat email (termasuk hashed)</li><li>Nomor telepon (termasuk hashed)</li><li>Alamat fisik</li><li>Informasi kontak pengguna lainnya</li></ul> | Tidak | Informasi kontak yang tidak boleh dikumpulkan. Namun, jika Anda mengonfigurasi aplikasi Anda untuk mengirimkan hashed email atau nomor telepon hashed, beri tanggapan yang sesuai di kuesioner App Store. |
| **Kebugaran** | Tidak | Jangan mengumpulkan |
| **Informasi keuangan**<ul><li>Informasi pembayaran</li><li>Informasi kredit</li><li>Informasi keuangan lainnya</li></ul> | Tidak | Jangan mengumpulkan |
| **Informasi lokasi**<ul><li>Lokasi tepatnya</li><li>Perkiraan lokasi</li></ul> | Lihat catatan | <ul><li>Lokasi tepat: Tidak</li><li>Perkiraan lokasi: Ya. Alamat IP dikumpulkan dan dipetakan ke perkiraan lokasi geografis.</li></ul> |
| **Informasi sensitif** | Tidak | Jangan mengumpulkan |
| **Kontak** | Tidak | Jangan mengumpulkan |
| **Konten pengguna**<ul><li>Email atau pesan teks (SMS)</li><li>Foto atau video</li><li>Data audio</li></ul> | Tidak | Jangan mengumpulkan |
| **Riwayat penjelajahan** | Tidak | Jangan mengumpulkan |
| **Riwayat pencarian** | Tidak | Jangan mengumpulkan |
| **Identifier**<ul><li>ID Pengguna</li><li>ID Perangkat (IDFA)</li></ul> | OPSIONAL | <ul><li>ID Pengguna: Pengembang aplikasi dapat mengatur dan mengirimkan ID pengguna (CUID)</li><li>ID Perangkat: ID Iklan (IDFA) dikumpulkan hanya jika dapat diakses.</li></ul> |
| **Pembelian**<ul><li>Riwayat pembelian</li></ul> | OPSIONAL | Pengembang aplikasi dapat memilih untuk mengonfigurasi event pembelian in-app tertentu untuk diukur. |
| **Data penggunaan**<ul><li>Interaksi produk</li><li>Data iklan</li><li>Data penggunaan lainnya</li></ul> | <ul><li>Ya</li><li>OPSIONAL</li><li>Tidak</li></ul> | <ul><li>Interaksi produk: Peluncuran aplikasi diukur, serta interaksi pengguna lainnya yang dikonfigurasi oleh pengembang aplikasi.</li><li>Data iklan: diterima jika pengembang aplikasi menggunakan modul pendapatan iklan AppsFlyer.</li></ul> |
| **Data diagnostik**<ul><li>Data crash</li><li>Data kinerja</li><li>Data diagnostik lainnya</li></ul> | <ul><li>Tidak</li><li>Ya</li><li>Tidak</li></ul> | Waktu peluncuran dan/atau level baterai dapat diterima untuk deteksi penipuan. |
| **Data lainnya**<ul><li>Jenis data lainnya</li><li>IDFV</li></ul> | Ya | <ul><li>Informasi perangkat teknis (misalnya, OS, jenis perangkat, bahasa, ukuran layar, dll.) atau informasi jaringan (misalnya, alamat IP, agen pengguna HTTP) diterima oleh AppsFlyer.</li><li>AppsFlyer menerapkan ID penginstalan untuk setiap penginstalan aplikasi yang disebut AF ID.</li><li>IDFV dikumpulkan</li></ul> |

<div id="data-use-purposes" />

### Tujuan penggunaan data

Apple memiliki daftar tujuan yang harus dipilih pengembang aplikasi, seperti yang dijelaskan dalam tabel berikut. Anda harus mengidentifikasi tujuan yang relevan untuk setiap jenis data yang terkait dengan penggunaan khusus Anda.

| Tujuan data | Pemilihan berdasarkan pada cara penggunaan data dari AppsFlyer |
| --- | --- |
| Iklan pihak ketiga | Pilih jika Anda membagikan jenis data dengan pihak ketiga untuk tujuan menampilkan iklan pihak ketiga di aplikasi Anda. |
| Iklan atau pemasaran pengembang | Pilih jika Anda menggunakan untuk iklan pihak ketiga di aplikasi Anda (termasuk jika membagikan dengan pihak ketiga untuk menampilkan iklan Anda) atau untuk tujuan pemasaran lainnya. |
| Analisis | Ya |
| Personalisasi produk | Pilih jika Anda menggunakan data untuk personalisasi produk apa pun. |
| Fungsionalitas aplikasi | Ya |
| Tujuan lainnya | Pilih jika Anda menggunakan data untuk tujuan lain yang tidak dinyatakan sebaliknya. |

<div id="data-linked-to-an-identity" />

### Data terhubung ke identitas

Jenis data yang dikumpulkan melalui AppsFlyer biasanya terhubung ke pengenal seperti ID perangkat (jika ada), atau pengenal lainnya seperti ID yang diterbitkan pelanggan saat dikonfigurasikan.

Oleh karena itu, pengembang aplikasi harus memilih **Ya** saat ditanya apakah data terhubung ke identitas.

<div id="see-also" />

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy/">Kebijakan Privasi Layanan AppsFlyer</Anchor> : Bagaimana AppsFlyer menangani dan menggunakan data.
> * <Anchor target="_blank" href="https://developer.apple.com/app-store/app-privacy-details/">Rincian privasi aplikasi di App Store oleh Apple</Anchor>.

<div data-zendesk-anchors="nutrition-labels-and-the-app-store-review=label-nutrisi-dan-tinjauan-app-store h_01HE7T7J409620K5KX5XKPEQVZ=label-nutrisi-dan-tinjauan-app-store data-types-collected=tipe-data-yang-dikumpulkan h_01HE7T7J4004XVJTMF6S964DVB=tipe-data-yang-dikumpulkan data-use-purposes=tujuan-penggunaan-data h_01HE7T7J4098NNW8D0BCD3EFBJ=tujuan-penggunaan-data data-linked-to-an-identity=data-terhubung-ke-identitas h_01HE7T7J41BJG9GTBWMVKG7031=data-terhubung-ke-identitas h_01HE7TES34MEF1XR4B6BDEMJW4=lihat-juga" />
