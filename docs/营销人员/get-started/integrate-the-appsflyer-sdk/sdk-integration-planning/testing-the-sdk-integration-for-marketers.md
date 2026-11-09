---
title: SDK对接测试（市场人员专用）
metadata:
  keywords:
    - Testing
    - SDK
    - Advertisers
    - Debug
    - Debugging
    - redirects test
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-11-12T14:15:08Z'
  edited_at: '2026-10-14T10:08:13Z'
  id: 360001559405
  locale: zh-cn
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/zh-cn/articles/360001559405
---
> **概要：** 本文重点讲解了如何测试安卓或iOS端与AppsFlyer的SDK对接。

<div id="overview" />

## 速览

SDK对接完毕后，建议您测试该SDK是否能正常向AppsFlyer服务器发送数据。市场人员可选择以下任一方式进行测试：

* 在**SDK对接测试**页面中完成测试。使用这种方法时，您可以：
  * <Image alt="" src="https://files.readme.io/16b90e430d7beea0eaa1530130d094d590c0a202f6c6ad298a88aac9508fee7a-31828933593745.png" width="30px" />[实时查看](#view-live-events)测试应用中发生的事件。
  * [测试非自然激活](#test-nonorganic-installs)
  * [测试深度链接（再营销）](#test-deep-links-retargeting)
* [使用归因链接测试。](#通过归因链接进行测试)

开发人员可在其开发环境中进行对接测试。详情请见<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integration-testing">Dev Hub中的的对接测试说明</Anchor>。

CTV应用也可以进行SDK对接测试。详情请见[CTV测试说明](#测试ctv)。

<div id="note" />

<div id="testing-using-the-sdk-integration-tests-page" />

## 使用SDK对接测试页面进行测试

请使用**SDK对接测试**页面查看实时事件数据，包括激活、广告收入和应用内事件，了解这些事件在应用中的实际触发情况。您也可以测试非自然激活、应用内事件及深度链接（再营销），找出对接中存在的问题。我们对该页面进行了更新，以实时事件查看器取代了先前的应用内事件测试工具。

**仅适用于iOS**SDK对接测试页面仅适用于启用了ATT弹窗的iOS应用。如需测试无ATT弹窗的应用，请参考[此文档](https://dev.appsflyer.com/hc/docs/testing-ios#apps-that-dont-implement-att)中的具体流程。

<div id="prepare-a-test-device" />

### **准备测试设备**

1. 准备一部未安装相关应用的设备（安卓或iOS）。如果您要使用的设备上已经安装了相关应用，请先将其卸载。
2. <Anchor target="_blank" href="/marketers/zh/docs/registering-test-devices">将该设备注册为测试机。</Anchor>

<div id="perform-the-integration-tests" />

<div id="note-1" />

### 进行对接测试

**SDK对接测试**页面提供以下三种测试：

<div id="view-live-events" />

<Accordion title="查看实时事件">

实时事件查看器（Live Event Viewer）是一种测试工具，可显示从SDK发送到AppsFlyer的实时数据，包括激活以及应用内事件。查看器中抓取到的每个事件都带有事件日志和详情。

**请按以下方式在实时事件查看器中查看事件：**

1. 从AppsFlyer后台的侧边栏中选择**配置** > **SDK对接测试**。

   <Image align="center" alt="" src="https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png" />
2. 点击**实时事件**。

   <Image align="center" alt="" src="https://files.readme.io/6ec1edba14e51bb27babf80d2d6f4873dbaa5113752217b4fb13399f7a1c61f1-31828925849489.png" />
3. 在**应用**列表中，选择您需要测试的应用。
4. 在**测试设备**列表中，选择同于测试相关应用的设备。若尚无测试设备，请点击**添加测试设备**链接，添加测试设备。
5. 点击**继续**，开始记录您的应用事件。
6. 打开应用并完成相关操作，生成应用打开事件（session）以及后续的应用内事件。

   <Image align="center" alt="" src="https://files.readme.io/72b8822197dc626c1b28a9f8d43bb3c1a91f99e600ae0d8d1f74829bc62dcce6-31828933607313.png" />
7. 点击所需事件，在右侧面板中查看该事件的详细信息。
8. 如需停止记录事件，则点击**停止**。如需继续记录事件，再次点击**开始**。

</Accordion>

<div id="test-nonorganic-installs" />

<Accordion title="测试非自然激活">

**测试非自然激活的方式如下：**

1. 从AppsFlyer后台的侧边栏中选择**配置** > **SDK对接测试**。

   <Image align="center" alt="" src="https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png" />
2. 点击**非自然激活**测试。

   <Image align="center" alt="" src="https://files.readme.io/34440ab6d328e2d519f759f3c2a1b17dbcbee55af32b47bdbd52bb9f537c6735-31828933612177.png" />
3. 在**应用**列表中，选择您需要测试的应用。
4. 在**测试设备**列表中，选择同于测试相关应用的设备。若尚无测试设备，请点击**添加测试设备**链接，添加测试设备。
5. 如果您的测试设备上已安装要测试的应用，请先将其删除。
6. 勾选**已从测试设备中移除该应用**的复选框。
7. 点击**继续**，然后按照向导工具的提示，完成各个步骤的操作。

**如果该应用未记录到非自然激活，可能是由以下原因造成的：**

* IDFA可用，但未在<Anchor target="_blank" href="/marketers/zh/docs/registering-test-devices#为ios测试设备加白">“测试设备”页用该ID注册</Anchor>测试机。
* 除了测试应用外，测试机上可能还安装了同一厂商的其他应用，但没有<Anchor target="_blank" href="/marketers/zh/docs/registering-test-devices#为ios测试设备加白">在“测试设备“页用IDFV注册</Anchor>该测试机。
* 记录到一次自然激活。
* 测试时下载的应用版本中未接入SDK。

如果对接本身有问题，请联系您的开发人员。

</Accordion>

<div id="test-deep-links-retargeting" />

<Accordion title="测试深度链接（再营销）">

**前期准备：**

* 打开测试应用，至少重复3次。
* 您必须先为相关应用配置OneLink才能测试深度链接（再营销），详情请见<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template">OneLink配置指南</Anchor>。
* 请确认<Anchor target="_blank" href="/marketers/zh/docs/app-settings#reengagement-attribution">再营销</Anchor>开关已打开。

**深度链接的测试方式如下：**

1. 从AppsFlyer后台的侧边栏中选择**配置** > **SDK对接测试**。

   [<Image align="center" alt="Keyboard Maestro Engine 2024-10-06 10.00.47.png" src="https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png" width="2895px" />](https://support.appsflyer.com/hc/article_attachments/36361369975185)
2. 点击**再营销**。

   <Image align="center" alt="" src="https://files.readme.io/7c5eb6870e8d4c25a817f6c2895163b699e0a4972a6cc675b94396c386288d72-31828925858961.png" />
3. 在**应用**列表中，选择您需要测试的应用。
4. 在**测试设备**列表中，选择同于测试相关应用的设备。若尚无测试设备，请点击**添加测试设备**链接，添加测试设备。
5. 点击**继续**，然后按照向导工具的提示，完成各个步骤的操作。

</Accordion>

<div id="note-3" />

<div id="note-2" />

<div id="testing-using-attribution-links" />

## 通过归因链接进行测试

以下章节说明了如何通过归因链接来测试激活。即使您的应用还处于待批（pending）状态（即还未在Google Play Store或Apple App Store正式上架），仍可以完成这些测试。

<div id="test-install-attribution" />

<Accordion title="测试激活归因">

测试激活是为了确认AppsFlyer的SDK能将激活正确归因到各种对应的渠道。

**请按以下步骤测试激活归因：**

1. 复制下图所示链接（分安卓和iOS），然后根据实际情况更改以下参数：

   1. **app\_id**值：输入您的应用在AppsFlyer后台的应用ID。
   2. **pid**参数：输入具体媒体渠道的名称，新增激活会被归因到这个渠道。
   3. **c**参数：输入广告系列的名称。
   4. 如果您测试的应用在第三方安卓应用商店上架，请在归因链接中添加<Anchor target="_blank" href="/marketers/zh/docs/set-up-multi-store-android-attribution#single-dashboard-attribution-links">af\_r</Anchor>参数。
   5. 将GAID、IDFA或IDFV改为具体的设备ID。

   <Tabs>
   <Tab title="Android">

   ```http
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&advertising_id=<GAID>
   ```

   </Tab>

   <Tab title="iOS">

   IDFA

   ```http
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&idfa=<IDFA>
   ```

   IDFV

   ```http
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&idfv=<IDFV>
   ```

   </Tab>
   </Tabs>

   以下是带有具体值的归因链接示例：

   <Tabs>
   <Tab title="Android">

   ```

   ```

   ```http
   https://app.appsflyer.com/com.my.app?pid=Test&c=Test&advertising_id=12345f9*-eba*-421*-876*-7654ac67876*
   ```

   </Tab>

   <Tab title="iOS">

   ```

   ```

   ```http
   https://app.appsflyer.com/id123456789?pid=Test&c=Test&idfa=1A2B****-9128-4***-123*-04E***654321
   ```

   </Tab>
   </Tabs>

   > 📘 **注意**
   >
   > 如果您不使用<Anchor target="_blank" href="/marketers/zh/docs/registering-test-devices">加白的测试设备</Anchor>对某款iOS应用进行测试，您在测试过程中完成的点击可能会被Protect360标记为假量。
   >
   > 为了防止这些点击被识别为假量，请在您的链接中添加以下参数：`pid=ios_testing`。

2. 复制更改后的链接，将其发送到测试机，然后在测试机上点击该链接。

   > 📘 **注意**
   >
   > 在iOS系统中，需要使用iMessage或邮件将链接发送到测试机。请勿将链接复制粘贴到iOS记事本中再点击链接，否则会导致链接断裂。

3. 此时可完成以下任一操作：

   * 如果应用已上架，则直接下载激活。
   * 如果您的应用还处于待批（pending）状态，界面会显示以下消息：*The app you are looking for is not available in the market yet.*（您要查找的应用还未上架）。这是正常现象。由于该应用还未上线，因此归因链接不会将您引导到任何应用商店，但仍可以进行归因。此时请按以下方式激活该应用：
     * **安卓应用：** 使用APK文件（开发人员可以使用Android Studio）安装应用
     * **iOS应用：** 从TestFlight下载（开发人员可从Xcode下载）

   您会看到在名为**Test**的渠道下，用于测试的广告系列获得了一个新增激活的归因。面板显示新增激活最多需要30分钟，请耐心等待。

   <Image align="center" alt="Test_Install_Attribution_Link" src="https://files.readme.io/1771da27f7b8c5334d68c3d7c8361e91e0e35a3a08abf60e3d711f83de9ad22d-31828925861265.png" />

<div id="tip" />

> 👍 **提示**
>
> 您还可以使用以下方法来验证测试结果：
>
> * 如果您有原始数据报告的权限，可下载<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">激活原始数据报告</Anchor>，下载过程可能需要数分钟。**报告下载方式如下：**
>   1. 在AppsFlyer后台左侧的菜单栏中选择**导出** > **原始数据导出**。
>   2. 点击<strong>用户获取（非自然）</strong>列表中的**激活**，然后下载报告。
> * 如果您有调试日志的权限，可使用<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/gcd-get-data">获取转化数据API</Anchor>来拉取某个具体激活的归因结果。

</Accordion>

<div id="test-inapp-events-attribution" />

<Accordion title="测试应用内事件归因">

测试应用内事件可验证事件对应的收入能正常显示到面板，且事件能归因到正确的渠道。

**请按以下步骤测试应用内事件的归因：**

1. 打开应用，然后完成数个应用内事件。
2. 打开该应用的活动面板，确认相关事件是否已成功上报。  
   正常情况下可看到事件及其关联的收入（若有）和渠道。事件显示到面板可能需要60-70分钟的时间，请耐心等待。

**小贴士：** 建议您下载<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">应用内事件原始数据报告</Anchor>，验证事件是否得到正确归因。下载过程可能需要数分钟。

**报告下载方式如下：**

1. 从AppsFlyer后台的侧边栏中选择**报告**>**原始数据导出**。
2. 在**原始数据报告**部分下载应用内事件原始数据报告。

</Accordion>

<div id="test-onelink" />

<Accordion title="测试OneLink">

您可以利用OneLink让您的安卓和iOS应用使用同一条归因链接。OneLink能识别用户的设备, 并让用户跳转到与其设备操作系统对应的应用商店。

此外, OneLink还支持深度链接功能。您可以通过深度链接让用户直接进入应用内的具体页面，同时为其提供定制化的内容。

详情请见<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">OneLink链接测试指南</Anchor>。

</Accordion>

<div id="note-4" />

<div id="testing-retargeting-using-attribution-links" />

## 通过归因链接测试再营销

以下章节说明了再营销归因的测试流程。

<div id="about-retargeting-tests" />

<Accordion title="再营销归因测试简介">

当用户与再营销广告交互，并点击其归因链接时，就会触发再营销归因，进而形成一个再归因或再互动事件。详情请见<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide">再营销归因指南</Anchor>。

再营销测试包括以下两种：

* [**测试再归因：**](/docs/testing-the-sdk-integration-for-marketers#test-reattribution)卸载应用后重新下载并激活该应用，然后检查面板是否记录到一次激活。
* [**测试再互动：**](/docs/testing-the-sdk-integration-for-marketers#test-reengagement)点击再营销归因链接或深度链接，然后检查面板是否将再互动归因到正确的渠道。

</Accordion>

<div id="prerequisites-to-run-retargeting-tests" />

<Accordion title="进行再营销测试前的准备工作">

在进行再营销测试前，请确保您已完成以下设置：

* 确保您已对测试应用开启了再营销功能。
* 创建该应用的专用链接或获取一条OneLink自定义链接，链接中必须包含再营销参数。

**请按以下步骤进行再营销测试：**

1. 在应用配置页打开再营销开关。

   点击应用面板中的**应用配置**，然后打开**启用再营销归因**的开关。

   <Image align="center" alt="Set_Reattribution_window" src="https://files.readme.io/1fe0c8c4add90c75237b0c5c97b6ff26d8f08ff95bd952912ef746fdec2e9f3d-31828933628561.png" />
2. 此时可完成以下任一操作：
   * 创建一条专用于测试应用的归因链接。确保该链接中包含再营销参数`is_retargeting=true`以及设备ID（advertising ID）。如需查看GAID、IDFA或IDFV，请按照<Anchor target="_blank" href="/marketers/zh/docs/registering-test-devices">测试设备加白</Anchor>说明完成操作。   
     以下示例中的归因链接带有安卓专用的设备ID（GAID）参数。如需了解其他的设备ID参数（如IDFA或IDFV），请参考<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#ios专用参数">归因链接的结构及参数</Anchor>。

     ```

     ```

     ```http
     https://app.appsflyer.com/<app_id>?pid=Test&c=Test&is_retargeting=true&advertising_id=<GAID>
     ```
   * 从<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#创建onelink链接">OneLink模板</Anchor>中获取<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#创建onelink模板">自定义链接的长链</Anchor>。请确保<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">再营销广告</Anchor>已激活。下图为自定义长链示例：![Testing_LongLink_en-us.png](https://files.readme.io/19c706b0cc11b83a5cb08d51b3418654c6fa1e597ee7ff9e631db21c33c00b82-31828933632401.png)

完成上述操作后，您就可以进行再归因和再互动测试了。

</Accordion>

<div id="test-reattribution" />

<Accordion title="测试再归因">

**前期准备：**

* 请根据[相关说明](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests)设置再营销测试。
* 请确保您的测试机**未经**注册。

**请按以下步骤测试再归因。**

1. 从设备上卸载应用。如果您刚刚激活该应用，请等待数分钟再进行卸载。
2. 复制您先前创建的[归因链接](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests)，可以是该应用专用的归因链接，也可以是OneLink模板中的自定义长链。将其发送到测试机，然后点击该链接。

   > 📘 **注意**
   >
   > 在iOS系统中，需要使用iMessage或邮件将链接发送到测试机。请勿将链接复制粘贴到iOS记事本中再点击链接，否则会导致链接断裂。

3. 此时可完成以下任一操作：
   * 如果应用已上架，则直接下载激活。
   * 如果应用仍处于待批（pending）状态，请按以下步骤激活应用：
     * **安卓应用**：从Android Studio下载应用或下载APK文件，然后激活。
     * **iOS应用：** 从TestFlight下载应用并激活。
4. 打开该应用的面板，然后在**视图类型**中选择**再营销**。
5. 在**归因触点类型**中选择**再归因**。

   您会看到该次激活被归因到了测试渠道和广告系列。再营销激活显示到面板上最多需要30分钟的时间，请耐心等待。

   <Image align="center" alt="Testing_SDK_Reattribution" src="https://files.readme.io/c5c59709b199262cbefd5cd70ee9fe0db2c788612a8ae6b598c7b2188b696345-small-31828925870609.png" />

<div id="tip-1" />

> 👍 **提示**
>
> 您还可以使用以下方法来验证测试结果：
>
> * 如果您有原始数据报告的权限，可下载<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">转化原始数据报告</Anchor>。下载过程可能需要数分钟。**报告下载方式如下：**
>   1. 在AppsFlyer后台左侧的菜单栏中选择**导出** > **原始数据导出**。
>   2. 点击**再营销**列表中的**转化（再互动与再归因）**，然后下载报告。
> * 如果您有调试日志的权限，可使用<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_app-id-2">SDK对接测试API</Anchor>来拉取某个具体激活的归因结果。

</Accordion>

<div id="test-reengagement" />

<Accordion title="测试再互动">

**前期准备：**

* 请根据[相关说明](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests)设置再营销测试。
* 为便于测试，请将转化之间的最短时间间隔设置为**无**。这样，面板就能记录到测试期间所有的再互动并对其归因。![Testing_Reattribution_window](https://files.readme.io/ec8c7c923093dbed0e99aa5ef57d0239217ead5a9db41f42fe4af8a70eb04551-4406211661841.png)
* 确保您的测试机上已经安装了该应用，且已多次打开。如果您刚刚激活该应用，请等待数分钟再进行卸载。

**请按以下步骤测试再互动（直接深度链接）：**

请确保您的应用已经配置了<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">深度链接</Anchor>，然后按照<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">相关流程</Anchor>进行测试。

**请按以下步骤测试再互动（间接深度链接）：**

1. 复制您先前创建的[归因链接](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests)，可以是该应用专属的归因链接，也可以是OneLink模板中的自定义长链。
2. 将链接发送至测试机，然后在测试机上点击该链接。
3. 请按以下任一方式打开该应用：

   * 在应用商店中点击**打开**。
   * 从设备端打开应用。

   面板会显示新增一次再互动，且该次再互动被归因到相应的渠道和广告系列。面板显示再互动最多需要30分钟时间，请耐心等待。

   <Image align="center" alt="Testing_SDK_Re-engagement" src="https://files.readme.io/5b64b671c8071f871d9835e8df4d89c18d06c85fe996f7227b6ddf429552fccd-small-31828933643153.png" />

**小贴士：** 您可以下载转化原始数据报告，检查该次再互动是否被归因到正确的渠道。下载过程可能需要数分钟。

**报告下载方式如下：**

1. 在AppsFlyer后台左侧的菜单栏中选择**导出** > **原始数据导出**。
2. 在**再营销**部分下载<strong>转化（再互动及再归因）</strong>报告。

</Accordion>

<div id="testing-organic-installs" />

## 测试自然激活

建议您先测试自然激活。

**请按以下步骤测试自然激活：**

1. 在<Anchor target="_blank" href="/marketers/zh/docs/registering-test-devices">已加白的测试机</Anchor>上激活应用。
2. 打开该应用。

该应用的面板上会显示一个新增自然激活。自然激活的数据更新最多会有30分钟的延时，请耐心等待。

<Image align="center" alt="" src="https://files.readme.io/49c242957324516ba93d6c5ebfa338ec19b05820bcf619d8c39d6f7e4ada9bae-31828925882001.png" />

<div id="traits-and-limitations" />

<div id="note-5" />

<div id="testing-ctv" />

## 测试CTV

特殊测试场景包括以下几种：

* **Android TV：** AppsFlyer的SDK适用于搭载安卓系统的智能电视。市场人员或任何团队成员都可按下文流程测试这类电视应用。
* **Apple TV（tvOS）：** AppsFlyer的SDK适用于Apple TV（tvOS）。市场人员或任何团队成员都可按下文流程测试这类电视应用。
* **未上架的tvOS应用：** 需要市场人员和开发人员合作完成测试（详情请见<Anchor target="_blank" href="/marketers/zh/docs/testing-tvos-integration-before-publishing">应用上架前的tvOS对接测试指南</Anchor>）。
* **Amazon Fire TV：** 营销人员可以通过AppsFlyer面板中的安卓SDK测试方式来[测试对接](/docs/testing-the-sdk-integration-for-marketers#testing-from-the-dashboard)。详情请见<Anchor target="_blank" href="/marketers/zh/docs/setting-up-amazon-fire-tv-ad-attribution">Amazon Fire TV归因说明</Anchor>。
* **PBA网页事件：** 需要市场人员和开发人员合作完成测试（详情请见<Anchor target="_blank" href="/marketers/zh/docs/test-pba-web-sdk-integration">PBA网页的SDK对接测试指南</Anchor>）。

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/partners/zh/docs/getting-started-onboarding-guide-for-ad-networks">广告平台对接测试</Anchor>

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 01H88X11QS2VYFXJGC95TXC6PN=%E9%80%9F%E8%A7%88 testing-using-the-sdk-integration-tests-page=%E4%BD%BF%E7%94%A8sdk%E5%AF%B9%E6%8E%A5%E6%B5%8B%E8%AF%95%E9%A1%B5%E9%9D%A2%E8%BF%9B%E8%A1%8C%E6%B5%8B%E8%AF%95 h_01HYX9R159XMZKMH1MBMBH9K9J=%E4%BD%BF%E7%94%A8sdk%E5%AF%B9%E6%8E%A5%E6%B5%8B%E8%AF%95%E9%A1%B5%E9%9D%A2%E8%BF%9B%E8%A1%8C%E6%B5%8B%E8%AF%95 prepare-a-test-device=%E5%87%86%E5%A4%87%E6%B5%8B%E8%AF%95%E8%AE%BE%E5%A4%87 h_01J9GTS4S2RXJAMYGG6XJ5HFRZ=%E5%87%86%E5%A4%87%E6%B5%8B%E8%AF%95%E8%AE%BE%E5%A4%87 perform-the-integration-tests=%E8%BF%9B%E8%A1%8C%E5%AF%B9%E6%8E%A5%E6%B5%8B%E8%AF%95 h_01J9GTW7RAGZXE7GK5BWGBA7N5=%E8%BF%9B%E8%A1%8C%E5%AF%B9%E6%8E%A5%E6%B5%8B%E8%AF%95 h_01HYX9R15983XCT54TJ0VDE8DE=view-live-events h_01HYX9R15931HJEA06SY3K47W5=test-nonorganic-installs h_01HYX9R159DDNJW53AWTWT4C2Z=test-deep-links-retargeting testing-using-attribution-links=%E9%80%9A%E8%BF%87%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E8%BF%9B%E8%A1%8C%E6%B5%8B%E8%AF%95 01H88X11QT0WDRW5GZDCR7MZ3D=%E9%80%9A%E8%BF%87%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E8%BF%9B%E8%A1%8C%E6%B5%8B%E8%AF%95 01H88X11QT6YVB3TQ6JEM4G92G=test-install-attribution h_01HMDX7JMR8RMDMGS49K3DVJGG=%E6%B3%A8%E6%84%8F 01H88X11QTG2NZ3VGMQXJR7368=%E6%B3%A8%E6%84%8F-2 01H88X11QT5TY25HRTX4RD06C7=%E6%8F%90%E7%A4%BA 01H88X11QTRBQQ11C8SAK7DCTC=test-inapp-events-attribution 01H88X11QTJE6HNPDHBMKQMDCP=test-onelink testing-retargeting-using-attribution-links=%E9%80%9A%E8%BF%87%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E6%B5%8B%E8%AF%95%E5%86%8D%E8%90%A5%E9%94%80 01H88X11QTQ94BAJGEE1V11F6X=%E9%80%9A%E8%BF%87%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E6%B5%8B%E8%AF%95%E5%86%8D%E8%90%A5%E9%94%80 01H88X11QT4DR3WA6RGB8HDZB3=about-retargeting-tests 01H88X11QTR3AGQHN674ZYEYF7=prerequisites-to-run-retargeting-tests 01H88X11QVFQ6552C272ST108D=test-reattribution 01H88X11QVYBPJPYSPZH2HS308=%E6%B3%A8%E6%84%8F-2 01H88X11QV5YVR7HCFTGD9BEFJ=%E6%8F%90%E7%A4%BA-1 01H88X11QVKAG3JWRQ6KXESTQA=test-reengagement testing-organic-installs=%E6%B5%8B%E8%AF%95%E8%87%AA%E7%84%B6%E6%BF%80%E6%B4%BB h_01HYX9R1594DD9BEZ6PMV9PJM8=%E6%B5%8B%E8%AF%95%E8%87%AA%E7%84%B6%E6%BF%80%E6%B4%BB Testing%20CTV=%E6%B5%8B%E8%AF%95ctv 01H88X11QT72F71N49G65BAEAE=%E6%B5%8B%E8%AF%95ctv h_01H9FHRVKE88CXGH8G7E26ZXT2=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
