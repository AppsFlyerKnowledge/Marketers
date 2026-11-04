---
title: Ghi chú phát hành SDK AppsFlyer cho iOS
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
  created_at: '2017-03-09T19:49:54Z'
  edited_at: '2023-11-24T13:23:37Z'
  id: 115001224823
  locale: vi
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/vi/articles/115001224823
---
> **Khái quát:** Ghi chú phát hành SDK iOS `phiên bản V4 trở lên`.

<div id="ios-sdk-release-notes" />

## SDK iOS V6

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk">Hướng dẫn tích hợp SDK iOS dành cho nhà phát triển</Anchor>

| Phiên bản | Ngày phát hành | Chỉ bảo trì | Lưu ý |
| --- | --- | --- | --- |
| 6.12.2 | Ngày 24 tháng 08 năm 2023 | Có |  |
| 6.12.1 | Ngày 20 tháng 07 năm 2023 |  | <ul><li>Đã sửa lỗi trong SKAdNetwork 4.0 khiến giá trị chuyển đổi thô được báo cáo là "Không"</li><li>Đã sửa lỗi treo trong triển khai tvOS</li></ul> |
| 6.12.0 | Ngày 28 tháng 06 năm 2023 |  | Đã gỡ bỏ hỗ trợ bitcode từ SDK |
| 6.11.2 | Ngày 13 tháng 06 năm 2023 |  | Đã sửa lỗi xuất hiện trong v6.11.0, trong đó gọi ra  `validateAndLogInAppPurchase`  (API cũ để Xác thực Mua và ghi nhật ký) không ghi lại sự kiện mua.   <br />  <br />**Quan trọng:** Nếu bạn đang sử dụng `v6.11.0`hoặc `v6.11.1`, và API `validateAndLogInAppPurchase` vui lòng nâng cấp lên phiên bản này. |
| 6.11.1 | Ngày 24 tháng 05 năm 2023 | Có |  |
| 6.11.0 | Ngày 25 tháng 04 năm 2023 |  | <ul><li>Tên miền AppsFlyer mới trong URL được SDK sử dụng để gửi yêu cầu đến máy chủ AppsFlyer.</li><li>Đã thay đổi hành vi của API setHost khi giá trị trống hoặc giá trị rỗng được gửi. [Tìm hiểu thêm](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#sethost)</li></ul> |
| 6.10.1 | Ngày 02 tháng 04 năm 2023 |  | Đã thêm thông số `link` vào tải trọng UDL của tình huống Liên kết Sâu Trực tiếp |
| 6.10.0 | Ngày 15 tháng 02 năm 2023 |  | Hỗ trợ SKAdNetwork 4.0. <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide">Tìm hiểu thêm về giải pháp SKAdNetwork của AppsFlyer</Anchor> |
| 6.9.2 | Ngày 31 tháng 01 năm 2023 |  | Đã cập nhật cấu trúc yêu cầu nội bộ để Nhận Dữ liệu Chuyển đổi (GCD). **Lưu ý**: Dữ liệu phản hồi vẫn giữ nguyên. |
| 6.9.1 | Ngày 28 tháng 11 năm 2022 |  | Đã cập nhật cấu trúc yêu cầu nội bộ để Nhận Dữ liệu Chuyển đổi (GCD). **Lưu ý**: Dữ liệu phản hồi vẫn giữ nguyên. |
| 6.9.0 | Ngày 06 tháng 11 năm 2022 |  | Đã cập nhật API nội bộ cho báo cáo AdRevenue. Bắt đầu từ phiên bản này, chỉ [Trình kết nối Chung cho AdRevenue](https://dev.appsflyer.com/hc/docs/ad-revenue-2) được hỗ trợ.<br /><br />Phiên bản này của SDK tương thích với Trình kết nối AdRevenue `V6.9.0`. |
| 6.8.1 | Ngày 09 tháng 08 năm 2022 |  | **Phát hiện Cài đặt lại**: Cải thiện khả năng phát hiện và báo cáo các lần cài đặt lại ứng dụng bằng bộ nhớ trên thiết bị. Khả năng này có thể được kiểm soát trong bảng điều khiển AppsFlyer từ <Anchor target="_blank" href="/marketers/vi/docs/app-settings">trang Apps Setting</Anchor>. |
| 6.8.0  <br />(Ngừng hỗ trợ) | Ngày 19 tháng 07 năm 2022 |  | Để Phát hiện Cài đặt lại, vui lòng sử dụng SDK V6.8.1 trở lên |
| 6.7.0 | Ngày 19 tháng 06 năm 2022 |  | Cập nhật cách triển khai cho SKAdNetwork để sử dụng API Apple `updatePostbackConversionValue` đã cập nhật, được giới thiệu trong iOS 15.4.<br /><br />Điều này không ảnh hưởng đến dữ liệu được gửi từ SKAdNetwork và không yêu cầu bất kỳ thay đổi nào đối với mã ứng dụng. |
| 6.6.1 | Ngày 16 tháng 05 năm 2022 | Có |  |
| 6.6.0 | Ngày 01 tháng 05 năm 2022 |  | Đã thêm nhiều thông số hơn vào lệnh gọi lại `didResolveDeepLink` của UDL cho luồng Liên kết Sâu Trực tiếp (người dùng hiện có). <Anchor target="_blank" href="/marketers/vi/docs/bulletin-additional-parameters-available-for-deep-linking-existing-users">Để biết thêm thông tin</Anchor>. |
| 6.5.4 | Ngày 23 tháng 03 năm 2022 | Có |  |
| 6.5.3 | Ngày 02 tháng 03 năm 2022 |  | **Sửa lỗi:** Đã sửa lỗi với lệnh gọi kép `didResolveDeepLink` trên các liên kết dựa trên lược đồ URI. |
| 6.5.2 | Ngày 26 tháng 01 năm 2022 | Có |  |
| 6.5.1 | Ngày 03 tháng 01 năm 2022 | Có |  |
| 6.5.0 | Ngày 22 tháng 12 năm 2021 |  | Tái cấu trúc và thay đổi nội bộ. |
| 6.4.4 | Ngày 12 tháng 12 năm 2021 | Có |  |
| 6.4.3 | Ngày 30 tháng 11 năm 2021 |  | Sửa lỗi ổn định cho MacOS 10.14.6 với xcframework. |
| 6.4.2 | Ngày 28 tháng 10 năm 2021 | Có |  |
| 6.4.1 | Ngày 24 tháng 10 năm 2021 |  | Đã giải quyết tính ổn định trong các ứng dụng Unity. |
| 6.4.0 | 12-09-2021 |  | **API bổ sung:** `setSharingFilterForPartners` cho phép bạn cấu hình những đối tác mà SDK sẽ không chia sẻ dữ liệu.<br /><br />Kể từ phiên bản này, `setSharingFilter` và `setSharingFilterForAllPartners` sẽ không còn được hỗ trợ. |
| 6.3.5 | Ngày 19 tháng 08 năm 2021 |  | **Bổ sung API**: `setCurrentDeviceLanguage`<br /><br />Bắt đầu từ phiên bản này, ngôn ngữ không còn được SDK tự động thu thập nữa. |
| 6.3.4 | Ngày 21 tháng 07 năm 2021 |  | <ul><li>**Sửa lỗi:** Đã sửa lỗi khi chạy SDK trên Trình mô phỏng XCode 12.5</li><li>Sửa lỗi và cập nhật nhỏ.</li></ul> |
| 6.3.2 | 2021-06-17 |  | Đã cải thiện nhật ký gỡ lỗi. |
| 6.3.1 | 2021-06-02 | Có | Đã giải quyết tính ổn định trong trình cắm Unity. |
| 6.3.0 | Ngày 13 tháng 05 năm 2021 |  | <ul><li>Hỗ trợ Apple Silicon: Đã thêm hỗ trợ để chạy SDK trên trình mô phỏng bằng máy Mac có chipset M1</li><li>Bắt đầu từ phiên bản này, SDK hỗ trợ iOS `9` trở lên. iOS `8` không còn được hỗ trợ.</li><li>SDK Chế độ Nghiêm ngặt của iOS: Đã thêm hỗ trợ cho trình quản lý phụ thuộc Carthage</li><li>Cập nhật kỹ thuật đối với API OneLink</li></ul> |
| 6.2.6 | Ngày 25 tháng 04 năm 2021 |  | <ul><li>Sửa lỗi: Quy tắc SKAdNetwork không tải khi quá trình khởi tạo SDK diễn ra sau `didFinishLaunchingWithOptions`</li><li>Sửa lỗi: trường hợp hiếm gặp `waitForATTUserAuthorization` khiến sự kiện khởi chạy được gửi mà không có IDFA, ngay cả khi có sự đồng ý của người dùng</li><li>Cho phép SDK chạy trên thiết bị iOS 8</li><li>Dọn dẹp và loại bỏ mã và dữ liệu không sử dụng</li></ul> |
| 6.2.5 | Ngày 06 tháng 04 năm 2021 |  | Tái cấu trúc, dọn dẹp, loại bỏ dữ liệu không sử dụng khỏi SDK.<br /><br />Bắt đầu từ phiên bản này:<ul><li>Phương thức `setShouldCollectDeviceName` không còn được hỗ trợ và sẽ không trả về tên thiết bị</li><li>Thông số `wifi` gửi từ SDK được đặt thành `False`</li></ul> |
| 6.2.4 | Ngày 15 tháng 03 năm 2021 |  | Sửa lỗi liên quan đến chế độ đo lường doanh thu SKAdNetwork và các sự kiện trong ứng dụng có chứa thông số `AF_REVENUE` .<br /><br />Bắt đầu từ phiên bản này, trong trường hợp đo lường doanh thu: bất kỳ sự kiện nào chứa `AF_REVENUE` đều ảnh hưởng đến giá trị chuyển đổi. Trước thay đổi này, giá trị chuyển đổi chỉ được đặt nếu nó nằm trong khung sự kiện`AF_PURCHASE`. <br /><br />**Lưu ý:** Nếu triển khai tính năng đo lường Doanh thu SKAdNetwork, bạn phải nâng cấp lên phiên bản này. |
| 6.2.3 | Ngày 07 tháng 03 năm 2021 |  | Sửa lỗi liên quan đến việc gọi `updateConversionValue` của SKAdNetwork. |
| 6.2.2 | Ngày 18 tháng 02 năm 2021 | Có |  |
| 6.2.1 | Ngày 15 tháng 02 năm 2021 |  | Hỗ trợ <Anchor target="_blank" href="/marketers/vi/docs/server-to-server-events-api-for-mobile-s2s-mobile">Báo cáo sự kiện bằng S2S</Anchor> |
| 6.2.0 | Ngày 07 tháng 02 năm 2021 |  | API bổ sung: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setpartnerdata">setPartnerData</Anchor> |
| 6.1.4 | Ngày 12 tháng 01 năm 2021 | Có |  |
| 6.1.3 | Ngày 24 tháng 12 năm 2020 |  | <ul><li>API Bổ sung: <Anchor target="_blank" href="/marketers/vi/docs/additional-sdk-integration-guide#record-push-notifications">`addPushNotificationDeepLinkPath`</Anchor> (hỗ trợ Movable Ink)</li><li>Hỗ trợ <Anchor target="_blank" href="https://developer.apple.com/documentation/adservices">Apple AdServices Framework</Anchor></li></ul> |
| 6.1.2 | Ngày 03 tháng 12 năm 2020 | Có |  |
| 6.1.1 | Ngày 17 tháng 11 năm 2020 |  | Giới thiệu <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">SDK chế độ nghiêm ngặt</Anchor> |
| 6.1.0 | Ngày 09 tháng 11 năm 2020 |  | Hỗ trợ <Anchor target="_blank" href="https://dev.appsflyer.com/docs/ios-unified-deep-linking">API liên kết sâu hợp nhất</Anchor> |
| 6.0.8 | Ngày 28 tháng 10 năm 2020 |  | Hỗ trợ phân bổ <Anchor target="_blank" href="/marketers/vi/docs/apple-app-clips-integration-guide">Apple App Clips</Anchor> |
| 6.0.7 | Ngày 21 tháng 10 năm 2020 | Có |  |
| 6.0.6 | Ngày 20 tháng 10 năm 2020 | Có |  |
| 6.0.5 | Ngày 08 tháng 10 năm 2020 | Có |  |
| 6.0.4 | Ngày 30 tháng 09 năm 2020 |  | Hỗ trợ nhiều chuyển hướng từ ESP |
| 6.0.3 | Ngày 06 tháng 09 năm 2020 |  | <ul><li>Thay đổi tên API:<br />waitForAdvertisingIdentifier --> waitForATTUserAuthorization</li><li>SDK thu thập IDFA theo mặc định cho iOS 14 (như đối với các phiên bản iOS cũ hơn)</li></ul> |
| 6.0.2 [ngừng hỗ trợ] | Ngày 27 tháng 08 năm 2020 |  | <ul><li>Thay đổi tên API:<br />deviceLoggingDisabled --> anonymizeUser</li><li>Cần có hộp thoại AppTrackingTransparency (ATT) để thu thập IDFA cho iOS 14</li><li>Đã thêm hỗ trợ cho phân bổ quảng cáo chéo IDFV</li></ul> |
| 6.0.1 beta<br /><br />[ngừng hỗ trợ] | Ngày 06 tháng 08 năm 2020 |  | <ul><li>Đã thêm hỗ trợ cho <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide">phân bổ SKAdNetwork</Anchor> để giúp nhà quảng cáo đo lường mức độ thành công của chiến dịch trong khi vẫn duy trì quyền riêng tư của người dùng</li></ul> |
| 6.0.0 beta<br /><br />[ngừng hỗ trợ] | Ngày 04 tháng 08 năm 2020 |  | <ul><li>Khả năng gỡ lỗi mở rộng</li><li>Các thay đổi lớn đối với chức năng SDK và API. [Tìm hiểu thêm](/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes)</li></ul> |

<div id="ios-v600-release-notes" />

<Accordion title="Ghi chú phát hành iOS V6.0.0">

### Các phương thức được thêm, loại bỏ hoặc đổi tên

#### Các phương thức được thêm vào

Các phương thức sau đã được thêm vào SDK:

* waitForAdvertisingIdentifier

#### Phương thức bị loại bỏ

Các phương thức sau đã bị loại bỏ khỏi SDK:

* disableAppleAdSupportTracking

#### Các phương thức đã đổi tên

| Tên API (trước V6) | Tên API hiện tại (V6 trở lên) |
| --- | --- |
| AppsFlyerTracker | AppsFlyerLib |
| disableIAdTracking | disableCollectASA |
| trackAppLaunchWithCompletionHandler | startWithCompletionHandler |
| trackLocation | logLocationEvent |
| trackAppLaunch | start |
| trackEvent | logEvent |
| disableAppleAdSupportTracking | disableAdvertiserIdentifier |
| validateAndTrackInAppPurchase | validateAndLogInAppPurchase |
| isStopTracking | isStopped |
| deviceTrackingDisabled | deviceLoggingDisabled |
| sharedTracker (Objective C) | shared |

### Hỗ trợ App Tracking Transparency (ATT)

SDK iOS hỗ trợ thu thập IDFA trên iOS 14 trở lên thông qua khung App Tracking Transparency. Để biết thêm thông tin chi tiết:

* <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">Cấu hình hỗ trợ ATT trong SDK iOS</Anchor>
* <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide#customize-att-consent-dialog">Tùy chỉnh hộp thoại đồng ý ATT</Anchor>

</Accordion>

## SDK iOS V5

<div id="ios-sdk-v5::7a4821ba" />

<Accordion title="SDK iOS V5">

| Phiên bản | Ngày phát hành | Lưu ý |
| --- | --- | --- |
| 5.4.4 | Ngày 23 tháng 08 năm 2020 | Sửa lỗi và bảo trì |
| 5.4.3 | Ngày 30 tháng 07 năm 2020 | <ul><li>Khả năng ghi nhật ký và gỡ lỗi mở rộng</li><li>Sửa lỗi và bảo trì</li></ul> |
| 5.4.1 | Ngày 30 tháng 06 năm 2020 | <ul><li>Cho phép nhà quảng cáo kiểm soát hoạt động chia sẻ dữ liệu với các đối tác/mạng tích hợp. <Anchor target="_blank" href="/marketers/vi/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">Tìm hiểu thêm</Anchor></li><li>Phương thức onAppOpenAttribution được cải thiện cho các URL dài của Liên kết Chung: Các thông số liên kết được trả về đã được phân tích cú pháp</li><li>Sửa lỗi và bảo trì</li></ul> |
| 5.4.0 | Ngày 03 tháng 06 năm 2020 | Hỗ trợ dự án MAC Catalyst |
| 5.3.0 | Ngày 27 tháng 04 năm 2020 | <ul><li>Truy cập dữ liệu chuyển đổi liên kết sâu trực tiếp mới nhất bất kỳ lúc nào, thông qua phương thức onAppOpenAttribution</li><li>Thông số bổ sung khả dụng cho các lượt hiển thị quảng cáo chéo</li><li>Các ứng dụng chính và tiện ích mở rộng ứng dụng có cùng ID AppsFlyer, do đó các sự kiện trong ứng dụng được nhóm tương tự nhau</li><li>Sửa lỗi và bảo trì</li></ul> |
| 5.2.0 | Ngày 10 tháng 03 năm 2020 | <ul><li>Khả năng ghi nhật ký và gỡ lỗi mở rộng</li><li>Sửa lỗi và bảo trì</li></ul> |
| 5.1.0 | Ngày 23 tháng 12 năm 2019 | <ul><li>Cải thiện Obj-C - Khả năng tương tác Swift</li><li>Sửa lỗi và bảo trì</li></ul> |

</Accordion>

<div id="ios-v500-release-notes" />

<Accordion title="Ghi chú phát hành iOS V5.0.0">

### Cải thiện thời gian phản hồi SDK

Bắt đầu từ SDK V5.0.0, thời gian phản hồi GCD cho các lượt cài đặt tự nhiên đã được cải thiện.

### Các phương thức đã bị xóa hoặc đổi tên

#### Thay đổi tên phương thức

Tên phương thức chuyển đổi dữ liệu hiện đã trùng với cả Android và iOS. Điều này ảnh hưởng thức xử lý:

* Dữ liệu chuyển đổi khi cài đặt
* Lỗi nếu không có dữ liệu

| Tên Android trước bản SDK V5 | Tên iOS trước bản SDK V5 | Tên tiêu chuẩn hóa |
| --- | --- | --- |
| `onInstallConversionDataLoaded` | `onConversionDataReceived` | `onConversionDataSuccess` |
| `onInstallConversionFailure` | `onConversionDataRequestFailure` | `onConversionDataFail` |

#### Phương thức bị loại bỏ

Các phương thức sau đã ngừng hỗ trợ trong các phiên bản SDK trước. Chúng hiện đã bị loại bỏ khỏi SDK.

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

Trong phiên bản này, đối với mỗi lượt cài đặt hoặc mở ứng dụng, SDK trả về một đối tượng bản đồ có chứa dữ liệu chuyển đổi (GCD), chẳng hạn như nguồn truyền thông và tên chiến dịch. Trong các phiên bản SDK trước, GCD chỉ trả về các thông số chứa một giá trị

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
>       "is_first_launch": true,
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
>       "is_first_launch": true,
>       "retargeting_conversion_type": "none"
>   }
> ```
>
> </Tab>
> </Tabs>
>

GCD trả về cùng một cấu trúc bất kể loại dữ liệu. Nếu một tham số trống, tham số đó sẽ được đưa vào GCD với giá trị null. Điều này giúp các nhà phát triển xử lý GCD dễ dàng hơn mà không cần phải điều chỉnh logic xử lý GCD, bất kể có bao gồm các thông số nhất định hay không. Để tìm hiểu thêm về dữ liệu chuyển đổi trong các tình huống khác nhau, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/conversion-data-payloads-and-scenarios">tại đây</Anchor>.

</Accordion>

<div id="deprecated-versions" />

<Accordion title="Các phiên bản ngừng hỗ trợ">

Bài đọc liên quan: <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-sdk-version-control-policy">Chính sách kiểm soát phiên bản SDK của AppsFlyer</Anchor>

| Phiên bản | Ngày phát hành | Lưu ý |
| --- | --- | --- |
| 5.0.0 | Ngày 12 tháng 11 năm 2019 | <ul><li>Sửa lỗi và bảo trì</li><li>Các thay đổi lớn đối với chức năng SDK và API. [Tìm hiểu thêm](/docs/appsflyer-ios-sdk-release-notes#ios-v500-release-notes)</li></ul> |
| 4.11.2 | Ngày 07 tháng 11 năm 2019 | Sửa lỗi và bảo trì |
| 4.11.1 | Ngày 31 tháng 10 năm 2019 | Sửa lỗi và bảo trì |
| 4.11.0 | Ngày 17 tháng 10 năm 2019 | <ul><li>Đã bỏ hỗ trợ cho iOS 7. iOS 8 hiện là phiên bản được hỗ trợ tối thiểu.</li><li>Đã cải thiện ghi nhật ký để có khả năng gỡ lỗi tốt hơn, giải quyết ESP và Liên kết Gắn thương hiệu cũng như cho onInstallConversionData và onAppOpenAttribution.</li><li>Đã cải thiện khả năng tìm nạp của Apple Search Ads.</li></ul> |
| 4.10.4 | Ngày 12 tháng 09 năm 2019 | <ul><li>Cần có bản cập nhật để truy xuất mã thông báo đẩy iOS 13 để Đo lường Lượt gỡ cài đặt</li><li>Sửa lỗi và bảo trì</li></ul> |
| 4.10.3 | Ngày 16 tháng 07 năm 2019 | Sửa lỗi và bảo trì |
| 4.10.2 | Ngày 02 tháng 07 năm 2019 | Sửa lỗi và bảo trì |
| 4.10.1 | Ngày 01 tháng 07 năm 2019 | Sửa lỗi và bảo trì |
| 4.10.0 | Ngày 14 tháng 05 năm 2019 | <ul><li>API trackAppLaunchWithCompletionHandler để xử lý thành công hay thất bại trong việc theo dõi việc khởi chạy ứng dụng</li><li>API CompleteHandler để xử lý thành công hay thất bại khi ghi lại các sự kiện trong ứng dụng</li><li>Sửa lỗi và bảo trì</li></ul> |
| 4.9.0 | Ngày 18 tháng 03 năm 2019 | <ul><li>API setResolveDeepLinkURLs để phân giải các OneLink được bọc bằng một Liên kết Chung khác</li><li>Đã loại bỏ mức sử dụng UIPasteboard cho phân bổ Meta ads cho iOS 7 trở xuống</li><li>Sửa lỗi và bảo trì</li></ul> |
| 4.8.12 | Ngày 13 tháng 02 năm 2019 | <ul><li>Cải thiện khả năng của gói miễn cước cho các nhà cung cấp dịch vụ di động</li><li>Cải thiện khả năng của gói miễn cước cho các nhà cung cấp dịch vụ di động</li><li>Sửa lỗi và bảo trì</li></ul> |
| 4.8.11 | Ngày 09 tháng 01 năm 2019 | <ul><li>Đã sửa lỗi API waitForCustomUserId() đang phá vỡ generateLink</li></ul> |
| 4.8.10 | Ngày 31 tháng 10 năm 2018 | <ul><li>Đã sửa lỗi tình trạng dồn đuổi khi continueUserActivity được gọi ra sau applicationDidBecomeActive khiến onAppOpenAttribution không được gọi ra</li><li>validateAndTrackInAppPurchase bỏ qua sửa thông số bổ sung</li><li>Sửa lỗi và bảo trì</li></ul> |
| 4.8.9 | Ngày 27 tháng 08 năm 2018 | <ul><li>Các sự kiện SDK mới: Đăng ký, Bắt đầu Dùng thử, Lượt nhấp vào Quảng cáo, Chế độ xem Quảng cáo</li><li>Sửa lỗi và bảo trì</li></ul> |
| 4.8.8 | Ngày 30 tháng 07 năm 2018 | <ul><li>Đã sửa lỗi khi sử dụng is\_first\_launch thông qua JSONSerialiser được trả về dưới dạng số nguyên thay vì boolean</li><li>Sửa lỗi và bảo trì4.8.7</li></ul> |
| 4.8.7 | Ngày 22 tháng 07 năm 2018 | Sửa lỗi và bảo trì |
| 4.8.6 | Ngày 18 tháng 06 năm 2018 | Sửa lỗi và bảo trì |
| 4.8.5 | Ngày 29 tháng 05 năm 2018 | Sửa lỗi và bảo trì |
| 4.8.4 | Ngày 03 tháng 05 năm 2018 | Sửa lỗi và bảo trì |
| 4.8.3 | Ngày 25 tháng 01 năm 2018 | <ul><li>Sửa lỗi và bảo trì</li><li>API shouldCollectDeviceName</li><li>thông số sự kiện af\_content</li><li>API shouldCollectDeviceName</li><li>thông số sự kiện af\_content</li></ul> |

</Accordion>

## Tổng kiểm tra SDK iOS

AppsFlyer sử dụng tính năng tổng kiểm tra md5:

<div id="v6-checksums" />

<Accordion title="Tổng kiểm tra V6">

| Phiên bản SDK iOS | Static Lib | Static Framework |
| --- | --- | --- |
| 6.6.1 | ff41a3dfeb9fe7579f8f706f3c62bbbc | 7acf1f10de7602b363a70d4a710b050d |
| 6.6.0 | ba2d2d0b64f3b0f6476b818c1b8faf5f | 544c7c7e4af29afa4100b6c43affcf8f |
| 6.5.4 | 5a1146a95abc84b20940b43cacc8b42a | 3a0a22a28b4082a5b2f0931104b0a9c8 |
| 6.5.3 | b33008f83f5eafa864902db97c003c06 | 3ff6754c8c238dd13e4c6251ffb4aedf |
| 6.5.2 | 3083df065d14553fb1b4e34f3f7fb381 | 3ce0ea75e4fe3cf6313fde27d57d20ed |
| 6.5.1 | 8d91f52cc2df073d1bca9919b44aeeeb | c9353bdfa71ff9b4acc9097eee83d35e |
| 6.5.0 | 4b72dcf125430d3d374967df5e084c6a | 5d6ac0e9f7a1430e106685da117a7716 |
| 6.4.4 | 86586acda674d95f5661a613dccea3dd | 7f4c431de13b84fd0926132c2154f0a8 |
| 6.4.3 | dd5fcf42065ba2ad28f6311153fd4752 | 178274e63a6aa604682a3095ddf59ac5 |
| 6.4.2 | 2341911e4f34d17560b85409b86528c4 | 46df5badc29ee983a872d7859cedd59a |
| 6.4.1 | 4ef6e6d424bc9b95a1ee8ebda0d5c639 | 0efc4140b47cbaf65b24a9087c61c434 |
| 6.4.0 | 9210f7064a7692c8dff7a779043e97fc | f103763da687fef88db60ca6b395dc41 |
| 6.3.5 | b61193ab28a601ec0dfaf4aa641a7834 | 9fbbf0f4cb865c95d919396d2af9a053 |
| 6.3.4 | 9cca998fde11c473e60bee3854f0c0da | c47a02177c28290ed8c934a6428dc0dc |
| 6.3.2 | c563e2b8ee4bf6647e496d1b0ad31285 | 5c474247d3ce607fca43af9c9faf1fbc |
| 6.3.1 | e04a567680676b3784079d35ca32b5fe | 36b808db3952803c929188ca57fe88c6 |
| 6.3.0 | baa5e6d82a363e636740d6c5494e107d | f2ebe86a93a2fd5122ad11224f17736c |
| 6.2.6 | 9b989e131fe596b51223b6f47efac3c6 | 6396371abf0f66f0e6aeccd8303eeb0a |
| 6.2.5 | 5b23262cb4b15230e262005b648aff0d | 85ec7457b36de4402ce2c4b591fa87ab |
| 6.2.4 | f61648cd99d94c05d50a6e3213329779 | 3b20d45695f5e196e78d3db6c2bd738d |
| 6.2.3 | 51eaa0654ec83db7da31511092312f00 | d540bdc543a06ff5ccd40f90b2078557 |
| 6.2.2 | 9e5ceb08a3121f42b3315da87c698af3 | 08917804e4fe48bcb797f391d5a111f6 |
| 6.2.1 | cbfe915e31bc06bb28227cb33ed22304 | abfa9d9dc81fd90b0ca65de973fb1ab8 |
| 6.2.0 | 652ee1362af8c93119335a337deba1a5 | 91bb64493b344b010ebc277c849e9234 |
| 6.1.4 | 7e2e74d3cc186807d73c1fcf57f8b117 | 6c9b4ed760c9c1139681f61e6a508c8e |
| 6.1.3 | 749e6c3de91afdfcddec91d290c46807 | ab5884cb0c1ea00c3b3fe9a1d26a4511 |
| 6.1.2 | 940da06a6f8f7e3931a2a80f4e8defc9 | 4d39c9e6d46c49b5bde2c5ff19781957 |
| 6.1.1 | 7d259bd1cc5e5d2c3fea4909953375ba | 09a273cf0300656ed995405e41eced58 |
| 6.1.0 | e95e509d48e7b87e0213c7f12ea253e4 | 2c87f3a79c9318a4ed49ad8c377b007f |
| 6.0.8 | d903e6c145492488e126e46b3a233444 | 3237e91d12ee0871ceb0f6a0829dd43b |
| 6.0.7 | 2d83f856d8d34c4f2e0e4e8561ddee05 | bbb742ded1e49eae0622deb40c3becc3 |
| 6.0.6 | 1dd3bfc9919db8ccb7c0de8cf6505d47 | 5d5e5fe1624123f8316c6bdc020aa47b |
| 6.0.5 | e8afac7ef0bc7e38432bf5187fcbde7d | 41966239e783ce0bbba852471a439caa |
| 6.0.4 | a88278fdb8c2f504ecb4406b8fbc1fe4 | a7bba01c6484baf721f5be51242c492b |
| 6.0.3 | 9f0cfed3c889ba3e334857c6d81e26be | 13b07e2da8316759a8f84efb2476e854 |
| 6.0.2 |  | 13936cb4e05221e134ae1539971b9317 |
| 6.0.1 beta |  | 6167276b56ac3b1fbdad2a4858b17bf3 |

</Accordion>

<div id="v5-checksums" />

<Accordion title="Tổng kiểm tra V5">

| Phiên bản SDK iOS | Static Lib | Static Framework |
| --- | --- | --- |
| 5.4.4 | 47d90cbc4ed48dd1c5d6f42a8d419e8b | 93716e13258fce87c81c0fc604bfd6fd |
| 5.4.3 | e5691c3ae1f20726168b4eb221937d98 | dbfa30607f44fa2819191c7a8d7a3fe4 |
| 5.4.1 | 61564250f26ab0693255e002873d1674 | fc86776f0ffcdf65cc49f33f7d943258 |
| 5.4.0 | fa835b3577f389a12ef635eea0b000bb | 0bd6a7b4441dc8f397831533e719a833 |
| 5.3.0 | e787da7334e6c68e0098fd53ebea285e | 2f160176b1c011f9aca558543cd63190 |
| 5.2.0 | 057c18bb7485e1c06f2b452d80ee5b22 | 736b50840b8c08093401f3bba2c4389b |
| 5.1.0 | f39819c11b06f98ff24e39cbd0f0f6ce | 39889a253dafcfb2d53151523c1c1d80 |
| 5.0.0 | 5ac9e35af65fbfcaf81c1f63a36542b9 | 1727be9fa19906f0c1e1907b4b160086 |

</Accordion>

<div id="v4-checksums" />

<Accordion title="Tổng kiểm tra V4">

| Phiên bản SDK iOS | Static Lib | Static Framework |
| --- | --- | --- |
| 4.11.2 | f5415c2014402a03b8ca2c9901ddf12d | 3fcf5afd6a20f353f7f88f1fbb4d4410 |
| 4.11.1 | 716394142df4d8e7a98e2c11cfe92ed1 | e6521d8216d3aa8d681ac74e279dab34 |
| 4.11.0 | e7238410372dfa7ca65e5839a31b1c2e | c6d3283bf69adb75aa9ed6c43195a3d6 |
| 4.10.0 | 4d5c01129b80d7ad182e32cf3b47faa4 | da926eeb09d61f68f2076a9b31c30d7a |
| 4.9.0 | d283ace3237479d1aabc2a81271ea5ba | bad6d9b8c627d7450e7acc8165b05618 |
| 4.8.9 | e9640a7f95257a89c3e99215df79f1df | fb0975064d2b93cedb71ce248cf3afb9 |
| 4.8.4 | b7748ea6b86afbc295e17bac3d5bdda6 | 4cd7a95f49cfb79ecd9a0ce0c73750a3 |
| 4.8.3 | 51d38c4b77f39c75c5fc5734165fedc2 | 23096a32726a9def3e215a761bf7ad30 |
| 4.8.2 | 0908336d4e9bcf4de1d5f4f2e37ad0cb | a386cfadd76fd783e6a10d0cd8fcb685 |
| 4.8.1 |  | 3b8a7d70b96bd7c5718feafeb31296b9 |
| 4.8.0 | bb1358226bd3ca70d70f4717b62ca38b | 3d81144bb653e91cb624778c87641051 |
| 4.7.9 | e9183f23954a3f42a9fa6ae3eeebb6df | 03905309048e26e9be7ee02895532d11 |
| 4.7.8 | 5595fa7dfc4c13b4a955638ba1da062e | 61c30629f3dcb5ae48da10a458e80d28 |
| 4.7.7 | 3a8d0be3b304de5e81c967ab8a465de3 | b8dd0ee60c75aa30884f56569068f32e |
| 4.7.6 | 6cc80a31cf9daae5709a22258f434c6d | 3d4607b13b6f138264db703e36f5452e |
| 4.7.3 | 73db4e0173fcfdb758644b08fdbbd7bf | 06572392afe0ae28a814601642963469 |
| 4.7.2 | 14a79e4ecffad264bc62b307d2db23a7 | 0aae1d0ace09e5b092f9906747119cfd |
| 4.7.11 | 27e228c921f560205c0ad2c7962e83b2 | d94cdab5734a88598cfcc078573e5b21 |
| 4.7.10 | 5cb1275b488369fee4713d21812186a0 |  |
| 4.7.1 | b121dfdf8d0dc53d031481114eba0c18 | 74ac06d17f167a0e22c361e06f4a2554 |
| 4.7.0 | c3c0a453caa9971492ef8acd8bee04ae | cadeab0479c4a723173943d77d253051 |

</Accordion>

<div id="see-also" />

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/about-att-and-skan">Hướng dẫn bắt đầu nhanh về iOS 14, ATT và SKAdNetwork</Anchor>

<div data-zendesk-anchors="ios-sdk-v6=sdk-ios-v6 01H8W3DDM1BYRSPMFTA3TCY8EQ=sdk-ios-v6 01EEYC8A6FEW8WN28KQ9CKX0G7=ios-v600-release-notes methods-added-removed-or-renamed=c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-%C4%91%C6%B0%E1%BB%A3c-th%C3%AAm-lo%E1%BA%A1i-b%E1%BB%8F-ho%E1%BA%B7c-%C4%91%E1%BB%95i-t%C3%AAn 01EEYC8A6FD7JZK1A63EF675HJ=c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-%C4%91%C6%B0%E1%BB%A3c-th%C3%AAm-lo%E1%BA%A1i-b%E1%BB%8F-ho%E1%BA%B7c-%C4%91%E1%BB%95i-t%C3%AAn methods-added=c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-%C4%91%C6%B0%E1%BB%A3c-th%C3%AAm-v%C3%A0o 01EEYC8A6FKPYQ35EKVW7X0EC0=c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-%C4%91%C6%B0%E1%BB%A3c-th%C3%AAm-v%C3%A0o methods-removed=ph%C6%B0%C6%A1ng-th%E1%BB%A9c-b%E1%BB%8B-lo%E1%BA%A1i-b%E1%BB%8F 01EEYC8A6FNJ91R15X633BHSXF=ph%C6%B0%C6%A1ng-th%E1%BB%A9c-b%E1%BB%8B-lo%E1%BA%A1i-b%E1%BB%8F methods-renamed=c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-%C4%91%C3%A3-%C4%91%E1%BB%95i-t%C3%AAn 01EEYC8A6F8PB4C94Z14KXYD68=c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-%C4%91%C3%A3-%C4%91%E1%BB%95i-t%C3%AAn app-tracking-transparency-att-support=h%E1%BB%97-tr%E1%BB%A3-app-tracking-transparency-att 01EEYC8A6G19ER7FGWQ51XPGJF=h%E1%BB%97-tr%E1%BB%A3-app-tracking-transparency-att ios-sdk-v5=sdk-ios-v5 01EEYC8A6GYYRK4F7CVT7YMTHJ=sdk-ios-v5 01H8W3DDM19M6R8AV62WKZ931G=ios-sdk-v5::7a4821ba 01EEYC8A6GR18M6KN5D2ZV2573=ios-v500-release-notes improved-sdk-response-time=c%E1%BA%A3i-thi%E1%BB%87n-th%E1%BB%9Di-gian-ph%E1%BA%A3n-h%E1%BB%93i-sdk 01EEYC8A6GF3MF7GJZWCE9TY88=c%E1%BA%A3i-thi%E1%BB%87n-th%E1%BB%9Di-gian-ph%E1%BA%A3n-h%E1%BB%93i-sdk methods-removed-or-renamed=c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-%C4%91%C3%A3-b%E1%BB%8B-x%C3%B3a-ho%E1%BA%B7c-%C4%91%E1%BB%95i-t%C3%AAn 01EEYC8A6G3KWSZ3FGKF904QM1=c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-%C4%91%C3%A3-b%E1%BB%8B-x%C3%B3a-ho%E1%BA%B7c-%C4%91%E1%BB%95i-t%C3%AAn method-name-changes=thay-%C4%91%E1%BB%95i-t%C3%AAn-ph%C6%B0%C6%A1ng-th%E1%BB%A9c 01EEYC8A6G1EFHXBMW229RTKYA=thay-%C4%91%E1%BB%95i-t%C3%AAn-ph%C6%B0%C6%A1ng-th%E1%BB%A9c methods-removed::92ba13cc=ph%C6%B0%C6%A1ng-th%E1%BB%A9c-b%E1%BB%8B-lo%E1%BA%A1i-b%E1%BB%8F-1 01EEYC8A6GE57XWGHTNQSAN516=ph%C6%B0%C6%A1ng-th%E1%BB%A9c-b%E1%BB%8B-lo%E1%BA%A1i-b%E1%BB%8F-1 changes-to-get-conversion-data-format=thay-%C4%91%E1%BB%95i-%C4%91%E1%BB%83-nh%E1%BA%ADn-%C4%91%E1%BB%8Bnh-d%E1%BA%A1ng-d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i 01EEYC8A6HVPFA5K349KHT5B3T=thay-%C4%91%E1%BB%95i-%C4%91%E1%BB%83-nh%E1%BA%ADn-%C4%91%E1%BB%8Bnh-d%E1%BA%A1ng-d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i 01EEYC8A6HG072RP472KEQ74S8=v%C3%AD-d%E1%BB%A5 01H8W3DDM1G62RTK2S3XEG3KGT=deprecated-versions ios-sdk-checksums=t%E1%BB%95ng-ki%E1%BB%83m-tra-sdk-ios 01EEYC8A6J6VF2WEPFEC9JRVA9=t%E1%BB%95ng-ki%E1%BB%83m-tra-sdk-ios 01EEYC8A6J77PYMCNDEGWZD3FJ=v6-checksums 01EEYC8A6JGHWTNJY0C06PD7H6=v4-checksums h_01HE7RE2EPQX872DKNDBJ2G2QE=xem-th%C3%AAm" />
