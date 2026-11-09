---
title: '[封闭测试 - 特殊访问] 设置您的 ESP 与 AppsFlyer 的集成'
metadata:
  keywords:
    - Premium
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2024-07-24T14:10:54Z'
  edited_at: '2026-10-14T10:11:08Z'
  id: 26967438815377
  locale: zh-cn
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/zh-cn/articles/26967438815377
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 设置与 AppsFlyer 的 ESP 集成，以在您的电子邮件活动中实现无缝和安全的深度链接，从而提高用户参与度和转化率。

## <Image alt="ESP 最终主要知识库图像.png" src="https://files.readme.io/f14a193bb8d303adb93c01b33dcafba9053359fd92a187378cd324544a94dc88-27434531852049.png" width="613px" />

<div id="about-the-appsflyer-esp-integration" />

## 关于 AppsFlyer ESP 集成

营销人员通常使用电子邮件服务提供商 (ESP) 来发送大规模电子邮件活动。尽管这应该是一个简单的过程，提供可预测的用户旅程，但情况往往并非如此。原因在于典型的 ESP 如何处理其分析，这往往会破坏深度链接并对移动用户体验产生负面影响。因此，用户有时会被引导到移动网站而不是您的应用程序，从而降低转化的可能性。

AppsFlyer 通过 ESP 集成解决方案解决了这个问题，使 AppsFlyer 能够充当 ESP 服务器与您的域名之间的中介。通过代理机制，AppsFlyer可为您的域名提供必要的关联文件（如AASA或Asset Links），从而实现稳定可靠的深度链接跳转体验。此外，AppsFlyer 解决方案将测量数据发送回您的 ESP，使您能够有效监控电子邮件分析。

设置与 AppsFlyer 的 ESP 集成，以在您的电子邮件活动中实现顺畅和安全的深度链接体验，以获得最佳的移动用户参与度和转化率。

<div id="set-up-the-integration" />

## 如需设置对接：

<span id="h_01J3JHFXRP57VS9D22FEWS2JZW"></span>本节描述如何设置您的 ESP 与 AppsFlyer 的集成。

<div id="prerequisites" />

### 前期准备

在开始设置与 AppsFlyer 的 ESP 集成之前，您需要拥有一个支持的 ESP* 的帐户。以下项目将是必需的：

