---
title: Thiết lập tích hợp X Ads (trước đây là Twitter Ads)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:33:40Z'
  edited_at: '2023-11-30T14:22:47Z'
  id: 4410472471825
  locale: vi
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/vi/articles/4410472471825
---
> **Tổng quan:** Tích hợp tài khoản X Ads của bạn với AppsFlyer để hiển thị dữ liệu phân bổ của các chiến dịch X Ads.

## Kết nối tài khoản X Ads của bạn với AppsFlyer

<Accordion title="Xem">

<Embed title="Thiết lập tích hợp X Ads (trước đây là Twitter Ads)" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/a65pnqoyxw" providerUrl="https://fast.wistia.com" />

</Accordion>

<Accordion title="Đọc">

> 📘 **Trước khi bắt đầu**
>
> Đảm bảo bạn đã <Anchor target="_blank" href="https://business.twitter.com/en/help/account-setup/billing-basics.html">thêm phương thức thanh toán</Anchor> vào tài khoản X Ads của mình. Nếu không, bạn sẽ không thể kích hoạt tích hợp đối tác trong AppsFlyer.

1. Đăng nhập vào Tài khoản X Ads của bạn trên <Anchor target="_blank" href="https://ads.twitter.com">ads.twitter.com</Anchor> Nếu bạn không được tự động chuyển hướng đến trang Ads, hãy nhấp vào nút Ads ở góc trên cùng bên trái.
2. Khi được nhắc chọn chiến dịch **Simple (NEW)** hoặc **Advanced** , hãy chọn **Advanced**.
3. Trong **Campaign objective**, hãy chọn **App Installs** hoặc **App re-engagements**, sau đó nhấp vào **Next**.  

   ![twitter-campaign-objective.png](https://files.readme.io/d91bd357dea4878f098086a573191f64c2d1a38af8a6a809c6de7c468e04e043-6148255768337.png)
4. Chọn ứng dụng của bạn, sau đó nhấp vào liên kết **mobile measurement partner**.
5. Trên trang **Conversion tracking** , hãy nhấp vào **Go to AppsFlyer**.   

   ![twitter-mmp-selection.png](https://files.readme.io/ebe8e97971c01e0d87c694d2ca1fcc996abf608309d96badcbcda2713ab80d3e-6148393350033.png)
6. Một thông báo hiển thị cho bạn biết rằng bạn sắp rời khỏi X Ads để truy cập trang web AppsFlyer. Nhấp vào **Go to AppsFlyer** và đăng nhập vào Bảng điều khiển của bạn.  

   <Image alt="twitter-go-to-appsflyer.png" src="https://support.appsflyer.com/hc/article_attachments/4411046208401" width="576px" />
7. Trong AppsFlyer, dưới phần **Configuration (Cấu hình)** đi đến **Partner Marketplace (Thị trường Đối tác)**.
8. Tìm kiếm **X Ads** và chọn.
9. Trong tab **Integration** , chấp nhận các Điều khoản và Điều kiện của X Ads để Ghi nhận Chuyển đổi Ứng dụng Di động (MACT), sau đó nhấp vào **Save integration**.
10. Bật **Activate partner** và nhấp vào **Log in with X Ads**.
11. Cho phép AppsFlyer sử dụng tài khoản X Ads của bạn bằng cách nhấp vào **Authorize app**.   

    [<Image alt="" src="https://support.appsflyer.com/hc/en-us/article_attachments/4411037924497/Twitter_Ads_6.png" width="476px" />](https://support.appsflyer.com/hc/vi/article_attachments/4411037924497/Twitter_Ads_6.png)
12. Bật lại **Activate Partner** để hiển thị cài đặt tab **Integration** và bật phân bổ.  
    **Lưu ý:** Nút bật/tắt phải luôn ở trạng thái bật (được kích hoạt) trong thời gian bạn làm việc với đối tác. Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">kích hoạt đối tác.</Anchor>
13. Chọn tài khoản X Ads của bạn để kích hoạt chúng, sau đó nhấp vào **Save & Close**.  

    ![twitter_account_name.png](https://support.appsflyer.com/hc/article_attachments/4411046818193)

</Accordion>

## Thiết lập phân bổ qua X Ads

Để xem mô tả chi tiết về tiêu đề trang cấu hình đối tác, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner">đây</Anchor>.

<div id="integration-tab" />

<Accordion title="Tab tích hợp">

Tab **Integration** được chia thành các phần khác nhau như được mô tả dưới đây. <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">Đối tác phải được kích hoạt</Anchor> trong lần truy cập đầu tiên để cho phép thiết lập diễn ra.

### Đã kết nối Tài khoản Quảng cáo

Chọn tài khoản để cho phép phân bổ.

![Twitter_msc_new_4.png](https://files.readme.io/c64dd5ddc51f35ce195c689b3d14ec4ed4010133662096926f4e8c45e48d60c4-4411049509137.png)

### Phân bổ lượt nhấp qua

Sử dụng thanh trượt để đặt **thời gian tối đa từ khi nhấp chuột đến khi cài đặt**. Chỉ các lượt cài đặt (khởi chạy lần đầu) diễn ra trong khoảng thời gian xem lại mới có thể được phân bổ cho X Ads.

Bạn có thể tùy chỉnh giá trị này thành 1-23 giờ hoặc 1-30 ngày. Bạn nên đặt thời gian xem lại lượt nhấp qua thành 14 ngày, để phù hợp với X Ads.

![Twitter_msc_new_6.png](https://files.readme.io/39c3e080cf2fff3b7d9b3e2cf694fc439cd447a263b113ecfc6730a38f653283-4411047369361.png)

### Cửa sổ xem lại phân bổ lượt xem qua

Thanh trượt này cho phép bạn đặt **thời gian tối đa từ khi hiển thị tới khi cài đặt**. Chỉ các lượt cài đặt (lần khởi chạy đầu tiên) diễn ra trong khung thời gian xem lại này, sau một lần hiển thị quảng cáo, được phân bổ cho X Ads, miễn là không có nhấp chuột quảng cáo liên quan khác.

Bạn có thể tùy chỉnh giá trị này thành 1-23 giờ hoặc 1-7 ngày. Bạn nên đặt thời gian xem lại Lượt xem qua thành 1 ngày, để phù hợp với X Ads.

![Twitter_msc_new_7.png](https://files.readme.io/4f64c994b0cffec692ab99345e539caa4ef07b8f4a439851f18af3aada6ab473-4411049638033.png)

### Cài đặt tương tác lại

Phân bổ nhắm mục tiêu lại trên X Ads chỉ bao gồm những chuyển đổi thu hút lại.

Bật **Re-engagement attribution** để bắt đầu phân bổ tương tác lại cho X Ads.

#### Thời gian xem lại lượt nhấp tương tác lại

Đặt thời lượng cho **Re-engagement click-through lookback window** (thời gian tối đa sau khi một quảng cáo được nhấp vào, trong thời gian đó người dùng được nhắm lại mục tiêu có thể được phân bổ cho quảng cáo). Bạn có thể đặt giá trị theo giờ (tối đa 23 giờ) hoặc ngày (1-30 ngày).

![twitter-reengagement-activate.png](https://files.readme.io/9272c626eceeb8457584d2f1bd1d2adb16f9022994a2efa22eeaeb5b584e2149-4411049796625.png)

#### Thời gian xem lại lượt xem hết tương tác lại

Để bắt đầu phân bổ các lượt hiển thị quảng cáo nhắm lại mục tiêu, hãy kích hoạt **Phân bổ lượt xem hết tương tác lại**.

Đặt thời lượng cho **Thời gian xem lại lượt xem hết tương tác lại** (thời gian tối đa sau khi một quảng cáo được xem, trong thời gian đó người dùng được nhắm lại mục tiêu có thể được phân bổ cho quảng cáo). Bạn có thể đặt giá trị theo giờ (tối đa 23) hoặc ngày (1-7):

![twitter-reengagement-view-through.png](https://files.readme.io/6d4b80bbe1b953e5df5a6420d71ead781342c616e864e4d1b4d71c68fa9d17fa-4411038679569.png)

#### Thời gian tương tác lại

Đặt thời lượng cho **Re-engagement window** (Khung thời gian tương tác lại) (thời gian khi sự kiện trong ứng dụng của người dùng được phân bổ cho nguồn truyền thông nhắm lại mục tiêu). Bạn có thể đặt giá trị theo ngày (1-90), giờ (tối đa 23) hoặc thậm chí là trọn đời:

![Twitter-reengagement-window.png](https://files.readme.io/de80d79c777fc97caa0a28a342657475f0a05c14e30b1f96d24898a4638e1af8-4411047581201.png)

### Cài đặt đăng lại sự kiện trong ứng dụng

Trong phần này, bạn có thể ánh xạ các sự kiện AppsFlyer của mình với đối tác của mình qua các postback.

[![In-app_event_postbacks_en-us.png](https://files.readme.io/b215324955412d3a6fc0f719ad54560c25b537a4d1b87475d23c91fbf4262632-7900234463121.png)](https://files.readme.io/b215324955412d3a6fc0f719ad54560c25b537a4d1b87475d23c91fbf4262632-7900234463121.png)

**Để cấu hình đăng lại sự kiện trong ứng dụng:**

1. Đặt **ID Đối tác** (nếu cần).
2. Bật **In-app event postback** (Đăng lại sự kiện trong ứng dụng).
3. Nhấp vào **Add event** để thêm một SDK hoặc sự kiện từ máy chủ đến máy chủ vào danh sách.
4. Nhập các thông số cần thiết theo bảng dưới đây.  

| Tham số | Mô tả |
| --- | --- |
| **AppsFlyer event** | Tên của sự kiện mà AppsFlyer nhận được từ SDK được tích hợp vào trong ứng dụng của bạn hoặc từ các sự kiện máy chủ đến máy chủ.<br />**Mẹo**: Không thấy sự kiện bạn đang tìm kiếm?<ul><li>Hãy đảm bảo kích hoạt sự kiện trên thiết bị có cài đặt không tự nhiên và kiểm tra lại.</li><li>Nhập vào **AppsFlyer event**, sau đó nhấp vào **Create custom**. Đọc thêm về <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#sự-kiện-tùy-chỉnh">ánh xạ sự kiện tùy chỉnh.</Anchor></li></ul> |
| **mapped to partner event** | Tên hoặc ID duy nhất của từng sự kiện được xác định ở phía đối tác. <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#ánh-xạ-sự-kiện">Cấu hình ánh xạ</Anchor> có thể có là:<ul><li>**Trường văn bản:** Nhận ID sự kiện tương ứng từ đối tác.</li><li>**Hộp thả xuống:** Chọn sự kiện AppsFlyer được xác định trước phù hợp nhất.</li><li>**Giữ nguyên**: Gửi các sự kiện như vốn có mà không ánh xạ tên.</li></ul> |
| **for users from** | Chọn tùy chọn gửi cho sự kiện:<br /><br /><br /><br />**Lưu ý**<br />Để X Ads nhận được các lượt đăng lại do đại lý phân bổ, bạn phải chọn **All media sources, including organic**. Nếu không, X Ads sẽ không nhận được những lượt đăng lại đó.<ul><li>**Chỉ đối tác này**: chỉ gửi đăng lại khi sự kiện này được phân bổ cho đối tác này.</li><li>**All media sources, including organic**: gửi bài đăng lại cho các sự kiện được phân bổ cho bất kỳ đối tác và sự kiện tự nhiên nào.</li></ul> |
| **including** | <ul><li>**No data (mặc định)**: chỉ gửi bản thân sự kiện mà không gửi giá trị sự kiện.</li><li>**Values and revenue**: gửi tất cả các thông số sự kiện, **bao gồm** cả giá trị doanh thu (nếu có trong sự kiện).</li><li>**Values without revenue**: gửi tất cả các thông số, **ngoại trừ** giá trị doanh thu.</li></ul> |

5. [Tùy chọn] Nhấp vào <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/d84715dd43041f10684d42e4fe56fd4f76aa4c38fbf9df227c8f8f5610c4f859-19616850611857.png" width="30px" /> để đặt điều kiện gửi các sự kiện trong ứng dụng nhất định cho đối tác.  
   Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#đăng-lại-sự-kiện-trong-ứng-dụng-có-điều-kiện">đăng lại các sự kiện trong ứng dụng có điều kiện</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Tab Liên kết Phân bổ">

X Ads không sử dụng đường dẫn phân bổ để phân bổ.

> 📘 **Lưu ý**
>
> Đối với tất cả các <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns">mạng tự báo cáo (SRN)</Anchor>, chẳng hạn như Meta ads, Apple Search Ads, Ads, X Ads, v.v., tab này không hoạt động vì chúng không sử dụng các đường dẫn phân bổ bên ngoài.

</Accordion>

<div id="cost-tab" />

<Accordion title="Tab Chi phí">

Tích hợp chi phí cung cấp dữ liệu tổng hợp sau:

* Dữ liệu chi phí cho các chiến dịch, bộ quảng cáo, quảng cáo và cấp kênh của bạn. Xem <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">bảng tích hợp chi phí mạng quảng cáo</Anchor> để biết đầy đủ chi tiết về các phương diện, số liệu và tính năng được hỗ trợ.  
  **Lưu ý**: Dữ liệu chi phí yêu cầu phải có đăng ký <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>.
* Dữ liệu về lượt chuột, lượt hiển thị và dữ liệu phong phú (từ khóa, tên chiến dịch và bộ quảng cáo).

**Để kích hoạt API Chi phí**:

* Tuân thủ <Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">hướng dẫn tích hợp này</Anchor>.

<Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Xem trạng thái API chi phí của bạn</Anchor> và lần cuối cùng AppsFlyer lấy được dữ liệu chi phí phù hợp trong trang tổng quan trạng thái tích hợp chi phí (và doanh thu quảng cáo) hoặc trang tổng quan mạng quảng cáo cá nhân.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Tab Doanh thu quảng cáo">

Tích hợp doanh thu quảng cáo không khả dụng cho X Ads. Để nhận dữ liệu doanh thu quảng cáo, hãy tích hợp MoPub.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Tab quyền truy cập">

Trong tab này, bạn có thể chọn quyền cấp cho X Ads, cho dù đối tác là mạng quảng cáo, đại lý hay thậm chí cả hai. Lưu ý rằng ngay cả khi tính năng phân bổ bị vô hiệu hóa đối với X Ads, tab quyền vẫn hoạt động và bạn có thể cấp quyền kiểm soát cho X Ads.

Sử dụng các chuyển đổi này để cấp quyền cho mạng quảng cáo xử lý cấu hình của riêng nó cho ứng dụng của bạn:

### Quyền truy cập mạng quảng cáo

* **Allow to configure integration** (Cho phép thiết lập cấu hình tích hợp) - cho phép đối tác thiết lập thanh cấu hình (ngoại trừ postback sự kiện trong ứng dụng)
* **Allow to configure in-app event postbacks** (Cho phép thiết lập cấu hình postbback sự kiện trong ứng dụng) - cho phép đại lý thiết lập postback sự kiện trong ứng dụng tự ánh xạ trên tab tích hợp
* **Allow access to your retention report** (Cho phép truy cập báo cáo giữ chân người dùng) - chỉ với dữ liệu giữ chân người dùng của đại lý
* **Allow access to your aggregate loyal user data** (Cho phép truy cập vào dữ liệu người dùng trung thành tổng hợp của bạn) - chỉ với dữ liệu người dùng trung thành của chính đối tác
* **Cho phép truy cập vào dữ liệu sự kiện trong ứng dụng hợp nhất** - chỉ với dữ liệu sự kiện trong ứng dụng của đối tác
* **Allow access to your aggregate revenue data** (Cho phép truy cập vào dữ liệu tổng doanh thu của bạn) - chỉ với dữ liệu doanh thu được phân bổ cho đối tác
* **Allow access to your Protect360 dashboard** (Cho phép truy cập vào bảng điều khiển Protect360 của bạn) - chỉ với dữ liệu Protect360 của đối tác và miễn là tính năng được kích hoạt cho nhà quảng cáo

Tìm hiểu thêm về việc cấp <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#permissions-tab">quyền truy cập mạng quảng cáo</Anchor>.

### Cấp quyền cho Đại lý

Tìm hiểu về việc <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#cấp-quyền-cho-đại-lý">cấp quyền cho đại lý</Anchor>.

</Accordion>

## Video Cài đặt X Ads Nâng cao

<Accordion title="Xem">

<Embed title="Thiết lập tích hợp X Ads (trước đây là Twitter Ads)" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/3ypfld8enr" providerUrl="https://fast.wistia.com" />

</Accordion>

## Điểm hạn chế

X Ads không hỗ trợ phân bổ MMP cho các chiến dịch Pre-roll.

<div data-zendesk-anchors="connecting-your-twitter-ads-account-to-appsflyer=k%E1%BA%BFt-n%E1%BB%91i-t%C3%A0i-kho%E1%BA%A3n-x-ads-c%E1%BB%A7a-b%E1%BA%A1n-v%E1%BB%9Bi-appsflyer h_01HDJVCRYQESA17XZ83GS81YZ3=k%E1%BA%BFt-n%E1%BB%91i-t%C3%A0i-kho%E1%BA%A3n-x-ads-c%E1%BB%A7a-b%E1%BA%A1n-v%E1%BB%9Bi-appsflyer h_01HDJVBAEZXA0WJ94JYMK84MAX=tr%C6%B0%E1%BB%9Bc-khi-b%E1%BA%AFt-%C4%91%E1%BA%A7u twitter-ads-attribution-setup=thi%E1%BA%BFt-l%E1%BA%ADp-ph%C3%A2n-b%E1%BB%95-qua-x-ads h_01HDJVBAEZ5W3JH1BN7WXJ08P6=thi%E1%BA%BFt-l%E1%BA%ADp-ph%C3%A2n-b%E1%BB%95-qua-x-ads h_01HDJVBAEZSFKRXAKQJP58N550=integration-tab ad-account-connected=%C4%91%C3%A3-k%E1%BA%BFt-n%E1%BB%91i-t%C3%A0i-kho%E1%BA%A3n-qu%E1%BA%A3ng-c%C3%A1o h_01HDJVBAEZD89BSGHQTPR84HSC=%C4%91%C3%A3-k%E1%BA%BFt-n%E1%BB%91i-t%C3%A0i-kho%E1%BA%A3n-qu%E1%BA%A3ng-c%C3%A1o clickthrough-attribution=ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-nh%E1%BA%A5p-qua h_01HDJVBAEZFJWQ6FD4Q4GSPD76=ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-nh%E1%BA%A5p-qua viewthrough-attribution-lookback-window=c%E1%BB%ADa-s%E1%BB%95-xem-l%E1%BA%A1i-ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-xem-qua h_01HDJVBAEZ2H91WBHNSMRQYQ7H=c%E1%BB%ADa-s%E1%BB%95-xem-l%E1%BA%A1i-ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-xem-qua reengagement-settings=c%C3%A0i-%C4%91%E1%BA%B7t-t%C6%B0%C6%A1ng-t%C3%A1c-l%E1%BA%A1i h_01HDJVBAEZZR1W06YH4XJSBKHV=c%C3%A0i-%C4%91%E1%BA%B7t-t%C6%B0%C6%A1ng-t%C3%A1c-l%E1%BA%A1i reengagement-clickthrough-lookback-window=th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-l%C6%B0%E1%BB%A3t-nh%E1%BA%A5p-t%C6%B0%C6%A1ng-t%C3%A1c-l%E1%BA%A1i h_01HDJVBAEZ59ERYD2WQQYK6T37=th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-l%C6%B0%E1%BB%A3t-nh%E1%BA%A5p-t%C6%B0%C6%A1ng-t%C3%A1c-l%E1%BA%A1i reengagement-viewthrough-lookback-window=th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-l%C6%B0%E1%BB%A3t-xem-h%E1%BA%BFt-t%C6%B0%C6%A1ng-t%C3%A1c-l%E1%BA%A1i h_01HDJVBAEZSCK7430NJ8AMQYVY=th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-l%C6%B0%E1%BB%A3t-xem-h%E1%BA%BFt-t%C6%B0%C6%A1ng-t%C3%A1c-l%E1%BA%A1i reengagement-window=th%E1%BB%9Di-gian-t%C6%B0%C6%A1ng-t%C3%A1c-l%E1%BA%A1i h_01HDJVBAEZCMWY5X47FEEFXTBX=th%E1%BB%9Di-gian-t%C6%B0%C6%A1ng-t%C3%A1c-l%E1%BA%A1i inapp-event-postback-settings=c%C3%A0i-%C4%91%E1%BA%B7t-%C4%91%C4%83ng-l%E1%BA%A1i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HDJVBAEZ5ZM9RDXPWTJPPYVA=c%C3%A0i-%C4%91%E1%BA%B7t-%C4%91%C4%83ng-l%E1%BA%A1i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HDJVBAEZATGM580CNC7BCVTN=l%C6%B0u-%C3%BD h_01HDJVBAEZR1Q2SVE9MEQ9EXKP=attribution-link-tab h_01HDJVBAEZ7R7BKFAZYXXBGS5Y=l%C6%B0u-%C3%BD h_01HDJVBAEZYSWN59VNXTDEWX93=cost-tab h_01HDJVBAF0VPBBAEHJPG40HJP8=ad-revenue-tab h_01HDJVBAF0KEVSWJ0EW54AEAWV=permissions-tab ad-network-permissions=quy%E1%BB%81n-truy-c%E1%BA%ADp-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o h_01HDJVBAF0BMSCKF6J9NJ019YJ=quy%E1%BB%81n-truy-c%E1%BA%ADp-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o agency-permissions=c%E1%BA%A5p-quy%E1%BB%81n-cho-%C4%91%E1%BA%A1i-l%C3%BD h_01HDJVBAF0W3ZE7J93CRE8EBRP=c%E1%BA%A5p-quy%E1%BB%81n-cho-%C4%91%E1%BA%A1i-l%C3%BD advanced-twitter-ads-setup-video=video-c%C3%A0i-%C4%91%E1%BA%B7t-x-ads-n%C3%A2ng-cao h_01HDJVBAF0SJ93TNQ8WSFVE91P=video-c%C3%A0i-%C4%91%E1%BA%B7t-x-ads-n%C3%A2ng-cao limitations=%C4%91i%E1%BB%83m-h%E1%BA%A1n-ch%E1%BA%BF h_01HDJVSZSVMX9ARG2B0CHY45X3=%C4%91i%E1%BB%83m-h%E1%BA%A1n-ch%E1%BA%BF" />
