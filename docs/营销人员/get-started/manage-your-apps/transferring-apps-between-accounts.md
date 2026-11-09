---
title: 在不同账户之间迁移应用
metadata:
  keywords:
    - Account
    - Advertisers
    - Agencies
    - moving apps
    - move app
    - app transfer
    - transferring apps
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2018-07-24T07:56:37Z'
  edited_at: '2026-10-30T12:27:34Z'
  id: 360001336005
  locale: zh-cn
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/zh-cn/articles/360001336005
---
> **At a glance:** 账户管理员可以按照本文介绍的步骤，在不同的 AppsFlyer 账户之间迁移应用，迁移双方的账户管理员均需参与此流程。

<Image align="center" alt="应用迁移流程动画：展示应用迁移向导的各个操作步骤。" src="https://files.readme.io/f4288a79bbd96e8cf828cf0ca9ae9ef994400f702cd66108d2861e3a405c4d79-360010967257.gif" />

<div id="app-transfer-between-accounts" />

## 账户间应用迁移

在不同 AppsFlyer 账户之间迁移应用时，转出方和接收方的应用所有者（即双方 AppsFlyer 账户的所有者）都必须满足相应的迁移条件，并同意此次迁移。

<div id="prerequisites" />

### 迁移前提条件

* 已获取转出方和接收方账户所有者的电子邮箱地址。
* 双方账户均处于正常启用状态。已暂停的账户无法转出或接收应用。
* 双方账户均无未支付的账单。
* 只有<Anchor target="_blank" href="/marketers/zh/docs/user-management#账户所有者">账户所有者</Anchor>可以迁移应用。账户管理员角色无权执行此操作。
* 应用只能迁移至采用 Growth 或 Enterprise 套餐的账户。<Anchor target="_blank" href="/marketers/zh/docs/account-management-plans-payments-and-billing#appsflyer-plans">了解详情</Anchor>。

<div id="app-transfer-process" />

### 应用迁移流程

应用迁移的主要步骤如下：

1. 转出方向 AppsFlyer 提交迁移申请，选择要迁移的应用，并填写接收方账户管理员的电子邮箱地址。
2. 接收方收到通知后，同意接收这些应用。
3. 转出方和接收方的账户管理员都会通过电子邮件以及<strong>「我的应用」</strong>页面收到待处理的迁移通知。   
   **注意：** 在迁移申请待处理期间，任一方的账户管理员都可以删除该迁移申请，取消此次迁移。
4. AppsFlyer 将应用迁移至接收方账户。如果尚有前提条件未满足，AppsFlyer 会联系相关方，协助完成必要的准备工作。

<Accordion title="应用迁移范围">

下表说明应用迁移时，各项功能和设置是否会一并迁移。请注意，转出方可以自行决定是否在迁移前删除部分设置和配置信息。

