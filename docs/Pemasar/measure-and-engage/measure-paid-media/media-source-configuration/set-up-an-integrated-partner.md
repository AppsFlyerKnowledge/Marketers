---
title: Siapkan mitra terintegrasi
metadata:
  keywords:
    - Advertisers
    - Agencies
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
  created_at: '2021-11-08T08:02:46Z'
  edited_at: '2023-11-22T12:44:49Z'
  id: 4410395957521
  locale: id
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/id/articles/4410395957521
---
> **Sekilas:** Aktifkan pengukuran atribusi, kirim postback ke mitra, dan aktifkan fitur integrasi lainnya dengan menyiapkan koneksi mitra dengan AppsFlyer.

## Overview

Mitra, sumber media, dan platform pihak ketiga terintegrasi dengan AppsFlyer by API. Artikel ini berisi petunjuk umum untuk mengaktifkan dan menyiapkan integrasi, termasuk membuat tautan atribusi untuk jaringan iklan non-SRN.

* Panduan ini tidak berlaku untuk SRN. Gunakan artikel eksplisit <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns">SRN</Anchor>.
* Beberapa jaringan iklan memiliki artikel khusus.
* Sebelum menyiapkan konfigurasi, Anda harus menghubungi mitra dan membuka akun dengan mereka.

<div id="partner-types-in-the-ecosystem" />

<Accordion title="Jenis mitra di ekosistem">

Gambar berikut berisi berbagai jenis mitra yang membentuk ekosistem atribusi.

<Image align="center" alt="Ecosystem.jpg" src="https://files.readme.io/9377db3a6a6effd7ff8139994e2e8ed8dea04331588b5df2a31f1acd643afd9f-4411031173265.jpg" />

**Bacaan terkait**: <Anchor target="_blank" href="https://www.appsflyer.com/performance-index/">Indeks Kinerja AppsFlyer</Anchor> memberi peringkat sumber media seluler menurut kategori dan wilayah.

| Jenis mitra | Deskripsi |
| --- | --- |
| Jaringan iklan | Jalankan kampanye atas nama Anda. |
| Agensi | Gunakan keahlian mereka untuk mendapatkan pengguna berkualitas tinggi dengan menjalankan kampanye atas nama Anda. Anda dapat memiliki hubungan yang transparan atau tidak transparan. |
| Mitra Pemasaran | Mitra pemasaran mengkhususkan diri untuk bekerja dengan jaringan iklan spesifik. Contoh: Mitra pengelolaan kampanye Meta, mitra pemasaran Iklan Penelusuran Apple, mitra pemasaran X. |
| Jaringan penargetan ulang | Jaringan iklan yang berspesialisasi dalam menjalankan kampanye penargetan ulang. |
| Platform pihak ketiga | Menyediakan layanan terkait BI seperti platform analitik dan otomatisasi pemasaran. |
| Atribusi TV | Partner yang memungkinkan atribusi yang lebih akurat dari install baru ke iklan TV yang ditayangkan. |
| Deteksi penipuan | Sistem anti-penipuan pihak ketiga bukan merupakan bagian dari solusi anti-penipuan AppsFlyer Protect360. |

</Accordion>

<div id="partners-in-the-marketplace" />

<Accordion title="Mitra di marketplace">

Semua mitra, sumber media, dan platform lain yang terintegrasi dengan AppsFlyer dapat ditemukan di halaman <Anchor target="_blank" href="/marketers/id/docs/partner-integrations">marketplace</Anchor> . Anda dapat menemukan baik mitra <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">aktif maupun mitra tidak aktif</Anchor> Anda dan mencari mitra baru untuk bekerja sama.

**Untuk mencari dan memfilter semua mitra, sumber media, atau platform lain di <Anchor target="_blank" href="/marketers/id/docs/partner-integrations">Marketplace</Anchor>:**

* Di AppsFlyer, di bawah **Konfigurasi** buka **Pasar Mitra**. Anda dapat menggunakan berbagai <Anchor target="_blank" href="/marketers/id/docs/partner-integrations#filters">filterpencarian</Anchor>.

<div id="invite-new-partners-to-appsflyer" />

#### Undang mitra baru ke AppsFlyer

Jika mitra yang bekerja sama dengan Anda belum terintegrasi dengan AppsFlyer, Anda dapat mengirimkan tautan undangan kepada mereka.

</Accordion>

<div id="your-integrated-partners" />

<Accordion title="Mitra terintegrasi aktif Anda">

Halaman <Anchor target="_blank" href="/marketers/id/docs/partner-integrations#active-partner-integrations">Integrasi aktif</Anchor> di Pasar Mitra menampilkan semua mitra terintegrasi <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">aktif</Anchor> Anda. Dari halaman ini, Anda dapat mempelajari tentang mitra dan mengelola integrasinya.

<div id="note" />

> 📘 **Catatan**
>
> Daftar mitra yang ditampilkan di halaman **Integrasi aktif** bervariasi menurut aplikasi yang dipilih (aplikasi terakhir yang dipilih sebelum memasuki Marketplace). Anda dapat melihat mitra mana yang terhubung ke aplikasi lain dengan mengeklik aplikasi dari pojok kiri atas dan memilih aplikasi lain.

**Untuk melihat semua mitra aktif Anda:**

* Di AppsFlyer, di bawah **Konfigurasi**, buka **Integrasi Aktif**.

Lihat <Anchor target="_blank" href="/marketers/id/docs/partner-integrations#what-you-can-do-from-the-active-integrations-page">apa yang dapat Anda lakukan dari halaman Integrasi aktif</Anchor>.

</Accordion>

<div id="about-the-integrated-partner-page" />

<Accordion title="Tentang halaman konfigurasi mitra">

Halaman ini disusun sebagai berikut:

* **Header** , berisi:
  * Nama mitra
  * Tautan ke artikel mitra khusus. Jika tidak ada artikel khusus, artikel ini akan ditampilkan.
  * Status integrasi
  * Aplikasi yang dipilih
* **Tab pengaturan**: Tab yang tersedia bergantung pada jenis mitra dan fitur yang didukung.
* **Footer** :
  * **Kembali ke daftar**: Kembali ke daftar Integrasi Aktif menggunakan opsi pemfilteran yang dipilih sebelumnya.
  * **Pesan Status**status data tab saat ini (mis., menyimpan, tersimpan, kesalahan, ada perubahan yang belum disimpan).
  * **Buang Perubahan:** Membatalkan perubahan terakhir tanpa menyimpan.
  * **Simpan:** Menyimpan pengaturan dari tab saat ini saja.

<div id="applicable-settings-tabs-per-partner-type" />

#### Tab pengaturan yang berlaku per jenis mitra

<table><thead><tr><th> </th><th colspan="2">Tab Pengaturan</th><th> </th></tr><tr><th>Jenis mitra</th><th>Integrasi </th><th>Hak Akses</th><th>Catatan</th></tr></thead><tbody><tr><td>Media Source</td><td>Y</td><td>Y</td><td><p><strong>Tersedia tab tambahan</strong>: Biaya, pendapatan iklan, tautan atribusi</p><p>Termasuk jaringan iklan, jaringan afiliasi, penerbit langsung, pengiklanan terprogram, jaringan iklan domestik China, dan Jaringan Penargetan Ulang.<br/>Untuk SRN, tab tautan atribusi tidak berlaku.</p></td></tr><tr><td>Agensi </td><td>N</td><td>Y</td><td>Agensi mandiri yang tidak berfungsi sebagai ad network </td></tr><tr><td>Platform pihak ketiga</td><td>Y</td><td>N</td><td>Platform otomatisasi Marketing atau Analisis</td></tr><tr><td> Mitra pemasaran </td><td>Y</td><td>N</td><td> </td></tr></tbody></table>

