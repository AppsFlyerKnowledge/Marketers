---
title: Hướng dẫn cài đặt Twitter Ads—Câu hỏi thường gặp và các khác biệt
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
  created_at: '2021-11-09T09:34:59Z'
  edited_at: '2023-11-09T05:06:48Z'
  id: 4410464352017
  locale: vi
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/vi/articles/4410464352017
---
> **Sơ lược:** Giải quyết các Câu hỏi thường gặp về Twitter Ads và tìm hiểu những khác biệt.

## Câu hỏi thường gặp về Twitter Ads và sự khác biệt

<div id="who-can-perform-the-twitter-setup-on-appsflyer" />

<Accordion title="Ai có thể chỉnh thiết lập Twitter trên AppsFlyer?">

Người dùng ủy quyền tích hợp giữa AppsFlyer  và Twitter phải có quyền truy cập Quản trị viên Tài khoản Twitter.

</Accordion>

<div id="what-happens-if-no-twitter-accounts-are-selected-for-attributing-on-appsflyer" />

<Accordion title="Điều gì sẽ xảy ra nếu không có tài khoản Twitter nào được chọn để phân bổ trên AppsFlyer?">

Tất cả các thuộc tính đều dành cho các chiến dịch trên tài khoản đã chọn. Nếu không có tài khoản nào được chọn, không có sự kiện hoặc hoạt động nào trong ứng dụng được gửi tới Twitter, ngay cả khi sự kiện vẫn hiển thị trên cửa sổ Cấu hình Twitter.

</Accordion>

<div id="do-the-account-owner-and-the-team-members-see-the-same-twitter-data" />

<Accordion title="Chủ sở hữu tài khoản và các thành viên trong nhóm có thấy cùng một dữ liệu Twitter không?">

Không. Chủ sở hữu tài khoản sẽ thấy tất cả các tài khoản Twitter đã kết nối. Thành viên nhóm chỉ thấy các tài khoản Twitter kết nối của họ.

</Accordion>

<div id="how-do-i-disconnect-twitter-from-appsflyer" />

<Accordion title="Làm cách nào để ngắt kết nối Twitter khỏi AppsFlyer?">

Bạn có thể ngắt kết nối AppsFlyer khỏi tài khoản Twitter. Các hướng dẫn sau đây giả định rằng bạn đã đăng nhập vào tài khoản Twitter của mình bằng trình duyệt máy tính để bàn hoặc máy tính xách tay:

1. Đăng nhập vào Twitter.
2. Trên menu bên trái, nhấp vào **More** > **Settings and Privacy**.
3. Đi đến **Security and account access** > **Apps and sessions** > **Connected apps**.
4. Nhấp vào AppsFlyer.
5. Nhấp vào **Revoke Access** (Hủy Quyền truy cập).

Bây giờ, bạn có thể quay lại tài khoản AppsFlyer và <Anchor target="_blank" href="/marketers/vi/docs/x-ads-formerly-twitter-ads-integration-setup">kết nối một tài khoản Twitter khác</Anchor> nếu muốn.

</Accordion>

<div id="is-it-possible-to-attribute-installs-to-multiple-twitter-accounts" />

<Accordion title="Có thể phân bổ lượt cài đặt cho nhiều tài khoản Twitter không?">

Có, nhưng điều này đòi hỏi một số hành động từ phía Twitter. Nhưng trước tiên, cần có một số nền:

Bạn có thể kết nối **chỉ một tên tài khoản** (còn được gọi là người dùng twitter) với tài khoản AppsFlyer của mình. Khi bạn kết nối tên tài khoản này, Tài khoản quảng cáo Twitter của bạn sẽ xuất hiện trong cấu hình Twitter trong bảng điều khiển AppsFlyer.

Nếu một thành viên nhóm cũng có Tài khoản quảng cáo Twitter, điều này có nghĩa là họ có tên tài khoản khác với của bạn và không thể kết nối tên tài khoản của họ với AppsFlyer. Điều này là bởi **tên tài khoản bạn đã kết nối với tài khoản AppsFlyer rồi**. Để Tài khoản quảng cáo Twitter của họ cũng xuất hiện trong AppsFlyer, họ cần **cho tên tài khoản của bạn quyền truy cập với tư cách quản trị viên tài khoản vào Tài khoản quảng cáo Twitter của họ**.

Giả sử tên thành viên nhóm của bạn là Jenny và tên tài khoản của cô ấy là @jenny. Tên tài khoản của bạn là @nivi và đây là tên tài khoản được kết nối với AppsFlyer. Để Tài khoản quảng cáo Twitter của Jenny xuất hiện trong tài khoản AppsFlyer, **cô ấy cần cho tên tài khoản của bạn quyền truy cập với tư cách quản trị viên tài khoản vào Tài khoản quảng cáo Twitter của mình**. Jenny cần cấp quyền truy cập cho Nivi vào Tài khoản quảng cáo Twitter của cô ấy chứ không phải theo cách khác. Khi cô làm như vậy, AppsFlyer nhìn vào tên tài khoản của Nivi và thấy tất cả các tài khoản quảng cáo được liên kết với tài khoản đó, bao gồm cả tài khoản của Jenny.

1. Jenny đăng nhập vào <Anchor target="_blank" href="http://ads.twitter.com/">ads.twitter.com</Anchor>
2. Cô nhấp vào **Account** rồi chọn **Edit access to account**  

   ![twitter_assign_account2.PNG](https://support.appsflyer.com/hc/article_attachments/4416810336785)
3. Sau đó, Jenny cấp quyền truy cập cho @nivi vào Tài khoản Twitter Ads của mình với tư cách là Quản trị viên tài khoản  

   [![twitter_edit_access_to_account.png](https://support.appsflyer.com/hc/article_attachments/4416810307601/twitter_edit_access_to_account.png)](https://support.appsflyer.com/hc/article_attachments/360002514658/twitter_edit_access_to_account.png)
4. Jenny đăng nhập vào tài khoản AppsFlyer và đi tới tùy chọn Active Integrations >> Twitter
5. Ở bước này, cô có thể thấy Tài khoản quảng cáo Twitter của mình cũng được liệt kê.
6. Giờ cô có thể thấy tài khoản Quảng cáo Twitter của mình và cấu hình tích hợp. Quản trị viên tài khoản có thể thấy tất cả các tài khoản Quảng cáo Twitter được kết nối.  

   Jenny nhìn thấy:

   ![jennys_ads_account.png](https://support.appsflyer.com/hc/article_attachments/4416824257041)

   Quản trị viên tài khoản nhìn thấy:

   ![jennys_ads_account__1_.png](https://support.appsflyer.com/hc/article_attachments/4416833416337)

</Accordion>

<div id="any-special-instructions-for-agencies" />

<Accordion title="Có hướng dẫn đặc biệt nào cho Agencies không?">

Yes.   
Khi Agency tạo chiến dịch Twitter mới, tên chiến dịch phải bắt đầu bằng tên đại lý và dấu gạch dưới (Ví dụ: "AgencyName\_Campaign1").

> 📘 **Lưu ý**
>
> Để thiết lập kết nối giữa AppsFlyer và Twitter, nhà quảng cáo PHẢI định cấu hình Twitter để cho phép các đại lý chạy lưu lượng truy cập Twitter.

Để biết thêm chi tiết, hãy truy cập <Anchor target="_blank" href="/partners/vi/docs/about-agency-accounts#cấu-hình-srn">tại đây</Anchor>.

</Accordion>

<div id="do-you-make-twitters-raw-data-available-to-agencies" />

<Accordion title="Bạn có cung cấp dữ liệu thô Twitter cho các đại lý không?">

Chúng tôi không cung cấp dữ liệu thô của Twitter cho các đại lý vì điều khoản dịch vụ của Twitter coi các đại lý là bên thứ ba.

</Accordion>

<div id="im-clicking-save-close-but-twitters-configuration-is-not-saved-help" />

<Accordion title="Tôi đã nhấp vào Lưu & Đóng nhưng cấu hình của Twitter không được lưu! Trợ giúp!">

Nếu ứng dụng của bạn đã từng được đăng ký với một nhà cung cấp phân bổ khác để phân bổ lượt cài đặt Twitter, các lỗi sau đây có thể xuất hiện khi định cấu hình Twitter trên trang tổng quan của AppsFlyer:

**Lỗi:  Ứng dụng được liên kết với một nhà cung cấp phân bổ khác. Vui lòng liên kết ứng dụng với AppsFlyer.**

Ngoài ra, các lỗi sau cũng có thể xuất hiện:  

 [![](https://support.appsflyer.com/hc/article_attachments/360001502209/Twitter_error_2.png)](https://support.appsflyer.com/hc/article_attachments/360001502209/Twitter_error_2.png)

**Lỗi:  Đã xảy ra lỗi trong khi lưu cấu hình Twitter.  Không thể cập nhật một số tài khoản:  XX Nhiều ID nhà cung cấp giống nhau (appid, conversionType) cho sự kiện appid2872.**

Nếu lựa chọn tài khoản không được lưu, có thể tài khoản Twitter liên quan trước đây được liên kết với một nhà cung cấp khác ở điểm cuối của Twitter. Để giải quyết vấn đề này:

* Liên hệ với Twitter để xóa các nhà cung cấp khác khỏi điểm cuối của bạn
* Chọn tên Tài khoản Đang hoạt động
* Nhấp vào **Lưu và Đóng**.
* Nếu thao tác này vẫn không giải quyết được vấn đề, bạn sẽ phải liên hệ với nhà cung cấp đo lường trước đây và yêu cầu xóa các thẻ Twitter cũ được liên kết với tài khoản của bạn.

</Accordion>

<div id="how-can-i-set-up-retargeting-campaigns-with-twitter" />

<Accordion title="Tôi có thể thiết lập chiến dịch tái mục tiêu với Twitter bằng cách nào?">

Để biết chi tiết về cách thiết lập cấu hình chiến dịch tái mục tiêu lại trên Twitter, hãy nhấp vào đây.

</Accordion>

<div id="does-retargeting-affect-inapp-events-sending-to-twitter" />

<Accordion title="Việc nhắm mục tiêu lại có ảnh hưởng đến các sự kiện trong ứng dụng gửi tới Twitter không?">

Yes. Nếu tính năng retargeting được bật, AppsFlyer sẽ không gửi các postback sự kiện post\_app\_opened về cho Twitter, theo yêu cầu của Twitter.   
 Lưu ý rằng ngay cả khi cửa sổ thiết lập Twitter cho phép lựa chọn này, các postback af\_app\_opened không được gửi kèm theo thiết lập retargeting.

</Accordion>

<div id="how-can-i-stop-measuring-twitter-attributions" />

<Accordion title="Tôi có thể bỏ đo lường phân bổ Twitter bằng cách nào?">

Để hủy tích hợp với Twitter, hãy bỏ chọn tất cả các tài khoản và nhấp vào **Lưu & Đóng**.

</Accordion>

<div id="can-an-agency-measure-twitter-attributions-for-advertisers" />

<Accordion title="Đại lý có thể đo lường phân bổ Twitter cho nhà quảng cáo không?">

Yes!  
 Để thiết lập kết nối giữa AppsFlyer và Twitter, nhà quảng cáo PHẢI chọn một tài khoản đang hoạt động trong trang đối tác của Twitter trong bảng điều khiển AppsFlyer, do đó, ít nhất một tài khoản Twitter phải được chọn.  
 Sau đó, agency cần kết nối tài khoản Twitter của mình trực tiếp từ bảng điều khiển của chính agency đó.

</Accordion>

<div id="can-an-agency-configure-inapp-events-for-twitter" />

<Accordion title="Agency có thể định cấu hình sự kiện trong ứng dụng cho Twitter không?">

Các đại lý không thể định cấu hình các sự kiện trong ứng dụng cho Twitter.  Tương tự như Meta ads, những quảng cáo này phải được Nhà quảng cáo định cấu hình.

</Accordion>

<div id="for-how-long-do-you-keep-twitter-s-userlevel-data" />

<Accordion title="Bạn giữ dữ liệu cấp độ người dùng của Twitter trong bao lâu?">

Twitter yêu cầu nhà cung cấp phân bổ xóa dữ liệu cấp người dùng 3 tháng sau khi cài đặt. Điều này có nghĩa là các sự kiện được thực hiện bởi những người dùng này 3 tháng sau khi họ cài đặt ứng dụng được tính là không phải trả tiền.

Dữ liệu tổng hợp trong quá khứ vẫn giữ nguyên.

</Accordion>

<div id="why-do-i-see-duplicated-cost-data" />

<Accordion title="Tại sao tôi thấy dữ liệu chi phí trùng lặp?">

Khi bạn thiết lập chiến dịch trên Twitter, bạn có thể thêm nhiều ứng dụng vào chiến dịch. Khi Twitter báo cáo chi phí, dữ liệu tổng chi phí chiến dịch hiển thị trong mỗi ứng dụng trong AppsFlyer và không được chia cho mỗi ứng dụng.

Ví dụ: nếu bạn chạy một chiến dịch có chi phí 1.000 đô la cho cả ứng dụng Android và iOS, thì chi phí 1.000 đô la sẽ hiển thị trong bảng điều khiển của AppsFlyer trong cả ứng dụng Android và iOS. Chi phí không được chia nhỏ, ví dụ như thành 500 đô la mỗi mục.

Để tránh trùng lặp chi phí, bạn chỉ nên xác định một ứng dụng cho mỗi mục hàng/chiến dịch.

</Accordion>

<div id="im-trying-to-link-my-twitter-account-with-appsflyer-but-i-get-an-error-message" />

<Accordion title="Tôi đang cố liên kết tài khoản Twitter của mình với AppsFlyer, nhưng nhận được thông báo lỗi">

Để nhận dữ liệu phân bổ từ AppsFlyer, tài khoản Twitter của bạn phải là một Tài khoản Quảng cáo đang hoạt động.

**Để giải quyết vấn đề này:**

1. Đăng xuất khỏi Twitter.
2. Đi đến **Active Integrations**.
3. trong **Trường Tìm kiếm,** nhập "Twitter"
4. Nhấp vào biểu tượng Twitter,   
   cửa sổ thiết lập đối tác sẽ mở ra.
5. Trong tab **Integration** (Tích hợp), nhấp vào **Activate partner** (Kích hoạt đối tác).
6. Nhấp vào **Login with Twitter** (Đăng nhập bằng Twitter),   
   cửa sổ đăng nhập Twitter sẽ mở ra.
7. Đăng nhập bằng Tài khoản Quảng cáo Twitter của bạn.

</Accordion>

## Sự khác biệt giữa Twitter và AppsFlyer

Mặc dù chúng tôi hợp tác chặt chẽ với Twitter, sự khác biệt có thể xuất hiện giữa bảng điều khiển Twitter và bảng điều khiển/báo cáo AppsFlyer.

Đây là những lý do phổ biến cho những khác biệt đó mà các nhà quảng cáo nên biết:

| Nguyên nhân | Twitter | AppsFlyer |
| --- | --- | --- |
| **Cửa sổ Phân bổ** | Twitter cho phép người dùng của mình định cấu hình cửa sổ phân bổ và hỗ trợ cả phân bổ nhấp chuột qua và xem qua. Theo mặc định - nhấp chuột qua là 14 ngày và xem qua là 1 ngày. | Nếu bạn chưa định cấu hình khoảng thời gian xem lại phân bổ AppsFlyer cho Twitter với cùng các giá trị như trong Twitter, sự khác biệt có thể xảy ra. |
| **Phân bổ Nguồn đa kênh** | Phân bổ của Twitter hoạt động như được chỉ định ở trên bất kể các nguồn khác. | AppsFlyer sử dụng phân bổ nhấp chuột cuối cùng (thông tin thêm về phân bổ AppsFlyer có sẵn <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model">tại đây</Anchor>) |
| **Sự khác biệt múi giờ** | Múi giờ của Twitter được xác định bởi múi giờ được định cấu hình của ứng dụng quảng cáo. | Múi giờ mặc định của AppsFlyer là UTC±00:00, nhưng nhà quảng cáo có thể đặt thành bất kỳ múi giờ nào. |
| **Cài đặt chênh lệch thời gian** | Twitter hiển thị các lượt cài đặt dựa trên thời gian nhấp chuột (được gọi là "thời gian tương tác"). | AppsFlyer hiển thị thời gian mở ứng dụng lần đầu. |
| **Loại tiếp xúc được phân bổ** | Phân bổ của Twitter dựa trên các lượt nhấp chuột và lượt hiển thị của riêng họ. | AppsFlyer ưu tiên phân bổ nhấp qua hơn phân bổ xem qua. Nếu Twitter đếm số lần hiển thị và AppsFlyer biết về một nhấp chuột bổ sung trong khoảng thời gian phân bổ nhấp qua, thì lượt nhấp chuột từ một nguồn khác được phân bổ cho bảng điều khiển của AppsFlyer. Trên Twitter, lượt hiển thị được phân bổ và được nhìn thấy trên bảng điều khiển. |
| **Cài đặt chia sẻ dữ liệu Twitter** | Twitter cho phép người dùng KHÔNG<Anchor target="_blank" href="https://twitter.com/settings/account/personalization">chia sẻ dữ liệu cá nhân của họ với bên thứ ba</Anchor>. Dữ liệu này bao gồm quảng cáo mà họ tương tác.<br /><br />Số liệu thống kê trên bảng điều khiển Twitter phản ánh tất cả các lượt tương tác, bao gồm cả người dùng đã chọn không chia sẻ dữ liệu. | AppsFlyer hiển thị dữ liệu tổng hợp của những người dùng Twitter này, nhưng không báo cáo dữ liệu thô ở cấp độ người dùng của họ (xem thêm <Anchor target="_blank" href="/marketers/vi/docs/x-ads-formerly-twitter-ads-setup-guide-overview#quyền-riêng-tư-của-người-dùng-x-ads">chi tiết</Anchor>). |
| **Logic thu hút lại trên Twitter** | Twitter tính người dùng duy nhất. Nếu người dùng thu hút lại nhiều lần do cùng một chiến dịch, Twitter sẽ hiển thị những tương tác thu hút này dưới dạng một lượt chuyển đổi. | AppsFlyer tính từng trường hợp thu hút lại và do đó, trong trường hợp tương tự, hiển thị những tương tác thu hút này dưới dạng nhiều lượt chuyển đổi. |

> 📘 **Lưu ý**
>
> Do <Anchor target="_blank" href="/marketers/vi/docs/implement-validation-rules-to-prevent-fraud">Quy tắc xác thực</Anchor> của AppsFlyer, các kết quả có thể khác nhau trong bảng điều khiển vì một số cài đặt được hiển thị trong Twitter và không được hiển thị trong bảng điều khiển AppsFlyer.

<div data-zendesk-anchors="twitter-ads-faq-and-discrepancies=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-twitter-ads-v%C3%A0-s%E1%BB%B1-kh%C3%A1c-bi%E1%BB%87t h_01HE7S15F9YR28FBA1TYCE3N0X=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-twitter-ads-v%C3%A0-s%E1%BB%B1-kh%C3%A1c-bi%E1%BB%87t h_01HE7S15F9NSQJSP268B0WF0JP=who-can-perform-the-twitter-setup-on-appsflyer h_01HE7S15F9PFZ8CATJC5YWC6QP=what-happens-if-no-twitter-accounts-are-selected-for-attributing-on-appsflyer h_01HE7S15F989Y94YFJ7TGK7QN5=do-the-account-owner-and-the-team-members-see-the-same-twitter-data h_01HE7S15F9GNWTK2N50GAHN52Q=how-do-i-disconnect-twitter-from-appsflyer h_01HE7S15F9CE4F29R97EVCG791=is-it-possible-to-attribute-installs-to-multiple-twitter-accounts h_01HE7S15F9G4M44CB2Q1KQMJPJ=any-special-instructions-for-agencies h_01HE7S15F9VG8XMJE7YSNN245P=l%C6%B0u-%C3%BD h_01HE7S15F9A7BBAW8BNN6H4AKQ=do-you-make-twitters-raw-data-available-to-agencies h_01HE7S15F9MM26SGKMAPGDH9F8=im-clicking-save-close-but-twitters-configuration-is-not-saved-help h_01HE7S15F923NKTTCS3Z1C40B5=how-can-i-set-up-retargeting-campaigns-with-twitter h_01HE7S15F931EWS48QVCQYPBCH=does-retargeting-affect-inapp-events-sending-to-twitter h_01HE7S15F98VN1TS99751S34C5=how-can-i-stop-measuring-twitter-attributions h_01HE7S15F9MEKBKAQ3NA76TFKY=can-an-agency-measure-twitter-attributions-for-advertisers h_01HE7S15F921V3T885F39VSPCQ=can-an-agency-configure-inapp-events-for-twitter for-how-long-do-you-keep-twitter%E2%80%99s-userlevel-data=for-how-long-do-you-keep-twitter-s-userlevel-data h_01HE7S15F90RXSWJ7HV3GSJB65=for-how-long-do-you-keep-twitter-s-userlevel-data h_01HE7S15F9B39KV628NSD29P6P=why-do-i-see-duplicated-cost-data h_01HE7S15F9N3CCJEMAD2QB38F9=im-trying-to-link-my-twitter-account-with-appsflyer-but-i-get-an-error-message discrepancies-between-twitter-and-appsflyer=s%E1%BB%B1-kh%C3%A1c-bi%E1%BB%87t-gi%E1%BB%AFa-twitter-v%C3%A0-appsflyer h_01HE7S15F9YWCY883DP9TEGQXK=s%E1%BB%B1-kh%C3%A1c-bi%E1%BB%87t-gi%E1%BB%AFa-twitter-v%C3%A0-appsflyer h_01HE7S15FAPS2696J3KQG3P3ME=l%C6%B0u-%C3%BD-1" />
