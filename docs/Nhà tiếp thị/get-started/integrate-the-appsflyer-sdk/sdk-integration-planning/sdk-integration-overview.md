---
title: Tổng quan về tích hợp SDK
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Integration
    - Advertisers
    - firetv
    - fire tv
    - Advertiser
    - Developer
    - appuid
    - anonymous
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2012-12-26T14:34:58Z'
  edited_at: '2023-11-17T02:24:05Z'
  id: 207032126
  locale: vi
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/vi/articles/207032126
---
> **Khái quát:** Tìm hiểu về các chức năng SDK AppsFlyer hiện có và xác định API nào bạn muốn sử dụng với ứng dụng Android hoặc iOS của mình.

Xem video này để có được bức tranh tổng thể về tích hợp SDK.

<Embed title="Tổng quan về tích hợp SDK" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/4iybquc6q3" providerUrl="https://fast.wistia.com" />

## Giới thiệu về SDK

SDK cung cấp chức năng cài đặt ứng dụng và ghi nhận sự kiện. Bạn có thể ghi nhận số lượt cài đặt, phiên và sự kiện trong ứng dụng. Các sự kiện trong ứng dụng bao gồm, ví dụ, mua hàng trong ứng dụng hoặc lên cấp trong trò chơi. Việc ghi nhận những sự kiện này có thể giúp bạn đánh giá ROI và chất lượng người dùng. 

Bài viết này mô tả quy trình tích hợp SDK V6+ và giúp người quản lý sản phẩm của nhà quảng cáo (chủ sở hữu ứng dụng) lập kế hoạch tích hợp SDK của AppsFlyer với ứng dụng Android hoặc iOS của họ.

Tài liệu bổ sung bao gồm những phần sau:

<Tabs>
<Tab title="Gốc Android">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk">Tài liệu cài đặt SDK dành cho nhà phát triển</Anchor>
* <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-android-sdk-release-notes">Ghi chú phát hành</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference">Tài liệu tham khảo SDK dành cho nhà phát triển</Anchor>
* <Anchor target="_blank" href="/marketers/vi/docs/fill-out-google-safety-section-form">Phần an toàn dữ liệu trên Google Play</Anchor>

</Tab>

<Tab title="Gốc iOS">

* <Anchor target="_blank" href="/marketers/vi/docs/updating-to-ios-sdk-v6-and-plugins">Cập nhật lên SDK iOS V6</Anchor>. Lưu ý rằng SDK iOS V5.4.4 tương thích hoàn toàn với iOS 14. Tuy nhiên, chúng tôi đề nghị bạn nên sử dụng SDK V6.X để đảm bảo khả năng tương thích với các bản phát hành iOS trong tương lai.
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">Tài liệu cài đặt SDK dành cho nhà phát triển</Anchor>
* <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes">Ghi chú phát hành</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference">Tài liệu tham khảo SDK dành cho nhà phát triển</Anchor>
* <Anchor target="_blank" href="/marketers/vi/docs/preparing-for-the-app-store-review-nutrition-labels">Chuẩn bị cho việc duyệt xét trên App Store—nhãn dinh dưỡng</Anchor>

</Tab>

<Tab title="Gốc Unity">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">Tài liệu cài đặt SDK dành cho nhà phát triển</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api">Tài liệu tham khảo SDK dành cho nhà phát triển</Anchor>

</Tab>

<Tab title="React">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">Tài liệu cài đặt SDK dành cho nhà phát triển</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api">Tài liệu tham khảo SDK dành cho nhà phát triển</Anchor>

</Tab>
</Tabs>

## Khả năng tương thích của SDK

SDK của AppsFlyer tương thích với các nền tảng sau:

<Tabs>
<Tab title="Android">

* Khởi động Android V4.0
* Các nền tảng dựa trên Android dành cho các thiết bị không phải di động như TV Thông minh (bao gồm cả Fire TV của Amazon). <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts">Xem phần tổng quan về CTV</Anchor>
* <Anchor target="_blank" href="/marketers/vi/docs/set-up-multi-store-android-attribution">Chợ ứng dụng ngoài cửa hàng</Anchor> dành cho các ứng dụng Android, chẳng hạn như Amazon và Baidu

</Tab>

<Tab title="iOS">

* iOS 9+ (iPhone, iPod, iPad)
* tvOS 9+ (Apple TV)
* Phù hợp với mạng <Anchor target="_blank" href="https://developer.apple.com/library/content/documentation/NetworkingInternetWeb/Conceptual/NetworkingOverview/UnderstandingandPreparingfortheIPv6Transition/UnderstandingandPreparingfortheIPv6Transition.html#//apple_ref/doc/uid/TP40010220-CH213-SW1">IPv6 DNS64/NAT64</Anchor> của Apple

