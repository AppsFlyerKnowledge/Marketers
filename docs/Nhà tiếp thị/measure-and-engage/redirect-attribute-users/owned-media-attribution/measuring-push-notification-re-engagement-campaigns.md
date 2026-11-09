---
title: Đo lường chiến dịch thu hút lại qua thông báo đẩy
metadata:
  keywords:
    - Re-Engagement
    - push
    - notifications
    - Advertisers
    - Developers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2016-01-18T10:03:11Z'
  edited_at: '2023-02-16T10:58:10Z'
  id: 207364076
  locale: vi
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/vi/articles/207364076
---
> **Khái quát:** Đo lường các chiến dịch thông báo đẩy trên cả iOS và Android.

<div id="overview" />

## Tổng quan

AppsFlyer hỗ trợ đo lường các chiến dịch thông báo đẩy từ tất cả các nhà cung cấp dịch vụ đẩy, cũng như các chiến dịch được triển khai trực tiếp trên Firebase Cloud Messaging hoặc Dịch vụ thông báo đẩy của Apple (APNS).

Có 2 cách triển khai tích hợp có thể thực hiện:

* Bằng cách sử dụng các mẫu OneLink (được đề xuất).
* Bằng cách gửi một đối tượng JSON có mã khóa `af` trong tải trọng của thông báo đẩy (kế thừa).

Các lượt chuyển đổi hiển thị trong bảng điều khiển Tổng quan, trong các chế độ xem nhắm mục tiêu lại hoặc thống nhất.

<div id="how-does-it-work" />

## Nó hoạt động như thế nào?

Khi bạn đã hoàn thành các bước trong bài viết này, ứng dụng của bạn sẽ hoạt động như sau:

1. Bạn kích hoạt thông báo đẩy có chứa mẫu OneLink **hoặc** mã khóa `af` trong tải trọng của thông báo đẩy đó.
2. Người dùng ứng dụng nhận được thông báo đẩy và nhấp vào thông báo đó.
3. Ứng dụng tải và SDK AppsFlyer bắt đầu.
4. SDK xử lý tải trọng của thông báo đẩy đã mở ứng dụng.
5. SDK trích xuất và gửi dữ liệu phân bổ tới AppsFlyer.

Trong trường hợp OneLink, nếu OneLink được cấu hình để định tuyến người dùng đến một vị trí cụ thể trong ứng dụng, thì luồng liên kết sâu sẽ được kích hoạt.

<div id="prerequisites" />

## Điều kiện tiên quyết

Trước khi tiếp tục, hãy đảm bảo rằng ứng dụng của bạn đã <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide">tích hợp SDK AppsFlyer</Anchor> **và** có thể nhận thông báo đẩy.

<div id="steps" />

## Các bước

Để thiết lập đo lường thông báo đẩy, phải hoàn thành các bước sau:

1. [Tạo thông báo đẩy](/docs/measuring-push-notification-re-engagement-campaigns#1-creating-the-push-notification) có chứa mã khóa dữ liệu tùy chỉnh với mẫu OneLink **hoặc** mã khóa `af` với đối tượng JSON làm giá trị của thông báo đẩy.
2. [Cấu hình SDK để phân giải mã khóa tùy chỉnh](/docs/measuring-push-notification-re-engagement-campaigns#2-configuring-the-sdk) (do nhà phát triển ứng dụng thực hiện).
3. [Thử nghiệm tích hợp](/docs/measuring-push-notification-re-engagement-campaigns#3-testing-the-integration) bằng cách kích hoạt thông báo đẩy.
4. [Xem hiệu suất chiến dịch thông báo đẩy](/docs/measuring-push-notification-re-engagement-campaigns#4-viewing-push-notification-campaigns-in-the-dashboard) trong bảng điều khiển.

<div id="1-creating-the-push-notification" />

<Accordion title="1. Tạo thông báo đẩy">

Trước tiên, hãy tạo thông báo đẩy chứa dữ liệu phân bổ bằng một trong các phương thức sau.

<div id="note" />

> 📘 **Lưu ý**
>
> Trong phần minh họa sau, chúng tôi sử dụng Firebase làm nhà cung cấp dịch vụ thông báo đẩy. Hướng dẫn phải được áp dụng cho mọi nhà cung cấp dịch vụ đẩy, với những khác biệt rất nhỏ (nếu có). Tham khảo tài liệu của nhà cung cấp dịch vụ thông báo đẩy tương ứng.

<Tabs>
<Tab title="Sử dụng OneLink (được đề xuất)">

<div id="using-onelink-recommended" />

#### **Sử dụng OneLink (được đề xuất)**

Đây là phương thức được đề xuất để tích hợp AppsFlyer với thông báo đẩy.

1. Tạo một <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">liên kết OneLink và thiết lập để nhắm mục tiêu lại.</Anchor>  
   **Lưu ý**: Cả URL rút gọn và đầy đủ của OneLink đều được hỗ trợ.
2. Trong dữ liệu tùy chỉnh thông báo đẩy, hãy thêm OneLink chứa dữ liệu phân bổ mà bạn muốn gửi đến AppsFlyer.

<div id="note-1" />

> 📄 **Ví dụ về Firebase**
>
> Trong Firebase:
>
> <Image align="center" alt="appsflyer-push-custom-data-firebase.png" src="https://files.readme.io/b2a753e8ec88ef0d0e0a71fe222a8ecc4f03786297696d150f185720b8f4e248-49839256715025.png" />

</Tab>

<Tab title="Sử dụng JSON (kế thừa)">

<div id="using-json-legacy" />

<div id="using-json" />

#### **Sử dụng JSON (kế thừa)**

<div id="note-2" />

> 📘 **Lưu ý**
>
> Các tài liệu sau ghi lại phương thức kế thừa của việc tích hợp AppsFlyer với thông báo đẩy và khả dụng cho các mục đích tương thích ngược. Nếu bạn thiết lập một ứng dụng mới, hãy sử dụng [giải pháp dựa trên OneLink được đề xuất](/docs/measuring-push-notification-re-engagement-campaigns#sử-dụng-onelink-được-đề-xuất).

Trong dữ liệu tùy chỉnh của thông báo đẩy, hãy thêm mã khóa tùy chỉnh có tên `af` chứa dữ liệu phân bổ mà bạn muốn gửi đến AppsFlyer ở định dạng JSON. Các thông số phân bổ sau là bắt buộc:

* `PID`
* `is_retargeting`
* `c`

<div id="note-3" />

> 📄 **Ví dụ về Firebase**
>
> Trong Firebase:
>
> <Image align="center" alt="appsflyer-push-custom-data-firebase-json.png" src="https://files.readme.io/138aa2abb70cdb0b8a2c1a4b4ce0a8b83b2faae58e29f3223d5653a4d575012b-49839256716049.png" />

</Tab>
</Tabs>

</Accordion>

<div id="2-configuring-the-sdk" />

<Accordion title="2. Cấu hình SDK">

Công việc này yêu cầu thay đổi mã ứng dụng. Làm theo hướng dẫn về cách cấu hình SDK:

* Khi triển khai giải pháp dựa trên OneLink được đề xuất:
  1. cho nhà phát triển ứng dụng biết tên của mã khóa tùy chỉnh bạn đã thêm vào thông báo. Trong ví dụ này, đó là `af_push_link`.
  2. Gửi cho họ <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications#integrating-appsflyer-with-push-notifications-using-onelink-recommended">các hướng dẫn này</Anchor>.
* Khi triển khai giải pháp cũdựa trên JSON, hãy gửi cho nhà phát triển của bạn <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications#integrating-appsflyer-with-push-notifications-legacy">các hướng dẫn này</Anchor>.

</Accordion>

<div id="3-testing-the-integration" />

<Accordion title="3. Thử nghiệm tích hợp">

Để kiểm tra đảm bảo việc đo lường thông báo đẩy được tích hợp chính xác, chỉ cần kích hoạt thông báo đẩy trong chiến dịch bạn đã thiết lập ở Bước 1.

Nếu mọi thứ được cấu hình đúng cách, SDK sẽ:

1. Lắng nghe thông báo đẩy.
2. Xử lý dữ liệu phân bổ được nhúng trong thông báo đẩy và gửi đến AppsFlyer.
3. Tiếp tục với quy trình liên kết sâu thông thường, nếu việc đo lường thông báo đẩy được triển khai bằng OneLink.

</Accordion>

<div id="4-viewing-push-notification-campaigns-in-the-dashboard" />

<Accordion title="4. Xem các chiến dịch thông báo đẩy trong bảng điều khiển">

Bạn có thể xem dữ liệu bắt nguồn từ thông báo đẩy trong <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide#retargeting-dashboard">bảng điều khiển Nhắm mục tiêu lại</Anchor>.

**Lưu ý**: AppsFlyer loại trùng lặp dữ liệu thông báo đẩy. Có nghĩa là, nếu nhận được trọng tải giống nhau nhiều hơn một lần, thì chỉ tính một lần.

</Accordion>

<div data-zendesk-anchors="overview=t%E1%BB%95ng-quan how-does-it-work=n%C3%B3-ho%E1%BA%A1t-%C4%91%E1%BB%99ng-nh%C6%B0-th%E1%BA%BF-n%C3%A0o prerequisites=%C4%91i%E1%BB%81u-ki%E1%BB%87n-ti%C3%AAn-quy%E1%BA%BFt steps=c%C3%A1c-b%C6%B0%E1%BB%9Bc using-onelink-recommended=s%E1%BB%AD-d%E1%BB%A5ng-onelink-%C4%91%C6%B0%E1%BB%A3c-%C4%91%E1%BB%81-xu%E1%BA%A5t" />
