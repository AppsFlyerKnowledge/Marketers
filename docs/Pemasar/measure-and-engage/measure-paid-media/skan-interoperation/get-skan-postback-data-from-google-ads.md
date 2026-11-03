---
title: 'Dapatkan data postback SKAN dari Google Ads '
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-06-28T19:34:39Z'
  edited_at: '2023-12-21T09:58:32Z'
  id: 4403215779857
  locale: id
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/id/articles/4403215779857
---
> **Sekilas:** Memungkinkan Google untuk membagikan konten postback iOS aplikasi SKAdNewtork (SKAN) Anda dengan AppsFlyer.

## Dapatkan data postback SKAN dari Google Ads

Jika Anda bekerja dengan beberapa mitra jaringan iklan, praktik terbaiknya adalah menyiapkannya di AppsFlyer. Dengan demikian, metrik kinerja SKAN untuk semua mitra jaringan iklan Anda, yang diperkaya dengan metrik lain seperti biaya, tersedia melalui platform AppsFlyer.

**Lingkup pelaporan SKAN dengan Google Ads**

* Google Ads membagikan gabungan postback SKAN iOS yang mereka terima dengan AppsFlyer dalam konteks kampanye aplikasi iOS. Postback ini mewakili penginstalan dari beberapa saluran seperti display (tampilan) dan YouTube, namun umumnya mengecualikan sebagian besar penelusuran karena SKAN tidak mendukung pelacakan web->aplikasi pada saat ini.
* AppsFlyer mendekode postback lalu memperbarui dashboard SKAN dan laporan (termasuk laporan data lengkap postback).
* <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns#ios-145-srn-attribution">Implikasi iOS 14.5 pada pelaporan SRN</Anchor>

**Pertimbangan**:

Saat menerima postback iOS, Google menentukan waktu klik terakhir menggunakan sinyal penayangan iklan. Namun, AppsFlyer menganggap waktu klik sebagai waktu instalasi. Hal ini dapat menyebabkan perbedaan antara dashboard AppsFlyer dan Google.

Karena metodologi pelaporan klik Google dan pembaruan data retroaktifnya setiap hari, AppsFlyer mengambil data dari 45 hari sebelumnya dan menampilkan penginstalan pada klik terakhir sebelum tanggal penginstalan.  Misalnya, klik pada tanggal 1 Juli dapat dilaporkan ke AppsFlyer hingga  tanggal 15 Agustus. AppsFlyer menampilkan penginstalan ini berdasarkan tanggal klik yang dilaporkan oleh Google. Hal ini berdampak pada <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide#reporting-options">laporan</Anchor> sebagai berikut:

* Laporan gabungan dan pembaruan dashboard secara retroaktif.
* <Anchor target="_blank" href="/marketers/id/docs/skan-raw-data-reports">Laporan data lengkap</Anchor> tidak berubah secara retroaktif. Data (disediakan melalui Data Locker) disediakan dalam folder sesuai dengan tanggal Google memberikan data tersebut ke AppsFlyer (tanggal kedatangan data).

## Siapkan interoperasi

Untuk menyiapkan interoperasi dengan Google Ads, selesaikan langkah-langkah di tab berikut.

<div id="set-up-postbacks" />

<Accordion title="Atur postback">

**Untuk mengatur pengiriman postback:**

