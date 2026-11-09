---
title: Ikhtisar pelaporan data lengkap
metadata:
  keywords:
    - LTV
    - raw data
    - uninstalls
    - AFI
    - Advertisers
    - Agencies
    - Premium Feature
    - Gray
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
  created_at: '2016-03-21T08:32:06Z'
  edited_at: '2023-11-08T14:41:05Z'
  id: 209680773
  locale: id
  section: Raw data reporting/APIs
  section_id: 6550930711057
  url: https://support.appsflyer.com/hc/id/articles/209680773
---
> **Sekilas:** Data tingkat baris (alias data lengkap) menjelaskan event yang berkaitan dengan pengguna seperti penginstalan, in-app event, kunjungan situs web, penginstalan yang diblokir Protect360, pendapatan iklan yang dihasilkan, dan postback terkait pengguna yang dikirim ke mitra. Laporan data lengkap tersedia melalui unduhan, API, dan Data Locker.

<div id="raw-data-reportingtools-and-reports" />

## Pelaporan data lengkap—alat dan laporan

Laporan data lengkap memungkinkan Anda menganalisis perilaku dan perjalanan pengguna, merekonsiliasi akun jaringan iklan, dan memperkaya sistem CRM dan BI Anda. Dengan menggunakan data lengkap, Anda meningkatkan kemampuan Anda untuk menganalisis, mengoptimalkan, dan meningkatkan kinerja aplikasi.

Laporan tersedia melalui alat pelaporan. Alat memiliki karakteristik berbeda yang cocok untuk kasus penggunaan yang berbeda. Misalnya, untuk merekonsiliasi akun jaringan iklan tertentu, unduh laporan sesuai kebutuhan melalui halaman Ekspor data. Untuk memuat data kinerja pengguna ke dalam sistem BI Anda, dapatkan data secara terprogram menggunakan Data Locker atau Pull API.

<div id="tip" />

> 👍 **Tips**
>
> Ingin mengerti lebih banyak tentang data lengkap? Lihat <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7806/play/18629/viewing-and-understanding-your-raw-data">kursus singkat dan informatif ini di Portal Pembelajaran AppsFlyer</Anchor>.

<div id="reporting-tools-characteristics-and-features" />

<Accordion title="Karakteristik dan fitur alat pelaporan">

Laporan tersedia menggunakan alat pelaporan yang tercantum di bagian ini.

Pertimbangan:

* Rentang tanggal laporan berkaitan dengan tanggal aktivitas (sebenarnya) event itu terjadi. Ini berbeda dengan laporan gabungan yang rentang tanggalnya <Anchor target="_blank" href="/marketers/id/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">berbasis LTV</Anchor> .
* Deskripsi bidang—lihat <Anchor target="_blank" href="/marketers/id/docs/raw-data-field-dictionary">kamus bidang data</Anchor> .

<div id="reporting-tools" />

#### Alat pelaporan

<table><thead><tr><th>Alat</th><th>Deskripsi</th><th>Multi-aplikasi /aplikasi tunggal (1)</th><th>Kemampuan kesegaran data (2)</th><th>Disematkan dalam skrip</th><th>zona waktu</th><th>Mata Uang</th></tr></thead><tbody><tr><td><a href="./raw-data-export-page" target="_blank">Halaman ekspor data lengkap</a></td><td><ul><li>Unduh laporan menggunakan antarmuka pengguna</li><li>Format: file CSV</li></ul></td><td>Tunggal</td><td>Terus diperbarui</td><td><strong><span>x</span></strong></td><td><p>Khusus-aplikasi</p></td><td>Khusus-aplikasi</td></tr><tr><td><a href="./pull-api-raw-data" target="_blank">Pull API\*</a></td><td><ul><li>Unduh laporan menggunakan panggilan API.</li><li>Format: file CSV</li></ul></td><td>Tunggal</td><td>Terus diperbarui</td><td><span>✓</span></td><td><ul><li>Dapat dipilih</li><li>Default: UTC</li></ul></td><td><ul><li>Dapat dipilih</li><li>Default: USD</li></ul></td></tr><tr><td> <a href="./data-locker-for-marketers" target="_blank">Data Locker</a> <strong><span>P</span></strong> </td><td><ul><li>Data di-stream ke <a href="./data-locker-cloud-service-setup" target="_blank">bucket di cloud</a> </li><li>Tidak ada batasan volume.</li><li>Jendela ketersediaan data: 14 hari.</li><li>Format: CSV atau  parquet</li></ul></td><td>Beberapa</td><td>Terus diperbarui dengan jeda beberapa jam</td><td><span>✓</span></td><td>UTC</td><td>USD </td></tr><tr><td> <a href="./push-api-streaming-raw-data" target="_blank">Push API<span></span></a> <strong><span>P</span></strong> </td><td><ul><li>Data perjalanan pengguna (penginstalan, in-app, penargetan ulang, SKAN) dikirim ke server Anda secara waktu aktual.</li><li>Format: JSON atau parameter kueri</li></ul></td><td>Dapat menggunakan titik akhir yang sama</td><td>Beberapa menit setelah event dicatat di AppsFlyer</td><td><span>✓</span></td><td>UTC + khusus aplikasi</td><td>USD + khusus aplikasi</td></tr><tr><td> <a href="./conversion-data-payloads-and-scenarios" target="_blank">Data Konversi SDK</a> (1)</td><td><ul><li>Dapatkan data konversi atribusi dalam aplikasi.</li><li>Format: JSON</li></ul></td><td>N/A</td><td> Waktu aktual &lt;5 detik</td><td> <span>✓</span> </td><td>UTC</td><td>N/A</td></tr></tbody><tfoot><tr><td colspan="7"><p><strong>Catatan/singkatan:</strong><br/> (1) Dukungan beberapa aplikasi<br/> (2) Kesegaran data aktual bergantung pada laporan itu sendiri, karena beberapa laporan bersifat Harian.<br/>(3) Metode data konversi SDK mengambil data atribusi pengguna dalam waktu kurang dari 5 detik sejak peluncuran aplikasi pertama, dan karenanya merupakan metode yang paling tidak akurat.<br/><strong><span>(P) </span></strong><span>Fitur premium</span><br/><a href="./report-generation-quotas-rate-limitations" target="_blank">(\*) Berlaku kuota pembuatan laporan</a></p></td></tr></tfoot></table>

