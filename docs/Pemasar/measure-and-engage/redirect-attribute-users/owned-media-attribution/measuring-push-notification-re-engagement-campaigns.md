---
title: Mengukur kampanye interaksi ulang notifikasi push
metadata:
  keywords:
    - Re-Engagement
    - push
    - notifications
    - Advertisers
    - Developers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2016-01-18T10:03:11Z'
  edited_at: '2023-02-15T14:42:26Z'
  id: 207364076
  locale: id
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/id/articles/207364076
---
> **Sekilas:** Mengukur kampanye notifikasi push di iOS dan Android.

## Overview

AppsFlyer mendukung pengukuran kampanye notifikasi push dari semua penyedia layanan push, serta kampanye yang diterapkan langsung di atas Firebase Cloud Messaging atau Layanan Notifikasi Push Apple (APNS).

Ada 2 kemungkinan cara untuk mengimplementasikan integrasi:

* Dengan menggunakan templat OneLink (metode yang disarankan).
* Dengan mengirimkan objek JSON dengan kode `af`  di payload notifikasi push (metode lama).

Konversi ditampilkan di dasbor Ikhtisar, dalam tampilan penargetan ulang atau terpadu.

<div id="how-does-it-work" />

## Bagaimana Cara Kerja API ini?

Setelah Anda menyelesaikan langkah-langkah dalam artikel ini, aplikasi Anda akan berfungsi sebagai berikut:

1. Anda memicu notifikasi push yang berisi template OneLink **atau** kode `af` dalam payloadnya.
2. Pengguna aplikasi menerima notifikasi push dan mengkliknya.
3. Aplikasi dimuat dan SDK AppsFlyer dimulai.
4. SDK memproses payload notifikasi push yang membuka aplikasi.
5. SDK mengekstrak dan mengirimkan data atribusi ke AppsFlyer.

Dalam skenario OneLink, jika OneLink dikonfigurasi untuk merutekan pengguna ke lokasi tertentu di aplikasi, alur deep link dipicu.

<div id="prerequisites" />

## Prasyarat

Sebelum melanjutkan, pastikan aplikasi Anda memiliki <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide">AppsFlyer SDK yang terintegrasi</Anchor> **dan**  dapat menerima notifikasi push.

<div id="steps" />

## Langkah

Untuk mengatur pengukuran notifikasi push, langkah-langkah berikut harus diselesaikan:

1. [Buat notifikasi push](/docs/measuring-push-notification-re-engagement-campaigns#1-creating-the-push-notification) yang berisi kode data kustom dengan templat OneLink **atau** kode `af` dengan objek JSON sebagai nilainya.
2. [Konfigurasikan SDK untuk menyelesaikan kode khusus](/docs/measuring-push-notification-re-engagement-campaigns#2-configuring-the-sdk) (dilakukan oleh pengembang aplikasi).
3. [Uji integrasi](/docs/measuring-push-notification-re-engagement-campaigns#3-testing-the-integration) dengan memicu notifikasi push.
4. [Lihat kinerja kampanye notifikasi push](/docs/measuring-push-notification-re-engagement-campaigns#4-viewing-push-notification-campaigns-in-the-dashboard) di dasbor.

<div id="1-creating-the-push-notification" />

<Accordion title="1. Membuat notifikasi push">

Pertama, buat notifikasi push yang berisi data atribusi menggunakan salah satu metode berikut.

<div id="note" />

> 📘 **Catatan**
>
> Dalam demonstrasi berikut, kami menggunakan Firebase sebagai penyedia layanan notifikasi push. Instruksi harus berlaku untuk semua penyedia layanan notifikasi push, dengan perbedaan kecil (jika ada). Lihat dokumentasi penyedia layanan notifikasi push masing-masing.

<Tabs>
<Tab title="Menggunakan OneLink (metode yang disarankan)">

<div id="using-onelink-recommended" />

#### **Menggunakan OneLink (disarankan)**

Ini adalah metode yang direkomendasikan untuk mengintegrasikan AppsFlyer dengan notifikasi push.

1. Buat <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">tautan OneLink dan atur untuk penargetan ulang.</Anchor>  
   **Catatan**: OneLink pendek dan URL panjang, keduanya didukung.
2. Dalam data kustom notifikasi push, tambahkan OneLink yang berisi data atribusi yang ingin Anda kirim ke AppsFlyer.

<div id="note-1" />

> 📄 **Contoh Firebase**
>
> Di Firebase:
>
> [![appsflyer-push-custom-data-firebase.png](https://files.readme.io/b2a753e8ec88ef0d0e0a71fe222a8ecc4f03786297696d150f185720b8f4e248-49839256715025.png)](https://files.readme.io/b2a753e8ec88ef0d0e0a71fe222a8ecc4f03786297696d150f185720b8f4e248-49839256715025.png)

</Tab>

<Tab title="Menggunakan JSON (metode lama)">

<div id="using-json-legacy" />

<div id="using-json" />

#### **Menggunakan JSON (metode lama)**

<div id="note-2" />

> 📘 **Catatan**
>
> Berikut ini mendokumentasikan metode lama dalam mengintegrasikan AppsFlyer dengan notifikasi push, dan tersedia untuk tujuan kompatibilitas dengan versi sebelumnya. Jika Anda menyiapkan aplikasi baru, gunakan [solusi berbasis OneLink yang disarankan](/docs/measuring-push-notification-re-engagement-campaigns#menggunakan-onelink-disarankan).

Dalam data kustom notifikasi push, tambahkan kode kustom yang disebut `af` yang berisi data atribusi yang ingin Anda kirim ke AppsFlyer dalam format JSON. Parameter atribusi berikut diperlukan:

* `PID`
* `is_retargeting`
* `c`

<div id="note-3" />

> 📄 **Contoh Firebase**
>
> Di Firebase:
>
> [![appsflyer-push-custom-data-firebase-json.png](https://files.readme.io/138aa2abb70cdb0b8a2c1a4b4ce0a8b83b2faae58e29f3223d5653a4d575012b-49839256716049.png)](https://files.readme.io/138aa2abb70cdb0b8a2c1a4b4ce0a8b83b2faae58e29f3223d5653a4d575012b-49839256716049.png)

</Tab>
</Tabs>

</Accordion>

<div id="2-configuring-the-sdk" />

<Accordion title="2. Mengonfigurasi SDK">

Tugas ini memerlukan perubahan pada kode aplikasi. Ikuti petunjuk tentang cara mengonfigurasi SDK:

* Saat menerapkan solusi berbasis OneLink yang direkomendasikan:
  1. beri tahu pengembang aplikasi apa nama kode khusus yang Anda tambahkan ke notifikasi. Dalam contoh ini, ini adalah `af_push_link`.
  2. Kirimkan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications#integrating-appsflyer-with-push-notifications-using-onelink-recommended">petunjuk ini</Anchor>.
* Saat menerapkan solusi berbasis JSON lama, kirimkan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications#integrating-appsflyer-with-push-notifications-legacy">petunjuk ini</Anchor> kepada pengembang Anda .

</Accordion>

<div id="3-testing-the-integration" />

<Accordion title="3. Menguji integrasi">

Untuk menguji apakah pengukuran notifikasi push terintegrasi dengan benar, cukup picu notifikasi push di kampanye yang Anda siapkan di Langkah 1.

Jika semuanya dikonfigurasi dengan benar, SDK akan:

1. Mendengarkan notifikasi push.
2. Memproses data atribusi yang disematkan dalam notifikasi push dan mengirimkannya ke AppsFlyer.
3. Melanjutkan dengan alur deep linking biasa, jika pengukuran notifikasi push diterapkan menggunakan OneLink.

</Accordion>

<div id="4-viewing-push-notification-campaigns-in-the-dashboard" />

<Accordion title="4. Melihat kampanye notifikasi push di dasbor">

Anda dapat melihat data yang berasal dari notifikasi push di <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide#retargeting-dashboard">dasbor Penargetan Ulang</Anchor>.

**Catatan** : AppsFlyer menghapus duplikat data notifikasi push. Artinya, jika payload identik diterima lebih dari satu kali, hanya satu yang dihitung.

</Accordion>

<div data-zendesk-anchors="how-does-it-work=bagaimana-cara-kerja-api-ini prerequisites=prasyarat steps=langkah using-onelink-recommended=menggunakan-onelink-disarankan" />
