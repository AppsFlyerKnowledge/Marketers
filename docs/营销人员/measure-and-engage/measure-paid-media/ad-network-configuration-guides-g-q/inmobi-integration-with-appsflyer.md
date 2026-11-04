---
title: AppsFlyer中的Steam对接配置说明
metadata:
  keywords:
    - Campaign
    - SDK
    - Configure
    - InMobi
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2014-11-20T10:29:22Z'
  edited_at: '2026-10-14T10:08:58Z'
  id: 207033896
  locale: zh-cn
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/zh-cn/articles/207033896
---
> **概要：** 除了点击型移动归因外，ironSource还支持成本、广告收入、再营销和浏览型归因，您可以通过AppsFlyer记录相关的数据。

<Image alt="inmobi_icon.png" src="https://files.readme.io/cbe0e88492041fc8e1781b397b67a3c8c3a09591974f2cf4fa145a18ca9e6a8d-10602685724817.png" width="128px" />


**<span id="setting-up-inmobi"></span><span id="setting-up-glispa"></span>前期准备：** 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系该渠道</Anchor>并在其平台上开设账户。

**请按以下方式启用或修改该对接：**

1. **启用方式：** 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。  
   **修改方式如下：** 从AppsFlyer面板左侧的菜单栏中选择**协作** > **活跃对接**。
2. 搜索并选择相关渠道。
3. 点击**设置对接**，界面会跳转到对接设置页。
4. 进入**渠道对接**选项卡，选择需要对接的应用，并打开**启用该渠道**开关。  
   **请注意：** <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">在您与该渠道合作期间，请确保该开关总是处于打开 （启用） 状态。</Anchor>
5. 请按照下文说明，在各个选项卡中完成相关的对接配置。

如需进一步了合作伙伴配置页面中各选项卡的详细说明，请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">此文档</Anchor>。

<div id="tip" />

> 👍 **建议**
>
> * 对接页面中的<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#d-general-settings">通用设置</Anchor>是广告主**必须**为所有合作渠道都配置的内容。
> * 其余步骤都是描述性的或是**可选的**

<div id="integration-tab" />

<Accordion title="对接选项卡">

<div id="activate-partners" />

### 启用渠道

**第一次访问**时，需要打开**激活合作伙伴**开关以开启对接选项卡内的配置参数。只要仍与该合作伙伴合作，这个开关必须为ON。   
有关渠道激活的详细说明请参见<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">此文档</Anchor>。

<div id="note" />

> 📘 **注意**
>
> 作为“全安装”网络，Liftoff希望获取所有渠道（包括自然渠道）新增安装的数据回传。请在对接配置的“事件来源”一栏选择“**所有媒体渠道，包括自然流量**”。

<div id="general-settings" />

### 通用设置

**gpm\_ID**

