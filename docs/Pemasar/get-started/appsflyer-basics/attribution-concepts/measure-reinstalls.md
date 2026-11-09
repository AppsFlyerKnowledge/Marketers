---
title: Penginstalan ulang
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2022-10-27T07:37:21Z'
  edited_at: '2023-08-15T12:04:32Z'
  id: 10164066030737
  locale: id
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/id/articles/10164066030737
---
> **Sekilas**: Penginstalan ulang terjadi saat pengguna menginstal aplikasi, menghapusnya, lalu menginstalnya ulang. Penginstalan ulang menghasilkan salah satu jenis atribusi berikut ini: penginstalan ulang non-organik, penginstalan ulang organik, atau atribusi ulang (penargetan ulang). Penginstalan ulang membantu menghindari beberapa biaya bagi pengguna yang mencopot pemasangan dan menginstalnya ulang.

<div id="what-is-a-reinstall" />

## Apa itu penginstalan ulang

Penginstalan ulang terjadi saat pengguna aplikasi menghapus aplikasi lalu menginstal ulang aplikasi selama <Anchor target="_blank" href="/marketers/id/docs/set-up-re-attribution-window#re-attribution-window">jendela atribusi ulang.</Anchor>

Penginstalan ulang dapat berasal dari kampanye penargetan ulang (atribusi ulang), sumber organik, atau sumber non-organik.

Penginstalan ulang yang berasal dari sumber organik, atau sumber non-organik, dan berada di <Anchor target="_blank" href="/marketers/id/docs/set-up-re-attribution-window#re-attribution-window">jendela atribusi ulang</Anchor>, disebut sebagai penginstalan ulang.

Penginstalan ulang yang berasal dari kampanye penargetan ulang disebut sebagai atribusi ulang.

Ini berbeda dalam cara penginstalan ulang dan in-app event dikaitkan.

Jika penginstalan terjadi di luar <Anchor target="_blank" href="/marketers/id/docs/set-up-re-attribution-window#re-attribution-window">jendela atribusi ulang</Anchor>, penginstalan ulang disebut <Anchor target="_blank" href="/marketers/id/docs/set-up-re-attribution-window#new-install">penginstalan baru</Anchor>. Penginstalan baru dikaitkan ke sumber media (atau organik jika tidak ada interaksi yang dicatat) dan jendela atribusi ulang baru akan dimulai.

Tabel di bawah menunjukkan apa yang AppsFlyer sebut sebagai penginstalan ulang yang berbeda

| Sumber penginstalan ulang | Apakah jendela atribusi ulang valid? | Apakah pengguna berinteraksi dengan kampanye penargetan ulang sebelum menginstal ulang? | Apakah pengguna berinteraksi dengan kampanye UA sebelum menginstal ulang? | Namanya |
| --- | --- | --- | --- | --- |
| Dari kampanye penargetan ulang | Ya | Ya | Tidak | Atribusi ulang |
| Dari sumber organik atau non-organik | Ya | Tidak | Ya atau Tidak | Penginstalan ulang |
| Dari sumber organik atau non-organik | Tidak | Tidak | Ya atau Tidak | Instal baru |

<div id="why-are-reinstalls-important" />

## Mengapa menginstal ulang itu hal penting

Selain menjadi indikasi yang baik bahwa pengguna kembali ke aplikasi Anda dan bahwa kampanye Anda berfungsi, atribusi penginstalan ulang yang tepat penting untuk membantu menghindari beberapa tagihan bagi pengguna yang menghapus penginstalan dan menginstal lagi dalam <Anchor target="_blank" href="/marketers/id/docs/set-up-re-attribution-window#re-attribution-window">jendela atribusi ulang.</Anchor>

Demikian pula, menghubungkan in-app event dari penginstalan ulang ke sumber media asli (penginstalan pertama) memberikan gambaran yang lebih baik kepada pemasang iklan tentang bagaimana pengguna terlibat. Ini juga menunjukkan seberapa efektif kampanye UA dan iklan Penargetan Ulang. Untuk informasi selengkapnya, lihat [in-app event](/docs/measure-reinstalls#in-app-event) di bawah ini.

<div id="reinstall-flow-and-outcome" />

## Alur dan hasil penginstalan ulang

<div id="reinstall" />

<Accordion title="Penginstalan ulang">

Setelah penginstalan aplikasi pertama, pengguna menghapus penginstalan, lalu menginstal ulang selama <Anchor target="_blank" href="/marketers/id/docs/set-up-re-attribution-window#re-attribution-window">jendela atribusi ulang</Anchor>. Penginstalan ulang dapat berasal dari kampanye organik atau UA (lihat [contoh](/docs/measure-reinstalls#examples)).

Hal berikut terjadi:

* Penginstalan TIDAK dikaitkan - tidak muncul di dashboard atau di data
* TIDAK ADA penginstalan postback dikirim ke sumber media apa pun
* Lihat [in-app event](/docs/measure-reinstalls#in-app-event) untuk informasi tentang bagaimana in-app event dikaitkan

</Accordion>

<div id="reattribution" />

<Accordion title="Atribusi ulang">

Setelah penginstalan aplikasi pertama, pengguna mencopot pemasangan, lalu terlibat dalam kampanye penargetan ulang, dan menginstal ulang selama <Anchor target="_blank" href="/marketers/id/docs/set-up-re-attribution-window#re-attribution-window">jendela atribusi ulang</Anchor>.  

Hal berikut terjadi:

* Penginstalan dikaitkan ke sumber media penargetan ulang dalam tampilan penargetan ulang dan terpadu dari dashboard Ringkasan
  * Tampilan akuisisi pengguna tidak berisi atribusi ulang
* Semua in-app event berikut dikaitkan ke sumber media penargetan ulang (lihat [in-app event](/docs/measure-reinstalls#in-app-event) untuk informasi lebih lanjut)
* Postback penginstalan dikirim ke sumber media penargetan ulang

Untuk informasi Atribusi Penargetan Ulang lainnya, klik <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide">di sini</Anchor>.

</Accordion>

<div id="postreinstall-events-attribution-state" />

<div id="note" />

<div id="post-reinstall-in-app-events" />

## In-App Event

### Ringkasan

<Image align="center" alt="" src="https://files.readme.io/2376efb764026f9cb3c585e8145ae6cf361c3e887c8478ec82709caea63feb1a-10485524792337.jpg" />

In-app event yang dilakukan oleh pengguna setelah penginstalan ulang, dapat diatributkan secara organik, dikaitkan non-organik, atau organik yang tidak dikaitkan bergantung pada status **atribusi Event Setelah Penginstalan Ulang** (lihat di bawah).

Contoh in-app event adalah pengguna yang menginstal ulang aplikasi, lalu melakukan pembelian dalam aplikasi.

#### In-app event dan bagaimana mereka dikaitkan

<table><tbody><tr><th>Status Atribusi Event Setelah Penginstalan Ulang</th><th>Setelah Penginstalan Ulang</th><th>Setelah Atribusi Ulang</th></tr><tr><td><strong>Dihubungkan sebagai in-app organik</strong></td><td>organik tanpa atribusi</td><td>Penargetan ulang</td></tr><tr><td> <strong>Dihubungkan dengan penginstalan pertama</strong><span>(1)</span> </td><td>sumber media penginstalan pertama</td><td>Penargetan ulang <span>(2)</span> </td></tr><tr><td colspan="3"><p><span>(1) Lihat batasan di bawah ini</span></p><p><span>(2) Di bidang sumber primer. Sumber media penginstalan pertama akan dicantumkan di kolom sumber sekunder (A<span>nda hanya akan melihatnya di data lengkap).</span></span></p></td></tr></tbody></table>

<div id="unattributed-organic-inapps" />

<Accordion title="In-app organik tanpa atribut">

Penginstalan ulang

* Semua in-app event dihitung sebagai organik atau diabaikan sepenuhnya bergantung pada dashboard.
* In-app event akan dilaporkan dengan conversion\_type dan campaign\_type sebagai "unknown" (tidak dikenal)
* Tanggal yang digunakan untuk menggabungkan data bergantung pada event:
  * Untuk sebagian besar in-app event yang berasal dari SDK, tanggal pengunduhan aplikasi digunakan untuk menggabungkan data; bukan tanggal penginstalan ulang.
  * Untuk event pendapatan iklan (af\_ad\_revenue) yang dikirim oleh konektor SDK, tanggal penginstalan ulang digunakan untuk menggabungkan data.

Atribusi ulang

* Semua in-app event dikaitkan ke sumber media penargetan ulang

</Accordion>

<div id="attributed-to-the-first-install" />

<Accordion title="Dikaitkan dengan penginstalan pertama">

> 🚧 **Prasyarat**
>
> Memerlukan pengaktifan. Hubungi CSM Anda untuk berdiskusi.

#### Tujuan

Memberi pemasang iklan gambaran yang lebih baik tentang bagaimana pengguna terlibat. Menunjukkan seberapa efektif kampanye UA dan iklan Penargetan Ulang dengan mengatribusikan in-app event ke sumber asli, bukan organik.

#### Penginstalan ulang

* Semua in-app event yang dihasilkan dari penginstalan ulang dikaitkan ke penginstalan awal (1)

#### Atribusi ulang

* Semua in-app event dikaitkan ke iklan penargetan ulang di sumber utama dan penginstalan awal di sumber sekunder. (2)

(1) Lihat [batasan di bawah ini.](/docs/measure-reinstalls#limitations)

(2) Anda hanya akan melihat ini di data lengkap.

<div id="note-1" />

#### Catatan

Data KPI organik di dashboard mungkin menampilkan nilai yang lebih rendah dengan **Post Reinstall Events Attribution** diatur ke **Attributed to the first install** karena beberapa dari angka tersebut sekarang mungkin dikaitkan dengan sumber media non-organik

</Accordion>

<div id="examples" />

<Accordion title="Contoh">

<div id="confirm-inapps-are-attributed-to-the-original-install" />

<div id="examples-for-first-install-mode-attribution" />

#### Dengan **Attributed to the first install** diaktifkan.

**Contoh 1**

Pengguna menginstal aplikasi (hari ke-0), melakukan pembelian seharga $10, lalu menghapus penginstalan aplikasi.

Hari berikutnya (hari 1), pengguna menginstal ulang aplikasi dan melakukan pembelian sebesar $5.

<Image align="center" alt="Reinstall_1.jpg" src="https://files.readme.io/7e8eccb3a6873b42a1d8503c0f027386728adb2eecbe457451d2e37c0a7b6774-10225445609873.jpg" />

Karena pengguna sudah melakukan pembelian sebelum menginstal ulang, tidak akan ada jumlah pengguna unik tambahan.

| Sumber media | pengguna | Af\_purchase:<br /><br />Pengguna Unik<br /><br />Hari 0 | Af\_purchase:<br /><br />Pengguna Unik<br /><br />Hari 1 (kumulatif) | Pendapatan<br /><br />Hari 0 | Pendapatan<br /><br />Hari 1 (kumulatif) |
| --- | --- | --- | --- | --- | --- |
| Media\_source\_A | 1 | 1 | 1 | $10 | $15 |

Kami akan melihat peningkatan pendapatan di bawah `device_identifier` yang sama.

| Appsflyer\_id | Pengenal perangkat | Sumber media | Nama Event | Tanggal Event |
| --- | --- | --- | --- | --- |
| 111 | XXX | media\_source\_A | install | hari 0 |
| 111 | XXX | media\_source\_A | af\_purchase | hari 0 |
| 222 | XXX | organik | instal ulang | hari 1 |
| 222 | XXX | media\_source\_A | af\_purchase | hari 1 |

**Contoh 2**

Pengguna menginstal aplikasi (hari 0), melakukan pembelian, lalu menghapus instalasi aplikasi.

Hari berikutnya (hari 1), pengguna menginstal ulang aplikasi dari kampanye UA dan melakukan pembelian.

| Sumber media | Nama Event | Tanggal Event | Atribusi penginstalan ulang | Atribusi in-app event |
| --- | --- | --- | --- | --- |
| media\_source\_A | install | hari 0 | media\_source\_A |  |
| media\_source\_A | af\_purchase | hari 0 |  | media\_source\_A |
| media\_source\_B | instal ulang | hari 1 | media\_source\_B |  |
| media\_source\_B | af\_purchase | hari 1 |  | media\_source\_A |

</Accordion>

<div id="limitations" />

<Accordion title="Batasan">

* Hanya pengguna yang telah setuju untuk membagikan pengenal perangkat mereka (seperti IDFA atau GAID) dengan aplikasi, baik untuk penginstalan maupun penginstalan ulang yang akan mendapatkan in-app event yang dikaitkan ke penginstalan awal
  * Pengenal perangkat pada penginstalan pertama dan penginstalan ulang harus cocok
* Penginstalan ulang harus terjadi dalam <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide#reengagement-rules-and-windows">jendela atribusi ulang</Anchor> dari penginstalan terakhir yang tercatat.
* Event pendapatan iklan dikaitkan sebagai organik
* Setiap penginstalan dan penginstalan ulang akan tetap memiliki `appsflyer_id` uniknya sendiri
* Dashboard tidak membedakan antara in-app event setelah penginstalan atau penginstalan ulang
  * Mungkin untuk melihat ini melalui data lengkap

</Accordion>

<div id="how-does-the-data-appear-in-the-appsflyer-dashboards" />

## Bagaimana data muncul di dashboard AppsFlyer

<table><tbody><tr><th colspan="2"> </th><th>Penginstalan ulang non-organik</th><th>Penginstalan ulang organik </th><th>Atribusi ulang</th></tr><tr><td colspan="2">Penginstalan ulang sendiri</td><td>Tidak terlihat</td><td>Tidak terlihat</td><td><span>Menargetkan ulang sumber media\*</span></td></tr><tr><td rowspan="2">Atribusi in-app event ke depannya</td><td>Event Setelah Penginstalan Ulang diatur ke <strong>Attributed as organic in-apps</strong> </td><td>Organik tanpa atribusi</td><td>Organik tanpa atribusi</td><td><span>Menargetkan ulang sumber media</span></td></tr><tr><td>Event Setelah Penginstalan Ulang diatur ke <strong>Attributed to the first install</strong> </td><td>Sumber media pertama</td><td>Sumber media pertama</td><td>Kampanye penargetan ulang</td></tr><tr><td colspan="5">\*Hanya di dashboard ringkasan.</td></tr></tbody></table>

<div id="reinstalls-raw-data-reports" />

## Menginstal ulang laporan data lengkap

<div id="prerequisites" />

> 🚧 **Prasyarat**
>
> Memerlukan pengaktifan. Hubungi CSM Anda untuk membahas hal ini.

* <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQtlerXtCVImurv-JyuG7JMPvLN6p2w79pmbMNBx6WBnLwnYq5bUqXiUuoy2l_UTzEjIr8UkDdclRxf/pub?output=csv">Instal ulang laporan contoh sebagai file CSV</Anchor>

<div id="how-the-install-and-in-app-events-are-attributed" />

#### Cara penginstalan dan in-app event dikaitkan

<table><tbody><tr><th colspan="2"> </th><th>Penginstalan ulang non-organik</th><th>Penginstalan ulang organik </th><th>Atribusi ulang</th><th>Penginstalan non-organik</th><th>Penginstalan organik</th></tr><tr><td colspan="2">Dikaitkan ke </td><td>kampanye UA</td><td>Organik</td><td>Kampanye penargetan ulang</td><td>kampanye UA</td><td>Organik</td></tr><tr><td rowspan="2">Atribusi event ke depannya</td><td>Event Setelah Penginstalan Ulang diatur ke <strong>Attributed as organic in-apps</strong> </td><td>Organik</td><td>Organik</td><td>Kampanye penargetan ulang</td><td>kampanye UA</td><td>Organik</td></tr><tr><td>Event Setelah Penginstalan Ulang diatur ke <strong>Attributed to the first install</strong> </td><td>Penginstalan pertama</td><td>Penginstalan pertama</td><td>Kampanye penargetan ulang</td><td>kampanye UA</td><td>Organik</td></tr></tbody></table>

<div id="availability-of-reinstall-reports" />

### Ketersediaan laporan penginstalan ulang

* Laporan penginstalan ulang data lengkap tersedia menggunakan alat pengiriman yang dirinci dalam tabel berikut.
* Laporan memiliki struktur yang sama dan diisi dengan cara yang sama untuk menginstal laporan dalam hal:
  * Bidang **sumber media** diisi menggunakan sumber media yang membawa penginstalan ulang atau organik.
  * **Waktu penginstalan** : Tafsirkan sebagai waktu penginstalan ulang, artinya waktu aplikasi pertama dibuka setelah penginstalan ulang
  * **Nama event:** *Penginstalan ulang*

| Laporkan metode pengiriman | Penginstalan ulang non-organik | Penginstalan ulang organik |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/id/docs/raw-data-reporting-overview">Ekspor data</Anchor> | ✓ | ✓ |
| <Anchor target="_blank" href="/marketers/id/docs/pull-api-aggregate-data">API Pull</Anchor> | ✓ | ✓ |
| <Anchor target="_blank" href="/marketers/id/docs/data-locker-for-marketers">Data Locker</Anchor> | ✓ | ✓ |
| API Push | ✓ | ✓ |

<div data-zendesk-anchors="what-is-a-reinstall=apa-itu-penginstalan-ulang 01H7SZVZPGHBQ7VM8TMWRD3CE4=apa-itu-penginstalan-ulang why-are-reinstalls-important=mengapa-menginstal-ulang-itu-hal-penting 01H7SZVZPG6T2AW9B3EMT29AQQ=mengapa-menginstal-ulang-itu-hal-penting reinstall-flow-and-outcome=alur-dan-hasil-penginstalan-ulang 01H7SZVZPGVQCNCQ7TCZMYM33T=alur-dan-hasil-penginstalan-ulang 01H7SZVZPGCDP3GRK1BWZ04MR6=reinstall 01H7SZVZPG8WNTK30YXNZ44VTS=reattribution inapp-events=in-app-event 01H7SZVZPGBYRWZGAZRT36EFGH=in-app-event overview=ringkasan 01H7SZVZPGK7X1NXW467CZP1KJ=ringkasan inapp-events-and-how-they-are-attributed=in-app-event-dan-bagaimana-mereka-dikaitkan 01H7SZVZPHW7E5WV9C643BG6YB=in-app-event-dan-bagaimana-mereka-dikaitkan 01H7SZVZPH4AE1PZK8V5JG6C6X=unattributed-organic-inapps 01H7SZVZPH7KPM7T42GHZ7N69S=attributed-to-the-first-install 01H7SZVZPHBQ7E3R107EB2KXES=prasyarat purpose=tujuan 01H7SZVZPHXBX6J2APBXS30CPX=tujuan reinstall::7f2d499b=penginstalan-ulang 01H7SZVZPHRJ9WPW3TCYECK50W=penginstalan-ulang reattribution::bbb1aabb=atribusi-ulang 01H7SZVZPHZFY9ZDEQYP967C2D=atribusi-ulang 01H7SZVZPH5YGSMPGW7NPKXJAF=catatan 01H7SZVZPHF3R44DTHCD9QHPR8=examples with-attributed-to-the-first-install-enabled=dengan-attributed-to-the-first-install-diaktifkan 01H7SZVZPHH3DS9J4VRD70VTX6=dengan-attributed-to-the-first-install-diaktifkan 01H7SZVZPH8MSBQ92XWFK0HWGQ=limitations how-does-the-data-appear-in-the-appsflyer-dashboards=bagaimana-data-muncul-di-dashboard-appsflyer 01H7SZVZPHHQS4NHEDATD7ZP9V=bagaimana-data-muncul-di-dashboard-appsflyer reinstalls-raw-data-reports=menginstal-ulang-laporan-data-lengkap 01H7SZVZPHPWN8REBQ5CWVFNJT=menginstal-ulang-laporan-data-lengkap 01H7SZVZPHCVDPDDYD6HHNFMMK=prasyarat-1 how-the-install-and-inapp-events-are-attributed=cara-penginstalan-dan-in-app-event-dikaitkan 01H7SZVZPHQT8XS3ZBA4W682GB=cara-penginstalan-dan-in-app-event-dikaitkan availability-of-reinstall-reports=ketersediaan-laporan-penginstalan-ulang 01H7SZVZPH6NY7FMG9YHDBB95R=ketersediaan-laporan-penginstalan-ulang" />
