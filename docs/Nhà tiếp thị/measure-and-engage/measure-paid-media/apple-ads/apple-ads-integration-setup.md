---
title: Thiết lập tích hợp Apple Search Ads
metadata:
  keywords:
    - cost
    - Advertisers
    - apple search ads
    - asa
    - apple ads
    - apple search advanced
    - apple search ads campaign group
    - apple keywords
    - apple searchads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-08-31T09:04:38Z'
  edited_at: '2023-12-07T17:40:33Z'
  id: 213747963
  locale: vi
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/vi/articles/213747963
---
> **Khái quát:** Apple Search Ads (ASA), một đối tác SRN của AppsFlyer, hỗ trợ người dùng tìm ứng dụng của bạn trong App Store bằng cách sử dụng từ khóa.

<Image alt="apple_search_ads.png" src="https://support.appsflyer.com/hc/article_attachments/17210504660625" width="217px" />

Mức độ liên quan của ứng dụng xác định xem quảng cáo của bạn có phải là quảng cáo được hiển thị theo một truy vấn tìm kiếm trong Cửa hàng Ứng dụng hay không. Phản hồi của người dùng đối với một quảng cáo là một tín hiệu về mức độ liên quan của quảng cáo. ASA sử dụng phản hồi của người dùng làm tín hiệu để quyết định quảng cáo nào sẽ hiển thị nhiều nhất.

