---
title: '[Beta]网页端效果衡量S2S API'
metadata:
  keywords:
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
  created_at: '2026-04-12T15:09:07Z'
  edited_at: '2026-10-14T10:00:27Z'
  id: 45670116601617
  locale: zh-cn
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/zh-cn/articles/45670116601617
---
> **概览：** 网页端效果衡量S2S API支持通过服务器直接向AppsFlyer发送网页访问和事件数据，不受广告拦截器、Cookie限制等浏览器端限制的影响。您可以将S2S API与Web SDK搭配使用，也可以单独使用，以获取更完整、更高质量的归因数据。

<div id="about-the-s2s-api-for-web-attribution" />

## 关于网页端归因S2S API

AppsFlyer支持使用Web SDK（客户端）或S2S API（服务器对服务器，简称S2S）发送用于归因的网页端数据。您可以根据实际配置和需求单独使用其中一种方式，也可以组合使用。

Web SDK在浏览器中运行。S2S API则支持从自有后端发送相同的数据。S2S API之所以重要，是因为Safari ITP、Firefox ETP和Brave等隐私保护型浏览器及相关功能，以及广告拦截器，都可能阻止或限制客户端衡量。据行业估算，网页端用户中受浏览器端拦截影响的比例约为25%–40%。S2S调用由服务器发起，无需经过浏览器，因此完全不受上述限制影响。

<div id="how-it-works" />

### 工作原理

1. 用户访问您的网站或在浏览器中触发事件。
2. 您的服务器接收事件。
3. 您的服务器将事件直接发送至AppsFlyer服务器进行归因。

<div id="why-use-s2s" />

### 为什么使用S2S

S2S API主要具有以下优势：

* **衡量服务器端事件：** 部分转化完全不会经过浏览器，例如由后端处理的订阅续订，或CRM系统中生成的事件。只有通过S2S API，才能将此类事件发送至AppsFlyer，并归因至相应的广告系列。
* **扩大衡量范围：** S2S调用来自服务器，而非浏览器，因此不受广告拦截器、Safari ITP Cookie限制及其他浏览器端限制的影响。您可以捕获单靠客户端衡量会遗漏的访问和转化数据。
* **通过后端丰富事件数据：** 通过S2S API发送事件前，您的服务器可以向事件中添加更多数据，包括Customer User ID、经过哈希处理的电子邮件地址或电话号码、CRM属性、订阅状态或任意内部标识符。这样有助于提升身份解析能力和信号质量。
* **安全性：** 开发者密钥、用户标识符及其他补充数据均保存在您的服务器上，并通过安全连接发送，您可以完全控制哪些数据会传出自有基础架构。

<div id="api-specification" />

## API规范

基础URL：`https://events.appsflyer.com`

<div id="authentication" />

### 身份验证

所有请求均须在请求标头中包含有效的S2S API令牌，并指定正确的内容类型。

| 标头 | 类型 | 说明 |
| --- | --- | --- |
| `Authorization` | API令牌 | 请按以下格式在标头中添加您的S2S API令牌：<br /><br />`Authorization: Bearer {s2s-token}` |
| `Content-Type` | 字符串 | 必须为`application/json`。所有请求均须包含此项。 |

<div id="note" />

> 📘 **注意**
>
> 如需创建S2S API令牌，请参阅<Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens#管理token">管理AppsFlyer令牌</Anchor>中的说明。

<div id="measure-an-event" />

### 衡量事件

`POST /v2.0/s2s/inapps/app/web/{appId}`

衡量指定应用的网页端事件，例如购买、注册或自定义操作。

<div id="path-parameter" />

<Accordion title="路径参数">

| 参数 | 是否必填 | 说明 |
| --- | --- | --- |
| `appId` | 是否必填 | AppsFlyer中定义的`unified_app_id`。例如：`website-www.example.com` |

</Accordion>

<div id="request-body" />

<Accordion title="请求正文">