* 一个新的 **点击跟踪域** (在 [步骤 1.](#step-1-create-a-onelink-template-for-your-email-campaign) 中描述）
* **ESP 端点**：该端点由 ESP 提供，以便您可以将点击路由到其服务器。ESP 端点结构示例：esp.endpoint.com。
* **特定 ESP 集成要求：**
  * **Emarsys** - 请向您的 Emarsys 客户成功经理请求启用 HTTP 重定向。
  * **蓝移** - 请向您的蓝移客户成功经理询问  
    将点击的HTTP响应代码更改为302（从默认的307）。

**要设置集成，请按照以下步骤操作：**

<div id="step-1-create-a-onelink-template-for-your-email-campaign" />

<Accordion title="第1步：在您的ESP平台上创建一个点击跟踪域（IT / 系统管理员任务）">

点击跟踪域（CTD）是出现在电子邮件消息中的URL的域组件。   
它由一个子域和您的主域组成，例如mail.yourbrand.com。不同的ESP可能将其称为链接品牌、跟踪器域、点击域、链接重写、点击跟踪或白标。

**创建一个新的CTD是强制性的**，即使您已经在使用现有的。这确保当前在线电子邮件活动的流量没有影响。

<div id="notes" />

> 📘 **说明**
>
> * SSL证书将由AppsFlyer处理（在第3步中）。
> * 在此阶段，电子邮件链接可能不会被保护，这意味着URL前缀将是HTTP而不是HTTPS。这将在[第5步中解决。](#h_01JMYDQGPF3B9GNH0RY27JW3E4)）

</Accordion>

<div id="h_01JMYD02VRGT8353RDBARRPJ2M" />

<div id="step-2-use-a-oneLink-template-for--your-email-campaign" />

<Accordion title="第2步：为您的电子邮件活动使用OneLink模板">

创建一个<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#创建onelink模板">OneLink模板</Anchor>并在"**应用安装时**"下配置通用链接/应用链接。此模板将在稍后用于为您的电子邮件活动创建OneLink链接。

*如果您已经配置了一个现有的OneLink模板以启用通用链接/应用链接，您可以使用它。

</Accordion>

<div id="step-3-set-your-esp-integration-in-appsflyer" />

<Accordion title="第3步：在AppsFlyer中设置您的ESP集成">

现在是时候在AppsFlyer中设置您的ESP集成了。请注意，此步骤和下一个步骤（"[第4步。配置您的应用](#step-2-configure-your-app-developer-task)")可以同时设置。

**在 AppsFlyer 中设置您的 ESP 集成：**

1. 在 **AppsFlyer** 中，从侧边菜单选择 **Engage** > **ESP 集成**。

<Image align="center" alt="从 Engage 点击 ESP 集成.png" src="https://files.readme.io/7b731446ce6158d5033020b63be5f386105e7899a8c1b291aa3cb13662a59ee5-27063684942481.png" width="196px" />

2. 选择您的 ESP。

<Image align="center" alt="select ESP.png" src="https://files.readme.io/526fed3aaf1e6fdbf2404243619159984e298752fdf5913fd3a65cc5a2ed9e1d-27086632495761.png" width="482px" />

3.选择您想用于电子邮件活动的 OneLink 模板，然后点击 **下一步**。

<Image align="center" alt="select OneLink template.png" src="https://files.readme.io/4f96b999740be8596a424ce9108a8f702bda2a7ed025ec1869c553393432d87d-27086632499729.png" />

4.确保您在所选的 ESP 上有一个有效的帐户。

您需要从您的 ESP 获取以下内容：

* 您在第 1 步中创建的点击跟踪域。
* ESP 端点

点击**下一步**。

5.输入您的点击跟踪域和 ESP 端点，然后点击 **验证连接**。这验证了点击跟踪域指向您输入的端点。

<Image align="center" alt="输入您的 ctd 和 esp 端点.png" src="https://files.readme.io/d068b7de020bed7ba979b25e0fe866c40a118b00bbfde06a36a4c097485ac885-27086632503441.png" />

添加完毕后，点击**下一步**。

6.将链接流量发送到AppsFlyer

a.<strong>复制并将 AppsFlyer 中的定制预制说明发送给您的 IT 或域管理员。</strong>他们需要通过使用 AppsFlyer 提供的新域更新您的 DNS CNAME 记录，将您的电子邮件活动流量从 ESP 服务器重新路由到 AppsFlyer 服务器。

因此，每次点击链接时，点击将被重定向到 AppsFlyer，AppsFlyer 将其重定向到 ESP 端点。

<Image align="center" alt="点击从 Af 到 ESP 的图像.png" src="https://files.readme.io/8a53fa7e8e2574246ea6b1344cfec0ac2d8f319bb181f6956ecb6db5b05cd0c5-26982377140369.png" width="374px" />

b.复制并发送说明后，点击 **完成**。

您的 ESP 集成已创建。

请注意：

* - 您的ESP对接状态为“处理中”，该对接仅在CNAME记录映射完毕后方可生效。
* - 映射完毕后，新的对接最多需要24小时方可生效并进入活跃状态。

</Accordion>

<div id="step-2-configure-your-app-developer-task" />

<Accordion title="第4步：配置您的应用程序（开发者任务）">

让您的开发者对您的应用程序进行以下配置：

* [配置您的应用以支持关联域](#配置您的应用以支持关联域)
* [配置您的应用以支持深度链接](#配置您的应用以支持深度链接)
* [配置您的应用以处理网页链接和应用链接](#配置您的应用以处理-web-链接和应用链接)

<div id="configure-your-app-to-support-associated-domains" />

#### **配置您的应用以支持关联域**

AppsFlyer 为您的应用托管应用关联文件，以启用 <Anchor target="_blank" href="/marketers/zh/docs/appsflyer-knowledge-base-glossary#universal-links">Universal Links (iOS)</Anchor> 或 <Anchor target="_blank" href="/marketers/zh/docs/appsflyer-knowledge-base-glossary#android-app-link">App Links (Android)</Anchor>。

**要配置您的应用以访问文件：**

**对于iOS**  
**前提条件：** SDK 来自 <Anchor target="_blank" href="/marketers/zh/docs/appsflyer-ios-sdk-release-notes">v6.12.3</Anchor>  
配置您的应用以从电子邮件消息启用通用链接到您的应用。  
了解有关配置 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">Universal links</Anchor> 的更多信息。  
请注意<strong>：</strong>点击域应添加到已在关联域中定义的当前域。

**对于Android**  
**前提条件：** SDK 来自 <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.appsflyer/af-android-sdk">v6.12.5</Anchor>  
配置您的应用以从电子邮件消息启用 Android 应用链接到您的应用。了解有关配置 Android <Anchor target="_blank" href="/marketers/zh/docs/appsflyer-knowledge-base-glossary#universal-links">App Links</Anchor> 的更多信息。  
请注意<strong>：</strong>点击域应添加到已在 Android Manifest 中定义的当前域。


<div id="configure-your-app-to-support-deep-linking" />

#### **配置您的应用以支持深度链接**

当点击应用链接或通用链接时，应用应打开。

**要使应用能够提取点击记录域后面的 OneLink 并解析深度链接：**

1. 向 SDK API resolveDeepLinkURLs 提供点击记录域。此 API 必须在 SDK 初始化之前调用。

* 对于 IOS，请遵循这些 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_esp_2_setup">说明</Anchor>.
* 对于 Android，请遵循以下 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_esp_2_setup#flow-description">说明</Anchor>。

2.使用 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">统一深度链接 API</Anchor> 获取深度链接参数并处理深度链接数据。


<div id="if-i-have-the-appsflyer-esp-integration-and-sdk-implemented-for-basic-onelink-deep-linking-do-i-need-to-add-both-the-onelink-domain-and-the-esp-click-tracking-domain-to-ios-associated-domains" />

<div id="do-i-need-to-create-an-ssl-certificate-at-any-point" />

<div id="faq" />

<div id="configure-your-app-to-handle-weblinks-and-application-links" />

#### **配置您的应用以处理 Web 链接和应用链接**

提供的代码旨在规范电子邮件活动中包装链接的功能，特别是针对两种类型：旨在打开网站的 Web 链接，以及通过通用链接或应用链接打开应用的链接。  
有关更多开发者信息，请参阅以下指南：

* iOS深度链接
* 安卓深度链接

</Accordion>

<div id="h_01JMYDQGPF3B9GNH0RY27JW3E4" />

<Accordion title="第5步：确保在您的 ESP 平台上启用 SSL 点击跟踪">

执行电子邮件测试以验证链接状态。   
如果 CTD 链接被识别为 HTTP，请联系 ESP 团队以启用 SSL 点击跟踪。   
这将确保所有 HTTP 链接自动转换为 HTTPS。

您可以在联系您的 ESP 时使用以下示例消息文本：

大家好！  
您能否为 CTD XXX 启用 SSL 点击跟踪？目前设置为 HTTP 而不是 HTTPS。   
感谢您对此更新的协助。

</Accordion>

<div id="step-4-customize-the-onelink-link-for-your-email-campaign" />

<Accordion title="第6步：在 AppsFlyer 中为您的电子邮件活动自定义 OneLink 链接">

**要为您的活动创建和自定义 OneLink 链接：**

1. 在 AppsFlyer 中，在您之前创建的 OneLink 模板内的 OneLink 管理页面（或手动）创建一个“电子邮件到应用” OneLink 链接。这是您将在电子邮件活动中使用的链接，将根据您的规格归因和重定向用户。了解如何创建 <Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#创建onelink链接">OneLink 链接</Anchor>。

<Image align="center" alt="email-to-app.png" src="https://files.readme.io/4e30986e039ed4cc13b9963ef3d1bb7b933061176bed812dced45a7240023d54-27082280943761.png" width="652px" />

**推荐方法：** 在 ESP 电子邮件活动和该活动中使用的 AppsFlyer OneLink 链接中使用相同的活动名称。

</Accordion>

<div id="step-5-test-the-link" />

<Accordion title="第5步：在您的ESP平台上测试集成">

**要测试您创建的OneLink链接的集成：**

在您创建的测试电子邮件中插入OneLink URL，并使用ESP电子邮件编辑器发送给自己。

* 在您的移动设备上，打开电子邮件并点击链接。如果您已安装该应用程序，应用程序将打开，并且您将深度链接到相关内容。此外，移动点击应出现在AppsFlyer仪表板中，归因于提供的媒体来源和活动，以及在您的ESP分析仪表板中。
* 点击网页链接并验证它是否重定向到正确的目的地。

一旦测试成功，您就可以开始使用了。

</Accordion>

<div id="step-6-use-the-link-in-your-email-campaigns-then-measure-the-results-use-the-link-confidently-in-your-email-campaigns" />

<Accordion title="第5步：在您的电子邮件活动中自信地使用该链接">

做得好！您现在可以在电子邮件活动中使用链接。之后，您可以在ESP或AppsFlyer仪表板中查看活动结果。

</Accordion>

*此集成支持的ESPs包括：Blueshift、Braze、CleverTap、Customer.io、Emarsys、Expert Sender、Klaviyo、MailExpress、MailGun、Moengage、RDStation、Reteno、Sailthru、Sendgrid、Sparkpost等。查看完整的<Anchor target="_blank" href="/marketers/zh/docs/email-service-provider-esp-integration-guide">列表</Anchor>.

<div data-zendesk-anchors="overview=%E5%85%B3%E4%BA%8E-appsflyer-esp-%E9%9B%86%E6%88%90 h_01J6RXTXCS7WC0P5X4J96T8JAP=%E5%85%B3%E4%BA%8E-appsflyer-esp-%E9%9B%86%E6%88%90 h_01J3JHJCCASM6E5QYJB5VHQ8HK=%E5%85%B3%E4%BA%8E-appsflyer-esp-%E9%9B%86%E6%88%90 set-up-your-esp-integration-with-appsflyer=%E5%A6%82%E9%9C%80%E8%AE%BE%E7%BD%AE%E5%AF%B9%E6%8E%A5 h_01J3JHFRGA6BTMWSK7EEEVGS6T=%E5%A6%82%E9%9C%80%E8%AE%BE%E7%BD%AE%E5%AF%B9%E6%8E%A5 prerequisites=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 h_01J3JJ74GYF5AJT9R2P2CXDXE1=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 h_01J3W0Z161XE7BKMMR62SEEZN7=step-1-create-a-onelink-template-for-your-email-campaign h_01JMYJG3CTGE9Y3SBFAECV326G=%E8%AF%B4%E6%98%8E step-2-use-a-oneLink-template-for-%20your-email-campaign=step-2-use-a-oneLink-template-for--your-email-campaign h_01JMYD02VRGT8353RDBARRPJ2M=step-2-use-a-oneLink-template-for--your-email-campaign h_01J3W0Z161T0D075HPE3Y8H3J4=step-3-set-your-esp-integration-in-appsflyer h_01J3W0Z1613XPYM75GH65R793W=step-2-configure-your-app-developer-task configure-your-app-to-support-associated-domains=%E9%85%8D%E7%BD%AE%E6%82%A8%E7%9A%84%E5%BA%94%E7%94%A8%E4%BB%A5%E6%94%AF%E6%8C%81%E5%85%B3%E8%81%94%E5%9F%9F h_01J3W8XR5QS227XNCD453RWYZ9=%E9%85%8D%E7%BD%AE%E6%82%A8%E7%9A%84%E5%BA%94%E7%94%A8%E4%BB%A5%E6%94%AF%E6%8C%81%E5%85%B3%E8%81%94%E5%9F%9F configure-your-app-to-support-deep-linking=%E9%85%8D%E7%BD%AE%E6%82%A8%E7%9A%84%E5%BA%94%E7%94%A8%E4%BB%A5%E6%94%AF%E6%8C%81%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 h_01J3WS4QWMRT8KSW6J3QHXM9TQ=%E9%85%8D%E7%BD%AE%E6%82%A8%E7%9A%84%E5%BA%94%E7%94%A8%E4%BB%A5%E6%94%AF%E6%8C%81%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 h_01J3W8Y7FMSWPG7MFF6FMSXFM3=%E9%85%8D%E7%BD%AE%E6%82%A8%E7%9A%84%E5%BA%94%E7%94%A8%E4%BB%A5%E6%94%AF%E6%8C%81%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 ::250c928e=%E9%85%8D%E7%BD%AE%E6%82%A8%E7%9A%84%E5%BA%94%E7%94%A8%E4%BB%A5%E5%A4%84%E7%90%86-web-%E9%93%BE%E6%8E%A5%E5%92%8C%E5%BA%94%E7%94%A8%E9%93%BE%E6%8E%A5 configure-your-app-to-handle-weblinks-and-application-links=%E9%85%8D%E7%BD%AE%E6%82%A8%E7%9A%84%E5%BA%94%E7%94%A8%E4%BB%A5%E5%A4%84%E7%90%86-web-%E9%93%BE%E6%8E%A5%E5%92%8C%E5%BA%94%E7%94%A8%E9%93%BE%E6%8E%A5 h_01J3WS4QWMSKZ33APWFR8CG5TZ=%E9%85%8D%E7%BD%AE%E6%82%A8%E7%9A%84%E5%BA%94%E7%94%A8%E4%BB%A5%E5%A4%84%E7%90%86-web-%E9%93%BE%E6%8E%A5%E5%92%8C%E5%BA%94%E7%94%A8%E9%93%BE%E6%8E%A5 h_01J3W8ZMHSXQGJPQEVR62Q28X9=%E9%85%8D%E7%BD%AE%E6%82%A8%E7%9A%84%E5%BA%94%E7%94%A8%E4%BB%A5%E5%A4%84%E7%90%86-web-%E9%93%BE%E6%8E%A5%E5%92%8C%E5%BA%94%E7%94%A8%E9%93%BE%E6%8E%A5 h_01J3W0Z1616GFFYCS7WPTNCCHT=step-4-customize-the-onelink-link-for-your-email-campaign h_01J3W0Z161M9NDXAN0KZFA9J4G=step-5-test-the-link h_01J3W0Z161RAYTKH3V9VBAADBM=step-6-use-the-link-in-your-email-campaigns-then-measure-the-results-use-the-link-confidently-in-your-email-campaigns" />
