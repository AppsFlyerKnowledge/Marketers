---
title: Tổng quan báo cáo hợp nhất và phân tích
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
    - Ad Networks
  created_at: '2020-02-04T09:38:14Z'
  edited_at: '2023-11-01T10:21:57Z'
  id: 360005437257
  locale: vi
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/vi/articles/360005437257
---
> **Khái quát:** Mô tả và so sánh các báo cáo phân bổ hợp nhất và phân tích, các công cụ và API có sẵn.

## Báo cáo hiệu suất hợp nhất và phân tích—các công cụ và báo cáo

Các công cụ phân tích hợp nhất trong nền tảng này cung cấp cho nhà quảng cáo các số liệu để họ có thể đánh giá hiệu suất của các ứng dụng, chiến dịch và người dùng của họ.

Các công cụ khác nhau về cách trình bày dữ liệu. Ví dụ: bảng điều khiển Tổng quan cung cấp số liệu giá trị vòng đời của chiến dịch (LTV) trong khi bảng điều khiển Nhóm người được sử dụng để phân tích mức độ thu hút của người dùng theo thời gian.

Các công cụ được trình bày chi tiết trong bài viết này liên quan đến dữ liệu có thể được xuất từ nền tảng. Sử dụng bảng so sánh công cụ dưới đây để nắm được chức năng chính và điểm khác biệt giữa các công cụ.

<div id="toolapi-comparison" />

<Accordion title="So sánh phương thức báo cáo">

Bảng dưới đây mô tả các phương thức báo cáo và bảng điều khiển khác nhau để nhận dữ liệu hợp nhất.

**[Tải xuống bảng dưới dạng tập tin CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vSICicxcvD0996RT59fTLDJvdGUKxqPqr47f5SMD8BmsbZtrWIoxRxJEo7tAXTBBmnIbiH097VtK6L9/pub?output=xlsx) để xem các trường bổ sung diễn giải các thông số kĩ thuật và giới hạn khác nhau nhằm giúp bạn so sánh và đối chiếu các phương thức báo cáo khác nhau.**

Các trường thông số kỹ thuật bổ sung trong tập tin CSV có thể tải xuống bao gồm:

* <Anchor target="_blank" href="/marketers/vi/docs/about-data-freshness-and-timezone-support">Data freshness</Anchor>: Khoảng thời gian giữa hai lần xuất hiện của sự kiện và dữ liệu có sẵn thông qua phương thức báo cáo.
* <Anchor target="_blank" href="/marketers/vi/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV/activity</Anchor>: Liệu dữ liệu là LTV hay hoạt động.
* <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide">Retargeting</Anchor>: Liệu dữ liệu nhắm mục tiêu lại (thu hút lại và phân bổ lại) có được hiển thị không.
* <Anchor target="_blank" href="/marketers/vi/docs/measure-reinstalls#attributed-to-the-first-install">Re-install events attribution to first install</Anchor>: Liệu các sự kiện sau khi cài đặt lại có thể được phân bổ cho lượt cài đặt ban đầu không.
* <Anchor target="_blank" href="/partners/vi/docs/about-agency-accounts#tính-minh-bạch-của-agency">Agency transparency</Anchor>: Liệu các nhà tiếp thị có thể nhìn thấy tên của nguồn truyền thông gốc đối với lưu lượng truy cập từ đại lý hay không.
* <Anchor target="_blank" href="/marketers/vi/docs/about-data-freshness-and-timezone-support#date-and-timezone-principles">Timezone</Anchor>: Múi giờ nào (UTC hay theo múi giờ ứng dụng chọn) được sử dụng để hiển thị dữ liệu.
* <Anchor target="_blank" href="/marketers/vi/docs/measure-reinstalls#unattributed-organic-inapps">Unattributed events</Anchor>: Liệu các sự kiện không được phân bổ sau khi cài đặt lại có hiển thị hay không.
* <Anchor target="_blank" href="/marketers/vi/docs/campaign-name-changes?">Campaign name changes</Anchor>: Liệu bạn có thể đổi tên chiến dịch mà không hiển thị tên trùng lặp hay không.

| Phương thức báo cáo | Mô tả |
| --- | --- |
| Bảng điều khiển tổng quan | Giá trị vòng đời (LTV) của những người dùng cài đặt, thu hút lại hoặc phân bổ lại trong phạm vi ngày đã chọn. |
| <Anchor target="_blank" href="/marketers/vi/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor>  <br />(Tính năng cao cấp) | LTV, hoạt động, giữ lại người dùng, nhóm người và hiệu suất của chiến dịch Protect360 được chọn theo API, dưới định dạng CSV hoặc JSON. |
| <Anchor target="_blank" href="/marketers/vi/docs/pull-api-aggregate-data">API Pull - báo cáo hợp nhất</Anchor> | Giá trị vòng đời (LTV) của những người dùng cài đặt, thu hút lại hoặc phân bổ lại trong các tập tin CSV. Dữ liệu UA tách biệt với dữ liệu nhắm mục tiêu lại; không có một lựa chọn hợp nhất. |
| <Anchor target="_blank" href="/marketers/vi/docs/aggregated-data-export-page">Trang Export data - báo cáo hợp nhất</Anchor> | Giá trị vòng đời (LTV) của những người dùng cài đặt, thu hút lại hoặc phân bổ lại trong các tập tin CSV. Dữ liệu UA tách biệt với dữ liệu nhắm mục tiêu lại; không có một lựa chọn hợp nhất. |
| <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN</Anchor>  <br /><Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">tổng quan</Anchor> | Các số liệu được báo cáo qua đăng lại SKAN trên thiết bị iOS và các điểm dữ liệu bổ sung trong các khung thời gian đo lường người dùng ban đầu. |
| <Anchor target="_blank" href="/marketers/vi/docs/skan-aggregated-performance-report-api">SKAN</Anchor>  <br /><Anchor target="_blank" href="/marketers/vi/docs/skan-aggregated-performance-report-api">API dữ liệu hợp nhất</Anchor> | Các số liệu được báo cáo qua đăng lại SKAN trên thiết bị iOS và các điểm dữ liệu bổ sung trong các khung thời gian đo lường người dùng ban đầu. |
| <Anchor target="_blank" href="/marketers/vi/docs/protect360-dashboard">Bảng điều khiển của Protect360</Anchor> | Số liệu và thông tin chi tiết liên quan đến lưu lượng truy cập gian lận.  <br />Dữ liệu dựa trên LTV cho lượt cài đặt và dữ liệu dựa trên hoạt động cho các sự kiện trong ứng dụng. |
| <Anchor target="_blank" href="/marketers/vi/docs/activity-dashboard">Bảng điều khiển hoạt động</Anchor> | Hoạt động trong ứng dụng, mức độ thu hút và số liệu trong ứng dụng trong phạm vi ngày đã chọn. |
| Bảng điều khiển sự kiện | Số liệu hiệu suất của sự kiện trong ứng dụng trên các nguồn truyền thông dựa vào dữ liệu LTV của những người dùng đã cài đặt ứng dụng trong phạm vi ngày đã chọn. |
| Bảng điều khiển giữ lại người dùng | Số liệu (phiên) thu hút người dùng duy nhất cho mỗi ngày sau khi cài đặt. |
| <Anchor target="_blank" href="/marketers/vi/docs/cohort-and-retention-dashboard">Bảng điều khiển nhóm người</Anchor> | Các số liệu người dùng khác nhau cho mỗi ngày sau khi cài đặt. |
| <Anchor target="_blank" href="/marketers/vi/docs/cohort-api">Cohort API</Anchor>  <br />(Tính năng cao cấp) | Các số liệu người dùng khác nhau cho mỗi ngày sau khi cài đặt. |
| <Anchor target="_blank" href="/marketers/vi/docs/cohort-analytics-via-data-locker">Cohort Data Locker</Anchor>  <br />(Tính năng cao cấp) | Các số liệu người dùng khác nhau cho mỗi ngày sau khi cài đặt. |
| <Anchor target="_blank" href="/marketers/vi/docs/custom-dashboards">Bảng điều khiển tùy chỉnh</Anchor> | Bảng điều khiển tùy chỉnh với số liệu thu hút người dùng LTV. |
| <Anchor target="_blank" href="/marketers/vi/docs/pivot-table-user-metrics">Pivot reports</Anchor>  <br />(Tính năng cao cấp) | LTV, hoạt động, giữ lại người dùng và KPI hiệu suất chiến dịch Protect360 được chọn, trong bảng điều khiển hoặc qua CSV. |
| <Anchor target="_blank" href="/marketers/vi/docs/set-up-and-use-roi360-cost-etl-reports">Chi phí ETL</Anchor> | Dữ liệu về chi phí của chiến dịch với tính chi tiết nhất có sẵn cho mỗi nguồn truyền thông. |
| Báo cáo mức sử dụng | Sự kết hợp của tất cả tính năng dựa trên mức sử dụng trong AppsFlyer tác động đến nghĩa vụ hợp đồng trong các khung chu kỳ thanh toán. |

</Accordion>

<div id="cohort-flavors" />

<Accordion title="Các biến thể của Nhóm người">

Cohort có sẵn một số *biến thể* khác nhau bao gồm <Anchor target="_blank" href="/marketers/vi/docs/cohort-and-retention-dashboard">Bảng điều khiển Nhóm người</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/cohort-api">API Nhóm người</Anchor> và <Anchor target="_blank" href="/marketers/vi/docs/cohort-analytics-via-data-locker">Phân tích Nhóm người thông qua Data Locker.</Anchor> Bảng dưới đây liệt kê những điểm khác biệt.

| Đặc điểm | Phân tích Nhóm người trong Data Locker | Bảng điều khiển Nhóm người | API Nhóm người |
| --- | --- | --- | --- |
| Nhiều hoặc một ứng dụng | Nhiều Dữ liệu được nhóm theo ứng dụng trong một tập tin hoặc được tách thành các tập tin riêng biệt trên một ứng dụng. | Nhiều Hiệu suất được kết hợp hoặc nhóm theo các tùy chọn ứng dụng. | Một |
| Nhóm | Phân cấp chiến dịch và tên sự kiện đầy đủ. Khoảng 20 nhóm | 4 nhóm | 7 nhóm |
| Các số liệu có sẵn | Tất cả số liệu | 1 số liệu có thể chọn và 4 số liệu cố định cho mỗi lượt xem | 1 số liệu có thể chọn và 4 số liệu cố định cho mỗi lệnh gọi |
| Số ngày khả dụng sau khi phân bổ (số ngày của nhóm người) | 365 | 180 | 180 |
| Các hạn chế xuất dữ liệu | Toàn bộ bộ dữ liệu đều có sẵn | Tải xuống thủ công và cài đặt | Tốc độ và kích thước phản hồi bị hạn chế |
| Yêu cầu có thể tùy chỉnh | Không | Có | Có |

</Accordion>

### Báo cáo hành trình của người dùng

* Báo cáo được mô tả có sẵn thông qua trang Xuất dữ liệu hoặc bằng cách sử dụng API Pull hợp nhất.
* Nội dung báo cáo gồm <Anchor target="_blank" href="/marketers/vi/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">Giá trị vòng đời (LTV)</Anchor> nên phạm vi ngày báo cáo liên quan đến ngày phân bổ:
  * Ngày cài đặt cho báo cáo UA và Protect360
  * Phân bổ lại hoặc ngày thu hút lại trong trường hợp báo cáo nhắm mục tiêu lại
* Ngày báo cáo sớm nhất khả dụng là ngày cài đặt ứng dụng đầu tiên.

<div id="ua-ltv-aggregate-data-reports-containing-nonorganic-and-organic-users" />

