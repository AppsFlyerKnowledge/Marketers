---
title: Laporan data lengkap SKAN
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-08T20:54:55Z'
  edited_at: '2023-11-27T11:06:08Z'
  id: 360014261518
  locale: id
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/id/articles/360014261518
---
> **Sekilas:** Laporan data lengkap SKAN berisi data tingkat baris yang dihasilkan setelah menerjemahkan dan mendekode postback yang diterima AppsFlyer dari iOS, serta postback SKAN lengkap. Data tersedia melalui <Anchor target="_blank" href="/marketers/id/docs/data-locker-for-marketers">Data Locker</Anchor> dan <Anchor target="_blank" href="/marketers/id/docs/push-api-streaming-raw-data">Push API</Anchor>. Jika paket langganan Anda menyertakan data lengkap, langganan Data Locker tidak diperlukan.

<div id="skan-raw-data-reports" />

## Laporan data lengkap SKAN

Prinsip-prinsip: 

* **Data disediakan oleh:**
  * **Data Locker**
    * **Catatan**! Tersedia untuk akun yang memiliki langganan data lengkap. Artinya, tidak perlu berlangganan Data Locker. Jika saat ini Anda tidak menggunakan Data Locker, pengguna admin harus mengonfigurasi Data Locker dan mengaktifkan laporan SKAN. Untuk melakukannya, buka **Integrasi** > **Data Locker**. Pilih laporan SKAN.
    * **Tingkat keaktualan data**: Harian. Data terdapat dalam folder j=23 pada tanggal postback diterima oleh AppsFlyer.Contoh: Jika postback diterima pada hari Senin, maka akan diproses setelah hari tersebut berakhir. Pemrosesan selesai, pada hari Selasa pukul 12.00 UTC, data ditulis ke folder Senin j=23.
  * **API Push**
    * Keaktualan data: Lihat <Anchor target="_blank" href="/marketers/id/docs/push-api-streaming-raw-data">Push API untuk data SKAN</Anchor>.
* **Tanggal penginstalan**: Diambil dari waktu kedatangan postback oleh AppsFlyer sebagai berikut:
  * Jika postbacknya adalah SKAN V4, rumus tanggal instalasinya adalah: Tanggal instalasi = waktu kedatangan postback - [akumulasi panjang jendela] - [rata-rata penundaan postback].
    * Postback 1: tanggal penginstalan = waktu kedatangan postback - 48j - 36j
    * Postback 2: tanggal penginstalan = waktu kedatangan postback - 168j - 84j
    * Postback 3: tanggal penginstalan = waktu kedatangan postback - 840j - 84j
  * Jika postbacknya adalah SKAN V3, maka rumus tanggal instalasinya adalah: Tanggal instalasi = waktu kedatangan postback - 36 jam - [rata-rata rentang aktif terakhir]. 
    * Defaultnya [rata-rata rentang aktif terakhir] adalah 12 jam.
    * Untuk nilai konversi 0, rata-rata rentang aktif terakhir ditetapkan ke 0.
  * Google memperkirakan sendiri waktu penginstalan dan AppsFlyer menggunakan waktu penginstalan tersebut. **Catatan**: Google memerlukan waktu hingga 13 hari untuk melaporkan penginstalan. <Anchor target="_blank" href="/marketers/id/docs/get-skan-postback-data-from-google-ads#dapatkan-data-postback-skan-dari-google-ads">Pelajari lebih lanjut</Anchor>

Jenis laporan yang tersedia adalah:

* **Postback perangkat**: 1 postback perangkat per instalasi atau pengunduhan ulang yang diterima dari perangkat iOS.
* **Data lengkap SKAN**:
  * AppsFlyer mendekode dan menerjemahkan postback perangkat menjadi catatan data lengkap.
  * Setiap postback menghasilkan catatan penginstalan atau pengunduhan ulang dan catatan in-app event.
  * Jumlah catatan in-app event bergantung pada nilai konversi (CV) sebagai berikut:
    * CV = 0, kosong, atau nol: Tidak ada catatan dalam aplikasi yang dibuat.
    * Rentang CV:
      * 1-63: Untuk nilai halus SKAN 3, dan SKAN 4 periode waktu 1, ini adalah jumlah catatan dalam aplikasi, bergantung pada pengaturan pengukuran Anda.
      * Rendah, sedang, atau tinggi: Untuk nilai kasar SKAN 4, ini adalah jumlah catatan dalam aplikasi, bergantung pada pengaturan pengukuran Anda.

**Mengapa beberapa bidang kosong?** Hal ini terjadi karena salah satu alasan berikut:

* Bidang pengayaan yang tidak wajib seperti campaign\_name, ad\_network\_campaign, ip yang tidak disediakan oleh jaringan iklan.
* Apple menahan data karena kebijakan ambang batas Apple. Bidang seperti source\_app\_id, skad\_campaign\_id, skad\_conversion\_value.

<div id="decoded-event::5dac9cbb" />

<div id="decoded-event::b8f2b4a4" />

<div id="decoded-event::5c7e459f" />

<div id="decoded-event" />

<div id="postback::315d5a62" />

<div id="postback" />

<div id="skan-raw-data-report-format-and-content" />