SDK hỗ trợ <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model">nhiều phương thức phân bổ</Anchor>. Các phương thức phân bổ được sử dụng dựa trên những điều sau:

* Phiên bản iOS được cài đặt trên thiết bị của người dùng
* Phiên bản SDK iOS được cài đặt trong ứng dụng

<table><thead><tr><th><span>Phương thức phân bổ được hỗ trợ</span></th><th><span>Phiên bản iOS</span></th><th><span>Hỗ trợ SDK iOS</span></th><th><span>Lưu ý</span></th></tr></thead><tbody><tr><td rowspan="2"><span>Mô hình xác suất</span></td><td><p><span>8 – 14.4</span></p></td><td>5.0.0+</td><td> </td></tr><tr><td><p><span>14.5+</span></p></td><td><span> 6.0.3+</span></td><td><span>Mô hình xác suất được giới hạn trong trường hợp đối với truyền thông sở hữu, quảng cáo chéo và các luồng chuyển đổi web sang ứng dụng đã có sự đồng ý.</span></td></tr><tr><td rowspan="2"> <span>Khớp ID</span><br/><span><br/></span> </td><td><span>8 - 13</span></td><td>5.0.0+</td><td><span>Người dùng có thể chọn không tham gia bằng cách sử dụng tính năng Giới hạn theo dõi quảng cáo (LAT).</span></td></tr><tr><td><span>14.5+</span></td><td><span>6.0.3+</span></td><td><p>Yêu cầu Minh bạch về Theo dõi Ứng dụng (ATT) và sự đồng ý của người dùng. Để biết thêm thông tin, hãy xem phần <a href="./basic-sdk-integration-guide#configure-app-tracking-transparency-att-support" target="_blank">định cấu hình SDK iOS để hỗ trợ ATT</a>.</p></td></tr><tr><td rowspan="2"><p><a href="./skadnetwork-skan-solution-guide" target="_blank"><span>SKAdNetwork</span></a></p></td><td><p><span>11.3 - 13</span></p></td><td rowspan="2"><p><span>6.2.3</span><br/><span><br/></span></p></td><td><p>Giải pháp SKAdNetwork (SKAN) được <span>giới hạn chỉ phân bổ lượt cài đặt theo đặc điểm kỹ thuật của </span><a href="https://developer.apple.com/documentation/storekit/skadnetwork" target="_blank">SKAN</a><span>, có nghĩa là không có giá trị chuyển đổi.</span></p></td></tr><tr><td><p><span>14+</span></p></td><td><ul><li>Luôn có sẵn SKAN ở cấp iOS và SDK bất kể chế độ cài đặt ATT là gì.</li><li>Nhà tiếp thị kích hoạt SKAN trong bảng điều khiển của AppsFlyer.</li></ul></td></tr></tbody></table>

Kể từ SDK V6.0.8, <Anchor target="_blank" href="/marketers/vi/docs/apple-app-clips-integration-guide">Tính năng phân bổ Apple App Clips</Anchor> sẽ được cung cấp. Bạn cũng có thể đọc <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/apple-app-clips">bài đăng trên blog</Anchor> của chúng tôi về Apple App Clips.

</Tab>
</Tabs>

## Tích hợp SDK

Quy trình cài đặt và tích hợp SDK yêu cầu người quản lý sản phẩm và nhà phát triển thiết bị di động phải làm việc cùng nhau.  **Trước khi** tích hợp SDK với ứng dụng của bạn, hãy xem lại tất cả các tác vụ tích hợp và xem xét các chức năng mà bạn muốn có trong ứng dụng của mình.

### Danh sách kiểm tra hoạt động lập kế hoạch SDK

Để giúp bạn bắt đầu, chúng tôi đã soạn lập một <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTD4OimHC93iw2AJCcAY45yAc9lOBfJe8PskI_0NFZTnWnrIq1hjPBvCztkbom9acMDDd4d1d5mMFfi/pub?output=xlsx">danh sách kiểm tra</Anchor> để hướng dẫn bạn trong quá trình lập kế hoạch. Đối với mỗi tác vụ, có các liên kết đến tài liệu dành cho nhà tiếp thị và nhà phát triển.

### Các tác vụ tích hợp SDK

Tích hợp SDK cơ bản bao gồm các tác vụ sau. Ước tính thời gian chỉ nhằm mục đích hướng dẫn chung.

