---
title: Konfigurasi kampanye Amazon DSP
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2023-01-04T10:14:20Z'
  edited_at: '2026-09-09T13:03:19Z'
  id: 11904659502737
  locale: id
  section: Amazon Ads
  section_id: 28703975923729
  url: https://support.appsflyer.com/hc/id/articles/11904659502737
---
> **Sekilas:** Amazon DSP (amazondsp\_int), mitra terintegrasi AppsFlyer, memberi pemilik aplikasi kemampuan untuk mengukur atribusi berbasis klik dan tampilan dengan AppsFlyer untuk TV, tablet, dan perangkat seluler.

<Image align="center" alt="mceclip0.png" src="https://files.readme.io/0a4c9078bd683c51bad40408c894f6e2b7314d7c369bd46ac90c3e622f62f0a7-11927906589329.png" />

<div id="complete-the-setup-in-amazon-ads" />

<div id="activate-partner" />

## Aktifkan mitra

**Prasyarat:** Sebelum menyiapkan integrasi, pastikan Anda <Anchor target="_blank" href="/marketers/id/docs/partner-integrations#contact-details">menghubungi mitra</Anchor> dan membuka akun dengan mereka.

Penyiapan dilakukan dari halaman **Integrasi Aktif** , tetapi untuk menemukan mitra baru, Anda harus terlebih dahulu membuka Pasar, seperti yang dijelaskan di bawah ini.

**Untuk mengaktifkan integrasi mitra:**

1. Di AppsFlyer, buka **Konfigurasi** > **Marketplace Mitra**.
2. Cari integrasi mitra baru dan pilih.
3. Klik **Atur integrasi**. Anda diarahkan ke halaman pengaturan **Integrasi Aktif** .
4. Di tab **Integrasi**, aktifkan tombol **Aktifkan mitra**.  
   **Catatan:** Tombol harus tetap aktif <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">(diaktifkan)</Anchor> selama Anda bekerja dengan mitra.
5. Selesaikan konfigurasi menggunakan tab yang relevan, seperti yang dijelaskan di bagian berikutnya.

<div id="setting-up-amazon-ads" />

## Mengatur integrasi Amazon DSP

Integrasi dengan Amazon DSP mendukung atribusi klik dan impresi. Jendela konfigurasi mencakup tab berikut: Integrasi, Tautan atribusi, Biaya, Pendapatan iklan, dan Izin. Tab yang tersedia untuk Amazon DSP adalah Integrasi dan Izin.

<div id="note" />

> 📘 **Catatan**
>
> * Beberapa setelan berbeda untuk perangkat iOS dan Android
> * Pelajari lebih lanjut cara <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner">mengatur integrasi mitra</Anchor>

<div id="integration-tab" />

<Accordion title="Tab Integrasi">

Tab **Integrasi** mencakup sejumlah bagian, seperti yang dijelaskan di bawah ini.

<div id="activate-partner-1" />

#### Aktifkan mitra

