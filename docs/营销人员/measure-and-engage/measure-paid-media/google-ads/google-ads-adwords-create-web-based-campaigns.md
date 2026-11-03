---
title: Google Ads（AdWords）网页广告的投放配置说明
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
  created_at: '2024-05-16T09:12:15Z'
  edited_at: '2026-10-14T10:00:31Z'
  id: 25096718837137
  locale: zh-cn
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/zh-cn/articles/25096718837137
---
> **概览：** 为您的网站应用设置 Google Ads 集成，以便通过离线转化 API (OCI) 向 Google 发送网络转化信号。

## 概览

AppsFlyer 支持与 Google Ads 集成（`googleads_int` ) 通过 Google Offline Conversion API (OCI) 获取网站应用营销活动和报告转化数据。

在本文中，您将学习如何在 AppsFlyer 和 Google Ads 中设置网络广告系列，以定位与 Google Ads 互动并在您的网站上进行转化的用户。

当用户点击 Google 广告并访问您的网站时，广告系列流程就开始了。当用户完成网站事件（例如购买或注册）时，AppsFlyer 会通过 OCI 向 Google Ads 发送转化信号。谷歌利用这些数据来优化广告投放和衡量广告系列效果。

> 📄 **另请参阅**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/web-performance-measurement-overview">AppsFlyer 网络归因分析 - 概述</Anchor>

### 前期准备

在为网站应用广告系列启用 Google Ads 集成之前，请确保您已完成以下操作：

* 在 AppsFlyer 中设置的网站应用程序
* 部署在您网站上的 AppsFlyer Web SDK
* 拥有相应角色或权限的 AppsFlyer 帐户

### 如何设置 Google Ads 网络广告系列

该装置分为两部分：

1. 在AppsFlyer中设置Google Ads对接 （必须完成）
2. 在 Google Ads 中设置广告系列（必需）

## 在 AppsFlyer 中设置 Google Ads 集成

首先激活 Google Ads 网络广告系列集成，并设置 AppsFlyer 向 OCI 发送的回传。

<div id="step-1-activate-the-integration" />

<Accordion title="第1步：激活对接：">

1. 在AppsFlyer面板的左侧菜单栏中点击**协作** > Partner Marketplace。
2. 搜索并选择**Google Ads Web**。
3. 点击**设置对接**，然后界面会跳转到活跃对接设置页面。
4. 在应用下拉菜单中，选择网页应用。
5. 在**渠道对接**选项卡中，打开**启用该渠道**开关。

   > 📘 **注意**
   >
   > 在您与该渠道合作期间，请确保该开关总是处于打开（即启用）状态。

6. **高级匹配数据共享：** 启用此功能，即可与 Google 共享高级匹配字段，例如哈希电子邮件、哈希电话号码、哈希名字和哈希姓氏（如果这些字段包含在发送给 AppsFlyer 的活动信息中）。详情请见：<Anchor target="_blank" href="/marketers/zh/docs/advanced-matching-data-sharing">高级匹配数据共享</Anchor>。
7. 输入您的**Customer ID**。您可以从Google Ads Manager中获取该ID：
   1. 登入您的Google Ads账户。
   2. 点击界面右上角的Google账户图标，然后向下滚动到Customer ID部分。
   3. 请完成以下任一操作：
      * 如果您有多个Google Ads账户同时为相关应用投放广告，必须使用经理账号（MCC）的Customer ID才能进行跨账户的转化监测。将 MCC ID（而不是特定帐户的客户 ID）粘贴到“客户 ID”字段中，同时粘贴到“MCC 客户 ID”文本框中（两个框中的 ID 相同）。 有关更多信息，请参阅<Anchor target="_blank" href="https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC">Google 关于配置 MCC 帐户的说明</Anchor>。
      * 如果您只使用一个 Google Ads 帐户来投放广告，只需将帐户 ID 粘贴到“客户 ID”文本框中，并将 MCC 客户 ID 文本框留空即可。
8. 如需允许AppsFlyer将转化数据上传到Google Ads，请点击**使用Google登录**。
9. 选择相关经理账号（即您在第7步中获取到Customer ID的MCC账号）中的管理员。
10. 点击**Allow**。

    > 📘 **注意**
    >
    > 在您通过Google登录并按照下方步骤允许AppsFlyer获取token后，*令牌缺失*的错误提示将不再显示。如果在登录后错误仍然存在，请验证您的令牌是否具有所需的权限。


</Accordion>

<div id="step-2-set-inapp-event-postbacks" />

<Accordion title="第2步：应用内事件回传">

将您的网站事件与 Google Ads 转化操作关联起来。AppsFlyer 通过 OCI 将这些事件发送给 Google，以支持基于转化率的优化。