<Accordion title="Báo cáo dữ liệu hợp nhất UA LTV có chứa người dùng tự nhiên và không tự nhiên">

<table><tbody><tr><th>Tên báo cáo</th><th>Được nhóm theo</th></tr><tr><td>Đối tác (nguồn truyền thông)</td><td>Đại lý, nguồn truyền thông, chiến dịch</td></tr><tr><td>Đối tác theo ngày</td><td>Ngày, đại lý, nguồn truyền thông, chiến dịch</td></tr><tr><td>Hoạt động hàng ngày</td><td>Ngày, đại lý, nguồn truyền thông, chiến dịch</td></tr><tr><td>Địa lý</td><td>Quốc gia, đại lý, nguồn truyền thông, chiến dịch</td></tr><tr><td>Địa lý theo ngày</td><td>Ngày, quốc gia, đại lý, nguồn truyền thông, chiến dịch</td></tr><tr><td>KPI phân bổ lượt xem hết (VTA)</td><td><p><a href="./pull-api-aggregate-data" target="_blank">Báo cáo VTA có sẵn bằng API Pull</a></p></td></tr><tr><td colspan="2"> <strong>Lưu ý</strong>: Nếu Meta ads là <em>nguồn truyền thông</em> được chọn thì sẽ có thêm các cột: Adgroup ID, Adgroup name, Adset ID, Adset name</td></tr></tbody></table>

Các trường ngày trong tệp tin CSV có định dạng yyyy-mm-dd (năm-tháng-ngày). Khi bạn mở tệp tin CSV trong Excel, các trường ngày được định dạng bằng cách sử dụng cài đặt ngày và giờ của máy tính của bạn. Hãy nhớ chọn cách hiển thị ngày thích hợp trong <Anchor target="_blank" href="https://support.office.com/en-us/article/format-a-date-the-way-you-want-8e10019e-d5d8-47a1-ba95-db95123d273e#ID0EAACAAA=Windows">Excel.</Anchor>

#### Ví dụ về báo cáo hợp nhất

