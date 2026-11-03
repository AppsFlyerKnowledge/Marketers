---
title: Ánh xạ sự kiện trong ứng dụng của quảng cáo Meta
metadata:
  keywords:
    - Facebook
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
  created_at: '2021-11-09T09:57:19Z'
  edited_at: '2023-09-07T02:59:33Z'
  id: 4410480904081
  locale: vi
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/vi/articles/4410480904081
---
> **Tổng quan:** Gửi các sự kiện phong phú trong ứng dụng của ứng dụng của bạn từ AppsFlyer đến quảng cáo Meta.

## Ánh xạ sự kiện Meta trong ứng dụng

Nhà quảng cáo ánh xạ các sự kiện trong ứng dụng, SDK hoặc Máy chủ đến máy chủ của họ đến các sự kiện được xác định trước của Meta. Các nhà quảng cáo cũng có thể gửi các bài đăng lại trên Meta về mỗi lần <Anchor target="_blank" href="/marketers/vi/docs/measure-sessions">khởi chạy ứng dụng</Anchor> hoặc <Anchor target="_blank" href="/marketers/vi/docs/measure-uninstalls#ánh-xạ-sự-kiện-gỡ-cài-đặt">bất kỳ lượt gỡ cài đặt ứng dụng nào đã biết</Anchor>.

Điều này cho phép nhà quảng cáo tận dụng các khả năng tối ưu hóa nâng cao của Meta, cũng như tạo phân đoạn Đối tượng Tương tự và Tùy chỉnh.

### Ánh xạ sự kiện được xác định trước

Quảng cáo Meta cung cấp <Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/getting-started-app-events-android#event-names">nhiều loại sự kiện</Anchor> đã được xác định trước và có thể ánh xạ.

Tìm <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-event-structure">tại đây</Anchor> danh sách **các sự kiện phong phú trong ứng dụng**, có thể được gửi tới Meta với các thông số bổ sung cung cấp **thêm thông tin về chất lượng của sự kiện**.

Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/meta-ads-integration-setup#inapp-event-mapping">các sự kiện ánh xạ trên Meta</Anchor>.

