---
title: 'Buletin: Dukungan SKAN 4 di AppsFlyer'
metadata:
  keywords:
    - iOS
    - Marketers
    - SKAN
    - SKAdNetwork (SKAN)
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2023-01-05T12:36:02Z'
  edited_at: '2023-08-21T03:00:02Z'
  id: 11938810583825
  locale: id
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/id/articles/11938810583825
---
| **Judul** | Solusi SKAdNetwork AppsFlyer sekarang mendukung SKAN 4. Ini termasuk perubahan besar pada Studio Konversi SKAN, serta dashboard dan laporan SKAN. |
| --- | --- |
| **Tanggal Efektif** | <ul><li>15 Februari 2023: Dengan iOS SDK V6.10+ asli</li><li>Kami menyarankan agar Anda memperbarui ke versi terbaru V6.12+, bahkan jika Anda menggunakan V6.10 sejak Februari<ul><li>Anda dapat melihat daftar perubahan <Anchor target="_blank" href="/marketers/id/docs/appsflyer-ios-sdk-release-notes">di sini</Anchor></li></ul></li><li>Segera hadir: Dukungan untuk SDK dan plugin AppsFlyer lainnya</li></ul> |
| **Prasyarat** | Agar data SKAN 4 iOS tercatat dengan baik, diperlukan hal-hal sebagai berikut:<ul><li><Anchor target="_blank" href="/marketers/id/docs/appsflyer-ios-sdk-release-notes">SDK AppsFlyer versi V6.12.1+</Anchor></li><li>Jaringan iklan harus membuat tanda tangan iklan untuk SKAdNetwork V4.</li><li>Untuk iklan yang ditampilkan di aplikasi, aplikasi harus dibuat dengan iOS 16.1 SDK atau lebih baru.</li><li>Untuk iklan web, iklan memerlukan Safari 16.1 atau lebih baru.</li><li>Aplikasi yang diiklankan harus bertanda App Store dan berjalan di perangkat dengan iOS 16.1 atau lebih baru.</li></ul> |
| **Tindakan yang diperlukan** | <ul><li>Tingkatkan <Anchor target="_blank" href="/marketers/id/docs/appsflyer-ios-sdk-release-notes">SDK AppsFlyer Anda ke V6.12.1+</Anchor></li><li>Di Studio Konversi SKAN AppsFlyer, tingkatkan ke <Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio#skan-4">mode pengukuran SKAN 4</Anchor> dan konfigurasikan CV untuk 3 jendela SKAN (atau pertahankan pengaturan default).</li></ul>**Catatan:** Setelah Anda melakukan upgrade ke SKAN 4:<ul><li>Timer aktivitas untuk penginstalan pra-SKAN 4 adalah 48 jam.</li><li>Anda tidak dapat kembali ke versi SKAN sebelumnya.</li></ul> |
| **Perubahan di <Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio#skan-4">Studio Konversi SKAN</Anchor>** | Mode pengukuran SKAN 4 baru untuk mengonfigurasi 3 jendela SKAN |
| **Perubahan di <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">dashboard</Anchor>** | <ul><li>Dashboard ikhtisar SKAN menyertakan kolom baru (tersedia di pengaturan tabel) untuk penghitungan event dan pendapatan selama 3 jendela SKAN:<ul><li>Jumlah event D0-D2</li><li>Jumlah event D0-D2 (dimodelkan)</li><li>Jumlah event D3-D7</li><li>Jumlah event D8-D35</li><li>Pendapatan D0-D2 ($)</li><li>Pendapatan D0-D2 ($) (dimodelkan)</li><li>Pendapatan D3-D7 ($)</li><li>Pendapatan D8-D35 ($)</li></ul></li><li>Tampilan dashboard SSOT menampilkan bidang data D2, bukan Jendela Aktivitas (AW). Untuk data SKAN 3, bidang ini menampilkan semua data jendela aktivitas, meskipun jendela tersebut lebih panjang atau lebih pendek dari 2 hari.</li></ul> |
| **Perubahan <Anchor target="_blank" href="/marketers/id/docs/skan-raw-data-reports">laporan</Anchor>** | <ul><li>Laporan SKAdNetwork mencakup bidang baru berikut untuk mendukung SKAN 4:<ul><li>**skad\_postback\_sequence\_index**: Nilai adalah bilangan bulat yang mewakili jendela SKAN, `0`,`1`, atau`2`. Untuk SKAN 3 nilainya adalah`0`.</li><li>**skad\_coarse\_conversion\_value**: Nilai bisa`rendah`,`sedang`, atau`tinggi`. Untuk SKAN 3 nilainya`null`.</li><li>**skad\_source\_identifier**: Nilai adalah string hingga 4 digit. Untuk SKAN 3 nilainya adalah`null`.</li><li>**skad\_source\_domain**: Nilai adalah string yang mewakili sumber iklan web yang dapat diatribusikan. Untuk SKAN 3 nilainya`null`.</li><li>**ad\_network\_creative**: Nilai adalah string berdasarkan pengayaan data yang diterima dari jaringan iklan. Untuk SKAN 3 nilainya kosong.</li></ul></li><li>Laporan Data Locker dan Push API berikut terpengaruh:</li></ul><ul><li>**skad\_installs** (melalui Data Locker dan Push API)</li><li>**skad\_redownloads** (melalui Data Locker dan Push API)</li><li>**skad\_inapps** (melalui Data Locker dan Push API)</li><li>**skad\_postbacks** (melalui Data Locker)</li><li>**skad\_postbacks\_copy** (tidak termasuk bidang ad\_network\_creative) (melalui Data Locker)</li><li><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQJzfkXrrdYU15SkRoEx2HlgezlNar76MHFMP1JWqNnGrtYuHFNz4Mf8u0diflSx-5-k0zfsMEzsuLS/pub?output=xlsx">Lihat skema laporan contoh</Anchor></li></ul><ul><li>API tanggal kedatangan postback gabungan SKAN dan API laporan kinerja gabungan SKAN berisi bidang SKAN 4. **Catatan**: Anda harus menggunakan jalur V2 API token untuk SKAN 4.</li></ul> |