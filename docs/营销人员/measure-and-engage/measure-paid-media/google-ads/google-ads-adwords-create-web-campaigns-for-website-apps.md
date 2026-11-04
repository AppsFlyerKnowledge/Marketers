---
title: Google Ads（AdWords）—为网站应用创建网络广告活动
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2026-04-07T12:46:10Z'
  edited_at: '2026-10-14T10:00:38Z'
  id: 45498975339537
  locale: zh-cn
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/zh-cn/articles/45498975339537
---
> 概览：为您的网站应用设置 Google Ads 集成，以通过离线转化 API（OCI）向 Google 发送网络转化信号。

<div id="overview" />

## 概览

AppsFlyer 支持与 Google Ads (`googleads_int`) 的集成，用于网站应用广告活动，并通过 Google 离线转化 API（OCI）报告转化数据。

在本文中，您将学习如何在 AppsFlyer 和 Google Ads 中设置网络广告活动，目标是与 Google Ads 互动并在您的网站上转化的用户。

广告活动流程始于用户点击 Google 广告并访问您的网站。当用户完成网站事件（例如，购买或注册）时，AppsFlyer 通过 OCI 向 Google Ads 发送转化信号。Google 使用这些数据来优化广告定位和衡量广告活动的表现。

<div id="see-also" />

> 📄 **另请参阅**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/web-performance-measurement-overview">AppsFlyer 网络归因 - 概述</Anchor>

<div id="prerequisites" />

### 前期准备

在激活网站应用广告活动的 Google Ads 集成之前，请确保您已：

* 在 AppsFlyer 中设置了一个网站应用
* 在您的网站上部署了 AppsFlyer Web SDK
* 拥有适当角色或权限的 AppsFlyer 账户

<div id="how-to-set-up-a-google-ads-web-campaign" />

### 如何设置 Google Ads 网络广告活动

设置分为两个部分：

1. 在AppsFlyer中设置Google Ads对接 （必须完成）
2. 在 Google Ads 中设置广告活动（必需）

<div id="set-up-the-google-ads-integration-in-appsflyer" />

## 在 AppsFlyer 中设置 Google Ads 集成

首先激活 Google Ads 的网络广告活动集成，并设置 AppsFlyer 发送到 OCI 的回调。

<div id="step-1-activate-the-integration" />

<Accordion title="第1步：请按以下步骤激活对接：">

1. 在AppsFlyer面板的左侧菜单栏中点击**协作** > Partner Marketplace。
2. 搜索并选择**Google Ads Web**。
3. 点击**设置对接**，然后界面会跳转到活跃对接设置页面。
4. 在应用下拉菜单中，选择网络应用。
5. 在**渠道对接**选项卡中，打开**启用该渠道**开关。

   <div id="note" />

   > 📘 **注意**
   >
   > 在您与该渠道合作期间，请确保该开关总是处于打开（即启用）状态。

6. 输入您的**Customer ID**。您可以从Google Ads Manager中获取该ID：
   1. 登入您的Google Ads账户。
   2. 点击界面右上角的Google账户图标，然后向下滚动到Customer ID部分。
   3. 请完成以下任一操作：
      * 如果您有多个Google Ads账户同时为相关应用投放广告，必须使用经理账号（MCC）的Customer ID才能进行跨账户的转化监测。在客户 ID 字段和 MCC 客户 ID 文本框中粘贴 MCC ID（而不是特定账户的客户 ID）（两个框中相同的 ID）。 有关更多信息，请参见 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC">Google 关于配置 MCC 账户的说明</Anchor>。
      * 如果您只使用一个 Google Ads 账户来投放广告，只需将账户 ID 粘贴到客户 ID 文本框中，并将 MCC 客户 ID 文本框留空。
7. 如需允许AppsFlyer将转化数据上传到Google Ads，请点击**使用Google登录**。
8. 选择相关经理账号（即您在第7步中获取到Customer ID的MCC账号）中的管理员。
9. 点击**Allow**。

   <div id="note-1" />

   > 📘 **注意**
   >
   > 在您通过Google登录并按照下方步骤允许AppsFlyer获取token后，*令牌缺失*的错误提示将不再显示。如果在登录后错误仍然存在，请验证您的令牌是否具有所需的权限。


</Accordion>

<div id="step-2-set-inapp-event-postbacks" />

<Accordion title="第2步：应用内事件回传">

将您的网站事件映射到 Google Ads 转换操作。AppsFlyer 通过 OCI 将这些事件发送到 Google，以支持基于转换的优化。

<div id="note-2" />

