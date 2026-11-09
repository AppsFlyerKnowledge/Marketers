---
title: 用户邀请归因
metadata:
  keywords:
    - OneLink
    - Advertisers
    - User invite
    - Developers
    - Marketers
    - Text-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Text-to-App
  created_at: '2017-08-30T12:13:45Z'
  edited_at: '2026-10-14T10:12:27Z'
  id: 115004480866
  locale: zh-cn
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/zh-cn/articles/115004480866
---
> **概要：** 当现有用户向其他人推荐您的应用，从而产生新用户时，您可以通过这个功能对这类激活进行归因和记录。

<Image align="center" alt="Invite_Attribution_new.png" src="https://files.readme.io/ee6793f57e16e7b051d1651108d7408482dff15501d9d786b5ca250e71d54ed4-360002880777.png" />

<div id="about-user-invite-attribution" />

## 用户邀请归因简介

用户邀请是指您的现有用户分享推广链接，引导其他人（比如好友）下载/打开您的应用。

用户邀请归因是指将新增的应用激活或互动归因到发送邀请/推荐的用户。

用户邀请归因适用于：

* 分析用户邀请的成本和ROI。由于用户邀请会占用相关应用中的广告位，而这些广告位本可用于广告变现。因此您可能需要对比用户邀请和广告变现哪一个能产生更高的ROI，从而作出相应决策。
* 对于完成邀请/推荐最多的用户，记录其相关信息，因为这些是高价值的深度用户，所以您可能需要对其进行定向投放或发放任务奖励。

您还可以使用用户邀请链接中的数据完成以下工作：

