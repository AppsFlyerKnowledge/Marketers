---
title: Cấu hình chiến dịch ironSource
metadata:
  keywords:
    - Supersonic
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-06T10:47:23Z'
  edited_at: '2023-10-16T02:47:35Z'
  id: 208005096
  locale: vi
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/vi/articles/208005096
---
> **Sơ lược:** ironSource, một đối tác tích hợp của AppsFlyer, xây dựng các công cụ kiếm tiền, tương tác, phân tích và khám phá cho các nhà phát triển ứng dụng, nhà sản xuất thiết bị, nhà cung cấp dịch vụ di động và nhà quảng cáo. Ngoài phân bổ trên thiết bị di động dựa trên lượt nhấp chuột, ironSource còn cung cấp chi phí, doanh thu quảng cáo, nhắm mục tiêu lại và phân bổ qua lượt xem mà bạn có thể ghi lại bằng AppsFlyer.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/ironsource.png?v=1" width="213px" />

 Lưu ý: Là một mạng cho tất cả lượt cài đặt, ironSource ưu tiên nhận postback cho tất cả lượt cài đặt mới ứng dụng của bạn từ BẤT KỲ nguồn nào, bao gồm cả nguồn tự nhiên. Để làm vậy, chọn Sự kiện được phân bổ cho bất kỳ đối tác nào để gửi tất cả các postback cài đặt đến ironSource.

Quá trình thiết lập được thực hiện từ trang cài đặt tích hợp đối tác , nhưng để tìm đối tác, trước tiên bạn phải truy cập vào <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations">thị trường</Anchor> (marketplace).

> 📘 **Lưu ý**
>
> Trước khi thiết lập tích hợp, hãy nhớ <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations#liên-hệ-với-đối-tác">liên hệ với đối tác</Anchor> và mở tài khoản với họ.

**Để kích hoạt tích hợp:**