> 📘 **注意**
>
> 对于网站应用，所有事件都是网页事件，没有安装事件。您希望 Google 优化的每个事件必须映射到相应的 Google Ads 转换操作 ID。

1. 打开**应用内事件回传**开关。
2. 如有需要，请设置 **应用内事件回传窗口**。窗口在用户的第一次网站转换事件发生时打开（相当于移动安装日期的网页事件）。
3. 点击**添加事件**。
4. 在 **AppsFlyer 事件** 列中，选择您想要发送的网站事件（例如，`purchase`，`sign_up`）。

   <div id="note-4" />

   <div id="note-3" />

   > 📘 **注意**
   >
   > 访问事件被排除在外。此下拉菜单中仅提供自定义网页事件。

5. 在 **映射到合作伙伴事件** 列中，输入 Google Ads 的 **转换操作 ID**。在您可以执行此操作之前，您需要在 Google Ads 中创建转换操作（请参见下面第 2 部分的第 2 步）。要查找转换操作 ID：
   * 在 Google Ads 中，打开转换操作页面。
   * 打开**Details**选项卡。
   * 然后在该页面URL中复制`ctid=*`查询参数的值。例如，如果 `ctid=123456789`，请输入 `123456789`。
6. 在 **来自用户** 列中，选择 **仅此合作伙伴**，以仅发送归因于 Google Ads 的事件。
7. 在 **包括** 列中，选择是否在回传中包含收入值。
8. 点击**保存对接**。

</Accordion>

<div id="set-up-a-web-conversion-campaign-in-google-ads" />

## 在 Google Ads 中设置网页转换活动

<div id="step-1-set-the-campaign-type-objective-and-goals" />

<Accordion title="第1步：设置投放类型、投放目标和转化目标">

1. 登入Google Ads并创建一个广告系列。
2. 选择投放目标（campaign objective）。
   * 所有目标均适用，除了 **应用推广**，该目标仅适用于移动应用活动。
   * 我们建议根据特定网站转换事件进行优化，选择 **销售** 或 **潜在客户**。
3. 选择您的**转化目标**。默认情况下，您会看到账户级目标。您可以保留这些目标或删除不相关的目标。
   * 如果您想优化的目标未列出，请创建一个自定义转化操作（请参见下面的第2步）。
4. 选择所需的campaign type（广告系列类型）
   * 所有类型均适用，除了**购物**，该类型需要产品目录和经过验证的域名。

</Accordion>

<div id="step-2-create-conversion-actions" />

<Accordion title="第2步：创建转化操作">

对于您在AppsFlyer中映射的每个网站事件，在Google Ads中创建相应的转化操作。创建后，复制转化操作ID并将其粘贴到上一部分的AppsFlyer事件映射中。

1. 在Google Ads中，从侧边菜单中打开**目标 > 转化 > 概述**。
2. 点击 **+ New conversion action**。
3. 选择**导入**作为转化数据源，然后选择以下任一选项：
   * **Manual import using API or uploads > Track conversions from clicks**（通过API或上传手动导入 > 跟踪点击带来的转化）。
   * <strong>CRM, files, or other data sources > Track conversions from clicks</strong>（CRM、文件或其他数据来源 > 跟踪点击带来的转化），然后在<em>Data source（数据来源）</em>部分下选择Skip this step and set up data source later（跳过这一步，之后再设置数据来源）。
4. 点击**继续**，进入下一步。
5. 在**Conversion goal**（转化目标）中选择一个转化操作类别。
6. 输入**Conversion name**（转化名称）。

   <div id="important" />

   > 🚧 **重要提示！**
   >
   > 如需在使用GCLID的基础上，通过GBRAID/WBRAID搭配Offline Conversions API，请确保转化操作中的**Count**字段设置为**Every**（默认），而非*One*。

7. 输入**转化名称**并点击**添加**。

   <div id="note-5" />

   > 📘 **注意**
   >
   > 如果您只需针对某一个具体转化行为来优化投放，请仅在选定转化类别中添加这一个转化操作。举例来说，如果您希望自己的广告系列针对First open（首次打开）进行优化，请确保该操作是您选定的转化类别中所包含的唯一一个转化操作。然后，您就可以在创建相关广告系列时将这个转化类别选作您的转化目标，用于优化投放。

