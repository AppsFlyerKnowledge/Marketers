---
title: Báo cáo dữ liệu thô Protect360
metadata:
  keywords:
    - Advertisers
    - Protect360
    - protect
    - protect 360
    - '360'
    - Raw Data
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-11-09T13:03:45Z'
  edited_at: '2023-11-09T05:06:38Z'
  id: 360015179337
  locale: vi
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/vi/articles/360015179337
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Khái quát:** Báo cáo dữ liệu thô mô tả lượt cài đặt và các sự kiện trong ứng dụng bị chặn bởi công cụ Protect360, cũng như từ các Quy tắc Xác thực được thêm vào theo cách thủ công.

<div id="about-protect360-raw-data-reports" />

## Giới thiệu về báo cáo dữ liệu thô của Protect360

Báo cáo dữ liệu thô:

* Hiển thị dữ liệu về:
  * Lượt nhấp, lượt cài đặt và các sự kiện trong ứng dụng mà công cụ Protect360 xác định là gian lận.
  * Lượt cài đặt và sự kiện trong ứng dụng được xác định thông qua Quy tắc Xác thực.
* Bao gồm lý do chặn cho mỗi lượt nhấp, lượt cài đặt hoặc sự kiện trong ứng dụng.
* Được các nhà quảng cáo sử dụng để đối chiếu các tài khoản mạng quảng cáo, để tối ưu hóa và để điều chỉnh bảng điều khiển phân bổ nhằm chống gian lận hậu phân bổ.
* Có thể có <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions">một số trường bị hạn chế hoặc không khả dụng</Anchor> nếu <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">Quyền riêng tư Nâng cao Hợp nhất (AAP) AppsFlyer</Anchor>.
* Các loại báo cáo và tính sẵn có theo lượt tải xuống, API và Data Locker (bộ chứa S3) được mô tả trong các phần tiếp theo.
* Thời gian lưu giữ báo cáo dữ liệu thô lịch sử lên tới 90 ngày, tùy thuộc vào công cụ báo cáo và nguồn gốc dữ liệu thô.

<div id="report-types" />

<Accordion title="Loại báo cáo">

<div id="protect360-raw-data-report-types" />

#### Các loại báo cáo dữ liệu thô của Protect360

