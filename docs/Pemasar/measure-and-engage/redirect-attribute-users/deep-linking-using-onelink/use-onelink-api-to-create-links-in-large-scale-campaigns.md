---
title: OneLink API
metadata:
  keywords:
    - api
    - Premium
    - Marketers
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Premium
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2018-06-27T12:00:29Z'
  edited_at: '2023-08-09T16:09:08Z'
  id: 360001250345
  locale: id
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/id/articles/360001250345
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Sekilas:** OneLink API membantu Anda melibatkan pengguna akhir dan memanfaatkan media yang dimiliki dengan menghasilkan tautan yang dipersonalisasi dalam kampanye skala besar, melalui SMS, dan masih banyak lagi. Mengharuskan pengiklan dan pengembang untuk menerapkan.

<div id="about-onelink-api" />

## OneLink API

OneLink API digunakan untuk:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/create-onelink-attribution-link">Buat</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-attribution-link">dapatkan</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/update-onelink-attribution-link">perbarui</Anchor>, dan  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/delete-onelink-attribution-link">hapus</Anchor> URL singkat OneLink dengan parameter yang disesuaikan secara otomatis.  
  Parameter dapat berupa:
  * Parameter terkait atribusi, digunakan untuk mengukur dan memantau upaya pemasaran, seperti sumber media, kampanye, dan adset. **Perhatikan**: Parameter sumber media (pid) itu wajib.
  * Parameter personalisasi, yang memungkinkan Anda mengonfigurasi pengalaman pengguna yang disesuaikan saat membuka aplikasi dari tautan yang relevan. Parameter ini memungkinkan Anda mengarahkan pengguna ke konten dalam aplikasi yang disesuaikan, misalnya, laman produk tertentu, kode kupon, atau promosi.
* Izinkan berbagi konten situs web dan aplikasi langsung ke pengguna seluler (sehingga meningkatkan interaksi dan penginstalan seluler).
* Hasilkan banyak tautan atribusi khusus OneLink secara instan.  
  **Catatan** : Untuk tautan rujukan, lihat <Anchor target="_blank" href="/marketers/id/docs/user-invite-attribution">artikel atribusi undangan pengguna</Anchor> .

> 📄 **Contoh**
>
> Feed Me, layanan pengiriman bahan makanan, ingin mengirim tautan yang dipersonalisasi melalui SMS ke pelanggan yang sudah ada untuk mendorong mereka mengunduh aplikasi Feed Me dan membeli pisang. Berdasarkan negara pelanggan, Feed Me menggunakan OneLink REST API untuk membuat URL OneLink kustom yang berisi detail spesifik untuk negara, identitas pengguna, dan penawaran istimewa untuk pisang yang sedang dijual.

Jumlah kueri API OneLink yang dapat Anda buat terbatas tergantung pada jenis akun Anda.Anda dapat melihat berapa banyak kueri yang Anda buat dan berapa banyak yang tersisa, di dashboard OneLink API. 

Anda dapat menghubungi CSM Anda untuk meningkatkan batas kueri API.  

### Pengaturan

**Untuk menyiapkan OneLink API:**