<table><thead><tr><th>项目</th><th>是否迁移</th><th>说明及注意事项</th></tr></thead><tbody><tr><td>应用设置 </td><td>是</td><td> <strong>转出方可自行决定：</strong>迁移前可以删除 Firebase/GCM 服务器密钥。 </td></tr><tr><td rowspan="2">已对接的合作伙伴</td><td>是</td><td><p>对接配置、成本配置和收入配置均会迁移，包括相关成本数据和收入数据。</p><p><strong>转出方可自行决定：</strong>如果接收方不需要迁移已对接的合作伙伴，转出方应先停用这些合作伙伴，并删除相关配置和凭据，包括成本及广告收入配置。</p></td></tr><tr><td>否</td><td><p>广告平台和代理机构的权限</p><p>Twitter 配置和凭据</p></td></tr><tr><td>链接管理</td><td>否</td><td><p>OneLink 模板和链接不会自动迁移，但可以联系客户成功经理（CSM）协助迁移。 </p><p><strong>迁移模板和链接：</strong>请联系您的 CSM，或发送邮件至 <a href="mailto:hello@appsflyer.com">hello@appsflyer.com</a>。 <br/><strong>注意：</strong>批量链接会随所属模板自动迁移。</p><ul><li>转出方可以在迁移前删除不再使用的链接。</li><li>OneLink API 令牌无法在不同账户之间迁移。您需要使用新账户中的<a href="./managing-appsflyer-tokens" target="_blank">令牌</a>。</li></ul><p>域名跳转允许列表也不会自动迁移。如果接收方账户的允许列表中尚未包含待迁移应用使用的域名，迁移后，使用这些域名的链接将无法正常跳转。请务必在迁移前或迁移完成后立即，在接收方账户中<a href="./set-up-your-domain-redirect-allowlist" target="_blank">配置域名跳转允许列表</a>。</p></td></tr><tr><td>Push API</td><td>是</td><td><p><strong>转出方可自行决定：</strong></p><ul><li>如果接收方不需要迁移 Push API 配置（端点），转出方应提前删除相关设置。否则，数据仍会发送至转出方配置的端点。</li><li>接收方也可以在收到应用后修改相关设置，确保转出方无法继续接收用户级数据。 </li></ul></td></tr><tr><td>Smart Banners</td><td>否</td><td>横幅、横幅组、创意素材和网站均不会迁移。 </td></tr><tr><td>Smart Script</td><td>否</td><td>在 AppsFlyer 界面中创建的 Smart Script 不会在新账户中显示。 </td></tr><tr><td>代理机构</td><td>否</td><td>代理机构将失去对该应用的访问权限。</td></tr><tr><td>受众群体</td><td>否</td><td>受众群体将被删除。</td></tr><tr><td>成本导入</td><td>不适用</td><td>接收方无法访问历史成本导入文件。但不会影响历史成本数据。 </td></tr><tr><td>Data Locker</td><td>否</td><td>该应用将从 Data Locker 配置中移除，转出方账户也将停止接收该应用的数据。 </td></tr><tr><td>历史数据</td><td>是</td><td> </td></tr><tr><td>PBA 品牌套件</td><td>否</td><td><p>如果转出方迁移了品牌套件中的任何一个关联应用，该品牌套件将不再对转出方可用。接收方也无法访问 PBA 数据。</p><p>这意味着，如果客户希望在新账户中继续使用 PBA，必须在应用迁移完成前删除原有的 Web 套件，否则将无法在新账户中创建相同的 Web 套件。</p></td></tr><tr><td>Protect360 数据</td><td>是</td><td><p>如果应用从未启用 Protect360 的账户迁移至已启用 Protect360 的账户： </p><ul><li>只有在应用迁移完成后，系统才会开始检测作弊行为。</li><li>如果接收方账户仅在部分时间段内启用了 Protect360，则只能查看该功能启用日期之后的作弊数据，无法追溯获取此前的数据。</li><li>应用迁移期间不会进行作弊检测。</li></ul></td></tr><tr><td>原始数据和汇总数据</td><td>是</td><td> </td></tr><tr><td>SDK 开发密钥</td><td>是</td><td> </td></tr><tr><td>验证规则</td><td>是</td><td> </td></tr></tbody></table>

</Accordion>

<div id="transfer-procedures" />

## 迁移操作流程

如需将一个或多个应用迁移至其他 AppsFlyer 账户，请先发起迁移申请，然后按照界面中的向导完成操作。

<Accordion title="转出方">

**提交迁移申请**：

