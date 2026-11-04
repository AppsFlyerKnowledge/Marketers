---
title: Hướng dẫn giải pháp SKAdNetwork (SKAN)
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - SKAD
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-07-25T21:19:42Z'
  edited_at: '2023-11-09T05:06:55Z'
  id: 360011420698
  locale: vi
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/vi/articles/360011420698
---
> **Khái quát**: Phân bổ lượt cài đặt ứng dụng bằng SKAN.

![5754](https://files.readme.io/a970d7b0e8da300ded2138f941bf2e891f32d396c8500292534992a4b4449d71-30757780264337.png)

## SKAN

SKAdNetwork (SKAN), một phần của Apple iOS, cho phép các nhà quảng cáo đo lường hiệu suất chiến dịch đồng thời bảo vệ quyền riêng tư của người dùng. SKAN hoạt động mà không cần đến IDFA hoặc ID quảng cáo khác. SKAN hoạt động mà không cần sự đồng ý về ATT.

<div id="tip" />

> 👍 **Mách nhỏ**
>
> * Bắt đầu từ iOS 15, chúng tôi đề nghị bạn nên gửi <Anchor target="_blank" href="/marketers/vi/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">bản sao đăng lại SKAN</Anchor> tới AppsFlyer. Làm như vậy sẽ cho phép AppsFlyer xác minh rằng Giá trị chuyển đổi trong các bản đăng lại chưa bị thao túng.
> * Bạn muốn hiểu rõ hơn về giải pháp SKAN của AppsFlyer? Hãy xem khóa học ngắn, bổ ích<Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7810/play/18638/ios14-and-skadnetwork-part-1">này trên Cổng thông tin Học tập AppsFlyer</Anchor>.

**Các định nghĩa**

* <Anchor target="_blank" href="/marketers/vi/docs/sdk-integration-overview">SDK</Anchor>: Phiên bản hiện tại của AppsFlyer iOS SDK được tích hợp trong một ứng dụng.
* **Khung thời gian đo lường SKAN**: Liên quan đối với SKAN 4+. Có 3 khoảng thời gian (khung thời gian) trong đó hoạt động sau cài đặt của người dùng được đo lường:
  * Khung thời gian 1: 1-2 ngày
  * Khung thời gian 2: 3-7 ngày
  * Khung thời gian 3: 8-35 ngày
* **Giá trị chuyển đổi (CV)**: Thước đo chất lượng người dùng được báo cáo trong postback do iOS gửi ở cuối cửa sổ đo lường SKAN 4 hoặc, đối với SKAN 3 trở xuống, ở cuối Cửa sổ hoạt động. SDK AppsFlyer thiết đặt các CV cho bạn. Tuy nhiên, nếu bạn muốn đặt CV, hãy sử dụng chế độ <Anchor target="_blank" href="/marketers/vi/docs/skan-cv-decode-map-your-cv-to-events">Giải mã</Anchor> để tải lên tệp tin ánh xạ CV của bạn.
  * Đối với SKAN 4+, có cả giá trị chuyển đổi mịn và thô.
* **Conversion Studio**: Giải pháp AppsFlyer để ánh xạ cơ sở hạ tầng Giá trị chuyển đổi (CV) thành sự kiện
* **Giải pháp:** SDK, Cơ sở hạ tầng, Conversion Studio và nền tảng AppsFlyer hoạt động cùng nhau. Giải pháp SKAN của AppsFlyer cung cấp cho các nhà quảng cáo và mạng quảng cáo dữ liệu LTV thông qua phân tích bảng điều khiển, báo cáo và bài đăng lại.
* **Khung thời gian hoạt động:** Liên quan đối với SKAN 3 trở xuống. Có thời lượng đã đặt, mặc định 24 giờ, bắt đầu với ứng dụng đầu tiên mở. Nếu bạn sử dụng SKAN 4+, nhưng thiết bị người dùng hoặc mạng quảng cáo chưa hỗ trợ SKAN 4, Khung thời gian hoạt động là 48 giờ.

Bài viết này mô tả các đặc điểm liên quan của cơ sở hạ tầng và giải pháp. Để thiết lập đo lường, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.

<div id="about-apple-skan" />

<Accordion title="Giới thiệu về Apple SKAN">

| Đặc điểm | Mô tả |
| --- | --- |
| Điều kiện tiên quyết | Để cho phép sử dụng SKAN trong ứng dụng:<ul><li>Ứng dụng dành cho nhà quảng cáo (ứng dụng của bạn) nghĩa là ứng dụng đang được quảng cáo triển khai SDK AppsFlyer để đặt CV. Ngoài ra, bạn có thể đặt CV bằng <Anchor target="_blank" href="/marketers/vi/docs/skan-cv-decode-map-your-cv-to-events">chế độ Giải mã</Anchor>.</li><li>Ứng dụng của nhà xuất bản (ứng dụng hiển thị quảng cáo): phải <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app">tạo cấu hình một ứng dụng nguồn</Anchor>.</li><li><Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/registering_an_ad_network">Mạng quảng cáo phải đăng ký với Apple</Anchor></li></ul> |
| Được hỗ trợ | <ul><li>Phiên bản SKAdNetwork được hỗ trợ phụ thuộc vào phiên bản iOS:<ul><li>iOS 11-13: V1 (chỉ cài đặt không có CV)</li><li>iOS 14-14.5: V2+ (có CV)</li><li>iOS 14.6-16: V3 (có CV)</li><li>iOS 16.1+: V4+ (có CV cho 3 cửa sổ, cũng như giá trị mịn và thô)</li></ul></li><li>Phân bổ từ ứng dụng đến ứng dụng</li></ul> |
| Điểm hạn chế | <ul><li>Không hỗ trợ Apple Search Ads</li><li>Không hỗ trợ web di động</li><li>Trước khi có SKAN, 4 số hiệu ID của chiến dịch bị <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skstoreproductparameteradnetworkcampaignidentifier">giới hạn trong phạm vi 1 - 100</Anchor>; có nghĩa là 100 giá trị độc nhất/mạng quảng cáo/ứng dụng. Các mạng quảng cáo cung cấp cho AppsFlyer ID và tên chiến dịch. Điều này phản ánh trong các bảng điều khiển và báo cáo của AppsFlyer.</li><li>Từ SKAN 4, mã định danh nguồn từ 1 - 10.000.</li><li>Lượt cài đặt tự nhiên: SKAN không hỗ trợ lượt cài đặt tự nhiên.</li><li>Tương tác lại.</li></ul> |
| Nguyên tắc phân bổ SKAN | <ul><li>SKAN phân bổ bằng cách sử dụng <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions">mô hình phân bổ sau</Anchor>:<ul><li>Sau khi nhấp vào một quảng cáo, trong vòng 30 ngày, Người dùng cài đặt (tải xuống) ứng dụng. Trong vòng 60 ngày sau đó, người dùng mở ứng dụng lần đầu tiên.</li><li>Sau khi xem một quảng cáo, trong vòng 24 giờ, người dùng cài đặt (tải xuống) ứng dụng. Trong vòng 60 ngày sau đó, người dùng sẽ mở ứng dụng lần đầu tiên.</li><li>Bắt đầu từ SKAdNetwork V2.2, ưu tiên phân bổ nhấp qua hơn phân bổ xem qua. Phiên bản SKAN phụ thuộc vào phiên bản iOS.</li><li>iOS gửi bài đăng lại đến mạng quảng cáo được phân bổ. Bắt đầu từ iOS 15, các nhà quảng cáo có thể gửi trực tiếp bản sao của bài đăng lại đến AppsFlyer.</li></ul></li></ul> |
| Cấp mạng ẩn danh | Apple gửi một số postback cùng với dữ liệu giới hạn để bảo vệ quyền riêng tư của người dùng trong trường hợp đó. Theo Apple, đăng lại sẽ không bao gồm các CV mịn hoặc thô, cũng như ID ứng dụng nguồn hoặc mã định danh nguồn hoàn chỉnh nếu như việc làm vậy chống lại giới hạn bậc quyền riêng tư của Apple. <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows">Tìm hiểu thêm</Anchor> |

</Accordion>

<div id="appsflyer-skan-solution" />

## Giải pháp AppsFlyer SKAN

AppsFlyer cung cấp kết quả phân bổ hợp nhất trên thiết bị iOS bằng các postback SKAN từ thiết bị iOS. Các bài đăng lại này được iOS gửi đến các mạng quảng cáo, các mạng này chuyển tiếp chúng đến AppsFlyer. Các postback này chứa hồ sơ phân bổ ẩn danh được bổ sung giá trị chuyển đổi (CV) do nhà quảng cáo đặt. CV là thước đo lường chất lượng người dùng trong cửa sổ sau cài đặt ban đầu.

Giải pháp SKAN của AppsFlyer cung cấp cho các nhà quảng cáo:

* Dữ liệu SKAN trong bảng điều khiển và báo cáo thu được bằng cách hợp nhất các postback từ mọi mạng quảng cáo được bổ sung các điểm dữ liệu khác như chi phí.
* Khả năng kiểm soát thành phần mà CV đo lường, thông qua AppsFlyer Conversion Studio, mà không cần đổi mã ứng dụng. CV có thể được dùng để đo lường doanh thu, mức tương tác hoặc sự kiện chuyển đổi.

<div id="principles-and-flow" />

<Accordion title="Nguyên tắc và luồng phân bổ">

<div id="skan-attribution-flow" />

#### **Luồng phân bổ SKAN**

![SKAN_flow_-_Affinity_diagram_2.png](https://files.readme.io/2e29f01cf9cf3689777bbd42044e42c0b9f1d4fb719ed75413d29dd84489686d-13112278947601.png)

1. Nhà quảng cáo thiết lập cài đặt đo lường SKAN trong AppsFlyer Conversion Studio.
2. Người dùng mở ứng dụng lần đầu.
3. Trong mỗi cửa sổ, AppsFlyer thiết lập CV dựa trên hành động của người dùng và lược đồ CV đã xác định.
4. Sau khi đóng cửa sổ, thiết bị iOS sẽ gửi postback cho mạng quảng cáo và một bản sao postback đến AppsFlyer. Postback được gửi đến chậm:
   * Đối với cửa sổ đo lường 1 của SKAN 4: 24 - 48 giờ
   * Đối với cửa sổ đo lường 2 - 3 của SKAN 4: 24 - 144 giờ
   * Đối với SKAN 3: 24 - 48 giờ sau lần tăng giá trị CV gần đây nhất.
5. Các bản sao postback được gửi trực tiếp từ thiết bị iOS tới AppsFlyer sẽ được chuyển tiếp đến điểm cuối đã xác định của nhà quảng cáo. Xem <Anchor target="_blank" href="/marketers/vi/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">gửi bản sao postback SKAN tới AppsFlyer.</Anchor>
6. Mạng quảng cáo chuyển tiếp postback bổ sung tới AppsFlyer hoặc SRN truyền dữ liệu postback bằng API.
7. AppsFlyer xác thực và giải mã CV. Dữ liệu đã giải mã sẽ được ghi lại và phân bổ trước khi cung cấp trong AppsFlyer thông qua bảng điều khiển, báo cáo và API.

Để khắc phục các hạn chế về chức năng và cấu trúc của cơ sở hạ tầng SKAdNetwork, giải pháp SKAN của AppsFlyer xem xét các đặc điểm trong bảng sau.

| Đặc điểm | Mô tả |
| --- | --- |
| <span id="data-collection"></span>Thu thập dữ liệu | <ul><li>Đối với nhà quảng cáo, các bài đăng lại của SKAdNetwork được thu thập từ nhiều mạng quảng cáo.</li><li>Các nhà quảng cáo không cần phải tích hợp riêng lẻ với từng mạng quảng cáo—một nhiệm vụ phức tạp và tẻ nhạt.</li></ul> |
| <span id="data-validation"></span>Xác thực dữ liệu | <ul><li>Đảm bảo các bài đăng lại được Apple ký; điều này làm giảm cơ hội thao tác đăng lại.</li><li>Sử dụng trường ID giao dịch để xác thực rằng các bài đăng lại là duy nhất.</li></ul> |
| <span id="data-enrichment"></span>Làm giàu dữ liệu | <ul><li>Làm giàu dữ liệu bài đăng lại SKAdNetwork với các điểm dữ liệu khác để cung cấp phân tích ROI hoàn chỉnh. Ví dụ, tên chiến dịch do mạng quảng cáo cung cấp, v.v.</li><li>Điểm dữ liệu bao gồm lượt hiển thị, lượt nhấp, chi phí, v.v.</li></ul> |
| <span id="data-delivery"></span>Phân phối dữ liệu | Dữ liệu SKAdNetwork được làm giàu có sẵn bằng cách sử dụng các cách sau:<ul><li><Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">Bảng điều khiển về giải pháp SKAdNetwork</Anchor></li><li>[Báo cáo có thể tải xuống](/docs/skadnetwork-skan-solution-guide#reporting-options)</li></ul> |
| <span id="seamless-integration"></span>Tích hợp liền mạch | <ul><li>Đóng gói đầy đủ cho phép nhà quảng cáo dễ dàng thông qua trang cài đặt ứng dụng.</li><li>Không cần viết mã. Ứng dụng yêu cầu phiên bản SDK mới nhất.</li><li>Bao gồm hỗ trợ cho những thay đổi dự kiến của Apple trong cơ sở hạ tầng SKAdNetwork.</li></ul> |
| <span id="agility"></span>Sự nhanh nhẹn | Nhà quảng cáo có thể thay đổi cấu hình đo lường nếu cần trong bảng điều khiển. |

</Accordion>

<div id="conversion-studio" />

<Accordion title="Conversion Studio">

AppsFlyer <Anchor target="_blank" href="/marketers/vi/docs/skan-conversion-studio">Conversion Studio</Anchor> là phần cốt lõi của giải pháp SKAN. Conversion Studio cung cấp cho bạn khả năng linh hoạt tối đa để tận dụng từng giá trị chuyển đổi. Bạn xác định chính xác dữ liệu đo lường nào cần mã hóa trong CV—bao gồm loại hoạt động và khoảng thời gian đo lường trong thời gian sau cài đặt. Có một số chế độ đo lường bạn có thể dùng để cấu hình cài đặt CV của bạn.

| Loại | Chế độ đo lường | Mô tả | Khung thời gian hoạt động |
| --- | --- | --- | --- |
| Linh hoạt | SKAN 4.0<br /><br />[Phương pháp thực hành tốt nhất] | Đặt kết hợp các chỉ số đo lường doanh thu, lượt chuyển đổi (sự kiện trong ứng dụng) và mức độ thu hút trong 3 khung thời gian hoạt động có thể cấu hình. | <ul><li>Khung thời gian 1: 1-2 ngày</li><li>Khung thời gian 2: 3-7 ngày</li><li>Khung thời gian 3: 8-35 ngày</li></ul> |
| Linh hoạt | <Anchor target="_blank" href="/marketers/vi/docs/skan-conversion-studio#custom">Tùy chính</Anchor> | Đặt kết hợp các chỉ số đo lường doanh thu, lượt chuyển đổi (sự kiện trong ứng dụng) và mức độ thu hút trong khung thời gian hoạt động có thể cấu hình. | 12 giờ-63 ngày |
| Cố định | Doanh thu<br /><br />[Mặc định]<br /><br />[Cũ] | Đo lường doanh thu bằng cách sử dụng một trong các khoảng sau:<ul><li>$1-$630 gia số $10</li><li>$1-$63 gia số $1</li><li>$0,01-$0,63 gia số $0,01</li></ul> | 24 giờ |
| Cố định | Chuyển đổi<br /><br />[Cũ] | Chọn 1-6 sự kiện trong ứng dụng. | 24 giờ |
| Cố định | Tương tác<br /><br />[Cũ] | Số lần người dùng thực hiện một sự kiện | 24 giờ |
| Linh hoạt | <Anchor target="_blank" href="/marketers/vi/docs/skan-cv-decode-map-your-cv-to-events">Giải mã</Anchor> | <ul><li>Tạo CV của riêng bạn để ánh xạ sự kiện và tự đặt CV trong ứng dụng. Sử dụng tùy chọn này nếu bạn không thể tích hợp SDK AppsFlyer vào ứng dụng của mình. Để sử dụng Giải mã, hãy đi đến **SKAN Conversion Studio,** nhấp vào tùy chọn (⋮), chọn **Tải lên tệp tin ánh xạ giải mã tùy chỉnh**.</li><li>SKAN 4 không được hỗ trợ</li></ul> | 12-1512 giờ (63 ngày) |

</Accordion>

<div id="additional-skadnetwork-information" />

## Thông tin bổ sung về SKAdNetwork

<div id="reporting-options" />

<Accordion title="Tùy chọn báo cáo">

Báo cáo SKAdNetwork không chứa mã định danh cấp người dùng.

| Tên báo cáo | Loại | Được AppsFlyer làm giàu | Phương thức phân phối | Tính năng cao cấp |
| --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/vi/docs/skan-aggregated-performance-report-api">Báo cáo hiệu suất hợp nhất của SKAN.</Anchor><br /><br />Tổng hợp lượt cài đặt, sự kiện trong ứng dụng và doanh thu. Dữ liệu tương tự như dữ liệu được tìm thấy trong bảng điều khiển SKAN. | Được tổng hợp bằng cách sử dụng ngày đến cài đặt hoặc đăng lại | Có | API | Không |
| <Anchor target="_blank" href="/marketers/vi/docs/skan-aggregated-postback-arrival-date-api">Báo cáo bài đăng lại tổng hợp SKAN</Anchor>.<br /><br />Đăng lại SKAN được tổng hợp ở mức chi tiết nhất có thể. | Tổng hợp bài đăng lại bằng sử dụng ngày đến của bài đăng lại | Không | API | Không |
| <Anchor target="_blank" href="/marketers/vi/docs/skan-raw-data-reports#raw-data-report-types">Báo cáo dữ liệu thô SKAN (cấp hàng) qua Data Locker</Anchor> (kèm theo các ví dụ).<br /><br />Các báo cáo có sẵn:<ul><li>Các bản đăng lại do iOS gửi với sự làm giàu dữ liệu do các đối tác mạng quảng cáo cung cấp</li><li>Lượt cài đặt</li><li>Tải lại</li><li>Sự kiện trong Ứng dụng</li><li>Phương diện quảng cáo SRN</li></ul> |  | Có | Data Locker | Đúng. Yêu cầu dữ liệu thô. Đăng ký Data Locker không bắt buộc. |
| Dữ liệu SKAN qua API Đẩy |  | Có | API Push | Có |

</Accordion>

<div id="skadnetwork-solution-implementation-checklist" />

<Accordion title="Danh sách kiểm tra việc triển khai giải pháp SKAdNetwork">

| Số thứ tự | Thao tác | Mô tả | Trách nhiệm |
| --- | --- | --- | --- |
| 1 | Chuẩn bị | <ul><li>Đọc <Anchor target="_blank" href="https://www.appsflyer.com/resources/prepare-your-app-ios14/">hướng dẫn giải pháp SKAdNetwork</Anchor></li><li>Đọc thêm: <Anchor target="_blank" href="https://www.appsflyer.com/resources/prepare-your-app-ios14/">Chuẩn bị ứng dụng của bạn cho iOS 14</Anchor></li></ul> | Nhà tiếp thị, Nhà phát triển |
| 2 | Cấu hình | Trong AppsFlyer, định cấu hình giải pháp SKAdNetwork trong <Anchor target="_blank" href="/marketers/vi/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>. | Nhà tiếp thị |
| 3 | Chuẩn bị ứng dụng | Di chuyển ứng dụng sang AppsFlyer <Anchor target="_blank" href="/marketers/vi/docs/sdk-integration-overview">V6 SDK</Anchor><ul><li>Không cần thay đổi logic ứng dụng cũng như mã ứng dụng.</li><li>Giải pháp SKAN của AppsFlyer dựa vào các sự kiện trong ứng dụng để thiết lập các sự kiện Gửi CV trong ứng dụng theo cách thông thường. Không yêu cầu thử nghiệm giải pháp cụ thể của SKAN.</li><li>Gửi ứng dụng đến App Store</li><li>Không cần đăng ký SKAdNetwork hoặc quy trình trong cửa hàng ứng dụng.</li></ul> | Nhà phát triển |
| 4 | Tích hợp đối tác | Các đối tác mạng quảng cáo phải tích hợp với AppsFlyer bằng tích hợp SKAdNetwork. Lưu ý! Mô phỏng AppsFlyer SKAdNetwork chứa dữ liệu của tất cả các đối tác của bạn bất kể trạng thái tích hợp hiện tại của họ. Điều này sẽ không xảy ra đối với trường hợp dữ liệu trực tiếp được các bài đăng lại của SKAdNetwork báo cáo.<br /><br />Liên quan đến các đối tác chạy chiến dịch của bạn, hãy hoàn thành những điều sau theo yêu cầu:<br /><br />**Không phải SRN**:<ol><li>Xác minh rằng đối tác có <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#c">huy hiệu năng lực AppsFlyer SKAdNetwork</Anchor> và trong giao diện người dùng đối tác, báo cáo chiến dịch SKAdNetwork đang được bật.</li><li>Xác minh rằng [tên sự kiện trong ứng dụng được ánh xạ](#sending-postbacks-to-integrated-partners) tới tên sự kiện trong ứng dụng của đối tác.</li></ol>**Quảng cáo Meta**:<ul><li><Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-interoperation-with-meta-ads">Định cấu hình khả năng tương tác AppsFlyer SKAdNetwork với quảng cáo Meta</Anchor></li></ul> | Nhà tiếp thị |

</Accordion>

<div id="troubleshooting-guide" />

<Accordion title="Hướng dẫn khắc phục sự cố">

| Dấu hiệu | Mô tả |
| --- | --- |
| Bảng điều khiển không chứa bất kỳ lượt cài đặt không tự nhiên nào. | <ol><li>Xác minh rằng **đo lường SKAdNetwork** đang bật.<ol><li>Đi đến **Configuration** (Cấu hình) > **SKAN Conversion Studio.**</li><li>Nhấp vào tùy chọn (⋮), kiểm tra cài đặt đo lường SKAN.</li></ol></li><li>Xác minh rằng phiên bản SDK của bạn là 6.2.6+.<ul><li>Để làm như vậy, hãy đi đến **Integration (Tích hợp)** > **SDK Information > Người dùng theo phiên bản SDK.**</li></ul></li><li>Nếu bạn sử dụng trình cắm SDK, hãy xác minh rằng bạn triển khai phiên bản hỗ trợ AppsFlyer SKAdNetwork.</li><li>Xác minh rằng các đối tác mạng quảng cáo của bạn được tích hợp với AppsFlyer và họ chuyển tiếp các bài đăng lại của iOS tới AppsFlyer.</li></ol> |
| Bảng điều khiển chứa các cài đặt không tự nhiên nhưng không có sự kiện trong ứng dụng nào cả. | <ol><li>Xác minh rằng phiên bản SDK của bạn là 6.2.6+.<ul><li>Để làm như vậy, hãy đi đến **Integration (Tích hợp)** > **SDK Information > Người dùng theo phiên bản SDK.**</li></ul></li><li>Nếu bạn sử dụng trình cắm SDK, hãy xác minh rằng bạn triển khai phiên bản hỗ trợ AppsFlyer SKAdNetwork.</li><li>Bạn có gửi sự kiện bằng S2S không? Nếu như vậy, hãy xác minh rằng **Ghi nhận kiện trong ứng dụng được gửi bởi API từ máy chủ đến máy chủ** đang bật.<ol><li>Đi đến **Configuration** (Cấu hình) > **SKAN Conversion Studio.**</li><li>**Nhấp vào tùy chọn (⋮), xác minh đảm bảo rằng cấu hình S2S đang bật.** Lưu ý: Trong chế độ đo lường Tùy chỉnh và Giải mã, tùy chọn cài đặt này luôn bật và không thể thay đổi.</li></ol></li></ol> |
| Bảng điều khiển chứa các cài đặt và một số sự kiện trong ứng dụng. Thiếu một số sự kiện trong ứng dụng. | <ol><li>Bạn có gửi sự kiện bằng S2S không? Nếu như vậy, hãy xác minh rằng **Ghi nhận kiện trong ứng dụng được gửi bởi API từ máy chủ đến máy chủ** đang bật.<ol><li>Đi đến **Configuration** (Cấu hình) > **SKAN Conversion Studio.**</li><li>**Nhấp vào tùy chọn (⋮), xác minh đảm bảo rằng cấu hình S2S đang bật.** Lưu ý: Trong chế độ đo lường Tùy chỉnh và Giải mã, tùy chọn cài đặt này luôn bật và không thể thay đổi.</li></ol></li><li>Kiểm tra <Anchor target="_blank" href="/marketers/vi/docs/skan-raw-data-reports#raw-data-report-types">dữ liệu thô đăng lại</Anchor> của bạn để xem liệu tất cả các sự kiện có được báo cáo hay không.</li></ol> |
| Vị trí địa lý (quốc gia) bị sai lệch | Dữ liệu địa lý được lấy như sau:<ul><li>Theo quốc gia liên kết với một chiến dịch và được mạng quảng cáo báo cáo cho AppsFlyer.</li><li>Sử dụng địa chỉ IP của thiết bị. Bắt đầu từ iOS 14.6, địa chỉ này là địa chỉ proxy và không thực sự đại diện cho vị trí địa lý của người dùng.</li></ul> |

</Accordion>

<div id="timing-from-app-install-until-dashboard-and-reports-update" />

<Accordion title="Thời gian được xác định từ khi cài đặt ứng dụng cho đến khi cập nhật bảng điều khiển và báo cáo">

| Mã khóa | Tên phần tử | Mô tả | Ví dụ A | Ví dụ B | Ví dụ C | Ví dụ D | Ví dụ E |
| --- | --- | --- | --- | --- | --- | --- | --- |
| A | Cửa sổ đo lường 1 của SKAN 4 | <ul><li>Trong cửa sổ này, các CV được đặt bởi ứng dụng</li><li>0 - 2 ngày</li><li>Cửa sổ có thể được khóa trước 2 ngày trong Conversion Studio</li></ul> | - | - | 2 ngày | - | - |
| B | Cửa sổ đo lường 2 của SKAN 4 | <ul><li>Trong cửa sổ này, CV được đặt bởi ứng dụng</li><li>3 - 7 ngày</li><li>Cửa sổ có thể được khóa trước 7 ngày trong Conversion Studio</li></ul> | - | - | - | 7 ngày | - |
| C | Cửa sổ đo lường 3 của SKAN 4 | <ul><li>Trong cửa sổ này, CV được đặt bởi ứng dụng</li><li>8 - 35 ngày</li><li>Cửa sổ có thể được khóa trước 35 ngày trong Conversion Studio</li></ul> | - | - |  | - | 35 ngày |
| D | Độ trễ khi gửi postback trong cửa sổ đo lường 1 của SKAN 4 | 24 - 48 giờ | - | - | 24 - 48 giờ | - | - |
| E | Độ trễ trong cửa sổ đo lường 2 - 3 của SKAN 4 | 24 - 144 giờ | - | - | - | 24 - 144 giờ | 24 - 144 giờ |
| F | Khung thời gian hoạt động<br /><br />(Không dành cho SKAN 4) | <ul><li>Trong khung thời gian, CV được đặt bởi ứng dụng.</li><li>Khung thời gian bắt đầu khi ứng dụng được mở lần đầu.</li><li>Thời lượng từ 12 giờ - 63 ngày.</li></ul> | 24 giờ | 72 giờ | - | - | - |
| G | Bộ định thời SKAdNetwork<br /><br />(Không dành cho SKAN 4) | <ul><li>Đồng hồ đếm ngược: 24 giờ</li><li>Mỗi khi CV tăng, bộ định thời sẽ được đặt lại. Điều này có nghĩa là bộ định thời bắt đầu đếm ngược từ 24 giờ.</li></ul> | 0-24 giờ | 0-24 giờ | - | - | - |
| H | Thời gian trễ ngẫu nhiên SKAdNetwork<br /><br />(Không dành cho SKAN 4) | Thời gian trễ ngẫu nhiên khi gửi postback. Đếm ngược bắt đầu vào cuối khoảng thời gian được F+G xác định. | 0-24 giờ | 0-24 giờ | - | - | - |
| I | Xử lý AppsFlyer | Các postback nhận được vào một ngày cho cụ thể xử lý vào cuối ngày theo giờ UTC, bắt đầu từ 00:01 giờ của ngày hôm sau. Dữ liệu có sẵn 8 giờ sau đó. Có nghĩa là việc xử lý mất 8-32 giờ. Độ trễ trung bình là 20 giờ. Ví dụ: một đăng lại nhận được vào thứ Hai được xử lý vào thứ Ba. Bảng điều khiển cập nhật trước 08:00 giờ UTC. | 8-32 giờ | 8-32 giờ | 8-32 giờ | 8-32 giờ | 8-32 giờ |
| J | Tóm lược | Tổng thời gian có thể trôi qua | 32 giờ - 104 giờ | 80-152 giờ | 80 giờ - 128 giờ | 200 giờ - 344 giờ | 872 giờ - 1016 giờ |

</Accordion>

<div id="organic-metrics-in-the-context-of-skadnetwork" />

<Accordion title="Các chỉ số tự nhiên trong ngữ cảnh của SKAdNetwork">

Các chỉ số tự nhiên trong bảng điều khiển SKAdNetwork được tính theo cơ chế sau:

* Phép đo tự nhiên cho các sự kiện trong ứng dụng sẽ không khả dụng nếu chế độ đo lường bạn đã chọn là <Anchor target="_blank" href="/marketers/vi/docs/skan-conversion-studio#các-khái-niệm-cơ-bản-về-skan-conversion-studio">SKAN 4, Tùy chỉnh hoặc Giải mã.</Anchor>
* Apple SKAdNetwork gửi các bài đăng lại liên quan đến những người dùng cài đặt sau khi tương tác với một nguồn phương tiện. Điều này cung cấp các số liệu không tự nhiên.
* Bảng điều khiển phân bổ AppsFlyer chứa các số liệu về tất cả các lượt cài đặt không phân biệt nguồn.  Xem phần <Anchor target="_blank" href="/marketers/vi/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side">xem phân bổ AppsFlyer song song với phân bổ SKAN</Anchor>.
* Sử dụng dữ liệu này, các phép đo tự nhiên được tính là A-B, trong đó:
  * A = Tổng số tất cả người dùng dựa trên bảng điều khiển truyền thống
  * B = Người dùng không tự nhiên theo báo cáo trong các bài đăng lại của SKAdNetwork

**Cảnh báo liên quan đến Apple Search Ads**: Số lượt cài đặt do Apple Search Ads mang lại trong bảng điều khiển truyền thống là không phải tự nhiên. Tuy nhiên, trong ngữ cảnh của SKAdNetwork, chúng tạo thành một phần của chỉ số tự nhiên.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Nhận xét |
| --- | --- |
| Truy cập mạng quảng cáo | Các mạng quảng cáo được cung cấp các bài đăng lại |
| Đại lý | Không được hỗ trợ. Điều này có nghĩa là các đại lý không được bật các mạng quảng cáo chạy các chiến dịch SKAdNetwork. Đại lý! Yêu cầu nhà quảng cáo kích hoạt Mạng quảng cáo, đừng tự mình làm điều đó. Các đại lý có thể cho biết họ đã mang lại cho người dùng bằng cách triển khai <Anchor target="_blank" href="/partners/vi/docs/getting-started-agency-onboarding#skadnetwork-agency-campaigns">công nhận đại lý SKAN</Anchor>. |
| Tính minh bạch của agency | Không áp dụng |
| Múi giờ | UTC |
| Tiền tệ | USD |
| Dữ liệu tự nhiên | Dựa trên dữ liệu sự kiện SDK. Ví dụ: số liệu về lượt cài đặt tự nhiên được tính như sau: Dữ liệu của tất cả các lượt cài đặt do SDK báo cáo trừ số lượt cài đặt không tự nhiên do SKAdNetworks báo cáo. |
| Dữ liệu không tự nhiên | Dựa trên các bài đăng lại của SKAdNetwork |
| Tính cập nhật của dữ liệu | Hàng ngày |
| Dữ liệu lịch sử | Ngày sớm nhất, tính khả dụng của iOS 14 (ngày 16 tháng 9 năm 2020) |
| Truy cập của người dùng | Người dùng tài khoản phải có <Anchor target="_blank" href="/marketers/vi/docs/user-management">các quyền cần thiết</Anchor> |
| Clip ứng dụng | Clip ứng dụng được cho là tự nhiên trong bảng điều khiển SKAdNetwork. Sử dụng bảng điều khiển tổng quan xem các nguồn phương tiện gọi hàm. |

</Accordion>

<div id="skan-integrated-partners" />

## Đối tác tích hợp SKAN

<div id="recording-ad-revenue" />

<Accordion title="Ghi nhận doanh thu quảng cáo">

Phân bổ doanh thu quảng cáo được tạo ra trong các cửa sổ đo lường SKAdNetwork cho chiến dịch mang lại người dùng. Hiện tại, điều này được giới hạn đến các nhà quảng cáo được tích hợp với doanh thu quảng cáo cấp lượt hiển thị chung thông qua SDK.

Để ghi lại doanh thu quảng cáo trong bảng điều khiển SKAN của bạn:

* Tích hợp <Anchor target="_blank" href="/marketers/vi/docs/integrate-the-roi360-ad-revenue-sdk-api">SDK doanh thu quảng cáo cấp lượt hiển thị chung</Anchor> vào ứng dụng của bạn.
* Nếu bạn sử dụng chế độ cố định SKAN Conversion Studio, <Anchor target="_blank" href="/marketers/vi/docs/skan-conversion-studio#report-events-by-servertoserver-api">bật hỗ trợ máy chủ đến máy chủ SKAdNetwork</Anchor>.

**Lưu ý**: Xem tài liệu về <Anchor target="_blank" href="/marketers/vi/docs/integrate-the-roi360-ad-revenue-sdk-api">trình kết nối SDK chung</Anchor> để biết thông tin về các nguồn quảng cáo có sẵn đề dàn xếp.

</Accordion>

<div id="sending-postbacks-to-integrated-partners" />

<Accordion title="Gửi bài đăng lại cho đối tác tích hợp">

AppsFlyer gửi cho các đối tác tích hợp các đăng lại liên quan đến việc phân bổ SKAN (đối với SKAN 4, các đăng lại chỉ được gửi cho khung thời gian 1).

Lưu ý các tùy chọn và yêu cầu khác nhau trong bảng sau

| Tiêu đề | Mô tả |
| --- | --- |
| <span id="transaction-id-sharing"></span>Chia sẻ ID giao dịch | **Hành động bắt buộc**: Kiểm tra với đối tác tích hợp nếu họ yêu cầu <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/verifying_an_install_validation_postback">ID giao dịch</Anchor> và định cấu hình cài đặt cho phù hợp.<br /><br />AppsFlyer gửi các bài đăng lại đối tác mạng quảng cáo được phân bổ. Có nghĩa là các bài đăng lại đã được giải mã, không phải là bản sao của các bài đăng lại SKAdNetwork nhận được từ iOS. Các bài đăng lại này chứa dữ liệu CV được giải mã liên quan đến cài đặt và dữ liệu sự kiện trong ứng dụng được liên kết của các hành động do người dùng thực hiện trong Khung thời gian hoạt động .<br /><br />Vì ID giao dịch có thể được sử dụng để giải mã CV của bạn, chúng tôi không chia sẻ nó khi chưa được sự cho phép của bạn.<br /><br />**Chia sẻ ID giao dịch**<br /><br />Nhà quảng cáo <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#b">bật tính năng chia sẻ ID giao dịch</Anchor> như sau: Trong AppsFlyer, đi đến **Configuration** > **Active Integrations** > chọn đối tác > **Integration tab** > **Data sharing**. |
| <span id="inapp-event-mapping-verification"></span>Xác minh ánh xạ sự kiện trong ứng dụng | **<span id="1611499069.009700"></span>Hành động bắt buộc**: Bạn phải <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#phương-thức-ánh-xạ">ánh xạ các sự kiện trong ứng dụng</Anchor> của mình với tên sự kiện đối tác tương ứng để đối tác ghi lại các bài đăng lại một cách chính xác.<br /><br />Đối với mỗi đối tác chạy chiến dịch SKAdNetwork, hãy xác minh rằng sự kiện trong ứng dụng được đặt theo loại đo lường ứng dụng đã chọn.<br /><br />**Để xác minh và thay đổi ánh xạ sự kiện trong ứng dụng của đối tác**:<ol><li>Trong AppsFlyer, đi đến **Configuration** > **Active Integrations**.</li><li>Chọn đối tác.</li><li>Đi tới tab **Integration** (Tích hợp).</li><li>Xác minh và nếu cần, thực hiện các thay đổi cài đặt như sau:<ol><li>Bật tùy chọn **In-app events postback (Đăng lại sự kiện trong ứng dụng)**.</li><li>Xác minh rằng các sự kiện trong ứng dụng, **tên sự kiện SDK** mà bạn đặt trong đo lường SKAdNetwork được ánh xạ tới **Mã định danh sự kiện của đối tác**.</li></ol></li><li>Nhấp vào **Save integration (Lưu tích hợp)**.</li></ol> |

</Accordion>

<div id="see-also" />

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/about-att-and-skan">Hướng dẫn bắt đầu nhanh & Câu hỏi thường gặp về iOS 14, ATT và SKAN</Anchor>
> * <Anchor target="_blank" href="/marketers/vi/docs/skan-conversion-studio">Thiết lập phép đo bằng SKAN Conversion Studio (cài đặt SKAdNetwork)</Anchor>
> * <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">Bảng điều khiển AppsFlyer SKAN</Anchor>
> * <Anchor target="_blank" href="/marketers/vi/docs/skan-integrated-partners-list">Danh sách đối tác tích hợp SKAN</Anchor>
> * Khả năng tương tác đối tác SKAN yêu cầu thiết lập trong AppsFlyer:
>   * <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-interoperation-with-meta-ads">Quảng cáo Meta</Anchor>
>   * <Anchor target="_blank" href="/marketers/vi/docs/get-skan-postback-data-from-google-ads">Google Ads</Anchor>
>   * <Anchor target="_blank" href="/marketers/vi/docs/skan-interoperation-with-tiktok-for-business">TikTok dành cho Doanh nghiệp</Anchor>
>   * <Anchor target="_blank" href="/marketers/vi/docs/skan-interoperation-with-snapchat">Snapchat</Anchor>

<div data-zendesk-anchors="01H7Z06Z03AQY25A3E45Z47A9G=skan 01H7Z06Z03CSKH1ZB9RQP6SHA8=m%C3%A1ch-nh%E1%BB%8F 01H7Z06Z03MRE6BCSG1AEXN947=about-apple-skan appsflyer-skan-solution=gi%E1%BA%A3i-ph%C3%A1p-appsflyer-skan 01H7Z06Z04G479NAKBEA33SGSZ=gi%E1%BA%A3i-ph%C3%A1p-appsflyer-skan 01H7Z06Z05CAVK3CR7F5FBKFC5=principles-and-flow skan-attribution-flow=lu%E1%BB%93ng-ph%C3%A2n-b%E1%BB%95-skan 01H7Z06Z05EGK5QBDK6G7BJQJK=lu%E1%BB%93ng-ph%C3%A2n-b%E1%BB%95-skan 01H7Z06Z053M2H3CJ6SV4VDZPZ=conversion-studio additional-skadnetwork-information=th%C3%B4ng-tin-b%E1%BB%95-sung-v%E1%BB%81-skadnetwork 01H7Z06Z05556NQ35HMR4E2TRY=th%C3%B4ng-tin-b%E1%BB%95-sung-v%E1%BB%81-skadnetwork 01H7Z06Z05G0YB56GDG5E196QM=reporting-options 01H7Z06Z05M3BPSBTCMJ3NHK5D=skadnetwork-solution-implementation-checklist 01H7Z06Z05YF4J0MPMJ40EG7BX=troubleshooting-guide 01H7Z06Z0502NW8KFJ7XRZFWJR=timing-from-app-install-until-dashboard-and-reports-update 01H7Z06Z068462E4QTGTSMNS7H=organic-metrics-in-the-context-of-skadnetwork 01H7Z06Z0615QHCY6JZ4MAMTJ8=traits-and-limitations skadnetwork-integrated-partners=%C4%91%E1%BB%91i-t%C3%A1c-t%C3%ADch-h%E1%BB%A3p-skan 01H7Z06Z06KGT6ESN42XTJSK2F=%C4%91%E1%BB%91i-t%C3%A1c-t%C3%ADch-h%E1%BB%A3p-skan 01H7Z06Z06NWJQ6W50MCD3P352=recording-ad-revenue 01H7Z06Z06K2ZB949GGTJV6MJP=sending-postbacks-to-integrated-partners h_01HE7TC49KRRX1RVGX1FY7C52T=xem-th%C3%AAm" />
