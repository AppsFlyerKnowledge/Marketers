---
title: Hướng dẫn tích hợp SDK Web PBA
metadata:
  keywords:
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-05-17T09:05:30Z'
  edited_at: '2026-08-14T16:22:54Z'
  id: 360001610038
  locale: vi
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/vi/articles/360001610038
---
> **Khái quát:** Tích hợp AppsFlyer vào các trang web sử dụng SDK Web để ghi nhận và đo lường lượt truy cập, sự kiện, lượt chuyển đổi và doanh thu.

[![5107_Infographic_Web_S2S_759x270_option1.jpg](https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg)](https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg)

<div id="advanced-verification-with-smart-banners" />

<div id="advanced-verification-without-smart-banners" />

<div id="standard-with-smart-banners" />

<div id="standard-without-smart-banners" />

<div id="advanced-sdk-verification" />

<div id="standard-web-sdk" />

<div id="important" />

<div id="selecting-a-code-snippet" />

<div id="web-sdk-user-and-integration-guide" />

## Hướng dẫn tích hợp và người dùng SDK Web

* Thẻ JavaScript SDK Web:
  * là một phần của giải pháp Phân bổ trên cơ sở người dùng (PBA) để phân tích hành trình của người dùng trên nhiều nền tảng.
  * báo cáo lượt truy cập và hành động của người dùng trên trang web của bạn cho nền tảng AppsFlyer.
  * là một mô-đun plug-in của trang web không cần lập trình. Nó không cần biết đến hệ điều hành và trình duyệt của khách truy cập trang web.
  * Kích thước: 40-60Kb.
* Triển khai SDK Web cùng với SDK AppsFlyer di động để ghi nhận và lập bản đồ hoạt động của người dùng trên các môi trường web và ứng dụng di động của bạn.
* Các sự kiện xảy ra bên ngoài trang web có thể được ghi nhận bằng cách sử dụng <Anchor target="_blank" href="/marketers/vi/docs/web-server-to-server-events-api-for-pba-web-s2s">API sự kiện từ máy chủ đến máy chủ Web</Anchor> (Web S2S)

<div id="integrating-the-web-sdk-into-the-website" />

## Tích hợp SDK Web vào trang web

<div id="installation-and-integration" />

<Accordion title="Cài đặt và tích hợp">

<div id="considerations-and-actions-required" />

#### Những điều cần lưu ý và hành động cần thiết

| Danh sách kiểm tra tích hợp |
| --- |
| Để đảm bảo rằng các lượt truy cập và sự kiện được ghi nhận, SDK Web phải được cài đặt trên tất cả các trang của trang web. |
| Đặt đoạn mã để đoạn mã để có thể tải càng sớm càng tốt trong phạm vi trang. Có thể thực hiện điều đó bằng cách đặt mã gần đầu thẻ head. |
| Nếu bạn đang tích hợp SDK bằng Trình quản lý Thẻ của Google (GTM):<ul><li>Đảm bảo rằng SDK tải một lần một trang.</li><li>Đặt SDK để tải ngay khi trang tải bằng <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/2772421?hl=en">chế độ ưu tiên GTM</Anchor>.</li></ul> |
| Bạn có thể triển khai SDK Web **có** hoặc **không có** Biểu ngữ Thông minh. Làm theo các hướng dẫn liên quan trong các phần tiếp theo. |
| Các yêu cầu bắt buộc về tích hợp<ul><li>Ghi nhận lượt truy cập</li><li>Ghi nhận sự kiện</li><li>Đặt [Customer User ID](/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid) (CUID)  : Nếu bạn không có CUID, hãy liên hệ với CSM của bạn để trao đổi về các lựa chọn thay thế.</li></ul>Xác thực việc tích hợp bằng <Anchor target="_blank" href="/marketers/vi/docs/test-pba-web-sdk-integration">công cụ thử nghiệm</Anchor> |

**Trước khi bắt đầu, bạn phải**:

* Xác minh với nhà tiếp thị rằng họ đã tạo <Anchor target="_blank" href="/marketers/vi/docs/pba-brand-bundles-and-settings">gói thương hiệu.</Anchor>
* Để biết thêm hướng dẫn bổ sung, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/onboarding-guide-to-people-based-attribution">Hướng dẫn về PBA dành cho người mới bắt đầu</Anchor>.
* Lưu ý: Nếu bạn đã có SDK web Biểu ngữ Thông minh độc lập, hãy xóa đi và thay thế bằng SDK Web cho cả Biểu ngữ Thông minh và Phân bổ trên cơ sở người dùng; đừng chỉ thêm SDK Web độc lập cho PBA.

**Thực hiện như sau:**

* Nhận Dev Key Web của SDK Web. **Lưu ý!** Đây không phải là khóa tương tự được sử dụng bởi các ứng dụng di động.
  * **Để nhận Dev Key Web:**
    1. Trong AppsFlyer, chuyển đến tab **My Apps** (Ứng dụng của Tôi).
    2. Nhấp vào **View brand bundles** (Xem gói thương hiệu).
    3. Sao chép **Dev Key Web được yêu cầu. (WEB\_DEV\_KEY)**
* Nếu bạn triển khai Biểu ngữ Thông minh, hãy lấy khóa Biểu ngữ Thông minh.   
  * **Để lấy Khóa Biểu ngữ Thông minh:**
    1. Trong AppsFlyer, đi đến **Engagement & Deep Linking** (Thu hút & Liên kết Sâu) > **Smart Banners** (Biểu ngữ Thông minh).
    2. Sao chép **Smart Banner Key** (Khóa Biểu ngữ Thông minh) bắt buộc.
* Quyền thêm tập lệnh vào thẻ head trên trang web.
* Nếu bạn sử dụng Trình quản lý Thẻ của Google thì nó phải được tích hợp vào trang web.

**Tiến hành tích hợp SDK web bằng cách sử dụng một trong các tùy chọn sau.**

<Tabs>
<Tab title="Gốc">

<div id="javascript-code-snippet" />

#### Đoạn mã JavaScript

Tích hợp SDK web bằng một trong các phương thức sau.

<div id="to-install-the-web-sdk-without-smart-banners" />

#### **Để cài đặt SDK Web không có Biểu ngữ Thông minh:**

1. Lặp lại quy trình sau trên tất cả các trang trong trang web của bạn.
2. Trong đoạn mã tiếp sau đó, hãy thay thế `WEB_DEV_KEY`  bằng cách sử dụng khóa được chỉ định trong điều kiện tiên quyết.
3. Dán đoạn mã vào thẻ head trên trang web của bạn. Dán vào gần đầu thẻ head.

```html
<script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyer.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
</script>
```

<div id="nonce-with-smart-banners" />

<div id="nonce-without-smart-banners" />

<div id="query-discard-options" />

<div id="advanced-sdk-verification-with-csp-nonce-snippets" />

<div id="content-security-policy-csp" />

<div id="explicit-control" />

<div id="sdk-initial-state-setting" />

<div id="to-implement-the-web-sdk-with-smart-banners" />

#### **Để triển khai SDK Web với Biểu ngữ Thông minh:**

1. Lặp lại quy trình sau trên tất cả các trang trong trang web của bạn.
2. Trong đoạn mã tiếp sau đó, hãy thay thế `WEB_DEV_KEY` và `YOUR_BANNER_KEY` bằng các khóa được chỉ định trong điều kiện tiên quyết.
3. Dán đoạn mã này vào thẻ head của trang web. Dán vào gần đầu thẻ head.

```html
<script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyer.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF", "pba,banners",{pba: {webAppId: "WEB_DEV_KEY"}, banners: {key: "YOUR_BANNER_KEY"}});
AF('banners', 'showBanner');
</script>
```

