---
title: Ekstensi Adobe Launch SDK
metadata:
  keywords:
    - SDK
    - Adobe
    - Advertisers
    - AppsFlyer SDK
    - Adobe Experience Platform
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
  created_at: '2019-02-13T08:03:45Z'
  edited_at: '2024-03-05T14:48:17Z'
  id: 360000939097
  locale: id
  section: Other platforms
  section_id: 6551244207121
  url: https://support.appsflyer.com/hc/id/articles/360000939097
---
> **Sekilas:** Kirim data ke Adobe Launch SDK dan AppsFlyer SDK dengan implementasi tunggal Ekstensi AppsFlyer Adobe Launch SDK.

## Ringkasan

Adobe Launch SDK merupakan bagian integral dari Adobe Experience Platform. Adobe Experience Platform membantu bisnis mengumpulkan, mengonsolidasikan, dan menganalisis data dari berbagai aplikasi dan platform. Hal ini memungkinkan pemilik bisnis dan pengembang untuk lebih memahami perilaku pelanggan untuk mengoptimalkan pengalaman dan pengiriman konten. Jika aplikasi Anda mengimplementasikan Adobe Launch SDK dan AppsFlyer SDK, Anda dapat mengirim data ke keduanya dengan satu implementasi dari **Ekstensi AppsFlyer Adobe Launch SDK**. Hal ini mengurangi kompleksitas keseluruhan proses pengembangan Anda dan membuat basis kode lebih bersih dan mudah dipelihara.

> 📘 **Catatan**
>
> Jika Anda menggunakan ekstensi Adobe Launch, Anda tidak memerlukan <Anchor target="_blank" href="/marketers/id/docs/adobe-analytics-integration-with-appsflyer">integrasi Adobe Analytics</Anchor> standar.

## Prasyarat

Beberapa hal diperlukan sebelum mengintegrasikan Ekstensi AppsFlyer Adobe SDK.

<div id="get-your-appsflyer-dev-key" />

<Accordion title="Dapatkan kunci pengembang AppsFlyer Anda">

<Image alt="dev_key.png" src="https://files.readme.io/bf25b5d583f3eaab57c230b68764f08c49806a50401955a511993d8a847e7d42-360006050318.png" width="357px" />

1. Di dashboard aplikasi Anda, klik ***Pengaturan Aplikasi*** di bawah ***Konfigurasi*** di menu sebelah kiri.
2. Di bawah ***Instalasi SDK***, salin bagian ***Kunci Pengembang (Dev Key)***.

</Accordion>

<div id="get-your-app-id" />

<Accordion title="Dapatkan ID aplikasi Anda">

* Untuk Android - ID aplikasi adalah nama paket, misalnya example.com.app.
* Untuk iOS - ID aplikasi adalah ID iTunes aplikasi tanpa awalan *id*, misalnya 123456748.

</Accordion>

## Langkah 1: Melakukan konfigurasi Adobe Launch

Ikuti petunjuk di sini untuk mengonfigurasi Adobe Launch.

<div id="11-creating-a-new-property-in-adobe-launch" />

<Accordion title="1.1 Membuat properti baru di Adobe Launch">

[![](https://files.readme.io/d03e61047c536785e7601d4f0efbd9b6488bd41c92efdd6e0d1021b42a5bec3a-small-360005983477.png)](https://files.readme.io/d03e61047c536785e7601d4f0efbd9b6488bd41c92efdd6e0d1021b42a5bec3a-small-360005983477.png)

1. Masuk ke Adobe Experience Cloud.
2. Pilih ***Launch***.
3. Klik ***Buka Launch***.
4. Klik ***Properti Baru***.
5. Beri nama properti dan pilih ***Seluler***.
6. Klik ***Simpan (Save)***.

</Accordion>

<div id="12-installing-required-adobe-launch-extensions" />

<Accordion title="1.2 Menginstal ekstensi Adobe Launch yang diperlukan">

Instal ekstensi berikut di Adobe Launch:

[![adboe_extensions.png](https://files.readme.io/bf0c0652c3807d4da0819a62b600ac875af1f8764387a36cc3f256a58e1ea852-360005983597.png)](https://files.readme.io/bf0c0652c3807d4da0819a62b600ac875af1f8764387a36cc3f256a58e1ea852-360005983597.png)

* Adobe Analytics - menghubungkan data yang dicatat dari SDK ke modul Adobe Analytics.
* Ekstensi AppsFlyer SDK - mengirimkan data dan event ke Adobe dan AppsFlyer menggunakan Adobe Launch SDK.
* Profil Adobe - memungkinkan SDK untuk menyimpan data ke dalam profil sisi klien.
* Adobe Mobile Core - memungkinkan konfigurasi SDK seluler dan menyediakan akses ke event dan kondisi siklus hidup default.

#### Menginstal ekstensi Adobe Analytics

1. Masuk ke Adobe Analytics.
2. <Anchor target="_blank" href="https://docs.adobe.com/help/en/analytics/admin/admin-console/create-report-suite.html">Membuat rangkaian laporan</Anchor>.
3. Masuk kembali ke Adobe Launch.
4. Dari daftar properti, klik pada properti yang telah Anda buat sebelumnya.
5. Klik ***Ekstensi***.
6. Mencari dan menginstal ***Adobe Analytics***.
7. Di bawah ***Rangkaian Laporan***, tentukan rangkaian laporan yang telah Anda buat di langkah 2.
8. Klik ***Simpan (Save)***.

#### Menginstal Ekstensi AppsFlyer SDK

1. Pilih ***Ekstensi*** lagi.
2. Mencari dan menginstal ***Ekstensi AppsFlyer SDK***.
3. Di bawah ***ID Aplikasi iOS Appsflyer***, tentukan ID aplikasi iOS yang Anda dapatkan di langkah prasyarat.
4. Di bawah ***Kunci Pengembang AppsFlyer*** tentukan kunci pengembang yang Anda dapatkan di langkah prasyarat.
5. Aktifkan ***Mengirim data atribusi ke Adobe Analytics***. Perhatikan bahwa ada beberapa <Anchor target="_blank" href="/marketers/id/docs/user-level-data-retention">pembatasan dalam membagikan data tingkat pengguna dengan platform analitik pihak ketiga</Anchor>.
6. Klik ***Simpan (Save)***.

#### Instal Profil dan ekstensi Mobile Core

1. Pilih ***Ekstensi*** lagi.
2. Mencari dan menginstal ***Profil***.
3. Mencari dan menginstal ***Mobile Core***.
   * Saat menginstal Mobile Core, cukup simpan ekstensi apa adanya. Tidak perlu menentukan ***Experience Server Cloud***.

</Accordion>

## Langkah 2: Menerapkan Ekstensi AppsFlyer Adobe SDK

Ikuti petunjuk di bagian ini untuk mengimplementasikan Ekstensi Adobe SDK ke dalam aplikasi Anda.

<div id="21-adding-the-sdk-to-the-app" />

<Accordion title="2.1 Menambahkan SDK ke aplikasi">

[![adobe_sdk.png](https://files.readme.io/076e6cc5911a0a515e5510a8da233bcefcb4144c92cf49190416b593fcdecc8f-small-360006050518.png)](https://files.readme.io/076e6cc5911a0a515e5510a8da233bcefcb4144c92cf49190416b593fcdecc8f-small-360006050518.png)

1. Di dalam properti Adobe Anda, pilih ***Lingkungan (Environments)***.
2. Pilih lingkungan tempat Anda ingin menerapkan SDK.
3. Di sisi kanan, klik ikon kotak.
4. Salin potongan kode dari jendela yang terbuka dan ikuti petunjuknya. Jika Anda adalah pemasar yang melakukan konfigurasi Adobe, kirim cuplikan kode ini ke pengembang aplikasi Anda.

</Accordion>

<div id="22-publishing-the-environment" />

<Accordion title="2.2 Memublikasikan lingkungan (environment)">

Untuk menyelesaikan implementasi SDK, Anda perlu memublikasikan lingkungan pada library.

[![adobe_publishing.png](https://files.readme.io/4e9ad08fce291ef59e7a3567726c678754ae3a3c96de75f4ae27cd80a84945d1-small-360006050558.png)](https://files.readme.io/4e9ad08fce291ef59e7a3567726c678754ae3a3c96de75f4ae27cd80a84945d1-small-360006050558.png)

1. Di dalam properti Adobe Anda, pilih ***Penerbitan (Publishing)***.
2. Klik ***Tambah Library Baru***.
3. Beri nama dan di bawah Lingkungan, pilih ***Pengembangan (Development)***.
4. Klik ***Simpan & Bangun untuk Pengembangan***.
5. Setelah pembangunan selesai, di bawah ***Pengembangan***, klik tiga titik di samping library dan pilih ***Kirim untuk Persetujuan***.
6. Di bawah ***Dikirimkan***, klik tiga titik di samping library dan pilih ***Bangun untuk Staging***.
7. Setelah pembangunan selesai, klik tiga titik di samping library dan pilih ***Setujui untuk Penerbitan***.
8. Di bawah ***Menyetujui***, klik tiga titik di samping library dan pilih ***Bangun & Terbitkan ke Produksi***.

</Accordion>

<div id="23-adding-android-install-referrer-to-your-app" />

<Accordion title="2.3 Menambahkan pengarah instal (install referrer) Android ke aplikasi Anda">

Pengarah Instal Android meningkatkan keakuratan atribusi, melindungi dari kecurangan penginstalan, dan banyak lagi. Ini didukung dari AppsFlyer Android SDK versi 4.8.6.

> 📘 **Catatan**
>
> Google menghentikan[BroadcastReceiver](https://android-developers.googleblog.com/2019/11/still-using-installbroadcast-switch-to.html) pada Maret 2020.
>
> * Perubahan ini tidak berdampak pada aplikasi.
> * Anda mungkin masih memerlukan BroadcastReceiver untuk atribusi di luar play store. Periksa dengan play store di mana aplikasi terdaftar untuk memastikan.
> * Mengimplementasikan install referrer (pengarah instal) sekarang diwajibkan.

Ada dua cara untuk menambahkan pengarah instal ke aplikasi Anda:

* Menggunakan Gradle (disarankan)
* Menambahkan pengarah instal secara manual

<Tabs>
<Tab title="Menambahkan pengarah instal menggunakan Gradle">

Tambahkan Pengarah Instal Android sebagai dependensi. Anda dapat menemukan versi terbaru <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.android.installreferrer/installreferrer/1.0">di sini</Anchor>.

1.
   ```java
   dependencies {
   //make sure to use the latest SDK version: https://mvnrepository.com/artifact/com.appsflyer/af-android-sdk
   	implementation 'com.appsflyer:af-android-sdk:5.+'
   	implementation 'com.android.installreferrer:installreferrer:1.1'
   }
   ```
2. Sinkronkan proyek untuk memunculkan dependensi kembali - lihat tangkapan layar berikut:  

    [![android_af_sdk_sync_gradle.png](https://files.readme.io/f8835cf76d51d7ddeb51206707d95b7214e398c5960299893118ad57ccffe890-22939234622609.png)](https://files.readme.io/f8835cf76d51d7ddeb51206707d95b7214e398c5960299893118ad57ccffe890-22939234622609.png)

Jika Anda menggunakan ProGuard dan ingin menggunakan pengarah API baru dari Google, tetapkan aturan ProGuard berikut ini: `-dontwarn com.android.installreferrer`

</Tab>

<Tab title="Menambahkan pengarah instal secara manual">

1. <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.android.installreferrer/installreferrer/1.0">Unduh Install Referrer aar</Anchor>
2. <Anchor target="_blank" href="https://stackoverflow.com/questions/16682847/how-to-manually-include-external-aar-package-using-new-gradle-android-build-syst">Tambahkan ke proyek</Anchor>
3. Tambahkan hak akses berikut ke manifes: `com.google.android.finsky.permission.BIND_GET_INSTALL_REFERRER_SERVICE`

</Tab>
</Tabs>

</Accordion>

<div id="24-setting-required-permissions" />

<Accordion title="2.4 Mengatur hak akses yang diperlukan">

Menambahkan hak akses membantu meningkatkan tingkat <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#probabilistic-modeling">Atribusi pemodelan probabilistik</Anchor>. Hal ini juga memungkinkan SDK untuk mengirimkan lebih banyak data seperti Wifi dan data jaringan operator. Anda dapat menemukan data ini di <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">laporan data lengkap</Anchor> dan menggunakannya untuk analisis dan pengoptimalan kampanye.

#### Tambahkan Hak Akses yang Diperlukan

1. Tambahkan hak akses berikut ke AndroidManifest.xml:  

   ```html Markup
   <uses-permission android:name="android.permission.INTERNET" />
   <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
   <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
   <!-- Optional : -->
   <uses-permission android:name="android.permission.READ_PHONE_STATE" />
   ```

</Accordion>

## Menggunakan ekstensi Adobe SDK

Sekarang Anda dapat mulai menggunakan ekstensi Adobe SDK untuk mengirim data ke Adobe dan AppsFlyer.

> 📘 **Catatan**
>
> Saat ini, ekstensi Adobe Launch SDK hanya mendukung untuk mendapatkan data konversi dan mengirim event. Namun, ketika Anda menambahkan ekstensi Adobe Launch SDK ke aplikasi Anda, AppsFlyer SDK juga ditambahkan. Oleh karena itu, fungsionalitas apa pun yang saat ini tidak ada dalam ekstensi Adobe SDK dapat diimplementasikan menggunakan AppsFlyer SDK.

<div id="sending-events" />

<Accordion title="Mengirim event">

In-App event memberikan wawasan tentang hal yang terjadi di aplikasi Anda. Sebaiknya luangkan waktu dan tentukan event yang ingin Anda catat. Mencatat in-app event membantu Anda mengukur KPI seperti ROI (Laba atas Investasi) dan LTV (Nilai Seumur Hidup).

Ekstensi Adobe Launch SDK memungkinkan Anda untuk mengirim data in-app event ke Adobe dan AppsFlyer. Anda kemudian dapat menggunakan Adobe Analytics untuk menganalisis perilaku pengguna dan AppsFlyer untuk menganalisis ROI dan LTV.

<Tabs>
<Tab title="Android">

```java
final Map<String,String> eventMap = new HashMap<>();  
eventMap.put("currency", "USD");  
eventMap.put("revenue", "200");  
eventMap.put("freehand", "param");

MobileCore.trackAction("af_purchase", eventMap);
```

</Tab>

<Tab title="iOS">

```objectivec
[ACPCore trackAction:@"af_purchase data:@{@"revenue":@"200",@"currency":@"USD"];
```

</Tab>
</Tabs>

Mengirimkan event seperti yang ditentukan dalam kode di atas akan membuat event di dashboard AppsFlyer bernama af\_purchase dengan pendapatan 200 Dolar Amerika Serikat. Event ini juga dikirim ke dan muncul di Adobe Analytics.

Semua <Anchor target="_blank" href="https://dev.appsflyer.com/docs/direct-deep-linking-1">data konversi</Anchor> yang dikirim dengan event diawali dengan ***appsflyer***. Lihat tabel berikut ini untuk contoh:

| Variabel data konversi yang diawali |
| --- |
| appsflyer.af\_click\_lookback |
| appsflyer.install\_time |
| appsflyer.cost\_cents\_USD |
| appsflyer.media\_source |
| appsflyer.af\_adset |
| appsflyer.click\_time |
| appsflyer.orig\_cost |
| appsflyer.campaign |

Data konversi digunakan dalam aplikasi yang Anda buat di Adobe Mobile Services. Ada parameter lain yang dapat muncul dalam data konversi. Untuk mempelajari lebih lanjut, klik <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#parameter-link-atribusi">di sini</Anchor>.

</Accordion>

<div id="getting-data-for-deep-linking-and-deferred-deep-linking" />

<Accordion title="Mendapatkan data untuk deep linking dan deferred deep linking">

Deep linking dan deferred deep linking memungkinkan Anda untuk meningkatkan pengalaman pengguna. Fitur ini memungkinkan Anda untuk membuka aplikasi dalam aktivitas tertentu dan menyesuaikan konten sesuai dengan data kampanye.

Untuk mendapatkan data dari deep linking, terapkan pemanggilan balik ekstensi.

<Tabs>
<Tab title="Android">

Di kelas aplikasi global, terapkan kode berikut:

```java
AppsFlyerAdobeExtension.registerAppsFlyerExtensionCallbacks(new AppsFlyerExtensionCallbacksListener() {
		@Override
		public void onCallbackReceived(Map<String, String> callback) {
			Log.d(AppsFlyerLibCore.LOG_TAG, callback.toString());
			if(callback.get("callback_type").equals("onConversionDataReceived")){
				// conversion data returned 
				if(callback.get("is_first_launch").equals("true")){
					String af_status = callback.get("af_status");
					if(af_status.equals("Non-organic")){
						Log.d(AppsFlyerLibCore.LOG_TAG, "this is first launch and a non organic install!");
					}
				}
			} else if(callback.get("callback_type").equals("onAppOpenAttribution")){
				// direct deeplink - redirect user
				Log.d(AppsFlyerLibCore.LOG_TAG, callback.toString());
			}
		}
		@Override
		public void onCallbackError(String errorMessage) {
			Log.d("TAG", errorMessage);
		}
	});
```

</Tab>

<Tab title="iOS">

Di AppDelegate.m, terapkan kode berikut:

```objectivec
[AppsFlyerAdobeExtension registerCallbacks:^(NSDictionary *dictionary) {
        NSLog(@"[AppsFlyerAdobeExtension] Received callback: %@", dictionary);
        if([[dictionary objectForKey:@"callback_type"] isEqualToString:@"onConversionDataReceived"]){
            if([[dictionary objectForKey:@"is_first_launch"] boolValue] == YES){
                NSString* af_status = [dictionary objectForKey:@"af_status"];
                if([af_status isEqualToString:@"Non-organic"]){
                    NSLog(@"this is first launch and a non organic install!");
                }
            }
        } else if([[dictionary objectForKey:@"callback_type"] isEqualToString:@"onAppOpenAttribution"]) {
            NSLog(@"onAppOpenAttribution Received");
        }
     }];
    [AppsFlyerAdobeExtension callbacksErrorHandler:^(NSError *error) {
          NSLog(@"[AppsFlyerAdobeExtension] Error recieving callback: %@" , error);
    }];
```

</Tab>
</Tabs>

</Accordion>

## Menghubungkan data konversi AppsFlyer

Data konversi dikirim bersama event ke platform Adobe. Variabel-variabel ini memungkinkan Anda menerapkan logika dan aturan pada dimensi, metrik, atau filter laporan.

![adobe_analytics.png](https://support.appsflyer.com/hc/article_attachments/360006050778)

1. Masuk ke <Anchor target="_blank" href="https://mobilemarketing.adobe.com">Adobe Mobile Services</Anchor> Anda.
2. Pilih aplikasi yang relevan dan masuk ke bagian halaman ***Kelola Variabel & Metrik***.
3. Pilih opsi ***Variabel Khusus*** dan konfigurasikan variabel untuk memetakan data AppsFlyer SDK ke sistem Adobe.
4. Untuk setiap variabel khusus, masukkan nama yang bermakna.
5. Pilih atau ketik data konversi AppsFlyer yang dipetakan dan pilih lingkup ***Persistence*** yang Anda sukai.

Lihat tabel berikut untuk memetakan variabel Konteks AppsFlyer:

| **Nama yang disarankan untuk pemetaan** | **Data konversi** |
| --- | --- |
| Jendela Lookback AppsFlyer | appsflyer.af\_click\_lookback |
| Waktu Instal AppsFlyer | appsflyer.install\_time |
| Biaya AppsFlyer Sen AS | appsflyer.cost\_cents\_USD |
| AppsFlyer MediaSource | appsflyer.media\_source |
| AppsFlyer Adset | appsflyer.af\_adset |
| Waktu Klik AppsFlyer | appsflyer.click\_time |
| Biaya Asli AppsFlyer | appsflyer.orig\_cost |
| Kampanye AppsFlyer | appsflyer.campaign |

### Menggunakan data konversi yang dipetakan AppsFlyer untuk Analitik dan Analisis

Semua data yang berasal dari SDK tersedia dalam rangkaian laporan Adobe Analytics yang terhubung ke aplikasi.

Anda dapat menggunakan data dan dimensi serta metrik terkait di seluruh laporan dan dashboard Adobe Analytics yang dihasilkan. Data ini juga tersedia di dashboard AppsFlyer untuk atribusi dan analisis in-app event.

<div data-zendesk-anchors="overview=ringkasan h_01HQQN1Y7MP7B0GXJFP5330G80=ringkasan h_01HQQNCMYNN0YH7S8Q5F2EWFG5=catatan prerequisites=prasyarat h_01HQQN1JWAQZZ9S3YV7VXTMRWM=prasyarat h_01HQQN1JWA4JYET26CB11JGY46=get-your-appsflyer-dev-key h_01HQQN1JWAHYQBRY43EWANQ57Z=get-your-app-id step-1-configuring-adobe-launch=langkah-1-melakukan-konfigurasi-adobe-launch h_01HQQN1JWAAR873B679QGA9NSX=langkah-1-melakukan-konfigurasi-adobe-launch h_01HQQN1JWAE1T7SP3DHTFB55TK=11-creating-a-new-property-in-adobe-launch h_01HQQN1JWA8FDWMNZ4Y17AWYKW=12-installing-required-adobe-launch-extensions installing-adobe-analytics-extension=menginstal-ekstensi-adobe-analytics h_01HQQN1JWAMB8607K8V2F3YKHE=menginstal-ekstensi-adobe-analytics installing-appsflyer-sdk-extension=menginstal-ekstensi-appsflyer-sdk h_01HQQN1JWAYHP9243MTFZ4B2EF=menginstal-ekstensi-appsflyer-sdk install-profile-and-mobile-core-extension=instal-profil-dan-ekstensi-mobile-core h_01HQQN1JWA1TEBQY1NH3YP2HQB=instal-profil-dan-ekstensi-mobile-core step-2-implementing-appsflyer-adobe-sdk-extension=langkah-2-menerapkan-ekstensi-appsflyer-adobe-sdk h_01HQQN1JWB3B24RHP9QMNPJK8J=langkah-2-menerapkan-ekstensi-appsflyer-adobe-sdk h_01HQQN1JWBMP4ARMH2VPX35TGH=21-adding-the-sdk-to-the-app h_01HQQN1JWBV3144WY92PAX6PW2=22-publishing-the-environment h_01HQQN1JWBRRCTGA6Q9RDC41KN=23-adding-android-install-referrer-to-your-app h_01HQQN1JWB40T4K3ZJB6AE42WQ=catatan-1 h_01HQQN1JWB19NTCNTWX9QRP8AC=24-setting-required-permissions add-required-permissions=tambahkan-hak-akses-yang-diperlukan h_01HQQN1JWBVVVGRRXGX9ZJTBT8=tambahkan-hak-akses-yang-diperlukan using-the-adobe-sdk-extension=menggunakan-ekstensi-adobe-sdk h_01HQQN1JWBFD2CZ4PMCBRM3JN8=menggunakan-ekstensi-adobe-sdk h_01HQQN1JWBSBVFVB911WH54Q32=catatan-2 h_01HQQN1JWBVZDAVAZD4NXMBG4S=sending-events h_01HQQN1JWBXG0JCE9RKA659H6V=getting-data-for-deep-linking-and-deferred-deep-linking connecting-appsflyer-conversion-data=menghubungkan-data-konversi-appsflyer h_01HQQN1JWBMBXGQFKGWHE058VT=menghubungkan-data-konversi-appsflyer using-appsflyer-mapped-conversion-data-for-analytics-and-analysis=menggunakan-data-konversi-yang-dipetakan-appsflyer-untuk-analitik-dan-analisis h_01HQQN1JWB0WBD6HZXQN6STJY9=menggunakan-data-konversi-yang-dipetakan-appsflyer-untuk-analitik-dan-analisis" />
