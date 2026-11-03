---
title: Pengukuran Uninstall
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2021-10-14T08:03:47Z'
  edited_at: '2023-11-15T15:21:04Z'
  id: 4408933557137
  locale: id
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/id/articles/4408933557137
---
> **Sekilas**: Ukur rasio uninstal untuk aplikasi Anda dan tentukan sumber mana (sumber media, kampanye, materi iklan, dan geo) yang mendatangkan pengguna berkualitas.

## Ringkasan

Untuk memahami nilai pengguna aplikasi, Anda harus menganalisis tingkat penginstalan dan uninstall. Metrik uninstal dapat membantu Anda mengukur performa aplikasi, serta memahami kapan dan mengapa pengguna meninggalkan aplikasi Anda.

### Bagaimana Cara Kerja API ini?

AppsFlyer menggunakan notifikasi push senyap, dikirim sekali sehari, untuk memverifikasi apakah aplikasi masih terpasang di perangkat tertentu. Jika tidak ada respons, penghapusan instalan dicatat, dan dikaitkan dengan sumber media yang awalnya membawa pengguna.

## Cara menggunakan uninstall data

Berikut adalah beberapa contoh yang dapat Anda pelajari dari mengukur uninstall, dan cara menggunakan data tersebut untuk mengoptimalkan kampanye dan interaksi pengguna.

<div id="compare-the-quality-of-sources" />

<Accordion title="Bandingkan kualitas sumber">

Dengan membandingkan kualitas pengguna yang diperoleh dari berbagai sumber (sumber media, kampanye, materi iklan, dan geo), Anda dapat menentukan sumber media dengan tingkat uninstall terendah, dan mengalokasikan kembali dana ke sumber tersebut.

