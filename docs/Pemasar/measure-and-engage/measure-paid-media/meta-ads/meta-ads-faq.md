---
title: FAQ Meta ads
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-11-09T10:04:49Z'
  edited_at: '2023-10-23T20:40:34Z'
  id: 4410472805649
  locale: id
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/id/articles/4410472805649
---
> **Sekilas:** Temukan jawaban atas pertanyaan yang sering ditanyakan tentang penggunaan Meta ads di AppsFlyer.

<div id="can-i-use-get" />

<div id="conversion-events-are-not-sent-to-meta-ads" />

<div id="aem-attribution-is-not-working" />

<div id="are-ios-universal-links-and-android-app-links-supported-in-metas-non-paid-content" />

<div id="how-can-i-get-device-level" />

<div id="note" />

<div id="submitting-the-decryption-key" />

<div id="sdk-and-setup-notes" />

<div id="campaign-attribution-fields" />

<div id="meta-install-referrer" />

<div id="google-play-install-referrer-api" />

<div id="meta-ads-faq" />

## FAQ iklan meta

<div id="i-dont-see-facebook-campaign-clicks-in-appsflyers-dashboard" />

<Accordion title="Saya tidak melihat klik kampanye Meta ads di dashboard AppsFlyer">

Secara default, Meta ads hanya mengirimkan data konversi dan interaksi. Namun, Anda juga dapat dengan mudah mulai mendapatkan <Anchor target="_blank" href="/marketers/id/docs/meta-ads-integration-setup#cost-clicks-and-impressions">data klik, impresi, dan biaya untuk kampanye Meta ads Anda</Anchor>.

</Accordion>

<div id="can-i-stop-cost-data-sync" />

<Accordion title="Dapatkah Saya Menghentikan Sinkronisasi Data Biaya?">

Untuk menghentikan sinkronisasi data biaya dengan Meta ads, <Anchor target="_blank" href="https://www.facebook.com/help/405094243235242">hapus AppsFlyer dari Integrasi Bisnis Anda di akun Meta ads Anda</Anchor>.

</Accordion>

<div id="can-appsflyer-show-the-campaign-level-and-ad-groups" />

<Accordion title="Dapatkah AppsFlyer menampilkan level kampanye dan ad grup?">

Ya. Faktanya, AppsFlyer juga menampilkan level iklan tunggal, jadi Anda memiliki 3 level pembagian dengan Meta ads, kampanye >> grup iklan >> iklan.

</Accordion>

<div id="is-facebook-data-shown-in-realtime" />

<Accordion title="Apakah data Meta ads ditampilkan secara real-time?">

Ya, semua penginstalan dan in-app event berikutnya ditampilkan secara real-time. Namun, data klik, impresi, dan biaya yang diperoleh AppsFlyer dalam bentuk gabungan dari Meta ads tiba secara berkala setiap beberapa jam.

</Accordion>

<div id="when-can-i-see-a-new-campaigns-data-on-appsflyer" />

<Accordion title="Kapan Saya Dapat Melihat Data Kampanye Baru di AppsFlyer?">

Untuk melihat data dari iklan baru, ad set, dan kampanye di Meta ads, mereka harus menghasilkan sedikitnya satu penginstalan.

Misalnya, sebuah iklan baru telah menghasilkan 100 klik tanpa penginstalan, dan tidak ditampilkan di dashboard dan data AppsFlyer. Iklan lainnya hanya menghasilkan 1 klik dan 1 penginstalan, tetapi ditampilkan di AppsFlyer.

</Accordion>

<div id="how-can-i-get-more-installs-from-facebook" />

<Accordion title="Bagaimana cara mendapatkan lebih banyak penginstalan dari Meta ads?">

Jika Anda telah mengaktifkan penargetan ulang untuk Meta ads, Anda bisa mendapatkan penginstalan hingga 100% lebih banyak dalam kampanye akuisisi pengguna, gratis!  
Bagaimana? Baca <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns#what-is-srn-mistargeting">di sini</Anchor>.

</Accordion>

<div id="do-you-make-facebook-raw-data-available-to-agencies" />

<Accordion title="Apakah Anda menyediakan data lengkap Meta ads untuk agensi?">

Tidak. Kami tidak diperbolehkan memberikan data lengkap Meta ads kepada agensi, hal ini karena agensi dianggap sebagai pihak ketiga dalam ketentuan layanan Meta.

</Accordion>

<div id="i-dont-see-facebook-raw-data-in-the-installation-and-inapp-events-reports" />

<Accordion title="Saya tidak melihat data lengkap Meta ads di laporan penginstalan dan in-app event">

Secara default, Meta ads tidak mengizinkan distribusi data tingkat pengguna. Lihat <Anchor target="_blank" href="/marketers/id/docs/meta-ads-integration-setup#pengaturan-atribusi-meta-ads-lanjutan">atribusi lanjutan Meta ads</Anchor> untuk detail lebih lanjut.

</Accordion>

<div id="any-specific-columns-for-facebook-in-appsflyers-performance-reports" />