| 字段 | 类型 | 是否必填 | 说明 |
| --- | --- | --- | --- |
| `user_id` | 对象 | 是否必填 | 用户标识符。必须至少包含`customer_user_id`或`appsflyer_id`中的一项。 |
| `event_name` | 字符串 | 是否必填 | 事件名称。1–64个字符。不得包含`@ = + -`。示例：`af_purchase` |
| `event_revenue` | 数值（double） | 选填 | 购买或变现事件的收入金额。 |
| `event_revenue_currency` | 字符串（ISO-4217） | 选填 | 收入金额对应的货币代码。例如`USD`或`EUR`。 |
| `event_value` | 对象 | 选填 | 可自由定义的事件参数。支持`custom_parameters`子对象。 |
| `event_url` | 字符串 | 选填 | 事件发生页面的URL。必须是有效的HTTP URL，最多4096个字符。 |
| `timestamp` | 整数（int64） | 选填 | Unix时间戳，单位为毫秒（UTC）。未提供时，AppsFlyer将使用事件接收时间。延迟接收窗口：事件必须在应用时区次日00:30前送达。 |
| `ip` | 字符串 | 选填 | 设备IP地址（IPv4或IPv6）。最多46个字符。 |
| `user_agent` | 字符串 | 选填 | 浏览器的完整用户代理字符串。最多1024个字符。 |
| `http_referrer` | 字符串 | 选填 | 当前页面的引荐来源URL。 |
| `customer_dedup_id` | 字符串 | 选填 | 客户提供的去重标识符。 |
| `email_hashed` | 字符串 | 选填 | 规范化电子邮件地址（转为小写并删除首尾空格）的SHA256哈希值。必须是64个字符的十六进制字符串。 |
| `phone_number_hashed` | 字符串 | 选填 | 电话号码的SHA256哈希值。必须是64个字符的十六进制字符串。 |
| `phone_number_e164_hashed` | 字符串 | 选填 | E.164格式电话号码的SHA256哈希值（例如`+14155552671`）。必须是64个字符的十六进制字符串。 |
| `first_name_hashed` | 字符串 | 选填 | 规范化名字的SHA256哈希值。必须是64个字符的十六进制字符串。 |
| `last_name_hashed` | 字符串 | 选填 | 规范化姓氏的SHA256哈希值。必须是64个字符的十六进制字符串。 |

</Accordion>

<div id="example-request" />

<Accordion title="请求示例">

```json
{"user_id":{"customer_user_id":"15667737-366d-4994-ac8b-653fe6b2be4a"},"event_name":"af_purchase","event_revenue":49.99,"event_revenue_currency":"USD","event_value":{"af_content_id":"SKU-001","af_quantity":2,"custom_parameters":{"promo_code":"SUMMER10"}},"event_url":"https://example.com/checkout/success","timestamp":1712000000000,"ip":"35.244.183.10","user_agent":"Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) ...","email_hashed":"a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2"}
```

</Accordion>

<div id="responses" />

<Accordion title="响应">

| 状态 | 说明 |
| --- | --- |
| 202 Accepted | 请求已接受。返回状态、消息以及可选的`messageId`。 |
| 400 Bad Request | 字段无效或缺失。 |
| 401 Unauthorized | 应用不存在或身份验证失败。 |
| 403 Forbidden | 应用流量已被屏蔽。 |
| **415 Unsupported Media Type** | `Content-Type`必须为`application/json`。 |

</Accordion>

<div id="measure-a-visit" />

### 衡量访问

`POST /v2.0/s2s/visits/app/web/{appId}`

衡量指定网页端应用的页面访问。此端点与事件端点使用相同的基础字段，但有两项主要区别：`event_url`为必填项，事件名称和收入字段不适用。

<div id="path-parameter::d8a9ef62" />

<Accordion title="路径参数">

| 参数 | 是否必填 | 说明 |
| --- | --- | --- |
| `appId` | 是否必填 | AppsFlyer中定义的`unified_app_id`。例如：`website-www.example.com` |

</Accordion>

<div id="request-body::f7fb791b" />

<Accordion title="请求正文">

