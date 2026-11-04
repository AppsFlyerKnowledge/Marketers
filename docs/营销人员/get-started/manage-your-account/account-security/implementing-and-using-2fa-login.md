---
title: 双重身份验证登录方式的设置与使用
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
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
    - Ad Networks
  created_at: '2020-06-22T10:25:26Z'
  edited_at: '2026-10-14T10:11:55Z'
  id: 360010178037
  locale: zh-cn
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/zh-cn/articles/360010178037
---
> **概要：** 使用双重身份验证（2FA），为登录流程加强安全防护。使用凭证登录的用户需要通过Google Authenticator或短信验证作为补充。

<div id="highlights" />

## 主要特点

* 双重身份验证是一项可由管理员启用的功能。
* 可选的验证方式为**Google Authenticator**和**短信验证。**
* 启用/停用后对所有账号用户生效。
* 启用时已存在的账号用户可正常登录，下次登录系统将提示用户设置双重身份验证。

<div id="-admin-managing-2fa" />

## ![admin.png](https://files.readme.io/d54680123b25ab7929285cebd778e0e74bd0d032df994b04d1bca106381c3dc6-360014518718.png) 管理员： 管理双重身份验证

只有管理员用户可以启用、重置或停用用户的双重身份验证设置。

<div id="activate" />

<Accordion title="启用">

若管理员同时启用了**Google Authenticator**和**短信验证**，则用户可以在两者中自行选择。

<div id="note" />

> 📘 **注意**
>
> 短信验证依赖于短信的成功送达率，送达率可能因移动运营商和国家/地区而有所差异。因此，强烈建议同时启用短信验证和Google Authenticator，以避免因短信发送失败而无法登陆。

**启用双重身份验证：**

1. 从页面顶部导航栏打开账户菜单（点击右上角的邮箱地址，打开下拉菜单）> **安全中心**。
2. 在**增强登录安全性**部分，点击**配置登录方式**，进入**登录安全**页面。
3. 在**双重身份验证**部分，开启**Google Authenticator**和/或**短信验证**开关。

</Accordion>

<div id="reset" />

<Accordion title="重置">

如果您的账户使用2FA，有时可能会需要重置个别用户的2FA设置。请注意，重置后默认的2FA登录界面是**Google Authenticator**。

**重置双重身份验证：**

1. 点击菜单栏中的邮箱地址，打开下拉菜单
2. 选择**用户管理**。
3. 点击**用户**选项卡中的菜单按钮<Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" />（位于用户行的最右边）。
4. 在菜单中选择**重置2FA**。

**注意：** 管理员可以重置其他管理员的2FA，但不能重置自己或<Anchor target="_blank" href="/marketers/zh/docs/user-management#管理员">账户所有者</Anchor>的2FA。如需重置账户所有者的2FA，请联系AppsFlyer技术支持团队。

</Accordion>

<div id="deactivate" />

<Accordion title="停用">

如停用2FA，账户用户仅需使用用户名和密码即可登录。

**停用双重身份验证:**

1. 从页面顶部导航栏打开账户菜单（点击右上角的邮箱地址，打开下拉菜单）> **安全中心**。
2. 在**增强登录安全性**部分，点击**配置登录方式**，进入**登录安全**页面。
3. 在**双重身份认证 (2FA)** 部分，停用 **Google Authenticator**和/或 **短信验证**开关。
4. 确认停用。

</Accordion>

<div id="account-users-using-google-or-microsoft-authenticator" />

## 账户用户：使用Google Authenticator验证

系统初始默认的2FA界面为**Google Authenticator**；此外，用户登录时系统也会显示上次登录使用的验证方式。

如果您选择不使用**Google Authenticator**，则可以在设置和登录界面中点击相应链接，跳转到短信验证的2FA界面。

<div id="firsttime-setup" />

<Accordion title="首次设置">

在首次使用2FA之前，每位账户用户须下载**Google Authenticator**和**二维码**扫描应用。用户可在**Google Play** (Android) 或**App Store** (iOS)中下载此类应用。

**新增账户用户**

1. 按照邮件指引创建密码。
2. 登录**AppsFlyer**后，系统会自动跳转至2FA设置页面。
3. 开始设置2FA。
   * 下载**Google Authenticator**和**二维码**扫描应用。
   * 扫描二维码。
   * 输入**Google Authenticator**生成的验证码。
   * 点击**验证**，系统会跳转至**我的应用**页面。

**已有账户用户**

1. 使用用户名和密码登录**AppsFlyer**后，系统会自动跳转至2FA设置页面。
2. 开始设置2FA。
   * 下载**Google Authenticator**和**二维码**扫描应用。
   * 扫描二维码。
   * 输入**Google Authenticator**生成的验证码。
   * 点击**验证**，系统会跳转至**我的应用**页面。

