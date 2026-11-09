---
title: '[Beta]基于用户的跨平台再互动归因'
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2026-04-05T12:40:10Z'
  edited_at: '2026-10-14T10:00:47Z'
  id: 45444294953361
  locale: zh-cn
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/zh-cn/articles/45444294953361
---
> 概览：了解跨平台再互动归因如何衡量用户回流。查看哪些媒体渠道在不同平台上重新激活了现有用户，并获得相应归因。

<div id="about-cross-platform-re-engagement-attribution" />

## 关于跨平台再互动归因

跨平台再互动归因扩展了<Anchor target="_blank" href="/marketers/zh/docs/beta-user-based-cross-platform-attribution">基于用户的跨平台归因模型</Anchor>。除原始获客渠道外，还会根据用户最近一次广告互动，衡量相应用户群体的后续表现。

在跨平台获客归因中，用户的所有活跃数据都会归因到促成首次转化的原始媒体渠道。AppsFlyer会通过持久性Customer User ID(CUID)，关联该用户在不同设备和平台上的事件。这样，无论用户旅程发生在哪个触点，您都可以获得每位用户的统一视图。

跨平台再互动归因是此模型基础上的进一步延伸。不同于始终归因到原始获客渠道，跨平台再互动归因会识别在用户一段时间未活跃后，促使其重新使用产品的媒体渠道，并将归因分配给这些渠道。这样，您就能衡量广告系列对整个产品线的真实影响，而不仅限于某个设备或平台。

以下是两种模型的对应关系：

|  | 跨平台获客归因 | 跨平台再互动归因 |
| --- | --- | --- |
| **衡量内容** | 首次转化及其后的所有活跃数据 | 对休眠用户的重新激活 |
| **归因到** | 原始获客渠道 | 再互动媒体渠道（例如Meta） |
| **范围** | 休眠恢复窗口期 | 仅再互动窗口期内的事件 |
| **设置** | 在产品线层级配置 | 选择启用，并在产品线层级的获客设置基础上完成配置。 |

再互动归因可与用户获取归因同时使用。您可以在同一个报表视图中同时查看最初获取用户的渠道，以及促使用户回流的渠道。

<div id="how-does-re-engagement-attribution-work" />

## 再互动归因的工作原理

要将某个应用内事件归因到再互动媒体渠道，必须同时满足以下所有条件：

* **已启用跨平台再互动功能：** 必须在AppsFlyer设置中为相应产品线启用再互动归因。
* **存在CUID：** 该事件必须包含有效的Customer User ID(CUID)，且该CUID此前已在同一产品线中出现过。AppsFlyer会据此判断该用户是回流用户，而非新用户。
* 再营销不活跃窗口期已结束：自该CUID上次出现后，该CUID必须在再互动不活跃窗口期内未再次出现。如果事件发生在该窗口期内，则不计为再互动，而是归因到原始获客渠道。
* 事件发生在再互动窗口期内：检测到符合条件的再互动后，系统会从该时间点开始计算再互动窗口期。只有在该窗口期内发生的应用内事件，才会归因到再互动媒体渠道。窗口期结束后发生的事件，将归因到原始获客渠道。

<div id="cross-platform-re-engagement-user-journey-example" />

## 跨平台再互动用户旅程示例

以下示例展示了同一用户旅程的两种情况：第一种未启用跨平台再互动，第二种已选择启用再互动。通过对比这两种情况，可以清楚了解再互动对归因结果的影响。

<div id="user-journey-without-re-engagement" />

<Accordion title="未启用再互动的用户旅程">

假设某个用户的旅程横跨三个平台。用户通过Google广告安装移动应用，随后使用Customer User ID完成注册。之后，同一用户通过Meta广告访问网页端平台，并使用相同的Customer User ID登录。登录后，该用户在移动端完成了两笔购买：$100和$50。

<Image align="center" alt="" src="https://files.readme.io/0cd29d386c9b8b83811aa048174ba38b25a551e060c64409b27b1735bb4051eb-45444733164945.png" />

由于此场景未启用再互动，所有活跃数据都会归因到原始获客渠道Google Ads。$100和$50两笔购买，以及两个平台激活（移动端和网页端），都会归因到Google。尽管Meta广告促成了网页端激活，但在跨平台归因中，Meta不会获得任何归因。

