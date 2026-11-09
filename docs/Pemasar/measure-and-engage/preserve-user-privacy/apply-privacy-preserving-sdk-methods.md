---
title: Pengguna ikut serta/tidak ikut serta dalam SDK AppsFlyer
metadata:
  keywords:
    - Advertisers
    - coppa
    - opt-out
    - opt out
    - consent management
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-08-20T11:14:36Z'
  edited_at: '2023-11-21T02:51:04Z'
  id: 360001422989
  locale: id
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/id/articles/360001422989
---
> **Sekilas:** Batasi atau hentikan berbagi data dengan AppsFlyer untuk mematuhi peraturan privasi seperti GDPR dan CCPA.

<Image align="center" alt="OptInOptOut_us-en.png" src="https://files.readme.io/bd2cd3e2fa3c443b9cc6a736e3c6b60834f165ad13510b829d40005740615496-360010352638.png" />

**Pertanyaan tentang privasi AppsFlyer**: Hubungan privasi antara Anda dan AppsFlyer diatur oleh <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy">Kebijakan Privasi Layanan AppsFlyer</Anchor>. Untuk pertanyaan terkait Kebijakan Privasi Layanan ini atau untuk menghubungi petugas perlindungan data kami, kirim email ke: [privacy@appsflyer.com](mailto:privacy@appsflyer.com). Untuk tujuan Pasal 27 Peraturan Perlindungan Data Umum, perwakilan AppsFlyer di UE adalah AppsFlyer Germany GmbH, Schönhauser Allee 180, 10119 Berlin, Jerman (hubungi [privacy@appsflyer.com](mailto:privacy@appsflyer.com); +49-30-166373500).

## Skenario ikut serta dan tidak ikut serta

* SDK AppsFlyer yang tersemat di aplikasi dapat diatur ke:
  * Tidak Ikut Serta: hentikan atau batasi pengumpulan data.
  * Ikut serta: setelah memilih keluar, lanjutkan pengumpulan data.
* Pengembang dan pemasar aplikasi, setelah mempertimbangkan persyaratan peraturan dan bisnis, menerapkan opt-in/opt-out seperti yang dijelaskan dalam artikel ini.
* Gunakan tidak ikut serta untuk:
  * Patuhi peraturan seperti GDPR dan CCPA yang melarang atau membatasi pengumpulan data.
  * **Tidak ikut serta sama sekali**: berhenti mengumpulkan data atribusi apa pun.
  * **Ikut serta sebagian:** mengirim beberapa data atau menganonimkan data yang dikirim.
  * **Penyisihan selektif:** berdasarkan peraturan tertentu atau usia pengguna aplikasi.
* **Gunakan opt-in:** Untuk mengalihkan opt-out ke opt-in.

## Pengguna yang tidak ikut serta

Opt-out dapat dilakukan pada beberapa tingkatan yang berbeda tergantung pada peraturan dan kebutuhan pengguna. Ikuti alur yang sesuai menggunakan skenario opt-out seperti yang dirinci. Lakukan hal ini untuk memastikan kepatuhan terhadap permintaan opt-out dan untuk terus mengumpulkan data atribusi jika diperlukan.

Dalam skenario di mana opt-out diaktifkan, ID AppsFlyer akan di-hash.

## Skenario

### Tidak ikut serta di penginstalan

