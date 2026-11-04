---
title: Tautan dan pengalaman OneLink
metadata:
  keywords:
    - Marketers
    - onelink
    - Text-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Text-to-App
  created_at: '2016-05-22T10:03:37Z'
  edited_at: '2023-11-24T13:19:26Z'
  id: 208874366
  locale: id
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/id/articles/208874366
---
> **Sekilas:** [Buat tautan OneLink](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#buat-tautan-onelink) yang memberi pengguna pengalaman yang Anda inginkan. Pengguna yang mengklik tautan akan diarahkan ke toko aplikasi, URL web, atau ke aplikasi yang benar sesuai kebutuhan. Dan pengguna diatribusikan ke sumber media yang benar.

<div id="onelink-links-and-experiences" />

## Tautan dan pengalaman OneLink

<Embed title="Pemutar video YouTube" typeOfEmbed="youtube" url="https://www.youtube.com/embed/KZBrxGEjVUE" providerUrl="https://www.youtube.com" />

Pelanggan Anda berinteraksi dengan merek Anda di banyak titik kontak online dan offline yang berbeda. Dari mana pun pengguna Anda berasal, Anda dapat membuat tautan yang memberikan pengalaman sempurna bagi mereka, mulai dari klik, hingga penginstalan aplikasi, hingga deep linking dan deferred deep linking.

Langkah-langkah yang diperlukan untuk menyiapkan tautan dijelaskan secara rinci di bagian berikut, tetapi pada dasarnya, langkah-langkah tersebut mencakup hal-hal berikut:

* Memilih pengalaman pengguna
* Pengaturan Umum
* Pengaturan khusus pengalaman
* Deep linking dan pengaturan pengarahan
* Pengaturan parameter tambahan

<div id="create-a-onelink-link" />

## Buat tautan OneLink

| **Siapa saja yang terlibat**<ul><li>Hanya pemasar yang diharuskan membuat tautan OneLink dengan pengalaman yang mengarahkan pengguna ke toko aplikasi, URL web, atau, setelah template disiapkan untuk membuka aplikasi dengan Tautan Aplikasi Android dan Tautan Universal iOS, ke laman beranda aplikasi .</li><li>Untuk menambahkan fungsi deep linking dan deferred deep linking ke tautan, diperlukan pemasar dan pengembang Android/iOS.</li></ul> |
| --- |
| **Prasyarat**<ul><li>Akun AppsFlyer dengan setidaknya satu aplikasi.</li><li><Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template">Templat OneLink</Anchor> yang menjadi dasar tautan Anda.</li><li>Untuk atribusi: <Anchor target="_blank" href="/marketers/id/docs/integrate-the-appsflyer-sdk">SDK AppsFlyer sudah terinstal</Anchor> di setiap aplikasi seluler Anda.<ul><li>Jika SDK belum diinstal di aplikasi Anda, masih dimungkinkan untuk membuat tautan pengarahan yang berjalan, tetapi hal itu tidak akan mungkin untuk mengukur instalasi di dashboard Anda, penautan langsung (deep link), atau penautan langsung tertunda (deferred deep link).</li></ul></li></ul> |
| **Waktu yang dibutuhkan**<br /><br />30 menit untuk sebagian besar tautan, tetapi sekitar 3 jam untuk tautan yang memerlukan deep linking atau fungsi deferred deep linking. |
| **Hasil**<ul><li>Tautan yang mengarahkan pengguna ke toko aplikasi, halaman web, atau aplikasi yang benar berdasarkan perangkat mereka, dan memberi mereka pengalaman yang Anda inginkan.</li></ul> |

**Untuk membuat tautan OneLink dengan pengalaman pengguna tertentu:**

1. Di dasbor AppsFlyer, buka **Experiences & deep linking** > **OneLink management.**
2. Pilih **OneLink template** untuk menambahkan tautan personalisasi untuk.
3. Klik **Add link** .
4. Pilih [pengalamanyang](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#experiences) ingin Anda buat untuk pengguna Anda.
5. Pilih sumber media atau masukkan sumber media khusus. Ini adalah sumber media tempat data ditampilkan di AppsFlyer. Sumber media disertakan dalam tautan Anda sebagai nilai parameter `pid`.
6. Klik **Berikutnya**.
7. Selesaikan [**Pengaturan umum**](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings).
8. Klik **Berikutnya**.
9. [Opsional] Selesaikan prosedur yang relevan dengan pengalaman pengguna yang Anda buat: 

| Pengalaman | Pilihan prosedur |
| --- | --- |
| <ul><li>Sosial-ke-aplikasi</li><li>Teks-ke-aplikasi</li><li>Referral ke aplikasi</li><li>Tautan khusus</li></ul> | <ul><li>[Pratinjau media sosial](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags)</li><li>[Laman awal aplikasi sosial](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page)</li></ul> |
| Email-ke-aplikasi | Jika Anda menggunakan ESP, ikuti <Anchor target="_blank" href="/marketers/id/docs/email-service-provider-esp-integration-guide">petunjuk integrasi ESP</Anchor>. |
| Aplikasi-ke-aplikasi | Anda dapat membuat tautan dinamis yang berfungsi di beberapa aplikasi melalui <Anchor target="_blank" href="/marketers/id/docs/cross-promotion-attribution-for-marketers">promosi silang</Anchor>. |
| Referral-ke-aplikasi | <ul><li>[Pratinjau media sosial](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags)</li><li>[Laman awal aplikasi sosial](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page)</li><li>Anda dapat membuat tautan rujukan-ke-aplikasi secara dinamis melalui SDK di aplikasi Anda melalui <Anchor target="_blank" href="/marketers/id/docs/user-invite-attribution">integrasi undangan pengguna</Anchor>.</li></ul> |

10. Klik **Berikutnya**.
11. [Opsional] Di **Deep linking dan pengarahan**, selesaikan [penyiapan deep linking/deferred deep linking](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking). Lewati bagian ini jika tautan ini tidak dimaksudkan untuk deep linking.
12. [Opsional] Di  **Deep linking dan pengarahan**, ubah pengaturan pengarahan. Lewati bagian ini jika pengaturan pengarahan dari templat OneLink sudah benar.
13. Klik **Berikutnya**.
14. Di **Parameter tambahan**, [tambahkan parameter yang ditentukan sebelumnya atau parameter khusus](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#additional-parameters) ke tautan Anda untuk analisis yang lebih terperinci. <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters">Pelajari lebih lanjut tentang parameter atribusi</Anchor>
15. Klik **Buat tautan**.

<div id="experiences" />

<Accordion title="Pengalaman">

Anda dapat membuat tautan untuk pengalaman pengguna berikut:

* **Sosial-ke-aplikasi**: Libatkan pengguna Anda di media sosial dan kirim mereka dari postingan media sosial ke aplikasi Anda.
* **Aplikasi-ke-aplikasi** : Mengirim pengguna ke aplikasi Anda melalui iklan yang mereka lihat di aplikasi lain.
* **QR-to-app**: Gunakan kode QR untuk mendorong pemasangan aplikasi dengan meminta pengguna memindai kode QR pada poin-poin penting selama pengalaman pelanggan offline mereka. Anda juga dapat menempatkan kode QR di situs desktop, atau di iklan TV dan CTV untuk mengarahkan pengguna ke aplikasi Anda.
* **Email-ke-aplikasi** : Gunakan penyedia layanan email (ESP) untuk melibatkan pengguna melalui email dan mengirim mereka dari kotak masuk mereka ke aplikasi Anda.
* **Teks-ke-aplikasi**: Buat  tautan untuk SMS dan kampanye perpesanan Anda dan libatkan pengguna melalui pesan teks.
* **Referral-ke-aplikasi**: Buat tautan undangan pengguna yang memungkinkan pengguna atau pemberi pengaruh mengundang orang lain ke aplikasi Anda atau berbagi konten in-app tertentu, misalnya, sebuah artikel.
* **Tautan khusus**: Untuk perjalanan pengguna yang tidak sesuai dengan salah satu pengalaman yang disebutkan di atas, Anda dapat membuat tautan khusus OneLink. Kemudian, dari mana pun pengguna Anda berasal, baik melalui desktop atau seluler, online atau offline, media milik atau berbayar, Anda dapat dengan mudah mengirim mereka ke tempat yang tepat.

</Accordion>

<div id="general-settings" />

<Accordion title="Pengaturan Umum">

Pengaturan umum adalah bagian dari proses pembuatan tautan OneLink yang berlaku untuk semua pengalaman.

**Untuk menyelesaikan pengaturan umum** :

1. [Opsional] Ubah nama sumber media.
2. [Opsional] Ubah nama kampanye.
3. [Opsional] Aktifkan **Penargetan Ulang** jika Anda berencana menggunakan tautan ini untuk menargetkan pengguna yang ada.  

   Ini memungkinkan Anda untuk melihat interaksi ulang yang dilakukan oleh pengguna yang mengklik tautan kustom Anda.

   Pengguna saat ini yang mengklik tautan non-penargetan ulang (UA) juga membuka aplikasi, dan memiliki pengalaman pengguna yang sama. Namun, interaksi ulang mereka direkam sebagai sesi reguler, yang artinya tidak dapat mengukur keberhasilan kampanye media yang dimiliki.

   **Penting**! Agar penargetan ulang berfungsi, Anda juga perlu mengaktifkan penargetan ulang untuk aplikasi.
4. [Opsional] Aktifkan **Abaikan pengguna aktif untuk penargetan ulang** dan pilih jendela tidak aktif.  
   Ini menambahkan parameter af\_inactivity\_window=[jumlah hari] ke tautan Anda, dan semua pengguna yang aktif selama periode tersebut diabaikan untuk penargetan ulang.
5. Atur jendela interaksi ulang untuk menentukan jangka waktu setelah interaksi ulang, di mana in-app event pengguna diatribusikan ke sumber media penargetan ulang.

   * Anda dapat mengatur nilai dalam satuan hari (1-90), jam (hingga 23), atau bahkan selamanya.
   * Jendela interaksi ulang ditambahkan ke tautan di parameter af\_reengagement\_window.
6. [Opsional] Pada subbagian **Tautan merek** :
   * Pilih domain yang berbeda untuk mencerminkan merek Anda. <Anchor target="_blank" href="/marketers/id/docs/brand-onelink-with-your-domain">Pelajari lebih lanjut</Anchor>
   * Edit ID URL untuk menyoroti penawaran kampanye. Maksimal karakter ID URL adalah 50 karakter dan dapat berupa kombinasi huruf dan angka. Secara default, ini adalah 8 karakter.

<div id="enable-retargeting-for-the-app" />

#### Aktifkan penargetan ulang untuk aplikasi

Jika Penargetan Ulang tidak pernah diaktifkan untuk aplikasi, Anda perlu melakukannya sekali. <Anchor target="_blank" href="/marketers/id/docs/app-settings#pengaturan-atribusi">Pelajari lebih lanjut</Anchor>

**Untuk mengatur Penargetan ulang pada level aplikasi:**

1. Di dasbor AppsFlyer, buka **Configuration** > **App Settings**.
2. Di bagian**Atribusi**, aktifkan **Atribusi interaksi ulang**.
3. Klik **Save settings** .

</Accordion>

<div id="social-media-preview-og-tags" />

<Accordion title="Pratinjau media sosial - tag OG">

Saat tautan dibagikan, tag grafik terbuka (open graph/OG) digunakan untuk membuat pratinjau dengan judul, deskripsi, dan gambar.

Tag OG ini dapat secara otomatis diambil dari URL web atau app store yang diarahkan. Namun, terkadang metode pembuatan pratinjau ini gagal. Oleh karena itu, kami menyarankan agar Anda mengatur pratinjau media sosial di OneLink, baik menggunakan UI OneLink, atau, untuk tautan yang tidak dibuat di UI OneLink, dengan menambahkan paramter tag OG ke tautan Anda.

Fitur pratinjau media sosial didukung oleh platform berikut:

* Facebook: postingan dan DM
* X (sebelumnya Twitter): postingan dan DM
* iMessage
* WhatsApp
* LinkedIn: postingan dan DM
* Line
* Telegram
* Slack
* Signal
* KakaoTalk
* Discord
* Reddit

**Untuk membuat pratinjau media sosial Anda di UI OneLink:**

1. Di editor tautan kustom OneLink Anda, buka bagian **Bagikan di media sosial**.
2. Di bagian **Pratinjau media sosial**  , masukkan:
   * Judul
   * Deskripsi
   * URL gambar

**Untuk menambahkan parameter tag OG ke tautan Anda–** (jika tidak dibuat di OneLink UI):

* Tambahkan parameter yang diwajibkan berikut ini:
  * af\_og\_title (hingga 40 karakter)
  * af\_og\_description (hingga 300 karakter)
  * af\_og\_image

**Catatan:** 

* Anda dapat menambahkan parameter tag OG ke tautan Anda di luar UI AppsFlyer.
* Jika Anda menambahkan tag OG terpisah untuk X (sebelumnya Twitter), tag tersebut akan menggantikan pratinjau AppsFlyer yang biasa.

</Accordion>

<div id="social-app-landing-page" />

<Accordion title="Laman awal aplikasi sosial">

<div id="important-1" />

> 🚧 **Penting!**
>
> Tautan Universal iOS kini didukung di Meta ads.
>
> * Karena Meta sekarang <Anchor target="_blank" href="/marketers/id/docs/meta-ads-faq#are-ios-universal-links-and-android-app-links-supported-in-meta-ads">mendukung tautan universal</Anchor>, halaman arahan aplikasi sosial tidak lagi diperlukan lagi untuk iklan berbayar Meta yang mendukung tautan universal.
> * Halaman arahan aplikasi sosial diperlukan untuk postingan yang dimiliki (iklan tidak berbayar).

Aplikasi media sosial dapat mengganggu kelancaran pengalaman pengguna yang sudah ada menggunakan Tautan Universal. Hal ini dapat diatasi dengan:

* [**Disarankan**] Membuat laman arahan aplikasi media sosial.  
  Saat membuat laman arahan aplikasi media sosial, sebaiknya pastikan Anda telah mengonfigurasi skema URI.
* [Alternatif] <Anchor target="_blank" href="/marketers/id/docs/onelink-troubleshooting-and-faq#penautan-langsung-yang-dipaksakan">Memaksa buka aplikasi</Anchor> menggunakan parameter `af_force_deeplink=true`.  
  **Catatan**: Parameter ini diaktifkan secara otomatis untuk Kakaotalk, Naver, Naver-Blog, Chrome, Weibo, dan X (sebelumnya Twitter).

Dengan laman arahan aplikasi media sosial, pengguna yang mengklik iklan di aplikasi media sosial diarahkan ke laman arahan yang dibuat AppsFlyer. Dari sana, pengguna dapat ditautkan langsung (deep linked), atau lanjut menginstal aplikasi.

AppsFlyer menyediakan berbagai templat laman arahan aplikasi media sosial. Posisi elemen dalam tempat itu tetap, tetapi elemennya sendiri dapat disesuaikan, termasuk gambar latar belakang atau warna, judul, teks, gambar, tombol, tag, dan yang lainnya.

Laman arahan aplikasi media sosial dapat digunakan dengan aplikasi media sosial berikut:

* Instagram
* Facebook/Facebook Messenger (**Catatan**: Untuk Facebook dan Facebook Messenger, jika skema URI dan halaman arahan aplikasi Media Sosial telah diatur, halaman arahan aplikasi Sosial tidak akan ditampilkan.)
* LinkedIn
* Pinterest for iOS
* Snapchat
* X (sebelumnya Twitter)
* WeChat

**Pengalaman pengguna**

Saat pengguna berinteraksi dengan tombol CTA di laman arahan:

* **Jika aplikasi terinstal**: pengguna yang mengklik membuka aplikasi.
* **Jika aplikasi TIDAK terinstal**: pengguna diarahkan ke app store yang relevan. Setelah menginstal, pengguna dapat menunda deep linking (dijelaskan di [deep linking dan deferred deep linking](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking)).

<div id="note-2" />

> 📘 **Catatan**
>
> Laman arahan aplikasi media sosial hanya mendukung URL pendek OneLink.

<div id="to-use-the-social-app-landing-page" />

#### **Untuk menggunakan laman arahan aplikasi media sosial:**

1. Konfigurasikan laman arahan seperti dijelaskan pada sesi berikut.
2. Catat URL yang dihasilkan URL singkat  OneLink.   
   Laman arahan aplikasi media sosial tidak berfungsi dengan URL OneLink yang panjang.
3. Posting URL pendek OneLink di aplikasi sosial.

Atribusi ditentukan berdasarkan pada pengaturan atribusi Anda.

<div id="to-set-up-the-social-apps-landing-page" />

#### **Untuk mengatur laman arahan aplikasi Sosial:**

1. Di penyiapan tautan Kustom Anda, buka bagianBagikan di media sosial.
2. Di bagian **Laman awal aplikasi Sosial** , klik **Buat laman awal**.  
   Jendela untuk memilih templat laman awal terbuka.  

   [![](https://files.readme.io/82a65bf446c4e6ae8803eaf048cc95ebe9c312f574fb8eda2764c123f0a50ee6-30151216576657.jpg)](https://files.readme.io/82a65bf446c4e6ae8803eaf048cc95ebe9c312f574fb8eda2764c123f0a50ee6-30151216576657.jpg)
3. Untuk memilih templat laman arahan, arahkan kursor ke templat yang dipilih dan klik **Create**.  

   **Tips**: Arahkan kursor ke ikon templat 🛈 untuk melihat kasus mana yang harus digunakan. Clustered Poster dan ShowAndTell direkomendasikan untuk Instagram.
4. Sesuaikan semua elemen di pembuatan laman arahan. Untuk melakukannya, pilih elemen berdasarkan nama atau klik elemen di gambar sebelumnya.    
    **Tips**: Simpan teks Anda untuk berjaga-jaga jika Anda mengganti templat pembuatan.
5. Ganti semua gambar templat dengan gambar Anda sendiri.  
   1. Enter image URLs including the extension, for example, `https://example.com/image.png`.
   2. Gunakan salah satu jenis file berikut: jpeg, jpg, png.   
      **Catatan**: format webp tidak didukung.
   3. Rekomendasi untuk gambar adalah:  

| Jenis gambar templat | Ukuran file gambar maksimum | Rasio gambar |
| --- | --- | --- |
| Pengumpulan | 300 KB | 16:9 (horizontal) |
| <ul><li>Trapeze</li><li>Carousel</li><li>ShowAndTell</li></ul> | 300 KB | 1:1 |
| <ul><li>Flyer</li><li>Poster</li><li>Blurry poster</li><li>Clustered poster</li></ul> | 300 KB | 9:16 (vertikal) |

   4. Jika salah satu gambar atau lebih bukan URL yang tepat, akan muncul kesalahan, dan Anda tidak akan dapat melihat pembuatan.  

      [![](https://files.readme.io/63223efc74994143111d5a5ef6b2d5fa7b84ac4f1033f8713d96cc293ba47588-30151216583697.png)](https://files.readme.io/63223efc74994143111d5a5ef6b2d5fa7b84ac4f1033f8713d96cc293ba47588-30151216583697.png)
6. Untuk melihat pembuatan laman awal, klik **Review (Lihat)**.  
   Jika diperlukan perubahan, klik **Back to editor (Kembali ke editor)**.  

   [![](https://files.readme.io/90b52321a6f7061a77624ec4486d6e2628c38c49ea0de734cf1c1fd0bc888cee-30151216593169.png)](https://files.readme.io/90b52321a6f7061a77624ec4486d6e2628c38c49ea0de734cf1c1fd0bc888cee-30151216593169.png)
7. Untuk menyimpan laman arahan, klik **Done (Selesai)**.  
   **Penting**: Materi iklan laman baru/yang diperbarui hanya berlaku setelah membuat/memperbarui tautan kustom.
8. [Opsional] Untuk mengedit laman awal Anda, klik **Edit social app landing page**.

</Accordion>

<div id="deep-linking-and-deferred-deep-linking" />

<Accordion title="Deep linking dan deferred deep linking">

Deep linking berarti Anda menargetkan ulang pengguna aplikasi yang ada dan mengirim mereka langsung ke pengalaman tertentu (misalnya, halaman tertentu) dalam aplikasi Anda, tanpa diarahkan ke toko aplikasi atau halaman beranda aplikasi terlebih dahulu. Pengguna ini diatribusikan menggunakan atribusi penargetan ulang.

Deferred deep linking berarti Anda memberikan pengalaman deep linking serupa kepada pengguna baru seperti pengguna yang sudah ada. Tetapi alur pengguna mereka adalah pertama, pengguna baru dikirim ke toko aplikasi, dan setelah mereka mengunduh dan meluncurkan aplikasi, mereka dikirim ke pengalaman atau halaman tertentu.

**Catatan**: Mengatur deep linking dan deferred deep linking memerlukan pengembang Android dan iOS Anda.

**Untuk menyiapkan deep linking dan deferred deep linking untuk mengarahkan pengguna ke pengalaman tertentu di aplikasi:**

1. Hubungi pengembang iOS dan Android Anda untuk merencanakan pengaturan **deep\_link\_value**di tautan Anda.
   * **Deep\_link\_value** adalah nama nilai untuk konten dalam aplikasi tertentu yang akan diarahkan oleh pengguna. Pengembang menerapkan perilaku yang diinginkan dari **deep\_link\_value** dalam kode.
   * Pengembang menerapkan perilaku yang dipilih dalam kode. Bagikan panduan ini agar pengembang memahami alur teknis dan lihat contohnya:
     * Untuk [penautan langsung DAN penautan langsung yang ditangguhkan](https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl) pengguna baru atau yang sudah ada, dengan atau tanpa aplikasi Anda. **Pertimbangan untuk UDL:** 
       * Memerlukan SDK V6.1 atau yang lebih baru.
       * Maksimum klik lookback window adalah 15 menit.
     * **Catatan**: Pelanggan yang sudah menggunakan OneLink untuk deep linking mungkin menggunakan metode lama untuk <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_gcd_legacy">Android</Anchor> dan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_gcd_legacy">iOS</Anchor>, bukan UDL.  

       > 👍 **Tips**
       >
       > **deep\_link\_value** dapat didasarkan pada SKU produk, ID postingan media sosial, jalur URL, atau nilai lainnya.
       >
       > Penting untuk bekerja sama dengan pembuat program Anda untuk menghasilkan sistem jangka panjang terbaik untuk **deep\_link\_value** dan parameter atau nilai lainnya. Ini akan meminimalkan tambahan pembaruan aplikasi. Sampaikankepada pembuat program Anda tentang penggunaan nilai dinamis, untuk menghasilkan berbagai tautan langsung yang mengarah ke berbagai konten dalam aplikasi, **tanpa perlu mengubah kode aplikasi setiap saat.** 
       >
       > Misalnya,**deep\_link\_value** dari jenis buah dipilih dan pembuat program membuat nilainya dinamis. Ini berarti Anda dapat memasukkan buah apa pun tanpa membutuhkan kerja lebih lanjut dari tim pembuat program Anda. 
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month&deep_link_value=apples...`
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month&deep_link_value=bananas...`
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month&deep_link_value=peaches...`

2. Setelah menerima konfirmasi dari pengembang bahwa aplikasi berperilaku sesuai dengan parameter dan nilai yang dipilih, di bagian **Deep linking dan pengalihan** halaman pengaturan tautan,masukkan nilai  **Deep link**sesuai dengan apa yang Anda putuskan dengan pengembang.
3. [Opsional]  Jika deep linking Anda memerlukan lebih dari satu pengalaman dalam aplikasi (misalnya, Anda ingin mengarahkan pengguna ke suatu produk, dan secara terpisah menawarkan diskon kepada mereka), Anda dapat menambahkan  **nilai deep link tambahan** (dengan parameter deep\_link\_sub1) ke muatan data deep linking. Anda dapat menambahkan parameter deep link lebih lanjut (deep\_link\_sub2-10) di bagian **Parameter tambahan**.
   1. Hubungi pengembang iOS dan Android Anda untuk merencanakan nilainya.
   2. Pengembang menerapkan perilaku yang dipilih dalam kode. Bagikan panduan OneLink dengan pengembang Anda untuk memahami alur teknis dan melihat contoh.

      <Tabs>
      <Tab title="Android">

      [Instruksi pengembang di OneLink](https://dev.appsflyer.com/hc/docs/dl_android_overview)

      </Tab>

      <Tab title="iOS">

      [Instruksi pengembang di OneLink](https://dev.appsflyer.com/hc/docs/dl_ios_overview)

      </Tab>

      <Tab title="Unity">

      [Instruksi pengembang di OneLink](https://dev.appsflyer.com/hc/docs/deeplinkintegrate)

      </Tab>
      </Tabs>

   3. Di bagian**Parameter tambahan**, tambahkan parameter khusus **deep\_link\_sub2-10** dan nilai yang diperlukan, sesuai dengan apa yang Anda putuskan dengan pengembang.

<div id="note-4" />

> 📘 **Catatan**
>
> Setelah parameter dan nilai dinamis diterapkan oleh pengembang, pemasar dapat menggunakan OneLink API untuk secara otomatis menghasilkan ribuan tautan kustom. <Anchor target="_blank" href="/marketers/id/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">Pelajari lebih lanjut</Anchor>

</Accordion>

<div id="redirection" />

<Accordion title="Pengarahan">

**Untuk mengarahkan pengguna baru ke** **laman awal, bukan ke toko aplikasi** :

1. Di bagian **Deep linking dan pengalihan** di halaman penyiapan tautan, di bawah Saat aplikasi tidak terinstal, pilih untuk mengirim pengguna ke URL yang berbeda.  
   URL Android dan iOS khusus mengarahkan pengguna baru ke laman landas yang Anda tentukan.   
   **Perhatikan!** Jika templat OneLink Anda sudah memiliki nilai yang ditetapkan untuk URL khusus, URL tautan khusus ini akan menimpanya.
2. Anda juga dapat mengirim pengguna baru ke <Anchor target="_blank" href="/marketers/id/docs/redirect-users-to-custom-app-store-product-pages">halaman produk toko kustom</Anchor>.

</Accordion>

<div id="additional-parameters" />

<Accordion title="Parameter tambahan">

Anda mungkin ingin menambahkan parameter tambahan ke tautan, seperti nama Ad set, nama Iklan, Saluran, parameter kustom Anda sendiri, atau 1-5 <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">parameter pelanggan</Anchor>. Ini memungkinkan analisis yang lebih terperinci terkait upaya pemasaran Anda. Baca lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters">parameter atribusi tambahan</Anchor>.

Anda juga dapat menambahkan parameter deep linking tambahan (deep\_link\_sub2-10).

**Untuk menambahkan parameter**:

1. Di bagian **Parameter tambahan** pada penyiapan tautan, klik **Add parameter** .
2. Pilih parameter untuk menambahkan atau memasukkan parameter khusus.

</Accordion>

<div id="testing" />

<Accordion title="Pengujian">

Anda dapat menguji apakah tautan Anda berfungsi untuk mengarahkan ulang:

* Pengguna baru yang tidak menginstal aplikasi Anda
* Pengguna yang sudah ada, yang menginstal aplikasi Anda

<div id="new-users-without-your-app-installed" />

#### Pengguna baru yang tidak menginstal aplikasi Anda

**Prasyarat**:  <Anchor target="_blank" href="/marketers/id/docs/registering-test-devices">Perangkat uji terdaftar</Anchor> tanpa aplikasi.

**Untuk menguji tautan Anda**:

1. Di dasbor AppsFlyer, buka **Experiences & deep linking** > **OneLink Custom Links**.
2. Arahkan kursor ke  ikon**Actions** dari tautan yang ingin Anda uji dan klik **Get URL** .
3. Kirim URL pendek atau panjang ke ponsel Anda. Anda juga dapat:
   * Memindai kode QR dengan kamera ponsel Anda atau aplikasi pemindai QR.
   * Email atau WhatsApp sendiri tautannya, dan buka di ponsel Anda.  
     **Catatan:** Jangan merekatkan ke catatan iOS, atau langsung ke browser seluler. Seringkali,  sistem operasi seluler dengan sengaja tidak akan membuka aplikasi dalam konteks ini.
4. Klik tautan di perangkat seluler Anda.  
   Bergantung pada platform Anda, itu akan membawa Anda ke app store atau laman awal.   
   **Catatan**:  Diperlukan klik nyata pada perangkat seluler. Pengarahan Javascript atau 301/302 tidak dapat  memicu Tautan Universal dan Tautan Aplikasi Android. Bahkan pengarahan dasar gagal dengan metode ini di beberapa browser.
5. Unduh dan luncurkan aplikasi.
   * Aplikasi harus membuka ke layar beranda.
   * Jika Anda menerapkan deferred deep linking, aplikasi akan terbuka ke konten yang Anda tentukan di tautan parameter.
6. Di dasbor Ikhtisar **Appsflyer** cari penginstalan baru.  
   Cari  klik dan penginstalan baru di bawah sumber media (misalnya tes) dan nama kampanye yang Anda masukkan ke dalam URL.

Tautan tidak berfungsi seperti yang diharapkan? Periksa di <Anchor target="_blank" href="/marketers/id/docs/onelink-troubleshooting-and-faq">Panduan penyelesaian masalah dan Pertanyaan Umum OneLink.</Anchor>

<div id="existing-users-with-your-app-installed" />

#### Pengguna yang sudah ada, yang menginstal aplikasi Anda

**Prasyarat**: Perangkat Android dan/atau iOS  dengan aplikasi terinstal. Pastikan itu adalah sumber dan versi aplikasi tempat pengembang membuat perubahan (dan menerapkan Tautan Universal, Tautan Aplikasi, dan/atau skema URI).

**Untuk menguji tautan Anda:**

1. Di dasbor AppsFlyer, buka **Experiences & deep linking** > **OneLink**.
2. Klik **templat OneLink** yang dipilih .
3. Dari daftar, pilih tautan Kustom.
4. Arahkan kursor ke  ikon**Actions** dari tautan yang ingin Anda uji dan klik **Get URL** .
5. Kirim URL pendek atau panjang ke ponsel Anda. Anda juga dapat:
   * Memindai kode QR dengan kamera ponsel Anda atau aplikasi pemindai QR.
   * Email atau WhatsApp sendiri tautannya, dan buka di ponsel Anda.  
     **Catatan:** Jangan merekatkan ke catatan iOS, atau langsung ke browser seluler. Seringkali,  sistem operasi seluler dengan sengaja tidak akan membuka aplikasi dalam konteks ini.
6. Klik tautan di perangkat seluler Anda.  
   * Aplikasi harus membuka ke layar beranda.
   * Jika Anda menerapkan deep linking, aplikasi akan terbuka ke konten yang Anda tentukan di tautan parameter.
7. Buka dasbor  Penargetan Ulang **AppsFlyer**  .  
   Cari klik/interaksi ulang (aplikasi terbuka) di bawah sumber media tautan Anda (misalnya tes) dan nama kampanye yang Anda masukkan ke dalam URL.

Tautan tidak berfungsi seperti yang diharapkan? Periksa di <Anchor target="_blank" href="/marketers/id/docs/onelink-troubleshooting-and-faq">Panduan penyelesaian masalah dan Pertanyaan Umum OneLink.</Anchor>

</Accordion>

<div id="additional-procedures" />

## Prosedur tambahan

<div id="create-a-custom-impression-url" />

<Accordion title="Buat URL tayangan khusus">

Tautan tayangan kustom memungkinkan Anda untuk:

* Ukur  <Anchor target="_blank" href="/marketers/id/docs/about-conversion-rates#marketing-funnel-stages-and-conversion-rates-1">rasio konversi tayangan ke klik</Anchor> dari iklan yang Anda tampilkan.
* Menerima atribusi untuk tayangan.

**Prasyarat:** URL panjang OneLink yang berfungsi. URL pendek tidak didukung.

**Siapa yang terlibat:**

Pemasar dan pengembang web

**Untuk membuat URL tampilan untuk mengukur tayangan saja:**

1. Di dashboard AppsFlyer, buka **Experiences & deep linking** > **OneLink Custom Links**.
2. Arahkan kursor ke ikon **Actions** (Tindakan) dari tautan yang Anda ingin uji dan klik **Get URL** (Dapatkan URL).
3. Salin URL panjang OneLink untuk mengedit.   
   Contoh:  `https://subdomain.onelink.me/j7rN?pid=email&c=Spring`
4. Ganti subdomain (atau seluruh Domain Bermerek, jika Anda menggunakannya) dengan 'tayangan'.  Contoh: `https://impressions.onelink.me/j7rN?pid=email&c=Spring`
5. Salin URL tayangan dan kirimkan ke pengembang Anda.
6. Instruksikan pengembang web Anda untuk menerapkan URL tayangan dalam logika situs web.

Sekarang Anda memiliki URL tayangan, yang dapat digunakan untuk menghitung tayangan di laman situs Anda, **tetapi tidak dapat mengaitkan instalasi baru**.Untuk atribusi lihat tayang, ikuti langkah selanjutnya.

**Untuk menggunakan URL tayangan untuk atribusi:**

1. Siapkan URL tayangan seperti yang dijelaskan di langkah sebelumnya.
2. Pastikan <Anchor target="_blank" href="/marketers/id/docs/measure-view-through-engagements">atribusi lihat-tayang diaktifkan</Anchor>.
3. [Opsional] Jika Anda ingin mengubah nilai  <Anchor target="_blank" href="/marketers/id/docs/set-up-lookback-windows">jendela lookback</Anchor>  lihat tayang 1 hari default, tambahkan parameter  `af_viewthrough_lookback`  dengan nilai baru. Misalnya, `af_ viewthrough_lookback=5d`.
4. Salin URL tayangan dan kirimkan ke pengembang Anda.
5. Instruksikan pengembang web Anda untuk menerapkan URL tayangan dalam logika situs web.

Contoh URL tayangan lengkap:

```http
https://impressions.onelink.me/j7rN?pid=email&c=Spring&af_viewthrough_lookback=1d
```

</Accordion>

<div id="deep-linking-post-event" />

<Accordion title="Pasca-event deep linking">

Anda mungkin ingin menautkan langsung pengguna ke aktivitas atau halaman tertentu hanya setelah event, misalnya:

* Login
* Melihat layar splash
* Menyetujui syarat dan ketentuan
* Dan banyak lagi

**Untuk menautkan langsung pengguna setelah event**:

Minta programmer Anda untuk mengikuti petunjuk mereka untuk menautkan langsung penggunapasca-event untuk [Android](https://dev.appsflyer.com/hc/docs/dl_android_dl_post_event) dan [iOS](https://dev.appsflyer.com/hc/docs/dl_ios_dl_post_event).

</Accordion>

<div id="deferred-deep-linking-with-ios-private-relay" />

<Accordion title="Deferred deep linking dengan Private Relay iOS">

Dengan peluncuran iOS 15, Apple memberi pengguna iCloud+ fitur yang disebut  <Anchor target="_blank" href="https://www.macworld.com/article/348965/icloud-plus-private-relay-safari-vpn-ip-address-encryption-privacy.html">Private Relay</Anchor> , yang memberi mereka opsi untuk mengenkripsilalu lintas penjelajahan web dan menyembunyikan lokasi persis, alamat IP, dan konten lalu lintas penjelajahan mereka. Jika pengguna memilih Relay Pribadi, ini dapat mengganggu atribusi dan deep linking yang ditangguhkan. Artinya, begitu pengguna baru tanpa aplikasi masuk ke App Store, dan menginstal serta meluncurkan aplikasi, Private Relay dapat mencegah mereka dikirim ke halaman tertentu di aplikasi.

Untuk memastikan bahwa deferred deep linking (DDL) tetap berfungsi sebagaimana mestinya, Anda harus menerapkan salah satu solusi AppsFlyer berikut:

* **[Disarankan] Solusi berbasis App Clip**: Buat App Clip yang memberi Anda data atribusi pengguna, dan mengarahkan pengguna ke pengalaman App Clip yang dipersonalisasi mirip dengan apa yang Anda inginkan dicapai oleh DDL. App clip juga dapat menyertakan alur untuk mengarahkan pengguna dari App Clip ke aplikasi lengkap Anda.
* **Solusi berbasis Clipboard**: Buat laman arahan web yang menyalin data deferred deep linking dari URL dan mengarahkan pengguna ke aplikasi dengan benar. **Catatan**: Solusi ini tidak memengaruhi atribusi.

<div id="app-clipbased-solution" />

<Accordion title="Solusi berbasis App Clip">

Solusi ini menggabungkan URL pendek OneLink dengan teknologi App Clip yang tersedia di iOS, dan memungkinkan Anda untuk mengirim pengguna ke alur tertentu di produk Anda tanpa harus menginstal aplikasi lengkap. URL pendek OneLink memberi Anda data atribusi pengguna dan mengarahkan pengguna ke pengalaman App Clip yang dipersonalisasi mirip dengan apa yang Anda inginkan untuk dicapai DDL. App clip juga dapat menyertakan alur untuk mengarahkan pengguna dari App Clip ke aplikasi lengkap Anda. **Catatan**: Jika pengguna menginstal ulang aplikasi lengkap dari solusi berbasis App Clip, ini dapat dilaporkan di AppsFlyer sebagai penginstalan organik. 

<div id="flow" />

#### **Alur**

Alur dari solusi DDL berbasis App Clip adalah sebagai berikut:

1. Pengiklan membuat App Clip dan menambahkannya ke templat OneLink bagi pengguna yang mengaktifkan Private Relay.
2. Pengguna mengetuk URL OneLink.
3. Web handler AppsFlyer memeriksa apakah:
   * Perangkat menggunakan iOS 15+
   * Browsernya Safari
   * Pengguna telah mengaktifkan Private Relay.
4. Setelah AppsFlyer mengonfirmasi hal-hal di atas dan pengguna diminta untuk mengklik **Play App Clip (Putar App Clip)** atau **View in Safari (Lihat di Safari)**.
   * Jika pengguna mengklik **Putar App Clip**, kartu App Clip ditampilkan ke pengguna.
   * Jika pengguna mengklik Lihat di Safari, laman arahan dibuka dan meminta mereka untuk membuka App Clip.
5. Pengguna membuka App Clip.
6. App Clip membuka dan memberi pengguna pengalaman yang ditentukan oleh pemasar dan pengembang aplikasi.
7. Jika App Clip menyertakan alur untuk mengarahkan pengguna ke aplikasi lengkap, pengguna akan diarahkan ke App Store untuk mengunduh aplikasi lengkap. Setelah peluncuran aplikasi, mereka mendapatkan pengalaman pengguna yang ditentukan oleh pengembang.

**Prasyarat:** SDK AppsFlyer V6.4.0+

**Untuk menyiapkan solusi DDL berbasis App Clip**:

1. Beri tahu pengembang untuk mengikuti <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_private_relay#app-clip-based-solution">instruksi dev hub (pusat pengembang) berbasis App Clip</Anchor>. dan buat App Clip yang memberi pengalaman pengguna yang diinginkan. Ini juga dapat menyertakan alur untuk mengarahkan pengguna dari App Clip ke aplikasi lengkap Anda
2. Membuat atau mengedit <Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template">Templat OneLink</Anchor> dengan Tautan Universal dan [penautan langsung tertunda](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking).
3. Di templat OneLink, aktifkan **Tampilkan App Clip jika pengguna memiliki Private Relay**. Jangan aktifkan kecuali Anda memiliki App Clip.  
   **Catatan**: Saat membuat perubahan pada templat OneLink dengan Tautan Universal, seperti menambahkan (atau menghapus) fitur App Clip, dapat diperlukan beberapa jam untuk memperbarui file AASA. Oleh karena itu, tautan yang Anda buat berbasis templat mungkin tidak langsung memiliki fungsi yang diperbarui.
4. Buat tautan personalisasi berbasis templat OneLink.
5. Di App Store Connect, buka bagian **App Clip Experience** , gulir ke bawah ke **URL Aplikasi**, dan masukkan URL templat OneLink (domain + ID. Misalnya: `yourbrand.onelink.me/GrbZ`), atau URL pendek tautan khusus OneLink.  
   **Catatan**: Jika Anda memasukkan tautan khusus OneLink, solusi berbasis App Clip hanya akan berfungsi bagi pengguna yang mengetuk tautan tertentu; tautan lain yang dibuat berbasis templat OneLink tidak akan berfungsi.

</Accordion>

<div id="clipboardbased-solution" />

<Accordion title="Solusi berbasis Clipboard">

<div id="flow-1" />

#### **Alur**

Alur solusi DDL berbasis clipboard adalah sebagai berikut:

1. Pengiklan membuat deferred deep link yang berisi parameter `af_cp_lp=true`.
2. Pengguna mengetuk deferred deep link.
3. AppsFlyer memeriksa apakah:
   * Perangkat menggunakan iOS 15+
   * Browsernya Safari
   * Pengguna telah mengaktifkan Private Relay.
   * Tautan tersebut berisi parameter `af_cp_lp=true`.
4. Setelah AppsFlyer mengonfirmasi hal di atas, laman arahan web dimuat, yang berisi ikon aplikasi, gambar, dan CTA untuk mendapatkan aplikasi dari App Store. Pengguna juga melihat pesan yang menjelaskan prosesnya: URL disalin untuk memastikan pengalaman pengguna terbaik yang akan mengarahkan mereka ke halaman tertentu di aplikasi.  

   ![ios_15_ip_masking__1_.png](https://files.readme.io/c130314c98ebd42f50feaafd752c0cea954f42c5bfd99a6dbd94daf9e48c2ff4-30151216595345.png)
5. Pengguna mengetuk **Get the app (Dapatkan aplikasi)**.
6. Pengguna diarahkan ke App Store untuk menginstal aplikasi. Kemudian, pada peluncuran pertama, pengguna diarahkan ke halaman aplikasi tertentu.

<div id="requirements" />

#### **Persyaratan**

Solusi salin/rekat DDL laman arahan mewajibkan:

* Pengguna menggunakan Safari untuk menelusuri web.
* Deferred deep link menyertakan parameter `af_cp_lp=true` .
* AppsFlyer iOS SDK V6+.
* Pengembang aplikasi iOS Anda untuk menerapkan kode yang merekatkan data deferred deep link di URL dari clipboard. Ini bukan bagian dari SDK AppsFlyer.
* Pengguna akhir untuk mencentang kotak (default). Jika tidak dicentang, URL tidak disalin dan deferred deep linking tidak berfungsi.

<div id="setup" />

#### **Pengaturan**

**Untuk mengatur solusi DDL berbasis clipboard**:

1. Beri tahu developer iOS Anda untuk: 
   1. Mengikuti <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_private_relay#clipboard-based-solution">instruksi dev hub</Anchor> dan mengintegrasikan kode yang diperlukan di SDK AppsFlyer.
   2. Menerapkan kode yang merekatkan data deferred deep link di URL dari clipboard. Ini bukan bagian dari SDK AppsFlyer.
2. Menambahkan parameter the `af_cp_lp=true` ke tautan Anda.   
   Anda dapat melakukannya dengan menambahkan parameter khusus di UI tautan khusus AppsFlyer OneLink atau cukup menambahkan parameter ke salah satu tautan Anda.

</Accordion>

</Accordion>

<div id="additional-information" />

## Informasi Tambahan

<div id="examples" />

<Accordion title="Contoh">

**Contoh dasar**

Mark adalah pemasar layanan pengiriman bahan makanan yang sukses yang disebut "Feed Me." Mark menargetkan nomor telepon basis penggunanya untuk mengunduh aplikasi iOS dan Android seluler Feed Me yang baru. Kampanye SMS direncanakan. Namun, Mark tidak mengetahui pengguna mana yang memiliki perangkat Android atau iOS. Dia juga tidak tahu apakah mereka menginstal aplikasi atau tidak.

Untuk mengatasi ini, Mark mengirimi pengguna SMS yang berisi URL pendek yang didukung oleh OneLink. Saat pengguna menerima SMS dan mengklik tautan:

* Jika mereka belum memiliki aplikasi, mereka secara otomatis mengarahkan mereka ke toko aplikasi atau laman awal yang sesuai, di mana mereka dapat menginstal aplikasi dengan mudah.
* Jika mereka sudah menginstal aplikasi, aplikasi akan terbuka untuk mereka.

Penginstalan baru dan interaksi ulang dikaitkan dengan kampanye SMS, memungkinkan Mark untuk memeriksa keberhasilan kampanye SMS di AppsFlyer. 

**Contoh deep linking**

Tandai SMS pemasar (dari contoh sebelumnya) sedikit berhasil membuat pengguna mengunduh dan membuka aplikasi. Namun, tidak banyak pengguna yang mengklik tautan dan membuka aplikasi yang dikonversi untuk melakukan pemesanan.

Mark memutuskan untuk meningkatkan konversi dengan menawarkan sekantong buah persik, apel, atau alpukat gratis untuk setiap pembelian. Untuk ini, Mark menciptakan pengalaman deep linking yang mulus untuk pengguna yang sudah ada. Dia mengirimkan email terperinci kepada basis penggunanya yang menekankan manfaat dari 3 buah sehat ini. 

Untuk setiap buah yang disebutkan dalam email, Mark menyertakan tautan dengan nilai deep link yang didukung oleh OneLink, dikonfigurasi (dengan bantuan pengembang seluler) ke:

Untuk mengatasi ini, Mark mengirimi pengguna SMS yang berisi URL pendek yang didukung oleh OneLink. Saat pengguna menerima SMS dan mengklik tautan:

* Jika mereka sudah menginstal aplikasi, mereka akan langsung dibawa ke laman buah yang relevan.
* Jika mereka belum memiliki aplikasi, mereka akan diarahkan ke toko aplikasi atau laman awal yang sesuai, berdasarkan perangkat mereka. Dan kemudian, begitu mereka mengunduh dan membuka aplikasi, mereka langsung dibawa ke laman buah.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Sifat | Catatan |
| --- | --- |
| <span id="onelink-characters"></span>Karakter OneLink | <ul><li>Panjang URL total tidak boleh melebihi 2.000 karakter</li><li>Nama tautan dan sumber media: tidak boleh melebihi 150 karakter</li><li>Karakter khusus berikut tidak diperbolehkan dalam parameter atau nilai OneLink: ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ', >, &lt;, /, \{, \}<ul><li>Karakter khusus () tidak diperbolehkan di Android, iOS, dan parameter pengalihan web</li></ul></li><li>ID URL pendek tidak boleh melebihi 50 karakter</li></ul> |
| <span id="posting-onelink-urls-in-web-pages"></span>Memposting URL OneLink di halaman web | Menggunakan `target="_blank"` di tag href HTML tidak menyebabkan pengarahan ke Google Play atau App Store. Jika URL OneLink ditempatkan di dalam html  tag dengan atribut **target="\_blank"** , ini membuka halaman kosong di Chrome di Android dan iOS. Hal ini memengaruhi fungsionalitas OneLink. Pastikan bahwa  tag tidak menyertakan atribut target. |
| <span id="agencies"></span>Agensi | Agensi dapat menggunakan templat OneLink yang ada untuk membuat tautan atribusi khusus untuk mereka sendiri **jika agensi adalah mitra dari semua aplikasi dalam templat**. |
| <span id="social-media-preview-image"></span>Gambar pratinjau media sosial | Jika jenis gambar tidak didukung oleh platform media sosial, itu tidak akan ditampilkan. |
| <span id="desktop"></span>Desktop | Saat Anda menyetel URL atau templat OneLink untuk mengarahkan pengguna desktop ke URL yang berbeda, URL web ditambahkan ke tautan di parameter `af_web_dp` . Saat tautan berisi  `af_web_dp` , AppsFlyer tidak mendaftarkan klik jika ini berasal dari desktop. |
| <span id="af_enc_data"></span>af\_enc\_data | Tidak didukung pada URL tayangan. |
| <span id="social-media-preview-og-tag"></span>Pratinjau media sosial - tag OG | Untuk WhatsApp, gambar tidak boleh melebihi 300 KB. |
| <span id="android-social-apps-webview-deep-linking-redirection"></span>Pengalihan tautan langsung Webview aplikasi sosial Android | Karena perubahan terkini di berbagai aplikasi sosial Android, alur pengalihan tautan langsung di tampilan browser internal (WebView) tidak berfungsi.<br /><br />Untuk mengakomodasi perubahan dan mengaktifkan kembali tautan langsung dan pengalihan, kami harus memperkenalkan interaksi pengguna tambahan untuk aplikasi sosial Android berikut:<ul><li>Versi Facebook di atas v420</li><li>Instagram</li><li>Facebook Messenger</li><li>Snapchat</li></ul>Alur pengguna baru mengharuskan pengguna aplikasi di atas untuk mengeklik tombol halaman awal tambahan untuk memicu pengalihan ke Google Play Store dan toko pihak ketiga lainnya.<br /><br /><br />**Catatan:**<ul><li>Facebook versi 420 dan di bawahnya berfungsi seperti sebelumnya, tanpa interaksi pengguna tambahan.</li><li>Tautan Aplikasi di postingan Facebook berfungsi seperti sebelumnya tanpa interaksi pengguna tambahan.</li><li>Tautan Aplikasi di Instagram chat berfungsi seperti sebelumnya tanpa interaksi pengguna tambahan.</li><li>Dalam alur tautan langsung, saat aplikasi tidak diinstal, ada batasan yang diketahui: pesan pop-up kesalahan. Pesan ini tidak memengaruhi alur; pengguna masih dialihkan ke toko seperti yang diharapkan.</li></ul> |
| <span id="onelink-link-previews-sometimes-fail-to-display-correctly-on-facebook-and-linkedin"></span>Pratinjau tautan OneLink terkadang gagal ditampilkan dengan benar di Facebook dan LinkedIn. | **Deskripsi**  <br />Masalah muncul ketika situs web tujuan tidak mengenali string agen pengguna `AppsFlyerBot-Previewer/1.0` dalam permintaan pratinjau sebagai berasal dari robot (atau crawler). Dalam kasus seperti itu, situs web gagal merespons dengan konten pratinjau yang diberi tag OG yang sesuai.<br /><br />**Solusi**  <br />Anda dapat mengonfigurasi halaman awal agar memperlakukan halaman dengan string header agen pengguna `AppsFlyerBot-Previewer/1.0` sebagai berasal dari robot dengan <Anchor target="_blank" href="https://moz.com/learn/seo/robotstxt">memperbarui file robot.txt situs web Anda</Anchor>. |

</Accordion>

<div data-zendesk-anchors="onelink-links-and-experiences=tautan-dan-pengalaman-onelink h_01H8Y6DDT4M8XGAEJJVTHKHPKV=tautan-dan-pengalaman-onelink create-a-onelink-link=buat-tautan-onelink h_01H8Y6DDT41C6JYKXET0NDRB1G=buat-tautan-onelink h_01H8Y6DDT4C543RS2BXAGS487M=experiences h_01H8Y6DDT4WZ5FKZYBX2H08MFD=general-settings enable-retargeting-for-the-app=aktifkan-penargetan-ulang-untuk-aplikasi h_01H8Y6DDT4R7785X5DRES66BKJ=aktifkan-penargetan-ulang-untuk-aplikasi h_01H8Y6DDT4JT9H0R13ZNGHJ79S=social-media-preview-og-tags h_01H8Y6DDT4PHY2F5E3GK582P51=social-app-landing-page h_01H8Y6DDT463F5569B28DD17SV=penting h_01H8Y6DDT4MMD1AW6D1PNGNX5X=catatan to-use-the-social-app-landing-page=untuk-menggunakan-laman-arahan-aplikasi-media-sosial h_01H8Y6DDT4JB4RT438MAGNNX2S=untuk-menggunakan-laman-arahan-aplikasi-media-sosial to-set-up-the-social-apps-landing-page=untuk-mengatur-laman-arahan-aplikasi-sosial h_01H8Y6DDT4G34S3RV3ZH64XT19=untuk-mengatur-laman-arahan-aplikasi-sosial h_01H8Y6DDT5XNJVYW2Y8F6JWPK2=deep-linking-and-deferred-deep-linking h_01H8Y6DDT5JR3B3DMR87JCBZ69=tips h_01H8Y6DDT5KSBE00WWDGQ5R1AQ=catatan-1 h_01H8Y6DDT58FC3HMSRZBMGZZRJ=redirection h_01H8Y6DDT5AAQ3BZD8QB9H19QB=additional-parameters h_01H8Y6DDT5B6M7CETQRD9NKX8R=testing new-users-without-your-app-installed=pengguna-baru-yang-tidak-menginstal-aplikasi-anda h_01H8Y6DDT50DH5TGVVPJPJC4MG=pengguna-baru-yang-tidak-menginstal-aplikasi-anda existing-users-with-your-app-installed=pengguna-yang-sudah-ada-yang-menginstal-aplikasi-anda h_01H8Y6DDT5KDEWS40XPYGYC8HK=pengguna-yang-sudah-ada-yang-menginstal-aplikasi-anda additional-procedures=prosedur-tambahan h_01H8Y6DDT5YR8JA5YMZFPMCC2X=prosedur-tambahan h_01H8Y6DDT58EFS8S46D1AVP3T1=create-a-custom-impression-url h_01H8Y6DDT5S4NEJMNJR4K3QMNH=deep-linking-post-event h_01H8Y6DDT58Y6CS27M2W3MHYAD=deferred-deep-linking-with-ios-private-relay h_01H8Y6DDT5A7J07KNNRWCXCBH2=app-clipbased-solution flow=alur h_01H8Y6DDT5VDKAR89B8N6D7YMB=alur h_01H8Y6DDT62H71A8DPG00A3ZTN=clipboardbased-solution flow::21baf6ac=alur-1 h_01H8Y6DDT638T7C9HQHZ1CJ726=alur-1 requirements=persyaratan h_01H8Y6DDT6JGP33AWFQV6Z8FF0=persyaratan setup=pengaturan h_01H8Y6DDT61ENGJFZ1XS28GS1T=pengaturan additional-information=informasi-tambahan h_01H8Y6DDT679SGBTSM669F9FHV=informasi-tambahan h_01H8Y6DDT6TX4WTP2HYRF11DZ3=examples h_01H8Y6DDT6TQYRS81BMHARB62S=traits-and-limitations" />