1. Truy cập Marketplace: Trên menu trên cùng của bất kỳ trang AppsFlyer nào, hãy nhấp vào **Marketplace**.
2. Tìm kiếm và chọn đối tác.
3. Nhấp vào **Set up integration**. Bạn được chuyển đến trang thiết lập tích hợp.
4. Trong tab **Integration**, bật **Activate partner**.  
   **Lưu ý:** Nút chuyển đổi phải luôn ở trạng thái bật (<Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">được kích hoạt</Anchor>) trong thời gian bạn làm việc với đối tác.
5. Hoàn thành cấu hình bằng cách sử dụng các tab có liên quan, như được mô tả bên dưới.

Cửa sổ cấu hình của ironSource bao gồm 5 thẻ: Tích hợp (Integration), Đường dẫn phân bổ (Attribution link), Chi phí (Cost), Doanh thu quảng cáo (Ad revenue) và Quyền (Permissions). Nhấp vào các mục bên dưới để đọc về cách thiết lập các thẻ.

Để biết mô tả chi tiết về Tiêu đề Cửa sổ Cấu hình Đối tác, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">đây</Anchor>.

> 👍 **Lời khuyên**
>
> * Bước <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#d">Cài đặt Chung</Anchor> trong thẻ Tích hợp (Integration) là **bắt buộc** với tất cả các đối tác
> * Tất cả các bước còn lại là mô tả hoặc **tùy chọn**

<div id="integration-tab" />

<Accordion title="Thẻ Integration">

### Kích hoạt đối tác

Trong **lần đầu truy cập** tại đây, bạn sẽ cần phải bật **Kích hoạt Đối tác** (Activate Partner) để kích hoạt cài đặt các thông số của thẻ tích hợp (integration). Nút chuyển đổi phải giữ bật chừng nào bạn còn làm việc với đối tác.  
Để biết thêm chi tiết về kích hoạt đối tác, vui lòng nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">đây</Anchor>.

#### Quyền riêng tư Nâng cao

Chỉ với ứng dụng iOS, khi bật **Quyền riêng tư Nâng cao (đối với iOS 14.5+ trở lên)** (Advanced Privacy (for iOS 14.5+ and later)), bạn có thể <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#b">kiểm soát dữ liệu nào được chia sẻ</Anchor> với ironSource qua postback và báo cáo.

### ID Giao dịch

Chỉ với ứng dụng iOS, khi bật **Chia sẻ ID giao dịch SKAN** (Share SKAN transaction ID), bạn sẽ  cho phép AppsFlyer <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">chia sẻ ID giao dịch của các postback SKAdNetwork</Anchor> với ironSource. Theo đó, ironSource có thể giải mã các Giá trị Chuyển đổi SKAdNetwork của bạn.

> 📘 **Lưu ý**
>
> Để biết khả năng tương tác của SKAN với AppsFlyer, hãy liên hệ với quản lý tài khoản ironSource của bạn để <Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/general/universal-skan-reporting/#step-1">kích hoạt gửi dữ liệu SKAN đến các MMP</Anchor>.

### Cài đặt chung

**ID nhà quảng cáo**

ironSource kết nối với AppsFlyer qua một ID nhà quảng cáo duy nhất (số có 6 chữ số) và mật khẩu. Nếu bạn chưa có ID nhà quảng cáo và mật khẩu, bạn phải lấy chúng từ ironSource để tiếp tục với việc tích hợp. Nếu không, sao chép ID và mật khẩu và dán chúng vào các trường tương ứng.

### Phân bổ Lượt cài đặt và Tương tác lại

Hai nút chuyển đổi này cho phép phân bổ đến ironSource các lượt cài đặt mới và tái phân bổ người dùng **đã xem** quảng cáo của bạn nhưng **chưa nhấp** vào quảng cáo. Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/measure-view-through-engagements">phân bổ lượt xem qua</Anchor>.

**Để phân bổ các lượt cài đặt mới:**

1. Bật **Phân bổ xem qua lượt xem cài đặt** (Install view-through attribution).
2. Cấu hình độ dài của cửa sổ xem lại **qua lượt xem** trong [thẻ Đường dẫn phân bổ](/docs/ironsource-campaign-configuration#attribution-link-tab) (Attribution link).

**Để phân bổ lượt tái tương tác mới của người dùng hiện có:**

1. Bật **Phân bổ qua lượt xem tái tương tác** (Re-engagement view-through attribution).
2. Cấu hình độ dài của cửa sổ xem lại **qua lượt xem** trong [thẻ Đường dẫn phân bổ](/docs/ironsource-campaign-configuration#attribution-link-tab) (Attribution link).

### Các bài đăng lại mặc định

Gửi postback tự động đến ironSource sau các lượt cài đặt và tái tương tác người dùng. Sử dụng phần này để xác định **nguồn của người dùng** cho phép gửi các postback này.

Chọn **Chỉ các sự kiện được phân bổ cho đối tác này** (Only events attributed to this partner) cho các sự kiện chỉ đến từ người dùng được phân bổ tới ironSource.  
Chọn **Sự kiện được phân bổ tới bất kỳ đối tác nào hoặc tự nhiên** (Events attributed to any partner, or organic) để cho cả cơ sở người dùng của bạn khả dụng để được báo cáo tới ironSource.

> 📘 **Lưu ý**
>
> Là một mạng cho tất cả lượt cài đặt, ironSource ưu tiên nhận postback cho tất cả lượt cài đặt mới ứng dụng của bạn từ bất kỳ nguồn nào, bao gồm cả nguồn tự nhiên. Để làm vậy, hãy chọn **Sự kiện được phân bổ tới bất kỳ đối tác nào hoặc tự nhiên** (Events attributed to any partner, or organic) để gửi mọi postback cài đặt đến ironSource.

### Đăng lại sự kiện trong ứng dụng

Định cấu hình ánh xạ các sự kiện trong ứng dụng với các sự kiện ironSource, được gửi qua đăng lại:

1. Bật tùy chọn **In-app event postbacks**.
2. Nhấp vào **Add event** để thêm một SDK hoặc sự kiện máy chủ đến máy chủ vào danh sách. Bảng sau đây mô tả các trường cần hoàn thành:  

| Tên thông số | Mô tả |
| --- | --- |
| **Sự kiện AppsFlyer** | Tên của sự kiện mà AppsFlyer nhận được từ SDK sẽ được tích hợp vào ứng dụng của bạn hoặc từ các sự kiện máy chủ đến máy chủ.<br />**Mẹo**: Bạn không thấy sự kiện đang tìm kiếm?<ul><li>Hãy đảm bảo kích hoạt sự kiện trên thiết bị có lượt cài đặt không tự nhiên và kiểm tra lại.</li><li>Nhập vào **AppsFlyer event**, sau đó nhấp vào **Create custom**. Đọc thêm về <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#sự-kiện-tùy-chỉnh">ánh xạ sự kiện tùy chỉnh.</Anchor></li></ul> |
| **mapped to partner event** | Tên hoặc ID duy nhất của từng sự kiện được xác định ở phía đối tác. Các cấu hình ánh xạ có thể có là:<ul><li>**Text field:** Nhận ID sự kiện tương ứng từ đối tác.</li><li>**Drop-down box:** Chọn sự kiện AppsFlyer được xác định trước phù hợp nhất.</li><li>**As is**: Gửi các sự kiện như vốn có mà không ánh xạ tên.</li></ul> |
| **for users from** | Chọn tùy chọn gửi cho sự kiện:<ul><li>**This partner only**: Chỉ gửi các bài đăng lại khi sự kiện này được phân bổ cho đối tác này.</li><li>**All media sources including organic**: Gửi các bài đăng lại cho các sự kiện được phân bổ cho bất cứ đối tác cũng như các sự kiện tự nhiên.</li></ul> |
| **bao gồm** | <ul><li>**No data (default)**: Chỉ gửi sự kiện mà không gửi bất kỳ giá trị sự kiện nào.</li><li>**Values and revenue**: Gửi tất cả các thông số sự kiện, **bao gồm** cả giá trị doanh thu (nếu có trong sự kiện).</li><li>**Values without revenue**: Gửi tất cả các thông số **ngoại trừ** giá trị doanh thu.</li></ul> |

3. [Tùy chọn] Nhấp vào biểu tượng **Add condition**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/a97c5e34c264ddfa9f94b894520f849a3e59b42be14839ee37c71a5b6cc5ebd7-17612766801425.png" width="30px" />để <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#đăng-lại-sự-kiện-trong-ứng-dụng-có-điều-kiện">đặt điều kiện</Anchor> cho một sự kiện.
4. Nhấp vào **Save integration**.
5. [Tùy chọn] Sau khi lưu tích hợp, trong khi vẫn còn ở trang cấu hình, bạn có thể tích hợp thêm ứng dụng của mình với đối tác:
   1. Từ góc trên cùng bên trái, dưới tên đối tác, hãy nhấp vào tên ứng dụng để mở danh sách ứng dụng.
   2. Chọn một ứng dụng khác từ danh sách thả xuống.
   3. Lặp lại <Anchor target="_blank" href="/marketers/vi/docs/amazon-ads-campaign-configuration#integration-tab">các bước tích hợp</Anchor> đối với ứng dụng đã chọn.

> 📘 **Lưu ý**
>
> * Chỉ dành cho ứng dụng iOS: Quyền kiểm soát dữ liệu của bạn được chia sẻ với đối tác thông qua các bài đăng lại và <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions">báo cáo</Anchor> tùy thuộc vào **trạng thái của nút chuyển đổi** <Anchor target="_blank" href="/marketers/vi/docs/tiktok-for-business-advanced-srn-integration-setup#quyền-riêng-tư-nâng-cao">Quyền riêng tư nâng cao (dành cho iOS 14.5+ trở lên)</Anchor>.
> * Bạn có thể gửi <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">đăng lại doanh thu quảng cáo</Anchor> tới ironSource để họ có thể tối ưu hóa các chiến dịch bằng cách sử dụng dữ liệu doanh thu quảng cáo:
>   * **Tên sự kiện:** af\_ad\_revenue
>   * **Đã được ánh xạ tới:** adRevenue

<div id="attribution-link-tab" />

<Accordion title="Thẻ Attribution link">

Tạo và lưu đường dẫn phân bổ và gửi chúng cho đối tác để phân bổ các chiến dịch, nhóm quảng cáo hoặc quảng cáo đơn lẻ - cho cả chiến dịch UA và chiến dịch nhắm mục tiêu lại. Bạn có thể sử dụng đường liên kết một nền tảng hoặc <Anchor target="_blank" href="/marketers/vi/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters">Thông tin thêm về cấu trúc đường dẫn phân bổ và thông số</Anchor>.

**Để tạo một đường dẫn phân bổ,** hãy làm theo <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#attribution-link-tab">các hướng dẫn này</Anchor>.  
Đọc thêm về cách ironSource xác định lượt nhấp chuột và lượt xem.

</Accordion>

<div id="cost-tab" />

<Accordion title="Thẻ Cost">

AppsFlyer nhận thông tin chi phí bằng API. Xem <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">bảng tích hợp chi phí mạng quảng cáo</Anchor> để biết chi tiết đầy đủ về các phương diện, phép đo và tính năng được hỗ trợ. **Lưu ý**: Dữ liệu chi phí yêu cầu phải có đăng ký ROI360.

**Để kích hoạt API chi phí**:

* <Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">Thực hiện theo các hướng dẫn tích hợp này</Anchor>

<Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Xem trạng thái API chi phí của bạn</Anchor> và lần gần nhất AppsFlyer lấy được dữ liệu chi phí phù hợp trong bảng điều khiển trạng thái tích hợp chi phí (và doanh thu quảng cáo) hoặc bảng điều khiển mạng quảng cáo cá nhân.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Thẻ Ad revenue">

Nếu bạn hiển thị quảng cáo trong ứng dụng do đối tác gửi thì phần này có liên quan.

* ironSource cung cấp mức độ chi tiết về doanh thu quảng cáo ở cấp độ người dùng và tổng hợp.
* **Sự khác biệt có thể có khi sử dụng mức độ chi tiết ở cấp người dùng**: Dữ liệu doanh thu quảng cáo được nhận hàng ngày vào lúc 14:00 UTC từ ironSource và chứa dữ liệu của ngày trước đó. ironSource có thể tiếp tục cập nhật dữ liệu sau khi chúng tôi lấy dữ liệu đó. Điều này gây ra sự khác biệt giữa dữ liệu AppsFlyer và ironSource.

Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution">phân bổ doanh thu quảng cáo</Anchor>.

**Để bật API doanh thu quảng cáo**:

* Tuân thủ <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">các hướng dẫn tích hợp này</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Thẻ Permission">

Trong thẻ này, bạn có thể chọn quyền cấp cho ironSource, cho dù đối tác là mạng quảng cáo, đại lý hay thậm chí cả hai. Lưu ý rằng kể cả nếu phân bổ được vô hiệu hóa cho ironSource, thẻ quyền (permissions) sẽ hoạt động và bạn có thể trao quyền kiểm soát cho ironSource.

Sử dụng các tính năng chuyển đổi này để cấp quyền cho mạng quảng cáo xử lý cấu hình riêng cho ứng dụng của bạn:

### Quyền truy cập mạng quảng cáo

* **Allow to configure integration** - cho phép đối tác thiết lập thẻ cấu hình (ngoại trừ đăng lại sự kiện trong ứng dụng)
* **Allow to configure in-app event postbacks** - cho phép đối tác thiết lập ánh xạ đăng lại sự kiện trong ứng dụng lên chính bản thân đối tác trên thẻ integration
* **Allow access to your retention report** - chỉ với dữ liệu lưu trữ của chính đối tác
* **Allow access to your aggregate loyal user data** - chỉ với dữ liệu người dùng trung thành của chính đối tác
* **Allow access to your aggregate in-app events data** - chỉ với dữ liệu sự kiện trong ứng dụng của đối tác
* **Allow access to your aggregate revenue data** - chỉ với dữ liệu doanh thu được phân bổ cho đối tác
* **Allow access to your Protect360 dashboard** - chỉ với dữ liệu Protect360 của chính đối tác và miễn là tính năng được kích hoạt cho nhà quảng cáo

Tìm hiểu thêm về việc cấp <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#permissions-tab">quyền truy cập mạng quảng cáo</Anchor>.

### Cấp quyền cho Đại lý

Sử dụng các công tắc này để cấp quyền cho đại lý xử lý cấu hình của họ cho ứng dụng của bạn:

* **Công tắc chính** - Đặt thành Bật (On) để hiển thị các tùy chọn cấp quyền của đại lý
* **Cho phép truy cập báo cáo giữ chân người dùng** (Allow access to your retention report) - chỉ với dữ liệu giữ chân người dùng của đại lý
* **Cho phép truy cập vào dữ liệu tự nhiên tổng hợp**
* **Cho phép cấu hình các postback sự kiện trong ứng dụng** (Allow to configure in-app event postbacks) - cho phép đối tác thiết lập ánh xạ đăng lại sự kiện trong ứng dụng lên chính bản thân đối tác trên thẻ tích hợp (integration)

Tìm hiểu thêm về cấp <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#cấp-quyền-cho-đại-lý">quyền cho đại lý</Anchor>.

</Accordion>

</Accordion>

<div data-zendesk-anchors="h_01HCFHXQQ8111WGWYVA8FAB8J1=l%C6%B0u-%C3%BD h_01HCFHXQQ8FRF8D22A85PDN1B1=l%E1%BB%9Di-khuy%C3%AAn h_01HCFHXQQ8XYCKWPVTMK8HF165=integration-tab activate-partners=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c h_01HCFHXQQ8HCXPEWR4CWY55M2H=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c advanced-privacy=quy%E1%BB%81n-ri%C3%AAng-t%C6%B0-n%C3%A2ng-cao h_01HCFHXQQ8ABQYRSBGC7Z1F1SV=quy%E1%BB%81n-ri%C3%AAng-t%C6%B0-n%C3%A2ng-cao transaction-id=id-giao-d%E1%BB%8Bch h_01HCFHXQQ8Q3BX7GSGD5MH4QT8=id-giao-d%E1%BB%8Bch h_01HCFHXQQ8D26KT5E6YEQ50DA4=l%C6%B0u-%C3%BD-1 general-settings=c%C3%A0i-%C4%91%E1%BA%B7t-chung h_01HCFHXQQ8J0ZC9FGCNTPMKHK6=c%C3%A0i-%C4%91%E1%BA%B7t-chung install-and-reengagement-attribution=ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-v%C3%A0-t%C6%B0%C6%A1ng-t%C3%A1c-l%E1%BA%A1i h_01HCFHXQQ8V2E8982XRSY4G50F=ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-v%C3%A0-t%C6%B0%C6%A1ng-t%C3%A1c-l%E1%BA%A1i default-postbacks=c%C3%A1c-b%C3%A0i-%C4%91%C4%83ng-l%E1%BA%A1i-m%E1%BA%B7c-%C4%91%E1%BB%8Bnh h_01HCFHXQQ8Q27JXG2V7G4XZX43=c%C3%A1c-b%C3%A0i-%C4%91%C4%83ng-l%E1%BA%A1i-m%E1%BA%B7c-%C4%91%E1%BB%8Bnh h_01HCFHXQQ8XZ6H3733GPR3ZFYE=l%C6%B0u-%C3%BD-2 inapp-event-postbacks=%C4%91%C4%83ng-l%E1%BA%A1i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HCFHXQQ891GH196XFRXY8MYS=%C4%91%C4%83ng-l%E1%BA%A1i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HCFHXQQ8VF25W10CWQHTEAYW=l%C6%B0u-%C3%BD-3 h_01HCFHXQQ8AYNTCH9GHZJG594E=attribution-link-tab h_01HCFHXQQ87EBRW9NBY58XYFGP=cost-tab h_01HCFHXQQ8XZ8XQFH3XRFVHRZV=ad-revenue-tab h_01HCFHXQQ891P7ET9Q4BSQWJXT=permissions-tab ad-network-permissions=quy%E1%BB%81n-truy-c%E1%BA%ADp-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o h_01HCFHXQQ86VNX9WRFEZECYV7R=quy%E1%BB%81n-truy-c%E1%BA%ADp-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o agency-permissions=c%E1%BA%A5p-quy%E1%BB%81n-cho-%C4%91%E1%BA%A1i-l%C3%BD h_01HCFHXQQ936CQ1FVHCRC58H4C=c%E1%BA%A5p-quy%E1%BB%81n-cho-%C4%91%E1%BA%A1i-l%C3%BD" />
