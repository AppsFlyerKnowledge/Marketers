---
title: Google Ads (AdWords)—biaya dan pendapatan iklan
metadata:
  keywords:
    - Advertisers
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-01-20T10:01:42Z'
  edited_at: '2023-10-27T14:54:32Z'
  id: 4417309205521
  locale: id
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/id/articles/4417309205521
---
> **Sekilas:** Aktifkan data biaya dan pendapatan iklan Google Ads di AppsFlyer.

## Status Sinkronisasi Data Biaya

<Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Lihat status API biaya</Anchor> dan terakhir kali AppsFlyer berhasil menarik data biaya yang cocok di dashboard status integrasi biaya (dan pendapatan iklan), atau di dashboard jaringan iklan individual. 

Google Ads memungkinkan Anda untuk melakukan sinkronisasi beberapa akun untuk mengambil data biaya. Untuk setiap akun yang disinkron, AppsFlyer menampilkan status integrasi biaya dan kali terakhir AppsFlyer berusaha mengambil data biaya yang cocok.

### Menonaktifkan sinkronisasi biaya Google

**Untuk berhenti menyinkronkan biaya Google, hapus koneksi akun Google:**

* <Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">Buka tab biaya, di kolom tindakan, arahkan kursor ke akun, klik Hapus koneksi.</Anchor> Setelah dihapus, AppsFlyer berhenti menerima biayanya. Menghapus koneksi tidak memengaruhi data historis.

## Biaya, Klik, dan Impresi

Integrasi biaya menyediakan data teragregasi berikut ini:

* Data biaya untuk kampanye, iklan, geo/negara, dan tingkat kanal Anda. Lihat <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabel integrasi biaya jaringan iklan</Anchor> untuk detail lengkap tentang dimensi, metrik, dan fitur yang didukung.  
  **Catatan:** Data biaya memerlukan langganan <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor> .
* Data klik, tayangan, dan data yang diperkaya (kata kunci, nama kampanye, dan adset).

> 📘 **Catatan**
>
> * Akun MCC didukung.
> * Data biaya, klik, dan tayangan saat ini tidak tersedia untuk kampanye prapendaftaran karena keterbatasan di Google Ads API.

Untuk melihat data biaya, klik, dan impresi Google Ads di dashboard AppsFlyer, hubungkan via halaman konfigurasi Google Ads. Setelah penyambungan selesai, AppsFlyer akan mulai meng-kueri jumlah biaya, klik, dan impresi Google Ads untuk semua kampanye yang ada.

Baca selengkapnya tentang <Anchor target="_blank" href="/marketers/id/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">mengatur biaya di Google Ads</Anchor>.

Baca selengkapnya tentang cara Google mendefinisikan klik dan tampilan.

Baca selengkapnya tentang <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6163740">batasan Google Ads</Anchor>.

**Setelah pengaturan, data akan masuk dalam beberapa jam**.