8. 点击**Save and continue** > **Done**，此时您尚未设置数据来源（data sources）。新创建的转化操作初始状态可能显示为“Inactive（未激活）”，在实际数据传入后会自动变为“Active（激活）”。
9. 找到新建转化操作的ID，将该操作映射到AppsFlyer的回传事件。在相关转化目标的**Summary**页面中，点击您创建的转化操作，并复制转化操作页面的URL中`ctid=*`查询参数的值。
10. 进入AppsFlyer后台，在“渠道对接”配置部分找到您想要让Google进行优化的AF回传事件，然后将`ctid`的值粘贴到**渠道映射事件**一栏。详情请见应用内事件回传

</Accordion>

<div id="step-3-set-the-campaigns-final-url" />

<Accordion title="第3步：设置活动的最终网址">

Google<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6080568?sjid=9660882197247124000-EU">将最终网址定义为&lt;1>“您网站中人们在点击广告后到达的网页的URL地址，也称为‘着陆页’。”</Anchor>

1. 进入Google Ads后台，打开**Campaigns** > ads页面。
2. 找到您需要的广告，点击该行中的编辑图标。
3. 在**最终网址字段**中，输入您的着陆页的URL。

   <div id="important-1" />

   > 🚧 **重要提示！**
   >
   > 切勿将最终到达网址设置为任何AppsFlyer网址（即OneLink链接或单平台归因链接），否则会导致您的广告系列被拒审。仅使用没有重定向的直接网址。
   >
   > 您可以将AF归因参数添加到最终到达网址（Final URL）中，并将其映射到Google的ValueTrack参数，如`af_c_id={campaignid}`。一旦点击Google广告并加载着陆页，这些参数将在页面上可用。如需进一步了解可用的ValueTrack参数，请参考<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348">Google提供的说明文档</Anchor>。
   >
   > 使用场景示例:
   >
   > ```http
   > https://example.com?product=1234&af_c_id={campaignid}
   > ```


<div id="note-6" />

> 📘 **注意**
>
> Google网页广告活动每次互动可以使用两个网址：最终网址和跟踪模板网址。但是，对于广告目标是网站的网页应用活动，跟踪模板网址不是必需的。只有当活动目标是网页到移动时，才可能需要跟踪模板网址。有关更多信息，请参见<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-create-web-based-campaigns">Google Ads网页到应用活动文章</Anchor>。

</Accordion>

<div id="view-web-performance-measurement-data" />

## 查看网络归因数据

Google Ads 活动的网络归因数据可在跨平台仪表板和原始数据导出中获取：

* **可在**在<Anchor target="_blank" href="/marketers/zh/docs/my-dashboards#crossplatform-dashboard">跨平台仪表板</Anchor>中，网络和应用数据并排显示，为您提供跨平台活动表现的统一视图。
* 原始数据导出网络归因数据也可以在<Anchor target="_blank" href="/marketers/zh/docs/raw-data-export-page">原始数据导出页面</Anchor>中获取。
  * `media_source`字段显示归因于 Google Ads 的网络事件的`googleadwords_int`。

<div id="note-7" />

> 📘 **注意**
>
> 这个统一的报告视图让您可以在一个地方分析网络和应用活动的表现，包括完整的移动和网络成本报告。

<div id="measure-web-performance-data-with-web-cost" />

## 通过网络成本测量网络归因数据

要获取 Google Ads 的网络归因数据和网络成本数据的完整表现视图，请确保在仪表板和<Anchor target="_blank" href="/marketers/zh/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">成本 ETL 报告</Anchor>中拥有<Anchor target="_blank" href="/marketers/zh/docs/roi360-onboarding-guide#roi360简介">ROI360 套件</Anchor>，并完成以下设置：

1. 通过`googleadwords_int`将成本连接到您的网站应用（而不是通过`googleads_int`）从**成本**选项卡或**成本设置**页面。有关如何连接成本的更多信息，请参见<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#启用cost-api">设置 ROI360 成本 API 以测量成本数据</Anchor>。
2. 在着陆页 URL 中包含活动 ID（`af_c_id`）。确保 URL 包含完整的活动层级，以便在最细粒度的级别查看与网络归因匹配的成本、点击和展示次数。

<div id="troubleshooting-in-app-event-postbacks" />

## 应用内事件回传问题排查

如果事件数据未出现在 Google Ads 中，请在联系支持之前检查以下内容。

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

<div id="traits-and-limitations" />

## 特点与局限性

