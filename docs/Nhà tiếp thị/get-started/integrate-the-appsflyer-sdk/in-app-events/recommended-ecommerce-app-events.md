---
title: ' Các sự kiện ứng dụng Thương mại điện tử được đề xuất'
metadata:
  keywords:
    - Advertisers
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
  created_at: '2021-04-19T06:32:18Z'
  edited_at: '2023-04-07T10:25:31Z'
  id: 360019347957
  locale: vi
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/vi/articles/360019347957
---
> **Khái quát:** Đo lường chất lượng của người dùng trong suốt hành trình người dùng của họ bằng cách ghi nhận các sự kiện trong ứng dụng được đề xuất này cho ứng dụng Thương mại điện tử của bạn.

<div id="-ecommerce" />

## <Image alt="InApp_Events_ecommerce.png" src="https://files.readme.io/c6497d250c22c7de5c13f01278ac72d8b3117bc60712ba3fe40ad24efcdc4947-360019350097.png" width="67px" /> Thương mại điện tử

Ứng dụng Thương mại điện tử cho phép người mua dễ dàng tìm kiếm và mua hàng trực tuyến. Các sự kiện điển hình mà bạn nên ghi nhận là tìm kiếm, giao dịch mua, thêm vào giỏ hàng và thêm vào danh sách yêu thích.

Việc ghi nhận các sự kiện có thể giúp bạn xác định:

* Các danh mục phổ biến nhất
* Người mua đang tìm kiếm những gì
* Có bao nhiêu người mua đã hoàn tất thanh toán
* Có bao nhiêu người mua định kỳ và bao nhiêu người mua một lần

<div id="important" />

> 🚧 **Quan trọng!**
>
> * Hãy nhớ đọc các <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#thiết-lập-sự-kiện-trong-ứng-dụng">hướng dẫn</Anchor> dành cho nhà tiếp thị về cách triển khai các sự kiện trong ứng dụng.
> * Để sắp xếp hợp lý hóa quy trình triển khai, hãy sử dụng <Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=ecommerce">Trình tạo sự kiện trong ứng dụng</Anchor> của chúng tôi. Công cụ này bao gồm tất cả các sự kiện trong ứng dụng điển hình được mô tả trong bài viết này và cho phép bạn sửa đổi sự kiện theo nhu cầu kinh doanh của mình. Sau khi hoàn tất, hãy chia sẻ tệp tin với nhà phát triển của bạn.
> * Đối với mỗi sự kiện được khuyên dùng có trong bài viết này, có <Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=ecommerce&view=code">các mẫu code</Anchor> dành cho các nhà phát triển iOS, Android và Unity.
> * Bạn có thể tìm hướng dẫn chi tiết dành cho nhà phát triển của mình trong **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">trung tâm nhà phát triển AppsFlyer</Anchor>.**
>
> Để biết thêm thông tin về cách ghi lại các sự kiện trong ứng dụng, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview">Hướng dẫn sự kiện phong phú trong ứng dụng</Anchor>.

<Image align="center" alt="Flowchart_for_recommended_events e-Commerce_app_user_journey" src="https://files.readme.io/81af149c4fbe9185af3dad4057147dbf9882eb30d30b0724f2ffad2714517084-360020063077.png" />

<div id="recommended-structures-for-predefined-events" />

## Cấu trúc đề xuất cho các sự kiện đã xác định trước

Phần dưới đây cung cấp danh sách các cấu trúc sự kiện điển hình cho ngành Thương mại điện tử. Mỗi cấu trúc bao gồm một tên sự kiện đã xác định trước và các thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Hoàn tất đăng ký (af_complete_registration)">

**Mục đích**

Tìm hiểu số lượng người dùng đã cài đặt ứng dụng và hoàn tất quá trình đăng ký, cùng phương pháp đăng ký nào mà người dùng của bạn thích

**Kích hoạt**

Thời điểm người dùng hoàn tất quá trình đăng ký

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_registration\_method | Loại phương thức đăng ký | Email, quảng cáo Meta |

</Accordion>

<div id="login-af_login" />

<Accordion title="Đăng nhập (af_login)">

**Mục đích**

Hiểu được việc giữ chân người dùng đã đăng ký của bạn

**Kích hoạt**

Thời điểm người dùng đăng nhập thành công

**Thông số sự kiện**

Có thể được gửi mà không cần bất kỳ thông số bổ sung nào

</Accordion>

<div id="search-af_search" />

<Accordion title="Tìm kiếm (af_search)">

**Mục đích**

Tìm hiểu những đối tượng tìm kiếm của người dùng và kết quả tìm kiếm nào phù hợp nhất và dẫn đến giao dịch mua.

**Kích hoạt**

Một trong những thông tin sau:

* Thời điểm người dùng nhấp vào nút tìm kiếm
* Thời điểm người dùng truy cập vào trang kết quả tìm kiếm

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_search\_string | Cụm từ tìm kiếm | Váy đỏ, giày chạy bộ |
| af\_content\_list | Danh sách các ID nội dung | 001, 092 |

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Khung hiển thị nội dung (af_content_view)">

**Mục đích**

Xác định tỷ lệ lượt xem các sản phẩm cụ thể. Sự kiện này có thể giúp bạn:

* Liên hệ lượt xem sản phẩm với doanh số bán sản phẩm.
* Hiểu danh mục nào là phổ biến nhất theo lượt xem sản phẩm.
* Xem mối tương quan giữa đơn vị tiền tệ của người mua và các sản phẩm mà họ xem

**Kích hoạt**

Thời điểm người dùng xem trang chi tiết của một sản phẩm cụ thể

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_price | Giá sản phẩm | 2000 |
| af\_content | Mã số hàng hóa quốc tế (EAN) khi áp dụng hoặc mã định danh sản phẩm hoặc nội dung khác<br /><br />**Thông số bắt buộc đối với quảng cáo động của quảng cáo Meta** | ABC123 |
| af\_content\_id | ID sản phẩm<br /><br />**Thông số bắt buộc đối với quảng cáo động của quảng cáo Meta** | 102 |
| af\_content\_type | Danh mục sản phẩm<br /><br />**Thông số bắt buộc đối với quảng cáo động của quảng cáo Meta** | Giày dép |
| af\_currency | Đơn vị tiền tệ trong trang thông tin chi tiết sản phẩm | THB, USD |

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="Xem danh sách (af_list_view)">

**Mục đích**

Ghi nhận danh sách nào (ví dụ: sản phẩm mới được thêm vào, sản phẩm có liên quan hoặc sản phẩm được đề xuất) mà người mua xem nhiều nhất.

**Kích hoạt**

Thời điểm người dùng xem một danh sách cụ thể

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_content\_type | Loại danh sách | Related, recommended, new arrivals |
| af\_content\_list | Danh sách ID nội dung từ danh mục | 001, 092 |

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="Thêm vào danh sách yêu thích (af_add_to_wishlist)">

**Mục đích**

Ghi nhận những sản phẩm và danh mục mà người mua thêm vào danh sách yêu thích của họ. Khi bạn biết sản phẩm nào thường được thêm vào danh sách mong muốn, bạn có thể cung cấp các sản phẩm này trong danh mục khuyến mãi hoặc giảm giá và khuyến khích người mua mua sản phẩm đó. Bạn cũng có thể nhắm mục tiêu lại những người dùng này theo các sản phẩm họ đã thêm vào danh sách yêu thích của họ.

**Kích hoạt**

Thời điểm người dùng thêm các mặt hàng vào danh sách yêu thích của họ

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_price | Giá của sản phẩm | 600 |
| af\_content\_id | ID sản phẩm | 300 |
| af\_content\_type | Danh mục sản phẩm | Giày dép, thiết bị điện tử |
| af\_currency | Đơn vị tiền tệ hiển thị trên trang chi tiết sản phẩm | GBP |

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="Thêm vào giỏ hàng (af_add_to_cart)">

**Mục đích**

