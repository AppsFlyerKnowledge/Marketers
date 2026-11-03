---
title: Snapchat与AppsFlyer的SKAN互通设置
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-02-10T20:20:51Z'
  edited_at: '2026-10-14T10:12:25Z'
  id: 360017604077
  locale: zh-cn
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/zh-cn/articles/360017604077
---
> **概要：概要：启用AppsFlyer与Snapchat的SKAN互通设置后，Snapchat就能向AppsFlyer发送SKAN回传，同时AppsFlyer也能与Snapchat分享广告主的CV值映射构架。**

## SKAN互通：

如果您与多个广告平台合作，建议您在AppsFlyer后台配置您与这些渠道的SKAN对接，这样您就可以利用AppsFlyer平台上的其他可用指标（如成本等）来扩充SKAN的效果指标数据。

**AppsFlyer与Snapchat的SKAN互通作用范围**

设置SKAN互通后，AppsFlyer和Snapchat会共享SKAN转化值（CV）的映射构架，这样广告主就能同时收到来自这两个平台的投放效果指标。如果您启用了Snapchat与AppsFlyer的对接，AppsFlyer还会向Snapchat发送事件，用于优化投放。

**Snapchat中的应用安装广告配置指南**

在Snapchat上配置iOS 14应用安装广告时，需注意Snapchat投放指南中的以下几条规则：

自2021年2月18日1起，Snapchat Ads Manager为所有广告主都开通了SKAN功能。建议您对相关应用做好必要的配置和测试，以确保Snapchat上iOS应用的广告投放和归因不受影响。未来Snapchat会要求广告主在该平台上针对iOS应用使用Goal-based Bidding（基于投放目标的竞价）投放机制时必须配置SKAN。

配置要求

在Snapchat中投放SKAN广告时需注意以下几点：