| 特点 | 说明 |
| --- | --- |
| 点击和展示 | 网络活动的点击和展示需要<Anchor target="_blank" href="/marketers/zh/docs/roi360-onboarding-guide">ROI360 订阅</Anchor>。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A7%88 h_01KNM00RR7V9BAA2BSPDECHC9F=%E6%A6%82%E8%A7%88 h_01KQC2B644Y44631ZQKC1HPEF4=%E5%8F%A6%E8%AF%B7%E5%8F%82%E9%98%85 prerequisites=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 h_01KNM00RR7H7A9CE06APEZSXKR=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 how-to-set-up-a-google-ads-web-campaign=%E5%A6%82%E4%BD%95%E8%AE%BE%E7%BD%AE-google-ads-%E7%BD%91%E7%BB%9C%E5%B9%BF%E5%91%8A%E6%B4%BB%E5%8A%A8 h_01KNM00RR77P8VD2YJ2R7DZBVX=%E5%A6%82%E4%BD%95%E8%AE%BE%E7%BD%AE-google-ads-%E7%BD%91%E7%BB%9C%E5%B9%BF%E5%91%8A%E6%B4%BB%E5%8A%A8 set-up-the-google-ads-integration-in-appsflyer=%E5%9C%A8-appsflyer-%E4%B8%AD%E8%AE%BE%E7%BD%AE-google-ads-%E9%9B%86%E6%88%90 h_01KNM00RR7E8MFSTGYKFEJDS1C=%E5%9C%A8-appsflyer-%E4%B8%AD%E8%AE%BE%E7%BD%AE-google-ads-%E9%9B%86%E6%88%90 h_01KNM00RR71ZXB72H8X1YXWKED=step-1-activate-the-integration h_01KNM00RR84CCGBR3T5WG7C5VW=%E6%B3%A8%E6%84%8F h_01KNM00RR86C5VKBVTA9X6QRAS=%E6%B3%A8%E6%84%8F-1 h_01KNM00RR8BCJTMPZ29C841BY1=step-2-set-inapp-event-postbacks h_01KNM00RR8PSJ7FEAP7MMEJ1XG=%E6%B3%A8%E6%84%8F-2 h_01KNM00RR89XJ0BZKFDXVC4860=%E6%B3%A8%E6%84%8F-3 set-up-a-web-conversion-campaign-in-google-ads=%E5%9C%A8-google-ads-%E4%B8%AD%E8%AE%BE%E7%BD%AE%E7%BD%91%E9%A1%B5%E8%BD%AC%E6%8D%A2%E6%B4%BB%E5%8A%A8 h_01KNM00RR8SAS3TM1NG5DC58TF=%E5%9C%A8-google-ads-%E4%B8%AD%E8%AE%BE%E7%BD%AE%E7%BD%91%E9%A1%B5%E8%BD%AC%E6%8D%A2%E6%B4%BB%E5%8A%A8 h_01KNM00RR8S24AG7FMN6067PZ2=step-1-set-the-campaign-type-objective-and-goals h_01KNM00RR8H1ZFSHFT0DVB11GN=step-2-create-conversion-actions h_01KNM00RR8EV8XY02YJFV5XSX8=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01KNM00RR8N96SNP1YK0CTN6YZ=%E6%B3%A8%E6%84%8F-4 h_01KNM00RR82NZSKB7K06HCP1VE=step-3-set-the-campaigns-final-url h_01KNM00RR8EP6J43G29Q8VVA5B=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 h_01KNM00RR8A704MKGVVC6MQ2KN=%E6%B3%A8%E6%84%8F-5 view-web-attribution-data=%E6%9F%A5%E7%9C%8B%E7%BD%91%E7%BB%9C%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE h_01KNM00RR8EYJAX2KRGCM65E9M=%E6%9F%A5%E7%9C%8B%E7%BD%91%E7%BB%9C%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE h_01KNM00RR86Q2GTHVNC505KCXZ=%E6%B3%A8%E6%84%8F-6 measure-web-attribution-data-with-web-cost=%E9%80%9A%E8%BF%87%E7%BD%91%E7%BB%9C%E6%88%90%E6%9C%AC%E6%B5%8B%E9%87%8F%E7%BD%91%E7%BB%9C%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE h_01KNM00RR9TF8JRTJXWN23MF1S=%E9%80%9A%E8%BF%87%E7%BD%91%E7%BB%9C%E6%88%90%E6%9C%AC%E6%B5%8B%E9%87%8F%E7%BD%91%E7%BB%9C%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE troubleshooting-in-app-event-postbacks=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5 h_01KNM00RR9Z0BM5EE62M17EE0F=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5 h_01KNM00RR9CJJQAP4GAXZ9KK8N=set-token-permissions h_01KNM00RR9215H3KB024BBFZX2=mcc-customer-id h_01KNM00RR9DBR5979GA0FVD5AK=conversion-action-id traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01KQAE3JKMQ6ZEATDAEXBC4PT6=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />
