---
title: Data Locker—pengaturan layanan cloud
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2021-02-10T17:35:25Z'
  edited_at: '2023-11-02T11:42:28Z'
  id: 360017603577
  locale: id
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/id/articles/360017603577
---
> **Sekilas**: Siapkan layanan cloud Anda untuk menerima data dari Data Locker: GCS, AWS, BigQuery, atau Snowflake.

Data Locker memungkinkan Anda untuk mengalirkan data ke solusi penyimpanan yang Anda pilih dan miliki, baik itu bucket atau gudang data. Atur layanan cloud Anda menggunakan salah satu prosedur berikut.

<div id="bucket-cloud-storage" />

## Penyimpanan cloud bucket

<div id="gcs-storage" />

<Accordion title="Penyimpanan GCS">

* Prosedur di bagian ini harus dilakukan oleh admin Google Cloud Anda.
* Anda dapat menghapus file dari Data Locker 25 jam atau lebih setelah ditulis. Jangan hapus mereka sebelumnya.

**Informasi untuk admin GCS**

Data Locker adalah solusi AppsFlyer untuk streaming data ke penyimpanan.

**Persyaratan**

* Buat bucket di GCS untuk penggunaan Data Locker secara eksklusif. Eksklusif berarti tidak ada layanan lain yang menulis data ke bucket.
* Nama bucket yang disarankan: `af-datalocker`.
* Berikan izin Data Locker menggunakan prosedur berikut.

**Untuk memberikan izin Data Locker:**

Dalam prosedur ini, gantikan `data-locker-example` menggunakan nama bucket yang sebelumnya Anda buat untuk Data Locker.