<div id="tool-limitations" />

#### Batasan alat

<table><thead><tr><th>Batasan </th><th>Pull API (\*)</th><th>Push API</th><th>Data Locker</th><th>Data <br/>Konversi SDK</th></tr></thead><tbody><tr><td>Batas data</td><td>1 juta baris per panggilan</td><td>N/A</td><td>N/A</td><td>N/A</td></tr><tr><td>Opsi pemilihan data</td><td>Pilih tipe data. Opsi pemilihan bidang terbatas</td><td>Pilih jenis data, bidang, dan in-app</td><td>Pilih jenis data, bidang, dan in-app</td><td>Tidak</td></tr><tr><td>Jendela ketersediaan data</td><td>90 hari</td><td>N/A</td><td>14 hari </td><td>Seumur Hidup (tersedia di SDK)</td></tr><tr><td colspan="5"><p><a href="./report-generation-quotas-rate-limitations" target="_blank">(\*) Berlaku kuota pembuatan laporan</a></p></td></tr></tbody></table>

<div id="integration-considerations" />

#### Pertimbangan integrasi

| Pertimbangan | Pull API | Push API | Data Locker | Data Konversi   <br />SDK |
| --- | --- | --- | --- | --- |
| Pengembangan sisi Server | OPSIONAL | WAJIB | OPSIONAL | OPSIONAL |
| Membutuhkan pemrosesan data | OPSIONAL | WAJIB | OPSIONAL | OPSIONAL |
| Risiko kehilangan data | Tidak | Ya, jika server penerima sedang down | Tidak | Kecil, jika ada keterlambatan dalam respons jaringan iklan |
| Biaya pemrosesan klien-server | Tidak ada | Tinggi | Rendah | Tidak ada (kecuali mengirim data ke server) |
| Pemeliharaan server-klien | Tidak ada | Tinggi | Rendah | Tidak ada (kecuali mengirim data ke server) |
| Format data | File CSV | JSON atau parameter kueri | CSV atau parquet | JSON |

</Accordion>

Catatan data lengkap yang terjadi dalam konteks tertentu dikelompokkan bersama dalam laporan. Misalnya, penginstalan non-organik, in-app event organik. Untuk memudahkan penjelasan, laporan dikelompokkan sebagai berikut:

* **Perjalanan pengguna:** Digunakan untuk melacak perjalanan dan interaksi pengguna dengan aplikasi.  
  Misalnya: klik > instal > in-app event > uninstall.
* **Fitur:** Berhubungan dengan fitur AppsFlyer tertentu tetapi bukan bagian dari perjalanan pengguna utama. Misalnya, postback ke jaringan iklan, laporan kecurangan dan Aturan Validasi, dan laporan pendapatan iklan tingkat pengguna.

<div id="report-fields" />

<Accordion title="Bidang laporan">

<Anchor target="_blank" href="/marketers/id/docs/raw-data-field-dictionary">Kamus bidang data lengkap</Anchor> berisi bidang yang relevan dengan laporan perjalanan pengguna dan beberapa bidang laporan fitur. Prinsip-prinsipnya adalah sebagai berikut:

* **Perjalanan pengguna:**
  * Memiliki seperangkat bidang yang sama.
  * Pengisian bidang tergantung pada konteks perjalanan. Misalnya, laporan non-organik berisi sumber media yang dikreditkan dengan membawa pengguna. Bidang atribusi dalam laporan organik tidak diisi karena tidak ada sumber media.
* **Fitur** : Memiliki kumpulan bidang yang unik atau berisi bidang perjalanan pengguna dan bidang tambahan yang relevan dengan fitur tersebut. Misalnya, laporan SKAdNetwork memiliki daftar bidang yang unik, sedangkan laporan postback berisi bidang perjalanan pengguna dan bidang tambahan yang berkaitan dengan pengiriman postback ke mitra.

**Tips** ! Cara terbaik untuk memahami laporan adalah dengan melihat laporan. Anda dapat mengunduh laporan melalui laman <Anchor target="_blank" href="/marketers/id/docs/raw-data-export-page">Ekspor data</Anchor>.

Untuk memudahkan pemahaman, bidang perjalanan pengguna dibagi menjadi beberapa kelompok berdasarkan konteks.

<div id="user-journey-raw-data-field-groups" />

#### Grup bidang data lengkap perjalanan pengguna

| Grup bidang | Relevan dengan pengguna organik | Contoh bidang |
| --- | --- | --- |
| Aplikasi | Ya | ID Aplikasi, nama aplikasi, versi aplikasi, versi SDK, ATT |
| Atribusi | Tidak, kecuali untuk waktu instal. | Waktu instal, w aktu sentuh yang diatribusikan, sumber media, kampanye, iklan, iklan, mitra, jenis konversi penargetan ulang |
| Atribusi kontributor | Tidak | Mitra kontributor, jenis pencocokan |
| Informasi perangkat | Ya | ID Iklan, GAID, OAID, jenis perangkat, ID pengguna pelanggan |
| Lokasi perangkat | Ya | Alamat IP, kota, negara |
| Event | Ya | Diisi dalam laporan in-app event:<br /><br />Nama event, nilai event, pendapatan event |

