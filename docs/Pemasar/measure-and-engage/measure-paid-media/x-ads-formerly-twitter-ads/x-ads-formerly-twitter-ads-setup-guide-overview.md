---
title: Panduan pengaturan X Ads (sebelumnya Twitter Ads)—ikhtisar
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
  created_at: '2021-11-09T09:31:36Z'
  edited_at: '2023-11-24T13:19:01Z'
  id: 4410464316049
  locale: id
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/id/articles/4410464316049
---
> **Sekilas:** Pelajari latar belakang integrasi akun X Ads Anda dengan AppsFlyer.

<Image align="center" alt="X Ads logo.png" src="https://files.readme.io/cecae90650321943ad1cb6d22b7f27d3d28b0484f1706cb1be1a19099dfbb20d-20375448207377.png" width="167px" />

<div id="mobile-app-promotion-on-x-ads" />

## Promosi aplikasi seluler di X Ads

Promosi Aplikasi Seluler X Ads adalah metode untuk mempromosikan aplikasi di X Ads. Ini memungkinkan pemasang iklan untuk mempromosikan aplikasi seluler mereka dengan desain kartu Aplikasi yang bagus yang mendorong penginstalan, interaksi aplikasi, dan tautan langsung. Pengguna aplikasi dapat dengan mudah menginstal dan berinteraksi dengan aplikasi, langsung dari timeline X Ads.

<div id="x-ads-user-privacy" />

## Privasi pengguna X Ads

Pengguna X Ads dapat mengontrol cara mereka berbagi informasi dengan pemasang iklan:

* Jika pengaturan pengguna diatur untuk mencegah berbagi informasi interaksi mereka dengan pemasang iklan, penginstalan yang diarahkan oleh X Ads dan in-app event mereka dihilangkan dari data lengkap tetapi masih diatribusikan ke X Ads.
* Data atribusi gabungan direfleksikan dengan benar di AppsFlyer dan tidak terpengaruh oleh kebijakan X Ads.
* Akibatnya, laporan gabungan dan data langsung X Ads tidak berkorelasi.

Mulai 31 Juli 2021, pemasang iklan yang tidak mengikuti program Pengukuran Seluler Lanjutan (AMM) X Ads akan berhenti menerima semua data tingkat pengguna MACT X Ads.

Melalui Program AMM, pemasang iklan dapat menerima data tingkat pengguna yang lebih lengkap setelah memberikan izin kepada X Ads untuk melakukan audit guna memastikan bahwa data X Ads digunakan secara eksklusif untuk tujuan pengukuran. Hal ini sesuai dengan undang-undang perlindungan data yang berlaku dan praktik umum di seluruh industri.  
**Untuk bergabung dengan program AMM:** Buka ads.twitter.com/help > **Aplikasi Seluler, Pelacakan Konversi, & Manajer Audiens,** dan pilih **Formulir Perjanjian Program Pengukuran Seluler Lanjutan**.

Perhatikan bahwa data tingkat pengguna yang diterima sebelum bergabung dengan program AMM, tidak dapat diekspor.

Untuk informasi lebih detail, hubungi Manajer Akun X Ads Anda.

<div id="x-ads-and-appsflyer-skan-interoperation" />

## Interoperasi SKAN X Ads dan AppsFlyer

X Ads mengirimkan data postback SKAdNetwork melalui API khusus. Data SKAN dari X Ads akan ditampilkan di <Anchor target="_blank" href="/marketers/id/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">dashboard SKAN</Anchor>.

X Ads memperkaya postback SKAN dengan bidang data berikut:

* Nama kampanye
* ID kampanye
* Nama Adset
* ID adset

<div data-zendesk-anchors="mobile-app-promotion-on-twitter=promosi-aplikasi-seluler-di-x-ads h_01H9QR6TH7M0H5YMXRWVVAYRK9=promosi-aplikasi-seluler-di-x-ads twitter-user-privacy=privasi-pengguna-x-ads h_01H9QR6TH74R50K00H7FYN61KC=privasi-pengguna-x-ads twitter-ads-and-appsflyer-skan-interoperation=interoperasi-skan-x-ads-dan-appsflyer h_01H9QR6TH74PKBGM5RC4M118GE=interoperasi-skan-x-ads-dan-appsflyer" />
