---
title: Pemetaan in-app event iklan Meta
metadata:
  keywords:
    - Facebook
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
  created_at: '2021-11-09T09:57:19Z'
  edited_at: '2023-08-04T16:54:36Z'
  id: 4410480904081
  locale: id
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/id/articles/4410480904081
---
> **Sekilas:** Kirimkan rich in-app event dari aplikasi Anda dari AppsFlyer ke Meta ads.

## Pemetaan in-app event Meta

Pemasang iklan memetakan in-app event mereka, SDK atau Server-ke-server, ke event Meta yang telah ditentukan sebelumnya. Pemasang iklan juga dapat mengirimkan postback ke Meta tentang setiap <Anchor target="_blank" href="/marketers/id/docs/measure-sessions">peluncuran aplikasi</Anchor> atau setiap <Anchor target="_blank" href="/marketers/id/docs/measure-uninstalls#memetakan-event-uninstall">unistall aplikasi</Anchor> yang diketahui.

Hal ini memungkinkan pemasang iklan untuk memanfaatkan kemampuan optimisasi tingkat lanjut Meta serta membangun segmen Audiens Khusus dan Serupa.

### Pemetaan event yang telah ditentukan sebelumnya

Meta ads menawarkan <Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/getting-started-app-events-android#event-names">berbagai macam event</Anchor> yang sudah ditentukan sebelumnya dan dapat dipetakan.

Temukan <Anchor target="_blank" href="/marketers/id/docs/in-app-events-event-structure">di sini</Anchor> daftar **rich in-app event**, yang dapat dikirim ke Meta dengan parameter tambahan yang menyediakan **informasi tambahan tentang kualitas event**.

Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/meta-ads-integration-setup#inapp-event-mapping">memetakan event di Meta</Anchor>.

