---
title: Phân bổ liên kết giới thiệu tải trước AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2022-03-02T09:54:10Z'
  edited_at: '2023-11-16T10:14:32Z'
  id: 4543811207313
  locale: vi
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/vi/articles/4543811207313
---
> **Khái quát:** AppsFlyer sử dụng liên kết giới thiệu tải trước để phân bổ lượt cài đặt cho chiến dịch tải trước, trong đó nhà tiếp thị ký kết hợp đồng với Nhà sản xuất Thiết bị Gốc (OEM), nhà cung cấp dịch vụ di động và đối tác khám phá ứng dụng để tải trước ứng dụng của họ tại nhà máy hoặc tại thời điểm thiết bị được người dùng bật lần đầu.

<div id="overview" />

## Phân bổ liên kết giới thiệu tải trước AppsFlyer

Trong chiến dịch tải trước, Nhà sản xuất Thiết bị Gốc (OEM), nhà cung cấp dịch vụ di động và đối tác khám phá ứng dụng tải trước ứng dụng trên thiết bị trước khi chúng đến tay người dùng. Điều này có thể được OEM thực hiện tại nhà máy hoặc các nhà cung cấp thực hiện khi kích hoạt thiết bị lần đầu.

Chiến dịch tải trước cho phép nhà quảng cáo tiếp cận lượng đối tượng tiềm năng lớn mà không cần chạy chiến dịch trực tuyến.

