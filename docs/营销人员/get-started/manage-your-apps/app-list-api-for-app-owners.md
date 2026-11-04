---
title: 应用所有者的应用列表 API
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2020-08-17T18:07:10Z'
  edited_at: '2026-10-30T12:25:15Z'
  id: 360011999877
  locale: zh-cn
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/zh-cn/articles/360011999877
---
> **概览：** 获取与您的 AppsFlyer 账户关联的已启用和待处理应用列表。

![mceclip0.png](https://files.readme.io/34b4b3d56ca5d7419830ba26701483f64ebb0a908e1e8e7ed65779bb89a14c67-24507752775313.png)

如果您是广告平台，请使用<Anchor target="_blank" href="/partners/zh/docs/app-list-api-for-ad-networks">广告平台专用的应用列表</Anchor> API。

**延伸阅读：** <Anchor target="_blank" href="/marketers/zh/docs/about-advertiser-apis">广告主 API 列表</Anchor>

<div id="get-app-list-api" />

## 获取应用列表 API

以下章节介绍使用此 API 所需的信息。

**获取应用列表基本信息**

<div id="get-api-list-basics" />

<Accordion title="API 基本信息">

<table><thead><tr><th>类别</th><th>项目</th><th><span>说明</span></th></tr></thead><tbody><tr><td rowspan="3">请求</td><td>HTTP 方法</td><td><code>GET</code></td></tr><tr><td>请求路径</td><td><span>https://hq1.appsflyer.com/api/mng/apps</span></td></tr><tr><td>授权请求 header </td><td><ul><li>必须在授权请求 header中提供 Bearer 令牌。 </li><li>账户管理员可以在控制面板中获取令牌：<a href="./managing-appsflyer-tokens" target="_blank">点击电子邮箱下拉菜单，然后选择 API tokens，获取 V2.0 令牌</a>。 </li></ul></td></tr><tr><td rowspan="3"> 响应</td><td>返回格式</td><td>JSON</td></tr><tr><td>请求频率限制</td><td><ul><li>每分钟 20 次请求</li><li>每日 100 次请求</li></ul></td></tr><tr><td>单次请求的记录数限制</td><td>每次请求最多返回 1,000 条记录。如果记录数超过 1,000 条，请按照本文介绍的分页机制继续发送请求。</td></tr></tbody></table>

</Accordion>

<div id="api-request" />

<Accordion title="API 请求">

API 请求包含 HTTP 方法、请求路径、必需的功能权限参数以及可选的分页参数。令牌需放在授权请求 header中。

**请求方法**

```http
GET https://hq1.appsflyer.com/api/mng/apps
```

获取应用列表的必需参数：

| 查询参数 | 说明 |
| --- | --- |
|  | 此 API 无必需的查询参数。 |

<div id="pagination-mechanism" />

#### **分页机制**

此 API 始终启用分页机制。

**分页规则：**

* 每次请求（每页）最多返回 1,000 条记录。
* JSON 响应中包含以下与分页相关的字段：
  * **meta.total\_items：** 所有分页合计需要返回的记录总数。即您拥有所查询*功能权限*的应用总数。
  * 分页链接（如下方 JSON 所示）包含以下字段：
    * **links.prev：** 如果存在上一页，该字段提供生成上一页数据的请求地址。
    * **links.self：** 当前页的请求地址，即生成当前 JSON（页面）的请求地址。
    * **links.next：** 获取下一页所需的请求地址。如果不存在 *next* 字段，表示当前页是最后一页。

**您可以采用以下任一方式控制分页：**

* 【推荐】使用 JSON 中的 *links* 字段：如果存在 *links.next* 字段，请使用该字段生成请求下一页的地址。重复此操作，直到收到的 JSON 中不再包含 *links.next* 字段。
* 结合 *total\_items* 字段，在程序中使用 *limit* 和 *offset* 参数实现分页。

**分页链接的 JSON 示例**

* 以下示例展示了第二次请求的结果，其中 data 部分包含 2 条记录（未展示具体内容）。
* 所有分页需要返回的记录总数为 6 条。
* **links.next** 字段提供了获取下一页（第 5 条和第 6 条记录）的请求地址。

```json
{                                                                                         
    "data": {[...]},   
    "meta": {
        "total_items": 6
    },
    "links": {
        "prev": "https://hq1.appsflyer.com/api/mng/apps?offset=0&limit=2",
        "self": "https://hq1.appsflyer.com/api/mng/apps?offset=2&limit=2",
        "next": "https://hq1.appsflyer.com/api/mng/apps?offset=4&limit=2"
    }
}
```

分页参数（可选）：

| 查询参数 | 说明 |
| --- | --- |
| limit | 每次请求返回的记录数。<ul><li>最大值：1,000</li><li>如果未指定`limit`，系统默认设置为 1,000。</li><li>示例：`limit=2`</li><li>是否必需：否</li></ul> |
| offset | 指定本次请求从第几条记录开始返回。记录编号从 0 开始。<ul><li>如果未指定 `offset`，系统默认设置为 0。</li><li>示例：`offset=2`</li><li>是否必需：否</li></ul> |

</Accordion>

<div id="json-response" />

<Accordion title="JSON 响应">

| **字段** | **说明** |
| --- | --- |
| id | 应用 ID。例如：`id123456789`、`com.myapp.com` |
| type | 始终返回 `app` |
| name | 应用名称 |
| platform | 应用平台：iOS 或 Android |
| currency | 应用专属货币代码 |
| time\_zone | 应用专属时区 |
| total\_items | 账户中包含的应用总数 |
| links | 分页链接（具体说明见参数章节）<ul><li>prev：生成上一页数据的请求地址</li><li>self：生成当前页数据的请求地址</li><li>next：生成下一页数据的请求地址</li></ul> |

</Accordion>

<div id="get-app-list-curl-example-and-response" />

<Accordion title="获取应用列表的 cURL 请求示例及响应">

**cURL 请求**

以下示例展示了完整的 API 请求，其中包含可选的分页参数。

```bash
cURL --location --request GET 'https://hq1.appsflyer.com/api/mng/apps?limit=1000&offset=0' \
-H 'Authorization: Bearer {控制面板中可获取的、长度超过 700 个字符的 API V2.0 令牌。}' \
```

**JSON 响应**

```json
{
    "data": [
        {
            "id": "com.appsflyer.xpend_qa1",
            "type": "app",
            "attributes": {
                "name": "com.appsflyer.xpend_qa1",
                "platform": "android",
                "currency": "USD",
                "time_zone": "UTC"
            }
        },
        {
            "id": "com.abc.app",
            "type": "app",
            "attributes": {
                "name": "com.abc.app",
                "platform": "android",
                "currency": "USD",
                "time_zone": "UTC",
                "enable_retargetting": true
            }
        },
        {
            "id": "com.def.app",
            "type": "app",
            "attributes": {
                "name": "com.def.app",
                "platform": "android",
                "currency": "JPY",
                "time_zone": "UTC"
            }
        }
    ],
    "meta": {
        "total_items": 6
    },
    "links": {
        "self": "https://hq1.appsflyer.com/api/mng/apps?offset=0&limit=1000"
           }
}
```

</Accordion>

<div id="http-response-codes" />

<Accordion title="HTTP 响应状态码">

| 状态码 | 消息 | 说明及故障排查 |
| --- | --- | --- |
| 200 | OK | 请求成功，已返回有效数据。 |
| 200 | OK | **问题：** 未返回任何数据<br /><br />**解决方法：** 检查授权请求 header中是否包含身份验证令牌，并确认令牌使用了 Bearer 认证格式。 |
| 400 | Bad request（请求无效） | 请查看 JSON 响应中包含的具体错误信息。 |
| 401 | Unauthorized（未授权） | **错误信息：** 授权令牌格式不正确<br /><br />请确认使用了正确的令牌，且令牌长度超过 700 个字符。 |
| 404 | Not found（未找到） | <ul><li>检查网络连接或防火墙是否存在问题。</li><li>确认已将 AppsFlyer 的<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-server-ip-address-ranges-allowlisting">IP 地址添加到允许列表</Anchor>。</li><li>确认使用的是最近签发的令牌。</li><li>如果提示未找到数据，则表示未找到任何应用。</li></ul> |
| 429 | Too many requests（请求次数过多） | 请求次数超出频率限制。请减少请求次数，并确保符合 API 的调用限制。 |

</Accordion>

<div data-zendesk-anchors="get-app-list-api=%E8%8E%B7%E5%8F%96%E5%BA%94%E7%94%A8%E5%88%97%E8%A1%A8-api h_01KQS56KS2G7TD4VHZCHVP0W9S=%E8%8E%B7%E5%8F%96%E5%BA%94%E7%94%A8%E5%88%97%E8%A1%A8-api h_01KQS56KS26TY81ACBN2XBK3W2=get-api-list-basics h_01KQS56KS27NETZ4C5RY28V804=api-request pagination-mechanism=%E5%88%86%E9%A1%B5%E6%9C%BA%E5%88%B6 h_01KQS56KS33VFVX099T1S2928G=%E5%88%86%E9%A1%B5%E6%9C%BA%E5%88%B6 h_01KQS56KS3Q5EEVSSC7G1FEFXR=json-response h_01KQS56KS3EZCH1KBBQQKTXWYP=get-app-list-curl-example-and-response h_01KQS56KS3S04KDZ58J7XKQNCK=http-response-codes" />
