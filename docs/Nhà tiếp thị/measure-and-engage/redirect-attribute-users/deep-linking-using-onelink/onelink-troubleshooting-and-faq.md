---
title: Câu hỏi thường gặp và khắc phục sự cố OneLink
metadata:
  keywords:
    - faq
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2020-10-27T11:26:30Z'
  edited_at: '2024-03-11T12:36:31Z'
  id: 360014821438
  locale: vi
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/vi/articles/360014821438
---
> **Sơ lược:** Nhanh chóng tìm giải pháp để kiểm tra và gỡ lỗi các vấn đề về chuyển hướng/trạng thái liên kết tùy chỉnh OneLink.

<div id="onelink-troubleshooting-guide" />

## Hướng dẫn khắc phục sự cố OneLink

<div id="onelink-frequently-asked-questions" />

## Câu hỏi thường gặp về OneLink

<div id="onelink-template-faq" />

### Câu hỏi thường gặp về mẫu OneLink

<div id="which-method-should-i-use-for-opening-apps-universal-links-app-links-or-uri-schemes" />

<Accordion title="Tôi nên sử dụng phương thức nào để mở ứng dụng—Liên kết Chung, Liên kết Ứng dụng hoặc lược đồ URI?">

**Liên kết Chung:** Bắt buộc đối với hơn 98% người dùng iOS

**Liên kết Ứng dụng:** Dành cho người dùng Android từ phiên bản 6.0 trở lên. **Lưu ý**: Hệ điều hành Samsung không thể mở ứng dụng bằng Liên kết Ứng dụng Android.

<div id="note" />

> 📘 **Lưu ý**
>
> Cả Liên kết Chung và Liên kết Ứng dụng đều yêu cầu bằng chứng rằng miền trong URL được nhấp (nói cách khác, miền liên kết tùy chỉnh OneLink hoặc miền được gắn thương hiệu) sở hữu và liên kết với ứng dụng cụ thể mà liên kết đó đang cố gắng mở. Việc liên kết miền này được thực hiện thông qua **tệp tin Apple App Site Association (AASA)** đối với iOS và tệp tin **Assetlinks** đối với Android.
>
> Các tệp tin này được AppsFlyer hoặc nhà quảng cáo lưu trữ trên trang web của họ. Theo mặc định, khi bạn tạo mẫu OneLink và thiết lập Liên kết Chung và Liên kết Ứng dụng, các tệp tin này được tạo và lưu trữ bởi AppsFlyer.

**Lược đồ URI:** Phương thức chính để mở ứng dụng trên thiết bị Samsung. Nếu không, đây sẽ là phương thức kế thừa và dự phòng để mở ứng dụng. Có thể được sử dụng:

* Cho người dùng Android phiên bản 6.0 trở xuống (chưa đến 15% người dùng Android)
* Là phương án dự phòng khi Liên kết Chung và Liên kết Ứng dụng không mở được ứng dụng, vì chúng không hoạt động hoặc không được thiết lập.

  **Lưu ý:** Việc sử dụng lược đồ URI làm phương án dự phòng cho Liên kết Chung phải tuân theo các hạn chế dựa trên iOS. <Anchor target="_blank" href="/marketers/vi/docs/uri-scheme-fallback-for-ios">Tìm hiểu thêm</Anchor>.

<div id="deep-linking" />

#### Liên kết Sâu

Liên kết Chung, Liên kết Ứng dụng và lược đồ URI là các phương thức **mở** ứng dụng an toàn. Để liên kết sâu và chuyển hướng người dùng vào các hoạt động hoặc trang cụ thể trong ứng dụng, hãy làm theo <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">hướng dẫn liên kết sâu OneLink</Anchor>.

</Accordion>

<div id="which-operating-systems-allow-uri-schemes-to-open-the-app" />

<Accordion title="Hệ điều hành nào cho phép lược đồ URI mở ứng dụng?">

| HĐH | Lược đồ URI có tác dụng mở ứng dụng không? |
| --- | --- |
| iOS | **Có.** Sử dụng làm phương án dự phòng khi Liên kết Chung bị lỗi.<br /><br />**Lưu ý quan trọng:**<ul><li>Việc sử dụng lược đồ URI làm phương án dự phòng phải tuân theo các giới hạn chế dựa trên iOS.</li><li>Đối với nhiều trình duyệt, bao gồm cả Safari, bạn phải thêm tham số `af_force_deeplink=true` vào URL để có thể sử dụng lược đồ URI làm phương án dự phòng. <Anchor target="_blank" href="/marketers/vi/docs/uri-scheme-fallback-for-ios">Tìm hiểu thêm</Anchor>.</li></ul> |
| Android | **Có.** Sử dụng cho các thiết bị Samsung, phiên bản Android 6.0 trở xuống và làm phương án dự phòng khi Liên kết Ứng dụng không sử dụng được trên các phiên bản Android cao hơn. |
| Amazon | **Không** |
| Windows Mobile | **Không** |

</Accordion>

<div id="do-i-need-to-update-the-app-after-ios-universal-links-and-android-app-links-setup" />

<Accordion title="Sau khi thiết lập Liên kết Chung iOS và Liên kết Ứng dụng Android, tôi có cần cập nhật ứng dụng không?">

**Có.** Bất cứ khi nào Liên kết Chung hoặc Liên kết Ứng dụng được triển khai để mở ứng dụng cho người dùng hiện có, Tên miền Liên kết iOS hoặc AndroidManifest.xml sẽ được cập nhật. Điều này có nghĩa là bạn phải tải phiên bản mới của ứng dụng lên cửa hàng ứng dụng thích hợp. **Mẹo:** Để giảm thiểu yêu cầu về cập nhật ứng dụng, hãy thực hiện mọi thay đổi liên quan đến nhà phát triển cần để <Anchor target="_blank" href="/marketers/vi/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">mở ứng dụng</Anchor> và <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">liên kết sâu</Anchor> tại một thời điểm.

</Accordion>

<div id="can-i-redirect-existing-users-to-a-web-page-instead-of-the-app" />

<Accordion title="Tôi có thể chuyển hướng người dùng hiện tại đến một trang web thay vì ứng dụng không?">

**Có.** Tuy nhiên, việc định cấu hình mẫu của bạn để làm như vậy sẽ ảnh hưởng đến tất cả người dùng (mới và hiện có) và đưa mọi người đến trang đích/URL web. Điều này có nghĩa là người dùng mới sẽ không được đưa đến cửa hàng ứng dụng.

Để đưa người dùng đến một trang web:

1. Trong mẫu của bạn, không thiết lập Liên kết Chung, Liên kết Ứng dụng hoặc lược đồ URI.
2. Thiết lập chuyển hướng khi ứng dụng không được cài đặt đến trang đích/URL web.
   * Trang đích/URL web được thêm vào làm giá trị cho các tham số af\_android\_url và af\_ios\_url.
   * Các hoạt động chuyển hướng sau đó cũng được áp dụng tự động khi ứng dụng được cài đặt (đối với cho người dùng hiện có).

**Lưu ý**: Nếu bạn muốn chuyển hướng người dùng hiện có sang trang web trên thiết bị di động chỉ sau khi khởi chạy ứng dụng, thì nhà phát triển ứng dụng của bạn phải cấu hình chế độ đó.

</Accordion>

<div id="can-i-redirect-tablet-users-to-a-different-app-or-url-then-mobile-app-users" />

<Accordion title="Tôi có thể chuyển hướng người dùng máy tính bảng đến ứng dụng hoặc URL khác với người dùng ứng dụng di động không?">

Bạn có thể thiết lập hoạt động chuyển hướng cụ thể cho:

* Điện thoại Windows
* iPad
* Amazon Kindle Fire.

Các máy tính bảng khác hiện không được hỗ trợ cho hoạt động chuyển hướng riêng.

</Accordion>

<div id="can-i-assign-an-app-to-multiple-onelink-templates" />

<Accordion title="Tôi có thể chỉ định một ứng dụng cho nhiều mẫu OneLink không?">

**Có.** Dù bạn có thể dùng một mẫu OneLink duy nhất để tạo không giới hạn số lượng URL OneLink, nhưng trong một số trường hợp, bạn có thể cần phải gán một ứng dụng cho nhiều mẫu OneLink. Ví dụ, nếu bạn có nhiều phiên bản của một ứng dụng Android cho các thị trường ngoài cửa hàng ứng dụng, bạn có thể cần một mẫu OneLink riêng cho mỗi phiên bản Android gán cùng ứng dụng iOS cho tất cả các mẫu.

**Quan trọng**:

Đối với các mẫu sử dụng Liên kết Chung iOS và Liên kết Ứng dụng Android để mở ứng dụng, **nếu mẫu của bạn có các miền phụ khác nhau**, thì bạn cần phải cấu hình và cập nhật các ứng dụng iOS và Android của mình cho từng mẫu:

* **Liên kết Chung iOS:** Sau khi tạo mẫu OneLink mới và cập nhật tên miền liên kết trong ứng dụng, hãy gửi phiên bản mới tới App Store. Chỉ người dùng iOS đã cập nhật lên phiên bản mới mới có thể kích hoạt URL OneLink được tạo trên cùng một mẫu.
* **Liên kết Ứng dụng Android:**
  1. Sau khi tạo mẫu OneLink mới, hãy sao chép đoạn XML ở cuối phần Liên kết Ứng dụng và thêm vào tệp **AndroidManifest.xml** bên trong mục đích bạn muốn liên kết sâu tới, ngoài bất kỳ các mục đích nào trước đó.
  2. Phát hành phiên bản mới lên cửa hàng ứng dụng. Chỉ người dùng Android đã cập nhật lên phiên bản mới mới có thể kích hoạt URL OneLink được tạo trên cùng một mẫu.

