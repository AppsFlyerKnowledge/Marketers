---
title: Memulai—Orientasi untuk pemasar
metadata:
  keywords:
    - SDK
    - Integration
    - Reports
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2015-01-18T11:03:01Z'
  edited_at: '2024-01-16T11:41:05Z'
  id: 207033486
  locale: id
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/id/articles/207033486
---
> **Sekilas:** Siapkan semuanya untuk memaksimalkan akun AppsFlyer Anda. Pahami langkah-langkah, garis waktu, dan dependensi untuk mengintegrasikan aplikasi dan tim Anda.

<Embed title="Memulai—Orientasi untuk pemasar" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/gamcb25kgu" providerUrl="https://fast.wistia.com" />

## Pengantar

Dokumen ini membantu pengiklan (pemilik aplikasi) manajer produk **merencanakan dan menerapkan integrasi mereka dengan AppsFlyer**. Untuk setiap item, pemilik dan perkiraan waktu implementasi disediakan.

Perhatikan bahwa perkiraan waktu dalam artikel ini hanya dimaksudkan sebagai pedoman umum. Perkiraan ini didasarkan pada pengalaman kami bekerja dengan banyak pelanggan baru, tetapi kami menyadari bahwa masing-masing pemilik aplikasi, aplikasi, dan penerapannya berbeda. Persyaratan waktu Anda yang sebenarnya mungkin berbeda.

## Pengaturan akun

**Admin akun** harus menyelesaikan langkah-langkah berikut ini:

| Langkah | Waktu | Komentar |
| --- | --- | --- |
| <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Mendaftar</Anchor> ke AppsFlyer | 5 menit | Idealnya, admin akun adalah pengguna AppsFlyer asli yang dapat menerima pesan penting saat dibutuhkan. |
| <Anchor target="_blank" href="/marketers/id/docs/user-management#creating-users">Tambahkan pengguna akun</Anchor> yang akan menggunakan dasbor AppsFlyer, dan atur izinnya | 1 menit per pengguna akun | <Anchor target="_blank" href="/marketers/id/docs/user-management#creating-users">Dalam beberapa kasus</Anchor>, pengguna dapat ditambahkan ke beberapa akun. |

**Hasil:** Selamat datang! Anda sekarang memiliki akun AppsFlyer aktif dan pengguna akun yang dapat mengaksesnya.

> 👍 **Tips**
>
> Baru mengenal AppsFlyer dan ingin tahu apa saja fitur-fiturnya?<Anchor target="_blank" href="/marketers/id/docs/welcome-to-appsflyer#apa-yang-anda-bisa-lakukan-dengan-appsflyer">Tonton video yang berdurasi 6 menit ini</Anchor>.

## Orientasi aplikasi

**Langkah 1-3 berikut wajib untuk setiap aplikasi** yang ditambahkan ke AppsFlyer (kecuali jika dinyatakan sebagai opsional).

Anda dapat mengikuti langkah-langkahnya menggunakan panduan ini atau melalui halaman orientasi aplikasi (hanya untuk aplikasi Android dan iOS). Halaman orientasi Aplikasi memandu Anda melalui langkah-langkah dasar yang diperlukan agar aplikasi Anda siap untuk atribusi. Jika Anda lebih suka menggunakannya, kami sarankan agar Anda juga h-memeriksa panduan ini untuk mengetahui langkah-langkah tambahan yang mungkin Anda perlukan untuk kebutuhan spesifik bisnis Anda.

**Untuk membuka halaman orientasi aplikasi:**

1. Di bilah menu, klik menu pengguna (tarik-turun alamat email)
2. Pilih Orientasi aplikasi

## Langkah 1: Pengaturan aplikasi

**Admin akun** harus menyelesaikan langkah-langkah berikut untuk setiap aplikasi Anda:

| Langkah | Waktu | Komentar |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/id/docs/adding-an-app-to-appsflyer">Tambahkan aplikasi Anda</Anchor> ke akun AppsFlyer | 1 menit | Jika penambahan aplikasi gagal, ini biasanya karena aplikasi tersebut sebelumnya ditetapkan di akun yang berbeda (biasanya biro iklan tempat pemasar Anda bekerja). Hubungi CSM Anda atau hello@appsflyer.com untuk <Anchor target="_blank" href="/marketers/id/docs/transferring-apps-between-accounts">mentransfer aplikasi ke akun Anda</Anchor>.<br /><br />Lihat <Anchor target="_blank" href="/marketers/id/docs/adding-an-app-to-appsflyer#troubleshooting">langkah-langkah penyelesaian masalah</Anchor> tambahan untuk menambahkan aplikasi. |
| Setel <Anchor target="_blank" href="/marketers/id/docs/adding-an-app-to-appsflyer#enter-additional-information-not-applicable-to-web-apps">zona waktu aplikasi, mata uang</Anchor>, dan apakah ditujukan untuk anak-anak | 1 menit |  |
| Setel  <br /><Anchor target="_blank" href="/marketers/id/docs/set-up-re-attribution-window">jendela atribusi ulang aplikasi</Anchor> (di halaman <Anchor target="_blank" href="/marketers/id/docs/app-settings#reattribution-window">Pengaturan aplikasi</Anchor>) | 1 menit | Jendela atribusi ulang adalah periode, mulai dari tanggal penginstalan pertama, selama **penginstalan ulang dari perangkat yang sama tidak diatribusikan** sebagai penginstalan baru. Nilai defaultnya adalah 90 hari, yang dapat Anda sesuaikan sesuai kebutuhan. |
| [Opsional] Migrasikan perangkat pengguna yang ada ke AppsFlyer | 2 jam | Jika aplikasi Anda sudah memiliki basis pengguna yang substansial, pertimbangkan <Anchor target="_blank" href="/marketers/id/docs/migration-to-appsflyer-from-other-vendors#migrasi-perangkat---opsional">untuk memigrasikan mereka ke AppsFlyer</Anchor> untuk menghindari tagihan ganda.<br /><br />**Catatan:** Dengan bantuan CSM AppsFlyer Anda atau tim dukungan di [hello@appsflyer.com](mailto:hello@appsflyer.com)). |

**Hasil:** Aplikasi Anda sekarang ditentukan di dasbor AppsFlyer.

## Langkah 2: Integrasi SDK

