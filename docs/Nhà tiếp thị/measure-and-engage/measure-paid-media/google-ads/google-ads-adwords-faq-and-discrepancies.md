---
title: Google Ads (AdWords)—Câu hỏi thường gặp và các khác biệt
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
  created_at: '2022-01-20T10:06:31Z'
  edited_at: '2023-11-17T02:10:05Z'
  id: 4417303339921
  locale: vi
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/vi/articles/4417303339921
---
> **Tổng quan:** Khắc phục sự cố thường gặp và sự khác biệt liên quan đến Google Ads.

## Câu hỏi thường gặp về Google Ads

<div id="why-am-i-not-seeing-clicks-from-google-ads" />

<Accordion title="Tại sao tôi không thấy các lượt nhấp chuột từ Quảng cáo Google?">

Dữ liệu lượt nhấp và lượt hiển thị hợp nhất từ Google Ads được thu thập khi bạn có tập hợp <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">chi phí, lượt nhấp và lượt hiển thị được xác thực</Anchor> trong tab **Cost**.

Dữ liệu nhấp chuột và hiển thị từ Google Ads đã được cung cấp trong tháng 8 năm 2018, đầu tiên cho các ứng dụng Android và sau đó cho các ứng dụng iOS. Do đó, khi phân tích dữ liệu nhấp chuột từ năm 2018 trở về trước, dữ liệu nhấp chuột của Google Ads có thể bị thiếu hoặc không đầy đủ.

</Accordion>

<div id="why-am-i-not-seeing-first_open-conversions-on-google-ads" />

<Accordion title="Tại sao tôi không thấy lượt chuyển đổi first_open trên Google Ads">

Nếu bạn không thấy lượt chuyển đổi first\_open trên Google Ads như được minh họa trong ảnh chụp màn hình bên dưới:

![AW_13.png](https://support.appsflyer.com/hc/article_attachments/4417310093457)  

điều đó có nghĩa là bạn cần nhập lượt chuyển đổi vào Google Ads. Thực hiện theo hướng dẫn về <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">nhập lượt chuyển đổi</Anchor>.

</Accordion>

<div id="why-cant-i-see-inapp-events-on-google-ads" />

<Accordion title="Tại sao tôi không thấy các sự kiện trong ứng dụng trên Quảng cáo Google?">

Bạn có thấy màn hình này trên Google Ads sau khi ánh xạ các sự kiện trong ứng dụng ưa thích của bạn trên bảng điều khiển của AppsFlyer (<Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-integration-setup-for-advertisers#step-3-map-your-inapp-events-recommended">bước cấu hình 3</Anchor>) không?

[![adwords missing events 2.png](https://support.appsflyer.com/hc/article_attachments/18726174138001)](https://support.appsflyer.com/hc/article_attachments/18726174138001)  

Nếu vậy, hãy thực hiện một trong những thao tác sau:

* Nếu tùy chọn gửi cho các sự kiện trong ứng dụng được đặt thành "This partner only" (Chỉ đối tác này), hãy đảm bảo phân bổ lượt cài đặt trên thiết bị của bạn cho Google, sau đó thực hiện các sự kiện trên thiết bị.
* Thay đổi <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-integration-setup-for-advertisers#step-3-map-your-inapp-events-recommended">tùy chọn gửi</Anchor> cho các sự kiện thành "All media sources, including organic" (Tất cả các nguồn truyền thông, bao gồm cả tự nhiên), rồi triển khai các sự kiện trên thiết bị của bạn.

> 🚧 **Quan trọng!**
>
> * Đảm bảo ánh xạ các sự kiện trong ứng dụng trước khi thực hiện trên thiết bị của bạn.
> * Có thể mất tới 6 giờ để các sự kiện hiển thị trên bảng điều khiển của Google Ads.

</Accordion>

<div id="can-i-stop-google-cost-sync" />

<Accordion title="Tôi có thể dừng đồng bộ hóa chi phí Google không?">

Để ngừng đồng bộ hóa chi phí với Google:

1. Đi tới <Anchor target="_blank" href="https://myaccount.google.com/permissions">Quyền tài khoản Google</Anchor> của bạn.
2. Nhấp vào Remove bên cạnh AppsFlyer Google Cost.  

   ![remove_appsflyer_cost.png](https://support.appsflyer.com/hc/article_attachments/4417304127249)

</Accordion>

<div id="do-i-need-to-create-and-then-import-session_start" />

<Accordion title="Tôi có cần tạo và sau đó nhập session_start không?">

Điều này phụ thuộc vào loại chiến dịch bạn đang chạy. Nếu bạn đang chạy một chiến dịch tương tác lại thì nên tạo và nhập `session_start` để đo mức độ tương tác.

Đối với một chiến dịch thu hút người dùng, điều này không bắt buộc.

</Accordion>

<div id="can-i-send-uninstall-information-to-google-ads" />

<Accordion title="Tôi có thể gửi thông tin gỡ cài đặt cho Google Ads không?">

Có.  
 **Để bắt đầu gửi các sự kiện gỡ cài đặt tới Google:**

1. Ánh xạ sự kiện af\_uninstall dưới dạng sự kiện Tùy chỉnh trong cửa sổ thiết lập Google Ads.
2. Nhập lượt chuyển đổi đó trong Google.
3. Google ghi nhận các sự kiện nếu nhận được trong khung thời gian phân bổ của Google (bắt đầu bằng việc thu hút quảng cáo và kéo dài 30-90 ngày). Các sự kiện mà Google nhận được sau khi khung thời gian này kết thúc không được ghi nhận trong Google.

</Accordion>

<div id="what-google-ads-data-does-appsflyer-display" />

<Accordion title="AppsFlyer hiển thị những dữ liệu Google Ads nào?">

Bạn có thể xem dữ liệu ở các cấp sau: chiến dịch, kênh, bộ quảng cáo và địa lý.

</Accordion>

<div id="do-i-need-to-configure-anything-to-create-audience-lists-in-google-ads-based-on-appsflyer-data" />

<Accordion title="Tôi có cần thiết lập cấu hình thứ gì đó để tạo danh sách đối tượng trong Quảng cáo Google dựa trên dữ liệu của AppsFlyer không?">

Không. Trong Google API, thông tin này đã được thiết lập và dựa trên cấu hình Sự kiện trong Ứng dụng của bạn.

</Accordion>

<div id="im-running-an-app-campaign-why-cant-i-see-data-or-conversion-events-in-the-appsflyer-or-google-ads-dashboard" />

<Accordion title="Tôi đang Chạy Chiến dịch UAC, tại sao tôi không thể thấy dữ liệu hoặc các sự kiện Chuyển đổi trong Bảng điều khiển AppsFlyer hoặc Quảng cáo Google?">

Rất có khả năng là bạn chưa nhập các sự kiện. Để biết thêm chi tiết về cách nhập sự kiện, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">here</Anchor>.

</Accordion>

<div id="what-do-i-do-if-there-are-multiple-accounts" />

<Accordion title="Tôi phải làm gì nếu có nhiều tài khoản?">

Không có vấn đề gì khi sử dụng nhiều tài khoản của Quảng cáo Google với AppsFlyer. AppsFlyer chỉ làm việc với một ID Liên kết. Do đó, chỉ một ID Liên kết phải được tạo ra trong Quảng cáo Google và ID này có thể được chia sẻ giữa nhiều tài khoản. Để biết thêm thông tin chi tiết, nhấp vào <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3030657">đây</Anchor>.

</Accordion>

<div id="what-happens-with-link-ids-created-at-mcc-level-vs-account-level" />

<Accordion title="Điều gì xảy ra với ID Liên kết được tạo ở Cấp MCC với Cấp Tài khoản">

ID Liên kết ở cấp MCC hoặc tài khoản được hỗ trợ bởi AppsFlyer. Chúng tôi khuyên bạn nên làm việc chặt chẽ với đại diện Quảng cáo Google của bạn để đảm bảo tài khoản của bạn được cấu trúc chính xác. Để biết thêm thông tin chi tiết, nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/recording-multiple-agency-mcc-google-ads-accounts">đây</Anchor>.

</Accordion>

<div id="what-is-parallel-tracking" />

<Accordion title="Theo dõi Song song là gì?">

Theo dõi song song của Google Ads cho phép trang đích của bạn tải nhanh hơn, giảm vấn đề mất lượt truy cập. Do đó, chuyển đổi được tăng lên và hiệu suất quảng cáo được cải thiện. Với Theo dõi Song song, người dùng được gửi đến URL cuối cùng, trực tiếp từ quảng cáo của bạn, trước khi gửi chúng đến các liên kết phân bổ, trong khi phép đo nhấp chuột diễn ra trong nền.

Để đọc thêm giải thích đầy đủ về Theo dõi Song song, nhấp vào <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7544674?hl=en">đây</Anchor>.

#### Điều gì cần thiết?

Để tính năng theo dõi song song hoạt động như dự định, URL cuối cùng phải khớp với URL của chiến dịch và được đưa vào <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348?hl=en">thông số ValueTrack `{lpurl}` của Google.</Anchor>

Điều này được thực hiện bằng cách:

* Sử dụng một liên kết phân bổ nền tảng duy nhất (không khuyến nghị)
  * thông số af\_r phải được sử dụng trong URL
* Sử dụng <Anchor target="_blank" href="/marketers/vi/docs/understand-onelink-short-vs-long-urls">liên kết đầy đủ OneLink</Anchor> (khuyến nghị)
  * Có các thông số URL sau được đưa vào URL chiến dịch
    * af\_android\_url
    * af\_ios\_url
    * af\_web\_dp
  * không nên sử dụng af\_dp
  * thêm URL cuối cùng của bạn (URL đích) vào thông số ValueTrack của Google. <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348?hl=en#urlinsertion&zippy=%2Ctracking-template-only">Tìm hiểu thêm</Anchor>

Ví dụ:

```
https://subdomain.onelink.me/template_id?pid=xxx&af_ios_url={lpurl}  
&af_android_url={lpurl}&af_web_dp={lpurl}
```

Lưu ý: Để xem tất cả các thông số được hỗ trợ, hãy tham khảo [bài viết](https://support.google.com/google-ads/answer/6305348?hl=en&sjid=12409212435602417786-AP#zippy=%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-campaign-level%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-ad-group-level%2Cfinal-url-tracking-template-or-custom-parameter) này.

Nhấp vào đây để xem cách định cấu hình các chiến dịch web của Google Ads với tính năng theo dõi song song.

</Accordion>

<div id="how-do-you-configure-a-campaign-with-android-or-ios-configuration" />

<Accordion title="Làm cách nào để thiết lập cấu hình một chiến dịch với Cấu hình Android hoặc iOS">

> 🚧 **Quan trọng!**
>
> AppsFlyer hỗ trợ tất cả các chiến dịch ứng dụng được kích hoạt bởi Quảng cáo Google.
>
> Google là một SRN (Mạng Tự Báo cáo). Để biết thêm thông tin về cách hoạt động của luồng phân bổ cho các mạng này, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns">đây</Anchor>.
>
> AppsFlyer có thể hiển thị bất kỳ thông tin chiến dịch nào được Google cung cấp. Loại chiến dịch (Tìm kiếm, Video, Hiển thị và Tương tác lại) và thông tin liên quan được xác định bởi Google. Bạn nên thiết lập cấu hình các chiến dịch UAC. Để được hướng dẫn về các loại chiến dịch khác, bạn nên liên hệ với người đại diện Google của mình. Để biết chi tiết về những chiến dịch này, hãy nhấp vào <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">here</Anchor>.

<div id="android-configuration-for-google-ads" />

<Accordion title="Cấu hình Android cho Google Ads">

Để hỗ trợ phân bổ Android, hãy đảm bảo rằng ứng dụng của bạn hỗ trợ thu thập GAID (ID Quảng cáo của Google) và ứng dụng đó được chuyển đến AppsFlyer thông qua SDK của chúng tôi.

#### Tạo Ghi nhận Chuyển đổi (Lượt cài đặt)

Để biết chi tiết về cách tạo ghi nhận chuyển đổi, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">here</Anchor>.

<span id="inapp_events"></span>Quảng cáo Google - Cấu hình Android - Gửi Sự kiện trong Ứng dụng

Nếu bạn muốn đo lường thêm sự thành công của các chiến dịch Cài đặt Ứng dụng Di động trong Google, bạn có thể gửi các sự kiện trong ứng dụng đến tài khoản Quảng cáo Google từ tài khoản AppsFlyer của mình.

#### Tạo một Chuyển đổi (Sự kiện trong Ứng dụng)

Để biết chi tiết về cách đo lường lượt chuyển đổi ứng dụng của bạn, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">here</Anchor>.

</Accordion>

<div id="ios-configuration-for-google-ads" />

<Accordion title="Cấu hình iOS cho Quảng cáo Google">

#### Google Ads - Cấu hình iOS: chiến dịch ứng dụng

Các chiến dịch ứng dụng cho phép bạn quảng bá ứng dụng iOS của mình trên Tìm kiếm Google, YouTube và Display ở một nơi cấu hình duy nhất.

Nói chung, bản thân Google không thể tự phân bổ cài đặt iOS từ các chiến dịch tìm kiếm vì các lượt nhấp chuột đến từ các nguồn web trên thiết bị di động, ngăn Google rút IDFA khỏi thiết bị và thực hiện khớp ID.

Trái lại, **tìm kiếm iOS** **trên** **Chiến dịch Ứng dụng có thể được phân bổ bởi Google**, cho những quảng cáo được phục vụ trên **Ứng dụng Tìm kiếm Google.**

#### Tạo Ghi nhận Chuyển đổi (Lượt cài đặt)

Để biết chi tiết về cách tạo ghi nhận chuyển đổi, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">here</Anchor>.

#### Google Ads - Cấu hình iOS - gửi sự kiện trong ứng dụng

Nếu bạn muốn đo lường thêm sự thành công của các chiến dịch Cài đặt Ứng dụng Di động trong Google, bạn có thể gửi các sự kiện trong ứng dụng đến tài khoản Quảng cáo Google từ tài khoản AppsFlyer của mình.

#### Tạo một Chuyển đổi (Sự kiện trong Ứng dụng)

Để biết chi tiết về cách đo lường lượt chuyển đổi ứng dụng của bạn, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">here</Anchor>.

</Accordion>

</Accordion>

<div id="for-how-long-do-you-keep-google-ads--userlevel-data" />

<Accordion title="Bạn giữ dữ liệu cấp độ người dùng của Google Ads trong bao lâu?">

Quảng cáo Google yêu cầu nhà cung cấp phân bổ xóa dữ liệu cấp người dùng 6 tháng sau khi cài đặt. Điều này có nghĩa là các sự kiện được thực hiện bởi những người dùng này 6 tháng sau khi họ cài đặt ứng dụng được tính là không phải trả tiền.

Dữ liệu tổng hợp trong quá khứ vẫn giữ nguyên.

Điều này có liên quan đến tất cả các kênh Google Ads.

</Accordion>

## Sự khác biệt về Google Ads

Đôi khi, có sự khác biệt giữa bảng điều khiển Quảng cáo Google và bảng điều khiển AppsFlyer.

Trong khi chúng tôi làm việc chặt chẽ với Google để giảm thiểu những khác biệt này, các nhà quảng cáo nên biết các nguyên nhân sau đây cho những khác biệt đó.

#### iOS và Android

| **Nguyên nhân** | **Google Ads** | **AppsFlyer** |
| --- | --- | --- |
| **Lượt cài đặt được hỗ trợ (aka Phân bổ đa chạm)** | Quảng cáo Google, là một SRN, phân bổ tất cả các cài đặt sau khi tham gia với Quảng cáo Google, trong cửa sổ phân bổ của chúng. | AppsFlyer phân bổ lượt nhấp chuột cuối cùng trong hành trình của người dùng, và coi lượt tương tác trước đó là <Anchor target="_blank" href="/marketers/vi/docs/measure-assisted-installs">lượt hỗ trợ</Anchor>. |
| **Cài đặt thời gian ghi** | Quảng cáo Google  quy chuyển đổi thành thời gian Nhấp chuột. | AppsFlyer quy chuyển đổi thành thời gian khởi chạy (mở ứng dụng). |
| **Vùng Thời gian** | Thay đổi - tùy thuộc vào vị trí | Thay đổi - tùy thuộc vào vị trí |
| **Cửa sổ Phân bổ** | 30 Ngày | Tích hợp Google được đặt mặc định trong 30 ngày (có thể điều chỉnh). |
| **Lượt chuyển đổi xem hết** | Lượt chuyển đổi VT chỉ hiển thị trong cột **Tất cả lượt chuyển đổi** và không hiển thị trong cột **Lượt chuyển đổi**, trừ khi được cài đặt khác trong Google Ads. | AppsFlyer hiển thị tổng số lượt cài đặt, lượt nhấp cài đặt và cài đặt VT. |
| **Lượt cài đặt lại** | Google Ads hiển thị lượt cài đặt lại dưới dạng chuyển đổi session\_start. | AppsFlyer phân bổ và hiển thị các lượt cài đặt lại (phân bổ lại AKA) như là một phần của dữ liệu nhắm mục tiêu lại. |
| **Sự kiện trong Ứng dụng** | Quảng cáo Google phân bổ sự kiện trong ứng dụng tới thời gian Nhấp chuột. | Trong bảng điều khiển của AppsFlyer, các sự kiện trong ứng dụng được phân bổ theo thời gian cài đặt. Trong Báo cáo Dữ liệu Thô, AppsFlyer phân bổ các sự kiện trong ứng dụng theo thời gian của sự kiện. |
| **Quy tắc Xác thực** | Google nhận tất cả thông tin từ AppsFlyer bất kể quy tắc xác thực. | AppsFlyer có thể khấu trừ một số lượt cài đặt dựa trên các quy tắc xác thực của chúng. |
| **Khoảng không quảng cáo Tìm kiếm theo Chiến dịch trên Ứng dụng iOS** | Google Ads bao gồm khoảng không quảng cáo cho kết quả tìm kiếm trên iOS AC trong cả web di động và ứng dụng tìm kiếm của Google. | Google Ads không phản hồi các truy vấn của đối tác phân bổ về lượt chuyển đổi tìm kiếm trên iOS AC trên web di động hay ứng dụng tìm kiếm của Google. Do đó, các lượt cài đặt này không được phân bổ cho Google Ads trong AppsFlyer. |
| **Chi phí - Các kênh chiến dịch Google Ads** | Google báo cáo chi phí cho tất cả các kênh của một chiến dịch nhất định - YouTube, hiển thị và tìm kiếm. | AppsFlyer nhận dữ liệu chi phí từ Google cho tất cả các kênh của chiến dịch, nhưng chỉ phân bổ lượt chuyển đổi từ YouTube và các kênh hiển thị trong iOS AC. Do đó, tổng CPI trong AppsFlyer sẽ cao hơn. |
| **Lượt cài đặt SKAN** | Từ API Google Ads V10+, trang tổng quan Google Ads không phân biệt giữa các lượt cài đặt với did\_win=TRUE và did\_win=NULL. Sự khác biệt chỉ trong dữ liệu thô. | Từ Google Ads API V10+, AppsFlyer chỉ hiển thị các lượt cài đặt từ các lượt đăng lại với did\_win=TRUE. Do đó, số lượt cài đặt trong AppsFlyer có thể thấp hơn. |

> 📘 **Lưu ý**
>
> * Mặc dù Google Ads hiển thị tất cả lượt cài đặt của chiến dịch nhắm mục tiêu lại ở cùng một nơi, nhưng trong bảng điều khiển Tổng quan của AppsFlyer, chế độ xem UA sẽ hiển thị lượt cài đặt mới, chế độ xem nhắm mục tiêu lại hiển thị các lượt phân bổ lại và chế độ xem hợp nhất hiển thị cả hai.
> * Khi so sánh dữ liệu từ bảng điều khiển Quảng cáo Google và AppsFlyer, hãy đảm bảo rằng dữ liệu trong bảng điều khiển Quảng cáo Google là dữ liệu được nhập từ phân tích của bên thứ 3 (AppsFlyer). Dữ liệu được nhập từ Firebase hoặc Google Play có cấu trúc khác nhau và không thể so sánh hoàn toàn với dữ liệu AppsFlyer. Để tìm hiểu cách nhập dữ liệu từ AppsFlyer vào bảng điều khiển Quảng cáo Google, nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">here</Anchor>.
> * Để so sánh các sự kiện cài đặt (first\_open trong Google Ads), hãy đảm bảo rằng bạn đi sâu vào để cài đặt các sự kiện trong báo cáo chuyển đổi trong Google Ads. Google Ads có thể hiển thị tất cả các lượt chuyển đổi (VD: lượt cài đặt, mua, đăng ký), đó là lý do tại sao việc chỉ chọn những sự kiện cài đặt đó trong số tất cả các sự kiện chuyển đổi là rất quan trọng.

> 📄 **Xem thêm**
>
> * Để biết những lưu ý liên quan đến iOS 14, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/get-skan-postback-data-from-google-ads">khả năng tương tác SKAdNetwork của Google Ads với AppsFlyer</Anchor>.

<div data-zendesk-anchors="google-ads-faq=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-google-ads h_01HA1SM7D91QPG17WH752FBAFT=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p-v%E1%BB%81-google-ads h_01HA1SM7D9JWBEPNE0E8FE665E=why-am-i-not-seeing-clicks-from-google-ads h_01HA1SM7DAW984PPRGHXA5BYSX=why-am-i-not-seeing-first_open-conversions-on-google-ads h_01HA1SM7DAXB3N9M7X8X2YB91C=why-cant-i-see-inapp-events-on-google-ads h_01HA1SM7DAH6VBNW2RPJ1CE1PT=quan-tr%E1%BB%8Dng h_01HA1SM7DACQDVGWGKV5MZ63D6=can-i-stop-google-cost-sync h_01HA1SM7DA415FQP3MFC09AE3Y=do-i-need-to-create-and-then-import-session_start h_01HA1SM7DAEKGVPDTX77RJ9Y37=can-i-send-uninstall-information-to-google-ads h_01HA1SM7DAKKVZ82WF6RVEDHE9=what-google-ads-data-does-appsflyer-display h_01HA1SM7DANYQ0DAY54CH4HPV4=do-i-need-to-configure-anything-to-create-audience-lists-in-google-ads-based-on-appsflyer-data h_01HA1SM7DA3XF8NBGYGZ0XTB69=im-running-an-app-campaign-why-cant-i-see-data-or-conversion-events-in-the-appsflyer-or-google-ads-dashboard h_01HA1SM7DAY7JNTFSG86A1QGKC=what-do-i-do-if-there-are-multiple-accounts h_01HA1SM7DAYSVMENT91T2BE26Z=what-happens-with-link-ids-created-at-mcc-level-vs-account-level h_01HA1SM7DAK186BRZN970PKPRM=what-is-parallel-tracking additional-information=%C4%91i%E1%BB%81u-g%C3%AC-c%E1%BA%A7n-thi%E1%BA%BFt h_01HA1SM7DAMNG8X22VNWMKBJ8R=%C4%91i%E1%BB%81u-g%C3%AC-c%E1%BA%A7n-thi%E1%BA%BFt h_01HA1SM7DBNAS6DP8G9D8KFHPW=how-do-you-configure-a-campaign-with-android-or-ios-configuration h_01HA1SM7DB16T3RGBVGT5Z9REW=quan-tr%E1%BB%8Dng-1 h_01HA1SM7DBC38CY8AN3EPMMJFW=android-configuration-for-google-ads creating-conversion-recording-installs=t%E1%BA%A1o-ghi-nh%E1%BA%ADn-chuy%E1%BB%83n-%C4%91%E1%BB%95i-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t h_01HA1SM7DBF9KDRNEV25KJHGHN=t%E1%BA%A1o-ghi-nh%E1%BA%ADn-chuy%E1%BB%83n-%C4%91%E1%BB%95i-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t create-a-conversion-inapp-events=t%E1%BA%A1o-m%E1%BB%99t-chuy%E1%BB%83n-%C4%91%E1%BB%95i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HA1SM7DBDQVNDQ5GG7X2PJ8K=t%E1%BA%A1o-m%E1%BB%99t-chuy%E1%BB%83n-%C4%91%E1%BB%95i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HA1SM7DBKKQ9R8MQMQT9GRXV=ios-configuration-for-google-ads google-ads-ios-configuration-app-campaigns=google-ads---c%E1%BA%A5u-h%C3%ACnh-ios-chi%E1%BA%BFn-d%E1%BB%8Bch-%E1%BB%A9ng-d%E1%BB%A5ng h_01HA1SM7DBNSDFCJA5BP59MMQ2=google-ads---c%E1%BA%A5u-h%C3%ACnh-ios-chi%E1%BA%BFn-d%E1%BB%8Bch-%E1%BB%A9ng-d%E1%BB%A5ng creating-conversion-recording-installs::6a56eb4b=t%E1%BA%A1o-ghi-nh%E1%BA%ADn-chuy%E1%BB%83n-%C4%91%E1%BB%95i-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-1 h_01HA1SM7DBXCT0NS4W50D4ZGEK=t%E1%BA%A1o-ghi-nh%E1%BA%ADn-chuy%E1%BB%83n-%C4%91%E1%BB%95i-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-1 google-ads-ios-configuration-sending-inapp-events=google-ads---c%E1%BA%A5u-h%C3%ACnh-ios---g%E1%BB%ADi-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HA1SM7DBEV9CJTAB5YHRJHYK=google-ads---c%E1%BA%A5u-h%C3%ACnh-ios---g%E1%BB%ADi-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng creating-a-conversion-inapp-events=t%E1%BA%A1o-m%E1%BB%99t-chuy%E1%BB%83n-%C4%91%E1%BB%95i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng-1 h_01HA1SM7DBCQYSJ3R67F0856QK=t%E1%BA%A1o-m%E1%BB%99t-chuy%E1%BB%83n-%C4%91%E1%BB%95i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng-1 for-how-long-do-you-keep-google-ads%E2%80%99-userlevel-data=for-how-long-do-you-keep-google-ads--userlevel-data h_01HA1SM7DBFAAV7C4ENA34B7JP=for-how-long-do-you-keep-google-ads--userlevel-data google-ads-discrepancies=s%E1%BB%B1-kh%C3%A1c-bi%E1%BB%87t-v%E1%BB%81-google-ads h_01HA1SM7DBA7KK1DXFCE2G0QTP=s%E1%BB%B1-kh%C3%A1c-bi%E1%BB%87t-v%E1%BB%81-google-ads both-ios-and-android=ios-v%C3%A0-android h_01HA1SM7DB18BTDKK5BK4949HX=ios-v%C3%A0-android h_01HA1SM7DBSTAREA36YWRRRG82=l%C6%B0u-%C3%BD h_01HDP2XBSEJVQ5G0MD0V5R05CM=xem-th%C3%AAm" />
