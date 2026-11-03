---
title: Bidang ID pengguna pelanggan/customer user ID field (CUID)
metadata:
  keywords:
    - ID
    - Customer User ID
    - User
    - Mixpanel
    - Swrve
    - Advertisers
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
  created_at: '2015-11-18T11:55:22Z'
  edited_at: '2023-11-28T04:51:31Z'
  id: 207032016
  locale: id
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/id/articles/207032016
---
> **Sekilas:** CUID memungkinkan Anda untuk mengelompokkan event dari pengguna yang sama di berbagai perangkat, sumber media, atau kanal.

## **Apa itu CUID?**

ID Pengguna Pelanggan (CUID) adalah  pengidentifikasi pengguna unik. Biasanya CUID dibuat dan diatur oleh pemilik aplikasi pada saat pendaftaran pengguna. CUID memungkinkan pemilik aplikasi mengikuti perjalanan pengguna di berbagai perangkat.

> 📄 **Contoh**
>
> Pengguna dengan dua perangkat atau lebih memiliki CUID yang sama dalam aplikasi. Setiap kali pengguna melakukan event di perangkat seluler atau desktop, acara tersebut direkam bersama dengan CUID. Hal ini memungkinkan pemasang iklan untuk menggabungkan data perangkat menjadi tampilan pengguna yang holistik.
>
> Beberapa kasus penggunaan:
>
> * Pembelian dalam aplikasi yang dilakukan oleh pengguna yang sama di aplikasi yang sama tetapi di beberapa perangkat (ponsel, tablet, TV, desktop) dapat digabungkan dalam satu tampilan.
> * Performa pengguna dalam game yang diinstal di berbagai platform (desktop, seluler, TV) dapat dibagikan di seluruh platform ini untuk mencapai pengalaman pengguna yang holistik.

## **Mengatur CUID**

Direkomendasikan untuk menyetel CUID sedini mungkin dalam alur inisialisasi SDK sehingga sebanyak mungkin event mendapatkan asosiasi CUID.

<Tabs>
<Tab title="Android asli">

Setelah CUID tersedia, Anda dapat mengaturnya dengan memanggil `setCustomerUserID`. CUID hanya dapat diasosiasikan dengan in-app event yang terjadi setelah CUID ditetapkan. Oleh karena itu, event penginstalan tidak akan diasosiasikan dengan CUID saat  `start` dipanggil sebelum `setCustomerUserID`.

### **Kaitkan CUID dengan acara penginstalan**

Jika penting bagi Anda untuk mengasosiasikan event penginstalan ke CUID, Anda harus mengaturnya sebelum menghubungi `start`.

**Penting:** Ingatlah bahwa mengatur CUID sebelum `start` dapat mencegah SDK mengirimkan event penginstalan dan dengan demikian mencegah terjadinya atribusi. Hal ini dapat terjadi, misalnya, saat pengguna meluncurkan aplikasi untuk pertama kalinya lalu keluar sebelum SDK dapat mengatur CUID.

Di Android, metode `start` dan penyiapan CUID dapat dijalankan dari kelas `Aplikasi` global atau kelas `Activitas` , bergantung pada implementasi aplikasi. Untuk informasi selengkapnya, lihat <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#pilih-di-kelas-apa-untuk-memulai-sdk">Pilih di kelas mana untuk memulai SDK</Anchor>.

#### Jika SDK dimulai di kelas Aplikasi

Jika Anda ingin mengasosiasikan CUID dengan  event penginstalan saat memulai dari kelas `Aplikasi`global, pastikan untuk menunda pengiriman event penginstalan menggunakan metode  `waitForCustomerUserId` . Metode ini menempatkan SDK pada mode menunggu hingga CUID diatur.

Catatan:  Jika karena alasan tertentu pengaturan CUID gagal, SDK akan tetap dalam mode menunggu dan tidak mengirimkan event apa pun.

#### Jika SDK dimulai di kelas Aktivitas

Jika Anda ingin mengasosiasikan CUID dengan event  penginstalan saat memulai dari kelas `Aktivitas` , Anda tidak perlu menunda pengiriman event penginstalan. Cukup hubungi `setCustomerUserId` sebelum memanggil `start`.

#### INSTRUKSI PENGEMBANG

Beri tahu programmer tentang hal berikut ini:

* Gunakan `waitForCustomerUserId` jika SDK dimulai di kelas `Aplikasi` global
* Tautan programmer:
  * Jika Anda ingin mengasosiasikan CUID dengan event penginstalan, lihat [di sini](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#associate-the-cuid-with-the-install-event).

</Tab>

<Tab title="iOS asli">

Gunakan metode `customerUserId` untuk mengatur CUID. Lokasi  `customerUserId`  dalam kaitannya dengan `metode start` menentukan event apa yang dapat dikaitkan dengan CUID.

* Jika `customerUserId` dipanggil sebelum memanggil `mulai`, CUID dikaitkan dengan penginstalan dan in-app event berikut ini
* Jika dipanggil setelah  `start (mulai)`, CUID hanya dikaitkan dengan event yang dicatat setelah penyetelan CUID.

#### INSTRUKSI PENGEMBANG

Rujuk pengembang Anda ke [Mengatur ID Pengguna Pelanggan](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#setting-the-customer-user-id) di Dev Hub.

</Tab>

<Tab title="Unity">

#### INSTRUKSI PENGEMBANG

Rujuk pengembang Anda ke [Mengatur ID Pengguna Pelanggan](https://dev.appsflyer.com/hc/docs/basicintegration#set-customer-user-id) di Dev Hub.

</Tab>

<Tab title="React Asli">

#### INSTRUKSI PENGEMBANG

Rujuk pengembang Anda ke referensi API [setCustomerUserId](https://dev.appsflyer.com/hc/docs/rn_api#setcustomeruserid) di Dev Hub.

</Tab>
</Tabs>

## **CUID dan privasi**

AppsFlyer menghargai dan menghormati privasi pengguna Anda dan [tidak mengizinkan pengumpulan atau transfer data pribadi sensitif ke platform AppsFlyer.](https://www.appsflyer.com/services-privacy-policy/#engagementinformation)

Untuk mengamankan privasi pengguna Anda, tidak diperbolehkan merancang CUID dengan informasi yang mengidentifikasi pengguna secara langsung. Ini termasuk nomor jaminan sosial atau nomor identifikasi nasional.

Selain itu, jika CUID yang diatur berisi alamat email atau nomor telepon pengguna,  informasi tersebut harus selalu di-hash saat dikirim ke AppsFlyer. Dilarang mengirimkan CUID yang berisi data pribadi tanpa hash ke AppsFlyer.

> 📄 **Lihat juga**
>
> * <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview#laporan-perjalanan-pengguna">Laporan perjalanan pengguna</Anchor> (untuk mengetahui lebih banyak tentang CUID dalam laporan data lengkap)
> * <Anchor target="_blank" href="https://support.google.com/analytics/answer/6366371?hl=en">Praktik terbaik Google untuk menghindari pengiriman PII</Anchor>

<div data-zendesk-anchors="what-is-cuid=apa-itu-cuid h_01HAJ00DVHRSDBS4FFKM16JFER=apa-itu-cuid h_01HAJ00DVHZ8V8MRAXN2W3T8DS=contoh setting-the-cuid=mengatur-cuid h_01HAJ00DVHDGM133A72HD5JXER=mengatur-cuid associate-the-cuid-with-the-install-event=kaitkan-cuid-dengan-acara-penginstalan h_01HAJ00DVHDE9V2MT6JQF8SAH3=kaitkan-cuid-dengan-acara-penginstalan if-the-sdk-starts-in-the-application-class=jika-sdk-dimulai-di-kelas-aplikasi h_01HAJ00DVH746B6YJVF70PMZJ8=jika-sdk-dimulai-di-kelas-aplikasi if-the-sdk-starts-in-an-activity-class=jika-sdk-dimulai-di-kelas-aktivitas h_01HAJ00DVHYZBER40RJH0GM8KF=jika-sdk-dimulai-di-kelas-aktivitas developer-instructions-android=instruksi-pengembang h_01HAJ00DVHZBZCRA1VGYJY44VY=instruksi-pengembang developer-instructions::31dbab4b=instruksi-pengembang h_01HAJ00DVH2RV902D6G224A4QY=instruksi-pengembang developer-instructions-unity=instruksi-pengembang h_01HCT1MKQWSJZ9MQTA9B1GJFWQ=instruksi-pengembang developer-instructions-react=instruksi-pengembang cuid-and-privacy=cuid-dan-privasi h_01HAJ00DVH4987JGZZVDA1NB29=cuid-dan-privasi h_01HE7RXTEPQAWV03276TDEPG0V=lihat-juga" />
