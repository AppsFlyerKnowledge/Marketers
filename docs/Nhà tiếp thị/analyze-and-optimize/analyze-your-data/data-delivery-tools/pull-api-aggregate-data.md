---
title: Dữ liệu hợp nhất API Pull
metadata:
  keywords:
    - Performance
    - raw data
    - Pull API
    - Reports
    - API
    - Parameters
    - API Policy
    - Advertisers
    - facebook rawdata
    - facebook raw data
    - Developers
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2013-04-24T15:08:25Z'
  edited_at: '2023-11-02T10:23:36Z'
  id: 207034346
  locale: vi
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/vi/articles/207034346
---
> **Khái quát:** Sử dụng API Pull này để nhận báo cáo hợp nhất AppsFlyer của bạn trong các tệp tin CSV.

[![PullAPIAverage_us-en.png](https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png)](https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png)

> 👍 **Tìm kiếm dữ liệu thô API Pull?**
>
> Tìm hiểu chi tiết đầy đủ <Anchor target="_blank" href="/marketers/vi/docs/pull-api-raw-data">ở đây</Anchor>.

## Dữ liệu hợp nhất API Pull

* API Pull cho phép bạn nhận báo cáo dữ liệu hợp nhất về thu hút người dùng (UA) và nhắm mục tiêu lại trong các tệp tin CSV.
* <Anchor target="_blank" href="/marketers/vi/docs/about-data-freshness-and-timezone-support#data-freshness-rates-and-timezone-support">Tốc độ làm mới dữ liệu</Anchor> giống như báo cáo tương tự trên trang Dữ liệu xuất và trang Bảng điều khiển tổng quan. Lưu ý rằng chi phí có thể được cập nhật trễ vài giờ, phụ thuộc vào đối tác cung cấp dữ liệu chi phí.
* Lọc theo các tùy chọn có sẵn: Nguồn truyền thông và phạm vi ngày.
* Các khả năng khác trong API Pull là:
  * Thêm loại tương tác được phân bổ
  * Chọn múi giờ

#### Báo cáo hiệu suất hợp nhất có sẵn thông qua API Pull

<table><tbody><tr><th>danh mục</th><th> UA</th><th>Nhắm mục tiêu lại\*</th></tr><tr><td>Đối tác (nguồn truyền thông)</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>Đối tác theo ngày</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>Hằng ngày</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>Địa lý</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>Báo cáo Địa lý theo ngày</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="3"><p>\* Đối với các báo cáo nhắm mục tiêu lại, hãy thêm <code><span>&amp;reattr=true</span></code> vào URI. </p></td></tr></tbody></table>

<div id="using-pull-api-aggregate-data" />

<Accordion title="Sử dụng dữ liệu hợp nhất API Pull">