</Accordion>

<div id="can-i-delete-a-onelink-template" />

<Accordion title="Tôi có thể xóa mẫu OneLink không?">

**Có,** nhưng chỉ bằng cách liên hệ với CSM của bạn hoặc gửi email đến đội ngũ Quan hệ Khách hàng của chúng tôi tại địa chỉ [hello@appsflyer.com](mailto:hello@appsflyer.com).

**Lưu ý:** Nếu bạn đang có các URL OneLink dựa trên mẫu đã xóa, **chúng thậm chí sẽ không thể đưa người dùng đến cửa hàng ứng dụng.** Vì lý do này, điều đặc biệt quan trọng là trước hết bạn phải đảm bảo rằng không có URL OneLink nào sử dụng mẫu thì mới nên xóa mẫu đó. Ngoài ra, cân nhắc xem bạn có thể đạt được kết quả bạn cần bằng cách thay đổi cấu hình của mẫu hiện có thay vì xóa mẫu đó đi hay không.

</Accordion>

<div id="can-i-change-the-subdomain-in-a-onelink-template" />

<Accordion title="Tôi có thể thay đổi miền phụ trong mẫu OneLink không?">

**Có, miễn là không có liên kết tùy chỉnh hiện có trong AppsFlyer dựa trên mẫu đó.**

Nếu đã có các liên kết tùy chỉnh trong AppsFlyer dựa trên mẫu OneLink thì bạn không thể thay đổi miền phụ. Mục dích của hạn chế này là để ngăn chặn việc gián đoạn hoạt động chuyển hướng/liên kết sâu của các liên kết còn hoạt động.

Nếu cần thay đổi miền phụ trong một mẫu bằng các liên kết tùy chỉnh hiện có, bạn có thể:

* Tạo mẫu OneLink mới với miền phụ mới, và tạo liên kết dựa trên miền phụ đó.
* Xóa tất cả các liên kết tùy chỉnh hiện có dựa trên mẫu mà miền phụ cần được thay đổi. Khi tất cả các liên kết dựa trên mẫu đã bị xóa thì có thể chỉnh sửa được miền phụ.

</Accordion>

<div id="can-the-domainsubdomain-of-a-onelink-template-be-applied-to-the-template-id-of-another-template" />

<Accordion title="Có thể áp dụng miền/miền phụ của mẫu Onelink cho ID mẫu của một mẫu khác không?">

**Không.** Việc đưa miền phụ/miền được cấu hình đến một mẫu và ID mẫu cụ thể và ghép nối thủ công miền đó với một ID mẫu khác sẽ làm hỏng chức năng của Liên kết Chung và Liên kết Ứng dụng cũng như gây ra mối đe dọa về bảo mật.

**Ví dụ:**

* Mẫu 1ABC được cấu hình với miền phụ **bank.onelink.me**.
* Mẫu D123 được cấu hình với miền phụ **game.onelink.me**.
* Liên kết **bank.onelink.me/1ABC/shorturl** được tạo dựa trên mẫu 1ABC và hoạt động.
* Liên kết **game.onelink.me/D123/exampleurl** được tạo dựa trên mẫu D123 và hoạt động.
* Liên kết **game.onelink.me/1ABC/shorturl** không hoạt động
* Liên kết **bank.onelink.me/D123/exampleurl** không hoạt động

</Accordion>

<div id="can-i-use-the-same-subdomain-for-more-than-one-template" />

<Accordion title="Tôi có thể sử dụng cùng một miền phụ cho nhiều mẫu không?">

**Có.** Tuy nhiên, hãy đảm bảo bạn tạo các mẫu riêng với miền phụ; không được chỉ thêm thủ công miền phụ vào một ID mẫu.

</Accordion>

<div id="how-can-i-redirect-desktop-users" />

<Accordion title="Làm cách nào để chuyển hướng người dùng máy tính để bàn?">

Người dùng máy tính để bàn có thể tương tác với các liên kết tùy chỉnh OneLink của bạn, chẳng hạn như thông qua chiến dịch email. Tuy nhiên, khi người dùng máy tính để bàn nhấp vào các liên kết này, họ sẽ không được chuyển hướng đến trang web trên thiết bị di động, cửa hàng ứng dụng hay ứng dụng.

**Vậy làm cách nào để mang đến cho người dùng máy tính để bàn trải nghiệm người dùng tốt và chuyển đổi họ thành người dùng di động?**

Trong URL hoặc mẫu OneLink, bạn có thể chuyển hướng người dùng máy tính để bàn (Windows hoặc Mac) đến một URL khác. URL web này được thêm vào liên kết trong tham số `af_web_dp`. **Lưu ý:** Nếu liên kết của bạn chứa `af_web_dp`, AppsFlyer không ghi nhận lượt nhấp khi lượt nhấp đó đến từ máy tính để bàn.

<div id="tip" />

> 👍 **Mẹo**
>
> Thử chuyển hướng người dùng máy tính để bàn đến URL web có chứa biểu mẫu web dành riêng gửi URL OneLink đến thiết bị di động của người dùng máy tính để bàn qua SMS hoặc email. Tìm hiểu thêm về tùy chọn này thuộc giải pháp <Anchor target="_blank" href="/marketers/vi/docs/set-up-smart-script-to-convert-web-visitors#desktop">Tập lệnh Thông minh OneLink</Anchor>.

</Accordion>

<div id="how-can-i-redirect-chrome-os-users" />

<Accordion title="Làm cách nào tôi có thể chuyển hướng người dùng Chrome OS?">

Các ứng dụng trên Chromebook được coi là ứng dụng Android.

Đối với Chromebook, để chuyển hướng người dùng mới mà không phải cài đặt ứng dụng của bạn đến một URL web khác:

1. Trong phần cài đặt mẫu OneLink, ở mục **Set link behavior** > **When app isn’t installed** > **Android**, nhấp vào **Change to a different URL**.  
   HOẶC  
   Trong phần cài đặt liên kết OneLink, ở mục **Deep linking & redirection** > **Redirect** > **When app isn't installed** > **Android**, chọn **Web URL**.
2. Nhập URL.  
   Khi được thêm qua cài đặt liên kết, URL sẽ được thêm vào liên kết của bạn trong tham số `af_android_url`.

</Accordion>

<div id="onelink-link-faq" />

### Câu hỏi thường gặp về liên kết OneLink

<div id="does-onelink-work-without-the-appsflyer-sdk" />

<Accordion title="OneLink có hoạt động mà không cần SDK AppsFlyer không?">

**Có, nhưng chỉ một phần.**

Nếu bạn cần chuyển đổi khách truy cập web di động thành người dùng di động nhanh chóng và không thể tích hợp SDK AppsFlyer, bạn có thể làm như vậy.

Có thể chuyển hướng người dùng cơ bản và khởi chạy ứng dụng ngay cả khi SDK AppsFlyer chưa được tích hợp vào ứng dụng. Biểu ngữ Thông minh cũng không yêu cầu SDK và cũng hoạt động tốt khi không có SDK.

Tuy nhiên, việc không có SDK có nghĩa là:

* Người dùng nhấp chuột sẽ không được liên kết sâu ngoài lần khởi chạy ứng dụng đầu tiên.
* Dữ liệu phân bổ không được ghi nhận.
* Các sự kiện trong ứng dụng không được ghi nhận.

</Accordion>

<div id="what-methods-are-available-for-creating-onelink-custom-links" />

<Accordion title="Có những phương thức nào để tạo liên kết tùy chỉnh OneLink?">

Bảng sau đây so sánh các phương thức khả dụng khác nhau để tạo liên kết tùy chỉnh OneLink.

| Phương thức tạo liên kết | Sử dụng | URL đầy đủ/rút gọn | Tính năng cao cấp | Hiển thị trong giao diện người dùng? | Phân bổ TTL (Thời gian Tồn tại) tối đa và mặc định |
| --- | --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Giao diện người dùng AppsFlyer</Anchor> | Tạo mẫu OneLink và các liên kết tùy chỉnh | Cả hai | -- | ✓ | Không có TTL |
| <Anchor target="_blank" href="/marketers/vi/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API OneLink</Anchor> | Tạo hàng nghìn OneLink một cách nhanh chóng | Rút gọn | ✓ | -- | 31 ngày |
| Tạo liên kết hàng loạt OneLink | Tạo hàng nghìn URL gọn OneLink nhanh chóng sử dụng các tham số được xác định trong một CSV | Rút gọn | -- | -- | 365 ngày |
| <Anchor target="_blank" href="/marketers/vi/docs/user-invite-attribution">SDK</Anchor> | Các chiến dịch mời (giới thiệu) người dùng | Rút gọn | -- | -- | 60 ngày |
| <Anchor target="_blank" href="/marketers/vi/docs/onelink-smart-script-overview">Tập lệnh Thông minh OneLink</Anchor> | Các chiến dịch từ web đến ứng dụng trên thiết bị di động | Đầy đủ | -- | -- | Không có TTL |
| <Anchor target="_blank" href="/marketers/vi/docs/understand-onelink-short-vs-long-urls">Bảng tính</Anchor> | Tạo hàng nghìn liên kết tùy chỉnh OneLink bằng cách áp dụng các công thức của riêng bạn | Đầy đủ | -- | -- | Không có TTL |

</Accordion>

<div id="can-onelink-custom-links-open-the-app-from-a-browser" />

<Accordion title="Các liên kết tùy chỉnh OneLink có thể mở ứng dụng từ trình duyệt không?">

