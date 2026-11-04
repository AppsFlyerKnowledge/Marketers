---
title: 跳转白名单的设置说明
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2024-05-15T11:31:00Z'
  edited_at: '2026-10-14T10:04:16Z'
  id: 25068636064529
  locale: zh-cn
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/zh-cn/articles/25068636064529
---
> **概要：** 设置用于跳转的域名白名单后，可保证用户跳转到经过验证的可靠地址，保障用户的数据安全以及贵司的品牌形象。

<div id="about-the-redirect-allowlist" />

## <Image alt="Main redirect allowlist image.png" src="https://files.readme.io/a13b1c4641f4b265ef93ba9b65c57b0a7891336d6f6c21e94dd2ff5d83b948d6-30258741325713.png" width="1340px" />关于跳转白名单

您可以通过跳转白名单为特定的根域名和子域名加白，仅允许相关链接跳转到带有这些域名的地址，防止您的链接受到未授权跳转、钓鱼攻击和作弊的侵害。启用白名单后，您通过AppsFlyer创建的链接仅会跳转到含有加白域名的网址。若网址中的域名未加白，用户点击链接后就会进入适配的应用商店。跳转白名单的适用范围包括：<Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">OneLink</Anchor>链接、通过<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#attribution-link-tab">渠道对接</Anchor>设置的单平台归因链接以及用于CTV、PC以及主机端的<Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-direct-attribution-links">直接归因链接</Anchor>。跳转白名单（以及自定义网页重跳转）功能仅对Growth和Enterprise套餐用户开放。

<div id="set-up-your-redirect-allowlist" />

## 跳转白名单的设置方式

您可以通过手动操作或CSV文件上传这两种方式来设置跳转白名单。在设置白名单之前，建议先与您的数据安全团队敲定需要加白的域名列表。

<div id="manual-setup" />

<Accordion title="手动设置">

**请按以下方式手动设置跳转白名单：**

1. 从页面顶部导航栏打开账户菜单（点击右上角的邮箱地址，打开下拉菜单）> **安全中心**。

