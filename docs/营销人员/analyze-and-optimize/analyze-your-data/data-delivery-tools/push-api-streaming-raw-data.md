---
title: 通过Push API获取原始数据
metadata:
  keywords:
    - Push API
    - Real-time
    - Installation and Conversion
    - Advertisers
    - Developers
    - Premium
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Raw Reports
  created_at: '2013-04-24T15:19:42Z'
  edited_at: '2026-10-14T10:15:48Z'
  id: 207034356
  locale: zh-cn
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/zh-cn/articles/207034356
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 本文重点解释如何将已归因事件的原始数据实时发送到您的服务器端点。

![6970_Push_API_image.png](https://files.readme.io/0bb5747a65a6ca6ed8f55f72f189b92e780649d55b766c5d295f5602745f04f5-4405028260241.png)

## Push API

使用AppsFlyer或SKAN归因，生成原始数据后，您可以通过Push API将这些数据以推送消息的形式传输到您的服务器，并自行选择消息类型、消息内容，同时设置目标端点。

可用的消息类型、字段以及数据时效性取决于您使用的归因框架（AppsFlyer或SKAN），这在以下几个章节中会有详细说明。

<div id="appsflyer-attribution-messages" />

<Accordion title="AppsFlyer归因消息">

消息特征

| 主要特点 | 说明 |
| --- | --- |
| 消息类型区分 | <ul><li>您可以按端点来区分消息（每个应用最多可对应6个端点），也可以通过下列字段的值来判断消息类型。<ul><li>event\_name</li><li>conversion\_type</li><li>campaign\_type</li></ul></li><li>各消息类型所对应的字段值请见下表。</li></ul>**举例来说，**<br /><br />如果一个消息中包含以下字段：<ul><li>conversion\_type=install</li><li>campaign\_type=organic</li><li>event\_name=install</li></ul>对照下表可判断出该事件是一个自然量的激活事件。 |
| 数据时效性 | AppsFlyer平台记录到事件后会立即发出消息。发送过程一般需要几分钟。 |
| 消息内容（字段） | <ul><li>消息结构为`key:value`。</li><li>请参考AppsFlyer归因<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary#field-availability-by-reporting-tool">Push API</Anchor>的可用字段。</li><li>每个键值对代表一个原始数据字段。详情请见<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary#data-fields-dictionary">AppsFlyer的原始数据字段说明</Anchor>。</li><li>若键值为空或null，则不会出现在消息中。</li><li>以下所附示例中同时包含了null和空白字段，但实际回传中不会出现这两种字段。示例的文件格式为JSON。<ul><li>[iOS](https://docs.google.com/spreadsheets/d/e/2PACX-1vRMoTZpgttICSjjjXTh4JU5m9p3ky7Ej_MYc0kZ3vYs7sNq6u_wNvWBgjFLF_VjdRbY54aE5e-4keLY/pub?gid=0&single=true&output=csv)</li><li>[安卓](https://docs.google.com/spreadsheets/d/e/2PACX-1vRMoTZpgttICSjjjXTh4JU5m9p3ky7Ej_MYc0kZ3vYs7sNq6u_wNvWBgjFLF_VjdRbY54aE5e-4keLY/pub?gid=233131974&single=true&output=csv)</li></ul></li></ul> |
| 时间戳字段的格式： | <ul><li>UTC时间戳：`yyyy-mm-dd hh:mm:ss.sss`。 举例来说，如果时间戳显示为`2019-09-17 00:09:00.123`。就表示在东京时间18:00发生了一个事件，系统会自动将事件时间将转换为UTC时间，即09:00。记录的时间是UTC时间。</li><li>选定时区（取决于应用层级的配置）时间戳：`yyyy-mm-dd hh:mm:ss.sss±th:tm`。使用场景示例:就表示在东京时间18:00发生了一个事件，显示的事件时间记录为18:00+09:00。09:00为东京时区。</li></ul> |

#### 可用的消息类型

<table><thead><tr><th>归因场景</th><th>消息类型</th><th>conversion_type字段</th><th>campaign_type字段</th><th>event_name字段</th><th>event_type字段</th></tr></thead><tbody><tr><td>用户获取</td><td>激活\*</td><td>install</td><td><p>非自然量UA（用户获取）</p><p>自然：organic</p></td><td>install</td><td><ul><li>install</li><li>organic-install</li></ul></td></tr><tr><td>用户获取 </td><td>UA应用内事件</td><td><span>install</span></td><td><p>非自然量UA（用户获取）</p><p>自然：organic</p></td><td>广告主侧定义的事件名称</td><td><ul><li>install-in-app-event</li><li>organic-install-in-app-event</li></ul></td></tr><tr><td>再营销</td><td>Re-engagement（再互动）</td><td>re-engagement</td><td>retargeting（再营销）</td><td>re-engagement</td><td>re-attribution</td></tr><tr><td>再营销 </td><td>再互动应用内事件</td><td>re-engagement</td><td>retargeting（再营销）</td><td>广告主侧定义的事件名称</td><td>re-engagement-in-app-event</td></tr><tr><td>再营销 </td><td>再归因（reattribution） </td><td>reinstall</td><td>retargeting（再营销）</td><td>re-attribution</td><td>re-attribution</td></tr><tr><td>用户获取 </td><td>Reinstall（重装激活）</td><td>reinstall</td><td><p>非自然量UA（用户获取）</p><p>自然：organic</p></td><td>reinstall</td><td><ul><li>reinstall</li><li>organic-reinstall</li></ul></td></tr><tr><td>再营销</td><td>再归因应用内事件</td><td>reinstall</td><td>retargeting（再营销）</td><td>广告主侧定义的事件名称</td><td>re-attribution-in-app-event</td></tr><tr><td colspan="6">\*一部分浏览型激活会被归因到<a href="./about-raw-data-identifier-restrictions" target="_blank">restricted media source</a>（受限媒体渠道）。 </td></tr></tbody></table>

#### 专属字段

<table><thead><tr><th>字段名称</th><th>Push API名称</th></tr></thead><tbody><tr><td>Selected currency\*（指定货币）</td><td>selected_currency</td></tr><tr><td>Revenue in selected currency（按指定货币显示的收入数据）</td><td>revenue_in_selected_<br/>currency</td></tr><tr><td>Cost in selected currency（以指定货币为单位的成本数据）</td><td>cost_in_selected_<br/>currency</td></tr><tr><td>Device download time selected timezone（按指定时区显示的设备层级下载时间）</td><td>device_download_time_selected_timezone</td></tr><tr><td>Attributed touch time selected timezone（按指定时区显示归因到的触达时间）</td><td>attributed_touch_time_selected_timezone</td></tr><tr><td>Install time selected timezone（按指定时区显示的激活时间）</td><td>install_time_selected_<br/>timezone</td></tr><tr><td>Event time selected timezone（按指定时区显示的事件时间）</td><td>event_time_selected_<br/>timezone</td></tr><tr><td>Selected timezone(\*)（指定时区）</td><td>selected_timezone</td></tr><tr><td colspan="2">\*视API消息发送时的有效应用层级设置而定。</td></tr></tbody></table>

</Accordion>

<div id="skan-attribution-messages" />

<Accordion title="SKAN归因消息">

本章节重点说明SKAN框架中的可用消息（报告类型），以及如何判断消息类型。请先通读本章，然后参考[SKAN归因端点设置指南](/docs/push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint)。

相关文档：<Anchor target="_blank" href="/marketers/zh/docs/skan-raw-data-reports">SKAN原始数据字段</Anchor>。Push API消息的结构和字段与其对应。

消息特征：

| 主要特点 | 说明 |
| --- | --- |
| 消息类型区分 | <ul><li>所有消息都会发送到您设置的1个端点。</li><li>若要判断消息类型，请使用event\_type字段。<br />注意：event\_type字段也可以用于判断event\_name字段和skad\_redownload字段。</li><li>各消息类型所对应的字段值请[下表](/docs/push-api-streaming-raw-data#skan归因的消息类型)。</li></ul>举例来说，<br /><br />如果一个消息中包含以下字段：<ul><li>event\_type: skad-re-download</li></ul>由此可以确定：<ul><li>这是一个重新下载事件。</li><li>event\_name: install</li><li>skad\_redownload: true</li></ul> |
| 数据时效性 | <ul><li>激活、重装和应用内事件：<ul><li>按天进行数据处理</li><li>AppsFlyer收到iOS回传后的第二天发送到您设置的端点</li><li>您会在UTC时间的08:00–11:00接收到事件消息（具体时间可能会有所波动）</li><li>举例来说，周一接收到的回传数据会在周二UTC时间的05:00开始发送</li></ul></li><li>来自iOS的回传和回传副本：AppsFlyer收到消息后将很快发送。</li></ul> |
| 消息示例 | 请见表格。示例的文件格式为JSON。 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vS0CO6W7jgx6zxMeSGIo-hbqLbFh3AO0OT6qp4cWmgdbWVMjLJ-2dermVz49jmAXexewiOGzR1YjGzu/pub?output=xlsx">SKAN示例消息</Anchor>。 |

#### SKAN归因的消息类型

| 消息类型 | event\_name字段 | skad\_redownload字段 | event\_type字段 |
| --- | --- | --- | --- |
| 激活假量 | install | <ul><li>可能出现的值：false、空白值、null。</li><li>若该字段未出现在消息中，则视对应值为false。</li></ul> | skad-installs |
| 重新下载（redownloads） | install | True | skad-re-download |
| 应用内事件 | 广告主侧设置的事件名称 | 广告主侧设置的事件名称 | skad-in-app-event |
| 来自iOS的回传 | 本消息中不可用 | 本消息中有时可用 | skad-postback |
| <Anchor target="_blank" href="/marketers/zh/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">回传备份</Anchor> | 本消息中不可用 | 本消息中有时可用 | skad-postback-copy |

</Accordion>

## 设置Push API端点

> ❗️ **注意事项**
>
> 出于下列原因，请不要使用Push API将AppsFlyer归因产生的数据发送给第三方：
>
> * 如果用户拒绝将其数据发送给第三方，这种做法就违反了有关的隐私条例（如CCPA等）
> * 某些媒体渠道所提供的用户级数据会在使用方式和/或共享方式方面有所限制。请务必遵守这些媒体渠道的使用条款。
>   如[X Ads、](https://business.twitter.com/en/help/ads-policies/introduction-to-twitter-ads/twitter-ads-policies.html)[Snapchat、](https://www.snap.com/en-US/privacy/privacy-policy/)[Pinterest。](https://policy.pinterest.com/en/privacy-policy)
>
> 请注意：  该事项不适用于SKAN数据，您可以使用Push API将SKAN数据发送到第三方端点。

请按下表所列的步骤设置Push API。

#### Push API设置流程

<table><thead><tr><th>步骤顺序 </th><th>AppsFlyer归因</th><th>SKAdNetwork归因  </th></tr></thead><tbody><tr><td>1</td><td colspan="2"><p>如果您已经有正在使用中的Push API端点，请跳过这一步。 </p><p>请确保您的服务器符合<a href="./push-api-streaming-raw-data#serverside-requirements-your-server">相关要求</a>。</p></td></tr><tr><td>2</td><td>若要使用AppsFlyer归因，请按照<a href="./push-api-streaming-raw-data#push-api-planning-checklist-for-appsflyer-attribution">Push API设置规划表</a>来规划端点的设置。 </td><td>不适用</td></tr><tr><td>3</td><td><a href="./push-api-streaming-raw-data#set-up-appsflyer-attribution-endpoint">设置AppsFlyer归因端点</a></td><td><a href="./push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint">设置SKAdNetwork归因端点</a></td></tr></tbody></table>

<div id="serverside-requirements-your-server" />

<Accordion title="服务器端须符合的要求（广告主侧）">

请确保您的服务器符合以下要求：

#### 服务器端要求

| 端点URL | <ul><li>域名有效</li><li>每个应用所对应的独立端点数上限如下：<ul><li>AppsFlyer：6个端点</li><li>SKAdNetwork3个端点</li></ul></li></ul> |
| --- | --- |
| 端点返回码 | 收到消息后，您的端点必须返回HTTP 200状态代码。 |
| AppsFlyer服务器加白 | 在您的防火墙和安全系统中对AppsFlyer服务器的<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-server-ip-address-ranges-allowlisting">IP地址</Anchor>加白，以确保AF服务器与端点之间的数据传输保持畅通。 |
| TLS版本 | <ul><li>TLS 1.1</li><li>TLS 1.2+，具体请参见<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-https-ssl-encryption-policy-support#outgoing-messages-appsflyer-as-client">适用的加密体系</Anchor></li></ul> |
| 端口 | 端口：80, 443 |

**请注意**：这里使用了一个为时4秒的计时机制，如果在这4秒内AF的服务器没有接收到发送成功的消息，那么系统就会认为该消息发送失败。

</Accordion>

<div id="push-api-planning-checklist-for-appsflyer-attribution" />

<Accordion title="针对AppsFlyer归因的Push API设置规划表">

* 请参照下表说明，规划您的AppsFlyer归因端点设置，图中的数字与下面清单中的行号匹配。
* 本节内容不涉及SKAdNetwork，有关SKAN归因的说明请参见[SKAdNetwork归因设置](/docs/push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint)。

**端点**

[![PushAPI_us-en.png](https://files.readme.io/38b22e23c087e97c5424b649552823635310402a5c7be742bf6fc4e16d86cc42-360007246758.png)](https://files.readme.io/38b22e23c087e97c5424b649552823635310402a5c7be742bf6fc4e16d86cc42-360007246758.png)

#### 端点规划表

| 不可以。 | 配置 | 说明 | 在本栏中记录您的设置规划 |
| --- | --- | --- | --- |
| 1 | 方法 | POST 或者 GET |  |
| 2 | 端点URL | - |  |
| 3 | 事件消息类型 | <ul><li>选择至少一种事件消息类型。</li><li>必须要先记录到至少一个应用内事件后，您才能勾选对应的应用内事件消息，否则该选项将显示为不可用。</li></ul>[![InappSelectionDisabled_us-en.png](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png) |  |
| 4 | <ul><li>字段</li><li>字段列表是所有消息类型共有的</li></ul> | **<span id="01H8E8DET2PBGQAKHJY40R1P9Z"></span>重要提示**<br />选择全部并不会自动包含将来添加的消息字段。要包含新字段，您必须手动更新选择。<br /><br /><br /><br />选择所需的字段。<ul><li>最常用的字段是默认勾选的</li><li>空/null的字段不会被发送</li></ul> |  |
| 5 | 应用内事件类型 | 您可以按应用内事件进行筛选，以控制发送到端点的流量。<ul><li>您可以选择一个、多个或所有应用内事件。请注意：如果事件未显示在列表中，请直接搜索该事件。</li><li>应用内事件必须至少被记录到一次，相应的消息选项才会显示为可选。 必要情况下可使用<Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>来发送事件。</li><li>[![mceclip1.png](https://files.readme.io/b945d7bf1b8cebb3a4b925fb240e3e1976aee934f1179cca68680ae21d565bf3-360007337257.png)](https://files.readme.io/b945d7bf1b8cebb3a4b925fb240e3e1976aee934f1179cca68680ae21d565bf3-360007337257.png)</li></ul> |  |

</Accordion>

<div id="set-up-appsflyer-attribution-endpoint" />

<Accordion title="设置AppsFlyer归因端点">

所有有权限访问API的团队成员都可以更改Push API设置。其他类型的用户只能查看该设置。

#### 请按以下步骤添加AppsFlyer归因端点：

1. 在AppsFlyer中，从侧边栏打开<strong>导出 > API访问。</strong>向下滚动到Push API部分。
2. 单击**添加端点。**
3. 选择HTTP方法： **POST**或者**GET**
4. 输入**端点URL**。 如果收到*this URL is not safe*（该URL不安全）的消息，请联系AppsFlyer技术支持。
5. 选择一种或多种事件类型。**请注意**：如果应用内事件消息显示为不可用，说明尚未记录到任何应用内事件。
6. 选择Push API消息中需要包含的字段。请注意：
   * 消息中始终包含必填字段：应用ID、事件名称、事件时间、IDFA（iOS）或Advertising ID（安卓）
   * 使用下图中描绘的控件选择可选字段。[![PushAPIFieldSelect1.jpg](https://files.readme.io/316bdfcb4740d870875176e7806f969c89784406c3abc5ca34c9fa0c675a5497-360007416298.jpg)](https://files.readme.io/316bdfcb4740d870875176e7806f969c89784406c3abc5ca34c9fa0c675a5497-360007416298.jpg)
     * 最常用的字段是默认勾选的您可以手动取消这些选项。
     * 根据需要选择可选字段。
     * 点击**清除全部**，清除所有可选字段。
     * AF系统不会发送null/空的字段及其对应的键，在数据入库BI和解析过程中，请留意此处。
7. 选择一个或多个（最多52个事件）或“ **所有**应用内事件”。
   * 该列表中只包含已经记录到的事件类型。如果其中没有显示您想要的事件类型，请先使用测试设备发送这类事件。
8. 点击**保存**。  
   该Push API就开始生效，将转化数据发送到端点。
9. 请按以下步骤测试端点。

#### 测试端点：

1. 点击**发送测试。**  
   **发送测试**按钮下方会显示测试结果。   
   测试消息将被发送到端点。如果显示测试失败，请确保您已对<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-server-ip-address-ranges-allowlisting">AppsFlyer服务器的IP地址加白</Anchor>。   
   **请注意**：这里使用了一个为时2秒的计时机制，如果在这4秒内AF的服务器没有接收到发送成功的消息，那么系统就会认为该消息发送失败。
2. 为确认您的端点是否接收到了测试消息，  
   您可以[查看测试消息的副本](https://docs.google.com/spreadsheets/d/e/2PACX-1vScQf189h3Ry0BU-ejbZYkMZCJRdXXYeOwuNxPEHwY77vCVYWW9P9xCTUSJKmTvVbp_yzLidXD0WGLm/pub?gid=0&single=true&output=csv)。

</Accordion>

<div id="set-up-skadnetwork-attribution-endpoint" />

<Accordion title="设置SKAdNetwork归因端点">

所有有权限访问API的团队成员都可以更改Push API设置。其他类型的用户只能查看该设置。

**请按以下步骤添加SKAdNetwork Push API端点：**

1. 在AppsFlyer中，从侧边栏打开<strong>导出 > API访问。</strong>向下滚动到Push API部分。
2. 选择**SKAdNetwork**作为归因实体。
3. 单击**添加端点。**  
   **请注意**：您可以为每个应用定义1-3个SKAdNetwork端点。
4. 选择HTTP方法： **POST**或者**GET**
5. 输入**端点URL**。 如果收到*this URL is not safe*（该URL不安全）的消息，请联系AppsFlyer技术支持。
6. AF系统不会发送null/空的字段及其对应的键，在数据入库BI和解析过程中，请留意此处。
7. 点击**保存**。  
   该Push API就开始生效，将数据发送到端点。

</Accordion>

<div id="configure-authentication-token" />

<Accordion title="配置身份验证令牌">

通过使用<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/put_tokens-app-app-id">Push API身份验证令牌</Anchor>，客户可以无缝接入并保护其Push API消息安全，只需为请求的令牌添加一个可自定义的授权header即可。  
您可以通过为每个App ID定义令牌名称和值，自定义随Push API消息一同发送的授权 header。这样不仅可确保消息的安全性，也能满足您的特定需求。

</Accordion>

## 其他操作 — 端点管理

所有有权限访问API的团队成员都可以更改Push API设置。其他类型的用户只能查看该设置。

<div id="change-an-endpoint" />

<Accordion title="修改端点设置">

**请按以下步骤修改端点设置：**

1. 在AppsFlyer中，从侧边栏打开<strong>导出 > API访问。</strong>向下滚动到Push API部分。
2. 找到要修改的端点。
3. 进行修改。
4. 点击**Save**。

</Accordion>

<div id="delete-an-endpoint" />

<Accordion title="删除端点">

**删除端点** ：

1. 在AppsFlyer中，从侧边栏打开**导出 > API访问。向下滚动到Push API部分。**
2. 单击**删除端点** 。
3. 点击**保存**。  
   端点被删除。

</Accordion>

## 问题排查、特点和局限性

<div id="test-message-fails" />

<Accordion title="未收到测试消息">

如果您的服务器通过IP地址来限制访问，在这种情况下没有接收到测试消息可能是因为没有<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-server-ip-address-ranges-allowlisting">对所有的AppsFlyer IP地址加白</Anchor>。

</Accordion>

<div id="duplicate-retargeting-inapp-events" />

<Accordion title="再营销应用内事件的重复">

如果用户点击了再营销广告并产生了付费事件，而该事件又发生在UA再互动窗口期内，这时再营销应用内事件就会发生重复。这一机制背后的逻辑是要将收入同时归因到UA渠道和再营销渠道。

如果您同时启用了以下两项，就会发生事件重复：

* UA应用内事件
* 再营销应用内事件

<Anchor target="_blank" href="/marketers/zh/docs/resolve-retargeting-double-attribution">事件重复的判断及去重</Anchor>

</Accordion>

<div id="inapp-event-message-selection-is-disabled" />

<Accordion title="应用内事件消息不可用">

[![InappSelectionDisabled_us-en.png](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)

* 应用内事件必须至少被记录到一次，相应的消息选项才会显示为可选。
* 使用测试设备生成应用内事件，或使用 <Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S API</Anchor>手动生成事件。

</Accordion>

<div id="missing-push-messages-and-cloudfront" />

<Accordion title="推送消息缺失和CloudFront">

如果您使用Amazon CloudFront作为端点，请检查您的CloudFront是否通过421拒绝码拒绝接收消息。如果发生上述情况，请参考<Anchor target="_blank" href="https://docs.aws.amazon.com/en_pv/AmazonCloudFront/latest/DeveloperGuide/cnames-https-dedicated-ip-or-sni.html">如何选择CloudFront对HTTPS请求的响应方式</Anchor>。

</Accordion>

<div id="endpoint-error-messages" />

<Accordion title="端点错误消息">

**具体问题**：设置端点URL时显示“*this URL is not safe*“（此URL不安全）的消息。

**应对办法**：联系AppsFlyer技术支持，在问题描述中包含应用ID、端点URL，以及错误消息截屏。

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="特点与局限性">

| **特点** | 说明 |
| --- | --- |
| <span id="ad-networks"></span>广告平台 | 不可用 |
| <span id="agencies"></span>代理 | 不可用 |
| <span id="appspecific-time-zone"></span>应用层级的指定时区 | 支持 |
| <span id="appspecific-currency"></span>应用配置中的指定货币 | 支持 |
| <span id="size-limitations"></span>大小限制 | 不适用 |
| <span id="organic"></span>自然量 | 是 |
| <span id="nonorganic"></span>非自然量 | 是 |
| <span id="data-freshness"></span>数据时效性 | 持续滚动 |
| <span id="historical-data"></span>历史数据 | 不支持。如果出现数据缺失，请使用Pull API来拉取数据。在SKAN归因的场景下，您可以通过Data Locker获取部分历史数据（具体取决于Data Locker的数据可用性窗口）。 |
| <span id="account-owneruser-access"></span>账户所有者/用户权限 | 只有AppsFlyer**账户所有者**才能更改Push API设置。<ul><li>每个AppsFlyer账户下**只能有一个**账户所有者。账户所有者**是相关AppsFlyer账户中的首个用户（即开户时创建的用户）**。</li></ul>其他类型的用户可以查看Push API设置，但不能对其进行更改。 |
| <span id="authentication-token-in-test-messages"></span>测试消息中的身份验证令牌 | [测试消息](#测试端点)的header不包含身份验证令牌。 |

</Accordion>

<div id="can-i-include-custom-headers-with-the-push-api-request" />

<Accordion title="我可以在Push API请求中添加自定义header吗？">

不可以。Push API仅支持使用header传递身份验证令牌。**不支持**额外的自定义header（如`consumer-key`）。

如果需要传递额外参数，请将其包含在URL中。使用场景示例:

```
https://your.server.com?consumer_key=abc456
```

</Accordion>

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">各种原始数据传输工具的对比</Anchor>
> * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/put_app-app-id">使用API设置Push API</Anchor>

<div data-zendesk-anchors="01H89PJFBPXVKJGGH18CJBJ41W=push-api 01H89PJFBP45FQDHT4YGS58NP8=appsflyer-attribution-messages available-message-types=%E5%8F%AF%E7%94%A8%E7%9A%84%E6%B6%88%E6%81%AF%E7%B1%BB%E5%9E%8B 01H89PJFBP9DEX520BDGC5PANQ=%E5%8F%AF%E7%94%A8%E7%9A%84%E6%B6%88%E6%81%AF%E7%B1%BB%E5%9E%8B unique-fields=%E4%B8%93%E5%B1%9E%E5%AD%97%E6%AE%B5 01H89PJFBPBK09Q7CRPMM4G7PJ=%E4%B8%93%E5%B1%9E%E5%AD%97%E6%AE%B5 01H89PJFBQM4NKFSFF8XGMX9XT=skan-attribution-messages message-types-for-skan-attribution=skan%E5%BD%92%E5%9B%A0%E7%9A%84%E6%B6%88%E6%81%AF%E7%B1%BB%E5%9E%8B 01H89PJFBQBFCK5QVWW2X09H28=skan%E5%BD%92%E5%9B%A0%E7%9A%84%E6%B6%88%E6%81%AF%E7%B1%BB%E5%9E%8B set-up-push-api-endpoints=%E8%AE%BE%E7%BD%AEpush-api%E7%AB%AF%E7%82%B9 01H89PJFBQZ2FW3ST5V4FW91GS=%E8%AE%BE%E7%BD%AEpush-api%E7%AB%AF%E7%82%B9 01H89PJFBQ6WP7ERP0DJ69QZ1G=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 push-api-setup-checklist=push-api%E8%AE%BE%E7%BD%AE%E6%B5%81%E7%A8%8B 01H89PJFBQ625A7G3QT5HQJXMW=push-api%E8%AE%BE%E7%BD%AE%E6%B5%81%E7%A8%8B 01H89PJFBQGW8ZV76Z0HTNX2AB=serverside-requirements-your-server serverside-requirements=%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%AB%AF%E8%A6%81%E6%B1%82 01H89PJFBQ2BC5GHX403RD2RAT=%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%AB%AF%E8%A6%81%E6%B1%82 01H89PJFBQ4FXB7ABMFVHX326H=push-api-planning-checklist-for-appsflyer-attribution endpoint-planning-table=%E7%AB%AF%E7%82%B9%E8%A7%84%E5%88%92%E8%A1%A8 01H89PJFBQJXWWPQDKZ387VYX3=%E7%AB%AF%E7%82%B9%E8%A7%84%E5%88%92%E8%A1%A8 01H89PJFBQZE6KJDHXRB8GK7TF=set-up-appsflyer-attribution-endpoint add-an-appsflyer-attribution-endpoint=%E8%AF%B7%E6%8C%89%E4%BB%A5%E4%B8%8B%E6%AD%A5%E9%AA%A4%E6%B7%BB%E5%8A%A0appsflyer%E5%BD%92%E5%9B%A0%E7%AB%AF%E7%82%B9 h_01JFSS65G8GTZNMY257QCV922M=%E8%AF%B7%E6%8C%89%E4%BB%A5%E4%B8%8B%E6%AD%A5%E9%AA%A4%E6%B7%BB%E5%8A%A0appsflyer%E5%BD%92%E5%9B%A0%E7%AB%AF%E7%82%B9 test-the-endopoint=%E6%B5%8B%E8%AF%95%E7%AB%AF%E7%82%B9 h_01JFSS6YVP1WFWXSZ7HP7GTDA2=%E6%B5%8B%E8%AF%95%E7%AB%AF%E7%82%B9 01H89PJFBQQS31C6AF245SSJ61=set-up-skadnetwork-attribution-endpoint h_01HSDW5XQ28T3SQJTN5PBSBCFT=configure-authentication-token additional-procedures%E2%80%94managing-endpoints=%E5%85%B6%E4%BB%96%E6%93%8D%E4%BD%9C--%E7%AB%AF%E7%82%B9%E7%AE%A1%E7%90%86 01H89PJFBQ7WV3NM7JR5Z9QEFB=%E5%85%B6%E4%BB%96%E6%93%8D%E4%BD%9C--%E7%AB%AF%E7%82%B9%E7%AE%A1%E7%90%86 01H89PJFBQ9RZXNHGNNYV5MP7P=change-an-endpoint 01H89PJFBQGE1WESD7ZEMBEFNE=delete-an-endpoint troubleshooting-traits-and-limitations=%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5%E7%89%B9%E7%82%B9%E5%92%8C%E5%B1%80%E9%99%90%E6%80%A7 01H89PJFBQJDGT1FVHKG9DETHJ=%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5%E7%89%B9%E7%82%B9%E5%92%8C%E5%B1%80%E9%99%90%E6%80%A7 01H89PJFBQAAZYF7YWKC7TP884=test-message-fails 01H89PJFBQHQJSHE09GC599AQ6=duplicate-retargeting-inapp-events 01H89PJFBRDET8T8CTAP1GW0J9=inapp-event-message-selection-is-disabled 01H89PJFBRH58FX1FTH37DP3HC=missing-push-messages-and-cloudfront 01H89PJFBR3CJSR2AEFP3HT5JE=endpoint-error-messages 01H89PJFBRZXXEMPBGBPB35MQ9=specifications-and-limitations h_01JQY6KXYBGXTSVDC18H5CZCWR=can-i-include-custom-headers-with-the-push-api-request h_01HE7SH7XFMPJ13DKCZ04RCJDD=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