</Accordion>

<div id="ongoing-use" />

<Accordion title="后续使用">

**请按照以下步骤操作。**

1. 登录**AppsFlyer**（使用用户名和密码）后，系统会自动跳转至2FA登陆页面。
2. 在您的手机上打开**Google Authenticator**，获取验证码。
3. 在2FA页面中输入代码。
4. 点击**验证**，系统将跳转至**我的应用**页面。

</Accordion>

<div id="account-users-using-sms-verification" />

## 账户用户：使用短信验证

如果您选择不使用**短信**，则可以在设置和登录界面中点击相应链接，跳转到**Google Authenticator**的2FA界面。

<div id="firsttime-sms-setup" />

<Accordion title="首次设置">

**Google Authenticator**是默认的2FA方法。如需切换至**短信验证**，请在界面上点击**短信验证**链接。

**新增账户用户**

1. 按照邮件指引创建密码。
2. 登录**AppsFlyer**后，系统会自动跳转至2FA设置页面。
3. 设置2FA：
   * 输入您的电话号码（仅数字，不要输入特殊字符），然后单击**发送验证码。**
   * 输入短信验证码 > 单击**验证。**

**已有账户用户**

1. 使用用户名和密码登录**AppsFlyer**后，系统会自动跳转至2FA设置页面。
2. 设置2FA：
   * 输入您的电话号码（仅数字，不要输入特殊字符），然后单击**发送验证码。**
   * 输入短信验证码 > 单击 **验证。**

</Accordion>

<div id="ongoing-sms-use" />

<Accordion title="后续使用">

**请按照以下步骤操作：**

1. 使用用户名和密码登录**AppsFlyer**后，系统会自动跳转至2FA登陆页面。
2. 如果在您上次登录时使用了**短信验证**，页面会直接显示短信验证界面；如果不是，请单击**Google Authenticator** 2FA页面底部的链接。
3. 系统会自动显示您已绑定的手机号，点击**发送验证码。**
4. 输入短信收到的验证码。
5. 点击**验证。**

</Accordion>

<div data-zendesk-anchors="highlights=%E4%B8%BB%E8%A6%81%E7%89%B9%E7%82%B9 h_01HEHRKE8PY64KWVSSFR6T4F1Z=%E4%B8%BB%E8%A6%81%E7%89%B9%E7%82%B9 admin-managing-2fa=-%E7%AE%A1%E7%90%86%E5%91%98-%E7%AE%A1%E7%90%86%E5%8F%8C%E9%87%8D%E8%BA%AB%E4%BB%BD%E9%AA%8C%E8%AF%81 h_01HEHRKE8PZA3H9SXPRD1FZ50S=-%E7%AE%A1%E7%90%86%E5%91%98-%E7%AE%A1%E7%90%86%E5%8F%8C%E9%87%8D%E8%BA%AB%E4%BB%BD%E9%AA%8C%E8%AF%81 h_01HEHRKE8PV0ZADPXHNBBDMKAF=activate 01JCDTA1W486FEFRPT2VYJ2PVX=%E6%B3%A8%E6%84%8F h_01HEHRKE8P9N2W871ZEB1D3MYN=reset h_01HEHRKE8PEDWCNKMG1N4CFDMN=deactivate account-users-using-google-authenticator=%E8%B4%A6%E6%88%B7%E7%94%A8%E6%88%B7%E4%BD%BF%E7%94%A8google-authenticator%E9%AA%8C%E8%AF%81 h_01HEHRKE8P1A2BARBDVMJPH1WY=%E8%B4%A6%E6%88%B7%E7%94%A8%E6%88%B7%E4%BD%BF%E7%94%A8google-authenticator%E9%AA%8C%E8%AF%81 h_01HEHRKE8QQTX3Y9ZY1HZ6GBAG=firsttime-setup h_01HEHRKE8QHWHCMNB5M7S5YVYJ=ongoing-use account-users-using-sms-verification=%E8%B4%A6%E6%88%B7%E7%94%A8%E6%88%B7%E4%BD%BF%E7%94%A8%E7%9F%AD%E4%BF%A1%E9%AA%8C%E8%AF%81 h_01HEHRKE8QZ245ZYBZ4FF814KN=%E8%B4%A6%E6%88%B7%E7%94%A8%E6%88%B7%E4%BD%BF%E7%94%A8%E7%9F%AD%E4%BF%A1%E9%AA%8C%E8%AF%81 h_01HEHRKE8Q30QHGZ5QYMV4MR27=firsttime-sms-setup h_01HEHRKE8Q0229YE5QP5EJFSD8=ongoing-sms-use" />
