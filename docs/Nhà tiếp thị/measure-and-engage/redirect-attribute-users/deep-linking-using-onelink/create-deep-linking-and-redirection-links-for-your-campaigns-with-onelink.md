---
title: Liên kết và trải nghiệm OneLink
metadata:
  keywords:
    - Marketers
    - onelink
    - Text-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Text-to-App
  created_at: '2016-05-22T10:03:37Z'
  edited_at: '2023-11-30T14:22:42Z'
  id: 208874366
  locale: vi
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/vi/articles/208874366
---
> **Khái quát:** [Tạo liên kết OneLink](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#tạo-liên-kết-onelink) mang đến cho người dùng chính xác trải nghiệm mà bạn mong muốn mang lại cho họ. Những người dùng nhấp vào liên kết sẽ được chuyển hướng đến đúng cửa hàng ứng dụng, URL web hoặc vào ứng dụng nếu cần. Và người dùng được phân bổ vào đúng nguồn truyền thông.

<div id="onelink-links-and-experiences" />

## Liên kết và trải nghiệm OneLink

<Embed title="Trình phát video YouTube" typeOfEmbed="youtube" url="https://www.youtube.com/embed/KZBrxGEjVUE" providerUrl="https://www.youtube.com" />

Khách hàng của bạn tương tác với thương hiệu của bạn trên nhiều điểm tiếp xúc trực tuyến và ngoại tuyến khác nhau. Bất kể người dùng của bạn đến từ đâu, bạn có thể tạo liên kết mang lại trải nghiệm lý tưởng cho họ, từ nhấp chuột, đến cài đặt ứng dụng, liên kết sâu đến deferred deep linking.

Các bước thiết lập liên kết cần thiết được mô tả chi tiết trong phần sau, nhưng về cơ bản, bao gồm các thao tác sau:

* Chọn trải nghiệm người dùng
* Cài đặt chung
* Cài đặt trải nghiệm cụ thể
* Cài đặt liên kết sâu và chuyển hướng
* Cài đặt thông số bổ sung

<div id="create-a-onelink-link" />

## Tạo liên kết OneLink

| **Đối tượng tham gia**<ul><li>Chỉ nhà tiếp thị phải tạo liên kết OneLink với trải nghiệm chuyển hướng người dùng đến cửa hàng ứng dụng, URL web hoặc sau khi mẫu được thiết lập để mở ứng dụng bằng Liên kết Ứng dụng Android và Liên kết Chung iOS, vào trang chủ của ứng dụng.</li><li>Để thêm liên kết sâu và chức năng deferred deep linking vào liên kết, cần có cả nhà tiếp thị và nhà phát triển Android/iOS.</li></ul> |
| --- |
| **Điều kiện tiên quyết**<ul><li>Tài khoản AppsFlyer có ít nhất một ứng dụng.</li><li><Anchor target="_blank" href="/marketers/vi/docs/create-a-onelink-template">Mẫu OneLink</Anchor> làm cơ sở cho các liên kết của bạn.</li><li>Để phân bổ: <Anchor target="_blank" href="/marketers/vi/docs/integrate-the-appsflyer-sdk">SDK AppsFlyer đã được cài đặt</Anchor> trong mỗi ứng dụng di động của bạn.<ul><li>Nếu SDK chưa được cài đặt trong ứng dụng của bạn, bạn vẫn có thể tạo liên kết chuyển hướng hoạt động, nhưng sẽ không thể đo lượt cài đặt trong bảng điều khiển, liên kết sâu hoặc liên kết sâu gián tiếp.</li></ul></li></ul> |
| **Thời gian cần thiết**<br /><br />30 phút cho hầu hết các liên kết, nhưng khoảng 3 giờ cho các liên kết yêu cầu chức năng liên kết sâu hoặc deferred deep linking. |
| **Kết quả**<ul><li>Một liên kết đưa người dùng đến đúng cửa hàng ứng dụng, trang web hoặc vào ứng dụng dựa trên thiết bị của họ và cung cấp cho họ chính xác trải nghiệm mà bạn mong muốn mang lại cho họ.</li></ul> |

**Để tạo liên kết OneLink với trải nghiệm người dùng cụ thể:**

1. Trong bảng điều khiển AppsFlyer, chuyển đến **Experiences & deep linking** > **OneLink management.**
2. Chọn **mẫu OneLink** để thêm liên kết tùy chỉnh cho.
3. Nhấp vào **Add link**.
4. Chọn [trải nghiệm](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#experiences) bạn muốn mang đến cho người dùng của mình.
5. Chọn một nguồn truyền thông hoặc nhập một nguồn truyền thông tùy chỉnh. Đây là nguồn truyền thông mà dữ liệu hiển thị trong AppsFlyer. Nguồn truyền thông được đưa vào liên kết của bạn dưới dạng giá trị thông số `pid`.
6. Nhấp vào **Next** (Tiếp theo).
7. Hoàn thành [**General settings**](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings).
8. Nhấp vào **Next** (Tiếp theo).
9. [Tùy chọn] Hoàn thành các quy trình liên quan đến trải nghiệm người dùng mà bạn đang tạo: 

| Trải nghiệm | Tùy chọn quy trình |
| --- | --- |
| <ul><li>Mạng xã hội sang ứng dụng</li><li>Tin nhắn sang ứng dụng</li><li>Giới thiệu sang ứng dụng</li><li>Liên kết tùy chỉnh</li></ul> | <ul><li>[Bản xem trước mạng xã hội](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags)</li><li>[Trang đích ứng dụng mạng xã hội](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page)</li></ul> |
| Email sang ứng dụng | Nếu bạn đang sử dụng ESP, hãy làm theo phần <Anchor target="_blank" href="/marketers/vi/docs/email-service-provider-esp-integration-guide">hướng dẫn tích hợp ESP</Anchor>. |
| Ứng dụng sang ứng dụng | Bạn có thể tạo các liên kết động hoạt động trên nhiều ứng dụng thông qua <Anchor target="_blank" href="/marketers/vi/docs/cross-promotion-attribution-for-marketers">quảng cáo chéo</Anchor>. |
| Liên kết giới thiệu sang ứng dụng | <ul><li>[Bản xem trước mạng xã hội](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags)</li><li>[Trang đích ứng dụng mạng xã hội](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page)</li><li>Bạn có thể tạo linh hoạt liên kết giới thiệu đến ứng dụng thông qua SDK trong ứng dụng của mình thông qua <Anchor target="_blank" href="/marketers/vi/docs/user-invite-attribution">tích hợp lời mời người dùng</Anchor>.</li></ul> |

10. Nhấp vào **Next** (Tiếp theo).
11. [Tùy chọn] Trong phần **Deep linking and redirection**, hãy hoàn tất [thiết lập liên kết sâu/deferred deep linking.](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking) Bỏ qua phần này nếu liên kết này không dành cho liên kết sâu.
12. [Tùy chọn] Trong phần **Deep linking and redirection**, hãy thay đổi [cài đặt chuyển hướng](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#redirection). Bỏ qua phần này nếu cài đặt chuyển hướng từ mẫu OneLink là chính xác.
13. Nhấp vào **Next** (Tiếp theo).
14. Trong phần **Additional parameters**, [hãy thêm thông số tùy chỉnh hoặc xác định trước](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#additional-parameters) vào liên kết của bạn để phân tích chi tiết hơn. <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters">Tìm hiểu thêm về thông số phân bổ</Anchor>
15. Nhấp vào **Generate link**.

<div id="experiences" />

<Accordion title="Trải nghiệm">

Bạn có thể tạo liên kết cho các trải nghiệm người dùng sau:

* **Mạng xã hội sang ứng dụng**: Thu hút người dùng trên mạng xã hội và chuyển họ từ bài đăng mạng xã hội đến ứng dụng của bạn.
* **Ứng dụng đến ứng dụng**: Đưa người dùng đến ứng dụng của bạn thông qua quảng cáo mà họ thấy được trong các ứng dụng khác.
* **Mã QR sang ứng dụng**: Sử dụng mã QR để thúc đẩy lượt cài đặt ứng dụng bằng cách yêu cầu người dùng quét mã QR tại các điểm chính trong trải nghiệm khách hàng ngoại tuyến của họ. Bạn cũng có thể đặt mã QR trên trang web dành cho máy tính để bàn hoặc trên quảng cáo TV và CTV để định hướng người dùng đến ứng dụng của bạn.
* **Email sang ứng dụng**: Sử dụng các nhà cung cấp dịch vụ email (ESP) để thu hút người dùng qua email và đưa họ từ hộp thư đến của họ đến ứng dụng của bạn.
* **Tin nhắn đến ứng dụng**: Tạo liên kết cho các chiến dịch SMS và tin nhắn của bạn và thu hút người dùng thông qua tin nhắn văn bản.
* **Liên kết giới thiệu đến ứng dụng**: Tạo liên kết lời mời người dùng cho phép người dùng hoặc những người có ảnh hưởng mời người khác đến ứng dụng của bạn hoặc chia sẻ nội dung cụ thể trong ứng dụng, chẳng hạn như một bài viết.
* **Liên kết tùy chỉnh**: Đối với hành trình của người dùng không phù hợp với một trong các trải nghiệm được đề cập ở trên, bạn có thể tạo liên kết tùy chỉnh OneLink. Sau đó, bất kể người dùng của bạn đến từ đâu, cho dù qua máy tính để bàn hay thiết bị di động, trực tuyến hay ngoại tuyến, nguồn truyền thông sở hữu hay trả phí, bạn đều có thể dễ dàng đưa họ đến đúng nơi mong muốn.

</Accordion>

<div id="general-settings" />

<Accordion title="Cài đặt chung">

Cài đặt chung là một phần của quy trình tạo liên kết OneLink áp dụng cho tất cả các trải nghiệm.

**Để hoàn thành cài đặt chung**:

1. [Tùy chọn] Thay đổi tên nguồn truyền thông.
2. [Tùy chọn] Thay đổi tên chiến dịch.
3. [Tùy chọn] Bật **Retargeting** nếu bạn có ý định sử dụng liên kết này để nhắm mục tiêu người dùng hiện có.  

   Điều này cho phép bạn xem các lượt thu hút lại được thực hiện bởi người dùng thực hiện thao tác nhấp vào liên kết tùy chỉnh của bạn.

   Người dùng hiện có nhấp vào liên kết không nhắm mục tiêu lại (UA) cũng khởi chạy ứng dụng và có cùng trải nghiệm người dùng. Tuy nhiên, các lượt thu hút lại của họ được ghi nhận dưới dạng phiên thông thường, điều đó có nghĩa là không thể đo lường sự thành công của chiến dịch truyền thông sở hữu.

   **Quan trọng**! Để nhắm mục tiêu lại có thể hoạt động, bạn cũng cần bật tính năng nhắm mục tiêu lại cho ứng dụng.
4. [Tùy chọn] Bật **Ignore active users for retargeting** và chọn khung thời gian không hoạt động.  
   Điều này sẽ thêm thông số af\_inactivity\_window=[số ngày] vào liên kết của bạn và tất cả người dùng hoạt động trong khoảng thời gian này sẽ bị bỏ qua đối với nhắm mục tiêu lại.
5. Đặt khung thời gian thu hút lại để xác định khoảng thời gian sau thu hút lại, nơi các sự kiện trong ứng dụng của người dùng được phân bổ cho nguồn truyền thông nhắm mục tiêu lại.

   * Bạn có thể đặt giá trị theo ngày (1-90), giờ (tối đa 23) hoặc thậm chí là trọn đời.
   * Khung thời gian thu hút lại được thêm vào liên kết trong thông số af\_reengagement\_window.
6. [Tùy chọn] Trong tiểu mục **Link branding**:
   * Chọn một miền khác để phản ánh thương hiệu của bạn. <Anchor target="_blank" href="/marketers/vi/docs/brand-onelink-with-your-domain">Tìm hiểu thêm</Anchor>
   * Chỉnh sửa ID URL để làm nổi bật các dịch vụ cung cấp của chiến dịch. ID URL phải có tối đa 50 ký tự và có thể sử dụng kết hợp chữ cái và số. Theo mặc định, ID này gồm 8 ký tự.

<div id="enable-retargeting-for-the-app" />

#### Bật tính năng nhắm mục tiêu lại cho ứng dụng

Nếu chưa từng bật tính năng Nhắm mục tiêu lại cho ứng dụng, thì bạn cần phải thực hiện thao tác đó một lần. <Anchor target="_blank" href="/marketers/vi/docs/app-settings#cài-đặt-phân-bổ">Tìm hiểu thêm</Anchor>

**Để cài đặt Nhắm mục tiêu lại ở cấp ứng dụng:**

1. Trong bảng điều khiển AppsFlyer, đi tới **Configuration** > **App Settings**.
2. Trong phần**Phân bổ** này, hãy bật **Phân bổ thu hút lại**.
3. Nhấp vào **Save settings**.

</Accordion>

<div id="social-media-preview-og-tags" />

<Accordion title="Xem trước mạng xã hội - thẻ OG">

Khi một liên kết được chia sẻ, các thẻ open graph (OG) được sử dụng để tạo bản xem trước có tiêu đề, mô tả và hình ảnh.

Các thẻ OG này có thể được lấy tự động từ URL web hoặc cửa hàng ứng dụng mà bạn đang chuyển hướng đến. Tuy nhiên, đôi khi phương thức tạo bản xem trước này sẽ không thành công. Do đó, chúng tôi đề nghị bạn nên đặt bản xem trước trên mạng xã hội của mình trong OneLink, hoặc sử dụng UI OneLink hoặc thêm thông số thẻ OG vào liên kết của bạn đối với các liên kết không được tạo trong UI OneLink.

Tính năng Bản xem trước trên mạng xã hội được hỗ trợ bởi các nền tảng sau:

* Facebook: bài đăng và Tin nhắn Trực tiếp
* X (trước đây là Twitter): bài đăng và Tin nhắn Trực tiếp
* iMessage
* WhatsApp
* LinkedIn: bài đăng và Tin nhắn Trực tiếp
* Line
* Telegram
* Slack
* Signal
* KakaoTalk
* Discord
* Reddit

**Để tạo bản xem trước trên mạng xã hội của riêng bạn trong UI OneLink:**

1. Trong trình chỉnh sửa liên kết tùy chỉnh OneLink, hãy đi đến phần **Share on social media**.
2. Trong phần **Social media preview**, hãy nhập:
   * Tiêu đề
   * Mô tả
   * URL hình ảnh

**Để thêm thông số thẻ OG vào liên kết của bạn**(nếu liên kết không được tạo trong giao diện người dùng OneLink):

* Thêm các thông số bắt buộc sau:
  * af\_og\_title (tối đa 40 ký tự)
  * af\_og\_description (tối đa 300 ký tự)
  * af\_og\_image

**Lưu ý:** 

* Bạn có thể thêm thông số thẻ OG vào liên kết của mình bên ngoài UI AppsFlyer.
* Nếu bạn thêm các thẻ OG riêng cho X (trước đây là Twitter), chúng sẽ ghi đè bản xem trước AppsFlyer thông thường.

</Accordion>

<div id="social-app-landing-page" />

<Accordion title="Trang đích ứng dụng mạng xã hội">

<div id="important-1" />

> 🚧 **Quan trọng!**
>
> Liên kết Chung iOS hiện được hỗ trợ trong Meta ads.
>
> * Vì Meta hiện <Anchor target="_blank" href="/marketers/vi/docs/meta-ads-faq#are-ios-universal-links-and-android-app-links-supported-in-meta-ads">hỗ trợ các liên kết chung</Anchor>, nên không còn cần có trang đích ứng dụng xã hội cho các quảng cáo trả tiền trên Meta có hỗ trợ các liên kết chung.
> * Cần có trang đích ứng dụng xã hội cho các bài đăng được sở hữu (quảng cáo không phải trả tiền).

Các ứng dụng mạng xã hội có thể ảnh hưởng đến trải nghiệm mượt mà của những người dùng hiện có sử dụng Liên kết Chung. Có thể khắc phục được hiện tượng này bằng cách:

* [**Khuyến nghị**] Tạo trang đích ứng dụng xã hội.  
  Khi tạo trang đích ứng dụng mạng xã hội, chúng tôi khuyến nghị bạn nên đảm bảo đã cấu hình lược đồ URI.
* [Phương thức thay thế] <Anchor target="_blank" href="/marketers/vi/docs/onelink-troubleshooting-and-faq#liên-kết-sâu-bắt-buộc">Buộc mở ứng dụng</Anchor> bằng thông số `af_force_deeplink=true`.  
  **Lưu ý**: Thông số này được bật tự động cho Kakaotalk, Naver, Naver-Blog, Chrome, Weibo và X (trước đây là Twitter).

Bằng cách sử dụng trang đích ứng dụng xã hội, những người dùng nhấp vào quảng cáo trong ứng dụng mạng xã hội sẽ được chuyển hướng đến trang đích do AppsFlyer tạo. Từ đó, họ có thể được liên kết sâu hoặc tiếp tục cài đặt ứng dụng.

AppsFlyer cung cấp nhiều mẫu trang đích ứng dụng xã hội. Vị trí các thành phần trong các mẫu là cố định, nhưng bản thân các thành phần đều có thể tùy chỉnh, bao gồm ảnh hoặc màu nền, tiêu đề, văn bản, hình ảnh, nút, thẻ, v.v.

Trang đích ứng dụng xã hội có thể được sử dụng với các ứng dụng mạng xã hội sau:

* Instagram
* Facebook/Facebook Messenger (**Lưu ý**: Đối với Facebook và Facebook Messenger, nếu cả lược đồ URI và trang đích của ứng dụng Mạng xã hội đều được thiết lập, thì trang đích của ứng dụng Mạng xã hội sẽ không hiển thị.)
* LinkedIn
* Pinterest dành cho iOS
* Snapchat
* X (trước đây là Twitter)
* WeChat

**Trải nghiệm người dùng**

Khi người dùng tương tác với nút CTA trong trang đích:

* **Nếu ứng dụng đã được cài đặt**: người dùng thực hiện thao tác nhấp vào sẽ khởi chạy ứng dụng.
* **Nếu ứng dụng CHƯA được cài đặt**: người dùng sẽ được đưa đến cửa hàng ứng dụng thích hợp. Sau khi cài đặt, có thể trì hoãn liên kết sâu người dùng (được giải thích trong [liên kết sâu và deferred deep linking](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking)).

<div id="note-2" />

> 📘 **Lưu ý**
>
> Trang đích của ứng dụng mạng xã hội chỉ hỗ trợ URL OneLink rút gọn.

<div id="to-use-the-social-app-landing-page" />

#### **Để sử dụng trang đích ứng dụng mạng xã hội:**

1. Cấu hình trang đích như được mô tả trong phần sau.
2. Ghi nhận URL OneLink **ngắn** đã tạo.  
   Trang đích ứng dụng xã hội không hoạt động với các URL OneLink dài.
3. Đăng URL OneLink rút gọn trên ứng dụng mạng xã hội.

Phân bổ được xác định dựa trên cài đặt phân bổ của bạn.

<div id="to-set-up-the-social-apps-landing-page" />

#### **Để thiết lập trang đích cho ứng dụng mạng xã hội:**

1. Trong thiết lập liên kết Tùy chỉnh, đi đến phần **Share on social media**.
2. Trong phần **Social app landing page**, nhấp vào **Create landing page**.  
   Hệ thống sẽ mở một cửa sổ để chọn mẫu trang đích.  

   [![](https://files.readme.io/82a65bf446c4e6ae8803eaf048cc95ebe9c312f574fb8eda2764c123f0a50ee6-30151216576657.jpg)](https://files.readme.io/82a65bf446c4e6ae8803eaf048cc95ebe9c312f574fb8eda2764c123f0a50ee6-30151216576657.jpg)
3. Để chọn mẫu trang đích, hãy di chuột đến mẫu đã chọn và nhấp vào **Create**.

   **Mẹo**: Di chuột đến biểu tượng 🛈 của một mẫu để xem nên sử dụng mẫu trong những trường hợp nào. Đề xuất sử dụng Áp phích Gộp và hình thức Trình bày & Chia sẻ dành cho Instagram.
4. Tùy chỉnh tất cả các thành phần trong nội dung sáng tạo trang đích. Để làm như vậy, hãy chọn các thành phần theo tên hoặc nhấp vào chúng trên hình ảnh xem trước.    
    **Mẹo**: Lưu văn bản của bạn trong trường hợp bạn thay thế mẫu nội dung sáng tạo.
5. Thay thế tất cả các hình ảnh mẫu bằng hình ảnh của riêng bạn.  
   1. Enter image URLs including the extension, for example, `https://example.com/image.png`.
   2. Sử dụng một trong các loại tệp tin sau: jpeg, jpg, png.   
      **Lưu ý**: Định dạng webp không được hỗ trợ.
   3. Các khuyến nghị cho hình ảnh là:  

| Loại hình ảnh mẫu | Kích thước tệp tin hình ảnh tối đa | Tỷ lệ hình ảnh |
| --- | --- | --- |
| Bộ sưu tập | 300 KB | 16:9 (ngang) |
| <ul><li>Quảng cáo dạng trapeze</li><li>Băng chuyền</li><li>Trình bày & Chia sẻ</li></ul> | 300 KB | 1:1 |
| <ul><li>Tờ rơi</li><li>Áp phích</li><li>Áp phích mờ</li><li>Áp phích Gộp</li></ul> | 300 KB | 9:16 (dọc) |

   4. Nếu một hoặc nhiều hình ảnh không phải là một URL chính xác thì sẽ hiển thị lỗi và bạn sẽ không thể xem lại nội dung sáng tạo.  

      [![](https://files.readme.io/63223efc74994143111d5a5ef6b2d5fa7b84ac4f1033f8713d96cc293ba47588-30151216583697.png)](https://files.readme.io/63223efc74994143111d5a5ef6b2d5fa7b84ac4f1033f8713d96cc293ba47588-30151216583697.png)
6. Để xem lại nội dung sáng tạo của trang đích, hãy nhấp vào **Review**.  
   Nếu cần thay đổi, hãy nhấp vào **Back to editor**.  

   [![](https://files.readme.io/90b52321a6f7061a77624ec4486d6e2628c38c49ea0de734cf1c1fd0bc888cee-30151216593169.png)](https://files.readme.io/90b52321a6f7061a77624ec4486d6e2628c38c49ea0de734cf1c1fd0bc888cee-30151216593169.png)
7. Để lưu trang đích của bạn, hãy nhấp vào **Done** (Xong).  
   **Quan trọng**: Quảng cáo trang đích cập nhật/mới chỉ áp dụng sau khi tạo/cập nhật liên kết tùy chỉnh.
8. [Tùy chọn] Để chỉnh sửa trang đích, hãy nhấp vào **Edit social app landing page**.

</Accordion>

<div id="deep-linking-and-deferred-deep-linking" />

<Accordion title="Liên kết sâu và deferred deep linking">

Liên kết sâu có nghĩa là bạn nhắm mục tiêu lại những người dùng ứng dụng hiện có của mình và đưa họ trực tiếp đến một trải nghiệm cụ thể (ví dụ: một trang cụ thể) trong ứng dụng của bạn mà không cần chuyển hướng đến cửa hàng ứng dụng hoặc trang chủ ứng dụng trước. Những người dùng này được phân bổ bằng cách sử dụng chức năng nhắm mục tiêu lại cho phân bổ.

Deferred deep linking có nghĩa là bạn cung cấp cho người dùng mới trải nghiệm liên kết sâu tương tự như người dùng hiện có. Nhưng quy trình người dùng của họ là trước tiên, người dùng mới được đưa đến cửa hàng ứng dụng, sau khi tải xuống và khởi chạy ứng dụng, họ sẽ được đưa đến trải nghiệm hoặc trang cụ thể.

**Lưu ý**: Việc thiết lập liên kết sâu và deferred deep linking sẽ cần nhờ đến các nhà phát triển Android và iOS của bạn.

**Để thiết lập liên kết sâu và deferred deep linking để hướng người dùng đến trải nghiệm cụ thể trong ứng dụng:**

1. Liên hệ với các nhà phát triển iOS và Android của bạn để dự liệu **deep\_link\_value**cần đặt trên các liên kết của bạn.
   * **deep\_link\_value** là tên giá trị cho nội dung cụ thể trong ứng dụng mà người dùng sẽ được chuyển hướng đến. Các nhà phát triển thực hiện hành vi mong muốn của **deep\_link\_value** trong mã.
   * Nhà phát triển triển khai hành vi mong muốn trong mã. Chia sẻ hướng dẫn để giúp họ hiểu quy trình kỹ thuật và xem các ví dụ:
     * Đối với người dùng mới hoặc người dùng hiện có trên [liên kết sâu VÀ liên kết sâu bị trì hoãn](https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl), có hay không có ứng dụng của bạn. **Những điều cần lưu ý đối với UDL:** 
       * Yêu cầu SDK V6.1 trở lên.
       * Khung thời gian xem lại lượt nhấp có thể lên đến 15 phút.
     * **Lưu ý**: Những khách hàng đã sử dụng OneLink để liên kết sâu có thể đang sử dụng các phương thức kế thừa dành cho <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_gcd_legacy">Android</Anchor> và <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_gcd_legacy">iOS</Anchor>, thay vì UDL.  

       <div id="tips" />

       > 👍 **Lời khuyên**
       >
       > **deep\_link\_value** có thể dựa trên SKU sản phẩm, ID bài đăng mạng xã hội, đường dẫn URL hoặc bất kỳ giá trị nào khác.
       >
       > Điều quan trọng là phải làm việc với các nhà phát triển của bạn để đưa ra hệ thống lâu dài tốt nhất cho **deep\_link\_value** và bất kỳ thông số hoặc giá trị nào khác. Điều này sẽ giảm thiểu các cập nhật ứng dụng bổ sung. Trao đổi với nhà phát triển của bạn về việc sử dụng các giá trị động, để tạo nhiều liên kết sâu khác nhau đi đến các nội dung khác nhau trong ứng dụng, **mà không cần phải thay mã ứng dụng mỗi lần.** 
       >
       > Ví dụ: **deep\_link\_value** của một loại hoa quả được chọn và các nhà phát triển cho các giá trị là động. Điều này có nghĩa là bạn có thể nhập bất kỳ loại hoa quả nào mà không cần nhóm nhà phát triển phải làm gì thêm. 
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month&deep_link_value=apples...`
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month&deep_link_value=bananas...`
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month&deep_link_value=peaches...`

2. Sau khi nhận được xác nhận từ nhà phát triển rằng ứng dụng hoạt động theo các thông số và giá trị đã chọn, trong phần **Deep linking and redirection** của trang thiết lập liên kết, hãy nhập **giá trị Liên kết sâu** theo những gì bạn đã quyết định với nhà phát triển.
3. [Tùy chọn] Nếu liên kết sâu của bạn yêu cầu nhiều hơn một trải nghiệm trong ứng dụng (ví dụ: bạn muốn chuyển hướng người dùng đến một sản phẩm và giảm giá riêng cho họ), thì bạn có thể thêm **Giá trị liên kết sâu bổ sung** (sử dụng thông số deep\_link\_sub1) vào trọng tải dữ liệu liên kết sâu. Bạn có thể thêm các thông số liên kết sâu khác (deep\_link\_sub2-10) vào phần **Additional parameters**.
   1. Liên hệ với các nhà phát triển iOS và Android của bạn để dự liệu về các giá trị đó.
   2. Nhà phát triển thực hiện hành vi mong muốn trong mã. Chia sẻ hướng dẫn OneLink với nhà phát triển của bạn để hiểu quy trình kỹ thuật và xem các ví dụ.

      <Tabs>
      <Tab title="Android">

      [Hướng dẫn dành cho nhà phát triển trên OneLink](https://dev.appsflyer.com/hc/docs/dl_android_overview)

      </Tab>

      <Tab title="iOS">

      [Hướng dẫn dành cho nhà phát triển trên OneLink](https://dev.appsflyer.com/hc/docs/dl_ios_overview)

      </Tab>

      <Tab title="Unity">

      [Hướng dẫn dành cho nhà phát triển trên OneLink](https://dev.appsflyer.com/hc/docs/deeplinkintegrate)

      </Tab>
      </Tabs>

   3. Trong phần **Additional parameters**, hãy thêm thông số tùy chỉnh **deep\_link\_sub2-10** và các giá trị theo yêu cầu, theo những gì bạn đã quyết định với nhà phát triển.

<div id="note-4" />

> 📘 **Lưu ý**
>
> Khi các thông số và giá trị động được các nhà phát triển triển khai, nhà tiếp thị có thể sử dụng API OneLink để tự động tạo ra hàng ngàn liên kết tùy chỉnh. <Anchor target="_blank" href="/marketers/vi/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">Tìm hiểu thêm</Anchor>

</Accordion>

<div id="redirection" />

<Accordion title="Chuyển hướng">

**Để đưa người dùng mới đến** **trang đích, thay vì đến cửa hàng ứng dụng**:

1. Trong phần **Deep linking and redirection** của trang thiết lập liên kết, trong phần When app isn't installed, hãy chọn đưa người dùng đến một URL khác.  
   Các URL Android và iOS tùy chỉnh chuyển hướng người dùng mới đến trang đích mà bạn chỉ định.   
   **Lưu ý!** Nếu mẫu OneLink của bạn đã có giá trị đặt cho URL tùy chỉnh, thì các URL liên kết tùy chỉnh này sẽ ghi đè lên nó.
2. Bạn cũng có thể đưa người dùng mới đến <Anchor target="_blank" href="/marketers/vi/docs/redirect-users-to-custom-app-store-product-pages">các trang sản phẩm tùy chỉnh trên cửa hàng</Anchor>.

</Accordion>

<div id="additional-parameters" />

<Accordion title="Các thông số bổ sung">

Có thể bạn cần thêm các thông số bổ sung vào liên kết của mình, chẳng hạn như Chiến dịch, Tên bộ quảng cáo, Tên quảng cáo, Kênh, thông số tùy chỉnh của riêng bạn hoặc 1-5 <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">thông số người đăng ký</Anchor>. Điều này cho phép phân tích chi tiết hơn về các nỗ lực tiếp thị của bạn. Đọc thêm về <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters">các thông số phân bổ khác</Anchor>.

Bạn cũng có thể thêm các thông số liên kết sâu bổ sung (deep\_link\_sub2-10).

**Để thêm thông số**:

1. Trong phần **Additional parameters** của thiết lập liên kết, hãy nhấp vào **Add parameter**.
2. Chọn thông số cần thêm hoặc nhập thông số tùy chỉnh.

</Accordion>

<div id="testing" />

<Accordion title="Thử nghiệm">

Bạn có thể kiểm tra xem liên kết của mình có hoạt động để chuyển hướng hay không:

* Người dùng mới chưa cài đặt ứng dụng của bạn
* Người dùng hiện có đã cài đặt ứng dụng của bạn

<div id="new-users-without-your-app-installed" />

#### Người dùng mới chưa cài đặt ứng dụng của bạn

**Điều kiện tiên quyết**: Một <Anchor target="_blank" href="/marketers/vi/docs/registering-test-devices">thiết bị thử nghiệm đã đăng ký</Anchor> chưa cài đặt ứng dụng.

**Để thử nghiệm liên kết**:

1. Trong bảng điều khiển AppsFlyer, đi đến **Experiences & deep linking** > **OneLink Custom Links**.
2. Di chuột qua biểu tượng **Actions** của liên kết bạn muốn thử nghiệm và nhấp vào **Get URL**.
3. Gửi URL rút gọn hoặc đầy đủ đến điện thoại của bạn. Bạn có thể:
   * Quét mã QR bằng camera của điện thoại hoặc ứng dụng quét QR.
   * Gửi liên kết qua email hoặc WhatsApp cho bản thân và mở trên điện thoại của bạn.  
     **Lưu ý:** Không dán vào ghi chú iOS hoặc trực tiếp vào trình duyệt trên thiết bị di động. Thông thường, hệ điều hành di động sẽ không mở ứng dụng trong tình huống này.
4. Nhấp vào liên kết trên thiết bị di động của bạn.  
   Tùy thuộc vào nền tảng của bạn mà bạn sẽ được đưa đến cửa hàng ứng dụng hoặc trang đích.  
   **Lưu ý**: Cần có một lượt nhấp thực trên thiết bị di động. Chuyển hướng Javascript hoặc 301/302 không thể kích hoạt Liên kết Chung và Liên kết Ứng dụng Android. Ngay cả chuyển hướng cơ bản cũng không thành công với các phương thức này trên một số trình duyệt.
5. Tải về và khởi chạy ứng dụng.
   * Ứng dụng sẽ mở màn hình chính của mình.
   * Nếu bạn đã triển khai deferred deep linking, ứng dụng sẽ mở đến nội dung bạn đã chỉ định trong thông số liên kết.
6. Trong **Bảng điều khiển tổng quan** của AppsFlyer, tìm một lượt cài đặt mới.  
   Tìm một lượt nhấp mới và lượt cài đặt trong nguồn truyền thông (ví dụ: thử nghiệm) và tên chiến dịch bạn đặt trong URL.

Liên kết không hoạt động như mong đợi? Xem phần <Anchor target="_blank" href="/marketers/vi/docs/onelink-troubleshooting-and-faq">Câu hỏi thường gặp và hướng dẫn khắc phục sự cố OneLink.</Anchor>

<div id="existing-users-with-your-app-installed" />

#### Người dùng hiện có đã cài đặt ứng dụng của bạn

**Điều kiện tiên quyết**: Một thiết bị Android và/hoặc iOS đã cài đặt ứng dụng. Đảm bảo rằng đó là nguồn và phiên bản ứng dụng mà (các) nhà phát triển đã thực hiện các thay đổi (và triển khai các lược đồ Liên kết Chung, Liên kết Ứng dụng và/hoặc URI).

**Để thử nghiệm liên kết của bạn:**

1. Trong bảng điều khiển AppsFlyer, đi đến **Experiences & deep linking** > **OneLink**.
2. Nhấp vào **OneLink template** đã chọn.
3. Từ danh sách, chọn Liên kết tùy chỉnh.
4. Di chuột qua biểu tượng **Actions** của liên kết bạn muốn thử nghiệm và nhấp vào **Get URL**.
5. Gửi URL rút gọn hoặc đầy đủ đến điện thoại của bạn. Bạn có thể:
   * Quét mã QR bằng camera của điện thoại hoặc ứng dụng quét QR.
   * Gửi liên kết qua email hoặc WhatsApp cho bản thân và mở trên điện thoại của bạn.  
     **Lưu ý:** Không dán vào ghi chú iOS hoặc trực tiếp vào trình duyệt trên thiết bị di động. Thông thường, hệ điều hành di động sẽ không mở ứng dụng trong tình huống này.
6. Nhấp vào liên kết trên thiết bị di động của bạn.
   * Ứng dụng sẽ mở màn hình chính của mình.
   * Nếu bạn đã triển khai liên kết sâu, ứng dụng sẽ mở đến nội dung bạn đã chỉ định trong thông số liên kết.
7. Đi tới bảng điều khiển **Retargeting** của AppsFlyer.  
   Tìm kiếm lượt nhấp chuột mới/thu hút lại (ứng dụng mở) trong nguồn truyền thông của liên kết của bạn (ví dụ: thử nghiệm) và tên chiến dịch bạn đặt trong URL.

Liên kết không hoạt động như mong đợi? Xem phần <Anchor target="_blank" href="/marketers/vi/docs/onelink-troubleshooting-and-faq">Câu hỏi thường gặp và hướng dẫn khắc phục sự cố OneLink.</Anchor>

</Accordion>

<div id="additional-procedures" />

## Các quy trình bổ sung

<div id="create-a-custom-impression-url" />

<Accordion title="Tạo URL lượt hiển thị tùy chỉnh">

Liên kết lượt hiển thị tùy chỉnh cho phép bạn:

* Đo lường <Anchor target="_blank" href="/marketers/vi/docs/about-conversion-rates#marketing-funnel-stages-and-conversion-rates-1">tỷ lệ chuyển đổi từ lượt hiển thị thành lượt nhấp</Anchor> của quảng cáo bạn hiển thị.
* Nhận phân bổ cho số lượt hiển thị.

**Điều kiện tiên quyết:** Một URL đầy đủ OneLink đang hoạt động. URL rút gọn không được hỗ trợ.

**Đối tượng tham gia:**

Nhà tiếp thị và nhà phát triển web

**Để tạo URL lượt hiển thị để chỉ đo lường lượt hiển thị:**

1. Trong bảng điều khiển AppsFlyer, đi đến **Experiences & deep linking** (Trải nghiệm & liên kết sâu) > **OneLink Custom Links** (Liên kết Tùy chỉnh OneLink).
2. Di chuột qua biểu tượng **Actions** (Hành động) của liên kết bạn muốn thử nghiệm và nhấp vào **Get URL** (Nhận URL).
3. Sao chép URL OneLink đầy đủ để chỉnh sửa.  
   Ví dụ:  `https://subdomain.onelink.me/j7rN?pid=email&c=Spring`
4. Thay thế miền phụ (hoặc toàn bộ Miền gắn thương hiệu, nếu bạn đang sử dụng) bằng 'lượt hiển thị'.  Ví dụ:  `https://impressions.onelink.me/j7rN?pid=email&c=Spring`
5. Sao chép URL lượt hiển thị và gửi cho nhà phát triển của bạn.
6. Hướng dẫn nhà phát triển web của bạn triển khai URL lượt hiển thị trong logic trang web.

Bây giờ bạn có một URL lượt hiển thị, có thể được sử dụng để đếm số lượt hiển thị trên các trang web của bạn **nhưng không thể phân bổ các lượt cài đặt mới**.Đối với phân bổ lượt xem hết, hãy làm theo các bước tiếp theo.

**Để sử dụng URL lượt hiển thị để phân bổ:**

1. Chuẩn bị URL lượt hiển thị như được mô tả trong các bước trước đó.
2. Đảm bảo rằng <Anchor target="_blank" href="/marketers/vi/docs/measure-view-through-engagements">tùy chọn phân bổ lượt xem hết được bật</Anchor>.
3. [Tùy chọn] Nếu bạn muốn thay đổi giá trị <Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows">khung thời gian xem lại</Anchor> lượt xem hết mặc định 1 ngày, hãy thêm thông số `af_viewthrough_lookback` bằng giá trị mới. Ví dụ: `af_viewthrough_lookback=1d`.
4. Sao chép URL lượt hiển thị và gửi cho nhà phát triển của bạn.
5. Chỉ thị nhà phát triển web của bạn thực hiện URL lượt hiển thị trong logic trang web.

Ví dụ URL lượt hiển thị đầy đủ:

```http
https://impressions.onelink.me/j7rN?pid=email&c=Spring&af_viewthrough_lookback=1d
```

</Accordion>

<div id="deep-linking-post-event" />

<Accordion title="Liên kết sâu sau sự kiện">

Bạn có thể chỉ muốn liên kết sâu người dùng vào các hoạt động hoặc trang cụ thể sau một sự kiện, ví dụ:

* Đăng nhập
* Xem một màn hình khởi động ứng dụng
* Đồng ý với các điều khoản và điều kiện
* Và nhiều hơn thế

**Để liên kết sâu người dùng sau một sự kiện**:

Yêu cầu nhà phát triển của bạn làm theo hướng dẫn của họ để liên kết sâu người dùng sau sự kiện dành cho [Android](https://dev.appsflyer.com/hc/docs/dl_android_dl_post_event) và [iOS](https://dev.appsflyer.com/hc/docs/dl_ios_dl_post_event).

</Accordion>

<div id="deferred-deep-linking-with-ios-private-relay" />

<Accordion title="Deferred deep linking với iOS Private Relay">

Với sự ra mắt iOS 15, Apple cung cấp cho người dùng iCloud+ tính năng có tên là <Anchor target="_blank" href="https://www.macworld.com/article/348965/icloud-plus-private-relay-safari-vpn-ip-address-encryption-privacy.html">Private Relay</Anchor>, hỗ trợ tùy chọn mã hóa lưu lượng duyệt web và ẩn vị trí chính xác, địa chỉ IP và nội dung lưu lượng duyệt web của họ. Nếu người dùng lựa chọn tham gia Private Relay, điều này có thể ảnh hưởng đến ảnh hưởng đến việc phân bổ và deferred deep linking. Điều này có nghĩa là, khi một người dùng mới không có ứng dụng đi đến Cửa hàng Ứng dụng, cài đặt và khởi chạy ứng dụng, thì Private Relay có thể ngăn việc đưa họ đến một trang cụ thể trong ứng dụng.

Để đảm bảo deferred deep linking (DDL) tiếp tục hoạt động như dự kiến, bạn cần phải triển khai một trong các giải pháp AppsFlyer sau đây:

* **[Đề xuất] Giải pháp dựa trên Clip Ứng dụng**: Tạo một Clip Ứng dụng cung cấp cho bạn dữ liệu phân bổ người dùng và hướng người dùng đến một trải nghiệm Clip Ứng dụng tùy chỉnh tương tự với trải nghiệm bạn muốn DDL đạt được. Clip ứng dụng cũng có thể bao gồm quy trình để hướng người dùng từ Clip Ứng dụng của bạn đến ứng dụng đầy đủ của bạn.
* **Giải pháp dựa trên bảng nhớ tạm**: Tạo một trang đích sao chép dữ liệu deferred deep linking từ URL và chuyển hướng người dùng chính xác đến ứng dụng. **Lưu ý**: Giải pháp này không hỗ trợ việc phân bổ.

<div id="app-clipbased-solution" />

<Accordion title="Giải pháp dựa trên Clip Ứng dụng">

Giải pháp này kết hợp các URL rút gọn của OneLink với công nghệ Clip Ứng dụng có sẵn trên iOS và cho phép bạn gửi người dùng đến các quy trình cụ thể trong sản phẩm của bạn mà không cần cài đặt ứng dụng đầy đủ. URL rút gọn của OneLink cung cấp cho bạn dữ liệu phân bổ người dùng và hướng người dùng đến một trải nghiệm Clip Ứng dụng tùy chỉnh tương tự với trải nghiệm bạn muốn DDL đạt được. Clip ứng dụng cũng có thể bao gồm quy trình để hướng người dùng từ Clip Ứng dụng của bạn đến ứng dụng đầy đủ. **Lưu ý**: Nếu người dùng cài đặt lại ứng dụng đầy đủ từ giải pháp dựa trên Clip Ứng dụng thì việc này có thể được báo cáo trong AppsFlyer là cài đặt tự nhiên. 

<div id="flow" />

#### **Quy trình**

Quy trình của giải pháp DDL dựa trên Clip Ứng dụng như sau:

1. Nhà quảng cáo tạo một Clip Ứng dụng và thêm nó vào một mẫu OneLink cho người dùng có bật chức năng Private Relay.
2. Người dùng nhấn vào URL OneLink.
3. Trình xử lý web AppsFlyer kiểm tra xem liệu:
   * Thiết bị có đang sử dụng iOS 15+ không
   * Trình duyệt có phải là Safari không
   * Người dùng có bật chức năng Private Relay hay không.
4. Khi AppsFlyer xác nhận các điều trên và người dùng được nhắc nhấp vào **Phát Clip Ứng dụng** hoặc **Xem trong Safari**.
   * Nếu người dùng nhấp vào **Phát Clip Ứng dụng**, thì thẻ Clip Ứng dụng sẽ hiển thị với người dùng.
   * Nếu người dùng nhấp vào Xem trong Safari, thì một trang đích sẽ mở ra, nhắc họ mở Clip Ứng dụng.
5. Người dùng mở Clip Ứng dụng.
6. Clip Ứng dụng mở ra và mang đến cho người dùng trải nghiệm được quyết định bởi nhà tiếp thị và nhà phát triển ứng dụng.
7. Nếu Clip Ứng dụng bao gồm một quy trình để hướng người dùng đến ứng dụng đầy đủ, thì người dùng được đưa đến Cửa hàng Ứng dụng để tải xuống ứng dụng đầy đủ. Khi khởi chạy ứng dụng, họ sẽ có được trải nghiệm người dùng xác định bởi nhà phát triển.

**Điều kiện tiên quyết:** SDK AppsFlyer V6.4.0+

**Để thiết lập giải pháp DDL dựa trên Clip Ứng dụng**:

1. Báo cho nhà phát triển tuân theo <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_private_relay#app-clip-based-solution">các hướng dẫn trung tâm phát triển giải pháp dựa trên Clip Ứng dụng</Anchor>. và tạo một Clip Ứng dụng cung cấp trải nghiệm người dùng mong muốn. Điều này cũng có thể bao gồm quy trình để hướng người dùng từ Clip Ứng dụng đến ứng dụng đầy đủ của bạn.
2. Tạo hoặc chỉnh sửa <Anchor target="_blank" href="/marketers/vi/docs/create-a-onelink-template">mẫu OneLink</Anchor> với [Liên kết Chung](https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links) và [liên kết sâu bị trì hoãn](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking).
3. Trong mẫu OneLink, bật **Hiển thị Clip Ứng dụng nếu người dùng có Private Relay**. Không bật chức năng này trừ khi bạn có Clip Ứng dụng.  
   **Lưu ý**: Khi thay đổi một mẫu OneLink bằng Liên kết Chung, ví dụ như thêm (hoặc gỡ) tính năng Clip Ứng dụng, thì tệp AASA có thể mất vài giờ để cập nhật. Do đó, liên kết bạn tạo dựa trên mẫu có thể chưa có ngay chức năng được cập nhật.
4. Tạo một liên kết tùy chỉnh dựa trên mẫu OneLink.
5. Trong App Store Connect, đi đến phần **App Clip Experience** (Trải nghiệm Clip Ứng dụng), cuộn xuống **App URL** (URL Ứng dụng) và nhập URL mẫu OneLink của bạn (tên miền + ID mẫu. Ví dụ: `yourbrand.onelink.me/GrbZ`), hoặc URL rút gọn liên kết tùy chỉnh OneLink cụ thể.  
   **Lưu ý**: Nếu bạn nhập liên kết tùy chỉnh OneLink, giải pháp dựa trên Clip Ứng dụng sẽ chỉ hoạt động cho người dùng nhấn vào liên kết cụ thể đó; các liên kết khác được tạo dựa trên mẫu OneLink sẽ không hoạt động.

</Accordion>

<div id="clipboardbased-solution" />

<Accordion title="Giải pháp dựa trên bảng nhớ tạm">

<div id="flow-1" />

#### **Quy trình**

Quy trình của giải pháp DDL dựa trên bảng nhớ tạm như sau:

1. Nhà quảng cáo tạo một liên kết sâu gián tiếp chứa tham số `af_cp_lp=true`.
2. Người dùng nhấn vào liên kết sâu gián tiếp.
3. AppsFlyer kiểm tra xem liệu:
   * Thiết bị có đang sử dụng iOS 15+ không
   * Trình duyệt có phải là Safari không
   * Người dùng có bật chức năng Private Relay hay không.
   * Liên kết có chứa tham số `af_cp_lp=true` hay không.
4. Khi AppsFlyer xác nhận thông tin trên, trang web đích sẽ tải, chứa biểu tượng ứng dụng, ảnh và CTA để tải ứng dụng từ Cửa hàng Ứng dụng. Người dùng cũng sẽ thấy tin nhắn giải thích quy trình: rằng URL được sao chép để đảm bảo trải nghiệm người dùng tốt nhất mà sẽ gửi họ đến trang cụ thể trong ứng dụng.  

   ![ios_15_ip_masking__1_.png](https://files.readme.io/c130314c98ebd42f50feaafd752c0cea954f42c5bfd99a6dbd94daf9e48c2ff4-30151216595345.png)
5. Người dùng nhấn vào **Tải ứng dụng**.
6. Người dùng được đưa đến Cửa hàng Ứng dụng để cài đặt ứng dụng. Sau đó, vào lần khởi chạy đầu tiên, họ được đưa đến trang ứng dụng cụ thể.

<div id="requirements" />

#### **Yêu cầu**

Giải pháp DDL trang đích sao chép/dán yêu cầu:

* Người dùng phải duyệt web trên Safari.
* Liên kết sâu gián tiếp bao gồm tham số `af_cp_lp=true`.
* SDK AppsFlyer iOS V6+.
* Nhà phát triển ứng dụng iOS của bạn phải triển khai mã dán dữ liệu liên kết sâu gián tiếp trong URL từ bảng nhớ tạm. Đây không phải là một phần của SDK AppsFlyer.
* Người dùng cuối phải duy trì trạng thái đánh dấu hộp kiểm (mặc định). Nếu không đánh dấu, URL sẽ không được sao chép và deferred deep linking sẽ không hoạt động.

<div id="setup" />

#### **Thiết lập**

**Để thiết lập giải pháp DDL dựa trên bảng nhớ tạm**:

1. Yêu cầu nhà phát triển iOS của bạn: 
   1. Tuân theo <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_private_relay#clipboard-based-solution">hướng dẫn trung tâm phát triển</Anchor> và tích hợp mã yêu cầu trong SDK AppsFlyer.
   2. Triển khai mã dán dữ liệu liên kết sâu gián tiếp trong URL từ bảng nhớ tạm. Đây không phải là một phần của SDK AppsFlyer.
2. Thêm tham số `af_cp_lp=true` vào các liên kết của bạn.   
   Bạn có thể thực hiện bằng cách thêm tham số tùy chỉnh vào UI liên kết tùy chỉnh OneLink của AppsFlyer hoặc đơn giản là nối tham số vào bất kỳ liên kết nào của mình.

</Accordion>

</Accordion>

<div id="additional-information" />

## Thông tin bổ sung

<div id="examples" />

<Accordion title="Ví dụ:">

**Ví dụ cơ bản**

Mark là nhà tiếp thị của một dịch vụ giao hàng tạp hóa rất thành công có tên "Feed Me". Mark nhắm mục tiêu vào các số điện thoại của cơ sở người dùng của mình để tải xuống các ứng dụng iOS và Android mới dành cho thiết bị di động của Feed Me. Một chiến dịch SMS đã được lên kế hoạch. Tuy nhiên, Mark không biết người dùng nào có thiết bị Android hoặc người nào dùng thiết bị iOS. Anh cũng không biết liệu họ đã cài đặt ứng dụng hay chưa.

Để giải quyết vấn đề này, Mark gửi SMS chứa một URL rút gọn do OneLink cung cấp. Khi người dùng nhận được SMS và nhấp vào liên kết:

* Nếu họ chưa có ứng dụng, SMS này sẽ tự động chuyển hướng họ đến cửa hàng ứng dụng hoặc trang đích thích hợp, nơi họ dễ dàng cài đặt ứng dụng.
* Nếu họ đã cài đặt ứng dụng, ứng dụng sẽ mở cho họ.

Số lượt cài đặt mới và lượt tương tác lại được phân bổ cho chiến dịch SMS, cho phép Mark kiểm tra mức độ thành công của chiến dịch SMS trong AppsFlyer. 

**Ví dụ về liên kết sâu**

SMS của nhà tiếp thị Mark (từ ví dụ trước) đã thu được thành công tương đối trong việc thu hút người dùng tải xuống và mở ứng dụng. Tuy nhiên, không có nhiều người dùng nhấp vào liên kết và mở ứng dụng đã chuyển đổi để đặt hàng.

Mark quyết định tăng lượt chuyển đổi bằng cách tặng miễn phí một túi đào, táo hoặc bơ với mỗi lần mua. Đối với điều này, Mark tạo ra trải nghiệm liên kết sâu, mượt mà cho người dùng hiện có. Anh đã gửi cơ sở người dùng của mình một email chi tiết nhấn mạnh lợi ích của 3 loại trái cây tốt cho sức khỏe này. 

Đối với mỗi loại trái cây được đề cập trong email, Mark đưa vào một liên kết có giá trị liên kết sâu do OneLink cung cấp, được cấu hình (với sự trợ giúp của các nhà phát triển thiết bị di động) để:

Để giải quyết vấn đề này, Mark gửi SMS chứa một URL rút gọn do OneLink cung cấp. Khi người dùng nhận được SMS và nhấp vào liên kết:

* Nếu họ đã cài đặt ứng dụng, họ sẽ được đưa thẳng đến trang trái cây có liên quan.
* Nếu họ chưa có ứng dụng, họ sẽ được chuyển hướng đến cửa hàng ứng dụng hoặc trang đích thích hợp, dựa trên thiết bị của họ. Và sau đó, khi tải xuống và mở ứng dụng, họ sẽ được đưa thẳng đến trang trái cây.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Lưu ý |
| --- | --- |
| <span id="onelink-characters"></span>Ký tự OneLink | <ul><li>Tổng chiều dài URL không được vượt quá 2000 ký tự</li><li>Tên liên kết và nguồn truyền thông: không được vượt quá 150 ký tự</li><li>Dưới đây là các ký tự đặc biệt không được phép sử dụng trong các thông số hoặc giá trị của OneLink: ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, &lt;, /, \{, \}, %<ul><li>Không được phép sử dụng ký tự đặc biệt () trong Android, iOS và thông số chuyển hướng web</li></ul></li><li>ID URL rút gọn không được vượt quá 50 ký tự</li></ul> |
| <span id="posting-onelink-urls-in-web-pages"></span>Đăng URL OneLink trên các trang web | Việc sử dụng `target="_blank"` trong thẻ HTML href sẽ không chuyển hướng đến Google Play hoặc App Store. Nếu URL OneLink được đặt bên trong một thẻ html **a** có thuộc tính **target="\_blank"** thì URL sẽ mở ra một trang trống trong Chrome trên Android và iOS. Điều này ảnh hưởng đến chức năng OneLink. Hãy chắc chắn rằng thẻ **a** không bao gồm các thuộc tính mục tiêu. |
| <span id="agencies"></span>Đại lý | Các đại lý có thể sử dụng các mẫu OneLink hiện có để tạo đường dẫn phân bổ tùy chỉnh cho mình **nếu đại lý này là một đối tác của tất cả các ứng dụng trong mẫu**. |
| <span id="social-media-preview-image"></span>Hình ảnh xem trước trên mạng xã hội | Nếu loại hình ảnh không được nền tảng mạng xã hội hỗ trợ thì sẽ không được hiển thị. |
| <span id="desktop"></span>Máy tính để bàn | Khi bạn đặt URL hoặc mẫu OneLink để chuyển hướng người dùng máy tính để bàn đến một URL khác, URL web sẽ được thêm vào liên kết trong thông số `af_web_dp`. Khi liên kết chứa `af_web_dp`, AppsFlyer không đăng ký lượt nhấp khi lượt nhấp đó đến từ máy tính để bàn. |
| <span id="af_enc_data"></span>af\_enc\_data | Không được hỗ trợ trong URL lượt hiển thị. |
| <span id="social-media-preview-og-tag"></span>Xem trước mạng xã hội - thẻ OG | Đối với WhatsApp, hình ảnh không được vượt quá 300 KB. |
| <span id="android-social-apps-webview-deep-linking-redirection"></span>Các ứng dụng xã hội Android Chuyển hướng liên kết sâu trong chế độ WebView | Do những thay đổi gần đây trong nhiều ứng dụng xã hội Android, luồng chuyển hướng liên kết sâu trong chế độ xem trình duyệt nội bộ (WebView) đã bị hỏng.<br /><br />Để đáp ứng những thay đổi cũng như kích hoạt lại liên kết sâu và chuyển hướng, chúng tôi đã phải giới thiệu thêm tính năng tương tác người dùng cho các ứng dụng xã hội Android sau:<ul><li>Các phiên bản Facebook trên v420</li><li>Instagram</li><li>Facebook Messenger</li><li>Snapchat</li></ul>Luồng người dùng mới yêu cầu người dùng từ các ứng dụng trên nhấp vào nút trang đích bổ sung để kích hoạt tính năng chuyển hướng đến Google Play Store và các cửa hàng bên thứ ba khác.<br /><br /><br />**Ghi chú:**<ul><li>Facebook phiên bản 420 trở xuống hoạt động như trước mà không cần thêm tương tác từ người dùng.</li><li>Liên kết ứng dụng trong bài viết trên Facebook hoạt động như trước mà không cần thêm tương tác từ người dùng.</li><li>Liên kết ứng dụng trong đoạn chat trên Instagram hoạt động như trước mà không cần thêm tương tác từ người dùng.</li><li>Trong luồng liên kết sâu, khi chưa cài đặt ứng dụng, sẽ có một hạn chế đã biết: thông báo lỗi bật lên. Thông báo này không ảnh hưởng đến luồng; người dùng vẫn được chuyển hướng đến cửa hàng như mong đợi.</li></ul> |
| <span id="onelink-link-previews-sometimes-fail-to-display-correctly-on-facebook-and-linkedin"></span>Bản xem trước liên kết OneLink đôi khi không hiển thị chính xác trên Facebook và LinkedIn. | **Mô tả**  <br />Sự cố phát sinh khi trang web đích không nhận ra chuỗi tác nhân người dùng `AppsFlyerBot-Previewer/1.0` trong yêu cầu xem trước là đến từ robot (hoặc trình thu thập thông tin). Trong những trường hợp như vậy, trang web không phản hồi với nội dung xem trước được gắn thẻ OG thích hợp.<br /><br />**Giải pháp**  <br />Bạn có thể định cấu hình trang đích của mình để coi các trang có chuỗi tiêu đề tác nhân người dùng `AppsFlyerBot-Previewer/1.0` là đến từ rô-bốt bằng cách <Anchor target="_blank" href="https://moz.com/learn/seo/robotstxt">cập nhật tập tin robot.txt trên trang web của bạn</Anchor>. |

</Accordion>

<div data-zendesk-anchors="onelink-links-and-experiences=li%C3%AAn-k%E1%BA%BFt-v%C3%A0-tr%E1%BA%A3i-nghi%E1%BB%87m-onelink h_01H8Y6DDT4M8XGAEJJVTHKHPKV=li%C3%AAn-k%E1%BA%BFt-v%C3%A0-tr%E1%BA%A3i-nghi%E1%BB%87m-onelink create-a-onelink-link=t%E1%BA%A1o-li%C3%AAn-k%E1%BA%BFt-onelink h_01H8Y6DDT41C6JYKXET0NDRB1G=t%E1%BA%A1o-li%C3%AAn-k%E1%BA%BFt-onelink h_01H8Y6DDT4C543RS2BXAGS487M=experiences h_01H8Y6DDT4WZ5FKZYBX2H08MFD=general-settings enable-retargeting-for-the-app=b%E1%BA%ADt-t%C3%ADnh-n%C4%83ng-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i-cho-%E1%BB%A9ng-d%E1%BB%A5ng h_01H8Y6DDT4R7785X5DRES66BKJ=b%E1%BA%ADt-t%C3%ADnh-n%C4%83ng-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i-cho-%E1%BB%A9ng-d%E1%BB%A5ng h_01H8Y6DDT4JT9H0R13ZNGHJ79S=social-media-preview-og-tags h_01H8Y6DDT4PHY2F5E3GK582P51=social-app-landing-page h_01H8Y6DDT463F5569B28DD17SV=quan-tr%E1%BB%8Dng h_01H8Y6DDT4MMD1AW6D1PNGNX5X=l%C6%B0u-%C3%BD to-use-the-social-app-landing-page=%C4%91%E1%BB%83-s%E1%BB%AD-d%E1%BB%A5ng-trang-%C4%91%C3%ADch-%E1%BB%A9ng-d%E1%BB%A5ng-m%E1%BA%A1ng-x%C3%A3-h%E1%BB%99i h_01H8Y6DDT4JB4RT438MAGNNX2S=%C4%91%E1%BB%83-s%E1%BB%AD-d%E1%BB%A5ng-trang-%C4%91%C3%ADch-%E1%BB%A9ng-d%E1%BB%A5ng-m%E1%BA%A1ng-x%C3%A3-h%E1%BB%99i to-set-up-the-social-apps-landing-page=%C4%91%E1%BB%83-thi%E1%BA%BFt-l%E1%BA%ADp-trang-%C4%91%C3%ADch-cho-%E1%BB%A9ng-d%E1%BB%A5ng-m%E1%BA%A1ng-x%C3%A3-h%E1%BB%99i h_01H8Y6DDT4G34S3RV3ZH64XT19=%C4%91%E1%BB%83-thi%E1%BA%BFt-l%E1%BA%ADp-trang-%C4%91%C3%ADch-cho-%E1%BB%A9ng-d%E1%BB%A5ng-m%E1%BA%A1ng-x%C3%A3-h%E1%BB%99i h_01H8Y6DDT5XNJVYW2Y8F6JWPK2=deep-linking-and-deferred-deep-linking h_01H8Y6DDT5JR3B3DMR87JCBZ69=l%E1%BB%9Di-khuy%C3%AAn h_01H8Y6DDT5KSBE00WWDGQ5R1AQ=l%C6%B0u-%C3%BD-1 h_01H8Y6DDT58FC3HMSRZBMGZZRJ=redirection h_01H8Y6DDT5AAQ3BZD8QB9H19QB=additional-parameters h_01H8Y6DDT5B6M7CETQRD9NKX8R=testing new-users-without-your-app-installed=ng%C6%B0%E1%BB%9Di-d%C3%B9ng-m%E1%BB%9Bi-ch%C6%B0a-c%C3%A0i-%C4%91%E1%BA%B7t-%E1%BB%A9ng-d%E1%BB%A5ng-c%E1%BB%A7a-b%E1%BA%A1n h_01H8Y6DDT50DH5TGVVPJPJC4MG=ng%C6%B0%E1%BB%9Di-d%C3%B9ng-m%E1%BB%9Bi-ch%C6%B0a-c%C3%A0i-%C4%91%E1%BA%B7t-%E1%BB%A9ng-d%E1%BB%A5ng-c%E1%BB%A7a-b%E1%BA%A1n existing-users-with-your-app-installed=ng%C6%B0%E1%BB%9Di-d%C3%B9ng-hi%E1%BB%87n-c%C3%B3-%C4%91%C3%A3-c%C3%A0i-%C4%91%E1%BA%B7t-%E1%BB%A9ng-d%E1%BB%A5ng-c%E1%BB%A7a-b%E1%BA%A1n h_01H8Y6DDT5KDEWS40XPYGYC8HK=ng%C6%B0%E1%BB%9Di-d%C3%B9ng-hi%E1%BB%87n-c%C3%B3-%C4%91%C3%A3-c%C3%A0i-%C4%91%E1%BA%B7t-%E1%BB%A9ng-d%E1%BB%A5ng-c%E1%BB%A7a-b%E1%BA%A1n additional-procedures=c%C3%A1c-quy-tr%C3%ACnh-b%E1%BB%95-sung h_01H8Y6DDT5YR8JA5YMZFPMCC2X=c%C3%A1c-quy-tr%C3%ACnh-b%E1%BB%95-sung h_01H8Y6DDT58EFS8S46D1AVP3T1=create-a-custom-impression-url h_01H8Y6DDT5S4NEJMNJR4K3QMNH=deep-linking-post-event h_01H8Y6DDT58Y6CS27M2W3MHYAD=deferred-deep-linking-with-ios-private-relay h_01H8Y6DDT5A7J07KNNRWCXCBH2=app-clipbased-solution flow=quy-tr%C3%ACnh h_01H8Y6DDT5VDKAR89B8N6D7YMB=quy-tr%C3%ACnh h_01H8Y6DDT62H71A8DPG00A3ZTN=clipboardbased-solution flow::21baf6ac=quy-tr%C3%ACnh-1 h_01H8Y6DDT638T7C9HQHZ1CJ726=quy-tr%C3%ACnh-1 requirements=y%C3%AAu-c%E1%BA%A7u h_01H8Y6DDT6JGP33AWFQV6Z8FF0=y%C3%AAu-c%E1%BA%A7u setup=thi%E1%BA%BFt-l%E1%BA%ADp h_01H8Y6DDT61ENGJFZ1XS28GS1T=thi%E1%BA%BFt-l%E1%BA%ADp additional-information=th%C3%B4ng-tin-b%E1%BB%95-sung h_01H8Y6DDT679SGBTSM669F9FHV=th%C3%B4ng-tin-b%E1%BB%95-sung h_01H8Y6DDT6TX4WTP2HYRF11DZ3=examples h_01H8Y6DDT6TQYRS81BMHARB62S=traits-and-limitations" />
