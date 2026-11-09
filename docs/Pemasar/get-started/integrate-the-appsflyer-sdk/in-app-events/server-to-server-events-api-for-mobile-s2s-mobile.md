---
title: API event server-ke-server untuk aplikasi seluler (S2S-seluler)
metadata:
  keywords:
    - iOS
    - Android
    - API
    - In-App
    - S2S
    - HTTP API
    - appsflyer_id
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2014-05-21T17:47:21Z'
  edited_at: '2024-05-06T08:41:03Z'
  id: 207034486
  locale: id
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/id/articles/207034486
---
> **Sekilas:** Kirim event dari server Anda ke AppsFlyer untuk mengukur event seluler yang muncul di luar aplikasi.

<Image align="center" alt="S2S_us-en.png" src="https://files.readme.io/2f228a03ca00df529e42bd033825a0dca595e99a537cadcfd5419754a29b5490-35863179575441.png" />

<div id="server-to-server-events-api-for-mobile" />

## API event server-ke-server untuk aplikasi seluler

Untuk aplikasi iOS, mulai iOS 14, Anda harus mengirimkan parameter os (sistem operasi).

Platform AppsFlyer mengatribusi dan mencatat event aplikasi seluler yang dikirim oleh AppsFlyer SDK dan oleh API. Gunakan S2S API untuk melaporkan event yang terjadi di luar aplikasi; misalnya, pengguna memperbarui langganan menggunakan antarmuka web Anda. Event S2S, setelah direkam, tersedia di seluruh platform, termasuk dasbor, data lengkap, dan analitik. Untuk event web PBA, lihat <Anchor target="_blank" href="/marketers/id/docs/web-server-to-server-events-api-for-pba-web-s2s">Web S2S untuk PBA.</Anchor>

AppsFlyer mengisi event S2S dengan:

* Nilai yang dikirim dalam pesan S2S
* Beberapa AppsFlyer menginstal nilai atribusi seperti, waktu penginstalan dan sumber media.

Untuk mengirimkan acara lewat API, beri tahu pembuat program Anda untuk mengikuti <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">instruksi API server-to-server event</Anchor> mereka.

<div id="populating-parameters" />

## Mengisi parameter

<div id="difference-between-organic-and-nonorganic" />

<Accordion title="Perbedaan antara organik dan non-organik">

Saat AppsFlyer memproses in-app event S2S, bidang atribusi diisi dengan menggunakan ID AppsFlyer untuk mengidentifikasi event penginstalan terkait sebelum in-app event.

Artinya, beberapa data yang AppsFlyer kaitkan dengan kejadian dalam aplikasi S2S non-organik, tidak terkait dengan in-app event S2S organik.

<div id="h_01_including-user-agent-and-ip-address-in-s2s-events" />

<div id="increasing-the-volume-of-data-transactions" />

<div id="note-1" />

<div id="note" />

> 📄 **Contoh**
>
> Misalnya, jika Anda membandingkan laporan data lengkap dari in-app event S2S non-organik dan organik, event non-organik berisi data yang tidak dimiliki oleh in-app event organik.
>
> In-app event non-organik mencakup data tentang sumber media, kampanye, jenis interaksi yang dikaitkan, dan waktu interaksi yang dikaitkan.
>
> In-app event organik, di sisi lain, mengikuti penginstalan organik. Penginstalan organik tidak memiliki data yang terkait dengan kampanye, sumber media, jenis interaksi yang dikaitkan, dan waktu penginstalan.

</Accordion>

<div id="mapping-appsflyer-id-with-customer-user-id-cuid" />

<Accordion title="Memetakan ID AppsFlyer dengan ID pengguna pelanggan (CUID)">

Logika backend diperlukan untuk mendapatkan nilai guna mengisi parameter. Berikut ini menjelaskan cara untuk mendapatkan ID AppsFlyer:

* ID AppsFlyer bersifat wajib dan digunakan untuk mengatribusikan event.
* ID ini dibuat saat pengguna pertama kali menginstal aplikasi seluler.
* Agar Anda dapat memetakan CUID Anda ke ID AppsFlyer, Anda harus mengatur CUID di aplikasi.

Untuk memudahkan Anda mengetahui pengguna mana yang melakukan event mana, terapkan alur berikut:.

* <Anchor target="_blank" href="/marketers/id/docs/customer-user-id-field-cuid">Tetapkan ID pengguna pelangganD</Anchor> saat pengguna menginstal aplikasi.
* Laporan data lengkap AppsFlyer berisi CUID dan ID AppsFlyer. Gunakan salah satu alat pengiriman data untuk mendapatkan ini atau API Push AppsFlyer.
* Gunakan laporan data lengkap untuk mencocokkan CUID dengan ID AppsFlyer.
* ID AppsFlyer tersedia di SDK yang terintegrasi dengan aplikasi Anda (Android/iOS).
* Petakan ID AppsFlyer ke ID pengguna pelanggan di sistem internal Anda (penting untuk penggunaan di kemudian hari).

