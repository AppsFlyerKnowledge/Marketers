---
title: Integrasi Oracle Responsys dengan AppsFlyer
metadata:
  keywords:
    - Oracle Responsys
    - Advertisers
    - Developers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-11-20T09:26:13Z'
  edited_at: '2023-10-27T14:54:34Z'
  id: 360003798297
  locale: id
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/id/articles/360003798297
---
> **Sekilas:** Oracle Responsys, platform pengiriman dan analitik email, menyematkan AppsFlyer OneLink di dalam email. Penerima email yang mengeklik tautan tersebut ditautkan langsung ke aplikasi Anda.

<Image align="center" alt="oracle-responsys-af-logo.png" src="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png" />

ESP (Penyedia Layanan Email) dapat menjadi sumber yang bagus untuk lalu lintas pengguna yang tersegmentasi.

Salah satu tantangan dengan ESP adalah melakukan atribusi dan tautan langsung yang benar. ESP menggabungkan URL tautan langsung dengan domain catatan klik ESP mereka sendiri. Prosedur ini sering kali merusak fungsi Tautan Universal iOS dan Tautan Aplikasi Android.

Namun, tautan langsung dan pencatatan klik masih dapat dilakukan dengan ESP yang mendukung Tautan Universal dan Tautan Aplikasi di atas domain pencatatan kliknya. Selain itu, Anda dapat menyiapkan domain klik Anda sendiri untuk bertindak sebagai domain pencatatan klik.

<div id="prerequisites" />

## Prasyarat

* Konfigurasikan aplikasi Anda untuk mendukung <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">tautan langsung dengan OneLink</Anchor>.
* Verifikasi versi SDK Anda (Android dan iOS)

<Tabs>
<Tab title="iOS">

* AppsFlyer iOS SDK versi 4.9.0 (atau lebih tinggi)

</Tab>

<Tab title="Android">

* AppsFlyer Android SDK versi 4.9.0 (atau lebih tinggi)

</Tab>
</Tabs>

<div id="setting-up-oracle-responsys-click-domain" />

## Menyiapkan domain klik Oracle Responsys

Ikuti bagian ini untuk menyiapkan domain klik Anda (domain pencatatan klik) di Oracle Responsys.

<div id="step-1-set-up-a-click-domain-in-oracle-responsys" />

### Langkah 1: Siapkan domain klik di Oracle Responsys

Untuk menyiapkan domain klik, ikuti panduan resmi Oracle Responsys tentang cara <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCEA/LinkTable_Main.htm?cshid=LinkTable_Main">membuat domain klik</Anchor>. Oracle Responsys menggunakan Tabel Tautan untuk membantu mencatat klik untuk kampanye tertentu

**Catatan**, di tabel Tautan, Anda dapat menentukan **URL tautan IOS** agar sama dengan URL Tautan:

<Image align="center" alt="Oracle-responsys-link-tracking-table.png" src="https://files.readme.io/c151c58af73cf460ba4275a9159e45c15807f311fa8d8b4b1531b0cdf7e3bc4e-49839256667665.png" />

Setelah Anda mengatur domain klik di Tabel Tautan, Responsys menggunakan domain ini untuk menggabungkan OneLink yang Anda sertakan dalam kampanye email. Dengan cara ini, Responsys dapat mencatat klik di sistem mereka sambil mempertahankan OneLink dan fungsionalitas tautan langsung.

<div id="step-2-give-responsys-an-aasa-ios-and-an-asset-links-file-android" />

### Langkah 2: Berikan Responsys file AASA (iOS) dan file Tautan Aset (Android)

<div id="aasa-for-ios" />

<Accordion title="AASA untuk iOS">

Agar Responsys mendukung Tautan Universal iOS, mereka memerlukan file AASA. Lihat instruksi berikut.

Saat Anda menyiapkan OneLink dengan Tautan Universal, Anda sudah memiliki AASA yang dikaitkan dengan OneLink. Untuk mendapatkan AASA:

1. Buka konfigurasi OneLink dan temukan OneLink yang dikonfigurasi dengan Tautan Universal.
2. Tambahkan **/.well-known/apple-app-site-association** di akhir URL OneLink.
3. Rekatkan OneLink di bilah alamat browser dan tekan enter. Misalnya: **`<OneLinkSubdomain>`.onelink.me/.well-known/apple-app-site-association**. Saat Anda melakukannya, file AASA diunduh ke komputer Anda. Anda dapat membukanya menggunakan editor teks sederhana mana pun.
4. Kirim file AASA ini ke Responsys. Untuk informasi lebih lanjut dan mempelajari lebih lanjut tentang isi file ini, lihat halaman 11 dari <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCFB/pdf/ios-universal-links-dev-guide.pdf">panduan Oracle</Anchor>.

</Accordion>

<div id="asset-links-for-android" />

<Accordion title="Tautan Aset untuk Android">

Saat Anda mengatur OneLink dengan Tautan Aplikasi, Anda sudah memiliki file Tautan Aset yang terkait dengan OneLink. Untuk mendapatkan file Tautan Aset. Untuk mendapatkan file Tautan Aset:

1. Buka konfigurasi OneLink dan temukan OneLink yang dikonfigurasi dengan Tautan Aplikasi.
2. Tambahkan **/.well-known/assetlinks.json** di akhir URL OneLink.
3. Rekatkan OneLink di bilah alamat browser dan tekan enter. Misalnya:**`<OneLinkSubdomain>`.onelink.me/.well-known/assetlinks.json**. Saat Anda melakukannya, file Tautan Aset telah diunduh ke komputer Anda. Anda dapat membukanya menggunakan editor teks sederhana mana pun.
4. Kirim file Tautan Aset ini ke Responsys. Untuk informasi lebih lanjut dan mempelajari lebih lanjut tentang isi file ini, lihat <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCFB/android/app-links/">panduan ini</Anchor>.

</Accordion>

<div id="setting-up-your-app" />

## Mengatur aplikasi Anda

<div id="step-1-for-android-setting-up-your-app-to-support-app-links" />

<Accordion title="Langkah 1 untuk Android: Menyiapkan aplikasi Anda untuk mendukung Tautan Aplikasi">

<div id="adding-the-click-domain-to-the-activity-in-the-android-manifest" />

#### Menambahkan domain klik ke aktivitas di manifes Android

Di manifes Android, tambahkan host domain klik dan awalan apa pun di tag aktivitas dari aktivitas yang ingin Anda langsung tautkan.

```html Markup
<activity android:name=".DeepLinkActivity">
    <intent-filter  android:autoVerify="true">
        <action android:name="android.intent.action.VIEW" />
           <category android:name="android.intent.category.DEFAULT" />
           <category android:name="android.intent.category.BROWSABLE" />
           <data android:scheme="https"
               android:host="click.example.com"
               android:pathPrefix="/campaign" />
     </intent-filter>
</activity>
```

<div id="setting-up-the-app-to-resolve-click-domains" />

#### Mengatur aplikasi untuk menyelesaikan domain klik

SDK perlu menyelesaikan OneLink di balik domain klik untuk mendapatkan detail kampanye. Detailnya dikembalikan dalam metode `onAppOpenAttribution` .

Untuk mengatasi domain klik:

1. Pastikan versi SDK Anda minimal 4.9.0.
2. Cantumkan domain klik di `setResolveDeepLinkURLs` API SDK. API ini perlu dipanggil sebelum inisialisasi SDK. Untuk informasi lebih lanjut, silakan lihat dokumentasi SDK <Anchor target="_blank" href="/marketers/id/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">di sini</Anchor>.  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("click.example.com");
   ```

   * **Penting!** Jika Anda menggunakan Movable Ink (MI) bersama dengan Oracle, Anda perlu mendapatkan MI CNAME dan domain internal dari manajer akun MI Anda dan menambahkannya ke `setResolveDeepLinkURLs`, selain tautan klik untuk Oracle. Contoh:

     ```java
     AppsFlyerLib.getInstance().setResolveDeepLinkURLs("oracle-click.example.com", "mi.example.com", "example.micpn.com");
     ```

</Accordion>

<div id="step-1-for-ios-setting-up-your-app-to-support-universal-links" />

<Accordion title="Langkah 1 untuk iOS: Mengatur aplikasi Anda untuk mendukung Tautan Universal">

Bagian ini membahas cara mengatur aplikasi Anda untuk mendukung Tautan Universal.

<div id="associating-click-domains-in-xcode" />

#### Mengaitkan domain klik di Xcode

1. Di Xcode, klik proyek Anda.
2. Klik di ***Kemampuan***.[![configure-xcode-deeplinking-domain.png](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)
3. Aktifkan ***Domain Terkait*** .
4. Klik tanda + dan tambahkan domain klik Anda. Misalnya, applinks:click.example.com.

</Accordion>

<div id="step-2-setting-up-the-app-to-resolve-click-domains" />

### Langkah 2: Mengatur aplikasi untuk menyelesaikan domain klik

SDK perlu menyelesaikan OneLink di balik domain klik untuk mendapatkan detail kampanye. Detailnya dikembalikan dalam metode `onAppOpenAttribution` .

Untuk mengatasi domain klik:

1. Pastikan versi SDK Anda minimal 4.9.0.
2. Cantumkan domain klik di properti SDK `resolveDeepLinkURLs`. Properti ini perlu disetel sebelum inisialisasi SDK. Untuk informasi lebih lanjut, silakan lihat dokumentasi SDK <Anchor target="_blank" href="/marketers/id/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">di sini</Anchor>.  

   <Tabs>
   <Tab title="Objective-C">

   ```objectivec
   [AppsFlyerTracker sharedTracker].resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```

   </Tab>

   <Tab title="Swift">

   ```swift
   AppsFlyerTracker.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   </Tab>
   </Tabs>

   * **Penting!** Jika Anda menggunakan Movable Ink (MI) bersama dengan Oracle, Anda perlu mendapatkan MI CNAME dan domain internal dari manajer akun MI Anda dan menambahkannya ke `setResolveDeepLinkURLs`, selain tautan klik untuk Oracle. Contoh domain:
     * Domain Oracle: oracle-klik.example.com
     * Domain MI CNAME: mi.example.com
     * Domain internal MI: example.micpn.com
3. Tambahkan kode berikut agar SDK dapat mengatasi domain pencatatan klik:  

   <Tabs>
   <Tab title="Objective-C">

   Tambahkan kode ini di AppDelegate.m

   ```objectivec
   - (NSDictionary *)allHTTPHeaderFieldsForResolveDeepLinkURL:(NSURL *)URL {
       if ([URL.host  isEqual: @"click.example.com"]) {
           return [NSDictionary dictionary];
       }
       else {
           return nil;
       }
   }
   ```

   </Tab>

   <Tab title="Swift">

   Tambahkan kode ini di AppDelgate.swift

   ```swift
   func allHTTPHeaderFields(forResolveDeepLinkURL URL: URL!) -> [String : String]! {
       if (URL.host == "click.example.com") {
           /// Change User-Agent
           return [:]
       } else {
           return nil;
       }
   }
   ```

   </Tab>
   </Tabs>

<div id="sending-your-first-email" />

## Mengirim email pertama Anda

1. Buat URL OneLink di halaman Manajemen Tautan (atau secara manual).
2. Saat membuat URL OneLink, pastikan URL mengkodekan semua nilai parameter.
3. Parameter berikut sangat disarankan untuk digunakan:
   * pid (sumber media) - Gunakan sumber media yang menandakan penggunaan ini seperti Email.
   * c (kampanye) - Nama kampanye yang ingin Anda ukur.
   * af\_dp - Skema URI tautan langsung ke mana Anda ingin tautkan pengguna Anda secara langsung.
   * af\_web\_dp - Tempat mengarahkan pengguna dengan mengeklik tautan di desktop.
   * af\_ios\_url - Tempat mengalihkan pengguna yang tidak memiliki aplikasi dengan mengeklik tautan di perangkat iOS.
   * af\_android\_url - Tempat mengarahkan pengguna yang tidak memiliki aplikasi dengan mengeklik tautan di perangkat Android.
4. Tempatkan URL OneLink di email yang Anda buat di Responsys. Contoh:

   ```http
   <a href="greatapp.onelink.me/abcd/1234567">Unduh aplikasi keren saya!</a>
   ```

   Pada tahap ini, Responsys menggabungkan tautan di atas dengan domain klik yang Anda atur pada langkah sebelumnya. Setiap klik pada domain klik mengalihkan ke tautan atribusi OneLink. Jika aplikasi diinstal pada perangkat pengguna, domain klik akan ditautkan langsung ke aplikasi.

