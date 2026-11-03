---
title: 移动设备的S2S事件API（S2S-mobile）
metadata:
  keywords:
    - iOS
    - Android
    - API
    - In-App
    - S2S
    - HTTP API
    - appsflyer_id
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2014-05-21T17:47:21Z'
  edited_at: '2026-10-14T10:02:33Z'
  id: 207034486
  locale: zh-cn
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/zh-cn/articles/207034486
---
> **概要：** 本文讲解了如何从广告主服务器向AppsFlyer发送事件数据，以衡量在应用外部发生的移动事件。

[![S2S_us-en.png](https://files.readme.io/2f228a03ca00df529e42bd033825a0dca595e99a537cadcfd5419754a29b5490-35863179575441.png)](https://files.readme.io/2f228a03ca00df529e42bd033825a0dca595e99a537cadcfd5419754a29b5490-35863179575441.png)

## 移动设备的S2S事件API

对于iOS 14以上的应用版本，您需要发送OS（操作系统）参数。

AppsFlyer平台会对由AppsFlyer SDK和API发送的移动应用事件进行归因和记录，因此您可以使用S2S API上报应用程序外部发生的事件（如用户在您的网页端完成的续订）。记录到的S2S事件会反映在AF后台的所有面板/报告中，包括控制面板，原始数据和分析报告。另请参阅<Anchor target="_blank" href="/marketers/zh/docs/web-server-to-server-events-api-for-pba-web-s2s">适用于PBA的网页S2S</Anchor>，了解有关PBA网页事件的详情。

AppsFlyer会将以下信息填充到S2S事件中：

* S2S消息中发送的值
* AppsFlyer的部分归因信息，例如激活时间和媒体渠道。

如需通过API发送事件，请让您的开发人员按照<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">服务器到服务器事件API指南</Anchor>完成相关设置。

## 填充参数

<div id="difference-between-organic-and-nonorganic" />

<Accordion title="自然量与非自然量的区别">

AppsFlyer处理S2S应用内事件时，会通过AppsFlyer ID来识别相关应用内事件之前的激活事件，从而填充归因字段。

也就是说，AppsFlyer会将某些数据与非自然的S2S应用内事件相关联，而这些数据与自然的S2S应用内事件是不相关的。

> 📄 **示例**
>
> 如果对比非自然和自然的S2S应用内事件原始数据报告, 会发现非自然事件中包含自然事件所没有的数据。
>
> 这些数据包括媒体渠道、广告系列、触点类型、触达时间等。
>
> 另一方面, 自然应用内事件来自于自然安装。而自然激活本来就没有广告系列、媒体渠道、触点类型和触达时间等数据。

</Accordion>

<div id="mapping-appsflyer-id-with-customer-user-id-cuid" />

<Accordion title="AppsFlyer ID与客户用户ID（CUID）之间的映射">

需要通过后端逻辑获取相关的值来填充参数。请按以下步骤获取AppsFlyer ID：

* AppsFlyer ID是必须配置的参数，用于归因事件。
* 该ID是在用户首次激活应用时生成的。
* 如果需要将CUID映射到AppsFlyer ID，请务必在应用中设置CUID。

请部署以下链路，以便将用户关联到事件：

* 在用户激活应用时<Anchor target="_blank" href="/marketers/zh/docs/customer-user-id-field-cuid">设置客户用户ID（CUID)</Anchor>
* AppsFlyer原始数据报告中会包含CUID和AppsFlyer ID。您可以使用任意数据传输工具或AppsFlyer的Push API来获取该数据。
* 使用原始数据报告将CUID与AppsFlyer ID进行匹配。
* 您在应用（安卓/iOS）中接入AppsFlyer SDK后，SDK会在用户激活应用时生成AppsFlyer ID。
* 将AppsFlyer ID映射到内部系统中的客户用户ID（CUID）（后续会有重要作用）。

AppsFlyer ID与CUID之间形成映射后，就可以将用户匹配到他们完成的事件。然后，您可以获取其他值（事件值，事件币种，事件时间等），并发送S2S应用内事件。

</Accordion>

<div id="fetching-the-appsflyer-id" />

<Accordion title="提取AppsFlyer ID">

`appsflyer_id`是服务器到服务器事件消息中的必要参数。AppsFlyer需要使用该参数才能将事件归因到原始设备和媒体渠道。您可以使用以下任一种方法获取该ID：

* 调用AppsFlyer SDK API，从移动设备端获取：

  <Tabs>
  <Tab title="安卓原生">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#getappsflyeruid">getAppsFlyerUID</Anchor>

  </Tab>

  <Tab title="iOS原生">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#getappsflyeruid">getAppsFlyerUID</Anchor>

  </Tab>

  <Tab title="Unity">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#getappsflyerid">getAppsFlyerId</Anchor>

  </Tab>

  <Tab title="React Native">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#getappsflyeruid">getAppsFlyerUID</Anchor>

  </Tab>
  </Tabs>

* 通过以下方式从AppsFlyer平台获取：<Anchor target="_blank" href="/marketers/zh/docs/pull-api-raw-data?query=pull">Pull API,</Anchor> <Anchor target="_blank" href="/marketers/zh/docs/push-api-streaming-raw-data">Push API,</Anchor>导出<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">原始激活数据</Anchor>。

</Accordion>

<div id="time-stamping-s2s-events" />

<Accordion title="S2S事件 的时间戳">

[![时间戳逻辑示意图](https://files.readme.io/2d9138cc505b0ab1bb106c00fb2d71bd1d070ee236d7f928c8b8b85afe14af59-35863166628497.png)](https://files.readme.io/2d9138cc505b0ab1bb106c00fb2d71bd1d070ee236d7f928c8b8b85afe14af59-35863166628497.png)

AppsFlyer批量接收S2S事件，并根据其`eventTime`的参数值和送达时间设置时间戳。`eventTime`参数值表示应用内事件发生的时间。

事件送达AppsFlyer时，其时间戳的判定方式如下：

* 如果事件记录中不包含`eventTime`参数，则事件时间为HTTP消息的送达时间。
* 如果事件在UTC时间02:00之前送达，其时间戳为`eventTime`的参数值。也就是说，如果某事件的时间戳为`eventTime`值，则表示该事件的上报时间一定是事件发生当天或第二天的UTC时间02:00前。
* 如果前一天或更早之前发生的事件在UTC时间02:00后送达，则其时间戳为数据送达时间（及API调用时间）。
* 如果事件中的`eventTime`参数值为未来的时间（即eventTime > 事件送达时间）：
  * 如果`eventTime`中上报的时间和事件送达时间属于同一天，则该事件的时间戳取`eventTime`的值。
  * 如果`eventTime`中上报的时间在事件送达时间的次日，则该事件的时间戳取事件送达时间。
* 如果事件中的`eventTime`值无效，则该事件的时间戳为HTTP消息送达的时间。

**示例**

* 发送一个事件，事件数据中带有`eventTime`= Monday 21:00。

| 事件送达AppsFlyer的时间 | AppsFlyer判定的时间戳 | 说明 |
| --- | --- | --- |
| 星期二01:00 | 星期一21:00 | 由于该事件在当天的营业时间结束前送达，因此其时间戳为`eventTime`的值。 |
| 星期三09:00 | 星期三09:00 | 由于该事件在当天的营业时间结束后送达，因此其时间戳为送达时间。 |

</Accordion>

<div id="sending-negative-revenue" />

<Accordion title="发送负收入">

您可以发送收入值为负的事件（如订单被取消）。参数`af_revenue`可以通过负值来记录此信息。

如果使用`af_quantity`，请根据您的系统逻辑来决定是否在其中填充负值。AppsFlyer不会使用`af_quantity`。

</Accordion>

> 📘 **注意事项**
>
> 如需将S2S事件计入<Anchor target="_blank" href="/marketers/zh/docs/incrementality-for-remarketing-overview">增量分析</Anchor>，其数据中必须包含广告ID（iOS需包含IDFA，Android需包含GAID）。

## 提高数据事务处理量

在使用渐进式扩容（gradual scaling）的场景下，AppsFlyer支持基于自动扩展（auto-scaling）方案处理高并发的每秒事务数（TPS）。例如：使用场景示例:

* 从10K开始，按1分钟为单位逐步提升TPS：
  * 00:00:00 - 发送10K TPS（基线）
  * 00:01:00 - 增加到12K TPS
  * 00:02:00 - 增加到14K TPS
  * 00:03:00 - 增加到16K TPS
  * 00:04:00 - 增加到18K TPS
  * …
* 请务必设置重试机制，以便在接收到错误响应时自动重发请求。

## 问题排查

<div id="events-arent-displaying-in-the-dashboard" />

<Accordion title="事件未在面板中显示">

* 端点:端点（endpoint)：请检查您所使用的节点（endpoint）是否正确。
* 请检查事件请求（payload）中是否包含所有必填参数，查看[说明](/docs/server-to-server-events-api-for-mobile-s2s-mobile#mapping-appsflyer-id-with-customer-user-id-cuid)。
* 请确保您用来触发事件的AppsFlyer ID是真实的appsflyer\_id，并且已存入应用中。查看[说明](/docs/server-to-server-events-api-for-mobile-s2s-mobile#fetching-the-appsflyer-id)。
* 一个S2S请求中不能包含多个事件，每个事件都必须单独发送。
  * 可以使用异步方式发送事件，以缩短响应时间。
* 在数据总览面板中，日期范围中的日期是指应用激活日期（即LTV维度），而非事件发生日期。
  * 确保您选择了正确的日期范围。
  * 确保面板日期范围对应于设备的激活日期（appsflyer\_id），而不是事件的日期。
* 事件原始数据报告：日期范围中的日期是事件发生日期，而非应用激活日期。

</Accordion>

<div id="events-dont-contain-revenue" />

<Accordion title="事件不包含收入">

如果发送的S2S事件中未记录收入：请确保JSON是字符串格式的。最重要的部分是JSON中的事件值参数。请务必将其转化为下图示例中的格式。

```json
"{\"af_revenue\":\"6\" ,\"af_content_type\":\"wallets\"}"
```

如果事件值未转化成字符串格式，则无法得到正确处理，导致记录不到收入。

收入值不得以任何方式设置格式。该值可以包含一个小数点，不包括货币符号或代码也不包括`,`分隔符。收入可以以`-`为前缀

* 有效值示例：`123`，`-123.45`，`123.456`
* 无效值示例：`1,234.56`，`1,234`

</Accordion>

<div id="not-all-fields-are-populated-in-s2s-events" />

<Accordion title="S2S事件中部分字段未被填充">

S2S事件的原始数据字段仅填充S2S调用中发送的值。因此，通过S2S API发送的事件中，以下字段无法通过S2S接口上报，因此在原始数据报告中将不会显示这些字段的内容：

* WIFI
* Operator
* Language
* Device Model
* Device Category（设备类别）
* App Version:您可以使用`app_version_name`
* App Name（应用名称）

</Accordion>

<div id="S2S_in-app_events_are_wrongly_attributed_as_organic" />

<Accordion title="S2S 应用内事件被错误归因为自然流量">

某些S2S事件（如登录事件）可能会在应用刚安装并启动SDK后立即发送至AppsFlyer。但如果这些S2S应用内事件在激活事件尚未完成处理前（通常处理时间为20–30秒或更久）被发送到AppsFlyer系统，它们可能会被标记为未归因的自然事件（organic）。

对于激活后立即发生的S2S应用内事件，建议您在上报至AppsFlyer服务器前加入短暂延时。

</Accordion>

<div data-zendesk-anchors="servertoserver-events-api-for-mobile=%E7%A7%BB%E5%8A%A8%E8%AE%BE%E5%A4%87%E7%9A%84s2s%E4%BA%8B%E4%BB%B6api h_01H9Q8KBYGXAA8H4AKKXP8T8DY=%E7%A7%BB%E5%8A%A8%E8%AE%BE%E5%A4%87%E7%9A%84s2s%E4%BA%8B%E4%BB%B6api populating-parameters=%E5%A1%AB%E5%85%85%E5%8F%82%E6%95%B0 h_01H9Q8KBYGHY1SDSMSFZRT2JXZ=%E5%A1%AB%E5%85%85%E5%8F%82%E6%95%B0 h_01H9Q8KBYG6W4TERWHARZZZASZ=difference-between-organic-and-nonorganic h_01H9Q8KBYG0JCCGTEJW3GXZMF1=%E7%A4%BA%E4%BE%8B h_01H9Q8KBYG6EBKPS5Y2KC1QT7G=mapping-appsflyer-id-with-customer-user-id-cuid h_01H9Q8KBYGR26VMQR9Y0CK85F6=fetching-the-appsflyer-id h_01H9Q8KBYG8ASB1WB9X4XM3CYZ=time-stamping-s2s-events h_01H9Q8KBYG63SZWNM4GWSJG605=sending-negative-revenue h_01JWV0HR3P78NFBHWY1KM97M98=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 increasing-the-volume-of-data-transactions=%E6%8F%90%E9%AB%98%E6%95%B0%E6%8D%AE%E4%BA%8B%E5%8A%A1%E5%A4%84%E7%90%86%E9%87%8F h_01HX77GDZ1CCWN48CN616P860D=%E6%8F%90%E9%AB%98%E6%95%B0%E6%8D%AE%E4%BA%8B%E5%8A%A1%E5%A4%84%E7%90%86%E9%87%8F troubleshooting=%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5 h_01H9Q8KBYGYR9Y7DPCNWSB4QY0=%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5 h_01H9Q8KBYGYHCWAPPNMG9WB8QN=events-arent-displaying-in-the-dashboard h_01H9Q8KBYGDC68637RH4DE2FZX=events-dont-contain-revenue h_01H9Q8KBYGDQKZF90EJAXRTMF3=not-all-fields-are-populated-in-s2s-events h_01JWV0CS5BFBXDT333794BHFER=S2S_in-app_events_are_wrongly_attributed_as_organic" />