| Langkah | Tindakan | Detail |
| --- | --- | --- |
| <span id="1"></span>1 | Tinjauan pengaturan SKAN | Verifikasi bahwa <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide">solusi SKAN</Anchor> AppsFlyer sudah diatur dan diaktifkan. Hal ini memungkinkan SDK AppsFlyer memanggil API SKAN dan menetapkan nilai konversi.<br /><br />**Untuk meninjau pengaturan SKAN**:<ol><li>Di AppsFlyer, buka **Configuration** > **SKAN Conversion Studio**.</li><li>Klik opsi (⋮), dan verifikasi bahwa **pengukuran SKAN** aktif.</li></ol>![skan-settings.png](https://files.readme.io/5602fded7e030177bb921ff83ff1e6dad7a230a87825e112314935a4c3dd83dd-4406452045457.png)<ol><li>Pilih mode pengukuran pilihan Anda.<br />Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.</li><li>Catat set nama event yang tepat. Anda akan membutuhkannya pada langkah berikutnya. **Perhatikan**! Nama peka huruf besar-kecil.</li></ol> |
| <span id="2"></span>2 | Pemetaan in-app event di AppsFlyer | **Untuk melihat dan mengatur pemetaan in-app event**:<ol><li>Di AppsFlyer, buka **Konfigurasi** > **Integrasi Aktif**.</li><li>Pilih **Google Ads**.</li><li>Dari tab **Integrasi** , verifikasi bahwa **Aktifkan Mitra** aktif. Jika belum, Anda harus menyelesaikan <Anchor target="_blank" href="/marketers/id/docs/google-ads-adwords-integration-setup-for-advertisers">integrasi dengan Google Ads</Anchor> terlebih dahulu.</li><li>Di **bagian postback in-app event**:<ol><li>Jika tidak aktif, aktifkan **Postback in-app event**.</li><li>Praktik terbaiknya adalah memetakan event terkait dengan jenis pengukuran yang dipilih saat ini. Catatan! Dalam hal pengukuran pendapatan, petakan af\_skad\_revenue ke event pendapatan Google yang sesuai</li></ol></li><li>Gulir ke bawah ke bagian bawah halaman.</li><li>Klik **Simpan integrasi**.</li></ol> |

</Accordion>

<div id="allow-google-ads-to-share-skan-data-with-appsflyer" />

<Accordion title="Izinkan Google Ads untuk membagikan data SKAN dengan AppsFlyer">

Untuk melihat penginstalan SKAN yang diatribusikan ke Google Ads di dashboard SKAN AppsFlyer, Anda harus mengizinkan Google Ads untuk berbagi data SKAN dengan AppsFlyer.

**Untuk memberikan izin kepada Google Ads untuk membagikan data SKAN dengan AppsFlyer:**

1. Prosedur berikut harus dilakukan oleh pemasang iklan, agensi, atau keduanya.
2. Di AppsFlyer, buka **Konfigurasi** > **Integrasi Aktif**.
3. Telusuri dan pilih **Google Ads**.
4. Buka tab **SKAN** .

   <Image alt="mceclip0.png" src="https://files.readme.io/ba8d881ca8430bfdcf67a37e862ad3e31a9af522f2f877d3fba30bc2e13006a6-4404428381457.png" width="309px" />
