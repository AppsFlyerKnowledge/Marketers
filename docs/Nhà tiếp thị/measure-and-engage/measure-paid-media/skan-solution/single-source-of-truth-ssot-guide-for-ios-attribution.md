---
title: 'Hướng dẫn Nguồn dữ liệu tin cậy duy nhất (SSOT) để phân bổ iOS '
metadata:
  keywords:
    - iOS
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
  created_at: '2021-11-11T09:28:42Z'
  edited_at: '2024-01-15T10:48:13Z'
  id: 4410634145425
  locale: vi
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/vi/articles/4410634145425
---
> **Sơ lược**: Trong môi trường iOS 14+, AppsFlyer tập hợp dữ liệu từ nhiều phương thức so khớp phân bổ như IDFA, IDFV, SKAN, Apple Search Ads, v.v. và đưa ra bức tranh toàn cảnh về hiệu suất của chiến dịch ứng dụng. Không có phương thức phân bổ nào cung cấp bức tranh đầy đủ về hiệu suất ứng dụng. Thách thức đặt ra là một người dùng nhất định chỉ được tính một lần vì hai phương thức có thể phân bổ cho cùng một người dùng. Cơ chế Nguồn thông tin đáng tin cậy duy nhất (SSOT) của AppsFlyer thực hiện điều đó. Các báo cáo và phép đo SSOT đều đúng và chính xác và chỉ tính cho cùng một người dùng một lần duy nhất.

<Embed title="Hướng dẫn Nguồn dữ liệu tin cậy duy nhất (SSOT) để phân bổ iOS" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/545isomgo1" providerUrl="https://fast.wistia.com" />

<div id="about-single-source-of-truthtrue-ios-performance-data" />

## Cách nhận dữ liệu thực về hiệu suất iOS 14+

Bài viết liên quan: <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide">Hướng dẫn giải pháp SKAN</Anchor> |  <Anchor target="_blank" href="/marketers/vi/docs/skan-conversion-studio">SKAN conversion studio</Anchor> | Bảng điều khiển tổng quan

Kể từ iOS 14, AppsFlyer phân bổ người dùng iOS bằng cách sử dụng dữ liệu từ nhiều luồng dữ liệu, bao gồm SKAdNetwork, người dùng đồng ý ATT, mô hình xác suất, thông tin chi tiết dựa trên tính gia tăng và API chuyên dụng dành cho Apple Search Ads. Việc không có IDFA khiến gần như không thể liên kết các phương thức phân bổ với nhau mà không có dữ liệu trùng lặp.

Cơ chế SSOT loại bỏ dữ liệu lượt cài đặt trùng lặp và sửa đúng cho lượt phân bổ của người dùng bị phân bổ sai. Nói cách khác, những người dùng được coi là tự nhiên lẽ ra phải được phân bổ cho nguồn truyền thông không tự nhiên. Do đó, số lượt cài đặt được phân bổ cho một chiến dịch được sửa đúng và các số liệu liên quan đến chi phí và doanh thu, như eCPI, ROI và ROAS, cũng được tính toán chính xác.

Hiểu đơn giản là cơ chế SSOT gắn cờ hiệu các lượt cài đặt SKAN cũng được phân bổ bằng cách sử dụng một phương thức so khớp khác. Khi tính toán các số liệu hợp nhất để tránh đếm hai lần cho cùng một người dùng, hãy cân nhắc đến cờ. Tương tự, bạn sử dụng cờ khi xử lý dữ liệu thô của SKAN.

Để gắn cờ SSOT cho dữ liệu của mình, bạn phải bật SSOT trong Conversion Studio.

<div id="turn-on-single-source-of-truth" />

<Accordion title="Bật Nguồn dữ liệu tin cậy duy nhất">

