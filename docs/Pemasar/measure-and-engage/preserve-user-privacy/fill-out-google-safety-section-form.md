---
title: Formulir bagian keamanan Google
metadata:
  keywords:
    - Google Play
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-19T15:00:21Z'
  edited_at: '2023-10-27T14:54:44Z'
  id: 4417197430289
  locale: id
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/id/articles/4417197430289
---
> **Sekilas**: Mulai April 2022, pengembang aplikasi diwajibkan untuk melengkapi formulir bagian keamanan Data Google Play dan mempublikasikan tautan ke kebijakan privasi, meskipun mereka tidak mengumpulkan jenis data apa pun yang ditentukan oleh Google. Halaman ini dimaksudkan untuk memberikan informasi guna membantu Anda menjawab Kuesioner Bagian Keamanan Google, hanya terkait dengan apa yang diproses AppsFlyer atas nama pelanggan.

Pelanggan harus bekerja sama dengan penasihat hukum dan profesional lainnya untuk menentukan dengan tepat bagaimana kebijakan Google berlaku untuk mereka dan harus menyesuaikan tanggapan mereka sesuai dengan konfigurasi dan penggunaan khusus mereka.

<div id="disclaimer" />

#### **Penafian**

Informasi yang ada dalam artikel ini dimaksudkan untuk membantu menjawab Kuesioner Bagian Keamanan Google **hanya** terkait dengan apa yang diproses AppsFlyer atas nama pelanggan.

Ini disediakan untuk tujuan informasi dan kenyamanan saja. Pelanggan harus bekerja sama dengan penasihat hukum dan profesional lainnya untuk menentukan dengan tepat bagaimana kebijakan Google berlaku untuk mereka dan harus menyesuaikan tanggapan mereka sesuai dengan konfigurasi dan penggunaan khusus mereka.

<div id="introduction" />

## Pengantar

Mulai April 2022, pengembang aplikasi diwajibkan untuk memberikan informasi terkait praktik privasi mereka melalui bagian keamanan khusus Google. Secara khusus, pengembang aplikasi harus memberikan informasi tentang data yang mereka kumpulkan, cara penanganan, dan pembagiannya, termasuk melalui penggunaan SDK pihak ketiga mana pun.

Informasi yang diberikan oleh setiap aplikasi akan ditampilkan di store listing Google untuk membantu pengguna akhir lebih memahami praktik privasi aplikasi.

<div id="audience" />

## Audiens

Semua pengembang aplikasi akan diwajibkan untuk mengisi kuesioner bagian keamanan dan mempublikasikan tautan ke kebijakan privasi meskipun mereka tidak mengumpulkan jenis data apa pun yang ditentukan oleh Google.

<div id="google-safety-form-questionnaire" />

## Formulir keamanan Google (kuesioner)

Google telah menerbitkan formulir (kuesioner) yang harus diisi oleh pengembang aplikasi. Kuesioner mencakup bagian-bagian berikut:

* Pengumpulan dan keamanan data
* Jenis data
* Penggunaan dan penanganan data

Pengembang aplikasi harus terlebih dahulu menilai praktik pengumpulan dan penanganan data mereka sebelum menjawab kuesioner.

Sehubungan dengan penggunaan AppsFlyer, pengembang aplikasi diingatkan bahwa mereka memiliki kendali penuh atas cara mereka menerapkan dan mengonfigurasi AppsFlyer, termasuk data yang dikumpulkan dan cara penggunaannya. Oleh karena itu, setiap pengembang aplikasi mungkin memiliki jawaban yang berbeda atas kuesioner berdasarkan praktik data dan penggunaan AppsFlyer mereka.

Pengembang aplikasi harus menjawab kuesioner sesuai dengan kasus penggunaan, konfigurasi, dan integrasi mitra khusus mereka.

<div id="data-collection-and-security" />

### Pengumpulan dan keamanan data

Di bagian ini, Anda akan ditanyai beberapa pertanyaan umum ya/tidak:

1. Apakah aplikasi Anda mengumpulkan atau membagikan salah satu jenis data yang diperlukan?
2. Apakah semua data pengguna yang dikumpulkan oleh aplikasi Anda dienkripsi sebelum dikirim?
3. Apakah Anda menyediakan cara bagi pengguna untuk meminta penghapusan data mereka?

