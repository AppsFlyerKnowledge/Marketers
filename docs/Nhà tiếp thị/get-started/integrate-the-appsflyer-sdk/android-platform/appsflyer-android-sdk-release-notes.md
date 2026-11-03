---
title: Ghi chú phát hành AppsFlyer SDK cho Android
metadata:
  keywords:
    - Advertisers
    - Release Notes
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2017-03-09T20:17:19Z'
  edited_at: '2024-07-03T07:56:19Z'
  id: 115001256006
  locale: vi
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/vi/articles/115001256006
---
> Sơ lược: Hãy xem ghi chú phát hành SDK để biết tổng quan nhanh về những thay đổi mới nhất đối với SDK Android. Các nhà phát triển đang tìm kiếm thông tin chi tiết toàn diện hơn nên xem lại <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-release-notes">Ghi chú phát hành Android trên Dev Hub</Anchor>.

## SDK Android V6

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk">Hướng dẫn tích hợp SDK Android dành cho nhà phát triển</Anchor>

| Phiên bản | Ngày phát hành | Lưu ý |
| --- | --- | --- |
| 6.14.2 | 2024-06-10 | <ul><li>Đã khắc phục sự cố khi tìm nạp Meta Install Referencerer trên các ứng dụng được xây dựng bằng Unity.</li></ul> |
| 6.14.1 | 2024-05-29 | Bảo trì SDK |
| 6.14.0 | 2024-04-18 | <ul><li>Đã thêm hỗ trợ cho luồng Xác thực mua hàng được cập nhật. Tính năng này hiện đang ở giai đoạn thử nghiệm kín. Tìm hiểu thêm.</li><li>Đã cập nhật tích hợp Người giới thiệu Huawei. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#huawei-install-referrer">Tìm hiểu thêm</Anchor>.</li></ul> |
| 6.13.1 | 2024-04-03 | Bảo trì SDK |
| 6.13.0 | 2024-02-08 | <ul><li>Đã thêm hỗ trợ cho Chính sách về sự đồng ý ở Liên minh Châu Âu (DMA) mới của Google</li></ul> |
| 6.12.6 | 2024-01-29 | Bảo trì SDK |
| 6.12.5 | 2023-12-18 | <ul><li>Đã thêm `original_link` tham số cho lệnh gọi lại liên kết sâu trong quy trình phân giải ESP.</li></ul> |
| 6.12.4 | 25-10-2023 | <ul><li>Dexguard đã cập nhật lên phiên bản 9.4.16 để cải thiện tính ổn định của SDK.</li></ul> |
| 6.12.3 | Ngày 31 tháng 08 năm 2023 | Bảo trì SDK |
| 6.12.2 | 02-08-2023 | <ul><li>Đã sửa lỗi có thể khiến ứng dụng bị sự cố trên một số thiết bị chạy Android 8.1.0 và Android 11.</li></ul> |
| 6.12.1 | 29-06-2023 | <ul><li>Đã khắc phục sự cố khiến quá trình khởi chạy của Cửa hàng Play bị trì hoãn trong quảng cáo chéo.</li><li>Đã khắc phục lỗi khiến ứng dụng bị văng trên một số thiết bị.</li></ul> |
| 6.12.0 | Ngày 28 tháng 06 năm 2023 | <ul><li>Ngưng hỗ trợ - vui lòng sử dụng phiên bản 6.12.1.</li></ul> |
| 6.11.2 | 29-06-2023 | <ul><li>Đã khắc phục lỗi khiến ứng dụng bị văng trên một số thiết bị.</li></ul> |
| 6.11.1 | 6-6-2023 | <ul><li>Ngưng hỗ trợ - vui lòng sử dụng phiên bản 6.12.1.</li><li>Đã khắc phục lỗi khiến ứng dụng đôi lúc bị văng sau khi khởi chạy SDK.</li></ul> |
| 6.11.0 | 16-5-2022 | <ul><li>Đã khắc phục sự cố đôi lúc khiến ứng dụng bị treo trên một số thiết bị khi SDK cố gắng lấy Liên kết giới thiệu Google Play</li></ul> |
| 6.10.3 | Ngày 25 tháng 04 năm 2023 | Bảo trì SDK |
| 6.10.1 | 1-3-2023 | <ul><li>Đã khắc phục sự cố đôi lúc khiến các ứng dụng trên thiết bị Samsung bị đóng khi khởi chạy SDK. Sự cố này ảnh hưởng đến các ứng dụng cài SDK V6.6.0 trở lên.</li></ul> |
| 6.10.0 | 13-02-2023 | <ul><li>Miền AppsFlyer mới cho giao tiếp giữa SDK và máy chủ AppsFlyer.</li><li>Đã thay đổi API setHost khi các giá trị trống hoặc null được gửi đi. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#sethost">Tìm hiểu thêm</Anchor></li></ul> |
| 6.9.4 | 06-12-2022 | <ul><li>Đã khắc phục sự cố kích hoạt một lệnh gọi đến trình nghe chuyển đổi trong quá trình gửi một sự kiện doanh thu quảng cáo từ trình kết nối SDK doanh thu quảng cáo.</li><li>Đã khắc phục sự cố đôi khi ứng dụng bị đóng băng khi một sự kiện doanh thu quảng cáo được gửi từ trình kết nối SDK doanh thu quảng cáo.</li></ul> |
| 6.9.3 | Ngày 28 tháng 11 năm 2022 | <ul><li>Đã cập nhật cấu trúc yêu cầu nội bộ để Nhận dữ liệu chuyển đổi (GCD). **Lưu ý**: Lưu ý: Dữ liệu phản hồi vẫn giữ nguyên.</li><li>Đã khắc phục sự cố xảy ra khi SDK kích hoạt một yêu cầu GCD trong lúc ứng dụng có ConversionListener được đặt thành null.</li></ul> |
| 6.9.2 | 02-10-2022 | <ul><li>Đã khắc phục sự cố liên quan đến yêu cầu xác thực mua sử dụng API validateAndLogInAppPurchase bị chậm.</li></ul> |
| 6.9.1 | 19-09-2022 | Bảo trì SDK |
| 6.9.0 | 12-09-2022 | <ul><li>Đã thêm hỗ trợ Liên kết giới thiệu trên Xiaomi GetApps Store.</li><li>Đã cập nhật API nội bộ cho báo cáo doanh thu quảng cáo. Kể từ phiên bản này, chỉ có trình kết nối SDK doanh thu quảng cáo chung được hỗ trợ.</li></ul> |
| 6.8.2 | 29-08-2022 | <ul><li>Đã khắc phục sự cố nghiêm trọng với cơ chế bộ nhớ đệm của SDK được đưa vào trong V6.7.0, khiến các sự kiện được lưu trong bộ nhớ đệm bị gửi nhiều lần.</li></ul> |
| 6.8.1  <br />Ngưng hỗ trợ | 24-08-2022 | <ul><li>Ngưng hỗ trợ Vui lòng sử dụng V6.8.2.</li></ul> |
| 6.8.0  <br />Ngưng hỗ trợ | 18-07-2022 | <ul><li>Ngưng hỗ trợ Vui lòng sử dụng V6.8.2.</li><li>Di chuyển `enableLocationCollection` API từ SDK. Ứng dụng vẫn có thể báo cáo dữ liệu vị trí của người dùng bằng cách chuyển trực tiếp tới SDK thông qua API logLocation.</li><li>Đã thêm `com.google.android.gms.permission.AD_ID` quyền của SDK `AndroidManifest.xml`. Đọc thêm thông tin ở đây.</li><li>Đã khắc phục sự cố liên quan đến tối ưu hóa và giấu mã bằng R8.</li></ul> |
| 6.7.0  <br />Ngưng hỗ trợ | Ngày 19 tháng 06 năm 2022 | <ul><li>Ngưng hỗ trợ Vui lòng sử dụng V6.8.2.</li><li>Đã thay đổi cách SDK xử lý các yêu cầu tới máy chủ AppsFlyer. Sau thay đổi này, yêu cầu báo cáo lần mở ứng dụng đầu tiên (lượt chuyển đổi) sẽ được ưu tiên hơn các sự kiện trong ứng dụng và các loại yêu cầu khác. Đọc thêm thông tin ở đây.</li><li>API mới: **`setDisableNetworkData`setDisableNetworkData** để lựa chọn không tham gia thu thập thông tin về mạng di động (tên nhà cung cấp dịch vụ, tên nhà mạng).</li></ul> |
| 6.6.1 | 16-05-2022 | Bảo trì SDK |
| 6.6.0 | Ngày 01 tháng 05 năm 2022 | <ul><li>Đã thêm nhiều thông số hơn vào lệnh gọi lại onDeepLinking của UDL cho luồng Liên kết sâu trực tiếp (người dùng hiện có). Để biết thêm thông tin.</li></ul> |
| 6.5.4 | Ngày 23 tháng 03 năm 2022 | Bảo trì SDK |
| 6.5.3 | 09-03-2022 | <ul><li>**Vá lỗi:** Sửa lỗi: Đã khắc phục sự cố bằng cách tạo liên kết mời người dùng chứa các ký tự không phải tiếng Anh.</li></ul> |
| 6.5.2 | 26-01-2022 | <ul><li>Đã khắc phục sự cố khi phân giải URL cho liên kết sâu bị trì hoãn trong UDL.</li><li>Đã cập nhật lên DexGuard 9.2</li><li>Tái cấu trúc và thay đổi nội bộ.</li></ul> |
| 6.5.1 | 29-12-2021 | <ul><li>Phân giải liên kết sâu bằng UDL đối với các ứng dụng sử dụng <Anchor target="_blank" href="/marketers/vi/docs/set-up-multi-store-android-attribution#channel-name">tùy chọn ngoài Cửa hàng kèm Kênh</Anchor></li></ul> |
| 6.5.0 | 07-12-2021 | <ul><li>Tái cấu trúc và thay đổi nội bộ.</li></ul> |
| 6.4.3 | 14-11-2021 | <ul><li>Đã sửa lỗi được giới thiệu trong `V6.4.2`với`LinkGenerator`gây ra việc tạo liên kết thiếu tham số URL.</li></ul> |
| 6.4.2 | Ngày 24 tháng 10 năm 2021 | Những lỗi sau đây đã được giải quyết:<ul><li>Thông số `pid`pidpid bị thêm hai lần vào URL tùy chỉnh do `LinkGenerator`LinkGeneratorLinkGenerator tạo.</li><li>Thêm `/` đã được thêm vào `af_dp` giá trị khi sử dụng `LinkGenerator` để tạo các lược đồ URI tùy chỉnh.</li><li>Nếu ứng dụng kích hoạt thu thập chỉ IMEI hoặc AndroidID, cả 2 loại mã này đều được thu thập.</li></ul> |
| 6.4.1 | 17-10-2021 | Đã giải quyết lỗi biên dịch khi sử dụng phiên bản Gradle thấp hơn V3.5.4. |
| 6.4.0 | 12-09-2021 | **API mới:** `setSharingFilterForPartners` cho phép bạn định cấu hình những đối tác mà SDK sẽ loại trừ khỏi việc chia sẻ dữ liệu.<br /><br />Kể từ phiên bản này, `setSharingFilter` Và `setSharingFilterForAllPartners` không được dùng nữa. |
| 6.3.2<br /><br />Khấu hao: 31/08/2024 | 06--06-2021 | **API mới**: [`setDisableAdvertisingIdentifiers`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers) |
| 6.3.1<br /><br />Khấu hao: 31/08/2024 | Ngày 26 tháng 05 năm 2021 | <ul><li>**API mới**: [`performOnDeepLinking`](https://dev.appsflyer.com/hc/docs/conversion-data)</li><li>Đã thêm khả năng kích hoạt API mời người dùng trước khi gọi lệnh <Anchor target="_blank" href="/marketers/vi/docs/user-invite-attribution#quy-trình-1">start</Anchor>/sau khi gọi lệnh `start`stopstart</li><li>**Vá lỗi**: Đã khắc phục sự cố trong đó cuộc gọi đến `waitForCustomerUserId` đã không được phát hành ngay cả sau khi gọi `setCustomerUserId`</li></ul> |
| 6.3.0<br /><br />Khấu hao: 31/08/2024 | 29-04-2021 | <ul><li>**Vá lỗi**: Việc gọi sai `onConversionDataFail` khi yêu cầu gửi sự kiện trong ứng dụng không thành công</li><li>Sửa lỗi: thu thập phép đo của cảm biến chuyển động (để phát hiện gian lận)</li><li>**Vá lỗi**: Sửa lỗi: Sửa lỗi liên quan đến giấu mã đối với UDL</li><li>Cập nhật kỹ thuật đối với API OneLink</li></ul> |
| 6.2.3  <br />Khấu hao: 31/08/2024 | 04-03-2021 | Bảo trì SDK |
| 6.2.0  <br />Khấu hao: 31/08/2024 | Ngày 07 tháng 02 năm 2021 | <ul><li>**API mới**: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setpartnerdata">`setPartnerData`</Anchor></li></ul> |
| 6.1.4  <br />Khấu hao: 31/08/2024 | Ngày 12 tháng 01 năm 2021 | <ul><li>Đã thêm hỗ trợ DexGuard V9</li></ul> |
| 6.1.3  <br />Khấu hao: 31/08/2024 | Ngày 24 tháng 12 năm 2020 | <ul><li>**API mới**: <Anchor target="_blank" href="/marketers/vi/docs/additional-sdk-integration-guide#record-push-notifications">`addPushNotificationDeepLinkPath`</Anchor> (hỗ trợ mực di chuyển)</li></ul> |
| 6.1.1  <br />Khấu hao: 31/08/2024 | Ngày 03 tháng 12 năm 2020 | <ul><li>Đã thêm hỗ trợ liên kết giới thiệu trên Samsung Galaxy Store</li><li>Sửa lỗi nhỏ và cải thiện hiệu suất.</li></ul> |
| 6.1.0  <br />Khấu hao: 31/08/2024 | Ngày 09 tháng 11 năm 2020 | <ul><li>Đã thêm hỗ trợ cho API liên kết sâu hợp nhất</li></ul> |
| 6.0.1  <br />Khấu hao: 31/08/2024 | Ngày 28 tháng 10 năm 2020 | Bảo trì SDK |
| 6.0.0  <br />Khấu hao: 31/08/2024 | 14-10-2020 | <ul><li>Các thay đổi lớn đối với chức năng SDK và API, bao gồm ngừng hỗ trợ và thay đổi tên phương thức. [Tìm hiểu thêm](/docs/appsflyer-android-sdk-release-notes#android-v600-release-notes)</li></ul> |

<div id="android-v600-release-notes" />

<Accordion title="Ghi chú phát hành Android V6.0.0">

### Các phương thức bị xóa/ngừng hỗ trợ hoặc đổi tên

#### Các phương thức bị loại bỏ/ngừng hỗ trợ

Các phương thức sau đã bị loại bỏ khỏi SDK:

* sendDeepLinkData
* trackAppLaunch
* setPluginDeepLinkData
* setConsumeAFDeepLinks
* setHostName

#### Các phương thức đã đổi tên

| Tên API (trước V6) | Tên API hiện tại (V6 trở lên) |
| --- | --- |
| stopTracking | stop |
| setCustomerIdAndTrack | setCustomerIdAndLogSession |
| startTracking | start |
| trackLocation | logLocation |
| reportTrackSession | logSession |
| trackEvent | logEvent |
| setDeviceTrackingDisabled | anonymizeUser |
| validateAndTrackInAppPurchase | validateAndLogInAppPurchase |
| isStopTracking | isStopped |
| trackAndOpenStore | logAndOpenStore |
| trackCrossPromoteImpression | logCrossPromoteImpression |
| trackInvite | logInvite |

### Đã đổi tên giao diện

| Tên giao diện (trước V6) | Tên giao diện hiện tại (V6 trở lên) |
| --- | --- |
| AppsFlyerTrackingRequestListener | AppsFlyerRequestListener |

</Accordion>

## Các phiên bản ngừng hỗ trợ

<div id="android-sdk-v5-release-notes" />

<Accordion title="Ghi chú phát hành SDK Android V5">

<table><tbody><tr><th>Phiên bản</th><th>Ngày phát hành</th><th>Chỉ bảo trì</th><th>Lưu ý</th></tr><tr><td><p>5.4.6</p></td><td>Ngày 09 tháng 11 năm 2020</td><td> </td><td><ul><li><span>Đã thêm hỗ trợ liên kết giới thiệu trên Huawei AppGallery.</span></li></ul></td></tr><tr><td><p>5.4.4</p></td><td>01-10-2020</td><td> </td><td><ul><li><span>Đã thêm hỗ trợ cho SDK để xử lý nhiều chuyển hướng từ ESP</span></li><li><span>Sửa lỗi và bảo trì</span></li></ul></td></tr><tr><td><p>5.4.3</p></td><td>Ngày 30 tháng 07 năm 2020</td><td> </td><td><ul><li><span>Khả năng ghi nhật ký và gỡ lỗi mở rộng</span></li><li><span>Sửa lỗi và bảo trì</span></li><li><span>Hỗ trợ người giới thiệu cài đặt V2 từ Google</span></li></ul></td></tr><tr><td><p>5.4.1</p></td><td>Ngày 30 tháng 06 năm 2020</td><td> </td><td><ul><li>Cho phép nhà quảng cáo kiểm soát hoạt động chia sẻ dữ liệu với các đối tác/mạng tích hợp. <a href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners" target="_blank">Tìm hiểu thêm</a> </li><li> <span>Sửa lỗi và bảo trì</span><span></span> </li></ul></td></tr><tr><td><p>5.4.0</p></td><td>Ngày 03 tháng 06 năm 2020</td><td> </td><td><ul><li><span>Hỗ trợ đầy đủ cho quá trình tự động thu thập OAID</span></li><li><span>Hỗ trợ nhiều người giới thiệu: SDK có thể thu thập những người giới thiệu Huawei và Google</span></li><li><span>Cải thiện hiệu suất SDK</span></li><li><span>Sửa lỗi và bảo trì</span></li></ul></td></tr><tr><td><p>5.3.0</p></td><td>2020-04-27 </td><td> </td><td><ul><li><span>Truy cập dữ liệu chuyển đổi liên kết sâu trực tiếp mới nhất bất kỳ lúc nào, thông qua phương thức onAppOpenAttribution</span></li><li><span>Thông số bổ sung khả dụng cho các lượt hiển thị quảng cáo chéo</span></li><li><span>Sửa lỗi: đã khắc phục sự cố bằng các tên tệp tin a. và b. trong Windows</span></li><li>Phương thức sendDeepLinkData <span>lấy dữ liệu phân bổ ngay cả khi người dùng được liên kết sâu vào một hoạt động cụ thể đã ngưng hỗ trợ để thay thế bằng phương thức startTracking()</span> </li></ul></td></tr><tr><td>5.2.0</td><td>2020-03-10 </td><td> </td><td><ul><li><span>Cho phép khởi tạo SDK trong mọi hoạt động</span></li><li><span>Khả năng bảo mật, ghi nhật ký và gỡ lỗi mở rộng</span></li><li><span>Sửa lỗi và bảo trì</span></li></ul></td></tr><tr><td>5.1.2</td><td>19-02-2020</td><td>Có</td><td></td></tr><tr><td>5.1.1</td><td>2020-01-23   </td><td>Có</td><td> </td></tr><tr><td>5.1.0</td><td>2020-01-06    </td><td> </td><td><ul><li><span>Nhắm mục tiêu đến Android 9 (API cấp 28) theo yêu cầu nhắm mục tiêu cấp API của Google</span></li><li><span>Các cải tiến để bảo vệ chống gian lận - dành cho khách hàng Protect360</span></li><li>Mô-đun tùy chọn để thu thập OAID (phù hợp với mạng nội địa Trung Quốc) - Xiaomi và Huawei (xem <span>https://github.com/AppsFlyerSDK/appsflyer-oaid</span>).</li><li><span>Cải thiện độ ổn định khi sử dụng setOneLinkCustomDomain cho ESP</span></li></ul></td></tr><tr><td>5.0.2</td><td>Ngày 23 tháng 12 năm 2019   </td><td> </td></tr><tr><td>5.0.1</td><td>2019-12-12   </td><td> </td></tr><tr><td>5.0.0</td><td>12-11-2019</td><td><ul><li> <span>Sửa lỗi và bảo trì</span><span></span> </li><li>Các thay đổi lớn đối với chức năng SDK và API, bao gồm ngừng hỗ trợ và thay đổi tên phương thức. <a href="./appsflyer-android-sdk-release-notes#android-v500-release-notes">Tìm hiểu thêm</a> </li></ul></td></tr></tbody></table>

</Accordion>

<div id="android-v500-release-notes" />

<Accordion title="Ghi chú phát hành Android V5.0.0">

#### **Cải thiện thời gian phản hồi SDK**

Bắt đầu từ SDK V5.0.0, thời gian phản hồi GCD cho các lượt cài đặt tự nhiên đã được cải thiện.

#### **Các phương thức đã bị xóa hoặc đổi tên**

**Thay đổi tên phương thức**

Tên phương thức chuyển đổi dữ liệu hiện đã trùng với cả Android và iOS. Điều này ảnh hưởng thức xử lý:

* dữ liệu chuyển đổi khi cài đặt
* lỗi nếu không có dữ liệu

| Tên Android trước bản SDK V5 | Tên iOS trước bản SDK V5 | Tên tiêu chuẩn hóa |
| --- | --- | --- |
| `onInstallConversionDataLoaded` | `onConversionDataReceived` | `onConversionDataSuccess` |
| `onInstallConversionFailure` | `onConversionDataRequestFailure` | `onConversionDataFail` |

**Phương thức bị loại bỏ**

Các phương pháp sau đã ngừng hỗ trợ trong các phiên bản SDK trước. Chúng hiện đã bị xóa khỏi SDK.

**Android**

* setGCMProjectID (String projectNumber)
* setGCMProjectNumber (String projectNumber)
* setGCMProjectNumber (Context context, String projectNumber)
* enableUninstallTracking (String senderId)
* setAppUserId (String id)
* setUserEmail (String email)
* setCollectFingerPrint (boolean isCollect)
* getAttributionId (ContentResolver contentResolver)
* Lớp FirebaseInstanceIdListener (phiên bản FirebaseInstanceIdService)

**iOS**

* loadConversionDataWithDelegate: (id`<AppsFlyerTrackerDelegate>`) delegate
* setHost:(NSString *) host

#### Thay đổi để nhận định dạng dữ liệu chuyển đổi

Trong phiên bản này, đối với mỗi lượt cài đặt hoặc mở ứng dụng, SDK trả về một đối tượng bản đồ có chứa dữ liệu chuyển đổi (GCD), chẳng hạn như nguồn truyền thông và tên chiến dịch.  Trong các phiên bản SDK trước, GCD chỉ trả về các thông số chứa một giá trị

Bắt đầu từ phiên bản này, tất cả thông số được trả về, kể cả những thông số không có giá trị. Các thông số không có giá trị sẽ được ghi là null.

> 📄 **Ví dụ**
>
> Lượt cài đặt sau khi nhấp vào URL sau:
>
> ```http
> https://app.appsflyer.com/com.sample.app?pid=super_media_source&c=awesome_campaign
>   &campaign_id=1234&af_sub1=promo
> ```
>
> Các phản hồi như sau:
>
>
> <Tabs>
> <Tab title="Phản hồi GCD trước SDK V5">
>
> ```json
>    {
>       "install_time": "2019-11-11 15:00:59.828",
>       "media_source": "super_media_source",
>       "orig_cost": "0.0",
>       "advertising_id": "215d8172-c61e-4d0c-9eb2-aa4d0971ed8c",
>       "af_status": "Non-organic",
>       "is_first_launch": "true",
>       "af_sub1": "promo",
>       "af_click_lookback": "7d",
>       "cost_cents_USD": "0",
>       "iscache": "true",
>       "click_time": "2019-11-11 15:00:35.102",
>       "campaign": "awesome_campaign",
>       "campaign_id": "1234",
>   }
> ```
>
> </Tab>
>
> <Tab title="Phản hồi GCD bắt đầu từ SDK V5">
>
> ```json
>    {
>       "adgroup": null,
>       "campaign": "awesome_campaign",
>       "media_source": "super_media_source",
>       "adset_id": null,
>       "campaign_id": 1234,
>       "iscache": true,
>       "install_time": "2019-11-11 15:00:59.828",
>       "adgroup_id": null,
>       "af_sub5": null,
>       "click_time": "2019-11-11 15:00:35.102",
>       "agency": null,
>       "cost_cents_USD": "0",
>       "advertising_id": "215d8172-c61e-4d0c-9eb2-aa4d0971ed8",
>       "adset": null,
>       "af_sub3": null,
>       "af_siteid": null,
>       "http_referrer": null,
>       "orig_cost": "0.0",
>       "af_sub4": null,
>       "af_cpi": null,
>       "af_sub1": "promo",
>       "af_click_lookback": "7d",
>       "af_sub2": null,
>       "af_status": "Non-organic",
>       "is_first_launch": "true",
>       "retargeting_conversion_type": "none"
>   }
> ```
>
> </Tab>
> </Tabs>
>

GCD trả về cùng một cấu trúc bất kể loại dữ liệu. Nếu một tham số trống, tham số đó sẽ được đưa vào GCD với giá trị null. Điều này giúp các nhà phát triển xử lý GCD dễ dàng hơn mà không cần phải điều chỉnh logic xử lý GCD, bất kể có bao gồm các thông số nhất định hay không. Để tìm hiểu thêm về dữ liệu chuyển đổi trong các tình huống khác nhau, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/conversion-data-payloads-and-scenarios">tại đây</Anchor>.

</Accordion>

<div id="deprecated-versions" />

<Accordion title="Ghi chú phát hành Android V4.0.0">

| Phiên bản | Ngày phát hành | Lưu ý |
| --- | --- | --- |
| 4.11.0 | 22-10-2019 | <ul><li>Cải thiện tính năng ghi nhật ký để gỡ lỗi tốt hơn cho:<ul><li>ESP</li><li>Phân giải Liên kết gắn thương hiệu</li><li>onInstallConversionData và onAppOpenAttribution.</li></ul></li><li>Sửa lỗi và bảo trì</li></ul> |
| 4.10.3 | 15-09-2019 | <ul><li>Sửa lỗi và bảo trì</li><li>Hỗ trợ Mã định danh Nhà quảng cáo Mở (OAID)</li></ul>4.10.2 |
| 4.10.1 | 01-07-2019 | Sửa lỗi và bảo trì |
| 4.10.0 | 14-05-2019 | <ul><li>Cải tiến SDK dành cho nhà phát triển sử dụng ProGuard.</li><li>Sửa lỗi và bảo trì</li></ul> |
| 4.9.0 | 17-03-2019 | <ul><li>setResolveDeepLinkURLs API để phân giải các OneLink được bọc bằng một Liên kết chung khác</li><li>Sửa lỗi ghi nhận thông báo đẩy khi bản ghi thông báo đẩy bị loại bỏ của tải trọng trước chứa cùng một pid và vẫn tồn tại trong bộ nhớ.</li><li>Sửa lỗi đánh máy từ af\_county thành af\_country</li><li>Sửa lỗi và bảo trì</li></ul> |
| 4.8.20 | 13-02-2019 | <ul><li>Cải thiện khả năng của gói miễn cước cho các nhà cung cấp dịch vụ di động</li><li>Sửa lỗi và bảo trì</li></ul> |
| 4.8.19 | 26-12-2018 | <ul><li>Đã khắc phục sự cố trong đó phương thức `waitForCustomerUserId()` nghỉ giải lao `generateLink`</li><li>Sửa lỗi và bảo trì</li></ul> |
| 4.8.18 | 11-11-2018 | <ul><li>Đã khắc phục sự cố liên kết sâu từ các hoạt động trampoline (thao tác nhấn)</li><li>Cải thiện độ chính xác của thu hút lại khi di chuyển giữa nền sau và nền trước</li><li>Sửa lỗi và bảo trì</li></ul> |
| 4.8.17 | 02-11-2018 | Khắc phục sự cố liên quan đến các xung đột trong ProGuard. Các xung đột này có thể dẫn đến mất dữ liệu khởi chạy ứng dụng trong một số trường hợp. Sự cố này chỉ ảnh hưởng đến phiên bản SDK 4.8.16 |
| 4.8.16 | 31-10-2018 | Sửa lỗi và bảo trì |
| 4.8.15 | 27-08-2018 | <ul><li>Sự kiện SDK bổ sung: Đăng ký, Bắt đầu dùng thử, Nhấp vào quảng cáo, Xem quảng cáo</li><li>Sửa lỗi và bảo trì</li></ul> |
| 4.8.14 | 31-07-2018 | <ul><li>Đã thêm API setOutOfStore và getOutOfStore để tự động đặt giá trị AF\_STORE</li><li>Thêm `onTrackingRequestFailure` Và `onTrackingRequestSuccess` API để nhận xác nhận rằng AppsFlyer đã nhận thành công máy chủ yêu cầu theo dõi</li></ul> |
| 4.8.13 | 20-06-2018 | <ul><li>Đã sửa lỗi trong một trường hợp hiếm gặp khi IMEI bị thiếu rõ ràng trong quá trình được chuyển qua API setImeiData</li><li>Sửa lỗi và bảo trì</li></ul> |
| 4.8.12 | 27-05-2018 | <ul><li>Đã sửa lỗi ứng dụng bị treo khi chạy thử JUnit sử dụng Robolectric</li><li>Sửa lỗi và bảo trì</li></ul> |
| 4.8.11 | 02-05-2018 | Sửa lỗi và bảo trì |
| 4.8.10 | 26-04-2018 | <ul><li>Thêm `setPreinstallAttribution` API</li><li>Sửa lỗi và bảo trì</li></ul> |
| 4.8.9 | 02-04-2018 | <ul><li>Chỉ thu thập IMEI nếu GooglePlayServices không tồn tại trên thiết bị và không thể truy xuất GAID trên thiết bị đó</li><li>Sửa lỗi và bảo trì</li></ul> |
| 4.8.8 | 11-03-2018 | <ul><li>Đã thêm API để trì hoãn quá trình khởi tạo SDK cho đến khi customerUserID được cung cấp</li><li>Sửa lỗi và bảo trì.</li></ul> |
| 4.8.7 | 25-01-2018 | <ul><li>`isStopTracking`isStopTrackingisStopTracking API để tắt tất cả các hoạt động SDK</li><li>`af_content` tham số sự kiện</li></ul> |
| 4.8.5 | 29-11-2017 | <ul><li>Hỗ trợ API của người giới thiệu mới từ Google</li><li>Phương thức init mới để nhận ngữ cảnh</li></ul> |
| 4.8.4 | 14-11-2017 | <ul><li>Đã gắn cờ vào getConversionData `is_first_launch`is\_first\_launchis\_first\_launch để cho biết đây là lần khởi chạy đầu tiên của ứng dụng. Cờ này cho phép nhà phát triển xác định lần khởi chạy đầu tiên của ứng dụng một cách dễ dàng trong phản hồi gọi lại getConversionData được trả về trong mỗi lần khởi chạy. Các giá trị của is\_first\_launch có thể bao gồm "true" hoặc "false"</li><li>Sửa lỗi và bảo trì</li></ul> |
| 4.8.3 | 27-09-2017 | Đã thêm hỗ trợ dữ liệu liên kết giới thiệu HTTP trên getConersionData |
| 4.8.2 | 19-09-2017 | Sửa lỗi sendDeepLinkData(this) cho các ứng dụng liên kết sâu tới nhiều hoạt động |
| 4.8.1 | 17-09-2017 | Cải thiện khả năng bảo vệ trước các sự kiện trong ứng dụng được gọi ra trước khi khởi tạo SDK |
| 4.8.0 | 03-09-2017 | <ul><li>API mời người dùng</li><li>API quảng cáo chéo</li><li>Tùy chỉnh thời gian giữa các phiên</li><li>Hỗ trợ Gói miễn cước cho các nhà cung cấp dịch vụ di động</li><li>Thông số sự kiện bổ sung af\_projected\_revenue</li><li>Sửa lỗi và bảo trì</li><li>Ra mắt phương thức init bổ sung - AppsFlyerLib.getInstance().init(AF\_DEV\_KEY,conversionDataListener);</li></ul> |
| 4.7.4 | 28-06-2017 | Đã cải thiện hiệu quả xử lý ScheduledExecutorSerice bị tắt nhiều lần |
| 4.7.3 | 06-06-2017 | Cải tiến để tích hợp mParticle |
| 4.7.2 | 22-05-2017 | <ul><li>Đã khắc phục sự cố rò rỉ nhỏ của bộ nhớ</li><li>Đã tăng độ chính xác của phép đo Lượt gỡ cài đặt</li><li>Đã sửa lỗi cảnh báo ProGaurd thường ảnh hưởng đến việc đo lường lượt gỡ cài đặt</li><li>Sửa lỗi và bảo trì</li></ul> |
| 4.7.1 | 22-02-2017 | Đã sửa lỗi cảnh báo do ProGuard kích hoạt |
| 4.7.0 | 13-02-2017 | <ul><li>Thông số sự kiện bổ sung</li><li>Hỗ trợ đo lường lượt gỡ cài đặt dựa trên Firebase</li><li>Sửa lỗi và bảo trì</li></ul> |

</Accordion>

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-sdk-version-control-policy">Chính sách kiểm soát phiên bản SDK của AppsFlyer</Anchor>

<div data-zendesk-anchors="android-sdk-v6=sdk-android-v6 h_01H9ZPCP8RWF24WAZ6YYMA1GS0=sdk-android-v6 h_01H9ZPCP8S2P9Z93ZDENDHKJHD=android-v600-release-notes methods-removeddeprecated-or-renamed=c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-b%E1%BB%8B-x%C3%B3ang%E1%BB%ABng-h%E1%BB%97-tr%E1%BB%A3-ho%E1%BA%B7c-%C4%91%E1%BB%95i-t%C3%AAn h_01H9ZPCP8SCYTEYJG9J1SANGVJ=c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-b%E1%BB%8B-x%C3%B3ang%E1%BB%ABng-h%E1%BB%97-tr%E1%BB%A3-ho%E1%BA%B7c-%C4%91%E1%BB%95i-t%C3%AAn methods-removeddeprecated=c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-b%E1%BB%8B-lo%E1%BA%A1i-b%E1%BB%8Fng%E1%BB%ABng-h%E1%BB%97-tr%E1%BB%A3 01EEYC8A6FNJ91R15X633BHSXF=c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-b%E1%BB%8B-lo%E1%BA%A1i-b%E1%BB%8Fng%E1%BB%ABng-h%E1%BB%97-tr%E1%BB%A3 methods-renamed=c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-%C4%91%C3%A3-%C4%91%E1%BB%95i-t%C3%AAn 01EEYC8A6F8PB4C94Z14KXYD68=c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-%C4%91%C3%A3-%C4%91%E1%BB%95i-t%C3%AAn renamed-interface=%C4%91%C3%A3-%C4%91%E1%BB%95i-t%C3%AAn-giao-di%E1%BB%87n h_01H9ZPCP8SV4VPEZA39VDTMCZ7=%C4%91%C3%A3-%C4%91%E1%BB%95i-t%C3%AAn-giao-di%E1%BB%87n android-sdk-v5=c%C3%A1c-phi%C3%AAn-b%E1%BA%A3n-ng%E1%BB%ABng-h%E1%BB%97-tr%E1%BB%A3 h_01H9ZPCP8S37W1456YQN6RQDM7=c%C3%A1c-phi%C3%AAn-b%E1%BA%A3n-ng%E1%BB%ABng-h%E1%BB%97-tr%E1%BB%A3 h_01H9ZPCP8SZ3QVX773J2X3QEGX=android-sdk-v5-release-notes h_01H9ZPCP8SAMFHXZW0T6CPEEYZ=android-v500-release-notes improved-sdk-response-time=c%E1%BA%A3i-thi%E1%BB%87n-th%E1%BB%9Di-gian-ph%E1%BA%A3n-h%E1%BB%93i-sdk h_01H9ZPCP8SN7NRGH3FZBEGCB3E=c%E1%BA%A3i-thi%E1%BB%87n-th%E1%BB%9Di-gian-ph%E1%BA%A3n-h%E1%BB%93i-sdk methods-removed-or-renamed=c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-%C4%91%C3%A3-b%E1%BB%8B-x%C3%B3a-ho%E1%BA%B7c-%C4%91%E1%BB%95i-t%C3%AAn h_01H9ZPCP8SY1HYDNR6HEZHXN37=c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-%C4%91%C3%A3-b%E1%BB%8B-x%C3%B3a-ho%E1%BA%B7c-%C4%91%E1%BB%95i-t%C3%AAn changes-to-get-conversion-data-format=thay-%C4%91%E1%BB%95i-%C4%91%E1%BB%83-nh%E1%BA%ADn-%C4%91%E1%BB%8Bnh-d%E1%BA%A1ng-d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i h_01H9ZPCP8S6Q97DNCZ8ANVMVT8=thay-%C4%91%E1%BB%95i-%C4%91%E1%BB%83-nh%E1%BA%ADn-%C4%91%E1%BB%8Bnh-d%E1%BA%A1ng-d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i h_01H9ZPCP8TAWT16MR1TVZVEVJ8=v%C3%AD-d%E1%BB%A5 h_01H9ZPCP8TFSA3SXDGTAZYC00V=deprecated-versions h_01HDNZ774ME3SVT89JS7R4MSKE=xem-th%C3%AAm" />