* 为受邀的新用户打造专属体验。比如打开应用后立即进入相关页面；或展示一条定制化的消息，如“John，你好！你的朋友Maria想要跟你对战一局。马上开始游戏！”
* 向完成推荐/邀请的用户发放奖励。[详情请见此处说明。](/docs/user-invite-attribution#reward-referrers-for-user-invite-installs)

用户与他人分享的邀请链接实际就是OneLink自定义链接（短链），这些链接由接入您应用的AppsFyer SDK生成。您可以通过调整OneLink链接的设置，确保受邀用户跳转到正确的位置—不管是进入适配的应用商店、打开相关应用，还是通过深度链接/延迟深度链接进入应用中的具体页面。<Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">进一步了解OneLink</Anchor>

<div id="flow" />

### 链路

用户邀请场景中的归因链路如下：

1. 用户A从其应用内点击相关按钮，与某个好友分享该应用（前提是用户A已完成应用激活且已登入其账号）。
2. 用户A点击按钮后，AppsFlyer SDK会生成一条链接，其中带有用户A的标识参数。
3. 用户A通过邮件、WhatsApp或短信等方式将该链接发送给用户B。
4. 如果用户B：
   * 已在其设备中安装了相关应用，这时该应用会打开。用户B可以通过深度链接进入应用中的某个具体页面，并且/或者获得奖励。
   * 尚未在其设备中安装相关应用，这时用户B会跳转到适配的应用商店。用户B可以通过延迟深度链接，在应用首次打开时进入某个具体页面，并且/或者获得奖励。
   * 用户B完成某个应用内事件后，用户A可以获得奖励。

<div id="viewing-data" />

## 数据查看方式

您可以通过AppsFlyer的面板或报告来获取用户邀请相关的数据。在AppsFlyer面板中，您可以按下列维度筛选出用户邀请的归因数据：

* **媒体渠道**：应用邀请（App invites）。
* **channel**由营销人员设定。
* **营销活动**:由营销人员设定。

在AppsFlyer报告中，用户邀请的媒体渠道信息（即参数`pid`）由SDK发送，并以默认值填充`af_app_invites`。

<div id="procedures" />

## 设置流程

**请按以下方式创建用户邀请链接**：

1. 创建一个<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#创建onelink模板">OneLink模板</Anchor>。
2. 设定流量入口和媒体渠道参数的值。详见[参数说明](/docs/user-invite-attribution#parameters)。
3. 设定这些链接的使用场景。常见的场景包括：
   * 让新用户通过深度链接进入应用中的某个具体页面。
   * 记录发起推荐/邀请的用户。
   * 奖励新用户。
4. 请与您的安卓和iOS开发人员沟通，根据链接的使用场景选取合适的参数。详见[可用参数](/docs/user-invite-attribution#parameters)说明。
5. 让开发人员<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">部署深度链接</Anchor>（即在代码中写入相关参数需要实现的行为）。
6. 根据实际情况，让您的开发人员在下列平台中部署用户邀请：

   <Tabs>
   <Tab title="安卓">

   请参考Dev Hub中的[Android用户邀请](https://dev.appsflyer.com/hc/docs/dl_android_user_invite)部署说明。

   </Tab>

   <Tab title="iOS">

   请参考Dev Hub中的[iOS用户邀请](https://dev.appsflyer.com/hc/docs/dl_ios_user_invite)部署说明。

   </Tab>

   <Tab title="Unity">

   请参考Dev Hub中的[用户邀请](https://dev.appsflyer.com/hc/docs/userinvite)部署说明。

   </Tab>
   </Tabs>

<div id="parameters" />

<Accordion title="参数">

<div id="parametersvalues-provided-to-the-developer-to-implement-in-the-sdk" />

#### 下表列出了可以写入SDK的参数，您可以在空白列中填入所需的值，然后发送给开发人员进行部署。

<table><thead><tr><th>参数/值</th><th>说明</th><th>记录需要部署的参数值/使用场景</th></tr></thead><tbody><tr><td>OneLink template ID</td><td>包含所有基础设置，用作所有用户邀请链接的基础。使用场景示例:H5hv</td><td> </td></tr><tr><td>Channel</td><td>流量入口的名称，用于在AppsFlyer面板中按流量入口对归因到的转化进行分组，便于查看。</td><td> </td></tr><tr><td>Campaign</td><td>广告系列的名称，用于在AppsFlyer面板中按广告名称对归因到的转化进行分组，便于查看。</td><td> </td></tr><tr><td> <span>is_retargeting=true</span><br/> </td><td>用于标识针对现有用户进行再营销的广告系列。</td><td> </td></tr><tr><td>deep_link_value</td><td>可在受邀用户的设备中形成特定的体验，常用于指定用户跳转的页面。比如在一个售卖水果的应用中，可以通过深度链接让用户跳转到苹果的详情页。</td><td> </td></tr><tr><td>deep_link_sub1</td><td rowspan="10">可在受邀用户的设备中形成特定的体验，一般情况下，引导用户进入具体页面的行为通过deep_link_value来实现，因此这些参数可用于您需要的任何其他功能，例如发放奖励/优惠，或记录发起邀请/推荐的用户。 </td><td> </td></tr><tr><td>deep_link_sub2</td><td> </td></tr><tr><td>deep_link_sub3</td><td> </td></tr><tr><td>deep_link_sub4</td><td> </td></tr><tr><td>deep_link_sub5</td><td> </td></tr><tr><td>deep_link_sub6</td><td> </td></tr><tr><td>deep_link_sub7</td><td> </td></tr><tr><td>deep_link_sub8</td><td> </td></tr><tr><td>deep_link_sub9</td><td> </td></tr><tr><td>deep_link_sub10</td><td> </td></tr><tr><td>【可选】pid</td><td><p>您生成的链接中默认包含参数值为<code>af_app_invites</code>的媒体渠道（即<code>pid</code>参数）。 </p><p>如需更改该默认值，请让您的开发人员另行添加一个名为的自定义参数，并在其中填充您指定的值。<strong>请注意</strong>：在安卓平台中，此方式仅适用于V6.4.2及以上版本的SDK。</p></td><td> </td></tr><tr><td>Branded name</td><td>即品牌域名，用于在AppsFlyer面板中按品牌域名对归因到的转化进行分组，便于查看。</td><td> </td></tr></tbody></table>

</Accordion>

<div id="example" />

<Accordion title="示例">

Mark负责一个水果售卖应用的营销工作。他想要通过深度链接让用户进入一个具体水果的页面，其中带有指定的购买量选项。

他希望这条链接能通过用户邀请发送，并且在这类邀请带来应用激活和商品购买时奖励发出邀请的用户。

为了实现这些链路，Mark向相关的开发人员发送了下列参数和参数值，用于用户邀请链接的部署：

| 参数 | 参数值 | 说明 |
| --- | --- | --- |
| deep\_link\_value | fruit\_name | 用于通过AppsFlyer UDL方式实现的深度链接。 |
| deep\_link\_sub1 | promo\_code | 用于通过AppsFlyer UDL方式实现的深度链接。 |
| deep\_link\_sub2 | referrer\_id | 用于通过SDK创建的链接。 |
| param\_1 | referrer\_id | 将该参数添加到受邀用户完成的购买事件中，从而将购买关联到发起邀请的用户。 |
| Channel | mobile\_share | 用于归因以及AppsFlyer中的数据呈现。 |
| Campaign | summer\_sale | 用于归因以及AppsFlyer中的数据呈现。 |

</Accordion>

<div id="additional-information" />

## 其他相关信息

<div id="record-user-invites-as-inapp-events" />

<Accordion title="将用户邀请记录为应用内事件">

在用户发送邀请后将其作为一个应用内事件记录下来，有助于识别出发送邀请的用户以及带来这些用户的媒体渠道。

**如需将用户邀请记录为应用内事件，请按以下方式操作**：

* 发送一个<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#invite-af_invite">af\_invite事件</Anchor>。请让您的开发人员按照我们在Dev Hub中提供的指南完成部署工作。

**请注意**：您还可以在该事件中添加其他需要关联的参数。请根据您的业务需求选择合适的参数，从而掌握更多的上下文信息并扩充相关数据。<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#设置应用内事件">详情请见此处说明。</Anchor>

</Accordion>

<div id="reward-referrers-for-user-invite-installs" />

<Accordion title="奖励带来激活的邀请人">

**如需奖励带来激活的邀请人，请按以下方式操作：**

1. 请使用[deep\_link\_sub1-10中的一个参数](/docs/user-invite-attribution#parameters)来传递邀请人标识符（referrer ID）。
2. 让开发人员<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">部署深度链接</Anchor>（即在代码中写入相关参数需要实现的行为）。
3. 请让您的后端开发与应用开发合作，从AppsFlyer报告中获取referrer ID并奖励这些邀请人。

举例来说，

1. 用户A邀请用户B安装您的应用。
2. 用户B打开应用时，该应用会获得用户A的referrer ID。
3. 您的后端开发人员从AppsFlyer报告中获取该referrer ID。
4. 将用户A的referrer ID添加到您后端的奖励发放对象列表中
5. 用户A打开该应用时，检查其referrer ID是否在奖励发放对象列表中。若是，则向其发放奖励。

</Accordion>

<div id="reward-referrers-for-referred-user-actions" />

<Accordion title="奖励带来用户行为的邀请人">

**如需奖励带来了特定应用内事件的邀请人，请按以下方式操作：**

1. 根据实际需求创建相关<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#设置应用内事件">应用内事件</Anchor>。
2. 请让您的开发人员在该事件中添加一个参数（如param\_1），参数值为邀请人的referrer ID。**请注意**：该referrer ID最初在应用激活时通过您选定的[参数](/docs/user-invite-attribution#parameters)（即deep\_link\_sub1-10）记录。
3. 请让您的后端开发与应用开发合作，从AppsFlyer报告中获取referrer ID并奖励这些邀请人。

举例来说，

1. 用户A邀请用户B在您的应用中完成某个操作。
2. 当用户B完成该操作时，AppsFlyer会记录到一个应用内事件，其中带有用户A的referrer ID。
3. 您的后端开发人员从AppsFlyer报告中获取该referrer ID。
4. 将用户A的referrer ID添加到您后端的奖励发放对象列表中
5. 用户A打开该应用时，检查其referrer ID是否在奖励发放对象列表中。若是，则向其发放奖励。

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| SDK版本 | 必须接入4.8.0及以上版本的AppsFlyer SDK版本和4.17.0及以上版本的Unity SDK。 |
| <Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page"> 社交媒体应用的落地页</Anchor> | 通过用户邀请生成的链接不支持社交媒体应用落地页。 |
| 链接有效期（TTL） | 对于通过SDK用户邀请生成的OneLink短链，其默认有效期（TTL）为60天。每次有用户点击该链接时，有效期就会自动延长60天。 |
| 定价 | 各类账户套餐皆可免费使用 |
| iOS 14+ | 由于用户邀请不使用IDFA进行归因，因此完全不受iOS 14影响。 |
| URL ID | 您可以更改URL ID（即短链ID），以凸显您的推广内容，例如：[https://myapp.onelink.me/abc123/apples](https://myapp.onelink.me/abc123/apples)。URL ID不能超过50个字符，可以同时包含字母和数字。默认长度为8个字符。<br /><br />**请注意**：您仅可更改当前未被使用的URL ID。 |

</Accordion>

<div data-zendesk-anchors="about-user-invite-attribution=%E7%94%A8%E6%88%B7%E9%82%80%E8%AF%B7%E5%BD%92%E5%9B%A0%E7%AE%80%E4%BB%8B h_01H98E1CZ2AG8AW2H77SPPHFGR=%E7%94%A8%E6%88%B7%E9%82%80%E8%AF%B7%E5%BD%92%E5%9B%A0%E7%AE%80%E4%BB%8B flow=%E9%93%BE%E8%B7%AF h_01H98E1CZ234MRBWDEYGZFCDRE=%E9%93%BE%E8%B7%AF viewing-data=%E6%95%B0%E6%8D%AE%E6%9F%A5%E7%9C%8B%E6%96%B9%E5%BC%8F h_01H98E1CZ23FEAS8JJC7FFTFXD=%E6%95%B0%E6%8D%AE%E6%9F%A5%E7%9C%8B%E6%96%B9%E5%BC%8F procedures=%E8%AE%BE%E7%BD%AE%E6%B5%81%E7%A8%8B h_01H98E1CZ2VBCG0RREERW8FNJE=%E8%AE%BE%E7%BD%AE%E6%B5%81%E7%A8%8B h_01H98E1CZ2WE6DJW717C6AJWXD=parameters parametersvalues-provided-to-the-developer-to-implement-in-the-sdk=%E4%B8%8B%E8%A1%A8%E5%88%97%E5%87%BA%E4%BA%86%E5%8F%AF%E4%BB%A5%E5%86%99%E5%85%A5sdk%E7%9A%84%E5%8F%82%E6%95%B0%E6%82%A8%E5%8F%AF%E4%BB%A5%E5%9C%A8%E7%A9%BA%E7%99%BD%E5%88%97%E4%B8%AD%E5%A1%AB%E5%85%A5%E6%89%80%E9%9C%80%E7%9A%84%E5%80%BC%E7%84%B6%E5%90%8E%E5%8F%91%E9%80%81%E7%BB%99%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98%E8%BF%9B%E8%A1%8C%E9%83%A8%E7%BD%B2 h_01H98E1CZ2CANBK1T55DD103JB=%E4%B8%8B%E8%A1%A8%E5%88%97%E5%87%BA%E4%BA%86%E5%8F%AF%E4%BB%A5%E5%86%99%E5%85%A5sdk%E7%9A%84%E5%8F%82%E6%95%B0%E6%82%A8%E5%8F%AF%E4%BB%A5%E5%9C%A8%E7%A9%BA%E7%99%BD%E5%88%97%E4%B8%AD%E5%A1%AB%E5%85%A5%E6%89%80%E9%9C%80%E7%9A%84%E5%80%BC%E7%84%B6%E5%90%8E%E5%8F%91%E9%80%81%E7%BB%99%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98%E8%BF%9B%E8%A1%8C%E9%83%A8%E7%BD%B2 h_01H98E1CZ2NXCCYEV12JC6EMFG=example additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01H98E1CZ28T2SJ3YNY8TNCAZY=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01H98E1CZ2172W6845K099F814=record-user-invites-as-inapp-events h_01H98E1CZ316WWYK55XTN4C8JE=reward-referrers-for-user-invite-installs h_01H98E1CZ330FXG06A4MVQ56PW=reward-referrers-for-referred-user-actions h_01H98E1CZ3SPASZDF5CCY3T3B3=traits-and-limitations" />
