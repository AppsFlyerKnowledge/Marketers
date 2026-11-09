---
title: API OneLink
metadata:
  keywords:
    - api
    - Premium
    - Marketers
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Premium
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2018-06-27T12:00:29Z'
  edited_at: '2023-09-07T03:08:32Z'
  id: 360001250345
  locale: vi
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/vi/articles/360001250345
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Khái quát:** OneLink API giúp bạn thu hút người dùng cuối và tận dụng truyền thông sở hữu bằng cách tạo các liên kết được cá nhân hóa trong các chiến dịch quy mô lớn, qua SMS, v.v. Yêu cầu cả nhà quảng cáo và nhà phát triển triển khai.

<div id="get-started" />

<div id="example" />

<div id="about-onelink-api" />

## API OneLink

API OneLink được sử dụng để:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/create-onelink-attribution-link">Tự động tạo</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-attribution-link">lấy</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/update-onelink-attribution-link">cập nhật và</Anchor> <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/delete-onelink-attribution-link">xóa</Anchor> URL rút gọn của OneLink bằng các thông số tùy chỉnh.  
  Các thông số có thể là:
  * Các thông số liên quan đến phân bổ, được sử dụng để đo lường và theo dõi các nỗ lực tiếp thị, như nguồn truyền thông, chiến dịch và bộ quảng cáo. **Lưu ý**: Thông số nguồn truyền thông (pid) là bắt buộc.
  * Các thông số được cá nhân hóa cho phép bạn cấu hình trải nghiệm người dùng tùy chỉnh khi mở ứng dụng từ liên kết có liên quan. Những thông số này cho phép bạn đưa người dùng đến nội dung trong ứng dụng được tùy chỉnh, ví dụ như một trang sản phẩm cụ thể, mã phiếu giảm giá hoặc khuyến mại.
* Cho phép chia sẻ nội dung trang web và ứng dụng trực tiếp đến người dùng thiết bị di động (do đó tăng mức độ thu hút và cài đặt trên thiết bị di động).
* Tạo tức thời một số lượng lớn các đường dẫn phân bổ tùy chỉnh OneLink.  
  **Lưu ý**: Đối với các liên kết giới thiệu, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/user-invite-attribution">bài viết Phân bổ lời mời người dùng</Anchor>.

> 📄 **Ví dụ**
>
> Feed Me, một dịch vụ giao hàng tạp hóa, muốn gửi một liên kết được cá nhân hóa qua SMS tới những khách hàng hiện tại để khuyến khích họ tải xuống ứng dụng Feed Me và mua chuối. Dựa trên quốc gia của khách hàng, Feed Me sử dụng API REST OneLink để tạo URL OneLink tùy chỉnh có chứa các chi tiết cụ thể đối với quốc gia, danh tính người dùng và ưu đãi đặc biệt cho các loại chuối đang được giảm giá.

Số lượng truy vấn API OneLink bạn có thể thực hiện bị giới hạn tùy thuộc vào loại tài khoản của bạn. Bạn có thể xem số lượng truy vấn bạn đã thực hiện và số lượng truy vấn còn lại trong bảng điều khiển API OneLink. 

Bạn có thể liên hệ với CSM của mình để tăng giới hạn truy vấn API.  

### Thiết lập

**Để thiết lập API OneLink:**

1. <Anchor target="_blank" href="/marketers/vi/docs/create-a-onelink-template#quy-trình">Tạo mẫu OneLink</Anchor>.
2. Ghi nhận ID OneLink.   

   <Image align="center" alt="" src="https://files.readme.io/b25f9c4dfe6f4a5a39e9b0a4d1b82d68330f8c0853248284564ac46c72d4d423-360019487418.jpg" />
3. Ghi nhận mã khóa API OneLink. Người dùng quản trị cần truy xuất khóa API; người dùng tài khoản không có quyền truy cập. 
   * Trong bảng điều khiển AppsFlyer, đi tới **Experiences & Deep Linking** > **OneLink API** > **View OneLink API key**
   * Nếu mã khóa API OneLink không có trong đó cho người dùng quản trị, thì điều đó có nghĩa là bạn không có gói cần thiết và bạn cần liên hệ với CSM của mình.
4. Cung cấp ID OneLink và mã khóa API OneLink cho nhà phát triển.
5. Yêu cầu nhà phát triển làm theo <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/onelink_rest_api">hướng dẫn trong trung tâm nhà phát triển</Anchor>.

<div id="referral-and-advocate-sharing" />

<div id="offline-and-qrbased-engagement" />

<div id="crmpowered-channels-sms-email-whatsapp" />

<div id="crossplatform-journeys-ctv-desktop-webtoapp" />

<div id="use-cases" />

<div id="dashboard" />

### Bảng điều khiển

Bảng điều khiển API OneLink hiển thị:

* Mức sử dụng API hàng ngày, hàng tháng và ba tháng của bạn.
* Mã khóa API OneLink.

**Để xem bảng điều khiển API OneLink**: 

Trong AppsFlyer, đi tới **Experiences & Deep Linking** > **OneLink API**.

<div id="traits-and-limitations" />

### Đặc điểm và hạn chế

