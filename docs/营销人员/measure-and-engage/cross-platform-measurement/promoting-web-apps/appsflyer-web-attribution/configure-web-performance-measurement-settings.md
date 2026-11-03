---
title: 网页端效果衡量设置
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
  created_at: '2026-02-05T08:47:53Z'
  edited_at: '2026-10-14T10:00:34Z'
  id: 43541863890961
  locale: zh-cn
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/zh-cn/articles/43541863890961
---
> **概览：** 配置网页端归因，控制AppsFlyer如何将网站访问、转化和用户活动归因至广告系列。设置项包括归因窗口、获客事件、再互动规则和排除域名。

## 概览

网页端归因设置决定AppsFlyer如何衡量网站上的用户活动并完成归因。这些设置决定：

* 哪些事件可作为获客事件。
* 后续事件可在多长时间内归因至营销来源。
* 何时将再次访问网站的用户判定为再互动或再次获取。
* 归因时排除哪些域名。

### 应由谁配置这些设置

营销团队和增长负责人通常会根据业务目标配置这些设置。SDK对接和域名配置可能需要技术团队参与。

### 访问网页端归因设置

如需打开网页端应用的归因设置：

1. 在AppsFlyer中，前往**我的应用**
2. 从列表中选择您的网页端应用
3. 前往**应用设置**>**归因**

## 快速参考

| 设置项 | 默认值 | 选项 | 可编辑 | 控制内容 |
| --- | --- | --- | --- | --- |
| 应用名称 | 用户输入 | 1–100个字符 | 是 | AppsFlyer中的显示名称 |
| 完整URL（主域名） | 用户输入 | 1–500个字符 | 否 | 应用标识符和主要排除域名 |
| Web SDK ID | 自动生成 | 1–550个字符 | 否 | 用于采集事件的SDK标识符 |
| 币种 | 用户选择 | ISO代码 | 是 | 收入和ROI报表 |
| 时区 | 用户选择 | IANA时区 | 受限 | 报表时间戳 |
| 获客事件 | 首次访问 | 事件名称 | 是 | 判定用户完成获客的条件 |
| 回溯窗口（UA） | 30天 | 1小时 – 90天 | 是 | 查找UA触点的回溯时长 |
| 再互动窗口 | 30天 | 1小时 – 90天 | 是 | 再营销广告互动可获得归因的时长 |
| 休眠窗口（再互动） | 已停用 | 0–30天 | 是 | 触发再营销前的最短未活跃时长 |
| 归因窗口 | 生命周期 | 预设选项 | 是 | 后续事件归因至获客来源的时长 |
| 休眠窗口（再次获取） | 90天 | 1–180天 | 是 | 用户何时被视为已流失 |
| 再次获取事件 | 访问 | 事件名称 | 是 | 用于判定流失用户再次获取的事件 |
| 排除域名 | 仅主域名 | 最多100个 | 是 | 归因时忽略的域名 |

**限制条件：**  
再互动休眠窗口的时长必须**小于或等于**再次获取休眠窗口的时长。否则，用户可能尚未满足再营销条件，就已被判定为再次获取。

## **基本设置**

网页端应用的基本设置包括：

* 应用名称
* 完整URL
* Web SDK ID
* 币种
* 时区

有关详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/adding-an-app-to-appsflyer#web">将应用添加到AppsFlyer</Anchor>。

## 获客设置

获客（UA）设置决定AppsFlyer何时将用户判定为首次获取，以及如何将该次获取归因至营销来源。

<div id="user-acquisition-event" />

<Accordion title="获客事件">

用于触发获客的事件。这一重要业务行为用于判定用户何时才算真正完成获客。

#### 为何自定义

默认的**首次访问**通常无法充分反映用户价值。用户可能误点广告，也可能进入网站后立即离开。自定义此设置后，系统会将长期价值（LTV）归因至真正促成有效行为的营销来源，避免仅根据一次随意点击进行归因。

**默认值：** 首次访问（用户首次访问网站时即完成获客）

#### 各行业常用选项

