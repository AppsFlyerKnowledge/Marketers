---
title: Dữ liệu thô API Pull
metadata:
  keywords:
    - Premium
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2020-04-14T18:24:00Z'
  edited_at: '2023-11-09T05:07:04Z'
  id: 360007530258
  locale: vi
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/vi/articles/360007530258
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Khái quát:** Sử dụng API này để truy cập các báo cáo dữ liệu thô trong tệp tin CSV.

[![PullAPIRaw_us-en.png](https://files.readme.io/1e68c85ee7d41a275ac6e09b35f6913fc10d974fc51c7c9c1357d3fd4d6d561c-33379479618705.png)](https://files.readme.io/1e68c85ee7d41a275ac6e09b35f6913fc10d974fc51c7c9c1357d3fd4d6d561c-33379479618705.png)

## Dữ liệu thô API Pull

* API Pull cho phép bạn truy cập các báo cáo dữ liệu thô trong tệp tin CSV. <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">Tìm hiểu thêm về báo cáo dữ liệu thô</Anchor>
* Bộ lọc theo các tùy chọn có sẵn: Nguồn truyền thông, phạm vi ngày, tên sự kiện trong ứng dụng, và địa lý.
* Các khả năng khác trong API Pull là:
  * Chọn đơn vị tiền tệ
  * Chọn múi giờ

#### Báo cáo dữ liệu thô có sẵn qua API Pull

<table><tbody><tr><th><span>Báo cáo</span></th><th><span>Mô tả</span></th><th><span>Tần suất làm mới</span></th></tr><tr><td colspan="3"><strong>Báo cáo dữ liệu thô (không tự nhiên)</strong></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-installs-report-v5" target="_blank">Lượt cài đặt</a></td><td><span>Ghi nhận lượt cài đặt không tự nhiên. Bản ghi được tạo khi người dùng mở ứng dụng lần đầu.<br/></span></td><td><span>Thời gian thực</span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-report-v5" target="_blank">Sự kiện trong Ứng dụng</a></td><td><span>Ghi nhận các sự kiện được người dùng thực hiện.<br/></span></td><td><span>Thời gian thực</span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-uninstall-events-report-v5" target="_blank">Gỡ cài đặt</a></td><td><span>Ghi nhận khi người dùng gỡ cài đặt ứng dụng.<br/></span></td><td><span>Hàng ngày</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-v5" target="_blank">Lượt cài đặt lại</a><br/></span></td><td><span>Ghi nhận những người dùng mà sau khi gỡ cài đặt ứng dụng sẽ tương tác với nguồn truyền thông UA và cài đặt lại ứng dụng trong khung thời gian phân bổ lại.</span></td><td><span>Thời gian thực</span></td></tr><tr><td colspan="3"> <span><strong>Báo cáo dữ liệu thô (tự nhiên)</strong></span><span><br/></span> </td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-installs-report-v5" target="_blank">Lượt cài đặt tự nhiên</a><br/></span></td><td><span>Ghi nhận khi người dùng mở ứng dụng lần đầu.<br/></span></td><td><span>Liên tục</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-in-app-events-report-v5" target="_blank">Sự kiện trong ứng dụng tự nhiên</a><br/></span></td><td><span>Ghi nhận thông tin chi tiết về các sự kiện do người dùng thực hiện.<br/></span></td><td><span>Liên tục</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-uninstall-events-report-v5" target="_blank">Các lượt gỡ cài đặt tự nhiên</a><br/></span></td><td><span>Ghi nhận người dùng gỡ cài đặt ứng dụng.<br/></span></td><td><span>Hàng ngày</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-organic-v5" target="_blank">Lượt cài đặt lại tự nhiên</a><br/></span></td><td><span>Ghi nhận doanh thu quảng cáo cho người dùng được phân bổ cho nguồn truyền thông nhắm mục tiêu lại trong khung thời gian thu hút lại.<br/></span></td><td><span>Hàng ngày<br/></span></td></tr><tr><td colspan="3"> <span><strong>Dữ liệu thô về doanh thu quảng cáo</strong></span><span><br/></span> </td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-raw-v5" target="_blank">Doanh thu quảng cáo được phân bổ</a><span><br/></span> </td><td>Ghi nhận doanh thu quảng cáo cho người dùng được phân bổ cho một nguồn truyền thông.</td><td>Hàng ngày</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-organic-raw-v5" target="_blank">Doanh thu quảng cáo tự nhiên</a></td><td>Ghi nhận doanh thu quảng cáo cho người dùng không được phân bổ cho nguồn truyền thông.</td><td>Hàng ngày</td></tr><tr><td colspan="3"><span><strong>Gian lận Protect360</strong></span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-installs-report-v5" target="_blank">Lượt cài đặt</a></td><td>Ghi nhận lượt cài đặt được xác định là gian lận và do đó không được phân bổ cho bất kỳ nguồn truyền thông nào.</td><td><span>Thời gian thực</span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-detection-v5" target="_blank">Lượt cài đặt hậu phân bổ</a></td><td>Ghi nhận các sự kiện trong ứng dụng từ các lượt cài đặt gian lận và do đó hoàn toàn không được phân bổ.</td><td>Thời gian thực</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-in-app-events-report-v5" target="_blank">Sự kiện trong Ứng dụng</a></td><td>Ghi nhận các sự kiện trong ứng dụng được Protect360 xác định là gian lận.</td><td>Hàng ngày</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-fraud-post-inapps-v5" target="_blank">Sự kiện trong ứng dụng hậu phân bổ</a></td><td>Ghi nhận các sự kiện trong ứng dụng đối với các lượt cài đặt được xác định là gian lận sau khi được phân bổ cho một nguồn truyền thông hoặc bị đánh giá là gian lận mà không liên quan đến chính lượt cài đặt đó.</td><td>Hàng ngày</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-clicks-report-v5" target="_blank">Lượt nhấp</a></td><td>Ghi nhận các lượt nhấp được người dùng thực hiện bị Protect360 chặn.</td><td>Hàng ngày</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-install-postbacks-v5" target="_blank">Postback lượt cài đặt bị chặn</a></td><td>Ghi nhận các bản sao của các đăng lại được gửi đến nguồn truyền thông dẫn đến lượt cài đặt bị chặn.</td><td>Thời gian thực</td></tr><tr><td colspan="3"><strong>Đăng lại</strong></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-postbacks-v5" target="_blank">Các đăng lại lượt cài đặt</a></td><td>Ghi nhận các sự kiện cài đặt được tạo khi người dùng mở ứng dụng lần đầu.</td><td>Hàng ngày</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-postbacks-v5" target="_blank">Postback Sự kiện trong Ứng dụng</a></td><td>Ghi nhận các đăng lại sự kiện trong ứng dụng được gửi đến nguồn truyền thông.</td><td>Hàng ngày</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-retarget-in-app-events-postbacks-v5" target="_blank">Nhắm mục tiêu lại các đăng lại sự kiện trong ứng dụng</a></td><td>Ghi nhận các sự kiện trong ứng dụng mà người dùng đã thực hiện trong khung thời gian thu hút lại.</td><td>Thời gian thực</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-retarget-install-postbacks-v5" target="_blank">Đăng lại lượt chuyển đổi nhắm mục tiêu lại</a></td><td>Ghi nhận các sự kiện trong ứng dụng mà người dùng đã thực hiện trong khung thời gian thu hút lại.</td><td>Thời gian thực</td></tr></tbody></table>

<div id="using-pull-api-raw-data" />

<Accordion title="Sử dụng dữ liệu thô API Pull">

**Để sử dụng dữ liệu thô API Pull**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Nhận mã thông báo API. Quản trị viên cần truy xuất mã thông báo.
2. Cung cấp cho nhà phát triển của bạn mã thông báo API cần dùng trong tiêu đề xác thực.
3. Cung cấp cho nhà phát triển các thông số đầu vào khi họ thực hiện lệnh gọi API, như được mô tả trong phần tiếp theo. Các thông số xác định nội dung chính trong báo cáo, cách tổ chức báo cáo và cung cấp khung thời gian báo cáo.
4. Yêu cầu nhà phát triển làm theo <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">hướng dẫn về dữ liệu thô API Pull</Anchor> trong trung tâm nhà phát triển.

#### Tham số

| Tham số | Mô tả |
| --- | --- |
| từ | <ul><li>Phạm vi ngày bao gồm thông số `ngày bắt đầu`và `ngày kết thúc`. Ngày tháng liên quan đến ngày hoạt động.</li><li>Định dạng: `yyyy-mm-dd`, `yyyy-mm-dd hh:mm` hoặc `yyyy-mm-dd hh:mm:ss` **Lưu ý**: Dấu cách cần được mã hóa như được trình bày tại đây `from=2020-04-01%2001:00:00` - Thông thường, các trình duyệt sẽ mã hóa dấu cách.</li><li>Ví dụ: 2010-01-01 hoặc 2010-01-01 20:15 (Thông số giờ và phút khả dụng cho báo cáo dữ liệu thô).</li></ul> |
| tới | Ngày kết thúc. Đối với `from` |
| media\_source | `media_source`: Để giới hạn (lọc) lệnh gọi trong một nguồn truyền thông cụ thể.<br /><br />Đặt cả thông số `media_source` và `category` như sau:<ul><li>Đối với quảng cáo Meta, hãy đặt danh mục và nguồn truyền thông thành *facebook*</li><li>Đối với Twitter, hãy đặt danh mục và nguồn truyền thông thành *twitter*</li><li>Đối với tất cả các nguồn truyền thông khác, hãy đặt danh mục thành *tiêu chuẩn* và nguồn truyền thông thành tên của nguồn truyền thông.</li></ul><ul><li>Ví dụ:<ul><li>`media_source=facebook&category=facebook`</li><li>`media_source=abc_example&category=standard`</li></ul></li></ul> |
| maximum\_rows | Số hàng tối đa được trả về bởi một lệnh gọi API.<ul><li>[Mặc định] nếu không gửi giá trị nào, tối đa 200K hàng</li><li>200000: Trả về tối đa 200 nghìn hàng</li><li>1000000: Trả về tối đa 1 triệu hàng</li><li>Ví dụ: `maximum_rows=1000000` cho phép tối đa 1 triệu hàng.</li></ul> |
| event\_name | Lọc sự kiện trong ứng dụng theo các sự kiện được chỉ định. Chọn nhiều sự kiện bằng cách sử dụng danh sách được phân tách bằng dấu phẩy.<br /><br />**Ví dụ**: `event_name=af_purchase,ftd` |
| reattr | Đặt dữ liệu nhắm mục tiêu lại cho phân bổ.<ul><li>[Mặc định] Nếu false, sẽ trả về các chiến dịch dữ liệu thu hút người dùng (UA).</li><li>Nếu true, sẽ trả về dữ liệu nhắm mục tiêu lại cho phân bổ.</li><li>**Ví dụ**:`reattr=true`</li></ul> |
| additional\_fields | Để có được các trường bổ sung ngoài các trường mặc định. <br /><br />**Ví dụ**: `additional_fields=device_download_time,deeplink_url` |
| tiền tệ | Đơn vị tiền tệ của doanh thu và chi phí<ul><li>[Mặc định] Nếu thông số không được gửi đi, dữ liệu sẽ trả về là USD. Có nghĩa là, kết quả sẽ trả về bằng USD nếu bạn không cần thực hiện bất kỳ thao tác nào.</li><li>Nếu bạn gửi, `currency=preferred` thì đơn vị tiền tệ <Anchor target="_blank" href="/marketers/vi/docs/app-settings#localization-time-zone">dành riêng cho ứng dụng</Anchor> sẽ được sử dụng. Nghĩa là đơn vị tiền tệ được đặt trong phần cài đặt của ứng dụng.</li></ul>**Ví dụ**: Nếu đơn vị tiền tệ dành riêng cho ứng dụng là EUR, bằng cách gửi `currency=preferred`thì các giá trị trả về bằng EUR. |
| Múi giờ | [Mặc định] Dữ liệu trả về bằng cách sử dụng UTC.<ul><li>Để lấy được dữ liệu trong múi giờ <Anchor target="_blank" href="/marketers/vi/docs/app-settings#localization-time-zone">dành riêng cho ứng dụng</Anchor>, hãy thêm `múi giờ` như được trình bày trong phần này vào lệnh gọi:</li></ul><ul><li>`timezone=[Numerical value]`</li><li>Ví dụ: Đối với múi giờ UTC+10:00, hãy sử dụng`timezone=+10:00` **Lưu ý**: `+`,`-` và `:` cần được mã hóa. Ví dụ: +10:00 mã hóa thành `%2B10%3A00`</li></ul> |
| địa lý | Lọc dữ liệu theo mã quốc gia.<br /><br />Giới hạn: Bạn chỉ có thể đặt một bộ lọc mã quốc gia cho mỗi lệnh gọi API. <br /><br />Ví dụ: `geo=ZA` |
| from\_install time | <ul><li>Phạm vi ngày bao gồm thông số `ngày bắt đầu`và `ngày kết thúc`. Ngày tháng liên quan đến ngày hoạt động.</li><li>Định dạng: `yyyy-mm-dd`</li><li>Ví dụ: 2010-01-01</li></ul> |
| to\_install\_time | Ngày kết thúc. Cho `from_install time` |
| đại lý | Để giới hạn (lọc) lệnh gọi chỉ một đại lý cụ thể. |

</Accordion>

<div id="protect360-fields" />

<Accordion title="Trường Protect360">

<Anchor target="_blank" href="/marketers/vi/docs/protect360-raw-data-reports#postattribution-reports">Xem hướng dẫn dữ liệu thô Protect360</Anchor>

</Accordion>

<div id="time-frame-fields" />

<Accordion title="Trường Khung thời gian">

Nếu kết quả API vượt quá mức tối đa, hãy chia báo cáo theo giờ và phút. Áp dụng những điều sau:

* **from**/**to:** **yyyy-mm-dd hh:mm**
* **from:** 
  * Chỉ ngày = từ đầu (00:00) của ngày đã chọn
  * Ngày và giờ = từ và bao gồm cả 00:00
* Thông số **to:** 
  * Chỉ ngày = đến cuối (24:00) của ngày đã chọn
  * Ngày và giờ = đến, nhưng không bao gồm, thời gian hiển thị

**Ví dụ:** Chủ sở hữu ứng dụng có 1300K lượt cài đặt hàng ngày từ tất cả các nguồn. Để vượt qua giới hạn 1 triệu hàng, chủ sở hữu ứng dụng chia ngày thành hai lệnh gọi URI 12 giờ. Xem các tùy chọn trong bảng sau.

<table><tbody><tr><th>Gọi API</th><th>Ngày bắt đầu </th><th>Đến </th></tr><tr><td><strong>Lệnh gọi API thứ nhất</strong> </td><td><p><span><strong>from</strong>=yyyy-mm-dd</span></p><p><span><strong>Ví dụ:</strong></span></p><ul><li><span><strong>from</strong>=<code>2019-12-29</code></span></li><li><span>Bắt đầu vào ngày này, vào đầu ngày lúc 00:00</span></li></ul></td><td><p><span><strong>ngày kết thúc</strong>=yyy</span><span>y-mm-dd 12:00</span></p><p><strong>Ví dụ:</strong> </p><ul><li><span><strong>to</strong>=<code>2019-12-29 12:00</code></span></li><li> <span>Tiếp tục đến 11:59:59, không gồm 12:00</span><span> </span> </li></ul></td></tr><tr><td><p><strong>Tùy chọn A:</strong> <strong>Lệnh gọi API thứ hai</strong> </p><p><span><strong>Ví dụ:</strong></span><span> </span></p><p><span><strong><kbd><code><kbd>&amp;from=2019-12-29 12:00&amp;to=2019-12-29</kbd></code></kbd></strong></span></p><ul><li><span>Bắt đầu từ trưa ngày 29 tháng 12 năm 2019</span></li><li><span>Kết thúc vào lúc nửa đêm ngày 29 tháng 12 năm 2019</span></li></ul></td><td> <p><span><strong>from</strong>=yyyy-mm-dd 12:00</span></p><p><strong>Ví dụ:</strong> </p><ul><li> <strong>from</strong>=<span><code>2019-12-29 12:00</code></span> </li><li><span>Bắt đầu từ và gồm cả 12:00</span></li></ul></td><td><p><span> </span></p><p><span><strong>to</strong>=yyy</span><span>y-mm-dd </span></p><p><span><strong>Ví dụ:</strong> </span></p><ul><li><span><strong>to</strong>=<code>2019-12-29</code></span></li><li><span>Kết thúc vào lúc nửa đêm</span></li></ul><p><span> </span></p></td></tr><tr><td><strong>Tùy chọn B: Lệnh gọi API thứ hai</strong></td><td><p><span><strong>from</strong>=yyyy-mm-dd 12:00</span></p><p><strong>Ví dụ:</strong> </p><ul><li> <strong>from</strong>=<span><code>2019-12-29 12:00</code></span> </li><li><span>Bắt đầu từ và gồm cả 12:00</span></li></ul></td><td><p><span><strong>to</strong>=yyyy-mm-dd+1 00:00</span></p><p><span><strong>+1</strong> = ngày hôm sau lúc 00:00</span></p><p><strong>Ví dụ:</strong> </p><ul><li><span><strong>to=<code>2019-12-30 00:00</code></strong></span></li><li>Có nghĩa là trước bất kỳ thời điểm nào đã qua trong ngày 30 tháng 12.</li></ul></td></tr><tr><td colspan="3"><p><span><strong>Lưu ý:</strong> Sử dụng tùy chọn A hoặc B vì cả hai đều có cùng kết quả. </span></p></td></tr></tbody></table>

</Accordion>

<div id="additional-fields" />

<Accordion title="Các Trưởng Bổ Sung">

Các trường báo cáo bổ sung không được thêm vào danh sách trường mặc định để các trường mới không ảnh hưởng đến quá trình nhập và xử lý của bạn. Sử dụng thông số `additional_fields` để truy cập các trường không phải trường mặc định.

* Mỗi lần chỉ liệt kê một trường.
* Xem <Anchor target="_blank" href="/marketers/vi/docs/raw-data-field-dictionary">danh sách các trường khả dụng</Anchor>.
* Ví dụ: `additional_fields=device_download_time,deeplink_url`

</Accordion>

<div id="default-fields" />

<Accordion title="Trường mặc định">

| Các trường API Pull mặc định |
| --- |
| Thời gian tiếp xúc được phân bổ |
| Thời gian cài đặt |
| Thời gian sự kiện |
| Tên của sự kiện |
| Giá trị của sự kiện |
| Doanh thu sự kiện |
| Tiền tệ doanh thu sự kiện |
| Doanh thu sự kiện USD |
| Nguồn sự kiện |
| Biên nhận đã được xác nhận chưa |
| Đối tác |
| Nguồn truyền thông |
| Kênh |
| Từ khóa |
| Chiến dịch |
| ID Chiến dịch |
| Bộ quảng cáo |
| ID Bộ quảng cáo |
| Quảng cáo |
| ID Quảng cáo |
| Loại Quảng cáo |
| ID trang |
| ID Trang phụ |
| Thông số phụ 1 |
| Thông số phụ 2 |
| Thông số phụ 3 |
| Thông số phụ 4 |
| Thông số phụ 5 |
| Mô hình Chi phí |
| Giá trị Chi phí |
| Đơn vị tiền tệ của chi phí |
| Đối tác Người đóng góp 1 |
| Nguồn phương tiện Người đóng góp 1 |
| Chiến dịch Người đóng góp 1 |
| Loại tương tác Người đóng góp 1 |
| Thời gian tương tác Người đóng góp 1 |
| Đối tác Người đóng góp 2 |
| Nguồn phương tiện Người đóng góp 2 |
| Chiến dịch Người đóng góp 2 |
| Loại tương tác Người đóng góp 2 |
| Thời gian tương tác Người đóng góp 2 |
| Đối tác Người đóng góp 3 |
| Nguồn phương tiện Người đóng góp 3 |
| Chiến dịch Người đóng góp 3 |
| Loại tương tác Người đóng góp 3 |
| Thời gian tương tác Người đóng góp 3 |
| Vùng |
| Mã quốc gia |
| Bang |
| thành phố |
| Mã bưu chính |
| DMA |
| ip |
| wifi |
| người điều hành |
| nhà cung cấp dịch vụ |
| ngôn ngữ |
| ID AppsFlyer |
| ID quảng cáo |
| IDFA |
| ID Android |
| Customer User ID |
| imei |
| IDFV |
| nền tảng |
| Loại thiết bị |
| Phiên bản hệ điều hành |
| Phiên bản ứng dụng |
| Phiên bản SDK |
| ID ứng dụng |
| Tên ứng dụng |
| ID gói |
| Đang nhắm mục tiêu lại |
| Loại lượt chuyển đổi nhắm mục tiêu lại |
| Xem lại phân bổ |
| Cửa sổ Tương tác lại |
| Là phân bổ chính |
| Tác nhân người dùng |
| Liên kết giới thiệu HTTP |
| URL gốc |

</Accordion>

## Thông tin bổ sung

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Nhận xét |
| --- | --- |
| Loại mã thông báo API bắt buộc | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)<Anchor target="_blank" href="/marketers/vi/docs/managing-appsflyer-tokens">Mã thông báo V2.0</Anchor> |
| Truy cập mạng quảng cáo | Không |
| Truy cập đại lý | Có |
| Tính minh bạch của agency | Có. Tuy nhiên, xin lưu ý rằng nếu bạn sử dụng cả bộ lọc đại lý và bộ lọc nguồn truyền thông, thì bộ lọc nguồn truyền thông không áp dụng cho các đại lý không minh bạch. Điều này có nghĩa là đối với các đại lý không minh bạch, tất cả dữ liệu đều được đưa vào; không chỉ dữ liệu từ các nguồn truyền thông được lọc. |
| Tiền tệ dành riêng cho ứng dụng | Có |
| Múi giờ riêng cho ứng dụng | Có |
| Tính cập nhật của dữ liệu | <ul><li>Tương đương với tính khả dụng của dữ liệu trong bảng điều khiển tổng quan.</li><li>Các báo cáo được cập nhật với độ trễ vài giờ:<ul><li>Sự kiện trong ứng dụng<br />tự nhiên</li></ul></li><li>Báo cáo được cập nhật Hàng ngày:<ul><li>Gỡ cài đặt</li><li>Sự kiện trong ứng dụng hậu phân bổ</li><li>Doanh thu Quảng cáo</li></ul></li></ul> |
| Dữ liệu lịch sử | Có.  Theo các chính sách <Anchor target="_blank" href="/marketers/vi/docs/user-level-data-retention">giữ chân người dùng</Anchor> và <Anchor target="_blank" href="/marketers/vi/docs/report-generation-quotas-rate-limitations">giới hạn lưu lượng</Anchor>. |
| Dữ liệu không tự nhiên | Có |
| Dữ liệu tự nhiên | Có |
| Giới hạn tỷ lệ | Giới hạn API cho <Anchor target="_blank" href="/marketers/vi/docs/report-generation-quotas-rate-limitations">dữ liệu thô</Anchor>. |
| Hạn chế về kích thước | <ul><li>Các lệnh gọi API trả về số hàng tối đa là 200K/1M.</li><li>Nếu một báo cáo có đúng 200K/1M hàng, thì giả sử là có các hàng bị thiếu.</li><li>Sử dụng thông số maximum\_rows để chọn số hàng tối đa.</li><li>Thực hiện nhiều lệnh gọi API, sử dụng thông số bắt đầu/kết thúc bao gồm cả thời gian trong ngày.</li></ul> |
| Install\_date from và install\_date\_to | Phạm vi ngày cài đặt phải trước phạm vi ngày hoạt động. |

</Accordion>

<div id="troubleshooting" />

<Accordion title="Xử lý sự cố">

| Dấu hiệu/thông báo | Giải pháp |
| --- | --- |
| Báo cáo không chứa dữ liệu được dự kiến theo phạm vi thời gian được chọn hoặc có sự khác biệt giữa báo cáo dữ liệu thô và báo cáo dữ liệu hợp nhất. | Xác minh rằng bạn đã đặt thông số `timezone`. Nếu không, dữ liệu sẽ được gửi bằng UTC chứ không phải múi giờ ứng dụng của bạn. |

</Accordion>

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Chọn đúng công cụ phân phối dữ liệu/API báo cáo</Anchor>

<div data-zendesk-anchors="pull-api-raw-data=d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-api-pull h_01HE7S6WDVJD2XFW498P8FPY7W=d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-api-pull aggregate-performance-reports-available-via-pull-api=b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-c%C3%B3-s%E1%BA%B5n-qua-api-pull h_01HE7S6WDV59VTP6Z4X790QDRD=b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-c%C3%B3-s%E1%BA%B5n-qua-api-pull h_01HE7S6WDVYJ5MAK04VWB4MF6A=using-pull-api-raw-data parameters=tham-s%E1%BB%91 h_01HE7S6WDVF8T4719HWDJH8JN1=tham-s%E1%BB%91 h_01HE7S6WDVGSS0F116ZB6QVG1N=protect360-fields h_01HE7S6WDVP47A3Q8J7NPH54T5=time-frame-fields h_01HE7S6WDWZ8FR6GRJ40B4CJAV=additional-fields h_01HE7S6WDWMXYF0RHYPF058A9K=default-fields additional-information=th%C3%B4ng-tin-b%E1%BB%95-sung h_01HE7S6WDW9V8XC3CJ0F96EHN0=th%C3%B4ng-tin-b%E1%BB%95-sung h_01HE7S6WDWV87YVJMN76STX7A1=traits-and-limitations h_01HE7S6WDWMZPPTR41VHJQ8MWC=troubleshooting h_01HE7S8S8QCSKRA62A2HVK2MYJ=xem-th%C3%AAm" />
