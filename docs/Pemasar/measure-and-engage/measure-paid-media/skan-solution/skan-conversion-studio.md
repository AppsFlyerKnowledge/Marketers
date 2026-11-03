---
title: SKAN Conversion Studio
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
  created_at: '2021-07-08T09:26:58Z'
  edited_at: '2023-10-26T14:42:46Z'
  id: 4403727223185
  locale: id
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/id/articles/4403727223185
---
> **Sekilas**: Gunakan SKAN Conversion Studio untuk menetapkan interaksi pengguna mana dalam aplikasi yang akan diukur, dan untuk berapa lama. Ukur pendapatan, konversi, interaksi, dan retensi selama periode pasca-penginstalan terbatas. Dengan menambahkan pengukuran Single Source of Truth, kami dapat memberi tahu Anda jika pengguna diatribusikan oleh AppsFlyer dan SKAN.

<Embed title="SKAN 4 Conversion Studio (termasuk kunci periode waktu)" typeOfEmbed="iframe" url="https://player.vimeo.com/video/810457121?h=a3acc3ee41&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" providerUrl="https://player.vimeo.com" />

## Dasar-dasar SKAN Conversion Studio

Dalam alur atribusi SKAdNetwork (SKAN), perangkat iOS mengirimkan postback SKAN yang berisi nilai konversi (CV) terbaru setelah setiap jendela pengukuran.

Untuk SKAN 3 ke bawah, ada 1 postback yang masuk setelah Jendela Aktivitas awal berakhir. Jendela Aktivitas bisa 12 jam-63 hari. CV dibatasi hingga 6 bit, menghasilkan 64 kemungkinan nilai (0-63).

Untuk SKAN 4, ada 3 postback yang tiba setelah masing-masing dari 3 periode waktu berakhir, masing-masing setelah hari ke 2, 7, dan 35. Untuk:

* Jendela 1, CV halus dibatasi hingga 6 bit, menghasilkan 64 kemungkinan nilai (0-63).
* Jendela 1-3, CV kasar terbatas pada CV rendah, sedang, atau tinggi. (Jendela 2 dan 3 tidak memiliki CV yang halus).

Keterbatasan CV ini berarti Anda mungkin perlu membuat beberapa pilihan sulit tentang cara menggunakan 64 kemungkinan nilai tersebut untuk CV halus dan 3 kemungkinan nilai untuk CV kasar.

Studio Konversi memberi Anda fleksibilitas maksimum untuk membuat setiap nilai dan jumlah bit yang mungkin. Anda menentukan dengan tepat data pengukuran apa yang harus dikodekan dalam CV—termasuk aktivitas apa dan mengukur untuk berapa lama selama periode pasca-penginstalan. Terdapat beberapa cara pengukuran yang dapat Anda gunakan untuk mengonfigurasi pengaturan CV Anda.