| **行业** | **推荐的UA事件** |
| --- | --- |
| 银行/金融 | registration或first\\_time\\_deposit |
| 电商 | sign\\_up或first\\_purchase |
| 外卖 | first\_order |
| SaaS/订阅 | subscription\_start |
| 游戏 | sign\_up、tutorial\_complete或first\_purchase |

#### 运作方式

如果设置为**首次访问**：

* 用户首次访问网站时即完成获客。
* 归因从首次访问开始。

如果设置为**自定义事件**（例如sign\_up）：

* 从首次访问网站到完成该事件，用户将进入<strong>「获客前阶段」</strong>。
* 在获客前阶段，系统会将事件归因至回溯窗口内最近一次非自然触点（末次触点归因）。
* 触发自定义UA事件后，系统会生成一条**获客转化**，并开始长期归因。

#### 示例场景（UA事件=sign\_up）：

* **第0天：** 用户通过Facebook广告访问网站→进入获客前阶段
* **第2天：** 用户通过Google广告访问网站→归因来源转为Google（末次触点）
* **第3天：** 用户完成注册→获客归因至Google广告

**第10天：** 用户完成购买→此次购买归因至Google，用于LTV衡量

</Accordion>

<div id="lookback-window-user-acquisition" />

<Accordion title="回溯窗口（获客）">

AppsFlyer向前回溯多长时间，以查找促成获客的营销触点。

此窗口决定营销触点在AppsFlyer中的有效时长。用户通过广告访问网站后，如果过一段时间才完成UA事件，该设置将决定广告是否仍能获得归因。

**默认值：** 30天

**范围：** 1小时至90天

#### 运作方式

用户触发UA事件（例如sign\_up）后，AppsFlyer会在回溯窗口内查找最近一次非自然触点，并将此次获客归因至对应的营销来源。

#### 示例1（30天回溯窗口）：

* **第0天：** 用户点击Facebook广告并访问网站
* **第25天：** 用户再次访问网站（直接访问），并完成sign\_up事件
* **结果：** 获客归因至Facebook（在30天回溯窗口内）

#### 示例2（回溯窗口已过期）：

* **第0天：** 用户点击Facebook广告并访问网站
* **第40天：** 用户再次访问网站（直接访问），并完成sign\_up事件

**结果：** 获客标记为自然量（已超出30天回溯窗口）

</Accordion>

## 再互动设置

再互动设置决定已获取用户通过再营销广告系列再次访问网站时，AppsFlyer如何对用户活动进行归因。

<div id="reengagement-window-item" />

<Accordion title="再互动窗口">

再互动转化发生后，AppsFlyer继续将事件归因至该营销触点的时长。

该设置决定再营销广告系列获得用户活动归因的时长。既让再营销广告系列获得相应归因，又能将长期LTV归因至最初的获客来源。

**默认值：** 30天

**范围：** 1小时至90天

#### 运作方式

完成获客的用户通过非自然来源（例如再营销广告）再次访问网站，并符合再互动条件时，系统会生成一条**再营销转化**。此窗口内发生的事件会进行**双重归因**：

1. **主要归因**→再营销广告系列
   * 目的：将事件归因至再营销广告系列
2. **辅助归因**→最初的获客来源
   * 目的：支持UA视图，将用户完整的生命周期价值（LTV）归因至最初的获客来源

#### 示例（在窗口期内）：

* **第0天：** 用户通过Facebook广告完成获客
* **第50天：** 用户点击邮件再营销广告系列并再次访问网站（生成再营销转化）
* **第60天：** 用户完成一笔100美元的购买（再营销后第10天）
* **结果-双重归因：**
  * **主要归因（再营销视图）：** 这笔100美元的购买归因至邮件广告系列
  * **辅助归因（UA视图）：** 用户LTV中的这笔100美元收入也会归因至Facebook广告
* **报表：**
  * 统一视图：显示这笔购买归因至邮件广告系列
  * 再营销视图：显示这笔购买归因至邮件广告系列
  * UA视图：显示这笔购买归因至Facebook广告

</Accordion>

<div id="inactivity-window-for-reengagement" />

<Accordion title="再互动休眠窗口">

在非自然触点能够生成再互动（再营销）转化前，用户必须保持未活跃的最短时长。

