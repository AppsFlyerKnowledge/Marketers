---
title: 'Buletin: Perubahan token API'
metadata:
  keywords:
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2023-01-23T15:35:25Z'
  edited_at: '2023-09-27T11:34:07Z'
  id: 12399683708305
  locale: id
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/id/articles/12399683708305
---
| **Kabar terbaru** | Untuk memberikan pengalaman penggunaan API yang lebih aman dan andal, token API V1, yang disertakan dalam URL API, tidak digunakan lagi dan diganti dengan token API V2, yang merupakan token berbasis JWT yang diteruskan di header untuk otorisasi pembawa.<br /><br />Token API V1 dan API yang menggunakannya tidak lagi tersedia mulai 18 September 2023. |
| --- | --- |
| **Tanggal Efektif** | 18 September 2023 |
| **Prasyarat** | Hanya admin yang dapat <Anchor target="_blank" href="/marketers/id/docs/managing-appsflyer-tokens#mengambil-token-api">mengambil token API V2</Anchor> dari dashboard AppsFlyer. |
| **Siapa yang perlu memperbarui token API?** | Baik pemasang iklan maupun agensi yang masih menggunakan token API V1 perlu memperbarui token mereka. |
| **Cara menemukan token API V1** | Menggunakan <Anchor target="_blank" href="/marketers/id/docs/audit-log">Log audit</Anchor> untuk memfilter token API V1 apa pun yang masih digunakan. Anda kemudian dapat mengunduh data ke file CSV:<ol><li>Buka dashboard [log Audit](https://hq1.appsflyer.com/audit-reader/dashboard).</li><li>Ketik "API Token V1" di bilah pencarian.</li><li>Dalam filter **Pelayanan** , pilih saja **Panggilan API**, dan filter hasilnya.</li><li>Klik ikon Unduh dari kanan atas halaman.<br />File CSV Anda diunduh dan menyertakan ID aplikasi Anda, layanan yang digunakan, dan URL panggilan API.</li></ol> |
| **Tindakan yang diperlukan** | **Perbarui API berikut untuk token API V2:**<ol><li>Buka <Anchor target="_blank" href="https://hq1.appsflyer.com/account/api-tokens">halaman token API</Anchor>.</li><li>Di bawah API token V2.0, klik ikon **Salin ke clipboard** .</li><li>Untuk setiap API berikut:<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/master_api_get">Master API V2</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-11">Pull API Teragregasi V2</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">Data lengkap Pull API V2</Anchor></li></ul><ol><li>Ganti URL API V1 dengan URL dalam dokumentasi di atas.</li><li>Tempelkan token yang Anda salin ke header autentikasi Pembawa.<br />![token_v2_bearer.png](https://files.readme.io/edab36cc4a091da5b8e08d6b9a446f03e364398dbec2984a83212320a8bac5f0-15407883767313.png)</li><li>Untuk **OpenDSR API**, tempelkan token ke header pembawa permintaan:<br />`'Autorisasi': 'Pembawa %AuthTokenV2%'`</li></ol></li></ol> |
| **Tentang token API** | **Pelajari lebih lanjut tentang token API:**<ul><li><Anchor target="_blank" href="/marketers/id/docs/managing-appsflyer-tokens">Mengelola token API</Anchor><ul><li><Anchor target="_blank" href="/marketers/id/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/pull-api-aggregate-data">Pull API Teragregasi</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/pull-api-raw-data">Data Lengkap</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/send-opendsr-api-requests#format-permintaan-gdpr">API OpenDSR</Anchor></li></ul></li></ul> |