<div id="note" />

> 📄 **Contoh**
>
> Parameter URL bukan URL yang dikodekan dalam contoh ini, hanya demi keterbacaan:
>
> ```http
> https://greatapp.onelink.me/abcd?pid=Email&c=Spring_Newsletter&is_retargeting=true&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

<div id="testing-your-links" />

### Menguji tautan Anda

Setelah mengikuti semua langkah wajib yang disebutkan di atas, membuat URL OneLink yang sesuai, dan menempatkannya di email, kirimkan email percobaan kepada diri Anda sendiri.

Apa yang Anda harapkan?

Jika Anda telah menginstal aplikasi tersebut, aplikasi tersebut harus dijalankan. Jika API relevan yang ditautkan langsung ke AppsFlyer SDK sudah diterapkan, Anda seharusnya sudah ditautkan secara langsung ke konten yang relevan.  
Selain itu, sebuah klik akan muncul di dashboard AppsFlyer, yang dikaitkan dengan sumber media dan kampanye yang disediakan, dan juga di data Responsys.

<div data-zendesk-anchors="prerequisites=prasyarat h_01HDNSK7GR33AN2M4GP956S1FD=prasyarat setting-up-oracle-responsys-click-domain=menyiapkan-domain-klik-oracle-responsys h_01HDNSK7GR84QSRTS86GH556WK=menyiapkan-domain-klik-oracle-responsys step-1-set-up-a-click-domain-in-oracle-responsys=langkah-1-siapkan-domain-klik-di-oracle-responsys h_01HDNSK7GRHYJZSMYCMT9RVEBW=langkah-1-siapkan-domain-klik-di-oracle-responsys step-2-give-responsys-an-aasa-ios-and-an-asset-links-file-android=langkah-2-berikan-responsys-file-aasa-ios-dan-file-tautan-aset-android h_01HDNSK7GRW57NNXMN1SWFTTFZ=langkah-2-berikan-responsys-file-aasa-ios-dan-file-tautan-aset-android h_01HDNSK7GR77N60SFVBD57S9GQ=aasa-for-ios h_01HDNSK7GR6ADJCPG63ZVP19NJ=asset-links-for-android setting-up-your-app=mengatur-aplikasi-anda h_01HDNSK7GRN751HAPPQ3HVRMDG=mengatur-aplikasi-anda h_01HDNSK7GRHCK378A8XKMK7ZZF=step-1-for-android-setting-up-your-app-to-support-app-links adding-the-click-domain-to-the-activity-in-the-android-manifest=menambahkan-domain-klik-ke-aktivitas-di-manifes-android h_01HDNSK7GRQNQGWXAEGHSTHADH=menambahkan-domain-klik-ke-aktivitas-di-manifes-android setting-up-the-app-to-resolve-click-domains=mengatur-aplikasi-untuk-menyelesaikan-domain-klik h_01HDNSK7GRP9ND0MHC3ZHD7G8H=mengatur-aplikasi-untuk-menyelesaikan-domain-klik h_01HDNSK7GRJ682QYAMPB4PSGRZ=step-1-for-ios-setting-up-your-app-to-support-universal-links associating-click-domains-in-xcode=mengaitkan-domain-klik-di-xcode h_01HDNSK7GSRENM232MQ25EB3J3=mengaitkan-domain-klik-di-xcode step-2-setting-up-the-app-to-resolve-click-domains=langkah-2-mengatur-aplikasi-untuk-menyelesaikan-domain-klik h_01HDNSK7GSP08G2EQSNVR5G45B=langkah-2-mengatur-aplikasi-untuk-menyelesaikan-domain-klik sending-your-first-email=mengirim-email-pertama-anda h_01HDNSK7GSA9VAMTRFCX8SZGSC=mengirim-email-pertama-anda h_01HDNSK7GS8HP7BAA8BYBVBABD=contoh testing-your-links=menguji-tautan-anda h_01HDNSK7GSTAJXAP6KGKE9TD8T=menguji-tautan-anda" />
