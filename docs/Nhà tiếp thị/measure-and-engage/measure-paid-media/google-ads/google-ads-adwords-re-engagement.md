---
title: Google Ads (AdWords)—thu hút lại
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
  created_at: '2022-01-20T09:55:51Z'
  edited_at: '2023-11-01T10:21:33Z'
  id: 4417296925073
  locale: vi
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/vi/articles/4417296925073
---
> **Sơ lược:** Đo lường các chiến dịch nhắm mục tiêu lại của Google Ads.

## Chiến dịch nhắm lại mục tiêu của Google Ads

Với AppsFlyer, bạn có thể đo lường kết quả của **Chiến dịch Ứng dụng Google Ads dành cho Thu hút**.  
Trong AppsFlyer, các chiến dịch như vậy được gọi là chiến dịch <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide">Nhắm mục tiêu lại</Anchor>. AppsFlyer hỗ trợ nhận dữ liệu chi phí, lượt nhấp và lượt hiển thị cho các chiến dịch nhắm mục tiêu lại. Việc tích hợp này cho phép bạn xem và đo lường chi tiêu quảng cáo của mình cho Google Ads và sau đó tính toán eCPI và ROI của các chiến dịch Google Ads của bạn.

Chiến dịch nhắm lại mục tiêu nhắm vào người dùng trước đây đã cài đặt ứng dụng của bạn.

* Lượt tương tác nhắm lại mục tiêu của người dùng, những người vẫn cài đặt ứng dụng của bạn, được gọi là **Tương tác lại**. Các lượt tương tác này thường dẫn đến những người dùng liên kết sâu.
* Tương tác nhắm lại mục tiêu theo người dùng, những người chưa cài đặt ứng dụng của bạn, được gọi là **Lượt cài đặt lại** hay **Lượt phân bổ lại**.

Để biết thêm thông tin, vui lòng xem <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">Google Ads để biết về tài liệu hỗ trợ tương tác</Anchor>.

## Thiết lập các chiến dịch ứng dụng Google Ads để tham gia

Trước khi bắt đầu, hãy xem lại <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001?hl=en">hướng dẫn của Google về cách chia sẻ liên kết với các tài khoản Google Ads khác</Anchor> để đảm bảo các chiến dịch thu hút của bạn được đo lường chính xác thông qua ID liên kết mà bạn đang có.

Để đo Chiến dịch Ứng dụng Google Ads cho Tương tác, hãy làm theo ba bước sau:

<div id="enabling-retargeting-in-app-settings" />

<Accordion title="Bật Nhắm lại mục tiêu trong cài đặt của ứng dụng">

Để bật chiến dịch nhắm lại mục tiêu của bất kỳ nguồn phương tiện nào, bạn cần bật nó ở cấp ứng dụng. Nếu đây là chiến dịch nhắm lại mục tiêu đầu tiên cho ứng dụng của bạn, hãy thực hiện như sau:

1. Trong AppsFlyer, đi tới **App settings** (Cài đặt của ứng dụng).
2. Cuộn xuống dưới cùng.
3. Bật tùy chọn **Phân bổ thu hút lại.**

</Accordion>

<div id="enable-google-ads-retargeting-in-appsflyer" />

<Accordion title="Bật tính năng Nhắm mục tiêu lại Google Ads trong AppsFlyer">

* Thực hiện theo mục số 5 trong các <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">hướng dẫn</Anchor> để thiết lập Google Ads trong AppsFlyer.

</Accordion>

<div id="importing-session-start-conversions-in-google-ads" />

<Accordion title="Nhập dữ liệu chuyển đổi phiên bắt đầu trong Google Ads">

Để ghi nhận lượt chuyển đổi cho các chiến dịch thu hút lại **trong Google Ads**, bạn cần nhập sự kiện session\_start trong Google Ads.

Sự kiện này xuất hiện trong Google Ads nếu có ít nhất một người dùng khởi chạy ứng dụng sau khi bạn bật nhắm lại mục tiêu trong AppsFlyer cho Google Ads. Để chắc chắn, hãy tự khởi chạy ứng dụng sau khi bạn bật nhắm lại mục tiêu.

Để tìm hiểu cách nhập chuyển đổi trong Google Ads, vui lòng xem thông tin <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">tại đây</Anchor>.

> 📘 **Lưu ý**
>
> Không giống như tất cả các sự kiện khác, session\_start có thể được yêu cầu bởi API Google Ads, ngay cả khi bạn không nhập session\_start vào Google Ads từ AppsFlyer.
>  Tuy nhiên, trong trường hợp đó, các lượt chuyển đổi này vẫn sẽ được phân bổ trong AppsFlyer. Điều này **tạo ra sự khác biệt đáng kể giữa dữ liệu của bạn trong AppsFlyer và trong Google Ads**. Hơn nữa, điều này **ngăn Google Ads tối ưu hóa** việc nhắm mục tiêu người dùng chiến dịch của bạn.