[![In-app_event_postbacks_en-us.png](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)

Lưu ý rằng không có sự kiện được xác định trước để gửi lượt gỡ cài đặt tới quảng cáo Meta. Để gửi lượt gỡ cài đặt, hãy sử dụng một [sự kiện tùy chỉnh](/docs/meta-ads-in-app-event-mapping#nối-sự-kiện-tuỳ-chỉnh-trong-ứng-dụng-facebook).

Dưới đây là danh sách các sự kiện được xác định trước khác của Meta không có thông số bổ sung:

| Mã định danh sự kiện Meta | Mô tả | Tên SDK AppsFlyer đề xuất |
| --- | --- | --- |
| Quyên tặng | Quyên tặng tiền cho tổ chức hoặc mục đích của bạn. | af\_donate |
| Lên lịch | Đặt cuộc hẹn để đến thăm một trong những địa điểm của bạn. | af\_schedule |
| SubmitApplication | Nộp đơn đăng ký cho một sản phẩm, dịch vụ hoặc chương trình bạn cung cấp, chẳng hạn như thẻ tín dụng, chương trình giáo dục hoặc công việc. | af\_submit\_application |
| FindLocation | Khi có người tìm thấy một trong những địa điểm của bạn thông qua web hoặc ứng dụng với ý định viếng thăm. Ví dụ: tìm kiếm một sản phẩm và tìm thấy nó tại một trong các cửa hàng địa phương của bạn. | af\_find\_location |
| Liên hệ | Điện thoại hoặc SMS, email, trò chuyện hoặc loại hình liên hệ khác giữa khách hàng và doanh nghiệp của bạn. | af\_contact |
| CustomizeProduct | Việc tùy biến sản phẩm thông qua một công cụ cấu hình hoặc ứng dụng khác mà doanh nghiệp của bạn sở hữu. | af\_customize\_product |

### Nối Sự kiện tuỳ chỉnh trong Ứng dụng Facebook

AppsFlyer cho phép bạn ánh xạ bất kỳ sự kiện trong ứng dụng tùy chỉnh nào để gửi tới Meta, bằng cách sử dụng tùy chọn Mã định danh sự kiện Meta TÙY CHỈNH.

Tên sự kiện và giá trị sự kiện (bao gồm các thông số sự kiện) được định cấu hình trong SDK được chuyển tiếp đến Meta, sau đó được hiển thị theo tên sự kiện SDK AppsFlyer ban đầu của nó - không phải dạng "tùy chỉnh".

Lưu ý rằng bạn có thể <Anchor target="_blank" href="https://www.facebook.com/business/help/2308889442692949?id=1716638325041491">sử dụng các sự kiện này để tùy chỉnh các chiến dịch của bạn</Anchor>.

[![](https://files.readme.io/b41d1fa6c42284db9992260e58083bc2ef46ee3e98dbe4e063cdb28883553471-37750368969233.png)](https://files.readme.io/b41d1fa6c42284db9992260e58083bc2ef46ee3e98dbe4e063cdb28883553471-37750368969233.png)

### Nối Thông số Tự động với sự kiện TÙY CHỈNH

Thông qua giải pháp tích hợp sâu của AppsFlyer với Meta, nhiều thông số sự kiện SDK tiêu chuẩn của AppsFlyer được tự động ánh xạ tới các thông số được xác định trước của Meta. Ví dụ: thông số **af\_revenue** được chuyển đổi thành thông số **\_valueToSum** trong Meta, cho phép bạn gửi doanh thu trên mỗi sự kiện có thể được đo lường và tối ưu hóa trong Meta.

> 📘 **Lưu ý**
>
> Ánh xạ thông số tự động có thể khác nhau giữa TÙY CHỈNH và các sự kiện được xác định trước.
>
> Đối với <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-event-structure">sự kiện được xác định trước</Anchor>, **af\_price** được ánh xạ tới **\_valueToSum** trong một số trường hợp (ví dụ: `fb_mobile_add_to_cart`). Trong các trường hợp khác, **af numvenue** được ánh xạ tới **\_valueToSum** (ví dụ: trong `fb_mobile_purchase`).
>
> Đối với các sự kiện được ánh xạ tới TÙY CHỈNH, **af\_price** luôn được ánh xạ tới **fb\_price** và **af numvenue** đến **\_valueToSum**.

Bảng sau liệt kê tất cả các thông số sự kiện của AppsFlyer, khi được ánh xạ thông qua sự kiện TÙY CHỈNH tới Meta, sẽ được tự động ánh xạ tới các thông số của Meta.

| Thông số AppsFlyer | Thông số Meta |
| --- | --- |
| af\_city | fb\_city |
| af\_class | fb\_travel\_class |
| af\_content\_id | fb\_content\_id |
| af\_content\_list | fb\_content\_id |
| af\_content\_type | fb\_content\_type |
| af\_country | fb\_country |
| af\_currency | fb\_currency |
| af\_date\_a | fb\_checkin\_date |
| af\_date\_b | fb\_checkout\_date |
| af\_departing\_arrival\_date | fb\_departing\_arrival\_date |
| af\_departing\_departure\_date | fb\_departing\_departure\_date |
| af\_description | fb\_description |
| af\_destination\_a | fb\_origin\_airport |
| af\_destination\_b | fb\_destination\_airport |
| af\_destination\_list | fb\_destination\_ids |
| af\_hotel\_score | fb\_hotel\_score |
| af\_level | fb\_level |
| af\_max\_rating\_value | fb\_max\_rating\_value |
| af\_num\_adults | fb\_num\_adults |
| af\_num\_children | fb\_num\_children |
| af\_num\_infants | fb\_num\_infants |
| af\_order\_id | fb\_order\_id |
| af\_payment\_info\_available | fb\_payment\_info\_available |
| af\_preferred\_neighborhoods | fb\_preferred\_neighborhoods |
| af\_preferred\_num\_stops | fb\_preferred\_num\_stops |
| af\_preferred\_price\_range | fb\_preferred\_price\_range |
| af\_preferred\_star\_ratings | fb\_preferred\_star\_ratings |
| af\_price | fb\_price |
| af\_quantity | fb\_num\_items |
| af\_region | fb\_region |
| af\_registration\_method | fb\_registration\_method |
| af\_returning\_arrival\_date | fb\_returning\_arrival\_date |
| af\_returning\_departure\_date | fb\_returning\_departure\_date |
| af\_revenue | \_valueToSum |
| af\_search\_string | fb\_search\_string |
| af\_success | fb\_success |
| af\_suggested\_destinations | fb\_suggested\_destinations |
| af\_suggested\_hotels | fb\_suggested\_hotels |
| af\_travel\_end | fb\_travel\_end |
| af\_travel\_start | fb\_travel\_start |
| af\_user\_score | fb\_user\_score |

## Giới hạn sự kiện và thông số

Các giới hạn sau áp dụng cho [các sự kiện bạn gửi tới quảng cáo Meta](https://developers.facebook.com/docs/app-events/faq#limits):

* Không được phép sử dụng các ký tự sau đây:
  * Dấu hai chấm (:)
  * Dấu chấm (.)
  * Bộ ký tự không phải là tiếng Latinh (tiếng Anh): Kể từ ngày 12 tháng 1 năm 2020, Meta không chấp nhận sử dụng Hán tự. AppsFlyer chưa thử nghiệm các bộ ký tự khác và bạn chỉ nên sử dụng các bộ ký tự này sau khi xác minh với Meta xem họ có hỗ trợ các bộ ký tự này trong các đăng lại hay không.
* Tên sự kiện có phân biệt chữ hoa và chữ thường. Để tránh sai lệnh, hãy đảm bảo bạn sử dụng chính xác chữ hoa chữ thường của tên sự kiện cho tất cả các nguồn truyền thông và phiên bản ứng dụng.
* Số lượng thông số tối đa: 25.
* Độ dài của tên và thông số sự kiện: 2–40.
* Độ dài thông số tối đa: 100 ký tự.
* Các ký tự được phép: Ký tự chữ và số, dấu gạch dưới, dấu gạch nối hoặc dấu cách. Không sử dụng các ký tự không phải tiếng Latinh (tiếng Anh). Sử dụng các chữ cái không phải tiếng Latinh sẽ dẫn đến các kết quả không nhất quán.

Những điều cần lưu ý về đặt tên sự kiện trong ứng dụng:

* Tên sự kiện trên AppsFlyer có thể được đặt giống như tên sự kiện Meta (ví dụ: fb\_price), tuy nhiên, những tên này không được gửi dưới dạng sự kiện TÙY CHỈNH tới Meta.  
  **Để đảm bảo an toàn, hãy tránh đặt tên sự kiện giống với tên sự kiện Meta.**
* Để thực hiện ánh xạ đăng lại sự kiện trong ứng dụng với Meta, hãy lấy dữ liệu sự kiện từ tất cả các nguồn, bao gồm cả nguồn tự nhiên.

> 🚧 **Quan trọng!**
>
> Ngoại trừ các thông số trên, AppsFlyer gửi dữ liệu sự kiện TÙY CHỈNH **nguyên trạng** tới Meta. Chủ sở hữu ứng dụng có trách nhiệm xác minh dữ liệu sự kiện theo yêu cầu của Meta, sử dụng các thông số Meta hợp lệ (xem bảng ở trên). Mặt khác, các thông số này sẽ không được gửi đến Meta.

<div data-zendesk-anchors="facebook-iae-mapping=%C3%A1nh-x%E1%BA%A1-s%E1%BB%B1-ki%E1%BB%87n-meta-trong-%E1%BB%A9ng-d%E1%BB%A5ng predefined-event-mapping=%C3%A1nh-x%E1%BA%A1-s%E1%BB%B1-ki%E1%BB%87n-%C4%91%C6%B0%E1%BB%A3c-x%C3%A1c-%C4%91%E1%BB%8Bnh-tr%C6%B0%E1%BB%9Bc custom-inapp-events-mapping=n%E1%BB%91i-s%E1%BB%B1-ki%E1%BB%87n-tu%E1%BB%B3-ch%E1%BB%89nh-trong-%E1%BB%A9ng-d%E1%BB%A5ng-facebook automatic-parameter-mapping-with-the-custom-event=n%E1%BB%91i-th%C3%B4ng-s%E1%BB%91-t%E1%BB%B1-%C4%91%E1%BB%99ng-v%E1%BB%9Bi-s%E1%BB%B1-ki%E1%BB%87n-t%C3%B9y-ch%E1%BB%89nh event-and-parameter-limitations=gi%E1%BB%9Bi-h%E1%BA%A1n-s%E1%BB%B1-ki%E1%BB%87n-v%C3%A0-th%C3%B4ng-s%E1%BB%91" />