Untuk mengonfigurasi integrasi, Anda harus [mengaktifkan](/docs/amazon-ads-campaign-configuration#aktifkan-mitra) sakelar **Aktifkan mitra** terlebih dahulu. Pelajari lebih lanjut cara <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation#mengaktifkan-integrasi-mitra">mengaktifkan dan menonaktifkan integrasi mitra</Anchor> . 

#### Privasi Lanjutan

Hanya untuk aplikasi iOS: Kontrol Anda atas data yang dibagikan dengan mitra melalui postback dan <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions">laporan</Anchor> bergantung pada status sakelar **Privasi Lanjutan (untuk iOS 14.5+ dan yang lebih baru)** :

| Privasi Tingkat Lanjut: Aktif | Privasi Tingkat Lanjut: Nonaktif |
| --- | --- |
| Postback dikirim hanya untuk event yang diatribusikan ke mitra | Postback dikirim sesuai dengan konfigurasi Anda:<ul><li>**Semua sumber media, termasuk organik.**</li><li>**Mitra ini saja**</li></ul> |
| Postback dikirim sesuai dengan <Anchor target="_blank" href="/partners/id/docs/advanced-privacy-guide-postback-macros-for-ad-networks">templat Privasi Tingkat Lanjut</Anchor> |  |
| <Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework">Data gabungan dan anonim</Anchor> dibagikan dengan mitra, artinya tidak ada data tingkat pengguna (ID perangkat) yang dibagikan. |  |

<div id="general-settings" />

#### Pengaturan umum

**ID produk Amazon**

Ini adalah kunci unik yang dibuat oleh Manajer Akun Amazon dan diberikan kepada pemasang iklan untuk aplikasi Amazon DSP. ID produk Amazon diperlukan untuk menyelesaikan integrasi dan mengizinkan atribusi ke Amazon DSP.

#### Postback Default

Konfigurasikan cara mengirim postback untuk penginstalan:  

* **Khusus mitra ini**: Kirim postback hanya jika event diatribusikan ke mitra ini—artinya, pengguna yang melakukannya berasal dari mitra ini.
* **Semua sumber media termasuk organik**: Kirim postback untuk event yang dihubungkan ke mitra mana pun dan untuk acara organik—artinya, jika pengguna yang melakukannya berasal dari sumber media mana pun.

> 📘 **Catatan**
>
> * Hanya untuk aplikasi iOS: Kontrol Anda atas data yang dibagikan dengan mitra melalui postback dan <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions">laporan</Anchor> bergantung pada status sakelar **Privasi Lanjutan (untuk iOS 14.5+ dan yang lebih baru)** .
> * Postback dibagikan melalui Data Locker dalam laporan per jam, bukan dalam waktu aktual.

<div id="note-1" />

<div id="ignore-active-users-for-retargeting" />

<div id="re-engagement-attribution" />

<div id="install-attribution" />

#### Instal atribusi

Atur jendela atribusi klik-tayang dan lihat-tayang untuk penginstalan (peluncuran pertama). Perhatikan bahwa hanya pemasangan dalam jendela lihat balik yang dapat diatribusikan ke Amazon DSP.

1. Atur **Jendela lookback klik-tayang penginstalan** ke 1-23 jam atau 1-30 hari.  
   **Catatan:** Amazon DSP merekomendasikan pengaturan jendela lookback klik-tayang ke 14 hari, agar selaras dengan jendela atribusinya.
2. [Opsional] Aktifkan **Instal atribusi lihat-tayang** dan atur **Instal jendela atribusi lihat-tayang** ke 1-24 jam.

<div id="in-app-event-postbacks" />

#### Postback in-app event

Konfigurasikan pemetaan in-app event dengan event Amazon DSP, dikirim melalui postback.

<div id="note-2" />

> 📘 **Catatan**
>
> Postback dibagikan melalui Data Locker dalam laporan per jam, bukan dalam waktu aktual.

**Untuk mengonfigurasi postback in-app event:**

1. Aktifkan **Postback in-app event**.
2. Klik **Tambahkan event** untuk menambahkan SDK atau event server-ke-server ke daftar. Tabel berikut ini menjelaskan bidang-bidang yang harus diisi:  

| Nama parameter | Deskripsi |
| --- | --- |
| **event AppsFlyer** | Nama event, seperti yang diterima oleh AppsFlyer baik dari SDK yang terintegrasi ke dalam aplikasi Anda atau dari event server-ke-server.<br />**Tip**: Tidak melihat event yang Anda cari?<ul><li>Pastikan untuk mengaktifkan event di perangkat dengan instalasi non-organik dan periksa kembali.</li><li>Ketik di **AppsFlyer event**, lalu klik **Create custom**. Baca lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#event-khusus">pemetaan event kustom</Anchor>.</li></ul> |
| **dipetakan ke event mitra** | Nama atau ID unik setiap event sebagaimana didefinisikan di pihak mitra. Kemungkinan konfigurasi pemetaannya adalah:<ul><li>**Bidang teks:** Dapatkan ID event terkait dari mitra.</li><li>**Kotak drop-down:** Pilih event AppsFlyer yang telah ditentukan sebelumnya yang paling sesuai.</li><li>**Apa adanya**: Kirim event apa adanya, tanpa pemetaan nama.</li></ul> |
| **untuk pengguna dari** | Pilih opsi pengiriman untuk event:<ul><li>**Khusus mitra ini**: Kirim postback hanya jika event ini diatribusikan ke mitra ini.</li><li>**Semua sumber media termasuk organik**: Kirim postback untuk event yang diatribusikan ke mitra mana pun, serta event organik.</li></ul> |
| **termasuk** | <ul><li>**Tidak ada data (default)**: Kirim hanya event itu sendiri tanpa nilai event apa pun.</li><li>**Nilai dan pendapatan**: Kirim semua parameter event, **termasuk** nilai pendapatan (jika terdapat dalam event).</li><li>**Nilai tanpa pendapatan**: Kirim semua parameter **kecuali** nilai pendapatan.</li></ul> |

3. [Opsional] Klik **Tambahkan ketentuan**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/e3b4e42933325fc5e93d4cc9e892a1b28388648078fddb965a31c8ec8c04b25f-17912947736465.png" width="30px" />ikon untuk <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#postback-in-app-event-bersyarat">mengatur kondisi</Anchor> suatu event.
4. Klik **Save Integration (Simpan Integrasi)**.
5. [Opsional]Setelah menyimpan integrasi, sambil tetap membuka halaman konfigurasi, Anda dapat mengintegrasikan lebih banyak aplikasi dengan mitra:
   1. Dari pojok kiri atas, di bawah nama mitra, klik nama aplikasi untuk membuka daftar aplikasi.
   2. Pilih aplikasi lainnya dari daftar drop-down.
   3. Ulangi [langkah integrasi](/docs/amazon-ads-campaign-configuration#integration-tab)  untuk aplikasi yang dipilih.

> 📘 **Catatan**
>
> Hanya untuk aplikasi iOS: Kontrol Anda atas data yang dibagikan dengan mitra melalui postback dan <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions">laporan</Anchor> bergantung pada status sakelar **Privasi Lanjutan (untuk iOS 14.5+ dan yang lebih baru)** .

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Tab tautan atribusi">

Tautan atribusi tidak relevan untuk Amazon DSP. Atribusi dilakukan dengan menggabungkan data keterlibatan dari Amazon DSP dengan data dari AppsFlyer, menggunakan jendela lookback klik-tayang dan lihat-tayang yang dikonfigurasi di [tab Integrasi](/docs/amazon-ads-campaign-configuration#integration-tab).

</Accordion>

<div id="cost-tab" />

<Accordion title="Tab Biaya">

Data biaya tidak tersedia untuk Amazon DSP.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Tab Pendapatan Iklan">

Pendapatan iklan tidak tersedia untuk Amazon DSP.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Tab Hak Akses">

Pilih izin mana yang akan diberikan kepada Amazon DSP untuk mengakses data Anda dan melakukan berbagai tindakan.

<div id="note-3" />

> 📘 **Catatan**
>
> * Saat integrasi <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">dinonaktifkan</Anchor> saat sakelar Izin masih diaktifkan, izin tetap diberikan.
> * Pelajari lebih banyak tentang <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#permissions-tab">pemberian izin</Anchor>.

</Accordion>

<div id="traits-and-limitations" />

<div id="see-also-1" />

<div id="note-5" />

<div id="dma-consent-methods" />

<div id="note-4" />

<div id="support-amazon-eu-consent-policy" />

<div id="ctv-to-mobile-attribution" />

<div id="raw-data-restrictions" />

<div id="deferred-deep-linking" />

<div id="see-also" />

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/setting-up-amazon-fire-tv-ad-attribution">Mengatur atribusi iklan Amazon Fire TV</Anchor>

<div data-zendesk-anchors="activate-partner=aktifkan-mitra 01H88VAJH3B5ESK12D3ATMMVZ8=aktifkan-mitra setting-up-amazon-dsp-integration=mengatur-integrasi-amazon-dsp 01H88VAJH3VENKYVRQY5RXN63P=mengatur-integrasi-amazon-dsp 01H88VAJH3BYZSXQGGZZJQ9N0C=catatan 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=aktifkan-mitra-1 01H88VAJH34GP7FK1KTJGRDPM7=aktifkan-mitra-1 advanced-privacy=privasi-lanjutan 01H88VAJH3G5FAR7RRNDEPNGME=privasi-lanjutan general-settings=pengaturan-umum 01H88VAJH3F2FJK5YP3M2V7RWD=pengaturan-umum default-postbacks=postback-default 01H88VAJH3WE9Z0971WMBRBJRS=postback-default 01H88VAJH3AETJZGYMY1YK7FJ6=catatan-3 install-attribution=instal-atribusi 01H88VAJH3SSG6ZNV7XQ46W5CX=instal-atribusi inapp-event-postbacks=postback-in-app-event 01H88VAJH3AS37MVF75GANWX4B=postback-in-app-event h_01HCW04WHZ8HGHBHV4733CS615=catatan-2 01H88VAJH36MYZ9W1YPWA92Z1Z=catatan-3 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=catatan-4 h_01HDNZ59NQEDFC3D8JYGENR1NR=lihat-juga" />