**Có,** nhưng lưu ý rằng Liên kết Chung và Liên kết Ứng dụng chỉ hoạt động khi được nhấp vào (ví dụ: khi nhấp vào liên kết trên trang web hoặc email). **Việc dán liên kết vào thanh địa chỉ của trình duyệt sẽ không khởi chạy ứng dụng.** Kiểm tra các liên kết của bạn bằng cách nhấp vào URL; không phải bằng cách dán chúng vào khung URL của trình duyệt.

</Accordion>

<div id="why-doesnt-the-onelink-url-open-the-app-or-deep-link-existing-users" />

<Accordion title="Tại sao URL OneLink không mở ứng dụng hoặc liên kết sâu người dùng hiện có?">

Mặc dù với mục đích tốt, nhưng trong một số trường hợp, URL OneLink của bạn có thể không thực hiện liên kết sâu như dự kiến. Khi xảy ra trường hợp này, thay vì mở ứng dụng hoặc liên kết sâu vào một hoạt động cụ thể trong ứng dụng, người dùng lại được chuyển hướng đến cửa hàng ứng dụng hoặc đến trang lỗi.

Có thể là do một số lý do sau:

* **Ứng dụng máy chủ:** Các ứng dụng trong đó liên kết phân bổ của bạn được chia sẻ (ví dụ: WhatsApp, Gmail, WeChat) sử dụng các phương thức khác nhau để kích hoạt các liên kết được nhấp, chẳng hạn như trình duyệt nội bộ độc quyền. Một số phương thức trong số này được biết là có thể chặn tất cả các liên kết phân bổ.
* **Trình duyệt:** Một số trình duyệt và nền tảng hệ điều hành nhất định hoạt động khác nhau với các liên kết. Ví dụ, trong một số trình duyệt nhất định, việc dán liên kết sẽ không có hiệu quả. Liên kết cần phải được nhấp vào thật.
* **Cập nhật hệ điều hành:** Các bản cập nhật hệ điều hành mới (cả iOS và Android) có thể gây ra các lỗi không mong muốn cản trở việc liên kết sâu.
* **Thiết bị:** Điện thoại thông minh, máy tính bảng, máy tính xách tay khác nhau và các thiết bị khác chạy các phiên bản khác nhau của iOS, Android, Windows Mobile và các hệ điều hành khác có thể khác biệt rất lớn trong việc xử lý liên kết phân bổ.
* **Cấu hình sai:** Việc sử dụng các <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#traits-and-limitations">ký tự đặc biệt</Anchor> trong giá trị liên kết sâu sẽ làm hỏng liên kết.

Hai giải pháp để cải thiện trải nghiệm người dùng là URL Dự phòng và liên kết sâu bắt buộc.

<div id="fallback-urls" />

#### URL Dự phòng

URL Dự phòng đưa người dùng đến các trang web được chỉ định nếu việc mở ứng dụng hoặc liên kết sâu không thành công vì bất kỳ lý do gì. **Thận trọng!** Các URL này cũng đưa những người dùng chưa cài đặt ứng dụng của bạn đến URL dự phòng thay vì đến đúng cửa hàng ứng dụng. Vì vậy, hãy đảm bảo chỉ sử dụng tùy chọn này nếu bạn đang nhắm mục tiêu lại người dùng đã cài đặt ứng dụng của bạn.

Để triển khai URL dự phòng, trong mẫu OneLink hoặc cài đặt liên kết tùy chỉnh, hãy đặt hoạt động liên kết cho trường hợp khi ứng dụng chưa được cài đặt để chuyển hướng đến một URL khác.

