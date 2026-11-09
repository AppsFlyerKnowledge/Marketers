---
title: Thiết lập đối tác tích hợp
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-11-08T08:02:46Z'
  edited_at: '2023-11-17T02:21:47Z'
  id: 4410395957521
  locale: vi
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/vi/articles/4410395957521
---
> **Khái quát:** Bật đo lường phân bổ, gửi đăng lại cho đối tác và bật các tính năng tích hợp khác bằng cách thiết lập kết nối đối tác với AppsFlyer.

<div id="overview" />

## Tổng quan

Đối tác, nguồn truyền thông và nền tảng bên thứ ba tích hợp với AppsFlyer bằng API. Bài viết này hướng dẫn chung về cách kích hoạt và thiết lập tích hợp, bao gồm tạo đường dẫn phân bổ cho các mạng quảng cáo không phải SRN.

* Hướng dẫn này không áp dụng cho SRN. Sử dụng bài viết cụ thể về <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns">SRN</Anchor>.
* Một số mạng quảng cáo có các bài viết riêng.
* Trước khi thiết lập cấu hình, bạn phải liên hệ với đối tác và mở tài khoản với họ.

<div id="partner-types-in-the-ecosystem" />

<Accordion title="Các loại đối tác trong hệ sinh thái">

Hình ảnh sau chứa các loại đối tác khác nhau tạo thành hệ sinh thái phân bổ.

<Image align="center" alt="Ecosystem.jpg" src="https://files.readme.io/9377db3a6a6effd7ff8139994e2e8ed8dea04331588b5df2a31f1acd643afd9f-4411031173265.jpg" />

**Bài viết liên quan**: <Anchor target="_blank" href="https://www.appsflyer.com/performance-index/">Chỉ số Hiệu suất của AppsFlyer</Anchor> xếp hạng các nguồn truyền thông di động theo danh mục và khu vực.

| Loại đối tác | Mô tả |
| --- | --- |
| Mạng quảng cáo | Chạy các chiến dịch thay cho bạn. |
| Đại lý | Sử dụng kiến thức chuyên môn của họ để có được người dùng chất lượng cao bằng cách chạy các chiến dịch thay cho bạn. Bạn có thể có một mối quan hệ minh bạch hoặc không minh bạch. |
| Đối tác tiếp thị | Các đối tác tiếp thị chuyên cộng tác với các mạng quảng cáo cụ thể. Ví dụ: đối tác quản lý chiến dịch Meta, đối tác tiếp thị Apple Search Ads, đối tác quảng cáo chính thức của Twitter. |
| Mạng nhắm mục tiêu lại | Mạng quảng cáo chuyên chạy các chiến dịch nhắm mục tiêu lại. |
| Nền tảng của bên thứ ba | Cung cấp các dịch vụ liên quan đến BI như nền tảng phân tích và tự động hóa tiếp thị. |
| Phân bổ TV | Đối tác cho phép phân bổ chính xác hơn các lượt cài đặt mới cho quảng cáo truyền hình được phát sóng. |
| Phát hiện gian lận | Hệ thống chống gian lận của bên thứ ba bên ngoài không thuộc giải pháp chống gian lận Protect360 của AppsFlyer. |

</Accordion>

<div id="partners-in-the-marketplace" />

<Accordion title="Đối tác trên marketplace">

Bạn có thể tìm thấy tất cả các đối tác, nguồn truyền thông và các nền tảng khác được tích hợp với AppsFlyer trên trang <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations">marketplace</Anchor>. Bạn có thể tìm thấy cả đối tác <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">đang hoạt động và không hoạt động</Anchor> của mình, đồng thời tìm kiếm các đối tác mới để kết nối.

**Để tìm kiếm và lọc tất cả các đối tác, nguồn truyền thông hoặc nền tảng khác trong <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations">Marketplace</Anchor>:**

* Trong AppsFlyer, dưới phần **Configuration** đi đến **Partner Marketplace**. Bạn có thể dùng nhiều <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations#lọc-danh-sách-đối-tác">bộ lọc</Anchor> tìm kiếm.

<div id="invite-new-partners-to-appsflyer" />

#### Mời các đối tác mới vào AppsFlyer

Nếu đối tác mà bạn đang làm việc cùng chưa được tích hợp với AppsFlyer, bạn có thể <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations#mời-các-đối-tác-mới-vào-appsflyer">gửi cho họ một đường liên kết lời mời</Anchor>.

</Accordion>

<div id="your-integrated-partners" />

<Accordion title="Đối tác tích hợp đang hoạt động của bạn">

Trang <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations#tích-hợp-tích-cực">Active integrations</Anchor> trong Partner Marketplace hiển thị tất cả các đối tác tích hợp <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">đang hoạt động</Anchor> của bạn. Từ trang này, bạn có thể tìm hiểu về đối tác và quản lý việc tích hợp.

<div id="note" />

> 📘 **Lưu ý**
>
> Danh sách các đối tác hiển thị trên trang **Active integrations** sẽ thay đổi theo ứng dụng được chọn (ứng dụng cuối cùng được chọn trước khi đưa vào Marketplace). Bạn có thể xem đối tác nào được kết nối với các ứng dụng khác bằng cách nhấp vào ứng dụng từ góc trên cùng bên trái và chọn một ứng dụng khác.

**Để xem tất cả các đối tác hoạt động:**

* Trong AppsFlyer, dưới phần **Configuration**, đi đến **Active Integrations**.

Xem <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations#xem-những-điều-bạn-có-thể-làm-từ-trang-active-integrations">những điều bạn có thể làm từ trang Active integrations</Anchor>.

</Accordion>

<div id="about-the-integrated-partner-page" />

<Accordion title="Giới thiệu về trang cấu hình đối tác">

Trang này có cấu trúc như sau:

* **Tiêu đề**, chứa:
  * Tên đối tác
  * Liên kết đến một bài viết riêng cho đối tác. Nếu không có bài viết riêng nào thì sẽ hiển thị bài viết này.
  * Trạng thái tích hợp
  * Ứng dụng được chọn
* **Các thẻ cài đặt**: Các thẻ này khả dụng tùy thuộc vào loại đối tác và tính năng được hỗ trợ.
* **Chân trang** :
  * **Quay lại danh sách**: Quay lại danh sách Đối tác Tích hợp bằng cách sử dụng các tùy chọn lọc đã chọn trước đó.
  * **Thông báo trạng thái:** Trạng thái hiện tại của dữ liệu trên tab (ví dụ: đang lưu, đã lưu, lỗi, có những nội dung thay đổi chưa lưu).
  * **Hủy Thay đổi:** Hoàn tác các thay đổi gần nhất mà không lưu.
  * **Lưu:** Chỉ lưu tùy chọn cài đặt của tab hiện tại.

<div id="applicable-settings-tabs-per-partner-type" />

#### Các tab cài đặt áp dụng cho mỗi loại đối tác

<table><thead><tr><th> </th><th colspan="2">Tab Cài đặt</th><th> </th></tr><tr><th>Loại đối tác</th><th>Tích hợp </th><th>Quyền</th><th>Lưu ý</th></tr></thead><tbody><tr><td>Nguồn truyền thông</td><td>Y</td><td>Y</td><td><p><strong>Các tab khả dụng khác</strong>: Chi phí, doanh thu quảng cáo, đường dẫn phân bổ</p><p>Bao gồm mạng quảng cáo, mạng liên kết, nhà phát hành trực tiếp, quảng cáo có lập trình, mạng quảng cáo nội địa Trung Quốc và Mạng nhắm mục tiêu lại.<br/>Đối với SRN, tab đường dẫn phân bổ không thể áp dụng.</p></td></tr><tr><td>Đại lý </td><td>N</td><td>Y</td><td>Các đại lý độc lập không hoạt động như mạng quảng cáo </td></tr><tr><td>Nền tảng của bên thứ ba</td><td>Y</td><td>N</td><td>Nền tảng tự động hóa Phân tích hoặc Marketing</td></tr><tr><td>Đối tác tiếp thị </td><td>Y</td><td>N</td><td> </td></tr></tbody></table>

</Accordion>

<div id="important" />

<div id="set-up-a-partner-non-srn" />

## Thiết lập đối tác (không phải SRN)

Để truy cập cài đặt và cấu hình chiến dịch của bạn với đối tác:

1. Tìm kiếm và chọn đối tác của bạn <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations#quản-lý-các-tiện-ích-tích-hợp-hiện-có">từ marketplace</Anchor> hoặc từ trang **Configuration** > **Active** I**ntegrations**.
2. Hoàn thành các cài đặt trên mỗi tab, theo yêu cầu. Xem các phần sau.

<div id="note-1" />

> 📘 **Lưu ý**
>
> Bước [Cài đặt chung](/docs/set-up-an-integrated-partner#d) trong tab **Integration** là bắt buộc với tất cả các đối tác. Bạn cũng phải hoàn thành tab **Attribution link** cho các mạng quảng cáo không phải SRN. Các tab còn lại là không bắt buộc.

<div id="integration-tab" />

<Accordion title="Tab tích hợp">

Tích hợp đối tác sẽ có yêu cầu khác nhau và có thể chứa một tập hợp con của tất cả các tùy chọn có thể được mô tả trong phần này. Có một số khác biệt giữa cài đặt iOS và Android.

<Image align="center" alt="set_up_an_integrated_partner.png" src="https://files.readme.io/441ddfcd784a000099ae75acdb234d32bfe75ab598a34a88c7f9ed651fe8f7ec-15520850610449.png" />

Hoàn thành các mục theo yêu cầu.

<div id="i-connect-more-apps-optional" />

<div id="g-in-app-event-postback-configuration" />

<div id="default-postbacks" />

<div id="e-cross-platform-attribution" />

<div id="reengagement-window" />

<div id="non-eu-users" />

<div id="d-general-settings" />

<div id="c-transaction-id" />

<div id="b-advanced-privacy" />

<div id="a-activate-partner" />

<div id="integration-sections" />

#### Các phần trong Integration

Bảng sau bao gồm các phần khác nhau của trang tích hợp. Một số phần dành cho tất cả mọi người, trong khi những phần khác dành riêng cho mỗi lần tích hợp.

<Table>
  <thead>
    <tr>
      <th>
        Mục
      </th>
      <th>
        Mô tả
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="a"></span>
        Kích hoạt đối tác
      </td>
      <td>
        Trước khi chia sẻ đường dẫn phân bổ với đối tác, bạn phải bật **Activate partner** và hoàn thành các mục còn lại của tab Integration.

        * Không sử dụng **Activate partner** (Kích hoạt đối tác) để tạm dừng hoặc tắt phân bổ chiến dịch
        * Việc tắt tích hợp đối tác **có thể gây ra thiệt hại không thể khắc phục cho các chiến dịch đang hoạt động**.
        * Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">kích hoạt đối tác</Anchor> và tác động của việc hủy kích hoạt đối tác.

        **Để kích hoạt đối tác tích hợp**:

        1. Trong AppsFlyer, đi đến **Configurations** > **Active integrations** >
        2. Tìm kiếm và chọn đối tác. Bạn được chuyển đến trang cấu hình đối tác.
        3. Bật **<Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">Activate partner</Anchor> (Kích hoạt đối tác).**
        4. Nhấp vào **Save Integration** (Lưu Tích hợp).
        5. [Tùy chọn] Để cho phép đối tác <Anchor target="_blank" href="/marketers/vi/docs/manage-data-access-permissions">xem dữ liệu được phân bổ cho họ</Anchor>, hãy đảm bảo bật [Quyền truy cập mạng quảng cáo](/docs/set-up-an-integrated-partner#quyền-truy-cập-mạng-quảng-cáo) trong tab [Quyền](/docs/set-up-an-integrated-partner#permissions-tab).
      </td>
    </tr>
    <tr>
      <td><span id="b"></span>
        Quyền riêng tư Nâng cao
      </td>
      <td>
        Chỉ dành cho ứng dụng iOS:  
        Khi bật **Advanced Privacy (for iOS 14.5+ and later)**, bạn có thể <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">kiểm soát loại dữ liệu nào muốn chia sẻ</Anchor> với đối tác thông qua đăng lại và báo cáo. Điều này hạn chế việc chia sẻ mã định danh người dùng với đối tác. Lưu ý rằng khi bật <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">Aggregated Advanced Privacy</Anchor> trong phần App Settings, **Advanced Privacy (for iOS 14.5+ and later)** sẽ được bật và khóa.
      </td>
    </tr>
    <tr>
      <td><span id="c"></span>
        ID Giao dịch
      </td>
      <td>
        Chỉ dành cho ứng dụng iOS:  
        Khi bật **Share SKAN transaction ID**, bạn đang <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">chia sẻ ID giao dịch của các đăng lại SKAdNetwork</Anchor> với đối tác. Bằng cách làm như vậy, đối tác có thể giải mã Giá trị Chuyển đổi SKAdNetwork của bạn.
      </td>
    </tr>
    <tr>
      <td><span id="d"></span>
        Cài đặt chung
      </td>
      <td>
        **Partner ID—Credentials**  
        Một số đối tác yêu cầu thông tin đăng nhập để AppsFlyer tích hợp với họ. Đối tác gọi ID này là ID ứng dụng, ID tài khoản, ID người dùng hoặc ID mạng. Nếu trường này hiển thị, hãy lấy ID từ bảng điều khiển của đối tác và nhập ID đó vào trường.
      </td>
    </tr>
    <tr>
      <td><span id="e-install-attribution"></span>
        Phân bổ lượt cài đặt
      </td>
      <td>
        Khi bật **Install attribution**, các lượt cài đặt mới của người dùng đã xem quảng cáo nhưng không nhấp vào quảng cáo đó sẽ được phân bổ.
      </td>
    </tr>
    <tr>
      <td><span id="e-re-engagement-attribution"></span>
        Phân bổ thu hút lại
      </td>
      <td>
        Bật và đặt khung thời gian xem lại để bắt đầu phân bổ lượt thu hút lại của người dùng hiện có của bạn. Đối với đối tác không phải SRN, cài đặt này có sẵn trong thẻ Integration hoặc trong thẻ [đường dẫn phân bổ](/docs/set-up-an-integrated-partner#thiết-lập-nhắm-lại-mục-tiêu).

        * **Re-engagement view-through attribution:** Khi được bật, các lượt thu hút lại người dùng đã xem quảng cáo của bạn nhưng không nhấp vào quảng cáo đó sẽ được phân bổ.
        * **Re-engagement click-through attribution:** Khi được bật, các lượt thu hút lại người dùng đã nhấp vào quảng cáo của bạn sẽ được phân bổ.
      </td>
    </tr>
    <tr>
      <td><span id="ignore-active-users"></span>
        Bỏ qua người dùng đang hoạt động để nhắm mục tiêu lại (SRN)
      </td>
      <td>
        Khi bật **Re-engagement attribution**, tùy chọn **Ignore active users for retargeting** (hiển thị cho <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns">SRN</Anchor>) sẽ được bật. Khi được bật và đặt **Inactivity window**, các lượt chuyển đổi nhắm mục tiêu lại người dùng đang hoạt động trong khung thời gian không hoạt động sẽ bị bỏ qua và không được ghi nhận trong AppsFlyer.
      </td>
    </tr>
    <tr>
      <td><span id="e"></span>
        Phân bổ nền tảng chéo
      </td>
      <td>
        Khi bật **Cross-platform equal attribution priority**, các lượt hiển thị trên nền tảng chéo trong khung thời gian đã chọn có mức độ ưu tiên phân bổ như nhau.
      </td>
    </tr>
    <tr>
      <td><span id="f-preload-attribution"></span>
        Phân bổ tải trước
      </td>
      <td>
        Khi bật **Preload attribution**, các lượt cài đặt được phân bổ cho <Anchor target="_blank" href="/marketers/vi/docs/measure-preload-campaigns-with-google-play-install">các chiến dịch tải trước</Anchor>. Đặt **Preload lookback window** để xác định khoảng thời gian sau khi kích hoạt thiết bị, lượt cài đặt tải trước có thể được phân bổ cho đối tác.
      </td>
    </tr>
    <tr>
      <td><span id="f-preload-equal-attribution-priority"></span>
        Mức độ ưu tiên phân bổ ngang bằng tải trước
      </td>
      <td>
        Khi bật **Preload equal attribution priority**, thu hút tải trước trong khung thời gian xem lại đã chọn có <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#phương-thức-phân-bổ">mức độ ưu tiên phân bổ</Anchor> như các lượt nhấp xác định.
      </td>
    </tr>
    <tr>
      <td><span id="advanced-data-sharing"></span>
        Chia sẻ Dữ liệu Nâng cao
      </td>
      <td>
        Khi tính năng **Advanced Data Sharing** được bật, dữ liệu bổ sung sẽ được chia sẻ với đối tác thông qua liên kết phân bổ.  
        **Lưu ý:** Tùy chọn chia sẻ này khác với tùy chọn <Anchor target="_blank" href="/marketers/vi/docs/meta-ads-integration-setup#aem-data-sharing">chia sẻ dữ liệu AEM Advanced của Meta ads</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="f"></span>
        Postback Mặc định
      </td>
      <td>
        Nếu bật partner integration, bạn có thể gửi đăng lại mặc định cho các đối tác liên quan đến hành động của người dùng xảy ra trước khi khởi chạy ứng dụng, chẳng hạn như lượt cài đặt, lượt cài đặt bị từ chối và lượt thu hút lại.

        <div id="01H80XGTBQ4MPGGKSZW0D9GG9H" />

        > 📘 **Lưu ý**
        >
        > * Các sự kiện bị từ chối là các sự kiện trong ứng dụng bị <Anchor target="_blank" href="/marketers/vi/docs/protect360-anti-fraud-guide">Protect360</Anchor> chặn hoặc các sự kiện được phát hiện là không tuân thủ theo quy tắc xác thực mục tiêu. Trong trường hợp các sự kiện bị từ chối, hãy xác nhận với đối tác rằng họ đã bật tự chối tích hợp sự kiện với AppsFlyer.
        > * Các đối tác không thực hiện phân bổ (như nền tảng của bên thứ ba) chỉ nhận được bài đăng lại mặc định cho các lượt cài đặt. Bài đăng lại phân bổ được gửi đến đối tác được phân bổ.

        **Để định cấu hình đăng lại mặc định cho đối tác**, hãy xác định nguồn người dùng để gửi đăng lại:

        * **Chỉ đối tác này**: Chỉ gửi đăng lại khi sự kiện được phân bổ cho đối tác này—nghĩa là người dùng thực hiện sự kiện đến từ đối tác này.  
          **Lưu ý:** Trong các trường hợp sau, đăng lại mặc định luôn được xác định là **Chỉ đối tác này**:
          * Lượt cài đặt bị từ chối
          * Đại lý (có [quyền](/docs/set-up-an-integrated-partner#cấp-quyền-cho-đại-lý))
        * **Tất cả các nguồn truyền thông bao gồm tự nhiên**: Gửi đăng lại cho các sự kiện được phân bổ cho bất kỳ đối tác nào và cho các sự kiện tự nhiên—nghĩa là người dùng thực hiện nó đến từ bất cứ nguồn truyền thông nào.
        * **Tắt**: Không gửi đăng lại mặc định cho đối tác này.
      </td>
    </tr>
    <tr>
      <td><span id="g"></span>
        <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration">Đăng lại sự kiện trong ứng dụng</Anchor>
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#ánh-xạ-sự-kiện">Ánh xạ</Anchor> các sự kiện AppsFlyer với các sự kiện của đối tác thông qua đăng lại. Nếu bật tính năng gửi đăng lại, điều này bao gồm các sự kiện trong ứng dụng bị từ chối (các sự kiện bị Protect360 chặn hoặc các sự kiện bị phát hiện là không tuân thủ theo quy tắc xác thực mục tiêu).

        **Để cấu hình đăng lại sự kiện trong ứng dụng:**

        1. Đặt **ID Đối tác** (nếu cần).
        2. Bật **In-app event postbacks**.
        3. Thiết lập **Khung thời gian đăng lại sự kiện trong ứng dụng**, nếu cần (đọc thêm về <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#khung-thời-gian-đăng-lại-sự-kiện-trong-ứng-dụng">cấu hình khung thời gian đăng lại sự kiện trong ứng dụng</Anchor>).
        4. Nhấp vào **Add event** để thêm một SDK hoặc sự kiện từ máy chủ đến máy chủ vào danh sách.
        5. Điền các thông số cần thiết theo <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#phương-thức-ánh-xạ">phương pháp ánh xạ</Anchor>.
        6. [Tùy chọn] Nhấp vào<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/e2543cb26e0cc02f4840040721376ae88a4015a24ac1fc271264e3965560c1f9-4413022777105.png" width="30px" /> để <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#đăng-lại-sự-kiện-trong-ứng-dụng-có-điều-kiện">đặt điều kiện</Anchor> gửi các sự kiện trong ứng dụng nhất định cho đối tác.

        | Tên thông số | Mô tả |
        | --- | --- |
        | <span id="appsflyer-event"></span>**AppsFlyer event** | Tên của sự kiện mà AppsFlyer nhận được từ SDK sẽ được tích hợp vào ứng dụng của bạn hoặc từ các sự kiện máy chủ đến máy chủ.  <br />**Mẹo**: Bạn không thấy sự kiện đang tìm kiếm?<br /><br />* Hãy đảm bảo kích hoạt sự kiện trên thiết bị có cài đặt không tự nhiên và kiểm tra lại.<br />* Nhập vào **AppsFlyer event**, sau đó nhấp vào **Create custom**. Đọc thêm về <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#sự-kiện-tùy-chỉnh">ánh xạ sự kiện tùy chỉnh.</Anchor> |
        | <span id="mapped-to-partner-event"></span>**mapped to partner event** | Tên hoặc ID duy nhất của từng sự kiện được xác định ở phía đối tác. <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#phương-thức-ánh-xạ">Các cấu hình ánh xạ có thể có</Anchor> là:<br /><br />* **Trường văn bản:** Nhận ID sự kiện tương ứng từ đối tác.<br />* **Hộp thả xuống:** Chọn sự kiện đối tác được xác định trước phù hợp nhất.<br />* **Giữ nguyên**: Gửi các sự kiện như vốn có mà không ánh xạ tên sự kiện. |
        | <span id="for-users-from"></span>**for users from** | Chọn tùy chọn gửi cho sự kiện:<br /><br />* **Chỉ đối tác này**: Chỉ gửi đăng lại khi sự kiện được phân bổ cho đối tác này—nghĩa là người dùng thực hiện sự kiện đến từ đối tác này.<br />* **Tất cả các nguồn truyền thông bao gồm tự nhiên**: Gửi đăng lại cho các sự kiện được phân bổ cho bất kỳ đối tác nào và cho các sự kiện tự nhiên—nghĩa là khi người dùng thực hiện nó đến từ bất cứ nguồn truyền thông nào. |
        | <span id="including"></span>**including** | Chọn <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#dữ-liệu-cần-đưa-vào-đăng-lại">dữ liệu sự kiện nào</Anchor> cần chia sẻ với đối tác trong đăng lại:<br /><br />* **Không có giá trị & không có doanh thu**: Chỉ gửi bản thân sự kiện mà không kèm bất kỳ thông số nào (giá trị hoặc doanh thu).<br />* **Không có giá trị & không có doanh thu**: Gửi tất cả các thông số, **ngoại trừ** giá trị doanh thu.<br />* **Giá trị & doanh thu**: Gửi tất cả các thông số sự kiện, **bao gồm** cả giá trị doanh thu (nếu có trong sự kiện). |

         Lưu ý:

        * Các sự kiện được ánh xạ trong tab Integration cho một đối tác cụ thể có thể áp dụng cho cả đăng lại tiêu chuẩn và <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">SKAN</Anchor>.
        * Đăng lại được gửi đến các đối tác trong thời gian thực.
        * Tên sự kiện AppsFlyer có thể được chọn hoặc nhập vào.  
          Các giá trị đã nhập được phép có khoảng trống được gạch dưới (dấu gạch ngang dưới) trước hoặc sau tên của sự kiện. Chỉ sử dụng dấu cách được gạch dưới nếu tên sự kiện được gửi từ AppsFlyer có cùng dấu cách được gạch dưới.
        * **Quan trọng**: Tên sự kiện có phân biệt chữ hoa chữ thường. Để tránh sai lệnh, hãy đảm bảo bạn sử dụng chính xác tên sự kiện cho tất cả các nguồn truyền thông và phiên bản ứng dụng.
        * Nếu phần **In-app event postbacks** không tồn tại trong tab **Integration**, điều đó có nghĩa là đối tác chưa thiết lập ghi nhận sự kiện trong ứng dụng với AppsFlyer trong cấu hình sơ bộ. Đối tác có thể liên hệ với AppsFlyer bằng <Anchor target="_blank" href="https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif">widget trợ lý đối tác</Anchor> để hoàn tất quá trình tích hợp.
        * Để ngăn các nhà quảng cáo vô tình chia sẻ quá nhiều thông tin với nền tảng của bên thứ ba, chúng tôi đã xóa tùy chọn **Send all events (excludes uninstalls and sessions)** cho nền tảng của bên thứ ba, kể từ tháng 3 năm 2019. Nền tảng của bên thứ ba được định cấu hình trước đó vẫn giữ tùy chọn thiết lập này.

        Bài đọc liên quan:

        * Cấu hình <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration">đăng lại sự kiện trong ứng dụng</Anchor>
        * Cấu hình <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">đăng lại sự kiện doanh thu quảng cáo</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="h"></span>
        Lưu tích hợp
      </td>
      <td>
        Nhấp vào **Save Integration** sau khi thực hiện thay đổi.
      </td>
    </tr>
    <tr>
      <td><span id="i"></span>
        Kết nối nhiều ứng dụng hơn (tùy chọn)
      </td>
      <td>
        Sau khi lưu tích hợp, trong khi vẫn ở trang cấu hình, bạn có thể tích hợp thêm ứng dụng của mình với đối tác.

        1. Từ góc trên cùng bên trái, dưới tên đối tác, hãy nhấp vào tên ứng dụng để mở danh sách ứng dụng.
        2. Chọn một ứng dụng khác từ danh sách thả xuống.
        3. Lặp lại các bước tích hợp đối với ứng dụng đã chọn.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Tab Liên kết Phân bổ">

Tạo và lưu các đường dẫn phân bổ để sử dụng mạng quảng cáo lượt nhấp (không phải SRN) và gửi đường dẫn phân bổ đến đối tác để phân bổ các chiến dịch, bộ quảng cáo hoặc quảng cáo đơn lẻ cụ thể.

**Lưu ý:** SRN không thực hiện các đường dẫn phân bổ do nhà quảng cáo tạo nên tab này không liên quan đến các chiến dịch SRN.

**Để tạo đường dẫn phân bổ**:

1. Chọn **Use a single-platform link** hoặc **Use OneLink**.

   Chọn **Use a single-platform link** nếu đúng với bất kỳ trường hợp nào sau đây:

   * Bạn dự định chỉ sử dụng <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">lược đồ URI</Anchor> để mở ứng dụng.
   * Bạn không cần phải liên kết sâu với URL.

   Chọn **Use OneLink** nếu đúng với bất kỳ trường hợp nào sau đây:

   * Bạn muốn có một liên kết duy nhất cho cả ứng dụng Android và iOS.
   * Bạn muốn sử dụng Liên kết Ứng dụng Android hoặc Liên kết Chung iOS để mở ứng dụng.
   * Bạn muốn chức năng liên kết sâu.

   **Lưu ý**: Việc chọn OneLink sẽ thay đổi liên kết ghi nhận lượt nhấp từ ứng dụng cụ thể thành <Anchor target="_blank" href="/marketers/vi/docs/onelink-guide">URL OneLink</Anchor>.
2. Nếu bạn đã chọn **Use OneLink**:

   1. Chọn mẫu OneLink bạn muốn sử dụng để mở ứng dụng (và có thể là liên kết sâu).
   2. [Tùy chọn] Nhập **giá trị Liên kết sâu**.
   3. [Tùy chọn] Nhập **Giá trị liên kết sâu bổ sung**.
3. Thêm thông số cho <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters#các-tham-số-cụ-thể-cho-android">Android</Anchor> và <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters#các-thông-số-cụ-thể-cho-ios">iOS</Anchor>, nếu cần.
4. [Tùy chọn] Chọn các thông số phân bổ bổ sung.

<div id="attribution-link-parameters" />

#### Thông số đường dẫn phân bổ

<Image align="center" alt="attribution-link-parameters-en_us.png" src="https://files.readme.io/5f010d760295d53b8ff1891b58aaa57ac8171af7d08d7bc0df07b0998f81f666-4414306787601.png" />

Việc thêm thông số vào đường dẫn phân bổ này cho phép bạn thực hiện việc phân tích truy cập sâu toàn diện. Các thông số đã được xác định trên đường dẫn phân bổ có thể được chỉnh sửa bằng cách thêm chúng và các giá trị mới của chúng ở đây. Khi lưu đường dẫn phân bổ, tất cả các thông số được cấu hình trong tab này cũng sẽ được lưu.

Chọn thông số bạn muốn thêm vào đường dẫn phân bổ.

<div id="attribution-link-parameters-1" />

#### Thông số đường dẫn phân bổ

| Tên | Mô tả | Thông số đường dẫn phân bổ |
| --- | --- | --- |
| Chiến dịch | **Thông số bắt buộc.**  <br />So sánh các chiến dịch khác nhau đang chạy với nguồn truyền thông. | c |
| Bộ quảng cáo | So sánh các bộ quảng cáo khác nhau trong các chiến dịch cụ thể của nguồn truyền thông. | af\_adset |
| Tên Quảng cáo | So sánh các nội dung quảng cáo khác nhau trong các bộ quảng cáo cụ thể trong các chiến dịch cụ thể của nguồn truyền thông. | af\_ad |
| ID Trang web và ID Trang Phụ | **Thông số bắt buộc.**<br /><br />Đặt ID Trang web để phân bổ lượt cài đặt cho các nhà phát hành cụ thể.<br /><br />ID trang web phải được chuyển đến AppsFlyer trong đường dẫn phân bổ vì ID này:<ul><li>Cho phép minh bạch và tăng tính rõ ràng về nhà phát hành</li><li>Được AppsFlyer sử dụng để xác định và loại bỏ các nhà phát hành gian lận và các cụm lưu lượng truy cập khác.</li></ul>Lưu ý rằng ID Trang web bị thiếu sẽ không ảnh hưởng đến việc phân bổ. Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters#site-id-parameter">thông số ID Trang web</Anchor>.<br /><br />Nếu có nhiều nhà phát hành, chúng tôi đề nghị bạn nên hạn chế số lượng ID trang web đã sử dụng và sử dụng thông số ID trang phụ, để tránh <Anchor target="_blank" href="/marketers/vi/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">vượt quá giới hạn ID trang web</Anchor>. | af\_siteid và af\_sub\_siteid |
| Thông số Người đăng ký | Sử dụng bất kỳ thông số nào trong số 5 thông số người đăng ký để chèn các giá trị hữu ích. Lưu ý rằng các tham số này được phân tích cú pháp và xuất hiện trong báo cáo dữ liệu thô, giúp chúng trở nên rất tiện dụng để thực hiện hợp nhất hoặc lọc dữ liệu. | af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5 |

Bạn có thể thêm các thông số khác vào đường dẫn phân bổ bằng cách nhập chúng vào hộp thông số mới. Bạn có thể sử dụng tất cả các <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters">thông số URL có sẵn của AppsFlyer.</Anchor> Lưu ý rằng chỉ lược đồ URI và thông số OneLink được mã hóa trên đường dẫn phân bổ.

<div id="retargeting-settings" />

#### Thiết lập Nhắm lại mục tiêu

**Khi bật tùy chọn nhắm mục tiêu lại**: AppsFlyer nhận diện được đường dẫn dưới dạng đường dẫn phân bổ <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide">nhắm mục tiêu lại</Anchor>, mà không phải là đường dẫn thu hút người dùng, bằng cách thêm `&is_retargeting=true` vào đường dân phân bổ. **Tham số liên kết phân bổ:** is\_retargeting

Để sử dụng đường dẫn của bạn để nhắm mục tiêu lại:

1. Bật tùy chọn **Retargeting settings**.
2. [Tùy chọn] Nhập lược đồ URI nếu bạn muốn lược đồ URI mở ứng dụng.  
   **Lưu ý**: 
   * Các lược đồ URI được khuyến nghị sử dụng làm phương thức dự phòng để mở ứng dụng nếu Liên kết Chung hoặc Liên kết Ứng dụng không thành công.
   * Nếu bạn thêm một lược đồ URI tại đây, lược đồ này sẽ ghi đè bất kỳ lược đồ URI nào khác đã có trong cài đặt mẫu OneLink.
   * Lược đồ URI được thêm vào liên kết trong thông số af\_dp.
3. [Tùy chọn] Bật tùy chọn **Ignore active users for retargeting**.
4. Đặt khung thời gian không hoạt động để xác định người dùng nào được coi là hoạt động và không hoạt động.
5. Đặt khung thời gian thu hút lại để xác định khoảng thời gian sau thu hút lại, nơi các sự kiện trong ứng dụng của người dùng được phân bổ cho nguồn truyền thông nhắm mục tiêu lại.

   * Bạn có thể đặt giá trị theo ngày (1-90), giờ (tối đa 23) hoặc thậm chí là trọn đời.
   * Khung thời gian thu hút lại được thêm vào liên kết trong thông số af\_reengagement\_window.

<div id="click-through-attribution" />

#### Phân bổ lượt nhấp qua

Sử dụng tùy chọn cài đặt để đặt **thời gian tối đa từ khi nhấp đến lúc cài đặt**. Chỉ các lượt cài đặt (lần khởi chạy đầu tiên) diễn ra trong khung thời gian xem lại mới được phân bổ.

Phạm vi cho phép: 1-23 giờ hoặc 1-30 ngày.

**Thông số liên kết phân bổ:**  af\_click\_lookback

Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows">khung thời gian xem lại lượt nhấp</Anchor>.

**Liên kết Phân bổ Nhấp chuột**

<Image align="center" alt="click-through-attribution-link_en-us.png" src="https://files.readme.io/aba15af3164c4f233625cd56f90aa4d1a18b834cfb151c4e7042fa099c8f9125-4411038599953.png" />

Đây là liên kết phân bổ chứa tất cả thông tin thiết lập bạn đã đặt. Bạn có thể lưu đường dẫn để tham khảo sau này bằng cách nhấp vào **Save attribution link** (Lưu đường dẫn phân bổ).

**Để sao chép đường dẫn phân bổ lượt nhấp:**

1. Nhấp vào **Save attribution link** (Lưu đường dẫn phân bổ).
2. Sao chép đường dẫn được tạo.

Gửi đường dẫn đến đối tác để được kích hoạt khi khách hàng tiềm năng của bạn nhấp vào quảng cáo tương ứng.

<div id="view-through-attribution-lookback-window" />

#### Cửa sổ xem lại phân bổ lượt xem qua

Đặt **thời gian tối đa từ lúc hiển thị đến lúc cài đặt**. Chỉ các lượt cài đặt (lần khởi chạy đầu tiên) diễn ra trong khoảng thời gian xem lại này, sau một lần hiển thị quảng cáo, được phân bổ cho đối tác, miễn là không có nhấp chuột quảng cáo có liên quan khác.

Bạn có thể tùy chỉnh giá trị này thành 1-24 giờ.

**Thông số liên kết phân bổ:** af\_viewthrough\_lookback

Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows">phân bổ lượt xem qua</Anchor>.

**Liên kết Phân bổ Số lần hiển thị**

<Image align="center" alt="impressions-attribution-link_en-us.png" src="https://files.readme.io/76a2d084f66f3a279b281f60a465af5098e05de8de128cfd6f04a97fe52c4dc6-4411047429265.png" />

Đường dẫn phân bổ lượt hiển thị chứa dữ liệu phân bổ tương tự với liên kết ghi nhận lượt nhấp (bên cạnh khung thời gian xem lại khác). Bạn có thể lưu đường dẫn để tham khảo sau này bằng cách nhấp vào **Save attribution link** (Lưu đường dẫn phân bổ).

Nhấp vào Lưu đường dẫn phân bổ rồi sao chép đường dẫn đã tạo.

**Để sao chép đường dẫn phân bổ lượt xem:**

1. Nhấp vào **Save attribution link** (Lưu đường dẫn phân bổ).
2. Sao chép đường dẫn được tạo.

Gửi đường dẫn cho đối tác để được kích hoạt khi quảng cáo tương ứng được xem, thường trong 1 giây trở lên.

</Accordion>

<div id="cost-tab" />

<Accordion title="Thẻ Cost">

* Dữ liệu chi phí được báo cáo bởi các đối tác tích hợp của bạn khi nhấp hoặc bởi API Chi phí.
* Thực hành tốt nhất là triển khai API Chi phí (yêu cầu phải có đăng ký ROI360).
* API Chi phí bao gồm các báo cáo lượt nhấp và lượt hiển thị. Xem <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">bảng tích hợp chi phí mạng quảng cáo</Anchor> để biết chi tiết đầy đủ về các phương diện, số liệu và tính năng được hỗ trợ.

<div id="note-2" />

> 📘 **Lưu ý**
>
> Nếu nhà quảng cáo sử dụng đại lý để chạy các chiến dịch của họ, thì chính đại lý đó chứ không phải nhà quảng cáo, cần tích hợp với các đối tác có liên quan. Mặt khác, nếu cả nhà quảng cáo và đại lý đều tích hợp với đối tác bằng cách sử dụng cùng thông tin đăng nhập cho cùng một ứng dụng, thì dữ liệu chi phí sẽ bị trùng lặp.

<div id="enabling-cost-data-by-api" />

#### Kích hoạt dữ liệu chi phí bằng API

**Để kích hoạt API Chi phí**:

* Tuân thủ <Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">hướng dẫn tích hợp này</Anchor>.

<div id="cost-data-sync-status" />

#### Trạng thái đồng bộ dữ liệu chi phí

<Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Xem trạng thái API chi phí của bạn</Anchor> và lần cuối cùng AppsFlyer lấy được dữ liệu chi phí phù hợp trong trang tổng quan trạng thái tích hợp chi phí (và doanh thu quảng cáo) hoặc trang tổng quan mạng quảng cáo cá nhân.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Tab Doanh thu quảng cáo">

Nếu bạn là nhà phát hành hiển thị quảng cáo trong ứng dụng, thì chức năng doanh thu quảng cáo sẽ cho phép bạn phân bổ doanh thu quảng cáo tới nguồn truyền thông đã mang cho bạn người dùng. <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution">Giới thiệu về phân bổ doanh thu quảng cáo.</Anchor>

<div id="enable-ad-revenue-attribution" />

#### Cho phép phân bổ doanh thu quảng cáo

1. Kiểm tra xem đối tác hỗ trợ phương thức nào, <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution#list-of-ad-revenue-integrated-partners">phân bổ hợp nhất hay cấp độ người dùng</Anchor>.
2. Thực hiện theo phương thức phù hợp trong <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution#thực-hiện">hướng dẫn tích hợp doanh thu quảng cáo</Anchor>.

<div id="ad-revenue-api-status-messages" />

#### Thông báo trạng thái API doanh thu quảng cáo

| Trạng thái | Nhận xét/hành động cần thiết |
| --- | --- |
| Hoạt động | Kết nối là trực tiếp và kéo dữ liệu. |
| Không tìm thấy dữ liệu để kéo về. | Kết nối thành công. Đối tác không có bất kỳ dữ liệu nào liên quan đến ứng dụng này. |
| API đối tác không phản hồi. Hãy liên hệ với bộ phận hỗ trợ của AppsFlyer. | Máy chủ của đối tác không phản hồi AppsFlyer. |
| Thông tin đăng nhập không hợp lệ. Nhập thông tin đăng nhập đã cập nhật. |  |
| Đã xảy ra lỗi. Hãy liên hệ với bộ phận hỗ trợ của AppsFlyer. | Đã xảy ra vấn đề về kỹ thuật. |
| Dữ liệu đối tác chưa sẵn sàng. Nếu vấn đề vẫn tiếp diễn, vui lòng liên hệ với bộ phận hỗ trợ của AppsFlyer. |  |
| Dữ liệu đang được xử lý và sẽ có sớm. | Chúng tôi hiện đang xử lý dữ liệu nhận được từ đối tác. Dữ liệu sẽ có sẵn trong bảng điều khiển và báo cáo. |
| Dữ liệu chưa bao giờ được kéo thành công | Nếu tình trạng này vẫn tiếp diễn trong hơn một giờ, hãy liên hệ với bộ phận hỗ trợ của AppsFlyer. |

</Accordion>

<div id="permissions-tab" />

<Accordion title="Tab quyền truy cập">

* Cho phép đối tác thực hiện các hành động khác nhau và truy cập dữ liệu của bạn theo các quyền hiện có.
* Bạn không cần phải bật tích hợp phân bổ với đối tác để cấp quyền cho họ.
* **Mạng quảng cáo do đại lý thiết lập:** Khi việc thiết lập đối tác do đại lý thực hiện thì nhà quảng cáo không thể xem trạng thái kích hoạt mạng quảng cáo cũng như các quyền được cấp.
* Nếu mối quan hệ của bạn với đối tác chỉ là đại lý, thì hãy bỏ qua phần **Quyền cấp cho Mạng Quảng cáo** và đặt phần **Quyền cấp cho Đại lý**.

<div id="note-3" />

<div id="ad-network-permissions" />

#### Quyền truy cập mạng quảng cáo

**Để trao quyền cho mạng quảng cáo và các thành viên nhóm:**

1. Bật **Quyền truy cập mạng quảng cáo**.
   * Ứng dụng của bạn xuất hiện trên bảng điều khiển của mạng quảng cáo.
   * Quản trị viên mạng quảng cáo có quyền <Anchor target="_blank" href="/marketers/vi/docs/manage-data-access-permissions">xem dữ liệu cơ bản về ứng dụng.</Anchor>
2. Cấp quyền cho thành viên nhóm mạng quảng cáo:  
   * Để cấp quyền cho các thành viên cụ thể trong nhóm, bạn cần thêm họ bằng cách sử dụng địa chỉ email của họ.  
     **Để thêm một thành viên nhóm**:
     1. Nhấp vào **Add team member** (Thêm thành viên nhóm).
     2. Nhập email của thành viên nhóm mạng quảng cáo
     3. Nhấp vào **Add** (Thêm).
3. Chọn các quyền bổ sung để cấp cho mạng quảng cáo: 

| **Quyền** | **Quyền hạn được cấp** |
| --- | --- |
| <span id="configure-integration"></span>Cấu hình tích hợp | Mạng quảng cáo có thể thay đổi các thông số trong tab tích hợp |
| <span id="configure-inapp-event-postbacks"></span>Cấu hình đăng lại sự kiện trong ứng dụng | Mạng quảng cáo có thể: Tạo, xác định và thay đổi cài đặt đăng lại.<br /><br />**Thận trọng**! Khi quyền này và tùy chọn **Configure integration** đồng thời được bật: mạng quảng cáo có quyền truy cập vào tất cả các sự kiện. Điều này bao gồm lưu lượng truy cập tự nhiên và không tự nhiên từ tất cả các nguồn truyền thông. |
| <span id="access-retention-report"></span>Truy cập báo cáo giữ lại người dùng | Mạng quảng cáo có thể truy cập vào báo cáo giữ lại người dùng trên ứng dụng. Họ sẽ chỉ thấy dữ liệu liên quan đến phiên của họ. |
| <span id="access-aggregate-loyal-users-data"></span>Truy cập dữ liệu người dùng trung thành hợp nhất | Mạng quảng cáo có thể truy cập chỉ số <Anchor target="_blank" href="/marketers/vi/docs/about-a-loyal-user">người dùng trung thành</Anchor> của riêng họ. |
| <span id="access-aggregate-conversions-data"></span>Truy cập dữ liệu chuyển đổi hợp nhất | Mạng quảng cáo có thể truy cập báo cáo hợp nhất về chỉ số sự kiện chuyển đổi của họ. Các chỉ số này bao gồm lượt cài đặt, lượt tương tác lại, lượt cài đặt lại và lượt phân bổ lại. Ví dụ: <Anchor target="_blank" href="/partners/vi/docs/aggregated-campaign-performance-report-for-ad-networks">Hiệu suất chiến dịch tổng hợp cho báo cáo mạng quảng cáo</Anchor>. |
| <span id="access-aggregate-inapp-events-data"></span>Truy cập dữ liệu sự kiện trong ứng dụng hợp nhất | Mạng quảng cáo có thể:<ul><li>Truy cập báo cáo hợp nhất dữ liệu sự kiện trong ứng dụng. Đối tác có quyền truy cập vào tất cả dữ liệu sự kiện trong ứng dụng, bao gồm dữ liệu sự kiện trong ứng dụng Protect360, không chỉ với các sự kiện được ánh xạ trong cấu hình đăng lại.</li><li>Truy cập báo cáo hợp nhất dữ liệu kiếm tiền từ quảng cáo, có thể bao gồm sự kiện kiếm tiền từ quảng cáo đến từ các nguồn truyền thông khác.</li></ul> |
| <span id="view-validation-rules"></span>Xem các quy tắc xác thực | Mạng quảng cáo có thể xem chi tiết <Anchor target="_blank" href="/marketers/vi/docs/implement-validation-rules-to-prevent-fraud">quy tắc xác thực</Anchor>. |
| <span id="access-aggregate-revenue-data"></span>Truy cập dữ liệu doanh thu hợp nhất | Mạng quảng cáo có thể truy cập báo cáo hợp nhất về dữ liệu trong ứng dụng và dữ liệu doanh thu quảng cáo được phân bổ cho người dùng do mạng quảng cáo cung cấp. **Lưu ý:** Quyền này không trực tiếp xác định đối tác doanh thu quảng cáo. Tuy nhiên, nếu bạn đã đặt tên sự kiện kiếm tiền để đưa vào cả tên đối tác, bạn có thể vô tình tiết lộ danh tính của mạng kiếm tiền. |
| <span id="use-ad-spend-ingestion"></span>Sử dụng nhập chi tiêu quảng cáo | Mạng quảng cáo có thể:<ul><li>Truy cập cửa sổ <Anchor target="_blank" href="/marketers/vi/docs/import-cost-data">Ad Spend Ingestion</Anchor>. Cửa sổ này chỉ hiển thị các ứng dụng họ có quyền truy cập.</li><li>Gửi tệp chi tiêu quảng cáo để nhập.</li></ul> |
| <span id="access-protect360-dashboard-raw-data"></span>Truy cập bảng điều khiển Protect360 & dữ liệu thô | Mạng quảng cáo có thể:<ul><li>Truy cập bảng điều khiển Protect360 của họ (bao gồm <Anchor target="_blank" href="/marketers/vi/docs/basic-fraud-detection-and-insights-with-protectlite-dashboard-and-reporting">ProtectLITE</Anchor>).</li><li>Truy cập Protect360, Quy tắc xác thực và dữ liệu thô nếu nằm trong gói đăng ký. ProtectLITE không bao gồm quyền truy cập vào dữ liệu thô.</li></ul>**Lưu ý:** Khi bạn có đăng ký <Anchor target="_blank" href="/marketers/vi/docs/protect360-anti-fraud-guide">Protect360</Anchor>, mạng quảng cáo có thể xem toàn bộ bảng điều khiển. Nếu không có đăng ký Protect360, họ có thể xem bảng điều khiển thu gọn. |
| <span id="access-ad-revenue-raw-data"></span>Truy cập dữ liệu thô về doanh thu quảng cáo | Mạng quảng cáo có thể truy cập <Anchor target="_blank" href="/partners/vi/docs/ad-revenue-signals-for-ua-ad-networks">dữ liệu doanh thu quảng cáo của họ để tối ưu hóa UA</Anchor>.   <br />**Lưu ý:** Quyền này chỉ khả dụng cho các ứng dụng có đăng ký <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>. |

<div id="important-1" />

<div id="agency-permissions" />

#### Cấp quyền cho Đại lý

* Khi bạn cấp quyền cho các đại lý, họ có thể cấp quyền cho các mạng quảng cáo mà họ hợp tác cùng để quản lý ứng dụng của bạn. Điều này giống như cấp quyền cho các mạng quảng cáo.
* Nếu bạn làm việc với mạng quảng cáo và đại lý của bạn cũng hoạt động với mạng quảng cáo này, cả bạn và đại lý đều có thể chỉnh sửa quyền thành viên nhóm quảng cáo để xem bảng điều khiển của ứng dụng. Điều này có nghĩa là nếu bạn thấy các thành viên nhóm mạng quảng cáo mới mà không phải bạn thêm vào hoặc thấy thiếu các thành viên nhóm mà không phải do bạn xóa, thì có thể nhà tiếp thị đã thêm hoặc xóa họ.
* **Thận trọng:** Các lượt cài đặt của đại lý xảy ra trong khi cơ chế kiểm soát bị tắt sẽ không được phân bổ cho đại lý và không hiển thị trên bảng điều khiển và dữ liệu của đại lý. Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation#agency-permissions">kích hoạt đại lý</Anchor>.
* Đọc tất cả về <Anchor target="_blank" href="/partners/vi/docs/getting-started-agency-onboarding#what-does-it-mean-to-get-permission-from-a-marketer">những hành động đại lý có thể thực hiện</Anchor> khi được cấp quyền.

**Để cấp quyền cho đại lý:**

1. Bật **quyền truy cập cho Đại lý**.
2. Chọn các quyền sẽ cấp cho đại lý: 

| **Quyền** | **Quyền hạn được cấp** |
| --- | --- |
| <span id="change-advanced-privacy-configuration"></span>Thay đổi cấu hình Quyền riêng tư Nâng cao | Đại lý có thể thay đổi cài đặt <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">Chia sẻ dữ liệu Quyền riêng tư Nâng cao</Anchor> của mạng quảng cáo. |
| <span id="access-retention-and-cohort-reports"></span>Truy cập báo cáo giữ lại người dùng và nhóm người | Đại lý chỉ có thể truy cập dữ liệu giữ lại người dùng/nhóm người được tạo bởi người dùng do đại lý mang đến. |
| <span id="access-aggregate-organic-data"></span>Truy cập dữ liệu tự nhiên hợp nhất | Đại lý có thể truy cập dữ liệu tự nhiên hợp nhất |
| <span id="view-validation-rules::6872643b"></span>Xem các quy tắc xác thực | Đại lý có thể xem thông tin chi tiết về quy tắc xác thực. |
| <span id="add-validation-rules"></span>Thêm quy tắc xác thực | Đại lý có thể thêm và chỉnh sửa quy tắc xác thực. Khả dụng khi bật **View validation rules**.   <br />**Lưu ý**: Đại lý không thể chỉnh sửa các quy tắc do nhà quảng cáo tạo. |
| <span id="access-rawdata-reports"></span>Truy cập các báo cáo dữ liệu thô | Đại lý có thể truy cập các báo cáo dữ liệu thô cho lưu lượng truy cập được phân bổ cho đại lý. Nhà quảng cáo không thể giới hạn các sự kiện mà đại lý có thể xem trong báo cáo. |
| <span id="access-protect360-dashboard-raw-data::dd9829fd"></span>Truy cập bảng điều khiển Protect360 & dữ liệu thô | Đại lý có thể:<ul><li>Truy cập bảng điều khiển Protect360 hợp nhất của bạn</li><li>Truy cập Protect360, Quy tắc xác thực và dữ liệu thô nếu nằm trong gói đăng ký</li></ul>**Lưu ý:** Đối với các nhà quảng cáo hợp tác với mạng quảng cáo thông qua đại lý, để cả mạng quảng cáo lẫn đại lý có thể truy cập dữ liệu, nhà quảng cáo phải tích hợp cả đại lý và mạng quảng cáo vào AppsFlyer và cấp quyền cho họ để truy cập dữ liệu. Nếu chỉ tích hợp và cấp quyền truy cập cho đại lý, mạng quảng cáo sẽ không truy cập được vào dữ liệu. |
| <span id="configure-inapp-event-postbacks::8743ba60"></span>Cấu hình đăng lại sự kiện trong ứng dụng | Đại lý có thể cấu hình các bài đăng lại sự kiện trong ứng dụng cho các sự kiện cụ thể mà bạn chọn:<ul><li>**Thêm sự kiện:** Từ menu thả xuống, hãy chọn các sự kiện mà bạn chấp thuận cấp quyền cho đại lý.</li></ul>Các tùy chọn sau áp dụng cho các sự kiện bạn đã chọn:<ul><li>**Gửi doanh thu sự kiện:** Khi được bật, đại lý có thể cấu hình việc gửi các sự kiện bao gồm cả giá trị tiền tệ của sự kiện.</li><li>**Tùy chọn gửi:**<ul><li>**Chỉ đối tác này:** Khi được chọn, đại lý có thể cấu hình chỉ gửi đăng lại cho các sự kiện được phân bổ cho lưu lượng truy cập do chính họ mang đến</li><li>**Tất cả các nguồn truyền thông, bao gồm cả các nguồn tự nhiên:** Khi được chọn, đại lý có thể cấu hình việc gửi các đăng lại đối với các sự kiện được phân bổ cho tất cả các nguồn truyền thông, đại lý và người dùng tự nhiên khác.</li></ul></li></ul> |

Tìm hiểu thêm về <Anchor target="_blank" href="/partners/vi/docs/about-agency-accounts#cơ-quan-truy-cập-vào-dữ-liệu-tiếp-thị">làm việc với các đại lý</Anchor>.

</Accordion>

<div id="test-the-integration" />

## Thử nghiệm tích hợp

Sau khi hoàn tất quá trình tích hợp đối tác và trước khi bạn bắt đầu chạy các chiến dịch với đối tác mới được thêm vào, quan trọng là bạn phải thử nghiệm tích hợp. Trong quá trình thiết lập rất có thể xảy ra sai lầm. Thử nghiệm trước giúp tránh rủi ro tiêu tốn nhiều tài nguyên chỉ rồi để phát hiện ra dữ liệu phân bổ của bạn bị thiếu hoặc không chính xác. 

<div id="note-4" />

> 📘 **Lưu ý**
>
> Trước khi thử nghiệm tích hợp, trước tiên hãy đảm bảo <Anchor target="_blank" href="/marketers/vi/docs/testing-the-sdk-integration-for-marketers">thử nghiệm ứng dụng về tích hợp SDK cơ bản,</Anchor> bao gồm cả lượt cài đặt tự nhiên và không tự nhiên.

<div id="test-the-attribution-link-for-nonsrns" />

<Accordion title="Kiểm tra đường dẫn phân bổ cho các mạng không phải SRN">

Các mạng quảng cáo không phải SRN, bao gồm 99,5% tất cả các mạng quảng cáo được tích hợp, sử dụng các đường dẫn phân bổ AppsFlyer. Tương tự, phân bổ truyền thông sở hữu được thực hiện bằng cách sử dụng các đường dẫn phân bổ tùy chỉnh AppsFlyer.

Vì việc phân bổ chính xác hay không phụ thuộc vào các thông số trên các đường dẫn phân bổ nên cần thử nghiệm các đường dẫn này trước khi bắt đầu chạy bất kỳ chiến dịch nào với mạng quảng cáo không phải SRN hoặc đường dẫn phân bổ tùy chỉnh.

**Để thử nghiệm đường dẫn phân bổ:**

1. Tạo một [đường dẫn phân bổ](/docs/set-up-an-integrated-partner#attribution-link-tab).
2. Gửi đường dẫn phân bổ mới đến thiết bị thử nghiệm <Anchor target="_blank" href="/marketers/vi/docs/registering-test-devices">đã đăng ký</Anchor> của bạn (qua email hoặc mã QR).
3. Nhấp vào liên kết, đảm bảo bạn được chuyển hướng đến cửa hàng ứng dụng.
4. Cài đặt ứng dụng.
5. Khởi chạy ứng dụng.
6. Kiểm tra xem lượt cài đặt có xuất hiện trên bảng điều khiển của AppsFlyer dưới tên nguồn truyền thông của đối tác hay không. Chờ tối đa 30 phút để lượt cài đặt xuất hiện trong bảng điều khiển.
7. Tìm kiếm cấp chiến dịch (bằng cách lựa chọn đối tác trong **Media Source Filter** (Bộ lọc nguồn phương tiện truyền thông) trên đầu trang tổng quan) để kiểm tra cài đặt xuất hiện dưới tên chiến dịch chính xác.
8. Nếu cần, tiếp tục đi sâu và kiểm tra bộ quảng cáo và các cấp quảng cáo đơn lẻ

</Accordion>

<div id="test-the-srn-integration" />

<Accordion title="Thử nghiệm tích hợp SRN">

SRN như quảng cáo Meta, Apple Search Ads và Google Ads không dựa vào các đường dẫn phân bổ bên ngoài cho các mục đích phân bổ. Thay vào đó, các SRN nhận được các truy vấn từ AppsFlyer, tự phân bổ và trả về câu trả lời. Do đó, việc thử nghiệm tích hợp riêng với hệ thống của mạng là không khả thi như với các mạng quảng cáo thông thường. Bạn phải thử nghiệm tích hợp riêng với từng SRN mà bạn hợp tác.

**Để thử nghiệm tích hợp SRN**:

1. Thực hiện thiết lập SRN đầy đủ trên AppsFlyer theo hướng dẫn thiết lập của đối tác cụ thể: <Anchor target="_blank" href="/marketers/vi/docs/meta-ads-integration-setup">quảng cáo Meta</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-integration-setup-for-advertisers">Google Ads</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/x-ads-formerly-twitter-ads-setup-guide-overview">Twitter</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/apple-ads-integration-setup">Apple Search Ads</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/snapchat-advanced-srn-integration-setup">Snapchat.</Anchor>
2. Chạy chiến dịch ngân sách thấp mới với đối tác SRN
3. Khi bảng điều khiển của đối tác hiển thị lượt cài đặt mới, hãy kiểm tra xem chúng có xuất hiện trên bảng điều khiển của AppsFlyer theo tên nguồn truyền thông của đối tác không.
4. Trong bảng điều khiển Tổng quan, hãy truy cập sâu đến cấp chiến dịch, bằng cách chọn đối tác trong **Media source filter**, để kiểm tra xem lượt cài đặt có xuất hiện dưới tên chiến dịch chính xác không. Chờ tối đa 30 phút để lượt cài đặt xuất hiện trong bảng điều khiển.
5. Nếu cần, tiếp tục truy cập sâu và kiểm tra bộ quảng cáo và các cấp quảng cáo đơn lẻ.

Nếu tất cả đều tốt, bạn có thể bắt đầu chạy các chiến dịch ngân sách lớn mới với đối tác. Chỉ cần thử nghiệm tích hợp một lần cho mỗi đối tác SRN là đủ. Có nghĩa là, không cần phải thử nghiệm cho từng chiến dịch.

</Accordion>

<div id="test-the-raw-data" />

<Accordion title="Thử nghiệm dữ liệu thô">

Nếu gói đăng ký của bạn với AppsFlyer bao gồm quyền truy cập vào dữ liệu thô, bạn nên thử nghiệm dữ liệu thô.

**Để thử nghiệm dữ liệu thô**:

1. Sau khi tiến hành thử nghiệm như đã đề cập trước đó,  hãy đi đến **Reports** (Báo cáo) > **<Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">Export Data</Anchor>** (Xuất Dữ liệu).
2. Chọn nguồn truyền thông đã thử nghiệm.
3. Cho phép tối đa 15 phút kể từ khi cài đặt và sau đó tải xuống Báo cáo lượt cài đặt.
4. Kiểm tra bản ghi lượt cài đặt từ đối tác hiện tại và bao gồm các thông số như nguồn truyền thông, tên chiến dịch, thời gian và loại tiếp xúc, ID thiết bị (nếu được áp dụng), tên đại lý (được gọi là "Đối tác" trong báo cáo), v.v.

<div id="important-2" />

> 🚧 **Quan trọng!**
>
> Một số mạng quảng cáo yêu cầu các hành động đặc biệt để cho phép thu thập dữ liệu thô cấp độ người dùng.
>
> Nếu bạn thấy lượt cài đặt mới trên bảng điều khiển nhưng không thấy trong dữ liệu thô, hãy tham khảo hướng dẫn cụ thể trong Trung tâm Trợ giúp dành cho mạng quảng cáo, ví dụ như <Anchor target="_blank" href="/marketers/vi/docs/x-ads-formerly-twitter-ads-faq-and-discrepancies#do-you-make-twitters-raw-data-available-to-agencies">Twitter</Anchor>.

</Accordion>

<div data-zendesk-anchors="overview=t%E1%BB%95ng-quan 01H80XGTBQ6MAK3VG0X6QMAYMP=t%E1%BB%95ng-quan 01H80XGTBQPPZV7WR5JBHQFB0B=partner-types-in-the-ecosystem 01H80XGTBQ4CPMBRVSMM7TD4VD=partners-in-the-marketplace invite-new-partners-to-appsflyer=m%E1%BB%9Di-c%C3%A1c-%C4%91%E1%BB%91i-t%C3%A1c-m%E1%BB%9Bi-v%C3%A0o-appsflyer 01H80XGTBQRJ78XCGNZBTJVYEQ=m%E1%BB%9Di-c%C3%A1c-%C4%91%E1%BB%91i-t%C3%A1c-m%E1%BB%9Bi-v%C3%A0o-appsflyer 01H80XGTBQ8VF6V9WARZRECWVR=your-integrated-partners 01H80XGTBQJQYD3R46H95WVVM0=l%C6%B0u-%C3%BD 01H80XGTBQ5BE24X219BVZBMDG=about-the-integrated-partner-page applicable-settings-tabs-per-partner-type=c%C3%A1c-tab-c%C3%A0i-%C4%91%E1%BA%B7t-%C3%A1p-d%E1%BB%A5ng-cho-m%E1%BB%97i-lo%E1%BA%A1i-%C4%91%E1%BB%91i-t%C3%A1c 01H80XGTBQPP74G38YNNYVXWP2=c%C3%A1c-tab-c%C3%A0i-%C4%91%E1%BA%B7t-%C3%A1p-d%E1%BB%A5ng-cho-m%E1%BB%97i-lo%E1%BA%A1i-%C4%91%E1%BB%91i-t%C3%A1c set-up-a-partner-nonsrn=thi%E1%BA%BFt-l%E1%BA%ADp-%C4%91%E1%BB%91i-t%C3%A1c-kh%C3%B4ng-ph%E1%BA%A3i-srn 01H80XGTBQXNQ7SFXZ5PBQGS1V=thi%E1%BA%BFt-l%E1%BA%ADp-%C4%91%E1%BB%91i-t%C3%A1c-kh%C3%B4ng-ph%E1%BA%A3i-srn 01H80XGTBQZXZARZCM61CMG0K3=l%C6%B0u-%C3%BD-1 01H80XGTBQB9T22GQ7CSHS2S1X=integration-tab integration-tab-sections=c%C3%A1c-ph%E1%BA%A7n-trong-integration 01H80XGTBQ0531M2RS3DH7E4Z0=c%C3%A1c-ph%E1%BA%A7n-trong-integration 01H80XGTBQ4MPGGKSZW0D9GG9H=l%C6%B0u-%C3%BD-2 01H80XGTBRT41FGP5107G96TWC=attribution-link-tab attribution-link-parameters=th%C3%B4ng-s%E1%BB%91-%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95 01H80XGTBRPENCTCRK8PPYSCGX=th%C3%B4ng-s%E1%BB%91-%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95 attribution-link-parameters::3874dfb8=th%C3%B4ng-s%E1%BB%91-%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95-1 01H80XGTBR8630SEV80K9RD6V9=th%C3%B4ng-s%E1%BB%91-%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95-1 retargeting-settings=thi%E1%BA%BFt-l%E1%BA%ADp-nh%E1%BA%AFm-l%E1%BA%A1i-m%E1%BB%A5c-ti%C3%AAu 01H80XGTBRT57QMPRENYSS81Z3=thi%E1%BA%BFt-l%E1%BA%ADp-nh%E1%BA%AFm-l%E1%BA%A1i-m%E1%BB%A5c-ti%C3%AAu clickthrough-attribution=ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-nh%E1%BA%A5p-qua 01H80XGTBREZTJ6B0Y08JCKN1E=ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-nh%E1%BA%A5p-qua viewthrough-attribution-lookback-window=c%E1%BB%ADa-s%E1%BB%95-xem-l%E1%BA%A1i-ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-xem-qua 01H80XGTBRXC1YYX4FW94NDR2Z=c%E1%BB%ADa-s%E1%BB%95-xem-l%E1%BA%A1i-ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-xem-qua 01H80XGTBRERTJ9XHGDV416T7V=cost-tab 01H80XGTBR54TQ0DNY1JR36GXN=l%C6%B0u-%C3%BD-3 enabling-cost-data-by-api=k%C3%ADch-ho%E1%BA%A1t-d%E1%BB%AF-li%E1%BB%87u-chi-ph%C3%AD-b%E1%BA%B1ng-api 01H80XGTBRV6BHWS76HWHK933M=k%C3%ADch-ho%E1%BA%A1t-d%E1%BB%AF-li%E1%BB%87u-chi-ph%C3%AD-b%E1%BA%B1ng-api cost-data-sync-status=tr%E1%BA%A1ng-th%C3%A1i-%C4%91%E1%BB%93ng-b%E1%BB%99-d%E1%BB%AF-li%E1%BB%87u-chi-ph%C3%AD 01H80XGTBRPWREFYFXA0A6VD47=tr%E1%BA%A1ng-th%C3%A1i-%C4%91%E1%BB%93ng-b%E1%BB%99-d%E1%BB%AF-li%E1%BB%87u-chi-ph%C3%AD 01H80XGTBRJ1AKX2Q7WPXFVA49=ad-revenue-tab enable-ad-revenue-attribution=cho-ph%C3%A9p-ph%C3%A2n-b%E1%BB%95-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o 01H80XGTBRHE9PPRA9X46M4TGZ=cho-ph%C3%A9p-ph%C3%A2n-b%E1%BB%95-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o ad-revenue-api-status-messages=th%C3%B4ng-b%C3%A1o-tr%E1%BA%A1ng-th%C3%A1i-api-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o 01H80XGTBRNT4K4ZNPKVV25ESJ=th%C3%B4ng-b%C3%A1o-tr%E1%BA%A1ng-th%C3%A1i-api-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o 01H80XGTBRGXS97JMG45QR4BEQ=permissions-tab ad-network-permissions=quy%E1%BB%81n-truy-c%E1%BA%ADp-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o 01H80XGTBRS9BTT2F8F95BCE9Z=quy%E1%BB%81n-truy-c%E1%BA%ADp-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o agency-permissions=c%E1%BA%A5p-quy%E1%BB%81n-cho-%C4%91%E1%BA%A1i-l%C3%BD 01H80XGTBRTVP407AAA77N090E=c%E1%BA%A5p-quy%E1%BB%81n-cho-%C4%91%E1%BA%A1i-l%C3%BD test-the-integration=th%E1%BB%AD-nghi%E1%BB%87m-t%C3%ADch-h%E1%BB%A3p 01H80XGTBSEWPHCPQF29XD6Y4W=th%E1%BB%AD-nghi%E1%BB%87m-t%C3%ADch-h%E1%BB%A3p 01H80XGTBSTHG2FC2M31F83RGK=l%C6%B0u-%C3%BD-4 01H80XGTBS4P06757QXHDKYAHT=test-the-attribution-link-for-nonsrns 01H80XGTBS2K9SPQ1MTAV7GP2H=test-the-srn-integration 01H80XGTBSTBV4RC3V279WNNB1=test-the-raw-data 01H80XGTBSN0VAX76XW9Y77T04=quan-tr%E1%BB%8Dng" />
