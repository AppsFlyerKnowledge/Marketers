---
title: Halaman ekspor data lengkap
metadata:
  keywords:
    - ad networks
    - Advertisers
    - Agencies
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
    - Ad Networks
  created_at: '2020-05-11T22:25:33Z'
  edited_at: '2024-09-18T17:32:44Z'
  id: 360008613838
  locale: id
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/id/articles/360008613838
---
> **Sekilas:** Unduh laporan data lengkap dalam file CSV. Hingga 1 juta baris per pengunduhan. Batasi laporan ke data yang Anda butuhkan dengan menggunakan filter.

Visual berikut ditampilkan saat pertama kali Anda membuka halaman **Ekspor data lengkap**; halaman **Laporan saya** ditampilkan jika Anda memiliki laporan yang siap untuk diunduh atau diduplikasi.

[![RawDataSplash.png](https://files.readme.io/febb6a32a3a7b86c5b396cd77ff9e7968057f57ed20fd991d6dbb4899d5eaf07-41225791757969.png)](https://files.readme.io/febb6a32a3a7b86c5b396cd77ff9e7968057f57ed20fd991d6dbb4899d5eaf07-41225791757969.png)

**Laporan saya**

Halaman **Laporan saya** mencantumkan laporan yang dibuat sebelumnya dan siap diunduh, duplikasi, atau keduanya. Laporan yang tercantum dibuat selama 90 hari sebelumnya. Periode pengunduhannya adalah 7 hari. Setelah 7 hari, jika Anda masih membutuhkan laporan tersebut, Anda harus membuatnya lagi.

Untuk deskripsi laporan data lengkap, lihat <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">Ikhtisar pelaporan data lengkap</Anchor>

Untuk membuat atau mengunduh laporan, lihat bagian prosedur dari artikel ini.

[![MyReportsRawDataExport.png](https://files.readme.io/1f82e365a7e6cd802ee899666b800be357ea5e99aa6909e75b1fa39a2e4a164e-41225791760145.png)](https://files.readme.io/1f82e365a7e6cd802ee899666b800be357ea5e99aa6909e75b1fa39a2e4a164e-41225791760145.png)

<div id="raw-data-export-page-features-and-filter-options" />

<Accordion title="Fitur halaman ekspor data lengkap dan opsi filter">

Halaman ekspor data lengkap menyediakan laporan yang memiliki fitur-fitur yang tercantum dalam tabel berikut.

<Table>
  <thead>
    <tr>
      <th>
        Fitur
      </th>
      <th>
        Catatan
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="report-categories"></span>
        Kategori laporan
      </td>
      <td>
        Berbeda sesuai dengan paket langganan Anda
      </td>
    </tr>
    <tr>
      <td><span id="date-range"></span>
        Rentang tanggal
      </td>
      <td>
        Laporan data lengkap difilter berdasarkan tanggal aktivitas (kejadian peristiwa). Anda juga dapat menambahkan filter untuk tanggal penginstalan. Lihat daftar opsi filter dalam tabel berikut.
      </td>
    </tr>
    <tr>
      <td><span id="maximum-number-of-rows"></span>
        Jumlah baris maksimum
      </td>
      <td>
        Baris 1 Juta
      </td>
    </tr>
    <tr>
      <td><span id="rate-limitation"></span>
        Batasan tingkat
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/id/docs/report-generation-quotas-rate-limitations">Mekanisme kuota</Anchor> membatasi jumlah laporan yang dapat dihasilkan per hari.
      </td>
    </tr>
    <tr>
      <td><span id="retentionreport-window"></span>
        Periode waktu retensi/laporan
      </td>
      <td>
        Laporan terkait penginstalan (penginstalan, postback penginstalan) **60** dari 90 hari sebelumnya dalam satu pengunduhan.

        Laporan terkait in-app event 31 dari 90 hari sebelumnya dalam satu pengunduhan.
      </td>
    </tr>
    <tr>
      <td><span id="filter-options"></span>
        Pilihan filter
      </td>
      <td>
        Filter yang tercantum tersedia untuk digunakan. Dalam beberapa kasus, tergantung pada filter, opsi filter diisi. Misalnya, saat memfilter berdasarkan Geo, daftar negara yang tersedia dicantumkan.
      </td>
    </tr>
    <tr>
      <td><span id="field-selection"></span>
        Pemilihan lapangan
      </td>
      <td>
        Bidang yang paling penting sudah dipilih sebelumnya. Anda dapat menambahkan/menghapus bidang yang dipilih di tab **Bidang laporan** . Beberapa bidang mungkin tidak memiliki relevansi dengan laporan tertentu. Namun demikian, Anda dapat memilih bidangnya. Kami melakukan ini agar Anda dapat memiliki format laporan yang konsisten (kolom)

        Misalnya, memilih bidang terkait penipuan (Protect360) dalam laporan in-app event akuisisi pengguna menghasilkan tampilan kolom kosong. Bidang-bidang ini hanya diisi dalam konteks laporan Protect360 eksplisit.
      </td>
    </tr>
    <tr>
      <td><span id="report-csv-field-order"></span>
        Urutan bidang laporan (CSV)
      </td>
      <td>
        Kolom dalam laporan diatur sesuai dengan pengaturan urutan bidang. Urutan kolom [yang tercantum dalam spreadsheetberisi](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGYcMOgC5yy_82yn3DWd3ucLE5KtuTA72eJfvu5KVB9fFH_mYwzM3KpR_inQOnat-KzgVjuuvXa6_g/pub?output=xlsx) tab terpisah untuk opsi legasi dan default.

        | Pengaturan | Pemilihan bidang diizinkan | Catatan |
        | --- | --- | --- |
        | <span id="default"></span>Default | Ya | * Bidang yang dipilih diurutkan sesuai dengan templat AppsFlyer.<br />* Ke depannya, urutannya akan dipertahankan. Bidang masa depan akan ditambahkan di sebelah kanan bidang yang sudah ada. |
        | <span id="alphabetical-az"></span>Abjad (A-Z) | Ya | Bidang yang dipilih diurutkan berdasarkan abjad (naik). |
        | <span id="alphabetical-za"></span>Alfabetis (Z-A) | Ya | Bidang yang dipilih diurutkan dalam urutan terbalik menurut abjad (menurun). |
        | <span id="legacy"></span>Legasi | Tidak | * Bidang diurutkan sesuai dengan urutan kolom dalam laporan yang disiapkan menggunakan versi sebelumnya dari halaman data ekspor.<br />* Pemilihan bidang sudah diperbaiki dan tidak dapat diubah.<br />* Ada beberapa variasi laporan per bidang tergantung pada laporan aktual |
      </td>
    </tr>
  </tbody>
</Table>

> 📘 **Catatan**
>
> Jika Anda menggunakan filter agensi dan filter sumber media, filter sumber media tidak berlaku untuk agensi yang tidak transparan. Ini berarti bahwa untuk lembaga non-transparan, semua data disertakan, bukan hanya data dari sumber media yang sudah difilter

| Filter | Pemasang iklan | Ad Network | Agensi |
| --- | --- | --- | --- |
| Sumber media | Ya | Tidak | Ya |
| Rentang tanggal aktivitas | Ya | Ya | Ya |
| Rentang tanggal penginstalan | Ya | Ya | Ya |
| Agensi | Ya | Tidak | Tidak |
| Geo (wilayah/negara) | Ya | Ya | Ya |
| In-app event (tersedia untuk laporan in-app event) | Ya | Tidak | Ya |

</Accordion>

<div id="note" />

<div id="procedures" />

## Prosedur

<div id="create-a-default-report" />

<Accordion title="Buat laporan default">

Anda dapat membuat laporan dengan pengaturan default tanpa menyesuaikan bidang atau filternya.

**Untuk membuat laporan default:**

1. Di AppsFlyer, dari menu samping, pilih **Ekspor** > **Ekspor Data Lengkap**
2. Klik + **Laporan baru**
3. Arahkan kursor pada jenis laporan yang ingin Anda buat dan klik **Buat.**
4. Pilih **Buat sekarang** dari menu drop-down.
5. Pada jendela popup, klik **Buat sekarang.** Pembuatan bisa memakan waktu hingga 10 menit.
   * Selama pembuatan laporan, Anda dapat terus bekerja, membuat laporan tambahan, atau menavigasi ke halaman lain.

**Pengaturan filter laporan default:**

| Filter | Pengaturan default |
| --- | --- |
| Tanggal kegiatan | 7 hari terakhir |
| Baris maksimum per file | 200.000 |
| Sumber media | Semua sumber media |
| Agensi | Semua Agensi |
| Geo | Semua wilayah geografis |

</Accordion>

<div id="create-a-custom-report" />

<Accordion title="Membuat laporan khusus">

Anda dapat membuat laporan khusus dengan mengatur filter dan bidangnya.

**Untuk membuat laporan khusus:**

1. Di AppsFlyer, dari menu samping, pilih **Ekspor** > **Ekspor Data Lengkap**
2. Klik + **Laporan baru**
3. Arahkan kursor pada jenis laporan yang ingin Anda buat dan klik **Buat.**
4. Pilih **Kustomisasi** dari menu drop-down.
5. Mengatur filter laporan
   * **Tanggal aktivitas:** Pilih rentang tanggal aktivitas. Anda dapat mengatur tanggal tertentu atau memilih dari opsi seperti kustom, kemarin, 7 hari terakhir, dan sebagainya.
   * **Baris maksimum per file:** [Opsional] Tetapkan jumlah maksimum baris yang dapat disertakan file. Pilih dari 100, 200 ribu, 500 ribu, atau 1 juta baris.
   * **Sumber media:** [Opsional] Hanya event yang dikaitkan dengan sumber media yang dipilih akan dimasukkan dalam laporan. Anda dapat menambahkan sumber media ke daftar dengan mengklik **Tambahkan item**.
   * **Agensi:** [Opsional] Hanya event yang dikaitkan dengan agensi yang dipilih akan dimasukkan dalam laporan. Anda dapat menambahkan agensi ke daftar dengan mengklik **Tambah item**.
   * **Geo:** [Opsional] Hanya event yang dikaitkan dengan wilayah geografis yang dipilih akan dimasukkan dalam laporan.
   * **Filter spesifik jenis laporan**: Setiap jenis laporan mungkin memiliki filternya sendiri dari mana Anda dapat memilih kriteria pemfilteran.
6. [Opsional]: Laporan diisi secara otomatis dengan bidang yang diperlukan. Anda dapat menambah atau menghapus bidang sebagai berikut:
   1. Buka tab **Laporkan bidang**. Daftar bidang yang dipilih lalu ditampilkan. Anda tidak dapat mengubah pilihan bidang wajib.
   2. Pilih atau hapus bidang yang dipilih sesuai kebutuhan.
   3. [Opsional] Atur **Urutan bidang Laporan (CSV)** untuk mengatur urutan kolom.
   4. [Opsi] Klik **Pulihkan default** jika diperlukan.
7. Klik **Buat.**
   * Halaman **Laporan saya** ditampilkan. Di awal, status menunjukkan bahwa laporan sedang dibuat.
   * Pembuatannya bisa memakan waktu hingga 10 menit.
   * Selama pembuatan laporan, Anda dapat terus bekerja, membuat laporan tambahan, atau menavigasi ke halaman lain.

</Accordion>

<div id="download-report" />

<Accordion title="Unduh laporan">

**Untuk mengunduh laporan**:

1. Verifikasi bahwa Anda berada di halaman **Ekspor Data Lengkap** . Jika perlu, navigasikan ke **Laporan** > **Ekspor Data Lengkap**.
2. Klik ![DownloadIcon.png](https://files.readme.io/6c00f4922fc3a835a856d7fdf527aa32d2f50570710c1527b039f43a7acbba79-41225791763217.png) (download), untuk mengunduh laporan. Laporan yang dibuat tersedia untuk diunduh selama 7 hari.

</Accordion>

<div id="duplicate-and-edit-report-settings" />

<Accordion title="Gandakan dan edit pengaturan laporan">

**Untuk menduplikasi dan mengedit pengaturan laporan:**

1. Verifikasi bahwa Anda berada di halaman **Ekspor Data Lengkap** .
2. Klik ![Duplicate.png](https://files.readme.io/f745081f1bf0c4f5861e275a29048fe84e8020f8b3bf4ebe4ad6a8d9254ab4b5-41225784681233.png) , untuk menduplikasi pengaturan laporan dan kemudian mengedit pengaturan.
3. Klik **Buat.** Laporan yang dibuat tersedia selama 7 hari.   
   * Halaman **Laporan saya** ditampilkan. Di awal, status menunjukkan bahwa laporan sedang dibuat.
   * Pembuatannya bisa memakan waktu hingga 10 menit.
   * Selama pembuatan laporan, Anda dapat terus bekerja, membuat laporan tambahan, atau menavigasi ke halaman lain.

</Accordion>

<div id="additional-information" />

## Informasi tambahan

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Karakteristik | Catatan |
| --- | --- |
| Akses jaringan iklan | Ya |
| Akses agensi | Ya |
| Transparansi agensi | Ya. Namun, perhatikan bahwa jika Anda menggunakan filter agensi dan filter sumber media, filter sumber media tidak berlaku untuk agensi yang tidak transparan. Ini berarti bahwa untuk agensi non-transparan, semua data disertakan; tidak hanya data dari sumber media yang sudah difilter. |
| Zona waktu khusus aplikasi | Ya |
| Mata uang khusus aplikasi | Ya |
| Batasan | Hingga 1 juta catatan per pengunduhan |
| Data organik | Tersedia |
| Data non-organik | Tersedia |
| Keaktualan data | Tergantung laporan |
| Data historis | 90 hari sebelumnya |
| Akses pengguna akun | Pengguna dalam <Anchor target="_blank" href="/marketers/id/docs/user-management">peran dengan izin yang diperlukan</Anchor> |
| Pengiriman email | Tidak didukung |
| Rentang tanggal penginstalan | Rentang tanggal penginstalan harus lebih awal dari rentang tanggal aktivitas. |
| Laporan postback data lengkap | Postback yang dikirim ke mitra karena event yang dikaitkan dengan agensi yang tidak transparan tidak dimasukkan dalam laporan Postback Data Lengkap Pemasang Iklan. |

</Accordion>

<div id="field-sequence-templates" />

<Accordion title="Templat urutan bidang">

Pengaturan urutan bidang Laporan memungkinkan Anda untuk menentukan urutan kolom dalam laporan, dan dalam beberapa kasus, bidang itu sendiri.

| Pengaturan | Pemilihan bidang diizinkan | Catatan |
| --- | --- | --- |
| <span id="default::b7bb6355"></span>Default | Ya | <ul><li>Bidang yang dipilih diurutkan sesuai dengan templat AppsFlyer.</li><li>Ke depannya, urutannya akan dipertahankan. Bidang masa depan akan ditambahkan di sebelah kanan bidang yang sudah ada.</li></ul> |
| <span id="alphabetical-az::b08af6b3"></span>Abjad (A-Z) | Ya | Bidang yang dipilih diurutkan berdasarkan abjad. |
| <span id="alphabetical-za::f0b3beb8"></span>Alfabetis (Z-A) | Ya | Bidang yang dipilih diurutkan dalam urutan menurut abjad yang terbalik |
| <span id="legacy::fb5fd8ec"></span>Legasi | Tidak | <ul><li>Bidang diurutkan sesuai dengan urutan kolom dalam laporan yang disiapkan menggunakan versi sebelumnya dari halaman data ekspor.</li><li>Pemilihan bidang sudah diperbaiki dan tidak dapat diubah.</li><li>Ada beberapa variasi laporan per bidang tergantung pada laporan aktual.</li></ul> |

[Spreadsheet](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGYcMOgC5yy_82yn3DWd3ucLE5KtuTA72eJfvu5KVB9fFH_mYwzM3KpR_inQOnat-KzgVjuuvXa6_g/pub?output=xlsx) ini berisi lembar Default dan Legasi. Masing-masing berisi daftar urutan bidang yang relevan.

**Untuk mengubah urutan bidang:**

1. Di tab bidang Laporan, pilih opsi **Urutan bidang laporan** .
2. Jika diperlukan, ubah bidang yang dipilih dengan memilih atau menghapus pilihan bidang yang diperlukan.

</Accordion>

<div data-zendesk-anchors="h_01HA28AT6QRSG68NBFYHH5SQY8=raw-data-export-page-features-and-filter-options h_01HA28CJ4W692V6EVC7XTQEZG6=catatan procedures=prosedur h_01HA28AT6Q9PV3M55C1YM3XN2E=prosedur h_01HZY1HQ9AVH6Q9QAQB4SM1VPX=create-a-default-report h_01HZY1HQ9ACEMZ4N8WPYNHZQP7=create-a-custom-report h_01HA28AT6QV1XP4N952PAEGSSG=download-report h_01HA28AT6QFT88RHJ3M05MV3B3=duplicate-and-edit-report-settings additional-information=informasi-tambahan h_01HA28AT6Q4DXKCZ22R9XEN2RR=informasi-tambahan h_01HA28AT6Q6SE8CB3EEXFMAN0H=traits-and-limitations h_01HA28AT6RW8C99ZGEBTN5E44R=field-sequence-templates" />