</Accordion>

<div id="user-journey-reports" />

## Laporan perjalanan pengguna

<Image align="center" alt="Raw_data_-_User_acquisition_.png" src="https://files.readme.io/319da2a6a5567d6cfe4a74337279e67e0bdcdb063e62ecacde5eb4293a98a1a2-36317497158033.png" />

<div id="user-journey-basics" />

<Accordion title="Dasar-dasar perjalanan pengguna">

Laporan perjalanan pengguna berisi data yang dikumpulkan untuk event yang terjadi selama nilai umur pengguna. Data tersebut dibagi menjadi laporan menurut:

* Sumber pengguna: organik atau non-organik
* Konteks perjalanan:
  * Interaksi dengan iklan sebelum penginstalan aplikasi (tayangan dan klik)
  * Akuisisi
  * Retargeting

**Laporan akuisisi pengguna (UA) berisi:**

* Tayangan dan klik yang terjadi sebelum penginstalan oleh *calon* pengguna yang berinteraksi dengan iklan.
* Event penginstalan.
* In-app event berikutnya yang dilakukan oleh pengguna.

**Laporan penargetan ulang berisi:**

* Tayangan dan klik yang terjadi saat pengguna ditargetkan ulang.
* Event konversi: Interaksi ulang atau atribusi ulang.
* In-app event berikutnya dilakukan sebagai bagian dari interaksi ulang. Pertimbangkan:
  * Data penargetan ulang selalu non-organik.
  * Penargetan ulang in-app event ada di UA dan laporan in-app event penargetan ulang. Lihat metodologi atribusi ganda <Anchor target="_blank" href="/marketers/id/docs/resolve-retargeting-double-attribution">penargetan ulang</Anchor>.

    <Image align="center" alt="Raw_data_-_Retargeting.png" src="https://files.readme.io/717f6e43ca3b224ead9e3e1c5f9b277d2f21dbc1fe3b4c217ebf4bdbc539bab7-36317470735249.png" />

Untuk mengikuti perjalanan pengguna, gabungkan laporan yang terkait dengan bagian perjalanan yang Anda minati, misalnya, penginstalan dan in-app event. Setelah melakukannya, urutkan laporan menggunakan ID AppsFlyer, waktu event, dan jenis laporan. Hasilnya adalah event pengguna tertentu dari waktu ke waktu, yang berarti perjalanan pengguna.

</Accordion>

<div id="user-journey-report-availability" />

<Accordion title="Ketersediaan laporan perjalanan pengguna">

* Ketersediaan laporan bergantung pada paket berlangganan Anda.
* Laporan dapat mencakup baik pengguna organik, pengguna non-organik, atau keduanya, seperti yang ditunjukkan.
* Kebijakan retensi yang berlaku untuk laporan data lengkap historis bergantung pada alat pelaporan dan asal data lengkap. Secara umum, data tersedia untuk 90 hari sebelumnya. **Perhatikan** ! Kebijakan retensi tidak berlaku untuk data gabungan.

<div id="user-journey-reports-1" />

#### Laporan perjalanan pengguna

<table><thead><tr><th>ketegori</th><th>Unik untuk Data Locker</th><th>Topik laporan</th><th>Organik</th><th>Non-organik</th></tr></thead><tbody><tr><td>Akuisisi User</td><td><span>✓</span></td><td>Klik</td><td colspan="2">N/A</td></tr><tr><td>Retargeting</td><td><span>✓</span></td><td>Klik dari kampanye penargetan ulang </td><td colspan="2">Penargetan ulang selalu non-organik</td></tr><tr><td>Akuisisi User</td><td><span>✓</span></td><td>Tayangan </td><td colspan="2">N/A</td></tr><tr><td>Retargeting</td><td><span>✓</span></td><td>Tayangan dari kampanye penargetan ulang</td><td colspan="2">Penargetan ulang selalu non-organik</td></tr><tr><td>Akuisisi User</td><td>-</td><td>Memasang </td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Akuisisi User</td><td>-</td><td>In-App Event </td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Akuisisi User</td><td>-</td><td>Pendapatan iklan yang diatribusikan</td><td>-</td><td><span>✓</span></td></tr><tr><td>Akuisisi User</td><td>-</td><td>Pendapatan iklan organik</td><td><span>✓</span></td><td>-</td></tr><tr><td>Retargeting</td><td>-</td><td>Penargetan ulang pendapatan iklan</td><td colspan="2">Penargetan ulang selalu non-organik</td></tr><tr><td>Retargeting</td><td>-</td><td>Konversi penargetan ulang (interaksi ulang dan atribusi ulang)</td><td colspan="2">Penargetan ulang selalu non-organik</td></tr><tr><td>Retargeting</td><td>-</td><td>Penargetan ulang in-app event (interaksi ulang dan atribusi ulang)</td><td colspan="2">Penargetan ulang selalu non-organik</td></tr><tr><td>Retargeting</td><td> <span>✓</span> </td><td>Sesi penargetan ulang (interaksi ulang dan atribusi ulang)</td><td colspan="2">Penargetan ulang selalu non-organik</td></tr><tr><td>Akuisisi User</td><td> <span>✓</span> </td><td>Sesi</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Akuisisi User</td><td>-</td><td>Pencopotan pemasangan non-organik </td><td>-</td><td><span>✓</span></td></tr><tr><td>Akuisisi User</td><td>-</td><td>Pencopotan pemasangan organik</td><td><span>✓</span></td><td>-</td></tr><tr><td>Akuisisi User</td><td><span>✓</span></td><td>Interaksi lintas platform</td><td><span>✓</span></td><td><span>✓</span></td></tr></tbody></table>

