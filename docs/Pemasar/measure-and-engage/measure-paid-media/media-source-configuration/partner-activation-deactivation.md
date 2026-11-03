---
title: Aktivasi/penonaktifan mitra
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
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
    - Ad Networks
  created_at: '2019-01-29T08:53:31Z'
  edited_at: '2024-09-12T12:28:47Z'
  id: 360000844778
  locale: id
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/id/articles/360000844778
---
> **Sekilas:** Mengaktifkan atau menonaktifkan integrasi mitra, mengizinkan atau menolak mereka untuk mendapatkan data Anda dan melakukan tindakan.

## Iktisar aktivasi

Integrasi mitra dapat bersifat aktif atau tidak aktif. Integrasi pertama kali diaktifkan dengan **mengaktifkan tombol Aktifkan mitra** dari halaman integrasi utama. Ada berbagai jenis integrasi. Integrasi juga dapat dianggap aktif jika [jenis integrasi](#integration-types) lainnya (lihat tabel di bawah) diaktifkan, bahkan ketika sakelar **Aktifkan mitra** dimatikan.

**Untuk masuk ke halaman integrasi mitra dari aplikasi yang dipilih saat ini:**

* Di AppsFlyer, dari menu samping, pilih **Kolaborasi** > **Integrasi Aktif** dan pilih mitra.

Bagian di bawah ini menjelaskan berbagai jenis integrasi, bagaimana tingkat aktivitas ditunjukkan, dan dampak pengaturan aktivasi mitra pada integrasi:

<div id="data-title" />

<Accordion title="Jenis integrasi">

Integrasi utama **(Aktifkan mitra)** diaktifkan pada tab integrasi pertama. Jenis integrasi tambahan (lihat tabel di bawah) diaktifkan dari tab berikutnya. **Setiap integrasi berjalan sendiri-sendiri**. Agar integrasi an integrasi dianggap aktif, setidaknya satu jenis integrasi harus diaktifkan, terlepas dari status sakelar Aktifkan mitra.

| Jenis integrasi | Deskripsi |
| --- | --- |
| **Integrasi utama (<Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#a-activate-partner">Mengaktifkan mitra</Anchor>)** | Memungkinkan konversi dikaitkan dan postback dikirim ke mitra |
| **<Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview">Biaya</Anchor>** (jika ada) | Memungkinkan mendapatkan data tentang biaya, klik, dan tayangan untuk kampanye, adset, iklan, dan geografis/negara Anda |
| <Anchor target="_blank" href="/marketers/id/docs/roi360-guide-ad-revenue-attribution">**Pendapatan iklan**</Anchor> (jika ada) | Memungkinkan mendapatkan data tentang pendapatan dari iklan Anda |
| **<Anchor target="_blank" href="/marketers/id/docs/skan-integrated-partners-list">SKAN</Anchor>** (jika ada) | Memungkinkan mendapatkan balasan SKAN dari mitra |
| **<Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#permissions-tab">Permissions</Anchor>** | Memungkinkan pemberian izin kepada jaringan iklan dan agensi untuk mengakses data Anda dan melakukan tindakan dalam integrasi Anda |

</Accordion>

<div id="integration-activity-indication" />

<Accordion title="Tingkat aktivitas">

Tingkat aktivitas integrasi mitra didasarkan pada jumlah hari dengan konversi aktif dalam 30 hari terakhir. Setiap integrasi mitra dapat memiliki dua tingkat aktivitas, yang ditunjukkan dengan titik hijau atau oranye di samping logo mitra di Pasar Mitra.

![active-integrations-page-orange2.png](https://support.appsflyer.com/hc/article_attachments/16668556226449)

Tabel berikut ini menguraikan kriteria indikasi tingkat aktivitas (hijau atau oranye) antara 30-90 hari, berdasarkan apakah aplikasi tertentu dipilih atau semua aplikasi:

| Indikasi tingkat aktivitas | Aplikasi tertentu yang dipilih | Semua aplikasi yang dipilih |
| --- | --- | --- |
| <span id="green-dot"></span>Titik hijau | Konversi dari mitra direkam dalam aplikasi yang dipilih | Setidaknya satu aplikasi memiliki konversi dengan mitra |
| <span id="orange-dot"></span>Titik oranye | Tidak ada konversi yang direkam dari mitra di aplikasi yang dipilih | Semua aplikasi tidak memiliki konversi dengan mitra |

> 📘 **Catatan**
>
> Integrasi yang tidak memiliki aktivitas selama lebih dari 90 hari akan [dinonaktifkan secara otomatis](#automatic-deactivation), .

</Accordion>

<div id="effect-of-the-partner-activation-setting" />

<Accordion title="Efek dari pengaturan aktivasi mitra">

Tabel berikut ini menyajikan dampak pengaturan aktivasi mitra pada atribusi dan postback dalam berbagai skenario.

<table><thead><tr><th>Skenario</th><th>Aktifkan mitra<br/>Aktif</th><th>Aktifkan mitra Nonaktif</th></tr></thead><tbody><tr><td><p>Atribusi dan postback untuk penginstalan baru, <span>atribusi ulang, dan interaksi ulang</span></p></td><td><p><strong>Atribusi:</strong> Ya</p><p><strong>Postback:</strong> Ya</p></td><td><p><strong>Atribusi:</strong> Tidak</p><p><strong>Postback:</strong> Tidak</p></td></tr><tr><td><span>Interaksi (klik) terjadi sebelum penonaktifan; pemasangan/atribusi ulang/interaksi ulang terjadi setelah penonaktifan</span></td><td><p><span>Tak dapat diterapkan</span></p></td><td><p><span>Mitra yang dinonaktifkan tidak akan dikaitkan.</span></p></td></tr><tr><td>Klik iklan </td><td colspan="2"><p>Ditampilkan di bawah nama mitra dalam data agregat tetapi tidak digunakan sebagai dasar untuk atribusi</p></td></tr><tr><td>Atribusi SKAN</td><td colspan="2"><p>Tak dapat diterapkan</p><p>Ketika atribusi SKAN dikonfigurasikan, data SKAN direkam, baik ketika <strong>Mengaktifkan mitra</strong> dinyalakan maupun dinonaktifkan. </p></td></tr></tbody></table>

</Accordion>

## Mengaktifkan integrasi mitra

**Untuk mengaktifkan atau mengedit integrasi utama (tab Integrasi) dari aplikasi yang sedang dipilih:**

1. **Untuk mengaktifkan:** Di AppsFlyer, dari menu samping, pilih**Kolaborasi**>**Pasar Mitra**.  
   Untuk mengedit: **Di AppsFlyer, dari menu samping, pilih** Kolaborasi **>** Integrasi Aktif.
2. Cari mitra dan pilih itu. Anda diarahkan ke halaman pengaturan integrasi.
3. Dari tab **Integrasi** , nyalakan  **Aktifkan mitra**.
4. Klik **Simpan Integrasi**.

Lihat [jenis integrasi lainnya](#integration-types).

> ❗️ **Perhatian**
>
> Pastikan untuk tidak menggunakan pengaturan **Aktifkan mitra** untuk menjeda atau mengakhiri kampanye. Melakukan hal tersebut dapat menyebabkan kerusakan permanen pada pengukuran kampanye aktif.

#### Siapa yang dapat mengaktifkan integrasi?

Integrasi mitra dapat diaktifkan oleh pemasar dan agensi sesuai dengan tabel berikut.

| Diaktifkan oleh | SRN | Non-SRN |
| --- | --- | --- |
| Pemasar | Diaktifkan untuk penggunaan sendiri dan atas nama agensi | Mengaktifkan untuk penggunaan sendiri |
| Agensi | Tidak dapat mengaktifkan | Mengaktifkan non-SRN yang ditunjuk oleh agensi |

## Menonaktifkan integrasi mitra

Anda dapat menonaktifkan integrasi mitra aplikasi Anda dengan menonaktifkan sakelar **Aktifkan mitra**. Ini berarti mitra tidak mendapatkan atribusi konversi dan postback tidak dikirimkan kepada mereka. Namun, jika salah satu [jenis integrasi](#integration-types) lainnya masih diaktifkan, maka jenis integrasi tersebut akan tetap beroperasi bahkan setelah tombol **Aktifkan mitra** dinonaktifkan. Ini berarti bahwa **integrasi masih Aktif** dan data masih dapat dikumpulkan.

<span id="deactivating-a-partner"></span>**Untuk menonaktifkan integrasi mitra:**

1. Di AppsFlyer, dari menu samping, pilih **Kolaborasi** > **Integrasi Aktif**.
2. Cari mitra dan pilih itu. Anda diarahkan ke halaman pengaturan integrasi.
3. Dari tab **Integrasi** , nonaktifkan  **Aktifkan mitra.**
4. Klik **Simpan Integrasi**.
5. Untuk menonaktifkan mitra sepenuhnya dari semua [jenis integrasi lainnya](#integration-types), buka setiap tab pada halaman integrasi dan nonaktifkan.  
   **Catatan:** Untuk iklan Google dan Meta, untuk berhenti merekam data SKAN, buka tab SKAN dan hapus koneksi.
6. Klik **Simpan Integrasi**.
7. [Opsional] Setelah menyimpan integrasi, sambil tetap berada di halaman konfigurasi, Anda dapat **menonaktifkan mitra dari aplikasi lain:**
   1. Dari pojok kiri atas, di bawah nama mitra, klik nama aplikasi untuk membuka daftar aplikasi.
   2. Pilih aplikasi lainnya dari daftar tarik-turun.
   3. Ulangi langkah 2-4.

### Menonaktifkan integrasi yang tidak digunakan

Mitra yang pengaturan **Aktifkan mitra** tetap aktif setelah Anda berhenti menjalankan kampanye dengan mereka akan terus menerima kiriman balasan yang berisi data kampanye. Mengingat potensi masalah privasi data, pertimbangkan untuk menonaktifkan integrasi yang tidak digunakan sebagai tindakan pencegahan. Untuk membantu mengidentifikasi integrasi mitra yang tidak digunakan dari 30+ hari terakhir yang masih aktif, dan mengingatkan Anda untuk menonaktifkannya, sebuah pesan peringatan akan muncul di bagian atas halaman Integrasi aktif.

![active-integrations-deactivate-message-mini2.png](https://support.appsflyer.com/hc/article_attachments/16666444578449)

Pesan tersebut menyertakan tautan ke kotak dialog **Nonaktifkan integrasi yang tidak digunakan** yang menampilkan integrasi dari aplikasi yang saat ini dipilih tanpa konversi terbaru. Dari halaman ini, Anda dapat meninjau integrasi yang tidak aktif dan memilih mana yang akan dinonaktifkan.

> 📘 **Catatan**
>
> Ketika menonaktifkan integrasi melalui kotak dialog, hanya integrasi utama yang dinonaktifkan (sakelar **Aktifkan mitra** dimatikan). Jika [jenis integrasi lainnya](#integration-types) tetap aktif, integrasi masih dianggap aktif.

**Untuk melihat dan menonaktifkan integrasi mitra yang tidak digunakan:**

1. Di AppsFlyer, dari menu samping, pilih **Kolaborasi** > **Integrasi** **Aktif**.
2. Dari pesan peringatan di bagian atas halaman, klik **Tinjau dan nonaktifkan**.
3. Dari kotak dialog **Nonaktifkan integrasi yang tidak digunakan**, Anda dapat melihat semua integrasi mitra yang tidak digunakan dari aplikasi yang saat ini dipilih.  
   **Catatan:** Daftar ini diurutkan berdasarkan integrasi mitra yang tidak digunakan dengan jumlah postback terbanyak yang dikirim.
4. Pilih integrasi mitra untuk dinonaktifkan.
5. Klik **Nonaktifkan**. Setelah konfirmasi, integrasi mitra yang dipilih akan dinonaktifkan.
6. Untuk menonaktifkan mitra sepenuhnya dari semua [jenis integrasi lainnya](#integration-types), buka setiap tab pada halaman integrasi dan nonaktifkan.  
   **Catatan:** Untuk iklan Google dan Meta, untuk berhenti merekam data SKAN, buka tab SKAN dan hapus koneksi.

Sebagai alternatif, mitra dapat dinonaktifkan dengan membuka halaman integrasi mitra tertentu dan menonaktifkan salah satu [jenis integrasi](#integration-types) dari tab yang relevan.

> 📘 **Catatan**
>
> * Ketika menonaktifkan integrasi dari kotak dialog, hanya sakelar **Aktifkan mitra** yang dimatikan. Jika salah satu [jenis integrasi lainnya](#integration-types) masih aktif, integrasi mitra akan dianggap aktif.
> * Pemasar harus memperhatikan bagaimana platform mereka menangani penonaktifan mitra dalam skenario tertentu. Demikian pula, mitra pemasaran dan analitik yang memerlukan balasan harus diaktifkan.

#### Siapa yang dapat melihat pesan peringatan dan menonaktifkan integrasi yang tidak digunakan?

* Pengguna akun dapat melihat pesan ini hanya untuk mitra yang dapat mereka edit konfigurasinya
* Agensi melihat pesan tersebut namun hanya dapat menonaktifkan integrasi mereka sendiri.
* Mitra **tidak dapat melihat** pesan penonaktifan, meskipun mereka memiliki izin untuk mengonfigurasi integrasi.

## Akses Mitra dan Agensi ke dasbor

Mitra dan agensi memiliki tampilan dasbor dan opsi konfigurasi yang berbeda, sesuai dengan izin mereka.

### Visibilitas mitra

* Mitra melihat pengaturan **Aktifkan mitra** dalam mode hanya-baca. Hal ini terjadi bahkan jika mitra memiliki izin untuk mengonfigurasi integrasi.
* Visibilitas pengaturan mitra tergantung pada apakah pemasar atau agensi yang mengonfigurasi integrasi, seperti yang dirinci dalam tabel berikut:

| Integrasi dikonfigurasi oleh | Pengaturan yang dapat dilihat oleh mitra |
| --- | --- |
| Pemasar | Ya |
| Agensi | Tidak |

### Hak Akses Agensi

Anda bisa memberikan izin kepada agensi untuk bekerja dengan aplikasi Anda dan menjalankan lalu lintas atas nama Anda.

**Untuk memberikan izin agensi pada aplikasi:**

1. Di AppsFlyer, dari menu samping, pilih **Kolaborasi** > **Integrasi** **Aktif**.
2. Temukan agensi dan pilihlah.
3. Buka tab **Izin** dan nyalakan pada **Izin Agensi.**
4. [Opsional] Berikan <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#hak-akses-agensi">izin</Anchor> tambahan kepada agensi.

> 📘 **Catatan**
>
> * **Agensi** dapat mengaktifkan atau menonaktifkan pengaturan **Aktifkan mitra** untuk **mitra non-SRN**.
> * **Pemasar** dapat mengaktifkan atau menonaktifkan pengaturan **Aktifkan mitra** untuk **SRN**. Ketika melakukannya, instalasi dari SRN tersebut **tidak dikaitkan dengan agensi.**

#### Izin agensi yang dinonaktifkan

Ketika izin dinonaktifkan untuk agensi:

* Agensi tidak dapat mengakses aplikasi di dasbor AppsFlyer.
* Penginstalan dan acara baru tidak dikaitkan dengan agensi.
* Postback tidak dikirim ke sumber media yang digunakan oleh agensi.
* Peristiwa baru dari konversi sebelum menonaktifkan agensi dikaitkan dan ditampilkan di dasbor pemasar, tetapi postback tidak dikirim ke sumber media.

Catatan: **Jika pemasar menonaktifkan izin keagenan, data historis keagenan (seperti pemasangan dan biaya) menjadi tidak transparan.**

Contoh berikut menjelaskan apa yang terjadi pada lalu lintas yang terus dikirim setelah pemasar menghapus izin keagenan:

> 📄 **Contoh 1**
>
> **Kampanye agensi dengan non-SRN (mitra tautan atribusi)**
>
> Lalu lintas dikaitkan ke organik, atau ke keterlibatan sebelumnya jika masih dalam jendela penelusuran. Agensi tidak dikaitkan.
>
> Contoh ini juga berlaku untuk skenario di mana AppsFlyer menerima tautan atribusi klik-tayang serta meminta API mitra

> 📄 **Contoh 2**
>
> **Kampanye agensi dengan SRN (mitra tautan atribusi)**
>
> Trafik dikaitkan ke SRN di dasbor pemasar, tetapi tidak dikaitkan ke agensi.

<div data-zendesk-anchors="overview=iktisar-aktivasi h_01HRA982WC3519NMGXV5WEY1AZ=iktisar-aktivasi %20data-title%3D=data-title h_01HRAERWRJN1J9Z4BYHY9NSND7=data-title h_01HRAERWRJPQTT9GZA5M10ARW2=integration-activity-indication h_01HRPMG9SJHE32VMWS89P2HFAQ=catatan h_01HRAERWRJ2SBRY9XQG983WP5M=effect-of-the-partner-activation-setting activating-a-partner=mengaktifkan-integrasi-mitra h_01HJR1D6THJ9TNGZZV78SEVBZN=mengaktifkan-integrasi-mitra h_01HJR1D6THSEA65CY71VWJYX1P=perhatian who-can-activate-partners=siapa-yang-dapat-mengaktifkan-integrasi h_01HJR1D6THRMF854SCSFVZFWM9=siapa-yang-dapat-mengaktifkan-integrasi deactivated-partners=menonaktifkan-integrasi-mitra h_01HJR1D6THE2QWSF971VQFXCBX=menonaktifkan-integrasi-mitra h_01HJR1D6THS60X7VTDN2X6FT0K=deactivating-a-partner deactivate-unused-integrations=menonaktifkan-integrasi-yang-tidak-digunakan h_01HJR1D6THFWAZX3NSWYSD9126=menonaktifkan-integrasi-yang-tidak-digunakan h_01HJR1D6TH329RWMW3F1E5YZCT=catatan-1 h_01HJR1D6THC13ZPV7H3CK8HYSV=catatan-2 who-can-see-the-warning-message-and-deactivate-unused-integrations=siapa-yang-dapat-melihat-pesan-peringatan-dan-menonaktifkan-integrasi-yang-tidak-digunakan h_01HRAK82N9J99VCEVF9KSJQVQR=siapa-yang-dapat-melihat-pesan-peringatan-dan-menonaktifkan-integrasi-yang-tidak-digunakan partner-and-agency-dashboards=akses-mitra-dan-agensi-ke-dasbor h_01HJR1D6THB0N1C8XCC5YAMQQ3=akses-mitra-dan-agensi-ke-dasbor partner-visibility=visibilitas-mitra h_01HJR1D6TJ6D3TV2PCFWP4SEAR=visibilitas-mitra agency-permissions=hak-akses-agensi h_01HJR1D6TJ9PHVG6GGQ2Z1KJRQ=hak-akses-agensi h_01HJR1D6TJ9T55PSPBRNW1XXS7=catatan-3 disabled-agency-permissions=izin-agensi-yang-dinonaktifkan h_01HJR1D6TJ1ABQM6HCPK277R0Z=izin-agensi-yang-dinonaktifkan h_01HJR1D6TJBT0D3G2KWKFKEW5S=contoh-1 h_01HJR1D6TJTXF49JP3VJE6ZYC9=contoh-2" />
