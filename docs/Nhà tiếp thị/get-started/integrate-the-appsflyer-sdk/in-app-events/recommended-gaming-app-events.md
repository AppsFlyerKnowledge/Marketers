---
title: Các sự kiện ứng dụng trò chơi được đề xuất
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2021-04-06T14:46:54Z'
  edited_at: '2023-03-26T11:42:21Z'
  id: 360018941117
  locale: vi
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/vi/articles/360018941117
---
> **Khái quát:** Đo lường chất lượng người dùng trong suốt hành trình của họ bằng cách ghi nhận các sự kiện trong ứng dụng trò chơi của bạn.

## <Image alt="InApp_Events_games.png" src="https://files.readme.io/ee2d46ddf11a6a6cacc95399ffd778d6613ecdd905d237cd971073e095cada5b-20659444711953.png" width="100px" /> Chơi game

Các ứng dụng trò chơi bao gồm các trò chơi như trò chơi điện tử, trò chơi chiến lược, trò chơi giáo dục và thậm chí là trò chơi cá cược. Các sự kiện điển hình chúng tôi đề nghị bạn nên ghi nhận là mua hàng trong ứng dụng, chia sẻ trên mạng xã hội và mời bạn bè. Ngoài ra, bạn có thể đưa vào các sự kiện như lên cấp và hoàn thành hướng dẫn trong trò chơi.

Việc ghi nhận các sự kiện có thể giúp bạn xác định:

* Ưu đãi nào người dùng mua nhiều nhất
* Mức độ tương tác của người dùng
* Số lượng người dùng đăng lượt chia sẻ lên mạng xã hội
* Số lượng người dùng mời bạn bè cài đặt ứng dụng

Các sự kiện này cũng có thể được sử dụng cho các ứng dụng trò chơi chạy trên các nền tảng sau đây:

* TV thông minh chạy Android
* Apple TV (tvOS)
* Amazon Fire TV
* Xbox
* Thiết bị di động Windows

> 🚧 **Quan trọng!**
>
> * Hãy đọc các <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#thiết-lập-sự-kiện-trong-ứng-dụng">hướng dẫn</Anchor> dành cho nhà tiếp thị về cách triển khai các sự kiện trong ứng dụng.
> * Để triển khai nhanh chóng và dễ dàng, hãy sử dụng <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=gaming">Trình tạo sự kiện trong ứng dụng</Anchor> của chúng tôi. Công cụ này bao gồm tất cả các sự kiện trong ứng dụng điển hình được mô tả trong bài viết này và cho phép bạn sửa đổi sự kiện theo nhu cầu kinh doanh của mình. Sau khi hoàn tất, hãy chia sẻ tệp tin với đội ngũ phát triển ứng dụng của bạn để triển khai ghi nhận sự kiện.
> * Đối với mỗi sự kiện được khuyên dùng có trong bài viết này, có <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=gaming&view=code">các mẫu code</Anchor> dành cho các nhà phát triển iOS, Android và Unity.
> * Bạn có thể tìm hướng dẫn chi tiết dành cho đội ngũ phát triển ứng dụng của mình trong **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">trung tâm nhà phát triển AppsFlyer</Anchor>.**
>
> Để biết thêm thông tin về cách ghi lại các sự kiện trong ứng dụng, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview">Hướng dẫn sự kiện phong phú trong ứng dụng</Anchor>.

[![Flowchart_for_recommended_events gaming_app_user_journey](https://files.readme.io/18546b2ca811e534d7b15527d3dadb4750edd8e985154543fa156216ad023f78-360020169778.png)](https://files.readme.io/18546b2ca811e534d7b15527d3dadb4750edd8e985154543fa156216ad023f78-360020169778.png)

## Cấu trúc sự kiện chuẩn khuyên dùng

Phần sau đây cung cấp danh sách các cấu trúc sự kiện tiêu biểu cho ngành trò chơi. Mỗi cấu trúc bao gồm một tên sự kiện đã xác định trước và các tham số sự kiện được khuyên dùng. Sự kiện trong ứng dụng có thể bao gồm bất kỳ tham số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.

<div id="login-af_login" />

<Accordion title="Đăng nhập (af_login)">

**Mục đích**

Hiểu rõ được khả năng giữ chân người dùng đã đăng ký của bạn

**Kích hoạt**

Mỗi lần người dùng đăng nhập thành công

**Tham số sự kiện**

Có thể được gửi mà không cần bất kỳ tham số bổ sung nào

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Hoàn tất đăng ký (af_complete_registration)">

**Mục đích**

Tìm hiểu số lượng người dùng đã cài đặt ứng dụng và hoàn tất quá trình đăng ký và nhận biết phương thức đăng ký ưa dùng.

**Kích hoạt**

Thời điểm người dùng hoàn tất quá trình đăng ký

**Tham số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_registration\_method | Loại phương thức đăng ký | email, Facebook |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Mua hàng (af_purchase)">

**Mục đích**

Nhiều ứng dụng trò chơi cho phép người dùng mua các vật phẩm như tiền xu, đá quý hoặc vũ khí. Việc ghi nhận các giao dịch mua này có thể giúp bạn:

* Xác định LTV của người dùng và ROI của các chiến dịch trên các mạng và đại lý quảng cáo
* Xác định ưu đãi nào được người dùng chọn nhiều nhất
* Kiểm tra chéo các chiến dịch để tối ưu hoá đối tượng của từng chiến dịch

**Kích hoạt**

Thời điểm người dùng hoàn tất mua hàng và được chuyển tới trang cảm ơn mua hàng thành công

**Tham số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Doanh thu ước tính từ giao dịch mua | 199.99 |
| af\_currency | Mã tiền tệ | THB, USD |
| af\_quantity | Số lượng mục hàng đã mua | 2 |
| af\_content\_id | ID mặt hàng | 001, 092 |
| af\_order\_id | ID đặt xe | 9277 |
| af\_receipt\_id | ID hóa đơn | 9277 |

</Accordion>

<div id="level-achieved-af_level_achieved" />

<Accordion title="Cấp độ đã đạt được (af_level_achieved)">

**Mục đích**

Một trong những mục tiêu chính của người dùng là lên cấp trong trò chơi. Tăng cấp độ giúp mở ra các tính năng và màn chơi mới và điều này khuyến khích người dùng tiếp tục chơi. Việc ghi nhận thành tích của người dùng có thể giúp bạn:

* Xác định chiến dịch nào tạo ra nhiều người dùng hoạt động nhất
* Xác định loại người dùng nào hoạt động và tương tác nhiều nhất
* Liên kết hoạt động tổng thể của người dùng với các khía cạnh như doanh thu

**Kích hoạt**

Khi người dùng được thông báo hoàn thành cấp độ

**Tham số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_level | Cấp độ người dùng đạt được | 3 |
| af\_score | Điểm số liên kết với thành tích của người dùng | 500 |

</Accordion>

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="Hoàn thành hướng dẫn (af_tutorial_completion)">

**Mục đích**

Hướng dẫn cách chơi cho người dùng. Việc ghi nhận sự kiện này có thể giúp bạn xác định:

* Chủ đề nào người dùng thường gặp khó khăn
* Hướng dẫn nào không có hiệu quả tốt

**Kích hoạt**

* Thời điểm người dùng xem xong hướng dẫn
* Thời điểm người dùng bắt đầu xem hướng dẫn nhưng thoát ra và không hoàn thành

**Tham số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_success | Người dùng có hoàn thành hướng dẫn không | true |
| af\_tutorial\_id | ID hướng dẫn | 3 |
| af\_content | Tên hướng dẫn | Bắt đầu |

</Accordion>

<div id="share-af_share" />

<Accordion title="Chia sẻ (af_share)">

**Mục đích**

Người dùng muốn chia sẻ thành tích chơi lên các trang mạng xã hội. Việc chia sẻ nâng cao nhận thức về thương hiệu và giúp thúc đẩy nhiều người dùng tải xuống và cài đặt ứng dụng của bạn hơn. Việc ghi nhận sự kiện này có thể giúp bạn biết thời điểm nào người dùng có nhiều khả năng chia sẻ ứng dụng với bạn bè nhất. Tìm hiểu thêm về cách <Anchor target="_blank" href="/marketers/vi/docs/user-invite-attribution">ghi nhận lượt chia sẻ và lời mời</Anchor>.

**Kích hoạt**

Khi người dùng đăng lượt chia sẻ thành công lên mạng xã hội

**Tham số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_description | Lý do chia sẻ trên mạng xã hội, như mức điểm cao mới hoặc lên cấp | Điểm cao mới, Lên cấp, Chiến thắng trò chơi |
| platform | Nền tảng được sử dụng để đăng lượt chia sẻ | Facebook, WhatsApp, email |

</Accordion>

<div id="invite-af_invite" />

<Accordion title="Mời bạn bè (af_invite)">

**Mục đích**

Tìm hiểu những trang mạng xã hội nào người dùng gửi lời mời và số lượng người dùng đã mời bạn bè của họ tải và cài đặt ứng dụng.

**Kích hoạt**

Khi người dùng mời thành công một người bạn tải xuống và cài đặt ứng dụng

**Tham số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_description | Mô tả lời mời | Dùng thử ứng dụng này |

</Accordion>

## Cấu trúc sự kiện tuỳ chỉnh khuyên dùng

Phần sau cung cấp cấu trúc sự kiện bao gồm tên sự kiện tùy chỉnh và tham số sự kiện được khuyên dùng. Sự kiện trong ứng dụng có thể bao gồm bất kỳ tham số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.

<div id="bonus-claimed-bonus_claimed" />

<Accordion title="Phần thưởng đã nhận (bonus_claimed)">

**Mục đích**

Xem có bao nhiêu người dùng đã nhận phần thưởng thêm được cung cấp cho họ và liên kết phần thưởng thêm đã nhận với hoạt động và mức độ tương tác của người dùng.

**Kích hoạt**

Khi người dùng nhận một phần thưởng và phần thưởng đó được cập nhật vào tài khoản của họ

**Tham số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| bonus\_type | Loại phần thưởng thêm mà người dùng nhận | Tiền xu |

</Accordion>

<div data-zendesk-anchors="gaming=-ch%C6%A1i-game recommended-structures-for-predefined-events=c%E1%BA%A5u-tr%C3%BAc-s%E1%BB%B1-ki%E1%BB%87n-chu%E1%BA%A9n-khuy%C3%AAn-d%C3%B9ng recommended-structures-for-custom-events=c%E1%BA%A5u-tr%C3%BAc-s%E1%BB%B1-ki%E1%BB%87n-tu%E1%BB%B3-ch%E1%BB%89nh-khuy%C3%AAn-d%C3%B9ng" />
