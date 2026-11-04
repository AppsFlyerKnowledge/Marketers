---
title: 卸载衡量
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2021-10-14T08:03:47Z'
  edited_at: '2026-10-14T10:14:09Z'
  id: 4408933557137
  locale: zh-cn
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/zh-cn/articles/4408933557137
---
> **概要**：本文主要介绍了应用卸载率的衡量方式以及优质用户来源（媒体渠道、广告系列、广告素材及地理位置）的识别方式。

<div id="overview" />

## 速览

要洞察应用用户的价值，就必须同时分析应用的激活率和卸载率。您可以通过卸载指标衡量应用的使用情况，并了解用户流失的节点和原因。

<div id="note" />

<div id="how-does-it-work" />

### 原理

1. AppsFlyer每天向Firebase Cloud Messaging（FCM）和 Apple Push Notification Services（APNS）发送一次API请求。
2. 然后FCM和APNS会发送一条静默推送消息，用于判断用户设备上是否仍装有相关应用。
3. 如果响应消息表示该应用已被卸载（FCM和APNS都适用），或在过去270天那未记录到任何用户行为（仅适用于FCM），AppsFlyer就会记录一次卸载。
4. AppsFlyer将该次卸载归因到最初带来该用户的渠道。

> 📘 **注意事项**
>
> 该指标仅在UA视图中可用。

<div id="how-to-use-uninstall-data" />

## 卸载数据的使用方式

您可以通过卸载衡量获得各种信息，并使用该数据来优化广告投放和用户互动。请参考以下示例，以便理解其使用方式。

<div id="compare-the-quality-of-sources" />

<Accordion title="对比用户来源的质量">

您可以对比各种流量来源（媒体渠道、广告系列、广告素材及地理位置）的用户质量，从而识别出卸载率最低的那个媒体渠道，并将预算转移到该渠道。

<div id="note-1" />