Selesaikan langkah-langkah berikut untuk setiap aplikasi yang ditentukan di AppsFlyer dalam [Langkah 1: Penyiapan aplikasi](/docs/getting-started-onboarding-for-marketers#langkah-1-pengaturan-aplikasi):

| Langkah | Pemilik | Waktu | Komentar |
| --- | --- | --- | --- |
| Pertimbangkan opsi yang tersedia dan pilih <Anchor target="_blank" href="/marketers/id/docs/sdk-integration-overview">fungsi SDK</Anchor> yang Anda ingin digunakan oleh aplikasi Anda | Manajer produk | 1 jam | <ul><li>Beberapa pertimbangan selain atribusi dasar:<ul><li>Apakah kampanye Anda akan menautkan langsung (deep link) pengguna ke aplikasi?</li><li>Apakah aplikasi harus <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#mengakses-data-atribusi-dan-deep-linking">mengakses data atribusi atau data deep linking</Anchor>?</li><li>Haruskah data AppsFlyer berisi <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">ID Pengguna Pelanggan</Anchor> Anda untuk referensi?</li><li>Bagaimana Anda menerapkan <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">pengaturan privasi untuk perangkat iOS 14+</Anchor>? Apakah Anda akan mengukur uninstall, menjalankan kampanye lintas promosi, dan banyak lagi?</li></ul></li><li>Apakah Anda memiliki aplikasi CTV? Lihat <Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-platform-attribution-concepts">Tinjauan CTV</Anchor>.</li></ul> |
| Pilih <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview">in-app event</Anchor> yang akan direkam | Manajer produk | 1 jam | Merekam event pasca-penginstalan yang dilakukan pengguna Anda di aplikasi membantu Anda lebih memahami **kualitas** pengguna Anda.<br /><br />Kunjungi [Generator in-app event](https://evgen.appsflyer.com/) untuk menggunakan daftar lengkap <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#recommended-events-by-business-vertical">rekomendasi in-app event</Anchor> dan parameter untuk vertikal Anda. Anda dapat menambahkan event dan parameter Anda sendiri.  <br />Klik tombol **Kode** untuk melihat dan menyalin kode yang dibuat secara otomatis untuk pengembang Anda (dan membuat mereka senang). |
| Pilih metode untuk mengambil data atribusi/deep linking | Manajer produk | 30 menit | Pelajari lebih lanjut tentang <Anchor target="_blank" href="/marketers/id/docs/basic-sdk-integration-guide#mengakses-data-atribusi-dan-deep-linking">metodeyang</Anchor> tersedia:<ul><li><Anchor target="_blank" href="/marketers/id/docs/pull-api-raw-data">Pull API</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/push-api-streaming-raw-data">Push API</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/create-a-onelink-template">API deep linking terpadu</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/conversion-data-payloads-and-scenarios">Dapatkan data konversi</Anchor></li></ul> |
| Implementasi oleh pengembang | Pengembang aplikasi: | 3 jam | Sumber daya AppsFlyer untuk pengembang Anda:<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk">Android</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">iOS</Anchor></li><li>Unity</li><li><Anchor target="_blank" href="/marketers/id/docs/windows-sdk-integration-for-developers">Windows phone</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/other-platforms">Platform lainnya</Anchor></li></ul> |
| <Anchor target="_blank" href="/marketers/id/docs/testing-the-sdk-integration-for-marketers">Uji integrasi</Anchor> | Manajer produk/  <br />Pengembang aplikasi | 1 jam | Anda dapat menguji integrasi SDK Anda sebelum atau setelah aplikasi Anda aktif di app store. Anda dapat menggunakan aplikasi debug untuk menjaga data aplikasi Anda tetap bersih.<br /><br />Pastikan untuk <Anchor target="_blank" href="/marketers/id/docs/registering-test-devices">mendaftarkan perangkat uji Anda</Anchor>. |
| Rilis versi aplikasi baru | Manajer produk | 1 jam | <Anchor target="_blank" href="/marketers/id/docs/preparing-for-the-app-store-review-nutrition-labels">Bersiaplah untuk ulasan App Store iOS</Anchor>. |

**Hasil:** Aplikasi Anda siap untuk menginstal atribusi, mengukur in-app event, dan fungsi AppsFlyer lainnya yang tidak memerlukan sumber daya pengembang tambahan.

## Langkah 3: Pengaturan atribusi

Selesaikan langkah-langkah berikut untuk setiap aplikasi yang ditentukan di AppsFlyer dalam [Langkah 1: Penyiapan aplikasi](/docs/getting-started-onboarding-for-marketers#langkah-1-pengaturan-aplikasi):

| Langkah | Pemilik | Waktu | Komentar |
| --- | --- | --- | --- |
| Atur sumber media **berbayar** untuk atribusi di AppsFlyer | Manajer produk/  <br /> Pemasar | 15 menit per sumber media | Pelajari tentang mengatribusikan <Anchor target="_blank" href="/marketers/id/docs/self-reporting-networks-srns">Self Reporting Networks</Anchor> (Jaringan Pelaporan Mandiri/SRN), khususnya:<ul><li><Anchor target="_blank" href="/marketers/id/docs/google-ads-adwords-integration-setup-for-advertisers">Google Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/meta-ads-integration-setup">Iklan Meta</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/apple-ads-integration-setup">Apple Search Ads</Anchor></li><li>GMP (Klik dua kali)</li></ul>Pelajari tentang mengatribusikan jaringan iklan non-SRN:<ul><li><Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner">Mitra terintegrasi lainnya</Anchor></li><li>Struktur dan parameter <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters">tautan atribusi</Anchor> AppsFlyer</li></ul> |
| Gunakan OneLink untuk mengatribusikan sumber media **milik Anda**: situs web seluler, media sosial, undangan pengguna, dan banyak lagi | Manajer produk | 1 jam | Pelajari tentang <Anchor target="_blank" href="/marketers/id/docs/onelink-guide#opsi-tambahan">solusi berbasis OneLink</Anchor> untuk kasus penggunaan media milik Anda |
| Implementasi pengembang media milik Anda | Pengembang aplikasi: | 0-6,5 jam (tergantung pada solusi yang diterapkan) | Untuk pengembang: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">Memulai Deep linking</Anchor> |
| Atur jendela atribusi | Manajer produk | 2 menit per sumber media | Pelajari lebih lanjut: <Anchor target="_blank" href="/marketers/id/docs/set-up-lookback-windows">Penjelasan jendela lookback klik dan lihat-tayang</Anchor> |
| [Opsional] Aktifkan kampanye penargetan ulang | Manajer produk | 2 menit | <Anchor target="_blank" href="/marketers/id/docs/app-settings#reengagement-attribution">Aktifkan Penargetan Ulang di halaman Pengaturan Aplikasi</Anchor>.<br /><br />Pelajari lebih lanjut tentang: <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide">Panduan penargetan ulang</Anchor> |

**Hasil:** Semua sumber media yang mendatangkan lalu lintas ke aplikasi Anda diatribusikan setiap kali pengguna baru atau pengguna kembali berinteraksi dengan sumber media tersebut.

## Langkah 4: Pengaturan tambahan

Selesaikan langkah-langkah berikut untuk setiap aplikasi yang ditentukan di AppsFlyer dalam [Langkah 1: Penyiapan aplikasi.](/docs/getting-started-onboarding-for-marketers#langkah-1-pengaturan-aplikasi)

Langkah-langkah tertentu mungkin wajib untuk memenuhi tujuan bisnis Anda.

| Langkah | Pemilik | Sumber daya tambahan |
| --- | --- | --- |
| Optimalkan kampanye akuisisi pengguna dengan mencatat pendapatan | Manajer produk/  <br /> Pengembang | <ul><li><Anchor target="_blank" href="/marketers/id/docs/legacy-receipt-validation-for-in-app-purchases">Validasi Pembelian Dalam-Aplikasi (In-app purchase)</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/roi360-guide-ad-revenue-attribution">Monetisasi iklan</Anchor></li><li>Langganan pengguna</li></ul> |
| Pelajari tentang metode untuk menggabungkan dan menampilkan data biaya pemasaran | Manajer produk | <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview">ROI360—ringkasan agregasi biaya</Anchor> |
| Atur <Anchor target="_blank" href="/marketers/id/docs/3rd-party-platforms">platform pihak ketiga</Anchor> yang digunakan aplikasi Anda | Manajer produk/  <br /> Pengembang | <ul><li><Anchor target="_blank" href="/marketers/id/docs/mparticle-integration-with-appsflyer">mParticle</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/segment-integration">Segmen</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/mixpanel-integration-with-appsflyer">Mixpanel</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/amplitude-integration-with-appsflyer">Amplitude</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/adobe-analytics-integration-with-appsflyer">Adobe Analytics</Anchor> (Omniture)</li><li><Anchor target="_blank" href="/marketers/id/docs/braze-formerly-appboy-integration-with-appsflyer">Braze</Anchor></li></ul> |
| Lihat fitur-fitur premium AppsFlyer yang dapat menghemat waktu dan uang Anda. | Manajer produk | <ul><li><Anchor target="_blank" href="/marketers/id/docs/audiences-guide">Audiences</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/pivot-table-user-metrics">Tabel Pivot</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/data-locker-for-marketers">Data Locker</Anchor></li></ul> |
| Lindungi kampanye Anda dari kecurangan dan salah sasaran | Manajer produk | <ul><li><Anchor target="_blank" href="/marketers/id/docs/protect360-anti-fraud-guide">Protect360—Solusi Anti Kecurangan</Anchor></li><li>Gunakan <Anchor target="_blank" href="/marketers/id/docs/implement-validation-rules-to-prevent-fraud">Aturan Validasi</Anchor> untuk memastikan kampanye tidak salah sasaran</li><li>Atur Live Alerts (Peringatan Langsung) untuk memantau berbagai KPI secara waktu aktual</li></ul> |
| Terapkan API Server-ke-Server untuk in-app event yang dilaporkan di luar aplikasi | Manajer produk/  <br /> Pengembang | <Anchor target="_blank" href="/marketers/id/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S REST API</Anchor> |
| Mengukur tingkat uninstall untuk sumber media Anda. | Manajer produk/  <br /> Pengembang | Pengukuran Uninstall |
| Mendapatkan wawasan terpadu tentang perjalanan pelanggan di seluruh saluran, platform, dan perangkat | Manajer produk/  <br /> Pengembang | <Anchor target="_blank" href="/marketers/id/docs/people-based-attribution-pba-overview">Atribusi berbasis orang (PBA)</Anchor> |
| Memastikan kepatuhan terhadap peraturan privasi: GDPR, CCPA, dll. | Manajer produk/  <br /> Pengembang | Mengizinkan pengguna untuk <Anchor target="_blank" href="/marketers/id/docs/apply-privacy-preserving-sdk-methods">menonaktifkan</Anchor> atribusi. |

## Memperkaya pengetahuan Anda

Direkomendasikan untuk semua pengguna AppsFlyer

| Langkah | Waktu |
| --- | --- |
| Kenali dasbor ikhtisar AppsFlyer | 15 menit |
| Menelusuri perbedaan antara <Anchor target="_blank" href="/marketers/id/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">Data Lifetime Value (LTV) dan data aktivitas</Anchor> AppsFlyer (memecahkan misteri mengapa ringkasan in-app event berbeda antara dasbor Tinjauan/Overview) dan dan Aktivitas/Activity) | 15 menit |
| Memahami <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model">model atribusiAppsFlyer</Anchor> | 30 menit |
| Mempelajari tentang <Anchor target="_blank" href="/marketers/id/docs/aggregated-and-analytics-reporting-overview">alat pelaporan dan analitik gabungan</Anchor> | 30 menit |
| Mempelajari tentang <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">pelaporan data lengkap</Anchor> | 30 menit |

## Terkait

> 👍 **Tips**
>
> Baru mengenal UA (akuisisi pengguna)? Pelajari <Anchor target="_blank" href="https://www.appsflyer.com/resources/ecommerce/getting-started-user-acquisition-apps-complete-guide/">semua tentang</Anchor> tantangan terbesar dan elemen terpenting dari perencanaan, pelaksanaan, dan terus mengoptimalkan upaya akuisisi pengguna Anda.

> 📘 **Catatan**
>
> Baru mengenal AppsFlyer tetapi bukan pengiklan? Tak perlu khawatir!
> Pilih panduan untuk Anda di bawah ini dan mulailah:
>
> * <Anchor target="_blank" href="/partners/id/docs/getting-started-agency-onboarding">Memulai untuk Agensi</Anchor>
> * <Anchor target="_blank" href="/partners/id/docs/getting-started-onboarding-guide-for-ad-networks">Memulai untuk jaringan iklan</Anchor>

<div data-zendesk-anchors="introduction=pengantar 01H8BD2FJ6TQ5FP9625MNP2B3Z=pengantar step-1-account-setup=pengaturan-akun 01H8BD2FJ6E8KZW41V04SBDQPQ=pengaturan-akun 01H8BD2FJ6A39JB8J0PQ3EY52N=tips app-onboarding=orientasi-aplikasi 01H8V6FS97NTTF1VPQQDZQT973=orientasi-aplikasi step-2-app-setup=langkah-1-pengaturan-aplikasi 01H8BD2FJ61S3Z22CD01H6F39E=langkah-1-pengaturan-aplikasi step-3-sdk-integration=langkah-2-integrasi-sdk 01H8BD2FJ6CY53QXVB5QC98KTT=langkah-2-integrasi-sdk step-4-attribution-setup=langkah-3-pengaturan-atribusi 01H8BD2FJ6Q8R83FV0XS5B93B3=langkah-3-pengaturan-atribusi step-5-additional-setup=langkah-4-pengaturan-tambahan 01H8BD2FJ76WD0MRCJXZH8XABN=langkah-4-pengaturan-tambahan enrich-your-knowledge=memperkaya-pengetahuan-anda 01H8BD2FJ7ZV0ZYHQZ8DBTTFFK=memperkaya-pengetahuan-anda related=terkait 01H8BD2FJ748GFC4VJWWYGGN1K=terkait 01H8BD2FJ712NGA534TCSWQGR8=tips-1 01H8BD2FJ7PRJAA1K8MESRK7VA=catatan" />
