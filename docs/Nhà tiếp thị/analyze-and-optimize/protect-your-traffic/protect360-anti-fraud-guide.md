---
title: Hướng dẫn chống gian lận Protect360
metadata:
  keywords:
    - Advertisers
    - Protect360
    - protect
    - protect 360
    - '360'
    - p360
    - p 360
    - 360protect
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2016-12-06T07:47:17Z'
  edited_at: '2023-11-09T05:06:40Z'
  id: 218254203
  locale: vi
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/vi/articles/218254203
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Khái quát:** Gian lận phân bổ làm cạn kiệt ngân sách tiếp thị, xâm phạm dữ liệu hiệu suất tiếp thị và có thể biến các chiến dịch thành công thành chiến dịch thất bại. **Protect360 cung cấp cho chủ sở hữu ứng dụng khả năng chống gian lận và phát hiện hậu phân bổ theo thời gian thực.**

<Image align="center" alt="p360intro2.jpg" src="https://files.readme.io/c8476382eeff62164ca93b9bf2f3c4cdbe0609d4160047eac36a44d5f333ffdb-360014803578.jpg" />

<div id="protect360-overview" />

## Tổng quan về Protect360

* Bảo vệ chống gian lận phân bổ. Giải pháp bao gồm các công cụ năng động có thể phát hiện gian lận và chặn phân bổ gian lận.
* Sử dụng quy mô, học máy và phân tích hành vi của AppsFlyer để bảo vệ chống lại các hình thức gian lận lượt nhấp/cài đặt đã biết và mới bao gồm bot và các hành vi bất thường.
* Bảo vệ các nhà tiếp thị khỏi bị gian lận ở cấp thiết bị, nhà phát hành và nguồn truyền thông.
* Sử dụng phương pháp phân lớp trong việc chặn gian lận theo thời gian thực và nhận dạng gian lận hậu phân bổ
* Không ảnh hưởng đến trải nghiệm người dùng ứng dụng. Trong trường hợp có hành vi gian lận liên quan đến người dùng thực, lượt cài đặt ứng dụng vẫn hoàn tất bình thường và chỉ ghi nhận phân bổ bị ảnh hưởng.

<div id="realtime-blocking" />

<Accordion title="Chặn theo thời gian thực">

* Theo thời gian thực, trước khi phân bổ, lượt cài đặt được xác định là đến từ một nguồn truyền thông gian lận và bị chặn phân bổ.
* Các sự kiện trong ứng dụng tiếp theo từ cùng một người dùng sẽ bị chặn.
* Các sự kiện trong ứng dụng và lượt cài đặt bị chặn được báo cáo trong bảng điều khiển Protect360 và các báo cáo lượt gian lận bị chặn.
  * Lượt cài đặt và sự kiện trong ứng dụng bị chặn: Không được đưa vào phân bổ và bảng điều khiển của AppsFlyer vì chúng chưa bao giờ được phân bổ.
* Postback cài đặt bị chặn được gửi đến các nguồn truyền thông, kèm theo lý do chặn, cho phép chúng tối ưu hóa.

<Anchor target="_blank" href="/marketers/vi/docs/protect360-raw-data-reports">Giới thiệu về sự kiện bị chặn</Anchor>

</Accordion>

<div id="postattribution-detection" />

<Accordion title="Phát hiện hậu phân bổ">

* Gian lận được phát hiện sau khi phân bổ được gọi là gian lận hậu phân bổ. Gian lận hậu phân bổ có thể được xác định vào ngày cài đặt và tối đa 7 ngày sau đó (tổng cộng 8 ngày).
* Sau khi được phân bổ thì sẽ không thể xóa lượt cài đặt. Vì lý do này, gian lận hậu phân bổ được xử lý khác với gian lận theo thời gian thực.
* Các lượt cài đặt và sự kiện trong ứng dụng gian lận được xác định trong quá khứ phải được coi là gian lận thực và không được tính tiền.

Khi một nguồn, như mạng quảng cáo hoặc ID trang web, được xác định là gian lận:

* Các lượt nhấp tương lai từ nguồn đó sẽ bị chặn.
* Lượt cài đặt trước đây:
  * Từ đầu tháng hiện tại cho tới nay, sẽ bị dán nhãn là gian lận hậu phân bổ nhưng **không bị xóa khỏi dữ liệu**. Kể từ tháng 1 năm 2020, hóa đơn của nhà quảng cáo được ghi có cho khoản phí phân bổ của các lượt cài đặt này.
  * Không thay đổi từ trước khi bắt đầu tháng hiện tại.
* Các sự kiện trong ứng dụng xảy ra:
  * **Cho đến khi** dán nhãn lượt cài đặt: được dán nhãn là gian lận.
  * **Sau khi** dán nhãn lượt cài đặt: được dán nhãn là gian lận.

Các ví dụ về gian lận hậu phân bổ:

* Các lượt cài đặt gần như định kỳ với các dấu hiệu gian lận sau đó trong các sự kiện trong ứng dụng
* Phát hiện một hình thức gian lận mới
* Các lượt cài đặt được coi là gian lận chỉ sau khi các thuật toán phát hiện bất thường thu thập đủ dữ liệu thống kê về các lượt cài đặt của bất kỳ nhà phát hành nào

</Accordion>

<div id="common-fraud-issues-and-solutions" />

<Accordion title="Các vấn đề phổ biến về gian lận và giải pháp">

Khi AppsFlyer xác định gian lận, **sự kiện** **phân bổ**liên quan đến gian lận sẽ bị chặn. Điều này giúp loại bỏ lợi ích và động lực của kẻ gian lận. **Lưu ý**: Quá trình cài đặt ứng dụng vẫn diễn ra và không bị chặn. Điều này có nghĩa là người dùng ứng dụng có thể sử dụng ứng dụng và tạo doanh thu cho nhà quảng cáo. 

