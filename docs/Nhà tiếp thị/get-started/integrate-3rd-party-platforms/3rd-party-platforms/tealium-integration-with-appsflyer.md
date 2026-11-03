---
title: Tích hợp Tealium với AppsFlyer
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
  edited_at: '2024-02-14T08:41:09Z'
  id: 10820404821393
  locale: vi
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/vi/articles/10820404821393
---
> **Khái quát:** Tealium, một Nền tảng Dữ liệu Khách hàng (CDP), kết nối dữ liệu khách hàng trên web, thiết bị di động, IoT và ngoại tuyến. Tìm hiểu cách tự động chia sẻ dữ liệu chuyển đổi với Tealium.

<Image alt="Tealium_icon.png" src="https://files.readme.io/e3cc1f95e8ce2de6fa83df63ff78dd4f4f76aebe1acb8e9378aa5b6aa4134364-10820461521681.png" width="276px" />

## Tổng quan

Bằng cách tích hợp Tealium với AppsFlyer, khách hàng di động có thể tận dụng SDK phân bổ di động AppsFlyer và gửi dữ liệu chuyển đổi phân bổ trực tiếp đến hồ sơ Tealium AudienceStream của họ.

> 🚧 **Quan trọng!**
>
> <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions#hạn-chế-nguồn-truyền-thông">Một số nguồn truyền thông</Anchor> hạn chế chia sẻ dữ liệu với các bên thứ ba. Do đó, đăng lại cho các sự kiện bị hạn chế sẽ không được gửi tới đối tác này, bất kể lựa chọn đã định cấu hình để gửi đăng lại là gì.

## Thiết lập Tealium

Bạn có thể chọn một trong các cách sau để tích hợp Tealium với AppsFlyer:

* Tích hợp phía máy khách
* Tích hợp phía máy chủ

### Tích hợp phía máy khách

Sử dụng lệnh từ xa cho thư viện iOS và Android, cho phép kích hoạt mã gốc trong SDK AppsFlyer.

**Để tích hợp Tealium bằng chức năng tích hợp phía máy khách:**

* Làm theo <Anchor target="_blank" href="https://docs.tealium.com/platforms/remote-commands/integrations/appsflyer/">hướng dẫn tích hợp lệnh từ xa</Anchor>

### Tích hợp phía máy chủ

Thiết lập trình kết nối Sự kiện trong Ứng dụng AppsFlyer trong tài khoản Trung tâm Dữ liệu Khách hàng của bạn để truyền dữ liệu giữa Tealium và AppsFlyer trong thời gian thực.

**Để tích hợp Tealium bằng chức năng tích hợp phía máy chủ:**

* Làm theo <Anchor target="_blank" href="https://docs.tealium.com/server-side-connectors/appsflyer-app-events-connector/">hướng dẫn kết nối Sự kiện trong Ứng dụng AppsFlyer</Anchor>

<div data-zendesk-anchors="overview=t%E1%BB%95ng-quan h_01H9HWK1ACY09ZVD7WHEQR4MR3=t%E1%BB%95ng-quan h_01H9HWK1ACA6A743PDY3Q1Y0KV=quan-tr%E1%BB%8Dng setting-up-tealium=thi%E1%BA%BFt-l%E1%BA%ADp-tealium h_01H9HWK1AC27GPZPZR13SFC3GM=thi%E1%BA%BFt-l%E1%BA%ADp-tealium clientside-integration=t%C3%ADch-h%E1%BB%A3p-ph%C3%ADa-m%C3%A1y-kh%C3%A1ch h_01H9HWK1ACH6K0FDTVCHAPSKME=t%C3%ADch-h%E1%BB%A3p-ph%C3%ADa-m%C3%A1y-kh%C3%A1ch serverside-integration=t%C3%ADch-h%E1%BB%A3p-ph%C3%ADa-m%C3%A1y-ch%E1%BB%A7 h_01H9HWK1ACDZQEYVRZ7QWQ4KY3=t%C3%ADch-h%E1%BB%A3p-ph%C3%ADa-m%C3%A1y-ch%E1%BB%A7" />
