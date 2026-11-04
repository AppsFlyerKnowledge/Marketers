---
title: Struktur dan parameter tautan atribusi
metadata:
  keywords:
    - pid
    - Marketers
    - af_
    - af
    - c
    - af_mp
    - clickid
    - af_siteid
    - af_sub_siteid
    - af_c_id
    - af_adset_id
    - af_ad_type
    - af_viewthrough
    - af_cost_model
    - af_cost_value
    - af_web_dp
    - af_ref
    - af_ip
    - af_os_version
    - deep_link_sub
    - deep_link_value
    - af_og_title
    - af_og_description
    - af_og_image
    - af_prt
    - af_adset
    - af_ad
    - af_ad_id
    - af_channel
    - af_keywords
    - af_cost_currency
    - af_sub
    - af_r
    - af_dp
    - af_force_deeplink
    - is_incentivized
    - af_param_forwarding
    - af_partner_account_id
    - af_ua
    - af_os
    - af_model
    - af_media_type
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-12-24T11:50:00Z'
  edited_at: '2023-11-20T06:30:09Z'
  id: 207447163
  locale: id
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/id/articles/207447163
---
> **Sekilas:**  Pelajari tentang struktur dan parameter tautan atribusi AppsFlyer.

## Overview

Tautan atribusi memungkinkan pengiklan mengumpulkan data tentang interaksi pengguna dengan iklan. Tautan atribusi ditempatkan di belakang iklan dan memberi tahu AppsFlyer saat pengguna berinteraksi dengan iklan. Interaksi dapat terjadi melalui klik pada iklan atau saat pengguna melihat tayangan iklan Salinan URL atribusi dikirim ke AppsFlyer.

Tautan atribusi dibuat menggunakan **OneLink** atau **tautan platform tunggal**.

