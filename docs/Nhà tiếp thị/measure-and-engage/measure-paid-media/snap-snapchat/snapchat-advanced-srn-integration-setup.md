---
title: Snapchat—Thiết lập tích hợp SRN nâng cao
metadata:
  keywords:
    - configuration
    - snapchat measurement partner
    - snapchat
    - measurement
    - snapchat measurement analytics
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-06-13T12:28:59Z'
  edited_at: '2023-11-09T05:06:43Z'
  id: 211011983
  locale: vi
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/vi/articles/211011983
---
> **Sơ lược:** Snapchat đã trở thành SRN Nâng cao từ giữa tháng 9 năm 2023. Tìm hiểu cách thiết lập tích hợp giữa AppsFlyer và Snapchat để cho phép đo lường phân bổ.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/snapchat.png?v=1" width="52px" />

## Tổng quan

Tích hợp SRN Nâng cao có nghĩa là tất cả lưu lượng truy cập <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-knowledge-base-glossary?query=glossar#dual-consent">được chấp thuận kép</Anchor> sẽ được phân bổ và báo cáo là lưu lượng truy cập SRN thông thường. Đối với lưu lượng truy cập không được chấp thuận, AppsFlyer có thể phân bổ và đo lường lưu lượng phân bổ dựa trên số lượt nhấp và lượt hiển thị từ Snapchat, tuân thủ các quy định hạn chế về quyền riêng tư. Tính năng tích hợp hỗ trợ phân bổ lượt nhấp và lượt hiển thị, chi phí, doanh thu quảng cáo và đối tượng.

## Thiết lập tích hợp Snapchat

Quy trình thiết lập được thực hiện từ trang **Active Integrations**, nhưng để tìm đối tác, trước tiên bạn phải truy cập vào <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations">marketplace</Anchor>.

**Cách cấu hình chiến dịch của bạn trên Snapchat:**

1. Trong AppsFlyer, dưới phần **Configuration (Cấu hình)** đi đến **Partner Marketplace (Thị trường Đối tác)**.
2. Tìm **Snapchat** và chọn.
3. Xem lại các Điều khoản và điều kiện của Snapchat dành cho Theo dõi chuyển đổi ứng dụng trên di động (MAST), nhấp vào **Accept** để chấp nhận các điều khoản.
4. Hoàn tất thiết lập bằng cách sử dụng các thẻ có liên quan.
5. Nhấp vào **Lưu Tích hợp**.

Để xem mô tả chi tiết về tiêu đề khung thời gian cấu hình đối tác, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">đây</Anchor>.

> 👍 **Lời khuyên**
>
> * Bước <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#d">General Settings</Anchor> trong thẻ Integration là **bắt buộc** với tất cả các đối tác.
> * Tất cả các bước còn lại chỉ mang tính mô tả hoặc **không bắt buộc**.

<div id="integration-tab" />

<Accordion title="Thẻ Integration">

Thẻ Integration được chia thành các phần khác nhau như được mô tả dưới đây.

#### Kích hoạt đối tác

Trong **first visit** tại đây, bạn phải bật **Activate Partner** để bật thiết lập.  
Để biết thêm chi tiết về kích hoạt đối tác, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">đây</Anchor>.

#### Cài đặt chung

**Bật phân bổ**

Bật **Activate Partner** để cho phép phân bổ cho Snapchat.