Ghi nhận khi có người dùng thêm sản phẩm vào giỏ hàng của họ. Sự kiện này có thể giúp bạn xác định:

* Xem số lượng sản phẩm trung bình mà người mua thêm vào trong một lần mua hàng
* Khoảng thời gian giữa hai lần thêm vào sản phẩm khác nhau
* Số lượng người mua từ bỏ giỏ hàng của họ

**Kích hoạt**

Thời điểm người dùng thêm một sản phẩm vào giỏ hàng

**Thông số sự kiện**

| Tên trường | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_price | Giá sản phẩm | 350, 1000 |
| af\_content | Mã số hàng hóa quốc tế (EAN) khi áp dụng hoặc mã định danh sản phẩm hoặc nội dung khác<br /><br />**Thông số bắt buộc đối với quảng cáo động của quảng cáo Meta** | ABC123 |
| af\_content\_id | ID sản phẩm<br /><br />**Thông số bắt buộc đối với quảng cáo động của quảng cáo Meta** | 001, 092 |
| af\_content\_type | Loại sản phẩm<br /><br />**Thông số bắt buộc đối với quảng cáo động của quảng cáo Meta** | Áo sơ mi, giày dép |
| af\_currency | Đơn vị tiền tệ sản phẩm | THB, USD |
| af\_quantity | Có bao nhiêu sản phẩm cùng loại đã được thêm vào giỏ hàng | 2, 5 |

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="Bắt đầu thanh toán (af_initiated_checkout)">

**Mục đích**

Hiểu hành vi của người mua khi họ tiến hành thanh toán. Sự kiện này có thể giúp bạn xác định:

* Giá trung bình khi người mua thanh toán so với giá trung bình trong sự kiện mua
* Người dùng thêm hay xóa sản phẩm sau khi đến mục thanh toán

**Kích hoạt**

Thời điểm người dùng bắt đầu thanh toán nhưng vẫn chưa hoàn tất thanh toán

**Thông số sự kiện**

| Tên trường | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_price | Tổng giá tiền trong giỏ hàng | 4000 |
| af\_content\_id | ID sản phẩm trong giỏ hàng | 221, 124 |
| af\_content\_type | Danh sách danh mục sản phẩm | Áo sơ mi, quần |
| af\_currency | Tiền tệ trong thời điểm thanh toán | THB |
| af\_quantity | Tổng số mặt hàng trong giỏ hàng | 2, 5 |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Mua hàng (af_purchase)">

**Mục đích**

Tìm hiểu về xu hướng mua trong ứng dụng của bạn. Sự kiện này có thể giúp bạn:

* Xác định LTV của người dùng và ROI của các chiến dịch của bạn trên các mạng quảng cáo và các đại lý quảng cáo
* Xác định những ưu đãi nào được người dùng chọn nhiều nhất
* Chiến dịch tham chiếu chéo với các mặt hàng đã mua để tối ưu hóa nhắm mục tiêu chiến dịch

**Kích hoạt**

Thời điểm người dùng truy cập trang cảm ơn sau khi mua hàng thành công

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Doanh thu ước tính từ giao dịch mua | 1205.99 |
| af\_price | Tổng số tiền mua hàng | 4000 |
| af\_content | Mã số hàng hóa quốc tế (EAN) khi áp dụng hoặc mã định danh sản phẩm hoặc nội dung khác<br /><br />**Thông số bắt buộc đối với** quảng cáo động **của quảng cáo Meta** | ABC123 |
| af\_content\_id | ID mặt hàng<br /><br />**Thông số bắt buộc đối với quảng cáo động của quảng cáo Meta** | 121, 262 |
| af\_content\_type | Danh mục mặt hàng<br /><br />**Thông số bắt buộc đối với quảng cáo động của quảng cáo Meta** | Giầy dép, quần |
| af\_currency | Mã tiền tệ | AUD |
| af\_quantity | Tổng số mặt hàng trong giỏ hàng | 2, 5 |
| af\_order\_id | ID đơn đặt hàng được tạo sau khi mua. | X123ABC |
| af\_receipt\_id | ID đặt xe<br /><br />**Thông số bắt buộc cho CRITEO và Google Ad Words để xác thực mua** | X123ABC |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Cấu trúc đề xuất cho các sự kiện tùy chỉnh

Phần sau cung cấp danh sách các cấu trúc sự kiện bao gồm tên sự kiện tùy chỉnh và các thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.

<div id="first-purchase-first_purchase" />

<Accordion title="Lần mua đầu tiên (first_purchase)">

**Mục đích**

Tương tự như sự kiện [Mua hàng](/docs/recommended-ecommerce-app-events#purchase-af_purchase). Ngoài ra, sự kiện này có thể giúp bạn xác định:

* Khoảng thời gian cần thiết để một người mua mới thực hiện mua hàng
* Những sản phẩm nào mà người mua lần đầu muốn mua
* Giá và doanh thu trung bình của giao dịch mua lần đầu

**Kích hoạt**

Thời điểm người dùng hoàn tất giao dịch mua lần đầu

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Doanh thu từ giao dịch mua | 1205.99 |
| af\_price | Tổng số tiền mua hàng | 4000 |
| af\_content | Mã số hàng hóa quốc tế (EAN) khi áp dụng hoặc mã định danh sản phẩm hoặc nội dung khác<br /><br />**Thông số bắt buộc đối với quảng cáo động của quảng cáo Meta** | ABC123 |
| af\_content\_id | ID mặt hàng<br /><br />**Thông số bắt buộc đối với quảng cáo động của quảng cáo Meta** | 121, 262 |
| af\_content\_type | Danh mục mặt hàng<br /><br />**Thông số bắt buộc đối với quảng cáo động của quảng cáo Meta** | Giầy dép, quần |
| af\_currency | Tiền tệ | AUD |
| af\_quantity | Số lượng mặt hàng trong giỏ hàng | 2, 5 |
| af\_order\_id | ID đơn đặt hàng được tạo sau khi mua. | X123ABC |
| af\_receipt\_id | ID đặt xe<br /><br />**Thông số bắt buộc để tích hợp nhắm mục tiêu lại CRITEO và Google AdWords** | X123ABC |

</Accordion>

<div id="remove-from-cart-remove_from_cart" />

<Accordion title="Xóa khỏi giỏ hàng (remove_from_cart)">

**Mục đích**

Ghi nhận sự kiện này có thể giúp bạn:

* Xác định những mặt hàng mà người mua xóa khỏi giỏ hàng của họ
* Xác định danh mục sản phẩm của các mặt hàng mà người mua xóa khỏi giỏ hàng của họ
* So sánh dữ liệu từ sự kiện [Thêm vào giỏ hàng](/docs/recommended-ecommerce-app-events#add-to-cart-af_add_to_cart) để có được thông tin chi tiết về các sản phẩm không được thanh toán

**Kích hoạt**

Thời điểm người dùng xóa một mặt hàng khỏi giỏ hàng

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_content\_id | ID sản phẩm hoặc mặt hàng | 521 |
| af\_content\_type | Danh mục sản phẩm hoặc mặt hàng | Giày dép |

</Accordion>

<div data-zendesk-anchors="ecommerce=-th%C6%B0%C6%A1ng-m%E1%BA%A1i-%C4%91i%E1%BB%87n-t%E1%BB%AD recommended-structures-for-predefined-events=c%E1%BA%A5u-tr%C3%BAc-%C4%91%E1%BB%81-xu%E1%BA%A5t-cho-c%C3%A1c-s%E1%BB%B1-ki%E1%BB%87n-%C4%91%C3%A3-x%C3%A1c-%C4%91%E1%BB%8Bnh-tr%C6%B0%E1%BB%9Bc recommended-structures-for-custom-events=c%E1%BA%A5u-tr%C3%BAc-%C4%91%E1%BB%81-xu%E1%BA%A5t-cho-c%C3%A1c-s%E1%BB%B1-ki%E1%BB%87n-t%C3%B9y-ch%E1%BB%89nh" />