> 📘 **注意**
>
> 对于网站应用而言，所有事件都是 Web 事件，没有安装事件。您希望 Google 进行优化的每个事件都必须映射到相应的 Google Ads 转化操作 ID。

1. 打开**应用内事件回传**开关。
2. 如有需要，请设置**应用内事件回发窗口**。该窗口在用户首次网站转化事件发生时打开（相当于移动设备的安装日期）。
3. 点击**添加事件**。
4. 在**AppsFlyer 活动**列中，选择要发送的网站活动（例如，`purchase` ，`sign_up` ）。

   > 📘 **注意**
   >
   > 参观活动除外。此下拉菜单中仅提供自定义 Web 事件。

5. 在 **“映射到合作伙伴事件”** 列中，输入 Google Ads**转化操作 ID** 。在此之前，您需要在 Google Ads 中创建转化操作（请参阅下面的第 2 部分中的步骤 2）。查找转化操作 ID：
   * 在 Google Ads 中，打开转化操作页面。
   * 打开**Details**选项卡。
   * 然后在该页面URL中复制`ctid=*`查询参数的值。例如，如果`ctid=123456789`， 进入`123456789`。
6. 在 **“用户来源”** 列中，选择 **“仅限此合作伙伴”** ，以仅发送归因于 Google Ads 的事件。
7. 在 **“包含”** 列中，选择是否在回传中包含收入值。
8. 点击**保存对接**。

</Accordion>

## 在 Google Ads 中设置网站转化广告系列

<div id="step-1-set-the-campaign-type-objective-and-goals" />

<Accordion title="第1步：设置投放类型、投放目标和转化目标">

1. 登入Google Ads并创建一个广告系列。
2. 选择投放目标（campaign objective）。
   * 除 **“应用推广”** 外，所有目标均适用，“应用推广”仅适用于移动应用推广活动。
   * 我们建议根据特定的网站转化事件，优化**销售**或**潜在客户**。
3. 选择您的**转化目标**。默认情况下，您会看到账户级别的目标。您可以保留这些内容，也可以删除不相关的内容。
   * 如果您要优化的目标未列出，请创建自定义转化操作（请参阅下面的步骤 2）。
4. 选择所需的campaign type（广告系列类型）
   * 除**购物功能**外，所有类型均适用；购物功能需要产品目录和已验证的域名。

</Accordion>

<div id="step-2-create-conversion-actions" />

<Accordion title="第2步：创建转化操作">

对于您在 AppsFlyer 中映射的每个网站事件，在 Google Ads 中创建相应的转化操作。创建完成后，复制转化操作 ID 并将其粘贴到上一节中的 AppsFlyer 事件映射中。

1. 在 Google Ads 中，从侧边菜单中打开 **“目标”>“转化”>“摘要”** 。
2. 点击 **+ New conversion action**。
3. 选择 **“导入”** 作为转换数据源，然后选择以下任一选项：
   * **Manual import using API or uploads > Track conversions from clicks**（通过API或上传手动导入 > 跟踪点击带来的转化）。
   * <strong>CRM, files, or other data sources > Track conversions from clicks</strong>（CRM、文件或其他数据来源 > 跟踪点击带来的转化），然后在<em>Data source（数据来源）</em>部分下选择Skip this step and set up data source later（跳过这一步，之后再设置数据来源）。
4. 点击**继续**，进入下一步。
5. 在**Conversion goal**（转化目标）中选择一个转化操作类别。
6. 输入**Conversion name**（转化名称）。

   > 🚧 **重要提示！**
   >
   > 如需在使用GCLID的基础上，通过GBRAID/WBRAID搭配Offline Conversions API，请确保转化操作中的**Count**字段设置为**Every**（默认），而非*One*。

7. 输入**转换名称**，然后单击 **“添加”** 。

   > 📘 **注意**
   >
   > 如果您只需针对某一个具体转化行为来优化投放，请仅在选定转化类别中添加这一个转化操作。举例来说，如果您希望自己的广告系列针对First open（首次打开）进行优化，请确保该操作是您选定的转化类别中所包含的唯一一个转化操作。然后，您就可以在创建相关广告系列时将这个转化类别选作您的转化目标，用于优化投放。

8. 点击**Save and continue** > **Done**，此时您尚未设置数据来源（data sources）。新创建的转化操作初始状态可能显示为“Inactive（未激活）”，在实际数据传入后会自动变为“Active（激活）”。
9. 找到新建转化操作的ID，将该操作映射到AppsFlyer的回传事件。在相关转化目标的**Summary**页面中，点击您创建的转化操作，并复制转化操作页面的URL中`ctid=*`查询参数的值。
10. 进入AppsFlyer后台，在“渠道对接”配置部分找到您想要让Google进行优化的AF回传事件，然后将`ctid`的值粘贴到**渠道映射事件**一栏。详情请见应用内事件回传

</Accordion>

<div id="step-3-set-the-campaigns-final-url" />

<Accordion title="第3步：设置活动最终网址">

Google<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6080568?sjid=9660882197247124000-EU">将最终网址定义</Anchor>为“用户点击您的广告后访问的网站网页的网址，也称为‘着陆页’”。

1. 进入Google Ads后台，打开**Campaigns** > ads页面。
2. 找到您需要的广告，点击该行中的编辑图标。
3. 在 **“最终网址”字段**中，输入您的目标网页的网址。

   > 🚧 **重要提示！**
   >
   > 切勿将最终到达网址设置为任何AppsFlyer网址（即OneLink链接或单平台归因链接），否则会导致您的广告系列被拒审。请仅使用直接网址，不要使用重定向。
   >
   > 您可以将AF归因参数添加到最终到达网址（Final URL）中，并将其映射到Google的ValueTrack参数，如`af_c_id={campaignid}`。当用户点击 Google 广告并加载着陆页后，这些参数就会显示在页面上。如需进一步了解可用的ValueTrack参数，请参考<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348">Google提供的说明文档</Anchor>。
   >
   > 使用场景示例:
   >
   > ```http
   > https://example.com?product=1234&af_c_id={campaignid}
   > ```


> 📘 **注意**
>
> Google Web Ads 广告系列每次互动可以使用两个网址：最终网址和跟踪模板网址。但是，对于广告目标为网站的网站应用广告系列，跟踪模板 URL 不是必需的。只有当营销活动目标是网页到移动设备时才需要跟踪模板 URL。有关更多信息，请参阅[Google Ads 网络到应用广告系列文章](/docs/google-ads-adwords-create-web-based-campaigns)。

</Accordion>

## 查看网络归因数据

Google Ads 广告系列的网络归因数据可在跨平台控制面板和原始数据导出文件中获取：

* **可在**在<Anchor target="_blank" href="/marketers/zh/docs/my-dashboards#crossplatform-dashboard">跨平台控制面板</Anchor>中，网页和应用程序数据并排显示，让您可以统一查看跨平台的广告系列效果。
* 原始数据导出在<Anchor target="_blank" href="/marketers/zh/docs/raw-data-export-page">“原始数据导出”页面</Anchor>中也可以找到网络归因数据。
  * 这`media_source`田野表演`googleadwords_int`归因于谷歌广告的网络事件。

> 📘 **注意**
>
> 这种统一的报告视图可让您在一个地方分析网站和应用程序的广告系列效果，包括完整的移动和网站成本报告。

## 利用网络成本衡量网络归因数据

要在信息中心和<Anchor target="_blank" href="/marketers/zh/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">成本 ETL 报告</Anchor>中查看 Google Ads 的网络归因数据和网络成本数据的完整效果视图，请确保您拥有<Anchor target="_blank" href="/marketers/zh/docs/roi360-onboarding-guide#roi360简介">ROI360 套件</Anchor>，并完成以下设置：

1. 通过以下方式将成本连接到您的网站应用程序`googleadwords_int`（并非通过）`googleads_int` ）从 **“成本”** 选项卡或 **“成本设置”** 页面。有关如何连接成本的更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#启用cost-api">设置 ROI360 成本 API 以测量成本数据</Anchor>。
2. 请提供活动 ID（`af_c_id` ）在着陆页 URL 中。确保 URL 包含完整的广告系列层级结构，以便以最精细的级别查看与网络归因匹配的成本、点击次数和展示次数。

## 应用内事件回传问题排查

如果活动数据未显示在 Google Ads 中，请在联系支持人员之前检查以下各项。

<div id="set-token-permissions" />

<Accordion title="设置令牌权限">

进入Google Ads后台，检查您的Access Token是否具有必要权限，可以上传离线转化：

1. 进入Google Developers Console.。
2. 确保`uploadClickConversions`具有以下OAuth权限范围：`https://www.googleapis.com/auth/adwords`
3. 在 AppsFlyer的对接选项卡中，点击**使用 Google登录**。
4. 选择MCC账户的管理员账户。
5. 点击**Allow**。

</Accordion>

<div id="mcc-customer-id" />

<Accordion title="MCC账号的Customer ID">

如果您有多个Google Ads账户同时为相关应用投放广告，必须使用经理账号（MCC）的Customer ID。详情请见<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6139186">Google提供的MCC账号配置说明</Anchor>。

</Accordion>

<div id="conversion-action-id" />

<Accordion title="转化操作ID">

