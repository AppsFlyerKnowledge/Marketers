---
title: '[测试版]高级安全防护360模块'
metadata:
  keywords:
    - Beta feature
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2025-09-17T15:23:22Z'
  edited_at: '2026-10-14T10:01:13Z'
  id: 39145848948625
  locale: zh-cn
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/zh-cn/articles/39145848948625
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **概要：** 通过高级安全模块加强 Android 应用的欺诈防护。此实时解决方案在归因安装之前检测并阻止归因欺骗和操纵流量。专为高流量应用和Protect360客户端设计，特别是那些与分支机构合作的客户。该模块完全可由您配置，允许初始设置和持续维护，以适应不断发展的欺诈模式并保护数据完整性。

<div id="important" />

> 🚧 **重要提示！**
>
> Protect360 高级安全模块测试版现已面向所有 Protect360 用户开放。如需加入，请联系您的客户成功经理 (CSM)。

<div id="what-is-sdk-spoofing" />

## 什么是 SDK 欺骗？

SDK 欺骗是一种高级欺诈策略，攻击者直接向 AppsFlyer 服务器发送虚假的安装和应用内事件请求，而无需在真实设备上安装或运行应用。应用程序 SDK 未被黑客攻击或修改。相反，欺诈者会模仿真实应用发出的网络请求，使活动看起来合法。

对于广告商而言，SDK 欺骗可能导致从未发生的安装和参与、安装量膨胀、AppsFlyer 和应用商店号之间的差异以及广告支出的浪费。

<div id="important-1" />

<div id="prerequisites" />

<div id="about-the-advanced-security-module" />

## 关于高级安全模块

**高级安全模块**是 AppsFlyer Protect360 套件的附加组件，旨在检测和阻止 Android 上的高级属性欺骗技术。通过评估首次应用启动后但归因发生前的安装活动，该模块可识别可疑流量，并防止欺诈性安装影响您的性能指标。

对于应用商店数据和 AppsFlyer 归属之间存在差异的应用，或管理联盟流量的应用(安装欺诈的两个常见指标 ) , 此解决方案尤其有价值。

**运行方式**

该模块在首次应用启动(由 SDK 记录)后触发，但在安装属性确定之前触发。要使用高级安全模块，您必须使用 Android SDK v6.15.2 或更高版本。

<div id="set-the-advanced-security-module" />

## 设置高级安全模块

设置高级安全模块，以验证应用内流量是否来自已签名的应用构建，并检测(并可选地阻止)欺骗流量。

<div id="configure-the-advanced-security-module" />

<Accordion title="配置高级安全模块">

<div id="step-1-open-and-select-an-app" />

#### 第4步：打开并选择应用程序'%1'

1. 在 AppsFlyer 中，转到**设置 > Protect360 > 高级安全模块**。
2. 单击**开始**或**添加构建**。
3. 选择要在其上实施高级安全模块解决方案的应用程序。
4. 点击**Next**。

<div id="step-2-add-certificate" />

#### 第4步：添加证书

1. 添加
   1. <span class="af-ol-a"></span>证书名称
   2. 证书值
2. 点击**Next**。

