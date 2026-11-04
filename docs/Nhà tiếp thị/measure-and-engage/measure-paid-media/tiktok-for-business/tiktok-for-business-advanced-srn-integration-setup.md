---
title: 'TikTok For Business—thiết lập tích hợp SRN Nâng cao '
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-06-09T16:49:57Z'
  edited_at: '2023-12-27T14:41:42Z'
  id: 6722785184913
  locale: vi
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/vi/articles/6722785184913
---
> **Khái quát:** TikTok For Business (tiktokglobal\_int), là Mạng Tự Báo cáo (<Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns">SRN</Anchor>) nâng cao cho phép cho chủ sở hữu ứng dụng đo lường phân bổ trên thiết bị di động dựa trên lượt nhấp và lượt xem với AppsFlyer.

> 📘 **Lưu ý**
>
> Vào ngày 30 tháng 1 năm 2023, tích hợp mới **TikTok for Business—SRN Nâng cao** `tiktokglobal_int` đã được thêm vào, trong khi tích hợp trên nền tảng **TikTok for Business [Cũ]** `bytedanceglobal_int` đang giảm dần hoạt động và sẽ ngừng hẳn kể từ tháng 3 năm 2024. Quá trình chuyển đổi này do TikTok xử lý và thông báo cho bạn thời điểm có thể xóa tích hợp cũ. **Để tránh mất dữ liệu, hãy đảm bảo duy trì cả hai tích hợp ở trạng thái hoạt động trong giai đoạn chuyển đổi**. Tìm hiểu thêm trong <Anchor target="_blank" href="/marketers/vi/docs/bulletin-tiktok-for-business-advanced-srn">bản tin</Anchor>.

<Image alt="TikTok_logo__2_.png" src="https://files.readme.io/3a081755b08fcf19b60ff178506a083449890cb900821f7f1e4b7ef85426dd45-11844735832081.png" width="193px" />

<div id="overview" />

## Tổng quan

Tích hợp SRN Nâng cao có nghĩa là tất cả lưu lượng truy cập <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-knowledge-base-glossary?query=glossar#dual-consent">được chấp thuận kép</Anchor> được phân bổ và báo cáo là lưu lượng truy cập SRN thông thường. Đối với lưu lượng truy cập không được chấp thuận, AppsFlyer có thể phân bổ và đo lường lượng phân bổ dựa trên số lượt nhấp và lượt hiển thị từ TikTok, tuân thủ các quy định hạn chế về quyền riêng tư. Tính năng tích hợp hỗ trợ phân bổ lượt nhấp và lượt hiển thị, chi phí, doanh thu quảng cáo và đối tượng.

## Kích hoạt đối tác

**Điều kiện tiên quyết:** Trước khi thiết lập tích hợp, hãy nhớ <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations#liên-hệ-với-đối-tác">liên hệ với đối tác</Anchor> và mở tài khoản với họ.

Quá trình thiết lập được thực hiện từ trang **Active Integrations**, nhưng để tìm đối tác mới, trước tiên bạn phải truy cập <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations">Partner Marketplace</Anchor>.

**Để kích hoạt chức năng tích hợp đối tác:**

1. Trong AppsFlyer, ở mục **Configuration** đi đến **Partner Marketplace**.
2. Tìm kiếm **TikTok For Business** và chọn.
3. Nhấp vào **Set up integration**. Bạn được chuyển đến trang thiết lập tích hợp.
4. Trong thẻ **Integration,** bật **Activate partner**.  
   **Lưu ý:** Nút bật/tắt phải luôn bật (<Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">được kích hoạt</Anchor>) trong thời gian bạn làm việc với đối tác<Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">.</Anchor>
5. Nhấp vào **Save Integration**.
6. Hoàn thành cấu hình bằng cách sử dụng các thẻ có liên quan, như được mô tả ở phần tiếp theo.

<div id="set-up-tiktok-for-business" />

## Thiết lập TikTok for Business

Cửa sổ cấu hình bao gồm các thẻ sau: Integration, Attribution link, Cost, Ad revenue và Permissions. Thẻ **Attribution link** không khả dụng đối với TikTok for Business, các thẻ còn lại là tùy chọn.

> 📘 **Lưu ý**
>
> * Một số tùy chọn cài đặt sẽ khác nhau giữa các thiết bị iOS và Android
> * Khi thiết lập chiến dịch, tên chiến dịch không được bắt đầu hoặc kết thúc bằng khoảng trắng, vì điều này có thể gây ra sự khác biệt trong trang tổng quan và báo cáo. Tìm hiểu thêm về <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=9535">cách thiết lập chiến dịch trên TikTok</Anchor>
> * Quảng cáo đến từ <Anchor target="_blank" href="https://www.tiktok.com/business/en/blog/introducing-tiktok-search-ads-toggle">TikTok Search Ads Toggle</Anchor> được đưa vào tất cả các thuộc tính của TikTok. AppsFlyer không nhận dữ liệu về các cụm từ tìm kiếm hoặc từ khóa cụ thể.

<div id="integration-tab" />

<Accordion title="Thẻ Integration">

Thẻ **Integration** bao gồm một số phần, như được mô tả bên dưới.

<div id="activate-partner" />

#### Kích hoạt đối tác

Để cấu hình tích hợp, trước tiên bạn phải [bật](#kích-hoạt-đối-tác) nút bật/tắt **Activate partner**. Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation#activating-a-partner">kích hoạt và hủy kích hoạt tích hợp</Anchor> đối tác.

<div id="advanced-data-sharing" />

#### Quyền riêng tư Nâng cao

Chỉ dành cho ứng dụng iOS: Bạn có thể chia sẻ quyền kiểm soát dữ liệu với đối tác qua các postback và <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions">báo cáo</Anchor>, tùy vào trạng thái bật/tắt của tính năng **<Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">Bảo mật Nâng cao</Anchor> (dành cho iOS phiên bản 14.5 trở lên)**:

| Quyền riêng tư Nâng cao: Bật | Quyền riêng tư Nâng cao: Tắt |
| --- | --- |
| Chỉ gửi các bài đăng lại về những sự kiện được phân bổ cho đối tác | Gửi các bài đăng lại theo cấu hình của bạn:<ul><li>**Tất cả các nguồn truyền thông, bao gồm nguồn tự nhiên**</li><li>**Chỉ đối tác này**</li></ul> |
| Gửi các bài đăng lại theo <Anchor target="_blank" href="/partners/vi/docs/advanced-privacy-guide-postback-macros-for-ad-networks">biểu mẫu Quyền riêng tư Nâng cao</Anchor> |  |
| <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">Dữ liệu hợp nhất và ẩn danh</Anchor> được chia sẻ với đối tác, đồng nghĩa với việc không chia sẻ dữ liệu ở cấp người dùng (ID thiết bị). |  |

> 📘 **Lưu ý**
>
> * Khi kích hoạt chức năng tích hợp (`tiktokglobal_int`), nút chuyển đổi **Advanced Privacy** được bật theo mặc định.
> * Khi di chuyển từ tích hợp cũ (`bytedanceglobal_int`) và kích hoạt tích hợp mới (`tiktokglobal_int`), nút chuyển đổi **Advanced Privacy** được bật theo mặc định, bất kể trạng thái trước khi di chuyển.
> * Theo TikTok for Business, giữ nút **on** chuyển đổi **Advanced Privacy** có thể dẫn đến các sự kiện chiến dịch không được báo cáo đầy đủ và hạn chế cải thiện hiệu suất chiến dịch trong tương lai trên TikTok

<div id="general-settings" />

#### Cài đặt chung

**ID Ứng dụng TikTok**

Một mã duy nhất được tạo trong Trình quản lý Quảng cáo TikTok và được TikTok sử dụng để xác nhận quyền sở hữu của nhà quảng cáo đối với ứng dụng của họ. Dù không bắt buộc nhưng bạn nên nhập ID ứng dụng cho từng ứng dụng của mình. Điều này giúp bạn kiểm soát tốt hơn dữ liệu của mình trên TikTok for Business và mở khóa các sản phẩm bổ sung.

**Cách thêm ID ứng dụng:**

1. [Tùy chọn] Nhập <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10001060">ID Ứng dụng TikTok</Anchor> của bạn, có sẵn tại bảng điều khiển Quảng cáo TikTok.
2. [Tùy chọn] Cách thêm nhiều ID ứng dụng:
   1. Sau khi nhập ID ứng dụng đầu tiên, hãy nhấn enter.
   2. Nhập ID Ứng dụng TikTok tiếp theo của bạn.

> 📘 **Lưu ý**
>
> * Cấu hình ID Ứng dụng TikTok không ảnh hưởng đến dữ liệu của bạn trong AppsFlyer
> * Khi di chuyển sang tích hợp mới (`tiktokglobal_int`), mọi giá trị từ tích hợp cũ (`bytedanceglobal_int`) đều được tự động nhập vào trường này.
> * <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10001070">Tìm hiểu thêm về yêu cầu ID Ứng dụng TikTok đối với iOS 14</Anchor>

<div id="default-postbacks" />

#### Các bài đăng lại mặc định

**Phần này chỉ liên quan đến** **lưu lượng truy cập không được chấp thuận**. Lưu lượng truy cập được chấp thuận sẽ được gửi trực tiếp đến TikTok for Business qua <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns?query=about%20srn">chế độ SRN</Anchor>.

Cấu hình cách gửi các bài đăng lại cho **lượt cài đặt**, **lượt cài đặt bị từ chối** và **lượt thu hút lại**, xảy ra trước khi khởi chạy ứng dụng:

* **This partner only** [Mặc định]: Chỉ gửi các bài đăng lại khi sự kiện được phân bổ cho đối tác này—nghĩa là người dùng thực hiện sự kiện đến từ đối tác này.
* **All media sources including organic**: Gửi các bài đăng lại về những sự kiện được phân bổ cho bất kỳ đối tác nào và cho những sự kiện tự nhiên—nghĩa là khi người dùng thực hiện sự kiện đến từ bất cứ nguồn truyền thông nào. TikTok for Business đề xuất thay đổi lựa chọn thành **All media sources including organic** để tối ưu hóa tốt hơn

> 📘 **Lưu ý**
>
> * Chỉ dành cho ứng dụng iOS: Quyền kiểm soát dữ liệu của bạn được chia sẻ với đối tác thông qua các bài đăng lại và <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions">báo cáo</Anchor> tùy thuộc vào trạng thái chuyển đổi **Quyền riêng tư Nâng cao (dành cho iOS 14.5+ trở lên)**.
> * Khi di chuyển từ tích hợp cũ (`bytedanceglobal_int`) và kích hoạt tích hợp mới (`tiktokglobal_int`), trạng thái mặc định của cài đặt bài đăng lại là **This partner only**, bất kể trạng thái trước khi di chuyển.

<div id="install-attribution" />

#### Phân bổ lượt cài đặt

Đặt phân bổ lượt nhấp qua và lượt xem hết cho lượt cài đặt (lần khởi chạy đầu tiên). Lưu ý rằng chỉ có thể phân bổ các lượt cài đặt trong khung thời gian xem lại đến TikTok for Business.

1. Đặt **Install click-through lookback window** thành 1-23 giờ hoặc 1-30 ngày.  
   **Lưu ý:** Theo TikTok for Business, bạn nên điều chỉnh phù hợp với họ bằng cách đặt khung thời gian xem lại lượt nhấp qua thành 7 ngày.
2. [Tùy chọn] Bật **Install view-through attribution** và đặt **Install view-through attribution window** trong khoảng thời gian từ 1 đến 23 giờ.  
   **Lưu ý:** Theo TikTok for Business, bạn nên điều chỉnh phù hợp với họ bằng cách đặt khung thời gian xem lại lượt nhấp qua thành 1 ngày.

> 📘 **Lưu ý**
>
> * TikTok for Business đang sử dụng các biện pháp bảo mật dữ liệu nâng cao để bảo vệ những người sử dụng dịch vụ của họ. Bắt đầu từ ngày 23 tháng 10 năm 2021, TikTok for Business sẽ cung cấp cho các nhà quảng cáo dữ liệu phân bổ lượt xem giới hạn ở cấp thiết bị. Đối với các nguồn cấp người dùng, chẳng hạn như báo cáo dữ liệu thô, thông báo API Push, báo cáo API Pull, trang Dữ liệu xuất và Khóa Dữ liệu, chỉ các trường sau sẽ được điền:
>
> * * Nguồn truyền thông (bytedanceglobal\_int)
>   * Kênh
>   * Loại tương tác được phân bổ (lượt hiển thị)
>   * Thời gian tương tác được phân bổ (chỉ được báo cáo dưới dạng ngày - "dd/mm/yyyy")
>   * Chiến dịch được báo cáo là "bị hạn chế"
>     Dữ liệu này không có sẵn trong GCD. Báo cáo dữ liệu tổng hợp tiếp tục hiển thị các chuyển đổi lượt xem qua.
> * Khi di chuyển từ tích hợp cũ (`bytedanceglobal_int`) và kích hoạt tích hợp mới (`tiktokglobal_int`), cài đặt cửa sổ xem lại (lượt nhấp qua và lượt xem qua) được đặt về **các giá trị mặc định**, bất kể trạng thái trước khi di chuyển. Bạn có thể cập nhật các cài đặt này.

<div id="re-engagement-attribution" />

#### Phân bổ thu hút lại

Đặt khung thời gian thu hút lại, bao gồm phân bổ lượt nhấp qua và lượt xem hết:

1. [Tùy chọn] Bật **Re-engagement attribution**, sau đó đặt **Re-engagement click-through lookback window**.
2. [Tùy chọn] Bật **Re-engagement view-through attribution**, sau đó đặt **Re-engagement view-through lookback window**.
3. [Tùy chọn] Đặt **Re-engagement window**.

> 🚧 **Quan trọng!**
>
> Khi di chuyển từ tích hợp cũ (`bytedanceglobal_int`) và kích hoạt tích hợp mới (`tiktokglobal_int`), nút chuyển đổi **Re-engagement** được **tắt theo mặc định**, bất kể trạng thái trước khi di chuyển. Nếu tích hợp cũ của bạn có <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide">chiến dịch nhắm mục tiêu lại</Anchor>, **để đảm bảo tính liên tục, hãy nhớ** **bật tính năng này** trong tích hợp mới.

Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide#reengagement-rules-and-windows">quy tắc và khung thời gian</Anchor> thu hút lại.

<div id="in-app-event-postbacks" />

#### Đăng lại sự kiện trong ứng dụng

**Phần này chỉ liên quan đến lưu lượng truy cập không được chấp thuận.** Lưu lượng truy cập được chấp thuận sẽ được gửi trực tiếp đến TikTok for Business qua <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns?query=about%20srn">chế độ SRN</Anchor>.

Cấu hình ánh xạ các sự kiện trong ứng dụng với các sự kiện của TikTok for Business, được gửi qua các bài đăng lại:

1. Bật tùy chọn **In-app event postbacks**.
2. Nhấp vào **Add event** để thêm một SDK hoặc sự kiện máy chủ đến máy chủ vào danh sách. Bảng sau đây mô tả các trường cần hoàn thành:  

| Tên thông số | Mô tả |
| --- | --- |
| **Sự kiện AppsFlyer** | Tên của sự kiện mà AppsFlyer nhận được từ SDK sẽ được tích hợp vào ứng dụng của bạn hoặc từ các sự kiện máy chủ đến máy chủ.<br />**Mẹo**: Bạn không thấy sự kiện đang tìm kiếm?<ul><li>Hãy đảm bảo kích hoạt sự kiện trên thiết bị có lượt cài đặt không tự nhiên và kiểm tra lại.</li><li>Nhập vào **Sự kiện AppsFlyer**, sau đó nhấp vào **Create custom**. Đọc thêm về <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#sự-kiện-tùy-chỉnh">cách ánh xạ sự kiện tùy chỉnh.</Anchor></li></ul> |
| **mapped to partner event** | Tên hoặc ID duy nhất của từng sự kiện được xác định ở phía đối tác. Các cấu hình ánh xạ có thể có là:<ul><li>**Text field:** Nhận ID sự kiện tương ứng từ đối tác.</li><li>**Drop-down box:** Chọn sự kiện AppsFlyer được xác định trước phù hợp nhất.</li><li>**As is**: Gửi các sự kiện như vốn có mà không ánh xạ tên.</li></ul> |
| **for users from** | Chọn tùy chọn gửi cho sự kiện:<ul><li>**This partner only** (mặc định): Chỉ gửi các bài đăng lại khi sự kiện này được phân bổ cho đối tác này.</li><li>**All media sources including organic**: Gửi các bài đăng lại cho các sự kiện được phân bổ cho bất cứ đối tác nào cũng như các sự kiện tự nhiên. TikTok for Business khuyến nghị chọn **All media sources including organic** để tối ưu hóa tốt hơn.</li></ul> |
| **bao gồm** | <ul><li>**No values & no revenue** (mặc định): Chỉ gửi sự kiện mà không gửi bất kỳ giá trị nào của sự kiện.</li><li>**Values & no revenue**: Gửi tất cả các thông số, **ngoại trừ** giá trị doanh thu.</li><li>**Values & revenue**: Gửi tất cả các thông số sự kiện, **bao gồm** cả giá trị doanh thu (nếu có trong sự kiện). TikTok for Business khuyến khích chọn **Values & revenue** để tối ưu hóa tốt hơn.</li></ul> |

3. [Tùy chọn] Nhấp vào biểu tượng **Add condition**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />để <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#đăng-lại-sự-kiện-trong-ứng-dụng-có-điều-kiện">đặt điều kiện</Anchor> cho một sự kiện.
4. Nhấp vào **Save integration**.
5. [Tùy chọn] Sau khi lưu tích hợp, trong khi vẫn ở trang cấu hình, bạn có thể tích hợp thêm ứng dụng của mình với đối tác:
   1. Từ góc trên cùng bên trái, dưới tên đối tác, hãy nhấp vào tên ứng dụng để mở danh sách ứng dụng.
   2. Chọn một ứng dụng khác từ danh sách thả xuống.
   3. Lặp lại các bước tích hợp đối với ứng dụng đã chọn.

> 📘 **Lưu ý**
>
> * Chỉ dành cho ứng dụng iOS: Quyền kiểm soát dữ liệu của bạn được chia sẻ với đối tác thông qua các bài đăng lại và <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions">báo cáo</Anchor> tùy thuộc vào trạng thái chuyển đổi **Quyền riêng tư Nâng cao (dành cho iOS 14.5+ trở lên)**.
> * Khi di chuyển sang tích hợp mới (`tiktokglobal_int`), mọi sự kiện đăng lại được cấu hình trong tích hợp cũ (`bytedanceglobal_int`) đều được tự động nhập với cấu hình tương tự.
>   * Nếu một sự kiện được ánh xạ tới **sự kiện** Pay trong TikTok for Business [Kế thừa], thì khi chuyển sang tích hợp mới, tên sự kiện này sẽ tự động được đổi thành **Purchase**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Thẻ Attribution link">

Đường dẫn phân bổ không liên quan đến <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns">SRN</Anchor> hoặc SRN Nâng cao.

SRN thực hiện phân bổ trong nền tảng của riêng mình. Phân bổ cho các SRN Nâng cao được thực hiện bằng cách kết hợp dữ liệu tương tác của họ với dữ liệu từ AppsFlyer—sử dụng cài đặt phân bổ mà bạn đã xác định trong [thẻ Integration](#integration-tab).

</Accordion>

<div id="cost-tab-for-cost-clicks-and-impressions" />

<Accordion title="Thẻ Cost (dành cho chi phí, lượt nhấp và lượt hiển thị)">

Việc tích hợp này cung cấp dữ liệu hợp nhất về chi phí, lượt nhấp và lượt hiển thị cho các chiến dịch, bộ quảng cáo, quảng cáo và vùng địa lý/quốc gia của bạn. Xem <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">bảng tích hợp chi phí mạng quảng cáo</Anchor> để biết chi tiết đầy đủ về các phương diện, phép đo và tính năng được hỗ trợ.

**Lưu ý:** Dữ liệu về lượt nhấp và lượt hiển thị đã được đưa vào tích hợp. Tuy nhiên, **dữ liệu chi phí yêu cầu phải có đăng ký <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>**.

**Để bật kết nối API dành cho chi phí, lượt nhấp và lượt hiển thị với TikTok For Business**:

1. Đi đến thẻ **Cost (Chi phí)** và bật **Get cost data (Nhận dữ liệu chi phí)**.
2. Nhấp vào **Log in to TikTok Ads**.
3. Từ cửa sổ TikTok mở ra, hãy đăng nhập vào tài khoản TikTok của bạn và xác nhận các quyền cần thiết.
4. Sau khi thông báo thành công xuất hiện trong cửa sổ TikTok, hãy đóng lại. Chi tiết tài khoản TikTok của bạn lúc này sẽ xuất hiện trong mục **Connected accounts**.
5. Từ **Advertiser account IDs** > **Advertiser ID**: Nhập ID tài khoản nhà quảng cáo TikTok và nhấp vào **Add**.  

   > 📘 **Lưu ý**
   >
   > * Để lấy **ID Nhà quảng cáo** từ tài khoản doanh nghiệp TikTok của bạn: Đi đến **Users** > **Members** và trong tài khoản Nhà quảng cáo, bạn có thể thấy ID.
   > * Đảm bảo **ID Nhà quảng cáo** mà bạn thêm vào được liên kết với **tài khoản TikTok** mà bạn đã kết nối ở bước 2, vì tài khoản này là nguồn thu thập dữ liệu.
   > * Kết nối ít nhất một **ID Nhà quảng cáo**. Bạn có thể thêm tối đa 30 ID.

6. Nhấp vào **Save Cost**.

<div id="for-roi360-subscribers" />

#### Đối với người đăng ký ROI360

* Các nhà quảng cáo và đại lý đã bật API chi phí trong cả các tích hợp `bytedanceglobal_int` cũ và tích hợp `tiktokglobal_int` hiện tại có thể thấy dữ liệu chi phí trùng lặp. Để tránh điều này, hãy đi đến tích hợp `bytedanceglobal_int` > thẻ **Cost** và tắt nút chuyển đổi.  
  Tuy nhiên, khi bật tính năng tích hợp chi phí mới, dữ liệu chi phí từ 5 ngày trước ngày chuyển đổi sẽ tự động được thu thập. Điều này có nghĩa là hoạt động tích hợp mới dự kiến sẽ hiển thị dữ liệu chi phí trùng lặp trong 5 ngày đó. **Ví dụ**: nếu tính năng tích hợp chi phí cũ bị tắt vào ngày 15 tháng 1 và tính năng tích hợp chi phí mới được bật vào cùng ngày thì dữ liệu chi phí trùng lặp sẽ được hiển thị trong tính năng tích hợp chi phí mới từ ngày 10 đến ngày 14 tháng 1, mặc dù tính năng này chỉ được bật vào ngày 15 tháng 1.
* Xem <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">bảng tích hợp chi phí mạng quảng cáo</Anchor> để biết chi tiết đầy đủ về các phương diện, phép đo và tính năng được hỗ trợ.
* <Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Xem trạng thái API chi phí của bạn</Anchor> và lần gần nhất AppsFlyer lấy được dữ liệu chi phí phù hợp trong bảng điều khiển trạng thái tích hợp chi phí (và doanh thu quảng cáo) hoặc bảng điều khiển mạng quảng cáo cá nhân.
* Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">việc bật kích hoạt API chi phí</Anchor>.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Thẻ Ad revenue">

Phần này sẽ có liên quan đến bạn nếu vai trò của bạn là nhà phát hành—hiển thị quảng cáo của đối tác cho người dùng của bạn. Bạn có thể đo lường mức độ tương tác của người dùng thu được từ các nguồn khác nhau và tìm ra nguồn nào mang lại nhiều lợi nhuận hơn.

**Để bật API doanh thu quảng cáo**:

* Tuân thủ <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">các hướng dẫn tích hợp này</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Thẻ Permission">

Trong phần này, bạn có thể chọn các quyền để cấp cho TikTok for Business quyền truy cập vào dữ liệu của mình và thực hiện các hành động khác nhau.

Lưu ý rằng ngay cả sau khi tích hợp bị <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">hủy kích hoạt</Anchor>, khi nút chuyển đổi **TikTok for Business permissions** được bật, các quyền vẫn sẽ được cấp. 

Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#permissions-tab">việc cấp quyền</Anchor>.

</Accordion>

<div id="set-up-tiktok-for-business-for-agencies" />

## Thiết lập TikTok For Business dành cho đại lý

Các đại lý làm việc thay mặt cho nhà quảng cáo có thể bật chức năng tích hợp TikTok for Business và bắt đầu nhận phân bổ cho các chiến dịch của họ. Tuy nhiên, chức năng tích hợp này có một số hạn chế đối với các đại lý.

<div id="agency-limitations" />

### Hạn chế của đại lý

* Một đại lý chỉ có thể truy cập chức năng tích hợp TikTok for Business sau khi nhà quảng cáo mà họ làm việc cùng đã kích hoạt chức năng này từ phía họ.
* Kể từ ngày 1 tháng 1 năm 2024, các thông số phân bổ hiển thị trên trang tích hợp của đại lý sẽ được kế thừa từ quá trình tích hợp của nhà quảng cáo ở chế độ **chỉ xem**. Điều này có nghĩa là đại lý có thể biết cách nhà quảng cáo định cấu hình giai đoạn xem lại phân bổ nhưng không thể tự định cấu hình chúng.
* Đối với các sự kiện sau khi phân bổ, nếu được nhà quảng cáo cấp phép, đại lý có thể định cấu hình các bài đăng lại theo sự kiện trong ứng dụng.
* Đại lý không thể bật cài đặt Bảo mật Nâng cao (ngay cả khi được cấp quyền)—điều này chỉ giới hạn cho nhà quảng cáo.

**Để thiết lập TikTok For Business dành cho đại lý:**

1. Trong AppsFlyer, ở mục **Configuration** đi đến **Partner Marketplace**.
2. Tìm và chọn **TikTok for Business** .
3. Nhập **ID Ứng dụng TikTok**.
4. Nhập **ID Tài khoản TikTok** đại lý của bạn. Điều này xác định lưu lượng truy cập của đại lý và phân biệt với lưu lượng truy cập của nhà quảng cáo.
5. Nhấp vào **Save Integration**.  

   <Image alt="tiktok_agency_account_id.png" src="https://support.appsflyer.com/hc/article_attachments/15195630638609" width="442px" />

> ❗️ **Cảnh báo**
>
> KHÔNG ĐƯỢC PHÉP chia sẻ ID tài khoản TikTok For Business với nhà quảng cáo hoặc đại lý. Nếu đã chia sẻ, TẤT CẢ lượt cài đặt của nhà quảng cáo sẽ tự động được phân bổ trên bảng điều khiển của đại lý.

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/bytedance-ads-china-campaign-configuration">Quảng cáo ByteDance (Ocean Engine)</Anchor> dành cho lưu lượng truy cập tại Trung Quốc (bytedance\_int)
> * <Anchor target="_blank" href="/marketers/vi/docs/skan-interoperation-with-tiktok-for-business">Khả năng tương tác SKAN với TikTok For Business</Anchor>

<div data-zendesk-anchors="01H8VVCC8GW5AZ3M475XFZY9JW=l%C6%B0u-%C3%BD overview=t%E1%BB%95ng-quan 01H8VVCC8G3ZXZJMHSMJ67GMG4=t%E1%BB%95ng-quan activate-partner=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c 01H8VVCC8GH1MNRAY9HC9P6JR0=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c setting-up-tiktok-for-business%C2%A0integration=thi%E1%BA%BFt-l%E1%BA%ADp-tiktok-for-business 01H8VVCC8GPY4SEFGK30Q1BJZ6=thi%E1%BA%BFt-l%E1%BA%ADp-tiktok-for-business 01H8VVCC8G6P25R0N5A7S3NGY7=l%C6%B0u-%C3%BD-1 01H8VVCC8GY6WTH0404RH2AR9F=integration-tab activate-partner::e4f2f638=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c-1 01H8VVCC8G0KR4AA2HD9S8QBKD=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c-1 advanced-privacy=quy%E1%BB%81n-ri%C3%AAng-t%C6%B0-n%C3%A2ng-cao 01H8VVCC8G0Z6ZHC10KVY9CGGQ=quy%E1%BB%81n-ri%C3%AAng-t%C6%B0-n%C3%A2ng-cao 01H8VVCC8GC57YTDWA9EB2VP87=l%C6%B0u-%C3%BD-2 general-settings=c%C3%A0i-%C4%91%E1%BA%B7t-chung 01H8VVCC8GSDPSNN0AJPVZPR8P=c%C3%A0i-%C4%91%E1%BA%B7t-chung 01H8VVCC8G2JB115XW49HJQFHA=l%C6%B0u-%C3%BD-3 default-postbacks=c%C3%A1c-b%C3%A0i-%C4%91%C4%83ng-l%E1%BA%A1i-m%E1%BA%B7c-%C4%91%E1%BB%8Bnh 01H8VVCC8GW677RN6R6CV35KGG=c%C3%A1c-b%C3%A0i-%C4%91%C4%83ng-l%E1%BA%A1i-m%E1%BA%B7c-%C4%91%E1%BB%8Bnh 01H8VVCC8G6M8D3WQ2CM10ZNZX=l%C6%B0u-%C3%BD-6 install-attribution=ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t 01H8VVCC8GK8VFPBEPAMVHCAWM=ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t 01H8VVCC8G3YFDZVV9X9709F9M=l%C6%B0u-%C3%BD-5 reengagement-attribution=ph%C3%A2n-b%E1%BB%95-thu-h%C3%BAt-l%E1%BA%A1i 01H8VVCC8HHG5290PYF0BT29QA=ph%C3%A2n-b%E1%BB%95-thu-h%C3%BAt-l%E1%BA%A1i 01H8VVDWH85M34K7Z75BAT7BQW=quan-tr%E1%BB%8Dng inapp-event-postbacks=%C4%91%C4%83ng-l%E1%BA%A1i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng 01H8VVCC8HHZRFQ2T1X478YZMP=%C4%91%C4%83ng-l%E1%BA%A1i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng 01H8VVCC8HDMTY1P2SG31HD61K=l%C6%B0u-%C3%BD-6 01H8VVCC8H53ZRMDBNK1436NAX=attribution-link-tab 01H8VVCC8H74GDVCNAXT0741MG=cost-tab-for-cost-clicks-and-impressions 01H8VVCC8HFJF62TC7DNXRH22A=l%C6%B0u-%C3%BD-7 for-xpend-subscribers=%C4%91%E1%BB%91i-v%E1%BB%9Bi-ng%C6%B0%E1%BB%9Di-%C4%91%C4%83ng-k%C3%BD-roi360 01H8VVCC8HWDC9A03FRY5BC87Y=%C4%91%E1%BB%91i-v%E1%BB%9Bi-ng%C6%B0%E1%BB%9Di-%C4%91%C4%83ng-k%C3%BD-roi360 01H8VVCC8H90ANM70QAHKTQQ1S=ad-revenue-tab 01H8VVCC8HAG0XVWE2T9PRDHTK=permissions-tab setting-up-tiktok-for-business-for-agencies=thi%E1%BA%BFt-l%E1%BA%ADp-tiktok-for-business-d%C3%A0nh-cho-%C4%91%E1%BA%A1i-l%C3%BD 01H8VVCC8HVNNQ9PJS4ZQCVDNS=thi%E1%BA%BFt-l%E1%BA%ADp-tiktok-for-business-d%C3%A0nh-cho-%C4%91%E1%BA%A1i-l%C3%BD agency-limitations=h%E1%BA%A1n-ch%E1%BA%BF-c%E1%BB%A7a-%C4%91%E1%BA%A1i-l%C3%BD h_01HHVGS94CB9XC0T63VFDZ18JS=h%E1%BA%A1n-ch%E1%BA%BF-c%E1%BB%A7a-%C4%91%E1%BA%A1i-l%C3%BD 01H8VVCC8HWJ2WQ83E0CZMEHH1=c%E1%BA%A3nh-b%C3%A1o h_01HE7RY8K7HV2CTZ2S537YRCNQ=xem-th%C3%AAm" />
