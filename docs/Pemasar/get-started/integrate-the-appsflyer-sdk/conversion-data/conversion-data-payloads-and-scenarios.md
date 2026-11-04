---
title: Payload dan skenario data konversi
metadata:
  keywords:
    - Conversion
    - Retargeting
    - Installs
    - Re-attribution
    - Re-engagement
    - Developers
    - SRN
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-12-31T13:05:33Z'
  edited_at: '2023-10-30T00:58:32Z'
  id: 360000726098
  locale: id
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/id/articles/360000726098
---
> **Sekilas:** Gunakan data konversi untuk mengidentifikasi berbagai skenario konversi, menyesuaikan pengalaman pengguna, dan lainnya.

<div id="overview" />

## Ringkasan

Panduan berikut berisi berbagai skenario konversi pengguna dan payload data konversi terkait:

* [Akuisisi Pengguna (UA)](#data-konversi-ua-dengan-srn)
* [Penargetan ulang](#menargetkan-ulang-data-konversi)

Data konversi tersedia di platform menggunakan salah satu dari berikut ini:

* <Anchor target="_blank" href="/marketers/id/docs/raw-data-export-page">Laporan Data Lengkap</Anchor>
* <Anchor target="_blank" href="/marketers/id/docs/push-api-streaming-raw-data">API Push</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">SDK AppsFlyer</Anchor>

Karena pengorbanan akurasi/latensi, data konversi untuk ID perangkat yang sama mungkin berbeda di seluruh API.

<div id="non-organic-conversion-data-payload-fields" />

### Bidang payload data konversi non-organik

<div id="fields-always-available" />

#### Bidang selalu tersedia

Tabel berikut mencantumkan bidang yang selalu ada untuk konversi **non-organik**, terlepas dari `media_source`konversi.

| Nama kolom payload | Nama kolom data lengkap | Catatan |
| --- | --- | --- |
| `media_source` | Sumber media | Penerbit yang dikaitkan. Setara dengan parameter `pid` di tautan atribusi |
| `install_time` | Install time |  |
| `click_time` | Waktu sentuh yang diatribusikan | Waktu terjadinya klik atau tayangan dalam UTC |
| `is_first_launch` | N/A | `true`, `false` |
| `af_status` | Data lengkap dibagi menjadi laporan terpisah: organik, non-organik | `"Non-organic"` |
| `af_siteid` | ID situs |  |
| `adgroup_id` | ID iklan |  |
| `adset` | adset |  |
| `adset_id` | ID adset |  |
| `agency` | Partner | `null`, atau nama agensi (untuk kampanye yang dijalankan oleh agensi) |
| `campaign` | Kampanye |  |
| `campaign_id` | ID kampanye |  |
| `http_referrer` | HTTP Referrer |  |
| `retargeting_conversion_type` | Jenis Konversi Penargetan Ulang | "tidak ada", atau retargeting\_conversion\_type |
| `af_sub[n] (n=1—5)` | Sub Param [n] (n=1–5) |  |

<div id="fields-available-in-some-cases" />

#### Kolom tersedia dalam beberapa kasus

Kolom dalam tabel berikut tersedia dalam beberapa kasus, bergantung pada cara SRN mengisi event individu.

<table><thead><tr><th>Nama kolom payload</th><th>Nama kolom data lengkap</th><th>Catatan</th></tr></thead><tbody><tr><td><code>af_channel</code></td><td>Channel</td><td><p>SRN mengisi parameter ini:</p><ul><li>AppLovin</li><li>Google Ads</li><li>Iklan Meta</li><li>Snapchat</li><li>TikTok untuk Bisnis</li><li>Twitter</li></ul><p>Contoh: Facebook—Instagram, Google—YouTube </p></td></tr><tr><td><code>orig_cost</code></td><td> </td><td><p>Catatan (1)</p></td></tr><tr><td><code>costs_cents_USD</code></td><td> </td><td><p>Catatan (1)</p></td></tr><tr><td><code>af_cpi</code></td><td> </td><td><p>Catatan (1)</p></td></tr></tbody><tbody><tr><td colspan="4"><p><strong>Catatan</strong></p><p>(1) Kolom biaya diisi dengan nilai yang dibagikan oleh jaringan iklan. Agar jaringan iklan berbagi data biaya dengan AppsFlyer, Anda harus mengaktifkan integrasi biaya di halaman <a href="./roi360-cost-aggregation-overview#ad-networks-supporting-cost-api" target="_blank"><strong>Integrasi aktif</strong></a> . Beberapa SRN mendukung pembagian biaya secara massal. Dalam hal ini, bidang biaya tingkat kejadian kembali sebagai 0. </p></td></tr></tbody></table>

<div id="additional-fields" />

### Kolom Tambahan

* <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#parameter-link-atribusi">Daftar parameter AppsFlyer</Anchor>
* Anda dapat menambahkan parameter  ke tautan atribusi, parameter tersebut tersedia di payload

Lihat <Anchor target="_blank" href="/marketers/id/docs/raw-data-field-dictionary#data-fields-dictionary">kamus kolom data lengkap</Anchor> untuk informasi tambahan.

<div id="limitations" />

### Batasan

<div id="custom-parameter-names" />

<Accordion title="Nama parameter khusus">

Parameter khusus tidak dapat disebut `nama` (huruf kecil "n". `Nama` valid).

Jika sebuah parameter disebut `nama`, maka akan dihapus dari payload.

</Accordion>

---

<div id="ua-conversion-data-with-srns" />

## Data konversi UA dengan SRN

<Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns">Jaringan pelaporan mandiri</Anchor> (SRN) adalah jaringan iklan yang menerapkan mekanisme atribusi mereka sendiri, misalnya Meta ads dan Google.

SRN tidak menggunakan tautan atribusi. Artinya:

* Bidang payload sudah ditentukan sebelumnya
* Anda tidak dapat menambahkan kolom ke payload dengan menambahkan parameter ke tautan atribusi.

SRN melaporkan konversi ke AppsFlyer. Data konversi tersedia di aplikasi. Kolom yang tersedia bervariasi menurut SRN dan dirinci dalam bilah SRN individual yang mengikuti.

<div id="a-note-about-meta-ads" />

#### Catatan tentang Meta ads

Jika Anda menjalankan kampanye di Meta ads dan tidak menandatangani persyaratan layanan Meta, AppsFlyer mengatribusikan penginstalan. Ketersediaan laporan terbatas sebagai berikut:

* **Tersedia:** Dashboard dan laporan agregat dan analitik
* **Tidak tersedia:** Data lengkap

<Tabs>
<Tab title="Meta ads">

<div id="meta-ads-conversion-data" />

### Data konversi Meta ads

| Nama kolom | Catatan | Sumber data |
| --- | --- | --- |
| `match_type` | Selalu `"srn"` | AppsFlyer |
| `media_source` | Selalu `"Meta ads" (iklan Meta)` | AppsFlyer |
| `agency` | null atau nilai parameter `af_prt` di tautan atribusi | Iklan Meta |
| `http_referrer` | Selalu `null` | Iklan Meta |
| `retargeting_conversion_type` |  | AppsFlyer |
| `af_channel` |  | Meta ads (publisher\_platform) |
| `af_status` | Selalu `"Non-organik"` | AppsFlyer |
| `ad_id` | Hanya untuk penggunaan internal Meta ads. | Meta ads (ad\_id) |
| `click_time` |  | AppsFlyer |
| `install_time` |  | AppsFlyer |
| `is_first_launch` | `true`, `false` | Perangkat |
| `adset_id` | Tersedia dalam data lengkap: ID Adset | Meta ads (campaign\_id) |
| `is_fb` | Selalu `benar` | AppsFlyer |
| `campaign` | Tersedia dalam data-lengkap: Nama Kampanye | Meta ads (campaign\_group\_name) |
| `campaign_id` | Tersedia dalam data-lengkap: ID Kampanye | Meta ads (campaign\_group\_id) |
| `is_paid` | Selalu `benar` | Iklan Meta |
| `adgroup` | Tersedia dalam data-lengkap: Iklan | Meta ads (adgroup\_name) |
| `adgroup_id` | Tersedia dalam data-lengkap: ID Iklan | Meta ads (adgroup\_id) |
| `adset` | Tersedia dalam data-lengkap: Adset | Meta ads (campaign\_name) |
| `af_siteid` | Selalu `null` | Iklan Meta |
| `af_sub[1-5]` | Selalu `null` | Pemasang iklan |

**Catatan** Kolom terkait biaya tidak tersedia karena Meta ads tidak membagikan data biaya saat konversi. Jika <Anchor target="_blank" href="/marketers/id/docs/meta-ads-integration-setup#cost-clicks-and-impressions">pembagian-biaya</Anchor> diaktifkan, Meta ads membagikan data biaya dengan AppsFlyer beberapa kali sehari.

</Tab>

<Tab title="Google">

<table><caption><h3><span id="google-ads-conversion-data"></span>Data konversi Google Ads</h3></caption><thead><tr><th>Nama kolom</th><th>Catatan</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>Selalu <code>"srn"</code> </td></tr><tr><td><code>media_source</code></td><td>Selalu <code>"googleadwords_int"</code> </td></tr><tr><td><code>agency</code></td><td> <code>"none"</code> atau nilai dari <code>af_prt</code> </td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr><tr><td><code>af_channel</code></td><td><p>Catatan (1)</p></td></tr><tr><td><code>af_status</code></td><td>Selalu <code>"Non-organik"</code> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> <code>true</code>, <code>false</code> </td></tr><tr><td><code>adgroup_name</code></td><td> </td></tr><tr><td><code>adset_id</code></td><td>Selalu <code>null</code> </td></tr><tr><td><code>campaign</code></td><td>Catatan (3)</td></tr><tr><td><code>campaign_id</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>adset</code></td><td>Catatan (3)</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>ad_event_id</code></td><td> </td></tr><tr><td><code>af_ad</code></td><td>String kosong</td></tr><tr><td><code>af_ad_id</code></td><td>String kosong</td></tr><tr><td><code>af_ad_type</code></td><td><span>Jenis iklan AdWords</span></td></tr><tr><td><code>af_adset</code></td><td><span>Tersedia dalam data-lengkap: Adset</span></td></tr><tr><td><code>af_adset_id</code></td><td>Tersedia dalam data lengkap: ID Adset</td></tr><tr><td><code>af_c_id</code></td><td>Tersedia dalam data-lengkap: ID Kampanye</td></tr><tr><td><code>af_click_lookback</code></td><td></td></tr><tr><td><code>af_cpi</code></td><td>Catatan (2)</td></tr><tr><td><code>af_dp</code></td><td>Hanya relevan dengan <a href="./google-ads-adwords-integration-setup-for-advertisers#menggunakan-penautan-langsung-yang-ditangguhkan-di-kampanye-aplikasi" target="_blank">kampanye Aplikasi Google di Feeds</a>.</td></tr><tr><td><code>af_keywords</code></td><td>Tersedia dalam data-lengkap: Kata Kunci</td></tr><tr><td><code>af_prt</code></td><td> <code>"none"</code> atau nilai dari <code>af_prt</code> </td></tr><tr><td><code>af_reengagement_window</code></td><td>Tersedia dalam data lengkap: Jendela Interaksi Ulang </td></tr><tr><td><code>af_viewthrough_lookback</code></td><td>Tersedia dalam data lengkap: Jendela Lookback untuk Atribusi View-through</td></tr><tr><td><code>click_url</code></td><td>Tersedia dalam data lengkap: Referrer HTTP</td></tr><tr><td><code>click-timestamp</code></td><td>Sumber: AppsFlyer</td></tr><tr><td><code>cost_cents_USD</code></td><td>Catatan (2)</td></tr><tr><td><code>external_account_id</code></td><td>ID akun AdWords</td></tr><tr><td><code>gclid</code></td><td> </td></tr><tr><td><code>lat</code></td><td> </td></tr><tr><td><code>network</code></td><td>Catatan (1)</td></tr><tr><td><code>orig_cost</code></td><td>Catatan (2)</td></tr><tr><td><code>video_id</code></td><td>Selalu <code>null</code> </td></tr><tr><td colspan="2"><p><strong>Catatan<br/></strong>(1) Google menggunakan beberapa jaringan iklan. Gunakan <code>af_channel</code> bersama dengan <code>network</code> untuk mendapatkan sumber penginstalan.<br/>(2) Kolom ini dikembalikan sebagai 0. Jika pemasang iklan mengaktifkan pembagian biaya, Google mengirimkan data biaya AppsFlyer beberapa kali dalam sehari.<br/>(3) Gunakan <code>campaign</code> dan <code>af_adset</code> untuk mempersonalisasi konten pengguna.</p></td></tr></tbody></table>

</Tab>

<Tab title="ASA">

<table><caption><h3><span id="apple-search-ads-conversion-data"></span>Data konversi Apple Search Ads</h3></caption><thead><tr><th>Nama kolom</th><th>Catatan</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>Selalu <code>"srn"</code> </td></tr><tr><td><code>media_source</code></td><td>Selalu <code>"Apple Search Ads"</code> </td></tr><tr><td><code>{"<strike>adset</strike>"}</code></td><td>Catatan (2)</td></tr><tr><td><code>adset_id</code></td><td> </td></tr><tr><td><code>{"<strike>af_adset</strike>"}</code></td><td>Catatan (2)</td></tr><tr><td><code>af_adset_id</code></td><td> </td></tr><tr><td><code>af_c_id</code></td><td> </td></tr><tr><td><code>af_click_lookback</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>Catatan (1)</td></tr><tr><td><code>{"<strike>af_keywords</strike>"}</code></td><td><p>Catatan (2)—Gunakan ID kata kunci</p></td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_status</code></td><td>Selalu <code>"Non-organik"</code> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>agency</code></td><td> <code>null</code> atau nilai dari <code>af_prt</code> </td></tr><tr><td><code>{"<strike>campaign</strike>"}</code></td><td>Catatan (2)</td></tr><tr><td><code>campaign_id</code></td><td> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> <code>true</code>, <code>false</code> </td></tr><tr><td><code>cost_cents_USD</code></td><td>Catatan (1)</td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>orig_cost</code></td><td>Catatan (1)</td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr></tbody><tbody><tr><td colspan="3"><p><strong>Catatan<br/></strong>(1) Apple Search Ads mendukung pembagian biaya secara massal, bukan dalam data konversi.<br/>(2) Tidak digunakan lagi mulai 15 Februari 2021, karena adopsi Apple Search Ads dari AdServices AP.</p></td></tr></tbody></table>

</Tab>

<Tab title="Snap">

| Nama kolom | Catatan |
| --- | --- |
| `match_type` | `"srn"` |
| `media_source` | `"snapchat_int"` |
| `adset` |  |
| `adset_id` |  |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_c_id` |  |
| `af_channel` |  |
| `af_cpi` |  |
| `af_siteid` |  |
| `af_status` | Selalu `"Non-organik"` |
| `af_sub[1-5]` |  |
| `af_viewthrough_lookback` |  |
| `agency` |  |
| `campaign` |  |
| `campaign_id` |  |
| `click_time` |  |
| `cost_cents_USD` |  |
| `http_referrer` |  |
| `install_time` |  |
| `is_first_launch` |  |
| `adgroup` |  |
| `adgroup_id` |  |
| `orig_cost` |  |
| `retargeting_conversion_type` |  |

</Tab>

<Tab title="Twitter">

| Nama kolom | Catatan |
| --- | --- |
| `match_type` | Selalu `"srn"` |
| `media_source` | Selalu `"Twitter"` |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_channel` |  |
| `af_siteid` |  |
| `af_status` | Selalu `"Non-organik"` |
| `af_sub[1-5]` |  |
| `agency` | Selalu `null` |
| `campaign` |  |
| `campaign_id` | `null` atau ID Kampanye |
| `click_time` |  |
| `http_referrer` |  |
| `install_time` |  |
| `is_first_launch` | `true`, `false` |
| `adgroup` |  |
| `adgroup_id` |  |
| `retargeting_conversion_type` | Selalu `"none"` |

**Catatan:** Kolom biaya tidak muncul di payload karena Twitter tidak mendukung berbagi data biaya.

</Tab>

<Tab title="Oath">

<table><caption><h3><span id="oath-ad-platforms-conversion-data"></span>Data konversi Platform Iklan Oath</h3></caption><thead><tr><th>Nama kolom</th><th>Catatan</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>Selalu <code>"srn"</code> </td></tr><tr><td><code>media_source</code></td><td>Selalu <code>"yahoogemini_int"</code> </td></tr><tr><td><code>adset</code></td><td> </td></tr><tr><td><code>adset_id</code></td><td> </td></tr><tr><td><code>af_ad</code></td><td> </td></tr><tr><td><code>af_ad_id</code></td><td> </td></tr><tr><td><code>af_c_id</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>Catatan (1)</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_status</code></td><td>Selalu <code>"Non-organik"</code> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>agency</code></td><td> </td></tr><tr><td><code>campaign</code></td><td> </td></tr><tr><td><code>campaign_id</code></td><td> </td></tr><tr><td><code>campaign_type</code></td><td> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>cost_cents_USD</code></td><td>Catatan (1)</td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>orig_cost</code></td><td>Catatan (1)</td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr><tr><td colspan="2"> <strong>Catatan</strong><br/>(1) Oath mendukung pembagian biaya tetapi mengirimkan data terkait biaya secara massal, bukan dalam data konversi.</td></tr></tbody></table>

</Tab>
</Tabs>

<div id="ua-conversion-with-other-ad-networks" />

## Konversi UA dengan jaringan iklan lain

Untuk jaringan iklan lainnya, data di payload dipengaruhi langsung oleh <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters">parameter di tautan atribusi</Anchor>.

Periksa payload JSON berikut ini.

**Catatan!** Data konversi kembali sebagai struktur data seperti peta. Pengembang **tidak** berinteraksi dengan JSON mentah.

<div id="applovin" />

<Accordion title="Applovin">

<div id="attribution-link" />

#### Tautan atribusi:

```http HTTPS
https://app.appsflyer.com/com.company.app?af_ad=ad_name&af_ad_type=INTER
  &af_channel=video&af_siteid=123_site_id&af_c_id=b8******************************&
  af_adset=_DEFAULT&pid=applovin_int&c=campaign_name
  &af_click_lookback=7d&clickid=10****************
  &advertising_id=50********************************&af_ip=
```

#### Payload:

```json
{
      "adgroup": null,
      "campaign": "campaign_name",
      "media_source": "applovin_int",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "install_time": "2018-12-30 23:49:54.186",
      "adgroup_id": null,
      "orig_cost": "0.0",
      "click_time": "2018-12-24 14:29:33.738",
      "agency": null,
      "cost_cents_USD": "0",
      "af_ad_type": "INTER",
      "af_c_id": "b8******************************",
      "adset": null,
      "advertising_id": "50********************************",
      "af_sub1": null,
      "clickid": "10****************",
      "af_click_lookback": "7d",
      "af_siteid": "123_site_id",
      "af_ad": "ad_name",
      "http_referrer": null,
      "af_channel": "video",
      "af_adset": "_DEFAULT",
      "af_sub5": null,
      "af_sub4": null,
      "af_cpi": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

* Parameter di tautan atribusi muncul sebagai kolom di payload
* Kolom lain di payload yang **tidak ada di link atribusi** muncul dengan nilai null
* AppLovin mendukung pembagian biaya iklan tetapi mengirimkan data biaya ke AppsFlyer secara massal. Bidang terkait biaya kembali sebagai 0.

</Accordion>

<div id="ironsource" />

<Accordion title="ironSource">

<div id="attribution-link-1" />

#### Tautan atribusi:

```http HTTPS
https://app.appsflyer.com/id123456789?
  af_ua=Mozilla/5.0+(iPhone;+CPU+iPhone+OS+12_1_2+like+Mac+OS+X)+AppleWebKit/605.1.15+(KHTML,+like+Gecko)+Mobile/16C101
  &clickid=ab*******************&redirect=false
  &ua=Mozilla/5.0+(iPhone;+CPU+iPhone+OS+12_1_2+like+Mac+OS+X)+AppleWebKit/605.1.15+(KHTML,+like+Gecko)+Mobile/16C101
  &af_lang=pt&imei=&af_sub1=&advertising_id=&af_ip=192.168.0.1&pid=ironsource_int
  &device_ip=192.168.0.1&c=campaign_name
  &idfa=01**********************************&af_siteid=123_site_id&
  af_enc_data=cN*********************************************************************
```

#### Payload:

```json
{
      "adgroup": null,
      "af_enc_data": "cN**************************************************************************************",
      "campaign": "campaign_name",
      "media_source": "ironsource_int",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "install_time": "2018-12-30 23:59:32.194",
      "adgroup_id": null,
      "redirect": "false",
      "orig_cost": "0.75",
      "click_time": "2018-12-30 23:58:54.517",
     "agency": null,
      "cost_cents_USD": "75",
      "adset": null,
      "advertising_id": "35**********************************",
      "af_sub1": null,
      "af_ip": "192.168.0.1",
      "clickid": "ab*******************",
      "af_sub3": null,
      "af_cost_value": "0.75",
      "af_ref": "ironsource_5f******************************************",
      "af_siteid": "123_site_id",
      "http_referrer": null,
      "af_cost_model": "cpi",
      "af_ua": "Mozilla/5.0 (Linux; Android 8.0.0; SM-N950F Build/R16NW; wv) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/71.0.3578.99 Mobile Safari/537.36",
      "af_cost_currency": "USD",
      "af_sub5": null,
      "af_sub4": null,
      "af_lang": "en",
      "af_cpi": null,
      "af_click_lookback": "7d",
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

ironSource membagikan data terkait biaya dengan AppsFlyer setelah konversi menggunakan bidang `orig_cost`, `costs_cents_USD`, dan `af_cost_value` .

Namun, data terkait biaya **tidak muncul di tautan atribusi**. ironSource mengenkripsi data biaya dan menyimpannya di bidang `af_enc_data` .

</Accordion>

<div id="retargeting-conversion-data" />

## Menargetkan ulang data konversi

Penargetan ulang mencakup dua jenis konversi, atribusi ulang atau interaksi ulang.

> 👍 **Tips**
>
> Data konversi untuk penargetan ulang tidak selalu memberikan indikasi yang jelas tentang jenis konversi. Lihat [sumber data konversi alternatif](#sumber-data-konversi-alternatif).

<div id="re-attribution-with-srns" />

### Atribusi ulang dengan SRN

Saat pengguna diatribusikan ulang melalui SRN, payload data konversi tidak menunjukkan bahwa ini adalah kampanye penargetan ulang. Karena SRN tidak menggunakan tautan atribusi, tidak ada cara untuk menetapkan parameter `is_retargeting=true` pada tautan atribusi. Untuk **SRN yang mendukung penargetan ulang**, AppsFlyer menentukan apakah pengguna harus diatribusikan ulang atau tidak.

Artinya, tidak ada cara untuk menentukan, pada tingkat SDK, apakah penginstalan berasal dari kampanye penargetan ulang. Satu-satunya cara adalah mengatur nama kampanye sedemikian rupa sehingga menunjukkan kampanye penargetan ulang.

> 📘 **Catatan**
>
> Menyetel nama kampanye sedemikian rupa sehingga menunjukkan penargetan ulang **bukanlah metode yang sangat mudah**. Lihat [contoh untuk mempelajari lebih lanjut](#contoh-akuisisi-pengguna-campuran-dan-atribusi-ulang).

<div id="re-attribution-with-regular-ad-networks" />

### Atribusi ulang dengan jaringan iklan biasa

Atribusi ke jaringan iklan bergantung pada tautan atribusi. Baik tautan atribusi reguler atau OneLink, dengan penargetan ulang tautan atribusi selalu memiliki parameter `is_retargeting=true` yang ditetapkan di dalamnya.

<div id="retargeting-campaign-with-criteo" />

<Accordion title="Kampanye penargetan ulang dengan Criteo">

<div id="attribution-link-2" />

#### Link Atribusi

```http
https://app.appsflyer.com/id1234567895?pid=criteo_int&af_click_lookback=30d&
  c=campaign_name&is_retargeting=true&redirect=false&idfa=68**********************************
  &af_reengagement_window=30d
```

<div id="conversion-data-payload" />

#### Payload data konversi

```json
{
      "adgroup": null,
      "campaign": "campaign_name",
      "media_source": "criteo_int",
      "retargeting_conversion_type": "re-attribution",
      "adset_id": null,
      "campaign_id": null,
      "af_reengagement_window": "30d",
      "install_time": "2018-12-01 23:13:03.126",
      "adgroup_id": null,
      "redirect": "false",
      "af_sub5": null,
      "click_time": "2018-11-18 20:02:31.559",
      "agency": null,
      "cost_cents_USD": "0",
      "is_retargeting": "true",
      "af_cpi": null,
      "af_click_lookback": "30d",
      "af_siteid": null,
      "idfa": "68**********************************",
      "http_referrer": null,
      "orig_cost": "0.0",
      "af_sub4": null,
      "adset": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

* parameter `retargeting_conversion_type` - parameter ini menunjukkan jenis penargetan ulang. Dapat berupa atribusi ulang, interaksi ulang, atau tidak ada.
* parameter `is_retargeting: true` - parameter ini menunjukkan bahwa penginstalan adalah penginstalan yang dikaitkan ulang
* `af_reengagement_window`: Jendela atribusi interaksi ulang adalah jumlah hari di mana peristiwa dapat dikaitkan ke **pengguna yang berinteraksi ulang**. Karena ini adalah konversi atribusi ulang, parameter ini berlebihan.

</Accordion>

<div id="re-attribution-with-deferred-deep-linking" />

### Atribusi ulang dengan deferred deep linking

Sering kali, Anda ingin menautkan langsung pengguna yang dikaitkan ulang yang mana, menurut definisi dikaitkan ulang, tidak menginstal aplikasi. Misalnya, Anda menetapkan kampanye yang bertujuan untuk mengembalikan pengguna yang meng-uninstal aplikasi. Kampanye mempromosikan produk atau layanan dan Anda ingin melayani pengguna dengan konten yang terkait dengan produk atau layanan yang Anda iklankan.

Ini disebut sebagai Deferred Deep Linking (Tautan Langsung yang Tertunda) Payload data konversi untuk Deferred Deep Linking berasal dari metode `onConversionDataSuccess` .

<div id="deferred-deep-linking-with-srns" />

<Accordion title="Deferred Deep Linking dengan SRN">

Parameter Deep Link (Tautan Langsung) yang ditentukan dalam kampanye SRN tidak tersedia di luar SRN. Ini termasuk parameter `af_dp` , yang menyimpan jalur skema di aplikasi. Satu-satunya pengecualian untuk hal ini adalah saat menggunakan <Anchor target="_blank" href="/marketers/id/docs/google-ads-adwords-integration-setup-for-advertisers#menggunakan-penautan-langsung-yang-ditangguhkan-di-kampanye-aplikasi">kampanye Aplikasi Google pada Feeds</Anchor>. Untuk menerapkan deferred deep linking (tautan langsung yang tertunda), logika tambahan harus diterapkan untuk kampanye SRN. Gunakan data dalam tanggapan `onConversionSuccess` , seperti kampanye, set iklan, grup iklan, untuk mengalihkan pengguna Anda secara terprogram.

<div id="conversion-data-for-deferred-deep-linking-with-meta-ads" />

#### Data konversi untuk deferred deep linking dengan Meta ads

<Tabs>
<Tab title="Android">

```json
{
     "adset":"Adidas Running Shoes Women",
       "adgroup": null,
     "campaign_id":"6**********",
     "af_status":"Non-organic",
     "retargeting_conversion_type": "none",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,
     "is_first_launch":true,
     "click_time":"2017-07-18 12:55:05",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "campaign":"running shoes summer collection",
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "media_source":"Meta ads",
     "install_time":"2017-07-19 08:06:56.189",
     "af_sub2":null
  }
```

</Tab>

<Tab title="iOS">

```json
  {
     "media_source":"Meta ads",
     "campaign":"running shoes summer collection",
     "adset":"Running Shoes Women",
     "adgroup":null,
     "campaign_id":"6**********",
     "retargeting_conversion_type": "none",
     "af_status":"Non-organic",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,  
   "is_first_launch":true,
     "click_time":"2017-07-17 16:23:18",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "install_time":"2017-07-18 15:10:50.190",
     "af_sub2":null
  }
```

</Tab>
</Tabs>

Anda dapat menggunakan data dalam respons getConversionData, seperti kampanye, adset, dll. untuk mengalihkan pengguna secara terprogram dan menyajikan konten yang relevan kepada mereka.

> 📄 **Contoh**
>
> Aplikasi ini adalah aplikasi eCommerce yang memiliki spesialisasi di bidang pakaian olahraga. Pengguna yang belum menginstal aplikasi diajak oleh iklan dan menginstal aplikasi. Setelah aplikasi mulai, SDK mengembalikan data konversi. Developer membuat aplikasi membuka aktivitas (kampanye) **koleksi sepatu lari musim panas** di toko dan melayani kategori **sepatu lari untuk wanita** (adset).

</Accordion>

<div id="deferred-deep-linking-with-attribution-links" />

<Accordion title="Deferred deep linking dengan tautan atribusi">

Ada tiga cara untuk menautkan pengguna secara langsung:

<div id="uri-schemes" />

#### Skema URI

Ketika menggunakan Skema URI, untuk tautan atribusi dan OneLink, tautan atribusi dan payload adalah sebagai berikut:

**Link Atribusi**

```http
http://app.appsflyer.com/com.appsflyer.nivisampleapp?pid=media_source_name
  &c=campaign_name&af_dp=superapp%3A%2F%2deeplink-activity
```

**OneLink**

```http
// short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //long OneLink
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true&af_dp=superapp%3A%2F%2deeplink-activity
```

**Payload**

```json
{
      "af_deeplink": true,
      "campaign": "campaign_name",
      "media_source": "media_source_name",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "orig_cost": "0.0",
      "click_time": "2018-12-30 23:59:09",
      "install_time": "2018-12-30 23:59:39.330",
      "agency": null,
      "cost_cents_USD": "0",
      "adset": "AD_SET_NAME",
      "ad_id": "AD_ID",
      "af_siteid": null,
      "http_referrer": null,
      "af_cpi": null,
      "af_sub5": null,
      "af_sub4": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic",
      "scheme": "superapp",
      "host": "deeplink_activity"
  }
```

* `af_deeplink: true` - ketika parameter ini muncul dan diatur ke true, lihat untuk bidang skema dan `tuan rumah`
* `skema` dan `tuan rumah` - bidang-bidang ini datang dari parameter `af_dp` di tautan atribusi dan mengindikasikan skema dan aktivitas yang seharusnya sudah ditautkan langsung dengan pengguna

<div id="ios-universal-links-and-android-app-links" />

#### Tautan universal iOS dan tautan aplikasi Android

Ini adalah dua dari tiga cara untuk melakukan deep linking (tautan langsung).

Ketika menggunakan tautan universal atau tautan aplikasi, OneLink dan payload adalah sebagai berikut:

**OneLink**

```http
// short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //long OneLink
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true
```

**Payload**

```json
{
      "install_time": "2019-01-08 16:24:49.853",
      "cost_cents_USD": "0",
      "campaign": "campaign_name",
      "retargeting_conversion_type": "none",
      "is_first_launch": true,
      "click_time": "2019-01-08 16:24:14.322",
      "af_click_lookback": "7d",
      "orig_cost": "0.0",
      "af_status": "Non-organic",
      "iscache": "true",
      "shortlink": "71ba577e",
      "media_source": "media_source_name",
      "is_retargeting": true
  }
```

* bidang `shortlink` - ini adalah bidang yang menunjukkan OneLink spesifik dari mana pengguna datang. Hal ini membantu developer tahu cara untuk lanjut dalam hal mengaktifkan aktivitas dan memberikan konten. Bidang lain seperti `kampanye` juga dapat digunakan untuk tujuan ini.

  > 🚧 **Penting!**
  >
  > Bidang `shortlink` tidak tampak di payload ketika menggunakan OneLink panjang.
  >
  > Di kedua kasus (OneLink pendek atau panjang), kami merekomendasikan untuk menambahkan parameter kustom yang mengindikasikan aktivitas. Contohnya `&deep_link_activity=shoes_cateogry`


> 📘 **Catatan**
>
> Menggunakan tautan universal dan tautan aplikasi hanya mungkin dengan OneLink.

</Accordion>

<div id="re-engagement-with-srns" />

### Interaksi ulang dengan SRN

Seperti dengan kampanye Atribusi Ulang, ketika pengguna berinteraksi ulang melalui sebuah SRN, data konversi tidak mengindikasikan bahwa ini adalah kampanye interaksi ulang. Anda dapat mengatur nama kampanya sehingga mengindikasikan bahwa ini adalah kampanye interaksi ulang.

<div id="re-engagement-with-regular-ad-networks" />

### Interaksi Ulang dengan jaringan iklan reguler

Di sini juga, payload data konversi tidak mengindikasikan bahwa pengguna datang dari kampanye interaksi ulang. Untuk mengatasi keterbatasan ini, Anda dapat mengatur nama kampanye untuk mengindikasikan interaksi ulang.

<div id="re-engagement-with-deep-linking" />

### Interaksi ulang dengan deep linking

Bagian besar dari Interaksi Ulang adalah mengirimkan pengguna ke suatu aktivitas spesifik. Contohnya, jika Anda mengiklankan beberapa produk atau obral. Di kasus seperti ini, Anda ingin mengirimkan pengguna yang mengeklik iklan langsung ke aktivitas aplikasi untuk produk atau obral ini.

Untuk melakukan hal tersebut, Anda menggunakan Deep Linking. Data konversi di Deep Linking sangatlah penting. Data ini menyimpan informasi yang dibutuhkan developer untuk mengkustomisasi pengalaman pengguna dan mengirimkan mereka ke aktivitas yang tepat.

<div id="reengagement-deep-linking-with-srns" />

<Accordion title="Interaksi ulang: deep linking dengan SRN">

Data konversi tidak tersedia ketika pengguna yang berinteraksi ulang datang dari sebuah SRN. Programmer perlu untuk menggunakan metode SRN untuk membuat peluncuran aplikasi berjalan lancar.

</Accordion>

<div id="reengagement-deep-linking-with-ad-networks" />

<Accordion title="Interaksi Ulang: deep linking dengan jaringan iklan">

Ketika pengguna berinteraksi ulang dan aplikasi diluncurkan, data konversi berikut ini tersedia di metode `onAppOpenAttribution` :

Untuk iOS dan Android, saat menggunakan OneLink versi pendek, data konversinya adalah peta terstruktur dari semua parameter dalam link:

Contoh:

```json
{
     af_dp: "superapp://Deeplink",
     pid: "media_source_name"
     c: "campaign_name",
     link: "https://abcd.onelink.me/12ab/12ab34c"
     is_retargeting: true
  }
```

* Programmer aplikasi dapat menggunakan parameter seperti `af_dp` dan nama kampanye untuk mengirimkan pengguna ke aktivitas spesifik dan memberikan konten yang relevan.

> 🚧 **Penting!**
>
> Kami merekomendasikan untuk menggunakan OneLink versi pendek. Klik <Anchor target="_blank" href="/marketers/id/docs/understand-onelink-short-vs-long-urls">di sini</Anchor> untuk mempelajari lebih lanjut.

Alasan lain untuk menggunakan OneLink versi pendek adalah struktur data konversi yang dikembalikan oleh versi panjang. Saat menggunakan versi panjang, data konversi adalah peta dengan satu bidang yang disebut `link` yang menampung seluruh OneLink panjang.

```json
{
     "link": "https://abcd.onelink.me/12ab?pid=media_source&c=campaign_name&is_retargeting=true&af_dp=superapp%3A%2F%2FDeepLink"
  }
```

</Accordion>

<div id="alternative-conversion-data-sources" />

### Sumber data konversi alternatif

* Push API menawarkan muatan konversi mendetail yang menunjukkan atribusi ulang atau keterlibatan ulang. Payload Push API menyertakan bidang yang disebut `re_targeting_conversion_type`. Kolom ini menunjukkan jenis konversi, baik atribusi ulang atau interaksi ulang. Untuk mempelajari lebih lanjut, lihat <Anchor target="_blank" href="/marketers/id/docs/push-api-streaming-raw-data">panduan Push APIkami</Anchor>.
* Laporan Data Lengkap juga berisi indikator untuk jenis konversi. Di laporan data lengkap untuk penargetan ulang konversi, terdapat kolom bernama ***Nama Event***. Nilai dalam kolom ini adalah ***interaksi ulang*** atau ***atribusi ulang*** menurut jenis konversi.

<div id="examples-of-mixed-user-acquisition-and-re-attribution" />

### Contoh akuisisi pengguna campuran dan atribusi ulang

> 📄
>
> 1. Seorang pengguna menginstal aplikasi Anda, lalu meng-uninstal-nya. Tindakan penginstalan menempatkan pengguna di <Anchor target="_blank" href="/marketers/id/docs/set-up-re-attribution-window">jendela atribusi ulang</Anchor>. Anda megatur kampanye akuisisi pengguna  (tidak menargetkan ulang) dengan Meta ads. Anda juga mengatur integrasi AppsFlyer dengan Meta ads untuk mengizinkan penargetan ulang.
>
>    Saat masih dalam jendela atribusi ulang, pengguna melihat iklan, mengekliknya, dan menginstal ulang aplikasi. Sejauh yang dilihat AppsFlyer, pengguna adalah pengguna yang diatribusikan ulang.
>
>    Hal ini disebabkan oleh dua faktor:
>    1. Konfigurasi dengan Meta ads mengizinkan penargetan ulang
>    2. Pengguna berada di jendela atribusi ulang
>    Dalam hal ini, nama kampanye tidak menunjukkan atribusi ulang.
> 2. Mari kita ambil contoh yang sama, hanya kali ini pengguna berada di luar jendela atribusi ulang. Dalam hal ini, penginstalan adalah penginstalan non-organik yang baru.
> 3. Mari kita lihat contoh lain. Anda mengatur kampanye penargetan ulang di Meta ads. Beberapa pengguna menemukan kampanye dan menginstal aplikasi. Namun, pengguna ini menginstal aplikasi untuk pertama kalinya. Pengguna tersebut tidak dianggap sebagai pengguna yang diatribusikan ulang. Sebaliknya, AppsFlyer menganggap mereka sebagai pengguna yang berasal dari kampanye akuisisi pengguna.

<div data-zendesk-anchors="overview=ringkasan h_01HCY86CKDJK9TNHPAZB0QX2ZX=ringkasan nonorganic-conversion-data-payload-fields=bidang-payload-data-konversi-non-organik h_01HCY86CKDEMB3428YHCNJQA5R=bidang-payload-data-konversi-non-organik fields-always-available=bidang-selalu-tersedia h_01HCY86CKDBQRGAY7GHNBJE4WK=bidang-selalu-tersedia fields-available-in-some-cases=kolom-tersedia-dalam-beberapa-kasus h_01HCY86CKDYQMYB9BQ4MXWP8A5=kolom-tersedia-dalam-beberapa-kasus additional-fields=kolom-tambahan h_01HCY86CKD47M85AZVEA5C4JH7=kolom-tambahan limitations=batasan h_01HCY86CKEFX646H9BSKSFGZ36=batasan h_01HCY86CKEZ2483XB461M2C9EC=custom-parameter-names ua-conversion-data-with-srns=data-konversi-ua-dengan-srn h_01EGKTQN6XDYHA60P2WKHBBVFT=data-konversi-ua-dengan-srn a-note-about-facebook=catatan-tentang-meta-ads h_01HCY86CKENFEGX53G9G4SGPSK=catatan-tentang-meta-ads facebook-conversion-data=data-konversi-meta-ads h_01HCY86CKE658H36F3VJQMATQK=data-konversi-meta-ads h_01HCY86CKF6FY96PAWB5Y7YXSQ=google-ads-conversion-data h_01HCY86CKFMNNNJZTPGK4870YN=apple-search-ads-conversion-data h_01HCY86CKFS5SJBECSY42VRJWP=oath-ad-platforms-conversion-data ua-conversion-with-other-ad-networks=konversi-ua-dengan-jaringan-iklan-lain h_01HCY86CKFB0GEJRTYSXN9YZ08=konversi-ua-dengan-jaringan-iklan-lain h_01HCY86CKFY787RD4BHQDVEVFV=applovin attribution-link=tautan-atribusi h_01HCY86CKFXM5XXJZSPXPB6397=tautan-atribusi h_01HCY86CKFDDXWT2KKFTKKBGHM=payload h_01HCY86CKFV55GYY7C51D7F72S=ironsource attribution-link::a45a1b4a=tautan-atribusi-1 h_01HCY86CKFYGEYR2TRPSD87KDA=tautan-atribusi-1 payload::81867f5c=payload-1 h_01HCY86CKFKKFQDG1P42R1FSDJ=payload-1 retargeting-conversion-data=menargetkan-ulang-data-konversi h_01EHQ74JS84509GT6M93SZA4HX=menargetkan-ulang-data-konversi h_01HCY86CKFP0DWCFMKSB1V130D=tips reattribution-with-srns=atribusi-ulang-dengan-srn h_01HCY86CKFAVWP1W0ZNEN5P30A=atribusi-ulang-dengan-srn h_01HCY86CKF2QY9DV1J9MWHKJ5P=catatan reattribution-with-regular-ad-networks=atribusi-ulang-dengan-jaringan-iklan-biasa h_01HCY86CKF1PV8MRR902RAHQGW=atribusi-ulang-dengan-jaringan-iklan-biasa h_01HCY86CKF1RGK01VTV3EEHQVM=retargeting-campaign-with-criteo attribution-link::c16e96bb=link-atribusi h_01HCY86CKFSKBBMFKA8NN8XTPC=link-atribusi conversion-data-payload=payload-data-konversi h_01HCY86CKG2YQQC629SC3RAFKE=payload-data-konversi reattribution-with-deferred-deep-linking=atribusi-ulang-dengan-deferred-deep-linking h_01HCY86CKGXV50H79R0YH1GB2C=atribusi-ulang-dengan-deferred-deep-linking h_01HCY86CKG12YRGFEEJ27DQART=deferred-deep-linking-with-srns conversion-data-for-deferred-deep-linking-with-facebook=data-konversi-untuk-deferred-deep-linking-dengan-meta-ads h_01HCY86CKGX9VHSV3ASKXMFM0X=data-konversi-untuk-deferred-deep-linking-dengan-meta-ads h_01HCY86CKGHM9FKBEHMYBF4597=contoh h_01HCY86CKG3XWM4X0YH7WYCEH4=deferred-deep-linking-with-attribution-links uri-schemes=skema-uri h_01HCY86CKGDM2NE1FCRC92K8R0=skema-uri ios-universal-links-and-android-app-links=tautan-universal-ios-dan-tautan-aplikasi-android h_01HCY86CKGY1NE4214DES0Y2AV=tautan-universal-ios-dan-tautan-aplikasi-android h_01HCY86CKG1NGYR8WCS7NMM782=penting h_01HCY86CKG9VF8MBJQTWJGDJ6Z=catatan-1 reengagement-with-srns=interaksi-ulang-dengan-srn h_01HCY86CKG4TRYR6TWYYVB0FJE=interaksi-ulang-dengan-srn reengagement-with-regular-ad-networks=interaksi-ulang-dengan-jaringan-iklan-reguler h_01HCY86CKGM2JS7C9T71R6GPH1=interaksi-ulang-dengan-jaringan-iklan-reguler reengagement-with-deep-linking=interaksi-ulang-dengan-deep-linking h_01HCY86CKG0NPQAA2ZRWWNKGQD=interaksi-ulang-dengan-deep-linking h_01HCY86CKGEBHQVFRGJH96KDFJ=reengagement-deep-linking-with-srns h_01HCY86CKGJ9HG7AGB5MFP33RK=reengagement-deep-linking-with-ad-networks h_01HCY86CKGC3AF6YDKTY95XMV5=penting-1 alternative-conversion-data-sources=sumber-data-konversi-alternatif h_01HCY86CKG3N6ZXV70G4VMZ0X5=sumber-data-konversi-alternatif examples-of-mixed-user-acquisition-and-reattribution=contoh-akuisisi-pengguna-campuran-dan-atribusi-ulang h_01HCY86CKGK9DVVB7T6CVNB8ZN=contoh-akuisisi-pengguna-campuran-dan-atribusi-ulang" />
