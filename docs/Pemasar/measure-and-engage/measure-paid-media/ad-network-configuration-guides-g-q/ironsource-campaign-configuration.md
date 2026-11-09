---
title: konfigurasi kampanye ironSource
metadata:
  keywords:
    - Supersonic
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-06T10:47:23Z'
  edited_at: '2023-10-12T15:22:34Z'
  id: 208005096
  locale: id
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/id/articles/208005096
---
> **Sekilas:** ironSource, mitra terintegrasi AppsFlyer, membangun alat monetisasi, keterlibatan, analitik, dan penemuan untuk pengembang aplikasi, produsen perangkat, operator seluler, dan pemasang iklan. Selain atribusi seluler berbasis klik, ironSource juga menawarkan biaya, pendapatan iklan, penargetan ulang, dan atribusi lihat-tayang, yang dapat Anda rekam dengan AppsFlyer.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/ironsource.png?v=1" width="213px" />

 Catatan Sebagai jaringan semua penginstalan, ironSource lebih suka menerima postback untuk semua penginstalan baru aplikasi Anda dari sumber APA PUN, termasuk organik. Untuk melakukannya, pilih Event yang diatribusikan ke mitra mana pun untuk mengirimkan semua postback penginstalan ke ironSource.

Pengaturan dilakukan dari halaman pengaturan integrasi  partner, tetapi untuk menemukan partner, Anda harus pergi ke <Anchor target="_blank" href="/marketers/id/docs/partner-integrations">marketplaceterlebih</Anchor> dahulu.

> 📘 **Catatan**
>
> Sebelum mengatur integrasi, pastikan Anda <Anchor target="_blank" href="/marketers/id/docs/partner-integrations#contact-details">menghubungi mitra</Anchor> dan membuka akun dengan mereka.

**Untuk mengaktifkan integrasi:**

1. Pergi ke Marketplace: Dari menu atas halaman AppsFlyer mana pun, klik **Marketplace**.
2. Cari mitra dan pilih itu.
3. Klik **Atur integrasi**. Anda diarahkan ke halaman pengaturan integrasi.
4. Di tab **Integrasi**, aktifkan tombol **Aktifkan mitra**.  
   **Catatan:** Tombol harus tetap aktif <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">(diaktifkan)</Anchor> selama Anda bekerja dengan mitra.
5. Selesaikan konfigurasi menggunakan tab yang relevan, seperti yang dijelaskan di bawah ini.

Jendela konfigurasi ironSource mencakup 5 tab: Integrasi, tautan Atribusi, Biaya, Pendapatan Iklan, dan Izin. Klik pada item di bawah ini untuk membaca tentang pengaturan tab.

Untuk deskripsi terperinci tentang Partner Configuration Window Header (Header Jendela Konfigurasi Mitra), klik di <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">sini</Anchor> .

> 👍 **Tips**
>
> * Tahap <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#d">Pengaturan Umum</Anchor> di tab Integrasi bersifat **wajib** bagi semua partner
> * Semua tahap lainnya bersifat deskriptif atau **opsional**

<div id="integration-tab" />

<Accordion title="Tab Integrasi">

<div id="activate-partners" />

### Aktifkan partner

Pada **kunjungan pertama** ke sini, Anda harus mengaktifkan sakelar **Aktifkan Partner** untuk mengaktifkan pengaturan parameter tab integrasi. Sakelar harus tetap aktif selama Anda bekerja dengan partner.  
Untuk detail lebih lanjut tentang aktivasi partner, silakan klik <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">di sini</Anchor>.

<div id="advanced-privacy" />

#### Privasi Lanjutan

Khusus untuk aplikasi iOS, ketika **Privasi Tingkat Lanjut (untuk iOS 14.5+ dan lebih baru)** diaktifkan, Anda dapat <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#b">mengontrol data apa yang dibagikan</Anchor> dengan ironSource melalui postback dan laporan.

<div id="transaction-id" />

### ID transaksi

Khusus untuk aplikasi iOS, saat **Bagikan ID transaksi SKAN** diaktifkan, Anda  mengizinkan AppsFlyer untuk <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">membagikan ID transaksi postback SKAdNetwork</Anchor> dengan ironSource. Dengan melakukannya, ironSource dapat mendekodekan Nilai Konversi SKAdNetwork Anda.

<div id="note-2" />

> 📘 **Catatan**
>
> Untuk interoperasi SKAN dengan AppsFlyer, hubungi manajer akun ironSource Anda untuk <Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/general/universal-skan-reporting/#step-1">mengaktifkan pengiriman data SKAN ke MMP</Anchor>.

<div id="general-settings" />

### Pengaturan umum

**ID Pemasang Iklan**

ironSource terhubung dengan AppsFlyer melalui ID pemasang iklan unik (angka 6 digit) dan kata sandi. Jika Anda belum memiliki ID dan kata sandi pemasang iklan, Anda harus mendapatkannya dari ironSource untuk melanjutkan integrasi. Jika tidak, salin ID dan kata sandi dan tempelkan ke bidang masing-masing.

<div id="install-and-re-engagement-attribution" />

### Atribusi Penginstalan dan Interaksi Ulang

Kedua sakelar ini mengaktifkan pengaitan ke penginstalan baru ironSource dan pengaitan ulang pengguna yang **melihat** iklan Anda tetapi **tidak mengekliknya** . Pelajari selengkapnya tentang <Anchor target="_blank" href="/marketers/id/docs/measure-view-through-engagements">atribusi lihat-tayang</Anchor>.

**Untuk mengatribusikan penginstalan baru:**

1. Aktifkan **Instal atribusi lihat-tayang**.
2. Konfigurasikan panjang jendela lookback **lihat-tayang** di [tab tautan Atribusi](/docs/ironsource-campaign-configuration#attribution-link-tab).

**Untuk mengatribusikan interaksi ulang baru dari pengguna yang ada:**

1. Aktifkan **Atribusi lihat-tayang interaksi ulang**.
2. Konfigurasikan panjang jendela lookback **lihat-tayang** di [tab tautan Atribusi](/docs/ironsource-campaign-configuration#attribution-link-tab).

<div id="default-postbacks" />

### Postback Default

Kirim postback otomatis ke ironSource setelah penginstalan dan interaksi ulang pengguna. Gunakan bagian ini untuk menentukan **sumber pengguna** yang mengizinkan pengiriman postback ini.

Pilih **Hanya acara yang diatribusikan ke partner ini** untuk acara yang hanya berasal dari pengguna yang diatribusikan dengan ironSource.  
Pilih **Acara yang diatribusikan ke partner mana pun, atau organik** agar seluruh basis pengguna Anda tersedia untuk dilaporkan ke ironSource.

<div id="note-3" />

> 📘 **Catatan**
>
> Sebagai jaringan semua penginstalan, ironSource lebih suka menerima postback untuk semua penginstalan baru aplikasi Anda dari sumber apa pun, termasuk organik. Untuk melakukannya, pilih **Acara yang diatribusikan ke partner mana pun, atau organik** untuk mengirim semua postback penginstalan ke ironSource.

<div id="in-app-event-postbacks" />

### Postback in-app event

Konfigurasikan pemetaan in-app event dengan event ironSource, dikirim melalui postback:

1. Aktifkan **Postback in-app event**.
2. Klik **Tambahkan event** untuk menambahkan SDK atau event server-ke-server ke daftar. Tabel berikut ini menjelaskan bidang-bidang yang harus diisi:  

| Nama parameter | Deskripsi |
| --- | --- |
| **event AppsFlyer** | Nama event, seperti yang diterima oleh AppsFlyer baik dari SDK yang terintegrasi ke dalam aplikasi Anda atau dari event server-ke-server.<br />**Tip**: Tidak melihat event yang Anda cari?<ul><li>Pastikan untuk mengaktifkan event di perangkat dengan instalasi non-organik dan periksa kembali.</li><li>Ketik di **AppsFlyer event**, lalu klik **Create custom**. Baca lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#event-khusus">pemetaan event kustom</Anchor>.</li></ul> |
| **dipetakan ke event mitra** | Nama atau ID unik setiap event sebagaimana didefinisikan di pihak mitra. Kemungkinan konfigurasi pemetaannya adalah:<ul><li>**Bidang teks:** Dapatkan ID event terkait dari mitra.</li><li>**Kotak drop-down:** Pilih event AppsFlyer yang telah ditentukan sebelumnya yang paling sesuai.</li><li>**Apa adanya**: Kirim event apa adanya, tanpa pemetaan nama.</li></ul> |
| **untuk pengguna dari** | Pilih opsi pengiriman untuk event:<ul><li>**Khusus mitra ini**: Kirim postback hanya jika event ini diatribusikan ke mitra ini.</li><li>**Semua sumber media termasuk organik**: Kirim postback untuk event yang diatribusikan ke mitra mana pun, serta event organik.</li></ul> |
| **termasuk** | <ul><li>**Tidak ada data (default)**: Kirim hanya event itu sendiri tanpa nilai event apa pun.</li><li>**Nilai dan pendapatan**: Kirim semua parameter event, **termasuk** nilai pendapatan (jika terdapat dalam event).</li><li>**Nilai tanpa pendapatan**: Kirim semua parameter **kecuali** nilai pendapatan.</li></ul> |

3. [Opsional] Klik **Tambahkan ketentuan**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/a97c5e34c264ddfa9f94b894520f849a3e59b42be14839ee37c71a5b6cc5ebd7-17612766801425.png" width="30px" />ikon untuk <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#postback-in-app-event-bersyarat">mengatur kondisi</Anchor> suatu event.
4. Klik **Simpan integrasi**.
5. [Opsional]Setelah menyimpan integrasi, sambil tetap membuka halaman konfigurasi, Anda dapat mengintegrasikan lebih banyak aplikasi dengan mitra:
   1. Dari pojok kiri atas, di bawah nama mitra, klik nama aplikasi untuk membuka daftar aplikasi.
   2. Pilih aplikasi lainnya dari daftar drop-down.
   3. Ulangi <Anchor target="_blank" href="/marketers/id/docs/amazon-ads-campaign-configuration#integration-tab">langkah integrasi</Anchor>  untuk aplikasi yang dipilih.

<div id="note-4" />

> 📘 **Catatan**
>
> * Hanya untuk aplikasi iOS: Kontrol Anda atas data yang dibagikan dengan mitra melalui postback dan <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions">laporan</Anchor> bergantung pada status sakelar **Privasi Lanjutan (untuk iOS 14.5+ dan yang lebih baru)** .
> * Anda dapat mengirimkan <Anchor target="_blank" href="/marketers/id/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">postback pendapatan iklan</Anchor> ke ironSource agar mereka dapat mengoptimalkan kampanye menggunakan data pendapatan iklan:
>   * **Nama event:** af\_ad\_revenue
>   * **Dipetakan ke:** ad\_revenue

<div id="attribution-link-tab" />

<Accordion title="Tab tautan atribusi">

Hasilkan dan simpan tautan atribusi dan kirim ke mitra untuk mengatribusikan kampanye, ad set, atau iklan tunggal tertentu - baik untuk UA maupun kampanye penargetan ulang. Anda dapat menggunakan tautan platform tunggal atau <Anchor target="_blank" href="/marketers/id/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters">Selengkapnya tentang struktur dan parameter tautan atribusi</Anchor>.

**Untuk membuat tautan atribusi,** ikuti <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#attribution-link-tab">petunjuk ini</Anchor>.  
Baca lebih lanjut tentang bagaimana ironSource mendefinisikan klik dan tampilan.

</Accordion>

<div id="cost-tab" />

<Accordion title="Tab Biaya">

AppsFlyer mendapatkan detail biaya dengan API. Lihat <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabel integrasi biaya jaringan iklan</Anchor> untuk detail lengkap tentang dimensi, metrik, dan fitur yang didukung. **Catatan**: Data biaya memerlukan langganan ROI360.

**Untuk mengaktifkan API biaya**:

* <Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">Ikuti instruksi integrasi ini</Anchor>

<Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Lihat status API biaya</Anchor> dan terakhir kali AppsFlyer berhasil menarik data biaya yang cocok di dashboard status integrasi biaya (dan pendapatan iklan), atau di dashboard jaringan iklan individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Tab Pendapatan Iklan">

Jika Anda menampilkan iklan di aplikasi yang dikirimkan oleh partner, bagian ini relevan.

* ironSource menawarkan perincian pendapatan iklan teragregasi dan tingkat pengguna.
* **Potensi perbedaan saat menggunakan perincian tingkat pengguna**: Data pendapatan iklan diambil setiap hari pukul 14.00 UTC dari ironSource dan berisi data kemarin. ironSource dapat terus memperbarui data setelah kami menariknya. Ini menyebabkan perbedaan antara data AppsFlyer dan ironSource.

Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/roi360-guide-ad-revenue-attribution">atribusi pendapatan iklan</Anchor>.

**Untuk mengaktifkan API pendapatan iklan**:

* Ikuti <Anchor target="_blank" href="/marketers/id/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">petunjuk integrasi ini</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Tab Hak Akses">

Di tab ini, Anda dapat memilih izin untuk diberikan kepada ironSource, baik partner yang bertindak sebagai jaringan iklan, agensi, atau bahkan keduanya. Perhatikan bahwa meskipun atribusi dinonaktifkan untuk ironSource, tab izin aktif dan Anda dapat memberikan kontrol ke ironSource.

Gunakan tombol ini untuk memberikan izin jaringan iklan untuk menangani konfigurasinya sendiri bagi aplikasi Anda:

<div id="ad-network-permissions" />

### Izin jaringan iklan

* **Allow to configure integration** (Izinkan untuk mengonfigurasi integrasi) - mengizinkan mitra untuk mengatur tab integrasi (kecuali pada postback in-app event)
* **Allow to configure in-app event postbacks** (Izinkan untuk mengonfigurasi postback in-app event) - mengizinkan mitra untuk mengatur mapping postback in-app event ke sistemnya sendiri pada tab integrasi
* **Allow access to your retention report** (Izinkan akses ke laporan retensi) - hanya ke data retensi milik mitra
* **Allow access to your aggregate loyal user data** (Izinkan akses ke data pengguna setia agregat Anda) - hanya ke data pengguna setia milik mitra
* **Allow access to your aggregate in-app events data** (Izinkan akses ke data in-app event agregat) - hanya ke data in-app event milik mitra
* **Allow access to your aggregate revenue data** (Izinkan akses ke data pendapatan agregat) - hanya ke data pendapatan yang terkait mitra
* **Allow access to your Protect360 dashboard** (Izinkan akses ke dashboard Protect360 Anda) - hanya ke data Protect360 milik mitra dan dengan syarat fitur ini diaktifkan untuk pemasang iklan

Pelajari lebih lanjut tentang memberikan <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#permissions-tab">izin jaringan iklan</Anchor>.

<div id="agency-permissions" />

### Hak Akses Agensi

Gunakan tombol ini untuk memberikan hak akses kepada agensi dalam menangani konfigurasinya sendiri pada app Anda:

* ***Tombol utama*** - Atur ke On untuk menampilkan pilihan izin agensi
* ***Izinkan akses ke laporan retensi Anda*** - hanya ke data retensi milik agensi
* **Izinkan akses untuk menggabungkan data organic**
* **Izinkan untuk mengonfigurasi postback in-app event** - mengizinkan mitra untuk mengatur mapping postback in-app event ke sistemnya sendiri pada tab integrasi

Pelajari lebih lanjut tentang memberikan <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#hak-akses-agensi">hak akses agensi</Anchor>.

</Accordion>

</Accordion>

<div data-zendesk-anchors="h_01HCFHXQQ8111WGWYVA8FAB8J1=catatan h_01HCFHXQQ8FRF8D22A85PDN1B1=tips h_01HCFHXQQ8XYCKWPVTMK8HF165=integration-tab activate-partners=aktifkan-partner h_01HCFHXQQ8HCXPEWR4CWY55M2H=aktifkan-partner advanced-privacy=privasi-lanjutan h_01HCFHXQQ8ABQYRSBGC7Z1F1SV=privasi-lanjutan transaction-id=id-transaksi h_01HCFHXQQ8Q3BX7GSGD5MH4QT8=id-transaksi h_01HCFHXQQ8D26KT5E6YEQ50DA4=catatan-1 general-settings=pengaturan-umum h_01HCFHXQQ8J0ZC9FGCNTPMKHK6=pengaturan-umum install-and-reengagement-attribution=atribusi-penginstalan-dan-interaksi-ulang h_01HCFHXQQ8V2E8982XRSY4G50F=atribusi-penginstalan-dan-interaksi-ulang default-postbacks=postback-default h_01HCFHXQQ8Q27JXG2V7G4XZX43=postback-default h_01HCFHXQQ8XZ6H3733GPR3ZFYE=catatan-2 inapp-event-postbacks=postback-in-app-event h_01HCFHXQQ891GH196XFRXY8MYS=postback-in-app-event h_01HCFHXQQ8VF25W10CWQHTEAYW=catatan-3 h_01HCFHXQQ8AYNTCH9GHZJG594E=attribution-link-tab h_01HCFHXQQ87EBRW9NBY58XYFGP=cost-tab h_01HCFHXQQ8XZ8XQFH3XRFVHRZV=ad-revenue-tab h_01HCFHXQQ891P7ET9Q4BSQWJXT=permissions-tab ad-network-permissions=izin-jaringan-iklan h_01HCFHXQQ86VNX9WRFEZECYV7R=izin-jaringan-iklan agency-permissions=hak-akses-agensi h_01HCFHXQQ936CQ1FVHCRC58H4C=hak-akses-agensi" />
