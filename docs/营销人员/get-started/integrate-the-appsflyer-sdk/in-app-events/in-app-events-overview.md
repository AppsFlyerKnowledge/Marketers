---
title: 应用内事件概览
metadata:
  keywords:
    - ios
    - Rich
    - In-App
    - android
    - Advertisers
    - In app events
    - Marketers
    - inapp events
    - attribution
    - inapp
    - inapp events attribution
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2017-11-02T08:12:51Z'
  edited_at: '2026-10-14T10:07:13Z'
  id: 115005544169
  locale: zh-cn
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/zh-cn/articles/115005544169
---
> **概要：** 记录激活后的应用内事件（如登录、注册或内购），将其归因到媒体渠道和广告活动。

## 为什么要记录应用内事件？

应用内事件能让您深入了解用户动态，帮助您有效识别用户价值以及**来自不同媒体渠道的流量质量**。记录应用内事件有助于您衡量ROI（投资回报率）和LTV（生命周期价值）等各项KPI。

当用户进行注册、完成教程、将商品添加到购物车或购买商品时，应用内事件数据会记录这些事件及其详细信息。如果要分析激活后的用户行为，就必须启用应用内事件。

## 关于应用内事件

创建应用内事件时，您需要填写事件名称，也可以添加事件参数。事件参数能针对正在发生的事件提供更多背景和信息。比如，在用户预订机票后，您不仅能看到这个订票事件，还能通过事件参数了解订单详情，如购买类型、目的地和收入金额等。

![travel.png](https://files.readme.io/0ebe64e7aa3ccc40ef014c55ee3a91edf678e21b2d00a7f8be1298d6b494e925-30858351609617.png)

> 👍 **提示**
>
> 如需进一步了解应用内事件，我们在<Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7774/play/18613/in-app-events-and-integrated-partners-part-1">AppsFlyer充电站里为您准备了相关课程</Anchor>，视频虽短，但干货满满！

### 预定义和自定义事件

您的开发人员需要在应用中的相关位置添加代码后您才能发送对应的应用内事件。事件名称和事件参数分为以下几种：

* **预定义型**：这类事件名称和事件参数是各种应用中最常用的。建议尽量使用<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#预定义事件名称">预定义事件名称</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#预定义事件参数">事件参数</Anchor>，原因如下：
  * 预定义命名允许事件与合作伙伴之间的顺利映射。
  * 如果AppsFlyer决定更改任何事件的名称或参数，您的设置是可以向下兼容的。
* **自定义型：** 这类事件名称和参数是由您自行根据应用中出现的特定用户场景来定义的。您可以使用任何自定义的事件名称或参数名称字符串，但请注意自定义事件是需要您的开发人员去维护的。详情请见相关[建议](/docs/in-app-events-overview#tips)和[限制](/docs/in-app-events-overview#limitations)。

## 应用内事件中的收入

以下几个部分将为您说明如何将收入事件发送至AppsFlyer，以及对事件中包含的参数进行映射。如您订阅了ROI360，您即可获得最精准、最实时的成本与收入数据（包括应用内购买、订阅和广告产生的收入数据）。进一步了解<Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-cost-and-revenue-data">ROI360</Anchor>。

<div id="actual-revenue" />

<Accordion title="事件收入">

`af_revenue` 是报告收入的默认参数。已缴纳的收入`af_revenue`为 AppsFlyer 产品（仪表板、LTV、用户群、ROAS、ROI）提供所有收入指标，并包含在回传给合作伙伴的信息中。请务必根据您的业务逻辑，选择能实际产生收入的应用内事件来使用该参数。

如果您还想按照自己的逻辑报告收入，例如，扣除应用商店费用和税款后，您可以额外发送`af_net_revenue`。这是对……的补充`af_revenue`并非替代品。请参见下方的[净收入](#h_NETREVENUE0001)。

* <Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#record-revenue">通过SDK记录收入</Anchor>
* 通过Unity记录收入

您可以通过记录负收入来监测取消订单或发出退款等事件。只需在传递到`af_revenue`af\_revenueaf\_revenue的收入值前面加上负号（-）即可记录负收入。

**af\_revenue**也可以出现负值，用来记录取消交易或退款等事件。

收入值中仅可包含数字（必要时可以使用小数点）：

* **切勿**在收入值中使用任何其他符号或格式，也就是说不能使用逗号、货币符号（如$）、特殊字符或文字。
* AppsFlyer 提供的收入值**精确到小数点后 5 位**。
* 该参数值的范围应介于-10,000到+10,000（美元或实际使用货币的等价金额）之间。在这个区间之外的值会出现在原始数据报告中，但汇总报告中不包含这类值。
* 示例：1234.56
* 以字符串的形式发送收入数据时，必须确保引号内的值是有效的。比如："1234.56"。

**请注意**：

* AppsFlyer后台会按原样展示SDK上报的收入数据，其中对VAT或应用商店抽成等不做任何计算。如需对SDK上报的收入作相应调整，SDK侧开发人员需要在上报收入前写入相关运算。如果您想申报扣除上述款项后的收入，请另行提交。`af_net_revenue` （参见[净收入](/docs/in-app-events-overview#h_NETREVENUE0001)）。

**af\_currency** 表示用于显示 af\_revenue（或 af\_price）的货币。如果事件参数缺少  af\_currency，AppsFlyer 将以默认值“美元”发送。

您可使用 **af\_price 作为不计为收入的货币参数**（例如“添加到购物车”事件）。 该参数意指单个商品价格。所有购买的总金额用 af\_revenue 参数表示。

</Accordion>

<div id="h_NETREVENUE0001" />

<Accordion title="净收入">

这`af_net_revenue`当您想要对收入金额应用自己的逻辑时，参数提供了一种可选的、额外的收入报告方式，例如，扣除应用商店费用、税收减免、毛利率或服务费后的收入。

<strong>af\_net\_revenue 不会取代 af\_revenue。</strong>请继续发送`af_revenue`照常添加`af_net_revenue`当您需要净报告时，可以将其与它一起使用。

* 货币遵循`af_currency`（默认美元），类似于`af_revenue`。
* 由于没有预定义的 SDK 常量`af_net_revenue`您必须将其作为自定义参数发送，并带有密钥。`af_net_revenue` 。
* 净收入为<Anchor target="_blank" href="/marketers/zh/docs/my-dashboards#metrics">“我的仪表盘”</Anchor>中的净指标（净收入、净投资回报率、净广告支出回报率、净每用户平均收入和净毛利润）提供支持。

> 📘 **注意**
>
> 如果您使用<Anchor target="_blank" href="/marketers/zh/docs/about-roi360-store-revenue">ROI360 商店收入</Anchor>`af_net_revenue`应用内购买和订阅事件会自动填充这些信息，因此您无需发送。`af_net_revenue`针对这些赛事。净收入等于总收入减去应用商店费用和税款。

</Accordion>

<div id="revenue-currency" />

<Accordion title="收入数据的货币单位">

AppsFlyer处理货币设置和货币换算的方式是非常重要的知识点，建议您了解相关内容。

AppsFlyer会通过货币换算来调和应用配置中的指定货币与应用内事件货币之间的差异。

![revenue_normalization_flow.png](https://files.readme.io/f890d34168f92202c94da4bfa548bd0f471c98dec9c8d4282b2549f5878e9321-46334674326033.png)

上图说明了货币换算的大致流程，具体内容如下：

1. SDK发送应用内事件 — 每个事件的货币各不相同
2. AppsFlyer将所有货币统一换算到美元
3. AppsFlyer处理收入数据
4. 面板会按应用配置中的指定货币显示收入数据
5. AppsFlyer会在原始数据报告中同时用事件货币和应用配置中的指定货币来填充收入数据。

AppsFlyer使用<Anchor target="_blank" href="https://openexchangerates.org/">Open Exchange Rates</Anchor>进行货币换算，其中的汇率每小时更新一次。AppsFlyer总是使用最近一小时内更新的汇率进行货币换算。

#### 货币换算

> 📄 **示例**
>
> 您在应用配置中将货币设置为GBP（英镑）。某用户在法国使用您的应用购买了一件商品，该商品的价格以欧元（€）计算。这个应用内事件会以以下形式发送到AppsFlyer：
>
> ```java
> Map<String, Object> eventValue = new HashMap<String, Object>();
> eventValue.put(AFInAppEventParameterName.REVENUE,200);
> eventValue.put(AFInAppEventParameterName.CONTENT_TYPE,"category_a");
> eventValue.put(AFInAppEventParameterName.CONTENT_ID,"1234567");
> eventValue.put(AFInAppEventParameterName.CURRENCY,"EUR");
> AppsFlyerLib.getInstance().trackEvent(getApplicationContext() , AFInAppEventType.PURCHASE , eventValue);
> ```
>
> 这里AppsFlyer先将收入从欧元换算到美元，然后再换算到英镑。假设这时的汇率为€1 = $1.13，那么€200就是$226.85。接下来，AppsFlyer再将收入从美元换算到英镑。假设这时的汇率为$1 = £0.78，那么$226.85就是£176.92。

#### 货币显示

<Anchor target="_blank" href="/marketers/zh/docs/app-settings#localization-currency">货币单位是在应用配置中设置的</Anchor>。您在应用配置中设置的货币单位就是面板数据的货币单位。无论您的应用内事件是以什么货币发送的，面板总是会按您在应用配置中设置的货币来显示收入数据。

> 📄 **示例**
>
> 假设您在应用配置中指定以**GBP**（英镑）为货币单位，而您发送的应用内事件中有的不以GBP为货币单位，有的直接不含货币信息。
>
> 您向AppsFlyer发送了以下三个应用内事件：
>
> 1. 事件A的收入为**234**，货币为**GBP**
> 2. 事件B的收入为**171**，货币为**EUR**（欧元）
> 3. 事件C的收入为**171**，且**没有货币**信息
>
> #### 面板中的收入数据
>
> AF会先将应用内事件的货币换算到美元，再换算到应用配置中的指定货币，然后在面板中呈现这个**换算值**。
>
> 如果事件中没有货币信息，**AppsFlyer会默认使用美元为单位**记录数据。面板显示的事件和收入信息如下：
>
>
>
> | 应用内事件 | 独立用户数 | 事件发生次数 | 收入 |
> | --- | --- | --- | --- |
> | A | 1 | 1 | £234 |
> | B | 1 | 1 | £149.4 - 先从EUR换算到USD，再从USD换算到GBP。 |
> | C | 1 | 1 | £132.9 - 因为没有货币信息，因此使用默认货币USD，并直接从USD换算到GBP。 |
>
>
>
> #### 原始数据报告中的收入数据
>
> 如果您在应用配置中将货币设置为**GBP**，但您发送的应用内事件中使用的货币不是GBP，则原始数据报告中会同时显示以GBP为单位的收入以及以应用内事件原始货币为单位的收入。
>
> 如果您在应用配置中将货币设置为**GBP**，但您发送的应用内事件中不包含货币信息，则原始数据报告中会同时显示以GBP和USD为单位的收入数据。
>
> 应用内事件原始数据报告中显示的事件和收入信息如下：
>
>
>
> | 事件 | 事件收入 | 事件收入货币 | 以GBP为单位的事件收入 |
> | --- | --- | --- | --- |
> | A | 234 | GBP | 234 |
> | B | 171 | EUR | 149.4 - 先从EUR换算到USD，再从USD换算到GBP。 |
> | C | 171 | USD | 132.9 - 因为没有货币信息，因此使用默认货币USD，并直接从USD换算到GBP。 |

</Accordion>

## 发送事件

您可通过多种方式将应用内事件发送给AppsFlyer：

* <Anchor target="_blank" href="/marketers/zh/docs/sdk-integration-overview">**AppsFlyer SDK**</Anchor>：这是最常用的事件发送方式。您可以在SDK级别使用AppsFlyer应用内事件API发送应用内事件，以记录用户在应用中的行为。
* <Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile">**服务器到服务器（S2S）API**</Anchor>：使用S2S API可以直接向AppsFlyer发送在移动应用以外发生的事件。例如，如果您有用户同时活跃于Web端和移动端，您可以通过这类API同时记录来自这两个端的事件，并在AppsFlyer中将这些事件匹配到同一个用户。它可以是应用内事件，也可以是其他事件，例如：网站事件、呼叫中心事件或实体店购买事件。
* <Anchor target="_blank" href="/marketers/zh/docs/purchase-and-subscription-validation-overview">**收据验证**</Anchor>：苹果和谷歌等支付平台可以通过这个安全的机制来验证报告中所呈现的应用内购事件是否真实发生。验证购买是防止内购刷单的主要手段。您还可以通过该机制查看真实的收入数据，并筛除未完成的应用内购买。
* <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-for-hybrid-apps">**混合应用**</Anchor>：这类应用结合了原生视图和HTML内容，同时也可以记录应用内事件。但由于SDK只能从原生侧发送事件，因此开发人员需要将所有事件数据转发到原生代码。

## 设置应用内事件

应用内事件的设置流程需要市场人员和开发人员的共同参与，具体方法如下：

| 步骤 | 角色 | 事项 | 说明 |
| --- | --- | --- | --- |
| 1 | 投放运营人员 | 确定您想要衡量的应用内事件。[定义](/docs/in-app-events-overview#defining-an-inapp-event)<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#预定义事件名称">事件名称</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#预定义事件参数">事件参数</Anchor>，并将这些信息同步给您的开发人员。 | 建议先设置3-5个事件作为KPI来衡量用户的质量（如购买、注册、分享）。事件参数不是必须设置的项目，您可以为任一事件名称设置任何事件参数。<br /><br />常见的应用内事件请参考[针对各垂类的推荐事件](/docs/in-app-events-overview#recommended-events-by-business-vertical)。 |
| 2 | 开发人员 | 在应用中的相关位置添加代码。 | 详情请见<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk">开发者文档</Anchor>。 |
| 3【可选】 | 投放运营人员 | 与开发人员合作设置<Anchor target="_blank" href="/marketers/zh/docs/customer-user-id-field-cuid">客户用户ID字段（CUID）</Anchor>。 | 该字段以CUID为密匙，将AppsFlyer归因数据与其他数据进行对照，从而使应用内事件数据更丰富。 |
| 4【可选】 | 投放运营人员 | 在面板中将<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#事件映射">事件映射</Anchor>到相关渠道。 | 这是一项长期持续的工作，具体取决于与您对接的渠道。 |

<div id="defining-an-inapp-event" />

<Accordion title="定义应用内事件">

确定了要衡量的应用内事件后，请使用<Anchor target="_blank" href="https://evgen.appsflyer.com/">应用内事件生成器</Anchor>按以下方式对事件和参数进行定义：

1. 基于您想要记录的场景，选择最合适的事件名称。
2. 考虑一下哪些参数能为该事件提供更多背景、使数据更丰富，请根据您的业务需求选择合适的参数，从而掌握更多的上下文信息并扩充相关数据。
3. 应用内事件生成器会根据您的设置生成相应代码并打包成压缩文件，请在生成器页面下载该文件并发送给您的开发人员。

> 📄 **示例**
>
> 一个电商应用的市场人员想要记录用户浏览的内容类型，以更好地了解哪些品类最受欢迎，并查看商品浏览量与商品销量之间的关系。
>
> 下表为该市场人员发送给开发人员的事件结构范例：
>
>
>
> <table><thead><tr><th>Event name</th><th>事件参数</th><th>参数值：</th><th>事件何时被触发？</th></tr></thead><tbody><tr><td rowspan="3">af_content_view</td><td>af_price</td><td>产品价格</td><td rowspan="3"><span>当用户浏览特定的商品详情页时</span></td></tr><tr><td><span>af_content_type</span></td><td><span>商品品类名称，如鞋类</span></td></tr><tr><td><span>af_content_id</span></td><td><span>商品ID，如SKU</span></td></tr></tbody></table>

</Accordion>

<div id="recommended-events-by-business-vertical" />

<Accordion title="针对各垂类的推荐事件">

下表所列的文章是我们针对各垂类推荐的常见应用内事件，其中包含实例和流程。

| 业务垂类 | 文章标题 |
| --- | --- |
| <Image alt="InApp_Events_games.png" src="https://files.readme.io/ee2d46ddf11a6a6cacc95399ffd778d6613ecdd905d237cd971073e095cada5b-20659444711953.png" width="38px" /> | <Anchor target="_blank" href="/marketers/zh/docs/recommended-gaming-app-events">游戏类应用事件推荐</Anchor> |
| <Image alt="InApp_Events_ecommerce.png" src="https://files.readme.io/c6497d250c22c7de5c13f01278ac72d8b3117bc60712ba3fe40ad24efcdc4947-360019350097.png" width="37px" /> | <Anchor target="_blank" href="/marketers/zh/docs/recommended-ecommerce-app-events">电商类应用内事件推荐</Anchor> |
| <Image alt="InApp_Events_streaming.png" src="https://files.readme.io/27f2f38b0ce7d242580c60edeff730079a3801f98ff0d7cb8a605380ed11071f-20659453813905.png" width="39px" /> | <Anchor target="_blank" href="/marketers/zh/docs/recommended-entertainment-app-events">娱乐类应用事件推荐</Anchor> |
| <Image alt="banking.png" src="https://files.readme.io/260638f807a43f42c6ff99bb72b8d4113b2df09436b9322a820888ad3f8a01ae-20659476893969.png" width="36px" /> | <Anchor target="_blank" href="/marketers/zh/docs/recommended-finance-and-banking-app-events">金融银行类应用内事件推荐</Anchor> |
| <Image alt="InApp_Events_lending.png" src="https://files.readme.io/e3465ee913a65a215f1c224db20d4f1fd61fd0bf488b798073c94b4e8387d252-20659507679889.png" width="36px" /> | <Anchor target="_blank" href="/marketers/zh/docs/recommended-p2p-lending-app-events">P2P贷款类应用事件推荐</Anchor> |
| <Image alt="education.png" src="https://files.readme.io/fb036c8f3b0cb4cc06a5284c26089bbb361273ab628bc5b740692bc49e7a2c40-20659493109393.png" width="37px" /> | <Anchor target="_blank" href="/marketers/zh/docs/recommended-online-education-app-events">在线教育类应用内事件推荐</Anchor> |
| <Image alt="InApp_Events_ride.png" src="https://files.readme.io/3901cfcc0cc821cc9c93edbe806bc2d570698be366b76b3710cb60e9aa190d91-20659532208401.png" width="37px" /> | <Anchor target="_blank" href="/marketers/zh/docs/recommended-ride-hailing-app-events">打车类应用事件推荐</Anchor> |
| <Image alt="InApp_Events_flight.png" src="https://files.readme.io/7a09c4a641dd5e797bffc41a6e66b20efe5660721f37abac3dd12ac83688b37b-20659533911697.png" width="38px" /> | <Anchor target="_blank" href="/marketers/zh/docs/recommended-flight-booking-app-events">机票预订类应用内事件推荐</Anchor> |
| <Image alt="InApp_Events_hotel.png" src="https://files.readme.io/ffc23cc65b6b6cfe99c12e988cca3df6667058b7e3a672db3639472a17602546-20659548553745.png" width="37px" /> | <Anchor target="_blank" href="/marketers/zh/docs/recommended-hotel-booking-app-events">酒店预订类应用事件推荐</Anchor> |
| <Image alt="5669_Healthcare_icon_3.png" src="https://files.readme.io/bb4bb46d842d1f2d08da548724e7d69910b0a050302fcdbd1500a8ebef325516-20659200427281.png" width="37px" /> | <Anchor target="_blank" href="/marketers/zh/docs/recommended-healthcare-app-events">医疗保健类应用事件推荐</Anchor> |
| <Image alt="telecommunications_icon.png" src="https://files.readme.io/42f1aac3b825957d9d0584d83480c441b9d53665cc6cf1a6b8cd1803bb9b6121-20659194885393.png" width="39px" /> | <Anchor target="_blank" href="/marketers/zh/docs/recommended-telecommunication-app-events">电信类应用事件推荐</Anchor> |
| <Image alt="InApp_Events_eWallet.png" src="https://files.readme.io/4d2ed4994bbe8e8eca7009b8ec8f5dbf22a626421a7a1efb213ddb4a12c7b487-4402543191825.png" width="39px" /> | <Anchor target="_blank" href="/marketers/zh/docs/recommended-ewallet-app-events">电子钱包类应用的事件记录推荐</Anchor> |
| <Image alt="soccer_ball.png" src="https://files.readme.io/2c5150b2c50ec166878cd976154dc81c0dc8a1e710fa8869aa582b535313b464-4413968925585.png" width="39px" /> | <Anchor target="_blank" href="/marketers/zh/docs/recommended-sports-betting-events">体育博彩类应用内事件推荐</Anchor> |

</Accordion>

<div id="view-inapp-event-data" />

<Accordion title="查看应用内事件数据">

用户从某个媒体渠道安装应用后，该用户整个生命周期内发生的应用内事件都会归因到这个渠道。事件数据以<Anchor target="_blank" href="/marketers/zh/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">用户生命周期价值或行为数据</Anchor>的形式呈现。

您可在下列板块中查看应用内事件数据：

* 总览面板：实时显示LTV维度的UA效果数据。**请注意**：这些数据包括通过应用内事件上报的自然量和非自然量收入，以及经过<Anchor target="_blank" href="/marketers/zh/docs/resolve-retargeting-double-attribution">双重归因</Anchor>的再营销收入。
* 事件面板：显示不同媒体渠道的LTV应用内事件效果。
* <Anchor target="_blank" href="/marketers/zh/docs/activity-dashboard">活跃数据面板</Anchor>：显示选定时间段内的应用内用户行为数据。
* <Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">原始数据应用内事件报告</Anchor>： 呈现用户行为数据及其含义，按时间顺序罗列所有用户完成的行为。该报告包含事件参数值，如：

  ```json
  {
    "af_level":"10",
    "af_score":"3387",
    "arena":"7",
    "char_type":"paladin"
  }
  ```

  请注意，原始数据报告是高阶功能。

> 📘 **注意**
>
> 应用内事件的参数值仅可在<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview#应用内事件">原始数据的应用内事件报告</Anchor>中查看。它们不会显示在概览、事件或活动面板中，也不会出现在汇总数据报表中。

</Accordion>

<div id="tips" />

<Accordion title="提示">

设置应用内事件名称和参数时请注意以下几点：

* 为确保原始数据报告中的数据一致性，我们建议在各平台上使用相同的应用内事件名称和结构，并对其做出相同的定义。
* 在对比不同渠道的用户质量时，建议您有针对性地选取事件，尽量缩减事件数量，以简化分析工作。
* **为了保护用户的隐私安全，请确保事件值中不包含能直接识别用户身份的信息，如电子邮箱、姓名、身份证件号码等，某些地区把邮编也作为身份识别信息。如需进一步了解受限数据，请参考**<Anchor target="_blank" href="https://www.appsflyer.com/legal/services-privacy-policy/">**服务隐私政策**</Anchor>。
* 请注意，AppsFlyer会在用户<Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy/#engagementinformation">互动</Anchor>期间收集设备的IP地址。在某些地区或使用场景中，IP地址也被视为个人身份识别信息（PII）。我们仅使用IP地址来获取粗粒度的地理位置信息（城市、行政区划层级），而非详细地址。如有需要，您可选择<Anchor target="_blank" href="/marketers/zh/docs/apply-ip-masking-to-user-data">掩盖IP地址</Anchor>，不让这些信息出现在原始数据报告中。
* 应用内事件是AppsFlyer中收入数据的唯一来源。您可以将特定收入值附加到每个事件中, 并在应用的主面板上查看。详情请参考[变现参数](/docs/in-app-events-overview#revenue-events)。![revenue_data.png](https://files.readme.io/9ada01568583ef5eb7d39ca09b2ae9dd68afb9415859574f35c477cf46d6272c-46334666577425.png)

</Accordion>

<div id="limitations" />

<Accordion title="局限性">

设置应用内事件名称和参数时请注意以下几点：

* 建议仅使用小写字母和数字（a-z 和0-9）来命名您的应用内事件。事件名称区分大小写，也就是说af\_purchase和af\_PURCHASE在原始数据中是两个不同的事件，但在汇总报表和面板中（例如“概览”或“事件”面板），事件名称仅支持小写字母，因此这些事件会被视为同一个事件并合并显示。
* 每天最多可用300个不同的事件。<Anchor target="_blank" href="/marketers/zh/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_events_limit">详情请见此处说明。</Anchor>
* 用户激活应用后完成的前100个事件有独立用户数指标，之后的事件不再统计该指标。
* 事件名称不能以下列字符开头：" = + -
* 事件值中不能带有+号，但可在URL中以编码替换，或按<Anchor target="_blank" href="https://www.w3schools.com/tags/ref_urlencode.ASP">ASCII</Anchor>进行编码。
* 事件名称中不能有空格，可以使用下划线代替。
* 事件值不能超过2000个字符，否则原始数据报告可能会缩短过长的事件值。对于SDK发出的事件，建议将事件值控制在1000个字符以下，这是为了确保通过HTTP请求发送这些数据时，有效信息（payload）不被截断。
* 如果事件值中包含链接，该链接必须经过<Anchor target="_blank" href="https://www.w3schools.com/tags/ref_urlencode.ASP">URL编码</Anchor>。
* Meta ads对于事件名称和参数设有限制。<Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/faq#limits">点击此处</Anchor>查看限制详情。

</Accordion>

## 常见问题解答

本章解答了关于应用内事件的常见问题。

<div id="how-do-i-use-the-revenue-parameter" />

<Accordion title="如何使用收入参数？">

您可以使用任何参数名称和事件发送收入值。但如果要在AppsFlyer的原始和聚合数据中记录收入（包括[负收入](/docs/in-app-events-overview#revenue-events)），必须使用***af\_revenue***参数。请务必根据您的业务逻辑，选择能实际产生收入的应用内事件来使用该参数。

**af\_currency**代表**af\_revenue**（或**af\_price**）中所呈现金额的货币单位。如果事件中没有配置**af\_currency**参数，AppsFlyer会以默认值“USD”（美元）为单位发送数据。关于***af\_revenue***参数的详细信息，请参见[收入归因指南](/docs/in-app-events-overview#revenue-events)。

如果您还想应用自己的逻辑来报告收入（例如，扣除费用和税款后），请发送`af_net_revenue`作为自定义参数`af_revenue`。`af_net_revenue`不取代`af_revenue`。有关更多信息，请参阅[净收入](#h_NETREVENUE0001)。

</Accordion>

<div id="how-does-appsflyer-attribute-events" />

<Accordion title="AppsFlyer是如何对事件进行归因的？">

AppsFlyer会将应用内事件归因到最初带来应用激活的那个媒体渠道。

用户激活应用（即首次打开应用）时，AppsFlyer会通过各种<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#归因方法">归因方式</Anchor>判断这次激活的归因结果。同时，AppsFlyer的SDK会生成一个全新的<Anchor target="_blank" href="/marketers/zh/docs/about-device-identifiers#appsflyer-id">AppsFlyer ID</Anchor>，并关联到归因信息。

之后用户在同一个设备上完成的每一个应用内事件都会带有这个ID。这样，AppsFlyer就可以通过该ID将这些事件归因到最初带来用户的渠道，而广告主则可以使用该ID来追溯用户在其应用中的完整链路。

由新近再营销广告促成的事件可能会受到<Anchor target="_blank" href="/marketers/zh/docs/resolve-retargeting-double-attribution">双重归因</Anchor>。

出现以下情况时，AppsFlyer会将用户在非自然激活后完成的事件计为**自然量**：

* 媒体渠道规定[必须删除用户层级数据](/docs/in-app-events-overview#how-long-does-appsflyer-retain-userlevel-data-and-what-are-the-deletion-obligations)。
* 用户删除了应用在其设备上存储的数据，迫使SDK生成新的AppsFlyer ID。

</Accordion>

<div id="are-events-recorded-if-a-device-is-offline" />

<Accordion title="能否记录离线设备上的事件？">

如果用户在网络连接不可用时启动事件，Appsflyer仍然可以记录该事件。它是这样工作的：

1. SDK向AppsFlyer服务器发送事件后，会等待服务器回复一个发送成功的信息。
2. 如果SDK没有接收到这个信息，那么事件就会被保存到缓存中。
3. 而一旦收到了发送成功的回复，缓存中的事件就会被再次发送到服务器。
4. 如果缓存中有多个事件，这些事件会依次被发送到服务器。

> 📘 **注意**
>
> SDK缓存最多可存储40个事件，这意味着只有离线时发生的最初40个事件会被保存。在这之后发生的所有事件都会被删除，直到下一次发送成功为止。
>
> 原始数据中显示的事件时间是设备再次联机后事件发送到AppsFlyer的时间，而不是事件实际发生的时间。

</Accordion>

<div id="what-are-complex-inapp-events-and-how-do-i-set-them-up" />

<Accordion title="复杂应用内事件的含义和设置方法">

复杂的应用内事件允许您在单个API调用中发送多个项目。当您想要将几个密切相关的用户操作组合在一起时，它们非常有用，例如在一次会话中将多个产品添加到购物车。

要构建复杂的应用内事件，请将 `af_content` 用作JSON数组。数组中的每个对象都必须包含 `id` 和 `quantity`。`af_content_list` 是可选的，可以省略。

> 📄 **示例**
>
> ```json
> {
>   "af_revenue": 4.99,
>   "af_currency": "USD",
>   "af_order_id": "12345",
>   "af_content": "[{"id":"ID1","quantity":"1"},{"id":"ID2","quantity":"1"},{"id":"ID3","quantity":"2"}]"
> }
> ```

> 🚧 **重要提示！**
>
> 如果 `af_content` 字符串超过1,000个字符，AppsFlyer可能会在没有 `fb_content` 参数的情况下将事件发送给Meta。在这种情况下，如果 `af_content_list` 也缺失，Meta将不会收到任何产品标识数据。对于包含许多项目的事件，请将 `af_content` 保持在1,000个字符以内。

有关向Meta发送复杂应用内事件的完整详细信息，请参阅 <Anchor target="_blank" href="/marketers/zh/docs/meta-ads-in-app-event-mapping#send-complex-in-app-events-to-meta-ads">Send complex in-app events to Meta ads</Anchor>。

**请注意：** 在 AppsFlyer <Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#limitations">Audiences</Anchor> 中，事件属性内不支持数组，仅支持数字或字符串。

</Accordion>

<div id="can-i-add-multiple-items-to-a-single-transaction" />

<Accordion title="能否在单笔交易中添加多件商品？">

您可以在单笔交易中添加多个商品。您可以用多件商品的数组来描述一笔交易，商品之间用逗号区隔开，不需要针对每件商品分开填写参数值。格式是JSON字符串。

> 📄 **示例**
>
> Smith先生在一家美国线上商店下单，在这一单中他分别购买了两件相同的衬衫、一双鞋和一个帽子。每件商品的罗列次序必须与各参数完全一致。
>
> ```json
> "{"af_content_id": ["123","988","399"], "af_quantity": ["2","1","1"], "af_price": ["25","50","10"], "af_revenue": "110", "af_currency": "USD"}"
> ```
>
> 多商品事件一般会以数组的形式<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration">回传</Anchor>。目前，Meta ads和X Ads都无法正确解析数组。为协助解决这个问题，AppsFlyer不再把多件商品以数组形式发送给SRN，而是对商品数量（af\_quantity）进行加总。在上述案例中，Meta ads就会收到**af\_quantity=4**。
>
> **<span id="h_01HDBZW9XFJ68WSM3066NVRATS"></span>注意**
>
> * 在 AppsFlyer <Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#limitations">Audiences</Anchor> 中，事件属性内不支持数组，仅支持数字或字符串。
> * 您可以在以下应用内事件中使用多商品描述：
>   af\_add\_to\_cart, af\_add\_to\_wishlist, af\_tutorial\_completion, af\_initiated\_checkout, af\_purchase, af\_rate, af\_spent\_credits, af\_content\_view, af\_travel\_booking, af\_update



</Accordion>

<div id="how-does-appsflyer-handle-event-deduplication" />

<Accordion title="AppsFlyer如何进行事件去重？">

我们会通过应用内事件去重机制它会检查所有应用内事件，以查看同一个 appsflyer\_id 是否10秒内有同一个应用内事件。如果找到此类事件, 该机制将删除重复项。

如果两个事件中的以下字段相同, 系统将视其为同一个事件:

* Event name
* Event value
* 应用ID
* AppsFlyer ID

> 📘 **注意**
>
> 去重机制仅适用于从SDK发送的应用内事件。
>
> 服务器对服务器的应用内事件不会去重。

</Accordion>

<div id="how-long-does-appsflyer-retain-userlevel-data-and-what-are-the-deletion-obligations" />

<Accordion title="AppsFlyer对用户层级数据会保留多久？负有什么删除义务？">

AppsFlyer会根据对接类型和合作渠道的要求保留原始的用户级数据。汇总数据最长可保留5年。

数据保留期限可能因媒体渠道和数据传输方式（例如Data Locker或Pull API）而异，并可能因法律、合同或合作渠道义务而发生变化。

数据一经删除，与被删除的用户有关的事件就会显示为自然流量事件，但之前的汇总数据保持不变。请参阅<Anchor target="_blank" href="/marketers/zh/docs/user-level-data-retention#数据保留与删除义务">数据保留与删除义务</Anchor>了解详情。

</Accordion>

<div id="do-i-need-to-add-the-os-operating-system-parameter-to-my-events" />

<Accordion title="是否需要在事件中添加OS（操作系统）参数？">

* 安卓SDK和iOS SDK会自动添加OS（操作系统）参数。
* 对于<Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S API</Anchor>，自2021年7月1日起，iOS应用必须发送OS（操作系统）参数。如果您不发送这个参数，那么系统就会默认数据来自iOS 14.5的用户，这会影响<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">原始数据的呈现方式</Anchor>。

</Accordion>

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration">应用内事件回传配置</Anchor>

<div data-zendesk-anchors="why-record-inapp-events=%E4%B8%BA%E4%BB%80%E4%B9%88%E8%A6%81%E8%AE%B0%E5%BD%95%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 h_01HDBZW9XEBTY13MG4AN93RNCD=%E4%B8%BA%E4%BB%80%E4%B9%88%E8%A6%81%E8%AE%B0%E5%BD%95%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 about-inapp-events=%E5%85%B3%E4%BA%8E%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 h_01HDBZW9XEBDSDA9T5X5B6KGTG=%E5%85%B3%E4%BA%8E%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 h_01HDBZW9XE3Z40JE9576C4XSF4=%E6%8F%90%E7%A4%BA predefind-and-custom-events=%E9%A2%84%E5%AE%9A%E4%B9%89%E5%92%8C%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6 01J9XGXGC7R9B19MMX4CQV7DAY=%E9%A2%84%E5%AE%9A%E4%B9%89%E5%92%8C%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6 revenue-in-inapp-events=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E4%B8%AD%E7%9A%84%E6%94%B6%E5%85%A5 01J9XGXGC990R3AG0R0XT9E5Y7=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E4%B8%AD%E7%9A%84%E6%94%B6%E5%85%A5 h_01HDBZW9XEZWDDHFATKY6KDN25=actual-revenue net-revenue=h_NETREVENUE0001 h_NETREVENUE0002=%E6%B3%A8%E6%84%8F h_01JJS31E3D7NCFC9F7QGTT02K1=revenue-currency currency-conversion=%E8%B4%A7%E5%B8%81%E6%8D%A2%E7%AE%97 h_01HDBZW9XEMGA5RAW0DBBPV3FQ=%E8%B4%A7%E5%B8%81%E6%8D%A2%E7%AE%97 h_01HDBZW9XERK3VN1GS8GHM911W=%E7%A4%BA%E4%BE%8B currency-display=%E8%B4%A7%E5%B8%81%E6%98%BE%E7%A4%BA h_01HDBZW9XE85YC3JHG58YYAB8F=%E8%B4%A7%E5%B8%81%E6%98%BE%E7%A4%BA h_01HDBZW9XEQNG1RDH7A8H002ZD=%E7%A4%BA%E4%BE%8B-1 revenue-data-in-the-dashboard=%E9%9D%A2%E6%9D%BF%E4%B8%AD%E7%9A%84%E6%94%B6%E5%85%A5%E6%95%B0%E6%8D%AE h_01HDBZW9XEVWB9045N0YEVWE6Z=%E9%9D%A2%E6%9D%BF%E4%B8%AD%E7%9A%84%E6%94%B6%E5%85%A5%E6%95%B0%E6%8D%AE revenue-data-in-raw-data-reports=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E4%B8%AD%E7%9A%84%E6%94%B6%E5%85%A5%E6%95%B0%E6%8D%AE h_01HDBZW9XEGYFD3W9FT1N3ZGQW=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E4%B8%AD%E7%9A%84%E6%94%B6%E5%85%A5%E6%95%B0%E6%8D%AE sending-events=%E5%8F%91%E9%80%81%E4%BA%8B%E4%BB%B6 h_01HDBZW9XFESG6MP9QF1XCJKE6=%E5%8F%91%E9%80%81%E4%BA%8B%E4%BB%B6 setting-up-inapp-events=%E8%AE%BE%E7%BD%AE%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 h_01HDBZW9XF13AGRCN2HJ18RHS2=%E8%AE%BE%E7%BD%AE%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 h_01HDBZW9XF6X9H4WCFWC28W1CD=defining-an-inapp-event h_01HDBZW9XFN2B8AC18VW99G8Z6=%E7%A4%BA%E4%BE%8B-2 h_01HDBZW9XFM33BYF90EJPQ35V9=recommended-events-by-business-vertical h_01HDBZW9XF6G2R6Y6S5GFNDM6W=view-inapp-event-data 01JEWW8YB6A91VT8Z4PM9NCV00=%E6%B3%A8%E6%84%8F-1 h_01HDBZW9XF1Q1NB1YS8Q0HKA6K=tips h_01HDBZW9XFFNWCJ18NETEM2287=limitations faq=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HDBZW9XF5H24H2HCJKKHCRTE=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HDBZW9XF5ZNGVEMND08137PR=how-do-i-use-the-revenue-parameter h_01HDBZW9XFZ144ND2FXW2AMGRW=how-does-appsflyer-attribute-events h_01HDBZW9XFDBFY580P939ZP0D4=are-events-recorded-if-a-device-is-offline h_01HDBZW9XFCDMKNWJ75AWHC2Y0=%E6%B3%A8%E6%84%8F-2 h_01HDBZW9XF8Q57JZPD8J2Y25SB=what-are-complex-inapp-events-and-how-do-i-set-them-up h_01KSMX2ECGTDXQP3G9PZW1PFQD=%E7%A4%BA%E4%BE%8B-3 h_01KSMX2ECGNMX39RD2F6ZHQEK4=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01HDBZW9XFRAFSXJE5N5ZPRW2R=can-i-add-multiple-items-to-a-single-transaction h_01HDBZW9XFB9TAT8W4CGNP1892=%E7%A4%BA%E4%BE%8B-4 h_01HDBZW9XFGMG5B5FG2785ERAM=how-does-appsflyer-handle-event-deduplication h_01HDBZW9XFWKN7W90PSVMX73FS=%E6%B3%A8%E6%84%8F-3 h_01HDBZW9XFFXXBYY14A3QGENSF=how-long-does-appsflyer-retain-userlevel-data-and-what-are-the-deletion-obligations h_01HDBZW9XFH80JK748PAPG09B5=do-i-need-to-add-the-os-operating-system-parameter-to-my-events h_01HDNZ708FN0N286R5HDQGMNGZ=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
