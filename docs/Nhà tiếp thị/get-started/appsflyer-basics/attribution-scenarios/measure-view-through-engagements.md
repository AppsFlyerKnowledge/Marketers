---
title: Hướng dẫn phân bổ lượt xem qua
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-20T07:38:24Z'
  edited_at: '2023-11-16T10:14:43Z'
  id: 210084473
  locale: vi
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/vi/articles/210084473
---
> **Sơ lược:** Người dùng xem quảng cáo (lượt hiển thị) và sau đó cài đặt ứng dụng sẽ được phân bổ theo phân bổ lượt xem qua.

<div id="overview" />

## Tổng quan

Phân bổ lượt xem qua đo lường số lượt cài đặt, lượt phân bổ lại và lượt tương tác lại của những người dùng đã xem quảng cáo nhưng không nhấp vào quảng cáo đó.

<div id="view-through-attribution-flow" />

### Luồng phân bổ lượt xem qua

![Retargeting_-_View-through__1_.png](https://files.readme.io/86d32778a8a0966499a0c5c91c1b2d8aed6d5bb24214b1a32fd484779c105a98-4412917609489.png)

<div id="terminology" />

### Bảng thuật ngữ

* **Lượt hiển thị:** Hiển thị quảng cáo cho người dùng, bất kể người dùng có nhấp chuột hay tương tác khác hay không.
* **Lượt cài đặt**: nghĩa là lượt cài đặt, lượt phân bổ lại và lượt tương tác lại trong bài viết này.
* **Phân bổ lượt xem qua:** Phân bổ số lượt cài đặt cho một nguồn truyền thông sau khi người dùng nhìn thấy quảng cáo hiển thị.

<div id="view-through-attribution-principles" />

### Nguyên tắc phân bổ lượt xem qua

* Hỗ trợ cả <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#device-id-matching">khớp ID thiết bị</Anchor> và <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#probabilistic-modeling">tạo mô hình xác suất</Anchor> (<Anchor target="_blank" href="/marketers/vi/docs/app-settings#viewthrough-attribution-via-probabilistic-modeling">tính năng bạn phải bật</Anchor>).
* Được hỗ trợ bởi các đối tác nằm trong [danh sách đối tác phân bổ lượt xem qua](/docs/measure-view-through-engagements#view-vta-partner-list).

Lượt hiển thị có thể được sử dụng để phân bổ lượt xem qua khi áp dụng các nguyên tắc sau:

* Lượt hiển thị xảy ra trong khoảng thời gian xem lại lượt xem qua (mặc định là 24 giờ).
* Xem xét lượt hiển thị gần đây nhất nếu có nhiều lượt hiển thị.
* Số lượt nhấp chuột được ưu tiên hơn số lượt hiển thị. Điều này có nghĩa là nếu có nhấp chuột trong giai đoạn xem lại nhấp qua thì nhấp chuột gần đây nhất sẽ thắng. Lần hiển thị gần đây nhất được coi là người đóng góp (hỗ trợ).

<div id="view-through-lookback-window" />

### Khoảng thời gian xem lại lượt xem qua

* Đối với các kênh không phải là SRN, thời lượng xem lại phân bổ lượt xem qua là 1-24 giờ. Đối với các kênh là SRN, khoảng thời gian xem lại có thể dài hơn.
* Cách đặt khoảng thời gian:
  * **Các kênh không phải là SRN:** Đặt thời lượng xem lại thông qua các đường dẫn phân bổ lượt hiển thị bằng cách cài đặt thông số  `af_viewthrough_lookback`. Nếu không đặt thông số này thì khoảng thời gian xem lại mặc định là 24 giờ.
  * **Các kênh là SRN**: Khoảng thời gian được xác định bởi SRN. Bạn nên cài đặt giá trị giống với giá trị của các kênh là SRN trong AppsFlyer.

<div id="view-through-attribution-reporting-and-metrics" />

### Báo cáo và số liệu phân bổ lượt xem qua

* **Dữ liệu tổng hợp:** Các mạng quảng cáo báo cáo dữ liệu lượt hiển thị tổng hợp cho AppsFlyer thông qua API hoặc theo mỗi lượt hiển thị. Hãy xem xét rằng việc tính số lượt hiển thị và báo cáo được xác định bởi từng đối tác riêng lẻ. Xem định nghĩa về số lượt hiển thị và số lượt nhấp chuột của các đối tác tích hợp chính. Các số liệu liên quan có sẵn trong trang Tổng quan và thông qua các công cụ báo cáo khác. Các số liệu có sẵn là: 
  * Số lượt hiển thị: Số lượt hiển thị xảy ra trong một khoảng thời gian nhất định.
  * Lượt xem qua: Số lượt cài đặt được phân bổ bằng cách sử dụng phân bổ lượt xem qua.
* **Dữ liệu thô**:
  * Dữ liệu cấp độ người dùng (dữ liệu thô) của người dùng được phân bổ thông qua phân bổ lượt xem qua có sẵn và tương tự như dữ liệu của người dùng được phân bổ theo lượt nhấp. Tuy nhiên, một số đối tác hạn chế tính sẵn có của dữ liệu này.
  * Dữ liệu lượt hiển thị (tương tự như dữ liệu lượt nhấp chuột) có sẵn.
  * Trường attributed\_touch\_type chứa giá trị *lượt hiển thị.*

<div id="view-through-operations" />

## Hoạt động xem qua

<div id="set-impression-links" />

<Accordion title="Đặt đường dẫn hiển thị">

Mạng quảng cáo gửi các đường dẫn hiển thị đến AppsFlyer cùng với các chi tiết về chiến dịch và các chi tiết khác tương tự như các chi tiết có trong <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters">đường dẫn phân bổ</Anchor> lượt nhấp qua.

Các đường dẫn được gửi theo thời gian thực nhằm mục đích nếu người dùng cài đặt sau khi xem một quảng cáo thì lượt cài đặt đó sẽ được phân bổ chính xác.

Hãy xem xét những điều sau đây khi chuẩn bị đường dẫn:

* URL cơ sở là `http://impression.appsflyer.com`. Cả hai giao thức HTTP và HTTPS đều được hỗ trợ
* Sử dụng một yêu cầu GET.
* Bao gồm ID thiết bị nếu có: IDFA, GAID, IDFV, v.v.
* Bao gồm các thông số về <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#các-thông-số-tạo-mô-hình-xác-suất-cho-mạng-quảng-cáo">tạo mô hình xác suất</Anchor>.
* Các giá trị ID thiết bị có thể bị băm để bảo mật tốt hơn bằng SHA1. Tên thông số phải bắt đầu bằng "sha1\_" và được theo sau bởi tên thông số và giá trị băm, tức là sha1\_idfa, sha1\_advertising\_id, sha1\_android\_id và sha1\_imei.

> 📄
>
>  Ví dụ
>
> ```http
> http://impression.appsflyer.com/{app-id}?c={campaign name}&pid={media source}
> &af_viewthrough_lookback=1d&af_prt={agency_name}&af_siteid={site id value}
> &af_sub1={free value}&idfa={idfa value}
> ```

</Accordion>

<div id="set-custom-impression-links" />

<Accordion title="Đặt đường dẫn hiển thị tùy chỉnh">

Nhà quảng cáo sử dụng các đường dẫn hiển thị lượt phân bổ với các nguồn truyền thông tùy chỉnh của riêng họ, ví dụ như biểu ngữ trang web.

Khi <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#tạo-liên-kết-onelink">tạo đường dẫn phân bổ tùy chỉnh</Anchor>, nhà quảng cáo sẽ nhận được các đường dẫn hiển thị đầy đủ, có thể được kích hoạt khi có một người dùng tương tác với quảng cáo của họ.

Đường dẫn hiển thị tùy chỉnh (được tạo qua OneLink) cũng có thể được sử dụng để thực hiện phân bổ lượt xem qua cho khách truy cập trang web bằng thiết bị di động. Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">cách tạo các URL lượt hiển thị tùy chỉnh</Anchor>.

</Accordion>

<div id="turn-off-viewthroughattribution" />

<Accordion title="Tắt tính năng phân bổ lượt xem qua">

Tính năng phân bổ lượt xem qua được bật mặc định. Nếu AppsFlyer nhận được đường dẫn phân bổ lượt hiển thị hợp lệ thì lượt hiển thị đó sẽ được đưa vào luồng phân bổ.

Vì tính năng phân bổ lượt xem qua được kích hoạt theo mặc định, nên điều quan trọng là các nhà quảng cáo phải đồng ý trước với mạng theo hợp đồng để biết liệu có nên bật tính năng phân bổ lượt xem qua hay không.

Phân bổ lượt xem hết có thể bị tắt với mỗi nguồn truyền thông. Tuy nhiên, nếu nhận được dữ liệu lượt hiển thị, và phân bổ lượt xem hết bị tắt:

* Số liệu về lượt hiển thị có sẵn trong bảng điều khiển.
* Quá trình phân bổ bỏ qua những lượt hiển thị này.

**Cách tắt tính năng phân bổ lượt xem qua:**

1. Trong AppsFlyer, đi đến **Configuration** > **Active Integrations**.
2. Chọn đối tác tích hợp.
3. Trong tab Integration, tắt **Install view-through attribution**.
4. Nhấp vào **Save integration** (Lưu tích hợp).

Liên quan đến các kênh là SRN: Các bước để tắt tính năng phân bổ lượt xem qua trong AppsFlyer không giống như đối với mạng. Hãy đảm bảo rằng bạn căn chỉnh cài đặt lượt xem qua trong cả AppsFlyer và mạng để tránh chênh lệch số liệu.

</Accordion>

<div id="view-vta-partner-list" />

<Accordion title="Xem danh sách đối tác VTA">

Danh sách các đối tác mạng quảng cáo hỗ trợ phân bổ lượt xem qua có sẵn trên trang tổng quan. 

**Cách xem danh sách**:

1. Trong AppsFlyer, đi đến **Configuration**> **Active Integrations**.
2. Chọn **All integrations**.
3. Trong bộ lọc **Partner capability**, chọn **View-through**.   
   Danh sách đối tác sẽ hiển thị.

</Accordion>

<div data-zendesk-anchors="overview=t%E1%BB%95ng-quan h_01HEMT7T1TB9W7ZBRPQW29SRPF=t%E1%BB%95ng-quan viewthrough-attribution-flow=lu%E1%BB%93ng-ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-xem-qua h_01HEMT7T1T6ZK4ZH7DKV3162J1=lu%E1%BB%93ng-ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-xem-qua terminology=b%E1%BA%A3ng-thu%E1%BA%ADt-ng%E1%BB%AF h_01HEMT7T1TY46QXBDS6MBF1DZ5=b%E1%BA%A3ng-thu%E1%BA%ADt-ng%E1%BB%AF viewthrough-attribution-principles=nguy%C3%AAn-t%E1%BA%AFc-ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-xem-qua h_01HEMT7T1THD8TVKRRJ168HKY2=nguy%C3%AAn-t%E1%BA%AFc-ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-xem-qua viewthrough-lookback-window=kho%E1%BA%A3ng-th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-l%C6%B0%E1%BB%A3t-xem-qua h_01HEMT7T1TWHN2AB3Q5X36TKKB=kho%E1%BA%A3ng-th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-l%C6%B0%E1%BB%A3t-xem-qua viewthrough-attribution-reporting-and-metrics=b%C3%A1o-c%C3%A1o-v%C3%A0-s%E1%BB%91-li%E1%BB%87u-ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-xem-qua h_01HEMT7T1TQNKM5GABA7VY6KR1=b%C3%A1o-c%C3%A1o-v%C3%A0-s%E1%BB%91-li%E1%BB%87u-ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-xem-qua viewthrough-operations=ho%E1%BA%A1t-%C4%91%E1%BB%99ng-xem-qua h_01HEMT7T1T13JC75ZYY01N8PS6=ho%E1%BA%A1t-%C4%91%E1%BB%99ng-xem-qua h_01HEMT7T1TQ3YNQ2Y0CCGPXWDX=set-impression-links h_01HEMT7T1T75MBS64JE837CJ0E=set-custom-impression-links h_01HEMT7T1T253G1CZNS9KVDFCP=turn-off-viewthroughattribution h_01HEMT7T1T5MQHC3F5EHSGMYQF=view-vta-partner-list" />
