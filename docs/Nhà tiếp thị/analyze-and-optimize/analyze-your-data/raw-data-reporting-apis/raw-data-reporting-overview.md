---
title: Tổng quan về báo cáo dữ liệu thô
metadata:
  keywords:
    - LTV
    - raw data
    - uninstalls
    - AFI
    - Advertisers
    - Agencies
    - Premium Feature
    - Gray
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
  created_at: '2016-03-21T08:32:06Z'
  edited_at: '2023-11-09T05:07:28Z'
  id: 209680773
  locale: vi
  section: Raw data reporting/APIs
  section_id: 6550930711057
  url: https://support.appsflyer.com/hc/vi/articles/209680773
---
> **Khái quát:** Dữ liệu cấp hàng (hay còn gọi là dữ liệu thô) mô tả các sự kiện liên quan đến người dùng như lượt cài đặt, sự kiện trong ứng dụng, lượt truy cập trang web, lượt cài đặt bị chặn trong Protect360, doanh thu quảng cáo được tạo và lượt đăng lại liên kết với người dùng được gửi cho đối tác. Báo cáo dữ liệu thô có sẵn thông qua tải xuống, API và Data Locker.

## Báo cáo dữ liệu thô—công cụ và báo cáo

Báo cáo dữ liệu thô cho phép bạn phân tích hành vi và hành trình của người dùng, đối chiếu các tài khoản mạng quảng cáo và làm phong phú thêm cho hệ thống CRM và BI. Bằng cách sử dụng dữ liệu thô, bạn tăng khả năng phân tích, tối ưu hóa và cải thiện hiệu suất của ứng dụng.

Báo cáo được tạo sẵn thông qua các công cụ báo cáo. Các công cụ có đặc điểm khác nhau phù hợp với các trường hợp sử dụng khác nhau. Ví dụ: để đối chiếu một tài khoản mạng quảng cáo nhất định, hãy tải xuống báo cáo, nếu cần, qua trang Export data. Để tải dữ liệu hiệu suất của người dùng vào hệ thống BI, hãy tải dữ liệu theo cách lập trình bằng Data Locker hoặc API Pull.

> 👍 **Lời khuyên**
>
> Bạn muốn hiểu rõ hơn về dữ liệu thô của mình? Hãy xem <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7806/play/18629/viewing-and-understanding-your-raw-data">khóa học ngắn, bổ ích này trên Cổng thông tin Học tập AppsFlyer</Anchor>.

<div id="reporting-tools-characteristics-and-features" />

<Accordion title="Công cụ báo cáo—đặc điểm và tính năng">

Các báo cáo được tạo sẵn bằng cách sử dụng các công cụ báo cáo được liệt kê trong phần này.

Những điều cần lưu ý:

* Phạm vi ngày báo cáo liên quan đến ngày hoạt động (thực tế) mà diễn ra sự kiện. Điều này trái ngược với các báo cáo hợp nhất trong đó phạm vi ngày là <Anchor target="_blank" href="/marketers/vi/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">dựa trên LTV</Anchor>.
* Mô tả trường—xem <Anchor target="_blank" href="/marketers/vi/docs/raw-data-field-dictionary">từ điển trường dữ liệu</Anchor>.

#### Công cụ báo cáo

<table><thead><tr><th>Công cụ</th><th>Mô tả</th><th>Một /nhiều ứng dụng (1)</th><th>Khả năng cập nhật dữ liệu (2)</th><th>Nhúng vào tập lệnh</th><th>Múi giờ</th><th>Tiền tệ</th></tr></thead><tbody><tr><td><a href="./raw-data-export-page" target="_blank">Trang xuất dữ liệu thô</a></td><td><ul><li>Tải xuống báo cáo sử dụng giao diện người dùng</li><li>Định dạng: tệp tin CSV</li></ul></td><td>Một</td><td>Cập nhật liên tục</td><td><strong><span>x</span></strong></td><td><p>Dành riêng cho ứng dụng</p></td><td>Dành riêng cho ứng dụng</td></tr><tr><td><a href="./pull-api-raw-data" target="_blank">API Pull\*</a></td><td><ul><li>Tải xuống báo cáo bằng lệnh gọi API.</li><li>Định dạng: tệp tin CSV</li></ul></td><td>Một</td><td>Cập nhật liên tục</td><td><span>✓</span></td><td><ul><li>Có thể lựa chọn</li><li>Mặc định: UTC</li></ul></td><td><ul><li>Có thể lựa chọn</li><li>Mặc định: USD</li></ul></td></tr><tr><td> <a href="./data-locker-for-marketers" target="_blank">Hộp khoá Dữ liệu</a> <strong><span>P</span></strong> </td><td><ul><li>Dữ liệu được truyền trực tiếp tới một <a href="./data-locker-cloud-service-setup" target="_blank">bộ chứa trên đám mây</a> </li><li>Không có giới hạn về khối lượng</li><li>Khung thời gian dữ liệu khả dụng: 14 ngày.</li><li>Định dạng: CSV hoặc  parquet</li></ul></td><td>Nhiều</td><td>Cập nhật liên tục với độ trễ vài giờ</td><td><span>✓</span></td><td>UTC</td><td>USD </td></tr><tr><td> <a href="./push-api-streaming-raw-data" target="_blank">API Push<span></span></a> <strong><span>P</span></strong> </td><td><ul><li>Dữ liệu hành trình của người dùng (lượt cài đặt, hoạt động trong ứng dụng, nhắm mục tiêu lại, SKAN) được gửi đến máy chủ của bạn trong thời gian thực.</li><li>Định dạng: JSON hoặc thông số truy vấn</li></ul></td><td>Có thể sử dụng cùng một điểm cuối</td><td>Vài phút sau khi sự kiện được ghi nhận trong AppsFlyer</td><td><span>✓</span></td><td>UTC + dành riêng cho ứng dụng</td><td>USD + dành riêng cho ứng dụng</td></tr><tr><td> <a href="./conversion-data-payloads-and-scenarios" target="_blank">Dữ liệu Chuyển đổi SDK</a> (3)</td><td><ul><li>Lấy dữ liệu chuyển đổi phân bổ trong ứng dụng.</li><li>Định dạng: JSON</li></ul></td><td>Không áp dụng</td><td> Thời gian thực &lt;5 giây</td><td> <span>✓</span> </td><td>UTC</td><td>Không áp dụng</td></tr></tbody><tfoot><tr><td colspan="7"><p><strong>Ghi chú và viết tắt:</strong><br/>(1) Hỗ trợ nhiều ứng dụng<br/>(2) Cập nhật dữ liệu thực tế phụ thuộc vào bản thân báo cáo, vì một số báo cáo là báo cáo Hàng ngày.<br/>(3) Dữ liệu chuyển đổi SDK truy xuất dữ liệu phân bổ người dùng trong chưa đầy 5 giây kể từ lần khởi chạy ứng dụng đầu tiên và do đó là phương thức kém chính xác nhất.<br/><strong><span>(P) </span></strong><span>Tính năng cao cấp<br/></span><a href="./report-generation-quotas-rate-limitations" target="_blank">(\*) Có áp dụng hạn mức tạo báo cáo</a></p></td></tr></tfoot></table>

