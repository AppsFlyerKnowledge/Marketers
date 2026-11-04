---
title: AppsFlyer中的Xbox对接
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-04-03T07:18:07Z'
  edited_at: '2026-10-14T10:06:44Z'
  id: 14241298075921
  locale: zh-cn
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/zh-cn/articles/14241298075921
---
> **概要： PC端原生对接支持PC端应用的归因和应用内事件记录（即在用户的PC上进行归因和记录）。**


<span id="about-epic-game-attribution"></span><span id="about-steam-attribution"></span>这些关键信息能够帮助营销人员评估并优化其市场推广工作。

<div id="example-attribution-flow" />

### 归因链接示例

下文所示的归因流程重点说明了从广告互动到归因的用户链路中最关键的几个环节。其中还包含AppsFlyer推荐的跨平台落地页。 **请注意**：请注意：虽然我们建议您使用跨平台落地页，但您仍可以选择直接归因链接。

![Epic_journey.jpg](https://files.readme.io/c5807442cff142ceb4aa3c4d55628e75b37627a011ca531fa390e46ccc3e23b8-small-14241275857553.jpg)

1. 营销触点 这些营销触点可包括定期/不定期邮件、社交媒体、移动端网页等等。
2. 您可以通过游戏落地页让用户跳转到您的Steam游戏页面。这个步骤对于UTM及其他URL参数的收集至关重要。有了这些参数，AppsFlyer就能将来自相关点击/激活的用户归因到带量的媒体渠道或广告主的自有媒体。  
   如果您的游戏支持多个平台，可以在落地页中提供跳转到各个平台的链接，比如Xbox、Microsoft商店以及Steam页面等。
4. 游戏激活游戏激活：用户激活游戏时即会触发归因，并开始记录应用内事件和应用打开（session）。

<div id="integration-procedures" />

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
      </td>
      <td>
        营销人员
      </td>
    </tr>
    <tr>
      <td>

      </td>
      <td>
        对接分为两种不同的方式，即S2S和SDK。

        若通过S2S对接：

        在您的应用中接入AppsFlyer PC API，使其向AppsFlyer上报下列事件：

        * 首次打开
        * 应用内事件
        * 应用打开（Sessions）

        **请注意**：

        * 应用首次打开（first app open）必须在应用内事件和应用打开（session）之前上报。
        * 使用`device_ids`参数时，请选择`custom`类型。
        * 通过该API发送事件。 请向开发人员说明您需要发送的事件。
        * 如需上报自有媒体中的广告互动，请对接<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API</Anchor>。

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

        * **platform**  
          epic
        * **app\_id**  

          使用场景示例:

          ```http
          https://store.epicgames.com/en-us/p/YOUR-GAME-ID
          ```
        * **media\_source**

        以下参数是可选的，但仍建议您配置：

        * **campaign**
        * **ad**
        * **ad\_set（广告组）**
        * **storefront\_redirect\_url**  

          比如：`https://store.epicgames.com/en-us/p/12345678/`
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

      </td>
    </tr>
  </tbody>
</Table>


<div id="traits-and-limitations" />

<div id="removing-appsflyer-data-when-uninstalling-the-app" />

## 特点与局限性

| 特点 | 说明 |
| --- | --- |
| 再营销 | 目前尚不支持 |
| 成本数据 | 必须通过邮件<Anchor target="_blank" href="/marketers/zh/docs/import-cost-data">上传</Anchor>的方式来发送成本数据。 |

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts">CTV、PC和主机平台简介</Anchor>

<div data-zendesk-anchors="01H7Z1F3SE03BXJD0WAJV8RE7Q=about-steam-attribution flow=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E7%A4%BA%E4%BE%8B 01H7Z1F3SETVXQKRQ71YAJACY3=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E7%A4%BA%E4%BE%8B integration-procedures=%E5%AF%B9%E6%8E%A5%E6%B5%81%E7%A8%8B 01H7Z1F3SF4J2WJ2Y6QG3VGGVK=%E5%AF%B9%E6%8E%A5%E6%B5%81%E7%A8%8B removing-appsflyer-data-when-uninstalling-the-app=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01J3349MAA4J231B6FJ74V3PTB=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01HF9WA5FJ6P4C357ZE231GMR0=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01HE7T4JX3RX3SZW2VPW5ZZY7E=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
