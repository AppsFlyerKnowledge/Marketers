---
title: Dashboard Protect360
metadata:
  keywords:
    - dashboard
    - Advertisers
    - Protect360
    - protect 360
    - '360'
    - P360
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-08-11T09:58:07Z'
  edited_at: '2023-11-28T04:51:38Z'
  id: 360011793077
  locale: id
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/id/articles/360011793077
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Sekilas**: Dashboard Protect360 memberikan wawasan tentang lalu lintas penipuan dan penginstalan yang diblokir karena penerapan aturan validasi.

[![p360_dashboard_main.png](https://support.appsflyer.com/hc/article_attachments/5218491552273)](https://support.appsflyer.com/hc/article_attachments/5218491552273)

## Tentang dashboard Protect360

Dashboard Protect360:

* Menampilkan data penipuan gabungan di tingkat akun.
* Memiliki tiga tampilan dashboard:
  * Penginstalan (CPI)
  * In-app event (CPA)
  * Anomali
* Mengatur penipuan berdasarkan kategori, termasuk:
  * Penginstalan palsu versus bajakan
  * Penipuan diblokir secara real-time versus penipuan yang teridentifikasi setelah atribusi
  * Penipuan dari UA versus kampanye penargetan ulang
* Memungkinkan Anda menelusuri untuk memeriksa lebih lanjut event penipuan dengan menggunakan opsi pemfilteran dan pengelompokan.

Untuk melihat dashboard Protect360, di  AppsFlyer, buka **Dashboard** > **Protect360.** 

<div id="filters-and-groupings" />

<Accordion title="Penyaringan dan pengelompokan">

**Jendela penyaringan dan pengelompokan**

[![p360_filters_2.png](https://files.readme.io/9fd2afbbfc1bdf671ae0427d75c1020085b36da724e40dcfe57da27943e15b0c-4408431325969.png)](https://files.readme.io/9fd2afbbfc1bdf671ae0427d75c1020085b36da724e40dcfe57da27943e15b0c-4408431325969.png)

Tersedia opsi penyaringan dan pengelompokan berikut:

* Penyaringan dasar:
  * Nama aplikasi
  * Jenis sumber: Non-organik dan/atau organik
  * Media Source
  * Geo
  * Rentang tanggal (<Anchor target="_blank" href="/marketers/id/docs/about-data-freshness-and-timezone-support#protect360-dashboard">lihat zona waktu yang tersedia</Anchor>)
  * Jenis atribusi: Penginstalan, atribusi ulang, dan/atau interaksi ulang
  * [Event yang harus dibayar](/docs/protect360-dashboard#payable-events) (tersedia di dashboard in-app)
* Penyaringan yang diperluas, klik panah biru, di sebelah kanan pemilih tanggal:
  * Agensi
  * Kampanye
  * Kanal
* Opsi pengelompokan, pilih dimensi yang berbeda untuk mengelompokan data kecurangan dengan cara mendapatkan wawasan spesifik yang Anda perlukan:
  * **Aplikasi:** Bandingkan jumlah total penipuan untuk setiap aplikasi Anda.
  * **Sumber Media** (default): Bandingkan penipuan yang teridentifikasi dari setiap sumber media yang digunakan oleh aplikasi Anda
  * **Sumber Media + Kampanye**: Bandingkan penipuan yang teridentifikasi dari semua kampanye Anda di semua sumber media yang digunakan oleh aplikasi Anda
  * **Sumber Media + ID Situs**: Bandingkan penipuan yang teridentifikasi dari semua penerbit (ID situs) di semua sumber media yang digunakan oleh aplikasi Anda
  * **Sumber Media + ID Situs + Kampanye**: Bandingkan penipuan yang teridentifikasi dari semua penerbit (ID situs) di semua sumber media yang digunakan oleh aplikasi Anda, yang terkait dengan nama kampanye yang relevan
  * **Sumber media + Geo**: (tersedia di dashboard in-app event): bandingkan penipuan yang teridentifikasi dari masing-masing sumber media yang digunakan oleh aplikasi Anda, yang terhubung dengan negara terkait
  * **Sumber media + Jenis atribusi**: Bandingkan penipuan yang teridentifikasi dari setiap sumber media Anda, terkait dengan jenis atribusi yang dipilih (penginstalan, atribusi ulang, dan/atau interaksi ulang)
  * **Geo**: membandingkan penipuan yang teridentifikasi dari semua negara

</Accordion>

## Dashboard instalasi

Dashboard penginstalan menampilkan data berbasis LTV, yang berarti data terkait penginstalan, atribusi ulang, dan interaksi ulang yang terjadi selama rentang tanggal yang Anda pilih.

Fitur dashboard dijelaskan di bagian selanjutnya.

<div id="installs-headline-metrics" />

<Accordion title="Penginstalan — metrik headline">

Metrik headline memungkinkan Anda untuk melihat:

* Estimasi penghematan
* Jumlah total penginstalan palsu,
* Jumlah (in-app) event palsu
* Anomali

Untuk setiap KPI terdapat nilai persentasenya. Nilai ini menunjukkan bagaimana KPI yang disajikan terkait dengan rentang tanggal paralel sebelumnya. Misalnya, minggu ini dibandingkan dengan minggu lalu, atau hari apa pun yang dipilih dalam rentang tanggal dibandingkan dengan jumlah hari yang sama sebelumnya: jika ini menunjukkan peningkatan estimasi penghematan sebesar X%, berarti rentang tanggal paralel sebelumnya memiliki X% lebih sedikit penginstalan, atribusi ulang, dan interaksi ulangpalsu.

**Estimasi penghematan**

[![](https://support.appsflyer.com/hc/article_attachments/4403139246993)](https://support.appsflyer.com/hc/article_attachments/4403139246993)

Estimasi metrik penghematan:

* Menampilkan nilai penipuan yang diblokir dalam waktu aktual atau pasca-atribusi teridentifikasi, untuk diselesaikan oleh Anda dengan jaringan iklan.
* Menggunakan rumus: Perkiraan Penghematan = jumlah penginstalan yang diblokir X eCPI rata-rata aplikasi.
* Tidak relevan untuk trafik organik.

Untu detail selengkapnya tentang bagaimana jumlah ini dihitung, baca <Anchor target="_blank" href="/marketers/id/docs/protect360-anti-fraud-guide#faq">FAQ</Anchor> berikut.

**Atribusi palsu yang teridentifikasi**

[![](https://files.readme.io/262403803bd074e4742f63d7998d4642e3b17781e178ed3bc24b35dd958ca262-4408437121297.png)](https://files.readme.io/262403803bd074e4742f63d7998d4642e3b17781e178ed3bc24b35dd958ca262-4408437121297.png)

Total metrik penipuan yang teridentifikasi menampilkan jumlah:

* Penginstalan, atribusi ulang, dan interaksi ulang palsu diblokir secara real-time karena berbagai alasan pemblokiran penipuan.
* Penginstalan, atribusi ulang, dan interaksi ulang diidentifikasi sebagai penipuan setelah atribusi.

**In-app event yang diblokir**

[![](https://files.readme.io/ed6692be83cae6a6bee556e5c763d6313c0d32cb577a9587caac41c54b51b378-4403139249809.png)](https://files.readme.io/ed6692be83cae6a6bee556e5c763d6313c0d32cb577a9587caac41c54b51b378-4403139249809.png)

Metrik in-app event yang diblokir menampilkan jumlah in-app event yang diblokir oleh AppsFlyer. Event tersebut mungkin telah diblokir karena menjadi bagian dari penginstalan yang diblokir, atau karena ditandai sebagai event pasca-atribusi yang mencurigakan.

</Accordion>

<div id="installs-charts" />

<Accordion title="Bagan — p enginstalan">

#### Grafik tren penipuan yang teridentifikasi

Diagram tren penipuan yang teridentifikasi menampilkan jumlah penginstalan, atribusi ulang, dan interaksi ulang palsu per hari, yang dikelompokkan berdasarkan:

* **Jenis deteksi**: Penginstalan diblokir secara real-time dan penginstalan diidentifikasi sebagai penipuan setelah atribusi.
* **Jenis atribusi**: Penginstalan, atribusi ulang, dan interaksi ulang
* **Jenis sumber**: Non-organik dan organik

Tampilannya dapat berupa grafik garis atau diagram batang.

#### Bagan koreksi atribusi penginstalan yang dibajak

Bagan koreksi atribusi penginstalan yang dibajak menampilkan sumber media yang berupaya mengambil kredit atas penginstalan, atribusi ulang, dan interaksi ulang, serta sumber kontributor terakhir yang valid.

Anda dapat:

* Filter berdasarkan atribusi yang dibajak yang diidentifikasi secara real-time, setelah atribusi, atau atribusi yang diidentifikasi melalui aturan validasi.
* Setel ke atribusi sumber yang valid mana yang dikoreksi atau dari mana atribusi sumber yang dibajak itu dikoreksi.
* Ubah tampilan bagan ke format tabel dan unduh data sebagai CSV.

**Catatan:**

* Bagan ini hanya dapat diakses oleh pemasang iklan. Agensi dan jaringan iklan tidak memiliki akses.
* Saat pembajakan diblokir secara real-time, atribusi yang benar akan ditampilkan di dashboard dan laporan AppsFlyer (bukan hanya Protect360). Ketika pembajakan teridentifikasi setelah atribusi, atribusi yang benar hanya ditampilkan di data lengkap Protect360.
* Bagan ini dapat menampilkan koreksi **ke** organik, tetapi tidak **dari** organik.

#### Bagan penipuan yang teridentifikasi

Bagan penipuan yang teridentifikasi menampilkan jenis penipuan yang Anda alami, berdasarkan persentase. Perincian penipuan dapat dilakukan dengan:

* Alasan pemblokiran
* Sub alasan pemblokiran
* Media Source
* Kampanye
* Geo
* Aplikasi

</Accordion>

<div id="installs-table" />

<Accordion title="Penginstalan—tabel">

#### Perincian penipuan yang teridentifikasi

Tabel **perincian penipuan yang teridentifikasi** menampilkan data berikut:

* Kecurangan yang diblokir secara waktu aktual
* Kecurangan teridentifikasi dan ditandai pasca-atribusi
* Indikasi lain dari kecurangan per sumber media

Tabel tersebut disajikan dalam format gambaran umum, seperti yang ditunjukkan pada gambar berikut.

[![p360_main_table.png](https://files.readme.io/15885268068f2b57e9b22b7028a824951690e737a47cb154cd38d1ddf79937b8-4408431449745.png)](https://files.readme.io/15885268068f2b57e9b22b7028a824951690e737a47cb154cd38d1ddf79937b8-4408431449745.png)

Struktur tabel dinamis:

* Memungkinkan Anda mengklik tombol pengaturan tabel untuk menambah atau menghapus kolom ke tabel.  
  Jika Anda melakukan perubahan apa pun pada tabel, pastikan untuk mengklik tombol **Simpan** setelahnya.
* Adalah per pengguna, sehingga setiap pengguna akun dengan akses ke Protect360 dapat secara pribadi menyesuaikan struktur tabel mereka sendiri. Lihat [opsi tabel lainnya](/docs/protect360-dashboard#opsi-tabel-tambahan) .

[![edit_table.jpg](https://files.readme.io/fcde2bc6970c29902dd7585ee92c2bc38edf1d5c56e65de4e3f10df784108e5c-360011641617.jpg)](https://files.readme.io/fcde2bc6970c29902dd7585ee92c2bc38edf1d5c56e65de4e3f10df784108e5c-360011641617.jpg)

#### Konten tabel rincian kecurangan yang teridentifikasi

| Kolom Tabel | Deskripsi |
| --- | --- |
| Grouping | <ul><li>[Default] Tabel dan dashboard dikelompokkan berdasarkan Sumber Media.</li><li>Saat memilih sumber media tertentu, pengelompokkan secara otomatis oleh sumber Media dan ID Situs.</li><li>Pengelompokan opsional termasuk Kampanye, GEO, Saluran, Agensi, Agensi + Sumber Media, dan kombinasinya.</li><li>Jika Anda memilih pengelompokan dengan dimensi yang hanya berlaku untuk lalu lintas non-organik, tabel akan menampilkan T/A untuk sumber media organik.</li></ul> |
| **Atribusi** | **Rincian utama dari kecurangan instalasi yang diblokir dan pasca atribusi.** |
| Total (A) | <ul><li>Total penginstalan = Penginstalan reguler (non-kecurangan) + penginstalan yang diblokir</li><li>Penginstalan reguler  tersedia per sumber media (non-organik) di dashboard Ikhtisar.</li></ul> |
| Diblokir (B) | <ul><li>Jumlah total penginstalan yang diblokir.</li><li>[Default] Tabel diurutkan menurun menggunakan KPI ini.</li></ul> |
| Diblokir % (B/A) | Instalasi yang diblokir / Total instalasi |
| Pasca-atribusi (C) | Penginstalan diidentifikasi sebagai penipuan pasca-atribusi. |
| Pasca-atribusi % (C/A) | Install pasca-atribusi / total jumlah install |
| Total kecurangan instalasi (D) | Semua instalasi kecurangan, diblokir secara waktu aktual atau diidentifikasi sebagai kecurangan pasca-atribusi. |
| Instalasi kecurangan % (D/A) | Instalasi kecurangan / Jumlah total instalasi |
| **Perincian jenis atribusi penipuan** | **Jenis atribusi dari penginstalan palsu, dibagi menjadi penginstalan, atribusi ulang, dan interaksi ulang.** |
| Install | Penipuan berawal dari kampanye UA. |
| Re-attribution (Atribusi ulang) | Penipuan berasal dari kampanye penargetan ulang yang berujung pada penginstalan. |
| Interaksi ulang | Penipuan berasal dari kampanye penargetan ulang yang mengarah pada interaksi ulang. |
| **Palsu** | **Penginstalan palsu atau atribusi ulang yang menyimulasikan aktivitas pengguna sebenarnya - dibagi berdasarkan blok real-time dan setelah atribusi.** |
| Pemblokiran waktu aktual | Instalasi palsu diblokir secara waktu aktual. |
| Kecurangan pasca-atribusi | Instalasi palsu diidentifikasi sebagai kecurangan pasca-atribusi. |
| **Dibajak** | **Kecurangan klik terakhir mencuri atribusi instalasi pengguna aktual, dibagi berdasarkan pemblokiran waktu aktual dan pasca-atribusi.** |
| Pemblokiran waktu aktual | Instalasi yang diretas dibloikir secara waktu aktual. |
| Kecurangan pasca-atribusi | Instalasi yang diretas diidentifikasi sebagai kecurangan pasca-atribusi. |
| **Aturan Validasi** | **Penginstalan memenuhi persyaratan aturan validasi.** |
| Instalasi yang diblokir | Penginstalan diblokir oleh aturan validasi. |
| Atribusi yang diblokir | Perubahan atribusi dari penginstalan karena aturan validasi. |
| **Rincian instalasi palsu yang diblokir** | **Detail install palsu curang yang diblokir dan pasca-atribusi, biasanya dilakukan secara terprogram** |
| Daftar hitam ID situs yang diblokir | Instalasi diblokir karena Protect360 memasukkan IDSitus ke daftar hitam. |
| Daftar hitam ID situs pasca atribusi | Instalasi ditandai sebagai penipuan karena Protect360 pasca atribusi memasukkan IDSitus ke daftar hitam. |
| Bot yang diblokir | Upaya instalasi yang diblokir dilakukan oleh bot otomatis. |
| Bot pasca-atribusi | Instalasi ditandai sebagai kecurangan karena aktivitas bot otomatis yang teridentifikasi pasca-atribusi |
| Anomali perilaku yang diblokir | Instalasi diblokir karena anomali perilaku, makna, sesi abnormal dan kinerja in-app event pengguna. |
| Anomali perilaku pasca-atribusi | Instalasi ditandai sebagai kecurangan karena anomali perilaku pasca-atribusi. |
| Validasi install yang diblokir | Total instalasi yang diblokir karena validasi store negatif. |
| **Detail pemblokiran install yang dibajak** | **Rincian kecurangan klik terakhir yang bertujuan untuk mencuri atribusi instalasi aplikasi pengguna sebenarnya** |
| Pembajakan install diblokir | Pembajakan instalasi sumber yang diblokir. |
| Pembajakan install pasca-atribusi | Pembajakan instalasi ditandai sebagai kecurangan di pasca-atribusi. |
| Anomali CTIT yang diblokir | Instalasi diblokir karena anomali CTIT. |
| Anomali CTIT pasca-atribusi | Anomali CTIT ditandai sebagai kecurangan di pasca-atribusi. |
| Click flooding yang diblokir | Instalasi diblokir karena banjir klik (upaya kecurangan untuk mengirimkan klik dalam jumlah besar yang diharapkan memberikan klik terakhir sebelum instalasi acak.) |
| Click flooding pasca-atribusi | Instalasi banjir klik ditandai sebagai kecurangan di pasca-atribusi. |
| **Klik** | **Klik dari sumber**<br /><br />**Catatan:** Semua jenis atribusi harus dipilih di bilah filter agar data klik dapat ditampilkan di tabel (jika tidak maka akan ditampilkan sebagai T/A). Pastikan untuk menyesuaikan pilihan filter Anda. |
| Total (E) | Jumlah total klik yang sah dan palsu yang diterima dari sumbernya |
| Diblokir | Klik diblokir karena penipuan (termasuk pembatasan) |
| Pembatasan | Klik diblokir karena pembatasan klik |
| **Tayangan** | **Tayangan dari sumber**<br /><br />**Catatan:** Semua jenis atribusi harus dipilih di bilah filter agar data impresi dapat ditampilkan di tabel (jika tidak, data tersebut akan ditampilkan sebagai T/A). Pastikan untuk menyesuaikan pilihan filter Anda. |
| Total | Jumlah total tayangan sah dan penipuan yang diterima dari sumber |
| Diblokir | Tayangan diblokir karena penipuan (termasuk pembatasan) |
| Pembatasan | Tayangan diblokir karena pembatasan tayangan |
| **In-App Event** | **In-app event dari sumbernya**<br /><br />**Catatan:** Ini termasuk in-app event dari penginstalan, bukan atribusi ulang atau interaksi ulang. |
| Total (G) | Total in-app event |
| Diblokir (H) | In-app event yang diblokir |
| % (H/G) | In-app event yang diblokir / total in-app event |
| **Indikator farm perangkat** | **Indikator aktivitas penipuan farm perangkat, menggunakan Reset ID Perangkat dan penipuan Pelacakan Iklan Terbatas (LAT).**<br /><br />**Catatan:** Ini termasuk penginstalan dan atribusi ulang, bukan interaksi ulang. |
| Instalasi (I) | Instalasi berisi ID perangkat baru yang tidak dikenal oleh AppsFlyer. |
| Instalasi % (I/A) | Instalasi perangkat baru / total jumlah instalasi |
| % Pengguna setia | KPI umum menunjukkan apakah apakah pengguna itu nyata atau palsu. |
| **Indikator click flooding** | **Indikasi penipuan banjir klik berdasarkan tingkat konversi atau bantuan yang tidak normal, atau waktu CTIT.** |
| Tingkat konversi (%) | Persentase rendah dibandingkan dengan rasio konversi app mengindikasikan kecurangan click flooding<br /><br />**Catatan**: Semua jenis atribusi harus dipilih di bilah filter agar data tingkat konversi dapat ditampilkan di tabel (jika tidak maka akan ditampilkan sebagai T/A). Pastikan untuk menyesuaikan pilihan filter Anda. |
| % Assist | Persentase tinggi dibandingkan dengan media source lainnya (di widget Assists di halaman overview) mengindikasikan kecurangan click flooding |
| CTIT > Lebih dari 60 menit | Penginstalan, atribusi ulang, dan interaksi ulang dengan waktu antara klik dan peluncuran aplikasi pertama lebih dari 60 menit. Penghitungan hanya mencakup penginstalan yang CTIT-nya di bawah 25 jam (dan tidak semua penginstalan). Biasanya, sekitar 30% peluncuran aplikasi pertama terjadi lebih dari 60 menit setelah pengunduhan. |
| CTIT > Lebih dari 5 jam | Penginstalan, atribusi ulang, dan interaksi ulang dengan waktu antara klik dan peluncuran aplikasi pertama lebih dari 5 jam. Penghitungan hanya mencakup penginstalan yang CTIT-nya di bawah 25 jam (dan tidak semua penginstalan). Biasanya, sekitar 20% peluncuran aplikasi pertama terjadi lebih dari 5 jam setelah pengunduhan. |

#### Opsi tabel tambahan

* Klik tombol **Ekspor CSV** untuk mengunduh tabel ke desktop Anda dalam format CSV
* Klik ikon roda gigi (perkakas) untuk:
  * Mengubah urutan kolom tabel
  * Menambah atau menghapus kolom yang dijelaskan di atas
  * Tambahkan atau hapus **in-app event** aplikasi Anda yang baru-baru ini diblokir. Untuk setiap in-app event yang ditambahkan, kolom berikut akan ditampilkan:

| Kolom Tabel | Deskripsi |
| --- | --- |
| Penghitung Event (Total) | Jumlah event yang diblokir pada event spesifik |
| User Unik | Jumlah user unik di mana event spesifiknya diblokir |

Perhatikan bahwa rasio tidak umum dari KPI ini mana pun tidak selalu mengindikasikan penipuan, karena banyak event yang diblokir karena install pasca-atribusi yang curang.

Data in-app event di dashboard CPI berbasis LTV, artinya semua in-app event yang terkait dengan instal yang terjadi selama rentang tanggal yang ditentukan.

</Accordion>

## Dashboard in-app event

Dashboard in-app event menampilkan data berbasis aktivitas, artinya data terkait in-app event yang terjadi selama rentang tanggal yang Anda pilih, termasuk event dari penginstalan yang terjadi sebelum rentang tanggal tersebut.

Fitur dashboard dijelaskan di bagian selanjutnya.

<div id="inapp-events-headline-metrics" />

<Accordion title="In-app event — metrik headline">

[![](https://files.readme.io/ea33b3ddafc4265eb74b2e1070a77a6afbad429a1aeb20cd1579127f7e8ee605-360012501757.jpg)](https://files.readme.io/ea33b3ddafc4265eb74b2e1070a77a6afbad429a1aeb20cd1579127f7e8ee605-360012501757.jpg)

Metrik headline memungkinkan Anda untuk melihat:

* Estimasi penghematan
  * Hanya tersedia jika [**Event yang harus dibayar**](/docs/protect360-dashboard#payable-events) diaktifkan.
  * Berdasarkan event yang harus dibayar yang telah Anda konfigurasikan.
* Jumlah total IAE palsu yang teridentifikasi

</Accordion>

<div id="inapp-events-charts" />

<Accordion title="—B agan in-app">

#### **Grafik tren kecurangan dari waktu ke waktu**

Grafik tren penipuan dari waktu ke waktu menampilkan jumlah event per hari, dibagi menjadi:

* **Waktu aktual** : In-app event penipuan diblokir secara waktu aktual
* **Pasca-atribusi** : Event penipuan diidentifikasi pasca-atribusi
* **Non-penipuan**

#### **Penipuan IAE teratas menurut grafik sumber media**

Penipuan in-app event teratas menurut daftar sumber media berisi: 

* 5 sumber media dengan jumlah in-app event penipuan tertinggi dalam urutan menurun.
* Bagan batang untuk setiap bilah sumber media yang menampilkan jenis in-app event berikut sebagai persentase dari total in-app event:
  * **Waktu aktual** : In-app event penipuan diblokir secara waktu aktual
  * **Pasca-atribusi** : Event penipuan diidentifikasi pasca-atribusi
  * **Non-penipuan**

</Accordion>

<div id="inapp-events-table" />

<Accordion title="Tabel — in-app event">

Tabel **perincian penipuan in-app event** menampilkan data berikut:

* Kecurangan yang diblokir secara waktu aktual
* Kecurangan teridentifikasi dan ditandai pasca-atribusi
* Indikasi lain dari kecurangan per sumber media

Tabel tersebut disajikan dalam format gambaran umum, seperti yang ditunjukkan pada gambar berikut.

[![IAE_fraud_table.jpg](https://files.readme.io/dd57a2508911b3e26268ad8cc4508d5402fa091ac95a77900c7f257486c99aeb-360012839758.jpg)](https://files.readme.io/dd57a2508911b3e26268ad8cc4508d5402fa091ac95a77900c7f257486c99aeb-360012839758.jpg)

Struktur tabel dinamis:

* Memungkinkan Anda mengklik tombol pengaturan tabel untuk menambah atau menghapus kolom ke tabel.  
  Jika Anda melakukan perubahan apa pun pada tabel, pastikan untuk mengklik tombol **Simpan** setelahnya.
* Adalah per pengguna, sehingga setiap pengguna akun dengan akses ke Protect360 dapat secara pribadi menyesuaikan struktur tabel mereka sendiri. Lihat [opsi tabel lainnya](/docs/protect360-dashboard#installs-table) .

[![iae_table_structure.jpg](https://files.readme.io/5b2933e2b254d8fa268e30a72ae53691da391e365d781d55bcdb6cfeb1f40a6a-360012839778.jpg)](https://files.readme.io/5b2933e2b254d8fa268e30a72ae53691da391e365d781d55bcdb6cfeb1f40a6a-360012839778.jpg)

#### Konten tabel rincian penipuan in-app event

| Kolom Tabel | Deskripsi |
| --- | --- |
| Grouping | <ul><li>[Default] Tabel dan dashboard dikelompokkan berdasarkan Sumber Media.</li><li>Saat memilih sumber media tertentu, pengelompokkan secara otomatis oleh sumber Media dan ID Situs.</li><li>Pengelompokan opsional termasuk Kampanye, GEO, Saluran, Agensi, Agensi + Sumber Media, dan kombinasinya.</li></ul> |
| **In-App Event** | **Rincian headline IAE yang diblokir dan penipuan pasca-atribusi.** |
| Total IAE (A) | <ul><li>Total IAE = IAE (non-penipuan) reguler + IAE yang diblokir + IAE yang diidentifikasi sebagai penipuan pasca atribusi.</li><li>IAE reguler tersedia per sumber media (non-organik) di dashboard Ikhtisar.</li></ul> |
| Total IAE penipuan (B) | <ul><li>Jumlah total IAE + IAE yang diblokir yang diidentifikasi sebagai penipuan pasca atribusi.</li><li>[Default] Tabel diurutkan menurun menggunakan KPI ini.</li></ul> |
| Event penipuan % (B/A) | IAE Penipuan/IAE Total |
| **Pemblokiran waktu aktual IAE palsu** | **IAE palsu yang diblokir secara waktu aktual.** |
| IAE palsu | IAE palsu diidentifikasi sebagai penipuan dan diblokir secara waktu aktual. |
| Instalasi palsu | Penginstalan asli diidentifikasi sebagai penipuan dan diblokir secara waktu aktual. |
| Penginstalan palsu pasca atribusi | Penginstalan asli diidentifikasi sebagai penipuan pasca-atribusi, sebelum IAE. |
| **Disimpan dari pembajakan secara waktu aktual.** | **IAE dengan penginstalan asli yang dibajak oleh sumber penipuan, yang diatribusikan dengan benar oleh AppsFlyer ke sumber non-penipuan terakhir.** |
| Dikoreksi menjadi organik | Penginstalan yang dibajak dengan sumber non-penipuan terakhir adalah organik. |
| Dikoreksi menjadi sumber non-organik | Penginstalan yang dibajak dengan sumber non-penipuan terakhir adalah sumber media non-organik. |
| **Penipuan IAE pasca-atribusi** | **In-app event diidentifikasi sebagai penipuan pasca-atribusi.** |
| Instalasi palsu | IAE terjadi sebelum penginstalan diidentifikasi sebagai pasca-atribusi penipuan. |
| Instalasi yang dibajak | IAE terjadi sebelum penginstalan diidentifikasi sebagai dibajak, dan tidak dapat diatribusikan dengan benar setelah atribusi. |
| **Aturan Validasi** | **IAEs diblokir karena memenuhi ketentuan aturan validasi.** |
| Instalasi yang diblokir | IAE dari penginstala yang diblokir oleh aturan validasi. |
| IAE terblokir | IAEs yang diblokir oleh aturan validasi. |
| Dikoreksi menjadi organik | Penginstalan yang dibajak dengan sumber non-penipuan terakhir adalah organik. |
| Dikoreksi menjadi sumber non-organik | Penginstalan yang dibajak dengan sumber non-penipuan terakhir adalah sumber media non-organik. |

#### Opsi tabel tambahan

* Klik tombol **Ekspor CSV** untuk mengunduh tabel ke desktop Anda dalam format CSV
* Klik ikon roda gigi (perkakas) untuk:
  * Mengubah urutan kolom tabel
  * Menambah atau menghapus kolom yang dijelaskan di atas

Jumlah event yang ditampilkan berdasarkan aktivitas dan tidak berdasarkan LTV, yaitu jumlah pasti pemblokiran event selama rentang tanggal yang ditentukan.

</Accordion>

<div id="payable-events" />

<Accordion title="Event yang harus dibayar">

Event yang harus dibayar adalah IAE yang memiliki biaya. Setelah diaktifkan dan dikonfigurasi, dashboard aktivitas in-app hanya menampilkan data yang terkait dengan event yang harus dibayar.

**Untuk mengaktifkan event yang harus dibayar dalam dashboard aktivitas in-app** :

* Di bagian **Filter menurut** di dashboard Aktivitas in-app, aktifkan event yang harus dibayar.  

  [![](https://files.readme.io/8162f6f4f6dcef50fbe0fd998b7a95d20deeb658dd53bafc216b75df050c734c-360012576718.jpg)](https://files.readme.io/8162f6f4f6dcef50fbe0fd998b7a95d20deeb658dd53bafc216b75df050c734c-360012576718.jpg)

**Untuk mengonfigurasi event yang harus dibayar** :

1. Pada dashboard Aktivitas in-app, klik **Konfigurasi event yang harus dibayar** .  

   [![](https://files.readme.io/00b1f4506f0c7ec8e1e1b90c16cc2232d2862b231b2673d2decc7a90b6c6b6af-360012505217.jpg)](https://files.readme.io/00b1f4506f0c7ec8e1e1b90c16cc2232d2862b231b2673d2decc7a90b6c6b6af-360012505217.jpg)

   Tampilan pop-up event berbayar.

   [![](https://files.readme.io/4643b9d0e0042ca5860d21ec3eb3ff7e4178f92f1f4215db56adda10be41c452-360012580938.jpg)](https://files.readme.io/4643b9d0e0042ca5860d21ec3eb3ff7e4178f92f1f4215db56adda10be41c452-360012580938.jpg)
2. [Opsional] Jika Anda mengonfigurasi event berbayar baru, klik **Tambah baru** .
3. Berdasarkan IAE berbayar mana yang ingin Anda tampilkan di dashboard, pilih berikut ini dari menu drop-down:
   * Aplikasi
   * In-App Event
   * Media source
   * Kampanye
4. Masukkan CPA dari IAE.
5. Klik ***Save***.
6. Klik **Tutup.**

</Accordion>

## Dashboard anomali

Dashboard anomali:

* Memberikan tinjauan tentang sumber media yang memiliki nilai Jeda Waktu Klik hingga Penginstalan (Click to Install Time/CTIT) yang mencurigakan, atau rasio perangkat baru, jika dibandingkan dengan sumber media lain.
* Memungkinkan Anda menggunakan KPI tingkat sumber media untuk menerima kompensasi dari sumber media dan mempertimbangkan apakah akan terus bekerja sama dengan mereka atau tidak.
* Membutuhkan lalu-lintas dari sumber yang dipercaya AppsFlyer untuk meminimalkan tingkat kecurangan. Ini untuk membuat baseline guna membandingkan sumber media lainnya.

<div id="ctit-tab" />

<Accordion title="Tab CTIT">

[![Anomalies_CTIT.png](https://files.readme.io/630ff7b8c065a302f86b0c1f69c0d166d3ff28a2833ebde3e79494ba8b283f08-360011641657.png)](https://files.readme.io/630ff7b8c065a302f86b0c1f69c0d166d3ff28a2833ebde3e79494ba8b283f08-360011641657.png)

**Untuk menampilkan tinjauan CTIT** (angka merujuk pada tangkapan layar sebelumnya):

1. Buka **Anomali** > **CTIT** .
2. Pilih aplikasi di halaman yang ingin Anda lihat.
3. Pilih negara mana yang berkontribusi ke data di halaman.
4. Pilih rentang tanggal data di halaman.
5. Anda dapat melihat hingga 180 hari ke belakang.  
   **Catatan**: 180 hari dimulai pada tanggal 6 April, jadi hingga 180 hari berlalu sejak saat itu, tersedia kurang dari 180 hari.
6. Aktifkan **Kecualikan penipuan setelah atribusi** untuk melihat hanya penipuan yang diblokir, atau nonaktifkan untuk melihat wawasan penuh dari penipuan.
7. Pilih baseline media source yang akan dibandingkan. **Baseline App** default mempertimbangkan beragam sumber yang dipercaya oleh AppsFlyer, yang berkontribusi ke lalu lintas Anda.
8. Pilih resolusi waktu yang ditampilkan di grafik: detik, menit, jam, atau hari.
9. Sesuaikan aturan validasi ke <Anchor target="_blank" href="/marketers/id/docs/implement-validation-rules-to-prevent-fraud#protect360-install-and-inapp-event-sources">kecualikan penginstalan dengan CTIT tidak logis</Anchor>.  
   **Catatan**: fitur aturan validasi harus diaktifkan untuk akun Anda agar dapat melakukan ini.
10. Untuk melihat detail selengkapnya, arahkan pointer mouse ke atas bagian dengan warna berbeda pada grafik, yang mengindikasikan anomali CTIT yang terdeteksi.  
    **Catatan**: Hanya jaringan iklan yang datanya kami miliki dengan cukup untuk membuat perbandingan akurat yang ditampilkan.
11. Klik link **Protect 360** untuk kembali ke halaman Identified Fraud.

Tabel **CTIT anomalies breakdown** , di bagian bawah halaman, menampilkan semua media source yang memiliki anomali CTIT. Gunakan untuk melihat data tentang jumlah dan persentase install dengan nilai CTIT tidak normal. Dengan tabel ini Anda juga dapat mengekspor ke CSV, menambah dan menghapus kolom atau mengatur urutannya.

</Accordion>

<div id="new-devices-tab" />

<Accordion title="Tab perangkat baru">

[![anomalies_new_devices](https://files.readme.io/5bb108e61e0641cb16ba16720625dfbdf5446f979e6dddc80c9ec179104f5ec7-360011641677.png)](https://files.readme.io/5bb108e61e0641cb16ba16720625dfbdf5446f979e6dddc80c9ec179104f5ec7-360011641677.png)

Tab **Perangkat baru** memungkinkan Anda mendeteksi sumber media dan ID situs secara visual, yang memiliki <Anchor target="_blank" href="/marketers/id/docs/protect360-anti-fraud-guide#benchmarks-and-tips">rasio tinggi yang mencurigakan dari perangkat baru yang</Anchor> menginstal aplikasi Anda.

Sumber, yang berwarna abu-abu, berada di bawah **ambang rasio Perangkat baru**. Untuk sumber berwarna kuning, jika warnanya lebih kuat, berarti terdapat  rasio perangkat baru yang lebih tinggi.

Area yang ditempati oleh sumber media mewakili jumlah total instalasinya, termasuk kecurangan yang diblokir dan pascaatribusi.

**Untuk melihat tinjauan perangkat baru**  (angka merujuk pada tangkapan layar sebelumnya) :

1. Buka **Anomali** > **Perangkat baru** .
2. Pilih aplikasi di halaman yang ingin Anda lihat.
3. Pilih negara mana yang berkontribusi ke data di halaman.
4. Pilih rentang tanggal data di halaman.
5. Atur **ambang rasio Perangkat baru** , di atas yang Anda anggap sebagai sumber media mencurigakan dan diwarnai dengan warna kuning.
6. Untuk melihat rincian lebih lanjut tentang sumber media, klik sumber media.   
   Klik tautan **Semua sumber media** untuk kembali ke tampilan semua sumber media.
7. Klik tautan **Penginstalan** untuk kembali ke tab **Penginstalan** .
8. Anda dapat mengekspor [tabel](/docs/protect360-dashboard#installs-table) **perincian kecurangan yang teridentifikasi**, yang berisi data perangkat baru.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Sifat | Catatan |
| --- | --- |
| Retargeting | <ul><li>Dashboard penginstalan (CPI) dapat menampilkan perincian tipe sentuh yang diatribusikan antara penginstalan, atribusi ulang, dan interaksi ulang.</li><li>Dashboard in-app event (CPA) menampilkan event penipuan dari penginstalan UA, namun bukan dari penargetan ulang. **Catatan**: Event penipuan dari atribusi ulang yang diidentifikasi secara real-time, dapat dilihat dalam laporan data lengkap.</li></ul> |
| Data historis | Data tersedia sejak awal langganan Protect360 |

</Accordion>

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/protect360-anti-fraud-guide">Ikhtisar Protect360</Anchor>
> * <Anchor target="_blank" href="/marketers/id/docs/protect360-raw-data-reports">Laporan Data Lengkap</Anchor>

<div data-zendesk-anchors="about-protect360-dashboard=tentang-dashboard-protect360 01H8H9GQ17C4PBHCAMXE879BX7=tentang-dashboard-protect360 01H8H9GQ173SQ8P29C4DETJRTD=filters-and-groupings installs-dashboard=dashboard-instalasi 01H8H9GQ173H3QH1Y5KZ26XMCW=dashboard-instalasi installs%E2%80%94headline-metrics=installs-headline-metrics 01H8H9GQ17FJKWE3M2YSZFTQCS=installs-headline-metrics installs%E2%80%94charts=installs-charts 01H8H9GQ18VHMK7FFV3RY409VB=installs-charts identified-fraud-trend-chart=grafik-tren-penipuan-yang-teridentifikasi 01H8H9GQ18JDSZ2H8BKZVWGBPV=grafik-tren-penipuan-yang-teridentifikasi hijacked-installs-attribution-correction-chart=bagan-koreksi-atribusi-penginstalan-yang-dibajak 01H8H9GQ18VXBPQRN55WHM3GG0=bagan-koreksi-atribusi-penginstalan-yang-dibajak identified-fraud-chart=bagan-penipuan-yang-teridentifikasi 01H8H9GQ18FW87TXQZCYERHNDE=bagan-penipuan-yang-teridentifikasi installs%E2%80%94table=installs-table 01H8H9GQ18FYXJA7TXQ4RNQGX2=installs-table identified-fraud-breakdown=perincian-penipuan-yang-teridentifikasi 01H8H9GQ18540JJ8X833E6WF44=perincian-penipuan-yang-teridentifikasi content-of-the-identified-fraud-breakdown-table=konten-tabel-rincian-kecurangan-yang-teridentifikasi 01H8H9GQ18DMPD7YTPTN2XJMSH=konten-tabel-rincian-kecurangan-yang-teridentifikasi additional-table-options=opsi-tabel-tambahan 01H8H9GQ18PZ8ABG3D51M7J91R=opsi-tabel-tambahan inapp-events-dashboard=dashboard-in-app-event 01H8H9GQ19CQZV00XA62MGVJ86=dashboard-in-app-event inapp-events%E2%80%94headline-metrics=inapp-events-headline-metrics 01H8H9GQ19B95MDK2WEHVNEFS5=inapp-events-headline-metrics inapp-events%E2%80%94charts=inapp-events-charts 01H8H9GQ19XEJ0HNY2Y8BMX7A5=inapp-events-charts fraud-trend-over-time-chart=grafik-tren-kecurangan-dari-waktu-ke-waktu 01H8H9GQ1969AB4KK4ENP8AVQJ=grafik-tren-kecurangan-dari-waktu-ke-waktu top-iae-fraud-by-media-source-chart=penipuan-iae-teratas-menurut-grafik-sumber-media 01H8H9GQ19Z078PK1HR7VEZHXG=penipuan-iae-teratas-menurut-grafik-sumber-media inapp-events%E2%80%94table=inapp-events-table 01H8H9GQ19PTNWGJV6YDWR7SH6=inapp-events-table content-of-the-inapp-event-fraud-breakdown-table=konten-tabel-rincian-penipuan-in-app-event 01H8H9GQ19773CS8TGS2QXBRG5=konten-tabel-rincian-penipuan-in-app-event additional-table-options::44e54bfa=opsi-tabel-tambahan-1 01H8H9GQ192WA6XFNW7CKGBQ03=opsi-tabel-tambahan-1 01H8H9GQ1AVAVQ31ZZA1K024RF=payable-events anomalies-dashboard=dashboard-anomali 01H8H9GQ1AGXHE6FNNAHZTMZG6=dashboard-anomali 01H8H9GQ1AW1MZJAQE71H384N7=ctit-tab 01H8H9GQ1A0MNJTGAB1V9X4RNF=new-devices-tab 01H8H9GQ1BJX0K01NX8VCC0690=traits-and-limitations h_01HE7S2JKX3VMRCF6913S4MCAR=lihat-juga" />