![from account click security center Cropped.jpg](https://files.readme.io/4ee3279e382e97817a6b977f50bff7054868f03c22186ed2bd79d712e2316ad4-25381243839377.jpg)

2. 在**跳转白名单**部分，点击 **管理跳转白名单**。

<Image alt="Manage redirect allowlist with arrow.jpg" src="https://files.readme.io/e9cd8c263eb618b86d3c10b1d9fc367390dfd1f9b6cc12afd7ac5f37411ba25c-25644439175313.jpg" width="549px" />  

界面会打开**跳转白名单**的页面。

3.在**手动**选项卡的**域名**字段中输入一个根域名或子域名，然后点击**域名加白**。

<Image alt="Manually add domains.jpg" src="https://files.readme.io/95b37db2064ddba8c787d2dd5ac5ab2aa7698605f5c6eb3b4a59dd6324dee355-25103405228689.jpg" width="403px" />

* 仅可使用字母、数字、连字符和句点。
* 域名的开头和结尾必须使用字母或数字，且不能超过253个字符。
* 请勿添加“https://”等前缀。

另请参见[特点和局限性](/docs/set-up-your-domain-redirect-allowlist#特点与局限性)部分。

已加白的域名会出现在右侧列表中。

4. 点击**保存白名单**。

保存的跳转白名单将在一小时内生效。

</Accordion>

<div id="setup-via-csv-file" />

<Accordion title="通过CSV文件设置">

**如需通过CSV文件上传来设置白名单，请按以下方式操作：**

1. 从页面顶部导航栏打开账户菜单（点击右上角的邮箱地址，打开下拉菜单）> **安全中心**。  

![from account click security center Cropped.jpg](https://files.readme.io/4ee3279e382e97817a6b977f50bff7054868f03c22186ed2bd79d712e2316ad4-25381243839377.jpg)

2. 在**跳转白名单**部分，点击 **管理跳转白名单**。  
<Image alt="Manage redirect allowlist with arrow.jpg" src="https://files.readme.io/e9cd8c263eb618b86d3c10b1d9fc367390dfd1f9b6cc12afd7ac5f37411ba25c-25644439175313.jpg" width="530px" />  

界面会打开**跳转白名单**的页面。

3.点击**CSV文件**选项卡，然后按照**CSV文件说明**，创建一个包含可靠域名列表的文件。  
![CSV file upload.jpg](https://files.readme.io/2be73080048545f79e102e6f48df0db956e6739f156153c172c4fef5a2ea339f-25381979219345.jpg)

4. 在文件上传字段中，上传您准备好的CSV文件。

* 文件上传完毕后，AppsFlyer会对其进行解析，并验证其中的值。
* 有效值会自动出现在右侧列表中。
* 无效值不会被添加。界面会将无效值的相关信息显示在**上传状态**部分，方便您查看或更正无效值，然后重新上传。详情请见[特点和局限性](/docs/set-up-your-domain-redirect-allowlist#特点与局限性)部分。

5. 点击**保存白名单**。

保存后的跳转白名单将在一小时内生效。

</Accordion>

<div id="edit-the-redirect-allowlist" />

<Accordion title="跳转白名单的修改方式">

您可以随时在白名单中添加或删除相关域名。

**如需从白名单中删除某个域名，请按以下方式操作：**

1. 将鼠标悬停在右侧列表中您想要删除的域名上，界面会显示删除图标。
2. 点击该删除图标。
3. 点击**保存列表**，保存更改。

**请注意：** 更新后的跳转白名单会在一小时内对相关点击生效。

</Accordion>

<div id="traits-and-limitations" />

## 特点与局限性

| 特点 | 说明 |
| --- | --- |
| 设置方式 | <ul><li>相关账户下具有管理员和数据安全角色的用户可以访问并管理跳转白名单。</li><li>跳转白名单是账户级别的设置，因此会对相关账户下的所有应用以及AppsFlyer链接生效。</li><li>跳转白名单（以及自定义网页跳转）功能仅对Growth和Enterprise套餐用户开放。对于关联到多个账号的团队成员，如果某个关联账号中没有支付方式信息，则该团队成员无法使用跳转白名单。</li><li>请通知负责AppsFlyer链接创建的同事及相关人员，确保其知悉跳转白名单的部署计划以及允许跳转的域名。</li></ul> |
| 适用范围 | <ul><li>该白名单会对**所有通过AppsFlyer创建的链接**生效，包括<Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">OneLink链接</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#attribution-link-tab">渠道对接</Anchor>页面中生成的单平台链接以及用于CTV、PC和主机端的<Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-direct-attribution-links">直接归因链接</Anchor>，无论这些链接是在何时创建的。</li><li>请在白名单中添加所有设置为链接跳转值的URL域名，无论是自定义网站/落地页、Google Play/App Store或其他应用商店的网站。该白名单支持并保护以下各类跳转：<ul><li>链接参数：<ul><li>`af_r`</li><li>`af_web_dp`</li><li>`af_ios_url`</li><li>`af_android_url`</li></ul></li><li>在OneLink模板中针对iOS、安卓和PC端设置的跳转</li><li>参数值为特定网址的`af_dp`，但不建议使用这类值。该参数一般用于填充<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_dp">URI scheme</Anchor>，以打开相关应用。</li></ul></li></ul> |
| 域名 | <ul><li>白名单中必须至少包含一个域名。</li><li>仅可配置根域名或子域名，切勿使用具体路径。请勿在域名值中添加“https://”或“http://”协议。</li><li>在白名单中添加跟域名后，白名单会对该跟域名下的所有子域名生效。<br />举例来说，假设您已为跟域名“website.com”加白，则您的白名单同时也覆盖“abc.website.com”和“xyz.website.com”。</li><li>仅支持跳转至可公开访问的域名。</li><li>请不要为了确保链接跳转符合预期而使用AppsFlyer域名（如onelink.me、app.appsflyer.com等）或其他具有其专属跳转机制的域名（如bit.ly）。</li><li>该白名单中最多可以添加100个域名/子域名。您可以在跳转白名单的主页面中看到已加白的域名数量。</li></ul> |
| 跳转 | 如果您不确定相关链接跳转到的域名是否已加白：<br /><br />查看跳转白名单，确认其中是否包含该域名<br /><br />或<br /><br />使用<Anchor target="_blank" href="/marketers/zh/docs/discover-your-campaign-link-parameters-and-behavior">链接解析</Anchor>工具。如果该域名未加白，则您输入相关链接后，**跳转**下方的**参数**一栏中会出现提示，提醒您该域名未加白。 |

<div data-zendesk-anchors="overview=%E5%85%B3%E4%BA%8E%E8%B7%B3%E8%BD%AC%E7%99%BD%E5%90%8D%E5%8D%95 h_01HYTJSH4YMAJ3CV88KZ9JD9XR=%E5%85%B3%E4%BA%8E%E8%B7%B3%E8%BD%AC%E7%99%BD%E5%90%8D%E5%8D%95 set-up-your-redirect-allowlist=%E8%B7%B3%E8%BD%AC%E7%99%BD%E5%90%8D%E5%8D%95%E7%9A%84%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F h_01HY0BNRBEN91348744YME42SW=%E8%B7%B3%E8%BD%AC%E7%99%BD%E5%90%8D%E5%8D%95%E7%9A%84%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F h_01HY04JEK8J3664HE8J9783S61=manual-setup h_01HY04JEK8Y51EG3H6WFKHYYH4=setup-via-csv-file h_01HY04JEK840Q4DZ2SRMTB7HRE=edit-the-redirect-allowlist traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01J6S6HS0H0M6GQ81WGZ3XT0P9=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />
