---
title: >-
  Hướng dẫn tích hợp trình kết nối SDK doanh thu quảng cáo chung ở mức lượt hiển
  thị trong ROI360
metadata:
  keywords:
    - ROI
    - ad revenue
    - Advertisers
    - Advertiser
    - Developer
    - Developers
    - ad revenue SDK
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-01-12T09:09:07Z'
  edited_at: '2024-07-01T13:48:40Z'
  id: 4416353506833
  locale: vi
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/vi/articles/4416353506833
---
> **Sơ lược:** Trình kết nối SDK doanh thu quảng cáo chung của AppsFlyer hoạt động với các mạng quảng cáo trực tuyến để báo cáo doanh thu quảng cáo với độ chi tiết ở mức lượt hiển thị.

![mceclip1__1_.png](https://files.readme.io/202ded6950dfbf370bb48738876224936d28ecfae0c0aba09d1c49892b774cb5-31202279100177.png)

## Báo cáo doanh thu quảng cáo ở mức lượt hiển thị qua trình kết nối SDK

**Tùy chọn báo cáo doanh thu quảng cáo**

Doanh thu quảng cáo được báo cáo cho AppsFlyer dựa trên độ chi tiết tổng hợp (thông qua API) hoặc độ chi tiết ở mức lượt hiển thị (thông qua SDK). Dữ liệu ở mức lượt hiển thị theo SDK:

* Có tính cập nhật của dữ liệu tốt hơn và tính sẵn có sớm hơn trong AppsFlyer.
* Hỗ trợ SKAN.

**Lưu ý:**

* Những lượt hiển thị này được thu thập và xử lý trong AppsFlyer, nhưng không bị tính vào gói trong ứng dụng của bạn.
* Có một <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad_revenue_unity_connector">trình cắm doanh thu quảng cáo của AppsFlyer cho Unity</Anchor>.

### Báo cáo doanh thu quảng cáo qua trình kết nối SDK

**Các nguyên tắc hoạt động của SDK**

Trình kết nối SDK doanh thu quảng cáo gửi dữ liệu doanh thu ở mức lượt hiển thị đến SDK AppsFlyer. Các sự kiện hiển thị này được thu thập và xử lý trong AppsFlyer và sự kiện doanh thu quảng cáo, `af_ad_revenue` , được tạo ra trong nền tảng với doanh thu được cho là đến từ nguồn UA ban đầu.

**Hiển thị dữ liệu**

Sự kiện `af_ad_revenue` được sử dụng để xác định doanh thu quảng cáo. Sự kiện này được triển khai trên toàn nền tảng, bao gồm các bảng điều khiển và công cụ phân phối dữ liệu khác.

**Mạng được hỗ trợ**

Danh sách các mạng dàn xếp quảng cáo và mạng kiếm tiền từ doanh thu quảng cáo được hỗ trợ có thể gửi dữ liệu cho chúng tôi qua trình kết nối SDK doanh thu quảng cáo chung như sau:

* <Anchor target="_blank" href="/marketers/vi/docs/ironsource-campaign-configuration#ad-revenue-tab">Mạng dàn xếp quảng cáo Unity LevelPlay</Anchor> (tên cũ là ironSource)
* <Anchor target="_blank" href="/marketers/vi/docs/applovin-max-ad-revenue-configuration">Applovin Max</Anchor>
* <Anchor target="_blank" href="/marketers/vi/docs/google-admob-ad-revenue-attribution-configuration">Google AdMob</Anchor>
* <Anchor target="_blank" href="/marketers/vi/docs/fyber-campaign-configuration">Fyber</Anchor>
* <Anchor target="_blank" href="/marketers/vi/docs/appodeal-campaign-configuration">Appodeal</Anchor>
* Admost
* Topon
* Tradplus
* <Anchor target="_blank" href="/marketers/vi/docs/yandex-direct-campaign-configuration">Yandex</Anchor>
* <Anchor target="_blank" href="/marketers/vi/docs/chartboost-campaign-configuration">Chartboost</Anchor>
* customMediation (khi giải pháp dàn xếp quảng cáo không nằm trong danh sách các đối tác dàn xếp quảng cáo được hỗ trợ)
* directMonetizationNetwork (khi ứng dụng tích hợp trực tiếp với các mạng kiếm tiền mà không cần mạng dàn xếp quảng cáo)

**Tính cập nhật của dữ liệu**

Trình kết nối SDK **gửi dữ liệu doanh thu đến nền tảng tại thời điểm hiển thị quảng cáo. Đối với khách hàng cao cấp của ROI360, dữ liệu sẽ có sẵn trong:**

* **Chủ đề về mức lượt hiển thị của DataLocker lúc 1 giờ sáng và mỗi 1 giờ sau đó,**
* **Báo cáo hoạt động và nhóm (cohort) của AppsFlyer lúc 5 giờ sáng theo giờ UTC và mỗi 4 giờ sau đó.**

## Triển khai trình kết nối SDK doanh thu quảng cáo chung của AppsFlyer

**Để triển khai trình kết nối SDK doanh thu quảng cáo chung của AppsFlyer**:

1. <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">Bật mục doanh thu quảng cáo cấp SDK trong AppsFlyer</Anchor> cho đối tác bạn muốn kết nối. **Lưu ý**: Bạn cần thực hiện thao tác này cho từng ứng dụng riêng lẻ.
2. Yêu cầu nhà phát triển của bạn tích hợp trình kết nối SDK doanh thu quảng cáo chung của AppsFlyer theo <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue">các hướng dẫn sau</Anchor>.
3. Để ghi lại doanh thu quảng cáo trong bảng điều khiển SKAdNetwork của bạn, hãy làm theo <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">hướng dẫn về doanh thu quảng cáo trong SKAN</Anchor>.

## Đặc điểm và hạn chế

| Đặc điểm | Lưu ý |
| --- | --- |
| Admob | <ul><li>Để bật iLTV cho Admob, hãy theo <Anchor target="_blank" href="https://support.google.com/admob/answer/11322405#getstarted">liên kết này</Anchor></li><li>Đối với Android và Unity, doanh thu dựa trên lượt hiển thị sẽ được báo cáo bởi iLTV SDK của Admob trong <Anchor target="_blank" href="https://developers.google.com/android/reference/com/google/android/gms/ads/AdValue#public-long-getvaluemicros">các đơn vị vi mô</Anchor>. Để hiển thị chính xác khoản doanh thu quảng cáo tính bằng USD trong AppsFlyer, trước khi gửi khoản doanh thu quảng cáo đến AppsFlyer, hãy chia số tiền nhận được từ trình xử lý sự kiện iLTV cho 1 triệu.</li></ul> |
| Giá trị doanh thu quảng cáo | Các sự kiện hiển thị có doanh thu trị giá hơn 10 USD (hoặc khoản tương đương bằng các đơn vị tiền tệ khác) sẽ không được trình kết nối SDK xử lý. |
| Kênh | Kênh không được hỗ trợ cho các ứng dụng ngoài cửa hàng, ngoại trừ Amazon. |
| Loại quảng cáo | Không được hỗ trợ. |

<div data-zendesk-anchors="impressionlevel-ad-revenue-reporting-by-sdk-connector=b%C3%A1o-c%C3%A1o-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o-%E1%BB%9F-m%E1%BB%A9c-l%C6%B0%E1%BB%A3t-hi%E1%BB%83n-th%E1%BB%8B-qua-tr%C3%ACnh-k%E1%BA%BFt-n%E1%BB%91i-sdk 01H8HHAQHK6CDK8X2Y6N4GANNC=b%C3%A1o-c%C3%A1o-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o-%E1%BB%9F-m%E1%BB%A9c-l%C6%B0%E1%BB%A3t-hi%E1%BB%83n-th%E1%BB%8B-qua-tr%C3%ACnh-k%E1%BA%BFt-n%E1%BB%91i-sdk reporting-ad-revenue-using-the-sdk-connector=b%C3%A1o-c%C3%A1o-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o-qua-tr%C3%ACnh-k%E1%BA%BFt-n%E1%BB%91i-sdk 01H8HHAQHKQ3H3R21Z1JYNJ2EE=b%C3%A1o-c%C3%A1o-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o-qua-tr%C3%ACnh-k%E1%BA%BFt-n%E1%BB%91i-sdk implementing-generic-appsflyer-ad-revenue-sdk-connector=tri%E1%BB%83n-khai-tr%C3%ACnh-k%E1%BA%BFt-n%E1%BB%91i-sdk-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o-chung-c%E1%BB%A7a-appsflyer 01H8HHAQHKCXKPJJE8EDT1J9CR=tri%E1%BB%83n-khai-tr%C3%ACnh-k%E1%BA%BFt-n%E1%BB%91i-sdk-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o-chung-c%E1%BB%A7a-appsflyer traits-and-limitations=%C4%91%E1%BA%B7c-%C4%91i%E1%BB%83m-v%C3%A0-h%E1%BA%A1n-ch%E1%BA%BF 01H8HHAQHMCSVQ2ZAT3G7XJKAN=%C4%91%E1%BA%B7c-%C4%91i%E1%BB%83m-v%C3%A0-h%E1%BA%A1n-ch%E1%BA%BF" />
