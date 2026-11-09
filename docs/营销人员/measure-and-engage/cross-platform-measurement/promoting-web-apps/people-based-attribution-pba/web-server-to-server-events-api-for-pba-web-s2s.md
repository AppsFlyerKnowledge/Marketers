---
title: PBA的Web服务器到服务器事件API（Web-S2S）
metadata:
  keywords:
    - SDK
    - Developers
    - pba
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-03-23T23:59:00Z'
  edited_at: '2026-10-14T10:08:27Z'
  id: 360006997298
  locale: zh-cn
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/zh-cn/articles/360006997298
---
> **概要：** 使用Web服务器到服务器（Web-S2S）事件API报告未通过Web SDK报告的事件和转化到PBA。

<Image align="center" alt="5107_Infographic_Web_S2S_759x270_option1.jpg" src="https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg" />

<div id="web-server-to-server-events-api-for-pba" />

## 适用于移动设备的服务器到服务器事件API

面向基于人群的归因的Web-S2S API补充了<Anchor target="_blank" href="/marketers/zh/docs/pba-web-sdk-integration-guide">Web SDK</Anchor>，允许营销人员报告发生在其网站上的事件，但超出了Web SDK的范围。例如，网站的访客（网络用户）触发了一个在线支付事件，由后端系统处理。处理后，后端使用S2S API将事件报告给AppsFlyer。

通过S2S API发送的事件：

* 与Web SDK报告的事件记录方式相似
* 如果设置为转化事件，则包含在PBA仪表板中
* 用*event\_source field*填充PBA原始数据，设置为*web S2S*

<div id="api-use-instructions" />

## API使用说明

使用以下部分创建您的API调用。