Lượt nhấp chuột, lượt cài đặt và các sự kiện trong ứng dụng gian lận bị chặn được tìm thấy trong <Anchor target="_blank" href="/marketers/vi/docs/protect360-raw-data-reports">các báo cáo dữ liệu thô về gian lận của Protect360</Anchor>.

Bảng sau đây mô tả một số hình thức gian lận và cách xử lý của Protect360.

| Hình thức gian lận | Mô tả | Giải pháp của AppsFlyer |
| --- | --- | --- |
| <span id="device-id-reset-fraud"></span>**Gian lận đặt lại ID thiết bị** | Kẻ gian lận liên tục đặt lại ID thiết bị trên cùng một thiết bị vật lý để tạo ra một số lượng lớn lượt cài đặt. | AppsFlyer xác định tỷ lệ các thiết bị mới bất thường và do đó cho các nguồn mang đến thiết bị mới đó vào danh sách từ chối. |
| <span id="install-hijacking"></span>**Đánh cắp lượt cài đặt** | Kẻ gian lận cấy phần mềm độc hại vào các thiết bị di động và thiết bị phát cảnh báo khi tải ứng dụng. Ngay lập tức, một lượt nhấp được gửi về AppsFlyer yêu cầu ghi nhận lượt cài đặt. | Chặn các lượt nhấp được phân bổ có CTIT (<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-to-install-time-ctit/">Thời gian từ nhấp đến cài đặt</Anchor>) quá nhanh và dựa trên API Phía Máy chủ của Google Play. |
| <span id="click-hijacking"></span>**<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-hijacking/">Đánh cắp lượt nhấp</Anchor>** | Phần mềm độc hại ghi nhận lượt nhấp vào đường dẫn phân bổ lượt cài đặt và ngay lập tức gửi một lượt nhấp khác để được ghi nhận nếu lượt nhấp được phân bổ. | Chặn các lượt nhấp được phân bổ xảy ra rất nhanh sau các lượt nhấp khác cho cùng một ứng dụng trên cùng thiết bị. |
| <span id="click-flooding"></span>**<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-flooding/">Nhấp hàng loạt</Anchor>** | Gian lận di động là khi một số lượng lớn các lượt nhấp gian lận được gửi đi với mục đích phân phối lượt nhấp gần nhất trước khi cài đặt. | Chặn các lượt nhấp được phân bổ từ ID trang web với tỷ lệ chuyển đổi thấp và CTIT dài. |
| <span id="behavioral-anomalies"></span>**Bất thường về hành vi** | Gian lận di động là khi kẻ gian lận tạo ra một hoạt động hậu cài đặt bất thường và không nhất quán. | Quy mô duy nhất của AppsFlyer cho phép chúng tôi theo dõi và hiểu rõ mô típ tương tác hành vi trên nhiều cấp độ - chẳng hạn như theo ứng dụng, khu vực, nguồn phương tiện và nhà phát hành. Các mẫu hành vi không phải của con người được xác định trong thời gian gần thực và được chặn tại nguồn. |
| <span id="ip-denylists"></span>**Danh sách từ chối IP** | Kẻ gian lận thường hoạt động từ <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-farms/">click farm</Anchor> (trại cày lượt nhấp), có thể được xác định theo địa chỉ IP trong một thời gian dài. | <ul><li>Các địa chỉ IP bị nghi ngờ là gian lận sẽ bị đưa vào danh sách từ chối hàng ngày dựa trên dữ liệu cập nhật nhận được từ nhà cung cấp toàn cầu bên thứ ba <Anchor target="_blank" href="http://www.digitalelement.com/">Digital Element</Anchor>.</li><li>Bảo vệ danh sách từ chối IP được bật cho tất cả các ứng dụng.</li></ul> |
| <span id="sdk-authentication"></span>**Xác thực SDK** | Kẻ gian lận gửi các tin nhắn SDK giả mạo để mô phỏng hành động có giá trị của người dùng. | <ul><li>Một giao thức biến đổi hash độc quyền được sử dụng để mã hóa các thông báo giữa SDK và dịch vụ web, ngăn những kẻ gian lận bắt chước các thông báo.</li><li>Bảo vệ xác thực SDK được bật cho tất cả các ứng dụng.</li></ul> |
| <span id="store-validations"></span>**Xác thực cửa hàng** | Kẻ gian lận gửi các tin nhắn SDK để mô phỏng lượt cài đặt hoặc lượt mua trong ứng dụng nhằm nhận phí CPA cao. <Anchor target="_blank" href="/marketers/vi/docs/implement-apple-app-store-itunes-install-validation">Xác thực cửa hàng Apple</Anchor>. | Cho phép <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/install-validation/">xác thực lượt cài đặt</Anchor> trên iTunes và xác thực mua trong ứng dụng cho cả iTunes và Google Play của lượt cài đặt hoặc mua trong ứng dụng bất kỳ đã diễn ra để ngăn chặn việc phân bổ hoạt động gian lận. |

**Lưu ý**: Các giá trị thời gian chính xác được trích dẫn ở trên không được công khai để bảo vệ khách hàng của chúng tôi.

Các lý do chặn bổ sung được giải thích trong <Anchor target="_blank" href="/marketers/vi/docs/protect360-raw-data-reports">bài viết về dữ liệu thô</Anchor>.

</Accordion>

Bảng dưới đây phác thảo các loại cài đặt gian lận và các sự kiện trong ứng dụng khác nhau và điều gì sẽ xảy ra khi công cụ Protect360 chặn chúng theo thời gian thực hoặc phát hiện chúng hậu phân bổ.

<table><caption>Phát hiện gian lận và kết quả trong Protect360</caption><thead><tr><th>Hình thức gian lận</th><th>Thời gian phát hiện</th><th>Điều gì xảy ra đối với lượt cài đặt</th><th>Điều gì xảy ra đối với sự kiện trong ứng dụng</th></tr></thead><tbody><tr><td rowspan="2"><span>Lượt cài đặt giả mạo</span></td><td><span>Thời gian thực</span></td><td><span>Bị chặn theo thời gian thực</span></td><td><span>Bị chặn theo thời gian thực</span></td></tr><tr><td><span>Hậu phân bổ</span></td><td><span>Được đánh dấu trong báo cáo Lượt cài đặt Hậu Phân bổ</span></td><td><ul><li><span>Các sự kiện trong ứng dụng xảy ra trước khi phát hiện gian lận sẽ được đánh dấu trong báo cáo Sự kiện Trong Ứng dụng Hậu Phân bổ.</span></li><li><span>Sau khi phát hiện: bị chặn theo thời gian thực</span></li></ul></td></tr><tr><td rowspan="2"><span>Đánh cắp phân bổ lượt cài đặt</span></td><td><span>Thời gian thực</span></td><td><ul><li><span>Bị chặn theo thời gian thực</span></li><li><span>Phân bổ được sửa thành nguồn hợp lệ cuối</span></li></ul></td><td><ul><li><span>Xuất hiện trong báo cáo Sự kiện Trong Ứng dụng bị Chặn</span></li><li><span>Được phân bổ cho cùng một nguồn hợp lệ như lượt cài đặt</span></li></ul></td></tr><tr><td><span>Hậu phân bổ</span></td><td><span>Được đánh dấu trong báo cáo Lượt cài đặt Hậu Phân bổ</span></td><td><ul><li><span>Các sự kiện trong ứng dụng xảy ra trước khi phát hiện gian lận sẽ được đánh dấu trong báo cáo Sự kiện Trong Ứng dụng Hậu Phân bổ.</span></li><li><p>Sau khi phát hiện gian lận: đánh dấu vào báo cáo Sự kiện Trong Ứng dụng Hậu Phân bổ tối đa 30 ngày kể từ thời điểm cài đặt.\*</p><p>\*Các sự kiện trong ứng dụng được sửa thành nguồn truyền thông hợp lệ cuối cùng trong 30 ngày kể từ khi cài đặt. Các sự kiện xảy ra sau 30 ngày không được sửa.</p></li></ul></td></tr><tr><td rowspan="2"><span>Gian lận sự kiện trong ứng dụng</span></td><td><span>Thời gian thực</span></td><td>-</td><td><span>Bị chặn theo thời gian thực</span></td></tr><tr><td><span>Hậu phân bổ</span></td><td>-</td><td><span>Được đánh dấu trong báo cáo Sự kiện Trong Ứng dụng Hậu Phân bổ</span></td></tr></tbody></table>

<div id="using-protect360" />

## Sử dụng Protect360

<div id="dashboard" />

<Accordion title="Bảng điều khiển">

<Anchor target="_blank" href="/marketers/vi/docs/protect360-dashboard">Bảng điều khiển Protect360</Anchor> hiển thị dữ liệu gian lận hợp nhất và cung cấp thông tin chi tiết liên quan đến lưu lượng truy cập gian lận.

Chế độ xem bảng điều khiển:

**Lượt cài đặt**: Thông tin chi tiết <Anchor target="_blank" href="/marketers/vi/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">dựa trên LTV</Anchor> về các lượt cài đặt gian lận, bị chặn theo thời gian thực và được xác định hậu phân bổ. Bạn có thể truy cập sâu để kiểm tra thêm các sự kiện gian lận bằng cách sử dụng các tùy chọn lọc và nhóm.

**Sự kiện trong ứng dụng**: Thông tin chi tiết <Anchor target="_blank" href="/marketers/vi/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">dựa trên hoạt động</Anchor> về các sự kiện trong ứng dụng gian lận, bị chặn theo thời gian thực và xác định hậu phân bổ. Bạn có thể truy cập sâu để kiểm tra thêm các sự kiện gian lận bằng cách sử dụng các tùy chọn lọc và nhóm.

**Điểm bất thường**: Thông tin về các nguồn truyền thông có lượt cài đặt với giá trị thời gian từ nhấp đến cài đặt (CTIT) bất thường, khi so sánh với các nguồn đáng tin cậy khác.

* Tham khảo chéo các lượt cài đặt đáng ngờ với dữ liệu lượt cài đặt thô của bạn và tìm kiếm các dấu hiệu đáng ngờ như số phiên bản của ứng dụng lạ, phiên bản hệ điều hành cũ, vị trí khác biệt, v.v.
* Sử dụng <Anchor target="_blank" href="/marketers/vi/docs/implement-validation-rules-to-prevent-fraud#protect360-install-and-inapp-event-sources">Quy tắc xác thực</Anchor> để chặn cài đặt với các giá trị CTIT ngắn. Protect360 tự động chặn cài đặt có giá trị CTIT rất thấp.

</Accordion>

<div id="raw-data" />

<Accordion title="Dữ liệu thô">

<Anchor target="_blank" href="/marketers/vi/docs/protect360-raw-data-reports">Dữ liệu thô</Anchor> về gian lận có sẵn qua API Pull, Dữ liệu xuất và <Anchor target="_blank" href="/marketers/vi/docs/data-locker-for-marketers">Data Locker (một tính năng cao cấp)</Anchor>.

Các báo cáo dữ liệu thô được chia như sau:

* Báo cáo bị chặn: Lượt cài đặt, lượt nhấp và sự kiện trong ứng dụng của những người dùng có phân bổ bị chặn và hoàn toàn không được phân bổ cho bất kỳ nguồn truyền thông nào.
* Các báo cáo hậu phân bổ:
  * Các lượt cài đặt được phân bổ cho một nguồn truyền thông, nhưng sau đó bị phát hiện là gian lận.
  * Sự kiện trong ứng dụng:
    * của lượt cài đặt được xác định là gian lận sau khi được phân bổ cho một nguồn truyền thông.
    * bị đánh giá là gian lận mà không liên quan đến bản thân lượt cài đặt.

* Nhà quảng cáo sử dụng các báo cáo này để đối chiếu các tài khoản mạng quảng cáo, để tối ưu hóa và để điều chỉnh bảng điều khiển phân bổ nhằm chống lại gian lận hậu phân bổ.

</Accordion>

<div id="validation-rules" />

<Accordion title="Quy tắc Xác thực">

<Anchor target="_blank" href="/marketers/vi/docs/implement-validation-rules-to-prevent-fraud">Quy tắc Xác thực</Anchor> cho phép chủ sở hữu ứng dụng đặt ra điều kiện để chặn một số lượt cài đặt nhất định, chặn phân bổ (và đảm bảo rằng lượt cài đặt được phân bổ cho nguồn truyền thông hợp lệ gần đây nhất) hoặc chặn các sự kiện trong ứng dụng.

</Accordion>

<div id="fraud-reconciliation-with-ad-networks" />

<Accordion title="Gian lận đối chiếu với các mạng quảng cáo">

Với Protect360, các nhà quảng cáo có được dữ liệu thô liên quan đến các lượt cài đặt gian lận và các sự kiện trong ứng dụng với các mạng quảng cáo có thể không ghi nhận là gian lận.

Nếu bạn phát hiện ra rằng một mạng quảng cáo đã gửi cho bạn lưu lượng truy cập từ các nguồn đáng ngờ, hãy thông báo cho mạng quảng cáo đó và yêu cầu họ ngừng gửi cho bạn lưu lượng truy cập từ các nguồn đáng ngờ đó. Sử dụng cột báo cáo lượt cài đặt dữ liệu thô được gọi là **Thời gian Tiếp xúc được Phân bổ** để xác minh rằng bạn không nhận thêm lượt cài đặt nào từ nguồn này sau khi bạn yêu cầu ngừng gửi lưu lượng truy cập.

Bạn cũng có thể sử dụng dữ liệu Protect360 để đối chiếu với các mạng quảng cáo và nhận về toàn bộ hoặc một phần tiền hoàn lại cho lưu lượng truy cập trước đây từ các nguồn đáng ngờ.

**Để đối chiếu các chiến dịch dựa trên CPI bằng Protect360:**

* Vào đầu mỗi tháng, hãy liên hệ với người quản lý tài khoản trong mỗi mạng quảng cáo nơi xảy ra gian lận.
* Thu thập dữ liệu thô về lượt cài đặt gian lận có liên quan từ các báo cáo Lượt cài đặt bị chặn và [lượt cài đặt hậu phân bổ](/docs/protect360-anti-fraud-guide#postattribution-detection).
* Chia sẻ dữ liệu thô về hành vi gian lận với mạng để đối chiếu và tối ưu hóa lưu lượng truy cập của mạng đó.
* Có thể tạo báo cáo dữ liệu thô chỉ gồm các lượt cài đặt hợp lệ nhưng loại trừ các lượt cài đặt gian lận hậu phân bổ. Để thực hiện, bạn cần tải xuống báo cáo ***Lượt cài đặt UA được phân bổ*** hàng tháng và loại trừ tất cả các mục nhập khỏi báo cáo ***Lượt cài đặt hậu phân bổ***.

**Để đối chiếu các chiến dịch dựa trên CPA/CPE bằng Protect360:**

* Vào đầu mỗi tháng, hãy liên hệ với người quản lý tài khoản trong mỗi mạng quảng cáo nơi xảy ra gian lận.
* Thu thập dữ liệu thô các sự kiện trong ứng dụng gian lận có liên quan từ các báo cáo Sự kiện trong ứng dụng bị chặn và [Sự kiện trong ứng dụng](/docs/protect360-anti-fraud-guide#postattribution-detection) Hậu phân bổ.
* Chia sẻ dữ liệu thô về hành vi gian lận với mạng để đối chiếu và tối ưu hóa lưu lượng truy cập của mạng đó.
* Có thể tạo báo cáo dữ liệu thô chỉ bao gồm các IAE hợp lệ, nhưng loại trừ các sự kiện gian lận hậu phân bổ. Để thực hiện, bạn cần tải xuống báo cáo ***Sự kiện trong ứng dụng UA được phân bổ*** hàng tháng và loại trừ tất cả các mục nhập khỏi báo cáo ***Sự kiện trong ứng dụng hậu phân bổ***.

</Accordion>

<div id="traits-and-limitations" />

## Đặc điểm và hạn chế

<div id="traits-and-limitations::a07033c3" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Nhận xét |
| --- | --- |
| Truy cập nhà quảng cáo | Tất cả người dùng tài khoản. |
| Truy cập mạng quảng cáo | <ul><li>Bảng điều khiển Protect360 và quyền truy cập dữ liệu thô yêu cầu phải được <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#quyền-truy-cập-mạng-quảng-cáo">nhà quảng cáo cho phép.</Anchor></li><li>Nhà quảng cáo phải có mạng quảng cáo như một đối tác tích hợp.</li></ul> |
| Truy cập đại lý | Bảng điều khiển Protect360 và quyền truy cập dữ liệu thô yêu cầu phải được <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#quyền-truy-cập-mạng-quảng-cáo">nhà quảng cáo cho phép.</Anchor> |
| Tính minh bạch của agency | Tính minh bạch của đại lý: Có thể xem các nguồn truyền thông cụ thể<br /><br />Đại lý không minh bạch: Không thể xem các nguồn truyền thông cụ thể |
| Múi giờ riêng cho ứng dụng | <ul><li>Múi giờ cụ thể cho ứng dụng sẽ được sử dụng trong bảng điều khiển với điều kiện là tất cả các ứng dụng được đặt về cùng một múi giờ.</li><li>Nếu các ứng dụng không được đặt về cùng một múi giờ, thì bảng điều khiển sẽ mặc định thành UTC.</li></ul> |
| Độ mới của dữ liệu | <ul><li>Bảng điều khiển của Protect360: Cập nhật <Anchor target="_blank" href="/marketers/vi/docs/about-data-freshness-and-timezone-support#eod">Hàng ngày</Anchor>.<br />Thời gian cập nhật gần đây nhất, hiển thị bên dưới bộ lọc phạm vi ngày trong Bảng điều khiển.</li><li>Báo cáo:<ul><li>Số lượt cài đặt bị chặn và sự kiện trong ứng dụng: Cập nhật liên tục gần nhưu theo thời gian thực.</li><li>Hậu phân bổ: <Anchor target="_blank" href="/marketers/vi/docs/about-data-freshness-and-timezone-support#eod">Hàng ngày</Anchor> sử dụng UTC.</li></ul></li></ul> |
| Lượt cài đặt lại | Dữ liệu gian lận đối với lượt cài đặt lại chỉ có sẵn ở dạng dữ liệu thô. Do đó, có thể có sự khác biệt giữa các con số tổng thể trong bảng điều khiển và báo cáo dữ liệu thô. |
| Nhắm mục tiêu lại | <ul><li>Đối với các lượt cài đặt được xác định là gian lận thì sẽ hiển thị bảng phân tích loại tương tác được phân bổ giữa các lượt cài đặt, phân bổ lại và thu hút lại.</li><li>Đối với các sự kiện trong ứng dụng:<ul><li>Bảng điều khiển sự kiện trong ứng dụng (CPA) hiển thị các sự kiện gian lận từ lượt cài đặt UA, chứ không phải từ nhắm mục tiêu lại.</li><li>Các sự kiện gian lận từ phân bổ lại được xác định theo thời gian thực, có thể xem được trong các báo cáo dữ liệu thô. Không thể xác định các sự kiện gian lận từ các lượt thu hút lại.</li><li>Không thể xác định các sự kiện gian lận từ nhắm mục tiêu lại sau phân bổ.</li></ul></li></ul> |
| Điểm hạn chế | <ul><li>Bảng giới hạn tối đa 20.000 hàng.</li><li>Nếu bạn truy vấn một tập dữ liệu lớn hơn, một số nguồn truyền thông có thể bị loại trừ. Để khắc phục hạn chế này, chúng tôi khuyến nghị như sau:<ul><li>Truy vấn bộ dữ liệu nhỏ hơn - khoảng thời gian ngắn hơn, ứng dụng cụ thể và nguồn phương tiện cụ thể</li><li>Xuất <Anchor target="_blank" href="/marketers/vi/docs/protect360-raw-data-reports">báo cáo dữ liệu thô Protect360</Anchor></li><li>Xuất Báo cáo Phát hiện Nâng cao Hợp nhất Protect360 <Anchor target="_blank" href="/marketers/vi/docs/pull-api-aggregate-data">thông qua API Pull</Anchor></li></ul></li></ul> |

</Accordion>

<div id="faq-and-tips" />

## Câu hỏi thường gặp và mẹo

<div id="faq" />

<Accordion title="Câu hỏi thường gặp">

| **Widget Tiết kiệm ước tính được tính như thế nào?**<br /><br />Đối với <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview">các mạng hỗ trợ chia sẻ dữ liệu chi phí</Anchor>, bạn nhận được số tiền tiết kiệm ước tính chính xác.<br /><br />Đối với các mạng không hỗ trợ chức năng này, AppsFlyer sử dụng chỉ số eCPI trung bình từ toàn bộ nhóm lượt cài đặt đã xác thực từ tất cả các nguồn có dữ liệu chi phí. |
| --- |
| **Protect360 có chống gian lận hiệu quả đến từ các đường dẫn phân bổ tùy chỉnh không?**<br /><br />Chắc chắn rồi! Protect360 phát hiện và chặn các hành vi gian lận đến từ các đường dẫn phân bổ tùy chỉnh, ngoài các mạng quảng cáo. Điều đó có nghĩa là bạn cũng được bảo vệ nếu bạn có các chiến dịch truyền thông của riêng mình, chẳng hạn như với những người có ảnh hưởng, chiến dịch email và SMS, biểu ngữ trang web và trang đích, bài đăng thu hút nhiều sự quan tâm trên phương tiện truyền thông xã hội, Thông báo đẩy hoặc thậm chí mã QR. |
| **Phiên bản 2 của Protect360 có gì mới so với phiên bản 1?**<ol><li>Có 3 thay đổi chính trong P360 V2.0:<br />Gian lận hậu phân bổ - bất cứ ở đâu chúng tôi hiển thị lượt cài đặt bị chặn, chúng tôi cũng thể hiện các lượt cài đặt gian lận hậu phân bổ. Hậu phân bổ cũng có sẵn dưới dạng báo cáo dữ liệu thô.</li><li>Thông tin bất thường - Một phần mới có tên gọi "Thông tin bất thường" được bổ sung, trong đó nhà quảng cáo có thể phân tích các bất thường thông qua các công cụ trực quan. Phần sẽ thay thế 2 biểu đồ trên tab "Phát hiện nâng cao" cũ.</li><li>Tập trung tất cả dữ liệu gian lận - tab "phát hiện nâng cao" đã được loại bỏ và thay vào đó chúng tôi trình bày tất cả các thông tin trong 1 tab.</li></ol> |
| **Tại sao không có dữ liệu thô hậu phân bổ trong trang Export Data (Dữ liệu xuất)?**<br /><br />Báo cáo hậu phân bổ được trình bày ở cấp độ tài khoản cho mỗi nguồn truyền thông để tạo thuận lợi cho quy trình đối chiếu. Trang **Export Data** (Xuất Dữ liệu) ở cấp độ ứng dụng đơn lẻ và vẫn bao gồm các dữ liệu gian lận bị Chặn trên cấp độ ứng dụng để tương thích ngược trở lại. |
| **Dữ liệu hậu phân bổ có cập nhật ngược trở lại không?**<ul><li>**Lượt cài đặt** - dữ liệu cài đặt trên trang tổng quan và tất cả các báo cáo khác ngoài bảng điều khiển Protect360 không cập nhật ngược trở lại.</li><li>**Sự kiện trong ứng dụng** - một khi lớp bảo vệ hậu phân bổ xác định lượt cài đặt là giả mạo thì các sự kiện trong ứng dụng đến từ cài đặt này sẽ bị chặn. Các sự kiện trong ứng dụng trước không cập nhật ngược trở lại.</li></ul> |
| **Tại sao dữ liệu trông khác khi chọn các mạng cụ thể/khác nhau trong Thông tin bất thường?**<br /><br />Khi bạn xem xét các điểm bất thường của CTIT và chọn AF\_Baseline làm điểm chuẩn, bạn có thể thấy các điểm bất thường của Mạng A. Sau đó, ví dụ: nếu bạn chọn Mạng A làm điểm chuẩn, bạn sẽ thấy sự bất thường của các mạng khác, nhưng không phải của Mạng A.<br /><br />Kết quả này thực ra không bất ngờ. Khi sử dụng đường cơ sở AppsFlyer đáng tin cậy, các mạng có tỷ lệ CTIT bất thường sẽ được hiển thị. Khi mạng bất thường được sử dụng làm đường cơ sở, các lượt cài đặt của mạng đó không còn được coi là bất thường nữa, nhưng các lượt cài đặt từ các mạng khác có thể được coi là bất thường so với nó. |
| **Lưu lượng truy cập bất thường thực sự có phải là gian lận không?**<br /><br />Có thể biến động bất thường về lưu lượng truy cập tự nhiên thực sự là gian lận. Nói chung, nếu thấy lưu lượng truy cập tự nhiên trong AppsFlyer mà bạn có lý do để tin là gian lận thực sự thì có thể là một trong 3 trường hợp sau:<ul><li>**Gian lận phân bổ không thành công:** Lượt nhấp của kẻ gian lận không nhận được phân bổ, ví dụ: nhấp hàng loạt với lượt nhấp cuối cùng diễn ra ngoài khung thời gian xem lại lượt nhấp.</li><li>**Gian lận không phân bổ:** Người dùng có hành vi gian lận, không liên quan đến việc phân bổ, ví dụ: gian lận để thu thập vật phẩm trong các trò chơi chiến lược.</li><li>**Sự cố tích hợp SDK:** Kiểm tra xem các sự kiện trong ứng dụng của bạn có được gửi chính xác không, tức là vào đúng thời điểm trong luồng và với các giá trị thông số sự kiện chính xác.</li></ul> |

</Accordion>

<div id="benchmarks-and-tips" />

<Accordion title="Mốc chuẩn và mẹo">

| **Phát hiện gian lận thiết bị mới**<br /><br />Những kẻ gian lận có thể che giấu thiết bị của họ bằng cách thường xuyên đặt lại ID chính của thiết bị của họ, tức là IDFA cho iOS và GAID cho Android.<br /><br />Thật may là AppsFlyer có thể xác định hơn 98% thiết bị di động toàn cầu.<br /><br />Do vậy, tỷ lệ phần trăm các thiết bị không xác định cao là một dấu hiệu rõ ràng cho thấy gian lận bởi các click farm (trại cày lượt xem), trừ khi cố tình nhắm mục tiêu vào các thiết bị mới.<br /><br />**Phát hiện thiết bị mới:**<ol><li>Trong Protect360, đi đến bảng ***Phân tích gian lận đã xác định***.</li><li>Cuộn thẳng đến cột ***Device farm indicators - new devices*** (Dấu hiệu kho thiết bị - thiết bị mới).</li><li>Nhấp vào tên cột ***Installs %*** (% Lượt cài đặt) để sắp xếp bảng theo thứ tự tỷ lệ thiết bị mới giảm dần.</li><li>Dấu hiệu gian lận thiết bị mới:</li></ol><ul><li>Các nguồn có tỷ lệ phần trăm **các** thiết bị mới cao. **Lưu ý**: Khi số lượt cài đặt tăng lên, tỷ lệ phần trăm thấp hơn cũng có thể được coi là gian lận (vì có số lượng tổng thể lớn).<ul><li>Khi tỷ lệ người dùng trung thành của nguồn được so sánh với tỷ lệ người dùng trung thành tổng thể, tỷ lệ tương đối thấp chính là dấu hiệu gian lận rõ ràng.</li></ul></li></ul>**Lưu ý**: Các chiến dịch <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-factory-preinstall-using-manifest-android">ứng dụng được cài đặt sẵn</Anchor> thường có tỷ lệ thiết bị mới rất cao, vì đây có thể là một trong những ứng dụng đầu tiên mà người dùng khởi chạy khi kích hoạt thiết bị mới của họ. Do đó, đối với các ứng dụng được cài đặt sẵn, việc gian lận thiết bị mới sẽ khó xảy ra, ngay cả với tỷ lệ thiết bị mới cao. |
| --- |
| **Phát hiện gian lận LAT**<br /><br />Người dùng LAT (Giới hạn Theo dõi Quảng cáo) chọn không để lộ ID, IDFA hoặc GAID của thiết bị của họ với nhà quảng cáo. Khoảng 15% người dùng iOS và 10% người dùng Android đưa ra lựa chọn này.<br /><br />Tương tự xếp hạng thiết bị mới, người dùng LAT có thể là những người dùng hợp lệ. Tuy nhiên, tỷ lệ phần trăm này cao có thể là dấu hiệu của hoạt động gian lận.<br /><br />**Phát hiện LAT:**<ol><li>Trong Protect360, đi đến bảng ***Phân tích gian lận đã xác định***.</li><li>Cuộn thẳng đến cột ***Device farm indicators (Dấu hiệu kho thiết bị) - LAT devices*** (Thiết bị LAT).</li><li>Nhấp vào tên cột ***Installs %*** (% lượt cài đặt) để sắp xếp bảng theo trật tự tỷ lệ thiết bị LAT giảm dần.</li><li>Dấu hiệu gian lận thiết bị LAT mới:</li></ol><ul><li>Các nguồn có tỷ lệ phần trăm các thiết bị **LAT** cao. **Lưu ý**: Khi số lượt cài đặt tăng lên, tỷ lệ phần trăm thấp hơn cũng có thể được coi là gian lận (vì có số lượng tổng thể lớn).</li><li>Khi tỷ lệ người dùng trung thành của nguồn được so sánh với tỷ lệ người dùng trung thành tổng thể, tỷ lệ tương đối thấp chính là dấu hiệu gian lận rõ ràng.</li></ul> |
| **Phát hiện gian lận nhấp hàng loạt**<ol><li>Bằng công cụ Nhấp hàng loạt, những kẻ lừa đảo sẽ gửi hàng triệu lượt nhấp với ID thiết bị thực, với hy vọng đăng ký làm lượt nhấp cuối cho những người dùng thực. Các nguồn có loại gian lận này có **tỷ lệ chuyển đổi rất thấp, nhưng người dùng chất lượng cao**, bởi đây là những người dùng thực.</li></ol>**Phát hiện nhấp chuột hàng loạt:**<ol><li>Trong Protect360, đi đến bảng ***Phân tích gian lận đã xác định***.</li><li>Cuộn thẳng đến cột ***Click flooding indicators*** (Dấu hiệu nhấp hàng loạt).</li><li>Nhấp vào tên cột ***Conversion rate*** (Tỷ lệ chuyển đổi) để sắp xếp bảng theo thứ tự tỷ lệ chuyển đổi tăng dần.</li><li>Mốc chuẩn gian lận nhấp hàng loạt:</li></ol><ul><li>Tỷ lệ chuyển đổi ***bình thường*** nằm trong khoảng 0,5% đến 35%.<br />Hãy nghi ngờ các nguồn có tỷ lệ chuyển đổi thấp bất thường hoặc **có tỷ lệ chuyển đổi trung bình của ứng dụng từ 25% trở xuống**. Bạn có thể tìm thấy KPI này trong bảng Báo cáo hiệu suất hợp nhất trong trang bảng điều khiển tổng quan.</li><li>Đối với các nguồn có tỷ lệ không rõ ràng, hãy so sánh ***% Hỗ trợ*** với tỷ lệ hỗ trợ trung bình. Bạn có thể xem tỷ lệ hỗ trợ bình thường trong widget hỗ trợ, ở trang bảng điều khiển tổng quan.<br />Các nguồn có tỷ lệ hỗ trợ **cao hơn 50% so với tỷ lệ hỗ trợ trung bình** của ứng dụng được coi là đáng ngờ.<br />Lưu ý rằng càng nhiều nguồn được sử dụng bởi ứng dụng thì tỷ lệ Đóng góp càng cao.</li></ul> |
| **Phát hiện nhấp hàng loạt bằng các chỉ số CTIT**<br /><br />Một dấu hiệu khác của hiện tượng nhấp hàng loạt, là **phân phối đồng đều CTIT**.<br />Thông thường, khoảng 70% lượt cài đặt bình thường diễn ra trong vòng 1 giờ kể từ khi thu hút với quảng cáo.<br />Với hiện tượng nhấp hàng loạt, không có mối liên hệ nào giữa thu hút giả và lượt cài đặt thực tế. Điều này dẫn đến số lượt cài đặt gian lận nhiều hơn 30% rất nhiều, có CTIT dài hơn 1 giờ.<br /><br />**Phát hiện các dấu hiện CTIT của tình trạng nhấp hàng loạt:**<ol><li>Trong Protect360, đi đến bảng ***Phân tích gian lận đã xác định***.</li><li>Cuộn thẳng đến cột ***Click flooding indicators*** ***- CTIT*** (Dấu hiệu nhấp hàng loạt - CTIT).</li><li>Mốc chuẩn CTIT nhấp hàng loạt:</li></ol><ul><li>Thông thường, các giá trị ***Trên 60 phút*** phải là khoảng 30%. Hãy nghi ngờ những nguồn có hơn 50% với số liệu này.</li><li>Thông thường, các giá trị ***Trên 5 tiếng*** phải là khoảng 20%. Hãy nghi ngờ những nguồn có hơn 40% với số liệu này.</li></ul>Sử dụng trang ***Anomaly insights*** <Anchor target="_blank" href="/marketers/vi/docs/protect360-dashboard#bảng-điều-khiển-về-bất-thường">(Thông tin chi tiết về bất thường)</Anchor> để điều tra các nguồn có CTIT đáng ngờ. |

</Accordion>

<div id="advanced-antifraud-tips" />

<Accordion title="Mẹo chống gian lận nâng cao">

| **Số lượt cài đặt**<br /><br />Việc lọc theo số lượt cài đặt mỗi nguồn đã kiểm tra có ý nghĩa rất quan trọng trong việc phát hiện những nguồn gian lận lớn nhất. Ngoài ra, số lượt cài đặt thấp hơn có thể không đáng kể về mặt toán học. Lưu ý:<br /><br />**Lưu ý**: Các nguồn có dưới 30 lượt cài đặt hoặc thậm chí 50 là không đủ lớn để đưa ra kết luận. Mở rộng khoảng ngày hoặc các tiêu chí tìm kiếm khác để có thêm các kết quả đáng kể. |
| --- |
| **Thay đổi định nghĩa về người dùng trung thành**<br /><br />Định nghĩa mặc định về Người dùng trung thành là từ 3 lượt khởi chạy ứng dụng trở lên. Đây là một chỉ số KPI quan trọng để đánh giá thu hút người dùng, nhưng đáng tiếc là nhiều kẻ gian lận biết điều này và lợi dụng để làm giả tỷ lệ người dùng trung thành cao, do đó tránh được nghi ngờ. Tránh bị lừa bằng cách tạo và chọn một định nghĩa về người dùng trung thành tinh vi và hợp lý hơn.<br /><br />Phân tích KPI chất lượng người dùng ứng dụng của bạn, chẳng hạn như đăng ký, hoàn thành hướng dẫn, mua hàng, nhiều phiên. Trong mã ứng dụng, hãy gửi sự kiện trong ứng dụng **mới dành cho người dùng trung thành** nếu người dùng thực hiện TẤT CẢ danh sách KPI.<br /><br />Sau khi sự kiện **người dùng trung thành** không tự nhiên đầu tiên được gửi đi, hãy đi đến **App Settings** (Cài đặt của ứng dụng) và chọn sự kiện đó để chỉ ra người dùng trung thành cho ứng dụng của bạn. Dự kiến tỷ lệ người dùng trung thành tổng quan sẽ giảm nhẹ và sau đó giảm mạnh đối với các nguồn gian lận. |

</Accordion>

<div id="tip" />

> 👍 **Lời khuyên**
>
> Bạn muốn hiểu rõ hơn về bảo vệ chống lại gian lận? Hãy xem khóa học <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7809/play/18635/mobile-app-fraud-and-protect360">ngắn, bổ ích này trên Cổng thông tin Học tập AppsFlyer</Anchor>.

<div id="see-also" />

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/protect360-raw-data-reports">Dữ liệu thô</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/marketers-guide-mobile-ad-fraud/">Hướng dẫn giới thiệu dành cho nhà tiếp thị về gian lận quảng cáo di động</Anchor>

<div data-zendesk-anchors="protect360-overview=t%E1%BB%95ng-quan-v%E1%BB%81-protect360 h_01HE7RSPPQ4T5J3W038EZRCTCE=t%E1%BB%95ng-quan-v%E1%BB%81-protect360 h_01HE7RSPPQ5BH7HBK0R8SY1T16=realtime-blocking h_01HE7RSPPRW4CQ3GB9ZEYAA6YN=postattribution-detection h_01HE7RSPPRYMQKJH46JET2ZZ0T=common-fraud-issues-and-solutions using-protect360=s%E1%BB%AD-d%E1%BB%A5ng-protect360 h_01HE7RSPPR8Y8J1VJJXXDCAZE6=s%E1%BB%AD-d%E1%BB%A5ng-protect360 h_01HE7RSPPR04G3SCSYHSWJKQDG=dashboard h_01HE7RSPPRS6PSTZCR5RT4A5ND=raw-data h_01HE7RSPPR8C9MHRAGJXYD2VVZ=validation-rules h_01HE7RSPPR1PQ2R6NJPRQGS1K1=fraud-reconciliation-with-ad-networks traits-and-limitations=%C4%91%E1%BA%B7c-%C4%91i%E1%BB%83m-v%C3%A0-h%E1%BA%A1n-ch%E1%BA%BF h_01HE7RSPPRV797PS12NFQHX1X5=%C4%91%E1%BA%B7c-%C4%91i%E1%BB%83m-v%C3%A0-h%E1%BA%A1n-ch%E1%BA%BF h_01HE7RSPPRWRKR1Y25PZV2RMVV=traits-and-limitations::a07033c3 faq-and-tips=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%C3%A0-m%E1%BA%B9o h_01HE7RSPPSV2TT8SMK8JZXFKMC=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%C3%A0-m%E1%BA%B9o h_01HE7RSPPS01J796008HDS1CRW=faq h_01HE7RSPPS018W98JWZGED54W8=benchmarks-and-tips h_01HE7RSPPSEDZWRH929DBSWEWM=advanced-antifraud-tips h_01HE7RSPPSY161MSQVQW7M767F=l%E1%BB%9Di-khuy%C3%AAn h_01HE7RX6167Q5QP5JNZDSXCCK5=xem-th%C3%AAm" />