| Báo cáo | Mô tả |
| --- | --- |
| Lượt cài đặt | Các báo cáo bao gồm:<ul><li>**Lượt cài đặt giả mạo**: Những lượt cài đặt mà công cụ Protect360 xác định là gian lận. Lượt gỡ cài đặt này sẽ không xuất hiện trong bất kỳ bảng điều khiển hoặc dữ liệu thô nào của AppsFlyer, ngoại trừ bảng điều khiển và dữ liệu thô của Protect360.</li><li>**Lượt cài đặt bị đánh cắp**: Người dùng thực cài đặt, trong đó lượt phân bổ bị đánh cắp, nhưng Protect360 [điều chỉnh lượt phân bổ](/docs/protect360-raw-data-reports#điều-chỉnh-phân-bổ-lượt-cài-đặt-bị-đánh-cắp).</li><li>**Quy tắc Xác thực**: Chặn cài đặt hoặc chặn phân bổ (Protect360 [điều chỉnh lượt phân bổ](/docs/protect360-raw-data-reports#điều-chỉnh-phân-bổ-lượt-cài-đặt-bị-đánh-cắp)).</li></ul> |
| Lượt cài đặt hậu phân bổ | Báo cáo bao gồm lượt cài đặt được phân bổ cho một nguồn truyền thông, nhưng sau đó bị phát hiện là gian lận.Protect360 [điều chỉnh lượt phân bổ](/docs/protect360-raw-data-reports#điều-chỉnh-phân-bổ-lượt-cài-đặt-bị-đánh-cắp). |
| Các sự kiện trong ứng dụng bị chặn | Báo cáo bao gồm các sự kiện trong ứng dụng từ:<ul><li>**Lượt cài đặt giả mạo**: IAE bị chặn.</li><li>**Sự kiện trong ứng dụng**: Được xác định là gian lận độc lập với các lượt cài đặt ban đầu.</li><li>**Quy tắc Xác thực**:<ul><li>IAE từ một quy tắc đã chặn lượt cài đặt hoặc chặn phân bổ.</li><li>IAE từ một quy tắc đã chặn sự kiện trong ứng dụng.</li></ul></li></ul> |
| Sự kiện trong ứng dụng hậu phân bổ | Báo cáo bao gồm sự kiện trong ứng dụng:<ul><li>Hậu phân bổ đã xác định.</li><li>Các lượt cài đặt được phân bổ cho một nguồn truyền thông, nhưng sau đó bị phát hiện là gian lận.</li></ul> |
| Lượt nhấp | Báo cáo bao gồm các lượt nhấp bị chặn với lý do chặn. |
| Postback lượt cài đặt bị chặn | Báo cáo bao gồm bản sao của các yêu cầu đăng lại bị từ chối được gửi đến các nguồn truyền thông mang lại các lượt cài đặt bị chặn. |

</Accordion>

<div id="postattribution-reports" />

<Accordion title="Các báo cáo hậu phân bổ">

* Báo cáo gian lận dữ liệu thô hậu phân bổ có cấu trúc tương tự như cấu trúc của các báo cáo gian lận bị chặn.
* Báo cáo hậu phân bổ của tháng hiện tại (theo ngày cài đặt) tiếp tục được cập nhật cho đến ngày thứ bảy của tháng tiếp theo (ngày phát hiện).
* Báo cáo dữ liệu thô hậu phân bổ được giới hạn chỉ cho các nhà quảng cáo. Các đại lý cần được cấp <Anchor target="_blank" href="/partners/vi/docs/protect360-for-integrated-partners">quyền</Anchor> để truy cập.
* Báo cáo chứa các sự kiện gian lận hậu phân bổ được Protect360 xác định và bao gồm tất cả các nguồn truyền thông trong một báo cáo duy nhất. **Lưu ý**: Nếu không có bất kỳ sự kiện gian lận hậu phân bổ nào được xác định trong phạm vi ngày đã chọn, báo cáo sẽ trả về trống,
* Báo cáo gian lận dữ liệu thô hậu phân bổ có sẵn như sau:

  * Giao diện người dùng bảng điều khiển: giới hạn ở một nguồn đa phương tiện trong một tháng.
  * Pull API (API kéo): chứa tất cả các nguồn đa phương tiện.  (Hạn chế: Chỉ dành cho chủ sở hữu ứng dụng)

<div id="using-post-attribution-reports" />

#### **Sử dụng báo cáo hậu phân bổ**

* Chọn bất kỳ cài đặt/IAE kết hợp nào và dò phạm vi ngày nếu cần.
* Lưu ý rằng Protect360 thực hiện việc phát hiện hậu phân bổ trong tháng theo lịch của lượt cài đặt và cho đến ngày thứ bảy của tháng tiếp theo. Điều này có nghĩa là, ví dụ, đối với các lượt cài đặt trong tháng 11, Protect360 sẽ kiểm tra gian lận đến ngày 7 tháng 12.
* Tốt nhất nên sử dụng API Pull này như sau:
  * Giả sử bạn kéo báo cáo hàng ngày.
  * Đặt phạm vi ngày cài đặt thành 60 ngày trở về trước kể từ ngày hiện tại.
  * Đặt phạm vi ngày bắt đầu/ngày kết thúc thành ngày trước ngày hiện tại.  
    Điều này có nghĩa là bạn sẽ nhận được danh sách gian lận hậu phân bổ được phát hiện ngày hôm qua. Nếu bạn không kéo báo cáo trong vài ngày, hãy điều chỉnh phạm vi ngày phát hiện và kéo báo cáo.

<div id="example" />

> 📄 **Ví dụ:**
>
> **Ví dụ A**: Trong tháng 12 (ngày cài đặt) 15 lượt cài đặt được phân bổ cho example\_media. Vào ngày 3 tháng 1 (ngày phát hiện), Protect360 xác định example\_media là kẻ lừa đảo. Do đó, 15 lượt cài đặt được phân bổ cho example\_media  được liệt kê vào danh sách gian lận trong báo cáo gian lận hậu phân bổ để chủ sở hữu ứng dụng tiếp tục hành động.
>
> **Ví dụ B**: Trong tháng 12, có15 lượt cài đặt được phân bổ cho example\_media. Vào ngày 9 tháng 1, Protect360 xác định example\_media là kẻ lừa đảo. Trong trường hợp này, Protect360 không thực hiện hành động nào vì kẻ lừa đảo đã được xác định sau tháng kết thúc vào ngày 7 tháng 1.

</Accordion>

<div id="raw-data-availability-by-tool-type" />

<Accordion title="Tính khả dụng của dữ liệu thô theo loại công cụ">

<div id="protect360-raw-data-availability-by-tool-type" />

#### Tính khả dụng của dữ liệu thô Protect 360 theo loại công cụ

<table><thead><tr><th>Báo cáo</th><th>Độ mới của dữ liệu</th><th>API Pull</th><th>Trang Dữ liệu xuất</th><th>Hộp khóa dữ liệu</th></tr></thead><tbody><tr><td>Lượt cài đặt</td><td>Thời gian thực</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Các sự kiện trong ứng dụng bị chặn </td><td>Thời gian thực</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Lượt nhấp</td><td>Thời gian thực</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Postback lượt cài đặt bị chặn</td><td>Thời gian thực</td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Lượt cài đặt hậu phân bổ</td><td><p>10:00 UTC hàng ngày</p></td><td><p><span>✓</span></p></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Sự kiện trong ứng dụng hậu phân bổ</td><td><p>10:00 UTC hàng ngày</p></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr></tbody><tfoot><tr><td colspan="5"><p>\* Hạn chế đối với báo cáo qua Hộp khóa Dữ liệu:</p><ul><li>Tính minh bạch của đại lý không được hỗ trợ. Có nghĩa là lưu lượng truy cập do đại lý thúc đẩy không chứa tên của nguồn truyền thông gửi lượt cài đặt. </li><li>Báo cáo có một bộ các trường duy nhất liên quan đến các báo cáo Data Locker khác. Không thể thay đổi danh sách này. </li><li>Dữ liệu nhắm mục tiêu lại không có sẵn trong báo cáo Lượt cài đặt; chỉ trong báo cáo Lượt cài đặt hậu phân bổ. </li></ul></td></tr></tfoot></table>

</Accordion>

<div id="getting-raw-data-reports" />

## Nhận báo cáo dữ liệu thô

Báo cáo dữ liệu thô có sẵn bằng cách tải xuống, API Pull và Hộp khóa Dữ liệu (bộ chứa S3). Bạn cũng có thể <Anchor target="_blank" href="/partners/vi/docs/protect360-for-integrated-partners">cấp cho đối tác quyền truy cập vào các báo cáo</Anchor>.

<div id="download" />

<Accordion title="Tải xuống">

**Để tải xuống:**

1. Trong bảng điều khiển Protect360, đi đến **Raw data reports** (Báo cáo dữ liệu thô) > **Blocked** or **Post-attribution** (Bị chặn hoặc Hậu phân bổ).
   * Đối với các báo cáo hậu phân bổ, hãy chọn nguồn truyền thông và tháng.
2. Chọn báo cáo **Protect360 & Quy tắc Xác thực** để tải xuống.

**HOẶC**

1. Trong bảng điều khiển AppsFlyer, hãy chuyển đến mục **Export Data** (Xuất Dữ liệu).
2. Chọn báo cáo **Protect360 & Quy tắc Xác thực** để tải xuống.

**Lưu ý**: Các báo cáo được tải xuống từ trang Xuất Dữ liệu chứa tất cả các nguồn truyền thông.

</Accordion>

<div id="pull-api" />

<Accordion title="API Pull">

**Để tải xuống các báo cáo dữ liệu thô có sẵn bằng API Pull:**

**Trước khi bạn bắt đầu:**

Bạn cần mã thông báo API Pull. Nhận token từ <Anchor target="_blank" href="/marketers/vi/docs/managing-appsflyer-tokens">admin user</Anchor>.

1. Đi đến **Integration > API Access** (Tích hợp > Truy cập API).  
   Trang <Anchor target="_blank" href="/marketers/vi/docs/pull-api-raw-data">Pull API</Anchor> (API Pull) sẽ mở ra.
2. Trong phần báo cáo gian lận của Protect360, hãy chọn lệnh gọi API Pull cần thiết.
3. Điền các thông số theo yêu cầu. Bảng sau liệt kê các thông số.
4. Kéo báo cáo.

<div id="pull-api-raw-data-report-parameters" />

#### Thông số báo cáo dữ liệu thô API Pull

| Tham số | Mô tả | Định dạng | Bắt buộc |
| --- | --- | --- | --- |
| app\_id | ID ứng dụng như xuất hiện trong AppsFlyer | chuỗi | Có |
| api\_token | Lấy mã khóa từ Bảng điều khiển. Đi đến **Integration** > **API Access.** Chỉ người dùng quản trị mới có thể truy xuất mã thông báo API. | chuỗi | Có |
| từ | Bắt đầu của phạm vi ngày:<ul><li>Đối với lượt cài đặt, đây là ngày cài đặt.</li><li>Đối với các sự kiện trong ứng dụng, đây là ngày diễn ra sự kiện.</li></ul> | NĂM-THÁNG-NGÀY | Có |
| tới | Kết thúc của phạm vi ngày:<ul><li>Đối với lượt cài đặt, đây là ngày cài đặt.</li><li>Đối với các sự kiện trong ứng dụng, đây là ngày diễn ra sự kiện.</li></ul> | NĂM-THÁNG-NGÀY | Có |
| event\_name | [Tùy chọn đối với gian lận sự kiện trong ứng dụng Hậu phân bổ]<br /><br />Lọc sự kiện theo sự kiện trong ứng dụng. Giới hạn báo cáo chỉ các sự kiện cụ thể.  Có thể bao gồm một hoặc nhiều sự kiện.<br /><br />Ví dụ sử dụng: `&event_name=af_purchase,af_login` | chuỗi | Không |
| additional\_fields=rejected\_reason\_value | [Tùy chọn đối với gian lận sự kiện trong ứng dụng Hậu phân bổ]<br /><br />**<Anchor target="_blank" href="/marketers/vi/docs/raw-data-field-dictionary#protect360">rejected\_reason\_value</Anchor>** hiển thị người đóng góp hợp lệ (nguồn truyền thông) cho các lượt cài đặt/sự kiện trong ứng dụng bị đánh cắp. Được điền bằng <Anchor target="_blank" href="/marketers/vi/docs/raw-data-field-dictionary#attribution::2a6fd501">**người đóng góp[1-3]**</Anchor> hoặc **tự nhiên**. | chuỗi | Không |
| ngày bắt đầu | [Tùy chọn đối với lượt cài đặt Hậu phân bổ]<br /><br />Bắt đầu của phạm vi ngày phát hiện gian lận. (Mặc định là from (từ).) (Được sử dụng trong gian lận cài đặt Hậu phân bổ.) (Được sử dụng trong gian lận cài đặt Hậu phân bổ.) | NĂM-THÁNG-NGÀY | Không |
| ngày kết thúc | [Tùy chọn đối với lượt cài đặt Hậu phân bổ]<br /><br />Kết thúc của phạm vi ngày phát hiện gian lận. (Mặc định là to (đến).) | NĂM-THÁNG-NGÀY | Không |

</Accordion>

<div id="data-locker" />

<Accordion title="Hộp khóa dữ liệu">

Hộp khóa Dữ liệu ghi dữ liệu thô vào một bộ chứa S3 AWS.

<Anchor target="_blank" href="/marketers/vi/docs/data-locker-advertiser-reports#protect360">Xem danh sách các báo cáo Protect360 có sẵn</Anchor>. 

<Anchor target="_blank" href="/marketers/vi/docs/data-locker-for-marketers#aws-cli">Xem hướng dẫn cấu hình Hộp khóa Dữ liệu</Anchor>.

</Accordion>

<div id="protect360-report-structure" />

## Cấu trúc báo cáo Protect360

Báo cáo Protect360 có cùng cấu trúc giống như các trường báo cáo thu hút người dùng.

Ngoài các <Anchor target="_blank" href="/marketers/vi/docs/raw-data-field-dictionary">trường báo cáo dữ liệu thô</Anchor> thông thường, báo cáo Protect360 cũng có các trường nhắm mục tiêu lại và lý do bị chặn, như sau:

<div id="blocked-reasons" />

### Lý do bị chặn

<div id="click-level-blocked-reasons" />

<Accordion title="Các lý do bị chặn ở cấp độ nhấp chuột">

Ở cấp độ lượt nhấp, các lượt nhấp bị chặn và quá trình phân bổ bỏ qua chúng.

| Lý do bị chặn | Mô tả |
| --- | --- |
| ip\_blacklist | Dựa trên danh sách được tạo linh hoạt (<Anchor target="_blank" href="/marketers/vi/docs/protect360-anti-fraud-guide#ip-denylists">chi tiết</Anchor>) |
| invalid\_fingerprint | Chỉ các lượt nhấp S2S: các thông số không hợp lệ do nguồn gửi (đối với Đối sánh xác suất) |
| click\_capping | Tỷ lệ gian lận lượt nhấp rất cao được phát hiện từ mạng quảng cáo đó. <Anchor target="_blank" href="/partners/vi/docs/protect360-for-integrated-partners#impression-capping">Tìm hiểu thêm</Anchor> |
| click\_signing | Chữ ký trên lượt nhấp không được xác thực. <Anchor target="_blank" href="/partners/vi/docs/click-signing-for-ad-networks">Tìm hiểu thêm</Anchor> |
| input\_validation | Tên nguồn truyền thông không hợp lệ |

</Accordion>

<div id="install-level-blocked-reasons" />

<Accordion title="Các lý do bị chặn ở cấp độ cài đặt">

Ở cấp cài đặt, chúng tôi xác định đủ thông tin tại thời điểm cài đặt để xác định:

* Lượt cài đặt giả, có nghĩa là người dùng cài đặt ứng dụng không phải là người thật. Trong trường hợp này, hoạt động phân bổ bị chặn hoàn toàn.
* Đánh cắp phân bổ, trong đó người dùng là thật nhưng hoạt động tương tác là giả mạo. Trong trường hợp này, hoạt động tương tác gian lận bị chặn và phân bổ được chỉ định lại cho mạng quảng cáo đóng góp hợp lệ đầu tiên.

Các bảng sau đây liệt kê các lý do bị chặn cấp cài đặt có thể xảy ra:

<div id="install-level-fake-install-block-sub-reasons" />

#### Cấp cài đặt: Lý do chặn lượt cài đặt giả

| Lý do bị chặn | Lý do phụ bị chặn | Mô tả |
| --- | --- | --- |
| Bot | fake\_device\_parameters | Hành vi không phải của con người được phát hiện trong các thông số liên quan đến thiết bị trong quá trình cài đặt ứng dụng |
| Bot | fake\_install\_parameters | Hành vi không phải của con người được phát hiện trong các thông số liên quan đến cài đặt trong quá trình cài đặt ứng dụng |
| Bot | bayesian\_network | Nhận dạng mạng Bayes của các dạng gian lận |
| install\_store\_validation | - | <Anchor target="_blank" href="/marketers/vi/docs/implement-apple-app-store-itunes-install-validation">Xác thực nhận lượt cài đặt</Anchor> Apple App Store không thành công |
| validation\_bots | invalid\_device\_parameters | Các kỳ vọng trường thiết bị cụ thể không khớp nhau - được xác định bởi khách hàng |
| validation\_bots | validation\_rules | Các quy tắc trong đó kết quả là các lượt cài đặt bị chặn dựa trên quy tắc xác thực được xác định theo cách thủ công |

<div id="install-level-attribution-hijacking-block-sub-reasons" />

#### Cấp cài đặt: Lý do chặn đánh cắp phân bổ

| Lý do bị chặn | Lý do phụ bị chặn | Mô tả |
| --- | --- | --- |
| ctit\_anomalies | short\_ctit | Lượt cài đặt bị chặn do CTIT ngắn: Do Protect360 xác định |
| install\_hijacking | referrer\_hijack | Lần tìm cách đánh cắp bị chặn dựa trên các thông số SDK GooglePlay API và AppsFlyer |
| install\_hijacking | integration\_temporarily\_blocked | Lượt cài đặt bị chặn vì đối tác (pid) có tỷ lệ gian lận cực cao và điểm bất thường đáng kể trong tất cả lưu lượng truy cập của họ |
| validation\_hijacking | short\_ctit | Lượt cài đặt bị chặn do CTIT ngắn: Do khách hàng xác định |
| validation\_hijacking | empty\_site\_id | Lượt cài đặt bị chặn do ID trang web không được phổ biến. Triển khai quy tắc theo từng giai đoạn |
| validation\_hijacking | validation\_rules | Các quy tắc trong đó kết quả là phân bổ bị chặn dựa trên quy tắc xác thực được xác định theo cách thủ công |

</Accordion>

<div id="cluster-level-blocked-reasons" />

<Accordion title="Các lý do bị chặn ở cấp cụm">

Khi có dạng gian lận bị phát hiện, nguồn gian lận được cho vào danh sách từ chối. Các lượt cài đặt từ nguồn trong danh sách từ chối này bị chặn vì một trong các lý do:

* Lượt cài đặt giả, có nghĩa là người dùng cài đặt ứng dụng không phải là người thật. Trong trường hợp này, hoạt động phân bổ bị chặn hoàn toàn.
* Đánh cắp phân bổ, trong đó người dùng là thật nhưng hoạt động tương tác là giả mạo. Trong trường hợp này, hoạt động tương tác gian lận bị chặn và phân bổ được chỉ định lại cho mạng quảng cáo đóng góp hợp lệ đầu tiên.

Các bảng sau đây liệt kê các lý do bị chặn cấp cụm có thể xảy ra:

<div id="cluster-level-fake-install-block-reasons" />

#### Cấp cụm: Lý do chặn lượt cài đặt giả

| Lý do bị chặn | Lý do phụ bị chặn | Mô tả |
| --- | --- | --- |
| Bot | timestamp\_anomalies | Các bất thường liên quan đến số lần nhấp luồng phân bổ và các nhãn thời gian khác được thu thập từ thiết bị |
| bot, site\_blacklist | device\_emulators | Các lượt cài đặt được tạo trên quy mô lớn bởi các tập lệnh tự động làm việc trong môi trường ảo. |
| site\_blacklist | device\_farms | Tỷ lệ cao của các thiết bị chưa biết (mới) |
| behavioral\_anomalies | behavioral\_anomalies | Hành vi đáng ngờ trong ứng dụng so với dạng hành vi người dùng ứng dụng thông thường |

<div id="cluster-level-attribution-hijacking-block-reasons" />

#### Cấp cụm: Lý do chặn đánh cắp phân bổ

| Lý do bị chặn | Lý do phụ bị chặn | Mô tả |
| --- | --- | --- |
| ctit\_anomalies, install\_hijacking | ctit\_anomalies | Dạng CTIT bất thường theo tiêu chuẩn ứng dụng |
| click\_flood | click\_flood | Khối lượng nhấp chuột cao bất thường trên các phân phối CTIT dài |
| install\_hijacking | click\_clusters | Các lượt nhấp được tạo bởi phần mềm độc hại cấp thiết bị |

</Accordion>

<div id="inapp-level-blocked-reasons" />

<Accordion title="Các lý do bị chặn ở cấp trong ứng dụng">

Các sự kiện trong ứng dụng có thể bị chặn vì những lý do sau:

* Cài đặt ban đầu được xác định là giả.
* Vì một quy tắc xác thực xác định.
* Vì thuật toán của chúng tôi phát hiện gian lận.

Bảng sau liệt kê các lý do bị chặn cấp trong ứng dụng có thể xảy ra.

<div id="in-app-level-block-reasons" />

#### Lý do chặn cấp trong ứng dụng

| Lý do bị chặn | Lý do phụ bị chặn | Mô tả |
| --- | --- | --- |
| Kế thừa lượt cài đặt | Kế thừa lượt cài đặt | Lượt cài đặt ban đầu được xác định là giả dựa trên lý do [cấp cài đặt](/docs/protect360-raw-data-reports#install-level-blocked-reasons) [hoặc danh sách từ chối](/docs/protect360-raw-data-reports#cluster-level-blocked-reasons) |
| inapps\_bots | fake\_device\_parameters | Thuật toán AppsFlyer phát hiện gian lận |
| in\_app\_store\_validation | - | Không thể <Anchor target="_blank" href="/marketers/vi/docs/legacy-receipt-validation-for-in-app-purchases">Xác thực biên lai</Anchor> để mua hàng trong ứng dụng. |
| validation\_inapps | validation\_rules | Dựa trên quy tắc xác thực được xác định theo cách thủ công |

</Accordion>

<div id="retargeting" />

### Nhắm mục tiêu lại

Dữ liệu thô của Protect360 bao gồm các lượt cài đặt gian lận và các phiên từ các chiến dịch nhắm mục tiêu lại (được gọi tương ứng là phân bổ lại và thu hút lại). Dữ liệu hiển thị bằng cách sử dụng trường <Anchor target="_blank" href="/marketers/vi/docs/raw-data-field-dictionary#event">tên sự kiện</Anchor> và <Anchor target="_blank" href="/marketers/vi/docs/raw-data-field-dictionary#attribution::e9c68f6c">loại lượt chuyển đổi nhắm mục tiêu lại</Anchor>. Chúng sẽ được đánh dấu là:

* Lượt cài đặt (áp dụng cho tên sự kiện, nhưng không áp dụng cho loại chuyển đổi nhắm mục tiêu lại)
* Ghi công lại
* Thu hút lại
* Lượt cài đặt lại

Dữ liệu thô nhắm mục tiêu lại của Protect360 có sẵn cho các lượt chặn thời gian thực và gian lận được phát hiện hậu phân bổ như sau:

<table><thead><tr><th>Báo cáo </th><th>Xuất dữ liệu</th><th>API Pull</th><th>Hộp khóa dữ liệu</th></tr></thead><tbody><tr><td>Lượt cài đặt</td><td><span>✓\*</span></td><td><span>✓\*</span></td><td>-</td></tr><tr><td>Lượt cài đặt hậu phân bổ</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="4"> <span>\* Dữ liệu thu hút lại không có sẵn</span><span><br/></span> </td></tr></tbody></table>

<div id="hijacked-installs-attribution-correction" />

### Điều chỉnh phân bổ lượt cài đặt bị đánh cắp

Đối với các lượt cài đặt bị đánh cắp, AppsFlyer chặn phân bổ cho mạng gian lận và thay vào đó phân bổ nguồn người đóng góp hợp pháp sau cùng. 

Đối với các lượt cài đặt bị đánh cắp, hãy sử dụng trường <Anchor target="_blank" href="/marketers/vi/docs/raw-data-field-dictionary#protect360">rejected\_reason\_value</Anchor> để xác định người đóng góp hợp lệ (nguồn truyền thông), nghĩa là người đóng góp đáng lẽ đã nhận được phân bổ ban đầu.

* Thông số **rejected\_reason\_value** được điền bằng <Anchor target="_blank" href="/marketers/vi/docs/raw-data-field-dictionary#attribution::2a6fd501">**người đóng góp[1-3]**</Anchor> hoặc **tự nhiên**. Kiểm tra các trường **người đóng góp[1-3]** **nguồn truyền thông/đối tác**để xem thông tin chi tiết về người đóng góp và đối chiếu.
* Nếu các trường người đóng góp không xuất hiện trong báo cáo của bạn, thì bạn có thể thêm các trường này vào từ trang **Xuất dữ liệu** .

**Lưu ý**: Khi lượt cài đặt bị đánh cắp bị chặn theo thời gian thực, thì các phân bổ chính xác sẽ hiển thị trong báo cáo và bảng điều khiển AppsFlyer (không chỉ Protect360). Khi lượt cài đặt bị đánh cắp được xác định hậu phân bổ thì các phân bổ chính xác chỉ được hiển thị trong dữ liệu thô của Protect360.

<div data-zendesk-anchors="about-protect360-raw-data-reports=gi%E1%BB%9Bi-thi%E1%BB%87u-v%E1%BB%81-b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-c%E1%BB%A7a-protect360 h_01HE7S55TCE60A34T6RCNTCQK8=gi%E1%BB%9Bi-thi%E1%BB%87u-v%E1%BB%81-b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-c%E1%BB%A7a-protect360 h_01HE7S55TC4G31R9EANMKCZ7V5=report-types protect360-rawdata-report-types=c%C3%A1c-lo%E1%BA%A1i-b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-c%E1%BB%A7a-protect360 h_01HE7S55TCKQYTXPV6J54SHM0D=c%C3%A1c-lo%E1%BA%A1i-b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-c%E1%BB%A7a-protect360 h_01HE7S55TC4F5S243BSGN74RDK=postattribution-reports using-postattribution-reports=s%E1%BB%AD-d%E1%BB%A5ng-b%C3%A1o-c%C3%A1o-h%E1%BA%ADu-ph%C3%A2n-b%E1%BB%95 h_01HE7S55TC7KCF75KFXHCE3K2K=s%E1%BB%AD-d%E1%BB%A5ng-b%C3%A1o-c%C3%A1o-h%E1%BA%ADu-ph%C3%A2n-b%E1%BB%95 h_01HE7S55TCR8BKZ0PQ5B14X3X4=v%C3%AD-d%E1%BB%A5 h_01HE7S55TC95YC1BJJ0ZERCQ14=raw-data-availability-by-tool-type protect360-rawdata-availability-by-tool-type=t%C3%ADnh-kh%E1%BA%A3-d%E1%BB%A5ng-c%E1%BB%A7a-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-protect-360-theo-lo%E1%BA%A1i-c%C3%B4ng-c%E1%BB%A5 h_01HE7S55TCH4CES29C5J3QXQK4=t%C3%ADnh-kh%E1%BA%A3-d%E1%BB%A5ng-c%E1%BB%A7a-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-protect-360-theo-lo%E1%BA%A1i-c%C3%B4ng-c%E1%BB%A5 getting-raw-data-reports=nh%E1%BA%ADn-b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 h_01HE7S55TC3MRT6E9QV0J0X6FC=nh%E1%BA%ADn-b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 h_01HE7S55TCBVFQ1DH06G53BNEN=download h_01HE7S55TCMT81J4SWBFQFYV2C=pull-api pull-api-raw-data-report-parameters=th%C3%B4ng-s%E1%BB%91-b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-api-pull h_01HE7S55TCRRD95D0QPCXBRF8T=th%C3%B4ng-s%E1%BB%91-b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-api-pull h_01HE7S55TCMAY86J1HKYB0APZ6=data-locker protect360-report-structure=c%E1%BA%A5u-tr%C3%BAc-b%C3%A1o-c%C3%A1o-protect360 h_01HE7S55TCS91ZC9V3K0VDSVXK=c%E1%BA%A5u-tr%C3%BAc-b%C3%A1o-c%C3%A1o-protect360 blocked-reasons=l%C3%BD-do-b%E1%BB%8B-ch%E1%BA%B7n h_01HE7S55TC1ZEDD5ABD21FCPY2=l%C3%BD-do-b%E1%BB%8B-ch%E1%BA%B7n h_01HE7S55TDMDSVQCVSV5YS3CZN=click-level-blocked-reasons h_01HE7S55TD754T07FWHFK5P71K=install-level-blocked-reasons install-level-fake-install-block-reasons=c%E1%BA%A5p-c%C3%A0i-%C4%91%E1%BA%B7t-l%C3%BD-do-ch%E1%BA%B7n-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-gi%E1%BA%A3 h_01HE7S55TDHTE5P47N1CCREGZX=c%E1%BA%A5p-c%C3%A0i-%C4%91%E1%BA%B7t-l%C3%BD-do-ch%E1%BA%B7n-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-gi%E1%BA%A3 install-level-attribution-hijacking-block-reasons=c%E1%BA%A5p-c%C3%A0i-%C4%91%E1%BA%B7t-l%C3%BD-do-ch%E1%BA%B7n-%C4%91%C3%A1nh-c%E1%BA%AFp-ph%C3%A2n-b%E1%BB%95 h_01HE7S55TDFA6WGAHE80ECV8CA=c%E1%BA%A5p-c%C3%A0i-%C4%91%E1%BA%B7t-l%C3%BD-do-ch%E1%BA%B7n-%C4%91%C3%A1nh-c%E1%BA%AFp-ph%C3%A2n-b%E1%BB%95 h_01HE7S55TDCHG0CVJA3JRSAW3G=cluster-level-blocked-reasons cluster-level-fake-install-block-reasons=c%E1%BA%A5p-c%E1%BB%A5m-l%C3%BD-do-ch%E1%BA%B7n-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-gi%E1%BA%A3 h_01HE7S55TDBES0BY0FF3WKSSVG=c%E1%BA%A5p-c%E1%BB%A5m-l%C3%BD-do-ch%E1%BA%B7n-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-gi%E1%BA%A3 cluster-level-attribution-hijacking-block-reasons=c%E1%BA%A5p-c%E1%BB%A5m-l%C3%BD-do-ch%E1%BA%B7n-%C4%91%C3%A1nh-c%E1%BA%AFp-ph%C3%A2n-b%E1%BB%95 h_01HE7S55TD3M45TH4PY2W805W7=c%E1%BA%A5p-c%E1%BB%A5m-l%C3%BD-do-ch%E1%BA%B7n-%C4%91%C3%A1nh-c%E1%BA%AFp-ph%C3%A2n-b%E1%BB%95 h_01HE7S55TDGB05PEZX8KS3J3QJ=inapp-level-blocked-reasons inapp-level-block-reasons=l%C3%BD-do-ch%E1%BA%B7n-c%E1%BA%A5p-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HE7S55TD661EHCV50S9BW5MS=l%C3%BD-do-ch%E1%BA%B7n-c%E1%BA%A5p-trong-%E1%BB%A9ng-d%E1%BB%A5ng retargeting=nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i h_01HE7S55TDSYDC8BWZ8D8DF9JE=nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i hijacked-installs-attribution-correction=%C4%91i%E1%BB%81u-ch%E1%BB%89nh-ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-b%E1%BB%8B-%C4%91%C3%A1nh-c%E1%BA%AFp h_01HE7S55TD8SDCQJCCYQC0MNES=%C4%91i%E1%BB%81u-ch%E1%BB%89nh-ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-b%E1%BB%8B-%C4%91%C3%A1nh-c%E1%BA%AFp" />
