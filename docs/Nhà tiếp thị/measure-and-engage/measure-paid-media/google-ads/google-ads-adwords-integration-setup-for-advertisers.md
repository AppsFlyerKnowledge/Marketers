---
title: Thiết lập tích hợp Google Ads (AdWords)
metadata:
  keywords:
    - Integration
    - Google AdWords
    - Configuration
    - google
    - migration
    - Advertisers
    - google ads configuration
    - ads
    - google ads
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2017-05-17T19:16:15Z'
  edited_at: '2024-04-02T09:52:19Z'
  id: 115002504686
  locale: vi
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/vi/articles/115002504686
---
> **Sơ lược:** Tích hợp tài khoản Google Ads của bạn với AppsFlyer để hiển thị dữ liệu phân bổ từ tất cả các chiến dịch của bạn.

> 🚧 **Quan trọng!**
>
> Xem bản tin về việc <Anchor target="_blank" href="/marketers/vi/docs/bulletin-supporting-the-new-google-eu-consent-policy">hỗ trợ chính sách đồng thuận mới của Google EU</Anchor>.

## Sử dụng Google Ads

Giao diện người dùng của Google Ads chỉ cho phép bạn định cấu hình <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6247380?hl=en">Chiến dịch Ứng dụng</Anchor>, cho các thiết bị chạy iOS và Android.

Để phân bổ người dùng từ các nền tảng khác, ví dụ như người dùng Windows Phone, đến Google Ads, bạn cần sử dụng <Anchor target="_blank" href="/marketers/vi/docs/set-up-smart-script-to-convert-web-visitors#google-ads-gclid">giải pháp trang đích</Anchor>.

Để định cấu hình các loại chiến dịch cụ thể khác ngoài Chiến dịch Ứng dụng, hãy liên hệ với đại diện Google của bạn.

<div id="configuring-google-ads-attribution-for-advertisers" />

## Định cấu hình phân bổ Google Ads cho nhà quảng cáo

Để bắt đầu phân bổ các chiến dịch Google Ads với AppsFlyer, hãy làm theo các bước sau:

> 📘 **Lưu ý**
>
> Là điều kiện tiên quyết để tích hợp với Google Ads, ứng dụng phải thu thập IDFA / GAID. Để biết thêm thông tin, hãy tham khảo phần <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">hướng dẫn tích hợp SDK</Anchor>.

<Accordion title="Xem">

<Embed title="Thiết lập tích hợp Google Ads (AdWords)" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/f3i7cti7r5" providerUrl="https://fast.wistia.com" />

<Accordion title="Đọc">

<div id="step-1-create-the-google-ads-link-id-mandatory" />

<Accordion title="Bước 1: Tạo ID Liên kết Google Ads (bắt buộc)">

Việc tạo ID liên kết cần phải có **quyền truy cập quản trị của Google** vào tài khoản.

1. Đăng nhập vào tài khoản quản trị viên Google Ads của bạn.
2. Từ menu trên cùng, nhấp vào **Tools and settings**.
3. Trong menu **Setup**, chọn **Data manager** và nhấp vào **+ Connect Product**.
4. Trong thanh tìm kiếm **Data sources**, nhập “Third-party app analytics”, chọn rồi nhấp vào **Continue**.
5. Nhấp vào **Create link ID**.
6. Chọn **AppsFlyer** làm nhà cung cấp dịch vụ phân tích ứng dụng của bạn.
7. Chọn nền tảng, Android hoặc iOS.
8. Tìm và chọn ứng dụng của bạn.
9. Nhấp vào **Create link ID**.

</Accordion>

<div id="step-2-set-up-google-ads-on-appsflyer-mandatory" />

<Accordion title="Bước 2: Thiết lập Google Ads trên AppsFlyer (bắt buộc)">

**(Bất kỳ thành viên nào trong tài khoản AppsFlyer)**

