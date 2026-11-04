---
title: In-app event generator
metadata:
  keywords:
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
  created_at: '2022-11-08T12:47:30Z'
  edited_at: '2023-11-02T12:44:45Z'
  id: 10457123447953
  locale: id
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/id/articles/10457123447953
---
> **Sekilas:** Secara otomatis membuat kode aplikasi (Android dan iOS asli, Unity) untuk mengirim in-app event dengan menentukan nama event dan konten sesuai dengan kebutuhan bisnis Anda.

<div id="introduction" />

## Pengantar

In-app event adalah alat utama bagi **pemilik aplikasi untuk mengukur kualitas pengguna mereka yang berasal dari berbagai sumber** berdasarkan tindakan yang diambil setelah penginstalan aplikasi. Event juga sering digunakan untuk melakukan kampanye pemasaran berbasis CPA.

Namun, lebih dari satu orang sering kali terlibat dalam definisi dan integrasi in-app event ke aplikasi. Meskipun pemasar/manajer produk menentukan konten kumpulan event sesuai dengan kebutuhan bisnis, satu atau beberapa pembuat aplikasi seluler umumnya diwajibkan untuk mengimplementasikan API in-app event di aplikasi mereka.

<Anchor target="_blank" href="https://evgen.appsflyer.com/">In-app event generator AppsFlyer</Anchor> **memecahkan tantangan yang melekat dalam kolaborasi penting antara pemasar dan pembuat aplikasi seluler ini**.

Dengan menggunakan In-app event generator, pemasar dapat:

* Menggunakan **serangkaian event dan parameter yang direkomendasikan** yang ditentukan sebelumnya untuk vertikalnya.
* Menambahkan atau menghapus event/parameter, deskripsi, pemicu, dan contoh yang ditentukan sebelumnya atau disesuaikan untuk referensi.
* **Mengirimkan kode yang dihasilkan secara otomatis** ke pembuat aplikasi seluler Android dan iOS mereka – **menghemat hari kerja,** komunikasi yang berlebihan, dan potensi kesalahan.
* **Menggunakan kembali pekerjaan mereka** jika nanti mereka memperbarui acara, menambahkan event baru, atau menambahkan aplikasi baru.

<div id="using-the-in-app-event-generator" />

## Menggunakan in-app event generator

**Menggunakan in-app event generator untuk membuat rangkaian event untuk aplikasi baru, atau untuk memperbarui rangkaian yang sudah ada.**

<div id="creating-a-new-event-set" />

### Membuat rangkaian event baru

**Untuk membuat rangkaian event baru:**

1. Buka <Anchor target="_blank" href="https://evgen.appsflyer.com/">In-app event generator</Anchor> dan masukkan nama aplikasi Anda.
2. Pilih vertikal atau impor rangkaian event dari aplikasi serupa yang sebelumnya diekspor ke file JSON.
3. Tambahkan atau hapus event dan parameter, sesuai dengan kebutuhan bisnis Anda.
4. Klik tombol **`</>` Code** untuk melihat dan menyalin kode yang dihasilkan untuk programmer Anda: Java (Android asli), Obj-C/Swift (iOS asli), atau C# (Unity).
5. Klik **Download .zip** untuk menyimpan rangkaian event untuk digunakan di masa mendatang atau untuk berkolaborasi dengan programmer dan kolega.

<div id="updating-an-existing-event-set" />

### Memperbarui rangkaian event yang sudah ada

**Untuk memperbarui rangkaian event yang sudah ada**

1. Buka <Anchor target="_blank" href="https://evgen.appsflyer.com/">In-app event generator</Anchor>.
2. Impor rangkaian event app Anda yang sebelumnya diekspor ke file JSON.
3. Tambahkan atau hapus event dan parameter, sesuai dengan kebutuhan bisnis Anda.
4. Klik tombol **`</>` Code** untuk melihat dan menyalin kode yang dihasilkan untuk programmer Anda: Java (Android asli), Obj-C/Swift (iOS asli), atau C# (Unity).
5. Klik **Download .zip** untuk menyimpan rangkaian event untuk digunakan di masa mendatang atau untuk berkolaborasi dengan programmer dan kolega.

<div id="adding-events" />

### Menambahkan event

**Untuk menambahkan event baru ke rangkaian event:**

1. Klik tombol **+ Event**. Event baru muncul di bagian bawah rangkaian event.
2. Pilih  event yang **telah ditentukan sebelumnya** dari daftar event yang disarankan (direkomendasikan), atau klik **Custom** untuk menentukan nama event Anda sendiri. Verifikasi bahwa nama event belum ada di rangkaian event.
3. Masukkan tujuan event, yang menjelaskan skenario bisnis.
4. Masukkan tindakan pemicu untuk event tersebut, yang menjelaskan waktu dalam perjalanan pengguna saat event harus dikirim. Penjelasan ini ditambahkan sebagai komentar dalam kode yang dihasilkan untuk referensi cepat oleh programmer.
5. [Opsional] Tambahkan satu atau beberapa parameter ke event.

<div id="adding-parameters" />

### Menambahkan parameter

**Untuk menambahkan parameter baru ke rangkaian event:**

1. Klik tombol **+ Add parameter** untuk event yang relevan.
2. Pilih **parameter yang ditentukan sebelumnya** dari daftar parameter yang disarankan (direkomendasikan).
3. Jika tidak, klik **Custom** untuk menentukan nama parameter Anda sendiri dan tekan **Enter**.
4. Ketik satu atau beberapa nilai parameter tipikal untuk referensi.
5. Untuk membantu programmer Anda, ketikkan deskripsi umum, jenis bidang, atau sumber yang sesuai untuk nilai parameter di aplikasi Anda. Ini muncul sebagai komentar untuk setiap parameter event dalam kode yang dihasilkan.

**Catatan**:<Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#predefined-and-custom-events">Penamaan standar</Anchor> memungkinkan pemetaan event dan parameter secara otomatis ke mitra dan merupakan metode yang direkomendasikan.

<div id="see-also" />

> 📄 **Lihat juga**
>
> * Dashboard event

<div data-zendesk-anchors="introduction=pengantar h_01HE7T0ZA12E7KHS7WBQ757KF1=pengantar using-the-inapp-event-generator=menggunakan-in-app-event-generator h_01HE7T0ZA2A1KS4NF43GRZB87X=menggunakan-in-app-event-generator creating-a-new-event-set=membuat-rangkaian-event-baru h_01HE7T0ZA2KQ44P40Y028VVA4K=membuat-rangkaian-event-baru updating-an-existing-event-set=memperbarui-rangkaian-event-yang-sudah-ada h_01HE7T0ZA2P2WZ07CT880ZSK0Z=memperbarui-rangkaian-event-yang-sudah-ada adding-events=menambahkan-event h_01HE7T0ZA2Z3D3J014E7E0T13X=menambahkan-event adding-parameters=menambahkan-parameter h_01HE7T0ZA2KAH7N44EQ9W5BH5G=menambahkan-parameter h_01HE7T4ZR4AY2J71B3PJKJP490=lihat-juga" />
