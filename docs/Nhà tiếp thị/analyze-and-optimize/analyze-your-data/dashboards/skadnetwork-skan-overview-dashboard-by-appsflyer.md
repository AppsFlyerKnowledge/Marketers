---
title: Bảng điều khiển tổng quan SKAdNetwork (SKAN) của AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-07-25T21:27:38Z'
  edited_at: '2024-09-12T12:26:13Z'
  id: 360011307357
  locale: vi
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/vi/articles/360011307357
---
> **Sơ lược:** Bảng điều khiển SKAdNetwork (SKAN) hiển thị các số liệu chiến dịch được báo cáo thông qua các bài đăng lại SKAN iOS và các điểm dữ liệu bổ sung trong khung thời gian đo lường người dùng ban đầu. Các số liệu theo mô hình xem xét chuyển đổi rỗng cũng có sẵn. Dữ liệu hiển thị bằng cách sử dụng ngày cài đặt hoặc ngày có bài đăng lại.

![SKAdHeadling8_us-en.png](https://files.readme.io/72c2eb452741cbd77c5828197f827f238c71c5097b8703528fa180dcafe2364c-360011831017.png)

<div id="dashboard-principles" />

## Nguyên tắc bảng điều khiển

Bảng điều khiển chứa dữ liệu hiệu suất chiến dịch SKAN và tuân thủ các nguyên tắc sau:

* Hãy xem xét rằng Apple, do <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork">cơ chế ngưỡng bảo mật</Anchor>, không phải lúc nào cũng điền giá trị chuyển đổi (CV). Đây được gọi là CV rỗng. Trong trường hợp CV rỗng, chỉ có một lượt cài đặt được ghi lại.
* Các số liệu được tính như sau:
  * Các số liệu không tự nhiên trong bảng điều khiển được tính bằng cách sử dụng dữ liệu đăng lại SKAN nhận được bởi AppsFlyer. Một số số liệu như lượt tải lại, ID ứng dụng nguồn và số liệu loại độ trung thực yêu cầu bạn định cấu hình ứng dụng của mình để <Anchor target="_blank" href="/marketers/vi/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">gửi các bản sao đăng lại trực tiếp đến AppsFlyer</Anchor>.
  * Số liệu tự nhiên được tính dưới dạng dữ liệu phân bổ AppsFlyer trừ dữ liệu phân bổ không tự nhiên SKAN. **Lưu ý**: Các số liệu tự nhiên không phải lúc nào cũng có sẵn. [Tìm hiểu thêm](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations).
    * Đảm bảo bạn lọc theo **Lượt cài đặt mới** trong trường kiểu cài đặt.
  * Một số số liệu, như doanh thu và ROAS, có cả giá trị ban đầu bắt nguồn từ các bài đăng lại và [giá trị theo mô hình](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) xem xét tỷ lệ CV rỗng.
* Lưu lượng truy cập do đại lý điều khiển được coi là đến từ một đại lý minh bạch.
* Tính cập nhật của dữ liệu:
  * Hằng ngày.
  * Các bài đăng lại nhận được vào một ngày nhất định sẽ được xử lý vào cuối ngày theo giờ UTC. Dữ liệu có sẵn vào 08:00 UTC của ngày hôm sau. Có nghĩa là các bài đăng lại nhận được vào thứ Hai có sẵn trong bảng điều khiển vào sáng thứ Ba.
  * Xem <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">thời gian cập nhật bảng điều khiển dự kiến.</Anchor>

<div id="skan-dashboard-view-options" />

## Các tùy chọn xem bảng điều khiển SKAN

Hiển thị dữ liệu bằng cách sử dụng [ngày cài đặt hoặc ngày có bài đăng lại](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#filter-options).

**Để chọn tùy chọn hiển thị ngày tháng**, trong AppsFlyer, từ menu bên, chọn **Analyze** (Phân tích) > **SKAN Overview (Tổng quan SKAN).** Trong thanh lọc, chọn tùy chọn ngày **Hiển thị theo**.

Các bộ lọc và tùy chọn hiển thị bổ sung được mô tả trong các phần sau.

<div id="dashboard-use" />

## Sử dụng bảng điều khiển

<div id="dashboard-settings" />

<Accordion title="Cài đặt bảng điều khiển">

Cài đặt bảng điều khiển khả dụng khi ứng dụng của bạn sử dụng <Anchor target="_blank" href="/marketers/vi/docs/skan-conversion-studio#fixed-modes">phép đo chuyển đổi chế độ cố định</Anchor> cũ để chọn sự kiện chuyển đổi.

**Để chọn sự kiện chuyển đổi**:

1. Ở phía trên bên phải của bảng điều khiển, nhấp vào **Dashboard settings** (Cài đặt bảng điều khiển).
2. Chọn một sự kiện chuyển đổi.
3. Nhấp vào apply (áp dụng).  
   Số liệu chuyển đổi được tính bằng sự kiện này.  
   Lưu ý! Cài đặt này liên quan đến hiển thị trong bảng điều khiển và không ảnh hưởng đến cài đặt CV trong ứng dụng.

</Accordion>

<div id="filter-options" />

<Accordion title="Tùy chọn lọc">

Sử dụng bộ lọc để tinh chỉnh thông tin được hiển thị.

| **Bộ lọc** | **Lưu ý** |
| --- | --- |
| Hiển thị bởi | <ul><li>**Ngày cài đặt**: Được lấy từ thời gian có bài đăng lại như sau:<ul><li>Nếu các bài đăng lại SKAN là SKAN V4, công thức ngày cài đặt là: Ngày cài đặt = thời gian có bài đăng lại - [độ dài khung thời gian tích lũy] - [độ trễ đăng lại trung bình].<ul><li>Đăng lại 1: ngày cài đặt = thời gian có bài đăng lại - 48h - 36h</li><li>Đăng lại 2: ngày cài đặt = thời gian có bài đăng lại - 168h - 84h</li><li>Đăng lại 3: ngày cài đặt = thời gian có bài đăng lại - 840h - 84h</li></ul></li><li>Nếu các bài đăng SKAN là SKAN V3 trở lên, công thức ngày cài đặt là: Ngày cài đặt = thời gian có bài đăng lại - 36 giờ - [phạm vi hoạt động cuối cùng trung bình].<ul><li>[Phạm vi hoạt động lần cuối trung bình] mặc định là 12 giờ.</li><li>Đối với giá trị chuyển đổi là 0, phạm vi hoạt động lần cuối trung bình được đặt thành 0.</li></ul></li></ul></li><li>**Ngày có bài đăng lại:**<ul><li>Ngày AppsFlyer nhận được bài đăng lại.</li><li>Khi bạn so sánh số liệu trong bảng điều khiển SKAN của AppsFlyer với các số liệu được cung cấp bởi mạng quảng cáo, hãy xem xét rằng các mạng quảng cáo thường cung cấp dữ liệu bằng cách sử dụng ngày có bài đăng lại.</li><li>Số liệu tự nhiên không khả dụng khi chọn tùy chọn này.</li><li>Trong trường hợp Google Ads, ngày có và ngày cài đặt không khác nhau.</li></ul></li></ul> |
| Phạm vi ngày | <ul><li>Ngày cài đặt được phân bổ. Ngày này được tính bằng cách sử dụng thời gian có bài đăng lại.</li><li>Nếu có số lượng lượt cài đặt lớn, sự không chính xác do các vấn đề về thời gian là không đáng kể.</li><li>Lượt cài đặt bao gồm các lượt tải lại.</li><li>Phạm vi ngày được giới hạn trong 90 ngày.</li></ul> |
| Nguồn truyền thông | <ul><li>Mạng quảng cáo được phân bổ với lượt cài đặt</li><li>Lưu lượng truy cập do đại lý điều khiển: Nguồn truyền thông thực tế hiển thị bất kể trạng thái minh bạch của đại lý. Do đó, bạn có thể thấy các nguồn truyền thông mà bạn không quen thuộc.</li></ul> |
| Chiến dịch | <ul><li>Tên chiến dịch và ID được thiết lập bởi mạng quảng cáo.</li><li>AppsFlyer phiên dịch ID chiến dịch đăng lại thành ID của mạng quảng cáo.</li><li>Nếu một ID chiến dịch nhất định có nhiều tên chiến dịch được liên kết với nó, thì tất cả tên sẽ hiển thị trong bảng điều khiển. Lưu ý! Mạng quảng cáo cung cấp ID chiến dịch và tên cho mỗi bài đăng lại. Cả ID chiến dịch và tên chiến dịch đều có sẵn trong dữ liệu thô và báo cáo SKAN tổng hợp.</li></ul> |
| ID trang | <ul><li>Ứng dụng nguồn hiển thị quảng cáo của bạn.</li><li>Sử dụng để phân tích các ứng dụng có lợi nhất cho bạn.</li></ul> |
| Địa lý | <ul><li>Lãnh thổ hoặc quốc gia</li><li>Địa lý được lấy bằng cách sử dụng dữ liệu được cung cấp bởi mạng quảng cáo hoặc sử dụng địa chỉ IP của thiết bị.</li><li>Bắt đầu từ iOS 14.6, địa chỉ IP của thiết bị được che bởi máy chủ proxy của Apple. Có nghĩa là vị trí địa lý của máy chủ Apple được phản ánh chứ không phải chính thiết bị.</li></ul> |
| Kiểu cài đặt | <ul><li>Lượt cài đặt</li><li>Lượt tải lại được báo cáo bởi cửa hàng ứng dụng</li></ul> |
| Bộ quảng cáo | Khả dụng nếu mạng quảng cáo cung cấp điểm dữ liệu này |
| Quảng cáo | Khả dụng nếu mạng quảng cáo cung cấp điểm dữ liệu này |
| Phiên bản | Phiên bản SKAN |

</Accordion>

<div id="headline-metrics" />

<Accordion title="Số liệu dạng tiêu đề">

| Số liệu | Lưu ý |
| --- | --- |
| Lượt cài đặt | SKAN không báo cáo lượt cài đặt nếu người dùng không tương tác với quảng cáo trước khi cài đặt. AppsFlyer tính toán các số liệu tự nhiên bằng cách sử dụng các lượt cài đặt được phân bổ của AppsFlyer (bảng điều khiển LTV.)<ul><li>Không tự nhiên: Các lượt cài đặt được phân bổ cho một nguồn truyền thông trong bối cảnh của chiến dịch ứng dụng đến ứng dụng trả phí và được báo cáo bởi SKAN.</li><li>Phần tự nhiên được tính toán bởi AppsFlyer bao gồm những điều sau:<ul><li>Các lượt cài đặt không do SKAN phân bổ hoặc không nhận được bài đăng lại từ mạng quảng cáo.</li><li>Clip Ứng dụng</li><li>Apple Search Ads.</li></ul></li></ul> |
| Các điểm tiếp xúc | Mạng quảng cáo báo cáo số lượt hiển thị và lượt nhấp chuột theo cú nhấp chuột hoặc API. |
| Tổng doanh thu | <ul><li>Có sẵn khi chế độ doanh thu đang hoạt động.</li><li>Hiển thị theo đơn vị USD hoặc đồng nội tệ cụ thể cho ứng dụng như được đặt trên <Anchor target="_blank" href="/marketers/vi/docs/app-settings">trang cài đặt của ứng dụng</Anchor>.</li><li>Phân chia giữa doanh thu tự nhiên và không tự nhiên.</li><li>Doanh thu tự nhiên được tính bằng doanh thu của tất cả các nguồn trừ đi doanh thu không tự nhiên.</li><li>Để cho phép so sánh tương tự như nhau, thời lượng của khung thời gian sau cài đặt của các lượt cài đặt tự nhiên và không tự nhiên là như nhau.</li><li>Bao gồm <Anchor target="_blank" href="/marketers/vi/docs/skan-modeled-data#null-conversion-values">dữ liệu theo mô hình</Anchor></li></ul>**Lưu ý**: Các số liệu tự nhiên không phải lúc nào cũng có sẵn. [Tìm hiểu thêm](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations). |
| Chi phí | <ul><li>Chi phí được báo cáo bởi mạng quảng cáo. Dữ liệu chi phí được báo cáo cho AppsFlyer bằng ROI360/API chi phí. Chi phí hiển thị theo đơn vị USD hoặc đồng nội tệ cụ thể cho ứng dụng như được đặt trên <Anchor target="_blank" href="/marketers/vi/docs/app-settings">trang cài đặt của ứng dụng</Anchor>.</li><li>Nếu tên chiến dịch thay đổi, chi phí hiển thị dưới tên chiến dịch gần đây nhất được sử dụng. (Nếu có nhiều tên chiến dịch)</li><li>Số liệu chi phí chỉ khả dụng cho bộ lọc Loại cài đặt = Tất cả bao gồm cả lượt cài đặt và lượt tải lại.</li></ul> |
| Tỷ lệ nhấp tới cài đặt | Tỷ lệ nhấp tới cài đặt. |
| Xu hướng thời kỳ liền kề | Giá trị xu hướng tính bằng % cho biết sự thay đổi của số liệu hiện tại so với số liệu của giai đoạn tương đương trước đó. Ví dụ: nếu giai đoạn hiện tại là ngày 1-10 tháng 5, giai đoạn trước là ngày 21-30 tháng 4. |

</Accordion>

<div id="charts" />

<Accordion title="Biểu đồ">

Các biểu đồ có sẵn phụ thuộc vào loại phép đo đã chọn.

<Table>
  <thead>
    <tr>
      <th>
        Số liệu biểu đồ
      </th>
      <th>
        Lưu ý
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Xu hướng thu về người dùng
      </td>
      <td>
        Phương diện có sẵn:

        * Tự nhiên
        * Không tự nhiên

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer2_us-en.png" src="https://files.readme.io/5c46dc05b4df07f3f60ff6015f115b4bc89106a6eb594f43d777af2100fdf460-360010368477.png" width="201px" />](https://files.readme.io/e30781379f0acb50d73e18e6c59ff76f8c91fa4cda6b92064310050555f826a3-360010359738.png)
      </td>
    </tr>
    <tr>
      <td>
        Chạm để chuyển đổi
      </td>
      <td>
        Lượt xem có sẵn:

        * Kích thước điểm tiếp xúc:
          * Lượt hiển thị
          * Lượt nhấp
        * Tỷ lệ nhấp tới cài đặt

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer3_us-en.png" src="https://files.readme.io/3e134f9411b356c8879dad8185b1762e6e039ed277da60fa9f67af351d8ab76d-360010368497.png" width="223px" />](https://files.readme.io/3e134f9411b356c8879dad8185b1762e6e039ed277da60fa9f67af351d8ab76d-360010368497.png)
      </td>
    </tr>
    <tr>
      <td>
        Số lượt cài đặt mỗi ngày được nhóm theo yếu tố thứ bậc quảng cáo
      </td>
      <td>
        Các yếu tố có sẵn: Nguồn truyền thông, Chiến dịch, ID trang web, Bộ quảng cáo, Quảng cáo, Phiên bản

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer4_us-en.png" src="https://files.readme.io/a9b80aaeb0f34a3054bfb97bb72ff2ab549ff88ae4f6af43bf1c5e1ab604d3d3-360010368537.png" width="206px" />](https://files.readme.io/a9b80aaeb0f34a3054bfb97bb72ff2ab549ff88ae4f6af43bf1c5e1ab604d3d3-360010368537.png)
      </td>
    </tr>
    <tr>
      <td>
        Phân tích số liệu theo các yếu tố thứ bậc quảng cáo
      </td>
      <td>
        Các yếu tố có sẵn: Nguồn truyền thông, Chiến dịch, ID trang web, Bộ quảng cáo, Quảng cáo, Phiên bản

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer5_us-en.png" src="https://files.readme.io/f201592b110b3137329f7ad3c48c53e20639fb664383d76ceba2a347e969f6e4-360010368657.png" width="198px" />](https://files.readme.io/f201592b110b3137329f7ad3c48c53e20639fb664383d76ceba2a347e969f6e4-360010368657.png)
      </td>
    </tr>
    <tr>
      <td>
        Sự kiện hàng đầu
      </td>
      <td>
        Các sự kiện hàng đầu chứa cả người dùng tự nhiên và không tự nhiên. Sử dụng bộ lọc nguồn truyền thông, ở đầu trang, để phân biệt giữa người dùng tự nhiên và không tự nhiên hoặc theo nguồn truyền thông được chọn.

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer6_us-en.png" src="https://files.readme.io/1a569224cec155b54a96433d6b2e36918c9c6f7924629cb09dcfc859358199c3-360010454658.png" width="245px" />](https://files.readme.io/1a569224cec155b54a96433d6b2e36918c9c6f7924629cb09dcfc859358199c3-360010454658.png)
      </td>
    </tr>
    <tr>
      <td>
        Các quốc gia hàng đầu
      </td>
      <td>
        [<Image alt="mceclip1.png" src="https://files.readme.io/aba8db1a2aa7a90d5fd5c07e184eebd6d09762c5564f87f87f584d91686a59c6-360011169298.png" width="181px" />](https://files.readme.io/aba8db1a2aa7a90d5fd5c07e184eebd6d09762c5564f87f87f584d91686a59c6-360011169298.png)

        Lưu ý: Biểu đồ này có sẵn cho các đại lý chứ không phải cho các nhà quảng cáo
      </td>
    </tr>
    <tr>
      <td>
        Bản sao đăng lại
      </td>
      <td>
        Biểu đồ này có sẵn sau khi bạn định cấu hình ứng dụng để gửi <Anchor target="_blank" href="/marketers/vi/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">bản sao đăng lại</Anchor> iOS 15+ đến AppsFlyer. Nếu không có biểu đồ nào hiển thị, hãy xem xét rằng:

        * Chúng tôi không nhận được bài đăng lại từ ứng dụng hoặc chưa nhận được chúng. Xác minh với nhà phát triển ứng dụng của bạn rằng điểm cuối AppsFlyer đã được đặt trong ứng dụng và phiên bản ứng dụng cập nhật nằm trong App Store.
        * Không nhận được bài đăng lại nào (nghĩa là không có lượt cài đặt SKAN) cho ngày được chọn hoặc bạn đã chọn ngày sớm hơn ngày 1 tháng 1 năm 2022.

        Lưu ý:

        * Tất cả các số liệu khác trong bảng điều khiển được tính toán bằng cách sử dụng các bài đăng lại iOS được các mạng quảng cáo chuyển tiếp đến AppsFlyer hoặc từ dữ liệu được cung cấp trực tiếp bởi các SRN. Dự kiến sự khác biệt giữa số liệu sao chép đăng lại và các số liệu khác.
        * Biểu đồ sao chép đăng lại không có sẵn cho các đại lý.

        [<Image alt="PostbackCopy.png" src="https://files.readme.io/0f2d290817650c87b3719ce2cdd107fdf66f62f575d3b4b75fcdd1f8330a04a9-4417816656657.png" width="207px" />](https://files.readme.io/0f2d290817650c87b3719ce2cdd107fdf66f62f575d3b4b75fcdd1f8330a04a9-4417816656657.png)

        | Phương diện | Lưu ý |
        | --- | --- |
        | Nguồn truyền thông | Nguồn truyền thông được phân bổ cho lượt cài đặt. <br /><br />* Số liệu:<br />  * **Tỷ lệ tải lại:** Các số liệu liên quan đến các bài đăng lại sử dụng SKAdNetwork V2.0+.<br />  * **Tỷ lệ kiểu tương tác được phân bổ:** Sự tương tác, lượt xem hoặc lượt nhấp chuột dẫn đến cài đặt. Các số liệu liên quan đến các bài đăng lại sử dụng SKAdNetwork V2.2+<br />* Lưu ý: Nếu ID nguồn truyền thông hiển thị, chúng tôi hiện không có tên được liên kết với ID đó. Yêu cầu nguồn truyền thông cập nhật ID SKAdNetwork của họ trong AppsFlyer. |
        | Ứng dụng nguồn | Tên nhà xuất bản quảng cáo, nói cách khác, tên ứng dụng mà người dùng tương tác với quảng cáo của bạn.<br /><br />* Số liệu: <br />  * **Số lượt cài đặt**: Số lượt cài đặt do ứng dụng nhà xuất bản mang lại.<br />* Lưu ý:<br />  * Nếu Apple giữ lại ID ứng dụng nguồn, do ngưỡng bảo mật, ứng dụng nguồn sẽ hiển thị là *unknown* (không xác định).<br />  * Nếu không thể tìm thấy tên ứng dụng, ID ứng dụng sẽ hiển thị |
        | ID ứng dụng nguồn | Id nhà xuất bản quảng cáo, nói cách khác, ID ứng dụng mà người dùng tương tác với quảng cáo của bạn.<br /><br />* Số liệu: <br />  * **Số lượt cài đặt**: Số lượt cài đặt do ID ứng dụng nhà xuất bản mang lại. |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="metrics" />

<Accordion title="Số liệu">

* Chọn các số liệu từ những số liệu có sẵn. [Các số liệu theo mô hình](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) xem xét tỷ lệ CV rỗng.
* Đặt nhóm chính và nhóm phụ theo phương diện để phân tích sâu vào các số liệu hiệu suất.

[![SKAdNetwork_Dashboard_AppsFlyer7_us-en.png](https://files.readme.io/434a848c7a33c052c80101788b066f4bdb90ef36423ea140f85c1cc59ace2ebf-360010368617.png)](https://files.readme.io/434a848c7a33c052c80101788b066f4bdb90ef36423ea140f85c1cc59ace2ebf-360010368617.png)

Giới thiệu về bảng số liệu:

* Sử dụng bảng để so sánh hiệu suất của các chiến dịch và nguồn truyền thông.
* Ban đầu, 20 nguồn truyền thông hàng đầu hiển thị, được sắp xếp theo số lượt cài đặt theo thứ tự giảm dần.
* Để sắp xếp bảng, nhấp vào một tiêu đề cột. Nhấp lại để đảo ngược thứ tự sắp xếp.
* Các số liệu liên quan đến chi phí (chi phí, lượt hiển thị và lượt nhấp chuột) có sẵn nếu có ít nhất 1 lượt cài đặt được liên kết với một chiến dịch nhất định. Lưu ý:
  * Chiến dịch có 0 lượt cài đặt hoàn toàn không hiển thị.
  * Một số mạng quảng cáo báo cáo các số liệu liên quan đến chi phí ở cấp độ bộ quảng cáo và quảng cáo, nhưng báo cáo cài đặt ở cấp chiến dịch. Trong trường hợp này, số liệu liên quan đến bộ quảng cáo và chi phí quảng cáo hiển thị với số liệu lượt cài đặt là 0.
* Giới hạn kích thước kiểu tương tác được phân bổ: Các số liệu liên quan đến chi phí không thể được chia nhỏ và hiển thị là **Unknown** (Không xác định).

Số liệu bảng:

<table><tbody><tr><th>Số liệu</th><th>Công thức/nhận xét</th></tr><tr><td><p><span>Lượt cài đặt</span></p></td><td><ul><li>Tổng lượt cài đặt</li><li>Lượt nhấp qua <ul><li><p>Người dùng được mang lại thông qua phân bổ lượt nhấp chuột qua</p></li><li><p>Có sẵn cho các lượt cài đặt được ghi bắt đầu từ ngày 22 tháng 12 năm 2021</p></li></ul></li><li>Lượt xem hết <ul><li>Có sẵn cho các lượt cài đặt được ghi bắt đầu từ ngày 22 tháng 12 năm 2021</li><li>Áp dụng cho các mạng quảng cáo triển khai SKAdNetwork V2.2+</li></ul></li></ul><p>Dữ liệu này được lấy từ trường fidelity_type trong bài đăng lại</p></td></tr><tr><td><p><span>Tỷ lệ giá trị chuyển đổi rỗng</span></p></td><td>Các bài đăng lại có giá trị chuyển đổi/lượt cài đặt rỗng \* 100 </td></tr><tr><td><p><span>Lượt hiển thị</span></p></td><td></td></tr><tr><td><p><span>Lượt nhấp</span></p></td><td> </td></tr><tr><td><p><span>Tỷ lệ nhấp tới cài đặt</span></p></td><td>Lượt cài đặt / Lượt nhấp chuột \* 100</td></tr><tr><td><p><span>Người dùng đã chuyển đổi</span></p></td><td><p><span>Số lượng người dùng duy nhất thực hiện một sự kiện đo lường được chỉ định.</span></p><ul><li><span>Chế độ tùy chỉnh: Luôn sử dụng af_skad_revenue (nếu đang chọn khác, người dùng được chuyển đổi sẽ vẫn trống)</span></li><li><span>Chế độ SKAN 4: Luôn sử dụng af_skad_revenue (nếu đang chọn khác, người dùng được chuyển đổi sẽ vẫn trống)</span></li><li><span>Chế độ doanh thu: Luôn sử dụng af_skad_revenue</span></li><li><span>Chế độ chuyển đổi: Sự kiện trong ứng dụng được chọn trong cài đặt bảng điều khiển</span></li><li> <span>Chế độ lượt tương tác: Sự kiện trong ứng dụng được đặt trong Conversion Studio</span><span></span> </li></ul></td></tr><tr><td>Người dùng chuyển đổi/Lượt cài đặt</td><td> </td></tr><tr><td><p><span>Tổng doanh thu</span></p></td><td>Doanh thu, bao gồm dữ liệu theo mô hình của các giá trị rỗng. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Tìm hiểu thêm</a> </td></tr><tr><td><p><span>Tổng doanh thu (không theo mô hình)</span></p></td><td>Doanh thu được báo cáo thông qua các giá trị chuyển đổi. Không bao gồm dữ liệu theo mô hình</td></tr><tr><td><p><span>Doanh thu D1-D2</span></p></td><td>Doanh thu cho khung thời gian SKAN 1 (ngày 1-2 trừ khi được sửa đổi), bao gồm dữ liệu theo mô hình có giá trị rỗng. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Tìm hiểu thêm</a> </td></tr><tr><td><p><span>Doanh thu D1-D2 (không theo mô hình)</span></p></td><td>Doanh thu nhận được trong khung thời gian SKAN 1 (ngày 1-2 trừ khi sửa đổi). Không bao gồm dữ liệu theo mô hình</td></tr><tr><td><p><span>Doanh thu D3-D7</span></p></td><td><span>Doanh thu cho khung thời gian SKAN 2 (ngày 3-7 trừ khi sửa đổi)</span></td></tr><tr><td><p><span>Doanh thu D8-D35</span></p></td><td><span>Doanh thu cho khung thời gian SKAN 3 (ngày 8-35 trừ khi sửa đổi)</span></td></tr><tr><td><p><span>Chi phí</span></p></td><td><ul><li><span>Chi phí được báo cáo bởi mạng quảng cáo </span></li><li>Nếu tên chiến dịch thay đổi, chi phí hiển thị dưới tên chiến dịch gần đây nhất được sử dụng. (Nếu có nhiều tên chiến dịch)</li></ul></td></tr><tr><td>ARPU</td><td><ul><li>Doanh thu trung bình trên mỗi người dùng, bao gồm dữ liệu theo mô hình có giá trị rỗng. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Tìm hiểu thêm</a> </li><li>Công thức: Doanh thu ($) (theo mô hình) / Lượt cài đặt</li></ul></td></tr><tr><td>ARPU (không theo mô hình)</td><td><p>Doanh thu trung bình trên mỗi người dùng, không bao gồm dữ liệu theo mô hình</p></td></tr><tr><td>ROI</td><td><ul><li>Lợi tức đầu tư, bao gồm dữ liệu theo mô hình của các giá trị rỗng. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Tìm hiểu thêm</a> </li><li>Công thức: (Doanh thu ($) (theo mô hình) - Chi phí) / Chi phí \* 100</li></ul></td></tr><tr><td>ROI (không theo mô hình)</td><td><p>Lợi tức đầu tư, không bao gồm dữ liệu theo mô hình</p></td></tr><tr><td>ROAS</td><td><ul><li>Lợi tức chi tiêu quảng cáo, bao gồm dữ liệu theo mô hình có giá trị rỗng. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Tìm hiểu thêm</a> </li><li>Công thức: (Doanh thu ($) (theo mô hình) / Chi phí \* 100</li></ul></td></tr><tr><td>ROAS (không theo mô hình)</td><td><p>Lợi tức chi tiêu quảng cáo, không bao gồm dữ liệu theo mô hình</p></td></tr><tr><td>eCPI</td><td> </td></tr><tr><td colspan="2"><strong>Số liệu sự kiện trong ứng dụng</strong></td></tr><tr><td>Tên sự kiện trong ứng dụng</td><td> </td></tr><tr><td>eCPA</td><td><ul><li>Chi phí hiệu quả cho mỗi hành động, bao gồm dữ liệu theo mô hình của các giá trị rỗng. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Tìm hiểu thêm</a> </li><li>Công thức: Chi phí / Người dùng duy nhất thực hiện các sự kiện (theo mô hình)</li></ul></td></tr><tr><td>eCPA (không theo mô hình)</td><td><p>Chi phí hiệu quả cho mỗi hành động, không bao gồm dữ liệu theo mô hình</p></td></tr><tr><td>Tổng số sự kiện</td><td>Tổng số lần xuất hiện sự kiện trên tất cả các khung thời gian, bao gồm dữ liệu theo mô hình của các giá trị rỗng. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Tìm hiểu thêm</a> </td></tr><tr><td>Tổng số sự kiện (không theo mô hình)</td><td>Tổng số lần xuất hiện sự kiện trên tất cả các khung thời gian, không bao gồm dữ liệu theo mô hình</td></tr><tr><td>Số sự kiện <span>D1-D2</span> </td><td>Số lần xuất hiện sự kiện cho khung thời gian 1 (ngày 1-2 trừ khi được sửa đổi), bao gồm dữ liệu theo mô hình của các giá trị rỗng. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Tìm hiểu thêm</a> </td></tr><tr><td>Số sự kiện <span>D1-D2 (không theo mô hình)</span> </td><td>Số lần xuất hiện sự kiện cho khung thời gian 1 (ngày 1-2 trừ khi được sửa đổi), không bao gồm dữ liệu theo mô hình</td></tr><tr><td>Số sự kiện <span>D3-D7</span> </td><td>Số lần xuất hiện sự kiện cho khung thời gian 2 (ngày 3-7 trừ khi được sửa đổi), bao gồm dữ liệu theo mô hình của các giá trị rỗng.<span> </span><a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Tìm hiểu thêm</a> </td></tr><tr><td>Số sự kiện <span>D8-D35</span> </td><td>Số lần xuất hiện sự kiện cho khung thời gian 3 (ngày 8-35 trừ khi được sửa đổi), bao gồm dữ liệu theo mô hình của các giá trị rỗng.<span> </span><a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Tìm hiểu thêm</a> </td></tr></tbody></table>

</Accordion>

<div id="modeled-metrics-and-null-cv" />

<Accordion title="Số liệu theo mô hình và CV rỗng">

Báo cáo SKAdNetwork (SKAN) có thể bị hạn chế bởi vì:

* SKAN dựa trên các giá trị chuyển đổi (CV) được giới hạn chỉ 6 bit, nghĩa là có thể có 64 giá trị (0-63).
* Apple đôi khi giữ lại CV thực (và trả về dữ liệu "null") để bảo vệ quyền riêng tư của người dùng.
* Dữ liệu chỉ có sẵn trong khung thời gian đo lường và giá trị trọn đời (LTV) không được xác định.

Dữ liệu theo mô hình SKAN giải quyết các vấn đề này, mang lại:

* Giá trị chuyển đổi theo mô hình thay vì giá trị rỗng.
* Doanh thu theo mô hình và lần xuất hiện sự kiện.
* Bức tranh toàn cảnh hơn về hiệu suất LTV của ứng dụng và chiến dịch.

Các số liệu theo mô hình có sẵn bao gồm:

* Doanh thu
* Số sự kiện
* eCPA
* ARPU
* ROI
* ROAS

<Anchor target="_blank" href="/marketers/vi/docs/skan-modeled-data">Tìm hiểu thêm về dữ liệu SKAN theo mô hình</Anchor>

</Accordion>

<div id="appsflyer-attribution-vs-skan-attribution" />

<Accordion title="Phân bổ AppsFlyer so với Phân bổ SKAN">

Các số liệu SKAN khác với các số liệu có sẵn bằng cách sử dụng mô hình phân bổ AppsFlyer. Bảng sau đây liệt kê các nguyên nhân chính.

Các định nghĩa:

* **Thời gian:** Giả sử khung thời gian hoạt động mặc định là 24 giờ (48 giờ sau khi bạn nâng cấp lên SKAN 4).
* **SDK:** SDK AppsFlyer được nhúng trong ứng dụng.
* **Quy tắc**: <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model">Mô hình phân bổ của AppsFlyer</Anchor>

<div id="attribution-framework-differences" />

#### Sự khác biệt khung phân bổ

| Khái niệm | SKAN | AppsFlyer |
| --- | --- | --- |
| Phương pháp phân bổ được hỗ trợ | Apple SKAN để phân bổ nhấp chuột và xem qua. Chứa lưu lượng truy cập của các chiến dịch ứng dụng đến ứng dụng của mạng quảng cáo và SRN hỗ trợ SKAN. | **<Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model">Mô hình phân bổ AppsFlyer</Anchor> hỗ trợ nhiều phương pháp và kịch bản phân bổ:**<ul><li>Web di động</li><li>Lượt xem qua</li><li>Lượt nhấp</li><li>Clip Ứng dụng</li><li>Phân bổ web</li><li>Apple Search Ads</li><li>Truyền thông Sở hữu</li><li>Lưu lượng SRN (người dùng đồng ý)</li><li>Và nhiều hơn nữa</li></ul> |
| Nguồn dữ liệu chính | <ul><li>Bài đăng lại SKAN</li><li>SDK</li></ul> | SDK và các giải pháp liên quan.  Ví dụ: Sự kiện Máy chủ đến Máy chủ. |
| Tính cập nhật của dữ liệu | <Anchor target="_blank" href="/marketers/vi/docs/about-data-freshness-and-timezone-support#skan">Độ mới của dữ liệu SKAN.</Anchor> | Thời gian thực khi người dùng khởi chạy và sử dụng ứng dụng. |
| Múi giờ | UTC | Múi giờ cụ thể theo ứng dụng. |
| Thời gian cài đặt | Bắt nguồn từ thời gian có bài đăng lại iOS. | Báo cáo bởi SDK. |
| Khung thời gian hoạt động | Hoạt động của người dùng trong một khung thời gian đo lường cố định, bắt đầu với ứng dụng đang mở. | Chứa dữ liệu LTV từ ngày cài đặt cho đến hiện tại.<br /><br />Sử dụng Nhóm người để xem dữ liệu giới hạn trong ngày nhóm 0 hoặc ngày nhóm 1, hoặc cả hai cùng nhau để xem khoảng thời gian đo lường có thể so sánh được.<br /><br />Hãy xem xét, ngày nhóm 0 bao gồm ít hơn 24 giờ hoạt động. Ví dụ: người dùng cài đặt lúc 18:00 vào một ngày nhất định có 6 giờ hoạt động vào ngày nhóm 0. |
| Số lượt cài đặt được báo cáo bởi | <ul><li>**SKAN**: Giới hạn ở các lượt cài đặt không tự nhiên và lượt tải lại không tự nhiên.</li><li>**SDK**: Tất cả các lượt cài đặt được báo cáo. Chỉ những lượt cài đặt lần đầu mới được tính cho mục đích số liệu. Có nghĩa là phân bổ lại bị bỏ qua.</li></ul> | SDK báo cáo tất cả các lượt cài đặt được phân loại bằng Quy tắc thành lượt cài đặt lần đầu và lượt cài đặt lại nhắm mục tiêu lại (phân bổ lại). |
| Mức độ chi tiết quảng cáo | Chiến dịch, bộ quảng cáo, ID bộ quảng cáo, quảng cáo và ID quảng cáo. | Thứ bậc hoàn chỉnh: Chiến dịch, ID chiến dịch, bộ quảng cáo, các thông số bổ sung như kênh và đối tác. |
| Lượt tải lại so với lượt cài đặt lại | Lượt tải lại liên quan đến hành động của người dùng Apple ID nhất định. Chúng không song song với phân bổ lại. | Nhắm mục tiêu lại (phân bổ lại tương tác lại) được phản ánh trong bảng điều khiển Nhắm mục tiêu lại. Chúng không song song với lượt tải lại. |

<div id="metric-differences" />

#### Sự khác biệt về số liệu

| Số liệu | SKAN | Phân bổ truyền thống |
| --- | --- | --- |
| Các lượt Cài đặt không tự nhiên | Số lượng bài đăng lại iOS hợp lệ nhận được bởi AppsFlyer.<br /><br />Hãy xem xét rằng, AppsFlyer không nhận được các bài đăng lại của các mạng quảng cáo chưa hoàn thành tích hợp SKAN với AppsFlyer.<br /><br />Điều này có thể dẫn đến việc đếm thiếu số lượt cài đặt không tự nhiên và tăng số lượt cài đặt tự nhiên. | <ul><li>Báo cáo bởi SDK.</li><li>Được phân bổ cho một nguồn truyền thông.</li><li>Được đếm bằng cách sử dụng Quy tắc.</li></ul> |
| Lượt cài đặt tự nhiên | Lượt cài đặt SDK trừ lượt cài đặt SKAN. | <ul><li>Báo cáo bởi SDK.</li><li>Không được phân bổ cho bất kỳ nguồn truyền thông nào.</li><li>Được đếm bằng cách sử dụng Quy tắc.</li></ul> |
| Doanh thu | **Không tự nhiên**: Doanh thu được báo cáo bởi bài đăng lại SKAN.<br /><br />**Tự nhiên:** Doanh thu được báo cáo bởi các sự kiện trong ứng dụng SDK trừ đi doanh thu không tự nhiên. **Lưu ý**: Các số liệu tự nhiên không phải lúc nào cũng có sẵn. [Tìm hiểu thêm](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations). | <ul><li>Được báo cáo bởi SDK và API máy chủ đến máy chủ.</li></ul> |
| Doanh thu quảng cáo | <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">Có sẵn</Anchor> | Doanh thu quảng cáo cấp người dùng được phân bổ dựa trên IDFV |
| ROI/ROAS | Doanh thu trong khung thời gian đo lường. | <ul><li>LTV</li><li>Số liệu của UA và các chiến dịch nhắm mục tiêu lại.</li></ul> |

</Accordion>

<div id="faq-skan-discrepancies" />

<Accordion title="FAQ—Sự khác biệt SKAN">

| Lý do | Sự khác biệt—Hỏi và đáp |
| --- | --- |
| A | **Hỏi: Tại sao số chuyển đổi trong bảng điều khiển AppsFlyer khác với số chuyển đổi của bảng điều khiển mạng quảng cáo?**<br /><br />**Đáp**: Lý do cho sự khác biệt<ul><li>**Ngày cài đặt so với ngày có bài đăng lại:**<ul><li>AppsFlyer: Ngày cài đặt được lấy nguồn bằng cách sử dụng một công thức tính đến thời gian có bài đăng lại iOS, độ dài khung thời gian và thời gian trễ đăng lại.</li><li>Mạng quảng cáo: Thông thường chỉ sử dụng thời gian có bài đăng lại iOS làm ngày cài đặt mà không cần điều chỉnh.</li><li>Sử dụng tùy chọn **display by postback arrival date** (hiển thị theo ngày có bài đăng lại) trong bảng điều khiển để loại bỏ sự khác biệt này.</li></ul></li><li>**Xác thực bài đăng lại:** AppsFlyer xác thực các bài đăng lại iOS nhận được và đảm bảo rằng chữ ký của Apple là hợp lệ. Mạng quảng cáo có thể gửi các bài đăng lại không hợp lệ mà AppsFlyer bỏ qua.</li><li>**Thiếu bài đăng lại**: Bài đăng lại iOS phải được mạng quảng cáo gửi đến AppsFlyer. AppsFlyer không nhận được bài đăng lại trực tiếp từ thiết bị. Nếu thiếu bài đăng lại, AppsFlyer không có cách nào để biết điều này.</li></ul> |
| B | **Hỏi**: **Sự khác biệt giữa <Anchor target="_blank" href="/marketers/vi/docs/skan-aggregated-performance-report-api">API hiệu suất SKAN</Anchor> và bảng điều khiển so với <Anchor target="_blank" href="/marketers/vi/docs/skan-aggregated-postback-arrival-date-api">API đăng lại tổng hợp SKAN là gì?</Anchor>**<br /><br />**Đáp**: Phạm vi ngày API đăng lại liên quan đến ngày mà AppsFlyer nhận được bài đăng lại. Phạm vi ngày API hiệu suất liên quan đến ngày cài đặt có nguồn gốc như được mô tả trong lý do A. |
| C | **Hỏi: Tất cả các mạng quảng cáo có báo cáo địa lý không?**<br /><br />**Đáp:** Không. |
| D | **Hỏi: Tại sao có sự khác biệt giữa bảng điều khiển Tổng quan và bảng điều khiển SKAN.**<br /><br />**Đáp:** Xem phần trước để biết tổng quan về lý do cho sự khác biệt. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Lưu ý |
| --- | --- |
| Các lần xuất hiện sự kiện theo mô hình | <ul><li>Các sự kiện theo mô hình dựa trên công thức được mô tả trong [số liệu theo mô hình và CV rỗng](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv).</li><li>Công thức được áp dụng cho mỗi hàng dữ liệu. Điều này có thể gây ra sự khác biệt giữa số lượng sự kiện theo mô hình cho một nguồn truyền thông nhất định và tổng số sự kiện theo mô hình của các chiến dịch của nguồn.</li></ul> |
| Ngày có bài đăng lại | Ngày cuối cùng trong phạm vi ngày được giới hạn trong ngày mà lượt cài đặt cuối cùng được ghi lại. |
| Dữ liệu tự nhiên | <ul><li>Đối với <Anchor target="_blank" href="/marketers/vi/docs/skan-conversion-studio#skan-4">SKAN 4</Anchor> và <Anchor target="_blank" href="/marketers/vi/docs/skan-conversion-studio#custom">chế độ tùy chỉnh</Anchor>, dữ liệu tự nhiên có sẵn cho các lượt cài đặt, không phải cho các sự kiện trong ứng dụng và doanh thu tổng thể.</li><li>Đối với <Anchor target="_blank" href="/marketers/vi/docs/skan-conversion-studio#fixed-modes">các chế độ cố định</Anchor>, dữ liệu tự nhiên có sẵn cho cả các lượt cài đặt và các sự kiện trong ứng dụng.</li><li>Cân nhắc sử dụng SSOT để xem dữ liệu tự nhiên, vì SSOT hủy trùng lặp các sự kiện được phân bổ SKAN và phân bổ mô hình AppsFlyer.</li><li>Nếu dữ liệu phân bổ AppsFlyer (lượt cài đặt mới cho cả tự nhiên và không tự nhiên) trừ đi dữ liệu phân bổ SKAN (lượt cài đặt không tự nhiên) bằng một số âm, bảng điều khiển SKAN sẽ hiển thị 0 trong lượt cài đặt tự nhiên.</li></ul> |
| Dữ liệu lịch sử | Dữ liệu chuyển đổi sớm nhất được hỗ trợ: Ngày 1 tháng 11 năm 2020 |
| Tiền tệ | Hiển thị theo đơn vị USD hoặc đồng nội tệ cụ thể cho ứng dụng như được đặt trên <Anchor target="_blank" href="/marketers/vi/docs/app-settings">trang cài đặt của ứng dụng</Anchor>. |
| Múi giờ | Đối với dữ liệu, lượt cài đặt và sự kiện do SKAN báo cáo hiển thị bằng UTC, ngoại trừ dữ liệu Meta và Google SKAN, trong đó múi giờ dựa trên múi giờ được cấu hình tương ứng trong tài khoản Meta và Google của bạn. |

</Accordion>

<div id="see-also" />

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide">Hướng dẫn giải pháp SKAN của AppsFlyer</Anchor>
> * <Anchor target="_blank" href="/marketers/vi/docs/about-att-and-skan">Có gì khác biệt—Các bản cập nhật liên quan đến iOS 14 của AppsFlyer</Anchor>

<div data-zendesk-anchors="dashboard-principles=nguy%C3%AAn-t%E1%BA%AFc-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n 01H81P8JPZM24J0536GKBPNFMJ=nguy%C3%AAn-t%E1%BA%AFc-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n skan-dashboard-view-options=c%C3%A1c-t%C3%B9y-ch%E1%BB%8Dn-xem-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-skan 01H81P8JPZC5K0KZR64P084N4W=c%C3%A1c-t%C3%B9y-ch%E1%BB%8Dn-xem-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-skan dashboard-use=s%E1%BB%AD-d%E1%BB%A5ng-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n 01H81P8JPZGSHQVMG27YEJPARH=s%E1%BB%AD-d%E1%BB%A5ng-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n 01H81P8JPZ93G4EQY343SV2B1Q=dashboard-settings 01H81P8JPZV5F4VCZHR537HREH=filter-options 01H81P8JQ0KRGXWCVT82YW30CS=headline-metrics 01H81P8JQ0ETB0W3SGS56CBCX8=charts 01H81P8JQ0KK1NMRGFR0GBX4EK=metrics 01H81P8JQ0ZKGTRWNW95D015Z7=modeled-metrics-and-null-cv 01H81P8JQ18NGP8Z74D02DMQ7P=appsflyer-attribution-vs-skan-attribution attribution-framework-differences=s%E1%BB%B1-kh%C3%A1c-bi%E1%BB%87t-khung-ph%C3%A2n-b%E1%BB%95 01H81P8JQ1VTYX3382WDXDMVT3=s%E1%BB%B1-kh%C3%A1c-bi%E1%BB%87t-khung-ph%C3%A2n-b%E1%BB%95 metric-differences=s%E1%BB%B1-kh%C3%A1c-bi%E1%BB%87t-v%E1%BB%81-s%E1%BB%91-li%E1%BB%87u 01H81P8JQ1M8M9TSHF0C12Z2QE=s%E1%BB%B1-kh%C3%A1c-bi%E1%BB%87t-v%E1%BB%81-s%E1%BB%91-li%E1%BB%87u faq%E2%80%94skan-discrepancies=faq-skan-discrepancies 01H81P8JQ157YYNX9C527ES4C8=faq-skan-discrepancies 01H81P8JQ1T3DE29Y14VARKASK=traits-and-limitations h_01HE7SWGPWNWG26CEN40VSTA9J=xem-th%C3%AAm" />