</Accordion>

<div id="user-journey-report-descriptions" />

<Accordion title="Deskripsi laporan perjalanan pengguna">

<div id="clicks-and-impressions" />

#### Klik dan Impresi

| Laporan | Karakteristik |
| --- | --- |
| Context | Pengguna berinteraksi dengan kampanye dan mengklik atau melihat iklan. |
| Karakteristik | Laporan berisi catatan tautan atribusi dan header HTTP yang ada saat pengguna mengeklik atau <Anchor target="_blank" href="/marketers/id/docs/measure-view-through-engagements#set-impression-links">melihat</Anchor> iklan. |
| Kasus penggunaan | <ul><li>Optimalkan kampanye yang tidak mengarah ke pembukaan aplikasi (instal, atribusi ulang, interaksi ulang).</li><li>Targetkan ulang pengguna ini menggunakan kampanye yang berbeda.</li></ul> |
| Contoh laporan | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=1036692270&single=true&output=csv">Klik</Anchor> |
| Catatan | Data SRN tidak tersedia. |
| Pengguna terbatas | Dalam beberapa kasus, karena aturan privasi, data tayangan dan klik dibatasi (tidak memiliki pengenal pengguna) atau tidak tersedia sama sekali. Ketersediaan tergantung pada sumber media dan platform. |

<div id="installs-and-retargeting-conversions" />

#### Penginstalan dan konversi penargetan ulang

<table><thead><tr><th rowspan="2">Nama laporan </th><th rowspan="2"><p>Akuisisi pengguna: Penginstalan</p></th><th rowspan="2">Penargetan Ulang: Konversi</th></tr></thead><tbody><tr><td> <br/>Context</td><td><p>Saat pengguna membuka aplikasi untuk pertama kalinya.</p></td><td><p>Setelah pengguna berinteraksi dengan iklan penargetan ulang dan kemudian membuka aplikasi. Konversi penargetan ulang menjadi interaksi ulang atau atribusi ulang.</p> Lihat <a href="./retargeting-attribution-guide#retargeting-reports-and-raw-data" target="_blank">pedoman atribusi penargetan ulang</a> </td></tr><tr><td>Gunakan case (kasus)</td><td><ul><li>Buat laporan gabungan menggunakan bidang yang tidak tersedia melalui alat analitik AppsFlyer.</li><li>Gabungkan dengan laporan lain untuk analisis lintas bagian lanjutan.</li><li>Analisis kinerja di berbagai dimensi seperti kota, area metropolitan, dan sebagainya. </li><li>Segmentasikan pengguna menurut negara, kota, dan bahasa untuk tujuan penargetan.</li><li>Dapatkan ID perangkat pengguna untuk tujuan penargetan ulang.</li></ul></td><td>Mirip dengan menginstal.</td></tr><tr><td>Organik vs. non-organik</td><td><ul><li> <strong>Non-organik:</strong> Grup bidang atribusi atribusi dan kontributor diisi</li><li> <strong>Organik:</strong>  Bidang sumber media kosong, null, atau organik. Pertimbangkan ini ketika Anda memuat data ke dalam sistem Anda. </li></ul></td><td>Tak dapat diterapkan</td></tr><tr><td>Contoh laporan</td><td><a href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=0&amp;single=true&amp;output=csv" target="_blank">Install</a></td><td>Laporan konversi penargetan ulang memiliki struktur yang sama dengan laporan penginstalan. Beberapa bidang diisi dalam konteks penargetan ulang. Lihat <a href="./retargeting-attribution-guide#retargeting-reports-and-raw-data" target="_blank">penargetan ulang data lengkap</a>. </td></tr></tbody></table>

<div id="in-app-events" />

#### In-App Event

