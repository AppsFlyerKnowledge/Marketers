---
title: Dashboard kohort
metadata:
  keywords:
    - Cohort
    - Cohort Report
    - Advertisers
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2015-12-24T10:20:01Z'
  edited_at: '2023-12-04T14:41:06Z'
  id: 207040496
  locale: id
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/id/articles/207040496
---
> **Sekilas**: Dashboard kohort mengelompokkan pengguna aplikasi berdasarkan tanggal akuisisi. Lakukan analisis kinerja di seluruh siklus hidup pengguna. Gunakan dashboard untuk mendapatkan wawasan tentang bagaimana perbedaan kampanye mengubah metrik kampanye.

**Pendapatan berdasarkan hari pasca instalasi yang dirinci berdasarkan sumber media**

![Full_cohort2_us-en.png](https://files.readme.io/b60e18dcd68ca4b1831c56b69ad667931ca52610a456f8612f44d4fac51150f6-14583921567377.png)

## Dashboard kohort

Untuk menggunakan Cohort (Kelompok), pilih pengguna dari salah satu aplikasi Anda atau lebih dan kelompokkan mereka berdasarkan tanggal konversi. Metrik kelompok seperti pendapatan, ROI, dan tingkat konversi event tersedia. Bagi kelompok, untuk tujuan perbandingan, ke dalam dimensi seperti kampanye atau sumber media. Melakukan hal itu dapat mengungkap pola atau perubahan kinerja selama siklus hidup pengguna atau kampanye. Lihat <Anchor target="_blank" href="https://www.appsflyer.com/blog/cohort-report-mobile-marketing-kpis/?utm_campaign=Blog%20Subscription%2003-2019&utm_source=hs_email&utm_medium=email&utm_content=76370689&_hsenc=p2ANqtz-8SX49xuEw2WX_Vrlh11_zxlDFvlfMpBzSQm1I-nFhc0WbZDf0ACC-VEi4qmKhesHCsUNdhU50Oinl-urwnGAOZMwwHSTp6UgdChCi7ARayJFUFTus&_hsmi=76370689">Kasus penggunaan kelompok</Anchor>.

> 👍 **Tips**
>
> Ingin tahu lebih banyak tentang laporan kelompok? Lihat <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7804/play/18625/your-users-journey-with-retention-and-cohort-reports">kursus singkat dan informatif ini di Portal Pembelajaran AppsFlyer</Anchor>.

<div id="cohort-principles" />

<Accordion title="Prinsip kohort">

[![OV.png](https://files.readme.io/738bf91c1a12671b32b088993c43d4103498907a8bbe15821ddc53a0b071b876-32127949500305.png)](https://files.readme.io/738bf91c1a12671b32b088993c43d4103498907a8bbe15821ddc53a0b071b876-32127949500305.png)

* **Jenis kohort**
  * **Terpadu**:
    * Kinerja gabungan dari akuisisi pengguna dan kampanye penargetan ulang (termasuk biaya dan pendapatan).
    * Jika suatu event diatribusikan ke kedua jenis konversi, hanya event penargetan ulang yang disertakan. Artinya, laporan dibuat menggunakan sumber media sentuhan terakhir yang sebenarnya. Jika Anda terbiasa dengan data lengkap, itu berarti event di mana <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">is\_primary\_attribution=true</Anchor>.
  * **Akuisisi pengguna:** data kinerja dari penginstalan (instal ulang tidak termasuk kecuali <Anchor target="_blank" href="/marketers/id/docs/measure-reinstalls#attributed-to-the-first-install">diaktifkan secara khusus</Anchor>)
  * **Penargetan ulang:** data kinerja dari atribusi ulang atau interaksi ulang
* **Jenis tren**
  * **Kinerja seumur hidup pengguna:** Pengguna dikelompokkan berdasarkan waktu**konversi**. Hal ini memungkinkan Anda membandingkan kinerja pengguna setelah konversi, dimulai dengan hari konversi, yang disebut sebagai hari kelompok 0. Kelompok mengabaikan jam event dan hanya menggunakan hari event. Tren ini biasanya digunakan untuk mengevaluasi performa pengguna relatif terhadap sumber media.
    * Untuk perincian jam, jumlah maksimal jam adalah 72.
    * Untuk perincian hari, jumlah maksimal hari adalah 180.
    * Untuk perincian minggu, jumlah maksimal minggu adalah 156
    * Untuk perincian bulan, jumlah maksimum bulan adalah 36

* * **KPI menurut waktu atribusi:** Pengguna dikelompokkan menurut **waktu**konversi . Ini memungkinkan Anda untuk mengevaluasi performa kampanye dari waktu ke waktu dan untuk melihat KPI kampanye relatif terhadap waktu konversi.
* **Metrik terkait biaya:** Dalam Kelompok, data biaya disertakan hanya jika ada atribusi terkait (pemasangan, keterlibatan ulang, atau atribusi ulang). Dengan kata lain, jika kampanye dikenakan biaya berdasarkan klik dan impresi tetapi tidak memiliki atribusi, biaya tersebut tidak disertakan dalam laporan kelompok. Prinsip ini berlaku untuk semua tingkat hierarki periklanan.
* **Opsi perincian**

| Jenis perincian | Jangka waktu yang diizinkan | Catatan |
| --- | --- | --- |
| Hari | Pilih 1–60 hari |  |
| Waktu | Pilih 1–72 jam dari 72 jam sebelumnya | Metrik terkait biaya tidak tersedia |
| Minggu | Hingga 26 minggu |  |
| Bulan | Hingga 12 bulan |  |

</Accordion>

<div id="example-user-lifetime-performance-trend-vs-kpi-by-attribution-time-trend" />

<Accordion title="Misalnya: Tren performa pengguna di periode retensi vs. KPI berdasarkan tren waktu atribusi">

Dalam contoh ini, data lengkap yang sama digunakan untuk menghasilkan dua jenis tren kohort. Tabel data lengkap berisi event atribusi yang terkait dengan masing-masing pengguna A, B, C, dan D. Pengguna berinteraksi dengan iklan, menginstal aplikasi, dan pasca konversi melakukan satu pembelian atau lebih. Hari kohort 0 adalah hari instalasi.

[![CohortExample_en-us.jpg](https://files.readme.io/7542605e2bb3972dc90fb12c9d6a328ff52ec65f0694a79752380d548e72e286-32127949500817.jpg)](https://files.readme.io/7542605e2bb3972dc90fb12c9d6a328ff52ec65f0694a79752380d548e72e286-32127949500817.jpg)

</Accordion>

<div id="metrics-available" />

<Accordion title="Metrik tersedia">

<table><thead><tr><th> </th><th> </th><th colspan="6">Fungsi</th></tr><tr><th rowspan="2">Selalu/ Opsional </th><th rowspan="2"><p>Metrik</p></th><th>Count (Hitung)</th><th>cvr (rasio konversi)</th><th>Rating</th><th>Jumlah</th><th>Pengguna Unik</th><th>eCPA</th></tr><tr><th>Jumlah</th><th>Persentase</th><th>Persentase</th><th>Jumlah</th><th>Jumlah</th><th>Jumlah</th></tr></thead><tbody><tr><td>Selalu</td><td>Pengguna (4)</td><td><span>✓</span></td><td>-</td><td>-</td><td><span>-</span></td><td><span>-</span></td><td><span>-</span></td></tr><tr><td>Selalu</td><td>Biaya (3)</td><td><span>-</span></td><td><span>-</span></td><td>-</td><td><span>✓</span></td><td>-</td><td><span>-</span></td></tr><tr><td>Selalu</td><td>eCPI Rata-Rata</td><td><span>-</span></td><td><span>-</span></td><td><span>✓</span></td><td><span>-</span></td><td><span>-</span></td><td><span>-</span></td></tr><tr><td>OPSIONAL</td><td><code>"event_name"</code></td><td> </td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td> <span>✓</span><span><span>(5)</span></span> </td></tr><tr><td>OPSIONAL</td><td>Pendapatan</td><td><span>✓</span></td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td><span>-</span></td></tr><tr><td>OPSIONAL</td><td>ROAS (3)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td><td><span>-</span></td></tr><tr><td>OPSIONAL</td><td>ROI (3)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td><td><span>-</span></td></tr><tr><td>OPSIONAL</td><td>Sesi (2)</td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td>-</td><td> ✓(1) </td><td><span><span>-</span></span></td></tr><tr><td>OPSIONAL</td><td>Uninstall (3)</td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td><td><span>-</span></td></tr></tbody><tfoot><tr><td colspan="8"><p>(1) Sesi unik muncul saat aggregation_type=on_day<br/>(2) Sesi penargetan ulang (interaksi ulang dan atribusi ulang) tersedia untuk sesi yang muncul mulai dari tanggal 13 Juli 2020. Artinya, sesi yang berlangsung hingga 12 Juli 2020 tidak ditampilkan. <br/>(3) Tidak tersedia dalam kasus berikut:</p><ul><li>Jenis tampilan disatukan</li><li>Rinciannya adalah per jam. Dihitung setiap hari menggunakan waktu UTC. </li></ul><p>(4) Metrik <em>Pengguna</em> menghitung jumlah atribusi (penginstalan, interaksi ulang, atribusi ulang) yang terjadi selama periode yang dipilih.   </p><p>(5) Biaya efektif per tindakan (eCPA): Biaya / Jumlah kumulatif pengguna unik yang melakukan event.</p></td></tr></tfoot></table>

</Accordion>

## Menggunakan Kohort

<div id="setting-up-an-analysis" />

<Accordion title="Menyiapkan analisis">

1. Buka ***Dashboard** >* ***Kohort***.  
   Dashboard kohort dibuka. Perincian dan rentang tanggal konversi ditampilkan.  
   ![mceclip0__1_.png](https://files.readme.io/4113fd619422979d6a26004a55c009ebc48eef59d10ddc7c3e5becd2a758e6d4-32127949494417.png)
2. Pilih perincian.
3. Atur periode atribusi (akuisisi pengguna atau interaksi penargetan ulang). Data yang berkaitan dengan tanggal terkini dapat menghasilkan [data parsial](/docs/cohort-and-retention-dashboard#partial-data) yang ditunjukkan oleh tanda hubung dalam grafik dan tabel.
4. Klik **Edit Cohort**.  
   Periode waktu pengaturan Kohort dibuka.  

   <Image alt="CohortSetup.jpg" src="https://files.readme.io/f09cc190770d16a2ddf60e1f210f458114ac43d4c19fc5507fb50b0d1d2f5c77-32127949495825.jpg" width="365px" />
5. Lakukan hal berikut:
   * **Kohort Jenis:**
     * **Akuisisi User**
     * **Retargeting**
     * **Terpadu:** termasuk in-app event dari atribusi pengguna dan atribusi penargetan ulang. **Catatan**: event penargetan ulang didahulukan dari event akuisisi pengguna yang berarti bahwa laporan berisi event di mana <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">is\_primary=true</Anchor>.
   * Pilih jenis Tren:
     * **Performa pengguna di periode retensi**.
     * **KPI berdasarkan waktu atribusi**.
   * **Pengguna aplikasi**: Pilih 1–banyak atau **semua** (berarti 100 aplikasi teratas di akun Anda). **Catatan**: Agensi hanya dapat memilih satu aplikasi.
   * ***Dikelompokkan berdasarkan***: Pilih salah satu atau lebih [dimensi](/docs/cohort-and-retention-dashboard#list-of-dimensions-for-grouping-and-filtering) [Default: *Media Source*].
   * **Minimum cohort size** (Ukuran kohort minimum): Atur ukuran kohort minimum. Ini mencegah untuk mengacaukan laporan Anda dengan kohort (kecil) yang tidak signifikan. [Default=1]
   * Bidang opsional:
     * **Filtered by** (Difilter berdasarkan): Pilih satu atau lebih [dimensi](/docs/cohort-and-retention-dashboard#list-of-dimensions-for-grouping-and-filtering) untuk difilter. Tidak ada filter default.
6. Klik **Apply changes** (Terapkan perubahan).  
   Laporan ditampilkan.
7. Untuk menyelesaikan pengaturan kohort, selesaikan salah satu dari prosedur jenis tren berikut.
8. [Opsional] [Mengelola laporan kohort yang disimpan](/docs/cohort-and-retention-dashboard#using-my-reports-save-and-select-reports).

</Accordion>

<div id="trend-type-user-lifetime-performance" />

<Accordion title="Tipe tren—Performa pengguna di periode retensi">

Pengguna dikelompokkan ke dalam kohort berdasarkan **hari**pasca konversi. Hari konversi disebut sebagai hari pasca konversi 0. Hari berikutnya disebut sebagai hari pasca konversi 1 dan seterusnya.

* Untuk perincian hari, jumlah maksimal hari adalah 180.
* Untuk perincian minggu, jumlah maksimal minggu adalah 156
* Untuk perincian bulan, jumlah maksimum bulan adalah 36

![DaysPost.jpg](https://support.appsflyer.com/hc/article_attachments/360005455377)

* **Pilih metrik, fungsi, dan per pengguna**:   
   **Catatan!** Tidak semua kombinasi metrik, fungsi, dan per pengguna tersedia.
  * Metrik: Pendapatan,<Anchor target="_blank" href="/marketers/id/docs/measure-sessions">Sesi</Anchor>, Hapus Instalasi, ROI, In-app event, ROAS.
  * Fungsi: Metrik dihitung menggunakan fungsi. Daftar fungsi bervariasi tergantung pada metrik.
    * ***Sum (Jumlah)**:* total pendapatan pada hari kohort.
    * **Count**: hitung event. Misalnya, jumlah sesi, jumlah event pendapatan, jumlah uninstall, dll.
    * **Unique users** (Pengguna unik): jumlah pengguna unik yang melakukan event. Ini berarti, misalnya, jika seorang pengguna membuka aplikasi 10 kali pada hari tertentu, hasil yang ditampilkan adalah 1.
    * **In-app conversion (Konversi in-app)**:rasio konversi dari penginstalan/penargetan ulang ke in-app event. Jumlah pengguna unik yang melakukan in-app event spesifik untuk **pertama kalinya**  dibagi berdasarkan jumlah pengguna unik dalam kohort. Misalnya, jumlah pengguna [unik] dalam kohort adalah 100. Dari jumlah tersebut, 20 pengguna melakukan in-app event spesifik untuk pertama kalinya. Rasio konversi In-app adalah 20/100=20%.
  * **Per-pengguna**: saat dipilih, sum (jumlah) atau count (hitung) dibagi berdasarkan jumlah pengguna aplikasi.
* **Display duration** (Durasi tampilan): Jumlah hari kohort untuk menampilkan pasca konversi. Hari ke-0 adalah hari konversi, Hari ke-1 adalah hari setelah konversi, dan seterusnya. Catatan: Durasi tampilan terpotong jika hasilnya adalah tanggal mendatang.
* **Tabel** atau **Grafik:**
  * Bagan menampilkan peringkat 5 atau 10 teratas berdasarkan jumlah pengguna aplikasi dalam laporan kohort. Ini terlepas dari dimensi yang ditampilkan.
  * Tabel menampilkan hingga 50 baris. Pengguna, biaya, dan rata-rata ecpi (biaya efektif per instalasi) selalu ditampilkan terlepas dari metrik yang dipilih.
* ***Pada hari*** atau ***Kumulatif***:
  * Pada hari berarti nilai metrik untuk hari itu saja.
  * Pada hari tidak memberikan metrik terkait Biaya.
  * Kumulatif berarti kumulatif atau total berjalan dari metrik. Perhatikan! Dalam konteks metrik pengguna unik, artinya jumlah pengguna unik yang melakukan event tertentu hingga hari kohort tertentu. Ini bukan jumlah pengguna unik dari hari-hari sebelumnya.

</Accordion>

<div id="trend-type-kpi-by-attribution-time" />

<Accordion title="Tipe tren—KPI berdasarkan waktu atribusi">

Pengguna dikelompokkan ke dalam kelompok menurut **waktu atribusi.**

![KPIdays.jpg](https://support.appsflyer.com/hc/article_attachments/360005458837)

* **Pilih metrik, fungsi, hari KPI, dan per pengguna** :   
   **Catatan!** Tidak semua kombinasi metrik, fungsi, dan per pengguna tersedia.
  * Metrik: Pendapatan, Sesi (tidak tersedia di tampilan terpadu), Uninstall (copot pemasangan), ROI, In-app event, ROAS.
  * Fungsi: Metrik dihitung menggunakan fungsi. Daftar fungsi bervariasi tergantung pada metrik.
    * ***Sum (Jumlah)**:* total pendapatan pada hari kohort.
    * **Count (Hitung)**
    * **Unique users** (Pengguna unik): jumlah pengguna unik yang melakukan event. Ini berarti, misalnya, jika seorang pengguna membuka aplikasi 10 kali pada hari tertentu, hasil yang ditampilkan adalah 1.
    * **Konversi In-app**: rasio konversi dari instalasi/penargetan ulang ke in-app event. Jumlah pengguna unik yang melakukan in-app event spesifik untuk **pertama kalinya**  dibagi berdasarkan jumlah pengguna unik dalam kohort. Misalnya, jumlah pengguna [unik] dalam kohort adalah 100. Dari jumlah tersebut, 20 pengguna melakukan in-app event spesifik untuk pertama kalinya. Rasio konversi In-app adalah 20/100=20%.
  * **Hari KPI**: Pilih dari Hari 0, Hari 3, Hari 7, dll. Hari 0 adalah hari konversi saja. Hari 3 berarti hari konversi dan tiga hari berikutnya, total empat hari, begitu juga, untuk hari-hari lainnya. Nilai KPI dijumlahkan untuk periode yang dipilih.
  * **Per-pengguna**: saat dipilih, sum (jumlah) atau count (hitung) dibagi berdasarkan jumlah pengguna aplikasi.
  * **Tabel** atau **Grafik:** Grafik menampilkan peringkat 5 atau 10 teratas berdasarkan jumlah pengguna aplikasi dalam kohort. Ini tidak terkait dengan dimensi yang ditampilkan dalam grafik. Tabel menampilkan hingga 50 baris.
  * **On day** (Pada hari): Nilai hanya pada Hari kohort yang ditentukan. Misalnya, dalam kasus Hari 7 berarti bahwa nilai pada hari 7 pasca konversi.
  * **Kumulatif** di mana: Nilai gabungan dari semua hari yang ditentukan dalam Hari. Misalnya, dalam hal Hari 7, artinya total hari konversi dan 7 hari berikutnya.  Perhatikan! Dalam konteks pengguna unik, artinya jumlah kumulatif dari pengguna unik.

</Accordion>

<div id="list-of-dimensions-for-grouping-and-filtering" />

<Accordion title="Daftar dimensi untuk pengelompokkan dan pemfilteran">

| Dimensi | Komentar | Dikelompokkan berdasarkan | Difilter berdasarkan |
| --- | --- | --- | --- |
| <span id="ad"></span>ad |  | ✓ | ✓ |
| <span id="ad-id"></span>ID iklan |  | ✓ | ✓ |
| <span id="adset"></span>adset |  | ✓ | ✓ |
| <span id="adset-id"></span>ID adset |  | ✓ | ✓ |
| <span id="agency"></span>agency |  | ✓ | ✓ |
| <span id="apps"></span>Aplikasi | Relevan saat laporan berisi beberapa aplikasi | ✓ | **x** |
| <span id="attributed-touchtype"></span>Attributed touch-type | Nilai: Klik, tayangan, atau NA (organik) | ✓ | ✓ |
| <span id="campaign"></span>Kampanye |  | ✓ | ✓ |
| <span id="campaign-id"></span>ID kampanye |  | ✓ | ✓ |
| <span id="channel"></span>Channel |  | ✓ | ✓ |
| <span id="conversion-type"></span>Tipe konversi | Ketergantungan jenis kohort:<ul><li>**Akuisisi pengguna**: Install</li><li>**Penargetan ulang**: Interaksi ulang, Atribusi ulang</li></ul> | ✓ | ✓ |
| <span id="country-geo"></span>Negara (Geo) | Berdasarkan alamat IP pengguna | ✓ | ✓ |
| <span id="time-in-the-case-of-daily-granularity-is-the-date-hourly-granularity-is-the-hour-of-the-day-weekly-granularity-is-the-week-of-the-year-monthly-granularity-is-the-month-of-the-year"></span>Waktu. Dalam kasus:<ul><li>Perincian harian adalah tanggal</li><li>Perincian per jam adalah jam dalam sehari</li><li>Perincian mingguan adalah minggu dalam setahun</li><li>Perincian bulanan adalah bulan dalam setahun</li></ul> | Ketergantungan jenis kohort:<ul><li>**Akuisisi pengguna dan terpadu**: Tanggal aplikasi diluncurkan untuk pertama kalinya.</li><li>**Penargetan ulang**: Tanggal aplikasi diluncurkan untuk pertama kalinya setelah interaksi ulang.</li></ul> | ✓ | **x** |
| <span id="install-app-store"></span>Instal App Store | Relevan untuk aplikasi yang menerapkan <Anchor target="_blank" href="/marketers/id/docs/set-up-multi-store-android-attribution">atribusi multi-store:</Anchor> AndroidHubungi CSM Anda untuk mengaktifkan dimensi ini. | ✓ | ✓ |
| <span id="keywords"></span>Keywords | Cari kata kunci yang disediakan oleh mitra terintegrasi | ✓ | ✓ |
| <span id="media-source"></span>Media Source |  | ✓ | ✓ |
| <span id="revenue-type"></span>Jenis Pendapatan | Reguler, Monetisasi Iklan | **x** | ✓ |
| <span id="site-id"></span>ID situs |  | ✓ | ✓ |
| <span id="sub-param-1"></span>Sub Param 1 |  | ✓ | ✓ |

</Accordion>

<div id="using-my-reports-save-and-select-reports" />

<Accordion title="Gunakan Laporan saya—Simpan dan pilih laporan">

* Laporan saya memungkinkan Anda untuk menyimpan pengaturan dashboard saat ini untuk digunakan di masa mendatang.
* Pilih laporan tersimpan untuk menampilkan data kohort terbaru yang tersedia.
* Anda dapat menyimpan satu laporan atau lebih.
* Hanya Anda yang dapat mengakses **My reports** (Laporan saya).

| Fitur | Deskripsi |
| --- | --- |
| Laporan saya | ![MyReports.png](https://files.readme.io/8f49c0e6dee55427bf3a64149ac48f67547967b8cd24aa8de3e34b760708f992-32127933340305.png)<br /><br />Pilih laporan untuk menampilkan tanggal terbaru yang tersedia. |
| Simpan perubahan | Simpan laporan. Catatan: Laporan yang dipilih saat ini ditimpa. |
| Opsi tindakan (![Elipse.png](https://files.readme.io/14b74dc6e733867bd16b6a3594f5f0856d7437462b2e0cf7c12adf11cfa295b3-32127949499409.png)) | <ul><li>**Simpan sebagai file baru**<ul><li>Simpan laporan menggunakan nama laporan lainnya</li><li>[Opsional] Jadikan laporan ini laporan default</li></ul></li><li>**Rename**: Ubah nama laporan</li><li>**Set as default**: Jadikan laporan ini laporan default. Saat Anda membuka Kohort, laporan ini yang ditampilkan terlebih dahulu</li><li>**Delete**: Hapus laporan</li></ul> |

</Accordion>

<div id="partial-data" />

<Accordion title="Data parsial">

Gunakan kontrol **Kohort Waktu Aktual** untuk memilih mode tampilan data:

* [Default] **Waktu aktual:**
  * Data atribusi diperbarui terus menerus dalam waktu aktual termasuk pendapatan.
  * Pembaruan data biaya rata-rata 6 kali sehari, setiap empat jam.
  * Data parsial (ditunjukkan dengan tanda hubung dalam laporan dan grafik) disertakan
* **Harian:** Data diperbarui setiap hari dan tersedia beberapa menit setelah tengah malam. Data setengah harian tidak ditampilkan.

Apa itu data parsial?

Untuk hari tertentu dalam rentang data konversi, jika jumlah hari yang telah berlalu sejak tanggal konversi kurang dari hari kelompok, hari kelompok tersebut berisi data parsial. Artinya data parsial muncul setiap hari saat hari kelompok &lt; tanggal hari ini-tanggal konversi.

</Accordion>

<div id="export-the-cohort-to-a-csv-file" />

<Accordion title="Ekspor kohort ke file CSV">

* Laporan kohort dapat diekspor ke file CSV.
* File CSV dibatasi hingga maksimum 10.000 baris.
* Fungsi ekspor CSV terbatas pada laporan **Kinerja periode retensi pengguna** .
* Nama kolom memiliki akhiran [parsial sama dengan tanda hubung yang ditampilkan pada grafik dan tabel pada antarmuka pengguna.](/docs/cohort-and-retention-dashboard#partial-data)

**Untuk mengekspor laporan kohort ke file CSV:**

* Di sisi kanan atas periode waktu laporan Kohort, klik, klik <Image alt="Download.png" src="https://files.readme.io/50af9c6cde00dada58a1bb89a9eb3e566f316c0e7336af68f4ce403584047a5b-32127933341969.png" width="21px" />(ekspor).  
   File CSV laporan kohort diunduh.

</Accordion>

## Informasi

<div id="cohort-for-agencies" />

<Accordion title="Kohort per agensi">

* Pengiklan perlu memberikan hak akses kepada agensi untuk menggunakan Kohort.
  * Untuk memberikan hak akses kepada agensi, pengiklan:
    * Buka **Konfigurasi** > **Integrasi Aktif.**
    * Pilih agensi.
    * Buka tab izin, aktifkan **Allow access to your retention and cohort reports** (Izinkan akses ke laporan retensi dan kohort Anda).
* Agensi dibatasi untuk mengakses data lalu lintas yang dihasilkan oleh agensi. Mereka tidak dapat melihat data terkait lalu lintas organik atau lalu lintas non-organik yang dihasilkan di tempat lain.

</Accordion>

<div id="use-cases" />

<Accordion title="Gunakan case (kasus)">

#### Jumlah pendapatan berdasarkan negara

**Grafik: Pendapatan kumulatif per pengguna**

[![CohortGraph.png](https://support.appsflyer.com/hc/article_attachments/360003206697)](https://support.appsflyer.com/hc/article_attachments/360003206697)

**Tabel: Pendapatan per hari**

[![CohortTable.png](https://support.appsflyer.com/hc/article_attachments/360003206717)](https://support.appsflyer.com/hc/article_attachments/360003206717)

#### Konversi In-app event

Pengiklan menentukan in-app event af\_purchase. Grafik kohort menampilkan persentasi pengguna aplikasi dalam kohort yang melakukan pembelian seluler. Kita dapat melihat pada hari ke-10 misalnya bahwa hampir 30% (11.11%+9.71%+7.47%) pengguna kohort melakukan pembelian seluler

[.![Kohort-inapp](https://files.readme.io/e365c6b930d765d97155b1fd4384a608cb7eb0339b2b61e4598ee2d5d17d3249-32127949502481.png)](https://files.readme.io/e365c6b930d765d97155b1fd4384a608cb7eb0339b2b61e4598ee2d5d17d3249-32127949502481.png)

</Accordion>

<div id="faq" />

<Accordion title="Pertanyaan Umum">

| Pertanyaan | Jawaban |
| --- | --- |
| <span id="can-i-view-apple-search-ads-keyword-cost-and-roi"></span>Dapatkah saya melihat Apple Search Ads <Anchor target="_blank" href="/marketers/id/docs/apple-ads-integration-setup#analyze-keyword-cost">kata kunci Biaya dan ROI</Anchor>. | Ya, bisa.  <br />Apple Search Ads menyediakan biaya untuk setiap kata kunci per hari yang dirinci berdasarkan Kampanye\Adset\Ad. **Catatan:** perincian berdasarkan Lokasi/negara tidak tersedia. |
| <span id="for-a-given-media-source-why-does-the-same-campaign-name-display-more-than-once"></span>Untuk sumber media tertentu, mengapa nama kampanye yang sama ditampilkan lebih dari sekali? | <ul><li>Jika Anda menggunakan nama kampanye yang sama dengan kampanye yang memiliki ID kampanye berbeda maka namanya ditampilkan lebih dari sekali.</li><li>Anda harus mengalokasikan nama unik ID kampanye</li><li>Saat mengubah nama kampanye, data disesuaikan dengan nama yang terakhir digunakan.</li></ul> |
| <span id="can-i-view-organic-users"></span>Dapatkah saya melihat pengguna organik? | Pengguna organik, secara default disertakan dalam laporan Kohort.<br /><br />**Untuk membatasi laporan Kohort hanya untuk pengguna organik:**<ol><li>Di **Dashboard kohort**, klik tombol **Edit kohort** .</li><li>Di jendela pengaturan Kohort **Filter berdasarkan** > **sumber media** adalah **Organik**:</li></ol>[![cohort_setup_filtered_by_media_source_is_organic.png](https://files.readme.io/ba95397eac2b66a365a2aabb2f56587e78624be5ecd06dd6c0463e19dfe9e26a-32127949503889.png)](https://files.readme.io/ba95397eac2b66a365a2aabb2f56587e78624be5ecd06dd6c0463e19dfe9e26a-32127949503889.png)<ol><li>Klik **Apply changes** (Terapkan perubahan).</li></ol> |
| <span id="can-i-see-data-from-deleted-installs"></span>Bisakah saya melihat data dari penginstalan yang dihapus? | Penginstalan yang dihapus, seperti penginstalan dari SRN yang dihapus karena kebijakan penyimpanan data atau penginstalan yang dihapus GDPR, tidak dapat dilihat di dashboard kelompok.<br /><br />Untuk informasi lebih lanjut, <Anchor target="_blank" href="/marketers/id/docs/user-level-data-retention#partner-data-retention-periods">klik di sini</Anchor>. |
| <span id="can-i-compare-data-for-daily-view-to-data-in-weekly-or-monthly-views"></span>Dapatkah saya membandingkan data untuk tampilan harian dengan data dalam tampilan mingguan atau bulanan? | Tidak mudah membandingkan data dari perincian harian ke perincian mingguan atau bulanan, karena LTV kelompok tidak selaras. <br /><br />Saat melihat kelompok dalam perincian harian, **Hari 0** menampilkan data untuk hari penginstalan. Hari 1 adalah hari setelah penginstalan, Hari 2 adalah 2 hari setelah penginstalan, dst. <br /><br />Saat melihat kelompok dalam perincian mingguan, data ditampilkan untuk semua penginstalan yang dilakukan di **seluruh Minggu 0**. Minggu 1 adalah minggu setelah penginstalan, Minggu 2 adalah 2 minggu setelah penginstalan, dst. <br /><br />Saat melihat kelompok dalam perincian bulanan, data ditampilkan untuk semua penginstalan yang dilakukan di **seluruh Bulan 0**. Bulan 1 adalah bulan setelah penginstalan, Bulan 2 adalah 2 bulan setelah penginstalan, dst. <br /><br />Ini berarti garis waktu LTV tidak selaras. Misalnya, jika Anda melihat data untuk tanggal 9-15 Januari: Jika Anda menggunakan perincian harian, **Hari 0** berisi data untuk hari pertama dari semua **penginstalan yang dilakukan pada tanggal 9-15 Januari.** Dan **Hari 6** berisi data untuk 6 hari pertama setelah penginstalan dari semua penginstalan yang dilakukan pada **9-15 Januari**. Sementara itu, dalam **perincian mingguan**, **Minggu 0** berisi data **seluruh periode** untuk semua penginstalan **yang dilakukan pada 9-15 Januari**. Jadi untuk penginstalan tanggal **9 Januari**, datanya seperti **Hari ke-6**. Tetapi untuk penginstalan pada **15 Januari**, itu seperti **Hari 0**. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Sifat | Catatan |
| --- | --- |
| Akses jaringan iklan ke kohort | Tidak tersedia |
| Akses agensi | Tersedia:<ul><li>Terbatas untuk satu aplikasi.</li><li>Akun hibrida tidak dapat mengakses Kelompok.</li><li>Memerlukan izin akses berdasarkan aplikasi per aplikasi.</li><li>Tidak dapat memilih beberapa aplikasi.</li><li>Akses ke data organik tidak dimungkinkan.</li></ul> |
| Transparansi agensi | Tersedia mulai 10 Januari 2021 |
| Zona waktu khusus aplikasi | <ul><li>Tersedia</li><li>Pengecualian: Dalam semua kasus berikut, AppsFlyer mengabaikan zona waktu khusus aplikasi dan menggunakan zona waktu default yaitu UTC +0:<ul><li>Laporan kohort berisi data dari beberapa aplikasi, dan aplikasi memiliki zona waktu berbeda.</li><li>Semua aplikasi memiliki zona waktu yang sama, dan zona waktu untuk setidaknya salah satu aplikasi berubah selama periode laporan kohort. Untuk menentukan periode laporan:<ul><li>Tanggal mulai: Tanggal pertama dalam rentang tanggal konversi</li><li>Tanggal akhir: Dihitung dengan menambahkan jumlah hari dalam durasi tampilan ke tanggal terakhir dalam rentang tanggal konversi. Misalnya: Tanggal terakhir: 1 Jan 2019. Durasi laporan: 30 hari. Tanggal akhir: 31 Januari 2019.</li></ul></li><li>Data mingguan dan bulanan akan ditampilkan dalam zona waktu UTC</li></ul></li></ul> |
| Mata uang khusus aplikasi | <ul><li>Tersedia</li><li>Pengecualian: Semua aplikasi perlu menggunakan mata uang yang sama. Jika tidak, USD digunakan.</li></ul> |
| Batasan | <ul><li>File unduhan CSV:<ul><li>Maksimal 10.000 baris</li><li>Tidak tersedia untuk tren KPI berdasarkan waktu atribusi.</li></ul></li><li>Grafik: menampilkan peringkat 5 atau 10 teratas yang diurutkan berdasarkan jumlah pengguna dalam kelompok.</li><li>Tabel: Menampilkan 50 baris pertama yang diurutkan berdasarkan jumlah pengguna dalam kohort.</li><li>Penginstalan ulang: Jika event setelah penginstalan dianggap organik tanpa atribut, mereka tidak disertakan dalam Kelompok. Jika mereka dikaitkan dengan penginstalan pertama, memang demikian. <Anchor target="_blank" href="/marketers/id/docs/measure-reinstalls#in-app-event-dan-bagaimana-mereka-dikaitkan">Pelajari lebih lanjut</Anchor></li><li>Biaya: AppsFlyer tidak melaporkan data biaya untuk kata kunci yang berisi huruf besar dalam laporan kohort atau API kohort.</li><li>Batas ekspor 10 CSV per menit dan 100 per hari (per pengguna).</li><li>Batas 20 kueri data per menit dan 500 per hari (per pengguna). Mengubah periode waktu, pengelompokan, KPI, dll. dianggap sebagai kueri baru.</li></ul> |
| Data organik | Termasuk |
| Data non-organik | Termasuk |
| Kesegaran data | <ul><li><Anchor target="_blank" href="/marketers/id/docs/about-data-freshness-and-timezone-support#eod">Waktu sebenarnya</Anchor></li><li>Pengecualian:<ul><li>Kelompok harian:<ul><li>Metrik biaya, pendapatan iklan, dan copot penginstalan diperbarui Setiap hari.</li><li>Uninstall dihitung sekali sehari menggunakan jam UTC.</li></ul></li><li>Kelompok mingguan dan bulanan:<ul><li>Data waktu sebenarnya tidak tersedia. Data hanya akan muncul setelah selesai (artinya di akhir minggu atau bulan).<br />Namun, data, di mana beberapa data penginstalan telah selesai, seperti beberapa data telah selesai (waktu setelah penginstalan) dan lainnya belum dimulai, akan ditampilkan.</li></ul></li></ul></li></ul> |
| Data historis | <ul><li>Kelompok harian: 2 tahun</li><li>Kelompok mingguan/bulanan: 3 tahun</li></ul> |
| Geo/negara | <ul><li>Tersedia</li><li>Saat geografi tidak diketahui (T/A), data pendapatan iklan tidak ditampilkan saat pengelompokan menurut geo.</li></ul> |
| Jumlah sesi | Jumlah sesi untuk Hari 0 di tampilan Penargetan Ulang mungkin lebih rendah dari jumlah pengguna.<br />Ada beberapa alasan hal ini bisa terjadi. Yang paling umum adalah:<ul><li>Sesi keterlibatan ulang telah diatribusikan sebelum keterlibatan ulang dicatat. Dalam hal ini, itu tidak akan dikaitkan dengan sesi penargetan ulang</li><li>Memfilter menurut setelan lain seperti **Waktu minimal antar sesi**. Dalam hal ini, keterlibatan ulang dicatat. Namun, sesi tersebut difilter dan tidak akan dicatat</li></ul> |
| Penargetan Ulang dan Data terpadu | Data sesi bulanan hanya tersedia mulai 1 September 2021 dan seterusnya |
| Pendapatan Iklan | <ul><li>Tidak tersedia saat melihat kelompok dengan rincian per jam.</li><li>Mungkin ada perbedaan antara jumlah pendapatan iklan yang ditampilkan di dashboard Kelompok dan Ikhtisar. Ini terjadi saat jaringan melaporkan pendapatan dalam UTC dan aplikasi memiliki pengaturan zona waktu yang berbeda.</li><li>Untuk peristiwa af\_ad\_revenue, metrik pengguna unik tidak tersedia jika jenis agregasinya adalah:<ul><li>"Kumulatif".</li><li>"Pada hari", untuk tanggal antara 5 Oktober 2022-16 Februari 2023.</li></ul></li></ul> |
| Perincian minggu dan bulan | <ul><li>Perincian minggu dan bulan hanya tersedia di dashboard Kelompok.</li><li>Metrik **pengguna unik** dan **rasio konversi** tidak tersedia jika data menyertakan penginstalan dari sebelum November 2022.</li><li>Metrik terkait biaya tidak tersedia saat mengelompokkan berdasarkan Minggu atau Bulan. Ini termasuk:</li></ul><ul><li>Biaya</li><li>eCPI</li><li>ROI</li><li>ROAS</li></ul><ul><li>Data historis hanya tersedia dari tahun 2021 dan seterusnya.</li></ul> |
| Periode kelompok | <ul><li>Periode konversi dirujuk sebagai 0 (Jam 0, Hari 0, Minggu 0, atau Bulan 0). Periode berikutnya setelah konversi disebut sebagai 1 (Jam 1, Hari 1, Minggu 1, atau Bulan 1), dan seterusnya.</li><li>Di AppsFlyer, periode kelompok tidak memperhitungkan stempel waktu penginstalan tertentu. Sebaliknya, jam kelompok dibulatkan ke jam terdekat, dan hari, minggu, dan bulan kelompok didasarkan pada hari, minggu, atau bulan kalender. Hal ini dapat menyebabkan perbedaan saat membandingkan data kelompok AppsFlyer dengan data kelompok jaringan lain, di mana semua periode kelompok ditentukan oleh stempel waktu penginstalan tertentu (artinya satu jam adalah 60 menit stempel waktu setelah penginstalan, satu hari adalah periode 24 jam setelah penginstalan setelah stempel waktu penginstalan, dll.).</li></ul> |

</Accordion>

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/aggregated-and-analytics-reporting-overview#cohort-flavors">Perbedaan antara rasa Kohort</Anchor>

<div data-zendesk-anchors="cohort-dashboard=dashboard-kohort 01H7WE9R0CX9C2MQHNK1MB15AM=dashboard-kohort 01H7WE9R0DSQ4E0WTXPTF43S08=tips 01H7WE9R0D15RA4F3ZN6Y1Q30N=cohort-principles 01H7WE9R0DJA1ZNDR265WEWVKH=example-user-lifetime-performance-trend-vs-kpi-by-attribution-time-trend 01H7WE9R0DTNKK17Y0XXZQRXD0=metrics-available using-cohort=menggunakan-kohort 01H7WE9R0DZDRBYYCM3ACSHXMS=menggunakan-kohort 01H7WE9R0DRV7CENP28NB0TNDK=setting-up-an-analysis trend-type%E2%80%94user-lifetime-performance=trend-type-user-lifetime-performance 01H7WE9R0D76VN0K95BF3ZBTH6=trend-type-user-lifetime-performance trend-type%E2%80%94kpi-by-attribution-time=trend-type-kpi-by-attribution-time 01H7WE9R0DN3ZPVTDGJ72QWEV0=trend-type-kpi-by-attribution-time 01H7WE9R0DSFAXSK2C1BBSJJCC=list-of-dimensions-for-grouping-and-filtering time-in-the-case-of%0A%0Adaily-granularity-is-the-date%0Ahourly-granularity-is-the-hour-of-the-day%0Aweekly-granularity-is-the-week-of-the-year%0Amonthly-granularity-is-the-month-of-the-year=time-in-the-case-of-daily-granularity-is-the-date-hourly-granularity-is-the-hour-of-the-day-weekly-granularity-is-the-week-of-the-year-monthly-granularity-is-the-month-of-the-year using-my-reports%E2%80%94save-and-select-reports=using-my-reports-save-and-select-reports 01H7WE9R0ERMN0ZNN1RDBD7SYA=using-my-reports-save-and-select-reports 01H7WE9R0E6BPEKRQKAMZVD12Y=partial-data 01H7WE9R0EMP5YPK4RSF06PP3B=export-the-cohort-to-a-csv-file information=informasi 01H7WE9R0ETQW8WCRW8Q2NSNFF=informasi 01H7WE9R0E8JHK7J4RZB50TAHE=cohort-for-agencies 01H7WE9R0E153RM1BE5BWZ7XEE=use-cases revenue-sum-by-country=jumlah-pendapatan-berdasarkan-negara 01H7WE9R0FNZC0QWNDNCR1CKH2=jumlah-pendapatan-berdasarkan-negara inapp-event-conversion=konversi-in-app-event 01H7WE9R0FC8BV8F2STR6P9J3M=konversi-in-app-event 01H7WE9R0FYH0CMQ3E6KMT5EKH=faq 01H7WE9R0F4GZ3WA21N1YF4AAG=traits-and-limitations h_01HE0CSHCJRXXG8WXRBHCWN7AC=lihat-juga" />