ASA cung cấp [phân bổ di động dựa trên lượt nhấp](/docs/apple-ads-integration-setup#asa-attribution), <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide">nhắm mục tiêu lại</Anchor> người dùng và dữ liệu <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview">chi phí</Anchor> thông qua API (với đăng ký ROI360).

<div id="set-up-apple-ads-integration" />

## Thiết lập tích hợp ASA

<div id="get-started" />

<Accordion title="Bắt đầu">

**Điều kiện tiên quyết**

* Phiên bản mới nhất của SDK iOS AppsFlyer được thông qua

**Thiết lập Apple Search Ads trong AppsFlyer:**

Quá trình thiết lập được thực hiện từ trang **Active Integrations**, nhưng để tìm đối tác mới, trước tiên bạn phải truy cập <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations">Partner Marketplace</Anchor>. Hoàn thành cấu hình bằng cách sử dụng các tab có liên quan, như được mô tả dưới đây.

> 📘 **Lưu ý**
>
> Trước khi thiết lập tích hợp, hãy nhớ <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations#liên-hệ-với-đối-tác">liên hệ với đối tác</Anchor> và mở tài khoản với họ.

**Để kích hoạt tích hợp:**

1. Trong AppsFlyer, ở mục **Configuration** đi đến **Partner Marketplace**.
2. Tìm kiếm và chọn đối tác. Bạn được chuyển hướng đến <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations#trang-đối-tác">trang chi tiết về đối tác</Anchor>.
3. Nhấp vào **Set up integration**. Bạn được chuyển đến trang thiết lập tích hợp.
4. Trong tab **Integration**, bật tùy chọn **Activate partner**.  
   **Lưu ý:** Nút bật/tắt phải luôn ở trạng thái bật (<Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">được kích hoạt</Anchor>) trong thời gian bạn làm việc với đối tác.
5. Hoàn thành cấu hình bằng cách sử dụng các tab có liên quan, như được mô tả bên dưới.

Tab tích hợp

</Accordion>

Apple Search Ads, một SRN, tích hợp với AppsFlyer thông qua API. Như vậy, không có các tùy chọn cài đặt đăng lại. Hoàn thành các mục sau theo mục tiêu phân bổ của bạn.

<table><thead><tr><th>Mục </th><th>Chi tiết</th></tr></thead><tbody><tr><td>Kích hoạt tích hợp</td><td><p><strong>Để kích hoạt tích hợp cho phân bổ:</strong></p><ol><li>Trong AppsFlyer, ở mục<span> </span><strong>Configuration</strong><span> </span>đi đến<span> </span><strong>Partner Marketplace</strong>. </li><li>Tìm kiếm và chọn đối tác. Bạn được chuyển hướng đến<span> </span><a href="./partner-integrations#trang-đối-tác" target="_blank">trang chi tiết về đối tác</a>.</li><li>Nhấp vào<span> </span><span></span><strong>Set up integration</strong>. Bạn được chuyển đến trang thiết lập tích hợp. </li><li>Trong tab <strong>Integration</strong>, bật tùy chọn <strong>Activate partner</strong>.<br/><strong>Lưu ý:</strong> Nút bật/tắt phải luôn ở trạng thái bật (<a href="./partner-activation-deactivation" target="_blank">được kích hoạt</a>) trong thời gian bạn làm việc với đối tác.</li><li>Hoàn thành cấu hình bằng cách sử dụng các tab có liên quan, như được mô tả bên dưới.</li></ol></td></tr><tr><td>Phân bổ lượt cài đặt</td><td><p><a href="./set-up-lookback-windows" target="_blank"><strong>Khung thời gian xem lại lượt nhấp cài đặt</strong></a></p><p>Đặt thời gian tối đa từ khi nhấp chuột đến khi cài đặt. Điều này sẽ cho phép AppsFlyer phân bổ lượt cài đặt (lần khởi chạy đầu tiên) diễn ra trong khung thời gian xem lại cho ASA.</p><p>Phạm vi: 1–30 ngày</p></td></tr><tr><td rowspan="2">Lượt cài đặt lại </td><td><p><strong>Phân bổ lượt cài đặt lại</strong></p><p>Nếu tùy chọn <strong>Phân bổ cài đặt lại</strong> bật, thì AppsFlyer có thể phân bổ lượt cài đặt lại cho ASA.</p><p>Tùy chọn cài đặt khung thời gian xem lại phân bổ lượt cài đặt lại được đặt theo tùy chọn phân bổ cài đặt.</p><p>Nếu người dùng đang trong <a href="./set-up-re-attribution-window" target="_blank">khung thời gian phân bổ lại</a> (được đặt tại thời điểm cài đặt ban đầu), thì lượt cài đặt được phân bổ cho ASA dưới dạng lượt cài đặt lại.</p><p>Có thể xem lượt cài đặt lại trong chế độ xem nhắm mục tiêu lại của bảng điều khiển Tổng quan.</p><p>Trường dữ liệu thô <strong>Store reinstall</strong> (Lưu trữ lượt cài đặt lại) được đặt thành true. </p><p>Hiện tại, tính năng nhắm mục tiêu lại ASA không hỗ trợ thu hút lại.</p></td></tr><tr><td><p><strong>Khung thời gian không hoạt động</strong></p><p>Đặt <a href="./set-retargeting-inactivity-window" target="_blank">ngưỡng không hoạt động</a> của người dùng (tính theo ngày) để kiểm soát tác động của các chiến dịch nhắm mục tiêu lại. </p></td></tr></tbody></table>


<div id="cost-tab" />

<Accordion title="Tab Chi phí">

Tích hợp chi phí cung cấp dữ liệu tổng hợp sau:

* Dữ liệu chi phí cho các chiến dịch, bộ quảng cáo, vùng địa lý/quốc gia và từ khóa của bạn. Xem <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">bảng tích hợp chi phí mạng quảng cáo</Anchor> để biết chi tiết đầy đủ về các phương diện, phép đo và tính năng được hỗ trợ.  
  **Lưu ý:** Dữ liệu chi phí yêu cầu phải có đăng ký ROI360.
* Dữ liệu về lượt chuột, lượt hiển thị và dữ liệu phong phú—từ khóa, tên chiến dịch và bộ quảng cáo.

> 📘 **Lưu ý**
>
> * Có hỗ trợ sử dụng nhiều tài khoản ASA. Nói cách khác, nếu bạn chạy các chiến dịch cho cùng một ứng dụng bằng các tài khoản ASA khác nhau, AppsFlyer có thể nhận dữ liệu này từ tất cả các tài khoản.
> * Dữ liệu chi phí cho "nhóm chiến dịch" không được API báo cáo ASA hỗ trợ và do đó, dữ liệu "nhóm chiến dịch" không có sẵn trong AppsFlyer.
> * Để đăng nhập bằng Apple, bạn cần có quyền cấp quản trị viên ASA (Tài khoản Chỉ đọc hoặc Tài khoản Đọc và Ghi).
> * Khi bạn đăng nhập bằng Apple, mọi chứng chỉ API được cung cấp trước đó sẽ ngừng lấy dữ liệu.
> * Khi bạn đăng nhập bằng Apple, quyền của các nhóm chiến dịch ASA sẽ không được tích lũy. Điều này có nghĩa là khi bạn tích hợp một ứng dụng mới, quyền cho các nhóm chiến dịch đã chọn cho ứng dụng trước đó sẽ bị thu hồi trừ khi được chọn lại.

**Để bật chi phí, lượt nhấp, lượt hiển thị và dữ liệu phong phú:**

* Thực hiện theo <Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">các hướng dẫn tích hợp này</Anchor>

<Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Xem trạng thái API chi phí của bạn</Anchor> và lần cuối cùng AppsFlyer lấy được dữ liệu chi phí phù hợp trong bảng điều khiển trạng thái tích hợp chi phí (và doanh thu quảng cáo) hoặc bảng điều khiển mạng quảng cáo cá nhân.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Tab quyền truy cập">

<Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#permissions-tab">Cài đặt quyền cho mạng quảng cáo và đại lý.</Anchor>

</Accordion>

<div id="set-up-agencies-and-apple-ads-marketing-partners" />

## Thiết lập đại lý và đối tác tiếp thị ASA

<div id="principles" />

<Accordion title="Nguyên tắc">

**Apple Search Ads: So sánh đối tác tiếp thị và Đại lý**

Các nhà quảng cáo và đại lý có thể chọn làm việc với Đối tác Tiếp thị ASA để báo cáo và tối ưu hóa các chiến dịch trên ASA.

Sự khác biệt giữa đại lý và đối tác tiếp thị được liệt kê trong bảng sau.

<div id="agency-vs-marketing-partner" />

#### So sánh đại lý và đối tác tiếp thị

|  | Đại lý | Đối tác tiếp thị |
| --- | --- | --- |
| AppsFlyer gửi đăng lại | Không | Có |
| Công nghệ | Chạy các chiến dịch thay cho bạn | Có giải pháp công nghệ giá trị gia tăng để tối ưu hóa các chiến dịch |

<div id="configuring-agencies-and-marketing-partners" />

#### Cấu hình đại lý và đối tác tiếp thị

Sử dụng danh sách kiểm tra sau để đảm bảo rằng bạn hoàn thành tất cả các bước trong quy trình định cấu hình. Hướng dẫn chi tiết được nêu rõ theo từng loại đối tác trong các mục tiếp theo.

<div id="configuration-steps-checklist" />

#### Danh sách kiểm tra các bước định cấu hình

| Được cấu hình bởi | Tích hợp với một đại lý | Tích hợp với đối tác tiếp thị |
| --- | --- | --- |
| Nhà quảng cáo | <ol><li>Trong AppsFlyer, ở tab integration ASA (tích hợp ASA), hãy bật **Activate partner** (Kích hoạt đối tác).</li><li>Chọn đại lý, trong tab Agency permissions (Quyền đại lý), hãy bật **Agency Permission** (Quyền đại lý).</li></ol> | <ol><li>Trong tab integration (tích hợp), bật tùy chọn **Activate partner** (Kích hoạt đối tác).</li><li>Trong bảng điều khiển ASA, lấy **ID Nhóm Chiến dịch** của đối tác tiếp thị.</li><li>Trong tab integration (tích hợp) của đối tác tiếp thị:<ol><li>Bật **Activate partner** (Kích hoạt đối tác).</li><li>Cài đặt Nhóm Chiến dịch.</li><li>Cấu hình đăng lại sự kiện trong ứng dụng.</li></ol></li></ol> |
| Đại lý | Trong tab integration (tích hợp) của ASA, hãy cài đặt **Apple Search Ads Campaign Group** (Nhóm Chiến dịch Apple Search Ads). | Không áp dụng |

</Accordion>

<div id="marketing-partner-setup" />

<Accordion title="Thiết lập đối tác tiếp thị">

**Để thiết lập đối tác tiếp thị:**

1. Nếu cần, hãy kích hoạt tính năng **tích hợp Apple Search Ads**:
   1. Trong AppsFlyer, đi đến **Configuration**> **Active integration partners** > **Apple Search Ads**.
   2. Bật **Activate Partner** (Kích hoạt Đối tác).
   3. Nhấp vào **Lưu**.
2. **Trong bảng điều khiển Apple Search Ads**: Nhận thông số ID Nhóm Chiến dịch Apple Search Ads liên quan đến đối tác tiếp thị. Sử dụng ảnh chụp màn hình sau đây làm hướng dẫn để xác định vị trí ID.

   ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)
3. **Trong AppsFlyer, hãy cấu hình đối tác tiếp thị ASA:**
   1. Trong AppsFlyer, đi đến **Configuration** > **Active integrations.**
   2. Tìm kiếm ***đối tác tiếp thị của* Apple Search Ads.**  
      Danh sách các đối tác tiếp thị sẽ hiển thị.
   3. Chọn đối tác tiếp thị.
   4. Bật **Activate partner** (Kích hoạt đối tác).
   5. Nhập **ID Nhóm Chiến dịch Apple Search Ads** của đối tác mà bạn đã truy xuất ở bước trước đó. Chỉ nhập các chữ số (số).
   6. Nhấp vào **Lưu**.
4. [Tùy chọn] Cấu hình đăng lại sự kiện trong ứng dụng:

   1. Bật tùy chọn **In-app events postback** (Đăng lại sự kiện trong ứng dụng).
   2. Nhấp vào **Add event** (Thêm sự kiện) để thêm một sự kiện SDK vào danh sách.
   3. Điền những tham số dưới đây:

      1. **Tên sự kiện SDK**: Tên sự kiện, như AppsFlyer nhận được từ SDK được tích hợp trong ứng dụng của bạn hoặc từ các sự kiện từ máy chủ đến máy chủ. **Mẹo:** Nếu không nhìn thấy sự kiện mong muốn trong danh sách, hãy đảm bảo bạn đã kích hoạt sự kiện trên thiết bị có cài đặt không tự nhiên và kiểm tra lại.
      2. **Gửi doanh thu:** Chọn một trong các tùy chọn sau: Không có giá trị và không có doanh thu, Giá trị và không có doanh thu hoặc Giá trị và doanh thu.
5. Nhấp vào **Save integration** (Lưu tích hợp).

</Accordion>

<div id="agency-setup" />

<Accordion title="Thiết lập đại lý">

Nhà quảng cáo cho phép các đại lý thay mặt họ chạy các chiến dịch bằng Apple Search Ads. Cả nhà quảng cáo và đại lý đều thực hiện các hành động thiết lập trong AppsFlyer như được mô tả trong mục này.

**Nhóm chiến dịch Apple Search Ads**

* Chiến dịch đại lý và chiến dịch của nhà quảng cáo phải là các nhóm chiến dịch ID Apple Search Ads riêng biệt.
* Không sử dụng ký tự đặc biệt và dấu cách cho tên nhóm.
* Khi bạn đăng nhập bằng Apple, quyền của các nhóm chiến dịch ASA sẽ không được tích lũy. Điều này có nghĩa là khi bạn tích hợp một ứng dụng mới, quyền cho các nhóm chiến dịch đã chọn cho ứng dụng trước đó sẽ bị thu hồi trừ khi được chọn lại. Bạn sẽ cần chọn **Quyền truy cập Hạn chế** và từng nhóm chiến dịch có liên quan (liên quan đến ứng dụng bạn muốn kết nối cho nhà quảng cáo).

<div id="advertiser-actions" />

#### **Hành động của nhà quảng cáo**

**Điều kiện tiên quyết**:

<Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#cấp-quyền-cho-đại-lý">Cấp quyền cho một đại lý</Anchor>.

**Để cho phép phân bổ Apple Search Ads, nhà quảng cáo:**

1. Trong AppsFlyer, đi đến **Configuration** > **Active integrations.**
2. Chọn **Apple Search Ads.**
3. Đi đến tab **Integration** (Tích hợp), bật **Activate partner** (Kích hoạt đối tác).
4. [Tùy chọn] Nếu bạn muốn phân bổ người dùng cài đặt lại ứng dụng trong khung thời gian phân bổ lại, hãy bật tùy chọn **Phân bổ lượt cài đặt lại.**
5. Nhấp vào **Lưu**.

<div id="agency-actions" />

#### **Hành động của đại lý**

1. **Trong bảng điều khiển Apple Search Ads**: Lấy ID Nhóm Chiến dịch của bạn. Sử dụng ảnh chụp màn hình sau đây làm hướng dẫn để xác định vị trí ID. Chỉ lấy các chữ số.

   ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)