> 👍 **Tips**
>
> User dapat mengonfirmasi bahwa mereka telah login menggunakan akun Google Ads yang tepat dengan cara memeriksa alamat email yang terlihat di pojok kanan atas dashboard Google Ads.
>
> ![short.png](https://support.appsflyer.com/hc/article_attachments/4417297915537)
>  Jika akun Google Ads tersebut adalah sub-akun dari akun MCC, maka ID MCC berada di kanan atas,  dan ID sub-akun berada di pojok kiri atas.
>
> Jika akun yang digunakan salah, logout dari akun, lalu login kembali menggunakan alamat email untuk akun Google yang berbeda.

## Mencatat pendapatan iklan dengan Google Ads

Integrasi pendapatan Google Ads (AdWords) telah dihentikan mulai 30 November 2020. Untuk data pendapatan iklan, pengguna AdWords harus bermigrasi ke <Anchor target="_blank" href="/marketers/id/docs/google-admob-ad-revenue-attribution-configuration">Google AdMob</Anchor>.

<div id="faq" />

<Accordion title="Pertanyaan Umum">

| **Mengapa saya tidak melihat Data Cost?**<br /><br />Ada beberapa kemungkinan alasan mengapa Anda tidak melihat data:<ul><li>Saat masuk, penting untuk memverifikasi akun Google yang benar yang digunakan.<br />Jika Anda masuk menggunakan akun Google yang salah, tidak ada biaya yang ditarik atau ditampilkan. Dalam situasi seperti ini, Anda harus menghapus aplikasi dari izin aplikasi Google dan masuk dengan akun yang benar. Untuk melakukannya, ikuti langkah-langkah berikut:<ol><li>Klik URL ini: <Anchor target="_blank" href="https://myaccount.google.com/permissions">https://myaccount.google.com/permissions</Anchor></li><li>Hapus AppsFlyer Cost pada Google dan login kembali.</li></ol></li><li>Dalam beberapa kasus, integrasi biaya agensi diaktifkan namun tidak menarik biaya karena pengguna agensi yang masuk tidak memiliki akses ke ID pelanggan Google Ads yang benar. Hal ini mengakibatkan pemasang iklan melihat data biaya yang tidak lengkap.</li></ul>Pastikan pengguna biro iklan yang masuk ke tab Biaya memiliki akses ke ID pelanggan Google Ads yang diatur di tab Integrasi.<br /><br />[<Image alt="" src="https://support.appsflyer.com/hc/article_attachments/5991137319441" width="457px" />](https://support.appsflyer.com/hc/article_attachments/5991137319441)<ul><li>Penggunaan spasi atau karakter khusus pada kampanye Penelusuran iOS atau Halaman Tujuan Android dapat menyebabkan masalah pencocokan data biaya untuk data jumlah klik, dan menyebabkan pelaporan biaya tidak dapat ditemukan.</li><li>Bila biro iklan menonaktifkan integrasi biaya setelah biaya sudah dikumpulkan, namun pemasang iklan masih memiliki integrasi biaya aktif, data dikaitkan dengan pemasang iklan hanya sejak biro iklan menonaktifkan integrasi tersebut.</li></ul> |
| --- |
| **Di manakah data klik berbasis geografis saya?**<br /><br />Dalam beberapa kasus, AppsFlyer menerima sebagian data klik Lokasi dari Google. Jika hal ini terjadi, AppsFlyer akan melengkapi informasi klik yang tidak lengkap dari sumber Google lain, yang tidak memiliki data Lokasi. Jadi, saat mengelompokan berdasarkan Lokasi, jumlah total klik dari kampanye Google mungkin tidak cocok dengan angka yang sama dalam dimensi pengelompokan lain. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Sifat | Catatan |
| --- | --- |
| Kampanye tidak aktif dan aktif | Integrasi Google mendukung pelaporan biaya untuk **kampanye tidak aktif**, dalam kasus berikut:<ul><li>Kampanye aplikasi untuk penginstalan (jenis kampanye ACI)</li><li>Kampanye aplikasi untuk interaksi (jenis kampanye ACE)</li></ul>Kampanye tidak aktif adalah kampanye yang tidak mencatat instalasi dan konversi di AppsFlyer.<br /><br />Untuk kampanye non-ACI dan non-ACE, AppsFlyer hanya melaporkan biaya untuk **kampanye aktif** , artinya setidaknya satu konversi atau penginstalan dicatat di AppsFlyer. Biaya dilaporkan untuk jangka waktu 7 hari konversi/penginstalan. |

</Accordion>

> 📄 **Lihat juga**
>
> * Untuk pertimbangan terkait iOS 14, lihat <Anchor target="_blank" href="/marketers/id/docs/get-skan-postback-data-from-google-ads">Interoperabilitas SKAdNetwork Google Ads dengan AppsFlyer</Anchor>.

<div data-zendesk-anchors="cost-data-sync-status=status-sinkronisasi-data-biaya h_01HDP2SMHJT8Z6DP7BHC0Y5RRN=status-sinkronisasi-data-biaya stopping-google-cost-sync=menonaktifkan-sinkronisasi-biaya-google h_01HDP2SMHJPEDKKZF9SBXW56KG=menonaktifkan-sinkronisasi-biaya-google cost-clicks-and-impressions=biaya-klik-dan-impresi h_01HDP2SMHJ26S1BCER3KKZ8H14=biaya-klik-dan-impresi h_01HDP2SMHJB5YE5PCWVJVBAKHD=catatan h_01HDP2SMHJF86QK9CJTVABKTYW=tips recording-ad-revenue-with-google-ads=mencatat-pendapatan-iklan-dengan-google-ads h_01HDP2SMHKC9TSZZZPFFNK8TPH=mencatat-pendapatan-iklan-dengan-google-ads h_01HDP2SMHK8NH6M4T1A2Y79P55=faq h_01HDP2SMHKPDEE07H8WAP212TZ=traits-and-limitations h_01HDP2XBSEJVQ5G0MD0V5R05CM=lihat-juga" />
