---
title: Tích hợp Medialyzer với AppsFlyer
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2023-05-01T11:43:34Z'
  edited_at: '2023-09-26T14:07:02Z'
  id: 14963611180689
  locale: vi
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/vi/articles/14963611180689
---
> **Khái quát:** Medialyzer, một đối tác tích hợp của AppsFlyer, phát triển và tiếp thị phần mềm dưới dạng giải pháp dịch vụ. Giải pháp này cho phép các nhà lập kế hoạch truyền thông tối ưu hóa các chiến dịch truyền hình của họ cho các doanh nghiệp trực tuyến dựa trên số lượt truy cập và chuyển đổi được tạo ngay lập tức mỗi lần phát quảng cáo trên truyền hình.

<div id="important" />

> 🚧 **Quan trọng!**
>
> <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions#hạn-chế-nguồn-truyền-thông">Một số nguồn truyền thông</Anchor> hạn chế chia sẻ dữ liệu với các bên thứ ba. Do đó, đăng lại cho các sự kiện bị hạn chế sẽ không được gửi tới đối tác này, bất kể lựa chọn đã định cấu hình để gửi đăng lại là gì.

<div id="setting-up-medialyzer" />

## Thiết lập Medialyzer

Quá trình thiết lập được thực hiện từ trang **Active Integrations**, nhưng để tìm đối tác, trước tiên bạn phải truy cập vào <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations">marketplace</Anchor>.

> 📘 **Lưu ý**
>
> Trước khi thiết lập tích hợp, hãy nhớ <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations#liên-hệ-với-đối-tác">liên hệ với đối tác</Anchor> và mở tài khoản với họ.

**Để kích hoạt tích hợp:**

1. Từ menu trên cùng của bất kỳ trang AppsFlyer nào, hãy nhấp vào **Marketplace**.
2. Tìm kiếm và chọn đối tác.
3. Nhấp vào **Set up integration**. Bạn được chuyển đến trang thiết lập tích hợp.
4. Trong thẻ **Integration**, chọn ứng dụng cho tích hợp và bật **Activate partner**.  
   **Lưu ý:** Nút bật/tắt phải luôn ở trạng thái bật <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">(được kích hoạt)</Anchor> trong thời gian bạn làm việc với đối tác.
5. Hoàn thành cấu hình bằng cách sử dụng các tab có liên quan, như được mô tả bên dưới.

Cửa sổ cấu hình chỉ sử dụng thẻ **Integration**.

Để biết mô tả chi tiết về Tiêu đề Cửa sổ Cấu hình Đối tác, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">đây</Anchor>.

<div id="integration-tab" />

<Accordion title="Thẻ Integration">

<div id="activate-partner" />

#### Kích hoạt đối tác

Trong lần truy cập đầu tiên, bạn sẽ cần bật nút bật/tắt **Activate partner** để thiết lập tích hợp. Nút bật/tắt phải luôn bật trong thời gian bạn làm việc với Medialyzer. Tìm hiểu thêm về kích <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">hoạt đối tác</Anchor>.

<div id="advanced-privacy" />

#### Quyền riêng tư Nâng cao

Đối với ứng dụng iOS, nút bật/tắt <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">Advance Privacy</Anchor> sẽ xuất hiện. Khi được bật, tính năng này sẽ giới hạn việc chia sẻ mã định danh người dùng với đối tác. Lưu ý rằng khi bật nút <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">Aggregated Advanced Privacy</Anchor> trong App Settings, **Advanced Privacy (for iOS 14.5+ and later)** cũng sẽ được bật và khóa theo mặc định.

<div id="default-postbacks" />

#### Postback Mặc định

AppsFlyer gửi postback mặc định đến Medialyzer sau các lượt cài đặt của người dùng. Sử dụng phần này để <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#f">xác định các postback này</Anchor>.

* **Off**: Postback cài đặt không được gửi đến Medialyzer.
* **All media sources, including organic**: Postback cài đặt được gửi cho các sự kiện được phân bổ cho bất kỳ đối tác và sự kiện tự nhiên nào.

![default_postbacks.png](https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png)

<div id="in-app-event-postbacks" />

#### Postback sự kiện trong ứng dụng

Trong phần này, bạn có thể ánh xạ các sự kiện AppsFlyer của mình với đối tác của mình qua các postback.

[![app_event_postbacks.JPG](https://files.readme.io/a6a4aaa89c3eb5ba759a32312663b4c9855738eaea56366070ca9a8da3840a69-14963640866833.png)](https://files.readme.io/a6a4aaa89c3eb5ba759a32312663b4c9855738eaea56366070ca9a8da3840a69-14963640866833.png)

1. Bật tùy chọn **In-app events postback**.
2. Nhấp vào **Add event** để thêm một SDK hoặc sự kiện từ máy chủ đến máy chủ vào danh sách.
3. Điền những tham số dưới đây: 

| Tên thông số | Mô tả |
| --- | --- |
| **AppsFlyer event** | Tên của sự kiện mà AppsFlyer nhận được từ SDK sẽ được tích hợp vào ứng dụng của bạn hoặc từ các sự kiện máy chủ đến máy chủ.<br />**Lời khuyên**: Bạn không thấy sự kiện đang tìm kiếm?<ul><li>Hãy đảm bảo kích hoạt sự kiện trên thiết bị có cài đặt không tự nhiên và kiểm tra lại.</li><li>Nhập vào **AppsFlyer event**, sau đó nhấp vào **Create custom**. Đọc thêm về <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#sự-kiện-tùy-chỉnh">ánh xạ sự kiện tùy chỉnh.</Anchor></li></ul> |
| **mapped to partner event** | Nhập tên sự kiện tương ứng hoặc ID của từng sự kiện, như được xác định trong BPM, hoặc gửi các sự kiện nguyên dạng không có ánh xạ tên. |
| **for users from** | Chọn **All media sources, including organic** để gửi postback cho các sự kiện được phân bổ cho bất kỳ đối tác và sự kiện tự nhiên nào. |
| **including** | <ul><li>**Không có giá trị & không có doanh thu**: Chỉ gửi bản thân sự kiện mà không kèm bất kỳ thông số nào (giá trị hoặc doanh thu).</li><li>**Không có giá trị & không có doanh thu**: Gửi tất cả các thông số, **ngoại trừ** giá trị doanh thu.</li><li>**Giá trị & doanh thu**: Gửi tất cả các thông số sự kiện, **bao gồm** cả giá trị doanh thu (nếu có trong sự kiện).</li></ul> |

4. Nhấp vào **Save Integration**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Thẻ Attribution link">

Các liên kết phân bổ không khả dụng cho Medialyzer.

</Accordion>

<div id="cost-tab" />

<Accordion title="Thẻ Cost">

Dữ liệu chi phí không được hỗ trợ trong tích hợp với Medialyzer.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Thẻ Ad revenue">

Dữ liệu doanh thu quảng cáo không được hỗ trợ trong tích hợp với Medialyzer.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Thẻ Permission">

Các quyền không khả dụng cho Medialyzer.

</Accordion>

<div data-zendesk-anchors="h_01H9FKEAV2225HM5CQAGWS2K99=quan-tr%E1%BB%8Dng setting-up-spoteffects=thi%E1%BA%BFt-l%E1%BA%ADp-medialyzer h_01H9FKEAV37AT3VTZ5WV1YMWC2=thi%E1%BA%BFt-l%E1%BA%ADp-medialyzer h_01H9FKEAV3AV8YMNADQ62476YR=l%C6%B0u-%C3%BD h_01H9FKEAV3YQY124TSZ5Q7VHAY=integration-tab activate-partner=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c h_01H9FKEAV3DW2A6RQ1NS44FT5F=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c advanced-privacy=quy%E1%BB%81n-ri%C3%AAng-t%C6%B0-n%C3%A2ng-cao h_01H9FKEAV3T3YCPBYW70QVF540=quy%E1%BB%81n-ri%C3%AAng-t%C6%B0-n%C3%A2ng-cao default-postbacks=postback-m%E1%BA%B7c-%C4%91%E1%BB%8Bnh h_01H9FKEAV3Z1Y09P6E18J8AVX2=postback-m%E1%BA%B7c-%C4%91%E1%BB%8Bnh inapp-event-postbacks=postback-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01H9FKEAV3GG6X17X3NCCSWJAS=postback-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01H9FKEAV3ZEF1AHRTQGEGYFSJ=attribution-link-tab h_01H9FKEAV3ERXQ98BJGKBQRGP2=cost-tab h_01H9FKEAV32MB7M2Q1ASDAE6RM=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab" />
