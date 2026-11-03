---
title: Cấu hình chiến dịch của Unity Ads
metadata:
  keywords:
    - Unity Ads
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
  created_at: '2016-03-06T10:05:52Z'
  edited_at: '2023-11-09T05:10:07Z'
  id: 208005086
  locale: vi
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/vi/articles/208005086
---
> **Sơ lược:** Unity Ads, một đối tác tích hợp mạng quảng cáo của AppsFlyer, là một mạng lưới quảng cáo video dành cho iOS và Android. Ngoài phân bổ trên thiết bị di động dựa trên lượt nhấp chuột, Unity Ads còn cung cấp chi phí, doanh thu quảng cáo và phân bổ qua lượt xem mà bạn có thể ghi lại trong AppsFlyer.

Để cấu hình chiến dịch của bạn với Unity Ads, hãy thực hiện theo các bước dưới đây.

## Thiết lập Unity Ads

Quá trình thiết lập được thực hiện từ trang **Tích hợp hoạt động** (Active Integrations),nhưng để tìm đối tác, trước tiên bạn phải truy cập vào <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations">thị trường</Anchor> (marketplace).

> 📘 **Lưu ý**
>
> Trước khi thiết lập tích hợp, hãy nhớ <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations#liên-hệ-với-đối-tác">liên hệ với đối tác</Anchor> và mở tài khoản với họ.

**Để kích hoạt tích hợp:**