**![coppa_compliant_appsflyer.png](https://files.readme.io/0f2588ad5a4e9d78df88958c6855f5e71498588e35c7a88c3b13c6ef676507f9-360002519649.png)**

**Kapan**: Saat peluncuran pertama (Contoh, <Anchor target="_blank" href="https://www.ftc.gov/enforcement/rules/rulemaking-regulatory-reform-proceedings/childrens-online-privacy-protection-rule">kepatuhan COPPA</Anchor>)

**Apa**: Aplikasi ini memerlukan persetujuan pengguna untuk melakukan pencatatan event selama semua sesi. Jika pengguna menyetujui pencatatan (misalnya, pengguna di atas usia tertentu), aplikasi akan memanggil metode `start` SDK. Jika tidak, metode `start` tidak boleh dipanggil.

> ❗️ **Perhatian**
>
> Jangan gunakan `stop` jika `start` tidak pernah dipanggil.

**Caranya**: Metode `start` harus selalu dipanggil pada awal sesi dari pengguna yang ikut serta, namun tidak boleh dipanggil untuk pengguna yang tidak ikut serta. Selain itu, in-app event tidak dapat dikirimkan kepada pengguna yang belum pernah ikut serta, karena event tersebut dianggap berasal dari pengguna yang tidak dikenal dan masuk ke organik.

Oleh karena itu, untuk aplikasi  yang mengaktifkan ***Penyisihan penginstalan***, kami merekomendasikan parameter tanda permanen yang menunjukkan jika `start` sudah dipanggil sebelumnya atau belum. Tanda ini harus SELALU diperiksa sebelum memanggil `start` atau `logEvent` .

**Data dikirim ke AppsFlyer:** Tidak ada data yang dikirim. Jika pengguna kemudian ikut serta dalam atribusi dan data sesi dikirim sejak `start` dipanggil.

> 📄 **Contoh**
>
> com.carefulapp mengharuskan pengguna untuk mendaftar saat menginstal. Formulir tersebut menyertakan kotak centang: "Saya berusia di atas 13 tahun". Pengembang menambahkan tanda yang disebut is\_tracking, yang menjadi benar hanya untuk pendaftaran yang kotaknya dicentang, lalu mengaktifkan `start`.
>
> Contoh sampel kode <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/SampleApp-Examples/blob/master/AndroidOptOutSampleApp/app/src/main/java/com/appsflyer/optoutsamples/OptInActivity.java">di sini</Anchor>

### Cegah berbagi data dengan pihak ketiga

**Kapan**: **Setiap kali SDK diinisialisasi**. 

**Apa**: Pengguna dapat meminta untuk tidak membagikan datanya dengan pihak ketiga. Dengan mengaktifkan opsi ini di AppsFlyer SDK SEBELUM panggilan `start` pertama, hal berikut ini berlaku untuk keseluruhan sesi:

* **Pengguna dari SRN** diatribusikan sebagai Organik, dan data mereka tidak dibagikan dengan mitra terintegrasi Anda.
* **Pengguna dari jaringan iklan klik** (non-SRN) diatribusikan dengan tepat di AppsFlyer, tetapi tidak dibagikan dengan jaringan iklan via postback, API, laporan data lengkap, atau dengan metode lainnya.

**Bagaimana**:

Untuk mencegah berbagi data event lewat:

* SDK (<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforpartners">iOS</Anchor>—dimulai dengan SDK V6.4+):
  * Cegah satu atau beberapa sumber media tertentu (atau semua sumber media) menerima event: Gunakan metode SDK `setSharingFilterForPartners` .
* S2S API:
  * Kirim <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_s2s_inappevent">parameter S2S sharing\_filter</Anchor>

**Data dikirim ke AppsFlyer:** Data dikirim dan disimpan di AppsFlyer, namun tidak pernah dibagikan dengan mitra terintegrasi AppsFlyer.

> 📄 **Contoh**
>
> com.to.california adalah aplikasi perjalanan untuk taman hiburan California. Agar mematuhi CCPA, jika penduduk California mengajukan permintaan untuk tidak ikut serta, aplikasi akan memberi tahu AppsFlyer untuk tidak membagikan data event pengguna dengan pihak ketiga.

### Tidak ikut serta sesi

**Kapan**: Pada setiap peluncuran aplikasi.

**Apa**: Semua sesi aplikasi memerlukan persetujuan pengguna untuk **melakukan pencatatan event dan data selama sesi.**

**Caranya**: Untuk skenario **penolakan Sesi** , panggilan SDK pertama dilakukan setelah pengguna menyetujui atau menolak pengiriman data dari perangkat mereka:

* Jika pengguna setuju untuk mengirim data, metode `start` harus dipanggil.
* Jika pengguna menolak pengiriman data, jangan panggil `start`.

**Data yang dikirim ke AppsFlyer** bergantung pada status opt-out setiap sesi sebagai berikut:

* **Sesi opt-out**: Tidak ada data yang dikirim.
* **Sesi Opt-in**: Semua data sesi dikirim. **Catatan:** Data atribusi dikirim saat pertama kali pengguna ikut serta.

> 📄 **Contoh**
>
> com.adultsplay adalah aplikasi game kasual untuk orang dewasa berumur lebih dari 18 tahun. Aplikasi ini tidak mengharuskan pengguna untuk mendaftar, tetapi membutuhkan konfirmasi usia dengan setiap peluncuran baru. Sesi, saat pengguna mengonfirmasi bahwa mereka berusia di atas 18 tahun, mendapatkan pengalaman bermain game yang lengkap dan direkam, sementara jika tidak, tidak ada perekaman yang dilakukan.
>
> Pengembang menambahkan flag yang disebut is\_tracking, yang berlaku hanya untuk sesi yang mengonfirmasi usia 18 tahun. Jika tanda ini benar, metode `start` akan dipanggil. Jika tidak, `start` tidak dipanggil.

### Opt-out satu kali

<Image align="center" alt="OpenGDPR-logo-BLK.png" src="https://files.readme.io/87560c35c45bf34d8eb7ede3e6bbf90fb4391ab41c7f3186e33a93d8f4f68a6e-360002512925.png" />

**Kapan**: Kapan saja (GDPR)

**Apa**: Pemilik aplikasi mengumpulkan data atribusi dan setelah penginstalan. **Pengguna meminta untuk menghentikan pengumpulan data lebih lanjut**, misalnya, sesuai dengan permintaan <Anchor target="_blank" href="/marketers/id/docs/send-opendsr-api-requests">GDPR</Anchor> .

**Caranya**: Jangan panggil `start`, lalu langsung panggil `stop`!

Sebagai gantinya, pada peluncuran pertama gunakan metode `start` dengan ***requestListener***. Setelah berhasil diselesaikan, dalam fungsi panggilan balik, panggil `stop`.

Pada semua sesi berikut, jangan panggil `start`.

**Data dikirim ke AppsFlyer:** Data instalasi dan sesi dikirim ke AppsFlyer. Tidak ada data yang dikirim ke AppsFlyer setelah metode *`stop`* dipanggil.

> 📄 **Contoh**
>
> com.watchmegrow adalah aplikasi melihat pertumbuhan tanaman, di mana pengguna menonton pertumbuhan tanaman dan iklan seluler. Pemilik aplikasi ingin merahasiakan semua data aktivitas dalam aplikasi.
>
> Pada peluncuran pertama, Pengembang memanggil metode `start` dengan ***requestListener***. Saat menerima penyelesaian yang berhasil, memanggil `stop` dari fungsi panggilan balik dan menyetel parameter persisten ***is\_first\_launch*** ke salah. Pada peluncuran berikutnya, Pengembang memeriksa apakah ***is\_first\_launch*** salah, lalu melewati `start`.
>
> Contoh kode sampel <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/SampleApp-Examples/blob/master/AndroidOptOutSampleApp/app/src/main/java/com/appsflyer/optoutsamples/TrackAndOptOut.java">di sini</Anchor>

### Rekam penginstalan dan anonimkan

**Kapan**: Setelah peluncuran pertama

**Apa**: Pemilik aplikasi ingin mengumpulkan semua data atribusi, lalu ingin mengumpulkan semua informasi selanjutnya, seperti data event atau sesi dalam aplikasi, sebagai data **organik tanpa atribusi** . Setelah instalasi, semua ID perangkat dianonimkan saat dikirim ke AppsFlyer dari SDK.

**Caranya**: Jangan panggil `start`, lalu langsung panggil `stop`!

Sebagai gantinya, pada peluncuran pertama gunakan metode `start` dengan ***requestListener***. Setelah berhasil diselesaikan, dalam panggilan fungsi panggilan balik, panggil `anonymizeUser(true)`.

**Data dikirimkan ke AppsFlyer:**

* **Saat diinstal:** Data atribusi lengkap dikirim ke AppsFlyer.
* **Setelah instalasi**: Data in-app event dan data sesi dikirim ke AppsFlyer tanpa data atribusi. Setelah diterima, pengidentifikasi pengguna dianonimkan dan ID AppsFlyer serta alamat IP di-hash. Gambar berikut menunjukkan contoh data yang dianonimkan dan di-hash. [![DataSample_anonymized.png](https://files.readme.io/71af1933aee76c2f7a77d24d941ef1976a15f35821448d50eb97db684ed9723c-360018851737.png)](https://files.readme.io/71af1933aee76c2f7a77d24d941ef1976a15f35821448d50eb97db684ed9723c-360018851737.png)

> 📄 **Contoh**
>
> Pemilik aplikasi com.munistic percaya bahwa semua pengguna dilahirkan sama dan lebih memilih untuk melihat semua tindakan setelah penginstalan mereka sebagai organik saja.
>
> Pada peluncuran pertama, Pengembang memanggil metode `start` dengan ***requestListener***. Saat menerima penyelesaian yang berhasil, panggil `anonymizeUser(true)` dari fungsi panggilan balik.

## Tidak ikut serta dalam kampanye penargetan ulang

Pertimbangkan untuk mengecualikan pengguna yang memilih tidak ikut serta dalam kampanye penargetan ulang. Pengguna ini cenderung mengeluh tentang penargetan ulang setelah memilih tidak ikut serta.

Saat menjalankan kampanye penargetan ulang secara manual, yang ditargetkan pada pengguna aktif, pastikan untuk menghapus pengguna yang memilih tidak ikut serta dari daftar yang dikirim ke daftar sumber media.

Sebagai alternatif, jika Anda menggunakan **Audiens AppsFlyer**, untuk membuat daftar audiens Anda dan mengirimkannya ke sumber media, pengguna yang tidak ikut serta akan dikecualikan dari daftar yang dikirim ke sumber media.

`<span id="stop-api-and-deep-linking"></span>stop` API dan tautan langsung

Penggunaan API `stop` akan menghentikan semua komunikasi eksternal oleh SDK AppsFlyer yang tertanam dalam aplikasi.

Oleh karena itu, setelah memanggil `stop`, tautan yang diperpendek tidak lagi didekodekan oleh SDK AppsFlyer. Artinya, tautan yang diperpendek tidak menghasilkan panggilan ke ***onAppOpenAttribution***, dan tautan langsung tidak dilakukan dengan benar.

Jika aplikasi Anda memiliki persentase pengguna yang tidak ikut serta yang relatif tinggi dan Anda merencanakan beberapa kampanye penargetan ulang untuk pengguna Anda, gunakan tautan panjang, dan hindari penggunaan tautan yang dipendekkan.

## Mulai ulang fungsi SDK

Ketika pengguna yang memilih untuk tidak ikut serta setuju untuk ikut serta, panggil metode `start` untuk memulai ulang SDK dan mulai mencatat data atribusi.

## SDK mode ketat (khusus iOS)

Terkadang pengembang lebih memilih untuk mengirimkan aplikasi mereka tanpa referensi apa pun ke kerangka AdSupport dan kumpulan IDFA dalam kode mereka. Dalam kasus seperti itu, gunakan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">SDK mode ketat</Anchor>.

<div data-zendesk-anchors="optin-and-optout-scenarios=skenario-ikut-serta-dan-tidak-ikut-serta h_01HFPME3VYC6G1CA3WD73JJD46=skenario-ikut-serta-dan-tidak-ikut-serta optingout-users=pengguna-yang-tidak-ikut-serta h_01HFPME3VYV81QKGT188CCR7QV=pengguna-yang-tidak-ikut-serta scenarios=skenario h_01HFPME3VYP4P1Q440QW2PN32P=skenario optout-at-installation=tidak-ikut-serta-di-penginstalan h_01HFPME3VY7JQY4Z71VT60NVVR=tidak-ikut-serta-di-penginstalan h_01HFPME3VYASX24WYXJSZVGPMY=perhatian h_01HFPME3VZ8FSNA9BR3DHMX408=contoh prevent-data-sharing-with-third-parties=cegah-berbagi-data-dengan-pihak-ketiga h_01HFPME3VZXRT3MN6SSQNVPYQH=cegah-berbagi-data-dengan-pihak-ketiga h_01HFPME3VZ7NGAFF8F7W77GJZZ=contoh-1 session-optout=tidak-ikut-serta-sesi h_01HFPME3VZKVV8G0C678X4N3BF=tidak-ikut-serta-sesi h_01HFPME3VZHBNZARMA5D75H2AF=contoh-2 onetime-optout=opt-out-satu-kali h_01HFPME3VZSKDBHBF6Q2573BVP=opt-out-satu-kali h_01HFPME3VZ1W6G78FH2XGZYDQZ=contoh-3 record-install-and-anonymize=rekam-penginstalan-dan-anonimkan h_01HFPME3VZ6RFCJ6VPREVZ93Q1=rekam-penginstalan-dan-anonimkan h_01HFPME3VZZRF8ERES0693D3DE=contoh-4 optingout-of-retargeting-campaigns=tidak-ikut-serta-dalam-kampanye-penargetan-ulang h_01HFPME3VZYKB97AG3T5BX9NG6=tidak-ikut-serta-dalam-kampanye-penargetan-ulang h_01HFPME3VZ21D3W8RRBQHG0905=stop-api-and-deep-linking restarting-the-sdk-function=mulai-ulang-fungsi-sdk h_01HFPME3VZBWJXCAM7XZ3C5Y7E=mulai-ulang-fungsi-sdk strict-mode-sdk-ios-only=sdk-mode-ketat-khusus-ios h_01HFPME3VZFC8A3Y48HS1KEFF5=sdk-mode-ketat-khusus-ios" />
