---
title: Kirim salinan postback SKAN langsung ke AppsFlyer (iOS 15+)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-06-08T12:09:25Z'
  edited_at: '2023-11-03T08:08:02Z'
  id: 4402320969617
  locale: id
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/id/articles/4402320969617
---
> **Sekilas:** Mulai iOS 15, konfigurasikan aplikasi Anda untuk mengirim salinan postback ke AppsFlyer selain mengirimnya ke jaringan iklan. Melakukan hal tersebut memungkinkan AppsFlyer untuk memvalidasi nilai konversi (CV) dan memverifikasi integritas postback. Konfigurasikan AppsFlyer Push API untuk meneruskan salinan postback ke titik akhir tambahan yang dipilih.

<div id="why-send-postback-copies-to-appsflyer" />

## Mengapa mengirim salinan postback ke AppsFlyer?

* Mendapatkan semua postback di satu tempat: Postback berisi informasi penting bagi pengiklan — khususnya, CV yang digunakan untuk mengukur kualitas pengguna. CV, dalam postback, tidak dienkripsi atau bagian dari tanda tangan postback. Akibatnya, CV seperti yang dilaporkan oleh jaringan iklan tidak dapat divalidasi dan berisiko dimanipulasi. AppsFlyer akan meneruskan salinan postback menggunakan Push API ke titik akhir yang Anda tentukan.
* Lihat metrik unduhan ulang. Beberapa jaringan iklan tidak membagikan data unduhan ulang dengan AppsFlyer. Salinan postback membantu melihat gambaran keseluruhan.
* Lihat data aplikasi penerbit
* Lihat interaksi tipe sentuhan

**Perhatikan!** AppsFlyer tetap harus menerima postback jaringan iklan karena berisi data tambahan yang disediakan oleh jaringan iklan (misalnya, nama kampanye).

<div id="important" />

<div id="configure-your-app-to-send-postback-copies-to-appsflyer" />

## Konfigurasikan aplikasi Anda untuk mengirim salinan postback ke AppsFlyer

Menurut dokumentasi Apple, Anda dapat mengatur satu titik akhir postback SKAN.

**Untuk mendaftarkan titik akhir AppsFlyer:**

1. Minta pengembang iOS Anda untuk <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#sending-skan-postback-copies-to-appsflyer">menambahkan AppsFlyer</Anchor> sebagai titik akhir postback SKAN di versi aplikasi berikutnya.
2. Kirim aplikasi iOS.
3. Postback akan dikirim ke AppsFlyer saat versi baru diterbitkan (bukan dari TestFlight).
4. Anda dapat melihat postback yang diterima di <Anchor target="_blank" href="/marketers/id/docs/skan-raw-data-reports">laporan salinan postback</Anchor>.

<div id="common-misconceptions" />

## Kesalahpahaman umum

<div id="traits-and-limitations" />

<div id="dont-believe-everything-you-hear" />

> 📘 **Jangan percaya begitu saja!**
>
> Apakah pernyataan-pernyataan ini benar atau salah?
>
> ![TrueOrFalse.png](https://files.readme.io/77212d5a12ce2af35b0a4c87ca9e58213b4f9fd88c775007793e7abb5aaa3f04-35682597298577.png)
>
> * Pemasang iklan tidak lagi bergantung pada jaringan iklan untuk mendapatkan postback.
>   * **False.** Pemasang iklan masih bergantung pada jaringan iklan untuk memecahkan kode bagian data yang signifikan. Misalnya, hanya jaringan iklan yang dapat memetakan ID kampanye SKAN ke nama kampanye.
> * Segera setelah saya menetapkan titik akhir tambahan, salinan semua postback dikirim ke sana.
>   * **False.** Fitur titik akhir tambahan hanya tersedia untuk perangkat yang menjalankan iOS 15+. Salinan postback tidak dikirim dari perangkat yang menjalankan versi sebelumnya.

<div id="see-also" />

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_an_advertised_app?changes=latest_minor#see-also">Pengembang Apple</Anchor>

<div data-zendesk-anchors="why-send-postback-copies-to-appsflyer=mengapa-mengirim-salinan-postback-ke-appsflyer h_01HE7SV29Y7DNSKAAR91MJX986=mengapa-mengirim-salinan-postback-ke-appsflyer configure-your-app-to-send-postback-copies-to-appsflyer=konfigurasikan-aplikasi-anda-untuk-mengirim-salinan-postback-ke-appsflyer h_01HE7SV29YDFA5Z0X4WS87YK0Y=konfigurasikan-aplikasi-anda-untuk-mengirim-salinan-postback-ke-appsflyer common-misconceptions=kesalahpahaman-umum h_01HE7SV29YC855TGCXTCT4KHRN=kesalahpahaman-umum h_01HE7SV29YMMTPH6EKYF3GQYEN=jangan-percaya-begitu-saja h_01HE7SX466CMCC03K99H68ZRBN=lihat-juga" />
