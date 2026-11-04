---
title: API Nhóm người
metadata:
  keywords:
    - API
    - Advertisers
    - Partners
    - Developer
    - Premium
    - Gray
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2020-01-14T07:04:32Z'
  edited_at: '2023-11-24T13:23:03Z'
  id: 360004799057
  locale: vi
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/vi/articles/360004799057
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Sơ lược:** API báo cáo Nhóm người cung cấp cho nhà quảng cáo theo cách có lập trình để lấy dữ liệu Nhóm người. Sử dụng API để tích hợp dữ liệu Nhóm người vào BI và hệ thống tự động hóa tiếp thị.

<div id="per_user" />

<div id="aggregation_type" />

<div id="preferred_timezone" />

<div id="preferred_currency" />

<div id="kpis" />

<div id="groupings" />

<div id="bearer" />

<div id="cohort-api" />

## API báo cáo Nhóm người

API báo cáo Nhóm người được sử dụng để lấy dữ liệu hiệu suất chiến dịch theo nhóm từ nền tảng AppsFlyer. API này có chức năng tương đương với <Anchor target="_blank" href="/marketers/vi/docs/cohort-and-retention-dashboard">bảng điều khiển Nhóm người</Anchor>.

### Những điều cần lưu ý dành cho nhà phát triển

