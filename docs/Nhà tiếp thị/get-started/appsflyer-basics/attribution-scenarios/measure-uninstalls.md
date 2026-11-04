---
title: Đo lường lượt Gỡ cài đặt
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2021-10-14T08:03:47Z'
  edited_at: '2023-10-25T11:24:06Z'
  id: 4408933557137
  locale: vi
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/vi/articles/4408933557137
---
> **Khái quát**: Đo lường tỷ lệ gỡ cài đặt cho ứng dụng của bạn và xác định nguồn nào (nguồn truyền thông, chiến dịch, quảng cáo và địa lý) mang đến người dùng chất lượng.

<div id="overview" />

## Tổng quan

Để hiểu giá trị của người dùng ứng dụng, bạn phải phân tích cả tỷ lệ lượt cài đặt và lượt gỡ cài đặt. Số liệu lượt gỡ cài đặt có thể giúp bạn đo lường hiệu suất của ứng dụng, đồng thời hiểu rõ thời điểm và lý do người dùng rời khỏi ứng dụng của bạn.

<div id="note" />

<div id="how-does-it-work" />

### Nó hoạt động như thế nào?

AppsFlyer sử dụng thông báo đẩy ngầm, một lần một ngày, để xác minh xem một ứng dụng có còn được cài đặt trên một thiết bị cụ thể hay không. Nếu không có phản hồi, lượt gỡ cài đặt sẽ được ghi nhận và được phân bổ cho nguồn truyền thông ban đầu mang đến người dùng.

<div id="how-to-use-uninstall-data" />

## Cách sử dụng dữ liệu lượt gỡ cài đặt

Sau đây là một số ví dụ về những điều bạn có thể biết được từ việc đo lường lượt gỡ cài đặt và cách bạn có thể sử dụng dữ liệu để tối ưu hóa chiến dịch và khả năng thu hút người dùng.

<div id="compare-the-quality-of-sources" />

<Accordion title="So sánh chất lượng các nguồn">

Bằng cách so sánh chất lượng người dùng có được từ các nguồn khác nhau (nguồn truyền thông, chiến dịch, quảng cáo và địa lý), bạn có thể xác định nguồn truyền thông có tỷ lệ lượt gỡ cài đặt thấp nhất và phân bổ lại tiền cho chúng.

<div id="note-1" />