<Table>
  <thead>
    <tr>
      <th>
        Laporan
      </th>
      <th>
        Karakteristik
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="report-context"></span>
        Konteks laporan
      </td>
      <td>
        Daftar kronologis tindakan yang dilakukan oleh pengguna setelah atribusi (instal, atribusi ulang, atau penargetan ulang)
      </td>
    </tr>
    <tr>
      <td><span id="characteristics"></span>
        Karakteristik
      </td>
      <td>
        * Struktur dan bidang laporan mirip dengan laporan penginstalan.
        * Bidang khusus menjelaskan event. Ini termasuk nama event, nilai, pendapatan, dan waktu.
      </td>
    </tr>
    <tr>
      <td><span id="use-case"></span>
        Kasus penggunaan
      </td>
      <td>
        Gunakan laporan untuk:

        * Dapatkan wawasan dengan mengamati perjalanan pengguna selama nilai umur pengguna
        * Gabungkan data lengkap instal dan in-app-event untuk mengikuti perjalanan pengguna yang lengkap.
      </td>
    </tr>
    <tr>
      <td><span id="event-values"></span>
        Nilai event
      </td>
      <td>
        **Bidang nilai event**

        Bidang nilai event berisi semua data yang terkait dengan event dalam JSON. Anda dapat memuat ini ke dalam sistem BI Anda untuk analisis lebih lanjut.

        **Tips!** Anda dapat menggunakan <Anchor target="_blank" href="https://docs.microsoft.com/en-us/power-query/parse-json-xml">Power Query di Microsoft Excel</Anchor> untuk mengurai parameter event dari string teks JSON.

        ```json
        {"af_level":"10","af_user_journey":"3387","arena":"7","char_type":"paladin"}
        ```

        **Melaporkan pendapatan**

        Data pendapatan dan ROI di AppsFlyer berasal dari af\_revenue yang dikirim dalam event.

        Saat parameter af\_revenue dikirim dalam in-app-event, AppsFlyer menggunakannya untuk mengisi bidang pendapatan event. Bidang inilah yang digunakan AppsFlyer untuk memperbarui dasbor dan laporan gabungan.

        Perhatikan! Gunakan hanya gunakan parameter af\_revenue dengan in-app-events yang menjelaskan **pendapatan aktual yang dihasilkan.** Untuk event lain yang melibatkan pendapatan, tetapi tidak bersifat final, misalnya add\_to\_cart, gunakan parameter yang berbeda seperti af\_price
      </td>
    </tr>
    <tr>
      <td><span id="example-report"></span>
        Contoh laporan
      </td>
      <td>
        [In-App Event](https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=819556999&single=true&output=csv)
      </td>
    </tr>
    <tr>
      <td><span id="remarks"></span>
        Catatan
      </td>
      <td>
        * Penargetan ulang in-app event <Anchor target="_blank" href="/marketers/id/docs/resolve-retargeting-double-attribution">dicatat dua kali</Anchor> di UA dan penargetan ulang laporan data lengkap in-app event.
        * In-app event tidak menyertakan event peluncuran (af\_app\_opened). Event ini tersedia dalam laporan data lengkap <Anchor target="_blank" href="/marketers/id/docs/measure-sessions">sesi</Anchor>.
        * Lokasi geografis: Dihasilkan dengan menggunakan alamat IP pengguna pada saat event dilakukan.
      </td>
    </tr>
  </tbody>
</Table>

<div id="sessions" />

#### Sesi

| Laporan | Karakteristik |
| --- | --- |
| Context | Saat pengguna membuka aplikasi, event sesi dikirim ke AppsFlyer. Event dicatat jika <Anchor target="_blank" href="/marketers/id/docs/measure-sessions">waktu minimum antara</Anchor> ambang batas sesi terlampaui. |
| Karakteristik | Struktur laporan sama dengan laporan in-app event. Sesi (event sesi) berada dalam laporan terpisah karena banyaknya jumlah event tersebut. |
| Kasus penggunaan | Pahami interaksi pengguna dengan aplikasi. |
| Contoh laporan | Laporan sesi ini mirip dengan laporan in-app event. Catatan: Dalam data lengkap, sesi memiliki *peluncuran* nama event. |

<div id="uninstalls" />

#### mencopot pemasangan

| Laporan | Karakteristik |
| --- | --- |
| Context | Catatan pengguna yang meng-uninstall aplikasi. |
| Karakteristik | <ul><li>Laporan ini diperbarui setiap hari dan tidak terus-menerus, seperti halnya laporan perjalanan pengguna lainnya.</li><li>Dalam laporan, waktu event menunjukkan waktu AppsFlyer menentukan bahwa aplikasi telah di-uninstall dan bukan uninstall aktual itu sendiri. Lihat Pengukuran Uninstall.</li></ul> |
| Bidang tersedia | <ul><li>Jika pengguna berasal dari sumber media non-organik, bidang sumber media akan diisi.</li><li>Pertimbangkan bahwa uninstall event dihasilkan oleh server AppsFlyer setelah menentukan bahwa pengguna di-uninstal. Akibatnya, banyak bidang tidak terisi.</li><li>Pengenal pengguna yang tersedia adalah yang dicatat pada saat penginstalan. CUID tidak tersedia.</li><li>Bidang terkait lokasi diisi dengan lokasi pengguna pada saat berinteraksi dengan sumber media (klik atau tayangan). Jika lokasi interaksi tidak tersedia, maka lokasi yang terkait dengan event penginstalan yang akan digunakan.</li></ul> |
| Contoh laporan | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=1558773473&single=true&output=csv">Uninstall</Anchor> Perhatikan! Dalam contoh, untuk kejelasan, baris 2 menunjukkan bidang mana yang diisi, jika data yang relevan tersedia. |
| Gunakan case (kasus) | <ul><li>Menganalisis event uninstall, perangkat, dan karakteristik pengguna</li><li>Membangun pemirsa event uninstall untuk penargetan ulang</li></ul> |

</Accordion>

<div id="user-journey-report-availability-per-tool" />

<Accordion title="Ketersediaan laporan perjalanan pengguna per alat">

<div id="ad-engagement-report-by-tool" />

#### Laporan interaksi iklan menurut alat

