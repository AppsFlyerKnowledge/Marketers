---
title: Hướng dẫn bắt đầu nhanh &amp; Câu hỏi thường gặp về iOS 14, ATT và SKAN
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Agencies
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-08-11T09:19:23Z'
  edited_at: '2024-09-18T17:31:00Z'
  id: 360011890298
  locale: vi
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/vi/articles/360011890298
---
> **Sơ lược**: Bắt đầu từ iOS 14.5, Apple yêu cầu bạn triển khai và tuân thủ các điều khoản của <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency">AppTrackingTransparency</Anchor> (ATT). ATT có nghĩa là *Nếu ứng dụng của bạn thu thập dữ liệu về người dùng cuối và chia sẻ dữ liệu đó với các công ty khác nhằm mục đích theo dõi trên các ứng dụng và trang web,* bạn phải sử dụng lời nhắc chấp thuận ATT và nhận được sự đồng ý của người dùng trong cả ứng dụng dành cho nhà xuất bản và nhà quảng cáo. Nếu bạn không theo dõi thì không cần hiển thị lời nhắc.

![iOS14-consent-pre-ATT-enforcement-6522_Cover-image_917x480.jpg](https://files.readme.io/622b57cf6b6b7ad9472b3d072f44d9b451e82fec6b0c918427e39e9e6700602e-360019478118.jpg)

## Đo lường phân bổ trong môi trường ATT

AppsFlyer cung cấp cho bạn nhiều phương pháp phân bổ, cung cấp cho bạn một loạt các giải pháp phân bổ hoàn chỉnh. Yêu cầu chấp thuận [ATT](/docs/about-att-and-skan#att-principles) ảnh hưởng đến việc phân bổ trong bối cảnh chiến dịch ứng dụng đến ứng dụng phải trả phí. Do đó, các nhà quảng cáo cần sử dụng kết hợp các giải pháp phân bổ và báo cáo. 

Trong trường hợp chiến dịch từ ứng dụng đến ứng dụng phải trả phí, [SKAN](/docs/about-att-and-skan#skan-solution-principles) cung cấp kết quả phân bổ xác định. Các loại chiến dịch khác như phương tiện được sở hữu, mạng đến ứng dụng và Apple Search Ads sử dụng các công cụ phân bổ truyền thống của AppsFlyer. Các công cụ truyền thống cung cấp phép đo LTV dài hạn, trong khi SKAN đo lường hiệu suất của người dùng trong một bài đăng ngắn sau khi cài đặt. 

Tóm lại, để có được một bức tranh hoàn chỉnh, hãy sử dụng cả giải pháp truyền thống của SKAN và AppsFlyer vì chúng bổ sung cho nhau.

Bài viết này giới thiệu cho các nhà quảng cáo về SKAN và ATT. Bài viết dành cho các nhà quảng cáo quen thuộc với nền tảng AppsFlyer.

<div id="skan-solution-principles" />

<Accordion title="Nguyên tắc Giải pháp SKAN">

AppsFlyer cung cấp kết quả phân bổ hợp nhất trên thiết bị iOS bằng các postback SKAN từ thiết bị iOS. Các bài đăng lại này được iOS gửi đến các mạng quảng cáo, các mạng này chuyển tiếp chúng đến AppsFlyer. Các postback này chứa hồ sơ phân bổ ẩn danh được bổ sung giá trị chuyển đổi (CV) do nhà quảng cáo đặt. CV là thước đo lường chất lượng người dùng trong cửa sổ sau cài đặt ban đầu.

<Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide">Giải pháp SKAN</Anchor> của AppsFlyer cung cấp cho các nhà quảng cáo:

* Dữ liệu SKAN trong bảng điều khiển và báo cáo thu được bằng cách hợp nhất các bài đăng lại từ mọi mạng quảng cáo được bổ sung các điểm dữ liệu khác như chi phí.
* Khả năng kiểm soát thành phần mà CV đo lường, thông qua AppsFlyer Conversion Studio, mà không cần đổi mã ứng dụng. CV có thể được dùng để đo lường doanh thu, mức tương tác hoặc sự kiện chuyển đổi.

**Hạn chế của SKAN**

* **Chiến dịch:** Không hỗ trợ, Apple Search Ads, chiến dịch quảng cáo chéo và lượt cài đặt được hỗ trợ trên mạng di động.
* **Thời gian đo:** Thời gian đo hiệu quả được giới hạn trong một vài ngày.

**Quy trình SKAN**

![SKAN_flow_-_Affinity_diagram_2.png](https://files.readme.io/2e29f01cf9cf3689777bbd42044e42c0b9f1d4fb719ed75413d29dd84489686d-13112278947601.png)

1. Nhà quảng cáo thiết lập cài đặt đo lường SKAN trong AppsFlyer Conversion Studio.
2. Người dùng mở ứng dụng lần đầu.
3. Trong mỗi cửa sổ, AppsFlyer thiết lập CV dựa trên hành động của người dùng và lược đồ CV đã xác định.
4. Sau khi đóng cửa sổ, thiết bị iOS sẽ gửi bài đăng lại cho mạng quảng cáo và một bản sao đăng lại đến AppsFlyer. Bài đăng lại được gửi đến chậm:
   * Đối với khung thời gian đo lường 1 của SKAN 4: 24 - 48 giờ
   * Đối với khung thời gian đo lường 2-3 của SKAN 4: 24 - 144 giờ
   * Đối với SKAN 3: 24-48 giờ sau lần tăng giá trị CV gần đây nhất.
5. Các bản sao đăng lại gửi trực tiếp từ thiết bị iOS tới AppsFlyer được chuyển tiếp đến điểm cuối xác định của nhà quảng cáo. Xem <Anchor target="_blank" href="/marketers/vi/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">gửi bản sao đăng lại SKAN tới AppsFlyer.</Anchor>
6. Mạng quảng cáo chuyển tiếp postback bổ sung tới AppsFlyer hoặc SRN truyền dữ liệu postback bằng API.
7. AppsFlyer xác nhận và giải mã CV. Dữ liệu được giải mã được ghi lại và phân bổ trước khi được cung cấp trong AppsFlyer thông qua bảng điều khiển, báo cáo và API.

</Accordion>

<div id="att-principles" />

<Accordion title="Nguyên tắc ATT">

Lời nhắc ATT cung cấp cho nhà quảng cáo một cách để có được sự đồng ý rõ ràng của người dùng, cho phép nhà quảng cáo thu thập và chia sẻ dữ liệu của họ. Bắt đầu từ iOS 14.5, IDFA chỉ có sẵn nếu người dùng chấp thuận thông qua lời nhắc.

Cả ứng dụng dành cho nhà xuất bản và nhà quảng cáo đều hiển thị lời nhắc. Nếu người dùng chấp thuận trong cả hai ứng dụng, điều đó có nghĩa là người dùng đồng ý được *theo dõi* và các nhà quảng cáo được Apple cho phép theo dõi người dùng giữa các ứng dụng thuộc sở hữu của các công ty khác nhau.

**Cài đặt ATT**

ATT được đặt thành một trong các giá trị được liệt kê trong bảng tiếp theo. Ban đầu, iOS đặt ATT thành không xác định hoặc hạn chế.

Hãy xem xét việc sử dụng lời nhắc chấp thuận để chuyển đổi người dùng từ *không xác định* đến *được ủy quyền* là tùy chọn. Tuy nhiên, nếu bạn không hiển thị lời nhắc thì bạn không thể nhận được *ủy quyền.*

| Giá trị ATT | Đồng ý  <br />(IDFA có sẵn) | Lưu ý |
| --- | --- | --- |
| Hạn chế | Không | <ul><li>Được Apple xác định dựa trên độ tuổi của người dùng và các tiêu chí khác. Không thể được người dùng thiết bị thay đổi.</li><li>Không thể hiển thị lời nhắc cho những người dùng này.</li></ul> |
| Không xác định (cho đến iOS 14.4) | Có | Giá trị mặc định |
| Không xác định<br /><br />(bắt đầu từ iOS 14.5) | Không | Giá trị mặc định |
| Bị từ chối | Không | Xảy ra nếu bất kỳ điều nào sau đây là đúng:<ul><li>Đặt sau khi hiển thị lời nhắc</li><li>Người dùng đã tắt *Allow Apps to Request to Track* (Cho phép Ứng dụng Yêu cầu Theo dõi) (công tắc chính ở cấp thiết bị)</li><li>Trước khi cài đặt iOS 14 trên thiết bị, LAT đã bật</li></ul> |
| Được cấp quyền | Có | Đặt sau khi hiển thị lời nhắc |

**Ý nghĩa của ATT**

Do ATT, nhiều người dùng sẽ không chấp thuận, IDFA sẽ không có sẵn và không được phép theo dõi. Do đó, các nhà quảng cáo dựa vào báo cáo phân bổ cấp người dùng cho đến iOS 14.5 phải chuyển một số phân tích sang các phương pháp phân bổ và báo cáo tổng hợp. <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model">Mô hình phân bổ AppsFlyer</Anchor>.

Dữ liệu liên quan đến phân bổ cho một ứng dụng đến từ một số nguồn. Số định danh có sẵn và được sử dụng bởi mỗi khác nhau. Hầu hết dữ liệu hiển thị bằng các công cụ phân bổ truyền thống. Tuy nhiên, đối với các lượt cài đặt được phân bổ bằng SKAN, báo cáo sẽ được thực hiện thông qua bảng điều khiển SKAN.

</Accordion>

<div id="which-dashboard-has-the-install" />

<Accordion title="Bảng điều khiển nào có lượt cài đặt?">

Trong iOS 14, lượt cài đặt có thể được phân bổ cho cả bảng điều khiển truyền thống và bảng điều khiển SKAN. Ngoài ra, tùy thuộc vào bối cảnh nguồn truyền thông, lượt cài đặt có thể được phân bổ là tự nhiên trong một bảng điều khiển và không tự nhiên trong bảng điều khiển khác.

</Accordion>

## Kiến thức quan trọng về iOS 14

#### Các bài viết và liên kết về iOS 14 và SKAN

| Khu vực | Bài viết | Mối quan tâm đặc biệt: Câu hỏi thường gặp, sự khác biệt, so sánh |
| --- | --- | --- |
| SKAN | <Anchor target="_blank" href="/marketers/vi/docs/skan-raw-data-reports">Trường dữ liệu thô SKAN</Anchor> | Các trường SKAN dữ liệu thô bổ sung hỗ trợ did\_win và SKAN 3.0 |
| SKAN | <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide">Giải pháp SKAN</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">Thời gian từ khi cài đặt ứng dụng đến khi cập nhật bảng điều khiển</Anchor></li><li><Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide#organic-metrics-in-the-context-of-skadnetwork">Các chỉ số tự nhiên trong ngữ cảnh của SKAN</Anchor></li><li><Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#appsflyer-attribution-vs-skan-attribution">Phân bổ AppsFlyer so với phân bổ SKAN</Anchor></li><li><Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#faq-skan-discrepancies">Câu hỏi thường gặp về sự khác biệt của SKAN</Anchor></li></ul> |
| SKAN | <Anchor target="_blank" href="/marketers/vi/docs/skan-interoperation">Khả năng tương tác của đối tác SKAN</Anchor> (phần bài viết) | <Anchor target="_blank" href="/marketers/vi/docs/skan-integrated-partners-list">Danh sách đối tác tích hợp SKAN</Anchor> |
| SKAN | <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-interoperation-with-meta-ads">Tích hợp Meta ads và SKAN của AppsFlyer</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-interoperation-with-meta-ads#troubleshooting-discrepancies-and-faq">Khắc phục sự cố và sự khác biệt</Anchor></li><li><Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-interoperation-with-meta-ads#measurement-and-timing-differences-between-appsflyer-and-facebook">Sự khác biệt về đo lường và thời gian</Anchor></li></ul> |
| SKAN | <Anchor target="_blank" href="/marketers/vi/docs/skan-interoperation-with-snapchat">Tương tác giữa Snapchat và SKAN của AppsFlyer</Anchor> | <Anchor target="_blank" href="/marketers/vi/docs/skan-interoperation-with-snapchat#discrepancies-guide">Hướng dẫn về sự khác biệt</Anchor> |
| Quyền riêng tư | <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">Quyền riêng tư Nâng cao Hợp nhất (AAP)</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework#các-tính-năng-bị-ảnh-hưởng-bởi-aap">Các tính năng bị ảnh hưởng bởi AAP</Anchor></li><li><Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework#aap-central-switch">Tắt và bật AAP</Anchor></li></ul> |
| Quyền riêng tư | <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions">Nguồn truyền thông bị hạn chế</Anchor> | <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields">Trường dữ liệu thô bị hạn chế</Anchor> |
| iOS 14 | <Anchor target="_blank" href="/marketers/vi/docs/preparing-for-the-app-store-review-nutrition-labels">Nhãn dinh dưỡng — chuẩn bị cho việc duyệt xét trên App Store</Anchor> |  |
| iOS 14 | <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">Cấu hình ATT trong ứng dụng</Anchor> (Nhà phát triển hướng dẫn SDK) |  |
| iOS 14 | <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns">Giới thiệu về mạng tự báo cáo (SRN) như Google, Meta ads, v.v</Anchor> | <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns#ios-145-srn-attribution">Các lượt cài đặt SRN được báo cáo ở đâu?</Anchor> |
| Thanh toán | <Anchor target="_blank" href="https://content.appsflyer.com/ios-14-hub/billing/">Thanh toán cho ứng dụng iOS</Anchor> |  |

<div id="ios-14-impact-on-attribution-and-measurement" />

<Accordion title="Tác động của iOS 14 đối với phân bổ và đo lường">

#### **Số liệu**

Xem xét rằng do ATT, các chỉ số liên quan đến người dùng không chấp thuận ATT có thể bị ảnh hưởng như sau:

| Số liệu | Tăng | Giảm | Lưu ý |
| --- | --- | --- | --- |
| Không tự nhiên so với tự nhiên | Tự nhiên | Không tự nhiên |  |
| Lượt cài đặt lại so với lượt cài đặt | Lượt cài đặt | Lượt cài đặt lại |  |
| Nhắm mục tiêu lại | Lượt cài đặt tự nhiên và sự kiện trong ứng dụng | Tương tác lại, Phân bổ lại |  |
| Apple Search Ads | -- | -- | Không thay đổi. Cả người dùng chấp thuận và không chấp thuận đều được phân bổ chính xác. |

#### **Liên kết Sâu**

Liên kết sâu bị trì hoãn sử dụng <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-legacy-apis#deferred-deep-linking">phương pháp kế thừa onConversionDataSuccess</Anchor> có thể không hoạt động đối với iOS 14.5+ vì nó yêu cầu dữ liệu phân bổ có thể không khả dụng do bảo vệ quyền riêng tư.

Chúng tôi khuyên bạn nên sử dụng <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl-1">liên kết sâu hợp nhất (UDL)</Anchor>. UDL tuân thủ các tiêu chuẩn bảo mật iOS 14.5+ và chỉ trả về các tham số liên quan đến liên kết sâu và liên kết sâu bị trì hoãn: `deep_link_value` và `deep_link_sub1`. Các thông số phân bổ như `media_source`, `campaign` và `af_sub1-5` trả về giá trị rỗng và không thể sử dụng cho mục đích liên kết sâu. <Anchor target="_blank" href="https://content.appsflyer.com/ios-14-hub/deep-linking-deferred-deep-linking/">Tìm hiểu thêm</Anchor>

</Accordion>

## Câu hỏi thường gặp—iOS 14+

<div id="what-happens-to-an-app-using-an-sdk-version-before-v6" />

<Accordion title="Điều gì xảy ra với một ứng dụng sử dụng phiên bản SDK trước V6+?">

Đối với các ứng dụng sử dụng phiên bản SDK cũ hơn V6.0:

* SKAdNetwork và Apple Search ads sẽ không hoạt động.
* Nếu bạn gửi ứng dụng đến App Store, hãy dự kiến rằng ứng dụng sẽ bị từ chối.

Đối với ứng dụng sử dụng SDK cũ hơn V6.10: SKAN 4 sẽ không hoạt động.

</Accordion>

<div id="is-it-mandatory-to-display-the-att-prompt" />

<Accordion title="Có bắt buộc phải hiển thị lời nhắc ATT không?">

Không. Bạn chỉ cần yêu cầu chấp thuận ATT nếu bạn muốn *theo dõi* một người dùng, thu thập IDFA hoặc làm cả hai.

</Accordion>

## CÂU HỎI THƯỜNG GẶP—SKAN

<div id="how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4" />

<Accordion title="Làm cách nào để biết khi nào tôi sẽ nhận được bài đăng lại và liệu chúng sẽ là SKAN 3 hay SKAN 4?">

Loại bài đăng lại SKAN bạn nhận được được xác định bởi nhiều yếu tố, bao gồm chế độ bạn sử dụng trong Conversion Studio, mạng quảng cáo bạn sử dụng và phiên bản iOS mà người dùng của bạn có.

Những yếu tố này tác động:

* Phiên bản đăng lại: SKAN 3 hoặc SKAN 4. <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide#principles-and-flow">Tìm hiểu thêm</Anchor>
* Khung thời gian 1 (AW): Đối với SKAN 4, đây là 48 giờ. Đối với SKAN 3, điều này dựa trên khung thời gian hoạt động. Lưu ý: Nếu Conversion Studio không phải là SKAN 4, nhưng chữ ký mạng quảng cáo là SKAN 4 thì khung thời gian sẽ dựa trên khung thời gian hoạt động hoặc 48 giờ, tùy theo khung nào thấp hơn.
* Độ trễ đăng lại: Vài giờ sau khi cài đặt khi có bài đăng lại SKAN. Điều này phụ thuộc vào thời điểm khung thời gian đóng lại. <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide?query=skan%20faq#timing-from-app-install-until-dashboard-and-reports-update">Tìm hiểu thêm</Anchor>
* Hẹn giờ lăn: Đối với SKAN 3, khung thời gian hoạt động có thể được kéo dài lên đến 63 ngày; bài đăng lại chỉ có sau khi khung thời gian đóng lại.

Lưu đồ sau đây giải thích điều này chi tiết hơn.

![SKAN_4_matrix_-_Page_8__1_.png](https://files.readme.io/0dbd4cae34d9f9fed80dbe835485789dab75d46dbb38de055f454d01efb97350-13756140934545.png)

</Accordion>

<div id="in-skan-am-i-limited-to-100-campaign-ids-per-ad-network" />

<Accordion title="Trong SKAN, tôi có bị giới hạn ở một số mã định danh nguồn/ID chiến dịch nhất định trên mỗi mạng quảng cáo không?">

Có. Trước đây, giới hạn là 100 ID chiến dịch. Tuy nhiên, từ SKAN 4, ID chiến dịch được gọi là mã định danh nguồn phân cấp và giới hạn là 10.000. Mã định danh nguồn là số nguyên gồm 4 chữ số.

Mạng quảng cáo ánh xạ mã định danh nguồn SKAN với ID chiến dịch của họ.

</Accordion>

<div id="what-is-the-use-case-for-skan-raw-data" />

<Accordion title="Trường hợp sử dụng cho dữ liệu thô SKAN là gì?">

* Sử dụng dữ liệu thô để tổng hợp các phương diện không có sẵn thông qua API tổng hợp.
* Dễ dàng điều chỉnh các quy trình nhập dữ liệu thô hiện có để sử dụng dữ liệu thô SKAN.

</Accordion>

<div id="why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio" />

<Accordion title="Tại sao giá trị chuyển đổi tôi nhận được không khớp với cấu hình của tôi trong AppsFlyer Conversion Studio?">

Thông thường, điều này là do một SDK khác trong ứng dụng của bạn có khả năng đặt giá trị chuyển đổi và điều đó xung đột với SDK AppsFlyer của bạn cũng như các giá trị chuyển đổi bạn đã định cấu hình trong AppsFlyer. Đảm bảo bạn không có SDK khác đặt giá trị chuyển đổi được tích hợp vào ứng dụng của mình.

</Accordion>

<div id="why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports" />

<Accordion title="Tại sao dữ liệu tổng hợp trong bảng điều khiển SKAN của tôi không khớp với số dữ liệu thô trong báo cáo SKAN Data Locker của tôi?">

Thông thường, sự khác biệt này là do xem báo cáo Data Locker không đúng chỗ. Dữ liệu từ Google có thể mất tối đa 13 ngày để nhận được. Và trong các báo cáo dữ liệu thô, dữ liệu được ghi vào ngày nhận được, không phải tích lũy. Do đó, để có được số liệu chính xác cho các lượt cài đặt liên quan đến một ngày cụ thể, bạn cũng cần xem tất cả các báo cáo sau 13 ngày kể từ ngày đó.

Ví dụ: Trong báo cáo ngày 12 tháng 6, báo cáo hiển thị 100 lượt cài đặt từ Google xảy ra vào ngày 11 tháng 6. Trong báo cáo ngày 24 tháng 6, báo cáo cho biết có THÊM 100 lượt cài đặt đã xảy ra vào ngày 11 tháng 6. Bạn sẽ cần xem tất cả các báo cáo trong 13 ngày qua (từ ngày 12 tháng 6 đến ngày 24 tháng 6) và tổng hợp dựa trên thời gian cài đặt hoặc dấu thời gian mạng quảng cáo để đọc chính xác tổng số 200 lượt cài đặt đã xảy ra vào ngày 11 tháng 6.

</Accordion>

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/getting-started-onboarding-for-marketers#bước-3-thiết-lập-phân-bổ">AppsFlyer bắt đầu từng bước</Anchor>

<div data-zendesk-anchors="attribution-measurement-in-an-att-environment=%C4%91o-l%C6%B0%E1%BB%9Dng-ph%C3%A2n-b%E1%BB%95-trong-m%C3%B4i-tr%C6%B0%E1%BB%9Dng-att h_01HE0C8YXSXSX003X0671Z97KZ=%C4%91o-l%C6%B0%E1%BB%9Dng-ph%C3%A2n-b%E1%BB%95-trong-m%C3%B4i-tr%C6%B0%E1%BB%9Dng-att h_01HE0C8YXSCA8M57F1RG4CJ7HK=skan-solution-principles h_01HE0C8YXSSCTQJAPDE27FB1H8=att-principles h_01HE0C8YXS0BFA2M16D1Q2PQYW=which-dashboard-has-the-install ios-14-important-knowledge=ki%E1%BA%BFn-th%E1%BB%A9c-quan-tr%E1%BB%8Dng-v%E1%BB%81-ios-14 h_01HE0C8YXS3BH109DF1Y1KNK5P=ki%E1%BA%BFn-th%E1%BB%A9c-quan-tr%E1%BB%8Dng-v%E1%BB%81-ios-14 ios-14-and-skan-articles-and-links=c%C3%A1c-b%C3%A0i-vi%E1%BA%BFt-v%C3%A0-li%C3%AAn-k%E1%BA%BFt-v%E1%BB%81-ios-14-v%C3%A0-skan h_01HE0C8YXSPZKBWXC51Z2636R0=c%C3%A1c-b%C3%A0i-vi%E1%BA%BFt-v%C3%A0-li%C3%AAn-k%E1%BA%BFt-v%E1%BB%81-ios-14-v%C3%A0-skan h_01HE0C8YXSTCVA8YYR4BQVHVXS=ios-14-impact-on-attribution-and-measurement metrics=s%E1%BB%91-li%E1%BB%87u h_01HE0C8YXSJMYN81FKPCA8ATK7=s%E1%BB%91-li%E1%BB%87u deep-linking=li%C3%AAn-k%E1%BA%BFt-s%C3%A2u h_01HE0C8YXS6ADG1SQCMVP0W69B=li%C3%AAn-k%E1%BA%BFt-s%C3%A2u faq%E2%80%94ios-14=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7pios-14 h_01HE0C8YXSV9VSK1NPG9RCTQW1=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7pios-14 h_01HE0C8YXS1FFYQJ8YZXP9W9ZV=what-happens-to-an-app-using-an-sdk-version-before-v6 h_01HE0C8YXSKA0325YJSXV81ZB9=is-it-mandatory-to-display-the-att-prompt faq%E2%80%94skan=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7pskan h_01HE0C8YXSQKH8ER1Q5VS6Z0NM=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7pskan how-do-i-know-when-i%E2%80%99ll-receive-postbacks-and-if-they%E2%80%99ll-be-skan-3-or-skan-4=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXS44YXAN2DV2ZR03GE=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXSCWM892QH0N7YQ8HP=in-skan-am-i-limited-to-100-campaign-ids-per-ad-network h_01HE0C8YXSSWHV45M6P7SQGCRD=what-is-the-use-case-for-skan-raw-data h_01HE0C8YXS8GJKFC23S1R9TWW0=why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio why-doesn%E2%80%99t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE0C8YXS1VW1T50ARJE0MP62=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE7SNR02VQDKG55QP06ECNAR=xem-th%C3%AAm" />
