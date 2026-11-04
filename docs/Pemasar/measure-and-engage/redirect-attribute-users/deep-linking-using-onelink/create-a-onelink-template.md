---
title: Templat OneLink
metadata:
  keywords:
    - template
    - Marketers
    - Link Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Link Management
  created_at: '2014-11-03T12:35:49Z'
  edited_at: '2023-11-15T15:31:41Z'
  id: 207032246
  locale: id
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/id/articles/207032246
---
> **Sekilas:** Buat templat untuk membentuk dasar logika pengarahan untuk semua tautan OneLink yang Anda buat untuk berbagai kampanye pemasaran Anda. Template diperlukan untuk membuat tautan dan pengalaman pengguna akhir.

<div id="onelink-templates" />

## Templat OneLink

<Embed title="Pemutar video YouTube" typeOfEmbed="youtube" url="https://www.youtube.com/embed/d4AtCJ9122Q" providerUrl="https://www.youtube.com" />

templat OneLink:

* Bukan tautan yang dapat diklik untuk pengguna akhir Anda; ini adalah dasar untuk menghasilkan banyak tautan khusus. Biasanya, Anda hanya memerlukan satu templat per aplikasi (di luar pengujian) untuk menghasilkan tautan sebanyak yang Anda inginkan untuk semua kampanye iklan yang berbeda.
* Adalah tempat Anda merekam keputusan Anda tentang cara mengarahkan pengguna berdasarkan platform perangkat mereka dan apakah mereka telah menginstal aplikasi Anda atau tidak.
* Mewakili logika perutean sebagai inti dari semua tautan OneLink yang Anda buat untuk berbagai kampanye pemasaran Anda. Ini termasuk pengaturan pengarahan untuk:
  * Pengguna baru yang tidak menginstal aplikasi Anda ke toko aplikasi atau URL web yang benar.
  * **Pengguna yang sudah ada, yang menginstal aplikasi Anda** : Membuka aplikasi melalui Tautan Aplikasi Android, Tautan Universal iOS, atau skema URI. Ini melibatkan beberapa pekerjaan pengembang untuk disiapkan.
  * **Catatan**: Pengaturan pengarahan untuk situs web atau toko aplikasi dapat diganti pada tingkat tautan.

<div id="create-a-onelink-template" />

## Prosedur

| **Siapa saja yang terlibat**<ul><li>Hanya pemasar yang wajib untuk menyiapkan logika pengarahan untuk pengguna baru yang belum menginstal aplikasi Anda (misalnya, ke toko aplikasi atau halaman web yang benar).</li><li>Untuk menambahkan logika pengarahan bagi pengguna aplikasi yang sudah ada yang telah menginstal aplikasi Anda (misalnya, untuk membuka aplikasi), diperlukan pemasar dan pengembang Android/iOS.</li></ul> |
| --- |
| **Prasyarat**<ul><li>Akun AppsFlyer dengan setidaknya satu aplikasi.</li><li>Pemasar harus menjadi pengguna admin AppsFlyer, atau memiliki <Anchor target="_blank" href="/marketers/id/docs/user-management">izin untuk menambah/mengedit template OneLink</Anchor>.</li></ul> |
| **Waktu yang dibutuhkan**<br /><br />Sekitar 1,5 jam, bekerja sama dengan pengembang Android/iOS Anda. |
| **Hasil**<ul><li>Templat di mana Anda dapat membuat tautan yang mengarahkan pengguna ke toko aplikasi, halaman web, atau ke dalam aplikasi yang benar berdasarkan perangkat mereka.</li></ul> |

<div id="create-a-onelink-template-with-redirection-logic-for-new-app-users" />

<Accordion title="Buat templat OneLink dengan logika pengarahan untuk pengguna aplikasi baru">

**Untuk membuat templat OneLink:**