[![In-app_event_postbacks_en-us.png](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)

Perhatikan bahwa tidak ada event yang ditentukan sebelumnya untuk mengirimkan uninstall ke Meta ads. Untuk mengirim uninstall, gunakan [event khusus](/docs/meta-ads-in-app-event-mapping#pemetaan-in-app-event-personalisasi).

Berikut adalah daftar event Meta lain yang telah ditentukan sebelumnya, yang tidak memiliki parameter tambahan:

| Pengidentifikasi event Meta | Deskripsi | Nama SDK AppsFlyer yang direkomendasikan |
| --- | --- | --- |
| Donasi | Sumbangan dana untuk organisasi atau kegiatan pemasaran Anda. | af\_donate |
| Jadwal | Pembuatan janji temu untuk mengunjungi salah satu lokasi Anda. | af\_schedule |
| AjukanAplikasi | Pengajuan aplikasi untuk produk, layanan, atau program yang Anda tawarkan, seperti kartu kredit, program pendidikan, atau pekerjaan. | af\_submit\_application |
| TemukanLokasi | Ketika seseorang menemukan salah satu lokasi Anda via web atau aplikasi, dengan niat untuk mengunjungi. Misalnya, mencari produk dan menemukannya di salah satu toko lokal Anda. | af\_find\_location |
| Kontak | Telepon atau SMS, email, obrolan, jenis kontak lainnya antara pelanggan dan bisnis Anda. | af\_contact |
| SesuaikanProduk | Kustomisasi produk melalui alat konfigurasi atau aplikasi lain yang dimiliki bisnis Anda. | af\_customize\_product |

### Pemetaan In-App Event Personalisasi

AppsFlyer memungkinkan Anda untuk memetakan in-app event khusus mana pun untuk dikirim ke Meta, dengan menggunakan opsi Pengidentifikasi Event Meta KHUSUS.

Nama event dan nilai event (termasuk parameter event) yang dikonfigurasi di SDK diteruskan ke Meta, sebagaimana adanya, dan ditampilkan dengan nama event SDK AppsFlyer aslinya - bukan sebagai "custom" (khusus).

Perhatikan bahwa Anda dapat <Anchor target="_blank" href="https://www.facebook.com/business/help/2308889442692949?id=1716638325041491">menggunakan event ini untuk mengoptimalkan kampanye Anda</Anchor>.

[![](https://files.readme.io/b41d1fa6c42284db9992260e58083bc2ef46ee3e98dbe4e063cdb28883553471-37750368969233.png)](https://files.readme.io/b41d1fa6c42284db9992260e58083bc2ef46ee3e98dbe4e063cdb28883553471-37750368969233.png)

### Pemetaan Parameter Otomatis dengan CUSTOM Event

Melalui integrasi yang menyeluruh AppsFlyer dengan Meta, beberapa parameter event SDK standar AppsFlyer secara otomatis dipetakan ke parameter Meta yang telah ditentukan sebelumnya. Misalnya, parameter **af\_revenue** diubah menjadi parameter **\_valueToSum** di Meta, yang memungkinkan Anda mengirimkan pendapatan per event yang dapat diukur dan dioptimalkan di Meta.

> 📘 **Catatan**
>
> Pemetaan parameter otomatis dapat berbeda antara event KUSTOM dan yang ditetapkan sebelumnya.
>
> Untuk <Anchor target="_blank" href="/marketers/id/docs/in-app-events-event-structure">event yang ditetapkan sebelumnya</Anchor>, **af\_price** dipetakan ke **\_valueToSum** dalam beberapa kasus (misalnya, `fb_mobile_add_to_cart`). Dalam kasus lain, **af\_revenue** dipetakan ke **\_valueToSum** (misalnya, dalam `fb_mobile_purchase`).
>
> Untuk event yang dipetakan ke KUSTOM, **af\_price** selalu dipetakan ke **fb\_price**, dan **af\_revenue** ke **\_ valueToSum**.

Tabel berikut memerinci semua parameter event AppsFlyer, yang saat dipetakan melalui event KHUSUS ke Meta akan secara otomatis dipetakan ke parameter Meta.

| Parameter AppsFlyer | Parameter Meta |
| --- | --- |
| af\_city | fb\_city |
| af\_class | fb\_travel\_class |
| af\_content\_id | fb\_content\_id |
| af\_content\_list | fb\_content\_id |
| af\_content\_type | fb\_content\_type |
| af\_country | fb\_country |
| af\_currency | fb\_currency |
| af\_date\_a | fb\_checkin\_date |
| af\_date\_b | fb\_checkout\_date |
| af\_departing\_arrival\_date | fb\_departing\_arrival\_date |
| af\_departing\_departure\_date | fb\_departing\_departure\_date |
| af\_description | fb\_description |
| af\_destination\_a | fb\_origin\_airport |
| af\_destination\_b | fb\_destination\_airport |
| af\_destination\_list | fb\_destination\_ids |
| af\_hotel\_score | fb\_hotel\_score |
| af\_level | fb\_level |
| af\_max\_rating\_value | fb\_max\_rating\_value |
| af\_num\_adults | fb\_num\_adults |
| af\_num\_children | fb\_num\_children |
| af\_num\_infants | fb\_num\_infants |
| af\_order\_id | fb\_order\_id |
| af\_payment\_info\_available | fb\_payment\_info\_available |
| af\_preferred\_neighborhoods | fb\_preferred\_neighborhoods |
| af\_preferred\_num\_stops | fb\_preferred\_num\_stops |
| af\_preferred\_price\_range | fb\_preferred\_price\_range |
| af\_preferred\_star\_ratings | fb\_preferred\_star\_ratings |
| af\_price | fb\_price |
| af\_quantity | fb\_num\_items |
| af\_region | fb\_region |
| af\_registration\_method | fb\_registration\_method |
| af\_returning\_arrival\_date | fb\_returning\_arrival\_date |
| af\_returning\_departure\_date | fb\_returning\_departure\_date |
| af\_revenue | \_valueToSum |
| af\_search\_string | fb\_search\_string |
| af\_success | fb\_success |
| af\_suggested\_destinations | fb\_suggested\_destinations |
| af\_suggested\_hotels | fb\_suggested\_hotels |
| af\_travel\_end | fb\_travel\_end |
| af\_travel\_start | fb\_travel\_start |
| af\_user\_score | fb\_user\_score |

## Batasan Event dan Parameter

Batasan berikut berlaku untuk [event yang Anda kirim ke Meta ads](https://developers.facebook.com/docs/app-events/faq#limits):

* Karakter berikut tidak diizinkan:
  * Titik dua (:)
  * Titik (.)
  * Kumpulan karakter non-Latin (Inggris): Mulai 12 Januari 2020, Meta menolak karakter Mandarin. AppsFlyer belum menguji set karakter lain dan Anda harus menggunakannya hanya setelah memverifikasi dengan Meta apakah mereka mendukung set karakter ini di postback atau tidak.
* Nama event peka huruf besar-kecil. Untuk menghindari perbedaan, pastikan Anda menggunakan huruf yang benar dalam nama event untuk semua sumber media dan versi aplikasi.
* Jumlah maksimum parameter: 25.
* Panjang nama dan parameter event: 2–40.
* Panjang parameter maksimum: 100 karakter.
* Karakter yang diizinkan: Karakter alfanumerik, garis bawah, tanda hubung, atau spasi. Jangan gunakan karakter non-Latin (Inggris). Menggunakan huruf non-Latin menghasilkan hasil yang tidak konsisten.

Pertimbangan terkait penamaan in-app event:

* Nama event di AppsFlyer dapat dinamakan sama dengan nama event Meta (misalnya, fb\_price), namun, ini tidak boleh dikirim sebagai event KHUSUS ke Meta.  
  **Untuk menjaga keamanan, jangan menamakan event sama dengan nama event Meta .**
* Untuk melakukan pemetaan postback in-app event dengan Meta, dapatkan data event dari semua sumber, termasuk organik.

> 🚧 **Penting!**
>
> Dengan pengecualian parameter di atas, AppsFlyer mengirimkan data event KHUSUS **sebagaimana adanya** ke Meta. Pemilik aplikasi bertanggung jawab untuk memverifikasi data event sesuai dengan persyaratan Meta , menggunakan parameter Meta yang valid (lihat tabel di atas). Jika tidak, parameter ini tidak dikirim ke Meta.

<div data-zendesk-anchors="facebook-iae-mapping=pemetaan-in-app-event-meta predefined-event-mapping=pemetaan-event-yang-telah-ditentukan-sebelumnya custom-inapp-events-mapping=pemetaan-in-app-event-personalisasi automatic-parameter-mapping-with-the-custom-event=pemetaan-parameter-otomatis-dengan-custom-event event-and-parameter-limitations=batasan-event-dan-parameter" />
