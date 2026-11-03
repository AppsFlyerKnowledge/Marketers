---
title: Hướng dẫn thiết lập X Ads (trước đây là Twitter Ads)—tổng quan
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:31:36Z'
  edited_at: '2023-11-30T14:22:49Z'
  id: 4410464316049
  locale: vi
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/vi/articles/4410464316049
---
> **Tổng quan:** Tìm hiểu nền tảng của việc tích hợp tài khoản X Ads của bạn với AppsFlyer.

<Image alt="X Ads logo.png" src="https://files.readme.io/cecae90650321943ad1cb6d22b7f27d3d28b0484f1706cb1be1a19099dfbb20d-20375448207377.png" width="167px" />

## Quảng cáo ứng dụng di động trên X Ads

Quảng cáo ứng dụng di động X Ads là một phương thức quảng cáo ứng dụng trên X Ads. Phương thức này cho phép các nhà quảng cáo có thể quảng cáo ứng dụng di động của họ bằng thiết kế thẻ Ứng dụng tuyệt vời thúc đẩy lượt cài đặt, tương tác với ứng dụng và liên kết sâu. Người dùng có thể dễ dàng cài đặt và tương tác trực tiếp với ứng dụng từ dòng thời gian X Ads.

## Quyền riêng tư của người dùng X Ads

Người dùng X Ads có thể kiểm soát cách chia sẻ thông tin với các nhà quảng cáo:

* Nếu cài đặt của người dùng được đặt để ngăn chặn chia sẻ thông tin tương tác của họ với nhà quảng cáo, thì lượt cài đặt và sự kiện trong ứng dụng của họ do X Ads thúc đẩy sẽ bị loại bỏ khỏi dữ liệu thô nhưng vẫn được phân bổ cho X Ads.
* Dữ liệu phân bổ hợp nhất phản ánh chính xác trong AppsFlyer và không bị ảnh hưởng bởi chính sách của X Ads.
* Do đó, báo cáo hợp nhất và dữ liệu thô của X Ads không tương quan với nhau.

Bắt đầu từ ngày 31 tháng 7 năm 2021, các nhà quảng cáo không thuộc trong chương trình Đo lường di động nâng cao (AMM) của X Ads sẽ ngừng nhận mọi dữ liệu MACT cấp người dùng của X Ads.

Thông qua Chương trình AMM, nhà quảng cáo có thể nhận được dữ liệu cấp người dùng đầy đủ hơn sau khi cấp cho X Ads quyền thực hiện kiểm tra để đảm bảo rằng dữ liệu X Ads đang được sử dụng riêng cho mục đích đo lường. Điều này phù hợp với luật bảo vệ dữ liệu hiện hành và các thông lệ chung trong toàn ngành.  
**Để tham gia chương trình AMM:** Truy cập ads.twitter.com/help > **Mobile App, Conversion Tracking & Audience Manager,** và chọn **Advanced Mobile Measurement Program Agreement Form**.

Lưu ý rằng không thể xuất dữ liệu cấp người dùng nhận được trước khi tham gia chương trình AMM.

Để biết thêm thông tin chi tiết, hãy liên hệ với Người quản lý Tài khoản X Ads của bạn.

## Tương tác giữa X Ads và AppsFlyer SKAN

X Ads gửi dữ liệu đăng lại SKAdNetwork qua một API chuyên dụng. Dữ liệu SKAN từ X Ads sẽ được hiển thị trong <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">bảng điều khiển SKAN</Anchor>.

X Ads làm phong phú các bài đăng lại SKAN bằng các trường dữ liệu sau:

* Tên chiến dịch
* ID Chiến dịch
* Tên bộ quảng cáo
* ID Bộ quảng cáo

<div data-zendesk-anchors="mobile-app-promotion-on-twitter=qu%E1%BA%A3ng-c%C3%A1o-%E1%BB%A9ng-d%E1%BB%A5ng-di-%C4%91%E1%BB%99ng-tr%C3%AAn-x-ads h_01H9QR6TH7M0H5YMXRWVVAYRK9=qu%E1%BA%A3ng-c%C3%A1o-%E1%BB%A9ng-d%E1%BB%A5ng-di-%C4%91%E1%BB%99ng-tr%C3%AAn-x-ads twitter-user-privacy=quy%E1%BB%81n-ri%C3%AAng-t%C6%B0-c%E1%BB%A7a-ng%C6%B0%E1%BB%9Di-d%C3%B9ng-x-ads h_01H9QR6TH74R50K00H7FYN61KC=quy%E1%BB%81n-ri%C3%AAng-t%C6%B0-c%E1%BB%A7a-ng%C6%B0%E1%BB%9Di-d%C3%B9ng-x-ads twitter-ads-and-appsflyer-skan-interoperation=t%C6%B0%C6%A1ng-t%C3%A1c-gi%E1%BB%AFa-x-ads-v%C3%A0-appsflyer-skan h_01H9QR6TH74PKBGM5RC4M118GE=t%C6%B0%C6%A1ng-t%C3%A1c-gi%E1%BB%AFa-x-ads-v%C3%A0-appsflyer-skan" />
