---
title: 素材管理
metadata:
  keywords:
    - Premium
    - Marketers
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2025-09-17T12:01:55Z'
  edited_at: '2026-10-14T10:01:27Z'
  id: 39137008313105
  locale: zh-cn
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/zh-cn/articles/39137008313105
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 创意管理帮助您更快地集中管理、审核和上线创意。利用它同步创意存储中的创意，了解跨媒体源的创意活动状态，轻松找到相关创意，并直接上传到支持的媒体来源活动中。

## 关于素材管理

创意管理是一个集中管理创意资产生命周期的中心中心，从存储同步到媒体源上传。

素材管理工具

* 同步创意存储中的创意。
* 在集中画廊中轻松搜索和评论创意作品。
* 了解各媒体渠道的创意活动状态。
* 优先考虑创意，利用AI驱动的发布前评分。
* 直接将创意上传到跨媒体渠道的活动中。
* 回顾上传结果，看看哪些创意成功上传或失败。

创意管理为规模设计，帮助市场营销和创意团队减少手工工作，优化上线时间，并提升活动表现。

## 启用方式

**前期准备**

订阅了<Anchor target="_blank" href="/marketers/zh/docs/creative-optimization-guide">Creative Optimization</Anchor>的AppsFlyer帐户。要注册创意管理，请联系您的客户成功经理或写信给[hello@appsflyer.com](mailto:hello@appsflyer.com)。也可能提供免费试用。

**要开始使用创意管理，请按照以下步骤操作：**

<div id="sync-creatives-from-the-creative-storage" />

<Accordion title="从创意存储中同步创意">

创意管理可以将创意从连接的存储中同步。连接保存后，创意管理会从连接的存储中提取创意素材，并在新增创意时保持库的更新。

创意管理目前支持 Google Drive 和 Dropbox。每个源都有不同的连接流程。

**支持的存储连接包括：**

