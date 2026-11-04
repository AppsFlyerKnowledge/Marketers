---
title: 受众共享中用于上传额外标识符的API
metadata:
  keywords:
    - Advertisers
    - Developers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2021-11-22T14:05:51Z'
  edited_at: '2026-10-14T10:15:43Z'
  id: 4411552670993
  locale: zh-cn
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/zh-cn/articles/4411552670993
---
> **概要：** 您可以使用Audiences Additional Identifiers API将用户标识符从您的内部系统（如BI和CRM）中批量上传到AppsFlyer的受众共享，以便让相关渠道根据这些标识符更广泛地触达目标群体。

<div id="about-the-api" />

## Audiences Additional Identifiers API简介

您可以使用Audiences Additional Identifiers API将您内部系统中的用户标识符添加到AppsFlyer的受众共享中：

* 最多可上传两个加密的邮箱地址
* 加密的电话号码
* 加密的E164电话号码

您可以向您的受众共享渠道发送这些标识符（具体取决于您<Anchor target="_blank" href="/marketers/zh/docs/audiences-user-identifier-policy">账户层级的用户标识符共享规则</Anchor>），帮助其精准匹配到您的目标客群。请注意：并非所有渠道都支持全部标识符。

<div id="when-should-i-use-this-api" />

### Audiences Additional Identifiers API的用途

该API专用于上传大批量标识符数据，通常适用于在较长一段时间内收集到的数据（比如在过去12个月内从某个应用中收集到的所有用户的加密邮箱地址）。如需对特定设备的标识符进行单独的实时更新，您可以在AppsFlyer SDK或S2S-mobile API中<Anchor target="_blank" href="/marketers/zh/docs/audiences-configure-additional-identifiers-for-partner-audience-creation">配置所需的额外标识符</Anchor>。

<div id="important" />

> 🚧 **重要提示！**
>
> 所有额外标识符的值都**必须**使用SHA256算法进行加密。未加密的标识符不予处理。
>
> **使用时间：** 为了确保标识符的精准匹配，您可以在AppsFlyer SDK上报主要标识符后的**第二天**（以UTC时间为准）使用Audiences Additional Identifiers API。举例来说，假设主要标识符在2022年1月3日（UTC时间）上报，您可在2022年1月4日或之后通过此API来更新这些标识符。

<div id="actions" />

## 可用操作

* [添加/修改标识符](/docs/upload-additional-identifiers-to-audiences-via-api#addmodify-identifiers-put)
* [删除标识符](/docs/upload-additional-identifiers-to-audiences-via-api#remove-identifiers-delete)

<div id="authentication" />

## 身份验证

发送请求时，HTTP请求头中必须包含您AF账号的<Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">AppsFlyer V2.0 API token。您可以让账号管理员为您提供此token信息。</Anchor>

<div id="api-specifications-and-sample-code" />

## API配置要求和示例代码

<div id="addmodify-identifiers-put" />

<Accordion title="添加/修改标识符（PUT）">

<span id="01ECF4ZD0T03JBV8DDH25MM01W"></span>**API请求URL**

```json
https://hq1.appsflyer.com/api/audience-bulk-api/v1/additional-identifiers/app/{app-id}
```

| 参数 | 说明 | 是否必须配置 |
| --- | --- | --- |
| `{app-id}` | 相关应用的App ID，通过该应用收集到其他各种标识符（与AppsFlyer面板中显示应用ID一致） | 是 |

<span id="01ECF4ZD0TWPH3DXV2YKN7G9B0"></span>**API请求体**

```json
{
  "key_type": "<key_type>",
  "action": "add",
  "data": [
    {
      "key_value": "<key_value>",
      "identifiers": {
        "hashed_emails": [
          "<hashed_email_value>",
          "<hashed_email_value>"
        ],
        "phone_number_sha256": "<phone_number_sha256_value>",
        "phone_number_e164_sha256": "<phone_number_e164_sha256_value>"
      }
    },
    {
      "key_value": "<key_value>",
      "identifiers": {
        "hashed_emails": [
          "<hashed_email_value>",
          "<hashed_email_value>"
        ],
        "phone_number_sha256": "<phone_number_sha256_value>",
        "phone_number_e164_sha256": "<phone_number_e164_sha256_value>"
      }
    }
  ]
}
```

| 参数 | 说明 | 是否必须配置 |
| --- | --- | --- |
| `{key_type}` | 将该标识符作为请求体的各行数据中代表相关用户的唯一值。<br /><br />此处配置的值对请求中的每一行都生效。<br /><br />可用值包括：<ul><li>idfa</li><li>gaid</li><li>idfv</li><li>customer\_user\_id</li><li>imei</li><li>oaid</li></ul> | 是 |
| `{action}` | 用于添加标识符 | 否<br /><br />默认值：add |
| `{key_value}` | 针对key\_type设置的有效标识符值 | 是 |
| \{identifiers\} | 对象中包含需要添加的标识符名称和值：<ul><li>\{hashed\_emails\}</li><li>\{phone\_number\_sha256\}</li><li>\{phone\_number\_e164\_sha256\}</li></ul> | 是<ul><li>必须包含这3个标识符中的至少1个标识符的值</li></ul> |
| `{hashed_emails}` | 以数组的形式呈现，最多可包含2个加密的邮箱地址<br /><br />格式：<ul><li>小写</li><li>无空格</li><li>须经过SHA256加密</li></ul>加密前的参数值示例：name@domain.com | 否 |
| `{phone_number_sha256}` | 电话号码（见下文说明）<br /><br />格式：<ul><li>无符号、字母，不能以零开头</li><li>需包含国家代码</li><li>须经过SHA256加密</li></ul>加密前的参数值示例：<br /><br />442070313000 | 否 |
| `{phone_number_e164_sha256}` | E164格式的电话号码（见下文说明）<br /><br />格式<ul><li>E164格式的电话号码</li><li>须经过SHA256加密</li></ul>加密前的参数值示例：<br /><br />+442070313000 | 否 |

<div id="notes" />

> 📘 **注意**
>
> 各个渠道支持的电话号码格式有所不同。因此如需添加电话号码，建议同时发送以下两种类型的电话号码参数：*phone\_number\_sha256*和*phone\_number\_e164\_sha256。*

**限制**

**添加/修改标识符**请求受以下规则的限制：

* 在请求中发送的值会覆盖之前存在的值（若有）。
* 每个请求的`{data}`对象中最多可包含4000行（key\_values）。

**添加标识符的请求示例**

```json
HTTP PUT
body:
{
  "key_type": "idfv",
  "action": "add",
  "data": [
    {
      "key_value": "CDDA802e-AAAA-BBBB-CCCC-DDDDDDDDDDDD",
      "identifiers": {
        "hashed_emails": [
          "34d31be18022626de6b311d6a76e791176d2691b6eef406f524d8f56364c187a",
          "d8c2aec999baad2464e521873ee4465caaf7ff6db8c8b4a25b09ca07694e4dee"
        ],
        "phone_number_sha256": "6c91c4c640f6ef0162833260db4f13dec0df2b683092f4dba7e874bef1acea37",
        "phone_number_e164_sha256": "f3d7e96c73fb0de1b66acfce541d7af758fbd4f3fa3af0ea4e10110000d3625e"
      }
    }
  ]
}
```

</Accordion>

<div id="remove-identifiers-delete" />

<Accordion title="删除标识符（PUT）">

**API请求URL**

```json
https://hq1.appsflyer.com/api/audience-bulk-api/v1/additional-identifiers/app/{app-id}
```

| 参数 | 说明 | 是否必须配置 |
| --- | --- | --- |
| `{app-id}` | 相关应用的App ID，通过该应用收集到其他各种标识符（与AppsFlyer面板中显示应用ID一致） | 是 |

**API请求体**

```json
{
  "key_type": "<key_type>",
  "action": "remove",
  "data": [
    {
      "key_value": ",<key_value>",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    },
    {
      "key_value": ",<key_value>",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    }
  ]
}
```

| 参数 | 说明 | 是否必须配置 |
| --- | --- | --- |
| `{key_type}` | 将该标识符作为请求体的各行数据中代表相关用户的唯一值。<br /><br />此处配置的值对请求中的每一行都生效。<br /><br />可用值包括：<ul><li>idfa</li><li>gaid</li><li>idfv</li><li>customer\_user\_id</li><li>imei</li><li>oaid</li></ul> | 是 |
| `{key_value}` | 针对key\_type设置的有效标识符值 | 是 |
| `{action}` | 用于移除标识符 | 否<br /><br />默认值：add |
| \{identifiers\} | 以数组的形式呈现，其中包含需要移除的标识符名称和值：<ul><li>\{hashed\_emails\}</li><li>\{phone\_number\_sha256\}</li><li>\{phone\_number\_e164\_sha256\}</li></ul> | 是<ul><li>必须包含这3个标识符中的至少1个</li></ul> |

**限制**

每个请求的`{data}`对象中最多可包含4000行（key\_values）。

**移除标识符的请求示例**

```json
HTTP PUT
body:
{
  "key_type": "gaid",
  "action": "remove",
  "data": [
    {
      "key_value": "cdda802e-aaaa-bbbb-cccc-dddddddddddd",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    }
  ]
}
```

</Accordion>

<div id="responses" />

<Accordion title="响应">

| 响应代码 | 响应消息 | 说明 |
| --- | --- | --- |
| 202 | Accepted for processing（接受处理） | 相关请求会在下一个处理窗口期内生效。 |
| 400 | Request body must have a valid key\_type（请求体内必须包含有效的key\_type） | key\_type支持以下标识符：<ul><li>idfa</li><li>gaid</li><li>idfv</li><li>customer\_user\_id</li><li>imei</li><li>oaid</li></ul> |
| 400 | Request must have ‘data’ with at least 1 element（请求中必须包含带有至少一个元素的数据） | 数据列表不能为空。 |
| 400 | Request ‘data’ should not exceeds the size of 4000 in a single request（请求的数据不能超过每次请求4000行的限制） | 数据列表不能超过4000行。 |
| 400 | Request data has too many invalid ‘data’ elements（请求的数据中包含过多无效的数据元素） | 要修改的数据中超过10%不符合配置要求 |
| 404 | AppsFlyer - Page Not Found（未找到页面） | 检查以下内容：<ul><li>API请求URL中的`{app-id}`是否设置正确</li><li>HTTP请求头中是否包含正确的<Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">AppsFlyer V2.0 API token</Anchor>。您可以让账号管理员为您提供此token信息。</li></ul> |

**响应示例**

```json
{
"message": "Accepted for processing",
"received": 1000,"invalid": 2,
"trace-id": "698ed323-c787-45b5-b792-463c67c94064"
}
```

```json
{
"error": "Request body must have a valid key_type",
"trace-id": "18a5f685-ea4d-4ca9-beab-a542a3786d12"
}
```

```json
{
"error": "Request must have 'data' with at least 1 element",
"trace-id": "c155a7fa-b573-4efe-9bfb-5ae7de40e7fd"
}
```

```json
{
"error": "Request 'data' should not exceeds the size of 4000 in a single request”,
"trace-id": "b325a7fa-b573-4efe-9bfb-5ae7de40e72c"
}
```

```json
{
"error": "Request data has too many invalid 'data' elements",
"valid": 2,
"invalid": 30,
"trace-id": "33551c1d-5682-405e-a959-c8729ca74735"
}
```

</Accordion>

<div id="rate-limitations" />

<Accordion title="频次限制">

* 每秒最多可发送5个请求
* 每分钟最多可发送350个请求

</Accordion>

<div data-zendesk-anchors="api-overview=audiences-additional-identifiers-api%E7%AE%80%E4%BB%8B h_01HNZP1Y2MQ8W25SNP2XVNZ7WW=audiences-additional-identifiers-api%E7%AE%80%E4%BB%8B when-should-i-use-this-api=audiences-additional-identifiers-api%E7%9A%84%E7%94%A8%E9%80%94 h_01HNZP1Y2MJY56TMN6QH4BVRPA=audiences-additional-identifiers-api%E7%9A%84%E7%94%A8%E9%80%94 h_01HNZP1Y2MX414NJ49BCVW7KZC=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA methods=%E5%8F%AF%E7%94%A8%E6%93%8D%E4%BD%9C h_01HNZP1Y2MS5V43XS008GG4S32=%E5%8F%AF%E7%94%A8%E6%93%8D%E4%BD%9C authentication=%E8%BA%AB%E4%BB%BD%E9%AA%8C%E8%AF%81 h_01HNZP1Y2MH2Y4P8ZT4SVM5GM2=%E8%BA%AB%E4%BB%BD%E9%AA%8C%E8%AF%81 api-specifications-and-sample-code=api%E9%85%8D%E7%BD%AE%E8%A6%81%E6%B1%82%E5%92%8C%E7%A4%BA%E4%BE%8B%E4%BB%A3%E7%A0%81 h_01HNZP1Y2MR0GCCA1916RMB6GJ=api%E9%85%8D%E7%BD%AE%E8%A6%81%E6%B1%82%E5%92%8C%E7%A4%BA%E4%BE%8B%E4%BB%A3%E7%A0%81 h_01HNZP1Y2M1N548KSMA6MQ601W=addmodify-identifiers-put h_01HNZP1Y2P2VVV4WT88D82QXJ4=%E6%B3%A8%E6%84%8F h_01HNZP1Y2Q0FAQQE3MTZ8B3FFS=remove-identifiers-delete h_01HNZP1Y2QK2J8ERP1SQTYB20C=responses h_01HNZP1Y2Q1WZCN2TCEAS6HB2X=rate-limitations" />