[Các ví dụ về báo cáo có trong bảng tính](https://docs.google.com/spreadsheets/d/e/2PACX-1vQmzRons779Dk5QWVoPsOF8E7yJLwNPB1IF87shZr6rcMJLjszlSNIbAMVcdeQLysr8Bc4QAby5QB4u/pub?output=xlsx)

#### Các trường trong báo cáo hợp nhất UA

<table><thead><tr><th rowspan="2">Trường</th><th rowspan="2">Mô tả</th><th colspan="5"><p><strong>Tên báo cáo</strong></p></th></tr><tr><th><p><strong>Đối tác (nguồn truyền thông)</strong></p></th><th><p><strong>Đối tác theo ngày</strong></p></th><th><p><strong>Hằng ngày</strong></p></th><th><p><strong>Địa lý</strong></p></th><th><p><strong>Địa lý theo ngày</strong></p></th></tr></thead><tbody><tr><td><p>Quốc gia</p></td><td>Quốc gia cài đặt</td><td> </td><td> </td><td> </td><td><p>✓</p></td><td> ✓</td></tr><tr><td><p>Ngày</p></td><td><p>Ngày phân bổ</p></td><td> </td><td><p>✓</p></td><td> </td><td> </td><td><p>✓</p></td></tr><tr><td><p>Đại lý/PMD (af_prt)</p></td><td><p>Tên đại lý/đối tác</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Nguồn Truyền thông (pid)</p></td><td><p>Nguồn truyền thông mang đến người dùng (pid=nguồn truyền thông)</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Chiến dịch</p></td><td><p>Tên chiến dịch</p><p>(c= tên chiến dịch)</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>ID Chiến dịch</p></td><td><p>ID chiến dịch của Meta </p></td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td></tr><tr><td><p>ID nhóm quảng cáo</p></td><td><p>ID nhóm quảng cáo hoặc ID quảng cáo của Meta</p></td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td></tr><tr><td><p>Tên nhóm quảng cáo</p></td><td><p>Nhóm quảng cáo của Meta</p></td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td></tr><tr><td><p>ID Bộ quảng cáo</p></td><td><p>ID bộ quảng cáo của Meta</p></td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td></tr><tr><td><p>Tên bộ quảng cáo</p></td><td><p>Tên bộ quảng cáo của Meta</p></td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td><td>Chỉ Meta ads</td></tr><tr><td><p>ARPU</p></td><td><p>Doanh thu trung bình trên mỗi người dùng</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td>✓</td><td><p>✓</p></td></tr><tr><td><p>eCPI trung bình</p></td><td><p>eCPI trung bình</p></td><td> </td><td><p>✓</p></td><td> </td><td> </td><td> </td></tr><tr><td><p>Lượt nhấp</p></td><td><p>Số lượt nhấp</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Tỷ lệ Chuyển đổi</p></td><td><p>Số lượt cài đặt/số lượt nhấp</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>CTR</p></td><td><p>Tỷ lệ nhấp</p></td><td> </td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td> </td></tr><tr><td><p>`{your event name}(Người dùng duy nhất)</p></td><td><p>Số người dùng duy nhất đã thực hiện sự kiện</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>{your event name} (Bộ đếm sự kiện)</p></td><td><p>Bộ đếm sự kiện</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>{your event name}` (Doanh thu bằng XXX)</p></td><td><p>Doanh thu sự kiện bằng XXX trong đó XXX là loại tiền tệ được chọn bởi ứng dụng</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Lượt hiển thị</p></td><td><p>Số lượt hiển thị</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td> </td><td> </td></tr><tr><td><p>Lượt cài đặt</p></td><td><p>Số lượt cài đặt</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Người dùng Trung thành</p></td><td><p>[mặc định] Người dùng mở ứng dụng hơn 3 lần</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Người dùng Trung thành/Lượt cài đặt</p></td><td><p>Tỷ lệ người dùng trung thành</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td> </td><td> </td></tr><tr><td><p>ROI</p></td><td><p>Lợi tức đầu tư</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td> </td><td> </td></tr><tr><td><p>Các phiên</p></td><td><ul><li>Số lần mở ứng dụng không tự nhiên</li><li>Các phiên tự nhiên và không tự nhiên có sẵn trong phân tích Nhóm người</li></ul></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Tổng Chi phí</p></td><td><p>-</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td> </td><td> </td></tr><tr><td><p>Tổng doanh thu</p></td><td><p>Tổng doanh thu tạo ra từ nguồn truyền thông và chiến dịch</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td colspan="7"><p> <strong>Lưu ý:</strong> Các cột hiển thị "Chỉ Meta ads" được đưa vào khi chọn Meta ads làm nguồn truyền thông duy nhất.</p></td></tr></tbody></table>

</Accordion>

<div id="retargeting" />

<Accordion title="Nhắm mục tiêu lại">

* Báo cáo nhắm mục tiêu lại bao gồm những người dùng đã thu hút với một <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide#retargeting-reports-and-raw-data">chiến dịch nhắm mục tiêu lại</Anchor> và thu hút lại hoặc phân bổ lại.
* Trong báo cáo nhắm mục tiêu lại, không có sự phân biệt giữa người dùng tự nhiên và người dùng không tự nhiên.
* Để nhận báo cáo nhắm mục tiêu lại qua API Pull, hãy thêm thông số *& reattr=true* vào URI báo cáo hiệu suất.

#### Báo cáo hợp nhất nhắm mục tiêu lại LTV

| Tên báo cáo | Được nhóm theo |
| --- | --- |
| Đối tác (nguồn truyền thông) | Đại lý, nguồn truyền thông, chiến dịch |
| Đối tác theo ngày | Ngày, đại lý, nguồn truyền thông, chiến dịch |
| Hoạt động theo ngày | Ngày, đại lý, nguồn truyền thông, chiến dịch |
| Quốc gia | Quốc gia, đại lý, nguồn truyền thông, chiến dịch |
| Quốc gia theo ngày | Ngày, quốc gia, đại lý, nguồn truyền thông, chiến dịch |

#### Báo cáo hợp nhất nhắm mục tiêu lại LTV

| Trường | Mô tả | Đối tác | Hàng ngày | Đối tác theo ngày | Địa lý theo ngày | Địa lý |
| --- | --- | --- | --- | --- | --- | --- |
| Ngày | Ngày chuyển đổi | - | - | ✓ | ✓ | - |
| Quốc gia |  | - | ✓ |  | ✓ | ✓ |
| Đại lý/PMD (af\_prt) | Tên đại lý/đối tác | ✓ | ✓ | ✓ | ✓ | ✓ |
| Nguồn Truyền thông (pid) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Chiến dịch (c) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Lượt nhấp |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Lượt chuyển đổi |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Loại chuyển đổi | Phân bổ lại hoặc thu hút lại | ✓ | ✓ | ✓ | ✓ | ✓ |
| Tỷ lệ Chuyển đổi | Lượt chuyển đổi/lượt nhấp | ✓ | ✓ | ✓ | ✓ | ✓ |
| Các phiên |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Người dùng Trung thành |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Người dùng Trung thành/Lượt cài đặt |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Tổng Chi phí |  | - | - | - | - | - |
| eCPI trung bình |  | - | - | - | - | - |
| Tổng doanh thu |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| ROI |  | - | - | - | - | - |
| ARPU |  | ✓ | ✓ | ✓ | - | ✓ |

</Accordion>

## Báo cáo tính năng

<div id="skadnetwork" />

<Accordion title="SKAdNetwork">

<Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide#reporting-options">Báo cáo hợp nhất của SKAdNetwork</Anchor>

</Accordion>

<div id="protect360-blocked-fraud" />

<Accordion title="Protect360—gian lận bị chặn">

![](https://theme.zdassets.com/theme_assets/245528/ffbbc473bb0e74b9fb636ed735f69e9af6a25a18.png)

* Các báo cáo hợp nhất về gian lận bị chặn cung cấp thông tin chi tiết về các sự kiện bị chặn bởi <Anchor target="_blank" href="/marketers/vi/docs/protect360-anti-fraud-guide">Protect360</Anchor>.
* Các báo cáo có sẵn thông qua API Pull. Các báo cáo này không có sẵn trên trang Export Data.
* Phạm vi ngày liên quan đến ngày cài đặt.

#### Báo cáo Protect360 hợp nhất có sẵn thông qua API Pull

| Tên báo cáo |
| --- |
| Đối tác (nguồn truyền thông) |
| Đối tác theo ngày |
| Địa lý |
| Địa lý theo ngày |
| Báo cáo chiến dịch của đối tác |

**Hạn chế:** Lý do chặn mà **Bot** hiển thị ngay cả trong trường hợp lý do là **phiên bản ứng dụng** hoặc **thiếu customer user id**.

</Accordion>

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/configuring-meta-campaign-management-partners">Cấu hình đối tác quản lý chiến dịch Meta</Anchor>
> * <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">Tổng quan về báo cáo dữ liệu thô</Anchor>

<div data-zendesk-anchors="aggregated-and-analytics-performance-reporting%E2%80%94tools-and-reports=b%C3%A1o-c%C3%A1o-hi%E1%BB%87u-su%E1%BA%A5t-h%E1%BB%A3p-nh%E1%BA%A5t-v%C3%A0-ph%C3%A2n-t%C3%ADchc%C3%A1c-c%C3%B4ng-c%E1%BB%A5-v%C3%A0-b%C3%A1o-c%C3%A1o 01EWA9VQ2HH93525BMK6WN0P6S=b%C3%A1o-c%C3%A1o-hi%E1%BB%87u-su%E1%BA%A5t-h%E1%BB%A3p-nh%E1%BA%A5t-v%C3%A0-ph%C3%A2n-t%C3%ADchc%C3%A1c-c%C3%B4ng-c%E1%BB%A5-v%C3%A0-b%C3%A1o-c%C3%A1o 01ED4D7W8B53Q81G7PXQH8ADE2=toolapi-comparison h_01HDNYFR9KBX2KP75K1FAZC2Q7=cohort-flavors user-journey-reports=b%C3%A1o-c%C3%A1o-h%C3%A0nh-tr%C3%ACnh-c%E1%BB%A7a-ng%C6%B0%E1%BB%9Di-d%C3%B9ng 01ED4D7W8CVAQ9V2GCEX1G6KD7=b%C3%A1o-c%C3%A1o-h%C3%A0nh-tr%C3%ACnh-c%E1%BB%A7a-ng%C6%B0%E1%BB%9Di-d%C3%B9ng h_01HDNYFR9KBMWAFXDNNJN8VA2X=ua-ltv-aggregate-data-reports-containing-nonorganic-and-organic-users examples-of-aggregate-reports=v%C3%AD-d%E1%BB%A5-v%E1%BB%81-b%C3%A1o-c%C3%A1o-h%E1%BB%A3p-nh%E1%BA%A5t 01ED4D7W8C3ZNBYR3CMHJF3QSE=v%C3%AD-d%E1%BB%A5-v%E1%BB%81-b%C3%A1o-c%C3%A1o-h%E1%BB%A3p-nh%E1%BA%A5t fields-in-ua-aggregate-reports=c%C3%A1c-tr%C6%B0%E1%BB%9Dng-trong-b%C3%A1o-c%C3%A1o-h%E1%BB%A3p-nh%E1%BA%A5t-ua h_01HDNYFR9KTQ7ZF35C7E7M7AF1=c%C3%A1c-tr%C6%B0%E1%BB%9Dng-trong-b%C3%A1o-c%C3%A1o-h%E1%BB%A3p-nh%E1%BA%A5t-ua 01ED4D7W8FCW3QTV08MWWA8FDT=retargeting aggregate-ltv-retargeting-reports=b%C3%A1o-c%C3%A1o-h%E1%BB%A3p-nh%E1%BA%A5t-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i-ltv h_01HDNYFR9MSJWCP3JA4M1WXN1H=b%C3%A1o-c%C3%A1o-h%E1%BB%A3p-nh%E1%BA%A5t-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i-ltv aggregate-ltv-retargeting-reports::b2093953=b%C3%A1o-c%C3%A1o-h%E1%BB%A3p-nh%E1%BA%A5t-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i-ltv-1 h_01HDNYFR9MSK9VQQ0Q889Z55TN=b%C3%A1o-c%C3%A1o-h%E1%BB%A3p-nh%E1%BA%A5t-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i-ltv-1 feature-reports=b%C3%A1o-c%C3%A1o-t%C3%ADnh-n%C4%83ng h_01HDNYFR9MYXVZ5BA9FDZ6D82M=b%C3%A1o-c%C3%A1o-t%C3%ADnh-n%C4%83ng 01ED4D7W8CBH7Q8D31VX5313WP=skadnetwork protect360%E2%80%94blocked-fraud=protect360-blocked-fraud h_01HDNYFR9MJNKGR7XFCACVP6KT=protect360-blocked-fraud aggregate-protect360-reports-available-via-pull-api=b%C3%A1o-c%C3%A1o-protect360-h%E1%BB%A3p-nh%E1%BA%A5t-c%C3%B3-s%E1%BA%B5n-th%C3%B4ng-qua-api-pull h_01HDNYFR9MSZ9K8F283J0WBHCZ=b%C3%A1o-c%C3%A1o-protect360-h%E1%BB%A3p-nh%E1%BA%A5t-c%C3%B3-s%E1%BA%B5n-th%C3%B4ng-qua-api-pull h_01HDNYYJXVY9XHX87K06NXYQNS=xem-th%C3%AAm" />
