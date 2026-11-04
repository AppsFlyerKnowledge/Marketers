---
title: 'Khắc phục sự cố đăng lại cho các nhà quảng cáo '
metadata:
  keywords:
    - Postback
    - Partner
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
  created_at: '2023-04-04T07:09:26Z'
  edited_at: '2023-11-30T14:23:33Z'
  id: 14272573202833
  locale: vi
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/vi/articles/14272573202833
---
> **Khái quát:** Tìm các nguyên nhân và giải pháp chính cho lý do tại sao đối tác của bạn không nhận được các bài đăng lại như mong đợi. Kiểm tra kỹ lưỡng từng chủ đề bên dưới và xem liệu chúng có phải là nguyên nhân hay không.

<div id="1703758710.321359" />

<div id="check-the-integration-toggles" />

## Kiểm tra các nút chuyển đổi tích hợp

Các nút chuyển đổi khác nhau kiểm soát các phần khác nhau của quy trình tích hợp. Trạng thái của nút chuyển đổi có thể gây ra sự cố không nhận được bài đăng lại. 

<div id="the-activate-partner-toggle-was-turned-off" />

<Accordion title="Tắt nút Activate partner">

Khi tắt nút <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">**Activate partner**</Anchor>, dữ liệu chuyển đổi sẽ không được phân bổ và bài đăng lại không được gửi cho đối tác.

![integration_turned_off.png](https://files.readme.io/d43b4f465749e343d9523e90e87e43b77a85cdd920f0c0770a94bcb7a585d920-14979273403793.png)

**Để kích hoạt tích hợp:**

1. Trong phần **Configuration** trên AppsFlyer truy cập **Active Integrations**
2. Nhấp vào biểu tượng Manage integration của đối tác.
3. Từ thẻ **Integration**, bật nút **Activate partner**.

Trong trường hợp khác, nếu nút <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">**Activate partner**</Anchor> hiện đang bật trong thời gian diễn ra sự kiện, thì trước đó nút này đã bị tắt. Sử dụng Audit log để kiểm tra và xem liệu quy trình tích hợp đối tác có hoạt động vào thời điểm diễn ra sự kiện hay không:

* Đi đến email người dùng của bạn (trên cùng bên phải) > **Security center** > **Audit log**.

</Accordion>

<div id="the-inapp-event-postbacks-toggle-was-turned-off" />

<div id="1703760110.503549" />

<Accordion title="Nút In-app event postbacks đã bị tắt">

Nút **<Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration">In-app event postbacks</Anchor>** đã bị tắt hoặc có thể đã bị tắt trong thời gian diễn ra sự kiện. Điều này có nghĩa là không có bài đăng lại nào được gửi.

**Cách bật nút In-app event postbacks:**

1. Trong phần **Configuration** trên AppsFlyer truy cập **Active Integrations**
2. Nhấp vào biểu tượng Manage integration của đối tác.
3. Trên thẻ **Integration**, cuộn xuống **In-app events postbacks** để bật nút lên.  

   ![integration-in_app_event_postbacks_toggle.png](https://files.readme.io/20dadaa71b8b54c4512e74a925e66cec9da5e8138bb28a545c5452eef2d38304-14627453566737.png)

</Accordion>

<div id="check-the-event-configuration" />

## Kiểm tra cấu hình sự kiện

Sự kiện có thể được định cấu hình theo cách khiến một số bài đăng lại nhất định không được gửi.

<div id="the-event-wasnt-configured" />

<Accordion title="Sự kiện không được định cấu hình">

Kiểm tra xem sự kiện có nằm trong danh sách các sự kiện trong ứng dụng đã định cấu hình hay không. Nếu không thấy trong danh sách, bài đăng lại sẽ không được gửi.

[![list_of_in_app_events.png](https://files.readme.io/c2b3a3a87c4a1f39a3fa3acc28c736fd69d8d6d21d4b9ed5d3c84e8df0d3bf39-14979245450641.png)](https://files.readme.io/c2b3a3a87c4a1f39a3fa3acc28c736fd69d8d6d21d4b9ed5d3c84e8df0d3bf39-14979245450641.png)

1. Trong phần **Configuration** trên AppsFlyer truy cập **Active Integrations**.
2. Nhấp vào biểu tượng Manage integration của đối tác.
3. Từ thẻ **Integration**, cuộn xuống nút **In-app event postbacks** và xem liệu tên sự kiện có xuất hiện không.

</Accordion>

<div id="the-event-was-configured-incorrectly" />

<Accordion title="Sự kiện được cấu hình không chính xác">

Kiểm tra xem <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#ánh-xạ-sự-kiện">event mapping</Anchor> có chính xác không. Đảm bảo **sự kiện** **AppsFlyer** (tên của sự kiện mà AppsFlyer nhận được từ ứng dụng di động của bạn hoặc qua S2S) khớp với **tên được ánh xạ tới tên đối tác** (tên sự kiện chính xác được đối tác sử dụng). 

[![in_app_event_postback_mapping_2.png](https://files.readme.io/b0b4935f2b40e1c81961fbbecd159ca054816be2c58248624eed177ec17f9c20-14979366291857.png)](https://files.readme.io/b0b4935f2b40e1c81961fbbecd159ca054816be2c58248624eed177ec17f9c20-14979366291857.png)

</Accordion>

<div id="the-event-was-configured-correctly-but-with-a-condition" />

<Accordion title="Sự kiện được cấu hình chính xác nhưng với một điều kiện">

Nếu một điều kiện được xác định cho sự kiện, bài đăng lại sẽ được gửi theo điều kiện đó. Kiểm tra xem có điều kiện nào giới hạn việc gửi bài đăng lại không.

[![in_app_event_condition__1_.png](https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png)](https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png)

</Accordion>

<div id="the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner" />

<Accordion title="Sự kiện được định cấu hình để chỉ gửi bài đăng lại cho đối tác được phân bổ">

Kiểm tra xem liệu cấu hình sự kiện trong ứng dụng được đặt để gửi các bài đăng lại tới <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#tùy-chọn-để-gửi-đăng-lại">**chỉ Đối tác này** hay tới **Tất cả các nguồn truyền thông, bao gồm cả nguồn tự nhiên**</Anchor>. Nếu cấu hình được đặt thành **This partner only** thì chỉ đối tác được phân bổ mới nhận được bài đăng lại.

[![in_app_event_sending_options.png](https://files.readme.io/3fd96860a0a8842dd183a29e9f9dd947b5c9082e2069c0aa74bd8eb781302908-14979359951761.png)](https://files.readme.io/3fd96860a0a8842dd183a29e9f9dd947b5c9082e2069c0aa74bd8eb781302908-14979359951761.png)

</Accordion>

<div id="the-event-occurred-outside-of-the-configuration-window" />

<Accordion title="Sự kiện đã xảy ra bên ngoài khung thời gian cấu hình">

Bài đăng lại được gửi theo cài đặt <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#khung-thời-gian-đăng-lại-sự-kiện-trong-ứng-dụng">postback window</Anchor>. Các bài đăng lại cho sự kiện sau khoảng thời gian này đã được gửi cho đối tác dù sự kiện vẫn được ghi lại trong AppsFlyer.

![in_app_event_postback_window.png](https://files.readme.io/21cae7825d557c1ee89c890ec64c922cb36e31be882850a26bfdc4e5595773f0-14661845664401.png)

Lưu ý rằng đối với <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns">các SRN</Anchor>, bài đăng lại sự kiện trong ứng dụng được gửi trong khoảng thời gian <Anchor target="_blank" href="/marketers/vi/docs/user-level-data-retention#partner-data-retention-periods">lưu giữ dữ liệu của đối tác</Anchor>.

</Accordion>

<div id="the-attribution-link-was-configured-not-to-send-postbacks-for-installs" />

<Accordion title="Đường dẫn phân bổ được định cấu hình để không gửi bài đăng lại cho lượt cài đặt">

Nếu đường dẫn phân bổ bao gồm tham số `af_installpostback=false`, các lượt cài đặt được ghi lại nhưng các bài đăng lại không được gửi cho đối tác.

**Cách xem đường dẫn phân bổ:**

* Trong phần **Configuration** > **Active integrations** trên AppsFlyer, đi đến thẻ **Attribution link** và cuộn xuống để xem đường dẫn phân bổ của bạn.

</Accordion>

<div id="privacy-restrictions" />

## Hạn chế về quyền riêng tư

Trong các trường hợp sau, AppsFlyer không gửi bài đăng lại do các hạn chế về quyền riêng tư.

<div id="the-partner-didnt-set-up-advanced-privacy" />

<Accordion title="Đối tác không hỗ trợ Quyền riêng tư nâng cao hoặc chưa thiết lập tính năng này">

Nếu bật <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework#partner-advanced-privacy-switch">Advanced Privacy</Anchor> nhưng bên đối tác không định cấu hình Quyền riêng tư nâng cao hoặc không hỗ trợ Quyền riêng tư nâng cao, họ sẽ không nhận được <Anchor target="_blank" href="/partners/vi/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks">các bài đăng lại tổng hợp về Quyền riêng tư nâng cao</Anchor>. 

![partner_not_supporting_ap_postbacks.png](https://files.readme.io/1d8784e8994eba5c403ac706673490b91b7b34ed4d5dbea8c3fe58f227d382c5-15140294126353.png)

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms" />

<Accordion title="Hạn chế nguồn truyền thông trên các nền tảng của bên thứ ba">

<Anchor target="_blank" href="/marketers/vi/docs/discrepancies-between-appsflyer-and-third-party-platforms#postback-restrictions-on-third-party-platforms">Một số nguồn truyền thông</Anchor> hạn chế chia sẻ dữ liệu với các bên thứ ba. AppsFlyer không cho phép chia sẻ dữ liệu ở mức người dùng có được thông qua các nguồn truyền thông này với bất kỳ nền tảng hoặc dịch vụ bên thứ ba nào. Do đó, tất cả các lượt cài đặt từ những nguồn truyền thông đó sẽ được gửi dưới dạng tự nhiên. Lưu ý rằng Meta ads không cho phép chia sẻ bất kỳ dữ liệu nào với các nền tảng bên thứ ba.

</Accordion>

<div id="the-sdk-was-set-not-to-share-information-with-the-partner" />

<Accordion title="SDK đã được đặt để không chia sẻ thông tin với đối tác">

Bộ lọc chia sẻ đã được triển khai trong SDK để ngăn đối tác nhận thông tin. Bộ lọc này có thể được kích hoạt theo yêu cầu lựa chọn không tham gia rõ ràng của người dùng hoặc tại bất kỳ thời điểm nào khác trong vòng đời của ứng dụng.

Để biết thêm thông tin, hãy xem: <Anchor target="_blank" href="/marketers/vi/docs/apply-privacy-preserving-sdk-methods#prevent-data-sharing-with-third-parties">Ngăn chặn chia sẻ dữ liệu với bên thứ ba</Anchor> và <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">setSharingFilterForPartners</Anchor>.

</Accordion>

<div id="miscellaneous" />

## Các nội dung khác

<div id="the-postback-was-sent-but-doesnt-show-on-the-partners-platform" />

<Accordion title="Bài đăng lại đã được gửi nhưng không hiển thị trên nền tảng của đối tác">

Trong một số trường hợp, mặc dù AppsFlyer đã gửi các bài đăng lại cho một đối tác nhưng đối tác đó không nhìn thấy được. Nếu gặp trường hợp như vậy, liên hệ với đối tác.

**Cách xem liệu bài đăng lại có được gửi từ AppsFlyer hay không:**

1. Trong phần **Reports** trên AppsFlyer hãy đi đến **Raw Data Export**.
2. Xem báo cáo có liên quan trong phần **Postbacks** (Số lượt cài đặt, Sự kiện trong ứng dụng, Chuyển đổi nhắm lại mục tiêu, Nhắm lại mục tiêu sự kiện trong ứng dụng).

[![postback_reports.JPG](https://files.readme.io/21f7ead0f04cf8b67735476348245c5849b638701946236cf649adfa69699df6-14981466637457.png)](https://files.readme.io/21f7ead0f04cf8b67735476348245c5849b638701946236cf649adfa69699df6-14981466637457.png)

</Accordion>

<div id="the-event-didnt-occur" />

<Accordion title="Sự kiện đã không xảy ra hoặc không được gửi đến AppsFlyer">

Bạn có thể tìm thấy tất cả các sự kiện đã xảy ra trên <Anchor target="_blank" href="/marketers/vi/docs/activity-dashboard">**Activity** dashboard</Anchor> và trong <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview?query=raw%20data%20reports">Raw data reports</Anchor>. Sự kiện không hiển thị ở đó nghĩa là sự kiện đó đã không xảy ra hoặc không được gửi đến AppsFlyer.

Đó có thể là sự kiện chưa được xác định trong SDK. Trong trường hợp này, bạn sẽ không thấy sự kiện đó trên nền tảng. Kiểm tra cấu hình SDK.  <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide#ghi-nhận-sự-kiện-trong-ứng-dụng">được xác định trong SDK</Anchor>.

Nếu bạn cho rằng sự kiện đã xảy ra, hãy kiểm tra bên dưới cách nhận biết liệu sự kiện đó xuất hiện trong Bảng điều khiển hoạt động hay không hoặc tạo báo cáo Dữ liệu thô và tìm kiếm sự kiện đó ở đó.

**Cách xem Bảng điều khiển hoạt động:**

* Trong **Dashboards** trên AppsFlyer hãy đi đến **Activity** và chọn đối tác và phạm vi ngày.

**Cách tạo báo cáo dữ liệu thô:**

1. Trong phần **Reports** trên AppsFlyer đi đến **Raw Data Export**.
2. Nhấp vào **Create report**.
3. Chọn báo cáo có liên quan.
4. Chọn phạm vi ngày và bất kỳ trường nào cần thiết, rồi nhấp vào **Create**.
5. Tải xuống báo cáo và tìm kiếm sự kiện ở đó.

</Accordion>

<div id="differences-in-time-zones" />

<Accordion title="Chênh lệch về múi giờ">

Có thể có sự khác biệt trong việc nhận bài đăng lại do chênh lệch múi giờ giữa nền tảng AppsFlyer và nền tảng của đối tác. Bảng điều khiển và báo cáo của AppsFlyer hiển thị theo múi giờ đã chọn.

**Cách xem múi giờ trên ứng dụng trong AppsFlyer:**

1. Trong phần **Configuration** trên AppsFlyer, đi đến **App settings**.
2. Xem múi giờ của ứng dụng dưới phần **Localization**.

</Accordion>

<div id="srns-missing-advertising-ids-idfagaid" />

<Accordion title="Các SRN thiếu ID quảng cáo (IDFA/GAID)">

Có một số <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid">trường hợp cụ thể đối với các SRN</Anchor> mà trong đó AppsFlyer không gửi bài đăng lại cho lượt cài đặt, lượt mở ứng dụng hoặc sự kiện trong ứng dụng.

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms::40092c14" />

<div id="advanced-privacy-postbacks" />

<Accordion title="Hạn chế nguồn truyền thông trên các nền tảng của bên thứ ba">

<Anchor target="_blank" href="/marketers/vi/docs/discrepancies-between-appsflyer-and-third-party-platforms#postback-restrictions-on-third-party-platforms">Một số nguồn truyền thông</Anchor> hạn chế chia sẻ dữ liệu với các bên thứ ba. AppsFlyer không thể chia sẻ dữ liệu ở cấp độ người dùng có được thông qua các nguồn truyền thông này với nền tảng hoặc dịch vụ của bên thứ ba. Do đó, tất cả các lượt cài đặt từ những nguồn truyền thông đó sẽ được gửi dưới dạng tự nhiên. Lưu ý rằng quảng cáo Meta không chia sẻ bất kỳ dữ liệu nào với nền tảng của bên thứ ba.

</Accordion>

<div id="see-also" />

> 📄 **Xem thêm**
>
> <Anchor target="_blank" href="/partners/vi/docs/postback-troubleshooting-for-ad-networks">Khắc phục sự cố đăng lại cho mạng quảng cáo</Anchor>

<div data-zendesk-anchors="activation-toggles=ki%E1%BB%83m-tra-c%C3%A1c-n%C3%BAt-chuy%E1%BB%83n-%C4%91%E1%BB%95i-t%C3%ADch-h%E1%BB%A3p h_01H9FT385FY1QJC6M2YVMZF2NC=ki%E1%BB%83m-tra-c%C3%A1c-n%C3%BAt-chuy%E1%BB%83n-%C4%91%E1%BB%95i-t%C3%ADch-h%E1%BB%A3p h_01H9FT385FJ0W62NB6FBB6ASKP=the-activate-partner-toggle-was-turned-off h_01H9FT385FKK7VQ293HH9RANBP=the-inapp-event-postbacks-toggle-was-turned-off event-configuration-issues=ki%E1%BB%83m-tra-c%E1%BA%A5u-h%C3%ACnh-s%E1%BB%B1-ki%E1%BB%87n h_01H9FT385FW71JV2KKZ22TP6TN=ki%E1%BB%83m-tra-c%E1%BA%A5u-h%C3%ACnh-s%E1%BB%B1-ki%E1%BB%87n h_01H9FT385FHFX4PNRQVRXX8A5X=the-event-wasnt-configured h_01H9FT385FE4GCP9D5XCNZ1FAR=the-event-was-configured-incorrectly h_01H9FT385FTT97PJ9NN09K0X9F=the-event-was-configured-correctly-but-with-a-condition h_01H9FT385FDEC21CAZ7V9BBT7M=the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner h_01H9FT385G8HSVJWWGKSRKT381=the-event-occurred-outside-of-the-configuration-window h_01H9FT385GDDV1D6X69JQWPN02=the-attribution-link-was-configured-not-to-send-postbacks-for-installs privacy-restrictions=h%E1%BA%A1n-ch%E1%BA%BF-v%E1%BB%81-quy%E1%BB%81n-ri%C3%AAng-t%C6%B0 h_01H9FT385G84E2A1J64VWG8H4Z=h%E1%BA%A1n-ch%E1%BA%BF-v%E1%BB%81-quy%E1%BB%81n-ri%C3%AAng-t%C6%B0 h_01H9FT385G3ECF0PXCE6S2GD5A=the-partner-didnt-set-up-advanced-privacy h_01H9FT385G9YMX9BAEYY0XQR4C=media-source-restrictions-on-thirdparty-platforms h_01HG0YAHWJ565C7BAXAXT75ACB=the-sdk-was-set-not-to-share-information-with-the-partner miscellaneous=c%C3%A1c-n%E1%BB%99i-dung-kh%C3%A1c h_01H9FT385GSWRPKEHKJ4HXCX01=c%C3%A1c-n%E1%BB%99i-dung-kh%C3%A1c h_01H9FT385GTSH1K93WNCARY2BA=the-postback-was-sent-but-doesnt-show-on-the-partners-platform h_01H9FT385G5HK6N2JEE8C6S245=the-event-didnt-occur h_01H9FT385GPVT9WAC6ZTPK6D10=differences-in-time-zones h_01H9FT385G8RXJD25KAQJ28TF6=srns-missing-advertising-ids-idfagaid h_01H9FT385GAYCY615W7M88XJT3=media-source-restrictions-on-thirdparty-platforms::40092c14 h_01HE7R6G699RG30ZSSQF02AK5Y=xem-th%C3%AAm" />
