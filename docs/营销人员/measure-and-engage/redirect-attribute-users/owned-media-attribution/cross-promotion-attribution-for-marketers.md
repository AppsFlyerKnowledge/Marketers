---
title: 营销人员的交叉推广归因指南
metadata:
  keywords:
    - tracking
    - Advertisers
    - Cross Promotion
    - cross-promotion
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2017-08-30T13:26:03Z'
  edited_at: '2026-10-14T10:09:55Z'
  id: 115004481946
  locale: zh-cn
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/zh-cn/articles/115004481946
---
> **概要：** 您可以在您的应用中推广其他应用，并对这类交叉营销广告带来的激活进行归因。

![CrossPromo_userJourney](https://files.readme.io/4ecc5b536021355247c51f1a19b23d71623da9f9578387622d6c6f0a57d4801b-4404615401489.png)

<div id="about-cross-promotion" />

## 交叉推广

交叉推广广告非常适用于现有应用的营销以及新发应用的获客。与大部分其他流量渠道相比，这类广告能带来更高的转化率和留存率。由于交叉推广使用自有媒体进行投放，因此广告主可以根据[设备ID](/docs/cross-promotion-attribution-for-marketers#交叉推广的归因)对新增激活进行确定性的归因。交叉推广归因对所有账号开放，无论您使用哪一种AppsFlyer套餐。

下图针对交叉推广的应用展示了相应的面板数据，其中对自有媒体（**af\_cross\_promotion**）及其他渠道上的广告投放指标进行了拆解。您可以看到交叉推广的激活数量和转化率要显著高于其他渠道。

[![CrossPromo_mediaSource](https://files.readme.io/e9a085a0fb987a559c4d35db956d3258c5ee783807eb5e2a222716f0259c1c16-4404613090321.png)](https://files.readme.io/e9a085a0fb987a559c4d35db956d3258c5ee783807eb5e2a222716f0259c1c16-4404613090321.png)

<div id="how-does-cross-promotion-work" />

### 交叉推广的原理

1. 用户在贵司的某个现有应用中看到一条交叉推广广告，这条广告宣传了贵司的另一款应用。广告样式可以是横幅、视频或任何可点击的素材。
2. 【可选】<Anchor target="_blank" href="/marketers/zh/docs/cross-promotion-attribution-for-developers">SDK记录</Anchor>到一条交叉推广展示并向AppsFlyer发送该数据。
3. 用户点击该广告。
4. SDK记录该点击并让用户跳转到应用商店，进入广告中宣传的应用详情页面。SDK记录到的点击中已包含设备ID信息。
5. 用户安装并打开受推广的应用后，[AppsFlyer面板](/docs/cross-promotion-attribution-for-marketers#受推广应用的面板)会在名为**af\_cross\_promotion**的媒体渠道下显示这个新增用户。
   * 如需更改交叉推广的默认渠道值，请让您的开发人员另行添加一个名为`pid`的自定义参数，并在其中填充您指定的值。**请注意**：在安卓平台中，此方式仅适用于V6.4.2及以上版本的SDK。
   * 带来这次新增激活的应用（即source app，流量侧应用）会显示为该交叉推广渠道的**子渠道**。
6. SDK会自动生成一个应用内事件。  
   在安卓应用中，该事件的名称是为`af_cross_promotion`；在iOS应用中，事件名为`af_cross_promotion_clicked`。

<div id="attributing-cross-promotion" />

## 交叉推广的归因

在AppsFlyer的归因体系中，您可以使用设备ID匹配的方式对交叉推广带来的激活进行记录和归因。您可以同时监测展示量和点击量，从而计算<Anchor target="_blank" href="/marketers/zh/docs/about-conversion-rates#marketing-funnel-stages-and-conversion-rates-1">点击率</Anchor>或激活/展示比。

可用于匹配的设备ID取决于以下因素：

* 用户的设备和操作系统版本
* 流量侧应用（source app）中的AppsFlyer SDK版本

| 用于交叉推广归因的设备ID | 设备/操作系统版本 | SDK版本 | 说明 |
| --- | --- | --- | --- |
| IDFA | iOS 9 – 14.4 | V5.0.0+ |  |
| IDFV | iOS 14-14.5： | V6.0.2+ | AppsFlyer SDK会自动收集IDFV，开发人员无需采取进一步的措施。 |
| GAID | 支持Google Play的安卓设备 |  |  |
| OAID、Android ID、IMEI、Fire ID | 不支持Google Play的安卓设备 |  |  |

<div id="setting-up-cross-promotion" />

## 交叉推广归因的配置

交叉推广归因的配置流程涉及AppsFlyer SDK中额外的代码部署，需要营销人员和开发人员合作完成。

营销人员和开发人员的工作流程如下：

| 步骤 | 角色 | 事项 | 说明 |
| --- | --- | --- | --- |
| 1 | 营销人员 | 选择一个现有应用，在其中投放交叉推广广告。 | 在受推广应用的面板中，带来相关激活的流量侧应用（source app）会显示为**子渠道**。 |
| 2 | 营销人员 | 确定是否要添加回溯窗口、广告组名称以及可配置参数等的<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">其他参数</Anchor>，并将这些参数的名称和值发送给开发人员。 |  |
| 3 | 开发人员 | 在SDK中写入相关代码。 | 详情请见<Anchor target="_blank" href="/marketers/zh/docs/cross-promotion-attribution-for-developers">开发者文档</Anchor>。 |
| 4 | 营销人员 | 在[受推广应用的面板](/docs/cross-promotion-attribution-for-marketers#受推广应用的面板)中查看交叉推广广告带来的流量，并对您的投放进行相应的优化。 |  |
| 5【可选】 | 营销人员 | 创建[自定义面板](/docs/cross-promotion-attribution-for-marketers#自定义面板)，就交叉推广带来的流量进行对比分析，并与该账户下的其他用户分享数据。 |  |

<div id="viewing-cross-promotion-data" />

## 交叉推广数据的查看方式

<div id="promoted-app-dashboard" />

### 受推广应用的面板

您可以查看受推广应用的面板，来判断哪些流量侧应用带来的流量质量最高。

**如需对比流量侧应用带来的流量，请按以下方式操作：**

1. 进入**数据总览**面板。
2. 在媒体渠道一栏中选择**af\_cross\_promotion**（或您自定义的渠道名称）。
3. 选择**子渠道ID**对面板数据进行分组，表格中就会列出所有的流量侧应用。[![CrossPromo_SiteID](https://files.readme.io/e057085e90a4a8e56e6769a0af332785488d7757cb5430418e8db6b3cfa67210-4404613179025.png)](https://files.readme.io/e057085e90a4a8e56e6769a0af332785488d7757cb5430418e8db6b3cfa67210-4404613179025.png)

<div id="analysis" />

#### 数据分析

如果您在多个流量侧应用中投放广告宣传同一个应用，可以使用这些流量侧应用的激活、点击、展示和转化率数据进行亲和度分析。转化率最高的流量侧应用（即子渠道）与受推广应用的亲和度最高，前者的用户安装后者的可能性最高。得到这些关键信息后，您就可以对您的交叉推广投放进行相应的优化。

<div id="example" />

> 📄 **示例**
>
> 假设您负责推广PlayIt Gaming International的游戏应用，该厂商旗下有多款人气游戏，包括Bowling（保龄球游戏，ID为com.playit.bowling）和Golfing（高尔夫游戏，ID为com.playit.golfing）。贵司最近发布了一款名为Billiards（桌球）的新游戏。您决定试投一轮交叉推广广告，试探现有应用中点击Billiards广告的用户数量水平。该广告系列在Bowling上的投放效果不错，转化率达到了7.92%，因此您决定在Golfing上也进行投放。
>
> 您查看面板时发现Golfing的转化率高达18.22%，大幅超越Bowling，因此可以判断Golfing与受推广应用Billiards的亲和度要高于Bowling。
>
> [![CrossPromo_conversionRate](https://files.readme.io/347e3abacdff19a3c61b0a5712d3c656d33ddbf14988414ae2e13fc9c22f09b0-4404615475857.png)](https://files.readme.io/347e3abacdff19a3c61b0a5712d3c656d33ddbf14988414ae2e13fc9c22f09b0-4404615475857.png)
>
> 基于以上关键信息，您可以按以下方式对您的广告投放进行优化：
>
> * 在Golfing上全量铺开交叉推广投放。
> * 在点击归因之外，增加对<Anchor target="_blank" href="/marketers/zh/docs/measure-view-through-engagements#浏览型归因链路">展示的归因</Anchor> 。由于您最初仅对您的广告配置了点击归因，因此如果用户仅浏览而未点击该广告，而随后又安装了新应用，他们会被记为自然激活（但这些其实是非自然流量）。也就是说，这种情况下您无法全面了解每个流量侧应用的投放效果。

<div id="custom-dashboard" />

### 自定义面板

受推广应用的面板能帮助您清晰地了解多个流量侧应用各自的带量水平。但如果您在某一个现有应用中推广多个新应用，这时应如何评估投放效果呢？这种情况下，自定义面板可以完美解决这个问题。

您可以使用<Anchor target="_blank" href="/marketers/zh/docs/custom-dashboards">自定义面板</Anchor>在同一个界面中查看多个受推广应用的信息，包括交叉推广带来的流量。此外，您还可以通过自定义面板与您账户下的其他用户快捷地共享数据。

<div id="example-1" />

> 📄 **示例**
>
> 假设您负责eCommerce Apps, Ltd.的营销工作，该厂商旗下有一款超人气应用，名为Shoes（鞋类）。您现在需要为Accessories（配饰）、Jackets and Coats（夹克与外套）以及Sport Shoes（运动鞋）这3个新应用开展上市推广。您决定在Shoes中投一轮交叉推广广告，看看这次投放为哪个新应用带来的效果最好。
>
> 您将您的用户群体分为3组。每当用户打开Shoes时，会看到以下三条广告中的任意一条：1. Accessories的广告；2. Jackets and Coats的广告；3. Sport Shoes的广告
>
> 为了在同一个界面中查看所有3个受推广应用的指标，您创建了一个自定义面板。通过下图所示的面板截屏，您可以看到Sport Shoes的转化率达到20.23%，表明Shoes与Sport Shoes的亲和度远高于另两个应用。
>
> ![CrossPromo_customWidget](https://files.readme.io/9363a68994956bc19115f6f9babb9acb0c7d4fe75478683b2a45720987486956-4404613319953.png)

<div data-zendesk-anchors="about-crosspromotion=%E4%BA%A4%E5%8F%89%E6%8E%A8%E5%B9%BF h_01HE7RXZ2CZCYENE4K40W5YSHF=%E4%BA%A4%E5%8F%89%E6%8E%A8%E5%B9%BF how-does-crosspromotion-work=%E4%BA%A4%E5%8F%89%E6%8E%A8%E5%B9%BF%E7%9A%84%E5%8E%9F%E7%90%86 h_01HE7RXZ2CE5EQV42Y4B9SK4FN=%E4%BA%A4%E5%8F%89%E6%8E%A8%E5%B9%BF%E7%9A%84%E5%8E%9F%E7%90%86 attributing-crosspromotion=%E4%BA%A4%E5%8F%89%E6%8E%A8%E5%B9%BF%E7%9A%84%E5%BD%92%E5%9B%A0 h_01HE7RXZ2CWB2GZ8HV6447RVV1=%E4%BA%A4%E5%8F%89%E6%8E%A8%E5%B9%BF%E7%9A%84%E5%BD%92%E5%9B%A0 setting-up-crosspromotion=%E4%BA%A4%E5%8F%89%E6%8E%A8%E5%B9%BF%E5%BD%92%E5%9B%A0%E7%9A%84%E9%85%8D%E7%BD%AE h_01HE7RXZ2C9JGFYV8K8FECFFJN=%E4%BA%A4%E5%8F%89%E6%8E%A8%E5%B9%BF%E5%BD%92%E5%9B%A0%E7%9A%84%E9%85%8D%E7%BD%AE viewing-crosspromotion-data=%E4%BA%A4%E5%8F%89%E6%8E%A8%E5%B9%BF%E6%95%B0%E6%8D%AE%E7%9A%84%E6%9F%A5%E7%9C%8B%E6%96%B9%E5%BC%8F h_01HE7RXZ2CE9NWMQ1PT3G98QVN=%E4%BA%A4%E5%8F%89%E6%8E%A8%E5%B9%BF%E6%95%B0%E6%8D%AE%E7%9A%84%E6%9F%A5%E7%9C%8B%E6%96%B9%E5%BC%8F promoted-app-dashboard=%E5%8F%97%E6%8E%A8%E5%B9%BF%E5%BA%94%E7%94%A8%E7%9A%84%E9%9D%A2%E6%9D%BF h_01HE7RXZ2CQG9M35Y2FJNPZWDA=%E5%8F%97%E6%8E%A8%E5%B9%BF%E5%BA%94%E7%94%A8%E7%9A%84%E9%9D%A2%E6%9D%BF analysis=%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90 h_01HE7RXZ2CVQD8H0J6EVRJM5T7=%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90 h_01HE7RXZ2CW1P0QNA8FFXP5KBS=%E7%A4%BA%E4%BE%8B custom-dashboard=%E8%87%AA%E5%AE%9A%E4%B9%89%E9%9D%A2%E6%9D%BF h_01HE7RXZ2C7N3DKNPF898WM4AD=%E8%87%AA%E5%AE%9A%E4%B9%89%E9%9D%A2%E6%9D%BF h_01HE7RXZ2C51KJMP795QYS26YK=%E7%A4%BA%E4%BE%8B-1" />