> 📄 **示例**
>
> 假设您负责推广PlayIt Gaming International的游戏应用，并分别在两个媒体渠道（渠道A和渠道B）上投放广告，推广新上线的应用。
>
> 您在AF的面板上看到渠道A激活量更高（10,390），但卸载率也较高（30%）。
>
> 而渠道B虽然只带来了5,949个激活，但其卸载率要比渠道A低很多（12%）。
>
> [![Uninstall rates.png](https://files.readme.io/36fb732bfe3a63729b1aa0913f2fe3f24df6a7c86adde9f5c2b95424d840dec4-33839423253137.png)](https://files.readme.io/36fb732bfe3a63729b1aa0913f2fe3f24df6a7c86adde9f5c2b95424d840dec4-33839423253137.png)
>
> 基于以上信息，您决定在渠道B上投入更多预算，以获取更多深度用户。

</Accordion>

<div id="share-uninstall-data-with-ad-networks-for-optimization" />

<Accordion title="与广告平台共享卸载数据，推动投放优化">

您可以将卸载事件回传到您的投放渠道，以推动拉新投放的优化。只需[将卸载事件af\_uninstall映射到您的合作渠道](/docs/measure-uninstalls#卸载事件映射)，即可发送相关数据。映射完成后，每次AF判定有用户卸载应用时，即会向该渠道发送卸载事件。广告平台可以通过该信息判断哪些用户止步于浅层互动，并将资源集中到深度用户的拉新。

<div id="note-3" />

<div id="note-2" />

> 📄 **示例**
>
> 假设您负责推广PlayIt Gaming International的游戏应用，并通过渠道A宣传新安卓应用的发布。您之前通过渠道A投放的广告带来了1000个新激活的用户，其中有300个用户后来卸载了应用。因此在这次新应用的广告投放中，您希望让渠道A接收相关的卸载数据，以使其对卸载问题做出快速响应。
>
> 渠道A根据前一次投放所产出的洞察信息创建了一个禁投用户名单，将某一类用户排除在这一次的投放范围之外，具体如下：
>
> * 根据历史数据显示价值较低的用户。
> * 经常卸载您应用的用户。
>
> 这样，渠道A就能优化人群定向，避免将您的投放预算浪费在对某些广告免疫的用户身上。

</Accordion>

<div id="exclude-uninstalls-from-retargeting-campaigns" />

<Accordion title="将卸载用户从再营销投放中排除">

在某些情况下，为了遵守GDPR和CCPA等监管规定，您可能需要将已卸载应用的用户排除在再营销投放的范围之外。这时，您就要用到卸载信息，以创建禁投用户名单，并实行隐私保护措施来保护用户的隐私和数据。

排除用户的方法有以下几种：

* <Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview#user-journey-report-availability">原始数据报告</Anchor>：从**卸载**报告中手动提取卸载用户列表，并创建禁投用户名单。
* <Anchor target="_blank" href="/marketers/zh/docs/audiences-guide">AppsFlyer受众共享面板：</Anchor>为人群包设置具体标准（如**未**卸载应用的用户），自动在定向投放中排除不符合标准的用户。

> 📄 **示例**
>
> 假设您负责推广PlayIt Gaming International的游戏应用，在投放一个安卓应用的再营销广告时，您决定使用AppsFlyer的受众共享功能来定义一个再营销人群包，并为该人群包设定了以下标准：
>
> * 未卸载应用的用户。
> * 在最近30天内未打开应用的用户。
>
> 这样，您就能创建一个较为精确的再营销人群包。您在投放再营销广告时，广告平台仅会向这个再营销人群包中的用户展示广告。

</Accordion>

<div id="setting-up-uninstall-measurement" />

## 设置卸载衡量

卸载衡量的设置流程同时涉及营销人员和开发人员，因此两方需合作完成设置。具体的启用方式取决于应用运行的操作系统。

营销人员和开发人员的工作流程如下：

<Tabs>
<Tab title="Android">

| 事项 | 负责人 |
| --- | --- |
| [将Firebase Cloud Messaging（FCM）连接到AppsFlyer](/docs/measure-uninstalls#将firebase-cloud-messaging连接到appsflyer安卓) | 营销人员 |
| [在AppsFlyer后台配置卸载衡量](/docs/measure-uninstalls#在appsflyer后台配置卸载衡量) | 营销人员 |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">与SDK集成</Anchor> | 安卓开发人员 |
| [测试卸载衡量](/docs/measure-uninstalls#卸载衡量测试) | 营销人员 |
| 【可选】在AF后台将[卸载事件映射](/docs/measure-uninstalls#卸载事件映射)到相关渠道 | 营销人员 |

</Tab>

<Tab title="iOS">

| 事项 | 负责人 |
| --- | --- |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement-ios#creating-a-p12-certificate">生成P12证书</Anchor> | iOS开发人员 |
| [在AppsFlyer后台配置卸载衡量](/docs/measure-uninstalls#在appsflyer后台配置卸载衡量) | 营销人员 |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">与SDK集成</Anchor> | iOS开发人员 |
| [测试卸载衡量](/docs/measure-uninstalls#卸载衡量测试) | 营销人员 |
| 【可选】在AF后台将[卸载事件映射](/docs/measure-uninstalls#卸载事件映射)到相关渠道 | 营销人员 |

</Tab>
</Tabs>

<div id="implementation-procedures" />

## 启用流程

如需启用卸载衡量，您的移动端开发人员需要在应用中写入一个推送通知响应机制。具体的启用方式取决于操作系统。

<div id="note-4" />

<div id="connect-firebase-cloud-messaging-to-appsflyer-android" />

### 将Firebase Cloud Messaging连接到AppsFlyer（安卓）

如需启用安卓卸载衡量，您需要在AppsFlyer后台配置卸载衡量，并在您的应用中接入Firebase Cloud Messaging（FCM）。

<div id="http-v1" />

<Accordion title="HTTP V1">

**请按以下步骤配置用于卸载的FCM HTTP V1：**

1. **获取Project ID**（项目ID）：
   1. 进入<Anchor target="_blank" href="https://console.firebase.google.com/">FCM Console</Anchor>（FCM控制台）。
   2. 选择一个项目。
   3. 进入**Project Overview**（项目总览）> **Project settings（项目设置）。**  

      ![UninstallFirebase.png](https://files.readme.io/15e74e10daa2f1f1d872f0c8fea274c9819c52c4655baa903728257dd6337e80-33839423254289.png)
   4. 复制Project ID。您会在后面的步骤中用到这个ID。
2. FCM API的启用方式如下：
   1. 进入**Cloud Messaging**选项卡。
   2. 确保<strong>Firebase Cloud Messaging API（V1）</strong>已设置为**Enabled**（启用）。
3. **将AppsFlyer指定为卸载角色：**
   1. 进入**Service accounts**（服务账号）选项卡。
   2. 点击**Manage service account permissions**（管理服务账号权限）。   
      在Google Cloud Platform中打开新的浏览选项卡。
   3. 在边栏目录中选择**Roles**（角色）。
   4. 点击 **+Create role**（创建角色）。
   5. 请完成以下操作：
      * 标题：输入**AppsFlyer uninstalls**。
      * ID：输入`af_uninstalls`。
      * 角色启用阶段：选择**General availability**（全量启用）。
   6. 单击**Add permissions**，添加权限。
   7. [![](https://files.readme.io/255f5cf42ba1b07cae905ec0acbe6459303c3bd5b03f2d36e1ac3f9606fbb229-33839382512145.png)](https://files.readme.io/255f5cf42ba1b07cae905ec0acbe6459303c3bd5b03f2d36e1ac3f9606fbb229-33839382512145.png)
   8. 点击**Add**（添加），然后再点击**Create**（创建）。
4. **将AppsFlyer指定为FCM卸载角色：**
   1. 在边栏菜单中选择**IAM**。
   2. 打开**PERMISSIONS** -> **VIEW BY PRINCIPALS**选项卡。
   3. 点击**Grant Access**（授予访问权限）。
   4. 进入**Add Principals**->**New principals**，输入**af-uninstalls-tracking@af-uninstalls-tracking.iam.gserviceaccount.com**
   5. 进入**Assign roles**->**Role**，选择您创建的自定义角色**AppsFlyer Uninstalls**。
   6. 点击**Save**（保存）。   
      AppsFlyer服务账户即被指定为AppsFlyer uninstall。

      > 📘 **注意**
      >
      > AppsFlyer仅将静默推送用于卸载情况的衡量和流失用户的识别，不作他用。


</Accordion>

<div id="legacy-http" />

<Accordion title="【已弃用】旧版HTTP">

<div id="important" />

> 🚧 **重要提示！**
>
> Firebase已于2023年6月20日弃用旧版HTTP API，并于2024年6月21日彻底移除该API。如果您还在使用该旧版API，强烈建议您[改用HTTP v1 API](/docs/measure-uninstalls#http-v1)。<Anchor target="_blank" href="https://firebase.google.com/docs/cloud-messaging/http-server-ref">详情请见此处说明。</Anchor>

Android SDK V4.7.0及以上版本支持通过Firebase Messaging进行卸载衡量。

**请按以下步骤获取Firebase服务器密钥：**

1. 创建一个Firebase安卓应用项目，或按以下说明把您的项目从**Google Developer Console**中迁出。详情请见<Anchor target="_blank" href="https://firebase.google.com/docs/cloud-messaging/android/client">Firebase</Anchor>中的相关说明。
2. 打开 Firebase <Anchor target="_blank" href="https://console.firebase.google.com">Console</Anchor>.
3. 在Firebase 控制台页面，导航至项目设置（点击项目总览旁边的设置图标）。  

   ![firebase_cloud_messaging_server_key.png](https://files.readme.io/4e31c02a1bea013c823b0148ba1704d4492f66d04e23f0e13e00a9c0c22d286c-33839382513041.png)
4. 您会在Cloud Messaging选项卡中看到两个Server Key（服务器密钥）。
5. 复制该**服务器密钥**。

</Accordion>

<div id="configure-uninstall-measurement-in-appsflyer" />

<div id="note-5" />

### 在AppsFlyer后台配置卸载衡量

<Tabs>
<Tab title="Android">

**前期准备**：安卓开发人员必须完成<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">对接流程</Anchor>。

**请按以下步骤在AppsFlyer后台配置卸载衡量**：

1. 从AppsFlyer后台的侧边栏中选择**配置** > **应用配置**。
2. 请根据业务需要启用**卸载衡量**。
3. 选择**HTTP V1并输入上一步中取得的项目ID**。

   ![UninstallHTTPV1.png](https://files.readme.io/80d13e47ea7ae1585d2ecc0e2f7210572e47dba936557c8e96314e49b0d738d8-33839423258641.png)
4. 点击**测试连接**。  
   界面显示“Success!”（对接成功）的消息。
5. 点击**保存设置** 。

</Tab>

<Tab title="iOS">

**前期准备**：iOS开发人员必须完成<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">对接流程</Anchor>。

**请按以下步骤在AppsFlyer后台配置卸载衡量：**

1. 从开发侧获取P12文件。
2. 从AppsFlyer后台的侧边栏中选择**配置** > **应用配置**。
3. 向下滚动到卸载板块。
4. 打开**卸载衡量**开关。

   ![Uninstall_iOS_p2.png](https://files.readme.io/3f9de3ebe6099886fa9bc210bd6e491ba91e8ff2c890c980f66c4d48398a597c-33839423260561.png)
5. 点击上传图标，并选择相关的P12文件。
6. 【可选】如果P12证书受密码保护，请输入密码。
7. 点击**验证**，将证书发送到AppsFlyer进行验证。
8. 点击**保存设置**。

</Tab>
</Tabs>

<div id="note-6" />

<div id="testing-uninstall-measurement" />

## 卸载衡量测试

完成了卸载衡量的启用流程后，您可以对相关应用进行激活并卸载，以测试面板是否能正常记录卸载事件。卸载量和卸载率在数据总览面板中查看。

<Tabs>
<Tab title="Android">

符合下列条件的应用都可进行上述测试：

* 在Google Play Store上架
* 待批（尚未在Google Play Store上架）
* 可通过下载链接直接下载
* 在第三方应用商店中上架

测试安卓应用时请注意以下两点：

* 卸载衡量数据<Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#uninstalls">每天</Anchor>处理一次。卸载事件会在发生后的24小时内记录到后台，但如果用户在这24小时内又重新安装该应用，则面板不会记录卸载。
* 在**原始数据报告中**和AppsFlyer面板（汇总效果报告）中，<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">卸载事件的显示最多会有48小时的延迟</Anchor>。

</Tab>

<Tab title="iOS">

在测试iOS应用时请注意以下两点：

* 卸载不会立即出现在AppsFlyer面板中。由于Apple推送服务（Apple Push Notification Service）的限制，卸载显示到面板至少需要9天时间。AppsFlyer更新和汇总卸载指标的频率为每24小时一次。

  <div id="h_01HB8CXQ49QN0PH138V2PD2QXE" />

  > 📄 **示例**
  >
  > * 第1天：用户激活了您的应用
  > * 第4天：用户卸载了您的应用
  > * 第12天：Apple推送服务在卸载发生的8天后上报应用卸载
  > * 第13天：您可以在AppsFlyer面板和原始数据报告中看到卸载数据

* 如果您使用的是测试版应用，请确保在沙盒环境中测试卸载。相关的开发人员指南请见[沙盒环境中的卸载测试流程](https://dev.appsflyer.com/hc/docs/uninstall-measurement-ios#testing-uninstall-measurement)。

</Tab>
</Tabs>

<div id="mapping-the-uninstall-event" />

## 卸载事件映射

![Uninstall_event_postback.png](https://files.readme.io/9c3c7f3fd330720d4f6f41fdf509c5af00d042291c1350ab83a1951464ac8e8f-33839423261713.png)

您需要将<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">af\_uninstall事件</Anchor>映射到渠道，才能与其共享卸载数据。卸载事件不是实时发送的，这与常规应用内事件的回传不同。上报的事件时间是AppsFlyer判定用户已卸载应用的时间，而非实际卸载的时间。

注意事项：

* AppsFlyer发送回传的前提条件是事件发生且被AppsFlyer记录到。
* 如果您没有在数据总览面板或原始数据报告中看到卸载数据，就表示没有卸载数据回传到渠道，即使您已完成**af\_uninstall**事件的映射。

<div id="limitations" />

#### 局限性

* 应用内事件回传报告中不包含卸载事件。
* **af\_uninstall**事件适用于所有渠道。如果您想要将卸载事件映射到某渠道，但该渠道的对接选项卡中没有可用的卸载事件，请联系您的CSM或发送邮件至[hello@appsflyer.com](mailto:hello@appsflyer.com)。

<div id="turning-off-uninstall-measurement" />

## 如何停用卸载衡量

<Tabs>
<Tab title="Android">

如果广告主提供了Firebase/GCM Server Key，则AF会默认启用卸载衡量。广告主可以在面板中停用该功能。

</Tab>

<Tab title="iOS">

如果广告主提供了有效的P12证书，则AF会默认启用卸载衡量。广告主可以在面板中停用该功能。

</Tab>
</Tabs>

**请注意：** 如需上报卸载，请在用户安装应用前就**启用卸载衡量**。只有在**启用卸载衡量**开关打开后发生的激活才能记录到其卸载。

<div id="to-turn-off-uninstall-measurement" />

#### **关闭卸载衡量的方法如下**：

1. 从AppsFlyer后台的侧边栏中选择**配置** > **应用配置**。
2. 下滚到**归因** > **卸载衡量**，关闭**启用卸载衡量**开关。

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| CUID | 卸载回传中不包含CUID。 |

</Accordion>

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 h_01HB8CXQ4824V2WEPYGK8YS4DC=%E9%80%9F%E8%A7%88 how-does-it-work=%E5%8E%9F%E7%90%86 h_01HB8CXQ48JEJECC1HR79DXCRK=%E5%8E%9F%E7%90%86 h_01HK25HB9SYTZY759VRMZMF3YY=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 how-to-use-uninstall-data=%E5%8D%B8%E8%BD%BD%E6%95%B0%E6%8D%AE%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HB8CXQ48E2SRN95MH4E2H7ZH=%E5%8D%B8%E8%BD%BD%E6%95%B0%E6%8D%AE%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HB8CXQ48HX9RH50G45FZMZTK=compare-the-quality-of-sources h_01HB8CXQ48DZYQW7FYBD3XYREM=%E7%A4%BA%E4%BE%8B h_01HB8CXQ488E22GPCEBE69VQ3M=share-uninstall-data-with-ad-networks-for-optimization h_01HB8CXQ48ZE5TTZRPQE5SEKJS=%E7%A4%BA%E4%BE%8B-1 h_01HB8CXQ48JTET73GH0QQBX5HF=exclude-uninstalls-from-retargeting-campaigns h_01HB8CXQ4832ZHRYQECYCQPP66=%E7%A4%BA%E4%BE%8B-2 setting-up-uninstall-measurement=%E8%AE%BE%E7%BD%AE%E5%8D%B8%E8%BD%BD%E8%A1%A1%E9%87%8F h_01HB8CXQ4810HTB45FAS5ZVRHF=%E8%AE%BE%E7%BD%AE%E5%8D%B8%E8%BD%BD%E8%A1%A1%E9%87%8F implementation-procedures=%E5%90%AF%E7%94%A8%E6%B5%81%E7%A8%8B h_01HB8CXQ489HRF72VRZ4G532GX=%E5%90%AF%E7%94%A8%E6%B5%81%E7%A8%8B connect-firebase-cloud-messaging-to-appsflyer-android=%E5%B0%86firebase-cloud-messaging%E8%BF%9E%E6%8E%A5%E5%88%B0appsflyer%E5%AE%89%E5%8D%93 h_01HB8CXQ48ZD5Y0RKTG1W51TKW=%E5%B0%86firebase-cloud-messaging%E8%BF%9E%E6%8E%A5%E5%88%B0appsflyer%E5%AE%89%E5%8D%93 h_01HB8CXQ4865MNVG0VERSNSE3F=http-v1 h_01J14PAAGZ60Y8SHH0PNT8SSXS=%E6%B3%A8%E6%84%8F h_01HB8CXQ48H079WQ6Q6G0XSQC7=legacy-http h_01HB8CXQ48ENMG65YH5ECGST9Z=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA configure-uninstall-measurement-in-appsflyer=%E5%9C%A8appsflyer%E5%90%8E%E5%8F%B0%E9%85%8D%E7%BD%AE%E5%8D%B8%E8%BD%BD%E8%A1%A1%E9%87%8F h_01HB8CXQ48CVA9B8B78W0H357C=%E5%9C%A8appsflyer%E5%90%8E%E5%8F%B0%E9%85%8D%E7%BD%AE%E5%8D%B8%E8%BD%BD%E8%A1%A1%E9%87%8F testing-uninstall-measurement=%E5%8D%B8%E8%BD%BD%E8%A1%A1%E9%87%8F%E6%B5%8B%E8%AF%95 h_01HB8CXQ48SW2TT5Z85XD3XWT6=%E5%8D%B8%E8%BD%BD%E8%A1%A1%E9%87%8F%E6%B5%8B%E8%AF%95 mapping-the-uninstall-event=%E5%8D%B8%E8%BD%BD%E4%BA%8B%E4%BB%B6%E6%98%A0%E5%B0%84 h_01HB8CXQ499ABX9ZGDFB1VAE8W=%E5%8D%B8%E8%BD%BD%E4%BA%8B%E4%BB%B6%E6%98%A0%E5%B0%84 limitations=%E5%B1%80%E9%99%90%E6%80%A7 h_01HB8CXQ49F2ARQTEV8Q032P9V=%E5%B1%80%E9%99%90%E6%80%A7 turning-off-uninstall-measurement=%E5%A6%82%E4%BD%95%E5%81%9C%E7%94%A8%E5%8D%B8%E8%BD%BD%E8%A1%A1%E9%87%8F h_01HB8CXQ49Y5NCG7GK93HXHYMD=%E5%A6%82%E4%BD%95%E5%81%9C%E7%94%A8%E5%8D%B8%E8%BD%BD%E8%A1%A1%E9%87%8F to-turn-off-uninstall-measurement=%E5%85%B3%E9%97%AD%E5%8D%B8%E8%BD%BD%E8%A1%A1%E9%87%8F%E7%9A%84%E6%96%B9%E6%B3%95%E5%A6%82%E4%B8%8B h_01HB8CXQ49WXZS4M6CK5XG1BCX=%E5%85%B3%E9%97%AD%E5%8D%B8%E8%BD%BD%E8%A1%A1%E9%87%8F%E7%9A%84%E6%96%B9%E6%B3%95%E5%A6%82%E4%B8%8B h_01HB8CXQ4916CJ9NDZWGWQHKSA=traits-and-limitations" />
