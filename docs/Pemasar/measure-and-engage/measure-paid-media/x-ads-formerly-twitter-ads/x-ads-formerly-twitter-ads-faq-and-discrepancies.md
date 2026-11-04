---
title: Panduan pengaturan X Ads (sebelumnya Twitter Ads)—FAQ dan perbedaan
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:34:59Z'
  edited_at: '2023-11-24T13:19:02Z'
  id: 4410464352017
  locale: id
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/id/articles/4410464352017
---
> **Sekilas:** Selesaikan FAQ X Ads dan pahami perbedaannya.

<div id="x-ads-faq-and-discrepancies" />

## FAQ X Iklan dan perbedaannya

<div id="who-can-perform-the-twitter-setup-on-appsflyer" />

<Accordion title="Siapa yang dapat melakukan pengaturan di AppsFlyer?">

Pengguna yang mengizinkan integrasi antara AppsFlyer dan Twitter harus memiliki akses Administrator Akun Twitter.

</Accordion>

<div id="what-happens-if-no-twitter-accounts-are-selected-for-attributing-on-appsflyer" />

<Accordion title="Apa yang terjadi jika tidak ada akun Twitter yang dipilih untuk diatribusikan di AppsFlyer?">

Semua atribusi ditujukan untuk kampanye di akun yang dipilih. Jika tidak ada akun yang dipilih, tidak ada in-app event atau atribusi yang dikirim ke Twitter, bahkan jika in-app event mapping masih terlihat di jendela Konfigurasi Twitter.

</Accordion>

<div id="do-the-account-owner-and-the-team-members-see-the-same-twitter-data" />

<Accordion title="Apakah pemilik akun dan anggota tim melihat data Twitter yang sama?">

Tidak. Pemilik akun melihat semua akun Twitter yang terhubung. Anggota tim hanya melihat akun Twitter mereka yang terhubung.

</Accordion>

<div id="how-do-i-disconnect-twitter-from-appsflyer" />

<Accordion title="Bagaimana cara memutus koneksi Twitter dari AppsFlyer?">

Anda dapat memutus koneksi AppsFlyer dari akun Twitter Anda. Instruksi berikut mengasumsikan bahwa Anda login ke akun Twitter menggunakan browser desktop atau laptop:

1. Login ke Twitter.
2. Di menu sebelah kiri, klik **Lainnya** > **Pengaturan dan Privasi**.
3. Buka **Keamanan dan akses akun** > **Aplikasi dan sesi** > **Aplikasi yang terhubung**.
4. Klik AppsFlyer.
5. Klik **Revoke Access (Cabut Akses)** .

Anda sekarang dapat kembali ke akun AppsFlyer Anda dan <Anchor target="_blank" href="/marketers/id/docs/x-ads-formerly-twitter-ads-integration-setup">menghubungkan akun Twitter lain</Anchor> jika Anda mau.

</Accordion>

<div id="is-it-possible-to-attribute-installs-to-multiple-twitter-accounts" />

<Accordion title="Apakah mungkin untuk mengatribusikan penginstalan ke beberapa akun Twitter?">

Ya, tapi ini memerlukan beberapa tindakan di Twitter. Tetapi pertama-tama diperlukan beberapa latar belakang:

Anda **hanya dapat menghubungkan satu nama pengguna** (juga dikenal sebagai pengguna Twitter) ke akun AppsFlyer Anda. Saat Anda menghubungkan nama pengguna ini, Akun X Ads Anda akan muncul di konfigurasi Twitter di dashboard AppsFlyer.

Jika salah satu anggota tim Anda juga memiliki Akun X Ads, ini berarti mereka memiliki nama pengguna yang berbeda dari Anda dan tidak dapat menghubungkan nama pengguna mereka ke AppsFlyer. Hal ini karena **nama pengguna Anda adalah nama yang sudah terhubung dengan akun AppsFlyer**. Agar Akun X Ads mereka juga muncul di AppsFlyer, mereka perlu **memberikan nama pengguna Anda akses sebagai administrator akun ke Akun X Ads mereka**.

