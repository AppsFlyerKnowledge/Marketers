---
title: 数据协作平台 （DCP） - 创建协作
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2025-01-28T14:17:59Z'
  edited_at: '2026-10-14T10:01:53Z'
  id: 32192739295377
  locale: zh-cn
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/zh-cn/articles/32192739295377
---
> **概要：** 合作使商业媒体网络和品牌能够利用组合数据来创造新的广告收入来源并实现最大的营销活动效果。

<div id="about-collaborations" />

## 关于合作

应用传单 <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-guide">数据协作平台 （DCP）</Anchor> 使商业媒体网络和品牌能够合作并释放其第一方数据的潜力，以吸引高意向用户。这个安全、以隐私为中心的平台可实现无缝协作，使合作伙伴能够产生新的广告收入来源，并从协作数据中构建自定义受众，以便在商业媒体网络或 Meta、Google 等媒体渠道中激活。

<div id="create-a-collaboration" />

## 创建协作

本节介绍如何创建新的协作。

**要创建协作，请按照以下步骤作：**

<div id="step-1-access-collaborations" />

<Accordion title="第1步：访问协作">

**要访问 DCP 协作：**

1. 通过单击 **合作** > **数据洁净室**，在AppsFlyer侧边菜单中。 

   <Image alt="from Collaborate.png" src="https://support.appsflyer.com/hc/article_attachments/32328511584529" width="37.55%" />
2. 转到 **合作** 选项卡> **+ 新的合作**.

   <Image alt="在协作选项卡中，单击新建协作arrow.png" src="https://support.appsflyer.com/hc/article_attachments/32348047403665" width="1240px" />

   将显示新的协作屏幕。

   [![全新合作 - 空state.png](https://files.readme.io/8f209f87aaf32315fed0fae46bd55e7bb101084ae6983b08e1566c64a89f0a8e-32192739280273.png)](https://files.readme.io/8f209f87aaf32315fed0fae46bd55e7bb101084ae6983b08e1566c64a89f0a8e-32192739280273.png)

</Accordion>

<div id="step-2-set-collaboration-details" />

<Accordion title="第2步：设置协作细节">

**要设置协作详细信息：**

1. 点击 **设置** （在 **设置协作详细信息**).

   <Image alt="设置.png" src="https://files.readme.io/e47781f360714e539ed54c6a8bfaa32b282f4609dc2c91d77021034f46dfb23a-32348709077393.png" width="951px" />
2. 输入协作名称。这也是您的协作者将看到的初始名称（您以后可以随时更改它）。然后，单击 **救**.

设置协作细节

</Accordion>

<div id="step-3-add-a-collaborator-optional" />

<Accordion title="第3步：添加协作者（可选）">

协作者是您邀请参与合作的品牌合作伙伴。协作者接受邀请后，他们将能够查看和使用与协作关联的源，如数据权限策略中所指定。**此步骤是可选的，可以随时完成** （在创建协作期间或之后）。

添加协作方

1. 点击 **加** （在 **添加协作者**).   

   <Image alt="添加协作者 点击Add.png" src="https://files.readme.io/958f88782e8cd36bbfa1962b51de72824200952be183a968d311fa6ef164553e-34014450760465.png" width="2088px" />
2. 输入协作者的电子邮件。

   <Image alt="add a collaborator.png" src="https://support.appsflyer.com/hc/article_attachments/32324746219537" width="83.55%" />
3. 设置您的 **数据权限策略**.<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#共享权限">详情请见此处说明。</Anchor>  
   该策略将适用于与协作关联的所有源，除非根据单个源进行修改。权限包括：
   * **对协作者可见** - 允许协作者查看您与协作关联的源。禁用后，您的源将仅对您可见。
   * **查询数据** - 允许协作者查询数据并创建聚合报告。
   * **建立受众群体** - 允许协作者在构建其 <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-add-connections">观众</Anchor>.您可以指定是可以使用所有关联数据还是只能使用相交数据（相交数据是指双方的共同用户。
   * **合作伙伴联系** - 允许协作者将受众发送到 <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-add-connections">合作伙伴目的地</Anchor>.
   * **文件导出** - 允许协作者将受众文件导出到他们的云存储桶。

     <Image alt="数据permissions.png" src="https://support.appsflyer.com/hc/article_attachments/34012032112913" width="93.74%" />

     设置权限后，单击 **救**.
4. 点击 **救** 再。创建协作后，协作者将在其收件箱中收到协作邀请。当他们通过电子邮件登录 AppsFlyer 时，他们将能够开始与您合作。

</Accordion>

<div id="step-4-associate-sources-optional" />

