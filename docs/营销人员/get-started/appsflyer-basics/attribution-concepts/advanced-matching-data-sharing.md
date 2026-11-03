---
title: 高级匹配数据共享
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-06-18T14:23:54Z'
  edited_at: '2026-10-14T10:00:29Z'
  id: 47876839961489
  locale: zh-cn
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/zh-cn/articles/47876839961489
---
> **概览：** 高级匹配数据共享功能允许将哈希用户标识符（例如电子邮件和电话号码）从 AppsFlyer 转发到选定的广告网络，从而使合作伙伴能够在没有设备 ID 的情况下将事件归因于广告互动。

## 关于高级匹配数据共享

随着设备标识符越来越少，广告网络越来越依赖第一方数据来匹配广告互动。高级匹配数据共享通过以符合隐私规定的格式将哈希标识符转发给支持的合作伙伴来弥补这一差距。

该功能为可选功能，并由每个合作伙伴进行配置。在支持的网络上启用后，AppsFlyer 会将哈希标识符与安装、重新互动和应用内事件的事件数据一起转发。

> 🚧 **重要提示！**
>
> 所有标识符在到达 AppsFlyer 之前都必须使用 SHA-256 进行哈希处理，无论是在设备上通过 SDK 还是在服务器端通过 S2S API。纯文本数据永远不会被接收、存储或转发，任何未通过验证的值都会在摄取时被丢弃。

### 适用渠道：

高级匹配数据共享的范围因合作伙伴而异。Snapchat 和 TikTok 支持安装、重新互动和应用内事件，而 Google 和 Meta 仅限于应用内事件匹配。该功能目前适用于以下网络：

| 渠道 | 对接类型 | 支持的赛事 |
| --- | --- | --- |
| Google (googleads\_int) | OCI | 应用内事件 |
| 元（facebook\_int、metaweb\_int） | SRN + CAPI | 应用内事件 |
| OpenAI（openai\_int） | CAPI | 安装量、​​重新互动、应用内事件 |
| TikTok（tiktokglobal\_int、tiktokweb\_int） | SRN + CAPI | 安装量、​​重新互动、应用内事件 |
| Snapchat（snapchat\_int，snapweb\_int） | SRN + CAPI | 安装量、​​重新互动、应用内事件 |
| Pinterest (pinterest\_int) | CAPI | 安装量、​​重新互动、应用内事件 |
| Reddit（reddit\_int） | CAPI | 安装量、​​重新互动、应用内事件 |
| Roku（rokuads\_​​int） | SRN + CAPI | 应用内事件 |

## 端到端流程

以下是从获取标识符到将其传递给合作伙伴之间发生的过程：

1. 在应用程序或后端检索标识符（电子邮件地址、电话号码或其他支持的类型）。
2. 标识符使用 SHA-256 进行规范化和哈希处理：由 AppsFlyer SDK 自动处理，或在通过 S2S API 发送之前在服务器上处理。
3. 哈希标识符会与事件（安装、重新安装、重新互动或应用内事件）一起发送到 AppsFlyer。
4. 如果合作伙伴启用了高级匹配数据共享，AppsFlyer 会将哈希值与事件有效负载一起转发。
5. 合作伙伴使用哈希值将事件与已知用户进行匹配，从而提高归因准确性和匹配质量。

> 📘 **注意**
>
> 只有在启用高级匹配数据共享功能的情况下，才会将哈希标识符转发给合作伙伴。当开启/关闭功能关闭时，即使事件中存在标识符，也不会与该合作伙伴共享任何哈希数据。

## AppsFlyer 如何获取哈希用户标识符

哈希标识符通过两种方法到达 AppsFlyer：SDK 或服务器到服务器 (S2S) API。这两种情况下，都只接受正确哈希的值。下面的各个标签页分别介绍了每种方法。

<Tabs>
<Tab title="SDK">

SDK V7.0.1 引入了一种将原始标识符传递给 AppsFlyer Android 和 iOS SDK 的方法。SDK 在将输入数据发送到 AppsFlyer 之前，会对输入数据进行规范化和哈希处理：

SDK按顺序执行以下步骤：

1. 根据每个合作伙伴的要求对输入进行规范化处理。
2. 使用 SHA-256 对规范化值进行哈希处理。
3. 仅将哈希值发送给 AppsFlyer。原始输入数据永远不会离开设备。

SDK 会拒绝无效值并报错，且不会将无效值发送到 AppsFlyer。

> 📘 **注意**
>
> 从 SDK V7.0.1 开始，Android 和 iOS 系统均可支持。

有关实现细节，请参阅Android SDK 集成指南和iOS SDK 集成指南。

</Tab>

<Tab title="S2S API">

通过 S2S 应用内事件 API 发送事件时，标识符必须在提交前在服务器端进行规范化和哈希处理。该 API 接受以下字段：

| 字段 | 说明 |
| --- | --- |
| `email_hashed` | 哈希电子邮件地址 |
| `phone_number_hashed` | 已加密的电话号码，仅包含数字 |
| `phone_number_e164_hashed` | 以 E.164 格式存储的哈希电话号码 |
| `first_name_hashed` | 名字已打哈希 |
| `last_name_hashed` | 姓氏已打哈希 |
| `fb_login_id` | Facebook 登录 ID（未加密；按原样传递） |

> 🚧 **重要提示！**
>
> 此表中的每个字段（除`fb_login_id`) 已根据 SHA-256 格式进行验证。不匹配的值会被默默丢弃，不会转发给任何合作伙伴。事件中的其他字段均正常处理。

<strong>为什么会有两个电话号码输入框？</strong>网络通过将 AppsFlyer 转发的哈希值与自身存储的用户电话号码哈希值进行比较来匹配事件。因为同一个数字以不同的格式进行规范化会产生不同的哈希值，所以双方必须使用相同的格式进行哈希运算才能得到匹配结果。由于网络对电话号码的规范化方式不同，而 AppsFlyer 接收到的值已经过哈希处理，因此必须发送这两个版本才能覆盖所有支持的合作伙伴。

* `phone_number_hashed`适用于 Meta 和 Snapchat。哈希前的规范化格式： `16501234567`
* `phone_number_e164_hashed`适用于谷歌和TikTok。哈希前的规范化格式： `+16501234567`

</Tab>
</Tabs>

## 规范化和哈希标识符

按照下述方法规范化原始值，然后使用 SHA-256 进行哈希处理，并发送小写十六进制摘要。

<div id="email-email_hashed" />

<Accordion title="电子邮件（email_hashed）">

1. 删除所有空格。
2. 转换为小写。
3. 使用 SHA-256 进行哈希运算。

**示例：**

`User@Example.COM` →`user@example.com` → SHA-256 哈希

</Accordion>

<div id="phone-number-digits-only-phone_number_hashed" />

<Accordion title="电话号码，仅数字（电话号码哈希值）">

可用于 Meta 和 Snapchat。

1. 在前面加上国家代码。
2. 删除所有符号、字母和前导零。
3. 使用 SHA-256 进行哈希运算。

**示例：**

`+1 (650) 123-4567` →`16501234567` → SHA-256 哈希

</Accordion>

<div id="phone-number-e164-phone_number_e164_hashed" />

<Accordion title="电话号码，E.164（phone_number_e164_hashed）">

可用于谷歌和TikTok。

1. 在前面加上国家代码。
2. 删除所有符号、字母和前导零。
3. 前面加上一个`+`符号。
4. 使用 SHA-256 进行哈希运算。

**示例：**

`+1 (650) 123-4567` →`+16501234567` → SHA-256 哈希

</Accordion>

<div id="first-name-first_name_hashed-and-last-name-last_name_hashed" />

<Accordion title="名字（first_name_hashed）和姓氏（last_name_hashed）">

1. 删除所有空格。
2. 转换为小写。
3. 使用 SHA-256 进行哈希运算。

</Accordion>

<div id="facebook-login-id-fb_login_id" />

<Accordion title="Facebook 登录 ID (fb_login_id)">

发送由 Facebook 登录 SDK 提供的原始 Facebook 登录 ID。该字段未进行哈希处理。

</Accordion>

## 启用高级匹配数据共享

