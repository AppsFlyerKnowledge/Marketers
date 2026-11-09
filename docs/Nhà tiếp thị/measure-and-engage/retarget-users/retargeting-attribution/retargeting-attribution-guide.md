---
title: Hướng dẫn phân bổ nhắm mục tiêu lại
metadata:
  keywords:
    - Attribution
    - Re-targeting
    - retargeting
    - Advertisers
    - reatribution
    - re-atribution
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-09-30T13:18:26Z'
  edited_at: '2023-11-16T10:14:41Z'
  id: 207033786
  locale: vi
  section: Retargeting attribution
  section_id: 6551326229265
  url: https://support.appsflyer.com/hc/vi/articles/207033786
---
> **Khái quát:** Các chiến dịch nhắm mục tiêu lại (tiếp thị lại) thúc đẩy người dùng mở và thu hút lại với ứng dụng hoặc khiến những người dùng đã xóa ứng dụng thì giờ cài đặt lại.

<div id="retargeting-fundamentals" />

## Các nguyên tắc cơ bản về nhắm mục tiêu lại

Nhắm mục tiêu lại cho phân bổ xảy ra khi một người dùng thu hút với chiến dịch nhắm mục tiêu lại bằng cách nhấp vào [đường dẫn nhắm mục tiêu lại cho phân bổ](/docs/retargeting-attribution-guide#retargeting-attribution-links) hoặc <Anchor target="_blank" href="/marketers/vi/docs/create-a-onelink-template">liên kết sâu</Anchor>. Điều này dẫn đến một trong các sự kiện phân bổ sau:

* **Thu hút lại:** Nếu ứng dụng có trên thiết bị, nguồn truyền thông thúc đẩy người dùng mở ứng dụng sẽ được ghi nhận lượt thu hút lại.
* **Phân bổ lại (còn gọi là lượt cài đặt lại nhắm mục tiêu lại)**: Nếu ứng dụng không có trên thiết bị của người dùng (nghĩa là người dùng đã gỡ cài đặt ứng dụng), thì việc thu hút với chiến dịch nhắm mục tiêu lại sẽ khiến người dùng cài đặt lại và mở ứng dụng. Nếu điều này xảy ra trong <Anchor target="_blank" href="/marketers/vi/docs/set-up-re-attribution-window">khung thời gian phân bổ lại:</Anchor> nguồn truyền thông nhắm mục tiêu lại được ghi có cho phân bổ lại đó. Bài viết liên quan: <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#reinstalls">Lượt cài đặt lại.</Anchor>

<Image align="center" alt="" src="https://files.readme.io/64b8d9f5040daa281ae13f0855749ab4a88a2e7e8616d6ada37975899db92c80-31937591646097.png" />

Trước khi chạy các chiến dịch nhắm mục tiêu lại, hãy xem lại các quy tắc thu hút lại và các trường hợp ví dụ trong các phần tiếp theo, sau đó thiết lập tính năng nhắm mục tiêu lại như được mô tả trong phần quy trình nhắm mục tiêu lại. Để dễ hiểu, bạn nên làm quen với <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model">mô hình phân bổ</Anchor> của AppsFlyer và các khung thời gian phân bổ liên quan.

<div id="tip" />

> 👍 **Lời khuyên**
>
> Bạn muốn biết thêm về tái xác định mục tiêu? Hãy xem <Anchor target="_blank" href="https://elevate.appsflyer.com/pages/142/remarketing">khóa học ngắn, bổ ích</Anchor> này trên Cổng thông tin Học tập AppsFlyer.

<div id="reengagement-rules-and-windows" />

<Accordion title="Quy tắc và khung thời gian thu hút lại">

* Các quy tắc nhắm mục tiêu lại cho phân bổ xác định xem một sự kiện có phải là sự kiện nhắm mục tiêu lại hay không và được phân bổ cho nguồn truyền thông nhắm mục tiêu lại.
* Tương tự như các chiến dịch phân bổ thu hút người dùng, các lượt thu hút lại nhắm mục tiêu lại SRN được API báo cáo và các lượt của nguồn không phải SRN được đường dẫn phân bổ báo cáo.
* Các quy tắc, dựa trên hành trình của người dùng, bao gồm:
  * [Các khung thời gian đưa vào](/docs/retargeting-attribution-guide#khung-thời-gian-đưa-vào), một khoảng thời gian mà trong đó lượt thu hút lại có thể diễn ra.
  * [Các khung thời gian loại trừ](/docs/retargeting-attribution-guide#khung-thời-gian-loại-trừ), một khoảng thời gian mà trong đó sự kiện thu hút lại không thể diễn ra.
* Nếu lượt thu hút lại được phân bổ, thì các sự kiện trong ứng dụng trong thời lượng khung thời gian thu hút lại được <Anchor target="_blank" href="/marketers/vi/docs/resolve-retargeting-double-attribution">phân bổ kép.</Anchor> Điều này có nghĩa là lượt thu hút lại được phân bổ cho cả nguồn truyền thông nhắm mục tiêu lại và nguồn truyền thông UA ban đầu nếu được xác định.

Sơ đồ sau chứa tập hợp các quy tắc thu hút lại. Sử dụng sơ đồ làm hướng dẫn để xác định xem liệu một lượt tương tác với chiến dịch nhắm mục tiêu lại có được coi là một lượt thu hút lại hay không.

**Quy tắc thu hút lại**

![](https://files.readme.io/e6643112f3e9969242c0dd394f6401406fbc837a9494cc4bb3825cff6365f36d-33563511578513.png) **Tham chiếu—khung thời gian đưa vào và loại trừ**

Các bảng sau chứa thông tin tham khảo về các khung thời gian liên quan đến nhắm mục tiêu lại cho phân bổ.

<div id="inclusion-windows" />

#### Khung thời gian đưa vào

| Loại khung thời gian | Mô tả |
| --- | --- |
| Lượt xem qua | Thời lượng tối đa từ lúc người dùng xem quảng cáo cho đến khi họ mở một ứng dụng.<br /><br />**Vị trí cấu hình**: Đường dẫn phân bổ<br /><br />**Thời lượng**:<ul><li>Mặc định: 1 ngày</li><li>Phạm vi: 1-23 giờ/1-7 ngày</li></ul> |
| Xem lại lượt nhấp | Thời lượng tối đa từ lúc người dùng nhấp vào quảng cáo cho đến khi họ mở một ứng dụng.<br /><br />**Vị trí cấu hình**: Đường dẫn phân bổ<br /><br />**Thời lượng** :<ul><li>Mặc định: 7 ngày</li><li>Phạm vi: 1-23 giờ/1-30 ngày</li></ul>**Lưu ý về SRN:** Kiểm tra với SRN xem chính sách khung thời gian xem lại cụ thể của họ là gì. |
| Thu hút lại | Hãy cân nhắc những điều sau liên quan đến khung thời gian thu hút lại:<ul><li>Khung thời gian bắt đầu khi người dùng mở ứng dụng lần đầu sau khi thu hút với nguồn truyền thông nhắm mục tiêu lại.</li><li>Các sự kiện trong ứng dụng được <Anchor target="_blank" href="/marketers/vi/docs/resolve-retargeting-double-attribution">phân bổ kép</Anchor> cho các nguồn truyền thông nhắm mục tiêu lại và thu hút người dùng trong suốt thời lượng của khung thời gian</li><li>Thời lượng của khung thời gian này được xác định bằng cài đặt của ứng dụng hoặc SRN.</li><li>Nếu người dùng tương tác với một chiến dịch nhắm mục tiêu lại khác trong khung thời gian thu hút lại không bị chặn bởi khung thời gian loại trừ thì khung thời gian thu hút lại sẽ kết thúc ngay lập tức và một khung thời gian thu hút lại mới sẽ bắt đầu.</li><li>Trong trường hợp phân bổ lại: thời lượng của **cửa sổ phân bổ** là không giới hạn (tương tự các lượt cài đặt). Tuy nhiên, cửa sổ này sẽ đóng trong trường hợp có lượt cài đặt mới, lượt cài đặt lại hoặc do các hạn chế lưu giữ dữ liệu.</li></ul>**Nơi đặt:** Đường dẫn phân bổ<ul><li>Mặc định: 30 ngày</li><li>Phạm vi: 1-23 giờ/1-90 ngày/trọn đời</li></ul>**Lưu ý về SRN**: Có thể cấu hình được đối với các SRN<br /><br />Nếu bạn thay đổi cài đặt khung thời gian, thay đổi sẽ ảnh hưởng đến các lượt thu hút lại trong tương lai. Nhưng sẽ không ảnh hưởng đến các lượt thu hút lại hiện có. |

<div id="exclusion-windows" />

#### Khung thời gian loại trừ

| Loại khung thời gian | Mô tả |
| --- | --- |
| Thời gian tối thiểu giữa các chuyển đổi thu hút lại | Không ghi nhận lượt thu hút lại trong khung thời gian loại trừ.<br /><br />**Thời gian tối thiểu giữa các chuyển đổi thu hút lại**<ul><li>Khi thu hút lại, một khung thời gian trong đó các sự kiện trong ứng dụng được phân bổ cho cả chiến dịch nhắm mục tiêu lại (chính) và UA (phụ) sẽ mở ra.</li><li>Điều này cho phép đo lường hiệu suất chiến dịch nhắm mục tiêu lại.</li><li>Nếu một mạng khác hoặc chiến dịch mang đến lượt thu hút lại trong khung thời gian này:<ul><li>[Mặc định] khung thời gian thu hút lại hiện có sẽ bị đóng, một lượt thu hút lại khác được ghi nhận và các sự kiện trong ứng dụng tiếp theo được phân bổ cho lượt thu hút lại gần đây nhất.</li><li>Để ngăn chặn điều này, hãy đặt Thời gian tối thiểu giữa các lượt chuyển đổi thu hút lại. Trong trường hợp này, chỉ có thể ghi nhận một lượt thu hút lại tiếp theo sau khi khoảng thời gian tối thiểu đã trôi qua.</li></ul></li><li>Cài đặt này không ảnh hưởng trong trường hợp khung thời gian thu hút lại ngắn hơn thời gian của cài đặt này. Ví dụ: Nếu thời gian thu hút lại là 1 ngày và cài đặt này là 4 ngày thì cài đặt này không có ảnh hưởng gì.</li><li>Các cài đặt này không ảnh hưởng đến thời gian giữa cài đặt và thu hút lại.</li></ul>**Vị trí đặt**: Trang cài đặt của ứng dụng<br /><br />**Thời lượng**:<ul><li>Mặc định: Không</li><li>Phạm vi: 1-23 giờ/1-30 ngày</li></ul> |
| <Anchor target="_blank" href="/marketers/vi/docs/set-retargeting-inactivity-window">Khoảng thời gian không hoạt động tối thiểu</Anchor> | Không ghi lại lượt thu hút lại hoặc phân bổ lại trong khung thời gian loại trừ.<br /><br />**Nơi đặt:** Trang cài đặt đối tác tích hợp trong tab Integration.<br /><br />**Thời lượng**:<ul><li>Mặc định: Không</li><li>0-30 ngày</li></ul>**Lưu ý về SRN**: Lưu ý rằng SRN thường có các quy tắc về khoảng thời gian không hoạt động riêng. Nếu cài đặt của bạn khác với cài đặt của SRN, điều này có thể dẫn đến khác biệt. |
| <Anchor target="_blank" href="/marketers/vi/docs/set-up-re-attribution-window">Ghi công lại</Anchor> | Khung thời gian phân bổ lại ảnh hưởng đến các lượt phân bổ lại nhưng không ảnh hưởng đến các lượt thu hút lại.<br /><br />Người dùng cài đặt lại trong khung thời gian phân bổ lại sau khi thu hút với chiến dịch nhắm mục tiêu lại được phân bổ cho các nguồn truyền thông nhắm mục tiêu lại. Bài viết liên quan: <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#reinstalls">Lượt cài đặt lại</Anchor><br /><br />**Vị trí đặt:** Cài đặt của ứng dụng |

<div id="example-flow-implementing-the-rules" />

#### **Quy trình mẫu thực hiện các quy tắc**

<Image align="center" alt="" src="https://files.readme.io/f4b53c27319370434863c156bf29051db9c2c12fda2128d0faf0f8a6ca6b7002-33563511579537.png" />

Danh sách kiểm tra quy tắc thu hút lại người dùng để phân bổ lượt nhấp qua và lượt xem hết:

| Quy tắc | Quy tắc |
| --- | --- |
| A | Người dùng đã tương tác với chiến dịch nhắm mục tiêu lại, nghĩa là người dùng đã xem hoặc nhấp vào quảng cáo được xác định là quảng cáo nhắm mục tiêu lại. |
| B | Thu hút xảy ra **trong** khung thời gian xem lại lượt nhấp hoặc xem hết. |
| C | Người dùng đã không hoạt động lâu hơn khoảng thời gian không hoạt động tối thiểu. |
| D | Trong trường hợp đối với các sự kiện trong ứng dụng, chúng diễn ra trong khoảng thời gian thu hút lại. |
| E | Khoảng thời gian giữa lần thu hút lại trước đó lớn hơn thời gian tối thiểu giữa các lần thu hút lại. |

</Accordion>

<div id="example-retargeting-scenarios" />

<Accordion title="Các tình huống ví dụ về nhắm mục tiêu lại">

| **Tình huống 1: Mua hàng trước, trong và sau khung thời gian thu hút lại**<br /><br />Hành trình của người dùng:<ul><li>Thu hút với quảng cáo từ mạng Z, cài đặt ứng dụng và mua hàng (A).</li><li>Tương tác với quảng cáo nhắm mục tiêu lại từ mạng Y, mở ứng dụng và mua hàng (B).</li><li>Mua hàng (C).</li></ul>![](https://files.readme.io/f4b53c27319370434863c156bf29051db9c2c12fda2128d0faf0f8a6ca6b7002-33563511579537.png)<br /><br />Cột P/S: Chính hoặc Phụ được mô tả trong <Anchor target="_blank" href="/marketers/vi/docs/resolve-retargeting-double-attribution">phân bổ kép các sự kiện nhắm mục tiêu lại</Anchor> |
| --- |
| **Tình huống 2: Nhiều lượt chuyển đổi trong khung thời gian phân bổ thu hút lại**<br /><br />Hành trình của người dùng:<ul><li>Thu hút với quảng cáo từ mạng Z, cài đặt ứng dụng và mua hàng (A).</li><li>Tương tác với quảng cáo nhắm mục tiêu lại từ mạng Y, mở ứng dụng và mua hàng (B).</li><li>Mua hàng (C).</li></ul>![](https://files.readme.io/bf57f8a9597bd56a89bb3f1be3700195e1b153b548cb11ee3d37c65d5382e711-33563474530321.png)<br /><br />Cột P/S: Chính hoặc Phụ được mô tả trong <Anchor target="_blank" href="/marketers/vi/docs/resolve-retargeting-double-attribution">phân bổ kép các sự kiện nhắm mục tiêu lại</Anchor> |

</Accordion>

<div id="retargeting-operations" />

## Hoạt động nhắm mục tiêu lại

<div id="retargeting-settings" />

<Accordion title="Thiết lập Nhắm lại mục tiêu">

Yêu cầu các tùy chọn cài đặt sau tùy thuộc vào tình huống.

| Loại chuyển đổi | SRN | Không phải SRN |
| --- | --- | --- |
| Thu hút lại | <ol><li>Đi đến **Configuration** > **App settings.**</li><li>Xác minh đảm bảo rằng đang bật tùy chọn **Phân bổ** **thu hút lại**.</li><li>Đối với SRN: Đi đến **Configuration** > **Active integrations,** chọn SRN.</li><li>Bật tùy chọn **Re-engagement attribution**.</li></ol> | <ol><li>Đi đến **Configuration** > **App settings.**</li><li>Xác minh đảm bảo rằng đang bật tùy chọn **Phân bổ thu hút lại**.</li><li>Đối với mạng không phải SRN: Nối thông số nhắm mục tiêu lại vào các đường dẫn phân bổ như được nêu chi tiết trong phần này</li></ol> |
| Ghi công lại | <ol><li>Đi đến **Configuration** > **Active integrations,** chọn SRN.</li><li>Bật tùy chọn **Reinstall attribution** (Phân bổ lượt cài đặt lại).</li></ol> | <ol><li>Không cần các cài đặt cụ thể.</li><li>Nối thông số nhắm mục tiêu lại vào các đường dẫn phân bổ như được nêu chi tiết trong phần này.</li></ol> |

<div id="non-srn-settings" />

#### **Cài đặt mạng không phải SRN**

**Để thiết lập đối tác nhắm mục tiêu lại mạng quảng cáo (không phải SRN)**:

1. Trong AppsFlyer, đi đến **Configuration** > **Active Integrations**.
2. Chọn mạng quảng cáo.
3. Bật **Enable** **retargeting settings**. Điều này sẽ sửa đổi đường dẫn phân bổ thành một URL nhắm mục tiêu lại, bằng cách thêm `is_retargeting=true` vào đường dẫn.   

   <Image align="center" alt="" src="https://files.readme.io/68b8939885439a4f0e6d1ec6601552185905d1afc817da9fb88ccfe043a83364-33563511582609.png" />
4. Hãy chọn một trong các mục sau:
   * **Sử dụng đường dẫn phân bổ tiêu chuẩn cho các liên kết** đơn nền tảng (dành riêng cho ứng dụng).
   * **Sử dụng OneLink**.
     * Nhập **URL liên kết sâu**, nếu cần (xem hướng dẫn <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Liên kết sâu</Anchor>).
5. Sao chép URL được tạo và cung cấp cho mạng quảng cáo để sử dụng với chiến dịch nhắm mục tiêu lại của bạn.  
   **Lưu ý**: URL không tồn tại và không thể lưu được.

</Accordion>

<div id="retargeting-dashboard" />

<Accordion title="Retargeting Dashboard">

Bảng điều khiển tổng quan chứa các chỉ số nhắm mục tiêu lại cũng như chỉ số thu hút người dùng. Các chỉ số này dựa trên LTV và liên quan đến những người dùng thu hút với chiến dịch nhắm mục tiêu lại.

**Để xem dữ liệu nhắm mục tiêu lại**:

1. Trong AppsFlyer, đi tới **Dashboards** > **Overview**.
2. Nhấp vào **View type**, rồi chọn **Retargeting**.  
   Dữ liệu nhắm mục tiêu lại được hiển thị.  
   Lưu ý! Bạn cũng có thể xem dữ liệu nhắm mục tiêu lại ở chế độ xem hợp nhất. Xem các loại chế độ xem Bảng điều khiển.

</Accordion>

<div id="retargeting-attribution-links" />

<Accordion title="Các đường dẫn phân bổ nhắm mục tiêu lại">

* Liên kết nhắm lại mục tiêu tương tự như liên kết thu hút người dùng thông thường.
* Tạo đường dẫn cho:
  * Mạng không phải SRN hỗ trợ nhắm mục tiêu lại.
  * Phương tiện truyền thông sở hữu, sử dụng trang <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">quản lý liên kết</Anchor>.

Các thông số đường dẫn phân bổ nhắm mục tiêu lại

| Tham số | Mô tả | Bắt buộc |
| --- | --- | --- |
| `is_retargeting` | Đặt thành: `is_retargeting=true` | Có |
| ID quảng cáo | Nếu có thể, hãy gửi ID quảng cáo như IDFA, OAID, IDFV, v.v. <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#probabilistic-modeling">Các hạn chế của Mô hình Xác suất đối với các ứng dụng iOS.</Anchor> | Không |
| Khung thời gian xem lại lượt nhấp nhắm mục tiêu lại | <ul><li><Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows">Khung thời gian xem lại lượt nhấp</Anchor> nhắm mục tiêu lại cũng hoạt động tương tự với của chiến dịch thu hút người dùng.</li><li>Khung thời gian này xác định khoảng thời gian tối đa có thể trôi qua từ lúc một người dùng nhấp vào quảng cáo cho đến khi người dùng đó được phân bổ.</li><li>Khung thời gian xem lại được đặt bằng thông số `&af_click_lookback`.</li><li>Tùy chọn cài đặt mặc định là 7 ngày.</li></ul>**<span id="01ECF12NKTFH6Q2NH4B1WKSYF9"></span>Ví dụ:**<br />Để cài đặt thời gian xem lại lượt nhấp chuột qua 14 ngày, hãy thêm thông số sau vào liên kết phân bổ chiến dịch nhắm mục tiêu lại: `&af_click_lookback=14d` | Không |
| Bộ định thời xem lại lượt xem hết nhắm mục tiêu lại | <ul><li><Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows">Khung thời gian xem lại lượt xem hết</Anchor> nhắm mục tiêu lại cũng hoạt động tương tự như của chiến dịch thu hút người dùng.</li><li>Khung thời gian này xác định khoảng thời gian tối đa có thể trôi qua sau khi một người dùng xem quảng cáo cho đến khi người dùng đó được phân bổ.</li><li>Thời gian mặc định là 1 ngày.</li><li>Khung thời gian xem lại được đặt bằng</li></ul>`af_viewthrough_lookback={time}`<br /><br /><br /><br />**<span id="01ECF12NKTE8W4K72VATN9RM2X"></span>Ví dụ:**<br />Để đặt thời gian xem lại lượt xem hết trong 5 giờ, hãy thêm thông số sau vào đường dẫn phân bổ chiến dịch nhắm mục tiêu lại: `&af_viewthrough_lookback=5h` | Không |
| Thời gian tương tác lại | <ul><li>**Khung thời gian thu hút lại** có thể được đặt trong giao diện người dùng của đường dẫn phân bổ. Thao tác này sẽ đặt thông số **af\_reengagement\_window** vào đường dẫn phân bổ. Thông số này có thể được thêm theo cách thủ công.</li><li>Thời gian mặc định là 30 ngày.</li><li>Các giá trị thời gian tương tác lại sau có sẵn:</li><li>Giờ: 1- 23 giờ</li><li>Ngày: 1-90 ngày</li><li>Trọn đời: Duy trì cho đến khi người dùng gỡ cài đặt hoặc thực hiện thu hút lại khác, ví dụ: af\_reengagement\_window=lifetime</li></ul>Ví dụ: **af\_reengagement\_window=60d** có nghĩa là các sự kiện được báo cáo trong vòng 60 ngày kể từ ngày thu hút lại được phân bổ cho nguồn truyền thông nhắm mục tiêu lại. | Không |

<div id="retargeting-view-through-lookback-period" />

#### Khoảng thời gian xem lại lượt xem hết nhắm mục tiêu lại

```http
https://app.appsflyer.com/id123456789?pid=remerge_int&af_dp=mydeeplink%3A%2F%2F&
clickid={clickid}&af_siteid={publisher}&idfa={device_id_raw}&sha1_idfa={device_id}
&af_sub1={creative_name}&is_retargeting=true&af_reengagement_window=60d
```

</Accordion>

<div id="retargeting-reports-and-raw-data" />

<Accordion title="Báo cáo nhắm mục tiêu lại và dữ liệu thô">

* Có sẵn báo cáo nhắm mục tiêu lại, tương tự như báo cáo <Anchor target="_blank" href="/marketers/vi/docs/aggregated-and-analytics-reporting-overview">hợp nhất</Anchor> và <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">dữ liệu thô</Anchor> UA, sử dụng các công cụ báo cáo.
* Các sự kiện và phiên trong ứng dụng nhắm mục tiêu lại được <Anchor target="_blank" href="/marketers/vi/docs/resolve-retargeting-double-attribution">phân bổ kép.</Anchor>

**Báo cáo lượt chuyển đổi nhắm mục tiêu lại**

* Báo cáo Chuyển đổi Nhắm lại mục tiêu chứa dữ liệu thô của các lần tương tác lại và phân bổ lại.
* Một số trường có ý nghĩa khác về ngữ cảnh nhắm mục tiêu lại so với các trường được sử dụng trong báo cáo thu hút người dùng.

Diễn giải các báo cáo dữ liệu thô trong ngữ cảnh nhắm mục tiêu lại

| Cột | **Mô tả** |
| --- | --- |
| Tên của sự kiện | <ul><li>Việc điền vào trường phụ thuộc vào loại báo cáo.</li><li>Báo cáo sự kiện trong ứng dụng: Tên sự kiện trong ứng dụng.</li><li>Báo cáo chuyển đổi nhắm mục tiêu lại: thu hút lại hoặc phân bổ lại. **Lưu ý!** Trong trường hợp các giá trị của Data Locker như sau:<ul><li>cài đặt có nghĩa là phân bổ lại</li><li>nhắm mục tiêu lại có nghĩa là thu hút lại</li></ul></li></ul> |
| Kiểu tương tác được phân bổ | Loại tương tác lại:<ul><li>Lượt nhấp</li><li>Lượt hiển thị</li></ul> |
| Thời gian chạm được phân bổ | Thời gian tương tác nhắm lại mục tiêu |
| Thời gian cài đặt | Ứng dụng đầu tiên khởi chạy sau khi tương tác lại hoặc phân bổ lại. |
| Thời gian sự kiện | Thời gian sự kiện xảy ra |
| ID AppsFlyer | <ul><li>Lượt phân bổ lại: ID AppsFlyer mới</li><li>Tương tác lại: Vẫn giữ nguyên</li></ul> |
| Đang nhắm mục tiêu lại | TRUE cho lượt chuyển đổi và sự kiện nhắm mục tiêu lại |
| Là phân bổ chính | TRUE cho lượt chuyển đổi và sự kiện nhắm mục tiêu lại |
| Loại lượt chuyển đổi nhắm mục tiêu lại | Trong tương lai, trường này sẽ bị ngừng hỗ trợ (ngày sẽ được thông báo sau.) Sử dụng conversion\_type và campaign\_type để xác định ngữ cảnh của lượt chuyển đổi.<ul><li>Thu hút lại</li><li>Ghi công lại</li></ul> |
| Loại chuyển đổi | Loại chuyển đổi:<ul><li>Cài đặt</li><li>Lượt cài đặt lại (1)</li><li>Thu hút lại</li><li>Không xác định (2)</li></ul>(1) Nếu conversion\_type= reinstall và campaign\_type=retargeting tương đương với retargeting\_conversion\_type=re-attribution<br /><br />(2) Các sự kiện trong ứng dụng/phiên không được phân bổ cho bất kỳ nguồn truyền thông nào. |
| Loại chiến dịch | Nguồn mang đến người dùng:<ul><li>UA</li><li>Tự nhiên</li><li>Nhắm mục tiêu lại</li><li>Không xác định</li></ul> |
| Xem lại phân bổ | Thời gian xem lại lượt click qua nhắm mục tiêu lại |
| URL gốc | Chứa một trong những yếu tố sau đây:<ul><li>Liên kết nhắm lại mục tiêu</li><li>Dữ liệu liên kết sâu</li><li>Trống cho các SRN</li></ul> |
| Trường người đóng góp | Không có sẵn dành cho thu hút lại |

</Accordion>

<div id="additional-information" />

## Thông tin bổ sung

<div id="probabilistic-modeling" />

<Accordion title="Mô hình xác suất">

Từ ngày 17 tháng 2 năm 2021, Mô hình Xác suất được hỗ trợ trong nhắm mục tiêu lại. Trong trường hợp <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#lưu-ý-đối-với-ứng-dụng-ios">phiên bản iOS từ 14.5 trở lên</Anchor>, sẽ áp dụng các hạn chế. Khung thời gian xem lại sử dụng trong Mô hình Xác suất nhắm mục tiêu lại được AppsFlyer đặt ở trạng thái động và phụ thuộc vào hệ điều hành. 

Xác minh rằng các lượt nhấp chuột được gửi bao gồm <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#các-thông-số-tạo-mô-hình-xác-suất-cho-mạng-quảng-cáo">các thông số Tạo mô hình xác suất</Anchor> cần thiết.

</Accordion>

<div id="app-requirements" />

<Accordion title="Yêu cầu của ứng dụng">

Để chạy chiến dịch nhắm mục tiêu lại, ứng dụng phải đáp ứng các yêu cầu tối thiểu sau.

* iOS
  * Ngoài tích hợp AppsFlyer SDK tiêu chuẩn, bạn phải thêm mã bổ sung vào ủy nhiệm hàm ứng dụng, hãy xem bài viết <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide#liên-kết-sâu-với-onelink">Tích hợp SDK</Anchor> (phần đường dẫn phân bổ).
  * Đối với iOS 9, mã Mở Ứng dụng Liên kết Chung phải được triển khai. <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">Liên kết chung với iOS 9</Anchor>.
* Android:

  * Nếu liên kết sâu mở ra một hoạt động khác với hoạt động chính, hãy xem bài viết <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide#deep-linking">Tích hợp SDK</Anchor> (phần đường dẫn phân bổ).

</Accordion>

<div id="retargeting-limitations" />

<Accordion title="Hạn chế nhắm mục tiêu lại">

* Bắt đầu từ ngày 17 tháng 2 năm 2021, tính năng nhắm mục tiêu lại hỗ trợ Mô hình Xác suất.
* Dữ liệu chi phí chiến dịch để nhắm mục tiêu lại có sẵn trong bảng điều khiển Tổng quan và Nhóm người cùng các báo cáo ở chế độ xem hợp nhất.

</Accordion>

<div id="faq" />

<Accordion title="Câu hỏi thường gặp">

| **Lượt nhấp nhắm mục tiêu lại:**<ul><li>Lượt nhấp nhắm mục tiêu lại bao gồm tất cả người dùng nhắm mục tiêu lại thu hút với đường dẫn phân bổ của AppsFlyer.</li><li>Số lượt nhấp từ SRN hoặc từ <Anchor target="_blank" href="/marketers/vi/docs/measuring-push-notification-re-engagement-campaigns">thông báo đẩy</Anchor> không được tính vào số lượng.</li><li>Một số lượt nhấp dẫn đến lượt cài đặt mới được tính là thu hút người dùng. Điều này xảy ra khi những người không phải là người dùng hoặc người dùng trước đây sau khi hết <Anchor target="_blank" href="/marketers/vi/docs/set-up-re-attribution-window">khung thời gian phân bổ lại</Anchor>, thu hút với liên kết nhắm mục tiêu lại và cài đặt.</li></ul> |
| --- |
| **Khi nào thì thời gian tiếp xúc được phân bổ giống với thời gian cài đặt?**<ul><li>Khi người dùng liên kết chung hoặc liên kết ứng dụng Android thực hiện liên kết sâu, họ được chuyển hướng về ứng dụng mà không thông qua AppsFlyer trước đó.</li><li>Khi ứng dụng khởi chạy và SDK báo cáo một lượt tương tác mới, AppsFlyer tái tạo dữ liệu của lượt nhấp bằng cùng dấu thời gian của lượt khởi chạy. Điều này khiến thời gian của lượt tương tác và khởi chạy giống nhau.</li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model">Mô hình phân bổ của AppsFlyer</Anchor>
> * <Anchor target="_blank" href="/marketers/vi/docs/audiences-guide">Hướng dẫn dành cho Audiences</Anchor>

<div data-zendesk-anchors="retargeting-fundamentals=c%C3%A1c-nguy%C3%AAn-t%E1%BA%AFc-c%C6%A1-b%E1%BA%A3n-v%E1%BB%81-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i h_01HCFJHC85VK0A05X5F69E2WKT=c%C3%A1c-nguy%C3%AAn-t%E1%BA%AFc-c%C6%A1-b%E1%BA%A3n-v%E1%BB%81-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i h_01HCFJHC851PV0VR42H07VQAXF=l%E1%BB%9Di-khuy%C3%AAn h_01HCFJHC85EW8MBQ8MBXBVPF03=reengagement-rules-and-windows inclusion-windows=khung-th%E1%BB%9Di-gian-%C4%91%C6%B0a-v%C3%A0o h_01HCFJHC85FRFJ531Y08DW03Y2=khung-th%E1%BB%9Di-gian-%C4%91%C6%B0a-v%C3%A0o exclusion-windows=khung-th%E1%BB%9Di-gian-lo%E1%BA%A1i-tr%E1%BB%AB h_01HCFJHC85ECS3PJV80D943TVY=khung-th%E1%BB%9Di-gian-lo%E1%BA%A1i-tr%E1%BB%AB example-flow-implementing-the-rules=quy-tr%C3%ACnh-m%E1%BA%ABu-th%E1%BB%B1c-hi%E1%BB%87n-c%C3%A1c-quy-t%E1%BA%AFc h_01HCFJHC8529NW0ABMQ0RB3E8R=quy-tr%C3%ACnh-m%E1%BA%ABu-th%E1%BB%B1c-hi%E1%BB%87n-c%C3%A1c-quy-t%E1%BA%AFc h_01HCFJHC85E1SWGYN0BH603BV9=example-retargeting-scenarios retargeting-operations=ho%E1%BA%A1t-%C4%91%E1%BB%99ng-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i h_01HCFJHC863XPHNWRHJ60JPSRF=ho%E1%BA%A1t-%C4%91%E1%BB%99ng-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i h_01HCFJHC86XNCT5AQP48R9ZDC4=retargeting-settings nonsrn-settings=c%C3%A0i-%C4%91%E1%BA%B7t-m%E1%BA%A1ng-kh%C3%B4ng-ph%E1%BA%A3i-srn h_01HCFJHC865V36R3H58D5PWXYY=c%C3%A0i-%C4%91%E1%BA%B7t-m%E1%BA%A1ng-kh%C3%B4ng-ph%E1%BA%A3i-srn h_01HCFJHC860BS9YJM99G437G24=retargeting-dashboard h_01HCFJHC860Y5HZN66DRNN2Q89=retargeting-attribution-links retargeting-viewthrough-lookback-period=kho%E1%BA%A3ng-th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-l%C6%B0%E1%BB%A3t-xem-h%E1%BA%BFt-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i h_01HCFJHC863CSP03AYBXFSNC37=kho%E1%BA%A3ng-th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-l%C6%B0%E1%BB%A3t-xem-h%E1%BA%BFt-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i h_01HCFJHC86MNFRGYMN776FYHJV=retargeting-reports-and-raw-data additional-information=th%C3%B4ng-tin-b%E1%BB%95-sung h_01HCFJHC86RKKPPMBYEZV4Q3X9=th%C3%B4ng-tin-b%E1%BB%95-sung h_01HCFJHC8690EN19DDX7P24AD0=probabilistic-modeling h_01HCFJHC862E6C46Q7645VJ6CZ=app-requirements h_01HCFJHC86SMKZ1HT5KHQNQS1N=retargeting-limitations h_01HCFJHC86BVSVRNAGJEKZFCJP=faq h_01HE7TPR7928SF2W8ZJS55Y5BG=xem-th%C3%AAm" />
