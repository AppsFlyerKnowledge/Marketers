---
title: Mạng tự báo cáo (SRN)
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Agencies
    - Ad Networks
    - srn
    - Self-reporting
    - networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2018-10-22T05:21:45Z'
  edited_at: '2023-08-13T18:22:33Z'
  id: 360001546905
  locale: vi
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/vi/articles/360001546905
---
> **Khái quát:** Tìm hiểu về các mạng tự báo cáo (SRN)—phân bổ, liên kết sâu, ý nghĩa của iOS và Câu hỏi thường gặp.

<div id="srns-integrated-with-appsflyer" />

## SRN được tích hợp với AppsFlyer

| **SRN** | **Biểu tượng** |
| --- | --- |
| <Anchor target="_blank" href="/marketers/vi/docs/apple-ads-integration-setup">Apple Search Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/iossearchads.png" width="131px" /> |
| <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-integration-setup-for-advertisers">Google Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/googleadwords.png?v=1" width="47px" /> |
| Google Marketing Platform | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png?v=1" width="45px" /> |
| <Anchor target="_blank" href="/marketers/vi/docs/meta-ads-integration-setup">Quảng cáo Meta</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/facebook.png?v=1" width="67px" /> |
| <Anchor target="_blank" href="/marketers/vi/docs/snapchat-advanced-srn-integration-setup">Snapchat</Anchor> | <Image alt="snapchat_logo.png" src="https://files.readme.io/c9b62d55d5c1497011d7411a21dca6f1668308bbe2806ab238b71742c421b182-32259457816209.png" width="41px" /> |
| Tencent Social Ads | <Image alt="blobid0.jpg" src="https://files.readme.io/6d6e9661c9d81f80ffeedfdf4850a84f3cc183faa49a514d1d3bb116641738da-32259428896017.jpg" width="80px" /> |
| <Anchor target="_blank" href="/marketers/vi/docs/tiktok-for-business-advanced-srn-integration-setup">TikTok for Business—SRN nâng cao</Anchor> | <Image alt="tiktok_logo.png" src="https://files.readme.io/307a95d0d848bd9e692b9a1996dffc11449a25cac1c7deeb7573b566506aeb73-15166720478993.png" width="106px" /> |
| <Anchor target="_blank" href="/marketers/vi/docs/x-ads-formerly-twitter-ads-setup-guide-overview">Twitter</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/twitter.png?v=1" width="40px" /> |
| <Anchor target="_blank" href="/marketers/vi/docs/yahoo-integration-setup">Yahoo (Oath: Ad Platforms / Yahoo Gemini)</Anchor> | <Image alt="verizonmedia.png" src="https://files.readme.io/36291ff556d07a5dbf2ae8ff693ea33d21dae9e0518a94b251202634a24049cf-32259428916369.png" width="76px" /> |
| <Anchor target="_blank" href="/marketers/vi/docs/yahoo-japan-search-ads-campaign-configuration">Yahoo! Search Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yahoojapansearch.png" width="139px" /> |

**Lưu ý:** SRN có <Anchor target="_blank" href="/marketers/vi/docs/user-level-data-retention">các hạn chế về lưu trữ và sử dụng dữ liệu ở mức người dùng.</Anchor>

<div id="attribution" />

## Phân bổ

Không giống như các mạng không phải SRN (mạng quảng cáo) sử dụng các đường dẫn phân bổ để báo cáo các sự kiện cho AppsFlyer, các SRN tự phân bổ bằng cách sử dụng ID thiết bị khi được AppsFlyer thông báo về một lượt cài đặt.

Phân bổ AppsFlyer cho mạng SRN và mạng không phải SRN dựa trên:

* Phương thức điểm chạm cuối và đa điểm chạm.
* Logic phân bổ tiêu chuẩn của AppsFlyer để sắp xếp dữ liệu về lượt hiển thị và lượt nhấp có liên quan theo thứ tự.

<div id="how-does-attribution-work-with-srns" />

