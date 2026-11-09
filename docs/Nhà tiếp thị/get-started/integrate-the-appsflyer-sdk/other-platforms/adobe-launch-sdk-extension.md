---
title: Tiện ích mở rộng Adobe Launch SDK
metadata:
  keywords:
    - SDK
    - Adobe
    - Advertisers
    - AppsFlyer SDK
    - Adobe Experience Platform
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
  created_at: '2019-02-13T08:03:45Z'
  edited_at: '2024-03-05T14:48:02Z'
  id: 360000939097
  locale: vi
  section: Other platforms
  section_id: 6551244207121
  url: https://support.appsflyer.com/hc/vi/articles/360000939097
---
> **Sơ lược:** Gửi dữ liệu đến Adobe Launch SDK và AppsFlyer SDK chỉ bằng một lần triển khai Tiện ích mở rộng AppsFlyer Adobe Launch SDK.

<div id="overview" />

## Tổng quan

Adobe Launch SDK là một phần không thể thiếu của Nền tảng Adobe Experience. Nền tảng Adobe Experience giúp các doanh nghiệp thu thập, hợp nhất và phân tích dữ liệu từ nhiều ứng dụng và nền tảng. Nền tảng này giúp chủ doanh nghiệp và nhà phát triển hiểu rõ hơn về hành vi của khách hàng để tối ưu hóa trải nghiệm và phân phối nội dung. Nếu ứng dụng của bạn triển khai cả Adobe Launch SDK và AppsFlyer SDK, bạn có thể gửi dữ liệu đến cả hai chỉ bằng một lần triển khai **Tiện ích mở rộng AppsFlyer Adobe Launch SDK**. Điều này giúp bạn đơn giản hóa tổng thể quá trình phát triển cũng như giúp cơ sở trở nên gọn gàng và có thể duy trì.

<div id="note" />

> 📘 **Lưu ý**
>
> Nếu bạn đang sử dụng tiện ích mở rộng Adobe Launch thì không cần tích hợp Adobe Analytics <Anchor target="_blank" href="/marketers/vi/docs/adobe-analytics-integration-with-appsflyer">tiêu chuẩn.</Anchor>

<div id="prerequisites" />

## Điều kiện tiên quyết

Một vài điểm cần thực hiện trước khi tích hợp Tiện ích mở rộng AppsFlyer Adobe SDK.

<div id="get-your-appsflyer-dev-key" />

<Accordion title="Nhận dev key AppsFlyer của bạn">

<Image align="center" alt="dev_key.png" src="https://files.readme.io/bf25b5d583f3eaab57c230b68764f08c49806a50401955a511993d8a847e7d42-360006050318.png" width="357px" />

1. Trong bảng điều khiển ứng dụng của bạn, nhấp vào ***App Settings*** trong phần ***Configuration*** ở menu bên trái.
2. Trong phần ***SDK Installation***, hãy sao chép ***Dev Key***.

</Accordion>

<div id="get-your-app-id" />

<Accordion title="Lấy ID ứng dụng của bạn">

* Đối với Android - ID ứng dụng là tên gói, ví dụ như example.com.app.
* Đối với iOS - ID ứng dụng là ID iTunes của ứng dụng không có tiền tố *id* ví dụ: 123456748.

</Accordion>

<div id="step-1-configuring-adobe-launch" />

## Bước 1: Định cấu hình Adobe Launch

Làm theo hướng dẫn dưới đây để định cấu hình Adobe Launch.

<div id="11-creating-a-new-property-in-adobe-launch" />

<Accordion title="1.1 Tạo thuộc tính mới trong Adobe Launch">

<Image align="center" alt="" src="https://files.readme.io/d03e61047c536785e7601d4f0efbd9b6488bd41c92efdd6e0d1021b42a5bec3a-small-360005983477.png" />

1. Đăng nhập vào Adobe Experience Cloud.
2. Chọn ***Launch***.
3. Nhấp vào ***Go to Launch***.
4. Nhấp vào ***New Property***.
5. Đặt tên cho thuộc tính rồi chọn ***Mobile***.
6. Nhấp vào ***Save***.

</Accordion>

<div id="12-installing-required-adobe-launch-extensions" />