避免在用户仍活跃于网站时，将其活动归因至再营销广告系列。确保广告系列面向真正未活跃的用户，从而优化再营销预算。

**默认值：** 已停用

**范围：** 0天（停用）至30天

#### 运作方式

**停用时：**

* 已获取用户产生的每个非自然触点都会生成再营销转化

**启用时（例如设为7天）：**

* 仅当用户已连续至少7天未活跃时，才会生成再营销转化
* 如果用户近期有过活跃，系统会将此次访问归因至最初的获客来源

**限制条件：**

* 不得超过休眠窗口（再次获取）

#### 示例（休眠窗口为7天）：

* **第0天：** 用户通过Facebook广告完成获客
* **第3天：** 用户通过自然流量访问网站
* **第5天：** 用户点击再营销广告→**不生成再营销转化**（仅连续未活跃2天）
* **第15天：** 用户点击再营销广告→**生成再营销转化**（已连续12天未活跃）

</Accordion>

## 再次获取设置

再次获取设置决定何时将未活跃用户判定为「已流失」，以及如何在这些用户再次访问后完成再次获取。

<div id="inactivity-window-reacquisition" />

<Accordion title="休眠窗口（再次获取）">

用户持续完全未活跃并被标记为「已流失」所需的时长。已流失用户可以再次获取，系统会为此生成一条新的UA转化。

该设置用于定义业务中的用户流失门槛。该设置决定何时将用户视为「已流失」并符合再次获取条件，使召回广告系列能够获得重新吸引流失用户的归因。

**默认值：** 90天

**范围：** 1至180天

#### 运作方式

**用户被标记为「已流失」后：**

* 用户之后发生的新事件不再归因至最初的获客来源
* 用户进入「获客前」状态（等待再次获取）
* 最初获客对应的归因窗口不再适用

**已流失用户再次访问时：**

* 用户完成再次获取事件→生成新的UA转化
* 召回广告系列被记为新的获客来源
* 在报表中，此次再次获取按全新的获客处理

#### 示例（90天休眠窗口）：

* **第0天：** 用户通过Google广告完成获客
* **第50天：** 用户最后一次活跃
* **第140天：** 用户被标记为已流失（连续90天未活跃）
* **第145天：** 用户点击邮件召回广告系列

**第146天：** 用户完成再次获取事件→**新的UA转化**归因至邮件广告系列

</Accordion>

<div id="reacquisition-event" />

<Accordion title="再次获取事件">

用于触发已流失用户再次获取的事件。只有已流失用户才能再次获取。

许多获客事件属于一次性行为（例如sign\_up、first\_purchase），无法重复发生。通过此设置，您可以定义一个可重复发生的事件，用于判定已流失用户已再次访问网站。

**默认值：** 访问（已流失用户首次再次访问网站时会**立即完成再次获取**）

**常用替代事件：** sign\_in或purchase

#### 运作方式

**如果设置为自定义事件（例如sign\_in**）：

* 已流失用户必须完成指定事件，才能再次获取
* 完成再次获取前，用户可以多次访问网站
* 采用更严格的标准判定用户是否真正完成再次获取

#### 示例（再次获取事件=sign\_in）：

* 用户连续90天未活跃后被标记为已流失
* 用户点击邮件召回广告系列并访问网站→尚未完成再次获取
* 一天后，用户登录→生成再次获取转化，并归因至邮件广告系列

</Accordion>

## 归因窗口

<div id="time-period" />

<Accordion title="时间范围">

用户完成获客后，AppsFlyer将事件归因至该转化的最长时段。

**默认值：** 永久

**可用选项：** 无、1天、7天、30天、60天、90天、180天、365天、永久（受数据保留期限限制）

</Accordion>

## 排除域名

归因时需要排除的域名。用户在指定域名与您的网站之间跳转时，AppsFlyer不会对由此产生的访问或事件进行归因。

**目的：**

1. **避免自归因：** 排除您自己的域名
2. **排除第三方流程：** 排除支付网关和身份验证提供商

<div id="domain-types" />

<Accordion title="域名类型">

#### 主要域名（必填，自动）