1. Di dasbor AppsFlyer, buka **Experiences & deep linking** > **OneLink management** .  
   OneLink adalah fitur tingkat akun, yang memungkinkan Anda membuat templat OneLink dan tautan kustom mereka untuk semua aplikasi Anda.  

   [![](https://files.readme.io/c5aacf61d1d1dc75ac7f0b9b6f681bb00e6521f6436fad3d2f073a42d4b0153f-4406696125713.png)](https://files.readme.io/c5aacf61d1d1dc75ac7f0b9b6f681bb00e6521f6436fad3d2f073a42d4b0153f-4406696125713.png)

   **Catatan** : Jika Anda tidak memiliki templat yang dibuat, panduan integrasi akan dibuka. Ikuti petunjuk di wizard dan abaikan prosedur lainnya ini.
2. Klik ikon menu > **Add OneLink template** .  
    Halaman pengaturan templat OneLink dibuka.  

   [![OneLink_template_page_en-us.png](https://files.readme.io/d773d60cd2febcf6a8389e9586e8ca23a1515fc853e4d42d0db98661cacb387a-360009665478.png)](https://files.readme.io/d773d60cd2febcf6a8389e9586e8ca23a1515fc853e4d42d0db98661cacb387a-360009665478.png)
3. Di kolom nama templat **OneLink**, masukkan nama.  

   <div id="note" />

   > 📘 **Catatan**
   >
   > * Nama template OneLink yang baik menyertakan **nama aplikasi** (misalnya feed\_me) atau kasus penggunaan atau pengalaman yang ditunjukkan oleh OneLink (misalnya pre\_launch\_landing\_page).
   > * Nama tidak boleh menyertakan nama kampanye atau saluran atau sumber media (karena ini bukan tautan pengguna akhir yang sebenarnya, hanya templat yang mendasari untuk membuat banyak tautan), atau nama platform (Android, iOS, karena banyak platform biasanya alasan untuk menggunakan templat OneLink di tempat pertama).
   > * Nama templat ini hanya digunakan secara internal. Hal tersebut tidak memengaruhi data atribusi pemasaran Anda dan tidak terlihat oleh pengguna.

4. Di kolom **Subdomain** , masukkan nama <Anchor target="_blank" href="/marketers/id/docs/appsflyer-knowledge-base-glossary#subdomain">subdomain</Anchor> Anda.
   * Pilih subdomain yang cocok dengan merek Anda. Misalnya, jika situs web Anda adalah www.abcd.com, pilih abcd sebagai subdomain Anda.
   * Pengguna akan melihat subdomain ini sebagai bagian dari URL tautan. Misalnya: `https://abcd.onelink.me/RPsv/37e5cd36`.
   * Subdomain tidak dapat diubah setelah tautan kustom dibuat berdasarkan template ini.
   * Gunakan hanya huruf kecil, digit, atau tanda hubung (-).
   * OneLink juga mendukung domain bermerek penuh, yang dapat membantu Anda meningkatkan kinerja kampanye dan meningkatkan eksposur merek. <Anchor target="_blank" href="/marketers/id/docs/brand-onelink-with-your-domain">Pelajari lebih lanjut</Anchor>
5. Pilih aplikasi Android, aplikasi iOS, atau keduanya.
6. Setel tempat untuk mengarahkan pengguna **Saat aplikasi tidak diinstal** .

   * Jika Anda telah memilih aplikasi Android dan aplikasi iOS, templat secara default dikonfigurasi untuk mengirim pengguna aplikasi baru ke toko aplikasi yang benar.
   * Jika Anda hanya memilih satu aplikasi, Android atau iOS, template dikonfigurasikan untuk mengirim SEMUA pengguna (iOS dan Android, baru dan yang sudah ada) ke satu tujuan yang ditentukan.
   * Jika Anda memilih aplikasi Android yang tidak ada di Google Play, Anda harus memasukkan URL tujuan pengarahan pengguna Android.
   * [opsional] **Arahkan ulang ke toko aplikasi pihak ketiga** jika aplikasi ada di toko lain selain Google Play. Pastikan aplikasi di toko lain memiliki nama paket yang sama dengan aplikasi Android yang dipilih di templat OneLink Anda.
   * [Opsional] **Ubah ke URL lainnya**: Dalam beberapa kasus, Anda mungkin lebih memilih untuk membawa pengguna baru ke pengalaman web seluler daripada langsung ke toko aplikasi (atau aplikasi Anda mungkin tidak tercantum di toko). Untuk menerapkan, masukkan URL tersebut di bidang URL. **Catatan**: Jika Anda menyetel pengalihan pihak ketiga dan URL yang berbeda, pengalihan default adalah ke app store pihak ketiga.
   * [Opsional] Aktifkan **Klip Aplikasi Tampilan untuk pengguna dengan Relay Pribadi** (tersedia di iOS 14+). <Anchor target="_blank" href="/marketers/id/docs/apple-app-clips-integration-guide">Pelajari lebih lanjut tentang Klip Aplikasi</Anchor> .
7. Lewati **Saat aplikasi diinstal** . Ini dibahas dalam [prosedur berikutnya](/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users) .
8. [Opsional] Ubah tujuan untuk **Saat tautan diklik di desktop.**  
   * Dalam beberapa kasus, tautan Anda mungkin diklik di komputer desktop, terutama jika itu dikirim melalui email atau media sosial. Jika Anda mengharapkan banyak lalu lintas desktop pada tautan Anda, Anda mungkin ingin mengirim para pengguna tersebut ke laman arahan atau beranda situs web utama, atau halaman di mana mereka dapat meminta tautan SMS di ponsel mereka, alih-alih app store terkait.
   * Secara default, pengguna desktop dialihkan ke laman App Store iOS aplikasi Anda, atau ke laman aplikasi Google Play, Jika aplikasi iOS tidak ditentukan.
9. [Opsional]**Pilih aplikasi dari platform lainnya**  
   Jika Anda memiliki versi aplikasi khusus untuk yang berikut:
   * **Windows phone**: Aktifkan tombol dan pilih aplikasi atau **Ubah ke URL yang berbeda** .
   * **iPad** : Aktifkan tombol dan pilih aplikasi iPad
   * **Amazon Kindle Fire**: Aktifkan tombol dan tambahkan Amazon store ASIN atau URL halaman aplikasi.
10. Klik **Save OneLink template** (Perbarui templat OneLink untuk templat yang diedit).   
    Templat OneLink Anda sekarang dibuat dan dapat digunakan untuk membuat banyak tautan berbeda yang dapat diklik (lihat <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">tautan dan pengalaman OneLink</Anchor> ).

</Accordion>

<div id="add-redirection-logic-for-existing-app-users" />

<Accordion title="Tambahkan logika pengarahan untuk pengguna aplikasi yang ada">

Pengguna aplikasi yang ada biasanya berharap untuk diarahkan langsung ke aplikasi, bukan ke toko aplikasi atau halaman web. Ada tiga teknologi yang tersedia untuk membuka aplikasi langsung setelahklik:

* **iOS Tautan Universal**: kompatibel dengan iOS 9 dan di atasnya, dan memberikan pengalaman menjelajah yang mulus dan aman saat membuka aplikasi Anda.
* **Tautan Aplikasi Android**: Kompatibel dengan Android 6 dan di atasnya, serta memberikan pengalaman menjelajah secara mulus dan aman saat membuka aplikasi Anda. **Catatan** : OS Samsung tidak dapat membuka aplikasi menggunakan Tautan Aplikasi Android.
* **Skema URI** :  
  * Metode fallback:
    * Android: Skema URI adalah metode fallback yang efektif ketika Tautan Aplikasi Android gagal membuka aplikasi baik karena tidak berfungsi atau tidak disiapkan
    * iOS: Kemampuan fallback terbatas ketika Tautan Universal gagal membuka aplikasi karena tidak berfungsi atau tidak disiapkan . <Anchor target="_blank" href="/marketers/id/docs/uri-scheme-fallback-for-ios">Pelajari lebih lanjut</Anchor>
  * Metode utama untuk membuka aplikasi di perangkat Samsung.
  * Adalah sebuah alamat yang jika diakses akan membuka aplikasi Anda jika aplikasi ini terinstal. Skema URI mirip dengan tautan situs web, tetapi membuka aplikasi bukan situs web.
  * Harus sama untuk iOS dan Android.

Untuk pengalaman pengguna, keamanan, dan jangkauan perangkat terbaik, kami merekomendasikan untuk mengaktifkan sebanyak mungkin teknologi.Jika Anda mengaktifkan semua teknologi tautan, OneLink secara otomatis akan menerapkan metode terbaik untuk setiap pengguna.

**Untuk menambahkan logika pengarahan untuk pengguna aplikasi yang ada ke templat OneLink Anda:**

1. Di dasbor AppsFlyer, buka **Pengalaman & deep linking** > **manajemen OneLink** .
2. Arahkan kursor ke templat OneLink yang ingin Anda edit, dan  klik ikon **Edit** .
3. Gulir ke bawan ke **When app is installed** (Saat aplikasi terinstal).

   [![](https://files.readme.io/c0e8e5364f0b184f33d72e33f28df131d5a8bb6c377dc74f0ec190bcc6e63e75-18363965490833.png)](https://files.readme.io/c0e8e5364f0b184f33d72e33f28df131d5a8bb6c377dc74f0ec190bcc6e63e75-18363965490833.png)
4. Ikuti instruksi untuk pengaturan iOS, Android, dan fallback:  

   <Tabs>
   <Tab title="Tautan iOS Universal">

   Tautan Universal menggunakan format tautan web reguler (mis. https://yourbrand.onelink.me atau https://www.yourbrand.com) dan kemudian memerlukan pengaturan subdomain (tercakup di [panduan sebelumnya](/docs/create-a-onelink-template#prosedur)). OneLink juga mendukung sepenuhnya <Anchor target="_blank" href="/marketers/id/docs/brand-onelink-with-your-domain">domain bermerek</Anchor>, tetapi tidak perlu untuk menyelesaikan panduan ini.

   **Untuk meluncurkan aplikasi menggunakan Tautan Universal**:

   1. Hubungi pengembang iOS Anda:
      * Beri mereka subdomain untuk templat OneLink ini.
      * Beri tahu mereka untuk mengikuti <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">instruksi ini</Anchor>.
      * Pengembang kembali kepada Anda dengan ID Tim (juga disebut Awalan ID Aplikasi Apple, misalnya, PF23MIWNTW).
      * Jika aplikasi belum dipublikasikan, pengembang juga harus memberi Anda Pengenal Aplikasi (Bundle Identifier) (misalnya, com.myapp.something).

        [![](https://files.readme.io/c469a6c99515b0d76d075b0036ea118af16cd11b2ef134a63499acf0467895a0-18363965493521.png)](https://files.readme.io/c469a6c99515b0d76d075b0036ea118af16cd11b2ef134a63499acf0467895a0-18363965493521.png)
   2. Di laman templat OneLink, klik **Change to launch the app using Universal Links** (Ubah untuk membuka aplikasi menggunakan Tautan Universal).
   3. Di jendela baru, pilih **Luncurkan aplikasi menggunakan Tautan Universal**.
   4. Di bidang **Team ID**, masukkan ID tim yang disediakan oleh pengembang Anda.
   5. Jika aplikasi belum dipublikasikan, masukkan juga **Bundle Identifier**.
   6. Klik **Save changes** (Simpan perubahan).

   </Tab>

   <Tab title="Tautan Aplikasi Android">

   Tautan Aplikasi menggunakan format tautan web reguler (mis. https://yourbrand.onelink.me or https://www.yourbrand.com) dan kemudian memerlukan pengaturan subdomain (tercakup pada [panduan sebelumnya](/docs/create-a-onelink-template#prosedur)). OneLink juga mendukung sepenuhnya <Anchor target="_blank" href="/marketers/id/docs/brand-onelink-with-your-domain">domain bermerek</Anchor>, tetapi tidak perlu untuk menyelesaikan panduan ini.

   Sebelum Anda mulai:

   Catat subdomain yang Anda pilih untuk templat OneLink ini.

   **Untuk membuka aplikasi menggunakan Tautan Aplikasi Android**:

   1. Hubungi pengembang Android Anda:   
       Bari tahu mereka untuk membuat SHA256 fingerprint dengan mengikuti <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#generating-a-sha256-fingerprint">instruksi ini</Anchor>.  
       Pengembang akan kembali ke Anda dengan SHA256 fingerprint. Misalnya: `DC:65:43:67:F3:BD:02:52:AC:B4:50:F1:74:54:23:49:4D:49:6C:E6:DF:56:BD:CB:53:06:11:5B:C9:4E:5D:0C`
   2. Di laman templat OneLink, klik **Change to launch the app using App Links** (Ubah untuk membuka aplikasi menggunakan Tautan Aplikasi).
   3. Di jendela baru, pilih **Luncurkan aplikasi menggunakan Tautan Aplikasi**.
   4. Di bidang **SHA256 fingerprint**, masukkan SHA256 fingerprint yang disediakan oleh pengembang.  
      Muncul kode intent-filter yang dibuat secara otomatis.
   5. Hubungi pengembang Android Anda:   
       Beri mereka kode intent-filter yang dibuat secara otomatis.  
      Beri tahu mereka untuk mengikuti <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#adding-app-link-intent-filter-to-main-activity">instruksi in</Anchor> dan konfirmasi penyelesaian.

   </Tab>

   <Tab title="Skema URI">

   Skema URI berfungsi utama sebagai fallback untuk pengguna iOS dan Android, dan oleh karenanya harus sama untuk keduanya.

   **Untuk mengatur fallback URI Android dan iOS:**

   1. Hubungi pengembang iOS DAN Android Anda dan tentukan skema URI-nya. Misalnya: `feedmeapp://`  

      <div id="h_01H9Q4E7VR4CAK0PJY269GQ9XJ" />

      <div id="tip" />

      > 👍 **Tips**
      >
      > * Baik Apple maupun Google tidak memberlakukan penamaan unik untuk skema aplikasi. **Pilih nama skema yang unik untuk merek Anda** untuk menghindari skema yang saling bertentangan di berbagai aplikasi. Nama skema yang baik dapat berupa ID bundel aplikasi Anda,   misalnya,**com.company.app**
      > * Untuk mengaktifkan OneLink untuk melayani iOS dan Android, **skema yang sama harus ditentukan  untuk kedua platform**. Berikut adalah petunjuk  untuk <Anchor target="_blank" href="https://help.contrast.co/hc/id/articles/200865293-URL-Scheme-Intro-for-App-Developers">iOS</Anchor> dan <Anchor target="_blank" href="https://developer.android.com/training/app-links/deep-linking.html">Android</Anchor>.
      > * Skema URI tidak dapat dimulai dengan http atau https.

   2. Beri tahu pengembang iOS untuk menerapkan skema URI dalam aplikasi mereka dengan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-uri-scheme">mengikuti instruksi ini</Anchor>.  
       **DAN**Beri tahu pengembang Android untuk menerapkan skema URI dalam aplikasi mereka dengan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#procedures-for-uri-scheme">mengikuti instruksi ini</Anchor>.
   3. Setelah selesai, pengembang mengonfirmasi nilai skema URI yang diterapkan. Dapat tampak seperti: `exampleapp://` or `exampleapp://home` or `exampleapp://main`, dll.
   4. Di laman templat OneLink, klik **Add URI scheme to launch the app** (Tambah skema URI untuk membuka aplikasi).
   5. Pilih **Launch the app using URI scheme** (Buka aplikasi menggunakan skema URI).
   6. Masukkan nilai skema URI.
   7. Klik **Save changes** (Simpan perubahan).
   8. Uji skema URI (ini dapat dilakukan oleh Anda ATAU pengembang Anda):
      1. Buka <Anchor target="_blank" href="https://halgatewood.com/deeplink/">alat pengujian publik gratis ini</Anchor> pada perangkat iOS dan Android yang memiliki penginstalan aplikasi Anda.
      2. Ketuk tautan yang dibuat oleh alat.  
          Jika skema URI-nya benar, aplikasi terbuka.

   </Tab>
   </Tabs>

5. Klik **Update OneLink template** (Perbarui templat OneLink).

<div id="h_favicon" />

<div id="note-2" />

<div id="note-1" />

> 📘 **Catatan**
>
> * Saat Anda menyimpan atau memperbarui templat OneLink, AppsFlyer secara otomatis menghasilkan file AASA dan/atau Tautan Aset Digital JSON untuk memverifikasi domain aplikasi Anda dan mengelolanya untuk Anda. Ini sangat penting agar Tautan Universal dan Tautan Aplikasi Anda dapat berfungsi dengan baik.
> * Diperlukan waktu hingga 1 jam agar pembaruan templat OneLink diterapkan.

</Accordion>

<div id="customize-qr-codes" />

<Accordion title="Sesuaikan kode QR">

![OnelinkQRFinal__1_.gif](https://files.readme.io/6eb996db8c8bcdb8ac46380151fc54c8ef5b686999aaaef3d1a951d627eadc70-11902870808081.gif)

Anda dapat menyesuaikan kode QR yang dibuat melalui OneLink dengan:

* Menambahkan logo Anda ke kode QR
* Mengubah warna kode QR.

**Catatan**: Penyesuaian kode QR dilakukan pada tingkat templat, bukan pada tingkat tautan individu. Oleh karena itu, penyesuaian memengaruhi semua kode QR berdasarkan templat yang diedit.

**Untuk menyesuaikan kode QR Anda**:

1. Di dashboard AppsFlyer, buka  **Experiences & deep linking** > **OneLink Custom Links**.
2. Arahkan kursor ke ikon **Actions (Tindakan)** dari templat yang ingin Anda edit dan klik **Sesuaikan kode QR**.  
   Editor kode QR dibuka.
3. Enter the URL where your logo is hosted. For example: https://yourbrand.com/logo.png.  

   Persyaratan logo:

   * Format PNG atau JPG
   * Kotak atau lingkaran dengan latar belakang transparan
   * Dimensi minimum 400 x 400 px
   * Untuk pencetakan, gunakan resolusi gambar maksimum
4. Atur warna kode QR.
5. Klik **Save**.

</Accordion>

<div id="key-traits-and-limitations" />

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Sifat | Catatan |
| --- | --- |
| Agensi | <ul><li>Agensi tidak dapat membuat templat OneLink sendiri.</li><li>Agensi dapat menggunakan template OneLink yang ada untuk membuat tautan atribusi khusus untuk mereka sendiri **jika agensi adalah mitra dari semua aplikasi dalam templat** .</li></ul> |
| Menambahkan/mengedit templat OneLink | Pengguna akun memerlukan  <Anchor target="_blank" href="/marketers/id/docs/user-management">izin</Anchor> untuk menambahkan dan mengedit template OneLink. |
| Templat OneLink | Hingga 600 templat OneLink per akun. |
| Desktop | Saat Anda menyetel URL atau templat OneLink untuk mengarahkan pengguna desktop ke URL yang berbeda, URL web ditambahkan ke tautan di parameter `af_web_dp` . Saat tautan berisi  `af_web_dp` , AppsFlyer tidak mendaftarkan klik jika ini berasal dari desktop. |
| Arahkan ke toko aplikasi pihak ketiga | Beberapa toko aplikasi dapat diatur pada template OneLink hanya jika nama paket aplikasi sama untuk semua toko aplikasi.<br /><br />**Catatan**:<ul><li>Huawei menggunakan nama paket yang berbeda, sehingga template OneLink yang sama tidak dapat digunakan untuk beberapa toko aplikasi.</li><li>Jika nama paketnya sama, tetapi salurannya berbeda, pengalihan berfungsi, tetapi atribusi tidak.</li><li><Anchor target="_blank" href="/marketers/id/docs/set-up-multi-store-android-attribution">Pelajari lebih lanjut</Anchor> tentang atribusi dan data toko aplikasi pihak ketiga.</li></ul> |
| Memperbarui templat | Perubahan pada konfigurasi templat OneLink membutuhkan waktu hingga 1 jam untuk diterapkan. |

</Accordion>

Punya pertanyaan tentang templat OneLink? Lihat <Anchor target="_blank" href="/marketers/id/docs/onelink-troubleshooting-and-faq#pertanyaan-umum-templat-onelink">Pertanyaan Umum (FAQ)</Anchor> kami!

<div id="next-step" />

## Langkah berikutnya

Ikuti instruksi untuk <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">membuat tautan OneLink</Anchor> berdasarkan templat Anda.

<div data-zendesk-anchors="onelink-templates=templat-onelink h_01H9Q4E7VQ0GKZ9HFF88190TYN=templat-onelink procedures=prosedur h_01H9Q4E7VQYGZ1MH5SS3ZYZF1K=prosedur h_01H9Q4E7VQ648CQ1VJTB1TC571=create-a-onelink-template-with-redirection-logic-for-new-app-users h_01H9Q4E7VQ15AAR1VXNKWR1XGT=catatan h_01H9Q4E7VQ4NEWYAD6AMR9YKGY=add-redirection-logic-for-existing-app-users h_01H9Q4E7VR8164HR6MD0EAV2SN=catatan-1 h_01H9Q4E7VR0F4B7CTF08YTG715=customize-qr-codes h_01H9Q4E7VR2B50EQE31DDG8GNZ=traits-and-limitations next-step=langkah-berikutnya h_01H9Q4E7VRJK31P9CSGJFCKQQF=langkah-berikutnya" />
