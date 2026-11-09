---
title: Hướng dẫn tích hợp SDK cơ bản
metadata:
  keywords:
    - sdk
    - iOS
    - Android
    - Integration
    - Advertisers
    - appuid
    - anonymous
    - kakao
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2013-08-22T16:09:08Z'
  edited_at: '2023-03-26T11:44:05Z'
  id: 207032066
  locale: vi
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/vi/articles/207032066
---
> **Khái quát:** Làm việc với nhà phát triển ứng dụng di động hoặc ứng dụng CTV của bạn để tích hợp và cài đặt SDK vào các ứng dụng Android hoặc iOS. Sau khi các tác vụ tích hợp cơ bản hoàn tất, ứng dụng của bạn đã sẵn sàng cho việc phân bổ lượt cài đặt và đo lường sự kiện trong ứng dụng.

> 📘 **Bài đọc liên quan**
>
> Để nắm rõ đầy đủ về việc lập kế hoạch tích hợp SDK với ứng dụng của bạn, hãy nhớ đọc các bài viết sau:
>
> * <Anchor target="_blank" href="/marketers/vi/docs/sdk-integration-overview">Tổng quan về tích hợp SDK</Anchor>
> * **Tích hợp SDK cơ bản (bài viết này)**
> * <Anchor target="_blank" href="/marketers/vi/docs/additional-sdk-integration-guide">Tích hợp SDK bổ sung</Anchor>
> * <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts">Tổng quan về TV được kết nối (CTV) và over-the-top (OTT)</Anchor>

<div id="starting-the-sdk-in-react" />

<div id="starting-the-sdk-in-Unity" />

<div id="starting-the-sdk-in-ios" />

<div id="select-your-privacy-preserving-strategy" />

<div id="starting-the-sdk-in-react-native" />

<div id="starting-the-sdk-in-unity" />

<div id="ios-developer-instructions" />

<div id="delay-the-sdk-start-in-ios" />

<div id="starting-the-sdk-in-ios-native" />

<div id="android-developer-instructions" />

<div id="select-in-what-class-to-start-the-sdk" />

<div id="starting-the-sdk-in-android-native" />

<div id="where-to-start-the-sdk" />

<div id="provide-the-dev-key-to-your-developer" />

<div id="retrieve-the-dev-key" />

<div id="implementing-the-dev-key-in-your-app" />

## Truy xuất dev key

Trước khi nhà phát triển của bạn có thể cài đặt và tích hợp SDK, bạn phải truy xuất dev key. AppsFlyer sử dụng dev key để xác định duy nhất tài khoản của bạn. Dev key là bắt buộc vì nó cho phép SDK gửi và truy xuất an toàn dữ liệu thuộc tài khoản của bạn.

**Để lấy khóa dev của bạn:**

1. Trong AppsFlyer, đi tới **Configuration** (Cấu hình) > **App Settings** (Cài đặt của Ứng dụng).
2. Sao chép dev key và gửi cho nhà phát triển ứng dụng thiết bị di động của bạn.

   <Image align="center" alt="af_devkey.png" src="https://files.readme.io/5078fdabbcce4d3977f3d32351b61bacbc8af406a68911f2c6b4cdca458712a5-30603573703057.png" />
3. Cung cấp cho nhà phát triển thiết bị di động các hướng dẫn <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">cài đặt</Anchor> và <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-integration">tích hợp SDK</Anchor>.

<div id="attribution" />

## Phân bổ

SDK thu thập các số <Anchor target="_blank" href="/marketers/vi/docs/about-device-identifiers">mã định danh</Anchor> cho các mục đích phân bổ. Để đảm bảo rằng số lượt cài đặt được ghi nhận và phân bổ chính xác, hãy xem lại và làm theo các nguyên tắc này.

**Tất cả các nền tảng**

<div id="unique-identifier-for-installs" />

<Accordion title="Mã định danh duy nhất cho lượt cài đặt">

ID AppsFlyer được tạo tự động cho mỗi lượt cài đặt ứng dụng mới. Nhà tiếp thị không cần phải thực hiện bất kỳ hành động nào.

