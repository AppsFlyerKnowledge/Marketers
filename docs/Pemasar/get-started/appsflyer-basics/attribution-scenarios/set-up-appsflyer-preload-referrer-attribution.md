---
title: Atribusi perujuk pramuat AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2022-03-02T09:54:10Z'
  edited_at: '2023-11-08T15:16:06Z'
  id: 4543811207313
  locale: id
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/id/articles/4543811207313
---
> **Sekilas:** AppsFlyer menggunakan perujuk pramuat untuk mengaitkan penginstalan ke kampanye pramuat, di mana pemasar membuat kontrak dengan Original Equipment Manufacturers (Produsen Peralatan Asli/OEM), operator seluler, dan mitra penemuan aplikasi untuk memuat aplikasi mereka di pabrik atau pada saat perangkat pertama kali dihidupkan oleh pengguna.

<div id="overview" />

## Atribusi perujuk pramuat AppsFlyer

Dalam kampanye pramuat, Produsen Perangkat Asli (OEM), operator seluler, dan mitra penemuan aplikasi melakukan pramuat aplikasi di perangkat sebelum menjangkau pengguna. Ini dapat dilakukan oleh OEM di pabrik atau oleh penyedia setelah aktivasi perangkat pertama kali.

Kampanye pramuat memungkinkan pemasang iklan untuk menjangkau audiens yang berpotensi besar tanpa menjalankan kampanye online.

