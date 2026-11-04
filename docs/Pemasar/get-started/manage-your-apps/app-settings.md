---
title: 'Pengaturan aplikasi  '
metadata:
  keywords:
    - App Settings
    - Advertisers
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
    - Platform essentials
    - Agencies
    - pm-guy-riesenberg
  created_at: '2016-08-16T07:50:37Z'
  edited_at: '2023-10-27T14:55:10Z'
  id: 211719806
  locale: id
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/id/articles/211719806
---
> **Sekilas:** Pelajari tentang pengaturan yang memengaruhi atribusi dan analitik aplikasi Anda di seluruh sumber media.

<div id="note" />

<div id="app-settings" />

## Pengaturan aplikasi

**Mengakses:**

* Admin (atau pengguna lain dengan izin yang sesuai) dapat **mengubah** pengaturan aplikasi.
* Semua pengguna akun dengan akses ke aplikasi tertentu dapat **melihat** pengaturan aplikasinya.

**Untuk mengubah atau melihat pengaturan aplikasi:**

1. Di AppsFlyer, buka ***Configuration (Konfigurasi)*** > ***App Settings (Pengaturan Aplikasi).***
2. Lihat pengaturan dan buat perubahan sesuai kebutuhan di laman Pengaturan Aplikasi.
3. Klik **Simpan Pengaturan**.

<div id="minimum-time-between-sessions" />

<div id="general-app-settings" />

### Pengaturan aplikasi umum

