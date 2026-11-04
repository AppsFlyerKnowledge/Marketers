---
title: API OpenDSR
metadata:
  keywords:
    - Advertisers
    - GDPR
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2022-12-12T09:14:00Z'
  edited_at: '2023-12-04T11:41:04Z'
  id: 11332840660625
  locale: id
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/id/articles/11332840660625
---
> **Sekilas:** Artikel ini ditujukan untuk penggunaan klien AppsFlyer, sering disebut sebagai pemasang iklan atau pemilik aplikasi, menggunakan Platform untuk mencatat penggunaan dan atribusi aplikasi. Pemilik aplikasi menerapkan OpenDSR (Permintaan Subjek Data) API untuk mematuhi undang-undang perlindungan data yang berlaku seperti GDPR (Eropa), CCPA (California), LGPD (Brasil), dan PDPA (Thailand).

**Pernyataan dari pengacara kami:** *Tidak ada pernyataan di sini yang merupakan nasihat hukum. Panduan ini hanya disediakan untuk informasi dan kenyamanan Anda. Anda harus bekerja sama dengan penasihat hukum dan profesional lainnya untuk menentukan dengan pasti apakah  GDPR, CCPA, atau undang-undang lainnya berlaku atau tidak untuk Anda.* Hubungan privasi antara Anda dan AppsFlyer diatur oleh<Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy">Kebijakan Privasi Layanan AppsFlyer</Anchor>. Untuk pertanyaan apa pun yang berkaitan dengan Kebijakan Privasi Layanan ini atau untuk menghubungi petugas perlindungan data kami, silakan kirim email kepada kami ke [privacy@appsflyer.com](mailto:privacy@appsflyer.com). Untuk tujuan Pasal 27 Regulasi Perlindungan Data Umum, perwakilan AppsFlyer di Uni Eropa adalah AppsFlyer Germany GmbH, Schönhauser Allee 180, 10119 Berlin, Jerman (hubungi [privacy@appsflyer.com](mailto:privacy@appsflyer.com); +49-30-166373500).

<div id="privacy-regulations" />

## Peraturan perlindungan privasi

Dalam artikel ini, referensi peraturan privasi mencakup peraturan yang tercantum dalam tabel berikut.