Atribusi perujuk pramuat (1 dari 3 <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#preload-campaigns">metode atribusi pramuat</Anchor>) memberi pemasar mekanisme yang akurat dan menjaga privasi untuk mengukur kinerja kampanye pramuat. Metode ini memberikan hasil atribusi deterministik kepada pemasar dan secara bersamaan memastikan bahwa privasi pengguna dipertahankan karena atribusi dilakukan melalui pencocokan perujuk dengan perujuk yang dihasilkan secara independen dari perangkat dan pengenal pengguna.

Solusinya menyediakan:

* Dukungan transparan untuk pembaruan aplikasi dan pengunduhan ulang aplikasi.
* Kemampuan visibilitas dan pengukuran antara aktivasi perangkat pertama dan peluncuran aplikasi pertama. Ini memungkinkan Anda melihat berapa banyak perangkat yang diaktifkan dengan aplikasi yang dimuat sebelumnya di perangkat oleh mitra tertentu, lalu melihat kapan aplikasi diluncurkan untuk pertama kali.

<div id="preload-referrer-options" />

### Opsi perujuk pramuat

Perujuk dapat digunakan untuk mengaitkan penginstalan dengan pramuat atau dengan klik untuk mengunduh. Lihat tabel berikut untuk lebih jelasnya.

AppsFlyer memberikan prioritas tertinggi untuk pramuat atribusi. Artinya, jika pengguna berinteraksi dengan kampanye lain sebelum membuka aplikasi untuk pertama kali, kampanye pramuat masih diberikan atribusi. Interaksi lainnya dianggap sebagai penginstalan yang dibantu. **Catatan**: Anda dapat mengaktifkan prioritas yang sama untuk keterlibatan pramuat. Hal ini memberikan klik deterministik prioritas atribusi yang sama dengan interaksi pramuat untuk seluruh periode lihat balik pramuat, sehingga atribusi ke kampanye pramuat dapat digantikan oleh interaksi iklan lainnya.

| Opsi perujuk | Deskripsi | UA menginstal jenis pencocokan data lengkap |
| --- | --- | --- |
| Pramuat | <ul><li>Aplikasi dimuat sebelumnya di pabrik atau dimuat saat pertama kali perangkat diaktifkan. Alternatifnya, wizard meminta pengguna untuk mengunduh aplikasi saat perangkat pertama kali diaktifkan.</li><li>Event pramuat, setara dengan klik, dilaporkan ke AppsFlyer saat perangkat dihidupkan untuk pertama kali.</li><li>Atribusi terjadi saat pengguna membuka aplikasi untuk pertama kalinya.</li><li>Event pramuat memiliki prioritas atribusi tertinggi (kecuali prioritas atribusi yang setara diaktifkan).</li></ul> | `preload_rfr` |
| Klik untuk mengunduh | <ul><li>Penginstalan aplikasi dilakukan nanti dalam siklus hidup perangkat, melalui notifikasi push, toko alternatif mitra, dll.</li><li>Saat pengguna terlibat dengan iklan atau pesan push, aplikasi diunduh dan dipasang secara otomatis di perangkat tanpa dialihkan ke app store.</li><li>Atribusi diberikan menggunakan aturan kemenangan klik terakhir AppsFlyer.</li></ul> | `af_referrer` |

<div id="view-preload-attribution-data" />

### Ketersediaan data

Pramuat/klik untuk mengunduh data kinerja kampanye keterlibatan tersedia sebagai berikut:

* **Dashboard ikhtisar:** Interaksi dihitung sebagai klik dalam laporan gabungan dan dashboard. Mereka digabungkan pada tingkat mitra pramuat (sumber media) dan kampanye.
* **Data lengkap:** Interaksi tersedia di laporan klik yang hanya tersedia melalui Data Locker. Mereka ditemukan di bidang URL asli dan dapat diidentifikasi di parameter af\_engagement\_type sebagai pramuat atau click\_to\_download. Untuk penginstalan, lihat tabel di bagian sebelumnya untuk melihat bagaimana jenis pencocokan ditampilkan dalam data lengkap.

<div id="traits-and-limitations" />

<div id="set-up-samsung-preload-referrer-attribution" />

<div id="samsung-preload-referrer" />

<div id="set-up-preload-referrer-attribution" />

### Siapkan atribusi perujuk pramuat

**Prasyarat:**

* Integrasikan AppsFlyer <Anchor target="_blank" href="/marketers/id/docs/appsflyer-android-sdk-release-notes">Android SDK 6.10.1+</Anchor>.
* Kontrak dengan mitra pramuat AppsFlyer.

**Untuk menyiapkan atribusi perujuk pramuat**:

1. Di AppsFlyer, buka **Konfigurasi** > **Integrasi Aktif**.
2. Pilih mitra pramuat.
3. Di tab **Integrasi** , aktifkan **Atribusi pramuat**.  

   [<Image alt="" src="https://files.readme.io/d2c08125ca318b4bde60b51668692f21b88e292ca1b3f4fef54b77df779815cb-15585078780433.png" width="538px" />](https://files.readme.io/d2c08125ca318b4bde60b51668692f21b88e292ca1b3f4fef54b77df779815cb-15585078780433.png)
4. Setel durasi **Jendela lookback pramuat** . Rentang: 1-180 hari.
5. [Opsional] Aktifkan **Prioritas atribusi setara pramuat**.  
   Hal ini memberikan klik deterministik prioritas atribusi yang sama seperti atribusi pramuat, artinya jika klik deterministik didaftarkan antara interaksi perujuk pramuat dan penginstalan, klik tersebut mendapat atribusi berdasarkan logika atribusi sentuhan terakhir standar, dan bukan digantikan oleh perujuk pramuat .
6. Klik **Simpan Integrasi**.
7. Beri tahu mitra pramuat bahwa Anda siap mengatribusikan kampanye mereka.

<div id="partners-supporting-preload-referrer-campaigns" />

### Mitra mendukung kampanye perujuk pramuat

<table><thead><tr><th rowspan="2">Partner</th><th rowspan="2">PID</th><th colspan="2">Opsi kampanye perujuk pramuat <span><a href="./set-up-appsflyer-preload-referrer-attribution#opsi-perujuk-pramuat">Pelajari lebih lanjut</a></span> </th></tr><tr><th>Pramuat</th><th>Klik untuk mengunduh</th></tr></thead><tbody><tr><td>Turbin Digital Pada Perangkat</td><td>digitalturbine_int</td><td><span><span>✓</span></span></td><td><p>Segera tersedia</p></td></tr><tr><td>Aura dari Unity</td><td>aura_int</td><td><span><span>✓</span></span></td><td><p>Segera tersedia</p></td></tr><tr><td><span>Appnext</span></td><td><span>appnext_int</span></td><td><span><span>✓</span></span></td><td><p>Segera tersedia</p></td></tr><tr><td> <span>Sekilas</span><span><br/></span> </td><td><span>glance_int</span></td><td><span><span>✓</span></span></td><td><p><span><span>✓</span></span></p></td></tr></tbody></table>

<div data-zendesk-anchors="appsflyer-preload-referrer-attribution=atribusi-perujuk-pramuat-appsflyer h_01HEKAF7K41PH189PSCKBRF070=atribusi-perujuk-pramuat-appsflyer preload-referrer-options=opsi-perujuk-pramuat h_01HEKAF7K4H3HNAMEYM6C58Y29=opsi-perujuk-pramuat campaign-performance-data-availability=ketersediaan-data h_01HEKAF7K4GJDDPHCFTTC75YBS=ketersediaan-data run-preload-referrer-campaigns=siapkan-atribusi-perujuk-pramuat h_01HEKAF7K41RBRVXC6GF6PCN3Y=siapkan-atribusi-perujuk-pramuat partners-supporting-preload-referrer-campaigns=mitra-mendukung-kampanye-perujuk-pramuat h_01HEKAF7K5CWX2P9TY8M0MTQAM=mitra-mendukung-kampanye-perujuk-pramuat" />