2. Trong AppsFlyer, chọn một Ứng dụng.
3. Đi đến **Configuration** > **Active integrations**.
4. Chọn **Apple Search Ads.**
5. Nhập thông số **ID Chiến dịch Apple Search Ads.** Lưu ý! Nhập chữ số (chỉ số)
6. Nhấp vào **Save** (Lưu).

> 📘 **Lưu ý**
>
> Khi một đại lý làm việc với Đối tác Tiếp thị Apple Search Ads, đại lý đó phải cấu hình cùng ID nhóm chiến dịch trong cả trang cấu hình Apple Search Ads và trang cấu hình Đối tác Tiếp thị.

<div id="cost-clicks-and-impressions-data" />

### Dữ liệu Chi phí, Nhấp chuột và Hiển thị

Nếu bạn bật API chi phí, AppsFlyer sẽ nhận dữ liệu về chi phí, lượt nhấp và hiển thị từ ASA thông qua API. Xem <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">bảng tích hợp chi phí mạng quảng cáo</Anchor> để biết chi tiết đầy đủ về các phương diện, số liệu và tính năng được hỗ trợ. Lưu ý: Dữ liệu chi phí yêu cầu phải có đăng ký ROI360. Nếu không có ROI360 thì sẽ chỉ nhận dữ liệu lượt nhấp và lượt hiển thị.

**Để bật API chi phí**:

* Thực hiện theo <Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">các hướng dẫn tích hợp này</Anchor>. Đảm bảo rằng khi được nhắc đăng nhập vào tài khoản Apple Search Ads trong **Chọn quyền**, hãy chọn một trong các tùy chọn sau:
  * **Tài khoản Đọc và Ghi**
  * **Tài khoản Chỉ Đọc**  
    **Lưu ý**: Nếu bạn chọn Truy cập Giới hạn và một nhóm chiến dịch cụ thể, thì bạn có thể gặp phải lỗi dữ liệu.

<Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Xem trạng thái API chi phí của bạn</Anchor> và lần cuối cùng AppsFlyer lấy được dữ liệu chi phí phù hợp trong bảng điều khiển trạng thái tích hợp chi phí (và doanh thu quảng cáo) hoặc bảng điều khiển mạng quảng cáo riêng.

</Accordion>

