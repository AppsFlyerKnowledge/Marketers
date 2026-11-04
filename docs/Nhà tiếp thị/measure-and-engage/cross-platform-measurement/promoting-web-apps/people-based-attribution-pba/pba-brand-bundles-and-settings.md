---
title: Gói và cài đặt thương hiệu PBA
metadata:
  keywords:
    - Advertisers
    - Bundles
    - Web Attribution
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2018-12-09T11:42:52Z'
  edited_at: '2025-05-08T09:17:30Z'
  id: 360000646498
  locale: vi
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/vi/articles/360000646498
---
> **Sơ lược:** Gói thương hiệu hợp nhất lượt phân bổ, sự kiện, lượt truy cập và doanh thu của các ứng dụng và trang web liên quan đến thương hiệu. Sử dụng trang cài đặt gói thương hiệu để đánh dấu các sự kiện chuyển đổi, tích hợp với Google Ads và nhiều hơn thế.

![BrandBundles.png](https://files.readme.io/eab9447f0bdd225ab7915724f996555057fa7f2840ec6e69a89465a90af6181e-360017356617.png)

<div id="about-brand-bundles" />

## Giới thiệu về gói thương hiệu

Các thương hiệu hoạt động trong một hệ sinh thái bao gồm cả thuộc tính web và di động. Với tư cách là nhà quảng cáo, một bức tranh đầy đủ về hiệu quả của thương hiệu trên các nền tảng–web và thiết bị di động–là điều cần thiết. Trong PBA, các gói thương hiệu hợp nhất dữ liệu của các thuộc tính web và di động thành một thực thể duy nhất để phân tích và dữ liệu thô.

<div id="what-is-a-web-app" />

> 📘 **Ứng dụng web là gì?**
>
> Ứng dụng web là một <Anchor target="_blank" href="/marketers/vi/docs/adding-an-app-to-appsflyer">thực thể bạn đã tạo trong AppsFlyer</Anchor> để chỉ định trang web mà bạn muốn đo lường hiệu quả.
>
> * Thực thể ứng dụng web đã được thêm vào AppsFlyer vào ngày 9 tháng 2 năm 2022. Trước ngày đó, bạn đã nhập miền của gói thương hiệu dưới dạng cài đặt riêng khi tạo gói thương hiệu. Bây giờ, bạn cần tạo một ứng dụng web để xác định miền, sau đó đưa ứng dụng web đó vào trong khi tạo gói.
> * Nếu có các gói thương hiệu vào ngày 9 tháng 2 năm 2022, bạn sẽ thấy rằng mình hiện có một ứng dụng web trên trang **My apps** tương ứng với từng gói đó. **Hãy yên tâm!** Lưu lượng truy cập web của bạn vẫn được tính như cũ và không có sự thay đổi đối với bảng điều khiển PBA hoặc báo cáo dữ liệu thô.

**Thông tin cơ bản về gói thương hiệu:**

* Gói thương hiệu chứa đúng 1 ứng dụng web *(bắt buộc)* và 1 hoặc nhiều ứng dụng di động *(không bắt buộc).*
* Một ứng dụng (web hoặc di động) chỉ có thể nằm trong 1 gói.
* Không thể xóa ứng dụng khỏi một gói hay chuyển ứng dụng giữa các gói mà không [xóa gói gốc](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle).
  * AppsFlyer sẽ ngừng phân bổ dữ liệu PBA cho gói bị xóa và thu hồi quyền truy cập vào dữ liệu lịch sử của gói đó.

<div id="accessing-brand-bundles" />

## Truy cập các gói thương hiệu

Truy cập trang **Brand Bundles** để quản lý các gói thương hiệu và cài đặt của chúng:

* Đi đến **My Apps** > **View brand bundles.**  
                           - hoặc -
* Từ cây điều hướng bên trái trên trang tổng quan, đi đến **Configuration** > **Brand Bundles.**

<div id="managing-brand-bundles" />

## Quản lý gói thương hiệu

Để thêm, xóa hoặc quản lý gói thương hiệu, hãy chọn một trong các tùy chọn sau từ trang **Brand Bundles**:

| Tùy chọn | Chi tiết |
| --- | --- |
| Thêm gói thương hiệu | Mở trang **Create bundle**   <br />Thực hiện theo [các hướng dẫn bên dưới](/docs/pba-brand-bundles-and-settings#add-brand-bundle) để tạo một gói mới. |
| Bảng điều khiển PBA | Mở bảng điều khiển thương hiệu |
| ID gói thương hiệu | Sao chép ID gói thương hiệu vào bảng nhớ tạm |
| Dev key web | Sao chép dev key web vào bảng nhớ tạm |
| Chọn một gói hiện có để cập nhật các tùy chọn và cài đặt gói thương hiệu | Các tùy chọn có sẵn:<ul><li>Đánh dấu sự kiện là sự kiện chuyển đổi:<ul><li>[Cài đặt sự kiện web](/docs/pba-brand-bundles-and-settings#web-event-settings)</li><li>[Cài đặt sự kiện trong ứng dụng](/docs/pba-brand-bundles-and-settings#inapp-event-settings)</li></ul></li><li>[Loại trừ miền](/docs/pba-brand-bundles-and-settings#domain-exclusion)</li><li><Anchor target="_blank" href="/marketers/vi/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">Tích hợp Google Ads</Anchor></li></ul> |
| Xóa biểu tượng | [Xóa gói thương hiệu đã chọn](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) (sau khi bạn xác nhận hành động này) |

<div id="add-brand-bundle" />

<Accordion title="Thêm gói thương hiệu">

Trước khi tiếp tục, hãy đảm bảo rằng tất cả ứng dụng bạn muốn đưa vào gói đã được thêm vào tài khoản của bạn. Sau khi tạo gói thương hiệu, bạn không thể thay đổi các ứng dụng trong đó trừ khi [xóa gói](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) và tạo lại gói đó.

**Cách thêm gói thương hiệu:**

1. Từ trang [Brand Bundles](/docs/pba-brand-bundles-and-settings#truy-cập-các-gói-thương-hiệu), nhấp vào **Add brand bundle.**
2. Nhập **Brand bundle name** (bất kỳ tên nào bạn muốn sử dụng để xác định gói).
3. Chọn ứng dụng để đưa vào gói.

   **Lưu ý:** Các ứng dụng nằm trong các gói khác sẽ không có để lựa chọn.

   * Ứng dụng web *[bắt buộc]*: Chọn 1 ứng dụng web có sẵn.
   * Ứng dụng di động *[không bắt buộc]:* Chọn các ứng dụng di động có sẵn mà bạn muốn đưa vào gói.
     * Không bắt buộc phải có ứng dụng di động khi tạo gói.
     * Không giới hạn về số lượng ứng dụng di động bạn có thể đưa vào một gói.
4. Nhấp vào Create bundle.

<div id="important" />

> 🚧 **Quan trọng!**
>
> Không thể tạo gói thương hiệu trong các trường hợp sau:
>
> * Ứng dụng web được chọn để đưa vào gói không trỏ đến URL hợp lệ.
> * Ứng dụng web và ứng dụng di động Android được chọn để đưa vào gói có cùng ID ứng dụng.

</Accordion>

<div id="web-event-settings" />

<Accordion title="Cài đặt sự kiện web">

Có hai loại sự kiện web: **tiêu chuẩn** và **chuyển đổi**. Hãy đặt một số sự kiện là sự kiện chuyển đổi để tập trung và ưu tiên các nỗ lực tối ưu hóa của bạn.

* PBA phân bổ các sự kiện tiêu chuẩn và sự kiện chuyển đổi theo cách tương tự nhau.
* Báo cáo <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">dữ liệu thô</Anchor> bao gồm sự kiện tiêu chuẩn và sự kiện chuyển đổi.
* Bảng điều khiển PBA chỉ gồm các sự kiện chuyển đổi.
* Bạn có thể thay đổi loại sự kiện bất cứ lúc nào; tuy nhiên, thay đổi này không áp dụng hồi tố.

**Cách đặt sự kiện chuyển đổi:**

1. Từ trang [Brand Bundles](/docs/pba-brand-bundles-and-settings#truy-cập-các-gói-thương-hiệu), chọn gói thương hiệu.  
   Trang **Update Brand bundles** sẽ mở ra.
2. Đi đến thẻ **Web event settings**.
3. Bật **Mark as conversion event** theo yêu cầu.
4. Nhấp vào **Update bundle.**

</Accordion>

<div id="inapp-event-settings" />

<Accordion title="Cài đặt sự kiện trong ứng dụng">

Đường dẫn Chuyển đổi coi các sự kiện trong ứng dụng được đánh dấu và các sự kiện web được đánh dấu là sự kiện chuyển đổi. Giống như các sự kiện web, nhà tiếp thị thiết đặt các sự kiện trong ứng dụng cụ thể là sự kiện chuyển đổi.

[Mặc định] Các sự kiện trong ứng dụng tạo ra doanh thu sẽ được đánh dấu là sự kiện chuyển đổi. **Lưu ý!** Nếu thay đổi các sự kiện mặc định, bạn phải tự đánh dấu rõ ràng các sự kiện doanh thu trong ứng dụng.

**Cách đánh dấu các sự kiện trong ứng dụng là sự kiện chuyển đổi:**

1. Từ trang [Brand Bundles](/docs/pba-brand-bundles-and-settings#truy-cập-các-gói-thương-hiệu), chọn gói thương hiệu.  
   Trang **Update Brand bundles** sẽ mở ra.
2. Đi đến thẻ **In-app event settings**.
3. Bật **Mark as conversion event** theo yêu cầu.
4. Nhấp vào **Update bundle.**

</Accordion>

<div id="domain-exclusion" />

<Accordion title="Loại trừ miền">

Triển khai cơ chế loại trừ miền, một phần của <Anchor target="_blank" href="/marketers/vi/docs/pba-media-source-attribution-rules">quy tắc nguồn truyền thông PBA,</Anchor> để ngăn chặn:

* Tự phân bổ: Nói cách khác, AppsFlyer sẽ không phân bổ các sự kiện cho trang web được xác định trong chính ứng dụng web và cho các miền bạn chỉ định được liên kết với trang web đó.
* Việc phân bổ hoặc ghi nhận sự kiện được liên kết với các miền không nằm trong gói thương hiệu của bạn nhưng tham gia vào luồng người dùng (ví dụ: cổng thanh toán).

| Loại miền | Mô tả | Tác động của loại trừ |
| --- | --- | --- |
| Chính | Miền của **ứng dụng web** nằm trong gói thương hiệu. Điều này bao gồm các miền phụ.<br /><br />Ví dụ: nếu miền của bạn là mydomain.co.za thì các miền phụ như a.mydomain.co.za, b.mydomain.co.za sẽ tự động bị loại trừ. <br /><br />Không thể thay đổi miền của ứng dụng web trừ khi [xóa](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) và tạo lại ứng dụng web. (Điều này cũng đồng nghĩa xóa gói chứa ứng dụng web). | Không tự phân bổ |
| Nội bộ | Liệt kê các miền khác tạo thành một phần thương hiệu của bạn, ví dụ: mydomain.com, mydomain.in, mydomain.co.ng, abc.com | Không tự phân bổ |
| Bên ngoài (do bạn liệt kê) | Các miền mà trang web của bạn sử dụng trực tiếp nhưng không nằm trong gói thương hiệu. Các miền này bao gồm các cổng thanh toán, trang xử lý thanh toán và nhiều hơn thế. | <Anchor target="_blank" href="/marketers/vi/docs/pba-media-source-attribution-rules#visit-recognition-rules">Bỏ qua các lượt truy cập</Anchor> |
| Bên ngoài (do AppsFlyer liệt kê) | Các miền do AppsFlyer liệt kê và luôn bị loại trừ.<ul><li>PayPal</li><li>Stripe</li><li>Adyen</li></ul>Danh sách miền tự động không chỉnh sửa được. | <Anchor target="_blank" href="/marketers/vi/docs/pba-media-source-attribution-rules#visit-recognition-rules">Bỏ qua các lượt truy cập</Anchor> |

**Cách loại trừ các miền nội bộ hoặc bên ngoài:**

1. Từ trang [Brand Bundles](/docs/pba-brand-bundles-and-settings#truy-cập-các-gói-thương-hiệu), chọn gói thương hiệu.  
   Trang **Update Brand bundles** sẽ mở ra.
2. Đi đến thẻ **Domain exclusion**.
3. Nhấp vào **Add domain.**
4. Nhập một tên miền.
5. Chọn loại miền: **Internal** hoặc **External.**
6. Nhấp vào **Add domain.**  
   Phải mất một giờ để loại trừ có hiệu lực.

</Accordion>

<div id="faq" />

## Câu hỏi thường gặp

<div id="can-i-include-the-same-app-in-more-than-one-bundle" />

<Accordion title="Tôi có thể đưa cùng một ứng dụng vào nhiều gói không?">

**Không.** Sau khi thêm ứng dụng vào một gói, bạn sẽ không thêm được ứng dụng đó vào gói khác.

</Accordion>

<div id="can-i-add-or-remove-apps-after-creating-a-bundle" />

<Accordion title="Tôi có thể thêm hoặc xóa ứng dụng sau khi tạo gói không?">

**Không.** Sau khi tạo gói, bạn sẽ không thể thay đổi các ứng dụng trong đó.

**Tại sao?** Mỗi ứng dụng có dữ liệu riêng và AppsFlyer sử dụng dữ liệu này để phân tích hành trình của người dùng trên các nền tảng (web và ứng dụng). Nếu một ứng dụng thay đổi, điều này sẽ liên quan đến một tập dữ liệu khác không tương thích với dữ liệu trước đó.

</Accordion>

<div id="how-do-i-add-or-remove-delete-apps-from-a-bundle" />

<Accordion title="Làm cách nào để thêm hoặc gỡ (xóa) ứng dụng khỏi gói?">

Để thay đổi gói chứa ứng dụng, hãy xóa gói ban đầu và tạo gói mới chứa ứng dụng đó.

</Accordion>

<div id="what-happens-if-i-delete-a-bundle" />

<Accordion title="Điều gì sẽ xảy ra nếu tôi xóa một gói?">

<div id="faqs-what-happens-if-i-delete-a-bundle" />

#### câu hỏi thường gặp điều gì xảy ra nếu tôi xóa một gói

Nếu bạn xóa một gói:

* AppsFlyer ngừng phân bổ gói.
* Dữ liệu gói được lưu giữ (nói cách khác, dữ liệu sẽ không bị xóa vĩnh viễn), nhưng bản thân gói đó không thể được khôi phục để xem dữ liệu.

  **Tại sao?** Gói mới sử dụng một dev key web khác. Do đó ngay cả khi gói đó chứa cùng các ứng dụng, gói ban đầu sẽ không được khôi phục.

</Accordion>

<div id="why-are-certain-apps-not-available-for-me-to-add-to-a-bundle" />

<Accordion title="Tại sao một số ứng dụng cụ thể không có để tôi thêm vào gói?">

* **Quản trị viên:** Nếu bạn không thể chọn một ứng dụng khi tạo gói, hãy đảm bảo ứng dụng đó đã được thêm vào tài khoản AppsFlyer của bạn và không nằm trong một gói khác.
* **Người dùng tài khoản khác:** Kiểm tra với quản trị viên tài khoản để đảm bảo bạn có vai trò và quyền cần thiết để truy cập vào ứng dụng bạn đang cố gắng thêm.

</Accordion>

<div id="see-also" />

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/onboarding-guide-to-people-based-attribution">Giới thiệu về PBA dành cho người mới</Anchor>
> * <Anchor target="_blank" href="/marketers/vi/docs/people-based-attribution-pba-overview">PBA bắt đầu</Anchor>

<div data-zendesk-anchors="about-brand-bundles=gi%E1%BB%9Bi-thi%E1%BB%87u-v%E1%BB%81-g%C3%B3i-th%C6%B0%C6%A1ng-hi%E1%BB%87u h_01HE0Y2A3A5W86YY44RWCTKM1Y=gi%E1%BB%9Bi-thi%E1%BB%87u-v%E1%BB%81-g%C3%B3i-th%C6%B0%C6%A1ng-hi%E1%BB%87u h_01HE0Y2A3AYAFFSPRSH2BQ00Z3=%E1%BB%A9ng-d%E1%BB%A5ng-web-l%C3%A0-g%C3%AC accessing-brand-bundles=truy-c%E1%BA%ADp-c%C3%A1c-g%C3%B3i-th%C6%B0%C6%A1ng-hi%E1%BB%87u h_01HE0Y2A3A7265NYM7GVBZVXEN=truy-c%E1%BA%ADp-c%C3%A1c-g%C3%B3i-th%C6%B0%C6%A1ng-hi%E1%BB%87u managing-brand-bundles=qu%E1%BA%A3n-l%C3%BD-g%C3%B3i-th%C6%B0%C6%A1ng-hi%E1%BB%87u h_01HE0Y2A3A272QJ4ZQH7VXJWCC=qu%E1%BA%A3n-l%C3%BD-g%C3%B3i-th%C6%B0%C6%A1ng-hi%E1%BB%87u h_01HE0Y2A3ATX4ZDYZSRQGSJ4G7=add-brand-bundle h_01HE0Y2A3AQC5MMNQA0AV34MZ3=quan-tr%E1%BB%8Dng h_01HE0Y2A3ATN6DEQ2KHCGT6VPQ=web-event-settings h_01HE0Y2A3A76VBZ17W4P1D0K2A=inapp-event-settings h_01HE0Y2A3A7F2YEW2SK0PSXXE4=domain-exclusion faq=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p h_01HE0Y2A3AB24NCNPAYFC0J4YH=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p h_01HE0Y2A3A5E816CYG2TMZ37DA=can-i-include-the-same-app-in-more-than-one-bundle h_01HE0Y2A3BENKY1AM51VM76TVS=can-i-add-or-remove-apps-after-creating-a-bundle h_01HE0Y2A3BK4JKMTND0JFCB179=how-do-i-add-or-remove-delete-apps-from-a-bundle h_01HE0Y2A3BKJTQZJXV49X32N1E=what-happens-if-i-delete-a-bundle faqs-what-happens-if-i-delete-a-bundle=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-%C4%91i%E1%BB%81u-g%C3%AC-x%E1%BA%A3y-ra-n%E1%BA%BFu-t%C3%B4i-x%C3%B3a-m%E1%BB%99t-g%C3%B3i h_01HE0Y2A3B276FV92EYBCZRA6C=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-%C4%91i%E1%BB%81u-g%C3%AC-x%E1%BA%A3y-ra-n%E1%BA%BFu-t%C3%B4i-x%C3%B3a-m%E1%BB%99t-g%C3%B3i h_01HE0Y2A3BEB2JG8CPSX3DA1V9=why-are-certain-apps-not-available-for-me-to-add-to-a-bundle h_01HE0Y2KTXS06WHN57MQ91AD09=xem-th%C3%AAm" />