|  | OneLink (tautan multi-platform) | Tautan platform tunggal |
| --- | --- | --- |
| Deskripsi dan kapan digunakan | Gunakan saat:<ul><li>Anda menginginkan satu tautan untuk semua platform.</li><li>Kemampuan deep linking diperlukan.</li><li>Anda ingin menggunakan Tautan Aplikasi Android atau Tautan Universal iOS untuk membuka aplikasi.</li></ul><Anchor target="_blank" href="/marketers/id/docs/onelink-guide">Pelajari lebih lanjut tentang OneLink</Anchor> | Gunakan saat:<ul><li>Anda hanya menggunakan satu platform. Misalnya, Android dan bukan iOS.</li><li>Anda hanya menggunakan skema URI untuk membuka aplikasi.</li></ul><Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#attribution-link-tab">Pelajari lebih lanjut tentang cara menyiapkan mitra terintegrasi</Anchor> |
| Prasyarat | <Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template">Templat OneLink</Anchor> | Tidak ada |
| Informasi wajib | <ul><li>[Media Source](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)</li><li>[Kampanye](#c)</li><li>[ID Situs / ID Sub Situs](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> | <ul><li>[Media Source](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)</li><li>[Kampanye](#c)</li><li>[ID Situs / ID Sub Situs](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> |
| URL Dasar | `{subdomain}`.onelink.me | app.appsflyer.com |
| Pengenal unik | ID Templat | app\_id |
| Struktur URL | `https://{subdomain}.onelink.me/  <br />{templateid}?pid={media_source}  <br />&af_siteid={ApplicationID}  <br />&c={CampaignName}` | `https://app.appsflyer.com/{app_id}?pid={media_source}&af_siteid={ApplicationID}&c={CampaignName}` |
| Contoh | `https://yourbrand.onelink.me/aAB1?pid=greatnetwork_int  <br />&c=GreatCampaign&af_siteid=A1b1` | `https://app.appsflyer.com/com.greatapp?pid=greatnetwork_int&  <br />c=GreatCampaign&af_siteid=A1b1` |

<div id="attribution-link-parameters" />

## Parameter link atribusi

* Parameter yang tercantum tersedia untuk digunakan di tautan atribusi.
* Kolom **nilai jenis bidang** adalah batas karakter dari nilai parameter. Temukan lebih lanjut tentang batasan panjang nilai parameter <Anchor target="_blank" href="/marketers/id/docs/raw-data-field-dictionary">di sini.</Anchor>

<div id="attribution-link-parametersua-and-retargeting" />

### Parameter tautan atribusi — UA dan penargetan ulang

Tabel berikut dapat [diunduh sebagai file `.csv`](https://docs.google.com/spreadsheets/d/e/2PACX-1vTZQnoDdFo2NxBuWXBs5gGgvkGU2pr_hn58H9Dtf5uHBAHv4Io89Wd44rRtL24pRsOXHthnBitaOyfp/pub?gid=0&single=true&output=csv).

<div id="attribution-parameters" />

| Parameter | Tampilkan nama dalam data lengkap | Deskripsi | Jenis dan panjang bidang |
| --- | --- | --- | --- |
| <span id="pid"></span>pid | Media Source | Mengidentifikasi secara unik mitra terintegrasi AppsFlyer. Jangan mengubahnya. [Rincian selengkapnya](/docs/about-link-structure-and-parameters#partner-id-pid-parameter) . | <span id="PID"></span>String 150 |
| <span id="c"></span>c | Kampanye | Disediakan oleh pemasang iklan atau penerbit. Lihat [limit untuk nama kampanye](/docs/about-link-structure-and-parameters#what-limits-are-there-on-campaign-names). | <span id="Campaign"></span>String 100 |
| <span id="af_prt"></span>af\_prt | Partner | <ul><li>Nama Akun Agensi memungkinkan mengatribusikan penginstalan ke agensi</li><li>**Perhatian** : Jangan gunakan parameter ini sebelum memastikan bahwa **Izin Agensi** diaktifkan</li></ul> | String 50 |
| <span id="af_mp"></span>af\_mp | N/A | <ul><li>Aktifkan pengiriman postback ke mitra pemasaran penerbit per penginstalan.</li><li>**Catatan**: Saat ini, parameter ini hanya relevan untuk Mitra Pemasaran Pinterest.</li></ul> |  |
| <span id="clickid"></span>clickid | N/A | Pengidentifikasi klik unik jaringan iklan |  |
| <span id="af_siteid"></span>af\_siteid | ID situs | <ul><li>ID unik yang mengidentifikasi penerbit yang menampilkan iklan. [Pelajari lebih lanjut](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> | <span id="Site_id"></span>String 24 |
| <span id="af_sub_siteid"></span>af\_sub\_siteid | ID Sub Situs | <ul><li>Sub-jaringan iklan/ID Penerbit.</li><li>Jika selain penerbit utama (ID situs), ada sub-penerbit, atau jika Anda menyertakan informasi tambahan, seperti jenis iklan/penempatan dalam aplikasi, seperti spanduk, iklan interstisial, video, dll. gunakan af\_sub\_siteid. Misalnya: af\_sub\_siteid =ABCD\_4567</li></ul> | String 50 |
| <span id="af_c_id"></span>af\_c\_id | ID kampanye | Disediakan oleh pemasang iklan/penayang | String 24 |
| <span id="af_adset"></span>af\_adset | adset | <ul><li>Disediakan oleh pemasang iklan/penayang.</li><li>Adset adalah tingkat menengah dalam hierarki antara Kampanye dan Iklan. [Lihat selengkapnya](/docs/about-link-structure-and-parameters#tingkat-perincian-data)</li></ul> | String 100 |
| <span id="af_adset_id"></span>af\_adset\_id | ID adset | Disediakan oleh pemasang iklan/penayang | String 24 |
| <span id="af_ad"></span>af\_ad | ad | Nama Iklan ([lihat selengkapnya](/docs/about-link-structure-and-parameters#tingkat-perincian-data)) disediakan oleh pengiklan/penayang | String 100 |
| <span id="af_ad_id"></span>af\_ad\_id | ID iklan | Disediakan oleh pemasang iklan/penayang | String 24 |
| <span id="af_ad_type"></span>af\_ad\_type | Jenis iklan | Gunakan konvensi penamaan berikut:<ul><li>**teks:** unit iklan yang hanya berisi teks, misalnya hasil pencarian</li><li>**spanduk:**  format dasar yang muncul di bagian atas atau bawah layar perangkat</li><li>**interstisial:**  iklan satu halaman penuh yang muncul selama jeda dalam pengalaman saat ini</li><li>**video:** a video standar, non-reward</li><li>**rewarded\_video:** unit iklan yang menawarkan reward dalam aplikasi sebagai imbalan untuk menonton video</li><li>**dapat dimainkan:** unit iklan yang berisi pratinjau interaktif dari pengalaman aplikasi</li><li>**sponsored\_content:**  tautan yang disertakan dalam konten bersponsor, seperti artikel advertorial</li><li>**audio:** iklan audio</li></ul> | String 24 |
| <span id="af_click_lookback"></span>af\_click\_lookback | Atribusi jendela lookback | <ul><li>Jendela Lookback untuk Atribusi Klik. Durasi periode waktu ini adalah CTIT (Jeda Waktu Klik hingga Penginstalan) maksimum bagi pengguna baru untuk diatribusikan ke sumber yang menampilkan iklan/tautan.</li><li>Jumlah  hari yang dapat dikonfigurasi untuk periode atribusi klik lookback. Nilai parameter yang tersedia: 1 hari - 30 hari (hari) ATAU 1 jam-23 jam (jam). Nilai defaultnya adalah 7hari.</li><li>Jendela lookback dapat disesuaikan untuk <Anchor target="_blank" href="/marketers/id/docs/set-up-lookback-windows#pengaturan-jendela-lookback">OneLinks dan SRNs</Anchor>.</li></ul>**Catatan** : Hanya memengaruhi URL klik dan bukan URL tayangan. | Maks. 3 karakter |
| <span id="af_viewthrough_lookback"></span>{"af_viewthrough_"}  <br />lookback | N/A | <ul><li>Jumlah hari yang dapat dikonfigurasi untuk periode atribusi lihat-tayang (view-through) lookback. Nilai parameter yang tersedia: 1 jam - 24 jam (jam). Defaultnya adalah 24 jam.</li><li>Jendela lookback dapat disesuaikan untuk <Anchor target="_blank" href="/marketers/id/docs/set-up-lookback-windows#pengaturan-jendela-lookback">SRN</Anchor>.</li></ul>**Catatan** : Hanya memengaruhi URL tayangan dan bukan URL klik | Maks. 3 karakter |
| <span id="af_channel"></span>af\_channel | Channel | Kanal sumber media tempat iklan didistribusikan, misalnya, UAC\_Search, UAC\_Display, Instagram, Meta Audience Network, dll. | Dynamic Enum. String 20 |
| <span id="af_keywords"></span>af\_keywords | Keywords | Daftar kata kunci untuk kampanye bertarget teks | String 100 |
| <span id="af_cost_model"></span>af\_cost\_model | Model Biaya | <ul><li>Model biaya, CPI (default) saat ini adalah satu-satunya model yang tersedia ketika melaporkan biaya berdasarkan klik, yang mengisi <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports">nilai biaya di laporan data gabungan AppsFlyer</Anchor> .</li><li>Jika memungkinkan, laporkan biaya berdasarkan <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview#cost-aggregation-methods">API</Anchor>. Dalam hal di mana biaya dilaporkan melalui tautan dan oleh API - API memiliki prioritas.</li></ul> | String 20 |
| <span id="af_cost_currency"></span>af\_cost\_currency | Mata Uang Biaya | <ul><li>Kode mata uang 3 huruf sesuai dengan <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview#cost-aggregation-methods">ISO-4217.</Anchor> Misalnya, USD, ZAR, EUR</li><li>[Default] USD</li></ul> | jumlah. 3 karakter |
| <span id="af_cost_value"></span>af\_cost\_value | Nilai Biaya | <ul><li>Nilai biaya dalam menggunakan mata uang biaya.</li><li>Hingga 4 digit setelah titik desimal.</li><li>Tetapkan HANYA angka numerik (gunakan titik desimal jika diperlukan) Contoh: "56", "2.85"</li></ul> | String 20 |
| <span id="af_sub-n-n15-example-af_sub1"></span>af\_sub[n]<br /><br />(n=1-5) contoh: af\_sub1 | Sub param [n] | Parameter kustom opsional yang ditentukan oleh pemasang iklan. Untuk informasi lebih lanjut tentang penggunaan parameter ini, periksa bagian [Ciri dan batasan](/docs/about-link-structure-and-parameters#traits-and-limitations) . | String 100 |
| <span id="af_r"></span>af\_r | N/A | Digunakan dalam tautan platform tunggal untuk mengarahkan pengguna ke URL tertentu untuk **kedua platform** (Android dan iOS).<ul><li>Ditimpa oleh parameter platform tunggal tingkat tautan berikut):<ul><li>[`af_android_url`](/docs/about-link-structure-and-parameters#af_android_url)</li><li>[`af_ios_url`](/docs/about-link-structure-and-parameters#af_ios_url)</li><li>[`af_web_dp`](/docs/about-link-structure-and-parameters#af_web_dp)</li></ul></li></ul><ul><li>Menggantikan parameter tingkat templat berikut:<ul><li>`android_custom_url`</li><li>`ios_custom_url`</li></ul></li></ul> |  |
| <span id="af_web_dp"></span>af\_web\_dp | N/A | URL untuk mengarahkan pengguna desktop (misalnya, Windows atau Mac) ke laman web yang berbeda dari yang dikonfigurasi di template OneLink. Gunakan cara ini untuk menyimpan data atribusi dari pengguna desktop di platform lain (mis. Google Analytics atau Omniture)<br /><br />**Catatan** : Jika Anda memiliki daftar <Anchor target="_blank" href="/marketers/id/docs/set-up-your-api-allowlist#redirect-allowlists">Pengalihan yang diizinkan</Anchor> aktif, pastikan domain URL ini ada dalam daftar. |  |
| <span id="af_dp"></span>af\_dp | N/A | Nilai fallback skema URI untuk meluncurkan aplikasi, akan digunakan jika metode Tautan Universal atau Tautan Aplikasi Android gagal, dan untuk pengguna Android versi sebelum 6.0. Seharusnya ini hanya mengarah pada <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">base path</Anchor>, yaitu aktivitas default. |  |
| <span id="af_force_deeplink"></span>af\_force\_deeplink | N/A | <Anchor target="_blank" href="/marketers/id/docs/onelink-troubleshooting-and-faq">Force deep linking</Anchor> ke aktivitas yang ditentukan dalam nilai af\_dp |  |
| <span id="af_ref"></span>af\_ref | N/A | Jaringan iklan yang bekerja dengan klik S2S dapat mengirim nilai perujuk unik menggunakan parameter berikut: &af\_ref= **ReferrerValue**<br /><br />Nilai af\_ref **harus** terdiri dari nilai unik, terstruktur sebagai berikut:<br /><br />**NetworkName\_UniqueClickValueForEachClick**<br /><br />Contoh: af\_ref=networkname\_123456789ABCDEF<br /><br />Nama jaringan dapat berupa string apa pun yang valid. Nama ini dapat berupa networkname\_int atau hanya nama jaringan.<br /><br />AppsFlyer dapat menggunakan parameter ini untuk atribusi di perangkat Android. AppsFlyer tidak menggunakan parameter ini untuk atribusi di perangkat iOS atau Windows. |  |
| <span id="is_incentivized"></span>is\_incentivized | N/A | Boolean: true/false<br /><br />Kampanye dengan insentif atau non-insentif |  |
| <span id="af_param_forwarding"></span>af\_param\_forwarding | N/A | <ul><li>Jika diatur ke false, parameter yang ada di tautan atribusi tidak akan diteruskan ke laman yang diarahkan</li><li>Gunakan cara ini untuk URL yang lebih rapi di laman yang diarahkan, atau jika parameter OneLink mungkin bermasalah karena penanganan parameter di laman yang diarahkan.</li></ul> |  |
| <span id="af_base_params_forward"></span>af\_base\_params\_forward | N/A | <ul><li>Jika disetel ke false, parameter PID dan C AppsFlyer yang ada di tautan atribusi tidak diteruskan ke halaman yang dialihkan.</li><li>Gunakan ini jika URL akan diklik dari desktop dan Anda ingin parameter CRM penting tetap ada, tetapi parameter PID dan C AppsFlyer dihapus. Ini akan menghindari memiliki banyak PID di URL.</li></ul> |  |
| <span id="af_partner_account_id"></span>af\_partner\_account\_id | ID Akun Jaringan | ID akun pengiklan dengan partner | String 100 |
| <span id="af_redirect"></span>redirect | N/A | Saat`af_redirect=false`, parameter ini memberitahu AppsFlyer bahwa ini adalah klik S2S dan mitra bertanggung jawab untuk mengalihkan pengguna yang mengeklik. |  |
| <span id="af_ua"></span>af\_ua | Pengguna | Relevan untuk jaringan iklan yang mengirimkan klik dan impresi <Anchor target="_blank" href="/partners/id/docs/redirecting-users-to-the-app-store">server-to-server</Anchor>.<br /><br />String pengguna dikirim sebagai:<ol><li>Parameter URL (dikodekan dengan URL)</li><li>Header permintaan HTTP (tidak dikodekan)</li></ol>Pengguna harus **sama, baik di parameter URL dan header HTTP**.<br /><br />**Perhatian**: Di Android, tugas pengguna terkadang dibatasi menjadi mengurus Client Hints. Hasilnya harus tetap dikirimkan.<ul><li>Contoh pengguna penuh: `Mozilla/5.0 (Linux; Android 12; Pixel 5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.16 Mobile Safari/537.36`</li><li>Contoh pengguna yang dibatasi: `Mozilla/5.0 (Linux; Android 10; K) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.0.0 Mobile Safari/537.36`</li></ul> |  |
| <span id="af_ip"></span>af\_ip | ip | Relevan untuk jaringan iklan yang mengirimkan klik dan impresi <Anchor target="_blank" href="/partners/id/docs/redirecting-users-to-the-app-store">server-to-server</Anchor>.<br /><br />**Alamat IP Perangkat**<br /><br />**Rekomendasi**: Jika tersedia, berikan IP perangkat berdasarkan parameter af\_ip.<br /><br />**Pilihan selanjutnya**: Jika tersedia, AppsFlyer akan menggunakan IP di X-Forwarded-For. |  |
| <span id="deprecated--af_os"></span>[Deprecated] af\_os | Versi iOS | [Khusus iOS] Versi sistem operasi perangkat.<br /><br />Parameter ini tidak digunakan lagi tetapi masih didukung oleh AppsFlyer. Rekomendasi: Gunakan parameter af\_os\_version parameter sebagai gantinya. |  |
| <span id="af_os_version"></span>af\_os\_version | Versi iOS | <ul><li>Relevan untuk jaringan iklan yang mengirimkan klik dan impresi <Anchor target="_blank" href="/partners/id/docs/redirecting-users-to-the-app-store">server-to-server</Anchor>.</li><li>Versi sistem operasi perangkat.<ul><li>Android:<ul><li>Contoh: 12</li><li>Untuk pengguna yang dibatasi (karena browser yang bekerja di desktop atau Android dan menggunakan mesin Chrome 110+), jaringan iklan harus menggunakan <Anchor target="_blank" href="https://web.dev/migrate-to-ua-ch/">Client Hints API</Anchor> untuk mendapatkan nilai ini.</li><li>Untuk pengguna yang **tidak** dibatasi, gunakan regex berikut ini untuk mengekstrak versi sistem operasi Android dari string pengguna: `(\d+(?:\.\d+)*);(?:\s..-..;)?\s(.+?(?=\)\|\s\w*\/))`.</li></ul></li><li>iOS:<ul><li>Contoh: 16.2</li></ul></li></ul></li></ul> |  |
| <span id="af_model"></span>af\_model | Model perangkat | <ul><li>Relevan untuk jaringan iklan yang mengirimkan klik dan impresi <Anchor target="_blank" href="/partners/id/docs/redirecting-users-to-the-app-store">server-to-server</Anchor>.</li><li>Model perangkat.<ul><li>Android:<ul><li>Contoh: Pixel 5</li><li>Untuk pengguna yang dibatasi (karena browser yang bekerja di desktop atau Android dan menggunakan mesin Chrome 110+), jaringan iklan harus menggunakan <Anchor target="_blank" href="https://web.dev/migrate-to-ua-ch/">Client Hints API</Anchor> untuk mendapatkan nilai ini.</li><li>Untuk pengguna yang **tidak** dibatasi, gunakan regex berikut ini untuk mengekstrak model Android ini dari string pengguna: `(\d+(?:\.\d+)*);(?:\s..-..;)?\s(.+?(?=\)\|\s\w*\/))`.</li></ul></li><li>iOS:<ul><li>Antara `iphone` atau `ipad` (semua huruf kecil)</li></ul></li></ul></li></ul> |  |
| <span id="af_media_type"></span>af\_media\_type | Jenis media: | Penempatan iklan yang membawa tautan sebagai berikut:<ul><li>app: Tautan tersedia melalui aplikasi</li><li>web: Tautan tersedia dalam situs web seluler</li></ul> |  |
| <span id="deep_link_sub110"></span>deep\_link\_sub1-10 | N/A | Nilai  deep link tambahan. Pengembang menerapkan perilaku nilai yang diinginkan dalam kode. |  |
| <span id="deep_link_value"></span>deep\_link\_value | N/A | Nama untuk konten in-app tertentu yang akan diarahkan oleh pengguna. Pengembang menerapkan perilaku yang diinginkan dari deep\_link\_value dalam kode. |  |
| <span id="af_og_title"></span>af\_og\_title | N/A | Saat tautan diposting ke media sosial, judul grafik terbuka (OG) akan menghasilkan pratinjau judul. | String 40 |
| <span id="af_og_description"></span>af\_og\_description | N/A | Saat tautan diposting ke media sosial, deskripsi grafik terbuka (OG) akan menghasilkan pratinjau deskripsi. | String 300 |
| <span id="af_og_image"></span>af\_og\_image | N/A | Saat tautan diposting ke media sosial, gambar grafik terbuka (OG) akan menghasilkan pratinjau gambar. |  |

<div id="attribution-link-parametersretargeting-only" />

### Parameter tautan atribusi —khusus penargetan ulang

| Parameter | Tampilkan nama dalam data lengkap | Deskripsi | Jenis dan lebar bidang |
| --- | --- | --- | --- |
| <span id="is_retargeting"></span>is\_retargeting | Merupakan Penargetan ulang (kampanye) | URL klik dari semua kampanye penargetan ulang harus menyertakan `&is_retargeting=true` .  <br />Jika parameter tidak disertakan atau nilainya "false", kampanye dianggap sebagai kampanye akuisisi pengguna biasa. | Enum 5 karakter |
| <span id="af_reengagement_window"></span>af\_reengagement\_window | Periode Waktu Re-engagement | Ubah <Anchor target="_blank" href="/marketers/id/docs/set-up-re-attribution-window#setting-the-re-attribution-window">jendela atribusi interaksi ulang</Anchor> dengan menambahkan parameter ini ke tautan atribusi.<br /><br />Opsi rentang jendela yang mungkin adalah:<ul><li>Hari: 1-90 atau Jam 1-36</li><li>Seumur hidup: Ini berarti jendela interaksi ulang tidak terbatas. Contoh: `&af_reengagement_window=lifetime`</li></ul>Nilai default: 30 hari<br /><br />Contoh: `&af_reengagement_window=30d` menyetel jendela interaksi ulang menjadi 30 hari. | N/A |

<div id="viewability-parameters" />

### Parameter jenis iklan

Bergantung pada jenis iklan, Anda juga dapat mengirim parameter visibilitas yang relevan yang merinci spesifikasi interaksi. Di bawah ini adalah daftar kemungkinan nilai untuk “af\_ad\_type” beserta perkiraan parameter visibilitas.

#### Jenis iklan (af\_ad\_type)

| Parameter | Format nilai | Deskripsi |
| --- | --- | --- |
| <span id="af_video_total_length"></span>af\_video\_total\_length | detik | Total kemungkinan durasi video |
| <span id="af_video_played_length"></span>af\_video\_played\_length | detik | Berapa banyak video yang dilihat |
| <span id="af_playable_played_length"></span>af\_playable\_played\_length | detik | Berapa lama elemen yang dapat diputar dimainkan setelah terisi penuh |
| <span id="af_ad_time_viewed"></span>af\_ad\_time\_viewed | detik | Berapa lama unit iklan terlihat di layar |
| <span id="af_ad_displayed_percent"></span>af\_ad\_displayed\_percent | % | Persentase maksimum unit iklan yang terlihat di layar perangkat |
| <span id="af_audio_total_length"></span>af\_audio\_total\_length | detik | Total kemungkinan durasi audio |
| <span id="af_audio_played_length"></span>af\_audio\_played\_length | detik | Berapa banyak audio yang didengar |

<div id="android-specific-parameters" />

### Parameter khusus Android

| Parameter | Tampilkan nama dalam data lengkap | Deskripsi | Jenis kolom |
| --- | --- | --- | --- |
| <span id="advertising_id"></span>advertising\_id | ID Iklan | ID Iklan Google - Memerlukan dukungan jaringan iklan | Maksimal 40 karakter |
| <span id="sha1_advertising_id"></span>sha1\_advertising\_id | N/A | ID Iklan Google di-hash dengan SHA1 - Memerlukan dukungan jaringan iklan |  |
| <span id="md5_advertising_id"></span>md5\_advertising\_id | N/A | ID Iklan Google di-hash dengan MD5 - Memerlukan dukungan jaringan iklan | Hanya didukung dengan penginstalan dan atribusi ulang |
| <span id="android_id"></span>android\_id | ID Android | Perangkat Android\_id - Memerlukan dukungan jaringan iklan | Maksimal 20 karakter |
| <span id="sha1_android_id"></span>sha1\_android\_id | N/A | Perangkat Android\_id di-hash dengan SHA1 - Memerlukan dukungan jaringan iklan |  |
| <span id="md5_android_id"></span>md5\_android\_id | N/A | Perangkat Android\_id di-hash dengan MD5 - Memerlukan dukungan jaringan iklan | Hanya didukung dengan penginstalan dan atribusi ulang |
| <span id="imei"></span>imei | IMEI | ID IMEI perangkat |  |
| <span id="sha1_imei"></span>sha1\_imei | N/A | ID IMEI perangkat  di-hash dengan SHA1 - Memerlukan dukungan jaringan iklan |  |
| <span id="md5_imei"></span>md5\_imei | N/A | ID IMEI perangkat di-hash dengan MD5 - Memerlukan dukungan jaringan iklan |  |
| <span id="oaid"></span>oaid | OAID | Buka Pengidentifikasi Perangkat Anonim | Tersedia di Android SDK versi 4.10.3 |
| <span id="sha1_oaid"></span>sha1\_oaid | N/A | Buka Pengidentifikasi Perangkat Anonim yang  di-hash dengan SHA1 - Memerlukan dukungan jaringan iklan | Tersedia di Android SDK versi 4.10.3 |
| <span id="md5_oaid"></span>md5\_oaid | N/A | Buka Pengidentifikasi Perangkat Anonim yang  di-hash dengan MD5 - Memerlukan dukungan jaringan iklan | Tersedia di Android SDK versi 4.10.3 |
| <span id="af_android_url"></span>af\_android\_url | N/A | Mengarahkan pengguna Android ke URL selain dari halaman aplikasi pada Google Play. Gunakan untuk <Anchor target="_blank" href="/marketers/id/docs/set-up-multi-store-android-attribution#dashboard-tunggal-vs-dashboard-per-toko">toko aplikasi pihak ketiga</Anchor>.<br /><br />**Catatan** : Jika Anda memiliki daftar <Anchor target="_blank" href="/marketers/id/docs/set-up-your-api-allowlist#redirect-allowlists">Pengalihan yang diizinkan</Anchor> aktif, pastikan domain URL ini ada dalam daftar. |  |
| <span id="sha1_el"></span>sha1\_el | N/A | Digunakan untuk atribusi desktop ke seluler - email di-hash dengan SHA1. Memerlukan dukungan jaringan iklan |  |
| <span id="fire_advertising_id"></span>fire\_advertising\_id | N/A | ID Iklan Amazon Fire |  |
| <span id="af_android_store_csl"></span>af\_android\_store\_csl | store\_product\_page | Listing toko kustom di Google Console | string |

<div id="ios-specific-parameters" />

### Parameter spesifik iOS

| Parameter | Nama Tampilan | Deskripsi |
| --- | --- | --- |
| <span id="idfa"></span>idfa | IDFA | Gunakan huruf besar. Membutuhkan dukungan jaringan iklan<br /><br />Jenis bidang: maks 40 karakter |
| <span id="idfv"></span>idfv | IDFV | Gunakan huruf besar. |
| <span id="af_ios_url"></span>af\_ios\_url |  | Gunakan ini untuk pengalihan ulang halaman arahan untuk mengalihkan pengguna iOS (iPhone atau iPad) ke URL berbeda dari halaman aplikasi di iTunes<br /><br />**Catatan** : Jika Anda memiliki daftar <Anchor target="_blank" href="/marketers/id/docs/set-up-your-api-allowlist#redirect-allowlists">Pengalihan yang diizinkan</Anchor> aktif, pastikan domain URL ini ada dalam daftar. |
| <span id="af_ios_store_cpp"></span>af\_ios\_store\_cpp | store\_product\_page | ID halaman produk kustom (ppid) |
| <span id="af_ios_fallback--deprecated"></span>af\_ios\_fallback [kedaluwarsa] | N/A | **Kedaluwarsa**: Pengguna diarahkan berdasarkan <Anchor target="_blank" href="/marketers/id/docs/uri-scheme-fallback-for-ios">alur skema URI iOS</Anchor>. |
| <span id="sha1_idfa"></span>sha1\_idfa | N/A | IDFA di-hash dengan SHA1. Membutuhkan dukungan jaringan iklan |
| <span id="sha1_idfv"></span>sha1\_idfv | N/A | IDFV di-hash dengan SHA1. |
| <span id="mac"></span>mac | N/A | Alamat mac perangkat. Membutuhkan dukungan jaringan iklan |
| <span id="md5_idfv"></span>md5\_idfv | N/A | IDFV di-hash dengan MD5 |
| <span id="sha1_mac"></span>sha1\_mac | N/A | Alamat mac perangkat di-hash dengan SHA1. Membutuhkan dukungan jaringan iklan |

<div id="example" />

> 📄 **Contoh**
>
> ```http
> https://app.appsflyer.com/{app_id}/?pid=airpush_int&c=RedBanner&
> 	  af_siteid={publisher_id}&af_sub1=1.5&af_sub2=USD&af_sub3=burst_campaign
> ```

Semua parameter tersedia di <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">Install report (Laporan penginstalan)</Anchor> dan <Anchor target="_blank" href="/marketers/id/docs/analytics-and-aggregate-reporting-apis">Analytics (Analisis), Reports (Laporan), serta APIs</Anchor>.

<div id="custom-parameters" />

### Parameter Kustom

Selain parameter khusus default Android dan iOS, Anda juga dapat menentukan parameter personalisasi. Parameter personalisasi ini dapat membantu jika Anda ingin mempersonalisasi pengalaman pengguna dan konten sesuai tautan atribusi yang mengarah ke penginstalan.

Anda dapat menambahkan parameter khusus ke tautan atribusi dalam format `parameter=value`. Contoh:

```http
https://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&af_adset=coats&af_ad=cashmere&my_custom_param=my_custom_value
```

Dua hal penting yang perlu diketahui tentang parameter khusus:

* Parameter khusus tidak muncul dalam data lengkap.
* Parameter khusus dapat diambil dari <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">mendapatkan data konversi SDK API</Anchor>.

<div id="partner-id-pid-parameter" />

<Accordion title="Parameter ID Mitra (Partner ID/PID)">

Di antara semua parameter tautan atribusi yang tersedia, PID adalah wajib. PID adalah pengenal unik dari sumber media yang dialokasikan oleh AppsFlyer.

Setiap <Anchor target="_blank" href="http://appsflyer.com/partners">mitra terintegrasi</Anchor> memiliki nilai PID unik mereka sendiri. PID memiliki akhiran *\_int*. Saat menggunakan <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">tautan OneLink</Anchor> , Anda dapat menyetel PID ke nilai apa pun yang Anda inginkan, asalkan belum ditentukan oleh mitra terintegrasi. **Untuk menghindari konflik, jangan gunakan akhiran *\_int***.

Contoh ID penerbit terintegrasi yang penting: organik, googleadwords\_int (Google AdWords), Meta ads (iklan Meta), dan Twitter. Anda dapat menggunakan nama apa pun untuk sumber yang tidak terintegrasi seperti email, sms, atau mail pigeon.

<div id="avoid-common-pid-issues" />

#### Hindari masalah PID umum

* **Selalu sertakan PID di tautan atribusi Anda.** Tanpa PID di tautan atribusi, pengguna secara otomatis diatribusi ke sumber media "Tidak Ada" dan sumber penginstalan aslinya hilang.
* **Untuk Sumber Kustom, gunakan PID mitra yang tidak terintegrasi.** Untuk setiap sumber terintegrasi, gunakan hanya PID yang ditentukan untuk atribusi yang benar dari penginstalannya. Untuk sumber media personalisasi apa pun, seperti email, SMS, atau bahkan postingan viral gratis di Facebook, gunakan nilai PID lain yang tidak terintegrasi.
* **Gunakan hanya karakter legal.** Jika parameter PID di Tautan Atribusi berisi salah satu karakter berikut /&lt;>*&?\
  * Klik atau instal muncul di dashboard di bawah ***af\_invalid\_param***
  * Tautan atribusi tidak akan diatribusikan
  * Kemampuan deep linking tidak akan berfungsi pada klik

<div id="tip" />

> 👍 **Tips**
>
> Hindari menggunakan spasi dalam nilai PID, atau pastikan URL mengkodekan tautan atribusi Anda sebelum menggunakannya.

</Accordion>

<div id="site-id-parameter" />

<Accordion title="Parameter ID situs">

ID situs adalah pengenal unik penerbit yang menayangkan iklan. Dengan kata lain, situs web atau aplikasi yang menampilkan iklan. Jaringan iklan mengalokasikan ID situs unik untuk setiap penerbit.

ID ini disertakan dalam parameter `af_siteid` yang diteruskan ke AppsFlyer di tautan atribusi dan tersedia melalui berbagai dashboard, opsi pelaporan, dan postback.

ID situs harus diteruskan ke AppsFlyer di tautan atribusi karena ID ini:

* Memberikan kejelasan dan transparansi tentang penerbit.
* Digunakan oleh AppsFlyer untuk mengidentifikasi dan menghapus penayang palsu, dan kluster lalu-lintas lainnya.

Parameter ID situs hanya menyertakan ID penayang yang menayangkan iklan.

Untuk menyertakan informasi tambahan, seperti jenis iklan, penempatan, atau keduanya dalam aplikasi, misalnya spanduk, pengantara, atau video, gunakan parameter ID sub situs.

<div id="example-1" />

> 📄 **Contoh**
>
> Tautan atribusi berikut mencakup:
>
> * `af_siteid` (ID situs): ID Penayang
> * `af_sub_siteid` (ID sub-situs): Informasi ID tambahan (dalam hal ini, sumber afiliasi dan penempatan jenis iklan)
>
> `https://app.appsflyer.com/com.yourapp?pid=mediaName_int&clickid={clickid}&advertising_id={gaid}&af_siteid=1234&af_sub_siteid=ABCD_4567`
>
> Di tautan contoh:
>
> * 1234 = ID Penayang
> * ABCD = Sumber afiliasi (sub-penayang) yang bekerja sama dengan penayang
> * 4567 = Penempatan jenis iklan di dalam aplikasi, seperti spanduk, iklan interstisial, atau video

<div id="faq-why-does-traffic-result-in-many-blocked-installs" />

#### **Pertanyaan Umum: Mengapa lalu-lintas menghasilkan banyak penginstalan yang diblokir?**

Penginstalan yang diblokir dapat disebabkan oleh hal berikut:

* **ID situs tidak ada:** Parameter `af_siteid` tidak ada di URL klik. Interaksi yang dikirim dengan ID situs yang kosong menandakan masalah teknis atau upaya yang disengaja untuk melewati mekanisme deteksi kecurangan.
* **Beberapa ID situs:** Penayang yang sama dikirim ke beberapa URL klik, menggunakan ID situs yang berbeda. Ini dianggap perilaku curang yang menyembunyikan aktivitas penayang yang sebenarnya dan seringkali dikaitkan dengan <Anchor target="_blank" href="https://www.appsflyer.com/blog/click-flooding-detection-false-positive-challenge/">click flooding (banjir klik)</Anchor>.
* **Pemformatan ID Situs yang salah:** Mengirimkan format yang salah, dikombinasikan dengan indikasi kecurangan lainnya, dapat menyebabkan pemblokiran tidak hanya penayang tertentu, tetapi juga level kluster yang lebih tinggi, dan dapat memengaruhi volume aktivitas mitra yang lebih besar.

Untuk menghindari pemblokiran penginstalan, pastikan Anda mengirimkan satu parameter ID situs per penayang, seperti yang ditunjukkan pada contoh.

</Accordion>

<div id="levels-of-data-granularity" />

## Tingkat perincian data

Anda dapat menggunakan hingga empat parameter URL untuk mengukur kinerja iklan Anda.

Menggunakan keempat parameter pada semua tautan atribusi aktif Anda memungkinkan Anda untuk:

* Mengatribusikan semua penginstgalan dan event pengguna ke iklan tertentu
* Telusuri dan bandingkan kinerja semua iklan Anda per ad set, per kampanye, dan per sumber media pada laporan gabungan untuk dioptimalkan di setiap tingkat
* Membandingkan semua iklan Anda di semua sumber media pada laporan data lengkap dan <Anchor target="_blank" href="/marketers/id/docs/pivot-table-user-metrics">tabel Pivot</Anchor>

Parameternya adalah:

* `Sumber media (pid=)`
* `nama kampanye (c=)`
* `Set iklan (af_adset=)`
* `Nama iklan (af_ad=)`

<div id="example-2" />

> 📄 **Contoh**
>
> Tautan atribusi berikut menggunakan 4 tingkat perincian untuk mencatat iklan "kashmir" dalam set iklan "mantel" dalam kampanye "musim dingin" yang berjalan pada sumber media "jaringan" terintegrasi.
>
> ```http
> https://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&
> af_adset=coats&af_ad=cashmere
> ```

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Sifat | Catatan |
| --- | --- |
| Karakter khusus | Karakter khusus berikut tidak diperbolehkan dalam parameter atau nilai: ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ', >, &lt;, /, \{, \}, % |
| Batas karakter URL | Panjang URL total tidak boleh melebihi 2.000 karakter |
| Pengalihan tautan langsung WebView aplikasi sosial Android | Lihat detail batasan <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#android-social-apps-webview-deep-linking-redirection">di sini</Anchor> |

</Accordion>

<div id="should-i-use-lower-or-upper-case-letters-for-parameters" />

<Accordion title="Haruskah saya menggunakan huruf kecil atau huruf besar untuk parameter">

Anda dapat menggunakan salah satunya tetapi Anda harus konsisten. Jika Anda menetapkan parameter khusus dengan karakter huruf besar atau kecil, pastikan untuk selalu menggunakan parameter itu.

Misalnya, jika Anda mengatur pid=MyMediaSource, pastikan untuk selalu menggunakannya. Jika Anda menggunakan pid=MyMediaSource di salah satu tautan atribusi dan pid=mymediasource di tautan atribusi lainnya, akan terjadi perbedaan data. Hal yang sama berlaku untuk semua parameter lainnya yang Anda atur di tautan atribusi.

</Accordion>

<div id="is-the-appsflyer-attribution-link-dynamic-or-static" />

<Accordion title="Apakah tautan atribusi AppsFlyer statis atau dinamis?">

Tautan atribusi bisa dinamis atau statis.  
Bagaimana cara mengetahui apakah suatu tautan dinamis atau statis?  
Jika **tautan atribusi berisi parameter**, itu adalah tautan atribusi panjang yang telah ditentukan sebelumnya, dan karena itu **statis**.  
**Hanya URL singkat** (misalnya, `yourbrand.onelink.me/HaT8/r5c2b371`), yang digunakan untuk tautan atribusi khusus, **yang dinamis**.  
Hal ini berarti bahwa begitu Anda mulai menggunakan tautan atribusi untuk mitra terintegrasi, atau URL panjang untuk media yang dimiliki, itu tidak akan berubah untuk setiap calon pengguna yang berinteraksi dengannya, bahkan jika Anda mengubah nilai tautan atribusi di dashboard AppsFlyer. Agar perubahan terjadi, selanjutnya Anda perlu menggunakan URL panjang baru.  
Di sisi lain, URL singkat untuk media yang dimiliki, tidak secara langsung berisi parameter. Saat seorang calon pelanggan berinteraksi dengan URL singkat, calon pelanggan diarahkan ke AppsFlyer dan parameter yang diatur saat ini berlangsung secara dinamis.

</Accordion>

<div id="what-is-this-play-store-error-message" />

<Accordion title="Apa pesan kesalahan Play Store ini?">

Jika Anda menemukan pesan kesalahan berikut di Play Store setelah mengikuti Tautan atribusi:

![TL_error_message.png](https://files.readme.io/03e509d3cbe68aa0621bb0f43ab113c25a8427e70826c5af5258f1fc9e3f3d36-360000002485.png)

Ini karena tautan atribusi menyertakan # karakter. Contoh:

```http
https://app.appsflyer.com/com.travelco?pid=globalwide_int&clickid=#reqid#
```

Biasanya, karakter ini ada di tautan karena mereka adalah makro, dan secara dinamis diganti dengan nilai, jadi ini bukan masalah besar dan Anda bisa mengabaikan pesannya.

</Accordion>

<div id="what-are-subscriber-parameters-good-for" />

<Accordion title="Apa gunanya parameter pelanggan?">

Parameter pelanggan, yaitu af\_sub1, af\_sub2, ..., af\_sub\_5 dapat digunakan untuk mencatat semua KPI yang berguna. Harap perhatikan bahwa parameter ini di-parsing dan muncul di laporan data lengkap, yang membuat parameter ini sangat berguna untuk menggabungkan atau memfilter data.  

<div id="example-3" />

> 📄 **Contoh**
>
> Aplikasi taksi online, Luber, memiliki materi iklan dengan 3 templat warna: biru, kuning, dan merah. Linda, pemasar seluler Luber ingin menguji templat warna mana yang menghasilkan lebih banyak penginstalan. Untuk melakukannya, dia menambahkan `&af_sub3=blue` pada tautan atribusi dari semua iklan biru di SEMUA sumber media non-SRN. Hal yang sama juga dilakukan untuk templat iklan warna kuning dan merah. Dengan ditampilkannya rincian informasi ini di laporan data lengkap, Linda dapat menganalisis keberhasilan berbagai warna templat iklan, dan memilih iklan dengan konversi terbaik.

</Accordion>

<div id="what-limits-are-there-on-campaign-names" />

<Accordion title="Limit apa yang ada di nama kampanye?">

* Panjang maksimal nama kampanye di URL link atribusi dibatasi hingga 100 karakter. Jika melebihi batas, nama kampanye diubah ke: `c_name_exceeded_max_length`
* Nama kampanye tidak boleh dimulai dari atau diakhiri dengan spasi putih, karena dapat menyebabkan perbedaan di dashboard dan laporan

</Accordion>

<div data-zendesk-anchors="01H8GN1XXC5T2ENFHBK0G4WQ1P=overview attribution-link-parameters=parameter-link-atribusi 01H8GN1XXDX1XMQ1GJTHCP425D=parameter-link-atribusi attribution-link-parameters%E2%80%94ua-and-retargeting=parameter-tautan-atribusi--ua-dan-penargetan-ulang 01H8GN1XXDEWPB2MPP3KJVPRJV=parameter-tautan-atribusi--ua-dan-penargetan-ulang af_sub%5Bn%5D%C2%A0%0An15-example-af_sub1=af_sub-n-n15-example-af_sub1 %5Bdeprecated%5D-af_os=deprecated--af_os attribution-link-parameters%E2%80%94retargeting-only=parameter-tautan-atribusi-khusus-penargetan-ulang 01H8GN1XXD9X7CWZJN43PSS94R=parameter-tautan-atribusi-khusus-penargetan-ulang ad-type-parameters=parameter-jenis-iklan 01H8GN1XXETQEYT39F05ZYX4E2=parameter-jenis-iklan ad-type-af_ad_type=jenis-iklan-af_ad_type 01H8GN1XXEPEZ53C3XFB601838=jenis-iklan-af_ad_type androidspecific-parameters=parameter-khusus-android 01H8GN1XXEE9RGSB1H72H025Z4=parameter-khusus-android iosspecific-parameters=parameter-spesifik-ios 01H8GN1XXESJ9VE3W8CYKRFFYX=parameter-spesifik-ios af_ios_fallback-%5Bdeprecated%5D=af_ios_fallback--deprecated 01H8GN1XXEFRSQSERTB6ARC773=contoh custom-parameters=parameter-kustom 01H8GN1XXEB58JN4SV9HX1ZV6S=parameter-kustom 01H8GN1XXE8EXMMKDZMJ2WNNH5=partner-id-pid-parameter avoid-common-pid-issues=hindari-masalah-pid-umum 01H8GN1XXEXTGC4M8AMJ256Q9G=hindari-masalah-pid-umum 01H8GN1XXEGNVX9GM5JYBMBGCF=tips 01H8GN1XXEVG65YP782CM37RES=site-id-parameter 01H8GN1XXED2MVSNRXN11KZ955=contoh-1 faq-why-does-traffic-result-in-many-blocked-installs=pertanyaan-umum-mengapa-lalu-lintas-menghasilkan-banyak-penginstalan-yang-diblokir 01H8GN1XXEK0G9TDW8WHWM17HK=pertanyaan-umum-mengapa-lalu-lintas-menghasilkan-banyak-penginstalan-yang-diblokir levels-of-data-granularity=tingkat-perincian-data 01H8GN1XXE4RF9J0APAAKD1WEG=tingkat-perincian-data 01H8GN1XXEHPFKX7V0RRW2MH2G=contoh-2 01H8GN1XXEBTW3XRGNZ3A8ZZJP=traits-and-limitations 01H8GN1XXEND9X8YVRQE1YFA5W=should-i-use-lower-or-upper-case-letters-for-parameters 01H8GN1XXER749PH4Z14A7AJ0F=is-the-appsflyer-attribution-link-dynamic-or-static 01H8GN1XXEPQTY0XNW6EZSA9ZN=what-is-this-play-store-error-message 01H8GN1XXFYAFYFX9MNBP6D35B=what-are-subscriber-parameters-good-for 01H8GN1XXFEFA498J22GRF5F8G=contoh-3 01H8GN1XXFS1DFS3HAHVTVG93A=what-limits-are-there-on-campaign-names" />
