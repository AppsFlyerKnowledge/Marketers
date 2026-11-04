---
title: Thử nghiệm tích hợp SDK cho nhà tiếp thị
metadata:
  keywords:
    - Testing
    - SDK
    - Advertisers
    - Debug
    - Debugging
    - redirects test
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-11-12T14:15:08Z'
  edited_at: '2023-11-02T10:24:14Z'
  id: 360001559405
  locale: vi
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/vi/articles/360001559405
---
> **Khái quát:** Thử nghiệm tích hợp ứng dụng Android hoặc iOS của bạn với AppsFlyer.

<div id="note-1" />

<div id="perform-the-integration-tests" />

<div id="prepare-a-test-device" />

<div id="note" />

<div id="testing-using-the-sdk-integration-tests-page" />

<div id="overview" />

## Tổng quan

Tích hợp được thử nghiệm cẩn thận đảm bảo việc thu thập dữ liệu sẽ chính xác và toàn diện. Bằng cách thử nghiệm tích hợp SDK, bạn có thể xác nhận rằng SDK đang giao tiếp thành công với máy chủ AppsFlyer và các lượt cài đặt, sự kiện trong ứng dụng và nhắm mục tiêu lại được ghi nhận và phân bổ chính xác.

Sau khi tích hợp SDK hoàn tất, mọi thành viên nhóm có quyền truy cập bảng điều khiển AppsFlyer đều có thể thực hiện [thử nghiệm cơ bản](/docs/testing-the-sdk-integration-for-marketers#thử-nghiệm-từ-bảng-điều-khiển). Nhà phát triển có thể sử dụng nhật ký gỡ lỗi trong <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integration-testing">môi trường phát triển</Anchor>.

Bài viết này mô tả các quy trình thử nghiệm từ bảng điều khiển và cung cấp các liên kết đến tài liệu mà nhà tiếp thị cần cung cấp cho nhà phát triển.

## Phương thức thử nghiệm

Các phần sau đây mô tả các thử nghiệm khác nhau cần thực hiện và các phương thức có sẵn.

### Thử nghiệm từ bảng điều khiển

Để thử nghiệm tích hợp SDK từ bảng điều khiển, trước tiên bạn phải <Anchor target="_blank" href="/marketers/vi/docs/registering-test-devices">đăng ký thiết bị thử nghiệm</Anchor> (Android hoặc iOS). Điều này cho phép bạn sử dụng cùng một thiết bị nhiều lần và ngăn việc ghi nhận các lượt cài đặt thành lượt cài đặt lại.

Bạn cần thực hiện các thao tác sau:

* Thử nghiệm lượt cài đặt tự nhiên.
* Thử nghiệm chức năng tích hợp cơ bản (lượt cài đặt không tự nhiên, sự kiện trong ứng dụng và nhắm mục tiêu lại).  
  Các phương thức hiện có bao gồm:
  * **[Trang thử nghiệm tích hợp SDK:](/docs/testing-the-sdk-integration-for-marketers#test-using-the-sdk-integration-tests-page)** Trình hướng dẫn trong bảng điều khiển của AppsFlyer hướng dẫn bạn quy trình chạy từng thử nghiệm.
  * [**Thử nghiệm bằng đường dẫn phân bổ:**](/docs/testing-the-sdk-integration-for-marketers#thử-nghiệm-sử-dụng-đường-dẫn-phân-bổ) Tất cả các mạng quảng cáo không phải SRN và các nguồn truyền thông sở hữu đều dựa vào các đường dẫn phân bổ của AppsFlyer; do đó, bạn nên thực hiện thử nghiệm bằng cách sử dụng các đường dẫn phân bổ. Bạn tạo đường dẫn phân bổ, sau đó chạy thử nghiệm để xác minh rằng SDK đang phân bổ lượt cài đặt không tự nhiên và sự kiện trong ứng dụng cho đúng nguồn truyền thông. Ngoài ra, bạn nên chạy thử nghiệm để xác minh rằng [việc nhắm mục tiêu lại](/docs/testing-the-sdk-integration-for-marketers#thử-nghiệm-nhắm-mục-tiêu-lại-bằng-đường-dẫn-phân-bổ) (phân bổ lại và thu hút lại) được ghi nhận và phân bổ chính xác cho các nguồn truyền thông.

<div id="ios-14-testing-consideration" />

<Accordion title="Lưu ý khi thử nghiệm trên iOS 14+">

Bắt đầu từ iOS 14.5, IDFA chỉ khả dụng nếu người dùng đồng ý thông qua lời nhắc Minh bạch về Theo dõi Ứng dụng (ATT). Nếu lời nhắc ATT được triển khai trên ứng dụng, bạn có thể chạy thử nghiệm với tư cách là người dùng đồng ý hoặc không đồng ý.  Để biết thêm thông tin, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/registering-test-devices#đăng-ký-thiết-bị-thử-nghiệm-ios">hướng dẫn</Anchor> đăng ký thiết bị thử nghiệm của bạn có IDFA hoặc IDFV.

</Accordion>

### Thử nghiệm trong môi trường phát triển

Nhà phát triển có thể thực hiện các thao tác sau:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-integration#debug-mode">**Bật và kiểm tra nhật ký gỡ lỗi**</Anchor> và các tình huống thử nghiệm như xác thực mua hàng, dữ liệu chuyển đổi và liên kết sâu.

  > 📘 **Lưu ý**
  >
  > Nếu nhà phát triển của bạn nhận được một phản hồi 403 trong nhật ký, thì có thể là do bạn đang sử dụng gói Zero. Gói này không bao gồm dữ liệu về phân bổ mà chỉ có dữ liệu về lượt nhấp và lượt hiển thị. Để biết thêm thông tin về các gói của chúng tôi, hãy liên hệ với nhóm CEM theo địa chỉ [hello@appsflyer.com](mailto:hello@appsflyer.com) hoặc truy cập <Anchor target="_blank" href="https://www.appsflyer.com/pricing/">bảng giá của AppsFlyer</Anchor>.

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integration-testing#debug-apps">**Tạo ứng dụng gỡ lỗi**</Anchor> để thử nghiệm tích hợp SDK. Khi thực hiện thử nghiệm, dữ liệu sẽ được ghi lại và hiển thị trong bảng điều khiển. Khi dữ liệu được ghi nhận thì không thể xóa. Nếu không muốn dữ liệu thử nghiệm được ghi nhận như một phần của ứng dụng sản xuất thì bạn có thể yêu cầu nhà phát triển thử nghiệm tích hợp SDK bằng cách sử dụng ứng dụng gỡ lỗi. Ứng dụng gỡ lỗi khác với ứng dụng sản xuất ở chỗ ứng dụng này có ID ứng dụng AppsFlyer khác, bảng điều khiển riêng và ứng dụng này không được xuất bản trên các cửa hàng ứng dụng.

#### **Thêm ứng dụng gỡ lỗi vào bảng điều khiển**

Nếu nhà phát triển của bạn tạo ứng dụng gỡ lỗi, bạn phải thêm ứng dụng đó vào bảng điều khiển. Khi nhà phát triển bắt đầu thực hiện thử nghiệm bằng ứng dụng này, thì dữ liệu sẽ hiển thị trong bảng điều khiển của ứng dụng.

Thực hiện một trong các quy trình sau để thêm ứng dụng gỡ lỗi:

<Tabs>
<Tab title="Thêm ứng dụng gỡ lỗi (Android)">

**Để thêm ứng dụng gỡ lỗi vào bảng điều khiển:**

1. Lấy tên gói của ứng dụng gỡ lỗi từ nhà phát triển của bạn và <Anchor target="_blank" href="/marketers/vi/docs/adding-an-app-to-appsflyer">thêm ứng dụng</Anchor> vào bảng điều khiển AppsFlyer của bạn.
2. Đặt trạng thái ứng dụng thành một trong các trạng thái sau:
   * **Chờ phê duyệt**
   * **Chưa xuất bản**

</Tab>

<Tab title="Thêm ứng dụng gỡ lỗi (iOS)">

**Để thêm ứng dụng gỡ lỗi vào bảng điều khiển:**

1. <Anchor target="_blank" href="/marketers/vi/docs/adding-an-app-to-appsflyer">Thêm ứng dụng</Anchor> vào bảng điều khiển AppsFlyer của bạn. ID ứng dụng là ID được cấp cho ứng dụng sau khi ứng dụng được xuất bản trên cửa hàng ứng dụng. Tuy nhiên, vì đây là một ứng dụng gỡ lỗi, nên bạn có thể cung cấp cho nó bất kỳ ID nào bạn muốn miễn là ID đó không thuộc ứng dụng khác. Đảm bảo rằng ID có 9 chữ số và bắt đầu bằng bốn chữ số 1, ví dụ: 111167538. Các con số còn lại phải là ngẫu nhiên.
2. Đặt trạng thái ứng dụng thành một trong các trạng thái sau:
   * **Chờ phê duyệt**
   * **Chưa xuất bản**
3. Cung cấp ID ứng dụng cho nhà phát triển của bạn.

</Tab>
</Tabs>

<div id="traits-and-limitations" />

<div id="note-5" />

<div id="testing-ctv" />

### Các trường hợp thử nghiệm đặc biệt

Các trường hợp thử nghiệm đặc biệt bao gồm:

* **Android TV:** SDK tương thích với TV thông minh dựa trên Android. Nhà tiếp thị hoặc mọi thành viên trong nhóm đều có thể thử nghiệm các ứng dụng TV này bằng cách làm theo các quy trình trong bài viết này.
* **Apple TV (tvOS):** SDK tương thích với Apple TV (tvOS). Nhà tiếp thị hoặc mọi thành viên trong nhóm đều có thể thử nghiệm các ứng dụng TV này bằng cách làm theo các quy trình trong bài viết này.
* **Ứng dụng tvOS chưa được xuất bản:** Yêu cầu nhà tiếp thị và nhà phát triển làm việc cùng nhau (xem <Anchor target="_blank" href="/marketers/vi/docs/testing-tvos-integration-before-publishing">Thử nghiệm tích hợp tvOS trước khi xuất bản</Anchor>).
* **Amazon Fire TV:** Nhà tiếp thị có thể [thử nghiệm tích hợp](/docs/testing-the-sdk-integration-for-marketers#thử-nghiệm-từ-bảng-điều-khiển) bằng phương thức thử nghiệm Android SDK trong bảng điều khiển AppsFlyer. (Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/setting-up-amazon-fire-tv-ad-attribution">phân bổ Amazon Fire TV</Anchor>).
* **Sự kiện web PBA:** Yêu cầu nhà tiếp thị và nhà phát triển làm việc cùng nhau (xem <Anchor target="_blank" href="/marketers/vi/docs/test-pba-web-sdk-integration">Kiểm tra tích hợp SDK web PBA</Anchor>).

<div id="testing-organic-installs" />

## Thử nghiệm chức năng SDK cơ bản

Phần sau đây mô tả các quy trình bạn cần làm theo để thử nghiệm tích hợp SDK cơ bản.

<div id="test-organic-installs" />

<Accordion title="Thử nghiệm lượt cài đặt tự nhiên">

Chúng tôi khuyến cáo bạn nên bắt đầu bằng cách thử nghiệm lượt cài đặt tự nhiên.

**Để thử nghiệm lượt cài đặt tự nhiên:**

1. Cài đặt ứng dụng trên <Anchor target="_blank" href="/marketers/vi/docs/registering-test-devices">thiết bị thử nghiệm đã đăng ký</Anchor>.
2. Khởi chạy ứng dụng.

Bảng điều khiển của ứng dụng sẽ hiển thị một lượt cài đặt tự nhiên mới. Chờ tối đa 30 phút để xuất hiện lượt cài đặt.

![Test_SDK_Organic_install](https://files.readme.io/49c242957324516ba93d6c5ebfa338ec19b05820bcf619d8c39d6f7e4ada9bae-31828925882001.png)

</Accordion>

<div id="test-using-the-sdk-integration-tests-page" />

<Accordion title="Thử nghiệm bằng cách sử dụng trang Thử nghiệm Tích hợp SDK">

Sử dụng trang Thử nghiệm Tích hợp SDK để thử nghiệm lượt cài đặt không tự nhiên, sự kiện trong ứng dụng và liên kết sâu (nhắm mục tiêu lại), đồng thời xác định bất kỳ sự cố tích hợp nào trong dự án của bạn.

**Chỉ dành cho iOS**: Trang SDK integration test chỉ áp dụng cho các ứng dụng iOS triển khai ATT. Bạn có thể thử nghiệm các ứng dụng không triển khai ATT bằng quy trình được nêu cụ thể [tại đây.](https://dev.appsflyer.com/hc/docs/testing-ios#apps-that-dont-implement-att)

**Trước khi bạn bắt đầu:**

1. Chuẩn bị một thiết bị (Android hoặc iOS) chưa cài đặt ứng dụng. Nếu cần, hãy gỡ cài đặt ứng dụng khỏi thiết bị.
2. <Anchor target="_blank" href="/marketers/vi/docs/registering-test-devices">Đăng ký thiết bị làm thiết bị thử nghiệm.</Anchor>

#### **Bước 1: Thử nghiệm lượt cài đặt không tự nhiên**

1. Trong bảng điều khiển, hãy chọn ứng dụng.
2. Đi đến **Integration (Tích hợp) > SDK Integration Tests (Thử nghiệm Tích hợp SDK).**   
   Trang thử nghiệm tích hợp SDK sẽ mở ra.   
   [![](https://files.readme.io/7b2af46dc66530db91c31466b08121673f067ea9188d5bbf7e5f4a4137cbc6e4-115011326025.png)](https://files.readme.io/7b2af46dc66530db91c31466b08121673f067ea9188d5bbf7e5f4a4137cbc6e4-115011326025.png)
3. Chạy thử nghiệm **Lượt Cài đặt Không Tự nhiên**.
4. Chọn một thiết bị thử nghiệm trong danh sách.
5. Chọn cửa hàng để cài đặt ứng dụng:
   * Đối với Android:
     * **Google Play**
     * **Khác** (ví dụ: Ngoài cửa hàng, Android Studio, tệp tin APK)
   * Đối với iOS:
     * **Cửa hàng Ứng dụng**
     * **Khác** (ví dụ: XCode, TestFlight)
6. Quét mã QR bằng thiết bị thử nghiệm đã đăng ký và làm theo hướng dẫn trên thiết bị.

   Lưu ý rằng đối với thiết bị Android, thử nghiệm này sử dụng <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#install-referrer-android-only">phương thức người giới thiệu cài đặt</Anchor> và do đó, đường dẫn phân bổ không bao gồm GAID.
7. Nếu bạn đã chọn **Khác**, hãy cài đặt ứng dụng từ môi trường phát triển của bạn.
8. Đợi cho đến khi lượt cài đặt không tự nhiên được đăng ký trên trang **Thử nghiệm Tích hợp SDK** cho biết thử nghiệm thành công. Thao tác này có thể kéo dài lên tới 2 phút.

   ![NonOrganic_install](https://files.readme.io/3faf784b3d6014e223fdce7b703c6d328ba09af0ea1dde77a8a1f366529e1e00-4406213597585.png)

   Nếu ứng dụng không ghi lại lượt cài đặt không tự nhiên, thì lý do có thể là:
   * IDFA khả dụng nhưng thiết bị thử nghiệm không được <Anchor target="_blank" href="/marketers/vi/docs/registering-test-devices#đăng-ký-thiết-bị-thử-nghiệm-ios">đăng ký với mã định danh này trên trang Thiết bị thử nghiệm</Anchor>.
   * Ứng dụng của bạn có nhiều hơn 1, ngoài ứng dụng thử nghiệm, được cài đặt trên thiết bị thử nghiệm nhưng thiết bị thử nghiệm chưa được <Anchor target="_blank" href="/marketers/vi/docs/registering-test-devices#đăng-ký-thiết-bị-thử-nghiệm-ios">đăng ký với IDFV trên trang Thiết bị thử nghiệm</Anchor>.
   * Lượt cài đặt tự nhiên đã không được ghi nhận.
   * Thử nghiệm được thực hiện trên phiên bản ứng dụng không có SDK.

Đối với lỗi tích hợp, hãy liên hệ với nhà phát triển của bạn.

#### **Bước 2: Thử nghiệm các sự kiện trong ứng dụng**

**Trước khi bạn bắt đầu:**

* Đảm bảo rằng bạn sử dụng cùng một thiết bị thử nghiệm đã được sử dụng để ghi nhận lượt cài đặt không tự nhiên.

1. Chạy thử nghiệm **Sự kiện trong Ứng dụng**.
2. Chọn một thiết bị thử nghiệm trong danh sách, sau đó nhấp vào **Next** (Tiếp theo).
3. Khởi chạy ứng dụng của bạn và bắt đầu tạo các sự kiện trong ứng dụng.
4. Bạn sẽ thấy một bản ghi của những sự kiện này khi chúng được đăng ký trong thời gian thực.

   ![Test_SDK_Integration_Inapp_events](https://files.readme.io/c501389bcbffd2859a2cb20e5232d57218fc0b75875f9425934c56bc13c12968-4406219047825.png)

#### **Bước 3: Thử nghiệm liên kết sâu (nhắm mục tiêu lại)**

**Trước khi bạn bắt đầu:**

* Đảm bảo rằng bạn sử dụng cùng một thiết bị thử nghiệm đã được sử dụng để ghi nhận lượt cài đặt không tự nhiên.
* Khởi chạy ứng dụng thử nghiệm ít nhất 3 lần.
* Để thử nghiệm liên kết sâu (nhắm mục tiêu lại), OneLink phải được xác định cho ứng dụng của bạn. Để biết thêm thông tin, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/create-a-onelink-template">hướng dẫn Thiết lập OneLink</Anchor>.
* Xác nhận rằng tính năng <Anchor target="_blank" href="/marketers/vi/docs/app-settings#reengagement-attribution">nhắm mục tiêu lại</Anchor> đã được bật.

1. Chạy thử nghiệm **Liên kết sâu**.
2. Chọn một thiết bị thử nghiệm trong danh sách.
3. Chọn một loại thử nghiệm:
   * **OneLink:** Chọn OneLink.
   * **Lược đồ URI:** Nhập lược đồ URI (ví dụ: greatapps://cars).
4. Nhấp vào **Next** (Tiếp theo).
5. Quét mã QR bằng thiết bị thử nghiệm đã được đăng ký của bạn và làm theo hướng dẫn trên thiết bị. Sau khi thử nghiệm kết thúc thì Thử nghiệm Liên kết Sâu sẽ được đăng ký là thành công.

   ![TestSDK_DeepLinks_en-us.png](https://files.readme.io/40c26ce173d14bd34771164fa32f6f26e8035fc26d4043fb9c78eef52d6451fa-4406221370385.png)

</Accordion>

<div id="tip" />

<div id="note-3" />

<div id="note-2" />

<div id="testing-using-attribution-links" />

## Thử nghiệm sử dụng đường dẫn phân bổ

Phần sau đây mô tả các quy trình bạn nên thực hiện theo để thử nghiệm lượt cài đặt bằng đường dẫn phân bổ. Bạn có thể thực hiện các thử nghiệm này ngay cả khi ứng dụng vẫn đang chờ xử lý (nghĩa là, không được liệt kê trong Cửa hàng Google Play hoặc Cửa hàng Ứng dụng của Apple).

<div id="test-install-attribution" />

<Accordion title="Thử nghiệm phân bổ lượt cài đặt">

Thử nghiệm lượt cài đặt cho phép bạn xác minh rằng SDK AppsFlyer đang phân bổ các lượt cài đặt một cách chính xác cho các nguồn truyền thông khác nhau.

**Để thử nghiệm phân bổ lượt cài đặt:**

1. Sao chép liên kết sau (Android hoặc iOS) và thực hiện các thay đổi sau đây:
   1. Giá trị **app\_id**: Thêm ID ứng dụng của bạn vào AppsFlyer.
   2. Thông số **pid**: Chỉ định tên của nguồn truyền thông mà lượt cài đặt được phân bổ đến.
   3. Thông số **c**: Chỉ định tên của chiến dịch.
   4. Nếu bạn đang thử nghiệm một ứng dụng có sẵn qua cửa hàng Android của bên thứ ba: hãy thêm thông số <Anchor target="_blank" href="/marketers/vi/docs/set-up-multi-store-android-attribution#single-dashboard-attribution-links">af\_r</Anchor> vào đường dẫn phân bổ.
   5. Thay thế GAID, IDFA hoặc IDFV bằng mã định danh thiết bị cụ thể của bạn.

   <Tabs>
   <Tab title="Android">

   ```http
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&advertising_id=<GAID>
   ```

   </Tab>

   <Tab title="iOS">

   IDFA

   ```http
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&idfa=<IDFA>
   ```

   IDFV

   ```http
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&idfv=<IDFV>
   ```

   </Tab>
   </Tabs>

   Dưới đây là các ví dụ về đường dẫn phân bổ với các giá trị cụ thể:

   <Tabs>
   <Tab title="Android">

   ```http
   https://app.appsflyer.com/com.my.app?pid=Test&c=Test&advertising_id=12345f9*-eba*-421*-876*-7654ac67876*
   ```

   </Tab>

   <Tab title="iOS">

   ```http
   https://app.appsflyer.com/id123456789?pid=Test&c=Test&idfa=1A2B****-9128-4***-123*-04E***654321
   ```

   </Tab>
   </Tabs>

2. Sao chép liên kết đã cập nhật của bạn, gửi đến thiết bị thử nghiệm, sau đó nhấp vào liên kết.

   > 📘 **Lưu ý**
   >
   > Trong iOS, sử dụng iMessage hoặc email để gửi liên kết đến thiết bị. Không dán liên kết vào ứng dụng Ghi chú iOS và nhấp vào liên kết. Thao tác này có thể khiến liên kết bị lỗi.

3. Thực hiện một trong những việc sau:
   * Nếu ứng dụng đang hoạt động, hãy tiếp tục cài đặt.
   * Nếu ứng dụng đang chờ xử lý, thì sẽ xuất hiện thông báo: "*The app you are looking for is not available in the market yet*" (Ứng dụng bạn đang tìm kiếm hiện chưa có sẵn trên thị trường). Đây là kết quả trong dự kiến. Vì ứng dụng không hoạt động nên đường dẫn phân bổ không điều hướng đến bất kỳ cửa hàng ứng dụng nào. Tuy nhiên, đường dẫn phân bổ vẫn hợp lệ cho các mục đích phân bổ và bạn nên cài đặt ứng dụng như sau:
     * **Đối với Android:** Từ tệp tin APK (hoặc Android Studio dành cho nhà phát triển)
     * **Đối với iOS:** Từ TestFlight (hoặc Xcode dành cho nhà phát triển)

   Bạn sẽ thấy một lượt cài đặt được phân bổ cho chiến dịch thử nghiệm trong nguồn truyền thông được gọi là **Test** (Thử nghiệm). Chờ tối đa 30 phút để lượt cài đặt xuất hiện trong bảng điều khiển của ứng dụng. [![Test_Install_Attribution_Link](https://files.readme.io/1771da27f7b8c5334d68c3d7c8361e91e0e35a3a08abf60e3d711f83de9ad22d-31828925861265.png)](https://files.readme.io/1771da27f7b8c5334d68c3d7c8361e91e0e35a3a08abf60e3d711f83de9ad22d-31828925861265.png)

> 👍 **Lời khuyên**
>
> Phần sau mô tả các cách thay thế để xác minh kết quả thử nghiệm của bạn:
>
> * Nếu bạn có quyền truy cập vào báo cáo dữ liệu thô, hãy tải xuống <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">Báo cáo dữ liệu thô lượt cài đặt</Anchor>. Thời gian tải xuống báo cáo này sẽ là vài phút.
>
>   **Để tải xuống báo cáo:**
>
>   1. Trong bảng điều khiển, chuyển đến **Reports** (Báo cáo) > **Export Data** (Xuất Dữ liệu).
>   2. Từ danh sách **Thu hút người dùng (không tự nhiên)**, hãy nhấp vào **Installs** (Cài đặt), sau đó tải xuống báo cáo.
> * Nếu bạn có quyền truy cập vào nhật ký gỡ lỗi, bạn có thể sử dụng <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_app-id-2">API thử nghiệm tích hợp SDK</Anchor> để truy xuất kết quả phân bổ cho một lượt cài đặt cụ thể.

</Accordion>

<div id="test-inapp-events-attribution" />

<Accordion title="Thử nghiệm phân bổ sự kiện trong ứng dụng">

Việc thử nghiệm sự kiện trong ứng dụng cho phép bạn xác nhận rằng doanh thu liên quan đến sự kiện được hiển thị và sự kiện trong ứng dụng được phân bổ cho nguồn truyền thông tạo ra lượt cài đặt.

**Để thử nghiệm phân bổ sự kiện trong ứng dụng:**

1. Khởi chạy ứng dụng, sau đó tạo một vài sự kiện trong ứng dụng.
2. Mở bảng điều khiển của ứng dụng và nhấp vào **Events** (Sự kiện).

   Bạn sẽ thấy các sự kiện, doanh thu của sự kiện (nếu doanh thu được liên kết với các sự kiện) và nguồn truyền thông mà các sự kiện được liên kết đến. Chờ tối đa 60-70 phút để các sự kiện xuất hiện trong bảng điều khiển.

   ![Testing_InAppEvents_Attribution](https://support.appsflyer.com/hc/article_attachments/4406219144593)

**Mẹo!** Nên cân nhắc tải xuống <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">báo cáo dữ liệu thô về sự kiện trong ứng dụng</Anchor> để xác minh rằng các sự kiện được phân bổ chính xác. Thời gian tải xuống báo cáo này sẽ là vài phút.

**Để tải xuống báo cáo:**

1. Trong bảng điều khiển, chuyển đến **Reports** (Báo cáo) > **Export Data** (Xuất Dữ liệu).
2. Trong phần **Raw Data Reports** (Báo cáo Dữ liệu Thô), hãy tải xuống báo cáo dữ liệu thô của sự kiện trong ứng dụng.

</Accordion>

<div id="test-onelink" />

<Accordion title="Thử nghiệm OneLink">

OneLink cho phép bạn đặt một đường dẫn phân bổ duy nhất cho cả Android và iOS. OneLink nhận ra thiết bị của người dùng và chuyển hướng chúng đến cửa hàng ứng dụng thích hợp.

Bên cạnh đó, OneLink cho phép liên kết sâu (deeplinking). Liên kết sâu cho phép bạn mở ứng dụng trong một hoạt động ứng dụng cụ thể trong khi phục vụ nội dung tùy chỉnh.

Để biết thêm thông tin chi tiết, vui lòng xem hướng dẫn của chúng tôi về <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">thử nghiệm các URL OneLink</Anchor>.

</Accordion>

<div id="note-4" />

<div id="testing-retargeting-using-attribution-links" />

## Thử nghiệm nhắm mục tiêu lại bằng đường dẫn phân bổ

Các phần sau đây mô tả các quy trình bạn cần thực hiện theo để thử nghiệm phân bổ nhắm mục tiêu lại.

<div id="about-retargeting-tests" />

<Accordion title="Giới thiệu về thử nghiệm nhắm mục tiêu lại">

Nhắm mục tiêu lại cho phân bổ xảy ra khi người dùng tương tác với chiến dịch nhắm mục tiêu lại bằng cách nhấp vào đường dẫn phân bổ nhắm mục tiêu lại. Điều này dẫn đến sự kiện phân bổ lại hoặc thu hút lại. Để biết thêm thông tin, hãy xem phần <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide">Hướng dẫn nhắm mục tiêu lại cho phân bổ</Anchor>.

Thử nghiệm nhắm mục tiêu lại bao gồm những thao tác sau:

* **[Đối với phân bổ lại:](/docs/testing-the-sdk-integration-for-marketers#test-reattribution)** Gỡ cài đặt và cài đặt lại ứng dụng. Sau đó, xác minh trong bảng điều khiển rằng một lượt cài đặt đã được ghi nhận.
* **[Đối với thu hút lại:](/docs/testing-the-sdk-integration-for-marketers#test-reengagement)** Nhấp vào đường dẫn phân bổ nhắm mục tiêu lại hoặc liên kết sâu, sau đó xác minh rằng lượt thu hút lại được phân bổ cho đúng nguồn truyền thông.

</Accordion>

<div id="prerequisites-to-run-retargeting-tests" />

<Accordion title="Các điều kiện tiên quyết để chạy thử nghiệm nhắm mục tiêu lại">

Trước khi chạy thử nghiệm nhắm mục tiêu lại, cần thiết lập như sau:

* Tính năng nhắm mục tiêu lại phải được kích hoạt cho ứng dụng bạn đang thử nghiệm.
* Tạo liên kết dành riêng cho ứng dụng hoặc truy xuất liên kết tùy chỉnh OneLink. Các liên kết này phải bao gồm thông số nhắm mục tiêu lại.

**Để thiết lập thử nghiệm nhắm mục tiêu lại:**

1. Bật nhắm mục tiêu lại trong cài đặt của ứng dụng.

   Trong bảng điều khiển của ứng dụng, nhấp vào **App Settings** (Cài đặt của Ứng dụng) và bật tùy chọn **Enable retargeting attribution** (Bật nhắm mục tiêu lại cho phân bổ).

   ![Set_Reattribution_window](https://files.readme.io/1fe0c8c4add90c75237b0c5c97b6ff26d8f08ff95bd952912ef746fdec2e9f3d-31828933628561.png)
2. Thực hiện một trong các thao tác sau: 
   * Tạo đường dẫn phân bổ dành riêng cho ứng dụng. Đảm bảo phải bao gồm thông số nhắm mục tiêu lại, `is_retargeting=true` và ID quảng cáo. Để xem GAID, IDFA hoặc IDFV, hãy làm theo hướng dẫn <Anchor target="_blank" href="/marketers/vi/docs/registering-test-devices">Đăng ký thiết bị thử nghiệm</Anchor>.    
     Dưới đây là ví dụ về đường dẫn phân bổ bao gồm thông số dành riêng cho Android làm mã định danh thiết bị (GAID). Để biết thêm thông tin về cách thêm các thông số mã định danh thiết bị khác, chẳng hạn như IDFA hoặc IDFV, hãy xem phần <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters#các-thông-số-cụ-thể-cho-ios">Cấu trúc và thông số đường dẫn phân bổ</Anchor>.

     ```http
     https://app.appsflyer.com/<app_id>?pid=Test&c=Test&is_retargeting=true&advertising_id=<GAID>
     ```
   * Truy xuất <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#tạo-liên-kết-onelink">URL đầy đủ của liên kết tùy chỉnh</Anchor> từ <Anchor target="_blank" href="/marketers/vi/docs/create-a-onelink-template#quy-trình">mẫu OneLink</Anchor>. Đảm bảo kích hoạt <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">Chiến dịch nhắm mục tiêu lại</Anchor>. Hình ảnh sau đây minh họa một ví dụ về URL đầy đủ tùy chỉnh:

     ![Testing_LongLink_en-us.png](https://files.readme.io/19c706b0cc11b83a5cb08d51b3418654c6fa1e597ee7ff9e631db21c33c00b82-31828933632401.png)

Giờ đây, bạn có thể thử nghiệm phân bổ lại và thu hút lại.

</Accordion>

<div id="test-reattribution" />

<Accordion title="Thử nghiệm phân bổ lại">

**Trước khi bạn bắt đầu:**

* Thực hiện theo các [hướng dẫn](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) để thiết lập thử nghiệm nhắm mục tiêu lại.
* Đảm bảo rằng thiết bị thử nghiệm của bạn **chưa được** đăng ký.

**Để thử nghiệm phân bổ lại:**

1. Gỡ cài đặt ứng dụng khỏi thiết bị. Nếu bạn vừa cài đặt ứng dụng, hãy đợi trong vài phút.
2. Sao chép [đường dẫn phân bổ](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) bạn đã tạo trước đây, đường dẫn phân bổ dành riêng cho ứng dụng hoặc đường dẫn đầy đủ tùy chỉnh từ mẫu OneLink, gửi đường dẫn đó đến thiết bị thử nghiệm, sau đó nhấp vào đường dẫn.

   > 📘 **Lưu ý**
   >
   > Trong iOS, sử dụng iMessage hoặc email để gửi liên kết đến thiết bị. Không dán liên kết vào ứng dụng Ghi chú iOS và nhấp vào liên kết. Thao tác này có thể khiến liên kết bị lỗi.

3. Thực hiện một trong những việc sau:
   * Nếu ứng dụng đang hoạt động, hãy tiếp tục cài đặt.
   * Nếu ứng dụng đang chờ xử lý, hãy cài đặt ứng dụng đó như sau:
     * **Đối với Android**: Cài đặt từ Android Studio hoặc tệp tin APK.
     * **Đối với iOS:** Cài đặt từ TestFlight.
4. Mở bảng điều khiển của ứng dụng và trong khung **View type**, hãy chọn **Retargeting**.
5. Trong khung **Attribution type**, hãy chọn **Re-attributions**.

   Bạn sẽ thấy lượt cài đặt được phân bổ cho nguồn truyền thông và chiến dịch. Cho phép tối đa 30 phút để lượt cài đặt nhắm mục tiêu lại xuất hiện trong bảng điều khiển.

   [![Testing_SDK_Reattribution](https://files.readme.io/c5c59709b199262cbefd5cd70ee9fe0db2c788612a8ae6b598c7b2188b696345-small-31828925870609.png)](https://files.readme.io/c5c59709b199262cbefd5cd70ee9fe0db2c788612a8ae6b598c7b2188b696345-small-31828925870609.png)

<div id="tip-1" />

> 👍 **Lời khuyên**
>
> Phần sau mô tả các cách thay thế để xác minh kết quả thử nghiệm của bạn:
>
> * Nếu bạn có quyền truy cập vào báo cáo dữ liệu thô, hãy tải xuống <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">Báo cáo dữ liệu thô lượt chuyển đổi</Anchor>. Thời gian tải xuống báo cáo này sẽ là vài phút.
>
>   **Để tải xuống báo cáo:**
>
>   1. Trong bảng điều khiển, chuyển đến **Reports** (Báo cáo) > **Export Data** (Xuất Dữ liệu).
>   2. Từ danh sách **Nhắm mục tiêu lại**, hãy nhấp vào **Conversions (re-engagements & re-attributions)** (Lượt chuyển đổi (thu hút lại & phân bổ lại)), sau đó tải xuống báo cáo.
> * Nếu bạn có quyền truy cập vào nhật ký gỡ lỗi, bạn có thể sử dụng <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_app-id-2">API thử nghiệm tích hợp SDK</Anchor> để truy xuất kết quả phân bổ cho một lượt cài đặt cụ thể.

</Accordion>

<div id="test-reengagement" />

<Accordion title="Thử nghiệm thu hút lại">

**Trước khi bạn bắt đầu:**

* Thực hiện theo các [hướng dẫn](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) để thiết lập thử nghiệm nhắm mục tiêu lại.
* Vì mục đích thử nghiệm, hãy đặt thời gian tối thiểu giữa các lần chuyển đổi thành **None** (Không). Điều này cho phép tất cả các lượt chuyển đổi thu hút lại được ghi nhận và phân bổ trong quá trình thử nghiệm.

  ![Testing_Reattribution_window](https://files.readme.io/ec8c7c923093dbed0e99aa5ef57d0239217ead5a9db41f42fe4af8a70eb04551-4406211661841.png)
* Đảm bảo ứng dụng được cài đặt trên thiết bị thử nghiệm của bạn và đã được khởi chạy nhiều lần. Nếu bạn vừa cài đặt ứng dụng, hãy đợi trong vài phút.

**Để thử nghiệm mức độ thu hút lại (liên kết sâu trực tiếp):**

Đảm bảo rằng ứng dụng của bạn được cấu hình để <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">liên kết sâu</Anchor>, sau đó làm theo <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">quy trình này</Anchor> để thử nghiệm.

**Để thử nghiệm thu hút lại (liên kết sâu gián tiếp):**

1. Sao chép [đường dẫn phân bổ](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) bạn đã tạo trước đây, đường dẫn phân bổ dành riêng cho ứng dụng hoặc đường dẫn đầy đủ tùy chỉnh từ mẫu OneLink.
2. Gửi đường dẫn này đến thiết bị thử nghiệm của bạn, sau đó nhấp vào đường dẫn.
3. Để mở ứng dụng, hãy thực hiện một trong các thao tác sau:
   * Trong cửa hàng ứng dụng, nhấp vào **Open** (Mở).
   * Khởi chạy ứng dụng từ thiết bị của bạn.

   Trong bảng điều khiển, bạn sẽ thấy mức độ thu hút lại được phân bổ cho nguồn truyền thông và chiến dịch. Chờ tối đa 30 phút để hành động thu hút lại xuất hiện.

   [![Testing_SDK_Re-engagement](https://files.readme.io/5b64b671c8071f871d9835e8df4d89c18d06c85fe996f7227b6ddf429552fccd-small-31828933643153.png)](https://files.readme.io/5b64b671c8071f871d9835e8df4d89c18d06c85fe996f7227b6ddf429552fccd-small-31828933643153.png)

**Mẹo!** Nên cân nhắc tải xuống báo cáo dữ liệu thô về lượt chuyển đổi để xác minh rằng lượt thu hút lại được phân bổ cho đúng nguồn truyền thông. Thời gian tải xuống báo cáo này sẽ là vài phút.

**Để tải xuống báo cáo:**

1. Trong bảng điều khiển, chuyển đến **Reports** (Báo cáo) > **Export Data** (Xuất Dữ liệu).
2. Trong phần **Retargeting** (Nhắm mục tiêu lại), hãy tải xuống báo cáo **Lượt chuyển đổi (thu hút lại và phân bổ lại)**.

</Accordion>

> 📄 **Xem thêm**
>
> * Kiểm tra tích hợp mạng quảng cáo trực tuyến <Anchor target="_blank" href="/partners/vi/docs/getting-started-onboarding-guide-for-ad-networks">Kiểm tra tích hợp mạng quảng cáo trực tuyến</Anchor>

<div data-zendesk-anchors="overview=t%E1%BB%95ng-quan 01H88X11QS2VYFXJGC95TXC6PN=t%E1%BB%95ng-quan testing-methods=ph%C6%B0%C6%A1ng-th%E1%BB%A9c-th%E1%BB%AD-nghi%E1%BB%87m 01H88X11QT88941QB4HAZCSW88=ph%C6%B0%C6%A1ng-th%E1%BB%A9c-th%E1%BB%AD-nghi%E1%BB%87m testing-from-the-dashboard=th%E1%BB%AD-nghi%E1%BB%87m-t%E1%BB%AB-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n 01H88X11QTD9F2QZKV6DWDBQW5=th%E1%BB%AD-nghi%E1%BB%87m-t%E1%BB%AB-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n 01H88X11QTMRBY15M52GRSTFCG=ios-14-testing-consideration testing-in-the-development-environment=th%E1%BB%AD-nghi%E1%BB%87m-trong-m%C3%B4i-tr%C6%B0%E1%BB%9Dng-ph%C3%A1t-tri%E1%BB%83n 01H88X11QTAGR4ETNB7ACWY0TV=th%E1%BB%AD-nghi%E1%BB%87m-trong-m%C3%B4i-tr%C6%B0%E1%BB%9Dng-ph%C3%A1t-tri%E1%BB%83n 01H88X11QT93QAD1KHA64VPFDC=l%C6%B0u-%C3%BD add-debug-apps-to-the-dashboard=th%C3%AAm-%E1%BB%A9ng-d%E1%BB%A5ng-g%E1%BB%A1-l%E1%BB%97i-v%C3%A0o-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n 01H88X11QTVQK5QV767MX0QFC2=th%C3%AAm-%E1%BB%A9ng-d%E1%BB%A5ng-g%E1%BB%A1-l%E1%BB%97i-v%C3%A0o-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n special-test-cases=c%C3%A1c-tr%C6%B0%E1%BB%9Dng-h%E1%BB%A3p-th%E1%BB%AD-nghi%E1%BB%87m-%C4%91%E1%BA%B7c-bi%E1%BB%87t 01H88X11QT72F71N49G65BAEAE=c%C3%A1c-tr%C6%B0%E1%BB%9Dng-h%E1%BB%A3p-th%E1%BB%AD-nghi%E1%BB%87m-%C4%91%E1%BA%B7c-bi%E1%BB%87t testing-basic-sdk-functionality=th%E1%BB%AD-nghi%E1%BB%87m-ch%E1%BB%A9c-n%C4%83ng-sdk-c%C6%A1-b%E1%BA%A3n 01H88X11QTAQ85WBE8RJQK9D74=th%E1%BB%AD-nghi%E1%BB%87m-ch%E1%BB%A9c-n%C4%83ng-sdk-c%C6%A1-b%E1%BA%A3n 01H88X11QTPS13PVCVRHZ1TN50=test-organic-installs 01H88X11QT1ZMAV8JY2840NXM7=test-using-the-sdk-integration-tests-page step-1-test-nonorganic-installs=b%C6%B0%E1%BB%9Bc-1-th%E1%BB%AD-nghi%E1%BB%87m-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-kh%C3%B4ng-t%E1%BB%B1-nhi%C3%AAn 01H88X11QT7RZYYE0EXTPV559P=b%C6%B0%E1%BB%9Bc-1-th%E1%BB%AD-nghi%E1%BB%87m-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-kh%C3%B4ng-t%E1%BB%B1-nhi%C3%AAn step-2-test-inapp-events=b%C6%B0%E1%BB%9Bc-2-th%E1%BB%AD-nghi%E1%BB%87m-c%C3%A1c-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng 01H88X11QTQMZSD152VGEXGK1Z=b%C6%B0%E1%BB%9Bc-2-th%E1%BB%AD-nghi%E1%BB%87m-c%C3%A1c-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng step-3-test-deep-links-retargeting=b%C6%B0%E1%BB%9Bc-3-th%E1%BB%AD-nghi%E1%BB%87m-li%C3%AAn-k%E1%BA%BFt-s%C3%A2u-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i 01H88X11QTEQZK675X3MF4P9GY=b%C6%B0%E1%BB%9Bc-3-th%E1%BB%AD-nghi%E1%BB%87m-li%C3%AAn-k%E1%BA%BFt-s%C3%A2u-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i testing-using-attribution-links=th%E1%BB%AD-nghi%E1%BB%87m-s%E1%BB%AD-d%E1%BB%A5ng-%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95 01H88X11QT0WDRW5GZDCR7MZ3D=th%E1%BB%AD-nghi%E1%BB%87m-s%E1%BB%AD-d%E1%BB%A5ng-%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95 01H88X11QT6YVB3TQ6JEM4G92G=test-install-attribution 01H88X11QTG2NZ3VGMQXJR7368=l%C6%B0u-%C3%BD-2 01H88X11QT5TY25HRTX4RD06C7=l%E1%BB%9Di-khuy%C3%AAn 01H88X11QTRBQQ11C8SAK7DCTC=test-inapp-events-attribution 01H88X11QTJE6HNPDHBMKQMDCP=test-onelink testing-retargeting-using-attribution-links=th%E1%BB%AD-nghi%E1%BB%87m-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i-b%E1%BA%B1ng-%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95 01H88X11QTQ94BAJGEE1V11F6X=th%E1%BB%AD-nghi%E1%BB%87m-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i-b%E1%BA%B1ng-%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95 01H88X11QT4DR3WA6RGB8HDZB3=about-retargeting-tests 01H88X11QTR3AGQHN674ZYEYF7=prerequisites-to-run-retargeting-tests 01H88X11QVFQ6552C272ST108D=test-reattribution 01H88X11QVYBPJPYSPZH2HS308=l%C6%B0u-%C3%BD-2 01H88X11QV5YVR7HCFTGD9BEFJ=l%E1%BB%9Di-khuy%C3%AAn-1 01H88X11QVKAG3JWRQ6KXESTQA=test-reengagement h_01H9FHRVKE88CXGH8G7E26ZXT2=xem-th%C3%AAm" />
