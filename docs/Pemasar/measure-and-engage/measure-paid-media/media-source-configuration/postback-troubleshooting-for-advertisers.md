---
title: 'Pemecahan masalah postback untuk pemasang iklan '
metadata:
  keywords:
    - Postback
    - Partner
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-04-04T07:09:26Z'
  edited_at: '2023-11-27T05:16:32Z'
  id: 14272573202833
  locale: id
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/id/articles/14272573202833
---
> **Sekilas:** Temukan penyebab utama dan solusi mengapa partner Anda tidak menerima postback yang diharapkan. Telusuri setiap topik di bawah ini dan lihat apakah mungkin itu penyebabnya.

<div id="check-the-integration-toggles" />

## Periksa tombol integrasi

Berbagai tombol mengendalikan berbagai bagian integrasi. Keadaan tombol bisa menjadi alasan untuk tidak menerima postback. 

<div id="the-activate-partner-toggle-was-turned-off" />

<Accordion title="Aktifkan partner dinonaktifkan">

Saat tombol <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">**Aktifkan partner**</Anchor> dinonaktifkan, konversi tidak diatribusikan dan postback tidak dikirim ke partner.

![integration_turned_off.png](https://files.readme.io/d43b4f465749e343d9523e90e87e43b77a85cdd920f0c0770a94bcb7a585d920-14979273403793.png)

**Untuk mengaktifkan integrasi:**

1. Di AppsFlyer, di bawah **Konfigurasi,** buka **Integrasi Aktif**
2. Klik ikon Kelola integrasi partner.
3. Dari tab **Integrasi**, aktifkan tombol **Aktifkan partner** .

Kasus lain mungkin jika sakelar <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">**Aktifkan partner**</Anchor> saat ini dihidupkan tetapi selama event, itu dimatikan. Gunakan log Audit untuk memeriksa dan melihat apakah integrasi partner aktif pada saat event:

* Buka email pengguna Anda (kanan atas) > **Pusat keamanan** > **Log audit**.

</Accordion>

<div id="the-inapp-event-postbacks-toggle-was-turned-off" />

<Accordion title="Postback in-app event dinonaktifkan">

Tombol **<Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration">postback in-app event</Anchor>** dinonaktifkan, atau mungkin telah dinonaktifkan selama event berlangsung. Ini berarti tidak ada postback yang dikirim.

**Untuk mengaktifkan postback In-app event:**

1. Di AppsFlyer, di bawah **Konfigurasi,** buka **Integrasi Aktif**
2. Klik ikon Kelola integrasi partner.
3. Dari tab **Integrasi** , gulir ke bawah ke sakelar **Postback in-app event** dan aktifkan.  

   ![integration-in_app_event_postbacks_toggle.png](https://files.readme.io/20dadaa71b8b54c4512e74a925e66cec9da5e8138bb28a545c5452eef2d38304-14627453566737.png)

</Accordion>

<div id="check-the-event-configuration" />

## Periksa konfigurasi event

Event dapat dikonfigurasi sedemikian rupa sehingga postback tertentu tidak dikirim.

<div id="the-event-wasnt-configured" />

<Accordion title="Event tidak dikonfigurasi">

Periksa apakah event tersebut disertakan dalam daftar in-app event yang telah dikonfigurasi. Jika tidak ditentukan, postback tidak akan dikirim.

[![list_of_in_app_events.png](https://files.readme.io/c2b3a3a87c4a1f39a3fa3acc28c736fd69d8d6d21d4b9ed5d3c84e8df0d3bf39-14979245450641.png)](https://files.readme.io/c2b3a3a87c4a1f39a3fa3acc28c736fd69d8d6d21d4b9ed5d3c84e8df0d3bf39-14979245450641.png)

1. Di AppsFlyer, di bawah **Konfigurasi** , buka **Integrasi Aktif**.
2. Klik ikon Kelola integrasi partner.
3. Dari tab **Integrasi** , gulir ke bawah ke **Postback in-app event** dan lihat apakah nama event muncul.

</Accordion>

<div id="the-event-was-configured-incorrectly" />

<Accordion title="Event dikonfigurasi dengan tidak benar">

Periksa apakah <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#pemetaan-event">pemetaan event</Anchor> sudah benar. Pastikan **event** **AppsFlyer** (nama event yang diterima oleh AppsFlyer dari aplikasi seluler Anda atau melalui S2S) cocok dengan **nama yang dipetakan ke partner** (nama event persis yang digunakan oleh partner). 

[![in_app_event_postback_mapping_2.png](https://files.readme.io/b0b4935f2b40e1c81961fbbecd159ca054816be2c58248624eed177ec17f9c20-14979366291857.png)](https://files.readme.io/b0b4935f2b40e1c81961fbbecd159ca054816be2c58248624eed177ec17f9c20-14979366291857.png)

</Accordion>

<div id="the-event-was-configured-correctly-but-with-a-condition" />

<Accordion title="Event dikonfigurasi dengan benar tetapi dengan syarat">

Jika suatu syarat ditentukan untuk acara tersebut, postback dikirim sesuai dengan syarat tersebut. Periksa apakah ada syarat yang membatasi pengiriman postback.

[![in_app_event_condition__1_.png](https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png)](https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png)

</Accordion>

<div id="the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner" />

<Accordion title="Event yang dikonfigurasi untuk mengirim postback hanya ke partner yang dikaitkan">

Periksa apakah konfigurasi in-app event diatur untuk mengirim postback ke <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#pilihan-untuk-mengirim-postback">**Partner ini saja** atau ke **Semua sumber media, termasuk organik**</Anchor>. Jika diatur ke **Hanya partner ini**, hanya partner yang dikaitkan yang mendapatkan postback.

[![in_app_event_sending_options.png](https://files.readme.io/3fd96860a0a8842dd183a29e9f9dd947b5c9082e2069c0aa74bd8eb781302908-14979359951761.png)](https://files.readme.io/3fd96860a0a8842dd183a29e9f9dd947b5c9082e2069c0aa74bd8eb781302908-14979359951761.png)

</Accordion>

<div id="the-event-occurred-outside-of-the-configuration-window" />

<Accordion title="Event tersebut terjadi di luar jendela konfigurasi">

Postback dikirim sesuai dengan pengaturan <Anchor target="_blank" href="/marketers/id/docs/in-app-event-postback-configuration#periode-waktu-postback-in-app-event">jendela postback</Anchor> . Postback untuk event setelah periode ini tidak dikirimkan ke partner, meskipun event tersebut masih dicatat di AppsFlyer.

![in_app_event_postback_window.png](https://files.readme.io/21cae7825d557c1ee89c890ec64c922cb36e31be882850a26bfdc4e5595773f0-14661845664401.png)

Perhatikan bahwa untuk <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns">SRN</Anchor>, postback in-app event dikirim selama durasi <Anchor target="_blank" href="/marketers/id/docs/user-level-data-retention#partner-data-retention-periods">periode retensi data partner</Anchor>.

</Accordion>

<div id="the-attribution-link-was-configured-not-to-send-postbacks-for-installs" />

<Accordion title="Tautan atribusi dikonfigurasi untuk tidak mengirim postback untuk penginstalan">

Saat tautan atribusi menyertakan parameter`af_installpostback=false` , penginstalan dicatat tetapi postback tidak dikirim ke partner.

**Untuk melihat tautan atribusi:**

* Di AppsFlyer, di bawah **Konfigurasi** > **Integrasi aktif**, buka tab **Tautan atribusi** dan gulir ke bawah untuk melihat tautan atribusi Anda.

</Accordion>

<div id="privacy-restrictions" />

## Pembatasan privasi

Dalam kasus berikut, AppsFlyer tidak mengirimkan postback karena pembatasan privasi.

<div id="the-partner-didnt-set-up-advanced-privacy" />

<Accordion title="Partner tidak mendukung Privasi Lanjutan atau tidak mengaturnya">

Saat <Anchor target="_blank" href="/marketers/id/docs/apply-aggregated-advanced-privacy-framework#partner-advanced-privacy-switch">Privasi Lanjutan</Anchor> diaktifkan tetapi mitra tidak mengonfigurasi Privasi Lanjutan di pihak mereka atau mereka tidak mendukung Privasi Lanjutan, mereka tidak akan menerima <Anchor target="_blank" href="/partners/id/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks">postback teragregasi Privasi Lanjutan</Anchor>. 

![partner_not_supporting_ap_postbacks.png](https://files.readme.io/1d8784e8994eba5c403ac706673490b91b7b34ed4d5dbea8c3fe58f227d382c5-15140294126353.png)

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms" />

<Accordion title="Pembatasan sumber media pada platform pihak ketiga">

<Anchor target="_blank" href="/marketers/id/docs/discrepancies-between-appsflyer-and-third-party-platforms#postback-restrictions-on-third-party-platforms">Beberapa sumber media</Anchor> membatasi pembagian data dengan pihak ketiga. AppsFlyer tidak mengizinkan pembagian data tingkat pengguna yang diperoleh melalui sumber media ini dengan platform atau layanan pihak ketiga mana pun. Oleh karena itu, semua penginstalan dari sumber media tersebut dikirim sebagai organik. Perlu diperhatikan bahwa Meta ads tidak mengizinkan pembagian data apa pun dengan platform pihak ketiga.

</Accordion>

<div id="the-sdk-was-set-not-to-share-information-with-the-partner" />

<Accordion title="SDK ditetapkan untuk tidak berbagi informasi dengan mitra">

Filter berbagi telah diterapkan di SDK untuk mencegah mitra menerima informasi. Filter ini dapat diaktifkan oleh permintaan tidak ikut serta secara eksplisit dari pengguna atau pada titik lain mana pun selama siklus hidup aplikasi.

Untuk informasi selengkapnya lihat: <Anchor target="_blank" href="/marketers/id/docs/apply-privacy-preserving-sdk-methods#cegah-berbagi-data-dengan-pihak-ketiga">Mencegah berbagi data dengan pihak ketiga</Anchor> dan <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">setSharingFilterForPartners</Anchor>.

</Accordion>

<div id="miscellaneous" />

## Aneka ragam

<div id="the-postback-was-sent-but-doesnt-show-on-the-partners-platform" />

<Accordion title="Postback telah dikirim tetapi tidak muncul di platform partner">

Dalam beberapa kasus, meskipun AppsFlyer mengirim postback ke partner, mereka tidak menampilkannya di sisi partner. Dalam kasus tersebut, hubungi partner.

**Untuk melihat apakah postback dikirim dari AppsFlyer:**

1. Di AppsFlyer, di bawah **Laporan** , buka **Ekspor Data Lengkap**.
2. Lihat laporan yang relevan di **Postback** (Penginstalan, In-app event, Konversi penargetan ulang, Penargetan ulang in-app event).

[![postback_reports.JPG](https://files.readme.io/21f7ead0f04cf8b67735476348245c5849b638701946236cf649adfa69699df6-14981466637457.png)](https://files.readme.io/21f7ead0f04cf8b67735476348245c5849b638701946236cf649adfa69699df6-14981466637457.png)

</Accordion>

<div id="the-event-didnt-occur" />

<Accordion title="Event tidak terjadi atau tidak dikirim ke AppsFlyer">

Semua peristiwa yang terjadi dapat ditemukan di <Anchor target="_blank" href="/marketers/id/docs/activity-dashboard">dashboard**Aktivitas**</Anchor> dan di <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview?query=raw%20data%20reports">Laporan data lengkap</Anchor>. Event yang tidak muncul di sana berarti tidak terjadi atau tidak dikirim ke AppsFlyer.

Bisa jadi event tersebut tidak ditentukan di SDK. Dalam hal ini, Anda tidak akan melihatnya di platform. Periksa konfigurasi SDK.  <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#merekam-in-app-event">didefinisikan dalam SDK</Anchor>.

Jika menurut Anda event tersebut terjadi, periksa di bawah cara melihat apakah peristiwa tersebut muncul di dashboard Aktivitas atau buat Laporan data lengkap dan cari di sana.

**Untuk melihat dashboard Aktivitas:**

* Di AppsFlyer, di bawah **Dashboard** , buka **Aktivitas** dan pilih partner dan rentang tanggal.

**Untuk membuat laporan data lengkap:**

1. Di AppsFlyer, di bawah **Laporan** masuk ke **Ekspor Data Lengkap**.
2. Klik **Buat laporan**.
3. Pilih laporan relevan.
4. Pilih rentang tanggal dan salah satu bidang yang diperlukan, lalu klik **Buat**.
5. Unduh laporan dan cari event di sana.

</Accordion>

<div id="differences-in-time-zones" />

<Accordion title="Perbedaan zona waktu">

Mungkin ada perbedaan dalam menerima postback karena perbedaan zona waktu antara platform AppsFlyer dan platform partner. Dashboard dan laporan AppsFlyer ditampilkan sesuai dengan zona waktu yang dipilih.

**Untuk melihat zona waktu aplikasi di AppsFlyer:**

1. Di AppsFlyer, di bawah **Konfigurasi** buka **Pengaturan aplikasi**.
2. Lihat zona waktu aplikasi di bawah **Pelokalan**.

</Accordion>

<div id="srns-missing-advertising-ids-idfagaid" />

<Accordion title="SRN tidak memiliki ID iklan (IDFA/GAID)">

Ada sejumlah <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid">kasus khusus untuk SRN</Anchor> di mana AppsFlyer tidak mengirimkan postback untuk penginstalan, pembukaan aplikasi, atau in-app event.

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms::40092c14" />

<div id="advanced-privacy-postbacks" />

<Accordion title="Pembatasan sumber media pada platform pihak ketiga">

<Anchor target="_blank" href="/marketers/id/docs/discrepancies-between-appsflyer-and-third-party-platforms#postback-restrictions-on-third-party-platforms">Beberapa sumber media</Anchor> membatasi berbagi data dengan pihak ketiga. AppsFlyer tidak dapat membagikan data tingkat pengguna yang diperoleh melalui sumber media ini dengan platform atau layanan pihak ketiga mana pun. Oleh karena itu, semua penginstalan dari sumber media tersebut dikirim sebagai organik. Perhatikan bahwa iklan Meta tidak membagikan data apa pun dengan platform pihak ketiga.

</Accordion>

<div id="see-also" />

> 📄 **Lihat juga**
>
> <Anchor target="_blank" href="/partners/id/docs/postback-troubleshooting-for-ad-networks">Pemecahan masalah postback untuk jaringan iklan</Anchor>

<div data-zendesk-anchors="activation-toggles=periksa-tombol-integrasi h_01H9FT385FY1QJC6M2YVMZF2NC=periksa-tombol-integrasi h_01H9FT385FJ0W62NB6FBB6ASKP=the-activate-partner-toggle-was-turned-off h_01H9FT385FKK7VQ293HH9RANBP=the-inapp-event-postbacks-toggle-was-turned-off event-configuration-issues=periksa-konfigurasi-event h_01H9FT385FW71JV2KKZ22TP6TN=periksa-konfigurasi-event h_01H9FT385FHFX4PNRQVRXX8A5X=the-event-wasnt-configured h_01H9FT385FE4GCP9D5XCNZ1FAR=the-event-was-configured-incorrectly h_01H9FT385FTT97PJ9NN09K0X9F=the-event-was-configured-correctly-but-with-a-condition h_01H9FT385FDEC21CAZ7V9BBT7M=the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner h_01H9FT385G8HSVJWWGKSRKT381=the-event-occurred-outside-of-the-configuration-window h_01H9FT385GDDV1D6X69JQWPN02=the-attribution-link-was-configured-not-to-send-postbacks-for-installs privacy-restrictions=pembatasan-privasi h_01H9FT385G84E2A1J64VWG8H4Z=pembatasan-privasi h_01H9FT385G3ECF0PXCE6S2GD5A=the-partner-didnt-set-up-advanced-privacy h_01H9FT385G9YMX9BAEYY0XQR4C=media-source-restrictions-on-thirdparty-platforms h_01HG0YAHWJ565C7BAXAXT75ACB=the-sdk-was-set-not-to-share-information-with-the-partner miscellaneous=aneka-ragam h_01H9FT385GSWRPKEHKJ4HXCX01=aneka-ragam h_01H9FT385GTSH1K93WNCARY2BA=the-postback-was-sent-but-doesnt-show-on-the-partners-platform h_01H9FT385G5HK6N2JEE8C6S245=the-event-didnt-occur h_01H9FT385GPVT9WAC6ZTPK6D10=differences-in-time-zones h_01H9FT385G8RXJD25KAQJ28TF6=srns-missing-advertising-ids-idfagaid h_01H9FT385GAYCY615W7M88XJT3=media-source-restrictions-on-thirdparty-platforms::40092c14 h_01HE7R6G699RG30ZSSQF02AK5Y=lihat-juga" />