1. 联系接收方账户管理员：
   1. 与接收方共同确认[应用迁移范围](/docs/transferring-apps-between-accounts#app-transfer-scope)。确保双方都清楚哪些内容会迁移、哪些内容不会迁移，并已做好相应准备。
   2. 请接收方提供其用于登录 AppsFlyer 的账户管理员电子邮箱地址。
2. 请执行以下操作之一：
   * 如需迁移单个应用：在顶部菜单栏中，选择**我的应用** > 点击应用操作菜单（...）> 选择**迁移应用**。
   * 如需迁移 2 个或以上应用：在顶部菜单栏中，选择**我的应用** > 点击应用操作菜单（...）> 选择**迁移应用**。
3. 选择要迁移的一个或多个应用。
4. 点击**下一步**。
5. 输入接收方账户管理员的电子邮箱地址。
6. 点击**下一步**。
7. 阅读并签署条款与条件。
   * 申请成功提交后，您和接收方都会收到电子邮件通知。
   * 如果申请需要 AppsFlyer 协助处理，系统会通过弹出提示告知您。
   * 申请提交后，待迁移的应用会显示在您的<strong>「我的应用」</strong>页面中，并标记为「正在迁移至 `<接收方邮箱地址>`」。此时，您仍然可以删除申请，取消此次迁移。

     <Image align="center" alt="示意图：转出方的「我的应用」页面显示待迁移的应用及「删除申请」选项。" src="https://files.readme.io/5e4762461afd7953657b91074054bd79a63ad5bf8a06d084ee4c655ac60088aa-360010128998.jpg" />

</Accordion>

<Accordion title="接收方">

1. 联系转出方账户管理员，共同确认[应用迁移范围](/docs/transferring-apps-between-accounts#app-transfer-scope)。确保双方都清楚哪些内容会迁移、哪些内容不会迁移，并已做好相应准备。
2. 收到转出方发起迁移申请的电子邮件通知。
3. 在<strong>「我的应用」</strong>页面中，点击**审核申请**。一份申请可以包含一个或多个应用。

   <Image align="center" alt="示意图：接收方的「我的应用」页面显示待处理的应用迁移申请及「审核申请」选项。" src="https://files.readme.io/696264fdbc5d2a05c314deabc3ce6410fc211c421b96b7518e4a8c4958b30553-360010129018.jpg" />
4. 审核每项申请，并选择批准或拒绝。
5. 阅读条款与条件；如果接受相关条款，请签署确认。
6. 申请获批后，您和转出方都会收到电子邮件通知。
7. 迁移完成后，相关应用会显示在您的<strong>「我的应用」</strong>页面中。

</Accordion>

<Accordion title="删除迁移申请">

在应用迁移最终完成之前，转出方或接收方的账户管理员均可删除申请，取消此次迁移。

**删除迁移申请的具体操作如下：**

* **转出方取消申请：** 在顶部菜单栏中，选择**我的应用** > 找到<strong>「正在迁移至 [邮箱地址]」</strong>部分 > 点击**删除申请**。   
  删除申请后，转出方和接收方的账户管理员都会收到电子邮件通知。
* **接收方取消申请：**
* 在顶部菜单栏中，选择**我的应用** > 找到<strong>「待接收的应用」</strong>部分 > 点击**拒绝**。   
  拒绝申请后，转出方和接收方的账户管理员都会收到电子邮件通知。

</Accordion>

<div data-zendesk-anchors="app-transfer-between-accounts=%E8%B4%A6%E6%88%B7%E9%97%B4%E5%BA%94%E7%94%A8%E8%BF%81%E7%A7%BB h_01HJR1G7Q71H5DAH1G9QFSYK35=%E8%B4%A6%E6%88%B7%E9%97%B4%E5%BA%94%E7%94%A8%E8%BF%81%E7%A7%BB prerequisites=%E8%BF%81%E7%A7%BB%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01HJR1G7Q7T1Q768MTTR3Y542X=%E8%BF%81%E7%A7%BB%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 app-transfer-process=%E5%BA%94%E7%94%A8%E8%BF%81%E7%A7%BB%E6%B5%81%E7%A8%8B h_01HJR1G7Q7EDJZ4E1T17GWYGTP=%E5%BA%94%E7%94%A8%E8%BF%81%E7%A7%BB%E6%B5%81%E7%A8%8B transfer-procedures=%E8%BF%81%E7%A7%BB%E6%93%8D%E4%BD%9C%E6%B5%81%E7%A8%8B h_01HJR1G7Q7JB0XD3NGT0MWYJZ5=%E8%BF%81%E7%A7%BB%E6%93%8D%E4%BD%9C%E6%B5%81%E7%A8%8B" />