* 创建应用时设置的主要网站域名
* 系统会自动添加，且无法移除
* 每个网页端应用只能设置一个主要域名
* **自动排除子域名：** 系统会自动排除主要域名下的所有子域名
  * 示例：example.com会自动排除shop.example.com、blog.example.com等子域名
* **排除后的影响：** 不会发生自归因

#### 内部域名（可选）

* 同一品牌下未涵盖在主要域名中的其他域名
* 最多可添加99个域名
* 示例：使用不同顶级域名的品牌网站，例如example.co.uk、example.in
* **排除后的影响：** 不会发生自归因

#### 外部域名（可选）

外部排除域名分为两类：

#### 外部域名（由您添加）

* 网站会直接使用、但不属于您品牌的域名
* 包括支付网关、支付处理网站和身份验证提供商
* 最多可添加99个域名
* 示例：auth0.com、okta.com、facebook.com、google.com
* **排除后的影响：** 系统会忽略相关访问

#### 外部域名（AppsFlyer预设）

* AppsFlyer会自动排除以下域名：

  **支付服务提供商**

  * PayPal（支付结算）
  * Stripe（支付结算）
  * Adyen（支付结算）
  * Klarna（支付结算）
  * Braintree（支付网关）
  * Square（支付结算）
  * Paddle（支付结算）
  * Mollie（支付结算）
  * Alipay（支付结算）
  * Razorpay（支付结算）
  * Paytm（支付结算）
  * PayU（支付结算）
  * Mercado Pago（支付结算）
  * Yandex Pay（支付结算）
  * Naver Pay（支付结算）

  **OAuth和SSO登录**

  * Google Sign-In（Google账号登录）
  * Apple ID（Apple账号登录）
  * Microsoft（Microsoft 365/Entra账号登录）
  * Microsoft Live（Outlook/Live账号登录）
  * Facebook Login（仅限Facebook登录域名）
  * Yandex Login（Yandex账号登录）
  * Kakao Login（Kakao账号登录）
  * Naver Login（Naver账号登录）
  * LINE Login（LINE账号登录）
  * Weixin Login（微信OAuth登录）
  * VK Login（VK账号登录）
  * Daum Login（Daum账号登录）
* 自动排除域名列表无法编辑
* **排除后的影响：** 系统会忽略相关访问

</Accordion>

<div id="adding-excluded-domains" />

<Accordion title="添加排除域名">

**如需添加域名：**

1. 前往网页端应用设置→归因
2. 找到「排除域名」部分
3. 点击**添加域名**
4. 输入域名（例如custom-gateway.com）
5. 选择域名类型：内部域名或外部域名
6. 点击**保存**

**重要说明：**

