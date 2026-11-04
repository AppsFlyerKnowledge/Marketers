---
title: Google Ads (AdWords)—interaksi ulang
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-20T09:55:51Z'
  edited_at: '2023-10-27T14:55:06Z'
  id: 4417296925073
  locale: id
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/id/articles/4417296925073
---
> **Sekilas:** Ukur kampanye penargetan ulang Google Ads.

<div id="google-ads-retargeting-campaigns" />

## Kampanye Penargetan Ulang Google Ads

Dengan AppsFlyer, Anda dapat mengukur hasil **Kampanye Aplikasi Google Ads untuk Interaksi**.  
Di AppsFlyer, kampanye semacam ini disebut kampanye <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide">Penargetan Ulang</Anchor> . AppsFlyer mendukung fitur mendapatkan data biaya, klik, dan tayangan untuk kampanye penargetan ulang. Integrasi ini memungkinkan Anda untuk melihat dan mengukur pengeluaran iklan di Google Ads, lalu menghitung eCPI dan ROI kampanye Google Ads Anda.

Kampanye penargetan ulang itu menargetkan pengguna yang telah menginstal aplikasi Anda sebelumnya.

* Pelibatan penargetan ulang oleh pengguna, yang masih menginstal aplikasi Anda itu disebut **Pelibatan ulang**. Ini biasanya menghasilkan pengguna yang tertaut langsung.
* Pelibatan penargetan ulang oleh pengguna, yang tidak menginstal aplikasi Anda itu disebut **Instalasi ulang** atau **Atribusi ulang**.

Untuk informasi lebih lanjut, lihat <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">Dokumentasi Google Ads untuk dukungan interaksi</Anchor>.

<div id="setting-up-google-ads-app-campaigns-for-engagement" />

## Menyiapkan kampanye aplikasi Google Ads untuk pelibatan

Sebelum Anda memulai, tinjau <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001?hl=en">Petunjuk Google tentang cara membagikan tautan dengan akun Google Ads lainnya</Anchor> untuk memastikan kampanye interaksi Anda diukur dengan benar melalui ID tautan yang ada.

Untuk mengukur Kampanye Aplikasi Google Ads untuk Interaksi, ikuti tiga langkah berikut:

<div id="enabling-retargeting-in-app-settings" />

<Accordion title="Mengaktifkan Retargeting di App Settings">

Untuk mengaktifkan kampanye retargeting media source mana pun, Anda perlu mengaktifkannya di level aplikasi. Jika ini adalah kampanye retargeting pertama untuk aplikasi Anda, lakukan hal berikut:

1. Di AppsFlyer, buka **App Settings (Pengaturan Aplikasi)**.
2. Gulir (Scroll) sampai ke bawah.
3. Aktifkan **Re-engagement attribution** (atribusi interaksi ulang).

</Accordion>

<div id="enable-google-ads-retargeting-in-appsflyer" />

<Accordion title="Mengaktifkan penargetan ulang Google Ads di AppsFlyer">

* Ikuti poin #5 pada <Anchor target="_blank" href="/marketers/id/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">instruksi</Anchor> untuk mengatur Google Ads di AppsFlyer.

</Accordion>

<div id="importing-session-start-conversions-in-google-ads" />

<Accordion title="Mengimpor konversi session start di Google Ads">

Untuk merekam konversi untuk kampanye interaksi ulang **di Iklan Google** , Anda perlu mengimpor event session\_start di Iklan Google.

Event ini muncul di Google Ads jika sedikitnya satu user meluncurkan aplikasi setelah Anda mengaktifkan retargeting di AppsFlyer untuk Google Ads. Untuk memastikan event ini muncul di Google Ads, Anda dapat meluncurkan aplikasi setelah mengaktifkan retargeting.

Untuk mempelajari cara mengimpor konversi di Google Ads, lihat <Anchor target="_blank" href="/marketers/id/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">di sini</Anchor>.

<div id="note" />