## Format dan konten laporan data lengkap SKAN

<div id="raw-data-report-types" />

<Accordion title="Jenis laporan data lengkap">

<Table>
  <thead>
    <tr>
      <th>
        Jenis laporan
      </th>
      <th>
        Nama laporan
      </th>
      <th>
        Deskripsi
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Postback
      </td>
      <td>
        Postback (postingan balik)
      </td>
      <td>
        Postback dikirim oleh iOS ke jaringan iklan. Postback, setelah diperkaya oleh jaringan iklan, diteruskan ke AppsFlyer. [Unduh contoh postback](https://docs.google.com/spreadsheets/d/e/2PACX-1vRfFFmj1YV1c73Wbar2VOiKWml6VmsyFvQuydXTPUOO4zXVKmwtw6nup9vKNtNwou2z8IqNpcF4yP6c/pub?gid=1225544365&single=true&output=csv) (CSV).

        Catatan: Postback tidak disertakan ketika did\_win=false.

        **Nama topik di Data Locker**: skad\_postbacks
      </td>
    </tr>
    <tr>
      <td>
        Postback
      </td>
      <td>
        Salinan postback (langsung dari Apple)
      </td>
      <td>
        Postback dikirim langsung oleh iOS ke AppsFlyer.

        Tersedia mulai iOS 15+ dan mewajibkan pemasang iklan untuk mengonfigurasi aplikasi untuk <Anchor target="_blank" href="/marketers/id/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">mengirim postback pemenang</Anchor> ke AppsFlyer. [Unduh contoh salinan postback](https://docs.google.com/spreadsheets/d/e/2PACX-1vSu0c3gYoIHe2k6_M3cngSFzc-txQvEN38X7Ig7qhXYPg8uBUzyyPqlSwDMugvZS_tUrFjtY8AGYKrh/pub?gid=1225544365&single=true&output=csv) (CSV).

        Catatan: Topik ini hanya berisi postback pemenang.

        **Nama topik di Data Locker**: skad\_postbacks\_copy
      </td>
    </tr>
    <tr>
      <td>
        Event yang didekodekan
      </td>
      <td>
        Instalasi
      </td>
      <td>
        **Penginstalan aplikasi pertama kali**

        SKAN melaporkan *redownload=false*. Artinya, ini adalah pertama kalinya pengguna yang diwakili oleh ID Apple mengunduh aplikasi tersebut.  
        [Unduh contoh penginstalan](https://docs.google.com/spreadsheets/d/e/2PACX-1vS4rNJAio8Ub2cffUEiYhzdavVfXaJAD6OpjhRBjVpGQsAlibOWCkZpfLl29n1OCDBZ2eToO4_gOvbl/pub?gid=1472391837&single=true&output=csv) (CSV).

        **Nama topik di Data Locker**: skad\_installs
      </td>
    </tr>
    <tr>
      <td>
        Event yang didekodekan
      </td>
      <td>
        Mengunduh ulang
      </td>
      <td>
        **Penginstalan aplikasi yang bukan merupakan penginstalan pertama kali**

        SKAN melaporkan *redownload=true*. Artinya, ini bukan yang pertama kalinya pengguna yang diwakili oleh ID Apple mengunduh aplikasi tersebut.  
         Laporan ini memiliki struktur yang sama dengan penginstalan.

        **Nama topik di Data Locker**: skad\_redownloads
      </td>
    </tr>
    <tr>
      <td>
        Event yang didekodekan
      </td>
      <td>
        In-app event
      </td>
      <td>
        **In-app event**

        Mulai tanggal 21 Juli 2021, ada perubahan pada cara kami menyediakan data lengkap in-app event seperti yang dijelaskan secara rinci dalam tabel.

        Jumlah catatan in-app event bergantung pada pengaturan pengukuran Anda.

        [Unduh contoh in-app event](https://docs.google.com/spreadsheets/d/e/2PACX-1vRwhxOmZwTkOr9uNFN0d4Rk2jFpipONoB8KzIZI5Tw12IvoLirj07QUdI9RJoL9rZYFSN1PvT-W6vP0/pub?gid=1454741057&single=true&output=csv) (CSV).

        **Nama topik di Data Locker**: skad\_inapps

        Berlaku untuk postback iOS yang diterima mulai 21 Juli 2021:

        | Jenis pengukuran | Deskripsi |
        | --- | --- |
        | Pendapatan | * Pendapatan pengguna tertentu. Jika pendapatan > 0, catatan berisi bidang skad\_revenue dan event\_name.<br />* Bidang min\_revenue dan max\_revenue diisi dengan nilai rentang konversi khusus Anda. |
        | Konversi dalam aplikasi dan event funnel (corong) | * Catatan untuk setiap event konversi unik yang dilakukan. Bidang event\_name diisi sesuai dengan itu. Jika tidak ada event yang dilakukan, tidak ada catatan.<br />* Event konversi memiliki min\_event\_counter = 0 dan max\_event\_counter = 1. |
        | Interaksi dalam aplikasi | Untuk menentukan berapa kali pengguna melakukan in-app event tertentu, gunakan rumus`[pembulatan ke atas (min_event_counter + max_event_counter) / 2]` |

        Berlaku untuk postback iOS yang diterima hingga 20 Juli 2021:

        | Jenis pengukuran | Jumlah catatan | Deskripsi |
        | --- | --- | --- |
        | Pendapatan | 0-1 | Jika pendapatan > 0, catatan berisi bidang skad\_revenue dan event\_name. |
        | Konversi | 0-6 | Catatan untuk setiap event konversi unik yang dilakukan. Bidang event\_name diisi sesuai dengan itu. Jika tidak ada event yang dilakukan, tidak ada catatan. |
        | Interaksi | 0-63 | Jumlah catatan mewakili berapa kali pengguna melakukan event interaksi. Jika pengguna tidak berinteraksi, tidak ada catatan interaksi. |
        | Kustom | 0-tanpa batas | Menurut skema konversi khusus Anda. |
      </td>
    </tr>
    <tr>
      <td>
        Event yang didekodekan
      </td>
      <td>
        Dimensi iklan SRN
      </td>
      <td>
        * Laporan berisi event Meta ads dengan kampanye, adset, dan perincian iklan. Setiap baris dalam laporan dapat berupa penginstalan atau in-app event.
        * Adset dan perincian iklan tidak disertakan dalam postback SKAN dari Meta ads. Data ini unik untuk laporan ini, dan tidak ditampilkan di dashboard SKAN, API Performa, dan laporan Data Locker SKAN lainnya.
        * Laporan tidak memiliki skema. Opsi seleksi bidang Data Locker tidak berlaku.
        * Praktik terbaik: Jangan menggabungkan atau membandingkan data dari laporan ini dengan laporan SKAN lainnya, karena mungkin ada perbedaan antara laporan ini, yang menggunakan data yang didekodekan oleh SRN, dan laporan lain, yang menggunakan data yang didekodekan oleh AppsFlyer. Perbedaan ini dapat disebabkan oleh perbedaan zona waktu, perbedaan skema SRN, atau kesalahan dalam memetakan in-app event ke CV dalam integrasi SRN.
        * <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTZjIpqZJxHY9WpIdf9OeDCVQYzM_fLmrpB1oAt3S-MbJTKueOJODwwl6Pz3M0SCAbCFIdMlshOayrw/pub?output=xlsx">Unduh contoh dimensi iklan SRN</Anchor> (CSV).

        **Nama topik di Data Locker**: skad\_srn\_advertising\_dimensions
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="raw-data-field-format-types" />

<Accordion title="Jenis format bidang data lengkap">

<div id="field-formats" />

#### Format bidang

| Nama format | Deskripsi |
| --- | --- |
| String [n] | Panjang maksimal string Kami biasanya tidak menerapkan batasan panjang bidang pada penerimaan data tetapi data mungkin terpotong setelahnya. |
| String waktu | String berformat`hh-bb-tttt jj:mm:dd`. Misalnya, `17-09-2019 00:09:25` |
| Enum [n] | Bidang enum hanya dapat berisi nilai tertentu. Misalnya, Mata uang biaya memiliki 3 karakter dan hanya dapat berisi kode mata uang seperti yang ditentukan |
| stempel waktu | Stempel waktu UNIX 10 digit. Contoh:<br /><br />4 Agustus 2020, 07.25 UTC diterjemahkan menjadi `"timestamp": "1596525944"` |
| Boolean | Nilai bidang dapat berupa `TRUE` atau `FALSE` |
| Bilangan Bulat | Bilangan Bulat |
| Float | Bilangan mengambang nyata yang dapat memiliki koma desimal dan nilai setelah koma desimal. |

</Accordion>

<div id="fields-available-in-postback-and-postback-copy-reports" />

<Accordion title="Bidang tersedia dalam postback dan laporan salinan postback">

<table><thead><tr><th>Nama kolom</th><th>Sumber atau versi awal SKAN iOS</th><th>Deskripsi</th><th>Format</th><th>Tersedia dalam salinan postback </th></tr></thead><tbody><tr><td><p>ad_network_campaign_id</p></td><td>Ad Network</td><td>ID kampanye dilaporkan oleh jaringan iklan ke AppsFlyer</td><td>String</td><td>Tidak</td></tr><tr><td><p>ad_network_campaign</p><p>_name</p></td><td>Ad Network</td><td><p>Nama kampanye dilaporkan oleh jaringan iklan ke AppsFlyer</p></td><td>String</td><td>Tidak</td></tr><tr><td><p>ad_network_timestamp</p></td><td>Ad Network</td><td><p>Waktu jaringan iklan menerima postback.</p><p>Dalam kasus Google Ads, waktu diperoleh dari waktu klik terakhir yang dilaporkan oleh Google.</p></td><td>stempel waktu</td><td>Tidak</td></tr><tr><td><p>app_id</p></td><td>AppsFlyer</td><td>ID Aplikasi (aplikasi pemasang iklan) dengan ID awalan.</td><td>String</td><td>Ya</td></tr><tr><td><p>city</p></td><td>AppsFlyer</td><td>Mulai 30 Agustus 2021, selalu null </td><td>String</td><td>Tidak</td></tr><tr><td><p>country_code</p></td><td>Ad Network</td><td> </td><td>String</td><td>Tidak</td></tr><tr><td>dma</td><td> </td><td>Mulai 30 Agustus 2021, selalu null </td><td>String</td><td>Tidak</td></tr><tr><td><p>postal_code</p></td><td> </td><td>Mulai 30 Agustus 2021, selalu null  </td><td>String</td><td>Tidak</td></tr><tr><td><p>Wilayah</p></td><td>AppsFlyer</td><td>Menurut country_code yang dilaporkan</td><td>String</td><td>Tidak</td></tr><tr><td><p>skad_ad_network_id</p></td><td>1.0 </td><td><p>Beberapa SRN tidak membagikan ID mereka, dan bidangnya dibiarkan kosong. Misalnya Twitter. </p></td><td>String</td><td><p>Ya </p></td></tr><tr><td><p>skad_attribution_signature</p></td><td>1.0</td><td> </td><td>String</td><td>Ya</td></tr><tr><td>skad_campaign_id</td><td>1.0</td><td>ID kampanye yang digunakan untuk menayangkan iklan. Rentang: 0-100</td><td>String</td><td>Ya</td></tr><tr><td>skad_conversion_value</td><td>2.0 </td><td><p>Nilai konversi yang dilaporkan oleh iOS. Rentang 0-63.</p><p>Jika null, iOS tidak mengisi bidang\*\* </p></td><td>Bilangan Bulat</td><td>Ya</td></tr><tr><td>skad_redownload</td><td>2.0</td><td>Jika true, aplikasi telah diunduh ulang</td><td><p>Boolean</p></td><td><p>Ya</p></td></tr><tr><td>skad_source_app_id</td><td>2.0</td><td><p>ID situs. Aplikasi menerbitkan iklan. Bidang ini identik dengan source_app_id</p><p>Populasi bidang bergantung pada ambang batas privasi\*\*</p></td><td>String</td><td>Ya</td></tr><tr><td>skad_transaction_id</td><td>1.0</td><td> </td><td>String</td><td>Ya</td></tr><tr><td>skad_version</td><td>2.0</td><td> </td><td>String</td><td>Ya</td></tr><tr><td>tanda waktu</td><td>Ad Network</td><td><p>Waktu AppsFlyer menerima postback SKAN. </p></td><td>String waktu</td><td>Ya</td></tr><tr><td>ad_network_name</td><td>Ad Network</td><td><p>Nama jaringan iklan yang dilaporkan oleh jaringan iklan ke AppsFlyer. </p><ul><li>Jika bidang ini kosong, jaringan iklan tidak (tidak dapat) mengisinya.</li><li>Anda dapat menentukan nama jaringan iklan menggunakan skad_ad_network_id. Gunakan <a href="./skan-integrated-partners-list#zd-apple-skadnetwork-ids-of-ad-networks" target="_blank">tabel</a> ini untuk melakukannya. </li></ul></td><td>String</td><td>Tidak</td></tr><tr><td>ip</td><td> </td><td><p>Alamat IP dalam pesan HTTP perangkat iOS yang mengirimkan postback.</p><p>Bidang ini diisi jika jaringan iklan memberi kami alamatnya.</p><p>Catatan! SDK tidak terlibat dalam mendapatkan alamat.</p></td><td>String</td><td>Tidak</td></tr><tr><td><p>skad_app_id</p></td><td>1.0</td><td> </td><td>String</td><td>Tidak</td></tr><tr><td><p>source_app_id</p></td><td>AppsFlyer</td><td>ID situs. Aplikasi menerbitkan iklan. Kolom ini identik dengan skad_source_app_id</td><td>String</td><td>Tidak</td></tr><tr><td><p>ad_network_adset_id</p></td><td>Ad Network</td><td> </td><td>String</td><td>Tidak</td></tr><tr><td><p>ad_network_adset_name</p></td><td>Ad Network</td><td> </td><td>String</td><td>Tidak</td></tr><tr><td><p>ad_network_ad_name</p></td><td>Ad Network</td><td> </td><td>String</td><td>Tidak</td></tr><tr><td><p>ad_network_ad_id</p></td><td>Ad Network</td><td> </td><td>String</td><td>Tidak</td></tr><tr><td><p>did_win</p></td><td>3.0 (iOS 14.6)</td><td><p>Digunakan untuk membedakan antara kampanye <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">yang berkontribusi atau dikaitkan</a> dengan penginstalan. </p><ul><li>Jika benar, kampanye diatribusikan untuk menghadirkan penginstalan.</li><li>Jika salah, kampanye dianggap berkontribusi terhadap penginstalan, tetapi tidak disertakan dalam dashboard atau laporan SKAN mana pun.</li><li>Jika null, iOS tidak mengisi bidang karena <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes" target="_blank">versi iOS atau SKAdNetwork lama</a>.</li></ul></td><td>Boolean</td><td>Ya</td></tr><tr><td><p>fidelity_type</p></td><td>2.2 (iOS 14.5)</td><td><p><span>Membedakan antara opsi <a href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions" target="_blank">presentasi iklan</a> yang memengaruhi atribusi. Diindikasikan menggunakan nilai 0 dan 1 sebagai berikut: </span></p><ul><li><span>Iklan view-though (0)</span></li><li><span>Iklan yang dirender StoreKit (1)</span></li></ul><p>Abaikan nilai bidang jika versi SKAN sebelum 2.2</p></td><td>Bilangan Bulat</td><td>Ya</td></tr><tr><td><p>ad_network_source_app_id</p></td><td>Ad Network</td><td><span>ID aplikasi penerbit yang dilaporkan oleh jaringan iklan. Gunakan untuk membantu menyamakan biaya; dilaporkan oleh jaringan iklan. Aplikasi penerbit memberikan dasar untuk data ini. </span></td><td>String</td><td>Tidak</td></tr><tr><td><p>ad_network_channel</p></td><td>Ad Network</td><td> </td><td>String</td><td>Tidak</td></tr><tr><td><p>af_prt</p></td><td>Ad Network</td><td> </td><td>String</td><td>Tidak</td></tr><tr><td><p><span>skad_postback_sequence_index</span></p></td><td><span>4.0 (iOS 16.2)</span></td><td><ul><li><span>Nilai mewakili jendela SKAN, <code>0</code>,<code>1</code>, atau<code>2</code>. </span></li><li><span>Untuk SKAN 3 nilainya adalah<code>0</code>.</span></li></ul></td><td><span>Bilangan Bulat</span></td><td><span>Ya</span></td></tr><tr><td><span>skad_coarse_conversion_value</span></td><td><p><span>4.0 (iOS 16.2)</span></p></td><td><ul><li><span>Nilainya bisa<code>low</code>,<code>medium</code>, atau<code>high</code>. </span></li><li><span>Untuk SKAN 3 nilainya<code>null</code>.</span></li></ul></td><td><span>String</span></td><td><span>Ya</span></td></tr><tr><td><span>skad_source_identifier</span></td><td><span>4.0 (iOS 16.2)</span></td><td><ul><li><span>Nilai bisa sampai 4 digit. </span></li><li><span>Untuk SKAN 3 nilainya adalah<code>null</code>. </span></li></ul></td><td><span>String</span></td><td><span>Ya</span></td></tr><tr><td><span>skad_source_domain</span></td><td><span>4.0 (iOS 16.2)</span></td><td><ul><li><span>Nilai mewakili sumber iklan web yang dapat diatribusikan. </span></li><li><span>Untuk SKAN 3 nilainya<code>null</code>.</span></li></ul></td><td><span>String</span></td><td><span>Ya</span></td></tr><tr><td><span>ad_network_creative</span></td><td><span>Ad Network</span></td><td><ul><li><span>Nilai didasarkan pada pengayaan data yang diterima dari jaringan iklan. </span></li><li><span>Untuk SKAN 3 nilainya<code>null</code>.</span></li></ul></td><td><span>String</span></td><td><span>Tidak</span></td></tr></tbody><tfoot><tr><td colspan="4"><p>\*\* Apple menentukan apakah bidang diisi menggunakan mekanisme ambang batas privasi </p></td><td></td></tr></tfoot></table>

</Accordion>

<div id="fields-available-in-decoded-event-reports" />

<Accordion title="Bidang tersedia dalam laporan event yang didekodekan">

<table><thead><tr><th>Nama kolom</th><th>Sumber</th><th>Deskripsi</th><th>Format</th><th>Termasuk dalam laporan dimensi iklan SRN</th></tr></thead><tbody><tr><td>ad_network_campaign_id</td><td>Ad Network</td><td>ID kampanye dilaporkan oleh jaringan iklan ke AppsFlyer</td><td>String</td><td>Ya</td></tr><tr><td>ad_network_campaign<br/>_name</td><td>Ad Network</td><td>Nama kampanye dilaporkan oleh jaringan iklan ke AppsFlyer</td><td>String</td><td>Ya</td></tr><tr><td>ad_network_timestamp</td><td>Ad Network</td><td><p>Waktu postback diterima oleh jaringan iklan</p><p>Dalam kasus Google Ads, bidang ini tidak diisi. </p></td><td><p>stempel waktu</p><p>(string waktu untuk laporan dimensi iklan SRN)</p></td><td>Ya</td></tr><tr><td>app_id</td><td>iOS</td><td>ID aplikasi (aplikasi pemasang iklan)</td><td>String</td><td>Ya</td></tr><tr><td>city</td><td> </td><td>Mulai 30 Agustus 2021, selalu null </td><td>String</td><td>Tidak</td></tr><tr><td>country_code</td><td>Ad Network</td><td> </td><td>String</td><td>Tidak</td></tr><tr><td>dma</td><td> </td><td>Mulai 30 Agustus 2021, selalu null </td><td>String</td><td>Tidak</td></tr><tr><td>event_name</td><td>AppsFlyer</td><td><p>Nama in-app event seperti yang dikonfigurasi di AppsFlyer.</p><p>Untuk laporan SRN ___, ini adalah nama in-app event yang dikonfigurasi di Meta ads.</p></td><td>String</td><td>Ya</td></tr><tr><td>event_uuid</td><td>AppsFlyer</td><td>Pengidentifikasi random unik yang memungkinkan mitra mengidentifikasi postback duplikat</td><td>String</td><td>Tidak</td></tr><tr><td>install_date</td><td>iOS</td><td>Diperkirakan oleh AppsFlyer berdasarkan waktu kedatangan postback.</td><td>String waktu</td><td>Tidak</td></tr><tr><td>install_type</td><td>iOS</td><td>Penginstalan baru</td><td>String</td><td>Tidak</td></tr><tr><td>ip</td><td>iOS</td><td><p>Alamat IP dalam pesan HTTP perangkat iOS yang mengirimkan postback.</p><p>Bidang ini diisi jika jaringan iklan memberi kami alamatnya.</p><p>Catatan! SDK tidak terlibat dalam mendapatkan alamat. </p></td><td>String</td><td>Tidak</td></tr><tr><td>media_source</td><td>iOS</td><td>Jaringan iklan diatribusikan menggunakan nama jaringan AppsFlyer</td><td>String</td><td>Ya</td></tr><tr><td>postal_code</td><td> </td><td>Mulai 30 Agustus 2021, selalu null </td><td>String</td><td>Tidak</td></tr><tr><td>Wilayah</td><td>AppsFlyer</td><td>Ditentukan berdasarkan country_code</td><td>String</td><td>Tidak</td></tr><tr><td>skad_ad_network_id</td><td>iOS</td><td>ID jaringan iklan yang dikirimi postback</td><td>String</td><td>Tidak</td></tr><tr><td>skad_ambiguous_event</td><td>AppsFlyer</td><td>Jika benar, postback iOS diterima selama 72 jam pertama setelah pemasang iklan mengubah pengaturan SKAN di dashboard. Karena berbagai timer yang digunakan oleh SKAN, AppsFlyer tidak dapat memetakan event secara akurat.</td><td>Boolean</td><td>Tidak</td></tr><tr><td>skad_attribution_signature</td><td>iOS</td><td> </td><td>String</td><td>Tidak</td></tr><tr><td>skad_campaign_id</td><td>iOS</td><td>ID kampanye yang digunakan untuk menayangkan iklan. Rentang: 0-100</td><td>Bilangan Bulat</td><td>Tidak</td></tr><tr><td>skad_conversion_value</td><td>iOS</td><td><p>Nilai konversi yang dilaporkan oleh iOS. Rentang 0-63.</p><p>Jika null, iOS tidak mengisi bidang\*\*</p></td><td>Bilangan Bulat</td><td>Tidak</td></tr><tr><td>skad_mode</td><td>AppsFlyer</td><td><p>Mode pengukuran konversi yang digunakan untuk mendekode postback iOS. Opsi:</p><ul><li>custom_decode</li><li>pendapatan</li><li>event</li><li>skan4</li><li>custom_encode</li><li>engagement</li></ul></td><td>String</td><td>Tidak</td></tr><tr><td>skad_redownload</td><td>iOS</td><td>Jika benar, aplikasi telah diunduh ulang</td><td>Boolean</td><td>Tidak</td></tr><tr><td>skad_revenue</td><td>iOS</td><td>Jumlah pendapatan event dalam USD.</td><td>Float</td><td>Tidak</td></tr><tr><td>skad_source_app_id</td><td>iOS</td><td><p>ID situs - aplikasi yang menerbitkan iklan.</p><p>Populasi bidang bergantung pada ambang batas privasi\*\*</p></td><td>String</td><td>Tidak</td></tr><tr><td>skad_transaction_id</td><td>iOS</td><td>-</td><td>String</td><td>Tidak</td></tr><tr><td>skad_version</td><td>iOS</td><td>-</td><td>String</td><td>Tidak</td></tr><tr><td>tanda waktu</td><td>iOS</td><td><p><span>Waktu AppsFlyer menerima postback SKAN</span>.</p><p>Untuk Google Ads dan Meta ads, inilah saatnya AppsFlyer mendapatkan data dari API Google dan API Meta ads berturut-turut.</p></td><td><p>stempel waktu</p><p>(string waktu untuk laporan dimensi iklan SRN)</p></td><td>Ya</td></tr><tr><td>event_value</td><td>S2S</td><td><p>Nilai default: null</p><p>Berisi string yang diatur oleh aplikasi yang menerapkan dekode khusus.</p><p>Pemasang iklan mengonsumsi ini dalam sistem mereka. AppsFlyer tidak memanfaatkannya. </p></td><td>String (JSON)</td><td>Tidak</td></tr><tr><td><p>ad_network_adset_id</p></td><td>Ad Network</td><td> </td><td>String</td><td>Ya</td></tr><tr><td><p>ad_network_adset_name</p></td><td>Ad Network</td><td> </td><td>String</td><td>Ya</td></tr><tr><td><p>ad_network_ad_name</p></td><td>Ad Network</td><td> </td><td>String</td><td>Ya</td></tr><tr><td><p>ad_network_ad_id</p></td><td>Ad Network</td><td></td><td>String</td><td>Ya</td></tr><tr><td><p>skad_did_win (1)</p></td><td>3.0 (iOS 14.6)</td><td><p>Digunakan untuk membedakan antara kampanye <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">yang berkontribusi atau dikaitkan</a> dengan penginstalan. </p><ul><li>Jika benar, kampanye diatribusikan untuk menghadirkan penginstalan.</li><li>Jika false, kampanye dianggap berkontribusi terhadap penginstalan, tetapi tidak disertakan dalam dashboard atau laporan SKAN mana pun.</li><li>Jika null, iOS tidak mengisi bidang karena <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes" target="_blank">versi iOS atau SKAdNetwork lama</a>.</li></ul></td><td>Boolean</td><td>Tidak</td></tr><tr><td><p>skad_fidelity_type (1)</p></td><td>2.2 (iOS 14.5)</td><td><p><span>Membedakan antara opsi <a href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions" target="_blank">presentasi iklan</a> yang memengaruhi atribusi. Diindikasikan menggunakan nilai 0 dan 1 sebagai berikut: </span></p><ul><li><span>Iklan view-though (0)</span></li><li><span>Iklan yang dirender StoreKit (1)</span></li></ul><p>Abaikan nilai bidang jika versi SKAN sebelum 2.2</p></td><td>Bilangan Bulat</td><td>Ya</td></tr><tr><td><p>ad_network_source_app_id (1)</p></td><td>Ad Network</td><td><span>ID aplikasi penerbit yang dilaporkan oleh jaringan iklan. Gunakan untuk membantu mendamaikan biaya; dilaporkan oleh jaringan iklan. Dasar untuk data ini disediakan oleh aplikasi penerbit.</span></td><td>String</td><td>Tidak</td></tr><tr><td><p>ad_network_channel (1)</p></td><td>Ad Network</td><td> </td><td>String</td><td>Tidak</td></tr><tr><td><p>af_prt (1)</p></td><td>Ad Network</td><td> </td><td>String</td><td>Tidak</td></tr><tr><td><p>min_revenue </p></td><td>AppsFlyer</td><td>Lihat catatan (4)</td><td>Nomor asli</td><td>Tidak</td></tr><tr><td><p>max_revenue </p></td><td>AppsFlyer</td><td>Lihat catatan (4)</td><td>Nomor asli</td><td>Tidak</td></tr><tr><td><p>event_revenue</p></td><td>AppsFlyer</td><td><p>Rumus: [jumlah nilai untuk event tertentu dalam USD]/[Jumlah event yang terjadi pada hari tertentu]</p></td><td>Float</td><td>Ya</td></tr><tr><td><p>min_event_counter</p></td><td>AppsFlyer</td><td>Gunakan untuk menghitung berapa kali pengguna melakukan suatu event. Lihat catatan (3)</td><td>Bilangan Bulat</td><td>Tidak</td></tr><tr><td><p>max_event_counter</p></td><td>AppsFlyer</td><td>Lihat catatan (3)</td><td>Bilangan Bulat</td><td>Tidak</td></tr><tr><td><p>min_time_post_install</p></td><td>AppsFlyer</td><td>Lihat catatan (5)</td><td>Bilangan Bulat</td><td>Tidak</td></tr><tr><td><p>max_time_post_install</p></td><td>AppsFlyer</td><td>Lihat catatan (5)</td><td>Bilangan Bulat</td><td>Tidak</td></tr><tr><td><p>af_attribution_flag</p></td><td>AppsFlyer</td><td><p>Saat mekanisme Single Source of Truth (SSOT) aktif: Jika benar, penginstalan diatribusikan oleh AppsFlyer dan SKAN. Jika salah, penginstalan tidak diatribusikan oleh AppsFlyer. Jika skad_conversion_value adalah null, tandanya adalah benar atau salah (berdasarkan <a href="./skan-modeled-data#null-conversion-values" target="_blank">pemodelan</a>).</p></td><td>Boolean</td><td>Tidak</td></tr><tr><td><p>measurement_window</p></td><td>AppsFlyer</td><td>Durasi jendela aktivitas. Standar 24j. </td><td>Bilangan Bulat</td><td>Tidak</td></tr><tr><td><p>interval</p></td><td>AppsFlyer</td><td>Interval jendela aktivitas. </td><td>Bilangan Bulat</td><td>Tidak</td></tr><tr><td><p>user_agent</p></td><td>AppsFlyer</td><td>Agen pengguna perangkat</td><td>String</td><td>Tidak</td></tr><tr><td><p><span>skad_postback_sequence_index</span></p></td><td><span>4.0 (iOS 16.2)</span></td><td><ul><li><span>Nilai mewakili jendela SKAN, <code>0</code>,<code>1</code>, atau<code>2</code>. </span></li><li><span>Untuk SKAN 3 nilainya adalah<code>0</code>.</span></li></ul></td><td><span>Bilangan Bulat</span></td><td><span>Ya</span></td></tr><tr><td><span>skad_coarse_conversion_value</span></td><td><p><span>4.0 (iOS 16.2)</span></p></td><td><ul><li><span>Nilainya bisa<code>low</code>,<code>medium</code>, atau<code>high</code>. </span></li><li><span>Untuk SKAN 3 nilainya<code>null</code>.</span></li></ul></td><td><span>String</span></td><td><span>Ya</span></td></tr><tr><td><span>skad_source_identifier</span></td><td><span>4.0 (iOS 16.2)</span></td><td><ul><li><span>Nilai bisa sampai 4 digit. </span></li><li><span>Untuk SKAN 3 nilainya adalah<code>null</code>. </span></li></ul></td><td><span>String</span></td><td><span>Ya</span></td></tr><tr><td><span>skad_source_domain</span></td><td><span>4.0 (iOS 16.2)</span></td><td><ul><li><span>Nilai mewakili sumber iklan web yang dapat diatribusikan. </span></li><li><span>Untuk SKAN 3 nilainya<code>null</code>.</span></li></ul></td><td><span>String</span></td><td><span>Ya</span></td></tr><tr><td><span>ad_network_creative</span></td><td><span>Ad Network</span></td><td><ul><li><span>Nilai didasarkan pada pengayaan data yang diterima dari jaringan iklan. </span></li><li><span>Untuk SKAN 3 nilainya<code>null</code>.</span></li></ul></td><td><span>String</span></td><td><span>Tidak</span></td></tr></tbody><tfoot><tr><td colspan="4"><p>\*\* Apple menentukan apakah bidang diisi menggunakan mekanisme ambang batas privasi</p><p>(1) Mulai tanggal 2 Juni 2021, bidang tersebut ditambahkan ke laporan, namun belum tentu diisi.</p><p>(3) Untuk menentukan berapa kali pengguna melakukan in-app event tertentu, gunakan rumus: <code>[pembulatan ke atas (min_event_counter + max_event_counter) / 2]</code> . Catatan! <mark> Anda harus melakukan pembulatan atas untuk bilangan bulat terdekat.</mark><br/>Contoh:<br/>A. Jika min = 0 dan maks = 1 rata-ratanya adalah 0,5; pembulatan ke atas memberi hasil 1.<br/>B. Jika min = 5 dan maks = 10, maka rata-ratanya adalah 7,5; pembulatan ke atas mengembalikan hasil 8.</p><p>(4) Pendapatan selalu disediakan di bidang <code>skad_revenue</code>. Jika Anda menggunakan<span> mode SKAN 4 atau </span><span><a href="./skan-conversion-studio" target="_blank">Kustom</a></span>, rentang bucket yang terkait dengan event dan digunakan untuk menghitung skad_revenue dideskripsikan oleh min_revenue dan max_revenue.</p><p>(5)</p><ul><li>Dalam Konversi khusus: AppsFlyer menghitung waktu penginstalan sebagai waktu kedatangan postback - 36j - rata-rata (min_time_post_install + max_time_post_install). Namun, jika CV=0 maka rata-rata (min_time_post_install + max_time_post_install) dianggap sebagai 0. </li><li>Dalam konversi Decode: min_time_post_install adalah satu jam lebih sedikit dari yang ditetapkan dalam max_time_post_install yang sama dengan <a href="./skan-cv-decode-map-your-cv-to-events#zd-decode-csv-file-specification" target="_blank">hours_from_install</a> yang Anda tetapkan dalam pemetaan konversi Decode Anda. </li></ul></td><td></td></tr></tfoot></table>

</Accordion>

<div id="additional-information" />

## Informasi tambahan

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Sifat | Catatan |
| --- | --- |
| Akses jaringan iklan | Jaringan iklan disediakan dengan postback |
| Akses agensi | Tidak tersedia |
| Transparansi agensi | T/A |
| Zona waktu | UTC |
| Mata uang | USD |
| Data organik | Berdasarkan data event SDK. Misalnya, metrik penginstalan organik dihitung sebagai berikut: Data semua penginstalan yang dilaporkan oleh SDK dikurangi penginstalan non-organik yang dilaporkan oleh SKAN. |
| Data non-organik | Berdasarkan postback SKAN |
| Keaktualan data | Harian. Waktu SKAN berarti iOS melaporkan penginstalan 24-48 jam setelah jendela ditutup. |
| Data historis | Terbatas pada periode waktu ketersediaan Data Locker. |
| Akses pengguna akun | Tersedia. Menurut izin akun |

</Accordion>

<div id="see-also" />

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-solution-guide#reporting-options">Laporan SKAN yang tersedia (panduan solusi SKAN)</Anchor>

<div data-zendesk-anchors="skan-raw-data-reports=laporan-data-lengkap-skan 01H8XHATZB2G6YZ9AJNPRZS59Y=laporan-data-lengkap-skan skan-raw-data-report-format-and-content=format-dan-konten-laporan-data-lengkap-skan 01H8XHATZCJQZTZF0Y5P18XMEA=format-dan-konten-laporan-data-lengkap-skan 01H8XHATZCR5BC2P5TSQTMDY5Q=raw-data-report-types 01H8XHATZC0MST5ASGWDGGK2R8=raw-data-field-format-types field-formats=format-bidang 01H8XHATZCZMNGK72DDE5HS6E9=format-bidang 01H8XHATZC24DH4AYB2C523JDH=fields-available-in-postback-and-postback-copy-reports 01H8XHATZCNXVG0E3MZ9H68AA1=fields-available-in-decoded-event-reports additional-information=informasi-tambahan 01H8XHATZD9D7JBHTFZ095EBD5=informasi-tambahan 01H8XHATZDMV0VN4BDTECGF91K=traits-and-limitations h_01HDNYQBVZP0A6SQASGDRFVFGP=lihat-juga" />
