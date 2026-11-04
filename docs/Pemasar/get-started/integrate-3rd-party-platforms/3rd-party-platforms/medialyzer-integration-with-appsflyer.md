---
title: Integrasi Medialyzer dengan AppsFlyer
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2023-05-01T11:43:34Z'
  edited_at: '2023-09-11T08:03:32Z'
  id: 14963611180689
  locale: id
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/id/articles/14963611180689
---
> **Sekilas:** Medialyzer, mitra terintegrasi AppsFlyer, mengembangkan dan memasarkan perangkat lunak sebagai solusi layanan. Solusi ini memungkinkan perencana media mengoptimalkan kampanye TV mereka untuk bisnis online berdasarkan kunjungan dan konversi yang dihasilkan secara langsung per penayangan iklan TV.

<div id="important" />

> 🚧 **Penting!**
>
> <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions#pembatasan-sumber-media">Beberapa sumber media</Anchor> membatasi pembagian data dengan pihak ketiga. Oleh karena itu, postback untuk event terbatas tidak akan dikirim ke mitra ini, terlepas dari pilihan yang dikonfigurasi untuk mengirim postback.

<div id="setting-up-medialyzer" />

## Mengatur Medialyzer

Pengaturan dilakukan dari halaman **Integrasi Aktif** , tetapi untuk menemukan mitra, Anda harus pergi ke <Anchor target="_blank" href="/marketers/id/docs/partner-integrations">pasarterlebih</Anchor> dahulu.

> 📘 **Catatan**
>
> Sebelum mengatur integrasi, pastikan Anda <Anchor target="_blank" href="/marketers/id/docs/partner-integrations#contact-details">menghubungi mitra</Anchor> dan membuka akun dengan mereka.

**Untuk mengaktifkan integrasi:**

1. Dari menu atas halaman AppsFlyer mana pun, klik **Marketplace**.
2. Cari mitra dan pilih itu.
3. Klik **Atur integrasi**. Anda diarahkan ke halaman pengaturan integrasi.
4. Di tab **Integrasi** , pilih aplikasi untuk integrasi dan aktifkan **Aktifkan mitra** .  
   **Catatan:** Tombol harus aktif <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">(diaktifkan)</Anchor> selama Anda bekerja dengan mitra.
5. Selesaikan konfigurasi menggunakan tab yang relevan, seperti yang dijelaskan di bawah ini.

Jendela konfigurasi hanya menggunakan tab **Integrasi** .

Untuk deskripsi terperinci dari Header Partner Configuration Window (Periode Waktu Konfigurasi Mitra), klik di <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">sini</Anchor>.

<div id="integration-tab" />

<Accordion title="Tab Integrasi">

<div id="activate-partner" />

#### Aktifkan mitra

Pada kunjungan pertama, Anda harus mengaktifkan tombol **Aktifkan mitra** untuk menyiapkan integrasi. Tombol harus tetap aktif selama Anda bekerja dengan Medialyzer. Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">aktivasi mitra</Anchor>.

<div id="advanced-privacy" />

#### Privasi Lanjutan

Untuk aplikasi iOS, tombol <Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework">Privasi Tingkat Lanjut</Anchor> muncul. Ketika diaktifkan, tombol membatasi pembagian identifier pengguna dengan mitra. Perhatikan bahwa ketika tombol <Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework">Privasi Lanjutan Teragregasi</Anchor> diaktifkan di Pengaturan Aplikasi, **Privasi Lanjutan (untuk iOS 14.5+ dan yang lebih baru)** diaktifkan dan dikunci secara default.

<div id="default-postbacks" />

#### Postback Default

AppsFlyer mengirimkan postback default ke Medialyzer setelah penginstalan pengguna. Gunakan bagian ini untuk <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#f">menentukan postback</Anchor>.

* **Off**: Postback penginstalan tidak dikirim ke Medialyzer.
* **Semua sumber media, termasuk organik**: Postback penginstalan dikirim untuk event yang diatribusikan ke mitra mana pun dan untuk event organik.