<Accordion title="1.2 Cài đặt các tiện ích mở rộng Adobe Launch cần thiết">

Cài đặt các tiện ích mở rộng sau vào Adobe Launch:

<Image align="center" alt="adboe_extensions.png" src="https://files.readme.io/bf0c0652c3807d4da0819a62b600ac875af1f8764387a36cc3f256a58e1ea852-360005983597.png" />

* Adobe Analytics - kết nối dữ liệu ghi được từ SDK với mô-đun Adobe Analytics.
* Tiện ích mở rộng AppsFlyer SDK - gửi dữ liệu và sự kiện đến cả Adobe và AppsFlyer bằng Adobe Launch SDK.
* Adobe Profile - cho phép SDK lưu trữ dữ liệu vào hồ sơ phía máy khách.
* Adobe Mobile Core - cho phép cấu hình SDK của thiết bị di động và cung cấp quyền truy cập vào các sự kiện và điều kiện vòng đời mặc định.

<div id="installing-adobe-analytics-extension" />

#### Cài đặt tiện ích mở rộng Adobe Analytics

1. Đăng nhập vào Adobe Analytics.
2. <Anchor target="_blank" href="https://docs.adobe.com/help/en/analytics/admin/admin-console/create-report-suite.html">Tạo bộ báo cáo</Anchor>.
3. Đăng nhập lại vào Adobe Launch.
4. Từ danh sách thuộc tính, hãy nhấp vào thuộc tính mà bạn đã tạo trước đó.
5. Nhấp vào ***Extensions***.
6. Tìm kiếm và cài đặt ***Adobe Analytics***.
7. Trong ***Report Suites***, chỉ định bộ báo cáo mà bạn đã tạo ở bước 2.
8. Nhấp vào ***Save***.

<div id="installing-appsflyer-sdk-extension" />

#### Cài đặt Tiện ích mở rộng AppsFlyer SDK

1. Chọn ***Extensions*** lại lần nữa.
2. Tìm kiếm và cài đặt ***AppsFlyer SDK Extension***.
3. Trong ***AppsFlyer iOS App ID***, hãy chỉ định ID ứng dụng iOS mà bạn nhận được trong bước điều kiện tiên quyết.
4. Trong ***AppsFlyer Dev Key***, hãy chỉ định dev key mà bạn nhận được trong bước điều kiện tiên quyết.
5. Bật tùy chọn ***Send attribution data to Adobe Analytics***. Lưu ý rằng có một số <Anchor target="_blank" href="/marketers/vi/docs/user-level-data-retention">hạn chế về việc chia sẻ dữ liệu cấp người dùng với các nền tảng phân tích của bên thứ 3</Anchor>.
6. Nhấp vào ***Save***.

<div id="install-profile-and-mobile-core-extension" />

#### Cài đặt tiện ích mở rộng Profile và Mobile Core

1. Chọn ***Extensions*** lại lần nữa.
2. Tìm kiếm và cài đặt ***Profile***.
3. Tìm kiếm và cài đặt ***Mobile Core***.
   * Khi cài đặt Mobile Core, chỉ cần lưu nguyên trạng tiện ích mở rộng. Không cần chỉ định ***Máy chủ Experience Cloud***.

</Accordion>

<div id="step-2-implementing-appsflyer-adobe-sdk-extension" />

## Bước 2: Triển khai Tiện ích mở rộng AppsFlyer Adobe SDK

Làm theo hướng dẫn trong phần này để triển khai Tiện ích mở rộng Adobe SDK vào ứng dụng của bạn.

<div id="21-adding-the-sdk-to-the-app" />

<Accordion title="2.1 Thêm SDK vào ứng dụng">

<Image align="center" alt="adobe_sdk.png" src="https://files.readme.io/076e6cc5911a0a515e5510a8da233bcefcb4144c92cf49190416b593fcdecc8f-small-360006050518.png" />

1. Bên trong thuộc tính Adobe của bạn, hãy chọn ***Environments***.
2. Chọn môi trường mà bạn muốn triển khai SDK.
3. Ở phía bên phải, nhấp vào biểu tượng hộp.
4. Sao chép đoạn mã từ cửa sổ mở ra và làm theo hướng dẫn. Nếu bạn là nhà tiếp thị đang định cấu hình Adobe, hãy gửi các đoạn mã này cho nhà phát triển ứng dụng của bạn.

