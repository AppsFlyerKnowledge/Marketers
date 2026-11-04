---
title: Cấu trúc và thông số liên kết phân bổ
metadata:
  keywords:
    - pid
    - Marketers
    - af_
    - af
    - c
    - af_mp
    - clickid
    - af_siteid
    - af_sub_siteid
    - af_c_id
    - af_adset_id
    - af_ad_type
    - af_viewthrough
    - af_cost_model
    - af_cost_value
    - af_web_dp
    - af_ref
    - af_ip
    - af_os_version
    - deep_link_sub
    - deep_link_value
    - af_og_title
    - af_og_description
    - af_og_image
    - af_prt
    - af_adset
    - af_ad
    - af_ad_id
    - af_channel
    - af_keywords
    - af_cost_currency
    - af_sub
    - af_r
    - af_dp
    - af_force_deeplink
    - is_incentivized
    - af_param_forwarding
    - af_partner_account_id
    - af_ua
    - af_os
    - af_model
    - af_media_type
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-12-24T11:50:00Z'
  edited_at: '2023-11-17T02:09:50Z'
  id: 207447163
  locale: vi
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/vi/articles/207447163
---
> **Khái quát:** Tìm hiểu về cấu trúc và thông số đường dẫn phân bổ của AppsFlyer.

<div id="overview" />

## Tổng quan

Đường dẫn phân bổ cho phép nhà quảng cáo thu thập dữ liệu về mức độ tương tác của người dùng với quảng cáo. Các đường dẫn phân bổ được đặt sau quảng cáo và thông báo cho AppsFlyer khi người dùng tương tác với một quảng cáo. Tương tác có thể xảy ra thông qua một lượt nhấp vào quảng cáo hoặc khi người dùng xem một lượt hiển thị quảng cáo. Một bản sao của URL phân bổ được gửi tới AppsFlyer.

Đường dẫn phân bổ được tạo bằng cách sử dụng **OneLink** hoặc **đường dẫn một nền tảng**.