| 字段 | 类型 | 是否必填 | 说明 |
| --- | --- | --- | --- |
| `user_id` | 对象 | 是否必填 | 用户标识符。必须至少包含`customer_user_id`或`appsflyer_id`中的一项。 |
| `event_url` | 字符串 | 是否必填 | 所访问页面的URL。必须是有效的HTTP URL，最多4096个字符。 |
| `timestamp` | 整数（int64） | 选填 | Unix时间戳，单位为毫秒（UTC）。未提供时，AppsFlyer将使用事件接收时间。延迟接收窗口：访问必须在应用时区次日00:30前送达。 |
| `ip` | 字符串 | 选填 | 设备IP地址（IPv4或IPv6）。最多46个字符。 |
| `user_agent` | 字符串 | 选填 | 浏览器的完整用户代理字符串。最多1024个字符。 |
| `http_referrer` | 字符串 | 选填 | 当前页面的引荐来源URL。 |
| `event_value` | 对象 | 选填 | 可自由定义的事件参数，其中包括`custom_parameters`子对象。 |
| `customer_dedup_id` | 字符串 | 选填 | 客户提供的去重标识符。 |
| `email_hashed` | 字符串 | 选填 | 规范化电子邮件地址的SHA256哈希值。必须是64个字符的十六进制字符串。 |
| `phone_number_hashed` | 字符串 | 选填 | 电话号码的SHA256哈希值。必须是64个字符的十六进制字符串。 |
| `phone_number_e164_hashed` | 字符串 | 选填 | E.164格式电话号码的SHA256哈希值必须是64个字符的十六进制字符串。 |
| `first_name_hashed` | 字符串 | 选填 | 规范化名字的SHA256哈希值。必须是64个字符的十六进制字符串。 |
| `last_name_hashed` | 字符串 | 选填 | 规范化姓氏的SHA256哈希值。必须是64个字符的十六进制字符串。 |

</Accordion>

<div id="example-request::6283854b" />

<Accordion title="请求示例">

```json
{"user_id":{"appsflyer_id":"1234567890abcdef","customer_user_id":"15667737-366d-4994-ac8b-653fe6b2be4a"},"event_url":"https://example.com/products/sneakers","timestamp":1712000000000,"ip":"35.244.183.10","user_agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64) ...","http_referrer":"https://www.google.com/","email_hashed":"a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2"}
```

</Accordion>

<div id="responses::5cfbc5cc" />

<Accordion title="响应">

| 状态 | 说明 |
| --- | --- |
| 202 Accepted | 请求已接受。返回状态、消息以及可选的`messageId`。 |
| 400 Bad Request | 字段无效或缺失。 |
| 401 Unauthorized | 应用不存在或身份验证失败。 |
| 403 Forbidden | 应用流量已被屏蔽。 |
| **415 Unsupported Media Type** | `Content-Type`必须为`application/json`。 |

</Accordion>

<div id="set-up-a-fully-server-side-integration" />

## 配置完全基于服务器端的对接

如果您同时使用Web SDK和S2S，请改为参阅[提取Web SDK的afUserID](#extracting-the-web-sdk-afuserid)。本节仅适用于完全不使用SDK的对接方式。

如果您的网站完全未使用Web SDK，则需要自行完成Web SDK通常会处理的所有任务，包括设置用户Cookie、发送正确的标识符，以及确保每个事件的有效负载完整无缺。正确完成配置后，您将获得[为什么使用S2S](#为什么使用s2s)中介绍的全部优势，但前提是准确处理上述细节。

<div id="h_01KZS2SFULLSVR02" />

<Accordion title="除事件外，还需发送访问数据">

访问数据包含后续所有事件所依赖的归因参数，系统要求先接收用户的访问数据，再接收该用户的任何事件。如果先发送事件、后发送访问数据，系统会将该事件归类为自然量。

</Accordion>

<div id="h_01KZS2SFULLSVR03" />

<Accordion title="通过HTTP设置第一方Cookie">

由于没有Web SDK为您设置`afUserId` Cookie，您需要自行设置和管理。该Cookie需作为HTTP Cookie通过`Set-Cookie`响应标头设置，不应通过JavaScript写入客户端。

原因在于，通过`document.cookie`设置的客户端Cookie有效期很短：在Safari中最快7天后过期，在受ITP限制的域名中最快仅24小时后过期。Cookie过期后，标识符会重置，回访用户也会被视为新用户。由服务器设置的Cookie不受上述期限限制，可持续保留至浏览器允许的最长期限（Chrome最长为400天）。还可将Cookie标记为`HttpOnly`，使页面脚本和广告拦截器无法读取或移除，并且完全无需依赖页面上运行的任何脚本。

设置和读取方法：

1. 收到未携带Cookie的访客首次请求时，在服务器上生成一个稳定的唯一ID（例如UUID）。
2. 通过第一方Cookie返回该ID：

   ```
   Set-Cookie: af_web_id=<generated-id>; Max-Age=34128000; Path=/; Secure; HttpOnly; SameSite=Lax
   ```
3. 后续每次收到请求时，从传入的Cookie标头中读取并重复使用该值。不得重新生成该值。
4. 每次向AppsFlyer发起调用时，都需要将该值作为请求`user_id`对象中的`appsflyer_id`发送。

Cookie可以任意命名；AppsFlyer读取的是您发送的值，与Cookie名称无关。只需确保通过自有第一方域名设置Cookie。

</Accordion>

<div id="h_01KZS2SFULLSVR04" />

<Accordion title="每次调用均需发送正确的标识符">

每次调用都必须包含`user_id`对象，并至少提供`appsflyer_id`（Cookie值）或`customer_user_id`（您的内部用户ID）中的一项。同时发送两项可提升身份解析能力。

需要注意：访问通常来自匿名用户，因此必须始终发送Cookie值。对于站内事件，识别出用户身份后，需添加`customer_user_id`，并继续同时发送Cookie值。对于并非来自浏览器的事件，只需发送`customer_user_id`，前提是AppsFlyer已在之前的会话中识别出该用户。

</Accordion>

<div id="option-2-destination-function" />

<div id="option-1-webhooks-actions-destination" />

<div id="note-1" />

<div id="send-events-via-segment-cdp" />

<div id="things-to-consider" />

## 注意事项

<div id="user-identification" />

<Accordion title="用户识别">

每个请求都必须包含`user_id`对象。必须至少提供以下一个标识符。

| 字段 | 类型 | 说明 |
| --- | --- | --- |
| `customer_user_id` | 字符串（1–64个字符） | 您在自有系统中设置的内部用户标识符。 |
| `appsflyer_id` | 字符串（至少1个字符） | AppsFlyer为网页端用户分配的内部标识符。使用AppsFlyer Web SDK时，可从Web SDK Cookie中获取`appsflyer_id`值。从`afUserId`中提取该值。参阅[提取Web SDK的afUserId](#extracting-the-web-sdk-afuserid) |

</Accordion>

<div id="late-acceptance-windows" />

<Accordion title="延迟接收窗口">

事件和访问数据必须在应用时区次日00:30前送达。对于延迟送达的事件，系统将改用服务器接收时间。

</Accordion>

<div id="hashed-pii-fields" />

<Accordion title="经过哈希处理的PII字段">

所有个人数据字段都必须在发送前进行SHA256哈希处理。进行哈希处理前，需先将文本规范化（转换为小写并删除首尾空格）。每个哈希值必须为64个十六进制字符，不区分大小写。

* 所有哈希字段均须遵循以下格式：`^[a-fA-F0-9]{64}$`
* `phone_number_e164_hashed`字段中的电话号码必须先转换为E.164格式（例如`+14155552671`），再进行哈希处理。

</Accordion>

<div id="extracting-the-web-sdk-afuserid" />

<Accordion title="提取Web SDK的afUserID">

* `afUserId`参数是Web SDK在用户首次访问网站时设置的唯一标识符。
* 如需获取`afUserId`，可使用以下任一方法。

<div id="h_01HKW2YAW5FK04C3AWCXGP1XAW" />

#### **从HTTP Cookie标头中获取afUserId**

* 访客浏览器向您的网站发起请求时会发送`afUserId`。
* 如有需要，可从HTTP Cookie标头中提取该值。

<div id="h_01HKW2YAW5CT2WZ229KJD2FWYK" />

#### **在访客浏览器中查看afUserId**

* 可在访客浏览器中查看`afUserId`，用于问题排查和调试。
* 访客必须至少访问过一次已部署Web SDK的页面，才能获取该值。
* 包含`afUserId`的Cookie属于您域名下的第一方Cookie。
* 以下操作步骤基于Chrome 81编写。不同浏览器和操作系统中的操作可能有所不同。

**如需从访客浏览器中获取afUserId：**

1. 在浏览器中打开您的网站。
2. 右键单击，然后选择***检查***。浏览器开发者工具窗口随即打开。
3. 打开（A）***Application***标签页。
4. 在侧边菜单中展开（B）Cookies。
5. 选择您的网站。若未显示，刷新浏览器。
6. 在（C）***filter***字段中输入`afUserId`。页面随即显示afUserID的值。

</Accordion>

<div data-zendesk-anchors="about-the-s2s-api-for-web-attribution=%E5%85%B3%E4%BA%8E%E7%BD%91%E9%A1%B5%E7%AB%AF%E5%BD%92%E5%9B%A0s2s-api h_01KP13TF66KEZ7F1TGAA7RGQ6G=%E5%85%B3%E4%BA%8E%E7%BD%91%E9%A1%B5%E7%AB%AF%E5%BD%92%E5%9B%A0s2s-api how-it-works=%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86 h_01KP13TF66W8V5A40YT2XYWQ5K=%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86 why-use-s2s=%E4%B8%BA%E4%BB%80%E4%B9%88%E4%BD%BF%E7%94%A8s2s h_01KP13TF671CF85KMYXFZE6W9D=%E4%B8%BA%E4%BB%80%E4%B9%88%E4%BD%BF%E7%94%A8s2s api-specification=api%E8%A7%84%E8%8C%83 h_01KP13TF67N1FVEAD1C7RV25TY=api%E8%A7%84%E8%8C%83 authentication=%E8%BA%AB%E4%BB%BD%E9%AA%8C%E8%AF%81 h_01KP13TF67MHPEQ5J3H69RTQH5=%E8%BA%AB%E4%BB%BD%E9%AA%8C%E8%AF%81 h_01KT98N5SBW812PVXP165FCWR3=%E6%B3%A8%E6%84%8F measure-an-event=%E8%A1%A1%E9%87%8F%E4%BA%8B%E4%BB%B6 h_01KP13TF67QQC3F1YP9RZRNMTK=%E8%A1%A1%E9%87%8F%E4%BA%8B%E4%BB%B6 h_01KP13TF67Z0TZVNYPDYR2SXA6=path-parameter h_01KP13TF67PVQFVAAG5SYP7DPG=request-body h_01KP13TF68J9BT3SFGQKXFSM60=example-request h_01KP13TF68PX70V0K94WSHCX76=responses measure-a-visit=%E8%A1%A1%E9%87%8F%E8%AE%BF%E9%97%AE h_01KP13TF68HMD8GSR6GSY95WYF=%E8%A1%A1%E9%87%8F%E8%AE%BF%E9%97%AE h_01KP13TF681639XH9DBQYVX7SS=path-parameter::d8a9ef62 h_01KP13TF68ETEEM3ZX7JMFRXSD=request-body::f7fb791b h_01KP13TF68CDH9MB888HWA11JC=example-request::6283854b h_01KP13TF68FCDABJC64XC4V6EG=responses::5cfbc5cc h_01KZS2SFULLSVR01=%E9%85%8D%E7%BD%AE%E5%AE%8C%E5%85%A8%E5%9F%BA%E4%BA%8E%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%AB%AF%E7%9A%84%E5%AF%B9%E6%8E%A5 set-up-a-fully-server-side-integration=%E9%85%8D%E7%BD%AE%E5%AE%8C%E5%85%A8%E5%9F%BA%E4%BA%8E%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%AB%AF%E7%9A%84%E5%AF%B9%E6%8E%A5 send-visits-not-just-events=h_01KZS2SFULLSVR02 assign-a-first-party-cookie-via-http=h_01KZS2SFULLSVR03 send-the-right-identifiers-on-each-call=h_01KZS2SFULLSVR04 things-to-consider=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 h_01KP13TF68F2T3P7P56A5EG2HW=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 h_01KP13TF68GMKHGV9A34D98SYH=user-identification h_01KP13TF68JP8MFSFTZ1RP2Q3N=late-acceptance-windows h_01KP13TF68VD15WYQHBQK4YS0X=hashed-pii-fields h_01HKW2YAW52T0KME7P2CRQ6WBR=extracting-the-web-sdk-afuserid get-afuserid-from-the-http-cookie-header=%E4%BB%8Ehttp-cookie%E6%A0%87%E5%A4%B4%E4%B8%AD%E8%8E%B7%E5%8F%96afuserid h_01HKW2YAW5FK04C3AWCXGP1XAW=%E4%BB%8Ehttp-cookie%E6%A0%87%E5%A4%B4%E4%B8%AD%E8%8E%B7%E5%8F%96afuserid viewing-afuserid-in-the-visitors-browser=%E5%9C%A8%E8%AE%BF%E5%AE%A2%E6%B5%8F%E8%A7%88%E5%99%A8%E4%B8%AD%E6%9F%A5%E7%9C%8Bafuserid h_01HKW2YAW5CT2WZ229KJD2FWYK=%E5%9C%A8%E8%AE%BF%E5%AE%A2%E6%B5%8F%E8%A7%88%E5%99%A8%E4%B8%AD%E6%9F%A5%E7%9C%8Bafuserid" />
