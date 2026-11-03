---
title: API Kohort
metadata:
  keywords:
    - API
    - Advertisers
    - Partners
    - Developer
    - Premium
    - Gray
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2020-01-14T07:04:32Z'
  edited_at: '2023-11-20T15:14:33Z'
  id: 360004799057
  locale: id
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/id/articles/360004799057
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Sekilas:** API pelaporan kelompok memberi pemasang iklan cara terprogram untuk mendapatkan data Kelompok. Gunakan API untuk mengintegrasikan data Kelompok ke dalam BI dan sistem otomasi pemasaran.

## API pelaporan kelompok

API pelaporan kelompok digunakan untuk mendapatkan data kinerja kampanye kelompok dari platform AppsFlyer. Ini secara fungsional setara dengan <Anchor target="_blank" href="/marketers/id/docs/cohort-and-retention-dashboard">dashboard Kelompok</Anchor>.

### Pertimbangan untuk pengembang

* **Tanggal:** Tanggal atau rentang tanggal mengacu pada tanggal nilai seumur hidup (<Anchor target="_blank" href="/marketers/id/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV)</Anchor> , yang berarti tanggal pengguna diatribusikan (berkonversi) dan bukan tanggal aktivitas itu sendiri.
* **Nilai Boolean:** Benar atau salah (peka huruf besar-kecil).
* **Lalu lintas agensi yang transparan dan tidak transparan:** Sumber media dari lalu lintas yang didorong oleh agensi selalu berasal dari agensi dan bukan sumber media asli. Saat ini, kelompok versi UI berperilaku berbeda.
* **Aplikasi tunggal**: API Kelompok adalah solusi aplikasi tunggal. Hal ini berbeda dengan dashboard Kelompok yang mendukung banyak aplikasi dalam satu panggilan.
* **Keaktualan data:** Lihat [ciri-ciri dan batasannya](/docs/cohort-api#traits-and-limitations).

## Instruksi API

Bagian tersebut berisi informasi yang diperlukan bagi Anda untuk membuat dan menggunakan API Kelompok. 

<div id="cohort-api-facts" />

<Accordion title="Fakta API Kelompok">

| Ringkasan | Panggilan API terdiri dari jalur, header, dan JSON yang berisi kueri data. Data dikembalikan secara default dalam file CSV. |
| --- | --- |
| Jalur | `https://hq1.appsflyer.com/api/cohorts/v1/data/app/app_id` |
| Parameter jalur  (wajib) | <ul><li>`app_id`: Apakah pengidentifikasi aplikasi seperti yang ditemukan di dashboard AppsFlyer. Masukkan persis seperti yang ditampilkan di dashboard.</li></ul> |
| Parameter kueri<br /><br />(opsional) | Hasil dikembalikan sebagai CSV atau JSON. Struktur file CSV berbentuk tabel sedangkan struktur file JSON berorientasi pada catatan.<ul><li>[Default] <Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360006698277">`csv`</Anchor> [nama file](/docs/cohort-api#csv-file-name-structure) tergantung pada kueri.</li><li>`json` berisi bagian kueri dan hasil</li><li>Contoh: `format=json`</li><li>`https://hq1.appsflyer.com/api/cohorts/v1/data/app/app_id?format=json`</li></ul> |
| Metode HTTP | `POST` |
| Jenis konten yang diterima | `application/json` |
| Otorisasi | <ul><li>Token pembawa di header permintaan</li><li>Hubungi CSM Anda untuk mengaktifkan API Kelompok lalu <Anchor target="_blank" href="/marketers/id/docs/managing-appsflyer-tokens">Dapatkan token di dashboard</Anchor><ul><li>Token yang sama digunakan untuk semua aplikasi di akun</li></ul></li></ul> |
| Batasan tanggal | <ul><li>Tanggal paling awal yang didukung: 730 hari sebelum tanggal saat ini. Artinya 2 tahun)</li><li>Rentang kueri maksimum: 60 hari.</li></ul> |
| Batasan tingkat | <ul><li>Batas tarif panggilan API hingga 60 panggilan per menit dan 50.000 panggilan setiap hari per akun</li><li>Kueri menghasilkan hingga 30.000 baris</li></ul> |
| Nilai Boolean | Selalu dalam huruf kecil: *benar*, *salah* |

### Minta header

| Kode | Nilai | Wajib |
| --- | --- | --- |
| Content-Type | `application/json` | Ya |
| Authorization | `Pembawa api_token_placeholder` | Ya |
| Terima | `application/json` | Ya |

</Accordion>

<div id="filtering-and-grouping-parameters" />

<Accordion title="Memfilter dan mengelompokkan parameter">

Gunakan parameter filter berikut untuk mendapatkan data yang diperlukan. 

| Nama parameter | Deskripsi | Wajib |
| --- | --- | --- |
| <span id="cohort-_type"></span>cohort \_type | Jenis atribusi kelompok (konversi) adalah salah satu dari berikut ini: `user_acquisition`, `penargetan ulang`, `unified`<ul><li>Unified menggabungkan kinerja kampanye akuisisi pengguna dan penargetan ulang.</li><li>Jika suatu event diatribusikan ke kampanye penargetan ulang dan akuisisi pengguna, hanya event penargetan ulang yang disertakan dalam KPI yang ditampilkan, artinya *<Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">is\_primary=true</Anchor>.*</li><li>Format: String</li><li>Contoh: `"cohort_type": "user_acquisition"`</li></ul> | Ya |
| <span id="min_cohort_size"></span>min\_cohort\_size | Ukuran kelompok minimum digunakan untuk mengurangi jumlah catatan yang dikembalikan dengan mengecualikan kelompok yang memiliki sedikit pengguna. Artinya KPI *pengguna* memiliki nilai yang sama atau lebih besar dari yang ditentukan.<ul><li>Format: Integer</li><li>Nilai minimum yang diperbolehkan: 1. Jangan kirim 0 (Nol)</li><li>Default: 1</li><li>Contoh: `"min_cohort_size": 50`</li></ul> | Tidak |
| <span id="from"></span>dari | Batas bawah rentang tanggal atribusi LTV. Tanggal paling awal yang didukung adalah 720 hari sebelum tanggal saat ini.<ul><li>Format: String hh-bb-tttt</li><li>Contoh: `"dari": "02-01-2020"`</li></ul> | Ya |
| <span id="to"></span>to | Batas atas rentang tanggal atribusi LTV<ul><li>Jumlah hari dalam rentang: 1-31 hari</li><li>Untuk satu hari: nilai `from` dan `to` adalah identik.</li><li>Format: hh-bb-tttt</li><li>Contoh: `"dari": "01-01-2020", "to": 31-01-2020` adalah 31 hari.</li></ul> | Ya |
| <span id="granularity"></span>granularitas | Perincian per jam untuk 72 jam sebelumnya dengan mengatur  `"granularitas": "jam"` dan mengatur rentang `from` dan `to` untuk menyertakan waktu.<ul><li>Format: hh-bb-tttt dd:mm:jj</li><li>Contoh:</li></ul>`"granularity": "hour","from": "2021-12-01 14:00:00", "to": "2021-12-03 11:00:00",` | Tidak |
| <span id="partial_data"></span>partial\_data | Untuk menghindari distorsi data dan salah tafsir, Kelompok mengembalikan data hari lengkap. Namun, data sebagian hari dapat bermanfaat.<br /><br />Jumlah hari kelompok lengkap untuk sebuah kueri dihitung sebagai selisih antara tanggal hari ini dan tanggal *to* .<ul><li>[Default] Jika salah, hari lengkap akan kembali.</li><li>Jika benar, hingga 180 hari kelompok akan kembali, termasuk hari yang datanya tidak lengkap.</li><li>Format: Boolean</li><li>Versi UI platform: salah</li></ul>**Contoh**: Pada tanggal 10 Mei, jumlah hari kelompok lengkap bagi pengguna yang melakukan konversi selama tanggal 1-30 April adalah 10.<ul><li>Jika salah [default], hari kelompok 0-9, kembali. Ini adalah jumlah hari (10) antara tanggal konversi terakhir dan hari ini.</li><li>Jika benar, hari kelompok 1-40 akan kembali. Hari 11-40 berisi sebagian data dan tidak dikembalikan. Misalnya, sejak 20 April baru lewat 20 hari, dan seterusnya.</li></ul>**Catatan**: Data parsial hanya diperbolehkan jika jenis agregasi bersifat kumulatif. | Tidak |
| <span id="filters"></span>filter | Filter data dan hari periode yang dikembalikan. Pilih filter dari [daftar dimensi filter](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions).<ul><li>Format: String dalam JSON bersarang</li><li>**Contoh batasan untuk Geo tertentu:** `"filter": {"geo": "US"}` hanya mencakup pengguna yang dikaitkan dengan Amerika Serikat.</li><li>**Contoh hari periode (kelompok)**: Filter `periode` menetapkan hari pengembalian pengukuran. Nilai yang mungkin adalah: 0-180.</li><li>Default: Jika tidak ada filter periode yang diatur, hari 0-30, 60, 90, dan 180 akan kembali. [Contoh filter dengan periode](/docs/cohort-api#using-period-filters)</li></ul> | Tidak |

Gunakan parameter pengelompokan berikut untuk menyertakan kolom tambahan dan membuat laporan Anda tidak terlalu terperinci.

| Parameter | Nilai | Wajib |
| --- | --- | --- |
| pengelompokan | <ul><li>Pilih 1-7 pengelompokan dari [daftar dimensi pengelompokan](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions).</li><li>Format: String dalam suatu larik</li><li>Example: `"groupings": ["af_ad", "c", "af_c_id", "af_prt"]`</li></ul> | Ya |

</Accordion>

<div id="selecting-and-formatting-kpis" />

<Accordion title="Memilih dan memformat KPI">

* Tabel ini mencantumkan KPI yang tersedia dan fungsi terkaitnya. Saat Anda memanggil KPI, semua fungsinya kembali.
* KPI berikut selalu muncul: pengguna, ecpi, dan biaya
* Pilih satu KPI tambahan per panggilan.

<table><thead><tr><th> </th><th> </th><th colspan="5">Fungsi</th></tr><tr><th rowspan="2">Default/ Opsional </th><th rowspan="2">KPI (Nama dimensi) </th><th>Hitung</th><th>cvr (rasio konversi)</th><th>Rating</th><th>Jumlah</th><th>Pengguna unik</th></tr><tr><th>Jumlah</th><th>Persentase</th><th>Persentase</th><th>Jumlah</th><th>Jumlah</th></tr></thead><tbody><tr><td>Selalu</td><td>pengguna</td><td><span>Y</span></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>Selalu</td><td>ecpi</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td>Selalu</td><td>biaya</td><td>-</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td></tr><tr><td>Opsional</td><td><span><code>"event_name"</code>(4) </span></td><td><span>Y</span></td><td><span>Y</span></td><td>-</td><td><span>Y (3)</span></td><td><span>Y</span></td></tr><tr><td>Opsional</td><td>pendapatan</td><td><span>Y</span></td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td></tr><tr><td>Opsional</td><td>ROAS</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td>Opsional</td><td>roi</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td>Opsional</td><td>sesi</td><td><span>Y</span></td><td>-</td><td><span>Y</span></td><td>-</td><td><span>Y(1)</span></td></tr><tr><td>Opsional</td><td>mencopot penginstalan (2)</td><td><span>Y</span></td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr></tbody><tfoot><tr><td colspan="7"><p>(1) Sesi unik kembali saat <em>aggregation_type=on_day</em></p><p>(2) Tidak tersedia ketika cohort_type=unified </p><p>(3) Jumlah berarti total pendapatan yang dihasilkan oleh event tersebut. Dalam laporan, ini dilambangkan dengan <span><code>sum_event_name"</code></span></p><p><span>(4) Catatan! Nama event peka huruf besar-kecil</span></p></td></tr></tfoot></table>

| Parameter | Nilai | Parameter wajib |
| --- | --- | --- |
| kpi | Pilih **satu** KPI dari beberapa KPI yang tersedia. Di masa mendatang, kami berencana untuk mengizinkan pemilihan beberapa KPI.<ul><li>Untuk setiap KPI yang diminta, semua fungsi dikembalikan.</li><li>Format: String dalam suatu larik</li><li>Contoh A: `"kpis": ["sessions"]`</li><li>Contoh B: `"kpi": ["event_name"]`</li></ul> | Ya |

### Presentasi fungsi KPI

Parameter format KPI berikut mengatur format KPI yang dikembalikan.

| Parameter | Nilai | Wajib |
| --- | --- | --- |
| preferred\_currency | Mata uang pendapatan KPI<ul><li>Jika benar, pendapatan dikembalikan menggunakan <Anchor target="_blank" href="/marketers/id/docs/app-settings#localization-currency">mata uang khusus aplikasi</Anchor> yang ditetapkan di platform.</li><li>[Default] Jika salah, hasilnya akan dikembalikan dalam USD.</li><li>Format: Boolean</li><li>Versi UI platform: benar</li></ul> | Tidak |
| preferred\_timezone | **Zona waktu dari rentang data**<ul><li>Jika benar, waktu dinyatakan menggunakan <Anchor target="_blank" href="/marketers/id/docs/app-settings#localization-time-zone">zona waktu khusus aplikasi</Anchor> yang ditetapkan di platform.</li><li>[Default] Jika salah, waktu dinyatakan menggunakan zona waktu UTC.</li><li>Format: Boolean</li><li>Versi UI platform: benar</li></ul> | Tidak |
| aggregation\_type | <ul><li>`kumulatif`</li><li>`on_day`</li></ul>`"aggregation_type": "cumulative"`<br /><br />`Format: String` | Ya |
| per\_user | Bagilah fungsi KPI dengan jumlah pengguna aplikasi. Hanya berlaku untuk KPI yang relevan.<ul><li>Jika benar, nilai KPI dibagi dengan jumlah pengguna dalam kelompok.</li><li>Jika salah, nilai KPI tidak dibagi dengan jumlah pengguna.</li><li>Format: Boolean</li><li>Contoh jika benar: total pendapatan adalah $1000, jumlah pengguna aplikasi adalah 500, nilai yang dikembalikan adalah $2.</li></ul> | Tidak |

</Accordion>

<div id="list-of-group-by-and-filter-by-dimensions" />

<Accordion title="Daftar kelompok dan filter berdasarkan dimensi">

<table><tbody><tr><th><p>Nama dimensi </p></th><th><p>Nilai API dimensi</p></th><th><p>Pengelompokan</p></th><th><p>Filter</p></th></tr><tr><td><p><span>Iklan</span></p></td><td><p><span>af_ad</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>ID Iklan</span></p></td><td><p><span>af_ad_id</span></p></td><td><p><span>Y</span></p></td><td><span><span>Y</span></span></td></tr><tr><td><p><span>Kampanye</span></p></td><td><p><span>c</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>ID kampanye</span></p></td><td><p><span>af_c_id</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Saluran</span></p></td><td><p><span>af_channel</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Sumber Media</span></p></td><td><p><span>pid</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Sub Param 1</span></p></td><td><p><span>af_sub1</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Kata Kunci</span></p></td><td><p><span>af_keywords</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Agensi</span></p></td><td><p><span>af_prt</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Jenis Konversi (1) </span></p></td><td><p><span>cohort _type</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>ID Situs</span></p></td><td><p><span>site_id</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Jenis Pendapatan (2)</span></p></td><td><p><span>revenue_type</span></p></td><td><p><span><span>x </span></span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Jenis Sentuhan yang Diatribusikan (3)</span></p></td><td><p><span>attributed_touch_type</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Adset</span></p></td><td><p><span>af_adset</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>ID Adset</span></p></td><td><p><span>af_adset_id</span></p></td><td><p><span>Y</span></p></td><td><span> Y</span></td></tr><tr><td><p><span>Negara</span></p></td><td><p><span>geo</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Tanggal (tanggal penginstalan/atribusi ulang/interaksi ulang dalam konteks cohort_type yang dipilih) </span></p></td><td><p><span>tanggal</span></p></td><td><p><span>Y</span></p></td><td><span><span>x </span></span></td></tr><tr><td><p>Periode</p></td><td><p><span>periode </span><span></span></p><p><a href="./cohort-api#using-period-filters">Penjelasan detail</a></p></td><td><p><span><span>x</span></span></p></td><td><p><span>Y</span></p></td></tr><tr><td colspan="4"><p>Catatan: </p><p>Opsi dimensi:</p><p>(1) Jenis Konversi:  <span><code>user_acquisition</code>, <code>retargeting</code>(<code>re-engagement</code>, dan <code>re-attribution</code>), </span><span><code>unified</code></span></p><ul><li> <span>Saat mengekspor:</span><ul><li><span><code>re-engagement</code> akan ditampilkan sebagai <code>retargeting</code></span></li><li><span><code>re-attribution</code> akan ditampilkan sebagai <code>reattr</code></span></li></ul></li></ul><p>(2) Jenis Pendapatan: <code>regular</code>, <code>ad_monetization</code><span></span></p> (3) Jenis Sentuhan yang Diatribusikan: <code>click</code>, <code>impression</code>, <code>TV</code>, <code>pre-installed</code> </td></tr></tbody></table>

</Accordion>

<div id="curl-example" />

<Accordion title="Contoh Curl">

Contoh ini berisi panggilan API lengkap.

```shell
curl -L -X POST 'https://hq1.appsflyer.com/api/cohorts/v1/data/app/<insert your app_id here>?format=<insert results format here>' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <cohort_api_token_placeholder. Note the token has more than 700 characters.>' \
-H 'Accept: application/json' \
--data-raw '{
    "cohort_type": "user_acquisition",
    "min_cohort_size": 1,
    "preferred_timezone": false,
    "from": "2020-01-01",
    "to": "2020-01-31",
    "filters": {
        "period": [
            0,
            1,
            2,
            10,
            30,
            60
        ],
        "geo": [
            "US",
            "CN"
        ],
        "pid": [
            "Meta ads",
            "googleadwords_int"
        ]
    },
    "preferred_currency": true,
    "aggregation_type": "on_day",
    "per_user": false,    
    "groupings": [
        "pid",
        "date"
    ],
    "kpis": [
        "sessions"
    ]
}'
```

Contoh file yang dikembalikan: <Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360006698277">CSV</Anchor>, <Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360006773078">JSON</Anchor>

</Accordion>

<div id="python-example" />

<Accordion title="Contoh python">

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("hq1.appsflyer.com")
payload = "{\r\n    \"cohort_type\": \"user_acquisition\",\r\n    \"min_cohort_size\": 1,\r\n    \"preferred_timezone\": false,\r\n    \"from\": \"2020-05-01\",\r\n    \"to\": \"2020-05-10\",\r\n    \"preferred_currency\": true,\r\n    \"aggregation_type\": \"cumulative\",\r\n    \"per_user\": false,   \r\n     \"groupings\": [\r\n               \"pid\",\r\n         \"date\"\r\n        ],\r\n    \"kpis\": [\r\n        \"roas\"\r\n    ]\r\n}"
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer [Enter token here]',
  'Accept': 'application/json',
  'Content-Type': 'application/json'
}
conn.request("POST", "/api/cohorts/v1/data/app/[My App ID here]?format=csv", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

</Accordion>

<div id="use-case-examples" />

<Accordion title="Contoh kasus penggunaan">

**Contoh 1: Retensi**

Retensi sumber media (sesi)  pengguna yang menginstal aplikasi selama bulan Januari pada hari ke 7, 14, dan 28

```json
{  
  "per_user": false,
  "groupings": [
    "c"
  ],
  "filters": {
    "period": [
      7, 14, 28
    ]
  },
  "partial_data": false,
  "aggregation_type": "cumulative",
  "min_cohort_size": 1,
  "cohort_type": "user_acquisition",
  "from": "2021-01-01",
  "to": "2021-01-30",
  "kpis": [
    "Checkout Start"
  ]
}
```

**Contoh 2: Pembelian kampanye**

Pendapatan per kampanye kelompok hari ke-3 setelah penginstalan

```json
{  
  "per_user": false,
  "groupings": [
    "c"
  ],
  "filters": {
    "period": [
      3
    ],
    "c":[
        "example_campaign_name"
    ]
  },
  "partial_data": false,
  "aggregation_type": "cumulative",
  "min_cohort_size": 1,
  "cohort_type": "user_acquisition",
  "from": "2021-01-01",
  "to": "2021-01-30",
  "kpis": [
    "Checkout Start"
  ]
}
```

**Contoh 3: Aktivitas kemarin**Aktivitas apa yang dilakukan pengguna yang melakukan konversi (menginstal, berinteraksi kembali, mengatribusikan ulang) selama periode konversi tertentu kemarin?

Gunakan data yang tersedia melalui <Anchor target="_blank" href="/marketers/id/docs/cohort-analytics-via-data-locker">Kelompok untuk Data Locker</Anchor>. Periode konversi dibatasi hingga 360 hari sebelumnya.

</Accordion>

## Informasi tambahan

<div id="response-codes-and-troubleshooting" />

<Accordion title="Kode respons dan pemecahan masalah">

| Kode respons | Pesan | Komentar |
| --- | --- | --- |
| 200 | OK | Data valid dikembalikan |
| 200 | OK | <ul><li>Tidak ada data yang dikembalikan<ul><li>Kueri tersebut valid, namun tidak ditemukan data yang cocok dengan kueri tersebut.</li><li>Pastikan rentang tanggal tidak mencakup tanggal yang akan datang.</li><li>Tidak ada token sama sekali yang dikirim dalam panggilan tersebut.</li></ul></li></ul> |
| 401 | Tidak berwenang | <ul><li>Token otorisasi salah format, periksa apakah Anda menggunakan token yang benar, panjangnya harus lebih dari 700 karakter</li></ul> |
| 404 | Tidak ditemukan | <ul><li>Hilangkan masalah apa pun yang terkait dengan jaringan, firewall, dll.</li><li>Pastikan Anda menggunakan token terbaru yang diterbitkan. Dapatkan token saat ini dari dashboard.</li><li>Pastikan Aplikasi yang ditentukan di jalur diberi wewenang untuk menggunakan API Kelompok. Yang berarti aplikasi tersebut adalah bagian dari paket berlangganan. Admin akun AppsFlyer dapat memeriksanya di Paket Saya.</li></ul> |
| 422 | Entitas yang tidak dapat diproses | Alasan umum untuk kode kesalahan ini adalah:<ul><li>Pastikan permintaan tersebut terdapat dalam JSON dan tidak dikirim sebagai parameter kueri.</li><li>Pastikan JSON diformat sesuai dengan dokumen ini.</li><li>Tanggal ilegal</li></ul> |

</Accordion>

<div id="csv-file-name-structure" />

<Accordion title="Struktur nama file CSV">

Nama yang dialokasikan ke file CSV yang dikembalikan dihasilkan dari kueri API. Strukturnya dirinci pada tabel berikut.

**Contoh nama file CSV**

```
cohort_aggregation_type_per_user_kpi_report_app_id_from_to_timezone_currency_hash.csv
```

| Variabel | Nilai yang mungkin |
| --- | --- |
| aggregation\_type | <ul><li>*on\_day*</li><li>*kumulatif*</li></ul> |
| per\_user | <ul><li>*per\_user*</li><li>false: Null</li></ul> |
| kpi | Contoh: sesi |
| app\_id | ID aplikasi diminta |
| from | **from** tanggal: format *hh-bb-tttt* |
| to | **to** tanggal: format *hh-bb-tttt* |
| timezone | Zona waktu default UTC |
| currency | Kode mata uang default USD |
| hash | Panjang string hash alfanumerik=5 |

</Accordion>

<div id="using-period-filters" />

<Accordion title="Menggunakan filter periode">

Periode mengacu pada hari setlah atribusi, dimana periode 0 adalah hari atribusi. Misalnya, pengguna menginstal aplikasi pada tanggal 1 Januari. Ini adalah hari atribusi. Pembelian yang dilakukan pada periode 0 berarti dilakukan pada tanggal 1 Januari. Pembelian yang dilakukan pada periode 3 berarti dilakukan pada tanggal 4 Januari. Demikian pula, pengguna yang menginstal pada tanggal 11 Januari, ini adalah periode 0. Pembelian yang dilakukan pada tanggal 14 Januari akan menjadi periode 3.

Jika rentang tanggal laporan Anda adalah 1 Januari hingga 11 Januari, pengguna yang mengatribusikan (menginstal) selama periode ini akan disertakan dalam laporan. Tidak ada data lain yang disertakan.

* Nilai periode dapat berupa satu atau lebih dari 0-180 berikut ini. Misalnya 0, 1, 2, 30, 180.
* Jika tidak ada periode yang ditentukan, nilai default 0, 1, 2, dan seterusnya hingga 30, 60, 90, dan 180 akan dikembalikan.

> 📄 **Contoh filter periode**
>
> * Contoh ini berisi parameter kueri JSON, data lengkap, dan file CSV yang dihasilkan.
> * *Kueri periode filter* 0, 1, dan 2 dan KPI yang dipilih adalah *revenue*.
> * Hasilnya, data yang dikembalikan berisi:
>   * Ukuran pengguna, biaya, dan ecpi yang selalu kembali
>   * Ukuran pendapatan yang terdiri dari penjumlahan dan penghitungan untuk setiap periode yang berarti periode 0, 1, dan 2.
>
> **Kueri**
>
> ```json
> {
>     "cohort_type": "user_acquisition",
>     "min_cohort_size": 1,
>     "preferred_timezone": false,
>     "from": "2019-12-01",
>     "to": "2020-01-01",
>     "filters": {
>         "period": [
>             0,
>             1,
>             2
>         ]
>     },
>     "aggregation_type": "on_day",
>     "per_user": false,
>     "groupings": [
>         "pid"
>     ],
>     "kpis": [
>         "revenue"
>     ]
> }
> ```
>
> **Data Lengkap**
>
> **![mceclip1.png](https://files.readme.io/846aade481d3b5fa72536817533bc3edad721f1ce6015edcb48bd500461342b9-32131110606865.png)**
>
> **Hasil**
>
> ![mceclip0.png](https://files.readme.io/c284e5133e4e811b9416c850e399ddefb3c5bfcfcf879f469556b7a6bc0062c6-32131110607249.png)

</Accordion>

<div id="user-interface-mapping-to-api-parameters" />

<Accordion title="Pemetaan antarmuka pengguna ke parameter API">

Gambar berikut memetakan antarmuka pengguna analitik Kelompok ke parameter API. Kedua solusi - API dan antarmuka pengguna serupa tetapi tidak identik.

Versi API memiliki opsi tambahan berikut:

* Pilihan mata uang
* Pilihan zona waktu
* Pemfilteran berdasarkan periode

[![CohortMapping.jpg](https://files.readme.io/28b5973a6c476407f342cbc55dbf03162fdd3047d4fd9b93b78a6de8dff11cdb-360012218018.jpg)](https://files.readme.io/28b5973a6c476407f342cbc55dbf03162fdd3047d4fd9b93b78a6de8dff11cdb-360012218018.jpg) [![Cohortmapping2.jpg](https://files.readme.io/59f2e9fd5120b7efbb81a937a42ee4a8145fd7ae74ddf855ec6ba13f061ba6c2-360006378018.jpg)](https://files.readme.io/59f2e9fd5120b7efbb81a937a42ee4a8145fd7ae74ddf855ec6ba13f061ba6c2-360006378018.jpg)

Perbedaan antara jenis agregasi

![CohortRevnueCumulative.jpg](https://files.readme.io/1c9ca17e217a941e989556637d4397147bac9d1ab65e7485a10c0757a70dec41-360006379038.jpg)

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Sifat | Catatan |
| --- | --- |
| Akses jaringan iklan | Tidak. <Anchor target="_blank" href="/partners/id/docs/access-to-aggregated-analytics-tools-for-api-partners">Mitra pengelolaan kampanye</Anchor> dapat menggunakan API jika pemasang iklan memberikan izin. |
| Akses agensi | Tidak |
| Transparansi agensi | Tidak didukung |
| Zona waktu khusus aplikasi | Ya |
| Mata uang khusus aplikasi | Ya |
| Keterbatasan ukuran | Tidak ada |
| Batasan tingkat | Batas tarif panggilan API: 60 panggilan per menit per akun |
| Data organik | Tersedia |
| Data non-organik | Tersedia |
| Batasan data biaya | <ul><li>Data biaya hanya untuk kampanye dengan setidaknya 1 catatan penginstalan.</li><li>AppsFlyer tidak melaporkan data biaya untuk kata kunci yang berisi huruf besar dalam laporan kelompok atau API kelompok.</li><li>Anda tidak dapat menggabungkan beberapa kombinasi pengelompokan dengan biaya. Misalnya, Meta ads dapat memiliki pengelompokan geografis atau saluran, namun tidak keduanya. Kombinasi pengelompokan yang tepat bergantung pada jaringan iklan.</li></ul> |
| Keaktualan data | Keaktualan data bergantung pada [*partial\_data*](/docs/cohort-api#partial_data) sebagai berikut:<ul><li>[Default] Jika salah, <Anchor target="_blank" href="/marketers/id/docs/about-data-freshness-and-timezone-support#daily-processing">Setiap Hari</Anchor></li><li>Jika benar, <Anchor target="_blank" href="/marketers/id/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">Waktu aktual (berkelanjutan)</Anchor></li><li>Metrik biaya dan penghapusan instalasi diperbarui setiap hari di semua kasus</li></ul> |
| Data historis | Kelompok harian: 2 tahun |
| Akses pengguna akun | Token otorisasi tersedia untuk pengguna admin di dashboard |
| Pendapatan Iklan | Untuk event af\_ad\_revenue, metrik pengguna unik tidak tersedia jika jenis agregasinya adalah "pada hari", untuk tanggal antara 5 Oktober 2022-16 Februari 2023. |
| Pengelompokan mingguan dan bulanan | Pengelompokan dimensi mingguan dan bulanan tidak tersedia dengan API Kelompok. Gunakan dashboard Kelompok. |
| API Kohort | <ul><li>Periode konversi disebut sebagai 0 (Jam 0 atau Hari 0). Periode berikutnya setelah konversi disebut sebagai 1 (Jam 1 atau Hari 1), dan seterusnya.</li><li>Di AppsFlyer, periode kelompok tidak memperhitungkan stempel waktu penginstalan spesifik. Sebaliknya, jam kelompok dibulatkan ke bawah ke jam terdekat, dan hari kelompok didasarkan pada hari kalender. Hal ini dapat menyebabkan perbedaan saat membandingkan data kelompok AppsFlyer dengan data kelompok jaringan lain, di mana semua periode kelompok ditentukan oleh stempel waktu penginstalan spesifik (artinya satu jam adalah 60 menit stempel waktu setelah penginstalan, satu hari adalah periode 24 jam setelah penginstalan setelah stempel waktu penginstalan).</li></ul> |

</Accordion>

<div data-zendesk-anchors="cohort-reporting-api=api-pelaporan-kelompok 01H7WFZR41YAQX4MFPBMJD1MBP=api-pelaporan-kelompok considerations-for-developers=pertimbangan-untuk-pengembang 01H7WFZR414KXJBQS563VNKPXR=pertimbangan-untuk-pengembang api-instructions=instruksi-api 01H7WFZR41SNPGFKRH6J5DJG95=instruksi-api 01H7WFZR4184TKQYEC4Q10D9HH=cohort-api-facts request-headers=minta-header 01H7WFZR42NHX3N1V72VKP06ZR=minta-header 01H7WFZR42H3CA0CSB4E3XED3H=filtering-and-grouping-parameters 01H7WFZR42XV4JY46GY11KT3CF=selecting-and-formatting-kpis presentation-of-kpi-functions=presentasi-fungsi-kpi 01H7WFZR43HFF65TSWG1AN0JTB=presentasi-fungsi-kpi 01H7WFZR43BJ8E6KVHSGV4CDDP=list-of-group-by-and-filter-by-dimensions 01H7WFZR448CBBZ3V7RT0PF072=curl-example 01H7WFZR44RBVB9Q6VZPG1EWNX=python-example 01H7WFZR44H0G3QCBRTRQ5Y0HD=use-case-examples additional-information=informasi-tambahan 01H7WFZR448RNM8539DD8WCBH0=informasi-tambahan 01H7WFZR441022SK7BQB00F0BJ=response-codes-and-troubleshooting 01H7WFZR443YKCSJTHJ9W6H2S3=csv-file-name-structure 01H7WFZR440NTXWWQ2T4P2ANWK=using-period-filters 01H7WFZR44RCXA56CXSCEZ0KXH=contoh-filter-periode 01H7WFZR45QFHJWXZAAX2HRXQ2=user-interface-mapping-to-api-parameters 01H7WFZR45VC96KYW1W9A8PBFT=traits-and-limitations" />
