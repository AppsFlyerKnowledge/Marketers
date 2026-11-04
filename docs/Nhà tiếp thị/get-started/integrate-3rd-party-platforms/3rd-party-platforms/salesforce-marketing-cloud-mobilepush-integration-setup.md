---
title: Cài đặt tích hợp Salesforce Marketing Cloud MobilePush
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-14T06:37:05Z'
  edited_at: '2023-09-16T14:07:04Z'
  id: 10590769196817
  locale: vi
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/vi/articles/10590769196817
---
> **Tổng quan:** Salesforce Marketing Cloud MobilePush, một đối tác tích hợp của AppsFlyer, là một nền tảng thu hút người dùng cho các nhóm tiếp thị, phát triển và tương tác.

<div id="overview" />

## Tổng quan

Salesforce Marketing Cloud MobilePush cho phép bạn tạo và gửi các tin nhắn đẩy nhắm mục tiêu dựa trên dữ liệu người tiêu dùng đa kênh. Điều này giúp khuyến khích sử dụng ứng dụng và đem lại ROI gia tăng. Với MobilePush, bạn có thể xem cách người dùng điều hướng qua ứng dụng của bạn, từ các sản phẩm họ xem đến thời gian dành trên mỗi trang. Tích hợp MobilePush cho phép bạn:

* Thúc đẩy tương tác và thương mại di động
* Nhận thông tin chi tiết đáng giá về người dùng
* Dễ dàng xây dựng các chiến dịch đa kênh
* Phân đoạn và lên lịch các tin nhắn

<div id="important" />

> 🚧 **Quan trọng!**
>
> <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions#hạn-chế-nguồn-truyền-thông">Một số nguồn truyền thông</Anchor> hạn chế chia sẻ dữ liệu với các bên thứ ba. Do đó, đăng lại cho các sự kiện bị hạn chế sẽ không được gửi tới đối tác này, bất kể lựa chọn đã định cấu hình để gửi đăng lại là gì.

<div id="setting-up-salesforce-marketing-cloud-mobilepush" />

## Thiết lập Salesforce Marketing Cloud MobilePush

Đa phần quá trình cài đặt được thực hiện trong SalesForce (bước 1-4). Bước 5 được thực hiện trong AppsFlyer.

<div id="step-1-set-up-mobilepush-sdk" />

### Bước 1: Thiết lập SDK MobilePush

* <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_get_started.htm&type=5">Triển khai cài đặt SDK MobilePush</Anchor>

<div id="step-2-provision-for-push-notifications" />

### Bước 2: Cung cấp thông báo đẩy

* <Anchor target="_blank" href="https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-provision.html">Tạo một `chứng chỉ` .p12</Anchor>

<div id="step-3-enable-app-push-notifications" />

### Bước 3: Bật thông báo đẩy của ứng dụng

* <Anchor target="_blank" href="https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-configureforpush.html">Triển khai thông báo đẩy</Anchor>

<div id="step-4-set-up-app-push-notifications" />

### Bước 4: Thiết lập thông báo đẩy của ứng dụng

* <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_outbound_message.htm&type=5">Tạo và gửi tin nhắn đẩy đến các thiết bị di động</Anchor>

<div id="note" />

> 📘 **Lưu ý**
>
> Khi tạo một thông báo đẩy trên đám mây tiếp thị của Salesforce, cần phải thêm một <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_custom_keys.htm&type=5">khóa tùy chỉnh</Anchor> để AppsFlyer có thể phân bổ đúng cách với PID và phân bổ chiến dịch chính xác. Sử dụng `AF_xxxxxxxxx` làm khóa tùy chỉnh.

<div id="step-5-set-up-push-notifications-in-appsflyer" />

### Bước 5: Thiết lập thông báo đẩy trong AppsFlyer

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications-ios#addpushnotificationdeeplinkpath-recommended">Cấu hình SDK iOS bằng OneLink (bước 3 trong liên kết này)</Anchor>

<div id="note-1" />

