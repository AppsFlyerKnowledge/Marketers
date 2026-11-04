---
title: Tidak termasuk pengguna dari kampanye UA
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2020-05-03T10:11:31Z'
  edited_at: '2021-03-26T15:21:35Z'
  id: 360007949158
  locale: id
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/id/articles/360007949158
---
> **Sekilas:** Kecualikan pengguna yang ada dari kampanye akuisisi pengguna (UA) untuk mendapatkan lebih banyak penginstalan dengan anggaran yang sama dan meningkatkan ROAS.

<div id="issues-and-consequences" />

## Masalah dan konsekuensi

Jika aplikasi Anda menerima lalu lintas dari berbagai media source (sumber media), maka sumber ini dapat  menargetkan pengguna yang ada di kampanye UA mereka.

Kinerja kampanye dapat terganggu karena alasan berikut:

| Pembayaran ganda | Membayar untuk tayangan/klik pengguna yang Anda bayar di masa lalu. |
| --- | --- |
| Tingkat konversi terdistorsi | Kampanye UA tampaknya kurang berhasil. Ada lebih sedikit instalasi karena tayangan terbuang untuk pengguna yang ada. |
| Kehilangan pengguna alternatif | Non-pengguna bisa melihat iklan dan menjadi pengguna seluler Anda. |

<Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns#what-is-srn-mistargeting">Kesalahan penargetan SRN</Anchor> adalah masalah kinerja yang serupa dan umum. Masalah signifikan ini dapat terjadi jika kampanye UA dan penargetan ulang Anda memiliki SRN yang sama. <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns#apakah-salah-sasaran-merupakan-masalah">Pelajari lebih lanjut</Anchor>

<div id="solutions" />

## Solusi

Solusi ini menguraikan cara  memperbarui jaringan iklan untuk mengecualikan pengguna yang ada dari kampanye UA.

<div id="manual-update" />

### Pembaruan manual

Kumpulkan data lengkap penginstalan tingkat pengguna Anda dari AppsFlyer untuk membuat daftar ID perangkat. Lalu, kirim daftar ini ke jaringan iklan untuk memastikan pengecualian pengguna.

Ada beberapa cara untuk menambahkan data lengkap ini ke sistem BI Anda:

* Unduh laporan data lengkap
* Gunakan permintaan Pull API data lengkap secara berkala
* Gunakan Push API untuk mengimplementasikan pengumpulan waktu sebenarnya
* Dapatkan data konversi dari SDK

<div id="note" />

> 📘 **Catatan**
>
> Dalam jeda waktu antara mengirim daftar berikutnya ke jaringan iklan secara manual, kampanye UA dapat menargetkan pengguna aplikasi terbaru Anda.

### Audiences

**<Anchor target="_blank" href="/marketers/id/docs/audiences-guide">Audiens</Anchor>** adalah fitur premium AppsFlyer. Setiap hari, segmen yang dipilih dari basis pengguna Anda dikirim secara otomatis ke beberapa jaringan iklan, seperti yang Anda pilih.

**Audiens** sangat berguna untuk mempertahankan daftar pengecualian:

| Sedikit upaya | Tidak diperlukan pengembangan atau pemeliharaan oleh Anda atau jaringan iklan. |
| --- | --- |
| Mudah digunakan | Setelah pengaturan awal yang singkat, Anda dapat mulai mengunggah audiens. |
| Efisien | Segmen dikirim ke jaringan iklan secara otomatis setiap 24 jam. |