确保回传中的应用内事件映射到正确的转化操作ID（Conversion Action ID）。如需在Google Ads中查找转化操作ID，请参考[此处说明](#step-2-create-conversion-actions)。创建转化操作。

</Accordion>

## 特性与限制

| 特点 | 说明 |
| --- | --- |
| 点击和展示 | 网络广告活动的点击量和曝光量需要<Anchor target="_blank" href="/marketers/zh/docs/roi360-onboarding-guide">ROI360 订阅</Anchor>。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A7%88 h_01KNM00RR7V9BAA2BSPDECHC9F=%E6%A6%82%E8%A7%88 h_01KQC2B644Y44631ZQKC1HPEF4=%E5%8F%A6%E8%AF%B7%E5%8F%82%E9%98%85 prerequisites=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 h_01KNM00RR7H7A9CE06APEZSXKR=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 how-to-set-up-a-google-ads-web-campaign=%E5%A6%82%E4%BD%95%E8%AE%BE%E7%BD%AE-google-ads-%E7%BD%91%E7%BB%9C%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97 h_01KNM00RR77P8VD2YJ2R7DZBVX=%E5%A6%82%E4%BD%95%E8%AE%BE%E7%BD%AE-google-ads-%E7%BD%91%E7%BB%9C%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97 set-up-the-google-ads-integration-in-appsflyer=%E5%9C%A8-appsflyer-%E4%B8%AD%E8%AE%BE%E7%BD%AE-google-ads-%E9%9B%86%E6%88%90 h_01KNM00RR7E8MFSTGYKFEJDS1C=%E5%9C%A8-appsflyer-%E4%B8%AD%E8%AE%BE%E7%BD%AE-google-ads-%E9%9B%86%E6%88%90 h_01KNM00RR71ZXB72H8X1YXWKED=step-1-activate-the-integration h_01KNM00RR84CCGBR3T5WG7C5VW=%E6%B3%A8%E6%84%8F h_01KNM00RR86C5VKBVTA9X6QRAS=%E6%B3%A8%E6%84%8F-1 h_01KNM00RR8BCJTMPZ29C841BY1=step-2-set-inapp-event-postbacks h_01KNM00RR8PSJ7FEAP7MMEJ1XG=%E6%B3%A8%E6%84%8F-2 h_01KNM00RR89XJ0BZKFDXVC4860=%E6%B3%A8%E6%84%8F-3 set-up-a-web-conversion-campaign-in-google-ads=%E5%9C%A8-google-ads-%E4%B8%AD%E8%AE%BE%E7%BD%AE%E7%BD%91%E7%AB%99%E8%BD%AC%E5%8C%96%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97 h_01KNM00RR8SAS3TM1NG5DC58TF=%E5%9C%A8-google-ads-%E4%B8%AD%E8%AE%BE%E7%BD%AE%E7%BD%91%E7%AB%99%E8%BD%AC%E5%8C%96%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97 h_01KNM00RR8S24AG7FMN6067PZ2=step-1-set-the-campaign-type-objective-and-goals h_01KNM00RR8H1ZFSHFT0DVB11GN=step-2-create-conversion-actions h_01KNM00RR8EV8XY02YJFV5XSX8=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01KNM00RR8N96SNP1YK0CTN6YZ=%E6%B3%A8%E6%84%8F-4 h_01KNM00RR82NZSKB7K06HCP1VE=step-3-set-the-campaigns-final-url h_01KNM00RR8EP6J43G29Q8VVA5B=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 h_01KNM00RR8A704MKGVVC6MQ2KN=%E6%B3%A8%E6%84%8F-5 view-web-attribution-data=%E6%9F%A5%E7%9C%8B%E7%BD%91%E7%BB%9C%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE h_01KNM00RR8EYJAX2KRGCM65E9M=%E6%9F%A5%E7%9C%8B%E7%BD%91%E7%BB%9C%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE h_01KNM00RR86Q2GTHVNC505KCXZ=%E6%B3%A8%E6%84%8F-6 measure-web-attribution-data-with-web-cost=%E5%88%A9%E7%94%A8%E7%BD%91%E7%BB%9C%E6%88%90%E6%9C%AC%E8%A1%A1%E9%87%8F%E7%BD%91%E7%BB%9C%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE h_01KNM00RR9TF8JRTJXWN23MF1S=%E5%88%A9%E7%94%A8%E7%BD%91%E7%BB%9C%E6%88%90%E6%9C%AC%E8%A1%A1%E9%87%8F%E7%BD%91%E7%BB%9C%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE troubleshooting-in-app-event-postbacks=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5 h_01KNM00RR9Z0BM5EE62M17EE0F=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5 h_01KNM00RR9CJJQAP4GAXZ9KK8N=set-token-permissions h_01KNM00RR9215H3KB024BBFZX2=mcc-customer-id h_01KNM00RR9DBR5979GA0FVD5AK=conversion-action-id traits-and-limitations=%E7%89%B9%E6%80%A7%E4%B8%8E%E9%99%90%E5%88%B6 h_01KQAE3JKMQ6ZEATDAEXBC4PT6=%E7%89%B9%E6%80%A7%E4%B8%8E%E9%99%90%E5%88%B6" />
