---
title: Push API streaming data lengkap
metadata:
  keywords:
    - Push API
    - Real-time
    - Installation and Conversion
    - Advertisers
    - Developers
    - Premium
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Raw Reports
  created_at: '2013-04-24T15:19:42Z'
  edited_at: '2023-11-20T08:40:18Z'
  id: 207034356
  locale: id
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/id/articles/207034356
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Sekilas:** Streaming event atribusi data lengkap ke titik akhir sisi server Anda.

![6970_Push_API_image.png](https://files.readme.io/0bb5747a65a6ca6ed8f55f72f189b92e780649d55b766c5d295f5602745f04f5-4405028260241.png)

## Push API

Push API mengalirkan data lengkap yang dihasilkan oleh atribusi AppsFlyer dan atribusi SKAdNetwork (SKAN) sebagai pesan ke server Anda. Anda dapat memilih jenis dan isi pesan serta mengatur titik akhir tujuan.

Jenis pesan yang tersedia, keaktualan data, dan bidang bergantung pada kerangka atribusi (AppsFlyer atau SKAN) seperti yang dijelaskan di bagian berikut.

<div id="appsflyer-attribution-messages" />

<Accordion title="Pesan atribusi AppsFlyer">

Karakteristik pesan

| Karakteristik | Detail |
| --- | --- |
| Pembagian jenis pesan | <ul><li>Pesan dapat dibagi berdasarkan titik akhir (maksimum 6 titik akhir per aplikasi) atau Anda dapat menentukan jenis pesan dengan memeriksa nilai bidang yang tercantum:<ul><li>event\_name</li><li>conversion\_type</li><li>campaign\_type</li></ul></li><li>Nilai bidang, per jenis pesan, ditunjukkan pada tabel berikut.</li></ul>**Contoh:**<br /><br />Pesan berisi hal berikut:<ul><li>conversion\_type=install</li><li>campaign\_type=organic</li><li>event\_name=install</li></ul>Gunakan tabel untuk menentukan bahwa event ini adalah event penginstalan dari pengguna organik. |
| Kesegaran data | Pesan dikirim segera setelah event dicatat di platform AppsFlyer. Biasanya dalam beberapa menit. |
| Isi pesan (bidang) | <ul><li>Pesan memiliki struktur `key:value`.</li><li>Lihat bidang atribusi AppsFlyer <Anchor target="_blank" href="/marketers/id/docs/raw-data-field-dictionary#field-availability-by-reporting-tool">Push API</Anchor> yang tersedia.</li><li>Setiap kode (key) mewakili bidang data lengkap. Lihat <Anchor target="_blank" href="/marketers/id/docs/raw-data-field-dictionary#data-fields-dictionary">deskripsi bidang data lengkap di AppsFlyer</Anchor>.</li><li>Kode kosong atau null tidak dikirim sama sekali.</li><li>Contoh berisi bidang null dan kosong. Postback real tidak memiliki bidang kosong atau null. Contoh yang diberikan memiliki format JSON.<ul><li>[iOS](https://docs.google.com/spreadsheets/d/e/2PACX-1vRMoTZpgttICSjjjXTh4JU5m9p3ky7Ej_MYc0kZ3vYs7sNq6u_wNvWBgjFLF_VjdRbY54aE5e-4keLY/pub?gid=0&single=true&output=csv)</li><li>[Android](https://docs.google.com/spreadsheets/d/e/2PACX-1vRMoTZpgttICSjjjXTh4JU5m9p3ky7Ej_MYc0kZ3vYs7sNq6u_wNvWBgjFLF_VjdRbY54aE5e-4keLY/pub?gid=233131974&single=true&output=csv)</li></ul></li></ul> |
| Format bidang stempel waktu | <ul><li>Stempel waktu UTC: `yyyy-mm-dd hh:mm:ss.sss`. Misalnya, ditampilkan sebagai`2019-09-17 00:09:00.123`. Sebuah event berlangsung pada pukul 18:00 waktu Tokyo. Waktu event dikonversi ke UTC, yaitu pukul 09:00. Waktu yang dicatat adalah waktu UTC.</li><li>Stempel zona waktu yang dipilih (khusus aplikasi): `yyyy-mm-dd hh:mm:ss.sss±th:tm`. Misalnya `2019-09-17 18:00:16.000+0900`. Sebuah event berlangsung pada pukul 18:00 waktu Tokyo. Waktu event yang ditampilkan dicatat sebagai 18:00+09:00. 09:00 adalah zona waktu Tokyo.</li></ul> |

<div id="available-message-types" />

#### Jenis pesan yang tersedia

<table><tbody><tr><th>Konteks atribusi</th><th>Jenis pesan</th><th>Bidang conversion_type </th><th>bidang campaign_type</th><th>bidang event_name</th><th>Bidang event_type</th></tr><tr><td>Akuisisi User</td><td>Penginstalan\*</td><td><span>Install</span></td><td><p>Non-organik: UA</p><p>Organik: organic</p></td><td><p>Install</p></td><td><ul><li><p>Install</p></li><li><p>penginstalan-organik</p></li></ul></td></tr><tr><td>Akuisisi pengguna </td><td>Instal in-app event</td><td><span>Install</span></td><td><p>Non-organik: UA</p><p>Organik: organic</p></td><td><p>Nama event yang ditentukan pengiklan</p></td><td><ul><li><p>penginstalan-in-app-event</p></li><li><p>penginstalan-organik-in-app-event</p></li></ul></td></tr><tr><td><p>Retargeting</p></td><td>Re-engagement</td><td><span>Re-engagement</span></td><td>penargetan ulang</td><td>Re-engagement</td><td><p>Re-engagement</p></td></tr><tr><td>Penargetan ulang </td><td>In-App Event Re-engagment</td><td>Re-engagement</td><td>penargetan ulang</td><td>Nama event yang ditentukan pengiklan</td><td><p>interaksi-ulang-in-app-event</p></td></tr><tr><td>Penargetan ulang </td><td>Atribusi ulang </td><td>instal ulang</td><td>penargetan ulang</td><td>Re-attribution</td><td><p>Re-attribution</p></td></tr><tr><td>Akuisisi pengguna </td><td>Penginstalan ulang</td><td>instal ulang</td><td><p>Non-organik: UA</p><p>Organik: organic</p></td><td><p>instal ulang</p></td><td><ul><li><p>instal ulang</p></li><li><p>penginstalan-organik</p></li></ul></td></tr><tr><td>Retargeting</td><td>In-App Event Re-attribution</td><td>instal ulang</td><td>penargetan ulang</td><td>Nama event yang ditentukan pengiklan</td><td><p>atribusi-ulang-in-app-event</p></td></tr><tr><td colspan="6">\* Beberapa penginstalan terkait atribusi lihat-tayang diatribusikan ke <a href="./about-raw-data-identifier-restrictions" target="_blank">sumber media yang dibatasi.</a> </td></tr></tbody></table>

<div id="unique-fields" />

#### Bidang unik

<table><tbody><tr><th>Nama tampilan</th><th>Nama Push API</th></tr><tr><td>Mata uang yang dipilih\*</td><td>selected_currency</td></tr><tr><td>Pendapatan dalam mata uang yang dipilih</td><td>mata uang income_in_selected_ <br/> </td></tr><tr><td>Biaya dalam mata uang yang dipilih</td><td>mata uang cost_in_selected_ <br/> </td></tr><tr><td>Zona waktu pengunduhan perangkat yang dipilih</td><td>device_download_time_selected_timezone</td></tr><tr><td>Zona waktu sentuh teratribusi yang dipilih</td><td>attributed_touch_time_selected_timezone</td></tr><tr><td>Zona waktu penginstalan yang dipilih</td><td>zona waktu install_time_selected_<br/> </td></tr><tr><td>Zona waktu event yang dipilih</td><td>Zona waktu event_time_selected_<br/> </td></tr><tr><td><p> zona waktu(\*) yang dipilih</p></td><td>selected_timezone</td></tr></tbody><tbody><tr><td colspan="2">\* Ini adalah pengaturan tingkat aplikasi yang berlaku pada saat pesan API dikirim.</td></tr></tbody></table>

</Accordion>

<div id="skan-attribution-messages" />

<Accordion title="Pesan atribusi SKAN">

Bagian ini menjelaskan pesan (jenis laporan) yang tersedia untuk SKAN dan cara mengidentifikasi pesan. Baca bagian ini, lalu [Siapkan titik akhir atribusi SKAN.](/docs/push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint)

Bacaan terkait: <Anchor target="_blank" href="/marketers/id/docs/skan-raw-data-reports">bidang data lengkap SKAN</Anchor>. Pesan Push API memiliki struktur dan bidang yang setara.

Karakteristik pesan:

| Karakteristik | Detail |
| --- | --- |
| Pembagian jenis pesan | <ul><li>Semua pesan dikirim ke 1 titik akhir yang ditentukan oleh Anda.</li><li>Untuk menentukan jenis pesan, gunakan bidang berikut:<ul><li>event\_name</li><li>skad\_redownload</li></ul></li><li>Nilai bidang, per jenis pesan, ditunjukkan pada tabel berikut</li></ul>Contoh:<br /><br />Pesan berisi hal berikut:<ul><li>event\_name: install</li><li>skad\_redownload: true</li></ul>Karena skad\_redownload: true, Anda menetapkan bahwa ini adalah event pengunduhan ulang. |
| Kesegaran data | <ul><li>Penginstalan, pengunduhan ulang, dan in-app event:<ul><li>Diproses setiap hari</li><li>Dikirim ke titik akhir Anda pada hari setelah menerima postback iOS oleh AppsFlyer</li><li>Perkiraan waktu penerimaan pesan event 05:00–08:00 UTC (waktu tepatnya berfluktuasi)</li><li>Misalnya: Postback yang diterima pada hari Senin dikirim mulai hari Selasa 05:00 UTC</li></ul></li><li>Postback dari iOS dan salinan Postback: Pesan dikirim segera setelah tiba di AppsFlyer</li></ul> |
| Contoh pesan | Lembar kerja berisi contoh pesan. Contoh yang diberikan memiliki format JSON. <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vS0CO6W7jgx6zxMeSGIo-hbqLbFh3AO0OT6qp4cWmgdbWVMjLJ-2dermVz49jmAXexewiOGzR1YjGzu/pub?output=xlsx">Pesan contoh SKAN</Anchor>. |

<div id="message-types-for-skan-attribution" />

#### Jenis pesan untuk atribusi SKAN

| Message type | bidang event\_name | bidang skad\_redownload | Bidang event\_type |
| --- | --- | --- | --- |
| Memasang | Install | <ul><li>Kemungkinan nilai: false, blank, null.</li><li>Jika bidang tidak ada dalam pesan, anggap nilainya adalah false (salah).</li></ul> | skad-instal |
| Pengunduhan ulang | Install | True | skad-unduh ulang |
| In-App Event | Nama event yang ditentukan oleh pengiklan | Nama event yang ditentukan oleh pengiklan | skad-in-app-event |
| Postback dari iOS | Tidak pernah tersedia dalam pesan ini | Terkadang tersedia | skad-postback |
| <Anchor target="_blank" href="/marketers/id/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">Salinan postback (postingan balik)</Anchor> | Tidak pernah tersedia dalam pesan ini | Terkadang tersedia | skad-postbacks-salin |

**Tentukan jenis pesan atribusi SKAN**

**Catatan:** Ini tidak berlaku untuk pesan salinan postback, yang datang langsung dari iOS.

![PushAPI-2_en-us.png](https://files.readme.io/7a3ede8da87e48cc640e6e61d8f42011174122140ca63ace37c1d5c25ceadc19-20274836865809.png)

</Accordion>

<div id="set-up-push-api-endpoints" />

## Atur titik akhir Push API

<div id="caution" />

> ❗️ **Perhatian**
>
> Jangan gunakan Push API untuk mengirim data yang diatribusikan dengan AppsFlyer ke pihak ketiga karena alasan berikut:
>
> * Anda dapat melanggar peraturan privasi, seperti CCPA, jika pengguna memilih tidak ingin mengirimkan data ke pihak ketiga.
> * Beberapa sumber media membatasi penggunaan data tingkat pengguna yang mereka sediakan, dibagikan dengan pihak ketiga, atau keduanya. Pastikan Anda mematuhi ketentuan penggunaan sumber media.
>   Misalnya, [Twitter,](https://business.twitter.com/en/help/ads-policies/introduction-to-twitter-ads/twitter-ads-policies.html) [Snapchat,](https://www.snap.com/en-US/privacy/privacy-policy/) [Pinterest.](https://policy.pinterest.com/en/privacy-policy)
>
> Catatan: Peringatan ini tidak berlaku untuk data SKAN. Gunakan Push API untuk mengirim data SKAN ke titik akhir pihak ketiga.

Untuk mengatur Push API, selesaikan daftar tindakan berikut.

<div id="push-api-setup-checklist" />

#### Daftar periksa pengaturan API

<table><tbody><tr><th>Langkah Nomor. </th><th>Atribusi AppsFlyer</th><th>Atribusi SKAdNetwork: </th></tr><tr><td>1</td><td colspan="2"><p>Jika Anda telah memiliki titik akhir Push API yang aktif, Anda dapat melewati langkah ini. </p><p>Selesaikan <a href="./push-api-streaming-raw-data#serverside-requirements-your-server">persyaratan sisi server</a>.</p></td></tr><tr><td>2</td><td><p>Untuk atribusi AppsFlyer, rencanakan pengaturan titik ahir menggunakan <a href="./push-api-streaming-raw-data#push-api-planning-checklist-for-appsflyer-attribution">Daftar periksa perencanaan Push API.</a></p></td><td><p>Tak dapat diterapkan</p></td></tr><tr><td>3</td><td><p><a href="./push-api-streaming-raw-data#set-up-appsflyer-attribution-endpoint">Atur titik akhir atribusi AppsFlyer</a></p></td><td><p><a href="./push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint">Atur titik akhir atribusi SKAdNetwork</a></p></td></tr></tbody></table>

<div id="serverside-requirements-your-server" />

<Accordion title="Persyaratan sisi server (server Anda)">

Pastikan server Anda mematuhi persyaratan berikut:

<div id="server-side-requirements" />

#### Persyaratan sisi server

| URL Titik Akhir | <ul><li>Nama domain yang valid</li><li>Jumlah maksimum titik akhir unik per aplikasi:<ul><li>AppsFlyer: 6 titik akhir</li><li>SKAdNetwork: 3 titik akhir</li></ul></li></ul> |
| --- | --- |
| Kode pengembalian titik akhir | Saat menerima pesan, titik akhir Anda harus mengembalikan kode status HTTP 200. |
| Izinkan server AppsFlyer | Izinkan daftar <Anchor target="_blank" href="/marketers/id/docs/appsflyer-server-ip-address-ranges-allowlisting">alamat IP</Anchor> server AppsFlyer di firewall dan sistem keamanan Anda untuk memastikan komunikasi dengan titik akhir. |
| Versi TLS | <ul><li>TLS 1.1</li><li>TLS 1.2+ Lihat <Anchor target="_blank" href="/marketers/id/docs/appsflyer-https-ssl-encryption-policy-support#outgoing-messages-appsflyer-as-client">cipher didukung</Anchor></li></ul> |
| Port | Port: 80, 443 |

</Accordion>

<div id="push-api-planning-checklist-for-appsflyer-attribution" />

<Accordion title="Daftar periksa Push API untuk atribusi AppsFlyer">

* Gunakan daftar periksa untuk memeriksa pengaturan titik akhir atribusi AppsFlyer. Angka-angka pada gambar sesuai dengan jumlah baris pada daftar periksa.
* Bagian ini tidak relevan dengan atribusi SKAdNetwork. Lihat [Mengatur atribusi SKAdNetwork.](/docs/push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint)

**Titik akhir**

[![PushAPI_us-en.png](https://files.readme.io/38b22e23c087e97c5424b649552823635310402a5c7be742bf6fc4e16d86cc42-360007246758.png)](https://files.readme.io/38b22e23c087e97c5424b649552823635310402a5c7be742bf6fc4e16d86cc42-360007246758.png)

<div id="configure-authentication-token" />

<div id="test-the-endpoint" />

<div id="add-an-appsflyer-attribution-endpoint" />

<div id="endpoint-planning-table" />

#### Tabel perencanaan titik akhir

| No. | Pengaturan | Detail | Gunakan kolom ini untuk mencatat pengaturan yang Anda rencanakan |
| --- | --- | --- | --- |
| 1 | Metode | POST atau GET |  |
| 2 | URL Titik Akhir | - |  |
| 3 | Tipe pesan event | <ul><li>Pilih setidaknya satu tipe pesan event.</li><li>Untuk memilih pesan in-app event, Anda harus merekam in-app event. Sampai Anda melakukannya, Anda tidak dapat memilih pesan in-app event.</li></ul>[![InappSelectionDisabled_us-en.png](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png) |  |
| 4 | <ul><li>Bidang</li><li>Daftar bidang bersifat umum untuk semua tipe pesan</li></ul> | **<span id="01H8E8DET2PBGQAKHJY40R1P9Z"></span>Peringatan**<br />Jika Anda menandai **Pilih semua** bidang yang baru ditambahkan juga akan dipilih secara otomatis. Harap pastikan Anda dapat mendukung semua bidang baru yang ditambahkan secara otomatis ke skema untuk menghindari masalah.<br /><br /><br /><br />Pilih bidang yang wajib diisi.<ul><li>Bidang yang paling umum dipilih sebelumnya secara default.</li><li>Kami tidak mengirim bidang kosong/null</li></ul> |  |
| 5 | Tipe in-app event | Menyaring berdasarkan in-app event untuk mengurangi lalu-lintas yang dikirim ke titik akhir Anda.<ul><li>Pilih satu atau lebih atau semua in-app event. Harap diperhatikan! Jika event tidak ditampilkan dalam daftar, carilah.</li><li>Jika Anda memilih semua, maka in-app event yang baru ditambahkan secara otomatis.</li><li>Anda hanya dapat memilih in-app event setelah direkam setidaknya sekali. Jika perlu, gunakan <Anchor target="_blank" href="/marketers/id/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor> untuk memulai event tersebut.</li><li>[![mceclip1.png](https://files.readme.io/b945d7bf1b8cebb3a4b925fb240e3e1976aee934f1179cca68680ae21d565bf3-360007337257.png)](https://files.readme.io/b945d7bf1b8cebb3a4b925fb240e3e1976aee934f1179cca68680ae21d565bf3-360007337257.png)</li></ul> |  |

</Accordion>

<div id="set-up-appsflyer-attribution-endpoint" />

<Accordion title="Atur titik akhir atribusi AppsFlyer">

**Catatan:** Hanya pemilik akun [AppsFlyer](/docs/push-api-streaming-raw-data#specifications-and-limitations) yang dapat melakukan perubahan pada pengaturan Push API. Pengguna akun lainnya dapat melihat pengaturan.

**Untuk menambahkan titik akhir atribusi AppsFlyer:**

1. Buka **Integrasi** > **Akses API**.  
   Gulir ke bawah ke sesi Push API.
2. Klik ***Tambahkan Titik Akhir.***
3. Pilih metode HTTP: ***POST***atau **GET**
4. Masukkan **URL Titik Akhir**. Jika Anda mendapatkan pesan *URL ini tidak aman*, hubungi tim dukungan AppsFlyer.
5. Pilih satu tipe event atau lebih. **Perhatikan**: Jika pesan in-app event dinonaktifkan, artinya tidak ada in-app event yang dicatat hingga saat ini.
6. Pilih bidang untuk mengisi pesan Push API. Catatan:  
   * Bidang-bidang wajib yang selalu dikirim: ID Aplikasi, Nama event, Waktu event, IDFA (iOS) atau ID Iklan (Android)
   * Gunakan kontrol yang dijabarkan pada gambar berikut untuk memilih bidang opsional.

     [![PushAPIFieldSelect1.jpg](https://files.readme.io/316bdfcb4740d870875176e7806f969c89784406c3abc5ca34c9fa0c675a5497-360007416298.jpg)](https://files.readme.io/316bdfcb4740d870875176e7806f969c89784406c3abc5ca34c9fa0c675a5497-360007416298.jpg)

     * Bidang yang paling umum dipilih sebelumnya secara default. Anda dapat membatalkan pilihan ini.
     * Pilih bidang opsional sesuai kebutuhan.
     * Gunakan ***Hapus semua*** untuk menghapus semua bidang pilihan.
     * Kami tidak mengirim bidang null/kosong dan kunci terkait. Pertimbangkan ini saat merencanakan proses impor/parsing Anda.
7. Pilih satu atau lebih (hingga 52 event) atau ***Semua*** in-app event.  
   * Daftar ini diisi oleh tipe event yang telah direkam. Jika acara tidak ada, kirimkan event dengan tipe ini menggunakan perangkat uji.
8. Klik **Save** (Simpan).  
   Push API sekarang aktif. Data konversi dikirim ke titik akhir.
9. Uji titik akhir menggunakan prosedur berikut.

**Untuk menguji titik akhir:**

1. Klik **Send Test.** Pesan hasil pengujian tampil di bawah tombol **Send Test** .   
    Sebuah pesan pengujian dikirimkan ke titik akhir. Jika pengujian gagal, pastikan Anda memiliki <Anchor target="_blank" href="/marketers/id/docs/appsflyer-server-ip-address-ranges-allowlisting">alamat IP AppsFlyer yang diizinkan</Anchor>.   
   **Catatan**! Mekanisme timeout, memiliki durasi 2 detik, digunakan. Jika AppsFlyer tidak mendapatkan pesan OK selama waktu ini, AppsFlyer menganggap ini sebagai kegagalan pengiriman pesan.
2. Verifikasi bahwa titik akhir Anda menerima pesan pengujian.  
   [Lihat salinan pesan yang dikirim.](https://docs.google.com/spreadsheets/d/e/2PACX-1vScQf189h3Ry0BU-ejbZYkMZCJRdXXYeOwuNxPEHwY77vCVYWW9P9xCTUSJKmTvVbp_yzLidXD0WGLm/pub?gid=0&single=true&output=csv)

</Accordion>

<div id="set-up-skadnetwork-attribution-endpoint" />

<Accordion title="Atur titik akhir atribusi SKAdNetwork">

**Catatan:** Hanya pemilik akun [AppsFlyer](/docs/push-api-streaming-raw-data#specifications-and-limitations) yang dapat melakukan perubahan pada pengaturan Push API. Pengguna akun lainnya dapat melihat pengaturan.

**Untuk menambahkan titik akhir SKAdNetwork Push API:**

1. Buka **Integrasi** > **Akses API**.  
   Gulir ke bawah ke sesi Push API.
2. Pilih **SKAdNetwork** sebagai entitas atribusi.
3. Klik Add Endpoint   
   (Tambahkan Titik Akhir). Catatan : Anda dapat menentukan 1-3 titik akhir SKAdNetwork per aplikasi.
4. Pilih metode HTTP: ***POST***atau **GET**
5. Masukkan URL **Titik Akhir** . Jika Anda mendapatkan pesan *URL ini tidak aman*, hubungi tim dukungan AppsFlyer.
6. Kami tidak mengirim bidang null/kosong dan kunci terkait. Pertimbangkan ini saat merencanakan proses impor/parsing Anda.
7. Klik **Save** (Simpan).  
   Push API sekarang aktif. Data dikirim ke titik akhir.

</Accordion>

<div id="additional-proceduresmanaging-endpoints" />

## Prosedur tambahan—mengelola titik akhir

<div id="change-an-endpoint" />

<Accordion title="Mengubah titik akhir">

**Catatan:** Hanya pemilik akun [AppsFlyer](/docs/push-api-streaming-raw-data#specifications-and-limitations) yang dapat melakukan perubahan pada pengaturan Push API. Pengguna akun lainnya dapat melihat pengaturan.

**Untuk mengubah pengaturan titik akhir:**

1. Buka **Integrasi** > **Akses API**.Gulir ke bawah ke sesi Push API.
2. Temukan titik akhir yang akan diubah.
3. Lakukan perubahan.
4. Klik **Save**.

</Accordion>

<div id="delete-an-endpoint" />

<Accordion title="Menghapus titik akhir">

**Catatan:** Hanya pemilik akun [AppsFlyer](/docs/push-api-streaming-raw-data#specifications-and-limitations) yang dapat melakukan perubahan pada pengaturan Push API. Pengguna akun lainnya dapat melihat pengaturan.

**Untuk menghapus titik akhir**:

1. Buka **Integration (Integrasi)** > **API Access (Akses API)**.  
    Gulir ke bawah ke bagian akses Push API.
2. Klik **Hapus titik akhir**.
3. Klik **Save**.  
    Titik akhir dihapus.

</Accordion>

<div id="authentication-token-in-test-messages" />

<div id="can-i-include-custom-headers-with-the-push-api-request" />

<div id="troubleshooting-traits-and-limitations" />

## Penyelesaian masalah, karakteristik, dan batasan

<div id="test-message-fails" />

<Accordion title="Pesan tes gagal">

Jika Anda tidak menerima pesan pengujian dan Anda membatasi akses ke server berdasarkan alamat IP: pastikan Anda memiliki <Anchor target="_blank" href="/marketers/id/docs/appsflyer-server-ip-address-ranges-allowlisting">semua alamat IP AppsFlyer yang diizinkan</Anchor>.

</Accordion>

<div id="duplicate-retargeting-inapp-events" />

<Accordion title="Duplikat penargetan ulang event dalam aplikasi">

Penargetan ulang event dalam aplikasi diduplikasi ketika event pembelian terjadi sebagai bagian dari kampanye penargetan ulang selama jendela interaksi ulang UA. Ini dilakukan untuk menghubungkan pendapatan dengan sumber media UA dan sumber media penargetan ulang.

Anda hanya akan mendapatkan duplikat event jika Anda telah mengaktifkan keduanya:

* Instal in-app event
* Menargetkan ulang event dalam aplikasi

<Anchor target="_blank" href="/marketers/id/docs/resolve-retargeting-double-attribution">Identifikasi dan hapus duplikat in-app event</Anchor>

</Accordion>

<div id="inapp-event-message-selection-is-disabled" />

<Accordion title="Pilihan pesan in-app event message dinonaktifkan">

[![InappSelectionDisabled_us-en.png](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)

* Pesan in-app event hanya dapat dipilih setelah salah satu in-app event telah direkam.
* Gunakan perangkat uji untuk menghasilkan in-app event atau gunakan <Anchor target="_blank" href="/marketers/id/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S API</Anchor> untuk melakukannya secara manual.

</Accordion>

<div id="missing-push-messages-and-cloudfront" />

<Accordion title="Pesan push dan CloudFront tidak ada">

Apakah Anda menggunakan Amazon CloudFront sebagai titik akhir Anda? Jika demikian, periksa apakah CloudFront menolak pesan dengan kode tolak 421. Jika demikian, lihat <Anchor target="_blank" href="https://docs.aws.amazon.com/en_pv/AmazonCloudFront/latest/DeveloperGuide/cnames-https-dedicated-ip-or-sni.html">Memilih Cara CloudFront Melayani Permintaan HTTPS</Anchor>

</Accordion>

<div id="endpoint-error-messages" />

<Accordion title="Pesan kesalahan titik akhir">

**Petunjuk:** Pesan *URL ini tidak aman* tampil saat Anda mengatur URL titik akhir.

**Tindakan yang diperlukan**: Hubungi tim dukungan AppsFlyer; sertakan ID aplikasi, URL titik akhir, dan screenshot pesan kesalahan.

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Spesifikasi dan batasan">

| **Spesifikasi** | Catatan |
| --- | --- |
| <span id="ad-networks"></span>Jaringan iklan | Tidak tersedia |
| <span id="agencies"></span>Agensi | Tidak tersedia |
| <span id="appspecific-time-zone"></span>Zona waktu khusus aplikasi | Didukung |
| <span id="appspecific-currency"></span>Mata uang khusus aplikasi | Didukung |
| <span id="size-limitations"></span>Keterbatasan ukuran | Tak dapat diterapkan |
| <span id="organic"></span>Organik | Ya |
| <span id="nonorganic"></span>Non-organik | Ya |
| <span id="data-freshness"></span>Kesegaran data | Terus menerus |
| <span id="historical-data"></span>Data historis | Tidak didukung. Jika Anda kehilangan data, gunakan Pull API untuk mendapatkan data. Dalam hal SKAN, Anda bisa mendapatkan beberapa data historis melalui Data Locker (dibatasi oleh jendela ketersediaan Data Locker). |
| <span id="account-owneruser-access"></span>Pemilik akun/akses pengguna | Hanya **pemilik akun**AppsFlyer yang dapat melakukan perubahan pada pengaturan Push API.<ul><li>Setiap akun AppsFlyer **hanya memiliki satu** pemilik akun. Ini adalah pengguna AppsFlyer pertama (dibuat pada saat akun dibuka) .</li></ul>Pengguna akun lainnya dapat melihat pengaturan Push API tetapi tidak dapat melakukan perubahan. |

</Accordion>

<div id="see-also" />

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Membandingkan alat pengiriman data lengkap</Anchor>
> * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/put_app-app-id">Siapkan Push API menggunakan API</Anchor>

<div data-zendesk-anchors="01H89PJFBPXVKJGGH18CJBJ41W=push-api 01H89PJFBP45FQDHT4YGS58NP8=appsflyer-attribution-messages available-message-types=jenis-pesan-yang-tersedia 01H89PJFBP9DEX520BDGC5PANQ=jenis-pesan-yang-tersedia unique-fields=bidang-unik 01H89PJFBPBK09Q7CRPMM4G7PJ=bidang-unik 01H89PJFBQM4NKFSFF8XGMX9XT=skan-attribution-messages message-types-for-skan-attribution=jenis-pesan-untuk-atribusi-skan 01H89PJFBQBFCK5QVWW2X09H28=jenis-pesan-untuk-atribusi-skan set-up-push-api-endpoints=atur-titik-akhir-push-api 01H89PJFBQZ2FW3ST5V4FW91GS=atur-titik-akhir-push-api 01H89PJFBQ6WP7ERP0DJ69QZ1G=perhatian push-api-setup-checklist=daftar-periksa-pengaturan-api 01H89PJFBQ625A7G3QT5HQJXMW=daftar-periksa-pengaturan-api 01H89PJFBQGW8ZV76Z0HTNX2AB=serverside-requirements-your-server serverside-requirements=persyaratan-sisi-server 01H89PJFBQ2BC5GHX403RD2RAT=persyaratan-sisi-server 01H89PJFBQ4FXB7ABMFVHX326H=push-api-planning-checklist-for-appsflyer-attribution endpoint-planning-table=tabel-perencanaan-titik-akhir 01H89PJFBQJXWWPQDKZ387VYX3=tabel-perencanaan-titik-akhir 01H89PJFBQZE6KJDHXRB8GK7TF=set-up-appsflyer-attribution-endpoint 01H89PJFBQQS31C6AF245SSJ61=set-up-skadnetwork-attribution-endpoint additional-procedures%E2%80%94managing-endpoints=prosedur-tambahanmengelola-titik-akhir 01H89PJFBQ7WV3NM7JR5Z9QEFB=prosedur-tambahanmengelola-titik-akhir 01H89PJFBQ9RZXNHGNNYV5MP7P=change-an-endpoint 01H89PJFBQGE1WESD7ZEMBEFNE=delete-an-endpoint troubleshooting-traits-and-limitations=penyelesaian-masalah-karakteristik-dan-batasan 01H89PJFBQJDGT1FVHKG9DETHJ=penyelesaian-masalah-karakteristik-dan-batasan 01H89PJFBQAAZYF7YWKC7TP884=test-message-fails 01H89PJFBQHQJSHE09GC599AQ6=duplicate-retargeting-inapp-events 01H89PJFBRDET8T8CTAP1GW0J9=inapp-event-message-selection-is-disabled 01H89PJFBRH58FX1FTH37DP3HC=missing-push-messages-and-cloudfront 01H89PJFBR3CJSR2AEFP3HT5JE=endpoint-error-messages 01H89PJFBRZXXEMPBGBPB35MQ9=specifications-and-limitations h_01HE7SH7XFMPJ13DKCZ04RCJDD=lihat-juga" />