> 📘 **Lưu ý**
>
> Đảm bảo khóa tùy chỉnh `AF_xxxxxxxxx` bạn nhập trong [bước 4](/docs/salesforce-marketing-cloud-mobilepush-integration-setup#bước-4-thiết-lập-thông-báo-đẩy-của-ứng-dụng) có cùng giá trị với khóa bạn nhập trong chức năng `addPushNotificationDeepLinkPath`.

<div data-zendesk-anchors="overview=t%E1%BB%95ng-quan h_01H9HWK3F5TQZ8YQZBHGBZACPG=t%E1%BB%95ng-quan h_01H9HWK5DM87JTDVFND0KB965G=quan-tr%E1%BB%8Dng setting-up-salesforce-marketing-cloud-mobilepush=thi%E1%BA%BFt-l%E1%BA%ADp-salesforce-marketing-cloud-mobilepush h_01H9HWK3F52YGQPX4B82N40PPD=thi%E1%BA%BFt-l%E1%BA%ADp-salesforce-marketing-cloud-mobilepush step-1-set-up-mobilepush-sdk=b%C6%B0%E1%BB%9Bc-1-thi%E1%BA%BFt-l%E1%BA%ADp-sdk-mobilepush h_01H9HWK3F5HCVZ0225MFRYRW5Q=b%C6%B0%E1%BB%9Bc-1-thi%E1%BA%BFt-l%E1%BA%ADp-sdk-mobilepush step-2-provision-for-push-notifications=b%C6%B0%E1%BB%9Bc-2-cung-c%E1%BA%A5p-th%C3%B4ng-b%C3%A1o-%C4%91%E1%BA%A9y h_01H9HWK3F5RNCZG340E0CT5XJC=b%C6%B0%E1%BB%9Bc-2-cung-c%E1%BA%A5p-th%C3%B4ng-b%C3%A1o-%C4%91%E1%BA%A9y step-3-enable-app-push-notifications=b%C6%B0%E1%BB%9Bc-3-b%E1%BA%ADt-th%C3%B4ng-b%C3%A1o-%C4%91%E1%BA%A9y-c%E1%BB%A7a-%E1%BB%A9ng-d%E1%BB%A5ng h_01H9HWK3F5E4W8FG35V4JTFN7F=b%C6%B0%E1%BB%9Bc-3-b%E1%BA%ADt-th%C3%B4ng-b%C3%A1o-%C4%91%E1%BA%A9y-c%E1%BB%A7a-%E1%BB%A9ng-d%E1%BB%A5ng step-4-set-up-app-push-notifications=b%C6%B0%E1%BB%9Bc-4-thi%E1%BA%BFt-l%E1%BA%ADp-th%C3%B4ng-b%C3%A1o-%C4%91%E1%BA%A9y-c%E1%BB%A7a-%E1%BB%A9ng-d%E1%BB%A5ng h_01H9HWK3F5K8V8AVADXNNG25GY=b%C6%B0%E1%BB%9Bc-4-thi%E1%BA%BFt-l%E1%BA%ADp-th%C3%B4ng-b%C3%A1o-%C4%91%E1%BA%A9y-c%E1%BB%A7a-%E1%BB%A9ng-d%E1%BB%A5ng h_01H9HWK3F5VG2GBCE93B69AADH=l%C6%B0u-%C3%BD step-5-set-up-push-notifications-in-appsflyer=b%C6%B0%E1%BB%9Bc-5-thi%E1%BA%BFt-l%E1%BA%ADp-th%C3%B4ng-b%C3%A1o-%C4%91%E1%BA%A9y-trong-appsflyer h_01H9HWK3F5YJ71YCWHV4B02VYP=b%C6%B0%E1%BB%9Bc-5-thi%E1%BA%BFt-l%E1%BA%ADp-th%C3%B4ng-b%C3%A1o-%C4%91%E1%BA%A9y-trong-appsflyer h_01H9HWK3F5T67NSPE9CVPS1KTA=l%C6%B0u-%C3%BD-1" />
