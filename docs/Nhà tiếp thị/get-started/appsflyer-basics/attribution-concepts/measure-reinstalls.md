---
title: Lượt cài đặt lại
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2022-10-27T07:37:21Z'
  edited_at: '2023-09-07T02:49:05Z'
  id: 10164066030737
  locale: vi
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/vi/articles/10164066030737
---
> **Khái quát**: Lượt cài đặt lại phát sinh khi người dùng cài đặt ứng dụng, gỡ cài đặt ứng dụng và sau đó cài đặt lại. Lượt cài đặt lại dẫn đến một trong các loại phân bổ sau: lượt cài đặt lại không tự nhiên, lượt cài đặt lại tự nhiên hoặc phân bổ lại (nhắm mục tiêu lại). Lượt cài đặt lại giúp tránh việc tính phí nhiều lần cho người dùng gỡ cài đặt rồi cài đặt lại.

<div id="what-is-a-reinstall" />

## Lượt cài đặt lại là gì

Lượt cài đặt lại xảy ra khi người dùng ứng dụng xóa một ứng dụng rồi cài đặt lại ứng dụng đó trong <Anchor target="_blank" href="/marketers/vi/docs/set-up-re-attribution-window#re-attribution-window">khung thời gian phân bổ lại.</Anchor>

Việc cài đặt lại có thể đến từ chiến dịch nhắm mục tiêu lại (phân bổ lại), nguồn tự nhiên hoặc nguồn không tự nhiên.

Các lượt cài đặt lại đến từ nguồn tự nhiên hoặc nguồn không tự nhiên và nằm trong <Anchor target="_blank" href="/marketers/vi/docs/set-up-re-attribution-window#re-attribution-window">khung thời gian phân bổ lại</Anchor>, được gọi là lượt cài đặt lại.

Các lượt cài đặt lại đến từ các chiến dịch nhắm mục tiêu lại được gọi là phân bổ lại.

Chúng khác nhau về cách phân bổ sự kiện cài đặt lại và sự kiện trong ứng dụng.

Nếu một lượt cài đặt xảy ra ngoài <Anchor target="_blank" href="/marketers/vi/docs/set-up-re-attribution-window#re-attribution-window">khung thời gian phân bổ lại</Anchor>, thì lượt cài đặt lại được gọi là <Anchor target="_blank" href="/marketers/vi/docs/set-up-re-attribution-window#new-install">lượt cài đặt mới</Anchor>. Một lượt cài đặt mới được phân bổ cho nguồn truyền thông (hoặc nguồn tự nhiên nếu không ghi nhận tương tác nào) và một khung thời gian phân bổ lại mới sẽ bắt đầu.

Bảng bên dưới cho biết AppsFlyer sẽ gọi những lượt cài đặt lại khác nhau là gì

| Nguồn cài đặt lại | Khung thời gian phân bổ lại có hợp lệ không? | Người dùng có tương tác với chiến dịch nhắm mục tiêu lại trước khi cài đặt lại không? | Người dùng có tương tác với chiến dịch UA trước khi cài đặt lại không? | Vậy được gọi là |
| --- | --- | --- | --- | --- |
| Từ một chiến dịch nhắm mục tiêu lại | Có | Có | Không | Phân bổ lại |
| Từ một nguồn tự nhiên hoặc không tự nhiên | Có | Không | Có hoặc Không | Lượt cài đặt lại |
| Từ một nguồn tự nhiên hoặc không tự nhiên | Không | Không | Có hoặc Không | Lượt cài đặt mới |

<div id="why-are-reinstalls-important" />

## Tại sao lượt cài đặt lại có ý nghĩa quan trọng

Ngoài việc là một dấu hiệu tốt cho thấy người dùng đang quay lại ứng dụng của bạn và các chiến dịch của bạn đang có hiệu quả, thì việc phân bổ lượt cài đặt lại phù hợp cũng rất quan trọng để giúp tránh tính phí nhiều lần cho những người dùng gỡ cài đặt rồi cài đặt lại trong <Anchor target="_blank" href="/marketers/vi/docs/set-up-re-attribution-window#re-attribution-window">khung thời gian phân bổ lại.</Anchor>