高级匹配数据共享是按合作伙伴和应用程序控制的，必须为每个网络明确启用。

启用高级匹配数据共享：

1. 从AppsFlyer面板左侧的菜单栏中选择**协作** > 活跃对接。
2. 搜索并选择相关渠道。
3. 启用**高级匹配数据共享**。
4. 点击**保存对接**。

启用高级匹配数据共享后，任何包含一个或多个受支持的标识符字段的事件都会将这些字段转发给合作伙伴。

> 📘 **注意**
>
> 关闭高级匹配数据共享功能后，将立即停止与该合作伙伴的哈希数据共享。其他集成设置，包括回传和事件数据，不受影响。

## 隐私和数据处理

当为合作伙伴启用高级匹配数据共享时，AppsFlyer 会开始将哈希用户标识符以及事件数据转发到该网络。开机前，请确认以下事项：

* 根据适用的隐私法律（例如通用数据保护条例 (GDPR) 或加州消费者隐私法 (CCPA)），存在合法依据与合作伙伴共享此数据。
* 您的隐私政策已更新，并且在需要时已获得用户同意。
* 您的数据共享做法符合合作伙伴的条款。

> 🚧 **重要提示！**
>
> AppsFlyer 不会处理或存储纯文本个人身份信息 (PII)。所有标识符字段在数据摄取时都会进行验证：不符合 SHA-256 格式的值将被丢弃，并且永远不会转发给任何合作伙伴。

## FAQ

<div id="is-advancedmatching-data-sharing-the-same-as-the-audiences-hashed-email-and-phone-feature" />

<Accordion title="高级匹配数据共享与受众群体的哈希电子邮件和电话号码功能相同吗？">

不，这是不同的机制。受众群体会建立用户列表以进行广告定向。高级匹配数据共享将哈希标识符与单个事件一起转发，以提高合作伙伴级别的匹配率。AppsFlyer 计划整合这两种方法，将新的数据检索方法用于高级匹配数据共享和受众群体。

</Accordion>

<div id="what-happens-if-i-send-an-invalid-hash-value" />

<Accordion title="如果我发送无效的哈希值会发生什么？">

该字段在数据摄取时被删除，不会转发给任何合作伙伴。事件中的其他字段均正常处理。

</Accordion>

<div id="do-i-need-to-send-all-supported-fields" />

<Accordion title="我需要发送所有支持的字段吗？">

不，只需要包含与已配置合作伙伴相关的可用标识符即可。缺失的字段不会被转发。

</Accordion>

<div id="will-advancedmatching-data-sharing-improve-install-attribution" />

<Accordion title="高级匹配数据共享能否改善安装归因分析？">

是的，Snapchat 和 TikTok 可以。这些合作伙伴支持基于哈希电子邮件和电话号码的安装和重新互动声明。目前，对于 Google 和 Meta 而言，它仅提高了应用内事件的匹配率。

</Accordion>

<div id="does-appsflyer-ever-receive-plaintext-user-identifiers" />

<Accordion title="AppsFlyer 是否会接收纯文本用户标识符？">

不。使用 SDK 时，哈希处理是在设备端进行的，之后才会将任何内容发送到 AppsFlyer。使用 S2S API 时，哈希处理会在提交之前在服务器端进行。AppsFlyer 只接受哈希值。

</Accordion>

