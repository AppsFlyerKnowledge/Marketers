---
title: Pengaturan integrasi X Ads (sebelumnya Twitter Ads).
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
  created_at: '2021-11-09T09:33:40Z'
  edited_at: '2023-11-24T13:19:13Z'
  id: 4410472471825
  locale: id
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/id/articles/4410472471825
---
> **Sekilas:** Integrasikan akun X Ads Anda dengan AppsFlyer untuk menampilkan data atribusi kampanye X Ads.

<div id="note" />

<div id="connecting-your-x-ads-account-to-appsflyer" />

## Menghubungkan akun X Ads Anda ke AppsFlyer

<Accordion title="Tonton">

<Embed title="Pengaturan integrasi X Ads (sebelumnya Twitter Ads)." typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/a65pnqoyxw" providerUrl="https://fast.wistia.com" />

</Accordion>

<Accordion title="Baca">

> 📘 **Sebelum Anda memulai**
>
> Pastikan Anda telah <Anchor target="_blank" href="https://business.twitter.com/en/help/account-setup/billing-basics.html">menambahkan metode pembayaran</Anchor> ke akun X Ads Anda. Jika tidak, Anda tidak akan dapat mengaktifkan integrasi mitra di AppsFlyer.

1. Masuk ke Akun X Ads Anda di <Anchor target="_blank" href="https://ads.twitter.com">ads.twitter.com</Anchor>  
   Jika Anda tidak secara otomatis diarahkan ke halaman Ads, klik tombol Ads di pojok kiri atas.