<table><tbody><tr><th>Laporan</th><th>Ekspor data</th><th>Pull API</th><th>Data Locker</th><th>Push API</th><th>Data Konversi <br/>SDK</th></tr><tr><td>Tampilan (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Klik (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td colspan="6">(1) Data klik dan tayangan disediakan oleh non-SRN. SRN tidak menyediakan data ini.</td></tr></tbody></table>

<div id="user-acquisition-reports-by-tool" />

#### Laporan akuisisi pengguna menurut alat

| Laporan | Ekspor data | Pull API | Data Locker | Push API | Data konversi SDK |
| --- | --- | --- | --- | --- | --- |
| Install | ✓ | ✓ | ✓ | ✓ | ✓ |
| Sesi | - | - | ✓ | - | - |
| In-App Event | ✓ | ✓ | ✓ | ✓ | - |
| mencopot pemasangan | ✓ | ✓ | ✓ | - | - |

<div id="retargeting-raw-data-reports-by-tool" />

#### Menargetkan ulang laporan data lengkap dengan alat

<table><thead><tr><th>Laporan</th><th>Ekspor data</th><th>Pull API</th><th>Data Locker</th><th>Push API</th><th>Data Konversi <br/>SDK</th></tr></thead><tbody><tr><td>Klik (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Konversi (atribusi ulang + interaksi ulang)</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Tampilan (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Sesi</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>In-App Event</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr></tbody><tbody><tr><td colspan="6"><p>(1) Data klik dan tayangan disediakan oleh non-SRN. SRN tidak menyediakan data ini.</p></td></tr></tbody></table>

</Accordion>

<div id="faq" />

<Accordion title="Pertanyaan Umum">

| Detail |
| --- |
| **Mengapa data lengkap Meta ads hilang?**<br /><br />Secara default, data lengkap Meta ads diatribusikan ke <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions">sumber media terbatas</Anchor>. Lihat <Anchor target="_blank" href="/marketers/id/docs/meta-ads-integration-setup#userlevel-data">data tingkat pengguna Meta ads.</Anchor> |
| **Apa perbedaan antar stempel waktu?**<br /><br />Stempel waktu umum untuk semua laporan. Hal ini memungkinkan untuk menggabungkan laporan yang berbeda.<br /><br />Stempel waktu berikut relevan:<ul><li>**Waktu sentuh yang diatribusikan**: Waktu pengguna berinteraksi dengan iklan.</li><li>**Waktu** **penginstalan** : Waktu aplikasi diluncurkan untuk pertama kali.</li><li>**Waktu event** : Waktu event berlangsung.</li></ul>Pertimbangkan:<ul><li>Dalam laporan penginstalan, waktu penginstalan dan event adalah sama.</li><li>Dalam laporan in-app event, waktu penginstalan dan event berbeda. Perbedaannya dapat menunjukkan waktu yang berlalu antara peluncuran aplikasi dan interaksi pengguna dengan aplikasi.</li></ul> |
| **Apa tujuan dari bidang kontributor?**<br /><br />Bidang kontributor mencantumkan sumber media kontributor. Terkadang disebut sebagai <Anchor target="_blank" href="/marketers/id/docs/measure-assisted-installs#pelaporan-assisted-installs-penginstalan-berbantuan">Penginstalan Berbantuan</Anchor>. Di Protect360, bidang ini juga digunakan untuk <Anchor target="_blank" href="/marketers/id/docs/protect360-raw-data-reports#koreksi-atribusi-penginstalan-yang-dibajak">koreksi atribusi penginstalan yang dibajak</Anchor> . |
| **Apa yang dimaksud dengan bidang kata kunci—mengapa tidak tersedia di semua penginstalan non-organik?**<br /><br />Penginstalan yang diatribusikan dengan Google Ads atau Apple Search Ads, dapat berisi kata kunci atau ID kata kunci yang terkait dengan iklan yang menyebabkan penginstalan. |

</Accordion>

<div id="install-report-tips" />

<Accordion title="Tips laporan penginstalan">

**Memahami perjalanan pengguna**

Perjalanan pengguna merupakan serangkaian langkah yang dilakukan pengguna sebelum mencapai tujuan seperti membeli produk atau memesan penerbangan. Gagasan di balik menganalisis perjalanan pengguna adalah untuk melihat apa yang dilakukan pengguna di aplikasi, seberapa aktif mereka, dan nilai apa yang mereka bawa selama masa tertentu.

Anda dapat mengidentifikasi dan menyoroti perjalanan pengguna dengan bantuan ID AppsFlyer. ID dibuat untuk setiap penginstalan aplikasi per perangkat. ID tetap tidak berubah sepanjang siklus hidup pengguna (dari menginstal hingga uninstall.) ID tetap ada jika pengguna menyetel ulang ID perangkat mereka.

Karena laporan penginstalan dan in-app event memiliki struktur yang sama, laporan tersebut dapat digabungkan menjadi satu. Dalam laporan gabungan, Anda dapat menggabungkan dan memfilter menggunakan ID AppsFlyer dan ID Pengguna Pelanggan (jika tersedia) untuk menganalisis perjalanan pengguna.

<div id="engaged-userstrong" />

> 📄 **Pengguna yang berinteraksi—kuat**
>
> * Seorang pengguna menginstal aplikasi pada 20 Agustus pukul 09:31.
> * Laporan gabungan menunjukkan bahwa mereka melakukan pembelian pada 20 Agustus pukul 10:31, 22 Agustus pukul 15:22, dan 25 Agustus pukul 16:47.
> * Dari sini, kami menyimpulkan bahwa pengguna adalah pengguna yang berinteraksi. Mereka melakukan pembelian satu jam setelah meluncurkan aplikasi dan melanjutkan pembelian pada hari-hari setelah penginstalan.
>
> #### <span id="engaged-userweak"></span>Pengguna yang berinteraksi—lemah
>
> * Seorang pengguna menginstal aplikasi pada 30 Juli. Laporan gabungan menunjukkan bahwa mereka menambahkan item ke keranjang mereka pada 15 Agustus, tetapi tidak ada event pembelian berikutnya.
> * Anda dapat berasumsi bahwa pengguna ragu-ragu untuk melakukan pembelian dan memilih untuk menargetkan ulang dengan item yang mereka tambahkan ke keranjang.
>
> #### <span id="analyzing-the-user-journey-for-campaign-optimization"></span>Menganalisis perjalanan pengguna untuk pengoptimalan kampanye
>
> * Manajer akuisisi pengguna (UA) dari aplikasi perjalanan mengunduh penginstalan dan laporan in-app event dan menggabungkannya.
> * Lalu, untuk melihat perjalanan pengguna di app, mereka memfilter atau menggabungkan data berdasarkan ID AppsFlyer.
> * Manajer UA melihat bahwa pengguna tertentu, yang diidentifikasi oleh ID AppsFlyer mereka, mengunduh aplikasi 12 bulan yang lalu dan memesan penerbangan beberapa hari kemudian.
> * Selanjutnya, pengguna melihat beberapa penawaran penerbangan tetapi tidak melakukan pemesanan. Mencermati hal ini, manajer UA menemukan lebih banyak pengguna dengan pola yang sama dan memutuskan untuk menggali hal ini lebih dalam.
> * Mereka menemukan bahwa sebagian besar pengguna ini berasal dari **Iklan A** dari **Kampanye B** yang dijalankan pada **Media sumber C.** Ternyata iklan dan kampanye ini menargetkan pengguna yang ingin bepergian ke tujuan tertentu.
> * Dengan menganalisis perjalanan pengguna, manajer UA mungkin menyimpulkan bahwa fokus kampanye terlalu sempit dan pengguna tidak cukup berinteraksi dengan aplikasi.

</Accordion>

<div id="feature-reports" />

## Laporan fitur

Laporan yang berkaitan dengan fitur tambahan tersedia di platform

* <Anchor target="_blank" href="/marketers/id/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">Pendapatan Iklan</Anchor>
* <Anchor target="_blank" href="/marketers/id/docs/incrementality-for-remarketing-overview#raw-data-reports">Inkrementalitas</Anchor>
* <Anchor target="_blank" href="/marketers/id/docs/skan-raw-data-reports">SKAdNetwork</Anchor>

<div id="postbacks" />

<Accordion title="Postback (postingan balik)">

Gunakan laporan postback, untuk meninjau salinan data yang dikirim ke jaringan iklan. Misalnya, gunakan untuk menyelidiki perbedaan. Laporan ini untuk tujuan informasi, dan tidak diperlukan untuk integrasi dengan jaringan iklan.

* Laporan tersebut berisi:
  * Salinan postback yang dikirim ke sumber media yang diatribusikan.
  * <Anchor target="_blank" href="/marketers/id/docs/raw-data-field-dictionary">Bidang data lengkap</Anchor> dan bidang tambahan seperti yang dijelaskan di bagian ini.
* Laporan tidak berisi:
  * Penginstalan SRN.
  * Peristiwa dalam aplikasi terkait Meta ads, Twitter, dan Iklan Pencarian Apple.
  * Postback mitra tanpa atribut. Lihat <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#g">event yang dikaitkan ke mitra atau organik mana pun</Anchor>.
  * Pengguna organik. Lihat  <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#f">tentang penginstalan organik.</Anchor>
  * Kampanye pemasangan BPA telah menonaktifkan postback penginstalan .
* Mulai Maret 2021, bidang diisi sesuai dengan pengaturan Privasi Lanjutan pada jaringan. Artinya, jika Privasi Lanjutan aktif, beberapa bidang, seperti pengenal pengguna tidak dimasukkan. Lihat <Anchor target="_blank" href="/partners/id/docs/advanced-privacy-guide-postback-macros-for-ad-networks#advanced-privacy-postback-specification">spesifikasi postback Privasi Lanjutan untuk jaringan iklan.</Anchor>
* <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTs4MUZTBKRQF24n-T8JM1L6EhU4TayYneX6MB5HjM9iwnrQtX8tlPLBA-J7zmqDcJqYTCpRxhStdGg/pub?output=xlsx">URI  untuk laporan postback melalui Pull API</Anchor>

<div id="postback-reports-available-via-the-export-data-page-and-pull-api" />

#### Laporan postback (tersedia melalui halaman Data Ekspor dan Pull API)

| Topik laporan | Event dikirim ke sumber media teratribusi |
| --- | --- |
| Install | Penginstalan non-organik (UA) |
| In-App Event | In-App Event Non-Organic |
| postback konversi penargetan ulang | Penargetan ulang (interaksi ulang dan atribusi ulang) |
| Menargetkan ulang event dalam aplikasi | Menargetkan ulang event dalam aplikasi |

<div id="additional-fields-in-postback-reports" />

#### Bidang tambahan dalam laporan postback

| Kolom | Catatan |
| --- | --- |
| Postback URL | Beberapa nilai, seperti pendapatan, mungkin tidak muncul di bidang yang sesuai, tetapi Anda tetap dapat melihat data ini di **URL Postback**. |
| Metode postback |  |
| Kode respons HTTP postback | 200: Mengonfirmasi bahwa postback diterima oleh jaringan iklan |
| Pesan kesalahan postback |  |

</Accordion>

<div id="protect360-fraud-and-validation-rules" />

<Accordion title="Penipuan Protect360 dan aturan validasi">

* Lihat <Anchor target="_blank" href="/marketers/id/docs/protect360-raw-data-reports">Protect360</Anchor> dan <Anchor target="_blank" href="/marketers/id/docs/implement-validation-rules-to-prevent-fraud#outcomes">aturan validasi</Anchor> laporan data lengkap
* Agensi dan jaringan iklan memerlukan <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#access-protect360-dashboard-raw-data">izin</Anchor> pemasang iklan untuk mengakses laporan Protect360 dan Aturan Validasi.

**Untuk memberikan izin mitra terintegrasi untuk mengakses Protect360:**

1. Buka **Konfigurasi** > **Integrasi Aktif**.
2. Pilih mitra terintegrasi.
3. Di **tab Izin** , aktifkan **Akses dasbor Protect360 & data lengkap Anda melalui API** .
4. Untuk memberikan akses ke dashboard In-app events (CPA), aktifkan **Access aggregate in-app event data (Akses data in-app event gabungan)**.

</Accordion>

<div id="see-also" />

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/aggregated-and-analytics-reporting-overview">Laporan dan analitik gabungan</Anchor>

<div data-zendesk-anchors="raw-data-reporting%E2%80%94tools-and-reports=pelaporan-data-lengkapalat-dan-laporan h_01HE7SRDXQ9TR0CRB2JC9XCQE2=pelaporan-data-lengkapalat-dan-laporan h_01HE7SRDXQQJFMV9EJKPY34D00=tips reporting-tools%E2%80%94characteristics-and-features=reporting-tools-characteristics-and-features h_01HE7SRDXQFJGMY05K1SV4TF63=reporting-tools-characteristics-and-features reporting-tools=alat-pelaporan h_01HE7SRDXQ647XRQ8QVMPGH43B=alat-pelaporan tool-limitations=batasan-alat h_01HE7SRDXQWQAKR0G6CNKC5AMT=batasan-alat integration-considerations=pertimbangan-integrasi h_01HE7SRDXQN3HSMGAPBAX9S3MB=pertimbangan-integrasi h_01HE7SRDXQRPD8MHC8M5916HTQ=report-fields user-journey-raw-data-field-groups=grup-bidang-data-lengkap-perjalanan-pengguna h_01HE7SRDXQMGQEG1QWGWEESQER=grup-bidang-data-lengkap-perjalanan-pengguna user-journey-reports=laporan-perjalanan-pengguna h_01HE7SRDXQZ50WMKCMYHZM7D92=laporan-perjalanan-pengguna h_01HE7SRDXQFN0P9QK8SKAZKVKP=user-journey-basics h_01HE7SRDXRS2B12Z67MYMH0QN9=user-journey-report-availability user-journey-reports::d286e1f5=laporan-perjalanan-pengguna-1 h_01HE7SRDXR7YQGWN4FNDXMNMX8=laporan-perjalanan-pengguna-1 h_01HE7SRDXRK6G27SDFK3CGDCRC=user-journey-report-descriptions clicks-and-impressions=klik-dan-impresi h_01HE7SRDXRC9YKZ0P9ED0218SJ=klik-dan-impresi installs-and-retargeting-conversions=penginstalan-dan-konversi-penargetan-ulang h_01HE7SRDXRN60XE5BSDQY28N71=penginstalan-dan-konversi-penargetan-ulang inapp-events=in-app-event h_01HE7SRDXR3ZT39EDNW4MVZZTX=in-app-event sessions=sesi h_01HE7SRDXRY05XQCMZE6YPXGWQ=sesi uninstalls=mencopot-pemasangan h_01HE7SRDXRA7ESDD4ME51WWBPR=mencopot-pemasangan h_01HE7SRDXRZYNFGK4CNP4VPAE0=user-journey-report-availability-per-tool ad-engagement-report-by-tool=laporan-interaksi-iklan-menurut-alat h_01HE7SRDXR171M74HMQBZJ2E8R=laporan-interaksi-iklan-menurut-alat user-acquisition-reports-by-tool=laporan-akuisisi-pengguna-menurut-alat h_01HE7SRDXRMGEP5QB452ZKQ8X7=laporan-akuisisi-pengguna-menurut-alat retargeting-raw-data-reports-by-tool=menargetkan-ulang-laporan-data-lengkap-dengan-alat h_01HE7SRDXRXR4J3HTMYW2P233Y=menargetkan-ulang-laporan-data-lengkap-dengan-alat h_01HE7SRDXRWW3JKNESSN2QA4DV=faq h_01HE7SRDXR61K28JGA8944D6HV=install-report-tips h_01HE7SRDXRKFR2WYGNF317CTRX=menargetkan-ulang-laporan-data-lengkap-dengan-alat engaged-user%E2%80%94strong=pengguna-yang-berinteraksikuat h_01HE7SRDXRW0CWHGQV75VF66DC=pengguna-yang-berinteraksikuat engaged-user%E2%80%94weak=pengguna-yang-berinteraksilemah h_01HE7SRDXRNMDZEJQ32665T14F=pengguna-yang-berinteraksilemah analyzing-the-user-journey-for-campaign-optimization=menganalisis-perjalanan-pengguna-untuk-pengoptimalan-kampanye h_01HE7SRDXRRET0YN4Q8WYMENSR=menganalisis-perjalanan-pengguna-untuk-pengoptimalan-kampanye feature-reports=laporan-fitur h_01HE7SRDXSVAHKBYQK0C71K6AR=laporan-fitur h_01HE7SRDXSFWMVY61NBYFQ4XSM=postbacks postback-reports-available-via-the-export-data-page-and-pull-api=laporan-postback-tersedia-melalui-halaman-data-ekspor-dan-pull-api h_01HE7SRDXS6T4M4CRQN0ZTJETR=laporan-postback-tersedia-melalui-halaman-data-ekspor-dan-pull-api additional-fields-in-postback-reports=bidang-tambahan-dalam-laporan-postback h_01HE7SRDXSYBDG0H2QEYBFWSRH=bidang-tambahan-dalam-laporan-postback h_01HE7SRDXS8K4MB76WVBCBHASQ=protect360-fraud-and-validation-rules h_01HE7ST20N8ZBFNY2QXW5G44A1=lihat-juga" />