| Jenis | Mode pengukuran | Deskripsi | Jendela aktivitas |
| --- | --- | --- | --- |
| Fleksibel | [SKAN 4.0](/docs/skan-conversion-studio#skan-4)<br /><br />[Praktik terbaik] | Tetapkan kombinasi pendapatan, konversi (in-app event), dan pengukuran interaksi selama 3 jendela pengukuran yang dapat dikonfigurasi.<br /><br />3 jendela mengukur 3 periode waktu pasca-penginstalan yang berbeda, tidak tumpang tindih. Artinya, jendela 2 mengukur hari ke 3-7 pasca-penginstalan, bukan hari ke 0-7. | <ul><li>Jendela 1: 1-2 hari</li><li>Jendela 2: 3-7 hari</li><li>Jendela 3: 8-35 hari</li></ul> |
| Fleksibel | Kustom | Tetapkan kombinasi pendapatan, konversi (in-app event), dan pengukuran interaksi selama jendela aktivitas yang dapat dikonfigurasi. | 12-1512 j (default hingga 72 jam, tetapi dapat diperpanjang) |
| Tetap | Pendapatan<br /><br />[Default]<br /><br />[Legasi] | Ukur pendapatan menggunakan salah satu rentang berikut:<ul><li>$1-$630 dalam kelipatan $10</li><li>$1-$63 dalam kelipatan $1</li><li>$0.01-$0.63 dalam kelipatan $0.01</li></ul> | 24 j |
| Tetap | Konversi<br /><br />[Legasi] | Pilih 1-6 in-app event. | 24 j |
| Tetap | Interaksi<br /><br />[Legasi] | Berapa kali pengguna melakukan suatu event | 24 j |
| Fleksibel | <Anchor target="_blank" href="/marketers/id/docs/skan-cv-decode-map-your-cv-to-events">Decode</Anchor> | <ul><li>Buat CV Anda sendiri untuk pemetaan event dan atur CV di aplikasi sendiri. Gunakan opsi ini jika Anda tidak dapat mengintegrasikan AppsFlyer SDK ke aplikasi Anda. Untuk menggunakan Decode, buka **SKAN Conversion Studio,** klik opsi (⋮), pilih **Upload custom decode mapping file**.</li></ul> | 12-1512j (63 hari) |

**Tips!** Lakukan eksperimen dengan Conversion Studio. Di AppsFlyer, buka > **Configuration** > **SKAN Conversion Studio**.

<div id="measurement-principles-and-definitions" />

<Accordion title="Prinsip dan definisi pengukuran">

**Definisi**

* **Jendela pengukuran SKAN**: Relevan untuk SKAN 4+. Ada 3 periode waktu (jendela) saat aktivitas setelah penginstalan pengguna diukur:
  * Jendela 1: 1-2 hari
  * Jendela 2: 3-7 hari
  * Jendela 3: 8-35 hari
  * 3 jendela mengukur 3 periode waktu pasca-penginstalan yang berbeda, tidak tumpang tindih. Artinya, jendela 2 mengukur hari ke 3-7 pasca-penginstalan, bukan hari ke 0-7.
* **Jendela Aktivitas:** Relevan untuk SKAN 3 dan di bawahnya. Memiliki durasi yang sudah diatur, default-nya 24 jam, dimulai dengan aplikasi pertama yang dibuka. Jika Anda menggunakan SKAN 4+ tetapi perangkat pengguna atau jaringan iklan belum mendukung SKAN 4, Jendela Aktivitas adalah 48 jam.
* **Nilai Konversi (Conversion Value - CV)**: Pengukuran kualitas pengguna dilaporkan di postback yang dikirimkan oleh iOS di akhir jendela SKAN 4 atau untuk SKAN 3 dan di bawahnya pada akhir Jendela Aktivitas. SDK AppsFlyer mengatur CV untuk Anda. Namun, jika Anda ingin mengatur CV menggunakan <Anchor target="_blank" href="/marketers/id/docs/skan-cv-decode-map-your-cv-to-events">Decode</Anchor> untuk mengunggah file pemetaan CV Anda.
  * Untuk SKAN 4+, ada nilai konversi halus dan kasar.
* **Kapasitas nilai konversi:** Jumlah CV yang diperlukan untuk memetakan pengaturan Anda. Semakin banyak komponen dan elemen pengukuran yang Anda pilih, semakin banyak kapasitas nilai konversi yang diperlukan. Setiap rentang atau elemen pengaturan yang dipilih menggunakan kapasitas nilai konversi. (Dan setiap unit pengaturan tambahan yang disertakan dalam satu komponen menggunakan kapasitas tersebut secara eksponensial!) [Contoh penggunaan CV yang dimaksimalkan.](/docs/skan-conversion-studio#maximized-custom-cv-examples)
* **Single Source of Truth (SSOT):** <Anchor target="_blank" href="/marketers/id/docs/single-source-of-truth-ssot-guide-for-ios-attribution">Mekanisme untuk menandai</Anchor> jika pengguna diatribusikan oleh SKAN dan metode pencocokan atribusi lainnya. Tanda tersebut digunakan untuk menghilangkan data penginstalan duplikat dalam data lengkap SKAN dan untuk menghitung metrik kinerja yang sebenarnya.
* **Komponen pengukuran**:  
  * **Pendapatan:** Mengukur pendapatan yang dihasilkan
  * **In-app event**: Mengukur konversi (jumlah pengguna unik yang melakukan peristiwa),  
    interaksi (berapa kali acara dilakukan), atau keduanya.
  * **Funnel**: Mengukur terjadinya in-app event berdasarkan daftar peristiwa berurutan di funnel. Seorang pengguna yang melakukan peristiwa apa pun di funnel dianggap telah melakukan semua peristiwa sebelum peristiwa tersebut.
  * **Prioritas**: Komponen yang berisi pendapatan, in-app event, atau keduanya.
  * **Prediksi:** Menggunakan algoritme pembelajaran mesin canggih untuk memberikan prediksi keberhasilan kampanye berbasis LTV yang akurat. KPI tingkat pengguna yang diprediksi (termasuk prediksi pendapatan dan retensi) dikodekan dan dikirimkan ke SKAN sebagai nilai konversi tunggal, yang kemudian dilaporkan SKAN sebagai postback, bersama dengan ID kampanye dan sumber atribusi.

**Prinsip**

* **![Admin.png](https://files.readme.io/74a71649d541921d2b61425323cc4cf5b669cd4d5665294d0813a3e9230bd11d-4405725144977.png) Khusus admin:** Hanya admin yang dapat menyimpan pengaturan Conversion Studio. Pengguna akun dapat melihat pengaturan.
* Pada waktu tertentu, hanya satu mode yang aktif.
* Untuk mode tertentu, AppsFlyer memetakan kombinasi yang ditentukan oleh pengaturan Anda ke CV. Anda dapat [melihat dan mengunduh tabel pemetaan](/docs/skan-conversion-studio#view-cv-mapping).
* Di aplikasi, AppsFlyer mengatur CV pasca setiap tindakan pengguna yang terukur menggunakan mode pengukuran aktif saat pengguna meluncurkan aplikasi untuk pertama kalinya.
* iOS mempertimbangkan <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows">anonimitas kerumunan Apple</Anchor> sebelum mengisi CV di postback.
* Tindakan pengguna yang terjadi setelah akhir jendela akan diabaikan.
* Dashboard dan laporan SKAN:
  * Layout dan metrik dasbor SKAN bergantung pada mode dan konfigurasinya.
  * Layout diperbarui setiap hari berdasarkan mode aktif pada tengah malam UTC. Perkiraan pembaruan layout akan tersedia pada pukul 05:00 UTC.
  * Di SKAN 4, Khusus dan Dekode, data organik untuk in-app event dan keseluruhan pendapatan tidak tersedia.

#### **prinsip S2S**

Tindakan terukur dapat dilaporkan oleh API [server-to-server (S2S)](/docs/skan-conversion-studio#report-events-by-servertoserver-api) . Pertimbangkan hal berikut per mode:

* SKAN 4 dan Kustom: S2S selalu aktif.
* Decode: S2S tidak cocok untuk S2S dan tidak tersedia. AppsFlyer tidak mengatur CV dalam mode ini.
* Model pendapatan, konversi, dan interaksi: Anda harus mengaktifkan [perekaman event S2S](/docs/skan-conversion-studio#report-events-by-servertoserver-api) sebelum mengirim events.

</Accordion>

## Mengatur nilai konversi di Studio Konversi SKAN

Ada beberapa mode tersedia di Studio Konversi SKAN untuk mengatur nilai konversi:

* SKAN 4: Menggunakan komponen pengukuran berbeda, seperti pendapatan, in-app event, prioritas, dan Single Source of Truth, untuk menentukan apa yang diukur selama masing-masing dari tiga jendela pengukuran..
* Kustom: Menggunakan komponen pengukuran berbeda, seperti pendapatan, in-app event, prioritas, dan Single Source of Truth, untuk menentukan apa yang diukur selama Jendela Aktivitas.
* Mode tetap: Mengukur nilai pengguna menggunakan satu dari pengukuran berikut ini:
  * Pendapatan
  * Konversi
  * Interaksi

Pelajari lebih banyak tentang mode pengukuran berbeda di bagian berikut ini.

> 🚧 **Penting!**
>
> Menetapkan nilai konversi di SKAN Conversion Studio harus dilakukan oleh admin atau pengguna akun yang memiliki izin **Kelola** di **SKAN Conversion Studio**.
>
> **Untuk melihat atau mengubah izin pengguna:**
>
> 1. Di AppsFlyer, di klik kanan atas alamat email Anda.
> 2. Pilih **Manajemen Pengguna**> Pilih pengguna.
> 3. Jika diperlukan, berikan pengguna izin **Kelola** di **SKAN Conversion Studio**. Untuk informasi selengkapnya tentang izin, lihat <Anchor target="_blank" href="/marketers/id/docs/user-management">Manajemen Pengguna</Anchor>.

<div id="skan-4" />

<Accordion title="SKAN 4">

Di SKAN 4, Anda menggunakan komponen pengukuran berbeda seperti pendapatan, in-app event, prioritas, dan Single Source of Truth, untuk menentukan apa yang diukur selama setiap dari tiga jendela pengukuran. Bersama-sama, komponen menciptakan mode pengukuran SKAN 4 Anda.

Jika Anda upgrade ke SKAN 4 dari mode SKAN sebelumnya, pemetaan skema Anda saat ini dibawa ke konfigurasi halus jendela 1. AppsFlyer secara otomatis memetakan nilai kasar untuk Anda untuk jendela 1-3.

Untuk mengatur SKAN 4 secara manual, lakukan eksperimen dengan opsi berbeda. Saat Anda membuat perubahan, ringkasan **Kapasitas nilai Konversi** diperbarui. Optimalkan pengaturan Anda untuk mengumpulkan data yang paling berharga bagi Anda tanpa melebihi kapasitas. Lihat [Penghitungan kapasitas nilai Konversi.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

Catatan:**Jika Anda upgrade ke SKAN 4 dari mode SKAN sebelumnya, pemetaan skema Anda saat ini dibawa ke pengukuran halus dan AppsFlyer akan memetakan nilai kasar secara otomatis untuk Anda. Jika Anda baru mengenal SKAN&lt; AppsFlyer menyediakan pemetaan default awal.**

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Untuk mengatur nilai konversi secara manual di Studio Konversi menggunakan mode SKAN 4:**

1. Di dashboard AppsFlyer, buka**Configurations** > **SKAN Conversion Studio.**
2. Klik opsi (⋮) untuk menampilkan menu opsi dan memastikan bahwa **pengukuran SKAN** diaktifkan. **Catatan**! Jika tidak aktif, SDK tidak memanggil fungsi SKAN iOS seperti *registerAppForAdNetworkAttribution*, *updateConversionValue.*
3. Pilih **mode pengukuran** SKAN 4.0.
4. Klik **Teruskan**.  
   Pengaturan untuk **Jendela 1 (1-2 hari) CV** halus terbuka.
5. [Opsional] Nyalakan **Single Source of Truth (SSOT)**.  
   Mekanisme SSOT menandai (dan menduplikasi) penginstalan yang dilaporkan oleh lebih dari satu metode pencocokan atribusi. <Anchor target="_blank" href="/marketers/id/docs/single-source-of-truth-ssot-guide-for-ios-attribution">Pelajari lebih lanjut</Anchor>
6. Klik **+ Tambahkan pengukuran** untuk menambahkan [komponen pengukuranyang](/docs/skan-conversion-studio#komponen-pengukuran) berbeda .  
   Bagian berikut merinci opsi dan komponen pengaturan. Gunakan mereka sebagai panduan saat Anda bereksperimen dengan pengaturan pengukuran SKAN yang berbeda:
   * Pendapatan
   * In-app event
   * Corong (Funnel)
   * Prioritas
   * Prediksi
7. Klik **Coarse** dan ulangi Langkah 6-7 untuk mengatur **Periode Waktu 1 (1-2 hari) kasar** CV.   
   **Catatan**: 
   * Hanya komponen Pendapatan dan pengukuran in-app event yang tersedia.
   * CV rendah harus menjadi sesi pengguna untuk memastikan postback dikirim.
8. [Opsional] Aktifkan **Kunci jendela** dan atur kondisi (waktu atau nilai konversi kasar) untuk mengunci jendela SKAN lebih awal dari default. [Pelajari lebih lanjut](/docs/skan-conversion-studio#lock-window)
9. Klik **Periode Waktu 2 (3-7 hari)** dan ulangi Langkah 6-8 untuk mengatur periode waktu 2 CV.   
   **Catatan**: 
   * Hanya komponen Pendapatan dan pengukuran in-app event yang tersedia.
   * [Direkomendasikan] CV rendah harus menjadi sesi pengguna.
10. Klik **Periode Waktu 3 (8-35 hari)** dan ulangi Langkah 6-8 untuk mengatur periode waktu 3 CV.   
    **Catatan**: 
    * Hanya komponen Pendapatan dan pengukuran in-app event yang tersedia.
    * [Direkomendasikan] CV rendah harus menjadi sesi pengguna.
11. Klik **Save**.
12. Verifikasi bahwa pemetaan postback in-app event mitra Anda memetakan event yang telah Anda konfigurasikan.

</Accordion>

<div id="custom" />

<Accordion title="Kustom">

Di Kustom, Anda menggunakan komponen pengukuran yang berbeda seperti pendapatan, in-app event, prioritas, dan Single Source of Truth, untuk  menentukan apa yang diukur dan mengatur jendela aktivitas untuk menentukan berapa lama dan pada interval apa pengukuran dilakukan. Bersama-sama, komponen membuat mode pengukuran Kustom Anda. 

Untuk mengatur Kustom, lakukan eksperimen dengan opsi berbeda. Saat Anda membuat perubahan, ringkasan **Kapasitas nilai Konversi** diperbarui. Optimalkan pengaturan Anda untuk mengumpulkan data yang paling berharga bagi Anda tanpa melebihi kapasitas. Lihat [Penghitungan kapasitas nilai Konversi.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Untuk mengatur nilai konversi secara manual di Studio Konversi menggunakan mode Kustom:**

1. Di dashboard AppsFlyer, buka**Configurations** > **SKAN Conversion Studio.**
2. Klik opsi (⋮) untuk menampilkan menu opsi dan memastikan bahwa **pengukuran SKAN** diaktifkan. **Catatan**! Jika tidak aktif, SDK tidak memanggil fungsi SKAN iOS seperti *registerAppForAdNetworkAttribution*, *updateConversionValue.*
3. Pilih mode pengukuran **Custom**.
4. Klik **Continue**.
5. [Opsional] Nyalakan **Single Source of Truth (SSOT)**.  
   Mekanisme SSOT menandai (dan menduplikasi) penginstalan yang dilaporkan oleh lebih dari satu metode pencocokan atribusi. <Anchor target="_blank" href="/marketers/id/docs/single-source-of-truth-ssot-guide-for-ios-attribution">Pelajari lebih lanjut</Anchor>
6. Klik **+ Add measurement** untuk menambah komponen pengukuran berbeda.  
   Bagian berikut ini memberikan detail tentang opsi pengaturan dan komponen. Gunakan bagian tersebut sebagai panduan saat Anda bereksperimen dengan pengaturan pengukuran SKAN yang berbeda:
   * Pendapatan
   * In-app event
   * Corong (Funnel)
   * Prioritas
   * Prediksi
7. Atur durasi jendela Aktivitas (12 jam-63 hari) selama Anda ingin mengukur aktivitas pengguna.  
   **Timer aktivitas** default memungkinkan Anda mengatur jendela ke 24-72 jam. Dan pengaturan **Interval** default memungkinkan Anda mengatur 12 atau 24 jam. Gunakan **Jendela khusus** untuk memperpanjang jendela aktivitas hingga 63 hari dan mengatur interval yang lebih lama.
8. Klik **Save**.
9. Verifikasi bahwa pemetaan postback in-app event mitra Anda memetakan event yang telah Anda konfigurasikan.

</Accordion>

<div id="fixed-modes" />

<Accordion title="Mode tetap">

Menggunakan mode tetap, Anda dapat mengukur nilai pengguna menggunakan salah satu pengukuran:

* * Pendapatan
  * Konversi
  * Interaksi

Saat Anda membuat perubahan terhadap pengaturan mode, **ringkasan Kapasitas nilai konversi** diperbarui. Optimalkan pengaturan Anda untuk menangkap data yang paling bernilai bagi Anda tanpa melebihi kapasitas. Lihat [Penghitungan kapasitas nilai konversi.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

**Perhatikan!**

* Pengukuran mode tetap adalah untuk jendela aktivitas 24 jam yang dimulai dengan aplikasi pertama yang terbuka.
* Jika Anda ingin mengirim event menggunakan S2S, Anda harus secara eksplisit mengaktifkan [SKAN S2S](/docs/skan-conversion-studio#report-events-by-servertoserver-api)

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Untuk mengatur nilai konversi secara manual di Studio Konversi menggunakan mode tetap:**

1. Di dashboard AppsFlyer, buka**Configurations** > **SKAN Conversion Studio.**
2. Klik opsi (⋮) untuk menampilkan menu opsi dan:
   * Pastikan **pengukuran SKAN** diaktifkan. **Catatan**! Jika tidak aktif, SDK tidak memanggil fungsi SKAN iOS seperti *registerAppForAdNetworkAttribution*, *updateConversionValue.*
   * [Opsional] [Aktifkan pengiriman peristiwa dengan S2S](/docs/skan-conversion-studio#report-events-by-servertoserver-api). Tersedia jika mode yang dipilih adalah pendapatan, konversi, atau interaksi.
3. Pilih mode pengukuran tetap.
4. Ikuti informasi dan instruksi di tabel yang mengikuti untuk mode pengukuran tetap yang Anda pilih.
5. Klik **Simpan**.
6. Verifikasi bahwa pemetaan postback in-app event mitra Anda memetakan event yang telah Anda konfigurasikan.

#### Pengukuran mode tetap

| Mode pengukuran | Deskripsi |
| --- | --- |
| [Default] Pendapatan | ![RevenueFixed.png](https://files.readme.io/ee0882a8b76e50c6fc0ce9bdb04934f3c22324bcaeb15181caf685b00c014a80-4406058625809.png)<br /><br />**Pendapatan yang dihasilkan selama jendela aktivitas 24 jam.**<br /><br />Pilih kurs unit-ke-USD dari salah satu dari berikut ini:<ul><li>$0,01 untuk mengukur hingga $0,63</li><li>$1 untuk mengukur hingga $63</li><li>$10 untuk mengukur hingga $630</li></ul>AppsFlyer secara otomatis mengisi 63 rentang pengukuran pendapatan. `af_skad_revenue` harus dipetakan. Di dasbor, pendapatan dicatat sebagai rentang maksimum. Misalnya, jika kisarannya adalah $60-$61, pendapatan yang dicatat adalah $61. Perhatikan! Pendapatan kustom menggunakan metode yang berbeda untuk menghitung pendapatan.<br /><br />**Metrik yang tersedia:**<ul><li>Pendapatan</li><li>ROI</li><li>ROAS</li><li>ARPU: Pendapatan/pengguna menginstal aplikasi</li><li>Tingkat konversi pengguna: Pengguna melakukan pembelian/pengguna menginstal aplikasi</li><li>eCPA</li></ul> |
| Konversi | ![mceclip0.png](https://files.readme.io/29535e45638cb2b1eecdf43e4fbee0fa52665c90aefe064caaaac9d0fc98472f-4406052008593.png)<br /><br />**In-app event dilakukan satu kali atau lebih selama jendela aktivitas 24 jam**<br /><br />**Pengaturan** :<ul><li>Pilih 1-6 in-app event untuk diukur dari daftar drop-down. Batasan: Daftar ini terbatas pada 300 event teratas selama 30 hari sebelumnya.</li><li>Di dasbor SKAdNetwork, pilih event tertentu sebagai <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings">event konversi</Anchor>.</li></ul>**Metrik per in-app event:**<ul><li>Jumlah pengguna yang melakukan event</li><li>Tingkat konversi: Pengguna yang melakukan Event Konversi/pengguna yang menginstal aplikasi</li><li>eCPA</li><li>Sesi (menggunakan event *af\_app\_opened* )</li></ul>Contoh jumlah pengguna:<ul><li>Penyelesaian pendaftaran</li><li>Melakukan pembelian</li><li>Mencapai level permainan</li></ul>**Klarifikasi!** Gunakan pengukuran konversi untuk menghitung **apakah** pengguna melakukan suatu event. Untuk menghitung berapa kali pengguna melakukan suatu event, gunakan pengukuran interaksi. |
| Interaksi | ![mceclip1.png](https://files.readme.io/51b38d6693e843f04fe7ce02706ae2959d88a047606b41cccad6ed09a46eea39-4406058637841.png)<br /><br />**Berapa kali pengguna melakukan in-app event tertentu selama Jendela Aktivitas**<br /><br />**Pengaturan:**<ul><li>Pilih in-app event dari daftar tarik-turun.</li><li>Pilihan in-app juga ditetapkan sebagai Event Konversi.</li><li>Rentang nilai: 0-63</li></ul>**Metrik untuk in-app event**:<ul><li>Jumlah pengguna yang melakukan event</li><li>Jumlah rata-rata event per pengguna</li><li>Rasio konversi</li><li>eCPA</li><li>Sesi</li></ul>Contoh:<ul><li>Ukur berapa kali:<ul><li>pengguna membuka aplikasi</li><li>pengguna melihat iklan</li></ul></li></ul> |

</Accordion>

<div id="decode" />

<Accordion title="Decode">

Buat CV Anda sendiri ke pemetaan event dan atur sendiri CV di aplikasi. Gunakan opsi ini jika Anda tidak dapat mengintegrasikan AppsFlyer SDK ke aplikasi Anda.

**Untuk menggunakan Decode**:

1. Di dashboard AppsFlyer, buka**Configurations** > **SKAN Conversion Studio.**
2. Klik opsi (⋮) untuk menampilkan menu opsi dan:
   * Pastikan **pengukuran SKAN** diaktifkan. **Catatan**! Jika tidak aktif, SDK tidak memanggil fungsi SKAN iOS seperti *registerAppForAdNetworkAttribution*, *updateConversionValue.*
   * Unggah file pemetaan Decode Anda.
3. Klik **Simpan**.
4. Verifikasi bahwa pemetaan postback in-app event mitra Anda memetakan event yang telah Anda konfigurasikan.

</Accordion>

## Komponen pengukuran

<div id="single-source-of-truth" />

<Accordion title="Single Source of Truth">

<table><tbody><tr><td colspan="2"><p><img alt="SSOTControl.png" src="https://files.readme.io/77570ca922d33a0ef3df4b5a42904452c07b9b472ea4c68c8390155ed2bc53ed-4458326657553.png"/></p><p><a href="./single-source-of-truth-ssot-guide-for-ios-attribution" target="_blank">Mekanisme Single Source of Truth (SSOT)</a> menandai (dan menduplikasi) penginstalan yang dilaporkan oleh lebih dari satu metode pencocokan atribusi. Dengan kata lain, SKAN dan metode lainnya. Tanda (flag) tersedia di laporan data lengkap SKAN dan dipertimbangkan dalam menghitung metrik di dashboard Overview <a href="./single-source-of-truth-ssot-guide-for-ios-attribution#dasbor-ikhtisar-single-source-of-truth" target="_blank">tampilan SSOT</a>. </p></td></tr><tr><td><p>Wajib</p></td><td>Tidak</td></tr><tr><td><p>Boleh digunakan berkali-kali</p></td><td>Tidak</td></tr><tr><td><p>Opsi pengaturan</p></td><td><p>jika SSOT aktif, CV diatur sehingga dapat menandai jika pengguna diatribusikan oleh SKAN dan metode pencocokan atribusi lainnya. </p><p>Di mana tanda (flag) SSOT digunakan?</p><ul><li>Dashboard Overview AppsFlyer tampilan SSOT</li><li>Laporan data lengkap SKAN memiliki bidang <em>af_attribution_flag</em> . Jika benar, pengguna diatribusikan oleh SKAN dan metode lain. </li><li>Laporan API atribusi gabungan SKAN.</li></ul></td></tr></tbody></table>

</Accordion>

<div id="predict-component" />

<Accordion title="Prediksi komponen">

<table><tbody><tr><td colspan="2"><p><img alt="Predict-SKAN_Conversion_Studio__1_.png" src="https://support.appsflyer.com/hc/article_attachments/7742007538065"/></p></td></tr><tr><td><p>Wajib</p></td><td><p>Tidak</p></td></tr><tr><td><p>Boleh digunakan berkali-kali</p></td><td><p>Tidak</p></td></tr><tr><td><p>Opsi pengaturan</p></td><td><ul><li><span>Hanya-baca</span></li><li><span>Jendela aktivitas diatur ke 24 jam</span></li><li><span>Pengaturan lain didasarkan pada pengaturan Prediksi.</span></li></ul></td></tr><tr><td><p>Ketersediaan</p></td><td><ul><li>Tersedia untuk Memprediksi pelanggan</li><li>Untuk mendapatkan akses Prediksi, hubungi CSM Anda</li></ul></td></tr></tbody></table>

</Accordion>

<div id="inapp-event-component" />

<Accordion title="Komponen in-app event">

<Table>
  <tbody>
    <tr>
      <td colSpan="2">
        ![ConversionStudioIn-app-event.png](https://files.readme.io/7b110093a72b13c0750ccb66da5efe737b8f83c0adcb95eb35185a4dc77bad6c-4406051824657.png)
      </td>
    </tr>
    <tr>
      <td>
        Wajib
      </td>
      <td>
        Tidak
      </td>
    </tr>
    <tr>
      <td>
        Boleh digunakan berkali-kali
      </td>
      <td>
        Ya
      </td>
    </tr>
    <tr>
      <td>
        Opsi pengaturan
      </td>
      <td>
        Pilih in-app event; kemudian atur rentang sesuai dengan tujuan pengukuran Anda sebagai berikut:

        * **Khusus konversi:** Konfigurasikan satu rentang dengan rentang 0–1
        * **Interaksi dan konversi:** Konfigurasikan beberapa rentang dengan rentang yang Anda pilih
      </td>
    </tr>
    <tr>
      <td>
        Rentang untuk interaksi
      </td>
      <td>
        Untuk mengukur interaksi, Anda harus membuat rentang kejadian. Ketika terjadinya event interaksi yang dipilih dilaporkan, SKAN mengaitkannya dengan rentang yang sesuai sesuai dengan jumlah event yang terjadi.

        **Karakteristik**

        * Setiap rentang berisi rentang kejadian yang terdiri dari a **dari** nilai dan  **ke** nilai. Nilai yang lebih rendah tidak termasuk dalam rentang, dan nilai yang lebih tinggi adalah. Misalnya, 5-10 berarti lebih besar dari 5 hingga dan termasuk 10.
        * Rentang dengan nilai terendah selalu dimulai dari 0 (tetapi tidak termasuk 0 itu sendiri).
        * Anda dapat membuat rentang sebanyak yang Anda inginkan, namun perlu diingat bahwa setiap rentang memengaruhi kapasitas nilai konversi Anda.
        * Rentang harus berurutan (tanpa jeda antar rentang).

        **Mengukur interaksi menggunakan rentang**

        * Ketika suatu kejadian dilaporkan, SKAN mengaitkan kejadian tersebut dengan rentang yang sesuai. Kejadian yang direkam berasal dari rata-rata rentang. Nilainya dibulatkan ke atas ke bilangan bulat terdekat. Misalnya, 5,7 dibulatkan menjadi 6.
        * Jika jumlah kejadian melebihi nilai maksimum rentang nilai tertinggi, kejadian dikaitkan dengan rentang nilai tertinggi. Jumlah kejadian yang dicatat adalah nilai rata-rata dari rentang rentang nilai tertinggi. Dengan kata lain, jumlah kejadian yang sebenarnya diabaikan.
        * Dalam data lengkap, jumlah kejadian dan rentang sebenarnya tersedia.

        **Contoh:**

        Pada gambar, diilustrasikan kejadian berikut:

        Rentang kejadian yang ditetapkan adalah:

        * A: 0-5
        * B: 5-10
        * C: 10-20

        Jumlah kejadian dicatat menggunakan rentang sebagai berikut:

        | Contoh | Jumlah kejadian yang dilaporkan oleh SDK | Rentang terkait | Jumlah kejadian yang dilaporkan |
        | --- | --- | --- | --- |
        | 1 | 5 | A | 3 |
        | 2 | 6 | B | 8 |
        | 3 | 10 | B | 8 |
        | 4 | 125 | C | 15 |
      </td>
    </tr>
    <tr>
      <td>
        Batasan
      </td>
      <td>
        In-app event tertentu dapat dikaitkan sekali dengan komponen ini.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="revenue-component" />

<Accordion title="Komponen pendapatan">

<Table>
  <tbody>
    <tr>
      <td colSpan="2">
        ![ConversionStudioRevenue.png](https://files.readme.io/202c258f11cd93248f8aceff410126efc02ced11e9a9b159bac8ba81cbc8d9fe-4406075612305.png)
      </td>
    </tr>
    <tr>
      <td>
        Wajib
      </td>
      <td>
        Tidak
      </td>
    </tr>
    <tr>
      <td>
        Boleh digunakan berkali-kali
      </td>
      <td>
        Ya, jika menggunakan sumber pendapatan in-app event.
      </td>
    </tr>
    <tr>
      <td>
        Opsi pengaturan
      </td>
      <td>
        Pendapatan dapat dicatat menggunakan satu event, atau Anda dapat mengaitkan pendapatan menurut alur menggunakan in-app event yang dipilih.

        Opsi sumber pendapatan berikut didukung:

        * **Pendapatan keseluruhan**
          * Setiap pendapatan dicatat oleh SKAN menggunakan event `af_skad_revenue` . `af_skad_revenue` harus dipetakan.
          * Komponen dapat dimasukkan sekali.
        * **In-app event**
          * Pendapatan yang dilaporkan menurut jenis dialokasikan ke in-app event yang dipilih dan dicatat oleh SKAN menggunakan in-app event yang dipilih. Event harus dipetakan; `af_skad_revenue` tidak boleh dipetakan.
          * Komponen dapat digunakan beberapa kali.
          * Jika Anda melaporkan pendapatan melalui postback ke jaringan iklan, verifikasi bahwa pemetaan postback in-app event Anda menyertakan peristiwa pendapatan dalam aplikasi yang Anda tetapkan.
      </td>
    </tr>
    <tr>
      <td>
        Rentang
      </td>
      <td>
        Untuk mengukur pendapatan, Anda harus membuat rentang pendapatan. Saat pendapatan dilaporkan, SKAN mengaitkan pendapatan yang dilaporkan dengan rentang yang sesuai.

        **Karakteristik**

        * Setiap rentang berisi rentang pendapatan yang terdiri dari a **dari** nilai dan **ke** nilai. Nilai yang lebih rendah tidak termasuk dalam rentang; namun, nilai atas disertakan. Misalnya, 5-10 berarti lebih besar dari 5 hingga dan termasuk 10.
        * Rentang dengan nilai terendah selalu dimulai dari 0 (tetapi tidak termasuk 0 itu sendiri).
        * Anda dapat membuat rentang sebanyak yang Anda inginkan, namun perlu diingat bahwa setiap rentang memengaruhi kapasitas nilai konversi Anda.
        * Rentang harus berurutan (tanpa jeda antar rentang).
        * Jumlahnya dalam USD
        * Jika Anda menjalankan kampanye di Meta ads, Anda harus memiliki 4 rentang atau lebih.
        * Nilai rentang dapat memiliki hingga 4 digit setelah titik desimal.

        **Mencatat pendapatan menggunakan rentang**

        * Saat pendapatan dilaporkan, SKAN mengaitkan pendapatan yang dilaporkan dengan rentang yang sesuai. Pendapatan yang dicatat sama dengan nilai rata-rata rentang.
        * Jika pendapatan yang dilaporkan melebihi nilai rata-rata dari rentang nilai tertinggi, pendapatan dikaitkan dengan rentang nilai tertinggi. **Perhatikan**! Pendapatan yang dicatat adalah nilai rata-rata dari rentang ini. Dengan kata lain, jumlah pendapatan aktual diabaikan.
        * Dalam data lengkap, pendapatan yang dicatat dan rentang terkait tersedia.

        **Contoh:**

        Pada gambar, diilustrasikan rentang pendapatan berikut:

        * A: 0-5
        * B: 5-10
        * C: 10-20

        Pendapatan dicatat dengan menggunakan rentang sebagai berikut:

        | Contoh | Pendapatan yang dilaporkan oleh SDK | Rentang terkait | Pendapatan dicatat |
        | --- | --- | --- | --- |
        | 1 | 5 | A | $2,5 |
        | 2 | 6 | B | $7,5 |
        | 3 | 10 | B | $7,5 |
        | 4 | 125 | C | $15 |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="funnel-component" />

<Accordion title="Komponen funnel">

<Table>
  <tbody>
    <tr>
      <td colSpan="2">
        <Image alt="ConversionValueFunnel.png" src="https://files.readme.io/b43b5db0cee11c9addd50fb56af1ac6d3221e1956e2ee3c4c21a6940e9dfe61b-4406051997969.png" width="674px" />
      </td>
    </tr>
    <tr>
      <td>
        Wajib
      </td>
      <td>
        Tidak
      </td>
    </tr>
    <tr>
      <td>
        Boleh digunakan berkali-kali
      </td>
      <td>
        Tidak
      </td>
    </tr>
    <tr>
      <td>
        Opsi pengaturan
      </td>
      <td>
        Buat daftar rangkaian event berurutan dalam funnel. Karena kejadian satu event diperlakukan sebagai kejadian semua event sebelumnya, urutan daftar event sangat penting, seperti yang diilustrasikan dalam contoh berikut.
      </td>
    </tr>
    <tr>
      <td>
        Contoh
      </td>
      <td>
        Funnel berisi event a, f, b, k, dan z, seperti yang diilustrasikan pada gambar sebelumnya.

        | Contoh | Event dilakukan | Event dicatat |
        | --- | --- | --- |
        | 1 | a | a |
        | 2 | b | a, f, b |
        | 3 | z | a, f, b, k, z |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="priority-measurement-component" />

<Accordion title="Komponen pengukuran prioritas">

Gunakan komponen pengukuran prioritas, bagian dari mode Kustom, untuk memberi peringkat perjalanan tindakan pengguna di aplikasi berdasarkan logika bisnis Anda sehingga pengukuran prioritas tinggi mengesampingkan yang prioritas rendah. Ini memungkinkan Anda memilih apa yang akan diukur di setiap langkah corong konversi. 

Setiap prioritas (maksimum 63) dapat berisi pendapatan, in-app event, atau keduanya. Saat pengguna melakukan event di aplikasi, AppsFlyer menentukan prioritas mana yang sesuai dengan tindakan yang dilakukan oleh pengguna dan menetapkan CV yang sesuai.

Untuk memudahkan pemahaman, mari kita bandingkan menggunakan Custom dengan dan tanpa komponen prioritas. **Tanpa** prioritas, AppsFlyer memetakan semua kemungkinan kombinasi pengukuran ke CV. Sedangkan **dengan** prioritas hanya kombinasi pengukuran yang ditetapkan secara eksplisit oleh Anda yang dipetakan ke CV.

Prioritas dijelaskan dengan sangat baik dalam [contoh terperinci](/docs/skan-conversion-studio#priority-measurement-detailed-example) di artikel ini. 

**Prinsip prioritas**

* Anda dapat menetapkan 1-63 prioritas. Jumlah yang tersedia tergantung pada jendela aktivitas Anda dan pengaturan Single Source of Truth.
* Prioritas 1 selalu memiliki prioritas tertinggi. Prioritas dengan angka terbesar memiliki prioritas terendah.
* Prioritas terdiri dari [pendapatan](/docs/skan-conversion-studio#revenue-component) atau i[n-app event,](/docs/skan-conversion-studio#inapp-event-component) atau kedua komponen. Prioritas tertentu dapat berisi beberapa in-app event dan aliran pendapatan.
* Corong (funnel) tidak tersedia dalam prioritas. Namun, tetapkan prioritas beberapa in-app event untuk mengukur konversi pengguna di corong.
* Untuk menggunakan komponen pengukuran prioritas, Anda tidak dapat mengonfigurasi komponen lain, seperti in-app event atau pendapatan.

**Untuk mengatur pengukuran menggunakan prioritas:**

1. Di AppsFlyer, buka **SKAN Conversion Studio.**
2. Pilih **Custom**, klik **Continue**.
3. Jika perlu, klik **Delete** , untuk menghapus pengaturan saat ini.
4. Klik **+ Add measurement**. Pilih **Priority**.   
   Prioritas 1 ditampilkan.  

   [![Priority1.png](https://files.readme.io/f0bc64c4fbb95462a17a1e6bb8d250d3396096b743b3d412cd0605d9b0a1079d-4756458366865.png)](https://files.readme.io/f0bc64c4fbb95462a17a1e6bb8d250d3396096b743b3d412cd0605d9b0a1079d-4756458366865.png)
5. Pilih komponen pengukuran dari:
   * Pendapatan
   * In-app event
6. Lengkapi bidang sesuai antarmuka pengguna.
   * Pertimbangkan bahwa prioritas dapat terdiri dari pendapatan, in-app event, atau keduanya.
   * Nilai rentang kejadian dan pendapatan event harus dalam urutan menaik (meningkat) dan berkelanjutan. Misalnya, rentang berikut meningkat dan berkelanjutan: 1-5, 5-8, 8-10, dan seterusnya. Rentang tertentu dapat digunakan lebih dari sekali (berulang) jika kedua kalinya yang digunakan adalah bagian dari kombinasi unik dan merupakan rentang yang sama dengan prioritas terakhir dengan rentang. Misalnya, 1-5, 1-5 + tambahkan ke troli.
7. Klik **Validate.  
   Prioritas adalah pesan yang valid** ditampilkan. Jika tidak demikian, perbaiki prioritas Anda sebelum melanjutkan.
8. Lakukan salah satu dari berikut ini:
   * Untuk menambahkan prioritas, klik **+ Add priority (Tambah prioritas).** Prioritas 1 yang ada digeser ke bawah dan menjadi prioritas 2. Selesaikan pengaturan prioritas seperti yang dijelaskan sebelumnya.
   * Untuk menghapus prioritas, klik … > **Delete (Hapus).**
   * Untuk mengubah tingkat prioritas, klik **Options** ( ), lalu pilih **Change order** atau **Make lowest priority** .
   * Untuk menduplikasi prioritas, klik **Options** ( ), lalu pilih **Duplicate** .
   * Klik **Save** , untuk menyelesaikan prioritas pengaturan.

</Accordion>

<div id="lock-window" />

<Accordion title="Kunci jendela">

**Catatan**: Kunci jendela hanya relevan untuk SKAN 4 ke atas.

<table><tbody><tr><td colspan="2"><p><img alt="lock_window.png" src="https://files.readme.io/d9db51890a5d589b7343ed389d55af0c4181b249a2c5e970b9a5e1244c489abc-14240675527057.png"/></p></td></tr><tr><td><p>Gunakan</p></td><td><span>Jendela SKAN secara default mengukur nilai pengguna untuk waktu tertentu sesudah penginstalan. Anda dapat mengunci jendela lebih awal dan mengatur agar postback dikirimkan dengan semua data yang tersedia. Untuk melakukan hal tersebut, atur kondisi untuk mengunci jendela.</span></td></tr><tr><td><p>Wajib</p></td><td>Tidak</td></tr><tr><td><p>Boleh digunakan berkali-kali</p></td><td>Ya, satu untuk setiap jendela SKAN</td></tr><tr><td><p>Pilihan kondisi</p></td><td><p>Jendela Kunci terdiri dari dua opsi untuk mengunci jendela SKAN lebih awal:</p><ul><li>Waktu: Anda harus memilih waktu sesudah penginstalan (sebelum waktu default) untuk mengunci jendela. <strong>Catatan</strong>: Kunci berdasarkan waktu tidak berjalan efektif kecuali pengguna membuka aplikasi.</li><li>Nilai kasar tinggi: Segera sesudah nilai kasar tinggi dicapai, jendela menutup.</li></ul></td></tr><tr><td><p>Dampak menggunakan jendela kunci</p></td><td><p>Postback SKAN tidak berisi informasi tentang kapan jendela ditutup, sehingga status jendela kunci tidak dipertimbangkan saat memperkirakan waktu penginstalan. Oleh karena itu, mengunci jendela lebih awal dapat memengaruhi ketepatan perkiraan waktu penginstalan.</p></td></tr></tbody></table>

</Accordion>

<div id="activity-window" />

<Accordion title="Jendela aktivitas">

**Catatan**:

* Jendela aktivitas hanya relevan untuk SKAN 3 dan di bawahnya (yang berarti mode Kustom dan tetap).
* Jika Anda menggunakan SKAN 4+ tetapi perangkat pengguna atau jaringan iklan belum mendukung SKAN 4, Jendela Aktivitas adalah 48 jam.

<table><tbody><tr><td colspan="2"><p><img alt="flex_activity_window.jpg" src="https://files.readme.io/ac51126eda5b9d319ccdd90adb936baaa512dcd844ad191cac6c20a45cd4aae8-6390396808081.jpg"/></p></td></tr><tr><td><p>Wajib</p></td><td>Ya </td></tr><tr><td><p>Boleh digunakan berkali-kali</p></td><td>Tidak</td></tr><tr><td><p>Karakteristik waktu</p></td><td><ul><li>Timer memiliki durasi tetap, yang Anda tetapkan, dan berjalan secara paralel dengan timer iOS.</li><li>Sedangkan timer iOS memiliki durasi awal 24 jam. Setiap kali nilai konversi meningkat, timer direset.</li><li>Durasi default 24 jam.</li><li>Pengukuran berhenti ketika salah satu timer mencapai 0. </li></ul></td></tr><tr><td>Durasi timer</td><td><ul><li>Rentang: 12-72 jam. Untuk opsi lainnya, lihat <strong>Pengukuran fleksibel</strong> di tabel ini.  </li><li>Saat timer berakhir, AppsFlyer berhenti mengukur.</li><li>Jika durasi timer lebih dari 24 jam, pengguna harus aktif di aplikasi setidaknya sekali per interval. Jika tidak, pengukuran dapat berakhir sebelum waktunya karena AppsFlyer tidak dapat mencegah timer iOS mencapai 0; artinya iOS mengakhiri pengukuran. </li></ul></td></tr><tr><td><p>Interval</p></td><td><p>12 atau 24 jam. Interval memengaruhi ketepatan rentang waktu aktif terakhir dan waktu penginstalan. Untuk opsi lainnya, lihat <strong>Pengukuran fleksibel</strong> di tabel ini. </p><p>Rentang waktu terakhir aktif tersedia dalam laporan data lengkap di kolom <em>min_install_time</em> dan <em>max_install_time</em> dan digunakan untuk menentukan waktu penginstalan seperti yang dijelaskan di bagian ini.</p><p>Contoh:</p><ul><li>Durasi timer diatur ke 48 jam</li><li>Pengguna terakhir aktif selama 40 jam</li><li>Tergantung pada pengaturan interval, rentang waktu terakhir aktif adalah: <br/><ul><li>Interval 12-jam: 36–48 jam</li><li>Interval 24-jam: 24–48 jam</li></ul></li></ul></td></tr><tr><td><p>Install time</p></td><td><p>Waktu penginstalan didapatkan sebagai berikut:</p><p><code>Waktu penginstalan = Waktu kedatangan postback - [Rata-ratarentang terakhir aktif] - [jeda postback iOS]</code></p><ul><li> <code>Waktu kedatangan postback</code>:  Waktu postback iOS pertama kali diterima langsung dari perangkat; biasanya oleh jaringan iklan. </li><li> <code>Rata-rata rentang terakhir aktif</code> mempertimbangkan CV dan dihitung sebagai berikut: <ul><li>Jika CV = 0  rentang terakhir aktif diasumsikan 0. </li><li>Jika CV &gt; 1 atau CV = null: Menggunakan waktu min_install_time dan max_install ini diatur berdasarkan interval dan terakhir kali pengguna terlihat aktif di aplikasi.  Misalnya, Jika intervalnya adalah 12, karena pengguna terakhir terlihat 25 jam setelah penginstalan, hasilnya adalah [24 + 36] / 2 = 30. </li></ul></li><li> <code>jeda postback iOS</code>: [24 + 48 ] / 2 = 36. Pertimbangkan bahwa timer iOS berakhir 24 jam setelah perubahan terakhir pada CV dan postback dikirim 0–24 jam setelahnya. <strong>36 jam adalah konstanta</strong>. </li></ul></td></tr><tr><td><p>Opsi pengaturan</p></td><td><p>Jendela Aktivitas terdiri dari dua pengaturan durasi dan interval. </p><ul><li>Durasi: 24–72 jam dengan interval 24 jam. Maksimal 3 interval.</li><li>Durasi: 12–72 jam dengan interval 12 jam. Maksimal 6 interval.</li></ul></td></tr><tr><td><p>Dampak mengubah durasi jendela aktivitas</p></td><td><ul><li>Postback dikirim 0-24 jam setelah timer iOS berakhir. </li><li>Awalnya, timer iOS ditetapkan berakhir setelah 24 jam. </li><li>Jika Anda mengatur jendela aktivitas ke lebih dari 24 jam, pengguna harus aktif setidaknya sekali per interval untuk memastikan bahwa timer iOS tidak berakhir.</li></ul></td></tr><tr><td><p>Pertimbangan terkait jaringan iklan</p></td><td><ul><li>Durasi timer default adalah 24 jam.</li><li>Anda dapat mengatur durasi yang berbeda, tetapi sebelum melakukannya, verifikasi dengan mitra jaringan iklan Anda jika mereka mendukung periode yang berbeda dari default. </li><li><span>Saat menggunakan jendela 24 jam, Anda dapat meningkatkan metrik dengan membagi periode 24 jam menjadi 2 interval, masing-masing 12 jam. Dengan melakukan hal tersebut, Anda akan tahu apakah pengguna terus menggunakan aplikasi setelah 12 jam pertama. </span></li></ul></td></tr><tr><td><p>Contoh persyaratan kapasitas rentang</p></td><td><p><span>Gambar di bagian ini menunjukkan timer 60 jam dengan interval 12 jam. </span></p></td></tr><tr><td><p>Opsi jendela aktivitas yang fleksibel</p></td><td><p>Pengukuran fleksibel memungkinkan Anda mengatur jendela aktivitas yang lebih lama dan memiliki perincian per jam. Demikian halnya untuk pengaturan interval. Pengaturan memiliki karakteristik sebagai berikut:</p><ul><li>Jendela aktivitas: <ul><li>Rentang: 12-1512 jam (63 hari)  </li><li>Perincian: 1 jam</li></ul></li><li>Interval: <ul><li>Rentang: <span>Minimum 1 jam dan pengganda lain dari jendela aktivitas</span> </li><li>Perinciannya 1 jam</li></ul></li></ul><p>Pertimbangan: Rasio jendela aktivitas terhadap interval harus bilangan bulat.</p><p>Praktik terbaik: Jangan atur interval ke lebih dari 24 jam, karena ini mengurangi keakuratan estimasi waktu penginstalan.</p></td></tr></tbody></table>

</Accordion>

## Informasi Tambahan

<div id="view-cv-mapping" />

<Accordion title="Lihat pemetaan CV">

* Lihat event yang dipetakan ke CV dengan memilih CV. Event yang dipetakan ditampilkan di bawah tabel.
* Unduh tabel pemetaan CV sebagai file CSV. Klik **Download mapping file.**
* Dapatkan pemetaan CV menggunakan <Anchor target="_blank" href="/marketers/id/docs/skan-cv-schema-api-for-advertisers">API skema SKAN CV untuk pengiklan</Anchor>.

![CVmapping.png](https://files.readme.io/97ec2570636897a6274f7750c7f77c92d8457cab51660de496bec6cb7504c4a3-4407788932113.png)

#### Kolom file pemetaan CSV

| Kolom | Deskripsi |
| --- | --- |
| app\_id |  |
| conversion\_value | nilai CV:<ul><li>0-63</li><li>Rendah, sedang, atau tinggi</li></ul> |
| event\_name |  |
| min\_event\_counter | Batas bawah rentang penghitung event |
| max\_event\_counter | <ul><li>Batas atas rentang penghitung event.</li><li>Dalam laporan yang dibuat oleh AppsFlyer, jumlah event dihitung menggunakan rumus berikut: Roundup ([min\_event\_counter + max\_event\_counter]) / 2</li></ul> |
| min\_event\_revenue | Batas bawah rentang pendapatan event dalam USD |
| max\_event\_revenue | <ul><li>Batas atas rentang pendapatan event dalam USD</li><li>Dalam laporan yang dihasilkan oleh AppsFlyer, pendapatan dihitung menggunakan rumus berikut: ([min\_event\_revenue + max\_event\_revenue]) / 2)</li></ul> |
| min\_time\_post\_install | Batas bawah, jam pasca-penginstalan, yang menunjukkan kapan pengguna terakhir kali aktif di aplikasi. |
| max\_time\_post\_install | Batas atas, jam setelah penginstalan, menunjukkan kapan pengguna terakhir kali aktif di aplikasi. |
| last\_config\_change | Tanggal saat Anda menyimpan konfigurasi di SKAN Conversion Studio. |

</Accordion>

<div id="conversion-value-capacity-formula" />

<Accordion title="Rumus kapasitas nilai konversi">

Seperti yang dijelaskan sebelumnya, jumlah maksimum nilai konversi yang tersedia adalah 64. Rumus berikut menghitung berapa banyak nilai konversi yang tersedia yang digunakan oleh mode.

```http
(activity time duration in hours / interval size in hours) * 
(number of revenue ranges + 1 ) * 
(number of in-app event ranges + 1 ) * 
(number of steps in a funnel + 1)
```

Sesuaikan rumus untuk memasukkan semua komponen pengukuran

</Accordion>

<div id="maximized-custom-cv-examples" />

<Accordion title="Contoh CV Kustom yang Dimaksimalkan">

#### Contoh 1

| Komponen | Deskripsi |
| --- | --- |
| Jendela aktivitas | <ul><li>Durasi: 24 jam</li><li>Interval: 24 jam menjadi 1 interval</li></ul> |
| Pendapatan | <ul><li>Pendapatan dilaporkan menggunakan satu in-app event (keseluruhan)</li><li>Rentang pendapatan: 15</li></ul> |
| In-app | Tidak ada |
| Corong (Funnel) | 3 in-app event |

#### Contoh 2

| Komponen | Deskripsi |
| --- | --- |
| Jendela aktivitas | <ul><li>Durasi: 24 jam</li><li>Interval: 12 jam menjadi 2 interval</li></ul> |
| Pendapatan | <ul><li>Pendapatan dilaporkan dialokasikan berdasarkan jenis menggunakan 2 in-app event yang berbeda</li><li>Rentang pendapatan: 3 (per in-app event)</li></ul> |
| Pengaturan in-app untuk konversi | 1 in-app event untuk mengukur konversi; setiap in-app membutuhkan 1 rentang |
| Corong (Funnel) | Tidak ada |

#### Contoh 3

| Komponen | Deskripsi |
| --- | --- |
| Jendela aktivitas | <ul><li>Durasi: 24 jam</li><li>Interval: 24 jam menjadi 1 interval</li></ul> |
| Pendapatan | <ul><li>Pendapatan dilaporkan menggunakan satu in-app event (keseluruhan)</li><li>Rentang pendapatan: 3</li></ul> |
| Pengaturan in-app untuk interaksi | <ul><li>2 in-app event untuk mengukur kejadian interaksi</li><li>Rentang kejadian: 3 per in-app event</li></ul> |
| Corong (Funnel) | Tidak ada |

#### Contoh 4

| Komponen | Deskripsi |
| --- | --- |
| Jendela aktivitas | <ul><li>Durasi: 48 jam</li><li>Interval: 12 jam menjadi 4 interval</li></ul> |
| Pendapatan | <ul><li>Pendapatan dilaporkan menggunakan satu in-app event (keseluruhan)</li><li>Rentang pendapatan: 7</li></ul> |
| Pengaturan in-app untuk konversi | 1 in-app event untuk mengukur konversi; membutuhkan 1 rentang |
| Corong (Funnel) | Tidak ada |

</Accordion>

<div id="priority-measurement-detailed-example" />

<Accordion title="Contoh detail pengukuran prioritas">

Dalam aplikasi belanja, pengiklan ingin memfokuskan pengukuran pada:

* Tindakan pengguna yang **tidak membayar**
* pendapatan dari pengguna yang **membayar**

Dengan demikian, pengiklan menggunakan CV untuk mencatat pendapatan dengan lebih tepat. Persyaratan pengukuran ini diterjemahkan menjadi serangkaian prioritas pengukuran seperti yang tercantum dalam tabel berikut. 

Pertimbangkan:

* Prioritas tertinggi selalu 1. **Perhatikan** ! Angka prioritas tidak langsung dipetakan ke CV. Pemetaan CV ditampilkan di antarmuka pengguna.
* Jumlah prioritas maksimum adalah 63. Jumlah aktual yang tersedia tergantung pada jendela aktivitas dan jika Single Source of Truth aktif.
* Setiap prioritas terdiri dari rentang pendapatan atau rentang in-app event, atau keduanya.
* Nilai rentang: Nilai batas yang lebih rendah tidak disertakan dalam rentang tetapi nilai batas yang lebih tinggi disertakan. Misalnya, rentang $5-$10 tidak menyertakan nilai 5 tetapi menyertakan nilai 10.

#### Contoh pengaturan prioritas pengukuran

<table><tbody><tr><th><p>Prioritas #</p></th><th><p>Rentang pendapatan</p></th><th>In-app event</th></tr><tr><td>1 [Prioritas tertinggi]</td><td>$5-$10</td><td>send_recommendation</td></tr><tr><td>2</td><td>$5-$10</td><td>--</td></tr><tr><td>3</td><td>$0-$5</td><td>send_recommendation</td></tr><tr><td>4</td><td>$0-$5</td><td>--</td></tr><tr><td>5</td><td>--</td><td>send_recommendation<br/>add_to_cart</td></tr><tr><td>6</td><td>--</td><td><p>send_recommendation</p></td></tr><tr><td>7 [Prioritas terendah]</td><td>--</td><td>add_to_cart</td></tr><tr><td colspan="3">-- Tidak ada nilai yang ditetapkan</td></tr></tbody></table>

Tabel berikut berisi skenario perjalanan pengguna. Setiap skenario berisi daftar tindakan yang dilakukan oleh pengguna selama perjalanan mereka dan prioritas yang ditentukan oleh AppsFlyer.

Di tabel:

* Beberapa tindakan dipisahkan menggunakan >
* Nilai dalam tanda kurung (), adalah prioritas yang ditentukan oleh AppsFlyer yang ditetapkan setelah pengguna menyelesaikan tindakan. Menggunakan prioritas AppsFlyer, perbarui CV di aplikasi.

#### Skenario perjalanan pengguna

| Skenario perjalanan pengguna | Tindakan dan prioritas pengguna |
| --- | --- |
| A | add\_to cart (7) |
| B | add\_to\_cart (7) > send\_recommendation (5) |
| C | Pembelian $3 (4) |
| D | Pembelian $6 (2) |
| E | Pembelian $6 (2) > send\_recommendation (1) |

</Accordion>

<div id="fixed-mode-examples" />

<Accordion title="Contoh mode tetap">

#### Contoh A: Pengukuran pendapatan

| Faktor | Catatan |
| --- | --- |
| Skenario | <ul><li>20 pengguna menginstal aplikasi dan melakukan pembelian berikut:<ul><li>9 pengguna, masing-masing melakukan pembelian $10</li><li>5 pengguna, masing-masing melakukan pembelian $5</li><li>1 pengguna melakukan pembelian $1, lalu $3, lalu $5, dan akhirnya $1. Totalnya $10.</li></ul></li><li>Data biaya yang disediakan oleh API dari jaringan iklan: $30</li></ul> |
| Konfigurasi SKAN | <ul><li>Pilih jenis pengukuran: pendapatan</li><li>Tetapkan faktor konversi: 1 unit konversi = $1</li><li>Event konversi yang ditentukan: Di SDK, Anda harus mengirim pendapatan menggunakan parameter *af\_revenue*.</li></ul> |
| Metrik yang dipilih | Metrik terkait pendapatan tersedia<ul><li>Penginstalan: 20</li><li>Pendapatan: $125</li><li>Konversi:15</li><li>ARPU: $6,25</li><li>ROI: 316%</li></ul> |
| Jumlah baris data lengkap per laporan | <Anchor target="_blank" href="/marketers/id/docs/skan-raw-data-reports">Laporan data lengkap tersedia melalui Data Locker</Anchor><ul><li>Postback perangkat: 20 baris</li><li>Penginstalan: 20 baris</li><li>In-app event: 15 baris. Perhatikan! Pengguna yang melakukan beberapa pembelian diwakili oleh satu baris $10.</li></ul> |
| Pertimbangan pengembang | Event yang membawa pendapatan dikenali |

#### Contoh B: Pengukuran konversi

<Table>
  <thead>
    <tr>
      <th>
        Faktor
      </th>
      <th>
        Catatan
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Contoh
      </td>
      <td>
        * 5 pengguna (AE) menginstal aplikasi
        * Mereka melakukan 0-3 in-app event yang berbeda, seperti yang digambarkan dalam tabel
        * Data biaya yang disediakan oleh API dari jaringan iklan: $30

        #### In-app event yang dilakukan oleh pengguna

        |  | in-app-1 | in-app-2 | in-app-3 |
        | --- | --- | --- | --- |
        | Pengguna A | Melakukan | Melakukan | - |
        | Pengguna B | Melakukan | - | Melakukan |
        | Pengguna C | Melakukan | Melakukan | - |
        | Pengguna D | Melakukan | Melakukan | - |
        | Pengguna E | - | - | - |
      </td>
    </tr>
    <tr>
      <td>
        Konfigurasi Atribusi SKAdNetwork
      </td>
      <td>
        Pilih jenis pengukuran: Konversi

        * Pilih in-app event: in-app-1, in-app-2, in-app-3
        * Di <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings">dasbor</Anchor> SKAdNetwork , Anda memilih salah satu event untuk menghitung metrik pengguna yang dikonversi. Anda dapat mengubah event yang dipilih sesuai kebutuhan.
      </td>
    </tr>
    <tr>
      <td>
        Metrik yang dipilih
      </td>
      <td>
        #### Metrik terkait in-app tersedia

        | Metrik | Aplikasi | in-app-1 | in-app -2 | in-app- 3 |
        | --- | --- | --- | --- | --- |
        | Install | 5 |  |  |  |
        | Konversi | 4 |  |  |  |
        | Pengguna Unik |  | 4 | 3 | 1 |
        | eCPA | $ 7,5 |  |  |  |

        **Perhatikan!** Karena Event Konversi yang ditetapkan adalah dalam in-app 1, nilai 4 digunakan untuk menghitung metrik tingkat aplikasi dan untuk metrik in-app-1.
      </td>
    </tr>
    <tr>
      <td>

      </td>
      <td>
        <Anchor target="_blank" href="/marketers/id/docs/skan-raw-data-reports">Laporan data lengkap tersedia melalui Data Locker</Anchor>

        * Postback perangkat: 5 baris
        * Penginstalan: 5 baris
        * In-app event: 8 baris
      </td>
    </tr>
    <tr>
      <td>
        Pertimbangan pengembang
      </td>
      <td>
        * Pastikan Anda mengirim in-app event yang dilakukan pengguna.
        * SKAdNetwork Solution mengabaikan nilai event (kecuali terkait dengan pengukuran pendapatan.
      </td>
    </tr>
  </tbody>
</Table>

#### Contoh C: Pengukuran interaksi

<Table>
  <thead>
    <tr>
      <th>
        Faktor
      </th>
      <th>
        Catatan
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Contoh
      </td>
      <td>
        5 pengguna menginstal aplikasi dan membuka aplikasi beberapa kali yang tercantum dalam tabel.

        #### Aplikasi dibuka

        |  | Berapa kali event tersebut dilakukan |
        | --- | --- |
        | Pengguna A | 63 |
        | Pengguna B | 10 |
        | Pengguna C | 5 |
        | Pengguna D | 1 |
        | Pengguna E | - |
      </td>
    </tr>
    <tr>
      <td>
        Konfigurasi Atribusi SKAdNetwork
      </td>
      <td>
        * Pilih jenis pengukuran: Interaksi
        * Event konversi yang ditentukan: af\_app\_opened Perhatikan! Anda dapat menggunakan event apa pun yang tersedia.
      </td>
    </tr>
    <tr>
      <td>
        Metrik yang dipilih
      </td>
      <td>
        Metrik sampel tersedia

        * Penginstalan: 5
        * Konversi: 4
        * Sesi: 79
      </td>
    </tr>
    <tr>
      <td>
        Jumlah baris data lengkap per laporan
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/id/docs/skan-raw-data-reports">Laporan data lengkap tersedia melalui Data Locker</Anchor>

        * Postback perangkat: 5 baris
        * Penginstalan: 5 baris
        * In-app event: 79 baris; satu baris setara dengan satu sesi
      </td>
    </tr>
    <tr>
      <td>
        Pertimbangan pengembang
      </td>
      <td>
        Setiap kali pengguna melakukan event interaksi yang dipilih: mengirim in-app event. SKAdNetwork menghitung berapa kali Anda mengirim event.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="skan-conversion-studio-api" />

<Accordion title="API Studio Konversi SKAN">

Jika Anda memiliki banyak aplikasi yang menginginkan konfigurasi nilai konversi SKAN serupa, mungkin akan memakan waktu dan menantang untuk merancang skema untuk setiap aplikasi secara terpisah di UI Studio Konversi. Untuk menghemat waktu dan tenaga, Anda dapat mengonfigurasi skema SKAN di UI satu kali, lalu menggunakan API Studio Konversi SKAN untuk menggunakan skema yang sama di beberapa aplikasi. **Catatan**: API hanya mendukung skema yang dikonfigurasi di UI menggunakan SKAN 4 atau mode pengukuran khusus (dan dalam mode ini, komponen pengukuran Predict tidak didukung.

**Untuk menggunakan API Studio Konversi SKAN** :

1. Dapatkan <Anchor target="_blank" href="/marketers/id/docs/managing-appsflyer-tokens">token API</Anchor> . Admin perlu mengambil token.
2. Berikan token API kepada pengembang Anda untuk digunakan di header autentikasi.
3. Beri developer Anda ID aplikasi dari:
   * Aplikasi yang skema SKAN-nya dikonfigurasi di UI (artinya aplikasi tempat Anda ingin menyalin skema SKAN).
   * Semua aplikasi yang Anda inginkan memiliki skema yang sama.
4. Beri tahu developer Anda untuk mengikuti <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/skan-studio-config-overview-1">petunjuk API Studio Konversi SKAN</Anchor> mereka di hub developer.

**Catatan**:

* API dapat digunakan untuk menyalin skema ke satu aplikasi per panggilan API. Namun, developer Anda kemudian dapat membuat skrip untuk menyalin skema yang diperlukan ke beberapa aplikasi.
* API Studio Konversi SKAN tidak tersedia untuk agensi.

</Accordion>

## Prosedur tambahan

<div id="change-skan-measurement-mode" />

<Accordion title="Ubah mode pengukuran SKAN">

Pertimbangkan:

* Setelah Anda mulai menggunakan mode pengukuran SKAN 4, Anda tidak dapat mengubahnya kembali ke mode sebelumnya.
* Ketika Anda membuat perubahan pengukuran, semuanya mulai bereaksi dari 00.00 UTC dan masa transisi dimulai. Selama periode ini, kami memecahkan kode nilai konversi menggunakan pengaturan yang paling terakhir dipilih. Namun, kedatangan postback sekarang berkaitan dengan penginstalan yang terjadi di masa lalu.
* Jumlah penginstalan yang dilaporkan tidak terkait dengan perubahan pengaturan dan akurat.

</Accordion>

<div id="disable-skan-measurement" />

<Accordion title="Nonaktifkan pengukuran SKAN">

Untuk menonaktifkan pengukuran SKAdNetwork:

1. Di AppsFlyer, buka **Configuration**  >  **SKAN Conversion Studio.**
2. Klik ⋮ .
3. Menonaktifkan **pengukuran SKAdNetwork.**   
   Untuk kasus lainnya, SDK berhenti memanggil fungsi SKAN seperti *registerAppForAdNetworkAttribution*, *updateConversionValue.*
4. Klik **Save changes.**

</Accordion>

<div id="report-events-by-servertoserver-api" />

<Accordion title="Laporkan event dengan API server-ke-server">

![SKAdNetwork_-_S2S__2_.png](https://files.readme.io/ed55e5c10184afcc27ce7e414a3213f69d2c20bd70d38f78be338f1b17254ee2-16281446657937.png)

Baik SDK maupun <Anchor target="_blank" href="/marketers/id/docs/server-to-server-events-api-for-mobile-s2s-mobile">server-to-server API (S2S)</Anchor> dapat mengirim in-app event ke server AppsFlyer.

S2S alurnya adalah sebagai berikut:

* Terjadinya suatu event terkait dengan pengguna di server pengiklan. Aplikasi mungkin terbuka atau tertutup saat ini.
* Server pengiklan melaporkan kejadian tersebut ke AppsFlyer oleh S2S.
* AppsFlyer menghitung nilai konversi yang diperbarui dan kemudian: 
  * Jika aplikasi terbuka di perangkat pengguna: SDK diberi tahu tentang nilai yang diperbarui. SDK memperbarui nilai konversi iOS pada perangkat.
  * Jika aplikasi tidak terbuka di perangkat pengguna: server menunggu hingga aplikasi dibuka untuk memberi tahu SDK tentang nilai konversi. Ini harus terjadi sebelum berakhirnya Jendela Aktivitas. Jika pemberitahuan gagal, event tersebut diabaikan.

**Versi SDK yang diperlukan**

* Mengadopsi versi SDK terbaru di aplikasi. **Perhatikan!** Tidak ada tindakan yang diperlukan oleh pengembang.

**Untuk mengimplementasikan pengiriman in-app event oleh API server-ke-server:**

1. Lakukan salah satu dari berikut ini:
   * Jika mode yang Anda pilih adalah SKAN 4 atau Kustom:
     * Tidak ada perubahan pengaturan yang diperlukan.
   * Jika mode yang Anda pilih adalah pendapatan, konversi, atau interaksi:
     1. Di AppsFlyer, buka **Configuration**  >  **SKAN Conversion Studio.**
     2. Klik options (⋮).
     3. Aktifkan **Catat in-app event yang dikirim oleh API server-ke-server** .
2. Kirim event dengan S2S.

**Batasan**

* Jika Anda menerapkan *anonimisasi pengguna* untuk pengguna tertentu, maka Anda tidak dapat mengirim event dengan S2S untuk pengguna tersebut.

</Accordion>

<div id="add-ssot-to-fixed-mode-measurements" />

<Accordion title="Tambahkan SSOT ke pengukuran mode tetap">

Jika Anda telah menyiapkan mode pengukuran Pendapatan atau Interaksi, Single Source of Truth (SSOT, yang menghapus duplikat dan secara akurat melaporkan data iOS), tidak didukung. <Anchor target="_blank" href="/marketers/id/docs/single-source-of-truth-ssot-guide-for-ios-attribution">Pelajari lebih lanjut tentang SSOT</Anchor>

**Untuk mengaktifkan SSOT saat Anda mengatur mode Pendapatan atau Interaksi** :

1. Di AppsFlyer, buka **Configuration** > **SKAN Conversion Studio**.
2. Gulir ke bawah ke mode pengukuran aktif Anda.
3. Klik **+ Add Single Source of Truth**.
   * Tombol Single Source of Truth diaktifkan secara otomatis.
   * Rentang pengukuran mode tetap Anda diubah secara minimal, untuk memungkinkan SSOT beberapa ruang nilai konversi.
4. Klik **Save**.

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Spesifikasi dan batasan">

| Spesifikasi | Catatan |
| --- | --- |
| Agensi | Agensi memiliki <Anchor target="_blank" href="/partners/id/docs/getting-started-agency-onboarding#access-to-skan-conversion-studio">akses terbatas ke Studio Konversi SKAN pengiklan</Anchor>. |
| Nilai kasar | Sampai komponen 10 pengukuran. |
| In-app event organik | Di SKAN 4, mode Khusus dan Dekode, metrik organik untuk in-app event dan keseluruhan pendapatan tidak tersedia. |

</Accordion>

<div data-zendesk-anchors="skan-conversion-studio-basics=dasar-dasar-skan-conversion-studio 01H7Z08MFDASBCBJD18QTXYSXK=dasar-dasar-skan-conversion-studio 01H7Z08MFDX3VYJTSWXQ5HQ7BZ=measurement-principles-and-definitions s2s-principles=prinsip-s2s 01H7Z08MFDWRGVNXB62Z6CT1G7=prinsip-s2s setting-up-conversion-values-in-skan-conversion-studio=mengatur-nilai-konversi-di-studio-konversi-skan 01H7Z08MFDB76C6Z5SSXHFT71P=mengatur-nilai-konversi-di-studio-konversi-skan 01H7Z08MFDEAYHJAG9XA2TGBWV=penting 01H7Z08MFD7VY1QP85W0YPK8RC=skan-4 01H7Z08MFD3SWVZK68K45NYDP8=custom 01H7Z08MFDZ1EKDQNZWGF7DHK9=fixed-modes fixed-mode-measurement=pengukuran-mode-tetap 01H7Z08MFDAYVJKJBT08R82N26=pengukuran-mode-tetap 01H7Z08MFDCJGZGQR2JR4WQVHR=decode measurement-components=komponen-pengukuran 01H7Z08MFDFE345QWHF77RGTD7=komponen-pengukuran 01H7Z08MFE5G01NGY5EFTAW93M=single-source-of-truth 01H7Z08MFEZRQ9NA2KTJW0PSST=predict-component 01H7Z08MFERDJHSD8NT5KN7DKN=inapp-event-component 01H7Z08MFETMGAE67X499V4092=revenue-component 01H7Z08MFEQG2HRJBWBYFTW3ZK=funnel-component 01H7Z08MFE22J8DDBDNJ18KBEJ=priority-measurement-component 01H7Z08MFES844SS08HS17Y29R=lock-window 01H7Z08MFE61QCC0MZW5RJ910B=activity-window additional-information=informasi-tambahan 01H7Z08MFET64PSAVMREQ4HP4S=informasi-tambahan 01H7Z08MFEKP9WNGJD2GBVKB0P=view-cv-mapping csv-mapping-file-columns=kolom-file-pemetaan-csv 01H7Z08MFETCB428W1TXTH2HJ8=kolom-file-pemetaan-csv 01H7Z08MFE5CBQK024CF8FARJ9=conversion-value-capacity-formula 01H7Z08MFETZVQSNWX639E56SK=maximized-custom-cv-examples example-1=contoh-1 01H7Z08MFEXME7RV67XTZRDWJE=contoh-1 example-2=contoh-2 01H7Z08MFEHRF4656X5AR301D8=contoh-2 example-3=contoh-3 01H7Z08MFEK0725CN35TP3MPYT=contoh-3 example-4=contoh-4 01H7Z08MFES7W3EF2JJ8B75K99=contoh-4 01H7Z08MFF2JXA0BFNKCW3ZCZ7=priority-measurement-detailed-example measurement-priorities-setting-example=contoh-pengaturan-prioritas-pengukuran 01H7Z08MFFXAAC37MBV0ES6ADQ=contoh-pengaturan-prioritas-pengukuran user-journey-scenarios=skenario-perjalanan-pengguna 01H7Z08MFFJ9TQMH0Q93B7N1A8=skenario-perjalanan-pengguna 01H7Z08MFFNBXECB8A5Y0KH9C8=fixed-mode-examples example-a-revenue-measurement=contoh-a-pengukuran-pendapatan 01H7Z08MFFVKZN3Y2R1ZEVEW4D=contoh-a-pengukuran-pendapatan example-b-conversion-measurement=contoh-b-pengukuran-konversi 01H7Z08MFFNBA5786R5XZDA5FG=contoh-b-pengukuran-konversi inapp-events-performed-by-users=in-app-event-yang-dilakukan-oleh-pengguna 01H7Z08MFFA7C6HWQPADZXQQNC=in-app-event-yang-dilakukan-oleh-pengguna inapp-related-metrics-available=metrik-terkait-in-app-tersedia 01H7Z08MFF1PEE91J5CJN1GC7V=metrik-terkait-in-app-tersedia example-c-engagement-measurement=contoh-c-pengukuran-interaksi 01H7Z08MFF8V718C23PQ2NG3C3=contoh-c-pengukuran-interaksi app-opens=aplikasi-dibuka 01H7Z08MFF4PRHSR8NCJ1Q78WM=aplikasi-dibuka 01H7Z08MFFVS6MYC9EB3KP0H2Y=skan-conversion-studio-api additional-procedures=prosedur-tambahan 01H7Z08MFFPZ4GKM5GFMAE2HDJ=prosedur-tambahan 01H7Z08MFFPKCX5TFQQTMYJEGW=change-skan-measurement-mode 01H7Z08MFF78F9NMWJATYE2YFE=disable-skan-measurement 01H7Z08MFFD4T3D71A6R9K83A3=report-events-by-servertoserver-api 01H7Z08MFFFAEW6NP0YAX773B3=add-ssot-to-fixed-mode-measurements 01H7Z08MFFG9EQFVEKN3AXE9DD=specifications-and-limitations" />