<div data-zendesk-anchors="about-advancedmatching-data-sharing=%E5%85%B3%E4%BA%8E%E9%AB%98%E7%BA%A7%E5%8C%B9%E9%85%8D%E6%95%B0%E6%8D%AE%E5%85%B1%E4%BA%AB h_01KVFJHWK1TYAPPMZDYFAP0RX0=%E5%85%B3%E4%BA%8E%E9%AB%98%E7%BA%A7%E5%8C%B9%E9%85%8D%E6%95%B0%E6%8D%AE%E5%85%B1%E4%BA%AB h_01KVFJHWK1T1PN0ENT84PM2E69=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA supported-partners=%E9%80%82%E7%94%A8%E6%B8%A0%E9%81%93 h_01KVFJHWK1VTJZH53FKNE8NZ59=%E9%80%82%E7%94%A8%E6%B8%A0%E9%81%93 the-endtoend-flow=%E7%AB%AF%E5%88%B0%E7%AB%AF%E6%B5%81%E7%A8%8B h_01KVFJHWK1JQ7J838YNDTYDD4A=%E7%AB%AF%E5%88%B0%E7%AB%AF%E6%B5%81%E7%A8%8B h_01KVFJHWK1JNHRHP1NJ5YCXV70=%E6%B3%A8%E6%84%8F how-hashed-user-identifiers-reach-appsflyer=appsflyer-%E5%A6%82%E4%BD%95%E8%8E%B7%E5%8F%96%E5%93%88%E5%B8%8C%E7%94%A8%E6%88%B7%E6%A0%87%E8%AF%86%E7%AC%A6 h_01KVFJHWK197KW8YBQ1NBD9XT1=appsflyer-%E5%A6%82%E4%BD%95%E8%8E%B7%E5%8F%96%E5%93%88%E5%B8%8C%E7%94%A8%E6%88%B7%E6%A0%87%E8%AF%86%E7%AC%A6 h_01KVFJHWK1JVSGVKPS9C2M01ZP=%E6%B3%A8%E6%84%8F-1 h_01KVFJHWK15MA0FG7AFB999JQR=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-2 normalize-and-hash-identifiers=%E8%A7%84%E8%8C%83%E5%8C%96%E5%92%8C%E5%93%88%E5%B8%8C%E6%A0%87%E8%AF%86%E7%AC%A6 h_01KVFJHWK16KQ1X1WFTTTFFND3=%E8%A7%84%E8%8C%83%E5%8C%96%E5%92%8C%E5%93%88%E5%B8%8C%E6%A0%87%E8%AF%86%E7%AC%A6 h_01KVFJHWK2KRFS56PAZF23KXE2=email-email_hashed h_01KVFJHWK208WBE3NB5TER7RWM=phone-number-digits-only-phone_number_hashed h_01KVFJHWK2HBN91BS5D52FZJQ9=phone-number-e164-phone_number_e164_hashed h_01KVFJHWK26PAD582XDE14ZDBE=first-name-first_name_hashed-and-last-name-last_name_hashed h_01KVFJHWK2TC4FK1F260CZWGYE=facebook-login-id-fb_login_id turn-on-advancedmatching-data-sharing=%E5%90%AF%E7%94%A8%E9%AB%98%E7%BA%A7%E5%8C%B9%E9%85%8D%E6%95%B0%E6%8D%AE%E5%85%B1%E4%BA%AB h_01KVFJHWK27C5FA358M526EJED=%E5%90%AF%E7%94%A8%E9%AB%98%E7%BA%A7%E5%8C%B9%E9%85%8D%E6%95%B0%E6%8D%AE%E5%85%B1%E4%BA%AB h_01KVFJHWK2CQX93GDZ6G97E4Y0=%E6%B3%A8%E6%84%8F-2 privacy-and-data-handling=%E9%9A%90%E7%A7%81%E5%92%8C%E6%95%B0%E6%8D%AE%E5%A4%84%E7%90%86 h_01KVFJHWK2BN2T7BTXANAWAX4B=%E9%9A%90%E7%A7%81%E5%92%8C%E6%95%B0%E6%8D%AE%E5%A4%84%E7%90%86 h_01KVFJHWK2GX1PGCWFGYADE1S3=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-2 h_01KVFJHWK2XB5VF8V2KPG62QYV=faq h_01KVFJHWK2J7R7P123Z1877Y3H=is-advancedmatching-data-sharing-the-same-as-the-audiences-hashed-email-and-phone-feature h_01KVFJHWK2XS2WK3F3GDDYCZ92=what-happens-if-i-send-an-invalid-hash-value h_01KVFJHWK2XY4FBWMZH38GYD2V=do-i-need-to-send-all-supported-fields h_01KVFJHWK2HJS895AS5ANK94AX=will-advancedmatching-data-sharing-improve-install-attribution h_01KVFJHWK2R7BAMWZRC41PKAX4=does-appsflyer-ever-receive-plaintext-user-identifiers" />