| Peraturan | Logo | Deskripsi |
| --- | --- | --- |
| GDPR | ![GDPR.png](https://files.readme.io/c3eb63a14b95bda24478f1d8fec75bcc59789157c4e53ffb44ab77ccd6dfe091-12830387561233.png) | Peraturan Perlindungan Data Umum adalah peraturan UE (Uni Eropa) yang berkaitan dengan perlindungan data dan privasi untuk warga negara Uni Eropa |
| CCPA | ![CCPA.png](https://files.readme.io/57988a70f4e8395b9562fce9e424348cd7d61401ec7ca0ff32de518a093eb4dc-12830389364241.png) | Undang-Undang Privasi Konsumen California |
| LGPD | ![LGPD.png](https://files.readme.io/4e50bdc8e83db49b4eb0d84f757816ebc1d0e461ae8792af9ab48d7e51d20af3-12830406815633.png) | Lei Geral de Proteção de Dados |
| PDPA | ![6137_Privacy_Shield_Thailand-01.png](https://files.readme.io/90833957690e7a52eb43b330d34a85c67af7a6c071b8ac79dec0733ec9aafcfc-12830408352657.png) | Undang-Undang Perlindungan Data Pribadi (Personal Data Protection Act/PDPA) |

Istilah peraturan privasi, GDPR, CCPA, LGPD, dan PDPA digunakan secara bergantian dalam artikel ini.

<div id="the-opendsr-initiative" />

### Inisiatif OpenDSR

Untuk menjawab dan mengelola permintaan oleh Subjek Data yang dikirimkan sesuai dengan peraturan privasi, AppsFlyer, bersama dengan mParticle, Amplitudo, dan Braze, memprakarsai protokol OpenDSR (sebelumnya dikenal sebagai OpenGDPR).

OpenDSR adalah kerangka kerja sumber terbuka, yang memfasilitasi kerja sama antara perusahaan teknologi untuk penggunaan data konsumen yang adil dan transparan. Ini memungkinkan vendor untuk mengambil tindakan privasi data di berbagai sistem yang memproses dan menyimpan data pelanggan.

<Anchor target="_blank" href="https://www.appsflyer.com/company/newsroom/pr/opengdpr-initiative/">Pelajari lebih lanjut tentang inisiatif OpenDSR</Anchor>.

<div id="definitions" />

### Definisi

| Istilah DSR | Istilah AppsFlyer | Deskripsi |
| --- | --- | --- |
| User | Pengguna Aplikasi atau Pengguna Akhir | Pengguna Aplikasi adalah orang yang datanya dikumpulkan |
| Pengontrol Data | Pemilik Aplikasi atau Pengiklan | Pemilik Aplikasi menentukan tujuan dan sarana yang digunakan untuk memproses data pribadi. |
| Pemroses Data | AppsFlyer dan mitra | AppsFlyer dan partnernya memproses data pribadi atas nama pengontrol data |

<div id="dsr-requirements" />

### persyaratan DSR

DSR merinci hak wajib Subjek Data, yang harus dipatuhi oleh Pengontrol Data. Untuk tujuan API, hak ini diterjemahkan ke dalam jenis permintaan. Rincian berikut menjelaskan bagaimana AppsFlyer memproses berbagai jenis permintaan.

| **Jenis permintaan**<br /><br />**(Hak)** | **Definisi GDPR** | Memproses permintaan oleh AppsFlyer |
| --- | --- | --- |
| **Akses** | <ul><li>Jika diminta, Pengguna Aplikasi memiliki hak untuk mengetahui apa, mengapa, dan untuk berapa lama pemilik Aplikasi akan memproses data mereka.</li><li>Jika data dibagikan dengan pihak ketiga, seperti AppsFlyer, Pengguna Aplikasi memiliki hak untuk mengetahui siapa pihak ketiga tersebut.</li><li>Hak untuk mengetahui kategori data yang sedang diproses.</li><li>Jika ada pemrosesan otomatis yang memiliki efek signifikan pada user</li></ul> | Pemilik Aplikasi menerima salinan data pribadi Pengguna Aplikasi yang diproses. |
| **Portabilitas** | Pengguna Aplikasi harus menerima semua data pribadi mereka dalam format yang terstruktur, umum digunakan, dan dalam format yang dapat dibaca sistem, seperti file CSV. | Pemilik Aplikasi menerima salinan data pribadi Pengguna Aplikasi yang diproses. |
| **Rektifikasi** | Mengizinkan Pengguna Aplikasi mengoreksi data mereka jika mereka melihatnya sebagai data tidak akurat atau tidak benar. Pemilik Aplikasi diwajibkan untuk menghapus atau mengoreksi data yang tidak benar atau tidak selesai. | <ul><li>AppsFlyer menghapus data Pengguna Aplikasi yang direkam sebelum tanggal permintaan *koreksi* .</li><li>Data yang diterima setelahnya direkam oleh AppsFlyer.</li></ul> |
| **Penghapusan** | Hak penghapusan mengharuskan Pemilik Aplikasi untuk menghapus data pribadi dalam waktu 14 hari setelah menerima permintaan. | Data dihapus |

<div id="appsflyer-gdpr-requests-api" />

## GDPR Requests API AppsFlyer

Gunakan API Permintaan GDPR seperti yang dijelaskan di bagian ini untuk menerapkan kepatuhan DSR.

* **Permintaan GDPR:** Melakukan salah satu dari jenis permintaan di atas: akses, portabilitas, penghapusan, koreksi.
* **Permintaan Status** - Kueri terhadap status permintaan GDPR saat ini
* **Permintaan Keterangan**: Pertanyaan tentang versi API dan Format Data yang didukung
* **Pembatalan**: Membatalkan permintaan GDPR selama tahap ***tertunda***.

Pemilik Aplikasi harus menerapkan perubahan UI pada aplikasi mereka sehingga Pengguna Aplikasi dapat mengirimkan permintaan. Perhatikan bahwa permintaan GDPR adalah per satu pengguna pada satu waktu.

<div id="1-gdpr-request" />

<Accordion title="1. Permintaan GDPR">

<div id="gdpr-request-flow" />

### Alur Permintaan GDPR

Jenis-jenis permintaan GDPR, akses, portabilitas, penghapusan, dan koreksi, memiliki alur yang sama:

1. **Pengguna Aplikasi** mengajukan permintaan.
2. **Pemilik Aplikasi** membuat permintaan GDPR (lihat di bawah) dan mengirimkannya ke AppsFlyer.
3. **AppsFlyer** menerima permintaan tersebut dan memberi respons "201 OK" untuk permintaan yang valid.
4. Selama 48 jam berikutnya, permintaan ini menunggu giliran untuk diproses dan memiliki status ***tertunda***. Pengguna Aplikasi dapat membatalkan permintaan tersebut.
5. Setelah 48 jam, status permintaan berubah menjadi ***in\_progress (dalam proses).*** AppsFlyer mengirimkan postback ***perubahan status*** . Saat ini, permintaan tidak dapat dibatalkan.
6. Dalam 14 hari (lihat catatan di bawah), AppsFlyer memenuhi permintaan, dan status permintaan diperbarui menjadi ***selesai***. AppsFlyer mengirimkan postback perubahan status.
   * Dalam kasus *penghapusan* atau *koreksi*, data Pengguna Aplikasi dihapus.
   * Dalam hal *portabilitas* atau *akses,* data Pengguna Aplikasi dapat diakses di dashboard AppsFlyer di bawah **GDPR** atau melalui Request API (lihat di bawah).

   **Catatan:** Periode 14 hari ini dimulai setelah periode ***tertunda*** 48 jam berakhir. Dengan demikian, total periode pemenuhan permintaan adalah 16 hari setelah Pemilik Aplikasi mengirimkan permintaan ke AppsFlyer.

<div id="gdpr-request-format" />

### Format Permintaan GDPR

GDPR Request API dapat dikirimkan via HTTP POST ke titik akhir berikut ini:

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests
```

Untuk otorisasi API, gunakan token V2 API yang sama seperti untuk Pull API. Pengguna admin dapat <Anchor target="_blank" href="/marketers/id/docs/managing-appsflyer-tokens#mengambil-token-api">mengambil token</Anchor> dari halaman token API di dashboard. Tambahkan token ke header permintaan sebagai berikut: `'Otorisasi': 'Pembawa %AuthTokenV2% '`

<div id="parameters" />

#### Parameter

<table><thead><tr><th><strong>Nama Properti</strong></th><th><strong>Wajib</strong></th><th><strong>Deskripsi</strong></th></tr></thead><tbody><tr><td><strong>subject_request_id</strong></td><td>Ya</td><td>String UUID v4. Dihasilkan oleh pengontrol pada saat pengajuan permintaan ke Prosesor. String ini dapat digunakan untuk memeriksa status permintaan, memperbarui, atau membatalkannya.</td></tr><tr><td><strong>subject_request_type</strong></td><td>Ya</td><td><p>Nilai string yang mewakili jenis Permintaan GDPR.  Nilai bantuan:</p><ul><li>erasure</li><li>portability</li><li>access</li><li>rectification</li></ul></td></tr><tr><td><strong>subject_identities</strong></td><td>Ya</td><td><ul><li>Serangkaian objek identitas yang mendefinisikan identitas pemohon (lihat di bawah).</li><li>Setiap permintaan hanya dapat berisi satu identitas subjek.</li></ul></td></tr><tr><td><strong>submitted_time</strong></td><td>Ya</td><td><ul><li>String tanggal RFC 3339 yang mewakili waktu permintaan aktual dari subjek data</li><li>Stempel waktu dalam UTC</li></ul></td></tr><tr><td><strong>property_id</strong></td><td>Ya</td><td><p>String yang mewakili aplikasi mobile yang mana�permintaan ini dicakup</p><p><strong>Contoh</strong>:</p><ul><li> iOS: id123456789 </li><li> <strong>Android</strong>: com.example, com.publishers.name </li><li> <strong>Android out-of-store</strong>: com.publisher.name-channel<br/> <strong>Catatan:</strong> Dalam beberapa kasus, pemilik aplikasi merekam atribusi out-of-store menggunakan nama Google Play Android. Dalam kasus ini, gunakan nama aplikasi reguler seperti yang ditampilkan di Dashboard.</li></ul></td></tr><tr><td><strong>api_version</strong></td><td>Tidak</td><td>Versi string  yang diinginkan dari API GDPR Requests</td></tr><tr><td><strong>status_callback_urls</strong> </td><td>Tidak, tapi direkomendasikan</td><td><ul><li>Larik sampai 3 titik akhir untuk status callback yang akan dikirim ke perubahan status permintaan berikut.</li><li>Hanya <span>titik akhir HTTPS yang didukung.</span> </li><li><span>URL yang tidak valid ditolak.</span></li></ul></td></tr><tr><td rowspan="2"> <strong>platform</strong><br/><br/> </td><td>Tidak</td><td><p>Nilai adalah salah satu platform DSR yang didukung: <br/><code>android</code>, <code>ios</code>, <code>web</code>, <code>windowsphone</code></p></td></tr><tr><td>Ya</td><td><p>Untuk permintaan platform CTV, PC, atau Konsol, sertakan salah satu platform berikut: </p><p><span> </span><code>nativepc</code><span>, </span><code>playstation</code><span>, </span><code>roku</code><span>, </span><code>steam</code><span>, </span><code>webos</code><span>, <br/></span><code>vidaa</code><span>,</span><code>tizen</code><span>, </span><code>smartcast</code><span>, </span><code>chatgpt</code><span>, </span><code>battlenet</code><span>, <br/></span><code>quest</code><span>, </span><code>switch</code><span>, </span><code>xbox</code><span>, </span><code>epic</code></p></td></tr></tbody></table>

<div id="subject_identities-objects" />

#### Objek Subject\_identities

| Jenis Objek | **Wajib** | **Deskripsi** |
| --- | --- | --- |
| identity\_type | Ya | <ul><li>Jenis identitas dalam format string untuk platform `android`, `ios`, `web`, `windowsphone` adalah salah satu dari berikut ini:<ul><li>ios\_advertising\_id</li><li>android\_advertising\_id</li><li>fire\_advertising\_id</li><li>microsoft\_advertising\_id</li><li>appsflyer\_id</li></ul></li></ul><ul><li>Jenis identitas dalam format string untuk platform `CTV`, `PC`, dan `Konsol`:<ul><li>appsflyer\_id</li><li>customer\_user\_id (CUID)</li></ul></li></ul><ul><li>Contoh: `android_advertising_id`</li></ul> |
| identity\_value | Ya | <ul><li>Format: String</li><li>Misalnya: "a7551968-d5d6-44b2-9831-815ac9017798"</li></ul> |
| identity\_format | Ya | <ul><li>Metode ini digunakan untuk menyandikan identity\_value: `raw` adalah satu-satunya yang didukung:</li><li>Contoh: "raw"</li></ul> |

<div id="example-gdpr-erasure-request" />

### Contoh: permintaan penghapusan GDPR

**Contoh permintaan penghapusan untuk platform `android`, `ios`, `web`, `windowsphone` :**

```bash
curl --location --request POST 'https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \  
--header 'Authorization: Bearer %AuthTokenv2% \
--data-raw '{ 
 "subject_request_id":"f4e5a271-f25e-4107-b681-************",
 "subject_request_type":"erasure",
 "submitted_time":"2020-07-05T10:00:00Z",
 "platform": "android",
 "subject_identities":[ 
  { 
   "identity_type":"android_advertising_id",
   "identity_value":"55*****-****-****-************",
   "identity_format":"raw"
  }
 ],
 "api_version":"0.1",
 "property_id":"com.*********.*********.*********",
 "status_callback_urls":[ 
 "https://examplecontroller.com/opendpr_callbacks"
 ] 
 }'
```

**Contoh permintaan penghapusan untuk platform`CTV`, `PC`, dan `Konsol` :**

```bash
curl --location --request POST 'https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \  
--header 'Authorization: Bearer %AuthTokenv2% \
--data-raw '
{"requester": "test@email.com",
"subject_request_id":"valid-uuid4-string",
"subject_request_type":"erasure",
"submitted_time":"2020-07-05T10:00:00Z",
"subject_identities":[ 
 { 
  "identity_type":"appsflyer_id",
  "identity_value":"valid-appsflyer-id-string",
  "identity_format":"raw"
 }
],
"api_version":"0.1",
"property_id":"app-id",
"platform": "roku",
"status_callback_urls":[ 
 "https://examplecontroller.com/opengdpr_callbacks"
 ]
}'
```

<div id="zd-gdpr-erasure-request-code-example" />

<div id="gdpr-erasure-request-code-example" />

### Contoh Kode Permintaan Penghapusan GDPR

<Tabs>
<Tab title="Java">

```java
/* 
menggunakan paket okhttp instal dari maven
https://mvnrepository.com/artifact/com.squareup.okhttp3/okhttp
 */ 

 impor okhttp3.*;
import java.io.IOException;

public class GdprSendRequest {
 public static void main(String[] args){

  OkHttpClient client = new OkHttpClient();
  RequestBody body = RequestBody.create(null, "" + 
 "{\r\n\"subject_request_id\": \"\"," + 
 "\r\n\"subject_request_type\": \"hapus\"," + 
 "\r\n \"platform\": \"android\"," + 
 "\r\n\"submitted_time\": \"2018-11-02T15:00:00Z\"," + 
 "\r\n\" subject_identities\": [\r\n" + 
 "{\r\n\"identity_type\": \"android_advertising_id\"," +
  "\r\n\"identity_value\": \"\"," +
  "\r\n\"identity_format\": \"raw\"\r\n}" + 
 "\r\n]," + 
 "\r\n\"property_id\": \"com.example.application\"} }");

  Request request = new Request.Builder()
  .url("https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/opendsr_requests")
  .post(body)
  .addHeader("Content-Type", "aplikasi/json") 
 .addHeader("Terima", "application/json") 
 .addHeader("Otorisasi: Bearer", "")
  .build();

  coba {
   Response response = client.newCall(request).execute();
   System.out.println(response.code());
   System.out.println(response.body().string());
   System.exit(0);
  } catch (IOException e) {
   e.printStackTrace();
   System.exit(1);
  }
 }
}
```

</Tab>

<Tab title="Python">

```python
""" menggunakan paket permintaan python, 
 instal menggunakan permintaan instal pip """ 

 permintaan impor 
 impor json 
 headers = {
 "Content-Type": "application/json",
 "Accept": "application/json",
 "Authorization: Bearer": ""
}

body = { 
 "subject_request_id": "", 
 "subject_request_type": "erasure ", 
 "submitted_time": "2018-10-02T15:00:00Z", 
 "platform": "android", 
 "subject_identities": [
  { "identity_type": "android_advertising_id", 
   "identity_value": "", 
   "identity_format": "raw" }
  ], 
 "property_id": "com.example .aplikasi" 
} 
body = json.dumps(body) 
res = requests.request("POST", 
"https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests", 
headers=headers, data=body, params=params) 
print(res.text)
```

</Tab>

<Tab title="Node.js">

```javascript
/* menggunakan paket npm permintaan, 
instal menggunakan npm instal permintaan */

var request = require("request");
var options = { method: 'POST',
 url: 'https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests',
 headers: 
 { Accept: 'application/json',
  'Content-Type': 'application/json',
  'Authorization: Bearer': '' },
 body:
 { subject_request_id: '',
  subject_request_type: 'erasure',
  submitted_time: '2018-10-02T15:00:00Z',
  platform: 'android',
  subject_identities: 
  [ { identity_type: 'android_advertising_id',
   identity_value: '',
   identity_format: 'raw' } ],
 property_id: 'com.example.application'
 },
 json: true };
request(options, function (error, response, body) {
 if (error) throw new Error(error);

 console.log(body);
});
```

</Tab>

<Tab title="C#">

```csharp
using System;
 using RestSharp;
 namespace CS
 {
  class Gdpr
  {
   static void Main(string[] args)
   {
 		var url = "https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests";
   var client = new RestClient(url);
   var request = new RestRequest(Method.POST);
   request.AddHeader("Content-Type", "application/json");
   request.AddHeader("Accept", "application/json");
   request.AddHeader("Authorization: Bearer", "")
   var body = "{\r\n\"subject_request_id\": \"\"," + 
    "\r\n \"subject_request_type\": \"erasure\"," + 
    "\r\n \"submitted_time\": \"2018-11-02T15:00:00Z\"," +
    "\r\n \"platform\": \"android\"," +
    "\r\n \"subject_identities\": [\r\n" +
    "{ \r\n \"identity_type\": \"android_advertising_id\"," +
    "\r\n \"identity_value\": \"\"," + 
    "\r\n \"identity_format\": \"raw\"\r\n }" + 
    "\r\n ]," + 
    "\r\n \"property_id\": \"com.example.application\"}";

    request.AddParameter("undefined", body,ParameterType.RequestBody);
    IRestResponse response = client.Execute(request);
    // handle response by reading response.StatusCode
    Console.WriteLine(response.Content);
   }
  }
```

</Tab>
</Tabs>

</Accordion>

<div id="2-status-request" />

<Accordion title="2. Permintaan Status">

Setiap permintaan GDPR yang diajukan nanti akan dapat dilihat statusnya dengan menentukan `subject_request_id`. Ada empat jenis status yang tersedia:

1. ***pending*** - Permintaan valid telah diterima dan sedang dalam antrean
2. ***in\_progress*** - Permintaan sedang diproses
3. ***completed*** - Permintaan telah diselesaikan
4. ***canceled*** - Permintaan telah dibatalkan

<div id="status-request-format" />

### Format Permintaan Status

Permintaan dapat dikirimkan via HTTP GET ke *endpoint* berikut:

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

<div id="status-response-example" />

### Contoh Respons Status

```http
HTTP/1.1 200 OK
Content-Type: application/json
X-OpenGDPR-Processor Domain: example processor.com
X-OpenGDPR-Signature:
kiGlog3PdQx+FQmB8wYwFC1fekbJG7Dm9WdqgmXc9uKkFRSM4uPzylLi7j083461xLZ+mUloo3tpsmyIZpt5eMfgo7ejXPh6lqB4ZgCnN6+1b6Q3NoNcn/+11UOrvmDj772wvg6uIAFzsSVSjMQxRs8LAmHqFO4cF2pbuoPuK2diHOixxLj6+t97q0nZM7u3wmgkwF9EHIo3C6G1SI04/odvyY/VdMZgj3H1fLnz+X5rc42/wU4974u3iBrKgUnv0fcB4YB+L6Q3GsMbmYzuAbe0HpVA17ud/bVoyQZAkrW2yoSy1x4Ts6XKba6pLifIHf446Bubsf5r7x1kg6Eo7B8zur666NyWOYrglkOzU4IYO8ifJFRZZXazOgk7ggn9obEd78GBc3kjKKZdwaCrLx7WV5y9TMDCf+2FILOJM/MwTUy1dLZiaFHhGdzld2AjbjK1CfVzyPssch0iQYYtbR49GhumvkYl11S4oDfu0c3t/xUCZWg0hoR3XL3B7NjcrlrQinB1KbyTNZccKR0F4Lk9fDgwTVkrAg152UqPyzXxpdzXjfkDkSEgAevXQwVJWBNf18bMIEgdH2usF/XauQoyrne7rcMIWBISPgtBPj3mhcrwscjGVsxqJva8KCVCKD/4Axmo9DISib5/7A6uczJxQG2Bcrdj++vQqK2succ=
{
 "controller_id":"example_controller_id",
 "expected_completion_time":"2018-11-01T15:00:01Z",
 "subject_request_id":"a7551968-d5d6-44b2-9831-815ac9017798",
 "request_status":"pending",
}
```

<div id="status-postbacks" />

### Postback Status

Seperti dijelaskan pada Alur Permintaan GDPR di atas, saat status permintaan GDPR berubah, dari ***pending*** menjadi ***in\_progress*** kemudian ***completed***, AppsFlyer mengirimkan postback GDPR ke endpoint yang meminta, disertai dengan properti **status\_callback\_urls**.

Contoh status postback:

```http
POST /opengdpr_callbacks HTTP/1.1
Host: examplecontroller.com
Content-Type: application/json
X-OpenGDPR-Processor Domain: gdpr.appsflyer.com
X-OpenGDPR-Signature: kiGlog3PdQx+FQmB8wYwFC1fekbJG7Dm9WdqgmXc9uKkFRSM4uPzylLi7j083461xLZ+mUloo3tpsmyIZpt5eMfgo7ejXPh6lqB4ZgCnN6+1b6Q3NoNcn/+11UOrvmDj772wvg6uIAFzsSVSjMQxRs8LAmHqFO4cF2pbuoPuK2diHOixxLj6+t97q0nZM7u3wmgkwF9EHIo3C6G1SI04/odvyY/VdMZgj3H1fLnz+X5rc42/wU4974u3iBrKgUnv0fcB4YB+L6Q3GsMbmYzuAbe0HpVA17ud/bVoyQZAkrW2yoSy1x4Ts6XKba6pLifIHf446Bubsf5r7x1kg6Eo7B8zur666NyWOYrglkOzU4IYO8ifJFRZZXazOgk7ggn9obEd78GBc3kjKKZdwaCrLx7WV5y9TMDCf+2FILOJM/MwTUy1dLZiaFHhGdzld2AjbjK1CfVzyPssch0iQYYtbR49GhumvkYl11S4oDfu0c3t/xUCZWg0hoR3XL3B7NjcrlrQinB1KbyTNZccKR0F4Lk9fDgwTVkrAg152UqPyzXxpdzXjfkDkSEgAevXQwVJWBNf18bMIEgdH2usF/XauQoyrne7rcMIWBISPgtBPj3mhcrwscjGVsxqJva8KCVCKD/4Axmo9DISib5/7A6uczJxQG2Bcrdj++vQqK2succ=

{
"controller_id":"example controller id at the processor",
"expected_completion_time":"2018-11-01T15:00:01Z",
"status_callback_url":"https://examplecontroller.com/opengdpr_callbacks",
"Subject_request_id":"a7551968-d5d6-44b2-9831-815ac9017798",
"Request_status":"pending"
}
```

<div id="validate-postback" />

### Memvalidasi postback

**Untuk memvalidasi keaslian postback yang masuk**:

1. Buat daftar yang diizinkan untuk semua domain prosesor yang Anda izinkan untuk melakukan callback.
2. Jika nilai header untuk `X-OpenGDPR-Processor-Domain` ada di daftar yang diizinkan, ambil sertifikatnya.
   * URL sertifikat adalah nilai dari `processor_certificate` di badan respons `/discovery` .
   * Anda juga dapat mengambil sertifikat langsung dari titik akhir AppsFlyer menggunakan token API V2 sebagai token pembawa di header otorisasi: `GET https://hq1.appsflyer.com/api/gdpr/v1/certificate`
3. Validasi sertifikat menggunakan pustaka untuk mengonfirmasi bahwa sertifikat:
   1. Dikeluarkan oleh otoritas tepercaya.
   2. Dikeluarkan untuk string yang sama yang disediakan dalam nilai header `X-OpenGDPR-Processor-Domain` .
   3. Tidak kedaluwarsa.
4. Setelah Anda mengonfirmasi bahwa sertifikat valid, gunakan untuk memvalidasi header `X-OpenGDPR-Signature` terhadap badan permintaan lengkap. AppsFlyer menggunakan SHA256 RSA sebagai algoritme penandatanganan.
5. Dapatkan respons di header status:
   1. `202 Diterima` jika validasi berhasil.
   2. `401 Tidak Diotorisasi` jika tanda tangan gagal divalidasi atau domain prosesor tidak ada dalam daftar yang diizinkan.

</Accordion>

<div id="3-report-request" />

<Accordion title="3. Permintaan Laporan">

Saat **Permintaan Akses** atau **Permintaan Portabilitas** selesai, Anda dapat mengunduh laporan via HTTP GET ke titik akhir berikut:

```http
https://hq1.appsflyer.com/api/gdpr/v1/download/[REQUEST_ID]
```

Laporan yang dihasilkan akan tersedia selama empat belas hari dari waktu penyelesaian.

</Accordion>

<div id="4-discovery-requestin-process" />

<Accordion title="4. Permintaan penemuan-sedang diproses">

Untuk mempelajari format yang didukung oleh AppsFlyer, permintaan keterangan dapat dikirimkan via HTTP GET ke endpoint berikut:

```http
https://hq1.appsflyer.com/api/gdpr/v1/discovery
```

<div id="discovery-response-example" />

### Contoh Respons Keterangan

```http
HTTP/1.1 200 OK
Content-Type: application/json
{
 "api_version": "0.1",
 "supported_identities": [
 {
  "identity_type": "android_advertising_id",
  "identity_format": "raw"
 },
 ],
 "supported_subject_request_types": [
 "erasure", "access", "portability", "rectification"
 ],
 "processor_certificate": "https://exampleprocessor.com/cert.pem"
}
```

</Accordion>

<div id="5-cancellation-request" />

<Accordion title="5. Permintaan Pembatalan">

Anda dapat membatalkan permintaan GDPR, berdasarkan  `subject_request_id`, tetapi hanya selama fase ***pending*** .

Untuk melakukan itu, kirimkan HTTP DELETE dengan `subject_request_id` ke:

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

<div id="cancellation-response" />

### Respons Pembatalan

Saat permintaan pembatalan GDPR diterima, AppsFlyer akan mengembalikan respons HTTP dengan kode status 202 dan beberapa parameter lainnya.

Setelah pembatalan permintaan diproses, AppsFlyer mengirimkan postback dengan status ***dibatalkan*** .

</Accordion>

<div id="6-gdpr-requests-test-api" />

<Accordion title="6. Menguji API untuk Permintaan GDPR">

API AppsFlyer ini adalah API pengujian untuk Permintaan GDPR API AppsFlyer.

<div id="how-does-it-work" />

### Bagaimana Cara Kerja API ini?

API pengujian bekerja seperti berikut:

1. Setelah permintaan GDPR dibuat, permintaan tersebut langsung mendapat status ‘Pending’. Untuk tujuan pengujian, status berubah setiap 30 detik.

2. Jika endpoint untuk postback status telah disertakan ke dalam permintaan GDPR, postback pertama akan dikirim segera setelah permintaan dan dua postback status tambahan akan dikirim dalam interval waktu 30 detik.

**Titik Akhir Pengujian Permintaan GDPR**: POST

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub
```

**Titik Akhir Pengujian Permintaan Status**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**Titik Akhir Pengujian Permintaan Penemuan**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/discovery
```

**Titik Akhir Pengujian Permintaan Pembatalan**: DELETE

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**Titik Akhir Pengujian Sertifikat**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stubcertificate
```

**Titik Akhir Pengujian Laporan Akses/Portabilitas**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/download/:requestId
```

> 📘 **Catatan**
>
> * Token API V2 yang valid harus dimasukkan ke dalam header permintaan sebagai berikut: `'Otorisasi': 'Pembawa %AuthTokenV2% '`
> * Pada properti ‘property\_id’, ID App harus dimiliki oleh pemilik akun (berdasarkan token API).

</Accordion>

<div id="7-request-logs" />

<Accordion title="7. Permintaan log">

Pengguna admin dapat mengakses permintaan GDPR yang dikirimkan ke Dashboard Log.

Laporan permintaan akses dan portabilitas lengkap juga dapat didownload dari dashboard ini.

Untuk mengakses Log Dashboard:

1. 1.  Buka dashboard utama dan klik nama user anda.
2. Klik **Log** dan jendela berikut dibuka:

![GDPR_Table.png](https://files.readme.io/5c2b2695b5c273e16a0396f0df2d227a0a0f61af6ad0626c0a911b77edc6a0d2-13949567038481.png)

</Accordion>

<div id="8-gdpr-api-return-codes-and-error-messages" />

<Accordion title="8. Kode pengembalian API GDPR dan pesan kesalahan">

Kode pengembalian HTTP API GDPR dan pesan kesalahan dirinci dalam sesi ini.

<div id="gdpr-api-return-codes" />

#### Kode pengembalian API GDPR

| Kode pengembalian | Deskripsi |
| --- | --- |
| 201 | Dibuat |
| 202 | Permintaan pembatalan diterima |
| 400 | Bad request (permintaan bermasalah). Bodi berisi kode dan pesan kesalahan seperti yang tercantum pada tabel berikut. |

<div id="http-return-code-400---bad-request" />

### Kode pengembalian kode 400 - bad request

Pesan yang memiliki kode 400 berisi JSON dengan kode dan pesan kesalahan.

`{ "error":{ "code":400, "af_gdpr_code": "%AF error code%", "message":"%error message text%"}}`

<div id="return-code-400-bad-request-messages" />

#### Pesan kode pengembalian 400 bad request

| Kode Error | Deskripsi (pesan) kesalahan |
| --- | --- |
| e111 | Melebihi batas nilai |
| e211 | Tidak dapat membatalkan permintaan dengan status tidak valid |
| e212 | Permintaan tidak diizinkan. Penghapusan sedang berlangsung untuk identifier (pengidentifikasi). |
| e213 | Permintaan sudah ada |
| e214 | Permintaan tidak ditemukan |
| e311 | Jenis konten permintaan tidak valid |
| e312 | Versi API tidak valid |
| e313 | subject\_request\_id tidak valid |
| e314 | submitted\_time format tidak valid |
| e315 | status\_callback\_url length tidak valid |
| e316 | status\_callback\_url format tidak valid |
| e317 | app\_id format tidak valid |
| e318 | identity\_type tidak valid |
| e319 | Platform aplikasi tidak sesuai dengan jenis identitas |
| e320 | identity\_type tidak valid |
| e321 | Pengguna LAT tidak didukung via api |
| e322 | subject\_request\_type tidak valid |
| e323 | subject\_identities format tidak valid |
| e324 | subject\_identities length tidak valid |
| e325 | subject\_identities value tidak valid |
| e411 | AppID salah atau bukan milik akun Anda |
| e412 | Tidak ada hak akses untuk membatalkan permintaan penghapusan |
| e413 | Tidak ada hak akses untuk melihat permintaan |
| e511 | Masalah internal, tunggu 60 menit lalu coba lagi. Jika masalah berlanjut, hubungi tim dukungan AppsFlyer. support@AppsFlyer.com |

</Accordion>

<div id="traits-and-limitations" />

## Karakteristik dan batasan

* Batasan tarif: 80 permintaan GDPR setiap 2 menit di tingkat akun (setara dengan 2.400 permintaan per jam dan 57.600 per hari). **Permintaan yang melebihi batas ini akan gagal.**
* UI menampilkan hingga 200 permintaan yang dipilih secara acak.
* Memeriksa status permintaan lebih dari 60 hari yang lalu mengembalikan "permintaan tidak ditemukan".

<div data-zendesk-anchors="privacy-regulations=peraturan-perlindungan-privasi h_01HB866TQ0AWHQ9659Q8Q4XMQM=peraturan-perlindungan-privasi the-opendsr-initiative=inisiatif-opendsr h_01HB866TQ0R18S4GCH3KPGNJHD=inisiatif-opendsr definitions=definisi h_01HB866TQ06XV2AJDMA3M5Q5KK=definisi dsr-requirements=persyaratan-dsr h_01HB866TQ0JNEZTHQ7BR1TMD5M=persyaratan-dsr appsflyer-gdpr-requests-api=gdpr-requests-api-appsflyer h_01HB866TQ0HNFGF9QTJNT792N7=gdpr-requests-api-appsflyer h_01HB866TQ0ATDT8B000Z70MBTH=1-gdpr-request gdpr-request-flow=alur-permintaan-gdpr h_01HB866TQ0FCZGQ1DWENVSWHSG=alur-permintaan-gdpr gdpr-request-format=format-permintaan-gdpr h_01HB866TQ0GC7V1081GT53TWEZ=format-permintaan-gdpr parameters=parameter h_01HB866TQ0CFAC0X2Y98B4EE5Q=parameter subject_identities-objects=objek-subject_identities h_01HB866TQ02HMKJMKKPHHR4CMN=objek-subject_identities example-gdpr-erasure-request=contoh-permintaan-penghapusan-gdpr h_01HB866TQ1CT316PTFBJC59C79=contoh-permintaan-penghapusan-gdpr h_01HB866TQ1D7290A6G29Q4HDE7=contoh-kode-permintaan-penghapusan-gdpr h_01HB866TQ15M1897AV5W099SFV=2-status-request status-request-format=format-permintaan-status h_01HB866TQ1YEZZ4M6QMHTKCEGX=format-permintaan-status status-response-example=contoh-respons-status h_01HB866TQ1M7G7JNH0V7TEVFYY=contoh-respons-status status-postbacks=postback-status h_01HB866TQ1109WJ2J13D8FM8KX=postback-status validate-postback=memvalidasi-postback h_01HB866TQ1YG0B6JDEQ2KMFEN0=memvalidasi-postback h_01HB866TQ1TYQWZ7492H0DKWB7=3-report-request h_01HB866TQ1CH06PRJ78MHE7ZG0=4-discovery-requestin-process discovery-response-example=contoh-respons-keterangan h_01HB866TQ1AJCSS2442EEWA19X=contoh-respons-keterangan h_01HB866TQ1R8C9G4VH085897ZQ=5-cancellation-request cancellation-response=respons-pembatalan h_01HB866TQ1F72KP3S55ZJYC8Y7=respons-pembatalan h_01HB866TQ1Y35SZVFSTPG3ZJDH=6-gdpr-requests-test-api how-does-it-work=bagaimana-cara-kerja-api-ini h_01HB866TQ1KFRGX7NZCSJWVW0T=bagaimana-cara-kerja-api-ini h_01HB866TQ1W6X6NSEA6ZXAE6AG=catatan h_01HB866TQ1H8BKVGP5PFQYVBAA=7-request-logs h_01HB866TQ139BREE45W1FGTT3K=8-gdpr-api-return-codes-and-error-messages gdpr-api-return-codes=kode-pengembalian-api-gdpr h_01HB866TQ128R2TSHS4JTCQK70=kode-pengembalian-api-gdpr http-return-code-400-bad-request=kode-pengembalian-kode-400---bad-request h_01HB866TQ1A51STZQCJC5TV65X=kode-pengembalian-kode-400---bad-request return-code-400-bad-request-messages=pesan-kode-pengembalian-400-bad-request h_01HB866TQ10MAMTS9WB0CKN55V=pesan-kode-pengembalian-400-bad-request limitations=karakteristik-dan-batasan h_01HB866TQ1PXGRX5JRHRSCT0EN=karakteristik-dan-batasan" />
