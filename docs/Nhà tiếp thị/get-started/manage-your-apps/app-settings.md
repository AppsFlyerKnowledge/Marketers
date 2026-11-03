---
title: 'Cài đặt Ứng dụng  '
metadata:
  keywords:
    - App Settings
    - Advertisers
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
    - Platform essentials
    - Agencies
    - pm-guy-riesenberg
  created_at: '2016-08-16T07:50:37Z'
  edited_at: '2023-11-01T10:21:49Z'
  id: 211719806
  locale: vi
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/vi/articles/211719806
---
> **Khái quát:** Tìm hiểu về các tùy chọn cài đặt ảnh hưởng đến phân bổ và phân tích ứng dụng của bạn trên tất cả các nguồn truyền thông.

## Cài đặt Ứng dụng

**Quyền truy cập:**

* Quản trị viên (hoặc người dùng khác có quyền thích hợp) có thể **thay đổi** cài đặt của ứng dụng.
* Tất cả người dùng tài khoản có quyền truy cập vào một ứng dụng cụ thể đều có thể **xem** cài đặt của ứng dụng đó.

**Cách thay đổi hoặc xem cài đặt của ứng dụng:**

1. Trong AppsFlyer, đi tới **Configuration** (Cấu hình) > **App Settings** (Cài đặt của Ứng dụng).
2. Xem phần cài đặt và thực hiện thay đổi nếu cần trong trang Cài đặt của Ứng dụng.
3. Nhấp vào **Save settings** (Lưu cài đặt).

### Cài đặt ứng dụng chung