Setelah Anda memetakan ID AppsFlyer dengan CUID, Anda dapat mencocokkan pengguna dengan event yang dilaksanakan. Anda kemudian dapat memperoleh nilai lain (nilai event, mata uang event, waktu event, dll.) dan mengirim server to server in-app event.

</Accordion>

<div id="fetching-the-appsflyer-id" />

<Accordion title="Mengambil ID AppsFlyer">

`appsflyer_id`adalah parameter wajib di pesan event server-ke-server. AppsFlyer menggunakan parameter ini untuk mengatribusi event ke perangkat asli dan ke sumber media yang teratribusi. Anda bisa mendapatkan ID ini menggunakan salah satu metode berikut:

* Dari perangkat seluler dengan memanggil API SDK AppsFlyer:

  <Tabs>
  <Tab title="Android native">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#getappsflyeruid">getAppsFlyerId</Anchor>

  </Tab>

  <Tab title="iOS native">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#getappsflyeruid">getAppsFlyerId</Anchor>

  </Tab>

  <Tab title="Unity">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#getappsflyerid">getAppsFlyerId</Anchor>

  </Tab>

  <Tab title="React Native">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#getappsflyeruid">getAppsFlyerUID</Anchor>

  </Tab>
  </Tabs>

* Dari platform AppsFlyer menggunakan salah satu dari yang berikut: <Anchor target="_blank" href="/marketers/id/docs/pull-api-raw-data?query=pull">Pull API,</Anchor> <Anchor target="_blank" href="/marketers/id/docs/push-api-streaming-raw-data">Push API,</Anchor> Ekspor <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">penginstalan data lengkap.</Anchor>

> 👍 **Tips**
>
> Saat menguji pesan S2S, jika Anda menggunakan data lengkap, cari catatan dengan sumber media "s2s\_test". Ini merupakan perangkat uji Anda dan ID Perangkat AppsFlyer-nya adalah ID yang Anda butuhkan.

</Accordion>

<div id="time-stamping-s2s-events" />

<Accordion title="Penyetempel waktu acara S2S">

<Image align="center" alt="diagram logika stempel waktu" src="https://files.readme.io/2d9138cc505b0ab1bb106c00fb2d71bd1d070ee236d7f928c8b8b85afe14af59-35863166628497.png" />

Saat acara S2S tiba secara massal ke AppsFlyer, event tersebut diberi stempel waktu sesuai dengan nilai properti `eventTime` dan waktu kedatangannya. Properti `eventTime` menunjukkan waktu kejadian dalam aplikasi.

Pada saat kedatangan, acara diberi cap waktu sebagai berikut:

* Jika parameter `eventTime` tidak disertakan dalam catatan event, waktu event diatur ke waktu kedatangan pesan HTTP.
* Event yang tiba sebelum 02.00 UTC dicap dengan nilai `eventTime` . Artinya, agar event dicap dengan `eventTime`, event tersebut harus dilaporkan pada hari event, atau hari berikutnya hingga pukul 02.00 UTC.
* Event yang berlangsung pada hari sebelumnya atau sebelumnya, tiba setelah pukul 02:00 UTC, dicap dengan waktu kedatangan (waktu panggilan API).
* Event tiba dengan nilai `eventTime` mendatang (eventTime > waktu kedatangan):
  * Jika `eventTime` yang dilaporkan dan waktu kedatangan keduanya jatuh pada hari kalender yang sama, acara tersebut diberi stempel waktu dengan nilai `eventTime` .
  * Jika `eventTime` yang dilaporkan berada di hari kalender berikutnya, event tersebut diberi stempel waktu dengan waktu kedatangan.
* Event dengan Nilai `eventTime` yang tidak valid dicap dengan waktu kedatangan pesan HTTP.

**Contoh**

* Sebuah event dikirim dengan `eventTime` = Senin 21.00.

| Tiba di AppsFlyer | Penyetempel waktu AppsFlyer | Catatan |
| --- | --- | --- |
| Selasa 01:00 | Senin 21:00 | Tiba sebelum akhir hari. Waktu diatur ke nilai `eventTime` . |
| Rabu 09:00 | Rabu 09:00 | Tiba setelah akhir hari. Waktu diatur ke waktu kedatangan. |

</Accordion>

<div id="sending-negative-revenue" />

<Accordion title="Mengirim pendapatan negatif">

Event yang memiliki nilai pendapatan negatif dapat dikirim. Misalnya, jika pembelian dibatalkan. Parameter `af_revenue` dapat memiliki nilai negatif jika mencatat nilai tersebut.

Jika Anda mengisi `af_quantity`, Anda mungkin ingin mengisinya dengan nilai negatif tergantung pada logika sistem Anda. AppsFlyer tidak menggunakan `af_quantity`.

</Accordion>

<div id="S2S_in-app_events_are_wrongly_attributed_as_organic" />

<div id="troubleshooting" />

## Pemecahan Masalah

<div id="events-arent-displaying-in-the-dashboard" />

<Accordion title="Event tidak ditampilkan di dasbor">

* Titik akhir: Pastikan titik akhir yang digunakan sudah benar.
* Pastikan bahwa payload berisi parameter wajib. Lihat [di sini](/docs/server-to-server-events-api-for-mobile-s2s-mobile#mapping-appsflyer-id-with-customer-user-id-cuid).
* Pastikan bahwa ID AppsFlyer yang Anda gunakan untuk memulai event tersebut adalah appsflyer\_id yang asli dan benar-benar diinstal pada aplikasi tertentu. Lihat [di sini](/docs/server-to-server-events-api-for-mobile-s2s-mobile#fetching-the-appsflyer-id).
* Event S2S tidak mendukung multi-event dalam satu permintaan S2S. Setiap event harus dikirim sebagai event terpisah.
  * Event dapat dikirim dengan metode tidak serentak untuk memudahkan waktu respons.
* Di dasbor tinjauan, rentang tanggal terkait dengan tanggal penginstalan aplikasi (LTV) dan bukan dengan tanggal event.
  * Pastikan Anda memilih rentang tanggal yang benar.
  * Pastikan rentang tanggal dasbor sesuai dengan tanggal penginstalan perangkat (appsflyer\_id) dan bukan tanggal event.
* Laporan data lengkap event: rentang tanggal berkaitan dengan tanggal event dan bukan tanggal penginstalan.

</Accordion>

<div id="events-dont-contain-revenue" />

<Accordion title="Event tidak berisi pendapatan">

Jika Anda mengirim event S2S tetapi pendapatannya tidak dicatat, pastikan bahwa JSON yang Anda kirim telah diubah menjadi string JSON. Bagian terpenting adalah parameter nilai event di JSON. Ini harus diubah menjadi string JSON seperti yang ditunjukkan pada contoh berikut.

```json
"{\"af_revenue\":\"6\" ,\"af_content_type\":\"wallets\"}"
```

Jika nilai event tidak diubah menjadi string, maka nilai tidak akan diproses dengan tepat dan pendapatan tidak dapat dicatat.

Nilai pendapatan tidak boleh diformat dengan cara apa pun. Ini dapat berisi titik desimal. Jangan menyertakan simbol atau kode mata uang atau `,` pemisah. Pendapatan dapat diawali dengan `-`

* Contoh nilai event yang valid adalah: `123`, `-123.45`, `123.456`
* Contoh nilai yang tidak valid: `1,234.56`, `1,234`

</Accordion>

<div id="not-all-fields-are-populated-in-s2s-events" />

<Accordion title="Tidak semua bidang diisi dalam event S2S">

Bidang data lengkap diisi menggunakan nilai yang dikirim dalam panggilan S2S dan beberapa bidang diisi menggunakan event penginstalan. Perilaku serupa tetapi tidak identik diamati untuk in-app event yang dilaporkan menggunakan AppsFlyer SDK. Ada beberapa perbedaan, khususnya, bidang berikut tidak diisi untuk event S2S:

* wifi
* Operator
* bahasa
* Model Perangkat
* Kategori Perangkat
* Versi Aplikasi: Anda dapat menggunakan `app_version_name`
* Nama aplikasi
* Agen Pengguna

</Accordion>

<div data-zendesk-anchors="servertoserver-events-api-for-mobile=api-event-server-ke-server-untuk-aplikasi-seluler h_01H9Q8KBYGXAA8H4AKKXP8T8DY=api-event-server-ke-server-untuk-aplikasi-seluler populating-parameters=mengisi-parameter h_01H9Q8KBYGHY1SDSMSFZRT2JXZ=mengisi-parameter h_01H9Q8KBYG6W4TERWHARZZZASZ=difference-between-organic-and-nonorganic h_01H9Q8KBYG0JCCGTEJW3GXZMF1=contoh h_01H9Q8KBYG6EBKPS5Y2KC1QT7G=mapping-appsflyer-id-with-customer-user-id-cuid h_01H9Q8KBYGR26VMQR9Y0CK85F6=fetching-the-appsflyer-id h_01H9Q8KBYGNC8PJE2GS8MHG0KQ=tips h_01H9Q8KBYG8ASB1WB9X4XM3CYZ=time-stamping-s2s-events h_01H9Q8KBYG63SZWNM4GWSJG605=sending-negative-revenue troubleshooting=pemecahan-masalah h_01H9Q8KBYGYR9Y7DPCNWSB4QY0=pemecahan-masalah h_01H9Q8KBYGYHCWAPPNMG9WB8QN=events-arent-displaying-in-the-dashboard h_01H9Q8KBYGDC68637RH4DE2FZX=events-dont-contain-revenue h_01H9Q8KBYGDQKZF90EJAXRTMF3=not-all-fields-are-populated-in-s2s-events" />