> 📄 **Contoh**
>
> Anda adalah pemasar aplikasi game untuk PlayIt Gaming International. Anda baru saja meluncurkan aplikasi baru dan menjalankan kampanye di dua sumber media yang berbeda (Sumber media A,  dan Sumber media B).
>
> Saat Anda memeriksa dashboard, Anda melihat bahwa meskipun Sumber media A memiliki jumlah penginstalan tertinggi (10.390), sumber ini juga memiliki tingkat uninstall tertinggi (30%).
>
> Sumber media B, di sisi lain, memiliki 5.949 penginstalan dan tingkat uninstall terendah (12%).
>
> [![Uninstall rates.png](https://files.readme.io/36fb732bfe3a63729b1aa0913f2fe3f24df6a7c86adde9f5c2b95424d840dec4-33839423253137.png)](https://files.readme.io/36fb732bfe3a63729b1aa0913f2fe3f24df6a7c86adde9f5c2b95424d840dec4-33839423253137.png)
>
> Berdasarkan wawasan ini, Anda dapat mengalokasikan lebih banyak anggaran ke Sumber media B dan mencoba mendapatkan lebih banyak pengguna yang terlibat.

</Accordion>

<div id="share-uninstall-data-with-ad-networks-for-optimization" />

<Accordion title="Bagikan data uninstall dengan jaringan iklan untuk pengoptimalan">

Mengirim postback event uninstall ke jaringan iklan tempat Anda bekerja berguna untuk mengoptimalkan kampanye akuisisi pengguna. Anda dapat mengirimkan event uninstall dengan [memetakan af\_uninstall ke jaringan iklan Anda](/docs/measure-uninstalls#memetakan-event-uninstall). Setelah pemetaan selesai, event dikirim setiap kali pengguna diidentifikasi telah uninstall aplikasi. Jaringan iklan dapat menggunakan informasi ini untuk menentukan pengguna mana yang kurang terlibat dan berfokus untuk mendapatkan lebih banyak pengguna yang terlibat.

> 📄 **Contoh**
>
> Anda adalah pemasar aplikasi game untuk PlayIt Gaming International. Sumber media A adalah jaringan iklan tempat Anda bekerja dengan peluncuran aplikasi Android baru Anda. Di kampanye sebelumnya Anda menjalankan dengan Sumber media A, 1.000 pengguna baru memasang aplikasi Anda, dan selanjutnya, 300 pengguna melakukan uninstall aplikasi. Untuk kampanye baru, Anda ingin Sumber media A menerima data di-uninstall. Ini akan memungkinkan sumber Media A untuk mengatasi tantangan uninstall dengan cepat.
>
> Berdasarkan wawasan dari kampanye sebelumnya, Sumber media A membuat daftar pengecualian kampanye yang mengecualikan jenis pengguna tertentu dari iklan yang berjalan di kampanye baru Anda:
>
> * Pengguna yang telah membuktikan bahwa mereka bernilai lebih rendah untuk aplikasi Anda.
> * Pengguna yang secara teratur meng-uninstall aplikasi Anda.
>
> Hal ini memungkinkan Sumber media A mengoptimalkan penargetan audiens untuk memastikan bahwa anggaran kampanye Anda tidak terbuang sia-sia untuk pengguna yang tidak perlu melihat iklan kampanye tertentu.

</Accordion>

<div id="exclude-uninstalls-from-retargeting-campaigns" />

<Accordion title="Kecualikan uninstall dari kampanye penargetan ulang">

Dalam beberapa kasus, untuk mematuhi <Anchor target="_blank" href="/marketers/id/docs/apply-privacy-preserving-sdk-methods#skenario-ikut-serta-dan-tidak-ikut-serta">peraturan seperti GDPR dan CCPA</Anchor>, Anda mungkin perlu mengecualikan pengguna yang melakukan uninstall aplikasi Anda dari kampanye penargetan ulang. Informasi uninstall memungkinkan Anda membuat daftar pengecualian dan menerapkan tindakan privasi untuk melindungi privasi dan data pelanggan Anda.

Metode untuk mengecualikan pengguna termasuk yang berikut:

* <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview#user-journey-report-availability">Laporan data lengkap:</Anchor> Metode manual di mana Anda mengambil daftar pengguna yang dihapus dari laporan **Uninstall** dan membuat daftar pengecualian.
* <Anchor target="_blank" href="/marketers/id/docs/audiences-guide">Audiens AppsFlyer:</Anchor> Metode otomatis di mana Anda menentukan audiens target berdasarkan kriteria tertentu (misalnya, pengguna yang **belum** meng-uninstall aplikasi Anda). Pengguna yang tidak memenuhi kriteria akan dikecualikan dari audiens.

> 📄 **Contoh**
>
> Anda adalah pemasar aplikasi game untuk PlayIt Gaming International. Anda sedang menjalankan kampanye penargetan ulang untuk salah satu aplikasi Android Anda dan Anda memutuskan untuk menggunakan Audiens AppsFlyer untuk menentukan audiens penargetan ulang. Kriteria audiens Anda adalah sebagai berikut:
>
> * Pengguna yang belum meng-uninstall aplikasi.
> * Pengguna yang belum meluncurkan aplikasi dalam 30 hari terakhir.
>
> Ini memungkinkan Anda untuk membuat audiens penargetan ulang yang lebih tepat. Saat kampanye penargetan ulang Anda berjalan, iklan hanya akan ditayangkan kepada pengguna yang ditentukan di audiens penargetan ulang Anda.

</Accordion>

## Menyiapkan pengukuran uninstall

Proses penyiapan metrik uninstall mengharuskan pemasar dan pengembang bekerja sama. Petunjuk penerapan bergantung pada sistem operasi yang menjalankan aplikasi Anda.

Alur untuk pemasar dan pengembang adalah sebagai berikut:

<Tabs>
<Tab title="Android">

| Tugas | Pemilik |
| --- | --- |
| [Hubungkan Firebase Cloud Messaging (FCM) ke AppsFlyer](/docs/measure-uninstalls#hubungkan-firebase-cloud-messaging-ke-appsflyer-android) | Pemasar |
| [Untuk mengonfigurasi pengukuran uninstall di AppsFlyer](/docs/measure-uninstalls#untuk-mengonfigurasi-pengukuran-uninstall-di-appsflyer) | Pemasar |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">Integrasikan dengan SDK</Anchor> | Pengembang Android |
| [Uji pengukuran uninstall](/docs/measure-uninstalls#menguji-pengukuran-uninstall) | Pemasar |
| [Opsional] [Petakan event uninstall](/docs/measure-uninstalls#memetakan-event-uninstall) ke mitra yang relevan di dashboard | Pemasar |

</Tab>

<Tab title="iOS">

| Tugas | Pemilik |
| --- | --- |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement-ios#creating-a-p12-certificate">Hasilkan sertifikat P12</Anchor> | Pengembang iOS |
| [Untuk mengonfigurasi pengukuran uninstall di AppsFlyer](/docs/measure-uninstalls#untuk-mengonfigurasi-pengukuran-uninstall-di-appsflyer) | Pemasar |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">Integrasikan dengan SDK</Anchor> | Pengembang iOS |
| [Uji pengukuran uninstall](/docs/measure-uninstalls#menguji-pengukuran-uninstall) | Pemasar |
| [Opsional] [Petakan event uninstall](/docs/measure-uninstalls#memetakan-event-uninstall) ke mitra yang relevan di dashboard | Pemasar |

</Tab>
</Tabs>

## Prosedur implementasi

Implementasi mengharuskan pengembang seluler Anda untuk mengintegrasikan mekanisme yang merespons notifikasi push ke aplikasi Anda. Instruksi implementasi bervariasi sesuai dengan sistem operasi.

### Hubungkan Firebase Cloud Messaging ke AppsFlyer (Android)

Pengukuran uninstal Android tersedia dengan mengonfigurasi pengukuran uninstal di AppsFlyer dan mengadopsi Firebase Cloud Messaging (FCM) ke dalam aplikasi Anda.

<div id="http-v1" />

<Accordion title="HTTP V1">

**Untuk mengonfigurasi FCM HTTP V1 untuk uninstall:**

1. **Untuk mendapatkan ID Proyek** :
   1. Buka [FCM console.](https://console.firebase.google.com/)
   2. Pilih sebuah proyek.
   3. Buka **Project Overview** > **Project settings**.

      ![UninstallFirebase.png](https://files.readme.io/15e74e10daa2f1f1d872f0c8fea274c9819c52c4655baa903728257dd6337e80-33839423254289.png)
   4. Salin ID Proyek. Anda akan membutuhkannya di tahap proses selanjutnya.
2. **Untuk menetapkan fungsi uninstall ke AppsFlyer:**
   1. Buka tab **Service accounts**.
   2. Klik **Manage service account permissions**.   
      Tab browser baru dibuka di Google Cloud Platform.
   3. Di menu samping, pilih **Roles (Fungsi)**.
   4. Klik **+ Create role.**
   5. Selesaikan sebagai berikut:
      * Judul: Masuk ke **uninstall AppsFlyer.**
      * ID: Masuk `af_uninstalls`.
      * Tahap peluncuran fungsi: Pilih **General availability**.
   6. Temukan lalu pilih `cloudmessaging.messages.create`.  

      ![AddPermissions.png](https://files.readme.io/efd461ecb74a61c15232e30a6e10eaaecac18f2e24a28565ba8b208ce0654d1a-5542178507665.png)
   7. Klik **Add**.
   8. Klik **Create**.
3. **Untuk menetapkan fungsi uninstall FCM ke AppsFlyer:**
   1. Di menu samping, pilih **IAM** .
   2. Klik **+ Add.**
   3. Di bidang **New members (Anggota baru)** masukkan af-uninstalls-tracking@af-uninstalls-tracking.iam.gserviceaccount.com
   4. Di daftar **Pilih peran** , pilih **Uninstall AppsFlyer**.
   5. Klik **Save**.   
       Akun layanan AppsFlyer telah diberi peran uninstall AppsFlyer.

</Accordion>

<div id="legacy-http" />

<Accordion title="[Tidak digunakan lagi] HTTP lama">

> 🚧 **Penting!**
>
> API HTTP lama tidak digunakan lagi oleh Firebase pada tanggal 20 Juni 2023, dan akan dihapus pada Juni 2024. Jika Anda menggunakan API lama, kami sangat menyarankan agar Anda [menggunakan HTTP v1 API](/docs/measure-uninstalls#http-v1). <Anchor target="_blank" href="https://firebase.google.com/docs/cloud-messaging/http-server-ref">Pelajari lebih lanjut</Anchor>

Pengukuran uninstall menggunakan Firebase Messaging didukung oleh Android SDK V4.7.0 +

**Untuk mendapatkan kode server Firebase:**

1. Buat proyek Aplikasi Android Firebase (jika Anda belum melakukannya), atau migrasikan proyek Anda dari **Google Developer Console** (ikuti petunjuk di sana). Untuk informasi lebih lanjut, buka <Anchor target="_blank" href="https://firebase.google.com/docs/cloud-messaging/android/client">Firebase</Anchor>.
2. Buka Firebase <Anchor target="_blank" href="https://console.firebase.google.com">Console</Anchor>.
3. Di halaman Firebase Console, arahkan ke Project Settings (klik pada ikon roda gigi di dekat Project Overview di panel kiri halaman tersebut).

   ![firebase_cloud_messaging_server_key.png](https://files.readme.io/4e31c02a1bea013c823b0148ba1704d4492f66d04e23f0e13e00a9c0c22d286c-33839382513041.png)
4. Di tab Cloud Messaging, Anda melihat dua Kode Server.
5. Copy **kode server**.

</Accordion>

### Untuk mengonfigurasi pengukuran uninstall di AppsFlyer

<Tabs>
<Tab title="Android">

**Prasyarat**: Pengembang Android harus menyelesaikan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">instruksi integrasi</Anchor> mereka.

**Untuk mengonfigurasi pengukuran uninstall di AppsFlyer**:

1. Di AppsFlyer, buka **Configuration** > **App Settings**.
2. Jika perlu, aktifkan **Uninstall measurement**.
3. Pilih **HTTP V1, dan masukkan ID proyek yang Anda siapkan sebelumnya.**

   ![UninstallHTTPV1.png](https://files.readme.io/80d13e47ea7ae1585d2ecc0e2f7210572e47dba936557c8e96314e49b0d738d8-33839423258641.png)
4. Klik **Uji koneksi**.  
   Berhasil! pesan ditampilkan.
5. Klik **Save settings**.

</Tab>

<Tab title="iOS">

**Prasyarat**: Pengembang Android harus menyelesaikan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">instruksi integrasi</Anchor> mereka.

**Untuk mengonfigurasi pengukuran uninstall di AppsFlyer:**

1. Dapatkan file P12 dari pengembang Anda.
2. Di AppsFlyer, buka **Configuration** > **App Settings.**
3. Gulir ke bawah ke bagian Uninstall.
4. Aktifkan**Uninstall measurement**.

   ![Uninstall_iOS_p2.png](https://files.readme.io/3f9de3ebe6099886fa9bc210bd6e491ba91e8ff2c890c980f66c4d48398a597c-33839423260561.png)
5. Klik ikon unggah, dan pilih file P12.
6. [Opsional] Jika sertifikat P12 dilindungi kata sandi, masukkan kata sandi.
7. Klik **Validasi** untuk mengirim sertifikat ke AppsFlyer untuk verifikasi.
8. Klik **Save Settings**.

</Tab>
</Tabs>

## Menguji pengukuran uninstall

Setelah prosedur implementasi selesai, Anda dapat menginstal dan menghapus penginstalan aplikasi untuk menguji apakah uninstall direkam dengan benar. Tingkat uninstall dan uninstall ditampilkan di dashboard Ikhtisar. 

<Tabs>
<Tab title="Android">

Anda dapat melakukan pengujian ini pada aplikasi yang:

* Di Google Play Store
* Tertunda (tidak terdaftar di Google Play Store)
* Tersedia melalui unduhan langsung
* Di toko aplikasi alternatif

Perhatikan hal berikut saat menguji aplikasi Android:

* Pengukuran uninstall diproses <Anchor target="_blank" href="/marketers/id/docs/about-data-freshness-and-timezone-support#uninstalls">setiap hari</Anchor>. Peristiwa uninstall didaftarkan dalam waktu 24 jam, tetapi jika aplikasi diinstal ulang selama waktu ini, event tidak akan direkam.
* **Peristiwa penghapusan penginstalan memerlukan waktu hingga 48 jam untuk ditampilkan** dalam <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">laporan data lengkap</Anchor> dan di dashboard AppsFlyer (Laporan Kinerja Gabungan).

</Tab>

<Tab title="iOS">

Ingatlah hal-hal berikut saat menguji aplikasi iOS:

* Penghapusan penginstalan tidak langsung muncul di dashboard AppsFlyer. Dikarenakan layanan Apple Push Notification, waktu yang diperlukan uninstall untuk muncul di dashboard adalah minimal 9 hari. AppsFlyer memperbarui dan mengagregasi metrik untuk uninstall setiap 24 jam.

  <div id="h_01HB8CXQ49QN0PH138V2PD2QXE" />

  > 📄 **Contoh**
  >
  > * Hari ke-1: pengguna menginstal aplikasi Anda.
  > * Hari ke-4: pengguna meng-uninstall aplikasi Anda.
  > * Hari ke-12: Layanan Notifikasi Push Apple melaporkan penghapusan aplikasi 8 hari setelah uninstall.
  > * Hari ke-13: Data uninstall muncul di dashboard AppsFlyer dan data lengkap.

* Jika Anda melakukan pengujian pada versi pengujian aplikasi, pastikan Anda menggunakan lingkungan sandbox. Lihat petunjuk pengembang untuk [prosedur uninstall sandbox](https://dev.appsflyer.com/hc/docs/uninstall-measurement-ios#testing-uninstall-measurement).

</Tab>
</Tabs>

## Memetakan Event Uninstall

![Uninstall_event_postback.png](https://files.readme.io/9c3c7f3fd330720d4f6f41fdf509c5af00d042291c1350ab83a1951464ac8e8f-33839423261713.png)

Untuk berbagi data uninstall dengan jaringan iklan, <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#g">event af\_uninstall</Anchor> harus dipetakan ke mitra. Tidak seperti postback untuk in-app event biasa, event uninstall tidak dikirim secara waktu aktual. Waktu event yang dilaporkan menunjukkan waktu yang ditentukan AppsFlyer saat aplikasi dihapus penginstalannya, dan bukan saat uninstall itu sendiri.

Ingatlah hal berikut:

* AppsFlyer hanya dapat mengirimkan postback jika event tersebut benar-benar terjadi dan direkam oleh AppsFlyer.
* Jika Anda tidak melihat uninstall di halaman Ikhtisar dashboard atau di laporan data lengkap, ini berarti postback uninstall tidak dikirim ke mitra, meskipun event **af\_uninstall** telah dipetakan.

#### Batasan

* Event uninstall tidak termasuk dalam laporan postback in-app event.
* Event **af\_uninstall** didukung oleh semua mitra. Jika Anda ingin memetakannya ke mitra, tetapi acara tersebut tidak tersedia di tab Integrasi mitra, hubungi CSM Anda atau hubungi [hello@appsflyer.com](mailto:hello@appsflyer.com).

<Tabs>
<Tab title="Firebase">

aturan firebase

</Tab>

<Tab title="GCM">

aturan GCM

</Tab>
</Tabs>

## Sedang menonaktifkan pengukuran uninstall

<Tabs>
<Tab title="Android">

Jika Kode Server Firebase/GCM disediakan, pengukuran uninstall aplikasi diaktifkan secara default. Pemilik aplikasi dapat menonaktifkan fitur ini melalui dasbor.

</Tab>

<Tab title="iOS">

Jika sertifikat P12 disediakan dan divalidasi, pengukuran uninstall aplikasi diaktifkan secara default. Pemilik aplikasi dapat menonaktifkan fitur ini melalui dashboard.

</Tab>
</Tabs>

**Catatan:** Agar uninstall dilaporkan, **Aktifkan pengukuran uninstall** harus diaktifkan pada saat aplikasi diinstal. Penginstalan yang terjadi ketika **Enable uninstalls measurement (Aktifkan pengukuran uninstall)** tidak aktif, tidak dilaporkan.

#### **Untuk mematikan pengukuran uninstall**:

1. Di AppsFlyer, buka **App settings**.
2. Gulir ke **Attribution** (Atribusi) > **Uninstall measurement** (Pengukuran uninstall) dan nonaktifkan **Enable uninstall measurement** (Aktifkan pengukuran uninstall).

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Sifat | Catatan |
| --- | --- |
| CUID | CUID tidak dikirim dalam postback uninstall. |

</Accordion>

<div data-zendesk-anchors="overview=ringkasan h_01HB8CXQ4824V2WEPYGK8YS4DC=ringkasan how-does-it-work=bagaimana-cara-kerja-api-ini h_01HB8CXQ48JEJECC1HR79DXCRK=bagaimana-cara-kerja-api-ini how-to-use-uninstall-data=cara-menggunakan-uninstall-data h_01HB8CXQ48E2SRN95MH4E2H7ZH=cara-menggunakan-uninstall-data h_01HB8CXQ48HX9RH50G45FZMZTK=compare-the-quality-of-sources h_01HB8CXQ48DZYQW7FYBD3XYREM=contoh h_01HB8CXQ488E22GPCEBE69VQ3M=share-uninstall-data-with-ad-networks-for-optimization h_01HB8CXQ48ZE5TTZRPQE5SEKJS=contoh-1 h_01HB8CXQ48JTET73GH0QQBX5HF=exclude-uninstalls-from-retargeting-campaigns h_01HB8CXQ4832ZHRYQECYCQPP66=contoh-2 setting-up-uninstall-measurement=menyiapkan-pengukuran-uninstall h_01HB8CXQ4810HTB45FAS5ZVRHF=menyiapkan-pengukuran-uninstall implementation-procedures=prosedur-implementasi h_01HB8CXQ489HRF72VRZ4G532GX=prosedur-implementasi connect-firebase-cloud-messaging-to-appsflyer-android=hubungkan-firebase-cloud-messaging-ke-appsflyer-android h_01HB8CXQ48ZD5Y0RKTG1W51TKW=hubungkan-firebase-cloud-messaging-ke-appsflyer-android h_01HB8CXQ4865MNVG0VERSNSE3F=http-v1 h_01HB8CXQ48H079WQ6Q6G0XSQC7=legacy-http h_01HB8CXQ48ENMG65YH5ECGST9Z=penting configure-uninstall-measurement-in-appsflyer=untuk-mengonfigurasi-pengukuran-uninstall-di-appsflyer h_01HB8CXQ48CVA9B8B78W0H357C=untuk-mengonfigurasi-pengukuran-uninstall-di-appsflyer testing-uninstall-measurement=menguji-pengukuran-uninstall h_01HB8CXQ48SW2TT5Z85XD3XWT6=menguji-pengukuran-uninstall mapping-the-uninstall-event=memetakan-event-uninstall h_01HB8CXQ499ABX9ZGDFB1VAE8W=memetakan-event-uninstall limitations=batasan h_01HB8CXQ49F2ARQTEV8Q032P9V=batasan turning-off-uninstall-measurement=sedang-menonaktifkan-pengukuran-uninstall h_01HB8CXQ49Y5NCG7GK93HXHYMD=sedang-menonaktifkan-pengukuran-uninstall to-turn-off-uninstall-measurement=untuk-mematikan-pengukuran-uninstall h_01HB8CXQ49WXZS4M6CK5XG1BCX=untuk-mematikan-pengukuran-uninstall h_01HB8CXQ4916CJ9NDZWGWQHKSA=traits-and-limitations" />