![SSOTControl.png](https://files.readme.io/fd99117e9278ebda3b1f0cc137afb266643e5e45325345ec51aeb58c16d4f13c-31247514683153.png)

**Để bật SSOT:**

1. Trước khi bắt đầu, hãy cân nhắc chính sách <Anchor target="_blank" href="https://content.appsflyer.com/ios-hub/billing/">thanh toán Nguồn dữ liệu tin cậy duy nhất</Anchor> của AppsFlyer.
2. Trong AppsFlyer, đi tới **Configuration** > **SKAN Conversion Studio**.
3. Chọn chế độ **Custom**.
4. Bật **Single Source of Truth.**
5. Hoàn thành cài đặt nếu cần.

Xem <Anchor target="_blank" href="/marketers/vi/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>

</Accordion>

<div id="overview-dashboard-single-source-of-truth-view" />

## Chế độ xem Nguồn dữ liệu tin cậy duy nhất trên Bảng điều khiển tổng quan

![SSOTisNowOn.png](https://files.readme.io/8e21fd0c64bb85fb94af752eb037472726d68cd55bf028dc5306b0acb398d199-31247490958225.png)

Chế độ xem Nguồn dữ liệu tin cậy duy nhất có sẵn trên Bảng điều khiển tổng quan cung cấp bức tranh toàn cảnh về các số liệu hiệu suất không tự nhiên. Trong chế độ xem này:

* Số liệu lượt cài đặt là đúng.
* Số liệu liên quan đến chi phí và doanh thu phụ thuộc vào số liệu lượt cài đặt, bao gồm eCPI, ARPU và ROAS, đều được tính toán chính xác.
* Các số liệu tự nhiên được điều chỉnh sau khi giải thích được về lượt cài đặt bị phân bổ sai.

Phần này nêu bật sự khác biệt và các tính năng độc đáo của chế độ xem SSOT. Giả định rằng bạn đã quen thuộc với Bảng điều khiển tổng quan.

<div id="turn-on-single-source-of-truth-view" />

<Accordion title="Bật chế độ xem Nguồn dữ liệu tin cậy duy nhất">

Dữ liệu trong chế độ xem SSOT có sẵn 3-5 ngày sau khi bật Nguồn dữ liệu tin cậy duy nhất trong Conversion Studio.

**Để bật chế độ xem Nguồn dữ liệu tin cậy duy nhất**:

1. Trước khi bắt đầu, hãy xác minh rằng <Anchor target="_blank" href="/marketers/vi/docs/skan-conversion-studio#single-source-of-truth">Nguồn dữ liệu tin cậy duy nhất</Anchor> đã được bật trong Conversion Studio.
2. Trong AppsFlyer, đi đến **Dashboard** > **Overview.**   

   <Image alt="SelectSavedReport.png" src="https://files.readme.io/863a9c66c37e031a1f1b2a7fb3e0c68eb9c29405283214e68a432357c35524dd-31247514684177.png" width="243px" />
3. Nhấp vào ▼.
4. Chọn **Lite overview**.  
   Nút chuyển Nguồn dữ liệu tin cậy duy nhất sẽ hiển thị.  

   <Image alt="SSOTviewon.png" src="https://files.readme.io/7b0a664f0882dad46e7239b5363592717358a79d920377dde13aa9c5dfbe84c3-31247514684433.png" width="246px" />
5. Bật Nguồn dữ liệu tin cậy duy nhất.
6. Một trong những điều sau đây xảy ra:
   * Số liệu và biểu đồ của bảng điều khiển sẽ hiển thị.  
     Các phần tiếp theo mô tả dữ liệu có sẵn. Xem các phần tiếp theo về dữ liệu sẽ hiển thị.  
     Lưu chế độ xem SSOT dưới dạng một báo cáo mới. Cách thực hiện:  
     1. Nhấp vào ▼.
     2. Nhấp vào **+ Save new report.**
     3. Nhập tên báo cáo.
     4. Nhấp vào **Save** (Lưu).
   * Dữ liệu không hiển thị. Lưu ý rằng có thể mất 3 - 5 ngày sau khi bật SSOT thì dữ liệu mới hiển thị. Hãy chờ hết khoảng thời gian này và truy cập lại bảng điều khiển.

Tắt công tắc SSOT bất kỳ lúc nào để xem dữ liệu thông thường với các phương diện không có sẵn trong chế độ xem SSOT.  Bằng cách đó, bạn có thể tìm hiểu sâu hơn.

</Accordion>

<div id="ssot-view-considerations" />

<Accordion title="Những điều cần lưu ý về chế độ xem SSOT">

Trong chế độ xem SSOT:

* **Giá trị chuyển đổi rỗng (CV)**: Được mô hình hóa. Công nghệ máy học nâng cao được sử dụng để lập mô hình giá trị rỗng do AppsFlyer hoặc SKAN phân bổ bằng cách sử dụng [cờ báo af\_attribution](/docs/single-source-of-truth-ssot-guide-for-ios-attribution#trường-cờ-phân-bổ). Nếu được quy cho SKAN thì tất cả các phép đo SKAN sau cài đặt sẽ được bao gồm trong bảng điều khiển SSOT. <Anchor target="_blank" href="/marketers/vi/docs/skan-modeled-data">Tìm hiểu thêm</Anchor>
* **Lượt tải lại**: Được bao gồm trong số liệu lượt cài đặt. Không có sự phân tách giữa lượt cài đặt và lượt tải lại.
* **Múi giờ**: Các sự kiện và lượt cài đặt được AppsFlyer báo cáo hiển thị theo UTC hoặc theo múi giờ địa phương dành riêng cho ứng dụng như được thiết lập trên <Anchor target="_blank" href="/marketers/vi/docs/app-settings">trang cài đặt ứng dụng</Anchor>. Đối với dữ liệu, lượt cài đặt và sự kiện do SKAN báo cáo hiển thị bằng UTC, ngoại trừ dữ liệu Meta và Google SKAN, trong đó múi giờ dựa trên múi giờ được cấu hình tương ứng trong tài khoản Meta và Google của bạn.
* **Tiền tệ**: Hiển thị theo đơn vị USD hoặc đồng nội tệ cụ thể cho ứng dụng như được thiết lập trên <Anchor target="_blank" href="/marketers/vi/docs/app-settings">trang cài đặt ứng dụng</Anchor>.

<div id="filter-considerations" />

#### Những điều cần lưu ý về bộ lọc

Cân nhắc tác động của các bộ lọc đối với việc hiển thị dữ liệu và các số liệu như được mô tả trong các bảng dưới đây.

| Bộ lọc | Điều cần lưu ý |
| --- | --- |
| Nguồn dữ liệu tin cậy duy nhất | Để xem số liệu Nguồn dữ liệu tin cậy duy nhất, xác minh rằng nút điều khiển đã bật. |
| Dạng xem | <ul><li>**Thu hút Người dùng:** Chế độ xem ưu tiên cho dữ liệu SSOT.</li><li>**Nhắm mục tiêu lại**: SKAN không hỗ trợ nhắm mục tiêu lại.</li><li>**Hợp nhất**: Các chiến dịch cài đặt chứa dữ liệu SSOT. Chiến dịch nhắm mục tiêu lại không bị SSOT ảnh hưởng.</li></ul> |
| Ngày | <ul><li>[Phương pháp thực hành tốt nhất] Chọn phạm vi ngày là 7 ngày trở lên, không bao gồm 3 ngày gần đây nhất để nhận được các kết quả chính xác.</li><li>Cân nhắc:<ul><li>Trong khoảng thời gian dưới 7 ngày, độ chính xác giảm do lệch múi giờ và ước tính thời gian cài đặt SKAN.</li><li>Các lượt cài đặt Google SKAN có thể được báo cáo trễ tối đa 13 ngày.</li></ul></li><li>Ngày khả dụng sớm nhất thường là 3 ngày sau khi bật SSOT. AppsFlyer xác định ngày này.</li><li>Ví dụ về lựa chọn ngày tối ưu:<ul><li>Nếu ngày hiện tại là ngày 10 tháng 2 và SSOT được bật vào ngày 29 tháng 1. Bạn có thể chọn từ ngày 1 đến ngày 7 tháng 2.</li></ul></li></ul> |
| Các bộ lọc của chiến dịch | Các bộ lọc phân cấp có sẵn của chiến dịch:<ul><li>Nguồn truyền thông</li><li>Chiến dịch</li></ul> |
| KPI dạng tiêu đề | KPI dạng tiêu đề có sẵn trong bảng điều khiển SSOT cho phép bạn xem:<ul><li>Thu hút người dùng: Cả không tự nhiên và tự nhiên</li><li>SKAN trùng lặp</li><li>Nhắm mục tiêu lại: Thu hút lại và phân bổ lại</li><li>Chi phí</li><li>eCPI</li><li>Số sự kiện gian lận (trong ứng dụng)</li></ul>Đối với mỗi chỉ số KPI, sẽ có một giá trị phần trăm. Giá trị này thể hiện chỉ số KPI được hiển thị có liên quan như thế nào với khoảng ngày song song trước đó. Ví dụ, tuần này so với tuần trước hoặc bất kỳ ngày nào được chọn trong phạm vi ngày so với cùng số ngày trước đó: Chẳng hạn như nếu chỉ số hiển thị số lượt cài đặt tăng X%, thì điều này có nghĩa là phạm vi ngày song song trước đó có số lượt cài đặt ít hơn X%. |
| Biểu đồ | **Phương diện có sẵn:**<ul><li>Phương thức phân bổ:<ul><li>Mô hình AF: Số lượt cài đặt được so khớp theo nhiều phương thức, bao gồm SKAN. Trong bảng điều khiển, bản ghi SKAN được bỏ qua để tránh đếm hai lần cho cùng một lượt cài đặt. Trong dữ liệu thô SKAN, af\_attribution\_flag của lượt cài đặt được đặt thành true.</li><li>SKAN duy nhất: Các lượt cài đặt chỉ được so khớp bởi SKAN và không theo phương thức nào khác. Trong dữ liệu thô SKAN, af\_attribution\_flag của lượt cài đặt được đặt thành false.</li></ul></li><li>Loại ghi công</li><li>Kiểu tương tác được phân bổ</li><li>Chiến dịch</li><li>ID Chiến dịch</li><li>Nguồn truyền thông</li><li>Nguồn</li><li>ID ứng dụng (đối với một số biểu đồ)</li><li>Địa lý (địa lý SKAN được <Anchor target="_blank" href="/marketers/vi/docs/skan-modeled-data#geo">tạo mô hình</Anchor>)</li><li>Tên sự kiện trong ứng dụng (nghĩa là tên của một sự kiện trong ứng dụng cụ thể được định cấu hình trong SKAN Converter Studio).</li></ul>**Số liệu:**<br /><br />Như được mô tả trong các phần số liệu. |
| Bảng | **Nhóm:**<ul><li>[Mặc định] Bảng được nhóm theo Nguồn truyền thông và chiến dịch.</li><li>Các tùy chọn nhóm bao gồm: Nguồn truyền thông, loại hình phân bổ, phương thức phân bổ, chiến dịch, ID chiến dịch, Loại tương tác được phân bổ, ngày, nguồn, địa lý và các phương án kết hợp của chúng. **Lưu ý**: Địa lý SKAN được <Anchor target="_blank" href="/marketers/vi/docs/skan-modeled-data#geo">tạo mô hình</Anchor>.</li><li>Nếu bạn chọn nhóm có các phương diện chỉ áp dụng cho lưu lượng truy cập không tự nhiên, thì bảng sẽ hiển thị N/A đối với nguồn truyền thông tự nhiên.</li></ul>**Số liệu:**<br /><br />Như được mô tả trong các phần số liệu. |

</Accordion>

<div id="metrics" />

<Accordion title="Số liệu">

Các phép đo có sẵn trong bảng điều khiển SSOT:

| Số liệu | Mô tả và những điều cần lưu ý |
| --- | --- |
| Nhóm | <ul><li>[Mặc định] Bảng được nhóm theo Nguồn truyền thông và chiến dịch.</li><li>Các tùy chọn nhóm bao gồm: Nguồn truyền thông, loại hình phân bổ, phương thức phân bổ, chiến dịch, ID chiến dịch, Loại tương tác được phân bổ, ngày, nguồn và các phương án kết hợp của chúng.</li><li>Nếu bạn chọn nhóm có phương diện chỉ áp dụng cho lưu lượng truy cập không tự nhiên, bảng sẽ hiển thị N/A đối với nguồn truyền thông tự nhiên.</li></ul> |
| **Phân bổ SSOT** | **Phân tích tiêu đề về số lượt cài đặt, phân bổ lại và thu hút lại SSOT trong những ngày đã chọn.**<ul><li>**Không tự nhiên: Chiến dịch mang đến người dùng. Cơ chế SSOT đảm bảo rằng cùng một lượt cài đặt chỉ được tính một lần.**</li><li>**Các số liệu tự nhiên.**</li></ul> |
| Tổng | Số lượt cài đặt, phân bổ lại và thu hút lại. |
| Lượt cài đặt | Số lượng người dùng duy nhất cài đặt ứng dụng. Được tính bằng số lượt cài đặt do AppsFlyer phân bổ trong ngữ cảnh của các chiến dịch UA cộng với số lượt cài đặt mới và lượt tải xuống lại được SKAN báo cáo sau khi loại bỏ trùng lặp. |
| Phân bổ lại | Số liệu nhắm mục tiêu lại có sẵn trong các chế độ xem Hợp nhất và Nhắm mục tiêu lại. Lưu ý rằng SKAN không hỗ trợ nhắm mục tiêu lại. |
| Tương tác lại | Số liệu nhắm mục tiêu lại có sẵn trong các chế độ xem Hợp nhất và Nhắm mục tiêu lại. Lưu ý rằng SKAN không hỗ trợ nhắm mục tiêu lại. |
| **Các số liệu khác** | **Nhiều số liệu khác liên quan đến SSOT và hiệu suất quảng cáo** |
| SKAN trùng lặp | Số lượt cài đặt SKAN với af\_attribution\_flag=true |
| Lượt nhấp | Dữ liệu về số lượt nhấp chuột và hiển thị được các mạng quảng cáo báo cáo qua API. Cơ chế SSOT không ảnh hưởng đến số liệu điểm tiếp xúc. |
| Lượt hiển thị | Dữ liệu về số lượt nhấp chuột và hiển thị được các mạng quảng cáo báo cáo qua API. Cơ chế SSOT không ảnh hưởng đến số liệu điểm tiếp xúc. |
| Tỷ lệ chuyển đổi | Lượt nhấp/cài đặt |
| Chi phí ($) | Dữ liệu về <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview">chi phí chiến dịch</Anchor> được các mạng quảng cáo báo cáo qua API. Dữ liệu hiển thị cho các chiến dịch có ít nhất một lượt cài đặt. Cơ chế SSOT không ảnh hưởng đến tổng chi phí được báo cáo. Cơ chế này chỉ ảnh hưởng đến các số liệu được tính dựa trên số lượt cài đặt. |
| AVG eCPI ($) | Số liệu hiệu quả chi phí trên mỗi lượt cài đặt được tính bằng cách sử dụng các số liệu lượt cài đặt trong chế độ xem SSOT. Số liệu này không bao gồm lượt cài đặt tự nhiên. |
| Lượt nhấp qua | Số lượt phân bổ phát sinh sau khi người dùng nhấp vào quảng cáo (CTA) |
| Tỷ lệ gỡ cài đặt | Tỷ lệ (%) người dùng gỡ cài đặt ứng dụng, là tỷ lệ người dùng phân bổ. Có nghĩa là cài đặt, thu hút lại hoặc phân bổ lại. Công thức: Lượt gỡ cài đặt / Phân bổ *100 (Chỉ thích hợp đối với Thu hút người dùng) |
| Gỡ cài đặt | <span id="simple-tabpanel-2"></span>Số lượng người dùng ứng dụng cài đặt ứng dụng sau đó gỡ cài đặt (xóa) ứng dụng (Chỉ thích hợp đối với Thu hút người dùng) |
| Lượt xem hết | Số lượt phân bổ phát sinh sau khi người dùng xem quảng cáo (VTA) |
| Doanh thu (D2) | Doanh thu được SKAN và AF báo cáo (bao gồm cả doanh thu quảng cáo) trong khung thời gian đo lường SKAN đầu tiên (D2):<ul><li>Doanh thu SKAN: Doanh thu cho lượt cài đặt SKAN (trong đó af\_attribution\_flag=false/null). Dựa trên tùy chọn cài đặt giá trị chuyển đổi cho <Anchor target="_blank" href="/marketers/vi/docs/skan-conversion-studio#revenue-component">doanh thu trong Conversion Studio</Anchor> và khung thời gian đo lường.</li><li>**Doanh thu được AF báo cáo:** Doanh thu do người dùng ứng dụng tạo ra sau một lượt cài đặt do AppsFlyer phân bổ và trong khung thời gian đo lường SKAN.</li><li>Đối với những người sử dụng SKAN 4 trong Conversion Studio, đây là dữ liệu trong 2 ngày sau khi cài đặt. Đối với những người sử dụng SKAN 3 trong Conversion Studio, dữ liệu sẽ dựa trên khung thời gian hoạt động SKAN đã xác định, cho dù đó là nhiều hơn hay ít hơn 2 ngày.</li><li>Loại trừ dữ liệu từ lượt cài đặt tự nhiên.</li><li>**Ví dụ**:<ul><li>Khung thời gian hoạt động là 24 giờ.</li><li>Sự kiện doanh thu diễn ra vào ngày sau khi cài đặt (Ngày X+1), nhưng trong khung thời gian hoạt động 24 giờ.<ul><li>Đối với doanh thu được cả SKAN và AF báo cáo, doanh thu sẽ được tính như đã diễn ra trong khung thời gian 24 giờ (ngay cả khi diễn ra vào một ngày không phải ngày cài đặt).</li></ul></li></ul></li></ul>**Lưu ý**:<ul><li>Nếu doanh thu SKAN chỉ được cấu hình cho các sự kiện nhất định, thì số liệu doanh thu SSOT chỉ cân nhắc các sự kiện doanh thu được AF báo cáo tương ứng.</li></ul>**Mẹo**: Để cải thiện độ chính xác của doanh thu SKAN:<ul><li>Thực hiện theo <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">các hướng dẫn về doanh thu quảng cáo SKAN</Anchor>.</li><li>Sử dụng đề xuất Doanh thu. [Sắp có]</li></ul> |
| Doanh thu D7 | <ul><li>Bao gồm dữ liệu được lập mô hình, ngoài khung thời gian đo lường SKAN, tối đa 7 ngày sau khi cài đặt. <Anchor target="_blank" href="/marketers/vi/docs/skan-modeled-data#revenue-ltv">Tìm hiểu thêm</Anchor></li><li>Loại trừ dữ liệu từ lượt cài đặt tự nhiên.</li></ul> |
| ARPU D2 | Doanh thu Trung bình trên mỗi Người dùng.<br /><br />Công thức: Doanh thu/Người dùng Duy nhất<br /><br />Đối với những người sử dụng SKAN 4 trong Conversion Studio, đây là dữ liệu trong 2 ngày sau khi cài đặt. Đối với những người sử dụng SKAN 3 trong Conversion Studio, dữ liệu sẽ dựa trên khung thời gian hoạt động SKAN đã xác định, cho dù đó là nhiều hơn hay ít hơn 2 ngày. |
| ARPU D7 | Bao gồm dữ liệu được lập mô hình, ngoài khung thời gian đo lường SKAN, tối đa 7 ngày sau khi cài đặt. <Anchor target="_blank" href="/marketers/vi/docs/skan-modeled-data#revenue-ltv">Tìm hiểu thêm</Anchor> |
| ROAS D2 | Lợi nhuận trên Chi tiêu quảng cáo (%).<br /><br />Công thức: Doanh thu/Chi phí * 100<br /><br />Đối với những người sử dụng SKAN 4 trong Conversion Studio, đây là dữ liệu trong 2 ngày sau khi cài đặt. Đối với những người sử dụng SKAN 3 trong Conversion Studio, dữ liệu sẽ dựa trên khung thời gian hoạt động SKAN đã xác định, cho dù đó là nhiều hơn hay ít hơn 2 ngày. |
| ROAS D7 | Bao gồm dữ liệu được lập mô hình, ngoài khung thời gian đo lường SKAN, tối đa 7 ngày sau khi cài đặt. <Anchor target="_blank" href="/marketers/vi/docs/skan-modeled-data#revenue-ltv">Tìm hiểu thêm</Anchor> |
| ROI D2 | Lợi tức đầu tư (%).<br /><br />Công thức: (Doanh thu - Chi phí)/Chi phí * 100<br /><br />Đối với những người sử dụng SKAN 4 trong Conversion Studio, đây là dữ liệu trong 2 ngày sau khi cài đặt. Đối với những người sử dụng SKAN 3 trong Conversion Studio, dữ liệu sẽ dựa trên khung thời gian hoạt động SKAN đã xác định, cho dù đó là nhiều hơn hay ít hơn 2 ngày. |
| ROI D7 | Bao gồm dữ liệu được lập mô hình, ngoài khung thời gian đo lường SKAN, tối đa 7 ngày sau khi cài đặt. <Anchor target="_blank" href="/marketers/vi/docs/skan-modeled-data#revenue-ltv">Tìm hiểu thêm</Anchor> |
| Lợi nhuận gộp D2 | Lợi nhuận sau khi trừ chi phí chiến dịch.<br /><br />Công thức: Doanh thu - Chi phí<br /><br />Đối với những người sử dụng SKAN 4 trong Conversion Studio, đây là dữ liệu trong 2 ngày sau khi cài đặt. Đối với những người sử dụng SKAN 3 trong Conversion Studio, dữ liệu sẽ dựa trên khung thời gian hoạt động SKAN đã xác định, cho dù đó là nhiều hơn hay ít hơn 2 ngày. |
| Lợi nhuận gộp D7 | Bao gồm dữ liệu được lập mô hình, ngoài khung thời gian đo lường SKAN, tối đa 7 ngày sau khi cài đặt. <Anchor target="_blank" href="/marketers/vi/docs/skan-modeled-data#revenue-ltv">Tìm hiểu thêm</Anchor> |
| **Số liệu sự kiện trong ứng dụng** | **Các số liệu liên quan đến các sự kiện trong ứng dụng (IAE) cụ thể** |
| Người dùng duy nhất của sự kiện (D2) | Người dùng duy nhất thực hiện sự kiện được tính bằng tổng số liệu giữa AppsFlyer và SKAN, bao gồm dữ liệu được mô hình hóa có giá trị null. Đối với những người sử dụng SKAN 4, dữ liệu này được cộng dồn số liệu của 2 ngày đầu tiên sau khi cài đặt. Đối với những người sử dụng SKAN 3, dữ liệu này được cộng dồn số liệu của các ngày sau cài đặt dựa trên Khoảng thời gian hoạt động đã xác định. |
| eCPA sự kiện (D2) | Chi phí mỗi hành động hiệu quả: Chi phí/số lượng người dùng duy nhất thực hiện sự kiện |
| Chuyển đổi sự kiện (D2) | Tỷ lệ (%) người dùng duy nhất thực hiện sự kiện, dưới dạng tỷ lệ người dùng phân bổ (có nghĩa là cài đặt, thu hút lại hoặc phân bổ lại). Công thức: Số lượng người dùng duy nhất /thuộc tính * 100 |
| Doanh thu sự kiện (D2) | Doanh thu được thu từ sự kiện này trong những ngày xác định sau khi cài đặt |

</Accordion>

<div id="how-does-ssot-work" />

## SSOT hoạt động như thế nào

<div id="understanding-skanaf-modeled-attribution-duplication" />

<Accordion title="Hiểu được trùng lặp phân bổ theo mô hình SKAN-AF">

Phân bổ SKAN và phân bổ theo mô hình AF hoạt động khác nhau và có các đặc điểm và hạn chế khác nhau. Do đó, mỗi lượt cài đặt có thể được phân bổ cho một trong các nguồn truyền thông không tự nhiên:

* Thông qua SKAN hoặc một mô hình AF riêng biệt (phân bổ duy nhất).
* Thông qua SKAN và một mô hình AF cùng lúc (trùng lặp). Trong trường hợp này, [cơ chế SSOT](/docs/single-source-of-truth-ssot-guide-for-ios-attribution#ssot-mechanism-workings) báo hiệu một lượt cài đặt trùng lặp SKAN với cờ: af\_attribution\_flag=TRUE. Và trong bảng điều khiển SSOT, chỉ hiển thị một lượt cài đặt, thay vì hai.
* Không phải SKAN hay mô hình AF, tức là lượt cài đặt này là tự nhiên.

Tình huống phân bổ theo SKAN-mô hình AF khả thi được minh hoạ trong sơ đồ Venn bên dưới.

![skan_af_model_diagram.png](https://files.readme.io/1b305d053044f79d12b9190d0b6c24dcc7e0bd17e17ef29029ad0b1c3c7d84c0-31247514684689.png)

Bảng dưới đây mô tả các lý do cho mỗi tình huống phân bổ.

| Chỉ SKAN | Chỉ mô hình AF | Cả SKAN và mô hình AF | Không phải SKAN hay mô hình AF |
| --- | --- | --- | --- |
| <ul><li>Nguồn truyền thông là SRN, thiết bị người dùng có iOS 14.5+, người dùng không đưa ra sự đồng ý ATT kép.</li><li>Nguồn truyền thông không thuộc SRN, thiết bị người dùng có iOS 14.5+,  mô hình xác suất không có sẵn, người dùng không cung cấp sự đồng ý ATT kép.</li></ul> | <ul><li>Thiết bị người dùng có iOS 14.4 trở xuống.</li><li>Nguồn truyền thông không hỗ trợ SKAN.</li><li>Cài đặt thông qua quy trình chuyển đổi web sang ứng dụng (SKAN chỉ hỗ trợ chuyển đổi ứng dụng sang ứng dụng).</li><li>Cài đặt thông qua nhắm mục tiêu lại (SKAN không hỗ trợ)</li></ul> | Không tồn tại hạn chế nào và cả SKAN và mô hình AF đều phân bổ lượt cài đặt.<br /><br />Điều này tạo ra các lượt cài đặt trùng lặp và là thời điểm cần SSOT để xóa lượt cài đặt trùng lặp. | Người dùng là tự nhiên |

</Accordion>

<div id="ssot-mechanism-workings" />

<Accordion title="Hoạt động của cơ chế SSOT">

SSOT hoạt động như được nêu chi tiết trong hình ảnh dưới đây.

![SingleSourceOfTruth.png](https://files.readme.io/882527d4828cf3c7156caf183652368de33463a440715c69f7ec39bfd0f655fa-31247514685329.png)

**Cơ chế SSOT hoạt động như thế nào?**

Cơ chế SSOT tồn tại trong AppsFlyer SDK trong ứng dụng của bạn trên thiết bị người dùng và trong nền tảng AppsFlyer như bên dưới:

**Thiết bị người dùng:**

* Người dùng mở ứng dụng lần đầu tiên. Nền tảng AppsFlyer cố gắng phân bổ người dùng. Khả năng phân bổ phụ thuộc vào loại chiến dịch và trạng thái đồng ý của người dùng (ATT).
* Nếu phân bổ thành công, SDK sẽ đặt bit phân bổ trong Giá trị chuyển đổi (CV)
* Quy trình SKAdNetwork thông thường tiếp tục không thay đổi. Nghĩa là tiếp tục đo lường hoạt động của người dùng và thiết đặt CV cho đến khi khung thời gian đo lường kết thúc.
* Sau đó, iOS sẽ gửi đăng lại.

**Nền tảng AppsFlyer**

* AppsFlyer nhận đăng lại từ iOS, giải mã giá trị chuyển đổi và hiển thị giá trị của bit phân bổ thông qua af\_attribution\_flag như được nêu chi tiết trong bảng dưới đây.

**Những điều cần lưu ý**

* Nói chung, AppsFlyer không tính các lượt cài đặt lại này. Trong SSOT, trạng thái cài đặt lại không được xem xét. Điều này có nghĩa là SSOT không xóa các lượt cài đặt SKAN trùng lặp đến từ các lượt cài đặt lại trong các phân tích SSOT và các lượt cài đặt trùng lặp này không ảnh hưởng đến cài đặt của cờ af\_attribution.

<div id="attribution-flag-field" />

#### **Trường cờ phân bổ**

| Dấu hiệu SSOT trong Giá trị chuyển đổi | Ý nghĩa | trường af\_attribution\_flag |
| --- | --- | --- |
| Bật | SSOT được bật trong Conversion Studio và AppsFlyer phân bổ người dùng thành công. | đúng |
| Tắt | SSOT được bật trong Conversion Studio và AppsFlyer không phân bổ người dùng. | SAI |
| -- | SSOT tắt trong Conversion Studio. | Rỗng |

**af\_attribution\_flag (bit phân bổ) tác động đến các công cụ báo cáo như thế nào?**

* Bảng điều khiển SKAN: Chỉ phản ánh hiệu suất được báo cáo trong các đăng lại của SKAN. Như vậy, cờ af\_attribution không được xem xét và các lượt cài đặt trùng lặp không bị xóa.
* <Anchor target="_blank" href="/marketers/vi/docs/skan-aggregated-performance-report-api">Các báo cáo hiệu suất hợp nhất</Anchor> của SKAN và <Anchor target="_blank" href="/marketers/vi/docs/skan-raw-data-reports">báo cáo dữ liệu thô</Anchor>: af\_attribution\_flag có sẵn trong các báo cáo này. Sử dụng cờ theo yêu cầu báo cáo của bạn. Nếu bạn kết hợp dữ liệu SKAN với dữ liệu AppsFlyer, hãy sử dụng cờ để xóa dữ liệu trùng lặp. Điều này áp dụng cho cả báo cáo dữ liệu thô và báo cáo dữ liệu hợp nhất.
* Chế độ xem SSOT trong Bảng điều khiển tổng quan: Dữ liệu từ tất cả các phương thức phân bổ, SKAN, IDFA, IDFV, Apple Search Ads, v.v. được hợp nhất trong một chế độ xem sau khi xóa dữ liệu SKAN trùng lặp.

</Accordion>

<div id="metrics-derived-by-combining-data-from-multiple-attribution-methods" />

<Accordion title="Các số liệu được lấy bằng cách kết hợp dữ liệu từ nhiều phương thức phân bổ">

Khi bạn kết hợp dữ liệu SKAN với dữ liệu của các phương thức phân bổ khác, hãy sử dụng af\_attribution\_flag để xóa dữ liệu trùng lặp khỏi dữ liệu. Điều này áp dụng cho cả báo cáo dữ liệu thô và báo cáo dữ liệu hợp nhất.

Các số liệu mẫu sau có thể được tính bằng cách sử dụng af\_attribution\_flag:

* Các lượt Cài đặt không tự nhiên
* Lượt cài đặt tự nhiên
* eCPI
* Doanh thu theo nhóm người

Công thức tính toán các phép đo mẫu:

| Mô tả số liệu | Chỉ định | Công thức |
| --- | --- | --- |
| Các lượt cài đặt AppsFlyer không tự nhiên | A | Các lượt cài đặt không tự nhiên được AppsFlyer báo cáo |
| Các lượt cài đặt duy nhất của SKAN | B | Lượt cài đặt SKAN trong đó af\_attribution\_flag=false |
| Tất cả các lượt cài đặt không tự nhiên | C | A + B |
| Lượt cài đặt tự nhiên | D | Tổng lượt cài đặt - C<br /><br />**Lưu ý**: Tổng lượt cài đặt là toàn bộ lượt cài đặt mà AppsFlyer SDK ghi nhận, bất kể phân bổ. |
| eCPI của chiến dịch | E | Chi phí / C |
| Doanh thu theo nhóm người | F | Thêm cùng với các nội dung sau:<ul><li>Doanh thu của những người dùng được xác định bởi A. Bao gồm các sự kiện được tạo trong giai đoạn sau lượt cài đặt đầu tiên tương đương với khung thời gian đo lường SKAN của bạn.</li><li>Doanh thu SKAN mà trong đó af\_attribution\_flag = false</li></ul> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Lưu ý |
| --- | --- |
| Chế độ xem SSOT | SSOT chỉ khả dụng nếu có ít nhất một lần đăng lại của SKAN cho mỗi ngày trong 5 ngày qua bao gồm `af_attribution_flag=true`. |
| Tổng lượt cài đặt | Trong một số trường hợp, có thể sẽ hiển thị nhiều lượt cài đặt hơn khi bật SSOT so với khi tắt. Một trong những lý do cho điều này là việc lập mô hình giá trị chuyển đổi rỗng có thể ảnh hưởng đến việc tính toán ngày cài đặt và gây ra sự sai khác khi so sánh các lượt cài đặt vào những ngày giống nhau. |
| Doanh thu | Doanh thu và các số liệu liên quan đến doanh thu khác (ARPU, ROAS, ROI, lợi nhuận gộp) được hỗ trợ kể từ ngày 1 tháng 9 năm 2022. |
| Đại lý | Người dùng đại lý có thể xem chế độ xem SSOT trong bảng điều khiển Tổng quan. |
| Mạng quảng cáo | <ul><li>Mạng quảng cáo có thể truy cập chế độ xem SSOT trong bảng điều khiển Tổng quan để xem dữ liệu được phân bổ cho nguồn truyền thông của họ. Để xem chế độ xem SSOT:<ul><li>Nhà quảng cáo phải bật SSOT trong Conversion Studio.</li><li>Mạng quảng cáo phải đang chạy các chiến dịch SKAN.</li><li>Mạng quảng cáo phải có <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#permissions-tab">các quyền cần thiết</Anchor> từ nhà quảng cáo để truy cập dữ liệu tổng hợp.</li></ul></li><li>Mạng quảng cáo có thể nhận tín hiệu SSOT thông qua các bài đăng lại SKAN.</li></ul> |
| Số liệu D7 | Số liệu D7 có thể bị thiếu hoặc ít hơn số liệu D2 nếu:<ul><li>Phạm vi ngày bao gồm những ngày trong vòng 8 ngày.</li><li>Dữ liệu được lập mô hình không khả dụng. Ví dụ: nếu không có dữ liệu doanh thu trong 14 ngày. <Anchor target="_blank" href="/marketers/vi/docs/skan-modeled-data#revenue-ltv">Tìm hiểu thêm</Anchor></li><li>Cấu hình SKAN Converter Studio đã được thay đổi trong 14 ngày qua.</li><li>Có ít hơn 10 lượt cài đặt trong một ngày nhất định.</li></ul> |
| Thay đổi cấu hình SKAN Converter Studio | Khi bạn thay đổi cấu hình SKAN Converter Studio, dữ liệu SSOT có thể sẽ không chính xác trong khoảng 84 giờ. Điều này là do AppsFlyer bắt đầu giải mã ngay các đăng lại SKAN bằng lược đồ mới, nhưng các đăng lại vẫn đến từ các lượt cài đặt được mã hóa bằng lược đồ trước đó. |
| Dữ liệu do AF báo cáo | <ul><li>Dữ liệu do AF báo cáo, đôi khi được gọi là dữ liệu mô hình AF, đề cập đến dữ liệu từ các lượt cài đặt hoặc các sự kiện khác được phân bổ thông qua một phương thức phân bổ AppsFlyer khác, trái ngược với SKAN.</li><li>Mục đích của bảng điều khiển SSOT là ngăn chặn sự trùng lặp các lượt cài đặt và sự kiện được phân bổ thông qua cả SKAN và một phương thức AppsFlyer khác.</li><li>Nếu bạn bật SSOT, nhưng lại muốn xem dữ liệu từ trước khi SSOT được bật thì bảng điều khiển SSOT chỉ hiển thị dữ liệu do AF báo cáo.</li></ul> |
| Sự kiện trong ứng dụng | Sự kiện trong ứng dụng (dưới dạng phương diện) và số liệu của sự kiện chỉ có sẵn cho:<ul><li>Các sự kiện được định cấu hình trong SKAN Converter Studio đều có sẵn.</li><li>Các sự kiện xảy ra trong Khoảng thời gian 1 đều có sẵn.</li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **Xem thêm**
>
> * Bảng điều khiển tổng quan

<div data-zendesk-anchors="how-to-get-true-ios-14-performance-data=c%C3%A1ch-nh%E1%BA%ADn-d%E1%BB%AF-li%E1%BB%87u-th%E1%BB%B1c-v%E1%BB%81-hi%E1%BB%87u-su%E1%BA%A5t-ios-14 01H8TZV6P41Z3ZEZ8VS86DK1J9=c%C3%A1ch-nh%E1%BA%ADn-d%E1%BB%AF-li%E1%BB%87u-th%E1%BB%B1c-v%E1%BB%81-hi%E1%BB%87u-su%E1%BA%A5t-ios-14 01H8TZV6P4G5AF2MJDQB8J6W2M=turn-on-single-source-of-truth overview-dashboard-single-source-of-truth-view=ch%E1%BA%BF-%C4%91%E1%BB%99-xem-ngu%E1%BB%93n-d%E1%BB%AF-li%E1%BB%87u-tin-c%E1%BA%ADy-duy-nh%E1%BA%A5t-tr%C3%AAn-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-t%E1%BB%95ng-quan 01H8TZV6P4ZBJTDH0FQ6F5D6Q9=ch%E1%BA%BF-%C4%91%E1%BB%99-xem-ngu%E1%BB%93n-d%E1%BB%AF-li%E1%BB%87u-tin-c%E1%BA%ADy-duy-nh%E1%BA%A5t-tr%C3%AAn-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-t%E1%BB%95ng-quan 01H8TZV6P47ZE6PMPF7S9GCJ16=turn-on-single-source-of-truth-view 01H8TZV6P4VCC5NRKBRQNJ4NX3=ssot-view-considerations filter-considerations=nh%E1%BB%AFng-%C4%91i%E1%BB%81u-c%E1%BA%A7n-l%C6%B0u-%C3%BD-v%E1%BB%81-b%E1%BB%99-l%E1%BB%8Dc 01H8TZV6P4QXEXYWSXKDB7B5SV=nh%E1%BB%AFng-%C4%91i%E1%BB%81u-c%E1%BA%A7n-l%C6%B0u-%C3%BD-v%E1%BB%81-b%E1%BB%99-l%E1%BB%8Dc 01H8TZV6P4YNTFBX5RXVKK8J0F=metrics how-does-ssot-work=ssot-ho%E1%BA%A1t-%C4%91%E1%BB%99ng-nh%C6%B0-th%E1%BA%BF-n%C3%A0o 01H8TZV6P4K8VXNKDR7JHM8PFW=ssot-ho%E1%BA%A1t-%C4%91%E1%BB%99ng-nh%C6%B0-th%E1%BA%BF-n%C3%A0o 01H8TZV6P4QYQJ177E2ZG676MH=understanding-skanaf-modeled-attribution-duplication 01H8TZV6P58E502Y1FDFHC3KHM=ssot-mechanism-workings attribution-flag-field=tr%C6%B0%E1%BB%9Dng-c%E1%BB%9D-ph%C3%A2n-b%E1%BB%95 01H8TZV6P5SSKDTKV4BV3TTA7D=tr%C6%B0%E1%BB%9Dng-c%E1%BB%9D-ph%C3%A2n-b%E1%BB%95 01H8TZV6P5AHZD8VRWRS4SPBYW=metrics-derived-by-combining-data-from-multiple-attribution-methods 01H8TZV6P5KN4F24ZN33V0TK7K=traits-and-limitations h_01HE182N43SSBX051E4GK7NFQ8=xem-th%C3%AAm" />