</Accordion>

<div id="22-publishing-the-environment" />

<Accordion title="2.2 Phát hành môi trường">

Để hoàn tất việc triển khai SDK, bạn cần phát hành môi trường lên thư viện.

<Image align="center" alt="adobe_publishing.png" src="https://files.readme.io/4e9ad08fce291ef59e7a3567726c678754ae3a3c96de75f4ae27cd80a84945d1-small-360006050558.png" />

1. Bên trong thuộc tính Adobe, hãy chọn ***Publishing***.
2. Nhấp vào ***Add New Library***.
3. Đặt tên cho thư viện và trong mục Environment, hãy chọn ***Development***.
4. Nhấp vào ***Save & Build for Development***.
5. Sau khi bản dựng hoàn tất, trong mục ***Development***, nhấp vào ba dấu chấm bên cạnh thư viện và chọn ***Submit for Approval***.
6. Trong mục ***Submitted***, nhấp vào ba dấu chấm bên cạnh thư viện và chọn ***Build for Staging***.
7. Sau khi bản dựng hoàn tất, hãy nhấp vào ba dấu chấm bên cạnh thư viện và chọn ***Approve for Publishing***.
8. Trong mục ***Approve***, nhấp vào ba dấu chấm bên cạnh thư viện và chọn ***Build & Publish to Production***.

</Accordion>

<div id="23-adding-android-install-referrer-to-your-app" />

<Accordion title="2.3 Thêm liên kết giới thiệu cài đặt Android vào ứng dụng của bạn">

Liên kết giới thiệu cài đặt Android cải thiện độ chính xác phân bổ, bảo vệ khỏi gian lận cài đặt và hơn thế nữa. Liên kết này được hỗ trợ từ Android SDK của AppsFlyer phiên bản 4.8.6.

<div id="note-1" />

> 📘 **Lưu ý**
>
> Google đã ngừng hỗ trợ [BroadcastReceiver](https://android-developers.googleblog.com/2019/11/still-using-installbroadcast-switch-to.html) vào tháng 3 năm 2020.
>
> * Thay đổi này không ảnh hưởng đến ứng dụng.
> * Bạn vẫn có thể cần BroadcastReceiver để thực hiện phân bổ ngoài cửa hàng. Để chắc chắn, hãy kiểm tra với cửa hàng nơi đăng ứng dụng đó.
> * Việc triển khai liên kết thiệu cài đặt hiện là bắt buộc.

Có hai cách để thêm liên kết giới thiệu cài đặt vào ứng dụng của bạn:

* Sử dụng Gradle (được đề xuất)
* Thêm thủ công liên kết giới thiệu cài đặt

<Tabs>
<Tab title="Thêm liên kết giới thiệu cài đặt bằng Gradle">

Thêm Liên kết giới thiệu cài đặt Android làm phần phụ thuộc. Bạn có thể tìm thấy phiên bản mới nhất <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.android.installreferrer/installreferrer/1.0">tại đây</Anchor>.

1.
   ```java
   dependencies {
   //make sure to use the latest SDK version: https://mvnrepository.com/artifact/com.appsflyer/af-android-sdk
   	implementation 'com.appsflyer:af-android-sdk:5.+'
   	implementation 'com.android.installreferrer:installreferrer:1.1'
   }
   ```
2. Đồng bộ hóa dự án để truy xuất các phần phụ thuộc - xem ảnh chụp màn hình sau:  

    <Image align="center" alt="android_af_sdk_sync_gradle.png" src="https://files.readme.io/f8835cf76d51d7ddeb51206707d95b7214e398c5960299893118ad57ccffe890-22939234622609.png" />

Nếu bạn đang sử dụng ProGuard và muốn sử dụng API liên kết giới thiệu mới của Google, hãy đặt quy tắc ProGuard sau: `-dontwarn com.android.installreferrer`

</Tab>

<Tab title="Thêm thủ công liên kết giới thiệu cài đặt">

1. <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.android.installreferrer/installreferrer/1.0">Tải xuống Install Referrer aar</Anchor>
2. <Anchor target="_blank" href="https://stackoverflow.com/questions/16682847/how-to-manually-include-external-aar-package-using-new-gradle-android-build-syst">Thêm vào dự án</Anchor>
3. Thêm quyền sau vào tệp kê khai: `com.google.android.finsky.permission.BIND_GET_INSTALL_REFERRER_SERVICE`

</Tab>
</Tabs>

</Accordion>

<div id="24-setting-required-permissions" />

<Accordion title="2.4 Thiết lập các quyền bắt buộc">

Thêm quyền truy cập giúp tăng tỷ lệ <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#probabilistic-modeling">Phân bổ mô hình xác suất</Anchor>. Nó cũng cho phép SDK gửi thêm dữ liệu như Wifi và dữ liệu mạng của nhà mạng. Bạn có thể tìm thấy dữ liệu này trong <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">báo cáo dữ liệu thô</Anchor> và sử dụng nó để phân tích và tối ưu hóa các chiến dịch.

<div id="add-required-permissions" />

#### Thêm Quyền truy cập Bắt buộc

1. Thêm các quyền truy cập sau vào AndroidManifest.xml:  

   ```html Markup
   <uses-permission android:name="android.permission.INTERNET" />
   <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
   <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
   <!-- Optional : -->
   <uses-permission android:name="android.permission.READ_PHONE_STATE" />
   ```

</Accordion>

<div id="using-the-adobe-sdk-extension" />

## Sử dụng tiện ích mở rộng Adobe SDK

Đến đây, bạn có thể bắt đầu sử dụng tiện ích mở rộng Adobe SDK để gửi dữ liệu đến Adobe và AppsFlyer.

<div id="note-2" />

> 📘 **Lưu ý**
>
> Hiện tại, tiện ích mở rộng Adobe Launch SDK chỉ hỗ trợ nhận dữ liệu chuyển đổi và gửi sự kiện. Tuy nhiên, khi bạn thêm tiện ích mở rộng Adobe Launch SDK vào ứng dụng của mình, AppsFlyer SDK cũng sẽ được thêm vào. Do đó, bất kỳ chức năng nào hiện đang bị thiếu trong tiện ích mở rộng Adobe SDK đều có thể được triển khai bằng AppsFlyer SDK.

<div id="sending-events" />

<Accordion title="Gửi sự kiện">

Các sự kiện trong ứng dụng cung cấp thông tin chi tiết về những gì đang xảy ra trong ứng dụng của bạn. Bạn nên dành thời gian và xác định các sự kiện bạn muốn ghi nhận. Việc ghi nhận sự kiện trong ứng dụng cho phép bạn đo lường các KPI như ROI (Lợi tức Đầu tư) và LTV (Giá trị Vòng đời).

Tiện ích mở rộng Adobe Launch SDK cho phép bạn gửi dữ liệu sự kiện trong ứng dụng đến cả Adobe và AppsFlyer. Sau đó, bạn có thể sử dụng Adobe Analytics để phân tích hành vi của người dùng và AppsFlyer để phân tích ROI và LTV.

<Tabs>
<Tab title="Android">

```java
final Map<String,String> eventMap = new HashMap<>();  
eventMap.put("currency", "USD");  
eventMap.put("revenue", "200");  
eventMap.put("freehand", "param");

MobileCore.trackAction("af_purchase", eventMap);
```

</Tab>

<Tab title="iOS">

```objectivec
[ACPCore trackAction:@"af_purchase data:@{@"revenue":@"200",@"currency":@"USD"];
```

</Tab>
</Tabs>

Gửi các sự kiện như được chỉ định trong mã ở trên sẽ tạo ra một sự kiện trong bảng điều khiển AppsFlyer tên là af\_purchase với doanh thu 200 USD. Sự kiện này cũng được gửi đến và xuất hiện trong Adobe Analytics.

Tất cả <Anchor target="_blank" href="https://dev.appsflyer.com/docs/direct-deep-linking-1">dữ liệu chuyển đổi</Anchor> được gửi cùng với các sự kiện đều có tiền tố là ***appsflyer***. Xem các ví dụ trong bảng sau:

| Biến dữ liệu chuyển đổi có tiền tố |
| --- |
| appsflyer.af\_click\_lookback |
| appsflyer.install\_time |
| appsflyer.cost\_cents\_USD |
| appsflyer.media\_source |
| appsflyer.af\_adset |
| appsflyer.click\_time |
| appsflyer.orig\_cost |
| appsflyer.campaign |

Dữ liệu chuyển đổi được sử dụng trong ứng dụng mà bạn tạo trong Dịch vụ Adobe Mobile. Có thể có các tham số khác xuất hiện trong dữ liệu chuyển đổi. Để tìm hiểu thêm, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters#thông-số-đường-dẫn-phân-bổ">đây</Anchor>.

</Accordion>

<div id="getting-data-for-deep-linking-and-deferred-deep-linking" />

<Accordion title="Lấy dữ liệu cho liên kết sâu và liên kết sâu gián tiếp">

Liên kết sâu và liên kết sâu gián tiếp cho phép bạn cải thiện trải nghiệm người dùng của mình. Chúng cho phép bạn mở ứng dụng trong các hoạt động cụ thể và tùy chỉnh nội dung theo dữ liệu chiến dịch.

Để lấy dữ liệu từ liên kết sâu, hãy triển khai lệnh gọi lại tiện ích mở rộng.

<Tabs>
<Tab title="Android">

Trong lớp ứng dụng toàn cục, hãy triển khai mã sau:

```java
AppsFlyerAdobeExtension.registerAppsFlyerExtensionCallbacks(new AppsFlyerExtensionCallbacksListener() {
		@Override
		public void onCallbackReceived(Map<String, String> callback) {
			Log.d(AppsFlyerLibCore.LOG_TAG, callback.toString());
			if(callback.get("callback_type").equals("onConversionDataReceived")){
				// conversion data returned 
				if(callback.get("is_first_launch").equals("true")){
					String af_status = callback.get("af_status");
					if(af_status.equals("Non-organic")){
						Log.d(AppsFlyerLibCore.LOG_TAG, "this is first launch and a non organic install!");
					}
				}
			} else if(callback.get("callback_type").equals("onAppOpenAttribution")){
				// direct deeplink - redirect user
				Log.d(AppsFlyerLibCore.LOG_TAG, callback.toString());
			}
		}
		@Override
		public void onCallbackError(String errorMessage) {
			Log.d("TAG", errorMessage);
		}
	});
```

</Tab>

<Tab title="iOS">

Trong AppDelegate.m, hãy triển khai mã sau:

```objectivec
[AppsFlyerAdobeExtension registerCallbacks:^(NSDictionary *dictionary) {
        NSLog(@"[AppsFlyerAdobeExtension] Received callback: %@", dictionary);
        if([[dictionary objectForKey:@"callback_type"] isEqualToString:@"onConversionDataReceived"]){
            if([[dictionary objectForKey:@"is_first_launch"] boolValue] == YES){
                NSString* af_status = [dictionary objectForKey:@"af_status"];
                if([af_status isEqualToString:@"Non-organic"]){
                    NSLog(@"this is first launch and a non organic install!");
                }
            }
        } else if([[dictionary objectForKey:@"callback_type"] isEqualToString:@"onAppOpenAttribution"]) {
            NSLog(@"onAppOpenAttribution Received");
        }
     }];
    [AppsFlyerAdobeExtension callbacksErrorHandler:^(NSError *error) {
          NSLog(@"[AppsFlyerAdobeExtension] Error recieving callback: %@" , error);
    }];
```

</Tab>
</Tabs>

</Accordion>

<div id="connecting-appsflyer-conversion-data" />

## Kết nối dữ liệu chuyển đổi AppsFlyer

Dữ liệu chuyển đổi được gửi cùng với các sự kiện đến nền tảng Adobe. Các biến này cho phép bạn áp dụng logic và quy tắc đối với các phương diện, chỉ số hoặc bộ lọc báo cáo.

<Image align="center" alt="adobe_analytics.png" src="https://files.readme.io/9c4355286d2e5f2254a8a16a49b1b1305b56628b54e738efcd4fdc90a6de8fab-360006050778.png" />

1. Đăng nhập vào Dịch vụ Adobe Mobile<Anchor target="_blank" href="https://mobilemarketing.adobe.com">.</Anchor>
2. Chọn ứng dụng có liên quan và vào trang ***Manage Variables & Metrics***.
3. Chọn tab ***Custom Variables*** và định cấu hình các biến để ánh xạ dữ liệu AppsFlyer SDK tới hệ thống Adobe.
4. Đối với mỗi biến tùy chỉnh, hãy nhập một tên có nghĩa.
5. Chọn hoặc nhập dữ liệu chuyển đổi AppsFlyer đã ánh xạ và chọn phạm vi ***Độ toàn vẹn*** mong muốn.

Xem bảng sau để ánh xạ các biến ngữ cảnh AppsFlyer:

| **Tên được đề xuất để ánh xạ** | **Dữ liệu chuyển đổi** |
| --- | --- |
| Khung thời gian Xem lại AppsFlyer | appsflyer.af\_click\_lookback |
| Thời gian Cài đặt AppsFlyer | appsflyer.install\_time |
| Chi phí AppsFlyer tính bằng Cent Mỹ | appsflyer.cost\_cents\_USD |
| AppsFlyer MediaSource | appsflyer.media\_source |
| Bộ quảng cáo AppsFlyer | appsflyer.af\_adset |
| Thời gian Nhấp chuột của AppsFlyer | appsflyer.click\_time |
| Chi phí Ban đầu của AppsFlyer | appsflyer.orig\_cost |
| Chiến dịch AppsFlyer | appsflyer.campaign |

<div id="using-appsflyer-mapped-conversion-data-for-analytics-and-analysis" />

### Sử dụng dữ liệu chuyển đổi được AppsFlyer ánh xạ cho Giải tích và Phân tích

Tất cả dữ liệu đến từ SDK đều có sẵn trong bộ báo cáo Adobe Analytics được kết nối với ứng dụng.

Bạn có thể sử dụng dữ liệu cũng như các phương diện và chỉ số liên quan trên các báo cáo và bảng điều khiển của Adobe Analytics đã tạo của mình. Dữ liệu này cũng có sẵn trong bảng điều khiển AppsFlyer dùng để phân bổ và phân tích sự kiện trong ứng dụng.

<div data-zendesk-anchors="overview=t%E1%BB%95ng-quan h_01HQQN1Y7MP7B0GXJFP5330G80=t%E1%BB%95ng-quan h_01HQQNCMYNN0YH7S8Q5F2EWFG5=l%C6%B0u-%C3%BD prerequisites=%C4%91i%E1%BB%81u-ki%E1%BB%87n-ti%C3%AAn-quy%E1%BA%BFt h_01HQQN1JWAQZZ9S3YV7VXTMRWM=%C4%91i%E1%BB%81u-ki%E1%BB%87n-ti%C3%AAn-quy%E1%BA%BFt h_01HQQN1JWA4JYET26CB11JGY46=get-your-appsflyer-dev-key h_01HQQN1JWAHYQBRY43EWANQ57Z=get-your-app-id step-1-configuring-adobe-launch=b%C6%B0%E1%BB%9Bc-1-%C4%91%E1%BB%8Bnh-c%E1%BA%A5u-h%C3%ACnh-adobe-launch h_01HQQN1JWAAR873B679QGA9NSX=b%C6%B0%E1%BB%9Bc-1-%C4%91%E1%BB%8Bnh-c%E1%BA%A5u-h%C3%ACnh-adobe-launch h_01HQQN1JWAE1T7SP3DHTFB55TK=11-creating-a-new-property-in-adobe-launch h_01HQQN1JWA8FDWMNZ4Y17AWYKW=12-installing-required-adobe-launch-extensions installing-adobe-analytics-extension=c%C3%A0i-%C4%91%E1%BA%B7t-ti%E1%BB%87n-%C3%ADch-m%E1%BB%9F-r%E1%BB%99ng-adobe-analytics h_01HQQN1JWAMB8607K8V2F3YKHE=c%C3%A0i-%C4%91%E1%BA%B7t-ti%E1%BB%87n-%C3%ADch-m%E1%BB%9F-r%E1%BB%99ng-adobe-analytics installing-appsflyer-sdk-extension=c%C3%A0i-%C4%91%E1%BA%B7t-ti%E1%BB%87n-%C3%ADch-m%E1%BB%9F-r%E1%BB%99ng-appsflyer-sdk h_01HQQN1JWAYHP9243MTFZ4B2EF=c%C3%A0i-%C4%91%E1%BA%B7t-ti%E1%BB%87n-%C3%ADch-m%E1%BB%9F-r%E1%BB%99ng-appsflyer-sdk install-profile-and-mobile-core-extension=c%C3%A0i-%C4%91%E1%BA%B7t-ti%E1%BB%87n-%C3%ADch-m%E1%BB%9F-r%E1%BB%99ng-profile-v%C3%A0-mobile-core h_01HQQN1JWA1TEBQY1NH3YP2HQB=c%C3%A0i-%C4%91%E1%BA%B7t-ti%E1%BB%87n-%C3%ADch-m%E1%BB%9F-r%E1%BB%99ng-profile-v%C3%A0-mobile-core step-2-implementing-appsflyer-adobe-sdk-extension=b%C6%B0%E1%BB%9Bc-2-tri%E1%BB%83n-khai-ti%E1%BB%87n-%C3%ADch-m%E1%BB%9F-r%E1%BB%99ng-appsflyer-adobe-sdk h_01HQQN1JWB3B24RHP9QMNPJK8J=b%C6%B0%E1%BB%9Bc-2-tri%E1%BB%83n-khai-ti%E1%BB%87n-%C3%ADch-m%E1%BB%9F-r%E1%BB%99ng-appsflyer-adobe-sdk h_01HQQN1JWBMP4ARMH2VPX35TGH=21-adding-the-sdk-to-the-app h_01HQQN1JWBV3144WY92PAX6PW2=22-publishing-the-environment h_01HQQN1JWBRRCTGA6Q9RDC41KN=23-adding-android-install-referrer-to-your-app h_01HQQN1JWB40T4K3ZJB6AE42WQ=l%C6%B0u-%C3%BD-1 h_01HQQN1JWB19NTCNTWX9QRP8AC=24-setting-required-permissions add-required-permissions=th%C3%AAm-quy%E1%BB%81n-truy-c%E1%BA%ADp-b%E1%BA%AFt-bu%E1%BB%99c h_01HQQN1JWBVVVGRRXGX9ZJTBT8=th%C3%AAm-quy%E1%BB%81n-truy-c%E1%BA%ADp-b%E1%BA%AFt-bu%E1%BB%99c using-the-adobe-sdk-extension=s%E1%BB%AD-d%E1%BB%A5ng-ti%E1%BB%87n-%C3%ADch-m%E1%BB%9F-r%E1%BB%99ng-adobe-sdk h_01HQQN1JWBFD2CZ4PMCBRM3JN8=s%E1%BB%AD-d%E1%BB%A5ng-ti%E1%BB%87n-%C3%ADch-m%E1%BB%9F-r%E1%BB%99ng-adobe-sdk h_01HQQN1JWBSBVFVB911WH54Q32=l%C6%B0u-%C3%BD-2 h_01HQQN1JWBVZDAVAZD4NXMBG4S=sending-events h_01HQQN1JWBXG0JCE9RKA659H6V=getting-data-for-deep-linking-and-deferred-deep-linking connecting-appsflyer-conversion-data=k%E1%BA%BFt-n%E1%BB%91i-d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i-appsflyer h_01HQQN1JWBMBXGQFKGWHE058VT=k%E1%BA%BFt-n%E1%BB%91i-d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i-appsflyer using-appsflyer-mapped-conversion-data-for-analytics-and-analysis=s%E1%BB%AD-d%E1%BB%A5ng-d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i-%C4%91%C6%B0%E1%BB%A3c-appsflyer-%C3%A1nh-x%E1%BA%A1-cho-gi%E1%BA%A3i-t%C3%ADch-v%C3%A0-ph%C3%A2n-t%C3%ADch h_01HQQN1JWB0WBD6HZXQN6STJY9=s%E1%BB%AD-d%E1%BB%A5ng-d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i-%C4%91%C6%B0%E1%BB%A3c-appsflyer-%C3%A1nh-x%E1%BA%A1-cho-gi%E1%BA%A3i-t%C3%ADch-v%C3%A0-ph%C3%A2n-t%C3%ADch" />
