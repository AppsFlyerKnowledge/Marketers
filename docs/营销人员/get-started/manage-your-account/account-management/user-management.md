---
title: 用户管理
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2021-10-17T11:54:49Z'
  edited_at: '2026-10-14T10:05:28Z'
  id: 4409128270481
  locale: zh-cn
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/zh-cn/articles/4409128270481
---
> **概要：** 本文主要讲解了如何创建并管理您账户中的AppsFlyer用户，以及如何为他们开放功能、应用及数据的权限。

<div id="overview" />

## 速览

AppsFlyer账户下可以有多个用户，而且您可以对每个用户的权限进行单独管理。您的账户下最多能有几个用户取决于您订购的套餐。

用户权限有三个维度：

* **角色**：该用户能够使用哪些功能、完成哪些操作
* **应用权限**：该用户对于现有及新增应用的权限
* **数据权限**：按媒体渠道及地理位置区分的数据权限
  * 重要提示！AppsFlyer的部分面板和功能的可用性取决于用户对渠道和地理位置数据的权限。详情请见相关面板和功能[列表](#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access)。

各维度下的权限是分开的。也就是说，您可以为某个用户分配一个能使用大部分功能的**角色**，但在**应用、媒体渠道和国家/地区维度限制该用户对这些功能的使用。** 只有[管理员角色](#管理员)具备所有功能、应用、媒体渠道和地理位置维度的权限，这在下文中有详细说明。

管理员可以[将同一个用户添加到多个账号](#multiple-accounts)，以便该用户在不同账号之间快速切换。

<div id="user-management-page" />

## 用户管理页面

**请按以下步骤进入用户管理页面：**

* 从页面顶部导航栏打开账户菜单（点击右上角的邮箱地址，打开下拉菜单）> **用户管理**。

[![user-management-page.jpg](https://files.readme.io/0ca6dd472b6f50bfde693bba9c131ce9454dc1df90e3a0fb029e2e05b2330db4-31780969019665.jpg)](https://files.readme.io/0ca6dd472b6f50bfde693bba9c131ce9454dc1df90e3a0fb029e2e05b2330db4-31780969019665.jpg)

<div id="users-tab" />

<Accordion title="用户选项卡">

**用户**选项卡中的表格显示了您账户中所有的现有用户。您可以以该表格为基础，创建、管理或移除用户。

“用户”选项卡的使用方式建议：

* 点击**用户**列的表头，按字母顺序对表格排序（升序/降序）。
* 使用搜索框查找具体用户。
* 点击**角色**列表头中的筛选图标 <Image alt="filter_icon.png" src="https://files.readme.io/1ceaac3efead3a218909988be1d50a2f0af93b07360f7197cd398b11d661992b-16162502598417.png" width="25px" />，按角色（包括临时角色）筛选用户
  * 在筛选条件下拉菜单中选择**无**，即可清除筛选条件。
* 点击**最近一次登录**列的标题，按用户最近一次登录AppsFlyer的日期进行排序。
  * **提示：** 您可以使用该功能来识别并[删除](#deleting-users)不活跃用户，阻止未授权用户登录您的账户。
* 使用复选框同时勾选并[编辑多个用户](#多用户编辑)。
* 仅向管理员开放的操作：点击页面右上角的下载图标<Image alt="download_icon.png" src="https://files.readme.io/fba5d56ceb7f6b3dc3191e5ec33c85ccbba0f7dc409ad0390de238c12b479b61-31780969029777.png" width="24px" />，下载CSV格式的完整用户列表。
  * 下载文件与**用户**页面中的表格各列内容相同。

</Accordion>

<div id="roles-tab" />

<Accordion title="角色选项卡">

**角色**选项卡显示了您账户中已界定的所有角色，包括：

* [预定义角色](#预定义角色)
* [您已创建的](#管理自定义角色)自定义角色
* 目前已分配的所有[临时角色](#临时角色)

每个角色旁边都会显示该角色下目前所包含的用户数。

点击左侧栏中任何角色的名称，即可查看该角色的所有可用功能详情。

</Accordion>

您可以尝试角色名称下方的各种可用操作，找到管理用户及其角色的最佳方式。

<div id="manage-users" />

## 管理用户

管理员可以创建新用户、将用户添加到多个账户、修改用户信息（如用户角色以及用户对应用和数据的权限）并删除用户。 其中部分操作可[通过专用的API批量完成](#通过api批量管理用户)。

<div id="creating-users" />

<Accordion title="创建用户">

<Embed title="用户管理" typeOfEmbed="youtube" url="https://www.youtube.com/embed/wLCXP5dFrKg" providerUrl="https://www.youtube.com" />

该页面用于用户的创建和修改，其中包括以下各个板块。请按下文说明填写相关字段。完成必要更改后，请点击页面右下角的**保存**按钮。

<div id="user-details" />

#### 用户详情

1. 进入**用户**选项卡，点击**新用户**。
2. 输入用户名（必填项）：
   * 可包含字母、数字、空格以及英文格式的句号（.）、连字符（-）、下划线（\_）、单引号（'）和双引号（"）。
   * 不能使用其他特殊字符。
3. 输入该用户的邮箱地址（必填项）：

   * 可包含字母、数字、美元符号（$）、井号（#）以及英文格式的撇号（'）、和号（&）、连字符（-）、下划线（\_）和句号（.）。
   * 不能两个句号连用（..）或使用其他的特殊字符。
   * 结尾的邮箱域名必须为有效域名。

   <div id="important" />

   > 🚧 **重要提示！**
   >
   > AppsFlyer平台通过用户的邮箱地址识别用户，所以：
   >
   > * 在不删除或重新创建某个用户的情况下无法更改其邮箱地址。
   > * 必须使用该用户能接收到邮件的有效邮箱地址。
   > * 该邮箱地址不能关联到任何AppsFlyer账户中的其他用户，[除非该用户关联到多个账户](#multiple-accounts)。如果您输入的邮箱地址已经有人使用（不管是您的账户还是其他账户中的用户），您会看到*Can't create this user*（无法创建该用户）的弹窗。 出现这种情况时，请按[下文中的排查步骤](/docs/user-management#troubleshooting-can-t-create-this-user)解决该问题。

4. 【可选】选择该用户所属的部门。

<div id="role" />

#### 角色

选择相关用户的角色（必须完成）—可以是预定义角色或您已创建过的自定义角色。

<div id="app-access" />

#### 应用访问权限

选择相关用户可访问的应用：

* 默认开放该账户下所有现有和新增应用的权限。如需更改该设置，请使用复选框来选择或取消具体应用的权限。
* 仅当用户具备所有现有应用的权限时，才能为其开放所有新增应用的权限。

<div id="data-access" />

#### 数据访问权限

按媒体渠道和国家/地区设置用户权限级别。确定是否向相关用户开放所有权限，或仅向其开放指定选项的权限。

<div id="note" />

> 📘 **注意**
>
> 如果相关用户仅具有部分媒体渠道或国家/地区的访问权限，则该用户无法使用某些[面板和功能](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access)。

<div id="media-sources" />

#### 媒体渠道

默认情况下设置为**所有选项**，即相关用户可访问该账户下的所有媒体渠道，包括后续添加的渠道。若仅选择特定的媒体渠道，则不包含后续添加渠道的访问权限。

<div id="note-1" />

> 📘 **注意**
>
> * 如果相关用户仅具有部分媒体渠道的访问权限，则无法使用某些[面板和功能](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access)。
> * 管理员以及账户安全相关的角色可以访问所有媒体渠道，不受限制。此设置无法更改。

**媒体渠道类型：**

媒体渠道的下拉菜单中会显示两类渠道：

* **付费媒体渠道：** 广告平台、自归因平台（SRN）和代理商
* **<span id="custom_media_sources"></span>自定义媒体渠道：** 即广告主预定义的媒体渠道，涵盖自有媒体链接、单平台链接、OneLink链接以及广告主在AppsFlyer以外的平台中创建的链接。

**媒体渠道列表的显示规则：**

* 显示最近24个月内产生流量的渠道，按流量产生的时间降序排列。
* 代理商在列表底部单独成组显示。
* 列表中最多包含1万个媒体渠道。
  * 最多可显示5000个广告平台、SRN及自定义渠道
  * 最多可显示5000家代理
* 每天更新一次。新近添加的媒体渠道仅在系统记录到其流量后的第二天才会呈现在列表中。
* 系统会将超过5年没有流量的渠道从列表中移除。

**默认设置的更改方式如下：**

1. 在**媒体渠道**标题下点击**所有选项**。
2. 界面会打开下拉菜单，您可以从中选择您允许该用户访问的渠道。

上述设置保存完毕后，该用户的面板就会仅显示选定渠道的数据。

<div id="geos" />

#### 国家/地区

此处的设置用于向相关用户开放**所有**或部分国家/地区的访问权限。默认开放所有国家/地区的访问权限。 如果相关用户仅具有部分国家/地区的访问权限，则无法使用某些[面板和功能](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access)。

**默认设置的更改方式如下：**

1. 在**地理位置**标题下，点击**全部**。
2. 界面会打开下拉菜单，您可以从中选择您允许该用户访问的具体地理位置。

<div id="user-activation" />

#### 用户激活

用户创建完毕后，您就能在用户列表中看到该用户，其名称旁会带有信封图标![pending_invitation_icon.png](https://files.readme.io/68ac08ab6e52191a592350f82996f7ade9d181773d0bdbc6e2cb60315b60a8f2-16162502609553.png)。这个图标表示平台已向该用户发送邀请邮件，正在等待其激活账户。该用户必须使用邮件中的链接激活其账户。激活链接的有效期为48小时，账户激活后信封图标就会消失。

<div id="note-2" />

> 📘 **注意**
>
> 如果用户未接收到邀请或链接过期，请[重新发送邀请](/docs/user-management#resending-a-user-invitation)。

</Accordion>

<div id="multiple-accounts" />

<Accordion title="将用户添加到多个账号">

您可以将相关用户添加到多个账号，并在每个账号下为其分配不同的角色。这样，使用不同账号的用户就无需重复输入登录证书。

<div id="log-in-to-multiple-accounts" />

#### 登录多个账户

用户可以通过所有登录方式进入多个账户: 凭证（用户名和密码）、<Anchor target="_blank" href="/marketers/zh/docs/implementing-and-using-2fa-login">双重身份验证</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/set-up-sso-authentication-with-your-identity-provider-idp">单点登录</Anchor>。

<div id="supported-accounts-and-users" />

#### 适用账户和用户

同一用户可登入多个广告主账户：在具备权限的情况下，广告主可以将用户添加到所有账户中。请参见局限性部分的说明。

<div id="limitations-on-adding-users-to-multiple-accounts" />

#### 将用户添加到多个账户的限制

* 此功能仅限广告主账户使用，且用户必须具有相关的用户管理权限。
* 用户只能在一个账户中担任[账户所有者](#账户所有者)的角色。在除此以外的其他账户中，该用户可以担任任何角色。
* 不能将尚未[激活账号](#用户激活)的用户添加到其他账户。

<div id="add-users-to-multiple-accounts" />

#### 将用户添加到多个账号

**请按以下方式将相关用户添加到多个账号：**

1. 登入相关账号，以在其中添加用户。
2. 点击菜单栏中的**电子邮件下拉菜单**>**用户管理**。
3. 在**用户**选项卡中，点击**新用户**。
4. 输入必填信息，选择相关用户在该账号中的角色，然后点击**保存**。
5. 重复第1-4步，将该用户添加到其他账号。

</Accordion>

<div id="editing-users" />

<Accordion title="编辑用户">

您可以对用户进行单独或批量编辑。

<div id="individual-editing" />

#### 单用户编辑

**请按以下步骤对单个用户进行编辑：**

1. 点击**用户**选项卡中的**操作**按钮<Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" />（位于用户行的最右边）。
2. 在菜单中选择**编辑**。
3. 根据需要编辑用户设置。
4. 除邮箱地址以外的所有设置都可以编辑（包括角色、应用、媒体渠道和地理位置）。
5. 点击**保存**。

<div id="multi-user-editing" />

#### 多用户编辑

您可以通过多用户编辑功能同时更改多个用户的账户权限，提高工作效率。该功能与**用户**选项卡中的搜索和筛选功能结合使用，非常有助于用户量较大时的用户管理。

<div id="note-4" />

> 📘 **注意**
>
> 您无法使用多用户编辑功能向用户分配管理员角色。

**请按以下步骤同时编辑多个用户：**

1. 在**用户**选项卡中勾选您想要编辑的用户。
   * 勾选表头的复选框可对所有可见用户进行全选。
   * 搜索框的右侧会显示当前已选用户的数量。请注意，[账户所有者](#账户所有者)是无法勾选的，也不会计入已选用户数中。
2. 表格右上方会显示一系列按钮：**角色、应用、媒体渠道**和**国家/地区**。
   * 如果选定的用户中有一个或多个具备新增应用权限，您就无法使用**应用**按钮（详情请见下文[临时角色的局限性](/docs/user-management#临时角色的局限性)）。
3. 点击按钮，选择您想要更改的权限。
4. 通过对话框或下拉菜单完成必要的更改。
   * 您所做的更改会应用到所有已选用户，所以在编辑时请认真仔细地进行操作。
5. 已编辑的用户会在表格中高亮标出，保存更改后会正常显示。保存更改前您还有机会做最后的检查并进行相应的确认或取消（下一步）。
6. 检查您所做的更改，点击**保存**确认更改，或点击**取消**撤销更改。

<div id="example" />

> 📄 **示例**
>
> * 您的账户中有30个用户，其中有10个用户被指定为**市场——部分权限**角色。
> * Alice、Bill和Charlie最近升职了，因此您想要将他们从**市场 - 部分权限**转移到市场角色。
> * Alice的工作主要支持名为Astounding的应用，Bill主要支持名为Beautiful的应用，Charlie主要支持名为Charming的应用。
>
> **步骤：**
>
> 1. 使用角色筛选<Image alt="filter_icon.png" src="https://files.readme.io/1ceaac3efead3a218909988be1d50a2f0af93b07360f7197cd398b11d661992b-16162502598417.png" width="25px" />功能来查看角色为**市场 - 部分权限**的用户
> 2. 将Alice、Bill和Charlie的角色改为**市场**：
>    * 在复选框中勾选Alice、Bill和Charlie。
>    * 点击**角色**按钮。
>    * 在下拉菜单中选择**市场**。
>    * 点击**保存**确认更改。
>    * 请注意，您确认了更改以后，**角色**筛选条件会清空，表格会显示所有用户。
> 3. 为Alice、Bill和Charlie开放相应的应用权限：
>    * 使用搜索框找到Alice，单独编辑其用户账户，为她开放Astounding的应用权限。
>    * 重复以上步骤，分别为Bill和Charlie开放Beautiful和Charming的应用权限。

</Accordion>

<div id="deleting-users" />

<Accordion title="删除用户">

可从相关账户中批量删除多个用户。

<div id="note-5" />

> 📘 **注意**
>
> * 账户所有者无法删除
> * 用户删除后无法恢复。

<span id="to-delete-users"></span>**删除用户的方法如下：**

1. 在**用户**选项卡中勾选您想要删除的用户。您可以使用搜索和筛选条件找到相关用户。
2. 选择用户后，点击出现在表格右上角的**删除**按钮。
3. 界面会弹出确认窗口，其中列出将要被删除的用户。点击**是的，删除**以确认。

</Accordion>

<div id="manage-users-in-bulk-via-api" />

### 通过API批量管理用户

某些用户管理操作可以通过<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/bulk-users-management-overview">专用API</Anchor>批量完成：

* [创建](https://dev.appsflyer.com/hc/reference/bulk-users-post)多个用户
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/bulk-users-delete">删除</Anchor>多个用户
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/bulk-users-get">获取</Anchor>多个用户的访问详情

该API支持平台上的主要用户管理功能，并会在出错时返回同样的报错消息。

<div id="manage-roles" />

## 管理角色

您必须为您AF账户下的每一个用户都分配一个角色，这些角色用于界定相关用户可以使用的AppsFlyer功能和可以完成的操作。如需了解具体内容，请在[用户管理](#roles-tab)页的**角色选项卡**中查看完整的分角色权限清单。

AppsFlyer账户中的角色共分为三种：[预定义角色](#预定义角色)、[自定义角色](#自定义角色)、[临时角色](#临时角色)（仅限部分场景）。

<div id="predefined-roles" />

### 预定义角色

AppsFlyer账户提供多种预定义角色：

* [管理员 - 特殊角色](#管理员)
* 团队经理
* 营销负责人
* 市场
* 市场 - 部分权限
* 协作方
* 财务
* 数据安全
* 质量保证

<div id="note-6" />

> 📘 **注意**
>
> 每个预定义角色的职能和权限都是固定的，即不能出现多个角色“混搭”。但是您可以随时将相关用户切换到另一个预定义或自定义角色，以调整其职能和权限（[账户所有者](#账户所有者)除外，具体请见下文）。

<div id="example-1" />

> 📄 **示例**
>
> 您给Bill Bates分配了**团队经理**的角色。在该角色中，Bill可以管理**OneLink模板**，但不能进入**我的套餐**或**付款**页面。
>
> **问：** 我把Bill指定为团队经理后，可以向他开放“我的套餐”和“付款”页面的权限吗？另外，我可以关闭他对OneLink模板的管理权限吗？
>
> **答：** 不可以。只要Bill还是团队经理，您就不能向他开放“我的套餐”和“付款”页面的权限，也不能关闭他的OneLink模板管理权限。您可以将Bill分配到其他的预定义角色，这样他的权限就会随之变化。或者您也可以为Bill创建一个自定义角色，根据具体情况为其配置所需的功能和权限。

<div id="admin" />

### 管理员

一个AppsFlyer账户可以有**一个或多个管理员**。此角色具有以下特性：

<div id="access" />

#### 进入

管理员角色具备**所有**的账户权限，包括：

* 所有功能和操作
* 所有的现行及新增应用
* 所有媒体渠道和地理位置

管理员角色的“全平台访问”属性是不能被更改或限制的。

<div id="manage-tokens" />

#### 管理令牌

只有具有管理员角色的用户可以 <Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">管理令牌</Anchor>：创建、重命名和删除API和S2S的令牌。

<div id="role-duplication" />

#### 角色复制

创建**自定义角色**时[不能复制](#管理自定义角色)管理员角色。

<div id="invite-new-partners-to-appsflyer" />

#### 在AppsFlyer中添加新的对接渠道

具有管理员角色的用户可以通过Partner Marketplace<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#在appsflyer中添加新的对接渠道">发送邀请链接</Anchor>，邀请尚未与AppsFlyer对接的合作渠道。

<div id="account-owner" />

### 账户所有者

在开设账户时创建的用户（即账户所有者）**默认为管理员角色**。账户所有者负责最初（即尚无其他账户管理员期间）的用户创建工作。

账号所有者具备区别于普通管理员的特殊属性。与其他管理员不同，账号所有者**无法**在[**用户管理**](/docs/user-management#用户管理页面)页面中被删除、移除管理员角色或进行任何修改。如果您需要更改账户所有者，请按[下列步骤](#changing-the-account-owner)进行操作。

<div id="custom-roles" />

### 自定义角色

AppsFlyer为平台所提供的各种预定义角色配置了相应的功能组合，旨在满足大部分的使用场景。因此，很多广告主不再需要对角色进行进一步的自定义配置。即使您还是需要额外的自定义配置，仍然可以使用预定义角色作为用户职能管理的基础，大幅简化您的工作。

详情请见[自定义角色管理](#管理自定义角色)。

<div id="temp-roles" />

### 临时角色

如果您的AppsFlyer账户是在之前的用户管理体系下创建的（账户类型仅分为管理员和团队成员），该账户中的所有用户在新体系下的权限是保持不变的。在这种情况下，大部分用户在现行体系中显示为**临时角色**。

详情请见[临时角色管理指南](#managing-temp-roles)。

<div id="get-roles-data-via-api" />

### 通过API获取角色数据

通过<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_roles">获取角色API</Anchor>，您可以获取当前账号中的角色列表及其对应的属性。

<div id="manage-custom-roles" />

## 管理自定义角色

<div id="creating-custom-roles" />

<Accordion title="创建自定义角色">

* **前期准备：** 仅[账户拥有者](#账户所有者)或具有 [管理员角色访问权限](#管理员)的用户可以创建自定义角色。

**自定义角色的创建方式如下：**

1. 在**角色**标签的左侧面板中，在搜索栏下方，点击 **+ 新建自定义角色**。
2. **角色名称：** 为您要创建的新角色命名。
   * **请注意：** 保存自定义角色后无法再更改该角色的名称。
   * **建议：** 使用具有说明性且易于识别的名称。
3. **角色模板：** 首先，请先选择一个与新建自定义角色所需功能和权限最为接近的预定义角色。
4. 根据您的自定义角色需求，调整所选角色模板的设置。所有可更改的功能权限级别会以按钮形式展示。您可以点击这些按钮来更改新建自定义角色的各种权限级别（请务必向下滚屏以查看所有的可用功能）。
   * **注意：** 未以按钮形式出现的功能当前不可编辑。
5. 为所有相关功能设置权限后，点击**保存角色**。  
   您可以在左侧栏中看到新创建的自定义角色，并在创建新用户或更新现有用户时使用该角色。

</Accordion>

<div id="editing-custom-roles" />

<Accordion title="编辑自定义角色">

**自定义角色的修改方式如下：**

1. 点击**角色**页左侧栏中您需要修改的自定义角色名称。
2. 点击页面右上角的**编辑** 图标<Image alt="edit-icon.jpg" src="https://files.readme.io/d32f150cb5d0271c5504fb3c107e23f73e59c9a3be1630769ad309edf4e79ea0-31780971794321.jpg" width="25px" />。右侧栏的内容会发生相应变化，便于您修改该角色的权限设置。
   * **注意：** 角色名称无法编辑。如需更改，您必须先删除该角色，然后使用其他名称重新创建一个新角色。
3. 所有可更改的功能权限级别会以按钮形式展示。您可以点击这些按钮来更改新建自定义角色的各种权限级别（请务必向下滚屏以查看所有的可用功能）。
4. 检查并确认您所选的各项设置，然后点击**保存角色**按钮。
5. 该角色的权限级别修改完毕，并对所有相关的新建和现有用户生效。

<div id="important-1" />

> 🚧 **重要提示！**
>
> 您对自定义角色所做的任何更改都会自动对该角色下的**所有现有用户**生效。

</Accordion>

<div id="deleting-custom-roles" />

<Accordion title="删除自定义角色">

**自定义角色的删除方式如下：**

1. 点击**角色**页左侧栏中您需要删除的自定义角色名称。
2. 点击页面右上角的**删除** 图标<Image alt="delete-icon.jpg" src="https://files.readme.io/87f206e21926af0836690be064a5af7cb3bce0007f0fc62301b2925701b1d9f9-31780971797265.jpg" width="24px" />。
3. 确认要删除该角色。
   * 仅当自定义角色下没有任何用户时才能被删除。如果某个自定义角色下还有用户，请先将这些用户分配到其他角色，然后再删除该自定义角色。

</Accordion>

<div id="special-situations-and-additional-procedures" />

## 特殊情况及其他操作

<div id="managing-temp-roles" />

<Accordion title="管理临时角色">

如果您的账户一直在用AF原先的用户管理系统，那么为了确保现有用户的权限不受影响，新系统会向其分配[**临时角色**](/docs/user-management#临时角色)。

* 权限相同的用户会分配到的相同临时角色。
* 使用[角色选项卡](/docs/user-management#roles-tab)中的功能来查看每个临时角色的具体权限以及用户名单。

<div id="temp-role-limitations" />

#### 临时角色的局限性

设立临时角色的目的是为了确保新旧用户管理系统之间的无缝衔接，因此这些角色具有以下局限性：

* 不能向非临时角色的用户（无论是新用户还是现有用户）分配临时角色。
* 不能将用户从一个临时角色转换到另一个临时角色（但可以更改其应用、媒体渠道和地理位置维度的权限）。
  * 请注意：临时角色用户对新增应用的权限**无法**更改。
* 临时角色用户一旦转换到预定义角色，就无法再转回先前的临时角色（或转换到其他临时角色）。
* 移除某个临时角色中的最后一位用户后，您的账户中就不会再出现该角色。

<div id="example-2" />

> 📄 **示例**
>
> 您的账户之前一直在用AF原先的用户管理系统。迁移到新系统时，Diana和Edward已经是账户中的现有用户。现在，Diana是临时角色1，Edward是临时角色2.
>
> * 您雇用了新员工Fiona。您可以为Fiona分配任意一个[预定义角色](/docs/user-management#预定义角色)，但不能分配临时角色1或临时角色2。
> * 您不能将Diana从临时角色1转移到临时角色2，但可以将其分配到任意一个预定义角色，并根据需要更改其应用、媒体渠道、地理位置维度的权限。
> * 如果您将Diana的角色从临时角色1转换到财务，那么她无法再回到临时角色1。
> * 如果Diana是临时角色1的最后一个用户，那么在您将其转换到财务角色后，您的账户中就不会再出现临时角色1。

</Accordion>

<div id="dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access" />

<Accordion title="媒体渠道/地理位置权限受限用户的面板和功能可用性">

如果您仅具备部分渠道和地理位置的数据权限，则**无法使用**下列AppsFlyer面板：

* SKAN总览面板
* SKAN转化值操作台
* Protect360
* 留存
* 基于用户的归因（PBA）
* 增量分析

在这种情况下，下列AppsFlyer功能也**不可用**：

* 数据透视表
* OneLink
* 验证规则
* 受众（不对媒体来源受限用户开放;地理限制用户只能访问包含“国家”过滤器的受众，且仅限于其授权访问的国家）
* SDK信息
* 广告消耗数据上传
* Cost ETL

</Accordion>

<div id="changing-the-account-owner" />

<Accordion title="更改账户拥有者">

由于账户管理员的权限与账户所有者基本一致，因此一般情况下无需更改账户所有者。但如果您一定要更改账户所有者，可以按以下步骤操作：

<div id="important-2" />

> 🚧 **重要提示！**
>
> 更改账户所有者必须按以下步骤手动操作，不能在**用户管理**页面更改。

<div id="1assign-a-team-member-the-admin-role" />

#### #1–分配一名团队成员管理员角色

更改账户所有者只能向拥有管理员角色的用户请求。因此，建议你：

* 指派一名团队成员完成所有步骤**行政**角色。
* 用户必须激活账户（即至少登录一次）。

<div id="2send-an-email-request" />

#### #1—发送邮件请求

拥有管理员角色的用户必须向 AppsFlyer 发送电子邮件请求 **来自当前账户持有者的邮箱地址。**

* 请确保该邮箱与AppsFlyer中的账户所有者邮箱一致。
* 如果当前的账户所有者已从贵司离职，请让贵司IT人员帮助您从该账户所有者的邮箱发送邮件。

请在申请邮件中说明以下信息：

| 收件人： | 您的AppsFlyer CSM或hello@appsflyer.com |
| --- | --- |
| CC： | 新账户所有者的邮箱 |
| 主题： | Request to change the account owner for （申请更改「账户名」的账户所有者） |
| 正文： | 简短说明新账户所有者的名字和职位 |

请参见下图的示例邮件：

![account_owner_change_email.png](https://files.readme.io/eb10736386a7a8cfc274979a3aa933e23288c74d1b26c0f06d72005ceebafe06-31780969048081.png)

<div id="3next-steps" />

#### #2–后续操作

申请处理完成后，您会收到AppsFlyer的邮件通知。

* 如果您想让原来的账户所有者继续使用您的AppsFlyer账户，请为其[创建新用户](/docs/user-management#creating-users)并分配新角色。
* 账户所有者发生变更时，使用token v2的API不受影响。<Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">进一步了解token的管理方式</Anchor>。

</Accordion>

<div id="troubleshooting-can-t-create-this-user" />

<Accordion title="问题排查：无法创建此用户">

如果您输入新用户邮箱地址后收到“*Can’t create this user*“（无法创建该用户）的报错消息，通常是因为该邮箱已关联了某个AppsFlyer的现有用户（可能是您账户下的用户，也可能是其他账户的用户）。请根据实际情况进行以下操作：

如果该用户在您的账户中：

* 检查该用户是否已激活其账号。如果尚未激活，请根据需要[重新发送邀请](/docs/user-management#resending-a-user-invitation)。
* 如果该用户已激活其账号，则让其使用关联邮箱重新登录。如有需要，请建议该用户点击**忘记密码**并按相关步骤更改密码。

如果该邮箱关联到了另一个账户，或者您无法确定该邮箱所关联的账户，您可以通过以下任意一种方式来解决此问题：

* 在另一个账户中删除该用户，并将其添加到您的账户中（前提是您或该用户在另一个账户内有所需权限）；或
* 使用其他邮箱地址，将该用户添加到您的账户中。请确保邮箱地址有效且用户可通过该邮箱接收邮件。
* 联系您的客户成功经理（CSM）或发送邮件到[hello@appsflyer.com](mailto:hello@appsflyer.com)联系我们的客户融合团队。

</Accordion>

<div id="resending-a-user-invitation" />

<Accordion title="重新发送用户邀请">

如果新用户未收到[账号激活邀请](#用户激活)或未在48小时内激活账号，请按以下步骤重新发送邮件：

1. 点击**用户**选项卡中的**操作**按钮<Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" />（位于用户行的最右边）。
   * 请注意，该用户在表格中应仍带有信封图标![pending_invitation_icon.png](https://files.readme.io/68ac08ab6e52191a592350f82996f7ade9d181773d0bdbc6e2cb60315b60a8f2-16162502609553.png)，表示其账户尚未激活。
2. 在菜单中选择**重新发送邮件邀请**。

</Accordion>

<div id="resetting-twofactor-authentication-2fa" />

<Accordion title="重置用户的双重身份验证 (2FA)">

如果您的账户使用2FA，有时可能会需要重置个别用户的2FA设置。发生这种情况时，请按以下步骤进行重置：

1. 点击**用户**选项卡中的**操作**按钮<Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" />（位于用户行的最右边）。
2. 在菜单中选择**重置2FA**。

**注意：** 管理员可以重置任何其他管理员的2FA，但不能重置自己的2FA或[账户所有者](#账户所有者)的2FA。如需重置账户所有者的2FA，请联系AppsFlyer技术支持团队。

</Accordion>

<div data-zendesk-anchors="background=%E9%80%9F%E8%A7%88 h_01H9Q9007QP8YMPDVZ57N4M1HD=%E9%80%9F%E8%A7%88 user-management-page=%E7%94%A8%E6%88%B7%E7%AE%A1%E7%90%86%E9%A1%B5%E9%9D%A2 h_01H9Q9007QW1RD3MTTV01Q8QRE=%E7%94%A8%E6%88%B7%E7%AE%A1%E7%90%86%E9%A1%B5%E9%9D%A2 h_01J6W88SQ45MA3AZ29K3WMW9PV=users-tab h_01J6W88SQ5B16Q897YMJ7ZNMQX=roles-tab managing-users=%E7%AE%A1%E7%90%86%E7%94%A8%E6%88%B7 h_01H9Q9007QYSJZYZMP0C8NA98G=%E7%AE%A1%E7%90%86%E7%94%A8%E6%88%B7 h_01H9Q9007QH3ME2P8PHC9DJBZV=creating-users user-details=%E7%94%A8%E6%88%B7%E8%AF%A6%E6%83%85 h_01HMP4EYM562HFSP80MQQ82B47=%E7%94%A8%E6%88%B7%E8%AF%A6%E6%83%85 h_01H9Q9007Q6SK4391P8C3A147N=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA role=%E8%A7%92%E8%89%B2 h_01HMP4Q56XP10343YFW17VX00W=%E8%A7%92%E8%89%B2 app-access=%E5%BA%94%E7%94%A8%E8%AE%BF%E9%97%AE%E6%9D%83%E9%99%90 h_01HMP4RDXVRM3Z0WDCJD3P2W8S=%E5%BA%94%E7%94%A8%E8%AE%BF%E9%97%AE%E6%9D%83%E9%99%90 data-access=%E6%95%B0%E6%8D%AE%E8%AE%BF%E9%97%AE%E6%9D%83%E9%99%90 h_01HMP4SW7RMESGDFNP1KFN7641=%E6%95%B0%E6%8D%AE%E8%AE%BF%E9%97%AE%E6%9D%83%E9%99%90 h_01HR6VBJHTZM48493B29FCWQT8=%E6%B3%A8%E6%84%8F media-sources=%E5%AA%92%E4%BD%93%E6%B8%A0%E9%81%93 h_01HRPRS4BHX2AMR9W4FNGE0N1P=%E5%AA%92%E4%BD%93%E6%B8%A0%E9%81%93 01HRPRSF0F8ENJ9ZAE1ZDTMAMB=%E6%B3%A8%E6%84%8F-1 geos=%E5%9B%BD%E5%AE%B6%E5%9C%B0%E5%8C%BA h_01HRPRVXYFX4P2ZG0H5HPNF2AG=%E5%9B%BD%E5%AE%B6%E5%9C%B0%E5%8C%BA user-activation=%E7%94%A8%E6%88%B7%E6%BF%80%E6%B4%BB h_01HFRCWNR8T5J990TV68K6B45T=%E7%94%A8%E6%88%B7%E6%BF%80%E6%B4%BB h_01HFRFRQXD1RD66EBRQH0T7Q78=%E6%B3%A8%E6%84%8F-2 01HFRF6SENRY51A4ZAQJTMTDA3=multiple-accounts log-in-to-multiple-accounts=%E7%99%BB%E5%BD%95%E5%A4%9A%E4%B8%AA%E8%B4%A6%E6%88%B7 h_01J2GN6ZA29SFC12HR4ZVBDFDT=%E7%99%BB%E5%BD%95%E5%A4%9A%E4%B8%AA%E8%B4%A6%E6%88%B7 supported-accounts-and-users=%E9%80%82%E7%94%A8%E8%B4%A6%E6%88%B7%E5%92%8C%E7%94%A8%E6%88%B7 h_01H9Z7XXE0CKRSE191ZN017MGE=%E9%80%82%E7%94%A8%E8%B4%A6%E6%88%B7%E5%92%8C%E7%94%A8%E6%88%B7 limitations-on-adding-users-to-multiple-accounts=%E5%B0%86%E7%94%A8%E6%88%B7%E6%B7%BB%E5%8A%A0%E5%88%B0%E5%A4%9A%E4%B8%AA%E8%B4%A6%E6%88%B7%E7%9A%84%E9%99%90%E5%88%B6 01J2GMV7ZYV5G0Q6C18RRY1TY0=%E5%B0%86%E7%94%A8%E6%88%B7%E6%B7%BB%E5%8A%A0%E5%88%B0%E5%A4%9A%E4%B8%AA%E8%B4%A6%E6%88%B7%E7%9A%84%E9%99%90%E5%88%B6 add-users-to-multiple-accounts=%E5%B0%86%E7%94%A8%E6%88%B7%E6%B7%BB%E5%8A%A0%E5%88%B0%E5%A4%9A%E4%B8%AA%E8%B4%A6%E5%8F%B7 h_01H9G1MP3Z7VCQQ8ZSQDGSWPC3=%E5%B0%86%E7%94%A8%E6%88%B7%E6%B7%BB%E5%8A%A0%E5%88%B0%E5%A4%9A%E4%B8%AA%E8%B4%A6%E5%8F%B7 h_01H9Q9007RTMXVRMR4RM6J80CW=editing-users individual-editing=%E5%8D%95%E7%94%A8%E6%88%B7%E7%BC%96%E8%BE%91 h_01H9Q9007R3QW4AYRJBTF0X7B9=%E5%8D%95%E7%94%A8%E6%88%B7%E7%BC%96%E8%BE%91 multiuser-editing=%E5%A4%9A%E7%94%A8%E6%88%B7%E7%BC%96%E8%BE%91 h_01H9Q9007R4JQPKQS2HVB251GH=%E5%A4%9A%E7%94%A8%E6%88%B7%E7%BC%96%E8%BE%91 h_01H9Q9007R9M9YDMJ2YYNZDW3D=%E6%B3%A8%E6%84%8F-3 h_01H9Q9007RAFXB899YK6CADD9R=%E7%A4%BA%E4%BE%8B h_01H9Q9007RF8QKS7YBZ1GRXVCF=deleting-users h_01HGTR4NEBYJZTW4BA5V9JJX5X=%E6%B3%A8%E6%84%8F-4 h_01HGTK2664A0R2RBJM37EYWNZG=to-delete-users manage-users-in-bulk-via-api=%E9%80%9A%E8%BF%87api%E6%89%B9%E9%87%8F%E7%AE%A1%E7%90%86%E7%94%A8%E6%88%B7 h_01HYASD07FG0HGX22FTHEQ9APP=%E9%80%9A%E8%BF%87api%E6%89%B9%E9%87%8F%E7%AE%A1%E7%90%86%E7%94%A8%E6%88%B7 more-about-roles=%E7%AE%A1%E7%90%86%E8%A7%92%E8%89%B2 h_01H9Q9007Q8CMR2RD6E4KN26YE=%E7%AE%A1%E7%90%86%E8%A7%92%E8%89%B2 predefined-roles=%E9%A2%84%E5%AE%9A%E4%B9%89%E8%A7%92%E8%89%B2 h_01H9Q9007Q28D43B6JRP71NDQM=%E9%A2%84%E5%AE%9A%E4%B9%89%E8%A7%92%E8%89%B2 h_01J6VZ7ANV3JHJZ5EVBF1BY585=%E6%B3%A8%E6%84%8F-5 h_01H9Q9007QXSGG375PR2SCS7QS=%E7%A4%BA%E4%BE%8B-1 admin%E2%80%94a-special-role=%E7%AE%A1%E7%90%86%E5%91%98 h_01H9Q9007Q4A6KETAAGAWEPQQ9=%E7%AE%A1%E7%90%86%E5%91%98 access=%E8%BF%9B%E5%85%A5 h_01HF8N2Z8ZP3HV06XJPMQ19DTK=%E8%BF%9B%E5%85%A5 manage-tokens=%E7%AE%A1%E7%90%86%E4%BB%A4%E7%89%8C h_01HV1F5S0FE083B73P8MEYX4FM=%E7%AE%A1%E7%90%86%E4%BB%A4%E7%89%8C role-duplication=%E8%A7%92%E8%89%B2%E5%A4%8D%E5%88%B6 h_01HF8N6DKWYKMBE35QKKB55KEM=%E8%A7%92%E8%89%B2%E5%A4%8D%E5%88%B6 invite-new-partners-to-appsflyer=%E5%9C%A8appsflyer%E4%B8%AD%E6%B7%BB%E5%8A%A0%E6%96%B0%E7%9A%84%E5%AF%B9%E6%8E%A5%E6%B8%A0%E9%81%93 h_01HVK8EB3SMC09VD8TJND9YWCD=%E5%9C%A8appsflyer%E4%B8%AD%E6%B7%BB%E5%8A%A0%E6%96%B0%E7%9A%84%E5%AF%B9%E6%8E%A5%E6%B8%A0%E9%81%93 account-owner=%E8%B4%A6%E6%88%B7%E6%89%80%E6%9C%89%E8%80%85 h_01HF8N69VYE3ZJVFW1ENC0XA62=%E8%B4%A6%E6%88%B7%E6%89%80%E6%9C%89%E8%80%85 custom-roles=%E8%87%AA%E5%AE%9A%E4%B9%89%E8%A7%92%E8%89%B2 h_01H9Q9007QZ7F2TX8B9D1TNYPN=%E8%87%AA%E5%AE%9A%E4%B9%89%E8%A7%92%E8%89%B2 temp-roles=%E4%B8%B4%E6%97%B6%E8%A7%92%E8%89%B2 h_01H9Q9007QE8YT1DNRPNTFQWYH=%E4%B8%B4%E6%97%B6%E8%A7%92%E8%89%B2 get-roles-data-via-api=%E9%80%9A%E8%BF%87api%E8%8E%B7%E5%8F%96%E8%A7%92%E8%89%B2%E6%95%B0%E6%8D%AE h_01J6VZ2XP6HM6NJ2TB5DJXD6SA=%E9%80%9A%E8%BF%87api%E8%8E%B7%E5%8F%96%E8%A7%92%E8%89%B2%E6%95%B0%E6%8D%AE managing-custom-roles=%E7%AE%A1%E7%90%86%E8%87%AA%E5%AE%9A%E4%B9%89%E8%A7%92%E8%89%B2 h_01H9Q9007RQHHNHZ3M38E88YPW=%E7%AE%A1%E7%90%86%E8%87%AA%E5%AE%9A%E4%B9%89%E8%A7%92%E8%89%B2 h_01H9Q9007RYZD19CFNSM60EARZ=creating-custom-roles h_01H9Q9007R6E6JGD8BC2WY8G3G=editing-custom-roles h_01H9Q9007RANMZP4T6S8R6WA1B=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 h_01H9Q9007R16190B6RB884FY61=deleting-custom-roles special-situations-and-additional-procedures=%E7%89%B9%E6%AE%8A%E6%83%85%E5%86%B5%E5%8F%8A%E5%85%B6%E4%BB%96%E6%93%8D%E4%BD%9C h_01H9Q9007RSWFVAZQ5DNVNN7T2=%E7%89%B9%E6%AE%8A%E6%83%85%E5%86%B5%E5%8F%8A%E5%85%B6%E4%BB%96%E6%93%8D%E4%BD%9C h_01H9Q9007RNZ28128XDB76ZVZC=managing-temp-roles temp-role-limitations=%E4%B8%B4%E6%97%B6%E8%A7%92%E8%89%B2%E7%9A%84%E5%B1%80%E9%99%90%E6%80%A7 h_01H9Q9007RJ0CQRGEYNEQJ2QR5=%E4%B8%B4%E6%97%B6%E8%A7%92%E8%89%B2%E7%9A%84%E5%B1%80%E9%99%90%E6%80%A7 h_01H9Q9007RHBYD2B6PHQRD7TWV=%E7%A4%BA%E4%BE%8B-2 h_01H9Q9007RRY6QERXQ0C4FSYCN=dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access h_01H9Q9007R221KXA7DFTXJY0PE=changing-the-account-owner h_01H9Q9007RR4M8V599A19B2M0F=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-2 1%E2%80%93send-an-email-request=1%E5%88%86%E9%85%8D%E4%B8%80%E5%90%8D%E5%9B%A2%E9%98%9F%E6%88%90%E5%91%98%E7%AE%A1%E7%90%86%E5%91%98%E8%A7%92%E8%89%B2 h_01H9Q9007RSA5406WXCB1E4JRK=1%E5%88%86%E9%85%8D%E4%B8%80%E5%90%8D%E5%9B%A2%E9%98%9F%E6%88%90%E5%91%98%E7%AE%A1%E7%90%86%E5%91%98%E8%A7%92%E8%89%B2 h_01K5P1G80QACK6YMKX4AGJA5ZK=1%E5%8F%91%E9%80%81%E9%82%AE%E4%BB%B6%E8%AF%B7%E6%B1%82 2%E2%80%93next-steps=2%E5%90%8E%E7%BB%AD%E6%93%8D%E4%BD%9C h_01H9Q9007RZ2X9RAY8067SZETF=2%E5%90%8E%E7%BB%AD%E6%93%8D%E4%BD%9C troubleshooting-can%E2%80%99t-create-this-user=troubleshooting-can-t-create-this-user h_01H9Q9007RR4VYEPGT90MEHV3T=troubleshooting-can-t-create-this-user h_01H9Q9007R11BQWQZC66X5FV0N=resending-a-user-invitation h_01H9Q9007R72FAH89XW58MWCXT=resetting-twofactor-authentication-2fa" />