<Table>
  <thead>
    <tr>
      <th>
        Pengaturan
      </th>
      <th>
        Deskripsi
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="sdk-authentication-dev-key"></span>
        Autentikasi SDK: Kode pengembang
      </td>
      <td>
        * Kode pengembang mengautentikasi event yang dikirim oleh aplikasi atau oleh S2S ke AppsFlyer.
        * Kode ini unik per akun dan digunakan oleh semua aplikasi di akun.
        * Kunci tersedia di halaman Pengaturan Aplikasi untuk setiap pengguna akun yang memiliki akses ke aplikasi tersebut.
        * [Opsional] Kunci aplikasi individual dapat dialokasikan pada skenario tertentu. Hubungi CSM Anda untuk membahas hal ini.
      </td>
    </tr>
    <tr>
      <td><span id="aggregated-advanced-privacy-ios-apps"></span>
        Privasi Tingkat Lanjut Gabungan (aplikasi iOS)
      </td>
      <td>
        Saat diaktifkan, data atribusi tingkat pengguna tidak tersedia untuk pemasang iklan. Postback dan data event yang dibagikan dengan mitra bersifat agregat dan anonim (lebih lanjut tentang kerangka kerja <Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework">Privasi Lanjutan Gabungan</Anchor> ).

        Jika dinonaktifkan, data atribusi tingkat pengguna tersedia untuk semua mitra sebagai data gabungan dan dapat ditetapkan untuk setiap mitra satu per satu.
      </td>
    </tr>
    <tr>
      <td><span id="analytics-define-loyal-user-trigger"></span>
        Analitik: Tentukan pemicu pengguna setia
      </td>
      <td>
        * Pemicu untuk menandai pengguna sebagai pengguna setia. Opsi default yang ditentukan saat Anda menambahkan aplikasi adalah tiga aplikasi terbuka.
        * Setelah mengatribusi in-app event, Anda dapat menggunakan in-app event sebagai event pemicu.
          * [Default] 3 aplikasi dibuka.
          * Pengaturan pengguna setia merupakan indikasi kualitas pengguna. Pertimbangkan untuk menggunakan <Anchor target="_blank" href="/marketers/id/docs/protect360-anti-fraud-guide#faq">Protect360</Anchor> untuk memberantas fraud.
          * Mengubah pengaturan ini memengaruhi data secara retroaktif, yang artinya data historis pengguna setia dihitung ulang.
      </td>
    </tr>
    <tr>
      <td><span id="app-store-country"></span>
        App Store Country
      </td>
      <td>
        Atur negara app store di mana aplikasi itu tersedia. Pengaturan ini memengaruhi aplikasi seperti yang dijelaskan di sini.

        * **Mengubah status aplikasi dari tertunda ke aktif**:
          * <Anchor target="_blank" href="/marketers/id/docs/why-is-my-app-still-pending">Saat aplikasi diaktifkan</Anchor>, AppsFlyer memeriksa store menggunakan pengaturan negara untuk mengambil rincian tentang aplikasi seperti ikonnya.
          * Jika aplikasi tidak ditemukan di pengaturan negara app store, AppsFlyer tidak dapat mengubah status aplikasi dari tertunda ke aktif.
        * Perilaku pengarahan dipengaruhi oleh pengaturan, tergantung pada skenario, seperti dijelaskan pada tabel berikut.

        | Jenis pengguna | Skenario pengarahan |
        | --- | --- |
        | <span id="mobile"></span>Seluler | Pengguna biasanya mengklik tautan atribusi dalam aplikasi seluler lainnya. Saat mengklik, sistem operasi menentukan negara app store di mana pengguna diarahkan:  <br /><br />* **Android** mengarahkan berdasarkan IP pengguna/lokasi.<br />* **iOS** mengarahkan ke app store yang terkait dengan akun iTunes yang aktif di perangkat. |
        | <span id="mobile-and-web"></span>Seluler dan web | Saat pengguna web mengklik tautan atribusi, di **situs web** (seluler dan desktop), pengarahan awal adalah ke app store yang diatur di negara app store.<br /><br />Pada upaya instalasi, sistem operasi mengarahkannya ke negara app store seperti dijelaskan untuk seluler di baris sebelumnya. |
        | <span id="ipad-ios-13"></span>iPad iOS 13 | Mulai dari iOS 13, <Anchor target="_blank" href="https://www.apple.com/ipados/features/">iPads mendukung versi desktop situs web</Anchor>. Ini berarti bahwa jenis pengguna (seluler atau web) tidak relevan. Klik pada tautan atribusi mengarah ke situs desktop, dan setelahnya, aturan pengarahan adalah milik pengguna web. |
      </td>
    </tr>
    <tr>
      <td><span id="localization-time-zone"></span>
        Pelokalan: Zona Waktu
      </td>
      <td>
        Pengaturan aplikasi default adalah UTC. <Anchor target="_blank" href="/marketers/id/docs/changing-app-time-zone-settings">Tentang zona waktu aplikasi.</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="localization-currency"></span>
        Pelokalan: Mata uang
      </td>
      <td>
        Pengaturan aplikasi default adalah USD.

        * Tersedia opsi perubahan mata untuk aplikasi tanpa pendapatan atau biaya.
        * Untuk aplikasi baru, mata uang diatur saat aplikasi ditambahkan.

        <div id="reporting-tools-impacted-by-app-currency" />

        #### Alat pelaporan yang dipengaruhi oleh mata uang aplikasi

        | Alat pelaporan | Tersedia opsi mata uang |
        | --- | --- |
        | <span id="dashboards"></span>Dashboard | Mata uang khusus aplikasi |
        | <span id="export-data-page"></span>Halaman ekspor data | Mata uang khusus aplikasi |
        | <span id="push-api"></span>Push API | Mata uang khusus aplikasi dan USD tersedia secara bersamaan |
        | <span id="pull-api"></span>Pull API | Data agregat: Mata uang khusus aplikasi<br /><br />Data lengkap: USD yang dapat dipilih atau mata uang khusus aplikasi |
        | <span id="master-api"></span>Master API | USD yang dapat dipilih atau mata uang khusus aplikasi |
        | <span id="data-locker"></span>Data Locker | Hanya USD |
      </td>
    </tr>
  </tbody>
</Table>

<div id="minimum-time-between-reengagement-conversions" />

<div id="note-1" />

<div id="attribution-settings" />

### Pengaturan atribusi

| Pengaturan | Deskripsi |
| --- | --- |
| <span id="reattribution-window"></span>Periode Waktu Re-attribution | <Anchor target="_blank" href="/marketers/id/docs/set-up-re-attribution-window">Jendela atribusi ulang</Anchor> adalah periode yang dimulai dari tanggal instalasi pertama, di mana instalasi ulang tidak dapat diatribusi sebagai instalasi baru.<ul><li>[Default] Tiga bulan</li><li>Rentang nilai: 1-24 bulan</li></ul> |
| <span id="viewthrough-attribution-via-probabilistic-modeling"></span>Atribusi view-through (lihat-tayang) melalui pemodelan probabilistik | <ul><li>[Praktik terbaik] Aktifkan pemodelan probabilistik atribusi lihat-tayang selain atribusi klik-tayang yang selalu diaktifkan.</li><li>Setelah mengaktifkan pemodelan probabilistik lihat-tayang, Anda juga harus mengaktifkan atribusi lihat-tayang di tab integrasi jaringan iklan.</li></ul> |
| <span id="reengagement-attribution"></span>Atribusi interaksi ulang | Bacaan terkait: <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide">Panduan penargetan ulang</Anchor><br /><br />**Untuk mengaktifkan atribusi interaksi ulang:**<ul><li>Buka **Pengaturan** > **Pengaturan aplikasi**, aktifkan **Atribusi interaksi ulang**.</li></ul>Selain pengaturan aplikasi, Anda juga harus <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide#retargeting-settings">membuat pengaturan per mitra</Anchor>.<br /><br />**<Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide#jendela-eksklusi">Waktu minimum antara konversi interaksi ulang</Anchor>** pengaturan digunakan untuk mencegah berakhirnya jendela sebelum durasi yang ditentukan. |
| <span id="organic-search-seo-mobile-app-attribution"></span>Atribusi aplikasi seluler penelusuran organik (SEO). | Bacaan terkait: <Anchor target="_blank" href="/marketers/id/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">Atribusi pencarian organik</Anchor><br /><br />**Untuk mengaktifkan atribusi pencarian organik:**<ul><li>Buka **Pengaturan** > **Pengaturan aplikasi**, aktifkan **Atribusi aplikasi seluler penelusuran organik (SEO)**.</li></ul> |
| <span id="uninstall-measurement"></span>Pengukuran Uninstall | Pengukuran uninstall berkaitan dengan penginstalan yang terjadi saat pengukuran uninstall aktif.<br /><br />**Untuk mengaktifkan pengukuran uninstal:**<ol><li>Selesaikan per sistem operasi berikut ini:<ul><li>**iOS**: Aplikasi yang menerapkan fitur atribusi uninstall iOS harus mengunggah sertifikat P12 di sini.</li><li>Aplikasi**Android** memerlukan Kode Server Firebase/GCM yang akan ditentukan di sini untukatribusi uninstall Android.</li></ul></li><li>Aktifkan**Uninstall pengukuran**.</li><li>Klik **Simpan Pengaturan**.</li></ol>**Untuk menghentikan pengukuran uninstall:**<ol><li>Matikan **Uninstall pengukuran** .</li><li>Klik **Simpan Pengaturan**.</li></ol> |

<div id="advanced-settings" />

### Pengaturan lanjutan

| Pengaturan | Deskripsi |
| --- | --- |
| <span id="mask-ip-address-in-raw-data-reports"></span>Alamat IP Mask | Ketika diaktifkan, <Anchor target="_blank" href="/marketers/id/docs/apply-ip-masking-to-user-data">alamat IP perangkat pengguna akhir akan disamarkan</Anchor> dalam laporan data lengkap dan dalam postback yang dikirim ke mitra dari aplikasi yang saat ini dipilih. |
| <span id="reinstall-detection-using-ondevice-storage-ios-only"></span>Instal ulang deteksi menggunakan penyimpanan di perangkat (khusus iOS) | Mendeteksi penginstalan ulang tanpa bergantung pada ID iklan. Ini dilakukan dengan menyimpan tanggal penginstalan aplikasi terakhir di penyimpanan lokal aman di perangkat (di iOS, Keychain). Menentukan apakah penginstalan merupakan penginstalan ulang atau penginstalan baru, memungkinkan Anda menghapus duplikat penginstalan ulang dari NOI Anda, membuat analitik atribusi lebih akurat. |
| <span id="ios-103-redirect-fallback"></span>Fallback pengarahan iOS 10.3 | [Tidak digunakan lagi] Untuk iOS 10.3+. Kami menyederhanakan alur untuk pengguna iOS dan parameter ini tidak digunakan lagi. <Anchor target="_blank" href="/marketers/id/docs/uri-scheme-fallback-for-ios">pengalihan iOS</Anchor>.<br /><br />Opsi ini hanya tersedia untuk aplikasi iOS. |
| <span id="change-app-name"></span>Ubah nama aplikasi | <ul><li>Nama aplikasi, yang kemudian ditampilkan di semua dashboard dan laporan data. Ini berguna jika Anda memiliki versi berbeda dari aplikasi yang sama, misalnya, untuk alasan distribusi regional.</li><li>Perubahan ini memengaruhi tampilan aplikasi. ID aplikasi, yang digunakan untuk mengidentifikasi aplikasi saat menggunakan berbagai API AppsFlyer, **tetaplah sama**.</li><li>Nama dibatasi hingga 50 karakter.</li></ul> |
| <span id="outofstore-app-url"></span>URL aplikasi out of store | <ul><li>Setel URL unduhan aplikasi yang digunakan untuk mengisi tautan atribusi.</li><li>Pengaturan ini tidak mengubah tautan atribusi yang dibuat sebelumnya.</li></ul>**Batasan**: Opsi tidak ditampilkan sama sekali jika Anda tidak mengatur URL saat menambahkan aplikasi. Dalam hal ini, tanyakan kepada CSM atau hubungi [hello@appsflyer.com](mailto:hello@Appsflyer.com) untuk melakukan pengaturan untuk Anda.<br /><br />Opsi ini hanya tersedia untuk aplikasi Android. |

<div id="see-also" />

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide">Pedoman Atribusi Penargetan Ulang</Anchor>
> * <Anchor target="_blank" href="/marketers/id/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">Atribusi penelusuran organik</Anchor>

<div data-zendesk-anchors="app-settings=pengaturan-aplikasi 01ECHQME56X51MDW9TMA6DBNCK=pengaturan-aplikasi general-app-settings=pengaturan-aplikasi-umum h_01HAVS8CVPQKSDKCEM3YHHJ99Y=pengaturan-aplikasi-umum reporting-tools-impacted-by-app-currency=alat-pelaporan-yang-dipengaruhi-oleh-mata-uang-aplikasi h_01HAVS8CVQESWAQXKDW5SNVHCJ=alat-pelaporan-yang-dipengaruhi-oleh-mata-uang-aplikasi attribution-settings=pengaturan-atribusi h_01HAVS8CVQN1YYTT7S49VGB3J0=pengaturan-atribusi advanced-settings=pengaturan-lanjutan h_01HAVS8CVQTKXVXSMT5KNYZ3T4=pengaturan-lanjutan h_01HDPCC9465DR4A3CCXYQC2M56=lihat-juga" />
