---
title: 公告：Unity Ads的成本API对接即将更新
metadata:
  keywords:
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - ROI360
  created_at: '2024-06-20T14:43:15Z'
  edited_at: '2026-10-14T10:06:32Z'
  id: 26078530790289
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/26078530790289
---
| **最新动态** | AppsFlyer通过API对接获取Unity的成本数据，该API即将更新。如需继续获取Unity的成本数据，请更新您的对接。 |
| --- | --- |
| **更新日期** | 2023年8月14日 |
| **重要须知** | <ul><li>Unity将推出新的成本API对接。</li><li>旧版成本API对接在2024年10月1日下线前仍可获取成本数据。</li></ul> |
| **待办事项** | 请务必更新您的证书信息，以启用新的Unity成本API对接，确保在2024年10月1日之后仍能正常获取成本信息。<br /><br />必要的证书信息如下：<ul><li>Organization Core ID</li><li>Service Account Secret Key</li><li>Service Account Key ID</li></ul>请按照下文说明在AppsFlyer后台更新您的Unity成本对接。更新流程分为以下两个步骤：<ol><li>[获取新的Unity证书](/docs/bulletin-unity-ads-cost-api-integration-update#get-unity-credentials)。</li><li>[在AppsFlyer后台输入新的证书信息，更新Unity成本API的对接。](/docs/bulletin-unity-ads-cost-api-integration-update#set-up-unity-cost-api-integration-in-appsflyer)</li></ol> |

<div id="unity-cost-api-integration-procedures" />

## Unity成本API对接流程

Unity成本API的对接流程分为以下两个步骤：

1. 获取新的Unity证书。
2. 在AppsFlyer后台输入新的证书信息，更新Unity成本API的对接。

各步骤的详细说明请见下文对应章节。

<div id="get-unity-credentials" />

<Accordion title="获取Unity证书">

配置Unity成本API对接时必须填写的证书如下：

* Organization Core ID
* Service Account Secret Key
* Service Account Key ID

**请注意**：建议创建一个新的Unity服务账号，用于获取secret key和key ID。详细操作请见下文。

**请按以下方式创建一个Unity服务账号，获取Unity成本API对接的必要证书信息**：

1. 登入您的Unity Cloud账号。
2. 从左侧菜单中选择**Grow (Unity Ads User Acquisition)** > **Settings**。  
    <Image align="center" alt="" src="https://files.readme.io/2fcc359913c11a4bcce29e1aaf30cb84161a09e39b14cdcd4ad4f141debd1798-26134832885137.png" />
3. 查找、复制并保存**Organization Core ID**。  
   Organization Core ID示例：5773102414648
4. 选择左侧菜单中的**Grow (Unity Ads User Acquisition)** > **`{}` API Management<strong>，然后点击</strong>Stats API v2.0** 部分中的**Service Account**。  
    <Image align="center" alt="" src="https://files.readme.io/36dd40e68eeeb6562c1e5a19f92873e8eb99b66f80c45db066e0ff54b66d0080-26369979011985.png" />
5. 点击 **+ New**，创建一个新的服务账号。  
    <Image align="center" alt="" src="https://files.readme.io/3a53e932bf8d023e910b66f74ea6f630c8048787885d45ea4206b2f1f3d4f65e-26136910848785.png" />
6. 点击**Keys** 部分中的 **+ Add key**，为该服务账号创建一个密钥。  
    <Image align="center" alt="" src="https://files.readme.io/f528d44a9659372bfeeb8d13538f9caf0a7955f53194194543988af983f9c517-26136957380753.png" />
7. 复制并保存界面中显示的**Key ID**和**Secret key**。**请注意**：这是访问Secret Key的唯一一次机会，因此请务必立即保存该信息！
   * 服务帐号的secret key示例：b0de73b1-b3ad-4175-bf9b-4913a0ff83ec
   * 服务帐号secret key的key ID示例：a0X\_cqHiXH4ABPS1Qr9TCy6EJdvG8ql5  
      <Image align="center" alt="" src="https://files.readme.io/6de3cd868541ab5487370dbefc758a375c3395434e07361f74553a1b9a9c7d57-26136957383697.png" />
8. 进入**Organization roles**部分，点击 **+ Manage organization roles**。  
    <Image align="center" alt="" src="https://files.readme.io/d368d6c611db2a8df76e341c7b6a692128b5ae37f51f6642fa7e60cd00f29689-26136910860689.png" />
9. 在**Edit roles in organization**部分，将**Growth**设置为**Advertise Stats API MMP Viewer**。  
    <Image align="center" alt="" src="https://files.readme.io/f1243cb65978d2f96d148ceb34b528ca005091c38dbed95368923047b3cfbfd1-26136957386513.png" />

</Accordion>

<div id="set-up-unity-cost-api-integration-in-appsflyer" />

<Accordion title="在AppsFlyer后台更新Unity成本API对接">

**请按以下方式更新AppsFlyer中的Unity成本API**:

1. 从AppsFlyer后台的侧边栏中选择**协作** > **活跃对接**，然后选择**Unity**。
2. 点击**管理对接**。
3. 打开相关渠道对接页面中的**成本**选项卡。
4. 打开**获取成本数据**的开关。界面会显示需要完成的渠道绑定操作。
5. 输入您的Unity证书信息。
6. 点击**保存成本**。
7. 点击**测试连接**。  
   * 完成上述操作后，API即处于启用状态。AppsFlyer每天会从Unity收集6次数据，平均每四小时一次。

<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data">如需进一步了解成本对接与渠道绑定，请参考此文档。</Anchor>

</Accordion>

<div data-zendesk-anchors="unity-cost-api-integration-procedures=unity%E6%88%90%E6%9C%ACapi%E5%AF%B9%E6%8E%A5%E6%B5%81%E7%A8%8B h_01J11ZP5XG6VDSQKRWASAYK4QJ=unity%E6%88%90%E6%9C%ACapi%E5%AF%B9%E6%8E%A5%E6%B5%81%E7%A8%8B h_01J14M3C6WNXPJJQHVWVNFB4GS=get-unity-credentials h_01J11ZHPJDZDZ7S24ZQK58B2FN=set-up-unity-cost-api-integration-in-appsflyer" />