* 您必须为每一个在Snap上推广的应用都配置一个[Snap App ID](https://businesshelp.snapchat.com/en-US/a/snap-app-id)。
* 需要对Snapchat Ad Sets启用SKAN衡量。
* 一个应用每次最多只能对10个广告组启用SKAN归因。

### AppsFlyer与Snapchat的SKAN互通启用方式

您需要在AppsFlyer和Snapchat后台都完成相关设置，才能实现SKAN互通。您无需对应用本身做任何互通设置，但必须在应用中接入最新版本的AppsFlyer SDK。

<Table>
  <thead>
    <tr>
      <th>
        步骤
      </th>
      <th>
        操作
      </th>
      <th>
        说明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        1
      </td>
      <td>
        应用侧的前期准备
      </td>
      <td>
        * 在应用中接入最新版本的AppsFlyer <Anchor target="_blank" href="/marketers/zh/docs/sdk-integration-overview">SDK</Anchor>。
      </td>
    </tr>
    <tr>
      <td>
        2
      </td>
      <td>
        检查SKAN设置
      </td>
      <td>
        设置并启用AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide">SKAN解决方案</Anchor>。

        **请按以下方式查看SKAN设置**：

        1. 从AppsFlyer后台进入**配置** > **SKAN转化值操作台**。
        2. 点击选项图标（⋮），并确认**SKAN衡量开关**已打开。  

           ![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)
        3. 选择适合您需求的衡量模式。  
           详情请见<Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio">SKAN转化值操作台</Anchor>。
        4. 记下应用内事件的准确名称，在下一步流程中会用到。
      </td>
    </tr>
    <tr>
      <td>
        3
      </td>
      <td>
        应用内事件映射
      </td>
      <td>
        检查应用内事件是否正确映射到Snapchat，并作必要的修改。

        **请按以下步骤查看并设置应用内事件映射**：

        1. 从AppsFlyer后台进入**配置** > **活跃对接**。
        2. 搜索并选择**Snapchat**。
        3. 在**渠道对接**选项卡中，确保**启用该渠道**开关已打开。
        4. 确认AppsFlyer中显示的Snap App ID与<Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/snap-app-id?language=en_US">Snapchat面板</Anchor>中的应用ID完全一致。
        5. 确认**应用内事件回传**开关已打开。  

           [<Image alt="mceclip0.png" src="https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png" width="432px" />](https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png)

           确认SKAN衡量中设置的**SDK事件名称**正确对应到**渠道事件标识符**（即Snapchat的事件名称）。请务必根据当前选定的SKAN衡量模式或您<Anchor target="_blank" href="/marketers/zh/docs/skan-cv-decode-map-your-cv-to-events">自定义的转化映射</Anchor>构架进行事件映射。**请注意**：默认的衡量模式为收入模式。

           #### 应用内事件映射指南

        | 衡量选项 | 映射条件 |
        | --- | --- |
        | 自定义 | 把在自定义模式中设置的应用内事件映射到Snap。<br /><br />如需通过回传上报收入，必须把**Send revenue**（发送收入）设置为**Values & revenue**（发送值与收入）。<br /><br />![SendValueandRevenue.png](https://files.readme.io/412c60db2b09d80a989b7546a6819aa1b030732e0ce004b323dc09db1015c238-11331054047377.png)<br /><br />*af\_skad\_revenue*用于总体收入的衡量，一般映射到Snap的收入事件。<br /><br />**请注意**：请注意：Snap收入事件可以对应多个事件。 |
        | 收入 | Map af\_skad\_revenue映射到PURCHASE |
        | 转化 | 映射1–6个转化事件，与Snapchat的事件一一对应。 |
        | 广告交互 | 映射您选定的互动事件，使其与相关的Snapchat事件一一对应。 |

        6. 点击**保存对接**。
      </td>
    </tr>
    <tr>
      <td>
        4
      </td>
      <td>
        让Snapchat将SKAN数据共享给AppsFlyer
      </td>
      <td>
        1. 进入Snapchat面板。
        2. 在Please share postbacks with this MMP（与该MMP共享回传数据）中选择AppsFlyer。

           [<Image alt="SnapchatSelectAppsFlyer.png" src="https://files.readme.io/e142c4bf54019e8587722af4c5cf5aa95ca49a76948f66e3fb584b003aaacdd6-360017154717.png" width="268px" />](https://files.readme.io/e142c4bf54019e8587722af4c5cf5aa95ca49a76948f66e3fb584b003aaacdd6-360017154717.png)
        3. 点击**更新**。
      </td>
    </tr>
  </tbody>
</Table>

## 其他相关信息

<div id="discrepancies-guide" />

<Accordion title="数据差异指南">

| 数据差异 | 说明 |
| --- | --- |
| 面板筛选条件 | **数据差异原因**<ul><li>AppsFlyer：AppsFlyer：SKAN面板中包含来自iOS回传的激活数据。</li><li>SnapchatSnapchat：默认情况下，Snapchat面板及报告中同时包含由SKAN和传统模式（IDFA）归因到的数据。您可以使用筛选条件使Snapchat报告仅呈现SKAN激活。</li></ul>**解决方法**<br /><br />在Snapchat面板中使用筛选条件，使其仅显示SKAN激活，从而与AppsFlyer面板显示的内容一致，具体请见下图示：<br /><br />[![SnapchatFilter.png](https://files.readme.io/6e067557aabe899df48454aaf4b7be7f466da55e41b7cd3c68db802e48df7d07-360019782137.png)](https://files.readme.io/6e067557aabe899df48454aaf4b7be7f466da55e41b7cd3c68db802e48df7d07-360019782137.png) |
| 激活日期差异 | **数据差异原因**<br /><br />AppsFlyer与Snapchat的激活日期差异如下：<ul><li>AppsFlyer：也就是说，AF中默认的调整幅度为48小时（均以UTC时间为准）。<Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#skan">详情请见SKAN数据时效性。</Anchor></li><li>SnapchatSnapchat：通常将iOS回传接收时间直接作为激活日期，不加调整。</li></ul>**解决方法**<br /><br />对比两个平台的数据时请注意上述差异。 |

</Accordion>

> 📄 **相关文档**
>
> * AppsFlyer的SKAN解决方案指南

<div data-zendesk-anchors="skan-interoperability-appsflyer-snapchat=skan%E4%BA%92%E9%80%9A h_01HDNZ3SP97C331D45AP1F8CM7=skan%E4%BA%92%E9%80%9A enabling-appsflyer-skan-interoperation-with-snapchat=appsflyer%E4%B8%8Esnapchat%E7%9A%84skan%E4%BA%92%E9%80%9A%E5%90%AF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HDNZ3SP9FZ3AXCNG185DJQY1=appsflyer%E4%B8%8Esnapchat%E7%9A%84skan%E4%BA%92%E9%80%9A%E5%90%AF%E7%94%A8%E6%96%B9%E5%BC%8F inapp-event-mapping-guide=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E6%98%A0%E5%B0%84%E6%8C%87%E5%8D%97 h_01HDNZ3SPA742313RAJPYSEHWV=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E6%98%A0%E5%B0%84%E6%8C%87%E5%8D%97 additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HDNZ3SPASN8P9G5YYQGRFC8F=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HDNZ3SPA99XHVBPXVWB5MN86=discrepancies-guide h_01HDNZ1BW5EBP0JCX84MTYPQ6K=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