* 域名排除设置将在**1小时**内生效
* 更改**仅对今后的数据生效**（不影响历史数据）
* 系统会自动排除常用支付服务提供商以及OAuth/SSO登录域名。完整列表请参阅[外部域名（AppsFlyer预设）](#外部域名appsflyer预设)，无需手动添加这些域名

</Accordion>

<div id="requirements-and-validation" />

<Accordion title="要求与验证">

#### 域名格式：

* 仅输入域名，不含协议、路径或端口
* 每个域名最多500个字符
* 系统会自动移除协议前缀（https://），并将域名转换为小写

#### 示例：

* example.com✅
* shop.example.com✅（如果example.com是主要域名，则无需添加）
* https://example.com→example.com✅（协议前缀已移除）
* example.com/path❌（不允许包含路径）
* example.com:8080❌（不允许包含端口）

#### 数量限制：

* 最多可添加100个域名（包括1个主要域名）

</Accordion>

## 从People-Based Attribution（PBA）迁移

<div id="key-differences" />

<Accordion title="主要区别">

| **对比项** | **PBA（旧版）** | **PBA（旧版）** |
| --- | --- | --- |
| **新版网页端效果衡量** | 配置层级 | 品牌包层级 |
| 网页端应用层级 | 自定义UA事件 | 不支持 |
| 可完全自定义 | 时间窗口 | 控制选项有限 |

</Accordion>

<div id="migration-steps" />

<Accordion title="可完全控制（1小时至永久）">

1. 迁移步骤
   1. 创建新的网页端应用
2. 前往「我的应用」→「添加应用」→选择「网站」   
   选择Web SDK ID
3. 建议继续使用现有PBA开发密钥，以免修改网站代码。   
   完成设置
4. 将PBA设置映射到新的网页端归因设置   
   添加排除域名

将PBA（品牌包）中的排除域名映射到新的网页端归因设置**注意：**

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A7%88 h_01KGPFHN8MKTPX5VYDEV30M9A7=%E6%A6%82%E8%A7%88 who-should-configure-these-settings=%E5%BA%94%E7%94%B1%E8%B0%81%E9%85%8D%E7%BD%AE%E8%BF%99%E4%BA%9B%E8%AE%BE%E7%BD%AE h_01KGPFK1RNA7ZTJRACJ6M97EAB=%E5%BA%94%E7%94%B1%E8%B0%81%E9%85%8D%E7%BD%AE%E8%BF%99%E4%BA%9B%E8%AE%BE%E7%BD%AE accessing-web-attribution-settings=%E8%AE%BF%E9%97%AE%E7%BD%91%E9%A1%B5%E7%AB%AF%E5%BD%92%E5%9B%A0%E8%AE%BE%E7%BD%AE h_01KGPFM0DJDMVDXZC2B6G6DVX5=%E8%AE%BF%E9%97%AE%E7%BD%91%E9%A1%B5%E7%AB%AF%E5%BD%92%E5%9B%A0%E8%AE%BE%E7%BD%AE quick-reference=%E5%BF%AB%E9%80%9F%E5%8F%82%E8%80%83 h_01KGPFT1W65R724WCNDPBHY3F6=%E5%BF%AB%E9%80%9F%E5%8F%82%E8%80%83 basic-settings=%E5%9F%BA%E6%9C%AC%E8%AE%BE%E7%BD%AE h_01KGPGJG092S1TEDB1T9JNBASE=%E5%9F%BA%E6%9C%AC%E8%AE%BE%E7%BD%AE user-acquisition-settings=%E8%8E%B7%E5%AE%A2%E8%AE%BE%E7%BD%AE h_01KGPGE592EK59XXVKTTFDGX16=%E8%8E%B7%E5%AE%A2%E8%AE%BE%E7%BD%AE h_01KGPGRTEFA0PJ3DB7MR4W85EB=user-acquisition-event why-customize=%E4%B8%BA%E4%BD%95%E8%87%AA%E5%AE%9A%E4%B9%89 h_01KGPHMJWF6Z1VV0KH301TYAS5=%E4%B8%BA%E4%BD%95%E8%87%AA%E5%AE%9A%E4%B9%89 common-alternatives-by-industry=%E5%90%84%E8%A1%8C%E4%B8%9A%E5%B8%B8%E7%94%A8%E9%80%89%E9%A1%B9 h_01KGPHMSEDGJ2E6NSB1ZCR5CCW=%E5%90%84%E8%A1%8C%E4%B8%9A%E5%B8%B8%E7%94%A8%E9%80%89%E9%A1%B9 how-it-works=%E8%BF%90%E4%BD%9C%E6%96%B9%E5%BC%8F h_01KGPHN5M5GBBMPBYRMYHB9F0E=%E8%BF%90%E4%BD%9C%E6%96%B9%E5%BC%8F example-scenario-ua-event-sign_up=%E7%A4%BA%E4%BE%8B%E5%9C%BA%E6%99%AFua%E4%BA%8B%E4%BB%B6sign_up h_01KGPHQES3SF5AKBNYD8CY3RG8=%E7%A4%BA%E4%BE%8B%E5%9C%BA%E6%99%AFua%E4%BA%8B%E4%BB%B6sign_up h_01KGPGRTEFYRAZD7Z9NYDKV907=lookback-window-user-acquisition how-it-works::69b3417c=%E8%BF%90%E4%BD%9C%E6%96%B9%E5%BC%8F-1 h_01KGPHX2JNAWZ8VJZ25CRWP1ER=%E8%BF%90%E4%BD%9C%E6%96%B9%E5%BC%8F-1 example-1-30day-lookback=%E7%A4%BA%E4%BE%8B130%E5%A4%A9%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 h_01KGPHX8JMG7FMRS1MYFYS6JRV=%E7%A4%BA%E4%BE%8B130%E5%A4%A9%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 example-2-window-expired=%E7%A4%BA%E4%BE%8B2%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3%E5%B7%B2%E8%BF%87%E6%9C%9F h_01KGPHXT83JHJ6J0APVN7NRJ3E=%E7%A4%BA%E4%BE%8B2%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3%E5%B7%B2%E8%BF%87%E6%9C%9F reengagement-settings=%E5%86%8D%E4%BA%92%E5%8A%A8%E8%AE%BE%E7%BD%AE h_01KGPJ1ZMXXJJNCBB52CHY95Z2=%E5%86%8D%E4%BA%92%E5%8A%A8%E8%AE%BE%E7%BD%AE reengagement-window%C2%A0item=reengagement-window-item h_01KGPJ58N3712E1NZ4E6JVGAY2=reengagement-window-item how-it-works::dafb60ec=%E8%BF%90%E4%BD%9C%E6%96%B9%E5%BC%8F-2 h_01KGPJFG3X578XCP5X353RRVR1=%E8%BF%90%E4%BD%9C%E6%96%B9%E5%BC%8F-2 example-within-window=%E7%A4%BA%E4%BE%8B%E5%9C%A8%E7%AA%97%E5%8F%A3%E6%9C%9F%E5%86%85 h_01KGPJG6WSYX2R0VVQYXXWZSMA=%E7%A4%BA%E4%BE%8B%E5%9C%A8%E7%AA%97%E5%8F%A3%E6%9C%9F%E5%86%85 h_01KGPJ58N3QH9RKXTVZXCZ1WGW=inactivity-window-for-reengagement how-it-works::4a4cf0f=%E8%BF%90%E4%BD%9C%E6%96%B9%E5%BC%8F-3 h_01KGPJK3H2JF7PV1ATQB3TE9AX=%E8%BF%90%E4%BD%9C%E6%96%B9%E5%BC%8F-3 example-7day-inactivity-window=%E7%A4%BA%E4%BE%8B%E4%BC%91%E7%9C%A0%E7%AA%97%E5%8F%A3%E4%B8%BA7%E5%A4%A9 h_01KGPJKDMY4FRAJSMHE19GGJCA=%E7%A4%BA%E4%BE%8B%E4%BC%91%E7%9C%A0%E7%AA%97%E5%8F%A3%E4%B8%BA7%E5%A4%A9 reacquisition-settings=%E5%86%8D%E6%AC%A1%E8%8E%B7%E5%8F%96%E8%AE%BE%E7%BD%AE h_01KGPJMJDX83SBA77A7BSRZ87V=%E5%86%8D%E6%AC%A1%E8%8E%B7%E5%8F%96%E8%AE%BE%E7%BD%AE h_01KGPJPC0QXYFD6Q09XF7T3XA9=inactivity-window-reacquisition how-it-works::9c91010b=%E8%BF%90%E4%BD%9C%E6%96%B9%E5%BC%8F-4 h_01KGPJV8EJR94H1P7GZXMP8HSR=%E8%BF%90%E4%BD%9C%E6%96%B9%E5%BC%8F-4 example-90day-window=%E7%A4%BA%E4%BE%8B90%E5%A4%A9%E4%BC%91%E7%9C%A0%E7%AA%97%E5%8F%A3 h_01KGPJVHCNBZHD9ZXW288CGG9H=%E7%A4%BA%E4%BE%8B90%E5%A4%A9%E4%BC%91%E7%9C%A0%E7%AA%97%E5%8F%A3 h_01KGPJPC0QY2726Z583AQ7G5W2=reacquisition-event how-it-works::587eebec=%E8%BF%90%E4%BD%9C%E6%96%B9%E5%BC%8F-5 h_01KGPJY5PA9907PXBRC2QHNJ6T=%E8%BF%90%E4%BD%9C%E6%96%B9%E5%BC%8F-5 example-reacquisition-event-sign_in=%E7%A4%BA%E4%BE%8B%E5%86%8D%E6%AC%A1%E8%8E%B7%E5%8F%96%E4%BA%8B%E4%BB%B6sign_in h_01KGPJYWG31QJ1G5A09QC00AMY=%E7%A4%BA%E4%BE%8B%E5%86%8D%E6%AC%A1%E8%8E%B7%E5%8F%96%E4%BA%8B%E4%BB%B6sign_in attribution-window=%E5%BD%92%E5%9B%A0%E7%AA%97%E5%8F%A3 h_01KGPK8H7P5AT59S0GQ9ZK0F01=%E5%BD%92%E5%9B%A0%E7%AA%97%E5%8F%A3 h_01KGPK1CSV5XGKHX3XVS37QFKS=time-period excluded-domains=%E6%8E%92%E9%99%A4%E5%9F%9F%E5%90%8D h_01KGPKA56KQRJKRS54HBR50NJN=%E6%8E%92%E9%99%A4%E5%9F%9F%E5%90%8D h_01KGPKCY1EBCMYDDYS6SZEK1ZR=domain-types primary-required-automatic=%E4%B8%BB%E8%A6%81%E5%9F%9F%E5%90%8D%E5%BF%85%E5%A1%AB%E8%87%AA%E5%8A%A8 h_01KGPKJQ7M82KW5VE9ESYNNFEQ=%E4%B8%BB%E8%A6%81%E5%9F%9F%E5%90%8D%E5%BF%85%E5%A1%AB%E8%87%AA%E5%8A%A8 internal-optional=%E5%86%85%E9%83%A8%E5%9F%9F%E5%90%8D%E5%8F%AF%E9%80%89 h_01KGPKJV9B2BHDR64JD24VHH1X=%E5%86%85%E9%83%A8%E5%9F%9F%E5%90%8D%E5%8F%AF%E9%80%89 external-optional=%E5%A4%96%E9%83%A8%E5%9F%9F%E5%90%8D%E5%8F%AF%E9%80%89 h_01KGPKJZQYZESHHH3D0NA2WC9F=%E5%A4%96%E9%83%A8%E5%9F%9F%E5%90%8D%E5%8F%AF%E9%80%89 external-listed-by-you=%E5%A4%96%E9%83%A8%E5%9F%9F%E5%90%8D%E7%94%B1%E6%82%A8%E6%B7%BB%E5%8A%A0 h_01KGPKK4THXQ88AXT58GZ2MHHE=%E5%A4%96%E9%83%A8%E5%9F%9F%E5%90%8D%E7%94%B1%E6%82%A8%E6%B7%BB%E5%8A%A0 external-listed-by-appsflyer=%E5%A4%96%E9%83%A8%E5%9F%9F%E5%90%8Dappsflyer%E9%A2%84%E8%AE%BE h_01KGPKK96ZAZSKVPBX60FC888X=%E5%A4%96%E9%83%A8%E5%9F%9F%E5%90%8Dappsflyer%E9%A2%84%E8%AE%BE h_01KGPKCY1ETKF1NQ2BP6Z3JH4T=adding-excluded-domains h_01KGPKCY1EE01631ZEYGC6FEJH=requirements-and-validation domain-format=%E5%9F%9F%E5%90%8D%E6%A0%BC%E5%BC%8F h_01KGPKKXRA59A4RDY4QE1M0Q66=%E5%9F%9F%E5%90%8D%E6%A0%BC%E5%BC%8F examples=%E7%A4%BA%E4%BE%8B h_01KGPKM213203KA8CEBHZ9KJP3=%E7%A4%BA%E4%BE%8B limits=%E6%95%B0%E9%87%8F%E9%99%90%E5%88%B6 h_01KGPKM8AMQ5BA88ZCSTRJ2JV7=%E6%95%B0%E9%87%8F%E9%99%90%E5%88%B6 migrating-from-peoplebased-attribution-pba=%E4%BB%8Epeople-based-attributionpba%E8%BF%81%E7%A7%BB h_01KGPKPGSF3VSBTQJR6JN80BF4=%E4%BB%8Epeople-based-attributionpba%E8%BF%81%E7%A7%BB h_01KGPKQPWC1GYYGYYD6PCDWX29=key-differences h_01KGPKQPWD00B08Z76ZYGRP4AT=migration-steps" />
