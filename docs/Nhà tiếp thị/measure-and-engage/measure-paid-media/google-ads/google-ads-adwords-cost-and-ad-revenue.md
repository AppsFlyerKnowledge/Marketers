---
title: Google Ads (AdWords)—chi phí và doanh thu quảng cáo
metadata:
  keywords:
    - Advertisers
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-01-20T10:01:42Z'
  edited_at: '2023-11-01T10:21:46Z'
  id: 4417309205521
  locale: vi
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/vi/articles/4417309205521
---
> **Sơ lược:** Bật dữ liệu chi phí và doanh thu quảng cáo của Google Ads trong AppsFlyer.

## Trạng thái đồng bộ dữ liệu chi phí

<Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Xem trạng thái API chi phí của bạn</Anchor> và lần cuối cùng AppsFlyer quản lý kéo dữ liệu chi phí phù hợp vào trang tổng quan trạng thái tích hợp chi phí (và doanh thu quảng cáo) hoặc trang tổng quan mạng quảng cáo cá nhân. 

Google Ads cho phép bạn đồng bộ vài tài khoản để kéo dữ liệu chi phí. Đối với từng tài khoản đã đồng bộ, AppsFlyer hiển thị trạng thái tích hợp chi phí và lần cuối cùng AppsFlyer kéo thành công dữ liệu chi phí khớp.

### Ngừng đồng bộ hóa chi phí Google

**Để ngừng đồng bộ hóa chi phí Google, hãy xóa kết nối tài khoản Google:**

* <Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">Chuyển đến tab chi phí, trong cột hành động, di chuột qua một tài khoản, nhấp vào Delete connection.</Anchor> Sau khi xóa, AppsFlyer sẽ ngừng nhận chi phí. Xóa kết nối không ảnh hưởng đến dữ liệu lịch sử.

## Chi phí, lượt nhấp và lượt hiển thị

Tích hợp chi phí cung cấp dữ liệu tổng hợp sau:

* Dữ liệu chi phí cho chiến dịch, nhóm quảng cáo, địa lý/quốc gia và cấp độ kênh của bạn. Xem <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">bảng tích hợp chi phí mạng quảng cáo</Anchor> để biết chi tiết đầy đủ về các phương diện, phép đo và tính năng được hỗ trợ.  
  **Lưu ý**: Dữ liệu chi phí yêu cầu phải có đăng ký <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>.
* Dữ liệu về lượt chuột, lượt hiển thị và dữ liệu phong phú (từ khóa, tên chiến dịch và bộ quảng cáo).

> 📘 **Lưu ý**
>
> * Có hỗ trợ Tài khoản MCC.
> * Hiện không có dữ liệu về chi phí, số lượt nhấp và số lượt hiển thị cho các chiến dịch đăng ký trước do những hạn chế trong API Google Ads.

Để xem dữ liệu chi phí, nhấp chuột và hiển thị của Google Ads trong bảng điều khiển AppsFlyer, hãy kết nối qua trang cấu hình Google Ads của bạn. Khi kết nối hoàn tất, AppsFlyer bắt đầu truy vấn số tiền chi phí, nhấp chuột và hiển thị Quảng cáo Google cho tất cả các chiến dịch hiện tại của bạn.

Đọc thêm về cách <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">thiết lập chi phí trong Google Ads</Anchor>.

Đọc thêm về cách Google xác định lượt nhấp và lượt xem.

Đọc thêm về <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6163740">các hạn chế của Google Ads</Anchor>.

**Sau khi cài đặt, dữ liệu sẽ đi qua trong vòng một vài giờ**.