### Phương thức phân bổ hoạt động như thế nào với SRN?

SRN báo cáo các sự kiện, chẳng hạn như lượt cài đặt mới và sự kiện trong ứng dụng, cho AppsFlyer theo cách sau:

* Sử dụng API để giao tiếp với các nhà cung cấp giải pháp phân bổ và đo lường.
* Khi các nhà cung cấp giải pháp phân bổ bên thứ ba phát hiện một lượt cài đặt, họ sẽ truy vấn mạng bằng ID quảng cáo.
* Báo cáo chi tiết về bất kỳ lượt nhấp hoặc lượt hiển thị quảng cáo có liên quan nào.

Sau khi AppsFlyer phân bổ, các đăng lại trong ứng dụng sẽ được gửi tới SRN trong <Anchor target="_blank" href="/marketers/vi/docs/user-level-data-retention#partner-data-retention-periods">khoảng thời gian cho phép lưu giữ dữ liệu của đối tác</Anchor>.

<div id="how-does-attribution-work-with-advanced-srns" />

### Phương thức phân bổ hoạt động như thế nào với các SRN nâng cao?

SRN nâng cao phân bổ cũng tương tự như SRN. Tuy nhiên, các SRN nâng cao còn có thể phân bổ các lượt thu hút khi không có ID thiết bị (IDFA)—bằng cách sử dụng khung <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-knowledge-base-glossary#quyền-riêng-tư-nâng-cao-hợp-nhất">Quyền riêng tư Nâng cao Hợp nhất</Anchor>.

<div id="install-attribution" />

### Phân bổ lượt cài đặt

Người dùng ứng dụng tiềm năng nhìn thấy và tương tác với nhiều quảng cáo trước khi cài đặt ứng dụng. Nói chung, các nhà cung cấp phương thức phân bổ cung cấp phân bổ điểm chạm cuối cho nhà quảng cáo—điều này phân bổ lượt cài đặt cho lượt nhấp cuối cùng được thực hiện trước khi thực sự cài đặt.

Khi một ứng dụng được khởi chạy lần đầu:

* AppsFlyer kiểm tra:
  * Ứng dụng được đặt để nhận lưu lượng truy cập từ SRN.
  * Người dùng có ID quảng cáo.
* Nếu cả hai điều kiện đều đúng, AppsFlyer sẽ truy vấn SRN bằng ID quảng cáo.
* AppsFlyer phân bổ sau khi xem xét các yêu cầu tính cho SRN.

<div id="install-attribution-examples" />

#### Ví dụ về phân bổ lượt cài đặt

<div id="example-a-assisted-attribution" />

<Accordion title="Ví dụ A: Phân bổ được hỗ trợ">

