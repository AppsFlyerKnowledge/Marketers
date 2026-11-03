---
title: Integrasi Tealium dengan AppsFlyer
metadata:
  keywords:
    - Marketers
    - TEST ID LOC
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-22T16:09:24Z'
  edited_at: '2024-02-14T08:41:05Z'
  id: 10820404821393
  locale: id
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/id/articles/10820404821393
---
> **Sekilas:** Tealium, Platform Data Pelanggan (CDP), menghubungkan data pelanggan di seluruh web, seluler, IoT, dan offline. Pelajari cara membagikan data konversi secara otomatis dengan Tealium.

<Image alt="Tealium_icon.png" src="https://files.readme.io/e3cc1f95e8ce2de6fa83df63ff78dd4f4f76aebe1acb8e9378aa5b6aa4134364-10820461521681.png" width="276px" />

## Overview

Dengan mengintegrasikan Tealium dengan AppsFlyer, pelanggan seluler dapat memanfaatkan SDK atribusi seluler AppsFlyer dan mengirimkan data konversi atribusi langsung ke profil Tealium AudienceStream mereka.

> 🚧 **Penting!**
>
> <Anchor target="_blank" href="/marketers/id/docs/about-raw-data-identifier-restrictions#pembatasan-sumber-media">Beberapa sumber media</Anchor> membatasi pembagian data dengan pihak ketiga. Oleh karena itu, postback untuk event terbatas tidak akan dikirim ke mitra ini, terlepas dari pilihan yang dikonfigurasi untuk mengirim postback.

## Menyiapkan Tealium

Anda dapat memilih salah satu cara berikut untuk mengintegrasikan Tealium dengan AppsFlyer:

* Integrasi sisi klien
* Integrasi sisi server

### Integrasi sisi klien

Gunakan perintah jarak jauh untuk perpustakaan iOS dan Android, yang memungkinkan kode asli dipicu di SDK AppsFlyer.

**Untuk mengintegrasikan Tealium menggunakan integrasi sisi klien:**

* Ikuti <Anchor target="_blank" href="https://docs.tealium.com/platforms/remote-commands/integrations/appsflyer/">panduan integrasi perintah jarak jauh</Anchor>

### Integrasi sisi server

Siapkan konektor App Events AppsFlyer di akun Pusat Data Pelanggan Anda untuk mengirimkan data antara Tealium dan AppsFlyer secara waktu sebenarnya.

**Untuk mengintegrasikan Tealium menggunakan integrasi sisi server:**

* Ikuti <Anchor target="_blank" href="https://docs.tealium.com/server-side-connectors/appsflyer-app-events-connector/">panduan konektor Event Aplikasi AppsFlyer</Anchor>

<div data-zendesk-anchors="h_01H9HWK1ACY09ZVD7WHEQR4MR3=overview h_01H9HWK1ACA6A743PDY3Q1Y0KV=penting setting-up-tealium=menyiapkan-tealium h_01H9HWK1AC27GPZPZR13SFC3GM=menyiapkan-tealium clientside-integration=integrasi-sisi-klien h_01H9HWK1ACH6K0FDTVCHAPSKME=integrasi-sisi-klien serverside-integration=integrasi-sisi-server h_01H9HWK1ACDZQEYVRZ7QWQ4KY3=integrasi-sisi-server" />