<Accordion title="第4步：关联源（可选）">

关联来源意味着共享您的数据（包括 <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources">来源</Anchor>和/或 <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-customized-data-views">数据视图</Anchor>）在合作中。这将使协作者有权查看和使用您在数据权限策略中定义的源，或按每个源定义的自定义权限。**此步骤是可选的，可以随时完成** （在创建协作期间或之后）。

将数据源与协作关联起来。

1. 在 **数据协作平台** > **合作** 选项卡>单击相关协作以访问它。
2. 点击 **副** 下 **关联来源**.  

   <Image alt="关联来源 单击associate.png" src="https://files.readme.io/ed192e758d04c3f48dd70877f90c39428f72460247d4a5940c1217393ae5f686-34014749769617.png" width="2080px" />
3. 选择要关联的源（或 <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources">创建新源</Anchor>).  

   关联数据源  
   然后点击 **救**.
4. **可选：** 按源设置自定义数据权限。

   您可以对源设置自定义权限（这与常规数据权限策略不同）。**要按来源设置自定义数据权限，请执行以下作：**

   点击 **编辑权限** 在源旁边。  

   <Image alt="edit permissions.png" src="https://support.appsflyer.com/hc/article_attachments/33579354753425" width="81.53%" />

   根据您的偏好设置权限（<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#grant-permissions-for-your-source">了解权限</Anchor>），然后单击 **救**.  

   <Image alt="权限source1.png" src="https://files.readme.io/e4b025bf9cd944024e578ac4bcfd60c46d847b3e403b1da737e3451eb708e5a9-34019077412369.png" width="90.08%" />

   **注意：** 您还可以通过转到 **关联来源**，然后点击源>右侧的作（3点）菜单 **编辑权限**.

   4. 点击 **创建协作**.

</Accordion>

就是这样！您的协作已准备就绪。现在是时候让您和您的合作者 <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-build-and-activate-audiences">创建受众</Anchor> 并开展活动。之后 <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-collaboration-measurement-overview">设置测量</Anchor> 并分析结果以获得见解。

<div id="manage-collaborations" />

## 管理协作

本节介绍如何管理现有协作。

<div id="general-actions" />

<Accordion title="关联或管理源">

**要管理关联的源，请执行以下作：**

1. 在数据协作平台（数据洁净室）中，转到 **合作** 选项卡>特定协作。   

   <Image alt="从合作到特定collaboration.png" src="https://support.appsflyer.com/hc/article_attachments/34019991093649" width="82.25%" />
2. 在协作仪表板中，单击 **相关来源** 部分或右上角的作菜单> **相关来源**.  

   <Image alt="actions menu open.png" src="https://files.readme.io/6f77b81a05cdb6ac3f3084d0521ba084b8dae57f9ae7b8cdc823ef1cfa138636-34019992385553.png" width="1377px" />


<div id="associate-new-sources" />

#### 关联新来源

**要关联新源，请执行以下作：** 点击 **+ 关联来源** > 从下拉菜单中选择来源>单击 **救**.  

<Image alt="将源关联到现有collaboration.png" src="https://files.readme.io/4ecd2b8d33195d79c93848b8b1385f504b2c8ee78f509b99d7e4f3b1910bf81e-34127880603921.png" width="574px" />

<div id="manage-sources" />

#### 管理数据源

**要管理已与协作关联的源，请执行以下作：** 单击源旁边的作菜单以：

* **转到源代码** - 这将显示所有源详细信息。
* **编辑权限** - 自定义该特定源的权限（默认情况下，所有源共享主源的权限 **数据权限策略** 你定义了）。<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#共享权限">详情请见此处说明。</Anchor>
* **从协作中删除** - 这会从您的协作中删除源（源仍将出现在您的平台中 **来源**).  
  **注意：** 从协作中删除源意味着协作者将无法再查看或使用关联的源 <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-customized-data-views">数据视图</Anchor>和关联的受众。该源代码仍将在平台的“源”下可用。

</Accordion>

<div id="edit-or-suspend-a-collaboration" />

<Accordion title="编辑或暂停协作">

**要编辑、重命名或暂停协作：**

1. 在数据协作平台（数据洁净室）中，转到 **合作** 选项卡>特定协作。  

   <Image alt="从合作到特定collaboration.png" src="https://support.appsflyer.com/hc/article_attachments/34019991093649" width="82.25%" />
2. 在协作仪表板中，单击右上角的作（3 个点）菜单，然后选择特定作。   

   <Image alt="actions menu open.png" src="https://files.readme.io/6f77b81a05cdb6ac3f3084d0521ba084b8dae57f9ae7b8cdc823ef1cfa138636-34019992385553.png" width="1377px" />

