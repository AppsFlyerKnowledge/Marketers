---
title: >-
  API sự kiện máy chủ đến máy chủ dành cho thiết bị di động (S2S trên thiết bị
  di động)
metadata:
  keywords:
    - iOS
    - Android
    - API
    - In-App
    - S2S
    - HTTP API
    - appsflyer_id
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
  created_at: '2014-05-21T17:47:21Z'
  edited_at: '2024-05-06T08:41:13Z'
  id: 207034486
  locale: vi
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/vi/articles/207034486
---
> **Khái quát:** Gửi các sự kiện từ máy chủ của bạn tới AppsFlyer để đo lường các sự kiện trên thiết bị di động xảy ra bên ngoài ứng dụng.

[![S2S_us-en.png](https://files.readme.io/2f228a03ca00df529e42bd033825a0dca595e99a537cadcfd5419754a29b5490-35863179575441.png)](https://files.readme.io/2f228a03ca00df529e42bd033825a0dca595e99a537cadcfd5419754a29b5490-35863179575441.png)

<div id="server-to-server-events-api-for-mobile" />

## API sự kiện máy chủ đến máy chủ cho thiết bị di động

Đối với các ứng dụng iOS, bắt đầu từ iOS 14, bạn phải gửi thông số OS (hệ điều hành).

Nền tảng AppsFlyer sẽ phân bổ và ghi nhận các sự kiện trong ứng dụng di động mà AppsFlyer SDK và API đã gửi lên. Hãy sử dụng API S2S để báo cáo những sự kiện diễn ra ngoài phạm vi ứng dụng; ví dụ: người dùng gia hạn gói đăng ký thông qua giao diện web. Sau khi được ghi nhận, các sự kiện S2S sẽ xuất hiện trên toàn nền tảng, bao gồm bảng điều khiển, dữ liệu thô và dữ liệu phân tích. Để biết những sự kiện web cho PBA, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/web-server-to-server-events-api-for-pba-web-s2s">S2S Web cho PBA.</Anchor>

AppsFlyer sẽ điền vào các sự kiện S2S với:

* Những giá trị gửi trong thông báo S2S
* Một số giá trị phân bổ lượt cài đặt AppsFlyer, chẳng hạn như thời gian cài đặt, nguồn truyền thông.

Để gửi sự kiện qua API, hãy bảo nhà phát triển của bạn tuân theo <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">hướng dẫn API sự kiện từ máy chủ đến máy chủ</Anchor> của họ.

<div id="populating-parameters" />

## Điền các thông số

<div id="difference-between-organic-and-nonorganic" />

<Accordion title="Sự khác biệt giữa Tự nhiên và Không tự nhiên">

Khi AppsFlyer xử lý các sự kiện trong ứng dụng S2S, hệ thống sẽ sử dụng ID AppsFlyer để điền vào các trường phân bổ nhằm xác định sự kiện cài đặt được liên kết đứng trước các sự kiện trong ứng dụng.

Điều này có nghĩa rằng một số dữ liệu mà AppsFlyer liên kết với các sự kiện trong ứng dụng S2S không tự nhiên thì không được liên kết với các sự kiện trong ứng dụng S2S tự nhiên.

> 📄 **Ví dụ**
>
> Ví dụ, nếu bạn so sánh báo cáo dữ liệu thô của các sự kiện trong ứng dụng S2S tự nhiên và không tự nhiên, các sự kiện không tự nhiên có chứa dữ liệu mà các sự kiện trong ứng dụng tự nhiên không có.
>
> Các sự kiện trong ứng dụng không tự nhiên có chứa dữ liệu về nguồn truyền thông, chiến dịch, loại tương tác và thời gian tương tác được phân bổ.
>
> Mặt khác, các sự kiện trong ứng dụng tự nhiên sẽ theo sau lượt cài đặt tự nhiên. Lượt cài đặt tự nhiên không có dữ liệu liên quan đến chiến dịch, các nguồn truyền thông hoặc loại tương tác được phân bổ và thời gian cài đặt.

</Accordion>

<div id="mapping-appsflyer-id-with-customer-user-id-cuid" />

<Accordion title="Ánh xạ ID AppsFlyer với customer user ID (CUID)">

Phải có Backend logic để hệ thống lấy giá trị và điền thông số. Phần dưới đây mô tả cách thức bạn có thể lấy ID AppsFlyer:

* ID AppsFlyer là thông tin bắt buộc và được dùng để phân bổ sự kiện.
* Hệ thống tạo ra ID này khi người dùng cài đặt ứng dụng di động lần đầu.
* Để có thể ánh xạ CUID tới ID AppsFlyer, bạn cần đặt CUID trong ứng dụng.

Để giúp bạn dễ dàng biết được người dùng nào đã thực hiện sự kiện nào, hãy triển khai luồng bên dưới:

* <Anchor target="_blank" href="/marketers/vi/docs/customer-user-id-field-cuid">Thiết lập customer user ID</Anchor> khi người dùng cài đặt ứng dụng.
* Báo cáo dữ liệu thô của AppsFlyer bao gồm CUID và ID AppsFlyer. Sử dụng một trong các công cụ phân phối dữ liệu để lấy dữ liệu này hoặc API Push AppsFlyer.
* Sử dụng báo cáo dữ liệu thô để so khớp CUID với ID AppsFlyer.
* ID AppsFlyer có trong SDK được tích hợp sẵn trong ứng dụng của bạn (Android/iOS).
* Ánh xạ ID AppsFlyer với customer user ID trong hệ thống nội bộ của bạn (một thao tác quan trọng phục vụ mục đích sử dụng sau này).

Sau khi bạn ánh xạ ID AppsFlyer với CUID, bạn có thể so khớp người dùng với những sự kiện được thực hiện. Sau đó, bạn có thể lấy các giá trị khác (giá trị sự kiện, tiền tệ sự kiện, thời gian sự kiện, v.v.) và gửi sự kiện trong ứng dụng máy chủ đến máy chủ.

</Accordion>

<div id="fetching-the-appsflyer-id" />

<Accordion title="Đang tìm nạp ID AppsFlyer">

`appsflyer_id` là thông số bắt buộc trong các thông báo sự kiện máy chủ đến máy chủ. AppsFlyer sử dụng thông số này để phân bổ sự kiện tới thiết bị ban đầu và nguồn truyền thông được phân bổ. Bạn có thể lấy ID bằng một trong các phương thức sau:

* Từ thiết bị di động bằng cách gọi ra API SDK AppsFlyer:

  <Tabs>
  <Tab title="Gốc Android">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#getappsflyeruid">getAppsFlyerId</Anchor>

  </Tab>

  <Tab title="Gốc iOS">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#getappsflyeruid">getAppsFlyerId</Anchor>

  </Tab>

  <Tab title="Gốc Unity">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#getappsflyerid">getAppsFlyerId</Anchor>

  </Tab>

  <Tab title="React">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#getappsflyeruid">getAppsFlyerUID</Anchor>

  </Tab>
  </Tabs>

* Thông qua nền tảng AppsFlyer, sử dụng một trong các cách thức sau: <Anchor target="_blank" href="/marketers/vi/docs/pull-api-raw-data?query=pull">API Pull,</Anchor> <Anchor target="_blank" href="/marketers/vi/docs/push-api-streaming-raw-data">API Push,</Anchor> Xuất <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">thông tin cài đặt dữ liệu thô.</Anchor>

> 👍 **Lời khuyên**
>
> Khi thử nghiệm các thông báo S2S, nếu bạn đang sử dụng dữ liệu thô, hãy tìm bản ghi có nguồn truyền thông "s2s\_test". Đây là thiết bị thử nghiệm của bạn và ID Thiết bị AppsFlyer là ID bạn cần.

</Accordion>

<div id="time-stamping-s2s-events" />

<Accordion title="Ghi nhãn thời gian các sự kiện S2S">

[![sơ đồ logic đánh dấu thời gian](https://files.readme.io/2d9138cc505b0ab1bb106c00fb2d71bd1d070ee236d7f928c8b8b85afe14af59-35863166628497.png)](https://files.readme.io/2d9138cc505b0ab1bb106c00fb2d71bd1d070ee236d7f928c8b8b85afe14af59-35863166628497.png)

Khi đến AppsFlyer với số lượng lớn, các sự kiện S2S được ghi nhãn thời gian theo giá trị thuộc tính `eventTime` và thời gian đến của sự kiện. Thuộc tính `eventTime` biểu thị thời gian xảy ra sự kiện trong ứng dụng.

Khi đến, các sự kiện được ghi nhãn thời gian như sau:

* Nếu thông số `eventTime` không có trong bản ghi sự kiện thì thời gian sự kiện được đặt thành thời gian đến của thông báo HTTP.
* Các sự kiện đến trước 02:00 UTC được ghi nhãn theo giá trị `eventTime`. Có nghĩa là, đối với các sự kiện được ghi nhãn theo `eventTime`, chúng phải được báo cáo vào ngày diễn ra sự kiện hoặc ngày hôm sau cho đến 02:00 UTC.
* Các sự kiện diễn ra vào ngày hôm trước hoặc sớm hơn, đến sau 02:00 UTC, sẽ được ghi nhãn theo thời gian đến (thời gian của lệnh gọi API).
* Các sự kiện đến với giá trị `eventTime` trong tương lai (eventTime > thời gian đến):
  * Nếu `eventTime` được báo cáo và thời gian đến đều vào cùng một ngày theo lịch, thì sự kiện sẽ được ghi nhãn thời gian theo giá trị `eventTime`.
  * Nếu `eventTime` được báo cáo là vào ngày tiếp theo theo lịch, sự kiện sẽ được ghi nhãn thời gian theo thời gian đến.
* Các sự kiện có Giá trị `eventTime` không hợp lệ được đóng dấu thời gian đến của thông báo HTTP.

**Ví dụ:**

* Sự kiện đã được gửi với thông tin `eventTime` = 21 giờ, thứ Hai.

| Đã đến AppsFlyer | Nhãn thời gian AppsFlyer | Nhận xét |
| --- | --- | --- |
| 01:00 giờ thứ Ba | 21:00 giờ thứ Hai | Đã đến trước giờ đóng cửa. Thời gian được đặt thành giá trị `eventTime`. |
| 09:00 giờ thứ Tư | 09:00 giờ thứ Tư | Đã đến sau giờ đóng cửa. Thời gian được đặt thành thời gian đến. |

</Accordion>

<div id="sending-negative-revenue" />

<Accordion title="Gửi doanh thu âm">

Hệ thống có thể gửi các sự kiện có giá trị doanh thu âm. Ví dụ: nếu hủy lệnh mua. Thông số `af_revenue` có thể mang các giá trị âm để ghi nhận sự kiện này.

Nếu bạn điền `af_quantity`, bạn có thể muốn điền một giá trị âm vào trường đó, tùy thuộc vào logic hệ thống của bạn. AppsFlyer không sử dụng `af_quantity`.

</Accordion>

<div id="troubleshooting" />

## Xử lý sự cố

<div id="events-arent-displaying-in-the-dashboard" />

<Accordion title="Các sự kiện không hiển thị trong bảng điều khiển">

* Điểm cuối: Xác minh rằng điểm cuối được sử dụng là điểm cuối chính xác.
* Xác minh rằng tải trọng chứa các thông số bắt buộc. Xem [tại đây](/docs/server-to-server-events-api-for-mobile-s2s-mobile#mapping-appsflyer-id-with-customer-user-id-cuid).
* Kiểm tra xem ID AppsFlyer mà bạn sử dụng để khởi chạy sự kiện có phải là một appsflyer\_id thực sự hay không, có thực sự được cài đặt trên ứng dụng cụ thể không. Xem [tại đây](/docs/server-to-server-events-api-for-mobile-s2s-mobile#fetching-the-appsflyer-id).
* Các sự kiện S2S không hỗ trợ nhiều sự kiện trong một yêu cầu S2S. Phải gửi riêng từng sự kiện.
  * Các sự kiện có thể được gửi bằng phương thức không đồng bộ để thời gian phản hồi tốt hơn.
* Trong bảng điều khiển tổng quan, phạm vi ngày liên quan đến ngày cài đặt ứng dụng (LTV), chứ không phải ngày sự kiện.
  * Đảm bảo rằng bạn chọn đúng phạm vi ngày.
  * Đảm bảo rằng phạm vi ngày trong bảng điều khiển tương ứng với ngày cài đặt trên thiết bị (appsflyer\_id), chứ không phải ngày sự kiện.
* Báo cáo dữ liệu thô về sự kiện cho biết: phạm vi ngày liên quan đến ngày sự kiện, chứ không phải ngày cài đặt.

</Accordion>

<div id="events-dont-contain-revenue" />

<Accordion title="Các sự kiện không chứa giá trị doanh thu">

Nếu bạn gửi sự kiện S2S nhưng hệ thống chưa ghi nhận doanh thu, hãy đảm bảo rằng hệ thống đã tạo chuỗi cho JSON mà bạn gửi. Phần quan trọng nhất là thông số giá trị sự kiện trong JSON. Phải tạo chuỗi như minh họa trong ví dụ bên dưới.

```json
"{\"af_revenue\":\"6\" ,\"af_content_type\":\"wallets\"}"
```

Nếu không được tạo chuỗi, thì giá trị sự kiện sẽ không được xử lý theo đúng cách và doanh thu sẽ không được ghi nhận.

Tuyệt đối không được định dạng các giá trị doanh thu. Chúng có thể chứa dấu thập phân. Không bao gồm mã hoặc ký hiệu tiền tệ, cũng như dấu phân cách `,`. Giá trị doanh thu có thể bắt đầu bằng tiền tố `-`

* Ví dụ về các giá trị hợp lệ: `123`, `-123.45`, `123.456`
* Ví dụ về các giá trị không hợp lệ: `1,234.56`, `1,234`

</Accordion>

<div id="not-all-fields-are-populated-in-s2s-events" />

<Accordion title="Trong sự kiện S2S, không phải tất cả các trường đều được hệ thống điền">

Hệ thống điền vào các trường dữ liệu thô bằng cách sử dụng giá trị được gửi trong lệnh gọi S2S và điền vào các trường khác bằng thông tin từ sự kiện cài đặt. Hệ thống sử dụng SDK AppsFlyer để quan sát hành vi tương tự, chứ không giống hệt nhau cho các sự kiện trong ứng dụng. Có một vài điểm khác biệt, cụ thể đó là các trường sau không được hệ thống điền dữ liệu cho các sự kiện S2S:

* wifi
* người điều hành
* ngôn ngữ
* Model Thiết bị
* Danh mục thiết bị
* Phiên bản Ứng dụng: Bạn có thể sử dụng `app_version_name`
* Tên ứng dụng
* Tác nhân người dùng

</Accordion>

<div data-zendesk-anchors="servertoserver-events-api-for-mobile=api-s%E1%BB%B1-ki%E1%BB%87n-m%C3%A1y-ch%E1%BB%A7-%C4%91%E1%BA%BFn-m%C3%A1y-ch%E1%BB%A7-cho-thi%E1%BA%BFt-b%E1%BB%8B-di-%C4%91%E1%BB%99ng h_01H9Q8KBYGXAA8H4AKKXP8T8DY=api-s%E1%BB%B1-ki%E1%BB%87n-m%C3%A1y-ch%E1%BB%A7-%C4%91%E1%BA%BFn-m%C3%A1y-ch%E1%BB%A7-cho-thi%E1%BA%BFt-b%E1%BB%8B-di-%C4%91%E1%BB%99ng populating-parameters=%C4%91i%E1%BB%81n-c%C3%A1c-th%C3%B4ng-s%E1%BB%91 h_01H9Q8KBYGHY1SDSMSFZRT2JXZ=%C4%91i%E1%BB%81n-c%C3%A1c-th%C3%B4ng-s%E1%BB%91 h_01H9Q8KBYG6W4TERWHARZZZASZ=difference-between-organic-and-nonorganic h_01H9Q8KBYG0JCCGTEJW3GXZMF1=v%C3%AD-d%E1%BB%A5 h_01H9Q8KBYG6EBKPS5Y2KC1QT7G=mapping-appsflyer-id-with-customer-user-id-cuid h_01H9Q8KBYGR26VMQR9Y0CK85F6=fetching-the-appsflyer-id h_01H9Q8KBYGNC8PJE2GS8MHG0KQ=l%E1%BB%9Di-khuy%C3%AAn h_01H9Q8KBYG8ASB1WB9X4XM3CYZ=time-stamping-s2s-events h_01H9Q8KBYG63SZWNM4GWSJG605=sending-negative-revenue troubleshooting=x%E1%BB%AD-l%C3%BD-s%E1%BB%B1-c%E1%BB%91 h_01H9Q8KBYGYR9Y7DPCNWSB4QY0=x%E1%BB%AD-l%C3%BD-s%E1%BB%B1-c%E1%BB%91 h_01H9Q8KBYGYHCWAPPNMG9WB8QN=events-arent-displaying-in-the-dashboard h_01H9Q8KBYGDC68637RH4DE2FZX=events-dont-contain-revenue h_01H9Q8KBYGDQKZF90EJAXRTMF3=not-all-fields-are-populated-in-s2s-events" />