Bạn có thể sử dụng mã định danh này để thực hiện các hoạt động sau:

* Gửi <Anchor target="_blank" href="/marketers/vi/docs/server-to-server-events-api-for-mobile-s2s-mobile">các sự kiện trong ứng dụng server-to-server</Anchor> .
* So khớp ID AppsFlyer với hồ sơ người dùng trong các hệ thống backend của bạn.
* Tải xuống <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">báo cáo dữ liệu thô sự kiện trong ứng dụng</Anchor> và sử dụng **appsflyer\_id** để phân tích hành vi và hành trình của người dùng.

</Accordion>

<div id="integrate-unique-identifiers-from-your-bi-system-with-appsflyer" />

<Accordion title="Tích hợp mã định danh duy nhất từ hệ thống BI của bạn với AppsFlyer">

Đặt Customer user ID (CUID) của riêng bạn trong SDK AppsFlyer để tham chiếu chéo ID duy nhất từ hệ thống BI với ID AppsFlyer và các mã định danh khác. CUID có sẵn trong các báo cáo <Anchor target="_blank" href="/marketers/vi/docs/raw-data-field-dictionary">dữ liệu thô</Anchor> của AppsFlyer. Bạn cũng có thể sử dụng CUID này trong API postback để tham chiếu chéo với ID nội bộ của bạn.

Xem <Anchor target="_blank" href="/marketers/vi/docs/customer-user-id-field-cuid#cài-đặt-cuid">hướng dẫn triển khai CUID dành cho nhà phát triển.</Anchor>

</Accordion>

**Chỉ dành cho Android**

Các phần sau đây mô tả những vấn đề cần lưu ý về phân bổ đối với Cửa hàng Google Play hoặc các cửa hàng ứng dụng của bên thứ ba.

<div id="attribute-apps-published-on-google-play" />

<Accordion title="Các ứng dụng phân bổ được xuất bản trên Google Play">

<div id="google-play-install-referrer" />

#### **Người giới thiệu Cài đặt Google Play**

<Anchor target="_blank" href="https://developer.android.com/google/play/installreferrer">API của Người giới thiệu Cài đặt Google Play</Anchor> giúp cải thiện độ chính xác của <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#phương-thức-phân-bổ">phân bổ</Anchor>, bảo vệ khỏi bị gian lận lượt cài đặt và cho phép truy xuất an toàn dữ liệu lượt giới thiệu từ Google Play (ví dụ: phiên bản của ứng dụng tại thời điểm ứng dụng được cài đặt lần đầu).

Bạn nên cung cấp cho nhà phát triển của mình <Anchor target="_blank" href="https://developer.android.com/google/play/installreferrer/library">các hướng dẫn này để thêm API của Người giới thiệu Cài đặt Google Play</Anchor>.

#### **GAID**

Kể từ phiên bản SDK V4.8.0, AppsFlyer sẽ tự động thu thập mã nhận dạng thiết bị này.

</Accordion>

<div id="attribute-apps-in-thirdparty-app-stores" />

<Accordion title="Phân bổ ứng dụng trong cửa hàng ứng dụng của bên thứ ba">

Với AppsFlyer, bạn có thể <Anchor target="_blank" href="/marketers/vi/docs/set-up-multi-store-android-attribution">phân bổ lượt cài đặt bắt nguồn từ các cửa hàng ứng dụng của bên thứ ba</Anchor>, chẳng hạn như Amazon, Opera, GetJar, Baidu và Huawei. Điều này cho phép bạn quảng bá ứng dụng của mình và tiếp cận đối tượng lớn hơn ở các thị trường không có Google Play Store.

AppsFlyer hỗ trợ phân bổ trong trường hợp cửa hàng ứng dụng của bên thứ ba như sau:

* **IMEI hoặc ID Android:** SDK không tự động thu thập IMEI hoặc ID Android. Tuy nhiên, nếu có nhu cầu thu thập các mã định danh này (ví dụ: đối với <Anchor target="_blank" href="/marketers/vi/docs/measure-attribution-in-the-chinese-domestic-market#attribution-android-apps-in-the-chinese-domestic-market">các ứng dụng ở thị trường nội địa Trung Quốc</Anchor>) thì nhà phát triển của bạn có thể triển khai một trong các hình thức thu thập sau:
  * Thu thập thủ công: Các ứng dụng chuyển IMEI hoặc ID Android đến SDK (sử dụng [`setImeiData`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setimeidata) hoặc API<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setandroididdata">`setAndroidIdData`</Anchor>) . SDK gửi dữ liệu đến máy chủ AppsFlyer.
  * Chọn tham gia thu thập ID thiết bị: Buộc SDK thu thập <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectimei">IMEI</Anchor> hoặc <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectandroidid">ID Android</Anchor>.
* **OAID:** Phân bổ lượt cài đặt từ các cửa hàng ứng dụng Android của bên thứ ba. Để biết thêm thông tin, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/android-oaid-implementation-in-the-sdk">hướng dẫn triển khai OAID</Anchor>.
* **Người giới thiệu cài đặt:** SDK hỗ trợ truy xuất dữ liệu giới thiệu từ Samsung Gallery và Huawei AppGallery.

</Accordion>

**Chỉ dành cho iOS**

Các phần sau đây đề cập những thông tin quan trọng về hỗ trợ cho các thiết bị iOS 14+.

<div id="configure-app-tracking-transparency-att-support" />

<Accordion title="Hỗ trợ Định cấu hình Minh bạch về Theo dõi Ứng dụng (ATT)">

#### **Thông tin cơ bản**

Kể từ phiên bản iOS 14.5, chức năng thu thập IDFA yêu cầu phải có sự đồng ý của người dùng. Trên thực tế, điều đó có nghĩa là quyền truy cập IDFA được điều chỉnh bởi khung <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency">**Minh bạch về Theo dõi Ứng dụng**</Anchor> (ATT). Trên thiết bị iOS từ phiên bản 14 trở lên, SDK sử dụng khung ATT để được quyền truy cập vào IDFA của thiết bị.

Để biết thông tin giới thiệu về ATT, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/about-att-and-skan#att-principles">các nguyên tắc về ATT</Anchor> .

Khi phân bổ xảy ra bằng cách sử dụng IDFA, quan trọng là IDFA phải được gửi vào **lần khởi chạy đầu tiên.** Vì lý do này, SDK cung cấp tiện ích <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support">waitForATTUserAuthorization</Anchor>.

<div id="waitforattuserauthorization-overview" />

#### **Tổng quan về waitForATTUserAuthorization**

<div id="important" />

> ❗️ **Quan trọng!**
>
> Không gọi ra `waitForATTUserAuthorization` nếu bạn không có ý định gọi ra lời nhắc ATT.

`waitForATTUserAuthorization` cho phép bạn định cấu hình thời gian SDK sẽ trì hoãn và chờ trạng thái ATT trước khi gửi dữ liệu đến máy chủ AppsFlyer.

<Image align="center" alt="ATT-flowchart_en-us.png" src="https://files.readme.io/a41e66c5aa23d2c673aba5b06589dcc24d34175e90900a8232343272ecca427c-30603573710993.png" />

Khi người dùng khởi chạy ứng dụng, trạng thái ATT là **notDetermined.** Trong thời gian chờ `waitForATTUserAuthorization`, SDK sẽ tạo hàng đợi sự kiện khởi chạy và các sự kiện trong ứng dụng liên tiếp trong bộ nhớ, tương tự như cách <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#offline-in-app-events">ghi nhận các sự kiện ngoại tuyến</Anchor>:

* Nếu người dùng **đồng ý** với lời nhắc ATT (Thu thập IDFA):
  * SDK sẽ thêm IDFA vào các sự kiện được lưu trong bộ nhớ tạm.
  * SDK bắt đầu và gửi các sự kiện được lưu trong bộ nhớ tạm kèm theo IDFA (mà không cần đợi hết thời gian chờ).
* Nếu người dùng **từ chối** lời nhắc ATT: SDK bắt đầu và gửi các sự kiện được lưu trong bộ nhớ đệm mà không kèm IDFA (mà không cần đợi hết thời gian chờ).
* Nếu thời gian chờ kết thúc và trạng thái ATT vẫn là **notDetermined:** SDK sẽ bắt đầu và gửi các sự kiện đã lưu trong bộ nhớ đệm mà không kèm theo IDFA.

**Những điều cần lưu ý**

* Việc gọi ra <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/3547037-requesttrackingauthorization">`requestTrackingAuthorization`</Anchor> mà không cài đặt `waitForATTUserAuthorization` sẽ dẫn đến việc khởi chạy và gửi sự kiện mà không kèm theo IDFA đối với thiết bị iOS từ phiên bản 14 trở lên.
* Nếu người dùng chuyển ứng dụng sang chạy ngầm trong thời gian chờ:
  * Bộ định thời tạm dừng cho đến khi ứng dụng quay trở lại chế độ chạy nổi.
  * Sự kiện được lưu vào bộ nhớ tạm.
* Nếu người dùng tắt ứng dụng, ứng dụng sẽ tắt hẳn trong thời gian chờ:
  * Bộ định thời được khởi động lại vào lần khởi chạy ứng dụng tiếp theo.
  * Sự kiện được lưu vào bộ nhớ tạm sẽ bị mất.

</Accordion>

<div id="customize-att-consent-dialog" />

<Accordion title="Tùy chỉnh hộp thoại đồng ý ATT">

Bạn có thể tùy chỉnh lời nhắc ATT. Thông báo nêu rõ mục đích của yêu cầu có thể giúp tăng tỷ lệ người dùng chọn đồng ý.

Hãy cem xét những điều sau khi tạo tin nhắn:

* Sử dụng từ ngữ giải thích tốt nhất cho người dùng của bạn về lý do ứng dụng yêu cầu sự đồng ý của người dùng.
* Thông báo cho người dùng về cách dữ liệu của họ sẽ được sử dụng. <Anchor target="_blank" href="https://developer.apple.com/app-store/user-privacy-and-data-use/">Tìm hiểu thêm về quyền riêng tư của người dùng và sử dụng dữ liệu.</Anchor>

Sau khi thông báo đã hoàn tất, hãy cung cấp cho nhà phát triển ứng dụng của bạn văn bản và <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#customizing-the-att-consent-dialog">hướng dẫn triển khai</Anchor>.

[Xem một số ví dụ bên ngoài về lời nhắc ATT.](https://www.attprompts.com/)

</Accordion>

<div id="support-for-skan-attribution" />

<Accordion title="Hỗ trợ phân bổ SKAN">

<div id="note" />

> 📘 **Lưu ý**
>
> Để hỗ trợ đầy đủ tính năng phân bổ SKAN, hãy nâng cấp lên SDK iOS V6.2.3+.

SKAN là một lớp được iOS sử dụng để xác thực các lượt cài đặt ứng dụng do nhà quảng cáo thúc đẩy. Quy trình xác thực lượt cài đặt ứng dụng liên quan đến ứng dụng nguồn và ứng dụng được quảng cáo. 

Ứng dụng nguồn là một ứng dụng tham gia vào các chiến dịch quảng cáo bằng cách hiển thị quảng cáo từ một mạng quảng cáo. Việc cấu hình ứng dụng của bạn để hiển thị quảng cáo không nằm trong phạm vi của SDK AppsFlyer. Để cấu hình, hãy làm theo <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app">hướng dẫn của Apple</Anchor>.

Đối với ứng dụng được quảng cáo (ứng dụng có SDK AppsFlyer), <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide">Giải pháp SKAN</Anchor> của AppsFlyer sử dụng SKAN để cung cấp tính năng đăng lại phân bổ trong khi AppsFlyer thu thập, dịch và tổng hợp dữ liệu, đồng thời duy trì quyền riêng tư của người dùng. Khi ứng dụng được khởi chạy lần đầu tiên, nền tảng AppsFlyer sử dụng cấu hình do nhà tiếp thị cài đặt để hướng dẫn SDK về cách cài đặt giá trị chuyển đổi SKAN.

Để sử dụng giải pháp SKAN:

* Nhà tiếp thị cần cấu hình đo lường SKAN trong AppsFlyer. Nhà phát triển không phải thực hiện bất kỳ công việc nào.
* SDK AppsFlyer tự động gọi ra các API SKAN cần thiết.
* Đảm bảo vô hiệu các lệnh gọi SKAN trong các SDK khác nếu bạn sử dụng AppsFlyer để phân bổ SKAN.
* Không yêu cầu nhà phát triển hoặc nhà tiếp thị phải có hành động hoặc quy trình đăng ký nào khác trong App Store.

Để tắt tính năng phân bổ SKAN, hãy hướng dẫn nhà phát triển của bạn <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableskadnetwork">tắt các lệnh gọi này trong SDK</Anchor>.

</Accordion>

<div id="recording-in-app-events" />

## Ghi nhận sự kiện trong ứng dụng

Các sự kiện trong ứng dụng (IAE) cung cấp thông tin chi tiết về những gì đang xảy ra trong ứng dụng của bạn. Việc ghi nhận sự kiện trong ứng dụng giúp bạn đo lường các giá trị KPI như Lợi tức đầu tư (ROI) và Giá trị vòng đời (LTV). Bạn nên dành thời gian xác định các sự kiện bạn muốn ghi nhận.

Sau khi đã xác định các sự kiện trong ứng dụng bạn muốn đo lường, hãy gửi tên sự kiện và tham số cho nhà phát triển ứng dụng và kèm theo một đường dẫn liên kết đến <Anchor target="_blank" href="http://dev.appsflyer.com/hc/docs/in-app-events-sdk">hướng dẫn triển khai</Anchor>.

Để tìm hiểu thêm về các sự kiện trong ứng dụng, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview">hướng dẫn Sự kiện phong phú trong ứng dụng</Anchor> của chúng tôi.

**Tất cả các nền tảng**

<div id="record-revenue" />

<Accordion title="Ghi nhận doanh thu">

Bạn có thể gửi doanh thu với bất kỳ sự kiện trong ứng dụng. Đảm bảo bạn sử dụng thông số **af\_revenue** để bao gồm doanh thu. Đây là thông số sự kiện duy nhất mà AppsFlyer tính là doanh thu thực trên bảng điều khiển và trong báo cáo dữ liệu thô. <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#revenue-events">Tìm hiểu thêm</Anchor>.

Để biết hướng dẫn dành cho nhà phát triển, hãy xem <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-android#logging-revenue">ghi lại doanh thu</Anchor>.

</Accordion>

<div id="validate-inapp-purchases" />

<Accordion title="Xác thực mua hàng trong ứng dụng">

SDK của AppsFlyer cung cấp xác minh máy chủ cho các giao dịch mua trong ứng dụng. Xác thực mua hàng trong ứng dụng sẽ tự động gửi một sự kiện mua trong ứng dụng tới AppsFlyer. Tự gửi sự kiện này tạo ra báo cáo sự kiện trùng lặp.

</Accordion>

<div id="industry-verticals" />

<Accordion title="Các ngành dọc">

<Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#recommended-events-by-business-vertical">Xem danh sách các sự kiện trong ứng dụng được đề xuất</Anchor> theo ngành, ví dụ, du lịch, trò chơi hoặc Thương mại điện tử.

</Accordion>

<div id="deep-linking-with-onelink" />

## Liên kết sâu với OneLink

OneLink là giải pháp của AppsFlyer để phân bổ đa nền tảng, **chuyển hướng và liên kết sâu**.

**Tất cả các nền tảng**

<div id="device-detection-and-redirection" />

<Accordion title="Nhận diện và chuyển hướng thiết bị">

Đối với người dùng chưa cài đặt ứng dụng của bạn, OneLink sẽ phát hiện loại thiết bị và chuyển hướng họ đến đích chính xác (ví dụ: Google Play, Apple App Store, cửa hàng ứng dụng của bên thứ ba hoặc trang web). Điều này dựa vào cài đặt mẫu OneLink của bạn. <Anchor target="_blank" href="/marketers/vi/docs/create-a-onelink-template">Tìm hiểu thêm</Anchor>

</Accordion>

<div id="deep-linking" />

<Accordion title="Deep Linking">

Đối với người dùng đã cài đặt ứng dụng của bạn, OneLink sẽ mở ứng dụng. Ngoài việc mở ứng dụng, bạn cũng có thể liên kết sâu người dùng với một hoạt động hoặc trang cụ thể trong ứng dụng. Điều này yêu cầu nhà phát triển của bạn triển khai <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl-1">Liên kết sâu hợp nhất (UDL)</Anchor>.

**Lưu ý**:

* UDL yêu cầu SDK V6.1+.
* Những khách hàng đã sử dụng OneLink để liên kết sâu có thể đang sử dụng <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-legacy-apis">phương thức kế thừa</Anchor>, thay vì UDL.

Xem hướng dẫn của chúng tôi về thiết lập liên kết sâu với OneLink.

</Accordion>

<div id="deferred-deep-linking" />

<Accordion title="Deferred deep linking">

Đối với người dùng chưa cài đặt ứng dụng của bạn, OneLink sẽ nhận diện loại thiết bị và chuyển hướng họ đến điểm đích chính xác: Google Play, Apple App Store, cửa hàng ứng dụng của bên thứ ba hoặc trang web. Sau khi người dùng khởi chạy ứng dụng, bạn có thể sử dụng liên kết sâu gián tiếp để chuyển hướng họ đến một hoạt động hoặc trang cụ thể trong ứng dụng.

Điều này yêu cầu nhà phát triển của bạn triển khai <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl-1">Liên kết sâu hợp nhất (UDL)</Anchor>.

**Lưu ý**:

* UDL yêu cầu SDK V6.1+.
* Những khách hàng đã sử dụng OneLink để liên kết sâu gián tiếp có thể đang sử dụng <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-legacy-apis#deferred-deep-linking">phương thức kế thừa</Anchor>, thay vì UDL

Xem hướng dẫn của chúng tôi về cách thiết lập deferred deep linking bằng OneLink.

</Accordion>

<div id="tip" />

<div id="accessing-attribution-and-deep-linking-data" />

## Truy cập dữ liệu phân bổ và liên kết sâu

Bảng sau mô tả các phương thức có sẵn để truy xuất dữ liệu phân bổ và liên kết sâu:

| Phương thức | Đối tượng tham gia là ai? | Trả về kết quả | Phương thức truy xuất | Dữ liệu phân bổ | Dữ liệu liên kết sâu | Tính khả dụng |
| --- | --- | --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/vi/docs/push-api-streaming-raw-data">**API Push**</Anchor> | <ul><li>Nhà tiếp thị</li><li>Nhà phát triển back-end</li></ul> | Thông thường trong vòng vài phút | Backend | Y | N | Cao cấp |
| **<Anchor target="_blank" href="/marketers/vi/docs/pull-api-raw-data">API Pull</Anchor>** | <ul><li>Nhà tiếp thị</li><li>Nhà phát triển back-end</li></ul> | <ul><li>Định kỳ (không theo thời gian thực).</li><li>Bạn có thể lên lịch tải xuống báo cáo dữ liệu thô.</li></ul> | Backend | Y | Y | Tính năng cao cấp cho các báo cáo dữ liệu thô |
| <Anchor target="_blank" href="/marketers/vi/docs/data-locker-for-marketers">**Data Locker**</Anchor> | <ul><li>Nhà tiếp thị</li><li>Nhà phát triển back-end</li></ul> | Báo cáo theo giờ có sẵn trong vòng 1 - 3 giờ | Lưu trữ đám mây thông qua một trong các tùy chọn sau:<ul><li>Bộ chứa do AppsFlyer sở hữu trên AWS</li><li>Bộ nhớ do bạn sở hữu (AWS hoặc GCS)</li></ul> | Y | Y | Cao cấp |
| <Anchor target="_blank" href="/marketers/vi/docs/conversion-data-payloads-and-scenarios#tổng-quan">**Nhận dữ liệu chuyển đổi (GCD)**</Anchor> | <ul><li>Nhà tiếp thị</li><li>Nhà phát triển ứng dụng di động</li></ul><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">Xem tài liệu dành cho nhà phát triển</Anchor> | Tối đa 5 giây | SDK | Y | Y | Tất cả các tài khoản |
| **<Anchor target="_blank" href="/marketers/vi/docs/create-a-onelink-template">Liên kết Sâu Hợp nhất (UDL)</Anchor>** | <ul><li>Nhà tiếp thị</li><li>Nhà phát triển ứng dụng di động</li></ul><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl">Xem tài liệu dành cho nhà phát triển</Anchor> | Tối đa 1 giây | SDK | N | Y | Tất cả các tài khoản |

Lưu ý những điều sau đối với người dùng iOS 14.5+ không đồng ý:

* Khi sử dụng UDL cho truyền thông có trả phí và được sở hữu, bạn sẽ có dữ liệu liên kết sâu.
* Khi sử dụng GCD cho truyền thông trả phí, dữ liệu sẽ bị hạn chế và không bao gồm thông tin chi tiết về phân bổ và liên kết sâu.

> 👍 **Lời khuyên**
>
> Chúng tôi đề xuất những điều sau:
>
> * Sử dụng API Push khi truy xuất dữ liệu phân bổ và gửi đến máy chủ của bạn để xử lý thêm. Phương thức này sẽ chờ khi có dữ liệu và do đó có độ chính xác cao và gần với theo thời gian thực. GCD trả về dữ liệu theo thời gian thực, nhưng có thể không chính xác khi các quyết định phân bổ cuối cùng được xác định sau hơn 5 giây.
> * Sử dụng API Pull để bổ sung định kỳ (ví dụ: hàng ngày) dữ liệu phân bổ theo thời gian thực và để bù cho bất kỳ lỗi giao tiếp nào có thể xảy ra.

<div id="note-1" />

<div id="testing-your-sdk-integration" />

## Kiểm tra tích hợp SDK

Sau khi quá trình tích hợp SDK hoàn tất, bạn có thể truy cập bảng điều khiển AppsFlyer và từ trang Thử nghiệm Tích hợp SDK, hãy thử nghiệm lượt cài đặt tự nhiên và không tự nhiên, sự kiện trong ứng dụng và liên kết sâu (nhắm mục tiêu lại). Điều này đảm bảo rằng các lượt cài đặt và sự kiện trong ứng dụng được ghi nhận và phân bổ một cách chính xác.

Nếu bạn cần nhà phát triển thử nghiệm tích hợp SDK, hãy thêm nhà phát triển làm <Anchor target="_blank" href="/marketers/vi/docs/user-management">người dùng</Anchor> trong tài khoản để họ có thể truy cập bảng điều khiển. 

Để biết các hướng dẫn và tình huống thử nghiệm, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/testing-the-sdk-integration-for-marketers">thử nghiệm tích hợp SDK</Anchor>.

<div data-zendesk-anchors="retrieving-the-dev-key=truy-xu%E1%BA%A5t-dev-key attribution=ph%C3%A2n-b%E1%BB%95 google-play-install-referrer=ng%C6%B0%E1%BB%9Di-gi%E1%BB%9Bi-thi%E1%BB%87u-c%C3%A0i-%C4%91%E1%BA%B7t-google-play background=th%C3%B4ng-tin-c%C6%A1-b%E1%BA%A3n waitforattuserauthorization-overview=t%E1%BB%95ng-quan-v%E1%BB%81-waitforattuserauthorization recording-inapp-events=ghi-nh%E1%BA%ADn-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng deep-linking-with-onelink=li%C3%AAn-k%E1%BA%BFt-s%C3%A2u-v%E1%BB%9Bi-onelink accessing-attribution-and-deep-linking-data=truy-c%E1%BA%ADp-d%E1%BB%AF-li%E1%BB%87u-ph%C3%A2n-b%E1%BB%95-v%C3%A0-li%C3%AAn-k%E1%BA%BFt-s%C3%A2u testing-your-sdk-integration=ki%E1%BB%83m-tra-t%C3%ADch-h%E1%BB%A3p-sdk" />
