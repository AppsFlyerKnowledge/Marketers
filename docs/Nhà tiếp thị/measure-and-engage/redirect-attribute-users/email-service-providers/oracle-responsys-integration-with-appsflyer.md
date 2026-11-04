---
title: Tích hợp Oracle Responsys với AppsFlyer
metadata:
  keywords:
    - Oracle Responsys
    - Advertisers
    - Developers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-11-20T09:26:13Z'
  edited_at: '2023-11-01T10:21:59Z'
  id: 360003798297
  locale: vi
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/vi/articles/360003798297
---
> **Sơ lược:** Oracle Responsys, một nền tảng phân tích và gửi email, nhúng AppsFlyer OneLink vào các email. Người nhận email nhấp vào liên kết sẽ được liên kết sâu vào ứng dụng của bạn.

![oracle-responsys-af-logo.png](https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png)

ESP (Nhà cung cấp Dịch vụ Email) có thể là nguồn tuyệt vời cho lưu lượng người dùng được phân đoạn.

Một trong những thách thức với ESP là thực hiện phân bổ chính xác và liên kết sâu. ESP bao bọc URL liên kết sâu bằng miền ghi lượt nhấp chuột của ESP. Quy trình này thường phá vỡ chức năng của Liên kết Chung iOS và Liên kết Ứng dụng Android.

Tuy nhiên, bạn vẫn có thể thực hiện liên kết sâu và ghi lại lượt nhấp chuột với các ESP hỗ trợ Liên kết Chung và Liên kết Ứng dụng trên miền ghi lượt nhấp chuột của chúng. Ngoài ra, bạn có thể thiết lập miền nhấp chuột của riêng mình để hoạt động như miền ghi lượt nhấp chuột.

<div id="prerequisites" />

## Điều kiện tiên quyết

* Cấu hình ứng dụng của bạn để hỗ trợ <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">liên kết sâu với OneLink</Anchor>.
* Xác minh phiên bản SDK của bạn (cả Android và iOS)

<Tabs>
<Tab title="iOS">

* SDK AppsFlyer iOS phiên bản 4.9.0 (trở lên)

</Tab>

<Tab title="Android">

* SDK AppsFlyer Android phiên bản 4.9.0 (trở lên)

</Tab>
</Tabs>

<div id="setting-up-oracle-responsys-click-domain" />

## Thiết lập miền nhấp chuột Oracle Responsys

Thực hiện theo phần này để thiết lập miền nhấp chuột của bạn (miền ghi lượt nhấp chuột) trong Oracle Responsys.

<div id="step-1-set-up-a-click-domain-in-oracle-responsys" />

### Bước 1: Thiết lập miền nhấp chuột trong Oracle Responsys

Để thiết lập miền nhấp chuột, hãy làm theo hướng dẫn chính thức của Oracle Responsys về cách <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCEA/LinkTable_Main.htm?cshid=LinkTable_Main">tạo miền nhấp chuột</Anchor>. Oracle Responsys sử dụng Bảng liên kết để giúp ghi lại số lần nhấp chuột cho một chiến dịch cụ thể

**Lưu ý**, trong bảng Liên kết, bạn có thể xác định **URL liên kết iOS** giống với URL Liên kết:

![Oracle-responsys-link-tracking-table.png](https://files.readme.io/c151c58af73cf460ba4275a9159e45c15807f311fa8d8b4b1531b0cdf7e3bc4e-49839256667665.png)

Sau khi bạn đặt các miền nhấp chuột trong Bảng Liên kết, Responsys sẽ sử dụng các miền này để bao bọc các OneLink mà bạn đưa vào chiến dịch email. Bằng cách này, Responsys có thể ghi lại các lượt nhấp chuột trong hệ thống của họ đồng thời duy trì chức năng OneLink và liên kết sâu.

<div id="step-2-give-responsys-an-aasa-ios-and-an-asset-links-file-android" />

### Bước 2: Cung cấp cho Responsys tệp AASA (iOS) và tệp Liên kết Nội dung (Android)

<div id="aasa-for-ios" />

<Accordion title="AASA cho iOS">

Để Responsys hỗ trợ Liên kết Chung iOS, họ cần có tệp AASA. Hãy xem các hướng dẫn sau.

Khi bạn thiết lập OneLink với Liên kết Chung, bạn đã có AASA được liên kết với OneLink. Để có được AASA:

1. Đi tới cấu hình OneLink và tìm OneLink được cấu hình bằng Liên kết Chung.
2. Thêm **/.well-known/apple-app-site-assocation** vào cuối URL OneLink.
3. Dán OneLink vào thanh địa chỉ trình duyệt và nhấn Enter. Ví dụ: **`<OneLinkSubdomain>`.onelink.me/.well-known/apple-app-site-assocation**. Khi bạn làm như vậy, tệp AASA sẽ được tải xuống máy tính của bạn. Bạn có thể mở nó bằng bất kỳ trình soạn thảo văn bản đơn giản nào.
4. Gửi tệp AASA này tới Responsys. Để biết thêm thông tin và tìm hiểu thêm về nội dung của tệp này, hãy xem trang 11 trong <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCFB/pdf/ios-universal-links-dev-guide.pdf">hướng dẫn của Oracle</Anchor>.

</Accordion>

<div id="asset-links-for-android" />

<Accordion title="Liên kết Nội dung dành cho Android">

Khi bạn thiết lập OneLink với Liên kết Ứng dụng, bạn đã có tệp Liên kết Nội dung được liên kết với OneLink. Để lấy tệp Liên kết Nội dung. Để lấy tệp Liên kết Nội dung:

1. Đi tới cấu hình OneLink và tìm OneLink được định cấu hình bằng Liên kết Ứng dụng.
2. Thêm **/.well-known/assetlinks.json** vào cuối URL OneLink.
3. Dán OneLink vào thanh địa chỉ trình duyệt và nhấn Enter. Ví dụ:**`<OneLinkSubdomain>`.onelink.me/.well-known/assetlinks.json**. Khi bạn làm như vậy, tệp Liên kết Nội dung sẽ được tải xuống máy tính của bạn. Bạn có thể mở nó bằng bất kỳ trình soạn thảo văn bản đơn giản nào.
4. Gửi tệp Liên kết Nội dung này tới Responsys. Để biết thêm thông tin và tìm hiểu thêm về nội dung của tệp này, hãy xem <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCFB/android/app-links/">hướng dẫn này</Anchor>.

</Accordion>

<div id="setting-up-your-app" />

## Thiết lập ứng dụng của bạn

<div id="step-1-for-android-setting-up-your-app-to-support-app-links" />

<Accordion title="Bước 1 dành cho Android: Thiết lập ứng dụng của bạn để hỗ trợ Liên kết Ứng dụng">

<div id="adding-the-click-domain-to-the-activity-in-the-android-manifest" />

#### Thêm miền nhấp chuột vào hoạt động trong tệp kê khai Android

Trong tệp kê khai Android, hãy thêm máy chủ miền nhấp chuột và bất kỳ tiền tố nào vào thẻ hoạt động của hoạt động mà bạn muốn liên kết sâu.

```html Markup
<activity android:name=".DeepLinkActivity">
    <intent-filter  android:autoVerify="true">
        <action android:name="android.intent.action.VIEW" />
           <category android:name="android.intent.category.DEFAULT" />
           <category android:name="android.intent.category.BROWSABLE" />
           <data android:scheme="https"
               android:host="click.example.com"
               android:pathPrefix="/campaign" />
     </intent-filter>
</activity>
```

<div id="setting-up-the-app-to-resolve-click-domains" />

#### Thiết lập ứng dụng để phân giải các miền nhấp chuột

SDK cần phân giải OneLink đằng sau miền nhấp chuột để biết thông tin chi tiết chiến dịch. Các chi tiết được trả về trong phương thức `onAppOpenAttribution` .

Để phân giải các miền nhấp chuột:

1. Đảm bảo rằng phiên bản SDK của bạn ít nhất là 4.9.0.
2. Liệt kê các miền nhấp chuột trong API SDK `setResolveDeepLinkURLs`. API này cần được gọi trước khi khởi tạo SDK. Để biết thêm thông tin, vui lòng tham khảo tài liệu SDK <Anchor target="_blank" href="/marketers/vi/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">tại đây</Anchor>.  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("click.example.com");
   ```

   * **Quan trọng!** Nếu bạn đang sử dụng Movable Ink (MI) kết hợp với Oracle, bạn cần lấy MI CNAME và các miền nội bộ từ người quản lý tài khoản MI của mình rồi thêm chúng vào `setResolveDeepLinkURLs`, ngoài liên kết nhấp chuột cho Oracle. Ví dụ:

     ```java
     AppsFlyerLib.getInstance().setResolveDeepLinkURLs("oracle-click.example.com", "mi.example.com", "example.micpn.com");
     ```

</Accordion>

<div id="step-1-for-ios-setting-up-your-app-to-support-universal-links" />

<Accordion title="Bước 1 dành cho iOS: Thiết lập ứng dụng của bạn để hỗ trợ Liên kết Chung">

Phần này thảo luận cách thiết lập ứng dụng của bạn để hỗ trợ Liên kết Chung.

<div id="associating-click-domains-in-xcode" />

#### Liên kết các miền nhấp chuột trong Xcode

1. Trong Xcode, hãy nhấp vào dự án của bạn.
2. Nhấp vào ***Capabilities***.[![configure-xcode-deeplinking-domain.png](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)
3. Bật ***Associated Domain***.
4. Nhấp vào dấu + và thêm miền nhấp chuột của bạn. Ví dụ: applinks:click.example.com.

</Accordion>

<div id="step-2-setting-up-the-app-to-resolve-click-domains" />

### Bước 2: Thiết lập ứng dụng để phân giải các miền nhấp chuột

SDK cần phân giải OneLink đằng sau miền nhấp chuột để biết thông tin chi tiết chiến dịch. Các chi tiết được trả về trong phương thức `onAppOpenAttribution` .

Để phân giải các miền nhấp chuột:

1. Đảm bảo rằng phiên bản SDK của bạn ít nhất là 4.9.0.
2. Liệt kê các miền nhấp chuột trong thuộc tính SDK `resolveDeepLinkURLs`. Thuộc tính này cần được đặt trước khi khởi tạo SDK. Để biết thêm thông tin, vui lòng tham khảo tài liệu SDK <Anchor target="_blank" href="/marketers/vi/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">tại đây</Anchor>.  

   <Tabs>
   <Tab title="Objective-C">

   ```objectivec
   [AppsFlyerTracker sharedTracker].resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```

   </Tab>

   <Tab title="Swift">

   ```swift
   AppsFlyerTracker.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   </Tab>
   </Tabs>

   * **Quan trọng!** Nếu bạn đang sử dụng Movable Ink (MI) kết hợp với Oracle, bạn cần lấy MI CNAME và các miền nội bộ từ người quản lý tài khoản MI của mình rồi thêm chúng vào `setResolveDeepLinkURLs`, ngoài liên kết nhấp chuột cho Oracle. Ví dụ về các miền:
     * Miền Oracle: oracle-click.example.com
     * Miền MI CNAME: mi.example.com
     * Miền nội bộ MI: example.micpn.com
3. Thêm mã sau để SDK có thể phân giải miền ghi lượt nhấp chuột:  

   <Tabs>
   <Tab title="Objective-C">

   Thêm mã này vào AppDelegate.m

   ```objectivec
   - (NSDictionary *)allHTTPHeaderFieldsForResolveDeepLinkURL:(NSURL *)URL {
       if ([URL.host  isEqual: @"click.example.com"]) {
           return [NSDictionary dictionary];
       }
       else {
           return nil;
       }
   }
   ```

   </Tab>

   <Tab title="Swift">

   Thêm mã này vào AppDelgate.swift

   ```swift
   func allHTTPHeaderFields(forResolveDeepLinkURL URL: URL!) -> [String : String]! {
       if (URL.host == "click.example.com") {
           /// Change User-Agent
           return [:]
       } khác {
           return nil;
       }
   }
   ```

   </Tab>
   </Tabs>

<div id="sending-your-first-email" />

## Gửi email đầu tiên của bạn

1. Tạo URL OneLink trong trang Link Management (hoặc theo cách thủ công).
2. Khi tạo URL OneLink, hãy đảm bảo URL mã hóa tất cả các giá trị tham số.
3. Các thông số sau đây được đặc biệt khuyến khích sử dụng:
   * pid (nguồn truyền thông) - Sử dụng nguồn truyền thông biểu thị việc sử dụng này, chẳng hạn như Email.
   * c (chiến dịch) - Tên chiến dịch bạn muốn đánh giá.
   * af\_dp - Lược đồ URI liên kết sâu mà bạn muốn liên kết sâu với người dùng của mình.
   * af\_web\_dp - Nơi chuyển hướng người dùng nhấp vào liên kết trên máy tính để bàn.
   * af\_ios\_url - Nơi chuyển hướng người dùng không có ứng dụng nhấp vào liên kết trên thiết bị iOS.
   * af\_android\_url - Nơi chuyển hướng người dùng không có ứng dụng, nhấp vào liên kết trên thiết bị Android.
4. Đưa URL OneLink vào email bạn tạo trong Responsys. Ví dụ:

   ```http
   <a href="greatapp.onelink.me/abcd/1234567">Tải xuống ứng dụng tuyệt vời của tôi!</a>
   ```

   Ở giai đoạn này, Responsys bao bọc liên kết trên bằng miền nhấp chuột mà bạn đã đưa vào các bước trước. Bất kỳ nhấp chuột nào vào tên miền nhấp chuột đều chuyển hướng đến liên kết phân bổ OneLink. Nếu ứng dụng được cài đặt trên thiết bị của người dùng, miền nhấp chuột sẽ liên kết sâu vào ứng dụng.

<div id="note" />

> 📄 **Ví dụ**
>
> Các tham số URL không được mã hóa URL trong ví dụ này, chỉ nhằm mục đích dễ đọc:
>
> ```http
> https://greatapp.onelink.me/abcd?pid=Email&c=Spring_Newsletter&is_retargeting=true&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

<div id="testing-your-links" />

### Kiểm tra liên kết của bạn

Sau khi làm theo tất cả các bước bắt buộc được đề cập ở trên, tạo URL OneLink phù hợp và đưa liên kết đó vào email, hãy gửi cho chính bạn một email kiểm tra.

Bạn nên dự kiến điều gì?

Nếu bạn đã cài đặt ứng dụng, ứng dụng sẽ được gọi. Nếu API liên kết sâu SDK AppsFlyer có liên quan được triển khai thì bạn nên liên kết sâu vào nội dung có liên quan.  
Ngoài ra, một lượt nhấp chuột sẽ xuất hiện trong cả bảng điều khiển AppsFlyer, được quy cho nguồn truyền thông và chiến dịch được cung cấp cũng như trong dữ liệu của Responsys.

<div data-zendesk-anchors="prerequisites=%C4%91i%E1%BB%81u-ki%E1%BB%87n-ti%C3%AAn-quy%E1%BA%BFt h_01HDNSK7GR33AN2M4GP956S1FD=%C4%91i%E1%BB%81u-ki%E1%BB%87n-ti%C3%AAn-quy%E1%BA%BFt setting-up-oracle-responsys-click-domain=thi%E1%BA%BFt-l%E1%BA%ADp-mi%E1%BB%81n-nh%E1%BA%A5p-chu%E1%BB%99t-oracle-responsys h_01HDNSK7GR84QSRTS86GH556WK=thi%E1%BA%BFt-l%E1%BA%ADp-mi%E1%BB%81n-nh%E1%BA%A5p-chu%E1%BB%99t-oracle-responsys step-1-set-up-a-click-domain-in-oracle-responsys=b%C6%B0%E1%BB%9Bc-1-thi%E1%BA%BFt-l%E1%BA%ADp-mi%E1%BB%81n-nh%E1%BA%A5p-chu%E1%BB%99t-trong-oracle-responsys h_01HDNSK7GRHYJZSMYCMT9RVEBW=b%C6%B0%E1%BB%9Bc-1-thi%E1%BA%BFt-l%E1%BA%ADp-mi%E1%BB%81n-nh%E1%BA%A5p-chu%E1%BB%99t-trong-oracle-responsys step-2-give-responsys-an-aasa-ios-and-an-asset-links-file-android=b%C6%B0%E1%BB%9Bc-2-cung-c%E1%BA%A5p-cho-responsys-t%E1%BB%87p-aasa-ios-v%C3%A0-t%E1%BB%87p-li%C3%AAn-k%E1%BA%BFt-n%E1%BB%99i-dung-android h_01HDNSK7GRW57NNXMN1SWFTTFZ=b%C6%B0%E1%BB%9Bc-2-cung-c%E1%BA%A5p-cho-responsys-t%E1%BB%87p-aasa-ios-v%C3%A0-t%E1%BB%87p-li%C3%AAn-k%E1%BA%BFt-n%E1%BB%99i-dung-android h_01HDNSK7GR77N60SFVBD57S9GQ=aasa-for-ios h_01HDNSK7GR6ADJCPG63ZVP19NJ=asset-links-for-android setting-up-your-app=thi%E1%BA%BFt-l%E1%BA%ADp-%E1%BB%A9ng-d%E1%BB%A5ng-c%E1%BB%A7a-b%E1%BA%A1n h_01HDNSK7GRN751HAPPQ3HVRMDG=thi%E1%BA%BFt-l%E1%BA%ADp-%E1%BB%A9ng-d%E1%BB%A5ng-c%E1%BB%A7a-b%E1%BA%A1n h_01HDNSK7GRHCK378A8XKMK7ZZF=step-1-for-android-setting-up-your-app-to-support-app-links adding-the-click-domain-to-the-activity-in-the-android-manifest=th%C3%AAm-mi%E1%BB%81n-nh%E1%BA%A5p-chu%E1%BB%99t-v%C3%A0o-ho%E1%BA%A1t-%C4%91%E1%BB%99ng-trong-t%E1%BB%87p-k%C3%AA-khai-android h_01HDNSK7GRQNQGWXAEGHSTHADH=th%C3%AAm-mi%E1%BB%81n-nh%E1%BA%A5p-chu%E1%BB%99t-v%C3%A0o-ho%E1%BA%A1t-%C4%91%E1%BB%99ng-trong-t%E1%BB%87p-k%C3%AA-khai-android setting-up-the-app-to-resolve-click-domains=thi%E1%BA%BFt-l%E1%BA%ADp-%E1%BB%A9ng-d%E1%BB%A5ng-%C4%91%E1%BB%83-ph%C3%A2n-gi%E1%BA%A3i-c%C3%A1c-mi%E1%BB%81n-nh%E1%BA%A5p-chu%E1%BB%99t h_01HDNSK7GRP9ND0MHC3ZHD7G8H=thi%E1%BA%BFt-l%E1%BA%ADp-%E1%BB%A9ng-d%E1%BB%A5ng-%C4%91%E1%BB%83-ph%C3%A2n-gi%E1%BA%A3i-c%C3%A1c-mi%E1%BB%81n-nh%E1%BA%A5p-chu%E1%BB%99t h_01HDNSK7GRJ682QYAMPB4PSGRZ=step-1-for-ios-setting-up-your-app-to-support-universal-links associating-click-domains-in-xcode=li%C3%AAn-k%E1%BA%BFt-c%C3%A1c-mi%E1%BB%81n-nh%E1%BA%A5p-chu%E1%BB%99t-trong-xcode h_01HDNSK7GSRENM232MQ25EB3J3=li%C3%AAn-k%E1%BA%BFt-c%C3%A1c-mi%E1%BB%81n-nh%E1%BA%A5p-chu%E1%BB%99t-trong-xcode step-2-setting-up-the-app-to-resolve-click-domains=b%C6%B0%E1%BB%9Bc-2-thi%E1%BA%BFt-l%E1%BA%ADp-%E1%BB%A9ng-d%E1%BB%A5ng-%C4%91%E1%BB%83-ph%C3%A2n-gi%E1%BA%A3i-c%C3%A1c-mi%E1%BB%81n-nh%E1%BA%A5p-chu%E1%BB%99t h_01HDNSK7GSP08G2EQSNVR5G45B=b%C6%B0%E1%BB%9Bc-2-thi%E1%BA%BFt-l%E1%BA%ADp-%E1%BB%A9ng-d%E1%BB%A5ng-%C4%91%E1%BB%83-ph%C3%A2n-gi%E1%BA%A3i-c%C3%A1c-mi%E1%BB%81n-nh%E1%BA%A5p-chu%E1%BB%99t sending-your-first-email=g%E1%BB%ADi-email-%C4%91%E1%BA%A7u-ti%C3%AAn-c%E1%BB%A7a-b%E1%BA%A1n h_01HDNSK7GSA9VAMTRFCX8SZGSC=g%E1%BB%ADi-email-%C4%91%E1%BA%A7u-ti%C3%AAn-c%E1%BB%A7a-b%E1%BA%A1n h_01HDNSK7GS8HP7BAA8BYBVBABD=v%C3%AD-d%E1%BB%A5 testing-your-links=ki%E1%BB%83m-tra-li%C3%AAn-k%E1%BA%BFt-c%E1%BB%A7a-b%E1%BA%A1n h_01HDNSK7GSTAJXAP6KGKE9TD8T=ki%E1%BB%83m-tra-li%C3%AAn-k%E1%BA%BFt-c%E1%BB%A7a-b%E1%BA%A1n" />
