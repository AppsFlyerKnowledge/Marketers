---
title: API OpenDSR
metadata:
  keywords:
    - Advertisers
    - GDPR
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2022-12-12T09:14:00Z'
  edited_at: '2023-12-04T11:40:57Z'
  id: 11332840660625
  locale: vi
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/vi/articles/11332840660625
---
> **Tổng quan**: Bài viết này dành cho khách hàng sử dụng AppsFlyer, thường được gọi là nhà quảng cáo hoặc chủ sở hữu ứng dụng, sử dụng Nền tảng để ghi nhận việc sử dụng và phân bổ ứng dụng. Chủ sở hữu ứng dụng triển khai API OpenDSR (Yêu cầu Chủ thể Dữ liệu) để tuân thủ các luật bảo vệ dữ liệu hiện hành như GDPR (Châu Âu), CCPA (California), LGPD (Brazil) và PDPA (Thái Lan).

**Tuyên bố của luật sư chúng tôi:** *Không nội dung nào được nêu trong tài liệu này là thông tin tư vấn pháp lý. Những nội dung này chỉ nhằm cung cấp thông tin và sự tiện lợi cho bạn. Bạn nên hợp tác chặt chẽ với các cố vấn pháp lý và các cố vấn chuyên môn khác để xác định chính xác cách thức mà GDPR, CCPA hay bất kỳ luật nào khác có khả năng có hoặc không áp dụng đối với bạn.* Mối quan hệ riêng tư giữa bạn và AppsFlyer được điều chỉnh bởi <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy">Chính sách Quyền riêng tư về Dịch vụ của AppsFlyer</Anchor>. Đối với bất kỳ câu hỏi nào liên quan đến Chính sách Quyền riêng tư về Dịch vụ này hoặc để liên hệ với nhân viên bảo vệ dữ liệu của chúng tôi, vui lòng gửi thư cho chúng tôi theo địa chỉ [privacy@appsflyer.com](mailto:privacy@appsflyer.com). Theo mục đích của Điều 27 của Quy định chung về bảo vệ dữ liệu, đại diện trong Liên minh Châu Âu của AppsFlyer là AppsFlyer Germany GmbH, Schönhauser Allee 180, 10119 Berlin, Đức (liên hệ [privacy@appsflyer.com](mailto:privacy@appsflyer.com); +49-30-166373500).

## Quy định về quyền riêng tư

Trong bài viết này, các tham chiếu đến các quy định về quyền riêng tư sẽ bao gồm các quy định được liệt kê trong bảng sau đây.