> 👍 **Lời khuyên**
>
> Người dùng có thể xác nhận họ đã đăng nhập bằng tài khoản Google Ads chính xác bằng cách kiểm tra địa chỉ email xuất hiện ở góc trên cùng bên phải của bảng điều khiển Google Ads.
>
> ![short.png](https://support.appsflyer.com/hc/article_attachments/4417297915537)
>  Nếu tài khoản Google Ads là tài khoản phụ của tài khoản MCC, thì ID bên phải trên cùng là của MCC,  và ID của tài khoản phụ sẽ nằm ở góc trên cùng bên trái.
>
> Nếu tài khoản không chính xác, hãy đăng xuất khỏi tài khoản và đăng nhập lại bằng địa chỉ email cho một tài khoản Google khác.

## Ghi nhận doanh thu quảng cáo bằng Google Ads

Tính năng tích hợp doanh thu Google Ads (AdWords) không còn được hỗ trợ kể từ ngày 30 tháng 11 năm 2020. Đối với dữ liệu doanh thu quảng cáo, khách hàng AdWords cần chuyển sang <Anchor target="_blank" href="/marketers/vi/docs/google-admob-ad-revenue-attribution-configuration">Google AdMob</Anchor>.

<div id="faq" />

<Accordion title="Câu hỏi thường gặp">

| **Tại sao tôi không thể nhìn thấy dữ liệu chi phí của tôi?**<br /><br />Có một số lý do có thể khiến bạn không nhìn thấy dữ liệu:<ul><li>Khi đăng nhập, điều quan trọng là phải xác minh đúng tài khoản Google được sử dụng.<br />Nếu bạn đăng nhập bằng tài khoản Google không chính xác, sẽ không có chi phí nào được kéo hoặc hiển thị. Trong tình huống như vậy, bạn phải xóa ứng dụng khỏi quyền của ứng dụng Google và đăng nhập bằng tài khoản đúng. Để làm như vậy, hãy làm theo các bước sau:<ol><li>Nhấp vào URL dưới đây: <Anchor target="_blank" href="https://myaccount.google.com/permissions">https://myaccount.google.com/permissions</Anchor></li><li>Xóa Chi phí AppsFlyer trên Google và đăng nhập lại.</li></ol></li><li>Trong một số trường hợp, tính năng tích hợp chi phí đại lý được bật nhưng không nhận chi phí vì người dùng đại lý đã đăng nhập không có quyền truy cập vào ID khách hàng Google Ads chính xác. Điều này dẫn đến việc nhà quảng cáo xem được dữ liệu chi phí không đầy đủ.</li></ul>Đảm bảo người dùng đại lý đăng nhập vào tab Chi phí có quyền truy cập vào ID khách hàng Google Ads được thiết lập trong tab Integration.<br /><br />[<Image alt="" src="https://support.appsflyer.com/hc/article_attachments/5991137319441" width="457px" />](https://support.appsflyer.com/hc/article_attachments/5991137319441)<ul><li>Sử dụng dấu cách hoặc ký tự đặc biệt trong chiến dịch Tìm kiếm trên iOS hoặc Trang đích của Android có thể gây ra sự cố với việc ghép dữ liệu chi phí với dữ liệu số lần nhấp chuột và dẫn đến báo cáo chi phí bị thiếu.</li><li>Khi đại lý tắt tính năng tích hợp chi phí sau khi chi phí đã được thu thập nhưng nhà quảng cáo vẫn có tính năng tích hợp chi phí đang hoạt động, thì dữ liệu chỉ được liên kết với nhà quảng cáo kể từ ngày đại lý tắt tính năng tích hợp.</li></ul> |
| --- |
| **Dữ liệu về lượt nhấp theo địa lý của tôi ở đâu?**<br /><br />Trong một số trường hợp, AppsFlyer nhận dữ liệu nhấp chuột theo địa lý một phần từ Google. Khi điều này xảy ra, AppsFlyer hoàn thành thông tin nhấp chuột bị thiếu từ các nguồn khác của Google, những nguồn này thiếu dữ liệu theo địa lý. Do đó, khi nhóm theo Địa lý, tổng số lần nhấp chuột từ các chiến dịch của Google, có thể không khớp với cùng một số với thứ nguyên theo nhóm khác. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Lưu ý |
| --- | --- |
| Chiến dịch không hoạt động và đang hoạt động | Tích hợp Google hỗ trợ báo cáo chi phí cho **các chiến dịch không hoạt động** trong các trường hợp sau:<ul><li>Chiến dịch ứng dụng để tăng lượt cài đặt (loại chiến dịch ACI)</li><li>Chiến dịch ứng dụng để thu hút tương tác (loại chiến dịch ACE)</li></ul>Chiến dịch không hoạt động là chiến dịch không có lượt cài đặt hoặc chuyển đổi nào được ghi lại trong AppsFlyer.<br /><br />Đối với các chiến dịch không phải ACI và không phải ACE, AppsFlyer chỉ báo cáo các chi phí cho **các chiến dịch đang hoạt động** , nghĩa là ít nhất một chuyển đổi hoặc lượt cài đặt được ghi lại trong AppsFlyer. Chi phí được báo cáo trong khoảng thời gian 7 ngày kể từ khi chuyển đổi/cài đặt. |

</Accordion>

> 📄 **Xem thêm**
>
> * Để biết những lưu ý liên quan đến iOS 14, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/get-skan-postback-data-from-google-ads">khả năng tương tác SKAdNetwork của Google Ads với AppsFlyer</Anchor>.

<div data-zendesk-anchors="cost-data-sync-status=tr%E1%BA%A1ng-th%C3%A1i-%C4%91%E1%BB%93ng-b%E1%BB%99-d%E1%BB%AF-li%E1%BB%87u-chi-ph%C3%AD h_01HDP2SMHJT8Z6DP7BHC0Y5RRN=tr%E1%BA%A1ng-th%C3%A1i-%C4%91%E1%BB%93ng-b%E1%BB%99-d%E1%BB%AF-li%E1%BB%87u-chi-ph%C3%AD stopping-google-cost-sync=ng%E1%BB%ABng-%C4%91%E1%BB%93ng-b%E1%BB%99-h%C3%B3a-chi-ph%C3%AD-google h_01HDP2SMHJPEDKKZF9SBXW56KG=ng%E1%BB%ABng-%C4%91%E1%BB%93ng-b%E1%BB%99-h%C3%B3a-chi-ph%C3%AD-google cost-clicks-and-impressions=chi-ph%C3%AD-l%C6%B0%E1%BB%A3t-nh%E1%BA%A5p-v%C3%A0-l%C6%B0%E1%BB%A3t-hi%E1%BB%83n-th%E1%BB%8B h_01HDP2SMHJ26S1BCER3KKZ8H14=chi-ph%C3%AD-l%C6%B0%E1%BB%A3t-nh%E1%BA%A5p-v%C3%A0-l%C6%B0%E1%BB%A3t-hi%E1%BB%83n-th%E1%BB%8B h_01HDP2SMHJB5YE5PCWVJVBAKHD=l%C6%B0u-%C3%BD h_01HDP2SMHJF86QK9CJTVABKTYW=l%E1%BB%9Di-khuy%C3%AAn recording-ad-revenue-with-google-ads=ghi-nh%E1%BA%ADn-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o-b%E1%BA%B1ng-google-ads h_01HDP2SMHKC9TSZZZPFFNK8TPH=ghi-nh%E1%BA%ADn-doanh-thu-qu%E1%BA%A3ng-c%C3%A1o-b%E1%BA%B1ng-google-ads h_01HDP2SMHK8NH6M4T1A2Y79P55=faq h_01HDP2SMHKPDEE07H8WAP212TZ=traits-and-limitations h_01HDP2XBSEJVQ5G0MD0V5R05CM=xem-th%C3%AAm" />