1. Truy cập Marketplace: Trên menu trên cùng của bất kỳ trang AppsFlyer nào, hãy nhấp vào **Marketplace**.
2. Tìm kiếm và chọn đối tác.
3. Nhấp vào **Set up integration**. Bạn được chuyển đến trang thiết lập tích hợp.
4. Trong tab **Integration**, bật tùy chọn **Activate partner**.  
   **Lưu ý:** Nút bật/tắt phải luôn ở trạng thái bật (<Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">được kích hoạt</Anchor>) trong thời gian bạn làm việc với đối tác.
5. Hoàn thành cấu hình bằng cách sử dụng các tab có liên quan, như được mô tả bên dưới.

Cửa sổ cấu hình của Unity Ads bao gồm 5 thẻ: Tích hợp (Integration), Đường dẫn phân bổ (Attribution link), Chi phí (Cost), Doanh thu quảng cáo (Ad revenue) và Quyền (Permissions). Nhấp vào các mục bên dưới để đọc về cách thiết lập các thẻ.

Để biết mô tả chi tiết về Tiêu đề Cửa sổ Cấu hình Đối tác, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">đây</Anchor>.

> 👍 **Lời khuyên**
>
> * Bước <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#d">General Settings</Anchor> trong thẻ Integration là **bắt buộc** với tất cả các đối tác.
> * Tất cả các bước còn lại chỉ mang tính mô tả hoặc **không bắt buộc**.

<div id="integration-tab" />

<Accordion title="Thẻ Integration">

### Kích hoạt đối tác

Trong lần truy cập đầu tiên, bạn sẽ cần bật nút chuyển đổi **Kích hoạt đối tác** (Activate partner) để thiết lập tích hợp. Nút chuyển đổi phải giữ bật chừng nào bạn còn làm việc với đối tác.  
Để biết thêm chi tiết về kích hoạt đối tác, vui lòng nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">đây</Anchor>.

### Cài đặt chung

**Gửi ID thiết bị (ID quảng cáo) đến Unity**

Ở đầu thẻ Tích hợp (Integration), có một lưu ý cho biết rằng Unity Ads yêu cầu gửi cho họ ID thiết bị cho mỗi lượt cài đặt—việc này được thực hiện tự động, bạn không cần phải làm gì cả.

[![Unity_msc_new_2.png](https://files.readme.io/4291f0b69f8231f6644872f2dfaec84e7c93047e81f653e76ff7266387fa10a9-360002583918.png)](https://files.readme.io/4291f0b69f8231f6644872f2dfaec84e7c93047e81f653e76ff7266387fa10a9-360002583918.png)

**ID trò chơi của Unity Ads**

Unity Ads yêu cầu kết nối với AppsFlyer qua một ID trò chơi duy nhất. Nếu bạn không biết ID của mình, bạn có thể nhận ID trực tiếp từ Unity Ads hoặc bạn có thể tìm thấy ID sau khi tải lên trò chơi, dưới phần **Ứng dụng** (Apps) > **Chiến dịch** (Campaigns), như trong hình chụp dưới đây.

[![](https://files.readme.io/c3315765f33e957b82c39b638bb8113e207bfe80f242bf2e6dde3dce30287a6f-8109147574673.png)](https://files.readme.io/c3315765f33e957b82c39b638bb8113e207bfe80f242bf2e6dde3dce30287a6f-8109147574673.png)

Nền tảng Unity Ads ánh xạ một ứng dụng tới một ID trò chơi của Unity Ads, cho mỗi cấp độ tài khoản (các nhà quảng cáo và đại lý sẽ có các ID trò chơi khác nhau cho cùng một ứng dụng). Nhiều tài khoản trên Nền tảng Unity Ads không thể chạy cùng một ứng dụng với các ID trò chơi khác nhau.

**Kích hoạt phân bổ lượt xem qua**

Bật tùy chọn này để phân bổ lượt cài đặt qua lượt xem từ Unity Ads. Thanh trượt xem lại lượt xem có sẵn trên thẻ đường dẫn phân bổ (mô tả dưới đây).

![Unity_ads_msc_new_3.png](https://files.readme.io/fab459ace7e8f1354d3bbfbca8ddefcd11376b7426a8e361abfab1b42b623880-360001875405.png)

### Các bài đăng lại mặc định

![Screen_Shot_2022-07-28_at_13.07.25.png](https://files.readme.io/a571ddc49e490373b34144e34626a18c6c18908cec3345cd7ac70c49aa855c05-7975491293329.png)

Gửi postback tự động đến Unity Ads sau lượt cài đặt và tái tương tác của người dùng. Sử dụng phần này để xác định nguồn của người dùng cho phép gửi các postback này:

* **Chỉ đối tác này** (This partner only): chỉ dành cho các sự kiện đến từ người dùng được phân bổ đến Unity Ads.
* **Tất cả các nguồn truyền thông, bao gồm cả các nguồn tự nhiên** (All media sources including organic): để toàn bộ cơ sở người dùng của bạn được báo cáo cho Unity Ads.

> 📘 **Lưu ý**
>
> Là một mạng cho tất cả các lượt cài đặt, Unity Ads ưu tiên nhận postback cho tất cả lượt cài đặt mới ứng dụng của bạn từ bất kỳ nguồn nào và họ khuyến khích chọn **Tất cả các nguồn truyền thông, bao gồm cả các nguồn tự nhiên** (All media sources including organic) để gửi mọi postback lượt cài đặt đến Unity Ads.

### Thiết lập Sự kiện trong Ứng dụng

Ánh xạ các sự kiện AppsFlyer với đối tác qua các đăng lại. Nếu bật tính năng gửi đăng lại, điều này bao gồm các sự kiện trong ứng dụng bị từ chối (các sự kiện bị Protect360 chặn hoặc các sự kiện bị phát hiện là không tuân thủ theo quy tắc xác thực mục tiêu).

[![](https://files.readme.io/e0d0af3c57c8452b646dfede7b4899215825ef8455d4e41293088f98ecc026eb-7975565240337.png)](https://files.readme.io/e0d0af3c57c8452b646dfede7b4899215825ef8455d4e41293088f98ecc026eb-7975565240337.png)

#### Để cấu hình postback sự kiện trong ứng dụng

1. Nhập **game\_id**. Đảm bảo game\_id chính xác và tương tự như giá trị được sử dụng cho phân bổ lượt cài đặt.
2. Bật tùy chọn **In-app event postbacks**.
3. Thiết lập **Khung thời gian postback sự kiện trong ứng dụng**, nếu cần (đọc thêm về<Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#khung-thời-gian-đăng-lại-sự-kiện-trong-ứng-dụng"> cấu hình khung thời gian postback sự kiện trong ứng dụng</Anchor>).
4. Nhấp vào **Thêm sự kiện** (Add event) để thêm một SDK hoặc sự kiện từ máy chủ đến máy chủ vào danh sách.
5. Điền những tham số dưới đây:

| Tên thông số | Mô tả |
| --- | --- |
| **Sự kiện AppsFlyer** | Tên của sự kiện mà AppsFlyer nhận được từ SDK sẽ được tích hợp vào ứng dụng của bạn hoặc từ các sự kiện máy chủ đến máy chủ.<br />**Mẹo**: Đừng xem sự kiện đang tìm kiếm?<ul><li>Hãy đảm bảo kích hoạt sự kiện trên thiết bị có cài đặt không tự nhiên và kiểm tra lại.</li><li>Nhập vào **Sự kiện AppsFlyer** (AppsFlyer event), sau đó nhấp vào **Tạo tùy chỉnh** (Create custom). Đọc thêm về <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#sự-kiện-tùy-chỉnh">ánh xạ sự kiện tùy chỉnh.</Anchor></li></ul> |
| **mapped to partner event** | Tên hoặc ID duy nhất của từng sự kiện được xác định ở phía đối tác. Các cấu hình ánh xạ có thể có là:<ul><li>**Trường văn bản (Text field):** Nhận ID sự kiện tương ứng từ đối tác.</li><li>**Hộp thả xuống (Drop-down box):** Chọn sự kiện AppsFlyer được xác định trước phù hợp nhất.</li><li>**Nguyên trạng (As is)**: Gửi các sự kiện như vốn có mà không ánh xạ tên.</li></ul> |
| **for users from** | Chọn tùy chọn gửi cho sự kiện:<ul><li>**This partner only**: chỉ gửi đăng lại khi sự kiện này được phân bổ cho đối tác này.</li><li>**Tất cả các nguồn truyền thông bao gồm cả các nguồn tự nhiên (All media sources, including organic)**: gửi postback cho các sự kiện được phân bổ cho bất cứ đối tác cũng như các sự kiện tự nhiên. Theo Unity Ads, nên sử dụng tùy chọn này.</li></ul> |
| **bao gồm** | <ul><li>**Không có dữ liệu (mặc định) (No data (default))**: chỉ gửi sự kiện mà không gửi giá trị sự kiện.</li><li>**Giá trị và doanh thu (Values and revenue)**: gửi tất cả các thông số sự kiện, **bao gồm** giá trị doanh thu (nếu có trong sự kiện). Theo Unity Ads, nên sử dụng tùy chọn này.</li><li>**Giá trị không có doanh thu (Values without revenue)**: gửi tất cả các thông số, **ngoại trừ** giá trị doanh thu.</li></ul> |

> 🚧 **Quan trọng!**
>
> Chọn sự kiện SDK/máy chủ đến máy chủ chính xác và mã định danh sự kiện đối tác tương ứng. Không được sao chép các sự kiện (không được chuyển cùng các sự kiện theo các tên sự kiện SDK/máy chủ đến máy chủ khác nhau).

> 📘 **Lưu ý**
>
> Bạn có thể gửi <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">đăng lại doanh thu quảng cáo</Anchor> cho Unity Ads để họ có thể tối ưu hóa các chiến dịch bằng cách sử dụng dữ liệu doanh thu quảng cáo:
>
> * **Tên sự kiện:** af\_ad\_revenue
> * **Đã được ánh xạ tới:** ad\_revenue

<div id="attribution-link-tab" />

<Accordion title="Thẻ Attribution link">

Tạo và lưu đường dẫn phân bổ và gửi chúng đến đối tác để phân bổ các chiến dịch cụ thể, bộ quảng cáo, hoặc quảng cáo đơn - cho cả UA và các chiến dịch nhắm mục tiêu lại. Bạn có thể dùng đường dẫn một nền tảng hoặc <Anchor target="_blank" href="/marketers/vi/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters">Thông tin thêm về cấu trúc đường dẫn phân bổ và thông số</Anchor>.  

**Để tạo một đường dẫn phân bổ,** hãy làm theo <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#attribution-link-tab">các hướng dẫn này</Anchor>.

**Lưu ý:**

* Khi đối tượng mục tiêu của ứng dụng Android bao gồm trẻ em, Unity sẽ gửi các ID quảng cáo giảm về không.
* Đọc thêm về cách Unity Ads xác định lượt nhấp chuột và lượt xem.

</Accordion>

<div id="cost-tab" />

<Accordion title="Thẻ Cost">

Không hỗ trợ chi phí theo lượt nhấp chuột. AppsFlyer nhận chi tiết chi phí bằng API. Xem <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">bảng tích hợp chi phí mạng quảng cáo</Anchor> để biết chi tiết đầy đủ về thứ nguyên, chỉ số và tính năng được hỗ trợ. 

**Lưu ý**:

* Dữ liệu chi phí yêu cầu đăng ký ROI360.
* Bạn chỉ có thể nhận được dữ liệu chi phí từ Unity Ads cho lượt tải xuống từ Google Play hoặc Apple App Store. Đối với Android, không hỗ trợ dữ liệu chi phí cho cửa hàng ứng dụng Android của bên thứ ba.
* Không hỗ trợ chi phí đại lý bằng chi phí theo lượt nhấp hoặc API. Nhà quảng cáo có thể gửi dữ liệu chi phí đại lý thông qua <Anchor target="_blank" href="/marketers/vi/docs/import-cost-data">Ad Spend Ingestion</Anchor>.

**Cách kích hoạt API chi phí**:

* Làm theo <Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">các hướng dẫn tích hợp này</Anchor>. **Lưu ý**: Đối với tích hợp chi phí Unity, mọi ứng dụng có cùng mã khóa API phải chứa cùng ID Tổ chức. Nếu không, dữ liệu chi phí kéo sẽ bị ảnh hưởng.

<Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Xem trạng thái API chi phí của bạn</Anchor> và lần cuối cùng AppsFlyer quản lý kéo dữ liệu chi phí phù hợp vào trang tổng quan trạng thái tích hợp chi phí (và doanh thu quảng cáo) hoặc trang tổng quan mạng quảng cáo cá nhân.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Thẻ Ad revenue">

Phần này chỉ có liên quan nếu bạn đang đóng vai trò là nhà xuất bản, hiển thị quảng cáo của đối tác cho người dùng của bạn. Như vậy, bạn chắc chắn muốn đo lường mức độ tham gia của người dùng của bạn thu được từ các nguồn khác nhau, để tìm ra các nguồn sinh lợi nhất cho bạn.

**Để bật API doanh thu quảng cáo**:

* Tuân thủ <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">các hướng dẫn tích hợp này</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Thẻ Permission">

Trong thẻ này, bạn có thể chọn các quyền sẽ cấp cho Unity Ads để thực hiện một số hành động. Lưu ý rằng ngay cả khi tính năng phân bổ bị vô hiệu hóa đối với Unity Ads, thẻ quyền (permissions) vẫn hoạt động và bạn có thể cấp quyền cho Unity Ads.  
Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#permissions-tab">các quyền bạn có thể cấp</Anchor>.

</Accordion>

</Accordion>

<div data-zendesk-anchors="setting-up-unity-ads=thi%E1%BA%BFt-l%E1%BA%ADp-unity-ads h_01HAPVZ510GTJRY1NXE0T3SMR6=thi%E1%BA%BFt-l%E1%BA%ADp-unity-ads h_01HAPVZ5105TY4Q4V32GPYAEER=l%C6%B0u-%C3%BD h_01HAPVZ5109NKD8GHD36EDN810=l%E1%BB%9Di-khuy%C3%AAn h_01HAPVZ510KPB0HQS9X6R4BCWT=integration-tab activate-partners=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c h_01HAPVZ510BGQ4KZ3S6ZP0QRE8=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c general-settings=c%C3%A0i-%C4%91%E1%BA%B7t-chung h_01HAPVZ510EZ3HKJQVPMKHV5FH=c%C3%A0i-%C4%91%E1%BA%B7t-chung default-postbacks=c%C3%A1c-b%C3%A0i-%C4%91%C4%83ng-l%E1%BA%A1i-m%E1%BA%B7c-%C4%91%E1%BB%8Bnh h_01HAPVZ511MRQXKPC78HR61X9P=c%C3%A1c-b%C3%A0i-%C4%91%C4%83ng-l%E1%BA%A1i-m%E1%BA%B7c-%C4%91%E1%BB%8Bnh h_01HAPVZ511CCXS93Y714STGQ67=l%C6%B0u-%C3%BD-1 inapp-events-settings=thi%E1%BA%BFt-l%E1%BA%ADp-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HAPVZ511CJ6JP49HYG9T6RPF=thi%E1%BA%BFt-l%E1%BA%ADp-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng to-configure-inapp-event-postbacks=%C4%91%E1%BB%83-c%E1%BA%A5u-h%C3%ACnh-postback-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HAPVZ511RMEVNASSTJNXKCJG=%C4%91%E1%BB%83-c%E1%BA%A5u-h%C3%ACnh-postback-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HAPVZ511AV30DEKMZ0YB5ZBD=quan-tr%E1%BB%8Dng h_01HAPVZ511PC45Q5FEXQMZ4MFC=l%C6%B0u-%C3%BD-2 h_01HAPVZ5110QVYGGCGQDHRJEQM=attribution-link-tab h_01HAPVZ511DSKFAKKNWTKV9522=cost-tab h_01HAPVZ5111WPRRMPF6GZJTRJS=ad-revenue-tab h_01HAPVZ511RBNY3HHSHJHJDPWG=permissions-tab" />
