---
title: Di chuyển sang AppsFlyer từ các nhà cung cấp khác
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2019-07-01T13:11:37Z'
  edited_at: '2023-08-30T15:43:41Z'
  id: 360001923697
  locale: vi
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/vi/articles/360001923697
---
> **Khái quát:** Lập kế hoạch di chuyển sang AppsFlyer từ một nhà cung cấp phân bổ khác. Hiểu cách tránh bị tính phí gấp đôi, trùng lặp dữ liệu và mất dữ liệu trong quá trình di chuyển.

![quy trình di chuyển](https://files.readme.io/31d67493ae3ae6912b4da3163ebb731a8d58494c3007ef1d08cb7332226d9e81-360017326677.png)

## Tổng quan

Việc di chuyển sang AppsFlyer từ một nhà cung cấp khác sẽ bao gồm các nhiệm vụ chính sau:

* [Tích hợp SDK](/docs/migration-to-appsflyer-from-other-vendors#tích-hợp-sdk)
* [Di chuyển thiết bị](/docs/migration-to-appsflyer-from-other-vendors#di-chuyển-thiết-bịtùy-chọn)
* [Di chuyển chiến dịch](/docs/migration-to-appsflyer-from-other-vendors#di-chuyển-chiến-dịch)
* [Thiết lập báo cáo dữ liệu](/docs/migration-to-appsflyer-from-other-vendors#thiết-lập-báo-cáo-dữ-liệu)

Bạn có thể xử lý các nhiệm vụ này đồng thời. Tuy nhiên, chúng tôi đề nghị bạn nên:

* Hoàn thành tất cả các nhiệm vụ trước khi phát hành ứng dụng bạn đã cập nhật với SDK AppsFlyer.
* Tạm dừng các chiến dịch tiếp thị hiện tại trước khi thực hiện di chuyển ID thiết bị.

> 📘 **Lưu ý**
>
> Nếu bạn muốn so sánh phép đo phân bổ giữa MMP hiện tại và AppsFlyer cho cùng một chiến dịch và nguồn truyền thông, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/measuring-attribution-with-multiple-mmps">bài viết này</Anchor>.

## Công việc

Bảng sau đây mô tả phạm vi công việc cần thiết cho mỗi tác vụ. Để xem phân tích chính xác các tác vụ chung theo thứ tự, bạn phải hoàn thành chúng, cũng như để ghi lại tiến trình của bạn, hãy tải xuống <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/1x6kdhfnfKLYHJgsROPUv7pQYC6i-Q5H3DdejBr8jKjw/export?format=xlsx">bảng tính này</Anchor>

#### Phạm vi công việc

<table><thead><tr><th>Nhiệm vụ</th><th>Hành động cần thiết</th><th>Đối tượng tham gia</th><th>Thời gian dự kiến</th><th>Nhận xét</th></tr></thead><tbody><tr><td>Điều kiện tiên quyết</td><td><ol><li> <a href="https://www.appsflyer.com/get-started" target="_blank">Tạo tài khoản AppsFlyer</a>.</li><li> <a href="./adding-an-app-to-appsflyer" target="_blank">Thêm ứng dụng</a> vào AppsFlyer.</li><li>[Tùy chọn] Thay đổi <a href="./set-up-re-attribution-window" target="_blank">khung thời gian phân bổ lại</a> mặc định 90 ngày để phù hợp <span>với định nghĩa về người dùng đang hoạt động.</span> </li></ol></td><td>Nhà tiếp thị/Người dùng bảng điều khiển AppsFlyer</td><td><p>2 giờ</p></td><td> </td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#tích-hợp-sdk">Tích hợp SDK</a></td><td><ul><li>Tích hợp SDK AppsFlyer vào ứng dụng của bạn.</li><li>Ánh xạ S2S hoặc các sự kiện trong ứng dụng SDK.</li><li>Cập nhật phiên bản ứng dụng trong các cửa hàng ứng dụng.</li></ul></td><td>Nhà phát triển ứng dụng</td><td><p>1-2 tuần</p></td><td><ul><li> <strong>Khuyến nghị</strong>: Tích hợp SDK AppsFlyer vào ứng dụng tiền sản xuất để thử nghiệm.</li><li>Ứng dụng sản xuất phải được cập nhật trong cửa hàng ứng dụng sau khi hoàn thành tất cả các tác vụ khác.</li></ul></td></tr><tr><td> <a href="./migration-to-appsflyer-from-other-vendors#di-chuyển-thiết-bịtùy-chọn">Di chuyển thiết bị</a> [tùy chọn]</td><td>Di chuyển ID thiết bị để tránh phân bổ hai lần cho người dùng hiện có của bạn.</td><td>Kỹ sư dữ liệu</td><td>1-2 tuần</td><td rowspan="2"><ul><li>Xem xét tạm dừng các chiến dịch hiện có trước khi di chuyển và tiếp tục các chiến dịch đó sau khi đã cập nhật phiên bản ứng dụng. </li><li>Cân nhắc việc lặp lại quy trình di chuyển thiết bị vào ngày di chuyển cuối cùng để đảm bảo phạm vi hoàn chỉnh. </li></ul></td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#di-chuyển-chiến-dịch">Di chuyển chiến dịch</a></td><td><ul><li>Tích hợp mạng quảng cáo vào AppsFlyer</li><li>Di chuyển các chiến dịch hiện tại từ:  <ul><li>SRN</li><li>Mạng quảng cáo không phải SRN</li><li>Truyền thông Sở hữu</li></ul></li></ul></td><td>Nhà tiếp thị/Quản lý UA</td><td>1-3 tuần</td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#thiết-lập-báo-cáo-dữ-liệu">Thiết lập báo cáo dữ liệu</a></td><td><ul><li>Điều chỉnh/ánh xạ cấu trúc báo cáo hiện tại của bạn với cấu trúc của AppsFlyer.</li><li>Chuẩn bị nhận báo cáo AppsFlyer.</li></ul></td><td>Kỹ sư dữ liệu</td><td>2-4 tuần</td><td> </td></tr></tbody></table>

### Tích hợp SDK

<div id="sdk-integration::c763138b" />

<Accordion title="Tích hợp SDK">

SDK AppsFlyer được tích hợp vào ứng dụng là liên kết giữa ứng dụng và nền tảng AppsFlyer. Tính năng này sẽ báo cáo số lượt cài đặt ứng dụng, số lần mở ứng dụng, sự kiện trong ứng dụng, v.v.

**Để tích hợp SDK AppsFlyer**:

1. Tích hợp SDK AppsFlyer vào ứng dụng.  
   Xem hướng dẫn tích hợp SDK <Anchor target="_blank" href="/marketers/vi/docs/sdk-integration-overview">Android</Anchor> và <Anchor target="_blank" href="/marketers/vi/docs/sdk-integration-overview">iOS</Anchor>.
2. Ánh xạ các sự kiện trong ứng dụng mà bạn muốn ghi lại, sử dụng lược đồ AppsFlyer.  
   Điều này có thể được thực hiện thông qua <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview">SDK</Anchor> hoặc <Anchor target="_blank" href="/marketers/vi/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>.
3. Xóa SDK của nhà cung cấp phân bổ cạnh tranh.  
   Bạn có thể thực hiện việc này ngay và chuyển riêng sang chỉ AppsFlyer hoặc chạy đồng thời cả hai SDK trong vài tuần. Xem kết quả phân tích các tùy chọn này trong bảng bên dưới.  

| Tùy chọn | Điều gì sẽ xảy ra sau  <br />khi cập nhật bản phát hành phiên bản ứng dụng | Tác động |
| --- | --- | --- |
| Xóa SDK của đối thủ cạnh tranh (khuyến nghị) | Chỉ AppsFlyer ghi nhận các lượt cài đặt mới và cập nhật người dùng.  <br />Đối thủ cạnh tranh vẫn hiển thị các sự kiện do người dùng thực hiện cho đến khi người dùng cập nhật ứng dụng của họ. | <ul><li>Chuyển đổi nhanh chóng.</li><li>Không phân bổ kép.</li></ul> |
| Giữ SDK của đối thủ cạnh tranh trong giai đoạn chuyển tiếp | AppsFlyer và đối thủ cạnh tranh phân bổ lượt cài đặt mới và báo cáo các sự kiện. Sau này, hãy xóa SDK của đối thủ cạnh tranh. | <ul><li>Có thể xác thực dữ liệu. Có nghĩa là, bạn có thể đối chiếu dữ liệu từ AppsFlyer và nhà cung cấp khác.</li><li>Phân bổ kép, có thể làm phát sinh gấp đôi chi phí với các mạng quảng cáo. Xem ví dụ dưới đây.</li><li>Khối lượng công việc cao hơn.</li></ul> |

4. Sau khi hoàn thành tất cả các nhiệm vụ khác trong phạm vi công việc, hãy cập nhật phiên bản ứng dụng có SDK AppsFlyer ra thị trường. Người dùng mới được phân bổ bởi AppsFlyer.   
   **Lưu ý**:
   * Đảm bảo cập nhật ứng dụng cho iOS, Google Play và mọi thị trường Android ngoài cửa hàng có liên quan.
   * Ứng dụng Android của bạn có thể tồn tại trong các trang APK không chính thức, ngay cả khi bạn không biết trang đó (tìm kiếm trên web để biết tên gói ứng dụng của bạn). Các trang web APK cần một thời gian mới có thể cập nhật lên phiên bản mới nhất, vì vậy chúng có thể mang đến cho người dùng tự nhiên cài đặt phiên bản cũ mà không có SDK AppsFlyer.
   * Thời gian hoàn thành quá trình phát hành bản cập nhật ứng dụng trên cửa hàng ứng dụng có thể mất vài ngày. Người dùng cài đặt trong thời gian này vẫn có thể nhận được phiên bản trước đó.

</Accordion>

### Di chuyển thiết bị—tùy chọn

<div id="about-device-migration" />

<Accordion title="Giới thiệu về di chuyển thiết bị">

Di chuyển thiết bị là quá trình tải lên danh sách các ID thiết bị người dùng hiện có của bạn (IDFA, IDFV, GAID, CUID) vào AppsFlyer. Bạn nên thực hiện quy trình này trước khi phát hành phiên bản ứng dụng mới - phiên bản sẽ bao gồm SDK AppsFlyer. Có hai tùy chọn khi di chuyển thiết bị, [di chuyển có phân bổ](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration) hoặc [di chuyển không được phân bổ](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration).

Việc di chuyển thiết bị giúp giải quyết các vấn đề về dữ liệu liên quan đến người dùng ứng dụng hiện tại của bạn, những người đã tải xuống ứng dụng và được nhà cung cấp trước đó của bạn phân bổ. Ví dụ: SRN tính phí gấp đôi, xảy ra khi người dùng ban đầu được phân bổ cho một SRN theo nhà cung cấp trước của bạn và những người vẫn còn trong khung thời gian xem lại, được SRN xác nhận quyền sở hữu lại trong AppsFlyer.

> 📄 **Ví dụ**
>
> * Một người dùng mới nhấp vào quảng cáo trên ứng dụng Facebook và cài đặt ứng dụng của bạn vào ngày 15 tháng 6.
> * Vào ngày 24 tháng 6, người dùng này cập nhật ứng dụng lên phiên bản có SDK AppsFlyer và khởi chạy. Đối với AppsFlyer, đây là người dùng mới, cần được phân bổ theo thời gian thực.
> * AppsFlyer sẽ truy vấn quảng cáo Meta bằng ID thiết bị của người dùng. Vì người dùng vẫn ở trong khung thời gian xem lại 28 ngày của quảng cáo Meta, nên quảng cáo Meta sẽ tự phân bổ người dùng. Điều này sẽ khiến chủ sở hữu ứng dụng phát sinh một khoản phí gấp đôi cho cùng một người dùng.

Sau khi bạn di chuyển thiết bị, dữ liệu sẽ phản ánh trong AppsFlyer như sau:

* **Dữ liệu** **lượt cài đặt:** Tương tự như <Anchor target="_blank" href="/marketers/vi/docs/set-up-re-attribution-window#reinstall">Lượt cài đặt lại</Anchor>, các thiết bị đã di chuyển không có dữ liệu cài đặt. Lượt cài đặt của thiết bị đã di chuyển không được hiển thị trong AppsFlyer.
* **Dữ liệu phiên và sự kiện trong ứng dụng**: Được ghi nhận và hiển thị dưới dạng tự nhiên đối với [phương pháp di chuyển thiết bị không được phân bổ](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration) hoặc được phân bổ cho nguồn truyền thông và chiến dịch, nếu sử dụng phương pháp [đã phân bổ](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration).
* **Nhắm mục tiêu lại**: Lượt phân bổ lại và thu hút lại được hiển thị bình thường.
* **Dữ liệu hoạt động:** Hiển thị bình thường.
* **Dữ liệu giữ chân người dùng và nhóm người**: Thiết bị đã di chuyển không có hồ sơ cài đặt. Do đó, chúng không được liên kết với bất kỳ nhóm người nào và không được hiển thị trong báo cáo Giữ chân người dùng và Nhóm người.

</Accordion>

<div id="how-to-migrate-devices" />

<Accordion title="Cách di chuyển thiết bị">

**Để di chuyển thiết bị:**

1. Quyết định cần di chuyển nhóm người dùng nào. Bạn có thể di chuyển tất cả người dùng hiện có (điều này có thể khiến bạn không nhận được chính xác dữ liệu phân bổ lại từ AppsFlyer) hoặc những người dùng chỉ mới cài đặt ứng dụng của bạn gần đây (điều này có thể dẫn đến việc những người dùng cũ hơn bị tính phí gấp đôi).  
   **Chúng tôi đề nghị bạn nên di chuyển những người dùng đang hoạt động trong khung thời gian phân bổ lại hiện tại của bạn.** Ví dụ: nếu ứng dụng của bạn có khung thời gian phân bổ lại là 90 ngày, thì hãy di chuyển những người dùng có ít nhất một phiên hoạt động trong 90 ngày trước đó.
2. [Tùy chọn] Yêu cầu nhà tiếp thị/quản lý UA tạm dừng các chiến dịch tiếp thị hiện tại (từ SRN, mạng quảng cáo không phải SRN, phương tiện truyền thông sở hữu, v.v.) cho đến sau khi di chuyển thiết bị.   
   Nếu bạn quyết định không tạm dừng chiến dịch, hãy di chuyển mọi ID thiết bị còn lại từ nhà cung cấp khác ngay sau khi cập nhật phiên bản ứng dụng có SDK AppsFlyer được phát hành cho các cửa hàng ứng dụng.
3. Chuẩn bị tệp CSV dựa trên nhóm người dùng đã chọn, sử dụng cấu trúc di chuyển được [phân bổ](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration) hoặc [không được phân bổ](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration). <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?output=csv">Xem CSV mẫu</Anchor>
4. Gửi CSV cho AppsFlyer CSM của bạn.  
   CSM của bạn sẽ di chuyển ID thiết bị sang AppsFlyer.

</Accordion>

<div id="attributed-migration" />

<Accordion title="Di chuyển phân bổ">

Các thiết bị được di chuyển sang AppsFlyer bằng phương thức này sẽ được ghi nhận và hiển thị sự kiện trong ứng dụng và phiên của chúng theo nguồn truyền thông được báo cáo bởi nhà cung cấp phân bổ trước đó và theo chính sách lưu giữ dữ liệu của mạng quảng cáo.

#### Cấu trúc CSV di chuyển thiết được phân bổ

| Tên  <br />cột | Mô tả | Bắt buộc | Ví dụ: |
| --- | --- | --- | --- |
| app\_id | ID ứng dụng như khi xuất hiện trong bảng điều khiển AppsFlyer | Có | <ul><li>Android: com.great.app1</li><li>iOS: id123456789</li></ul> |
| platform | Nền tảng thiết bị: iOS hoặc Android | Có | <ul><li>ios</li><li>android</li></ul> |
| device\_id | <ul><li>Android: gaid</li><li>iOS: IDFV (khuyến nghị, nếu có) hoặc IDFA</li><li>Không được sao chép cùng một ID thiết bị và ID ứng dụng kết hợp vào nhiều hàng. Nếu xảy ra trùng lặp, lần xuất hiện cuối cùng trong tệp sẽ được sử dụng.</li></ul> | Có | <ul><li>**gaid** (chữ thường): 9c9a82fb-d5de-4cd1-90c3-527441c11828</li><li>**IDFV** (chữ hoa): A7328D98-A973-402A-8B87-D22A8611F2AF</li><li>**IDFA** (chữ hoa): 9876F1SS-2983-3855-27RR-2R626772VFNB</li></ul> |
| id\_type | <ul><li>Android: advertiserId (cũng hỗ trợ amazon\_aid)</li><li>iOS:idfa hoặc idfv</li><li>Hiện tại, các mã định danh khác, OAID, IMEI và ID Android không được hỗ trợ.<br />Sử dụng tính năng di chuyển không phân bổ cho người dùng Android không phải từ Google Play.</li></ul> | Có | <ul><li>advertiserId</li><li>idfa</li><li>idfv</li></ul> |
| install\_time | Thời gian cài đặt ứng dụng gốc với định dạng UTC <Anchor target="_blank" href="http://joda-time.sourceforge.net/cal_iso.html">ISO 8601</Anchor>:<br />**yyyy-mm-ddTHH:MM:SS.SSS**<ul><li>**Best practice**: Để trống trường này. Trong trường hợp này, thời gian di chuyển được sử dụng thay thế.</li><li>Nếu bạn điền ngày thì đó phải là ngày hợp lệ trước đó, không cũ hơn khoảng thời gian phân bổ lại.<ul><li>Trong một số trường hợp, các thiết bị đã di chuyển khi khởi chạy lần đầu sẽ được coi là lượt cài đặt mới.<br />Ví dụ 1: Thiết bị có thời gian cài đặt trước ngày tạo tệp trừ đi khoảng thời gian phân bổ lại ứng dụng sẽ không được di chuyển bằng phân bổ. Trong lần khởi chạy đầu tiên, thiết bị được coi là một lượt cài đặt mới (rất có thể là tự nhiên).<br />Ví dụ 2: Một thiết bị được di chuyển có thời gian cài đặt nhưng lần khởi chạy đầu tiên chỉ diễn ra sau quá trình di chuyển và nằm ngoài khoảng thời gian phân bổ lại. Trong trường hợp này, một lượt cài đặt mới sẽ được ghi lại.</li></ul></li></ul> | Không | 2018-01-22T08:45:33.412 |
| media\_source | <ul><li>Hoặc:<ul><li>ID đối tác AppsFlyer như xuất hiện trong bảng điều khiển AppsFlyer</li><li>Nguồn truyền thông tùy chỉnh (không được là ID đối tác).</li></ul></li><li>Để lấy danh sách các ID đối tác theo yêu cầu của AppsFlyer:<ul><li><Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner">Bật tất cả các đối tác tích hợp liên quan.</Anchor></li><li>Chạy <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_v1-integrations">API nhận tích hợp hoạt động</Anchor> để lấy danh sách tất cả các tích hợp hoạt động.</li><li>Dùng **media\_source\_name** từ API làm giá trị **media\_source** trong CSV.</li><li>Ngoại lệ:<ul><li>Đối với Apple Search Ads, sử dụng **Apple Search Ads**.</li><li>Đối với Twitter, sử dụng **twitter**.</li></ul></li></ul></li><li>Định dạng: Giá trị có phân biệt chữ hoa chữ thường</li></ul> | Có | Không tự nhiên: facebook\_int, googleadwords\_int<br /><br />Tự nhiên: organic |
| integrated\_partner | <ul><li>Cho biết nguồn truyền thông có phải là đối tác tích hợp hay không. Có nghĩa là nguồn truyền thông tự nhiên hoặc tùy chỉnh.</li><li>Định dạng: Giá trị có phân biệt chữ hoa chữ thường</li></ul> | Có | <ul><li>có</li><li>không (nếu media\_source là tùy chỉnh)</li></ul> |
| chiến dịch | Để biết thêm thông tin về phân bổ chi tiết, hãy cung cấp tên chiến dịch ban đầu.<br /><br />Định dạng: Chuỗi | Không |  |
| campaign\_id | Để biết thêm thông tin về phân bổ chi tiết, hãy cung cấp id chiến dịch ban đầu.<br /><br />Định dạng: Chuỗi không được phép sử dụng dấu cách | Không |  |

**Quy tắc tệp tin CSV:**

* Tệp tin CSV có thể chứa thiết bị của người dùng từ nhiều ứng dụng.
* Không được sao chép cùng một ID thiết bị và ID ứng dụng kết hợp vào nhiều hàng. Nếu xảy ra trùng lặp, lần xuất hiện cuối cùng trong tệp sẽ được sử dụng.
* Tất cả các tiêu đề cột phải bao gồm: app\_id, platform, device\_id, id\_type, install\_time, media\_source, integrated\_partner, campaign, campaign\_id. **Lưu ý**: Thứ tự các trường rất quan trọng và phải được duy trì.
* Bạn có thể thêm cả IDFV và IDFA cho cùng thiết bị, nhưng chúng phải ở các hàng riêng. Mọi trường trnog các hàng riêng phải giống nhau, ngoại trừ device\_id.
* Mỗi hàng phải chứa đúng 9 trường được phân tách bằng dấu phẩy.
* Để trống các trường không bắt buộc (trống).
* Các tệp tin có thể chứa tới 20 triệu hàng.
* Nếu bạn có nhiều tệp tin, hãy đặt tên duy nhất cho mỗi tệp.
* Mã hóa dữ liệu bằng UTF-8.
* [Tùy chọn] Nén tệp tin bằng ZIP hoặc GZIP.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=0&single=true&output=csv">Xem CSV mẫu</Anchor>

</Accordion>

<div id="nonattributed-migration" />

<Accordion title="Di chuyển không phân bổ">

Các thiết bị được di chuyển sang AppsFlyer bằng phương thức này sẽ được ghi nhận (nhưng không hiển thị) dưới dạng người dùng tự nhiên. Dữ liệu phiên và sự kiện trong ứng dụng của họ cũng được ghi nhận và hiển thị dưới dạng tự nhiên.

#### Cấu trúc tệp tin CSV di chuyển thiết bị không phân bổ

| Cột | Thời điểm sử dụng | Ví dụ: |
| --- | --- | --- |
| ID Ứng dụng + IDFA/GAID/IDFV | <ul><li>Nếu tất cả người dùng Android của bạn có mã định danh GAID.</li><li>Chỉ người dùng iOS</li></ul> | [<Image alt="device_migration_file_option_1.png" src="https://files.readme.io/e4902c1fd33dc348d636f0c9a571bddad966c37aa1f8fad19cf6160c8c1b7dfb-360003138317.png" width="244px" />](https://files.readme.io/e4902c1fd33dc348d636f0c9a571bddad966c37aa1f8fad19cf6160c8c1b7dfb-360003138317.png) |
| ID Ứng dụng + ID Thiết bị + Loại ID Thiết bị | <ul><li>Nếu một số người dùng Android của bạn chỉ có IMEI hoặc ID Android, nhưng không có GAID (thị trường ngoài cửa hàng, phiên bản Android dưới 4.4.2).</li><li>ID Android cần có định dạng thập lục phân.</li></ul>**Lưu ý**:<ul><li>Sử dụng các chuỗi chính xác cho cột **ID type**: advertiserId (cũng hỗ trợ amazon\_aid), idfa, idfv, android\_id, imei.</li><li>Nếu bạn sử dụng android\_id hoặc imei và sau này AppsFlyer nhận được mã định danh tốt hơn thì thuộc tính mới có thể được ghi lại.</li></ul> | [<Image alt="device_migration_file_option_2.png" src="https://files.readme.io/a85463bc7fd8f08e9c5e20d09b3b39f951547f18402c225ef3d952b18923b648-360003224698.png" width="244px" />](https://files.readme.io/a85463bc7fd8f08e9c5e20d09b3b39f951547f18402c225ef3d952b18923b648-360003224698.png) |

**Quy tắc tệp tin CSV:**

* Tệp tin CSV có thể chứa thiết bị của người dùng từ nhiều ứng dụng.
* Mỗi hàng chứa một ID thiết bị cho mỗi ứng dụng.
* Tệp tin phải bao gồm tất cả các tiêu đề cột như sau:
  * Tùy chọn 1: Tệp tin phải bao gồm tất cả các tiêu đề cột như sau: app\_id, device\_id
  * Tùy chọn 2: app\_id, device\_id, id\_type
* ID Ứng dụng ở dạng chữ thường
* Mã định danh Android ở dạng chữ thường
* IDFA/IDFV ở dạng chữ in hoa
* Cho phép tối đa 25 triệu hàng

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=935533759&single=true&output=csv">Xem CSV mẫu</Anchor>

</Accordion>

### Di chuyển chiến dịch

Chuyển các chiến dịch tiếp thị hiện tại sang AppsFlyer để bật tính năng phân bổ AppsFlyer và tránh phí gấp đôi và mất dữ liệu phân bổ.

**Lưu ý**: Bạn có thể chọn chỉ di chuyển một vài chiến dịch tiếp thị cùng một lúc. Trong trường hợp này, bạn có thể phân đoạn những người bạn muốn di chuyển theo nguồn truyền thông (ví dụ: mạng quảng cáo hoặc đại lý), địa lý hoặc chiến dịch.

<div id="srns" />

<Accordion title="SRN">

SRN phản hồi Đối tác Đo lường trên Thiết bị di động (MMP) khi được truy vấn về lượt thu hút của các thiết bị cụ thể. Nếu hai MMP, ví dụ như AppsFlyer và một nhà cung cấp phân bổ cạnh tranh, truy vấn cùng một SRN về cùng một lượt cài đặt thiết bị, thì có thể phát sinh phí gấp đôi.

**Để di chuyển các chiến dịch SRN**:

* Kích hoạt và cấu hình <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns#srn-được-tích-hợp-với-appsflyer">SRN</Anchor> có liên quan trong AppsFlyer.

> 📘 **Lưu ý**
>
> * SRN có thể chạy nhiều MMP (ngoại trừ quảng cáo Meta và Twitter).
> * Quảng cáo Meta không thể bỏ trùng lặp các sự kiện trong ứng dụng.

</Accordion>

<div id="nonsrn-ad-networks" />

<Accordion title="Mạng quảng cáo không phải SRN">

Đường dẫn phân bổ của mạng quảng cáo ghi nhận lượt thu hút người dùng và sau đó được sử dụng để phân bổ lượt thu hút trở thành lượt cài đặt thực tế.

**Để di chuyển các chiến dịch mạng quảng cáo không phải SRN**:

1. <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner">Kích hoạt</Anchor> các mạng quảng cáo liên quan trong AppsFlyer.
2. <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#attribution-link-tab">Tạo các đường dẫn phân bổ AppsFlyer</Anchor> cho mỗi mạng quảng cáo.
3. Chuyển các đường dẫn hiện có trong từng chiến dịch của bạn bằng các đường dẫn phân bổ AppsFlyer.

</Accordion>

<div id="owned-media" />

<Accordion title="Truyền thông Sở hữu">

Truyền thông sở hữu tìm đến các đường dẫn phân bổ mà bạn sử dụng trong:

* Chia sẻ nội dung
* Chuyển đổi Web sang Ứng dụng
* Email
* SMS
* Bài đăng trên mạng xã hội
* Blog
* Cộng đồng Internet (Quora, v.v.)
* và nhiều hơn nữa...

Đối với các chiến dịch này, AppsFlyer sử dụng <Anchor target="_blank" href="/marketers/vi/docs/onelink-guide">liên kết tùy chỉnh OneLink</Anchor>. Liên kết tùy chỉnh OneLink chuyển hướng người dùng dựa trên thiết bị của họ đến đúng cửa hàng ứng dụng, trực tiếp vào ứng dụng hoặc đến URL web/trang đích.

**Để thay đổi liên kết của bạn cho các nhà cung cấp khác thành AppsFlyer OneLink:**

* Liên hệ với CSM của bạn, người này sẽ hỗ trợ bạn di chuyển hàng loạt tất cả các liên kết của bạn.

</Accordion>

<div id="skan" />

<Accordion title="SKAN">

Đối với phân bổ SKAdNetwork (SKAN), bạn chỉ có thể có một SDK cập nhật giá trị chuyển đổi. Nếu không, dữ liệu SKAN sẽ trở nên vô nghĩa. Do đó, hãy đảm bảo rằng sau khi di chuyển, chỉ SDK AppsFlyer mới được cập nhật giá trị chuyển đổi SKAN.

<Anchor target="_blank" href="/marketers/vi/docs/skan-conversion-studio">Tìm hiểu về cách thiết lập giá trị chuyển đổi SKAN trong AppsFlyer.</Anchor>

</Accordion>

### Thiết lập báo cáo dữ liệu

<div id="adapt-and-map-report-structures" />

<Accordion title="Điều chỉnh và ánh xạ cấu trúc báo cáo">

Trước khi di chuyển, hệ thống sẽ lưu trữ dữ liệu phân bổ của bạn từ nhà cung cấp hiện tại theo cấu trúc báo cáo, trường và thông số mà bạn đã thiết lập với họ. Để AppsFlyer báo cáo dữ liệu một cách chính xác, bạn phải điều chỉnh và ánh xạ cấu trúc báo cáo hiện tại của mình theo cấu trúc, trường và thông số báo cáo của AppsFlyer.

**Để điều chỉnh/ánh xạ cấu trúc báo cáo:**

* Hãy liên hệ với CSM AppsFlyer của bạn để được trợ giúp trong việc điều chỉnh/di chuyển nhanh chóng cấu trúc dữ liệu báo cáo của bạn từ Adjust, Branch/Tune hoặc Kochava sang AppsFlyer.

</Accordion>

<div id="prepare-report-methods" />

<Accordion title="Chuẩn bị các phương pháp báo cáo">

Bạn có thể sử dụng một số phương thức nhận dữ liệu báo cáo <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-apis">thô</Anchor> và <Anchor target="_blank" href="/marketers/vi/docs/analytics-and-aggregate-reporting-apis">hợp nhất</Anchor> từ AppsFlyer. Làm quen với các phương thức và thiết lập phương thức phù hợp với bạn.

Các phương pháp báo cáo bao gồm:

* Xuất CSV
* API Push
* API Pull
* Data Locker

</Accordion>

<div data-zendesk-anchors="overview=t%E1%BB%95ng-quan 01H8EDSTP8N4GZJQ5J609C3DHM=t%E1%BB%95ng-quan 01H8EDZ8C5F06701DKT71D8T5P=l%C6%B0u-%C3%BD tasks=c%C3%B4ng-vi%E1%BB%87c 01H8EDSTP8YGDZBPEY1976JP8C=c%C3%B4ng-vi%E1%BB%87c scope-of-work=ph%E1%BA%A1m-vi-c%C3%B4ng-vi%E1%BB%87c 01H8EDSTP8HGCVHYX49GQQEHBB=ph%E1%BA%A1m-vi-c%C3%B4ng-vi%E1%BB%87c sdk-integration=t%C3%ADch-h%E1%BB%A3p-sdk h_01F0RDXJ4F34DDKRFV5G6WZQX0=t%C3%ADch-h%E1%BB%A3p-sdk 01H8EDSTP97C85X2E9EKBSVFQJ=sdk-integration::c763138b device-migration%E2%80%94optional=di-chuy%E1%BB%83n-thi%E1%BA%BFt-b%E1%BB%8Bt%C3%B9y-ch%E1%BB%8Dn h_01F0RDXVSQ13R9Q2KT7PK1KSCQ=di-chuy%E1%BB%83n-thi%E1%BA%BFt-b%E1%BB%8Bt%C3%B9y-ch%E1%BB%8Dn 01H8EDSTP9NDF6611MVEMWQSMZ=about-device-migration 01H8EDSTP93QJA4XZB6TDWWH1V=v%C3%AD-d%E1%BB%A5 01H8EDSTP9M2MDMGZ8QBQGPM6S=how-to-migrate-devices h_01F0RPWKQ4B0T1TXRGPVTYPPFB=attributed-migration attributed-device-migration-csv-structure=c%E1%BA%A5u-tr%C3%BAc-csv-di-chuy%E1%BB%83n-thi%E1%BA%BFt-%C4%91%C6%B0%E1%BB%A3c-ph%C3%A2n-b%E1%BB%95 01H8EDSTP9HABKEZJXMB84CDDE=c%E1%BA%A5u-tr%C3%BAc-csv-di-chuy%E1%BB%83n-thi%E1%BA%BFt-%C4%91%C6%B0%E1%BB%A3c-ph%C3%A2n-b%E1%BB%95 h_01F0RPX3SJ391M8SPNNN50DDA8=nonattributed-migration nonattributed-device-migration-csv-file-structure=c%E1%BA%A5u-tr%C3%BAc-t%E1%BB%87p-tin-csv-di-chuy%E1%BB%83n-thi%E1%BA%BFt-b%E1%BB%8B-kh%C3%B4ng-ph%C3%A2n-b%E1%BB%95 01H8EDSTP9AFDMQS6BPQJY19ZH=c%E1%BA%A5u-tr%C3%BAc-t%E1%BB%87p-tin-csv-di-chuy%E1%BB%83n-thi%E1%BA%BFt-b%E1%BB%8B-kh%C3%B4ng-ph%C3%A2n-b%E1%BB%95 campaign-migration=di-chuy%E1%BB%83n-chi%E1%BA%BFn-d%E1%BB%8Bch h_01F0RDY9WPSBZVP3B7XN3ZEJKK=di-chuy%E1%BB%83n-chi%E1%BA%BFn-d%E1%BB%8Bch 01H8EDSTP94KSE1J4J5B7HX96Z=srns 01H8EDSTP9ZGMHSM44BWGF1FJN=l%C6%B0u-%C3%BD-1 01H8EDSTP981XVWVM2NE0A45RM=nonsrn-ad-networks 01H8EDSTP9XNJA80Z5XR7WR9QN=owned-media 01H8EDSTP9Q8JAPNXSQWSHSK32=skan data-report-setup=thi%E1%BA%BFt-l%E1%BA%ADp-b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u h_01F0RDYKYHAEZ65GZBZ3MWTB5Z=thi%E1%BA%BFt-l%E1%BA%ADp-b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u 01H8EDSTP91E934EDXTPXW2ARJ=adapt-and-map-report-structures 01H8EDSTPAF8H5ESHDVK42M0RB=prepare-report-methods" />