1. Masuk ke konsol GCS Anda.
2. Buka **Penyimpanan** > **Peramban** **penyimpanan**.  

   [![mceclip0.png](https://files.readme.io/933df60c2073a7eba97429f3cf95967ae04513a50a14e8c22ec9ee0a94f480d7-360016875898.png)](https://files.readme.io/933df60c2073a7eba97429f3cf95967ae04513a50a14e8c22ec9ee0a94f480d7-360016875898.png)
3. Pilih bucket yang sebelumnya Anda buat, misalnya `data-locker-example`.
4. Buka tab **Permission (Izin)**.
5. Klik **+Tambah**.  
   Jendela Tambahkan anggota terbuka.
6. Selesaikan sebagai berikut:
   1. **Anggota baru**, tempel cuplikan berikut.

      ```http
      af-data-delivery@af-raw-data.iam.gserviceaccount.com
      ```
   2. **Pilih peran**: **Penyimpanan cloud** > **Admin Objek Penyimpanan**.   

      [![mceclip0.png](https://files.readme.io/925501e1f16f4276d4a7aa0be8a78c94057fbdf07d48929e55bafe489f01cd42-360017059798.png)](https://files.readme.io/925501e1f16f4276d4a7aa0be8a78c94057fbdf07d48929e55bafe489f01cd42-360017059798.png)
7. Klik **Simpan**.

</Accordion>

<div id="aws-storage" />

<Accordion title="Penyimpanan AWS">

* Prosedur di bagian ini harus dilakukan oleh admin AWS Anda.
* Anda dapat menghapus file dari Data Locker 25 jam atau lebih setelah ditulis. Mohon jangan hapus sebelum.

**Informasi untuk Admin AWS**

Data Locker adalah solusi AppsFlyer untuk streaming data ke penyimpanan.

**Persyaratan**

* Buat keranjang AWS dengan nama af-datalocker-mybucket. Awalan af-datalocker- adalah wajib. Akhirannya adalah teks bebas (free text).
* Kami menyarankan af-datalocker-yyyy-mm-dd-hh-mm-free-text. Di mana yyyy-mm-dd-hh-mm adalah tanggal dan waktu saat ini, dan Anda menambahkan teks lain yang Anda inginkan seperti yang ditunjukkan dalam gambar berikut.

**Antarmuka pengguna dalam konsol AWS**

![MyBucket.jpg](https://files.readme.io/b8a16d185279200026388e146cfb3eb03ae3c7737ac26da3aa0d116a0cf9c078-4403551836305.jpg)

Setelah membuat bucket, beri izin kepada AppsFlyer untuk menggunakan prosedur berikut.

**Untuk membuat bucket dan memberikan izin kepada AppsFlyer:**

1. Login ke konsol AWS.
2. Buka layanan S3.
3. **Untuk membuat bucket**:
   1. Klik **Buat bucket**.
   2. Lengkapi **Nama bucket** sebagai berikut: Mulai dari `af-datalocker-` lalu kemudian tambahkan teks lain seperti yang dijelaskan sebelumnya.
   3. Klik **Create bucket** (Buat bucket).
4. **Untuk memberikan izin kepada AppsFlyer:**
   1. Pilih bucket.
   2. Buka tab **Permission (Izin)**.
   3. Di bagian **Bucket policy (Kebijakan bucket)**, klik **Edit**.   
      Jendela kebijakan Bucket terbuka.
   4. Rekatkan potongan kode berikut ke jendela.

      ```json
      {
        "Version": "2012-10-17",
        "Statement": [
          {
            "Sid": "AF_DataLocker_Direct",
            "Effect": "Allow",
            "Principal": {
              "AWS": "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
            },
            "Tindakan": [
              "s3:GetObject",
              "s3:ListBucket",
              "s3:DeleteObject",
              "s3:PutObject"
            ],
            "Sumber Daya": [
          "arn:aws:s3:::af-datalocker-my-bucket",
          "arn:aws:s3:::af-datalocker-my-bucket/*"
         ]
          }
        ]
      }
      ```
5. Di potongan kode tersebut, ganti `af-data-locker-my-bucket` dengan nama bucket yang Anda buat.
6. [Opsional] Tambahkan dukungan untuk bucket terenkripsi KMS. Untuk melakukannya, di bagian **Kebijakan Kunci** , pilih **Beralih ke tampilan kebijakan** dan rekatkan cuplikan berikut di **array Pernyataan.**

   ```json
   {
         "Sid": "Izinkan penggunaan kunci",
      "Efek": "Izinkan",
         "Utama": {
             "AWS": "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
         },
      "Tindakan": "kms:GenerateDataKey*",
         "Sumber Daya": "*"
     }
   ```
7. Klik **Save changes** (Simpan perubahan).
8. Selesaikan <Anchor target="_blank" href="/marketers/id/docs/data-locker-for-marketers#set-up-data-locker">Prosedur Pengaturan Data Locker.</Anchor>

</Accordion>

<div id="beta--azure-storage" />

<Accordion title="[Beta] Penyimpanan Azure">

* Prosedur di bagian ini harus dilakukan oleh admin Azure Cloud Anda.
* Anda dapat menghapus file dari Data Locker 25 jam atau lebih setelah ditulis. Jangan hapus mereka sebelumnya.

**Informasi untuk admin Azure**

Data Locker merupakan solusi AppsFlyer untuk streaming data ke akun penyimpanan Anda.

**Untuk menentukan akun penyimpanan untuk Data Locker:**

1. Buka [akun penyimpanan Azure](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Storage%2FStorageAccounts)
2. Buat akun penyimpanan baru untuk mendapatkan Data Appsflyer Anda
3. Opsional: Buat grup sumber daya baru (jika tidak ada grup sumber daya)
4. Pilih langganan, Beri nama akun penyimpanan baru Anda, dan pilih wilayah yang relevan
5. Aktifkan namespace hierarki
6. Hubungi CSM Anda untuk mengaktifkan Azure di Data Locker (setelah diaktifkan, Anda memerlukan nama akun penyimpanan di atas dan kuncinya untuk memasukkan wizard koneksi baru di Data Locker)

</Accordion>

<div id="yandex" />

<Accordion title="[Beta] Penyimpanan Yandex Cloud">

* Prosedur di bagian ini harus dilakukan oleh admin Yandex Cloud Anda.
* Anda dapat menghapus file dari Data Locker 25 jam atau lebih setelah ditulis. Jangan hapus mereka sebelumnya.

**Informasi untuk admin Yandex**

Data Locker adalah solusi AppsFlyer untuk streaming data ke penyimpanan.

**Untuk membuat keranjang dan memberikan izin Data Locker:**

1. Di <Anchor target="_blank" href="https://console.cloud.yandex.com/">konsol Yandex CloudAnda</Anchor>, buka tab **Akun Layanan** dan klik **Buat akun layanan**.
2. Beri nama akun layanan, misalnya, `af-datalocker`.
3. Buat kunci akses statis untuk akun layanan. Di akun layanan:
   1. Klik **Buat kunci baru**.
   2. Pilih **Buat kunci akses statis**.
   3. Simpan **ID Kunci** dan **Kunci Rahasia**.
4. Berikan **storage.editor** akun layanan baru Anda izin.
   1. Di pengaturan bucket Anda, buka **Akses Bindings** dan klik **Tetapkan bindings**.
   2. Untuk akun layanan baru Anda, tambahkan peran **storage.editor** dan klik **Simpan**.
5. Hubungi CSM AppsFlyer Anda untuk mengaktifkan Yandex di Data Locker.
6. Setelah diaktifkan, gunakan ID kunci dan kunci rahasia selama <Anchor target="_blank" href="/marketers/id/docs/data-locker-for-marketers#set-up-data-locker">pengaturan Data Locker</Anchor>.

</Accordion>

<div id="data-warehouse-cloud-storage" />

## Penyimpanan cloud gudang data

<div id="bigquery" />

<Accordion title="BigQuery">

Prosedur di bagian ini harus dilakukan oleh admin BigQuery Anda.

**Informasi untuk Admin BigQuery**

Data Locker adalah solusi AppsFlyer untuk streaming data ke penyimpanan.

**Persyaratan**

* <span id="step-1-create-a-bigquery-dataset"></span>Buat set data BigQuery

**Untuk membuat set data BigQuery:**

1. Di BigQuery, buat proyek atau gunakan proyek yang sudah ada.
2. Di proyek, klik **BUAT SET DATA**.

   [![GCSCreateDataSEt_1_.png](https://files.readme.io/702b81dcff4185ce98ad82afd0a9b545f99ef49e3f6292709f3b00330821472c-4405548469521.png)](https://files.readme.io/702b81dcff4185ce98ad82afd0a9b545f99ef49e3f6292709f3b00330821472c-4405548469521.png)
3. Berikan ID yang sesuai untuk set data.
4. Beri AppsFlyer akses ke set data. <Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/control-access-to-resources-iam#grant_access_to_a_resource">Lihat petunjuk Big Query</Anchor>
   * Untuk **Tambahkan principal**, gunakan pengguna AppsFlyer berikut: [datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com](mailto:datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com)
   * Untuk **Tetapkan peran**, pilih BigQuery Data Editor.
5. Selesaikan pengaturan yang tersisa sesuai kebutuhan.

</Accordion>

<div id="snowflake" />

<Accordion title="Snowflake">

Hubungkan Data Locker ke akun Snowflake Anda. Dengan melakukannya, data dikirim ke Snowflake dan terus tersedia di penyimpanan cloud pilihan Anda.

**Pertimbangan untuk pengembang BI**

* Tingkat keaktualan data sama dengan data yang disediakan dalam bucket.
* Struktur tabel dan kolom data setara dengan yang ditemukan di data yang tersedia langsung dari bucket Data Locker.
* Saat baris ditambahkan ke bagian Snowflake, kolom `_ingestion_time` diisi. Untuk memastikan keunikan baris dan untuk mencegah penyerapan baris yang sama lebih dari sekali:
  1. Simpan `max_ingestion_time` per tabel yang diserap.
  2. Setiap kali Anda menjalankan proses penyerapan, hanya serap baris dengan `_ingestion_time > max_ingestion_time`

Selesaikan prosedur berikut untuk menyambungkan Snowflake ke Data Locker.

<div id="snowflake-connector-procedures" />

#### **Prosedur konektor Snowflake**

**Untuk mendapatkan ID akun dan wilayah Snowflake Anda**:

1. Di Snowflake, <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">masuk ke akun Snowflake Anda</Anchor>.
2. Di bilah menu, pilih nama Anda.  
   ID akun dan wilayah Anda ditampilkan.  

   [![SnowflakeAccountId.png](https://files.readme.io/146dc699865a8a72780ba409d37ca1206767943e27221bec635b9fb49ffc7223-4412207884433.png)](https://files.readme.io/146dc699865a8a72780ba409d37ca1206767943e27221bec635b9fb49ffc7223-4412207884433.png)

**Untuk menyambungkan Data Locker ke Snowflake**:

1. Di AppsFlyer, buka **Integrasi**> **Data Locker**.
2. Pilih Snowflake.
3. Masukkan **wilayah Snowflake** dan **ID akun Snowflake** menggunakan informasi yang Anda dapatkan sebelumnya dari Snowflake.
4. Klik **Save**.

**Untuk** **membuat database dari berbagi di Snowflake**:

1. Di Snowflake, <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">masuk ke akun Snowflake Anda</Anchor>.
2. Beralih peran ke **Accountadmin**. Lihat <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/data-share-consumers.html#creating-a-database-from-a-share.">Membuat database dari share.</Anchor>
3. Pilih **Bagikan**.
4. Pilih berbagi AppsFlyer. Contohnya, APPSFLYER\_ACC\_XXX\_DATA\_LOCKER.
5. Klik **Buat Database dari Berbagi yang Aman**, dan lengkapi detail yang diperlukan. **Perhatikan**! Anda harus memuat data dari database bersama ke dalam tabel Anda, karena data dalam database bersama hanya tersedia untuk jangka waktu terbatas (saat ini 14 hari).
6. Di database Anda, tabel yang diimpor ditampilkan. Nama dan struktur tabel setara dengan yang ada di bucket Data Locker.

</Accordion>

<div data-zendesk-anchors="bucket-cloud-storage=penyimpanan-cloud-bucket h_01HE2SPKYZWFXA63YD5NK4KJRD=penyimpanan-cloud-bucket h_01HE2SPKYZM9QQCGFN86J7FNDY=gcs-storage h_01HE2SPKYZK4F9E22MG3K8SJE8=aws-storage %5Bbeta%5D-azure-storage=beta--azure-storage h_01HE2SRAJA94R8ZKHRBEFNKX8D=beta--azure-storage h_01HE2SPKYZXAXMKPH5DQV40X1W=yandex data-warehouse-cloud-storage=penyimpanan-cloud-gudang-data h_01HE2SPKYZ77X8WP9ZNRB1D05B=penyimpanan-cloud-gudang-data h_01HE2SPKYZMNW776CZRZAFVV5H=bigquery step-1%E2%80%94create-a-bigquery-dataset=step-1-create-a-bigquery-dataset h_01HE2SPKYZC3W4G3YXFM10H9D3=snowflake snowflake-connector-procedures=prosedur-konektor-snowflake h_01HE2SPKYZ11B1MJYX2HRCS07D=prosedur-konektor-snowflake" />
