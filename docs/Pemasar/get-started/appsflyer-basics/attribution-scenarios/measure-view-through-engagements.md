---
title: Panduan atribusi lihat-tayang (view-through)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-20T07:38:24Z'
  edited_at: '2023-11-08T15:16:02Z'
  id: 210084473
  locale: id
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/id/articles/210084473
---
> **Sekilas:** Pengguna yang melihat (tayangan) iklan kemudian menginstal aplikasi, diatribusikan melalui atribusi lihat-tayang.

<div id="overview" />

## Ringkasan

Atribusi lihat-tayang mengukur penginstalan, atribusi ulang, dan interaksi ulang pengguna yang melihat iklan namun tidak mengekliknya.

<div id="view-through-attribution-flow" />

### Alur atribusi lihat-tayang

![Retargeting_-_View-through__1_.png](https://files.readme.io/86d32778a8a0966499a0c5c91c1b2d8aed6d5bb24214b1a32fd484779c105a98-4412917609489.png)

<div id="terminology" />

### Terminologi

* **Tayangan:** Tampilan iklan kepada pengguna terlepas dari klik atau interaksi pengguna lainnya.
* **Penginstalan**: Dalam artikel ini berarti penginstalan, atribusi ulang, dan interaksi ulang.
* **Atribusi lihat-tayang:** Mengatribusikan penginstalan ke sumber media setelah pengguna melihat tayangan.

<div id="view-through-attribution-principles" />

### Prinsip atribusi lihat-tayang

* <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#device-id-matching">Pencocokan ID perangkat</Anchor> dan <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#probabilistic-modeling">pemodelan probabilistik</Anchor> (<Anchor target="_blank" href="/marketers/id/docs/app-settings#viewthrough-attribution-via-probabilistic-modeling">yang harus Anda aktifkan</Anchor>) didukung.
* Didukung oleh mitra yang tercantum dalam [daftar mitra atribusi lihat-tayang](/docs/measure-view-through-engagements#view-vta-partner-list).

Tayangan merupakan kandidat untuk atribusi lihat-tayang menggunakan prinsip berikut:

* Tayangan terjadi dalam periode waktu lookback lihat-tayang (default 24 jam).
* Jika beberapa tayangan ditemukan, tayangan terbaru akan dipertimbangkan.
* Klik diprioritaskan dibandingkan tayangan. Artinya, jika ada klik di periode waktu lookback klik-tayang, klik terbaru yang menang. Tayangan terbaru diatribusikan sebagai kontributor (bantuan).

<div id="view-through-lookback-window" />

### Periode waktu lookback lihat-tayang

* Untuk non-SRN, durasi periode waktu lookback atribusi lihat-tayang adalah 1-24 jam. Untuk SRN, periode waktu lookback bisa lebih lama.
* Untuk mengatur jendela:
  * **Non-SRN:** Tetapkan durasi menggunakan tautan atribusi tayangan dengan menetapkan parameter  `af_viewthrough_lookback` . Jika parameter tidak diatur, periode waktu 24 jam default akan digunakan.
  * **SRNs**: Periode waktu ditentukan oleh SRN. Kami merekomendasikan pengaturan nilai yang sama dengan SRN di AppsFlyer.

<div id="view-through-attribution-reporting-and-metrics" />

### Pelaporan dan metrik atribusi lihat-tayang

* **Data agregat:** Jaringan iklan melaporkan data tayangan agregat ke AppsFlyer melalui API, atau berdasarkan per tayangan. Pertimbangkan bahwa penghitungan dan pelaporan tayangan ditentukan oleh masing-masing mitra secara individual. Lihat definisi tayangan dan klik menurut mitra terintegrasi utama. Metrik terkait tersedia di dashboard Ikhtisar dan melalui alat pelaporan lainnya. Metrik yang tersedia adalah: 
  * Tayangan: Jumlah tayangan yang ditampilkan selama periode tertentu.
  * Lihat-tayang: Jumlah penginstalan yang diatribusikan menggunakan atribusi lihat-tayang.
* **Data lengkap**:
  * Data tingkat pengguna (data lengkap) dari pengguna yang diatribusikan melalui atribusi lihat-tayang tersedia dan serupa dengan data pengguna yang diatribusikan melalui klik. Namun, beberapa mitra membatasi ketersediaan data ini.
  * Data tayangan (mirip dengan data klik) tersedia.
  * Bidang atributted\_touch\_type berisi *tayangan* nilai.

<div id="view-through-operations" />

## Operasi lihat-tayang

<div id="set-impression-links" />

<Accordion title="Tetapkan tautan tayangan">

Jaringan iklan mengirimkan tautan tayangan ke AppsFlyer yang diisi dengan kampanye dan detail lainnya serupa dengan yang disertakan dalam <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters">tautan atribusi</Anchor> klik-tayang.

Tautan dikirim dalam waktu aktual sehingga jika penginstalan mengikuti tayangan, maka akan diatribusikan dengan benar.

Pertimbangkan hal berikut dalam menyiapkan tautan:

* URL yang ditampilkan adalah `http://impression.appsflyer.com`. Protokol HTTP dan HTTPS didukung.
* Gunakan permintaan GET.
* Sertakan ID perangkat jika tersedia: IDFA, GAID, IDFV, dan sebagainya.
* Sertakan parameter <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#parameter-pemodelan-probabilistik-untuk-jaringan-iklan">pemodelan probabilistik</Anchor> .
* Nilai ID perangkat dapat di-hash untuk keamanan yang lebih baik menggunakan SHA1. Nama parameter harus dimulai dengan "sha1\_" dan diikuti dengan nama parameter dan nilai hash, misalnya sha1\_idfa, sha1\_advertising\_id, sha1\_android\_id, dan sha1\_imei.

> 📄
>
>  Contoh
>
> ```http
> http://impression.appsflyer.com/{app-id}?c={campaign name}&pid={media source}
> &af_viewthrough_lookback=1d&af_prt={agency_name}&af_siteid={site id value}
> &af_sub1={free value}&idfa={idfa value}
> ```

</Accordion>

<div id="set-custom-impression-links" />

<Accordion title="Tetapkan tautan tayangan khusus">

Pemasang iklan memanfaatkan tautan tayangan atribusi dengan sumber media khusus mereka sendiri, misalnya spanduk situs web.

Saat pemasang iklan <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#buat-tautan-onelink">membuat tautan atribusi khusus</Anchor>, mereka mendapatkan tautan tayangan penuh, yang dapat diaktifkan setiap kali pengguna berinteraksi dengan iklan miliknya.

Tautan tayangan khusus (dibuat melalui OneLink) juga dapat digunakan untuk melakukan atribusi lihat-tayang untuk pengunjung situs web seluler. Pelajari lebih lanjut cara <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">membuat URL tayangan khusus</Anchor>.

</Accordion>

<div id="turn-off-viewthroughattribution" />

<Accordion title="Nonaktifkan atribusi lihat-tayang">

Secara default, atribusi lihat-tayang diaktifkan. Jika AppsFlyer menerima tautan atribusi tayangan yang valid, tayangan tersebut berpartisipasi dalam alur atribusi.

Karena atribusi lihat-tayang diaktifkan secara default, penting bagi pemasang iklan untuk terlebih dahulu menyetujui kontrak dengan jaringan tentang apakah atribusi lihat-tayang mereka harus diaktifkan atau tidak.

Atribusi lihat-tayang dapat dinonaktifkan per sumber media. Namun, jika tayangan diterima, dan atribusi lihat-tayang dinonaktifkan:

* Metrik tayangan tersedia di dashboard.
* Proses atribusi mengabaikan tayangan ini.

**Untuk menonaktifkan atribusi lihat-tayang:**

1. Di AppsFlyer, buka **Konfigurasi** > **Integrasi Aktif**.
2. Pilih mitra terintegrasi.
3. Di tab Integrasi, nonaktifkan **Instal atribusi lihat-tayang**.
4. Klik **Save Integration (Simpan Integrasi)**.

Sehubungan dengan SRN: Menonaktifkan atribusi lihat-tayang di AppsFlyer tidak memberikan dampak yang sama pada sisi jaringan. Pastikan Anda menyelaraskan pengaturan lihat-tayang baik di AppsFlyer maupun di jaringan untuk menghindari perbedaan.

</Accordion>

<div id="view-vta-partner-list" />

<Accordion title="Lihat daftar mitra VTA">

Daftar mitra jaringan iklan yang mendukung atribusi lihat-tayang tersedia melalui dashboard. 

**Untuk melihat daftarnya**:

1. Di AppsFlyer, buka **Konfigurasi**> **Integrasi Aktif**.
2. Pilih **Semua integrasi**.
3. Di filter **Kemampuan mitra** , pilih **Lihat-tayang**.   
   Daftar mitra ditampilkan.

</Accordion>

<div data-zendesk-anchors="overview=ringkasan h_01HEMT7T1TB9W7ZBRPQW29SRPF=ringkasan viewthrough-attribution-flow=alur-atribusi-lihat-tayang h_01HEMT7T1T6ZK4ZH7DKV3162J1=alur-atribusi-lihat-tayang terminology=terminologi h_01HEMT7T1TY46QXBDS6MBF1DZ5=terminologi viewthrough-attribution-principles=prinsip-atribusi-lihat-tayang h_01HEMT7T1THD8TVKRRJ168HKY2=prinsip-atribusi-lihat-tayang viewthrough-lookback-window=periode-waktu-lookback-lihat-tayang h_01HEMT7T1TWHN2AB3Q5X36TKKB=periode-waktu-lookback-lihat-tayang viewthrough-attribution-reporting-and-metrics=pelaporan-dan-metrik-atribusi-lihat-tayang h_01HEMT7T1TQNKM5GABA7VY6KR1=pelaporan-dan-metrik-atribusi-lihat-tayang viewthrough-operations=operasi-lihat-tayang h_01HEMT7T1T13JC75ZYY01N8PS6=operasi-lihat-tayang h_01HEMT7T1TQ3YNQ2Y0CCGPXWDX=set-impression-links h_01HEMT7T1T75MBS64JE837CJ0E=set-custom-impression-links h_01HEMT7T1T253G1CZNS9KVDFCP=turn-off-viewthroughattribution h_01HEMT7T1T5MQHC3F5EHSGMYQF=view-vta-partner-list" />