<div id="disable-agencies-and-marketing-partners" />

<Accordion title="Tắt các đại lý và đối tác tiếp thị">

**Để ngừng ghi nhận lượt cài đặt Apple Search Ads do các đại lý hoặc đối tác tiếp thị tạo:**

1. Trong AppsFlyer, đi đến **Configuration** > **Active integrations.**
2. Chọn đại lý hoặc đối tác tiếp thị tùy từng trường hợp.
3. Xóa nội dung của **trường ID Nhóm Chiến dịch Apple Search Ads.**
4. Nhấp vào **Save integration** (Lưu tích hợp).

</Accordion>

<div id="additional-information" />

## Thông tin bổ sung

<div id="asa-attribution" />

<Accordion title="Phân bổ ASA">

Apple Search Ads hoạt động độc lập với SKAdNetwork và phân bổ xác định người dùng, bất kể có đồng ý ATT hay không. Điều này có nghĩa là đối với những người dùng được phân bổ cho ASA, bạn có đầy đủ các tính năng và kết quả đo lường được cung cấp bởi <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model">mô hình phân bổ LTV</Anchor> của chúng tôi.

Phân bổ ASA không dựa vào IDFA—phân bổ được thực hiện bằng cách sử dụng mã thông báo từ thiết bị (phân bổ xác định)—và khác nhau tùy theo quyết định đồng ý ATT:

| **Đồng ý ATT** | **Thời gian nhấp chuột có sẵn** | **Khung thời gian xem lại lượt nhấp** | **Nhận xét** |
| --- | --- | --- | --- |
| Có | Có | Do nhà quảng cáo thiết lập | Đã sử dụng các quy tắc phân bổ lượt nhấp cuối cùng của AppsFlyer |
| Không | Không | 30 ngày  <br />(do ASA đặt) | Không cung cấp thời gian nhấp chuột. Các ứng viên có tính tất định được ưu tiên |

</Accordion>

<div id="discrepancies" />

<Accordion title="Sự khác biệt">

AppsFlyer và Apple Search Ads sử dụng logic phân bổ khác nhau, dẫn đến sự khác biệt giữa các nền tảng. <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns#phân-bổ">Apple Search Ads</Anchor>, một SRN, báo cáo lượt cài đặt mới bằng API.

**Báo cáo Apple Search Ads cho AppsFlyer bằng API**

* Chiến dịch được hợp nhất theo Địa lý.
* Những thông tin sau không được báo cáo: Số lượt hiển thị, số lượt nhấp hoặc chi phí của vùng địa lý có ít hơn 100 lượt hiển thị đối với một chiến dịch nhất định.
* Khi nhóm theo Địa lý trong AppsFlyer, các khu vực Địa lý với dữ liệu không có sẵn sẽ không được hiển thị và tổng dữ liệu không có sẵn sẽ xuất hiện trong N/A (Không).

<div id="retargeting-related-discrepancies" />

### Các khác biệt liên quan đến nhắm mục tiêu lại

Cơ chế phân bổ nhắm mục tiêu lại AppsFlyer cho phép nhà quảng cáo đo lường và phân tích các chiến dịch nhắm mục tiêu lại, ngoài các chiến dịch thu hút người dùng.

Các số liệu sau đây minh họa sự khác biệt có thể xảy ra như thế nào liên quan đến các chiến dịch nhắm mục tiêu lại (bất kể cài đặt kiểm soát nhắm mục tiêu lại) chạy trên Apple Search Ads.

**Tính năng nhắm mục tiêu lại bật**

