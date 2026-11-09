---
title: 发送 OpenDSR API 请求
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
  edited_at: '2026-10-14T10:09:42Z'
  id: 11332840660625
  locale: zh-cn
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/zh-cn/articles/11332840660625
---
> **概要：** 本文供AppsFlyer客户（通常称为广告主或应用所有者）使用。应用所有者可通过在平台上通过OpenDSR（数据主体请求）API来应用使用与归因情况，以满足相关数据保护法规的合规要求。相关法规包括：GDPR（欧洲《通用数据保护条例》）、CCPA（美国加州《消费者隐私法案》）、LGPD（巴西《通用数据保护法》）、PDPA（泰国《个人数据保护法》）、PIPA（韩国《个人信息保护法》）。

**法律提示：** *以下内容仅供参考，不可作为法律意见使用。请咨询法律顾问及其他专业顾问，以明确GDPR、CCPA或其他相关法律是否适用。* 您与AppsFlyer之间的隐私关系受<Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy">《AppsFlyer服务隐私政策》</Anchor>约束。如果您对我们的服务隐私政策有任何疑问，或需要联系我们的数据保护负责人，请发邮件至**privacy@appsflyer.com**。为帮助您遵守《通用数据保护条例》（General Data Protection Regulation）第27条的规定，特此提供AppsFlyer欧盟境内代表人的联系信息：**AppsFlyer Germany GmbH, Schönhauser Allee 180, 10119 Berlin, Germany（联系方式：** privacy@appsflyer.com/strong>*；+49-30-166373500）。*

<div id="privacy-regulations" />

## 隐私法规

本文提及的隐私法规包括下表中的相关法规：