> 📘 **Catatan**
>
> Tidak seperti semua event lainnya, session\_start dapat diklaim oleh Google Ads API, bahkan jika Anda tidak mengimpor session\_start ke Google Ads dari AppsFlyer.
>  Namun, dalam hal itu, konversi ini masih akan diatribusikan di AppsFlyer. Hal ini **menciptakan perbedaan besar antara data Anda di AppsFlyer dan Google Ads** . Selanjutnya, hal ini **mencegah Iklan Google dari mengoptimalkan** penargetan pengguna kampanye Anda.

</Accordion>

<div id="setting-up-deep-linking-for-app-campaigns-for-engagement" />

<Accordion title="Mengatur deep linking untuk kampanye aplikasi untuk interaksi">

Kampanye Aplikasi Google untuk Interaksi mengharuskan Anda untuk <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6310747?hl=en&ref_topic=3121770">menggunakan deep link untuk kampanye interaksi ulang</Anchor>. Solusi tautan langsug pihak ketiga tidak dapat digunakan karena ketidakcocokan domain. Ini termasuk OneLink AppsFlyer. Gunakan <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6046977?hl=en">Tautan Aplikasi internal, Tautan Universal, atau skema URI khusus</Anchor> Anda sendiri.

Anda tidak perlu menambahkan parameter tambahan apa pun ke deep link (is\_retargeting=true dan pid=adwords tidak diperlukan).

</Accordion>

<div id="dynamic-remarketing-and-shopping-campaigns" />

## Pemasaran ulang dinamis dan kampanye belanja

Pemasaran ulang dinamis untuk aplikasi dan kampanye belanja didukung di AppsFlyer. Platform AppsFlyer memperlakukan mereka sama seperti kampanye interaksi ulang lainnya.

Untuk mempelajari tentang Pemasaran ulang dinamis untuk aplikasi, klik <Anchor target="_blank" href="https://support.google.com/adwords/answer/7538938">di sini</Anchor>.  
 Untuk mempelajari tentang Kampanye belanja, klik <Anchor target="_blank" href="https://support.google.com/google-ads/answer/2454022?hl=en">di sini</Anchor>.  
 Untuk mempelajari lebih lanjut tentang Google Ads untuk Interaksi klik <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">di sini</Anchor>.

<div id="see-also" />

> 📄 **Lihat juga**
>
> * Untuk pertimbangan terkait iOS 14, lihat <Anchor target="_blank" href="/marketers/id/docs/get-skan-postback-data-from-google-ads">Interoperabilitas SKAdNetwork Google Ads dengan AppsFlyer</Anchor>.

<div data-zendesk-anchors="google-ads-retargeting-campaigns=kampanye-penargetan-ulang-google-ads h_01HDP34BWZFG09ABN5NQB6EY32=kampanye-penargetan-ulang-google-ads setting-up-google-ads-app-campaigns-for-engagement=menyiapkan-kampanye-aplikasi-google-ads-untuk-pelibatan h_01HDP34BWZXXNZDE0SR4MXBC9V=menyiapkan-kampanye-aplikasi-google-ads-untuk-pelibatan h_01HDP34BWZNHY08NDX6YSE9CXR=enabling-retargeting-in-app-settings h_01HDP34BWZNNNT4HRMXJB2X3S2=enable-google-ads-retargeting-in-appsflyer h_01HDP34BWZ8MGJKEZFC77VYWNG=importing-session-start-conversions-in-google-ads h_01HDP34BWZHWVKKNB7CEHY73R0=catatan h_01HDP34BWZ64XG2G0PTH6XCCMG=setting-up-deep-linking-for-app-campaigns-for-engagement dynamic-remarketing-and-shopping-campaigns=pemasaran-ulang-dinamis-dan-kampanye-belanja h_01HDP34BWZ990SD3B1C5DZRESK=pemasaran-ulang-dinamis-dan-kampanye-belanja h_01HDP2XBSEJVQ5G0MD0V5R05CM=lihat-juga" />