| 不可以。 | 注意事项 | 说明 |
| --- | --- | --- |
| 1 | 唯一用户ID | <ul><li>努力提供我们可用的最佳唯一用户ID。这对数据分析有重大影响。</li><li>最佳实践是发送customerUserId。如果不可用，请发送afUserId，即由WebSdk设置的网站cookie ID。</li><li>在任何时候，您将客户用户ID（<Anchor target="_blank" href="/marketers/zh/docs/customer-user-id-field-cuid">CUID</Anchor>）与[afUserId](/docs/web-server-to-server-events-api-for-pba-web-s2s#extracting-the-web-sdk-afuserid)关联时，发送包含两个ID的setCuID()消息。</li></ul> |
| 2 | 时间戳 | <ul><li>AppsFlyer对传入事件时间戳应用严格验证：</li></ul><ul><li>**迟到的事件：** 如果事件在其所属日期的24小时内到达，则接受其原始时间戳。**例如**, 如果在**周二** 23:59:59 UTC之前的任何时间发送，带有周一时间戳的事件（2025-08-18 23:59 UTC）将保留该时间戳。如果在星期二23:59:59 UTC之后发送相同的事件，时间戳将被服务器接收时间覆盖。</li><li>**未来时间戳：** 不允许有时间戳晚于实际到达时间的事件。这样的时间戳也会被服务器接收时间覆盖。</li></ul><ul><li>时间戳是基于UTC的。如有必要，在填充参数之前将本地时间转换为UTC时间。</li></ul> |
| 3 | 收入和货币 | 即使它们包含在eventValue中，您也必须填充*eventRevenueCurrency*和*eventRevenue*。这样做是因为我们在仪表板中使用它们。 |

<div id="api-basics" />

<Accordion title="API基础信息">

API实现需要在仪表板中可用的以下凭据：

* 包ID（即品牌包ID）
* (WEB\_DEV\_KEY)。

**获取凭据：**

1. 从AppsFlyer后台的顶部菜单栏中选**我的应用 >** **查看品牌套件**。  
   包的列表显示。
2. 复制并记录适当的：
   * 品牌套件 ID
   * (WEB\_DEV\_KEY)。

<div id="web-s2s-api-basics" />

#### Web S2S API基础知识

| 路径 | `https://webs2s.appsflyer.com/v1/bundleId/method`<ul><li>回传数据接收时间：应用包ID是否在仪表板中可用。</li><li>完成以下任一操作：<ul><li>[event](/docs/web-server-to-server-events-api-for-pba-web-s2s#event-method)：发送可报告的后端事件</li><li>[setCuId:](/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method) 在将afUserId与您的CUID关联时发送</li></ul></li></ul> |
| --- | --- |
| HTTP方法 | `POST` |
| 内容类型要求 | `application/json` |
| JSON的payload限制 | JSON有效负载大小：最大1KB |
| 拉取频次限制 | POST限制量：每分钟60,000个POST请求。如需提高限额，请联系您的CSM。 |
| TLS | <ul><li>TLS 1.2或更高版本</li><li><Anchor target="_blank" href="/marketers/zh/docs/appsflyer-https-ssl-encryption-policy-support#outgoing-messages-appsflyer-as-client">详见适用密码。</Anchor></li></ul> |

</Accordion>

<div id="setcuid-method" />

<Accordion title="setCuId方法">

| 方法名称 | setCuId |
| --- | --- |
| 使用场景 | 将CUID与您网站的访客关联时。例如，每当您将网络`afUserId`与您的客户用户ID匹配时。这样可以使PBA匹配来自各种来源的数据。这类似于<Anchor target="_blank" href="/marketers/zh/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid">setCustomerUserId</Anchor>在网站上的用法。 |
| 方法路径 | `https://webs2s.appsflyer.com/v1/bundleId/setcuid` |
| Payload | JSON有效负载由此处列出的参数组成。所有参数都是必需的。<ul><li>[customerUserID](/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method)</li><li>[afUserId](/docs/web-server-to-server-events-api-for-pba-web-s2s#extracting-the-web-sdk-afuserid)</li><li>[webDevKey](/docs/web-server-to-server-events-api-for-pba-web-s2s#webdevkey)</li></ul> |

<div id="curl-example-setcuid" />

#### Curl示例setCuId

```bash
curl --location --request POST 'https://webs2s.appsflyer.com/v1/bundleId/setcuid' \
--header 'Accept-Encoding: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
	"customerUserId": "1234567890abcdef",
	"afUserId":"9999999-f848-4963-a091-568f0bf9a361",
        "webDevKey" : "99999999-9999-9999-9999-999999999999"}
```

</Accordion>

<div id="event-method" />

<Accordion title="事件类型">

| 方法名称 | event\_ |
| --- | --- |
| 使用场景 | 发送 |
| 方法路径 | `https://webs2s.appsflyer.com/v1/bundleId/event` |
| 详情 | [事件方法详细信息](/docs/web-server-to-server-events-api-for-pba-web-s2s#事件方法详细信息)本节包含有效负载详细信息、Curl示例、Python示例和测试建议。 |

</Accordion>

<div id="event-method-details" />

## 事件方法详细信息

<div id="payload-parameters" />

<Accordion title="Payload参数">

有效负载参数分为用户标识符和事件参数。

* \_user\_id<mark>您必须至少发送一个用户ID参数。</mark>
* event\_根据需要发送必需参数和可选参数。

<div id="user-identifier-parameters-send-at-least-one-parameter" />

#### 用户标识符参数（至少发送一个参数）

| 用户ID参数 | 说明 |
| --- | --- |
| <span id="customeruserid"></span>customerUserId | <Anchor target="_blank" href="/marketers/zh/docs/customer-user-id-field-cuid">客户用户ID（CUID）</Anchor>是由您设置的唯一标识符。<ul><li>使用相同的标识符通过任何方式报告的事件到 AppsFlyer。这意味着在 Web SDK、移动 SDK 和 S2S API 中使用相同的标识符。</li><li><Anchor target="_blank" href="/marketers/zh/docs/pba-web-sdk-integration-guide#setting-customer-user-id-after-signup">Web SDK 客户用户 ID</Anchor></li><li>格式：字符串</li><li>例如： `"customerUserId" : "663274"`</li><li>填充原始数据字段：`customer_user_id`</li></ul> |
| <span id="afuserid"></span>afUserId | Web SDK 为每个访问您网站的用户分配的唯一用户 ID。您需要将 cookie 值传递给您的后端服务器。<ul><li>Cookie 详情：<ul><li>名称：afUserId</li><li>值：将 *afUserId* 设置为此值</li><li>域：网站域名</li></ul></li><li>示例：`"afUserId" : "unique_cookie_uuid"`</li><li>填充原始数据字段：`af_web_id`</li></ul> |

<div id="event-parameters" />

#### 事件参数

| 参数名称 | 必须配置 | 说明 |
| --- | --- | --- |
| <span id="webdevkey"></span>webDevKey | 是 | 使用仪表板上可用的 [web dev key](/docs/web-server-to-server-events-api-for-pba-web-s2s#getting-the-web-dev-key) 填充。<ul><li>示例：`"webDevKey" : "ffffffff-ffff-ffff-ffff-ffffffffffff"`</li></ul> |
| <span id="eventtype"></span>事件类型 | 是 | AppsFlyer 内部使用的事件属性标识符。始终设置为 *EVENT.*<ul><li>例如： `"eventType" : "EVENT"`</li></ul> |
| <span id="eventname"></span>eventName | 是 | <ul><li>我们使用此参数通过营销人员在 PBA 设置中设置的 <Anchor target="_blank" href="/marketers/zh/docs/pba-brand-bundles-and-settings#web-event-settings">事件转换列表</Anchor> 来区分转换和非转换事件。</li><li>确保用与营销人员的转换逻辑一致的值填充它。</li><li>格式：字符串</li><li>例如： `"eventName" : "web_purchase"`</li><li>填充原始数据字段：`event_name`</li></ul> |
| <span id="timestamp"></span>timestamp | 否 | 事件发生的时间（以毫秒为单位）。作为 <Anchor target="_blank" href="https://www.unixtimestamp.com/">Unix 时间戳</Anchor> 发送，具有 13 位数字。<ul><li>如果未发送时间戳，则使用服务器时间设置时间。</li><li>**事件延迟到达时使用当前服务器时间戳记。** 延迟是指在事件发生后的午夜 UTC 之后到达。例如，发生在星期一的事件 **必须** 在星期二的午夜 UTC 之前处理。</li><li>具有未来时间戳的事件（相对于当前服务器时间）将以服务器时间进行时间戳。</li><li>格式：Int</li><li>例如： `"timestamp" : 1584835200123`</li><li>填充原始数据字段：`event_time`</li></ul> |
| <span id="eventvalue"></span>Event value | 否 | 描述事件的事件参数映射。用于发送富应用内事件，如商品SKU、单价。<ul><li><strong>关于收入的说明！</strong>您可以用收入详情填充此参数。此外，您必须填充 *eventRevenue,* 和 *eventRevenueCurrency.*</li></ul><ul><li>格式：JSON</li><li>举例来说， 要发送 SKU ABC123，颜色为蓝色，单价为 $3.99，请将 eventValue 设置为：<br />`{"Purchase": {"sku" : "ABC123", "color": "blue", "unit_price":3.99,"currency": "USD"}}`</li><li>局限性： 1000个字符。超出部分将被截断。</li><li>填充原始数据字段： `event_value`</li></ul> |
| <span id="eventrevenuecurrency"></span>eventRevenueCurrency | 否 | 收入事件的货币代码，为三字符 <Anchor target="_blank" href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</Anchor> 货币代码。<ul><li>默认USD</li><li>格式：字符串</li><li>示例： `"eventRevenueCurrency" : "EUR"`</li><li>填充原始数据字段：`event_revenue_currency`</li></ul> |
| <span id="eventrevenue"></span>事件收入 | 否 | 分配给事件的收入（货币价值）。<br /><br />**请注意：** 如果收入在 *eventValue,* 中报告，也请在 *eventRevenue* 中报告，并填充 eventRevenueCurrency。<ul><li>允许负值。例如，退款。</li><li>格式：浮点数</li><li>示例值：`1`、`1.2`、`1234.20`</li><li>填充原始数据字段：`event_revenue`</li></ul> |
| <span id="eventcategory"></span>~~eventCategory~~ | 否 | 此参数已弃用，将在未来某个日期从系统中删除。请改用 eventValue。 |
| <span id="eventlabel"></span>~~eventLabel~~ | 否 | 此参数已弃用，将在未来某个日期从系统中删除。请改用 eventValue。 |
| <span id="referrer"></span>\_referrer | 否 | HTTP Referrer<ul><li>格式：字符串</li><li>比如</li><li>填充原始数据字段： `http_referrer`</li></ul> |
| <span id="useragent"></span>userAgent | 否 | <Anchor target="_blank" href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent">用户代理请求</Anchor> 由浏览器发送到服务器。<ul><li>在可能的情况下发送此值，因为它有助于确定设备类型。</li><li>格式：字符串</li><li>比如</li><li>填充原始数据字段： `user_agent`</li></ul> |
| <span id="ip"></span>ip | 否 | 用户 IP 地址<ul><li>在可能的情况下发送此字段的值。它有助于确定用户的 <Anchor target="_blank" href="/marketers/zh/docs/determine-user-location">地理位置</Anchor>。</li></ul><ul><li>格式：字符串</li><li>比如</li><li>填充原始数据字段： `ip`</li></ul> |

</Accordion>

<div id="curl-example" />

<Accordion title="Curl示例">

```bash
curl --location --request POST 'https://webs2s.appsflyer.com/v1/bundleId/event' \
--header 'Accept-Encoding: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
	"customerUserId": "1234567890abcdef",
	"afUserId":"9999999-f848-4963-a091-568f0bf9a361",
    "webDevKey" : "99999999-9999-9999-9999-999999999999",
    "ip" : "192.0.2.1",
	"eventType":"EVENT",
	"timestamp" : 1234567890123,
	"eventName":"my_web_event",
	"eventRevenueCurrency" : "EUR",
	"eventRevenue" : 1234.56,

		"eventValue": {
		"purchase":{
		 "shoes": "color",
		 "quantity" : "3",
		 "Revenue" : "1234.56",
		 "Currency" : "ZAR"
		}
	}

}'
```

</Accordion>

<div id="python-example" />

<Accordion title="Python示例">

```python
''' using the requests python package, install using pip install requests  '''
import requests
url = "https://webs2s.appsflyer.com/v1/bundleId/event"
payload = {
    "customerUserId": "1234567890abcdef",
    "afUserId": "9999999-f848-4963-a091-568f0bf9a361",
    "webDevKey": "99999999-9999-9999-9999-999999999999",
    "ip": "192.0.2.1",
    "eventType": "EVENT",
    "timestamp": 1234567890123,
    "eventName": "my_web_event",
    "eventRevenenuCurrency": "EUR",
    "eventRevenue": 1234.56,
    "eventValue":
        {
            "purchase":
            {
                "shoes": "color",
                "quantity": "3",
                "Revenue": "1234.56",
                "Currency": "ZAR"
            }
        }
    }
headers = {
    'Accept-Encoding': 'application/json',
    'Content-Type': 'application/json'
}
response = requests.request("POST", url, headers=headers, json=payload)
print(response.text.encode('utf8'))
```

</Accordion>

<div id="testing" />

<Accordion title="测试">

出于测试目的，发送多个事件如下：

1. 发送事件。
2. 确保您获得200 OK返回代码。如果没有，请根据返回代码和错误消息采取纠正措施。
3. 在协调世界时（UTC）午夜后等待几个小时，以查看PBA原始数据中报告的事件。您必须等待，因为PBA数据每天处理一次。

</Accordion>

<div id="additional-information" />

## 其他相关信息

<div id="getting-the-web-dev-key" />

<Accordion title="获取Web开发密钥">

**如需获取网页开发者密钥：**

1. 在AppsFlyer中，转到***我的应用***选项卡。
2. 点击*查看品牌套件。*

   <Image align="center" alt="GetWebDevKeyPba_us-en.pn" src="https://files.readme.io/e6fdec52461790183f1b12f540db51235a0bb01d3489084ed78a40e96e207495-360007733958.png" />
3. 复制所需的*Web Dev Key*

</Accordion>

<div id="extracting-the-web-sdk-afuserid" />

<Accordion title="提取Web SDK afUserID">

* `afUserId`是一个唯一标识符，由Web SDK在用户首次访问您的网站时设置。
* 如果您需要`afUserId`，请使用以下方法之一。

<div id="get-afuserid-from-the-http-cookie-header" />

#### **从HTTP cookie头中获取afUserId**

* `afUserId`由访问者的浏览器在调用您的网站时发送。
* 如有需要，从HTTP cookie头中提取。

<div id="viewing-afuserid-in-the-visitors-browser" />

#### **在访问者的浏览器中查看afUserId**

* 在访问者的浏览器中查看`afUserId`，以进行故障排除和调试。
* 为了使其可用，访问者需要至少访问一次包含Web SDK的页面。
* 包含`afUserId`的cookie是与您的域相关的第一方cookie。
* 以下程序是使用Chrome 81准备的。不同浏览器和操作系统之间可能存在一些差异。

**要从访问者的浏览器获取afUserId：**

1. 在您的浏览器中，访问您的网站。
2. 右键单击，选择 ***检查***  
   浏览器的检查元素窗口打开。

   <Image align="center" alt="S2S_inspect.jpg" src="https://files.readme.io/d1608d0085cb5333ad9631acdfb5306398f0388f42b5b3a333493daad8923385-360008059697.jpg" />
3. 转到 (A) ***应用程序*** 选项卡。
4. 在侧边菜单中，(B) 展开 Cookies。
5. 选择您的网站。如果未显示，请刷新浏览器。
6. 在 (C) ***过滤器*** 字段中，输入 `afUserId`  
   afUserID 的值显示。

</Accordion>

<div id="response-codes" />

<Accordion title="响应代码">

| 响应代码 | 响应消息 | 如何处理 |
| --- | --- | --- |
| 200 | OK |  |
| 404 | Not found（未找到） | <ul><li>检查端点</li><li>检查 Bundle ID 是否正确</li></ul> |
| 400 | Bad request（请求无效） | <ul><li>JSON 中存在错误。查看错误消息以获取详细信息。</li></ul> |

</Accordion>

<div id="troubleshooting" />

<Accordion title="问题排查">

* 问题描述HTTP 返回代码未返回  
  解决方案： AppsFlyer服务器加白

</Accordion>

<div id="release-notes" />

<Accordion title="发布说明">

<table><caption>Web SDK发布说明</caption><thead><tr><th>Date </th><th>端点版本\*</th><th>说明</th></tr></thead><tbody><tr><td>2020-05-12</td><td>1</td><td> 初始发布</td></tr><tr><td>21</td><td>1</td><td> </td></tr></tbody><tfoot><tr><td colspan="3">\* 版本号与端点版本号相关。<code>https://webs2s.appsflyer.com/v1/<var>method</var></code> </td></tr></tfoot></table>

</Accordion>

<div data-zendesk-anchors="web-servertoserver-events-api-for-pba=%E9%80%82%E7%94%A8%E4%BA%8E%E7%A7%BB%E5%8A%A8%E8%AE%BE%E5%A4%87%E7%9A%84%E6%9C%8D%E5%8A%A1%E5%99%A8%E5%88%B0%E6%9C%8D%E5%8A%A1%E5%99%A8%E4%BA%8B%E4%BB%B6api h_01HKW2YAW4HHYK27F41HC3B24Y=%E9%80%82%E7%94%A8%E4%BA%8E%E7%A7%BB%E5%8A%A8%E8%AE%BE%E5%A4%87%E7%9A%84%E6%9C%8D%E5%8A%A1%E5%99%A8%E5%88%B0%E6%9C%8D%E5%8A%A1%E5%99%A8%E4%BA%8B%E4%BB%B6api api-use-instructions=api%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E h_01HKW2YAW4DCESP3MNY9D4GTFK=api%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E h_01HKW2YAW4Z6G8HEVJJHCVG9G3=api-basics web-s2s-api-basics=web-s2s-api%E5%9F%BA%E7%A1%80%E7%9F%A5%E8%AF%86 h_01HKW2YAW4XDKZ3YGAHAP3AG2T=web-s2s-api%E5%9F%BA%E7%A1%80%E7%9F%A5%E8%AF%86 h_01HKW2YAW4YFK2WWKM0VB8AGNN=setcuid-method curl-example-setcuid=curl%E7%A4%BA%E4%BE%8Bsetcuid h_01HKW2YAW5SJFKGTNRGRKN6NCJ=curl%E7%A4%BA%E4%BE%8Bsetcuid h_01HKW2YAW5A9TJGZG08K4ZW69C=event-method event-method-details=%E4%BA%8B%E4%BB%B6%E6%96%B9%E6%B3%95%E8%AF%A6%E7%BB%86%E4%BF%A1%E6%81%AF h_01HKW2YAW53H43SCYTDXAYBDHX=%E4%BA%8B%E4%BB%B6%E6%96%B9%E6%B3%95%E8%AF%A6%E7%BB%86%E4%BF%A1%E6%81%AF h_01HKW2YAW5WDPMXDKA3X4HZBD2=payload-parameters user-identifier-parameters-send-at-least-one-parameter=%E7%94%A8%E6%88%B7%E6%A0%87%E8%AF%86%E7%AC%A6%E5%8F%82%E6%95%B0%E8%87%B3%E5%B0%91%E5%8F%91%E9%80%81%E4%B8%80%E4%B8%AA%E5%8F%82%E6%95%B0 h_01HKW2YAW5RR4Q2PCWC9717ACG=%E7%94%A8%E6%88%B7%E6%A0%87%E8%AF%86%E7%AC%A6%E5%8F%82%E6%95%B0%E8%87%B3%E5%B0%91%E5%8F%91%E9%80%81%E4%B8%80%E4%B8%AA%E5%8F%82%E6%95%B0 event-parameters=%E4%BA%8B%E4%BB%B6%E5%8F%82%E6%95%B0 h_01HKW2YAW5G46ZV4Z0CYEWB011=%E4%BA%8B%E4%BB%B6%E5%8F%82%E6%95%B0 h_01HKW2YAW56HZ0WYRWNBATB8WR=curl-example h_01HKW2YAW5A78VREGZEZ12XMPE=python-example h_01HKW2YAW59JSCCACGD2H153M5=testing additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HKW2YAW5D4N3SYA625F10YFW=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HKW2YAW5HV506YV5328ME236=getting-the-web-dev-key h_01HKW2YAW52T0KME7P2CRQ6WBR=extracting-the-web-sdk-afuserid get-afuserid-from-the-http-cookie-header=%E4%BB%8Ehttp-cookie%E5%A4%B4%E4%B8%AD%E8%8E%B7%E5%8F%96afuserid h_01HKW2YAW5FK04C3AWCXGP1XAW=%E4%BB%8Ehttp-cookie%E5%A4%B4%E4%B8%AD%E8%8E%B7%E5%8F%96afuserid viewing-afuserid-in-the-visitors-browser=%E5%9C%A8%E8%AE%BF%E9%97%AE%E8%80%85%E7%9A%84%E6%B5%8F%E8%A7%88%E5%99%A8%E4%B8%AD%E6%9F%A5%E7%9C%8Bafuserid h_01HKW2YAW5CT2WZ229KJD2FWYK=%E5%9C%A8%E8%AE%BF%E9%97%AE%E8%80%85%E7%9A%84%E6%B5%8F%E8%A7%88%E5%99%A8%E4%B8%AD%E6%9F%A5%E7%9C%8Bafuserid h_01HKW2YAW5HTV9N4ZEJJ99RBN0=response-codes h_01HKW2YAW6MG7VNQJAB1Q37K6T=troubleshooting h_01HKW2YAW6RM6VJKFECT0ETGTG=release-notes" />
