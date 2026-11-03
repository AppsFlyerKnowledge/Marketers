---
title: Panduan anti-kecurangan Protect360
metadata:
  keywords:
    - Advertisers
    - Protect360
    - protect
    - protect 360
    - '360'
    - p360
    - p 360
    - 360protect
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2016-12-06T07:47:17Z'
  edited_at: '2023-11-03T12:15:36Z'
  id: 218254203
  locale: id
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/id/articles/218254203
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Sekilas:** Penipuan atribusi menguras anggaran pemasaran, mencemari data kinerja pemasaran, dan dapat mengubah keberhasilan kampanye menjadi kegagalan. **Protect360 memberi pemilik aplikasi perlindungan penipuan waktu aktual dan deteksi setelah atribusi.**

![p360intro2.jpg](https://files.readme.io/c8476382eeff62164ca93b9bf2f3c4cdbe0609d4160047eac36a44d5f333ffdb-360014803578.jpg)

## Ikhtisar Protect360

* Melindungi dari penipuan atribusi. Ini terdiri dari alat dinamis yang mendeteksi penipuan dan memblokir atribusi penipuan.
* Menggunakan skala AppsFlyer, pembelajaran mesin, dan analisis perilaku untuk menyediakan perlindungan terhadap penipuan klik/instalasi yang umum dan baru termasuk bot dan anomali perilaku.
* Melindungi pemasar dari penipuan di level perangkat, penerbit, dan sumber media.
* Menggunakan pendekatan berlapis pemblokiran penipuan waktu aktual dan  identifikasi penipuan pasca atribusi
* Tidak memengaruhi pengalaman pengguna aplikasi. Dalam kasus upaya penipuan yang melibatkan pengguna nyata, penginstalan aplikasi selesai secara normal, dan hanya pencatatan atribusi yang terpengaruh.

<div id="realtime-blocking" />

<Accordion title="Pemblokiran waktu aktual">

* Dalam waktu aktual, sebelum atribusi, penginstalan diidentifikasi berasal dari sumber media yang palsu dan diblokir dari atribusi.
* In-app event berikutnya dari pengguna yang sama, diblokir.
* Penginstalan yang diblokir dan in-app event dilaporkan di dashboard Protect360 dan laporan penipuan yang diblokir.
  * Penginstalan yang diblokir dan in-app event: Tidak disertakan dalam atribusi dan dashboard AppsFlyer karena tidak pernah diatribusikan.
* Postback instalasi yang diblokir dikirim ke sumber media, dengan alasan pemblokiran, memungkinkannya untuk dioptimalkan.

<Anchor target="_blank" href="/marketers/id/docs/protect360-raw-data-reports">Tentang event yang diblokir</Anchor>

</Accordion>

<div id="postattribution-detection" />

<Accordion title="Deteksi pasca atribusi">

* Kecurangan yang diidentifikasi setelah atribusi disebut sebagai kecurangan pasca-atribusi. Kecurangan pasca-atribusi dapat diidentifikasi pada hari penginstalan, dan hingga 7 hari setelahnya (total 8 hari).
* Setelah diatribusikan, penginstalan tidak dapat dihapus. Untuk alasan ini, penipuan pasca atribusi ditangani secara berbeda dengan penipuan waktu aktual.
* Kecurangan penginstalan dan in-app event yang diidentifikasi dalam retrospek , harus diperlakukan sebagai kecurangan nyata dan tidak dikenakan biaya.

Setelah sumber, seperti jaringan iklan atau ID situs, diidentifikasi sebagai penipuan:

* Klik berikutnya dari sumber diblokir.
* Pasca instalasi:
  * Dari awal bulan kalender saat ini hingga saat ini, diberi label sebagai penipuan pasca atribusi, tetapi  **tidak dihapus dari data** . Pada Januari 2020, tagihan pengiklan dikreditkan untuk biaya atribusi instalasi ini.
  * Dari sebelum awal bulan ini, tidak berubah.
* In-app event terjadi:
  * **Hingga** pelabelan instal: diberi label sebagai penipuan.
  * **Setelah** pelabelan: diberi label sebagai penipuan.

Contoh kecurangan pasca-atribusi:

* Install reguler yang tampaknya diikuti oleh sinyal kecurangan dalam in-app event
* Bentuk penipuan baru ditemukan
* Install yang diketahui sebagai kecurangan hanya setelah algoritme deteksi anomali mengumpulkan cukup data statistik tentang install penerbit

</Accordion>

<div id="common-fraud-issues-and-solutions" />

<Accordion title="Masalah dan solusi penipuan yang umum">

Ketika AppsFlyer mengidentifikasi penipuan, **eventatribusi**  yang terkait dengan penipuan diblokir. Ini menghilangkan keuntungan dan motivasi penipu. **Catatan**: Penginstalan aplikasi itu sendiri berlangsung dan tidak diblokir. Artinya, pengguna aplikasi dapat menggunakan aplikasi tersebut dan menghasilkan pendapatan bagi pengiklan.  

Klik, instalasi, dan in-app event penipuan yang diblokir  ditampilkan di <Anchor target="_blank" href="/marketers/id/docs/protect360-raw-data-reports">laporan data lengkap penipuan Protect360</Anchor>.

Tabel berikut menjelaskan beberapa jenis penipuan dan bagaimana Protect360 menanganinya.

| Jenis penipuan | Deskripsi | Solusi AppsFlyer |
| --- | --- | --- |
| <span id="device-id-reset-fraud"></span>**Reset fraud ID Device** | ID Perangkat selalu direset oleh penipu pada perangkat fisik yang sama, untuk menghasilkan  penginstalan dalam jumlah besar. | AppsFlyer mengidentifikasi tingkat abnormal pada perangkat baru dan sebagai akibatnya menolak daftar sumber yang mengirimkannya. |
| <span id="install-hijacking"></span>**Pembajakan install** | Para pelaku kecurangan menanam malware pada perangkat mobile yang memperingatkan saat download app dilakukan. Klik langsung dikirim ke AppsFlyer yang mengklaim kredit untuk install. | Klik terkait diblokir dengan CTIT yang sangat cepat (<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-to-install-time-ctit/"> Click to Install Time/Jeda Waktu Klik Hingga Instalasi)</Anchor> ) dan berdasarkan API Sisi Server Google Play. |
| <span id="click-hijacking"></span>**<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-hijacking/">Pembajakan klik</Anchor>** | Malware mengidentifikasi klik tautan atribusi penginstalan dan secara langsung mengirimkan klik lain yang memberinya kredit jika diatribusikan. | AppsFlyer memblokir klik terkait yang terjadi begitu cepat setelah klik lainnya untuk aplikasi yang sama pada perangkat yang sama. |
| <span id="click-flooding"></span>**<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-flooding/">Click flooding</Anchor>** | Mobile fraud di mana jumlah klik kecurangan yang besar dikirim, dengan tujuan untuk mengirimkan klik terakhir sebelum install. | Memblokir klik terkait dari ID situs dengan rasio konversi rendah dan CTIT panjang. |
| <span id="behavioral-anomalies"></span>**Anomali perilaku** | Mobile fraud di mana pelaku kecurangan menghasilkan aktivitas pasca-install yang tidak konsisten dan tidak normal. | Skala unik kami memungkinkan kita untuk mengukur dan memahami pola interaksi perilaku pada beberapa level, seperti dengan app, wilayah, media source, dan penerbit. Pola perilaku bukan manusia teridentifikasi dalam waktu aktual dekat, dan diblokir di sumber. |
| <span id="ip-denylists"></span>**Daftar blokir IP** | Para pelaku kecurangan biasanya beroperasi dari <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-farms/">pabrik klik</Anchor>, yang bisa diidentifikasi oleh alamat IP mereka selama periode waktu yang lama. | <ul><li>Alamat IP yang diduga penipuan akan diblokir setiap hari berdasarkan data terkini yang diterima dari penyedia global pihak ketiga,  <Anchor target="_blank" href="http://www.digitalelement.com/">Elemen Digital</Anchor> .</li><li>Perlindungan daftar blokir IP diaktifkan untuk semua aplikasi.</li></ul> |
| <span id="sdk-authentication"></span>**Autentikasi SDK** | Para pelaku kecurangan mengirimkan pesan SDK palsu untuk menstimulasi tindakan user yang bernilai. | <ul><li>Protokol hashing dengan hak milik digunakan untuk mengenkripsi pesan antara SDK dan layanan web, mencegah penipu meniru pesan tersebut.</li><li>Perlindungan autentikasi SDK diaktifkan untuk semua aplikasi.</li></ul> |
| <span id="store-validations"></span>**Validasi store** | Penipu mengirim pesan SDK palsu untuk meniru instalasi atau in-app purchase sehingga mereka dapat mengklaim biaya CPA yang tinggi. <Anchor target="_blank" href="/marketers/id/docs/implement-apple-app-store-itunes-install-validation">Validasi Apple store</Anchor> . | Mengaktifkan <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/install-validation/">validasi instalasi</Anchor> di iTunes dan validasi pembelian dalam aplikasi untuk iTunes dan Google Play, dari instalasi atau pembelian in-app apa pun yang telah terjadi untuk mencegah atribusi aktivitas penipuan. |

**Catatan**: Nilai waktu persis yang dikutip di atas tidak diungkap untuk melindungi klien kami.

Alasan pemblokiran tambahan dijelaskan di <Anchor target="_blank" href="/marketers/id/docs/protect360-raw-data-reports">artikel data lengkap</Anchor>.

</Accordion>

Tabel di bawah ini menguraikan berbagai macam penginstalan dan in-app palsu, dan apa yang terjadi saat mesin Protect360 memblokir penipuan tersebut secara waktu aktual, atau mendeteksi penipuan pasca-atribusi.

<table><caption>Deteksi penipuan dan kegunaan Protect360</caption><thead><tr><th>Jenis penipuan</th><th>Waktu deteksi</th><th>Apa yang terjadi dengan penginstalan</th><th>Apa yang terjadi dengan in-app event</th></tr></thead><tbody><tr><td rowspan="2"><span>Penginstalan palsu</span></td><td><span>Waktu sebenarnya</span></td><td><span>Diblokir secara waktu aktual</span></td><td><span>Diblokir secara waktu aktual</span></td></tr><tr><td><span>Pasca-atribusi</span></td><td><span>Ditandai dalam laporan Penginstalan Setelah Atribusi</span></td><td><ul><li><span>In-app event yang terjadi sebelum deteksi penipuan akan ditandai dalam laporan In-app event Setelah Atribusi.</span></li><li><span>Setelah terdeteksi: diblokir secara waktu aktual</span></li></ul></td></tr><tr><td rowspan="2"><span>Instal pembajakan atribusi</span></td><td><span>Waktu sebenarnya</span></td><td><ul><li><span>Diblokir secara waktu aktual</span></li><li><span>Attribusi dikoreksi ke sumber valid terakhir</span></li></ul></td><td><ul><li><span>Muncul di laporan In-App Event yang Diblokir</span></li><li><span>Diatribusikan ke sumber valid yang sama dengan penginstalan</span></li></ul></td></tr><tr><td><span>Pasca-atribusi</span></td><td><span>Ditandai dalam laporan Penginstalan Setelah Atribusi</span></td><td><ul><li><span>In-app event yang terjadi sebelum deteksi penipuan akan ditandai dalam laporan In-app event Setelah Atribusi.</span></li><li><p>Setelah deteksi penipuan: ditandai dalam laporan In-App Event SetelahAtribusi hingga 30 hari sejak penginstalan.\*</p><p>\*In-app event diperbaiki sampai sumber media terakhir yang valid selama 30 hari sejak penginstalan. Event yang terjadi setelah 30 hari tidak diperbaiki.</p></li></ul></td></tr><tr><td rowspan="2"><span>Penipuan in-app event</span></td><td><span>Waktu sebenarnya</span></td><td>-</td><td><span>Diblokir secara waktu aktual</span></td></tr><tr><td><span>Pasca-atribusi</span></td><td>-</td><td><span>Ditandai dalam laporan In-App Event Setelah Atribusi</span></td></tr></tbody></table>

## Menggunakan Protect360

<div id="dashboard" />

<Accordion title="Dashboard">

<Anchor target="_blank" href="/marketers/id/docs/protect360-dashboard">Dashboard Protect360</Anchor> menampilkan data kecurangan gabungan dan memberikan wawasan yang berkaitan dengan lalu lintas kecurangan.

Tampilan dashboard:

**Penginstalan**: Wawasan<Anchor target="_blank" href="/marketers/id/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">berbasis LTV</Anchor> tentang penipuan penginstalan yang diblokir secara waktu aktual dan teridentifikasi pasca-atribusi. Anda dapat menelusuri lebih lanjut untuk menyelidiki event penipuan dengan menggunakan opsi pemfilteran dan pengelompokan.

**In-app event**: Wawasan <Anchor target="_blank" href="/marketers/id/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">berbasis aktivitas</Anchor> tentang penipuan in-app event yang diblokir secara waktu aktual dan teridentifikasi pasca-atribusi. Anda dapat menelusuri lebih lanjut untuk menyelidiki event penipuan dengan menggunakan opsi pemfilteran dan pengelompokan.

**Anomali**: Informasi tentang sumber media yang memiliki penginstalan dengan nilai click-through-to-install time (CTIT) yang tidak normal, jika dibandingkan dengan sumber tepercaya lainnya.

* Melakukan referensi silang antara instalasi yang dicurigai dengan data instalasi lengkap Anda dan mencari tanda-tanda yang mencurigakan seperti nomor versi aplikasi yang janggal, versi OS yang lama, lokasi yang tidak lazim, dll.
* Gunakan <Anchor target="_blank" href="/marketers/id/docs/implement-validation-rules-to-prevent-fraud#protect360-install-and-inapp-event-sources">Aturan validasi</Anchor> untuk memblokir instalasi dengan nilai CTIT yang pendek. Protect360 secara otomatis memblikir instalasi dengan nilai CTIT yang sangat pendek.

</Accordion>

<div id="raw-data" />

<Accordion title="Data Lengkap">

<Anchor target="_blank" href="/marketers/id/docs/protect360-raw-data-reports">Data lengkap</Anchor> tentang penipuan tersedia melalui Pull API, Export Data (Ekspor Data), dan <Anchor target="_blank" href="/marketers/id/docs/data-locker-for-marketers">Data Locker (fitur premium)</Anchor>.

Laporan data lengkap dibagi sebagai berikut:

* Laporan pemblokiran: Instalasi, klik, dan in-app event pengguna yang atribusinya diblokir dan sama sekali tidak diatribusikan ke media source apa pun.
* Laporan pasca atribusi:
  * Instalasi diatribusikan ke media source, tetapi kemudian terdeteksi sebagai penipuan.
  * In-App Event 
    * dari instalasi yang diidentifikasi sebagai penipuan setelah diatribusikan ke media source.
    * dianggap sebagai penipuan terlepas dari instalasi itu sendiri.

* Pengiklan menggunakan laporan ini untuk merekonsiliasi akun jaringan iklan, untuk pengoptimalan, dan untuk menyesuaikan dashboard atribusi untuk kecurangan pasca- atribusi.

</Accordion>

<div id="validation-rules" />

<Accordion title="Aturan Validasi">

<Anchor target="_blank" href="/marketers/id/docs/implement-validation-rules-to-prevent-fraud">Aturan Validasi</Anchor> memungkinkan pemilik aplikasi untuk menetapkan persyaratan untuk memblokir penginstalan tertentu, memblokir atribusi (dan memastikan bahwa penginstalan diatribusikan ke sumber media valid terbaru), atau memblokir in-app event.

</Accordion>

<div id="fraud-reconciliation-with-ad-networks" />

<Accordion title="Rekonsiliasi penipuan dengan jaringan iklan">

Dengan Protect360, para pengiklan mendapatkan data lengkap mengenai kecurangan penginstalan dan in-app event dimana jaringan iklan mungkin tidak dicatat sebagai kecurangan.

Jika Anda menemukan bahwa jaringan iklan mengirimkan Anda lalu lintas dari sumber-sumber yang mencurigakan, beritahukan jaringan iklan dan minta mereka untuk berhenti mengirimkan Anda lalu lintas dari sumber-sumber yang mencurigakan. Gunakan kolom laporan penginstalan data lengkap yang disebut **Attributed Touch Time (Waktu Sentuh Teratribusi)** untuk memverifikasi bahwa tidak ada lagi penginstalan yang diterima dari sumber setelah permintaan Anda untuk menghentikannya.

Anda juga dapat menggunakan data Protect360 untuk melakukan rekonsiliasi dengan jaringan iklan dan menerima pengembalian dana penuh atau sebagian untuk lalu lintas sebelumnya dari sumber yang mencurigakan.

**Untuk merekonsiliasi kampanye berbasis CPI menggunakan Protect360:**

* Pada awal setiap bulan, hubungi manajer akun di masing-masing jaringan periklanan tempat terjadinya kecurangan.
* Kumpulkan data lengkap instalasi palsu yang relevan dari laporan instalasi yang diblokir dan [laporaninstalasi pasca-atribusi](/docs/protect360-anti-fraud-guide#postattribution-detection) .
* Bagikan data lengkap kecurangan dengan jaringan untuk rekonsiliasi dan optimisasi lalu lintasnya.
* Anda dapat membuat laporan data lengkap yang hanya menyertakan penginstalan yang valid, tetapi mengecualikan kecurangan penginstalan pasca-atribusi. Untuk melakukannya, Anda harus mengunduh laporan bulanan ***Penginstalan UA yang diatribusikan*** dan mengecualikan semua entri dari laporan ***Penginstalan pasca-atribusi*** .

**Untuk merekonsiliasi kampanye berbasis CPA/CPE menggunakan Protect360:**

* Pada awal setiap bulan, hubungi manajer akun di masing-masing jaringan periklanan tempat terjadinya kecurangan.
* Kumpulkan data lengkap in-app event penipuan yang relevan dari laporan in-app event yang diblokir dan laporan[in-app event](/docs/protect360-anti-fraud-guide#postattribution-detection) pasca atribusi .
* Bagikan data lengkap kecurangan dengan jaringan untuk rekonsiliasi dan optimisasi lalu lintasnya.
* Anda dapat membuat laporan data lengkap yang hanya menyertakan IAE yang valid, tetapi mengecualikan event kecurangan pasca-atribusi. Untuk melakukannya, Anda harus mengunduh laporan bulanan ***In-app event UA yang diatribusikan*** dan mengecualikan semua entri dari laporan ***In-app event pasca-atribusi*** .

</Accordion>

## Karakteristik dan batasan

<div id="traits-and-limitations::a07033c3" />

<Accordion title="Karakteristik dan batasan">

| Sifat | Catatan |
| --- | --- |
| Akses pengiklan | Semua pengguna akun. |
| Akses jaringan iklan | <ul><li>Akses dashboard Protect360 dan data lengkap memerlukan <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#hak-akses-ad-network">izin pemasang iklan.</Anchor></li><li>Pemasang iklan harus memiliki jaringan iklan sebagai mitra terintegrasi.</li></ul> |
| Akses agensi | Akses dashboard Protect360 dan data lengkap memerlukan <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#hak-akses-ad-network">izin pemasang iklan.</Anchor> |
| Transparansi agensi | Agensi transparan: Dapat melihat sumber media tertentu<br /><br />Agensi non-transparan: Tidak dapat melihat sumber media tertentu |
| Zona waktu khusus aplikasi | <ul><li>Zona waktu khusus aplikasi digunakan di dashboard, asalkan semua aplikasi diatur pada zona waktu sama.</li><li>Jika aplikasi tidak diatur ke zona waktu yang sama, maka default dashboard ke UTC.</li></ul> |
| Kesegaran data | <ul><li>Dashboard Protect360: Diperbarui <Anchor target="_blank" href="/marketers/id/docs/about-data-freshness-and-timezone-support#eod">Setiap hari</Anchor> .<br />Waktu pembaruan terkini , ditampilkan di bawah filter rentang tanggal di Dashboard.</li><li>Laporan:<ul><li>Instalasi yang diblokir dan in-app event: Perbarui terus menerus hampir secara waktu aktual.</li><li>Pasca atribusi: <Anchor target="_blank" href="/marketers/id/docs/about-data-freshness-and-timezone-support#eod">Setiap hari</Anchor> menggunakan UTC.</li></ul></li></ul> |
| Install Ulang | Data penipuan untuk instalasi ulang hanya tersedia dalam data lengkap. Oleh karena itu, mungkin terdapat perbedaan antara angka keseluruhan di dashboard dan laporan data lengkap. |
| Retargeting | <ul><li>Untuk penginstalan yang teridentifikasi sebagai penipuan, perincian tipe sentuh yang diatribusikan antara penginstalan, atribusi ulang, dan interaksi ulang akan ditampilkan.</li><li>Untuk in-app event:<ul><li>Dashboard in-app event (CPA) menampilkan event penipuan dari penginstalan UA, namun bukan dari penargetan ulang.</li><li>Peristiwa penipuan dari atribusi ulang yang diidentifikasi dalam waktu aktual, dapat dilihat dalam laporan data lengkap. Event penipuan dari interaksi ulang tidak dapat diidentifikasi.</li><li>Event penipuan dari penargetan ulang tidak dapat diidentifikasi setelah atribusi.</li></ul></li></ul> |
| Batasan | <ul><li>Tabel dibatasi hingga maksimum 20.000 baris.</li><li>Jika Anda meminta pengaturan data yang lebih besar, beberapa sumber media mungkin akan dikeluarkan dari tabel tersebut. Untuk mengatasi batasan ini, kami menyarankan tindakan berikut:<ul><li>Mintalah dataset yang lebih kecil - rentang tanggal lebih kecil, app spesifik dan media source spesifik</li><li>Ekspor Protect360 <Anchor target="_blank" href="/marketers/id/docs/protect360-raw-data-reports">laporan data lengkap</Anchor></li><li>Ekspor Laporan Deteksi Lanjutan Teragregasi Protect360 <Anchor target="_blank" href="/marketers/id/docs/pull-api-aggregate-data">melalui Pull API</Anchor></li></ul></li></ul> |

</Accordion>

## Pertanyaan umum dan tips

<div id="faq" />

<Accordion title="Pertanyaan Umum">

| **Bagaimana cara menghitung widget ***Estimated savings (estimasi penghematan)?<br /><br />Untuk <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview">jaringan yang mendukung data biaya bersama</Anchor>, Anda akan mendapatkan estimasi penghematan yang akurat.<br /><br />Untuk jaringan yang tidak mendukung hal tersebut, AppsFlyer menggunakan eCPI rata-rata yang berasal dari seluruh grup penginstalan terverifikasi dari semua sumber yang memiliki data biaya. |
| --- |
| **Apakah Protect360 berfungsi melawan kecurangan yang berasal dari tautan atribusi khusus?**<br /><br />Tentu saja! Protect360 mendeteksi dan memblokir kecurangan yang berasal dari tautan atribusi khusus, selain jaringan iklan. Hal ini berarti Anda juga dilindungi jika Anda memiliki kampanye owned media, seperti dengan influencer, kampanye email dan SMS, spanduk situs web dan halaman arahan, posting viral di media sosial, notifikasi otomatis atau bahkan kode QR. |
| **Apa yang baru di Protect360 V2 dibandingkan dengan V1?**<ol><li>Ada 3 perubahan utama di P360 V2.0:<br />Penipuan Pasca-Atribusi - di mana pun kami menampilkan penginstalan terblokir. Pasca atribusi juga tersedia sebagai laporan data lengkap.</li><li>Anomaly Insights - Penambahan bagian baru yang disebut "Anomaly Insights", di mana pemasang iklan dapat menganalisis anomali melalui alat visualisasi. Bagian ini mengganti 2 grafik pada tab "Advanced Detection".</li><li>Sentralisasi semua data kecurangan - tab "advanced detection" dihapus dan kami menyajikan semua informasi dalam 1 tab.</li></ol> |
| **Mengapa data lengkap pasca-atribusi tidak tersedia di halaman Export Data?**<br /><br />Laporan pasca-atribusi berada di tingkat akun per sumber media, agar proses rekonsiliasi lebih mudah. Laman **Ekspor Data**berada di tingkat aplikasi tunggal, dan masih berisi Data kecurangan yang diblokir pada tingkat aplikasi, untuk kompabilitas mundur. |
| **Apakah data pasca-atribusi di-update secara retroaktif?**<ul><li>**Penginstalan** - Data penginstalan di laman ikhtisar dan semua laporan lainnya di luar dashboard Protect360 tidak diperbarui secara retroaktif.</li><li>**In-app event** - setelah lapisan perlindungan pasca-atribusi mengidentifikasi instalasi palsu, in-app event berikut yang berasal dari instalasi ini diblokir. In-app event  sebelumnya tidak diperbarui secara retroaktif.</li></ul> |
| **Mengapa data terlihat berbeda saat memilih jaringan tertentu/berbeda di wawasan Anomali?**<br /><br />Saat Anda melihat anomali CTIT dan memilih AF\_Baseline sebagai tolok ukur, Anda mungkin melihat anomali Jaringan A. Lalu, jika, misalnya, Anda memilih Jaringan A sebagai tolok ukur, Anda akan melihat anomali jaringan lain, namun tidak pada Jaringan A.<br /><br />Hasil ini sebenarnya adalah apa yang seharusnya Anda harapkan. Ketika baseline AppsFlyer yang tepercaya digunakan, jaringan dengan tingkat CTIT yang tidak normal akan ditampilkan. Ketika jaringan anomali digunakan sebagai baseline, instalasinya tidak lagi dikategorikan sebagai anomali, namun instalasi dari jaringan lain mungkin dianggap anomali relatif terhadap hal tersebut. |
| **Apakah lalu lintas organik yang abnormal sebenarnya kecurangan?**<br /><br />Mungkin saja lonjakan abnormal dalam lalu lintas organik sebenarnya kecurangan. Secara umum, jika Anda melihat lalu lintas organik di AppsFlyer, yang Anda yakini benar-benar kecurangan, itu bisa menjadi salah satu dari 3 kasus berikut:<ul><li>**Kecurangan atribusi gagal** - klik curang gagal menerima atribusi, misalnya, banjir klik dengan klik terakhir yang terjadi di luar klik jendela lookback.</li><li>**Kecurangan non-atribusi:** Pengguna melakukan kecurangan yang tidak terkait atribusi, misalnya melakukan kecurangan untuk mengumpulkan item dalam permainan strategi.</li><li>**Masalah integrasi SDK:** Periksa apakah in-app event dikirim dengan benar, yaitu pada waktu yang tepat dalam alur dan dengan nilai paramater event yang tepat.</li></ul> |

</Accordion>

<div id="benchmarks-and-tips" />

<Accordion title="Benchmarks dan tips">

| **Mendeteksi kecurangan device baru**<br /><br />Penipu dapat menyamarkan perangkat mereka dengan sering mengatur ulang ID utama perangkat mereka, yaitu. IDFA untuk iOS dan GAID untuk Android.<br /><br />Untungnya, AppsFlyer mengidentifikasi lebih dari 98%  perangkat mobile secara global.<br /><br />Oleh karena itu, persentase tinggi device baru yang tidak dikenal adalah indikasi kuat kecurangan menggunakan pabrik klik, kecuali dengan sengaja menargetkan device baru.<br /><br />**Mendeteksi device baru**<ol><li>Di Protect360, buka tabel ***Identified fraud breakdown (rincian penipuan teridentifikasi)***.</li><li>Gulir ke kanan ke kolom ***Indikator device farm - perangkat baru*** .</li><li>Klik pada nama kolom ***Installs %*** untuk mengurutkan tabel dalam urutan menurun dari rasio perangkat baru.</li><li>Indikator kecurangan perangkat baru:</li></ol><ul><li>Sumber-sumber dengan persentase  **perangkat** baru yang tinggi. **Catatan**: Saat jumlah penginstalan meningkat, persentase yang lebih rendah juga dapat dianggap sebagai kecurangan (karena jumlah keseluruhannya besar).<ul><li>Jika rasio pengguna setia sumber dibandingkan dengan rasio pengguna setia secara keseluruhan, persentase yang relatif rendah merupakan indikasi kecurangan yang kuat.</li></ul></li></ul>**Catatan**: Kampanye <Anchor target="_blank" href="/marketers/id/docs/appsflyer-factory-preinstall-using-manifest-android">aplikasi pra-penginstalan</Anchor> biasanya memiliki tingkat perangkat baru yang sangat tinggi, karena ini mungkin menjadi aplikasi paling pertama yang diluncurkan pengguna saat mengaktifkan perangkat baru mereka. Oleh sebab itu, untuk aplikasi pra-penginstalan, penipuan perangkat baru jarang terjadi, meskipun dengan tingkat perangkat baru yang tinggi. |
| --- |
| **Mendeteksi kecurangan LAT**<br /><br />Pengguna LAT (Pengukuran Iklan Terbatas) memilih untuk tidak mengekspos ID, IDFA atau GAID perangkat mereka kepada pemasang iklan. Sekitar 15% dari pengguna iOS dan 10% dari pengguna Android mengambil pilihan ini.<br /><br />Sama halnya dengan peringkat perangkat baru, pengguna LAT mungkin adalah pengguna yang sah. Namun, persentase yang tinggi dapat mengindikasikan aktivitas kecurangan.<br /><br />**Mendeteksi LAT:**<ol><li>Di Protect360, buka tabel ***Identified fraud breakdown (rincian penipuan teridentifikasi)***.</li><li>Gulir ke kanan ke kolom ***Indikator device farm - perangkat baru*** .</li><li>Klik pada nama kolom ***Instal %*** untuk mengurutkan tabel dalam urutan menurun dari rasio perangkat baru.</li><li>Indikator kecurangan perangkat LAT:</li></ol><ul><li>Sumber-sumber dengan persentase perangkat **LAT** yang tinggi. **Catatan**: Saat jumlah penginstalan meningkat, persentase yang lebih rendah juga dapat dianggap sebagai penipuan (karena jumlah keseluruhannya besar).</li><li>Jika rasio pengguna setia sumber dibandingkan dengan rasio pengguna setia secara keseluruhan, persentase yang relatif rendah merupakan indikasi kecurangan yang kuat.</li></ul> |
| **Mendeteksi kecurangan click flooding**<ol><li>Menggunakan click flooding, penipu mengirimkan jutaan klik dengan ID perangkat asli, dengan harapan terdaftar sebagai klik terakhir untuk pengguna sebenarnya. Sumber dengan jenis penipuan ini memiliki **rasio konversi yang sangat rendah, tetapi pengguna berkualitas tinggi**, karena ini adalah pengguna sebenarnya.</li></ol>**Mendeteksi banjir klik:**<ol><li>Di Protect360, buka tabel ***Identified fraud breakdown (rincian penipuan teridentifikasi)***.</li><li>Gulir ke kanan ke kolom ***Indikator click flooding*** .</li><li>Klik pada nama kolom ***Conversion rate (Rasio konversi)*** untuk mengurutkan tabel dalam urutan menaik dari rasio konversi.</li><li>Benchmark kecurangan click flooding:</li></ol><ul><li>***Tingkat Konversi*** normal adalah antara 0.5% to 35%.<br />Mencurigai sumber yang rasio konversinya sangat rendah, atau yang **memiliki 25% atau kurang dari rasio konversi rata-rata** aplikasi. Anda dapat menemukan KPI ini di tabel laporan kinerja Gabungan di laman ikhtisar dashboard.</li><li>Untuk sumber ambang (borderline), bandingkan ***Assist %*** dengan rasio assist rata-rata. Anda dapat melihat rasio assist normal di assist widget, di laman ikhtisar dashboard.<br />Sumber yang rasio assist-nya **50% lebih tinggi dari rasio assist rata-rata** aplikasi itu dianggap mencurigakan.<br />Perhatikan bahwa semakin banyak sumber yang digunakan suatu aplikasi, semakin tinggi pula tingkat Kontribusinya.</li></ul> |
| **Mendeteksi click flooding dengan indikator CTIT**<br /><br />Indikasi lain dari banjir klik adalah **distribusi CTIT yang merata**.<br />Biasanya, sekitar 70% dari penginstalan normal itu terjadi dalam 1 jam sejak interaksi iklan.<br />Dengan banjir klik, tidak ada kaitan antara interaksi palsu dan penginstalan aktual. Ini menyebabkan lebih dari 30% penginstalan palsu, yang memiliki lebih dari 1 jam CTIT.<br /><br />**Mendeteksi indikasi banjir klik CTIT:**<ol><li>Di Protect360, buka tabel ***Identified fraud breakdown (rincian penipuan teridentifikasi)***.</li><li>Gulir ke kanan ke kolom ***Indikator click flooding*** ***- CTIT*** .</li><li>Benchmark click flooding CTIT:</li></ol><ul><li>Biasanya, ***Selama 60 menit*** nilainya harus sekitar 30%. Curigai sumber yang memiliki nilai lebih dari 50% dengan metrik ini.</li><li>Biasanya, ***Selama 5 jam*** nilainya harus sekitar 20%. Curigai sumber yang memiliki nilai lebih dari 40% dengan metrik ini.</li></ul>Gunakan laman ***Anomaly insights (tinjauan anomali)***  untuk menyelidiki sumber dengan CTIT yang mencurigakan. |

</Accordion>

<div id="advanced-antifraud-tips" />

<Accordion title="Tips anti-kecurangan tingkat lanjut">

| **Jumlah Install**<br /><br />Memfilter berdasarkan jumlah install per sumber yang diperiksa adalah langkah penting untuk mendeteksi sumber kecurangan terbesar. Selain itu, jumlah install yang rendah mungkin tidak signifikan secara matematis. Catatan:<br /><br />**Catatan**: Sumber dengan penginstalan kurang dari 30, atau bahkan 50, tidak cukup signifikan untuk disimpulkan. Perluas rentang tanggal atau kriteria pencarian lain untuk mendapatkan hasil yang lebih signifikan. |
| --- |
| **Ubah definisi pengguna setia (loyal user)**<br /><br />Definisi default dari Pengguna Setia (Loyal users) adalah 3 peluncuran aplikasi atau lebih. Ini KPI yang penting untuk interaksi pengguna, tetapi sayangnya banyak penipu mengetahuinya dan menggunakannya untuk memalsukan jumlah pengguna setia yang banyak, kemudian menghindari kecurigaan. Hindari penipuan dengan membuat dan memilih definisi pengguna setia yang lebih baik dan lebih terperinci.<br /><br />Analisis KPI kualitas pengguna aplikasi  seperti pendaftaran, penyelesaian tutorial, pembelian, multi sesi. Dalam kode aplikasi, kirim in-app event **pengguna setia** jika pengguna melakukan SEMUA daftar KPI.<br /><br />Setelah event non-organik pertama **pengguna setia** dikirimkan, buka **Pengaturan Aplikasi** dan pilih untuk mengindikasikan pengguna setia untuk aplikasi Anda. Diperkirakan tingkat pengguna setia sedikit menurun lalu kemudian turun drastis untuk sumber penipuan. |

</Accordion>

> 👍 **Tips**
>
> Ingin memahami lebih banyak mengenai perlindungan dari penipuan? Lihat <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7809/play/18635/mobile-app-fraud-and-protect360">kursus singkat dan informatif ini di Portal Pembelajaran AppsFlyer</Anchor>.

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/protect360-raw-data-reports">Data Lengkap</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/marketers-guide-mobile-ad-fraud/">Panduan pengantar bagi pemasar tentang penipuan iklan seluler</Anchor>

<div data-zendesk-anchors="protect360-overview=ikhtisar-protect360 h_01HE7RSPPQ4T5J3W038EZRCTCE=ikhtisar-protect360 h_01HE7RSPPQ5BH7HBK0R8SY1T16=realtime-blocking h_01HE7RSPPRW4CQ3GB9ZEYAA6YN=postattribution-detection h_01HE7RSPPRYMQKJH46JET2ZZ0T=common-fraud-issues-and-solutions using-protect360=menggunakan-protect360 h_01HE7RSPPR8Y8J1VJJXXDCAZE6=menggunakan-protect360 h_01HE7RSPPR04G3SCSYHSWJKQDG=dashboard h_01HE7RSPPRS6PSTZCR5RT4A5ND=raw-data h_01HE7RSPPR8C9MHRAGJXYD2VVZ=validation-rules h_01HE7RSPPR1PQ2R6NJPRQGS1K1=fraud-reconciliation-with-ad-networks traits-and-limitations=karakteristik-dan-batasan h_01HE7RSPPRV797PS12NFQHX1X5=karakteristik-dan-batasan h_01HE7RSPPRWRKR1Y25PZV2RMVV=traits-and-limitations::a07033c3 faq-and-tips=pertanyaan-umum-dan-tips h_01HE7RSPPSV2TT8SMK8JZXFKMC=pertanyaan-umum-dan-tips h_01HE7RSPPS01J796008HDS1CRW=faq h_01HE7RSPPS018W98JWZGED54W8=benchmarks-and-tips h_01HE7RSPPSEDZWRH929DBSWEWM=advanced-antifraud-tips h_01HE7RSPPSY161MSQVQW7M767F=tips h_01HE7RX6167Q5QP5JNZDSXCCK5=lihat-juga" />