* **Ngày:** Ngày hoặc phạm vi ngày đề cập đến ngày có giá trị lâu dài (<Anchor target="_blank" href="/marketers/vi/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV)</Anchor>, nghĩa là ngày mà người dùng phân bổ (chuyển đổi) chứ không phải ngày của chính hoạt động.
* **Giá trị Boolean:** true hoặc false (phân biệt chữ hoa chữ thường).
* **Lưu lượng truy cập của đại lý minh bạch và không minh bạch:** Nguồn truyền thông của lưu lượng truy cập do đại lý kiểm soát luôn là đại lý chứ không phải nguồn truyền thông ban đầu. Hiện tại, phiên bản UI của nhóm người hoạt động khác.
* **Ứng dụng duy nhất**: API Nhóm người là một giải pháp ứng dụng duy nhất. Điều này trái ngược với bảng điều khiển Nhóm người hỗ trợ nhiều ứng dụng trong một lệnh gọi duy nhất.
* **Tính cập nhật của dữ liệu:** Xem phần [các đặc điểm và hạn chế](/docs/cohort-api#traits-and-limitations).

## Hướng dẫn API

Các phần này chứa thông tin cần thiết để bạn tạo và sử dụng API Nhóm người. 

<div id="cohort-api-facts" />

<Accordion title="Dữ kiện về API Nhóm người">

| Tổng quan | Lệnh gọi API bao gồm đường dẫn, tiêu đề và JSON chứa truy vấn dữ liệu. Dữ liệu được trả về theo mặc định trong tệp CSV. |
| --- | --- |
| Đường dẫn | `https://hq1.appsflyer.com/api/cohorts/v1/data/app/app_id` |
| Thông số đường dẫn  (bắt buộc) | <ul><li>`app_id`: Là mã định danh ứng dụng được dùng trong bảng điều khiển AppsFlyer. Chèn đúng theo mã này như được hiển thị trong bảng điều khiển.</li></ul> |
| Thông số truy vấn<br /><br />(tùy chọn) | Kết quả trả về dưới dạng CSV hoặc JSON. Cấu trúc tệp CSV ở dạng bảng trong khi cấu trúc của bản ghi JSON được định hướng.<ul><li>[Mặc định] <Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360006698277">`csv`</Anchor> [tên tệp](/docs/cohort-api#csv-file-name-structure) phụ thuộc vào truy vấn.</li><li>`json` chứa phần truy vấn và kết quả</li><li>Ví dụ: `format=json`</li><li>`https://hq1.appsflyer.com/api/cohorts/v1/data/app/app_id?format=json`</li></ul> |
| Phương thức HTTP | `POST` |
| Loại nội dung được chấp nhận | `application/json` |
| Ủy quyền | <ul><li>Mã thông báo truy cập trong tiêu đề yêu cầu</li><li>Hãy liên hệ với CSM của bạn để bật API Nhóm người và sau đó <Anchor target="_blank" href="/marketers/vi/docs/managing-appsflyer-tokens">Nhận mã thông báo trong bảng điều khiển</Anchor><ul><li>Mã thông báo tương tự được sử dụng cho tất cả các ứng dụng trong tài khoản</li></ul></li></ul> |
| Giới hạn ngày | <ul><li>Ngày sớm nhất được hỗ trợ: 730 ngày trước ngày hiện tại. Nghĩa là 2 năm)</li><li>Phạm vi truy vấn tối đa: 60 ngày.</li></ul> |
| Giới hạn tỷ lệ | <ul><li>Giới hạn tần suất lệnh gọi API ở mức 60 lệnh gọi mỗi phút và 50.000 lệnh gọi mỗi ngày cho mỗi tài khoản</li><li>Truy vấn trả về tối đa 30.000 hàng</li></ul> |
| Giá trị Boolean | Luôn viết thường: *true*, *false* |

### Tiêu đề yêu cầu

| Mã khóa | Giá trị | Bắt buộc |
| --- | --- | --- |
| Content-Type | `application/json` | Có |
| Authorization | `Truy cập api_token_placeholder` | Có |
| Chấp nhận | `application/json` | Có |

</Accordion>

<div id="filtering-and-grouping-parameters" />

<Accordion title="Lọc và nhóm thông số">

Sử dụng các thông số bộ lọc sau để có được dữ liệu cần thiết. 

| Tên thông số | Mô tả | Bắt buộc |
| --- | --- | --- |
| <span id="cohort-_type"></span>cohort \_type | Loại phân bổ nhóm người (chuyển đổi) là một trong những loại sau: `user_acquisition`, `retargeting`, `unified`<ul><li>Thống nhất kết hợp hiệu suất của các chiến dịch thu hút người dùng và nhắm mục tiêu lại.</li><li>Nếu một sự kiện được phân bổ cho cả chiến dịch nhắm mục tiêu lại và chiến dịch thu hút người dùng thì chỉ sự kiện nhắm mục tiêu lại mới được đưa vào KPI được trả về, nghĩa là *<Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">is\_primary=true</Anchor>.*</li><li>Định dạng: Chuỗi</li><li>Ví dụ: `"cohort_type": "user_acquisition"`</li></ul> | Có |
| <span id="min_cohort_size"></span>min\_cohort\_size | Kích thước nhóm người tối thiểu được sử dụng để giảm số lượng bản ghi được trả về bằng cách loại trừ các nhóm người có ít người dùng. Điều này có nghĩa là KPI *người dùng* có giá trị bằng hoặc lớn hơn giá trị được chỉ định.<ul><li>Định dạng: Số nguyên</li><li>Giá trị tối thiểu được phép: 1. Không gửi 0 (Không)</li><li>Mặc định: 1</li><li>Ví dụ: `"min_cohort_size": 50`</li></ul> | Không |
| <span id="from"></span>bắt đầu | Giới hạn thấp hơn của phạm vi ngày phân bổ LTV. Ngày sớm nhất được hỗ trợ là 720 ngày trước ngày hiện tại.<ul><li>Định dạng: Chuỗi yyyy-mm-dd</li><li>Ví dụ: `"from": "2020-01-02"`</li></ul> | Có |
| <span id="to"></span>tới | Giới hạn cao hơn của phạm vi ngày phân bổ LTV<ul><li>Số ngày trong phạm vi: 1-31 ngày</li><li>Trong một ngày: các giá trị `bắt đầu` và `kết thúc` sẽ giống nhau.</li><li>Định dạng: yyyy-mm-dd</li><li>Ví dụ: `"from": "2020-01-01", "to": 2020-01-31` là 31 ngày.</li></ul> | Có |
| <span id="granularity"></span>tính chi tiết | Mức độ chi tiết hàng giờ trong 72 giờ trước đó bằng cách đặt  `"granularity": "hour"` và đặt phạm vi `bắt đầu` và `kết thúc` để bao gồm thời gian trong ngày.<ul><li>Định dạng: yyyy-mm-dd hh:mm:ss</li><li>Ví dụ:</li></ul>`"granularity": "hour","from": "2021-12-01 14:00:00", "to": "2021-12-03 11:00:00",` | Không |
| <span id="partial_data"></span>partial\_data | Để tránh làm sai lệnh dữ liệu và hiểu sai Nhóm người trả về dữ liệu của những ngày đầy đủ. Tuy nhiên, dữ liệu của các ngày một phần có thể hữu ích.<br /><br />Số ngày nhóm người hoàn chỉnh cho một truy vấn được tính bằng chênh lệch giữa ngày hôm nay và ngày *kết thúc*.<ul><li>[Mặc định] Nếu false, trả về số ngày đầy đủ.</li><li>Nếu true, tối đa 180 ngày nhóm người sẽ được trả về, bao gồm cả những ngày có dữ liệu không đầy đủ.</li><li>Định dạng: Boolean</li><li>Phiên bản UI nền tảng: false</li></ul>**Ví dụ**: Vào ngày 10 tháng 5, số ngày nhóm người hoàn chỉnh cho người dùng chuyển đổi trong khoảng thời gian từ ngày 1 đến ngày 30 tháng 4 là 10.<ul><li>Nếu false [mặc định], trả về các ngày nhóm người 0-9. Đây là số ngày (10) giữa ngày chuyển đổi cuối cùng và ngày hôm nay.</li><li>Nếu true, sẽ trả về các ngày nhóm người 1-40. Ngày 11-40 chứa dữ liệu một phần và không trả về. Ví dụ, kể từ ngày 20 tháng 4, chỉ có 20 ngày trôi qua, v.v.</li></ul>**Lưu ý**: Dữ liệu một phần chỉ được phép khi loại tổng hợp là tích lũy. | Không |
| <span id="filters"></span>bộ lọc | Lọc dữ liệu và số ngày theo khoảng thời gian sẽ được trả về. Chọn bộ lọc từ [danh sách phương diện bộ lọc](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions).<ul><li>Định dạng: Chuỗi dưới dạng JSON lồng nhau</li><li>**Giới hạn ví dụ đối với các Vị trí địa lý cụ thể:** `"filters": {"geo": "US"}` chỉ bao gồm những người dùng được phân bổ ở Hoa Kỳ.</li><li>**Ví dụ về ngày (nhóm người) theo khoảng thời gian**: Bộ lọc `period` đặt các ngày mà phép đo được trả về. Các giá trị có thể là: 0-180.</li><li>Mặc định: Nếu không đặt bộ lọc khoảng thời gian, các ngày 0-30, 60, 90 và 180 sẽ trả về. [Ví dụ về bộ lọc theo khoảng thời gian](/docs/cohort-api#using-period-filters)</li></ul> | Không |

Sử dụng các thông số nhóm sau để gộp các cột bổ sung và giúp báo cáo của bạn ít chi tiết hơn.

| Tham số | Giá trị | Bắt buộc |
| --- | --- | --- |
| nhóm | <ul><li>Chọn nhóm 1-7 từ [danh sách phương diện nhóm](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions).</li><li>Định dạng: Chuỗi trong một mảng</li><li>Example: `"groupings": ["af_ad", "c", "af_c_id", "af_prt"]`</li></ul> | Có |

</Accordion>

<div id="selecting-and-formatting-kpis" />

<Accordion title="Lựa chọn và định dạng KPI">

* Bảng liệt kê các KPI có sẵn và các chức năng liên quan của chúng. Khi bạn gọi ra một KPI, tất cả các chức năng của API đó sẽ trả về.
* Các KPI sau luôn trả về: người dùng, ecpi và chi phí
* Chọn một KPI bổ sung cho mỗi lệnh gọi.

<table><thead><tr><th> </th><th> </th><th colspan="5">Hàm</th></tr><tr><th rowspan="2">Mặc định/ Tùy chọn </th><th rowspan="2">KPI (Tên phương diện) </th><th>Số đếm</th><th>cvr (tỷ lệ chuyển đổi)</th><th>Xếp hạng</th><th>Tổng</th><th>Người dùng duy nhất</th></tr><tr><th>Số</th><th>Tỷ lệ phần trăm</th><th>Tỷ lệ phần trăm</th><th>Số</th><th>Số</th></tr></thead><tbody><tr><td>Luôn luôn</td><td>người dùng</td><td><span>Y</span></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>Luôn luôn</td><td>ecpi</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td>Luôn luôn</td><td>cost</td><td>-</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td></tr><tr><td>Tùy chọn</td><td><span><code>"event_name"</code>(4) </span></td><td><span>Y</span></td><td><span>Y</span></td><td>-</td><td><span>Y (3)</span></td><td><span>Y</span></td></tr><tr><td>Tùy chọn</td><td>revenue</td><td><span>Y</span></td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td></tr><tr><td>Tùy chọn</td><td>ROAS</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td>Tùy chọn</td><td>roi</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td>Tùy chọn</td><td>sessions</td><td><span>Y</span></td><td>-</td><td><span>Y</span></td><td>-</td><td><span>Y(1)</span></td></tr><tr><td>Tùy chọn</td><td>lượt gỡ cài đặt (2)</td><td><span>Y</span></td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr></tbody><tfoot><tr><td colspan="7"><p>(1) Các phiên duy nhất trả về khi <em>aggregation_type=on_day</em></p><p>(2) Không khả dụng khi cohort_type=unified </p><p>(3) Tổng có nghĩa là tổng doanh thu do sự kiện tạo ra. Trong báo cáo, điều này được biểu thị bằng <span><code>sum_event_name"</code></span></p><p><span>(4) Lưu ý! Tên sự kiện có phân biệt chữ hoa chữ thường</span></p></td></tr></tfoot></table>

| Tham số | Giá trị | Thông số bắt buộc |
| --- | --- | --- |
| kpi | Chọn **một** KPI từ các KPI có sẵn. Trong tương lai, chúng tôi dự định cho phép lựa chọn nhiều KPI.<ul><li>Đối với mỗi KPI được yêu cầu, tất cả các hàm đều được trả về.</li><li>Định dạng: Chuỗi trong một mảng</li><li>Ví dụ A: `"kpis": ["sessions"]`</li><li>Ví dụ B: `"kpis": ["event_name"]`</li></ul> | Có |

<div id="formatting-kpi-functions" />

### Trình bày các hàm KPI

Các thông số định dạng KPI sau đây đặt định dạng của KPI được trả về.

| Tham số | Giá trị | Bắt buộc |
| --- | --- | --- |
| preferred\_currency | Đơn vị tiền tệ doanh thu KPI<ul><li>Nếu true, doanh thu sẽ được trả về bằng cách sử dụng <Anchor target="_blank" href="/marketers/vi/docs/app-settings#localization-currency">đơn vị tiền tệ dành riêng cho ứng dụng</Anchor> được đặt trong nền tảng.</li><li>[Mặc định] Nếu false, kết quả trả về bằng USD.</li><li>Định dạng: Boolean</li><li>Phiên bản UI nền tảng: true</li></ul> | Không |
| preferred\_timezone | **Múi giờ của phạm vi dữ liệu**<ul><li>Nếu true, thời gian được biểu thị bằng <Anchor target="_blank" href="/marketers/vi/docs/app-settings#localization-time-zone">múi giờ dành riêng cho ứng dụng</Anchor> được đặt trong nền tảng.</li><li>[Mặc định] Nếu false, thời gian được biểu thị bằng múi giờ UTC.</li><li>Định dạng: Boolean</li><li>Phiên bản UI nền tảng: true</li></ul> | Không |
| aggregation\_type | <ul><li>`cumulative`</li><li>`on_day`</li></ul>`"aggregation_type": "cumulative"`<br /><br />`Định dạng: Chuỗi` | Có |
| per\_user | Chia chức năng KPI theo số lượng người dùng ứng dụng. Chỉ áp dụng cho các KPI có liên quan.<ul><li>Nếu true, giá trị KPI sẽ được chia theo số lượng người dùng trong nhóm người.</li><li>Nếu false, giá trị KPI sẽ không được chia cho số lượng người dùng.</li><li>Định dạng: Boolean</li><li>Ví dụ, nếu true: tổng doanh thu là $1000, số lượng người dùng ứng dụng là 500, giá trị trả về là $2.</li></ul> | Không |

</Accordion>

<div id="list-of-group-by-and-filter-by-dimensions" />

<Accordion title="Danh sách nhóm theo và lọc theo phương diện">

<table><tbody><tr><th><p>Tên phương diện </p></th><th><p>Giá trị API phương diện</p></th><th><p>Nhóm</p></th><th><p>Bộ lọc</p></th></tr><tr><td><p><span>Quảng cáo</span></p></td><td><p><span>af_ad</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>ID Quảng cáo</span></p></td><td><p><span>af_ad_id</span></p></td><td><p><span>Y</span></p></td><td><span><span>Y</span></span></td></tr><tr><td><p><span>Chiến dịch</span></p></td><td><p><span>c</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>ID Chiến dịch</span></p></td><td><p><span>af_c_id</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Kênh</span></p></td><td><p><span>af_channel</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Nguồn Truyền thông</span></p></td><td><p><span>pid</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Thông số Phụ 1</span></p></td><td><p><span>af_sub1</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Từ khóa</span></p></td><td><p><span>af_keywords</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Đại lý</span></p></td><td><p><span>af_prt</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Loại Chuyển đổi (1) </span></p></td><td><p><span>cohort_type</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>ID Trang</span></p></td><td><p><span>site_id</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Loại Doanh thu (2)</span></p></td><td><p><span>revenue_type</span></p></td><td><p><span><span>x </span></span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Loại Tương tác Được phân bổ (3)</span></p></td><td><p><span>attributed_touch_type</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Bộ quảng cáo</span></p></td><td><p><span>af_adset</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>ID Bộ quảng cáo</span></p></td><td><p><span>af_adset_id</span></p></td><td><p><span>Y</span></p></td><td><span> Y</span></td></tr><tr><td><p><span>Quốc gia</span></p></td><td><p><span>geo</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Ngày (ngày cài đặt/phân bổ lại/tương tác lại trong ngữ cảnh của cohort_type đã chọn) </span></p></td><td><p><span>date</span></p></td><td><p><span>Y</span></p></td><td><span><span>x </span></span></td></tr><tr><td><p>Khoảng thời gian</p></td><td><p><span>period </span><span></span></p><p><a href="./cohort-api#using-period-filters">Giải thích chi tiết</a></p></td><td><p><span><span>x</span></span></p></td><td><p><span>Y</span></p></td></tr><tr><td colspan="4"><p>Lưu ý: </p><p>Tùy chọn phương diện:</p><p>(1) Loại Chuyển đổi:  <span><code>user_acquisition</code>, <code>retargeting</code>(<code>re-engagement</code> và <code>re-attribution</code>), </span><span><code>unified</code></span></p><ul><li> <span>Khi xuất:</span><ul><li><span><code>re-engagement</code> sẽ hiển thị là <code>retargeting</code></span></li><li><span><code>re-attribution</code> sẽ hiển thị là <code>reattr</code></span></li></ul></li></ul><p>(2) Loại Doanh thu: <code>regular</code>, <code>ad_monetization</code><span></span></p> (3) Loại Tương tác Được phân bổ: <code>click</code>, <code>impression</code>, <code>TV</code>, <code>pre-installed</code> </td></tr></tbody></table>

</Accordion>

<div id="curl-example" />

<Accordion title="Ví dụ về Curl">

Ví dụ này chứa lệnh gọi API hoàn chỉnh.

```shell
curl -L -X POST 'https://hq1.appsflyer.com/api/cohorts/v1/data/app/<insert your app_id here>?format=<insert results format here>' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <cohort_api_token_placeholder. Note the token has more than 700 characters.>' \
-H 'Accept: application/json' \
--data-raw '{
    "cohort_type": "user_acquisition",
    "min_cohort_size": 1,
    "preferred_timezone": false,
    "from": "2020-01-01",
    "to": "2020-01-31",
    "filters": {
        "period": [
            0,
            1,
            2,
            10,
            30,
            60
        ],
        "geo": [
            "US",
            "CN"
        ],
        "pid": [
            "Meta ads",
            "googleadwords_int"
        ]
    },
    "preferred_currency": true,
    "aggregation_type": "on_day",
    "per_user": false,    
    "groupings": [
        "pid",
        "date"
    ],
    "kpis": [
        "sessions"
    ]
}'
```

Các tệp mẫu được trả về: <Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360006698277">CSV</Anchor>, <Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360006773078">JSON</Anchor>

</Accordion>

<div id="python-example" />

<Accordion title="Ví dụ về Python">

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("hq1.appsflyer.com")
payload = "{\r\n    \"cohort_type\": \"user_acquisition\",\r\n    \"min_cohort_size\": 1,\r\n    \"preferred_timezone\": false,\r\n    \"from\": \"2020-05-01\",\r\n    \"to\": \"2020-05-10\",\r\n    \"preferred_currency\": true,\r\n    \"aggregation_type\": \"cumulative\",\r\n    \"per_user\": false,   \r\n     \"groupings\": [\r\n               \"pid\",\r\n         \"date\"\r\n        ],\r\n    \"kpis\": [\r\n        \"roas\"\r\n    ]\r\n}"
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer [Enter token here]',
  'Accept': 'application/json',
  'Content-Type': 'application/json'
}
conn.request("POST", "/api/cohorts/v1/data/app/[My App ID here]?format=csv", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

</Accordion>

<div id="use-case-examples" />

<Accordion title="Ví dụ về trường hợp sử dụng">

**Ví dụ 1: Giữ chân**

Tỷ lệ giữ chân nguồn phương tiện (phiên) của người dùng đã cài đặt ứng dụng trong tháng 1 vào ngày 7, 14 và 28

```json
{
  "per_user": false,
  "groupings": [
    "pid"
  ],
  "filters": {
    "period": [
      7, 14, 28
    ]
  },
  "partial_data": false,
  "aggregation_type": "on_day",
  "min_cohort_size": 1,
  "cohort_type": "user_acquisition",
  "from": "2021-01-01",
  "to": "2021-01-30",
  "kpis": [
    "sessions"
  ]
}
```

**Ví dụ 2: Giao dịch mua trong chiến dịch**

Doanh thu sau cài đặt nhóm người của ngày 3 trên mỗi chiến dịch

```json
{  
  "per_user": false,
  "groupings": [
    "c"
  ],
  "filters": {
    "period": [
      3
    ],
    "c":[
        "example_campaign_name"
    ]
  },
  "partial_data": false,
  "aggregation_type": "cumulative",
  "min_cohort_size": 1,
  "cohort_type": "user_acquisition",
  "from": "2021-01-01",
  "to": "2021-01-30",
  "kpis": [
    "Checkout Start"
  ]
}
```

**Ví dụ 3: Hoạt động ngày hôm qua**Người dùng đã chuyển đổi (cài đặt, tương tác lại, phân bổ lại) trong khoảng thời gian chuyển đổi nhất định đã thực hiện hoạt động gì vào ngày hôm qua?

Dữ liệu sử dụng có sẵn qua <Anchor target="_blank" href="/marketers/vi/docs/cohort-analytics-via-data-locker">Nhóm người cho Data Locker</Anchor>. Khoảng thời gian chuyển đổi được giới hạn trong 360 ngày trước đó.

</Accordion>

<div id="additional-information" />

## Thông tin bổ sung

<div id="response-codes-and-troubleshooting" />

<Accordion title="Mã phản hồi và khắc phục sự cố">

| Mã phản hồi | Nội dung | Nhận xét |
| --- | --- | --- |
| 200 | OK | Dữ liệu hợp lệ được trả về |
| 200 | OK | <ul><li>Không có dữ liệu được trả về<ul><li>Truy vấn hợp lệ nhưng không tìm thấy dữ liệu nào phù hợp với truy vấn.</li><li>Kiểm tra đảm bảo phạm vi ngày không bao gồm các ngày trong tương lai.</li><li>Không có mã thông báo nào được gửi trong lệnh gọi.</li></ul></li></ul> |
| 401 | Không được phép | <ul><li>Mã thông báo ủy quyền không đúng định dạng, hãy kiểm tra xem bạn có đang sử dụng đúng mã thông báo hay không, mã thông báo này phải dài hơn 700 ký tự</li></ul> |
| 404 | Không tìm thấy | <ul><li>Loại bỏ mọi vấn đề liên quan đến mạng, tường lửa, v.v.</li><li>Đảm bảo rằng bạn đang sử dụng mã thông báo được phát hành gần đây nhất. Lấy mã thông báo hiện hành từ bảng điều khiển.</li><li>Đảm bảo rằng Ứng dụng được chỉ định trong đường dẫn được phép sử dụng API Nhóm người. Có nghĩa là nó là một phần của gói đăng ký. Quản trị viên tài khoản AppsFlyer có thể kiểm tra điều này trong Gói của tôi.</li></ul> |
| 422 | Thực thể không thể xử lý | Những lý do phổ biến đối với mã lỗi này là:<ul><li>Đảm bảo rằng yêu cầu được chứa trong JSON và không được gửi dưới dạng thông số truy vấn.</li><li>Đảm bảo rằng JSON được định dạng phù hợp với tài liệu này.</li><li>Ngày không hợp lệ</li></ul> |

</Accordion>

<div id="csv-file-name-structure" />

<Accordion title="Cấu trúc tên tệp CSV">

Tên được phân bổ cho tệp CSV trả về được tạo từ truy vấn API. Cấu trúc được trình bày chi tiết trong bảng sau.

**Tên tệp CSV mẫu**

```
cohort_aggregation_type_per_user_kpi_report_app_id_from_to_timezone_currency_hash.csv
```

| Biến | Những giá trị có thể có |
| --- | --- |
| aggregation\_type | <ul><li>*on\_day*</li><li>*cumulative*</li></ul> |
| per\_user | <ul><li>*per\_user*</li><li>false: Rỗng</li></ul> |
| kpi | Ví dụ: sessions |
| app\_id | Id ứng dụng được yêu cầu |
| từ | Ngày **bắt đầu**: định dạng *yyyy-mm-dd* |
| tới | Ngày **kết thúc**: định dạng *yyyy-mm-dd* |
| múi giờ | Mặc định múi giờ UTC |
| tiền tệ | Mặc định mã tiền tệ USD |
| hash | Độ dài chuỗi băm chữ và số=5 |

</Accordion>

<div id="using-period-filters" />

<Accordion title="Sử dụng bộ lọc khoảng thời gian">

Khoảng thời gian đề cập đến ngày sau phân bổ, trong đó khoảng thời gian 0 là ngày phân bổ. Ví dụ, người dùng cài đặt ứng dụng vào ngày 1 tháng 1. Đây là ngày phân bổ. Giao dịch mua được thực hiện vào khoảng thời gian 0 có nghĩa là giao dịch được thực hiện vào ngày 1 tháng 1. Giao dịch mua được thực hiện vào khoảng thời gian 3 có nghĩa là giao dịch mua đó được thực hiện vào ngày 4 tháng 1. Tương tự, người dùng cài đặt vào ngày 11 tháng 1 thì đây là khoảng thời gian 0. Giao dịch mua được thực hiện vào ngày 14 tháng 1 sẽ là khoảng thời gian 3.

Nếu phạm vi ngày báo cáo của bạn là từ ngày 1 tháng 1 đến ngày 11 tháng 1 thì những người dùng được phân bổ (đã cài đặt) trong khoảng thời gian này sẽ được đưa vào báo cáo. Không đưa vào các dữ liệu khác.

* Giá trị của khoảng thời gian có thể là một hoặc nhiều giá trị từ 0-180 sau đây. Ví dụ: 0, 1, 2, 30, 180.
* Nếu không có khoảng thời gian nào được chỉ định, thì các giá trị mặc định là 0, 1, 2, v.v. cho đến 30, 60, 90 và 180 sẽ được trả về.

<div id="example-period-filter" />

> 📄 **Ví dụ về bộ lọc khoảng thời gian**
>
> * Ví dụ này chứa các thông số truy vấn JSON, dữ liệu thô và tệp CSV kết quả.
> * Truy vấn *lọc khoảng thời gian* 0, 1 và 2 và KPI được chọn là *revenue*.
> * Kết quả là dữ liệu trả về chứa:
>   * Các thước đo về người dùng, chi phí và ecpi luôn trả về
>   * Các phép đo doanh thu bao gồm tổng và số lượng cho từng khoảng thời gian, nghĩa là các khoảng thời gian 0, 1 và 2.
>
> **Truy vấn**
>
> ```json
> {
>     "cohort_type": "user_acquisition",
>     "min_cohort_size": 1,
>     "preferred_timezone": false,
>     "from": "2019-12-01",
>     "to": "2020-01-01",
>     "filters": {
>         "period": [
>             0,
>             1,
>             2
>         ]
>     },
>     "aggregation_type": "on_day",
>     "per_user": false,
>     "groupings": [
>         "pid"
>     ],
>     "kpis": [
>         "revenue"
>     ]
> }
> ```
>
> **Dữ liệu thô**
>
> **![mceclip1.png](https://files.readme.io/846aade481d3b5fa72536817533bc3edad721f1ce6015edcb48bd500461342b9-32131110606865.png)**
>
> **Kết quả**
>
> ![mceclip0.png](https://files.readme.io/c284e5133e4e811b9416c850e399ddefb3c5bfcfcf879f469556b7a6bc0062c6-32131110607249.png)

</Accordion>

<div id="user-interface-mapping-to-api-parameters" />

<Accordion title="Ánh xạ giao diện người dùng tới các thông số API">

Các số liệu tiếp theo ánh xạ giao diện người dùng phân tích Nhóm người với các thông số API. Hai giải pháp - API và giao diện người dùng tương tự nhau nhưng không tương đồng.

Phiên bản API có các tùy chọn bổ sung sau:

* Lựa chọn tiền tệ
* Lựa chọn múi giờ
* Lọc theo khoảng thời gian

[![CohortMapping.jpg](https://files.readme.io/28b5973a6c476407f342cbc55dbf03162fdd3047d4fd9b93b78a6de8dff11cdb-360012218018.jpg)](https://files.readme.io/28b5973a6c476407f342cbc55dbf03162fdd3047d4fd9b93b78a6de8dff11cdb-360012218018.jpg) [![Cohortmapping2.jpg](https://files.readme.io/59f2e9fd5120b7efbb81a937a42ee4a8145fd7ae74ddf855ec6ba13f061ba6c2-360006378018.jpg)](https://files.readme.io/59f2e9fd5120b7efbb81a937a42ee4a8145fd7ae74ddf855ec6ba13f061ba6c2-360006378018.jpg)

Điểm khác biệt giữa các loại tổng hợp

![CohortRevnueCumulative.jpg](https://files.readme.io/1c9ca17e217a941e989556637d4397147bac9d1ab65e7485a10c0757a70dec41-360006379038.jpg)

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Nhận xét |
| --- | --- |
| Truy cập mạng quảng cáo | Không. <Anchor target="_blank" href="/partners/vi/docs/access-to-aggregated-analytics-tools-for-api-partners">Đối tác quản lý chiến dịch</Anchor> có thể sử dụng API nếu nhà quảng cáo cấp quyền. |
| Truy cập đại lý | Không |
| Tính minh bạch của đại lý | Không được hỗ trợ |
| Múi giờ cụ thể theo ứng dụng | Có |
| Tiền tệ cụ thể theo ứng dụng | Có |
| Hạn chế về kích thước | Không |
| Giới hạn tỷ lệ | Giới hạn tần suất lệnh gọi API: 60 lệnh gọi mỗi phút cho mỗi tài khoản |
| Dữ liệu tự nhiên | Có sẵn |
| Dữ liệu không tự nhiên | Có sẵn |
| Giới hạn dữ liệu chi phí | <ul><li>Dữ liệu chi phí chỉ dành cho các chiến dịch có ít nhất 1 lượt cài đặt được ghi nhận.</li><li>AppsFlyer không báo cáo dữ liệu chi phí cho các từ khóa chứa chữ hoa trong báo cáo nhóm người hoặc API nhóm người</li><li>Bạn không thể kết hợp một số phương án kết hợp nhóm với chi phí. Ví dụ, Meta ads có thể có nhóm vị trí địa lý hoặc nhóm kênh nhưng không thể có cả hai. Phương án kết hợp chính xác nhóm phụ thuộc vào mạng quảng cáo.</li></ul> |
| Tính cập nhật của dữ liệu | Tính cập nhật của dữ liệu phụ thuộc vào [*partial\_data*](/docs/cohort-api#partial_data) như sau:<ul><li>[Mặc định] Nếu false, <Anchor target="_blank" href="/marketers/vi/docs/about-data-freshness-and-timezone-support#daily-processing">Hàng ngày</Anchor></li><li>Nếu true, <Anchor target="_blank" href="/marketers/vi/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">Liên tục (thời gian thực)</Anchor></li><li>Số liệu chi phí và lượt gỡ cài đặt cập nhật hàng ngày trong mọi phiên bản</li></ul> |
| Dữ liệu lịch sử | Nhóm người hàng ngày: 2 năm |
| Quyền truy cập tài khoản của người dùng | Mã thông báo ủy quyền có sẵn cho người dùng quản trị viên trong bảng điều khiển |
| Doanh thu quảng cáo | Đối với sự kiện af\_ad\_revenue, số liệu người dùng duy nhất không khả dụng khi loại dữ liệu hợp nhất là "on day" cho các ngày từ ngày 5 tháng 10 năm 2022-ngày 16 tháng 2 năm 2023. |
| Nhóm hàng tuần và hàng tháng | Nhóm phương diện hàng tuần và hàng tháng không có sẵn đối với API Nhóm người. Sử dụng bảng điều khiển Nhóm người. |
| API Nhóm người | <ul><li>Khoảng thời gian chuyển đổi được gọi là 0 (Giờ 0 hoặc Ngày 0). Khoảng thời gian tiếp theo sau chuyển đổi được gọi là 1 (Giờ 1 hoặc Ngày 1), v.v.</li><li>Trong AppsFlyer, khoảng thời gian của nhóm người không tính đến nhãn thời gian lượt cài đặt cụ thể. Thay vào đó, số giờ của nhóm người được làm tròn xuống giờ gần nhất và ngày của nhóm người được dựa trên ngày theo lịch. Điều này có thể gây ra sự sai khác khi so sánh dữ liệu nhóm người AppsFlyer với dữ liệu nhóm người của các mạng khác, trong đó tất cả các khoảng thời gian của nhóm người được xác định theo nhãn thời gian cài đặt cụ thể (có nghĩa là một giờ là nhãn thời gian sau khi cài đặt 60 phút, một ngày là nhãn thời gian sau khi cài đặt khoảng thời gian 24 giờ sau cài đặt, v.v.).</li></ul> |

</Accordion>

<div data-zendesk-anchors="cohort-reporting-api=api-b%C3%A1o-c%C3%A1o-nh%C3%B3m-ng%C6%B0%E1%BB%9Di 01H7WFZR41YAQX4MFPBMJD1MBP=api-b%C3%A1o-c%C3%A1o-nh%C3%B3m-ng%C6%B0%E1%BB%9Di considerations-for-developers=nh%E1%BB%AFng-%C4%91i%E1%BB%81u-c%E1%BA%A7n-l%C6%B0u-%C3%BD-d%C3%A0nh-cho-nh%C3%A0-ph%C3%A1t-tri%E1%BB%83n 01H7WFZR414KXJBQS563VNKPXR=nh%E1%BB%AFng-%C4%91i%E1%BB%81u-c%E1%BA%A7n-l%C6%B0u-%C3%BD-d%C3%A0nh-cho-nh%C3%A0-ph%C3%A1t-tri%E1%BB%83n api-instructions=h%C6%B0%E1%BB%9Bng-d%E1%BA%ABn-api 01H7WFZR41SNPGFKRH6J5DJG95=h%C6%B0%E1%BB%9Bng-d%E1%BA%ABn-api 01H7WFZR4184TKQYEC4Q10D9HH=cohort-api-facts request-headers=ti%C3%AAu-%C4%91%E1%BB%81-y%C3%AAu-c%E1%BA%A7u 01H7WFZR42NHX3N1V72VKP06ZR=ti%C3%AAu-%C4%91%E1%BB%81-y%C3%AAu-c%E1%BA%A7u 01H7WFZR42H3CA0CSB4E3XED3H=filtering-and-grouping-parameters 01H7WFZR42XV4JY46GY11KT3CF=selecting-and-formatting-kpis presentation-of-kpi-functions=tr%C3%ACnh-b%C3%A0y-c%C3%A1c-h%C3%A0m-kpi 01H7WFZR43HFF65TSWG1AN0JTB=tr%C3%ACnh-b%C3%A0y-c%C3%A1c-h%C3%A0m-kpi 01H7WFZR43BJ8E6KVHSGV4CDDP=list-of-group-by-and-filter-by-dimensions 01H7WFZR448CBBZ3V7RT0PF072=curl-example 01H7WFZR44RBVB9Q6VZPG1EWNX=python-example 01H7WFZR44H0G3QCBRTRQ5Y0HD=use-case-examples additional-information=th%C3%B4ng-tin-b%E1%BB%95-sung 01H7WFZR448RNM8539DD8WCBH0=th%C3%B4ng-tin-b%E1%BB%95-sung 01H7WFZR441022SK7BQB00F0BJ=response-codes-and-troubleshooting 01H7WFZR443YKCSJTHJ9W6H2S3=csv-file-name-structure 01H7WFZR440NTXWWQ2T4P2ANWK=using-period-filters 01H7WFZR44RCXA56CXSCEZ0KXH=v%C3%AD-d%E1%BB%A5-v%E1%BB%81-b%E1%BB%99-l%E1%BB%8Dc-kho%E1%BA%A3ng-th%E1%BB%9Di-gian 01H7WFZR45QFHJWXZAAX2HRXQ2=user-interface-mapping-to-api-parameters 01H7WFZR45VC96KYW1W9A8PBFT=traits-and-limitations" />
