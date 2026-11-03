---
title: 面向儿童的应用 — 常见问题解答
metadata:
  keywords:
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
  created_at: '2023-09-05T19:02:32Z'
  edited_at: '2026-10-23T12:58:27Z'
  id: 18324823209745
  locale: zh-cn
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/zh-cn/articles/18324823209745
---
**内容概要：** 解答有关面向儿童的应用的常见问题。

## 概述

为保护儿童隐私，面向儿童的应用需要遵守多项政策、法律和法规，主要包括《儿童在线隐私保护法》（COPPA）和《通用数据保护条例》（GDPR）。近年来，iOS 和 Android 等平台也陆续出台了相关政策，以加强对儿童隐私的保护。创建应用时，首先需要确定目标受众是仅面向儿童，还是同时面向儿童和成人。如需了解如何为面向儿童的应用实施符合相关法规要求的归因解决方案，请参阅<Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">儿童应用合规指南</Anchor>。

## 添加面向儿童的应用

<div id="what-steps-do-i-need-to-take-when-adding-a-childdirected-app" />

<Accordion title="添加面向儿童的应用时，需要执行哪些步骤？">

1. 按照<Anchor target="_blank" href="/marketers/zh/docs/adding-an-app-to-appsflyer">添加应用向导</Anchor>完成操作。
2. 在向导的第 2 步中，按照<Anchor target="_blank" href="/marketers/zh/docs/adding-an-app-to-appsflyer#定义应用受众">面向儿童的应用相关说明</Anchor>设置目标受众。
3. 添加应用后：
   * 在 SDK 中配置 <Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#在相关应用中添加dev-key">Dev key</Anchor>。
   * 根据要求配置相应的<Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">隐私控制措施</Anchor>。

 有关如何与广告平台对接合规工具的更多信息，请参阅[使用广告平台合规工具](#使用-appsflyer-合规工具)。

</Accordion>

<div id="when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children" />

<Accordion title="将新应用标记为面向儿童后，会发生什么？">

添加应用两周后，您会收到一条通知，要求确认已为面向儿童的应用配置隐私控制措施。确认后，系统会发送确认消息。您可以随时在通知中心查看该消息，也可以在<Anchor target="_blank" href="/marketers/zh/docs/audit-log">审计日志</Anchor>中查看确认详情。

</Accordion>

<div id="if-ive-added-an-app-and-didn-t-define-it-as-directed-towards-children-can-i-change-this-later" />

<Accordion title="可以更改应用是否面向儿童的设置吗？">

目前，添加应用时选择是否将其设为面向儿童的应用后，无法撤销或更改该选择。只有在添加应用时，才能进行此项设置。

</Accordion>

<div id="how-can-i-see-if-someone-in-my-team-confirmed-childdirected-apps" />

<Accordion title="如何查看团队成员是否将某个应用标记为面向儿童？">

确认某个应用面向儿童后，可以通过以下两种方式查看确认记录：

* **通知中心：** 点击菜单栏中的通知图标![notificatin center icon.png](https://files.readme.io/5d0b4f1712ba0c05786025adf183e065a2144e1917542ebec0f302688dccb5eb-18473195561489.png)，找到相关确认通知。
* **审计日志：**
  1. 点击菜单栏中的用户菜单（电子邮件地址下拉菜单）。
  2. 选择 **Security Center（安全中心）。**
  3. 在 **Audit Log**（审计日志）部分，点击 **View Audit Log**（查看审计日志）。  
     在 **My Apps**（我的应用）服务下，可以查看相关确认详情。

</Accordion>

## 使用 AppsFlyer 合规工具

<div id="how-do-i-know-which-tool-to-use" />

<Accordion title="如何确定该使用哪种工具？">

如果您的应用面向儿童，或同时面向儿童和成人，可以从<Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">儿童应用合规指南</Anchor>推荐的工具中，选择符合相关法规要求的工具。更多 SDK 相关资源，详见本文末尾。 

#### 合规工具示例及其用途

<table><thead><tr><th>工具</th><th>iOS</th><th>Android</th><th>原始数据可用性</th></tr></thead><tbody><tr><td><span id="strict-sdk"></span><p><a href="./additional-sdk-integration-guide#strictmode-sdk" target="_blank">Strict SDK</a>： </p><p>确保 IDFA 不会发送至 AppsFlyer。通常建议面向儿童的应用使用此方式。</p></td><td><span><span>✓</span></span></td><td>- </td><td>仅限广告主查看</td></tr><tr><td><span id="standard-sdk-using-the-setdisableadvertisingidentifiers-api"></span><p>标准 SDK，使用 <a href="./android-oaid-implementation-in-the-sdk#opting-out-of-oaid-collection" target="_blank"><kbd>setDisableAdvertisingIdentifiers</kbd> 接口</a>：</p><p>确保 AAID（Google 安卓广告 ID）不会发送至 AppsFlyer。通常建议面向儿童的应用使用此方式。</p></td><td>- </td><td><span><span>✓</span></span></td><td>仅限广告主查看</td></tr><tr><td><span id="standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-specific-ad-networks"></span><p>标准 SDK + 年龄限制，针对<strong>特定</strong>广告平台使用 <a href="./additional-sdk-integration-guide#exclude-partners-from-getting-data" target="_blank"><kbd>setSharingFilterForPartners</kbd> 函数</a>： </p><p>阻止相关广告平台获取未达到年龄限制用户的数据\*。</p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>仅限特定广告平台可查看</td></tr><tr><td><span id="standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-all-ad-networks"></span><p>标准 SDK + 年龄限制，针对<strong>所有</strong>广告平台使用 <a href="./additional-sdk-integration-guide#exclude-partners-from-getting-data" target="_blank"><kbd>setSharingFilterForPartners</kbd> 函数</a>：</p><p>阻止所有广告平台获取未达到年龄限制用户的数据\*。</p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>仅限广告主查看</td></tr><tr><td><span id="skan-only"></span><p><a href="./skadnetwork-skan-solution-guide" target="_blank">仅使用 SKAN</a>：</p><p>确保广告 ID 不会与其他广告平台共享。</p></td><td><span><span>✓</span></span></td><td>- </td><td>仅限广告主查看</td></tr><tr><td><span id="sdkless-solutions-less-recommended"></span><p>不依赖 SDK 的方案（不太推荐）：</p><p><span>自行配置服务器，将数据发送至 AppsFlyer，作为通过 </span><span>SDK 发送数据的替代方式。</span></p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>取决于您的具体配置</td></tr><tr><td><span id="aggregated-advanced-privacy-framework-enforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners"></span><p><a href="./apply-aggregated-advanced-privacy-framework" target="_blank">Aggregated Advanced Privacy 框架</a>： </p><p>强制执行 Apple ATT 隐私级别，确保广告主和广告平台均<span>无法获取</span><span>用户级数据。</span></p></td><td><span><span>✓</span></span></td><td>- </td><td>广告主和广告平台均不可查看</td></tr><tr><td colspan="4"><span id="-when-applying-an-age-gate-block-userlevel-data-that-doesnt-fall-under-the-age-gate-is-available-in-raw-data-reports"></span><p>\* 应用年龄限制拦截后，不受年龄限制约束的用户级数据仍会显示在原始数据报告中。</p></td></tr></tbody></table>

</Accordion>

<div id="how-does-using-the-tools-in-the-guide-affect-attribution" />

<Accordion title="使用指南中的工具会对归因产生什么影响？">

<Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">AppsFlyer 合规解决方案指南</Anchor>提供了多种工具，每种工具的[控制粒度各不相同](#how-do-i-know-which-tool-to-use)。具体对归因的影响，取决于您选择实施哪种工具。

使用限制发送用户数据（例如设备 ID）的工具时，系统会采用其他归因方式，例如<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#probabilistic-modeling">概率建模</Anchor>或 <Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#install-referrer-android-only">Install Referrer（仅限 Android）</Anchor>。

不发送用户级数据的工具可视为保护隐私的方案，仍可获取汇总后的广告系列数据。

</Accordion>

<div id="i-dont-know-if-the-ad-network-im-working-with-is-compliant-what-do-i-do" />

<Accordion title="我不确定合作的广告平台是否合规，该怎么办？">

广告平台是否符合相关法律要求，有时并不容易判断。您可以直接向对方咨询这一问题。如果对方不合规，或您无法确认，可以选择不与其共享数据。您可以使用 <Anchor target="_blank" href="/marketers/zh/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">`setSharingFilterForPartners` 函数</Anchor>，指定需要阻止获取应用数据的广告平台。也可以使用该函数阻止所有广告平台。更多内容请参阅[合规工具示例及其用途](#合规工具示例及其用途)。

</Accordion>

<div id="do-i-need-to-implement-appsflyer-compliance-tools-if-the-ad-network-is-compliant" />

<Accordion title="如果广告平台已合规，我还需要实施 AppsFlyer 的合规工具吗？">

无论如何，都必须实施 AppsFlyer 的合规工具；具体选用哪些工具，取决于应用的目标受众。如果合作的广告平台已承诺，仅在 COPPA、GDPR、相关适用法律法规，或其他要求此类承诺的平台规则所允许的有限用途范围内，以数据处理者的身份处理您共享的数据，并已获得相应同意，您可以使用 **<Anchor target="_blank" href="/marketers/zh/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">`setSharingFilterForPartners` 函数</Anchor>**（“MediaSourceName”）。

这一原则适用于您合作的每一个广告平台。

</Accordion>

<div id="what-data-am-i-sending-to-ad-networks-what-control-do-i-have-over-this" />

<Accordion title="我向广告平台共享了哪些数据？ 我能对此进行哪些控制？">

非<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns">自归因网络（SRN）</Anchor>的广告平台，会通过回传（postback）接收您的数据。他们可以自行定义回传中包含哪些事件。系统默认会发送安装回传用于归因，而应用内事件回传仅在您<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">配置了特定事件</Anchor>需要发送时才会发送。 只要回传未被 SDK 拦截或限制，其中就可能包含与应用用户互动行为（安装、应用内事件、再互动）相关的用户级数据。

除回传之外，广告平台和代理商通过平台能够访问的数据<Anchor target="_blank" href="/marketers/zh/docs/manage-data-access-permissions">有限</Anchor>。

**如需查看通过回传发送给广告平台的具体数据：**

* 前往 **Reports**（报告） > **Raw Data Export**（原始数据导出）菜单，下载<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview#postbacks">回传报告</Anchor>

**如需控制您发送的数据：**

* 使用任意 SDK 合规工具，例如 <Anchor target="_blank" href="/marketers/zh/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">`setSharingFilterForPartners`</Anchor>，阻止或限制特定数据的发送。
* 选择将<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#default-postbacks">默认回传</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">应用内事件回传</Anchor>发送给谁——可以仅发送给归因该事件的广告平台，也可以发送给包括自然量在内的所有媒体渠道。

**如需控制 iOS 用户用户级归因数据的可用范围：**

* 使用 <Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">聚合高级隐私框架</Anchor> 来执行 Apple ATT 隐私级别。 OR这样即便用户级数据被用于归因，广告主和广告平台在 AppsFlyer 中也无法查看这些数据。汇总数据则不受此限制，可正常查看。

</Accordion>

<div id="do-i-need-the-sdk-if-my-app-is-childdirected-and-all-ad-networks-are-blocked" />

<Accordion title="如果我的应用面向儿童，并已阻止所有广告平台，还需要使用 SDK 吗？">

SDK 用于记录应用事件，例如安装、再互动和应用内事件。没有 SDK，就无法实现归因。您可以<Anchor target="_blank" href="/marketers/zh/docs/additional-sdk-integration-guide#用户隐私">通过 SDK 保护用户隐私</Anchor>，仅展示汇总数据。

</Accordion>

> 📄 **另请参阅**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/sdk-integration-overview">SDK 对接概述</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/apply-privacy-preserving-sdk-methods">SDK：隐私保护方法</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/additional-sdk-integration-guide#用户隐私">SDK：用户隐私设置</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/trust/privacy/">AppsFlyer 的隐私保护措施</Anchor>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%BF%B0 h_01HA20EGWDBSNAFZ7WNXJFFRRV=%E6%A6%82%E8%BF%B0 general-questions=%E6%B7%BB%E5%8A%A0%E9%9D%A2%E5%90%91%E5%84%BF%E7%AB%A5%E7%9A%84%E5%BA%94%E7%94%A8 h_01H9ZK2THJVFYQ49HHRYKZZNEK=%E6%B7%BB%E5%8A%A0%E9%9D%A2%E5%90%91%E5%84%BF%E7%AB%A5%E7%9A%84%E5%BA%94%E7%94%A8 h_01HHCE11YQX4DKV5BEW6QHKN55=what-steps-do-i-need-to-take-when-adding-a-childdirected-app when-adding-a-new-app-what-happens-after-i%E2%80%99ve-indicated-my-app-is-directed-towards-children=when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children h_01H9ZK2THJ225P38Q9CHQSTNY4=when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children if-ive-added-an-app-and-didn%E2%80%99t-define-it-as-directed-towards-children-can-i-change-this-later=if-ive-added-an-app-and-didn-t-define-it-as-directed-towards-children-can-i-change-this-later h_01HGZ5VAJHNW2K62ARTK43SG19=if-ive-added-an-app-and-didn-t-define-it-as-directed-towards-children-can-i-change-this-later h_01H9ZK2THJK5Q5EE3K38GTCCT7=how-can-i-see-if-someone-in-my-team-confirmed-childdirected-apps implementing-compliance-tools=%E4%BD%BF%E7%94%A8-appsflyer-%E5%90%88%E8%A7%84%E5%B7%A5%E5%85%B7 h_01HGZ5VAJHNJVM2ENFZ3DEAK42=%E4%BD%BF%E7%94%A8-appsflyer-%E5%90%88%E8%A7%84%E5%B7%A5%E5%85%B7 h_01HGZ4VWDBZJE8RWM05EJNH0S9=how-do-i-know-which-tool-to-use examples-of-compliance-tools-and-their-use=%E5%90%88%E8%A7%84%E5%B7%A5%E5%85%B7%E7%A4%BA%E4%BE%8B%E5%8F%8A%E5%85%B6%E7%94%A8%E9%80%94 h_01HHEED2AQTW7G0MJJZDZV2B09=%E5%90%88%E8%A7%84%E5%B7%A5%E5%85%B7%E7%A4%BA%E4%BE%8B%E5%8F%8A%E5%85%B6%E7%94%A8%E9%80%94 standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function%C2%A0for-all-ad-networks=standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-all-ad-networks aggregated-advanced-privacy-framework%C2%A0%0Aenforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners=aggregated-advanced-privacy-framework-enforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners h_01HKHX0GBS9EWMXMY387FQ95X1=how-does-using-the-tools-in-the-guide-affect-attribution h_01HH9EAB8T4Z6RMT8MVS77Q6BP=i-dont-know-if-the-ad-network-im-working-with-is-compliant-what-do-i-do h_01HKHWSQQKEDZBCDH0P8H760K6=do-i-need-to-implement-appsflyer-compliance-tools-if-the-ad-network-is-compliant h_01HHEEQ4AAEZSA0YB6V2DSRYXK=what-data-am-i-sending-to-ad-networks-what-control-do-i-have-over-this h_01HKJ843208PMQF1MCYCWMJC3H=do-i-need-the-sdk-if-my-app-is-childdirected-and-all-ad-networks-are-blocked h_01HE7TQV7VDSEX3E7RTKAHBMNN=%E5%8F%A6%E8%AF%B7%E5%8F%82%E9%98%85" />
