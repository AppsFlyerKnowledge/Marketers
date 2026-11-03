---
title: Mô hình phân bổ của AppsFlyer
metadata:
  keywords:
    - Attribution
    - NativeTrack
    - Look-Back
    - Twiiter
    - Multi-Channel
    - Re-Install
    - Facebook
    - media source
    - Advertisers
    - Ad Networks
    - reinstall
    - branch
    - attribution determination
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T10:54:37Z'
  edited_at: '2023-11-17T02:09:48Z'
  id: 207447053
  locale: vi
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/vi/articles/207447053
---
> **Khái quát:** AppsFlyer xác định nguồn truyền thông thúc đẩy người dùng cài đặt hoặc thu hút lại với một ứng dụng và phân bổ hành động của người dùng cho nguồn đó bằng cách sử dụng mô hình phân bổ của AppsFlyer.

[![Mobile_user_journey.png](https://support.appsflyer.com/hc/article_attachments/19544107641105)](https://support.appsflyer.com/hc/article_attachments/19544107641105)

## Phân bổ là gì?

**Phân bổ** là hành động xác định nguyên nhân thúc đẩy (khiến) người dùng cài đặt một ứng dụng hoặc thực hiện các hành vi hậu cài đặt như thu hút lại và phân bổ lại. Kết quả phân bổ là:

* **Nguồn truyền thông không tự nhiên**: Người dùng đã tương tác (thường bằng cách hiển thị hoặc nhấp chuột) với nguồn truyền thông.
* **Tự nhiên**: Người dùng không tương tác với nguồn truyền thông. Lưu ý! Để dễ hiểu, chúng tôi thường đề cập là người dùng được *phân bổ một cách tự nhiên*. Chúng tôi biết rằng điều này không hoàn toàn đúng, vì người dùng cài đặt tự nhiên không hề được phân bổ.

Phân bổ là thiết yếu trong việc tối ưu hóa việc thu hút người dùng cũng như tối ưu hóa kết quả và nỗ lực thu hút lại.

> 👍 **Lời khuyên**
>
> Bạn muốn biết thêm về phân bổ? Hãy xem <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7766/play/18609/attribution-101-part-1">khóa học ngắn, bổ ích</Anchor> này trên Cổng thông tin Học tập AppsFlyer.

## Lượt cài đặt ứng dụng là gì?

**Mô hình Phân bổ** là một bộ quy tắc xác định cách thức chỉ định ghi nhận của một sự kiện cho các điểm tiếp xúc trong lộ trình chuyển đổi. Mỗi người tham gia trong hệ sinh thái tiếp thị ứng dụng, Google Play, App Store, Apple, CTV, PC và nền tảng bảng điều khiển , mạng quảng cáo như quảng cáo Meta và Twitter cũng như các công ty đo lường di động đều có mô hình phân bổ của riêng họ. Mỗi mô hình phân bổ tính lượt cài đặt và sự kiện theo cách khác nhau.

Điều quan trọng không phải là sự khác biệt giữa các mô hình mà là việc các quy tắc phải rõ ràng và được thực hiện theo cách trung thực, khách quan. Cho phép nhà quảng cáo tối ưu hóa chiến dịch và so sánh chất lượng hiệu suất của người dùng.

Điều quan trọng là phải hiểu các mô hình và quy tắc của những người chơi mà bạn làm việc cùng. Điều quan trọng nhất là hiểu mô hình và khác biệt nhỏ giữa các phương thức được AppsFlyer hỗ trợ.

Trong AppsFlyer, có thể xảy ra một sự kiện phân bổ khi xảy ra bất kỳ tình huống nào sau đây:

* Trong trường hợp thu hút người dùng: Lượt **cài đặt** được ghi nhận và phân bổ sau khi người dùng tải xuống và khởi chạy ứng dụng. Điều này có nghĩa là trong AppsFlyer, **nhãn thời gian cài đặt ứng dụng là lần khởi chạy đầu tiên**. Ngược lại, các mạng quảng cáo sử dụng thời gian thu hút và các cửa hàng ứng dụng sử dụng thời gian tải xuống.
* Trong trường hợp [nhắm mục tiêu lại](/docs/appsflyer-attribution-model#retargeting-attribution):
  * **Thu hút lại**
  * **Phân bổ lại**

## Phương thức phân bổ

AppsFlyer sử dụng một số phương thức phân bổ được liệt kê trong bảng sau:

<table><thead><tr><th>Phương thức</th><th>Sử dụng ID</th><th>Kỹ thuật</th><th><p>Được phân bổ bởi</p></th><th><p>Android (1)</p></th><th>iOS </th><th>Nền tảng Window Universal</th><th>Nền tảng CTV, PC và bảng điều khiển (3)</th></tr></thead><tbody><tr><td><a href="#install-referrer-android-only">Liên kết giới thiệu</a></td><td>Không</td><td>Xác định</td><td>AppsFlyer</td><td>Có (2)</td><td>Không</td><td>Có</td><td>Không</td></tr><tr><td><a href="./appsflyer-attribution-model#device-id-matching">Khớp ID thiết bị</a></td><td>Có</td><td>Xác định</td><td>AppsFlyer</td><td>Có </td><td>Có</td><td>Có</td><td>Có</td></tr><tr><td><a href="./appsflyer-attribution-model#probabilistic-modeling">Mô hình xác suất</a></td><td>Không</td><td>Xác suất</td><td>AppsFlyer</td><td>Có </td><td>Có </td><td>Không</td><td>Có</td></tr><tr><td><a href="./appsflyer-attribution-model#aggregated-advanced-privacy-aap">Quyền riêng tư Nâng cao Hợp nhất (AAP)</a></td><td>Không</td><td>Hợp nhất</td><td>AppsFlyer</td><td>Không</td><td>Có</td><td>Không</td><td>Không</td></tr><tr><td><a href="./appsflyer-attribution-model#preload-campaigns">Tải trước</a></td><td>Không</td><td>Xác định</td><td>AppsFlyer</td><td>Có</td><td>Không</td><td>Có</td><td>Không</td></tr><tr><td> <a href="./skadnetwork-skan-solution-guide" target="_blank">SKAdNetwork</a> (SKAN)</td><td>Không</td><td>Xác định</td><td>Apple</td><td>Không</td><td>Có</td><td>Không</td><td>Không</td></tr><tr><td><a href="./apple-ads-integration-setup" target="_blank">Apple Search Ads</a></td><td>Không</td><td>Xác định</td><td>Apple</td><td>Không</td><td>Có</td><td>Không</td><td>Không</td></tr><tr><td><a href="./appsflyer-attribution-model#deep-link">Liên kết sâu</a></td><td>Không</td><td>Xác định</td><td>AppsFlyer</td><td>Có</td><td>Có</td><td>Có</td><td>Không</td></tr><tr><td colspan="7"><p>(1) Google Play và các cửa hàng của bên thứ ba</p><p>(2) Được hỗ trợ bởi một số cửa hàng bên thứ ba</p><p>(3) Xem <a href="./ctv-pc-and-console-platform-attribution-concepts#nền-tảng-được-hỗ-trợ" target="_blank">danh sách đầy đủ các nền tảng <span>CTV, PC và bảng điều khiển</span></a> </p></td><td></td></tr></tbody></table>

Các phương thức phân bổ được sử dụng theo mức độ ưu tiên được hiển thị trong bảng. Khi có lượt cài đặt mới, nếu có nhiều hơn một hành động thu hút hợp lệ, **AppsFlyer sẽ ưu tiên lượt nhấp thay vì lượt hiển thị và phương thức xác định hơn là phương pháp xác suất**.

![Attribution method priorities 23.png](https://support.appsflyer.com/hc/article_attachments/19910400460561)

Xem mô tả chi tiết bên dưới về các mô hình phân bổ của AppsFlyer.

<div id="install-referrer-android-only" />

<Accordion title="Người giới thiệu cài đặt (chỉ áp dụng với Android)">

Các ứng dụng Android được tải xuống từ Google Play và một số cửa hàng ứng dụng khác thường được phân bổ theo phương thức liên kết giới thiệu cài đặt. Liên kết giới thiệu cung cấp URL gốc, được nhấp vào trước khi chuyển hướng đến cửa hàng Android. Đây là phương thức chính để phân bổ Android. Hiện tại, Google Play, cửa hàng ứng dụng Huawei, Samsung Galaxy Store và Xiaomi GetApps Store, hỗ trợ phân bổ liên kết giới thiệu cài đặt. <Anchor target="_blank" href="/marketers/vi/docs/set-up-multi-store-android-attribution#referrer-implementation-thirdparty-android-app-stores">Phân bổ cửa hàng ứng dụng thay thế bằng cách sử dụng người giới thiệu.</Anchor>

</Accordion>

<div id="device-id-matching" />

<Accordion title="Khớp ID thiết bị">

Mạng quảng cáo có quyền truy cập thiết bị người dùng sẽ gửi ID thiết bị cho AppsFlyer trên URL nhấp chuột, hoặc khi thông báo cho AppsFlyer rằng một lượt hiển thị đã được ghi nhận. Điều này cho phép AppsFlyer khớp ID thiết bị của lượt nhấp với ID thiết bị được tìm nạp bởi SDK của AppsFlyer.

Khớp ID thiết bị là phương pháp ghi công chính áp dụng với iOS.

Các ID khả dụng là:

* **Thiết bị iOS**: IDFA, IDFV
* **Các thiết bị Android: có dịch vụ Google Play:** GAID
* **Các thiết bị Android không có dịch vụ Google Play**: OAID, ID Android, IMEI, ID Fire

ID thiết bị có thể được băm bằng SHA1 hoặc MD5 trên các đường dẫn phân bổ.

</Accordion>

<div id="device-id-matching-using-idfv-ios" />

<Accordion title="So khớp ID Thiết bị bằng IDFV (iOS)">

* Mã định danh cho nhà cung cấp (IDFV) có sẵn trong iOS 6.0+. Mã này không tuân theo các cơ chế <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor> và LAT của Apple. Mã này luôn có sẵn và có thể được sử dụng để quảng cáo chéo cho các ứng dụng từ cùng một nhà cung cấp.
* AppsFlyer SDK thu thập IDFV theo mặc định.
* <Anchor target="_blank" href="https://developer.apple.com/documentation/uikit/uidevice/1620059-identifierforvendor">Theo Apple,</Anchor> *Giá trị của thuộc tính này là như nhau đối với các ứng dụng đến từ cùng một nhà cung cấp chạy trên cùng một thiết bị.*
* IDFV được Apple tạo ra khi người dùng cài đặt ứng dụng đầu tiên của một nhà cung cấp nhất định. Có nghĩa là, Apple kiểm tra rằng không có ứng dụng nào khác từ cùng một nhà cung cấp trên thiết bị này. Do đó,  việc xóa tất cả các ứng dụng của một nhà cung cấp nhất định và sau đó cài đặt một ứng dụng từ cùng một nhà cung cấp dẫn đến một IDFV mới.
* Bạn nên gửi IDFV nếu có. Điều này sẽ giúp cải thiện việc phân bổ. Chúng tôi sử dụng IDFV trong một số tình huống bao gồm:
  * Phân bổ quảng cáo chéo.
  * Phân bổ lượt cài đặt lại trên cùng một thiết bị.
  * Báo cáo dữ liệu thô.
  * Đối tượng.

</Accordion>

<div id="device-id-matching-for-selfreporting-networks" />

<Accordion title="Khớp ID thiết bị cho mạng Tự báo cáo">

Khi khởi chạy ứng dụng lần đầu, AppsFlyer sẽ kiểm tra cài đặt của ứng dụng xem có được cấu hình để nhận lưu lượng truy cập từ các <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns#srn-được-tích-hợp-với-appsflyer">mạng tự báo cáo</Anchor> (SRN), như quảng cáo Meta, Snapchat và Google Ads hay không.

AppsFlyer truy vấn các SRN liên quan sử dụng ID thiết bị duy nhất của lượt cài đặt mới. Truy vấn sẽ sử dụng API Đối tác Đo lường Di động (MMP) như theo xác định của các SRN. Dựa trên phản hồi, AppsFlyer có thể phân bổ người dùng mới cho SRN.

</Accordion>

<div id="probabilistic-modeling" />

<Accordion title="Mô hình xác suất">

Mô hình xác suất là một kỹ thuật thống kê tận dụng máy học để ước tính hiệu suất chiến dịch. Các thông số mô hình xác suất được thu thập:

* Ban đầu khi nhấp chuột hoặc xem quảng cáo (nếu được bật)
* Một lần nữa khi ứng dụng được khởi chạy

#### **Lưu ý đối với ứng dụng iOS:**

Bắt đầu từ phiên bản iOS 14.5 trở lên, mô hình xác suất được giới hạn trong trường hợp truyền thông sở hữu, quảng cáo chéo và các luồng chuyển đổi từ web đến ứng dụng đã có sự đồng ý. Trong các trường hợp khác, [Quyền riêng tư Nâng cao Hợp nhất](/docs/appsflyer-attribution-model#aggregated-advanced-privacy-aap) sẽ được sử dụng.

**Đặc điểm triển khai**

* Sử dụng thống kê và không dựa trên ID duy nhất.
* Là một phương thức dự phòng, được sử dụng trong trường hợp không có ID người giới thiệu hoặc quảng cáo. Các phương thức phân bổ xác định, tức là lượt nhấp chuột có người giới thiệu hoặc ID khớp, được ưu tiên nếu chúng xảy ra trong khung thời gian xem lại.
* Khung thời gian phân bổ được AppsFlyer xác định động, dựa trên mạng người dùng. Thời lượng khung thời gian có tính thích ứng nhưng ngắn hơn khung thời gian của các phương thức khác (lên đến 24 giờ).
* Mô hình xác suất lượt nhấp qua luôn được bật.
* Mô hình xác suất lượt xem hết cần được bật trong trang cài đặt của ứng dụng và trong tab tích hợp của mạng không phải SRN. Đối với các ứng dụng CTV, PC và bảng điều khiển, tính năng này được bật mặc định.

#### Các thông số tạo mô hình xác suất cho mạng quảng cáo

Mạng quảng cáo đang triển khai tính năng phân bổ Tạo mô hình xác suất phải gửi các thông số sau qua  đường dẫn phân bổ hoặc qua tiêu đề yêu cầu HTTP:

* <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters#af_ua">af\_ua</Anchor>
* <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters#af_os_version">af\_os\_version</Anchor>
* <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters#af_model">af\_model</Anchor>
* <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters#af_ip">af\_ip</Anchor>

</Accordion>

<div id="aggregated-advanced-privacy-aap" />

<Accordion title="Quyền riêng tư Nâng cao Hợp nhất (AAP)">

Quyền riêng tư Nâng cao Hợp nhất (AAP) hiển thị kết quả hiệu suất chiến dịch theo dạng hợp nhất, ngăn chặn bất kỳ tùy chọn nào theo dõi người dùng trên các ứng dụng và trang web do các công ty khác nhau sở hữu và khả năng xác định một người dùng hoặc một thiết bị riêng.

AAP sử dụng các mức độ quyền riêng tư của SKAdNetwork Apple làm tiêu chuẩn tối thiểu cho các ngưỡng bảo vệ quyền riêng tư của mình. AAP là mô hình phân bổ mặc định cho các thiết bị của Apple hoạt động trên iOS từ phiên bản 14.5 trở lên, ngoại trừ các trường hợp được Apple cho phép một cách rõ ràng, chẳng hạn như truyền thông sở hữu và người dùng đồng ý ATT.

Không giống như các phương thức phân bổ khác được mô tả, mục tiêu của thuật toán máy học AAP là tối đa hóa độ chính xác của hiệu suất hợp nhất của chiến dịch, chứ không phải độ chính xác của phân bổ người dùng cuối.

</Accordion>

<div id="preload-campaigns" />

<Accordion title="Các chiến dịch tải trước">

Trong chiến dịch tải trước, đối tác tải trước sẽ cài ứng dụng trên thiết bị của người dùng tại nhà máy hoặc khi kích hoạt thiết bị. Đối tác tải trước có thể là:

* Nhà sản xuất Thiết bị Gốc (OEM)
* Nền tảng khám phá ứng dụng
* Các nhà cung cấp dịch vụ di động

Có 3 phương pháp để phân bổ các chiến dịch tải trước. Có thể sử dụng đồng thời cả ba phương pháp vì chúng không can thiệp vào cơ chế của nhau.

3 phương pháp và một vài thông số kỹ thuật chính được nêu trong bảng sau. Nhấp vào liên kết để tìm hiểu thêm về từng phương pháp tải trước.

<table><thead><tr><th>Phương thức phân bổ tải trước</th><th>Trường hợp sử dụng</th><th>Thông tin từ kích hoạt thiết bị đến khởi chạy ứng dụng\*</th><th>Khoảng thời gian xem lại\*\*</th><th>Loại khớp trong dữ liệu thô</th></tr></thead><tbody><tr><td> <a href="./set-up-appsflyer-preload-referrer-attribution" target="_blank">Người giới thiệu AppsFlyer</a>\*</td><td><ul><li>Được tải trước tại nhà máy</li><li>Được tải trước tại thời điểm kích hoạt thiết bị</li></ul></td><td>Có</td><td><ul><li>Lên đến 180 ngày</li><li>Mặc định là 90 ngày</li></ul></td><td><ul><li>Tải trước: preload_rfr</li><li>Nhấp vào để tải về: af_referrer</li></ul></td></tr><tr><td> <a href="./measure-preload-campaigns-with-google-play-install" target="_blank">Tự động cài đặt Google Play</a>\*\*</td><td><p>Được tải trước tại thời điểm kích hoạt thiết bị (đối với ứng dụng Google Play)</p></td><td>Không</td><td><ul><li>Lên đến 180 ngày</li><li>Mặc định là 90 ngày</li></ul></td><td>preload_pai</td></tr><tr><td> <a href="./appsflyer-factory-preinstall-using-manifest-android" target="_blank">Tải trước tại nhà máy thông qua biến System Property (Android)</a>\*\*</td><td><ul><li>Được tải trước tại nhà máy</li><li>Được tải trước tại thời điểm kích hoạt thiết bị</li></ul></td><td>Không</td><td><p>Không giới hạn</p></td><td><p>preload_conf</p></td></tr><tr><td colspan="5"><p>\* Giải pháp tải trước của người giới thiệu của AppsFlyer cung cấp khả năng hiển thị và đo lường giữa lần đầu kích hoạt thiết bị và lần đầu khởi chạy ứng dụng. Điều này cho phép bạn xem có bao nhiêu thiết bị đã được một đối tác cụ thể kích hoạt mà có ứng dụng được tải sẵn trên thiết bị và sau đó xem thời điểm ứng dụng được khởi chạy lần đầu tiên.</p><p>Đối với hai phương pháp còn lại, chỉ xác định phân bổ sau khi người dùng khởi chạy ứng dụng lần đầu tiên, số lượng thiết bị đã cài đặt ứng dụng trước lần khởi chạy đầu tiên sẽ không được tính.</p><p>\*\* Có thể mất vài ngày hoặc vài tuần, bắt đầu từ lần đầu tiên người dùng bật thiết bị của mình cho đến lần đầu tiên họ khởi chạy ứng dụng tải trước. Do đó, AppsFlyer ưu tiên cao nhất cho các chiến dịch tải trước khi đang xác định phân bổ, với khung thời gian xem lại lâu hơn.</p></td></tr></tbody></table>

</Accordion>

<div id="deep-link" />

<Accordion title="Liên kết sâu">

Chỉ dành cho tương tác lại, người dùng không được chuyển hướng đến cửa hàng ứng dụng để tải xuống ứng dụng. Do đó, thông tin trong URL có thể được kết nối trực tiếp với lượt nhấp (và lượt mở ứng dụng tiếp theo). Phương pháp phân bổ này được gọi là liên kết sâu, vì URL liên kết sâu mang thông tin được dùng để phân bổ tương tác lại.

</Accordion>

### Phương thức phân bổ cho mỗi nguồn truyền thông và tính năng AppsFlyer

Xem các phần tiếp theo để biết phân tích đầy đủ về các phương thức phân bổ cụ thể nào được hỗ trợ, tùy thuộc vào:

* Nguồn truyền thông: sở hữu hoặc trả phí
* Tính năng AppsFlyer được sử dụng
* Thiết bị của người dùng: Android hoặc iOS

<div id="owned-media" />

<Accordion title="Truyền thông Sở hữu">

<table><thead><tr><th rowspan="2">Nguồn truyền thông</th><th rowspan="2">Tính năng</th><th colspan="2">Phương thức phân bổ</th></tr><tr><th>Android</th><th>iOS</th></tr></thead><tbody><tr><td>Truyền thông sở hữu: email (bao gồm cả ESP), SMS, bài đăng trên mạng xã hội, người có tầm ảnh hưởng/đối tác liên kết, báo in, v.v.</td><td><a href="./onelink-guide" target="_blank"><span>OneLink</span></a></td><td><ul><li>Người giới thiệu cài đặt</li><li>Mô hình xác suất</li></ul></td><td><p>Mô hình xác suất</p></td></tr><tr><td rowspan="2">Trang web/trang đích dành cho thiết bị di động được sở hữu có lưu lượng truy cập đến được trả phí hoặc tự nhiên</td><td><a href="./smart-banners-mobile-web-to-app-for-marketers" target="_blank">Biểu ngữ Thông minh</a></td><td>Mô hình xác suất</td><td>Mô hình xác suất</td></tr><tr><td><a href="./onelink-smart-script-overview" target="_blank">Tập lệnh thông minh OneLink</a></td><td><ul><li>Người giới thiệu cài đặt</li><li>Mô hình xác suất</li></ul></td><td>Mô hình xác suất</td></tr><tr><td rowspan="2">Ứng dụng di động sở hữu</td><td><a href="./user-invite-attribution" target="_blank">Lời mời/giới thiệu của người dùng</a></td><td><p>Mô hình xác suất</p></td><td><p>Mô hình xác suất</p></td></tr><tr><td><a href="./cross-promotion-attribution-for-marketers" target="_blank">Quảng cáo chéo</a></td><td>Khớp ID thiết bị</td><td>Khớp ID thiết bị</td></tr></tbody></table>

</Accordion>

<div id="paid-media" />

<Accordion title="Truyền thông trả phí">

<table><thead><tr><th rowspan="2">Nguồn truyền thông</th><th colspan="3">Phương thức phân bổ</th></tr><tr><th>Android</th><th>iOS</th><th><strong>Nền tảng CTV, PC và bảng điều khiển</strong></th></tr></thead><tbody><tr><td><a href="./self-reporting-networks-srns" target="_blank">SRN</a></td><td><p>Khớp ID thiết bị</p></td><td><ul><li>Khớp ID thiết bị</li><li>AAP (iOS 14.5+)</li><li>SKAdNetwork (iOS 14+)</li></ul></td><td><p>Khớp ID thiết bị</p></td></tr><tr><td><ul><li>Mạng quảng cáo (không phải SRN) thông qua <a href="./set-up-an-integrated-partner#attribution-link-tab" target="_blank">đường dẫn phân bổ cho đối tác</a> </li><li><span>Nền tảng CTV, PC và bảng điều khiển</span></li></ul></td><td><ul><li>Người giới thiệu cài đặt</li><li>Khớp ID thiết bị</li><li>Mô hình xác suất</li></ul></td><td><ul><li>Khớp ID thiết bị</li><li>Mô hình xác suất (trước iOS 14.5)</li><li>AAP (iOS 14.5+)</li><li>SKAdNetwork (iOS 14+)</li></ul></td><td> </td></tr><tr><td><p><a href="./appsflyer-factory-preinstall-using-manifest-android" target="_blank">Được cài đặt sẵn trên thiết bị</a></p></td><td>Trước khi cài đặt</td><td>--</td><td> </td></tr></tbody></table>

</Accordion>

## Loại phân bổ lượt tương tác người dùng

Phân bổ được thực hiện dựa trên thu hút lượt nhấp qua và xem hết. Phân bổ nguồn truyền thông đạt được bằng cách sử dụng các kỹ thuật mô hình xác suất và so khớp ID thiết bị.

<div id="clickthrough-attribution" />

<Accordion title="Phân bổ lượt nhấp qua">

Hầu hết các lượt cài đặt là kết quả của việc người dùng nhấp vào quảng cáo, như biểu ngữ, video và quảng cáo xen kẽ.

Khi nhấp vào quảng cáo, khung thời gian xem lại lượt nhấp sẽ mở ra với thời gian mặc định là 7 ngày. Lượt cài đặt xảy ra trong khung thời gian xem lại là không tự nhiên và được phân bổ cho nguồn truyền thông. Lượt cài đặt diễn ra ngoài khung thời gian xem lại được coi là lượt cài đặt tự nhiên. Thường được gọi là phân bổ tự nhiên.

* Khung thời gian xem lại lượt nhấp bảy ngày được coi là tiêu chuẩn của ngành. Đặt khoảng khung thời gian phù hợp với thỏa thuận của bạn với nguồn truyền thông.
* Căn chỉnh các khung thời gian xem lại SRN với thời gian do SRN xác định.

<table><thead><tr><th rowspan="2"><p><strong>Loại ghi công</strong></p></th><th rowspan="2"><p><strong>Phương thức phân bổ</strong></p></th><th rowspan="2"><p>Phạm vi</p></th><th rowspan="2">Mặc định</th></tr></thead><tbody><tr><td rowspan="2"><p>Lượt nhấp</p><p>(Tất cả đối tác tích hợp)</p></td><td><p>Referrer, Khớp ID</p></td><td><p>1 – 30 ngày</p></td><td><p>7 ngày</p></td></tr><tr><td><p>Mô hình xác suất</p></td><td><p>0–24 giờ</p></td><td><ul><li>Thích ứng</li><li>Do AppsFlyer xác định</li></ul></td></tr></tbody></table>

<Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows">Tìm hiểu thêm về khung thời gian xem lại</Anchor>

</Accordion>

<div id="viewthrough-attribution" />

<Accordion title="Phân bổ lượt xem qua (View-through Attribution)">

Có thể phân bổ những người dùng xem quảng cáo, nhưng không nhấp vào quảng cáo, cho mạng quảng cáo phân phát quảng cáo.

Khung thời gian xem lại cho phân bổ lượt xem hết:

* ngắn hơn so với khung thời gian xem lại của phân bổ lượt nhấp qua
* có thể cấu hình được.

Để bật phân bổ lượt xem hết, hãy đặt khoảng thời gian xem lại trong cửa sổ cấu hình.

Điều này đặc biệt hữu ích đối với các mạng quảng cáo video vốn có mức CTR thấp trên các quảng cáo video của mình, nhưng đồng thời cũng hữu ích với các mạng quảng cáo video phát các quảng cáo thông thường.

<table><thead><tr><th><strong>Loại ghi công</strong></th><th><p><strong>Phương thức phân bổ</strong></p></th><th><p><strong>Phạm vi</strong></p></th><th><p><strong>Mặc định<br/></strong></p></th></tr></thead><tbody><tr><td rowspan="2"><p>Lượt xem qua</p><p>(<a href="./measure-view-through-engagements#view-vta-partner-list" target="_blank">Đối tác tích hợp đã chọn</a>)</p></td><td><p>Khớp ID</p></td><td><p>0-24 giờ</p></td><td><p>1 ngày</p></td></tr><tr><td><p>Mô hình xác suất</p></td><td><p>0-24 giờ</p></td><td><ul><li>Thích ứng</li><li>Do AppsFlyer xác định</li></ul></td></tr></tbody></table>

Trong trường hợp cả lượt nhấp và lượt hiển thị đều xảy ra, lượt nhấp luôn chiếm ưu thế bởi đó là tương tác chủ động.

<Anchor target="_blank" href="/marketers/vi/docs/measure-view-through-engagements">Tìm hiểu thêm về phân bổ lượt xem qua</Anchor>

</Accordion>

## Chủ đề phân bổ nâng cao

<div id="in-app-events" />

<Accordion title="Sự kiện trong ứng dụng">

AppsFlyer tạo một ID AppsFlyer duy nhất cho một lượt cài đặt ứng dụng liên kết với chi tiết phân bổ. Điều này cho phép ứng dụng **phân bổ sự kiện trong ứng dụng đến nguồn truyền thông gốc**. Các nhà quảng cáo có thể sử dụng thông tin này để theo dõi hành trình của người dùng trong dữ liệu thô của ứng dụng của họ.

Để biết thêm thông tin về phân bổ sự kiện, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview?query=in%20app%20event#how-does-appsflyer-attribute-events">đây</Anchor>.

</Accordion>

<div id="assisted-installs" />

<Accordion title="Lượt cài đặt được hỗ trợ (Assisted Installs)">

AppsFlyer ghi công hoàn toàn chỉ một nguồn truyền thông cho một lượt cài đặt, thường theo lượt nhấp quảng cáo gần nhất hoặc lượt hiển thị quảng cáo gần nhất (nếu không có lượt nhấp).

Lượt cài đặt được hỗ trợ (còn gọi là phân bổ đa tương tác) là các cài đặt trong đó nguồn truyền thông/chiến dịch không phải là người liên hệ cuối cùng nhưng đã tương tác với người dùng trước khi diễn ra cài đặt và tương tác trong khoảng thời gian xem lại phân bổ.

Các mạng hỗ trợ được hiển thị dưới dạng người đóng góp cài đặt trong AppsFlyer.

Để biết thêm thông tin chi tiết, nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/measure-assisted-installs">đây</Anchor>.

</Accordion>

<div id="reinstalls" />

<Accordion title="Lượt cài đặt lại">

Lượt cài đặt lại phát sinh khi người dùng cài đặt ứng dụng, gỡ cài đặt ứng dụng và sau đó cài đặt lại. Phân bổ lượt cài đặt lại được điều chỉnh bởi <Anchor target="_blank" href="/marketers/vi/docs/set-up-re-attribution-window">khung thời gian phân bổ lại</Anchor> như sau:

* Nếu lượt cài đặt lại xảy ra sau khi hết khung thời gian phân bổ lại: lượt cài đặt mới sẽ được ghi nhận.
* Nếu lượt cài đặt lại xảy ra trong khung thời gian phân bổ lại, thì một trong những trường hợp sau sẽ được áp dụng:
  * Nếu người dùng thu hút với chiến dịch nhắm mục tiêu lại trước khi cài đặt lại: <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide">lượt cài đặt lại nhắm mục tiêu lại</Anchor> (hay còn gọi là phân bổ lại) sẽ được ghi nhận.
  * Nếu người dùng không thu hút bằng một chiến dịch hoặc đã thu hút bằng một chiến dịch UA: không lượt cài đặt nào sẽ được ghi nhận. Tùy thuộc vào trạng thái <Anchor target="_blank" href="/marketers/vi/docs/measure-reinstalls#tổng-quan">**Phân bổ sự kiện hậu cài đặt lại**</Anchor>, các sự kiện trong ứng dụng của những người dùng cài đặt lại này sẽ được phân bổ về lượt cài đặt tự nhiên hoặc về lượt cài đặt gốc.

Khi thử nghiệm thiết bị và cài đặt nhiều lần, hãy <Anchor target="_blank" href="/marketers/vi/docs/registering-test-devices">đăng ký</Anchor> thiết bị với AppsFlyer. Nếu bạn không đăng ký thiết bị thì chỉ có lần cài đặt đầu tiên sẽ được ghi nhận.

Lưu ý rằng AppsFlyer mang lại độ chính xác cao hơn trong việc phân bổ lượt cài đặt lại iOS mà không cần ID nhà quảng cáo. Bạn có thể bật tính năng này trên trang <Anchor target="_blank" href="/marketers/vi/docs/app-settings#reinstall-detection-using-ondevice-storage-ios-only">App Settings</Anchor>.

#### Cài đặt lại các ứng dụng iOS được sao lưu trên iCloud

Khi một ứng dụng được sao lưu bằng iCloud và sau đó được khôi phục (trên cùng một thiết bị hoặc trên một thiết bị khác), AppsFlyer không tính đó là lượt cài đặt mới hay cài đặt lại. Người dùng khôi phục ứng dụng từ iCloud sẽ duy trì ID AppsFlyer và dữ liệu phân bổ.

</Accordion>

<div id="retargeting-attribution" />

<Accordion title="Phân bổ Nhắm lại mục tiêu (Retargeting Attribution)">

![Retargeting_-_Flow__2_.png](https://files.readme.io/64b8d9f5040daa281ae13f0855749ab4a88a2e7e8616d6ada37975899db92c80-31937591646097.png)

Người dùng cài đặt lại ứng dụng trong <Anchor target="_blank" href="/marketers/vi/docs/set-up-re-attribution-window">khung thời gian phân bổ lại</Anchor> (90 ngày theo mặc định) được coi là phân bổ lại. Nếu lượt cài đặt này xảy ra sau khi thu hút với chiến dịch nhắm mục tiêu lại, thì lượt đó sẽ được ghi nhận dưới dạng lượt cài đặt lại nhắm mục tiêu lại hay còn gọi là phân bổ lại và được báo cáo trong <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide">nhắm mục tiêu lại</Anchor>.

</Accordion>

<div id="app-updates" />

<Accordion title="Cập nhật ứng dụng">

* Khi người dùng hiện có cập nhật ứng dụng lên phiên bản tiếp theo, thì đây không được coi là sự kiện phân bổ có thể kiểm đếm, nếu người dùng đã được AppsFlyer phân bổ trước đó. Lưu ý! Nếu bạn di chuyển sang AppsFlyer từ một người dùng hiện có MMP khác trong lần mở ứng dụng lần đầu, thì sau khi di chuyển, sẽ được phân bổ là tự nhiên.
* Các số liệu liên quan đến số lượng người dùng trên mỗi phiên bản ứng dụng có sẵn trong <Anchor target="_blank" href="/marketers/vi/docs/sdk-information-version-consent-dashboard">bảng điều khiển Thông tin SDK.</Anchor>

</Accordion>

<div data-zendesk-anchors="what-is-attribution=ph%C3%A2n-b%E1%BB%95-l%C3%A0-g%C3%AC 01H8GG9XPSS8KA9CHPD6ECNR2J=ph%C3%A2n-b%E1%BB%95-l%C3%A0-g%C3%AC 01H8GG9XPSA15N5CSHGZNBWSAV=l%E1%BB%9Di-khuy%C3%AAn what-is-an-app-install=l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-%E1%BB%A9ng-d%E1%BB%A5ng-l%C3%A0-g%C3%AC 01EDRHGMTXK94Y97DPKFAMCJ5B=l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-%E1%BB%A9ng-d%E1%BB%A5ng-l%C3%A0-g%C3%AC attribution-methods=ph%C6%B0%C6%A1ng-th%E1%BB%A9c-ph%C3%A2n-b%E1%BB%95 01EDRHGMTXCRNVXS9JGHQ1JAQT=ph%C6%B0%C6%A1ng-th%E1%BB%A9c-ph%C3%A2n-b%E1%BB%95 01H8GG9XPS6P3CXX5AN2KY8WN4=install-referrer-android-only 01H8GG9XPSGVK90FV0K9HZARH7=device-id-matching 01H8GG9XPSQZPWJZ0BC0EAMB97=device-id-matching-using-idfv-ios 01H8GG9XPSV247F3JRCR870JK0=device-id-matching-for-selfreporting-networks 01EDRHGMTXHAKWZK99Q2X86BND=probabilistic-modeling note-for-ios-apps=l%C6%B0u-%C3%BD-%C4%91%E1%BB%91i-v%E1%BB%9Bi-%E1%BB%A9ng-d%E1%BB%A5ng-ios 01H8GG9XPSE1H8F9TCCXSZSW9W=l%C6%B0u-%C3%BD-%C4%91%E1%BB%91i-v%E1%BB%9Bi-%E1%BB%A9ng-d%E1%BB%A5ng-ios probabilistic-modeling-parameters-for-ad-networks=c%C3%A1c-th%C3%B4ng-s%E1%BB%91-t%E1%BA%A1o-m%C3%B4-h%C3%ACnh-x%C3%A1c-su%E1%BA%A5t-cho-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o h_01HEMSHXKGNW2DF41094BXY0FY=c%C3%A1c-th%C3%B4ng-s%E1%BB%91-t%E1%BA%A1o-m%C3%B4-h%C3%ACnh-x%C3%A1c-su%E1%BA%A5t-cho-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o 01H8GG9XPSZ5CPKNSCV7NF1MKW=preload-campaigns attribution-methods-per-media-source-and-appsflyer-feature=ph%C6%B0%C6%A1ng-th%E1%BB%A9c-ph%C3%A2n-b%E1%BB%95-cho-m%E1%BB%97i-ngu%E1%BB%93n-truy%E1%BB%81n-th%C3%B4ng-v%C3%A0-t%C3%ADnh-n%C4%83ng-appsflyer 01H8GG9XPTXDR41QANF4XVSZMM=ph%C6%B0%C6%A1ng-th%E1%BB%A9c-ph%C3%A2n-b%E1%BB%95-cho-m%E1%BB%97i-ngu%E1%BB%93n-truy%E1%BB%81n-th%C3%B4ng-v%C3%A0-t%C3%ADnh-n%C4%83ng-appsflyer 01H8GG9XPT65G88DE8548HZREE=owned-media 01H8GG9XPTADWMQ37WBB6P9WVS=paid-media user-engagement-attribution-types=lo%E1%BA%A1i-ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-t%C6%B0%C6%A1ng-t%C3%A1c-ng%C6%B0%E1%BB%9Di-d%C3%B9ng 01EDRHGMTX7851H14R20F9KNAN=lo%E1%BA%A1i-ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-t%C6%B0%C6%A1ng-t%C3%A1c-ng%C6%B0%E1%BB%9Di-d%C3%B9ng 01EDRHGMTXJ7WKTWQXFCHTD9AV=clickthrough-attribution 01EDRHGMTXN0Y0ZRVBX7HHW7NN=viewthrough-attribution advanced-attribution-topics=ch%E1%BB%A7-%C4%91%E1%BB%81-ph%C3%A2n-b%E1%BB%95-n%C3%A2ng-cao 01EDRHGMTYYXBSCDPKXCDK1641=ch%E1%BB%A7-%C4%91%E1%BB%81-ph%C3%A2n-b%E1%BB%95-n%C3%A2ng-cao 01EDRHGMTYMH3SVNBTQ28D4F42=in-app-events 01EDRHGMTY2CF0B70T3RAGPCJ1=reinstalls reinstalling-ios-apps-that-are-backed-up-in-icloud=c%C3%A0i-%C4%91%E1%BA%B7t-l%E1%BA%A1i-c%C3%A1c-%E1%BB%A9ng-d%E1%BB%A5ng-ios-%C4%91%C6%B0%E1%BB%A3c-sao-l%C6%B0u-tr%C3%AAn-icloud 01EDRHGMTYDSNJKQNPNYFXJPAZ=c%C3%A0i-%C4%91%E1%BA%B7t-l%E1%BA%A1i-c%C3%A1c-%E1%BB%A9ng-d%E1%BB%A5ng-ios-%C4%91%C6%B0%E1%BB%A3c-sao-l%C6%B0u-tr%C3%AAn-icloud 01EDRHGMTYYB9XVM5CBWSPJGMN=retargeting-attribution 01EDRHGMTYTQRMG1W7ZBW4G6W4=app-updates" />