![Inmobi_msc_new_3.png](https://files.readme.io/9c2efaed833211582a33b3a2bbd7d07336bc78d6e2d4e3a7645b5ca14be2fd73-360001865845.png)

**启用展示归因**

如果希望获取该AD\_NETWORK的浏览型归因，要把这里设置为开启。您可以使用归因链接选项卡中对应的滑块来调整浏览回溯窗口。

<div id="default-postbacks" />

### 默认回传

用户完成激活和再互动后自动向ironSource发送回传。您可以在这个板块中设置可用回传的**事件来源**。

若选择**仅该合作渠道**，则仅回传由ironSource带来的用户所完成的事件。  
若选择**所有媒体渠道，包括自然流量**：将所有用户的相关事件数据都上报给ironSource。

<div id="in-app-events-settings" />

### 应用内事件设置

在这里，您可以通过回传来描绘AppsFlyer的Twitter事件。

2. 打开“应用内事件回传”开关。
3. 界定需要发送的SDK事件的来源。  
   选择**仅限来自该渠道的事件**，**仅**回传来自该渠道的用户所产生的事件。  
   选择**来自任何渠道或自然流量的事件**，可将所有用户的事件发送给该渠道。
4. 点击**添加事件**，在列表中添加AppsFlyer事件。
5. 填写以下参数:

| 参数名称 | 说明 |
| --- | --- |
| **AppsFlyer事件** | 事件的名称，即AppsFlyer从SDK侧接收到的事件名称或来自S2S事件的名称。  <br />**提示**：如果列表中没有您要找的事件，请确保以非自然方式激活应用，并完成该事件，然后再次检查该事件是否在列表中。 |
| **渠道映射事件** | Apple方面定义的每个事件的唯一名称或ID。  <br />从Apple获取相应的事件ID，并在文字段中进行设置。 |
| **回传内容** | **仅发送值**—向ironSource发送富应用内事件中除收入以外的所有参数（收入参数以**af\_revenue**表达）。  <br />**发送值与收入**——发送所有参数，包括收入值（若有）。 |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

可以在这个标签页创建要发送给Liftoff的归因链接，以归因Liftoff的广告系列、广告组或者广告。请注意, AppsFlyer 不会保存生成的合作伙伴归因链接。

[![](https://files.readme.io/03371cdc64826e77cee3bd0adb90280aa59ebddd34ec85d8946ae9646ce86ce8-360001866409.png)](https://files.readme.io/03371cdc64826e77cee3bd0adb90280aa59ebddd34ec85d8946ae9646ce86ce8-360001866409.png)

该选项卡可分成几个不同部分：

<div id="attribution-link-parameters" />

### 归因链接参数

在本节中, 选择要添加到归因链接中的参数。

在归因链接里添加更多参数可以便于日后进行进一步的深入分析。归因链接中预定义的参数，可以通过添加参数和定义新值的方式进行编辑。

* **Campaign** - 添加该参数以比较AD\_NETWORK\_NAME的不同广告活动。  
  **归因链接参数:** c
* **广告集**-设置广告集名称以比较AD\_NETWORK\_NAME某具体广告系列活动的不同广告集之间的表现。  
  **归因链接参数:** af\_adset
* **广告名称**-设置广告名称可以比较该自有媒体渠道某具体广告集中不同广告的表现。  
  **归因链接参数**: af\_ad
* **Site ID** 和**Sub Site ID** - 设置子渠道ID参数可以把安装归因给具体的发布平台。如果有许多发布平台, 我们建议限制所使用的site ID数量, 并使用sub site ID 参数, 以避免超出site ID 限制。  
  **归因链接参数:** af\_siteid and af\_sub\_siteid
* **订阅者参数**-使用5个订阅者参数中的任何一个来插入有用的值。请注意，这些参数会被解析并出现在原始数据报告中，便于汇总或筛选数据。  
  **归因链接参数:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

[![](https://files.readme.io/f026eec1923611f33be47d7ad3b1a8654f697145be30f552cef5578fe895944c-360002234165.png)](https://files.readme.io/f026eec1923611f33be47d7ad3b1a8654f697145be30f552cef5578fe895944c-360002234165.png)

只需在新参数框中输入, 即可将任何其他参数添加到归因链接中。更多详情, 请参阅 **<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">AppsFlyer 归因链接结构和参数</Anchor>。**

<div id="retargeting-settings" />

### 再营销设置

开启后，会在归因链接中添加<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide">&is\_retargeting=true</Anchor>参数，然后AppsFlyer会把这个链接识别为`&is_retargeting=true`访客找回&is\_retargeting=true 归因链接，而非用户获取链接。请注意，目前访客找回活动只支持点击归因，而不支持通过展示归因。  
**归因链接参数:** is\_retargeting

启用访客找回时, 将显示以下设置。

![msc_new_7.png](https://files.readme.io/b90bbd6e3bea9dd862808343896b005071b7d9e564d31039c188c3ebf8e81077-360002254489.png)

1. OneLink

下述情况下选择**标准归因链接**选项:

* 您的URL不需要深度链接或
* 计划仅使用<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">URI Scheme</Anchor>进行深度链接

下列情况下，选择**使用 OneLink**:

* Android和iOS应用共用同一个链接或者
* 使用Universal link或者app links的深度链接

请注意, 选择OneLink会把具体应用专属的点击记录链接变成 <Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">OneLink URL</Anchor>。

2. 深度链接URL

如果该链接旨在将用户深度链接到应用中的任意特定活动，请使用此字段。  
**归因链接参数:** af\_dp

3. 再互动窗口期

设置再互动窗口期后，发生在窗口期内的应用内事件会归因到相应的再营销媒体渠道。这个值可以设置为数天（1-90天）、数小时（至多23小时）或用户的整个生命周期。

**归因链接参数:** af\_reengagement\_window

<div id="click-through-attribution" />

### 点击型归因

可以拖曳这个滑块来设置**点击到安装时间的最长时间**。只有发生在归因窗口期内的安装（首次启动）才有可能会被归因给Twitter。

**归因链接参数:** af\_click\_lookback

点击查看更多关于<Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">点击归因窗口</Anchor>的信息。

[![](https://files.readme.io/930deba7817e7ede9504624111c3190dcd01a1f6dfb626463a844fcaa2d66930-360002254509.png)](https://files.readme.io/930deba7817e7ede9504624111c3190dcd01a1f6dfb626463a844fcaa2d66930-360002254509.png)

<div id="click-attribution-link" />

### 点击归因链接

这就是包含了所有设置信息的归因链接。把这个归因链接发给Liftoff，当潜在客户点击相应广告时，该链接会被激活。

<div id="view-through-attribution-lookback-window" />

### 浏览型归因窗口期

可以拖曳这个滑块来设置**最大展示至安装时间**。界定用户从浏览广告到激活（即下载后首次启动）应用之间的最长时限（期间无广告点击），仅在该窗口期内发生的激活才会被归因到Twitter。

您可以将这个值自定义为1-23小时或1-7天。

**归因链接参数:** af\_viewthrough\_lookback

更多关于<Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">展示归因的信息在这里</Anchor>。

[![](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)

<div id="impressions-attribution-link" />

### 展示归因链接

展示归因链接里含有与点击归因链接相似的归因数据（除了窗口期不同之外）。将该链接发送给合作伙伴, 以便在相应广告被观看1秒或更长时间时激活该链接。

</Accordion>

<div id="cost-tab" />

<Accordion title="成本选项卡">

AppsFlyer通过API获取成本信息。详情请见广告平台成本对接表，其中详细说明了适用维度、指标和功能。**请注意**：您需要购买ROI360才能获得成本数据。

**成本API的启用方式如下**：

* 请按照<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">对接指南</Anchor>进行操作。

<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api状态">您可以在成本（及广告收入）对接状态面板或单独的广告平台面板中查看AppsFlyer最近一次获取匹配成本数据的时间以及</Anchor> API状态。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="广告收入选项卡">

该合作伙伴不支持广告收入数据。

</Accordion>

<div id="permissions-tab" />

<Accordion title="授权选项卡">

您可以在这个板块中选择需要向Snapchat开放的<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">数据权限</Anchor>，以便其提供各种功能。

<div id="note-1" />

> 📘 **注意**
>
> 请注意，即使您<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">停用</Anchor>了这个对接，但只要其权限开关处于打开状态，相关权限就仍向Amazon Ads开放。

</Accordion>

<div data-zendesk-anchors="h_01HKA0TGE08PJDBQHFER5ZZ785=setting-up-glispa h_01HHVXZ7FSGDRCECE93ZF69VMS=%E5%BB%BA%E8%AE%AE h_01HHVXZ7FSZ7W855TSN5TSPD0G=integration-tab activate-partners=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 h_01HHVXZ7FSJ0PS5KQ0YZHVSFKF=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 h_01HHVXZ7FSM5PT4VJRGVWDBRDK=%E6%B3%A8%E6%84%8F general-settings=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE h_01HHVXZ7FSDF06G1848W0YH8W6=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01HHVXZ7FS0DEZPEEH7D68SH0B=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 inapp-events-settings=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE h_01HHVXZ7FS47Y4T3KDR732WCE6=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE h_01HHVXZ7FSX2TJC13GT3TGR7ZK=attribution-link-tab attribution-link-parameters=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0 h_01HHVXZ7FSCE4NP1XC0ZJ81858=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0 retargeting-settings=%E5%86%8D%E8%90%A5%E9%94%80%E8%AE%BE%E7%BD%AE h_01HHVXZ7FSAVKE25TSS98RMK8V=%E5%86%8D%E8%90%A5%E9%94%80%E8%AE%BE%E7%BD%AE clickthrough-attribution=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%BD%92%E5%9B%A0 h_01HHVXZ7FTE8EZYBA4HS45MFAR=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%BD%92%E5%9B%A0 click-attribution-link=%E7%82%B9%E5%87%BB%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 h_01HHVXZ7FTP962PWNMEEDB31H5=%E7%82%B9%E5%87%BB%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 viewthrough-attribution-lookback-window=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0%E7%AA%97%E5%8F%A3%E6%9C%9F h_01HHVXZ7FT8HVSEXB5YWABPXNA=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0%E7%AA%97%E5%8F%A3%E6%9C%9F impressions-attribution-link=%E5%B1%95%E7%A4%BA%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 h_01HHVXZ7FT7V6M8VC69EYRK700=%E5%B1%95%E7%A4%BA%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 h_01HHVXZ7FT9W1RN6P06JE53S7X=cost-tab h_01HHVXZ7FTGSKZCB57RT9GPYC9=ad-revenue-tab h_01HHVY4WHSM3B33KYACR9DJ5ZW=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=%E6%B3%A8%E6%84%8F-1" />