1. <Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template#prosedur">Buat templat OneLink</Anchor>.
2. Catat ID OneLink.   

   [![](https://files.readme.io/b25f9c4dfe6f4a5a39e9b0a4d1b82d68330f8c0853248284564ac46c72d4d423-360019487418.jpg)](https://files.readme.io/b25f9c4dfe6f4a5a39e9b0a4d1b82d68330f8c0853248284564ac46c72d4d423-360019487418.jpg)
3. Catat kunci OneLink API. Pengguna admin perlu mengambil kunci API; pengguna akun tidak memiliki akses. 
   * Di dashboard AppsFlyer, buka **Pengalaman & Deep Linking** > **OneLink API** > **Lihat kunci OneLink API**
   * Jika kunci API OneLink tidak ada untuk pengguna admin, itu berarti Anda tidak memiliki paket yang diperlukan, dan Anda perlu menghubungi CSM Anda.
4. Berikan OneLink ID dan kode OneLink API kepada pengembang.
5. Beri tahu pengembang untuk mengikuti <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/onelink_rest_api">petunjuk di pusat pengembang</Anchor>.

### Dashboard

Dashboard OneLink API menampilkan:

* Penggunaan API harian, bulanan, dan tiga bulan Anda.
* Kunci OneLink API.

**Untuk melihat dashboard OneLink API**: 

Di AppsFlyer, buka **Pengalaman & Deep Linking** > **OneLink API**.

<div id="traits-and-limitations" />

### Karakteristik dan batasan

| **Sifat** | **Catatan** |
| --- | --- |
| Batas kuota API | <ul><li>Batas penggunaan OneLink API untuk membuat, mengedit, atau menghapus tautan OneLink adalah 7,5 juta per bulan (zona waktu UTC), per akun.</li><li>Semua permintaan yang dibuat **setelah** melebihi kuota ini tidak dilayani, dan tautan tidak dibuat; panggilan API menerima kode status kesalahan 429 dengan pesan tersebut "Kuota bulanan terlampaui".</li><li>Informasi mengenai berapa kuota tarif yang terpakai/tetap ditampilkan di dashboard OneLink API.</li></ul> |
| Batas angka | <ul><li>Batas angka per akun adalah 500 permintaan per detik (30000 per menit).</li><li>Semua permintaan yang dibuat melebihi 500 permintaan per detik(30000 per menit) tidak dilayani, dan tautan tidak dibuat; panggilan API menerima kode status kesalahan 429 dengan pesan "Batas tarif terlampaui".</li></ul> |
| Visibilitas tautan | <ul><li>Tautan yang dibuat melalui API tidak muncul di daftar tautan khusus OneLink di dashboard AppsFlyer.</li><li>Praktik terbaik: Simpan tautan yang dibuat API ke tabel lokal, sehingga Anda dapat mengakses tautan untuk tujuan apa pun di masa mendatang.</li></ul> |
| TTL | <ul><li>Waktu hidup default (TTL) untuk URL singkat OneLink yang dibuat melalui OneLink API adalah 31 hari. Ini diperpanjang 31 hari setiap kali tautan diklik.  Mengeklik tautan setelah TTL kedaluwarsa masih merupakan perilaku default yang ditentukan dalam konfigurasi dasar OneLink, tetapi atribusi tidak akan berfungsi.<ul><li>Diperlukan waktu hingga 48 jam untuk menghapus URL pendek OneLink setelah TTL kedaluwarsa.</li></ul></li><li>TTL maksimum adalah 31 hari. Nilai TTL apa pun yang lebih besar dari 31 diganti dengan TTL default 31.</li><li>Anda dapat mengubah TTL default dengan menambahkan parameter `ttl={value}` dan menentukan berapa hari, jam, atau menit. Misalnya `ttl=7d`, `ttl=12h`, atau `ttl=10m`.</li><li>Anda dapat mengirim<Anchor target="_blank" href="https://dev.appsflyer.com/reference/onelink_rest_api#update-onelink-attribution-link">permintaan pembaruan</Anchor>untuk menentukan TTL. Setiap permintaan pembaruan mengatur ulang TTL (untuk tautan yang ada) ke yang ditentukan dalam konten permintaan.<ul><li>Ini berarti TTL diganti. Misalnya, jika Anda melakukan panggilan pembaruan dengan TTL 2d untuk tautan yang saat ini memiliki TTL 29d, itu akan berubah menjadi **TTL=2d** (bukan 31d).</li><li>Panggilan pembaruan berpotensi memperpanjang masa pakai tautan atribusi. Misalnya, jika Anda melakukan panggilan pembaruan dengan TTL 31d untuk tautan yang saat ini memiliki TTL 20d tetapi 5 hari telah berlalu, TTL akan menjadi 31d sejak waktu pembaruan.</li></ul></li><li>Jika Anda tidak ingin tautan TTL diperpanjang secara otomatis, tambahkan parameter `renew_ttl=false` ke tautan Anda. Nilai untuk parameter ini adalah boolean, baik true (default) atau false.</li><li>Parameter `renew_ttl` tidak tampil pada URL aktual.</li></ul> |
| Karakter khusus | Karakter berikut harus dikodekan jika digunakan untuk tautan yang dibuat API: ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ', >, &lt;, /  <br />Jika Anda tidak menyandikan karakter ini, mereka diganti dengan ruang kosong, dan tautan serta fungsinya berpotensi rusak |
| Payload | String kueri dari payload tidak boleh melebihi 2.048 karakter. |
| ID URL | ID URL (atau ID tautan pendek) dapat diedit untuk menyoroti penawaran kampanye Anda. Contohnya: https://myapp.onelink.me/abc123/apples. ID URL tidak boleh melebihi 50 karakter dan dapat berupa kombinasi huruf dan angka. Secara default, ini adalah 8 karakter.<br /><br />**Catatan**:<ul><li>Anda hanya dapat mengedit ID URL jika ID saat ini belum digunakan.</li><li>Jika ID URL sudah digunakan, pembuatan tautan gagal dan mengembalikan respons kesalahan (400). Anda dan pengembang Anda perlu memutuskan dan mengonfigurasi apa yang terjadi dalam event semacam itu.</li><li>Panggilan yang gagal tetap diperhitungkan dalam kuota API bulanan Anda.</li></ul> |

<div data-zendesk-anchors="setup=pengaturan traits-and-limitations=karakteristik-dan-batasan" />
