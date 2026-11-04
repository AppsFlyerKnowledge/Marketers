---
title: AppsFlyer token的管理方式
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2020-01-01T09:50:22Z'
  edited_at: '2026-10-14T10:11:54Z'
  id: 360004562377
  locale: zh-cn
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/zh-cn/articles/360004562377
---
> **概要：** Token可以帮助您强化数据安全。能让广告主通过AppsFlyer API获取数据，或使用服务器到服务器（S2S）的调用指令来接收事件数据。AF账户管理员可以在保障数据不中断的情况下管理多个token。Token管理包括API和S2S token的创建、重命名和移除等操作，具体取决于您的实际需求。

<div id="important" />

> 🚧 **重要提示！**
>
> ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)
>
> * 只有AppsFlyer账户的管理员才能查看和管理token。账户用户无法访问令牌页面。
> * 请妥善保存好您的token，因为这关系到您的数据读取权限。切勿在公共代码库中发布这些token。
> * 建议您每180天更换一次token。

<div id="about-appsflyer-tokens" />

## AppsFlyer token简介

广告主需要使用Token才能通过AppsFlyer API以及S2S调用指令获取数据。对于AF账户管理员来说，token有以下几种用途：

* 推行数据安全措施：
  * 为解决具体的数据安全隐患（如token被盗或疑似未授权访问）而更换token
  * 作为数据安全政策例行更新的一环定期更换token
* 管理多个API的调用
* 在测试中使用
* 在特定功能中使用，如OneLink API

<div id="reaching-the-tokens-page" />

## Tokens页面

1. 从页面顶部导航栏打开账户菜单（点击右上角的邮箱地址，打开下拉菜单）> **安全中心**。
2. 向下滚动到**AppsFlyer API token**部分，点击**管理您的AppsFlyer token。** 界面会显示当前正在使用的token。

<div id="token-types" />

## Token类型

我们针对各种不同的用途提供多种token。默认情况下，AF会为每个新账户生成一个API token（API token V2）。账户管理员最多可创建两个同一类型的token，详情请见下表。

| Token类型 | 用途 |
| --- | --- |
| <span id="api-token"></span>API token | 用于对Pull API、Cohort API、ROI API等各种API的调用进行授权的JWT token（即JSON Web Token）。 |
| <span id="onelink-api-premium"></span><Anchor target="_blank" href="/marketers/zh/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor>（高阶付费） | 该token用于OneLink API，具有唯一性。OneLink API用于生成个性化链接，帮助您充分提升用户与应用的互动，适用于大规模广告投放。 |
| <span id="s2s-token"></span>S2S token | 通过调用S2S API发送数据时使用。 |
| <span id="mcp-token"></span>MCP token： | 用于验证第三方或自托管系统与 AppsFlyer MCP。 |

<div id="manage-your-tokens" />

## 管理token