![default_postbacks.png](https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png)

<div id="in-app-event-postbacks" />

#### Postback in-app event

Pada bagian ini, Anda dapat memetakan event AppsFlyer Anda dengan mitra Anda melalui postback.

[![app_event_postbacks.JPG](https://files.readme.io/a6a4aaa89c3eb5ba759a32312663b4c9855738eaea56366070ca9a8da3840a69-14963640866833.png)](https://files.readme.io/a6a4aaa89c3eb5ba759a32312663b4c9855738eaea56366070ca9a8da3840a69-14963640866833.png)

1. Aktifkan **Postback in-app event**.
2. Klik **Tambahkan event** untuk menambahkan SDK atau event server-to-server ke daftar.
3. Isi parameter berikut: 

| Nama Parameter | Deskripsi |
| --- | --- |
| **event AppsFlyer** | Nama event, seperti yang diterima oleh AppsFlyer baik dari SDK yang terintegrasi ke dalam aplikasi Anda atau dari event server-to-server.<br />**Tip**: Tidak melihat event yang Anda cari?<ul><li>Pastikan untuk mengaktifkan event di perangkat dengan penginstalan non-organik dan periksa kembali.</li><li>Ketik di **event AppsFlyer**, lalu klik **Buat khusus**. Baca lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#event-khusus">pemetaan event khusus</Anchor>.</li></ul> |
| **dipetakan ke event mitra** | Masukkan nama event atau ID yang sesuai untuk setiap event, sebagaimana ditentukan dalam BPM, atau kirim event apa adanya tanpa pemetaan nama. |
| **untuk pengguna dari** | Pilih **Semua sumber media, termasuk organik** untuk mengirimkanpostback untuk event yang diatribusikan ke mitra mana pun dan untuk event organik. |
| **termasuk** | <ul><li>**Tidak ada nilai & tidak ada pendapatan**: Kirim hanya event tersebut tanpa parameter apa pun (nilai atau pendapatan).</li><li>**Nilai dan tanpa pendapatan**: Mengirimkan semua parameter **tidak termasuk** nilai pendapatan.</li><li>**Nilai dan pendapatan**: Mengirimkan semua parameter event, **termasuk** nilai pendapatan (jika ada dalam event).</li></ul> |

4. Klik **Simpan Integrasi**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Tab tautan atribusi">

Tautan atribusi tidak tersedia untuk Medialyzer.

</Accordion>

<div id="cost-tab" />

<Accordion title="Tab Biaya">

Data biaya tidak didukung dalam integrasi dengan Medialyzer.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Tab Pendapatan Iklan">

Data pendapatan iklan tidak didukung dalam integrasi dengan Medialyzer.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Tab Hak Akses">

Hak Akses tidak tersedia untuk Medialyzer.

</Accordion>

<div data-zendesk-anchors="h_01H9FKEAV2225HM5CQAGWS2K99=penting setting-up-spoteffects=mengatur-medialyzer h_01H9FKEAV37AT3VTZ5WV1YMWC2=mengatur-medialyzer h_01H9FKEAV3AV8YMNADQ62476YR=catatan h_01H9FKEAV3YQY124TSZ5Q7VHAY=integration-tab activate-partner=aktifkan-mitra h_01H9FKEAV3DW2A6RQ1NS44FT5F=aktifkan-mitra advanced-privacy=privasi-lanjutan h_01H9FKEAV3T3YCPBYW70QVF540=privasi-lanjutan default-postbacks=postback-default h_01H9FKEAV3Z1Y09P6E18J8AVX2=postback-default inapp-event-postbacks=postback-in-app-event h_01H9FKEAV3GG6X17X3NCCSWJAS=postback-in-app-event h_01H9FKEAV3ZEF1AHRTQGEGYFSJ=attribution-link-tab h_01H9FKEAV3ERXQ98BJGKBQRGP2=cost-tab h_01H9FKEAV32MB7M2Q1ASDAE6RM=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab" />