Sehubungan dengan penggunaan AppsFlyer Anda, AppsFlyer mengenkripsi semua data sebelum dikirim melalui SDK. AppsFlyer juga memberi pelanggan kemampuan untuk menghapus data pengguna akhir tertentu melalui kerangka kerja OpenGDPR-nya. Untuk jenis data yang dikumpulkan, lihat tabel di bagian [Jenis data](/docs/fill-out-google-safety-section-form#jenis-data).

<div id="data-types" />

### Jenis data

Di bagian ini, Anda akan diminta untuk memilih jenis data yang dikumpulkan dan menjawab hal berikut:

1. Apakah data dibagikan
2. Apakah data diproses secara sementara
3. Apakah data diwajibkan atau dapatkah pengguna akhir menolak pengumpulan data?
4. Tujuan

Tabel berikut mengasumsikan konfigurasi default software AppsFlyer. Pengembang aplikasi bertanggung jawab untuk memastikan bahwa mereka beradaptasi sesuai dengan konfigurasi dan penggunaan khusus mereka.

“Dikumpulkan” berarti data yang dikirimkan dari perangkat dengan cara apa pun (misalnya, tampilan web, atau SDK)..  Pengecualian adalah jika enkripsi end-to-end digunakan untuk membuat data tidak dapat dibaca oleh siapa pun.

| Jenis data | Pengumpulan data default AppsFlyer | Catatan |
| --- | --- | --- |
| Info Lokasi<ul><li>Perkiraan Lokasi</li><li>Lokasi tepatnya</li></ul> | Lihat catatan | Lokasi Tepat: Tidak<br /><br />Perkiraan Lokasi: Ya, alamat IP diterima dan dipetakan ke tingkat wilayah/kota. |
| Informasi pribadi<ul><li>Nama</li><li>Alamat Email</li><li>Pengidentifikasi pribadi (ID akun, nomor, atau nama)</li><li>Alamat</li><li>Nomor Telepon</li><li>Ras dan etnis</li><li>Keyakinan politik atau agama</li><li>Orientasi seksual atau identitas gender</li><li>Informasi pribadi lainnya</li></ul> | Lihat catatan | Informasi pribadi tidak boleh dikumpulkan, dan AppsFlyer membatasi pengumpulan data pribadi seperti nama dan alamat. Namun, jika pengembang aplikasi telah mengonfigurasi untuk mengirimkan email yang di-hash atau nomor telepon yang di-hash atau mereka telah mengonfigurasi ID akun pengguna pelanggan (CUID), mereka harus menjawabnya. |
| Informasi Keuangan<ul><li>Kartu kredit, kartu debit, atau nomor rekening bank</li><li>Riwayat pembelian</li><li>Informasi kredit</li><li>Informasi keuangan lainnya</li></ul> | No  <br />  <br />Opsional<br /><br />Tidak  <br />Tidak | Informasi keuangan seperti kartu kredit dan informasi kartu kredit tidak boleh dikumpulkan.<br /><br />Jika Anda mengukur pembelian dalam aplikasi (riwayat pembelian), Anda harus menjawab **Ya** |
| Kesehatan dan Kebugaran<ul><li>Informasi kesehatan</li><li>Informasi kebugaran</li></ul> | Tidak | Tidak boleh dikumpulkan |
| Pesan<ul><li>Email</li><li>Pesan SMS atau MMS</li><li>Pesan dalam aplikasi lainnya</li></ul> | Tidak | Tidak boleh dikumpulkan |
| Foto atau Video<ul><li>Foto</li><li>Video</li></ul> | Tidak | Tidak boleh dikumpulkan |
| File Audio<ul><li>Rekaman suara atau suara</li><li>File musik</li><li>File audio lainnya</li></ul> | Tidak | Tidak boleh dikumpulkan |
| Kalender<ul><li>Kalender acara</li></ul> | Tidak | Tidak boleh dikumpulkan |
| Aktivitas aplikasi<ul><li>Tampilan halaman dan ketukan dalam aplikasi</li><li>Riwayat pencarian dalam aplikasi</li><li>Aplikasi yang diinstal</li><li>Konten buatan pengguna lainnya</li><li>Tindakan lainnya</li></ul> | Lihat catatan | AppsFlyer secara default mengukur peluncuran aplikasi yang dapat dianggap sebagai tampilan halaman atau tindakan lainnya.<br /><br />Selanjutnya, jika Anda mengonfigurasi aplikasi untuk mengukur event dalam aplikasi tertentu, Anda harus menjawab Ya sesuai dengan konfigurasi Anda. |
| Penelusuran web | Tidak | Tidak boleh dikumpulkan |
| Info dan kinerja aplikasi<ul><li>Data crash</li><li>Diagnostik</li><li>Data kinerja aplikasi lainnya</li></ul> | Tidak<br /><br />Ya<br /><br />Ya | Waktu peluncuran atau tingkat baterai dapat diterima untuk tujuan deteksi penipuan |
| Perangkat atau pengenal lainnya<ul><li>Perangkat atau pengenal lainnya (misalnya, IMEI, MAC, dan ID Iklan)</li></ul> | OPSIONAL | ID iklan dikumpulkan saat dapat diakses |

## Berbagi data

“Berbagi/dibagikan” berarti transfer data ke pihak ketiga (baik di luar maupun di perangkat).

Pengecualian termasuk yang berikut:

* Transfer ke penyedia layanan yang memproses data atas nama Anda dan sesuai instruksi Anda
* Transfer yang diwajibkan untuk tujuan hukum (misalnya, sebagai tanggapan atas permintaan pemerintah)
* Tindakan pengguna akhir atau berdasarkan pengungkapan dan persetujuan dalam aplikasi yang jelas
* Data anonim

Penting untuk diperhatikan bahwa meskipun AppsFlyer hanya bertindak sebagai penyedia layanan atas nama Anda dan sesuai instruksi Anda, jika Anda berbagi data dengan jaringan pihak ketiga (misalnya, melalui postback, SRN, dan audiens ), ini akan dianggap berbagi data.  Oleh karena itu, setiap pengembang aplikasi perlu menilai konfigurasi dan integrasi mitranya serta meresponsnya dengan tepat.

<div id="ephemeral-processing" />

## Pemrosesan sementara

Pemrosesan sementara mengacu pada data yang diproses dalam memori, hanya untuk periode waktu yang diperlukan untuk memproses tindakan tertentu secara waktu aktual dan tidak untuk tujuan lain. Mengingat karakteristik layanan AppsFlyer, data yang diproses oleh AppsFlyer atas nama Anda tidak diproses secara sementara.

<div id="user-choice" />

## Pilihan pengguna

Secara umum, data yang dikumpulkan diperlukan untuk menyediakan layanan. Dengan demikian, pengembang aplikasi memiliki kemampuan untuk mengatur pengumpulan data apa pun ke kontrol menyetujui atau menolak.

<div id="purpose" />

## Tujuan

Google telah menyediakan daftar tujuan yang harus dipilih oleh pengembang aplikasi seperti yang dijelaskan dalam tabel berikut. Anda harus mengidentifikasi tujuan yang relevan.

| Tujuan | Catatan |
| --- | --- |
| Fungsionalitas aplikasi | Pilih jika Anda menggunakan data untuk mengaktifkan fitur apa pun di aplikasi |
| Analisis | Ya |
| Komunikasi pengembang | Pilih jika Anda menggunakan data untuk mengirim pemberitahuan apa pun kepada pengguna |
| Periklanan dan Pemasaran | Pilih jika Anda berbagi jenis data dengan pihak ketiga untuk tujuan menampilkan iklan pihak ketiga atau jika digunakan untuk mempromosikan produk atau mengirim notifikasi push |
| Penipuan, pencegahan, keamanan, dan kepatuhan | Ya |
| Personalisasi | Pilih jika Anda menggunakan data untuk semua jenis personalisasi produk |
| Manajemen akun | Pilih jika Anda menggunakan data untuk pengaturan dan pengelolaan akun pengguna |

<div id="see-also" />

> 📄 **Lihat juga**
>
> Untuk mempelajari lebih banyak tentang persiapan bagian keamanan Google Play dan cara melengkapi formulir yang diperlukan, baca artikel berikut:
>
> * <Anchor target="_blank" href="https://android-developers.googleblog.com/2021/07/new-google-play-safety-section.html">Mempersiapkan bagian keamanan Google Play yang baru</Anchor>
> * <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/10787469">Memberikan informasi untuk bagian keamanan Data Google Play</Anchor>

<div data-zendesk-anchors="disclaimer=penafian h_01HDP3NTTKH3X3585J3DM6MCDC=penafian introduction=pengantar h_01HDP3NTTK1BDTZTHNWRM3411D=pengantar audience=audiens h_01HDP3NTTKQE2N0HZDNGK2ZQPC=audiens google-safety-form-questionnaire=formulir-keamanan-google-kuesioner h_01HDP3NTTKK6DJSF49326V3BEG=formulir-keamanan-google-kuesioner data-collection-and-security=pengumpulan-dan-keamanan-data h_01HDP3NTTK89K8YPT6C7S9QM3W=pengumpulan-dan-keamanan-data data-types=jenis-data h_01HDP3NTTK9DYZTQ2B64QMKGX8=jenis-data data-sharing=berbagi-data h_01HDP3NTTKF5PQ1N8VBTMB1W2Z=berbagi-data ephemeral-processing=pemrosesan-sementara h_01HDP3NTTKT7C0TGVCZJ4GR9BF=pemrosesan-sementara user-choice=pilihan-pengguna h_01HDP3NTTK4CT8MJ1S84MAG8VD=pilihan-pengguna purpose=tujuan h_01HDP3NTTKD3MND388MWCC6PAT=tujuan h_01HDP3RBENN69F150ESQMSVP3Q=lihat-juga" />