> 📄 **Ví dụ**
>
> Bạn là nhà tiếp thị ứng dụng trò chơi cho PlayIt Gaming International. Bạn vừa cho ra mắt một ứng dụng mới và bạn đang chạy các chiến dịch trên hai nguồn truyền thông khác nhau (Nguồn truyền thông A và Nguồn truyền thông B).
>
> Khi kiểm tra bảng điều khiển, bạn thấy rằng mặc dù Nguồn truyền thông A có số lượt cài đặt cao nhất (10.390) nhưng nguồn truyền thông này cũng có tỷ lệ lượt gỡ cài đặt cao nhất (30%).
>
> Mặt khác, nguồn truyền thông B có 5.949 lượt cài đặt và tỷ lệ lượt gỡ cài đặt thấp nhất (12%).
>
> [![Uninstall rates.png](https://files.readme.io/36fb732bfe3a63729b1aa0913f2fe3f24df6a7c86adde9f5c2b95424d840dec4-33839423253137.png)](https://files.readme.io/36fb732bfe3a63729b1aa0913f2fe3f24df6a7c86adde9f5c2b95424d840dec4-33839423253137.png)
>
> Dựa trên những thông tin chi tiết này, bạn có thể phân bổ lại nhiều ngân sách hơn cho Nguồn truyền thông B và cố gắng có được nhiều người dùng được thu hút hơn.

</Accordion>

<div id="share-uninstall-data-with-ad-networks-for-optimization" />

<Accordion title="Chia sẻ dữ liệu lượt gỡ cài đặt với các mạng quảng cáo để tối ưu hóa">

Việc gửi đăng lại sự kiện lượt gỡ cài đặt tới các mạng quảng cáo mà bạn đang hợp tác rất hữu ích để tối ưu hóa các chiến dịch thu hút người dùng. Bạn có thể gửi sự kiện gỡ cài đặt bằng cách [ánh xạ af\_uninstall tới mạng quảng cáo của mình](/docs/measure-uninstalls#ánh-xạ-sự-kiện-gỡ-cài-đặt). Sau khi ánh xạ hoàn tất, một sự kiện sẽ được gửi mỗi khi người dùng được xác định là đã gỡ cài đặt ứng dụng. Mạng quảng cáo có thể sử dụng thông tin này để xác định người dùng nào ít thu hút hơn và tập trung vào việc có được nhiều người dùng thu hút hơn.

<div id="note-3" />

<div id="note-2" />

> 📄 **Ví dụ**
>
> Bạn là nhà tiếp thị ứng dụng trò chơi cho PlayIt Gaming International. Nguồn truyền thông A là một mạng quảng cáo mà bạn đang hợp tác khi khởi chạy ứng dụng Android mới của mình. Trong chiến dịch trước, bạn đã chạy với Nguồn truyền thông A, 1.000 người dùng mới đã cài đặt ứng dụng của bạn và sau đó, 300 người dùng đã gỡ cài đặt ứng dụng. Đối với chiến dịch mới, bạn muốn Nguồn truyền thông A nhận dữ liệu lượt gỡ cài đặt. Điều này sẽ cho phép Nguồn truyền thông A nhanh chóng giải quyết các thách thức dẫn đến việc gỡ cài đặt.
>
> Dựa trên thông tin chi tiết từ chiến dịch trước, nguồn truyền thông A tạo danh sách loại trừ cho chiến dịch để loại trừ các loại người dùng cụ thể khỏi quảng cáo đang chạy trong chiến dịch mới của bạn:
>
> * Những người dùng đã chứng minh rằng họ có ít giá trị đối với ứng dụng của bạn.
> * Người dùng thường xuyên gỡ cài đặt ứng dụng của bạn.
>
> Điều này cho phép Nguồn truyền thông A tối ưu hóa việc nhắm mục tiêu đối tượng để đảm bảo rằng ngân sách chiến dịch của bạn không bị lãng phí cho những người dùng không cần xem các quảng cáo nhất định của chiến dịch.

</Accordion>

<div id="exclude-uninstalls-from-retargeting-campaigns" />

<Accordion title="Loại trừ lượt gỡ cài đặt khỏi chiến dịch nhắm mục tiêu lại">

Trong một số trường hợp, để tuân thủ <Anchor target="_blank" href="/marketers/vi/docs/apply-privacy-preserving-sdk-methods#optin-and-optout-scenarios">các quy định như GDPR và CCPA</Anchor>, bạn có thể cần phải loại trừ những người dùng đã gỡ cài đặt ứng dụng của bạn khỏi các chiến dịch nhắm mục tiêu lại. Thông tin về lượt gỡ cài đặt cho phép bạn tạo danh sách loại trừ và áp dụng các biện pháp về quyền riêng tư để bảo vệ quyền riêng tư và dữ liệu của khách hàng.

Các phương thức để loại trừ người dùng bao gồm:

* <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview#user-journey-report-availability">Báo cáo dữ liệu thô:</Anchor> Một phương thức thủ công trong đó bạn truy xuất danh sách người dùng đã gỡ cài đặt từ báo cáo **Lượt gỡ cài đặt** và tạo danh sách loại trừ.
* <Anchor target="_blank" href="/marketers/vi/docs/audiences-guide">AppsFlyer Audiences:</Anchor> Một phương thức tự động trong đó bạn xác định đối tượng mục tiêu dựa trên các tiêu chí cụ thể (ví dụ: người dùng **chưa** gỡ cài đặt ứng dụng của bạn). Người dùng không đáp ứng tiêu chí sẽ bị loại khỏi đối tượng.

> 📄 **Ví dụ**
>
> Bạn là nhà tiếp thị ứng dụng trò chơi cho PlayIt Gaming International. Bạn đang chạy chiến dịch nhắm mục tiêu lại cho một trong các ứng dụng Android của mình và bạn quyết định sử dụng AppsFlyer Audiences để xác định đối tượng nhắm mục tiêu lại. Các tiêu chí cho đối tượng của bạn như sau:
>
> * Người dùng chưa gỡ cài đặt ứng dụng.
> * Người dùng chưa khởi chạy ứng dụng trong 30 ngày qua.
>
> Điều này cho phép bạn tạo đối tượng nhắm mục tiêu lại chính xác hơn. Khi chiến dịch nhắm mục tiêu lại của bạn chạy, quảng cáo sẽ chỉ được phân phát cho những người dùng được xác định trong đối tượng nhắm mục tiêu lại của bạn.

</Accordion>

<div id="setting-up-uninstall-measurement" />

## Thiết lập đo lường lượt gỡ cài đặt

Quá trình thiết lập số liệu lượt gỡ cài đặt yêu cầu nhà tiếp thị và nhà phát triển phải phối hợp với nhau. Hướng dẫn triển khai tùy thuộc vào hệ điều hành chạy ứng dụng của bạn.

Luồng cho nhà tiếp thị và nhà phát triển như sau:

<Tabs>
<Tab title="Android">

| Nhiệm vụ | Chủ sở hữu |
| --- | --- |
| [Kết nối Firebase Cloud Messaging (FCM) với AppsFlyer](/docs/measure-uninstalls#kết-nối-firebase-cloud-messaging-với-appsflyer-android) | Nhà tiếp thị |
| [Cấu hình đo lường lượt gỡ cài đặt trong AppsFlyer](/docs/measure-uninstalls#cấu-hình-đo-lường-lượt-gỡ-cài-đặt-trong-appsflyer) | Nhà tiếp thị |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">Tích hợp với SDK</Anchor> | Nhà phát triển Android |
| [Thử nghiệm đo lường lượt gỡ cài đặt](/docs/measure-uninstalls#thử-nghiệm-đo-lường-lượt-gỡ-cài-đặt) | Nhà tiếp thị |
| [Tùy chọn] [Ánh xạ sự kiện gỡ cài đặt](/docs/measure-uninstalls#ánh-xạ-sự-kiện-gỡ-cài-đặt) tới các đối tác có liên quan trong bảng điều khiển | Nhà tiếp thị |

</Tab>

<Tab title="iOS">

| Nhiệm vụ | Chủ sở hữu |
| --- | --- |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement-ios#creating-a-p12-certificate">Tạo chứng chỉ P12</Anchor> | Nhà phát triển iOS |
| [Cấu hình đo lường lượt gỡ cài đặt trong AppsFlyer](/docs/measure-uninstalls#cấu-hình-đo-lường-lượt-gỡ-cài-đặt-trong-appsflyer) | Nhà tiếp thị |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">Tích hợp với SDK</Anchor> | Nhà phát triển iOS |
| [Thử nghiệm đo lường lượt gỡ cài đặt](/docs/measure-uninstalls#thử-nghiệm-đo-lường-lượt-gỡ-cài-đặt) | Nhà tiếp thị |
| [Tùy chọn] [Ánh xạ sự kiện gỡ cài đặt](/docs/measure-uninstalls#ánh-xạ-sự-kiện-gỡ-cài-đặt) tới các đối tác có liên quan trong bảng điều khiển | Nhà tiếp thị |

</Tab>
</Tabs>

<div id="implementation-procedures" />

## Quy trình thực hiện

Việc thực hiện yêu cầu nhà phát triển thiết bị di động tích hợp cơ chế phản hồi thông báo đẩy vào ứng dụng của bạn. Hướng dẫn thực hiện sẽ khác nhau tùy theo hệ điều hành.

<div id="note-4" />

<div id="connect-firebase-cloud-messaging-to-appsflyer-android" />

### Kết nối Firebase Cloud Messaging với AppsFlyer (Android)

Đo lường lượt gỡ cài đặt dành cho nền tảng Android khả dụng bằng cách cấu hình đo lường lượt gỡ cài đặt trong AppsFlyer và sử dụng Firebase Cloud Messaging (FCM) trong ứng dụng của bạn.

<div id="http-v1" />

<Accordion title="HTTP V1">

**Để cấu hình FCM HTTP V1 cho các lượt gỡ cài đặt:**

1. **Để nhận được ID Dự án**:
   1. Đi đến [FCM console](https://console.firebase.google.com/) (Bảng điều khiển FCM)
   2. Chọn một dự án.
   3. Đi đến <strong>Project Overview</strong> (Tổng quan Dự án) > Project settings  
       (Cài đặt dự án).

      ![UninstallFirebase.png](https://files.readme.io/15e74e10daa2f1f1d872f0c8fea274c9819c52c4655baa903728257dd6337e80-33839423254289.png)
   4. Sao chép ID Dự án. Bạn sẽ cần ID Dự án cho giai đoạn sau này trong quá trình.
2. **Cách chỉ định vai trò gỡ cài đặt cho AppsFlyer:**
   1. Đi đến tab **Service accounts** (Tài khoản dịch vụ).
   2. Nhấp vào **Manage service account permissions** (Quản lý quyền truy cập tài khoản dịch vụ).   
      Một tab trình duyệt mới sẽ mở ra trong Google Cloud Platform.
   3. Trong menu bên, hãy chọn **Roles** (Vai trò).
   4. Nhấp vào **+Create role** (Tạo vai trò).
   5. Hoàn thành như sau:
      * Tiêu đề: Nhập **AppsFlyer uninstalls** (Lượt gỡ cài đặt AppsFlyer).
      * ID: Nhập `af_uninstalls`.
      * Giai đoạn khởi chạy vai trò: Chọn **General availability** (Tính khả dụng chung).
   6. Tìm rồi chọn `cloudmessaging.messages.create`.  

      ![AddPermissions.png](https://files.readme.io/efd461ecb74a61c15232e30a6e10eaaecac18f2e24a28565ba8b208ce0654d1a-5542178507665.png)
   7. Nhấp vào **Add** (Thêm).
   8. Nhấp vào **Create** (Tạo).
3. **Cách chỉ định vai trò gỡ cài đặt FCM cho AppsFlyer:**
   1. Trong menu bên, hãy chọn **IAM**.
   2. Nhấp **+ Add** (Thêm).
   3. Trong trường **New members**, hãy chèn af-uninstalls-tracking@af-uninstalls-tracking.iam.gserviceaccount.com.
   4. Trong danh sách **Select a role**, chọn **AppsFlyer uninstalls**.
   5. Nhấp **Save** (Lưu).   
      Tài khoản dịch vụ AppsFlyer vừa được chỉ định vai trò lượt gỡ cài đặt AppsFlyer.

</Accordion>

<div id="legacy-http" />

<Accordion title="[Đã ngừng hỗ trợ] HTTP cũ">

<div id="important" />

> 🚧 **Quan trọng!**
>
> API HTTP cũ đã bị Firebase ngừng hỗ trợ vào ngày 20 tháng 6 năm 2023 và sẽ bị xóa vào tháng 6 năm 2024. Nếu bạn đang sử dụng API cũ, chúng tôi khuyên bạn nên [sử dụng API HTTP v1](/docs/measure-uninstalls#http-v1). <Anchor target="_blank" href="https://firebase.google.com/docs/cloud-messaging/http-server-ref">Tìm hiểu thêm</Anchor>

Việc đo lường lượt gỡ cài đặt sử dụng Firebase Messaging được SDK Android V4.7.0+ hỗ trợ.

**Cách lấy khóa máy chủ Firebase:**

1. Tạo một dự án Ứng dụng Android Firebase (nếu bạn chưa tạo) hoặc di chuyển dự án của bạn từ **Bảng điều khiển dành cho nhà phát triển Google** (làm theo hướng dẫn tại đó). Để biết thêm thông tin, hãy truy cập <Anchor target="_blank" href="https://firebase.google.com/docs/cloud-messaging/android/client">Firebase</Anchor>.
2. <Anchor target="_blank" href="https://console.firebase.google.com">Mở Bảng điều khiển Firebase</Anchor>.
3. Trong trang Giao diện điều khiển Firebase, điều hướng tới Cài đặt Dự án (nhấp vào bánh răng kế bên Tổng quan ở ổ vuông bên trái của trang).

   ![firebase_cloud_messaging_server_key.png](https://files.readme.io/4e31c02a1bea013c823b0148ba1704d4492f66d04e23f0e13e00a9c0c22d286c-33839382513041.png)
4. Trong tab Cloud Messaging, bạn sẽ thấy hai Khóa Máy chủ.
5. Sao chép **Khóa máy chủ**.

</Accordion>

<div id="configure-uninstall-measurement-in-appsflyer" />

<div id="note-5" />

### Cấu hình đo lường lượt gỡ cài đặt trong AppsFlyer

<Tabs>
<Tab title="Android">

**Điều kiện tiên quyết**: Nhà phát triển Android phải hoàn thành <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">hướng dẫn tích hợp</Anchor>.

**Để cấu hình đo lường lượt gỡ cài đặt trong AppsFlyer**:

1. Trong AppsFlyer, đi đến **Configuration** (Cấu hình) > **App Settings** (Cài đặt Ứng dụng).
2. Nếu cần thiết, hãy bật **Uninstall measurement** (Đo lường lượt gỡ cài đặt).
3. Chọn **HTTP V1 và nhập ID dự án mà bạn đã chuẩn bị trước đó.**

   ![UninstallHTTPV1.png](https://files.readme.io/80d13e47ea7ae1585d2ecc0e2f7210572e47dba936557c8e96314e49b0d738d8-33839423258641.png)
4. Nhấp vào **Test connection** (Kiểm tra kết nối).  
   Thông báo thành công sẽ hiện ra.
5. Nhấp vào **Save settings** (Lưu cài đặt).

</Tab>

<Tab title="iOS">

**Điều kiện tiên quyết**: Nhà phát triển iOS phải hoàn thành <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">hướng dẫn tích hợp</Anchor>.

**Để cấu hình đo lường lượt gỡ cài đặt trong AppsFlyer:**

1. Nhận tập tin P12 từ nhà phát triển của bạn.
2. Trong AppsFlyer, đi tới **Configuration** (Cấu hình) > **App Settings** (Cài đặt ứng dụng).
3. Cuộn xuống phần Gỡ cài đặt.
4. Bật tùy chọn **Uninstall measurement** (Đo lường lượt gỡ cài đặt).

   ![Uninstall_iOS_p2.png](https://files.readme.io/3f9de3ebe6099886fa9bc210bd6e491ba91e8ff2c890c980f66c4d48398a597c-33839423260561.png)
5. Nhấp vào biểu tượng tải lên và chọn tập tin P12.
6. [Tùy chọn] Nếu chứng chỉ P12 được bảo vệ bằng mật khẩu, hãy nhập mật khẩu.
7. Nhấp vào **Validate** để gửi chứng chỉ tới AppsFlyer để xác minh.
8. Nhấp vào **Save settings** (Lưu cài đặt).

</Tab>
</Tabs>

<div id="note-6" />

<div id="testing-uninstall-measurement" />

## Thử nghiệm đo lường lượt gỡ cài đặt

Sau khi quy trình thực hiện hoàn tất, bạn có thể cài đặt rồi gỡ cài đặt ứng dụng để kiểm tra xem các lượt gỡ cài đặt có được ghi nhận chính xác hay không. Lượt gỡ cài đặt và tỷ lệ lượt gỡ cài đặt được hiển thị trên Bảng điều khiển tổng quan. 

<Tabs>
<Tab title="Android">

Bạn có thể thực hiện thử nghiệm này trên các ứng dụng:

* Trong Cửa hàng Google Play
* Đang chờ xử lý (không được đăng trong Cửa hàng Google Play)
* Có sẵn thông qua tải xuống trực tiếp
* Trong các cửa hàng ứng dụng thay thế

Hãy ghi nhớ những điều sau đây khi thử nghiệm ứng dụng Android:

* Việc đo lường lượt gỡ cài đặt được xử lý <Anchor target="_blank" href="/marketers/vi/docs/about-data-freshness-and-timezone-support#uninstalls">hàng ngày</Anchor>. Sự kiện gỡ cài đặt được đăng ký trong vòng 24 giờ, nhưng nếu ứng dụng được cài đặt lại trong thời gian này, sự kiện sẽ không được ghi nhận.
* **Sự kiện gỡ cài đặt mất tới 48 giờ để hiển thị** trong <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">báo cáo dữ liệu thô</Anchor> và trong bảng điều khiển của AppsFlyer (Báo cáo Hiệu suất Hợp nhất).

</Tab>

<Tab title="iOS">

Hãy ghi nhớ những điều sau đây khi thử nghiệm ứng dụng iOS:

* Số lượt gỡ cài đặt không xuất hiện ngay trong bảng điều khiển của AppsFlyer: Do có dịch vụ Thông báo Đẩy của Apple, thời gian cần để lượt gỡ cài đặt xuất hiện trên bảng điều khiển là tối thiểu 9 ngày. AppsFlyer cập nhật và hợp nhất số liệu lượt gỡ cài đặt sau mỗi 24 tiếng.

  <div id="h_01HB8CXQ49QN0PH138V2PD2QXE" />

  > 📄 **Ví dụ**
  >
  > * Ngày 1: Người dùng cài đặt ứng dụng của bạn.
  > * Ngày 4: Người dùng gỡ cài đặt ứng dụng của bạn.
  > * Ngày 12: Dịch vụ Thông báo Đẩy của Apple báo cáo sự kiện gỡ ứng dụng 8 ngày sau khi gỡ cài đặt.
  > * Ngày 13: Dữ liệu gỡ cài đặt xuất hiện trên bảng điều khiển và dữ liệu thô của AppsFlyer.

* Nếu bạn đang thực hiện thử nghiệm trên phiên bản thử nghiệm của ứng dụng, hãy đảm bảo rằng bạn đang sử dụng môi trường sandbox. Xem hướng dẫn dành cho nhà phát triển để biết [quy trình thiết lập sandbox cho lượt gỡ cài đặt](https://dev.appsflyer.com/hc/docs/uninstall-measurement-ios#testing-uninstall-measurement).

</Tab>
</Tabs>

<div id="mapping-the-uninstall-event" />

## Ánh xạ Sự kiện Gỡ cài đặt

![Uninstall_event_postback.png](https://files.readme.io/9c3c7f3fd330720d4f6f41fdf509c5af00d042291c1350ab83a1951464ac8e8f-33839423261713.png)

Để chia sẻ dữ liệu lượt gỡ cài đặt với mạng quảng cáo, cần ánh xạ <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#g">sự kiện af\_uninstall</Anchor> với một đối tác. Không giống như đăng lại dành cho các sự kiện trong ứng dụng thông thường, sự kiện gỡ cài đặt không được gửi đi trong thời gian thực. Thời gian sự kiện được báo cáo thể hiện thời gian AppsFlyer xác định ứng dụng đã được gỡ cài đặt chứ không phải chính thời gian thực hiện gỡ cài đặt trong thực tế.

Hãy ghi nhớ những điều sau:

* AppsFlyer chỉ có thể gửi bài đăng lại nếu sự kiện thực sự xảy ra và được AppsFlyer ghi nhận.
* Nếu bạn không thấy các lượt gỡ cài đặt trong trang Tổng quan của bảng điều khiển hoặc trong báo cáo dữ liệu thô, điều này có nghĩa là các đăng lại lượt gỡ cài đặt đã không được gửi tới đối tác, ngay cả khi sự kiện **af\_uninstall** đã được ánh xạ.

<div id="limitations" />

#### Điểm hạn chế

* Các sự kiện gỡ cài đặt không được đưa vào báo cáo bài đăng lại sự kiện trong ứng dụng.
* Sự kiện **af\_uninstall** được tất cả các đối tác hỗ trợ. Nếu bạn muốn ánh xạ sự kiện với một đối tác, nhưng sự kiện không có trong thẻ Integration của đối tác, hãy liên hệ với CSM của bạn hoặc liên hệ qua [hello@appsflyer.com](mailto:hello@appsflyer.com).

<Tabs>
<Tab title="Firebase">

quy tắc firebase

</Tab>

<Tab title="GCM">

Quy tắc GCM

</Tab>
</Tabs>

<div id="turning-off-uninstall-measurement" />

## Tắt tùy chọn đo lường lượt gỡ cài đặt

<Tabs>
<Tab title="Android">

Nếu bạn cung cấp Mã khóa Máy chủ GCM/Firebase, thì tính năng đo lường lượt gỡ cài đặt ứng dụng được bật theo mặc định. Chủ sở hữu ứng dụng có thể tắt tính năng này thông qua bảng điều khiển.

</Tab>

<Tab title="iOS">

Nếu chứng chỉ P12 được cung cấp và xác thực, tính năng đo lường lượt gỡ cài đặt ứng dụng được bật theo mặc định. Chủ sở hữu ứng dụng có thể tắt tính năng này thông qua bảng điều khiển.

</Tab>
</Tabs>

**Lưu ý:** Để báo cáo lượt gỡ cài đặt, bạn phải bật tính năng **Enable uninstall measurement** ở thời điểm cài đặt ứng dụng. Lượt cài đặt xảy ra khi tính năng **Enable uninstalls measurement** đang tắt sẽ không được báo cáo.

<div id="to-turn-off-uninstall-measurement" />

#### **Để tắt tính năng đo lường lượt gỡ cài đặt**:

1. Trong AppsFlyer, đi tới **App settings** (Cài đặt ứng dụng).
2. Đi đến **Attribution** > **Uninstall measurement** và tắt **Enable uninstall measurement.**

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Lưu ý |
| --- | --- |
| CUID | CUID không được gửi trong các đăng lại lượt gỡ cài đặt. |

</Accordion>

<div data-zendesk-anchors="overview=t%E1%BB%95ng-quan h_01HB8CXQ4824V2WEPYGK8YS4DC=t%E1%BB%95ng-quan how-does-it-work=n%C3%B3-ho%E1%BA%A1t-%C4%91%E1%BB%99ng-nh%C6%B0-th%E1%BA%BF-n%C3%A0o h_01HB8CXQ48JEJECC1HR79DXCRK=n%C3%B3-ho%E1%BA%A1t-%C4%91%E1%BB%99ng-nh%C6%B0-th%E1%BA%BF-n%C3%A0o how-to-use-uninstall-data=c%C3%A1ch-s%E1%BB%AD-d%E1%BB%A5ng-d%E1%BB%AF-li%E1%BB%87u-l%C6%B0%E1%BB%A3t-g%E1%BB%A1-c%C3%A0i-%C4%91%E1%BA%B7t h_01HB8CXQ48E2SRN95MH4E2H7ZH=c%C3%A1ch-s%E1%BB%AD-d%E1%BB%A5ng-d%E1%BB%AF-li%E1%BB%87u-l%C6%B0%E1%BB%A3t-g%E1%BB%A1-c%C3%A0i-%C4%91%E1%BA%B7t h_01HB8CXQ48HX9RH50G45FZMZTK=compare-the-quality-of-sources h_01HB8CXQ48DZYQW7FYBD3XYREM=v%C3%AD-d%E1%BB%A5 h_01HB8CXQ488E22GPCEBE69VQ3M=share-uninstall-data-with-ad-networks-for-optimization h_01HB8CXQ48ZE5TTZRPQE5SEKJS=v%C3%AD-d%E1%BB%A5-1 h_01HB8CXQ48JTET73GH0QQBX5HF=exclude-uninstalls-from-retargeting-campaigns h_01HB8CXQ4832ZHRYQECYCQPP66=v%C3%AD-d%E1%BB%A5-2 setting-up-uninstall-measurement=thi%E1%BA%BFt-l%E1%BA%ADp-%C4%91o-l%C6%B0%E1%BB%9Dng-l%C6%B0%E1%BB%A3t-g%E1%BB%A1-c%C3%A0i-%C4%91%E1%BA%B7t h_01HB8CXQ4810HTB45FAS5ZVRHF=thi%E1%BA%BFt-l%E1%BA%ADp-%C4%91o-l%C6%B0%E1%BB%9Dng-l%C6%B0%E1%BB%A3t-g%E1%BB%A1-c%C3%A0i-%C4%91%E1%BA%B7t implementation-procedures=quy-tr%C3%ACnh-th%E1%BB%B1c-hi%E1%BB%87n h_01HB8CXQ489HRF72VRZ4G532GX=quy-tr%C3%ACnh-th%E1%BB%B1c-hi%E1%BB%87n connect-firebase-cloud-messaging-to-appsflyer-android=k%E1%BA%BFt-n%E1%BB%91i-firebase-cloud-messaging-v%E1%BB%9Bi-appsflyer-android h_01HB8CXQ48ZD5Y0RKTG1W51TKW=k%E1%BA%BFt-n%E1%BB%91i-firebase-cloud-messaging-v%E1%BB%9Bi-appsflyer-android h_01HB8CXQ4865MNVG0VERSNSE3F=http-v1 h_01HB8CXQ48H079WQ6Q6G0XSQC7=legacy-http h_01HB8CXQ48ENMG65YH5ECGST9Z=quan-tr%E1%BB%8Dng configure-uninstall-measurement-in-appsflyer=c%E1%BA%A5u-h%C3%ACnh-%C4%91o-l%C6%B0%E1%BB%9Dng-l%C6%B0%E1%BB%A3t-g%E1%BB%A1-c%C3%A0i-%C4%91%E1%BA%B7t-trong-appsflyer h_01HB8CXQ48CVA9B8B78W0H357C=c%E1%BA%A5u-h%C3%ACnh-%C4%91o-l%C6%B0%E1%BB%9Dng-l%C6%B0%E1%BB%A3t-g%E1%BB%A1-c%C3%A0i-%C4%91%E1%BA%B7t-trong-appsflyer testing-uninstall-measurement=th%E1%BB%AD-nghi%E1%BB%87m-%C4%91o-l%C6%B0%E1%BB%9Dng-l%C6%B0%E1%BB%A3t-g%E1%BB%A1-c%C3%A0i-%C4%91%E1%BA%B7t h_01HB8CXQ48SW2TT5Z85XD3XWT6=th%E1%BB%AD-nghi%E1%BB%87m-%C4%91o-l%C6%B0%E1%BB%9Dng-l%C6%B0%E1%BB%A3t-g%E1%BB%A1-c%C3%A0i-%C4%91%E1%BA%B7t mapping-the-uninstall-event=%C3%A1nh-x%E1%BA%A1-s%E1%BB%B1-ki%E1%BB%87n-g%E1%BB%A1-c%C3%A0i-%C4%91%E1%BA%B7t h_01HB8CXQ499ABX9ZGDFB1VAE8W=%C3%A1nh-x%E1%BA%A1-s%E1%BB%B1-ki%E1%BB%87n-g%E1%BB%A1-c%C3%A0i-%C4%91%E1%BA%B7t limitations=%C4%91i%E1%BB%83m-h%E1%BA%A1n-ch%E1%BA%BF h_01HB8CXQ49F2ARQTEV8Q032P9V=%C4%91i%E1%BB%83m-h%E1%BA%A1n-ch%E1%BA%BF turning-off-uninstall-measurement=t%E1%BA%AFt-t%C3%B9y-ch%E1%BB%8Dn-%C4%91o-l%C6%B0%E1%BB%9Dng-l%C6%B0%E1%BB%A3t-g%E1%BB%A1-c%C3%A0i-%C4%91%E1%BA%B7t h_01HB8CXQ49Y5NCG7GK93HXHYMD=t%E1%BA%AFt-t%C3%B9y-ch%E1%BB%8Dn-%C4%91o-l%C6%B0%E1%BB%9Dng-l%C6%B0%E1%BB%A3t-g%E1%BB%A1-c%C3%A0i-%C4%91%E1%BA%B7t to-turn-off-uninstall-measurement=%C4%91%E1%BB%83-t%E1%BA%AFt-t%C3%ADnh-n%C4%83ng-%C4%91o-l%C6%B0%E1%BB%9Dng-l%C6%B0%E1%BB%A3t-g%E1%BB%A1-c%C3%A0i-%C4%91%E1%BA%B7t h_01HB8CXQ49WXZS4M6CK5XG1BCX=%C4%91%E1%BB%83-t%E1%BA%AFt-t%C3%ADnh-n%C4%83ng-%C4%91o-l%C6%B0%E1%BB%9Dng-l%C6%B0%E1%BB%A3t-g%E1%BB%A1-c%C3%A0i-%C4%91%E1%BA%B7t h_01HB8CXQ4916CJ9NDZWGWQHKSA=traits-and-limitations" />
