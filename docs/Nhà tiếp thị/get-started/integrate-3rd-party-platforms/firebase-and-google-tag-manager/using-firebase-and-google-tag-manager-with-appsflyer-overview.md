---
title: Sử dụng Firebase và Google Tag Manager với AppsFlyer—Tổng quan
metadata:
  keywords:
    - GTM
    - Google Tag Manager
    - firebase
    - Advertisers
    - datalayer
    - data layer
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-05-13T19:42:23Z'
  edited_at: '2023-11-09T05:06:32Z'
  id: 210353513
  locale: vi
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/vi/articles/210353513
---
> **Sơ lược:** Về việc gửi các sự kiện được báo cáo qua SDK Firebase tới AppsFlyer bằng Google Tag Manager.

<Image align="center" alt="gtm.png" src="https://files.readme.io/fbb4e0f83baf6f5f7f8dc83e02986ca011f5cb919b9870768da1606798211dcc-360002517245.png" width="289px" />

Việc tích hợp AppsFlyer với Google Tag Manager (GTM) và Firebase cho phép nhà phát triển gửi các sự kiện trong ứng dụng tới Firebase bằng SDK Firebase và gửi các sự kiện tới AppsFlyer qua SDK bằng Google Tag Manager. Điều này tránh việc gửi cùng một sự kiện hai lần.

Các sự kiện gửi bằng GTM được mô hình hóa dựa trên các sự kiện trong ứng dụng AppsFlyer. Tên sự kiện, thông số và cấu trúc giống nhau. Nếu đã có GTM trong ứng dụng của mình, bạn có thể sử dụng GTM để gửi sự kiện tới AppsFlyer rất đơn giản.

Làm theo các bước và hướng dẫn trong hướng dẫn này để gửi sự kiện. 

<div id="considerations" />

### Những điều cần lưu ý

* **Nguồn sự kiện trong dữ liệu thô:** Các sự kiện do GTM tạo ra đặt nguồn thành S2S trong báo cáo dữ liệu thô. Điều này có thể dẫn đến một số nhầm lẫn khi SDK báo cáo các sự kiện.
* **Cập nhật giá trị chuyển đổi SKAdNetwork**: Các sự kiện do GTM tạo ra và báo cáo cho SDK như được mô tả trong hướng dẫn này sẽ khiến SDK cập nhật giá trị chuyển đổi theo cách tương tự như các sự kiện SDK thông thường. Tất cả những gì bạn cần làm là bật và đặt <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide">cài đặt đo lường SKAdNetwork</Anchor> của mình.

<div id="note" />

> 📘 **Lưu ý**
>
> * Hiện tại, tích hợp Google Tag Manager không hỗ trợ gửi các thông số sau tới AppsFlyer:
>   * <Anchor target="_blank" href="/marketers/vi/docs/customer-user-id-field-cuid">Customer user ID</Anchor>
>   * `att`
>   * `os`Lưu ý rằng:
>   * Khi gửi đăng lại sự kiện trong ứng dụng tới SRN, cần có thông số `att`.
>   * Khi gửi đăng lại sự kiện trong ứng dụng tới Meta ads, cần có thông số `att` và `os`.

<div id="prerequisites" />

### Điều kiện tiên quyết

Trước khi có thể bắt đầu gửi sự kiện tới AppsFlyer bằng GTM, bạn cần triển khai SDK GTM trong ứng dụng của mình. Bạn cần:

1. Bạn cần có [tài khoản GTM.](https://www.google.com/analytics/tag-manager/)
2. Bạn cần có thiết lập tích hợp GTM + Firebase cho ứng dụng của mình (hướng dẫn dành cho [Android](https://developers.google.com/tag-manager/android) và [iOS](https://developers.google.com/tag-manager/ios/)).
3. <Anchor target="_blank" href="/marketers/vi/docs/integrate-the-appsflyer-sdk">Tích hợp SDK AppsFlyer</Anchor> nếu bạn chưa làm như vậy.

Khi mọi thứ đã sẵn sàng, hãy tiến hành <Anchor target="_blank" href="/marketers/vi/docs/using-firebase-and-google-tag-manager-with-appsflyer-google-tag-manager-setup">thiết lập GTM</Anchor>.

<div id="see-also" />

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/migrate-from-firebase-dynamic-links-to-appsflyer">Di chuyển từ Liên kết Động Firebase sang AppsFlyer</Anchor>

<div data-zendesk-anchors="considerations=nh%E1%BB%AFng-%C4%91i%E1%BB%81u-c%E1%BA%A7n-l%C6%B0u-%C3%BD h_01HE7SKSCBH47YYFTKBWY3JVSV=nh%E1%BB%AFng-%C4%91i%E1%BB%81u-c%E1%BA%A7n-l%C6%B0u-%C3%BD h_01HE7SKSCBBTTWATRZ87BYRW6G=l%C6%B0u-%C3%BD prerequisites=%C4%91i%E1%BB%81u-ki%E1%BB%87n-ti%C3%AAn-quy%E1%BA%BFt h_01HE7SKSCB9QHA4WEERVSWMF0P=%C4%91i%E1%BB%81u-ki%E1%BB%87n-ti%C3%AAn-quy%E1%BA%BFt h_01HE7SQQG2VJW9179Q77PTZFPH=xem-th%C3%AAm" />
