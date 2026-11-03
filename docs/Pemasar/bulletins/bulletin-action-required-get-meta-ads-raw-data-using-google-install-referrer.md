---
title: >-
  Buletin: Diperlukan tindakan—Dapatkan data lengkap Meta ads menggunakan Google
  Install Referrer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-10-21T07:02:51Z'
  edited_at: '2023-11-27T05:34:07Z'
  id: 4409322107537
  locale: id
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/id/articles/4409322107537
---

<Table>
  <tbody>
    <tr>
      <td>
        **Kabar terbaru**
      </td>
      <td>
        Dapatkan data lengkap kampanye Meta ads dari iklan yang mengarah ke Google Play Store menggunakan Install Referrer.
      </td>
    </tr>
    <tr>
      <td>
        **Apa yang berubah**

        **![Information_icon.png](https://files.readme.io/cc1ff74668360a2be64ec90db8f771d751b0a95847ecaee582c2e31c60e310cf-20445036062993.png)**
      </td>
      <td>
        Mulai 29 Oktober 2021, data atribusi tingkat pengguna (data lengkap) pengguna yang dibawa oleh Meta ads **setelah** tanggal ini dibatasi. Meta ads membuat data ini tersedia untuk MMP seperti AppsFlyer, tetapi tidak untuk pemasang iklan.

        Namun, jika iklan mengarahkan pengguna ke Google Play Store, bidang atribusi tersedia untuk pengiklan di Google Install Referrer yang harus<Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">diintegrasikan ke aplikasi Anda.</Anchor> Bidang ini tersedia melalui pengarah yang mengisi laporan data lengkap AppsFlyer yang tersedia untuk Anda dan mengaktifkan AppsFlyer untuk mengatribusikan pengguna yang tidak memiliki ID iklan (LAT diaktifkan).

        Menggunakan mekanisme pengarah memerlukan AppsFlyer SDK V5.4+

        **Catatan:** Data perujuk lebih diprioritaskan daripada data yang disediakan oleh API dan tidak dibatasi.

        Data dalam perujuk dienkripsi oleh Meta ads dan didekripsi menggunakan kunci yang tersedia untuk Anda di akun pengembang Meta ads Anda. Anda harus memberi kami kode dekripsi seperti yang dijelaskan pada baris tindakan yang diwajibkan.

        **Bidang atribusi kampanye tersedia melalui referrer:**

        * ID iklan
        * Nama iklan
        * ID adset
        * Nama Adset
        * ID kampanye
        * Nama kampanye
        * ID Akun
        * Channel
        * Jenis iklan (bidang ini belum tersedia)

        **Perhatikan**:

        * Tidak ada bidang lain yang tersedia melalui pengarah.
        * Solusi ini berlaku untuk atribusi klik-tayang dan bukan atribusi lihat-tayang.
        * Data referrer tidak berlaku untuk kampanye interaksi ulang, karena pengguna tidak melalui toko.

        **Kapan AppsFlyer akan meluncurkan perubahan ini?**

        * Mulai 29 Oktober 2021
          * Pembatasan Meta ads untuk data klik-tayang (dengan kata lain data mentah atribusi) diterapkan.
          * Pengiklan dapat memperbarui kode dekripsi referrer di AppsFlyer.
        * Mulai 3 November, 2021
          * AppsFlyer mengisi data lengkap dan mengatribusi menggunakan data yang disediakan oleh mekanisme referrer.
      </td>
    </tr>
    <tr>
      <td>
        **Ringkasan ketersediaan data**
      </td>
      <td>
        <table><tbody><tr><th rowspan="2">Cara pengatribusian</th><th rowspan="2">Sumber data atribusi</th><th colspan="2">Data tersedia untuk pengiklan </th><th>Catatan</th></tr><tr><th>Data Lengkap</th><th>Data agregat</th><th> </th></tr><tr><td>Klik-tayang</td><td>Pengarah/Referrer (berlaku untuk aplikasi Android yang diunduh dari Google Play Store)</td><td>Tersedia</td><td>Tersedia</td><td><ul><li>Data atribusi pengguna LAT tersedia.</li><li>Pengarah lebih diprioritaskan daripada data MMP jika keduanya tersedia.</li><li>Tidak berlaku untuk kampanye interaksi ulang.</li></ul></td></tr><tr><td>Klik-tayang</td><td>API MMP</td><td>Dibatasi\*</td><td>Tersedia</td><td> </td></tr><tr><td>View-Through (Lihat-Tayang)</td><td>API MMP</td><td>Dibatasi\*</td><td>Tersedia</td><td>Mekanisme referrer tidak didukung.</td></tr><tr><td colspan="5"><p><strong>Catatan:</strong> Saat ketersediaan data dibatasi:</p><ul><li><ul><li>Instal dan postback in-app event hanya dikirim ke jaringan iklan yang membatasi. Mitra pihak ketiga, seperti mitra analitik, tidak mendapatkan postback untuk atribusi terbatas. </li><li>Postback tanpa atribut (tidak berisi bidang atribusi) dikirim ke jaringan iklan yang dikonfigurasi untuk menerima semua peristiwa (termasuk organik dan tanpa atribut). Ini termasuk mitra manajemen kampanye Meta.</li></ul></li></ul></td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        **Tindakan yang diperlukan**
      </td>
      <td>
        **Untuk mendapatkan kunci dekripsi Anda dari Meta ads:**

        [Informasi berikut didasarkan pada informasi yang diberikan oleh Facebook kepada kami]

        1. Masuk ke portal pengembang Meta Anda.
        2. Arahkan ke **My Apps)** (Aplikasi Saya) di pojok kanan atas.
        3. Pilih aplikasi yang ingin Anda akses kode dekripsinya.
        4. Arahkan ke **Settings**(Pengaturan) > **Basic**(Dasar) di sisi kiri halaman.

           [![FBUIforKey.png](https://files.readme.io/7581629ac17217154300bc796fd54416c1b04c08353b21ae7b93662fe182f694-4409669308049.png)](https://files.readme.io/7581629ac17217154300bc796fd54416c1b04c08353b21ae7b93662fe182f694-4409669308049.png)
        5. Gulir ke bawah ke bagian **Android**dan Anda akan melihat kode dekripsi Anda berlabel **kode dekripsi Install Referrer** di bawah bidang **Package Names**(Nama Paket). Catatan: Ini adalah bagian yang sama di mana Anda mengonfigurasikan nama paket dan Google Play Store.

        **Untuk mengaktifkan mekanisme pengarah/referrer di AppsFlyer.**

        1. [Wajib] Verifikasi bahwa Anda menggunakan SDK AppsFlyer V5.4+ di aplikasi Anda. Jangan gunakan versi sebelumnya.
        2. Lakukan salah satu dari berikut ini:
           1. [Segera hadir] Setel kode dekripsi melalui API.
           2. Untuk menyetel kode dekripsi melalui antarmuka pengguna:
              1. Di AppsFlyer, buka **Konfigurasi** > **Integrasi Aktif**.
              2. Pilih Meta ads.  

                 ![meta-ads-install-referrer-decryption-key.png](https://files.readme.io/adf6caa8d7cee493695eb8fb7db1b61c60e6a1cef0273e615c43a05ad8a9485d-13963525463825.png)
           3. Di tab **Integration)** (Integrasi), rekatkan kode di **Install Referrer** Decryption Key **(Kode Dekripsi Install Referrer)**.
           4. Klik **Save Integration (Simpan Integrasi)**.
      </td>
    </tr>
    <tr>
      <td>
        **Perbarui kode dekripsi melalui API**
      </td>
      <td>
        **[Segera hadir]**

        Kami akan merilis API yang memperbarui kunci dekripsi.
      </td>
    </tr>
    <tr>
      <td>
        **Ketersediaan data lengkap di masa mendatang**
      </td>
      <td>
        * Jika data atribusi diperoleh melalui mekanisme pengarah, data tidak dibatasi dan tersedia melalui laporan data lengkap.
        * Jika data atribusi diperoleh melalui API, maka data lengkap pengguna yang dibawa oleh Meta ads ditetapkan ke sumber media *yang dibatasi*
        * Perubahan ini tidak berdampak pada data lengkap pengguna yang dibawa sebelum perubahan. Atau sebelum 29 Oktober 2021, 08:00 UTC.
      </td>
    </tr>
    <tr>
      <td>
        **Apa yang tetap sama?**
      </td>
      <td>
        AppsFlyer terus menerima data tingkat perangkat dari Meta ads, yang berarti kemampuan atribusi dan pelaporan kami (termasuk atribusi multi-sentuh, LTV, ROI, kelompok, laporan retensi, perlindungan penipuan, Audiens, dan layanan lainnya) tetap tidak berubah. Lihat <Anchor target="_blank" href="/marketers/id/docs/aggregated-and-analytics-reporting-overview">alat pelaporan gabungan dan analitik</Anchor>.

        **Perhatikan**: Jika Anda memberi kami kode dekripsi, kami dapat mengatribusikan pengguna yang tidak memiliki ID iklan (LAT-diaktifkan). Ini meningkatkan akurasi atribusi.
      </td>
    </tr>
    <tr>
      <td>
        **Perubahan pada atribusi**
      </td>
      <td>
        Deep linking yang ditangguhkan melalui GCD akan tersedia untuk aplikasi Android menggunakan mekanisme Google Install Referrer. Ini tidak tersedia untuk aplikasi iOS.
      </td>
    </tr>
    <tr>
      <td>
        **FAQ**
      </td>
      <td>
        * **Apakah kode dekripsi pengarah instal perlu diperbarui?**  
          Setelah dikirimkan, kode dekripsi tidak perlu diperbarui.
        * **Kapan saya dapat melihat data tingkat pengguna dalam laporan data lengkap?**  
          Data tingkat pengguna ditampilkan dalam laporan data lengkap setelah kode dekripsi pengarah penginstalan yang valid dikirimkan dan penginstalan diatribusikan ke Meta ads.
        * **Apakah data atribusi tingkat pengguna tersedia untuk penginstalan yang terjadi antara 29 Oktober 2021 dan 3 November 2021?**  
          Sayangnya, data ini tidak tersedia.
      </td>
    </tr>
  </tbody>
</Table>