| **Đặc điểm** | **Lưu ý** |
| --- | --- |
| Giới hạn hạn mức API | <ul><li>Giới hạn sử dụng API OneLink để tạo, chỉnh sửa hoặc xóa đường liên kết OneLink là 7,5 triệu mỗi tháng (múi giờ UTC), mỗi tài khoản.</li><li>Tất cả các yêu cầu được thực hiện **sau khi** vượt quá hạn mức này sẽ không được phân phối và các đường liên kết không được tạo; lệnh gọi API nhận được mã trạng thái lỗi 429 với thông báo "Đã vượt quá hạn mức hàng tháng".</li><li>Thông tin về hạn mức tỷ lệ đã sử dụng/còn lại được hiển thị trong bảng điều khiển API OneLink.</li></ul> |
| Giới hạn tốc độ | <ul><li>Giới hạn tốc độ API cho mỗi tài khoản là 500 yêu cầu mỗi giây (30000 mỗi phút).</li><li>Tất cả các yêu cầu được thực hiện vượt quá 500 yêu cầu mỗi giây (30000 yêu cầu mỗi phút) đều không được phân phối và đường liên kết sẽ không được tạo; lệnh gọi API nhận được mã trạng thái lỗi 429 với thông báo "Đã vượt quá giới hạn tốc độ".</li></ul> |
| Khả năng hiển thị liên kết | <ul><li>Các liên kết được tạo qua API không xuất hiện trong danh sách các liên kết tùy chỉnh OneLink trong bảng điều khiển của AppsFlyer.</li><li>Phương pháp hay nhất: Lưu các liên kết do API tạo vào một bảng cục bộ để bạn có thể truy cập các liên kết cho bất kỳ mục đích nào sau này.</li></ul> |
| TTL | <ul><li>Thời gian tồn tại mặc định (TTL) cho các URL rút gọn OneLink được tạo qua API OneLink là 31 ngày. Thời gian này được kéo dài thêm 31 ngày mỗi khi liên kết nhận được lượt nhấp.  Việc nhấp vào liên kết như vậy khi TTL hết hạn vẫn được mặc định dẫn đến hoạt động được xác định trong cấu hình cơ sở OneLink, nhưng tính năng phân bổ sẽ không hoạt động.<ul><li>Có thể mất tối đa 48 giờ để xóa một URL rút gọn OneLink sau khi TTL hết hạn.</li></ul></li><li>TTL tối đa là 31 ngày. Bất kỳ giá trị TTL nào lớn hơn 31 đều bị ghi đè bằng TTL mặc định là 31.</li><li>Bạn có thể thay đổi TTL mặc định bằng cách thêm thông số `ttl={value}` và chỉ định số ngày, giờ hoặc phút. Ví dụ `ttl=7d`, `ttl=12h`hoặc `ttl=10m`.</li><li>Bạn có thể gửi <Anchor target="_blank" href="https://dev.appsflyer.com/reference/onelink_rest_api#update-onelink-attribution-link">yêu cầu cập nhật</Anchor> để chỉ định TTL. Mọi yêu cầu cập nhật đều đặt lại TTL (đối với các liên kết hiện có) thành một yêu cầu được chỉ định trong nội dung yêu cầu.<ul><li>Điều này có nghĩa là TTL sẽ được thay thế. Ví dụ, nếu bạn gọi lệnh cập nhật với TTL 2 ngày cho một liên kết hiện có TTL 29 ngày, thì sẽ được thay đổi thành **TTL=2d** (không phải 31 ngày).</li><li>Lệnh gọi cập nhật có khả năng kéo dài thời gian tồn tại của đường dẫn phân bổ. Ví dụ, nếu bạn thực hiện lệnh gọi cập nhật với TTL 31 ngày cho một liên kết hiện có TTL 20 ngày nhưng đã qua 5 ngày, thì TTL sẽ là 31 ngày kể từ thời điểm cập nhật.</li></ul></li><li>Nếu bạn không muốn các TTL của liên kết tự động kéo dài thời gian, hãy thêm thông số `renew_ttl=false` vào các đường liên kết của bạn. Giá trị cho thông số này là boolean, true (mặc định) hoặc false.</li><li>Thông số `renew_ttl` không hiển thị trên URL thực tế.</li></ul> |
| Ký tự đặc biệt | Các ký tự sau phải được mã hóa nếu được sử dụng cho các đường liên kết do API tạo: ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ', >, &lt;, /  <br />Nếu bạn không mã hóa các ký tự này, chúng sẽ được thay thế bằng khoảng trắng và đường liên kết cũng như chức năng của đường liên kết có thể bị lỗi. |
| Tải trọng | Chuỗi truy vấn từ tải trọng không được vượt quá 2.048 ký tự. |
| ID URL | Có thể chính sửa ID URL (hoặc ID liên kết rút gọn) để làm nổi bật dịch vụ cung cấp của chiến dịch. Ví dụ: https://myapp.onelink.me/abc123/apples. ID URL không được vượt quá 50 ký tự và có thể là sự kết hợp giữa các chữ cái và số. Theo mặc định, ID này gồm 8 ký tự.<br /><br />**Lưu ý**:<ul><li>Bạn chỉ có thể chỉnh sửa ID URL nếu ID hiện tại chưa được sử dụng.</li><li>Nếu ID URL đã được sử dụng, việc tạo đường liên kết sẽ không thành công và trả về phản hồi lỗi (400). Bạn và nhà phát triển của bạn cần quyết định và định cấu hình hoạt động sẽ xảy ra trong một sự kiện như vậy.</li><li>Lệnh gọi không thành công vẫn được tính vào hạn mức API hàng tháng của bạn.</li></ul> |

<div data-zendesk-anchors="onelink-api=api-onelink setup=thi%E1%BA%BFt-l%E1%BA%ADp dashboard=b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n traits-and-limitations=%C4%91%E1%BA%B7c-%C4%91i%E1%BB%83m-v%C3%A0-h%E1%BA%A1n-ch%E1%BA%BF" />