</Accordion>

<div id="important" />

<div id="set-up-a-partner-non-srn" />

## Siapkan mitra (non-SRN)

Untuk mengakses pengaturan dan mengonfigurasi kampanye Anda dengan mitra:

1. Cari mitra Anda, bisa <Anchor target="_blank" href="/marketers/id/docs/partner-integrations#manage-existing-integrations">dari marketplace</Anchor> atau dari halaman **Konfigurasi** > halaman **Integrasi** A**ktif** .
2. Selesaikan pengaturan per tab, sesuai kebutuhan. Lihat bagian berikut.

<div id="note-1" />

> 📘 **Catatan**
>
> Langkah [pengaturan Umum](/docs/set-up-an-integrated-partner#d) di tab **Integrasi** bersifat wajib untuk semua mitra. Anda juga harus menyelesaikan tab **Tautan atribusi** untuk jaringan iklan non-SRN. Tab yang tersisa adalah opsional.

<div id="integration-tab" />

<Accordion title="Tab Integration">

Integrasi mitra berbeda dalam persyaratannya dan dapat berisi sebagian dari semua kemungkinan opsi yang dijelaskan di bagian ini. Ada beberapa perbedaan antara pengaturan iOS dan Android.

<Image align="center" alt="set_up_an_integrated_partner.png" src="https://files.readme.io/441ddfcd784a000099ae75acdb234d32bfe75ab598a34a88c7f9ed651fe8f7ec-15520850610449.png" />

Selesaikan bagian sesuai kebutuhan.

<div id="i-connect-more-apps-optional" />

<div id="g-in-app-event-postback-configuration" />

<div id="default-postbacks" />

<div id="e-cross-platform-attribution" />

<div id="reengagement-window" />

<div id="non-eu-users" />

<div id="d-general-settings" />

<div id="c-transaction-id" />

<div id="b-advanced-privacy" />

<div id="a-activate-partner" />

<div id="integration-sections" />

#### Bagian integrasi

Tabel berikut mencakup berbagai bagian berbeda dari halaman integrasi. Beberapa bagian tersedia untuk semua, yang lainnya khusus untuk setiap integrasi.

<Table>
  <thead>
    <tr>
      <th>
        Bagian
      </th>
      <th>
        Deskripsi
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="a"></span>
        Aktifkan mitra
      </td>
      <td>
        Sebelum berbagi tautan atribusi dengan mitra, Anda harus mengaktifkan **Activate partner** dan selesaikan bagian lain dari tab Integrasi.

        * Jangan gunakan **Activate partner** untuk menjeda atau menonaktifkan atribusi kampanye
        * Menonaktifkan integrasi mitra  **dapat menyebabkan kerusakan permanen pada kampanye aktif** .
        * Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">aktivasi mitra</Anchor> dan dampak penonaktifan mitra.

        **Untuk mengaktifkan mitra terintegrasi**:

        1. Di AppsFlyer, buka **Konfigurasi** > **Integrasi aktif** >
        2. Cari dan pilih mitra. Anda diarahkan ke halaman konfigurasi mitra.
        3. Hidupkan **<Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">Aktifkan mitra</Anchor> .**
        4. Klik **Save Integration**.
        5. [Opsional] Untuk mengizinkan mitra <Anchor target="_blank" href="/marketers/id/docs/manage-data-access-permissions">melihat data yang dikaitkan dengan mereka</Anchor>, pastikan untuk mengaktifkan [Izin jaringan iklan](/docs/set-up-an-integrated-partner#hak-akses-ad-network) di tab [Izin](/docs/set-up-an-integrated-partner#permissions-tab).
      </td>
    </tr>
    <tr>
      <td><span id="b"></span>
        Privasi Lanjutan
      </td>
      <td>
        Untuk aplikasi iOS saja:  
        Saat **Privasi Tingkat Lanjut (untuk iOS 14.5+ dan lebih baru)** diaktifkan, Anda dapat mengontrol <Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework">data apa yang akan dibagikan</Anchor> dengan mitra melalui postback dan laporan. Ini membatasi pembagian pengidentifikasi pengguna dengan mitra. Perhatikan bahwa ketika <Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework">Privasi Lanjutan Teragregasi</Anchor> diaktifkan di Pengaturan Aplikasi, **Privasi Lanjutan (untuk iOS 14.5+ dan lebih baru)** diaktifkan dan dikunci.
      </td>
    </tr>
    <tr>
      <td><span id="c"></span>
        ID transaksi
      </td>
      <td>
        Untuk aplikasi iOS saja:  
        Saat **Bagikan ID transaksi SKAN** diaktifkan, Anda <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">membagikan ID transaksi postback SKAdNetwork</Anchor> dengan mitra. Dengan melakukannya, mitra dapat mendekode Nilai Konversi SKAdNetwork Anda.
      </td>
    </tr>
    <tr>
      <td><span id="d"></span>
        Pengaturan Umum
      </td>
      <td>
        **ID Mitra—Kredensial**  
        Beberapa mitra memerlukan kredensial untuk AppsFlyer untuk diintegrasikan dengan mereka. Mitra menyebut ID ini sebagai ID aplikasi, ID akun, ID pengguna, atau ID jaringan. Jika bidang ini ditampilkan, dapatkan ID dari dashboard mitra dan masukkan ke bidang.
      </td>
    </tr>
    <tr>
      <td><span id="e-install-attribution"></span>
        Instal atribusi
      </td>
      <td>
        Saat **Atribusi penginstalan** diaktifkan, penginstalan baru pengguna yang melihat iklan tetapi tidak mengekliknya akan diatribusikan.
      </td>
    </tr>
    <tr>
      <td><span id="e-re-engagement-attribution"></span>
        Atribusi interaksi ulang
      </td>
      <td>
        Aktifkan dan atur jendela lookback untuk mulai mengatribusikan interaksi ulang pengguna Anda yang sudah ada. Untuk non-SRN, pengaturan ini tersedia di tab Integrasi atau di tab [tautan atribusi](/docs/set-up-an-integrated-partner#pengaturan-retargeting) .

        * **Atribusi lihat-tayang interaksi ulang:** Jika  diaktifkan, interaksi ulang pengguna yang melihat iklan Anda tetapi tidak mengekliknya akan diatribusikan.
        * **Atribusi klik-tayang interaksi ulang:** Jika diaktifkan, interaksi ulang pengguna yang mengeklik iklan Anda diatribusikan.
      </td>
    </tr>
    <tr>
      <td><span id="ignore-active-users"></span>
        Abaikan pengguna aktif untuk penargetan ulang (SRN)
      </td>
      <td>
        Saat **Atribusi interaksi ulang** diaktifkan, **Abaikan pengguna aktif untuk penargetan ulang** (ditampilkan untuk <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns">SRN</Anchor>) diaktifkan. Saat diaktifkan dan **Jendela tidak aktif** diatur, konversi penargetan ulang pengguna yang aktif selama jendela tidak aktif akan diabaikan dan tidak dicatat di AppsFlyer.
      </td>
    </tr>
    <tr>
      <td><span id="e"></span>
        Atribusi lintas platform
      </td>
      <td>
        Jika **Prioritas atribusi yang sama lintas platform** diaktifkan, tayangan lintas platform selama kerangka waktu yang dipilih memiliki prioritas yang sama untuk atribusi.
      </td>
    </tr>
    <tr>
      <td><span id="f-preload-attribution"></span>
        Atribusi pramuat
      </td>
      <td>
        Saat **Atribusi pramuat** diaktifkan, penginstalan diatribusikan ke <Anchor target="_blank" href="/marketers/id/docs/measure-preload-campaigns-with-google-play-install">kampanye pramuat</Anchor>. Atur **Jendela loockback pramuat** untuk menentukan berapa lama setelah aktivasi perangkat, penginstalan pramuat dapat diatribusikan ke partner.
      </td>
    </tr>
    <tr>
      <td><span id="f-preload-equal-attribution-priority"></span>
        Prioritas atribusi sama pramuat
      </td>
      <td>
        Jika **Prioritas atribusi sama pramuat** diaktifkan, keterlibatan pramuat selama jendela lookback yang dipilih memiliki <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#metode-atribusi">prioritas atribusi</Anchor> yang sama dengan klik deterministik.
      </td>
    </tr>
    <tr>
      <td><span id="advanced-data-sharing"></span>
        Berbagi Data Tingkat Lanjutan
      </td>
      <td>
        Jika **Berbagi Data Tingkat Lanjut** diaktifkan, data tambahan dibagikan kepada mitra melalui tautan atribusi.  
        **Catatan:** Opsi berbagi ini berbeda dengan <Anchor target="_blank" href="/marketers/id/docs/meta-ads-integration-setup#aem-data-sharing">Berbagai data lanjutan AEM Meta ads.</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="f"></span>
        Postback Default
      </td>
      <td>
        Jika integrasi partner diaktifkan, Anda dapat mengirimkan postback default terkait tindakan pengguna yang terjadi sebelum peluncuran aplikasi kepada partner, seperti misalnya penginstalan, penginstalan yang ditolak, dan interaksi ulang.

        <div id="01H80XGTBQ4MPGGKSZW0D9GG9H" />

        > 📘 **Catatan**
        >
        > * Event yang ditolak adalah in-app event yang diblokir oleh <Anchor target="_blank" href="/marketers/id/docs/protect360-anti-fraud-guide">Protect360</Anchor> atau event yang ditemukan tidak sesuai dengan validasi target. Jika event ditolak, konfirmasikan dengan mitra bahwa mereka telah mengaktifkan penolakan integrasi event dengan AppsFlyer.
        > * Mitra yang tidak melakukan atribusi (seperti platform pihak ketiga) menerima postback default untuk penginstalan saja. Postback atribusi dikirim ke mitra yang diatribusikan.

        **Untuk mengonfigurasi postback default untuk mitra** , tentukan sumber pengguna untuk mengirim postback:

        * **Khusus mitra ini**: Kirim postback hanya jika event diatribusikan ke mitra ini—artinya, pengguna yang melakukannya berasal dari mitra ini.  
          **Catatan:** Dalam kasus berikut, postback default selalu ditentukan sebagai **Mitra ini saja** :
          * Pengistalan yang ditolak
          * Agensi (dengan [izin](/docs/set-up-an-integrated-partner#hak-akses-agensi))
        * **Semua sumber media termasuk organik**: Kirim postback untuk event yang diatribusikan ke mitra mana pun dan untuk event organik—artinya, pengguna yang melakukannya berasal dari sumber media mana pun.
        * **Off** : Jangan kirim postback default ke mitra ini.
      </td>
    </tr>
    <tr>
      <td><span id="g"></span>
        <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration">Postback in-app event</Anchor>
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#pemetaan-event">Petakan</Anchor> event AppsFlyer dengan event mitra lewat postback. Jika pengiriman postback diaktifkan, ini termasuk in-app event yang ditolak (event yang diblokir oleh Protect360 atau event yang ditemukan tidak sesuai dengan aturan validasi target).

        **Untuk mengonfigurasi postback in-app event:**

        1. Atur **ID Mitra** (jika diperlukan).
        2. Aktifkan  **Postback in-app event.**
        3. Atur ***Jendela postback In-app event***, jika diperlukan (baca lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#periode-waktu-postback-in-app-event">konfigurasi jendela postback in-app event</Anchor>).
        4. Klik **Add event** untuk menambahkan SDK atau event server-ke-server ke daftar.
        5. Lengkapi parameter yang diperlukan sesuai dengan <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#metode-pemetaan">metode pemetaan</Anchor>.
        6. [Opsional] Klik<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/e2543cb26e0cc02f4840040721376ae88a4015a24ac1fc271264e3965560c1f9-4413022777105.png" width="30px" /> untuk <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#postback-in-app-event-bersyarat">menyetel ketentuan</Anchor> pengiriman in-app event tertentu ke mitra.

        | Nama Parameter | Deskripsi |
        | --- | --- |
        | <span id="appsflyer-event"></span>**Event AppsFlyer** | Nama event yang diterima oleh AppsFlyer, baik yang berasal dari SDK yang terintegrasi di aplikasi Anda, atau dari event server ke server.  <br />**Tip**: Tidak melihat acara yang Anda cari?<br /><br />* Pastikan untuk mengaktifkan event di perangkat dengan instalasi non-organik dan periksa kembali.<br />* Ketik di **AppsFlyer event**, lalu klik **Create custom**. Baca lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#event-khusus">pemetaan event kustom</Anchor>. |
        | <span id="mapped-to-partner-event"></span>**dipetakan ke event mitra** | Nama atau ID unik setiap event sebagaimana didefinisikan di pihak mitra. <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#metode-pemetaan">Kemungkinan konfigurasi pemetaannya</Anchor> adalah:<br /><br />* **Bidang teks:** Dapatkan ID event terkait dari mitra.<br />* **Kotak drop-down:** Pilih event mitra yang telah ditentukan sebelumnya yang paling sesuai.<br />* **Apa adanya**: mengirim event apa adanya, tanpa pemetaan nama event. |
        | <span id="for-users-from"></span>**untuk pengguna dari** | Pilih opsi pengiriman untuk event:<br /><br />* **Khusus mitra ini**: Kirim postback hanya jika event diatribusikan ke mitra ini—artinya, pengguna yang melakukannya berasal dari mitra ini.<br />* **Semua sumber media termasuk organik**: Kirim postback untuk event yang dihubungkan ke mitra mana pun dan untuk acara organik—artinya, jika pengguna yang melakukannya berasal dari sumber media mana pun. |
        | <span id="including"></span>**termasuk** | Pilih <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#data-untuk-disertakan-dalam-postback">data event mana yang</Anchor> akan dibagikan dengan mitra di postback:<br /><br />* **Tidak ada nilai & tidak ada pendapatan**: Kirim hanya event tersebut tanpa parameter apa pun (nilai atau pendapatan).<br />* **Nilai dan tanpa pendapatan**: Mengirim semua parameter **tidak termasuk** nilai pendapatan.<br />* **Nilai dan pendapatan**: Mengirimkan semua parameter event, **termasuk** nilai pendapatan (jika ada dalam event). |

         Catatan:

        * Acara yang dipetakan di tab Integrasi untuk mitra tertentu dapat diterapkan baik untuk <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">postback standar maupun SKAN</Anchor>.
        * Postback dikirim ke mitra dalam waktu aktual.
        * Nama event AppsFlyer dapat dipilih atau diketik.  
          Nilai yang diketik diizinkan memiliki spasi bergaris bawah (garis bawah) sebelum atau setelah nama event. Gunakan spasi bergaris bawah hanya jika nama event yang dikirim dari AppsFlyer memiliki spasi bergaris bawah juga.
        * **Penting**:Nama event peka akan huruf besar-kecil. Untuk menghindari perbedaan, pastikan Anda menggunakan nama event yang benar untuk semua sumber media dan versi aplikasi.
        * Jika bagian ***Postback Event In-App*** tidak ada di tab ***Integrasi***, artinya mitra belum mengatur pencatatan in-app event dengan AppsFlyer pada awal konfigurasi. Mitra dapat menghubungi AppsFlyer menggunakan <Anchor target="_blank" href="https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif">widget asisten mitra</Anchor> untuk menyelesaikan integrasi.
        * Untuk mencegah pemasang iklan membagikan terlalu banyak informasi kepada platform pihak ketiga secara tidak sengaja, kami telah menghapus opsi **Kirim semua event (tidak termasuk pencopotan penginstalan dan sesi)** untuk platform pihak ketiga, mulai Maret 2019. Platform pihak ketiga yang dikonfigurasi sebelum ini, masih mempertahankan opsi pengaturan ini.

        Bacaan terkait:

        * Konfigurasi <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration">postback in-app event</Anchor>
        * Konfigurasi <Anchor target="_blank" href="/marketers/id/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">postback event pendapatan iklan</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="h"></span>
        Simpan integrasi
      </td>
      <td>
        Klik **Save Integration** setelah melakukan perubahan.
      </td>
    </tr>
    <tr>
      <td><span id="i"></span>
        Hubungkan lebih banyak aplikasi (opsional)
      </td>
      <td>
        Setelah menyimpan integrasi, sambil tetap berada di halaman konfigurasi, Anda dapat mengintegrasikan lebih banyak aplikasi Anda dengan mitra.

        1. Dari pojok kiri atas, di bawah nama mitra, klik nama aplikasi untuk membuka daftar aplikasi.
        2. Pilih aplikasi lainnya dari daftar drop-down.
        3. Ulangi langkah integrasi untuk aplikasi yang dipilih.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Tab Link Atribusi">

Buat dan simpan tautan atribusi untuk penggunaan jaringan iklan klik (non-SRN), dan kirim tautan atribusi ke mitra untuk mengatribusikan kampanye, set iklan, atau iklan tunggal tertentu.

**Catatan:** SRN tidak menerapkan tautan atribusi yang dihasilkan pengiklan sehingga tab ini tidak relevan dengan kampanye SRN.

**Untuk menghasilkan tautan atribusi** :

1. Pilih salah satu **Gunakan tautan platform tunggal** atau **Gunakan OneLink** .

   Pilih **Gunakan tautan platform tunggal** jika salah satu dari berikut ini berlaku:

   * Anda berencana untuk hanya menggunakan <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">skema URI</Anchor> untuk membuka aplikasi.
   * Anda tidak perlu menautkan langsung (deep link) ke URL.

   Pilih **Gunakan OneLink** jika salah satu dari berikut ini berlaku:

   * Anda menginginkan satu tautan untuk aplikasi Android dan iOS, atau
   * Anda ingin menggunakan Tautan Aplikasi Android atau Tautan Universal iOS untuk membuka aplikasi.
   * Anda menginginkan kemampuan deep linking.

   **Catatan** : Memilih OneLink akan mengubah tautan perekaman klik dari aplikasi khusus ke <Anchor target="_blank" href="/marketers/id/docs/onelink-guide">URL OneLink</Anchor>.
2. Jika Anda memilih **Gunakan OneLink**:

   1. Pilih templat OneLink mana yang ingin Anda gunakan untuk membuka aplikasi (dan kemungkinan deep link).
   2. [Opsional] Masukkan nilai **Deep link/Tautan langsung**.
   3. [Opsional] Masukkan nilai **Deep link tambahan** .
3. Tambahkan parameter untuk <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#parameter-khusus-android">Android</Anchor> dan <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#parameter-spesifik-ios">iOS</Anchor>, sesuai kebutuhan.
4. [Opsional] Pilih parameter atribusi tambahan.

<div id="attribution-link-parameters" />

#### Parameter link atribusi

<Image align="center" alt="attribution-link-parameters-en_us.png" src="https://files.readme.io/5f010d760295d53b8ff1891b58aaa57ac8171af7d08d7bc0df07b0998f81f666-4414306787601.png" />

Menambahkan parameter ke tautan atribusi memungkinkan Anda melakukan analisis penelusuran secara menyeluruh. Parameter yang sudah ditentukan pada tautan atribusi dapat diedit dengan menambahkannya dan nilai barunya di sini. Saat menyimpan tautan atribusi, semua parameter yang dikonfigurasikan di tab ini disimpan.

Pilih parameter mana yang ingin Anda tambahkan ke tautan atribusi.

<div id="attribution-link-parameters-1" />

#### Parameter link atribusi

| Nama | Deskripsi | Parameter Link Atribusi |
| --- | --- | --- |
| Kampanye | **Parameter yang diperlukan.**  <br />Bandingkan berbagai kampanye yang dijalankan dengan sumber media. | c |
| adset | Bandingkan berbagai ad set dalam kampanye tertentu dari sumber media. | af\_adset |
| Nama Iklan | Bandingkan berbagai materi iklan dalam ad set tertentu di dalam kampanye tertentu dari sumber media. | af\_ad |
| Site ID dan Sub Site ID | **Parameter yang diperlukan.**<br /><br />Atur Site ID untuk mengatribusi penginstalan ke penerbit tertentu.<br /><br />ID situs harus diteruskan ke AppsFlyer di tautan atribusi karena ID ini:<ul><li>Memberikan kejelasan dan transparansi tentang penerbit.</li><li>Digunakan oleh AppsFlyer untuk mengidentifikasi dan menghapus penayang palsu, dan kluster lalu-lintas lainnya.</li></ul>Perhatikan bahwa ketiadaan ID Situs tidak akan memengaruhi atribusi. Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#site-id-parameter">parameter ID Situs</Anchor>.<br /><br />Jika ada banyak penayang, sebaiknya batasi jumlah ID situs yang digunakan dan gunakan parameter ID subsitus, untuk menghindari <Anchor target="_blank" href="/marketers/id/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">melebihi batasan ID situs</Anchor> . | af\_siteid and af\_sub\_siteid |
| Parameter Pelanggan | Gunakan salah satu dari 5 parameter pelanggan untuk memasukkan nilai yang berguna. Harap perhatikan bahwa parameter ini di-parsing dan muncul di laporan data lengkap, yang membuat parameter ini sangat berguna untuk melakukan agregasi atau pemfilteran. | af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5 |

Anda dapat menambahkan parameter lain ke tautan atribusi dengan menuliskannya pada kotak parameter baru. Anda dapat menggunakan semua <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters">Parameter URL AppsFlyer yang tersedia.</Anchor> Perhatikan bahwa hanya skema URI dan parameter OneLink yang disandikan pada tautan atribusi.

<div id="retargeting-settings" />

#### Pengaturan Retargeting

**Saat penargetan ulang aktif** : AppsFlyer mengenali sebuah tautan sebagai tautan atribusi <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide">penargetan ulang</Anchor> , bukan tautan akuisisi pengguna, dengan menambahkan `&is_retargeting=true` ke tautan atribusi. **Parameter link atribusi:** is\_retargeting

Untuk menggunakan tautan Anda untuk penargetan ulang:

1. Aktifkan **pengaturan Penargetan Ulang** .
2. [Opsional] Masukkan skema URI  jika Anda ingin skema URI membuka aplikasi.  
    **Catatan**:
   * Skema URI direkomendasikan sebagai metode fallback untuk membuka aplikasi jika Tautan Universal atau Tautan Aplikasi gagal.
   * Jika Anda menambahkan skema URI di sini, skema URI tersebut akan menggantikan skema URI lainnya yang sudah ada di pengaturan template OneLink Anda.
   * Skema URI ditambahkan ke tautan di parameter af\_dp.
3. [Opsional] Aktifkan **Abaikan pengguna aktif untuk penargetan ulang** .
4. Atur jendela tidak aktif untuk menentukan pengguna mana yang dianggap aktif dan tidak aktif.
5. Atur jendela interaksi ulang untuk menentukan jangka waktu setelah interaksi ulang, di mana in-app event pengguna diatribusikan ke sumber media penargetan ulang.

   * Anda dapat mengatur nilai dalam satuan hari (1-90), jam (hingga 23), atau bahkan selamanya.
   * Jendela interaksi ulang ditambahkan ke tautan di parameter af\_reengagement\_window.

<div id="click-through-attribution" />

#### Atribusi Click-Through

Gunakan pengaturan untuk mengatur **waktu maksimum dari klik hingga penginstalan** . Hanya penginstalan (peluncuran pertama) yang terjadi dalam jendela lihat balik yang diatribusikan.

Rentang yang diizinkan: 1-23 jam atau 1-30 hari.

**Parameter link atribusi:** af\_click\_lookback

Pelajari selengkapnya tentang <Anchor target="_blank" href="/marketers/id/docs/set-up-lookback-windows">klik jendela lookback</Anchor>.

**Link Atribusi Klik**

<Image align="center" alt="click-through-attribution-link_en-us.png" src="https://files.readme.io/aba15af3164c4f233625cd56f90aa4d1a18b834cfb151c4e7042fa099c8f9125-4411038599953.png" />

Ini adalah tautan atribusi yang berisi semua informasi pengaturan yang telah Anda tetapkan. Anda dapat menyimpan tautan untuk referensi di masa mendatang dengan mengeklik **Simpan tautan atribusi** .

**Untuk menyalin tautan atribusi klik:**

1. Klik **Simpan tautan atribusi.**
2. Salin tautan yang dihasilkan.

Kirim tautan ke mitra untuk diaktifkan saat calon pelanggan mengklik iklan terkait.

<div id="view-through-attribution-lookback-window" />

#### Lookback Window Atribusi View-Through

Tetapkan **waktu maksimum mulai dari tayangan hingga penginstalan** . Hanya penginstalan (peluncuran pertama) yang terjadi di dalam lookback window (jendela lihat-balik), setelah tayangan iklan, yang dapat diatribusikan ke partner, dengan syarat tidak ada klik iklan relevan lainnya.

Anda dapat menyesuaikan nilai ini menjadi 1-24 jam.

**Parameter link atribusi:** af\_viewthrough\_lookback

Pelajari selengkapnya tentang <Anchor target="_blank" href="/marketers/id/docs/set-up-lookback-windows">atribusi lihat-tayang (view-through)</Anchor>.

**Link Atribusi Impresi**

<Image align="center" alt="impressions-attribution-link_en-us.png" src="https://files.readme.io/76a2d084f66f3a279b281f60a465af5098e05de8de128cfd6f04a97fe52c4dc6-4411047429265.png" />

Link atribusi impresi berisi data atribusi yang serupa dengan link klik (selain lookback window yang berbeda). Anda dapat menyimpan tautan untuk referensi di masa mendatang dengan mengeklik **Simpan tautan atribusi** .

Klik Save attribution link (Simpan tautan atribusi) lalu salin tautan yang dibuat.

**Untuk menyalin tautan atribusi impresi:**

1. Klik **Simpan tautan atribusi.**
2. Salin tautan yang dihasilkan.

Kirim ke mitra untuk diaktifkan saat iklan terkait tampil, biasanya selama 1 detik atau lebih.

</Accordion>

<div id="cost-tab" />

<Accordion title="Tab biaya">

* Data biaya dilaporkan oleh mitra terintegrasi Anda di klik atau oleh Cost API.
* Praktik terbaiknya adalah menerapkan Cost API (API Biaya) (langganan ROI360 diperlukan).
* API Biaya mencakup laporan klik dan tayangan. Lihat <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabel integrasi biaya jaringan iklan</Anchor> untuk detail lengkap tentang dimensi, metrik, dan fitur yang didukung.

<div id="note-2" />

> 📘 **Catatan**
>
> Jika pengiklan menggunakan biro iklan untuk menjalankan kampanye mereka, biro iklan, dan bukan pengiklan, harus berintegrasi dengan mitra terkait. Jika tidak, jika pengiklan dan agensi berintegrasi dengan partner menggunakan kredensial yang sama untuk aplikasi yang sama, data biaya akan digandakan.

<div id="enabling-cost-data-by-api" />

#### Mengaktifkan data biaya oleh API

**Untuk mengaktifkan API Biaya**:

* Ikuti <Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">petunjuk integrasi ini</Anchor>.

<div id="cost-data-sync-status" />

#### Status Sinkronisasi Data Biaya

<Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Lihat status API biaya</Anchor> dan terakhir kali AppsFlyer berhasil menarik data biaya yang cocok di dashboard status integrasi biaya (dan pendapatan iklan), atau di dashboard jaringan iklan individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Tab Ad Revenue">

Jika Anda bertindak sebagai penerbit yang menampilkan iklan di aplikasi Anda, fungsi pendapatan iklan memungkinkan Anda untuk mengatribusikan pendapatan iklan dengan media source (sumber media) yang membawa pengguna. <Anchor target="_blank" href="/marketers/id/docs/roi360-guide-ad-revenue-attribution">Tentang atribusi pendapatan iklan.</Anchor>

<div id="enable-ad-revenue-attribution" />

#### Mengaktifkan atribusi pendapatan iklan

1. Periksa untuk melihat metode mana, <Anchor target="_blank" href="/marketers/id/docs/roi360-guide-ad-revenue-attribution#list-of-ad-revenue-integrated-partners">agregat atau atribusi tingkat pengguna</Anchor>, yang didukung oleh mitra.
2. Ikuti metode yang sesuai dalam panduan <Anchor target="_blank" href="/marketers/id/docs/roi360-guide-ad-revenue-attribution#implementasi">integrasi pendapatan iklan</Anchor>.

<div id="ad-revenue-api-status-messages" />

#### Pesan status API pendapatan iklan

| Status | Keterangan/diperlukan tindakan |
| --- | --- |
| Aktif | Koneksinya aktif dan menarik data. |
| Tidak ada data untuk ditarik ditemukan. | Koneksinya berhasil. Mitra tidak memiliki data apa pun terkait aplikasi ini. |
| API mitra tidak merespons. Hubungi tim dukungan AppsFlyer. | Server mitra tidak merespons AppsFlyer. |
| Kredensial tidak valid. Masukkan kredensial yang diperbarui. |  |
| Terjadi kesalahan. Hubungi tim dukungan AppsFlyer. | Ada kendala teknis. |
| Data mitra belum siap. Jika masalah berlanjut, hubungi tim dukungan AppsFlyer. |  |
| Data sedang diproses dan akan segera tersedia. | Kami sedang memproses data yang diterima dari mitra. Data akan segera tersedia di dashboard dan laporan. |
| Data tidak berhasil ditarik | Jika status ini masih berlanjut, hubungi tim dukungan AppsFlyer. |

</Accordion>

<div id="permissions-tab" />

<Accordion title="Tab Permissions">

* Memungkinkan mitra untuk melakukan berbagai tindakan dan untuk mengakses data Anda berdasarkan hak akses yang tersedia.
* Anda tidak harus mengaktifkan integrasi atribusi dengan mitra untuk memberikan mereka hak akses.
* **Jaringan iklan yang diatur oleh agensi:** Saat pengaturan mitra dilakukan oleh agensi, pemasang iklan tidak dapat melihat status aktivasi jaringan iklan atau hak akses yang diberikan.
* Jika hubungan Anda dengan mitra hanya agensi, abaikan bagian **Hak Akses Jaringan Iklan** dan atur bagian **Hak Akses Agensi** .

<div id="note-3" />

<div id="ad-network-permissions" />

#### Hak Akses Ad Network

**Untuk memberikan izin ke jaringan iklan dan anggota tim mereka:**

1. Hidupkan **Izin jaringan iklan**.
   * Aplikasi Anda muncul di dashboard jaringan iklan.
   * Admin jaringan iklan memiliki izin ke <Anchor target="_blank" href="/marketers/id/docs/manage-data-access-permissions">lihat data dasar tentang aplikasi.</Anchor>
2. Berikan izin ke anggota tim jaringan iklan:  
   * Untuk memberikan hak akses kepada anggota tim tertentu, Anda harus menambahkan anggota tim menggunakan alamat email mereka.  
     **Untuk menambahkan anggota tim**:
     1. Klik **Tambahkan anggota tim**
     2. Masukkan email anggota tim ad network
     3. Klik **Tambahkan**.
3. Pilih hak akses tambahan untuk diberikan ke jaringan iklan: 

| **Hak Akses** | **Kapabilitas diberikan** |
| --- | --- |
| <span id="configure-integration"></span>Konfigurasikan integrasi | Jaringan iklan dapat mengubah parameter pada tab integrasi |
| <span id="configure-inapp-event-postbacks"></span>Konfigurasikan postback in-app event. | Jaringan iklan dapat: Membuat, menentukan, dan mengubah pengaturan postback.<br /><br />**Perhatian**! Jika izin ini dan **fitur Configure integration** diaktifkan secara bersamaan, jaringan iklan memiliki akses ke semua event. Ini termasuk lalu-lintas organik dan non-organik dari semua sumber media. |
| <span id="access-retention-report"></span>Akses laporan retensi | Jaringan iklan dapat mengakses laporan retensi aplikasi. Mereka hanya akan melihat data yang terkait dengan sesi mereka. |
| <span id="access-aggregate-loyal-users-data"></span>Akses data agregat pengguna setia | Jaringan iklan dapat mengakses metrik <Anchor target="_blank" href="/marketers/id/docs/about-a-loyal-user">pengguna setia</Anchor> mereka sendiri. |
| <span id="access-aggregate-conversions-data"></span>Akses data konversi gabungan | Jaringan iklan dapat mengakses laporan metrik event konversi gabungan mereka. Ini termasuk penginstalan, interaksi ulang, penginstalan ulang, dan atribusi ulang. Contoh: <Anchor target="_blank" href="/partners/id/docs/aggregated-campaign-performance-report-for-ad-networks">Laporan kinerja kampanye gabungan untuk jaringan iklan</Anchor>. |
| <span id="access-aggregate-inapp-events-data"></span>Akses data in-app event gabungan | Jaringan iklan dapat:<ul><li>Akses ke laporan gabungan data in-app event. Mitra mendapatkan akses ke semua data in-app event, termasuk data in-app event Protect360, tidak hanya ke event yang dipetakan ke dalam konfigurasi postback.</li><li>Akses laporan gabungan data monetisasi iklan,  yang mungkin menyertakan event monetisasi iklan dari sumber media lain.</li></ul> |
| <span id="view-validation-rules"></span>Lihat aturan validasi | Jaringan iklan dapat melihat detail <Anchor target="_blank" href="/marketers/id/docs/implement-validation-rules-to-prevent-fraud">aturan validasi</Anchor> . |
| <span id="access-aggregate-revenue-data"></span>Akses data pendapatan gabungan | Jaringan iklan dapat mengakses laporan gabungan dari data dalam aplikasi dan pendapatan iklan yang diatribusikan ke pengguna yang dibawa oleh jaringan iklan. **Catatan:** Izin ini tidak secara langsung mengidentifikasi mitra pendapatan iklan. Namun, jika Anda telah menyetel nama event monetisasi untuk menyertakan nama mitra, Anda mungkin mengungkapkan identitas jaringan monetisasi secara tidak sengaja. |
| <span id="use-ad-spend-ingestion"></span>Gunakan penyerapan belanja iklan | Jaringan iklan dapat:<ul><li>Akses jendela <Anchor target="_blank" href="/marketers/id/docs/import-cost-data">Penyerapan Belanja Iklan</Anchor>. Jendela ini hanya menampilkan aplikasi yang izinnya mereka miliki.</li><li>Kirim file belanja iklan untuk pelaporan.</li></ul> |
| <span id="access-protect360-dashboard-raw-data"></span>Akses dasboard Protect360 & data lengkap | Jaringan iklan dapat:<ul><li>Mengakses dashboard Protect360 mereka (termasuk <Anchor target="_blank" href="/marketers/id/docs/basic-fraud-detection-and-insights-with-protectlite-dashboard-and-reporting">ProtectLITE</Anchor>).</li><li>Akses Protect360, Aturan Validasi, dan data lengkap jika merupakan mereka merupakan bagian dari paket langganan Anda. ProtectLITE tidak menyertakan akses ke data lengkap.</li></ul>**Catatan:** Ketika Anda berlangganan <Anchor target="_blank" href="/marketers/id/docs/protect360-anti-fraud-guide">Protect360</Anchor> , jaringan iklan dapat melihat dashboard lengkap. Tanpa langganan Protect360, mereka dapat melihat dashboard lite. |
| <span id="access-ad-revenue-raw-data"></span>Mengakses data lengkap pendapatan iklan | Jaringan iklan dapat mengakses <Anchor target="_blank" href="/partners/id/docs/ad-revenue-signals-for-ua-ad-networks">data pendapatan iklan mereka untuk digunakan demi pengoptimalan UA</Anchor>.   <br />**Catatan:** Izin ini hanya tersedia untuk aplikasi dengan langganan <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor> . |

<div id="important-1" />

<div id="agency-permissions" />

#### Hak Akses Agensi

* Saat Anda memberikan izin kepada agensi, mereka dapat memberikan hak akses untuk mengelola aplikasi Anda kepada jaringan iklan yang bekerja sama dengan mereka. Hal ini sama seperti memberikan hak akses ke jaringan iklan.
* Jika Anda bekerja dengan jaringan iklan dan agensi Anda juga bekerja dengan jaringan iklan ini, Anda berdua dapat mengedit izin anggota tim jaringan iklan untuk melihat dasbor aplikasi. Artinya, jika Anda melihat anggota tim jaringan iklan baru yang tidak Anda tambahkan, atau anggota tim yang tidak Anda hapus hilang, mungkin pemasar menambahkan atau menghapusnya.
* **Perhatian:** Penginstalan agensi yang terjadi saat kontrol dinonaktifkan itu tidak diatribusikan ke agensi dan tidak ditampilkan di dashboard dan data agensi. Pelajari selengkapnya tentang <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation#hak-akses-agensi">aktivasi agensi</Anchor>.
* Baca semua tentang <Anchor target="_blank" href="/partners/id/docs/getting-started-agency-onboarding#what-does-it-mean-to-get-permission-from-a-marketer">apa yang dapat dilakukan agensi</Anchor> ketika diberikan izin.

**Untuk memberikan hak akses kepada agensi:**

1. Aktifkan **Izin agensi**.
2. Pilih hak akses yang akan diberikan kepada agensi: 

| **Hak Akses** | **Kapabilitas diberikan** |
| --- | --- |
| <span id="change-advanced-privacy-configuration"></span>Ubah konfigurasi Privasi Lanjutan | Agensi dapat mengubah setelan <Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework">berbagi data Privasi Lanjutan</Anchor> jaringan iklan. |
| <span id="access-retention-and-cohort-reports"></span>Akses retensi dan laporan kohort | Agensi dapatmengakses data retensi/kelompok yang dibuat oleh pengguna yang dibawa oleh agensi saja. |
| <span id="access-aggregate-organic-data"></span>Akses data organik agregat | Agensi dapatmengakses data organik agregat |
| <span id="view-validation-rules::6872643b"></span>Lihat aturan validasi | Agensi dapat melihat detail aturan validasi. |
| <span id="add-validation-rules"></span>Tambahkan aturan validasi | Agensi dapat menambahkan dan mengedit aturan validasi. Tersedia saat **Lihat aturan validasi** diaktifkan.   <br />**Catatan**: Agensi tidak dapat mengedit aturan yang dibuat oleh pemasang iklan. |
| <span id="access-rawdata-reports"></span>Akses laporan data lengkap | Agensi dapat mengakses laporan data lengkap untuk lalu lintas yang diatribusikan ke agensi. Pemasang iklan tidak dapat membatasi event yang dapat dilihat agensi dalam laporan. |
| <span id="access-protect360-dashboard-raw-data::dd9829fd"></span>Akses dasboard Protect360 & data lengkap | Agensi dapat:<ul><li>Akses dashboard agregat Protect360 Anda</li><li>Akses Protect360, Aturan Validasi, dan data lengkap jika mereka merupakan bagian dari paket langganan Anda</li></ul>**Catatan:** Untuk pemasang iklan yang bekerja dengan jaringan iklan melalui agensi, agar jaringan iklan dan agensi dapat mengakses data, pemasang iklan harus mengintegrasikan agensi dan jaringan iklan di AppsFlyer dan memberi keduanya izin untuk mengakses data. Jika hanya agensi yang terintegrasi dan diberikan izin, jaringan iklan tidak memiliki akses ke data tersebut. |
| <span id="configure-inapp-event-postbacks::8743ba60"></span>Konfigurasikan postback in-app event. | Agensi dapat mengonfigurasi postback in-app event dari event tertentu yang Anda pilih:<ul><li>**Tambahkan event:** Dari menu tarik-turun, pilih event yang Anda setujui dengan memberikan izin agensi.</li></ul>Opsi berikut berlaku untuk event yang Anda pilih:<ul><li>**Kirim pendapatan acara:** Saat diaktifkan, agensi dapat mengonfigurasi pengiriman acara termasuk nilai uangnya.</li><li>**Opsi pengiriman:**<ul><li>**Hanya mitra ini:** Jika dipilih, agensi dapat mengonfigurasi pengiriman postback hanya untuk event  yang diatribusikan ke lalu lintas yang mereka bawa sendiri</li><li>**Semua sumber media, termasuk organik:** Jika dipilih, agensi dapat mengonfigurasi pengiriman postback untuk event yang diatribusikan ke semua sumber media, agensi, dan pengguna organik lainnya.</li></ul></li></ul> |

Pelajari lebih lanjut tentang <Anchor target="_blank" href="/partners/id/docs/about-agency-accounts#akses-agen-ke-data-pemasar">bekerja dengan agensi</Anchor>.

</Accordion>

<div id="test-the-integration" />

## Uji integrasinya

Setelah menyelesaikan integrasi mitra, dan sebelum Anda mulai menjalankan kampanye dengan mitra yang baru ditambahkan, penting untuk menguji integrasi tersebut. Kesalahan kemungkinan besar terjadi selama penyiapan. Pengujian lebih awal menghindari risiko menghabiskan banyak sumber daya, hanya untuk menemukan data atribusi Anda hilang atau salah. 

<div id="note-4" />

> 📘 **Catatan**
>
> Sebelum menguji integrasi, pastikan untuk terlebih dahulu <Anchor target="_blank" href="/marketers/id/docs/testing-the-sdk-integration-for-marketers">menguji aplikasi untuk integrasi SDK dasar,</Anchor> termasuk penginstalan organik dan non-organik.

<div id="test-the-attribution-link-for-nonsrns" />

<Accordion title="Uji tautan atribusi untuk non-SRN">

Jaringan iklan non-SRN, yang terdiri dari 99,5% jaringan iklan terintegrasi, menggunakan tautan atribusi AppsFlyer. Demikian pula, atribusi media yang dimiliki dilakukan dengan menggunakan tautan atribusi khusus AppsFlyer.

Karena atribusi yang tepat tergantung pada parameter di tautan atribusinya, lakukan pengujian sebelum Anda memulai kampanye baru dengan jaringan iklan reguler atau tautan atribusi khusus

**Untuk menguji tautan atribusi:**

1. Buat [tautan atribusi](/docs/set-up-an-integrated-partner#attribution-link-tab).
2. Kirim tautan atribusi baru ke perangkat uji <Anchor target="_blank" href="/marketers/id/docs/registering-test-devices">terdaftar</Anchor>  Anda (melalui email atau kode QR).
3. Klik tautannya, pastikan Anda dialihkan ke app store.
4. Instal aplikasi
5. Luncurkan aplikasi.
6. Periksa apakah penginstalan muncul pada dashboard AppsFlyer di bawah nama sumber media mitra. Tunggu hingga 30 menit hingga penginstalan muncul di dashboard.
7. Drill down ke level kampanye (dengan memilih partner di **filter Media source** di bagian atas halaman garis besar) untuk memastikan install muncul di bagian nama kampanye yang benar
8. Jika perlu, lanjutkan drill down dan periksa juga level adset dan iklan

</Accordion>

<div id="test-the-srn-integration" />

<Accordion title="Uji integrasi SRN">

SRN seperti Meta ads, Iklan Pencarian Apple, dan Google Ads tidak mengandalkan tautan atribusi eksternal untuk tujuan atribusi. Sebagai gantinya, SRN menerima permintaan dari AppsFlyer, mengatribusi mereka sendiri dan memberikan jawaban. Oleh karena itu, tidak mungkin menguji integrasi secara terpisah dari sistem jaringan seperti pada jaringan iklan reguler. Anda harus menguji integrasi secara terpisah dengan setiap SRN yang Anda gunakan.

**Untuk menguji integrasi SRN**:

1. Lakukan pengaturan SRN lengkap di AppsFlyer sesuai dengan <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns#srn-diintegrasikan-dengan-appsflyer">panduan pengaturan SRN spesifik</Anchor>.
2. Pasang kampanye low budget baru dengan partner SRN
3. Ketika dashboard mitra menampilkan penginstalan baru, periksa apakah mereka muncul di dashboard AppsFlyer di bawah nama sumber media mitra.
4. Di dasbor Overview (Tinjauan), telusuri ke tingkat kampanye, dengan memilih mitra di **Filter Sumber Media**, untuk memastikan bahwa penginstalan muncul di bawah nama kampanye yang benar. Tunggu hingga 30 menit hingga penginstalan muncul di dasbor.
5. Jika perlu, lanjutkan penelusuran untuk memeriksa level adset dan iklan tunggal.

Jika semuanya sudah sesuai, Anda dapat memulai kampanye baru beranggaran besar dengan mitra tersebut. Ini cukup untuk menguji integrasi sekali per mitra SRN. Artinya, tidak perlu menguji per kampanye.

</Accordion>

<div id="test-the-raw-data" />

<Accordion title="Uji data lengkap">

Jika paket langganan Anda mencakup akses ke data lengkap, Anda harus menguji data lengkap tersebut.

**Untuk menguji data lengkap** :

1. Setelah melakukan tes yang disebutkan sebelumnya,  buka **Reports** > **<Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">Export Data</Anchor>**.
2. Pilih sumber media yang diuji.
3. Tunggu hingga 15 menit sejak penginstalan, lalu unduh laporan Penginstalan.
4. Periksa catatan penginstalan dari mitra yang ada, dan sertakan parameter seperti sumber media, nama kampanye, waktu dan jenis touch, ID perangkat (jika ada), nama agensi (disebut "Mitra" di laporan), dll.

<div id="important-2" />

> 🚧 **Penting!**
>
> Beberapa jaringan iklan memerlukan tindakan khusus untuk mengaktifkan pengumpulan data lengkap level pengguna.
>
> Jika Anda melihat penginstalan baru di dashboard namun tidak melihatnya di data lengkap, baca panduan Help Center (Pusat Bantuan) spesifik untuk jaringan iklan, misalnya  <Anchor target="_blank" href="/marketers/id/docs/x-ads-formerly-twitter-ads-faq-and-discrepancies#do-you-make-twitters-raw-data-available-to-agencies">Twitter</Anchor>.

</Accordion>

<div data-zendesk-anchors="01H80XGTBQ6MAK3VG0X6QMAYMP=overview 01H80XGTBQPPZV7WR5JBHQFB0B=partner-types-in-the-ecosystem 01H80XGTBQ4CPMBRVSMM7TD4VD=partners-in-the-marketplace invite-new-partners-to-appsflyer=undang-mitra-baru-ke-appsflyer 01H80XGTBQRJ78XCGNZBTJVYEQ=undang-mitra-baru-ke-appsflyer 01H80XGTBQ8VF6V9WARZRECWVR=your-integrated-partners 01H80XGTBQJQYD3R46H95WVVM0=catatan 01H80XGTBQ5BE24X219BVZBMDG=about-the-integrated-partner-page applicable-settings-tabs-per-partner-type=tab-pengaturan-yang-berlaku-per-jenis-mitra 01H80XGTBQPP74G38YNNYVXWP2=tab-pengaturan-yang-berlaku-per-jenis-mitra set-up-a-partner-nonsrn=siapkan-mitra-non-srn 01H80XGTBQXNQ7SFXZ5PBQGS1V=siapkan-mitra-non-srn 01H80XGTBQZXZARZCM61CMG0K3=catatan-1 01H80XGTBQB9T22GQ7CSHS2S1X=integration-tab integration-tab-sections=bagian-integrasi 01H80XGTBQ0531M2RS3DH7E4Z0=bagian-integrasi 01H80XGTBQ4MPGGKSZW0D9GG9H=catatan-2 01H80XGTBRT41FGP5107G96TWC=attribution-link-tab attribution-link-parameters=parameter-link-atribusi 01H80XGTBRPENCTCRK8PPYSCGX=parameter-link-atribusi attribution-link-parameters::3874dfb8=parameter-link-atribusi-1 01H80XGTBR8630SEV80K9RD6V9=parameter-link-atribusi-1 retargeting-settings=pengaturan-retargeting 01H80XGTBRT57QMPRENYSS81Z3=pengaturan-retargeting clickthrough-attribution=atribusi-click-through 01H80XGTBREZTJ6B0Y08JCKN1E=atribusi-click-through viewthrough-attribution-lookback-window=lookback-window-atribusi-view-through 01H80XGTBRXC1YYX4FW94NDR2Z=lookback-window-atribusi-view-through 01H80XGTBRERTJ9XHGDV416T7V=cost-tab 01H80XGTBR54TQ0DNY1JR36GXN=catatan-3 enabling-cost-data-by-api=mengaktifkan-data-biaya-oleh-api 01H80XGTBRV6BHWS76HWHK933M=mengaktifkan-data-biaya-oleh-api cost-data-sync-status=status-sinkronisasi-data-biaya 01H80XGTBRPWREFYFXA0A6VD47=status-sinkronisasi-data-biaya 01H80XGTBRJ1AKX2Q7WPXFVA49=ad-revenue-tab enable-ad-revenue-attribution=mengaktifkan-atribusi-pendapatan-iklan 01H80XGTBRHE9PPRA9X46M4TGZ=mengaktifkan-atribusi-pendapatan-iklan ad-revenue-api-status-messages=pesan-status-api-pendapatan-iklan 01H80XGTBRNT4K4ZNPKVV25ESJ=pesan-status-api-pendapatan-iklan 01H80XGTBRGXS97JMG45QR4BEQ=permissions-tab ad-network-permissions=hak-akses-ad-network 01H80XGTBRS9BTT2F8F95BCE9Z=hak-akses-ad-network agency-permissions=hak-akses-agensi 01H80XGTBRTVP407AAA77N090E=hak-akses-agensi test-the-integration=uji-integrasinya 01H80XGTBSEWPHCPQF29XD6Y4W=uji-integrasinya 01H80XGTBSTHG2FC2M31F83RGK=catatan-4 01H80XGTBS4P06757QXHDKYAHT=test-the-attribution-link-for-nonsrns 01H80XGTBS2K9SPQ1MTAV7GP2H=test-the-srn-integration 01H80XGTBSTBV4RC3V279WNNB1=test-the-raw-data 01H80XGTBSN0VAX76XW9Y77T04=penting" />