Phân bổ liên kết giới thiệu tải trước (1 trong 3 <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#preload-campaigns">phương thức phân bổ tải trước</Anchor>) cung cấp cho các nhà tiếp thị một cơ chế chính xác và bảo vệ quyền riêng tư để đo lường hiệu suất của các chiến dịch tải trước. Phương thức này cung cấp cho các nhà tiếp thị kết quả phân bổ có tính xác định và đồng thời đảm bảo rằng quyền riêng tư của người dùng được duy trì do phân bổ được thực hiện thông qua so khớp liên kết giới thiệu với liên kết giới thiệu được tạo độc lập với thiết bị và mã định danh người dùng.

Giải pháp cung cấp:

* Sự hỗ trợ minh bạch cho các bản cập nhật ứng dụng và lượt tải xuống lại ứng dụng.
* Khả năng hiển thị và đo lường giữa lần kích hoạt thiết bị đầu tiên và lần khởi chạy ứng dụng đầu tiên. Điều này cho phép bạn xem có bao nhiêu thiết bị đã được một đối tác cụ thể kích hoạt mà có ứng dụng được tải sẵn trên thiết bị và sau đó xem thời điểm ứng dụng được khởi chạy lần đầu tiên.

<div id="preload-referrer-options" />

### Các tùy chọn liên kết giới thiệu tải trước

Có thể sử dụng liên kết giới thiệu để phân bổ lượt cài đặt bằng cách tải trước hoặc bằng cách nhấp để tải xuống. Xem bảng sau để biết thêm chi tiết.

AppsFlyer ưu tiên cao nhất cho phân bổ tải trước. Điều này có nghĩa là nếu người dùng tương tác với các chiến dịch khác trước khi mở ứng dụng lần đầu tiên, thì chiến dịch tải trước vẫn được ghi nhận phân bổ. Các lượt tương tác khác được coi là lượt cài đặt được hỗ trợ. **Lưu ý**: Bạn có thể đặt mức độ ưu tiên bằng nhau cho các lượt tương tác tải trước. Điều này mang lại mức độ ưu tiên phân bổ cho các lượt nhấp chuột xác định ngang bằng với mức độ ưu tiên của các lượt tương tác tải trước trong toàn bộ khoảng thời gian xem lại tải trước; do đó, việc phân bổ cho chiến dịch tải trước có thể được thay thế bằng một lượt tương tác quảng cáo khác.

| Các tùy chọn liên kết giới thiệu | Mô tả | Loại so khớp dữ liệu thô của lượt cài đặt UA |
| --- | --- | --- |
| Tải trước | <ul><li>Ứng dụng được tải trước tại nhà máy hoặc được tải trước vào thời điểm thiết bị được kích hoạt lần đầu tiên. Ngoài ra, một trình hướng dẫn sẽ nhắc người dùng tải xuống ứng dụng khi thiết bị được kích hoạt lần đầu.</li><li>Một sự kiện tải trước, tương đương với một lượt nhấp, được báo cáo cho AppsFlyer khi thiết bị được bật lần đầu tiên.</li><li>Phân bổ diễn ra khi người dùng mở ứng dụng lần đầu tiên.</li><li>Sự kiện tải trước có mức độ ưu tiên phân bổ cao nhất (trừ khi bật mức độ ưu tiên phân bổ bằng nhau).</li></ul> | `preload_rfr` |
| Nhấp để tải xuống | <ul><li>Quá trình cài đặt ứng dụng diễn ra sau này trong vòng đời của thiết bị, thông qua thông báo đẩy, cửa hàng thay thế của đối tác, v.v.</li><li>Khi người dùng tương tác với quảng cáo hoặc thông báo đẩy, ứng dụng sẽ tự động được tải xuống và cài đặt trên thiết bị mà không cần chuyển hướng đến cửa hàng ứng dụng.</li><li>Phân bổ được ghi nhận bằng cách sử dụng quy tắc lượt nhấp cuối cùng sẽ thắng của AppsFlyer.</li></ul> | `af_referrer` |

<div id="view-preload-attribution-data" />

### Tính khả dụng của dữ liệu

Dữ liệu hiệu suất chiến dịch tương tác tải trước/nhấp để tải xuống sẽ được cung cấp như sau:

* **Bảng điều khiển tổng quan:** Tương tác được tính là lượt nhấp trong báo cáo hợp nhất và bảng điều khiển. Chúng được hợp nhất ở cấp đối tác tải trước (nguồn truyền thông) và cấp chiến dịch.
* **Dữ liệu thô:** Tương tác được cung cấp trong báo cáo lượt nhấp chỉ có sẵn qua Data Locker. Chúng được tìm thấy trong trường URL gốc và có thể được xác định trong thông số af\_engagement\_type dưới dạng preload hoặc click\_to\_download. Đối với lượt cài đặt, hãy xem bảng trong phần trước để biết loại so khớp được hiển thị như thế nào trong dữ liệu thô.

<div id="traits-and-limitations" />

<div id="set-up-samsung-preload-referrer-attribution" />

<div id="samsung-preload-referrer" />

<div id="set-up-preload-referrer-attribution" />

### Thiết lập phân bổ liên kết giới thiệu tải trước

Điều kiện tiên quyết:

* Tích hợp AppsFlyer <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-android-sdk-release-notes">Android SDK 6.10.1+</Anchor>.
* Ký kết hợp đồng với đối tác tải trước AppsFlyer.

**Để thiết lập phân bổ liên kết giới thiệu tải trước**:

1. Trong AppsFlyer, đi đến **Configuration** > **Active Integrations.**
2. Chọn đối tác tải trước.
3. Trong thẻ **Integration**, bật **Preload attribution**.  

   [<Image alt="" src="https://files.readme.io/d2c08125ca318b4bde60b51668692f21b88e292ca1b3f4fef54b77df779815cb-15585078780433.png" width="538px" />](https://files.readme.io/d2c08125ca318b4bde60b51668692f21b88e292ca1b3f4fef54b77df779815cb-15585078780433.png)
4. Đặt thời lượng **khung thời gian xem lại tải trước**. Phạm vi: 1-180 ngày.
5. [Tùy chọn] Bật **Preload equal attribution priority**.  
   Điều này mang lại mức độ ưu tiên phân bổ cho các lượt nhấp chuột xác định ngang bằng với mức độ ưu tiên của các lượt phân bổ tải trước, nghĩa là nếu một lượt nhấp chuột xác định được đăng ký giữa lượt tương tác và lượt cài đặt liên kết giới thiệu tải trước, thì lượt nhấp chuột sẽ nhận được phân bổ theo logic phân bổ tương tác cuối cùng tiêu chuẩn, thay vì bị thay thế bởi liên kết giới thiệu tải trước.
6. Nhấp vào **Save Integration**.
7. Cho đối tác tải trước biết rằng bạn đã sẵn sàng phân bổ chiến dịch của họ.

<div id="partners-supporting-preload-referrer-campaigns" />

### Các đối tác hỗ trợ các chiến dịch liên kết giới thiệu tải trước

<table><thead><tr><th rowspan="2">Đối tác</th><th rowspan="2">PID</th><th colspan="2">Các tùy chọn chiến dịch liên kết giới thiệu tải trước <span><a href="./set-up-appsflyer-preload-referrer-attribution#các-tùy-chọn-liên-kết-giới-thiệu-tải-trước">Tìm hiểu thêm</a></span> </th></tr><tr><th>Tải trước</th><th>Nhấp để tải xuống</th></tr></thead><tbody><tr><td>Nền tảng On Device của Digital Turbine</td><td>digitalturbine_int</td><td><span><span>✓</span></span></td><td><p>Sắp ra mắt</p></td></tr><tr><td>Aura từ Unity</td><td>aura_int</td><td><span><span>✓</span></span></td><td><p>Sắp ra mắt</p></td></tr><tr><td><span>Appnext</span></td><td><span>appnext_int</span></td><td><span><span>✓</span></span></td><td><p>Sắp ra mắt</p></td></tr><tr><td> <span>Glance</span><span></span><br/> </td><td><span>glance_int</span></td><td><span><span>✓</span></span></td><td><p><span><span>✓</span></span></p></td></tr></tbody></table>

<div data-zendesk-anchors="appsflyer-preload-referrer-attribution=ph%C3%A2n-b%E1%BB%95-li%C3%AAn-k%E1%BA%BFt-gi%E1%BB%9Bi-thi%E1%BB%87u-t%E1%BA%A3i-tr%C6%B0%E1%BB%9Bc-appsflyer h_01HEKAF7K41PH189PSCKBRF070=ph%C3%A2n-b%E1%BB%95-li%C3%AAn-k%E1%BA%BFt-gi%E1%BB%9Bi-thi%E1%BB%87u-t%E1%BA%A3i-tr%C6%B0%E1%BB%9Bc-appsflyer preload-referrer-options=c%C3%A1c-t%C3%B9y-ch%E1%BB%8Dn-li%C3%AAn-k%E1%BA%BFt-gi%E1%BB%9Bi-thi%E1%BB%87u-t%E1%BA%A3i-tr%C6%B0%E1%BB%9Bc h_01HEKAF7K4H3HNAMEYM6C58Y29=c%C3%A1c-t%C3%B9y-ch%E1%BB%8Dn-li%C3%AAn-k%E1%BA%BFt-gi%E1%BB%9Bi-thi%E1%BB%87u-t%E1%BA%A3i-tr%C6%B0%E1%BB%9Bc campaign-performance-data-availability=t%C3%ADnh-kh%E1%BA%A3-d%E1%BB%A5ng-c%E1%BB%A7a-d%E1%BB%AF-li%E1%BB%87u h_01HEKAF7K4GJDDPHCFTTC75YBS=t%C3%ADnh-kh%E1%BA%A3-d%E1%BB%A5ng-c%E1%BB%A7a-d%E1%BB%AF-li%E1%BB%87u run-preload-referrer-campaigns=thi%E1%BA%BFt-l%E1%BA%ADp-ph%C3%A2n-b%E1%BB%95-li%C3%AAn-k%E1%BA%BFt-gi%E1%BB%9Bi-thi%E1%BB%87u-t%E1%BA%A3i-tr%C6%B0%E1%BB%9Bc h_01HEKAF7K41RBRVXC6GF6PCN3Y=thi%E1%BA%BFt-l%E1%BA%ADp-ph%C3%A2n-b%E1%BB%95-li%C3%AAn-k%E1%BA%BFt-gi%E1%BB%9Bi-thi%E1%BB%87u-t%E1%BA%A3i-tr%C6%B0%E1%BB%9Bc partners-supporting-preload-referrer-campaigns=c%C3%A1c-%C4%91%E1%BB%91i-t%C3%A1c-h%E1%BB%97-tr%E1%BB%A3-c%C3%A1c-chi%E1%BA%BFn-d%E1%BB%8Bch-li%C3%AAn-k%E1%BA%BFt-gi%E1%BB%9Bi-thi%E1%BB%87u-t%E1%BA%A3i-tr%C6%B0%E1%BB%9Bc h_01HEKAF7K5CWX2P9TY8M0MTQAM=c%C3%A1c-%C4%91%E1%BB%91i-t%C3%A1c-h%E1%BB%97-tr%E1%BB%A3-c%C3%A1c-chi%E1%BA%BFn-d%E1%BB%8Bch-li%C3%AAn-k%E1%BA%BFt-gi%E1%BB%9Bi-thi%E1%BB%87u-t%E1%BA%A3i-tr%C6%B0%E1%BB%9Bc" />
