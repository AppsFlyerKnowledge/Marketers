---
title: 'Buletin: Verifikasi kepemilikan aplikasi Meta ads'
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-04-12T09:40:58Z'
  edited_at: '2023-11-27T05:34:05Z'
  id: 5410285239313
  locale: id
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/id/articles/5410285239313
---
| **Tanggal buletin** | 7 April 2022 |
| --- | --- |
| **Kabar terbaru** | **<span id="h_01HG5TS8MTCHDMF3J56ADXX466"></span>Penting!**<br />Mulai paruh pertama tahun 2023, semua pemilik aplikasi akan diwajibkan untuk mengonfirmasi kepemilikan aplikasi seluler Android atau iOS apa pun, untuk aplikasi baru dan **yang sudah ada** . Jika kepemilikan aplikasi belum dikonfirmasi, pengiklan tidak akan dapat mengoptimalkan iklan aplikasi mereka untuk pemasangan aplikasi seluler.<br /><br /><br /><br />Mulai 7 April 2022, pemilik aplikasi dari aplikasi baru yang ditambahkan ke Meta ads (sebelumnya Meta ads) akan diwajibkan untuk mengonfirmasi kepemilikan mereka atas aplikasi tersebut. Perubahan ini berlaku untuk semua platform periklanan Meta seperti FB, IG, Messenger, FAN, dll., dan untuk semua sistem operasi.<br /><br />**Jika kepemilikan tidak dikonfirmasi, pemasang iklan dapat kehilangan akses platform atau gangguan aplikasi lainnya, dan tidak akan dapat:**<ul><li>**Menjalankan tujuan kampanye Penginstalan Aplikasi Seluler**</li><li>**Mengoptimalkan penayangan iklan aplikasi mereka untuk penginstalan aplikasi seluler**</li></ul> |
| **Apa yang harus saya lakukan?** | Meta ads mewajibkan pemasang iklan yang menambahkan aplikasi baru atau mengedit aplikasi yang ditambahkan setelah tanggal 7 April, untuk mengonfirmasi kepemilikan aplikasi mereka. Langkah pertama adalah memperbarui<br />file app-ads.txt di domain situs web yang tercantum dalam listing app store Anda. Lalu, buka Dashboard Aplikasi Meta untuk Pengembang, masukkan ID aplikasi Anda, dan konfirmasikan kepemilikan Anda.<br />Meta ads akan memverifikasi bahwa file app-ads.txt Anda ada di URL domain yang diberikan dan mengonfirmasi kepemilikan aplikasi.<ul><li>**Lihat <Anchor target="_blank" href="https://www.facebook.com/business/help/441531361057663">petunjuk terperinci</Anchor> untuk mengonfirmasi kepemilikan aplikasi.**</li><li>**Lihat <Anchor target="_blank" href="https://developers.facebook.com/docs/audience-network/optimization/best-practices/troubleshoot-app-ads">panduan pemecahan masalah</Anchor> untuk masalah pada app-ads.txt.**</li><li>**Pelajari lebih lanjut tentang <Anchor target="_blank" href="https://iabtechlab.com/wp-content/uploads/2019/03/app-ads.txt-v1.0-final-.pdf?fbclid=IwAR2U1W8QXLcH3OGdB-yLpkH6irqyCijwhYH-gf52BbsRHUu3hpnS4IDlWac">spesifikasi yang diwajibkan untuk app-ads.txt</Anchor>.**</li></ul> |
| **Pertanyaan Umum** | <ul><li>**Apakah saya masih dapat mengiklankan aplikasi jika saya belum mengautentikasinya?**<br />Satu-satunya cara untuk terus mengiklankan aplikasi yang tidak diautentikasi yang dikirimkan setelah tanggal 7 April adalah dengan menambahkan tautan toko aplikasi terkait dan tidak mengoptimalkan pemasangan aplikasi. Autentikasi aplikasi hanya membatasi penggunaan pengoptimalan penginstalan aplikasi, bukan iklan secara keseluruhan.</li><li>**Apakah saya harus memublikasikan ulang SDK saya di Play Store atau App Store setelah menambahkan app-ads.txt?**<br />Ya, pemilik aplikasi harus memperbarui listing toko aplikasinya di Play Store (Android) dan App Store (iOS) setelah menambahkan app-ads.txt ke situs web pengembangnya karena listing toko aplikasi perlu diperbarui menjadi situs web pengembang baru. Ini hanya diwajibkan jika situs web pengembang sebelumnya tidak terdaftar di listing toko aplikasi. Catatan: Ini bukan persyaratan di App Store atau Play Store. Persetujuan listing app store memerlukan waktu sekitar 1 minggu.</li></ul> |