* [Google Drive](#连接google-drive)
* [Dropbox](#连接dropbox)

#### 连接Google Drive。

**要连接Google Drive文件夹：**

1. 在 AppsFlyer 中，前往 **优化>创意管理**.

**<Image alt="点击 Creative Management New.png" src="https://files.readme.io/c4ae98a4409b0766c9bd41e2f153d67c3d6168d31af82dadd1f43f345678878e-40988213459217.png" width="35.83%" />**

2. 咔哒 **创作人脉**.

<Image alt="点击创意connection.png" src="https://files.readme.io/a1ba600e90389351dc119bb00a358d14909eb92a3fc0b8391e3efa7650992ae2-small-48939135740689.png" width="150%" />

3. 点击**添加连接**。
4. 精选 **谷歌云端硬盘**.
5. 在 Google 云端硬盘中，通过共享包含你创意的文件夹，赋予 AppsFlyer 服务账户的浏览权限，让 AppsFlyer 访问该文件夹： `creative-google-account-drive@creative-prod.iam.gserviceaccount.com`.
   * 创意管理会同步选定文件夹及其子文件夹中的创意。
6. 返回创意管理，输入文件夹URL。
7. 选择相关的应用 ID。这一步是可选的，但我们推荐这样做，因为它有助于正确组织和匹配创意。
8. 咔哒 **添加网址**.
9. 重复前两步，同时连接多个文件夹。

<Image alt="" src="https://files.readme.io/c29dab5dc76470b5e99e8efd8accaec7bfd1c6878f3bcfe8d58d7b650063065b-48939152741393.png" width="92.07%" />altimage (9).png

10. 点击**连接**。

#### 连接Dropbox

连接Dropbox之前，确保你已经用有权限访问相关创意文件夹的账号登录了Dropbox。

**连接Dropbox文件夹：**

1. 在 AppsFlyer 中，前往 **优化>创意管理**.
2. 咔哒 **创作人脉**.
3. 点击**添加连接**。
4. 精选 **Dropbox**.
5. 在Dropbox登录弹窗中，连接到相关的Dropbox账户。
6. 在连接模态中，点击 **选择文件夹**然后选择你想连接的文件夹。
   * 创意管理会同步选定文件夹及其子文件夹中的创意。

<Image alt="点击选择folders.png" src="https://files.readme.io/13d62001deedecfb95a202aa54d36a1d7948d36aa76ac2a93b056be54d2ffe01-48939135745937.png" width="84.64%" />

7. 为每个文件夹选择相应的应用。这一步是可选的，但我们推荐这样做，因为它有助于正确组织和匹配创意。
8. 点击**连接**。

连接建立后，创意管理开始提取和处理创意素材。处理完成后，创意会以创意类型、同步日期、发布日期、状态和可用版本等元数据出现在画廊中。

</Accordion>

<div id="browse-and-select-creatives" />

<Accordion title="浏览并选择创意">

创意管理画廊是你评审、搜索、筛选和选择创意的地方。

每张创意卡代表一个创意人士。创意作品可能包含多个版本，比如不同的分辨率或格式。通过卡片，你可以快速了解创意在媒体源上的新、活跃还是非活跃，并查看高级元数据，如首次上线时间及与创意管理同步时间。每个新创意都会被自动分析和评分，帮助你在上线前挑选出最合适的。分数从C（不太成功）到A（准备扩展），帮助您自信地优先考虑高绩效素材。

<Image alt="" src="https://files.readme.io/a295ed00e01564b04bd32a7ce515cf41012a62324a8fcd350d1b4b9113e0cacb-small-48939135746577.png" width="150%" />altimage (9).png

#### 滤镜创意

使用搜索栏和筛选器通过以下方式查找相关广告素材：

* **搜索栏**:通过ID或姓名搜索创意人员。
* 应用专注于与特定应用相关的创意。
* **媒体渠道**：寻找在特定网络上活跃或曾经活跃的创意人员。
* 素材类型按图片、视频或HTML进行筛选。
* **创作地位**:按新创作、活跃或非活跃创意筛选。
* **创意配乐**:重点关注具有特定AI分数的新创意。
* **同步日期**:查找在特定时期内加入创意管理的创意人员。
* 启动日期寻找在特定时期首次发布的创意。
* 分辨率寻找拥有特定版本的创意人员。

默认情况下，创意按同步日期排序，因此最近添加的创意会优先显示。你也可以按发布日期或创意名称排序。

</Accordion>

<div id="upload-creatives-to-media-sources" />

<Accordion title="将创意上传到媒体来源">

当你准备启动创意时，从图库中选择一个或多个创意并点击 **上传至媒体源**.

创意管理目前仅支持应用推广活动的上传。上传设置会根据所选媒体源而变化，因为每个网络的需求和目的地结构不同。

对于所有支持的媒体来源，你可以同时将创意上传到多个目的地。

**支持的媒体来源包括：**

* [Google Ads](#google-ads)
* [Meta Ads](#meta-ads)
* [TikTok Ads](#tiktok-ads)
* [Mintegral](#mintegral)
* [Unity Ads](#unity-ads)

#### Google Ads

对于谷歌广告，你可以将创意上传到现有的应用推广广告组。

1. 从画廊中挑选创意作品。
2. 咔哒 **上传至媒体源**.
3. 选择谷歌广告。
4. 选择所需的目的地详情：谷歌账号和广告组。
   * 你可以使用广告活动筛选器来缩小对特定广告组的搜索范围。
   * 你不需要添加YouTube频道。
5. 如果上传动作包含视频，选择上传的视频是否为儿童制作。
6. 从中选择创意人员 **所有创意人士** 并将其分配给广告组。
7. 如果一个创意有多个版本，选择你想上传的相关版本。
8. 检查设置和任何验证信息。
9. 咔哒 **上传到谷歌广告**.

<Image alt="点击上传到谷歌Ads.png" src="https://files.readme.io/5280a1a396584e6874d8a2c24882fb9be4b25747d322fab607944da57a8fcdc9-48939152742545.png" width="100%" />

> 📘 **注意**
>
> 在首次上传大量内容之前，我们建议先用单个创意进行测试，确认它是否正确出现在所选媒体源中。

#### Meta Ads

对于Meta来说，你可以在现有的广告集内创建广告。

1. 从画廊中挑选创意作品。
2. 咔哒 **上传至媒体源**.
3. 选择元广告。
4. 选择所需的目的地详情：元广告账户和广告集。
   * 你可以使用广告筛选器缩小广告组搜索范围。
5. 根据需要创建尽可能多的新广告。
   * 如果你选择了多个广告集，每个广告都会在每个广告集里创建。
6. 从中选择创意人员 **所有创意人士** 并将它们分配给广告。
7. 如果一个创意有多个版本，选择你想上传的相关版本。

<Image alt="Meta Ads.png" src="https://files.readme.io/56c387af74f4904921770abdee23e0d27a92e8f26c40d2d4fa46a4c42a4e2bb0-48939152743441.png" width="1838px" />

8. 检查设置和任何验证信息。
9. 点击**Next**。
10. 设置广告级别字段：Facebook主页、Instagram主页、主要文本、标题、CTA、发布状态，以及是否允许为你的创意添加Meta增强。
    * 默认情况下，这种设置适用于所有新创建的广告。你可以从中选择特定广告来编辑 **定制特定广告** 下拉菜单。
11. 咔哒 **在Meta中创建广告**.

<Image alt="" src="https://files.readme.io/95125f551e731428a8d18a7ba1162246a867cdff4e0d34aee3950e08446c5eeb-48939152744209.png" width="1840px" />altimage (9).png

#### TikTok Ads

对于TikTok广告，你可以将创意上传到现有的应用推广广告中。

1. 从画廊中挑选创意作品。
2. 咔哒 **上传至媒体源**.
3. 选择TikTok。
4. 选择所需的目的地详情：TikTok广告账号和广告。
   * 你可以使用广告活动和广告组筛选器来缩小对特定广告的搜索范围。
   * 你不需要添加YouTube频道。
5. 从中选择创意人员 **所有创意人士** 并将它们分配给广告。
6. 如果一个创意有多个版本，选择你想上传的相关版本。
7. 检查设置和任何验证信息。
8. 咔哒 **上传到TikTok**.

#### Unity Ads

> 📘 **注意**
>
> 对于Unity广告，目前你只能将创意上传到Unity的创意库。即将加入直接上传到活动的功能。

1. 从画廊中挑选创意作品。
2. 咔哒 **上传至媒体源**.
3. 选择 **Unity广告**.
4. 选择你希望创意关联的应用，以及创意的语言（可选）。
5. 如果一个创意有多个版本，选择你想上传的相关版本。
6. 咔哒 **上传到 Unity 广告**.

#### Mintegral

> 📘 **注意**
>
> 对于Mintegral，目前你只能将创意上传到Mintegral的创意库。即将加入直接上传到活动的功能。

1. 从画廊中挑选创意作品。
2. 咔哒 **上传至媒体源**.
3. 选择 **积分**.
4. 选择你希望创意角色关联的Mintegral账号。
5. 如果一个创意有多个版本，选择你想上传的相关版本。
6. 咔哒 **上传到 Mintegral**.

</Accordion>

<div id="review-upload-results" />

<Accordion title="查看上传结果">

开始上传后，上传窗口会自动关闭，创意管理会在后台继续上传，而你则继续工作。

要查看上传结果，请点击 **上传历史** 来自创意管理画廊。

上传历史显示之前的上传作业及其结果，包括：

* 媒体来源和目的地。
* 上传状态成功、部分成功或失败。
* 从被选中中上传的创意数量。
* 上传完成的时间。
* 关于失败创意者的详细信息。

如果上传部分成功或失败，创意管理会在上传历史中显示提示，方便你之后查看问题。在细节视图中，失败的创意者出现了失败的原因。

</Accordion>

<div id="creative-activity-status" />

<Accordion title="创作活动状态">

创意状态帮助你了解创意在你连接的媒体渠道中被如何使用。

在画廊中，每个创意者都可以展示它是否符合：

* 新功能｜创意项目还没上线。
* 启用创意项目目前正在运行。
* 不活跃创意之前是活跃的，但目前没有运行。

创意管理还帮助你了解当前活跃的创意人处于什么状态。点击创意卡片打开右侧面板，您可以准确看到创意活跃于哪些活动和广告组。

利用状态信息回答以下问题：

* 接下来我应该上传哪些新创意？
* 哪些创意在一个媒体平台上活跃，可以在另一个媒体上测试？
* 哪些创意项目之前被测试过，可能值得重新推出？
* 哪些创意正在测试活动中活跃，应该上传到更多活动中？

</Accordion>

## 特性与限制

| 特性 | 说明 |
| --- | --- |
| 战役范围 | Creative Management 目前仅支持应用推广活动。 |
| 支持的存储源 | 目前支持 Google Drive 和 Dropbox 的仓库同步。 |
| 上传目的地因网络而异 | 支持的上传目的地和所需字段因媒体来源而异。 |
| 上传方式因网络而异 | 上传方式因网络而异。  <br />Google Ads、Meta Ads 和 TikTok 支持直接上传到广告活动中（作为广告或创意集）;Unity Ads 和 Mintegral 目前仅支持上传到网络的创意库。 |
| 资产需求 | 创意文件格式、尺寸、时长和大小必须满足每个网络的要求。 |
| 上传历史范围 | 上传历史反映的是上传结果，而非创意的持续交付或审核状态。 |

> 📄 **另请参阅**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/creative-optimization-guide">素材优化指南</Anchor>

<div data-zendesk-anchors="about-creative-management=%E5%85%B3%E4%BA%8E%E7%B4%A0%E6%9D%90%E7%AE%A1%E7%90%86 get-started=%E5%90%AF%E7%94%A8%E6%96%B9%E5%BC%8F h_01KXDN2V1R9SRPFSRGZZ4ZA62S=sync-creatives-from-the-creative-storage connect-google-drive=%E8%BF%9E%E6%8E%A5google-drive h_01KXDN2V1RGCDYJ074FV4KJY8T=%E8%BF%9E%E6%8E%A5google-drive connect-dropbox=%E8%BF%9E%E6%8E%A5dropbox h_01KXDN2V1R75971RE5ECTDM8TM=%E8%BF%9E%E6%8E%A5dropbox h_01KXDN2V1RAA882M55HK9152D6=browse-and-select-creatives filter-creatives=%E6%BB%A4%E9%95%9C%E5%88%9B%E6%84%8F h_01KXDN2V1RHJJZC67ZM84TNT0Y=%E6%BB%A4%E9%95%9C%E5%88%9B%E6%84%8F h_01KXDN2V1R8CXZ4XGTX656XRWF=upload-creatives-to-media-sources h_01KXDN2V1RE8748NWSCJP824PD=google-ads h_01KXDN2V1R31MABH1A3G0T9B84=%E6%B3%A8%E6%84%8F h_01KXDN2V1RG25RR7BXYAFVEAT7=meta-ads h_01KXDN2V1RBANB482286YP1QSY=tiktok-ads h_01KXDN2V1R52Y91AZNVGPPWW44=unity-ads h_01KXDN2V1RF9TZ25DFYQ91RVRC=%E6%B3%A8%E6%84%8F-1 h_01KXDN2V1REED32CRW83W7MMC9=mintegral h_01KXDN2V1SVWASV4KGJJ2VC162=%E6%B3%A8%E6%84%8F-2 h_01KXDN2V1S8NZP8F4QN51NS3XP=review-upload-results h_01KXDN2V1SC0PHRY810NJG6QY3=creative-activity-status traits-and-limitations=%E7%89%B9%E6%80%A7%E4%B8%8E%E9%99%90%E5%88%B6 h_01KXDN2V1SDNR1Z5FTKEJNDZF3=%E5%8F%A6%E8%AF%B7%E5%8F%82%E9%98%85" />
