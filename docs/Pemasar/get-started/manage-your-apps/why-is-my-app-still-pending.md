---
title: Mengapa aplikasi saya masih tertunda?
metadata:
  keywords:
    - Google Play
    - App Store
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2018-10-14T07:22:04Z'
  edited_at: '2021-12-02T02:03:31Z'
  id: 360001533885
  locale: id
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/id/articles/360001533885
---
> **Sekilas:** Pantau status aplikasi yang menunggu publikasi (tertunda) ke app store dari dashboard AppsFlyer.

Saat Anda <Anchor target="_blank" href="/marketers/id/docs/adding-an-app-to-appsflyer">menambahkan aplikasi baru</Anchor> ke dashboard AppsFlyer, pertama-tama Anda memilih apakah status aplikasi tersebut tertunda atau sudah tersedia di market.

Aplikasi yang tertunda di AppsFlyer terlihat sama dengan aplikasi aktif. Aplikasi tersebut memiliki dashboard yang dapat diakses dan semua pengukuran atribusi berfungsi. Satu-satunya perbedaan adalah logo aplikasi yang ditampilkan dengan logo AppsFlyer, bukan logo aplikasi yang sebenarnya.

<Image align="center" alt="Pending_App.png" src="https://files.readme.io/fd280ea8dbcd280aae0a1328d1523f52c51d2f30dc163e7a62deb424ae5bc8ed-360001789338.png" />

<div id="whats-happening" />

## Apa yang terjadi?

AppsFlyer secara otomatis memeriksa status aplikasi beberapa kali sehari.

Jika aplikasi masih belum tersedia di toko saat AppsFlyer memeriksa status aplikasi, aplikasi akan muncul sebagai tertunda di dashboard. Setelah aplikasi akhirnya dikirimkan ke iTunes atau Google, aplikasi ini diperbarui statusnya menjadi aktif dan logo aplikasi berubah menjadi logo asli aplikasi.

Status aplikasi di dashboard tidak berpengaruh pada pengumpulan dan pengukuran data. Jika aplikasi aktif di Google Play atau App Store dan pengguna menginstal aplikasi dan berinteraksi dengannya, data penginstalan dan in-app event ditampilkan serupa.

<div id="refreshing-the-app-status" />

## Memuat ulang status aplikasi

Agar status aplikasi berubah menjadi aktif, AppsFlyer memeriksa statusnya di toko. Jika Anda yakin bahwa aplikasi telah dipublikasikan di Google Play atau iTunes, tetapi masih muncul sebagai tertunda di dashboard, admin dapat memeriksa statusnya secara manual.

**Prasyarat**: Tersedia untuk admin akun.

**Untuk memperbarui status aplikasi secara manual:**

1. Di dashboard, klik **My Apps (Aplikasi Saya)** di pojok kanan atas.  
   <Image align="center" alt="app-refersh-status.png" src="https://files.readme.io/d995ea3ee3523a8f0d4854f9ec116efc33c892694d56334c483b7d9fa6da8d64-360001704577.png" />
2. Di samping aplikasi yang tertunda, klik  **Refresh Status (Segarkan Status).**  
   Jika status aplikasi tidak berubah, aplikasi tetap ditampilkan sebagai Tertunda. Jika sudah diperbarui, statusnya ditampilkan sebagai Live (Aktif) dan logo diperbarui.

<div id="store-country" />

## Negara App Store

Beberapa aplikasi hanya tersedia di Google Play atau iTunes untuk negara tertentu. **Penting bahwa negara yang benar diatur untuk sebuah aplikasi** agar AppsFlyer dapat memeriksa dan memperbarui statusnya.

### iOS

Saat Anda <Anchor target="_blank" href="/marketers/id/docs/adding-an-app-to-appsflyer">menambahkan aplikasi iOS</Anchor> ke dashboard AppsFlyer, Anda memilih negara Apple Store tempat aplikasi tersebut dipublikasikan. Jika negara yang dipilih salah, AppsFlyer tidak dapat memperbarui status aplikasi meskipun telah dipublikasikan.

Untuk mengubah negara Apple Store:

1. Di dashboard aplikasi Anda, klik **App Settings (Pengaturan Aplikasi)** di menu sebelah kiri
2. Di bawah **App Store Country (Negara App Store)** pilih negara yang benar
3. Gulir ke bawah dan klik **Save Settings (Simpan Pengaturan)**
4. Jika aplikasi masih muncul sebagai tertunda, [klik **Refresh Status (Segarkan Status)**](/docs/why-is-my-app-still-pending#refreshing-the-app-status).

### Android

Saat Anda <Anchor target="_blank" href="/marketers/id/docs/adding-an-app-to-appsflyer">menambahkan aplikasi Android</Anchor> ke dashboard AppsFlyer Anda, tidak ada opsi untuk memilih negara Google Play dan secara default disetel ke AS. Jika aplikasi Anda tidak dipublikasikan di Google Play Store AS, penting untuk mengatur toko yang benar untuk aplikasi agar AppsFlyer dapat memeriksa dan memperbarui status aplikasi.

Untuk mengubah negara Google Play:

1. Di dashboard aplikasi Anda, klik **App Settings (Pengaturan Aplikasi)** di menu sebelah kiri
2. Di bawah **App Store Country (Negara App Store)** pilih negara yang benar
3. Gulir ke bawah dan klik **Save Settings (Simpan Pengaturan)**
4. Jika aplikasi masih muncul sebagai tertunda, [klik **Refresh Status (Segarkan Status)**](/docs/why-is-my-app-still-pending#refreshing-the-app-status).