AppsFlyer账户管理员具有多个token的管理权限，包括token的创建、重命名、和移除，主要用于现行token换新。换新时需要先[创建](#token的创建方式)新token并将其部署到您的系统中，等到新token正式可用后将旧的token[删除](#token的删除方式)。

<div id="retrieve-tokens" />

### token的获取方式

1. 从页面顶部导航栏打开账户菜单（点击右上角的邮箱地址，打开下拉菜单）> **安全中心**。
2. 向下滚动到**AppsFlyer token**部分，点击管理您的AppsFlyer token。
3. 界面会显示可用token。
4. 根据实际需要复制相关token。

<div id="create-a-token" />

### token的创建方式

1. 在[**Tokens**页面](#tokens页面)中点击 **+新token**。
2. 输入token名称。
3. 选择token类型。
4. 单击**创建token**。

<div id="note-1" />

> 📘 **注意**
>
> * 新令牌立即可用。
> * 请确保将新token部署到您的系统中

### token的重命名方式

1. 在[**Tokens**页面](#tokens页面)中找到您想要重命名的token，然后点击该token的编辑图标。
2. 重新命名该token。
3. 点击**保存**。

<div id="delete-a-token" />

### token的删除方式

<div id="warning" />

> ❗️ **注意事项**
>
> * 删除某个token后，使用该token的系统可能会出现故障。
> * 删除令牌时，它会从令牌页面中移除，之前的令牌的所有调用都会被拒绝。
> * 如需更换token，请先创建一个新token并将其部署到您的系统中，等到新token正式变为可用状态后（即不再处于“处理中”的状态），才能删除旧的token。

1. 在[**Tokens**页面](#tokens页面)中找到您想要删除的token，然后点击该token的删除图标。
2. 确认要删除该token时必须键入“Delete token”。
3. 点击**删除token**。

<div id="applications-of-the-api-v2-token" />

## API V2 token的使用方式

下表列出了广告主和广告平台的API V2 token使用场景：

<div id="advertiser" />

### 广告主

| API V2 token |
| --- |
| <Anchor target="_blank" href="/marketers/zh/docs/pull-api-raw-data">Pull API 原始数据报告</Anchor> |
| <Anchor target="_blank" href="/marketers/zh/docs/pull-api-aggregate-data">Pull API汇总数据</Anchor> |
| <Anchor target="_blank" href="/marketers/zh/docs/app-list-api-for-app-owners">获取应用列表</Anchor> |
| <Anchor target="_blank" href="/marketers/zh/docs/cohort-api">群组</Anchor> |
| <Anchor target="_blank" href="/marketers/zh/docs/skan-aggregated-performance-report-api">SKAN汇总报告</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_copy">复制渠道对接设置</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-integration-params">设置Install Referrer解密密钥</Anchor> |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-tax-and-store-commission-rates-with-the-net-revenue-api">净收入 API</Anchor> |
| <Anchor target="_blank" href="/marketers/zh/docs/send-opendsr-api-requests">OpenDSR API</Anchor> |
| <Anchor target="_blank" href="/marketers/zh/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor> |
| 导入受众API |

<div id="ad-network" />

### 广告平台

| API V2 token |
| --- |
| <Anchor target="_blank" href="/partners/zh/docs/app-list-api-for-ad-networks">广告平台的应用列表</Anchor> |
| <Anchor target="_blank" href="/partners/zh/docs/access-to-aggregated-analytics-tools-for-api-partners">与广告投放管理平台对接</Anchor> |
| <Anchor target="_blank" href="/partners/zh/docs/protect360-for-integrated-partners#protect360的广告平台数据上报api">对接渠道的Protect360报告</Anchor> |
| <Anchor target="_blank" href="/partners/zh/docs/incost-api-for-ad-networks">InCost</Anchor> |

<div id="applications-of-the-s2s-token" />

## S2S token的使用方式

广告主和使用 S2S 令牌的广告主的用例：

<div id="advertiser-1" />

### 广告主

| S2S token |
| --- |
| <Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile">移动端应用内事件S2S API</Anchor> |
| <Anchor target="_blank" href="/marketers/zh/docs/server-to-server-s2s-api-for-web-performance-measurement">网络事件 S2S API</Anchor> |

<div id="ad-network-1" />

### 广告平台

| S2S token |
| --- |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-appsflyer-preload-referrer-attribution">AppsFlyer预装referrer归因</Anchor> |

<div id="note-2" />

> 📘 **注意**
>
> 对于大多数广告网络，S2S 令牌生成不再是自助服务。因此，管理员在用户界面中不会看到生成 S2S 令牌的选项。自助令牌生成仅适用于特定的托管合作伙伴。

<div id="applications-for-the-onelink-token" />

## OneLink token的用途

广告主的OneLink API token使用场景包括：

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/create-onelink-attribution-link">创建</Anchor>、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-attribution-link">获取</Anchor>、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/update-onelink-attribution-link">更新</Anchor>和<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/delete-onelink-attribution-link">删除</Anchor>带有自定义参数的OneLink短链。

<div id="applications-for-the-mcp-token" />

## MCP 令牌的申请

请参阅 <Anchor target="_blank" href="/marketers/zh/docs/beta-appsflyer-mcp">AppsFlyer MCP 文章</Anchor> 以查看 MCP 令牌的可用用例。

<div data-zendesk-anchors="01HFNX0XS4RAB543NKR12B2W50=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA overview=appsflyer-token%E7%AE%80%E4%BB%8B h_01HFY5D0E1H66CEB3KMJQEXV4K=appsflyer-token%E7%AE%80%E4%BB%8B reaching-the-tokens-page=tokens%E9%A1%B5%E9%9D%A2 h_01HFTT570KF3XM9MBSFYRDYN9S=tokens%E9%A1%B5%E9%9D%A2 token-types=token%E7%B1%BB%E5%9E%8B h_01HFBR7KP8BZN7KH0BNJ982WK8=token%E7%B1%BB%E5%9E%8B manage-your-tokens=%E7%AE%A1%E7%90%86token h_01HFY5D0E1AF4NYPX31W3VJYQC=%E7%AE%A1%E7%90%86token retrieving-api-tokens=token%E7%9A%84%E8%8E%B7%E5%8F%96%E6%96%B9%E5%BC%8F h_01HBQN3T2HKEMNC8MSR0THYW2S=token%E7%9A%84%E8%8E%B7%E5%8F%96%E6%96%B9%E5%BC%8F create-a-token=token%E7%9A%84%E5%88%9B%E5%BB%BA%E6%96%B9%E5%BC%8F h_01HFY5D0E1FECQC1HN0EXWMXAV=token%E7%9A%84%E5%88%9B%E5%BB%BA%E6%96%B9%E5%BC%8F h_01HFY5D0E1HJFKFPRT8WVNPHDG=%E6%B3%A8%E6%84%8F rename-a-token=token%E7%9A%84%E9%87%8D%E5%91%BD%E5%90%8D%E6%96%B9%E5%BC%8F h_01HFY5D0E2Z8ZH0PAX148C4F38=token%E7%9A%84%E9%87%8D%E5%91%BD%E5%90%8D%E6%96%B9%E5%BC%8F delete-a-token=token%E7%9A%84%E5%88%A0%E9%99%A4%E6%96%B9%E5%BC%8F h_01HFY5D0E2B1KXGSFZR0AYAER5=token%E7%9A%84%E5%88%A0%E9%99%A4%E6%96%B9%E5%BC%8F h_01HFY5D0E2KZYG0J2R7GR1R7W5=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 applications-of-the-api-v2-token=api-v2-token%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HG64DMW7PYRXBMZN00EQN991=api-v2-token%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F v20-token%E2%80%94advertiser-apis=%E5%B9%BF%E5%91%8A%E4%B8%BB h_01HBQN7TBASK192P8D7AEWM9P6=%E5%B9%BF%E5%91%8A%E4%B8%BB v20-token%E2%80%94ad-network-apis=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0 h_01HBQN7TBAWAHEQXMYK9V14G0M=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0 applications-of-the-s2s-token=s2s-token%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HG64M8K1PPY2Z2406MC78EEN=s2s-token%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F advertiser=%E5%B9%BF%E5%91%8A%E4%B8%BB-1 h_01JSKCVT6ACKHECVJGZ0QVD8C6=%E5%B9%BF%E5%91%8A%E4%B8%BB-1 h_01JSKD341C1EKE51Z16MMPG3Ckjh=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0-1 ad-network=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0-1 h_01KKBYBR8M9ZJWVB3MP1QG4FR4=%E6%B3%A8%E6%84%8F-1 applications-for-the-onelink-token=onelink-token%E7%9A%84%E7%94%A8%E9%80%94 h_01JSKCWS5406YQJP3RR9KAXJC9=onelink-token%E7%9A%84%E7%94%A8%E9%80%94 applications-for-the-mcp-token=mcp-%E4%BB%A4%E7%89%8C%E7%9A%84%E7%94%B3%E8%AF%B7 h_01K9YD2Y9M1C8QDBS5H048XYYD=mcp-%E4%BB%A4%E7%89%8C%E7%9A%84%E7%94%B3%E8%AF%B7" />
