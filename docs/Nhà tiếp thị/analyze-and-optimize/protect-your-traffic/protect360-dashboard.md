---
title: Bảng điều khiển của Protect360
metadata:
  keywords:
    - dashboard
    - Advertisers
    - Protect360
    - protect 360
    - '360'
    - P360
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-08-11T09:58:07Z'
  edited_at: '2023-11-09T05:07:18Z'
  id: 360011793077
  locale: vi
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/vi/articles/360011793077
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Khái quát**: Bảng điều khiển Protect360 cung cấp những thông tin chuyên sâu về lưu lượng truy cập gian lận và các lượt cài đặt bị chặn do việc áp dụng các quy tắc xác thực.

<Image align="center" alt="p360_dashboard_main.png" src="https://support.appsflyer.com/hc/article_attachments/5218491552273" />

<div id="about-protect360-dashboard" />

## Giới thiệu về bảng điều khiển Protect360

Bảng điều khiển Protect360:

* Hiển thị dữ liệu gian lận hợp nhất ở cấp tài khoản.
* Có ba chế độ xem của bảng điều khiển:
  * Lượt cài đặt (CPI)
  * Sự kiện trong ứng dụng (CPA)
  * Bất thường
* Sắp xếp gian lận dựa trên các danh mục, bao gồm:
  * Lượt cài đặt giả so với lượt cài đặt bị đánh cắp
  * Gian lận bị chặn theo thời gian thực so với gian lận được xác định hậu phân bổ
  * Gian lận từ UA so với các chiến dịch nhắm mục tiêu lại
* Cho phép bạn truy cập sâu để xem xét thêm các sự kiện gian lận bằng cách sử dụng các tùy chọn lọc và nhóm.

Để xem bảng điều khiển Protect360, trong AppsFlyer, hãy đi đến **Dashboard** (Bảng điều khiển) > **Protect360.** 

<div id="filters-and-groupings" />

<Accordion title="Bộ lọc và nhóm">

**Cửa sổ bộ lọc và nhóm**

<Image align="center" alt="p360_filters_2.png" src="https://files.readme.io/9fd2afbbfc1bdf671ae0427d75c1020085b36da724e40dcfe57da27943e15b0c-4408431325969.png" />

Các tùy chọn lọc và nhóm sau đây có sẵn:

* Bộ lọc cơ bản:
  * Tên ứng dụng
  * Loại nguồn: Không tự nhiên và/hoặc tự nhiên
  * Nguồn truyền thông
  * Địa lý
  * Phạm vi ngày (<Anchor target="_blank" href="/marketers/vi/docs/about-data-freshness-and-timezone-support#protect360-dashboard">xem phần hỗ trợ múi giờ</Anchor>)
  * Loại phân bổ: Lượt cài đặt, lượt phân bổ lại và/hoặc lượt thu hút lại
  * [Các sự kiện phải trả](/docs/protect360-dashboard#payable-events) (có sẵn trong bảng điều khiển Sự kiện trong ứng dụng)
* Bộ lọc mở rộng - nhấp vào mũi tên màu xanh lam, ở bên phải của công cụ chọn ngày:
  * Đại lý
  * Chiến dịch
  * Kênh
* Tùy chọn nhóm - chọn các phương diện khác nhau để nhóm dữ liệu gian lận theo để có được thông tin chi tiết cụ thể bạn cần:
  * **Ứng dụng:** So sánh tổng số trường hợp gian lận trên mỗi ứng dụng của bạn.
  * **Nguồn Truyền thông** (mặc định): So sánh gian lận được xác định từ mỗi nguồn truyền thông mà ứng dụng của bạn sử dụng
  * **Nguồn Truyền thông + Chiến dịch**: So sánh gian lận được xác định từ tất cả các chiến dịch trên tất cả các nguồn truyền thông mà ứng dụng của bạn sử dụng
  * **Nguồn Truyền thông + ID Trang**: So sánh gian lận được xác định từ tất cả các đơn vị phát hành (ID trang web) trên tất cả các nguồn truyền thông mà ứng dụng của bạn sử dụng
  * **Nguồn Truyền thông + ID Trang + Chiến dịch**: So sánh gian lận được xác định từ tất cả các nhà phát hành (ID trang) trên tất cả các nguồn truyền thông được ứng dụng của bạn sử dụng, liên kết với các tên chiến dịch liên quan
  * **Nguồn truyền thông + Địa lý**: (có sẵn trong bảng điều khiển Sự kiện trong ứng dụng): so sánh gian lận được xác định từ từng nguồn truyền thông được ứng dụng của bạn sử dụng liên kết với các quốc gia liên quan
  * **Nguồn truyền thông + Loại phân bổ**: So sánh gian lận được xác định từ từng nguồn truyền thông của bạn, được liên kết với loại phân bổ đã chọn (lượt cài đặt, phân bổ lại và/hoặc thu hút lại)
  * **Địa lý**: so sánh gian lận được xác định từ tất cả các quốc gia

</Accordion>

<div id="installs-dashboard" />

## Bảng điều khiển lượt cài đặt

Bảng điều khiển lượt cài đặt hiển thị dữ liệu dựa trên LTV, nghĩa là dữ liệu liên quan đến lượt cài đặt, phân bổ lại và thu hút lại đã diễn ra trong phạm vi ngày bạn đã chọn.

Các tính năng của bảng điều khiển được mô tả trong các phần tiếp theo.

<div id="installs-headline-metrics" />

<Accordion title="Lượt cài đặt —s ố liệu dạng tiêu đề">

Các số liệu dạng tiêu đề cho phép bạn xem:

* Mức tiết kiệm ước tính
* Tổng số lượt cài đặt gian lận,
* Số sự kiện gian lận (trong ứng dụng)
* Bất thường

Đối với mỗi chỉ số KPI, sẽ có một giá trị phần trăm. Giá trị này thể hiện chỉ số KPI được hiển thị có liên quan như thế nào với khoảng ngày song song trước đó. Ví dụ, tuần này so với tuần trước hoặc bất kỳ ngày nào được chọn trong phạm vi ngày so với cùng số ngày trước đó: nếu chỉ số hiển thị mức tiết kiệm ước tính tăng X%, thì điều này có nghĩa là phạm vi ngày song song trước đó có lượt cài đặt, phân bổ lại và thu hút lại gian lận ít hơn X%.

**Mức tiết kiệm ước tính**

<Image align="center" alt="" src="https://support.appsflyer.com/hc/article_attachments/4403139246993" />

Số liệu về số tiền tiết kiệm ước tính:

* Hiển thị giá trị của gian lận bị chặn theo thời gian thực hoặc được xác định hậu phân bổ, để bạn quyết toán với mạng quảng cáo.
* Sử dụng công thức: Tiết kiệm Ước tính = số lượt cài đặt bị chặn X eCPI trung bình của ứng dụng.
* Không liên quan đối với lưu lượng truy cập tự nhiên.

Để biết thêm chi tiết về cách tính số tiền này, hãy đọc mục <Anchor target="_blank" href="/marketers/vi/docs/protect360-anti-fraud-guide#faq">Câu hỏi thường gặp</Anchor> này.

**Số lượt phân bổ gian lận được xác định**

<Image align="center" alt="" src="https://files.readme.io/262403803bd074e4742f63d7998d4642e3b17781e178ed3bc24b35dd958ca262-4408437121297.png" />

Tổng số liệu về gian lận được xác định hiển thị số:

* Lượt cài đặt, phân bổ lại và thu hút lại gian lận bị chặn theo thời gian thực vì tất cả các lý do chặn gian lận khác nhau.
* Lượt cài đặt, phân bổ lại và thu hút lại được xác định là gian lận hậu phân bổ.

**Các sự kiện trong ứng dụng bị chặn**

<Image align="center" alt="" src="https://files.readme.io/ed6692be83cae6a6bee556e5c763d6313c0d32cb577a9587caac41c54b51b378-4403139249809.png" />

Số liệu sự kiện trong ứng dụng bị chặn hiển thị số sự kiện trong ứng dụng bị AppsFlyer chặn. Các sự kiện này có thể bị chặn do thuộc về các lượt cài đặt bị chặn hoặc do bị đánh dấu là các sự kiện hậu phân bổ đáng ngờ.

</Accordion>

<div id="installs-charts" />

<Accordion title="Lượt cài đặt—b iểu đồ">

<div id="identified-fraud-trend-chart" />

#### Biểu đồ xu hướng gian lận được xác định

Biểu đồ xu hướng gian lận được xác định hiển thị số lượt cài đặt, phân bổ lại và tương tác lại gian lận mỗi ngày, được chia nhỏ theo:

* **Loại phát hiện**: Các lượt cài đặt bị chặn theo thời gian thực và lượt cài đặt được xác định là gian lận hậu phân bổ.
* **Loại phân bổ**: Lượt cài đặt, phân bổ lại và thu hút lại
* **Loại nguồn**: Không tự nhiên và tự nhiên

Hiển thị có thể là biểu đồ đường hoặc biểu đồ thanh.

<div id="hijacked-installs-attribution-correction-chart" />

#### Biểu đồ điều chỉnh phân bổ số lượt cài đặt bị đánh cắp

Biểu đồ điều chỉnh phân bổ số lượt cài đặt bị đánh cắp hiển thị các nguồn truyền thông đã cố gắng lấy điểm tín dụng cho lượt cài đặt, phân bổ lại và thu hút lại, cũng như các nguồn người đóng góp hợp lệ sau cùng.

Bạn có thể:

* Lọc theo lượt phân bổ bị đánh cắp được xác định theo thời gian thực, hậu phân bổ hoặc lượt phân bổ được xác định thông qua quy tắc xác thực.
* Đặt phân bổ nguồn hợp lệ nào được điều chỉnh hoặc phân bổ nguồn bị đánh cắp nào mà từ đó đã được điều chỉnh.
* Thay đổi chế độ xem biểu đồ thành định dạng bảng và tải xuống dữ liệu dưới dạng CSV.

**Lưu ý:**

* Biểu đồ này chỉ được các nhà quảng cáo truy cập. Đại lý và mạng quảng cáo không có quyền truy cập.
* Khi hoạt động đánh cắp bị chặn theo thời gian thực, thì các phân bổ chính xác sẽ hiển thị trong báo cáo và bảng điều khiển AppsFlyer (không chỉ Protect360). Khi hoạt động đánh cắp được xác định hậu phân bổ thì các lượt phân bổ chính xác chỉ được hiển thị trong dữ liệu thô của Protect360.
* Biểu đồ này có thể hiển thị điều chỉnh **đến** nguồn tự nhiên, nhưng không hiển thị điều chỉnh **từ** nguồn tự nhiên.

<div id="affiliate-attribution-model" />

<div id="identified-fraud-chart" />

#### Biểu đồ gian lận được xác định

Biểu đồ gian lận được xác định hiển thị các loại gian lận mà bạn gặp phải theo tỷ lệ phần trăm. Phân tích gian lận có thể theo:

* Lý do chặn
* Lý do phụ bị chặn
* Nguồn truyền thông
* Chiến dịch
* Địa lý
* Ứng dụng

</Accordion>

<div id="installs-table" />

<Accordion title="Lượt cài đặt—bảng">

<div id="identified-fraud-breakdown" />

#### Phân tích gian lận đã xác định

Bảng **Phân tích gian lận đã xác định** hiển thị dữ liệu sau:

* Gian lận bị chặn trong thời gian thực
* Gian lận được xác định và đánh dấu hậu phân bổ
* Các dấu hiệu gian lận khác trên mỗi nguồn truyền thông

Bảng được trình bày ở định dạng tổng quan chung, như được thể hiện trong hình ảnh sau đây.

<Image align="center" alt="p360_main_table.png" src="https://files.readme.io/15885268068f2b57e9b22b7028a824951690e737a47cb154cd38d1ddf79937b8-4408431449745.png" />

Cấu trúc bảng động:

* Cho phép bạn nhấp vào nút cài đặt bảng để thêm vào hoặc xóa các cột khỏi bảng.  
  Nếu bạn thực hiện bất kỳ thay đổi nào đối với bảng, hãy nhớ nhấp vào nút **Save** (Lưu) sau đó.
* Là theo mỗi người dùng, vì vậy mọi người dùng tài khoản có quyền truy cập vào Protect360 đều có thể tự tùy chỉnh cấu trúc bảng của riêng họ. Xem [thêm các tùy chọn bảng](/docs/protect360-dashboard#tùy-chọn-bảng-bổ-sung).

<Image align="center" alt="edit_table.jpg" src="https://files.readme.io/fcde2bc6970c29902dd7585ee92c2bc38edf1d5c56e65de4e3f10df784108e5c-360011641617.jpg" />

<div id="content-of-the-identified-fraud-breakdown-table" />

#### Nội dung của bảng phân tích gian lận đã xác định

| Cột bảng | Mô tả |
| --- | --- |
| Nhóm | <ul><li>[Mặc định] Bảng và bảng điều khiển được nhóm theo Nguồn truyền thông.</li><li>Việc chọn một nguồn truyền thông cụ thể sẽ tự động nhóm theo cả Nguồn truyền thông và ID trang web.</li><li>Các nhóm tùy chọn bao gồm Chiến dịch, Địa lý, Kênh, đại lý và các kết hợp của những nhóm này.</li><li>Nếu bạn chọn nhóm có phương diện chỉ áp dụng cho lưu lượng truy cập không tự nhiên, bảng sẽ hiển thị N/A đối với nguồn truyền thông tự nhiên.</li></ul> |
| **Phân bổ** | **Phân tích tiêu đề của các lượt cài đặt gian lận bị chặn và hậu phân bổ.** |
| Tổng (A) | <ul><li>Tổng lượt cài đặt = Lượt cài đặt thông thường (không gian lận) + lượt cài đặt bị chặn</li><li>Số lượt cài đặt thông thường có sẵn trên mỗi nguồn truyền thông (không tự nhiên) trong bảng điều khiển Tổng quan.</li></ul> |
| Bị chặn (B) | <ul><li>Tổng số lượt cài đặt bị chặn.</li><li>[Mặc định] Bảng được sắp xếp theo thứ tự giảm dần sử dụng KPI này.</li></ul> |
| % bị chặn (B/A) | Lượt cài đặt bị chặn / Tổng lượt cài đặt |
| Hậu phân bổ (C) | Lượt cài đặt được xác định là gian lận hậu phân bổ. |
| % hậu phân bổ (C/A) | Lượt cài đặt hậu phân bổ/tổng số lượt cài đặt |
| Tổng số lượt cài đặt gian lận (D) | Các lượt cài đặt gian lận, bị chặn theo thời gian thực hoặc được xác định là gian lận hậu phân bổ. |
| % lượt cài đặt gian lận (D/A) | Lượt cài đặt gian lận / Tổng số lượt cài đặt |
| **Phân tích loại phân bổ gian lận** | **Các loại phân bổ lượt cài đặt gian lận, chia nhỏ thành lượt cài đặt, phân bổ lại và thu hút lại.** |
| Lượt cài đặt | Gian lận bắt nguồn từ một chiến dịch UA. |
| Phân bổ lại | Gian lận bắt nguồn từ chiến dịch nhắm mục tiêu lại dẫn đến lượt cài đặt. |
| Tương tác lại | Gian lận bắt nguồn từ chiến dịch nhắm mục tiêu lại dẫn đến thu hút lại. |
| **Giả mạo** | **Lượt cài đặt hoặc phân bổ lại gian lận mô phỏng hoạt động của người dùng thực - chia cho các lượt bị chặn và hậu phân bổ theo thời gian thực.** |
| Chặn theo thời gian thực | Lượt cài đặt giả bị chặn theo thời gian thực. |
| Gian lận hậu phân bổ | Lượt cài đặt giả được xác định là gian lận hậu phân bổ. |
| **Đã bị đánh cắp** | **Các lượt nhấp cuối cùng gian lận đánh cắp phân bổ của lượt cài đặt người dùng thực - chia cho các lượt bị chặn và hậu phân bổ theo thời gian thực.** |
| Chặn theo thời gian thực | Lượt cài đặt bị đánh cắp bị chặn theo thời gian thực. |
| Gian lận hậu phân bổ | Lượt cài đặt bị đánh cắp được xác định là gian lận hậu phân bổ. |
| **Quy tắc Xác thực** | **Lượt cài đặt đáp ứng các điều kiện của quy tắc xác thực.** |
| Lượt cài đặt bị chặn | Lượt cài đặt bị chặn bởi các quy tắc xác thực. |
| Phân bổ bị chặn | Thay đổi phân bổ của lượt cài đặt do các quy tắc xác thực. |
| **Phân tích chặn các lượt cài đặt giả** | **Phân tích các lượt cài đặt giả mạo gian lận hậu phân bổ và bị chặn, thường do lập trình** |
| Danh sách từ chối ID trang bị chặn | Các lượt cài đặt bị chặn do Protect360 đưa SiteID vào danh sách từ chối. |
| Danh sách từ chối ID trang hậu phân bổ | Các lượt cài đặt được đánh dấu là gian lận do SiteID nằm trong danh sách từ chối hậu phân bổ của Protect360. |
| Bot bị chặn | Số lần bot tự động tìm cách cài đặt đã bị chặn. |
| Bot hậu phân bổ | Các lượt cài đặt được đánh dấu là gian lận do hoạt động hậu phân bổ bot tự động được xác định |
| Các bất thường về hành vi bị chặn | Các lượt cài đặt bị chặn do các hành vi bất thường, ý nghĩa, phiên bất thường và hiệu suất sự kiện trong ứng dụng của người dùng. |
| Các bất thường về hành vi hậu phân bổ | Các lượt cài đặt được đánh dấu là gian lận do các hành vi bất thường hậu phân bổ. |
| Xác thực lượt cài đặt bị chặn | Tổng số lượt cài đặt bị chặn do xác thực cửa hàng tiêu cực. |
| **Phân tích chặn các lượt cài đặt bị đánh cắp** | **Phân tích các lượt nhấp gian lận cuối cùng nhằm đánh cắp phân bổ lượt cài đặt ứng dụng người dùng thực** |
| Đánh cắp lượt cài đặt bị chặn | Đánh cắp lượt cài đặt bị chặn của nguồn. |
| Đánh cắp lượt cài đặt hậu phân bổ | Đánh cắp lượt cài đặt được đánh dấu là gian lận trong hậu phân bổ. |
| Bất thường về CTIT bị chặn | Các lượt cài đặt bị chặn do bất thường về CTIT. |
| Bất thường về CTIT hậu phân bổ | Bất thường về CTIT được đánh dấu là gian lận trong hậu phân bổ. |
| Nhấp hàng loạtbị chặn | Các lượt cài đặt bị chặn do nhấp hàng loạt (các lần gian lận, tìm cách gửi số lượng lớn các lượt nhấp với hi vọng phân phối lượt nhấp cuối cùng trước cho các lượt cài đặt ngẫu nhiên.) |
| Nhấp hàng loạt hậu phân bổ | Các lượt cài đặt có nhấp hàng loạt được đánh dấu là gian lận trong hậu phân bổ. |
| **Lượt nhấp** | **Số lượt nhấp từ nguồn**<br /><br />**Lưu ý:** Tất cả các loại phân bổ phải được chọn trong thanh bộ lọc để dữ liệu nhấp chuột hiển thị trong bảng (nếu không, sẽ được hiển thị là N/A). Hãy nhớ điều chỉnh các lựa chọn bộ lọc của bạn cho phù hợp. |
| Tổng (E) | Tổng số lượt nhấp hợp pháp và gian lận nhận được từ nguồn |
| Bị chặn | Số lượt nhấp bị chặn do gian lận (bao gồm cả giới hạn lượt nhấp) |
| Giới hạn lượt nhấp | Số lượt nhấp bị chặn do giới hạn lượt nhấp |
| **Lượt hiển thị** | **Số lần hiển thị từ nguồn**<br /><br />**Lưu ý:** Tất cả các loại phân bổ phải được chọn trong thanh bộ lọc để dữ liệu lượt hiển thị hiển thị trong bảng (nếu không, sẽ được hiển thị là N/A). Hãy nhớ điều chỉnh các lựa chọn bộ lọc của bạn cho phù hợp. |
| Tổng | Tổng số lần hiển thị hợp pháp và gian lận nhận được từ nguồn |
| Bị chặn | Số lần hiển thị bị chặn do gian lận (bao gồm cả giới hạn lần hiển thị) |
| Giới hạn lượt nhấp | Số lần hiển thị bị chặn do giới hạn lần hiển thị |
| **Sự kiện trong Ứng dụng** | **Các sự kiện trong ứng dụng từ nguồn**<br /><br />**Lưu ý:** Điều này bao gồm các sự kiện trong ứng dụng từ lượt cài đặt; không phải phân bổ lại hoặc thu hút lại. |
| Tổng (G) | Tổng số sự kiện trong ứng dụng |
| Bị chặn (H) | Các sự kiện trong ứng dụng bị chặn |
| % (H/G) | Các sự kiện trong ứng dụng bị chặn / tổng số sự kiện trong ứng dụng |
| **Dấu hiệu gian lận thiết bị** | **Các dấu hiệu hoạt động kho thiết bị gian lận, sử dụng gian lận Đặt lại ID Thiết bị và Theo dõi Quảng cáo Giới hạn (LAT).**<br /><br />**Lưu ý:** Điều này bao gồm lượt cài đặt và phân bổ lại; không phải thu hút lại. |
| Lượt cài đặt (I) | Các lượt cài đặt có ID thiết bị mới mà AppsFlyer không xác định được. |
| % lượt cài đặt (I/A) | Lượt cài đặt thiết bị mới / Tổng số lượt cài đặt |
| % người dùng trung thành | KPI tổng quan cho biết người dùng là thật hay giả. |
| **Dấu hiệu nhấp hàng loạt** | **Các dấu hiệu gian lận nhấp chuột nhiều lần dựa trên tỷ lệ chuyển đổi hoặc hỗ trợ bất thường, hoặc thời gian CTIT.** |
| Tỷ lệ chuyển đổi (%) | Tỷ lệ phần trăm thấp so với tỷ lệ chuyển đổi chung của ứng dụng cho thấy gian lận nhấp hàng loạt<br /><br />**Lưu ý**: Tất cả các loại phân bổ phải được chọn trong thanh bộ lọc để dữ liệu tỷ lệ chuyển đổi hiển thị trong bảng (nếu không, sẽ được hiển thị là N/A). Hãy nhớ điều chỉnh các lựa chọn bộ lọc của bạn cho phù hợp. |
| % hỗ trợ | Tỷ lệ phần trăm cao so với các nguồn phương tiện khác (trong widget hỗ trợ trong trang tổng quan) cho thấy gian lận nhấp hàng loạt |
| CTIT > Trên 60 phút | Lượt cài đặt, phân bổ lại và thu hút lại trong đó thời gian giữa lần nhấp chuột và lần khởi chạy ứng dụng đầu tiên là hơn 60 phút. Phép tính chỉ bao gồm các lượt cài đặt có CTIT dưới 25 giờ (và không phải tất cả các lượt cài đặt). Thông thường, khoảng 30% các lượt khởi chạy ứng dụng đầu tiên diễn ra hơn 60 phút sau khi tải xuống. |
| CTIT > Trên 5 giờ | Lượt cài đặt, phân bổ lại và thu hút lại trong đó thời gian giữa lần nhấp chuột và lần khởi chạy ứng dụng đầu tiên là hơn 5 giờ. Phép tính chỉ bao gồm các lượt cài đặt có CTIT dưới 25 giờ (và không phải tất cả các lượt cài đặt). Thông thường, khoảng 20% các lượt khởi chạy ứng dụng đầu tiên diễn ra hơn 5 giờ sau khi tải xuống. |

<div id="additional-table-options" />

#### Tùy chọn bảng bổ sung

* Nhấp vào **Export CSV** (Xuất CSV) để tải bảng về máy tính để bàn dưới định dạng CSV
* Nhấp vào biểu tượng bánh răng để:
  * Thay đổi thứ tự các cột trong bảng
  * Thêm hoặc xóa các cột được mô tả ở trên
  * Thêm hoặc xóa bất kỳ **sự kiện trong ứng dụng bị chặn gần đây** của ứng dụng của bạn. Đối với mỗi sự kiện trong ứng dụng được thêm vào, các cột sau sẽ được hiển thị:

| Cột bảng | Mô tả |
| --- | --- |
| Bộ đếm sự kiện (Tổng số) | Số lần bị chặn của một sự kiện cụ thể |
| Người dùng duy nhất | Số lượng người dùng duy nhất có sự kiện cụ thể bị chặn |

Lưu ý rằng tỷ lệ bất thường của một trong số các chỉ số KPI này không nhất thiết thể hiện sự gian lận, bởi vì rất nhiều sự kiện bị chặn do các lượt cài đặt hậu phân bổ gian lận.

Dữ liệu sự kiện trong ứng dụng trên bảng điều khiển CPI dựa trên LTV, nghĩa là tất cả các sự kiện trong ứng dụng liên quan đến lượt cài đặt đã xảy ra trong phạm vi ngày được chỉ định.

</Accordion>

## In-App Events Dashboard

Bảng điều khiển sự kiện trong ứng dụng hiển thị dữ liệu dựa trên hoạt động, nghĩa là dữ liệu liên quan đến các sự kiện trong ứng dụng đã diễn ra trong phạm vi ngày bạn đã chọn, bao gồm các sự kiện từ lượt cài đặt xảy ra trước phạm vi ngày này.

Các tính năng của bảng điều khiển được mô tả trong các phần tiếp theo.

<div id="inapp-events-headline-metrics" />

<Accordion title="Sự kiện trong ứng dụng —s ố liệu dạng tiêu đề">

<Image align="center" alt="" src="https://files.readme.io/ea33b3ddafc4265eb74b2e1070a77a6afbad429a1aeb20cd1579127f7e8ee605-360012501757.jpg" />

Các số liệu dạng tiêu đề cho phép bạn xem:

* Mức tiết kiệm ước tính
  * Chỉ khả dụng nếu [**Các sự kiện phải trả**](/docs/protect360-dashboard#payable-events) được bật.
  * Dựa trên các sự kiện phải trả mà bạn đã cấu hình.
* Tổng số IAE gian lận được xác định

</Accordion>

<div id="inapp-events-charts" />

<Accordion title="Sự kiện trong ứng dụng —b iểu đồ">

<div id="fraud-trend-over-time-chart" />

#### **Xu hướng gian lận thể hiện qua biểu đồ thời gian**

Biểu đồ xu hướng gian lận theo thời gian hiển thị số sự kiện mỗi ngày, được chia thành:

* **Thời gian thực**: Các sự kiện trong ứng dụng gian lận bị chặn theo thời gian thực
* **Hậu phân bổ**: Các sự kiện gian lận được xác định hậu phân bổ
* **Không gian lận**

<div id="top-iae-fraud-by-media-source-chart" />

#### **Gian lận IAE hàng đầu theo biểu đồ nguồn truyền thông**

Gian lận sự kiện trong ứng dụng hàng đầu theo danh sách nguồn truyền thông bao gồm: 

* 5 nguồn truyền thông có số sự kiện trong ứng dụng gian lận cao nhất theo thứ tự giảm dần.
* Biểu đồ dạng cột cho mỗi thanh nguồn truyền thông hiển thị các loại sự kiện trong ứng dụng sau đây dưới dạng phần trăm tổng số sự kiện trong ứng dụng:
  * **Thời gian thực**: Các sự kiện trong ứng dụng gian lận bị chặn theo thời gian thực
  * **Hậu phân bổ**: Các sự kiện gian lận được xác định hậu phân bổ
  * **Không gian lận**

</Accordion>

<div id="inapp-events-table" />

<Accordion title="Sự kiện trong ứng dụng —b ảng">

Bảng **Phân tích gian lận sự kiện trong ứng dụng** hiển thị dữ liệu sau:

* Gian lận bị chặn trong thời gian thực
* Gian lận được xác định và đánh dấu hậu phân bổ
* Các dấu hiệu gian lận khác trên mỗi nguồn truyền thông

Bảng được trình bày ở định dạng tổng quan chung, như được thể hiện trong hình ảnh sau đây.

<Image align="center" alt="IAE_fraud_table.jpg" src="https://files.readme.io/dd57a2508911b3e26268ad8cc4508d5402fa091ac95a77900c7f257486c99aeb-360012839758.jpg" />

Cấu trúc bảng động:

* Cho phép bạn nhấp vào nút cài đặt bảng để thêm vào hoặc xóa các cột khỏi bảng.  
  Nếu bạn thực hiện bất kỳ thay đổi nào đối với bảng, hãy nhớ nhấp vào nút **Save** (Lưu) sau đó.
* Là theo mỗi người dùng, vì vậy mọi người dùng tài khoản có quyền truy cập vào Protect360 đều có thể tự tùy chỉnh cấu trúc bảng của riêng họ. Xem [thêm các tùy chọn bảng](/docs/protect360-dashboard#installs-table).

<Image align="center" alt="iae_table_structure.jpg" src="https://files.readme.io/5b2933e2b254d8fa268e30a72ae53691da391e365d781d55bcdb6cfeb1f40a6a-360012839778.jpg" />

<div id="content-of-the-in-app-event-fraud-breakdown-table" />

#### Nội dung của bảng phân tích gian lận sự kiện trong ứng dụng

| Cột bảng | Mô tả |
| --- | --- |
| Nhóm | <ul><li>[Mặc định] Bảng và bảng điều khiển được nhóm theo Nguồn truyền thông.</li><li>Việc chọn một nguồn truyền thông cụ thể sẽ tự động nhóm theo cả Nguồn truyền thông và ID trang web.</li><li>Các nhóm tùy chọn bao gồm Chiến dịch, Địa lý, Kênh, đại lý và các kết hợp của những nhóm này.</li></ul> |
| **Sự kiện trong Ứng dụng** | **Phân tích tiêu đề các IAE gian lận hậu phân bổ và bị chặn.** |
| Tổng IAE (A) | <ul><li>Tổng IAE = IAE thông thường (không gian lận) + IAE bị chặn + IAE được xác định là gian lận hậu phân bổ.</li><li>Các IAE thông thường có sẵn trên mỗi nguồn truyền thông (không tự nhiên) trong bảng điều khiển Tổng quan.</li></ul> |
| Tổng IAE gian lận (B) | <ul><li>Tổng số IAE bị chặn + IAE được xác định là gian lận hậu phân bổ.</li><li>[Mặc định] Bảng được sắp xếp theo thứ tự giảm dần sử dụng KPI này.</li></ul> |
| % sự kiện gian lận (B/A) | IAE gian lận/Tổng IAE |
| **Lượt chặn IAE giả mạo theo thời gian thực** | **Các IAE gian lận bị chặn theo thời gian thực.** |
| IAE giả mạo | IAE giả mạo được xác định là gian lận và bị chặn theo thời gian thực. |
| Lượt cài đặt giả | Lượt cài đặt ban đầu được xác định là gian lận và bị chặn theo thời gian thực. |
| Lượt cài đặt gian lận hậu phân bổ | Lượt cài đặt ban đầu đã được xác định là gian lận hậu phân bổ, trước IAE. |
| **Được ngăn chặn khỏi bị đánh cắp theo thời gian thực** | **Các IAE có lượt cài đặt ban đầu bị đánh cắp bởi một nguồn gian lận, mà AppsFlyer phân bổ chính xác cho nguồn không gian lận cuối cùng.** |
| Đã sửa thành tự nhiên | Lượt cài đặt bị đánh cắp với nguồn không gian lận cuối cùng là tự nhiên. |
| Đã sửa thành nguồn không tự nhiên | Lượt cài đặt bị đánh cắp với nguồn không gian lận cuối cùng là nguồn truyền thông không tự nhiên. |
| **Gian lận IAE hậu phân bổ** | **Các sự kiện trong ứng dụng được xác định là gian lận hậu phân bổ.** |
| Lượt cài đặt giả | IAE xảy ra trước khi lượt cài đặt được xác định là gian lận hậu phân bổ. |
| Lượt cài đặt bị đánh cắp | IAE xảy ra trước khi lượt cài đặt được xác định là bị đánh cắp và không thể được phân bổ chính xác hậu phân bổ. |
| **Quy tắc Xác thực** | **IAE bị chặn do đáp ứng các điều kiện của quy tắc xác thực.** |
| Lượt cài đặt bị chặn | IAE của các lượt cài đặt bị chặn bởi các quy tắc xác thực. |
| IAE bị chặn | IAE bị chặn bởi các quy tắc xác thực. |
| Đã sửa thành tự nhiên | Lượt cài đặt bị đánh cắp với nguồn không gian lận cuối cùng là tự nhiên. |
| Đã sửa thành nguồn không tự nhiên | Lượt cài đặt bị đánh cắp với nguồn không gian lận cuối cùng là nguồn truyền thông không tự nhiên. |

<div id="additional-table-options-1" />

#### Tùy chọn bảng bổ sung

* Nhấp vào **Export CSV** (Xuất CSV) để tải bảng về máy tính để bàn dưới định dạng CSV
* Nhấp vào biểu tượng bánh răng để:
  * Thay đổi thứ tự các cột trong bảng
  * Thêm hoặc xóa các cột được mô tả ở trên

Số lượng sự kiện hiển thị là dựa trên hoạt động và không dựa trên LTV, tức đó là số lượng chính xác các lượt chặn sự kiện trong một khoảng thời gian cụ thể.

</Accordion>

<div id="payable-events" />

<Accordion title="Các sự kiện phải trả">

Các sự kiện phải trả là các IAE có chi phí. Sau khi được bật và cấu hình, bảng điều khiển Hoạt động trong ứng dụng chỉ hiển thị dữ liệu liên quan đến các sự kiện phải trả.

**Để bật Các sự kiện phải trả trong bảng điều khiển Hoạt động trong ứng dụng**:

* Trong phần **Filter by** (Lọc theo) của bảng điều khiển Hoạt động trong ứng dụng, hãy bật Các sự kiện phải trả.  

  <Image align="center" alt="" src="https://files.readme.io/8162f6f4f6dcef50fbe0fd998b7a95d20deeb658dd53bafc216b75df050c734c-360012576718.jpg" />

**Để cấu hình các sự kiện phải trả**:

1. Trong bảng điều khiển Hoạt động trong ứng dụng, nhấp vào **Configure payable events** (Cấu hình các sự kiện phải trả).  

   <Image align="center" alt="" src="https://files.readme.io/00b1f4506f0c7ec8e1e1b90c16cc2232d2862b231b2673d2decc7a90b6c6b6af-360012505217.jpg" />

   Cửa sổ bật lên Cấu hình các sự kiện phải trả sẽ được hiển thị.

   <Image align="center" alt="" src="https://files.readme.io/4643b9d0e0042ca5860d21ec3eb3ff7e4178f92f1f4215db56adda10be41c452-360012580938.jpg" />
2. [Tùy chọn] Nếu bạn cấu hình một sự kiện phải trả mới, hãy nhấp vào **Add new** (Thêm mới).
3. Tùy bạn muốn hiển thị những IAE phải trả nào trong bảng điều khiển, hãy chọn những mục sau đây từ menu thả xuống:
   * Ứng dụng
   * Sự kiện trong Ứng dụng
   * Nguồn truyền thông
   * Chiến dịch
4. Nhập CPA của IAE.
5. Nhấp vào **Lưu**.
6. Nhấp vào **Close** (Đóng).

</Accordion>

## Bảng điều khiển về bất thường

Bảng điều khiển về Bất thường:

* Cung cấp thông tin chi tiết về các nguồn truyền thông có giá trị Thời gian Nhấp tới Cài đặt (CTIT) hoặc tỷ lệ thiết bị mới đáng ngờ, khi so sánh với các nguồn truyền thông khác.
* Cho phép bạn sử dụng KPI cấp nguồn truyền thông để nhận được tiền thù lao từ các nguồn truyền thông và cân nhắc xem có nên tiếp tục làm việc với họ hay không.
* Bạn cần có lưu lượng truy cập từ các nguồn được AppsFlyer tin cậy để giảm thiểu tỷ lệ gian lận. Điều này nhằm tạo đường cơ sở để so sánh các nguồn truyền thông khác.

<div id="ctit-tab" />

<Accordion title="Tab CTIT">

<Image align="center" alt="Anomalies_CTIT.png" src="https://files.readme.io/630ff7b8c065a302f86b0c1f69c0d166d3ff28a2833ebde3e79494ba8b283f08-360011641657.png" />

**Để xem thông tin về CTIT** (các số tham chiếu đến ảnh chụp màn hình trước):

1. Đi đến **Anomalies** (Bất thường) > **CTIT**.
2. Chọn ứng dụng để xem trong trang.
3. Chọn quốc gia đóng góp dữ liệu trong trang.
4. Chọn khoảng ngày của dữ liệu trên trang.
5. Bạn có thể xem tới 180 ngày trở lại.  
   **Lưu ý**: 180 ngày bắt đầu từ ngày 6 tháng 4, vì vậy cho đến khi 180 ngày trôi qua kể từ đó, chỉ còn dưới 180 ngày.
6. Bật tính năng **Loại trừ gian lận hậu phân bổ** để chỉ xem gian lận bị chặn hoặc tắt tùy chọn này để xem toàn bộ thông tin về gian lận.
7. Chọn đường cơ sở nguồn phương tiện để so sánh. **Đường cơ sở ứng dụng** mặc định cân nhắc các nguồn khác nhau được AppsFlyer tin cậy, có đóng góp vào lưu lượng truy cập của bạn.
8. Chọn đơn vị thời gian được hiển thị trong biểu đồ: giây, phút, giờ hoặc ngày.
9. Tùy chỉnh quy tắc xác thực thành <Anchor target="_blank" href="/marketers/vi/docs/implement-validation-rules-to-prevent-fraud#protect360-install-and-inapp-event-sources">loại trừ lượt cài đặt có CTIT phi logic</Anchor>.  
   **Lưu ý**: tính năng quy tắc xác thực phải được bật cho tài khoản của bạn để thực hiện thao tác này.
10. Để xem thêm thông tin, hãy di chuột phía trên các phần có màu khác biệt trong biểu đồ trong đó thể hiện những bất thường về CTIT.  
    **Lưu ý**: Chỉ những mạng quảng cáo mà chúng tôi có đủ dữ liệu để so sánh chính xác mới được hiển thị.
11. Nhấp vào liên kết **Protect 360** để quay lại trang Gian lận được xác định.

Bảng **phân tích bất thường CTIT**  ở cuối trang hiển thị tất cả các nguồn phương tiện có bất thường về CTIT. Sử dụng bảng này để xem dữ liệu về số lượng và tỷ lệ phần trăm lượt cài đặt có giá trị CTIT bất thường. Với bảng này, bạn cũng có thể xuất ra CSV, thêm hoặc xóa các cột hoặc thiết lập thứ tự các cột.

</Accordion>

<div id="new-devices-tab" />

<Accordion title="Tab thiết bị mới">

<Image align="center" alt="anomalies_new_devices" src="https://files.readme.io/5bb108e61e0641cb16ba16720625dfbdf5446f979e6dddc80c9ec179104f5ec7-360011641677.png" />

Tab **New devices** (Thiết bị mới) cho phép bạn phát hiện trực quan các nguồn truyền thông và ID trang web có <Anchor target="_blank" href="/marketers/vi/docs/protect360-anti-fraud-guide#benchmarks-and-tips">tỷ lệ thiết bị mới cài đặt ứng dụng của bạn cao đáng ngờ</Anchor>.

Các nguồn có màu xám là dưới **Ngưỡng tỷ lệ thiết bị mới**. Đối với các nguồn màu vàng, màu sắc càng đậm thì tỷ lệ thiết bị mới càng cao.

Vùng bị chiếm bởi một nguồn truyền thông đại diện cho tổng số lượt cài đặt của nguồn truyền thông đó, bao gồm cả gian lận bị chặn và hậu phân bổ.

**Để xem thông tin về thiết bị mới** (các số tham chiếu ảnh chụp màn hình trước):

1. Đi đến **Anomalies** (Bất thường) > **New devices** (Thiết bị mới).
2. Chọn ứng dụng để xem trong trang.
3. Chọn quốc gia đóng góp dữ liệu trong trang.
4. Chọn khoảng ngày của dữ liệu trên trang.
5. Đặt **Ngưỡng tỷ lệ thiết bị mới**, trên ngưỡng mà bạn xem các nguồn truyền thông là nghi ngờ và đánh dấu màu vàng.
6. Để xem thêm chi tiết về một nguồn truyền thông, hãy nhấp vào nguồn truyền thông đó.  
   Nhấp vào liên kết **Tất cả các nguồn truyền thông** để quay lại chế độ xem tất cả các nguồn truyền thông.
7. Nhấp vào liên kết **Installs** (Lượt cài đặt) để quay lại tab **Installs** (Lượt cài đặt).
8. Bạn có thể xuất [bảng](/docs/protect360-dashboard#installs-table) **Phân tích gian lận đã xác định**, chứa dữ liệu thiết bị mới.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Lưu ý |
| --- | --- |
| Nhắm mục tiêu lại | <ul><li>Bảng điều khiển lượt cài đặt (CPI) có thể hiển thị phân tích loại cảm ứng được phân bổ giữa các lượt cài đặt, phân bổ lại và tương tác lại.</li><li>Bảng điều khiển sự kiện trong ứng dụng (CPA) hiển thị các sự kiện gian lận từ lượt cài đặt UA nhưng không phải từ việc nhắm mục tiêu lại. **Lưu ý**: Bạn có thể xem các sự kiện gian lận từ việc phân bổ lại theo thời gian thực trong báo cáo dữ liệu thô.</li></ul> |
| Dữ liệu lịch sử | Dữ liệu có sẵn từ khi bắt đầu đăng ký Protect360 |

</Accordion>

<div id="see-also" />

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/protect360-anti-fraud-guide">Tổng quan về Protect360</Anchor>
> * <Anchor target="_blank" href="/marketers/vi/docs/protect360-raw-data-reports">Báo cáo dữ liệu thô</Anchor>

<div data-zendesk-anchors="about-protect360-dashboard=gi%E1%BB%9Bi-thi%E1%BB%87u-v%E1%BB%81-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-protect360 01H8H9GQ17C4PBHCAMXE879BX7=gi%E1%BB%9Bi-thi%E1%BB%87u-v%E1%BB%81-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-protect360 01H8H9GQ173SQ8P29C4DETJRTD=filters-and-groupings installs-dashboard=b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t 01H8H9GQ173H3QH1Y5KZ26XMCW=b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t installs%E2%80%94headline-metrics=installs-headline-metrics 01H8H9GQ17FJKWE3M2YSZFTQCS=installs-headline-metrics installs%E2%80%94charts=installs-charts 01H8H9GQ18VHMK7FFV3RY409VB=installs-charts identified-fraud-trend-chart=bi%E1%BB%83u-%C4%91%E1%BB%93-xu-h%C6%B0%E1%BB%9Bng-gian-l%E1%BA%ADn-%C4%91%C6%B0%E1%BB%A3c-x%C3%A1c-%C4%91%E1%BB%8Bnh 01H8H9GQ18JDSZ2H8BKZVWGBPV=bi%E1%BB%83u-%C4%91%E1%BB%93-xu-h%C6%B0%E1%BB%9Bng-gian-l%E1%BA%ADn-%C4%91%C6%B0%E1%BB%A3c-x%C3%A1c-%C4%91%E1%BB%8Bnh hijacked-installs-attribution-correction-chart=bi%E1%BB%83u-%C4%91%E1%BB%93-%C4%91i%E1%BB%81u-ch%E1%BB%89nh-ph%C3%A2n-b%E1%BB%95-s%E1%BB%91-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-b%E1%BB%8B-%C4%91%C3%A1nh-c%E1%BA%AFp 01H8H9GQ18VXBPQRN55WHM3GG0=bi%E1%BB%83u-%C4%91%E1%BB%93-%C4%91i%E1%BB%81u-ch%E1%BB%89nh-ph%C3%A2n-b%E1%BB%95-s%E1%BB%91-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-b%E1%BB%8B-%C4%91%C3%A1nh-c%E1%BA%AFp identified-fraud-chart=bi%E1%BB%83u-%C4%91%E1%BB%93-gian-l%E1%BA%ADn-%C4%91%C6%B0%E1%BB%A3c-x%C3%A1c-%C4%91%E1%BB%8Bnh 01H8H9GQ18FW87TXQZCYERHNDE=bi%E1%BB%83u-%C4%91%E1%BB%93-gian-l%E1%BA%ADn-%C4%91%C6%B0%E1%BB%A3c-x%C3%A1c-%C4%91%E1%BB%8Bnh installs%E2%80%94table=installs-table 01H8H9GQ18FYXJA7TXQ4RNQGX2=installs-table identified-fraud-breakdown=ph%C3%A2n-t%C3%ADch-gian-l%E1%BA%ADn-%C4%91%C3%A3-x%C3%A1c-%C4%91%E1%BB%8Bnh 01H8H9GQ18540JJ8X833E6WF44=ph%C3%A2n-t%C3%ADch-gian-l%E1%BA%ADn-%C4%91%C3%A3-x%C3%A1c-%C4%91%E1%BB%8Bnh content-of-the-identified-fraud-breakdown-table=n%E1%BB%99i-dung-c%E1%BB%A7a-b%E1%BA%A3ng-ph%C3%A2n-t%C3%ADch-gian-l%E1%BA%ADn-%C4%91%C3%A3-x%C3%A1c-%C4%91%E1%BB%8Bnh 01H8H9GQ18DMPD7YTPTN2XJMSH=n%E1%BB%99i-dung-c%E1%BB%A7a-b%E1%BA%A3ng-ph%C3%A2n-t%C3%ADch-gian-l%E1%BA%ADn-%C4%91%C3%A3-x%C3%A1c-%C4%91%E1%BB%8Bnh additional-table-options=t%C3%B9y-ch%E1%BB%8Dn-b%E1%BA%A3ng-b%E1%BB%95-sung 01H8H9GQ18PZ8ABG3D51M7J91R=t%C3%B9y-ch%E1%BB%8Dn-b%E1%BA%A3ng-b%E1%BB%95-sung inapp-events-dashboard=in-app-events-dashboard 01H8H9GQ19CQZV00XA62MGVJ86=in-app-events-dashboard inapp-events%E2%80%94headline-metrics=inapp-events-headline-metrics 01H8H9GQ19B95MDK2WEHVNEFS5=inapp-events-headline-metrics inapp-events%E2%80%94charts=inapp-events-charts 01H8H9GQ19XEJ0HNY2Y8BMX7A5=inapp-events-charts fraud-trend-over-time-chart=xu-h%C6%B0%E1%BB%9Bng-gian-l%E1%BA%ADn-th%E1%BB%83-hi%E1%BB%87n-qua-bi%E1%BB%83u-%C4%91%E1%BB%93-th%E1%BB%9Di-gian 01H8H9GQ1969AB4KK4ENP8AVQJ=xu-h%C6%B0%E1%BB%9Bng-gian-l%E1%BA%ADn-th%E1%BB%83-hi%E1%BB%87n-qua-bi%E1%BB%83u-%C4%91%E1%BB%93-th%E1%BB%9Di-gian top-iae-fraud-by-media-source-chart=gian-l%E1%BA%ADn-iae-h%C3%A0ng-%C4%91%E1%BA%A7u-theo-bi%E1%BB%83u-%C4%91%E1%BB%93-ngu%E1%BB%93n-truy%E1%BB%81n-th%C3%B4ng 01H8H9GQ19Z078PK1HR7VEZHXG=gian-l%E1%BA%ADn-iae-h%C3%A0ng-%C4%91%E1%BA%A7u-theo-bi%E1%BB%83u-%C4%91%E1%BB%93-ngu%E1%BB%93n-truy%E1%BB%81n-th%C3%B4ng inapp-events%E2%80%94table=inapp-events-table 01H8H9GQ19PTNWGJV6YDWR7SH6=inapp-events-table content-of-the-inapp-event-fraud-breakdown-table=n%E1%BB%99i-dung-c%E1%BB%A7a-b%E1%BA%A3ng-ph%C3%A2n-t%C3%ADch-gian-l%E1%BA%ADn-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng 01H8H9GQ19773CS8TGS2QXBRG5=n%E1%BB%99i-dung-c%E1%BB%A7a-b%E1%BA%A3ng-ph%C3%A2n-t%C3%ADch-gian-l%E1%BA%ADn-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng additional-table-options::44e54bfa=t%C3%B9y-ch%E1%BB%8Dn-b%E1%BA%A3ng-b%E1%BB%95-sung-1 01H8H9GQ192WA6XFNW7CKGBQ03=t%C3%B9y-ch%E1%BB%8Dn-b%E1%BA%A3ng-b%E1%BB%95-sung-1 01H8H9GQ1AVAVQ31ZZA1K024RF=payable-events anomalies-dashboard=b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-v%E1%BB%81-b%E1%BA%A5t-th%C6%B0%E1%BB%9Dng 01H8H9GQ1AGXHE6FNNAHZTMZG6=b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-v%E1%BB%81-b%E1%BA%A5t-th%C6%B0%E1%BB%9Dng 01H8H9GQ1AW1MZJAQE71H384N7=ctit-tab 01H8H9GQ1A0MNJTGAB1V9X4RNF=new-devices-tab 01H8H9GQ1BJX0K01NX8VCC0690=traits-and-limitations h_01HE7S2JKX3VMRCF6913S4MCAR=xem-th%C3%AAm" />