<div id="notes-on-suspended-collaborations" />

> 📘 **暂停合作的注意事项**
>
> * 只有协作所有者/创建者才能暂停协作。
> * 暂停协作会暂停协作者查看数据并对其执行任何作的访问权限。 从协作和动态查询创建的受众将变得不可用。
> * 暂停协作后，您可以通过单击 **重新激活协作** 来自同一菜单。

</Accordion>

<div id="invite-team-members" />

<Accordion title="邀请团队成员">

您可以邀请团队的所有或部分成员加入协作。受邀后，他们将能够在协作中查看源并执行作。

**要邀请团队成员：**

1. 在数据协作平台（数据洁净室）中，转到 **合作** 选项卡>特定协作。  

   <Image alt="从合作到特定collaboration.png" src="https://support.appsflyer.com/hc/article_attachments/34019991093649" width="574px" />
2. 点击 **管理访问权限** （在右上角）。   

   <Image alt="管理access.png" src="https://files.readme.io/e9cfaf5da2b147f68255d6d442078a3770db4c9873109d1188b9a2b5c0f4e65f-36132545995281.png" width="475px" />
3. **要允许公司中的任何人（具有 DCP 权限）访问协作，请执行以下作：**   

   将 **一般访问** settings 设置为 **“贵公司”的任何人**  

   <Image alt="协作是草稿 - 管理访问下拉列表 w arrow.png" src="https://files.readme.io/6358d272f675d9f6f7ad4b07637db7361d772d34738bbd54488212c9870598b4-36132546008209.png" width="623px" />

   **要邀请特定用户：**   

   将 **一般访问** settings 设置为 **仅限受邀者**.  
   在搜索栏中输入姓名或电子邮件以搜索用户，然后单击 **邀请用户**  

   **<Image alt="搜索用户 w arrow.png" src="https://files.readme.io/c32fc8962fbdda7c70dc218147c8f9bbc25e806e72bb00c18c7b50fbc3b373cb-36132546008721.png" width="622px" />**  

   受邀用户将收到一封电子邮件，通知他们收到邀请。他们将能够查看关联的源并在协作中执行作。

</Accordion>

<div data-zendesk-anchors="about-collaborations=%E5%85%B3%E4%BA%8E%E5%90%88%E4%BD%9C h_01JJPMS2D6P3Q9H22FCJ73K0XC=%E5%85%B3%E4%BA%8E%E5%90%88%E4%BD%9C create-a-collaboration=%E5%88%9B%E5%BB%BA%E5%8D%8F%E4%BD%9C h_01JJPN6P4A6XHE3NN7A2V9GDSY=%E5%88%9B%E5%BB%BA%E5%8D%8F%E4%BD%9C h_01JJS67943FHXD9SDRAKE69DZ1=step-1-access-collaborations h_01JJS679434FJNTWD25J3R8MJW=step-2-set-collaboration-details h_01JJS67943DM2X478959482YB7=step-3-add-a-collaborator-optional h_01JJS67943NKA5051CF8CNW05V=step-4-associate-sources-optional additional-information=%E7%AE%A1%E7%90%86%E5%8D%8F%E4%BD%9C h_01JG9CWR6DNKA1N67WR61PR05W=%E7%AE%A1%E7%90%86%E5%8D%8F%E4%BD%9C 01JH5HBXYYT56AP6QJXNSBMT4G=general-actions associate-new-sources=%E5%85%B3%E8%81%94%E6%96%B0%E6%9D%A5%E6%BA%90 h_01JJPMS2D7FTXTKG1E50RCWTX5=%E5%85%B3%E8%81%94%E6%96%B0%E6%9D%A5%E6%BA%90 h_01JWX0XGH0X5AKQ0WE0DP7SMJT=%E5%85%B3%E8%81%94%E6%96%B0%E6%9D%A5%E6%BA%90 manage-sources=%E7%AE%A1%E7%90%86%E6%95%B0%E6%8D%AE%E6%BA%90 h_01JWX0Z31E4SGZKF3VNBVME3X6=%E7%AE%A1%E7%90%86%E6%95%B0%E6%8D%AE%E6%BA%90 h_01JWX0FYB6PSV600DJSGVMBYHR=edit-or-suspend-a-collaboration h_01JK30ZKC1T298TNVXK9SP17EE=%E6%9A%82%E5%81%9C%E5%90%88%E4%BD%9C%E7%9A%84%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 h_01JWX0FYB68MRHEPY8SNDNC481=invite-team-members" />