注意：向开发人员询问用于对应用程序进行签名的所有[证书哈希](https://dev.appsflyer.com/hc/docs/android-security-plugin#generating-a-sha256-fingerprint)。安全模块使用这些证书来验证流量是否来自您的应用，因此应包含所有相关哈希。

<div id="step-3-excluded-app-versions-from-detection" />

#### 第4步：从检测中排除的应用版本

* 添加应从高级安全检测中排除的应用版本。典型的情况是：
  * 集成高级安全模块之前发布的版本。
  * 不包括模块的测试或遗留构建。

<div id="step-4-build-activation" />

#### 第4步：生成激活

1. 单击**激活构建**。
2. 您的构建将进入**进行中**，直到构建完成。这可能需要10-15分钟。
3. 完成后，单击构建上的**复制代码**按钮复制代码，并将其发送给开发人员以集成到应用程序 SDK 中。"

<div id="note" />

> 📘 **注意**
>
> 生成后，检测模式默认设置为**标记**。在此模式下，AppsFlyer 会标记可疑流量，但不阻止它。安全版本启用后，切换到**已实施**模式以阻止欺骗流量。有关标记模式和已实现模式的详细信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/beta-fraud-protection-studio#fps模式">FPS模式</Anchor>。

</Accordion>

<div id="maintaining-and-updating-the-configuration" />

<Accordion title="维护和更新配置">

欺诈技术会随着时间而变化，恶意行为者可能会尝试逆向设计检测逻辑。定期维护可确保持续有效。

<div id="when-to-update-the-configuration" />

#### **何时更新配置**

如果您发现以下情况，请更新您的设置：

* 通过检测的可疑安装或事件
* 交通模式的变化
* 新的应用版本或证书更改
* 降低现有保护措施的有效性

<div id="what-you-can-update" />

#### **您可以更新的内容**

您可以：

* 添加或更新应用证书
* 修改排除的应用程序版本
* 重建和重新部署安全模块
* 根据展开状态调整检测模式

<div id="best-practices" />

#### **最佳实践**

* 定期查看高级安全见解
* 在应用发布之前与开发人员进行协调
* 签名更改后立即更新证书
* 定期重新评估配置，以领先于新出现的欺诈方法

</Accordion>

<div id="data-visibility" />

## **数据可见性**

高级安全模块检测体现在两个方面：

* Protect360面板
* 作弊防护操作台

<div id="protect360-dashboard" />

<Accordion title="Protect360面板">

高级安全模块检测可在**归属欺骗**部分下找到。

数据被分解为两个KPI和一个图表。

**KPI**

* **标记的归属欺骗**：高级安全模块在标记模式下检测到的安装候选项数。
* 已**实现的归属欺骗**：高级安全模块在实现模式下检测到并阻止的安装候选项数。

**图表**

* **归属欺骗趋势**：高级安全模块检测随时间推移的反映。此图反映了应用程序/秒级欺骗检测的高级别状态。

<Image alt="" src="https://files.readme.io/2f9e63d283850d3b1150dfcefff3c3cd47383cb58c4194dbbec3296da807fcb9-39145854862353.png" width="624px" />

</Accordion>

<div id="fraud-protection-studio-fps" />

<Accordion title="作弊防护操作台">

高级安全模块可以在防欺诈工作室页面找到。

<div id="how-to-access" />

#### 如何访问

要访问高级安全模块，请执行以下操作：

1. 登入AppsFlyer。
2. 在面板左侧的菜单栏中点击配置 > Protect360 > 作弊防护操作台。
3. 使用页面顶部的应用下拉菜单，选择您想要配置的应用。
4. 从左侧菜单中选择高级安全模块卡。

<div id="the-advanced-security-module-page" />

#### “高级安全模块”页面

<Image alt="" src="https://files.readme.io/a94b0c810f719846ae2882cac2ff1dbe4e32f815ee4e023e65e563199f4e3345-39145848945681.png" width="624px" />

高级安全模块页面分为三个部分。

<div id="detection-status" />

##### 检测状态

* 显示检测模式。这两个选项被实现并标记。默认情况下，它设置为**标记**。

注意：要更改检测状态，请与 CSM 联系。

<div id="top-app-versions-by-detection-status" />

##### 按检测状态排名靠前的应用版本

* 该图表显示了安装量排名前 5 的应用版本
  * 每个应用版本都按以下分类：
    * **未标记** - 安装高级安全模块未检测到的候选项。
    * **已标记** - 在标记模式下安装高级安全模块检测到的候选项。
    * **已阻止** - 安装高级安全模块在实现模式下检测到的候选项。每个被阻止的安装候选项都不会继续。

<div id="insights" />

##### 深入分析

洞察帮助您了解图表的细分。三种类型的见解是：

* **所有流量均被阻止** - 100% 被阻止的应用版本可能表示它们未添加到排除列表中。请与您的 CSM 检查应用版本排除列表，并考虑添加相关应用版本。
* **所有流量都标记**了 - 100% 标记的应用版本可能尚未添加到排除列表中。请与您的 CSM 检查应用版本排除列表，并考虑添加相关应用版本。
* **高标记检测率** - 一个或多个应用版本在标记模式下显示超过 20% 的高级安全模块检测。强烈建议联系您的CSM切换到已实施的检测模式，以获得最佳结果。

</Accordion>

<div id="faq" />

<Accordion title="常见问题解答">

<div id="what-is-advanced-security" />

#### 什么是高级安全？

高级安全是 AppsFlyer Android SDK 的附加保护层，可帮助防止归属欺骗，这是一种欺诈，即使没有真实用户安装或使用应用程序，也会报告虚假安装或事件。

<div id="what-problem-does-advanced-security-solve" />

#### 高级安全能解决什么问题？

高级安全有助于防止由 AppsFlyer 中出现的但应用商店或后端系统中不存在的欺骗导致的虚假安装和应用内活动。这样可以减少夸大的安装数量、数据差异和浪费的广告支出。

<div id="what-is-attribution-spoofing" />

#### 什么是归因欺骗？

属性欺骗是一种欺诈技术，攻击者生成虚假的安装或应用内事件数据，并将其发送到 AppsFlyer,同时假装这些数据来自您的应用。没有实际发生真正的应用安装或用户活动。

<div id="how-does-advanced-security-prevent-attribution-spoofing" />

#### 高级安全如何防止归属欺骗？

高级安全性 通过为每个请求添加唯一的验证签名，验证安装和应用内事件数据是否真正来自应用的 SDK。AppsFlyer 会检查此签名，以确认数据是真实的，没有被欺骗或篡改。

<div id="does-advanced-security-affect-the-app-or-user-experience" />

#### 高级安全性会影响应用程序或用户体验吗？

否。高级安全在后台运行，不会改变用户安装或使用应用程序的方式。任何额外的处理都发生在幕后，用户不会注意到。

<div id="who-should-use-advanced-security" />

#### 谁应该使用高级安全？

高级安全对于大量使用非 SRN 或附属网络的应用最为相关，它们看到应用商店安装和 AppsFlyer 数据之间无法解释的差距，或者怀疑存在使用标准方法难以检测的复杂欺诈。

<div id="is-advanced-security-available-for-all-platforms" />

#### 高级安全是否适用于所有平台？

否。高级安全目前仅适用于 Android 应用程序，并且提供给 Protect360 高级客户。它还兼容所有 AppsFlyer 插件。

<div id="how-do-i-know-advanced-security-is-working" />

#### 如何知道高级安全功能在起作用？

在Protect360仪表板和欺诈防护工作室中可以看到检测结果，您可以跟踪被标记或阻止的欺骗流量，并查看随时间推移的趋势。

</Accordion>

<div data-zendesk-anchors="h_01K5EBZV8BY54H332WTWEMYVSA=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA what-is-sdk-spoofing=%E4%BB%80%E4%B9%88%E6%98%AF-sdk-%E6%AC%BA%E9%AA%97 h_01KH8MPFJBSN67PSQXX25NG6ZZ=%E4%BB%80%E4%B9%88%E6%98%AF-sdk-%E6%AC%BA%E9%AA%97 about-the-advanced-security-module=%E5%85%B3%E4%BA%8E%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E6%A8%A1%E5%9D%97 h_01K5C4BCNRE8JWQ9DA20DJ3A07=%E5%85%B3%E4%BA%8E%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E6%A8%A1%E5%9D%97 set-the-advanced-security-module=%E8%AE%BE%E7%BD%AE%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E6%A8%A1%E5%9D%97 h_01KHK6M3CTY4YSCRTSMS707S5Z=%E8%AE%BE%E7%BD%AE%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E6%A8%A1%E5%9D%97 h_01KH8MQXD943CTH2XB4HTH890S=configure-the-advanced-security-module step-1-open-and-select-an-app=%E7%AC%AC4%E6%AD%A5%E6%89%93%E5%BC%80%E5%B9%B6%E9%80%89%E6%8B%A9%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F1 h_01KH8XDACWA2C46MEEGFMM6J8M=%E7%AC%AC4%E6%AD%A5%E6%89%93%E5%BC%80%E5%B9%B6%E9%80%89%E6%8B%A9%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F1 step-2-add-certificate=%E7%AC%AC4%E6%AD%A5%E6%B7%BB%E5%8A%A0%E8%AF%81%E4%B9%A6 h_01KH8XDACYBFZJWHZZCD0JSNGJ=%E7%AC%AC4%E6%AD%A5%E6%B7%BB%E5%8A%A0%E8%AF%81%E4%B9%A6 step-3-excluded-app-versions-from-detection=%E7%AC%AC4%E6%AD%A5%E4%BB%8E%E6%A3%80%E6%B5%8B%E4%B8%AD%E6%8E%92%E9%99%A4%E7%9A%84%E5%BA%94%E7%94%A8%E7%89%88%E6%9C%AC h_01KH8XDAD08E1JJVVSV9GY4RAB=%E7%AC%AC4%E6%AD%A5%E4%BB%8E%E6%A3%80%E6%B5%8B%E4%B8%AD%E6%8E%92%E9%99%A4%E7%9A%84%E5%BA%94%E7%94%A8%E7%89%88%E6%9C%AC step-4-build-activation=%E7%AC%AC4%E6%AD%A5%E7%94%9F%E6%88%90%E6%BF%80%E6%B4%BB h_01KH8XDAD122D7PWP2367YVNP2=%E7%AC%AC4%E6%AD%A5%E7%94%9F%E6%88%90%E6%BF%80%E6%B4%BB h_01KH8XJXN717M3GDJNPPMWDBHY=%E6%B3%A8%E6%84%8F h_01KH9HBT6Y803N7ABMSWHZCKE9=maintaining-and-updating-the-configuration when-to-update-the-configuration=%E4%BD%95%E6%97%B6%E6%9B%B4%E6%96%B0%E9%85%8D%E7%BD%AE h_01KH8XDAD3M4RARMK7DS7RA08X=%E4%BD%95%E6%97%B6%E6%9B%B4%E6%96%B0%E9%85%8D%E7%BD%AE what-you-can-update=%E6%82%A8%E5%8F%AF%E4%BB%A5%E6%9B%B4%E6%96%B0%E7%9A%84%E5%86%85%E5%AE%B9 h_01KH8XDAD46P524Z2H8BBZRAR1=%E6%82%A8%E5%8F%AF%E4%BB%A5%E6%9B%B4%E6%96%B0%E7%9A%84%E5%86%85%E5%AE%B9 best-practices=%E6%9C%80%E4%BD%B3%E5%AE%9E%E8%B7%B5 h_01KH8XDAD5PVKNPW37PMG3NKHH=%E6%9C%80%E4%BD%B3%E5%AE%9E%E8%B7%B5 data-visibility=%E6%95%B0%E6%8D%AE%E5%8F%AF%E8%A7%81%E6%80%A7 h_01K5C4BCNTBVDQX8DGTGEAN01T=%E6%95%B0%E6%8D%AE%E5%8F%AF%E8%A7%81%E6%80%A7 h_01KH9H6RPBTNTPNMW68VSSN582=protect360-dashboard h_01KH9H6RPBAY53PNH00FX9596D=fraud-protection-studio-fps how-to-access=%E5%A6%82%E4%BD%95%E8%AE%BF%E9%97%AE h_01K5C4BCNZBS424A4PMS7AR8XG=%E5%A6%82%E4%BD%95%E8%AE%BF%E9%97%AE the-advanced-security-module-page=%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E6%A8%A1%E5%9D%97%E9%A1%B5%E9%9D%A2 h_01K5C4BCP14ARR3JMDPMRWZPTT=%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E6%A8%A1%E5%9D%97%E9%A1%B5%E9%9D%A2 h_01K5C4BVN5CQVP8HJG1MBV72AW=%E6%A3%80%E6%B5%8B%E7%8A%B6%E6%80%81 h_01K5C4BVN69SK4TBNWPFPWYXPN=%E6%8C%89%E6%A3%80%E6%B5%8B%E7%8A%B6%E6%80%81%E6%8E%92%E5%90%8D%E9%9D%A0%E5%89%8D%E7%9A%84%E5%BA%94%E7%94%A8%E7%89%88%E6%9C%AC h_01K5C4BVN6XA4SNP4TK9SSRHS9=%E6%B7%B1%E5%85%A5%E5%88%86%E6%9E%90 h_01KH9JJ5Y7QA631VTKXVGFXBYJ=faq what-is-advanced-security=%E4%BB%80%E4%B9%88%E6%98%AF%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8 h_01KH9HERVW7QE2JXCGBBC206VW=%E4%BB%80%E4%B9%88%E6%98%AF%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8 what-problem-does-advanced-security-solve=%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E8%83%BD%E8%A7%A3%E5%86%B3%E4%BB%80%E4%B9%88%E9%97%AE%E9%A2%98 h_01KH9HERVX8V537KQBSMAR31T8=%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E8%83%BD%E8%A7%A3%E5%86%B3%E4%BB%80%E4%B9%88%E9%97%AE%E9%A2%98 what-is-attribution-spoofing=%E4%BB%80%E4%B9%88%E6%98%AF%E5%BD%92%E5%9B%A0%E6%AC%BA%E9%AA%97 h_01KH9HERVY5G1J5KQV9ZKTHGXX=%E4%BB%80%E4%B9%88%E6%98%AF%E5%BD%92%E5%9B%A0%E6%AC%BA%E9%AA%97 how-does-advanced-security-prevent-attribution-spoofing=%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E5%A6%82%E4%BD%95%E9%98%B2%E6%AD%A2%E5%BD%92%E5%B1%9E%E6%AC%BA%E9%AA%97 h_01KH9HERVZAT11WNX99R2EQCPB=%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E5%A6%82%E4%BD%95%E9%98%B2%E6%AD%A2%E5%BD%92%E5%B1%9E%E6%AC%BA%E9%AA%97 does-advanced-security-affect-the-app-or-user-experience=%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E6%80%A7%E4%BC%9A%E5%BD%B1%E5%93%8D%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F%E6%88%96%E7%94%A8%E6%88%B7%E4%BD%93%E9%AA%8C%E5%90%97 h_01KH9HERW0XFEGCKGJZA6C44HY=%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E6%80%A7%E4%BC%9A%E5%BD%B1%E5%93%8D%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F%E6%88%96%E7%94%A8%E6%88%B7%E4%BD%93%E9%AA%8C%E5%90%97 who-should-use-advanced-security=%E8%B0%81%E5%BA%94%E8%AF%A5%E4%BD%BF%E7%94%A8%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8 h_01KH9HERW00N9M05DSF8998JE0=%E8%B0%81%E5%BA%94%E8%AF%A5%E4%BD%BF%E7%94%A8%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8 is-advanced-security-available-for-all-platforms=%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E6%98%AF%E5%90%A6%E9%80%82%E7%94%A8%E4%BA%8E%E6%89%80%E6%9C%89%E5%B9%B3%E5%8F%B0 h_01KH9HERW13WYZYBAGA9XXKW1B=%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E6%98%AF%E5%90%A6%E9%80%82%E7%94%A8%E4%BA%8E%E6%89%80%E6%9C%89%E5%B9%B3%E5%8F%B0 how-do-i-know-advanced-security-is-working=%E5%A6%82%E4%BD%95%E7%9F%A5%E9%81%93%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E5%8A%9F%E8%83%BD%E5%9C%A8%E8%B5%B7%E4%BD%9C%E7%94%A8 h_01KH9HERW2CQ76W33ERFTP0FS9=%E5%A6%82%E4%BD%95%E7%9F%A5%E9%81%93%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E5%8A%9F%E8%83%BD%E5%9C%A8%E8%B5%B7%E4%BD%9C%E7%94%A8" />
