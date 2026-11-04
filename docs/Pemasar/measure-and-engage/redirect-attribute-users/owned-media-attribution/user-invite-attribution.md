---
title: Atribusi Undangan Pengguna
metadata:
  keywords:
    - OneLink
    - Advertisers
    - User invite
    - Developers
    - Marketers
    - Text-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Text-to-App
  created_at: '2017-08-30T12:13:45Z'
  edited_at: '2023-09-27T11:34:18Z'
  id: 115004480866
  locale: id
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/id/articles/115004480866
---
> **Sekilas:** Atribusikan dan catat penginstalan baru ketika pengguna lama merujuk orang lain untuk menggunakan aplikasi Anda.

[![Invite_Attribution_new.png](https://files.readme.io/ee6793f57e16e7b051d1651108d7408482dff15501d9d786b5ca250e71d54ed4-360002880777.png)](https://files.readme.io/ee6793f57e16e7b051d1651108d7408482dff15501d9d786b5ca250e71d54ed4-360002880777.png)

<div id="about-user-invite-attribution" />

## Tentang atribusi undangan pengguna

Undangan pengguna berarti pengguna aplikasi Anda saat ini membagikan tautan yang mengarahkan orang lain (misalnya, teman mereka) untuk mengunduh/membuka aplikasi Anda.

Atribusi undangan pengguna berarti Anda mengatribusikan setiap penginstalan atau interaksi aplikasi yang baru kepada pengguna yang mengirimkan rujukan.

Atribusi undangan pengguna memungkinkan Anda:

* Analisis biaya dan ROI undangan pengguna. Undangan pengguna menghabiskan ruang iklan aplikasi Anda, yang seharusnya dapat digunakan untuk menghasilkan pendapatan iklan. Anda mungkin ingin melihat apakah undangan pengguna memberikan ROI yang lebih baik dibandingkan alternatif lainnya.
* Catat informasi tentang pengguna Anda yang paling banyak merujuk orang lain. Pengguna yang mengundang orang lain ke aplikasi Anda adalah pengguna yang bernilai tinggi dan terlibat, yang mungkin ingin Anda targetkan ulang atau berikan insentif.

Anda juga dapat menggunakan data dari tautan ke:

* Sesuaikan pengalaman pengguna baru. Misalnya, buka aplikasi untuk konten tertentu, atau alih-alih pesan umum, personalisasikan pesan selamat datang, seperti, "Hai John! Temanmu Maria ingin menantangmu bermain. Main sekarang!"
* Hadiahi pengguna yang mereferensikan orang lain. [Pelajari lebih banyak](/docs/user-invite-attribution#reward-referrers-for-user-invite-installs)

Tautan undangan pengguna yang dibagikan pengguna dengan orang lain sebenarnya adalah tautan khusus OneLink (URL pendek) yang dihasilkan oleh SDK AppsFlyer yang terintegrasi dalam aplikasi Anda. Pengaturan OneLink Anda memastikan bahwa pengguna yang mendapat undangan dialihkan ke tempat yang tepat—ke app store yang benar, ke dalam aplikasi Anda, atau tautan langsung/menunda deep link (tautan langsung) ke halaman tertentu di aplikasi Anda. <Anchor target="_blank" href="/marketers/id/docs/onelink-guide">Pelajari lebih banyak tentang OneLink</Anchor>

<div id="flow" />

### Alur

Alur kerjanya sebagai berikut:

1. Pengguna A mengetuk dari dalam aplikasinya untuk berbagi aplikasi dengan teman. (Pengguna A telah menginstal aplikasi dan masuk.)
2. Ketukan tersebut menghasilkan tautan dengan parameter yang mengidentifikasi Pengguna A di dalamnya.
3. Pengguna A mengirimkan tautan ke Pengguna B melalui email/WhatsApp/SMS, dll.
4. Jika Pengguna B:
   * Setelah aplikasi terinstal, aplikasi akan terbuka. Pengguna B dapat ditautkan secara langsung ke halaman tertentu di aplikasi dan/atau diberi hadiah.
   * Tidak menginstal aplikasi, aplikasi dikirim ke app store yang tepat. Pengguna B dapat ditangguhkan tautan langsungnya ke halaman tertentu di aplikasi setelah peluncuran aplikasi pertama, dan/atau Pengguna A dapat diberi hadiah.
   * Melakukan in-app event, Pengguna A dapat diberi hadiah.

<div id="viewing-data" />

## Melihat data

Data undangan pengguna tersedia melalui dashboard dan laporan AppsFlyer. Di dashboard AppsFlyer, Anda dapat memfilter atribusi undangan pengguna berdasarkan:

* **Sumber media**: Undangan aplikasi.
* **Saluran**: Seperti yang diputuskan oleh pemasar.
* **Kampanye**: Seperti yang diputuskan oleh pemasar.

Dalam laporan, sumber media (parameter `pid` ) dikirim oleh SDK dengan nilai default `af_app_invites`. 

<div id="procedures" />

## Prosedur

**Untuk membuat tautan undangan pengguna**:

1. Buat <Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template#prosedur">templat OneLink</Anchor>.
2. Tentukan nilai parameter kanal dan kampanye. Lihat [parameter](/docs/user-invite-attribution#parameters).
3. Putuskan kasus penggunaan mana yang Anda inginkan untuk tautan tersebut. Kasus penggunaan umum meliputi:
   * Deep link (Penautan langsung) pengguna baru ke halaman tertentu di aplikasi.
   * Catat pengguna mana yang membuat rujukan.
   * Hadiahi pengguna baru.
4. Hubungi pengembang Android dan iOS Anda untuk merencanakan parameter mana yang akan bertanggung jawab atas kasus penggunaan yang Anda inginkan untuk tautan. Lihat [parameter](/docs/user-invite-attribution#parameters) yang tersedia.
5. Beri tahu pengembang untuk <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">menerapkan deep linking</Anchor> (menggunakan perilaku parameter yang diinginkan dalam kode).
6. Beri tahu pengembang untuk menerapkan undangan pengguna di platform berikut:

   <Tabs>
   <Tab title="Android">

   Lihat [undangan pengguna Android](https://dev.appsflyer.com/hc/docs/dl_android_user_invite) di Dev Hub.

   </Tab>

   <Tab title="iOS">

   Lihat [undangan pengguna iOS](https://dev.appsflyer.com/hc/docs/dl_ios_user_invite) di Dev Hub.

   </Tab>

   <Tab title="Unity">

   Lihat [Undangan pengguna](https://dev.appsflyer.com/hc/docs/userinvite) di Dev Hub.

   </Tab>
   </Tabs>

<div id="parameters" />

<Accordion title="Parameter">

<div id="parametersvalues-provided-to-the-developer-to-implement-in-the-sdk" />

#### Parameter/nilai diberikan kepada pengembang untuk diterapkan di SDK

<table><thead><tr><th><span>Parameter/nilai</span></th><th><span>Catatan</span></th><th><span>Catat nilai/kasus penggunaan yang harus diterapkan pengembang</span></th></tr></thead><tbody><tr><td><span>ID templat OneLink</span></td><td><p>ID templat OneLink dengan pengaturan dasar yang menjadi dasar semua tautan undangan pengguna. Misalnya: H5hv</p></td><td></td></tr><tr><td><span>Channel</span></td><td><p>Nama kanal. Ini membantu Anda mengurutkan dan melihat atribusi berdasarkan kanal di UI AppsFlyer.</p></td><td></td></tr><tr><td><span>Kampanye</span></td><td><p>Nama kampanye. Ini membantu Anda mengurutkan dan melihat atribusi berdasarkan kampanye di UI AppsFlyer.</p></td><td></td></tr><tr><td> <span>is_retargeting=true</span><span><br/></span> </td><td><p>Ditambahkan jika kampanye Anda menargetkan ulang pengguna yang sudah ada.</p></td><td></td></tr><tr><td><span>deep_link_value</span></td><td><p>Parameter yang akan digunakan pada perangkat pengguna yang dirujuk untuk memberikan mereka pengalaman tertentu. Biasanya, ini digunakan untuk <span>memberi nama halaman tertentu yang akan dituju pengguna. Misalnya, jika aplikasi Anda menjual buah, Anda dapat menautkan langsung pengguna ke halaman apel.</span></p></td><td></td></tr><tr><td><span>deep_link_sub1</span></td><td rowspan="10"><p>Parameter yang akan digunakan pada perangkat pengguna yang dirujuk untuk memberikan mereka pengalaman tertentu. Karena deep_link_value biasanya digunakan untuk mengarahkan pengguna ke halaman tertentu, parameter ini dapat digunakan untuk fungsi lain yang diinginkan. Misalnya untuk menambahkan hadiah atau diskon, atau mencatat pengguna yang melakukan referral. </p></td><td></td></tr><tr><td><span>deep_link_sub2</span></td><td></td></tr><tr><td><span>deep_link_sub3</span></td><td></td></tr><tr><td><span>deep_link_sub4</span></td><td></td></tr><tr><td><span>deep_link_sub5</span></td><td></td></tr><tr><td><span>deep_link_sub6</span></td><td></td></tr><tr><td><span>deep_link_sub7</span></td><td></td></tr><tr><td><span>deep_link_sub8</span></td><td></td></tr><tr><td><span>deep_link_sub9</span></td><td></td></tr><tr><td><span>deep_link_sub10</span></td><td></td></tr><tr><td><span>[Opsional] pid</span></td><td><p>Secara default, tautan yang Anda buat menyertakan<span> sumber media (parameter <code>pid</code> ) dengan nilai <code>af_app_invites</code>. </span></p><p><span>Untuk mengubah nilainya, pengembang Anda perlu menambahkan parameter khusus yang disebut <code>pid</code> dengan nilai yang Anda inginkan. <strong>Catatan</strong>: Untuk Android, ini hanya berfungsi untuk SDK V6.4.2+.</span></p></td><td></td></tr><tr><td><span>Nama bermerek</span></td><td><p>Nama domain bermerek. Ini membantu Anda mengurutkan dan melihat atribusi berdasarkan domain bermerek di UI AppsFlyer.</p></td><td></td></tr></tbody></table>

</Accordion>

<div id="example" />

<Accordion title="Contoh">

Tandai pemasar yang memiliki aplikasi yang menjual buah. Dia ingin membuat tautan yang menautkan langsung pengguna ke halaman buah tertentu, dengan opsi untuk membeli buah dalam jumlah tertentu.

Dia ingin tautan ini dapat dikirim melalui undangan pengguna dan memberi penghargaan kepada perujuk setiap kali rujukan mereka mengarah ke penginstalan aplikasi baru dan pembelian buah.

Agar semua ini berfungsi, Mark mengirimkan kepada pengembangnya daftar parameter dan nilai berikut yang akan digunakan saat menerapkan tautan undangan pengguna: pengembangnya akan menerapkan:

| Parameter | value | Catatan |
| --- | --- | --- |
| deep\_link\_value | fruit\_name | Untuk tautan langsung menggunakan metode UDL AppsFlyer. |
| deep\_link\_sub1 | promo\_code | Untuk tautan langsung menggunakan metode UDL AppsFlyer. |
| deep\_link\_sub2 | referrer\_id | Untuk pembuatan tautan melalui SDK. |
| param\_1 | referrer\_id | Untuk in-app event yang mencatat setiap pembelian. |
| Channel | mobile\_share | Untuk atribusi dan melihat data di AppsFlyer. |
| Kampanye | summer\_sale | Untuk atribusi dan melihat data di AppsFlyer. |

</Accordion>

<div id="additional-information" />

## Informasi Tambahan

<div id="record-user-invites-as-inapp-events" />

<Accordion title="Catat undangan pengguna sebagai in-app event">

Mencatat in-app event setelah pengguna mengirimkan undangan pengguna akan membantu Anda mengidentifikasi pengguna yang mereferensikan orang lain, serta sumber media yang memberi Anda perujuk tersebut.

**Untuk mencatat in-app event undangan pengguna**:

* Kirim <Anchor target="_blank" href="/marketers/id/docs/in-app-events-event-structure#invite-af_invite">event af\_invite.</Anchor> Pengembang perlu menerapkan ini dengan mengikuti instruksi hub pengembang kami.

**Catatan**: Anda dapat menambahkan lebih banyak parameter yang ingin Anda kaitkan dengan event tersebut. Pilih parameter yang akan memberikan konteks tambahan pada event dan memperkaya data. <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#mengatur-in-app-event">Pelajari lebih lanjut</Anchor>

</Accordion>

<div id="reward-referrers-for-user-invite-installs" />

<Accordion title="Hadiahi perujuk untuk penginstalan undangan pengguna">

**Untuk memberikan hadiah kepada perujuk atas undangan pengguna yang menghasilkan penginstalan**:

1. Pastikan ID perujuk adalah nilai salah satu [parameter deep\_link\_sub1-10](/docs/user-invite-attribution#parameters).
2. Beri tahu pengembang aplikasi Anda untuk <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">menerapkan tautan langsung</Anchor> (menggunakan perilaku yang diinginkan dari parameter yang dipilih dalam kode).
3. Beritahu pengembang backend Anda untuk bekerja sama dengan pengembang aplikasi Anda untuk mengambil ID perujuk (dari laporan AppsFlyer) dan memberi hadiah kepada perujuk.

Contoh:

1. Pengguna A mengundang Pengguna B untuk menginstal aplikasi Anda.
2. Saat Pengguna B meluncurkan aplikasi, aplikasi tersebut mendapatkan ID perujuk Pengguna A.
3. Backend Anda mengambil ID perujuk dari laporan AppsFlyer.
4. Di backend Anda, tambahkan ID perujuk pengguna A ke daftar pengguna yang akan diberi hadiah
5. Saat Pengguna A meluncurkan aplikasi, periksa apakah ID perujuknya ada dalam daftar pengguna yang akan diberi hadiah, dan jika ya, berikan hadiah kepada mereka.

</Accordion>

<div id="reward-referrers-for-referred-user-actions" />

<Accordion title="Hadiahi perujuk untuk tindakan pengguna yang dirujuk">

**Untuk memberikan hadiah kepada perujuk atas undangan pengguna yang menghasilkan in-app event tertentu**:

1. <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#mengatur-in-app-event">Buat in-app event</Anchor> yang ingin Anda beri hadiah.
2. Beritahu pengembang untuk menambahkan parameter (misalnya, param\_1) ke event dengan nilai sebagai ID perujuk. **Catatan**: ID perujuk aslinya dicatat pada penginstalan aplikasi menggunakan [parameter](/docs/user-invite-attribution#parameters) yang Anda pilih (deep\_link\_sub1-10).
3. Beritahu pengembang backend Anda untuk bekerja sama dengan pengembang aplikasi Anda untuk mengambil ID perujuk (dari laporan AppsFlyer) dan memberi hadiah kepada perujuk.

Contoh:

1. Pengguna A mengundang Pengguna B untuk melakukan suatu tindakan di aplikasi Anda.
2. Saat Pengguna B melakukan tindakan tersebut, sebuah in-app event dicatat yang berisi ID perujuk Pengguna A.
3. Backend Anda mengambil ID perujuk dari laporan AppsFlyer.
4. Di backend Anda, tambahkan ID perujuk pengguna A ke daftar pengguna yang akan diberi hadiah
5. Saat Pengguna A meluncurkan aplikasi, periksa apakah ID perujuknya ada dalam daftar pengguna yang akan diberi hadiah, dan jika ya, berikan hadiah kepada mereka.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Karakteristik dan batasan">

| Sifat | Deskripsi |
| --- | --- |
| Versi SDK | Harus memiliki SDK AppsFlyer versi 4.8.0+ dan Unity SDK versi 4.17.0+. |
| <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page"> Laman arahan aplikasi media sosial</Anchor> | Tautan yang dihasilkan dari undangan pengguna tidak dapat mengimplementasikan halaman awal aplikasi media sosial. |
| Waktu hidup (TTL) | Waktu hidup (TTL) default untuk URL pendek OneLink yang dibuat melalui undangan pengguna SDK adalah 60 hari. Ini diperpanjang 60 hari setiap kali tautan diklik. |
| Harga | Gratis untuk semua paket akun |
| iOS 14+ | Atribusi undangan pengguna tidak menggunakan IDFA, jadi iOS 14 tidak memengaruhinya dengan cara apa pun. |
| ID URL | ID URL (atau ID tautan pendek) dapat diedit untuk menyoroti penawaran kampanye Anda. Contohnya: https://myapp.onelink.me/abc123/apples. ID URL tidak boleh melebihi 50 karakter dan dapat berupa kombinasi huruf dan angka. Secara default, ini adalah 8 karakter.<br /><br />**Catatan**: Anda hanya dapat mengedit ID URL jika ID saat ini belum digunakan. |

</Accordion>

<div data-zendesk-anchors="about-user-invite-attribution=tentang-atribusi-undangan-pengguna h_01H98E1CZ2AG8AW2H77SPPHFGR=tentang-atribusi-undangan-pengguna flow=alur h_01H98E1CZ234MRBWDEYGZFCDRE=alur viewing-data=melihat-data h_01H98E1CZ23FEAS8JJC7FFTFXD=melihat-data procedures=prosedur h_01H98E1CZ2VBCG0RREERW8FNJE=prosedur h_01H98E1CZ2WE6DJW717C6AJWXD=parameters parametersvalues-provided-to-the-developer-to-implement-in-the-sdk=parameternilai-diberikan-kepada-pengembang-untuk-diterapkan-di-sdk h_01H98E1CZ2CANBK1T55DD103JB=parameternilai-diberikan-kepada-pengembang-untuk-diterapkan-di-sdk h_01H98E1CZ2NXCCYEV12JC6EMFG=example additional-information=informasi-tambahan h_01H98E1CZ28T2SJ3YNY8TNCAZY=informasi-tambahan h_01H98E1CZ2172W6845K099F814=record-user-invites-as-inapp-events h_01H98E1CZ316WWYK55XTN4C8JE=reward-referrers-for-user-invite-installs h_01H98E1CZ330FXG06A4MVQ56PW=reward-referrers-for-referred-user-actions h_01H98E1CZ3SPASZDF5CCY3T3B3=traits-and-limitations" />