Misalkan anggota tim Anda adalah Jenny dan nama penggunanya adalah @jenny. Nama pengguna Anda adalah @nivi dan merupakan nama pengguna yang terhubung ke AppsFlyer. Agar Akun X Ads miliknya muncul di akun AppsFlyer, **dia perlu memberikan nama pengguna Anda akses sebagai administrator akun ke Akun X Ads miliknya**. Jenny perlu memberikan akses ke Nivi untuk Akun X Ads miliknya dan bukan sebaliknya. Ketika ia melakukannya, AppsFlyer melihat pegangan Nivi, dan melihat semua akun iklan terkait dengannya, termasuk Jenny.

1. Jenny login ke <Anchor target="_blank" href="http://ads.twitter.com/">ads.twitter.com</Anchor>
2. Dia mengklik **Akun** dan kemudian memilih **Edit akses ke akun**  

   ![twitter_assign_account2.PNG](https://support.appsflyer.com/hc/article_attachments/4416810336785)
3. Jenny kemudian memberikan @nivi akses ke Akun X Ads miliknya sebagai atau Administrator akun  

   [![twitter_edit_access_to_account.png](https://support.appsflyer.com/hc/article_attachments/4416810307601/twitter_edit_access_to_account.png)](https://support.appsflyer.com/hc/article_attachments/360002514658/twitter_edit_access_to_account.png)
4. Jenny masuk ke akun AppsFlyer dan masuk ke Integrasi Aktif >> opsi Twitter
5. Pada tahap ini, dia dapat melihat Akun X Ads miliknya juga terdaftar.
6. Dia sekarang dapat melihat akun X Ads-nya dan mengonfigurasi integrasi. Admin akun dapat melihat semua akun X Ads yang terhubung.  

   Tampilan yang dilihat Jenny:

   ![jennys_ads_account.png](https://support.appsflyer.com/hc/article_attachments/4416824257041)

   Tampilan admin akun:

   ![jennys_ads_account__1_.png](https://support.appsflyer.com/hc/article_attachments/4416833416337)

</Accordion>

<div id="any-special-instructions-for-agencies" />

<Accordion title="Ada instruksi khusus untuk agensi?">

Ya.  
 Saat agensi membuat kampanye Twitter baru, nama kampanye harus dimulai dengan nama agensi dan garis bawah (Contoh: "AgencyName\_Campaign1").

<div id="note" />

> 📘 **Catatan**
>
> Untuk membangun koneksi antara AppsFlyer dan Twitter, pemasang iklan HARUS mengonfigurasi Twitter untuk mengizinkan agensi menjalankan lalu lintas Twitter.

Untuk detail selengkapnya, lihat <Anchor target="_blank" href="/partners/id/docs/about-agency-accounts#konfigurasi-srn">di sini</Anchor>.

</Accordion>

<div id="do-you-make-twitters-raw-data-available-to-agencies" />

<Accordion title="Apakah data lengkap Twitter tersedia untuk agensi?">

Kami tidak memberikan data lengkap Twitter kepada agensi karena ketentuan layanan mereka menganggap agensi sebagai pihak ketiga.

</Accordion>

<div id="im-clicking-save-close-but-twitters-configuration-is-not-saved-help" />

<Accordion title="Saya mengeklik simpan & tutup, namun konfigurasi Twitter tidak disimpan! Mohon bantuannya!">

Jika aplikasi Anda telah berlangganan ke penyedia atribusi lain sebelumnya, yang digunakan untuk mengatribusikan penginstalan Twitter, terjadi kesalahan berikut saat mengonfigurasi Twitter di dashboard AppsFlyer:

**Kesalahan: Aplikasi terkait dengan penyedia atribusi lain Harap kaitkan dengan AppsFlyer.**

Selain itu, kesalahan berikut mungkin juga muncul:  

[![](https://support.appsflyer.com/hc/article_attachments/360001502209/X%20Ads_error_2.png)](https://support.appsflyer.com/hc/article_attachments/360001502209/X%20Ads_error_2.png)

**Kesalahan: Terjadi kesalahan saat menyimpan konfigurasi Twitter. Beberapa akun gagal diperbarui: XX Beberapa ID penyedia ke (appid, conversionType) sama untuk event appid2872.**

Jika pilihan akun tidak disimpan, ini mungkin karena akun Twitter yang dipermasalahkan sebelumnya terkait dengan penyedia lain di Twitter. Untuk mengatasi hal ini:

* Hubungi Twitter untuk menghapus penyedia lain dari sisi Anda
* Pilih nama Akun Aktif
* Klik **Save and Close (Simpan dan Tutup)** .
* Jika ini masih tidak menyelesaikan masalah, Anda harus menghubungi penyedia pengukuran sebelumnya dan memintanya untuk menghapus tag Twitter lama yang terkait dengan akun Anda.

</Accordion>

<div id="how-can-i-set-up-retargeting-campaigns-with-twitter" />

<Accordion title="Bagaimana saya bisa mengatur kampanye penargetan ulang dengan Twitter?">

Untuk detail tentang cara mengonfigurasi Kampanye Penargetan Ulang Twitter, klik di sini.

</Accordion>

<div id="does-retargeting-affect-inapp-events-sending-to-twitter" />

<Accordion title="Apakah penargetan ulang memengaruhi pengiriman in-app event ke Twitter?">

Ya. Jika penargetan ulang diaktifkan, AppsFlyer tidak mengirim postback event af\_app\_opened ke Twitter, sesuai permintaan Twitter.  
Perhatikan bahwa meskipun jendela pengaturan Twitter mengizinkan pemilihan ini, postback af\_app\_opened tidak dikirim dengan penargetan ulang.

</Accordion>

<div id="how-can-i-stop-measuring-twitter-attributions" />

<Accordion title="Bagaimana saya bisa berhenti mengukur atribusi Twitter?">

Untuk menonaktifkan integrasi dengan Twitter, hapus centang semua akun dan klik **Simpan & Tutup** .

</Accordion>

<div id="can-an-agency-measure-twitter-attributions-for-advertisers" />

<Accordion title="Dapatkah agensi mengukur atribusi Twitter untuk pemasang iklan?">

Ya!  
 Untuk membuat koneksi antara AppsFlyer dan Twitter, pemasang iklan HARUS memilih akun aktif di halaman mitra Twitter di dashboard AppsFlyer, jadi setidaknya satu akun Twitter dicentang.  
Setelah itu, agensi perlu menghubungkan akun Twitter-nya langsung dari dashboard agensinya sendiri.

</Accordion>

<div id="can-an-agency-configure-inapp-events-for-twitter" />

<Accordion title="Bisakah agensi mengonfigurasi in-app event untuk Twitter?">

Agensi tidak dapat mengonfigurasi in-app event untuk Twitter. Mirip dengan Meta ads, ini harus dikonfigurasi oleh Pemasang Iklan.

</Accordion>

<div id="for-how-long-do-you-keep-twitter-s-userlevel-data" />

<Accordion title="Berapa lama Anda menyimpan data tingkat pengguna Twitter?">

Twitter mewajibkan penyedia atribusi untuk menghapus data tingkat penggunanya 3 bulan setelah penginstalan. Ini berarti bahwa event yang dilakukan oleh pengguna 6 bulan setelah mereka meng-install aplikasi dianggap sebagai organik.

Data agregat sebelumnya tetap sama.

</Accordion>

<div id="why-do-i-see-duplicated-cost-data" />

<Accordion title="Mengapa saya melihat data biaya duplikat?">

Saat Anda mengatur kampanye di Twitter, Anda dapat menambahkan beberapa aplikasi ke kampanye. Saat Twitter melaporkan biaya, total data biaya kampanye ditampilkan di bawah setiap aplikasi di AppsFlyer, dan tidak dibagi per aplikasi.

Misalnya, jika Anda menjalankan satu kampanye dengan biaya $1.000 untuk aplikasi Android dan iOS, maka biaya $1.000 ditampilkan di dashboard AppsFlyer di bawah aplikasi Android dan iOS. Biayanya tidak dibagi, misalnya, masing-masing menjadi $500.

Untuk menghindari duplikasi biaya, Anda disarankan untuk menetapkan hanya satu aplikasi per item baris/kampanye.

</Accordion>

<div id="im-trying-to-link-my-twitter-account-with-appsflyer-but-i-get-an-error-message" />

<Accordion title="Saya mencoba menghubungkan akun Twitter saya dengan AppsFlyer, tetapi saya mendapatkan pesan kesalahan">

Akun Twitter Anda harus menjadi Akun Iklan aktif untuk menerima data atribusi dari AppsFlyer.

**Untuk mengatasi masalah ini:**

1. Keluar dari Twitter.
2. Buka **Integrasi Aktif**.
3. di **Bidang Pencarian,** ketik "Twitter"
4. Klik pada ikon Twitter,  
    jendela pengaturan mitra terbuka.
5. Di tab **Integrasi**, klik **Aktifkan mitra** .
6. Klik **Login with Twitter**,  
   jendela login Twitter terbuka.
7. Masuk dengan Akun X Ads Anda.

</Accordion>

<div id="discrepancies-between-x-ads-and-appsflyer" />

## Perbedaan antara Twitter dan AppsFlyer

Meskipun kami bekerja sama dengan Twitter, perbedaan mungkin muncul antara dasbor Twitter dan dashboard/laporan AppsFlyer.

Berikut adalah alasan umum perbedaan yang harus diperhatikan pemasang iklan:

| Penyebab | Twitter | AppsFlyer |
| --- | --- | --- |
| **Periode Waktu Atribusi** | Twitter memungkinkan penggunanya untuk mengonfigurasi jendela atribusi dan mendukung atribusi klik-tayang dan lihat-tayang. Secara default - klik-tayang 14 hari dan lihat-tayang 1 hari. | Jika Anda belum mengonfigurasi jendela lihat balik atribusi AppsFlyer untuk Twitter dengan nilai yang sama seperti di Twitter, perbedaan dapat terjadi. |
| **Atribusi Sumber Multi Channel** | Atribusi Twitter berfungsi seperti yang ditentukan di atas terlepas dari sumber lainnya. | AppsFlyer menggunakan atribusi klik terakhir (informasi lebih lanjut tentang atribusi AppsFlyer dapat dilihat di <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model">sini</Anchor>). |
| **Perbedaan zona waktu** | Zona waktu Twitter ditentukan oleh zona waktu yang dikonfigurasi aplikasi pemasang iklan. | Zona waktu default AppsFlyer adalah UTC ± 00: 00, tetapi dapat diatur ke zona waktu mana pun oleh pengiklan. |
| **Instal perbedaan waktu** | Twitter menunjukkan penginstalan berdasarkan waktu klik (disebut sebagai "waktu interaksi"). | AppsFlyer menampilkan waktu pembukaan aplikasi pertama. |
| **Jenis sentuhan atribusi** | Atribusi Twitter didasarkan pada klik dan tayangan mereka sendiri. | AppsFlyer memprioritaskan atribusi klik-tayang daripada atribusi lihat-tayang. Jika Twitter menghitung sebuah tayangan dan AppsFlyer mengetahui adanya klik tambahan dalam jendela atribusi klik-tayang, klik dari sumber lain akan diatribusikan di dashboard AppsFlyer. Di Twitter, tayangan tersebut diatribusikan dan ditampilkan di dasbor mereka. |
| **Pengaturan berbagi data Twitter** | Twitter mengizinkan penggunanya untuk TIDAK <Anchor target="_blank" href="https://twitter.com/settings/account/personalization">membagikan data pribadi mereka dengan pihak ketiga</Anchor> . Data ini termasuk iklan yang berinteraksi dengan mereka.<br /><br />Statistik di dashboard Twitter mencerminkan semua interaksi, termasuk pengguna yang memilih untuk tidak membagikan data. | AppsFlyer menampilkan data agregat pengguna Twitter ini, namun tidak melaporkan data lengkap tingkat pengguna mereka ( <Anchor target="_blank" href="/marketers/id/docs/x-ads-formerly-twitter-ads-setup-guide-overview#privasi-pengguna-x-ads">detail</Anchor> lebih lanjut). |
| **Logika interaksi ulang Twitter** | Twitter menghitung pengguna unik. Jika pengguna berinteraksi ulang lebih dari sekali sebagai hasil dari kampanye yang sama, Twitter menampilkan interaksi ini sebagai satu konversi. | AppsFlyer menghitung setiap instance re-engagement (interaksi ulang), dan oleh karena itu, dalam kasus serupa, menampilkan interaksi ini sebagai beberapa konversi. |

<div id="note-1" />

> 📘 **Catatan**
>
> Dampak dari <Anchor target="_blank" href="/marketers/id/docs/implement-validation-rules-to-prevent-fraud">AppsFlyer's Validation Rules (Aturan Validasi AppsFlyer)</Anchor> , hasilnya mungkin berbeda di dashboard karena beberapa penginstalan ditampilkan di Twitter dan tidak ditampilkan di dashboard AppsFlyer.

<div data-zendesk-anchors="twitter-ads-faq-and-discrepancies=faq-x-iklan-dan-perbedaannya h_01HE7S15F9YR28FBA1TYCE3N0X=faq-x-iklan-dan-perbedaannya h_01HE7S15F9NSQJSP268B0WF0JP=who-can-perform-the-twitter-setup-on-appsflyer h_01HE7S15F9PFZ8CATJC5YWC6QP=what-happens-if-no-twitter-accounts-are-selected-for-attributing-on-appsflyer h_01HE7S15F989Y94YFJ7TGK7QN5=do-the-account-owner-and-the-team-members-see-the-same-twitter-data h_01HE7S15F9GNWTK2N50GAHN52Q=how-do-i-disconnect-twitter-from-appsflyer h_01HE7S15F9CE4F29R97EVCG791=is-it-possible-to-attribute-installs-to-multiple-twitter-accounts h_01HE7S15F9G4M44CB2Q1KQMJPJ=any-special-instructions-for-agencies h_01HE7S15F9VG8XMJE7YSNN245P=catatan h_01HE7S15F9A7BBAW8BNN6H4AKQ=do-you-make-twitters-raw-data-available-to-agencies h_01HE7S15F9MM26SGKMAPGDH9F8=im-clicking-save-close-but-twitters-configuration-is-not-saved-help h_01HE7S15F923NKTTCS3Z1C40B5=how-can-i-set-up-retargeting-campaigns-with-twitter h_01HE7S15F931EWS48QVCQYPBCH=does-retargeting-affect-inapp-events-sending-to-twitter h_01HE7S15F98VN1TS99751S34C5=how-can-i-stop-measuring-twitter-attributions h_01HE7S15F9MEKBKAQ3NA76TFKY=can-an-agency-measure-twitter-attributions-for-advertisers h_01HE7S15F921V3T885F39VSPCQ=can-an-agency-configure-inapp-events-for-twitter for-how-long-do-you-keep-twitter%E2%80%99s-userlevel-data=for-how-long-do-you-keep-twitter-s-userlevel-data h_01HE7S15F90RXSWJ7HV3GSJB65=for-how-long-do-you-keep-twitter-s-userlevel-data h_01HE7S15F9B39KV628NSD29P6P=why-do-i-see-duplicated-cost-data h_01HE7S15F9N3CCJEMAD2QB38F9=im-trying-to-link-my-twitter-account-with-appsflyer-but-i-get-an-error-message discrepancies-between-twitter-and-appsflyer=perbedaan-antara-twitter-dan-appsflyer h_01HE7S15F9YWCY883DP9TEGQXK=perbedaan-antara-twitter-dan-appsflyer h_01HE7S15FAPS2696J3KQG3P3ME=catatan-1" />