![SRN_1.png](https://files.readme.io/8e244c99f54b36a4e88b03bf05bb7ca0da2db5c7c601882ea9f68c191c38981b-32259428920337.png)

**Thứ Hai:** Mạng A báo cáo có lượt nhấp của người dùng.

**Thứ ba:** Mạng B báo cáo tương tác video.

**Thứ Tư:** Mạng C báo cáo một lượt nhấp vào quảng cáo có thể phát và 30 phút sau có một lượt cài đặt.

**AppsFlyer** phân bổ lượt cài đặt cho Mạng C và ghi nhận Mạng A và B vì đã hỗ trợ lượt cài đặt đó.

AppsFlyer cung cấp dữ liệu hỗ trợ cho nhà quảng cáo (các lượt thu hút không được phân bổ xảy ra trước khi cài đặt). Điều này cho phép các nhà quảng cáo tùy chỉnh mô hình đa điểm chạm hoặc phân bổ ghi nhận nhiều nguồn. Xem <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model">giải thích ngắn</Anchor> này.

</Accordion>

<div id="example-b-last-click-attribution" />

<Accordion title="Ví dụ B: Phân bổ nhấp chuột cuối cùng">

![SRN_2.png](https://files.readme.io/6817d8235acfdbbb5324d07ea8a31ace21cf2306e8e099129d9802e3e0d58b0c-32259457863825.png)

**Mạng D** (SRN) báo cáo một lượt nhấp chuột trước Mạng C vài phút.

**Mạng C** sử dụng tích hợp phân bổ tiêu chuẩn.

**AppsFlyer** phân bổ lượt cài đặt cho Mạng C vì mạng này có lượt nhấp cuối cùng.

</Accordion>

<div id="attribution-windows" />

### Khung thời gian phân bổ

Khoảng thời gian phân bổ bao gồm lượt xem lại và lượt xem hết. Một số SRN thu phí các nhà quảng cáo cho một lượt cài đặt dựa trên Chi phí trên mỗi Lượt hiển thị (CPM) và Chi phí trên mỗi Hành động (CPA)—những thông số này được tính dựa trên số lượt nhấp hoặc hiển thị xảy ra trong vòng từ 1-28 ngày.

**AppsFlyer** phân bổ lượt cài đặt, hoạt động, Chi phí Hiệu quả trên mỗi Lượt cài đặt (eCPI) và Chi phí Hiệu quả trên mỗi Hành động (eCPA) dựa trên phương thức phân bổ ưa thích của nhà quảng cáo và khung thời gian xem lại.

**Các nhà quảng cáo** có thể phải trả tiền cho các lượt cài đặt dựa trên khung thời gian xem lại phân bổ SRN và các mô hình lượt xem hết.

* Các nhà quảng cáo kỳ vọng phương thức phân bổ chung bên thứ ba của AppsFlyer sẽ tối ưu hóa và phân bổ chi tiêu quảng cáo của họ.
* Tại sao ư? Bởi vì AppsFlyer báo cáo eCPI và eCPA thực tế dựa trên các điều khoản do nhà quảng cáo xác định.
* SRN có thể được lợi trong thời gian ngắn vì họ thường xác định các điều khoản thanh toán của riêng mình. Tuy nhiên, các nhà quảng cáo điều chỉnh điều này bằng cách sử dụng các nhà cung cấp phương thức phân bổ bên thứ ba.

<div id="deep-linking-with-srns" />

## Liên kết sâu với SRN

Để người dùng mở ứng dụng của bạn khi nhấp vào liên kết, bạn chỉ cần thiết lập Liên kết Ứng dụng/Liên kết Chung/Lược đồ URI. Tuy nhiên, để thực hiện liên kết sâu hoặc liên kết sâu bị trì hoãn tới một trang hoặc hoạt động cụ thể trong ứng dụng của bạn, SRN sẽ sử dụng các phương thức riêng—không liên quan đến phương thức liên kết sâu của AppsFlyer.

Vậy làm cách nào để liên kết sâu người dùng và nhận được những dữ liệu thích hợp từ SRN?

<div id="direct-deep-linking" />

<Accordion title="Liên kết sâu trực tiếp">

Khi thực hiện liên kết sâu, thiết bị người dùng có thể liên kết sâu trực tiếp với các SRN mà không cần gọi ra phương thức liên kết sâu của AppsFlyer. Trong ví dụ bên dưới, người dùng hiện có nhấp vào một quảng cáo và được chuyển hướng trực tiếp đến hoạt động bằng các phương thức của Facebook, trong khi người dùng mới sẽ có trải nghiệm tương tự khi sử dụng dữ liệu chuyển đổi của AppsFlyer. Tìm hiểu cách <Anchor target="_blank" href="/marketers/vi/docs/meta-ads-faq#who-needs-facebooks-sdk">Meta ads sử dụng OneLink để liên kết sâu</Anchor>

<div id="example" />

> 📄 **Ví dụ**
>
> Jill, nhà tiếp thị di động của "greatapp", quyết định chạy chiến dịch liên kết sâu trên Meta ads nhắm mục tiêu đến đối tượng chung. Chiến dịch chuyển hướng bất kỳ người dùng nào nhấp vào đến hoạt động "bonus".
> Jack, nhà phát triển ứng dụng di động, bổ sung logic này sau khi nhận được dữ liệu chuyển đổi:
>
> 1. Có phải bắt nguồn từ Facebook ("is\_fb=true") không?
> 2. Nếu là true thì lấy giá trị của thông số nhóm quảng cáo.
> 3. Nếu giá trị có từ "bonus" thì đưa người dùng đến hoạt động "bonus".

</Accordion>

<div id="deferred-deep-linking" />

<Accordion title="Deferred deep linking">

Ngược lại với liên kết sâu, có thể thực hiện liên kết sâu trì hoãn với SRN bằng API GCD của AppsFlyer.   
AppsFlyer nhận dữ liệu chuyển đổi và cung cấp cho ứng dụng trong lần khởi chạy đầu tiên.  
Người dùng mới cài đặt sau khi nhấp vào chiến dịch liên kết sâu/nhắm mục tiêu lại trên SRN có thể được chuyển hướng bên trong ứng dụng khi khởi chạy, bằng cách sử dụng dữ liệu chuyển đổi.

Tuy nhiên, với SRN, các thông số liên kết sâu thông thường của AppsFlyer không xuất hiện như một phần của dữ liệu liên kết sâu. Để sử dụng dữ liệu này trong ứng dụng, nhà phát triển cần triển khai các logic cao hơn dựa trên các thông số hiện có, ví dụ như tên chiến dịch, bộ quảng cáo hoặc quảng cáo đơn.

**Lưu ý**: Đối với <Anchor target="_blank" href="/marketers/vi/docs/meta-ads-faq#who-needs-facebooks-sdk">Meta ads</Anchor>, liên kết sâu bị trì hoãn qua GCD có sẵn cho các ứng dụng Android sử dụng cơ chế Liên kết Giới thiệu của Google. Liên kết sâu bị trì hoãn không có sẵn cho các ứng dụng iOS.

</Accordion>

<div id="ios-implications" />

## Ý nghĩa của iOS

Hầu hết các SRN đều hỗ trợ SKAdNetwork và có tích hợp cần thiết với AppsFlyer.

<div id="ios-145-srn-attribution" />

<Accordion title="Phân bổ SRN trên iOS 14.5">

Bắt đầu từ iOS 14.5, khi người dùng đồng ý với ATT trong các ứng dụng của nhà quảng cáo và nhà phát hành (<Anchor target="_blank" href="/marketers/vi/docs/appsflyer-knowledge-base-glossary#đồng-ý-kép">đồng ý kép</Anchor>), lượt cài đặt SRN, được ghi nhận trong <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">bảng điều khiển SKAdNetwork</Anchor>, cũng được hiển thị trên bảng điều khiển truyền thống.

<div id="note" />

> 📘 **Lưu ý**
>
> * Bảng điều khiển truyền thống cho thấy số lượt cài đặt phân bổ cho SRN giảm. Khi xem xét hiệu suất SRN, hãy sử dụng <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">bảng điều khiển SKAdNetwork</Anchor>. Nhìn chung, dự kiến sẽ có tình trạng giảm lượt cài đặt được phân bổ cho SRN và tăng lượt cài đặt tự nhiên một cách tương xứng. Tuy nhiên, các SRN nâng cao sẽ ít bị tác động hơn do chúng còn phân bổ các lượt thu hút khi không có ID thiết bị.
> * <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">Bảng điều khiển SKAdNetwork</Anchor> cập nhật với độ trễ từ 48-72 giờ sau khi cài đặt.
> * Các lượt cài đặt do Apple Search Ads (ASA) mang lại không được phân bổ trong bảng điều khiển SKAdNetwork.

</Accordion>

<div id="sending-event-postbacks-to-srns" />

<Accordion title="Gửi đăng lại sự kiện tới SRN">

SRN nhận đăng lại sự kiện dựa vào việc đưa ID thiết bị vào đăng lại. Điều này cho phép các SRN tự phân bổ các hành động được báo cáo của người dùng. Nhiều người dùng iOS 14 không đồng ý, nghĩa là họ không cho phép truy cập vào ID thiết bị (IDFA) của họ. Trong trường hợp này, bạn nên dự kiến sẽ xảy ra tình trạng:

* Giảm số lượng đăng lại sự kiện được gửi tới SRN
* Có sự không nhất quán về số lượng đăng lại sự kiện giữa SRN và AppsFlyer—chủ thể ghi nhật ký tất cả các sự kiện.

<div id="note-1" />

> 📘 **Lưu ý**
>
> * Nếu không có IDFA thì đăng lại cho lượt cài đặt, lần mở ứng dụng hoặc sự kiện trong ứng dụng sẽ không được gửi tới SRN ([ngoại trừ tình huống này trong Google ads](/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid)). Tuy nhiên, một số SRN nâng cao cũng nhận được đăng lại hợp nhất khi không có IDFA.
> * Các mạng quảng cáo tính phí theo lượt nhấp không bị ảnh hưởng vì sử dụng các ID giao dịch riêng, không phải ID thiết bị, để tự phân bổ thông tin đăng lại sự kiện.

</Accordion>

<div id="faq" />

## Câu hỏi thường gặp

<div id="how-does-retargeting-work-with-srns" />

<Accordion title="Phương thức nhắm mục tiêu lại hoạt động như thế nào với SRN?">

Việc nhắm mục tiêu lại các lượt nhấp từ các mạng không phải SRN sẽ dễ nhận biết hơn nhờ có thông số `is_retargeting=true` trong đường dẫn phân bổ nhắm mục tiêu lại.  
Các SRN không có thông số tương tự để biểu thị điều này. Thay vào đó, để cho phép phân bổ thu hút lại từ SRN, AppsFlyer sử dụng logic khác:

* Điều kiện tiên quyết:
  * Trên trang **App Settings**, bật **Enable retargeting.**
  * Trong trang **Active Integrations**, chọn SRN và bật **Retargeting**.
* Với mỗi lần khởi chạy ứng dụng, AppsFlyer truy vấn SRN về các lượt thu hút gần đây theo ID thiết bị với các quảng cáo của chiến dịch cho ứng dụng.
  * Nếu SRN phản hồi lại với các thông tin thu hút, AppsFlyer sẽ xác thực lượt thu hút nằm trong khung thời gian xem lại và vượt quá thời gian tối thiểu giữa các lượt thu hút lại.
  * Các lượt thu hút đã xác thực được ghi nhận dưới dạng lượt thu hút lại và phân bổ cho SRN.

</Accordion>

<div id="what-is-srn-mistargeting" />

<Accordion title="Nhắm sai mục tiêu SRN là gì?">

Các chiến dịch SRN phải nhắm mục tiêu đến một đối tượng cụ thể, nhưng điều này không phải lúc nào cũng xảy ra: Đối tượng không phải người dùng trong các chiến dịch thu hút người dùng và những người dùng hiện có trong các chiến dịch nhắm mục tiêu lại.

Nếu dùng một SRN để chạy cả chiến dịch thu hút người dùng và nhắm mục tiêu lại, điều này có thể dẫn đến việc nhắm sai người dùng. Kết quả là bạn phải trả tiền cho lưu lượng truy cập ngoài ý muốn.

**Tình huống:** Một SRN trong nền tảng AppsFlyer được bật cho chiến dịch thu hút người dùng.

* Sau mỗi lần khởi chạy ứng dụng, AppsFlyer truy vấn SRN để kiểm tra xem gần đây ID quảng cáo (người dùng) có lượt thu hút nào hay không.
* Nếu có,
  * SRN trả lời tên chiến dịch.
  * AppsFlyer xác định xem đó có phải là lần khởi chạy đầu tiên (hay không) và phân bổ sao cho phù hợp:  
    **Khởi chạy lần đầu**: Một lượt cài đặt mới được phân bổ cho chiến dịch.  
     **Khởi chạy lần thứ hai hoặc sau đó**: Một sự kiện nhắm mục tiêu lại được phân bổ cho chiến dịch.

**Kết luận:** Việc nhận các sự kiện nhắm mục tiêu lại từ chiến dịch thu hút người dùng thật lãng phí.

<div id="is-mistargeting-a-problem" />

#### Việc nhắm sai mục tiêu có phải là vấn đề?

Các nhà phân tích dữ liệu của AppsFlyer đã kiểm tra các chiến dịch **thu hút người dùng** của Meta ads trong một tháng nhất định.

* Tính năng Nhắm mục tiêu lại đã được bật.
* Trong 30% số lượng chiến dịch, có ít nhất 15% người dùng được nhắm mục tiêu là người dùng hiện có của ứng dụng.
* Trong 5% chiến dịch, ít nhất 40% là người dùng ứng dụng hiện có.
* **Kết luận: Trong các chiến dịch thu hút người dùng trên SRN, cứ 10 người dùng được nhắm mục tiêu thì có 1 người dùng hiện có.**

[![mistargeted_users.png](https://files.readme.io/e135e9fc9ccda47a5d06c9595f171a60f9892f4c63212b4e459eeec897b16a3b-32259428927505.png)](https://files.readme.io/e135e9fc9ccda47a5d06c9595f171a60f9892f4c63212b4e459eeec897b16a3b-32259428927505.png)

<div id="solving-the-mistargeting-problem" />

#### Giải quyết vấn đề nhắm mục tiêu nhầm

**Giải pháp cơ bản:** Không đưa người dùng hiện có của ứng dụng vào chiến dịch thu hút người dùng.

* SRN sẽ chỉ nhắm mục tiêu người dùng mới tiềm năng.
* **Tối đa các kết quả thu hút người dùng mới đối với cùng một mức ngân sách**.
* Cập nhật định kỳ (và thủ công) chiến dịch, ví dụ: mỗi tháng một lần.
* Tuy nhiên, khoảng trống thời gian có nghĩa là người dùng hiện có có thể được nhắm mục tiêu trong chiến dịch thu hút người dùng trong suốt tháng đầu tiên sau khi cài đặt ứng dụng.

**<Anchor target="_blank" href="/marketers/vi/docs/audiences-guide">Audiences</Anchor>**, một tính năng cao cấp của AppsFlyer, cho phép bạn tự động gửi bất kỳ phân đoạn nào trong cơ sở người dùng của bạn tới hàng chục mạng quảng cáo mỗi ngày.

Nghiên cứu của AppsFlyer cho thấy rằng việc giải quyết lỗi nhắm sai mục tiêu có thể tác động đáng kể đến nỗ lực tiếp thị và thu hút người dùng.

</Accordion>

<div id="why-is-the-original-url-field-empty-in-raw-data-reports" />

<Accordion title="Tại sao trường Original URL lại trống trong báo cáo dữ liệu thô?">

Lượt nhấp được thực hiện trong môi trường SRN nhưng không có đường dẫn phân bổ của AppsFlyer. Do đó, dữ liệu Original URL được liên kết của lượt nhấp không có sẵn cho AppsFlyer.

</Accordion>

<div id="dashboard-doesnt-show-srn-clicks-and-impressions" />

<Accordion title="Bảng điều khiển không hiển thị số lượt nhấp và hiển thị SRN">

Lượt nhấp được thực hiện trong môi trường SRN nhưng không có đường dẫn phân bổ của AppsFlyer. Do đó, một số SRN không cung cấp dữ liệu về lượt nhấp và hiển thị cho AppsFlyer.

<Anchor target="_blank" href="/marketers/vi/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Meta ads</Anchor> và <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-cost-and-ad-revenue">Google</Anchor> cung cấp một số dữ liệu hợp nhất cho AppsFlyer.

</Accordion>

<div id="can-agencies-configure-srn-campaigns" />

<Accordion title="Các đại lý có thể cấu hình chiến dịch SRN không?">

Có, <Anchor target="_blank" href="/partners/vi/docs/about-agency-accounts#mạng-quảng-cáo-tự-báo-cáo">xem tại đây về cấu hình SRN của Đại lý</Anchor>.

</Accordion>

<div id="does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid" />

<Accordion title="AppsFlyer có gửi đăng lại đối với các ID quảng cáo (IDFA/GAID) bị thiếu không?">

Khi ID quảng cáo chứa một chuỗi trống (“”) hoặc hiển thị giá trị ‘00000000-0000-0000-0000-000000000000’ (IDFA bằng 0), AppsFlyer không gửi đăng lại cho các lượt cài đặt, lần mở ứng dụng hay sự kiện trong ứng dụng, ngoại trừ các tình huống sau:

* Nằm trong quá trình tích hợp để đo lường tiếp thị lại với Google Ads, khi người dùng iOS không chấp thuận thực hiện mở ứng dụng hoặc thực hiện một sự kiện trong ứng dụng, AppsFlyer sẽ gửi `gbraid` và thông tin sự kiện cho Google Ads (đối với sự kiện `additional_data_json`).
* Trên Android, khi không có ID thiết bị nhưng giá trị liên kết giới thiệu chứa `gclid` (dành cho lượt cài đặt) hoặc sự kiện thu hút lại chứa liên kết sâu với thông số `gclid`, AppsFlyer sẽ gửi `gclid` và thông tin sự kiện tới Google Ads.

**Thông số** `gbraid` **của Google Ads:** Mã định danh hợp nhất do Google tạo để xác định một nhóm thiết bị và được liên kết sâu tham chiếu.

**ID Lượt nhấp của Google (thông số `gclid`):** Một thông số được chuyển vào URL với các lượt nhấp của quảng cáo (để xác định chiến dịch) và các thuộc tính khác của lượt nhấp (được liên kết với quảng cáo). Thông số này được sử dụng để theo dõi quảng cáo và phân bổ chiến dịch.

</Accordion>

<div data-zendesk-anchors="srns-integrated-with-appsflyer=srn-%C4%91%C6%B0%E1%BB%A3c-t%C3%ADch-h%E1%BB%A3p-v%E1%BB%9Bi-appsflyer attribution=ph%C3%A2n-b%E1%BB%95 how-does-attribution-work-with-srns=ph%C6%B0%C6%A1ng-th%E1%BB%A9c-ph%C3%A2n-b%E1%BB%95-ho%E1%BA%A1t-%C4%91%E1%BB%99ng-nh%C6%B0-th%E1%BA%BF-n%C3%A0o-v%E1%BB%9Bi-srn how-does-attribution-work-with-advanced%E2%80%94srns=ph%C6%B0%C6%A1ng-th%E1%BB%A9c-ph%C3%A2n-b%E1%BB%95-ho%E1%BA%A1t-%C4%91%E1%BB%99ng-nh%C6%B0-th%E1%BA%BF-n%C3%A0o-v%E1%BB%9Bi-c%C3%A1c-srn-n%C3%A2ng-cao install-attribution=ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t install-attribution-examples=v%C3%AD-d%E1%BB%A5-v%E1%BB%81-ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t attribution-windows=khung-th%E1%BB%9Di-gian-ph%C3%A2n-b%E1%BB%95 deep-linking-with-srns=li%C3%AAn-k%E1%BA%BFt-s%C3%A2u-v%E1%BB%9Bi-srn ios-implications=%C3%BD-ngh%C4%A9a-c%E1%BB%A7a-ios faq=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p is-mistargeting-a-problem=vi%E1%BB%87c-nh%E1%BA%AFm-sai-m%E1%BB%A5c-ti%C3%AAu-c%C3%B3-ph%E1%BA%A3i-l%C3%A0-v%E1%BA%A5n-%C4%91%E1%BB%81 solving-the-mistargeting-problem=gi%E1%BA%A3i-quy%E1%BA%BFt-v%E1%BA%A5n-%C4%91%E1%BB%81-nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-nh%E1%BA%A7m" />