| Quy định | Biểu tượng | Mô tả |
| --- | --- | --- |
| GDPR | ![GDPR.png](https://files.readme.io/c3eb63a14b95bda24478f1d8fec75bcc59789157c4e53ffb44ab77ccd6dfe091-12830387561233.png) | Quy định Bảo vệ Dữ liệu Chung là quy định của EU liên quan đến việc bảo vệ dữ liệu và quyền riêng tư của công dân Liên minh Châu Âu |
| CCPA | ![CCPA.png](https://files.readme.io/57988a70f4e8395b9562fce9e424348cd7d61401ec7ca0ff32de518a093eb4dc-12830389364241.png) | Đạo luật Quyền riêng tư của Người tiêu dùng California |
| LGPD | ![LGPD.png](https://files.readme.io/4e50bdc8e83db49b4eb0d84f757816ebc1d0e461ae8792af9ab48d7e51d20af3-12830406815633.png) | Lei Geral de Proteção de Dados |
| PDPA | ![6137_Privacy_Shield_Thailand-01.png](https://files.readme.io/90833957690e7a52eb43b330d34a85c67af7a6c071b8ac79dec0733ec9aafcfc-12830408352657.png) | Đạo luật Bảo vệ Dữ liệu Cá nhân |

Các thuật ngữ như quy định về quyền riêng tư, GDPR, CCPA, LGPD và PDPA được sử dụng có thể thay thế cho nhau trong bài viết này.

### Sáng kiến OpenDSR

Để giải quyết và quản lý các yêu cầu do Chủ thể Dữ liệu gửi theo các quy định về quyền riêng tư, AppsFlyer, cùng với mParticle, Amplitude và Braze, đã khởi tạo giao thức OpenDSR (trước đây gọi là OpenGDPR).

OpenDSR là một khuôn khổ mã nguồn mở giúp tạo điều kiện cho hoạt động hợp tác giữa các công ty công nghệ để sử dụng dữ liệu khách hàng một cách công bằng và minh bạch. Giao thức này cho phép các nhà cung cấp thực hiện các hành động bảo vệ dữ liệu trên nhiều hệ thống xử lý và lưu trữ dữ liệu khách hàng.

<Anchor target="_blank" href="https://www.appsflyer.com/company/newsroom/pr/opengdpr-initiative/">Tìm hiểu thêm về sáng kiến OpenDSR</Anchor>.

### Các định nghĩa

| Điều khoản DSR | Thuật ngữ AppsFlyer | Mô tả |
| --- | --- | --- |
| Chủ thể Dữ liệu | Người dùng Ứng dụng hoặc Người dùng cuối | Người dùng Ứng dụng là người dùng có dữ liệu được thu thập |
| Người kiểm soát Dữ liệu | Chủ sở hữu Ứng dụng hoặc Nhà quảng cáo | Chủ sở hữu Ứng dụng xác định mục đích và phương tiện xử lý dữ liệu cá nhân. |
| Người xử lý Dữ liệu | AppsFlyer và các đối tác của mình | AppsFlyer và các đối tác xử lý dữ liệu cá nhân thay mặt cho người kiểm soát dữ liệu |

### Yêu cầu DSR

DSR quy định chi tiết các quyền bắt buộc của Chủ thể Dữ liệu mà Đơn vị Kiểm soát Dữ liệu phải tuân thủ. Đối với mục đích API, các quyền này được chuyển thành các loại yêu cầu. Các chi tiết sau đây xác định cách AppsFlyer xử lý các loại yêu cầu khác nhau.

| **Loại yêu cầu**<br /><br />**(Quyền)** | **Định nghĩa GDPR** | Xử lý yêu cầu của AppsFlyer |
| --- | --- | --- |
| **Quyền truy cập** | <ul><li>Nếu được yêu cầu, Người dùng Ứng dụng có quyền biết Chủ sở hữu ứng dụng liệu có được xử lý dữ liệu của họ hay không, lý do và thời gian là bao lâu.</li><li>Nếu dữ liệu được chia sẻ với các bên thứ ba, như AppsFlyer, thì Người dùng Ứng dụng có quyền biết những bên thứ ba đó là ai.</li><li>Quyền được biết những loại dữ liệu nào đang được xử lý.</li><li>Nếu có chế độ xử lý tự động, thì chế độ này có ảnh hưởng đáng kể đến các dữ liệu đó.</li></ul> | Chủ sở hữu Ứng dụng nhận được một bản sao dữ liệu cá nhân đã xử lý của Người dùng Ứng dụng. |
| **Tính khả chuyển** | Người dùng Ứng dụng cần nhận tất cả dữ liệu cá nhân của họ theo định dạng có cấu trúc, thường được sử dụng và có thể đọc được – chẳng hạn như tệp CSV. | Chủ sở hữu Ứng dụng nhận được một bản sao dữ liệu cá nhân đã xử lý của Người dùng Ứng dụng. |
| **Quyền hiệu chỉnh** | Cho phép Người dùng Ứng dụng sửa dữ liệu của họ nếu họ thấy không chính xác hoặc không trung thực. Chủ sở hữu Ứng dụng được yêu cầu phải xóa hoặc sửa dữ liệu không chính xác hoặc không đầy đủ. | <ul><li>AppsFlyer xóa dữ liệu của Người dùng Ứng dụng nhận được trước ngày yêu cầu *hiệu chỉnh*.</li><li>Dữ liệu nhận được sau đó được AppsFlyer ghi lại.</li></ul> |
| **Quyền xóa** | Quyền xóa yêu cầu Chủ sở hữu Ứng dụng xóa dữ liệu cá nhân trong vòng 14 ngày kể từ ngày nhận được yêu cầu. | Dữ liệu bị xóa |

## GDPR của AppsFlyer Yêu cầu API

Sử dụng API Yêu cầu GDPR theo mô tả trong phần này để tuân thủ DSR.

* **Yêu cầu GDPR:** Thực hiện một trong các loại yêu cầu trên: truy cập, tính khả chuyển, quyền xóa, hiệu chỉnh.
* **Yêu cầu Trạng thái** - Truy vấn trạng thái hiện tại của yêu cầu GDPR
* **Yêu cầu Phát hiện**: Yêu cầu thông tin về phiên bản API được hỗ trợ và Định dạng Dữ liệu
* **Hủy**: Hủy một yêu cầu GDPR trong giai đoạn ***chờ*** xử lý

Chủ sở hữu Ứng dụng cần thực hiện các thay đổi về giao diện người dùng cho ứng dụng của họ để Người dùng Ứng dụng có thể gửi yêu cầu. Lưu ý rằng yêu cầu GDPR là cho một người dùng tại một thời điểm.

<div id="1-gdpr-request" />

<Accordion title="1. Yêu cầu GDPR">

### Quy trình yêu cầu GDPR

Các loại yêu cầu GDPR, quyền truy cập, tính khả chuyển, quyền xóa và hiệu chính, có cùng một luồng:

1. **Người dùng Ứng dụng** gửi yêu cầu.
2. **Chủ sở hữu Ứng dụng** tạo yêu cầu GDPR (xem bên dưới) và gửi đến AppsFlyer.
3. **AppsFlyer** nhận được yêu cầu và trả lời là "201 OK" cho các yêu cầu hợp lệ.
4. Trong 48 giờ sau, yêu cầu được xếp hàng đợi và có trạng thái là ***đang chờ xử lý***. Người dùng Ứng dụng có thể hủy yêu cầu.
5. Sau 48 giờ, trạng thái yêu cầu sẽ thay đổi thành ***đang xử lý.*** AppsFlyer gửi đăng lại ***thay đổi trạng thái***. Tại thời điểm này, sẽ không thể hủy bỏ yêu cầu.
6. Trong vòng 14 ngày (xem ghi chú bên dưới), AppsFlyer đáp ứng yêu cầu và trạng thái yêu cầu sẽ cập nhật thành đã ***hoàn thành***. AppsFlyer gửi đăng lại thay đổi trạng thái.
   * Trong trường hợp *xóa* hoặc *hiệu chỉnh*, dữ liệu của Người dùng Ứng dụng sẽ bị xóa.
   * Trong trường hợp *khả năng di chuyển* hoặc *quyền truy cập,* dữ liệu của Người dùng Ứng dụng có thể được truy cập trong bảng điều khiển AppsFlyer theo **GDPR** hoặc thông qua API Yêu cầu (xem bên dưới).

   **Lưu ý:** Thời hạn 14 ngày này bắt đầu sau khi thời gian ***chờ xử lý*** 48 giờ kết thúc. Do đó, tổng thời gian để thực hiện yêu cầu là 16 ngày kể từ khi Chủ sở hữu Ứng dụng gửi yêu cầu đến AppsFlyer.

### Định dạng yêu cầu GDPR

API Yêu cầu GDPR có thể được gửi qua HTTP POST tới điểm cuối sau:

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests
```

Đối với việc cấp quyền API, hãy sử dụng cùng mã thông báo API V2 như đối với API Pull. Người dùng quản trị có thể <Anchor target="_blank" href="/marketers/vi/docs/managing-appsflyer-tokens#truy-xuất-mã-thông-báo-api">truy xuất mã thông báo</Anchor> từ trang mã thông báo API trong bảng điều khiển. Thêm mã thông báo vào tiêu đề yêu cầu như sau: `'Authorization': 'Bearer %AuthTokenV2%'`

#### Tham số

<table><thead><tr><th><strong>Tên Thuộc tính</strong></th><th><strong>Bắt buộc</strong></th><th><strong>Mô tả</strong></th></tr></thead><tbody><tr><td><strong>subject_request_id</strong></td><td>Có</td><td>Chuỗi UUID v4. Được Người kiểm soát tạo tại thời điểm gửi yêu cầu tới Người xử lý. Sau đó, chuỗi này có thể được sử dụng để kiểm tra trạng thái của yêu cầu, cập nhật hoặc hủy bỏ yêu cầu.</td></tr><tr><td><strong>subject_request_type</strong></td><td>Có</td><td><p>Giá trị chuỗi đại diện cho loại Yêu cầu GDPR. Các giá trị được hỗ trợ:</p><ul><li>xóa</li><li>khả năng di chuyển</li><li>truy cập</li><li>hiệu chỉnh</li></ul></td></tr><tr><td><strong>subject_identities</strong></td><td>Có</td><td><ul><li>Một chuỗi đối tượng nhận dạng xác định danh tính của người yêu cầu (xem bên dưới).</li><li>Mỗi yêu cầu chỉ có thể chứa một danh tính chủ thể.</li></ul></td></tr><tr><td><strong>submitted_time</strong></td><td>Có</td><td><ul><li>Chuỗi ngày RFC 3339 về thời gian yêu cầu ban đầu của chủ thể dữ liệu</li><li>Nhãn thời gian theo giờ UTC</li></ul></td></tr><tr><td><strong>property_id</strong></td><td>Có</td><td><p>Chuỗi đại diện cho ứng dụng dành cho thiết bị di động trong phạm vi của yêu cầu</p><p><strong>Ví dụ</strong>:</p><ul><li> iOS: id123456789</li><li> <strong>Android</strong>: com.example, com.publishers.name </li><li> <strong>Ứng dụng Android không có trên cửa hàng</strong>: com.publisher.name-channel<br/> <strong>Lưu ý</strong>  Trong một số trường hợp, chủ sở hữu ứng dụng ghi nhận phân bổ ngoài cửa hàng bằng cách sử dụng tên ứng dụng Android trên Google Play. Trong những trường hợp này, hãy sử dụng tên ứng dụng thông thường vì tên này sẽ hiển thị trong Bảng điều khiển.</li></ul></td></tr><tr><td><strong>phiên_bản_api</strong></td><td>Không</td><td>Chuỗi phiên bản đại diện cho phiên bản mong muốn của API yêu cầu GDPR</td></tr><tr><td><strong>status_callback_urls</strong> </td><td>Không, nhưng khuyến nghị</td><td><ul><li>Chuỗi tối đa 3 điểm cuối cho các lệnh gọi lại trạng thái sẽ được gửi đến các thay đổi trạng thái yêu cầu sau đây.</li><li>Chỉ <span>hỗ trợ các điểm cuối HTTPS.</span> </li><li><span>URL không hợp lệ bị từ chối.</span></li></ul></td></tr><tr><td rowspan="2"> <strong>platform</strong><br/><br/> </td><td>Không</td><td><p>Giá trị là một trong những nền tảng DSR được hỗ trợ:<br/><code>android</code>, <code>ios</code>, <code>web</code>, <code>windowsphone</code></p></td></tr><tr><td>Có</td><td><p>Đối với yêu cầu nền tảng CTV, PC hoặc Console, sẽ tính cả bất kỳ nền tảng nào sau đây: </p><p><span> </span><code>nativepc</code><span>, </span><code>playstation</code><span>, </span><code>roku</code><span>, </span><code>steam</code><span>, </span><code>webos</code><span>, <br/></span><code>vidaa</code><span>,</span><code>tizen</code><span>, </span><code>smartcast</code><span>, </span><code>chatgpt</code><span>, </span><code>battlenet</code><span>, <br/></span><code>quest</code><span>, </span><code>switch</code><span>, </span><code>xbox</code><span>, </span><code>epic</code></p></td></tr></tbody></table>

#### Đối tượng Subject\_identities

| Loại đối tượng | **Bắt buộc** | **Mô tả** |
| --- | --- | --- |
| identity\_type | Có | <ul><li>Loại danh tính trong định dạng chuỗi cho các nền tảng `android`, `ios`, `web`, `windowsphone` là bất kỳ loại nào sau đây:<ul><li>ios\_advertising\_id</li><li>android\_advertising\_id</li><li>fire\_advertising\_id</li><li>microsoft\_advertising\_id</li><li>appsflyer\_id</li></ul></li></ul><ul><li>Loại nhận dạng ở định dạng chuỗi cho nền tảng `CTV`, `PC` và `Console`:<ul><li>appsflyer\_id</li><li>customer\_user\_id (CUID)</li></ul></li></ul><ul><li>Ví dụ: `android_advertising_id`</li></ul> |
| identity\_value | Có | <ul><li>Định dạng: Chuỗi</li><li>Ví dụ: "a7551968-d5d6-44b2-9831-815ac9017798"</li></ul> |
| identity\_format | Có | <ul><li>Phương thức được sử dụng để mã hóa identity\_value: chỉ hỗ trợ giá trị `chưa xử lý`:</li><li>Ví dụ: "chưa xử lý"</li></ul> |

### Ví dụ: yêu cầu xóa GDPR

**Ví dụ về yêu cầu xóa đối với các nền tảng `android`, `ios`, `web`, `windowsphone`:**

```bash
curl --location --request POST 'https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \  
--header 'Authorization: Bearer %AuthTokenv2% \
--data-raw '{ 
 "subject_request_id":"f4e5a271-f25e-4107-b681-************",
 "subject_request_type":"erasure",
 "submitted_time":"2020-07-05T10:00:00Z",
 "platform": "android",
 "subject_identities":[ 
  { 
   "identity_type":"android_advertising_id",
   "identity_value":"55*****-****-****-************",
   "identity_format":"raw"
  }
 ],
 "api_version":"0.1",
 "property_id":"com.*********.*******.********",
 "status_callback_urls":[ 
  "https://examplecontroller.com/opengdpr_callbacks"
 ]
}'
```

**Ví dụ về yêu cầu xóa đối với nền tảng`CTV`, `PC` và `Console`:**

```bash
curl --location --request POST 'https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \  
--header 'Authorization: Bearer %AuthTokenv2% \
--data-raw '
{"requester": "test@email.com",
"subject_request_id":"valid-uuid4-string",
"subject_request_type":"erasure",
"submitted_time":"2020-07-05T10:00:00Z",
"subject_identities":[ 
 { 
  "identity_type":"appsflyer_id",
  "identity_value":"valid-appsflyer-id-string",
  "identity_format":"raw"
 }
],
"api_version":"0.1",
"property_id":"app-id",
"platform": "roku",
"status_callback_urls":[ 
 "https://examplecontroller.com/opengdpr_callbacks"
 ]
}'
```

<div id="gdpr-erasure-request-code-example" />

### Ví dụ về mã yêu cầu xóa của GDPR

<Tabs>
<Tab title="Java">

```java
/* 
using the okhttp package install from maven
https://mvnrepository.com/artifact/com.squareup.okhttp3/okhttp
 */

import okhttp3.*;
import java.io.IOException;

public class GdprSendRequest {
 public static void main(String[] args){

  OkHttpClient client = new OkHttpClient();
  RequestBody body = RequestBody.create(null, "" +
  "{\r\n\"subject_request_id\": \"\"," +
  "\r\n\"subject_request_type\": \"erasure\"," +
  "\r\n\"platform\": \"android\"," +
  "\r\n\"submitted_time\": \"2018-11-02T15:00:00Z\"," +
  "\r\n\"subject_identities\": [\r\n" +
  "{\r\n\"identity_type\": \"android_advertising_id\"," +
  "\r\n\"identity_value\": \"\"," +
  "\r\n\"identity_format\": \"raw\"\r\n}" +
   "\r\n]," +
   "\r\n\"property_id\": \"com.example.application\"}");

  Request request = new Request.Builder()
  .url("https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/opendsr_requests")
  .post(body)
  .addHeader("Content-Type", "application/json")
  .addHeader("Accept", "application/json")
  .addHeader("Authorization: Bearer", "")
  .build();

  try {
   Response response = client.newCall(request).execute();
   System.out.println(response.code());
   System.out.println(response.body().string());
   System.exit(0);
  } catch (IOException e) {
   e.printStackTrace();
   System.exit(1);
  }
 }
}
```

</Tab>

<Tab title="Python">

```python
""" using the requests python package, 
install using pip install requests """

import requests
import json
headers = {
 "Content-Type": "application/json",
 "Accept": "application/json",
 "Authorization: Bearer": ""
}

body = {
 "subject_request_id": "", 
 "subject_request_type": "erasure", 
 "submitted_time": "2018-10-02T15:00:00Z",
 "platform": "android", 
 "subject_identities": [
  { "identity_type": "android_advertising_id", 
   "identity_value": "", 
   "identity_format": "raw" }
  ], 
 "property_id": "com.example.application" 
} 
body = json.dumps(body) 
res = requests.request("POST", 
"https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests", 
headers=headers, data=body, params=params) 
print(res.text)
```

</Tab>

<Tab title="Node.js">

```javascript
/* using the request npm package, 
install using npm install request */

var request = require("request");
var options = { method: 'POST',
 url: 'https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests',
 headers: 
 { Accept: 'application/json',
  'Content-Type': 'application/json',
  'Authorization: Bearer': '' },
 body:
 { subject_request_id: '',
  subject_request_type: 'erasure',
  submitted_time: '2018-10-02T15:00:00Z',
  platform: 'android',
  subject_identities: 
  [ { identity_type: 'android_advertising_id',
   identity_value: '',
   identity_format: 'raw' } ],
 property_id: 'com.example.application'
 },
 json: true };
request(options, function (error, response, body) {
 if (error) throw new Error(error);

 console.log(body);
});
```

</Tab>

<Tab title="C#">

```csharp
using System;
 using RestSharp;
 namespace CS
 {
  class Gdpr
  {
   static void Main(string[] args)
   {
 		var url = "https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests";
   var client = new RestClient(url);
   var request = new RestRequest(Method.POST);
   request.AddHeader("Content-Type", "application/json");
   request.AddHeader("Accept", "application/json");
   request.AddHeader("Authorization: Bearer", "")
   var body = "{\r\n\"subject_request_id\": \"\"," + 
    "\r\n \"subject_request_type\": \"erasure\"," + 
    "\r\n \"submitted_time\": \"2018-11-02T15:00:00Z\"," +
    "\r\n \"platform\": \"android\"," +
    "\r\n \"subject_identities\": [\r\n" +
    "{ \r\n \"identity_type\": \"android_advertising_id\"," +
    "\r\n \"identity_value\": \"\"," + 
    "\r\n \"identity_format\": \"raw\"\r\n }" + 
    "\r\n ]," + 
    "\r\n \"property_id\": \"com.example.application\"}";

    request.AddParameter("undefined", body,ParameterType.RequestBody);
    IRestResponse response = client.Execute(request);
    // handle response by reading response.StatusCode
    Console.WriteLine(response.Content);
   }
  }
```

</Tab>
</Tabs>

</Accordion>

<div id="2-status-request" />

<Accordion title="2. Yêu cầu trạng thái">

Mỗi yêu cầu GDPR đã gửi đi, sau này có thể được truy vấn về trạng thái của nó, bằng cách nêu rõ `subject_request_id`. Có bốn loại trạng thái được hỗ trợ:

1. ***đang chờ xử lý*** - Một yêu cầu chính xác đã được nhận và hiện đang xếp hàng đợi
2. ***in\_progress*** - Yêu cầu hiện đang được thực hiện
3. ***đã hoàn thành*** - Yêu cầu đã được hoàn thành
4. ***đã hủy*** - Yêu cầu đã bị hủy

### Định dạng yêu cầu trạng thái

Yêu cầu trạng thái có thể được gửi qua HTTP GET tới điểm cuối dưới đây:

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

### Ví dụ về phản hồi trạng thái

```http
HTTP/1.1 200 OK
Content-Type: application/json
X-OpenGDPR-Processor Domain: example processor.com
X-OpenGDPR-Signature:
kiGlog3PdQx+FQmB8wYwFC1fekbJG7Dm9WdqgmXc9uKkFRSM4uPzylLi7j083461xLZ+mUloo3tpsmyIZpt5eMfgo7ejXPh6lqB4ZgCnN6+1b6Q3NoNcn/+11UOrvmDj772wvg6uIAFzsSVSjMQxRs8LAmHqFO4cF2pbuoPuK2diHOixxLj6+t97q0nZM7u3wmgkwF9EHIo3C6G1SI04/odvyY/VdMZgj3H1fLnz+X5rc42/wU4974u3iBrKgUnv0fcB4YB+L6Q3GsMbmYzuAbe0HpVA17ud/bVoyQZAkrW2yoSy1x4Ts6XKba6pLifIHf446Bubsf5r7x1kg6Eo7B8zur666NyWOYrglkOzU4IYO8ifJFRZZXazOgk7ggn9obEd78GBc3kjKKZdwaCrLx7WV5y9TMDCf+2FILOJM/MwTUy1dLZiaFHhGdzld2AjbjK1CfVzyPssch0iQYYtbR49GhumvkYl11S4oDfu0c3t/xUCZWg0hoR3XL3B7NjcrlrQinB1KbyTNZccKR0F4Lk9fDgwTVkrAg152UqPyzXxpdzXjfkDkSEgAevXQwVJWBNf18bMIEgdH2usF/XauQoyrne7rcMIWBISPgtBPj3mhcrwscjGVsxqJva8KCVCKD/4Axmo9DISib5/7A6uczJxQG2Bcrdj++vQqK2succ=
{
 "controller_id":"example_controller_id",
 "expected_completion_time":"2018-11-01T15:00:01Z",
 "subject_request_id":"a7551968-d5d6-44b2-9831-815ac9017798",
 "request_status":"pending",
}
```

### Postback trạng thái

Như được mô tả trong Quy trình Yêu cầu GDPR ở trên, khi trạng thái của yêu cầu GDPR thay đổi, từ ***pending*** thành ***in\_progress*** thành ***completed***, AppsFlyer gửi một postback GDPR tới các điểm cuối yêu cầu, được xác định với thuộc tính **status\_callback\_urls.**

Ví dụ về đăng lại trạng thái:

```http
POST /opengdpr_callbacks HTTP/1.1
Host: examplecontroller.com
Content-Type: application/json
X-OpenGDPR-Processor Domain: gdpr.appsflyer.com
X-OpenGDPR-Signature: kiGlog3PdQx+FQmB8wYwFC1fekbJG7Dm9WdqgmXc9uKkFRSM4uPzylLi7j083461xLZ+mUloo3tpsmyIZpt5eMfgo7ejXPh6lqB4ZgCnN6+1b6Q3NoNcn/+11UOrvmDj772wvg6uIAFzsSVSjMQxRs8LAmHqFO4cF2pbuoPuK2diHOixxLj6+t97q0nZM7u3wmgkwF9EHIo3C6G1SI04/odvyY/VdMZgj3H1fLnz+X5rc42/wU4974u3iBrKgUnv0fcB4YB+L6Q3GsMbmYzuAbe0HpVA17ud/bVoyQZAkrW2yoSy1x4Ts6XKba6pLifIHf446Bubsf5r7x1kg6Eo7B8zur666NyWOYrglkOzU4IYO8ifJFRZZXazOgk7ggn9obEd78GBc3kjKKZdwaCrLx7WV5y9TMDCf+2FILOJM/MwTUy1dLZiaFHhGdzld2AjbjK1CfVzyPssch0iQYYtbR49GhumvkYl11S4oDfu0c3t/xUCZWg0hoR3XL3B7NjcrlrQinB1KbyTNZccKR0F4Lk9fDgwTVkrAg152UqPyzXxpdzXjfkDkSEgAevXQwVJWBNf18bMIEgdH2usF/XauQoyrne7rcMIWBISPgtBPj3mhcrwscjGVsxqJva8KCVCKD/4Axmo9DISib5/7A6uczJxQG2Bcrdj++vQqK2succ=

{
"controller_id":"example controller id at the processor",
"expected_completion_time":"2018-11-01T15:00:01Z",
"status_callback_url":"https://examplecontroller.com/opengdpr_callbacks",
"Subject_request_id":"a7551968-d5d6-44b2-9831-815ac9017798",
"Request_status":"pending"
}
```

### Xác thực đăng lại

**Để xác thực tính xác thực của các đăng lại gửi đến**:

1. Tạo danh sách cho phép gồm tất cả các miền của bộ xử lý mà bạn cho phép thực hiện lệnh gọi lại.
2. Nếu giá trị tiêu đề của `X-OpenGDPR-Processor-Domain` nằm trong danh sách cho phép của bạn, hãy tìm nạp chứng chỉ.
   * URL chứng chỉ là giá trị `processor_certificate` trong nội dung phản hồi `/discovery` .
   * Bạn cũng có thể tìm nạp chứng chỉ trực tiếp từ điểm cuối AppsFlyer bằng cách sử dụng mã thông báo API V2 làm mã thông báo truy cập trong tiêu đề cấp quyền: `GET https://hq1.appsflyer.com/api/gdpr/v1/certificate`
3. Xác thực chứng chỉ bằng thư viện để xác nhận rằng chứng chỉ:
   1. Được cấp bởi một cơ quan đáng tin cậy.
   2. Được cấp cho cùng một chuỗi được cung cấp trong giá trị tiêu đề `X-OpenGDPR-Processor-Domain`.
   3. Chưa hết hạn sử dụng.
4. Sau khi bạn xác nhận chứng chỉ hợp lệ, hãy sử dụng chứng chỉ đó để xác thực tiêu đề `X-OpenGDPR-Signature` đối với nội dung yêu cầu thô. AppsFlyer sử dụng RSA SHA256 làm thuật toán ký.
5. Nhận phản hồi trong tiêu đề trạng thái:
   1. `202 Accepted` nếu xác thực thành công.
   2. `401 Unauthorized` nếu chữ ký không xác thực được hoặc miền của bộ xử lý không có trong danh sách cho phép của bạn.

</Accordion>

<div id="3-report-request" />

<Accordion title="3. Yêu cầu báo cáo">

Khi **Yêu cầu Truy cập** hoặc **Yêu cầu Khả năng Di chuyển** đã được hoàn tất, bạn có thể tải xuống báo cáo qua HTTP GET tới điểm cuối sau:

```http
https://hq1.appsflyer.com/api/gdpr/v1/download/[REQUEST_ID]
```

Báo cáo được tạo sẽ khả dụng trong mười bốn ngày kể từ thời điểm hoàn thành.

</Accordion>

<div id="4-discovery-requestin-process" />

<Accordion title="4. Quá trình yêu cầu khám phá">

Để tìm hiểu về các định dạng được AppsFlyer hỗ trợ, có thể gửi yêu cầu phát hiện qua HTTP GET tới điểm cuối sau:

```http
https://hq1.appsflyer.com/api/gdpr/v1/discovery
```

### Ví dụ về yêu cầu phát hiện

```http
HTTP/1.1 200 OK
Content-Type: application/json
{
 "api_version": "0.1",
 "supported_identities": [
 {
  "identity_type": "android_advertising_id",
  "identity_format": "raw"
 },
 ],
 "supported_subject_request_types": [
 "erasure", "access", "portability", "rectification"
 ],
 "processor_certificate": "https://exampleprocessor.com/cert.pem"
}
```

</Accordion>

<div id="5-cancellation-request" />

<Accordion title="5. Yêu cầu Hủy">

Có thể hủy yêu cầu GDPR, dựa trên `subject_request_id`, nhưng chỉ hủy được trong gia đoạn ***chờ xử lý.***

Để gửi một HTTP DELETE với `subject_request_id`:

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

### Phản hồi Hủy

Khi nhận được yêu cầu hủy GDPR, AppsFlyer sẽ trả về phản hồi HTTP có mã trạng thái 202 và một số thông số khác.

Sau khi đã hủy bỏ yêu cầu, AppsFlyer sẽ gửi một đăng lại với trạng thái ***đã hủy***.

</Accordion>

<div id="6-gdpr-requests-test-api" />

<Accordion title="6. API Kiểm tra yêu cầu GDPR">

API này của AppsFlyer là một API kiểm tra của API Yêu cầu GDPR.

### Nó hoạt động như thế nào?

API kiểm tra hoạt động như sau:

1. Sau khi yêu cầu GDPR được thực hiện, yêu cầu sẽ ngay lập tức được đặt vào trạng thái 'Đang chờ xử lý'. Để phục vụ mục đích kiểm tra, trạng thái này thay đổi sau mỗi 30 giây.

2. Nếu một điểm cuối cho một postback trạng thái đã được chèn vào yêu cầu GDPR, một postback đầu tiên được gửi ngay sau khi yêu cầu và thêm hai postback trạng thái được gửi sau 30 giây.

**Điểm cuối Kiểm tra Yêu cầu GDPR**: POST

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub
```

**Điểm cuối Kiểm tra Yêu cầu Trạng thái**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**Điểm cuối Kiểm tra Yêu cầu Khám phá**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/discovery
```

**Điểm cuối Kiểm tra Yêu cầu Hủy**: DELETE

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**Điểm cuối Kiểm tra Chứng chỉ**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stubcertificate
```

**Điểm cuối Kiểm tra Báo cáo Truy cập/Khả năng Di chuyển**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/download/:requestId
```

> 📘 **Lưu ý**
>
> * Mã thông báo API V2 hợp lệ phải được chèn vào tiêu đề yêu cầu như sau: `'Authorization': 'Bearer %AuthTokenV2%'`
> * Trong thuộc tính ‘property\_id’, ID Ứng dụng phải thuộc về chủ tài khoản (theo mã thông báo API).

</Accordion>

<div id="7-request-logs" />

<Accordion title="7. Nhật ký yêu cầu">

Người dùng quản trị có thể truy cập các yêu cầu GDPR được gửi trong Bảng điều khiển Nhật ký.

Đối với các yêu cầu truy cập và khả chuyển đã hoàn tất, bạn cũng có thể tải xuống báo cáo từ bên trong bảng điều khiển này.

Để truy cập Bảng điều khiển Nhật ký:

1. 1.  Truy cập bảng điều khiển chính và nhấp vào tên người dùng của bạn.
2. Nhấp vào **Nhật ký** và cửa sổ sau đây sẽ mở ra:

![GDPR_Table.png](https://files.readme.io/5c2b2695b5c273e16a0396f0df2d227a0a0f61af6ad0626c0a911b77edc6a0d2-13949567038481.png)

</Accordion>

<div id="8-gdpr-api-return-codes-and-error-messages" />

<Accordion title="8. Thông báo lỗi và mã trả về cho API GDPR">

Thông báo lỗi và mã trả về HTTP cho API GDPR được trình bày chi tiết trong phần này.

#### Mã trả về cho API GDPR

| Mã trả về | Mô tả |
| --- | --- |
| 201 | Đã tạo |
| 202 | Đã nhận yêu cầu hủy |
| 400 | Lỗi yêu cầu. Phần nội dung có chứa mã lỗi và thông báo như được liệt kê trong bảng bên dưới. |

### Mã trả về HTTP 400 - lỗi yêu cầu

Thông báo có mã trả về là 400 có chứa JSON kèm theo mã lỗi và thông báo.

`{ "error":{ "code":400, "af_gdpr_code": "%AF error code%", "message":"%error message text%"}}`

#### Thông báo lỗi yêu cầu có mã trả về 400

| Mã lỗi | Mô tả lỗi (thông báo) |
| --- | --- |
| e111 | Vượt quá giới hạn lưu lượng |
| e211 | Không thể hủy yêu cầu có trạng thái không hợp lệ |
| e212 | Yêu cầu này không được phép. Đang xóa mã định danh. |
| e213 | Đã tồn tại yêu cầu này |
| e214 | Không tìm thấy yêu cầu |
| e311 | content-type yêu cầu không hợp lệ |
| e312 | Phiên bản API không hợp lệ |
| e313 | subject\_request\_id không hợp lệ |
| e314 | Định dạng submitted\_time không hợp lệ |
| e315 | Độ dài status\_callback\_url không hợp lệ |
| e316 | Định dạng status\_callback\_url không hợp lệ |
| e317 | Định dạng app\_id không hợp lệ |
| e318 | identity\_type không hợp lệ |
| e319 | Nền tảng ứng dụng không khớp với hình thức nhận dạng |
| e320 | identity\_type không hợp lệ |
| e321 | Người dùng LAT không được hỗ trợ thông qua api |
| e322 | subject\_request\_type không hợp lệ |
| e323 | Định dạng subject\_identities không hợp lệ |
| e324 | Độ dài subject\_identities không hợp lệ |
| e325 | Giá trị subject\_identities không hợp lệ |
| e411 | AppID không chính xác hoặc không thuộc về tài khoản của bạn |
| e412 | Không có quyền để hủy yêu cầu xóa |
| e413 | Không có quyền để xem yêu cầu |
| e511 | Đã xảy ra sự cố nội bộ, vui lòng chờ 60 phút và thử lại. Nếu sự cố vẫn tiếp diễn, vui lòng liên hệ bộ phận hỗ trợ AppsFlyer. support@AppsFlyer.com |

</Accordion>

## Đặc điểm và hạn chế

* Giới hạn tốc độ: 80 yêu cầu GDPR cứ sau 2 phút ở cấp tài khoản (tương đương với 2.400 yêu cầu mỗi giờ và 57.600 mỗi ngày). **Số yêu cầu vượt quá giới hạn này sẽ không thành công.**
* UI hiển thị tối đa 200 yêu cầu được chọn ngẫu nhiên.
* Việc kiểm tra trạng thái của yêu cầu từ hơn 60 ngày trước sẽ trả về "không tìm thấy yêu cầu".

<div data-zendesk-anchors="privacy-regulations=quy-%C4%91%E1%BB%8Bnh-v%E1%BB%81-quy%E1%BB%81n-ri%C3%AAng-t%C6%B0 h_01HB866TQ0AWHQ9659Q8Q4XMQM=quy-%C4%91%E1%BB%8Bnh-v%E1%BB%81-quy%E1%BB%81n-ri%C3%AAng-t%C6%B0 the-opendsr-initiative=s%C3%A1ng-ki%E1%BA%BFn-opendsr h_01HB866TQ0R18S4GCH3KPGNJHD=s%C3%A1ng-ki%E1%BA%BFn-opendsr definitions=c%C3%A1c-%C4%91%E1%BB%8Bnh-ngh%C4%A9a h_01HB866TQ06XV2AJDMA3M5Q5KK=c%C3%A1c-%C4%91%E1%BB%8Bnh-ngh%C4%A9a dsr-requirements=y%C3%AAu-c%E1%BA%A7u-dsr h_01HB866TQ0JNEZTHQ7BR1TMD5M=y%C3%AAu-c%E1%BA%A7u-dsr appsflyer-gdpr-requests-api=gdpr-c%E1%BB%A7a-appsflyer-y%C3%AAu-c%E1%BA%A7u-api h_01HB866TQ0HNFGF9QTJNT792N7=gdpr-c%E1%BB%A7a-appsflyer-y%C3%AAu-c%E1%BA%A7u-api h_01HB866TQ0ATDT8B000Z70MBTH=1-gdpr-request gdpr-request-flow=quy-tr%C3%ACnh-y%C3%AAu-c%E1%BA%A7u-gdpr h_01HB866TQ0FCZGQ1DWENVSWHSG=quy-tr%C3%ACnh-y%C3%AAu-c%E1%BA%A7u-gdpr gdpr-request-format=%C4%91%E1%BB%8Bnh-d%E1%BA%A1ng-y%C3%AAu-c%E1%BA%A7u-gdpr h_01HB866TQ0GC7V1081GT53TWEZ=%C4%91%E1%BB%8Bnh-d%E1%BA%A1ng-y%C3%AAu-c%E1%BA%A7u-gdpr parameters=tham-s%E1%BB%91 h_01HB866TQ0CFAC0X2Y98B4EE5Q=tham-s%E1%BB%91 subject_identities-objects=%C4%91%E1%BB%91i-t%C6%B0%E1%BB%A3ng-subject_identities h_01HB866TQ02HMKJMKKPHHR4CMN=%C4%91%E1%BB%91i-t%C6%B0%E1%BB%A3ng-subject_identities example-gdpr-erasure-request=v%C3%AD-d%E1%BB%A5-y%C3%AAu-c%E1%BA%A7u-x%C3%B3a-gdpr h_01HB866TQ1CT316PTFBJC59C79=v%C3%AD-d%E1%BB%A5-y%C3%AAu-c%E1%BA%A7u-x%C3%B3a-gdpr h_01HB866TQ1D7290A6G29Q4HDE7=v%C3%AD-d%E1%BB%A5-v%E1%BB%81-m%C3%A3-y%C3%AAu-c%E1%BA%A7u-x%C3%B3a-c%E1%BB%A7a-gdpr h_01HB866TQ15M1897AV5W099SFV=2-status-request status-request-format=%C4%91%E1%BB%8Bnh-d%E1%BA%A1ng-y%C3%AAu-c%E1%BA%A7u-tr%E1%BA%A1ng-th%C3%A1i h_01HB866TQ1YEZZ4M6QMHTKCEGX=%C4%91%E1%BB%8Bnh-d%E1%BA%A1ng-y%C3%AAu-c%E1%BA%A7u-tr%E1%BA%A1ng-th%C3%A1i status-response-example=v%C3%AD-d%E1%BB%A5-v%E1%BB%81-ph%E1%BA%A3n-h%E1%BB%93i-tr%E1%BA%A1ng-th%C3%A1i h_01HB866TQ1M7G7JNH0V7TEVFYY=v%C3%AD-d%E1%BB%A5-v%E1%BB%81-ph%E1%BA%A3n-h%E1%BB%93i-tr%E1%BA%A1ng-th%C3%A1i status-postbacks=postback-tr%E1%BA%A1ng-th%C3%A1i h_01HB866TQ1109WJ2J13D8FM8KX=postback-tr%E1%BA%A1ng-th%C3%A1i validate-postback=x%C3%A1c-th%E1%BB%B1c-%C4%91%C4%83ng-l%E1%BA%A1i h_01HB866TQ1YG0B6JDEQ2KMFEN0=x%C3%A1c-th%E1%BB%B1c-%C4%91%C4%83ng-l%E1%BA%A1i h_01HB866TQ1TYQWZ7492H0DKWB7=3-report-request h_01HB866TQ1CH06PRJ78MHE7ZG0=4-discovery-requestin-process discovery-response-example=v%C3%AD-d%E1%BB%A5-v%E1%BB%81-y%C3%AAu-c%E1%BA%A7u-ph%C3%A1t-hi%E1%BB%87n h_01HB866TQ1AJCSS2442EEWA19X=v%C3%AD-d%E1%BB%A5-v%E1%BB%81-y%C3%AAu-c%E1%BA%A7u-ph%C3%A1t-hi%E1%BB%87n h_01HB866TQ1R8C9G4VH085897ZQ=5-cancellation-request cancellation-response=ph%E1%BA%A3n-h%E1%BB%93i-h%E1%BB%A7y h_01HB866TQ1F72KP3S55ZJYC8Y7=ph%E1%BA%A3n-h%E1%BB%93i-h%E1%BB%A7y h_01HB866TQ1Y35SZVFSTPG3ZJDH=6-gdpr-requests-test-api how-does-it-work=n%C3%B3-ho%E1%BA%A1t-%C4%91%E1%BB%99ng-nh%C6%B0-th%E1%BA%BF-n%C3%A0o h_01HB866TQ1KFRGX7NZCSJWVW0T=n%C3%B3-ho%E1%BA%A1t-%C4%91%E1%BB%99ng-nh%C6%B0-th%E1%BA%BF-n%C3%A0o h_01HB866TQ1W6X6NSEA6ZXAE6AG=l%C6%B0u-%C3%BD h_01HB866TQ1H8BKVGP5PFQYVBAA=7-request-logs h_01HB866TQ139BREE45W1FGTT3K=8-gdpr-api-return-codes-and-error-messages gdpr-api-return-codes=m%C3%A3-tr%E1%BA%A3-v%E1%BB%81-cho-api-gdpr h_01HB866TQ128R2TSHS4JTCQK70=m%C3%A3-tr%E1%BA%A3-v%E1%BB%81-cho-api-gdpr http-return-code-400-bad-request=m%C3%A3-tr%E1%BA%A3-v%E1%BB%81-http-400---l%E1%BB%97i-y%C3%AAu-c%E1%BA%A7u h_01HB866TQ1A51STZQCJC5TV65X=m%C3%A3-tr%E1%BA%A3-v%E1%BB%81-http-400---l%E1%BB%97i-y%C3%AAu-c%E1%BA%A7u return-code-400-bad-request-messages=th%C3%B4ng-b%C3%A1o-l%E1%BB%97i-y%C3%AAu-c%E1%BA%A7u-c%C3%B3-m%C3%A3-tr%E1%BA%A3-v%E1%BB%81-400 h_01HB866TQ10MAMTS9WB0CKN55V=th%C3%B4ng-b%C3%A1o-l%E1%BB%97i-y%C3%AAu-c%E1%BA%A7u-c%C3%B3-m%C3%A3-tr%E1%BA%A3-v%E1%BB%81-400 limitations=%C4%91%E1%BA%B7c-%C4%91i%E1%BB%83m-v%C3%A0-h%E1%BA%A1n-ch%E1%BA%BF h_01HB866TQ1PXGRX5JRHRSCT0EN=%C4%91%E1%BA%B7c-%C4%91i%E1%BB%83m-v%C3%A0-h%E1%BA%A1n-ch%E1%BA%BF" />
