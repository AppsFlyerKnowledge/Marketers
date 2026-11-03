---
title: 受众共享（Audiences）功能指南
metadata:
  keywords:
    - Audiences
    - Advertisers
    - Premium
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2017-05-30T07:21:22Z'
  edited_at: '2026-10-14T10:06:23Z'
  id: 115002689186
  locale: zh-cn
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/zh-cn/articles/115002689186
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 本文介绍了如何使用AppsFlyer的受众共享（Audiences）功能创建人群包，并将其连接到渠道平台用于投放，从而提升拉新和再营销广告的投放效率。

![Intro_image.png](https://files.readme.io/645503f41e6a76c854c62236fc279be591849879790d02001eafc75f0d1a974a-30258966500753.png)

## 受众共享功能简介

AppsFlyer的受众共享产品（Audiences）能帮助您快速完成人群分组，并将其连接到您的自有媒体或付费渠道，实现个性化的广告投放，从而提升用户互动和营销效果。您投放定向广告后，还可以在受众共享面板中查看效果指标。

人群包是根据您所设定的具体标准所细分出来的应用用户，包括现有用户和以往用户。您可以根据个人特征、行为、应用使用情况、归因来源、收入生成情况、地理位置、设备类型等各种信息来配置人群包。

**第1步——在AppsFlyer中创建人群包：** 您可以从零开始创建自定义人群包、导入既定人群包或从我们的“推荐人群包”列表中选择一个预配人群包（可自行调整）。该功能不仅能帮助您节省时间，而且其中的人群包都是根据相关行业的最佳实践配置的。

**第2步——连接人群包：** 人群包创建完毕后，您就可以在AppsFlyer后台将该人群包连接到您所使用的媒体渠道中，AF会将该人群包中的用户标识符发送给渠道，并在渠道系统中创建相应的人群包。这样，渠道就能想这些用户定向投放特定的广告。人群包每天自动更新一次并发送到渠道。此外，您还可以向Amazon S3存储桶等第三方服务商上传人群包，或从面板直接下载CSV格式的人群包文件。

向渠道上传人群包数据时要用到的所有信息都在AF后台的合作伙伴连接中配置。您可以使用不同的账户、登录信息等为同一个渠道创建多个连接。为了符合iOS 14.5和其他用户隐私政策的规定，受众共享功能中与渠道共享的标识符完全由广告主决定，不管是在账户层面还是各个渠道连接中都可以调整相关配置。

### 流量拆分及增量测试

<Anchor target="_blank" href="/marketers/zh/docs/incrementality-for-remarketing-overview">增量</Anchor>测试功能可通过A/B测试精确衡量广告投放的增效幅度——即对比投放广告与不投放广告时的转化量差异，帮助您了解广告投放的真实效果。您可以通过AppsFlyer受众共享面板将人群包拆分到指定渠道以及对照组，作为A/B测试的基础，然后您就可以使用增量分析面板，了解广告投放的真正价值。

## 启用方式

请按照以下步骤启用受众共享功能：

|  | 步骤 |
| --- | --- |
| 1 | 从AppsFlyer后台的侧边栏中选择**互动** > **受众共享**。<br /><br />**请注意：** 受众共享是 AppsFlyer 的高阶功能。如果您在初次使用受众共享产品时需要任何帮助，请联系您的客户成功经理，或发邮件至**hello@appsflyer.com**。 |
| 2 | 在账户级别设置渠道的用户标识符共享<Anchor target="_blank" href="/marketers/zh/docs/audiences-user-identifier-policy">规则</Anchor>。 |
| 3 | 创建新的人群包：<ul><li>[自定义人群包](/docs/audiences-guide#create-a-custom-audience)——从零开始创建人群包</li><li>[推荐人群包](/docs/audiences-guide#create-a-suggested-audience)——根据各行业最佳实践预定义的人群包，您可以自行调整其配置</li><li><Anchor target="_blank" href="/marketers/zh/docs/audiences-import-audience-segments-from-internal-systems">导入人群包</Anchor>——从您的内部系统（如BI或CRM）导入人群分组</li></ul> |
| 4 | 将人群包连接到一个或多个渠道 |
| 可选 | [将人群包拆分到多个渠道和一个对照组](/docs/audiences-guide#audience-split-and-control-groups) |
| 可选 | <Anchor target="_blank" href="/marketers/zh/docs/audiences-create-better-audiences-with-user-attribute-data">导入用户特征</Anchor> |

## 创建并管理人群包

本节说明了人群包的创建和管理方式，以及增量测试的设置方式。

<div id="create-a-custom-audience" />

<Accordion title="创建自定义人群包">

自定义人群包即使用任意的规则组合和筛选条件从零开始创建人群包。

**请按以下步骤创建自定义人群包：**

1. 从AppsFlyer后台的侧边栏中选择**互动** > **受众共享**。
2. 点击**添加人群包**。
3. 选择**自定义人群包**。  
   界面会显示**配置**选项卡。
4. 输入**人群包名称**，不能与其他人群包的名称重复。  
   **请注意：** 人群包名称不可包含特殊字符（" ’ # % & * + / : ; `< = >` ? ( ) [ ] `{ }` \ | ~）
5. 选择适用平台：**安卓**或**iOS**。
6. 选择[用户标识符](/docs/audiences-guide#user-identifier-device-id-vs-customer-id)：
7. 【默认】**设备ID**：仅按设备ID统计符合规则的用户。
8. **客户用户ID**（CUID）：按CUID对设备进行分组，在此基础上统计符合规则的用户（如需使用此方法，请先确认您的数据包含有效的CUID）。
9. 选择**新建规则组合**，如果您想要将现有人群包中的用户添加到新人群包，请点击**从现有人群包中选择**，然后从列表中选择所需的人群包。
10. 按照面板提示配置人群包。有关规则选项的详细信息，请参考[规则组合详解](/docs/audiences-guide#规则组合说明)。
11. 通过逻辑运算符来组合规则：and（并且）、or（或者）、exclude（排除）。
12. 您在创建人群包时，右侧窗格中会自动更新预计的人群包规模以及分渠道的上传量。
13. 定义该人群包的受众，然后点击**继续**。  
    界面会打开**人群包连接**窗口。您可以通过该窗口[将人群包连接到您的合作渠道](/docs/audiences-guide#connect-an-audience-to-media-partners)。

**请注意：**

* 您最多可以同时有100个活跃的自定义/推荐人群包。
* *人群包名称可能会出现在您对接的媒体渠道平台中，所以请注意不要在其中加入任何敏感信息。

</Accordion>

<div id="create-a-suggested-audience" />

<Accordion title="推荐人群包的创建方式">

推荐人群包根据各行业的最佳实践配置，您可以通过该功能尝试各种**预配人群分组**。您可以选择一个推荐人群包，将其调整到最适合您的状态，然后将其连接到您的合作渠道，实现精准的定向投放。

共有30多个预定人群包可供选择，分为**获取、激活、互动、变现和分行业人群包**几个类别。这些人群包的所有配置都可以调整，帮助您创建精准贴合您需求的人群包。推荐人群包包括：

* 将广告点击转化为激活
* 获取相似用户
* 禁投名单
* 吸引用户注册
* 吸引用户购买
* 通过购买用户变现
* 以及众多其他预配人群包

> 📄 **使用场景示例**
>
> 常见的使用场景如下：假设您想要促使您应用中尚未购买任何商品的活跃用户完成首次购买，您可以选择“吸引用户购买”的人群包，并在其中定义具体的应用内购买事件。然后您可以将该人群包连接到您使用的渠道，并投放一系列推广广告，吸引用户购买产品，并将其引导至应用中的购买页面。
>
> ![Encourage_purchase_image_this_one.jpeg](https://files.readme.io/8b49590a0c97707bd4a0b151d30cc48183e15ffb13d2d4e9ee25d522de71846c-30259018203153.jpg)

**请按以下步骤创建推荐人群包：**

1. 从AppsFlyer后台的侧边栏中选择**互动** > **受众共享**。
2. 点击**添加人群包**。
3. 选择**推荐人群包**。
4. 选择相关应用。
5. 浏览各个类别并根据您的目标选择人群包。   
   **请注意：** 部分人群包需要您添加特定的<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">应用内事件</Anchor>，用于定义人群包条件。如果您的应用中已经配置了AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#预定义事件名称">预定义事件</Anchor>，推荐人群包就会预先选择这些事件。如果没有配置，您需要从下拉菜单中选择合适的自定义事件。 <Image alt="Select_an_event__1_.jpeg" src="https://files.readme.io/b5055ca61791f15efc3a91f3f2d749e1df9e3f5e8b956b9167e186474de57ac4-30258966520721.jpg" width="419px" />
6. 点击**选择并自定义**。
7. 输入**人群包名称**，不能与其他人群包的名称重复。  
   **请注意：** 人群包名称不可包含特殊字符（" ’ # % & * + / : ; `< = >` ? ( ) [ ] `{ }` \ | ~）
8. 选择适用平台：安卓或iOS。
9. 选择[用户标识符](/docs/audiences-guide#user-identifier-device-id-vs-customer-id)：
   * 【默认】**设备ID**：仅按设备ID统计符合规则的用户。
   * **客户用户ID**（CUID）：按CUID对设备进行分组，在此基础上统计符合规则的用户（如需使用此方法，请先确认您的数据包含有效的CUID）。
10. 如果您想要添加其他[规则组合](/docs/audiences-guide#规则组合说明)，从而进一步调整该人群包，可以点击 **+筛选条件**按钮。添加完毕后，点击**下一步**。   
    界面会打开**人群包连接**窗口。您可以通过该窗口[将人群包连接到您的合作渠道](/docs/audiences-guide#connect-an-audience-to-media-partners)。   

    **请注意：** 您最多可以同时有100个活跃的自定义/推荐人群包。

</Accordion>

<div id="import-an-audience" />

<Accordion title="导入人群包">

您可以将内部系统（如BI和CRM）的<Anchor target="_blank" href="/marketers/zh/docs/audiences-import-audience-segments-from-internal-systems">预定义人群分组导入AppsFlyer</Anchor>的受众共享面板，然后通过该面板集中管理所有的人群分组，将各人群包连接到相关的渠道。此外，导入的人群包也可使用各种受众共享功能，如标识符匹配/数据扩展和关联投放数据。

</Accordion>

<div id="connect-an-audience-to-media-partners" />

<Accordion title="将人群包连接到渠道">

人群包配置完毕后，您就可以将其连接到您的合作渠道了。

**具体方法如下：**

1. 在人群包**创建**页面配置完人群包后，点击**下一步**。 界面会打开**人群包连接**窗口。
2. 点击 **+添加合作伙伴连接**，然后完成以下任一操作：
   * **如需添加新连接**，请点击 **+添加连接**渠道（详见下文[创建新连接](/docs/audiences-guide#create-a-new-connection)部分）。
   * **从现有连接中选择：**
     1. 搜索所需的合作伙伴连接。
     2. 选择一个或多个现有连接。
     3. 点击**保存**。  
        界面会显示“人群包连接”窗口。
     4. 【可选】[将人群包拆分到渠道和对照组](/docs/audiences-guide#audience-split-and-control-groups)。
     5. 【可选】[将拆分后的分组复制到S3](/docs/audiences-guide#audience-split-and-control-groups)。
3. 点击**保存**。  
   连接完毕后，该人群包每天更新一次并发送到渠道。

</Accordion>

<div id="user-identifier-device-id-vs-customer-id" />

<Accordion title="用户标识符—设备ID与客户用户ID">

AF会通过用户标识符来统计符合指定规则的用户。可选的用户标识符如下：

* 【默认】**设备ID：** 根据设备ID（GAID或IDFA/IDFV）来统计符合指定规则组合的用户。如果用户符合要求，AF就会将其设备ID添加到对应的人群包用户列表中。**请注意：** 仅当设备ID符合您的用户标识符规定时，AppsFlyer才会与渠道共享该ID。
* <Anchor target="_blank" href="/marketers/zh/docs/customer-user-id-field-cuid">**客户用户ID（CUID）**</Anchor>：
  * 将设备ID按其关联的CUID进行分组，从而统计符合指定规则组合的用户。如果该组符合规则组合的要求，则AF会将该组中所包含的设备ID添加到对应的人群包。**注意**：CUID本身不属于人群包用户信息，因此不会发送给渠道。
  * 使用CUID时的注意事项：
    * 请确保您的数据中包含有效的 CUID。
    * 没有CUID的应用用户（即设备）会被直接忽略。
    * 当某个设备ID匹配到一个CUID时，该用户以往的人群包数据会回滚更新，且之后会出现在人群包配置中。**注意**：原始数据不会有任何变化。
    * 如果某个设备ID关联到了两个不同的CUID，则取最近关联的那个CUID。
    * 将CUID作为标识符创建人群包时，须确保AppsFlyer接收到的相关激活（而不仅仅是激活后事件）中包含其关联的CUID数据，从而完成CUID与相关设备的完整关联，同时添加其它设备标识符（即GAID、IDFA），实现数据扩充。<Anchor target="_blank" href="/marketers/zh/docs/customer-user-id-field-cuid#设置cuid">了解更多</Anchor>

<Image alt="CuidExaplainded_us-en.jpg" src="https://files.readme.io/d40309ab2fd34a4862b9c089ac2fade2f5642973fc4d4977da66f1ee6bf1e390-30258966523921.jpg" width="387px" />

> 📄 **比如设备ID与CUID**
>
> 由消费金额超过5美元的用户组成的人群包
>
>
>
> | Advertising  <br />ID | CUID | 消费金额（美元） |
> | --- | --- | --- |
> | A | 99 | 1 |
> | A | 99 | 2 |
> | B | 77 | 1 |
> | B | 77 | 5 |
> | C | 99 | 3 |
> | D | 无 | 50 |
>
>
>
> | 用户统计基础 | 该人群包中的设备ID | 说明 |
> | --- | --- | --- |
> | 设备 ID | B、D | 不会包含A和C — 付费少于5美金 |
> | CUID | A, B, C | * A和C具有相同的CUID（99）— 总共消费6美金。<br />* D会被忽略 — 没有CUID |

</Accordion>

<div id="audience-split-and-control-groups" />

<Accordion title="人群包拆分及对照组">

使用人群包拆分开关，将相关人群包拆分到渠道和对照组，快速完成A/B测试的基本准备工作，然后进行<Anchor target="_blank" href="/marketers/zh/docs/incrementality-for-remarketing-overview">增量衡量</Anchor>，掌握广告投放实质效果的关键信息。启用该功能后，系统会将相关人群包随机拆分到渠道和对照组。对照组是指专门留出一部分流量，不发送给渠道，这是增量衡量的必要条件。您可以根据需求调整拆分比例，并在人群包层级停用或重启拆分功能。

| 功能 | 描述 |
| --- | --- |
| 人群包拆分 | <ul><li>该功能会将相关人群包随机拆分到指定渠道和对照组。**如果您购买了增量分析产品，则该功能默认开启**。您可以随时停用或重启该功能。</li><li>人群包拆分功能可用于各种场景，如A/B测试和增量衡量。</li><li>**请注意：** 更改渠道之间的现有拆分比例会造成整个人群包流量的重新分配，这可能会削弱A/B测试或增量测试结果的有效性，并终止正在进行中的增量实验，使其作为新实验重新开始测试。</li></ul> |
| 对照组 | 保留人群包中的一部分流量，将其作为对照组，不发送到任何渠道：<ul><li>对照组用于A/B测试，并衡量营销投放的增量效果</li><li>对照组的流量比例最好不要低于15%，否则可能会影响有效性</li><li>如要启动增量实验，至少需将1%的流量分配到对照组</li></ul> |
| 将备份拆分列表发送到S3存储桶 | 包含拆分受众列表和对照组的CSV文件可以发送至Amazon S3储存区。<ul><li>**注意**：该场景中的Amazon S3并不是一个已连接的渠道。</li><li>您可以下载CSV格式的人群包列表文件，并将该CSV文件发送到尚未与AppsFlyer对接的渠道。</li></ul> |

**请按以下步骤拆分人群包，并完成其他渠道相关操作：**

1. 点击AppsFlyer面板的左侧菜单栏中的**互动** > **受众共享**。
2. 在**受众共享**选项卡中选择相关人群包。
3. 进入**连接**选项卡。  
   [![audience_split_1200px.png](https://support.appsflyer.com/hc/article_attachments/30258966527249)](https://support.appsflyer.com/hc/article_attachments/30258966527249) 当前设置显示：  
   * 右上方的窗格中会显示预估的人群包总体规模以及对所有渠道的总上传量。
   * 右下方的窗格中会显示一个环形图，体现以下两方面的情况：
     * 对各渠道的预估上传量
     * 渠道重叠情况（仅适用于不拆分的人群包）
4. 完成以下任一操作：

<Table>
  <thead>
    <tr>
      <th>
        需完成的操作
      </th>
      <th>
        流程
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="split-an-audience-between-partners-and-control-group"></span>
        将人群包拆分到渠道及对照组
      </td>
      <td>
        1. 确保**拆分人群包/衡量增量效果**开关已打开。
           * 拆分到对照组和渠道的流量比例总和必须为100%。
           * 如果您不想设置对照组，请将分配到对照组的流量比例设为0%。
           * 所有已连接的渠道都必须分配到一定比例的流量（不能将分配比例设为0%）。
           * 如需查看已分配的总体比例：向下滚动，界面会显示已拆分的流量比例总和。
        2. 输入分配到以下各部分的流量比例：
           * **对照组**——建议将拆分比例设为15%或以上。
           * 为每个连接设定拆分比例。
           * 向下滚动到总体拆分比例，确保各比例相加为100%。
           * 点击**保存拆分设置**。
           * 点击**保存**。
      </td>
    </tr>
    <tr>
      <td><span id="copy-split-groups-to-s3"></span>
        将流量组复制到S3
      </td>
      <td>
        **请按以下步骤将人群包拆分列表发送到S3存储桶：**

        1. 点击**将流量组复制到S3**。
        2. 选择一个连接。
        3. 点击**保存**。

        AF发送文件时使用的目录和文件名结构如下：

        * **目录**：

          ```
           \YYYY-MM-DD\audienceID_audienceName_timestamp\
          ```
        * **文件名**：渠道或对照组的名称。  
          请注意：如果渠道连接失效，则文件无法上传，且渠道名称后会出现**failed**字样（如*partner\_name\_failed.csv*）
      </td>
    </tr>
    <tr>
      <td><span id="create-and-add-a-new-connection"></span>
        创建并添加新连接
      </td>
      <td>
        **请按以下步骤创建新连接：**

        1. 点击**添加** > **渠道** > **连接**。
        2. 输入连接名称。
        3. 选择一个渠道。
        4. 按照面板提示完成相关流程。
        5. 点击**添加渠道连接**。
      </td>
    </tr>
    <tr>
      <td><span id="add-or-remove-an-existing-connection"></span>
        添加或移除现有连接
      </td>
      <td>
        **请按以下步骤移除或添加现有连接：**

        1. 将鼠标悬停在渠道连接上。
        2. 点击“移除”图标。
        3. 点击**保存**。
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="manage-audiences" />

<Accordion title="管理人群包">

**请按以下步骤在受众共享面板中管理人群包：**

1. 点击AppsFlyer面板的左侧菜单栏中的**互动** > **受众共享**。
2. 可用选项如下：  

| 选项 | 描述 |
| --- | --- |
| <span id="create-a-new-audience"></span>创建新的人群包 | 创建新的人群包 |
| <span id="change-audience-settings"></span>更改人群包设置 | 点选一个**人群包名称**，然后执行以下任一操作：<ul><li>在**配置**选项卡中查看和更改规则组合。</li><li>在**连接**选项卡中设置人群包的拆分和对照组选项。</li></ul> |
| <span id="actions"></span>可用操作 | 进入受众共享的主面板，将鼠标悬停在相关人群包上，该列右侧会显示<Image alt="3_dots_icon.png" src="https://support.appsflyer.com/hc/article_attachments/30259018212369" width="7px" />图标：<ul><li>**查看历史记录**：该操作可呈现人群包的上传历史，包括人群包规模以及各渠道间的拆分比例。</li><li>**立即上传**：该操作可向已连接的渠道发送该人群包。</li><li>**下载CSV文件**：<ul><li>生成并下载CSV格式的人群包列表，其中包含您选定的标识符。下载的文件中仅包含符合相关<Anchor target="_blank" href="/marketers/zh/docs/audiences-user-identifier-policy">用户标识符</Anchor>规定的数据。</li><li>针对每个渠道生成一个文件。</li><li>人群包计算完毕后文件才会下载，因此您创建或更改某个人群包后可能需要等待一段时间才能下载。</li><li>下载的文件限长5百万条。如果数据量较大，请将邮件发送到<Anchor target="_blank" href="/marketers/zh/docs/audiences-partner-connections#amazon-s3">S3数据存储桶</Anchor>。</li><li>人群包只有在连接到渠道平台后才会每天更新。没有连接到渠道的人群包则不会在创建日期之后持续更新。如果您需要下载最新信息，可以复制并重新创建该人群包（见下文），然后下载该人群包副本的CSV文件。</li></ul></li><li>**复制**：<ul><li>复制相关人群包的受众定义。</li><li>创建人群包副本时，请确保其名称与其他人群包不重复。</li><li>【可选】在创建副本时移除一个或多个已连接的渠道。</li></ul></li><li>**重新计算**：【适用于导入的人群包】重新计算某个人群包中的用户数。您可以根据实际需要使用该功能，当预估的人群包规模与您的认知有偏差时刷新预估值。</li><li>**<span id="pause"></span>暂停：**</li></ul><ul><li>暂停某个人群包后，该人群包就会处于停用状态，因此AppsFlyer不再计算该人群包中的用户，也不会将其发送到关联渠道（但会保留现有人群包过去3年的数据）。</li><li>您可以暂停不再使用的人群包，以确保您的活跃人群包数量不超过上限。您最多可以同时有100个活跃的自定义/推荐人群包以及500个活跃的导入人群包。</li></ul>**人群包的暂停方式如下：**<ol><li>进入受众共享的主面板，将鼠标悬停在相关人群包上，该列右侧会显示<Image alt="3_dots_icon.png" src="https://support.appsflyer.com/hc/article_attachments/30259018212369" width="7px" />操作图标：</li></ol>![Actions menu.jpg](https://support.appsflyer.com/hc/article_attachments/30258966545297)<ol><li>点击该图标并选择**暂停**。</li></ol>完成上述操作后，该人群包即已暂停。<br /><br />您也可以一次性暂停多个人群包，只需勾选相关人群包左侧的复选框，然后点击界面右上方显示的**暂停**按钮即可。<ul><li>**删除：** 永久性删除该人群包。</li></ul> |
| <span id="bulk-actions"></span>批量操作 | 您可以同时对多个人群包进行相同的操作。使用批量操作功能时，请选择一个或多个人群包，然后执行以下任一操作：<ul><li>**立即上传**</li><li>**显示重叠流量**：显示所选人群包之间的重叠流量</li><li>**删除**</li></ul> |

</Accordion>

## 规则组合说明

本节解释了如何使用规则组合来定义您的人群包。

<div id="audience-segmentation-rulesets" />

<Accordion title="用于人群细分的规则组合">

![audience_segmentation_rulesets.jpg](https://support.appsflyer.com/hc/article_attachments/30259018214801)

* 人群细分规则组合由一条或多条规则组成，帮助广告主实现精准的人群筛选。
* 通过逻辑运算符来组合规则：and（并且）、or（或者）、exclude（排除）。
* 在逐步设定并叠加规则的过程中，预估的人群包规模会实时更新。
* 您可以使用<Image alt="duplicate_icon.png" src="https://support.appsflyer.com/hc/article_attachments/30258966550033" width="17px" />图标来复制规则组合。
* 如果一个人群包中包含多个规则组合，您可以通过重叠图来了解人群细分情况。
* AF会使用设备ID（默认）或客户用户ID（即CUID）作为[用户标识符](/docs/audiences-guide#user-identifier-device-id-vs-customer-id)来统计符合规则的用户。

以下示例解释了各种场景下所使用的规则组合。

</Accordion>

<div id="ruleset-examples" />

<Accordion title="规则组合示例">

> 📄 **示例：基于位置的规则**
>
> 上个月卸载了该应用的纽约用户
>
> ![example_location_based_rule.jpg](https://support.appsflyer.com/hc/article_attachments/30258966552209)

> 📄 **示例：基于用户特征的规则**
>
> 选出具有以下特征的用户：在最近七天内至少打开应用一次，且最喜欢的武器是剑。
>
> ![example_user_attributes_based_rule.jpg](https://support.appsflyer.com/hc/article_attachments/30258966566801)

> 📄 **示例：收入**
>
> 选出在过去7天内激活应用并消费1美元的用户。
>
> ![example_revenue.jpg](https://support.appsflyer.com/hc/article_attachments/30258966567825)

> 📄 **示例：自有媒体筛选条件**
>
> 您可以为自有媒体带来的用户创建专门的人群包，用于定向投放。AF支持的自有媒体类型包括社交媒体（付费广告除外）、SMS、邮件、推荐、网页或二维码等。您还可以对人群进行更精细的划分，按具体的渠道、广告系列、广告组或单个广告创建人群包。
>
> 下图示例中筛选出的用户具有以下特征：在最近7天内至少打开过一次应用，他们的激活被归因到某次邮件营销的某个广告系列的某些广告组的某些广告。
>
> ![Owned_media_example.jpg](https://support.appsflyer.com/hc/article_attachments/30258966580753)
>
> 您可以使用人群包在自有或付费媒体上进行定向投放，通过个性化广告内容吸引这些用户再次使用您的应用，或在投放广告时将这些用户列入禁投名单，避免无效广告打扰用户。

> 📄 **示例：再营销**
>
> 根据用户的点击和浏览行为开展有效的再营销投放。这类用户需要再稍加鼓励或提醒，才会最终转化。由于他们大概率会转化，因此与拉新推广相比，对这些用户进行再营销的效果会好很多。根据收集到的点击和展示数据创建精准定向的人群包，用于再营销投放。
>
> 选出那些在最近两天内点击了广告但没有激活应用的潜在用户，建立人群包。
>
> ![example_remarketing.jpg](https://support.appsflyer.com/hc/article_attachments/30259018231313)
>
> 这些用户最近点击过您的广告，表示他们对您的应用感兴趣，但出于某些原因没有安装应用，或者安装了应用但没有打开。有些用户可能只需要一个小小的提醒，就能推动其激活应用。其他人可能需要查看您应用的更多展示或功能才能实现最终转换。因此，对于那些已点击而未激活的用户，建议您不要投放用于拉新的主素材，而是使用其他素材来做再营销。

</Accordion>

<div id="ruleset-filters" />

<Accordion title="规则组合中的筛选条件">

* 一个规则组合由一条或多条规则组成。
* 规则组合配置选项中包含各类筛选条件，包括事件、收入、地理位置、归因、用户特征、设备及自有媒体。
* 规则的参数和设置各不相同，具体请见下表：

<table><tbody><tr><td colspan="3"><h4><span id="events"></span>事件</h4><img alt="engagement_filter_with_A___B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966588305"/> </td></tr><tr><td> <img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/><ul><li>看过广告</li><li>点击过广告</li><li>已激活应用</li><li>未激活应用</li><li>打开过应用</li><li>未打开应用</li><li>卸载了应用程序 </li></ul></td><td colspan="2"><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/></p><p>时间范围和频次 </p></td></tr><tr><td colspan="3"><h4><span id="inapp-events"></span>应用内事件</h4><img alt="in-app_event_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018249873"/> </td></tr><tr><td> <img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/><ul><li>完成了事件：[<em>事件名称</em>]</li><li>未完成事件：[<em>事件名称]</em> </li></ul></td><td><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/></p><p>时间范围和频次 </p></td><td><p><img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018252561"/></p><p>事件参数 + 值：</p><ul><li>是</li><li>大于</li><li>小于</li></ul></td></tr><tr><td colspan="3"><p><a href="./in-app-events-overview" target="_blank"><strong>应用内事件</strong></a><strong>相关说明：</strong></p><ul><li>应用内事件列表<a href="./about-data-freshness-and-timezone-support#daily-processing" target="_blank">每天</a>更新一次。 </li><li>如果您选择了<strong>Did event</strong>（完成了事件），且该事件具有关联的参数，您可以通过事件的参数值来进行筛选。 </li><li><p>默认情况下，应用内事件的每个参数最多可以有100个独立值。比如“purchase”（购买）事件的“content-type”（内容类型）参数最多只能出现100种内容类型。但数值型参数值不受此限制影响。<br/>如果您发现列表中的应用内事件参数和参数值有所缺失，可以点击<strong>添加事件参数</strong> &gt; <strong>添加项目</strong>，手动添加相关参数和值。<br/> </p><p><strong><img alt="Add_item.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966609297"/></strong></p><p>请注意：</p><p>- 所有手动添加的事件参数必须以字符串（文本）的形式输入。不可添加数值，即使添加也无法正常生效。</p><p>- 手动添加事件后，“预估人群包规模”可能无法准确反映实际的人群包大小。 <br/>如果您需要用到的参数/值超过100个，请请联系您的CSM或发送邮件至hello@AppsFlyer.com。</p></li></ul></td></tr><tr><td colspan="3"><h4><span id="revenue::3358edf4"></span>收入</h4><img alt="revenue_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966611089"/> </td></tr><tr><td> <img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/><ul><li>应用内购总收入</li><li>广告变现总收入</li><li>总体收入 </li></ul></td><td colspan="2"><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/></p><ul><li>是</li><li>大于</li><li>小于 </li></ul><p><strong>定义：</strong></p><ul><li> <strong>应用内购总收入</strong>：某个具体的设备ID/CUID通过<code>af_revenue</code>参数上报的所有事件值的总和。</li><li> <strong>广告变现总收入</strong>：某个具体的设备ID/CUID带来的广告收入总和</li><li> <strong>总体收入</strong>：应用内购总收入 + 广告变现总收入</li></ul><p><strong>请注意：</strong></p><ul><li>如需使用<strong>广告变现总收入</strong>和<strong>总收入</strong>这两个筛选条件，必须确保您在AppsFlyer账户中启用了<a href="./roi360-guide-ad-revenue-attribution" target="_blank">广告收入归因</a>。</li><li>所有与收入有关的筛选条件都是按美元计算的。</li></ul></td></tr><tr><td colspan="3"><h4><span id="geo"></span>国家/地区</h4><img alt="location_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018257041"/> </td></tr><tr><td> <img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/><ul><li>地理位置 </li></ul></td><td> <img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/><ul><li>是</li><li>不是</li></ul></td><td><p><img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018252561"/></p><p><strong>位置选项</strong></p><ul><li>国家</li><li>State（州）</li><li>City（城市）</li></ul></td></tr><tr><td colspan="3"> <strong>关于位置的备注：</strong><ul><li>如果您选择了多个国家，就不能选择州。</li><li>如果您选择了多个州，仍能选择城市。</li></ul></td></tr><tr><td colspan="3"><h4><span id="owned-media"></span>自有媒体</h4><img alt="doctored_owned_media_image_with_app_specified__final_version_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966614801"/> </td></tr><tr><td> <img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/><ul><li>自有媒体渠道</li><li>自有媒体广告系列</li><li>自有媒体广告组</li><li>自有媒体广告</li></ul></td><td> <img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/><ul><li>是</li><li>不是</li></ul></td><td><p><img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018252561"/></p><p>AF支持的自有媒体包括：</p><ul><li>电子邮件</li><li>短信</li><li>网页</li><li>社交媒体（付费广告除外）</li><li>二维码</li><li>推荐</li><li>具体广告系列、广告组和广告</li></ul></td></tr><tr><td colspan="3"><p>您可以为自有媒体带来的用户创建专门的人群包，用于定向投放。此外，您还可以对人群进行更精细的划分，按具体的渠道、广告系列、广告组和/或单个广告创建人群包。</p><p>您可以使用人群包在自有或付费媒体上进行定向投放，通过个性化广告内容吸引这些用户再次使用您的应用，或在投放拉新/再营销广告时将这些用户列入禁投名单，避免无效广告打扰用户。</p></td></tr><tr><td colspan="3"><h4><span id="device"></span>设备</h4><img alt="device_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966618897"/> </td></tr><tr><td> <img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/><ul><li>设备品牌</li><li>设备型号</li><li>App version</li><li>OS version</li><li>Carrier</li></ul></td><td> <img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/><ul><li>是</li><li>不是 </li></ul></td><td> <img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018252561"/>选定值</td></tr><tr><td colspan="3"><h4><span id="attribution"></span>归因</h4><img alt="Attribution_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966620049"/> </td></tr><tr><td> <img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/><ul><li>自然</li><li>再营销</li></ul></td><td> <img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/><ul><li>否</li><li>True</li></ul></td><td> </td></tr><tr><td colspan="3"><h4><a href="./audiences-create-better-audiences-with-user-attribute-data" target="_blank"><span id="user-attributes"></span>用户归因</a></h4><img alt="user_attribute_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966622097"/> </td></tr><tr><td><p><img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/></p><p>用户特征名称</p></td><td> <img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/><ul><li>字符串类型<ul><li>是</li><li>不是</li></ul></li><li>数字类型<ul><li>是</li><li>大于</li><li>小于</li></ul></li></ul></td><td><p><img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018252561"/><br/>字符串：选择一个值</p><p>数字：输入一个值</p></td></tr></tbody></table>

</Accordion>

<div id="combine-rulesets" />

<Accordion title="规则组合的搭配">

**请按以下步骤将某个规则组合搭配到现有人群包：**

1. 从AppsFlyer后台进入**互动** > **受众共享**。
2. 点击**添加人群包**。   
   界面会显示**配置**选项卡。
3. 输入**人群包名称**，不能与其他人群包的名称重复。
4. 选择适用平台：**安卓**或**iOS**。
5. 【可选】选择**高级设置**，然后选择[用户标识符](/docs/audiences-guide#user-identifier-device-id-vs-customer-id)：
   * 【默认】**设备ID**：仅通过设备ID统计符合规则要求的用户。
   * **客户用户ID**：将设备按CUID进行分组，在此基础上统计符合规则的用户。如需使用此方法，请先确认您的数据中包含有效的CUID。
6. 点击**现有人群包**，然后从列表中选择所需的人群包。
7. 选择一个逻辑运算符：and（并且）、or（或者）、exclude（排除）。

**局限性：**

* 现有人群包和新建人群包的平台（如iOS或安卓）必须一致。
* 不能使用基于现有人群包所创建的人群包。
* 不能使用导入的人群包。

</Accordion>

## 创建并管理渠道连接

本节说明了渠道连接的创建和管理方式。

<div id="create-a-new-connection" />

<Accordion title="创建新连接">

**连接**选项卡中会显示您所有的渠道连接及其状态。向渠道上传人群包数据时要用到的所有信息都在AF后台的合作伙伴连接中配置。您可以使用不同的账户、登录信息等为同一个渠道创建多个连接。

**请按以下步骤创建新连接：**

1. 从AppsFlyer后台进入**互动** > **受众共享 > 连接**。
2. 点击 **+添加人群包**。  

   **请注意：** 如果您要通过人群包配置页面创建新的渠道连接，请点击**管理人群包连接**窗口中的 **+添加渠道连接**按钮。
3. 选择相关的**渠道名称**。
4. 输入**连接名称**。  

   **请注意：** 它必须是创建其他连接时从未使用过的新名称。
5. 填写该渠道的必填字段/登录信息。部分渠道配有<Anchor target="_blank" href="/marketers/zh/docs/audiences-partner-connections">详细的连接指南</Anchor>。  

   **请注意：** 凭证必须是唯一的。为了防止重复创建连接，如果凭证已被用于另一个合作伙伴连接，您将被阻止创建新连接。
6. 选择您向该渠道开放共享的用户标识符。
   * 各渠道支持的标识符可能会有所不同。该列表中仅显示选定渠道支持的标识符。
   * AF仅会上传符合您<Anchor target="_blank" href="/marketers/zh/docs/audiences-user-identifier-policy">账户层级用户标识符规定</Anchor>的标识符。如果您选择的标识符不符合账户层级的规定，界面会显示警告消息。  
     ![doctored_connection_image.jpg](https://support.appsflyer.com/hc/article_attachments/30258966624017)
7. 点击**保存**。

</Accordion>

<div id="manage-connections" />

<Accordion title="管理连接">

**请按以下方式管理现有连接：**

1. 选择一个渠道。
2. 选择一个连接。![](https://support.appsflyer.com/hc/article_attachments/30259018273553) altEdit\_connection\_screen.jpgalt
3. 完成以下任一操作：

| 选项 | 流程 |
| --- | --- |
| <span id="change-the-connection-name"></span>更改连接名称 | **如需更改连接名称**，请直接编辑**连接名称**字段。 |
| <span id="reconnect"></span>重新连接 | **请按以下步骤重新连接：**<ol><li>如果连接状态显示为不活跃，请点击“**重新连接**”。</li><li>升级连接证书，或登录渠道平台并根据界面提示重新验证身份。</li></ol> |
| <span id="modify-user-identifiers"></span>更改用户标识符 | **如需更改用户标识符**，请使用“选择”或“取消选择”按钮，调整您要授权与该渠道共享的用户标识符。 AF仅会上传符合您<Anchor target="_blank" href="/marketers/zh/docs/audiences-user-identifier-policy">账户层级用户标识符规定</Anchor>的标识符。 |
| <span id="delete-connection"></span>删除连接 | **请按以下步骤删除连接：**<ol><li>如果存在关联的人群包，请按以下方式将其移除：<ol><li>选择相关的人群包。</li><li>人群包连接选项卡中会打开一个新的标签页。</li><li>移除连接。</li><li>关闭该标签页。</li></ol></li><li>重复以上流程，将该连接下所有的人群包都移除。</li><li>点击**删除连接**。</li></ol> |

</Accordion>

## 面板和指标

本节介绍了面板中的各项功能和投放指标。

<div id="audiences-dashboard" />

<Accordion title="受众共享面板">

[![new_dashboard_image_doctored.jpg](https://support.appsflyer.com/hc/article_attachments/30258966628625)](https://support.appsflyer.com/hc/article_attachments/30258966628625)

| 栏位 | 描述 |
| --- | --- |
| <span id="audience-name"></span>人群包名称 | 人群包名称 |
| <span id="size"></span>规模 | 所有符合目标人群判定条件的用户数量。 |
| <span id="upload-size"></span>上传量 | 根据您账户层级的<Anchor target="_blank" href="/marketers/zh/docs/audiences-user-identifier-policy">用户标识符规定</Anchor>以及您为该渠道连接指定的标识符类型，得出的可上传用户数量。<br /><br />**请注意：** 受以下因素影响，该数字可能会与渠道侧的实际用户数量有所差异：<ul><li>渠道的判定流程。</li><li>对于iOS，上传量反映的是基于IDFV划分的增强受众段数量，可能包含重复的IDFA。渠道侧在接收数据时会进行去重处理，这也可能导致差异。</li></ul> |
| <span id="app-name"></span>App name | 人群包的受众定义中所配置的应用，不一定是使用该人群包进行定向推广的应用。 |
| <span id="upload-to"></span>上传至 | <ul><li>人群包接收渠道的图标</li><li><Image alt="SplitAudiences.png" src="https://support.appsflyer.com/hc/article_attachments/30259018280465" width="36px" />图标表示该人群包被拆分到了不同渠道</li></ul> |
| <span id="incrementality"></span>增量分析 | 如果您购买了<Anchor target="_blank" href="/marketers/zh/docs/incrementality-for-remarketing-overview">增量分析产品，界面就会显示这一栏。</Anchor> 可能出现的状态包括：<ul><li>**准备中**——即初始的数据收集期（48小时），从投放日期开始计算。</li><li>**关联到广告系列**——选择相关的广告系列，将其关联到该实验。这里会预选AF推荐的广告系列，且下拉菜单中会按相关性列出其他的推荐选项。</li><li>**进行中**——该试验正在进行中。</li><li>**已完成**——该实验已结束。</li></ul>点击状态后可进入增量分析面板。 |
| <span id="upload-status"></span>上传状态 | <ul><li>当前的人群包上传状态</li><li>提示框中会显示最近一次上传的日期和时间。</li><li>如果上传失败，请点击**查看详情**并根据报错消息中显示的信息做相应的调整。</li></ul> |

</Accordion>

<div id="campaign-metrics" />

<Accordion title="投放指标">

#### 指标哈希

#### 投放指标简介

受众共享面板的**投放指标**部分会显示使用人群包（无论是包含、排除还是作为相似受众的参照）进行定向投放的广告系列的数据。

* 通过媒体渠道投放广告的其中一个环节就是使用人群包进行定向（以及选择人群包的使用方式）。各种媒体渠道所支持的人群包使用方式有所不同。

**适用渠道：** 目前，投放指标数据对Meta ads、Google Ads和Snapchat可用。仅在适用渠道下有关联的人群包时，面板的**投放指标**部分才会显示相关数据。

**请按以下方式查看投放指标：**

1. 将页面拉到受众共享面板的最右侧，让**投放指标**完全显示在屏幕上。
2. 使用日期选择器设定数据显示的时间范围（面板默认显示过去7天的数据）。

**请按以下方式下载选定时间范围内的投放指标：**

1. 点击受众共享面板顶部的**导出**按钮。
2. 文件生成后会自动下载。

#### 摘要视图

初始的**投放指标**视图会呈现各人群包的投放数据摘要：

[<Image alt="campaign_metrics_summary_view.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018286225" width="433px" />](https://support.appsflyer.com/hc/article_attachments/30258966633233)

| 表头 | 描述 |
| --- | --- |
| <span id="campaigns"></span>广告系列 | 在选定时间范围内使用了该人群包进行定向投放的广告系列总数（仅限在适用渠道上投放的广告系列） |
| <span id="campaign-cost"></span>投放成本 | 这些广告系列在选定时间范围内的总成本 |
| <span id="campaign-revenue"></span>广告产生的收入 | 在选定时间范围内归因到这些广告系列的总收入 |

#### 详情视图

在选定人群包的摘要视图中点击<Image alt="show_detailed_view_icon.png" src="https://support.appsflyer.com/hc/article_attachments/30259018287633" width="24px" />图标，进入详情视图。（<Image alt="show_detailed_view_icon.png" src="https://support.appsflyer.com/hc/article_attachments/30259018287633" width="24px" />图标在鼠标所在行的最右侧）。

详情视图会显示按适用渠道和广告系列进行细分的数据。

[![campaign_metrics_detailed_view.jpg](https://support.appsflyer.com/hc/article_attachments/30259018293649)](https://support.appsflyer.com/hc/article_attachments/30259018290321)

如果您选定的人群包被用于多个应用的定向推广，请使用下拉菜单![pin_A.png](https://support.appsflyer.com/hc/article_attachments/30259018295697)按应用筛选数据。

点击**数据总览面板**链接![pin_B.png](https://support.appsflyer.com/hc/article_attachments/30258966657169)后，可在数据总览面板中查看相关广告系列：

* 浏览器会新开一个标签页显示数据总览面板，其中自动筛选出相关的广告系列。
* 如果**数据总览面板**链接不可用，请在下拉菜单![pin_A.png](https://support.appsflyer.com/hc/article_attachments/30259018295697)中选定一个应用，就能启用该链接。这时点击该链接就会进入选定应用的数据总览面板。

| 表头 | 描述 |
| --- | --- |
| <span id="cost"></span>成本 | 选定时间范围内的投放成本（总成本以及按适用渠道和广告系列细分的成本） |
| <span id="revenue"></span>收入 | 在选定时间范围内归因到相关广告系列的收入（总收入以及按适用渠道和广告系列细分的收入） |
| <span id="daily-reach"></span>日均触达量 | 在选定时间范围内浏览过相关广告系列中的广告的日平均独立用户数。 |

#### 数据来源及可用性

**投放指标**数据的可用性取决于数据来源：

* **渠道数据：** 由于您需要从渠道侧选择具体广告系列的定向投放人群包，因此下列信息只有相关渠道能够提供：
  * 某个人群包与某个广告系列之间的连接（即某个广告系列用于定向的人群包）
  * 看到该广告系列中广告的日平均独立用户数（“日均触达量”）
* **AppsFlyer数据：** 成本与收入数据由AppsFlyer提供。

<div id="partner-data-availability" />

<Accordion title="渠道数据可用性">

仅上报通过[适用渠道](/docs/audiences-guide#投放指标简介)投放产生的指标数据。

* **请注意：** Google Ads不上报日均触达量。

</Accordion>

<div id="appsflyer-data-availability" />

<Accordion title="AppsFlyer数据可用性">

如果相关应用在AppsFlyer后台的其他板块中（如数据总览面板和事件面板）有成本和收入数据，那么这些数据也会出现在**投放指标**部分。

* 您需要购买<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview">ROI360</Anchor>才能获取成本数据。
* 您需要先配置<Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution">广告收入归因</Anchor>和/或<Anchor target="_blank" href="/marketers/zh/docs/roi360-revenue-attribution-overview">应用内事件收入归因</Anchor>，才能获取收入数据。

</Accordion>

<div id="why-dont-i-see-campaign-metrics-data-for-campaigns-run-with-supported-partners" />

<Accordion title="面板未呈现适用渠道的投放指标数据">

您投放的广告系列必须满足以下任一条件，才会在面板中产生可用的投放指标数据：

* 该广告系列已关联到某个人群包。
* 该广告系列在适配的渠道网站中投放。
* 在主页面中的选定时间段内，该广告系列处于活跃状态。
* 在“投放指标”部分的选定时间段内，我们收到了该广告系列带来的激活流量。
* 您具有相关渠道连接的广告系列层级数据权限。如果看不到该数据，请更改您对该渠道的使用权限，或在渠道连接设置中更换证书。

</Accordion>

</Accordion>

## 特点和局限性

受众共享产品具有以下特点和局限性，敬请留意。

<div id="traits" />

<Accordion title="特点">

| 特点 | 是否支持 | 说明 |
| --- | --- | --- |
| 广告平台 | **x** |  |
| 代理商 | **x** |  |
| 代理数据透明化 | **x** |  |
| 应用层级的指定时区 | 不适用 |  |
| 应用层级的指定货币 | 不适用 |  |
| 大小限制 | 不适用 |  |
| 自然量数据 | ✓ | 包含 |
| 非自然量数据 | ✓ | 包含 |
| 数据时效性 | 日均UTC | <ul><li>每天向合作平台发送一次更新数据。</li><li>规则配置器中的应用内事件列表每天都会更新。</li></ul> |
| 历史数据 | ✓ | 受众共享工具可以访问您订阅该产品之前90天的应用内事件数据以及前31天的点击和展示数据。回滚流程结束后（一般最长需要2周时间），您就可以使用这些数据了。 |
| 账户用户权限 | ✓ | <ul><li>CSV下载、S3设置、SFTP及Slack渠道连接等功能需要用户账户对原始数据的权限授权。</li><li>为了安全起见，如果您用于创建某人群包的账户被删除，AppsFlyer会停止向相关渠道上传该人群包的数据。如需查看人群包的上传状态，请从后台进入**互动** > **受众共享**。如需重新启用相关人群包，请为其创建副本并在[人群包拆分](/docs/audiences-guide#audience-split-and-control-groups)设置中完成相应配置。</li></ul> |

</Accordion>

<div id="limitations" />

<Accordion title="局限性">

| 局限性 | 说明 |
| --- | --- |
| 归因数据 | 点击和展示数据仅涵盖原始点击链接中含有advertising\_id/idfa的设备。人群包的点击数据中不包含来自SRN（即不使用外部归因链接）的用户设备。 |
| 创建人群包 | <ul><li>您无法在渠道平台侧更改人群包名称。</li><li>创建人群包时，菜单仅显示前100个事件。但是如果您输入一个事件名称，就能看到所有事件。</li><li>在查询参数配置器中使用总收入作为筛选条件时，面板无法呈现“预估的人群包规模”。但这对人群包的创建流程没有影响。</li></ul> |
| 连接 | 不支持创建重复的渠道连接（如使用相同账户、登录信息、Property ID等的连接），否则将导致报错。 |
| 下载CSV文件 | 下载的文件最多含5百万条数据。 |
| 已导入受众 | 导入的人群包无法与其他人群包或规则组合搭配使用。 |
| 不活跃人群包： | 不活跃的人群包会暂停使用。也就是说，AF不会再计算这类人群包或将其上传到关联渠道。如需重新启用相关人群包，请点击立即上传。这样，AF就会继续按照暂停之前的方式计算该人群包并自动将其上传到关联渠道。 |
| 不支持 | 以下内容不受 AppsFlyer Audiences 支持：<ul><li><Anchor target="_blank" href="/marketers/zh/docs/audiences-partner-connections#google-ads">Google Ads</Anchor>：不支持UAC广告，其他广告类型都适用。</li><li>Windows Phone OS</li><li>嵌套事件值</li></ul> |
| 人群包规模 | <ul><li>您每天最多可以创建 100 个受众。</li><li>您最多可以同时有100个活跃的自定义/推荐人群包。</li><li>您最多可以同时有500个活跃的导入人群包。</li></ul> |
| 规则组合 | <ul><li>在规则组合中，应用内事件的每一个参数最多可配置100个独立值。比如“purchase”（购买）事件的“content-type”（内容类型）参数最多只能出现100种内容类型。但数值型参数值不受此限制影响。如果一个事件参数需要用到的值超过100个，请联系您的CSM或发送邮件至hello@AppsFlyer.com。</li><li>数值型规则组合筛选条件仅支持整数，不支持小数型数值。举例来说，支持的条件 - 应用内收入等于“$1 USD”；不支持的条件 - 应用内收入等于“$1.5 USD”。</li></ul> |
| S2S报告 | 请确保在S2S应用内事件的回传数据中包含用户标识符（IDFV或IDFA），并且该IDFV或IDFA与AppsFlyer SDK所采集的数据一致。这样可以避免数据遗漏，并确保受众相关的统计和分析结果准确无误。 |

</Accordion>

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/incrementality-for-remarketing-overview">增量分析指南</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/run-an-incrementality-for-remarketing-experiment">增量分析实验实操指南</Anchor>

<div data-zendesk-anchors="audiences-basics=%E5%8F%97%E4%BC%97%E5%85%B1%E4%BA%AB%E5%8A%9F%E8%83%BD%E7%AE%80%E4%BB%8B h_01HBQMA619CKEESZD3ADSP3PSB=%E5%8F%97%E4%BC%97%E5%85%B1%E4%BA%AB%E5%8A%9F%E8%83%BD%E7%AE%80%E4%BB%8B audience-split-and-incrementality-testing=%E6%B5%81%E9%87%8F%E6%8B%86%E5%88%86%E5%8F%8A%E5%A2%9E%E9%87%8F%E6%B5%8B%E8%AF%95 h_01HBQMA619KMJFVX7Y8MXMMQ6N=%E6%B5%81%E9%87%8F%E6%8B%86%E5%88%86%E5%8F%8A%E5%A2%9E%E9%87%8F%E6%B5%8B%E8%AF%95 get-started=%E5%90%AF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HBQMA619118PWF4TA98C4X0B=%E5%90%AF%E7%94%A8%E6%96%B9%E5%BC%8F create-and-manage-audiences=%E5%88%9B%E5%BB%BA%E5%B9%B6%E7%AE%A1%E7%90%86%E4%BA%BA%E7%BE%A4%E5%8C%85 h_01HBQMA619DBX2C7DRY7MSV3P9=%E5%88%9B%E5%BB%BA%E5%B9%B6%E7%AE%A1%E7%90%86%E4%BA%BA%E7%BE%A4%E5%8C%85 h_01HBQMA6195AT0YD7783V6BQR6=create-a-custom-audience h_01HBQMA619F2P2CVPCSMX9RTKB=create-a-suggested-audience h_01HBQMA619RBRYNMVMNQ839196=%E4%BD%BF%E7%94%A8%E5%9C%BA%E6%99%AF%E7%A4%BA%E4%BE%8B h_01HBQMA619ATHVJARHYXQNY955=import-an-audience h_01HBQMA6193FFM66XDTB6WYX06=connect-an-audience-to-media-partners user-identifier%E2%80%94device-id-vs-customer-id=user-identifier-device-id-vs-customer-id h_01HBQMA61A192YFES8TK1347FJ=user-identifier-device-id-vs-customer-id 01ECF4ZD0NWN5QQPP88ZKW0578=%E6%AF%94%E5%A6%82%E8%AE%BE%E5%A4%87id%E4%B8%8Ecuid 01ECF4ZD0WNEF6FRPF1NJHZ9WR=audience-split-and-control-groups h_01HBQMA61ANM52HBDAFA5QZPFN=manage-audiences h_01HT04HW2VBB9ZY28V5KQ5K2AJ=pause all-about-rulesets=%E8%A7%84%E5%88%99%E7%BB%84%E5%90%88%E8%AF%B4%E6%98%8E h_01HBQMA61ANB4K0TCJ4WBHMV8D=%E8%A7%84%E5%88%99%E7%BB%84%E5%90%88%E8%AF%B4%E6%98%8E h_01HBQMA61A30YGERD8Z6DXV3KA=audience-segmentation-rulesets h_01HBQMA61AF7V3M0Y8ZN1R0HZC=ruleset-examples h_01HBQMA61ATV5MHN35XMTJ8MEH=%E7%A4%BA%E4%BE%8B%E5%9F%BA%E4%BA%8E%E4%BD%8D%E7%BD%AE%E7%9A%84%E8%A7%84%E5%88%99 h_01HBQMA61ATB7NYKBP7CD6SZZH=%E7%A4%BA%E4%BE%8B%E5%9F%BA%E4%BA%8E%E7%94%A8%E6%88%B7%E7%89%B9%E5%BE%81%E7%9A%84%E8%A7%84%E5%88%99 h_01HBQMA61APWHKS4EP2NKABSQD=%E7%A4%BA%E4%BE%8B%E6%94%B6%E5%85%A5 01ECF4ZD0MJ8HVQCC54YHFE6DX=%E7%A4%BA%E4%BE%8B%E8%87%AA%E6%9C%89%E5%AA%92%E4%BD%93%E7%AD%9B%E9%80%89%E6%9D%A1%E4%BB%B6 h_01JRAGFYEQ28R6RQNPEK6WZV2F=%E7%A4%BA%E4%BE%8B%E5%86%8D%E8%90%A5%E9%94%80 h_01HBQMA61AEKT6N97SJBW4B01C=ruleset-filters h_01HBQMA61A17Y4928D2ZDGAEXV=events h_01HBQMA61BK8NZF79KDPK0JBX6=inapp-events h_01HBQMA61B4FGBE11W6BW2Z9AH=revenue::3358edf4 h_01HBQMA61BX9XQKBX3MAGYXC2Y=geo h_01HBQMA61B9DRMSNKJM3B0WBE1=owned-media h_01HBQMA61BC1G2VZSJEJF90T7Q=device h_01HBQMA61BF2N8FN6TJ3JD6YXC=attribution h_01HBQMA61CKVMYYS8GG6CP72WD=user-attributes h_01HBQMA61C7K8R4AR13D4WHTHX=combine-rulesets create-and-manage-partner-connections=%E5%88%9B%E5%BB%BA%E5%B9%B6%E7%AE%A1%E7%90%86%E6%B8%A0%E9%81%93%E8%BF%9E%E6%8E%A5 h_01HBQMA61C6WS72DQ8FXVR0KVW=%E5%88%9B%E5%BB%BA%E5%B9%B6%E7%AE%A1%E7%90%86%E6%B8%A0%E9%81%93%E8%BF%9E%E6%8E%A5 h_01HBQMA61CRDF41WBYCDQ91M3R=create-a-new-connection h_01HBQMA61CXZYEW2R12KS99X2N=manage-connections dashboard-and-metrics=%E9%9D%A2%E6%9D%BF%E5%92%8C%E6%8C%87%E6%A0%87 h_01HBQMA61C6WPFFR1F8P0HE4KA=%E9%9D%A2%E6%9D%BF%E5%92%8C%E6%8C%87%E6%A0%87 h_01HBQMA61CMPNC9TYAW82ED18Q=audiences-dashboard h_01HBQMA61CWHR9GDANKT7P6Z27=campaign-metrics metrics-hash=%E6%8C%87%E6%A0%87%E5%93%88%E5%B8%8C h_01HBQMA61CMF3WZFPXKY89076K=%E6%8C%87%E6%A0%87%E5%93%88%E5%B8%8C campaign-metrics-basics=%E6%8A%95%E6%94%BE%E6%8C%87%E6%A0%87%E7%AE%80%E4%BB%8B h_01HBQMA61C4D5HFCDY83HNF5K7=%E6%8A%95%E6%94%BE%E6%8C%87%E6%A0%87%E7%AE%80%E4%BB%8B summary-view=%E6%91%98%E8%A6%81%E8%A7%86%E5%9B%BE h_01HBQMA61DW9Z84G8CH1RNY2RF=%E6%91%98%E8%A6%81%E8%A7%86%E5%9B%BE detailed-view=%E8%AF%A6%E6%83%85%E8%A7%86%E5%9B%BE h_01HBQMA61D3VHDKD103EMN61YH=%E8%AF%A6%E6%83%85%E8%A7%86%E5%9B%BE data-sources-and-availability=%E6%95%B0%E6%8D%AE%E6%9D%A5%E6%BA%90%E5%8F%8A%E5%8F%AF%E7%94%A8%E6%80%A7 h_01HBQMA61DB595QKRTPE97F94E=%E6%95%B0%E6%8D%AE%E6%9D%A5%E6%BA%90%E5%8F%8A%E5%8F%AF%E7%94%A8%E6%80%A7 h_01HBQMA61DCV0M97GMXRA1A30F=partner-data-availability h_01HBQMA61DXNR275AT9SK0G32S=appsflyer-data-availability h_01HBQMA61DH9P5B1H5GYXQ9CCN=why-dont-i-see-campaign-metrics-data-for-campaigns-run-with-supported-partners traits-and-limitations=%E7%89%B9%E7%82%B9%E5%92%8C%E5%B1%80%E9%99%90%E6%80%A7 h_01HBQMA61DT46P43FNSRC1KGAX=%E7%89%B9%E7%82%B9%E5%92%8C%E5%B1%80%E9%99%90%E6%80%A7 h_01HBQMA61DYHF0REXYKDQBDXP5=traits h_01HBQMA61D28F5RG2WXT801XXZ=limitations h_01HDNZ24ZDXSAPJ1F5QCB9X1EN=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
