---
title: Gửi trực tiếp bản sao đăng lại SKAN tới AppsFlyer (iOS 15+)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-06-08T12:09:25Z'
  edited_at: '2023-11-09T05:06:51Z'
  id: 4402320969617
  locale: vi
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/vi/articles/4402320969617
---
> **Khái quát:** Bắt đầu từ iOS 15, hãy cấu hình ứng dụng của bạn để gửi các bản sao đăng lại tới AppsFlyer ngoài việc gửi chúng đến các mạng quảng cáo. Làm vậy sẽ cho phép AppsFlyer xác thực giá trị chuyển đổi (CV) và xác minh tính toàn vẹn của đăng lại. Cấu hình API Push AppsFlyer để chuyển tiếp các bản sao đăng lại tới một điểm cuối đã chọn bổ sung.

<div id="why-send-postback-copies-to-appsflyer" />

## Tại sao phải gửi bản sao đăng lại tới AppsFlyer?

* Nhận tất cả các đăng lại ở cùng một nơi: Các đăng lại chứa thông tin quan trọng đối với nhà quảng cáo—cụ thể là CV được sử dụng để đo lường chất lượng người dùng. CV, trong các đăng lại, không được mã hóa và cũng không phải là một phần của chữ ký đăng lại. Do đó, CV mà mạng quảng cáo báo cáo sẽ không thể được xác thực và có thể bị thao túng. AppsFlyer sẽ chuyển tiếp các bản sao đăng lại bằng API Push tới các điểm cuối do bạn xác định.
* Xem số liệu tải xuống lại; một số mạng quảng cáo không chia sẻ dữ liệu tải xuống lại với AppsFlyer. Bản sao đăng lại giúp hoàn thành bức tranh.
* Xem dữ liệu ứng dụng của nhà phát hành
* Xem tương tác kiểu chạm

**Lưu ý!** AppsFlyer vẫn phải nhận các đăng lại của mạng quảng cáo vì chúng chứa dữ liệu bổ sung do mạng quảng cáo cung cấp (ví dụ: tên chiến dịch).

<div id="configure-your-app-to-send-postback-copies-to-appsflyer" />

## Cấu hình ứng dụng của bạn để gửi các bản sao đăng lại tới AppsFlyer

Theo tài liệu của Apple, bạn có thể đặt một điểm cuối đăng lại SKAN duy nhất.

**Để đăng ký điểm cuối AppsFlyer:**

1. Yêu cầu nhà phát triển iOS <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#sending-skan-postback-copies-to-appsflyer">thêm AppsFlyer</Anchor> làm điểm cuối đăng lại SKAN trong phiên bản ứng dụng tiếp theo.
2. Gửi ứng dụng iOS.
3. Các đăng lại sẽ được gửi tới AppsFlyer khi phiên bản mới được phát hành (không phải từ TestFlight).
4. Bạn có thể xem các đăng lại đã nhận trong <Anchor target="_blank" href="/marketers/vi/docs/skan-raw-data-reports">báo cáo sao chép bài đăng lại</Anchor>.

<div id="common-misconceptions" />

## Những quan niệm sai lầm phổ biến

<div id="dont-believe-everything-you-hear" />

> 📘 **Đừng tin tất cả những gì bạn nghe thấy!**
>
> Những nhận định này đúng hay sai?
>
> ![TrueOrFalse.png](https://files.readme.io/77212d5a12ce2af35b0a4c87ca9e58213b4f9fd88c775007793e7abb5aaa3f04-35682597298577.png)
>
> * Các nhà quảng cáo giờ không còn phụ thuộc vào các mạng quảng cáo để nhận đăng lại nữa.
>   * **Sai.** Nhà quảng cáo vẫn phụ thuộc vào mạng quảng cáo để giải mã các phần dữ liệu quan trọng. Ví dụ: chỉ mạng quảng cáo mới có thể ánh xạ ID chiến dịch SKAN với tên chiến dịch.
> * Ngay sau khi tôi đặt điểm cuối bổ sung, các bản sao của tất cả các đăng lại đều sẽ được gửi đến đó.
>   * **Sai .** Tính năng điểm cuối bổ sung chỉ khả dụng cho các thiết bị chạy iOS 15+. Các bản sao đăng lại không được gửi từ các thiết bị chạy phiên bản cũ hơn.

<div id="see-also" />

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_an_advertised_app?changes=latest_minor#see-also">Nhà phát triển Apple</Anchor>

<div data-zendesk-anchors="why-send-postback-copies-to-appsflyer=t%E1%BA%A1i-sao-ph%E1%BA%A3i-g%E1%BB%ADi-b%E1%BA%A3n-sao-%C4%91%C4%83ng-l%E1%BA%A1i-t%E1%BB%9Bi-appsflyer h_01HE7SV29Y7DNSKAAR91MJX986=t%E1%BA%A1i-sao-ph%E1%BA%A3i-g%E1%BB%ADi-b%E1%BA%A3n-sao-%C4%91%C4%83ng-l%E1%BA%A1i-t%E1%BB%9Bi-appsflyer configure-your-app-to-send-postback-copies-to-appsflyer=c%E1%BA%A5u-h%C3%ACnh-%E1%BB%A9ng-d%E1%BB%A5ng-c%E1%BB%A7a-b%E1%BA%A1n-%C4%91%E1%BB%83-g%E1%BB%ADi-c%C3%A1c-b%E1%BA%A3n-sao-%C4%91%C4%83ng-l%E1%BA%A1i-t%E1%BB%9Bi-appsflyer h_01HE7SV29YDFA5Z0X4WS87YK0Y=c%E1%BA%A5u-h%C3%ACnh-%E1%BB%A9ng-d%E1%BB%A5ng-c%E1%BB%A7a-b%E1%BA%A1n-%C4%91%E1%BB%83-g%E1%BB%ADi-c%C3%A1c-b%E1%BA%A3n-sao-%C4%91%C4%83ng-l%E1%BA%A1i-t%E1%BB%9Bi-appsflyer common-misconceptions=nh%E1%BB%AFng-quan-ni%E1%BB%87m-sai-l%E1%BA%A7m-ph%E1%BB%95-bi%E1%BA%BFn h_01HE7SV29YC855TGCXTCT4KHRN=nh%E1%BB%AFng-quan-ni%E1%BB%87m-sai-l%E1%BA%A7m-ph%E1%BB%95-bi%E1%BA%BFn h_01HE7SV29YMMTPH6EKYF3GQYEN=%C4%91%E1%BB%ABng-tin-t%E1%BA%A5t-c%E1%BA%A3-nh%E1%BB%AFng-g%C3%AC-b%E1%BA%A1n-nghe-th%E1%BA%A5y h_01HE7SX466CMCC03K99H68ZRBN=xem-th%C3%AAm" />