5. Jika **pesan yang sementara tidak tersedia ditampilkan**, sering kali itu berarti pemblokir iklan aktif. Jika ya, nonaktifkan pemblokir iklan dan muat ulang halaman. Jika tidak demikian, hubungi dukungan AppsFlyer.

   ![mceclip1.png](https://files.readme.io/e86b868f71e11ad347ff7557a793090d9d6adb8fe4df4f9010c8d770b373ac6a-4404428420497.png)
6. Klik **login Google Ads**.
   * Anda harus masuk ke Google Ads menggunakan peran pengguna Administrator di akun.
   * Jika akun Google diasosiasikan dengan beberapa aplikasi, masuk sekali, dan semua aplikasi diotorisasi. Dengan kata lain, tidak perlu melakukan otorisasi per aplikasi.
   * AppsFlyer mengambil data untuk semua aplikasi iOS AppsFlyer yang dikaitkan dengan akun Google Anda, terlepas dari pengaturan mitra pengaktifan aplikasi tersebut.
7. Ikuti instruksi di antarmuka pengguna.
8. Dalam beberapa kasus, Anda mungkin diminta untuk memberikan izin kepada AppsFlyer untuk **Mengelola kampanye AdWords Anda.** Jika demikian, Anda harus mengaktifkan izin tersebut. Jangan khawatir, kami tidak akan melakukan perubahan pada pengaturan kampanye Anda.

   [<Image alt="GoogleManageAdWords.png" src="https://files.readme.io/bf327f152f937cdbea0b71cca72cc989aa83de6cef83677fca1f687b71aa8606-4405185007121.png" width="182px" />](https://files.readme.io/bf327f152f937cdbea0b71cca72cc989aa83de6cef83677fca1f687b71aa8606-4405185007121.png)
9. Verifikasi bahwa status akun, **menunggu sinkronisasi** ditampilkan.  
   Pesan ini tetap ada hingga kami mendapatkan data dari Google Ads (maksimal 24 jam.)
10. Tunggu hingga setelah pukul 02.00 UTC keesokan harinya, lalu verifikasi bahwa statusnya berubah menjadi **aktif.**  
    Data di dashboard SKAN diperbarui setiap hari paling lambat pukul 08.00 UTC. **Perhatikan**! Seperti yang dijelaskan di bagian pertimbangan, Google dapat memperbarui data 45 hari secara retroaktif.
11. Baca tentang [perbedaan pengukuran](/docs/get-skan-postback-data-from-google-ads#measurement-and-timing-differences-between-appsflyer-and-google-ads).

</Accordion>

## Informasi tambahan

<div id="turning-off-the-skan-integration" />

<Accordion title="Mematikan integrasi SKAN">

Saat menonaktifkan integrasi Google Ads , menonaktifkan sakelar **Aktifkan mitra saja** tidak cukup, Anda harus menghapus koneksi SKAN secara terpisah untuk menghentikan pencatatan data SKAN.

**Untuk mematikan integrasi SKAN:**

1. Di AppsFlyer, buka **Konfigurasi** > **Integrasi Aktif**.
2. Telusuri dan pilih Google Ads.
3. Buka tab **SKAN** .
4. Klik ikon hapus untuk akun yang ingin Anda hapus.

</Accordion>

<div id="measurement-and-timing-differences-between-appsflyer-and-google-ads" />

<Accordion title="Perbedaan pengukuran dan waktu antara AppsFlyer dan Google Ads">

| Item | Detail |
| --- | --- |
| <span id="earliest-data-availability"></span>Ketersediaan data paling awal | Data tersedia mulai tanggal Anda mengaktifkan integrasi menurut waktu UTC. Karena Google menggunakan waktu klik, penginstalan dari sebelum tanggal mulai dapat ditampilkan secara retroaktif. |
| <span id="install-date"></span>Tanggal penginstalan | Google mengatur waktu penginstalan ke perkiraan waktu klik terakhir sebelum penginstalan. Google yang menentukan waktu klik menggunakan sinyal penayangan iklan.<br /><br />Hal berikut harus dipertimbangkan ketika membandingkan sumber media dan dashboard di AppsFlyer:<ul><li>AppsFlyer tidak mempertimbangkan zona waktu aplikasi atau zona waktu akun iklan Google Ads.</li><li>Google dapat melaporkan penginstalan secara retroaktif selama 45 hari setelah tanggal penginstalan.</li><li>Dalam kasus sumber media lain, kami memperoleh waktu penginstalan menggunakan waktu kedatangan postback.</li></ul> |
| <span id="installs"></span>Penginstalan | Dari Google Ads API V10+, AppsFlyer hanya menampilkan penginstalan dari postback dengan did\_win=TRUE. Akibatnya, jumlah penginstalan di AppsFlyer mungkin lebih rendah dibandingkan di dashboard Google Ads. |

</Accordion>

<div id="troubleshooting-and-faq" />

<Accordion title="Pemecahan masalah dan Pertanyaan Umum (FAQ)">

| Item | Detail |
| --- | --- |
| <span id="sending-events-to-google-ads"></span>Mengirim acara ke Google Ads | **T**: Apakah masuk akal untuk mengirimkan postback event tambahan ke Google Ads untuk event yang tidak dipilih dalam opsi pengukuran nilai konversi?<br /><br />**J**: Untuk pengguna yang menyetujui, kirimkan seluruh rangkaian event untuk memaksimalkan kemampuan Google Ads dalam optimisasi. |
| <span id="map-multiple-events-to-the-same-google-ads-event"></span>Memetakan beberapa event ke event Google Ads yang sama | **T**: Dapatkah saya memetakan beberapa in-app event ke satu event Google Ads?<br /><br />**J**: Jika beberapa event dipetakan ke satu event standar Google Ads, Google Ads tidak dapat membedakan event-event tersebut. Jadi, Google Ads akan mengoptimalkan satu event yang mereka kenali. |
| <span id="campaign-types-supported"></span>Jenis kampanye didukung | **T:** Jenis kampanye Google Ads apa yang didukung?<br /><br />**J**: Kampanye iOS web-ke-aplikasi dan Aplikasi-ke-aplikasi termasuk penelusuran, video, dan sebagainya. |
| <span id="no-data-to-pull"></span>Tidak ada data untuk diambil | **T:** Mengapa status koneksi menampilkan "Tidak ada data untuk diambil: Periksa izin berbagi data Google Anda"?<br /><br />**A**: Mungkin belum ada data SKAN atau Anda harus masuk ke Google Ads menggunakan peran pengguna Administrator di akun tersebut. |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Spesifikasi dan batasan">

| Spesifikasi | Deskripsi |
| --- | --- |
| <span id="engaged-views"></span>Penayangan tak dilewati | Penayangan tak dilewati dihitung sebagai klik dan postback dikirim untuknya karena berfungsi untuk atribusi klik-tayang mana pun. |
| <span id="data-freshness"></span>Keaktualan data | <ul><li>Kami mengumpulkan data SKAN dari Google Ads setiap hari mulai pukul 01.00 UTC.</li><li>Pembaruan dashboard dan data gabungan 7 jam kemudian.</li></ul> |
| <span id="reports-available"></span>Laporan yang tersedia | Data Google Ads tersedia di laporan dashboard SKAN, laporan gabungan, dan laporan data lengkap. Lihat <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide#reporting-options">opsi pelaporan SKAN.</Anchor> |
| <span id="agencies"></span>Agensi | Jika agensi memiliki peran pengguna Administrator di akun Google Ads pemasang iklan, maka mereka dapat melakukan prosedur dalam artikel ini dan mengaktifkan interoperasi SKAN Google atas nama pemasang iklan. Pemasang iklan juga tidak perlu masuk ke Google Ads mereka juga. Login agensi ditunjukkan di akun pemasang iklan. |

</Accordion>

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide">Panduan Solusi AppsFlyer SKAN</Anchor>

<div data-zendesk-anchors="get-skan-postback-data-from-google-ads=dapatkan-data-postback-skan-dari-google-ads h_01HCHYGCVJA3C8WJS8JH7BG0CD=dapatkan-data-postback-skan-dari-google-ads set-up-interoperation=siapkan-interoperasi h_01HCHYGCVJY5KT4J6RQS0BJ90G=siapkan-interoperasi h_01HCHYGCVJKHF0NFJSAZMMKZ7Z=set-up-postbacks h_01HCHYGCVJEA39W87MWXF7P018=allow-google-ads-to-share-skan-data-with-appsflyer additional-information=informasi-tambahan h_01HCHYGCVJTS53PCGK21BEZB2T=informasi-tambahan h_01HCHYGCVJCSGKYQD3EH0GKZVS=turning-off-the-skan-integration h_01HCHYGCVJE80JX9BKE8NFMA45=measurement-and-timing-differences-between-appsflyer-and-google-ads h_01HCHYGCVJX832CCX87JHGD50W=troubleshooting-and-faq h_01HCHYGCVJ1D32JW8G9YSR27PN=specifications-and-limitations h_01HE7RMSECNDW9VD9XY6H01H55=lihat-juga" />