[![ASA_R_Enabled.png](https://files.readme.io/ced87f066490d95631f352ef7905c5c812ac7736c9763d08792eedb383afb8c7-360002911777.png)](https://files.readme.io/ced87f066490d95631f352ef7905c5c812ac7736c9763d08792eedb383afb8c7-360002911777.png)

**Tính năng nhắm mục tiêu lại tắt**

[![ASA_R_Disabled.png](https://files.readme.io/425a0e1e802482a00230d7ceaebdcaa7f74523fb6feb75d60168f94b56886201-31197514618001.png)](https://files.readme.io/425a0e1e802482a00230d7ceaebdcaa7f74523fb6feb75d60168f94b56886201-31197514618001.png)

<div id="additional-reasons-for-discrepancies" />

### Các lý do sai lệch khác

Bảng sau liệt kê các lý do chính dẫn đến sự khác biệt.

| Sai lệch | Apple Search Ads | AppsFlyer |
| --- | --- | --- |
| <span id="differences-related-to-appsflyer-sdk-versions"></span>Sự khác biệt liên quan đến các phiên bản SDK của AppsFlyer | Đếm lượt chuyển đổi bất kể là phiên bản SDK nào của AppsFlyer. | Đối với AdsServices, phải có SDK phiên bản từ V6.1.3 trở lên để phân bổ chính xác. |
| <span id="limit-ad-tracking-lat-and-att"></span>Giới hạn theo dõi quảng cáo (LAT) và ATT. | Luôn tính lượt chuyển đổi.<br /><br />Nếu chiến dịch của bạn bị giới hạn bằng độ tuổi và giới tính, người dùng LAT sẽ bị loại khỏi chiến dịch.<br /><br />Người dùng Apple dưới 18 tuổi sẽ luôn là LAT. | Lượt chuyển đổi LAT được phân bổ cho tự nhiên.<br /><br />Nếu AdServices được triển khai và iOS phiên bản từ 14.3 trở lên được cài đặt, thì người dùng không đồng ý sẽ được phân bổ chính xác. |
| <span id="counting-users"></span>Đếm số người dùng | Đếm người dùng dựa trên lượt tải xuống | Đếm người dùng dựa trên sự kiện mở ứng dụng lần đầu |
| <span id="reinstall-a-user-after-installing-the-app-deletes-it-clicks-on-a-search-ad-then-installs-the-app-again"></span>Cài đặt lại: Người dùng sau khi cài đặt ứng dụng, xóa ứng dụng, nhấp vào Quảng cáo Tìm kiếm, sau đó cài đặt lại ứng dụng | Được tính là một lượt chuyển đổi (lượt cài đặt) | <ul><li>Có IFDA: AppsFlyer xác định lượt cài đặt lại và không tính lượt đó cho các mục đích UA. Mẹo! Bật tùy chọn nhắm mục tiêu lại và lượt cài đặt lại được ghi nhận dưới dạng lượt cài đặt nhắm mục tiêu lại (hay còn gọi là phân bổ lại)</li><li>Không có IDFA: AppsFlyer có thể dựa vào IDFV để xác định xem đây là lượt cài đặt lại hay lượt cài đặt mới:<ol><li>Nếu một hoặc nhiều ứng dụng khác của nhà cung cấp được cài đặt trên thiết bị, AppsFlyer sẽ phân bổ ASA với phân bổ lại.</li><li>Nếu không (không có ứng dụng nào khác tồn tại), AppsFlyer sẽ phân bổ ASA với lượt cài đặt mới.</li></ol></li></ul> |
| <span id="click-lookback-window"></span>Khung thời gian xem lại lượt nhấp | Khung thời gian 30 ngày cố định | Đối với các phản hồi từ AdServices không có thời gian nhấp chuột, khung thời gian xem lại lượt nhấp được cố định thành khung thời gian 30 ngày. |
| <span id="winning-click"></span>Giành được lượt nhấp | Luôn phân bổ cho bản thân nếu người dùng đã tương tác và tải xuống ứng dụng. | Có khả năng hiển thị trên nhiều mạng và phân bổ theo phương pháp lượt nhấp cuối cùng |
| <span id="install-time"></span>Thời gian cài đặt | Thời gian tải xuống ứng dụng | Mở ứng dụng lần đầu |
| <span id="time-zone"></span>Múi giờ | Múi giờ địa phương của cửa hàng ứng dụng | Múi giờ UTC hoặc như được đặt trong cài đặt AppsFlyer |
| <span id="conversion-data"></span>Dữ liệu chuyển đổi | Có thể mất hơn 5 giây để cập nhật AppsFlyer rằng Quảng cáo Tìm kiếm mang đến lượt cài đặt đó | Phân bổ trong vòng 5 giây tại thời điểm API dữ liệu chuyển đổi phản hồi. Nếu không nhận được dữ liệu nào thì phản hồi là tự nhiên. |
| <span id="cost-data"></span>Dữ liệu chi phí | Báo cáo chi phí cho tất cả các từ khóa | Không báo cáo dữ liệu chi phí cho các từ khóa có chứa chữ hoa trong bảng điều khiển nhóm người hoặc API nhóm người. |
| <span id="geo-locations"></span>Vị trí địa lý | Apple Search Ads cho phép các nhà quảng cáo nhắm mục tiêu người dùng theo quốc gia và khu vực của họ. Apple Search Ads hỗ trợ số lượng [**quốc gia**](https://searchads.Apple.com/storefronts/) hạn chế. | AppsFlyer nhận diện được vị trí địa lý chính xác của người dùng dựa trên địa chỉ IP và do đó, các báo cáo về địa lý không có sẵn trên Apple Search Ads.<br /><br />Mẹo! Người dùng cài đặt khi đang ở quốc gia thực tế của cửa hàng ứng dụng có cùng dữ liệu địa lý trên AppsFlyer và Apple Search Ads |

</Accordion>

<div id="tips" />

<Accordion title="Lời khuyên">

Làm việc với Apple Search Ads cho phép bạn thu thập dữ liệu tiếp thị có giá trị, điều này có thể ảnh hưởng đến nỗ lực thu hút người dùng của bạn với tất cả các nguồn truyền thông dành cho ứng dụng iOS của bạn.

Mẹo để giúp bạn tối đa hóa lợi ích của việc sử dụng Apple Search Ads:

| Mách nhỏ | Chi tiết |
| --- | --- |
| <span id="get-keyword-data"></span>Lấy dữ liệu từ khóa | Apple Search Ads chia sẻ dữ liệu từ khóa với AppsFlyer. Bạn có thể xem dữ liệu từ khóa trong dữ liệu thô và các công cụ phân tích như Bảng pivot, Giữ chân người dùng và Nhóm người.<br /><br />**Lưu ý:**<ul><li>Việc nhận dữ liệu từ khóa có thể bị trì hoãn trong 8-12 giờ và trong một số trường hợp, có thể chỉ bao gồm ID từ khóa mà không có cụm từ khóa đó</li><li>Để có được dữ liệu từ khóa, nút bật/tắt Chi phí phải ở trạng thái bật. Dữ liệu từ khóa được cung cấp như một phần của [Tích hợp chi phí](/docs/apple-ads-integration-setup#cost-tab) mà không cần đăng ký ROI360.</li></ul>Nếu dữ liệu từ khóa trong AppsFlyer bị thiếu, điều này có thể do:<ul><li>**Loại gói:** Dữ liệu từ khóa được Apple Search Ads chia sẻ với các nhà quảng cáo, có gói Apple Search Ads [nâng cao](https://searchads.Apple.com/advanced/).</li><li>**Loại chiến dịch:** Bạn có thể cấu hình các loại so khớp từ khóa chiến dịch khác nhau trong Apple Search Ads. Dựa trên loại so khớp, Apple Search Ads chia sẻ các từ khóa như sau:<ul><li>**Khớp chính xác**: Các từ khóa chính xác mà người dùng tìm kiếm</li><li>**Khớp mở rộng**: Các từ khóa Apple sử dụng để thực hiện tìm kiếm. Các từ khóa này tương tự như các thuật ngữ tìm kiếm thực tế của người dùng.</li><li>**Khớp tìm kiếm**: Apple **không** chia sẻ các từ khóa này với các nhà quảng cáo.</li></ul></li><li>**Phân biệt chữ hoa chữ thường**: API tiếp thị Apple Search Ads trả về dữ liệu phân biệt chữ hoa chữ thường và API phân bổ Apple Search Ads trả về dữ liệu chữ thường. Để tránh xung đột dữ liệu trong báo cáo, chỉ sử dụng các từ khóa viết thường.</li></ul>Chiến dịch tìm kiểm **Chỉ sử dụng khớp chính xác hoặc khớp mở rộng** để nhận dữ liệu từ khóa hoàn chỉnh. |
| <span id="compare-the-quality-of-users-based-on-keyword-data"></span>So sánh chất lượng người dùng dựa trên dữ liệu từ khóa | Không phải tất cả các từ khóa đều tương đương, có nghĩa là trong khi các từ khóa khác nhau có thể có cùng chi phí nhưng chất lượng người dùng thu hút được có thể khác nhau. Sử dụng báo cáo Giữ chân người dùng hoặc <Anchor target="_blank" href="/marketers/vi/docs/pivot-table-user-metrics">Pivot</Anchor> để xác định các từ khóa tối đa hóa ROI của bạn. |
| <span id="analyze-keyword-cost"></span>Phân tích chi phí từ khóa | Nền tảng chứa dữ liệu chi phí từ khóa hợp nhất khi các chiến dịch từ khóa ASA được cấu hình dưới dạng [khớp chính xác hoặc khớp mở rộng](/docs/apple-ads-integration-setup#get-keyword-data). Dữ liệu chi phí từ khóa có các đặc điểm sau:<ul><li>Dữ liệu lịch sử có sẵn bắt đầu từ ngày 13 tháng 10 năm 2019.</li><li>Phương diện:<ul><li>Ngày</li><li>Chiến dịch</li><li>Bộ quảng cáo</li></ul></li><li>Công cụ phân tích:<ul><li><Anchor target="_blank" href="/marketers/vi/docs/cohort-and-retention-dashboard">Nhóm người</Anchor></li><li><Anchor target="_blank" href="/marketers/vi/docs/pivot-table-user-metrics">Bảng tổng hợp</Anchor></li><li><Anchor target="_blank" href="/marketers/vi/docs/master-api-user-acquisition-metrics-via-api">API Chính</Anchor></li></ul></li></ul>**Điểm hạn chế**<ul><li>Chỉ sử dụng các phương diện được ghi chú để lọc và nhóm các cụm từ tìm kiếm về dữ liệu chi phí. Ví dụ: không lọc hoặc nhóm sử dụng Địa lý.</li></ul>**<span id="cohort-example"></span>Ví dụ về Nhóm người**<br />Ví dụ sau hiển thị cách thiết lập Nhóm người để xem thông tin chi phí và ROI.<br /><br />**Thiết lập Nhóm người**<br /><br />[<Image alt="CohortRequest.png" src="https://files.readme.io/73004ab25cfff029786ec4601e22a0ac4b02a146141787b51bda1a02d5412330-31197524095377.png" width="327px" />](https://files.readme.io/73004ab25cfff029786ec4601e22a0ac4b02a146141787b51bda1a02d5412330-31197524095377.png)<br /><br />**Bảng kết quả Nhóm người**<br /><br />Trong bảng sau, tổng chi phí và ROI Nhóm người được hiển thị<br /><br />[<Image alt="CohortTable.png" src="https://files.readme.io/ebceedb82207bdbc7f58daafc0557630ac35a73a11b14d207a7283b93294073d-31197514633233.png" width="429px" />](https://files.readme.io/ebceedb82207bdbc7f58daafc0557630ac35a73a11b14d207a7283b93294073d-31197514633233.png)<br /><br />**<span id="pivot-example"></span>Ví dụ về Pivot**<br /><br />**Thiết lập Pivot**<br /><br />[<Image alt="Pivot_define.png" src="https://files.readme.io/29ad177a5ef681f8358968092005d8ba871f3dd06661a8dea6d186318c08a476-31197524107153.png" width="413px" />](https://files.readme.io/29ad177a5ef681f8358968092005d8ba871f3dd06661a8dea6d186318c08a476-31197524107153.png)<br /><br />**Bảng kết quả Pivot**<br /><br />[<Image alt="Pivot.png" src="https://files.readme.io/ef9766de2059d0608e8ae6dc063053f2926ffa296e7eca2e13a1bc4171921d2c-31197524111505.png" width="439px" />](https://files.readme.io/ef9766de2059d0608e8ae6dc063053f2926ffa296e7eca2e13a1bc4171921d2c-31197524111505.png) |
| <span id="find-the-best-performing-creative-set"></span>Tìm bộ nội dung sáng tạo có hiệu suất tốt nhất | ![creative_sets.png](https://files.readme.io/ef8e38d67121283742dcbd1faef11d94a8ea1c612dc258611e72cbf826d7ef8f-31197524112785.png)<br /><br />Một phương pháp thực hành tốt là kiểm tra cách khách hàng tiềm năng phản ứng với các bộ nội dung sáng tạo khác nhau mà bạn sử dụng. Các bộ nội dung sáng tạo có hiệu suất tốt nhất sẽ có tỷ lệ chuyển đổi cao nhất. Ngoài ra, các bộ nội dung sáng tạo tốt nhất sẽ chuyển đổi người dùng với mức độ tương tác cao hơn.<br /><br />Điều này tác động đến tất cả các khách hàng tiềm năng trên iOS của bạn, không chỉ các khách hàng tiềm năng ASA, vì tất cả họ đều tiếp cận trang ứng dụng của bạn trong cửa hàng ứng dụng. Tuy nhiên, với lượt cài đặt ASA, AppsFlyer cho thấy ID bộ nội dung sáng tạo trong thông số **ID Quảng cáo** của <Anchor target="_blank" href="/marketers/vi/docs/raw-data-field-dictionary">dữ liệu thô</Anchor>, cho phép bạn so sánh hiệu suất của các bộ nội dung sáng tạo khác nhau. |
| <span id="target-redownloaders"></span>Nhắm mục tiêu vào những người tải lại | Người dùng trước đây của bạn có thể là đối tượng tốt nhất để bạn nhắm mục tiêu sử dụng ASA.<br /><br />Một người dùng, người này đã gỡ cài đặt ứng dụng của bạn rồi cài đặt lại do chiến dịch nhắm mục tiêu lại ASA của bạn, được ASA gọi là Người Tải lại. Nếu lượt cài đặt lại được thực hiện trong <Anchor target="_blank" href="/marketers/vi/docs/set-up-re-attribution-window">khung thời gian phân bổ lại</Anchor>, AppsFlyer gọi đây là Phân bổ lại. Trong tất cả các trường hợp khác, đây được coi là một lượt cài đặt mới.<br /><br />![ASACGroupID.png](https://files.readme.io/ebdc380f2abc3e9a3b134cd258d90ae32f75b3ee4d9eadde39adbc728daae523-31197514645265.png) |

</Accordion>

<div id="asa-change-log" />

<Accordion title="Nhật ký thay đổi ASA">

| Ngày có hiệu lực | Cập nhật/thay đổi |
| --- | --- |
| <span id="20230207"></span>07-02-2023 | Thông số phân bổ phong phú `Tên chiến dịch`, `Tên bộ quảng cáo` và `Từ khóa` chỉ khả dụng khi tab Cost được bật, bất kể gói đăng ký của bạn là gì.  <br />**Điều này có nghĩa là để bảng điều khiển và báo cáo dữ liệu thô hiển thị tên chiến dịch, tên bộ quảng cáo hoặc từ khóa, bạn phải bật tab Cost.** |
| <span id="20220216"></span>Ngày 16 tháng o2 năm 2022 | Từ khóa có sẵn thông qua API Chi phí. Bạn phải bật API này trong trang tích hợp của Apple Search Ads. Lưu ý! Tất cả các nhà quảng cáo đều có thể sử dụng API này không phân biệt gói đăng ký của bạn. |
| <span id="20210407"></span>Ngày 07 tháng 04 năm 2021 | Tích hợp Apple Search Ads: ASA hoạt động độc lập với SKAdNetwork và phân bổ người dùng theo cách có thể xác định. Điều này có nghĩa là đối với những người dùng được phân bổ cho ASA, bạn có đầy đủ các tính năng và kết quả đo lường được cung cấp bởi <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model">mô hình phân bổ LTV.</Anchor> |
| <span id="20210307"></span>Ngày 07 tháng 03 năm 2021 | Apple Search Ads sẽ ra mắt API Quản lý Chiến dịch V4.0. API liên quan đến chi phí và các dữ liệu khác liên quan đến chiến dịch. API không tác động đến việc phân bổ. Chúng tôi đang trong quá trình đưa API cập nhật vào sử dụng. Bạn không cần thực hiện bất kỳ hành động nào. |
| <span id="20210215"></span>Ngày 15 tháng 02 năm 2021 | Kể từ hôm nay, có thể điền vào các trường tên chiến dịch và tên bộ quảng cáo nếu bạn bật [API Chi phí](/docs/apple-ads-integration-setup#cost-tab) ASA. Tất cả các nhà quảng cáo đều có thể sử dụng API này không phân biệt gói đăng ký. |

</Accordion>

<div id="availability-of-apple-search-ads-campaign-parameters" />

<Accordion title="Tính khả dụng của các thông số chiến dịch Apple Search Ads">

Bảng bên dưới hiển thị tính khả dụng của các thông số phân bổ trong báo cáo dữ liệu thô hoặc trên bảng điều khiển.

| Thông số báo cáo dữ liệu thô | Tính khả dụng |
| --- | --- |
| Tên chiến dịch | Để thông số này khả dụng, bạn phải bật API [Chi phí](/docs/apple-ads-integration-setup#cost-tab) trên trang tích hợp Apple Search Ads. Tất cả các nhà quảng cáo đều có thể sử dụng API này không phân biệt gói đăng ký |
| ID Chiến dịch | Luôn khả dụng |
| Tên bộ quảng cáo | Để thông số này khả dụng, bạn phải bật API [Chi phí](/docs/apple-ads-integration-setup#cost-tab) trên trang tích hợp Apple Search Ads. Tất cả các nhà quảng cáo đều có thể sử dụng API này không phân biệt gói đăng ký |
| ID Bộ quảng cáo | Luôn khả dụng |
| Quảng cáo | Hiện không khả dụng |
| ID Quảng cáo | Thông số này chỉ khả dụng khi cả hai điều kiện sau được đáp ứng:<ul><li>Người dùng sử dụng iOS phiên bản 15.2 trở đi</li><li>Quảng cáo sử dụng <Anchor target="_blank" href="https://developer.apple.com/app-store/product-page/">Trang Sản phẩm Tùy chỉnh</Anchor> cho các chiến dịch liên kết với một trong các vị trí đặt quảng cáo sau:<ul><li>`Tab Ngày hôm nay`</li><li>`Kết quả tìm kiếm`</li></ul></li></ul> |
| Từ khóa | Để thông số này khả dụng, bạn phải bật API [Chi phí](/docs/apple-ads-integration-setup#cost-tab) trên trang tích hợp Apple Search Ads. Tất cả các nhà quảng cáo đều có thể sử dụng API này không phân biệt gói đăng ký |
| ID từ khóa | Thông số này khả dụng qua báo cáo dữ liệu thô. Tuy nhiên, trường này phải được chọn rõ ràng trong Data Locker, API Push và Dữ liệu xuất. Trong trường hợp của API Pull, thêm `keyword_id` vào thông số  `&additional_fields` <Anchor target="_blank" href="/marketers/vi/docs/pull-api-raw-data#additional-fields">của lệnh gọi API Pull</Anchor>. |
| Loại so khớp từ khóa | Hiện không khả dụng |

</Accordion>

<div id="impact-of-aggregated-advanced-privacy" />

<Accordion title="Tác động của Quyền riêng tư Nâng cao Hợp nhất">

Bắt đầu từ iOS 14 [ATTrackingManager](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/) (ATT) điều chỉnh tính khả dụng của IDFA và dữ liệu phân bổ cấp người dùng về lượt cài đặt do ASA mang lại được ASA kiểm soát. Do đó, tính khả dụng của dữ liệu cấp người dùng của các lượt cài đặt do ASA mang lại không bị ảnh hưởng bởi <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">Aggregated Advanced Privacy</Anchor>.

Lưu ý! Các lượt cài đặt do ASA mang lại không được báo cáo trong khung SKAdNetwork.

| **Đồng ý ATT** | **Thời gian nhấp chuột có sẵn** | **Khung thời gian xem lại lượt nhấp** | **Nhận xét** | **Tính khả dụng của dữ liệu** | **IDFA có sẵn** |
| --- | --- | --- | --- | --- | --- |
| Đồng ý | Có | Do nhà quảng cáo thiết lập | Đã sử dụng các quy tắc phân bổ lượt nhấp cuối cùng của AppsFlyer | Dữ liệu phân bổ cấp người dùng | Có |
| Không đồng ý | Không | 30 ngày  <br />(do ASA đặt) | Các ứng viên tất định được ưu tiên. | Dữ liệu phân bổ cấp người dùng không có thời gian nhấp chuột. | Không |

</Accordion>

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">Khuôn khổ Aggregated Advanced Privacy</Anchor>
> * <Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows">Giải thích về khung thời gian xem lại</Anchor>

<div data-zendesk-anchors="set-up-asa-integration=thi%E1%BA%BFt-l%E1%BA%ADp-t%C3%ADch-h%E1%BB%A3p-asa h_01HDPCGMP2CY4B37VM3AT2P114=thi%E1%BA%BFt-l%E1%BA%ADp-t%C3%ADch-h%E1%BB%A3p-asa h_01HDPCGMP35S325269JETX1EJW=get-started h_01HDPCGMP383Y223E1YXF60C8S=l%C6%B0u-%C3%BD h_01HDPCGMP3JC93JWHM2SM8EVZA=cost-tab h_01HDPCGMP3XGYXVZZJ8SGDK3G2=l%C6%B0u-%C3%BD-1 h_01HDPCGMP3KXMKSHN0GFD6MAFG=permissions-tab set-up-agencies-and-asa-marketing-partners=thi%E1%BA%BFt-l%E1%BA%ADp-%C4%91%E1%BA%A1i-l%C3%BD-v%C3%A0-%C4%91%E1%BB%91i-t%C3%A1c-ti%E1%BA%BFp-th%E1%BB%8B-asa h_01HDPCGMP3D96BG496G7H97YWP=thi%E1%BA%BFt-l%E1%BA%ADp-%C4%91%E1%BA%A1i-l%C3%BD-v%C3%A0-%C4%91%E1%BB%91i-t%C3%A1c-ti%E1%BA%BFp-th%E1%BB%8B-asa h_01HDPCGMP3EBHM0CQXKP05SG9F=principles agency-vs-marketing-partner=so-s%C3%A1nh-%C4%91%E1%BA%A1i-l%C3%BD-v%C3%A0-%C4%91%E1%BB%91i-t%C3%A1c-ti%E1%BA%BFp-th%E1%BB%8B h_01HDPCGMP3YGJEA942DF2YC9P1=so-s%C3%A1nh-%C4%91%E1%BA%A1i-l%C3%BD-v%C3%A0-%C4%91%E1%BB%91i-t%C3%A1c-ti%E1%BA%BFp-th%E1%BB%8B configuring-agencies-and-marketing-partners=c%E1%BA%A5u-h%C3%ACnh-%C4%91%E1%BA%A1i-l%C3%BD-v%C3%A0-%C4%91%E1%BB%91i-t%C3%A1c-ti%E1%BA%BFp-th%E1%BB%8B h_01HDPCGMP3NQQ76SC32SEC8TS4=c%E1%BA%A5u-h%C3%ACnh-%C4%91%E1%BA%A1i-l%C3%BD-v%C3%A0-%C4%91%E1%BB%91i-t%C3%A1c-ti%E1%BA%BFp-th%E1%BB%8B configuration-steps-checklist=danh-s%C3%A1ch-ki%E1%BB%83m-tra-c%C3%A1c-b%C6%B0%E1%BB%9Bc-%C4%91%E1%BB%8Bnh-c%E1%BA%A5u-h%C3%ACnh h_01HDPCGMP39HE117X4MP25M77W=danh-s%C3%A1ch-ki%E1%BB%83m-tra-c%C3%A1c-b%C6%B0%E1%BB%9Bc-%C4%91%E1%BB%8Bnh-c%E1%BA%A5u-h%C3%ACnh h_01HDPCGMP3BT4YJWJ2G8X76NSE=marketing-partner-setup h_01HDPCGMP3X6B4RYF289WY49P7=agency-setup advertiser-actions=h%C3%A0nh-%C4%91%E1%BB%99ng-c%E1%BB%A7a-nh%C3%A0-qu%E1%BA%A3ng-c%C3%A1o h_01HDPCGMP3S3PHHH3F6KZE3SEV=h%C3%A0nh-%C4%91%E1%BB%99ng-c%E1%BB%A7a-nh%C3%A0-qu%E1%BA%A3ng-c%C3%A1o agency-actions=h%C3%A0nh-%C4%91%E1%BB%99ng-c%E1%BB%A7a-%C4%91%E1%BA%A1i-l%C3%BD h_01HDPCGMP3MK61YRMCQA2KA5X2=h%C3%A0nh-%C4%91%E1%BB%99ng-c%E1%BB%A7a-%C4%91%E1%BA%A1i-l%C3%BD h_01HDPCGMP3E7PZB8FDG4XN79JA=l%C6%B0u-%C3%BD-2 cost-clicks-and-impressions-data=d%E1%BB%AF-li%E1%BB%87u-chi-ph%C3%AD-nh%E1%BA%A5p-chu%E1%BB%99t-v%C3%A0-hi%E1%BB%83n-th%E1%BB%8B h_01HDPCGMP3AVYYK2X03RF057FN=d%E1%BB%AF-li%E1%BB%87u-chi-ph%C3%AD-nh%E1%BA%A5p-chu%E1%BB%99t-v%C3%A0-hi%E1%BB%83n-th%E1%BB%8B h_01HDPCGMP3113BYD1GPJM7XBQH=disable-agencies-and-marketing-partners additional-information=th%C3%B4ng-tin-b%E1%BB%95-sung h_01HDPCGMP3BXVASH2YJ9G8AS2C=th%C3%B4ng-tin-b%E1%BB%95-sung h_01HDPCGMP31QFVN1SWBCABJ65K=asa-attribution h_01HDPCGMP4DCKH898AEWAY6N01=discrepancies retargeting-related-discrepancies=c%C3%A1c-kh%C3%A1c-bi%E1%BB%87t-li%C3%AAn-quan-%C4%91%E1%BA%BFn-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i h_01HDPCGMP4Z9M3QR6QGRR7A8BM=c%C3%A1c-kh%C3%A1c-bi%E1%BB%87t-li%C3%AAn-quan-%C4%91%E1%BA%BFn-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i additional-reasons-for-discrepancies=c%C3%A1c-l%C3%BD-do-sai-l%E1%BB%87ch-kh%C3%A1c h_01HDPCGMP4QJ3HYEP7EAYMHRQQ=c%C3%A1c-l%C3%BD-do-sai-l%E1%BB%87ch-kh%C3%A1c h_01HDPCGMP4A8NAD8SYD191YJYR=tips h_01HDPCGMP4HNS84AVWH7J8H7YA=c%C3%A1c-l%C3%BD-do-sai-l%E1%BB%87ch-kh%C3%A1c h_01HDPCGMP4MF9FBP4WDRHVZ4BR=cohort-example h_01HDPCGMP4EFMZ4FHZ8WBWW9R2=pivot-example h_01HDPCGMP4XKB75F6R7DDWDHPB=asa-change-log h_01HDPCGMP40MW37BFT8A096PNG=availability-of-apple-search-ads-campaign-parameters h_01HDPCGMP48M04SDA4FGYW6XNQ=impact-of-aggregated-advanced-privacy h_01HDPD3C1T4ZXXZ2RE0GSXPZP3=xem-th%C3%AAm" />
