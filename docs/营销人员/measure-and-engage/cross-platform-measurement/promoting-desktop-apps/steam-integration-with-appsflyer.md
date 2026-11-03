---
title: AppsFlyer中的Steam对接配置说明
metadata:
  keywords:
    - CTV
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2022-12-08T10:02:09Z'
  edited_at: '2026-10-14T10:03:48Z'
  id: 11241130508433
  locale: zh-cn
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/zh-cn/articles/11241130508433
---
> **概要： 概要：本文介绍了Steam上的游戏/应用与AppsFlyer的对接方式。对接完成后，您就可以获得Steam广告的归因和事件数据。Steam对接支持针对用户Steam设备上的Steam应用进行归因和事件记录。**

## Steam归因简介

Steam平台可在Windows和Mac设备、Steam Deck及其他以Steam为操作系统的设备中运行。

在PC端运行的应用可以通过S2S API或SDK与AppsFlyer对接，从而获得归因数据和投放效果指标，了解应用打开和应用内事件的流量来源和带量广告。这些关键信息能够帮助营销人员评估并优化其市场推广工作。

### 归因链接示例

下文所示的归因流程重点说明了从广告互动到归因的用户链路中最关键的几个环节。其中还包含AppsFlyer推荐的跨平台落地页。**请注意**：请注意：虽然我们建议您使用跨平台落地页，但您仍可以选择直接归因链接。

Steam\_user\_journey.jpg

1. 营销触点这些营销触点可包括定期/不定期邮件、社交媒体、移动端网页等等。
2. 您可以通过游戏落地页让用户跳转到您的Steam游戏页面。这个步骤对于UTM及其他URL参数的收集至关重要。有了这些参数，AppsFlyer就能将来自相关点击/激活的用户归因到带量的媒体渠道或广告主的自有媒体。  
   如果您的游戏支持多个平台，可以在落地页中提供跳转到各个平台的链接，比如Xbox、Microsoft商店以及Steam页面等。  
   ![awesome_game.png](https://files.readme.io/37cabff10a2e0a721b4d2901e7df47f53a7dedff25bdac80b97003b60eaef430-51473918248465.png)
3. <span id="marketing-touchpoint"></span>Steam应用页面即您的Steam商店页面，其中包含可供用户下载的Steam应用。
4. 游戏激活游戏激活：用户激活游戏时即会触发归因，并开始记录应用内事件和应用打开（session）。

## 对接流程

下表列出了Steam应用对接到AppsFlyer时需要完成的工作。

<Table>
  <thead>
    <tr>
      <th>
        事项
      </th>
      <th>
        可用操作
      </th>
      <th>
        人员
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        设置应用
      </td>
      <td>
        * <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">创建一个AppsFlyer帐户</Anchor>
        * <Anchor target="_blank" href="/marketers/zh/docs/user-management">在账户下添加用户，并为其开放必要权限</Anchor>
        * <Anchor target="_blank" href="/marketers/zh/docs/adding-an-app-to-appsflyer">在AppsFlyer后台添加您的Steam应用</Anchor>
      </td>
      <td>
        营销人员
      </td>
    </tr>
    <tr>
      <td>
        应用对接（通过S2S或SDK）
      </td>
      <td>
        对接分为两种不同的方式，即S2S和SDK。S2S和SDK。

        如果您使用S2S对接，请在您的应用中<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">接入AppsFlyer API</Anchor>，使其向AppsFlyer上报下列事件：

        * 首次打开
        * 应用内事件
        * 应用打开（Sessions）

        **请注意**：

        * 应用首次打开（first app open）必须在应用内事件和应用打开（session）之前上报。
        * 使用`device_ids`参数时，请选择`custom`类型。
        * 通过该API发送事件。请向开发人员说明您需要发送的事件。对于要发送到AppsFlyer的事件，请务必在配置API时完成这些事件的设置和映射。
        * 如需上报自有媒体中的广告互动，请对接<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API</Anchor>。

        若通过SDK对接，可供选择的SDK版本有原生<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/steam-vanilla">C++</Anchor>、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unreal-steam">Unreal</Anchor>和<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unity-steam">Unity</Anchor>三种。

        **请注意**：
      </td>
      <td>
        应用开发人员
      </td>
    </tr>
    <tr>
      <td>
        跨平台落地页设置
      </td>
      <td>
        **推荐**：

        <Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">进一步了解跨平台落地页</Anchor>

        <Anchor target="_blank" href="/marketers/zh/docs/cross-platform-landing-pages-with-smart-script">进一步了解跨平台落地页的设置方式</Anchor>

        **请注意**：

        Steam中必须配置下列参数：

        * **platform**: steam
        * **steam\_app\_id**:  

          您可以在地址栏的URL中找到您的应用ID，也可以进入[https://steamdb.info/](https://steamdb.info/)并在其中搜索您的游戏。使用场景示例:

          ```http
          https://store.steampowered.com/app/12345678/
          ```

          这里的12345678就是您的应用ID。
        * **media\_source**

        以下参数是可选的，但仍建议您配置：

        * **campaign**
        * **ad**
        * **ad\_set（广告组）**
        * **storefront\_redirect\_url**:比如：`https://store.steampowered.com/app/12345678/`
      </td>
      <td>
        营销人员（可能需要开发人员协助）
      </td>
    </tr>
    <tr>
      <td>
        链接设置
      </td>
      <td>
        如果您不使用跨平台落地页，可以创建直接归因链接，将其置于广告中。

        <Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-direct-attribution-links">了解直接归因链接的创建方式</Anchor>
      </td>
      <td>
        营销人员
      </td>
    </tr>
    <tr>
      <td>
        报告设置/查看数据
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts#数据可用性">了解面板与报告中的数据可用性</Anchor>
      </td>
      <td>
        营销人员/数据工程师
      </td>
    </tr>
  </tbody>
</Table>


## 特点与局限性

| 特点 | 说明 |
| --- | --- |
| 再营销 | 目前尚不支持 |
| 成本数据 | 必须通过邮件<Anchor target="_blank" href="/marketers/zh/docs/import-cost-data">上传</Anchor>的方式来发送成本数据。 |

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts">CTV、PC和主机平台的归因说明</Anchor>

<div data-zendesk-anchors="about-steam-attribution=steam%E5%BD%92%E5%9B%A0%E7%AE%80%E4%BB%8B 01H7Z1DJRW1KPJQ4CZ6T85ASRK=steam%E5%BD%92%E5%9B%A0%E7%AE%80%E4%BB%8B flow=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E7%A4%BA%E4%BE%8B 01H7Z1DJRWHB8TQC15WW4FVSHG=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E7%A4%BA%E4%BE%8B integration-procedures=%E5%AF%B9%E6%8E%A5%E6%B5%81%E7%A8%8B 01H7Z1DJRWX54DN2SNS21GPGXB=%E5%AF%B9%E6%8E%A5%E6%B5%81%E7%A8%8B removing-appsflyer-data-when-uninstalling-the-app=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01J3349MAA4J231B6FJ74V3PTB=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01HDEHMH0HF201TH4XDW691STH=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01HDP1K6FDDEED5P2WNESST7GE=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