<Accordion title="Adakah kolom khusus untuk Meta ads di laporan kinerja AppsFlyer?">

Ya. Laporan kinerja memiliki struktur kolom statis dalam kombinasi sumber media apa pun yang dipilih, yang menyajikan informasi hingga ke level kampanye.  
Namun, jika Anda HANYA mengunduh laporan kinerja untuk Meta ads, AppsFlyer akan menambahkan 4 kolom ke laporan kinerja yang menyajikan informasi hingga ke level iklan tunggal! Kolom yang ditambahkan adalah Nama Adset, ID Adset, Nama Adgroup (yaitu iklan tunggal), dan ID Adgroup.

[![](https://files.readme.io/fe0c08fc17a6060bfdfa0e9c8b21eee755a7a868ee1b4b60a16808e126281dc4-4411036714001.png)](https://files.readme.io/fe0c08fc17a6060bfdfa0e9c8b21eee755a7a868ee1b4b60a16808e126281dc4-4411036714001.png)

</Accordion>

<div id="can-i-work-with-facebook-fmps-and-measure-performance-with-appsflyer" />

<Accordion title="Dapatkah saya bekerja dengan mitra manajemen kampanye Meta dan mengukur kinerja dengan AppsFlyer?">

Ya. AppsFlyer terintegrasi dengan puluhan mitra manajemen kampanye Meta. Mitra ini dapat disiapkan untuk atribusi di halaman Integrasi Aktif di dashboard.

Untuk detail tentang pengaturan pengaitan dengan mitra pengelolaan kampanye Meta, klik <Anchor target="_blank" href="/marketers/id/docs/configuring-meta-campaign-management-partners">di sini</Anchor>.

</Accordion>

<div id="what-should-i-do-when-i-receive-the-following-warning" />

<Accordion title="Apa yang harus saya lakukan jika menerima peringatan berikut?">

[![](https://files.readme.io/ad1d07250ae23a0f4d5e145b615ac09a81990e6d46b50a2795c26b4e2be21297-4411045335185.png)](https://files.readme.io/ad1d07250ae23a0f4d5e145b615ac09a81990e6d46b50a2795c26b4e2be21297-4411045335185.png)

* Verifikasi ID Aplikasi Facebook dan periksa apakah Anda memiliki batasan geografis atau usia pada ID Aplikasi Facebook mereka.
* Jika atribusi sudah berjalan, hal ini mengindikasikan bahwa aplikasi sudah tersedia untuk publik pada Portal Pengembang Meta dan Anda dapat mengabaikan pesan kesalahan ini.

</Accordion>

<div id="what-happens-with-different-lookback-windows-than-on-facebook" />

<Accordion title="Apa yang terjadi dengan jendela lookback yang berbeda dari Meta ads?">

Klik 7 hari dan tampilan 1 hari adalah jendela lookback maksimum dan default untuk Meta ads.  
Mengonfigurasi periode waktu ini agar menjadi lebih pendek di AppsFlyer akan menurunkan atribusi Meta ads di AppsFlyer. Di sisi lain, mengonfigurasinya lebih lama di AppsFlyer tidak berpengaruh, karena penginstalan yang dilakukan setelah jendela Meta ads berakhir, tidak diatribusikan ke Meta ads.  
Jadi, untuk meminimalkan perbedaan, disarankan untuk mengonfigurasi jendela lookback Meta ads di AppsFlyer menjadi klik 7 hari dan tampilan 1 hari.

</Accordion>

<div id="what-are-the-facebook-api-parameters" />

<Accordion title="Apa itu parameter Meta API?">

Pada beberapa API AppsFlyer, parameter Meta memiliki nama yang berbeda dengan yang ditampilkan di dashboard, untuk alasan kompatibilitas dengan versi lama. Lihat tabel di bawah ini:  

| Data konversi | Data lengkap AppsFlyer | Meta |
| --- | --- | --- |
| campaign | campaign | campaign\_group\_name |
| campaign\_id | ID kampanye | campaign\_group\_id |
| adgroup | ad | adgroup\_name |
| adgroup\_id | ID iklan | adgroup\_id |
| adset | adset | campaign\_name |
| adset\_id | ID adset | campaign\_id |
| ad\_id | ID IKLAN | ad\_id |
| agency | Partner | N/A |
| is\_fb | Media Source | is\_fb |
| af\_channel | Channel | publisher\_platform |

</Accordion>

<div id="how-long-do-you-keep-facebook-s-userlevel-data" />

<Accordion title="Berapa lama Anda menyimpan data tingkat pengguna Meta ads?">

Meta ads mengharuskan penyedia atribusi untuk menghapus data tingkat pengguna 6 bulan setelah penginstalan. Ini berarti bahwa event yang dilakukan oleh pengguna 6 bulan setelah mereka meng-nstal aplikasi dihitung sebagai organik.  
Data agregat sebelumnya tetap sama.  
Ini relevan untuk semua kanal Meta ads (aplikasi Facebook, Instagram, Messenger, dan AudienceNetwork).

</Accordion>

<div id="are-ios-universal-links-and-android-app-links-supported-in-meta-ads" />

<Accordion title="Apakah Tautan Universal iOS dan Tautan Aplikasi Android didukung di Meta Ads?">

Tautan Universal iOS dan Tautan Aplikasi Android didukung dan dapat digunakan di Meta ads. Untuk informasi lebih lanjut, lihat<Anchor target="_blank" href="https://www.facebook.com/business/help/1627795160837067?id=1858550721111595"> Pusat bantuan Meta</Anchor>.

* Untuk iklan Statis (non-katalog), Tautan Universal iOS dan Tautan Aplikasi Android hanya didukung di kampanye tempat **Aplikasi** dipilih sebagai tujuan.
* Untuk iklan Dinamis, Tautan Universal iOS, Tautan Aplikasi Android, dan skema URI dapat digunakan sebagaimana diuraikan [di sini](/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads).

**Catatan:** Tautan Universal iOS dan Tautan Aplikasi Android hanya didukung di iklan berbayar.

</Accordion>

<div id="can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads" />

<Accordion title="Dapatkah tautan OneLink digunakan untuk pembukaan aplikasi dan deep linking di iklan produk dinamis?">

Ya. Tautan OneLink dengan Tautan Aplikasi, Tautan Universal, atau skema URI yang dikonfigurasi didukung dalam iklan produk dinamis. Anda dapat menggunakan tautan OneLink di umpan data Anda untuk katalog yang digunakan dalam iklan dinamis di bawah **applink.ios\_url** dan **applink.android\_url** bidang.

</Accordion>

<div id="meta-ads-cost-faq" />

## FAQ biaya Meta ads

<div id="getting-facebook-cost-data-in-the-appsflyer-dashboard" />

<Accordion title="Mendapatkan data biaya Meta ads di dashboard AppsFlyer">

AppsFlyer mendapatkan data pembelanjaan (termasuk klik dan impresi) dari kampanye Meta ads jika satu atau lebih penginstalan terjadi selama 7 hari sebelumnya.

Jika kampanye Meta ads terlibat dengan beberapa platform (Android, iOS, desktop, dll.), biaya di Dashboard adalah khusus platform dan dihitung oleh Meta ads.

<Anchor target="_blank" href="/marketers/id/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Mendapatkan biaya Meta ads  termasuk klik dan impresi</Anchor>.

</Accordion>

<div id="facebook-cost-example" />

<Accordion title="Contoh biaya Meta ads">

Pemasang iklan menjalankan kampanye menggunakan Meta ads. Di AppsFlyer, pemasang iklan akan melihat hal berikut:

![mceclip2.png](https://files.readme.io/a1aa5847db5c0b873b34b1d4de43ade7d4109608371e05a84342122e56d0ce08-4411031032081.png)

Informasi biaya disediakan oleh Meta ads ke AppsFlyer. Jumlah **penginstalan** dihitung oleh AppsFlyer menggunakan aturan atribusi AppsFlyer. Akibatnya, eCPI yang dihitung oleh Meta ads dan AppsFlyer biasanya berbeda.

</Accordion>

<div id="i-cant-see-old-facebook-cost-data-in-the-appsflyer-dashboard" />

<Accordion title="Saya tidak dapat melihat data biaya Meta ads lama di dashboard AppsFlyer">

Setelah melakukan login admin Meta ads pertama yang dijelaskan di atas AppsFlyer menerima data biaya Meta ads hingga 7 hari secara retroaktif untuk kampanye yang ada. Data biaya sebelumnya tidak tersedia.

Dalam sinkronisasi selanjutnya, AppsFlyer juga menerima data dari 7 hari terakhir. Artinya, data biaya, klik, dan impresi dikumpulkan untuk semua kampanye, yang memiliki minimal 1 konversi selama 7 hari terakhir.

</Accordion>

<div id="cost-data-was-fine-for-a-few-months-but-it-stopped-displaying" />

<Accordion title="Data biaya ditampilkan beberapa bulan, tetapi kemudian berhenti ditampilkan.">

Meta ads dapat mengatur ulang izin ini untuk mendapatkan data biaya setiap beberapa bulan. Jika Anda melihat data biaya berhenti muncul di dashboard, harap ulangi langkah login admin Meta ads lagi.

Jika pengguna admin Meta ads mengubah kata sandi Meta ads mereka, langkah login juga harus diulang.

</Accordion>

<div id="i-clicked-on-my-facebook-ad-5-minutes-ago-why-dont-i-see-the-click-in-appsflyer" />

<Accordion title="Saya mengklik iklan Facebook saya 5 menit yang lalu. Mengapa saya tidak melihat klik di AppsFlyer?">

AppsFlyer memperoleh kumpulan data klik, impresi, dan biaya dari Meta ads secara berkala setiap beberapa jam. Jadi, mungkin diperlukan beberapa jam sebelum tindakan ini ditampilkan di dashboard AppsFlyer.

</Accordion>

<div id="can-i-get-raw-data-on-clicks-and-impressions-from-facebook" />

<Accordion title="Bisakah saya mendapatkan data lengkap tentang klik dan impresi dari Meta ads?">

Karena AppsFlyer hanya mendapatkan data klik dan impresi gabungan dari Meta ads, seluruh kumpulan klik dan impresi lengkap tidak tersedia. Satu-satunya klik dan impresi lengkap yang tersedia dalam laporan lengkap adalah semua yang menghasilkan penginstalan.

</Accordion>

<div id="are-there-limitations-of-facebook-cost-data-by-geo" />

<Accordion title="Apakah ada batasan data biaya Meta ads menurut geo?">

Jika Anda memfilter menurut Geo di dashboard AppsFlyer, Anda dapat melihat ringkasan dan perincian data biaya Meta ads.

Data ini hanya tersedia untuk "Kampanye Penginstalan Aplikasi Seluler" di Meta ads.

Selain itu, biaya menurut data Geo hanya tersedia untuk kampanye platform tunggal. Ini berarti kampanye yang memiliki ad set bertarget Android dan ad set bertarget iOS tidak dapat memiliki data biaya khusus Geo. **Untuk mendapatkan data biaya penuh, dedikasikan kampanye untuk setiap platform**.

</Accordion>

<div id="what-are-the-limitations-of-facebook-cost-data-in-master-api" />

<Accordion title="Apa batasan data biaya Meta ads di Master API?">

Facebook tidak mendukung pengelompokan data biaya berdasarkan Geo dan Kanal secara simultan di <Anchor target="_blank" href="/marketers/id/docs/master-api-user-acquisition-metrics-via-api">laporan API Master</Anchor>.

Untuk membuat laporan dengan data biaya secara lengkap, kelompokkan hanya berdasarkan satu dimensi berikut.

</Accordion>

<div id="the-total-cost-doesnt-match" />

<Accordion title="Total biayanya tidak cocok.">

Ada perbedaan antara Meta ads dan model atribusi AppsFlyer. Perbedaan ini dapat menyebabkan perbedaan dengan data biaya Meta ads:

* **Atribusi lintas-perangkat Meta ads:** hal ini terkadang dapat menyebabkan masalah saat kampanye untuk satu platform (iOS/Android) menunjukkan penginstalan dengan biayanya untuk platform lain.
* **Kampanye non-seluler Meta ads:** dalam kampanye ini, seperti kampanye klik tautan Meta ads, pengguna desktop pada akhirnya dapat menginstal aplikasi seluler. Untuk kampanye lintas perangkat ini, AppsFlyer tidak menampilkan biaya. Namun, jika klik tautan dilakukan oleh perangkat yang sama yang menginstal aplikasi, data biaya diterima.  
  Misalnya, pengguna Facebook mengeklik iklan yang mengarah ke halaman arahan pemasang iklan di komputer desktop. Seminggu kemudian, pengguna Facebook yang sama menginstal aplikasi iOS pemasang iklan di perangkat iPhone. Meskipun penginstalan diatribusikan dan ditampilkan di dashboard AppsFlyer, biaya penginstalan lintas platform ini tidak.
* **Kampanye dengan 0 hasil dalam 7 hari terakhir** - AppsFlyer menyinkronkan biaya hanya untuk kampanye yang memiliki penginstalan/konversi dalam 7 hari terakhir. Jika biaya Meta ads baru saja ditetapkan, kampanye yang tidak aktif selama lebih dari 7 hari sebelumnya tidak akan menampilkan biaya.

</Accordion>

<div id="why-is-the-appsflyer-calculation-for-ecpi-different-from-the-cost-calculated-by-facebook-while-the-total-cost-is-identical" />

<Accordion title="Mengapa perhitungan AppsFlyer untuk eCPI berbeda dengan biaya yang dihitung oleh Meta ads, sedangkan total biayanya identik?">

Biaya Per Pengistalan dihitung dengan membagi total biaya dengan jumlah penginstalan. Karena <Anchor target="_blank" href="/marketers/id/docs/meta-ads-discrepancies">AppsFlyer menghitung instal dengan cara yang berbeda dari Meta ads</Anchor>, biasanya eCPI akan berbeda di antara keduanya.

</Accordion>

<div id="why-doesnt-cost-data-include-data-from-all-campaigns" />

<Accordion title="Mengapa data biaya tidak menyertakan data dari semua kampanye?">

Ketika pengguna yang melakukan login Meta ads (dijelaskan di atas) tidak memiliki akses ke beberapa kampanye yang sedang berjalan, hasilnya adalah kampanye yang ditampilkan di dashboard AppsFlyer tetapi tidak memiliki data biaya, klik, dan impresi.

**Catatan:** Meskipun beberapa pengguna Meta ads mungkin memiliki izin untuk menjalankan kampanye di Meta Business Manager, hanya satu yang diperlukan untuk melakukan login Meta ads.

</Accordion>

<div id="is-facebook-cost-data-displayed-for-retargeting-campaigns" />

<Accordion title="Apakah data biaya Meta ads ditampilkan untuk kampanye penargetan ulang?">

Data biaya dan ROI untuk kampanye penargetan ulang dapat ditemukan di tampilan **terpadu**  <Anchor target="_blank" href="/marketers/id/docs/cohort-and-retention-dashboard">Laporan Kohort</Anchor>.

</Accordion>

<div id="why-does-the-facebook-cost-configuration-window-close-before-login" />

<Accordion title="Mengapa jendela konfigurasi biaya Meta ads ditutup sebelum login?">

Jika Anda masuk ke Meta ads di browser yang sama di tempat Anda melakukan konfigurasi, jendela secara otomatis terhubung ke Meta ads menggunakan kredensial tersebut. Jika akses telah diberikan ke AppsFlyer, maka tidak ada yang dapat dilakukan dan jendela ditutup.

</Accordion>

<div id="why-is-there-a-discrepancy-in-cost-data-for-apps-in-the-amazon-app-store" />

<Accordion title="Mengapa ada perbedaan data biaya untuk aplikasi di Amazon app store?">

Berbeda dengan data AppsFlyer, Meta ads tidak membedakan antara data biaya dari aplikasi Android seperti aplikasi Amazon—yang berbasis Android. Oleh karena itu, data biaya pengguna Amazon dapat diatribusikan ke kampanye yang menargetkan pengguna Android lain, bukan kampanye Amazon asli.

</Accordion>

<div id="how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked" />

<Accordion title="Bagaimana cara menghubungkan data biaya akun Meta ads baru saat akun lama saya ditautkan?">

Jika Anda ingin beralih ke akun iklan baru tetapi biaya Meta ads Anda sudah ditautkan melalui AppsFlyer dengan akun iklan lama Anda, Anda harus memutuskan hubungan akun iklan melalui Meta ads dan kemudian menghubungkan akun iklan baru di AppsFlyer.

1. Pada Meta ads, buka **Pengaturan** > **Integrasi Bisnis**.
2. Pada tab **Active**, hapus integrasi AppsFlyer.  

    [![](https://files.readme.io/8dc7c577d4497aac2206dc46db683c2de9a48f4b23674f81560b04b82a3cf44f-4411031030033.png)](https://files.readme.io/8dc7c577d4497aac2206dc46db683c2de9a48f4b23674f81560b04b82a3cf44f-4411031030033.png)
3. Buka dashboard AppsFlyer dan hubungkan biaya dengan akun iklan baru.

</Accordion>

<div id="facebook-sdk-faq" />

## FAQ SDK Facebook

<div id="who-needs-facebooks-sdk" />

<Accordion title="Siapa yang butuh SDK Facebook?">

Aplikasi Anda mungkin sudah memiliki SDK Facebook yang terintegrasi ke dalamnya, sebelum SDK AppsFlyer. Meskipun tidak, Anda mungkin ingin tahu apakah Anda benar-benar memerlukan SDK Facebook selain SDK AppsFlyer. Dan jika Anda ingin tahu, dapatkah keduanya tetap ada tanpa adanya duplikasi laporan?

Aplikasi Anda tidak memerlukan SDK Facebook untuk hal berikut:

* **Akuisisi pengguna**: Umumnya, SDK AppsFlyer menangani semua tujuan atribusi akuisisi pengguna seluler dari pengguna Meta ads Anda, termasuk interaksi, penginstalan, sesi, dan event setelah penginstalan.
* **Deep linking:** Untuk membuka aplikasi ketika tautan tersebut diklik dan pengguna menautkan langsung (deep link) ke halaman tertentu atau kegiatan di aplikasi, Anda dapat menggunakan Onelink, tanpa Facebook SDK. Anda dapat menggunakan Tautan Universal iOS, Tautan Aplikasi Android, dan skema URI untuk melakukannya. Untuk informasi selengkapnya, lihat <Anchor target="_blank" href="https://www.facebook.com/business/help/1627795160837067?id=1858550721111595">pusat bantuan Meta</Anchor>.  

  **Catatan:**   
  Untuk iklan Statis (non-katalog), Tautan Universal iOS dan Tautan Aplikasi Android hanya didukung di kampanye tempat **Aplikasi** dipilih sebagai tujuan.  
  Misalnya, jika Anda menyiapkan kampanye kesadaran di Meta - karena kampanye ini tidak mengizinkan **Aplikasi** dipilih sebagai tujuan, Tautan Universal iOS dan Tautan Aplikasi Android tidak didukung.  

  Untuk iklan Dinamis, Tautan Universal iOS, Tautan Aplikasi Android, dan skema URI dapat digunakan sebagaimana diuraikan [di sini](/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads).  

  Iklan Meta menggores URL OneLink, dan menggunakannya untuk membuat Tautan Aplikasi Meta ads yang membuka aplikasi, dan menautkan dalam pengguna.

Aplikasi Anda memerlukan SDK Facebook selain SDK AppsFlyer untuk hal berikut:

* **Penautan langsung yang tertunda (DDL)**:  
  Saat ini, data DDL Meta ads hanya dapat diakses melalui <Anchor target="_blank" href="/marketers/id/docs/conversion-data-payloads-and-scenarios#data-konversi-ua-dengan-srn">Metode warisan data konversi</Anchor>. Untuk aplikasi iOS dan Android, SDK Facebook diperlukan agar data ini tersedia dalam metode data Konversi. Namun, hanya di Android dan Google Play, penautan langsung yang tertunda dapat dilakukan menggunakan  <Anchor target="_blank" href="/marketers/id/docs/meta-ads-integration-setup#how-to-get-userlevel-data-for-android-installs">mekanisme Perujuk Pemasangan Google</Anchor>.
* **Data kampanye Iklan Produk Dinamis** : Anda hanya bisa mendapatkan data untuk Iklan Produk Dinamis dari SDK Facebook.
* **Fitur Meta ads lainnya**: Anda mungkin memerlukan SDK Facebook untuk alasan yang tidak terkait dengan atribusi seperti autentikasi, monetisasi iklan, berbagi sosial, undangan pengguna, dll.

<div id="note-1" />

> 📘 **Catatan**
>
> Informasi dan rekomendasi di atas mengenai deep linking dan deferred deep linking didasarkan pada pengujian menyeluruh yang kami lakukan menggunakan alat demo/pratinjau Meta ads yang tersedia, yang menggunakan mekanisme berbeda dari iklan aktif.

</Accordion>

<div id="avoiding-duplicates-with-facebook-sdk" />

<Accordion title="Menghindari duplikasi dengan SDK Facebook">

Jika Anda memiliki <Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/faq#faq_593792547454717">SDK AppsFlyer dan Facebook di aplikasi Anda</Anchor>, penginstalan dan in-app event dilaporkan melalui SDK Facebook, lalu melalui postback ke server Meta ads melalui AppsFlyer. Bagaimana Anda menghindari pelaporan duplikat ini?

* **Untuk penginstalan**, Meta menghapus duplikat penginstalan. Ini berarti **tidak ada duplikasi** dan setiap penginstalan hanya dihitung satu kali.
* **Untuk In-app event**, Meta ads tidak menghilangkan duplikasi in-app event. Ini berarti Meta ads mungkin salah melaporkan in-app event rangkap. Untuk menghindari duplikasi seperti itu di Meta ads:
  * Jangan konfigurasikan event pada SDK Facebook
  * Untuk Android, nonaktifkan <Anchor target="_blank" href="/marketers/id/docs/meta-ads-in-app-event-mapping">pemetaan in-app event Meta ads</Anchor> dari AppsFlyer.  
    Perhatikan bahwa untuk mengaktifkan atribusi SKAN untuk iOS 14.5+, Anda harus <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-interoperation-with-meta-ads#in-app-event-mapping">memetakan in-app event ke Meta ads</Anchor>.

</Accordion>

<div id="meta-ads-attribution-faq" />

## FAQ atribusi Meta ads

<div id="attributing-agencies-with-facebook" />

<Accordion title="Mengatribusikan agensi dengan Meta ads">

Agensi dan mitra manajemen kampanye Meta dapat menjalankan dan mengaitkan kampanye Meta ads atas nama pemasang iklan di AppsFlyer, atau bahkan bersama dengan kampanye Meta ads milik pemasang iklan. Agar kampanye agensi diatribusikan ke agensi, nama kampanye HARUS diawali dengan nama agensi.

Perhatikan bahwa untuk pengguna iOS 14, hanya **satu** agensi yang dapat menjalankan kampanye untuk akun iklan tertentu. Lihat selengkapnya tentang <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-interoperation-with-meta-ads#skan-interoperability-appsflyer---meta-ads">interoperabilitas Meta ads dan SKAdNetwork AppsFlyer</Anchor>.

Untuk detail lebih lanjut tentang agensi dan atribusi penginstalan Meta ads, silakan <Anchor target="_blank" href="/partners/id/docs/about-agency-accounts#konfigurasi-srn">buka di sini</Anchor>.

Selain itu, **biro iklan tidak dapat mengubah jendela lookback Meta ads dan kontrol penargetan ulang**. Sebaliknya, mereka perlu meminta pemasang iklan untuk melakukan perubahan ini jika diperlukan.

Selain itu, agensi tidak dapat mengubah postback in-app event apa pun yang dikirim ke Meta ads. Alasannya adalah persyaratan Meta ads untuk menerima informasi tentang semua penginstalan, termasuk yang tidak dikaitkan dengannya (dan karenanya tidak boleh dibawa oleh agensi).

Gambar di bawah menunjukkan semua setelan yang perlu dikonfigurasi oleh pemasang iklan agar agensi dapat mengelola kampanye Meta ads-nya:

[![advertiser-vs-agency-facebook-int-new.png](https://files.readme.io/c07ed13221c23223f99442a52a643004447361f1a7b48c2a2735507039ef350c-14238179231377.png)](https://files.readme.io/c07ed13221c23223f99442a52a643004447361f1a7b48c2a2735507039ef350c-14238179231377.png)

</Accordion>

<div id="attribution-for-facebook-for-outofstore-android-apps" />

<Accordion title="Atribusi untuk Meta ads untuk aplikasi Android di luar toko">

Meta ads tidak mengizinkan pembuatan kampanye penginstalan aplikasi seluler untuk aplikasi Android yang ada di pasar luar toko, misalnya, Baidu.

Namun, Anda dapat mengiklankan dan mencatat penginstalan untuk aplikasi di luar toko di Meta ads dengan mengikuti petunjuk berikut:

1. Developer harus menyiapkan APK terpisah untuk setiap app store yang Anda gunakan untuk mengiklankan aplikasi. <Anchor target="_blank" href="/marketers/id/docs/set-up-multi-store-android-attribution">Detail selengkapnya di sini</Anchor>.
2. Buat kampanye **Lalu Lintas** atau **Konversi** di Meta ads, dengan mengaktifkan atribusi seluler, yang mengirimkan prospek ke halaman awal.
3. Laman arahan harus menyertakan tombol **Unduh Aplikasi** , yang langsung menautkan ke pasar aplikasi out-of-store di mana APK ada.
4. Prospek mengeklik tombol dan dialihkan ke pasar di luar toko. Setelah menyelesaikan penginstalan, AppsFlyer mengatribusikan pengguna ke Meta ads, melalui API MMP-nya.

<div id="note-2" />

> 📘 **Catatan**
>
> Solusi yang sama berlaku untuk aplikasi di Google Play dan App store, yang <Anchor target="_blank" href="/marketers/id/docs/set-up-smart-script-to-convert-web-visitors#facebook-click-id">membutuhkan laman arahan</Anchor> sebelum pengalihan ke pasar.

Untuk instruksi khusus tentang pengaitan untuk aplikasi di Amazon, klik <Anchor target="_blank" href="/marketers/id/docs/set-up-multi-store-android-attribution#driving-users-to-the-amazon-app-store-from-facebook">di sini</Anchor>.

</Accordion>

<div id="what-is-facebook-android-and-ios-crossattribution" />

<Accordion title="Apa yang dimaksud dengan atribusi silang Meta ads Android dan iOS?">

Meta ads mengidentifikasi pengguna berdasarkan akun Meta ads mereka. Beberapa pengguna memiliki perangkat iOS dan Android yang diasosiasikan dengan akun Meta ads yang sama.

Jika pengguna tersebut mengeklik atau melihat iklan untuk aplikasi Anda di perangkat Android mereka, tetapi menginstal aplikasi tersebut di perangkat iOS mereka, Meta ads menganggap diri mereka telah menghasilkan penginstalan. Akibatnya, nama Kampanye Android muncul di dashboard iOS Anda.

<div id="example" />

> 📄 **Contoh**
>
> Andrew Josef sedang sibuk di perangkat Androidnya. Saat menggunakannya, dia mengeklik iklan kampanye Android Meta untuk aplikasi bernama **Bubbles**. Dia tidak mengunduh aplikasi tersebut.
>
> Sehari kemudian, Andrew Josef memutuskan untuk mengunduh aplikasi **Bubbles** secara organik di perangkat iOS-nya dan meluncurkannya.
>
> Dalam situasi ini, atribusi AppsFlyer mengambil kampanye Meta ads Android dari Meta ads dan menampilkannya di Dashboard iOS tempat Andrew Josef mengunduh dan meluncurkannya.

</Accordion>

<div id="what-are-facebook-ads-channels" />

<Accordion title="Apa itu kanal iklan Meta?">

Dengan Meta ads, Anda dapat melihat data dipecah tidak hanya menurut kampanye, ad set, dan iklan, tetapi juga menurut kanal iklan Meta (disebut Penempatan):

* **Facebook** - pengguna dari aplikasi Facebook
* **Instagram** - user dari app Instagram
* **Messenger** - user dari app Facebook Messenger
* **AudienceNetwork** - pengguna dari aplikasi lain yang merupakan milik atau berafiliasi dengan Meta ads

Gunakan data ini untuk membandingkan kualitas pengguna yang Anda dapatkan dari berbagai saluran.

![Facebook_channels.png](https://files.readme.io/f6b51baf3056f42ee32ac9709b1e4b3661580ce6148acfa36fc2bad102e7bfd8-4411036713745.png)

</Accordion>

<div data-zendesk-anchors="facebook-ads-faq=faq-iklan-meta h_01HD1JTW2EP1MY3DD9136E9CHC=faq-iklan-meta h_01HD1JTW2EN36V9SHH11283Y3A=i-dont-see-facebook-campaign-clicks-in-appsflyers-dashboard h_01HD1JTW2EJQHKVJF4XHWGVASJ=can-i-stop-cost-data-sync h_01HD1JTW2EJE0K034KSV8B3WZQ=can-appsflyer-show-the-campaign-level-and-ad-groups h_01HD1JTW2EFKCJMNBXBK2C55DN=is-facebook-data-shown-in-realtime h_01HD1JTW2E4SVC1Z9C3K6XJB2G=when-can-i-see-a-new-campaigns-data-on-appsflyer h_01HD1JTW2ECWSXFKQC1YBP1592=how-can-i-get-more-installs-from-facebook h_01HD1JTW2ED762B3K1QS6QC38M=do-you-make-facebook-raw-data-available-to-agencies h_01HD1JTW2EWQGK4QA9W8DFZTMH=i-dont-see-facebook-raw-data-in-the-installation-and-inapp-events-reports h_01HD1JTW2EYSBJ38WNS1HP5MCE=any-specific-columns-for-facebook-in-appsflyers-performance-reports h_01HD1JTW2ETTXQAP7ZSTMVGA8K=can-i-work-with-facebook-fmps-and-measure-performance-with-appsflyer h_01HD1JTW2EPY8W5Z84PBWSM86G=what-should-i-do-when-i-receive-the-following-warning h_01HD1JTW2ED2DNPTXAFYJTTGV3=what-happens-with-different-lookback-windows-than-on-facebook h_01HD1JTW2EXF1R0MA91ZSW7QG4=what-are-the-facebook-api-parameters how-long-do-you-keep-facebook%E2%80%99s-userlevel-data=how-long-do-you-keep-facebook-s-userlevel-data h_01HD1JTW2EPDNSY30J45JB443A=how-long-do-you-keep-facebook-s-userlevel-data h_01HD1JTW2EN8THFCRNZ0EBQ2M3=are-ios-universal-links-and-android-app-links-supported-in-meta-ads h_01HD1JTW2ETG739TWQVTKPCM2R=can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads facebook-ads-cost-faq=faq-biaya-meta-ads h_01HD1JTW2EEVD1PDPFW15K45CE=faq-biaya-meta-ads h_01HD1JTW2EE0WQ90J431Z8NQ8Q=getting-facebook-cost-data-in-the-appsflyer-dashboard h_01HD1JTW2ESVMMPK32W34PA54T=facebook-cost-example h_01HD1JTW2EVFXAET26WK2KSHTV=i-cant-see-old-facebook-cost-data-in-the-appsflyer-dashboard h_01HD1JTW2EYJTA2TRY7EE75KXA=cost-data-was-fine-for-a-few-months-but-it-stopped-displaying h_01HD1JTW2EYXZW2QCMQH5CRFSK=i-clicked-on-my-facebook-ad-5-minutes-ago-why-dont-i-see-the-click-in-appsflyer h_01HD1JTW2EYE2ZDNVRT5BCRXZJ=can-i-get-raw-data-on-clicks-and-impressions-from-facebook h_01HD1JTW2EG11RRBYHJ5BMJM5M=are-there-limitations-of-facebook-cost-data-by-geo h_01HD1JTW2E3RMV2TMPNZZ86HG5=what-are-the-limitations-of-facebook-cost-data-in-master-api h_01HD1JTW2EKVSAQ3706NC8JV9M=the-total-cost-doesnt-match h_01HD1JTW2EMJQJHBBB9SRJ6MZN=why-is-the-appsflyer-calculation-for-ecpi-different-from-the-cost-calculated-by-facebook-while-the-total-cost-is-identical h_01HD1JTW2E2S79FC9VAHA12X93=why-doesnt-cost-data-include-data-from-all-campaigns h_01HD1JTW2ET6Y2EHG29AQS09NA=is-facebook-cost-data-displayed-for-retargeting-campaigns h_01HD1JTW2EXTS1GDZHN8PAMV8C=why-does-the-facebook-cost-configuration-window-close-before-login h_01HD1JTW2FC0NJK00HZ76SFH30=why-is-there-a-discrepancy-in-cost-data-for-apps-in-the-amazon-app-store how-to-connect-cost-data-of%C2%A0a-new-facebook-ad-account-while-my-old-account-is-linked=how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked h_01HD1JTW2F401DA2NHBSPTKATB=how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked facebook-ads-sdk-faq=faq-sdk-facebook h_01HD1JTW2FPRCVGBF7CG7ZMKXF=faq-sdk-facebook h_01HD1JTW2F03XQSEVTFBW8JCX3=who-needs-facebooks-sdk h_01HD1JTW2FB09HM2CC83GMT901=catatan h_01HD1JTW2FNNHPZQARZNCCP7ER=avoiding-duplicates-with-facebook-sdk facebook-ads-attribution-faq=faq-atribusi-meta-ads h_01HD1JTW2F2JV2BMDS40HFG6K0=faq-atribusi-meta-ads h_01HD1JTW2FK1ZTPTA8B8A4N64Z=attributing-agencies-with-facebook h_01HD1JTW2F63AT1NGBY96Y6CCE=attribution-for-facebook-for-outofstore-android-apps h_01HD1JTW2FMKYDHNSM7G182EY0=catatan-1 h_01HD1JTW2F8JT69CSN04GCZ91V=what-is-facebook-android-and-ios-crossattribution h_01HD1JTW2F5PY7A8T5NMHBZ87B=contoh h_01HD1JTW2FX3QWC9BKWQ65E5B8=what-are-facebook-ads-channels" />