</Tab>

<Tab title="Trình quản lý Thẻ của Google">

**Để triển khai SDK web với Trình quản lý Thẻ của Google (GTM):**  

1. <Anchor target="_blank" href="https://developers.google.com/tag-manager/quickstart">Đi đến Trình quản lý Thẻ của Google.</Anchor>
2. Tạo thẻ mới cho SDK web AppsFlyer.  

   [![](https://files.readme.io/bd695bcbaf3983aac809cb7e1d63af0b89a08cea1751bbd8c2fc39863182fe7a-360002745245.png)](https://files.readme.io/bd695bcbaf3983aac809cb7e1d63af0b89a08cea1751bbd8c2fc39863182fe7a-360002745245.png)
3. Chọn loại thẻ **Custom HTML** (HTML Tùy chỉnh).
4. Đặt tên có ý nghĩa cho thẻ.
5. Thực hiện một trong những việc sau:
   * Nếu bạn đang tích hợp SDK web **mà không có** Biểu ngữ Thông minh:
     1. Dán đoạn mã sau vào cửa sổ **Tag Configuration** (Cấu hình Thẻ).
     2. Trong đoạn mã, hãy thay thế `WEB_DEV_KEY` bằng cách sử dụng khóa được đề cập trong điều kiện tiên quyết.  

        ```javascript
        <!-- AppsFlyer web SDK -->
        <script>
        !function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
        (t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
        t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
        o.src="https://websdk.appsflyer.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
        p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
        </script>
        ```
   * Nếu bạn đang tích hợp SDK web **có** Biểu ngữ Thông minh:
     1. Dán đoạn mã sau vào cửa sổ **Tag Configuration** (Cấu hình Thẻ).
     2. Trong đoạn mã, hãy thay thế `WEB_DEV_KEY` và `YOUR_BANNER_KEY` bằng các khóa được đề cập trong điều kiện tiên quyết.  

        ```javascript
        <!-- AppsFlyer web SDK -->  
        <script>
        !function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
        (t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
        t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
        o.src="https://websdk.appsflyer.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
        p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF", "pba,banners",{pba: {webAppId: "WEB_DEV_KEY"}, banners: {key: "YOUR_BANNER_KEY"}});
        AF('banners', 'showBanner');
        </script>
        ```
6. Nhấp vào **Save** (Lưu).
7. Thực hiện một trong những việc sau:
   * **Để thêm trình kích hoạt cho tất cả các trang:**
     1. Nhấp vào **Add Trigger** (Thêm Trình kích hoạt).

        [![gtm-af-tag-sdk-trigger.png](https://files.readme.io/9cae70cdc376e57d3458fab80f8b9e57aa6981a3f3029c17d32e96b5f569fc28-360007722757.png)](https://files.readme.io/9cae70cdc376e57d3458fab80f8b9e57aa6981a3f3029c17d32e96b5f569fc28-360007722757.png)
     2. Chọn **All Pages** (Tất cả các Trang).
     3. Nhấp vào **Save** (Lưu).
     4. Nhập tên thẻ, nhấp vào **Save** (Lưu).  
        Bạn đã hoàn quy trình.
   * **Để thêm trình kích hoạt vào các trang cụ thể:**

     1. Nhấp vào **Save Tag** (Lưu Thẻ).
     2. Trong cửa sổ chính của GTM, hãy chọn **Triggers** (Trình kích hoạt).Nhấp vào **New** (Mới).
     3. Nhấp vào biểu tượng cây bút.
     4. Chọn loại trình kích hoạt **Page View** (Lượt Xem trang).  
        [![PBAselectTrigger_us-en.jpg](https://files.readme.io/e62926fed956da9f3fcbf04f818858c69f07cbac892fafd839451c73d72a6741-360007811677.jpg)](https://files.readme.io/e62926fed956da9f3fcbf04f818858c69f07cbac892fafd839451c73d72a6741-360007811677.jpg)
     5. Chọn **Some Page Views** (Một số Lượt xem Trang).
     6. Đặt trang và điều kiện trình kích hoạt nếu cần.
     7. Nhấp vào **Save** (Lưu).
     8. Liên kết trình kích hoạt với thẻ SDK Web AppsFlyer. Cách thực hiện:
        1. Trong cửa sổ chính của GTM, chọn Tags (Thẻ).
        2. Chọn thẻ bạn đã tạo trước đó.
        3. Trong bảng kích hoạt, hãy nhấp vào bút.
        4. Chọn trình kích hoạt lượt xem trang mà bạn đã tạo trước đó.  

           [![](https://files.readme.io/c4e9b2e4b4d3ce6b7377d419070be650e758eddcdf5603fa5f3c65560402f1d7-360002745305.png)](https://files.readme.io/c4e9b2e4b4d3ce6b7377d419070be650e758eddcdf5603fa5f3c65560402f1d7-360002745305.png)
        5. Nhấp vào **Save** (Lưu).

</Tab>

<Tab title="Trình quản lý Thẻ Khởi chạy Adobe">

1. [Tạo thuộc tính trong Adobe Experience Cloud](/docs/pba-web-sdk-integration-guide#create-a-property-in-adobe-experience-cloud)
2. [Thêm SDK Web vào thuộc tính Khởi chạy Adobe](/docs/pba-web-sdk-integration-guide#add-the-web-sdk-to-the-adobe-launch-property)
3. [Thêm thẻ Khởi chạy Adobe vào trang web](/docs/pba-web-sdk-integration-guide#add-the-adobe-launch-tag-to-the-website)
4. [Phát hành môi trường Khởi chạy Adobe](/docs/pba-web-sdk-integration-guide#publish-the-adobe-launch-environment)

<div id="create-a-property-in-adobe-experience-cloud" />

<Accordion title="Tạo thuộc tính trong Adobe Experience Cloud">

![adobe_create_property.png](https://files.readme.io/1f97d619d5fdfe47b1dd1a2e17c0169e939c32bcda62580ba259d6e86f61d6c2-20260884824209.png)

1. Đi đến **Adobe Experience Cloud** > **Launch** (Khởi chạy).
2. Trong mục **Adobe Experience Cloud Launch** (Khởi chạy Adobe Experience Cloud), nhấp vào **Go to Launch** (Đi tới mục Khởi chạy).
3. Nhấp vào **New Property** (Thuộc tính Mới).
4. Đặt tên cho thuộc tính.
5. Trong mục **Platform** (Nền tảng), chọn **Web**.
6. Nhập miền trang web của bạn.
7. Nhấp vào **Save** (Lưu).

</Accordion>

<div id="add-the-web-sdk-to-the-adobe-launch-property" />

<Accordion title="Thêm SDK Web vào thuộc tính Khởi chạy Adobe">

<Image alt="web_property_rules.png" src="https://files.readme.io/5f592f3ce1f5b319c8f6f96a6235618d884a4faccb1387b1f22c1fd2ce662d15-360006168098.png" width="491px" />

1. Trên trang **My web property** (Thuộc tính web của tôi), hãy chọn tab **Rules** (Quy tắc).
2. Đặt tên cho quy tắc. Nên sử dụng, **Load web SDK** (Tải SDK web).
3. Trong phần **IF** (NẾU), bên dưới **EVENTS** (SỰ KIỆN), nhấp vào **+Add** (+Thêm).
   * Trong **Event Type** (Loại Sự kiện), chọn **Core - DOM Ready**
   * Nhấp vào **Keep Changes** (Lưu Thay đổi).
4. Trong phần **THEN** (THÌ), bên dưới **Actions** (Hoạt động), nhấp vào **+Add** (+Thêm).
   * Trong mục **Action Type** (Loại Hành động) > **Custom Code** (Mã Tùy chỉnh).
   * Chọn **JavaScript** > **Open Editor** (Mở Trình chỉnh sửa) và dán đoạn mã SDK Web **không có thẻ &lt;script>**.
   * Nhấp vào **Keep Changes** (Lưu Thay đổi) để đóng trình chỉnh sửa mã.
5. Nhấp vào **Save** (Lưu).

</Accordion>

<div id="add-the-adobe-launch-tag-to-the-website" />

<Accordion title="Thêm thẻ Khởi chạy Adobe vào trang web">

[![adobe_tag.png](https://files.readme.io/4da5418fc3f2591d15fe68ea1d0451f2b393cb177ae4309d5d431259e2d4003f-small-20260884828049.png)](https://files.readme.io/4da5418fc3f2591d15fe68ea1d0451f2b393cb177ae4309d5d431259e2d4003f-small-20260884828049.png)

1. Trên trang **My web property** (Thuộc tính web của tôi), chọn tab **Environments** (Môi trường).
2. Tìm đến hàng có môi trường bạn muốn phát hành (phát triển hoặc sản xuất).
   * Dưới tiêu đề **INSTALL** (CÀI ĐẶT), nhấp vào biểu tượng hộp trên hàng liên quan; đây thường là một môi trường sản xuất.
   * Xem phần về phát hành môi trường **Adobe Launch**.
3. Trong hộp thoại **Web Install Instructions** (Hướng dẫn Cài đặt Web):
   * Sao chép đoạn mã tập lệnh.
   * Đóng hộp thoại.
4. Dán đoạn mã vào thẻ &lt;head> của trang web.

</Accordion>

<div id="publish-the-adobe-launch-environment" />

<Accordion title="Phát hành môi trường Adobe Launch">

[![adobe_publishing_env.png](https://files.readme.io/863b7c81a9f90d774f7f4388a22db3420dca5c5db632efc6c0dc40783702f418-small-20260884829329.png)](https://files.readme.io/863b7c81a9f90d774f7f4388a22db3420dca5c5db632efc6c0dc40783702f418-small-20260884829329.png)

1. Trên trang **My web property** (Thuộc tính web của tôi), đi đến tab **Publishing** (Phát hành).
2. Trong phần **Development** (Phát triển), nhấp vào **Add New Library** (Thêm Thư viện Mới).
   * Đặt tên cho thư viện và chọn một môi trường.
   * Trong mục **RESOURCE CHANGES** (THAY ĐỔI TÀI NGUYÊN), nhấp vào **Add a Resource** (Thêm Tài nguyên).
   * Nhấp vào **Rules** (Quy tắc) > **Load web SDK** (Tải SDK web) > **Latest** (Mới nhất) > **Select & Create a New Revision** (Chọn & Tạo Bản sửa đổi Mới).
   * Nhấp vào **Save** (Lưu).
3. Trong phần **Development** (Phát triển):
   * Bên cạnh thư viện mới tạo, hãy nhấp vào menu Action (Hành động) (3 chấm) > chọn **Build for Development** (Xây dựng để Phát triển).
   * Nhấp lại vào menu hành động > chọn **Submit for Approval** (Gửi để Phê duyệt).
4. Trong phần **Submitted** (Đã gửi):
   * Nhấp vào hành động > chọn **Build for Staging** (Xây dựng để Kiểm thử).
   * Nhấp lại vào hành động > chọn **Approve for Publishing** (Phê duyệt để Phát hành).
5. Trong phần **Approved** (Được Phê duyệt):
   * Nhấp vào hành động > chọn **Build & Publish to Production** (Xây dựng & Phát hành đến Sản xuất).
   * Đến đây, quá trình đã hoàn tất.

</Accordion>

Khi trang web tải trên thiết bị di động, các nội dung quảng cáo đang hoạt động sẽ hiển thị trong biểu ngữ. Để hiển thị biểu ngữ trên các trang cụ thể hoặc theo hành động của người dùng, hãy xem <Anchor target="_blank" href="https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html">quy tắc Khởi chạy Adobe</Anchor>.

</Tab>
</Tabs>

</Accordion>

<div id="ensure-that-the-sdk-is-working" />

<Accordion title="Đảm bảo rằng SDK đang hoạt động">

Sau khi cài đặt, hãy xác nhận rằng SDK web AppsFlyer được trình duyệt của khách truy cập gọi và đang gửi thông báo. Có thể thực hiện thao tác này bằng cách kiểm tra kết nối mạng thông báo được báo cáo trong trình duyệt.

**Để đảm bảo rằng SDK sẽ tải và đang hoạt động:**

1. Đi đến trang web.
2. Mở công cụ dành cho nhà phát triển trong trình duyệt.

   ![WebSDK_us-en.jpg](https://files.readme.io/5550f0ee8c1a5852a983e6482cb0489696b669ffe5fade49d2308ee32f57201b-360009548497.jpg)
3. Đi đến tab (A) **Network** (Mạng).
4. Làm mới trang.
5. Lọc theo (B) **wa.appsflyer**.
6. Chọn (C) thông báo **sự kiện**.
7. Trong tab tiêu đề (D), hãy đảm bảo rằng:
   * **URL yêu cầu** là wa.appsflyer.com/events.
   * thông số truy vấn site\_id= `WEB_DEV_KEY`.
   * (E) **mã trạng thái là 200**.
8. Xác minh rằng giá trị của site\_id bằng với giá trị của `WEB_DEV_KEY` trong cài đặt gói thương hiệu:
   1. Trong AppsFlyer, đi tới **Configuration** (Cấu hình) > **Brand Bundles** (Gói Thương hiệu).
   2. Nhấp vào **Web dev key,** như vậy sẽ sao chép mã khóa này.
   3. Dán mã khóa vào bất kỳ vị trí nào (tab trình duyệt mới, notepad) để hiển thị mã khóa.
   4. Xác minh rằng site\_id và `WEB_DEV_KEY` khớp nhau.
9. Đảm bảo rằng SDK chỉ tải một lần. Việc tải nhiều SDK có thể khiến SDK ngừng hoạt động.

</Accordion>

<div id="sending-events-optinoptout" />

<Accordion title="Gửi sự kiện lựa chọn tham gia/lựa chọn không tham gia">

![5578-VistiorPrivacyOptIn_us-en.png](https://files.readme.io/cd6cbcaeb7f831f4efe74a9a6c6b20d5095602e7edf4dd38becd90864e73c2fb-360010263157.png)

SDK Web gửi dữ liệu sự kiện của khách truy cập tới AppsFlyer. Bạn có thể kiểm soát, dừng hoặc bắt đầu sự kiện như được mô tả trong phần này.

Cân nhắc:

* **Cài đặt trạng thái ban đầu của SDK**: Xác định xem SDK có gửi các sự kiện khi tải trang web ban đầu hay không hay liệu SDK phải đợi cho đến khi bạn đưa ra một lệnh cụ thể để bắt đầu gửi các sự kiện. Cài đặt chứa trong đoạn mã web này.
* **Kiểm soát cụ thể:** Sử dụng để dừng hoặc bắt đầu gửi sự kiện. Ví dụ: nếu bạn triển khai biểu ngữ lựa chọn tham gia/lựa chọn không tham gia dữ liệu (còn được gọi là biểu ngữ chấp thuận cookie), hãy tích hợp các lệnh cụ thể vào các tùy chọn kiểm soát biểu ngữ của bạn để bắt đầu và dừng gửi sự kiện. Kiểm soát cụ thể có mức độ ưu tiên hơn so với cài đặt trạng thái ban đầu SDK và sử dụng cookie liên tục của bên thứ nhất có các đặc điểm sau:  
  * Đặt miền trang web.
  * Hết hạn sau một khoảng thời gian do SDK Web đặt hoặc do trình duyệt xác định. Sau khi cookie hết hạn, SDK Web sẽ trở về cài đặt trạng thái ban đầu.
  * Cookie SDK Web không ảnh hưởng và luôn tuân theo cài đặt cookie dành riêng cho trình duyệt.

| Cài đặt | Đoạn mã bắt buộc |
| --- | --- |
| [Mặc định] Gửi sự kiện | Thực hiện thay đổi sau đối với đoạn mã SDK Web.Nếu cần, hãy thêm thông số measurementStatus:<br /><br />Đặt measurementStatus=true<br /><br />`{pba:{webAppId: "********-****-****-*****************",measurementStatus:true}` |
| Không gửi sự kiện | Thực hiện thay đổi sau đối với đoạn mã SDK Web. Nếu cần, hãy thêm thông số measurementStatus:<br /><br />Đặt measurementStatus=false  <br />  <br />`{pba: {webAppId: "********-****-****-*****************",measurementStatus:false}` |

| Tùy chọn | Lệnh |
| --- | --- |
| Bắt đầu gửi sự kiện (lựa chọn tham gia) | `window.AF_SDK.PLUGINS.PBA.enableMeasurement()` |
| Dừng gửi sự kiện (lựa chọn không tham gia) | `window.AF_SDK.PLUGINS.PBA.disableMeasurement()` |

</Accordion>

<div id="implement-a-content-security-policy-csp-policy" />

<Accordion title="Triển khai chính sách Chính sách Bảo mật Nội dung (CSP)">

Một số quản trị viên web yêu cầu phải bảo mật Javascript bằng CSP của họ. Bạn có thể sử dụng một số cơ chế CSP để thực hiện điều này, bao gồm bất kỳ cơ chế nào sau đây:

* CSP sử dụng *self*
* CSP sử dụng nonce: Nối lệnh nonce vào thẻ script bằng cách sử dụng giá trị nonce ngẫu nhiên do bạn tạo.

  ```html
  <script nonce="random value generated by you">
  !function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
  ....
  </script>
  ```

</Accordion>

<div id="discard-query-params" />

<Accordion title="Loại bỏ thông số truy vấn">

Nếu các thông số truy vấn của bạn chứa dữ liệu mà bạn không muốn AppsFlyer ghi lại, thì bạn có thể chỉ thị nền tảng AppsFlyer loại bỏ một số hoặc tất cả các thông số truy vấn. Bằng cách đó, chúng sẽ không xuất hiện trong dữ liệu thô hoặc các báo cáo.

Bạn có thể thực hiện các phương thức được mô tả liên quan đến url, người giới thiệu và header\_referer.

| Phương thức | Mô tả |
| --- | --- |
| Loại bỏ tất cả các thông số truy vấn | Nối `af_url=true` vào url |
| Loại bỏ các thông số truy vấn đã chỉ định | Bằng cách cài đặt mặt nạ thông số truy vấn, bạn sẽ chỉ định thông số nào cần được loại bỏ.  Đặt mặt nạ loại bỏ bằng cách sử dụng `af_url_mask=param` trong đó param là tên thông số.<br /><br />Ví dụ: <br /><br />**Url có mặt nạ:**<br /><br />`param1=value1&param2=value2&param3=value3&af_url_mask=param2;param3`<br /><br />**Url sau khi loại bỏ:**<br /><br />**`param1=value1&af_url_mask=param2;param3`** |

</Accordion>

<div id="principles-of-event-recording" />

## Nguyên tắc ghi nhận sự kiện

<div id="conversion-and-standard-events" />

<Accordion title="Sự kiện chuyển đổi và tiêu chuẩn">

* Các sự kiện của người dùng được SDK ghi nhận, sẽ gửi sự kiện đến nền tảng AppsFlyer.
* Sử dụng danh sách <Anchor target="_blank" href="/marketers/vi/docs/pba-brand-bundles-and-settings#web-event-settings">sự kiện chuyển đổi</Anchor> do nhà tiếp thị đặt, AppsFlyer chia các sự kiện thành các sự kiện chuyển đổi và tiêu chuẩn.
* Dữ liệu sự kiện chuyển đổi có sẵn trong các bảng điều khiển PBA.
* Dữ liệu sự kiện chuyển đổi và tiêu chuẩn có sẵn trong <Anchor target="_blank" href="/marketers/vi/docs/pba-raw-data-reports">báo cáo dữ liệu thô.</Anchor>

<div id="conversion-events" />

### Sự kiện chuyển đổi

* Sự kiện chuyển đổi cung cấp thông tin chi tiết về nỗ lực tiếp thị và kinh doanh của bạn. Các sự kiện chuyển đổi bao gồm mua, tải xuống, đăng ký và đặt mua dài hạn.
* PBA phân bổ các sự kiện chuyển đổi cho nguồn truyền thông đã thúc đẩy người dùng truy cập trang web.
* Bằng cách xác định nguồn truyền thông được phân bổ, bạn có thể đo lường và phân biệt được chất lượng của người dùng do các nguồn truyền thông khác nhau mang lại.
* Sự kiện chuyển đổi được sử dụng để ghi nhận doanh thu và tính toán ROI.
* Sử dụng chúng để so sánh ngân sách quảng cáo cho các nguồn truyền thông cụ thể so với doanh thu được tạo ra từ người dùng đến từ các nguồn truyền thông này.

<div id="standard-events" />

### Sự kiện tiêu chuẩn

* Các sự kiện tiêu chuẩn được sử dụng để xác thực hành trình của người dùng và các kênh đưa đến lượt chuyển đổi.
* Sử dụng chúng để đo lường hoạt động của người dùng và đánh dấu các nguồn truyền thông mang đến người dùng bị thu hút.
* Ghi nhận hoạt động của người dùng để đánh dấu người dùng cho các chiến dịch thu hút lại.

<div id="recording-events" />

### Ghi nhận sự kiện

Kích hoạt SDK web để ghi nhận các sự kiện khi đáp ứng các điều kiện nhất định, chẳng hạn như khi tải trang đích hoặc khi người dùng tương tác với các phần tử của trang web. Xem [các ví dụ về ghi nhận sự kiện](/docs/pba-web-sdk-integration-guide#ghi-nhận-sự-kiện).

</Accordion>

<div id="identifying-users-using-customer-user-id-cuid" />

<Accordion title="Xác định người dùng bằng customer user ID (CUID)">

* Người dùng web được xác định trong AppsFlyer bằng cách sử dụng CUID duy nhất mà bạn phân bổ cho họ. Thông thường, CUID được quản lý bởi các máy chủ backend của bạn.
* Sử dụng cùng một giá trị CUID mà bạn sử dụng trong môi trường di động.Bằng cách đó, bạn sẽ có được cái nhìn tổng thể về hoạt động của người dùng trên nhiều nền tảng. Chức năng trong SDK dành cho thiết bị di động là hàm setCustomerUserId(<Anchor target="_blank" href="/marketers/vi/docs/customer-user-id-field-cuid#ios-sdk-developer-instructions">iOS</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/customer-user-id-field-cuid#android-sdk-developer-instructions">Android,</Anchor> Unity).
* Để đặt CUID trong SDK web:
  * Đặt CUID tại điểm sớm nhất mà bạn có quyền truy cập vào. Điều này thường có nghĩa là bạn cần phải đợi người dùng xác định thông qua đăng nhập hoặc đăng ký.
  * Kích hoạt lệnh gọi JavaScript tới setCustomerUserId() như được hiển thị trong ví dụ sau.   
    Lưu ý! Gửi CUID dưới dạng một chuỗi ngay cả khi nó là dạng số. Thực hiện bằng cách đặt CUID vào dấu ngoặc kép.
* Nếu bạn triển khai S2S web, hãy lưu ý rằng bạn có thể cần thông báo cho PBA khi bạn <Anchor target="_blank" href="/marketers/vi/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method">liên kết</Anchor> CUID với id khách truy cập web trong phần backend của bạn.
* CUID không được chứa <Anchor target="_blank" href="/marketers/vi/docs/customer-user-id-field-cuid#cuid-design-and-privacy">thông tin cá nhân có thể nhận dạng trực tiếp</Anchor> như số điện thoại hoặc địa chỉ email.

**Ví dụ: đặt CUID**

```javascript
// Liên kết tất cả sự kiện web của người dùng hiện tại với ID 663274 riêng 
AF('pba', 'setCustomerUserId' , '663274')
```

</Accordion>

<div id="web-sdk-event-parameters" />

<Accordion title="Thông số sự kiện SDK Web">

| Tên thông số | Bắt buộc | Mô tả |
| --- | --- | --- |
| eventType | Có | Loại sự kiện<br /><br />Định dạng: Chuỗi<br /><br />Luôn điền thông số này với SỰ KIỆN.<br /><br />Ví dụ: eventType: "EVENT" (SỰ KIỆN) |
| Tên của sự kiện | Có | Tên của sự kiện<br /><br />Định dạng: Chuỗi<br /><br />Ví dụ: Mua hàng, Đặt mua dài hạn |
| ~~eventCategory~~ | Không | Thông số này không còn được hỗ trợ nữa và sẽ bị xóa khỏi hệ thống vào một ngày sẽ được công bố. Thay vào đó, hãy sử dụng thông số eventValue. |
| ~~eventLabel~~ | Không | Thông số này không còn được hỗ trợ nữa và sẽ bị xóa khỏi hệ thống vào một ngày sẽ được công bố. Thay vào đó, hãy sử dụng thông số eventValue. |
| eventRevenue | Không | Doanh thu được chỉ định cho một sự kiện chuyển đổi<br /><br />Định dạng: Động |
| eventRevenueCurrency | Không | Tiền tệ doanh thu<ul><li>Mã tiền tệ 3 ký tự <Anchor target="_blank" href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</Anchor></li><li>Mặc định: USD</li></ul>Định dạng: Chuỗi |
| Giá trị của sự kiện | Không | Bản đồ các thông số sự kiện mô tả sự kiện. Sử dụng thông số này để gửi các sự kiện phong phú trong ứng dụng như SKU sản phẩm, giá của mục hàng.<br /><br />Định dạng: JSON<br /><br />**Ví dụ:** Để gửi SKU ABC123, có màu xanh lam và đơn giá là $3,99<br /><br />`{"sku": "ABC123", “color": "blue", "unit_price":3.99,"currency": "USD"}`<br /><br />**Giới hạn:** 1000 ký tự. Không được vượt quá mức này, vì nội dung sẽ bị cắt bớt. |

</Accordion>

<div id="recording-event-scenarios" />

<Accordion title="Ghi nhận các tình huống sự kiện">

Sự kiện ví dụ

```javascript
// purchase event of shoes with associated revenue
AF('pba', 'event', {eventType: 'EVENT', eventName: 'purchase', eventRevenue: 12, eventValue: {"key1": 123, "key2": "name"}});
```

Các sự kiện mà bạn gửi phụ thuộc vào bản chất của ứng dụng web của bạn. Ví dụ: một ứng dụng cửa hàng trực tuyến yêu cầu một tập hợp các sự kiện khác với một đơn vị đưa tin. Xem các tình huống sau để biết các sự kiện bạn nên gửi và thời điểm gửi.

<div id="online-store" />

#### Cửa hàng trực tuyến

Giả sử bạn đang quản lý một cửa hàng trực tuyến. Một số sự kiện tiêu chuẩn mà bạn có thể muốn ghi nhận sẽ là:

* Tìm kiếm: sự kiện tiêu chuẩn
* Thêm vào giỏ hàng: sự kiện tiêu chuẩn
* Xóa khỏi giỏ hàng: sự kiện tiêu chuẩn
* Mua hàng: sự kiện chuyển đổi

Đơn vị đưa tin

Giả sử bạn đang quản lý một cửa hàng mới. Một số sự kiện mà bạn có thể muốn ghi nhận sẽ là:

* Đăng ký: sự kiện chuyển đổi
* Mua gói đặt mua dài hạn: sự kiện chuyển đổi

</Accordion>

<div id="ensuring-that-events-are-sent" />

<Accordion title="Đảm bảo rằng các sự kiện được gửi đi">

Phần này dành cho các nhà phát triển web.

<Anchor target="_blank" href="/marketers/vi/docs/test-pba-web-sdk-integration">Thử nghiệm tích hợp SDK web PBA:</Anchor> xem các sự kiện thử nghiệm theo thời gian thực.

**Để đảm bảo rằng các sự kiện được gửi đến AppsFlye**r:

1. Mở trang web.
2. Mở công cụ dành cho nhà phát triển trong trình duyệt.
   * <Anchor target="_blank" href="https://developers.google.com/web/tools/chrome-devtools/open#console">Cách mở công cụ dành cho nhà phát triển trong Chrome</Anchor>
   * <Anchor target="_blank" href="https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/Web_Inspector_Tutorial/EnableWebInspector/EnableWebInspector.html">Cách mở các công cụ dành cho nhà phát triển trong Safari</Anchor>
3. Chuyển sang tab Network (Mạng).
4. Kích hoạt sự kiện.
5. Lọc theo thông báo.

   ![pba_af_event.png](https://files.readme.io/394f43890d1aaf09114054a3bca1a003178526e768a5da0b554dbc8d63ef1eb4-360003502238.png)
6. Tìm kiếm một yêu cầu mạng bắt đầu bằng đích wa.appsflyer.com (xem ảnh chụp màn hình bên dưới).
7. Đảm bảo rằng:
   1. Mã trạng thái là 200.
   2. Tải trọng Yêu cầu phù hợp với các thông số trong sự kiện.

</Accordion>

<div id="examples" />

## Ví dụ:

<div id="recording-events::f1e16eae" />

<Accordion title="Ghi nhận sự kiện">

Mã được cung cấp chỉ dành cho mục đích minh họa. Không sử dụng y nguyên mã này.

* Giả định: SDK Web đã được trang tải vào thời điểm sự kiện được gửi.
* Các tình huống ví dụ chứa mã để ghi nhận các sự kiện khi:
  * trang đích tải.
  * người dùng tương tác với trang web.

<Tabs>
<Tab title="Ghi nhận sự kiện gốc">

**Ghi nhận các sự kiện khi trang đích tải**

* Bạn có một trang đặt mua dài hạn cho các bản tin và bạn muốn ghi nhận đặt mua dài hạn.
* Bạn cũng có thể thiết lập trang cảm ơn và chuyển hướng người dùng đến trang đó sau khi họ đăng ký.

```html
<html>
    <head>
        <!-- Assume that the server returns a response with details about the newly subscribed user -->
        <!-- Alternatively, you can extract data from localStorage or cookies,
            in case data was set in either of them during the subscription process
        -->
        <script>window.onload = function(){
            AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category': 'holiday_promotion', eventValue: {'label' : 'newspaper'}, eventName: 'subscription',}); } </script> </head> <body> <h1>Thank You for Subscribing to Our Newsletter</h1> </body> </html>
```

* Mã trước chứa một trang HTML cơ bản. Trang web cần tải SDK Web để bạn gửi các sự kiện.
* Khi trang tải, sau khi người dùng được chuyển hướng đến trang đó, phương thức tải cửa sổ gọi ra phương thức AF() để gửi sự kiện đặt mua dài hạn đến AppsFlyer.

**Ghi nhận các sự kiện khi người dùng tương tác với trang web**

* Bạn có một trang web Thương mại điện tử và bạn muốn ghi nhận các sự kiện thanh toán.
* Khi người dùng nhấp vào nút thanh toán, SDK Web sẽ gửi một sự kiện đến AppsFlyer.

```html
<html>
<head>
    <!-- Assume that data about products in the shopping cart
    is stored in localStorage -->
    <script>
        window.onload = function () {
            document.getElementById('checkout').addEventListener('click', function () {
                AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'});
            });
        }
    </script>
</head>
<body>
    <h1>Shopping Cart</h1>
    <h2>Shirt</h2>
    <p>
        <ul>
            <li>Color: Blue</li>
            <li>Quantity: 2</li>
            <li>Price: $20</li>
        </ul>
    </p>
    <h2>Pants</h2>
    <p>
        <ul>
            <li>Color: Black</li>
            <li>Quantity: 3</li>
            <li>Price: $15</li>
        </ul>
    </p>
    <button id='checkout'>Checkout</button>
</body>
</html>
```

Đoạn mã trước ở trên hiển thị một trang HTML cơ bản. Trang web cần tải SDK Web để bạn gửi các sự kiện.

* Sau khi tải trang, phương thức liên kết trình nghe nhấp chuột vào nút **Checkout** (Thanh toán).
* Khi người dùng nhấp vào nút **Checkout** (Thanh toán), hàm gọi lại sẽ:
  * tìm nạp dữ liệu từ localStorage.
  * gọi ra phương thức AF() và chuyển dữ liệu cho nó.
* Phương thức AF() gửi sự kiện đến AppsFlyer.

</Tab>

<Tab title="Ghi nhận sự kiện trong Trình quản lý Thẻ">

**Ghi nhận các sự kiện khi trang đích tải**

* Bạn có một trang đặt mua dài hạn cho các bản tin và bạn muốn ghi nhận các lượt đặt mua dài hạn thành công.
* Bạn thiết lập một trang cảm ơn mà người dùng được chuyển hướng đến sau khi đăng ký thành công.

1. Thiết lập một trang cảm ơn  

   ```html Markup
   <html>
   <head>
       <script>
            // Google Tag Manager loads the Web SDK
           <script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
           new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
           j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
           'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
           })(window,document,'script','dataLayer','GTM-XXXX');
       </script>
        <script>
           // Assume that the server returns a response with details about the newly subscribed user
           function getResponseFromServer() {
               return JSON.stringify({ action: 'subscribe', category: 'site actions', label: userEmail })
           }
           //Alternatively, you can extract data from localStorage or cookies,
           //in case data was set in either of them during the subscription process
           localStorage.setItem('data', JSON.stringify({ action: 'subscribe', category: 'site actions', label: 'user@email.com' }));
       </script>
   </head>
   <body>
       <h1>Thank You for Subscribing to Our Newsletter</h1>
   </body>
   </html>
   ```

   Mã trước đó tải GTM, sau đó sẽ tải SDK Web. Sau đó, hai hành động khác diễn ra trong tập lệnh. Một là hàm nhận phản hồi từ máy chủ với thông tin chi tiết về người dùng. Hai là thiết lập dữ liệu thành bộ nhớ cục bộ. GTM có quyền truy cập vào cả hàm và localStorage. Bạn có thể gọi ra hàm và truy cập localstorage bằng GTM.
2. Thêm thẻ mới để phân bổ các lượt đặt mua dài hạn sau khi tải trang cảm ơn  

   [![](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
3. Đặt tên riêng cho thẻ và chọn tùy chọn loại thẻ **Custom HTML** (HTML Tùy chỉnh).
4. Cho mã sau vào **Custom HTML** (HTML Tùy chỉnh).  

   ```html
   <script> 
   AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'subscription'}); </script>
   ```

   ![gtm_tag_after_subscribe.png](https://files.readme.io/6cf080f94a97a7f38c50899a93d154320995e91f60963c075a5dd03b3a080408-360003515298.png)
5. Mở rộng tùy chọn điều khiển **Advanced Settings** (Cài đặt Nâng cao) và sau đó là tùy chọn điều khiển **Tag Sequencing** (Sắp xếp thứ tự Thẻ) bên dưới vùng văn bản và đảm bảo tùy chọn đó được thiết lập để kích hoạt chuyển đổi sau khi thẻ được thực thi.  

   [![](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)](//hc/article_attachments/360002902065/gtm_fire_before.png)
6. Để kích hoạt thẻ chuyển đổi, hãy đặt một trình kích hoạt. Trong ví dụ này, trình kích hoạt được kích hoạt khi tải trang Thank you (Cảm ơn).  

   [![](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)

**Ghi nhận các sự kiện khi người dùng tương tác với trang web**

* Bạn có một trang web Thương mại điện tử và bạn muốn ghi nhận các sự kiện thanh toán.
* Khi người dùng nhấp vào nút thanh toán, SDK Web sẽ gửi một sự kiện đến AppsFlyer.

1. Thiết lập trang thanh toán  

   ```html Markup
   <html>
   <head>
       <script>
           // Google Tag Manager loads the Web SDK
           <script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
           new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
           j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
           'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
           })(window,document,'script','dataLayer','GTM-XXXX');
       </script>
   </head>
   <body>
       <h1>Shopping Cart</h1>
       <h2>Shirt</h2>
       <p>
           <ul>
               <li>Color: Blue</li>
               <li>Quantity: 2</li>
               <li>Price: $20</li>
           </ul>
       </p>
       <h2>Pants</h2>
       <p>
           <ul>
               <li>Color: Black</li>
               <li>Quantity: 3</li>
               <li>Price: $15</li>
           </ul>
       </p>
       <button id='checkout'>Checkout</button>
   </body>
   </html>
   ```

   Đoạn mã trước tải SDK Web bằng GTM Phần còn lại chỉ đơn giản là HTML mô phỏng trang giỏ hàng. Chú ý nút **Checkout** (Thanh toán) có ID thanh toán. Yêu cầu ID này khi thiết lập GTM để xử lý lượt nhấp vào nút đó.
2. Trong GTM, nhấp vào **Variables** (Biến), **Configure** (Cấu hình) rồi chọn **Click Element** (Phần tử Nhấp) trong danh sách **Built-In Variables** (Biến Tích hợp).  

    [![gtm-create-variable.png](https://files.readme.io/2f38308b4e4b9f279420f0219b220f2796d337a39a79241861c3d31bdb442b24-360002899569.png)](https://files.readme.io/2f38308b4e4b9f279420f0219b220f2796d337a39a79241861c3d31bdb442b24-360002899569.png)
3. Tạo một biến mới, đặt tên có ý nghĩa và chọn loại **All Elements**(Tất cả các Phần tử)  
   [![gtm-checkout-all-elements.png](https://files.readme.io/1c370646a4c21dc0fcb8351c756a9fdc81a1a8039d0557b716bc8a4ae51a3fad-360002899589.png)](https://files.readme.io/1c370646a4c21dc0fcb8351c756a9fdc81a1a8039d0557b716bc8a4ae51a3fad-360002899589.png).
4. Trong cấu hình trình kích hoạt, hãy chọn **Some Clicks** (Một số Lượt nhấp), **Click Element** (Phần tử Nhấp) **phù hợp với Bộ chọn CSS** của #checkout.  

    [![gtm-checkout-click-elememt.png](https://files.readme.io/a101d6c27438d3e05eed9db7ea58b57df8bba9a92d4f9e30caee005366dbcf8c-360002903565.png)](https://files.readme.io/a101d6c27438d3e05eed9db7ea58b57df8bba9a92d4f9e30caee005366dbcf8c-360002903565.png)
5. Tạo thẻ mới cho hành động thanh toán, chọn loại HTML Tùy chỉnh và đặt trình kích hoạt thành trình kích hoạt thanh toán.  

   ```html
   <script>
    AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'}); </script>
   ```

   ![gtm-checkout-tag.png](https://files.readme.io/8d3f99dcd3c3ff8df9e6fc13076b798237b86f8cbc5bbd26f349fa9948edb0d6-360003431857.png)

</Tab>
</Tabs>

* Đảm bảo rằng thẻ hàm SDK web được tải trước khi sự kiện được kích hoạt
* Không gửi các ký tự đặc biệt trong giá trị sự kiện, chẳng hạn như ký hiệu tiền tệ trong giá trị doanh thu.
* Chuỗi giá trị phải ngắn hơn 50 ký tự.

</Accordion>

<div id="setting-customer-user-id-after-signup" />

<Accordion title="Đặt customer user ID sau khi đăng ký">

Mã được cung cấp trong các ví dụ này chỉ để tham khảo. Không sử dụng y nguyên mã này. Nếu bạn không chắc chắn về cách sử dụng mã này, hãy tham khảo ý kiến nhà phát triển web của bạn. 

Giả định: SDK Web được tải bởi trang trước khi sự kiện được gửi đi; đừng tải lại SDK.

Tình huống người dùng:

* Có người dùng đăng ký vào trang web của bạn.
* Mã trang web thu thập thông tin chi tiết người dùng và gửi đến máy chủ của bạn.
* Máy chủ tạo CUID duy nhất cho người dùng đó.
* Trong trang cảm ơn sau khi đăng ký, bạn truy vấn máy chủ về CUID mới.
* Bằng cách sử dụng phản hồi của máy chủ, bạn đặt CUID AppsFlyer bằng phương thức SDK Web setCustomerUserId().

<Tabs>
<Tab title="Native">

Thiết lập trang đăng ký:

```html Markup
<html>
<head>
    <!-- The Web SDK script loads first -->
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyer.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        };
    // This function stores the user email sent to the server after the user reaches the thank you page
    // The response from the server is a unique CUID that should be set using the web SDK setCustomerUserId method
        function storeUserEmail (){
            var userEmail = document.getElementById('email').value;
            localStorage.setItem('user_email', userEmail);
        }
    </script>
</head>
<body>
    <h1>Sign Up</h1>
    <form onsubmit="storeUserEmail()" action="/signup" method="post">
        <div><label>Name</label>
            <input type="text" name="name" id="name"></div>
        <br />
        <div> <label>Email</label>
            <input type="email" name="email" id="email"></div>
        <br />
        <input type="submit" id="submit">
    </form>
</body>
</html>
```

Mã trước ở trên là một biểu mẫu đăng ký đơn giản. Khi biểu mẫu được gửi, email được lưu trữ trong localStorage. Khi người dùng đến trang cảm ơn, địa chỉ email của người dùng sẽ được gửi đến máy chủ để tạo CUID duy nhất cho địa chỉ email đó.

Thiết lập trang cảm ơn cho những người dùng đăng ký:

```html Markup
<html>
<head>
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyer.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        // Using the fetch API to send the user email to the server
        // and get the unique user id in return	
        window.onload = function () {
            var userEmail = localStorage.getItem('user_email');
            fetch('users/' + userEmail).then(function (res) {
                   res.text().then(function (id) {
                    console.log(id);
                    AF('pba', 'setCustomerUserId', id);
                });
            });
        }  </script> 
     </head> 
     <body> 
        <h1>Thank You for Signing Up!</h1> 
     </body> 
</html>
```

Đoạn mã sử dụng API tìm nạp. Đoạn mã này sẽ gửi cho máy chủ địa chỉ email được nhập bởi người dùng. Giả sử rằng máy chủ tạo cho người dùng một CUID duy nhất khi đăng ký, việc gửi địa chỉ email đến máy chủ là nhằm mục đích nhận một CUID duy nhất. Máy chủ phản hồi bằng một CUID duy nhất và CUID duy nhất này là giá trị được chuyển bằng phương thức setCustomerUserId.

</Tab>

<Tab title="Google Tag Manager">

1. Thiết lập trang đăng ký:

   ```html Markup
   <html>
   <head>
       <script>  
            // Google Tag Manager loads the Web SDK
           (function (w, d, s, l, i) {
               w[l] = w[l] || []; w[l].push({
                   'gtm.start':
                       new Date().getTime(), event: 'gtm.js'
               }); var f = d.getElementsByTagName(s)[0],
                   j = d.createElement(s), dl = l != 'dataLayer' ? '&l=' + l : ''; j.async = true; j.src =
                       'https://www.googletagmanager.com/gtm.js?id=' + i + dl; f.parentNode.insertBefore(j, f);
           })(window, document, 'script', 'dataLayer', 'GTM-5VJ6C7R');  

       // This function stores the user email to be sent to the server after the user reaches the thank you page
       // the response from the server is a unique CUID that should be used in the web SDK setCustomerUserId method
           function storeUserEmail (){
               var userEmail = document.getElementById('email').value;
               localStorage.setItem('user_email', userEmail);
           }
       </script>
   </head>
   <body>
       <h1>Sign Up</h1>
       <form onsubmit="storeUserEmail()" action="/signup" method="post">
           <div><label>Name</label>
               <input type="text" name="name" id="name"></div>
           <br />
           <div> <label>Email</label>
               <input type="email" name="email" id="email"></div>
           <br />
           <input type="submit" id="submit">
       </form>
   </body>
   </html>
   ```

   Đoạn mã trên là một biểu mẫu đăng ký đơn giản. Khi biểu mẫu được gửi đi, địa chỉ email được lưu trữ trong localStorage. Khi người dùng đến trang cảm ơn, địa chỉ email của người dùng sẽ được gửi đến máy chủ để lấy CUID duy nhất cho email đó.
2. Thiết lập trang cảm ơn cho những người dùng đăng ký:

   ```html Markup
   (t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
   t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
   o.src="https://websdk.appsflyer.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
   p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
       </script>
       <script>
           // using the fetch api to send the user email to the server
           // and get the unique user id in return 
           window.onload = function () {
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
                  res.text().then(function (id) {
                  console.log(id);
                  AF('pba', 'setCustomerUserId', id);
               });
            });
           } </script> 
       </head>
       <body> 
               <h1>Thank You for Signing Up!</h1> 
        </body> 
    </html>
   ```

   Mã trước là trang cảm ơn có trình kích hoạt GTM gửi cho máy chủ địa chỉ email do người dùng cung cấp trong biểu mẫu đăng ký.  
   Giả sử rằng khi đăng ký, máy chủ sẽ tạo một người dùng có CUID duy nhất.  
   Gửi email đến máy chủ nhằm mục đích nhận một CUID duy nhất.  
   Máy chủ phản hồi bằng một CUID duy nhất được gửi bằng phương thức setCustomerUserId().  
   Tiếp tục quy trình này để tạo trình kích hoạt và tab.
3. Thêm thẻ mới để phân bổ các lượt đặt mua dài hạn sau khi tải trang cảm ơn.[![](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
4. Đặt tên riêng cho thẻ và chọn tùy chọn loại thẻ “Custom HTML” (HTML Tùy chỉnh)[![GoogleTag.jpg](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)

   ```html
   <script>
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
            res.text().then(function (id) {
                  console.log(id);
                  AF('pba', 'setCustomerUserId', id);
               });
            });
   </script>
   ```
5. Mở rộng tùy chọn điều khiển **Advanced Settings** (Cài đặt Nâng cao) và sau đó là tùy chọn điều khiển **Tag Sequencing** (Sắp xếp thứ tự Thẻ) bên dưới vùng văn bản và đảm bảo tùy chọn đó được thiết lập để kích hoạt chuyển đổi sau khi thẻ được thực thi.  

   [![](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)](//hc/article_attachments/360002902065/gtm_fire_before.png)
6. Đặt trình kích hoạt cho thẻ chuyển đổi để cho biết khi nào thẻ chuyển đổi sẽ được kích hoạt (trong ví dụ bên dưới, thẻ này được kích hoạt khi tải trang "Cảm ơn")  

   [![](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)

</Tab>
</Tabs>

Hàm setCustomerUserId có thể được gửi ở bất kỳ giai đoạn nào trong luồng người dùng, ví dụ: sau khi người dùng đăng nhập và đăng ký. AppsFlyer sử dụng CUID được gửi gần đây nhất để cập nhật người dùng hiện tại đang được quan sát cho các điểm tiếp xúc và sự kiện trong quá khứ hoặc tương lai.

Sử dụng cùng một giá trị CUID như bạn đã làm trong hàm setCustomerUserId trong ứng dụng dành cho thiết bị di động (xem setCustomerUserId dành cho thiết bị di động cho: <Anchor target="_blank" href="/marketers/vi/docs/customer-user-id-field-cuid#ios-sdk-developer-instructions">iOS</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/customer-user-id-field-cuid#android-sdk-developer-instructions">Android,</Anchor> Unity)

</Accordion>

<div id="addtional-information" />

## Thông tin bổ sung

<div id="web-sdk-cookies" />

<Accordion title="Cookie SDK Web">

Các cookie được liệt kê trong bảng sau do SDK Web đặt hoặc sử dụng trên trang web của bạn.

Trong bảng sử dụng các từ viết tắt sau:

* AMP: Trang Nhanh cho Thiết bị di động (Accelerated Mobile Pages)
* CDN: Mạng Phân phối Nội dung (Content Delivery Network)
* 3PC: Cookie của Bên Thứ ba (Third-party Cookies)

| Tên cookie | Miền | Thời gian sử dụng | Chi tiết |
| --- | --- | --- | --- |
| afUserid | Miền trang web của bạn | không phải AMP | Xác định người dùng trong trường hợp các sự kiện điều hướng và tải web |
| AF\_SYNC | Miền trang web của bạn | không phải AMP | <ul><li>Cờ hiệu cho biết rằng mã định danh người dùng cuối cùng đã được đặt</li><li>Điều này được tận dụng để giảm thời gian tải trang web</li></ul> |
| af\_id | appsflyer.com | không phải AMP khi 3PC được phép | Xác định người dùng trong trường hợp các sự kiện điều hướng và khởi chạy ứng dụng |
| af\_id | onelink.me | không phải AMP khi 3PC được phép | Liên kết các hành động thu hút với biểu ngữ, thu hút với onelink hoặc cả hai với các sự kiện khởi chạy ứng dụng. |
| amp-afUserid | AMP CDN hoặc miền trang web của bạn | Đối với dịch vụ trang của AMP |  |

</Accordion>

<div id="release-notes" />

<Accordion title="Ghi chú phát hành">

| Ngày | Phiên bản | Lưu ý |
| --- | --- | --- |
| 01/07/2021 | 1.0 | [Loại bỏ thông số truy vấn](/docs/pba-web-sdk-integration-guide#discard-query-params) |
| 01/06/2021 | 1.0 | [Thực hiện Chính sách Bảo mật Nội dung (CSP)](/docs/pba-web-sdk-integration-guide#implement-a-content-security-policy-csp-policy) |
| 31/08/2020 | 1.0 | [Đã thêm chức năng lựa chọn tham gia và lựa chọn không tham gia](/docs/pba-web-sdk-integration-guide#sending-events-optinoptout) |
| Ngày 16 tháng 04 năm 2020 | 1.0 | Hàm customerUserId () thay thế sự kiện IDENTIFY để gửi CUID duy nhất |
| Ngày 30 tháng 7 năm 2020 | 1.0 | <ul><li>Bắt đầu/dừng kiểm soát cụ thể để gửi sự kiện</li><li>Thay đổi trạng thái mặc định ban đầu</li></ul> |

</Accordion>

<div id="deprecations" />

<Accordion title="Ngừng hỗ trợ">

* Thông báo ngừng hỗ trợ nêu rõ ý định của chúng tôi về việc ngừng hỗ trợ một tính năng hoặc phương thức. Tính năng hoặc phương thức sẽ tiếp tục hoạt động cho đến ngày ngừng hỗ trợ.
* Hãy coi các thông báo ngừng hỗ trợ là cơ hội để thực hiện các thay đổi đối với mã của bạn.

| Ngày ngừng hỗ trợ | Ngày ngừng hỗ trợ | Chi tiết |
| --- | --- | --- |
| Ngày 16 tháng 04 năm 2020 | Sẽ được công bố | **Phương thức không còn được hỗ trợ:** Gửi customer user ID (CUID) trong thông số sự kiện customUserId với eventType được đặt thành "IDENTIFY" (XÁC ĐỊNH)<br /><br />**Phương thức hiện tại:** Gửi CUID bằng cách sử dụng hàm setCustomerUserId(). |

</Accordion>

<div data-zendesk-anchors="web-sdk-user-and-integration-guide=h%C6%B0%E1%BB%9Bng-d%E1%BA%ABn-t%C3%ADch-h%E1%BB%A3p-v%C3%A0-ng%C6%B0%E1%BB%9Di-d%C3%B9ng-sdk-web integrating-the-web-sdk-into-the-website=t%C3%ADch-h%E1%BB%A3p-sdk-web-v%C3%A0o-trang-web considerations-and-actions-required=nh%E1%BB%AFng-%C4%91i%E1%BB%81u-c%E1%BA%A7n-l%C6%B0u-%C3%BD-v%C3%A0-h%C3%A0nh-%C4%91%E1%BB%99ng-c%E1%BA%A7n-thi%E1%BA%BFt javascript-code-snippet=%C4%91o%E1%BA%A1n-m%C3%A3-javascript to-install-the-web-sdk-without-smart-banners=%C4%91%E1%BB%83-c%C3%A0i-%C4%91%E1%BA%B7t-sdk-web-kh%C3%B4ng-c%C3%B3-bi%E1%BB%83u-ng%E1%BB%AF-th%C3%B4ng-minh to-implement-the-web-sdk-with-smart-banners=%C4%91%E1%BB%83-tri%E1%BB%83n-khai-sdk-web-v%E1%BB%9Bi-bi%E1%BB%83u-ng%E1%BB%AF-th%C3%B4ng-minh principles-of-event-recording=nguy%C3%AAn-t%E1%BA%AFc-ghi-nh%E1%BA%ADn-s%E1%BB%B1-ki%E1%BB%87n conversion-events=s%E1%BB%B1-ki%E1%BB%87n-chuy%E1%BB%83n-%C4%91%E1%BB%95i standard-events=s%E1%BB%B1-ki%E1%BB%87n-ti%C3%AAu-chu%E1%BA%A9n recording-events=ghi-nh%E1%BA%ADn-s%E1%BB%B1-ki%E1%BB%87n online-store=c%E1%BB%ADa-h%C3%A0ng-tr%E1%BB%B1c-tuy%E1%BA%BFn examples=v%C3%AD-d%E1%BB%A5 addtional-information=th%C3%B4ng-tin-b%E1%BB%95-sung" />