[![different_url.png](https://files.readme.io/6e15b343cb778a0ab4e76c1be4a6bf3cd21ad675f9a64c521a61a4756a580a01-30192900484625.png)](https://files.readme.io/6e15b343cb778a0ab4e76c1be4a6bf3cd21ad675f9a64c521a61a4756a580a01-30192900484625.png)

Việc sử dụng tùy chọn cài đặt này sẽ thêm `af_ios_url` và `af_android_url` làm tham số đích cho phương án dự phòng, điều này sẽ khiến người dùng iOS được chuyển hướng đến trang được chỉ định bởi `af_ios_url` và người dùng Android được chuyển hướng đến trang được chỉ định bởi `af_android_url`.

<div id="tip-1" />

> 📄 **Ví dụ**
>
> Ví dụ, hãy xem xét URL OneLink sau:
>
> ```http
> https://go.onelink.ly/qwerty?pid=source&af_dp=greatapp%3A%2F%2F&af_ios_url=www.yoursite.com/ios-bonus
> &af_android_url=www.yoursite.com/android-bonus
> ```
>
> Cả người dùng iOS và Android nhấp vào liên kết này sẽ được liên kết sâu với ứng dụng. Tuy nhiên, khi liên kết sâu không thành công, người dùng được chuyển hướng như sau:
>
> * iOS: www.yoursite.com/ios-bonus
> * Android: www.yoursite.com/android-bonus

<div id="note-1" />

> 📘 **Lưu ý**
>
> * Nếu bạn thêm ký hiệu dấu thăng (#) vào giá trị tham số ở URL, bạn cần mã hóa nó.
> * Khi chuyển hướng xảy ra, tham số URL OneLink đi qua trang đích được chỉ định bởi `af_ios_url` hoặc `af_android_url`. Để ngăn chặn hiện tượng này, hãy thêm tham số `af_param_forwarding=false` vào OneLink.

<div id="forced-deep-linking" />

#### Liên kết sâu bắt buộc

Liên kết sâu bắt buộc cho phép bạn dùng lược đồ URI làm phương án dự phòng để mở ứng dụng và liên kết sâu người dùng.

Giải pháp này có hiệu quả rất tốt đối với hầu hết người dùng đã cài đặt ứng dụng. Tuy nhiên, đối với iOS, việc sử dụng lược đồ URI để mở ứng dụng sẽ có những hạn chế và bạn có thể cần thêm `af_force_deeplink=true` vào URL OneLink để bắt buộc liên kết sâu vào hoạt động được chỉ định trong lược đồ URI (tham số `af_dp`). Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/uri-scheme-fallback-for-ios">phương án dự phòng lược đồ URI đối với iOS.</Anchor>

</Accordion>

<div id="why-does-my-onelink-url-open-a-blank-page-in-chrome" />

<Accordion title="Tại sao URL OneLink của tôi lại mở một trang trống trong Chrome?">

Hãy đảm bảo bạn không sử dụng thẻ HTML  có thuộc tính `target`. Nếu URL OneLink được đặt bên trong thẻ  có thuộc tính `target="_blank"`, URL đó sẽ mở một trang trống trong Chrome (trên cả iOS và Android) và người dùng không được chuyển hướng đến App Store hoặc Google Play.

</Accordion>

<div id="can-i-use-onelink-for-redirection-on-brave" />

<Accordion title="Tôi có thể sử dụng OneLink để chuyển hướng trên Brave không?">

Có. Tuy nhiên, trên Android, khi người dùng nhấp vào liên kết OneLink trên trình duyệt Brave, liên kết sâu gián tiếp không hoạt động. Và trên iOS, sau khi người dùng nhấp vào, họ sẽ thấy màn hình trống và liên kết sâu gián tiếp chỉ hoạt động nếu sau đó họ thực hiện thao tác gì đó trên màn hình trống, ví dụ như cuộn hoặc nhấn nút.

</Accordion>

<div id="do-onelink-custom-links-take-longer-to-load-than-other-links" />

<Accordion title="Liên kết tùy chỉnh OneLink có mất nhiều thời gian tải hơn các liên kết khác không?">

**Không.** Liên kết tùy chỉnh OneLink không cần thêm thời gian xử lý hoặc thời gian tải để hoạt động bình thường và chuyển hướng người dùng theo yêu cầu. Chúng hoạt động nhanh như bất kỳ liên kết AppsFlyer nào khác.

</Accordion>

<div id="how-can-i-record-the-cost-per-install-when-using-onelink" />

<Accordion title="Làm cách nào để ghi nhận chi phí theo mỗi lượt cài đặt khi sử dụng OneLink?">

Bật tùy chọn **Enable cost per install** (trong **Advanced parameters**) sẽ cho phép bạn áp dụng giá trị CPI cụ thể cho mỗi lượt cài đặt đến từ liên kết.

Chọn đơn vị tiền tệ chi phí và sau đó là **giá trị CHỈ chứa số** (tối đa 4 chữ số sau dấu phẩy thập phân) biểu thị chỉ số CPI. Điều này sẽ thêm các tham số af\_cost\_currency và af\_cost\_value vào liên kết.

<div id="tip-2" />

> 📄 **Ví dụ**
>
> Một chiến dịch SMS có giá $20 cho mỗi 1000 tin nhắn (CPM). Kinh nghiệm cho thấy rằng các chiến dịch của bạn đạt được tỷ lệ chuyển đổi 5%, nghĩa là CPI thu được là $0,40. Việc đặt chi phí theo mỗi lượt cài đặt là 0,40 USD cho phép bạn đo lường ROI cuối cùng của chiến dịch SMS.

Tìm hiểu thêm về cách <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview">đo lường chi phí và ROI</Anchor>.

</Accordion>

<div id="how-can-i-prevent-parameter-forwarding-on-redirections" />

<Accordion title="Làm cách nào để ngăn chuyển tiếp tham số khi chuyển hướng?">

`af_r`, `af_ios_url`, `af_android_url`, và `af_web_dp` chuyển các tham số từ liên kết phân bổ hoặc OneLink đến trang được chuyển hướng. Để ngăn chặn trạng thái này, hãy thêm `af_param_forwarding=false` vào liên kết phân bổ.

</Accordion>

<div id="how-can-i-remove-appsflyer-pid-and-c-parameters-when-forwarding-while-keeping-all-other-parameters-on-redirection-urls" />

<Accordion title="Làm cách nào tôi có thể gỡ bỏ các tham số PID và C của AppsFlyer khi chuyển tiếp trong khi giữ lại mọi tham số khác trên URL chuyển hướng?">

Trong một số trường hợp, bạn có thể có URL với nhiều PID. Trường hợp này xảy ra vì AppsFlyer thêm các tham số PID và C vào URL chuyển hướng và khách hàng cũng có thể thêm tham số PID của riêng họ. Ví dụ, “ID sản phẩm” có thể là “pid” trong URL trang web của khách hàng.

Thông thường, việc thêm `af_param_forwarding=false` vào liên kết phân bổ sẽ loại bỏ tất cả các tham số.

Tuy nhiên, nếu liên kết được nhấp từ máy tính bàn, khách hàng có thể cần giữ nguyên các tham số CRM thiết yếu. Để chỉ xóa các tham số PID và C của AppsFlyer và giữ lại tất cả các tham số khác, hãy thêm `af_base_params_forward=false` vào liên kết phân bổ.

</Accordion>

<div id="are-singleplatform-custom-links-still-available" />

<Accordion title="Các liên kết tùy chỉnh đơn nền tảng có còn không?">

OneLink hiện là phương thức duy nhất được hỗ trợ để tạo liên kết phân bổ tùy chỉnh cho phương tiện truyền thông sở hữu.

Trước đây, chủ sở hữu ứng dụng cũng có thể sử dụng liên kết tùy chỉnh đơn nền tảng (dành riêng cho ứng dụng) mà không cần sử dụng OneLink. Phương thức này không còn được hỗ trợ nữa và chỉ có thể tạo các liên kết tùy chỉnh mới dựa trên mẫu OneLink.

Tuy nhiên, nếu bạn có các liên kết tùy chỉnh đơn nền tảng cũ, chúng vẫn hoạt động như bình thường. Bạn cũng có thể xem và chỉnh sửa các liên kết cũ của mình bằng cách nhấp vào **View legacy single platform links** ở góc trên cùng bên phải của trang liên kết tùy chỉnh OneLink.

</Accordion>

<div id="can-i-change-the-short-url-id-after-saving-a-link" />

<Accordion title="Tôi có thể thay đổi ID URL rút gọn sau khi lưu một liên kết không?">

**Không,** bạn chỉ có thể đặt ID URL rút gọn tại thời điểm tạo liên kết.

</Accordion>

<div id="can-i-wrap-and-shorten-onelink-custom-links" />

<Accordion title="Tôi có thể bao gói và rút ngắn các liên kết tùy chỉnh OneLink không?">

**Các trình rút gọn liên kết bên ngoài hoặc bao gói các liên kết tùy chỉnh OneLink của bạn sẽ phá hỏng chức năng mở ứng dụng của Liên kết Chung và Liên kết Ứng dụng.**

Để kích hoạt Liên kết Chung hoặc Liên kết Ứng dụng, HĐH cần nhận diện được miền của URL được liên kết với ứng dụng và bất kỳ loại bao gói, rút gọn bên ngoài nào, nếu không, việc chuyển hướng đến liên kết hiện cho người dùng sẽ khiến hoạt động này không thể thực hiện được. Điều này bao gồm việc sử dụng bit.ly, các liên kết không gắn thương hiệu AppsFlyer hoặc Nhà cung cấp Dịch vụ Email (ESP) đã bật tính năng ghi nhận lượt nhấp.

**Để bao gói hoặc rút ngắn liên kết theo cách cho phép việc chuyển hướng hoạt động chính xác:**

* Sử dụng các URL rút gọn do AppsFlyer tạo khi bạn tạo liên kết tùy chỉnh OneLink (thay vì các trình rút gọn bên ngoài như bit.ly).  
  **Mẹo**! Rút ngắn URL hơn nữa bằng cách tạo miền gắn thương hiệu ngắn trên liên kết của bạn. Và nếu bạn tạo các liên kết trong UI AppsFlyer, bạn có thể chỉnh sửa ID URL để ngắn nhất có thể. Ví dụ: https://brand.com/a1b2/a (trong đó **brand.com** là tên miền gắn thương hiệu của bạn, **a1b2** là ID mẫu luôn có 4 ký tự và **a** là ID URL, có thể chỉnh sửa thành 1 ký tự.   
  Lợi ích:
  * Phương thức này hoạt động vì nó sử dụng miền phụ OneLink được cấu hình trong mẫu OneLink.
  * Trang này cho phép bạn thay đổi nhanh các tham số, bao gồm bất kỳ cài đặt liên kết sâu nào, ngay cả sau khi phân phối các liên kết phân bổ cho khách hàng tiềm năng của bạn.
  * Trang còn hỗ trợ tính toán tất cả số lượt nhấp từ thiết bị di động trong bảng điều khiển AppsFlyer, vì vậy bạn không cần phải kiểm tra dịch vụ khác.
  * Phần cuối cùng trong URL rút gọn có thể được tùy chỉnh để biến thành một <Anchor target="_blank" href="/marketers/vi/docs/brand-onelink-with-your-domain">miền gắn thương hiệu</Anchor>.
* Sử dụng <Anchor target="_blank" href="https://dev.appsflyer.com/docs/initial-setup-2#procedures-for-uri-scheme">lược đồ URI</Anchor> làm phương án dự phòng để mở ứng dụng khi không sử dụng được Liên kết Chung và Liên kết Ứng dụng và thêm tham số sau vào liên kết: `af_force_deeplink=true`.
* Xem các tùy chọn để [làm việc với ESP](/docs/onelink-troubleshooting-and-faq#can-i-use-onelink-custom-links-in-emails).

</Accordion>

<div id="can-i-use-onelink-custom-links-in-emails" />

<Accordion title="Tôi có thể sử dụng liên kết tùy chỉnh OneLink trong email không?">

**Có,** nhưng điều này cần được đặc biệt cân nhắc khi bạn làm việc với Nhà cung cấp Dịch vụ Email (ESP). Để tính số lượt nhấp đã thực hiện, ESP sẽ bao gói tất cả các liên kết được đặt bên trong email. Điều này sẽ làm gián đoạn luồng liên kết sâu/mở ứng dụng cho những người dùng nhấp vào URL.

Để ngăn chặn trường hợp này, hãy sử dụng một trong các giải pháp tùy chọn sau:

* Tắt ghi nhận lượt nhấp trong cấu hình ESP của bạn.  
  **(Mẹo: Đây thường là giải pháp dễ dàng nhất.)**
* Buộc mở ứng dụng bằng lược đồ URI được chỉ định trong tham số `af_dp` bằng cách thêm cờ báo `af_esp=true` vào liên kết phân bổ. Giải pháp này rất có hiệu quả đối với những người dùng đã cài đặt ứng dụng.
* Sử dụng các ESP hỗ trợ giải pháp AppsFlyer để mở ứng dụng và liên kết sâu với Liên kết Chung. <Anchor target="_blank" href="/marketers/vi/docs/email-service-provider-esp-integration-guide">Tìm hiểu thêm</Anchor>.

</Accordion>

<div id="how-do-users-get-redirected-to-their-regional-app-store" />

<Accordion title="Người dùng được chuyển hướng đến cửa hàng ứng dụng khu vực của họ bằng cách nào?">

OneLink chuyển hướng người dùng đến cửa hàng ứng dụng khu vực chính xác dựa trên địa chỉ IP của họ.

</Accordion>

<div id="why-isnt-my-onelink-url-redirecting-users-to-the-specified-domain" />

<Accordion title="Tại sao URL OneLink của tôi không chuyển hướng người dùng đến miền được chỉ định?">

Kiểm tra xem bạn có kích hoạt danh sách cho phép Chuyển hướng trong AppsFlyer chưa. Nếu bạn đã kích hoạt, miền hoặc miền phụ URL web mong muốn phải được liệt kê. <Anchor target="_blank" href="/marketers/vi/docs/set-up-your-api-allowlist#redirect-allowlists">Tìm hiểu thêm về danh sách cho phép Chuyển hướng</Anchor>

</Accordion>

<Accordion title="Tại sao tôi gặp lỗi “Ứng dụng bạn đang tìm kiếm không khả dụng”?">

Lỗi “Ứng dụng bạn đang tìm kiếm không khả dụng” có thể phát sinh thay vì chuyển hướng đến Google Play do:

* Ứng dụng của bạn hiện đang ở trạng thái “Đang chờ xử lý” trên Google Play. Để tránh thông báo lỗi được đề cập ở trên, hãy đặt chuyển hướng của liên kết để trỏ đến URL web thay vì Google Play. Sau khi ứng dụng được phê duyệt, bạn có thể thay đổi chuyển hướng trở lại Google Play. Những thay đổi cấu hình này được thực hiện trên <Anchor target="_blank" href="/marketers/vi/docs/create-a-onelink-template#create-a-onelink-template-with-redirection-logic-for-new-app-users">trang mẫu của liên kết</Anchor>.
* Nếu ứng dụng của bạn chỉ có sẵn thông qua cửa hàng của bên thứ ba, sự cố có thể phát sinh do ứng dụng được gán trạng thái Google Play không chính xác trong AppsFlyer. Để khắc phục sự cố này, bạn <Anchor target="_blank" href="/marketers/vi/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app">phải đặt trạng thái Google Play thành Đã xuất bản ngoài cửa hàng</Anchor> trên trang Settings My Apps.

</Accordion>

<div id="can-i-manually-switch-between-the-branded-domain-and-its-onelink-subdomain-in-an-existing-link" />

<Accordion title="Tôi có thể chuyển đổi thủ công giữa miền gắn thương hiệu và miền phụ OneLink trong liên kết hiện có không?">

Có - Nếu miền gắn thương hiệu và miền phụ OneLink được ánh xạ chính xác. Xem: <Anchor target="_blank" href="/marketers/vi/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer">Thiết lập Tên miền gắn Thương hiệu trong AppsFlyer</Anchor>

**Ví dụ**:  
Tên miền phụ OneLink: **demo.onelink.me**  
ID Mẫu: **A1r4**  
Các miền gắn Thương hiệu được ánh xạ tới miền phụ [**demo.onelink.me**](http://demo.onelink.me) là:

* **app.simulatorapp.com**
* **click.simulatorapp.com**

Bạn đã tạo liên kết gắn thương hiệu sau trong UI OneLink:  
**app.simulatorapp.com/A1r4/simulationlink**  
Bạn có thể thay thế liên kết gắn thương hiệu ở trên bằng liên kết miền gắn thương hiệu khác hoặc liên kết miền phụ OneLink.  
Các liên kết sau đây có chức năng giống hệt nhau và hoạt động giống nhau ở mọi nơi:

* app.simulatorapp.com/A1r4/simulationlink
* demo.onelink.me/A1r4/simulationlink
* click.simulatorapp.com/A1r4/simulationlink

</Accordion>

<div id="onelink-parameter-faq" />

### Câu hỏi thường gặp về tham số OneLink

<div id="what-parameters-are-mandatory-for-onelink-custom-links" />

<Accordion title="Những tham số nào là bắt buộc đối với liên kết tùy chỉnh OneLink?">

Chỉ tham số kênh truyền thông (**pid**) là bắt buộc.

</Accordion>

<div id="can-parameters-be-appended-to-the-short-url" />

<Accordion title="Có thể nối các tham số vào URL rút gọn không?">

**Có,** mọi tham số đều có thể được nối vào URL rút gọn.

**Quan trọng!** Các tham số được nối vào URL rút gọn không ghi đè các tham số bên trong liên kết.

<div id="tip-3" />

> 📄 **Ví dụ**
>
> * Bạn tạo liên kết tùy chỉnh OneLink với đầu ra sau:
>   * **URL đầy đủ:** https://onelink-sim.onelink.me/Il2C?pid=training&c=peaches
>   * **URL rút gọn:** https://onelink-sim.onelink.me/Il2C/70e6d165
> * Bạn nối các tham số sau vào URL rút gọn: https://onelink-sim.onelink.me/Il2C/70e6d165?c=bananas&af_adset=fruits
> * Tham số **af\_adset=fruits** được thêm vào URL rút gọn có tác dụng trong việc phân bổ. Tuy nhiên, tham số **c = bananaskhông có tác dụng** vì đã có tham số **c** trong URL đầy đủ.

</Accordion>

<div id="what-custom-media-source-names-can-i-use" />

<Accordion title="Tôi có thể sử dụng tên kênh truyền thông tùy chỉnh nào?">

Đối với phương tiện truyền thông sở hữu, tên kênh truyền thông tùy chỉnh có thể là bất kỳ tên nào. Tuy nhiên, không nên dùng *organic* làm tên kênh truyền thông tùy chỉnh vì điều này có thể ảnh hưởng đến tính toàn vẹn của dữ liệu phân bổ.

Nếu bạn sử dụng OneLink cho phương tiện truyền thông trả phí:

* Sử dụng các giá trị **PID** dành riêng cho đối tác tích hợp (các giá trị kết thúc bằng **\_int**), làm giá trị kênh truyền thông trong liên kết tùy chỉnh OneLink. Không sử dụng các kênh truyền thông SRN như *googleadwords* hoặc *facebook* làm tên kênh truyền thông tùy chỉnh. Điều này có thể ảnh hưởng đến tính toàn vẹn dữ liệu phân bổ.
* Đảm bảo đối tác được tích hợp với AppsFlyer và hoạt động (nút chuyển đổi **Activate partner** phải bật) cho mọi ứng dụng được thiết lập trong mẫu OneLink.

</Accordion>

<div id="what-attribution-parameters-can-be-added-to-a-onelink" />

<Accordion title="Có thể thêm những tham số phân bổ nào vào OneLink?">

Bạn có thể thêm nhiều tham số phân bổ để cho phép bạn thực hiện việc phân tích chi tiết.

| **Tham số phân bổ** | **Mô tả** | **Tên liên kết tham số** |
| --- | --- | --- |
| **Chiến dịch** | Đặt tên chiến dịch để so sánh các chiến dịch khác nhau trong kênh truyền thông sở hữu | c |
| **Bộ quảng cáo** | Đặt tên bộ quảng cáo để so sánh các bộ quảng cáo khác nhau trong các chiến dịch cụ thể của kênh truyền thông sở hữu | af\_adset |
| **Tên Quảng cáo** | Đặt tên quảng cáo để so sánh các quảng cáo khác nhau trong các bộ quảng cáo/chiến dịch cụ thể của kênh truyền thông sở hữu | af\_ad |
| **Kênh** | Đặt tên kênh nếu bạn muốn so sánh nhiều kênh phân phối cho kênh truyền thông sở hữu của mình.<br /><br />Ví dụ: Nếu bạn tách tin nhắn SMS giữa hai nhà cung cấp dịch vụ SMS, hãy chỉ định nhà cung cấp bằng cách sử dụng tham số kênh. Sau đó, bạn có thể so sánh tỷ lệ chuyển đổi của hai nhà cung cấp. | af\_channel |
| **Tham số Người đăng ký** | Sử dụng bất kỳ tham số nào trong số 5 tham số người đăng ký có sẵn để chèn các giá trị hữu ích cho phân tích của bạn.<br /><br />**Lưu ý:** Các tham số này được phân tích và xuất hiện trong các báo cáo dữ liệu thô, điều này giúp chúng trở nên hữu ích trong việc thực hiện tổng hợp hoặc lọc dữ liệu. | af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5 |
| **Tham số Tùy chỉnh** | Tương tự như tham số người đăng ký, bạn có thể chỉ định các trường với bất kỳ tên và giá trị tham số nào và bất kỳ tên nào.<br /><br />Không giống như tham số người đăng ký, tham số tùy chỉnh không được phân tích trong dữ liệu thô; chúng chỉ xuất hiện trong các báo cáo dữ liệu thô trong cột **url gốc**. | Tùy chỉnh  <br />(như bạn chỉ định) |

Xem thêm thông tin về các <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters">Tham số và cấu trúc liên kết phân bổ của AppsFlyer</Anchor>.

</Accordion>

<div id="are-custom-parameters-added-to-onelink-custom-links-available-in-raw-data" />

<Accordion title="Các tham số tùy chỉnh được thêm vào liên kết tùy chỉnh OneLink có sẵn trong dữ liệu thô không?">

**Có.** Các tham số tùy chỉnh được chuyển đến cột **url gốc** trong dữ liệu thô và có thể được nhìn thấy ở đó. Chúng không có cột riêng trong dữ liệu thô.

Đối với dữ liệu được phân tích cú pháp, hãy sử dụng tham số người đăng ký `af_sub1-5`, mỗi tham số có một cột riêng trong báo cáo dữ liệu thô.

</Accordion>

<div id="are-parameter-names-case-sensitive" />

<Accordion title="Tên tham số có phân biệt chữ hoa chữ thường không?">

**Có.** Đảm bảo bạn chỉ dùng chữ cái viết thường cho các tham số và giá trị của mình. Chữ viết hoa hoặc Viết hoa không thống nhất tên tham số và giá trị có thể gây ra lỗi hoặc sai lệch dữ liệu, cả trên bảng điều khiển và trong dữ liệu thô.

</Accordion>

<div id="integrated-partner-faq" />

### Câu hỏi thường gặp về đối tác tích hợp

<div id="can-i-use-onelink-in-social-apps-unpaid" />

<Accordion title="Tôi có thể sử dụng OneLink trong các ứng dụng mạng xã hội (không trả phí) không?">

Bạn có thể cần sử dụng OneLink trong các bài đăng không trả phí trên các ứng dụng mạng xã hội vì người dùng tiềm năng xem được các bài đăng đó không thể được nhắm mục tiêu trước tùy theo thiết bị của họ.

Thật không may, các giới hạn và hạn chế đối với Liên kết Chung của iOS do một số ứng dụng mạng xã hội đặt ra làm phức tạp thêm cho việc sử dụng OneLink để nhận diện thiết bị cơ bản, chuyển hướng và phân bổ cũng như liên kết sâu. Trong một số trường hợp nhất định, có thể cần thiết lập trang đích Ứng dụng mạng xã hội hoặc lược đồ URI để chuyển hướng hoặc liên kết sâu người dùng.

Bảng sau đây tóm tắt thời điểm OneLink có thể được sử dụng trong các ứng dụng mạng xã hội phổ biến hiện nay:

<table><thead><tr><th>Ứng dụng mạng xã hội</th><th>Người dùng Android chưa cài đặt ứng dụng</th><th>Liên kết sâu Android</th><th>Người dùng iOS chưa cài đặt ứng dụng</th><th>Liên kết sâu iOS</th></tr></thead><tbody><tr><td> <strong>Facebook</strong> (bao gồm các bài đăng được tăng cường)</td><td><span>✓\*\*<span>†</span><span>† </span></span></td><td><span>✓\*\*</span></td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Facebook Messenger</strong></td><td><span>✓\*\*<span>†</span><span>† </span></span></td><td> <span>✓\*\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Snapchat</strong></td><td><span>✓<span>†</span><span>† </span></span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Instagram</strong></td><td><span>✓<span>†</span><span>† </span></span></td><td><span>✓</span></td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>LinkedIn</strong></td><td><span>✓</span></td><td><span>✓\*\*</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td><strong>Reddit</strong></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td><strong>Slack</strong></td><td><span>✓</span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>X (trước đây là Twitter)</strong></td><td><span>✓</span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>WeChat</strong></td><td><span>✓<span>† </span></span></td><td><span>✓<span>† </span> </span></td><td><span>✓\*</span></td><td><span>✓\*<span>† </span></span></td></tr><tr><td><strong>WhatsApp</strong></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="5"><p>\* Nếu <a href="./onelink-troubleshooting-and-faq#which-operating-systems-allow-uri-schemes-to-open-the-app">lược đồ URI</a> hoặc trang đích Ứng dụng mạng xã hội được thiết lập. <strong>Lưu ý</strong>: Đối với Facebook và Facebook Messenger, nếu cả lược đồ URI và trang đích của Ứng dụng mạng xã hội đều được thiết lập, thì trang đích của Ứng dụng mạng xã hội sẽ không hiển thị.</p><p>\*\* Phải có lược đồ URI.</p><p><span>†</span> Người dùng có thể được nhắc mở liên kết trong trình duyệt bên ngoài.</p><p><span>†</span><span>† </span><span><span>Các ứng dụng mạng xã hội Android Giới hạn việc chuyển hướng liên kết sâu trong chế độ WebView. Xem chi tiết <a href="./create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#android-social-apps-webview-deep-linking-redirection" target="_blank">tại đây</a>.</span></span></p></td></tr></tbody></table>

</Accordion>

<div id="can-i-use-onelink-with-ad-networks-paid" />

<Accordion title="Tôi có thể sử dụng OneLink với các mạng quảng cáo (trả phí) không?">

**Có,** nhưng lưu ý rằng OneLink chủ yếu được sử dụng với mạng truyền thông sở hữu, không phải với mạng quảng cáo. Điều này là do mạng quảng cáo thường quảng cáo trong ứng dụng (có nghĩa là họ biết nền tảng của người dùng, ID thiết bị, v.v.), liên kết phân bổ cụ thể cho ứng dụng và nền tảng là đủ, vì vậy việc sử dụng OneLink là không cần thiết. Tuy nhiên, đối với các trường hợp mạng quảng cáo không biết trước về nền tảng người dùng (ví dụ: khi họ tự chạy các chiến dịch email hoặc SMS), OneLink có thể là giải pháp.

<div id="important" />

> 🚧 **Quan trọng!**
>
> Khi sử dụng OneLink với các mạng quảng cáo, bạn phải sử dụng URL đầy đủ của OneLink.

**Để thiết lập OneLink cho mạng quảng cáo đối tác:**

* Thực hiện theo <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#attribution-link-tab">hướng dẫn liên kết phân bổ mạng quảng cáo</Anchor> rồi chọn **Use OneLink** khi được nhắc.

Sau khi tất cả các tham số cho Android và iOS được thêm vào đúng cách, khi liên kết tùy chỉnh OneLink được nhấp vào và người dùng được chuyển hướng đến nền tảng phù hợp, các tham số bắt buộc sẽ được gửi đến mạng trong một lượt đăng lại sau khi người dùng cài đặt.

<div id="tip-4" />

> 📄 **Ví dụ**
>
> ```http
> https://greatapp.onelink.me/3287867539?pid=network_int&c=email&
> idfa{$IDFA}&gaid={$GAID}&clickid=$SITEID&
> af_sub1=[pixel_code]&af_sub2=[creative]
> ```
>
> Mạng sử dụng các tham số của IDFA hoặc GAID theo nền tảng thiết bị của khách và bỏ qua tham số khác.

</Accordion>

<div id="how-can-i-solve-the-ios-applaunching-issue-from-social-media-apps" />

<Accordion title="Làm cách nào để khắc phục sự cố khởi chạy ứng dụng iOS từ các ứng dụng mạng xã hội?">

Facebook và các ứng dụng mạng xã hội khác đôi khi chặn Liên kết Chung iOS mở ứng dụng. <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Trang đích ứng dụng mạng xã hội</Anchor> là giải pháp khuyên dùng cho các sự cố khởi chạy ứng dụng này.

Nếu không muốn sử dụng trang đích Ứng dụng mạng xã hội, bạn có thể sử dụng lược đồ URI làm phương án dự phòng. Tuy nhiên, lưu ý:

* Việc sử dụng lược đồ URI làm phương án dự phòng phải tuân theo các giới hạn chế dựa trên iOS.
* Đối với nhiều trình duyệt, bao gồm cả Safari, bạn phải thêm tham số `af_force_deeplink=true` vào URL để có thể sử dụng lược đồ URI làm phương án dự phòng. <Anchor target="_blank" href="/marketers/vi/docs/uri-scheme-fallback-for-ios">Tìm hiểu thêm</Anchor>.

</Accordion>

<div id="can-i-use-onelink-on-instagram" />

<Accordion title="Tôi có thể sử dụng OneLink trên Instagram không?">

**Có,** nhưng hãy lưu ý những hạn chế sau:

* Do cách Instagram kết xuất văn bản của bài đăng trên trang, các liên kết không thể nhấp vào được khi được nhập vào đoạn chú thích của bài đăng.
* Việc mở ứng dụng và liên kết sâu vào các ứng dụng Android được hỗ trợ mà không có lưu ý đặc biệt nào. Tuy nhiên, Instagram không hỗ trợ mở ứng dụng và liên kết sâu vào ứng dụng iOS. Để khắc phục sự cố này, bạn có thể thực hiện một trong hai cách:

  * **Đề xuất:** Cấu hình <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">trang đích Ứng dụng mạng xã hội</Anchor>. Các mẫu Áp phích Gộp và Trình bày & Chia sẻ hoạt động tốt nhất. Ngoài trang đích Mạng xã hội, chúng tôi đề nghị bạn nên cài đặt lược đồ URI trong mẫu OneLink của mình.
  * Sử dụng lược đồ URI và [liên kết sâu bắt buộc](/docs/onelink-troubleshooting-and-faq#liên-kết-sâu-bắt-buộc) khi sử dụng OneLinks trên Instagram. Hãy nhớ ghi nhớ những điểm sau khi sử dụng `af_force_deeplink=true` với OneLink trên Instagram:  

| Bạn đã cài đặt ứng dụng? | Nhấp vào có af\_force\_deeplink=true? | Kết quả |
| --- | --- | --- |
| Không | Có | Nhấp sẽ mở cửa hàng ứng dụng |
| Không | Không | Nhấp sẽ mở cửa hàng ứng dụng |
| Có | Có | Nhấp sẽ mở ứng dụng |
| Có | Không | Nhấp sẽ mở cửa hàng ứng dụng |

</Accordion>

<div id="can-i-use-onelink-for-redirection-on-wechat" />

<Accordion title="Tôi có thể dùng OneLink để chuyển hướng trên WeChat không?">

WeChat ghi đè liên kết sâu Android và iOS và chuyển hướng người dùng đến một trang web. Từ trang web này, người dùng phải nhấp vào nút **Options** và chọn để mở trang trong trình duyệt. Kết quả là người dùng có trải nghiệm không liền mạch và tăng khả năng họ từ bỏ trong phễu chuyển đổi.

Để khắc phục, OneLink nhận diện lượt nhấp chuột trong WeChat và tải một trang đích riêng hướng dẫn người dùng nhấp vào nút tùy chọn và nhấp vào **Open in Browser**. Như thế sẽ mở ra URL chuyển hướng được xác định trong thiết lập mẫu OneLink.

![WeChat_a.jpg](https://files.readme.io/49c03a10d458f6ce71fd6448e922294682ac9239775534c6264c29151ec1ea6d-30192900489105.jpg)

Nếu ngôn ngữ WeChat của người dùng được đăng ký là tiếng Trung, OneLink sẽ tạo một phiên bản được bản địa hóa của trang đích:

![WeChat_b.jpg](https://files.readme.io/502ef821a122459ab991f2a507c720f25fcac7129eb647a01290e8cabfa7a34e-30192887085841.jpg)

</Accordion>

<div id="why-are-android-users-with-the-app-installed-being-redirected-to-a-web-url-and-not-into-the-app-when-they-click-a-link-on-facebook-webview" />

<Accordion title="Tại sao người dùng Android có cài đặt ứng dụng được chuyển hướng đến URL web và không phải vào ứng dụng khi họ nhấp vào liên kết trên chế độ xem web của Facebook?">

Bạn thường có thể mở ứng dụng và liên kết sâu từ quảng cáo trên Facebook. Tuy nhiên, nếu áp dụng các điều kiện sau, Facebook không thể mở ứng dụng cho người dùng ứng dụng hiện tại từ URL OneLink. Thay vào đó, tất cả người dùng, bao gồm cả những người có ứng dụng, được gửi đến URL được xác định trong mẫu OneLink hoặc trong giá trị của tham số **af\_android\_url**, **af\_r** hoặc **af\_custom\_android\_url**:

* Người dùng có thiết bị di động Android.
* Liên kết được nhấp trên ứng dụng Facebook.
* Liên kết dẫn đến trang HTML mở trong chế độ xem web của Facebook (là trang hoặc trang đích của ứng dụng mạng xã hội).
* Trang HTML chứa liên kết có cả tham số **af\_dp** (với lược đồ URI) và cài đặt chuyển hướng URL trong mẫu OneLink hoặc trong tham số (một trong **af\_android\_url**, **af\_r** hoặc **af\_custom\_android\_url**).

</Accordion>

<div id="testing-faq" />

### Câu hỏi thường gặp về thử nghiệm

<div id="how-can-i-ab-test-the-social-app-landing-page" />

<Accordion title="Làm cách nào tôi có thể thực hiện thử nghiệm A/B trang đích Ứng dụng mạng xã hội?">

<Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Trang đích ứng dụng mạng xã hội</Anchor> mang đến cho người dùng trải nghiệm khởi chạy ứng dụng liền mạch khi sử dụng OneLink trong các ứng dụng mạng xã hội. Bạn có thể lo ngại rằng việc thêm một bước vào phễu sẽ làm giảm tỷ lệ chuyển đổi. Nhưng sự thật là, nếu không có trang đích, hành trình của người dùng thường bị gián đoạn, dẫn đến tỷ lệ chuyển đổi rất thấp.

Nếu bạn vẫn chưa tin chắc hoàn toàn, tại sao lại không thử nghiệm cách này nhỉ?

<Anchor target="_blank" href="/marketers/vi/docs/create-a-b-tests">Thực hiện thử nghiệm A/B</Anchor> liên kết tùy chỉnh của bạn trong ứng dụng mạng xã hội, có và không có trang đích Ứng dụng mạng xã hội.

**Để thực hiện thử nghiệm A/B trang đích Ứng dụng mạng xã hội:**

1. <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Tạo liên kết OneLink</Anchor> (được gọi là Link1) để sử dụng với các ứng dụng mạng xã hội. Không đặt trang đích Ứng dụng mạng xã hội cho liên kết này.
2. Thêm tham số phân bổ **af\_adset**.
3. Thêm tham số phân bổ **af\_ad** với giá trị "no lp".
4. Thử nghiệm Liên kết 1 bên ngoài các ứng dụng mạng xã hội và xác minh rằng liên kết hoạt động và khởi chạy ứng dụng của bạn một cách chính xác.
5. Sao chép Liên kết 1 và đặt tên là Liên kết 2.
6. Thay đổi giá trị tham số phân bổ **af\_ad** thành "using lp".
7. <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Tạo trang đích Ứng dụng mạng xã hội</Anchor> chỉ cho Liên kết 2.
8. Đăng 2 bài đăng khác nhau trong **cùng** một ứng dụng mạng xã hội, sử dụng Link1 và Link2.  
   Đừng lo lắng về số lượt nhấp chuột khác nhau mà mỗi liên kết tạo ra. KPI quan trọng là tỷ lệ chuyển đổi cuối cùng của mỗi liên kết.
9. **Kiểm tra kết quả thử nghiệm A/B sau khi tạo đủ lưu lượng truy cập.**
   1. Đi tới Bảng điều khiển tổng quan của AppsFlyer và cuộn xuống bảng **Aggregated performance report**.
   2. Liên kết 1 và Liên kết 2 có cùng kênh truyền thông, chiến dịch và tên bộ quảng cáo. Truy cập sâu vào bộ quảng cáo cụ thể.
   3. So sánh tỷ lệ chuyển đổi (và các KPI khác) của những người dùng đã nhấp vào Liên kết 1 hoặc Liên kết 2.

</Accordion>

<div id="how-can-i-bypass-the-app-selection-dialog" />

<Accordion title="Làm cách nào để bỏ qua hộp thoại lựa chọn ứng dụng?">

Nếu bạn thấy hộp thoại chọn ứng dụng khi thử nghiệm OneLinks của mình, hãy đảm bảo <Anchor target="_blank" href="https://developer.android.com/studio/publish/app-signing">ký ứng dụng của bạn</Anchor> ngay cả khi đó là <Anchor target="_blank" href="https://developer.android.com/studio/publish/app-signing#debug-mode">ứng dụng gỡ lỗi.</Anchor> Chứng chỉ bạn sử dụng để ký ứng dụng cũng chính là chứng chỉ bạn sử dụng để <Anchor target="_blank" href="https://dev.appsflyer.com/docs/initial-setup-for-deep-linking-and-deferred-deep-linking#generating-a-sha256-fingerprint">tạo dấu vân tay SHA256</Anchor> khi cấu hình OneLink cho Liên kết Ứng dụng.

</Accordion>

<div id="deep-linking-faq" />

### Câu hỏi thường gặp về liên kết sâu

<div id="what-deep-linking-methods-should-be-implemented" />

<Accordion title="Cần triển khai phương thức liên kết sâu nào?">

Nhà phát triển của bạn nên triển khai phương thức liên kết sâu thống nhất (UDL) cho liên kết sâu. Xem <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">hướng dẫn liên kết sâu</Anchor> đầy đủ của chúng tôi.

Liên kết Chung và Liên kết Ứng dụng Android là **các phương thức khởi chạy ứng dụng, không thực sự liên kết sâu người dùng** (đưa họ đến nội dung cụ thể trong ứng dụng). Phương thức lược đồ URI có thể khởi chạy ứng dụng và liên kết sâu người dùng (thông qua tham số liên kết tùy chỉnh **af\_dp**), nhưng phương thức chỉ nên được cấu hình để khởi chạy ứng dụng. Cách sử dụng chính của nó là như một phương án dự phòng cho Liên kết Chung và Liên kết Ứng dụng cũng như cho người dùng khởi chạy ứng dụng có phiên bản hệ điều hành Android 6.0 trở xuống.

Sau khi ứng dụng được khởi chạy bằng bất kỳ phương thức nào trong số này, SDK AppsFlyer cung cấp **deep\_link\_value** được chỉ định trong liên kết phân bổ tùy chỉnh. Giá trị này phải được phân phối thông qua phương thức UDL do các nhà phát triển của bạn triển khai.

</Accordion>

<div id="can-a-uri-scheme-af_dp-parameter-be-used-for-deep-linking" />

<Accordion title="Có thể sử dụng lược đồ URI (tham số af_dp) để liên kết sâu không?">

**Có,** nhưng không được khuyên dùng. Tốt nhất, bạn nên sử dụng **deep\_link\_value** để liên kết sâu và lược đồ URI như một phương án dự phòng để khởi chạy ứng dụng mà không cần liên kết sâu (thông qua tham số **af\_dp**). Tuy nhiên, nếu bạn đã thiết lập lược đồ URI thành liên kết sâu, với các tham số bổ sung được nối như một phần của đường dẫn URI (ví dụ: greatapp://param1/param2), bạn không cần phải thay đổi cấu hình hoặc mã hiện có của bạn; lược đồ URI sẽ tiếp tục hoạt động. 

**Cách tốt nhất để thêm tham số tùy chỉnh là thông qua trang thiết lập liên kết tùy chỉnh**.

</Accordion>

<div id="ios-14-faq" />

### Câu hỏi thường gặp về iOS 14

<div id="does-onelink-deep-linking-work-for-ios-14" />

<Accordion title="Liên kết sâu OneLink có tác dụng với iOS 14 không?">

Không có tác động trải nghiệm người dùng nào đối với người dùng iOS 14 được liên kết sâu từ các chiến dịch trên mạng quảng cáo và phương tiện truyền thông sở hữu bằng phương thức UDL. Phương thức kế thừa này có thể cản trở việc liên kết sâu.

Đối với mục đích phân bổ/báo cáo, AppsFlyer sử dụng IDFA hoặc IDFV khi có sẵn. Nếu không có IDFA hoặc IDFV, có thể sẽ sử dụng mô hình xác suất. Bắt đầu từ phiên bản iOS 14.5 trở lên, mô hình xác suất được giới hạn ở trường hợp truyền thông sở hữu, quảng cáo chéo và các luồng chuyển đổi từ web đến ứng dụng đã có sự đồng thuận của người dùng.

</Accordion>

<div id="does-onelink-deferred-deep-linking-work-for-ios-14" />

<Accordion title="Liên kết sâu gián tiếp OneLink có hoạt động với iOS 14 không?">

Không có tác động trải nghiệm người dùng nào đối với người dùng iOS 14 được liên kết sâu gián tiếp từ các chiến dịch trên mạng quảng cáo và phương tiện truyền thông sở hữu bằng phương thức UDL. Phương thức kế thừa này có thể cản trở việc liên kết sâu gián tiếp.

Đối với mục đích phân bổ/báo cáo, AppsFlyer sử dụng IDFA hoặc IDFV khi có sẵn. Nếu không có IDFA hoặc IDFV, có thể sẽ sử dụng mô hình xác suất. Bắt đầu từ phiên bản iOS 14.5 trở lên, mô hình xác suất được giới hạn ở trường hợp truyền thông sở hữu, quảng cáo chéo và các luồng chuyển đổi từ web đến ứng dụng đã có sự đồng thuận của người dùng. Chúng tôi khuyến khích những khách hàng muốn triển khai liên kết sâu gián tiếp từ các mạng quảng cáo và phương tiện truyền thông sở hữu nên sử dụng SDK iOS AppsFlyer V6.1.0 trở lên để cho phép chấp thuận ATT (nếu cần), giảm thiểu bất kỳ tác động phân bổ nào và có được thời gian phản hồi nhanh hơn.

</Accordion>

<div data-zendesk-anchors="onelink-troubleshooting-guide=h%C6%B0%E1%BB%9Bng-d%E1%BA%ABn-kh%E1%BA%AFc-ph%E1%BB%A5c-s%E1%BB%B1-c%E1%BB%91-onelink 01H7WPYJV9CQ1J6J3PFCEQFGB0=h%C6%B0%E1%BB%9Bng-d%E1%BA%ABn-kh%E1%BA%AFc-ph%E1%BB%A5c-s%E1%BB%B1-c%E1%BB%91-onelink onelink-frequently-asked-questions=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-onelink 01H7WPYJV9H52P659N8JPRX2TY=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-onelink onelink-template-faq=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-m%E1%BA%ABu-onelink 01H7WPYJV9TJRKHFZ77DFMKDDG=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-m%E1%BA%ABu-onelink which-method-should-i-use-for-opening-apps%E2%80%94universal-links-app-links-or-uri-schemes=which-method-should-i-use-for-opening-apps-universal-links-app-links-or-uri-schemes 01H7WPYJV9JQG66S3K7TRHMFHA=which-method-should-i-use-for-opening-apps-universal-links-app-links-or-uri-schemes 01H7WPYJV9TV402AGAAGYARATW=l%C6%B0u-%C3%BD deep-linking=li%C3%AAn-k%E1%BA%BFt-s%C3%A2u 01H7WPYJV9JSQ5FV73YCE3H5AF=li%C3%AAn-k%E1%BA%BFt-s%C3%A2u 01H7WPYJV9CMQAQZ56P5P2MDBV=which-operating-systems-allow-uri-schemes-to-open-the-app 01H7WPYJV975A2YS61MQM1WX4W=do-i-need-to-update-the-app-after-ios-universal-links-and-android-app-links-setup 01H7WPYJV9GPXDP0KSQEPZXJCH=can-i-redirect-existing-users-to-a-web-page-instead-of-the-app 01H7WPYJV9A266QMK2J1K2AQXR=can-i-redirect-tablet-users-to-a-different-app-or-url-then-mobile-app-users 01H7WPYJV9DCVNRR3NNF7JMR0D=can-i-assign-an-app-to-multiple-onelink-templates 01H7WPYJV90RVHSAWA2YHBNNHA=can-i-delete-a-onelink-template 01H7WPYJV9RPNG3Z94630B789K=can-i-change-the-subdomain-in-a-onelink-template 01H7WPYJV9C0H3ZH6F6F3E43WH=can-the-domainsubdomain-of-a-onelink-template-be-applied-to-the-template-id-of-another-template 01H7WPYJV9246X8821B943N9AD=can-i-use-the-same-subdomain-for-more-than-one-template 01H7WPYJVAFBS0Y56NWN8M979B=how-can-i-redirect-desktop-users 01H7WPYJVA6PWA88VD8V0B3M74=m%E1%BA%B9o 01H7WPYJVAB57R0VQAS7C0D9NK=how-can-i-redirect-chrome-os-users onelink-link-faq=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-li%C3%AAn-k%E1%BA%BFt-onelink 01H7WPYJVAPNYAQ1SH4FBX4Z9F=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-li%C3%AAn-k%E1%BA%BFt-onelink 01H7WPYJVAEQQDSJ298M8JV361=does-onelink-work-without-the-appsflyer-sdk 01H7WPYJVA8XASRX9X3QVAWYS9=what-methods-are-available-for-creating-onelink-custom-links 01H7WPYJVATBVVMEPNAVBW9ZFZ=can-onelink-custom-links-open-the-app-from-a-browser 01H7WPYJVAWJ9BFYBXM6DJ3V22=why-doesnt-the-onelink-url-open-the-app-or-deep-link-existing-users fallback-urls=url-d%E1%BB%B1-ph%C3%B2ng 01H7WPYJVACCGVJD1Z7ZPVG2SQ=url-d%E1%BB%B1-ph%C3%B2ng 01H7WPYJVAHXE4M12X94T9C7A5=v%C3%AD-d%E1%BB%A5 01H7WPYJVAEMX54GZAX166FPS7=l%C6%B0u-%C3%BD-1 forced-deep-linking=li%C3%AAn-k%E1%BA%BFt-s%C3%A2u-b%E1%BA%AFt-bu%E1%BB%99c 01H7WPYJVA1W3HYYJJFQM01136=li%C3%AAn-k%E1%BA%BFt-s%C3%A2u-b%E1%BA%AFt-bu%E1%BB%99c 01H7WPYJVAWSD03E141SZEN2J9=why-does-my-onelink-url-open-a-blank-page-in-chrome 01H7WPYJVAV93G4EGDH2A91XMP=can-i-use-onelink-for-redirection-on-brave 01H7WPYJVAJQ6FKWDK8MNZAZT3=do-onelink-custom-links-take-longer-to-load-than-other-links 01H7WPYJVAX7P2YCBV1K1DCGEJ=how-can-i-record-the-cost-per-install-when-using-onelink 01H7WPYJVAEFX5306YA4GA45FW=v%C3%AD-d%E1%BB%A5-1 01H7WPYJVAQZJQYX3H5V8YTC27=how-can-i-prevent-parameter-forwarding-on-redirections 01H7WPYJVAYVK3A77Q35H1ENKF=how-can-i-remove-appsflyer-pid-and-c-parameters-when-forwarding-while-keeping-all-other-parameters-on-redirection-urls 01H7WPYJVA89118V5Y2DSM67Y4=are-singleplatform-custom-links-still-available 01H7WPYJVANDKXGFKYXZ6CKHSF=can-i-change-the-short-url-id-after-saving-a-link 01H7WPYJVAC2WXXY43WEYKVPYP=can-i-wrap-and-shorten-onelink-custom-links 01H7WPYJVANTMSMGZ6VP36DTV1=can-i-use-onelink-custom-links-in-emails 01H7WPYJVAE0TSRPPTD21X9Q4V=how-do-users-get-redirected-to-their-regional-app-store 01H7WPYJVA4W7YFMQD4HEE313P=why-isnt-my-onelink-url-redirecting-users-to-the-specified-domain h_01HAKSWWMSHVW9KFWA34XGXWN2=can-i-manually-switch-between-the-branded-domain-and-its-onelink-subdomain-in-an-existing-link onelink-parameter-faq=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-tham-s%E1%BB%91-onelink 01H7WPYJVAGRVWHRVMZVQG1ZVE=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-tham-s%E1%BB%91-onelink 01H7WPYJVBCS3JZ98FYMAPY2YT=what-parameters-are-mandatory-for-onelink-custom-links 01H7WPYJVBCD7GG37JZTF919YQ=can-parameters-be-appended-to-the-short-url 01H7WPYJVB15Q3YAVJ8M7EQ1FW=v%C3%AD-d%E1%BB%A5-2 01H7WPYJVBNTKJM3F72ZEZG32Z=what-custom-media-source-names-can-i-use 01H7WPYJVB25VGB37D3DZ2J786=what-attribution-parameters-can-be-added-to-a-onelink 01H7WPYJVBSQBR8E9NY0GJ3APT=are-custom-parameters-added-to-onelink-custom-links-available-in-raw-data 01H7WPYJVB3CCB838A7N6K932G=are-parameter-names-case-sensitive integrated-partner-faq=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-%C4%91%E1%BB%91i-t%C3%A1c-t%C3%ADch-h%E1%BB%A3p 01H7WPYJVB8ZZSKFT1V01EN6QF=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-%C4%91%E1%BB%91i-t%C3%A1c-t%C3%ADch-h%E1%BB%A3p 01H7WPYJVBCQNPTEZPM8KFE6YX=can-i-use-onelink-in-social-apps-unpaid 01H7WPYJVBTBQKK50JR179S7MW=can-i-use-onelink-with-ad-networks-paid 01H7WPYJVBJ0DX0MZPGXYF76EP=quan-tr%E1%BB%8Dng 01H7WPYJVBB9KJRZQTFZDG7NDK=v%C3%AD-d%E1%BB%A5-3 01H7WPYJVB60DFMHN8PCVFC5S9=how-can-i-solve-the-ios-applaunching-issue-from-social-media-apps 01H7WPYJVB94NGD94MW4HYDB5S=can-i-use-onelink-on-instagram 01H7WPYJVBT5PJHVAFD1TY6CDY=can-i-use-onelink-for-redirection-on-wechat 01H7WPYJVB05C8BXKRG0WGBJ8P=why-are-android-users-with-the-app-installed-being-redirected-to-a-web-url-and-not-into-the-app-when-they-click-a-link-on-facebook-webview testing-faq=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-th%E1%BB%AD-nghi%E1%BB%87m 01H7WPYJVC1PJJDA0GGT1DVVCF=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-th%E1%BB%AD-nghi%E1%BB%87m 01H7WPYJVCQ89S3R4X1111TRGZ=how-can-i-ab-test-the-social-app-landing-page 01H7WPYJVC20TXWKRB89XFTK1N=how-can-i-bypass-the-app-selection-dialog deep-linking-faq=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-li%C3%AAn-k%E1%BA%BFt-s%C3%A2u 01H7WPYJVCTM39HKCG9JN03BN6=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-li%C3%AAn-k%E1%BA%BFt-s%C3%A2u 01H7WPYJVCZMRN53QG5JNSB8MP=what-deep-linking-methods-should-be-implemented 01H7WPYJVC6BXRJGTJBY6KG8JX=can-a-uri-scheme-af_dp-parameter-be-used-for-deep-linking ios-14-faq=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-ios-14 01H7WPYJVCVCVWHJW4RH85KC40=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-ios-14 01H7WPYJVCFANQQ9T27M2YGGBD=does-onelink-deep-linking-work-for-ios-14 01H7WPYJVCBC9YMBQ6TV1B2SBV=does-onelink-deferred-deep-linking-work-for-ios-14" />