<Table>
  <thead>
    <tr>
      <th>
        Cài đặt
      </th>
      <th>
        Mô tả
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="sdk-authentication-dev-key"></span>
        Xác thực SDK: Dev key
      </td>
      <td>
        * Dev key xác thực các sự kiện do ứng dụng hoặc S2S gửi đến AppsFlyer.
        * Mã khóa này là duy nhất cho mỗi tài khoản và được tất cả các ứng dụng trong tài khoản sử dụng.
        * Khóa có sẵn trên trang App Settings cho bất kỳ người dùng tài khoản nào có quyền truy cập vào ứng dụng đó.
        * [Tùy chọn] Một khóa ứng dụng riêng có thể được phân bổ trong các tình huống nhất định. Liên hệ với CSM của bạn để thảo luận về điều này.
      </td>
    </tr>
    <tr>
      <td><span id="aggregated-advanced-privacy-ios-apps"></span>
        Quyền riêng tư Nâng cao Hợp nhất (ứng dụng iOS)
      </td>
      <td>
        Khi được bật, dữ liệu phân bổ cấp người dùng sẽ không có sẵn cho nhà quảng cáo. Các bài đăng lại và dữ liệu sự kiện đã chia sẻ với các đối tác được hợp nhất và ẩn danh (tìm hiểu thêm về khung <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">Quyền riêng tư nâng cao hợp nhất</Anchor>).

        Khi tắt tính năng này, dữ liệu phân bổ cấp người dùng sẽ có sẵn cho tất cả đối tác dưới dạng dữ liệu hợp nhất và có thể được đặt riêng cho từng đối tác.
      </td>
    </tr>
    <tr>
      <td><span id="analytics-define-loyal-user-trigger"></span>
        Phân tích: Xác định yếu tố kích hoạt người dùng trung thành
      </td>
      <td>
        * Trình kích hoạt để chỉ định người dùng làm người dùng trung thành. Tùy chọn mặc định được đặt khi bạn thêm ứng dụng là 3 lượt mở ứng dụng.
        * Sau khi phân bổ các sự kiện trong ứng dụng, bạn có thể sử dụng sự kiện trong ứng dụng làm sự kiện kích hoạt.
          * [Mặc định] 3 ứng dụng sẽ mở ra.
          * Cài đặt người dùng trung thành có tính biểu thị cho chất lượng người dùng. Cân nhắc sử dụng <Anchor target="_blank" href="/marketers/vi/docs/protect360-anti-fraud-guide#faq">Protect360</Anchor> để chống gian lận.
          * Thay đổi cài đặt này tác động đến dữ liệu ngược trở lại, nghĩa là dữ liệu người dùng trung thành trong lịch sử được tính toán lại.
      </td>
    </tr>
    <tr>
      <td><span id="app-store-country"></span>
        Quốc gia của cửa hàng ứng dụng
      </td>
      <td>
        Đặt quốc gia của cửa hàng ứng dụng nơi ứng dụng khả dụng. Cài đặt này tác động đến ứng dụng như được nêu chi tiết ở đây.

        * **Thay đổi trạng thái ứng dụng từ chờ xử lý sang hoạt động**:
          * <Anchor target="_blank" href="/marketers/vi/docs/why-is-my-app-still-pending">Khi ứng dụng hoạt động</Anchor>, AppsFlyer sẽ kiểm tra cửa hàng bằng cách sử dụng cài đặt quốc gia để truy xuất thông tin chi tiết về ứng dụng như biểu tượng của ứng dụng.
          * Nếu không tìm thấy ứng dụng trong cửa hàng của quốc gia đã đặt, AppsFlyer không thể thay đổi trạng thái ứng dụng từ trạng thái chờ xử lý sang hoạt động.
        * Hành vi chuyển hướng bị ảnh hưởng bởi cài đặt tùy thuộc vào tình huống, như được nêu chi tiết trong bảng sau.

        | Kiểu người dùng | Tình huống chuyển hướng |
        | --- | --- |
        | <span id="mobile"></span>Di động | Người dùng thường nhấp vào đường dẫn phân bổ trong các ứng dụng di động khác. Khi nhấp vào, hệ điều hành sẽ xác định quốc gia của cửa hàng ứng dụng mà người dùng được chuyển hướng đến:  <br /><br />* **Android** chuyển hướng dựa trên IP/vị trí của người dùng.<br />* **iOS** chuyển hướng đến cửa hàng ứng dụng được liên kết với tài khoản iTunes đang hoạt động trên thiết bị. |
        | <span id="mobile-and-web"></span>Di động và web | Khi người dùng web nhấp vào đường dẫn phân bổ, trong **các trang web** (thiết bị di động và máy tính để bàn), chuyển hướng ban đầu là đến cửa hàng được thiết lập tại quốc gia có cửa hàng trong ứng dụng.<br /><br />Khi thử cài đặt, hệ điều hành sẽ chuyển hướng chúng đến cửa hàng của quốc gia như được mô tả dành cho di động ở hàng trước. |
        | <span id="ipad-ios-13"></span>iPad iOS 13 | Bắt đầu từ iOS 13, <Anchor target="_blank" href="https://www.apple.com/ipados/features/">iPad phục vụ phiên bản máy tính của các trang web</Anchor>. Điều này có nghĩa là kiểu người dùng (di động hoặc web) không có liên quan. Một lượt nhấp vào đường dẫn phân bổ sẽ đi đến trang web dành cho máy tính và sau đó, quy tắc chuyển hướng là quy tắc của người dùng web. |
      </td>
    </tr>
    <tr>
      <td><span id="localization-time-zone"></span>
        Bản địa hóa: Múi Giờ
      </td>
      <td>
        Tùy chọn cài đặt ứng dụng mặc định là UTC. <Anchor target="_blank" href="/marketers/vi/docs/changing-app-time-zone-settings">Giới thiệu về múi giờ của ứng dụng.</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="localization-currency"></span>
        Bản địa hóa: Tiền tệ
      </td>
      <td>
        Cài đặt ứng dụng mặc định là USD.

        * Chức năng thay đổi tiền tệ có sẵn cho các ứng dụng không có doanh thu hoặc chi phí.
        * Đối với các ứng dụng mới, tiền tệ được đặt khi ứng dụng được thêm vào.

        #### Công cụ báo cáo bị ảnh hưởng bởi tiền tệ của ứng dụng

        | Công cụ báo cáo | Tùy chọn tiền tệ khả dụng |
        | --- | --- |
        | <span id="dashboards"></span>Bảng điều khiển | Tiền tệ dành riêng cho ứng dụng |
        | <span id="export-data-page"></span>Trang dữ liệu xuất | Tiền tệ dành riêng cho ứng dụng |
        | <span id="push-api"></span>API Push | Loại tiền tệ cụ thể theo ứng dụng và USD đồng thời có sẵn |
        | <span id="pull-api"></span>API Pull | Dữ liệu hợp nhất: Đơn vị tiền tệ cụ thể theo ứng dụng<br /><br />Dữ liệu thô: USD có thể lựa chọn hoặc loại tiền tệ cụ thể theo ứng dụng |
        | <span id="master-api"></span>API chính | USD có thể lựa chọn hoặc loại tiền tệ cụ thể theo ứng dụng |
        | <span id="data-locker"></span>Hộp khóa dữ liệu | Chỉ USD |
      </td>
    </tr>
  </tbody>
</Table>

### Cài đặt phân bổ

| Cài đặt | Mô tả |
| --- | --- |
| <span id="reattribution-window"></span>Cửa sổ Phân bổ lại | <Anchor target="_blank" href="/marketers/vi/docs/set-up-re-attribution-window">Thời gian phân bổ lại</Anchor> là khoảng thời gian bắt đầu từ ngày cài đặt đầu tiên, trong đó lượt cài đặt lại không thể được phân bổ là lượt cài đặt mới.<ul><li>[Mặc định] Ba tháng</li><li>Phạm vi giá trị: 1-24 tháng</li></ul> |
| <span id="viewthrough-attribution-via-probabilistic-modeling"></span>Phân bổ lượt xem hết thông qua mô hình xác suất | <ul><li>[Phương pháp tốt nhất] Bật mô hình xác suất xem hết ngoài phân bổ lượt nhấp qua luôn ở chế độ bật.</li><li>Sau khi bật mô hình xác suất xem hết, bạn cũng phải bật phân bổ lượt xem hết trong tab tích hợp mạng quảng cáo.</li></ul> |
| <span id="reengagement-attribution"></span>Phân bổ thu hút lại | Bài viết liên quan: <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide">Hướng dẫn nhắm mục tiêu lại</Anchor><br /><br />**Cách bật tính năng phân bổ thu hút lại:**<ul><li>Đi đến **Settings** > **App settings**, bật **Re-engagement attribution**.</li></ul>Ngoài cài đặt của ứng dụng, bạn cũng phải <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide#retargeting-settings">thực hiện cài đặt cho mỗi đối tác</Anchor>.<br /><br />Tùy chọn cài đặt **<Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide#khung-thời-gian-loại-trừ">Minimum time between re-engagement conversions</Anchor>** (Thời gian tối thiểu giữa chuyển đổi thu hút lại) được sử dụng để ngăn việc kết thúc khung thời gian thu hút lại hiện có trước thời lượng đã đặt. |
| <span id="organic-search-seo-mobile-app-attribution"></span>Organic search (SEO) mobile app attribution | Bài đọc liên quan: <Anchor target="_blank" href="/marketers/vi/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">Phân bổ tìm kiếm tự nhiên</Anchor><br /><br />**Cách bật phân bổ tìm kiếm tự nhiên:**<ul><li>Đi đến **Settings** > **App settings**, bật **Organic search (SEO) mobile app attribution**.</li></ul> |
| <span id="uninstall-measurement"></span>Đo lường lượt Gỡ cài đặt | Đo lường lượt gỡ cài đặt liên quan đến lượt cài đặt xảy ra khi bật tính năng đo lường lượt gỡ cài đặt.<br /><br />**Để bật tùy chọn đo lường lượt gỡ cài đặt:**<ol><li>Hoàn thành theo hệ điều hành như sau:<ul><li>**iOS**: Các ứng dụng triển khai tính năng phân bổ lượt gỡ cài đặt iOS cần tải lên chứng chỉ P12 tại đây.</li><li>**Android**: Các ứng dụng yêu cầu Mã khóa Máy chủ Firebase/GCM được xác định tại đây đối với phân bổ lượt gỡ cài đặt Android.</li></ul></li><li>Bật tùy chọn **Uninstall measurement** (Đo lường lượt gỡ cài đặt).</li><li>Nhấp vào **Save settings** (Lưu cài đặt)</li></ol>**Để dừng đo lường lượt gỡ cài đặt:**<ol><li>Tắt tùy chọn **Uninstall measurement** (Đo lường lượt gỡ cài đặt).</li><li>Nhấp vào **Save settings** (Lưu cài đặt).</li></ol> |

### Cài đặt nâng cao

| Cài đặt | Mô tả |
| --- | --- |
| <span id="mask-ip-address-in-raw-data-reports"></span>Địa chỉ IP ẩn | Sau khi bật, <Anchor target="_blank" href="/marketers/vi/docs/apply-ip-masking-to-user-data">địa chỉ IP của thiết bị người dùng cuối sẽ bị ẩn</Anchor> trong các báo cáo dữ liệu thô và trong đăng lại được gửi đến đối tác từ ứng dụng hiện được chọn. |
| <span id="reinstall-detection-using-ondevice-storage-ios-only"></span>Reinstall detection using on-device storage (iOS only) | Phát hiện các lượt cài đặt lại mà không phụ thuộc vào ID quảng cáo. Điều này được thực hiện bằng cách lưu trữ ngày cài đặt ứng dụng cuối cùng trên bộ lưu trữ cục bộ an toàn trong thiết bị (trong iOS là Keychain). Việc xác định xem một lượt cài đặt là cài đặt lại hay cài đặt mới cho phép bạn loại bỏ các lượt cài đặt lại trùng lặp khỏi NOI, hỗ trợ phân tích phân bổ chính xác hơn. |
| <span id="ios-103-redirect-fallback"></span>Dự phòng chuyển hướng iOS 10.3 | [Không còn được hỗ trợ] Đối với iOS 10.3+. Chúng tôi đã đơn giản hóa quy trình cho người dùng iOS và thông số này không còn được sử dụng nữa. <Anchor target="_blank" href="/marketers/vi/docs/uri-scheme-fallback-for-ios">Chuyển hướng iOS</Anchor>.<br /><br />Tùy chọn này chỉ có sẵn cho các ứng dụng iOS. |
| <span id="change-app-name"></span>Thay đổi Tên Ứng dụng | <ul><li>Tên của ứng dụng, tên này sau đó sẽ được hiển thị trên bảng điều khiển và báo cáo dữ liệu. Điều này rất hữu ích nếu bạn có các phiên bản khác nhau của cùng một ứng dụng, ví dụ vì lý do phân phối khu vực.</li><li>Thay đổi này tác động đến việc hiển thị ứng dụng. ID ứng dụng, được sử dụng để xác định ứng dụng khi sử dụng các API AppsFlyer khác nhau, **vẫn giữ nguyên**.</li><li>Tên giới hạn chỉ 50 ký tự.</li></ul> |
| <span id="outofstore-app-url"></span>URL ứng dụng ngoài cửa hàng | <ul><li>Đặt URL tải xuống ứng dụng được sử dụng để điền các đường dẫn phân bổ.</li><li>Cài đặt này không làm thay đổi các đường dẫn phân bổ đã tạo trước đó.</li></ul>**Giới hạn**: Tùy chọn hoàn toàn không hiển thị nếu bạn không đặt URL khi thêm ứng dụng. Trong trường hợp này, hãy yêu cầu CSM của bạn hoặc liên hệ với [hello@appsflyer.com](mailto:hello@Appsflyer.com) để đặt URL cho bạn.<br /><br />Tùy chọn này chỉ có sẵn cho các ứng dụng Android. |

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide">Hướng dẫn phân bổ nhắm mục tiêu lại</Anchor>
> * <Anchor target="_blank" href="/marketers/vi/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">Thuộc tính tìm kiếm tự nhiên</Anchor>

<div data-zendesk-anchors="app-settings=c%C3%A0i-%C4%91%E1%BA%B7t-%E1%BB%A9ng-d%E1%BB%A5ng 01ECHQME56X51MDW9TMA6DBNCK=c%C3%A0i-%C4%91%E1%BA%B7t-%E1%BB%A9ng-d%E1%BB%A5ng general-app-settings=c%C3%A0i-%C4%91%E1%BA%B7t-%E1%BB%A9ng-d%E1%BB%A5ng-chung h_01HAVS8CVPQKSDKCEM3YHHJ99Y=c%C3%A0i-%C4%91%E1%BA%B7t-%E1%BB%A9ng-d%E1%BB%A5ng-chung reporting-tools-impacted-by-app-currency=c%C3%B4ng-c%E1%BB%A5-b%C3%A1o-c%C3%A1o-b%E1%BB%8B-%E1%BA%A3nh-h%C6%B0%E1%BB%9Fng-b%E1%BB%9Fi-ti%E1%BB%81n-t%E1%BB%87-c%E1%BB%A7a-%E1%BB%A9ng-d%E1%BB%A5ng h_01HAVS8CVQESWAQXKDW5SNVHCJ=c%C3%B4ng-c%E1%BB%A5-b%C3%A1o-c%C3%A1o-b%E1%BB%8B-%E1%BA%A3nh-h%C6%B0%E1%BB%9Fng-b%E1%BB%9Fi-ti%E1%BB%81n-t%E1%BB%87-c%E1%BB%A7a-%E1%BB%A9ng-d%E1%BB%A5ng attribution-settings=c%C3%A0i-%C4%91%E1%BA%B7t-ph%C3%A2n-b%E1%BB%95 h_01HAVS8CVQN1YYTT7S49VGB3J0=c%C3%A0i-%C4%91%E1%BA%B7t-ph%C3%A2n-b%E1%BB%95 advanced-settings=c%C3%A0i-%C4%91%E1%BA%B7t-n%C3%A2ng-cao h_01HAVS8CVQTKXVXSMT5KNYZ3T4=c%C3%A0i-%C4%91%E1%BA%B7t-n%C3%A2ng-cao h_01HDPCC9465DR4A3CCXYQC2M56=xem-th%C3%AAm" />