</Accordion>

<div id="setting-up-deep-linking-for-app-campaigns-for-engagement" />

<Accordion title="Thiết lập liên kết sâu cho các chiến dịch ứng dụng dành cho tương tác">

Chiến dịch Ứng dụng Google dành cho Tương tác yêu cầu bạn <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6310747?hl=en&ref_topic=3121770">sử dụng các liên kết sâu cho các chiến dịch thu hút lại</Anchor>. Các giải pháp liên kết sâu của bên thứ ba không thể được sử dụng do không khớp tên miền. Điều này bao gồm OneLink của AppsFlyer. Sử dụng <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6046977?hl=en">Liên kết Ứng dụng được phát triển nội bộ của riêng bạn, Liên kết Chung hoặc các lược đồ URI tùy chỉnh</Anchor>.

Không cần thêm bất kỳ tham số bổ sung nào vào liên kết sâu (is\_retargeting=true và pid=adwords là không bắt buộc).

</Accordion>

## Tiếp thị lại năng động và chiến dịch mua sắm

Tiếp thị lại năng động cho các ứng dụng và chiến dịch mua sắm được hỗ trợ trong AppsFlyer. Nền tảng AppsFlyer xử lý chúng giống như bất kỳ chiến dịch tương tác lại nào khác.

Để tìm hiểu về tiếp thị lại năng động cho các ứng dụng, nhấp vào <Anchor target="_blank" href="https://support.google.com/adwords/answer/7538938">đây</Anchor>.  
 Để tìm hiểu về các chiến dịch Mua sắm, nhấp vào <Anchor target="_blank" href="https://support.google.com/google-ads/answer/2454022?hl=en">đây</Anchor>.  
 Để tìm hiểu thêm về Google Ads dành cho Tương tác, nhấp vào <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">đây</Anchor>.

> 📄 **Xem thêm**
>
> * Để biết những lưu ý liên quan đến iOS 14, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/get-skan-postback-data-from-google-ads">khả năng tương tác SKAdNetwork của Google Ads với AppsFlyer</Anchor>.

<div data-zendesk-anchors="google-ads-retargeting-campaigns=chi%E1%BA%BFn-d%E1%BB%8Bch-nh%E1%BA%AFm-l%E1%BA%A1i-m%E1%BB%A5c-ti%C3%AAu-c%E1%BB%A7a-google-ads h_01HDP34BWZFG09ABN5NQB6EY32=chi%E1%BA%BFn-d%E1%BB%8Bch-nh%E1%BA%AFm-l%E1%BA%A1i-m%E1%BB%A5c-ti%C3%AAu-c%E1%BB%A7a-google-ads setting-up-google-ads-app-campaigns-for-engagement=thi%E1%BA%BFt-l%E1%BA%ADp-c%C3%A1c-chi%E1%BA%BFn-d%E1%BB%8Bch-%E1%BB%A9ng-d%E1%BB%A5ng-google-ads-%C4%91%E1%BB%83-tham-gia h_01HDP34BWZXXNZDE0SR4MXBC9V=thi%E1%BA%BFt-l%E1%BA%ADp-c%C3%A1c-chi%E1%BA%BFn-d%E1%BB%8Bch-%E1%BB%A9ng-d%E1%BB%A5ng-google-ads-%C4%91%E1%BB%83-tham-gia h_01HDP34BWZNHY08NDX6YSE9CXR=enabling-retargeting-in-app-settings h_01HDP34BWZNNNT4HRMXJB2X3S2=enable-google-ads-retargeting-in-appsflyer h_01HDP34BWZ8MGJKEZFC77VYWNG=importing-session-start-conversions-in-google-ads h_01HDP34BWZHWVKKNB7CEHY73R0=l%C6%B0u-%C3%BD h_01HDP34BWZ64XG2G0PTH6XCCMG=setting-up-deep-linking-for-app-campaigns-for-engagement dynamic-remarketing-and-shopping-campaigns=ti%E1%BA%BFp-th%E1%BB%8B-l%E1%BA%A1i-n%C4%83ng-%C4%91%E1%BB%99ng-v%C3%A0-chi%E1%BA%BFn-d%E1%BB%8Bch-mua-s%E1%BA%AFm h_01HDP34BWZ990SD3B1C5DZRESK=ti%E1%BA%BFp-th%E1%BB%8B-l%E1%BA%A1i-n%C4%83ng-%C4%91%E1%BB%99ng-v%C3%A0-chi%E1%BA%BFn-d%E1%BB%8Bch-mua-s%E1%BA%AFm h_01HDP2XBSEJVQ5G0MD0V5R05CM=xem-th%C3%AAm" />