![mceclip0.png](https://files.readme.io/cf4e73fec951e4e9d2c1919ca20adff88fc0d49d7fea9b033ab9c39194ce2702-360003259638.png)

**ID ứng dụng Snap**

1. Trong Trình quản lý doanh nghiệp trên Snap, đi tới Apps và sao chép ID ứng dụng Snap (đọc hướng dẫn của Snapchat về <Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/a/snap-app-id">cách tạo ID ứng dụng Snap</Anchor>).
2. Dán ID vào trường Snap App ID trong AppsFlyer.

![snapchat-app-id.png](https://files.readme.io/2e5f53240893e2a80ba36065f67f4504f69e1167d96ef35bd7a4ab874d5a7bb9-360008280878.png)

**Trong trường hợp ứng dụng được quảng cáo bởi một đại lý**,

* Chỉ nhà quảng cáo mới có thể thêm ID ứng dụng Snap.
* Nếu đại lý thuộc cùng một tổ chức với bạn trên nền tảng quảng cáo Snapchat, hãy chỉ sử dụng một ID ứng dụng Snap.
* Nếu đại lý trực thuộc một tổ chức khác trên nền tảng quảng cáo Snapchat, hãy yêu cầu họ cung cấp ID ứng dụng Snap cho ứng dụng này và nhập vào trường này. Có thể nhập nhiều ID. Nhấn Enter sau mỗi ID.

#### Phân bổ lượt nhấp qua

Thanh trượt này cho phép bạn đặt **thời gian tối đa từ khi nhấp chuột cho tới khi cài đặt**. Chỉ các lượt cài đặt (khởi chạy lần đầu) diễn ra trong khung thời gian xem lại mới có thể được phân bổ cho Snapchat.

Bạn có thể tùy chỉnh giá trị này thành 1-23 giờ hoặc 1-30 ngày. Bạn nên đặt khung thời gian xem lại Lượt nhấp qua thành 28 ngày để phù hợp với Snapchat.

Để biết thêm chi tiết về <Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows">khung thời gian xem lại lượt nhấp tại đây</Anchor>.

![snap-click-window.png](https://files.readme.io/07eb4b7d4a5ec37791cdef31e0fbb77e22f0b65cd189a426bf293d166827b44a-360011563618.png)

#### Khung thời gian xem lại phân bổ lượt xem hết

Thanh trượt này cho phép bạn đặt **thời gian tối đa từ hiển thị tới cài đặt**. Sau một lần hiển thị quảng cáo, chỉ các lượt cài đặt (lần khởi chạy đầu tiên) diễn ra trong khung thời gian xem lại này mới được phân bổ cho Snapchat, miễn là không có nhấp vào quảng cáo liên quan khác.

Bạn có thể tùy chỉnh giá trị này thành 1-23 giờ hoặc 1-7 ngày. Bạn nên đặt khung thời gian xem lại lượt xem hết thành 1 ngày, để phù hợp với Snapchat.

Thông tin chi tiết về <Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows">phân bổ lượt xem hết tại đây</Anchor>.

![snap-viewthrough-window.png](https://files.readme.io/a493869ca1bb6f6b9ff63438e3b5aa4ade45d047e05fe0d8ebdd99c3ef6affcc-360011482617.png)

#### Phân bổ thu hút lại

Kích hoạt Phân bổ thu hút lại để bắt đầu phân bổ thu hút lại cho Snapchat.  
Nếu bạn là đại lý, hãy yêu cầu nhà quảng cáo làm điều đó cho bạn từ phía họ.

#### Thời gian xem lại lượt nhấp tương tác lại

Đặt thời lượng cho **Re-engagement click-through lookback window** (Thời gian xem lại lượt nhấp tương tác lại) (thời gian tối đa sau khi một quảng cáo được nhấp vào, trong thời gian đó người dùng được nhắm lại mục tiêu có thể được phân bổ cho quảng cáo). Bạn có thể đặt giá trị theo giờ (tối đa 23) hoặc ngày (1-30):

![snap-reengagement-activate.png](https://files.readme.io/318deeab0432870035a163a7b8a5b8c03be7d683bfc369104c8577674fde0036-36433422309905.png)

#### Thời gian xem lại lượt xem hết tương tác lại

Để bắt đầu phân bổ các lượt hiển thị quảng cáo nhắm lại mục tiêu, hãy kích hoạt **Re-engagement view-through attribution**.  
Đặt thời lượng cho Khung thời gian xem lại lượt xem hết thu hút lại (thời gian tối đa sau khi một quảng cáo được xem, trong thời gian đó người dùng được nhắm lại mục tiêu có thể được phân bổ cho quảng cáo). Bạn có thể đặt giá trị theo giờ (tối đa 23) hoặc ngày (1-7):

![snap-reengagement-view-through.png](https://files.readme.io/4faf93b6d8a8e45043eb9440d8f56a70eba2da51f3a572ea6cd698e072f033c6-36433415112849.png)

#### Khung thời gian thu hút lại

Đặt thời lượng cho **Re-engagement window** (khoảng thời gian khi sự kiện trong ứng dụng của người dùng được phân bổ cho nguồn truyền thông nhắm lại mục tiêu). Bạn có thể đặt giá trị theo ngày (1-90), giờ (tối đa 23) hoặc thậm chí là trọn đời:

![snap-reengagement-window.png](https://files.readme.io/99aab0e0e808514d1450fd297a1e7d2217be4e21d8ca85bd5a922e797f39755e-360008512418.png)

#### Cài đặt đăng lại sự kiện trong ứng dụng

Ánh xạ các sự kiện AppsFlyer với đối tác qua các đăng lại. Nếu bật tính năng gửi đăng lại, điều này bao gồm các sự kiện trong ứng dụng bị từ chối (các sự kiện bị Protect360 chặn hoặc các sự kiện bị phát hiện là không tuân thủ theo quy tắc xác thực mục tiêu).

[![In-app_event_postbacks_en-us.png](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)

**Cách cấu hình đăng lại sự kiện trong ứng dụng:**

1. Đặt **Partner ID** (nếu cần).
2. Bật **In-app event postback.**
3. Thiết lập **In-app event postback window**, nếu cần (đọc thêm về <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#khung-thời-gian-đăng-lại-sự-kiện-trong-ứng-dụng">cấu hình khung thời gian đăng lại sự kiện trong ứng dụng</Anchor>).
4. Nếu có, hãy chọn gửi sự kiện theo cách tự động hoặc thủ công. Tìm hiểu thêm về cách <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped">gửi tất cả các sự kiện nguyên trạng</Anchor>.
5. Nhấp vào **Add event** để thêm một SDK hoặc sự kiện từ máy chủ đến máy chủ vào danh sách.
6. Hoàn thành các thông số yêu cầu.
7. [Tùy chọn] Nhấp vào <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/6524810d15f08b4b85deab9c2cbfb8fd7880126b3c3180e3ecf4ead5f1f0a9ae-17798909160465.png" width="30px" /> để đặt điều kiện gửi các sự kiện trong ứng dụng nhất định cho đối tác.  
   Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#đăng-lại-sự-kiện-trong-ứng-dụng-có-điều-kiện">đăng lại các sự kiện trong ứng dụng có điều kiện</Anchor>.

| Tên thông số | Mô tả |
| --- | --- |
| **AppsFlyer event** | Tên của sự kiện mà AppsFlyer nhận được từ SDK sẽ được tích hợp vào ứng dụng của bạn hoặc từ các sự kiện máy chủ đến máy chủ.<br />**Lời khuyên**: Bạn không thấy sự kiện đang tìm kiếm?<ul><li>Hãy đảm bảo kích hoạt sự kiện trên thiết bị có cài đặt không tự nhiên và kiểm tra lại.</li><li>Nhập vào **AppsFlyer event**, sau đó nhấp vào **Create custom**. Đọc thêm về <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#sự-kiện-tùy-chỉnh">ánh xạ sự kiện tùy chỉnh.</Anchor></li></ul> |
| **mapped to partner event** | Tên hoặc ID duy nhất của từng sự kiện được xác định ở phía đối tác. Các cấu hình ánh xạ có thể có là:<ul><li>**Text field:** Nhận ID sự kiện tương ứng từ đối tác.</li><li>**Drop-down box:** Chọn sự kiện AppsFlyer được xác định trước phù hợp nhất.</li><li>**As is**: Gửi các sự kiện như vốn có mà không ánh xạ tên.</li></ul> |
| **for users from** | Chọn tùy chọn gửi cho sự kiện:<ul><li>**This partner only**: chỉ gửi đăng lại khi sự kiện này được phân bổ cho đối tác này.</li><li>**All media sources including organic**: gửi đăng lại cho các sự kiện được phân bổ cho bất kỳ đối tác và sự kiện tự nhiên nào.</li></ul> |
| **including** | <ul><li>**No data (default)**: chỉ gửi sự kiện mà không gửi giá trị sự kiện.</li><li>**Values and revenue**: gửi tất cả các thông số sự kiện, **bao gồm** cả giá trị doanh thu (nếu có trong sự kiện).</li><li>**Values without revenue**: gửi tất cả các thông số, **ngoại trừ** giá trị doanh thu.</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Thẻ Attribution link">

Đường dẫn phân bổ không có sẵn cho Snapchat.

> 📘 **Lưu ý**
>
> Đối với tất cả các SRN, chẳng hạn như Facebook, Apple Search Ads, Adwords, Snapchat, v.v., thẻ này không hoạt động vì chúng không sử dụng các đường dẫn phân bổ bên ngoài.

</Accordion>

<div id="cost-tab" />

<Accordion title="Thẻ Cost">

Tích hợp chi phí cung cấp dữ liệu hợp nhất sau:

* Dữ liệu chi phí cho các chiến dịch, bộ quảng cáo, quảng cáo và cấp kênh của bạn. Xem <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">bảng tích hợp chi phí mạng quảng cáo</Anchor> để biết đầy đủ chi tiết về các phương diện, số liệu và tính năng được hỗ trợ.  
  **Lưu ý**: Dữ liệu chi phí yêu cầu phải có đăng ký <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>.
* Dữ liệu về lượt nhấp và lượt hiển thị.

**Cách kích hoạt API chi phí**:

* Tuân thủ <Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">các hướng dẫn tích hợp này</Anchor>.

<div id="cost-data-sync-status" />

<Accordion title="Trạng thái đồng bộ dữ liệu chi phí">

<Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Xem trạng thái API chi phí của bạn</Anchor> và lần cuối cùng AppsFlyer quản lý kéo dữ liệu chi phí phù hợp vào trang tổng quan trạng thái tích hợp chi phí (và doanh thu quảng cáo) hoặc trang tổng quan mạng quảng cáo cá nhân.

</Accordion>

<div id="stop-snapchat-cost-sync" />

<Accordion title="Dừng đồng bộ hóa chi phí Snapchat">

**Cách dừng nhận chi phí Snapchat và xóa tài khoản Snapchat được kết nối:**

* <Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">Trong cột actions, di chuột qua một tài khoản, nhấp vào **Delete connection**</Anchor>   
  Sau khi đã bị xóa, AppsFlyer sẽ ngừng nhận dữ liệu về chi phí. Xóa kết nối không ảnh hưởng đến dữ liệu lịch sử.

</Accordion>

> 📘 **Lưu ý**
>
> * Đảm bảo bạn thiết lập chiến dịch trong Snapchat dành cho ứng dụng iOS hoặc Android; không phải cả hai. Nếu chiến dịch dành cho cả hai ứng dụng, AppsFlyer sẽ không thể phân chia chi phí cho mỗi ứng dụng và chi phí sẽ không hiển thị trong AppsFlyer.
> * Để tránh xuất hiện sai lệch trong dữ liệu chi phí, hãy đặt cùng một múi giờ trong cả <Anchor target="_blank" href="/marketers/vi/docs/changing-app-time-zone-settings#changing-the-time-zone">app settings</Anchor> và tài khoản quảng cáo Snapchat của bạn.
> * Khi bạn thiết lập, chi phí Snap sẽ không làm thay đổi tên của bất kỳ chiến dịch, bộ quảng cáo hoặc quảng cáo đơn lẻ đang vận hành, vì điều đó có thể gây ra sự chênh lệch nghiêm trọng hoặc thiếu dữ liệu chi phí.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Thẻ Ad revenue">

Doanh thu quảng cáo không được hỗ trợ khi tích hợp với đối tác này.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Thẻ Permission">

Trong thẻ này, bạn có thể chọn các quyền sẽ cấp cho Snapchat. Lưu ý rằng ngay cả khi tính năng phân bổ bị vô hiệu hóa đối với Snapchat, thẻ permission này vẫn hoạt động và bạn có thể cấp quyền kiểm soát cho Snapchat.

Bật **Ad Network Permissions** để bắt đầu cấu hình.

Sau khi bạn bật **Ad Network Permissions**:

* Ứng dụng xuất hiện trên bảng điều khiển của mạng quảng cáo
* Quyền truy cập chỉ được cấp cho mạng quảng cáo này
* Quản trị viên mạng quảng cáo có thể nhìn thấy <Anchor target="_blank" href="/marketers/vi/docs/manage-data-access-permissions">dữ liệu cơ bản về ứng dụng</Anchor>

#### Cấp quyền cho thành viên trong mạng quảng cáo

Theo mặc định, quản trị viên Snapchat có quyền truy cập vào ứng dụng của bạn; tuy nhiên, bạn có thể cấp cho nhân viên Snapchat cụ thể quyền quản lý ứng dụng của bạn. Để có thể làm như vậy, những nhân viên này phải được quản trị viên Snapchat thêm vào AppsFlyer làm **thành viên nhóm**.

Sau đó, lấy địa chỉ email của các thành viên nhóm Snapchat liên quan.

Cách thêm các thành viên nhóm có quyền quản lý ứng dụng của bạn:

1. Nhấp vào **Add team member**.
2. Nhập email của thành viên nhóm trong mạng quảng cáo.
3. Nhấp vào **Add**.
4. Lặp lại quy trình để thêm nhiều thành viên nhóm nếu cần.

Khi bạn bật quyền cho mạng quảng cáo, hãy chọn quyền bạn muốn cấp.

Sử dụng các tính năng chuyển đổi này để cấp quyền cho mạng quảng cáo xử lý cấu hình riêng cho ứng dụng của bạn:

#### Quyền truy cập mạng quảng cáo

* **Allow to configure integration** - cho phép đối tác thiết lập thẻ cấu hình (ngoại trừ đăng lại sự kiện trong ứng dụng)
* **Allow to configure in-app event postbacks** - cho phép đối tác thiết lập ánh xạ đăng lại sự kiện trong ứng dụng lên chính bản thân đối tác trên thẻ integration
* **Allow access to your retention report** - chỉ với dữ liệu lưu trữ của chính đối tác
* **Allow access to your aggregate loyal user data** - chỉ với dữ liệu người dùng trung thành của chính đối tác
* **Allow access to your aggregate in-app events data** - chỉ với dữ liệu sự kiện trong ứng dụng của đối tác
* **Allow access to your aggregate revenue data** - chỉ với dữ liệu doanh thu được phân bổ cho đối tác
* **Allow spend ingestion** - ở cấp ứng dụng
* **Allow access to your Protect360 dashboard** - chỉ với dữ liệu Protect360 của chính đối tác và miễn là tính năng được kích hoạt cho nhà quảng cáo

Tìm hiểu thêm về việc cấp <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#permissions-tab">quyền truy cập mạng quảng cáo</Anchor>.

</Accordion>

## Liên kết sâu với Snapchat

Liên kết sâu với Snapchat dựa trên việc sử dụng liên kết sâu gốc trong nền tảng của Snapchat, đồng thời bổ sung các thông số AppsFlyer vào liên kết đó.

Cách thực hiện liên kết sâu với Snapchat:

1. Xác minh rằng **liên kết sâu** cho [tính năng nhắm mục tiêu lại đã được bật cho Snapchat.](/docs/snapchat-advanced-srn-integration-setup#làm-cách-nào-để-thiết-lập-liên-kết-sâu-trên-nền-tảng-snap)
2. Xác minh đảm bảo rằng <Anchor target="_blank" href="/marketers/vi/docs/app-settings#reengagement-attribution">chức năng phân bổ thu hút lại được bật trong AppsFlyer.</Anchor>
3. Lấy URI lược đồ liên kết sâu của ứng dụng và thêm **ít nhất** các thông số sau:

* **PID** - Nguồn truyền thông; trong trường hợp này luôn là **snapchat\_int**. Điều này cho phép tất cả dữ liệu xuất hiện trong bảng điều khiển AppsFlyer dưới nguồn truyền thông **Snapchat\_int**.
* **C -** tên chiến dịch liên quan
* **is\_retargeting=true -** trường này xác định chiến dịch là chiến dịch nhắm mục tiêu lại. Tương tác của người dùng hiện có với chiến dịch nhắm mục tiêu lại được đánh dấu là tương tác lại do sự tồn tại của trường này trong URI. Điều này đảm bảo dữ liệu của người dùng xuất hiện trong bảng điều khiển nhắm mục tiêu lại.

> 📄 **Ví dụ về URI**
>
> client://home?pid=snapchat\_int&c=TEST&is\_retargeting=true

### Làm cách nào để thiết lập liên kết sâu trên nền tảng Snap?

1. Đi tới loại cơ hội **Drive traffic to app**.
2. Thêm URI liên kết sâu:  
     
    [![](https://files.readme.io/428258bbc5eb2fc7332ea07356e098eb66ac2cfdd0955117a14666eb76a20f79-360001717778.png)](https://files.readme.io/428258bbc5eb2fc7332ea07356e098eb66ac2cfdd0955117a14666eb76a20f79-360001717778.png)

### Liên kết sâu bị trì hoãn với Snapchat

Bạn có thể truy cập trực tiếp vào dữ liệu chuyển đổi của người dùng Snapchat trong thời gian thực ở cấp độ SDK bằng cách sử dụng <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">liên kết sâu bị trì hoãn</Anchor>.

<Anchor target="_blank" href="/marketers/vi/docs/conversion-data-payloads-and-scenarios#snapchat-conversion-data">Dữ liệu chuyển đổi Snapchat</Anchor> bao gồm thông số **af\_dp**, cho phép bạn liên kết sâu và cung cấp nội dung tùy chỉnh, dựa trên mức độ tương tác của người dùng với quảng cáo của bạn trong Snapchat.

Ngoài ra, bạn có thể sử dụng các thông số dữ liệu chuyển đổi khác như **af\_adset** hoặc **af\_channel**.

## Thiết lập Snapchat cho các đại lý

Thiết lập phân bổ Snapchat của đại lý tương tự như thiết lập của nhà quảng cáo.

Các đại lý không thể thiết lập cài đặt Advanced Privacy—mục này được giới hạn chỉ cho nhà quảng cáo.

Bạn cần thực hai bước để hoàn tất thiết lập:

1. Nhà quảng cáo phải bật **Activate Partner** cho Snapchat để cho phép thiết lập các thông số của thẻ Integration.  
   Để biết thêm chi tiết về kích hoạt đối tác, vui lòng nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">đây</Anchor>.
2. Trên bảng điều khiển của đại lý, trên trang cấu hình Snapchat, bật vùng văn bản ID tài khoản Snapchat như bên dưới. Các đại lý có thể nhập tối đa 50 ID tài khoản Snapchat khác nhau vào vùng văn bản. Tất cả dữ liệu phân bổ sau đó đến từ các tài khoản này chỉ hiển thị trong bảng điều khiển của đại lý.[![snapchat-agency-integration.png](https://files.readme.io/261a0246bb7da0899e653a776eb25e17ce3ae8bff1efef33acac0ef0bf99abcf-21074932431505.png)](https://files.readme.io/261a0246bb7da0899e653a776eb25e17ce3ae8bff1efef33acac0ef0bf99abcf-21074932431505.png)

> ❗️ **Cảnh báo**
>
> Các ID tài khoản Snapchat không được chia sẻ giữa nhà quảng cáo hoặc đại lý. Nếu đã chia sẻ, TẤT CẢ lượt cài đặt của nhà quảng cáo sẽ tự động được phân bổ trên bảng điều khiển của đại lý.

## Hạn chế dữ liệu thô

* Bắt đầu từ ngày 1 tháng 3 năm 2023, lượt gỡ cài đặt Snapchat không được đưa vào báo cáo dữ liệu thô
* Bắt đầu từ ngày 12 tháng 9 năm 2023, Snapchat sẽ cung cấp cho các nhà quảng cáo dữ liệu phân bổ xem hết giới hạn ở cấp thiết bị. Đối với các nguồn cấp người dùng, chẳng hạn như báo cáo dữ liệu thô, thông báo API Push, báo cáo API Pull, trang Dữ liệu xuất và Khóa Dữ liệu, chỉ các trường sau sẽ được điền:

* * Nguồn truyền thông (snapchat\_int)
  * Kênh
  * Loại tương tác được phân bổ (lượt hiển thị)
  * Thời gian tương tác được phân bổ (chỉ được báo cáo dưới dạng ngày - "dd/mm/yyyy")
  * Chiến dịch được báo cáo là "bị hạn chế"

## Lưu trữ dữ liệu Snapchat

Snapchat yêu cầu nhà cung cấp phân bổ xóa dữ liệu ở mức người dùng trong 12 tháng sau khi cài đặt. Điều này có nghĩa là các sự kiện được thực hiện bởi những người dùng này trong 12 tháng sau khi họ cài đặt ứng dụng sẽ được tính là tự nhiên.

Dữ liệu hợp nhất trong quá khứ vẫn giữ nguyên.

> 📄 **Xem thêm**
>
> <Anchor target="_blank" href="/marketers/vi/docs/skan-interoperation-with-snapchat">Khả năng tương tác giữa Snapchat và SKAdNetwork của AppsFlyer</Anchor>

<div data-zendesk-anchors="overview=t%E1%BB%95ng-quan 01H8F1RWVPTHBDGF3830DY7G7M=t%E1%BB%95ng-quan setting-up-snapchat-integration=thi%E1%BA%BFt-l%E1%BA%ADp-t%C3%ADch-h%E1%BB%A3p-snapchat 01H7WQ47ECTZHPKMG5Z5ZPAND5=thi%E1%BA%BFt-l%E1%BA%ADp-t%C3%ADch-h%E1%BB%A3p-snapchat 01H7WQ47ECXP15V425JY4G2HC9=l%E1%BB%9Di-khuy%C3%AAn 01H7WQ47ECD76GFNM7VVV7C9RG=integration-tab activate-partner=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c 01H7WQ47ECZB5GNCQ0XH68N1DK=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c general-settings=c%C3%A0i-%C4%91%E1%BA%B7t-chung 01H7WQ47ECQSQPP63H398NTQ6M=c%C3%A0i-%C4%91%E1%BA%B7t-chung clickthrough-attribution=ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-nh%E1%BA%A5p-qua 01H7WQ47ECP56VNB2MY0WYE420=ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-nh%E1%BA%A5p-qua viewthrough-attribution-lookback-window=khung-th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-xem-h%E1%BA%BFt 01H7WQ47EC7S1SPVV70SR04CPY=khung-th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-xem-h%E1%BA%BFt reengagement-attribution=ph%C3%A2n-b%E1%BB%95-thu-h%C3%BAt-l%E1%BA%A1i 01H7WQ47ECHGMWS35VEM8MD2F2=ph%C3%A2n-b%E1%BB%95-thu-h%C3%BAt-l%E1%BA%A1i reengagement-clickthrough-lookback-window=th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-l%C6%B0%E1%BB%A3t-nh%E1%BA%A5p-t%C6%B0%C6%A1ng-t%C3%A1c-l%E1%BA%A1i 01H7WQ47ECSP3H6202PAR816CX=th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-l%C6%B0%E1%BB%A3t-nh%E1%BA%A5p-t%C6%B0%C6%A1ng-t%C3%A1c-l%E1%BA%A1i reengagement-viewthrough-lookback-window=th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-l%C6%B0%E1%BB%A3t-xem-h%E1%BA%BFt-t%C6%B0%C6%A1ng-t%C3%A1c-l%E1%BA%A1i 01H7WQ47ECEW3QBCA65DVGGB7E=th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-l%C6%B0%E1%BB%A3t-xem-h%E1%BA%BFt-t%C6%B0%C6%A1ng-t%C3%A1c-l%E1%BA%A1i reengagement-window=khung-th%E1%BB%9Di-gian-thu-h%C3%BAt-l%E1%BA%A1i 01H7WQ47ECDVE76A1TA81SJAYZ=khung-th%E1%BB%9Di-gian-thu-h%C3%BAt-l%E1%BA%A1i inapp-event-postback-settings=c%C3%A0i-%C4%91%E1%BA%B7t-%C4%91%C4%83ng-l%E1%BA%A1i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng 01H7WQ47ECYF4XW9F657WRJWFW=c%C3%A0i-%C4%91%E1%BA%B7t-%C4%91%C4%83ng-l%E1%BA%A1i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng 01H7WQ47EDWX9TGAD4X0E41RQ8=attribution-link-tab 01H7WQ47ED5N4REX0SFVY5ZG2K=l%C6%B0u-%C3%BD 01H7WQ47EDCKQ1T4NVFD3C1KV0=cost-tab 01H7WQ47ED1HYEBHFJDHTB6HJH=cost-data-sync-status 01H7WQ47ED3P53B269W93Z341E=stop-snapchat-cost-sync 01H7WQ47EDQ0253RY37PX67REV=l%C6%B0u-%C3%BD-1 01H7WQ47EDC3YB1BKNG2C7AD6J=ad-revenue-tab 01H7WQ47EDXRE05R6M1YVD9DK7=permissions-tab grant-permissions-to-ad-network-team-members=c%E1%BA%A5p-quy%E1%BB%81n-cho-th%C3%A0nh-vi%C3%AAn-trong-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o 01H7WQ47ED0KXZ1ACV2ER2B0GJ=c%E1%BA%A5p-quy%E1%BB%81n-cho-th%C3%A0nh-vi%C3%AAn-trong-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o ad-network-permissions=quy%E1%BB%81n-truy-c%E1%BA%ADp-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o 01H7WQ47ED6YSJ5Q64578A9RF8=quy%E1%BB%81n-truy-c%E1%BA%ADp-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o deep-linking-with-snapchat=li%C3%AAn-k%E1%BA%BFt-s%C3%A2u-v%E1%BB%9Bi-snapchat 01H7WQ47EDC973V7CPE38QAQE7=li%C3%AAn-k%E1%BA%BFt-s%C3%A2u-v%E1%BB%9Bi-snapchat 01H7WQ47EDXS702A9TZ7DJ8MPG=v%C3%AD-d%E1%BB%A5-v%E1%BB%81-uri how-to-set-up-deep-links-on-snap-platform=l%C3%A0m-c%C3%A1ch-n%C3%A0o-%C4%91%E1%BB%83-thi%E1%BA%BFt-l%E1%BA%ADp-li%C3%AAn-k%E1%BA%BFt-s%C3%A2u-tr%C3%AAn-n%E1%BB%81n-t%E1%BA%A3ng-snap 01H7WQ47EDJAX2DW7A2JJ4XVJN=l%C3%A0m-c%C3%A1ch-n%C3%A0o-%C4%91%E1%BB%83-thi%E1%BA%BFt-l%E1%BA%ADp-li%C3%AAn-k%E1%BA%BFt-s%C3%A2u-tr%C3%AAn-n%E1%BB%81n-t%E1%BA%A3ng-snap deferred-deep-linking-with-snapchat=li%C3%AAn-k%E1%BA%BFt-s%C3%A2u-b%E1%BB%8B-tr%C3%AC-ho%C3%A3n-v%E1%BB%9Bi-snapchat 01H7WQ47EDS3MYRN9A9ZPHXG9Z=li%C3%AAn-k%E1%BA%BFt-s%C3%A2u-b%E1%BB%8B-tr%C3%AC-ho%C3%A3n-v%E1%BB%9Bi-snapchat setting-up-snapchat-for-agencies=thi%E1%BA%BFt-l%E1%BA%ADp-snapchat-cho-c%C3%A1c-%C4%91%E1%BA%A1i-l%C3%BD 01H7WQ47EDARK9SSP47V5MGX18=thi%E1%BA%BFt-l%E1%BA%ADp-snapchat-cho-c%C3%A1c-%C4%91%E1%BA%A1i-l%C3%BD 01H7WQ47EDPEDQHX9XRDKYKB1W=c%E1%BA%A3nh-b%C3%A1o raw-data-restrictions=h%E1%BA%A1n-ch%E1%BA%BF-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 h_01HA3XZPWSKVRX7VTRXT1WQ1EZ=h%E1%BA%A1n-ch%E1%BA%BF-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 keeping-snapchat-data=l%C6%B0u-tr%E1%BB%AF-d%E1%BB%AF-li%E1%BB%87u-snapchat 01H7WQ47ED9STKS1CVW5EXYX0Z=l%C6%B0u-tr%E1%BB%AF-d%E1%BB%AF-li%E1%BB%87u-snapchat h_01HE7RP6VPPAY2CCSNTJ0RVSXM=xem-th%C3%AAm" />