#### Hạn chế của công cụ

<table><thead><tr><th>Hạn chế </th><th>API Pull (\*)</th><th>API Push</th><th>Hộp khóa dữ liệu</th><th>Dữ liệu Chuyển đổi<br/>SDK</th></tr></thead><tbody><tr><td>Giới hạn dữ liệu</td><td>1 triệu hàng cho mỗi lệnh gọi</td><td>Không áp dụng</td><td>Không áp dụng</td><td>Không áp dụng</td></tr><tr><td>Tùy chọn lựa chọn dữ liệu</td><td>Chọn loại dữ liệu. Các tùy chọn lựa chọn trường hạn chế</td><td>Chọn loại dữ liệu, trường và sự kiện trong ứng dụng</td><td>Chọn loại dữ liệu, trường và sự kiện trong ứng dụng</td><td>Không</td></tr><tr><td>Khung thời gian dữ liệu khả dụng</td><td>90 ngày</td><td>Không áp dụng</td><td>14 ngày </td><td>Trọn đời (có sẵn trong SDK)</td></tr><tr><td colspan="5"><p><a href="./report-generation-quotas-rate-limitations" target="_blank">(\*) Có áp dụng hạn mức tạo báo cáo</a></p></td></tr></tbody></table>

#### Những điều cần lưu ý về tích hợp

| Lưu ý | API Pull | API Push | Hộp khóa dữ liệu | Dữ liệu Chuyển đổi  <br /> SDK |
| --- | --- | --- | --- | --- |
| Phát triển phía máy chủ | Tùy chọn | Bắt buộc | Tùy chọn | Tùy chọn |
| Yêu cầu xử lý dữ liệu | Tùy chọn | Bắt buộc | Tùy chọn | Tùy chọn |
| Rủi ro mất dữ liệu | Không | Có, nếu máy chủ tiếp nhận gặp sự cố | Không | Không đáng kể, nếu có sự chậm trễ trong phản hồi của mạng quảng cáo |
| Chi phí xử lý máy khách-máy chủ | Không | Cao | Thấp | Không (trừ khi gửi dữ liệu đến máy chủ) |
| Bảo trì máy khách-máy chủ | Không | Cao | Thấp | Không (trừ khi gửi dữ liệu đến máy chủ) |
| Định dạng dữ liệu | Tệp tin CSV | JSON hoặc thông số truy vấn | CSV hoặc parquet | JSON |

</Accordion>

Các bản ghi dữ liệu thô diễn ra trong một trường hợp nhất định được nhóm lại với nhau trong các báo cáo. Ví dụ: lượt cài đặt không tự nhiên, sự kiện trong ứng dụng tự nhiên. Để tiện lợi cho việc diễn giải, các báo cáo được nhóm lại như sau:

* **Hành trình của người dùng:** Sử dụng để theo dõi hành trình và mức độ thu hút của người dùng với ứng dụng.  
  Ví dụ: lượt nhấp > lượt cài đặt > sự kiện trong ứng dụng > lượt gỡ cài đặt.
* **Tính năng:** Liên quan đến một tính năng AppsFlyer nhất định nhưng không phải là một phần của hành trình chính của người dùng. Ví dụ: đăng lại cho mạng quảng cáo, báo cáo Quy tắc Xác thực và gian lận cũng như báo cáo doanh thu quảng cáo cấp người dùng.

<div id="report-fields" />

<Accordion title="Trường báo cáo">

Từ điển trường <Anchor target="_blank" href="/marketers/vi/docs/raw-data-field-dictionary">dữ liệu thô</Anchor> chứa các trường liên quan đến báo cáo hành trình của người dùng và một số trường báo cáo tính năng. Nguyên tắc như sau:

* **Hành trình của người dùng:**
  * Có một tập hợp các trường chung.
  * Việc điền trường phụ thuộc vào trường hợp của hành trình. Ví dụ: các báo cáo không tự nhiên chứa nguồn truyền thông được ghi nhận là đã mang lại người dùng. Các trường phân bổ trong báo cáo tự nhiên không được điền vì không có nguồn truyền thông.
* **Tính năng**: Có một tập hợp các trường duy nhất hoặc chứa các trường hành trình của người dùng và các trường bổ sung liên quan đến tính năng. Ví dụ: báo cáo SKAdNetwork có một danh sách các trường duy nhất, trong khi báo cáo đăng lại chứa các trường hành trình của người dùng và các trường bổ sung liên quan đến việc gửi đăng lại cho đối tác.

**Mẹo**! Cách tốt nhất để quen thuộc với các báo cáo là xem báo cáo. Bạn có thể tải xuống báo cáo của mình qua trang <Anchor target="_blank" href="/marketers/vi/docs/raw-data-export-page">Export data</Anchor>.

Để dễ hiểu, các trường hành trình của người dùng được chia thành các nhóm dựa trên ngữ cảnh.

#### Nhóm trường dữ liệu thô của hành trình người dùng

| Nhóm trường | Có liên quan đến người dùng tự nhiên | Các trường ví dụ |
| --- | --- | --- |
| Ứng dụng | Có | ID ứng dụng, tên ứng dụng, phiên bản ứng dụng, phiên bản SDK, ATT |
| Phân bổ | Không, ngoại trừ thời gian cài đặt | Thời gian cài đặt, thời gian tiếp xúc được phân bổ, nguồn truyền thông, chiến dịch, bộ quảng cáo, quảng cáo, đối tác, loại chuyển đổi nhắm mục tiêu lại |
| Phân bổ người đóng góp | Không | Đối tác người đóng góp, loại đối sánh |
| Thông tin thiết bị | Có | ID quảng cáo, GAID, OAID, loại thiết bị, customer user ID |
| Vị trí thiết bị | Có | Địa chỉ IP, thành phố, quốc gia |
| Sự kiện | Có | Được điền vào báo cáo sự kiện trong ứng dụng:<br /><br />Tên sự kiện, giá trị sự kiện, doanh thu sự kiện |

</Accordion>

## Báo cáo hành trình của người dùng