| Các tác vụ tích hợp SDK cơ bản | Thời gian lập kế hoạch |
| --- | --- |
| Truy xuất <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide#truy-xuất-dev-key">dev key của AppsFlyer</Anchor> và gửi đường dẫn liên kết kèm hướng dẫn cài đặt và tích hợp cho đội ngũ phát triển ứng dụng của bạn. | 15 phút |
| Xem lại <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide#phân-bổ">những điều cần lưu ý về phân bổ</Anchor> và xác định mã định danh thiết bị nào cần thu thập. | 30 phút |
| Xác định <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide#ghi-nhận-sự-kiện-trong-ứng-dụng">các sự kiện trong ứng dụng</Anchor> mà bạn muốn đo lường và gửi tên sự kiện và thông số sự kiện cho nhà phát triển. | 1 giờ |
| Xác định <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide#liên-kết-sâu-với-onelink">các phương thức liên kết sâu</Anchor> cần sử dụng. | 30 phút |
| Xác định các phương thức <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide#truy-cập-dữ-liệu-phân-bổ-và-liên-kết-sâu">truy cập dữ liệu phân bổ</Anchor>. | 30 phút |
| Khi quá trình tích hợp cơ bản hoàn tất, bất kỳ người dùng tài khoản nào có quyền truy cập vào bảng điều khiển của AppsFlyer đều có thể thực hiện <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide#kiểm-tra-tích-hợp-sdk">thử nghiệm cơ bản</Anchor>.<br /><br />Nhà phát triển có thể sử dụng nhật ký gỡ lỗi trong <Anchor target="_blank" href="/marketers/vi/docs/testing-the-sdk-integration-for-marketers#thử-nghiệm-trong-môi-trường-phát-triển">môi trường phát triển</Anchor>. | 1 giờ |

Bạn có thể làm việc với đội ngũ phát triển ứng dụng thiết bị di động của mình để triển khai các API bổ sung này trong SDK.

| Các tác vụ tích hợp SDK bổ sung | Thời gian lập kế hoạch |
| --- | --- |
| Xác định xem ứng dụng của bạn có yêu cầu thiết lập <Anchor target="_blank" href="/marketers/vi/docs/additional-sdk-integration-guide#các-phương-thức-phân-bổ-bổ-sung">phân bổ bổ sung</Anchor> hay không (ví dụ: đo lường lượt gỡ cài đặt hoặc phân bổ lượt cài đặt cho các cửa hàng ứng dụng của bên thứ ba). | 30 phút |
| Xác định <Anchor target="_blank" href="/marketers/vi/docs/additional-sdk-integration-guide#các-phiên">báo cáo phiên của người dùng</Anchor>. | 30 phút |
| Xác định các phương thức phân bổ để sử dụng cho <Anchor target="_blank" href="/marketers/vi/docs/additional-sdk-integration-guide#truyền-thông-sở-hữu">các nguồn truyền thông sở hữu</Anchor>. | 1 giờ |
| Quản lý các chính sách <Anchor target="_blank" href="/marketers/vi/docs/additional-sdk-integration-guide#quyền-riêng-tư-của-người-dùng">quyền riêng tư của người dùng</Anchor> để đảm bảo ứng dụng của bạn tuân thủ các quy định về quyền riêng tư (GDPR, CCPA). | 1 giờ |

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts">Tổng quan về nền tảng CTV, PC và console</Anchor>

<div data-zendesk-anchors="about-the-sdk=gi%E1%BB%9Bi-thi%E1%BB%87u-v%E1%BB%81-sdk h_01H9FHRVKE6BHGW05G6YMKF737=gi%E1%BB%9Bi-thi%E1%BB%87u-v%E1%BB%81-sdk sdk-compatibility=kh%E1%BA%A3-n%C4%83ng-t%C6%B0%C6%A1ng-th%C3%ADch-c%E1%BB%A7a-sdk h_01H9FHRVKEQ837Q0GFECNPPAN2=kh%E1%BA%A3-n%C4%83ng-t%C6%B0%C6%A1ng-th%C3%ADch-c%E1%BB%A7a-sdk sdk-integration=t%C3%ADch-h%E1%BB%A3p-sdk h_01H9FHRVKEN0MMGTSD362FTWPS=t%C3%ADch-h%E1%BB%A3p-sdk sdk-planning-checklist=danh-s%C3%A1ch-ki%E1%BB%83m-tra-ho%E1%BA%A1t-%C4%91%E1%BB%99ng-l%E1%BA%ADp-k%E1%BA%BF-ho%E1%BA%A1ch-sdk h_01H9FHRVKE468M1RTMF7VTYV1R=danh-s%C3%A1ch-ki%E1%BB%83m-tra-ho%E1%BA%A1t-%C4%91%E1%BB%99ng-l%E1%BA%ADp-k%E1%BA%BF-ho%E1%BA%A1ch-sdk sdk-integration-tasks=c%C3%A1c-t%C3%A1c-v%E1%BB%A5-t%C3%ADch-h%E1%BB%A3p-sdk h_01H9FHRVKERHXY19R97EN86EGP=c%C3%A1c-t%C3%A1c-v%E1%BB%A5-t%C3%ADch-h%E1%BB%A3p-sdk h_01H9FHRVKE88CXGH8G7E26ZXT2=xem-th%C3%AAm" />
