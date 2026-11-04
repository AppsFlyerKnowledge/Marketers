---
title: Hướng dẫn phân bổ doanh thu quảng cáo
metadata:
  keywords:
    - ad revenue
    - ad monetization
    - monetization
    - Advertisers
    - adrevenue
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2016-12-12T10:53:27Z'
  edited_at: '2023-11-16T10:30:54Z'
  id: 217490046
  locale: vi
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/vi/articles/217490046
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Khái quát:** Phân bổ doanh thu quảng cáo để hoàn thành chế độ xem hiệu suất LTV.

[![Attributes_ad_revenue.png](https://files.readme.io/e512531f0363fcda600fbad8ca8e5081d882b5721fb35fc9c449f8774859a5da-small-15734558614033.png)](https://files.readme.io/e512531f0363fcda600fbad8ca8e5081d882b5721fb35fc9c449f8774859a5da-small-15734558614033.png)

<div id="ad-revenue-attribution" />

## Phân bổ doanh thu quảng cáo

* Quảng cáo hiển thị trong ứng dụng trên biểu ngữ, mục làm nhiệm vụ nhận ưu đãi, quảng cáo xen kẽ, v.v. và tạo doanh thu quảng cáo.
* Doanh thu quảng cáo, kết hợp với các giao dịch mua trong ứng dụng và doanh thu từ gói đăng ký cung cấp cho bạn bức tranh LTV hoàn chỉnh của người dùng. Bằng cách so khớp LTV của người dùng với chiến dịch chi tiêu truyền thông, ROI được xác định và cung cấp để phân tích thêm trong nền tảng.

**Dữ liệu doanh thu quảng cáo được phân bổ**:

* Có được từ mạng mediation và/hoặc mạng ad monetization thông qua API máy chủ hoặc bằng SDK báo cáo được nhúng trong ứng dụng (gồm cả iOS 14).
* Được phân bổ cho nguồn truyền thông ban đầu mang đến người dùng. Ví dụ:
  * Người dùng thấy được quảng cáo từ Mạng A và tải xuống ứng dụng của bạn.
  * Quảng cáo sẽ hiển thị bên trong ứng dụng.
  * Doanh thu quảng cáo được phân bổ cho Mạng A (chịu trách nhiệm thu hút người dùng), bất kể ai đã xuất bản quảng cáo.
* Mức độ chi tiết của báo cáo phụ thuộc vào việc tích hợp mạng kiếm tiền và loại phân bổ doanh thu quảng cáo.

<div id="integration-types-for-ad-revenue-attribution" />

<Accordion title="Các loại tích hợp để phân bổ doanh thu quảng cáo">

Phân bổ doanh thu quảng cáo hỗ trợ các phương thức về mức độ chi tiết khác nhau. Mức độ chi tiết phụ thuộc vào mạng kiếm tiền.

| Loại tích hợp phân bổ doanh thu quảng cáo | Mô tả |
| --- | --- |
| [Cấp hợp nhất](/docs/roi360-guide-ad-revenue-attribution#aggregate-granularity-using-app-open-or-inapp-events) thông qua API S2S | <ul><li>AppsFlyer nhận doanh thu hàng ngày được chia nhỏ theo vùng địa lý.</li><li>Doanh thu hiệu quả trên mỗi hành động (eRPA) được tính bằng cách chia doanh thu cho số trường hợp sự kiện kích hoạt.</li><li>Sự kiện kích hoạt là các sự kiện mở ứng dụng hoặc sự kiện trong ứng dụng cụ thể được đặt trong ứng dụng.</li><li>Nếu bạn đang sử dụng mạng trung gian, hãy nhớ tắt các tích hợp doanh thu quảng cáo cho các đối tác kiếm tiền có trung gian qua mạng trung gian trước khi bật tích hợp doanh thu quảng cáo với mạng trung gian đó. Nếu không làm như vậy thì sẽ dẫn đến dữ liệu trùng lặp.</li></ul> |
| [Cấp thiết bị](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data) thông qua API S2S | <ul><li>Mạng trung gian hay mạng kiếm tiền đều báo cáo doanh thu của người dùng ở cấp thiết bị. Không phải tất cả các mạng đều hỗ trợ mức độ chi tiết cấp thiết bị.</li><li>Doanh thu này là do nguồn truyền thông mang đến người dùng. Có nghĩa là tính năng phân bổ doanh thu quảng cáo của AppsFlyer tuân thủ các quy tắc phân bổ có trên nền tảng, bao gồm cả các quy tắc phân bổ nhắm mục tiêu lại.</li><li>Nếu bạn đang sử dụng mạng trung gian, hãy nhớ tắt các tích hợp doanh thu quảng cáo cho các đối tác kiếm tiền có trung gian qua mạng trung gian trước khi bật tích hợp doanh thu quảng cáo với mạng trung gian đó. Nếu không làm như vậy thì sẽ dẫn đến dữ liệu trùng lặp.</li><li>Cấp thiết bị thông qua API S2S bao gồm toàn bộ doanh thu quảng cáo và có độ chuẩn xác dữ liệu cao nhất trong số các loại tích hợp doanh thu quảng cáo.</li><li>Dữ liệu có sẵn trong <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">các báo cáo dữ liệu thô</Anchor>. Chúng tôi không gửi đăng lại dữ liệu cấp thiết bị cho các đối tác tích hợp.</li></ul> |
| Cấp lượt hiển thị qua SDK | <ul><li>Cấp lượt hiển thị đề cập đến cách AppsFlyer nhận dữ liệu. Dữ liệu có thể được báo cáo ở các cấp độ chi tiết khác (chẳng hạn như cấp thiết bị).</li><li>Mạng trung gian hay mạng kiếm tiền sẽ báo cáo doanh thu của người dùng ở cấp lượt hiển thị. Không phải tất cả các mạng đều hỗ trợ mức độ chi tiết ở cấp lượt hiển thị.</li><li>Doanh thu này là do nguồn truyền thông mang đến người dùng. Có nghĩa là tính năng phân bổ doanh thu quảng cáo của AppsFlyer tuân thủ các quy tắc phân bổ có trên nền tảng, bao gồm cả các quy tắc phân bổ nhắm mục tiêu lại.</li><li>Nếu bạn đang sử dụng mạng trung gian, hãy nhớ tắt các tích hợp doanh thu quảng cáo cho các đối tác kiếm tiền có trung gian qua mạng trung gian trước khi bật tích hợp doanh thu quảng cáo với mạng trung gian đó. Nếu không làm như vậy thì sẽ dẫn đến dữ liệu trùng lặp.</li><li>Cấp lượt hiển thị qua SDK có tính cập nhật của dữ liệu tốt nhất trong tất cả các loại tích hợp doanh thu quảng cáo.</li><li>Hỗ trợ SKAN.</li></ul> |
| Cấp lượt hiển thị (qua SDK) với cấp thiết bị (qua API S2S) | <ul><li>Cho phép phân bổ và báo cáo dữ liệu cấp lượt hiển thị đến qua SDK vào Ngày X, đồng thời chuyển đổi dữ liệu này với dữ liệu cấp thiết bị đến qua API vào Ngày 1 trở đi. **Lưu ý**: Đối với Android, dữ liệu được báo cáo qua SDK từ các thiết bị không xác định (không có ID thiết bị) sẽ không được thay thế bằng dữ liệu đến từ API.</li><li>Cho phép cập nhật dữ liệu với độ chuẩn xác. Có nghĩa là, bạn nhận được lợi ích từ việc cập nhật dữ liệu cho Ngày X với độ chuẩn xác dữ liệu cho Ngày X+1 trở đi.</li><li>Hỗ trợ SKAN.</li></ul> |

</Accordion>

<div id="implementation" />

## Thực hiện

Các phần sau đây mô tả các loại phân bổ doanh thu quảng cáo có sẵn, cũng như quy trình và các bước cần thiết để triển khai và duy trì.

<div id="connect-to-ad-revenue-integrated-partners" />

<Accordion title="Kết nối với các đối tác tích hợp của doanh thu quảng cáo">

**Trước khi bạn bắt đầu**:

* Yêu cầu đối tác tích hợp doanh thu quảng cáo cung cấp cho bạn thông tin đăng nhập API.

**Để bật tích hợp doanh thu quảng cáo với mạng doanh thu quảng cáo**:

1. Trong AppsFlyer, đi đến **ROI360** > **Revenue Settings** > **Ad revenue**.
2. Trong tích hợp Doanh thu quảng cáo, hãy nhấp vào **New ad revenue integration**.
3. Chọn một đối tác doanh thu quảng cáo và nhấp vào **Next**.  
   ![ad_revenue_ui.png](https://files.readme.io/d91b886ed5b9715a508a481afbb86a7dd8381894322455214674ba68b483e91b-13751596101649.png)
4. Chọn loại dữ liệu doanh thu quảng cáo bạn muốn nhận. **Lưu ý**: Không phải tất cả các mạng quảng cáo đều cung cấp tất cả các tùy chọn trong danh sách bên dưới.
   * Doanh thu được phân bổ. Có nghĩa là doanh thu dựa trên nguồn thu hút người dùng. Báo cáo doanh thu được phân bổ có thể là:
     * [Cấp hợp nhất](/docs/roi360-guide-ad-revenue-attribution#aggregate-granularity-using-app-open-or-inapp-events) thông qua API S2S. 
       * Chọn sự kiện để làm cơ sở cho doanh thu quảng cáo. Ví dụ: nếu bạn chọn sự kiện af\_app\_opened, thì tổng doanh thu quảng cáo được chia cho tất cả các sự kiện mở ứng dụng, mang lại cho bạn doanh thu quảng cáo trên mỗi lần mở ứng dụng.
     * Cấp thiết bị thông qua API S2S.
       * **Lưu ý**: Nếu đang bật API doanh thu quảng cáo cấp thiết bị của một mạng trung gian, bạn phải tắt tích hợp doanh thu quảng cáo của các mạng kiếm tiền mà API đó làm trung gian. Nếu không làm như vậy thì sẽ dẫn đến dữ liệu trùng lặp.
     * Cấp lượt hiển thị qua SDK.
     * Yêu cầu nhà phát triển ứng dụng của bạn tích hợp công cụ kết nối doanh thu quảng cáo SDK của AppsFlyer. Các tùy chọn có sẵn cho <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-2">iOS</Anchor> và <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad_revenue_unity_connector">Unity</Anchor>.* Cấp lượt hiển thị qua SDK với cấp hợp nhất qua API S2S.
     * Yêu cầu nhà phát triển ứng dụng của bạn tích hợp công cụ kết nối doanh thu quảng cáo SDK của AppsFlyer. Các tùy chọn có sẵn cho <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-2">iOS</Anchor> và <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad_revenue_unity_connector">Unity</Anchor>.* Cấp lượt hiển thị (qua SDK) ở cấp thiết bị (qua API S2S).
     * Yêu cầu nhà phát triển ứng dụng của bạn tích hợp công cụ kết nối doanh thu quảng cáo SDK của AppsFlyer. Các tùy chọn có sẵn cho <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-2">iOS</Anchor> và <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad_revenue_unity_connector">Unity</Anchor>.* **Lưu ý**: Nếu bạn đang sử dụng mạng trung gian, hãy nhớ tắt tích hợp doanh thu quảng cáo đối với các đối tác kiếm tiền có trung gian qua mạng trung gian trước khi bật tích hợp doanh thu quảng cáo với mạng trung gian. Nếu không làm như vậy thì sẽ dẫn đến dữ liệu trùng lặp.
5. Nhập thông tin đăng nhập hoặc đăng nhập API theo yêu cầu của đối tác tích hợp. Thao tác này không liên quan đến tích hợp SDK.
6. Nhấp vào **Save**.
7. Nếu nút Test Connection (Kiểm tra Kết nối) hiển thị như trong hình trên, hãy nhấp vào **Test Connection** **(Kiểm tra Kết nối).**
   * Nếu API key verified được hiển thị, nghĩa là bạn đã thành công hoàn tất quy trình.
   * Nếu có thông báo khác xuất hiện, hãy xem [trạng thái và thử nghiệm API doanh thu quảng cáo](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-api-status-and-testing) và lặp lại quy trình.
8. Nếu không thấy nút Test Connection tức là bạn đã hoàn tất quy trình.   
   AppsFlyer thu thập dữ liệu của đối tác nhiều lần mỗi ngày<Anchor target="_blank" href="/marketers/vi/docs/about-data-freshness-and-timezone-support#ad-revenue">.</Anchor>
9. [Tùy chọn]QA và so sánh dữ liệu doanh thu quảng cáo trong AppsFlyer với dữ liệu doanh thu quảng cáo trong trang tổng quan đối tác trung gian và đối tác UA của bạn. <Anchor target="_blank" href="/marketers/vi/docs/compare-roi360-ad-revenue-data-with-partner-data">Tìm hiểu thêm</Anchor>
10. [Tùy chọn] Chia sẻ dữ liệu doanh thu quảng cáo với đối tác của bạn thông qua <Anchor target="_blank" href="/marketers/vi/docs/compare-roi360-ad-revenue-data-with-partner-data">tín hiệu UA</Anchor> và [đăng lại sự kiện doanh thu quảng cáo](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks).

**Lưu ý**: Nếu bạn đổi từ loại tích hợp này sang loại tích hợp khác, thì sự thay đổi đó sẽ có hiệu lực vào lúc 12 giờ trưa theo giờ UTC của ngày hôm sau.

</Accordion>

<div id="view-edit-and-delete-ad-revenue-integrated-partners" />

<Accordion title="Xem, chỉnh sửa và xóa đối tác tích hợp doanh thu quảng cáo">

![delete_edit_adi.png](https://support.appsflyer.com/hc/article_attachments/13751607197713)

**Cách xem, chỉnh sửa hoặc xóa tích hợp mạng doanh thu quảng cáo**:

1. Trong AppsFlyer, đi tới **ROI360** > **Revenue Settings** > **Ad revenue** và chọn ứng dụng của bạn.  
   Danh sách tất cả các tích hợp đối tác của bạn sẽ được hiển thị cùng với thông tin về sản phẩm và loại tích hợp, trạng thái tích hợp và tên sự kiện doanh thu quảng cáo.
2. Di chuột đến tích hợp và nhấp vào **Edit** hoặc **Delete** nếu cần.

</Accordion>

<div id="deduplicate-cross-referenced" />

<Accordion title="Loại bỏ trùng lặp doanh thu quảng cáo được tham chiếu chéo">

Có thể xảy ra tình trạng trùng lặp một phần dữ liệu doanh thu quảng cáo khi một ứng dụng sử dụng hai <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-knowledge-base-glossary#nền-tảng-trung-gian">nền tảng trung gian</Anchor>, cả hai đều được liên kết với cùng một <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-knowledge-base-glossary#mạng-kiếm-tiền">mạng kiếm tiền</Anchor>. Trong những trường hợp như vậy, mỗi nền tảng trung gian sẽ báo cáo tất cả doanh thu quảng cáo do mạng kiếm tiền được liên kết của họ tạo ra, bất kể doanh thu đó có được tạo ra trong khi chỉ có một trong các mạng làm trung gian hay không.

**Để tránh trùng lặp một phần dữ liệu doanh thu khi hai nền tảng trung giang tham chiếu chéo lẫn nhau**:

1. Trong AppsFlyer, đi đến **ROI360** > **Revenue Settings** > **Ad Revenue**.
2. Trong **General Settings**, nhấp vào **Deduplicate ad revenue when two mediation partners cross-reference each other**. **Lưu ý**: Không hủy trùng lặp nếu 2 nền tảng trung gian điều giải các định dạng quảng cáo khác nhau. Ví dụ, khi nền tảng 1 hiển thị Biểu ngữ và Xen kẽ, và nền tảng 2 hiển thị các quảng cáo AppOpen và Native.

[![dedup.png](https://support.appsflyer.com/hc/article_attachments/17299804281361)](https://support.appsflyer.com/hc/article_attachments/17299804281361)

</Accordion>

<div id="aggregate-granularity-using-app-open-or-inapp-events" />

<Accordion title="Dữ liệu tổng quát sử dụng các sự kiện mở ứng dụng hoặc sự kiện trong ứng dụng">

Mức độ chi tiết hợp nhất cho doanh thu quảng cáo hoạt động như sau:

* Mạng tích hợp báo cáo tổng doanh thu mỗi ngày được chia nhỏ theo khu vực địa lý.
* AppsFlyer lấy doanh thu hiệu quả trên mỗi hành động (eRPA) bằng cách chia doanh thu quảng cáo với số trường hợp sự kiện kích hoạt.
* AppsFlyer tạo một sự kiện \_monetized, bao gồm tổng eRPA cho từng thiết bị được phân bổ. Ví dụ như ad\_matched\_monetized.
* Sử dụng eRPA, doanh thu được phân bổ cho các nguồn truyền thông.
* Bạn có thể sử dụng một trong các loại sự kiện sau:
  * **Sự kiện kiếm tiền duy nhất trong ứng dụng** yêu cầu sửa đổi ứng dụng.
  * Sự kiện **af\_app\_opened** có sẵn theo mặc định.
* Không báo cáo số tiền doanh thu quảng cáo trong các sự kiện trong ứng dụng song song với tích hợp doanh thu quảng cáo. Nếu làm vậy, doanh thu quảng cáo sẽ bị trùng lặp trong bảng điều khiển vì AppsFlyer lấy dữ liệu doanh thu từ mạng kiếm tiền bằng cách tích hợp.

<div id="aggregate-ad-revenue-using-events" />

#### Hợp nhất doanh thu quảng cáo sử dụng các sự kiện

| Phương thức sự kiện | Cách triển khai | Những điều cần lưu ý |
| --- | --- | --- |
| Sự kiện kiếm tiền duy nhất trong ứng dụng | <ul><li>Sự kiện trong ứng dụng được đặt tại thời điểm hiển thị quảng cáo</li><li>Điều này sẽ cung cấp số lượng các hành động riêng biệt của người dùng cho phép tính toán eRPA tốt hơn</li><li>Có thể tinh chỉnh thêm tính năng này bằng cách có một sự kiện trong ứng dụng khác nhau cho mỗi mạng kiếm tiền, làm như vậy sẽ cho phép bạn chia nhỏ doanh thu theo mạng kiếm tiền<br />Xem bảng sau để có nội dung thảo luận đầy đủ.</li></ul> | <ul><li>Yêu cầu nhà phát triển phải sửa đổi ứng dụng</li><li>Doanh thu có thể được chia nhỏ theo mạng kiếm tiền trong Bảng điều khiển</li></ul> |
| sự kiện af\_app\_opened | <ul><li>Sự kiện af\_app\_opened được SDK Appsflyer gửi theo mặc định</li><li>Tính năng được kích hoạt bởi mỗi phiên người dùng</li></ul> | <ul><li>Không cần sửa đổi ứng dụng</li><li>Triển khai nhanh chóng</li><li>Giá trị eRPA sẽ bị sai lệch đáng kể trừ khi bạn chỉ hiển thị một ứng dụng mỗi phiên</li><li>Không có phân tích doanh thu theo mạng kiếm tiền</li><li>Sự kiện liên quan đến tất cả người dùng khởi chạy ứng dụng và sẽ không có chỉ dấu nào cho bạn biết rằng người dùng sẵn sàng xem quảng cáo</li></ul> |

<div id="comparison-of-in-app-event-methods" />

#### So sánh các phương thức sự kiện trong ứng dụng

| Phương thức | Ưu điểm | Nhược điểm | Những điều cần lưu ý |
| --- | --- | --- | --- |
| Sử dụng cùng một sự kiện cho tất cả các mạng. Ví dụ: ad\_watched. Hoạt động này sẽ tự động tạo sự kiện ad\_watched\_monetized chứa thông tin chi tiết về kiếm tiền | Triển khai đơn giản nhất | Không có thông tin về chất lượng, chẳng hạn như số lượt nhấp và doanh thu quảng cáo trên mỗi mạng | <ul><li>Phù hợp nhất nếu mục tiêu chính là tìm nguồn/chiến dịch thu hút người dùng có xu hướng nhấp vào quảng cáo nhiều nhất.</li><li>Không phù hợp cho việc so sánh hiệu suất của các mạng kiếm tiền.</li></ul> |
| **(Phương pháp hay nhất)** Mỗi mạng được phân bổ một sự kiện duy nhất cho việc xem quảng cáo. Ví dụ: ad\_watch\_admob,<br /><br /> ad\_watch\_vungle. | Khả năng hiển thị và so sánh đầy đủ các mạng kiếm tiền trong bảng điều khiển ngoài dữ liệu thô. | Doanh thu quảng cáo không được tích lũy trong một sự kiện. Số lượng sự kiện tương đương với số lượng mạng | Cho phép so sánh các mạng kiếm tiền trong bảng điều khiển. Doanh thu quảng cáo được phân tách theo mạng bằng sự kiện trong ứng dụng trên mỗi mạng. |

</Accordion>

<div id="ad-revenue-api-status-and-testing" />

<Accordion title="Trạng thái và thử nghiệm API doanh thu quảng cáo">

* Trạng thái hoạt động của tích hợp doanh thu quảng cáo có sẵn như sau:

  * <Anchor target="_blank" href="/marketers/vi/docs/dashboard-cost-and-ad-revenue-status">Bảng điều khiển trạng thái tích hợp chi phí và doanh thu quảng cáo</Anchor>: Danh sách tập trung các đối tác được bật tích hợp doanh thu quảng cáo cho một hoặc nhiều ứng dụng có trong tài khoản của bạn.
  * Một số đối tác cho phép bạn thử nghiệm kết nối API. Nếu có sẵn, nút **Test connection** (Thử nghiệm kết nối) sẽ hiển thị. <Image alt="mceclip0.png" src="https://support.appsflyer.com/hc/article_attachments/360006975517" width="104px" />
  * Để xác minh rằng kết nối API đang hoạt động:
  * Nhấp vào **Test connection (Thử nghiệm kết nối).** Thông báo **Đã xác minh mã khóa API sẽ hiển thị.** Nếu không, hãy làm theo hướng dẫn hành động khắc phục trong bảng sau.

| Trạng thái | Ý nghĩa | Nhận xét/hành động cần thiết |
| --- | --- | --- |
| Đã xác minh mã khóa API | <ul><li>Kết nối đang hoạt động và có thể lấy dữ liệu.</li><li><Anchor target="_blank" href="/marketers/vi/docs/about-data-freshness-and-timezone-support#ad-revenue">Dữ liệu được lấy mỗi ngày một lần.</Anchor></li></ul> | Không có |
| Thông tin đăng nhập không hợp lệ | Một hoặc nhiều thông tin đăng nhập được cung cấp không chính xác. | Nhận thông tin đăng nhập chính xác từ đối tác doanh thu quảng cáo |
| Thiếu thông tin chi tiết về cấu hình | Một hoặc nhiều trường thông tin đăng nhập chưa hoàn thành | Truy xuất thông tin đăng nhập trong bảng điều khiển của đối tác doanh thu quảng cáo hoặc liên hệ với đối tác và yêu cầu thông tin đăng nhập. |

</Accordion>

<div id="ad-revenue-data" />

## Dữ liệu doanh thu quảng cáo

Dữ liệu doanh thu quảng cáo có sẵn qua bảng điều khiển AppsFlyer và báo cáo dữ liệu thô.

<div id="ad-revenue-aggregate-data" />

<Accordion title="Dữ liệu hợp nhất của doanh thu quảng cáo">

Doanh thu quảng cáo cho thấy chất lượng của người dùng từ các nguồn khác nhau theo thời gian. Khi người dùng tiếp tục khởi chạy ứng dụng và tương tác với quảng cáo, LTV của họ sẽ tăng lên.

**Lưu ý**: Có thể có sự khác biệt giữa dữ liệu doanh thu quảng cáo trong các bảng điều khiển và báo cáo khác nhau. [Tìm hiểu thêm](#is-there-discrepency).

Phân bổ doanh thu quảng cáo có sẵn như sau:

* Dựa trên LTV:
  * Bảng điều khiển: Tổng quan, sự kiện
  * Báo cáo LTV
  * Bảng điều khiển và báo cáo theo nhóm người
  * API chính
* Dựa trên hoạt động:
  * Bảng điều khiển: Hoạt động
  * Dữ liệu thô về doanh thu quảng cáo

<div id="overview-dashboard---aggregated-performance-report" />

#### **Bảng điều khiển tổng quan - báo cáo hiệu suất hợp nhất**

[![](https://support.appsflyer.com/hc/article_attachments/360002239229)](https://support.appsflyer.com/hc/article_attachments/360002239229)

Trong Bảng điều khiển tổng quan:

* Giá trị, bao gồm cả doanh thu, là LTV. Xem <Anchor target="_blank" href="/marketers/vi/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">So sánh giữa LTV và dữ liệu hoạt động</Anchor>.
* Cột **Doanh thu** bao gồm tất cả doanh thu, cả doanh thu quảng cáo và mua hàng trong ứng dụng.
* Truy cập sâu vào phân cấp quảng cáo (nguồn truyền thông, chiến dịch, bộ quảng cáo, địa lý) để xem các **sự kiện kiếm tiền** trong báo cáo.

**Bảng điều khiển sự kiện**[![](https://support.appsflyer.com/hc/article_attachments/360002218905)](https://support.appsflyer.com/hc/article_attachments/360002218905)

Trong Bảng điều khiển hoạt động:

* Giá trị bao gồm cả doanh thu là dựa trên ngày hoạt động. Xem <Anchor target="_blank" href="/marketers/vi/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">So sánh giữa LTV và dữ liệu hoạt động</Anchor>.
* **Số hành động Trung bình trên Mỗi Người dùng** cho biết xu hướng tương tác của người dùng với các quảng cáo được hiển thị trong ứng dụng.

<div id="examples" />

> 📄 **Ví dụ:**
>
> Ba người dùng cài đặt một ứng dụng vào ngày 31 tháng 12 năm 2017. Họ được phân bổ như sau:
>
> * Người dùng A: Mạng A
> * Người dùng B: Mạng B
> * Người dùng C: Tự nhiên
>
> Ứng dụng được tích hợp với năm nền tảng kiếm tiền khác nhau. Mỗi nền tảng sử dụng một sự kiện trong ứng dụng duy nhất bằng cách sử dụng SDK AppsFlyer như sau:
>
> * Mạng Đối tượng của Meta: fb\_ad\_view
> * Chartboost: chartboost\_ad\_view
> * Admob: admob\_ad\_view
> * Applovin: applovin\_ad\_view
> * IronSource: is\_ad\_view
>
> Sau 4 ngày kể từ thời điểm cài đặt, quảng cáo sẽ được hiển thị cho người dùng như sau:
>
>
>
> | Người dùng | Mạng UA | fb\_  <br />ad\_view | chartboost\_  <br />ad\_view | admob\_  <br />ad\_view | applovin\_  <br />ad\_view | is\_ad\_view | Tổng |
> | --- | --- | --- | --- | --- | --- | --- | --- |
> | A | Mạng A<br /><br />31-12-2017 | 01-01-2018<br /><br />$1 | 02-01-2018<br /><br />$1 | 03-01-2018<br /><br />$1 | 04-01-2018<br /><br />$1 |  | $4 |
> | B | Mạng B<br /><br />31-12-2017 | 02-01-2018<br /><br />$1 |  | 04-01-2018<br /><br />$1 |  |  | $2 |
> | C | Tự nhiên<br /><br />31-12-2017 | 01-01-2018<br /><br />$1 |  |  |  | 02-01-2018<br /><br />$1 | $2 |
>
>
>
> Nhìn vào dữ liệu, hiện chúng ta có thể tóm tắt doanh thu thu được theo mỗi người dùng, mỗi ngày (và mỗi sự kiện trong ứng dụng):
>
>
>
> | Người dùng | 01-01-2018 | 02-01-2018 | 03-01-2018 | 04-01-2018 | Tổng LTV |
> | --- | --- | --- | --- | --- | --- |
> | A | $1 | $1 | $1 | $1 | $4 |
> | B |  | $1 |  | $1 | $2 |
> | C | $1 | $1 |  |  | $2 |
> | Tổng | $2 | $3 | $1 | $2 | 8 USD |
>
>
>
> **Hiểu rõ Báo cáo:**
>
> Như đã đề cập, doanh thu quảng cáo gắn liền với LTV người dùng. Do đó, khoảng thời gian bạn chọn trong Bảng điều khiển đại diện cho nhóm người của lượt cài đặt mà doanh thu được tổng hợp cho đến ngày và giờ hiện tại. Hãy xem xét một báo cáo với hai lựa chọn ngày khác nhau:
>
> Báo cáo Hợp nhất: Ngày được chọn: 31-12-2017-05-01-2018
>
>
>
> | Mạng | Doanh thu LTV |
> | --- | --- |
> | Tự nhiên | $2 |
> | Mạng A | $4 |
> | Mạng B | $2 |
> | Mạng C | $2 |
>
>
>
> Trong trường hợp này, nhóm người là những người dùng đã cài đặt ứng dụng từ 31-12-2017 cho đến ngày hiện tại, 05-01-2018. Tất cả doanh thu do những người dùng đó tạo ra được gắn trở lại nguồn thu hút và được thể hiện dưới dạng LTV của người dùng.

</Accordion>

<div id="ad-revenue-raw-data" />

<Accordion title="Dữ liệu thô về doanh thu quảng cáo">

<Image alt="PremiumFeature.jpg" src="https://files.readme.io/674e5d0c9efde9d12008bd705b3ba95f04e133fec3f39d4278612675123d4de4-360007173877.jpg" width="78px" />

Báo cáo dữ liệu thô về doanh thu quảng cáo chứa dữ liệu được cung cấp từ các mạng kiếm tiền có tích hợp cấp thiết bị hoặc cấp lượt hiển thị với AppsFlyer.

**Nguyên tắc về dữ liệu thô doanh thu quảng cáo**

* Dữ liệu được hợp nhất theo số lượt hiển thị duy nhất cho mỗi người dùng. Số lượt hiển thị duy nhất có được nhờ sự kết hợp của mạng ad monetization, đơn vị quảng cáo và vị trí đặt quảng cáo.
* Dữ liệu thô cấp lượt hiển thị là:
  * Được hợp nhất ở cấp thiết bị và có sẵn trong báo cáo cấp thiết bị.
  * Có sẵn dưới dạng báo cáo cấp lượt hiển thị trong Data Locker.
  * [Cập nhật dữ liệu thô](/docs/roi360-guide-ad-revenue-attribution#data-freshness) giống như cập nhật doanh thu quảng cáo cấp thiết bị trong bảng điều khiển Hoạt động.

<table><tbody><tr><th>Báo cáo</th><th><p>Trang dữ liệu xuất</p></th><th>API Pull </th><th>Data Locker</th></tr><tr><td>Doanh thu quảng cáo phân bổ (không tự nhiên)</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Doanh thu quảng cáo tự nhiên</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Doanh thu quảng cáo nhắm mục tiêu lại </td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Dữ liệu thô cấp lượt hiển thị </td><td><span>-</span></td><td><span>-</span></td><td><span>✓ </span></td></tr><tr><td colspan="4">\* Báo cáo được tạo phiên bản cũng có sẵn, được cập nhật nhiều lần mỗi ngày, với dữ liệu được hợp nhất ở cấp thiết bị. Báo cáo Data Locker không được tạo phiên bản được cập nhật hàng ngày.</td></tr></tbody></table>

**Các đặc điểm và trường dữ liệu**

Các trường trong báo cáo doanh thu quảng cáo được điền:

* Thông qua chính sự kiện doanh thu quảng cáo và được liệt kê trong bảng sau. Các trường này được chia thành:
  * **Cụ thể:** Các trường cụ thể cho doanh thu quảng cáo. Ví dụ: số lượt hiển thị và vị trí. **Lưu ý**! Các trường được điền khác nhau theo đối tác kiếm tiền, như được hiển thị trong bảng Trường theo mạng trong phần này.
  * **Ngữ cảnh:** Các trường có ý nghĩa tương tự trong các báo cáo dữ liệu thô khác. Ví dụ: tên sự kiện, giá trị sự kiện, đơn vị tiền tệ.
* Do việc phân bổ sự kiện cho nguồn truyền thông đã mang đến người dùng. Có nghĩa là các trường này được sao chép từ sự kiện chuyển đổi đã mang đến người dùng. Ví dụ: nguồn truyền thông và chiến dịch. Các trường này không được liệt kê trong bảng sau.

<div id="fields-populated-by-ad-revenue" />

#### Các trường được điền bằng doanh thu quảng cáo

| api\_name | Tên trường | Loại trường | Mô tả |
| --- | --- | --- | --- |
| event\_time | Thời gian sự kiện | Ngữ cảnh | Ngày doanh thu được phân bổ cho |
| event\_name | Tên của sự kiện | Ngữ cảnh | <ul><li>Trường mặc định được đặt thành af\_ad\_revenue</li><li>Cũng có thể là một sự kiện tùy chỉnh</li></ul> |
| event\_revenue | Tiền tệ doanh thu sự kiện | Ngữ cảnh | <ul><li>Số tiền doanh thu sử dụng đơn vị tiền tệ của doanh thu sự kiện</li><li>Giá trị 0 cho biết số lượt hiển thị không có doanh thu</li></ul> |
| event\_revenue\_currency | Đơn vị tiền tệ của Sự kiện | Ngữ cảnh | Tiền tệ doanh thu sự kiện |
| event\_revenue\_XXX | Doanh thu Sự kiện XXX | Ngữ cảnh | <ul><li>Trong trang xuất: Doanh thu được chuyển đổi sang đơn vị tiền tệ cụ thể cho ứng dụng</li><li>Trong Data Locker luôn là USD</li><li>Trong API Pull theo đơn vị tiền tệ của Pull.</li></ul> |
| country | Quốc gia | Ngữ cảnh | Cài đặt quốc gia của lượt chuyển đổi cài đặt |
| ad\_unit | Đơn vị quảng cáo | Cụ thể | Loại quảng cáo |
| segment | Phân đoạn | Cụ thể | Tên vị trí đặt quảng cáo |
| monetization\_network | Mạng Kiếm tiền | Cụ thể | Mạng gửi quảng cáo |
| impressions | Lượt hiển thị | Cụ thể | Số lần người dùng nhìn thấy quảng cáo |
| mediation\_network | Mạng mediation | Cụ thể | Mạng mediation báo cáo sự kiện cho AppsFlyer |

<div id="fields-by-network" />

#### Trường theo mạng

<table><tbody><tr><th>Tên hiển thị</th><th>Admob</th><th>ironSource</th><th>AppLovin MAX</th><th>Appodeal</th><th>Fyber</th></tr><tr><td>Đơn vị quảng cáo</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Phân đoạn</td><td>-</td><td>(1)</td><td>-</td><td>-</td><td>-</td></tr><tr><td>Vị trí đặt</td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Mạng Kiếm tiền</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Lượt hiển thị</td><td><span>-</span></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td>Mạng mediation</td><td><span>-</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td colspan="6">(1) Nhà quảng cáo cần cấu hình phần này trong ironSource</td></tr></tbody></table>

[Mẫu báo cáo dữ liệu thô về doanh thu quảng cáo](https://docs.google.com/spreadsheets/d/e/2PACX-1vRm_1tevWFdzdj6JgdxYawLBtYAJj-ubDeY4g1QfbdSkd2-Adi18oemPMdd7m7cM2e3fzm7VH0w6lhD/pub?output=xlsx)

</Accordion>

<div id="data-freshness" />

<Accordion title="Tính cập nhật của dữ liệu">

Tính cập nhật của dữ liệu tùy thuộc vào loại tích hợp và phương thức báo cáo. 

Đối với các tích hợp API S2S, thời điểm sớm nhất mà dữ liệu có sẵn là:

* Bảng điều khiển và báo cáo (thông qua Data Locker), bắt đầu từ Ngày X+1 từ 8 giờ sáng theo giờ UTC, được cập nhật 6 giờ/lần và khoảng 4 lần/ngày. Đối với người đăng ký ROI360, bảng điều khiển và báo cáo được làm mới 1 lần/ngày vào các ngày 2, 3, 7 và 14.

Đối với các tích hợp SDK cấp lượt hiển thị, thời điểm sớm nhất mà dữ liệu có sẵn là:

* Bảng điều khiển và báo cáo (thông qua Data Locker) trong tình huống tốt nhất, bắt đầu từ Ngày X từ 5 giờ sáng theo giờ UTC, được cập nhật 4 giờ/lần và khoảng 6 lần/ngày.
* Báo cáo dữ liệu thô ở cấp lượt hiển thị (thông qua Data Locker), bắt đầu từ Ngày X từ 1 giờ sáng theo giờ UTC, được cập nhật hàng giờ.

Đối với cấp độ lượt hiển thị (thông qua SDK) với cấp độ thiết bị (qua API S2S), bạn được cập nhật dữ liệu cho Ngày X với độ chính xác dữ liệu cho Ngày X+1, như sau:

* Đối với dữ liệu cấp độ lượt hiển thị đến qua SDK:
  * Bảng điều khiển và báo cáo (thông qua Data Locker) trong tình huống tốt nhất, bắt đầu từ Ngày X từ 5 giờ sáng theo giờ UTC, được cập nhật 4 giờ/lần và khoảng 6 lần/ngày.
  * Báo cáo dữ liệu thô ở cấp lượt hiển thị (thông qua Data Locker), bắt đầu từ Ngày X từ 1 giờ sáng theo giờ UTC, được cập nhật hàng giờ.
* Đối với dữ liệu cấp độ thiết bị đến qua API S2S:
  * Bảng điều khiển và báo cáo (thông qua Data Locker), bắt đầu từ Ngày X+1 từ 8 giờ sáng theo giờ UTC, được cập nhật 6 giờ/lần và khoảng 4 lần/ngày. Và đối với người đăng ký ROI360, các ngày 2, 3, 7 và 14, mỗi ngày một lần.

Đối với các tích hợp cũ (trước ROI360), thời điểm sớm nhất để cập nhật dữ liệu là Ngày X+1, 5 giờ chiều theo giờ UTC.

**Lưu ý:** Khi thay đổi loại tích hợp, dữ liệu nhận được qua loại tích hợp trước đó cho các ngày trong quá khứ sẽ không được bổ sung bằng loại tích hợp mới.  Ví dụ: nếu vào ngày X, loại tích hợp bị thay đổi từ SDK thành S2S, thì dữ liệu sẽ được lấy từ ngày X+1 trở đi, không lấy từ các ngày trước ngày X.

<div id="ad-revenue-data-locker-reports" />

<Accordion title="Báo cáo Doanh thu Quảng cáo qua Data Locker">

| Tên | Tính cập nhật | Các phần trong Báo cáo |
| --- | --- | --- |
| ***Doanh thu Quảng cáo Hàng ngày (hợp nhất ở cấp thiết bị)*** | Doanh thu quảng cáo cho một ngày cụ thể (ngày X) sẽ được báo cáo vào ngày tiếp theo (X+1) vào 8 giờ tối theo giờ UTC.<br /><br />Chẳng hạn như doanh thu quảng cáo từ ngày 1 tháng 5 sẽ được báo cáo vào ngày 2 tháng 5. | Báo cáo bao gồm các phần Doanh thu Quảng cáo Đã phân bổ, Tự nhiên và Nhắm mục tiêu lại. |
| ***Báo cáo Doanh thu Quảng cáo Hàng ngày được tạo phiên bản*** ***(hợp nhất ở cấp thiết bị)*** | Báo cáo hàng ngày bao gồm:<ul><li>Các phiên bản trong ngày được tạo một lần sau mỗi 4 giờ trong ngày có doanh thu (ngày X). Dữ liệu trong ngày được trình kết nối SDK ROI thu thập.</li><li>Các phiên bản cả ngày được tạo vào ngày 2, 3, 7 và 13, dựa trên dữ liệu xuất phát từ các báo cáo API S2S.</li></ul>Nói cách khác, bộ phiên bản của báo cáo hàng ngày bao gồm các phiên bản sau:<ul><li>00:00 — 04:00 vào ngày X.</li><li>00:00 — 08:00 vào ngày X [trình kết nối SDK ROI]</li><li>00:00 — 12:00 vào ngày X [trình kết nối SDK ROI]</li></ul>…* 00:00 — 24:00 vào ngày X [trình kết nối SDK ROI]<ul><li>00:00 — 24:00 vào ngày x+1 [S2S]</li><li>00:00 — 24:00 vào ngày x+2 [S2S]</li><li>00:00 — 24:00 vào ngày x+6 [S2S]</li><li>00:00 cho đến 24:00 vào ngày x+13 [S2S]</li></ul> | Mỗi phiên bản báo cáo bao gồm các phần Doanh thu Quảng cáo Đã phân bổ, Tự nhiên và Nhắm mục tiêu lại. |
| ***Báo cáo Doanh thu Quảng cáo ở cấp lượt hiển thị (cấp lượt hiển thị)*** | Cứ mỗi giờ, bản ghi doanh thu quảng cáo ở cấp lượt hiển thị sẽ được ghi vào một tập tin riêng. |  |

</Accordion>

</Accordion>

<div id="additional-information" />

## Thông tin bổ sung

<div id="migrating-from-aggregate-to-userlevel-granularity" />

<Accordion title="Di chuyển từ mức độ chi tiết hợp nhất sang mức độ chi tiết cấp thiết bị">

* Việc di chuyển không ảnh hưởng đến dữ liệu doanh thu quảng cáo trong quá khứ. Dữ liệu này vẫn không thay đổi.
* Dữ liệu doanh thu quảng cáo được lấy mỗi ngày một lần vào 14:00 UTC bằng cách sử dụng các tùy chọn tính chi tiết được chọn vào thời điểm đó.
* Mức độ chi tiết cấp thiết bị không yêu cầu bạn xác định các sự kiện trong ứng dụng (giống như bạn thực hiện đối với báo cáo cấp độ hợp nhất). Bạn có thể tiếp tục gửi các sự kiện này, nhưng các sự kiện sẽ không ảnh hưởng đến báo cáo mức độ chi tiết cấp thiết bị trong AppsFlyer.

</Accordion>

<div id="closed-beta--ua-signals-for-ad-networks" />

<Accordion title="Tín hiệu UA cho mạng quảng cáo">

Bạn có thể muốn làm việc với các mạng quảng cáo có thể nhận tín hiệu UA. Điều này có nghĩa là các mạng quảng cáo phụ trách việc thu hút người dùng có thể nhận dữ liệu từ các mạng trung gian liên quan đến doanh thu quảng cáo và sử dụng dữ liệu đó để tối ưu hóa các chiến dịch UA của khách hàng.

Để gửi tín hiệu tới các mạng quảng cáo UA, các đối tác trung gian phải tích hợp ở cấp lượt hiển thị hoặc cấp thiết bị.

* Để biết **đối tác** cần làm gì để nhận được báo cáo, hãy xem tại <Anchor target="_blank" href="/partners/vi/docs/ad-revenue-signals-for-ua-ad-networks#enable-the-ad-revenue-report">đây</Anchor>.
* Để tìm hiểu những điều mà **nhà quảng cáo** cần thực hiện để cấp quyền cho đối tác báo cáo, hãy xem [tại đây.](#permission-to-get-ad-revenue-data)

**Danh sách các đối tác trung gian có thể gửi tín hiệu UA đến mạng quảng cáo UA:**

* Applovin Max
* Google AdMob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* Unity LevelPlay mediation (trước đây là ironSource)
* Admost
* Tradplusad
* Yandex

**Danh sách các mạng quảng cáo UA có thể nhận tín hiệu UA:**

* AdAction
* Adamobi
* Adjoe
* Adonco
* Adshow
* Appier
* Apprainbow
* Aura từ Unity
* Betop
* Bidswave
* Brandscale
* Chameleostudios
* Chartboost
* Datawave
* DLab
* Ecomonline
* Etusdigital
* Foregon
* GNA Company
* Happimobi
* Hybrid
* Inflecto
* Irismedia
* Lambadapp
* Leadidadmonster
* Lifestreet
* Liftoff
* Melodong
* Mintegral
* Mobrand
* Moloco
* Motive
* Mpnd
* Msla
* Muvmobile
* Nexamob
* Nftdroper
* Nsofmedia
* Performadlive
* Personalyrtb
* Pitatroas
* Rebornads
* RTBhouse
* Runfuns
* Scmobi
* Shalltry
* Shareit
* Smadex
* Tapjoy
* Targetmedia
* Thepurpleline
* TikTok dành cho Doanh nghiệp
* Trademob
* Truemoney
* Unity Ads
* Yandex
* Yeahmobi
* Z2A Digital
* Zoyo

</Accordion>

<div id="permission-to-get-ad-revenue-data" />

<Accordion title="Cho phép mạng quảng cáo nhận dữ liệu thô về doanh thu quảng cáo">

Mạng quảng cáo phụ trách thu hút người dùng phải được bạn cho phép trước khi có thể nhận dữ liệu từ các mạng trung gian.

**Điều kiện tiên quyết**:

* Bạn phải đăng ký gói ROI360 Nâng cao.
* hãy liên hệ với mạng quảng cáo để xác nhận rằng mạng đó có sẵn luồng tiếp nhận và logic tối ưu hóa để xử lý dữ liệu của bạn.

**Cách cấp quyền cho mạng quảng cáo nhận dữ liệu về doanh thu quảng cáo:**

1. Đi đến **Configuration** > **Active integrations**.
2. Chọn đối tác tích hợp.
3. Đi tới thanh **Integration** (Tích hợp).
4. Xác minh rằng tùy chọn **Activate Partner** (Kích hoạt Đối tác) đang bật. Nếu không, dữ liệu sẽ không được chia sẻ.
5. Đi tới tab **Permissions** (Quyền).
6. Bật **Ad network permissions**.
7. Bật **Access ad revenue raw data** (Truy cập dữ liệu thô doanh thu quảng cáo).
8. Trong **tùy chọn Sending**, chọn chỉ gửi dữ liệu về doanh thu quảng cáo từ đối tác này (**This partner only**) hoặc từ tất cả các nguồn truyền thông (**All media sources, including organic**).
9. Nhấp vào **Save Settings** (Lưu Cài đặt).
10. Liên hệ với mạng quảng cáo để thông báo bạn đã cấp quyền.
11. Đảm bảo rằng <Anchor target="_blank" href="/partners/vi/docs/ad-revenue-signals-for-ua-ad-networks#enable-the-ad-revenue-report">mạng quảng cáo đã bật báo cáo trong Data Locker và cấu hình cài đặt đầu ra của báo cáo</Anchor>

</Accordion>

<div id="ad-revenue-event-postbacks-for-ad-networks" />

<Accordion title="Đăng lại sự kiện doanh thu quảng cáo cho mạng quảng cáo">

Bạn có thể định cấu hình đăng lại doanh thu quảng cáo cho mạng quảng cáo. Điều này có nghĩa là các mạng quảng cáo phụ trách việc thu hút người dùng có thể nhận dữ liệu theo thời gian thực từ các mạng trung gian liên quan đến doanh thu quảng cáo và sử dụng dữ liệu đó để tối ưu hóa các chiến dịch UA của khách hàng. 

Để gửi đăng lại tới mạng quảng cáo UA, bạn phải có tích hợp cấp hiển thị qua SDK với mạng trung gian. AppsFlyer tự động tạo sự kiện af\_ad\_revenue cho mỗi lượt hiển thị. Bạn có thể chọn những sự kiện này từ danh sách các sự kiện sẽ được gửi qua <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration">đăng lại sự kiện trong ứng dụng</Anchor> tới mạng quảng cáo UA.

> 🚧 **Quan trọng!**
>
> Mặc dù bạn có thể gửi thông tin đăng lại về doanh thu quảng cáo cho các đối tác cụ thể nhưng bạn cần đảm bảo xác thực cách đối tác sử dụng dữ liệu trước khi bắt đầu tích hợp.

**Để thiết lập đăng lại sự kiện doanh thu quảng cáo**:

1. Tìm kiếm và chọn đối tác của bạn, hoặc <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations#quản-lý-các-tiện-ích-tích-hợp-hiện-có">từ trang thị trường</Anchor> hoặc từ **Configuration** > **trang Active** I**ntegrations** .
2. Trong tab **Integration**, cuộn xuống và bật tùy chọn **In-app event postbacks**.
3. Chọn sự kiện af\_ad\_revenue của AppsFlyer.
4. Ánh xạ sự kiện đó vào sự kiện mạng quảng cáo UA như sau:

| Mạng quảng cáo UA | Sự kiện ánh xạ af\_ad\_revenue tới | Ảnh chụp màn hình |
| --- | --- | --- |
| ironSource | adRevenue | [![](https://files.readme.io/fd902115e177e02ad96e20f2e0a81bbebbc324f5cc02b7e504e26ddd4f840897-17566964074257.png)](https://files.readme.io/fd902115e177e02ad96e20f2e0a81bbebbc324f5cc02b7e504e26ddd4f840897-17566964074257.png) |
| Unity Ads | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Moloco | Không cần ánh xạ |  |
| Mintegral | Không cần ánh xạ |  |
| Smadex | Không cần ánh xạ |  |
| Quảng cáo Meta | fb\_mobile\_purchase | [![](https://files.readme.io/fa62ae03002f9989482f8cb2b2d1628529110dbb8d17041d6ad865e381ee0361-17566964080145.png)](https://files.readme.io/fa62ae03002f9989482f8cb2b2d1628529110dbb8d17041d6ad865e381ee0361-17566964080145.png) |
| TikTok For Business - SRN Nâng cao | ImpressionLevelAdRevenue | [![](https://files.readme.io/8beed93895ac3e9d52049bea06b89388e8f32ca12d404c3461a3dcc493aed26f-24100803659665.png)](https://files.readme.io/8beed93895ac3e9d52049bea06b89388e8f32ca12d404c3461a3dcc493aed26f-24100803659665.png) |

5. Nhấp vào **Save integration**.

**Danh sách các đối tác trung gian có thể gửi các sự kiện doanh thu quảng cáo ở cấp lượt hiển thị tới các mạng quảng cáo UA:**

* Applovin Max
* Google AdMob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* ironSource
* Admost
* Tradplusad
* Yandex

**Danh sách các mạng quảng cáo UA có thể nhận đăng lại sự kiện doanh thu quảng cáo:**

* ironSource
* Unity Ads
* Moloco
* Mintegral
* Quảng cáo Meta
* Smadex
* TikTok For Business - SRN Nâng cao

</Accordion>

<div id="faq" />

<Accordion title="Câu hỏi thường gặp">

<span id="01ECF1PZ38DM24YCZPVH104FP4"></span>| **Làm cách nào để tôi có thể nhận tổng doanh thu quảng cáo từ mỗi nền tảng?**<ul><li>Phân bổ doanh thu quảng cáo được liên kết và hiển thị liên quan đến nguồn thu hút người dùng.</li><li>Điều này cung cấp chế độ xem LTV về ROI và KPI của bạn.</li><li>Để xem tổng doanh thu từ mỗi nền tảng kiếm tiền, hãy [sử dụng một sự kiện trong ứng dụng khác nhau cho từng mạng](/docs/roi360-guide-ad-revenue-attribution#aggregate-granularity-using-app-open-or-inapp-events) và sử dụng quy trình sau:<ol><li>Trong Bảng điều khiển tổng quan, hãy chuyển đến **bảng báo cáo hiệu suất hợp nhất.**</li><li>Chọn tối đa bốn sự kiện kiếm tiền đại diện cho các nền tảng bạn muốn truy vấn.</li></ol></li></ul>![selecting_monetized_events.png](https://support.appsflyer.com/hc/article_attachments/360002218865)<ol><li>Tải xuống báo cáo bằng cách nhấp vào **Export CSV** (Xuất CSV).</li><li>Tổng hợp cột **Doanh thu** của sự kiện kiếm tiền trên nền tảng được yêu cầu</li></ol>![revenue_sum_up.png](https://support.appsflyer.com/hc/article_attachments/360002218885)<br /><br />Lưu ý: Tổng doanh thu quảng cáo này là dữ liệu LTV, tức là toàn bộ doanh thu được tạo ra bởi một mạng kiếm tiền cho ứng dụng của bạn từ những người dùng đã cài đặt trong phạm vi ngày được chỉ định. |
| --- |
| **Doanh thu quảng cáo có sẵn trên trang hoạt động không?**<br /><br />Có. Trang Hoạt động báo cáo về doanh thu kết hợp từ giao dịch mua trong ứng dụng và doanh thu quảng cáo. **Lưu ý**: Dữ liệu doanh thu quảng cáo được gửi đến AppsFlyer hàng ngày, vào ngày sau khi xảy ra sự kiện |
<span id="01ECF1PZ39C7CG3R7H9P64QF51"></span>| **Tôi có cần kích hoạt đối tác trong tab Integration (Tích hợp) không?**<br /><br />Nếu bạn tương tác với đối tác chỉ để kiếm tiền từ quảng cáo (doanh thu quảng cáo), không bật tùy chọn **Activate Partner** trong thẻ Integration. Chỉ bật dữ liệu **Get Ad Revenue** trong thẻ Ad Revenue. |
<span id="01ECF1PZ39KCKY2BC3ZGK3CA0V"></span>| **Doanh thu quảng cáo cấp thiết bị được phân bổ như thế nào nếu người dùng sử dụng phiên bản ứng dụng không có SDK AppsFlyer?**<br /><br />Doanh thu quảng cáo được phân bổ là không tự nhiên. |
<span id="is-there-discrepency"></span>| **Có sự sai khác giữa dữ liệu doanh thu quảng cáo trong các bảng điều khiển và báo cáo khác nhau không?**<br /><br />Có thể có sự sai khác giữa dữ liệu doanh thu quảng cáo trong Bảng điều khiển tổng quan và báo cáo dữ liệu thô và trong bảng điều khiển Hoạt động hoặc Nhóm người. Điều này là do:<ul><li>Dữ liệu doanh thu quảng cáo trong bảng điều khiển Nhóm người và Hoạt động, cũng như dữ liệu qua API Chính và API Nhóm người được cập nhật trở về trước; dữ liệu doanh thu quảng cáo trong bảng điều khiển Tổng quan và thông qua xuất dữ liệu thô và API Pull thì không.</li><li>Đôi khi, dữ liệu được hiển thị trong bảng điều khiển Hoạt động và Nhóm người trước bảng điều khiển Tổng quan.</li><li>Bảng điều khiển bao gồm các sự kiện được đánh dấu là `af_ad_revenue` và `_monetized`, trong khi dữ liệu thô chỉ bao gồm các sự kiện `af_ad_revenue`.</li></ul> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Nhận xét |
| --- | --- |
| Điểm hạn chế | Các sự kiện về doanh thu quảng cáo không khả dụng đối với:<ul><li>API Push</li><li>Retargeting Dashboard</li></ul>Giới hạn mức độ chi tiết cấp thiết bị:<ul><li>Sự kiện af\_ad\_revenue không có sẵn cho nhóm người trong Pivot và API Chính.</li><li>Sự kiện có sẵn trong Phân tích theo nhóm người.</li><li><Anchor target="_blank" href="/marketers/vi/docs/applovin-max-ad-revenue-configuration#best-practice">Có thể xuất hiện tình trạng không nhất quán khi triển khai doanh thu giá thầu **trong ứng dụng** của Meta ads.</Anchor></li></ul>Số lượng người dùng duy nhất kích hoạt sự kiện af\_ad\_revenue không được hỗ trợ trong các bảng điều khiển AppsFlyer. |
| Truy cập mạng quảng cáo | Không thể truy cập báo cáo Nhóm người |
| Truy cập đại lý | Đại lý:<ul><li>Không thể truy cập cấu hình doanh thu quảng cáo.</li><li>Có thể xem tất cả các bảng điều khiển và dữ liệu có liên quan đến chúng.</li></ul> |
| Tính minh bạch của agency | Không được hỗ trợ |
| Múi giờ | Doanh thu quảng cáo chỉ hiển thị trong bảng điều khiển AppsFlyer và báo cáo theo múi giờ UTC. Có nghĩa là nếu được báo cáo vào 2 giờ chiều theo giờ UTC+2, thì dữ liệu đó sẽ hiển thị trong AppsFlyer là 2 PM UTC. được xử lý hàng ngày.<br /><br />Lý do là AppsFlyer cần chuẩn hóa dữ liệu được thu thập từ nhiều nguồn và đối tác, hầu hết trong số đó báo cáo dữ liệu của họ theo giờ UTC. |
| Tiền tệ | Trong AppsFlyer:<ul><li>Bảng điều khiển hiển thị đơn vị tiền tệ cụ thể cho ứng dụng của nhà quảng cáo.</li><li>Báo cáo dữ liệu thô hiển thị đơn vị tiền tệ gốc và cũng chuyển đổi tiền tệ này sang đơn vị tiền tệ cụ thể cho ứng dụng của nhà quảng cáo.</li></ul> |
| Loại dữ liệu | Cả dữ liệu tự nhiên và không tự nhiên đều được hỗ trợ |
| Tính cập nhật của dữ liệu | [Doanh thu Quảng cáo](/docs/roi360-guide-ad-revenue-attribution#data-freshness) |
| Dữ liệu lịch sử/trở về trước | <ul><li>Dữ liệu được lấy và có sẵn từ ngày tích hợp. Điều này có nghĩa là dữ liệu lịch sử sẽ không có sẵn trước ngày tích hợp (ngày 0).</li><li>Dữ liệu doanh thu quảng cáo nhận được qua API S2S trong một ngày cụ thể được cập nhật vào ngày 1, 2 và 3.</li><li>Dữ liệu doanh thu quảng cáo trong bảng điều khiển Nhóm người và Hoạt động, cũng như dữ liệu qua API Chính và API Nhóm người được cập nhật trở về trước; dữ liệu doanh thu quảng cáo trong bảng điều khiển Tổng quan và thông qua xuất dữ liệu thô và API Pull thì không. Nếu bạn có gói doanh thu nâng cao, dữ liệu cũng sẽ được cập nhật trong Data Locker.</li></ul> |
| Quyền truy cập tài khoản của người dùng | Được hỗ trợ |
| SKAN | Được hỗ trợ bởi trình kết nối SDK doanh thu quảng cáo cấp lượt hiển thị. |
| Địa lý/quốc gia | Trong bảng điều khiển Nhóm người, khi không xác định được địa lý (N/A), dữ liệu N/A sẽ không được hiển thị trong quá trình hợp nhất theo địa lý. |
| Đăng lại sự kiện trong ứng dụng | Các bài đăng lại cho đối tác cung cấp dữ liệu liên quan đến các sự kiện trong ứng dụng được phân bổ cho đối tác đó, không bao gồm dữ liệu liên quan đến các nguồn truyền thông khác. |

</Accordion>

<div id="list-of-ad-revenue-integrated-partners" />

<Accordion title="Danh sách các đối tác tích hợp doanh thu quảng cáo">

| Đối tác | Yêu cầu thông số thông tin đăng nhập | Tính chi tiết của dữ liệu |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/vi/docs/adcolony-campaign-configuration">AdColony</Anchor> | <ul><li>Mã khóa API</li><li>ID ứng dụng</li></ul> | Cấp hợp nhất với địa lý |
| Admost | <ul><li>ID ứng dụng trên mạng</li><li>Token</li></ul> | Cấp thiết bị với địa lý |
| <Anchor target="_blank" href="/marketers/vi/docs/applovin-campaign-configuration">AppLovin</Anchor> | <ul><li>Mã khóa Báo cáo</li><li>Tên Gói Ứng dụng</li></ul> | Cấp hợp nhất với địa lý |
| <Anchor target="_blank" href="/marketers/vi/docs/applovin-max-ad-revenue-configuration">AppLovin MAX</Anchor> | <ul><li>Mã khóa Báo cáo</li><li>Tên Gói Ứng dụng</li></ul> | <ul><li>Cấp thiết bị với địa lý</li><li>Cấp lượt hiển thị (thông qua SDK)</li></ul> |
| <Anchor target="_blank" href="/marketers/vi/docs/appodeal-campaign-configuration">Appodeal</Anchor> | <ul><li>Mã khóa ứng dụng</li><li>Mã khóa API</li><li>ID người dùng</li></ul> | <ul><li>Cấp hợp nhất với địa lý</li><li>Cấp thiết bị</li></ul> |
| <Anchor target="_blank" href="/marketers/vi/docs/bytedance-ads-china-campaign-configuration">Quảng cáo Bytedance - Lưu lượng truy cập tại Trung Quốc</Anchor> | <ul><li>Mã khóa an toàn</li><li>ID ứng dụng</li><li>ID tài khoản</li></ul> | Cấp hợp nhất với địa lý |
| <Anchor target="_blank" href="/marketers/vi/docs/chartboost-campaign-configuration">Chartboost</Anchor> | <ul><li>ID người dùng</li><li>Chữ ký Người dùng</li><li>ID ứng dụng</li></ul> | Cấp hợp nhất với địa lý |
| <Anchor target="_blank" href="/marketers/vi/docs/meta-ads-integration-setup">Quảng cáo Meta</Anchor> | <ul><li>Đăng nhập vào Meta ads</li></ul> | Cấp hợp nhất với địa lý |
| <Anchor target="_blank" href="/marketers/vi/docs/fyber-campaign-configuration#ad-revenue-tab">Fyber</Anchor> | <ul><li>Mã bí mật khách hàng</li><li>ID API</li><li>ID khách hàng</li></ul> | <ul><li>Cấp thiết bị với địa lý</li><li>Cấp lượt hiển thị (thông qua SDK)</li></ul> |
| Google Marketing Platform -DV360/CM (DoubleClick) | <ul><li>Đăng nhập vào Google Marketing Platform - DV360/CM</li></ul> | Cấp hợp nhất với địa lý |
| <Anchor target="_blank" href="/marketers/vi/docs/google-admob-ad-revenue-attribution-configuration">Google Admob</Anchor> | <ul><li>ID ứng dụng AdMob</li></ul> | <ul><li>Cấp hợp nhất với địa lý</li><li>Cấp lượt hiển thị (thông qua SDK)</li></ul> |
| <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-cost-and-ad-revenue#ghi-nhận-doanh-thu-quảng-cáo-bằng-google-ads">Google Ads</Anchor> | <ul><li>Xác thực API bằng OAuth</li></ul> | Cấp hợp nhất với địa lý |
| <Anchor target="_blank" href="/marketers/vi/docs/ironsource-campaign-configuration#ad-revenue-tab">Ironsource</Anchor> | <ul><li>Mã khoá Bí mật</li><li>Tên Người dùng</li><li>ID ứng dụng</li></ul> | <ul><li>Cấp hợp nhất với địa lý</li><li>Cấp thiết bị</li><li>Cấp lượt hiển thị (thông qua SDK)</li></ul> |
| Mintegral | <ul><li>ID ứng dụng</li><li>Mã khoá Bí mật</li><li>Mã khóa API</li></ul> | Cấp hợp nhất với địa lý |
| Tapjoy | <ul><li>ID ứng dụng</li><li>Mã khóa API tiếp thị</li></ul> | Cấp thiết bị với địa lý |
| TikTok dành cho Doanh nghiệp | <ul><li>Mã khóa An toàn</li><li>ID ứng dụng</li><li>ID tài khoản</li></ul> | Cấp hợp nhất với địa lý |
| TopOn | <ul><li>ID ứng dụng trên mạng</li><li>Mã khóa của nhà phát hành</li></ul> | Cấp thiết bị với địa lý |
| Tradplus mediation | <ul><li>Mã khóa API</li><li>ID ứng dụng trên mạng</li></ul> | Cấp thiết bị với địa lý |
| <Anchor target="_blank" href="/marketers/vi/docs/unity-ads-campaign-configuration">Unity Ads</Anchor> | <ul><li>Mã khóa API</li><li>ID ứng dụng</li></ul> | <ul><li>Cấp hợp nhất với địa lý</li><li>Cấp lượt hiển thị (thông qua SDK)</li></ul> |
| Quảng cáo Voodoo | <ul><li>ID gói</li><li>Mã thông báo quyền truy cập</li></ul> | Cấp hợp nhất với địa lý |
| <Anchor target="_blank" href="/marketers/vi/docs/vungle-campaign-configuration">Vungle</Anchor> | <ul><li>Mã khóa API</li><li>ID ứng dụng</li></ul> | Cấp hợp nhất với địa lý |
| Yandex | Không áp dụng | <ul><li>Cấp lượt hiển thị (thông qua SDK)</li></ul> |

</Accordion>

<div data-zendesk-anchors="ad-revenue-attribution=ph%C3%A2n-b%E1%BB%95-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o 01ECF1PZ2XNCHR4QPATTBV0VMV=ph%C3%A2n-b%E1%BB%95-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o 01ECF1PZ2Y6ZBAWSNQPEXGJWX3=integration-types-for-ad-revenue-attribution implementation=th%E1%BB%B1c-hi%E1%BB%87n 01ECF1PZ2Y9ERT5C50ZD4CDJET=th%E1%BB%B1c-hi%E1%BB%87n 01ECF1PZ31TBRGG7GW3404Y1HN=connect-to-ad-revenue-integrated-partners 01H8V10BKK6TVY9G1KWC273K0S=deduplicate-cross-referenced aggregate-ad-revenue-using-events=h%E1%BB%A3p-nh%E1%BA%A5t-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o-s%E1%BB%AD-d%E1%BB%A5ng-c%C3%A1c-s%E1%BB%B1-ki%E1%BB%87n 01H8V10BKK06Z3E823G6GNTPKH=h%E1%BB%A3p-nh%E1%BA%A5t-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o-s%E1%BB%AD-d%E1%BB%A5ng-c%C3%A1c-s%E1%BB%B1-ki%E1%BB%87n comparison-of-inapp-event-methods=so-s%C3%A1nh-c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng 01H8V10BKKMG2A704NZC2VFSJM=so-s%C3%A1nh-c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng 01ECF1PZ32Z4C20NADJ2SF3EPC=ad-revenue-api-status-and-testing ad-revenue-data=d%E1%BB%AF-li%E1%BB%87u-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o 01ECF1PZ3315R242DC78HV60YC=d%E1%BB%AF-li%E1%BB%87u-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o 01ECF1PZ33EJHN1YY0DMFKWY7N=ad-revenue-aggregate-data overview-dashboard-aggregated-performance-report=b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-t%E1%BB%95ng-quan---b%C3%A1o-c%C3%A1o-hi%E1%BB%87u-su%E1%BA%A5t-h%E1%BB%A3p-nh%E1%BA%A5t 01ECF1PZ348365STFGE3136WEJ=b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-t%E1%BB%95ng-quan---b%C3%A1o-c%C3%A1o-hi%E1%BB%87u-su%E1%BA%A5t-h%E1%BB%A3p-nh%E1%BA%A5t 01ECF1PZ348P0JCBASS4QBD56W=v%C3%AD-d%E1%BB%A5 01ECF1PZ36R9W7A0X4WBR95JDS=ad-revenue-raw-data fields-populated-by-ad-revenue=c%C3%A1c-tr%C6%B0%E1%BB%9Dng-%C4%91%C6%B0%E1%BB%A3c-%C4%91i%E1%BB%81n-b%E1%BA%B1ng-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o 01H8V10BKK7BHC31W27G22D23K=c%C3%A1c-tr%C6%B0%E1%BB%9Dng-%C4%91%C6%B0%E1%BB%A3c-%C4%91i%E1%BB%81n-b%E1%BA%B1ng-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o fields-by-network=tr%C6%B0%E1%BB%9Dng-theo-m%E1%BA%A1ng 01H8V10BKKW6NERRYCRD6BVZ54=tr%C6%B0%E1%BB%9Dng-theo-m%E1%BA%A1ng 01H8V10BKK6N5XJ6GHKC201E3Y=data-freshness 01H8V10BKKG50X5RZR8T2YB092=ad-revenue-data-locker-reports additional-information=th%C3%B4ng-tin-b%E1%BB%95-sung 01H8V10BKMX7H9H04ZBF3HRJVY=th%C3%B4ng-tin-b%E1%BB%95-sung 01H8V10BKMH781GR6GHFSD5N50=migrating-from-aggregate-to-userlevel-granularity %5Bclosed-beta%5D-ua-signals-for-ad-networks=closed-beta--ua-signals-for-ad-networks 01H8V10BKM7MMM63JHGCF2DYMC=closed-beta--ua-signals-for-ad-networks 01H8V10BKMGBZ6APJ8A9G7XDKS=th%C3%B4ng-tin-b%E1%BB%95-sung h_01H5W1BP1CA6F3HDX1F5TS98P1=permission-to-get-ad-revenue-data 01H8V10BKMED8J73G22CFVH6GJ=ad-revenue-event-postbacks-for-ad-networks h_01HFAAC1J9KQ6ZNSCRSRKE9GA3=quan-tr%E1%BB%8Dng 01H8V10BKM75W6YZ59S6FHFY93=faq 01ECF1PZ39PTEPWJDQA4XPBR4R=traits-and-limitations 01ECF1PZ3A2E5GVNC6D6XDC6WW=list-of-ad-revenue-integrated-partners" />