1. Trong AppsFlyer, từ menu bên, chọn **Collaborate** > **Partner Marketplace**.
2. Tìm kiếm và chọn **Google Ads**.
3. Nhấp vào **Set up integration**. Bạn được chuyển hướng đến trang thiết lập tích hợp.
4. Từ thẻ **Integration**, bật tùy chọn **Activate partner**.  
   **Lưu ý:** Nút bật/tắt phải luôn ở trạng thái bật (<Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">được kích hoạt</Anchor>) trong thời gian bạn làm việc với đối tác<Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">.</Anchor>
5. Dán **ID Liên kết** bạn đã sao chép ở bước trước.
6. Quyết định có bật <Anchor target="_blank" href="/marketers/vi/docs/support-google-eu-consent-policy#do-i-have-control-over-consent-data-for-nonue-users">**người dùng ngoài khu vực Châu Âu**</Anchor> hay không.  

   <Image alt="non eu usrs.png" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="557px" />
7. Định cấu hình **Phân bổ lượt cài đặt**:
   1. Thiết lập **khung thời gian xem lại lượt nhấp qua cài đặt**.  
      Chọn đơn vị khung thời gian xem lại (giờ hoặc ngày) và đặt thanh trượt về giá trị mong muốn. Bạn nên đặt khung thời gian xem lại thành 30 ngày để khớp với Google Ads.
   2. [Tùy chọn] Nếu bạn chạy chiến dịch đăng ký trước cho ứng dụng Android, hãy cài đặt **Pre-registration campaign lookback window** (mặc định là 90 ngày). Thanh trượt này xác định khung thời gian xem lại để phân bổ lượt cài đặt cho các chiến dịch đăng ký trước.
   3. Bật tùy chọn **Install view-through attribution**.
   4. Chọn đơn vị khung thời gian xem lại (giờ hoặc ngày) và đặt thanh trượt về giá trị mong muốn. Chúng tôi đề nghị bạn nên đặt khung thời gian xem lại lượt xem hết thành 1 ngày để khớp với Google Ads.  
      **Lưu ý:** Google không gửi xác nhận quyền sở hữu đối với lượt hiển thị ứng dụng iOS. Nút chuyển phân bổ lượt xem hết/lượt cài đặt và thanh trượt khung thời gian xem lại không còn phù hợp với các ứng dụng iOS.  

      [![](https://files.readme.io/a6f05b9f92abf6dfdbaafc248c0381bfe063086daa10727dc088d484c1b38f0b-30759221879825.png)](https://files.readme.io/a6f05b9f92abf6dfdbaafc248c0381bfe063086daa10727dc088d484c1b38f0b-30759221879825.png)
8. Để bật phân bổ lượt cài đặt lại, hãy bật **Reinstall attribution**.  
   Không cần định cấu hình khung thời gian xem lại đối với phân bổ lượt cài đặt lại, vì các giá trị được lấy từ các tùy chọn cài đặt phân bổ lượt cài đặt.  

   <div id="important" />

   > 🚧 **Quan trọng!**
   >
   > Dữ liệu chuyển đổi cài đặt lại được **trình bày dưới dạng session\_start** trên bảng điều khiển của Google Ads. Trong AppsFlyer, dữ liệu được phân bổ và được xem là phân bổ lại.

9. Định cấu hình **Phân bổ thu hút lại**:  
   1. <Anchor target="_blank" href="/marketers/vi/docs/app-settings#reengagement-attribution">Bật tính năng nhắm mục tiêu lại trong phần Cài đặt của Ứng dụng</Anchor>.
   2. Bật tùy chọn **Phân bổ thu hút lại.**
   3. Đặt **Re-engagement click-through lookback window**, đó là khoảng thời gian, bắt đầu từ khi nhấp chuột vào quảng cáo, trong đó các ứng dụng phải được khởi chạy để lượt nhấp được ghi nhận như một lượt thu hút lại. Chọn khung thời gian xem lại theo giờ hoặc ngày và đặt thanh trượt về giá trị mong muốn.
   4. Bật tính năng **Phân bổ lượt xem hết thu hút lại**.  
      **Lưu ý:** Google không gửi xác nhận quyền sở hữu đối với lượt hiển thị ứng dụng iOS. Nút chuyển phân bổ lượt xem hết/lượt cài đặt và thanh trượt khung thời gian xem lại không còn phù hợp với các ứng dụng iOS.
   5. Đặt **Re-engagement view-through lookback window**, đó là khoảng thời gian bắt đầu từ khi hiển thị quảng cáo, trong đó ứng dụng phải được khởi chạy để lượt hiển thị được ghi nhận như một lượt thu hút lại. Chọn khung thời gian xem lại theo giờ hoặc ngày và đặt thanh trượt về giá trị mong muốn.
   6. Thiết lập **Khung thời gian tương tác lại**. Đây là khoảng thời gian các sự kiện trong ứng dụng của người dùng được phân bổ cho nguồn phương tiện nhắm lại mục tiêu, theo sau một lượt nhấp hoặc một lượt hiển thị. Bạn có thể đặt giá trị theo ngày (1-90), giờ (tối đa 23) hoặc thậm chí là trọn đời. Thời gian mặc định là 30 ngày.  

      [![](https://files.readme.io/221a5489e91a15f1d9e4db9ab8f7cbff9e47dc1b50b0f7b43323096b26008870-30759261966225.png)](https://files.readme.io/221a5489e91a15f1d9e4db9ab8f7cbff9e47dc1b50b0f7b43323096b26008870-30759261966225.png)
10. Nếu bạn có tiện ích mở rộng ứng dụng iOS cho Google Ads:  
    Để nhận phân bổ từ liên kết quảng cáo, hãy chuyển đến tab **<Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#attribution-link-tab">Attribution link</Anchor>**, tạo liên kết phân bổ nền tảng đơn AppsFlyer và chèn liên kết đó vào tiện ích mở rộng ứng dụng Google Ads.  
    **Lưu ý:** Đảm bảo thêm tên chiến dịch tĩnh (bắt buộc).  

    [![](https://files.readme.io/6b7513829fb3abbaab75942e3612760f39f6ae6502064eac1f31b0783a63e95b-30759221884561.png)](https://files.readme.io/6b7513829fb3abbaab75942e3612760f39f6ae6502064eac1f31b0783a63e95b-30759221884561.png)
11. Truy cập tab **Cost**.
12. Bật tùy chọn **Get cost, clicks, and impressions data**.
13. Nhấp vào nút **Connect Google Ads** và đăng nhập vào tài khoản Google của bạn để nhận tất cả chi phí chiến dịch Google Ads trên AppsFlyer. <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-cost-and-ad-revenue">Thông tin chi tiết tại đây</Anchor>.
14. Nhấp vào **Save**.

<div id="stop" />

> ❗️ **Dừng lại!**
>
> Bạn PHẢI **[qua bước 4](/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory) để xem lượt cài đặt Google Ads trong AppsFlyer.**
> Nếu bạn cũng cần ánh xạ các sự kiện trong ứng dụng của mình tới Google Ads, trước tiên hãy hoàn thành [bước 3](/docs/google-ads-adwords-integration-setup-for-advertisers#step-3-map-your-inapp-events-recommended).

</Accordion>

<div id="step-3-map-your-inapp-events-recommended" />

<Accordion title="Bước 3: Ánh xạ các sự kiện trong ứng dụng của bạn (khuyến nghị)">

**(Bất kỳ thành viên nào được liên kết với tài khoản AppsFlyer)**

[![In-app_event_postbacks_en-us.png](https://files.readme.io/fbeef1b9d6f4462750d849878045d31b4a6614a9f36d20cd9c6f69d91a34f65a-30759221886609.png)](https://files.readme.io/fbeef1b9d6f4462750d849878045d31b4a6614a9f36d20cd9c6f69d91a34f65a-30759221886609.png)

1. Chuyển đến tab **Integration** và cuộn xuống phần **In-app event postbacks**.

   <div id="note-1" />

   > 📘 **Lưu ý**
   >
   > Khi bật ánh xạ sự kiện trong ứng dụng của Google Ads cho một ứng dụng **lần đầu:**
   >
   > * Sự kiện **af\_app\_opened** được tự động xác định và ánh xạ tới **session\_start** (nếu không, hãy thêm theo cách thủ công).
   > * Trong mục **for users from**, bạn phải chọn **All media sources, including organic** cho từng sự kiện để cho phép Google Ads nhận các sự kiện này. Sau khi tích hợp được thiết lập thành công, bạn có thể thay đổi lựa chọn này cho bất kỳ sự kiện nào.

2. Bật tùy chọn **In-app event postbacks**.
3. Nhấp vào **Add event** để thêm một SDK hoặc sự kiện từ máy chủ đến máy chủ vào danh sách.
4. Điền những tham số dưới đây: 

| Tên tham số | Mô tả |
| --- | --- |
| **AppsFlyer event** | Tên của sự kiện mà AppsFlyer nhận được từ SDK sẽ được tích hợp vào ứng dụng của bạn hoặc từ các sự kiện máy chủ đến máy chủ.<br />**Mẹo**: Bạn không thấy sự kiện đang tìm kiếm?<ul><li>Hãy đảm bảo kích hoạt sự kiện trên thiết bị có cài đặt không tự nhiên và kiểm tra lại.</li><li>Nhập vào **AppsFlyer event**, sau đó nhấp vào **Create custom**. Đọc thêm về <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#sự-kiện-tùy-chỉnh">ánh xạ sự kiện tùy chỉnh.</Anchor></li></ul> |
| **mapped to partner event** | Tên hoặc ID duy nhất của từng sự kiện được xác định ở Google Ads. Các cấu hình ánh xạ có thể có là:<ul><li>**Text field:** Nhận ID sự kiện tương ứng từ Google Ads.</li><li>**Drop-down box:** Chọn sự kiện AppsFlyer được xác định trước phù hợp nhất.</li><li>**As is**: Gửi các sự kiện nguyên trạng, mà không cần ánh xạ tên.</li></ul> |
| **for users from** | Chọn tùy chọn gửi cho sự kiện:<ul><li>**This partner only**: Chỉ gửi đăng lại khi sự kiện này được phân bổ cho Google Ads.</li><li>**All media sources, including organic**: Gửi đăng lại cho các sự kiện được quy cho bất kỳ đối tác và sự kiện tự nhiên nào.</li></ul> |
| **including** | <ul><li>**No data (default)**: Chỉ gửi riêng sự kiện mà không có giá trị sự kiện.</li><li>**Values and revenue**: Gửi tất cả các tham số sự kiện, **bao gồm cả** giá trị doanh thu (nếu tồn tại trong sự kiện).</li><li>**Values without revenue**: Gửi tất cả các tham số **không bao gồm** giá trị doanh thu.</li></ul> |

5. Nhấp vào **Save integration**.
6. Sau khi lưu tích hợp, trong khi vẫn ở trang cấu hình, bạn có thể tích hợp thêm ứng dụng của mình với đối tác.
   1. Từ góc trên cùng bên trái, dưới tên đối tác, hãy nhấp vào tên ứng dụng để mở danh sách ứng dụng.
   2. Chọn một ứng dụng khác từ danh sách thả xuống.
   3. Lặp lại các bước tích hợp đối với ứng dụng đã chọn.

</Accordion>

<div id="step-4-measure-your-app-conversions-mandatory" />

<Accordion title="Bước 4: Đo lường chuyển đổi ứng dụng của bạn (bắt buộc)">

<div id="note" />

<div id="important-1" />

> 🚧 **Quan trọng!**
>
> Để Google Ads đăng ký lượt chuyển đổi mới, bạn phải **khởi chạy ứng dụng của mình và thực hiện ít nhất một lần các sự kiện trong ứng dụng được ánh xạ**. Để thử nghiệm ứng dụng iOS, bạn phải thu thập IDFA để xem sự kiện. Có thể mất đến 6 giờ cho đến khi các lượt chuyển đổi sự kiện được thêm vào hàng đợi. Sau khi các lượt chuyển đổi được thêm vào, bạn có thể nhập chúng và lượt chuyển đối mới sẽ thay đổi trạng thái từ "No recent conversion" thành "recording conversion".

Bước này yêu cầu **quyền truy cập quản trị của Google** vào tài khoản để tạo ID liên kết.

Thực hiện theo các bước được mô tả trong <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7382633?sjid=11699141105296914680-EU">tài liệu Trợ giúp của Google Ads</Anchor>. Sau đây là những điều cần lưu ý:

* Ở Bước 7, chọn hộp bên cạnh **first\_open** cho tất cả các ứng dụng của bạn và cho mỗi sự kiện bạn muốn nhập. Nếu mã định danh Sự kiện Đối tác trong Google Ads đã bị thay đổi hoặc được gắn nhãn là CUSTOM, trong khi tên sự kiện tương ứng đã được sửa đổi trong AppsFlyer, thì bạn sẽ cần nhập lại dữ liệu.
* Sau khi hoàn tất quy trình, bạn có thể xem các sự kiện chuyển đổi của bên thứ ba trên trang **Conversions** > **Summary**. Nếu sự kiện không xuất hiện trong danh sách hoặc sự kiện đó đã bị xóa khỏi danh sách chuyển đổi của Google Ads
  1. Nhấp vào **View all conversion actions**. Bộ lọc **Status** sẽ xuất hiện.
  2. Nhấp vào **Status** và chọn **All** để xem tất cả các sự kiện, kể cả các sự kiện đã bị vô hiệu hóa và bị xóa.
* Đảm bảo thiết lập "đưa vào lượt chuyển đổi" phù hợp với mục tiêu chiến dịch của bạn trong Google Ads. Để biết thêm thông tin, hãy tham khảo ý kiến của đại diện Google của bạn hoặc tham khảo tài liệu Google <Anchor target="_blank" href="https://support.google.com/google-ads/answer/4677036?hl=en&co=ADWORDS.IsAWNCustomer=false">tại đây</Anchor>.

Xin chúc mừng! Giờ đây, bạn đang đo lường các chiến dịch di động của Google Ads với AppsFlyer!

</Accordion>

</Accordion>

</Accordion>

<div id="tip" />

> 👍 **Mẹo**
>
> Tích hợp API Google Ads tự động đưa vào tính năng tiếp thị lại Google Ads. Bằng cách hoàn thành tích hợp này và gửi các sự kiện tới Google Ads, bạn có thể tạo danh sách đối tượng tiếp thị lại trong Google Ads mà không cần bất kỳ tích hợp bổ sung nào.

<div id="granting-permissions-to-google-ads-team-members" />

## Cấp quyền cho các thành viên nhóm Google Ads

Bạn có thể cấp quyền cho Google Ads <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#permissions-tab">truy cập vào một số dữ liệu nhất định trong tài khoản của mình.</Anchor> Bạn có thể thực hiện việc cấp quyền này trên trang cấu hình Google Ads trong tab Permission cho mỗi ứng dụng trong số các ứng dụng của bạn.

Để có thể có được các quyền này và quyền truy cập ứng dụng của bạn, đại diện Google Ads của bạn phải là thành viên nhóm trong tài khoản đối tác của Google Ads trên Appsflyer.

Do các yêu cầu về quyền riêng tư của Google, Google chỉ có thể thêm thành viên nhóm mới vào tài khoản đối tác AppsFlyer của mình khi được nhà quảng cáo yêu cầu một cách rõ ràng.

Để cấp quyền truy cập cho thành viên nhóm Google Ads vào ứng dụng của bạn, hãy thực hiện như sau:

1. Điền vào và gửi <Anchor target="_blank" href="https://docs.google.com/forms/d/e/1FAIpQLSfJmwEPxy4bXw0mEsKfJ3D5dZmRZgHS3LCiyoEFsZRos0jWIQ/viewform">biểu mẫu này</Anchor> để yêu cầu thêm người quản lý tài khoản của bạn vào tài khoản đối tác của Google trên AppsFlyer.
2. Đợi Google Ads xác nhận đã thêm người quản lý tài khoản Google Ads của bạn.
3. Đi đến **Configuration** > **Active Integrations** > **Google Ads** > **Permissions**, và thêm email của người quản lý tài khoản vào danh sách các thành viên trong nhóm.
4. Kích hoạt các quyền bạn muốn cấp cho người quản lý tài khoản Google Ads.

Đọc thêm về cách <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#permissions-tab">cấp quyền cho Mạng quảng cáo</Anchor>.

<div id="enabling-google-ads-attribution-for-agencies" />

## Bật phân bổ Google Ads cho đại lý

AppsFlyer hỗ trợ thiết lập cấu hình đại lý với Google Ads. Điều quan trọng là nhà quảng cáo và đại lý phải có tài khoản Google Ads riêng biệt để cho phép AppsFlyer xác định chính xác dữ liệu. Để biết chi tiết, hãy nhấp <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-integration-setup-for-agencies">vào đây</Anchor>.

<div id="running-with-multiple-google-ads-accounts" />

## Chạy với nhiều Tài khoản Google Ads

AppsFlyer hỗ trợ làm việc với nhiều tài khoản Google Ads cho cùng một ứng dụng. Điều này được thực hiện thông qua việc chia sẻ ID Liên kết trong Google Ads và nhập các sự kiện vào từng tài khoản Google Ads.

Để biết thêm chi tiết về cách chia sẻ ID liên kết Google Ads của bạn, hãy nhấp vào <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001">đây</Anchor>.

<div id="ios-app-campaigns" />

## Chiến dịch Ứng dụng iOS

**Lưu ý**: Phần này áp dụng cho các chiến dịch ứng dụng đối với lượt cài đặt và **không phải** chiến dịch thu hút của ứng dụng.

Vào ngày 27 tháng 1 năm 2021, <Anchor target="_blank" href="https://blog.google/products/ads-commerce/preparing-developers-and-advertisers-for-policy-updates/">Google đã công bố các nội dung cập nhật về chính sách</Anchor> để phù hợp với bản phát hành iOS 14.

Kể từ khi bắt đầu thực thi ATT, các ứng dụng Google trên iOS không nhắc ATT và do đó, các sản phẩm của Google Ads <Anchor target="_blank" href="https://support.google.com/google-ads/answer/10417364">đã ngừng sử dụng</Anchor> mã định danh thiết bị (IDFA) thuộc ATT.

Để duy trì báo cáo và tối ưu hóa chiến dịch, Google đã mở rộng chuyển đổi được mô hình hóa sang lưu lượng truy cập iOS 14+.

Vì chuyển đổi được mô hình hóa không phụ thuộc vào ID của thiết bị, nên bắt đầu từ bản phát hành iOS14.5, logic khoảng không quảng cáo của chiến dịch cài đặt ứng dụng iOS được Google sử dụng như sau:

* Khoảng không quảng cáo/kênh tìm kiếm ACI iOS không được phân bổ (theo chính sách trước đó ngày 24 tháng 1 năm 2020).
* Khoảng không quảng cáo/kênh YouTube ACI iOS không được phân bổ vì ứng dụng YouTube không nhắc ATT nên không thể sử dụng IDFA.
* Khoảng không quảng cáo/kênh Hiển thị ACI iOS chỉ có thể được phân bổ khi có ID của thiết bị, trong trường hợp có sự đồng ý trên ứng dụng của cả nhà quảng cáo và nhà phát hành.

<div id="note-2" />

<div id="using-deferred-deep-linking-in-app-campaigns" />

## Sử dụng liên kết sâu gián tiếp rong Chiến dịch ứng dụng

<Anchor target="_blank" href="https://support.google.com/google-ads/answer/9959794?hl=en&ref_topic=10011599">Nguồn cấp dữ liệu của Google trong Chiến dịch ứng dụng</Anchor> giúp bạn mang đến trải nghiệm mượt mà theo nội dung cụ thể cho người dùng di động mới.

Khi một người dùng tiềm năng nhấp vào nguồn cấp dữ liệu, họ sẽ được chuyển hướng đến trang ứng dụng. Sau khi người dùng cài đặt và khởi chạy ứng dụng, SDK cung cấp thông tin chi tiết sản phẩm cụ thể (ví dụ: giày chạy bộ) với liên kết sâu gián tiếp. Nhà phát triển ứng dụng sử dụng dữ liệu này để cung cấp trải nghiệm người dùng có liên quan trong ứng dụng.

**Để bật liên kết sâu gián tiếp với Google Ads:**

1. Đảm bảo sử dụng <Anchor target="_blank" href="/marketers/vi/docs/conversion-data-payloads-and-scenarios#phân-bổ-lại-với-liên-kết-sâu-bị-trì-hoãn">GCD</Anchor> để nhận tham số `af_dp` trong SDK AppsFlyer.
2. Trong Google, <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9958973?hl=en&ref_topic=10011599">thiết lập nguồn cấp dữ liệu</Anchor>.
3. Trong AppsFlyer, đi đến **Configuration** > **Active Integrations**. Chọn **Google Ads (Adwords)**.
4. Trong tab **Integration**, bật **Deferred deep linking with Google Ads.**
5. Nhấp vào **Save integration**.

<div id="google-ads-parameter-mapping" />

## Ánh xạ tham số Google Ads

Bảng sau đây mô tả ánh xạ tham số giữa Google Ads và AppsFlyer. Lưu ý rằng nhà quảng cáo không thể thêm các than số được cá nhân hóa vào bất kỳ chiến dịch Google Ads nào.

<table><thead><tr><th><p><strong>Loại mạng</strong></p></th><th><strong>Tìm kiếm</strong></th><th><strong>Hiển thị</strong></th><th><strong>YouTube</strong></th></tr></thead><tbody><tr><td>Kênh (af_channel)</td><td>Xem bảng bên dưới, <a href="./google-ads-adwords-integration-setup-for-advertisers#cách-điền-tham-số-kênh">Cách điền tham số <kbd>Kênh</kbd></a> </td></tr><tr><td>Chiến dịch (c)</td><td>Có</td><td>Có</td><td>Có</td></tr><tr><td><p>ID Chiến dịch (af_c_id)</p></td><td>Có</td><td>Có</td><td>Có</td></tr><tr><td>Bộ quảng cáo (af_adset)<br/>Được điền bằng tham số ad_group_name.<br/>Nếu tham số này rỗng, thì AF sẽ điền af_adset với ad_group_id.</td><td>Có</td><td>Có</td><td>Có</td></tr><tr><td>ID Bộ quảng cáo (af_adset_id) được điền bằng tham số ad_group_id của Google</td><td>Có</td><td>Có</td><td>Có</td></tr><tr><td><p>Quảng cáo (af_ad)</p></td><td>Không áp dụng</td><td>Không áp dụng</td><td>Không áp dụng</td></tr><tr><td>ID Quảng cáo (af_ad_id)</td><td>Không áp dụng</td><td>Không áp dụng</td><td>Không áp dụng</td></tr><tr><td>Loại quảng cáo (af_ad_type)</td><td>Có\*</td><td>Có\*</td><td>Có\*</td></tr><tr><td>ID Trang (af_siteid)</td><td>GoogleSearch/<br/>SearchPartners</td><td>Không áp dụng</td><td>YouTubeVideos/<br/>VideoPartners</td></tr><tr><td>Từ khóa</td><td>Không áp dụng</td><td>Không áp dụng</td><td>Không áp dụng</td></tr></tbody></table>

<div id="note-3" />

<div id="populate-the-channel-parameter" />

### Cách điền tham số `Kênh`

Google Ads không gửi tham số `Channel(af_channel)`. AppsFlyer quyết định cách điền tham số này cho các loại chiến dịch nhận được từ Google Ads, theo các quy tắc sau:

<table><thead><tr><th colspan="2">Logic Loại chiến dịch <strong>AND</strong> Loại mạng:</th><th rowspan="2"> Tham số <kbd>Kênh</kbd> </th><th rowspan="2">Ví dụ</th></tr><tr><th>campaign_type</th><th>network_type</th></tr></thead><tbody><tr><td> <kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>Mua sắm</kbd> hoặc <kbd>Khách sạn</kbd> </td><td><p>Mọi loại mạng</p></td><td><kbd>campaign_type_network_type</kbd></td><td>kênh = <kbd>ACI_Search</kbd> </td></tr><tr><td><p><strong>Không phải:</strong></p><kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>Mua sắm</kbd> hoặc <kbd>Khách sạn</kbd> </td><td><kbd>Hiển thị</kbd></td><td><kbd>network_subtype</kbd></td><td>kênh = <kbd>mGDN</kbd> </td></tr><tr><td><p><strong>Không phải:</strong></p><kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>Mua sắm</kbd> hoặc <kbd>Khách sạn</kbd> </td><td><p><strong>Không phải:</strong></p><kbd>Hiển thị</kbd> </td><td><kbd>network_type</kbd></td><td>kênh = <kbd>Search</kbd> </td></tr></tbody></table>

Để biết thêm thông tin về loại quảng cáo nào có sẵn trong phản hồi của Google, hãy xem <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">tại đây</Anchor>.

<div id="campaign-type-app-campaigns" />

### Loại chiến dịch: chiến dịch ứng dụng

<div id="changes-to-campaign-names-by-google-ads" />

#### Các thay đổi đối với tên chiến dịch của Google Ads

| Cho đến ngày 15 tháng 2 năm 2021 | Bắt đầu từ ngày 23 tháng 2 năm 2021 |
| --- | --- |
| UAC | ACI |
| UACE | ACE |
| UACPre | ACPRE |

**Lưu ý:** Loại tên chiến dịch được đặt theo ngày của lượt nhấp hoặc ngày của lượt hiển thị, không phải ngày cài đặt.

<div id="engaged-view-parameter-in-raw-data-reports" />

### Tham số lượt xem thu hút trong báo cáo dữ liệu thô

Lượt xem tương tác là lượt hiển thị một quảng cáo video dài hơn 10 giây cho người dùng. Lượt này tính là một lượt nhấp. Đối với Android, các lượt này hiển thị trong báo cáo dữ liệu thô, điền vào mục “sub param 5”.  
Tham số này được hiển thị nếu lượt xem thu hút xảy ra trong khung thời gian xem lại lượt nhấp đã xác định trong AppsFlyer, nhưng tối đa là 3 ngày.

<div id="send-complex-in-app-events-to-google-ads" />

<div id="important-2" />

> 🚧 **Quan trọng!**
>
> * Google là một SRN (Mạng Tự Báo cáo). Để biết thêm thông tin về cách hoạt động của luồng phân bổ cho các mạng này, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns">đây</Anchor>.
> * AppsFlyer có thể hiển thị bất kỳ thông tin chiến dịch nào được Google cung cấp. Loại chiến dịch (Tìm kiếm, Video, Hiển thị) và thông tin liên quan được xác định bởi Google. Để biết thêm thông tin chi tiết, hãy nhấp vào <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">đây</Anchor>.

<div id="optimize-google-ads-campaigns-for-conversions-without-device-id" />

## Tối ưu hóa các chiến dịch Google Ads cho các lượt chuyển đổi mà không cần ID thiết bị

Bắt đầu với iOS14.5 trở lên và Android 12 trở lên, Google Ads đã giới thiệu một số mã định danh. Các mã định danh này được sử dụng để phân bổ xác định các lượt chuyển đổi không có ID thiết bị:

| Mã định danh | Sẵn có từ | Nguồn | Hệ điều hành | Được sử dụng cho | Tính chi tiết của dữ liệu |
| --- | --- | --- | --- | --- | --- |
| gclid | Tháng 12 năm 2021 | Liên kết giới thiệu Google Play | Android | Lượt cài đặt | Cấp người dùng |
| gclid | Tháng 12 năm 2021 | URL Liên kết sâu | Android + iOS | Tương tác lại | Cấp người dùng |
| gbraid | Tháng 3 năm 2021 | URL Liên kết sâu | iOS | Tương tác lại | Hợp nhất |

Khi AppsFlyer nhận được các mã định danh này và gửi chúng trong các đăng lại của Google Ads, Google Ads có thể xác nhận các lượt chuyển đổi dựa trên các mã định danh đó. AppsFlyer sử dụng xác nhận quyền sở hữu và xem xét các tham số để phân bổ và liên kết các sự kiện LTV.  
**Để cho phép nhận các tham số này, nhà quảng cáo không cần thực hiện bất kỳ hành động nào.**

<div id="google-probabilistic-attribution-icm-traits-and-limitations" />

<div id="advertising-without-the-firebase-sdk" />

<div id="data-visibility-by-operating-system" />

### Khả năng hiển thị dữ liệu theo hệ điều hành

**Ứng dụng Android:**

Trong AppsFlyer và Google Ads, nhà quảng cáo có thể nhận toàn bộ dữ liệu chiến dịch về lưu lượng truy cập mà không cần ID thiết bị – cả về lượt cài đặt và hành động thu hút lại.

**Ứng dụng iOS:**

Trong Google Ads và AppsFlyer, nhà quảng cáo có thể nhận dữ liệu chiến dịch đầy đủ về lưu lượng truy cập mà không cần ID thiết bị cho hoạt động tương tác lại của họ.

<div id="h_01HDP0SBEE75MAT4A4S9E7Y7FF" />

> 📄 **Xem thêm**
>
> * Để biết những lưu ý liên quan đến iOS 14, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/get-skan-postback-data-from-google-ads">khả năng tương tác SKAdNetwork của Google Ads với AppsFlyer</Anchor>.

<div data-zendesk-anchors="h_01HMEH8VW3PYCZ6GC4T5BYBS3V=quan-tr%E1%BB%8Dng using-google-ads=s%E1%BB%AD-d%E1%BB%A5ng-google-ads h_01HACTC1H575PKYKRH4T4NVKH1=s%E1%BB%AD-d%E1%BB%A5ng-google-ads configuring-google-ads-attribution-for-advertisers=%C4%91%E1%BB%8Bnh-c%E1%BA%A5u-h%C3%ACnh-ph%C3%A2n-b%E1%BB%95-google-ads-cho-nh%C3%A0-qu%E1%BA%A3ng-c%C3%A1o h_01HACTC1H5MANBCRWYQPNW5CC2=%C4%91%E1%BB%8Bnh-c%E1%BA%A5u-h%C3%ACnh-ph%C3%A2n-b%E1%BB%95-google-ads-cho-nh%C3%A0-qu%E1%BA%A3ng-c%C3%A1o h_01HACTC1H5XXGREE80GFHGZY7N=l%C6%B0u-%C3%BD h_01HACTC1H5XEJEPMZ4C7GP8GG6=step-1-create-the-google-ads-link-id-mandatory h_01HACTC1H5HEP9759J2PCPPZSW=step-2-set-up-google-ads-on-appsflyer-mandatory h_01HACTC1H5R995RXYRFQBFHRF1=quan-tr%E1%BB%8Dng-1 h_01HACTC1H5EFJKV6AXNSTNFZA4=d%E1%BB%ABng-l%E1%BA%A1i h_01HACTC1H50DDS3WCZ9DCHKN0P=step-3-map-your-inapp-events-recommended h_01HACTC1H58WHJDBN2DRQAZKGB=l%C6%B0u-%C3%BD-1 h_01HACTC1H5GV04KFM29NCCK8J2=step-4-measure-your-app-conversions-mandatory h_01HSX7TJC7PQ0ATM1J86Z4HMYJ=quan-tr%E1%BB%8Dng-2 h_01HACTC1H5Z3XXS1MGBS4WYJBV=m%E1%BA%B9o granting-permissions-to-google-ads-team-members=c%E1%BA%A5p-quy%E1%BB%81n-cho-c%C3%A1c-th%C3%A0nh-vi%C3%AAn-nh%C3%B3m-google-ads h_01HACTC1H5PAY95M4H1A6WTSEF=c%E1%BA%A5p-quy%E1%BB%81n-cho-c%C3%A1c-th%C3%A0nh-vi%C3%AAn-nh%C3%B3m-google-ads enabling-google-ads-attribution-for-agencies=b%E1%BA%ADt-ph%C3%A2n-b%E1%BB%95-google-ads-cho-%C4%91%E1%BA%A1i-l%C3%BD h_01HACTC1H5QE93EAYYVVDQV2WC=b%E1%BA%ADt-ph%C3%A2n-b%E1%BB%95-google-ads-cho-%C4%91%E1%BA%A1i-l%C3%BD running-with-multiple-google-ads-accounts=ch%E1%BA%A1y-v%E1%BB%9Bi-nhi%E1%BB%81u-t%C3%A0i-kho%E1%BA%A3n-google-ads h_01HACTC1H5Z8B15RHQ75HVV2RP=ch%E1%BA%A1y-v%E1%BB%9Bi-nhi%E1%BB%81u-t%C3%A0i-kho%E1%BA%A3n-google-ads ios-app-campaigns=chi%E1%BA%BFn-d%E1%BB%8Bch-%E1%BB%A9ng-d%E1%BB%A5ng-ios h_01HACTC1H5X567H6A8M3FWCTAN=chi%E1%BA%BFn-d%E1%BB%8Bch-%E1%BB%A9ng-d%E1%BB%A5ng-ios using-deferred-deep-linking-in-app-campaigns=s%E1%BB%AD-d%E1%BB%A5ng-li%C3%AAn-k%E1%BA%BFt-s%C3%A2u-gi%C3%A1n-ti%E1%BA%BFp-rong-chi%E1%BA%BFn-d%E1%BB%8Bch-%E1%BB%A9ng-d%E1%BB%A5ng h_01HACTC1H57HJZNAGDKSQD6MVC=s%E1%BB%AD-d%E1%BB%A5ng-li%C3%AAn-k%E1%BA%BFt-s%C3%A2u-gi%C3%A1n-ti%E1%BA%BFp-rong-chi%E1%BA%BFn-d%E1%BB%8Bch-%E1%BB%A9ng-d%E1%BB%A5ng google-ads-parameter-mapping=%C3%A1nh-x%E1%BA%A1-tham-s%E1%BB%91-google-ads h_01HACTC1H6P1A2E160Z6GAGZZS=%C3%A1nh-x%E1%BA%A1-tham-s%E1%BB%91-google-ads how-to-populate-the-channel-parameter=c%C3%A1ch-%C4%91i%E1%BB%81n-tham-s%E1%BB%91-k%C3%AAnh h_01HACTC1H6TPTDDFSMPQ9YVMDY=c%C3%A1ch-%C4%91i%E1%BB%81n-tham-s%E1%BB%91-k%C3%AAnh campaign-type-app-campaigns=lo%E1%BA%A1i-chi%E1%BA%BFn-d%E1%BB%8Bch-chi%E1%BA%BFn-d%E1%BB%8Bch-%E1%BB%A9ng-d%E1%BB%A5ng h_01HACTC1H6CEGD2E3HXHWFWBRB=lo%E1%BA%A1i-chi%E1%BA%BFn-d%E1%BB%8Bch-chi%E1%BA%BFn-d%E1%BB%8Bch-%E1%BB%A9ng-d%E1%BB%A5ng changes-to-campaign-names-by-google-ads=c%C3%A1c-thay-%C4%91%E1%BB%95i-%C4%91%E1%BB%91i-v%E1%BB%9Bi-t%C3%AAn-chi%E1%BA%BFn-d%E1%BB%8Bch-c%E1%BB%A7a-google-ads h_01HACTC1H6A028HKVXJ66MCF6M=c%C3%A1c-thay-%C4%91%E1%BB%95i-%C4%91%E1%BB%91i-v%E1%BB%9Bi-t%C3%AAn-chi%E1%BA%BFn-d%E1%BB%8Bch-c%E1%BB%A7a-google-ads engaged-view-parameter-in-raw-data-reports=tham-s%E1%BB%91-l%C6%B0%E1%BB%A3t-xem-thu-h%C3%BAt-trong-b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 h_01HACTC1H6Q6WCTK4Z9RGV6PA4=tham-s%E1%BB%91-l%C6%B0%E1%BB%A3t-xem-thu-h%C3%BAt-trong-b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 h_01HACTC1H62HC36C08ZBFZ05XS=quan-tr%E1%BB%8Dng-3 optimize-google-ads-campaigns-for-conversions-without-device-id=t%E1%BB%91i-%C6%B0u-h%C3%B3a-c%C3%A1c-chi%E1%BA%BFn-d%E1%BB%8Bch-google-ads-cho-c%C3%A1c-l%C6%B0%E1%BB%A3t-chuy%E1%BB%83n-%C4%91%E1%BB%95i-m%C3%A0-kh%C3%B4ng-c%E1%BA%A7n-id-thi%E1%BA%BFt-b%E1%BB%8B h_01HACTC1H6EFDVN9N89Y17HDFR=t%E1%BB%91i-%C6%B0u-h%C3%B3a-c%C3%A1c-chi%E1%BA%BFn-d%E1%BB%8Bch-google-ads-cho-c%C3%A1c-l%C6%B0%E1%BB%A3t-chuy%E1%BB%83n-%C4%91%E1%BB%95i-m%C3%A0-kh%C3%B4ng-c%E1%BA%A7n-id-thi%E1%BA%BFt-b%E1%BB%8B data-visibility-by-operating-system=kh%E1%BA%A3-n%C4%83ng-hi%E1%BB%83n-th%E1%BB%8B-d%E1%BB%AF-li%E1%BB%87u-theo-h%E1%BB%87-%C4%91i%E1%BB%81u-h%C3%A0nh h_01HACTC1H6WZNMVJK479M5KJYF=kh%E1%BA%A3-n%C4%83ng-hi%E1%BB%83n-th%E1%BB%8B-d%E1%BB%AF-li%E1%BB%87u-theo-h%E1%BB%87-%C4%91i%E1%BB%81u-h%C3%A0nh h_01HDP0SBEE75MAT4A4S9E7Y7FF=xem-th%C3%AAm" />