**Cách sử dụng dữ liệu hợp nhất của API Pull**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/5dd980a707877c2ab26826170f7f1313bffba1fed8ab3eacb59954770c302932-19754884868369.png) Nhận mã thông báo API. Quản trị viên cần truy xuất mã thông báo.
2. Cung cấp cho nhà phát triển của bạn mã thông báo API cần dùng trong tiêu đề xác thực.
3. Cung cấp cho nhà phát triển các [thông số](/docs/pull-api-aggregate-data#parameters) đầu vào khi họ thực hiện lệnh gọi API, như được mô tả trong phần tiếp theo. Các thông số xác định nội dung chính trong báo cáo, cách tổ chức báo cáo và cung cấp khung thời gian báo cáo.
4. Yêu cầu nhà phát triển làm theo <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-11">hướng dẫn về dữ liệu hợp nhất của API Pull</Anchor> của họ trong trung tâm nhà phát triển.

</Accordion>

<div id="parameters" />

<Accordion title="Tham số">

| Tham số | Mô tả |
| --- | --- |
| app\_id | ID ứng dụng |
| từ | <ul><li>Phạm vi ngày bao gồm thông số `from`và `to` . Phạm vi là phạm vi ngày LTV (cài đặt).</li><li>Định dạng: `yyyy-mm-dd`,</li><li>Ví dụ: 2010-01-01</li></ul> |
| tới | Ngày kết thúc. Đối với `from` |
| media\_source | Sử dụng để giới hạn (lọc) cho một nguồn truyền thông cụ thể.<ul><li>Ví dụ:`media_source=facebook`</li></ul> |
| attribution\_touch\_type | Đặt thông số này như trong ví dụ minh họa để lấy KPI [phân bổ lượt xem hết](/docs/pull-api-aggregate-data) (VTA).<br /><br />Ví dụ: `attribution_touch_type=impression`<br /><br />Một số KPI VTA, như lượt nhấp, lượt hiển thị và API chi phí, không có giá trị được liên kết với chúng và thay vào đó sẽ hiển thị giá trị N/A. |
| tiền tệ | Đơn vị tiền tệ của doanh thu và chi phí.<br /><br />Báo cáo API Pull hợp nhất luôn sử dụng đơn vị tiền tệ dành riêng cho ứng dụng. |
| reattr | Nhận dữ liệu lượt chuyển đổi nhắm mục tiêu lại.<ul><li>[Mặc định] Nếu sai, sẽ trả về các chiến dịch dữ liệu thu hút người dùng (UA).</li><li>Nếu là true, lượt chuyển đổi nhắm mục tiêu lại sẽ được trả về.</li><li>**Ví dụ**:`reattr=true`</li></ul> |
| Múi giờ | [Mặc định] Dữ liệu trả về bằng cách sử dụng UTC.<ul><li>URI mẫu được điền bằng thông số múi giờ được đặt thành múi giờ dành riêng cho ứng dụng.</li><li>[Mặc định] Nếu thông số không được gửi đi, dữ liệu sẽ trả về sử dụng UTC.</li><li>Nếu bạn gửi`timezone=[Joda-Time]`, thì dữ liệu sẽ trả về sử dụng múi giờ cụ thể cho ứng dụng.</li></ul>Lưu ý về việc chọn múi giờ<ul><li>1. Định dạng múi giờ Joda-Time tính đến thời gian tiết kiệm ánh sáng ban ngày.</li><li>Giá trị Joda-Time phải giống hệt với giá trị trên trang cài đặt ứng dụng. Ví dụ, nếu múi giờ cài đặt là Paris, thì giá trị múi giờ trong URL của API Pull phải là `timezone=Europe%2fParis`.</li><li>Chỉ có thể kéo dữ liệu trong múi giờ đã chọn kể từ ngày thiết lập múi giờ. Mọi dữ liệu trước ngày thay đổi đều sử dụng UTC làm múi giờ.</li></ul> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Nhận xét |
| --- | --- |
| Loại mã thông báo API bắt buộc | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/5dd980a707877c2ab26826170f7f1313bffba1fed8ab3eacb59954770c302932-19754884868369.png)<Anchor target="_blank" href="/marketers/vi/docs/managing-appsflyer-tokens">Mã thông báo V2.0</Anchor> |
| Truy cập mạng quảng cáo | N |
| Truy cập đại lý | Y |
| Tính minh bạch của agency | Y |
| Tiền tệ dành riêng cho ứng dụng | Y |
| Múi giờ riêng cho ứng dụng | Y |
| Chi phí | Dữ liệu chi phí chỉ dành cho các chiến dịch UA; không dành cho các chiến dịch nhắm mục tiêu lại hoặc không hoạt động (chiến dịch không có bất kỳ lượt cài đặt nào). |
| Độ mới của dữ liệu | <Anchor target="_blank" href="/marketers/vi/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">Liên tục</Anchor> |
| Dữ liệu lịch sử | 5 năm |
| Dữ liệu không tự nhiên | Y |
| Dữ liệu tự nhiên | Y |
| Giới hạn lưu lượng | <Anchor target="_blank" href="/marketers/vi/docs/report-generation-quotas-rate-limitations">Mức giới hạn</Anchor> |
| Hạn chế về kích thước | <ul><li>Các lệnh gọi API trả về số hàng tối đa là 200K.</li><li>Nếu một báo cáo có đúng 200K hàng, thì giả sử là có các hàng bị thiếu.</li><li>Thực hiện nhiều lệnh gọi API, sử dụng thông số bắt đầu/kết thúc bao gồm cả thời gian trong ngày.</li></ul>Lưu ý! API Pull lấy dữ liệu thô chỉ hỗ trợ 1 triệu hàng. Báo cáo dữ liệu hợp nhất có giới hạn chỉ 200 nghìn hàng. |
| Thay đổi tên chiến dịch | Báo cáo API Pull không hỗ trợ thay đổi tên chiến dịch |

</Accordion>

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/aggregated-and-analytics-reporting-overview">Mô tả và ví dụ về các báo cáo hợp nhất</Anchor>
> * <Anchor target="_blank" href="/marketers/vi/docs/aggregated-and-analytics-reporting-overview">Chọn công cụ phân phối dữ liệu phù hợp cho dữ liệu hợp nhất</Anchor>

<div data-zendesk-anchors="h_01HE0YP82966QHRAEW979ABCTP=t%C3%ACm-ki%E1%BA%BFm-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-api-pull pull-api-aggregate-data=d%E1%BB%AF-li%E1%BB%87u-h%E1%BB%A3p-nh%E1%BA%A5t-api-pull h_01HE0YP829WD5TDFHTPYAV30QN=d%E1%BB%AF-li%E1%BB%87u-h%E1%BB%A3p-nh%E1%BA%A5t-api-pull aggregate-performance-reports-available-via-pull-api=b%C3%A1o-c%C3%A1o-hi%E1%BB%87u-su%E1%BA%A5t-h%E1%BB%A3p-nh%E1%BA%A5t-c%C3%B3-s%E1%BA%B5n-th%C3%B4ng-qua-api-pull h_01HE0YP829EQ7N6CST352X917H=b%C3%A1o-c%C3%A1o-hi%E1%BB%87u-su%E1%BA%A5t-h%E1%BB%A3p-nh%E1%BA%A5t-c%C3%B3-s%E1%BA%B5n-th%C3%B4ng-qua-api-pull h_01HE0YP82954F1ACVR2K4AFD5W=using-pull-api-aggregate-data h_01HE0YP8292131Q2561A4E1GYZ=parameters h_01HE0YP829ZPJAPHPDR9H4HMRT=traits-and-limitations h_01HE0Y2KTXS06WHN57MQ91AD09=xem-th%C3%AAm" />