|  | OneLink (liên kết đa nền tảng) | Liên kết một nền tảng |
| --- | --- | --- |
| Mô tả và trường hợp sử dụng | Sử dụng khi:<ul><li>Bạn muốn có một liên kết duy nhất cho tất cả các nền tảng.</li><li>Bắt buộc phải có khả năng liên kết sâu.</li><li>Bạn muốn sử dụng Liên kết Ứng dụng Android hoặc Liên kết Chung iOS để mở ứng dụng.</li></ul><Anchor target="_blank" href="/marketers/vi/docs/onelink-guide">Tìm hiểu thêm về OneLink</Anchor> | Sử dụng khi:<ul><li>Bạn chỉ sử dụng một nền tảng duy nhất. Ví dụ: Android mà không phải iOS.</li><li>Bạn chỉ sử dụng lược đồ URI để mở ứng dụng.</li></ul><Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#attribution-link-tab">Tìm hiểu thêm về cách thiết lập đối tác tích hợp</Anchor> |
| Điều kiện tiên quyết | <Anchor target="_blank" href="/marketers/vi/docs/create-a-onelink-template">Mẫu OneLink</Anchor> | Không |
| Thông tin bắt buộc | <ul><li>[Nguồn truyền thông](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)</li><li>[Chiến dịch](#c)</li><li>[ID Trang web / ID Trang Phụ](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> | <ul><li>[Nguồn truyền thông](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)</li><li>[Chiến dịch](#c)</li><li>[ID Trang web / ID Trang Phụ](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> |
| URL cơ sở | `{subdomain}`.onelink.me | app.appsflyer.com |
| Mã định danh duy nhất | ID mẫu | app\_id |
| Cấu trúc URL | `https://{subdomain}.onelink.me/  <br />{templateid}?pid={media_source}  <br />&af_siteid={ApplicationID}  <br />&c={CampaignName}` | `https://app.appsflyer.com/{app_id}?pid={media_source}&af_siteid={ApplicationID}&c={CampaignName}` |
| Ví dụ: | `https://yourbrand.onelink.me/aAB1?pid=greatnetwork_int  <br />&c=GreatCampaign&af_siteid=A1b1` | `https://app.appsflyer.com/com.greatapp?pid=greatnetwork_int&  <br />c=GreatCampaign&af_siteid=A1b1` |

<div id="attribution-link-parameters" />

## Thông số đường dẫn phân bổ

* Các thông số được liệt kê có sẵn để sử dụng trong đường dẫn phân bổ.
* Cột **loại trường** giá trị là giới hạn ký tự của giá trị thông số. Tìm hiểu thêm về các giới hạn liên quan đến độ dài của các giá trị thông số <Anchor target="_blank" href="/marketers/vi/docs/raw-data-field-dictionary">tại đây.</Anchor>

<div id="attribution-link-parametersua-and-retargeting" />

### Thông số đường dẫn phân bổ—UA và nhắm mục tiêu lại

Có thể [tải xuống bảng sau dưới dạng tệp tin `.csv`](https://docs.google.com/spreadsheets/d/e/2PACX-1vTZQnoDdFo2NxBuWXBs5gGgvkGU2pr_hn58H9Dtf5uHBAHv4Io89Wd44rRtL24pRsOXHthnBitaOyfp/pub?gid=0&single=true&output=csv).

<div id="attribution-parameters" />

| Tham số | Hiển thị tên trong dữ liệu thô | Mô tả | Loại và độ dài trường |
| --- | --- | --- | --- |
| <span id="pid"></span>pid | Nguồn truyền thông | Xác định một đối tác tích hợp của AppsFlyer một cách duy nhất. Đừng thay đổi thông số này. [Thông tin chi tiết khác](/docs/about-link-structure-and-parameters#partner-id-pid-parameter). | <span id="PID"></span>Chuỗi 150 |
| <span id="c"></span>c | Chiến dịch | Được cung cấp bởi nhà quảng cáo hoặc nhà phát hành. Xem [các giới hạn về tên chiến dịch](/docs/about-link-structure-and-parameters#what-limits-are-there-on-campaign-names). | <span id="Campaign"></span>Chuỗi 100 |
| <span id="af_prt"></span>af\_prt | Đối tác | <ul><li>Tên Tài khoản Đại lý cho phép phân bổ lượt cài đặt cho đại lý</li><li>**Thận trọng**: Không sử dụng tham số này trước khi đảm bảo đã bật **Quyền Đại lý**</li></ul> | Chuỗi 50 |
| <span id="af_mp"></span>af\_mp | Không áp dụng | <ul><li>Cho phép gửi đăng lại cho các đối tác tiếp thị của nhà phát hành mỗi lượt cài đặt.</li><li>**Lưu ý**: Hiện tại thông số này chỉ thích hợp cho Đối tác Tiếp thị Pinterest.</li></ul> |  |
| <span id="clickid"></span>clickid | Không áp dụng | Mã định danh lượt nhấp riêng của mạng quảng cáo |  |
| <span id="af_siteid"></span>af\_siteid | Site ID | <ul><li>ID duy nhất xác định nhà phát hành hiển thị quảng cáo. [Tìm hiểu thêm](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> | <span id="Site_id"></span>Chuỗi 24 |
| <span id="af_sub_siteid"></span>af\_sub\_siteid | ID Trang phụ | <ul><li>Mạng phụ quảng cáo/ID Nhà phát hành.</li><li>Nếu ngoài nhà phát hành chính (ID trang web), còn có nhà phát hành phụ hoặc bạn muốn thêm thông tin bổ sung, chẳng hạn như loại hình/vị trí đặt quảng cáo trong ứng dụng, như biểu ngữ, quảng cáo xen kẽ, video, v.v., hãy sử dụng af\_sub\_siteid. Ví dụ: af\_sub\_siteid =ABCD\_4567</li></ul> | Chuỗi 50 |
| <span id="af_c_id"></span>af\_c\_id | ID Chiến dịch | Do nhà quảng cáo/nhà phát hành cung cấp | Chuỗi 24 |
| <span id="af_adset"></span>af\_adset | Bộ quảng cáo | <ul><li>Do nhà quảng cáo/nhà phát hành cung cấp.</li><li>Bộ quảng cáo là cấp trung gian giữa Chiến dịch và Quảng cáo trong cấu trúc phân cấp. [Xem thêm](/docs/about-link-structure-and-parameters#mức-độ-chi-tiết-dữ-liệu)</li></ul> | Chuỗi 100 |
| <span id="af_adset_id"></span>af\_adset\_id | ID Bộ quảng cáo | Do nhà quảng cáo/nhà phát hành cung cấp | Chuỗi 24 |
| <span id="af_ad"></span>af\_ad | Quảng cáo | Tên Quảng cáo ([xem thêm](/docs/about-link-structure-and-parameters#mức-độ-chi-tiết-dữ-liệu)) - do nhà quảng cáo/nhà xuất bản cung cấp | Chuỗi 100 |
| <span id="af_ad_id"></span>af\_ad\_id | ID Quảng cáo | Do nhà quảng cáo/nhà phát hành cung cấp | Chuỗi 24 |
| <span id="af_ad_type"></span>af\_ad\_type | Loại quảng cáo | Sử dụng quy ước đặt tên sau:<ul><li>**text:** một đơn vị quảng cáo chỉ chứa văn bản, ví dụ: kết quả tìm kiếm</li><li>**banner:** một định dạng cơ bản xuất hiện ở trên cùng hoặc dưới cùng của màn hình thiết bị</li><li>**interstitial:** một quảng cáo toàn trang xuất hiện trong khoảng nghỉ trong trải nghiệm hiện tại</li><li>**video:** một video chuẩn, không phải video xem có thưởng</li><li>**rewarded\_video:** một đơn vị quảng cáo cung cấp phần thưởng trong ứng dụng để đổi lấy lượt xem video</li><li>**playable:** một đơn vị quảng cáo chứa bản xem trước tương tác của trải nghiệm ứng dụng</li><li>**sponsored\_content:** một liên kết nằm trong nội dung được tài trợ, như một bài viết quảng cáo</li><li>**audio:** một quảng cáo âm thanh</li></ul> | Chuỗi 24 |
| <span id="af_click_lookback"></span>af\_click\_lookback | Khung thời gian xem lại lượt phân bổ | <ul><li>Cửa sổ xem lại cho Phân bổ Lượt nhấp.  Thời lượng của cửa sổ này là CTIT (Thời gian nhấp để cài đặt) tối đa cho người dùng mới được phân bổ đến nguồn hiển thị quảng cáo/liên kết.</li><li>Số ngày có thể cấu hình cho thời gian phân bổ lượt nhấp xem lại.   Giá trị thông số khả dụng: 1d - 30d (ngày) HOẶC 1h-23h (giờ). Giá trị mặc định là 7d.</li><li>Có thể tùy chỉnh khung thời gian xem lại cho <Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows#thiết-lập-khung-thời-gian-xem-lại">OneLink và SRN</Anchor>.</li></ul>**Lưu ý**: Chỉ ảnh hưởng đến URL lượt nhấp mà không ảnh hưởng đến URL hiển thị. | Tối đa 3 ký tự |
| <span id="af_viewthrough_lookback"></span>{"af_viewthrough_"}  <br />lookback | Không áp dụng | <ul><li>Số giờ có thể cấu hình cho thời gian xem lại phân bổ lượt xem hết. Giá trị thông số khả dụng: 1h - 24h (giờ). Mặc định là 24h.</li><li>Khung thời gian xem lại có thể được tùy chỉnh cho <Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows#thiết-lập-khung-thời-gian-xem-lại">SRN</Anchor>.</li></ul>**Lưu ý**: Chỉ ảnh hưởng đến URL hiển thị mà không ảnh hưởng đến URL lượt nhấp | Tối đa 3 ký tự |
| <span id="af_channel"></span>af\_channel | Kênh | Kênh nguồn truyền thông mà quảng cáo được phân bổ, ví dụ như UAC\_Search, UAC\_Display, Instagram, Mạng Đối tượng Meta, v.v. | Enum động. Chuỗi 20 |
| <span id="af_keywords"></span>af\_keywords | Từ khóa | Danh sách từ khóa cho các chiến dịch nhắm mục tiêu văn bản | Chuỗi 100 |
| <span id="af_cost_model"></span>af\_cost\_model | Mô hình Chi phí | <ul><li>Mô hình chi phí, CPI (mặc định) hiện là mô hình được hỗ trợ duy nhất, khi báo cáo chi phí theo lượt nhấp, mà điền <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports">giá trị chi phí trong báo cáo dữ liệu hợp nhất của AppsFlyer</Anchor>.</li><li>Trường hợp có thể, báo cáo chi phí bằng <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview#cost-aggregation-methods">API</Anchor>. Trong trường hợp chi phí được báo cáo bằng trên liên kết và bằng API - API được ưu tiên.</li></ul> | Chuỗi 20 |
| <span id="af_cost_currency"></span>af\_cost\_currency | Đơn vị tiền tệ của chi phí | <ul><li>Mã tiền tệ 3 chữ cái tuân thủ <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview#cost-aggregation-methods">ISO-4217.</Anchor> Ví dụ: USD, ZAR, EUR</li><li>[Mặc định]: USD</li></ul> | Enum. 3 ký tự |
| <span id="af_cost_value"></span>af\_cost\_value | Giá trị Chi phí | <ul><li>Giá trị chi phí trong việc sử dụng tiền tệ chi phí.</li><li>Lên tới 4 chữ số sau dấu thập phân.</li><li>CHỈ thiết lập chữ số (sử dụng dấu thập phân nếu cần thiết) Ví dụ: "56", "2.85"</li></ul> | Chuỗi 20 |
| <span id="af_sub-n-n15-example-af_sub1"></span>af\_sub[n]<br /><br />(n=1-5) ví dụ: af\_sub1 | Thông số phụ [n] | Thông số tùy chỉnh tùy chọn được xác định bởi nhà quảng cáo. Để biết thêm thông tin về cách sử dụng các tham số này, hãy xem phần [Câu hỏi thường gặp](/docs/about-link-structure-and-parameters#faq). | Chuỗi 100 |
| <span id="af_r"></span>af\_r | Không áp dụng | Được sử dụng trong các liên kết đơn nền tảng để chuyển hướng người dùng đến URL được chỉ định cho **cả hai nền tảng** (Android và iOS).<ul><li>Được ghi đè bởi các thông số nền tảng đơn cấp liên kết sau):<ul><li>[`af_android_url`](/docs/about-link-structure-and-parameters#af_android_url)</li><li>[`af_ios_url`](/docs/about-link-structure-and-parameters#af_ios_url)</li><li>[`af_web_dp`](/docs/about-link-structure-and-parameters#af_web_dp)</li></ul></li></ul><ul><li>Ghi đè các thông số cấp mẫu sau:<ul><li>`android_custom_url`</li><li>`ios_custom_url`</li></ul></li></ul> |  |
| <span id="af_web_dp"></span>af\_web\_dp | Không áp dụng | URL chuyển hướng người dùng máy tính để bàn (ví dụ: Windows hoặc Mac) đến một trang web khác trang web đã cấu hình trong mẫu OneLink. Sử dụng tính năng này để duy trì dữ liệu phân bổ của người dùng máy tính để bàn trên các nền tảng khác (ví dụ: Google Analytics hoặc Omniture)<br /><br />**Lưu ý**: Nếu bạn có <Anchor target="_blank" href="/marketers/vi/docs/set-up-your-api-allowlist#redirect-allowlists">Danh sách cho phép chuyển hướng</Anchor> đang hoạt động, hãy đảm bảo đưa miền của URL này vào danh sách. |  |
| <span id="af_dp"></span>af\_dp | Không áp dụng | Giá trị dự phòng lược đồ URI để khởi chạy ứng dụng, được sử dụng nếu phương thức Liên kết Chung hoặc Liên kết Ứng dụng Android không thành công và cho người dùng Android có phiên bản thấp hơn phiên bản 6.0. Chỉ nên chỉ đến <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">đường dẫn cơ sở</Anchor>, tức là hoạt động mặc định. |  |
| <span id="af_force_deeplink"></span>af\_force\_deeplink | Không áp dụng | <Anchor target="_blank" href="/marketers/vi/docs/onelink-troubleshooting-and-faq">Đẩy liên kết sâu</Anchor> vào hoạt động được chỉ định trong giá trị af\_dp |  |
| <span id="af_ref"></span>af\_ref | Không áp dụng | Mạng quảng cáo làm việc với lượt nhấp S2S có thể gửi giá trị tham chiếu duy nhất bằng tham số sau đây: &af\_ref=**ReferrerValue**<br /><br />Giá trị af\_ref **phải** bao gồm một giá trị duy nhất, có cấu trúc như sau:<br /><br />**NetworkName\_UniqueClickValueForEachClick**<br /><br />Ví dụ: af\_ref=networkname\_123456789ABCDEF<br /><br />Tên mạng có thể là bất kỳ chuỗi nào hợp lệ. Tên mạng có thể là networkname\_int hoặc chỉ là networkname.<br /><br />AppsFlyer có thể sử dụng tham số này cho phân bổ trong các thiết bị Android. AppsFlyer không sử dụng tham số này cho phân bổ trong các thiết bị iOS hoặc Windows. |  |
| <span id="is_incentivized"></span>is\_incentivized | Không áp dụng | Boolean: true/false<br /><br />Chiến dịch khuyến khích hoặc không khuyến khích |  |
| <span id="af_param_forwarding"></span>af\_param\_forwarding | Không áp dụng | <ul><li>Khi được đặt thành false, các tham số trên liên kết phân bổ sẽ không được chuyển tiếp đến trang được chuyển hướng</li><li>Sử dụng điều này để tìm URL sạch hơn trong trang được chuyển hướng hoặc nếu các tham số liên kết phân bổ có thể gây ra sự cố do xử lý tham số truy vấn trên trang được chuyển hướng</li></ul> |  |
| <span id="af_base_params_forward"></span>af\_base\_params\_forward | Không áp dụng | <ul><li>Khi được đặt thành false, các thông số PID và C của sẽ AppsFlyer trên đường dẫn phân bổ sẽ không được chuyển tiếp đến trang được chuyển hướng</li><li>Sử dụng thông số này nếu URL sẽ được nhấp từ máy tính để bàn và bạn muốn giữ nguyên các thông số CRM thiết yếu nhưng xóa các thông số PID và C của AppsFlyer. Điều này sẽ tránh có nhiều PID trong URL.</li></ul> |  |
| <span id="af_partner_account_id"></span>af\_partner\_account\_id | ID tài khoản mạng | ID tài khoản của nhà quảng cáo với đối tác | Chuỗi 100 |
| <span id="af_redirect"></span>redirect | Không áp dụng | Khi `&redirect=false`, thông số này cho phép AppsFlyer biết rằng đây là một lượt nhấp S2S và đối tác là người chịu trách nhiệm chuyển hướng người dùng đã nhấp. |  |
| <span id="af_ua"></span>af\_ua | Tác nhân người dùng | Có liên quan đối với các mạng quảng cáo gửi lượt nhấp và lượt hiển thị <Anchor target="_blank" href="/partners/vi/docs/redirecting-users-to-the-app-store">từ máy chủ đến máy chủ</Anchor>.<br /><br />Chuỗi tác nhân người dùng được gửi dưới dạng:<ol><li>Thông số URL (mã hóa URL)</li><li>Tiêu đề yêu cầu HTTP (không được mã hóa)</li></ol>Tác nhân người dùng phải **giống hệt nhau trong cả thông số URL và tiêu đề HTTP**.<br /><br />**Lưu ý**: Trong Android, tác nhân người dùng đôi khi bị rút gọn thành Client Hints. Vẫn cần gửi tác nhân người dùng này.<ul><li>Ví dụ về tác nhân người dùng đầy đủ: `Mozilla/5.0 (Linux; Android 12; Pixel 5) AppleWebKit/537.36 (KHTML, như Gecko) Chrome/95.0.4638.16 Safari Di động/537.36`</li><li>Ví dụ về tác nhân người rút gọn: `Mozilla/5.0 (Linux; Android 10; K) AppleWebKit/537.36 (KHTML, như Gecko) Chrome/95.0.0.0 Safari Di động/537.36`</li></ul> |  |
| <span id="af_ip"></span>af\_ip | ip | Có liên quan đối với các mạng quảng cáo gửi lượt nhấp và lượt hiển thị <Anchor target="_blank" href="/partners/vi/docs/redirecting-users-to-the-app-store">từ máy chủ đến máy chủ</Anchor>.<br /><br />**Địa chỉ IP của thiết bị**<br /><br />**Đề xuất**: Nếu có, hãy cung cấp IP của thiết bị theo thông số af\_ip.<br /><br />**Tùy chọn tiếp theo**: Nếu có, AppsFlyer sẽ sử dụng IP trong X-Forwarded-For. |  |
| <span id="deprecated--af_os"></span>[Không còn được hỗ trợ] af\_os | Phiên bản hệ điều hành | [Chỉ dành cho iOS] Phiên bản hệ điều hành của thiết bị.<br /><br />Thông số này không còn được hỗ trợ nữa nhưng vẫn được AppsFlyer cho phép dùng. Khuyến nghị: Thay vào đó, hãy sử dụng thông số af\_os\_version. |  |
| <span id="af_os_version"></span>af\_os\_version | Phiên bản hệ điều hành | <ul><li>Có liên quan đối với các mạng quảng cáo gửi lượt nhấp và lượt hiển thị <Anchor target="_blank" href="/partners/vi/docs/redirecting-users-to-the-app-store">từ máy chủ đến máy chủ</Anchor>.</li><li>Phiên bản hệ điều hành của thiết bị.<ul><li>Android:<ul><li>Ví dụ: 12</li><li>Đối với tác nhân người dùng rút gọn (do trình duyệt chạy trên máy tính để bàn hoặc Android và sử dụng công cụ Chrome 110+), nên mạng quảng cáo phải sử dụng <Anchor target="_blank" href="https://web.dev/migrate-to-ua-ch/">API Client Hints</Anchor> để nhận giá trị này.</li><li>Đối với tác nhân người dùng **không** bị rút gọn, hãy sử dụng biểu thức chính quy sau để trích xuất phiên bản HĐH Android từ chuỗi tác nhân người dùng: `(\d+(?:\.\d+)*);(?:\s..-..;)?\s(.+?(?=\)\|\s\w*\/))`.</li></ul></li><li>iOS:<ul><li>Ví dụ: 16.2</li></ul></li></ul></li></ul> |  |
| <span id="af_model"></span>af\_model | Model Thiết bị | <ul><li>Có liên quan đối với các mạng quảng cáo gửi lượt nhấp và lượt hiển thị <Anchor target="_blank" href="/partners/vi/docs/redirecting-users-to-the-app-store">từ máy chủ đến máy chủ</Anchor>.</li><li>Model thiết bị.<ul><li>Android:<ul><li>Ví dụ: Pixel 5</li><li>Đối với tác nhân người dùng rút gọn (do trình duyệt chạy trên máy tính để bàn hoặc Android và sử dụng công cụ Chrome 110+), nên mạng quảng cáo phải sử dụng <Anchor target="_blank" href="https://web.dev/migrate-to-ua-ch/">API Client Hints</Anchor> để nhận giá trị này.</li><li>Đối với tác nhân người dùng **không** bị rút gọn, hãy sử dụng biểu thức chính quy sau để trích xuất mô hình Android từ chuỗi tác nhân người dùng: `(\d+(?:\.\d+)*);(?:\s..-..;)?\s(.+?(?=\)\|\s\w*\/))`.</li></ul></li><li>iOS:<ul><li>`ipad` hoặc `iphone` (tất cả đều là chữ thường)</li></ul></li></ul></li></ul> |  |
| <span id="af_media_type"></span>af\_media\_type | Loại đa phương tiện | Vị trí đặt quảng cáo có liên kết như sau:<ul><li>ứng dụng: Liên kết có sẵn thông qua một ứng dụng</li><li>web: Liên kết có sẵn trong một trang web di động</li></ul> |  |
| <span id="deep_link_sub110"></span>deep\_link\_sub1-10 | Không áp dụng | Giá trị liên kết sâu bổ sung. Nhà phát triển triển khai hành vi mong muốn của các giá trị trong mã. |  |
| <span id="deep_link_value"></span>deep\_link\_value | Không áp dụng | Tên của nội dung trong ứng dụng cụ thể mà người dùng sẽ được chuyển hướng đến. Các nhà phát triển thực hiện hành vi mong muốn của deep\_link\_value trong mã. |  |
| <span id="af_og_title"></span>af\_og\_title | Không áp dụng | Khi một liên kết được đăng lên mạng xã hội, tiêu đề biểu đồ mở (OG) sẽ tạo ra bản xem trước của tiêu đề. | Chuỗi 40 |
| <span id="af_og_description"></span>af\_og\_description | Không áp dụng | Khi một liên kết được đăng lên mạng xã hội, mô tả biểu đồ mở (OG) sẽ tạo ra bản xem trước của mô tả. | Chuỗi 300 |
| <span id="af_og_image"></span>af\_og\_image | Không áp dụng | Khi một liên kết được đăng lên mạng xã hội, hình ảnh biểu đồ mở (OG) sẽ tạo ra bản xem trước của hình ảnh. |  |

<div id="attribution-link-parametersretargeting-only" />

### Thông số đường dẫn phân bổ—chỉ nhắm mục tiêu lại

| Tham số | Hiển thị tên trong dữ liệu thô | Mô tả | Loại và chiều rộng của trường |
| --- | --- | --- | --- |
| <span id="is_retargeting"></span>is\_retargeting | Đang nhắm lại mục tiêu (chiến dịch) | URL lượt nhấp của tất cả các chiến dịch nhắm lại mục tiêu phải bao gồm `&is_retargeting=true`.  <br />Nếu tham số không được bao gồm hoặc có giá trị là "false" thì chiến dịch được coi là chiến dịch thu hút người dùng bình thường. | Enum 5 ký tự |
| <span id="af_reengagement_window"></span>af\_reengagement\_window | Thời gian tương tác lại | Thay đổi cửa sổ <Anchor target="_blank" href="/marketers/vi/docs/set-up-re-attribution-window#setting-the-re-attribution-window">thuộc tính thu hút lại</Anchor> bằng cách thêm tham số này vào liên kết phân bổ.<br /><br />Các tùy chọn khoảng thời gian có thể là:<ul><li>Ngày: 1-90 hoặc Giờ 1-36</li><li>Trọn đời: Điều này có nghĩa là khung thời gian thu hút lại không giới hạn. Ví dụ:`&af_reengloyment_window=lifetime`</li></ul>Giá trị mặc định: 30 ngày<br /><br />Ví dụ - `&af_reengagement_window=60d` đặt cửa sổ thu hút lại là 60 ngày. | Không áp dụng |

<div id="viewability-parameters" />

### Thông số loại quảng cáo

Tùy thuộc vào loại quảng cáo, bạn cũng có thể gửi tham số khả năng xem có liên quan nêu ra chi tiết các thông số kỹ thuật của mức độ tương tác. Dưới đây là danh sách các giá trị có thể cho “af\_ad\_type” cùng với các tham số khả năng xem dự kiến.

#### Loại quảng cáo (af\_ad\_type)

| Tham số | Định dạng giá trị | Mô tả |
| --- | --- | --- |
| <span id="af_video_total_length"></span>af\_video\_total\_length | giây | Tổng thời lượng có thể của video |
| <span id="af_video_played_length"></span>af\_video\_played\_length | giây | Video được xem trong bao lâu |
| <span id="af_playable_played_length"></span>af\_playable\_played\_length | giây | Thời gian thành phần có thể phát được phát sau khi được tải đầy đủ |
| <span id="af_ad_time_viewed"></span>af\_ad\_time\_viewed | giây | Đơn vị quảng cáo hiển thị trên màn hình trong bao lâu |
| <span id="af_ad_displayed_percent"></span>af\_ad\_displayed\_percent | % | Tỷ lệ phần trăm tối đa của đơn vị quảng cáo hiển thị trên màn hình thiết bị |
| <span id="af_audio_total_length"></span>af\_audio\_total\_length | giây | Tổng thời lượng có thể của âm thanh |
| <span id="af_audio_played_length"></span>af\_audio\_played\_length | giây | Âm thanh được nghe trong bao lâu |

<div id="android-specific-parameters" />

### Các tham số cụ thể cho Android

| Tham số | Hiển thị tên trong dữ liệu thô | Mô tả | Loại trường |
| --- | --- | --- | --- |
| <span id="advertising_id"></span>advertising\_id | Advertising ID | ID quảng cáo Google - Yêu cầu hỗ trợ mạng quảng cáo | Tối đa 40 ký tự |
| <span id="sha1_advertising_id"></span>sha1\_advertising\_id | Không áp dụng | ID quảng cáo Google biến đổi hash với SHA1 - Yêu cầu hỗ trợ mạng quảng cáo |  |
| <span id="md5_advertising_id"></span>md5\_advertising\_id | Không áp dụng | ID quảng cáo Google biến đổi hash với MD5 - Yêu cầu hỗ trợ mạng quảng cáo | Chỉ được hỗ trợ với lượt cài đặt và phân bổ lại |
| <span id="android_id"></span>android\_id | Android ID | Android\_id thiết bị - Yêu cầu hỗ trợ mạng quảng cáo | Tối đa 20 ký tự |
| <span id="sha1_android_id"></span>sha1\_android\_id | Không áp dụng | Android\_id thiết bị biến đổi hash với SHA1 - Yêu cầu hỗ trợ mạng quảng cáo |  |
| <span id="md5_android_id"></span>md5\_android\_id | Không áp dụng | Android\_id thiết bị được biến đổi hash với MD5 - Yêu cầu hỗ trợ mạng quảng cáo | Chỉ được hỗ trợ với lượt cài đặt và phân bổ lại |
| <span id="imei"></span>imei | IMEI | ID IMEI thiết bị |  |
| <span id="sha1_imei"></span>sha1\_imei | Không áp dụng | ID IMEI của thiết bị được biến đổi hash bằng SHA1 - Yêu cầu hỗ trợ mạng quảng cáo |  |
| <span id="md5_imei"></span>md5\_imei | Không áp dụng | ID IMEI của thiết bị được biến đổi hash bằng MD5 - Yêu cầu hỗ trợ mạng quảng cáo |  |
| <span id="oaid"></span>oaid | OAID | Mã định danh Thiết bị Ẩn danh Mở | Có sẵn kể từ phiên bản SDK Android 4.10.3 |
| <span id="sha1_oaid"></span>sha1\_oaid | Không áp dụng | Mã định danh Thiết bị Ẩn danh Mở được biến đổi hash bằng SHA1 - Yêu cầu hỗ trợ mạng quảng cáo | Có sẵn kể từ phiên bản SDK Android 4.10.3 |
| <span id="md5_oaid"></span>md5\_oaid | Không áp dụng | Mã định danh Thiết bị Ẩn danh Mở được biến đổi hash bằng MD5 - Yêu cầu hỗ trợ mạng quảng cáo | Có sẵn kể từ phiên bản SDK Android 4.10.3 |
| <span id="af_android_url"></span>af\_android\_url | Không áp dụng | Chuyển hướng người dùng Android đến một URL khác URL trên trang của ứng dụng trên Google Play. Sử dụng cho <Anchor target="_blank" href="/marketers/vi/docs/set-up-multi-store-android-attribution#bảng-điều-khiển-duy-nhất-so-với-bảng-điều-khiển-cho-mỗi-cửa-hàng">các cửa hàng ứng dụng của bên thứ ba</Anchor>.<br /><br />**Lưu ý**: Nếu bạn có <Anchor target="_blank" href="/marketers/vi/docs/set-up-your-api-allowlist#redirect-allowlists">Danh sách cho phép chuyển hướng</Anchor> đang hoạt động, hãy đảm bảo đưa miền của URL này vào danh sách. |  |
| <span id="sha1_el"></span>sha1\_el | Không áp dụng | Được sử dụng để phân bổ từ máy tính đến thiết bị di động - biến đổi hash email với SHA1. Yêu cầu hỗ trợ mạng quảng cáo |  |
| <span id="fire_advertising_id"></span>fire\_advertising\_id | Không áp dụng | ID Quảng cáo Amazon Fire |  |
| <span id="af_android_store_csl"></span>af\_android\_store\_csl | store\_product\_page | Trang thông tin tùy chỉnh trên Google Console | chuỗi |

<div id="ios-specific-parameters" />

### Các thông số cụ thể cho iOS

| Tham số | Tên hiển thị | Mô tả |
| --- | --- | --- |
| <span id="idfa"></span>idfa | IDFA | Sử dụng chữ hoa. Yêu cầu hỗ trợ mạng quảng cáo<br /><br />Loại trường: tối đa 40 ký tự |
| <span id="idfv"></span>idfv | IDFV | Sử dụng chữ hoa. |
| <span id="af_ios_url"></span>af\_ios\_url |  | Sử dụng thông số này để chuyển hướng trang đích nhằm chuyển hướng người dùng iOS (iPhone hoặc iPad) đến một URL khác với trang ứng dụng trên iTunes<br /><br />**Lưu ý**: Nếu bạn có <Anchor target="_blank" href="/marketers/vi/docs/set-up-your-api-allowlist#redirect-allowlists">Danh sách cho phép chuyển hướng</Anchor> đang hoạt động, hãy đảm bảo đưa miền của URL này vào danh sách. |
| <span id="af_ios_store_cpp"></span>af\_ios\_store\_cpp | store\_product\_page | ID trang sản phẩm tùy chỉnh (ppid) |
| <span id="af_ios_fallback--deprecated"></span>af\_ios\_fallback [không còn được hỗ trợ] | Không áp dụng | **Không còn được hỗ trợ**: Người dùng được chuyển hướng dựa trên <Anchor target="_blank" href="/marketers/vi/docs/uri-scheme-fallback-for-ios">luồng lược đồ URI iOS</Anchor>. |
| <span id="sha1_idfa"></span>sha1\_idfa | Không áp dụng | IDFA băm với SHA1. Yêu cầu hỗ trợ mạng quảng cáo |
| <span id="sha1_idfv"></span>sha1\_idfv | Không áp dụng | IDFV băm với SHA1 |
| <span id="mac"></span>mac | Không áp dụng | Địa chỉ mac của thiết bị. Yêu cầu hỗ trợ mạng quảng cáo |
| <span id="md5_idfv"></span>md5\_idfv | Không áp dụng | IDFV băm với MD5 |
| <span id="sha1_mac"></span>sha1\_mac | Không áp dụng | Địa chỉ mac của thiết bị biến đổi hash với SHA1. Yêu cầu hỗ trợ mạng quảng cáo |

<div id="example" />

> 📄 **Ví dụ**
>
> ```http
> https://app.appsflyer.com/{app_id}/?pid=airpush_int&c=RedBanner&
> 	  af_siteid={publisher_id}&af_sub1=1.5&af_sub2=USD&af_sub3=burst_campaign
> ```

Tất cả các thông số có sẵn trong <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">Báo cáo cài đặt</Anchor> và <Anchor target="_blank" href="/marketers/vi/docs/analytics-and-aggregate-reporting-apis">Phân tích, Báo cáo và API</Anchor>.

<div id="custom-parameters" />

### Thông số tùy chỉnh

Ngoài các thông số mặc định dành riêng cho Android và iOS, bạn cũng có thể chỉ định các thông số tùy chỉnh. Các thông số tùy chỉnh này có thể hữu ích cho bạn nếu bạn muốn tùy chỉnh trải nghiệm và nội dung của người dùng theo đường dẫn phân bổ dẫn đến lượt cài đặt.

Bạn có thể nối các thông số tùy chỉnh vào liên kết phân bổ ở định dạng `thông số=giá trị`. Ví dụ:

```http
https://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&af_adset=coats&af_ad=cashmere&my_custom_param=my_custom_value
```

Hai điều quan trọng cần biết về thông số tùy chỉnh:

* Thông số tùy chỉnh không xuất hiện trong dữ liệu thô.
* Có thể truy xuất thông số tùy chỉnh từ <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">API SDK nhận dữ liệu chuyển đổi</Anchor>.

<div id="partner-id-pid-parameter" />

<Accordion title="Thông số ID đối tác (PID)">

Trong số tất cả các thông số đường dẫn phân bổ có sẵn, PID là bắt buộc. PID là mã định danh duy nhất của nguồn truyền thông do AppsFlyer phân bổ.

Mỗi <Anchor target="_blank" href="http://appsflyer.com/partners">đối tác tích hợp</Anchor> đều có giá trị PID duy nhất của riêng họ. PID kết thúc bằng hậu tố *\_int*. Khi sử dụng <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">liên kết OneLink</Anchor>, bạn có thể đặt PID thành bất kỳ giá trị nào bạn muốn, miễn là chưa có đối tác tích hợp nào dùng giá trị này. **Để tránh xung đột, không sử dụng hậu tố *\_int***.

Ví dụ về các ID nhà phát hành tích hợp quan trọng: tự nhiên, googleadwords\_int (Google AdWords), quảng cáo Meta và Twitter. Bạn có thể sử dụng bất kỳ tên nào cho những nguồn không tích hợp, chẳng hạn như email, SMS hoặc bồ câu đưa thư.

<div id="avoid-common-pid-issues" />

#### Tránh các sự cố PID phổ biến:

* **Luôn đưa PID vào đường dẫn phân bổ của bạn.** Nếu không có PID trên đường dẫn phân bổ, người dùng được tự động phân bổ vào nguồn truyền thông "None" và nguồn cài đặt ban đầu biến mất.
* **Đối với các Nguồn Tùy chỉnh, hãy sử dụng PID của đối tác không tích hợp.** Đối với mỗi nguồn tích hợp, chỉ sử dụng PID được chỉ định để phân bổ chính xác lượt cài đặt. Đối với bất cứ nguồn truyền thông tùy chỉnh, chẳng hạn như email, SMS hoặc thậm chí là những bài đăng phổ biến không trả tiền trên Facebook, hãy sử dụng các giá trị PID không tích hợp khác.
* **Chỉ sử dụng các ký tự hợp lệ.** Nếu thông số PID trong Đường dẫn Phân bổ chứa một trong các ký tự sau /&lt;>*&?\
  * Lượt nhấp hoặc lượt cài đặt xuất hiện trong bảng điều khiển trong ***af\_invalid\_param***
  * Đường dẫn phân bổ sẽ không được phân bổ
  * Chức năng liên kết sâu sẽ không hoạt động đối với lượt nhấp

<div id="tip" />

> 👍 **Lời khuyên**
>
> Tránh sử dụng khoảng trắng trong giá trị PID hoặc đảm bảo URL mã hóa liên kết phân bổ của bạn trước khi sử dụng.

</Accordion>

<div id="site-id-parameter" />

<Accordion title="Thông số ID trang web">

ID trang web là mã định danh duy nhất của nhà phát hành phân phát quảng cáo. Nói cách khác, trang web hoặc ứng dụng hiển thị quảng cáo. Các mạng quảng cáo phân bổ ID trang web duy nhất cho từng nhà phát hành.

ID này được đưa vào thông số `af_siteid` được chuyển đến AppsFlyer trong đường dẫn phân bổ và được cung cấp thông qua các bảng điều khiển, tùy chọn báo cáo và đăng lại khác nhau.

ID trang web phải được chuyển đến AppsFlyer trong đường dẫn phân bổ vì ID này:

* Cho phép minh bạch và tăng tính rõ ràng về nhà phát hành
* Được AppsFlyer sử dụng để xác định và loại bỏ các nhà phát hành gian lận và các cụm lưu lượng truy cập khác.

Thông số ID trang web chỉ bao gồm ID của nhà phát hành phục vụ quảng cáo.

Để đưa vào thông tin bổ sung, chẳng hạn như loại quảng cáo, vị trí đặt hoặc cả hai trong ứng dụng, ví dụ như biểu ngữ, quảng cáo xen kẽ hoặc video, hãy sử dụng thông số ID trang phụ.

<div id="example-1" />

> 📄 **Ví dụ**
>
> Đường dẫn phân bổ sau đây bao gồm:
>
> * `af_siteid` (ID trang web): ID Nhà phát hành
> * `af_sub_siteid` (ID trang phụ): Thông tin ID bổ sung (trong trường hợp này là nguồn liên kết và vị trí đặt loại quảng cáo)
>
> `https://app.appsflyer.com/com.yourapp?pid=mediaName_int&clickid={clickid}&advertising_id={gaid}&af_siteid=1234&af_sub_siteid=ABCD_4567`
>
> Trong liên kết ví dụ:
>
> * 1234 = ID Nhà phát hành
> * ABCD = Nguồn liên kết (nhà phát hành phụ) mà nhà phát hành đang hợp tác làm việc
> * 4567 = Vị trí đặt loại quảng cáo trong ứng dụng, chẳng hạn như biểu ngữ, quảng cáo xen kẽ hoặc video

<div id="faq-why-does-traffic-result-in-many-blocked-installs" />

#### **Câu hỏi thường gặp: Tại sao lưu lượng truy cập dẫn đến nhiều lượt cài đặt bị chặn?**

Lượt cài đặt bị chặn có thể do những nguyên nhân sau:

* **Thiếu ID trang web:** Thông số `af_siteid` trống trong URL trang đích. Các lượt thu hút được gửi cùng ID Trang web trống biểu thị đã xảy ra sự cố kỹ thuật hoặc cố ý vượt qua các cơ chế phát hiện gian lận.
* **Nhiều ID trang web:** Cùng một nhà phát hành được gửi trên nhiều URL trang đích, sử dụng các ID trang web khác nhau. Đây được coi là hành vi gian lận che giấu hoạt động thực sự của nhà phát hành và thường liên quan đến <Anchor target="_blank" href="https://www.appsflyer.com/blog/click-flooding-detection-false-positive-challenge/">hành vi nhấp hàng loạt</Anchor>.
* **ID trang web được định dạng không chính xác:** Việc gửi sai định dạng, kết hợp với các dấu hiệu gian lận khác, có thể dẫn đến việc chặn không chỉ nhà phát hành cụ thể mà còn ở cấp độ cụm cao hơn và có thể ảnh hưởng đến khối lượng hoạt động lớn hơn của đối tác.

Để tránh lượt cài đặt bị chặn, hãy đảm bảo bạn gửi một thông số ID trang web cho mỗi nhà phát hành, như được minh họa trong ví dụ.

</Accordion>

<div id="levels-of-data-granularity" />

## Mức độ Chi tiết Dữ liệu

Bạn có thể sử dụng tối đa bốn thông số URL để tìm hiểu chi tiết hiệu suất quảng cáo.

Sử dụng tất cả 4 tham số trên tất cả liên kết phân bổ hoạt động cho phép bạn:

* Phân bổ tất cả lượt cài đặt và sự kiện của người dùng cho các quảng cáo cụ thể
* Truy cập sâu và so sánh hiệu suất của tất cả quảng cáo cho mỗi bộ quảng cáo, mỗi chiến dịch và mỗi nguồn truyền thông trên các báo cáo hợp nhất để tối ưu trên từng mức độ
* So sánh tất cả quảng cáo của bạn trong tất cả nguồn truyền thông trên các báo cáo dữ liệu thô và <Anchor target="_blank" href="/marketers/vi/docs/pivot-table-user-metrics">Bảng tổng hợp</Anchor>

Các tham số là:

* `Nguồn truyền thông (pid=)`
* `tên chiến dịch (c=)`
* `Bộ quảng cáo (af_adset=)`
* `Tên quảng cáo (af_ad=)`

<div id="example-2" />

> 📄 **Ví dụ**
>
> Các liên kết phân bổ sau đây sử dụng 4 mức độ chi tiết để ghi nhận quảng cáo "cashmere" trong bộ quảng cáo "áo khoác" trong chiến dịch "mùa đông" chạy trên nguồn truyền thông "networkx" tích hợp.
>
> ```http
> https://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&
> af_adset=coats&af_ad=cashmere
> ```

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Lưu ý |
| --- | --- |
| Ký tự đặc biệt | Dưới đây là các ký tự đặc biệt không được phép sử dụng trong các thông số hoặc giá trị: ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, &lt;, /, \{, \}, % |
| Giới hạn ký tự URL | Tổng chiều dài URL không được vượt quá 2000 ký tự |
| Các ứng dụng xã hội Android Chuyển hướng liên kết sâu trong chế độ WebView | Xem chi tiết giới hạn <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#android-social-apps-webview-deep-linking-redirection">tại đây</Anchor> |

</Accordion>

<div id="should-i-use-lower-or-upper-case-letters-for-parameters" />

<Accordion title="Tôi nên sử dụng chữ thường hay chữ hoa đối với các thông số">

Bạn có thể sử dụng một trong hai nhưng cần phải nhất quán. Nếu bạn đặt thông số tùy chỉnh gồm các ký tự chữ hoa hoặc chữ thường, hãy đảm bảo luôn sử dụng thông số đó.

Ví dụ, nếu bạn đặt pid=MyMediaSource, hãy đảm bảo luôn sử dụng thông số này. Nếu bạn sử dụng pid=MyMediaSource trên một đường dẫn phân bổ và pid=mymediasource trên một đường dẫn khác, có thể xảy ra sự khác biệt về dữ liệu. Điều tương tự cũng xảy ra với bất kỳ thông số nào khác mà bạn đặt trên đường dẫn phân bổ.

</Accordion>

<div id="is-the-appsflyer-attribution-link-dynamic-or-static" />

<Accordion title="Đường dẫn phân bổ của AppsFlyer là động hay tĩnh?">

Liên kết phân bổ của AppsFlyer không phải là trình theo dõi và có thể là động hoặc tĩnh.  
Làm thế nào để bạn biết một liên kết là động hay tĩnh?  
Nếu **liên kết phân bổ có chứa thông số**, đó là liên kết phân bổ đã xác định trước, vì vậy là liên kết **tĩnh**.  
**Chỉ các URL rút gọn** (ví dụ: `yourbrand.onelink.me/HaT8/r5c2b371`), được sử dụng cho các đường dẫn phân bổ tùy chỉnh, **là động**.  
Điều này có nghĩa là khi bạn bắt đầu sử dụng đường dẫn phân bổ cho đối tác được tích hợp hoặc URL đầy đủ cho truyền thông sở hữu, đường dẫn sẽ không thay đổi đối với bất kỳ khách hàng tiềm năng nào tương tác với nó, ngay cả khi bạn thay đổi giá trị đường dẫn phân bổ trên bảng điều khiển của AppsFlyer. Để thực hiện thay đổi, bạn phải sử dụng URL đầy đủ mới từ giờ về sau.  
Mặt khác, các URL rút gọn dùng cho truyền thông sở hữu, không trực tiếp chứa các thông số. Khi khách hàng tiềm năng tương tác với URL rút gọn của AppsFlyer, khách hàng tiềm năng được chuyển hướng đến AppsFlyer và các thông số cài đặt hiện tại diễn ra có tính động.

</Accordion>

<div id="what-is-this-play-store-error-message" />

<Accordion title="Thông báo lỗi trên Cửa hàng Play này là gì?">

Nếu bạn đã từng gặp thông báo lỗi sau trong Cửa hàng Play sau khi vào một liên kết phân bổ:

![TL_error_message.png](https://files.readme.io/03e509d3cbe68aa0621bb0f43ab113c25a8427e70826c5af5258f1fc9e3f3d36-360000002485.png)

Nguyên nhân là do liên kết phân bổ có chứa ký tự #. Ví dụ:

```http
https://app.appsflyer.com/com.travelco?pid=globalwide_int&clickid=#reqid#
```

Thông thường, các ký tự này nằm trong liên kết vì chúng là các macro và được thay thế động bằng một giá trị, do đó, đây không phải là một vấn đề lớn và bạn có thể bỏ qua thông báo.

</Accordion>

<div id="what-are-subscriber-parameters-good-for" />

<Accordion title="Tham số Người đăng ký có mục đích gì?">

Thông số Người đăng ký, nghĩa là af\_sub1, af\_sub2, ..., af\_sub\_5 có thể được sử dụng để ghi nhận bất kỳ KPI hữu ích nào. Các thông số này được phân tích và xuất hiện trong báo cáo dữ liệu thô, giúp chúng trở nên rất tiện dụng để thực hiện hợp nhất hoặc lọc dữ liệu.

<div id="example-3" />

> 📄 **Ví dụ**
>
> Một ứng dụng gọi xe, Luber, có quảng cáo với 3 mẫu màu: xanh lam, vàng và đỏ. Nhà marketing trên thiết bị di động của Luber muốn kiểm tra xem mẫu màu nào mang đến nhiều lượt cài đặt hơn. Để kiểm tra, cô ấy thêm `&af_sub3=blue` vào liên kết phân bổ của tất cả quảng cáo màu xanh trong TẤT CẢ nguồn truyền thông không phải SRN. Cách tương tự được thực hiện với quảng cáo màu vàng và đỏ. Khi thông tin này được phân tích và xuất hiện trong các báo cáo dữ liệu thô, Linda có thể phân tích thành công của các quảng cáo có màu khác nhau và chọn quảng cáo chuyển đổi tốt nhất.

</Accordion>

<div id="what-limits-are-there-on-campaign-names" />

<Accordion title="Có các giới hạn nào về tên chiến dịch?">

* Độ dài tối đa của tên chiến dịch trong URL liên kết phân bổ là 100 ký tự. Nếu vượt quá, tên chiến dịch được đổi thành: `c_name_exceeded_max_length`
* Tên chiến dịch không nên bắt đầu hoặc kết thúc bằng dấu cách, vì có thể gây ra sai khác trong bảng điều khiển và báo cáo

</Accordion>

<div data-zendesk-anchors="overview=t%E1%BB%95ng-quan 01H8GN1XXC5T2ENFHBK0G4WQ1P=t%E1%BB%95ng-quan attribution-link-parameters=th%C3%B4ng-s%E1%BB%91-%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95 01H8GN1XXDX1XMQ1GJTHCP425D=th%C3%B4ng-s%E1%BB%91-%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95 attribution-link-parameters%E2%80%94ua-and-retargeting=th%C3%B4ng-s%E1%BB%91-%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95ua-v%C3%A0-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i 01H8GN1XXDEWPB2MPP3KJVPRJV=th%C3%B4ng-s%E1%BB%91-%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95ua-v%C3%A0-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i af_sub%5Bn%5D%C2%A0%0An15-example-af_sub1=af_sub-n-n15-example-af_sub1 %5Bdeprecated%5D-af_os=deprecated--af_os attribution-link-parameters%E2%80%94retargeting-only=th%C3%B4ng-s%E1%BB%91-%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95ch%E1%BB%89-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i 01H8GN1XXD9X7CWZJN43PSS94R=th%C3%B4ng-s%E1%BB%91-%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95ch%E1%BB%89-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i ad-type-parameters=th%C3%B4ng-s%E1%BB%91-lo%E1%BA%A1i-qu%E1%BA%A3ng-c%C3%A1o 01H8GN1XXETQEYT39F05ZYX4E2=th%C3%B4ng-s%E1%BB%91-lo%E1%BA%A1i-qu%E1%BA%A3ng-c%C3%A1o ad-type-af_ad_type=lo%E1%BA%A1i-qu%E1%BA%A3ng-c%C3%A1o-af_ad_type 01H8GN1XXEPEZ53C3XFB601838=lo%E1%BA%A1i-qu%E1%BA%A3ng-c%C3%A1o-af_ad_type androidspecific-parameters=c%C3%A1c-tham-s%E1%BB%91-c%E1%BB%A5-th%E1%BB%83-cho-android 01H8GN1XXEE9RGSB1H72H025Z4=c%C3%A1c-tham-s%E1%BB%91-c%E1%BB%A5-th%E1%BB%83-cho-android iosspecific-parameters=c%C3%A1c-th%C3%B4ng-s%E1%BB%91-c%E1%BB%A5-th%E1%BB%83-cho-ios 01H8GN1XXESJ9VE3W8CYKRFFYX=c%C3%A1c-th%C3%B4ng-s%E1%BB%91-c%E1%BB%A5-th%E1%BB%83-cho-ios af_ios_fallback-%5Bdeprecated%5D=af_ios_fallback--deprecated 01H8GN1XXEFRSQSERTB6ARC773=v%C3%AD-d%E1%BB%A5 custom-parameters=th%C3%B4ng-s%E1%BB%91-t%C3%B9y-ch%E1%BB%89nh 01H8GN1XXEB58JN4SV9HX1ZV6S=th%C3%B4ng-s%E1%BB%91-t%C3%B9y-ch%E1%BB%89nh 01H8GN1XXE8EXMMKDZMJ2WNNH5=partner-id-pid-parameter avoid-common-pid-issues=tr%C3%A1nh-c%C3%A1c-s%E1%BB%B1-c%E1%BB%91-pid-ph%E1%BB%95-bi%E1%BA%BFn 01H8GN1XXEXTGC4M8AMJ256Q9G=tr%C3%A1nh-c%C3%A1c-s%E1%BB%B1-c%E1%BB%91-pid-ph%E1%BB%95-bi%E1%BA%BFn 01H8GN1XXEGNVX9GM5JYBMBGCF=l%E1%BB%9Di-khuy%C3%AAn 01H8GN1XXEVG65YP782CM37RES=site-id-parameter 01H8GN1XXED2MVSNRXN11KZ955=v%C3%AD-d%E1%BB%A5-1 faq-why-does-traffic-result-in-many-blocked-installs=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-t%E1%BA%A1i-sao-l%C6%B0u-l%C6%B0%E1%BB%A3ng-truy-c%E1%BA%ADp-d%E1%BA%ABn-%C4%91%E1%BA%BFn-nhi%E1%BB%81u-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-b%E1%BB%8B-ch%E1%BA%B7n 01H8GN1XXEK0G9TDW8WHWM17HK=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-t%E1%BA%A1i-sao-l%C6%B0u-l%C6%B0%E1%BB%A3ng-truy-c%E1%BA%ADp-d%E1%BA%ABn-%C4%91%E1%BA%BFn-nhi%E1%BB%81u-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-b%E1%BB%8B-ch%E1%BA%B7n levels-of-data-granularity=m%E1%BB%A9c-%C4%91%E1%BB%99-chi-ti%E1%BA%BFt-d%E1%BB%AF-li%E1%BB%87u 01H8GN1XXE4RF9J0APAAKD1WEG=m%E1%BB%A9c-%C4%91%E1%BB%99-chi-ti%E1%BA%BFt-d%E1%BB%AF-li%E1%BB%87u 01H8GN1XXEHPFKX7V0RRW2MH2G=v%C3%AD-d%E1%BB%A5-2 01H8GN1XXEBTW3XRGNZ3A8ZZJP=traits-and-limitations 01H8GN1XXEND9X8YVRQE1YFA5W=should-i-use-lower-or-upper-case-letters-for-parameters 01H8GN1XXER749PH4Z14A7AJ0F=is-the-appsflyer-attribution-link-dynamic-or-static 01H8GN1XXEPQTY0XNW6EZSA9ZN=what-is-this-play-store-error-message 01H8GN1XXFYAFYFX9MNBP6D35B=what-are-subscriber-parameters-good-for 01H8GN1XXFEFA498J22GRF5F8G=v%C3%AD-d%E1%BB%A5-3 01H8GN1XXFS1DFS3HAHVTVG93A=what-limits-are-there-on-campaign-names" />
