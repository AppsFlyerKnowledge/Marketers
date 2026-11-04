---
title: 带有自定义域名的OneLink品牌链接
metadata:
  keywords:
    - Marketers
    - cname
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-08-26T09:00:09Z'
  edited_at: '2026-10-14T10:09:52Z'
  id: 360002329137
  locale: zh-cn
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/zh-cn/articles/360002329137
---
> **概要：** 使用OneLink链接的广告主可以为链接打上品牌域名，从而优化投放效果并提升品牌曝光。

![Branded_1__3_.jpg](https://files.readme.io/20d0a59aa3e896960c9a0faaacad51a58e314073368452e07a7507e0770ca817-30192959736465.png)

<div id="branded-domains" />

## 品牌域名

* 如上图所示，品牌域名的原理就是使用您的品牌名称和域名为归因链接打上品牌标签。
  * OneLink链接：abcdef.onelink.me
  * 品牌：abcdef.com
  * 子域名：如“app”。
  * 写入品牌域名并使用完整域名，这样归因链接就变成了click.abcdef.com
* 品牌域名的下列优势可以推动投放效果的优化：
  * 提升用户信任度：充分发掘品牌价值，贯彻始终如一的品牌认知，打造无摩擦的用户链路，最终提升转化率。
  * 可以让您在深度链接中使用品牌标签。
  * 简单易用，具有与OneLink相同的功能。
  * 提升品牌知名度： 摈弃泛型链接，用品牌来标记您的广告。
  * 进行邮件营销时无需担心链接与发件人的邮箱不匹配而被标记为垃圾邮件。
  * AppsFlyer付费<Anchor target="_blank" href="/marketers/zh/docs/account-management-plans-payments-and-billing">订阅计划</Anchor>包含品牌域名。

<div id="principles-of-implementation" />

### 部署原理

品牌域名的作用原理是将您在Domain Name System（域名系统，简称DNS）中定义的完整域名关联到某个OneLink子域名（AppsFlyer CNAME）。您需要在DNS中使用标准设置，并在AppsFlyer后台设置一个品牌域名。此外，您还需要对应用作一些微调，使其支持品牌域名。

具体的部署工作需要DNS管理员的协助，DNS管理员通常是您的IT团队成员或DNS托管服务商以及应用开发人员。

一个OneLink子域名可关联多个完整域名。也就是说，同一个OneLink子域名可用于多个品牌。

<div id="setting-up-branded-domains" />

### 品牌域名的设置

下表列出了品牌域名的设置流程。

|  | 负责人员 | 操作 | 说明 |
| --- | --- | --- | --- |
| 1 | DNS管理员协助市场人员完成 | [在AppsFlyer后台设置一条品牌链接](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer) | DNS管理员（通常是您的IT团队成员或DNS托管服务商）需要定义完整域名（即host）并按下文流程中所述的方法设置CNAME记录。 |
| 2 | 开发人员 | [在应用中设置品牌域名](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app) | 对应用代码进行微调。 |
| 3 | 营销人员 | [使用并测试品牌域名](/docs/brand-onelink-with-your-domain#using-and-testing-branded-domains) |  |
| 按需 | 营销人员 | [修改或删除品牌域名](/docs/brand-onelink-with-your-domain#editing-and-deleting-branded-domains) |  |

<div id="procedures" />

### 设置流程

<div id="set-up-a-branded-domain-in-appsflyer" />

<Accordion title="在AppsFlyer后台设置品牌域名的说明文档。">

设置品牌域名的实质就是将您DNS中的完整域名组关联到AppsFlyer中的某个OneLink子域名，如下图所示。

**指向AppsFlyer服务器的品牌域名**

[![](https://files.readme.io/43bcdbe50ec58af434f404f0216f90ad345b7b1e034cb7d7c80e3c3c4307c1d2-30192946333713.png)](https://files.readme.io/43bcdbe50ec58af434f404f0216f90ad345b7b1e034cb7d7c80e3c3c4307c1d2-30192946333713.png)

**前期准备：**

* 确定一个完整域名，如app.abcdef.com，  
  其中abcdef.com代表您的品牌。您也可以根据实际情况自行配置子域名（如上述示例中的app）。
* 让DNS管理员创建该完整域名（即host）。
* 让DNS管理员设置一个CNAME记录，  
  让完整域名（即品牌域名）指向特定的URL（即AppsFlyer服务器）。  
  即如上图中所示，品牌域名指向AppsFlyer服务器。

**将您的完整域名映射到OneLink子域名**：

1. 在 AppsFlyer 中，点击 **“互动”** > **“品牌域名”** 。
2. 点击 **+添加品牌域名**。
3. 在**品牌域名**字段中输入您在DNS中设定的完整域名，比如**click.abcdef.com Note:** 切勿在域名后加句点（.）。
4. 在界面所示的列表中选择相关的OneLink子域名。若界面中未显示列表，  
   则表示您需要创建一个OneLink模板，创建完毕后就会呈现一个  
   默认子域名。
5. 点击**下一步**。
6. 设置一个CNAME记录：
   * 如果您的域名正常映射到AppsFlyer CNAME，  
     界面会显示消息“AppsFlyer CNAME was found”（找到了AppsFlyer CNAME）。
   * 如果未找到CNAME，请复制相关的AppsFlyer CNAME并将其发送给您的DNS管理员，让他们确保您的完整域名映射到这个CNAME。DNS管理员必须将完整域名映射到AppsFlyer CNAME，否则您创建的品牌域名将无法生效。

     <div id="note" />

     > 📘 **注意**
     >
     > CNAME记录的映射必须在7天内完成，从品牌域名创建之日起开始计算，到确认窗口中显示的具体日期为止。  
     > 如果相关的CNAME记录在截止日期前未完成映射，您需要  
     > [刷新7天的映射期限](#刷新cname记录的7天映射期限)。

7. 点击**完成**。完成以上步骤后，您就可以使用您的品牌域名在该OneLink模板下创建新链接。

   <div id="note-1" />

   > 📘 **注意**
   >
   > * 如果您已经基于OneLink模板创建了不含品牌域名的链接，这些链接仍然有效。
   > * 品牌域名从创建到生效最长需要24小时。


<div id="renew-the-7-day-period-for-mapping-the-cname-record" />

#### 刷新CNAME记录的7天映射期限

如果完整域名的CNAME记录未在品牌域名创建后的7天内映射到AppsFlyer，则新建的品牌域名无法生效。

<div id="note-2" />

> 📘 **注意**
>
> 如果您在7天的期限过期后完成了CNAME记录的映射，仍需刷新7天的映射期限，否则新建的品牌域名无法正常生效。

**7天映射期限的刷新方式如下：**

1. 从AppsFlyer后台的左侧的菜单栏中选择**互动** > **品牌域名**。
2. 找到尚未映射到AppsFlyer的品牌域名。您可以通过警示图标（![alert.png](https://files.readme.io/7df53739ca5c629ec0bda789563f59717da9699986222705228f57e0d947c8de-30192946335761.png)）定位到相关域名。
3. 点击刷新图标（<Image alt="refresh.png" src="https://files.readme.io/052b47c423612c1b0549f37ed6394373d37f28331e09f4c709601a7e5473bf2b-30192959741585.png" width="18px" />），刷新7天的映射期限。

<div id="note-3" />

> 📘 **注意**
>
> 如果您决定不刷新7天的映射期限，可以点击删除图标（<Image alt="delete-subdomain.png" src="https://files.readme.io/0029cc63db331d998182d46a63f9da9856de9b2351abd5b2d87fb2b47ae853c2-30192959748241.png" width="16px" />）删除该品牌域名。您只能删除尚未映射到AppsFlyer的品牌域名。

<div id="custom-ssl-certificate-optional" />

#### 自定义 SSL 证书（可选）

AppsFlyer 管理的 SSL 是大多数客户的默认和推荐选项，无需额外操作，因为 AppsFlyer 会自动处理证书颁发和续订。如果您有特定的安全或合规性要求，您可以选择使用您自己的 SSL 证书颁发机构（自定义 SSL 证书）而不是 AppsFlyer 管理的 SSL。如果您选择此选项，您将负责颁发、上传、维护和续订证书。如果证书过期且未及时续期，服务可能会中断。

**要使用自定义 SSL 证书：**

1. [创建品牌域名](/docs/brand-onelink-with-your-domain#品牌域名的设置)。
2. 在 AppsFlyer 中，从 **“互动”** > **“品牌域名”** 中，将鼠标悬停在相关域名上，然后选择“自定义 SSL 证书”图标。   
   <Image alt="SSL证书图标 最新极简.png" src="https://files.readme.io/8b22a41fd755a3f36e8eaf4a869b107661894d81504bbfb44e1fc728b9b06751-45231876708497.png" width="1044px" />
3. 填写证书详情表。   
   <Image alt="填写表格以生成 CSR 文件.png" src="https://files.readme.io/4327a4da0cbcc6243c9bbdbec21fe4f91d7fe701ccbffca99e629a5eadd248e8-45231876709649.png" width="66.18%" />
4. 点击 **“下载 CSR”** 下载您刚刚填写的表格副本。  
   下载CSR文件
5. 请将您刚刚下载的 CSR 文件提供给您选择的 SSL 证书颁发机构。
6. 一旦他们给你新的 SSL 证书，就把它上传回 AppsFlyer。

<Image alt="上传新的 SSL 证书到 AF.png" src="https://files.readme.io/b22525d9f653c3897f39f02a7beded3ad5c42d74a5487458f2ed720a20351e03-45231892701969.png" width="811px" />

<div id="note-4" />

> 📘 **注意**
>
> 请关注SSL证书的有效期限。您需在当前证书到期前完成续期，并将更新后的证书上传至AppsFlyer

</Accordion>

<div id="set-up-branded-domains-in-the-app" />

<Accordion title="在应用中设置品牌域名">

* 请使用以下SDK版本：
  * 安卓：V4.10.1及以上
  * iOS：V4.10.1及以上
  * 如需在用户邀请推荐（邀请好友）场景中使用品牌域名，安卓和iOS都需要使用V5.2.0及以上的SDK

**接入品牌域名SDK时的注意事项**

* 使用品牌域名的深度链接生效时，AppsFlyer SDK无法获取激活和深度链接的转化数据。
* 如需克服这个问题，开发人员可以根据相关应用的操作平台分别使用`setOneLinkCustomDomain`（安卓）和`oneLinkCustomDomains`（iOS）这两个SDK API。
* 该API会查询品牌域名，获取品牌域名所映射的OneLink域名，并将品牌域名填入OneLink。

<Tabs>
<Tab title="Android">

请务必更新manifest的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#adding-app-link-intent-filter-to-main-activity">intent-filter</Anchor>，设置android:host，以确保其中包含您的品牌域名。

请在<Anchor target="_blank" href="https://developer.android.com/reference/android/app/Application">Android global application class</Anchor>中使用该API，并将其设置在SDK初始化之前。

**示例**

```java
public class AFApplication extends Application {

    @Override
    public void onCreate() {
    super.onCreate();

      // Set branded link domain. Don't include https:// as part of the domain. 
      AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com");
      AppsFlyerLib.getInstance().init(AF_DEV_KEY, conversionListener, this);
      AppsFlyerLib.getInstance().start(this, AF_DEV_KEY);

    }
}
```

如果您有多个品牌域名，请将所有的品牌域名都传递到该API，以确保您总是可以获取相关的转化数据，并深度链接到应用中。

**示例**

```java
AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com", 
                                                        "click.greatapp.com", 
                                                        "deals.greatapp.com");
```

</Tab>

<Tab title="iOS">

<Tabs>
<Tab title="Objective C">

请在AppDelegate.m中使用该API，放在didFinishLaunchingWithOptions方法中：

```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    /** APPSFLYER INIT **/
    [AppsFlyerLib shared].appsFlyerDevKey = @"SED_DEV_KEY";
    [AppsFlyerLib shared].appleAppID = @"123456789";
    [AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com"];
    //...
    //...
  }
```

如果您有多个品牌域名，请将所有的品牌域名都传递到该API，以确保您总是可以获取相关的转化数据，并深度链接到应用中。

**示例**

```objectivec
[AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com", @"click.greatapp.com"];
```

</Tab>

<Tab title="Swift">

请在AppDelegate.swift中使用该API，放在didFinishLaunchingWithOptions方法中。

```swift
   func application(_ application: UIApplication, didFinishLaunchingWithOptions 
        launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {
          AppsFlyerLib.shared().appsFlyerDevKey = "6CQi4Be6Zs9oNLsCusPbUL"
          AppsFlyerLib.shared().appleAppID = "340954504"
          AppsFlyerLib.shared().oneLinkCustomDomains = ["example.com"]
          //...
          //...
   }
```

如果您有多个品牌域名，可以将所有品牌域名以字符串数组的形式传递到该API。这样，无论您使用的是那个品牌链接，都可以保证转化数据的获取以及深度链接的实现。

**示例**

```objectivec
AppsFlyerLib.shared().oneLinkCustomDomains = ["promotion.greatapp.com", "click.greatapp.com"]
```

</Tab>
</Tabs>

</Tab>
</Tabs>

</Accordion>

<div id="using-and-testing-branded-domains" />

<Accordion title="使用并测试品牌域名">

**前期准备**：

在正式使用和测试前，请先完成[品牌域名设置流程](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app)中的所有步骤。

**请按以下步骤创建并测试品牌域名：**

1. 使用映射到品牌域名的OneLink模板<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#创建onelink链接">创建OneLink链接</Anchor>。
2. 将自定义归因链接复制粘贴到文本编辑器中。
3. 自定义归因链接由一个OneLink子域名、OneLink ID和自定义Link ID组成。将OneLink子域名替换为完整域名。请参考下方示例：

| 自定义归因链接 | 品牌域名 |
| --- | --- |
| **abcdef.onelink.me**/A1bc/dc1234ef | **click.abcdef.com**/A1bc/dc1234ef |

4. 使用品牌链接<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">测试激活和深度链接</Anchor>。
5. 如果您在测试过程中使用原始数据报告，则会在Original URL字段中看到品牌链接。

</Accordion>

<div id="editing-verifying-and-deleting-branded-domains" />

<Accordion title="修改、验证及删除品牌域名">

<div id="edit-a-branded-domain-mapping" />

#### **请按以下步骤修改品牌域名的映射：**

您可以修改现有完整域名的映射，将其关联到另一个OneLink子域名，无需再设置一个CNAME。

1. 从AppsFlyer后台的左侧的菜单栏中选择**互动** > **品牌域名**。
2. 进入您需要编辑的品牌域名。
3. 点击编辑图标（<Image alt="edit-subdomain.png" src="https://files.readme.io/ffe3da7d1c065a806a44c607bcf1231e06bf7e7478ca50187e57cb5ab876ae72-30192959751185.png" width="17px" />）。
4. 选择新建的OneLink子域名。
5. 点击<strong>下一步。</strong>无需再设置一个CNAME。
6. 点击**完成**。

<div id="important" />

> ❗️ **警告**
>
> 修改在投广告的品牌域名可能会使链接功能发生变化或失效。

<div id="verify-a-branded-domain-mapping" />

#### **验证品牌域名的映射**

如果您更改了映射到您品牌域名的OneLink子域名，请验证该品牌域名的映射可正常生效：

1. 从AppsFlyer后台的左侧的菜单栏中选择**互动** > **品牌域名**。
2. 进入您想要验证的品牌域名。
3. 点击验证图标（<Image alt="verify-2.png" src="https://files.readme.io/4ac94a535e9101b3e727351f67df8917c0870d6ede8ec963de8c5528893b8e2b-30192946342929.png" width="17px" />）。

<div id="note-5" />

> 📘 **注意**
>
> 如果由于CNAME记录尚未映射而导致验证失败，请在验证失败的消息弹窗中指定的日期之前（即7天内）完成映射。
> 如果相关的CNAME记录在截止日期前未完成映射，您需要刷新7天的映射期限。

<div id="domain-cname-record-no-longer-pointing-to-appsflyer" />

#### **域名CNAME记录不再指向AppsFlyer**

如果您将CNAME记录修改为不再指向AppsFlyer，您的品牌域名将被AppsFlyer中删除。

<div id="delete-a-branded-domain-mapping" />

#### **删除品牌域名的映射**

如需删除某个品牌域名，请联系您的CSM或发邮件至hello@appsflyer.com。

</Accordion>

<div id="troubleshooting-traits-and-limitations" />

## 问题排查、特点和局限性

<div id="troubleshooting" />

<Accordion title="问题排查">

| 问题表现 | 原因/解决方法 |
| --- | --- |
| 品牌域名无法映射到OneLink模板 | <ul><li>**域名无效：** 将品牌域名映射到OneLink模板时，AppsFlyer会验证该品牌链接中的域名是否有效。有效域名的格式应为：click.abdef.com</li><li>**该品牌域名已映射**：一个完整域名只能映射一次。</li></ul> |
| 品牌域名无法深度链接到应用中 | <ul><li>[请检查该品牌域名是否在正常使用中](#验证品牌域名的映射)</li><li>**验证CNAME**：确保有CNAME记录从您的品牌域名指向AppsFlyer。</li><li>**验证OneLink模板的深度链接设置**：出现该问题可能是因为OneLink的深度链接设置有误。请确保您已使用OneLink设置深度链接。</li><li>**OneLink映射变更**：您可以修改品牌域名，将其映射到另一个OneLink。如果新映射的OneLink的深度链接设置不同于之前的OneLink，或没有深度链接设置，则深度链接可能无法生效。</li></ul> |
| 未记录到来自品牌域名的激活 | <ul><li>**检查OneLink模板的设置**：确保映射到品牌域名的OneLink子域名所关联的应用正确无误。</li><li>**OneLink子域名变更：** 如果您的品牌域名所映射的OneLink模板或OneLink子域名发生变更，可能会影响归因。</li><li>**确保在应用中写入了**setOneLinkCustomDomain API。</li></ul> |
| 未记录到来自品牌域名的再互动 | 确保以下各项已配置完毕并已激活：<ul><li><Anchor target="_blank" href="/marketers/zh/docs/onelink-guide#设置onelink">使用OneLink配置深度链接</Anchor>。</li><li>相关应用使用了品牌域名专用的[SKD API setOneLinkCustomDomain](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer)。</li><li><Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide#retargeting-settings">应用配置页中的再营销开关已打开</Anchor>。</li></ul> |
| 在设置品牌域名的过程中界面提示“**该域名不存在**”。 | <ol><li>联系您的DNS管理员并让他们检查问题所在。</li><li>等待DNS管理员确认该域名已注册完毕。</li><li>点击**重新验证**。</li></ol> |
| 在设置品牌域名的过程中界面提示“**未找到AppsFlyer CNAME**” | <ol><li>让DNS管理员设置一个CNAME记录，让完整域名（即品牌域名）指向指定链接（即AppsFlyer host）。即如本文开头的图中所示，品牌链接指向AppsFlyer服务器。</li><li>等待DNS管理员确认该CNAME已激活。</li></ol> |
| 加载带有品牌域名的页面时提示**您已被屏蔽** | 由于品牌域名中不包含相关模板或任何参数，因此在使用品牌域名时，您必须在该品牌域名URL的末尾添加相关模板或参数。<br /><br />举例来说，假设您的品牌域名为“click.abcdef.com”，当您仅使用“**click.abcdef.com**”时，就会出现**您已被屏蔽**的报错。<br /><br />您必须在其末尾添加参数或模板，如click.abcdef.com **/A1bc/dc1234ef** |
| 加载带有品牌域名的页面时出现**err\_cert\_authority\_invalid**报错 | 出现该报错是因为Certificate Authority无法识别，说明您的品牌域名缺少有效的HTTP证书。由于AppsFlyer会使用Let’s Encrypt来为您的品牌域名签发证书，因此出现这类错误很可能是因为Let's Encrypt未能通过您域名的CAA（Certification Authority Authorization，证书颁发机构授权）DNS记录被识别为有效的Certificate Authority（CA）。<br /><br />**解决方案**<br />请完成以下操作：<ol><li>通过<Anchor target="_blank" href="https://www.entrust.com/resources/certificate-solutions/tools/caa-lookup">此类</Anchor>服务平台确认您的域名是否能将Let’s Encrypt识别为有效的CA。</li><li>让您的系统管理员更您的域名CAA记录，在其中添加Let's Encrypt，将其作为授权CA。</li></ol> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 是 ✓ / 否 **x** | 说明 |
| --- | --- | --- |
| 相关账户下的用户权限 | ✓ |  |
| 渠道权限 | **x** |  |
| 代理访问权限 | **x** | 代理无法创建品牌域名（或OneLink链接）。 |
| 代理数据透明化 | **x** |  |
| 应用层级的指定货币 | 不适用 |  |
| 应用层级的指定时区 | 不适用 |  |
| 品牌域名可用性 | 不适用 | 品牌域名仅适用于符合条件的付费套餐。如果您的订阅计划到期或被取消，则对品牌域名的访问权限将被移除，并且使用您的品牌域名的现有链接将无法工作。 |
| 字符限制 | 不适用 | 输入您的品牌域名时，最后一个字符不能为句点（“.”）。 |
| 数据时效性 | 不适用 |  |
| 历史数据 | ✓ |  |
| HTTP | **x** | 品牌链接不支持超文本传输协议（HTTP），必须使用超文本传输安全协议（HTTPS）。 |
| 非自然量数据 | ✓ |  |
| 自然量数据 | ✓ |  |
| 拉取频次限制 | ✓ | 品牌域名的SSL/HTTP证书是由AppsFlyer通过<Anchor target="_blank" href="https://letsencrypt.org/">Let's Encryp</Anchor>提供的，每个域名每周最多可获取50个新证书。 |
| 大小限制 | 不适用 |  |
| SSL/HTTP证书更新 | ✓ | 由AppsFlyer管理的品牌域名SSL/HTTP证书会自动更新，无需您执行任何操作。 |

</Accordion>

<div data-zendesk-anchors="branded-domains=%E5%93%81%E7%89%8C%E5%9F%9F%E5%90%8D h_01HFM51V4PE53FQAED68V8Q834=%E5%93%81%E7%89%8C%E5%9F%9F%E5%90%8D principles-of-implementation=%E9%83%A8%E7%BD%B2%E5%8E%9F%E7%90%86 h_01HFM51V4PPJXMCSV5ZVDPT49M=%E9%83%A8%E7%BD%B2%E5%8E%9F%E7%90%86 setting-up-branded-domains=%E5%93%81%E7%89%8C%E5%9F%9F%E5%90%8D%E7%9A%84%E8%AE%BE%E7%BD%AE h_01HFM51V4PH58ZA4ZXHP5J6K2W=%E5%93%81%E7%89%8C%E5%9F%9F%E5%90%8D%E7%9A%84%E8%AE%BE%E7%BD%AE procedures=%E8%AE%BE%E7%BD%AE%E6%B5%81%E7%A8%8B h_01HFM51V4PWWX7TBCHFMPR3QVB=%E8%AE%BE%E7%BD%AE%E6%B5%81%E7%A8%8B h_01HQ5CWGQNRBXQ6QQDADV7XCQP=set-up-a-branded-domain-in-appsflyer h_01HQ5CWGQN7ED03CBQE3XMJQC6=%E6%B3%A8%E6%84%8F h_01HQ5DHKPW0RBEDZ3JVZRV37JW=%E6%B3%A8%E6%84%8F-1 renew-the-day=%E5%88%B7%E6%96%B0cname%E8%AE%B0%E5%BD%95%E7%9A%847%E5%A4%A9%E6%98%A0%E5%B0%84%E6%9C%9F%E9%99%90 h_01HQ5CWGQNQJJ1CXDKTGZ8N9ZE=%E5%88%B7%E6%96%B0cname%E8%AE%B0%E5%BD%95%E7%9A%847%E5%A4%A9%E6%98%A0%E5%B0%84%E6%9C%9F%E9%99%90 h_01HQ5CWGQNEPDY6J30B6VY0FCP=%E6%B3%A8%E6%84%8F-2 h_01HQ5CWGQNSRNKQHARJCB3C5EA=%E6%B3%A8%E6%84%8F-3 custom-ssl-certificate=%E8%87%AA%E5%AE%9A%E4%B9%89-ssl-%E8%AF%81%E4%B9%A6%E5%8F%AF%E9%80%89 h_01KM0E8VHARA2JRAR2H37QM91Y=%E8%87%AA%E5%AE%9A%E4%B9%89-ssl-%E8%AF%81%E4%B9%A6%E5%8F%AF%E9%80%89 h_01KM0FTWTX09651KY524RH9JSJ=%E6%B3%A8%E6%84%8F-4 h_01HFM51V4PP0NQHVHTKB86250R=set-up-branded-domains-in-the-app h_01HFM51V4PN0FPEDNAF0Q1QS8P=using-and-testing-branded-domains h_01HQ5CWGQPZ6MEFA6MDTHYHCSA=editing-verifying-and-deleting-branded-domains edit-a-branded-domain-mapping=%E8%AF%B7%E6%8C%89%E4%BB%A5%E4%B8%8B%E6%AD%A5%E9%AA%A4%E4%BF%AE%E6%94%B9%E5%93%81%E7%89%8C%E5%9F%9F%E5%90%8D%E7%9A%84%E6%98%A0%E5%B0%84 h_01HQ5FJZD6QMNFA45Z2C7CA3ST=%E8%AF%B7%E6%8C%89%E4%BB%A5%E4%B8%8B%E6%AD%A5%E9%AA%A4%E4%BF%AE%E6%94%B9%E5%93%81%E7%89%8C%E5%9F%9F%E5%90%8D%E7%9A%84%E6%98%A0%E5%B0%84 h_01HQ5G6ZQ481TGXA0P6FNB4NN7=%E8%AD%A6%E5%91%8A verify-a-branded-domain-mapping=%E9%AA%8C%E8%AF%81%E5%93%81%E7%89%8C%E5%9F%9F%E5%90%8D%E7%9A%84%E6%98%A0%E5%B0%84 h_01HQ5FK5XJNZ1EABJA66RMYBCN=%E9%AA%8C%E8%AF%81%E5%93%81%E7%89%8C%E5%9F%9F%E5%90%8D%E7%9A%84%E6%98%A0%E5%B0%84 h_01HQ5CWGQP7F54G518AKV2PV1G=%E6%B3%A8%E6%84%8F-5 domain-cname-record-no-longer-pointing-to-appsflyer=%E5%9F%9F%E5%90%8Dcname%E8%AE%B0%E5%BD%95%E4%B8%8D%E5%86%8D%E6%8C%87%E5%90%91appsflyer h_01JSHFECXS00M6BXH8168ZWJE5=%E5%9F%9F%E5%90%8Dcname%E8%AE%B0%E5%BD%95%E4%B8%8D%E5%86%8D%E6%8C%87%E5%90%91appsflyer delete-a-branded-domain-mapping=%E5%88%A0%E9%99%A4%E5%93%81%E7%89%8C%E5%9F%9F%E5%90%8D%E7%9A%84%E6%98%A0%E5%B0%84 h_01JSHF5RMXXFJTXC246KKAQBSS=%E5%88%A0%E9%99%A4%E5%93%81%E7%89%8C%E5%9F%9F%E5%90%8D%E7%9A%84%E6%98%A0%E5%B0%84 troubleshooting-traits-and-limitations=%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5%E7%89%B9%E7%82%B9%E5%92%8C%E5%B1%80%E9%99%90%E6%80%A7 h_01HFM51V4PH4YM13DVXENRWF2E=%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5%E7%89%B9%E7%82%B9%E5%92%8C%E5%B1%80%E9%99%90%E6%80%A7 h_01HFM51V4PJNHZTD97X75WPN98=troubleshooting h_01HFM51V4QQ2TZQMJ2ATNDG91F=traits-and-limitations" />