| 媒体渠道 | 归因到的转化总数 | 用户获取 | 再互动 | 平台激活 | 移动端 | 网页 | LTV |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Google | 1 | 1 | 0 | 2 | 1 | 1 | $150 |
| Meta | 0 | 0 | 0 | 0 | 0 | 0 | $ 0 |

</Accordion>

<div id="user-journey-with-re-engagement" />

<Accordion title="启用再互动的用户旅程">

该用户旅程与上述示例完全相同。区别在于，该产品线已选择启用再互动。

<Image align="center" alt="" src="https://files.readme.io/9981d9d9ffc20841778f390941f7759d9ff0c3e630e14e4578dc001c9d692cbf-45444733163409.png" />

在这种情况下，系统会根据再营销不活跃窗口期判定，用户通过Meta广告完成的网页端登录，是否符合再互动事件的条件。该窗口期从上一次识别到Customer User ID时（用户在移动端注册时）开始计算。如果用户在网页端登录前已经过足够长的时间，也就是说，该登录发生在再互动不活跃窗口期之外，则Meta会获得再互动归因。

Meta获得再互动归因后，系统开始计算再互动窗口期。在该窗口期内发生的任何应用内事件，都会归因到Meta。在此示例中，$100购买发生在再互动窗口期内，因此归因到Meta。$50购买发生在再互动窗口期之外，因此会重新归因到Google。

| 媒体渠道 | 归因到的转化总数 | 用户获取 | 再互动 | 平台激活 | 移动端 | 网页 | LTV |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Google | 1 | 1 | 0 | 1 | 1 | 0 | $50 |
| Meta | 1 | 0 | 1 | 1 | 0 | 1 | $100 |

</Accordion>

<div id="set-up-cross-platform-re-engagement-attribution" />

## 设置跨平台再互动归因

要设置跨平台再互动归因，您需要先完成产品线设置，然后在AppsFlyer中应用几项与再互动相关的专用设置。更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/product-line-group-apps-for-cross-platform-attribution#如何创建产品线">如何创建产品线</Anchor>。

<div id="view-cross-platform-attribution-results" />

## 查看跨平台归因结果

<div id="see-also" />

> 📄 **另请参阅**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/end-user-events-cross-platform-report-in-data-locker">Data Locker终端用户事件跨平台报告</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/my-dashboards#crossplatform-dashboard">跨平台面板</Anchor>

<div data-zendesk-anchors="about-cross-platform-re-engagement-attribution=%E5%85%B3%E4%BA%8E%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%86%8D%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0 h_01KNEVA6TAJZRZYS11Z0Q59AQJ=%E5%85%B3%E4%BA%8E%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%86%8D%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0 how-does-re-engagement-attribution-work=%E5%86%8D%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0%E7%9A%84%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86 h_01KNEVA6TASWZ0S6HH5QT0ZZF0=%E5%86%8D%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0%E7%9A%84%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86 a-cross-platform-re-engagement-user-journey-example=%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%86%8D%E4%BA%92%E5%8A%A8%E7%94%A8%E6%88%B7%E6%97%85%E7%A8%8B%E7%A4%BA%E4%BE%8B h_01KNEVA6TA5PVF5E8YWFE13QAQ=%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%86%8D%E4%BA%92%E5%8A%A8%E7%94%A8%E6%88%B7%E6%97%85%E7%A8%8B%E7%A4%BA%E4%BE%8B h_01KNEVA6TAPFZ48SHNN1F8Y8P5=user-journey-without-re-engagement h_01KNEVA6TA0ZRG6Z6A38JGEFAQ=user-journey-with-re-engagement set-up-cross-platform-re-engagement-attribution=%E8%AE%BE%E7%BD%AE%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%86%8D%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0 h_01KNEVH8QZ2K59BJX0HZ908FXR=%E8%AE%BE%E7%BD%AE%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%86%8D%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0 view-cross-platform-attribution-results=%E6%9F%A5%E7%9C%8B%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%BD%92%E5%9B%A0%E7%BB%93%E6%9E%9C h_01KNEVH8QZNV046JAF9PRADK4E=%E6%9F%A5%E7%9C%8B%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%BD%92%E5%9B%A0%E7%BB%93%E6%9E%9C h_01KNEVH8QZK4J276D8RPBH15JY=%E5%8F%A6%E8%AF%B7%E5%8F%82%E9%98%85" />
