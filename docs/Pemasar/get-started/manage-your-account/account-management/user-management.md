---
title: Manajemen pengguna
metadata:
  keywords:
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
  created_at: '2021-10-17T11:54:49Z'
  edited_at: '2023-11-23T11:40:35Z'
  id: 4409128270481
  locale: id
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/id/articles/4409128270481
---
> **Sekilas:** Buat dan kelola pengguna AppsFlyer akun Anda, dan beri mereka izin untuk mengakses fitur, aplikasi, dan data.

<div id="overview" />

## Latar belakang

Akun AppsFlyer memungkinkan untuk banyak pengguna, masing-masing dengan izin yang dikelola secara individual. Jumlah maksimal pengguna per akun ditentukan oleh paket langganan Anda.

Setiap izin pengguna ditentukan dalam 3 dimensi utama:

* **Peran** (kemampuan untuk mengakses fitur dan menjalankan fungsi)
* **Akses aplikasi** untuk aplikasi saat ini dan yang akan datang
* **Akses data** berdasarkan sumber media dan geo
  * Penting! Dashboard dan fitur AppsFlyer tertentu tidak tersedia untuk pengguna dengan akses data terbatas (ke sumber media dan geo). Dashboard dan fitur ini [tercantum di sini](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access).

Izin dalam masing-masing dimensi ini diberikan secara independen. Dengan kata lain, Anda dapat menetapkan **peran** dengan kemampuan fungsional yang luas kepada pengguna, namun mengizinkan mereka menggunakan kemampuan tersebut hanya dalam kumpulan **aplikasi, sumber media, dan geo yang ditentukan secara sempit.** Satu-satunya pengecualian adalah [peran Admin](/docs/user-management#adminperan-khusus), seperti dibahas di bawah, yang memiliki akses ke semua kemampuan, aplikasi, sumber media, dan geo.

Fitur baru, yang saat ini masih dalam versi Beta, memungkinkan Anda untuk [menambahkan pengguna ke beberapa akun](#multiple-accounts) sehingga mereka dapat dengan mudah beralih antar akun.

<div id="manage-roles" />

## Peran

Setiap pengguna akun AppsFlyer Anda harus diberi peran. Setiap peran menentukan fitur AppsFlyer spesifik yang dapat diakses pengguna dan fungsi yang dapat mereka lakukan. Daftar lengkap kemampuan per peran tersedia di [tab Peran](/docs/user-management#tab-peran) di halaman **Pengelolaan pengguna** .

Peran dalam AppsFlyer dapat berupa [peran yang telah ditentukan sebelumnya](/docs/user-management#peran-yang-telah-ditentukan), [peran khusus](/docs/user-management#peran-khusus), atau (dalam keadaan tertentu) [peran sementara](/docs/user-management#peran-sementara).

<div id="predefined-roles" />

### Peran yang telah ditentukan

AppsFlyer dikonfigurasikan dengan banyak peran yang telah ditentukan sebelumnya:

* Admin
* Manajer tim
* Pimpinan pemasaran
* Pemasaran
* Pemasaran – terbatas
* Kontributor
* Akuntansi
* Keamanan
* Penjaminan Mutu

Untuk masing-masing peran yang telah ditentukan ini, kapabilitas fungsionalnya tetap: tidak ada "pencampuran dan pencocokan" yang diperbolehkan. Namun, Anda dapat mengubah kemampuan fungsional pengguna kapan saja dengan menugaskannya ke peran berbeda yang telah ditentukan sebelumnya atau peran khusus (kecuali untuk [pemilik akun](#pemilik-akun), seperti yang dibahas di bawah).

<div id="example-1" />

> 📄 **Contoh**
>
> Anda telah menugaskan Bill Bates sebagai **Manajer tim.** Peran ini memberi Bill kemampuan untuk mengelola **templat OneLink,** tetapi tidak mengizinkannya untuk mengakses halaman **Paket saya** dan **Pembayaran** .
>
> **Pertanyaan:** Dapatkah saya mempertahankan Bill dalam peran Manajer tim, tetapi juga memberinya kemampuan untuk mengakses halaman Paket saya dan Pembayaran? Bisakah saya mengambil kemampuannya untuk mengelola template OneLink?
>
> **Jawaban:** Tidak. Selama Bill tetap dalam peran manajer Tim, Anda tidak dapat memberinya kemampuan untuk mengakses halaman Paket Saya dan Pembayaran. Anda juga tidak dapat menghapus kemampuannya untuk mengelola templat OneLink. Tentu saja, Anda dapat menugaskan Bill ke peran yang telah ditentukan sebelumnya, dan kemampuannya akan berubah sesuai dengan yang ditentukan oleh peran tersebut. Atau, Anda dapat membuat peran khusus untuk Bill yang mengubah kemampuannya sesuai kebutuhan Anda.

<div id="custom-roles" />

### Peran khusus

Peran yang telah ditentukan sebelumnya di AppsFlyer telah dikonfigurasikan dengan kombinasi kemampuan khusus yang diperlukan di sebagian besar situasi. Karena alasan ini, banyak pemasang iklan merasa bahwa mereka tidak perlu menyesuaikan peran lebih lanjut. Namun, saat penyesuaian tambahan diperlukan, peran yang telah ditentukan masih merupakan titik awal yang bagus untuk mengelola kemampuan pengguna Anda.

Pelajari lebih lanjut tentang [mengelola peran khusus](/docs/user-management#mengelola-peran-khusus).

<div id="temp-roles" />

### Peran sementara

Jika akun AppsFlyer Anda ada di bawah sistem manajemen pengguna kami sebelumnya (ketika satu-satunya jenis akun yang tersedia adalah Admin dan Anggota tim), semua pengguna dibawa ke sistem baru dengan kemampuan yang tidak berubah. Akibatnya, sebagian besar pengguna ini muncul di sistem saat ini dengan **peran sementara**.

Pelajari lebih lanjut tentang [mengelola peran sementara](/docs/user-management#managing-temp-roles).

<div id="admin" />

### Admin—peran khusus

Akun AppsFlyer dapat memiliki **satu atau lebih Admin**. Peran khusus ini memiliki beberapa karakteristik unik:

<div id="access" />

#### Akses

Peran Admin memiliki akses ke **semua kemampuan akun**, termasuk:

* Semua fitur dan fungsi
* Semua aplikasi saat ini dan masa depan
* Semua sumber media dan geo

Karakteristik "akses penuh" dari peran Admin ini tidak dapat diubah atau dibatasi.

<div id="role-duplication" />

#### Duplikasi peran

Peran Admin **tidak dapat diduplikasi** saat membuat [peran khusus](/docs/user-management#mengelola-peran-khusus).

<div id="account-owner" />

#### Pemilik Akun

Pengguna yang dibuat pada saat akun dibuka, "pemilik akun", diberi peran Admin secara default. Pemilik akun awalnya bertanggung jawab untuk membuat pengguna tambahan, hingga pengguna tambahan dengan kemampuan pengelolaan pengguna dibuat.

Seorang pemilik akun memiliki ciri-ciri unik:

* Berbeda dengan Admin mana pun selain pemilik akun, pemilik akun tidak dapat dihapus, dihapus dari peran Admin, atau diedit dari halaman [**Manajemen pengguna**](/docs/user-management#halaman-manajemen-pengguna) .
* Jika Anda perlu mengubah pemilik akun, ikuti [langkah-langkah yang tercantum di bawah ini](/docs/user-management#changing-the-account-owner).
* Hanya pemilik akun yang dapat:
  * Mengambil atau menyetel ulang <Anchor target="_blank" href="/marketers/id/docs/managing-appsflyer-tokens">token AppsFlyer API</Anchor>
  * Mengonfigurasikan atau membuat perubahan pada <Anchor target="_blank" href="/marketers/id/docs/push-api-streaming-raw-data">pengaturan Push API</Anchor>

<div id="user-management-page" />

## Halaman manajemen pengguna

**Untuk mengakses halaman Manajemen pengguna:**

1. Di bilah menu, klik tarik-turun alamat email.
2. Pilih **Manajemen pengguna.**

<div id="users-tab" />

### Tab pengguna

Tab **Pengguna** menampilkan tabel semua pengguna yang ada di akun Anda. Ini adalah titik awal untuk membuat, mengelola, dan menghapus pengguna.

Tips untuk menavigasi tab Pengguna:

* Klik judul kolom **Pengguna** untuk mengurutkan tabel menurut abjad (naik/turun).
* Gunakan kotak telusur untuk menemukan dan menampilkan pengguna tertentu.
* Klik ikon filter <Image alt="filter_icon.png" src="https://files.readme.io/1ceaac3efead3a218909988be1d50a2f0af93b07360f7197cd398b11d661992b-16162502598417.png" width="25px" /> di judul kolom **Peran** untuk memfilter pengguna berdasarkan peran mereka (termasuk peran sementara).
  * Untuk menghapus filter, pilih **Tidak ada** di daftar tarik-turun filter.
* Klik tajuk kolom **Login terakhir** untuk mengurutkan pengguna berdasarkan tanggal terakhir mereka login ke AppsFlyer.
  * **Tips:** Gunakan fitur ini untuk mengidentifikasi dan [menghapus](/docs/user-management#deleting-users) pengguna yang tidak aktif dengan mudah, membantu menjaga keamanan akun Anda dari proses masuk yang tidak sah.
* Gunakan kotak centang untuk memilih dan [mengedit beberapa pengguna](/docs/user-management#pengeditan-multi-pengguna) sekaligus.
* Khusus admin: Klik ikon unduh <Image alt="download_icon.png" src="https://files.readme.io/fba5d56ceb7f6b3dc3191e5ec33c85ccbba0f7dc409ad0390de238c12b479b61-31780969029777.png" width="24px" /> di pojok kanan atas halaman untuk mengunduh tabel pengguna lengkap sebagai file CSV.
  * File yang diunduh menyertakan kolom yang sama dengan tabel di tab **Pengguna** .

<div id="roles-tab" />

### Tab peran

Tab **Peran** menampilkan daftar semua peran yang ditentukan di akun Anda, termasuk:

* [Peran yang telah ditentukan](/docs/user-management#peran-yang-telah-ditentukan)
* [Peran khusus](/docs/user-management#mengelola-peran-khusus) yang telah Anda buat
* Semua [peran sementara](/docs/user-management#peran-sementara) yang saat ini ditetapkan ke pengguna

Di samping setiap peran, Anda dapat melihat jumlah pengguna yang saat ini ditetapkan untuk peran tersebut.

Klik nama peran apa pun di panel kiri untuk menampilkan detail lengkap kemampuan peran tersebut.

<div id="manage-users" />

## Mengelola pengguna

Admin dapat membuat pengguna baru, menambahkan mereka ke beberapa akun (Beta), mengedit detail mereka seperti peran dan akses yang mereka miliki ke aplikasi dan data, dan menghapus pengguna.

<div id="creating-users" />

<Accordion title="Membuat pengguna">

Ada dua tahap untuk membuat pengguna. Pertama, pengguna dibuat di platform. Selanjutnya, pengguna yang baru dibuat harus mengaktifkan akunnya.

#### Buat pengguna

1. Pada tab **Pengguna** , klik tombol **Pengguna baru** .
2. Masukkan nama pengguna (wajib):
   * Dapat menyertakan huruf, angka, spasi, tanda titik (.), tanda hubung (-), garis bawah (\_), dan tanda kutip tunggal (') atau ganda (").
   * Karakter khusus lainnya tidak diperbolehkan.
3. Masukkan alamat email pengguna (wajib):
   * Dapat berisi huruf, angka, apostrof ('), ampersan (&), tanda dolar ($), simbol hash (#), tanda hubung (-), garis bawah (\_), dan tanda titik (.)
   * Dua titik berturut-turut (..) dan karakter khusus lainnya tidak diperbolehkan.
   * Harus diakhiri dengan domain email yang valid.

   <div id="important" />

   > 🚧 **Penting!**
   >
   > Alamat email pengguna adalah yang mengidentifikasi mereka di platform AppsFlyer, artinya:
   >
   > * Nantinya tidak dapat diubah tanpa menghapus dan membuat ulang pengguna.
   > * Ini harus berupa alamat email yang valid di mana pengguna dapat menerima email.
   > * Ini tidak dapat dikaitkan dengan pengguna lain di akun AppsFlyer mana pun, [kecuali untuk pengguna di akun beta](/docs/user-management#multiple-accounts). Jika alamat email sudah digunakan (di akun Anda atau di akun lain), Anda akan melihat pesan *Tidak dapat membuat pengguna ini.* Ikuti [langkah pemecahan masalah di bawah ini](/docs/user-management#troubleshooting-can-t-create-this-user) untuk mengatasi masalah ini.

4. Pilih departemen pengguna (opsional).
5. Pilih peran pengguna (wajib) – baik peran yang sudah ditentukan sebelumnya atau peran khusus yang telah Anda buat.
6. Pilih aplikasi yang dapat diakses pengguna:
   * Pengaturan default memungkinkan akses ke semua aplikasi saat ini dan yang akan datang di akun. Untuk mengubah setelan ini, gunakan kotak centang untuk memilih dan membatalkan pilihan aplikasi.
   * Pengguna dapat diberi akses ke semua aplikasi mendatang hanya jika mereka memiliki akses ke semua aplikasi saat ini.
7. Pilih sumber media yang dapat diakses pengguna: Pengaturan default memungkinkan akses ke semua sumber media. Untuk mengubah pengaturan ini:
   1. Klik tombol **Semua** .
   2. Dari daftar tarik-turun, pilih sumber media tertentu yang dapat diakses pengguna.  

      > 📘 **Catatan**
      >
      > * Saat memilih sumber media tertentu, pengguna hanya akan memiliki akses ke mitra yang terintegrasi dengannya
      > * Akses ke sumber media yang dimiliki hanya tersedia saat memilih **Semua** sumber media.
      > * [Dashboard dan fitur AppsFlyer tertentu tidak tersedia](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access) untuk pengguna dengan akses sumber media terbatas.

8. Pilih lokasi yang dapat diakses pengguna:
   * Pengaturan default memungkinkan akses ke semua lokasi. Untuk mengubah pengaturan ini:
     * Klik tombol **Semua** .
     * Dari daftar tarik-turun, pilih lokasi tertentu yang dapat diakses pengguna.
   * [Dashboard dan fitur AppsFlyer tertentu tidak tersedia](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access) untuk pengguna dengan akses geografis terbatas.
9. Klik **Simpan** untuk membuat pengguna.

<div id="user-activation" />

#### Aktivasi pengguna

Setelah pengguna dibuat, Anda dapat melihatnya di tabel pengguna dengan ikon amplop ![pending_invitation_icon.png](https://files.readme.io/68ac08ab6e52191a592350f82996f7ade9d181773d0bdbc6e2cb60315b60a8f2-16162502609553.png). Ini menandakan undangan telah terkirim dan akun sedang menunggu aktivasi. Pengguna harus mengaktifkan akunnya menggunakan tautan di emailnya. Tautan aktivasi berlaku selama 48 jam. Setelah pengguna mengaktifkan akunnya, amplop tersebut menghilang.

<div id="note-2" />

> 📘 **Catatan**
>
> Jika pengguna tidak menerima undangan atau jika tautan telah kedaluwarsa, Anda dapat [mengirim ulang undangan](/docs/user-management#resending-a-user-invitation).


</Accordion>

<div id="multiple-accounts" />

<Accordion title="Menambahkan pengguna ke beberapa akun">

> 📘 **Catatan**
>
> Fitur ini saat ini hanya tersedia untuk akun yang berpartisipasi dalam versi beta. Jika Anda ingin mencobanya, hubungi CSM Anda atau [hello@appsflyer.com](mailto:hello@appsflyer.com).

Pengguna dapat ditambahkan ke beberapa akun dan ditetapkan ke peran berbeda di setiap akun. Ini membantu pengguna bekerja di akun yang berbeda tanpa perlu memasukkan kembali kredensial.

<div id="supported-accounts-and-users" />

#### Akun dan pengguna yang didukung

Akun berikut mendukung adanya pengguna yang sama di beberapa akun:

* Hanya akun pemasang iklan
* Akun yang tidak menggunakan <Anchor target="_blank" href="/marketers/id/docs/implementing-and-using-2fa-login">2FA</Anchor> atau <Anchor target="_blank" href="/marketers/id/docs/set-up-sso-authentication-with-your-identity-provider-idp">SSO</Anchor>

Batasan pengguna berikut berlaku saat menambahkan pengguna ke beberapa akun:

* Fitur ini hanya tersedia untuk pengguna dengan izin manajemen Pengguna yang sesuai.
* [Pemilik akun](#pemilik-akun) hanya bisa ada di satu akun. Pengguna ini tidak boleh ada di akun lain mana pun, bahkan dalam peran yang berbeda.
* Pengguna yang belum [mengaktifkan akunnya](#aktivasi-pengguna) tidak dapat ditambahkan ke akun lain.

<div id="add-users-to-multiple-accounts" />

#### Tambahkan pengguna ke beberapa akun

**Untuk menambahkan pengguna yang sama ke beberapa akun:**

1. Masuk ke akun tempat Anda ingin menambahkan pengguna.
2. Dari bilah menu, klik **tarik-turun alamat email** > **Manajemen pengguna**.
3. Dari tab **Pengguna** , klik **Pengguna baru**.
4. Masukkan detail yang diperlukan, pilih peran pengguna di akun ini, dan klik **Simpan**.
5. Ulangi langkah 1-4 untuk menambahkan pengguna ke akun lain.

</Accordion>

<div id="editing-users" />

<Accordion title="Mengedit pengguna">

Pengguna dapat diedit, satu per satu atau dalam kelompok.

<div id="individual-editing" />

#### Pengeditan perorangan

**Untuk mengedit pengguna perorangan:**

1. Pada tab **Pengguna** , klik tombol **Tindakan** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> di sisi paling kanan baris pengguna.
2. Pilih **Edit** dari menu.
3. Edit pengaturan pengguna sesuai kebutuhan.
4. Semua pengaturan selain alamat email dapat diedit (termasuk peran, aplikasi, sumber media, dan lokasi).
5. Klik **Save**.

<div id="multi-user-editing" />

#### Pengeditan multi-pengguna

Pengeditan multi-pengguna adalah cara yang efisien untuk mengubah izin akun beberapa pengguna sekaligus. Menggunakan fitur ini bersama dengan kemampuan pencarian dan pemfilteran pada tab **Pengguna** dapat membuatnya sangat membantu untuk mengelola sejumlah besar pengguna.

<div id="note-4" />

> 📘 **Catatan**
>
> Anda tidak dapat menghapus pengguna atau menetapkannya ke peran Admin menggunakan pengeditan multi-pengguna.

**Untuk mengedit banyak pengguna:**

1. Pada tab **Pengguna** , centang kotak pengguna atau beberapa pengguna yang ingin Anda edit.
   * Pilih kotak centang di judul kolom untuk memilih semua pengguna yang terlihat.
   * Jumlah pengguna yang dipilih saat ini ditampilkan di sisi kanan kotak pencarian. Perhatikan bahwa [pemilik akun](#pemilik-akun) tidak dapat dipilih dan tidak termasuk dalam jumlah pengguna yang dipilih.
2. Serangkaian tombol ditampilkan di kanan atas tabel: **Peran, Aplikasi, Sumber media,** dan **Geografis.**
   * Jika satu atau beberapa pengguna terpilih memiliki akses ke aplikasi mendatang, tombol **Aplikasi** tidak tersedia. (Lihat [Batasan peran sementara](/docs/user-management#batasan-peran-sementara), di bawah.)
3. Klik tombol untuk izin yang ingin Anda ubah.
4. Lakukan perubahan yang diperlukan menggunakan kotak dialog atau daftar tarik-turun yang ditampilkan.
   * Ingatlah bahwa perubahan Anda berlaku untuk semua pengguna yang dipilih!
5. Pengguna yang diedit disorot dalam tabel, dan pengguna muncul sebagaimana adanya setelah perubahan disimpan. Namun, Anda masih memiliki kesempatan untuk meninjau perubahan dan mengonfirmasi atau membatalkannya di langkah berikutnya.
6. Tinjau perubahan Anda. Klik **Simpan** untuk mengonfirmasi atau **Batal** untuk membatalkannya.

<div id="example" />

> 📄 **Contoh**
>
> **Skenario:**
>
> * Ada 30 pengguna di akun Anda. Sepuluh di antaranya ada di **Pemasaran – peran** terbatas .
> * Alice, Bill, dan Charlie baru saja menerima promosi, dan Anda ingin mengubahnya dari peran **Pemasaran – peran terbatas** menjadi peran **Pemasaran** .
> * Alice akan bekerja dengan aplikasi Astounding. Bill akan bekerja dengan aplikasi Beautiful. Charlie akan bekerja dengan aplikasi Charming.
>
> **Langkah:**
>
> 1. Gunakan filter Peran <Image alt="filter_icon.png" src="https://files.readme.io/1ceaac3efead3a218909988be1d50a2f0af93b07360f7197cd398b11d661992b-16162502598417.png" width="25px" /> untuk melihat hanya pengguna di **Pemasaran–peran terbatas** .
> 2. Ubah Alice, Bill, dan Charlie ke peran **Pemasaran** :
>    * Pilih kotak centang untuk Alice, Bill, dan Charlie.
>    * Klik tombol **Peran** .
>    * Pilih **Pemasaran** dari daftar tarik-turun.
>    * Klik **Simpan** untuk mengonfirmasi.
>    * Perhatikan bahwa setelah Anda mengonfirmasi perubahan, filter **Peran** dihapus, dan tabel menampilkan semua pengguna.
> 3. Beri Alice, Bill, dan Charlie akses aplikasi yang sesuai:
>    * Gunakan kotak pencari untuk menemukan Alice, lalu edit penggunanya satu per satu untuk memberinya akses ke aplikasi Astounding.
>    * Ulangi langkah-langkah ini untuk Bill dan Charlie untuk memberi mereka akses masing-masing ke Beautiful dan Charming.

</Accordion>

<div id="deleting-users" />

<Accordion title="Menghapus pengguna">

**Untuk menghapus pengguna:**

1. Pada tab **Pengguna** , klik **Tindakan** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> tombol di sisi paling kanan baris pengguna.
2. Pilih **Hapus** dari menu.

</Accordion>

<div id="manage-custom-roles" />

## Mengelola peran khusus

<div id="creating-custom-roles" />

<Accordion title="Membuat peran khusus">

Proses pembuatan peran khusus melibatkan duplikasi peran **yang telah ditentukan sebelumnya** dan memodifikasi kemampuannya sesuai kebutuhan.

> 📘 **Catatan**
>
> * Hanya pemilik akun atau pengguna dengan akses Admin yang dapat membuat peran khusus.
> * Peran Admin, peran khusus, dan peran sementara tidak dapat diduplikasi.

**Untuk membuat peran khusus:**

1. Di panel kiri tab **Peran** , klik nama peran **yang telah ditentukan sebelumnya** dengan kemampuan yang paling mirip dengan yang ingin Anda buat. Ini adalah titik awal Anda.
2. Klik tombol **Duplikat** ![user_management_duplicate_button.png](https://files.readme.io/93d3427f3890b6d19470523ab8baa4435489428da62c23cd56a7cca7e8be923c-8781532671249.png) di pojok kanan atas layar.

   Tampilan panel kanan berubah, memungkinkan Anda untuk membuat peran kustom baru.
3. Masukkan nama untuk peran baru yang Anda buat.
   * **Catatan:** Setelah Anda menyimpan peran khusus, nama peran tidak dapat diedit.
   * **Direkomendasikan:** Buatlah nama deskriptif dan mudah dikenali nantinya.
4. Tingkat izin dari semua kemampuan yang dapat diedit ditampilkan sebagai tombol. Klik tombol ini untuk mengubah tingkat izin untuk peran khusus yang baru. (Pastikan untuk menggulir ke bawah untuk melihat daftar lengkap kemampuan.)
   * **Catatan:** Kemampuan yang tidak muncul sebagai tombol saat ini tidak dapat diedit. Untuk mengubah tingkat izin pengguna untuk kemampuan yang tidak dapat diedit, pengguna tersebut harus diberi peran yang telah ditentukan sebelumnya dengan tingkat izin yang diperlukan.
5. Saat Anda puas dengan semua pilihan Anda, klik tombol **Simpan peran** .
6. Peran khusus baru ditampilkan di panel kiri dan dapat ditetapkan saat membuat pengguna baru atau mengedit pengguna yang sudah ada.

</Accordion>

<div id="editing-custom-roles" />

<Accordion title="Mengedit peran khusus">

**Untuk mengedit peran khusus:**

1. Di panel kiri tab **Peran** , klik nama peran khusus yang ingin Anda edit.
2. Klik tombol **Edit** ![user_management_edit_role_button.png](https://files.readme.io/bf1ba44ddaa3483996c55c9450c42056acb6acbc9e921e339c8af5061f1c0bfb-8781493918225.png) di sudut kanan atas layar.

   Tampilan panel kanan berubah, memungkinkan Anda mengedit pengaturan izin peran.

   * **Catatan:** Nama peran tidak dapat diedit. Untuk mengubah nama peran, hapus dan buat ulang dengan nama baru.
3. Tingkat izin dari semua kemampuan yang dapat diedit ditampilkan sebagai tombol. Klik tombol ini untuk mengubah tingkat izin untuk peran khusus yang baru. (Pastikan untuk menggulir ke bawah untuk melihat daftar lengkap kemampuan.)
4. Saat Anda puas dengan semua pilihan Anda, klik tombol **Simpan peran** .
5. Tingkat izin peran diubah untuk semua pengguna baru dan yang sudah ada.

<div id="important-1" />

> 🚧 **Penting!**
>
> Setiap perubahan yang Anda buat pada peran khusus diterapkan secara otomatis ke **semua pengguna yang ada** dalam peran tersebut.

</Accordion>

<div id="deleting-custom-roles" />

<Accordion title="Menghapus peran khusus">

**Untuk menghapus peran khusus:**

1. Di panel kiri tab **Peran** , klik nama peran khusus yang ingin Anda hapus.
2. Klik tombol **Hapus** ![user_management_delete_role_button.png](https://files.readme.io/6a9a97ce9437de6fca16ebb9ed3ac365299e7e558f5075698d20806076c0fd9c-8781434340113.png) di sudut kanan atas layar.
3. Konfirmasikan bahwa Anda ingin menghapus peran tersebut.
   * Peran khusus hanya dapat dihapus jika tidak ada pengguna yang ditetapkan padanya. Jika ada pengguna yang saat ini ditetapkan ke peran khusus, tetapkan pengguna tersebut ke peran lain sebelum menghapus peran khusus tersebut.

</Accordion>

<div id="special-situations-and-additional-procedures" />

## Situasi khusus dan prosedur tambahan

<div id="managing-temp-roles" />

<Accordion title="Mengelola peran sementara">

Jika akun Anda sebelumnya menggunakan sistem manajemen pengguna kami sebelumnya, [**peran sementara**](/docs/user-management#peran-sementara) diberikan kepada pengguna yang ada untuk memastikan bahwa mereka dibawa ke sistem baru dengan kemampuan yang tidak berubah.

* Pengguna dengan kemampuan yang sama diberi peran sementara yang sama.
* Gunakan fitur [tab Peran](/docs/user-management#tab-peran) untuk meninjau kemampuan setiap peran sementara dan daftar pengguna yang saat ini ada di dalamnya.

<div id="temp-role-limitations" />

#### Batasan peran sementara

Peran sementara dirancang khusus untuk memungkinkan transisi yang mulus dari sistem manajemen pengguna kami sebelumnya. Dengan demikian, mereka hanya tersedia dalam situasi terbatas:

* Peran sementara tidak dapat ditetapkan ke pengguna lain (baru atau yang sudah ada).
* Pengguna dengan peran sementara tidak dapat diberi peran sementara yang berbeda (walaupun Anda dapat mengubah aplikasi, sumber media, dan lokasi yang dapat mereka akses).
  * Perhatikan bahwa akses pengguna ke aplikasi mendatang **tidak dapat** diubah saat pengguna dalam peran sementara.
* Saat pengguna dengan peran sementara diubah ke peran yang ditentukan sebelumnya, mereka tidak dapat dikembalikan ke peran sementara yang ditetapkan sebelumnya (atau ke peran sementara lainnya).
* Jika pengguna terakhir dalam peran sementara dihapus darinya, peran tersebut tidak akan muncul lagi di akun Anda.

<div id="example-2" />

> 📄 **Contoh**
>
> Akun Anda sebelumnya menggunakan sistem manajemen pengguna kami sebelumnya. Diana dan Edward adalah pengguna yang ada saat akun Anda dipindahkan ke sistem baru. Diana sekarang di peran Sementara 1, dan Edward di peran Sementara 2.
>
> * Anda mempekerjakan karyawan baru, Fiona. Anda dapat menugaskan Fiona salah satu dari [peran yang telah ditentukan](/docs/user-management#peran-yang-telah-ditentukan). Namun, Anda tidak dapat menetapkan Fiona sebagai peran Sementara 1 atau peran Sementara 2.
> * Diana tidak dapat dipindahkan dari peran Sementara 1 ke peran Sementara 2. Namun, Anda dapat memberinya peran apa pun yang telah ditentukan sebelumnya. Anda juga dapat mengubah aksesnya ke aplikasi, sumber media, dan lokasi jika diperlukan.
> * Jika Anda memindahkan Diana dari peran Sementara 1 ke peran Akuntansi, nanti dia tidak dapat dipindahkan kembali ke peran Sementara 1.
> * Jika Diana adalah pengguna terakhir di peran Sementara 1 saat Anda memindahkannya ke peran Akuntansi, peran Sementara 1 tidak akan muncul lagi di akun Anda.

</Accordion>

<div id="dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access" />

<Accordion title="Dashboard dan ketersediaan fitur untuk pengguna dengan sumber media/akses geografis terbatas">

Dashboard AppsFlyer berikut **tidak tersedia** untuk pengguna yang aksesnya terbatas pada sumber media dan lokasi tertentu:

* Ikhtisar SKAN
* Protect360
* Retensi
* Atribusi Berbasis Orang
* Inkrementalitas

Selain itu, fitur AppsFlyer berikut **tidak tersedia** untuk pengguna ini:

* Pivot
* OneLink
* Aturan Validasi
* Audiens (tidak tersedia untuk pengguna yang dibatasi sumber medianya; tersedia untuk pengguna yang dibatasi secara geografis)
* Informasi SDK
* Penyerapan pembelanjaan iklan
* ETL Biaya

</Accordion>

<div id="changing-the-account-owner" />

<Accordion title="Mengubah pemilik akun">

Karena semua Admin pada dasarnya memiliki izin yang sama dengan pemilik akun, maka perubahan pemilik akun biasanya tidak diperlukan. Namun jika ternyata Anda harus mengubah pemilik akun, ikuti langkah-langkah berikut untuk melakukannya.

<div id="important-2" />

> 🚧 **Penting!**
>
> Mengubah pemilik akun harus diselesaikan secara manual sesuai dengan langkah-langkah ini. Itu tidak dapat dilakukan dari halaman **Manajemen pengguna** .

<div id="1assign-a-team-member-the-admin-role" />

#### #1–Kirim permintaan email

Untuk memulai proses perubahan pemilik akun, kirim permintaan email ke AppsFlyer **dari email pemilik akun saat ini.**

* Pastikan ini adalah alamat email pemilik akun saat ini seperti yang muncul di akun AppsFlyer Anda.
* Jika pemilik akun saat ini telah keluar dari perusahaan Anda, minta tim TI Anda untuk mengizinkan Anda mengirim email dari alamat mereka.

Sertakan informasi berikut dalam permintaan Anda:

| Untuk: | CSM AppsFlyer Anda atau hello@appsflyer.com |
| --- | --- |
| CC: | Email pemilik akun baru |
| Subjek: | Permintaan untuk mengubah pemilik akun untuk `{account name}` |
| Body: | Pesan singkat berisi nama dan jabatan pemilik akun baru |

Gunakan contoh email ini sebagai referensi:

![account_owner_change_email.png](https://files.readme.io/eb10736386a7a8cfc274979a3aa933e23288c74d1b26c0f06d72005ceebafe06-31780969048081.png)

<div id="3next-steps" />

#### #2–Langkah selanjutnya

Setelah perubahan diproses, Anda akan menerima notifikasi email dari AppsFlyer.

* Jika Anda ingin pemilik akun sebelumnya terus menggunakan akun AppsFlyer Anda, [buat pengguna baru](/docs/user-management#creating-users) untuk mereka dan tetapkan peran baru untuk mereka.
* API yang menggunakan token v2 tidak terpengaruh oleh perubahan pemilik akun. Namun, jika Anda ingin menyetel ulang token, buka halaman token API dan <Anchor target="_blank" href="/marketers/id/docs/managing-appsflyer-tokens#menyetel-ulang-token-api">setel ulang secara manual</Anchor> setelah pemilik diubah.

</Accordion>

<div id="troubleshooting-can-t-create-this-user" />

<Accordion title="Pemecahan masalah 'Tidak dapat membuat pengguna ini'">

Jika Anda menerima pesan kesalahan *Tidak dapat membuat pengguna ini* saat memasukkan alamat email pengguna baru, biasa artinya email tersebut sudah dikaitkan dengan pengguna AppsFlyer (baik di akun Anda atau di akun lain). Ikuti langkah-langkah yang relevan dengan situasi Anda:

Jika pengguna ada di akun Anda:

* Periksa untuk melihat apakah pengguna telah mengaktifkan akunnya. Jika tidak, [kirim ulang undangan](/docs/user-management#resending-a-user-invitation) jika diperlukan.
* Jika pengguna telah mengaktifkan akunnya, minta mereka untuk mencoba masuk lagi menggunakan alamat email yang terkait dengan penggunanya. Sarankan mereka untuk mengikuti langkah-langkah **Lupa kata sandi** jika diperlukan.

Jika email pengguna digunakan di akun lain atau Anda tidak dapat menentukan akun yang menggunakan email pengguna, pilih salah satu opsi berikut:

* Hapus mereka dari akun lain dan tambahkan ke akun Anda (Anda atau pengguna harus memiliki izin yang diperlukan di akun lain); atau
* Tambahkan mereka ke akun Anda menggunakan alamat email yang berbeda. Ini harus alamat email yang valid di mana mereka benar-benar dapat menerima email; atau
* Hubungi Customer Success Manager (CSM) Anda atau kirim email ke tim Customer Engagement kami di [hello@appsflyer.com](mailto:hello@appsflyer.com).

</Accordion>

<div id="resending-a-user-invitation" />

<Accordion title="Mengirim ulang undangan pengguna">

Jika pengguna baru tidak menerima [undangan aktivasi akun](#aktivasi-pengguna) mereka atau jika mereka tidak melakukan aktivasi dalam waktu 48 jam, Anda dapat mengirim ulang email sebagai berikut:

1. Pada tab **Pengguna** , klik **Tindakan** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> tombol di sisi paling kanan baris pengguna.
   * Perhatikan bahwa pengguna masih ditampilkan dengan ikon amplop ![pending_invitation_icon.png](https://files.readme.io/68ac08ab6e52191a592350f82996f7ade9d181773d0bdbc6e2cb60315b60a8f2-16162502609553.png), menunjukkan bahwa mereka belum mengaktifkan akunnya).
2. Pilih **Kirim ulang undangan email** dari menu.

</Accordion>

<div id="resetting-twofactor-authentication-2fa" />

<Accordion title="Mengatur ulang autentikasi dua faktor (2FA)">

Jika akun Anda menggunakan 2FA, mungkin ada saatnya Anda perlu menyetel ulang setelan 2FA pengguna. Lakukan sebagai berikut:

1. Pada tab **Pengguna** , klik **Tindakan** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> tombol di sisi paling kanan baris pengguna.
2. Pilih **Setel ulang 2FA** dari menu.

**Catatan:** Admin dapat menyetel ulang 2FA admin lain selain milik mereka atau [milik pemilik akun](#pemilik-akun). Untuk mengatur ulang 2FA pemilik akun, hubungi tim Dukungan AppsFlyer.

</Accordion>

<div data-zendesk-anchors="background=latar-belakang h_01H9Q9007QP8YMPDVZ57N4M1HD=latar-belakang more-about-roles=peran h_01H9Q9007Q8CMR2RD6E4KN26YE=peran predefined-roles=peran-yang-telah-ditentukan h_01H9Q9007Q28D43B6JRP71NDQM=peran-yang-telah-ditentukan h_01H9Q9007QXSGG375PR2SCS7QS=contoh custom-roles=peran-khusus h_01H9Q9007QZ7F2TX8B9D1TNYPN=peran-khusus temp-roles=peran-sementara h_01H9Q9007QE8YT1DNRPNTFQWYH=peran-sementara admin%E2%80%94a-special-role=adminperan-khusus h_01H9Q9007Q4A6KETAAGAWEPQQ9=adminperan-khusus access=akses h_01HF8N2Z8ZP3HV06XJPMQ19DTK=akses role-duplication=duplikasi-peran h_01HF8N6DKWYKMBE35QKKB55KEM=duplikasi-peran account-owner=pemilik-akun h_01HF8N69VYE3ZJVFW1ENC0XA62=pemilik-akun user-management-page=halaman-manajemen-pengguna h_01H9Q9007QW1RD3MTTV01Q8QRE=halaman-manajemen-pengguna users-tab=tab-pengguna h_01H9Q9007QJB7XD599VTT89MFX=tab-pengguna roles-tab=tab-peran h_01H9Q9007Q8B4VNDWZEX3Z4WNT=tab-peran managing-users=mengelola-pengguna h_01H9Q9007QYSJZYZMP0C8NA98G=mengelola-pengguna h_01H9Q9007QH3ME2P8PHC9DJBZV=creating-users create-a-user=buat-pengguna h_01HFRD69G8XHPNR83Q71332YTX=buat-pengguna h_01H9Q9007Q6SK4391P8C3A147N=penting h_01H9Q9007R3VH0NMBFX4JZ5THK=catatan user-activation=aktivasi-pengguna h_01HFRCWNR8T5J990TV68K6B45T=aktivasi-pengguna h_01HFRFRQXD1RD66EBRQH0T7Q78=catatan-1 01HFRF6SENRY51A4ZAQJTMTDA3=multiple-accounts h_01HAS6HHHZ5SFFMR741KFYVT7A=catatan-2 supported-accounts-and-users=akun-dan-pengguna-yang-didukung h_01H9Z7XXE0CKRSE191ZN017MGE=akun-dan-pengguna-yang-didukung adding-users-to-multiple-accounts=tambahkan-pengguna-ke-beberapa-akun h_01H9G1MP3Z7VCQQ8ZSQDGSWPC3=tambahkan-pengguna-ke-beberapa-akun h_01H9Q9007RTMXVRMR4RM6J80CW=editing-users individual-editing=pengeditan-perorangan h_01H9Q9007R3QW4AYRJBTF0X7B9=pengeditan-perorangan multiuser-editing=pengeditan-multi-pengguna h_01H9Q9007R4JQPKQS2HVB251GH=pengeditan-multi-pengguna h_01H9Q9007R9M9YDMJ2YYNZDW3D=catatan-3 h_01H9Q9007RAFXB899YK6CADD9R=contoh-1 h_01H9Q9007RF8QKS7YBZ1GRXVCF=deleting-users managing-custom-roles=mengelola-peran-khusus h_01H9Q9007RQHHNHZ3M38E88YPW=mengelola-peran-khusus h_01H9Q9007RYZD19CFNSM60EARZ=creating-custom-roles h_01H9Q9007R6AF9PD8D3Z9GRHSR=catatan-4 h_01H9Q9007R6E6JGD8BC2WY8G3G=editing-custom-roles h_01H9Q9007RANMZP4T6S8R6WA1B=penting-1 h_01H9Q9007R16190B6RB884FY61=deleting-custom-roles special-situations-and-additional-procedures=situasi-khusus-dan-prosedur-tambahan h_01H9Q9007RSWFVAZQ5DNVNN7T2=situasi-khusus-dan-prosedur-tambahan h_01H9Q9007RNZ28128XDB76ZVZC=managing-temp-roles temp-role-limitations=batasan-peran-sementara h_01H9Q9007RJ0CQRGEYNEQJ2QR5=batasan-peran-sementara h_01H9Q9007RHBYD2B6PHQRD7TWV=contoh-2 h_01H9Q9007RRY6QERXQ0C4FSYCN=dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access h_01H9Q9007R221KXA7DFTXJY0PE=changing-the-account-owner h_01H9Q9007RR4M8V599A19B2M0F=penting-2 1%E2%80%93send-an-email-request=1kirim-permintaan-email h_01H9Q9007RSA5406WXCB1E4JRK=1kirim-permintaan-email 2%E2%80%93next-steps=2langkah-selanjutnya h_01H9Q9007RZ2X9RAY8067SZETF=2langkah-selanjutnya troubleshooting-can%E2%80%99t-create-this-user=troubleshooting-can-t-create-this-user h_01H9Q9007RR4VYEPGT90MEHV3T=troubleshooting-can-t-create-this-user h_01H9Q9007R11BQWQZC66X5FV0N=resending-a-user-invitation h_01H9Q9007R72FAH89XW58MWCXT=resetting-twofactor-authentication-2fa" />
