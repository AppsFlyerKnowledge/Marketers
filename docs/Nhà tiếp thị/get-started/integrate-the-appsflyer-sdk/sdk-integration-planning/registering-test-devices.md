---
title: 'Đăng ký thiết bị thử nghiệm '
metadata:
  keywords:
    - whitelisting
    - Testing
    - device
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2015-03-10T08:19:35Z'
  edited_at: '2023-11-10T08:08:33Z'
  id: 207031996
  locale: vi
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/vi/articles/207031996
---
> **Khái quát:** Khi thực hiện các thử nghiệm phân bổ, hãy đăng ký thiết bị thử nghiệm của bạn để đảm bảo mỗi lượt cài đặt được ghi nhận dưới dạng một lượt cài đặt mới. Thiết bị thử nghiệm đã đăng ký ngăn không cho ghi nhận các lượt cài đặt dưới dạng lượt cài đặt lại.

<div id="why-register-a-test-device" />

## Lý do phải đăng ký thiết bị thử nghiệm

Khi thực hiện thử nghiệm phân bổ, khung thời gian phân bổ lại giới hạn số lần phân bổ lượt cài đặt thành một lần trong 90 ngày. Vì vậy, nếu bạn sử dụng cùng một thiết bị nhiều lần để thử nghiệm phân bổ lượt cài đặt, thì sẽ không có thông tin nào được ghi nhận. Việc đăng ký một thiết bị làm thiết bị thử nghiệm sẽ tránh ghi lại các lượt cài đặt lặp lại trên thiết bị đã đăng ký thành lượt cài đặt lại.

<div id="methods-for-registering-a-test-device" />

## Phương pháp đăng ký thiết bị thử nghiệm

Đăng ký thiết bị thử nghiệm bao gồm chọn hệ điều hành của thiết bị (Android, iOS hoặc Windows) và thêm mã định danh thiết bị.

Bạn có thể sử dụng một trong các phương thức sau để đăng ký:

* [Tải xuống và cài đặt ID thiết bị của tôi bằng ứng dụng AppsFlyer:](#register-a-device-using-the-appsflyer-device-id-app-admin-only) Sau khi cài đặt ứng dụng trên thiết bị thử nghiệm, bạn có thể tự động đăng ký thiết bị và chia sẻ thông tin ID thiết bị cho tài khoản AppsFlyer của mình. Thiết bị sẽ được liệt kê tự động trên trang **Thiết bị thử nghiệm**.

  <div id="note" />

  > 📘 **Lưu ý**
  >
  > Trong các thiết bị thử nghiệm chạy iOS 14 trở lên, bạn có thể sử dụng phương thức đăng ký này chỉ khi AppTransparency Tracking (ATT) được triển khai trên ứng dụng của bạn và bạn muốn chạy thử nghiệm với tư cách là người dùng đồng ý. Nếu điều này không xảy ra, hãy dùng phương thức thủ công.

* [Thêm thiết bị thử nghiệm theo cách thủ công:](#register-a-device-manually) Bất kỳ người dùng tài khoản nào cũng có thể đăng ký thiết bị thử nghiệm trực tiếp bằng cách thêm mã định danh thiết bị vào trang **Thiết bị thử nghiệm**.

Hãy ghi nhớ những điều sau:

* Thiết bị thử nghiệm đã đăng ký khả dụng cho tất cả các ứng dụng thuộc tài khoản.
* Mạng quảng cáo cần yêu cầu nhà quảng cáo thêm thiết bị; đại lý có thể thêm thiết bị của riêng họ.

<div id="supported-device-identifiers" />

<Accordion title="Mã định danh thiết bị được hỗ trợ">

Mã định danh thiết bị bao gồm:

* **Android:** AID (GAID hoặc OAID), IMEI, ID Android

  <div id="note-1" />

  > 📘 **Lưu ý**
  >
  > Khi đăng ký thiết bị thử nghiệm, bạn nên thêm IMEI hoặc mã định danh thiết bị ID Android chỉ nếu như ứng dụng của bạn thu thập và sử dụng các mã định danh này.

* **iOS:** IDFA, IDFV
* **Windows Phone:** ID quảng cáo của Windows

</Accordion>

<div id="managing-test-device-registration" />

## Quản lý đăng ký thiết bị thử nghiệm

<div id="register-a-device-using-the-appsflyer-device-id-app-admin-only" />

<Accordion title="Đăng ký thiết bị sử dụng ứng dụng ID thiết bị của AppsFlyer">

**Để tải xuống ứng dụng ID thiết bị AppsFlyer:**

1. Tải xuống và cài đặt ứng dụng bằng mã QR (cửa hàng Google Play) hoặc một trong các đường dẫn được cấp.  

   <Tabs>
   <Tab title="Android">

   [<Image alt="" src="https://support.appsflyer.com/hc/article_attachments/360005641117" width="233px" />](https://support.appsflyer.com/hc/article_attachments/360005641117)

   **Đường dẫn:** [Google Play](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid&hl=en) và [Cửa hàng ngoài thị trường](https://apkpure.com/my-device-id-by-appsflyer/com.appsflyer.android.deviceid)

   </Tab>

   <Tab title="iOS">

   [<Image alt="" src="https://support.appsflyer.com/hc/article_attachments/360001988157" width="233px" />](https://support.appsflyer.com/hc/article_attachments/360001988157)

   </Tab>

   <Tab title="Windows">

   [<Image alt="" src="https://files.readme.io/6e60bf0e69c0055c5946d111a0a5a2a04dddb268ba777b52097ab0650327d280-31773660950673.png" width="233px" />](https://files.readme.io/6e60bf0e69c0055c5946d111a0a5a2a04dddb268ba777b52097ab0650327d280-31773660950673.png)

   </Tab>
   </Tabs>

2. Trên thiết bị phiên bản iOS 14.5 trở lên, nếu bạn muốn cho phép thu thập IDFA, hãy nhấn vào **Allow** khi xuất hiện lời nhắc ATT.

   [![](https://files.readme.io/3be1b8f24bf558d022c45913b393cf8c8011639354d8b11d9c591e58024f1c8d-31773660957329.png)](https://files.readme.io/3be1b8f24bf558d022c45913b393cf8c8011639354d8b11d9c591e58024f1c8d-31773660957329.png)
3. Trên màn hình Android/iOS/Windows, nhấn vào **Register** để đăng ký thiết bị.

   <Tabs>
   <Tab title="Android">

   [![](https://files.readme.io/b6deed582cc87925576b893fb8f021e4aa254c15a99ec532fd456e146769a125-31773630607889.png)](https://files.readme.io/b6deed582cc87925576b893fb8f021e4aa254c15a99ec532fd456e146769a125-31773630607889.png)

   </Tab>

   <Tab title="iOS">

   [![](https://files.readme.io/f06f609433b8ce483e5281cc2a0d062ab71a150318d7892879f3defb706f5429-31773660968081.png)](https://files.readme.io/f06f609433b8ce483e5281cc2a0d062ab71a150318d7892879f3defb706f5429-31773660968081.png)

   </Tab>

   <Tab title="Windows">

   [![](https://files.readme.io/6bbfb8680a3f6ea507a7d011d3140fbcc11173f4ef091f7c5f7c3cc863598ab8-31773660972817.jpg)](https://files.readme.io/6bbfb8680a3f6ea507a7d011d3140fbcc11173f4ef091f7c5f7c3cc863598ab8-31773660972817.jpg)

   </Tab>
   </Tabs>

4. Nhập thông tin đăng nhập AppsFlyer của bạn. Thiết bị hiện đã được đăng ký.
5. Nhấn vào **Share details** để chia sẻ thông tin về ID Thiết bị.

</Accordion>

<div id="register-a-device-manually" />

<Accordion title="Đăng ký thiết bị theo cách thủ công">

Người dùng tài khoản có thể đăng ký thiết bị theo cách thủ công:

1. Trong AppsFlyer, ở phía trên bên phải, nhấp vào địa chỉ email của bạn.
2. Chọn **Test** **devices**.
3. Nhấp vào **+ Add device**.

   [![](https://files.readme.io/e28ef06002e423d4cf7863d4c7fd2b269a0ede5c4b996a50cee25ffbedfcd9d1-31773630618769.png)](https://files.readme.io/e28ef06002e423d4cf7863d4c7fd2b269a0ede5c4b996a50cee25ffbedfcd9d1-31773630618769.png)
4. Hoàn thành các trường sau:
   * **Name (chỉ sử dụng chữ cái tiếng Anh):** Nhập tên định danh duy nhất cho thiết bị.
   * **OS:** Chọn hệ điều hành.
   * **Device ID type:** Chọn một mã định danh thiết bị.
   * **Device ID:** Cung cấp ID thiết bị theo hệ điều hành:

     <Tabs>
     <Tab title="iOS">

     Cách lấy mã định danh IDFA hoặc IDFV:

     * **IDFA:** Để lấy IDFA, cài đặt ứng dụng ID thiết bị AppsFlyer trên thiết bị thử nghiệm của bạn. Để biết cách thực hiện, hãy xem: [Thêm thiết bị](#register-a-device-manually) thông qua ứng dụng ID thiết bị AppsFlyer (chỉ dành cho quản trị viên) ở trên.
     * **IDFV:** Để lấy IDFV, yêu cầu nhà phát triển của bạn cài ứng dụng công cụ thử nghiệm IDFV trên thiết bị thử nghiệm của bạn. Sau khi cài đặt và khởi chạy, ứng dụng công cụ thử nghiệm sẽ hiển thị IDFV. **Lưu ý:** Chỉ có thể cài công cụ thử nghiệm sau khi nhà phát triển đã thực hiện các bước sơ bộ trong X-Code.

     Để biết thời điểm cần sử dụng IDFA hoặc IDFV, hãy xem phần [Đăng ký thiết bị thử nghiệm iOS](#đăng-ký-thiết-bị-thử-nghiệm-ios).

     </Tab>

     <Tab title="Android">

     Nhận mã định danh bằng cách sử dụng ứng dụng ID thiết bị AppsFlyer hoặc bằng cách nhập mã quay số vào thiết bị:

     | Mã định danh | Phương thức truy xuất | Google Play | Khác |
     | --- | --- | --- | --- |
     | AID (GAID hoặc OAID) | Sử dụng [ứng dụng ID thiết bị AppsFlyer](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid) | Bắt buộc | Có thể được sử dụng để đăng ký thiết bị |
     | imei | *#06#* | Không áp dụng | Có thể được sử dụng để đăng ký thiết bị |
     | ID Android | *#*#8255#*#* (có thể không hoạt động trên các thiết bị mới hơn) | Không áp dụng | Có thể được sử dụng để đăng ký thiết bị |

     </Tab>

     <Tab title="Windows">

     **Windows Ad ID** [Nhận ID quảng cáo của Windows](https://www.microsoft.com/en-us/p/my-ad-device-id/9nn69nbsj9xw?activetab=pivot:overviewtab)

     </Tab>
     </Tabs>

5. Nhấp vào **Save**. Thiết bị hiển thị trong danh sách các thiết bị đã đăng ký. **Lưu ý**: Mặc dù thiết bị hiển thị ngay lập tức trong danh sách các thiết bị đã đăng ký, nhưng quy trình đăng ký vào hệ thống và hoạt động như dự kiến có thể mất vài phút.

<div id="note-2" />

> 📘 **Lưu ý**
>
> **Thêm nhiều hơn một mã định danh**
>
> Có thể có trường hợp bạn muốn thêm nhiều hơn một mã định danh vào thiết bị thử nghiệm của mình, ví dụ như bạn muốn cả IDFA và IDFV trên cùng một thiết bị.
>
> **Để thêm một mã định danh bổ sung:**
>
> 1. Nhấp vào **Add device**.
> 2. Sử dụng cùng tên cho thiết bị thử nghiệm và thêm mã định danh thứ hai.
> 3. Nhấp vào **Save**.

</Accordion>

<div id="unregister-a-device" />

<Accordion title="Hủy đăng ký thiết bị">

Mỗi tài khoản có thể đăng ký tối đa 200 thiết bị. Chỉ người dùng quản trị mới có thể xóa thiết bị thử nghiệm.

**Để xóa thiết bị khỏi danh sách:**

1. Trong AppsFlyer, ở phía trên bên phải, nhấp vào địa chỉ email của bạn.
2. Chọn **Test** **devices**.
3. Nhấp vào biểu tượng xóa để gỡ thiết bị.

</Accordion>

<div id="registering-an-ios-test-device" />

## Đăng ký thiết bị thử nghiệm iOS

Biểu đồ tiến trình bên dưới minh họa các đường lối hành động khả thi khi đăng ký thiết bị thử nghiệm iOS của bạn.

[![](https://files.readme.io/214818cd73ebc8cd5d3479d27e3074fec55ec7f9e3d4702b17f3c8811270f54e-31773630621585.png)](https://files.readme.io/214818cd73ebc8cd5d3479d27e3074fec55ec7f9e3d4702b17f3c8811270f54e-31773630621585.png)

Chọn giữa các tùy chọn sau khi đăng ký thiết bị thử nghiệm iOS của bạn:

<div id="register-your-testing-device-with-idfa" />

<Accordion title="Đăng ký thiết bị thử nghiệm của bạn bằng IDFA">

<div id="when-to-use-idfa-for-test-device-registration" />

#### **Khi nào nên dùng IDFA để đăng ký thiết bị thử nghiệm?**

Bạn có thể đăng ký bằng IDFA nếu AppTransparency Tracking (ATT) được triển khai trên ứng dụng của bạn và bạn muốn chạy thử nghiệm với tư cách là người dùng đồng ý. Khi khởi chạy ứng dụng đã thử nghiệm lần đầu, hãy nhớ nhấp vào **Allow** trong lời nhắc ATT.

<div id="how-to-register-your-test-device-with-an-idfa" />

#### **Làm thế nào để đăng ký thiết bị thử nghiệm bằng IDFA?**

Để đăng ký bằng IDFA, hãy đăng ký thiết bị bằng ứng dụng ID thiết bị AppsFlyer.

</Accordion>

<div id="register-your-testing-device-with-idfv" />

<Accordion title="Đăng ký thiết bị thử nghiệm bằng IDFV">

<div id="when-to-use-idfv-for-test-device-registration" />

#### **Khi nào nên dùng IDFV để đăng ký thiết bị thử nghiệm?**

Nếu không thể truy cập IDFA, IDFV là lựa chọn duy nhất của bạn. Dưới đây là các tình huống bạn **phải sử dụng IDFV**:

* **ATT đã được triển khai** nhưng bạn muốn chạy thử nghiệm với tư cách là người dùng không đồng ý. Khi khởi chạy ứng dụng lần đầu, hãy nhớ nhấp vào **Don't Allow** trong lời nhắc ATT.
* **ATT không hề được triển khai**.

<div id="how-to-register-your-device-with-idfv" />

#### **Làm thế nào để đăng ký thiết bị bằng IDFV?**

1. Trước khi bạn có thể đăng ký thiết bị thử nghiệm bằng IDFV, nhà phát triển của bạn phải cài ứng dụng công cụ thử nghiệm IDFV trên thiết bị thử nghiệm của bạn. Để xem hướng dẫn dành cho nhà phát triển, bạn có thể giới thiệu <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-the-idfv-test-tool-app">bài viết này</Anchor> cho nhà phát triển của bạn.
2. Sau khi nhà phát triển của bạn cài đặt ứng dụng công cụ thử nghiệm IDFV, khởi chạy ứng dụng và sao chép IDFV được hiển thị.
3. [Đăng ký thiết bị thử nghiệm thủ công](#register-a-device-manually) bằng IDFV.

<div id="note-3" />

> 📘 **Lưu ý**
>
> **Lý do cài đặt ứng dụng công cụ thử nghiệm IDFV là gì?**
>
> * Công cụ thử nghiệm IDFV được dùng để xuất IDFV bạn cần trong quá trình đăng ký thiết bị thử nghiệm.
> * Khi bạn không có ứng dụng khác thuộc sở hữu của tài khoản nhà phát triển được cài đặt trên thiết bị thử nghiệm của bạn. Trong trường hợp này, iOS sẽ chỉ định một ID nhà cung cấp mới cho mỗi lần cài lại ứng dụng. Vì hoạt động thử nghiệm liên quan đến nhiều trường hợp, bao gồm cài lại ứng dụng, mỗi lượt cài đặt lại sẽ kích hoạt iOS đặt lại IDFV. **Bằng cách giả vờ thuộc về nhà cung cấp, ứng dụng tiện íchngăn iOS tạo ra một IDFV mới mỗi lần cài lại ứng dụng trên thiết bị thử nghiệm.**

</Accordion>

<div id="dont-register-a-testing-device" />

<Accordion title="Không đăng ký thiết bị thử nghiệm">

Chỉ sử dụng tùy chọn này nếu bạn không thể đăng ký thiết bị thử nghiệm bằng IDFA hoặc IDFV. Trong trường hợp này, mô hình xác suất sẽ được sử dụng để phân bổ. Mỗi lượt cài đặt sẽ được ghi nhận dưới dạng lượt cài đặt mới trên thiết bị thử nghiệm. Phương thức này có thể giúp đăng ký các lượt cài đặt thử nghiệm lặp lại cho cùng một thiết bị nếu ít nhất một trong các trường hợp sau xảy ra:

* SDK AppsFlyer dành cho iOS là v6.8.0 trở xuống.
* Tính năng phát hiện lượt cài đặt lại bị tắt đối với ứng dụng (không nên dùng cho các ứng dụng trực tiếp).
* Đường dẫn phân bổ thử nghiệm chứa "is\_retargeting=true". Trong trường hợp này, lượt cài đặt được ghi nhận dưới dạng phân bổ lại và có sẵn trong bảng điều khiển nhắm mục tiêu lại và báo cáo dữ liệu thô nhắm mục tiêu lại.

</Accordion>

<div data-zendesk-anchors="why-register-a-testing-device=l%C3%BD-do-ph%E1%BA%A3i-%C4%91%C4%83ng-k%C3%BD-thi%E1%BA%BFt-b%E1%BB%8B-th%E1%BB%AD-nghi%E1%BB%87m 01H7W9EA7RQDB69QS339XFHAFZ=l%C3%BD-do-ph%E1%BA%A3i-%C4%91%C4%83ng-k%C3%BD-thi%E1%BA%BFt-b%E1%BB%8B-th%E1%BB%AD-nghi%E1%BB%87m methods-for-registering-a-testing-device=ph%C6%B0%C6%A1ng-ph%C3%A1p-%C4%91%C4%83ng-k%C3%BD-thi%E1%BA%BFt-b%E1%BB%8B-th%E1%BB%AD-nghi%E1%BB%87m 01H7W9EA7RRRJBFSXW3KY53R9K=ph%C6%B0%C6%A1ng-ph%C3%A1p-%C4%91%C4%83ng-k%C3%BD-thi%E1%BA%BFt-b%E1%BB%8B-th%E1%BB%AD-nghi%E1%BB%87m 01H7W9EA7RTTQ1FHZZ6GBGV0WP=l%C6%B0u-%C3%BD 01H7W9EA7RWWNACKSEETMCP90W=supported-device-identifiers 01H7W9EA7R9A8KCNRD0BTPPQTH=l%C6%B0u-%C3%BD-1 managing-testingdevice-registration=qu%E1%BA%A3n-l%C3%BD-%C4%91%C4%83ng-k%C3%BD-thi%E1%BA%BFt-b%E1%BB%8B-th%E1%BB%AD-nghi%E1%BB%87m 01H7W9EA7R7SJVVQCST3WA6YBM=qu%E1%BA%A3n-l%C3%BD-%C4%91%C4%83ng-k%C3%BD-thi%E1%BA%BFt-b%E1%BB%8B-th%E1%BB%AD-nghi%E1%BB%87m h_01H6V7FQFF10E4C82ZQ97PEEZA=register-a-device-using-the-appsflyer-device-id-app-admin-only h_01H6V7GM8KKXF8VS5ZRA4NV592=register-a-device-manually 01H7W9EA7R190M9DH7GPY1VJ77=l%C6%B0u-%C3%BD-2 01H7W9EA7R0KGH3YXZ9SMAFESZ=unregister-a-device registering-an-ios-testing-device=%C4%91%C4%83ng-k%C3%BD-thi%E1%BA%BFt-b%E1%BB%8B-th%E1%BB%AD-nghi%E1%BB%87m-ios h_01H6S2AKDH181MBDFGPBP1BQPV=%C4%91%C4%83ng-k%C3%BD-thi%E1%BA%BFt-b%E1%BB%8B-th%E1%BB%AD-nghi%E1%BB%87m-ios 01H7W9EA7SPA47GR1X0S9WZKDH=register-your-testing-device-with-idfa when-to-use-idfa-for-testing-device-registration=khi-n%C3%A0o-n%C3%AAn-d%C3%B9ng-idfa-%C4%91%E1%BB%83-%C4%91%C4%83ng-k%C3%BD-thi%E1%BA%BFt-b%E1%BB%8B-th%E1%BB%AD-nghi%E1%BB%87m 01H7W9EA7SRD5V5134H2BRZ2AF=khi-n%C3%A0o-n%C3%AAn-d%C3%B9ng-idfa-%C4%91%E1%BB%83-%C4%91%C4%83ng-k%C3%BD-thi%E1%BA%BFt-b%E1%BB%8B-th%E1%BB%AD-nghi%E1%BB%87m how-to-register-your-testing-device-with-an-idfa=l%C3%A0m-th%E1%BA%BF-n%C3%A0o-%C4%91%E1%BB%83-%C4%91%C4%83ng-k%C3%BD-thi%E1%BA%BFt-b%E1%BB%8B-th%E1%BB%AD-nghi%E1%BB%87m-b%E1%BA%B1ng-idfa 01H7W9EA7SBBCAP3Y24FFCCGJW=l%C3%A0m-th%E1%BA%BF-n%C3%A0o-%C4%91%E1%BB%83-%C4%91%C4%83ng-k%C3%BD-thi%E1%BA%BFt-b%E1%BB%8B-th%E1%BB%AD-nghi%E1%BB%87m-b%E1%BA%B1ng-idfa 01H7W9EA7SNZ3ER02MBV8VJGH3=register-your-testing-device-with-idfv when-to-use-idfv-for-testing-device-registration=khi-n%C3%A0o-n%C3%AAn-d%C3%B9ng-idfv-%C4%91%E1%BB%83-%C4%91%C4%83ng-k%C3%BD-thi%E1%BA%BFt-b%E1%BB%8B-th%E1%BB%AD-nghi%E1%BB%87m 01H7W9EA7S3103TSHSH4XHTP1R=khi-n%C3%A0o-n%C3%AAn-d%C3%B9ng-idfv-%C4%91%E1%BB%83-%C4%91%C4%83ng-k%C3%BD-thi%E1%BA%BFt-b%E1%BB%8B-th%E1%BB%AD-nghi%E1%BB%87m how-to-register-your-device-with-idfv=l%C3%A0m-th%E1%BA%BF-n%C3%A0o-%C4%91%E1%BB%83-%C4%91%C4%83ng-k%C3%BD-thi%E1%BA%BFt-b%E1%BB%8B-b%E1%BA%B1ng-idfv 01H7W9EA7SGTDQCRVJKKRH0EVT=l%C3%A0m-th%E1%BA%BF-n%C3%A0o-%C4%91%E1%BB%83-%C4%91%C4%83ng-k%C3%BD-thi%E1%BA%BFt-b%E1%BB%8B-b%E1%BA%B1ng-idfv 01H7W9EA7SHVSDPJN8P2WBSFN1=l%C6%B0u-%C3%BD-3 01H7W9EA7S3KJ89AN9ZBMHFGRR=dont-register-a-testing-device" />
