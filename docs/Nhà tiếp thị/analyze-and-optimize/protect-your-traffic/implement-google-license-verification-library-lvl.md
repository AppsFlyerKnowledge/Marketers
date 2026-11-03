---
title: Thiết lập Thư viện Xác minh Giấy phép (LVL) của Google
metadata:
  keywords:
    - Premium
    - Premium Feature
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2023-07-27T14:45:46Z'
  edited_at: '2024-07-08T13:52:23Z'
  id: 17329535522961
  locale: vi
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/vi/articles/17329535522961
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Sơ lược:** Bảo vệ ứng dụng của bạn khỏi việc sử dụng trái phép bằng cách thêm Thư viện Xác minh Giấy phép (LVL) của Google để xử lý tất cả các giao tiếp liên quan đến giấy phép với Google Play.

## Tổng quan

Thư viện Xác minh Giấy phép (LVL) là thư viện bạn có thể thêm vào ứng dụng của mình (có thể tải xuống từ SDK Android) để xử lý tất cả các giao tiếp liên quan đến cấp phép với dịch vụ cấp phép của Google Play.

Thư viện này bổ sung thêm một lớp bảo vệ khác, bên cạnh các thuật toán Protect360, bằng cách bật xác minh rằng các lượt cài đặt đến từ người dùng Google Play thực sự. Điều này giúp giảm sự khác biệt giữa số lượt cài đặt hiển thị trên Google Play và bảng điều khiển AppsFlyer.

Dịch vụ Cấp phép của Google Play xác định xem người dùng có được cấp phép sử dụng ứng dụng hay không. Google Play coi người dùng là đã cấp phép nếu họ là người mua ứng dụng được ghi nhận. Giấy phép này là duy nhất cho mỗi ứng dụng và có thể được sử dụng để tăng cường bảo vệ. <Anchor target="_blank" href="https://developer.android.com/google/play/licensing">Tìm hiểu thêm</Anchor>

SDK AppsFlyer thu thập dữ liệu từ phía khách hàng và Protect360 thực hiện xác minh giấy phép phía máy chủ, chặn các lượt cài đặt gian lận không xác minh thành công cho cả lượt cài đặt tự nhiên và không tự nhiên. “Lý do chặn” bạn sẽ thấy trong bảng điều khiển Protect360 và các báo cáo sẽ là “Bot”.

## Thiết lập LVL

<div id="add-lvl" />

<Accordion title="Thêm LVL">

Hiện tại, đây là quy trình thủ công, trong đó bạn sẽ cần chuyển thông tin bên dưới tới CSM AppsFlyer của mình để họ có thể thêm thông tin đó theo cách thủ công.

**Để thêm LVL:**

1. Đảm bảo bạn có phiên bản SDK 5.4.3 trở lên để thêm SDK mới nhất vào triển khai build.gradle. **Lưu ý:** khuyến khích sử dụng phiên bản 6.12.3 trở lên.   

   ```http
   com.appsflyer:af-android-sdk:6.12.3
   ```
2. Thêm thư viện LVL vào triển khai build.gradle  

   ```http
   com.appsflyer:lvl:6.12.3
   ```
3. Nhận Giấy phép và thanh toán trong ứng dụng của ứng dụng:  
   Từ Giao diện điều khiển dành cho Nhà phát triển trên Google Play (Chọn ứng dụng -> Development Tools -> Services and APIs).  

   ```http
   Base64-encoded RSA public key
   ```
4. Chuyển thông tin trên tới CSM AppsFlyer của bạn.

</Accordion>

<div id="test-and-troubleshoot" />

<Accordion title="Kiểm tra và khắc phục sự cố">

Khi gỡ lỗi ứng dụng, bạn sẽ có thể xem thông tin LVL trên tải trọng được gửi tới AppsFlyer, như ví dụ bên dưới:

```json
"lvl":{
      "ttr":,<ttr>,
      "signature":"<signature>",
      "signedData":"<signedData>"
   }
```

Làm việc với nhóm hỗ trợ/SDK của bạn trong trường hợp không có thông tin LVL trên thông báo cài đặt.

Vui lòng cung cấp cho CSM của bạn những thông tin sau:

* khóa công khai
* app\_id
* phiên bản ứng dụng tối thiểu LVL được tích hợp trong

</Accordion>

<div id="setup-process" />

<Accordion title="Quá trình thiết lập">

Sau khi chúng tôi nhận được yêu cầu của bạn, nhóm Protect360 sẽ định cấu hình xác minh LVL ở chế độ STAGING. Ở giai đoạn này, hệ thống sẽ chỉ báo cáo kết quả xác minh LVL nội bộ cho AppsFlyer. Một vài ngày sau, chúng tôi sẽ kiểm tra dữ liệu của mình.

**Nếu mọi thứ đều ổn:**

* Chúng tôi sẽ đặt xác minh LVL thành chế độ PRODUCTION và nó sẽ bắt đầu chặn lưu lượng truy cập.
* Nhóm Protect360 sẽ thông báo cho CSM.

**Nếu có điều gì đó không ổn** (chẳng hạn như nếu chúng tôi không thấy thông tin LVL trên các sự kiện cài đặt):

* Chúng tôi sẽ để xác minh LVL ở chế độ STAGING.
* CSM của bạn sẽ thông báo cho bạn và giúp bạn khắc phục sự cố triển khai trong ứng dụng.

</Accordion>

## Câu hỏi thường gặp

<div id="what-if-an-app-is-installed-from-a-store-other-than-google-play" />

<Accordion title="Điều gì sẽ xảy ra nếu một ứng dụng được cài đặt từ một cửa hàng không phải Google Play?">

Xác thực LVL sẽ không xác minh và không chặn lượt cài đặt đến từ các cửa hàng không phải Google Play.

</Accordion>

<div id="how-much-time-does-it-take-to-get-lvl-set-up" />

<Accordion title="Mất bao lâu để thiết lập LVL?">

Sau khi chúng tôi nhận được thông tin, sẽ mất vài ngày làm việc để thiết lập LVL và xác minh dữ liệu. Xem chi tiết về [quá trình thiết lập](/docs/implement-google-license-verification-library-lvl#setup-process).

</Accordion>

<div id="does-lvl-affect-app-functionality" />

<Accordion title="LVL có ảnh hưởng đến chức năng ứng dụng không?">

Không, chức năng ứng dụng không bị ảnh hưởng.

</Accordion>

<div id="what-is-the-difference-between-lvl-and-gpreferrer" />

<Accordion title="Sự khác biệt giữa LVL và trình giới thiệu GP là gì?">

Xác minh giấy phép sử dụng LVL khác với các thuật toán xác minh liên kết giới thiệu GP vì LVL xử lý việc xác minh giấy phép cho chính ứng dụng đó (giấy phép cho mỗi ứng dụng), trong khi liên kết giới thiệu GP được sử dụng để lấy nguồn chuyển hướng của lượt cài đặt tới cửa hàng Google Play với URL liên kết giới thiệu của gói đã cài đặt (nhãn thời gian khi xảy ra lượt nhấp chuột liên kết giới thiệu, thời điểm bắt đầu cài đặt, phiên bản ứng dụng, v.v.). Nói ngắn gọn, trong khi LVL được sử dụng để kiểm tra xem người dùng có được cấp phép sử dụng ứng dụng hay không thì liên kết giới thiệu GP được sử dụng để xác minh rằng chi tiết lượt cài đặt không bị giả mạo.

</Accordion>

<div data-zendesk-anchors="overview=t%E1%BB%95ng-quan 01H7YJ35YKDHJ2MDZSSYKMDCJ4=t%E1%BB%95ng-quan set-up-lvl=thi%E1%BA%BFt-l%E1%BA%ADp-lvl 01H7YJ35YKDW0CB9TWRBKFBCDJ=thi%E1%BA%BFt-l%E1%BA%ADp-lvl 01H7YJ35YK585NA5F4HZN8C74K=add-lvl 01H7YJ35YKX1CVYMRZ1W8NRH7Y=test-and-troubleshoot 01H7YJ35YKMCN2E2BDWA5DD5M3=setup-process faq=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p 01H7YJ35YMR8PBTTSHD77WZ4AE=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p 01H7YJ35YMRZ8KRSVND1JT6JGH=what-if-an-app-is-installed-from-a-store-other-than-google-play 01H7YJ35YM11J0EG0B8PBMSPAC=how-much-time-does-it-take-to-get-lvl-set-up 01H7YJ35YMH0NM73Y1R90JDMEA=does-lvl-affect-app-functionality 01H7YJ35YM6RHCA6QP3MK0Y9J0=what-is-the-difference-between-lvl-and-gpreferrer" />