![Raw_data_-_User_acquisition_.png](https://files.readme.io/319da2a6a5567d6cfe4a74337279e67e0bdcdb063e62ecacde5eb4293a98a1a2-36317497158033.png)

<div id="user-journey-basics" />

<Accordion title="Thông tin cơ bản về hành trình của người dùng">

Báo cáo hành trình của người dùng chứa dữ liệu được thu thập cho các sự kiện xảy ra trong suốt vòng đời của người dùng. Dữ liệu được chia thành các báo cáo theo:

* Nguồn người dùng: tự nhiên hoặc không tự nhiên
* Trường hợp của hành trình:
  * Thu hút với quảng cáo trước khi cài đặt ứng dụng (lượt hiển thị và lượt nhấp)
  * Thu hút
  * Nhắm mục tiêu lại

**Báo cáo thu hút người dùng (UA)** **chứa:**

* Lượt hiển thị và lượt nhấp xảy ra trước khi cài đặt bởi bất kỳ người dùng *tiềm năng* nào tương tác với quảng cáo.
* Sự kiện cài đặt.
* Các sự kiện trong ứng dụng tiếp theo do người dùng thực hiện.

**Báo cáo nhắm mục tiêu lại bao gồm:**

* Lượt hiển thị và lượt nhấp xảy ra khi người dùng được nhắm mục tiêu lại.
* Sự kiện chuyển đổi: Thu hút lại hoặc phân bổ lại.
* Các sự kiện trong ứng dụng tiếp theo được thực hiện như một phần của quá trình thu hút lại. Lưu ý:
  * Dữ liệu nhắm mục tiêu lại luôn là không tự nhiên.
  * Sự kiện trong ứng dụng nhắm mục tiêu lại có trong cả báo cáo UA và báo cáo sự kiện trong ứng dụng nhắm mục tiêu lại. Xem phương pháp <Anchor target="_blank" href="/marketers/vi/docs/resolve-retargeting-double-attribution">phân bổ kép nhắm mục tiêu lại</Anchor>.

    ![Raw_data_-_Retargeting.png](https://files.readme.io/717f6e43ca3b224ead9e3e1c5f9b277d2f21dbc1fe3b4c217ebf4bdbc539bab7-36317470735249.png)

Để theo dõi hành trình của người dùng, hãy kết hợp các báo cáo liên quan đến phần hành trình mà bạn quan tâm, chẳng hạn như lượt cài đặt và sự kiện trong ứng dụng. Sau khi kết hợp, hãy sắp xếp báo cáo bằng cách sử dụng ID AppsFlyer, thời gian sự kiện và loại báo cáo. Kết quả sẽ là các sự kiện của một người dùng nhất định theo thời gian, có nghĩa là hành trình của người dùng.

</Accordion>

<div id="user-journey-report-availability" />

<Accordion title="Tính khả dụng của báo cáo hành trình người dùng">

* Tính khả dụng của báo cáo phụ thuộc vào gói đăng ký của bạn.
* Báo cáo có thể bao gồm người dùng tự nhiên, người dùng không tự nhiên hoặc cả hai, theo chỉ định.
* Chính sách lưu giữ áp dụng cho các báo cáo dữ liệu thô lịch sử tùy thuộc vào công cụ báo cáo và nguồn gốc của dữ liệu thô. Nói chung, dữ liệu khả dụng trong 90 ngày trước đó. **Lưu ý**! Chính sách lưu giữ không áp dụng cho dữ liệu hợp nhất.

#### Báo cáo hành trình của người dùng

<table><thead><tr><th>danh mục</th><th>Là đặc biệt đối với Hộp khóa Dữ liệu</th><th>Chủ đề báo cáo</th><th>Tự nhiên</th><th>Không tự nhiên</th></tr></thead><tbody><tr><td>Thu hút người dùng</td><td><span>✓</span></td><td>Lượt nhấp</td><td colspan="2">Không áp dụng</td></tr><tr><td>Nhắm mục tiêu lại</td><td><span>✓</span></td><td>Lượt nhấp từ các chiến dịch nhắm mục tiêu lại </td><td colspan="2">Nhắm mục tiêu lại luôn là không tự nhiên</td></tr><tr><td>Thu hút người dùng</td><td><span>✓</span></td><td>Lượt hiển thị</td><td colspan="2">Không áp dụng</td></tr><tr><td>Nhắm mục tiêu lại</td><td><span>✓</span></td><td>Lượt hiển thị từ các chiến dịch nhắm lại mục tiêu</td><td colspan="2">Nhắm mục tiêu lại luôn là không tự nhiên</td></tr><tr><td>Thu hút người dùng</td><td>-</td><td>Lượt cài đặt </td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Thu hút người dùng</td><td>-</td><td>Sự kiện trong ứng dụng </td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Thu hút người dùng</td><td>-</td><td>Doanh thu quảng cáo được phân bổ</td><td>-</td><td><span>✓</span></td></tr><tr><td>Thu hút người dùng</td><td>-</td><td>Doanh thu quảng cáo tự nhiên</td><td><span>✓</span></td><td>-</td></tr><tr><td>Nhắm mục tiêu lại</td><td>-</td><td>Doanh thu quảng cáo nhắm mục tiêu lại</td><td colspan="2">Nhắm mục tiêu lại luôn là không tự nhiên</td></tr><tr><td>Nhắm mục tiêu lại</td><td>-</td><td>Lượt chuyển đổi nhắm mục tiêu lại (thu hút lại và phân bổ lại)</td><td colspan="2">Nhắm mục tiêu lại luôn là không tự nhiên</td></tr><tr><td>Nhắm mục tiêu lại</td><td>-</td><td>Các sự kiện trong ứng dụng nhắm mục tiêu lại (thu hút lại và phân bổ lại)</td><td colspan="2">Nhắm mục tiêu lại luôn là không tự nhiên</td></tr><tr><td>Nhắm mục tiêu lại</td><td> <span>✓</span> </td><td>Phiên nhắm mục tiêu lại (thu hút lại và phân bổ lại)</td><td colspan="2">Nhắm mục tiêu lại luôn là không tự nhiên</td></tr><tr><td>Thu hút người dùng</td><td> <span>✓</span> </td><td>Các phiên</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Thu hút người dùng</td><td>-</td><td>Các lượt Gỡ cài đặt không tự nhiên</td><td>-</td><td><span>✓</span></td></tr><tr><td>Thu hút người dùng</td><td>-</td><td>Các lượt gỡ cài đặt tự nhiên</td><td><span>✓</span></td><td>-</td></tr><tr><td>Thu hút người dùng</td><td><span>✓</span></td><td>Tương tác đa nền tảng</td><td><span>✓</span></td><td><span>✓</span></td></tr></tbody></table>

</Accordion>

<div id="user-journey-report-descriptions" />

<Accordion title="Mô tả báo cáo hành trình của người dùng">

#### Nhấp chuột và Hiển thị

| Báo cáo | Đặc điểm |
| --- | --- |
| Ngữ cảnh | Người dùng thu hút với một chiến dịch, nhấp hoặc xem một quảng cáo. |
| Đặc điểm | Các báo cáo chứa bản ghi của đường dẫn phân bổ và tiêu đề HTTP hiển thị khi người dùng nhấp hoặc <Anchor target="_blank" href="/marketers/vi/docs/measure-view-through-engagements#set-impression-links">xem</Anchor> quảng cáo. |
| Trường hợp sử dụng | <ul><li>Tối ưu hóa các chiến dịch không dẫn đến việc mở ứng dụng (cài đặt, phân bổ lại, thu hút lại).</li><li>Nhắm mục tiêu lại những người dùng này bằng các chiến dịch khác nhau.</li></ul> |
| Báo cáo ví dụ | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=1036692270&single=true&output=csv">Lượt nhấp</Anchor> |
| Lưu ý | Dữ liệu SRN không có sẵn. |
| Người dùng bị hạn chế | Trong một số trường hợp, do các quy tắc bảo mật, dữ liệu lượt hiển thị và lượt nhấp bị hạn chế (không có mã định danh người dùng) hoặc hoàn toàn không có sẵn. Tính khả dụng phụ thuộc vào nguồn truyền thông và nền tảng. |

#### Lượt cài đặt và chuyển đổi nhắm mục tiêu lại

<table><thead><tr><th rowspan="2">Tên báo cáo </th><th rowspan="2"><p>Thu hút người dùng: Lượt cài đặt</p></th><th rowspan="2">Nhắm mục tiêu lại: Lượt chuyển đổi</th></tr></thead><tbody><tr><td> <br/>Ngữ cảnh</td><td><p>Khi người dùng mở một ứng dụng lần đầu.</p></td><td><p>Sau khi người dùng thu hút với một quảng cáo nhắm mục tiêu lại và sau đó mở ứng dụng. Chuyển đổi nhắm mục tiêu lại là thu hút lại hoặc phân bổ lại.</p> Xem <a href="./retargeting-attribution-guide#retargeting-reports-and-raw-data" target="_blank">hướng dẫn Phân bổ nhắm mục tiêu lại.</a> </td></tr><tr><td>Các trường hợp sử dụng</td><td><ul><li>Tạo báo cáo hợp nhất bằng cách sử dụng các trường không có sẵn thông qua công cụ phân tích AppsFlyer.</li><li>Kết hợp với các báo cáo khác để phân tích chéo, nâng cao.</li><li>Phân tích hiệu suất với nhiều phương diện khác nhau, chẳng hạn như thành phố, khu vực đô thị, v.v. </li><li>Phân đoạn người dùng theo quốc gia, thành phố và ngôn ngữ cho các mục đích nhắm mục tiêu.</li><li>Nhận ID thiết bị của người dùng cho mục đích nhắm mục tiêu lại.</li></ul></td><td>Tương tự với lượt cài đặt.</td></tr><tr><td>So sánh tự nhiên và không tự nhiên</td><td><ul><li> <strong>Không tự nhiên:</strong> Các nhóm trường phân bổ và phân bổ người đóng góp được điền</li><li> <strong>Tự nhiên:</strong> Trường nguồn truyền thông, rỗng, trống hoặc tự nhiên. Hãy cân nhắc điều này khi bạn tải dữ liệu vào hệ thống của mình. </li></ul></td><td>Không áp dụng</td></tr><tr><td>Báo cáo ví dụ</td><td><a href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=0&amp;single=true&amp;output=csv" target="_blank">Lượt cài đặt</a></td><td>Báo cáo chuyển đổi nhắm mục tiêu lại có cấu trúc giống với báo cáo lượt cài đặt. Một số trường được điền trong trường hợp nhắm mục tiêu lại. Xem <a href="./retargeting-attribution-guide#retargeting-reports-and-raw-data" target="_blank">dữ liệu thô nhắm mục tiêu lại</a>. </td></tr></tbody></table>

#### Sự kiện trong Ứng dụng

<Table>
  <thead>
    <tr>
      <th>
        Báo cáo
      </th>
      <th>
        Đặc điểm
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="report-context"></span>
        Trường hợp báo cáo
      </td>
      <td>
        Danh sách theo thứ tự thời gian các hành động do người dùng thực hiện sau khi phân bổ (cài đặt, phân bổ lại hoặc thu hút lại)
      </td>
    </tr>
    <tr>
      <td><span id="characteristics"></span>
        Đặc điểm
      </td>
      <td>
        * Cấu trúc báo cáo và các trường tương tự với cấu trúc của báo cáo lượt cài đặt.
        * Các trường dành riêng mô tả sự kiện. Các trường này bao gồm tên sự kiện, giá trị, doanh thu và thời gian.
      </td>
    </tr>
    <tr>
      <td><span id="use-case"></span>
        Trường hợp sử dụng
      </td>
      <td>
        Sử dụng báo cáo để:

        * Nhận thông tin chi tiết bằng cách theo dõi hành trình của người dùng trong suốt thời gian hoạt động của người dùng
        * Kết hợp dữ liệu thô của sự kiện cài đặt và trong ứng dụng để theo dõi toàn bộ hành trình của người dùng.
      </td>
    </tr>
    <tr>
      <td><span id="event-values"></span>
        Giá trị của sự kiện
      </td>
      <td>
        **Trường giá trị sự kiện**

        Trường giá trị sự kiện chứa tất cả dữ liệu liên quan đến sự kiện trong JSON. Bạn có thể tải dữ liệu này vào hệ thống BI của mình để phân tích thêm.

        **Lời khuyên!** Bạn có thể sử dụng <Anchor target="_blank" href="https://docs.microsoft.com/en-us/power-query/parse-json-xml">Power Query trong Microsoft Excel</Anchor> để phân tích cú pháp các thông số sự kiện từ chuỗi văn bản JSON.

        ```json
        {"af_level":"10","af_user_journey":"3387","arena":"7","char_type":"paladin"}
        ```

        **Báo cáo doanh thu**

        Dữ liệu doanh thu và ROI trong AppsFlyer được lấy từ af\_revenue sẽ được gửi trong các sự kiện.

        Khi thông số af\_revenue được gửi trong một sự kiện trong ứng dụng, AppsFlyer sẽ sử dụng thông số này để điền vào trường doanh thu của sự kiện. Trong trường này, AppsFlyer sử dụng để cập nhật bảng điều khiển và các báo cáo hợp nhất.

        Lưu ý! Chỉ sử dụng thông số af\_revenue với các sự kiện trong ứng dụng mô tả **doanh thu thực tế đã tạo ra.** Đối với các sự kiện khác liên quan đến doanh thu, nhưng không phải là cuối cùng, ví dụ: add\_to\_cart, hãy sử dụng các thông số khác nhau như af\_price
      </td>
    </tr>
    <tr>
      <td><span id="example-report"></span>
        Báo cáo ví dụ
      </td>
      <td>
        [Sự kiện trong Ứng dụng](https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=819556999&single=true&output=csv)
      </td>
    </tr>
    <tr>
      <td><span id="remarks"></span>
        Lưu ý
      </td>
      <td>
        * Sự kiện nhắm mục tiêu lại trong ứng dụng được <Anchor target="_blank" href="/marketers/vi/docs/resolve-retargeting-double-attribution">ghi nhận hai lần</Anchor> trong cả báo cáo dữ liệu UA và dữ liệu thô sự kiện trong ứng dụng nhắm mục tiêu lại.
        * Sự kiện trong ứng dụng không bao gồm sự kiện khởi chạy (af\_app\_opened). Điều này có sẵn trong báo cáo dữ liệu thô của <Anchor target="_blank" href="/marketers/vi/docs/measure-sessions">phiên</Anchor>.
        * Vị trí địa lý: Được lấy bằng địa chỉ IP của người dùng tại thời điểm sự kiện được thực hiện.
      </td>
    </tr>
  </tbody>
</Table>

#### Các phiên

| Báo cáo | Đặc điểm |
| --- | --- |
| Ngữ cảnh | Khi người dùng mở ứng dụng, một sự kiện phiên được gửi đến AppsFlyer. Sự kiện được ghi nhận nếu vượt quá ngưỡng <Anchor target="_blank" href="/marketers/vi/docs/measure-sessions">thời gian tối thiểu giữa các phiên</Anchor>. |
| Đặc điểm | Cấu trúc báo cáo giống với báo cáo sự kiện trong ứng dụng. Phiên (sự kiện phiên) nằm trong một báo cáo riêng biệt do các sự kiện như vậy có số lượng rất lớn. |
| Trường hợp sử dụng | Hiểu mức độ người dùng thu hút với ứng dụng. |
| Báo cáo ví dụ | Báo cáo phiên tương tự như báo cáo sự kiện trong ứng dụng. Lưu ý: Trong dữ liệu thô, các phiên có tên sự kiện là *launch*. |

#### Gỡ cài đặt

| Báo cáo | Đặc điểm |
| --- | --- |
| Ngữ cảnh | Bản ghi người dùng gỡ cài đặt ứng dụng. |
| Đặc điểm | <ul><li>Báo cáo này cập nhật hàng ngày và không liên tục, như trường hợp của các báo cáo hành trình của người dùng khác.</li><li>Trong báo cáo, thời gian sự kiện đại diện cho thời gian AppsFlyer xác định ứng dụng đã được gỡ cài đặt chứ không phải thực sự bản thân lượt gỡ cài đặt. Xem Đo lường lượt gỡ cài đặt.</li></ul> |
| Các trường khả dụng | <ul><li>Nếu người dùng đến từ một nguồn truyền thông không tự nhiên, thì các trường nguồn truyền thông sẽ được điền.</li><li>Xin lưu ý rằng sự kiện gỡ cài đặt được máy chủ AppsFlyer tạo sau khi xác định rằng người dùng đã gỡ cài đặt. Do đó, nhiều trường sẽ không được điền.</li><li>Mã định danh người dùng có sẵn là các mã định danh được ghi nhận tại thời điểm cài đặt. Không bao giờ có sẵn CUID.</li><li>Các trường liên quan đến địa lý được điền với vị trí của người dùng tại thời điểm thu hút với nguồn truyền thông (lượt nhấp hoặc hiển thị). Nếu vị trí thu hút không có sẵn thì vị trí được liên kết với sự kiện cài đặt sẽ được sử dụng.</li></ul> |
| Báo cáo ví dụ | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=1558773473&single=true&output=csv">Lượt gỡ cài đặt</Anchor> Lưu ý! Trong ví dụ, để rõ ràng, hàng 2 cho biết trường nào sẽ được điền nếu có sẵn dữ liệu liên quan. |
| Các trường hợp sử dụng | <ul><li>Phân tích các đặc điểm sự kiện gỡ cài đặt, thiết bị và người dùng.</li><li>Tạo đối tượng sự kiện gỡ cài đặt để nhắm mục tiêu lại.</li></ul> |

</Accordion>

<div id="user-journey-report-availability-per-tool" />

<Accordion title="Tính khả dụng của báo cáo hành trình của người dùng trên mỗi công cụ">

#### Báo cáo mức độ thu hút với quảng cáo theo công cụ

<table><tbody><tr><th>Báo cáo</th><th>Xuất dữ liệu</th><th>API Pull</th><th>Hộp khóa dữ liệu</th><th>API Push</th><th>Dữ liệu Chuyển đổi<br/> SDK</th></tr><tr><td>Lượt hiển thị (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Lượt nhấp (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td colspan="6">(1) Dữ liệu về lượt nhấp và lượt hiển thị được cung cấp bởi các mạng không phải SRN. SRN không cung cấp dữ liệu này.</td></tr></tbody></table>

#### Báo cáo thu hút người dùng theo công cụ

| Báo cáo | Xuất dữ liệu | API Pull | Hộp khóa dữ liệu | API Push | Dữ liệu chuyển đổi SDK |
| --- | --- | --- | --- | --- | --- |
| Lượt cài đặt | ✓ | ✓ | ✓ | ✓ | ✓ |
| Các phiên | - | - | ✓ | - | - |
| Sự kiện trong Ứng dụng | ✓ | ✓ | ✓ | ✓ | - |
| Gỡ cài đặt | ✓ | ✓ | ✓ | - | - |

#### Báo cáo dữ liệu thô nhắm mục tiêu lại theo công cụ

<table><thead><tr><th>Báo cáo</th><th>Xuất dữ liệu</th><th>API Pull</th><th>Hộp khóa dữ liệu</th><th>API Push</th><th>Dữ liệu chuyển đổi<br/>SDK</th></tr></thead><tbody><tr><td>Lượt nhấp (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Chuyển đổi (phân bổ lại + thu hút lại)</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Lượt hiển thị (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Các phiên</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Sự kiện trong Ứng dụng</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr></tbody><tbody><tr><td colspan="6"><p>(1) Dữ liệu về lượt nhấp và lượt hiển thị được cung cấp bởi các mạng không phải SRN. SRN không cung cấp dữ liệu này.</p></td></tr></tbody></table>

</Accordion>

<div id="faq" />

<Accordion title="Câu hỏi thường gặp">

| Chi tiết |
| --- |
| **Tại sao quảng cáo Meta thiếu dữ liệu thô?**<br /><br />Theo mặc định, dữ liệu thô của quảng cáo Meta được phân bổ cho <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions">nguồn truyền thông bị hạn chế</Anchor>. Xem <Anchor target="_blank" href="/marketers/vi/docs/meta-ads-integration-setup#userlevel-data">dữ liệu cấp người dùng của quảng cáo Meta.</Anchor> |
| **Đâu là khác biệt giữa các nhãn thời gian?**<br /><br />Nhãn thời gian là chung cho tất cả các báo cáo. Điều này cho phép bạn có thể kết hợp các báo cáo khác nhau.<br /><br />Các nhãn thời gian sau có liên quan:<ul><li>**Thời gian tiếp xúc được phân bổ**: Thời gian người dùng thu hút với một quảng cáo.</li><li>**Thời gian** **cài đặt**: Thời gian ứng dụng được khởi chạy lần đầu.</li><li>**Thời gian sự kiện**: Thời gian sự kiện diễn ra.</li></ul>Cân nhắc:<ul><li>Trong báo cáo lượt cài đặt, thời gian cài đặt và sự kiện là giống nhau.</li><li>Trong báo cáo sự kiện trong ứng dụng, thời gian cài đặt và sự kiện là khác nhau. Sai lệch có thể cho thấy thời gian trôi qua giữa thời điểm khởi chạy ứng dụng và mức độ thu hút của người dùng với ứng dụng.</li></ul> |
| **Mục đích của trường người đóng góp là gì?**<br /><br />Trường người đóng góp liệt kê các nguồn truyền thông của người đóng góp. Đôi khi được gọi là <Anchor target="_blank" href="/marketers/vi/docs/measure-assisted-installs#báo-cáo-lượt-cài-đặt-được-hỗ-trợ">Lượt cài đặt được Hỗ trợ</Anchor>. Trong Protect360, trường này cũng được sử dụng để <Anchor target="_blank" href="/marketers/vi/docs/protect360-raw-data-reports#điều-chỉnh-phân-bổ-lượt-cài-đặt-bị-đánh-cắp">sửa lỗi phân bổ lượt cài đặt bị đánh cắp</Anchor>. |
| **Trường từ khóa là gì—tại sao không có sẵn trong tất cả các lượt cài đặt không tự nhiên?**<br /><br />Lượt cài đặt được phân bổ cho Google Ads hoặc Apple Search Ads, có thể chứa các từ khóa hoặc ID từ khóa được liên kết với quảng cáo mang lại lượt cài đặt. |

</Accordion>

<div id="install-report-tips" />

<Accordion title="Mẹo báo cáo lượt cài đặt">

**Hiểu hành trình của người dùng**

Hành trình của người dùng là một loạt các bước mà người dùng thực hiện trước khi đạt đến mục tiêu như mua sản phẩm hoặc đặt chuyến bay. Ý tưởng đằng sau việc phân tích hành trình của người dùng là theo dõi hành vi người dùng trong ứng dụng, mức độ hoạt động của họ và giá trị họ mang lại trong một khoảng thời gian nhất định.

Bạn có thể xác định và đánh dấu hành trình của người dùng với sự trợ giúp của ID AppsFlyer. ID được tạo cho mỗi lượt cài đặt ứng dụng trên mỗi thiết bị. ID không thay đổi trong suốt thời gian sử dụng của người dùng (từ cài đặt đến gỡ cài đặt.) ID vẫn tồn tại nếu người dùng đặt lại ID thiết bị của họ.

Vì báo cáo sự kiện cài đặt và trong ứng dụng có cấu trúc giống nhau nên chúng có thể được hợp nhất thành một báo cáo. Trong báo cáo hợp nhất, bạn có thể tổng hợp và lọc bằng cách sử dụng ID AppsFlyer và Customer User ID (nếu có) để phân tích hành trình của người dùng.

> 📄 **Ví dụ**
>
> #### Người dùng thu hút—mạnh
>
> * Một người dùng cài đặt ứng dụng vào lúc 09:31 ngày 20 tháng 8.
> * Báo cáo hợp nhất cho thấy người này đã thực hiện giao dịch mua hàng vào lúc 10:31 ngày 20 tháng 8, 15:22 ngày 22 tháng 8 và 16:47 ngày 25 tháng 8.
> * Từ đó, chúng tôi kết luận rằng người dùng là người dùng thu hút. Họ đã mua sau một giờ khởi chạy ứng dụng và tiếp tục mua vào các ngày sau đó.
>
> #### Người dùng thu hút—yếu
>
> * Một người dùng cài đặt ứng dụng vào ngày 30 tháng 7. Báo cáo hợp nhất cho thấy rằng họ đã thêm một mặt hàng vào giỏ vào ngày 15 tháng 8, nhưng không có sự kiện mua hàng nào sau đó.
> * Bạn có thể cho rằng người dùng do dự khi mua hàng và chọn nhắm mục tiêu lại đối với họ cho các mặt hàng họ đã thêm vào giỏ hàng.
>
> #### Phân tích hành trình của người dùng để tối ưu hóa chiến dịch
>
> * Người quản lý thu hút người dùng (UA) của một ứng dụng du lịch tải xuống báo cáo lượt cài đặt và sự kiện trong ứng dụng và hợp nhất chúng.
> * Sau đó, để xem hành trình của người dùng trong ứng dụng, họ lọc hoặc tổng hợp dữ liệu bằng cách sử dụng ID AppsFlyer.
> * Họ nhận thấy rằng có một người dùng, được xác định bằng ID AppsFlyer, đã tải xuống ứng dụng cách đây 12 tháng và đặt chuyến bay vài ngày sau đó.
> * Sau đó, người dùng này đã xem một số ưu đãi chuyến bay nhưng không thực hiện đặt vé. Khi xem xét thêm, người quản lý UA nhận thấy nhiều người dùng cũng có kiểu hành vi tương tự nên đã quyết định tìm hiểu sâu hơn.
> * Họ nhận thấy rằng hầu hết những người dùng này đến từ **Quảng cáo A** của **Chiến dịch B** chạy trên **Nguồn truyền thông C.** Hóa ra, quảng cáo và chiến dịch này đã nhắm mục tiêu đến những người dùng muốn đi đến một điểm đích cụ thể.
> * Bằng cách phân tích hành trình của người dùng, người quản lý UA có thể kết luận rằng chiến dịch đã tập trung phạm vi quá hẹp và ứng dụng không đủ thu hút người dùng.

</Accordion>

## Báo cáo tính năng

Báo cáo liên quan đến các tính năng bổ sung có sẵn trong nền tảng

* <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">Doanh thu quảng cáo</Anchor>
* <Anchor target="_blank" href="/marketers/vi/docs/incrementality-for-remarketing-overview#raw-data-reports">Tính gia tăng</Anchor>
* <Anchor target="_blank" href="/marketers/vi/docs/skan-raw-data-reports">SKAdNetwork</Anchor>

<div id="postbacks" />

<Accordion title="Đăng lại">

Sử dụng báo cáo đăng lại, để xem xét các bản sao dữ liệu được gửi đến mạng quảng cáo. Ví dụ: sử dụng chúng để xem xét các khác biệt. Các báo cáo này dành cho mục đích cung cấp thông tin và không bắt buộc tích hợp với mạng quảng cáo.

* Báo cáo bao gồm:
  * Bản sao của các đăng lại đã được gửi đến nguồn truyền thông được phân bổ.
  * <Anchor target="_blank" href="/marketers/vi/docs/raw-data-field-dictionary">Các trường dữ liệu thô</Anchor> và các trường bổ sung như được trình bày chi tiết trong phần này.
* Báo cáo không chứa:
  * Lượt cài đặt của SRN.
  * Các sự kiện trong ứng dụng liên quan đến quảng cáo Meta, Twitter và Apple Search Ads.
  * Đăng lại của đối tác không được phân bổ. Xem <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#g">các sự kiện được phân bổ cho bất kỳ đối tác hoặc tự nhiên</Anchor>.
  * Người dùng tự nhiên. Xem <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#f">về lượt cài đặt tự nhiên.</Anchor>
  * Chiến dịch cài đặt CPA đã vô hiệu hóa Đăng lại lượt cài đặt.
* Bắt đầu từ tháng 3 năm 2021, các trường được điền theo tùy chọn cài đặt Quyền riêng tư Nâng cao của mạng. Có nghĩa là, nếu Quyền riêng tư Nâng cao được bật, thì một số trường, chẳng hạn như mã định danh người dùng sẽ không được đưa vào. Xem <Anchor target="_blank" href="/partners/vi/docs/advanced-privacy-guide-postback-macros-for-ad-networks#advanced-privacy-postback-specification">thông số kỹ thuật đăng lại Quyền riêng tư Nâng cao dành cho mạng quảng cáo.</Anchor>
* <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTs4MUZTBKRQF24n-T8JM1L6EhU4TayYneX6MB5HjM9iwnrQtX8tlPLBA-J7zmqDcJqYTCpRxhStdGg/pub?output=xlsx">URI dành cho báo cáo đăng lại thông qua API Pull</Anchor>

#### Báo cáo đăng lại (có sẵn qua trang Export Data và API Pull)

| Chủ đề báo cáo | Các sự kiện được gửi đến nguồn truyền thông được phân bổ |
| --- | --- |
| Lượt cài đặt | Lượt cài đặt không tự nhiên (UA) |
| Sự kiện trong Ứng dụng | Sự kiện trong Ứng dụng không tự nhiên |
| Đăng lại lượt chuyển đổi nhắm mục tiêu lại | Nhắm mục tiêu lại (thu hút lại và phân bổ lại) |
| Nhắm lại mục tiêu Sự kiện trong Ứng dụng | Nhắm lại mục tiêu Sự kiện trong Ứng dụng |

#### Các trường bổ sung trong báo cáo đăng lại

| Trường | Lưu ý |
| --- | --- |
| URL Đăng lại | Một số giá trị, như doanh thu, có thể không xuất hiện trong trường thích hợp, nhưng bạn vẫn có thể thấy dữ liệu này trong URL **Đăng lại**. |
| Phương thức đăng lại |  |
| Mã phản hồi HTTP đăng lại | 200: Xác nhận rằng mạng quảng cáo đã nhận được lượt đăng lại |
| Thông báo lỗi đăng lại |  |

</Accordion>

<div id="protect360-fraud-and-validation-rules" />

<Accordion title="Gian lận và quy tắc xác thực Protect360">

* Xem các báo cáo dữ liệu thô của <Anchor target="_blank" href="/marketers/vi/docs/protect360-raw-data-reports">Protect360</Anchor> và <Anchor target="_blank" href="/marketers/vi/docs/implement-validation-rules-to-prevent-fraud#outcomes">quy tắc xác thực</Anchor>
* Mạng quảng cáo và đại lý cần được nhà quảng cáo <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#access-protect360-dashboard-raw-data">cấp quyền</Anchor> để truy cập vào báo cáo Protect360 và báo cáo Quy tắc Xác thực

**Để cấp cho đối tác tích hợp quyền truy cập Protect360:**

1. Đi đến **Configuration** > **Active Integrations**.
2. Chọn đối tác tích hợp.
3. Trong tab **Permissions**, hãy bật tùy chọn **Access your Protect360 dashboard & raw data via API**.
4. Để cấp quyền truy cập vào bảng điều khiển Sự kiện trong ứng dụng (CPA), hãy bật tùy chọn **Access aggregate in-app events data**.

</Accordion>

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/aggregated-and-analytics-reporting-overview">Báo cáo tổng hợp và phân tích</Anchor>

<div data-zendesk-anchors="raw-data-reporting%E2%80%94tools-and-reports=b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4c%C3%B4ng-c%E1%BB%A5-v%C3%A0-b%C3%A1o-c%C3%A1o h_01HE7SRDXQ9TR0CRB2JC9XCQE2=b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4c%C3%B4ng-c%E1%BB%A5-v%C3%A0-b%C3%A1o-c%C3%A1o h_01HE7SRDXQQJFMV9EJKPY34D00=l%E1%BB%9Di-khuy%C3%AAn reporting-tools%E2%80%94characteristics-and-features=reporting-tools-characteristics-and-features h_01HE7SRDXQFJGMY05K1SV4TF63=reporting-tools-characteristics-and-features reporting-tools=c%C3%B4ng-c%E1%BB%A5-b%C3%A1o-c%C3%A1o h_01HE7SRDXQ647XRQ8QVMPGH43B=c%C3%B4ng-c%E1%BB%A5-b%C3%A1o-c%C3%A1o tool-limitations=h%E1%BA%A1n-ch%E1%BA%BF-c%E1%BB%A7a-c%C3%B4ng-c%E1%BB%A5 h_01HE7SRDXQWQAKR0G6CNKC5AMT=h%E1%BA%A1n-ch%E1%BA%BF-c%E1%BB%A7a-c%C3%B4ng-c%E1%BB%A5 integration-considerations=nh%E1%BB%AFng-%C4%91i%E1%BB%81u-c%E1%BA%A7n-l%C6%B0u-%C3%BD-v%E1%BB%81-t%C3%ADch-h%E1%BB%A3p h_01HE7SRDXQN3HSMGAPBAX9S3MB=nh%E1%BB%AFng-%C4%91i%E1%BB%81u-c%E1%BA%A7n-l%C6%B0u-%C3%BD-v%E1%BB%81-t%C3%ADch-h%E1%BB%A3p h_01HE7SRDXQRPD8MHC8M5916HTQ=report-fields user-journey-raw-data-field-groups=nh%C3%B3m-tr%C6%B0%E1%BB%9Dng-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-c%E1%BB%A7a-h%C3%A0nh-tr%C3%ACnh-ng%C6%B0%E1%BB%9Di-d%C3%B9ng h_01HE7SRDXQMGQEG1QWGWEESQER=nh%C3%B3m-tr%C6%B0%E1%BB%9Dng-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-c%E1%BB%A7a-h%C3%A0nh-tr%C3%ACnh-ng%C6%B0%E1%BB%9Di-d%C3%B9ng user-journey-reports=b%C3%A1o-c%C3%A1o-h%C3%A0nh-tr%C3%ACnh-c%E1%BB%A7a-ng%C6%B0%E1%BB%9Di-d%C3%B9ng h_01HE7SRDXQZ50WMKCMYHZM7D92=b%C3%A1o-c%C3%A1o-h%C3%A0nh-tr%C3%ACnh-c%E1%BB%A7a-ng%C6%B0%E1%BB%9Di-d%C3%B9ng h_01HE7SRDXQFN0P9QK8SKAZKVKP=user-journey-basics h_01HE7SRDXRS2B12Z67MYMH0QN9=user-journey-report-availability user-journey-reports::d286e1f5=b%C3%A1o-c%C3%A1o-h%C3%A0nh-tr%C3%ACnh-c%E1%BB%A7a-ng%C6%B0%E1%BB%9Di-d%C3%B9ng-1 h_01HE7SRDXR7YQGWN4FNDXMNMX8=b%C3%A1o-c%C3%A1o-h%C3%A0nh-tr%C3%ACnh-c%E1%BB%A7a-ng%C6%B0%E1%BB%9Di-d%C3%B9ng-1 h_01HE7SRDXRK6G27SDFK3CGDCRC=user-journey-report-descriptions clicks-and-impressions=nh%E1%BA%A5p-chu%E1%BB%99t-v%C3%A0-hi%E1%BB%83n-th%E1%BB%8B h_01HE7SRDXRC9YKZ0P9ED0218SJ=nh%E1%BA%A5p-chu%E1%BB%99t-v%C3%A0-hi%E1%BB%83n-th%E1%BB%8B installs-and-retargeting-conversions=l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-v%C3%A0-chuy%E1%BB%83n-%C4%91%E1%BB%95i-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i h_01HE7SRDXRN60XE5BSDQY28N71=l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-v%C3%A0-chuy%E1%BB%83n-%C4%91%E1%BB%95i-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i inapp-events=s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HE7SRDXR3ZT39EDNW4MVZZTX=s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng sessions=c%C3%A1c-phi%C3%AAn h_01HE7SRDXRY05XQCMZE6YPXGWQ=c%C3%A1c-phi%C3%AAn uninstalls=g%E1%BB%A1-c%C3%A0i-%C4%91%E1%BA%B7t h_01HE7SRDXRA7ESDD4ME51WWBPR=g%E1%BB%A1-c%C3%A0i-%C4%91%E1%BA%B7t h_01HE7SRDXRZYNFGK4CNP4VPAE0=user-journey-report-availability-per-tool ad-engagement-report-by-tool=b%C3%A1o-c%C3%A1o-m%E1%BB%A9c-%C4%91%E1%BB%99-thu-h%C3%BAt-v%E1%BB%9Bi-qu%E1%BA%A3ng-c%C3%A1o-theo-c%C3%B4ng-c%E1%BB%A5 h_01HE7SRDXR171M74HMQBZJ2E8R=b%C3%A1o-c%C3%A1o-m%E1%BB%A9c-%C4%91%E1%BB%99-thu-h%C3%BAt-v%E1%BB%9Bi-qu%E1%BA%A3ng-c%C3%A1o-theo-c%C3%B4ng-c%E1%BB%A5 user-acquisition-reports-by-tool=b%C3%A1o-c%C3%A1o-thu-h%C3%BAt-ng%C6%B0%E1%BB%9Di-d%C3%B9ng-theo-c%C3%B4ng-c%E1%BB%A5 h_01HE7SRDXRMGEP5QB452ZKQ8X7=b%C3%A1o-c%C3%A1o-thu-h%C3%BAt-ng%C6%B0%E1%BB%9Di-d%C3%B9ng-theo-c%C3%B4ng-c%E1%BB%A5 retargeting-raw-data-reports-by-tool=b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i-theo-c%C3%B4ng-c%E1%BB%A5 h_01HE7SRDXRXR4J3HTMYW2P233Y=b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i-theo-c%C3%B4ng-c%E1%BB%A5 h_01HE7SRDXRWW3JKNESSN2QA4DV=faq h_01HE7SRDXR61K28JGA8944D6HV=install-report-tips h_01HE7SRDXRKFR2WYGNF317CTRX=v%C3%AD-d%E1%BB%A5 engaged-user%E2%80%94strong=ng%C6%B0%E1%BB%9Di-d%C3%B9ng-thu-h%C3%BAtm%E1%BA%A1nh h_01HE7SRDXRW0CWHGQV75VF66DC=ng%C6%B0%E1%BB%9Di-d%C3%B9ng-thu-h%C3%BAtm%E1%BA%A1nh engaged-user%E2%80%94weak=ng%C6%B0%E1%BB%9Di-d%C3%B9ng-thu-h%C3%BAty%E1%BA%BFu h_01HE7SRDXRNMDZEJQ32665T14F=ng%C6%B0%E1%BB%9Di-d%C3%B9ng-thu-h%C3%BAty%E1%BA%BFu analyzing-the-user-journey-for-campaign-optimization=ph%C3%A2n-t%C3%ADch-h%C3%A0nh-tr%C3%ACnh-c%E1%BB%A7a-ng%C6%B0%E1%BB%9Di-d%C3%B9ng-%C4%91%E1%BB%83-t%E1%BB%91i-%C6%B0u-h%C3%B3a-chi%E1%BA%BFn-d%E1%BB%8Bch h_01HE7SRDXRRET0YN4Q8WYMENSR=ph%C3%A2n-t%C3%ADch-h%C3%A0nh-tr%C3%ACnh-c%E1%BB%A7a-ng%C6%B0%E1%BB%9Di-d%C3%B9ng-%C4%91%E1%BB%83-t%E1%BB%91i-%C6%B0u-h%C3%B3a-chi%E1%BA%BFn-d%E1%BB%8Bch feature-reports=b%C3%A1o-c%C3%A1o-t%C3%ADnh-n%C4%83ng h_01HE7SRDXSVAHKBYQK0C71K6AR=b%C3%A1o-c%C3%A1o-t%C3%ADnh-n%C4%83ng h_01HE7SRDXSFWMVY61NBYFQ4XSM=postbacks postback-reports-available-via-the-export-data-page-and-pull-api=b%C3%A1o-c%C3%A1o-%C4%91%C4%83ng-l%E1%BA%A1i-c%C3%B3-s%E1%BA%B5n-qua-trang-export-data-v%C3%A0-api-pull h_01HE7SRDXS6T4M4CRQN0ZTJETR=b%C3%A1o-c%C3%A1o-%C4%91%C4%83ng-l%E1%BA%A1i-c%C3%B3-s%E1%BA%B5n-qua-trang-export-data-v%C3%A0-api-pull additional-fields-in-postback-reports=c%C3%A1c-tr%C6%B0%E1%BB%9Dng-b%E1%BB%95-sung-trong-b%C3%A1o-c%C3%A1o-%C4%91%C4%83ng-l%E1%BA%A1i h_01HE7SRDXSYBDG0H2QEYBFWSRH=c%C3%A1c-tr%C6%B0%E1%BB%9Dng-b%E1%BB%95-sung-trong-b%C3%A1o-c%C3%A1o-%C4%91%C4%83ng-l%E1%BA%A1i h_01HE7SRDXS8K4MB76WVBCBHASQ=protect360-fraud-and-validation-rules h_01HE7ST20N8ZBFNY2QXW5G44A1=xem-th%C3%AAm" />
