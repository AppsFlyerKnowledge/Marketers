---
title: Pembatasan konten data lengkap—sumber media atau pengidentifikasi pengguna
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
  created_at: '2020-03-23T08:29:01Z'
  edited_at: '2023-11-26T15:25:32Z'
  id: 360006868017
  locale: id
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/id/articles/360006868017
---
> **Sekilas:** Bidang di beberapa laporan data lengkap dibatasi karena batasan privasi. Dalam kasus lain, mitra memerlukan penyuntingan sumber media saat membagikan postback ke platform pihak ketiga. Artikel ini menjelaskan batasan dan implikasinya.

<div id="raw-data-restriction" />

## Pembatasan data lengkap

AppsFlyer membatasi ketersediaan beberapa bidang dalam laporan data lengkap untuk menjaga privasi pengguna.Hal ini sesuai dengan pengaturan<Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework">AAP</Anchor> pemasang iklanatau sesuai dengan kebijakan berbagi data dari jaringan iklan yang menyediakan data tersebut. Pembatasannya berbeda-beda, bergantung pada jenis laporan dan alasan pembatasan. Pembatasan ini memengaruhi data lengkap yang disediakan menggunakan <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">alat pengiriman data lengkap</Anchor>.

<div id="media-source-restrictions" />

### Pembatasan sumber media

Tabel berikut mencantumkan batasan per sumber media.

<div id="note" />

> 📘 **Catatan**
>
> * Data gabungan dan analitik dari platform AppsFlyer tersedia tanpa batasan
> * <Anchor target="_blank" href="/marketers/id/docs/discrepancies-between-appsflyer-and-third-party-platforms">Pembatasan postback pada platform pihak ketiga:</Anchor>
>   * Postback untuk event yang dibatasi oleh sumber media, seperti yang dideskripsikan dalam tabel di bawah, **tidak dikirim ke platform pihak ketiga** (seperti platform analitik dan pemasaran).
>   * Pembatasan postback lebih lanjut mungkin berlaku untuk event lainnya

| Media Source | Pembatasan jenis atribusi |
| --- | --- |
| <span id="meta-ads"></span>Iklan Meta | <ul><li>Hingga 28 Oktober 2021: Lihat-tayang</li><li>Mulai 29 Oktober 2021: Klik-tayang dan lihat-tayang. Namun, jika Anda mengaktifkan mekanisme Perujuk Pemasangan Google Play, beberapa data klik-tayang tersedia untuk Anda. Perhatikan bahwa Perujuk Pemasangan Google Play tidak berlaku untuk kampanye penargetan ulang dan tersedia tanpa batasan.</li><li>**Pengecualian:** Semua data dari <Anchor target="_blank" href="/marketers/id/docs/meta-ads-integration-setup#app-aem-for-reengagement">atribusi interaksi ulang tautan dalam</Anchor> tersedia tanpa batasan pelaporan.</li></ul> |
| <span id="pinterest"></span>Pinterest | Mulai 4 September 2023: Atribusi klik-tayang dan lihat-tayang |
| <span id="roku-oneview"></span>Roku OneView | Klik-tayang dan lihat-tayang untuk semua platform (CTV dan seluler) |
| <span id="samsung-dsp"></span>Samsung DSP | Mulai 17 Oktober 2023, atribusi klik-tayang dan lihat-tayang dibatasi. Bidang berikut **diisi** di alat pengiriman data lengkap:<ul><li>Sumber media (samsungdsp\_int)</li><li>Channel</li><li>Attributed touch-type</li><li>Waktu sentuh yang diatribusikan</li><li>Detail kampanye: Nama kampanye, ID kampanye, nama adset, ID adset, nama iklan, dan ID iklan</li></ul> |
| <span id="snapchat"></span>Snapchat | <ul><li>Mulai 1 Maret 2023, Uninstall Snapchat tidak disertakan dalam laporan data lengkap</li><li>Mulai 13 September 2023, atribusi lihat-tayang dibatasi. Bidang berikut **diisi** di alat pengiriman data lengkap:<ul><li>Sumber media (snapchat\_int)</li><li>Channel</li><li>Jenis sentuhan yang diatribusikan (tayangan)</li><li>Waktu sentuh yang dikaitkan (dilaporkan sebagai tanggal saja - "hh/bb/tttt")</li><li>Kampanye dilaporkan sebagai *"dibatasi"*</li></ul></li></ul> |
| <span id="tiktok-for-business"></span>TikTok untuk Bisnis | <ul><li>Antara 28 Juli 2021 hingga 23 Oktober 2021, data atribusi lihat-tayang dibatasi.</li><li>Mulai 23 Oktober 2021, atribusi lihat-tayang dibatasi. Bidang berikut **diisi** di alat pengiriman data lengkap:<ul><li>Sumber media (bytedanceglobal\_int dan tiktokglobal\_int)</li><li>Channel</li><li>Jenis sentuhan yang diatribusikan (tayangan)</li><li>Waktu sentuh yang dikaitkan (dilaporkan sebagai tanggal saja - "hh/bb/tttt")</li><li>Kampanye dilaporkan sebagai *"dibatasi"*</li></ul></li></ul> |
| <span id="twitter"></span>Twitter | Dalam beberapa kasus, Twitter tidak mengizinkan data lengkap tersedia di platform AppsFlyer. Dalam kasus ini, event tidak muncul di laporan data lengkap. |

<div id="raw-data-context" />

### Konteks data lengkap

Pembatasan tingkat bidang data lengkap bergantung pada konteks data, seperti yang tercantum dalam tabel berikut.

| Jenis pembatasan | Laporan yang terdampak |
| --- | --- |
| [Sumber media terbatas](/docs/about-raw-data-identifier-restrictions#pembatasan-sumber-media): Tempat asal pengguna | <ul><li>Atribusi: Penginstalan, konversi penargetan ulang, penginstalan</li><li>In-app event, sesi</li><li>Laporan Protect360</li></ul> |
| Sepenuhnya dibatasi | <ul><li>Klik</li><li>Tayangan</li><li>Klik yang diblokir (Protect360)</li></ul> |

**Pengiriman data lengkap**

Data atribusi tingkat pengguna di AppsFlyer tersedia menggunakan alat pengiriman data mentah berikut:

* Data Locker
* API Pull data lengkap
* Push API
* Halaman ekspor dashboard
* Postback ke jaringan
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">Dapatkan API data konversi (GCD)</Anchor> dalam konteks API data tingkat pengguna sisi klien

<div id="unavailable-attribution-fields" />

<Accordion title="Kolom atribusi tidak tersedia">

Kolom berikut tidak tersedia saat sumber media dibatasi:

| Nama tampilan | Nama API |
| --- | --- |
| ad | af\_ad |
| ID iklan | af\_ad\_id |
| Jenis iklan | af\_ad\_type |
| adset | af\_adset |
| ID adset | af\_adset\_id |
| Atribusi jendela lookback | af\_attribution\_lookback |
| ID kampanye | af\_c\_id |
| Channel | af\_channel |
| Mata Uang Biaya | af\_cost\_currency |
| Model Biaya | af\_cost\_model |
| Nilai Biaya | af\_cost\_value |
| Keywords | af\_keywords |
| Partner | af\_prt |
| ID situs | af\_siteid |
| ID Sub Situs | af\_sub\_siteid |
| Sub Param [n] (n=1-5) | af\_sub[n] (n=1-5) |
| Waktu sentuh yang diatribusikan | attributed\_touch\_time |
| Attributed touch-type | attributed\_touch\_type |
| Kampanye | campaign |
| Kontributor [n] sumber media (n=1-3) | contributor[n]\_media\_source (n=1-3) |
| Kontributor [n] mitra (n=1-3) | contributor[n]\_af\_prt  <br />(n=1-3) |
| Kontributor [n] kampanye (n=1-3) | kontributor[n]\_kampanye  <br />(n=1-3) |
| Kontributor [n] jenis pencocokan (n=1-3) | contributor[n]\_match\_type (n=1-3) |
| Kontributor [n] jenis sentuh (n=1-3) | contributor[n]\_touch\_time  <br />(n=1-3) |
| Kontributor [n] jenis sentuh (n=1-3) | contributor[n]\_touch\_type  <br />(n=1-3) |
| URL Deep Link | deeplink\_url |
| Perujuk HTTP | http\_referrer |
| Instal App Store | install\_app\_store |
| ID kata kunci | keyword\_id |
| Jenis pencocokan kata kunci | keyword\_match\_type |
| Jenis pencocokan | match\_type |
| ID Akun Jaringan | network\_account\_id |
| Original URL | original\_url |
| Periode Waktu Re-engagement | af\_reengagement\_window |
| Halaman produk toko | store\_product\_page |

</Accordion>

<div id="identifier-restriction" />

<Accordion title="Pembatasan pengidentifikasi">

Saat pembatasan pengidentifikasi berlaku, bidang yang tercantum dalam tabel berikut adalah satu-satunya bidang yang tersedia dalam laporan data lengkap.

| Nama API |
| --- |
| <span id="event_time"></span>event\_time |
| <span id="event_name"></span>event\_name |
| <span id="event_revenue"></span>event\_revenue |
| <span id="event_revenue_currency"></span>event\_revenue\_currency |
| <span id="event_revenue_usd"></span>event\_revenue\_usd |
| <span id="af_cost_model"></span>af\_cost\_model |
| <span id="af_cost_value"></span>af\_cost\_value |
| <span id="af_cost_currency"></span>af\_cost\_currency |
| <span id="event_source"></span>event\_source |
| <span id="media_source"></span>media\_source |
| <span id="af_channel"></span>af\_channel |
| <span id="campaign"></span>campaign |
| <span id="af_c_id"></span>af\_c\_id |
| <span id="af_adset"></span>af\_adset |
| <span id="af_adset_id"></span>af\_adset\_id |
| <span id="af_ad"></span>af\_ad |
| <span id="af_ad_id"></span>af\_ad\_id |
| <span id="af_ad_type"></span>af\_ad\_type |
| <span id="af_siteid"></span>af\_siteid |
| <span id="af_sub_siteid"></span>af\_sub\_siteid |
| <span id="app_id"></span>app\_id |
| <span id="app_name"></span>app\_name |
| <span id="bundle_id"></span>bundle\_id |
| <span id="is_retargeting"></span>is\_retargeting |
| <span id="retargeting_conversion_type"></span>retargeting\_conversion\_type |
| <span id="is_primary_attribution"></span>is\_primary\_attribution |
| <span id="af_attribution_lookback"></span>af\_attribution\_lookback |
| <span id="af_reengagement_window"></span>af\_reengagement\_window |
| <span id="country_code"></span>country\_code |
| <span id="blocked_reason"></span>blocked\_reason |
| <span id="blocked_reason_value"></span>blocked\_reason\_value |
| <span id="blocked_reason_rule"></span>blocked\_reason\_rule |
| <span id="blocked_sub_reason"></span>blocked\_sub\_reason |
| <span id="platform"></span>platform |
| <span id="is_paid_media"></span>is\_paid\_media |

</Accordion>

<div id="faq" />

## Pertanyaan Umum

<div id="what-events-are-restricted" />

<Accordion title="Event apa saja yang dibatasi?">

Event yang dibatasi, sebagaimana dirinci dalam [tabel di atas](/docs/about-raw-data-identifier-restrictions#pembatasan-sumber-media), mungkin mencakup konversi (instalasi dan interaksi ulang) dan in-app event terkait yang diatribusikan dengan jaringan iklan yang membatasi.

</Accordion>

<div id="how-does-the-restricted-media-source-impact-raw-data-reports" />

<Accordion title="Bagaimana sumber media yang dibatasi memengaruhi laporan data lengkap?">

* Bidang *sumber media* diisi dengan *dibatasi*.
* Kolom atribusi yang tercantum dalam artikel ini kosong atau diisi dengan *null*.

**Contoh laporan:** Penginstalan <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vScXJznEex0WwdCy78Bm8LtrhbCk1jNy14O_t7etrq5ab5v4CIEiInfFD4B1EsZCE-_w-dVRAxl_cu4/pub?output=csv">data lengkap terbatas</Anchor> dalam file CSV. Laporan data lengkap lainnya diisi dengan cara yang sama.

</Accordion>

<div id="how-does-the-restricted-media-source-impact-postbacks-sent-to-partners" />

<div id="what-is-the-impact-on-postbacks-to-partners-when-the-media-source-is-restricted" />

<Accordion title="Bagaimana dampak sumber media yang dibatasi terhadap postback yang dikirim ke mitra?">

Postback yang dikirim ke partner tidak menyertakan kolom atribusi.

</Accordion>

<div id="how-do-restricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="Bagaimana dampak event yang dibatasi terhadap postback ke platform pihak ketiga?">

Postback untuk jaringan iklan yang diatribusikan yang tercantum pada [tabel di atas](/docs/about-raw-data-identifier-restrictions#pembatasan-sumber-media) tidak dikirim ke platform pihak ketiga.

</Accordion>

<div id="do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="Apakah event yang tidak dibatasi berdampak pada postback ke platform pihak ketiga?">

[Dalam beberapa kasus](/docs/about-raw-data-identifier-restrictions#media-source-sharing-limitations-on-thirdparty-platforms), postback untuk event tidak dibatasi yang dikirim ke platform pihak ketiga tidak menyertakan sumber media. Ini berarti atribusi dikreditkan sebagai organik.

</Accordion>

<div id="what-about-the-data-of-assists-that-form-part-of-the-attribution" />

<Accordion title="Bagaimana dengan data bantuan yang menjadi bagian dari atribusi?">

Data terkait bantuan dianggap sebagai data atribusi dan tidak tersedia.

</Accordion>

<div id="see-also" />

> 📄 **Lihat juga**
>
> <Anchor target="_blank" href="/marketers/id/docs/user-level-data-retention">Retensi data tingkat pengguna</Anchor>

<div data-zendesk-anchors="raw-data-restriction=pembatasan-data-lengkap 01H7WQHTV9RM2JF2BV45XF626H=pembatasan-data-lengkap media-source-restrictions=pembatasan-sumber-media 01H7WQHTV9HJEHHH1N8VN6APX6=pembatasan-sumber-media 01H7WQHTV90YFRP3Z9AEP7ACRD=catatan raw-data-context=konteks-data-lengkap 01H7WQHTVA8H9FTBJ1FB6BJQ2A=konteks-data-lengkap 01H7WQHTVA0XP6B2H95EEM7EYD=unavailable-attribution-fields 01H7WQHTVA7ERWW1PC3DF5H0NP=identifier-restriction faq=pertanyaan-umum 01H7WQHTVA5439QPE6GNXNKJ63=pertanyaan-umum h_01HDBND48E05P1WV51ZJGD072N=what-events-are-restricted 01H7WQHTVAHCK7QDZ5P25YRQ2D=how-does-the-restricted-media-source-impact-raw-data-reports 01H7WQHTVABKATP6B6XN4NRC54=what-is-the-impact-on-postbacks-to-partners-when-the-media-source-is-restricted h_01HDBND48EDTAFBFXTADGWJADM=how-do-restricted-events-impact-postbacks-to-thirdparty-platforms h_01HE5TK3WSNBPM6W5D1Y9S6PDX=do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms 01H7WQHTVA60PWZ017WJMRTKVP=what-about-the-data-of-assists-that-form-part-of-the-attribution h_01HE7SCVN3VJ4Y6KF2QZSNBEMZ=lihat-juga" />
