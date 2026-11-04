---
title: 公告：迁移到Pinterest的新回传端点
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2025-07-23T07:26:53Z'
  edited_at: '2026-10-14T10:00:13Z'
  id: 37418019002641
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/37418019002641
---

<Table>
  <thead>
    <tr>
      <th>
        板块
      </th>
      <th>
        详情
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **最新动态**
      </td>
      <td>
        Pinterest已迁移至其Conversions API (CAPI)架构的新端点。若需继续将应用事件发送至Pinterest，请您完成升级。旧端点将于2025年9月30日停用。
      </td>
    </tr>
    <tr>
      <td>
        **生效日期**
      </td>
      <td>
        07/23/2025
      </td>
    </tr>
    <tr>
      <td>
        **重要须知**
      </td>
      <td>
        > 📘 **注意**
        >
        > 本公告涉及向CAPI迁移阶段的相关信息。关于Pinterest对接的通用说明，请参阅<Anchor target="_blank" href="/marketers/zh/docs/pinterest-create-a-mobile-app-integration#应用内事件设置">知识库文章</Anchor>。

        升级至新API中的应用内事件设置可保障Pinterest衡量功能的正常使用，同时为您解锁以下新功能：

        * **支持更多事件类型**：可根据业务目标追踪更多事件，例如：潜在客户、搜索、浏览类别、页面访问等。
          * **注意：** Pinterest V5新端点的事件名称已更新。如未同步更新面板设置，事件报告中将显示为“未知”（unkown）。请参考下方新事件名称列表。
        * **数据质量提升：** 匹配效果更佳，归因更准确。

        新的对接方式需要提供**广告帐户ID**（Ad Account ID）和**访问令牌**（Access token）。为保证回传正常运行，合作渠道必须在2025年9月30日前完成新回传端点的迁移。   

        **如何在Pinterest中获取AppsFlyer广告帐户ID**  
        您可以在Pinterest**Business Manager**或Pinterest**转化**报告中找到AppsFlyer的转化报告广告帐户ID。

        1. 登录您的Pinterest企业帐户（只有在企业资料中您才能看到Hub选项）。
        2. 在浏览器中输入或粘贴网址[https://www.pinterest.com/business/hub/](https://www.pinterest.com/business/hub/)，然后按Enter键访问。
        3. 查看左侧深灰色导航栏。如该栏已折叠，请点击左上角的 “≡”图标以展开。
        4. 下滑找到“Manage business”部分。
        5. 点击Conversion（位于“Manage business”下方）。此操作将打开Conversions面板，您可在此查看发送至Pinterest的AppsFlyer转化数据。
        6. 您可以在浏览器URL中找到广告账号ID。
        7. 如有多个Pinterest广告账号接收来自AppsFlyer的 克隆转化（cloned conversion），请在Pinterest Business Manager中核实所有相关广告账号ID，并确保选择原始的母账号ID作为AppsFlyer转化的目标账号。

        **如何在Pinterest中获取AppsFlyer访问令牌**  
        请按照<Anchor target="_blank" href="https://help.pinterest.com/en/business/article/getting-started-with-the-conversions-api">Pinterest帮助中心</Anchor>列出的步骤进行操作。进入Pinterest的转化界面后，点击 **Conversions API** > **Set-up API**，为该账号生成新的访问访问令牌。  

         **重要提示：** 如果您此前已在AppsFlyer之外单独设置过Pinterest的Conversions API，请在AppsFlyer中继续使用相同的访问令牌。
      </td>
    </tr>
    <tr>
      <td>
        **操作指南**
      </td>
      <td>
        请按照以下说明在AppsFlyer控制面板中设置和迁移应用内事件回传。

        1. **应用内事件设置和控制面板参数处理**  
           我们目前支持以下控制面板参数，以便将您的AppsFlyer事件与Pinterest进行映射：

           * **Ad Account ID**（可见）
           * **Access Token**（可见）
           * **Tag ID**（在控制面板上不可见，仅后端支持，用于辅助向V5版本过渡。完全迁移至V5端点后，该字段也将在后端移除。）

           **请注意：**  
           新回传设置中，**AdAccountID**和**AccessToken**为必填项（可从Pinterest平台获取）。<strong>任一字段的缺失都将导致事件回传失败。</strong>请确保在Pinterest**活跃对接**页面中正确填写这两个参数。有关详细信息, 请参阅<Anchor target="_blank" href="/marketers/zh/docs/pinterest-create-a-mobile-app-integration#应用内事件设置">知识库文章</Anchor>。  
           感谢您对此次迁移的配合与支持。
        2. **应用内事件映射和回传设置**
           1. <span class="af-ol-a"></span>请在合作渠道事件名称（Partner event name）”字段中将当前的Pinterest事件名称替换为新版Pinterest Conversions API的事件名称。例如，如果您目前填写的是pin\_add\_to\_cart，请改为add\_to\_cart。 有关更多信息，请参见此处<Anchor target="_blank" href="/marketers/zh/docs/pinterest-create-a-mobile-app-integration#inapp-event-postbacks">知识库文章</Anchor> 。

        | 事件名称（旧版） | 事件名称（新的转化API） |
        | --- | --- |
        | pin\_add\_to\_cart | add\_to\_cart |
        | pin\_purchase | checkout |
        | pin\_search | search |
        | pin\_registration | signup |
        | pin\_sign\_up | signup |
        | pin\_category\_view | view\_category |
        | add\_cart | add\_to\_cart |
        | start\_checkout | checkout |
        | content\_view | view\_category |

              **注意：** 如果未将旧版事件名称更新为Conversions API要求的新事件名称，Pinterest将无法显示正确事件名称，事件将被归为“Other”(其他)。
           2. 将**应用内事件回传窗口**设置为**生命周期内（Lifetime）**，以便Pinterest接收到尽可能多的转化数据用于广告优化。
           3. 请在**To users from**选项中选择**包括自然流量在内的所有媒体渠道**，以便Pinterest接收到尽可能多的转化数据用于广告优化。有关更多信息，请参见此处<Anchor target="_blank" href="/marketers/zh/docs/pinterest-create-a-mobile-app-integration#inapp-event-postbacks">知识库文章</Anchor> 。
        3. **回滚处理流程**  
           建议广告主持续监控Pinterest上AppsFlyer应用的转化数据，以便及时发现迁移过程中可能出现的问题。AppsFlyer的转化数据通常在Pinterest上最多可能延迟30分钟才会显示，请在迁移后的几天内定期检查数据，以确认迁移是否成功。  

           如迁移过程中遇到问题，您通过省略`account_id`或`access_token`的方式，回滚至旧端点。 

           **操作规则：**

           * `account_id`和`access_token`均不填写→回传将发送到旧端点。
           * 仅填写`account_id`（即`access_token`为空）→回传将发送至旧端点。
           * 仅填写`access_token`（即`account_id`为空）→回传将发送至旧端点。
           * 同时填写`account_id`和`access_token`→回传将发送至新端点。

           如遇任何问题，请通过support@appsflyer.com联系AppsFlyer技术支持团队。有关Pinterest的任何问题，请联系api-support@pinterest.com或您的Pinterest代表。
      </td>
    </tr>
  </tbody>
</Table>

<div data-zendesk-anchors="h_01K0VD1AY1XVQWA6JP0WCQP8RN=%E6%B3%A8%E6%84%8F" />
