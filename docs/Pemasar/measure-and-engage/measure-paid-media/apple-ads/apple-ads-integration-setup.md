---
title: Pengaturan integrasi Apple Search Ads
metadata:
  keywords:
    - cost
    - Advertisers
    - apple search ads
    - asa
    - apple ads
    - apple search advanced
    - apple search ads campaign group
    - apple keywords
    - apple searchads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-08-31T09:04:38Z'
  edited_at: '2023-12-07T17:40:26Z'
  id: 213747963
  locale: id
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/id/articles/213747963
---
> **Sekilas**: Apple Search Ads (ASA), mitra AppsFlyer SRN, membantu pengguna untuk menemukan aplikasi Anda di App Store menggunakan kata kunci.

<Image alt="apple_search_ads.png" src="https://support.appsflyer.com/hc/article_attachments/17210504660625" width="217px" />

Relevansi aplikasi menentukan apakah iklan Anda ditampilkan sebagai tanggapan atas permintaan pencarian di App Store. Respons pengguna terhadap iklan adalah sinyal relevansi iklan. ASA menggunakan respons pengguna sebagai sinyal dalam memutuskan iklan mana untuk ditampilkan paling sering.

ASA menawarkan [atribusi seluler berbasis klik](/docs/apple-ads-integration-setup#asa-attribution), <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide">penargetan ulangpengguna</Anchor>, dan data <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview">biaya</Anchor> melalui API (dengan langganan ROI360).

<div id="set-up-apple-ads-integration" />

## Pengaturan integrasi ASA

<div id="get-started" />

<Accordion title="Memulai">

**Prasyarat**

* Versi terbaru dari AppsFlyer iOS SDK diadopsi

**Mengatur Apple Search Ads di AppsFlyer:**

Pengaturan dilakukan dari halaman **Integrasi aktif** , tetapi untuk menemukan mitra baru, Anda harus pergi ke <Anchor target="_blank" href="/marketers/id/docs/partner-integrations">Pasar Mitraterlebih</Anchor> dahulu. Selesaikan konfigurasi menggunakan tab yang relevan, seperti yang dijelaskan di bawah ini.

<div id="note-1" />

> 📘 **Catatan**
>
> Sebelum mengatur integrasi, pastikan Anda <Anchor target="_blank" href="/marketers/id/docs/partner-integrations#contact-details">menghubungi mitra</Anchor> dan membuka akun dengan mereka.

**Untuk mengaktifkan integrasi:**

1. Di AppsFlyer, di bawah **Konfigurasi** buka **Pasar Mitra**.
2. Cari mitra dan pilih. Anda diarahkan ke <Anchor target="_blank" href="/marketers/id/docs/partner-integrations#partner-details-and-performance">halaman detail mitra</Anchor>.
3. Klik **Siapkan integrasi**. Anda diarahkan ke halaman pengaturan integrasi.
4. Di tab **Integrasi**, aktifkan tombol **Aktifkan mitra**.  
   **Catatan:** Tombol harus tetap aktif <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">(diaktifkan)</Anchor> selama Anda bekerja dengan mitra.
5. Selesaikan konfigurasi menggunakan tab yang relevan, seperti yang dijelaskan di bawah ini.

Tab Integration

</Accordion>

Apple Search Ads, sebuah SRN, terintegrasi dengan AppsFlyer melalui API. Oleh karena itu, tidak ada pengaturan postback. Selesaikan bagian berikut sesuai dengan tujuan atribusi Anda.

<table><thead><tr><th>Bagian </th><th>Detail</th></tr></thead><tbody><tr><td>Aktivasi integrasi</td><td><p><strong>Untuk mengaktifkan integrasi untuk atribusi:</strong></p><ol><li>Di AppsFlyer, di bawah<span> </span><strong>Konfigurasi</strong><span> </span>buka<span> </span><strong>Pasar Mitra</strong>. </li><li>Cari mitra dan pilih. Anda diarahkan ke<span> </span><a href="./partner-integrations#partner-details-and-performance" target="_blank">halaman detail mitra</a>.</li><li>Klik<span> </span><span></span><strong>Siapkan integrasi</strong>. Anda diarahkan ke halaman pengaturan integrasi. </li><li>Di tab <strong>Integrasi</strong>, aktifkan tombol <strong>Aktifkan mitra</strong>.<br/><strong>Catatan:</strong> Tombol harus tetap aktif <a href="./partner-activation-deactivation" target="_blank">(diaktifkan)</a> selama Anda bekerja dengan mitra.</li><li>Selesaikan konfigurasi menggunakan tab yang relevan, seperti yang dijelaskan di bawah ini.</li></ol></td></tr><tr><td>Instal atribusi</td><td><p><a href="./set-up-lookback-windows" target="_blank"><strong>Menginstal jendela lookback klik-tayang</strong></a></p><p>Tetapkan waktu maksimum dari click-to-install. Melakukannya memungkinkan AppsFlyer untuk mengatribusikan penginstalan (peluncuran pertama) yang terjadi dalam lookback window (jendela lihat balik) ke ASA.</p><p>Rentang:1–30 hari.</p></td></tr><tr><td rowspan="2">Penginstalan ulang </td><td><p><strong>Instalasi ulang atribusi</strong></p><p>Jika <strong>Instal ulang atribusi</strong> aktif, AppsFlyer dapat mengatribusikan penginstalan ulang ke ASA.</p><p>Penginstalan ulang pengaturan jendela atribusi lookback diatur sesuai dengan pengaturan atribusi penginstalan.</p><p>Jika pengguna berada dalam <a href="./set-up-re-attribution-window" target="_blank">jendela atribusi ulang</a> (ditetapkan pada saat penginstalan asli), penginstalan diatribusikan ke ASA sebagai penginstalan ulang.</p><p>Penginstalan ulang dapat dilihat di tampilan penargetan ulang di dashboard Ikhtisar.</p><p>Bidang data lengkap<strong>Simpan penginstalan ulang</strong> disetel ke true. </p><p>Saat ini penargetan ulang ASA tidak mendukung interaksi ulang.</p></td></tr><tr><td><p><strong>Jendela ketidakaktifan</strong></p><p>Tetapkan <a href="./set-retargeting-inactivity-window" target="_blank">ambang ketidakaktifan</a> pengguna (dalam hari) untuk mengontrol dampak kampanye penargetan ulang. </p></td></tr></tbody></table>


<div id="cost-tab" />

<Accordion title="Tab Cost">

Integrasi biaya menyediakan data teragregasi berikut ini:

* Data biaya untuk kampanye, set iklan, lokasi/negara, dan kata kunci Anda. Lihat <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabel integrasi biaya jaringan iklan</Anchor> untuk detail lengkap tentang dimensi, metrik, dan fitur yang didukung.  
  **Catatan:** Data biaya memerlukan langganan ROI360.
* Data tentang klik, tayangan, dan data yang diperkaya—kata kunci, nama kampanye, dan set iklan.

<div id="note-2" />

> 📘 **Catatan**
>
> * Penggunaan beberapa akun ASA didukung. Dengan kata lain, jika Anda menjalankan kampanye untuk aplikasi yang sama menggunakan akun ASA yang berbeda, AppsFlyer dapat menerima data ini dari semua akun.
> * Data biaya untuk "grup kampanye" tidak didukung oleh API pelaporan ASA, sehingga data "grup kampanye" tidak tersedia di AppsFlyer.
> * Untuk masuk dengan Apple, Anda memerlukan izin tingkat admin ASA (baik Hanya Baca Akun atau Baca dan Tulis Akun).
> * Saat Anda login dengan Apple, semua sertifikat API yang diberikan sebelumnya berhenti menarik data.
> * Saat Anda masuk dengan Apple, otorisasi grup kampanye ASA tidak bersifat kumulatif. Artinya, saat Anda mengintegrasikan aplikasi baru, otorisasi untuk grup kampanye yang dipilih untuk aplikasi sebelumnya akan dicabut kecuali dipilih lagi.

**Untuk mengaktifkan biaya, klik, tayangan, dan data yang diperkaya:**

* Ikuti <Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">petunjuk integrasi ini</Anchor>

<Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Lihat status API biaya</Anchor> dan terakhir kali AppsFlyer berhasil menarik data biaya yang cocok di dashboard status integrasi biaya (dan pendapatan iklan), atau di dashboard jaringan iklan individual.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Tab Permissions">

<Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#permissions-tab">Mengatur jaringan iklan dan izin agensi.</Anchor>

</Accordion>

<div id="set-up-agencies-and-apple-ads-marketing-partners" />

## Atur agensi dan mitra pemasaran ASA

<div id="principles" />

<Accordion title="Prinsip">

**Apple Search Ads: Mitra Pemasaran Vs. Agensi**

Pengiklan dan agensi dapat memilih untuk bekerja dengan Mitra Pemasaran ASA untuk melaporkan dan mengoptimalkan kampanye di ASA.

Perbedaan antara biro iklan dan mitra pemasaran dicantumkan dalam tabel berikut.

<div id="agency-vs-marketing-partner" />

#### Agensi vs. mitra pemasaran

|  | Agensi | Mitra pemasaran |
| --- | --- | --- |
| AppsFlyer mengirim postback | Tidak | Ya |
| Teknologi | Jalankan kampanye atas nama Anda | Memiliki nilai tambah solusi teknologi untuk mengoptimalkan kampanye |

<div id="configuring-agencies-and-marketing-partners" />

#### Mengonfigurasi agensi dan mitra pemasaran

Gunakan daftar periksa berikut untuk memastikan bahwa Anda menyelesaikan semua langkah dalam proses konfigurasi. Disertakan instruksi terperinci per jenis mitra di bagian berikutnya.

<div id="configuration-steps-checklist" />

#### Daftar periksa langkah-langkah konfigurasi

| Dikonfigurasi oleh | Integrasi dengan agensi | Integrasi dengan mitra pemasaran |
| --- | --- | --- |
| Pemasang iklan | <ol><li>Di AppsFlyer, di tab integrasi ASA, aktifkan **Activate partner (Aktifkan mitra).**</li><li>Pilih agensi, di tab izin Agensi, aktifkan **Agency Permission (Izin Agensi).**</li></ol> | <ol><li>Di tab integrasi ASA, hidupkan **Aktifkan mitra.**</li><li>Di dashboard ASA, dapatkan **Campaign Group ID (ID Grup Kampanye.**</li><li>Di tab integrasi mitra pemasaran:<ol><li>Hidupkan **Activate partner** (Aktifkan mitra).</li><li>Tetapkan Grup Kampanye.</li><li>Konfigurasikan postback in-app event.</li></ol></li></ol> |
| Agensi | Di tab integrasi ASA, atur **Kampanye Grup Apple Search Ads (Iklan Penelusuran Apple).** | N/A |

</Accordion>

<div id="marketing-partner-setup" />

<Accordion title="Pengaturan mitra pemasaran">

**Untuk mengatur mitra pemasaran:**

1. Jika perlu, aktifkan **integrasi Apple Search Ads (Iklan Penelusuran Apple:)**
   1. Di AppsFlyer, buka, **Konfigurasi**> **Mitra integrasi aktif** > **Apple Search Ads**.
   2. Nyalakan **Aktifkan Mitra**.
   3. Klik ***Save***.
2. **Di dashboard Apple Search Ads**: Dapatkan parameter ID Grup Kampanye Apple Search Ads terkait mitra pemasaran. Gunakan tangkapan layar (screenshot) berikut sebagai panduan untuk mendapatkan ID.

   ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)
3. **Di AppsFlyer, konfigurasikan mitra pemasaran ASA:**
   1. Di AppsFlyer, buka **Konfigurasi** > **Integrasi aktif.**
   2. Cari mitra pemasaran **Apple Search Ads .**  
      Daftar mitra pemasaran ditampilkan.
   3. Pilih mitra pemasaran.
   4. Hidupkan **Activate partner** (Aktifkan mitra).
   5. Masukkan **Grup Kampanye Apple Search Ads (Iklan Penelusuran Apple)** milik mitra yang Anda ambil di langkah sebelumnya.  Hanya masukkan digit (angka).
   6. Klik ***Save***.
4. [Opsional] Konfigurasi postback in-app event:

   1. Aktifkan **postback In-app event.**
   2. Klik **Add event** (Tambah event) untuk menambahkan Event SDK ke daftar.
   3. Isi parameter berikut:

      1. **Nama event SDK**: Nama event yang diterima oleh AppsFlyer baik dari SDK yang terintegrasi di aplikasi Anda, atau event server to server. **Tipa** - Jika Anda tidak melihat event yang Anda inginkan dalam daftar, pastikan untuk mengaktifkan event di perangkat dengan penginstalan non-organik dan periksa ulang.
      2. **Kirim pendapatan:** Pilih salah satu dari yang berikut: Tanpa nilai dan tanpa pendapatan, Nilai & tanpa pendapatan atau Nilai dan pendapatan.
5. Klik **Save Integration** (Simpan Integrasi).

</Accordion>

<div id="agency-setup" />

<Accordion title="Pengaturan agensi">

Pemasang iklan mengizinkan agensi untuk menjalankan kampanye atas nama mereka menggunakan Apple Search Ads (Iklan Penelusuran Apple). Baik pengiklan dan agensi melakukan tindakan pengaturan di AppsFlyer seperti yang dijelaskan di bagian ini.

**Grup kampanye Apple Search Ads (Iklan Penelusuran Apple)**

* Kampanye agensi dan kampanye pemasang iklan harus terpisah dari grup kampanye ID Apple Search Ads.
* Jangan gunakan karakter dan spasi khusus untuk nama grup.
* Saat Anda masuk dengan Apple, otorisasi grup kampanye ASA tidak bersifat kumulatif. Artinya, saat Anda mengintegrasikan aplikasi baru, otorisasi untuk grup kampanye yang dipilih untuk aplikasi sebelumnya akan dicabut kecuali dipilih lagi. Anda harus memilih **Akses Terbatas** dan masing-masing grup kampanye yang relevan (terkait dengan aplikasi yang ingin Anda hubungkan untuk pemasang iklan).

<div id="advertiser-actions" />

#### **Tindakan pengiklan**

**Prasyarat**:

<Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#hak-akses-agensi">Berikan izin kepada agensi</Anchor>.

**Untuk mengaktifkan atribusi untuk Apple Search Ads (Iklan Penelusuran Apple), pemasang iklan:**

1. Di AppsFlyer, buka **Konfigurasi** > **Integrasi aktif.**
2. Pilih **Apple Search Ads (Iklan Penelusuran Apple).**
3. Buka tab **Integration (Integrasi)**, hidupkan **Activate partner (aktifkan mitra\_** .
4. [Opsional] Jika Anda ingin mengatribusikan pengguna yang menginstal ulang aplikasi selama jendela atribusi ulang, aktifkan **Penginstalan ulang atribusi.**
5. Klik ***Save***.

<div id="note-3" />

<div id="agency-actions" />

#### **Tindakan agensi**

1. **Di dashboard Apple Search Ads**: Dapatkan ID Grup Kampanye Anda. Gunakan tangkapan layar (screenshot) berikut sebagai panduan untuk mendapatkan ID. Dapatkan digit (hanya angka).

   ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)
2. Di AppsFlyer, pilih sebuah Aplikasi.
3. Buka **Konfigurasi** > **Integrasi aktif**.
4. Pilih **Apple Search Ads (Iklan Penelusuran Apple).**
5. Masukkan parameter **ID Grup Kampanye Apple Search Ads (Iklan Penelusuran Apple)**. Catatan! Masukkan digit (hanya angka)
6. Klik **Simpan**.

> 📘 **Catatan**
>
> Saat agensi bekerja dengan Apple Search Ads Marketing Partner (Mitra Pemasaran Iklan Penelusuran Apple), agensi harus mengonfigurasi ID grup kampanye yang sama di laman konfigurasi Apple Search Ads dan laman konfigurasi Marketing Partner (Mitra Pemasaran).

<div id="note-4" />

<div id="cost-clicks-and-impressions-data" />

### Data Biaya, Klik, dan Impresi

Jika Anda mengaktifkan API biaya, AppsFlyer menerima data biaya, klik, dan tayangan data dari ASA melalui API. Lihat  <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabel integrasi biaya jaringan iklan</Anchor>  untuk detail lengkap tentang dimensi, metrik, dan fitur yang didukung. Catatan: Data biaya memerlukan langganan ROI360. Tanpa Xpend, hanya data klik dan tayangan yang diterima.

**Untuk mengaktifkan API Biaya**:

* Ikuti <Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">petunjuk integrasi ini</Anchor>. Pastikan saat diminta untuk masuk ke akun Apple Search Ads Anda di **Pilih izin**, pilih salah satu dari berikut ini:
  * **Baca dan Tulis Akun**
  * **Akun Hanya Baca**  
    **Catatan**: Jika Anda memilih Akses Terbatas dan grup kampanye tertentu, Anda mungkin mengalami kesalahan data.

<Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Lihat status API biaya</Anchor> dan terakhir kali AppsFlyer berhasil menarik data biaya yang cocok di dashboard status integrasi biaya (dan pendapatan iklan), atau di dashboard jaringan iklan individual.

</Accordion>

<div id="disable-agencies-and-marketing-partners" />

<Accordion title="Menonaktifkan agensi dan mitra pemasaran">

**Untuk berhenti mencatat atribusi penginstalan Apple Search Ads yang dihasilkan oleh agensi atau mitra pemasaran:**

1. Di AppsFlyer, buka **Konfigurasi** > **Integrasi aktif.**
2. Pilih agensi atau mitra pemasaran sesuai kasusnya.
3. Hapus konten bidang **ID Grup Kampanye Apple Search Ads.**
4. Klik **Save Integration (Simpan Integrasi)** .

</Accordion>

<div id="before-september-1-2026" />

<div id="after-september-1-2026" />

<div id="additional-information" />

## Informasi Tambahan

<div id="asa-attribution" />

<Accordion title="Atribusi ASA">

Apple Search Ads berfungsi secara independen dari SKAdNetwork dan secara deterministik mengatribusikan pengguna, terlepas dari persetujuan ATT. Ini berarti bahwa untuk pengguna yang diatribusikan ke ASA, Anda memiliki rangkaian lengkap fitur dan pengukuran yang disediakan oleh <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model">model atribusi LTV kami.</Anchor>

Atribusi ASA tidak bergantung pada IDFA—atribusi dilakukan menggunakan token dari perangkat (atribusi deterministik)—dan berbeda menurut persetujuan ATT:

| **Persetujuan ATT** | **Waktu klik tersedia** | **Klik jendela lookback** | **Catatan** |
| --- | --- | --- | --- |
| Ya | Ya | Yang ditetapkan oleh pemasang iklan | Digunakan aturan atribusi klik terakhir AppsFlyer |
| Tidak | Tidak | 30 hari  <br />(diatur oleh ASA) | Tidak ada waktu klik yang disediakan. Prioritas diberikan kepada kandidat deterministik. |

</Accordion>

<div id="discrepancies" />

<Accordion title="Perbedaan">

AppsFlyer dan Apple Search Ads menggunakan logika atribusi berbeda yang menyebabkan perbedaan di antara platform. <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns#atribusi">Apple Search Ads</Anchor>, sebuah SRN, melaporkan penginstalan baru oleh API.

**Pelaporan Apple Search Ads (Iklan Penelusuran Apple) ke AppsFlyer oleh API**

* Kampanye dikumpulkan oleh Geo.
* Hal berikut tidak dilaporkan: Tayangan, ketukan, atau biaya geografis yang memiliki kurang dari 100 tayangan untuk kampanye tertentu.
* Saat dikelompokkan berdasarkan Geo di AppsFlyer, Geo dengan data yang tidak tersedia tidak ditampilkan, dan total data yang tidak tersedia muncul di bawah N/A.

<div id="retargeting-related-discrepancies" />

### Perbedaan terkait penargetan ulang

Mekanisme atribusi penargetan ulang AppsFlyer memungkinkan pemasang iklan untuk mengukur dan menganalisis kampanye penargetan ulang, selain kampanye akuisisi pengguna.

Gambar berikut menggambarkan bagaimana perbedaan dapat terjadi dalam kaitannya dengan kampanye penargetan ulang (terlepas dari setelan kontrol penargetan ulang) yang dijalankan di Apple Search Ads.

**Penargetan ulang aktif**

[![ASA_R_Enabled.png](https://files.readme.io/ced87f066490d95631f352ef7905c5c812ac7736c9763d08792eedb383afb8c7-360002911777.png)](https://files.readme.io/ced87f066490d95631f352ef7905c5c812ac7736c9763d08792eedb383afb8c7-360002911777.png)

**Penargetan ulang dinonaktifkan**

[![ASA_R_Disabled.png](https://files.readme.io/425a0e1e802482a00230d7ceaebdcaa7f74523fb6feb75d60168f94b56886201-31197514618001.png)](https://files.readme.io/425a0e1e802482a00230d7ceaebdcaa7f74523fb6feb75d60168f94b56886201-31197514618001.png)

<div id="20260901" />

<div id="h_01M0YZYCC5S0E3HA296KAA0SDZ" />

<div id="missing-conversion-payload-for-gender-and-age-targeted-users" />

<div id="preregistration-click-and-impression-lookback-window-discrepancy" />

<div id="impression-lookback-window" />

<div id="see-also" />

<div id="before-september-1-2026-1" />

<div id="after-september-1-2026-1" />

<div id="additional-reasons-for-discrepancies" />

### Alasan tambahan untuk perbedaan

Tabel berikut mencantumkan alasan utama perbedaan.

| Perbedaan | Apple Search Ads | AppsFlyer |
| --- | --- | --- |
| <span id="differences-related-to-appsflyer-sdk-versions"></span>Perbedaan terkait versi SDK AppsFlyer | Menghitung konversi, apa pun versi SDK AppsFlyer-nya. | Untuk AdsServices, SDK V6.1.3+ diperlukan untuk mengatribusikan dengan benar. |
| <span id="limit-ad-tracking-lat-and-att"></span>Batasi pelacakan iklan (LAT) dan ATT. | Selalu hitung konversi.<br /><br />Jika kampanye Anda dibatasi oleh usia dan jenis kelamin, pengguna LAT dikecualikan dari kampanye.<br /><br />Pengguna Apple berusia di bawah 18 tahun selalu merupakan pengguna LAT. | Konversi LAT diatribusikan ke organik.<br /><br />Jika AdServices diterapkan dan iOS14.3+ diinstal, maka pengguna yang tidak memberi persetujuan diatribusikan dengan benar. |
| <span id="counting-users"></span>Menghitung pengguna | Hitung pengguna berdasarkan unduhan | Hitung pengguna berdasarkan pembukaan aplikasi pertama |
| <span id="reinstall-a-user-after-installing-the-app-deletes-it-clicks-on-a-search-ad-then-installs-the-app-again"></span>Penginstalan ulang: Pengguna setelah menginstal aplikasi, menghapusnya, mengklik Iklan Penelusuran, lalu menginstal aplikasi lagi | Hitung sebagai konversi (penginstalan) | <ul><li>Dengan IDFA: AppsFlyer mengidentifikasi penginstalan ulang dan tidak memperhitungkannya untuk tujuan UA. Tips! Aktivasi penargetan ulang dan penginstalan ulang dicatat sebagai penginstalan penargetan ulang (atau atribusi ulang)</li><li>Tanpa IDFA: AppsFlyer dapat mengandalkan IDFV untuk menentukan apakah ini penginstalan ulang atau penginstalan baru:<ol><li>Jika satu atau lebih aplikasi vendor diinstal di perangkat, AppsFlyer mengatribusikan ASA sebagai atribusi ulang.</li><li>Jika tidak (tidak ada aplikasi lainnya), AppsFlyer mengatribusikan ASA sebagai penginstalan baru.</li></ol></li></ul> |
| <span id="click-lookback-window"></span>Klik jendela lookback | Memperbaiki jendela 30 hari | Untuk tanggapan dari AdServices yang tidak memiliki waktu klik, jendela lihat balik klik ditetapkan menjadi jendela 30 hari. |
| <span id="winning-click"></span>Klik menang | Selalu mengaitkan dirinya sendiri jika pengguna terlibat dan mengunduh aplikasi. | Memiliki visibilitas di beberapa jaringan, dan mengatribusi sesuai dengan metodologi klik terakhir |
| <span id="install-time"></span>Install time | Waktu pengunduhan aplikasi | Aplikasi pertama dibuka |
| <span id="time-zone"></span>Zona waktu | Zona waktu lokal app store | Zona waktu UTC atau seperti yang diatur dalam pengaturan AppsFlyer |
| <span id="conversion-data"></span>Data konversi | Diperlukan lebih dari 5 detik untuk memperbarui AppsFlyer terkait penginstalan yang dibawa Search Ads | Mengatribusi dalam 5 detik saat API data Konversi merespons. Jika tidak ada data yang diterima maka responsnya organik. |
| <span id="cost-data"></span>Data biaya | Laporkan biaya untuk semua kata kunci | Tidak melaporkan data biaya untuk kata kunci yang berisi huruf besar di dashboard kohort atau API kohort. |
| <span id="geo-locations"></span>Lokasi geografis | Apple Search Ads memungkinkan pengiklan untuk menargetkan pengguna sesuai dengan negara dan wilayah  mereka. Iklan Pencarian Apple mendukung sejumlah [**negara**](https://searchads.Apple.com/storefronts/) . | AppsFlyer mengenali lokasi geografis yang tepat dari pengguna berdasarkan alamat IP, sehingga laporan tentang geo tidak tersedia di Apple Search Ads.<br /><br />Pengguna yang menginstal saat berada di negara sebenarnya dari app store memiliki data geo yang sama di AppsFlyer dan Apple Search Ads |

</Accordion>

<div id="tips" />

<Accordion title="Tips">

Bekerja dengan Apple Search Ads (Iklan Penelusuran Apple) memungkinkan Anda mengumpulkan data pemasaran yang berharga, yang dapat memengaruhi upaya akuisisi pengguna Anda dengan semua sumber media untuk aplikasi iOS Anda.

Kiat untuk membantu Anda memaksimalkan manfaat menggunakan Apple Search Ads (Iklan Penelusuran Apple)

| Tips | Detail |
| --- | --- |
| <span id="get-keyword-data"></span>Dapatkan data kata kunci | Apple Search Ads (Iklan Penelusuran Apple) membagikan data kata kunci dengan AppsFlyer. Anda dapat melihat data kata kunci dalam data lengkap dan alat analitik seperti Pivot, Retensi, dan Kohort.<br /><br />**Catatan:**<ul><li>Mendapatkan data kata kunci mungkin tertunda selama 8-12 jam, dan dalam beberapa kasus, mungkin hanya menyertakan ID kata kunci tanpa istilah kata kunci</li><li>Untuk mendapatkan data kata kunci, sakelar Biaya harus diaktifkan. Data kata kunci diberikan sebagai bagian dari [integrasi Biaya](/docs/apple-ads-integration-setup#cost-tab), tanpa perlu berlangganan ROI360.</li></ul>Jika data kata kunci tidak ada di AppsFlyer, ini dapat disebabkan oleh:<ul><li>**Jenis paket:** Data kata kunci dibagikan oleh Apple search Ads (Iklan Penelusuran Apple) dengan pengiklan, yang memiliki  paket Apple Search Ads [lanjutan](https://searchads.Apple.com/advanced/)</li><li>**Jenis kampanye:** Anda dapat mengonfigurasi berbagai jenis pencocokan kata kunci kampanye di Apple Search Ads (Iklan Penelusuran Apple). Berdasarkan jenis pencocokan, Apple Search Ads (Iklan Penelusuran Apple) membagikan kata kunci sebagai berikut:<ul><li>**Exact match**: Kata kunci yang tepat dicari oleh pengguna</li><li>**Broad match** : Kata kunci yang digunakan Apple untuk melakukan pencarian. Ini mirip dengan istilah penelusuran aktual pengguna.</li><li>**Search match**:Apple  **tidak**  membagikan kata kunci ini dengan pengiklan.</li></ul></li><li>**Peka huruf besar-kecil**: API pemasaran Apple Search Ads menampilkan data peka huruf besar-kecil dan API atribusi Apple Search Ads menampilkan data huruf kecil. Untuk menghindari konflik data dalam laporan, gunakan hanya kata kunci dengan huruf kecil.</li></ul>**Gunakan hanya kampanye penelusuran pencocokan yang tepat atau luas** untuk menerima data kata kunci yang lengkap. |
| <span id="compare-the-quality-of-users-based-on-keyword-data"></span>Bandingkan kualitas pengguna berdasarkan data kata kunci | Tidak semua kata kunci memiliki arti yang sama, sementara kata kunci yang berbeda mungkin harganya sama, kualitas yang ditarik pengguna bisa berbeda. Gunakan laporan Retensi  atau  <Anchor target="_blank" href="/marketers/id/docs/pivot-table-user-metrics">Pivot</Anchor>  untuk mengidentifikasi kata kunci yang memaksimalkan ROI Anda. |
| <span id="analyze-keyword-cost"></span>Analisis biaya kata kunci | Platform ini berisi data biaya kata kunci agregat ketika kampanye kata kunci ASA dikonfigurasikan sebagai [exact match (pencocokan tepat) atau broad match (pencocokan luas)](/docs/apple-ads-integration-setup#get-keyword-data). Data biaya kata kunci memiliki karakteristik berikut:<ul><li>Data historis tersedia mulai 13 Oktober 2019.</li><li>Dimensi:<ul><li>Tanggal</li><li>Kampanye</li><li>adset</li></ul></li><li>Alat analisis:<ul><li><Anchor target="_blank" href="/marketers/id/docs/cohort-and-retention-dashboard">Kohort</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/pivot-table-user-metrics">Pivot</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor></li></ul></li></ul>**Batasan**<ul><li>Hanya gunakan dimensi yang dicatat untuk memfilter dan mengelompokkan kueri data biaya. Misalnya, jangan memfilter atau mengelompokkan menggunakan Geo.</li></ul>**<span id="cohort-example"></span>Contoh Kohort**<br />Contoh berikut menampilkan cara mengatur Kohort untuk melihat informasi biaya dan ROI.<br /><br />**Pengaturan kohort**<br /><br />[<Image alt="CohortRequest.png" src="https://files.readme.io/73004ab25cfff029786ec4601e22a0ac4b02a146141787b51bda1a02d5412330-31197524095377.png" width="327px" />](https://files.readme.io/73004ab25cfff029786ec4601e22a0ac4b02a146141787b51bda1a02d5412330-31197524095377.png)<br /><br />**Tabel hasil kohort**<br /><br />Dalam tabel berikut, total biaya dan ROI Kohort ditampilkan<br /><br />[<Image alt="CohortTable.png" src="https://files.readme.io/ebceedb82207bdbc7f58daafc0557630ac35a73a11b14d207a7283b93294073d-31197514633233.png" width="429px" />](https://files.readme.io/ebceedb82207bdbc7f58daafc0557630ac35a73a11b14d207a7283b93294073d-31197514633233.png)<br /><br />**<span id="pivot-example"></span>Contoh pivot**<br /><br />**Pengaturan pivot**<br /><br />[<Image alt="Pivot_define.png" src="https://files.readme.io/29ad177a5ef681f8358968092005d8ba871f3dd06661a8dea6d186318c08a476-31197524107153.png" width="413px" />](https://files.readme.io/29ad177a5ef681f8358968092005d8ba871f3dd06661a8dea6d186318c08a476-31197524107153.png)<br /><br />**Tabel hasil pivot**<br /><br />[<Image alt="Pivot.png" src="https://files.readme.io/ef9766de2059d0608e8ae6dc063053f2926ffa296e7eca2e13a1bc4171921d2c-31197524111505.png" width="439px" />](https://files.readme.io/ef9766de2059d0608e8ae6dc063053f2926ffa296e7eca2e13a1bc4171921d2c-31197524111505.png) |
| <span id="find-the-best-performing-creative-set"></span>Temukan kumpulan kreatif berkinerja terbaik | ![creative_sets.png](https://files.readme.io/ef8e38d67121283742dcbd1faef11d94a8ea1c612dc258611e72cbf826d7ef8f-31197524112785.png)<br /><br />Praktik yang baik untuk menguji bagaimana prospek merespons berbagai perangkat kreatif yang Anda gunakan. Kumpulan materi iklan berkinerja terbaik memiliki tingkat konversi tertinggi. Selain itu, kumpulan materi iklan terbaik mengubah pengguna dengan tingkat keterlibatan yang lebih baru.<br /><br />Hal ini memengaruhi semua prospek iOS Anda, bukan hanya prospek ASA, karena semuanya menjangkau halaman aplikasi Anda di app store. Namun, dengan instalasi ASA, AppsFlyer menunjukkan ID kumpulan kreatif di <Anchor target="_blank" href="/marketers/id/docs/raw-data-field-dictionary">raw data</Anchor> (data lengkap) parameter**ID Ad**, mengizinkan Anda untuk membandingkan kinerja kumpulan kreatif yang berbeda. |
| <span id="target-redownloaders"></span>Target pengunduh ulang | Pengguna lama Anda mungkin adalah audiens terbaik untuk Anda targetkan menggunakan ASA.<br /><br />Seorang pengguna, yang meng-uninstall aplikasi Anda, dan sebagai hasil dari kampanye penargetan ulang ASA Anda menginstal lagi, disebut Re-Downloader (Pengunduh Ulang) oleh ASA. Jika penginstalan ulang dilakukan selama <Anchor target="_blank" href="/marketers/id/docs/set-up-re-attribution-window">jendela atribusi ulang</Anchor>, AppsFlyer menyebut ini Re-Attribution (Atribusi Ulang). Dalam semua kasus lain, ini diperlakukan sebagai penginstalan baru.<br /><br />![ASACGroupID.png](https://files.readme.io/ebdc380f2abc3e9a3b134cd258d90ae32f75b3ee4d9eadde39adbc728daae523-31197514645265.png) |

</Accordion>

<div id="asa-change-log" />

<Accordion title="Log perubahan ASA">

| Tanggal Efektif | Pembaruan/perubahan |
| --- | --- |
| <span id="20230207"></span>07-02-2023 | Parameter atribusi yang diperkaya `Nama kampanye`, `Nama Adset`, dan `Kata Kunci` hanya tersedia bila tab Biaya diaktifkan, terlepas dari paket langganan Anda.  <br />**Artinya, agar dashboard dan laporan data lengkap Anda menampilkan nama kampanye, nama adset, atau kata kunci, Anda harus mengaktifkan tab Biaya.** |
| <span id="20220216"></span>16-02-2022 | Kata kunci tersedia melalui API Biaya. Anda harus mengaktifkan API Biaya di halaman integrasi Apple Search Ads. Perhatikan! API tersebut tersedia untuk semua pemasang iklan, apa pun paket langganan Anda. |
| <span id="20210407"></span>2021-04-07 | Integrasi Apple Search Ads: ASA berfungsi secara independen dari SKAdNetwork dan secara deterministik mengatribusikan pengguna. Ini berarti bahwa agar pengguna diatribusikan ke ASA, Anda memiliki berbagai fitur dan pengukuran yang disediakan oleh <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model">model atribusi LTV kami.</Anchor> |
| <span id="20210307"></span>2021-03-07 | Apple Search Ads meluncurkan API Manajemen Kampanye V4.0. API terkait biaya dan data terkait kampanye lainnya. Hal ini tidak berdampak pada atribusi. Kami sedang dalam proses mengadopsi API yang diperbarui. Anda tidak perlu melakukan tindakan apa pun. |
| <span id="20210215"></span>2021-02-15 | Mulai tanggal ini, bidang nama kampanye dan nama adset dapat diisi jika Anda mengaktifkan [API Biaya](/docs/apple-ads-integration-setup#cost-tab) ASA. API tersebut tersedia untuk semua pemasang iklan, apa pun paket langganannya. |

</Accordion>

<div id="availability-of-apple-search-ads-campaign-parameters" />

<Accordion title="Ketersediaan parameter kampanye Apple Search Ads">

Tabel di bawah menunjukkan ketersediaan parameter atribusi di laporan data lengkap atau di dashboard.

| Parameter laporan data lengkap | Ketersediaan |
| --- | --- |
| Nama kampanye | Agar parameter ini tersedia, Anda harus mengaktifkan [API](/docs/apple-ads-integration-setup#cost-tab) Biaya di halaman integrasi Apple Search Ads. API tersebut tersedia untuk semua pemasang iklan, apa pun paket langganan Anda |
| ID kampanye | Selalu tersedia |
| Nama Adset | Agar parameter ini tersedia, Anda harus mengaktifkan [API](/docs/apple-ads-integration-setup#cost-tab) Biaya di halaman integrasi Apple Search Ads. API tersebut tersedia untuk semua pemasang iklan, apa pun paket langganan Anda |
| ID adset | Selalu tersedia |
| ad | Sedang tidak tersedia |
| ID iklan | Parameter ini hanya tersedia bila kedua kondisi berikut terpenuhi:<ul><li>Pengguna menggunakan iOS 15.2 dan yang lebih baru</li><li>Iklan tersebut menggunakan <Anchor target="_blank" href="https://developer.apple.com/app-store/product-page/">Halaman Produk Khusus</Anchor> untuk kampanye yang dikaitkan dengan salah satu penempatan iklan berikut:<ul><li>`Tab hari ini`</li><li>`Hasil pencarian`</li></ul></li></ul> |
| Keywords | Agar parameter ini tersedia, Anda harus mengaktifkan [API Biaya](/docs/apple-ads-integration-setup#cost-tab)   di halaman integrasi Apple Search Ads. API tersebut tersedia untuk semua pemasang iklan, apa pun paket langganan Anda |
| ID kata kunci | Parameter ini tersedia melalui laporan data lengkap. Namun, ini harus dipilih secara eksplisit di Data Locker, Push API, dan data Ekspor. Dalam kasus Pull API, tambahkan `keyword_id` ke parameter  `&additional_fields` <Anchor target="_blank" href="/marketers/id/docs/pull-api-raw-data#additional-fields">dari panggilan Pull API</Anchor>. |
| Jenis Pencocokan Kata Kunci | Sedang tidak tersedia |

</Accordion>

<div id="impact-of-aggregated-advanced-privacy" />

<Accordion title="Dampak Privasi Tingkat Lanjut Gabungan">

Mulai iOS 14 [ATTrackingManager](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/) (ATT) mengatur ketersediaan IDFA dan data atribusi tingkat pengguna dari penginstalan yang dibawa oleh ASA dikontrol oleh ASA. Dengan demikian, ketersediaan data tingkat pengguna dari penginstalan yang dibawa oleh ASA tidak dipengaruhi oleh <Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework">Privasi Tingkat Lanjut Gabungan</Anchor>.

Perhatikan! Penginstalan yang dibawa oleh ASA tidak dilaporkan di framework SKAdNetwork.

| **Persetujuan ATT** | **Waktu klik tersedia** | **Klik jendela lookback** | **Catatan** | **Ketersediaan data** | **IDFA tersedia** |
| --- | --- | --- | --- | --- | --- |
| Menyetujui | Ya | Yang ditetapkan oleh pemasang iklan | Digunakan aturan atribusi klik terakhir AppsFlyer | Data atribusi tingkat pengguna | Ya |
| Tanpa persetujuan | Tidak | 30 hari  <br />(diatur oleh ASA) | Prioritas diberikan kepada kandidat deterministik. | Data atribusi tingkat pengguna tanpa waktu klik. | Tidak |

</Accordion>

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework">Kerangka Privasi Lanjutan Gabungan</Anchor>
> * <Anchor target="_blank" href="/marketers/id/docs/set-up-lookback-windows">Jendela lookback dijelaskan</Anchor>

<div data-zendesk-anchors="set-up-asa-integration=pengaturan-integrasi-asa h_01HDPCGMP2CY4B37VM3AT2P114=pengaturan-integrasi-asa h_01HDPCGMP35S325269JETX1EJW=get-started h_01HDPCGMP383Y223E1YXF60C8S=catatan h_01HDPCGMP3JC93JWHM2SM8EVZA=cost-tab h_01HDPCGMP3XGYXVZZJ8SGDK3G2=catatan-1 h_01HDPCGMP3KXMKSHN0GFD6MAFG=permissions-tab set-up-agencies-and-asa-marketing-partners=atur-agensi-dan-mitra-pemasaran-asa h_01HDPCGMP3D96BG496G7H97YWP=atur-agensi-dan-mitra-pemasaran-asa h_01HDPCGMP3EBHM0CQXKP05SG9F=principles agency-vs-marketing-partner=agensi-vs-mitra-pemasaran h_01HDPCGMP3YGJEA942DF2YC9P1=agensi-vs-mitra-pemasaran configuring-agencies-and-marketing-partners=mengonfigurasi-agensi-dan-mitra-pemasaran h_01HDPCGMP3NQQ76SC32SEC8TS4=mengonfigurasi-agensi-dan-mitra-pemasaran configuration-steps-checklist=daftar-periksa-langkah-langkah-konfigurasi h_01HDPCGMP39HE117X4MP25M77W=daftar-periksa-langkah-langkah-konfigurasi h_01HDPCGMP3BT4YJWJ2G8X76NSE=marketing-partner-setup h_01HDPCGMP3X6B4RYF289WY49P7=agency-setup advertiser-actions=tindakan-pengiklan h_01HDPCGMP3S3PHHH3F6KZE3SEV=tindakan-pengiklan agency-actions=tindakan-agensi h_01HDPCGMP3MK61YRMCQA2KA5X2=tindakan-agensi h_01HDPCGMP3E7PZB8FDG4XN79JA=catatan-2 cost-clicks-and-impressions-data=data-biaya-klik-dan-impresi h_01HDPCGMP3AVYYK2X03RF057FN=data-biaya-klik-dan-impresi h_01HDPCGMP3113BYD1GPJM7XBQH=disable-agencies-and-marketing-partners additional-information=informasi-tambahan h_01HDPCGMP3BXVASH2YJ9G8AS2C=informasi-tambahan h_01HDPCGMP31QFVN1SWBCABJ65K=asa-attribution h_01HDPCGMP4DCKH898AEWAY6N01=discrepancies retargeting-related-discrepancies=perbedaan-terkait-penargetan-ulang h_01HDPCGMP4Z9M3QR6QGRR7A8BM=perbedaan-terkait-penargetan-ulang additional-reasons-for-discrepancies=alasan-tambahan-untuk-perbedaan h_01HDPCGMP4QJ3HYEP7EAYMHRQQ=alasan-tambahan-untuk-perbedaan h_01HDPCGMP4A8NAD8SYD191YJYR=tips h_01HDPCGMP4HNS84AVWH7J8H7YA=alasan-tambahan-untuk-perbedaan h_01HDPCGMP4MF9FBP4WDRHVZ4BR=cohort-example h_01HDPCGMP4EFMZ4FHZ8WBWW9R2=pivot-example h_01HDPCGMP4XKB75F6R7DDWDHPB=asa-change-log h_01HDPCGMP40MW37BFT8A096PNG=availability-of-apple-search-ads-campaign-parameters h_01HDPCGMP48M04SDA4FGYW6XNQ=impact-of-aggregated-advanced-privacy h_01HDPD3C1T4ZXXZ2RE0GSXPZP3=lihat-juga" />
