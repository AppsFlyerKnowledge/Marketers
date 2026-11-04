---
title: Mengelola token API
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2020-01-01T09:50:22Z'
  edited_at: '2023-11-16T11:41:06Z'
  id: 360004562377
  locale: id
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/id/articles/360004562377
---
> **![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Sekilas:** Admin mengeluarkan token API untuk memungkinkan pengguna mengakses data melalui API AppsFlyer.

> 🚧 **Penting!**
>
> * Untuk memastikan keamanan data, hanya admin yang dapat melihat halaman token API. Artinya, pengguna akun dan mitra tidak memiliki akses ke halaman ini.
> * Amankan token Anda karena memungkinkan akses ke data Anda. Jangan publikasikan token di repositori kode publik.
> * Disarankan untuk menyetel ulang token API setiap 180 hari.

<div id="applications-of-the-api-v2-token" />

<div id="warning" />

<div id="delete-a-token" />

<div id="note-1" />

<div id="create-a-token" />

<div id="retrieve-tokens" />

## Mengambil token API

**Untuk mengambil token API:**

1. Dari bilah menu, akses menu pengguna (tarik-turun alamat email di pojok kanan atas).
2. Pilih **Security center.**
3. Di bagian **token API AppsFlyer** , klik **Manage your AppsFlyer API tokens.**
4. Token yang tersedia (V2.0) ditampilkan.
5. Salin token yang diperlukan.

## Menyetel ulang token API

> ❗️ **Perhatian**
>
> Jika Anda menyetel ulang token, token saat ini menjadi tidak valid dan token pengganti dikeluarkan. Untuk mencegah kehilangan data, segera sematkan token pengganti di skrip dan proses otomatis Anda.

**Untuk menyetel ulang token API:**

1. Dari bilah menu, akses menu pengguna (tarik-turun alamat email).
2. Pilih **Security center.**
3. Di bagian **token API AppsFlyer** , klik **Manage your AppsFlyer API tokens.**
4. Token yang tersedia (V2.0) ditampilkan.
5. Identifikasi token mana yang akan disetel ulang dan klik tautan **Setel ulang** **tokennya** .
6. Jika Anda ingin melanjutkan, klik **Setel ulang token** di kotak dialog.
7. Salin token baru.
8. Sematkan token pengganti dalam skrip dan proses otomatis yang memerlukan token.

## Jenis token diperlukan per API

<div id="advertiser-1" />

<div id="advertiser" />

### Token V2.0—API Pemasang Iklan

| API |
| --- |
| <Anchor target="_blank" href="/marketers/id/docs/pull-api-aggregate-data">Data lengkap Pull API</Anchor> |
| <Anchor target="_blank" href="/marketers/id/docs/pull-api-aggregate-data">data teragregasi Pull API</Anchor> |
| <Anchor target="_blank" href="/marketers/id/docs/app-list-api-for-app-owners">Dapatkan daftar aplikasi</Anchor> |
| <Anchor target="_blank" href="/marketers/id/docs/cohort-api">Kohort</Anchor> |
| <Anchor target="_blank" href="/marketers/id/docs/skan-aggregated-performance-report-api">Pelaporan agregasi SKAdNetwork</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_copy">Salin pengaturan integrasi mitra</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-integration-params">Tetapkan kunci dekripsi perujuk penginstalan</Anchor> |
| API pajak Pendapatan Sebenarnya |
| <Anchor target="_blank" href="/marketers/id/docs/send-opendsr-api-requests">API OpenDSR</Anchor> |
| <Anchor target="_blank" href="/marketers/id/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor> |

<div id="applications-for-the-mcp-token" />

<div id="applications-for-the-onelink-token" />

<div id="note-2" />

<div id="applications-of-the-s2s-token" />

<div id="ad-network-1" />

<div id="ad-network" />

### Token V2.0—API jaringan iklan

| API |
| --- |
| <Anchor target="_blank" href="/partners/id/docs/app-list-api-for-ad-networks">Daftar aplikasi untuk jaringan iklan</Anchor> |
| <Anchor target="_blank" href="/partners/id/docs/access-to-aggregated-analytics-tools-for-api-partners">Integrasi dengan platform manajemen kampanye</Anchor> |
| <Anchor target="_blank" href="/partners/id/docs/protect360-for-integrated-partners#protect360-ad-network-reporting-api">Laporan Protect360 untuk mitra terintegrasi</Anchor> |
| <Anchor target="_blank" href="/partners/id/docs/incost-api-for-ad-networks">InCost</Anchor> |

<div data-zendesk-anchors="h_01HBQN3T2HQKXZ0RC31DG28D6X=penting retrieving-api-tokens=mengambil-token-api h_01HBQN3T2HKEMNC8MSR0THYW2S=mengambil-token-api resetting-api-tokens=menyetel-ulang-token-api h_01HBQN3T2HM6NV4NW723YMNQ48=menyetel-ulang-token-api h_01HBQN3T2H58T5E075CZ14S9B9=perhatian token-type-required-per-api=jenis-token-diperlukan-per-api h_01HBQN7TBA4DX7HYMVK84SSNCP=jenis-token-diperlukan-per-api v20-token%E2%80%94advertiser-apis=token-v20api-pemasang-iklan h_01HBQN7TBASK192P8D7AEWM9P6=token-v20api-pemasang-iklan v20-token%E2%80%94ad-network-apis=token-v20api-jaringan-iklan h_01HBQN7TBAWAHEQXMYK9V14G0M=token-v20api-jaringan-iklan" />