| 法规 | 图标 | 说明 |
| --- | --- | --- |
| GDPR | ![GDPR.png](https://files.readme.io/c3eb63a14b95bda24478f1d8fec75bcc59789157c4e53ffb44ab77ccd6dfe091-12830387561233.png) | 《通用数据保护条例》 (GDPR) 是欧盟法律中关于欧盟公民数据保护和隐私的一项条例。 |
| CCPA | ![CCPA.png](https://files.readme.io/57988a70f4e8395b9562fce9e424348cd7d61401ec7ca0ff32de518a093eb4dc-12830389364241.png) | 《加州消费者隐私法案》 |
| LGPD | ![LGPD.png](https://files.readme.io/4e50bdc8e83db49b4eb0d84f757816ebc1d0e461ae8792af9ab48d7e51d20af3-12830406815633.png) | 《一般数据保护法》 |
| PDPA | ![6137_Privacy_Shield_Thailand-01.png](https://files.readme.io/90833957690e7a52eb43b330d34a85c67af7a6c071b8ac79dec0733ec9aafcfc-12830408352657.png) | 《个人数据保护法》 |

在本文中，隐私法规、GDPR、CCPA、LGPD、PDPA等术语可互换使用。

<div id="the-opendsr-initiative" />

### OpenDSR倡议

为了响应和处理数据主体根依据隐私法规提交的请求，AppsFlyer联合mParticle、Amplitude和Braze推出了OpenGSR协议（原OpenGDPR）。

OpenGSR是一个统一的开源框架，旨在技术公司之间的合作, 以公正透明地使用消费者数据。该框架使得供应商能够在多个系统中执行数据隐私操作, 以处理和存储客户数据。

<Anchor target="_blank" href="https://www.appsflyer.com/company/newsroom/pr/opengdpr-initiative/">进一步了解 OpenDSR 倡议</Anchor>。

<div id="definitions" />

### 定义

| DSR术语 | AppsFlyer条款 | 说明 |
| --- | --- | --- |
| 数据对象 | 应用用户或终端用户 | 被收集数据的应用用户 |
| 数据控制者 | App所有者/广告主 | 应用所有者决定处理个人数据的目的和方式。 |
| 数据处理者 | AppsFlyer及其合作伙伴 | AppsFlyer及其合作伙伴代表数据控制人处理个人数据 |

<div id="dsr-requirements" />

### DSR要求

DSR详细说明了数据对象的强制性权利，广告主必须遵守这些权利。在API使用场景中，这些权利被转换为不同的请求类型。以下为AppsFlyer处理各类请求的方式：

| **请求类型**<br /><br />**（权利）** | **GDPR定义** | AppsFlyer处理请求 |
| --- | --- | --- |
| **访问权** | <ul><li>App用户有权知晓应用所有者是否会处理其数据、处理的原因，以及处理的时长。</li><li>如果与第三方（如AppsFlyer）共享数据，则应用程序用户有权知道这些第三方是谁。</li><li>用户有权了解被处理的数据类型。</li><li>如果存在对用户产生重大影响的自动化处理，用户有权获知。</li></ul> | 应用所有者将收到用户被处理的个人数据副本。 |
| **转移权** | App用户有权以结构化、常用和机器可读的格式 (如 CSV 文件) 接收其所有个人数据。 | 应用程序所有者会收到应用程序用户处理过的个人数据的副本。 |
| **更正权** | 如果用户发现数据不准确或不真实，有权要求更正。应用程序所有者必须删除或更正不准确或不完整的数据。 | <ul><li>AppsFlyer会删除更正请求提出之前记录的App用户数据。</li><li>此后收到的数据由AppsFlyer记录。</li></ul> |
| **删除权** | 用户有权要求删除个人数据，应用所有者需在收到请求后10天内完成。 | 删除数据 |

<div id="appsflyer-gdpr-requests-api" />

## AppsFlyer的GDPR请求API

您可以使用本文介绍的GDPR请求API来实现DSR合规处理。

* **GDPR请求： 执行上述请求类型之一："访问"、"转移"、"删除" 或 "更正"。**
* **状态请求**：查询GDPR请求的当前状态
* **查询请求**： 查询支持的API版本和数据格式
* <strong>取消请求</strong>： 取消<strong><em>pending（待处理）</em></strong>阶段的GDPR请求

应用所有者必须在应用中增加UI功能，以响应用户的请求。注意，GDPR请求每次仅限一个用户。

<div id="1-gdpr-request" />

<Accordion title="1. GDPR请求">

<div id="gdpr-request-flow" />

#### GDPR请求流程

GDPR请求类型（访问、转移、更正、删除）的处理流程如下：

1. **用户**提交请求。
2. **应用所有者**构建GDPR请求（请参见下文）并将其发送至AppsFlyer。
3. **AppsFlyer**接收请求，如果有效，将返回 “201 OK”。
4. **访问和转移请求：** 8天内完成。  
   **注意：** 此8天期限从应用所有者提交请求时开始计算。如状态将从“待处理（pending）” 变为“处理中（in progress）”，请求将在6天内完成，总计8天。  
   **删除与更正请求：**
   * 前48小时，请求处于排队和***待处理***状态。用户可在此期间取消请求。
   * 48小时后，请求状态变为***处理中***。AppsFlyer发送*状态变更*通知。此时，请求无法取消。
   * 在10天内（见后文说明），AppsFlyer完成请求，请求状态变更为***已完成***。AppsFlyer发送状态变更通知。

     * 在*删除*或*更正*的情况下，应用程序用户的数据将被删除。
     * 在*转移*或*访问*的情况下，可以在AppsFlyer控制面板中的**GDPR**部分或通过请求API（见下文）访问终端用户数据。

     **请注意：此10天期限从应用所有者提交请求时开始计算。48小时后，请求状态将变为处理中，此后将在8天内完成，总共10天。**

<div id="gdpr-request-format" />

#### GDPR请求格式

GDPR请求API可以通过HTTP POST提交到以下端点：

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests
```

对于API授权，请使用与Pull API相同的V2 API令牌。管理员可在面板的API token页面获取令牌。在请求头中加入：

<div id="parameters" />

#### 参数说明

<table><thead><tr><th><strong>参数名称</strong></th><th><strong>是否必须配置</strong></th><th><strong>说明</strong></th></tr></thead><tbody><tr><td><strong>subject_request_id</strong></td><td>是</td><td>UUID v4 字符串。由控制器提交请求时生成，可用于查询、更新或取消请求。</td></tr><tr><td><strong>subject_request_type</strong></td><td>是</td><td>表示GDPR请求类型的字符串值。支持的值：<ul><li>erasure（删除）</li><li>portability（转移）</li><li>access（访问）</li><li>rectification（更正）</li></ul></td></tr><tr><td><strong>subject_identities</strong></td><td>是</td><td><ul><li>由身份对象组成的数组，用于定义请求者的身份（见下文）。</li><li>每个请求只能包含一个主体身份。</li></ul></td></tr><tr><td><strong>submitted_time</strong></td><td>是</td><td><ul><li>数据主体原始请求时间的RFC 3339日期字符串</li><li>UTC时间戳</li></ul></td></tr><tr><td><strong>property_id</strong></td><td>是</td><td><p>表示本次请求所对应移动应用的字符串：</p><p><strong>示例</strong>：</p><ul><li> <strong>iOS</strong>: id123456789</li><li> <strong>Android</strong> ：com.example，com.publishers.name</li><li> <strong>第三方安卓商店</strong> ：com.publisher.name-channel <br/><strong>注意</strong> 应用所有者会使用Android Google Play名称来记录非商店版本的归因。在这种情况下，应使用面板中显示的常规应用名称。</li></ul></td></tr><tr><td><strong>api_version</strong></td><td>否</td><td>表示所需GDPR请求API版本的字符串版本</td></tr><tr><td><strong>status_callback_urls</strong></td><td>否（但推荐填写）</td><td><ul><li>最多可配置3个回调端点，用于接收请求状态变更通知。</li><li>仅支持https端点。</li><li>无效的URL会被拒绝。</li></ul></td></tr><tr><td rowspan="2"> <strong>platform</strong><br/><br/> </td><td>否</td><td>值应为以下受支持的DSR平台之一：<br/>可能出现的值为<code>android</code>、<code>ios</code>、<code>web</code>、<code>windowsphone</code> </td></tr><tr><td>是</td><td><p>如为CTV、PC或主机端请求，可使用以下平台： </p><p> <code>nativepc</code>, <code>playstation</code>, <code>roku</code>, <code>steam</code>, <code>webos</code>, <br/><code>vidaa</code>,<code>tizen</code>, <code>smartcast</code>, <code>chatgpt</code>, <code>battlenet</code>, <br/><code>quest</code>, <code>switch</code>, <code>xbox</code>, <code>epic</code></p></td></tr></tbody></table>

<div id="subject_identities-objects" />

#### Subject\_identities对象

| 对象类型 | **是否必须配置** | **说明** |
| --- | --- | --- |
| identity\_type | 是 | <ul><li>在`android`, `ios`, `web`, `windowsphone`平台上，身份类型（字符串格式）可为以下任一值：<ul><li>ios\_advertising\_id</li><li>android\_advertising\_id</li><li>fire\_advertising\_id</li><li>microsoft\_advertising\_id</li><li>appsflyer\_id</li><li>Customer user ID（客户用户ID，即CUID）</li></ul></li></ul><ul><li>`CTV`、`PC`和`Console`平台的可选值：<ul><li>appsflyer\_id</li><li>Customer user ID（客户用户ID，即CUID）</li></ul></li></ul><ul><li>示例：`android_advertising_id`</li></ul>**<span id="01JFVT3ATDGJXBX4VN7BHX6JB8"></span>重要提示！**<br />如需在OpenDSR API中使用CUID，应用内事件中必须带有CUID，并与`idfa`/`appsflyer_id`一同发送。支持的事件名称`event_name`包括：`Login - Complete`或`Registration - Account created`。 |
| identity\_value | 是 | <ul><li>格式：字符串</li><li>示例：“ a7551968-d5d6-44b2-9831-815ac9017798”</li></ul> |
| identity\_format | 是 | <ul><li>身份值的编码方式，目前仅支持`raw`。</li><li>示例：“ raw”</li></ul> |

<div id="zd-gdpr-erasure-request-code-example" />

<div id="example-gdpr-erasure-request" />

#### 举例来说，GDPR数据删除请求

**以下是在**`android`, `ios`, `web`, `windowsphone`**平台上的删除请求的示例：**

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

**以下是**`CTV`, `PC`**, 和**`Console`**平台上删除请求的示例：**

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

#### GDPR数据删除请求代码示例

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

<Tab title="PythonNode.jsC#">

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
</Tabs>

</Accordion>

<div id="2-status-request" />

<Accordion title="2. 状态请求">

每个已提交的GDPR请求都可以通过`subject_request_id`来查询其后续状态。支持的状态类型有四种：

1. ***待处理***-已收到正确的请求, 并且正处于等待队列中
2. ***处理中***-请求正在处理中
3. ***已完成***-请求已完成
4. ***已取消***-请求已被取消

<div id="status-request-format" />

#### 状态请求格式

状态请求可以通过HTTP GET提交到以下端点:

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

<div id="status-response-example" />

#### 状态响应示例

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

<div id="status-postbacks" />

#### 状态回传

如上GDPR请求流程所述，当GDPR请求状态改变时，从***待处理***到***处理中***到***完成***，AppsFlyer会以**status\_callback\_urls**形式给GDPR请求端点回传状态信息。

状态回传示例:

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

<div id="validate-postback" />

#### 验证回传

**要验证接收到的回传数据是否真实有效，请按以下步骤操作**：

1. 建立一个域名白名单，仅允许这些域名发起回调。
2. 如果请求头中的`X-OpenGDPR-Processor-Domain`值在白名单中，则获取其证书。
   * 证书URL位于`processor_certificate`响应体中的`/discovery`字段。
   * 您也可以直接从AppsFlyer端点获取证书，使用V2 API token作bearer token添加到Authorization请求头中：`GET https://hq1.appsflyer.com/api/gdpr/v1/certificate`
3. 使用相关库验证证书，确保证书：
   1. 由受信任的机构签发；
   2. 签发对象与`X-OpenGDPR-Processor-Domain`请求头中的值一致；
   3. 未过期。
4. 确认证书有效后，使用其验证`X-OpenGDPR-Signature`请求头与原始请求体是否匹配。AppsFlyer使用SHA256 RSA作为签名算法。
5. 检查响应状态：
   1. `202 Accepted`：验证成功。
   2. `401 Unauthorized`：签名验证失败，或处理方域名不在白名单中。

</Accordion>

<div id="3-report-request" />

<Accordion title="3. 报告请求">

当**访问请求**或**数据转移请求**完成后, 您可以通过HTTP GET将报告下载到以下端点:

```http
https://hq1.appsflyer.com/api/gdpr/v1/download/[REQUEST_ID]
```

生成的报告自完成之日起14天内有效。

</Accordion>

<div id="4-discovery-requestin-process" />

<Accordion title="4. Discovery请求-处理中">

若要了解AppsFlyer支持的格式, 可以通过HTTP GET将发现请求提交到以下端点:

```http
https://hq1.appsflyer.com/api/gdpr/v1/discovery
```

<div id="discovery-response-example" />

#### Discovery响应示例

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

<Accordion title="5. 取消请求">

用户可以基于`subject_request_id`取消GDPR请求，但仅能在***待处理***阶段取消请求。

如需提交包含`subject_request_id`的HTTP DELETE请求：

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

<div id="cancellation-response" />

#### 取消响应

当收到GDPR取消请求时, AppsFlyer会返回HTTP 202状态码及其他参数。

一旦请求被取消, AppsFlyer会发送状态为***已取消***的回传。

</Accordion>

<div id="6-gdpr-requests-test-api" />

<Accordion title="6. GDPR请求测试API">

该AppsFlyer API是AppsFlyer GDPR请求API的测试API。

<div id="how-does-it-work" />

#### 原理

测试 API 的工作原理如下:

1. GDPR请求提出后, 该请求将立即进入“待处理”状态。为达到测试目的，请求状态会每隔30秒自动变更一次。

2. 如果在GDPR请求中配置了状态回传的端点, 第一个回传会在请求提交后立即发送，随后每隔30秒再发送两次状态回传。

**GDPR请求测试端点**:POST

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub
```

**状态请求测试端点**:GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**发现请求测试端点**:GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/discovery
```

**取消请求测试端点**:删除

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**证书测试端点：** GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stubcertificate
```

**访问/数据转移报告测试端点**：GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/download/:requestId
```

<div id="note" />

> 📘 **注意**
>
> * 请求头中必须包含有效的V2 API token，格式如下：
> * 在property\_id参数中填写的App ID必须属于该API token所对应的账号所有者。

</Accordion>

<div id="7-request-logs" />

<Accordion title="7.请求日志">

管理员用户可以在日志面板（Logs Dashboard） 中查看已提交的GDPR请求。

对于已完成的访问和数据转移请求, 您也可以从该控制面板中下载报表。

访问日志控制面板：

1. 从页面顶部导航栏打开账户菜单（点击右上角的邮箱地址，打开下拉菜单）> E-GDPR日志。
2. 系统将打开以下窗口：

<Image align="center" alt="GDPR_Table.png" src="https://files.readme.io/5c2b2695b5c273e16a0396f0df2d227a0a0f61af6ad0626c0a911b77edc6a0d2-13949567038481.png" />

</Accordion>

<div id="8-gdpr-api-return-codes-and-error-messages" />

<Accordion title="8.GDPR API返回代码和错误信息">

本节详细介绍了GDPR API的HTTP返回代码和错误消息。

<div id="gdpr-api-return-codes" />

#### GDPR API返回代码

| 返回码 | 说明 |
| --- | --- |
| 201 | Created（请求已创建） |
| 202 | Cancellation request received（取消请求已接收） |
| 400 | Bad request（错误请求）。响应体中会包含错误码与错误信息，见下表。 |

<div id="http-return-code-400---bad-request" />

#### HTTP返回代码400 - 错误请求

当返回码为400时，返回的消息体会包含一个JSON，其中包含错误码和错误信息。

`{ "error": { "code":400, "af_gdpr_code": "%AF error code%", "message":"%error message text%" } }`

<div id="return-code-400-bad-request-messages" />

#### 返回代码400错误请求消息

| 错误代码 | 错误描述（消息） |
| --- | --- |
| e211 | 无法取消状态无效的请求 |
| e212 | 请求不被允许。正在对标识符进行删除。 |
| e213 | 请求已存在 |
| e214 | 未找到请求 |
| e311 | 请求的内容类型无效 |
| e312 | API版本无效 |
| e313 | subject\_request\_id无效 |
| e314 | submitted\_time格式无效 |
| e315 | status\_callback\_url长度无效 |
| e316 | status\_callback\_url格式无效 |
| e317 | app\_id格式无效 |
| e318 | identity\_type无效 |
| e319 | 应用平台与身份类型不匹配 |
| e321 | LAT用户不支持通过API提交 |
| e322 | subject\_request\_type无效 |
| e323 | subject\_identities格式无效 |
| e324 | subject\_identities长度无效 |
| e325 | subject\_identities值无效 |
| e326 | 请求体JSON格式无效 |
| e411 | AppID错误或不属于您的账号 |
| e412 | 无权限取消删除请求 |
| e413 | 无权限查看请求 |
| e511 | 内部问题，请等待60分钟后重试。如问题仍存在，请联系AppsFlyer支持：support@appsflyer.com |

</Accordion>

<div id="traits-and-limitations" />

## 特点与局限性

* **OpenDSR API请求速率限制：每分钟最多350个请求**。超过该限制会导致报错，需要重新发送请求。在限制范围内，每天最多可执行约504000个请求。
* 若查询60天前的请求，将返回“request not found”（未找到请求）。

<div data-zendesk-anchors="privacy-regulations=%E9%9A%90%E7%A7%81%E6%B3%95%E8%A7%84 h_01HB866TQ0AWHQ9659Q8Q4XMQM=%E9%9A%90%E7%A7%81%E6%B3%95%E8%A7%84 the-opendsr-initiative=opendsr%E5%80%A1%E8%AE%AE h_01HB866TQ0R18S4GCH3KPGNJHD=opendsr%E5%80%A1%E8%AE%AE definitions=%E5%AE%9A%E4%B9%89 h_01HB866TQ06XV2AJDMA3M5Q5KK=%E5%AE%9A%E4%B9%89 dsr-requirements=dsr%E8%A6%81%E6%B1%82 h_01HB866TQ0JNEZTHQ7BR1TMD5M=dsr%E8%A6%81%E6%B1%82 appsflyer-gdpr-requests-api=appsflyer%E7%9A%84gdpr%E8%AF%B7%E6%B1%82api h_01HB866TQ0HNFGF9QTJNT792N7=appsflyer%E7%9A%84gdpr%E8%AF%B7%E6%B1%82api h_01HB866TQ0ATDT8B000Z70MBTH=1-gdpr-request gdpr-request-flow=gdpr%E8%AF%B7%E6%B1%82%E6%B5%81%E7%A8%8B h_01HB866TQ0FCZGQ1DWENVSWHSG=gdpr%E8%AF%B7%E6%B1%82%E6%B5%81%E7%A8%8B gdpr-request-format=gdpr%E8%AF%B7%E6%B1%82%E6%A0%BC%E5%BC%8F h_01HB866TQ0GC7V1081GT53TWEZ=gdpr%E8%AF%B7%E6%B1%82%E6%A0%BC%E5%BC%8F parameters=%E5%8F%82%E6%95%B0%E8%AF%B4%E6%98%8E h_01HB866TQ0CFAC0X2Y98B4EE5Q=%E5%8F%82%E6%95%B0%E8%AF%B4%E6%98%8E subject_identities-objects=subject_identities%E5%AF%B9%E8%B1%A1 h_01HB866TQ02HMKJMKKPHHR4CMN=subject_identities%E5%AF%B9%E8%B1%A1 example-gdpr-erasure-request=%E4%B8%BE%E4%BE%8B%E6%9D%A5%E8%AF%B4gdpr%E6%95%B0%E6%8D%AE%E5%88%A0%E9%99%A4%E8%AF%B7%E6%B1%82 h_01HB866TQ1CT316PTFBJC59C79=%E4%B8%BE%E4%BE%8B%E6%9D%A5%E8%AF%B4gdpr%E6%95%B0%E6%8D%AE%E5%88%A0%E9%99%A4%E8%AF%B7%E6%B1%82 gdpr-erasure-request-code-example=%E4%B8%BE%E4%BE%8B%E6%9D%A5%E8%AF%B4gdpr%E6%95%B0%E6%8D%AE%E5%88%A0%E9%99%A4%E8%AF%B7%E6%B1%82 h_01HB866TQ1D7290A6G29Q4HDE7=gdpr%E6%95%B0%E6%8D%AE%E5%88%A0%E9%99%A4%E8%AF%B7%E6%B1%82%E4%BB%A3%E7%A0%81%E7%A4%BA%E4%BE%8B h_01HB866TQ15M1897AV5W099SFV=2-status-request status-request-format=%E7%8A%B6%E6%80%81%E8%AF%B7%E6%B1%82%E6%A0%BC%E5%BC%8F h_01HB866TQ1YEZZ4M6QMHTKCEGX=%E7%8A%B6%E6%80%81%E8%AF%B7%E6%B1%82%E6%A0%BC%E5%BC%8F status-response-example=%E7%8A%B6%E6%80%81%E5%93%8D%E5%BA%94%E7%A4%BA%E4%BE%8B h_01HB866TQ1M7G7JNH0V7TEVFYY=%E7%8A%B6%E6%80%81%E5%93%8D%E5%BA%94%E7%A4%BA%E4%BE%8B status-postbacks=%E7%8A%B6%E6%80%81%E5%9B%9E%E4%BC%A0 h_01HB866TQ1109WJ2J13D8FM8KX=%E7%8A%B6%E6%80%81%E5%9B%9E%E4%BC%A0 validate-postback=%E9%AA%8C%E8%AF%81%E5%9B%9E%E4%BC%A0 h_01HB866TQ1YG0B6JDEQ2KMFEN0=%E9%AA%8C%E8%AF%81%E5%9B%9E%E4%BC%A0 h_01HB866TQ1TYQWZ7492H0DKWB7=3-report-request h_01HB866TQ1CH06PRJ78MHE7ZG0=4-discovery-requestin-process discovery-response-example=discovery%E5%93%8D%E5%BA%94%E7%A4%BA%E4%BE%8B h_01HB866TQ1AJCSS2442EEWA19X=discovery%E5%93%8D%E5%BA%94%E7%A4%BA%E4%BE%8B h_01HB866TQ1R8C9G4VH085897ZQ=5-cancellation-request cancellation-response=%E5%8F%96%E6%B6%88%E5%93%8D%E5%BA%94 h_01HB866TQ1F72KP3S55ZJYC8Y7=%E5%8F%96%E6%B6%88%E5%93%8D%E5%BA%94 h_01HB866TQ1Y35SZVFSTPG3ZJDH=6-gdpr-requests-test-api how-does-it-work=%E5%8E%9F%E7%90%86 h_01HB866TQ1KFRGX7NZCSJWVW0T=%E5%8E%9F%E7%90%86 h_01HB866TQ1W6X6NSEA6ZXAE6AG=%E6%B3%A8%E6%84%8F h_01HB866TQ1H8BKVGP5PFQYVBAA=7-request-logs h_01HB866TQ139BREE45W1FGTT3K=8-gdpr-api-return-codes-and-error-messages gdpr-api-return-codes=gdpr-api%E8%BF%94%E5%9B%9E%E4%BB%A3%E7%A0%81 h_01HB866TQ128R2TSHS4JTCQK70=gdpr-api%E8%BF%94%E5%9B%9E%E4%BB%A3%E7%A0%81 http-return-code-400-bad-request=http%E8%BF%94%E5%9B%9E%E4%BB%A3%E7%A0%81400---%E9%94%99%E8%AF%AF%E8%AF%B7%E6%B1%82 h_01HB866TQ1A51STZQCJC5TV65X=http%E8%BF%94%E5%9B%9E%E4%BB%A3%E7%A0%81400---%E9%94%99%E8%AF%AF%E8%AF%B7%E6%B1%82 return-code-400-bad-request-messages=%E8%BF%94%E5%9B%9E%E4%BB%A3%E7%A0%81400%E9%94%99%E8%AF%AF%E8%AF%B7%E6%B1%82%E6%B6%88%E6%81%AF h_01HB866TQ10MAMTS9WB0CKN55V=%E8%BF%94%E5%9B%9E%E4%BB%A3%E7%A0%81400%E9%94%99%E8%AF%AF%E8%AF%B7%E6%B1%82%E6%B6%88%E6%81%AF limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01HB866TQ1PXGRX5JRHRSCT0EN=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />
