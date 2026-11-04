---
title: Thiết lập tích hợp quảng cáo Meta
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Facebook
    - App Install
    - View-Through
    - integrated partner
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
  created_at: '2013-01-24T20:13:58Z'
  edited_at: '2024-10-12T18:01:25Z'
  id: 207033826
  locale: vi
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/vi/articles/207033826
---
> **Sơ lược:** Tìm hiểu về cách tích hợp quảng cáo Meta với AppsFlyer.

<div id="meta-ads-setup-guide" />

## Hướng dẫn thiết lập quảng cáo Meta

Mất bao lâu để bắt đầu phân bổ quảng cáo ứng dụng thiết bị di động trên quảng cáo Meta của bạn với AppsFlyer?

Nếu bạn đã tích hợp <Anchor target="_blank" href="/marketers/vi/docs/integrate-the-appsflyer-sdk">AppsFlyer SDK vào ứng dụng của mình</Anchor> và đã xác định ứng dụng của bạn trên quảng cáo Meta thì thời gian sẽ chỉ mất chưa đầy một phút!

Bạn không cần thực hiện Đăng nhập Facebook hoặc tích hợp ứng dụng của bạn với SDK của Facebook để phân bổ trên thiết bị di động. Chỉ cần làm theo hướng dẫn [thiết lập từng bước cơ bản](/docs/meta-ads-integration-setup#thiết-lập-phân-bổ-quảng-cáo-meta-cơ-bản) dưới đây. Sau đó, hãy xem [các tùy chọn thiết lập nâng cao](/docs/meta-ads-integration-setup#thiết-lập-phân-bổ-quảng-cáo-meta-nâng-cao) cho quảng cáo Meta.

### ID Ứng dụng Facebook

Để tích hợp quảng cáo Meta với AppsFlyer, trước tiên, hãy tạo <Anchor target="_blank" href="https://developers.facebook.com/docs/apps/register">ID Ứng dụng Facebook</Anchor>, sau đó truy xuất ID đó.

**Để tạo** ID Ứng dụng Facebook:

1. Trên **quảng cáo Meta**, hãy chuyển đến <Anchor target="_blank" href="https://developers.facebook.com/apps">App Dashboard</Anchor> của bạn.
2. Trong phần **Apps**, nhấp vào **Create New App**.
3. Nhập tên cho ứng dụng của bạn và nhập một không gian tên duy nhất. Đảm bảo thêm nền tảng chính xác cho ứng dụng của bạn, nếu không, lượt cài đặt có thể không được phân bổ chính xác.

**Để truy xuất ID Ứng dụng Facebook**:

1. Trên **quảng cáo Meta**, hãy chuyển đến <Anchor target="_blank" href="https://developers.facebook.com/apps">App Dashboard</Anchor> của bạn.
2. Nhấp vào ứng dụng được yêu cầu.
3. Nhấp vào App ID xuất hiện ở trên cùng bên trái của màn hình để sao chép.  
   ![meta-ads-for-developters.jpg](https://files.readme.io/86ef4cdfbb965a362c77527a532af2bb7e7eb2b39b477e4a93a2d2f22e19f377-30354101851793.jpg)

AppsFlyer phân bổ dữ liệu cho mỗi ID Ứng dụng. Có thể sử dụng cùng một ID Ứng dụng Facebook cho [cả ứng dụng Android và iOS](https://developers.facebook.com/docs/app-ads/app-setup/). Lưu ý rằng, đối với phiên bản iOS 14 trở lên, quảng cáo Meta giới hạn số lượng tài khoản quảng cáo ở mức 9 tài khoản cho mỗi ứng dụng.

<div id="optional--configure-recommended-settings" />

<div id="set-the-meta-ads-active-integration" />

<div id="enable-meta-ads-device-level-data" />

<div id="create-and-retreive-facebook-app-id" />

<div id="important" />

<div id="basic-meta-ads-attribution-setup" />

## Thiết lập phân bổ quảng cáo Meta cơ bản

Để bắt đầu phân bổ các chiến dịch quảng cáo Meta với AppsFlyer, hãy làm theo các bước sau:

<Accordion title="Xem">

<Embed title="Thiết lập tích hợp quảng cáo Meta" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/mrwnab4x7r" providerUrl="https://fast.wistia.com" />

</Accordion>

<Accordion title="Đọc">

1. **Để kích hoạt tùy chọn tích hợp với quảng cáo Meta:**
   1. Đi tới ứng dụng của bạn trên [Meta dành cho nhà phát triển](https://developers.facebook.com/apps).
   2. Chọn ứng dụng.  

      ![find-fb-app-id.jpg](https://support.appsflyer.com/hc/article_attachments/25899320112017)
   3. Để sao chép ID ứng dụng của bạn, hãy nhấp vào ID đó ở trên cùng của màn hình. màn.  

      ![meta-ads-copy-app-id.jpg](https://support.appsflyer.com/hc/article_attachments/25899342893585)
   4. Trong AppsFlyer, từ menu bên, chọn **Collaborate** > **Partner Marketplace**
   5. Tìm kiếm và chọn quảng cáo Meta.
   6. Nhấp vào **Set up integration**. Bạn đang được chuyển đến trang thiết lập tích hợp.
   7. Trong tab **Integration** (Tích hợp): Bật Activate Partner (Kích hoạt Đối tác).  
       **Lưu ý:** Nút bật/tắt phải luôn ở trạng thái bật (<Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">activated (được kích hoạt)</Anchor>) trong thời gian bạn làm việc với đối tác<Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">.</Anchor>
   8. Trong phần **Cài đặt chung**:  

      ![meta_ads_general_settings2.png](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)

      * Dán ID ứng dụng của bạn vào **ID ứng dụng Facebook** Trường
      * Dán liên kết giới thiệu cài đặt Để nhận khóa giải mã của bạn từ Meta ads:
   9. Bật hoặc tắt **Chia sẻ dữ liệu nâng cao**, xem [Chia sẻ dữ liệu nâng cao](#advanced_data_sharing) dưới. (Dần dần có sẵn cho tất cả các tài khoản vào tháng Mười Ngày 23 tháng 2024 năm 14
   10. Nhấp vào **Save Integration**.
2. [tùy chọn] **Cấu hình các tùy chọn cài đặt đề xuất:**  

   ![meta_ads_install_attribution.png](https://files.readme.io/82b59d3460ea0487de932b7e49be7de10a8f4eaca151afaca281724f85d0c325-30354145601681.png)

   * Để khớp với cửa sổ xem lại nhấp qua của Quảng cáo meta, đặt thành 7 ngày.  
      Lưu ý rằng: (Lưu ý rằng [có một số trường hợp riêng thì cài đặt mặc định sẽ khác](https://www.facebook.com/business/help/395050428485124?id=428636648170202)).
   * Để khớp với khoảng thời gian xem lại của Meta ads, Đặt nó thành một ngày.
   * Để phân bổ người dùng cài đặt lại ứng dụng trong Cửa sổ Phân bổ lại Bật tùy chọn Reinstall attribution (Phân bổ lượt cài đặt lại).  
      Bạn không cần bật tính năng phân bổ xem qua hoặc định cấu hình các cửa sổ lookback để cài đặt lại phân bổ, Vì nó lấy cấu hình của nó từ phân bổ cài đặt Cài đặt:

Bạn vẫn không thấy kết quả trên AppsFlyer? Tham khảo Khắc phục sự cố khi tích hợp quảng cáo Meta

</Accordion>

<div id="note-1" />

<div id="campaign-attribution-fields-available-via-the-referrer" />

<div id="note" />

<div id="meta-install-referrer" />

<div id="google-play-install-referrer-api" />

<div id="advanced-meta-ads-attribution-setup" />

## Thiết lập phân bổ quảng cáo Meta nâng cao

Với tính năng phân bổ cơ bản đã được thiết lập cho quảng cáo Meta, đã đến lúc bạn nên thiết lập phân bổ nâng cao nhanh.

<Accordion title="Xem">

<Embed title="Thiết lập tích hợp quảng cáo Meta" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/slxtvp2pcs" providerUrl="https://fast.wistia.com" />

</Accordion>

<Accordion title="Đọc">

<div id="userlevel-data" />

<Accordion title="Dữ liệu cấp độ người dùng">

#### Dữ liệu phân bổ bị hạn chế đối với quảng cáo Meta

Có hiệu lực từ ngày 29 tháng 10 năm 2021, chỉ báo cáo tổng hợp Dữ liệu có sẵn cho nhà quảng cáo  Điều này có nghĩa là cả hai Dữ liệu phân bổ xem qua và nhấp qua sẽ xuất hiện như "bị hạn chế" trong báo cáo dữ liệu thô. Các lĩnh vực khác Các trường khác liên quan đến kênh truyền thông không được điền. Xem: <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions#hạn-chế-dữ-liệu-thô">Hạn chế nội dung dữ liệu thô</Anchor>.

Điều này áp dụng cho tất cả các nhà quảng cáo, hệ điều hành và MMP. Điều này liên quan đến dữ liệu cấp thiết bị cho tất cả những người dùng hệ điều hành iOS và Android, bất kể trạng thái chấp thuận ATT hoặc việc cá nhân hóa quảng cáo.

AppsFlyer tiếp tục nhận dữ liệu cấp thiết bị từ quảng cáo Meta, có nghĩa là khả năng phân bổ và báo cáo của chúng ta (bao gồm phân bổ đa điểm chạm, LTV, ROI, nhóm người, báo cáo giữ chân người dùng, bảo vệ chống gian lận, Đối tượng và các dịch vụ khác) vẫn không thay đổi. Xem phần <Anchor target="_blank" href="/marketers/vi/docs/aggregated-and-analytics-reporting-overview">các công cụ báo cáo hợp nhất và phân tích</Anchor>.

<div id="getting-userlevel-data-for-android-installs" />

#### Nhận dữ liệu cấp người dùng cho lượt cài đặt Android và sự kiện trong ứng dụng

**API Liên kết giới thiệu Cài đặt Google Play**

Mặc dù dữ liệu cấp người dùng bị hạn chế, nhưng quảng cáo Meta chia sẻ siêu dữ liệu chiến dịch với các nhà quảng cáo cho quảng cáo ứng dụng Android chuyển hướng người dùng đến Cửa hàng Google Play. Trong trường hợp này, các trường phân bổ có sẵn cho các nhà quảng cáo trong API Liên kết giới thiệu cài đặt Google Play, các trường này phải được <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">tích hợp vào ứng dụng của bạn.</Anchor> Các trường được cung cấp thông qua API liên kết giới thiệu cài đặt Google Play sẽ điền báo cáo dữ liệu thô của AppsFlyer bằng loại đối sánh `gp_referrer`. Tính năng này chỉ khả dụng sau khi khóa giải mã được gửi và lượt cài đặt được phân bổ cho quảng cáo Meta. Điều này cho phép AppsFlyer phân bổ người dùng không có ID quảng cáo (đã bật LAT).

**Liên kết giới thiệu cài đặt Meta**

Đối với API iên kết giới thiệu cài đặt Google Play: Meta cài đặt liên kết giới thiệu cho phép AppsFlyer nhận Siêu dữ liệu chiến dịch quảng cáo từ bộ nhớ cục bộ của thiết bị. Dữ liệu này được sử dụng để đo lường việc phân bổ. Các sự khác biệt chính giữa Cài đặt Google Play Referrer API và liên kết giới thiệu cài đặt Meta là:

* Liên kết giới thiệu cài đặt Meta có thể bao gồm lượt hiển thị và nhấp vào dữ liệu, trong khi Cài đặt Google Play API liên kết giới thiệu được giới hạn ở dữ liệu nhấp chuột
* Liên kết giới thiệu cài đặt Meta có khả năng bao gồm dữ liệu từ nhiều phiên, trong khi Google Play Install Referrer API bị giới hạn ở dữ liệu chỉ từ phiên cuối cùng (thiết bị phải cài đặt ứng dụng trong cùng phiên với nhấp chuột đã xảy ra)

Do đó, bạn có thể thấy sự gia tăng của Meta-attributed Báo cáo dữ liệu thô về lượt cài đặt lại Khi cài đặt là Đối với API iên kết giới thiệu cài đặt Google Play: hoặc liên kết giới thiệu cài đặt Meta, dữ liệu có sẵn trong báo cáo dữ liệu thô. Các trường có thể có sẵn để phân bổ thông qua liên kết giới thiệu cài đặt Meta điền vào AppsFlyer báo cáo dữ liệu thô với match\_type phân bổ từ ứng dụng Facebook và `ig_referrer` để phân bổ từ ứng dụng Instagram. Tính năng này chỉ khả dụng một lần Khóa giải mã được gửi và cài đặt là được quy cho quảng cáo Meta. Đối với liên kết giới thiệu cài đặt Meta: Khóa giải mã là cùng một khóa Đối với API iên kết giới thiệu cài đặt Google Play: và không cần cung cấp cho AppsFlyer một giây Thời gian.

**Các trường phân bổ chiến dịch được cung cấp qua liên kết giới thiệu:**

* ID Quảng cáo
* Tên quảng cáo
* ID Bộ quảng cáo
* Tên bộ quảng cáo
* ID Chiến dịch
* Tên chiến dịch
* ID tài khoản
* Kênh

> 📘 **Lưu ý**
>
> * **Đối với API iên kết giới thiệu cài đặt Google Play:**
>   * SDK AppsFlyer phải là **V5.4.0+** để dữ liệu liên kết giới thiệu được chuyển Đúng. Dữ liệu liên kết giới thiệu được ưu tiên trên dữ liệu do API cung cấp và không Hạn chế Giải pháp này áp dụng Phân bổ lượt nhấp qua Phân bổ lượt xem qua
>   * Trường Channel được xác định bởi giá trị kênh nhận được từ API Liên kết giới thiệu của Google Play (do Meta gửi đến Google Play). Nếu nhận được một chuỗi rỗng, trường Channel sẽ hiển thị "Không có".
> * **Đối với liên kết giới thiệu cài đặt Meta:** Tham khảo đến <Anchor target="_blank" href="/marketers/vi/docs/bulletin-get-meta-ads-attribution-in-raw-data-reports-with-the-meta-install-refe">Điều kiện tiên quyết và hành động cần thiết</Anchor> được mô tả trong bản tin.

<div id="meta-install-referrerfaq" />

#### Liên kết giới thiệu cài đặt Meta—FAQ

**Liên kết giới thiệu cài đặt Meta được áp dụng cho việc phân bổ trong trường hợp nào?**

* Đối với phân bổ lượt cài đặt:
  * Phân bổ lượt nhấp chuột, cho tất cả các chiến dịch
  * Phân bổ xem qua được hỗ trợ cho tất cả các Chiến dịch ứng dụng Advantage+ và Chiến dịch quảng cáo ứng dụng thủ công với phạm vi rộng Nhắm mục tiêu (ví dụ: trong đó độ tuổi và giới tính được đặt thành Mặc định).
* Khả năng tương thích: Cửa hàng Google Play và không phải của Google Cửa hàng ứng dụng Play Android
* Các trường hợp loại trừ: Điều này không bao gồm chuyển hướng chiến dịch đến trang đích

**"Nhắm mục tiêu rộng" được sử dụng với mục đích gì trong quảng cáo Meta?**

Cần nhắm mục tiêu rộng để nhận dữ liệu cài đặt lượt xem hết. Cài đặt dữ liệu. Cấu hình chiến dịch được hỗ trợ Bao gồm

* Độ tuổi: Cài đặt mặc định được áp dụng là (18-65+)
* Giới tính: Cài đặt mặc định được áp dụng là (Tất cả các giới tính)
* Vị trí: Các nhóm quốc gia và quốc gia được hỗ trợ. **Lưu ý:** Để biết thêm các vị trí được nhắm mục tiêu (chẳng hạn như thành phố hoặc mã zip) chiến dịch sử dụng Nhắm mục tiêu bao gồm với những điều này cần được thiết lập Đặt là tùy thích.
* Nhắm mục tiêu chi tiết: Phân khúc sở thích, hành vi, và nhân khẩu học nâng cao được đặt là thoải mái.
* Đối tượng tùy chỉnh: Đặt là tùy thích.
* Đối với "thoải mái", "Nhắm mục tiêu chi tiết lợi thế" Hộp cho các chiến dịch quảng cáo phải được chọn:  

  <Image alt="" src="https://support.appsflyer.com/hc/article_attachments/22950622532497" width="569px" />

<div id="encrypted-data-from-google-play-referrer-api-or-meta-install-referrer" />

#### Dữ liệu được mã hóa từ API liên kết giới thiệu Google Play hoặc liên kết giới thiệu cài đặt Meta

Dữ liệu từ API Liên kết giới thiệu Google Play hoặc liên kết giới thiệu cài đặt Meta đều được Meta mã hóa. Dữ liệu này có thể được giải mã sử dụng khóa có sẵn cho bạn trong tài khoản nhà phát triển Meta. Bạn phải cung cấp cho chúng tôi khóa giải mã được mô tả trong hàng những hành động cần thiết. Chỉ cần gửi khóa giải mã một lần cho mỗi ứng dụng.

Lưu ý rằng nếu bạn không cung cấp hoặc đã xóa mã khóa, thì sẽ có một số trường hợp trong đó quảng cáo Meta vẫn được phân bổ cho lượt cài đặt dựa trên liên kết giới thiệu - ngay cả khi không có trường phân bổ chiến dịch (được đề cập trong danh sách ở trên). Trường hợp này xảy ra khi:

* Quảng cáo Meta không yêu cầu xác nhận quyền sở lữu lượt cài đặt
* Dữ liệu nhận được từ API Liên kết giới thiệu cài đặt của Google Play đã được nhận nhưng chưa được giải mã
* Và đây là lượt nhấp cuối cùng

**Để nhận khóa giải mã từ Meta:**

1. Hãy đăng nhập vào cổng thông tin nhà phát triển Meta của bạn.
2. Điều hướng đến **My Apps** ở góc trên bên phải.
3. Chọn ứng dụng mà bạn muốn truy cập khóa giải mã của mình.
4. Điều hướng đến mục **Settings** > **Basic** ở bên trái của trang.  

   [![](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)
5. Cuộn xuống phần Android và bạn sẽ xem khóa giải mã của bạn có nhãn Cài đặt liên kết giới thiệu khóa giải mã bên dưới trường Tên gói. Lưu ý: Đây là cùng một phần mà bạn đã định cấu hình tên gói của bạn và Cửa hàng Google Play.

**Để thiết lập khóa giải mã trong AppsFlyer:**

1. [Bắt buộc] Xác minh rằng AppsFlyer SDK V5.4+ là được áp dụng trong ứng dụng của bạn. Không phụ thuộc vào các phiên bản cũ hơn.
2. Trong AppsFlyer, từ menu bên, chọn **Collaborate** > **Active Integrations**.
3. Chọn **Meta ads**.  
    [![meta_ads_general_settings2.png](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)
4. Trong tab **Integration (Tích hợp):** Đặt khóa giải mã liên kết giới thiệu cài đặt Thao tác này chỉ cần thực hiện một lần cho mỗi ứng dụng.
5. Nhấp vào **Save integration**.

</Accordion>

<div id="cost-clicks-and-impressions" />

<Accordion title="Chi phí, lượt nhấp và lượt hiển thị">

[![meta_cost_tab.png](https://files.readme.io/5c840dbce9c019a8655e8b7b54b8d8e29f3128a8e7115065d0f4083b703b80c0-30354101895185.png)](https://files.readme.io/5c840dbce9c019a8655e8b7b54b8d8e29f3128a8e7115065d0f4083b703b80c0-30354101895185.png)  

Tích hợp này cung cấp dữ liệu tổng hợp về chi phí, nhấp chuột và hiển thị cho các chiến dịch, nhóm quảng cáo của bạn, quảng cáo và địa lý/quốc gia. Xem <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">Bảng tích hợp chi phí mạng quảng cáo</Anchor> để biết đầy đủ thông tin chi tiết về thứ nguyên, chỉ số được hỗ trợ, và các tính năng.

**Lưu ý:** Dữ liệu về lượt nhấp và lượt hiển thị. được bao gồm trong tích hợp. Tuy nhiên: Dữ liệu chi phí yêu cầu đăng ký ROI360.

**Để kích hoạt API chi phí**:

1. Đảm bảo bạn đã đăng nhập vào người dùng Meta ads tài khoản, được bật để xử lý tài khoản chiến dịch trên Meta ads. Người dùng đăng nhập phải: có quyền chạy tất cả các chiến dịch trong Meta Trình quản lý kinh doanh.
2. Truy cập tab **Cost**.
3. Bật tùy chọn **Get Cost, Clicks and Impressions Data**.
4. Nhấp vào nút **f login**. Mày có thể đăng nhập bằng quản trị viên hoặc doanh nghiệp quảng cáo Meta Tài khoản
5. Khi được nhắc, hãy cho phép AppsFlyer truy cập vào Dữ liệu chiến dịch quảng cáo meta.  
    **Lưu ý**: Trong lần đồng bộ hóa dữ liệu đầu tiên sau khi tích hợp, cũng như các đồng bộ hóa tiếp theo, AppsFlyer nhận dữ liệu chi phí quảng cáo Meta cho tối đa đến 7 ngày gần nhất hồi tố.

Đọc thêm về cách quảng cáo Meta xác định số lần nhấp và lượt xem.

**Để xóa tài khoản quảng cáo Meta đã kết nối: IN Trong cột actions, di chuột qua một tài khoản và nhấp vào Delete connection. Xóa kết nối**

<div id="notes" />

> 📘 **Lưu ý**
>
> * Nếu bạn đã đăng nhập vào quảng cáo Meta, Khi bạn nhấp vào biểu tượng **Đăng nhập f** , cửa sổ ngay lập tức mở ra và Đóng. Đây là trạng thái bình thường.
> * Nếu bạn có nhiều người dùng có quyền đối với Meta ads, phương pháp hay nhất là thực hiện đăng nhập cho tất cả chúng, để <Anchor target="_blank" href="/marketers/vi/docs/meta-ads-faq#why-doesnt-cost-data-include-data-from-all-campaigns">Tránh lấy một phần dữ liệu</Anchor>.

<div id="cost-data-sync-status" />

#### Trạng thái đồng bộ dữ liệu chi phí

<Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Xem trạng thái API chi phí của bạn</Anchor> và lần cuối cùng AppsFlyer lấy dữ liệu chi phí so khớp vào bảng điều khiển trạng thái tích hợp chi phí (và doanh thu quảng cáo) hoặc bảng điều khiển mạng quảng cáo riêng.

Bạn có thể đồng bộ vài tài khoản để lấy dữ liệu chi phí. Đối với mỗi tài khoản được đồng bộ hóa, AppsFlyer hiển thị trạng thái tích hợp chi phí và lần cuối cùng AppsFlyer quản lý để lấy dữ liệu chi phí phù hợp.

Tìm hiểu thêm về cách làm phong phú thêm dữ liệu của bạn với <Anchor target="_blank" href="/marketers/vi/docs/meta-ads-faq#câu-hỏi-thường-gặp-về-chi-phí-meta-ads">dữ liệu chi phí, số lượt truy cập và lượt hiển thị</Anchor>.

</Accordion>

<div id="inapp-event-mapping" />

<Accordion title="Ánh xạ sự kiện trong ứng dụng">

[![meta_iae_postbacks.png](https://files.readme.io/8f2fd671a067684738964d245a9e80873bbb28f33a55c61ee0cb00a32ac9815e-30354145614865.png)](https://files.readme.io/8f2fd671a067684738964d245a9e80873bbb28f33a55c61ee0cb00a32ac9815e-30354145614865.png)

**Để ánh xạ các sự kiện trong ứng dụng:**

1. Bật tùy chọn **In-App Event Postbacks.**  
    Khi bật ánh xạ sự kiện trong ứng dụng quảng cáo meta Đối với ứng dụng **lần đầu tiên**, **af\_app\_open** là tự động được ánh xạ tới **fb\_mobile\_activate\_app**.
2. Điền những thông số dưới đây: 

| Tên thông số | Mô tả |
| --- | --- |
| **AppsFlyer event** | Nhập tên của sự kiện. nhận được bởi AppsFlyer hoặc từ SDK được tích hợp vào ứng dụng của bạn hoặc từ máy chủ đến máy chủ events<br />**Mẹo**: Không Xem sự kiện bạn đang tìm kiếm Đối với:<ul><li>Đảm bảo kích hoạt Sự kiện trên thiết bị với cài đặt phi hữu cơ và kiểm tra lại.</li><li>Nhập nó vào AppsFlyer event Nhấp vào Create custom Đọc thêm về <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#sự-kiện-tùy-chỉnh">ánh xạ sự kiện tùy chỉnh.</Anchor></li></ul> |
| **mapped to partner event** | Tên hoặc ID duy nhất của Mỗi sự kiện, như được định nghĩa trên Quảng cáo Meta: Có thể lập bản đồ Cấu hình SRN<ul><li>**Trường văn bản:** Nhận tương ứng ID sự kiện từ quảng cáo Meta</li><li>**Hộp thả xuống:** Chọn phù hợp nhất pre-defined AppsFlyer Sự kiện</li><li>**Nguyên trạng**: Gửi sự kiện dưới dạng chúng là, không có ánh xạ tên.</li></ul> |
| **for users from** | Chọn tùy chọn gửi cho sự kiện:<ul><li>**Chỉ đối tác này**: chỉ gửi đăng lại khi sự kiện này được phân bổ cho quảng cáo Meta.</li><li>**Tất cả các kênh truyền thông, kể cả kênh tự nhiên**: gửi đăng lại cho các sự kiện được phân bổ cho bất kỳ đối tác và sự kiện tự nhiên nào.</li></ul> |
| **including** | <ul><li>**No data (default)**: Chỉ gửi chính sự kiện không có giá trị sự kiện.</li><li>**Values and revenue**: gửi tất cả các thông số sự kiện, **including** Giá trị doanh thu (nếu tồn tại trong sự kiện).</li><li>**Values without revenue**: Gửi tất cả các tham số **Loại trừ** giá trị doanh thu.</li></ul> |

3. Để thêm SDK Sự kiện Máy chủ đến Máy chủ. Trong danh sách, hãy nhấp vào **Thêm sự kiện**.

**Hạn chế về tên sự kiện:**

* Giới hạn độ dài của tên sự kiện: 2-40 ký tự
* Không được phép sử dụng các ký tự sau đây:
  * Dấu hai chấm (:)
  * Dấu chấm (.)
  * Bộ ký tự không phải tiếng La tinh (tiếng Anh): Như Ngày 12/1/2020, Meta Ads từ chối Chữ Hán. AppsFlyer thì không đã thử nghiệm các bộ ký tự khác và bạn nên chỉ sử dụng những thứ này sau khi xác minh với Meta quảng cáo nếu chúng hỗ trợ các bộ ký tự này trong postbacks.
* Tên sự kiện có phân biệt chữ hoa và chữ thường. Để tránh sự khác biệt, Hãy chắc chắn rằng bạn sử dụng đúng trường hợp trong trường hợp Tên cho tất cả các nguồn phương tiện và phiên bản ứng dụng.

<div id="use-deep-links-in-meta-ads-campaigns" />

<div id="advanced_matching_data_sharing" />

<div id="see-also" />

<div id="note-3" />

<div id="whatsapp-retargeting-campaign-attribution" />

<div id="note-2" />

> 📘 **Lưu ý**
>
> * Bạn có thể gửi <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">Đăng lại doanh thu quảng cáo</Anchor> đến Meta Ads để họ có thể tối ưu hóa chiến dịch Sử dụng dữ liệu doanh thu quảng cáo:
>   * **Tên sự kiện:** af\_ad\_revenue
>   * **Đã được ánh xạ tới:** fb\_mobile\_purchase
> * Tìm hiểu thêm về Ánh xạ sự kiện trong ứng dụng của quảng cáo Meta

</Accordion>

<div id="retargeting-attribution" />

<Accordion title="Phân bổ nhắm lại mục tiêu">

Phân bổ nhắm mục tiêu lại AppsFlyer cho quảng cáo Meta cho phép Nhà quảng cáo phân bổ mức độ tương tác của người dùng hiện tại với quảng cáo trên Facebook và đo lường chất lượng của người dùng, tương tác bài đăng, sử dụng báo cáo AppsFlyer. Nó chỉ nên được sử dụng nếu bạn đang tích cực chạy các chiến dịch nhắm mục tiêu đến người dùng Facebook của riêng bạn.

1. <Anchor target="_blank" href="/marketers/vi/docs/app-settings#reengagement-attribution">Bật tùy chọn retargeting trên trang App Settings</Anchor> .
2. Trên trang đối tác quảng cáo Meta, hãy bật Phân bổ thu hút lại
3. Đặt Thời gian xem lại lượt nhấp tương tác lại  
    Cửa sổ nhìn lại tương tác lại là khoảng thời gian thời gian, bắt đầu từ lần nhấp vào quảng cáo, trong thời gian đó Ứng dụng phải được khởi chạy để nhấp chuột được ghi nhận là tái đính hôn.  
    Chọn đơn vị cửa sổ xem lại (giờ hoặc ngày), và đặt thanh trượt thành giá trị mong muốn.  

   ![re-engagement_attribution_toggle.png](https://files.readme.io/86e0bb7d4dfa8e55720ed67d1ff8ea34f0e71df9df12382996bb7ea8817da4ba-30354101904785.png)
4. Bật tính năng **Phân bổ lượt xem hết tương tác lại**.
5. Đặt thanh trượt **Khoảng thời gian xem lại lượt xem hết tương tác lại** về giá trị mong muốn (tối đa 24 giờ). Đó là khoảng thời gian bắt đầu từ lúc hiển thị quảng cáo, trong đó ứng dụng phải được khởi chạy để lượt hiển thị được ghi nhận như một lượt tương tác lại.

   ![re-engagement_view-through_toggle.png](https://support.appsflyer.com/hc/article_attachments/13880480985489)
6. Thiết lập **Khoảng thời gian tương tác lại**.  
    Đây là khoảng thời gian diễn ra sự kiện trong ứng dụng của người dùng Tất cả các sự kiện trong ứng dụng được phân bổ cho nguồn truyền thông nhắm mục tiêu lại làm nguồn chính.  
    Bạn có thể đặt giá trị theo ngày (1-90), giờ (tăng đến 23), hoặc thậm chí cả đời. Thời gian mặc định là 30 ngày.  

   ![re-engagement_window.png](https://files.readme.io/6f589562cd6248697ffa8d5ebb4a72e2fdad118df6abf517e43b4fa23c3332ec-30354101914385.png)

Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide">Phân bổ nhắm mục tiêu lại AppsFlyer</Anchor>.

Tìm hiểu thêm về Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns#liên-kết-sâu-với-srn">liên kết sâu người dùng từ SRN chẳng hạn như quảng cáo Meta</Anchor>.

</Accordion>

<div id="advanced_data_sharing" />

<Accordion title="Chia sẻ dữ liệu nâng cao">

Khi **Chia sẻ dữ liệu nâng cao** được quay bật, Meta nhận postback và sự kiện ở cấp thiết bị giá trị nhận dạng cho tất cả các thiết bị, bao gồm cả các thiết bị chưa cung cấp ID quảng cáo (IDFA) của họ. Hơn nữa, khi **Chia sẻ dữ liệu nâng cao** được bật, những sự kiện này có thể do AppsFlyer quy cho. Khi tắt, chỉ đăng lại và sự kiện từ thiết bị với IDFA được gửi và phân bổ.

Phương pháp này sẽ hoạt động để chọn không tham gia một lần và kép Thiết bị: Các sự kiện sẽ được giới hạn ở lần nhấp cuối cùng Phân bổ, với khoảng thời gian phân bổ tối đa là 24 - 144 giờ

Lưu ý: Dần dần có sẵn cho tất cả các tài khoản trước ngày 14 tháng 10 năm 2024

</Accordion>

<div id="comply-with-california-consumer-privacy-act-ccpa" />

<Accordion title="Tuân thủ Đạo luật về Quyền riêng tư của Người tiêu dùng California (CCPA)">

Việc tuân thủ các quy định về quyền riêng tư của CCPA sẽ giới hạn dữ liệu đến từ người dùng quảng cáo Meta có trụ sở tại California, USA.

**Để cho phép tuân thủ CCPA:** Bật **Giới hạn việc quảng cáo Meta sử dụng thông tin cá nhân của người dùng (CCPA)** Trong tab Integration (Tích hợp):

Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/send-opendsr-api-requests">Luật bảo vệ dữ liệu</Anchor>.

</Accordion>

<div id="ad-revenue-recording" />

<Accordion title="Ghi nhận doanh thu quảng cáo">

![meta_ads_ad_revenue.png](https://files.readme.io/5c27f2adf0e4515a7ad0efac4776eb296874273e2af71e14c9be8bd65a983757-30354101917201.png)

Nếu ứng dụng của bạn sử dụng Doanh thu quảng cáo trên Meta Audience Network Để kiếm tiền từ quảng cáo, bạn có thể ghi lại doanh thu của mình từ quảng cáo Meta trên AppsFlyer. Điều này, có hoặc không có Dữ liệu doanh thu mua hàng trong ứng dụng cung cấp cho bạn **Bức tranh toàn cảnh về doanh thu của người dùng**.

<div id="record-meta-audience-network-ad-revenue" />

#### Ghi nhận doanh thu quảng cáo từ Mạng đối tượng Meta

1. Chuyển đến tab **Doanh thu Quảng cáo**. Bật tùy chọn Nhận dữ liệu doanh thu quảng cáo.
2. Chọn loại dữ liệu tổng hợp về doanh thu quảng cáo Bạn muốn nhận: **Doanh thu được phân bổ**: Doanh thu kiếm tiền tổng hợp:
   * **Doanh thu được phân bổ**: Là doanh thu dựa trên nguồn thu hút người dùng. Nguồn  
      Đặt **Nguồn sự kiện**, là sự kiện đại diện cho Mô hình doanh thu quảng cáo tốt nhất có thể cách. Ví dụ: nếu doanh thu của bạn là Dựa trên số lần hiển thị, nó được khuyến khích để gửi cho AppsFlyer một sự kiện ad\_viewed. Sự kiện tốt nhất có thể được định cấu hình cho mỗi nền tảng kiếm tiền riêng biệt. Tuy nhiên, cũng có thể sử dụng sự kiện. Sự kiện IN Trường hợp này, doanh thu quảng cáo được quy cho Mọi ứng dụng đang mở đều do người dùng thực hiện.
   * **Doanh thu kiếm tiền tổng hợp**: Doanh thu dựa trên nguồn quảng cáo.
3. **Sự kiện Doanh thu Quảng cáo** được hiển thị. Đây là trường chỉ đọc trình bày quảng cáo mới Sự kiện doanh thu có tên [Sự kiện nguồn]\_monetized (ví dụ: Ad\_Watched\_Monetized như được hiển thị above). Sự kiện doanh thu quảng cáo được trình bày trong bảng điều khiển như một sự kiện bổ sung.
4. Bấm **Kết nối với quảng cáo Meta** đến kích hoạt bộ sưu tập Meta Audience Network Doanh thu quảng cáo trên quảng cáo Meta. Đăng nhập bằng Meta của bạn thông tin đăng nhập quảng cáo để ủy quyền cho Meta Audience Network Doanh thu quảng cáo
5. Nhập Nhập **ID Ứng dụng Mạng Đối tượng ([ID Ứng dụng Facebook](/docs/meta-ads-integration-setup#id-ứng-dụng-facebook)).** Nhận thông tin này từ Mạng Đối tượng Meta.
   * Nhận ID Ứng dụng Facebook
   * Sao chép ID vào **ID ứng dụng Audience Network** trường trong AppsFlyer.
6. Nhấp vào **Save ad revenue**.

</Accordion>

<div id="permissions" />

<Accordion title="Quyền">

Cho phép quảng cáo Meta thực hiện các hành động khác nhau và Truy cập dữ liệu của bạn theo các quyền có sẵn.

Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#permissions-tab">Cấp quyền cho Đối tác tích hợp</Anchor>.

</Accordion>

</Accordion>

<div id="aggregate-event-measurement-aem-for-ios" />

## Đo lường Sự kiện Hợp nhất (AEM) cho iOS

<Anchor target="_blank" href="/marketers/vi/docs/meta-ads-aggregate-event-measurement-aem-for-ios">AppsFlyer hỗ trợ giải pháp Đo lường Sự kiện Hợp nhất (AEM) của quảng cáo Meta. Giải pháp này giúp tối ưu hóa chuyển đổi iOS và sự kiện trong ứng dụng, đồng thời phân bổ lượt tái tương tác iOS trên quảng cáo Meta.</Anchor>

<div id="aem-attribution-is-not-working" />

<div id="meta-ads-integration-troubleshooting" />

## Khắc phục sự cố khi tích hợp quảng cáo Meta

Nếu bạn đã hoàn thành giải pháp tích hợp cơ bản và vẫn không thấy kết quả từ quảng cáo Meta trên bảng điều khiển của AppsFlyer, trước tiên hãy xác minh rằng bạn có lượt cài đặt mới từ quảng cáo Meta kể từ thời điểm tích hợp.

Nếu có, vui lòng tham khảo các lý do chính dưới đây để khắc phục sự cố này:

<div id="no-idfa-collection" />

<Accordion title="Không thu thập IDFA">

Như đã nêu trong Hướng dẫn Tích hợp SDK - iOS, bạn phải thêm AdSupport.framework vào dự án của mình để quá trình thu thập IDFA diễn ra. Kiểm tra báo cáo Dữ liệu Thô Cài đặt để xem cột IDFA có thực sự trống hay không. Bạn nên cho phép ứng dụng của mình thu thập IDFA trong trường hợp ứng dụng iOS và GAID trong trường hợp ứng dụng Android.  
Bắt đầu từ iOS 14.5, bạn sẽ phải hiển thị lời nhắc về ATT của Apple và phải được sự đồng ý của người dùng trước khi có thể thu thập IDFA.

**Lưu ý:** Phân bổ SKAdNetwork không bị ảnh hưởng bởi tính khả dụng của IDFA. Tuy nhiên, hãy đảm bảo rằng bạn bật chế độ chuyển đổi Chiến dịch iOS 14 trong quảng cáo Meta trong khi thiết lập các chiến dịch iOS 14.

</Accordion>

<div id="wrong-facebook-app-id" />

<Accordion title="ID Ứng dụng Facebook không chính xác">

ID Ứng dụng Facebook đã được cấu hình không chính xác trong AppsFlyer.  
Xác minh rằng ID ứng dụng là chính xác và khớp với giá trị trong bảng điều khiển quảng cáo Meta.  

Lưu ý - bạn cũng có thể sử dụng <Anchor target="_blank" href="https://developers.facebook.com/tools/explorer/?method=GET&path=&version=v6.0">API Biểu đồ của Facebook</Anchor> để xác thực ID Ứng dụng Facebook của mình.

</Accordion>

<div id="app-status-on-meta-ads" />

<Accordion title="Trạng thái ứng dụng trên quảng cáo Meta">

Ứng dụng phải được xác định trên quảng cáo Meta là **Live** thay vì **In development** để phân bổ hoạt động.

![fb-app-status.png](https://files.readme.io/b982355eb0d3d858988866673d3f9ee4f081c43042221d11ebfb93afe05c36a4-30354101922577.png)

</Accordion>

<div id="wrong-type-of-meta-ads-campaign" />

<Accordion title="Loại chiến dịch quảng cáo Meta không chính xác">

Đảm bảo chiến dịch quảng cáo Meta là **Mobile app install ads** hoặc **Mobile App Engagement**. Đối với các mục tiêu chiến dịch khác (ví dụ: Nhấp vào Liên kết cho các trang đích), để tính toán lượt cài đặt trên thiết bị di động, nhà quảng cáo phải chọn tùy chọn App Event recording khi xác định chiến dịch quảng cáo Meta.

</Accordion>

<div id="meta-ads-app-install" />

<Accordion title="Cài đặt ứng dụng quảng cáo Meta">

Khi thiết lập chiến dịch cài đặt ứng dụng quảng cáo Meta, bạn có thể chọn ứng dụng từ danh sách thả xuống hoặc dán URL cửa hàng đầy đủ vào ứng dụng. Mặc dù bạn có thể sử dụng cả hai phương thức trên quảng cáo Meta, nhưng phương thức thứ hai không phân bổ được trên AppsFlyer.

Thiết lập chính xác - phân bổ có hiệu quả.

<Image alt="fb-app-install.png" src="https://files.readme.io/5cb735144128035d752281f7d94e2015478c62049a2e96fc5a42400513f7fad3-30354101926033.png" width="496px" />

Thiết lập không đúng cách - phân bổ không thành công.

![fb-app-incorrect_setup.png](https://files.readme.io/77d508b62d5445cac071262cb35e4a89a6dfa5be439325254c0b8f6c5f51606c-30354145644561.png)

</Accordion>

## Cập nhật quảng cáo Meta

> 🚧 **Quan trọng!**
>
> Có hiệu lực từ ngày 29 tháng 10 năm 2021, chỉ báo cáo tổng hợp từ quảng cáo Meta mới được cung cấp cho các nhà quảng cáo. Điều này bao gồm cả các cài đặt và sự kiện trong ứng dụng. Thay đổi này áp dụng cho tất cả các nhà quảng cáo, hệ điều hành và MMP. Điều này liên quan đến dữ liệu cấp thiết bị cho tất cả những người dùng hệ điều hành iOS và Android, bất kể trạng thái chấp thuận ATT hoặc việc cá nhân hóa quảng cáo.
> Dữ liệu thô cho các cài đặt và sự kiện trong ứng dụng được cung cấp trước thời điểm thay đổi (ngày 29 tháng 10 năm 2021) vẫn khả dụng.
> Lưu ý rằng dữ liệu cấp người dùng có thể được nhận qua Liên kết Giới thiệu Cài đặt Google.
> Hãy xem <Anchor target="_blank" href="/marketers/vi/docs/bulletin-action-required-get-meta-ads-raw-data-using-google-install-referrer">bản tin</Anchor> để biết thêm thông tin chi tiết.

<div id="ios-14-updates-relating-to-meta-ads" />

### Các bản cập nhật iOS 14 liên quan đến quảng cáo Meta

AppsFlyer xác nhận rằng tích hợp MMP của chúng tôi với quảng cáo Meta luôn triển khai cờ báo *Đã bật Theo dõi Nhà quảng cáo*. Có nghĩa là, bạn không cần thực hiện bất kỳ hành động nào trong AppsFlyer. Thông tin này được cung cấp theo danh sách kiểm tra hướng dẫn ứng dụng quảng cáo Meta dành cho iOS 14 vào tháng 2 năm 2021.

<div id="see-also-1" />

> 📄 **Xem thêm**
>
> * Để biết những điều cần lưu ý liên quan đến iOS 14, hãy xem phần <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-interoperation-with-meta-ads">tương tác của SKAN trên quảng cáo Meta</Anchor>
> * <Anchor target="_blank" href="/marketers/vi/docs/configuring-meta-campaign-management-partners">Cấu hình đối tác quản lý chiến dịch Meta</Anchor> (<Anchor target="_blank" href="/marketers/vi/docs/bidalgo-meta-campaign-management-partner-configuration">Bidalgo</Anchor> / <Anchor target="_blank" href="/marketers/vi/docs/kenshoo-meta-campaign-management-partner-configuration">Kenshoo</Anchor> / <Anchor target="_blank" href="/marketers/vi/docs/adquant-meta-campaign-management-partner-configuration">Adquant</Anchor> / <Anchor target="_blank" href="/marketers/vi/docs/webpals-mobile-meta-campaign-management-partner-configuration">Webpals</Anchor>)

<div data-zendesk-anchors="facebook-ads-setup-guide=h%C6%B0%E1%BB%9Bng-d%E1%BA%ABn-thi%E1%BA%BFt-l%E1%BA%ADp-qu%E1%BA%A3ng-c%C3%A1o-meta 01H7YJVNMSZ4WG4HWBZF648HZN=h%C6%B0%E1%BB%9Bng-d%E1%BA%ABn-thi%E1%BA%BFt-l%E1%BA%ADp-qu%E1%BA%A3ng-c%C3%A1o-meta facebook-app-id=id-%E1%BB%A9ng-d%E1%BB%A5ng-facebook 01H7YJVNMTP8PP2S88Q70E082G=id-%E1%BB%A9ng-d%E1%BB%A5ng-facebook basic-facebook-attribution-setup=thi%E1%BA%BFt-l%E1%BA%ADp-ph%C3%A2n-b%E1%BB%95-qu%E1%BA%A3ng-c%C3%A1o-meta-c%C6%A1-b%E1%BA%A3n 01H7YJVNMTFW076FAJZGJWT4R9=thi%E1%BA%BFt-l%E1%BA%ADp-ph%C3%A2n-b%E1%BB%95-qu%E1%BA%A3ng-c%C3%A1o-meta-c%C6%A1-b%E1%BA%A3n advanced-facebook-attribution-setup=thi%E1%BA%BFt-l%E1%BA%ADp-ph%C3%A2n-b%E1%BB%95-qu%E1%BA%A3ng-c%C3%A1o-meta-n%C3%A2ng-cao 01H7YJVNMTHF800PD5CEWPFS49=thi%E1%BA%BFt-l%E1%BA%ADp-ph%C3%A2n-b%E1%BB%95-qu%E1%BA%A3ng-c%C3%A1o-meta-n%C3%A2ng-cao 01H7YJVNMTP2CA09QPEQ4DV37C=userlevel-data meta-ads-restricted-attribution-data=d%E1%BB%AF-li%E1%BB%87u-ph%C3%A2n-b%E1%BB%95-b%E1%BB%8B-h%E1%BA%A1n-ch%E1%BA%BF-%C4%91%E1%BB%91i-v%E1%BB%9Bi-qu%E1%BA%A3ng-c%C3%A1o-meta h_01HNW0B77CQ4HS6ERHBD8YV28E=d%E1%BB%AF-li%E1%BB%87u-ph%C3%A2n-b%E1%BB%95-b%E1%BB%8B-h%E1%BA%A1n-ch%E1%BA%BF-%C4%91%E1%BB%91i-v%E1%BB%9Bi-qu%E1%BA%A3ng-c%C3%A1o-meta getting-userlevel-data-for-android-installs=nh%E1%BA%ADn-d%E1%BB%AF-li%E1%BB%87u-c%E1%BA%A5p-ng%C6%B0%E1%BB%9Di-d%C3%B9ng-cho-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-android-v%C3%A0-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng 01H7YJVNMTYJV5H1FSM5HBD3N7=nh%E1%BA%ADn-d%E1%BB%AF-li%E1%BB%87u-c%E1%BA%A5p-ng%C6%B0%E1%BB%9Di-d%C3%B9ng-cho-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-android-v%C3%A0-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng 01H7YJVNMTAQKG7YDS72125HFP=l%C6%B0u-%C3%BD meta-install-referrer%E2%80%94faq=li%C3%AAn-k%E1%BA%BFt-gi%E1%BB%9Bi-thi%E1%BB%87u-c%C3%A0i-%C4%91%E1%BA%B7t-metafaq h_01HQR6QZKDEWXXMGFXXMG2VZ7F=li%C3%AAn-k%E1%BA%BFt-gi%E1%BB%9Bi-thi%E1%BB%87u-c%C3%A0i-%C4%91%E1%BA%B7t-metafaq encrypted-data-from-the-referrer=d%E1%BB%AF-li%E1%BB%87u-%C4%91%C6%B0%E1%BB%A3c-m%C3%A3-h%C3%B3a-t%E1%BB%AB-api-li%C3%AAn-k%E1%BA%BFt-gi%E1%BB%9Bi-thi%E1%BB%87u-google-play-ho%E1%BA%B7c-li%C3%AAn-k%E1%BA%BFt-gi%E1%BB%9Bi-thi%E1%BB%87u-c%C3%A0i-%C4%91%E1%BA%B7t-meta 01H7YJVNMTZGQFEGJD9QEEVZHR=d%E1%BB%AF-li%E1%BB%87u-%C4%91%C6%B0%E1%BB%A3c-m%C3%A3-h%C3%B3a-t%E1%BB%AB-api-li%C3%AAn-k%E1%BA%BFt-gi%E1%BB%9Bi-thi%E1%BB%87u-google-play-ho%E1%BA%B7c-li%C3%AAn-k%E1%BA%BFt-gi%E1%BB%9Bi-thi%E1%BB%87u-c%C3%A0i-%C4%91%E1%BA%B7t-meta 01H7YJVNMTBN9RJ6Q7TJ1AJ0XX=cost-clicks-and-impressions 01H7YJVNMTGRBQG54DVMJDHDKS=l%C6%B0u-%C3%BD-1 cost-data-sync-status=tr%E1%BA%A1ng-th%C3%A1i-%C4%91%E1%BB%93ng-b%E1%BB%99-d%E1%BB%AF-li%E1%BB%87u-chi-ph%C3%AD 01H7YJVNMTRQAYG7TY29AX4MZS=tr%E1%BA%A1ng-th%C3%A1i-%C4%91%E1%BB%93ng-b%E1%BB%99-d%E1%BB%AF-li%E1%BB%87u-chi-ph%C3%AD 01H7YJVNMTNRREKWY96CK9JJKV=inapp-event-mapping 01H7YJVNMT2DRVR26F8CDDTWHP=l%C6%B0u-%C3%BD-2 01H7YJVNMV5AZ9G2KCKEFF1CSV=retargeting-attribution 01H7YJVNMVSA4Y33MW6Q8Y777Y=advanced_data_sharing 01H7YJVNMVWRG10SZY1B33H5EA=ad-revenue-recording record-meta-audience-network-ad-revenue=ghi-nh%E1%BA%ADn-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o-t%E1%BB%AB-m%E1%BA%A1ng-%C4%91%E1%BB%91i-t%C6%B0%E1%BB%A3ng-meta 01H7YJVNMV1TTHKMMX4TFB2BF3=ghi-nh%E1%BA%ADn-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o-t%E1%BB%AB-m%E1%BA%A1ng-%C4%91%E1%BB%91i-t%C6%B0%E1%BB%A3ng-meta 01H7YJVNMVMW5BXWEP8BPX4D7E=permissions aggregate-event-measurement-aem-for-ios=%C4%91o-l%C6%B0%E1%BB%9Dng-s%E1%BB%B1-ki%E1%BB%87n-h%E1%BB%A3p-nh%E1%BA%A5t-aem-cho-ios 01H7YJVNMVGFYMHE5FACTD9NS0=%C4%91o-l%C6%B0%E1%BB%9Dng-s%E1%BB%B1-ki%E1%BB%87n-h%E1%BB%A3p-nh%E1%BA%A5t-aem-cho-ios meta-ads-integration-troubleshooting=kh%E1%BA%AFc-ph%E1%BB%A5c-s%E1%BB%B1-c%E1%BB%91-khi-t%C3%ADch-h%E1%BB%A3p-qu%E1%BA%A3ng-c%C3%A1o-meta 01H7YJVNMVCAQ6ETKBGCAM31B9=kh%E1%BA%AFc-ph%E1%BB%A5c-s%E1%BB%B1-c%E1%BB%91-khi-t%C3%ADch-h%E1%BB%A3p-qu%E1%BA%A3ng-c%C3%A1o-meta 01H7YJVNMV3YRF59RX87TJCT8D=no-idfa-collection 01H7YJVNMVHCYVWKDW5WWPX1A5=wrong-facebook-app-id 01H7YJVNMVE9QJAXQBD4P14C88=app-status-on-meta-ads 01H7YJVNMVBRVTT9HH7KM8P33B=wrong-type-of-meta-ads-campaign 01H7YJVNMV4G3VP40E6VFD7SJD=meta-ads-app-install facebook-ads-updates=c%E1%BA%ADp-nh%E1%BA%ADt-qu%E1%BA%A3ng-c%C3%A1o-meta 01H7YJVNMV5MQX81Z9NP3X5KJM=c%E1%BA%ADp-nh%E1%BA%ADt-qu%E1%BA%A3ng-c%C3%A1o-meta 01H7YJVNMVS2A95Z20R1ENQYPR=quan-tr%E1%BB%8Dng ios-14-updates-relating-to-facebook=c%C3%A1c-b%E1%BA%A3n-c%E1%BA%ADp-nh%E1%BA%ADt-ios-14-li%C3%AAn-quan-%C4%91%E1%BA%BFn-qu%E1%BA%A3ng-c%C3%A1o-meta 01H7YJVNMVQP5PR6XDHTCPXVDC=c%C3%A1c-b%E1%BA%A3n-c%E1%BA%ADp-nh%E1%BA%ADt-ios-14-li%C3%AAn-quan-%C4%91%E1%BA%BFn-qu%E1%BA%A3ng-c%C3%A1o-meta h_01HDP0Y4CZBZEK5VZ6FG3T31JB=xem-th%C3%AAm" />