Tương tự như vậy, việc phân bổ các sự kiện trong ứng dụng từ lượt cài đặt lại cho nguồn truyền thông ban đầu (cài đặt lần đầu) mang đến cho nhà quảng cáo bức tranh toàn cảnh hơn về cách người dùng tương tác. Nó cũng cho thấy mức độ hiệu quả của các chiến dịch UA và quảng cáo Nhắm mục tiêu lại. Để biết thêm thông tin, hãy xem [các sự kiện trong ứng dụng](/docs/measure-reinstalls#sự-kiện-trong-ứng-dụng) bên dưới.

<div id="reinstall-flow-and-outcome" />

## Luồng cài đặt lại và kết quả

<div id="reinstall" />

<Accordion title="Lượt cài đặt lại">

Sau lần cài đặt ứng dụng lần đầu, người dùng gỡ cài đặt, sau đó cài đặt lại trong <Anchor target="_blank" href="/marketers/vi/docs/set-up-re-attribution-window#re-attribution-window">khung thời gian phân bổ lại</Anchor>. Lượt cài đặt lại có thể đến từ chiến dịch tự nhiên hoặc chiến dịch UA (xem [ví dụ](/docs/measure-reinstalls#examples)).

Trường hợp sau đây sẽ xảy ra:

* Lượt cài đặt KHÔNG được phân bổ - lượt cài đặt không xuất hiện trong bảng điều khiển hay trên dữ liệu
* KHÔNG có đăng lại lượt cài đặt nào được gửi đến bất kỳ nguồn truyền thông nào
* Xem [sự kiện trong ứng dụng](/docs/measure-reinstalls#sự-kiện-trong-ứng-dụng) để được biết thông tin về cách phân bổ sự kiện trong ứng dụng

</Accordion>

<div id="reattribution" />

<Accordion title="Phân bổ lại">

Sau lần cài đặt ứng dụng đầu tiên, người dùng gỡ cài đặt, sau đó tương tác với chiến dịch nhắm mục tiêu lại và cài đặt lại trong <Anchor target="_blank" href="/marketers/vi/docs/set-up-re-attribution-window#re-attribution-window">khung thời gian phân bổ lại</Anchor>.  

Trường hợp sau đây sẽ xảy ra:

* Lượt cài đặt được phân bổ cho nguồn truyền thông nhắm mục tiêu lại trong chế độ xem hợp nhất và nhắm mục tiêu lại của Bảng điều khiển tổng quan
  * Chế độ xem thu hút người dùng không chứa phân bổ lại
* Tất cả các sự kiện trong ứng dụng sau đây được phân bổ cho nguồn truyền thông nhắm mục tiêu lại (xem [các sự kiện trong ứng dụng](/docs/measure-reinstalls#sự-kiện-trong-ứng-dụng) để biết thêm thông tin)
* Đăng lại lượt cài đặt được gửi đến nguồn truyền thông nhắm mục tiêu lại

Để biết thêm thông tin về Nhắm mục tiêu lại cho phân bổ, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide">đây</Anchor>.

</Accordion>

<div id="postreinstall-events-attribution-state" />

<div id="note" />

<div id="post-reinstall-in-app-events" />

## Sự kiện trong ứng dụng

### Tổng quan

<Image align="center" alt="" src="https://files.readme.io/2376efb764026f9cb3c585e8145ae6cf361c3e887c8478ec82709caea63feb1a-10485524792337.jpg" />

Các sự kiện trong ứng dụng do người dùng thực hiện sau khi cài đặt lại sẽ là tự nhiên và được phân bổ hoặc không tự nhiên và được phân bổ hoặc tự nhiên và không được phân bổ tùy thuộc vào trạng thái **phân bổ Sự kiện hậu cài đặt lại** (xem bên dưới).

Một ví dụ về sự kiện trong ứng dụng là người dùng cài đặt lại ứng dụng rồi mua hàng trong ứng dụng.

#### Sự kiện trong ứng dụng và cách chúng được phân bổ

<table><tbody><tr><th>Trạng thái Phân bổ Sự kiện Hậu Cài đặt lại</th><th>Sau khi cài đặt lại</th><th>Sau khi Phân bổ lại</th></tr><tr><td><strong>Được phân bổ là tự nhiên trong ứng dụng</strong></td><td>tự nhiên và không được phân bổ</td><td>Nhắm mục tiêu lại</td></tr><tr><td> <strong>Phân bổ cho lượt cài đặt đầu tiên</strong><span>(1)</span> </td><td>nguồn truyền thông lượt cài đặt đầu tiên</td><td>Nhắm mục tiêu lại <span>(2)</span> </td></tr><tr><td colspan="3"><p><span>(1) Xem các hạn chế bên dưới</span></p><p><span>(2) Trong trường nguồn chính. Nguồn truyền thông lượt cài đặt đầu tiên sẽ được liệt kê trong trường nguồn phụ (<span>bạn sẽ chỉ thấy điều này trong dữ liệu thô).</span></span></p></td></tr></tbody></table>

<div id="unattributed-organic-inapps" />

<Accordion title="Tự nhiên trong ứng dụng không được phân bổ">

Lượt cài đặt lại

* Tất cả các sự kiện trong ứng dụng được tính là tự nhiên hoặc hoàn toàn bị bỏ qua tùy thuộc vào bảng điều khiển.
* Các sự kiện trong ứng dụng sẽ được báo cáo với conversion\_type và campaign\_type là "unknown".
* Ngày được sử dụng để tổng hợp dữ liệu tùy thuộc vào sự kiện:
  * Đối với hầu hết các sự kiện trong ứng dụng bắt nguồn từ SDK, ngày tải xuống ứng dụng được sử dụng để tổng hợp dữ liệu; không phải là ngày cài đặt lại.
  * Đối với các sự kiện doanh thu quảng cáo (af\_ad\_revenue) được gửi bởi trình kết nối SDK, ngày cài đặt lại được sử dụng để tổng hợp dữ liệu.

Phân bổ lại

* Tất cả các sự kiện trong ứng dụng được phân bổ cho nguồn truyền thông nhắm mục tiêu lại

</Accordion>

<div id="attributed-to-the-first-install" />

<Accordion title="Được phân bổ cho lượt cài đặt đầu tiên">

> 🚧 **Điều kiện tiên quyết**
>
> Yêu cầu kích hoạt. Liên hệ với CSM của bạn để thảo luận.

#### Mục đích

Mang đến cho nhà quảng cáo bức tranh toàn cảnh hơn về cách người dùng tương tác. Cho biết mức độ hiệu quả của các chiến dịch UA và quảng cáo Nhắm mục tiêu lại bằng cách phân bổ các sự kiện trong ứng dụng cho nguồn ban đầu thay vì tự nhiên.

#### Lượt cài đặt lại

* Tất cả các sự kiện trong ứng dụng được tạo từ lượt cài đặt lại đều được phân bổ cho lượt cài đặt ban đầu (1)

#### Phân bổ lại

* Tất cả các sự kiện trong ứng dụng được phân bổ cho quảng cáo nhắm mục tiêu lại trong nguồn chính và lượt cài đặt ban đầu trong nguồn phụ. (2)

(1) Xem các [hạn chế bên dưới.](/docs/measure-reinstalls#limitations)

(2) Bạn sẽ chỉ thấy điều này trong dữ liệu thô.

<div id="note-1" />

#### Lưu ý

Dữ liệu KPI tự nhiên trong bảng điều khiển có thể hiển thị giá trị thấp hơn khi **Post Reinstall Events Attribution** được đặt thành **Attributed to the first install** vì một vài trong số đó hiện có thể được phân bổ cho nguồn truyền thông không tự nhiên.

</Accordion>

<div id="examples" />

<Accordion title="Ví dụ">

<div id="confirm-inapps-are-attributed-to-the-original-install" />

<div id="examples-for-first-install-mode-attribution" />

#### Với **Attributed to the first install** được bật.

**Ví dụ 1**

Một người dùng cài đặt ứng dụng (ngày 0), mua hàng với giá 10 USD rồi gỡ cài đặt ứng dụng.

Ngày hôm sau (ngày 1), người dùng cài đặt lại ứng dụng và có giao dịch mua 5 USD.

<Image align="center" alt="Reinstall_1.jpg" src="https://files.readme.io/7e8eccb3a6873b42a1d8503c0f027386728adb2eecbe457451d2e37c0a7b6774-10225445609873.jpg" />

Vì người dùng đã có giao dịch mua trước khi cài đặt lại nên sẽ không cộng thêm một người dùng duy nhất nữa.

| Nguồn truyền thông | người dùng | Af\_purchase:<br /><br />Người dùng duy nhất<br /><br />Ngày 0 | Af\_purchase:<br /><br />Người dùng duy nhất<br /><br />Ngày 1 (tích lũy) | Doanh thu<br /><br />Ngày 0 | Doanh thu<br /><br />Ngày 1 (tích lũy) |
| --- | --- | --- | --- | --- | --- |
| Nguồn\_truyền\_thông\_A | 1 | 1 | 1 | 10 USD | 15 USD |

Chúng ta sẽ thấy doanh thu tăng ở cùng một `device_identifier`.

| Appsflyer\_id | Mã định danh của thiết bị | Nguồn truyền thông | Tên của sự kiện | Ngày của sự kiện |
| --- | --- | --- | --- | --- |
| 111 | XXX | nguồn\_truyền\_thông\_A | lượt cài đặt | ngày 0 |
| 111 | XXX | nguồn\_truyền\_thông\_A | af\_purchase | ngày 0 |
| 222 | XXX | tự nhiên | lượt cài đặt lại | ngày 1 |
| 222 | XXX | nguồn\_truyền\_thông\_A | af\_purchase | ngày 1 |

**Ví dụ 2**

Một người dùng cài đặt ứng dụng (ngày 0), mua hàng rồi gỡ cài đặt ứng dụng.

Ngày hôm sau (ngày 1), người dùng cài đặt lại ứng dụng từ chiến dịch UA và mua hàng.

| Nguồn truyền thông | Tên của sự kiện | Ngày của sự kiện | Phân bổ lượt cài đặt lại | Phân bổ sự kiện trong ứng dụng |
| --- | --- | --- | --- | --- |
| nguồn\_truyền\_thông\_A | lượt cài đặt | ngày 0 | nguồn\_truyền\_thông\_A |  |
| nguồn\_truyền\_thông\_A | af\_purchase | ngày 0 |  | nguồn\_truyền\_thông\_A |
| nguồn\_truyền\_thông\_B | lượt cài đặt lại | ngày 1 | nguồn\_truyền\_thông\_B |  |
| nguồn\_truyền\_thông\_B | af\_purchase | ngày 1 |  | nguồn\_truyền\_thông\_A |

</Accordion>

<div id="limitations" />

<Accordion title="Điểm hạn chế">

* Chỉ những người dùng đã đồng ý chia sẻ mã định danh thiết bị của họ (chẳng hạn như IDFA hoặc GAID) với ứng dụng cho cả lượt cài đặt và cài đặt lại mới có các sự kiện trong ứng dụng được phân bổ cho lượt cài đặt ban đầu
  * Mã định danh thiết bị trong lần cài đặt đầu tiên và lần cài đặt lại phải khớp nhau
* Quá trình cài đặt lại phải diễn ra trong <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide#reengagement-rules-and-windows">khoảng thời gian phân bổ lại</Anchor> của lượt cài đặt được ghi nhận gần đây nhất.
* Các sự kiện doanh thu quảng cáo được phân bổ là tự nhiên
* Mỗi lượt cài đặt và cài đặt lại sẽ vẫn có `appsflyer_id` riêng
* Bảng điều khiển không phân biệt giữa sự kiện trong ứng dụng sau khi cài đặt hoặc cài đặt lại
  * Có thể thấy điều này qua dữ liệu thô

</Accordion>

<div id="how-does-the-data-appear-in-the-appsflyer-dashboards" />

## Dữ liệu xuất hiện như thế nào trong bảng điều khiển AppsFlyer

<table><tbody><tr><th colspan="2"> </th><th>Lượt cài đặt lại không tự nhiên</th><th>Lượt cài đặt lại tự nhiên </th><th>Phân bổ lại</th></tr><tr><td colspan="2">Lượt cài đặt lại đó</td><td>Không thấy</td><td>Không thấy</td><td><span>Nguồn truyền thông nhắm mục tiêu lại\*</span></td></tr><tr><td rowspan="2">Phân bổ sự kiện trong ứng dụng trong tương lai</td><td>Post Reinstall Events được đặt thành <strong>Attributed as organic in-apps</strong> </td><td>Tự nhiên và không được phân bổ</td><td>Tự nhiên và không được phân bổ</td><td><span>Nguồn truyền thông nhắm mục tiêu lại</span></td></tr><tr><td>Post Reinstall Events được đặt thành <strong>Attributed to the first install</strong> </td><td>Nguồn truyền thông đầu tiên</td><td>Nguồn truyền thông đầu tiên</td><td>Chiến dịch nhắm mục tiêu lại</td></tr><tr><td colspan="5">\*Chỉ trong bảng điều khiển tổng quan.</td></tr></tbody></table>

<div id="reinstalls-raw-data-reports" />

## Báo cáo dữ liệu thô về lượt cài đặt lại

<div id="prerequisites" />

> 🚧 **Điều kiện tiên quyết**
>
> Yêu cầu kích hoạt. Liên hệ với CSM của bạn để thảo luận về điều này.

* <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQtlerXtCVImurv-JyuG7JMPvLN6p2w79pmbMNBx6WBnLwnYq5bUqXiUuoy2l_UTzEjIr8UkDdclRxf/pub?output=csv">Cài đặt lại báo cáo mẫu dưới dạng tệp CSV</Anchor>

<div id="how-the-install-and-in-app-events-are-attributed" />

#### Cách phân bổ lượt cài đặt và sự kiện trong ứng dụng

<table><tbody><tr><th colspan="2"> </th><th>Lượt cài đặt lại không tự nhiên</th><th>Lượt cài đặt lại tự nhiên </th><th>Phân bổ lại</th><th>Lượt cài đặt không tự nhiên</th><th>Lượt cài đặt tự nhiên</th></tr><tr><td colspan="2">Được phân bổ cho </td><td>Chiến dịch UA</td><td>Tự nhiên</td><td>Chiến dịch nhắm mục tiêu lại</td><td>Chiến dịch UA</td><td>Tự nhiên</td></tr><tr><td rowspan="2">Phân bổ sự kiện trong tương lai</td><td>Post Reinstall Events được đặt thành <strong>Attributed as organic in-apps</strong> </td><td>Tự nhiên</td><td>Tự nhiên</td><td>Chiến dịch nhắm mục tiêu lại</td><td>Chiến dịch UA</td><td>Tự nhiên</td></tr><tr><td>Post Reinstall Events được đặt thành <strong>Attributed to the first install</strong> </td><td>Lượt cài đặt đầu tiên</td><td>Lượt cài đặt đầu tiên</td><td>Chiến dịch nhắm mục tiêu lại</td><td>Chiến dịch UA</td><td>Tự nhiên</td></tr></tbody></table>

<div id="availability-of-reinstall-reports" />

### Tính sẵn có của các báo cáo về lượt cài đặt lại

* Các báo cáo dữ liệu thô về lượt cài đặt lại sẽ có sẵn bằng cách sử dụng các công cụ tạo xuất được trình bày chi tiết trong bảng sau.
* Các báo cáo sẽ có cùng cấu trúc và được điền theo cách tương tự với báo cáo về lượt cài đặt trong đó:
  * Các trường **Media source** được điền bằng cách sử dụng nguồn truyền thông đã mang lại lượt cài đặt lại hoặc tự nhiên.
  * **Install time**: Được hiểu ở đây là thời gian cài đặt lại, nghĩa là thời gian mở ứng dụng đầu tiên sau khi cài đặt lại
  * **Tên sự kiện:** *Cài đặt lại*

| Phương thức tạo xuất báo cáo | Lượt cài đặt lại không tự nhiên | Lượt cài đặt lại tự nhiên |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">Xuất dữ liệu</Anchor> | ✓ | ✓ |
| <Anchor target="_blank" href="/marketers/vi/docs/pull-api-aggregate-data">API Pull</Anchor> | ✓ | ✓ |
| <Anchor target="_blank" href="/marketers/vi/docs/data-locker-for-marketers">Data Locker</Anchor> | ✓ | ✓ |
| API Push | ✓ | ✓ |

<div data-zendesk-anchors="what-is-a-reinstall=l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-l%E1%BA%A1i-l%C3%A0-g%C3%AC 01H7SZVZPGHBQ7VM8TMWRD3CE4=l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-l%E1%BA%A1i-l%C3%A0-g%C3%AC why-are-reinstalls-important=t%E1%BA%A1i-sao-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-l%E1%BA%A1i-c%C3%B3-%C3%BD-ngh%C4%A9a-quan-tr%E1%BB%8Dng 01H7SZVZPG6T2AW9B3EMT29AQQ=t%E1%BA%A1i-sao-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-l%E1%BA%A1i-c%C3%B3-%C3%BD-ngh%C4%A9a-quan-tr%E1%BB%8Dng reinstall-flow-and-outcome=lu%E1%BB%93ng-c%C3%A0i-%C4%91%E1%BA%B7t-l%E1%BA%A1i-v%C3%A0-k%E1%BA%BFt-qu%E1%BA%A3 01H7SZVZPGVQCNCQ7TCZMYM33T=lu%E1%BB%93ng-c%C3%A0i-%C4%91%E1%BA%B7t-l%E1%BA%A1i-v%C3%A0-k%E1%BA%BFt-qu%E1%BA%A3 01H7SZVZPGCDP3GRK1BWZ04MR6=reinstall 01H7SZVZPG8WNTK30YXNZ44VTS=reattribution inapp-events=s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng 01H7SZVZPGBYRWZGAZRT36EFGH=s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng overview=t%E1%BB%95ng-quan 01H7SZVZPGK7X1NXW467CZP1KJ=t%E1%BB%95ng-quan inapp-events-and-how-they-are-attributed=s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng-v%C3%A0-c%C3%A1ch-ch%C3%BAng-%C4%91%C6%B0%E1%BB%A3c-ph%C3%A2n-b%E1%BB%95 01H7SZVZPHW7E5WV9C643BG6YB=s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng-v%C3%A0-c%C3%A1ch-ch%C3%BAng-%C4%91%C6%B0%E1%BB%A3c-ph%C3%A2n-b%E1%BB%95 01H7SZVZPH4AE1PZK8V5JG6C6X=unattributed-organic-inapps 01H7SZVZPH7KPM7T42GHZ7N69S=attributed-to-the-first-install 01H7SZVZPHBQ7E3R107EB2KXES=%C4%91i%E1%BB%81u-ki%E1%BB%87n-ti%C3%AAn-quy%E1%BA%BFt purpose=m%E1%BB%A5c-%C4%91%C3%ADch 01H7SZVZPHXBX6J2APBXS30CPX=m%E1%BB%A5c-%C4%91%C3%ADch reinstall::7f2d499b=l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-l%E1%BA%A1i 01H7SZVZPHRJ9WPW3TCYECK50W=l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-l%E1%BA%A1i reattribution::bbb1aabb=ph%C3%A2n-b%E1%BB%95-l%E1%BA%A1i 01H7SZVZPHZFY9ZDEQYP967C2D=ph%C3%A2n-b%E1%BB%95-l%E1%BA%A1i 01H7SZVZPH5YGSMPGW7NPKXJAF=l%C6%B0u-%C3%BD 01H7SZVZPHF3R44DTHCD9QHPR8=examples with-attributed-to-the-first-install-enabled=v%E1%BB%9Bi-attributed-to-the-first-install-%C4%91%C6%B0%E1%BB%A3c-b%E1%BA%ADt 01H7SZVZPHH3DS9J4VRD70VTX6=v%E1%BB%9Bi-attributed-to-the-first-install-%C4%91%C6%B0%E1%BB%A3c-b%E1%BA%ADt 01H7SZVZPH8MSBQ92XWFK0HWGQ=limitations how-does-the-data-appear-in-the-appsflyer-dashboards=d%E1%BB%AF-li%E1%BB%87u-xu%E1%BA%A5t-hi%E1%BB%87n-nh%C6%B0-th%E1%BA%BF-n%C3%A0o-trong-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-appsflyer 01H7SZVZPHHQS4NHEDATD7ZP9V=d%E1%BB%AF-li%E1%BB%87u-xu%E1%BA%A5t-hi%E1%BB%87n-nh%C6%B0-th%E1%BA%BF-n%C3%A0o-trong-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-appsflyer reinstalls-raw-data-reports=b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-v%E1%BB%81-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-l%E1%BA%A1i 01H7SZVZPHPWN8REBQ5CWVFNJT=b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-v%E1%BB%81-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-l%E1%BA%A1i 01H7SZVZPHCVDPDDYD6HHNFMMK=%C4%91i%E1%BB%81u-ki%E1%BB%87n-ti%C3%AAn-quy%E1%BA%BFt-1 how-the-install-and-inapp-events-are-attributed=c%C3%A1ch-ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-v%C3%A0-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng 01H7SZVZPHQT8XS3ZBA4W682GB=c%C3%A1ch-ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-v%C3%A0-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng availability-of-reinstall-reports=t%C3%ADnh-s%E1%BA%B5n-c%C3%B3-c%E1%BB%A7a-c%C3%A1c-b%C3%A1o-c%C3%A1o-v%E1%BB%81-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-l%E1%BA%A1i 01H7SZVZPH6NY7FMG9YHDBB95R=t%C3%ADnh-s%E1%BA%B5n-c%C3%B3-c%E1%BB%A7a-c%C3%A1c-b%C3%A1o-c%C3%A1o-v%E1%BB%81-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-l%E1%BA%A1i" />