2. Saat diminta untuk memilih kampanye **Sederhana (BARU)** atau **Lanjutan** , pilih **Lanjutan**.
3. Pada **Tujuan kampanye**, pilih **Penginstalan Aplikasi** atau **Interaksi ulang aplikasi**, lalu klik **Berikutnya**.  

   ![twitter-campaign-objective.png](https://files.readme.io/d91bd357dea4878f098086a573191f64c2d1a38af8a6a809c6de7c468e04e043-6148255768337.png)
4. Pilih aplikasi Anda, lalu klik tautan **mitra pengukuran seluler** .
5. Pada halaman **Pelacakan konversi** , klik **Buka AppsFlyer**.   

   ![twitter-mmp-selection.png](https://files.readme.io/ebe8e97971c01e0d87c694d2ca1fcc996abf608309d96badcbcda2713ab80d3e-6148393350033.png)
6. Sebuah notifikasi ditampilkan untuk menginformasikan bahwa Anda akan meninggalkan X Ads untuk mengunjungi situs web AppsFlyer. Klik **Buka AppsFlyer** dan masuk ke Dashboard Anda.  

   <Image alt="twitter-go-to-appsflyer.png" src="https://support.appsflyer.com/hc/article_attachments/4411046208401" width="576px" />
7. Di AppsFlyer, di bawah **Konfigurasi**, buka **Pasar Mitra**.
8. Cari **X Ads** dan pilih itu.
9. Dalam tab **Integrasi** , terima Syarat dan Ketentuan X Ads untuk Pencatatan Konversi Aplikasi Seluler (MACT), lalu klik **Simpan integrasi**.
10. Nyalakan **Aktifkan mitra**, dan klik **Masuk dengan X Ads**.
11. Otorisasi AppsFlyer untuk menggunakan akun X Ads Anda dengan mengeklik **Otorisasi aplikasi**.   

    [<Image alt="" src="https://support.appsflyer.com/hc/en-us/article_attachments/4411037924497/Twitter_Ads_6.png" width="476px" />](https://support.appsflyer.com/hc/id/article_attachments/4411037924497/Twitter_Ads_6.png)
12. Nyalakan kembali **Aktifkan Mitra** untuk menampilkan pengaturan tab **Integrasi** dan mengaktifkan atribusi.  
    **Catatan:** Sakelar harus tetap nyala (diaktifkan) selama Anda bekerja dengan mitra. Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">aktivasi mitra.</Anchor>
13. Pilih akun X Ads Anda untuk mengaktifkannya, lalu klik **Simpan & Tutup**.  

    ![twitter_account_name.png](https://support.appsflyer.com/hc/article_attachments/4411046818193)

</Accordion>

<div id="x-ads-attribution-setup" />

## Pengaturan atribusi X Ads

Untuk penjelasan rinci tentang Header halaman konfigurasi mitra, klik <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner">di sini</Anchor>.

<div id="integration-tab" />

<Accordion title="Tab Integration">

**Tab Integrasi** dibagi menjadi beberapa bagian, seperti yang dijelaskan di bawah. <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">Mitra harus diaktifkan</Anchor> pada kunjungan pertama untuk mengaktifkan pengaturannya.

<div id="note-1" />

<div id="advanced-privacy" />

<div id="ad-account-connected" />

### Akun iklan terhubung

Pilih akun untuk mengaktifkan atribusi.

![Twitter_msc_new_4.png](https://files.readme.io/c64dd5ddc51f35ce195c689b3d14ec4ed4010133662096926f4e8c45e48d60c4-4411049509137.png)

<div id="click-through-attribution" />

### Atribusi Click-Through

Gunakan slider untuk mengatur **waktu maksimal dari klik hingga penginstalan**. Hanya penginstalan (peluncuran pertama) yang berlangsung dalam jendela lihat-balik yang dapat diatribusikan ke X Ads.

Anda dapat menyesuaikan nilai ini ke 1-23 jam atau 1-30 hari. Kami merekomendasikan pengaturan jendela lihat balik klik-tayang menjadi 14 hari, agar selaras dengan X Ads.

![Twitter_msc_new_6.png](https://files.readme.io/39c3e080cf2fff3b7d9b3e2cf694fc439cd447a263b113ecfc6730a38f653283-4411047369361.png)

<div id="reinstall-settings" />

<div id="view-through-attribution-lookback-window" />

### Lookback Window Atribusi View-Through

Slider ini memungkinkan Anda untuk mengatur **waktu maksimal mulai dari tayangan hingga penginstalan**. Hanya penginstalan (peluncuran pertama) yang terjadi dalam jendela lihat balik ini, setelah tayangan iklan, yang diatribusikan ke X Ads, asalkan tidak ada klik iklan lain yang relevan.

Anda dapat mengkustomisasi nilai ini ke 1-23 jam atau 1-7 hari. Kami merekomendasikan pengaturan Jendela lihat balik lihat-tayang menjadi 1 hari, agar selaras dengan X Ads.

![Twitter_msc_new_7.png](https://files.readme.io/4f64c994b0cffec692ab99345e539caa4ef07b8f4a439851f18af3aada6ab473-4411049638033.png)

<div id="important" />

<div id="re-engagement-settings" />

### Pengaturan interaksi ulang

Atribusi penargetan ulang X Ads hanya mencakup konversi interaksi ulang.

Aktifkan sakelar **Atribusi interaksi ulang** untuk mulai mengatribusikan interaksi ulang untuk X Ads.

<div id="re-engagement-click-through-lookback-window" />

#### Jendela lihat-balik klik-tayang interaksi ulang

Tetapkan durasi **Jendela lihat balik klik-tayang interaksi ulang** (jangka waktu maksimal setelah iklan diklik, yang mana pengguna yang ditargetkan ulang dapat diatribusikan ke iklan tersebut). Anda dapat mengatur nilainya dalam jam (hingga 23) atau hari (1-30).

![twitter-reengagement-activate.png](https://files.readme.io/9272c626eceeb8457584d2f1bd1d2adb16f9022994a2efa22eeaeb5b584e2149-4411049796625.png)

<div id="re-engagement-view-through-lookback-window" />

#### Jendela lihat-balik lihat-tayang interaksi ulang

Untuk mulai mengatribusikan tayangan iklan penargetan ulang, aktifkan **Re-engagement view-through attribution (atribusi lihat tayang interaksi ulang)** .

Tetapkan durasi **Re-engagement view-through lookback window (jendela lookback klik-tayang interaksi ulang)** (jangka waktu maksimum setelah iklan diklik, di mana pengguna yang ditargetkan ulang dapat diatribusikan ke iklan tersebut). Anda dapat menyetel nilai dalam jam (hingga 23) atau hari (1-7):

![twitter-reengagement-view-through.png](https://files.readme.io/6d4b80bbe1b953e5df5a6420d71ead781342c616e864e4d1b4d71c68fa9d17fa-4411038679569.png)

<div id="ignore-active-users-for-retargeting" />

<div id="re-engagement-window" />

#### Periode Waktu Re-engagement

Tetapkan durasi jendela **Re-engagement window (jendela interaksi ulang)** (periode ketika in-app event pengguna dikaitkan ke sumber media retargeting (penargetan ulang). Anda dapat mengatur nilai dalam hari (1-90), jam (hingga 23), atau bahkan selamanya:

![Twitter-reengagement-window.png](https://files.readme.io/de80d79c777fc97caa0a28a342657475f0a05c14e30b1f96d24898a4638e1af8-4411047581201.png)

<div id="in-app-event-postback-settings" />

### Pengaturan postback in-app event

Pada bagian ini, Anda dapat memetakan event AppsFlyer Anda dengan mitra Anda melalui postback.

[![In-app_event_postbacks_en-us.png](https://files.readme.io/b215324955412d3a6fc0f719ad54560c25b537a4d1b87475d23c91fbf4262632-7900234463121.png)](https://files.readme.io/b215324955412d3a6fc0f719ad54560c25b537a4d1b87475d23c91fbf4262632-7900234463121.png)

**Untuk mengonfigurasi postback in-app event:**

1. Atur **ID Mitra** (jika diperlukan).
2. Aktifkan  **Postback in-app event.**
3. Klik **Add event** untuk menambahkan SDK atau event server-ke-server ke daftar.
4. Lengkapi parameter yang diperlukan sesuai tabel di bawah ini.  

| Parameter | Deskripsi |
| --- | --- |
| **Event AppsFlyer** | Nama event yang diterima oleh AppsFlyer, baik yang berasal dari SDK yang terintegrasi di aplikasi Anda, atau dari event server ke server.<br />**Tips**: Tidak menemukan event yang Anda cari?<ul><li>Pastikan untuk melakukan testing dengan install non-organic dan periksa kembali.</li><li>Ketik di **AppsFlyer event**, lalu klik **Create custom**. Baca lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#event-khusus">pemetaan event kustom</Anchor>.</li></ul> |
| **dipetakan ke event mitra** | Nama atau ID unik setiap event, sebagaimana ditentukan di pihak mitra. <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#pemetaan-event">Konfigurasi pemetaan</Anchor> yang mungkin:<ul><li>**Bidang teks:** Dapatkan ID event terkait dari mitra.</li><li>**Kotak drop-down:** Pilih event AppsFlyer yang telah ditentukan sebelumnya yang paling sesuai.</li><li>**Apa adanya**  - kirim event apa adanya, tanpa pemetaan nama.</li></ul> |
| **untuk pengguna dari** | Pilih opsi pengiriman untuk event:<br /><br /><br /><br />**Catatan**<br />Agar X Ads menerima postback yang dikaitkan dengan agensi, Anda harus memilih **Semua sumber media, termasuk organik**. Jika tidak, X Ads tidak akan menerima postback semacam itu.<ul><li>**Khusus mitra ini**: kirim postback hanya jika event ini diatribusikan ke mitra ini.</li><li>**Semua sumber media, termasuk organik**: mengirimkan postback untuk event yang dikaitkan dengan mitra mana pun dan event organik.</li></ul> |
| **termasuk** | <ul><li>**Tanpa data (default)**: hanya mengirim event itu sendiri tanpa nilai event.</li><li>**Nilai dan pendapatan**: mengirimkan semua parameter event, **termasuk** nilai pendapatan (jika terdapat dalam event).</li><li>**Nilai tanpa pendapatan**: mengirim semua parameter **kecuali** nilai pendapatan.</li></ul> |

5. [Opsional] Klik<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/d84715dd43041f10684d42e4fe56fd4f76aa4c38fbf9df227c8f8f5610c4f859-19616850611857.png" width="30px" /> untuk mengatur ketentuan pengiriman in-app-event tertentu ke mitra.  
   Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#postback-in-app-event-bersyarat">postback in-app event bersyarat</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Tab Link Atribusi">

X Ads tidak menggunakan tautan atribusi untuk atribusi.

<div id="h_01HDJVBAEZATGM580CNC7BCVTN" />

<div id="note-2" />

> 📘 **Catatan**
>
> Untuk semua <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns">jaringan pelaporan mandiri (SRN)</Anchor>, seperti Meta ads, Iklan Penelusuran Apple (Apple Search Ads), Google Ads, X Ads, dll., tab ini tidak berfungsi karena tidak menggunakan tautan atribusi eksternal.

</Accordion>

<div id="cost-tab" />

<Accordion title="Tab Cost">

Integrasi biaya menyediakan data teragregasi berikut ini:

* Data biaya untuk tingkat kampanye, ad set, iklan, dan kanal Anda. Lihat <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabel integrasi biaya jaringan iklan</Anchor> untuk detail selengkapnya tentang dimensi, metrik, dan fitur yang didukung.   
  **Catatan:** Data biaya memerlukan langganan <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor> .
* Data klik, impresi, dan data yang diperkaya (kata kunci, nama kampanye, dan adset).

**Untuk mengaktifkan API Biaya**:

* Ikuti <Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">petunjuk integrasi ini</Anchor>.

<Anchor target="_blank" href="/marketers/id/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Lihat status API biaya</Anchor> dan terakhir kali AppsFlyer berhasil menarik data biaya yang cocok di dashboard status integrasi biaya (dan pendapatan iklan), atau di dashboard jaringan iklan individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Tab Ad Revenue">

Integrasi pendapatan iklan tidak tersedia untuk X Ads. Untuk menerima data pendapatan iklan, integrasikan MoPub.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Tab Permissions">

Di tab ini, Anda dapat memilih izin untuk diberikan kepada X Ads, untuk mitra bertindak sebagai jaringan iklan, agensi, atau bahkan keduanya. Perhatikan bahwa meskipun atribusi dinonaktifkan untuk X Ads, tab izin aktif dan Anda dapat memberikan kontrol ke X Ads.

Gunakan tombol ini untuk memberikan hak akses kepada ad network dalam menangani konfigurasinya sendiri pada app Anda:

<div id="ad-network-permissions" />

### Hak Akses Ad Network

* **Allow to configure integration** (Izinkan untuk mengonfigurasi integrasi) - mengizinkan partner untuk mengatur tab integration(kecuali pada postback in-app event)
* **Allow to configure in-app event postbacks** (Membuka akses postback in-app event) - mengizinkan partner untuk mengatur mapping postback in-app event ke sistem nya sendiri pada tab integration
* **Allow access to your retention report** (Izinkan akses ke laporan retensi) - hanya ke data retensi milik partner
* **Allow access to your aggregate loyal user data** (Izinkan akses ke data pengguna setia agregat) - hanya ke data pengguna setia milik partner
* **Izinkan akses ke data in-app event gabungan Anda** -  hanya ke data in-app event milik mitra
* **Allow access to your aggregate revenue data** (Izinkan akses ke data pendapatan agregat) - hanya ke data pendapatan yang terkait partner
* **Allow access to your Protect360 dashboard** (Izinkan akses ke dashboard Protect360 Anda) - hanya ke data Protect360 milik partner, dan dengan syarat fitur ini diaktifkan untuk pemasang iklan

Pelajari lebih lanjut tentang memberikan <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#permissions-tab">izin jaringan iklan.</Anchor>

<div id="twitter-user-privacy" />

<div id="twitter-ads-and-appsflyer-skan-interoperation" />

<div id="webtoapp-measuring-app-activity-for-nonapp-campaigns-android-only" />

<div id="mobile-app-promotion-on-x-ads" />

<div id="traits-and-limitations" />

<div id="advanced-srn-parameter-names" />

<div id="important-1" />

<div id="x-ads-features" />

<div id="agency-permissions" />

### Hak Akses Agensi

Pelajari tentang <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#hak-akses-agensi">memberikan izin agensi</Anchor>.

</Accordion>

## Video pengaturan X Ads tingkat lanjut

<Accordion title="Tonton">

<Embed title="Pengaturan integrasi X Ads (sebelumnya Twitter Ads)." typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/3ypfld8enr" providerUrl="https://fast.wistia.com" />

</Accordion>

## Batasan

X Ads tidak mendukung atribusi MMP untuk kampanye Pra-putar.

<div data-zendesk-anchors="connecting-your-twitter-ads-account-to-appsflyer=menghubungkan-akun-x-ads-anda-ke-appsflyer h_01HDJVCRYQESA17XZ83GS81YZ3=menghubungkan-akun-x-ads-anda-ke-appsflyer h_01HDJVBAEZXA0WJ94JYMK84MAX=sebelum-anda-memulai twitter-ads-attribution-setup=pengaturan-atribusi-x-ads h_01HDJVBAEZ5W3JH1BN7WXJ08P6=pengaturan-atribusi-x-ads h_01HDJVBAEZSFKRXAKQJP58N550=integration-tab ad-account-connected=akun-iklan-terhubung h_01HDJVBAEZD89BSGHQTPR84HSC=akun-iklan-terhubung clickthrough-attribution=atribusi-click-through h_01HDJVBAEZFJWQ6FD4Q4GSPD76=atribusi-click-through viewthrough-attribution-lookback-window=lookback-window-atribusi-view-through h_01HDJVBAEZ2H91WBHNSMRQYQ7H=lookback-window-atribusi-view-through reengagement-settings=pengaturan-interaksi-ulang h_01HDJVBAEZZR1W06YH4XJSBKHV=pengaturan-interaksi-ulang reengagement-clickthrough-lookback-window=jendela-lihat-balik-klik-tayang-interaksi-ulang h_01HDJVBAEZ59ERYD2WQQYK6T37=jendela-lihat-balik-klik-tayang-interaksi-ulang reengagement-viewthrough-lookback-window=jendela-lihat-balik-lihat-tayang-interaksi-ulang h_01HDJVBAEZSCK7430NJ8AMQYVY=jendela-lihat-balik-lihat-tayang-interaksi-ulang reengagement-window=periode-waktu-re-engagement h_01HDJVBAEZCMWY5X47FEEFXTBX=periode-waktu-re-engagement inapp-event-postback-settings=pengaturan-postback-in-app-event h_01HDJVBAEZ5ZM9RDXPWTJPPYVA=pengaturan-postback-in-app-event h_01HDJVBAEZATGM580CNC7BCVTN=catatan h_01HDJVBAEZR1Q2SVE9MEQ9EXKP=attribution-link-tab h_01HDJVBAEZ7R7BKFAZYXXBGS5Y=catatan h_01HDJVBAEZYSWN59VNXTDEWX93=cost-tab h_01HDJVBAF0VPBBAEHJPG40HJP8=ad-revenue-tab h_01HDJVBAF0KEVSWJ0EW54AEAWV=permissions-tab ad-network-permissions=hak-akses-ad-network h_01HDJVBAF0BMSCKF6J9NJ019YJ=hak-akses-ad-network agency-permissions=hak-akses-agensi h_01HDJVBAF0W3ZE7J93CRE8EBRP=hak-akses-agensi advanced-twitter-ads-setup-video=video-pengaturan-x-ads-tingkat-lanjut h_01HDJVBAF0SJ93TNQ8WSFVE91P=video-pengaturan-x-ads-tingkat-lanjut limitations=batasan h_01HDJVSZSVMX9ARG2B0CHY45X3=batasan" />
