---
title: 使用您的身份提供者 (IdP) 设置 SSO 身份验证
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - login security
    - SSO
    - SSO verification
    - SSO certificate
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
  created_at: '2020-11-02T10:50:55Z'
  edited_at: '2026-10-14T10:13:35Z'
  id: 360015017198
  locale: zh-cn
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/zh-cn/articles/360015017198
---
> **概要：** 通过将 AppsFlyer 与您的身份提供者 (IdP) 集成，AppsFlyer 账户用户可以使用单点登录 (SSO) 登录 AppsFlyer。了解如何在 AppsFlyer 和您的 IdP 平台中设置 SSO 身份验证。

<div id="note" />

<div id="considerations" />

## 注意事项

* **前期准备：** 用户必须在两个系统 (AppsFlyer 和 IdP) 中使用相同的电子邮件进行设置。
* SSO 配置设置只能由管理员管理和删除。
* 当 **强制 SSO** 被设置时，所有用户必须通过 SSO 登录，个别用户无法被排除。
* 使用 SSO 时不支持 2FA。
* 不建议同时启用用户名和密码的 SSO。

<div id="access-the-sso-configuration-page" />

## 访问 SSO 配置页面

1. 从页面顶部导航栏打开账户菜单（点击右上角的邮箱地址，打开下拉菜单）> **安全中心**。
2. 在 **增强登录安全性** 下，选择 **配置登录方法**。
3. 在 **登录安全性** 页面，点击 **配置 SSO**。

<div id="set-up-sso" />

## 设置 SSO

SSO 配置在 IdP 平台和 AppsFlyer 中完成，具体步骤如下。 配置状态可以是 **活动**（当 SSO 设置完成时），或 **未配置**（当没有设置配置或配置已被删除时）。

<div id="note-1" />

> 📘 **注意**
>
> * 本指南包括以下 IdP 的详细程序。为所有其他 IdP 描述了一般设置概述。
>   * JumpCloud
>   * Okta
>   * OneLogin
>   * Ping Identity

<div id="step-1-set-up-the-idp-platform" />

<Accordion title="第1步：设置 IdP 平台">

请参阅以下 IdP 中配置 SSO 身份验证的详细程序：

* <Anchor target="_blank" href="/marketers/zh/docs/configure-appsflyer-sso-in-jumpcloud">JumpCloud</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/configure-appsflyer-sso-in-okta">Okta</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/configure-appsflyer-sso-in-onelogin">OneLogin</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/configure-appsflyer-sso-in-ping-identity">Ping Identity</Anchor>

<div id="setup-overview-for-other-idp-platforms" />

#### 其他 IdP 平台的设置概述

配置其他 IdP 平台的过程如下所示：

* 在 IdP 平台上使用 SAML 2.0 协议创建一个 AppsFlyer 应用，并在 IdP 平台中集成 [AppsFlyer 认证证书](#the-authentication-certificate)。
* 将用户分配到新创建的 AppsFlyer 应用。
* 检索 IdP 证书或元数据以在 AppsFlyer 中使用（如 [第 2 步中提到的：设置 AppsFlyer --> 5。提供 IdP 元数据](#step-5-provide-idp-metadata)）。

<div id="note-2" />

> 📘 **注意**
>
> * <strong>重要提示！</strong>在将用户分配给 IdP 时，请确保使用与 AppsFlyer 中相同的用户电子邮件，以便两个平台上的每个用户都有相同的电子邮件。
> * <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">AppsFlyer 元数据</Anchor> 包含：
>   * 加密和签名证书
>   * 实体ID
>   * Callback URL

<div id="step-2-set-up-appsflyer" />

<Accordion title="第2步：设置 AppsFlyer">

以下流程将引导您完成在 IdP 平台上配置后在 AppsFlyer 中设置 SSO 认证的步骤。

查看如何 [访问 SSO 配置设置页面](#访问-sso-配置页面)。

<div id="step-1-select-authentication-starting-point" />

<Accordion title="1. 选择认证起点">

1. 选择用户进入 AppsFlyer 的位置。这也定义了认证过程。
   * [身份提供者 (IdP)](#身份提供者-idp)
   * [服务提供者 (AppsFlyer)](#服务提供商appsflyer)
2. 点击**Next**。

<div id="identity-provider-idp" />

#### 身份提供者 (IdP)

用户通过 IdP 认证插件或网页登录，然后在认证后被引导到 AppsFlyer。

<div id="note-3" />

> 📘 **注意**
>
> 通过选择此选项，用户可以通过 IdP 和服务提供商（AppsFlyer）登录。

<div id="service-provider-appsflyer" />

#### 服务提供商（AppsFlyer）

用户通过点击 <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-callback">AppsFlyer SSO 登录页面</Anchor> 中的 **使用 SSO 登录** 并输入他们的电子邮件地址进入 AppsFlyer。然后，他们被引导到 IdP 进行认证，并重定向到 AppsFlyer 主页。

<Image align="center" alt="AppsFlyer_login_page.png" src="https://files.readme.io/fb80e44cf0cad29349ec85f75f65de73041b1787b278ae9d96449783580faeaa-17233244722577.png" width="257px" />

<div id="note-4" />

> 📘 **注意**
>
> 通过选择此选项，用户只能通过服务提供商（AppsFlyer）登录，而不能直接从 IdP 登录。

<div id="step-2-set-login-method" />

<Accordion title="2. 设置登录方式">

1. 选择用户如何登录 AppsFlyer：
   * **强制 SSO** [推荐]： 此方法强制执行更安全的登录。
   * **SSO 或用户名和密码**：用户可以选择通过 SSO 或使用他们的用户名和密码登录。
2. 点击**Next**。

</Accordion>

<div id="step-3-select-certificate-type" />

<Accordion title="3. 选择证书类型">

AppsFlyer 提供两种类型的公共加密密钥证书来加密数据和签署 SSO 请求：

* **AppsFlyer 签名证书：** 从 <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">AppsFlyer 元数据 URL</Anchor> 创建的 AppsFlyer 证书。
* **CA 签名证书：** 由 **亚马逊** 签名的 AppsFlyer 证书。

**执行此步骤：**

* 选择证书类型并点击 **下一步**.

<div id="6-activate-sso" />

<div id="5-add-exception-users" />

<div id="activation-results" />

<div id="note-7" />

<div id="delete-an-exception-user" />

<div id="add-login-methods-for-multiple-users" />

<div id="note-6" />

<div id="note-5" />

> 📘 **注意**
>
> 证书仅在双方完成相互证书实施过程后激活：AppsFlyer 集成了 IdP SAML 配置，IdP 集成了最新的 AppsFlyer SSO 元数据。以下是完成此操作的步骤。

</Accordion>

<div id="step-4-obtain-service-provider-appsflyer-metadata" />

<Accordion title="4. 获取服务提供商（AppsFlyer）元数据">

1. 复制最新的 AppsFlyer SSO 元数据并将其实施到您的 IdP SAML 配置中。
   * 如果您选择了 **AppsFlyer 签名的证书：** 复制以下任意字段。
     * **元数据 URL:** 对于支持完整元数据 URL 的 IdP，请复制 URL 并将其实施到您的 IdP 中。
     * **元数据组件:** 对于不支持完整元数据 URL 的 IdP，请复制每个组件并将其实施到您 IdP 中的相应部分：**实体 ID**，**加密密钥**（可下载），和 **位置 URL**。
     * **XML 文件:** 您可以选择将 AppsFlyer SSO 元数据下载为 XML 文件。
   * 如果您选择了 **CA 签名的证书：** 复制 **元数据组件**。
2. 点击**Next**。

</Accordion>

<div id="step-5-provide-idp-metadata" />

<Accordion title="5. 提供 IdP 元数据">

使用以下选项提供 IdP SSO 元数据，然后验证元数据格式。**请注意**：IdP 证书数据必须为单行格式，且不包含元字符。

1. 选择提供 IdP 元数据的首选方法：
   * **URL**: 输入 IdP 元数据 URL。
   * **XML 文件:** 上传 IdP 元数据 XML 文件。
2. 点击**验证**。页面顶部会出现一条确认消息，指示验证状态。
3. 点击 **激活**。页面顶部会出现一条确认消息，指示 SSO 认证激活状态。

</Accordion>

</Accordion>

<div id="step-3-test-the-sso-configuration" />

<Accordion title="第3步：测试 SSO 配置">

在两个平台（IdP 和 AppsFlyer）上完成 SSO 配置后，检查用户是否可以通过 **任一** [URL 回调方法&lt;2>：您的 IdP 或服务提供商（AppsFlyer），但不能同时使用。](#single-signon-url-configuration)

<div id="test-authentication-via-your-idp" />

#### 通过您的 IdP 测试认证

如果您已配置通过 IdP 登录的认证，请检查用户是否可以通过 IdP 插件或网页进入 AppsFlyer：

1. 如果您已登录到 AppsFlyer 和 IdP，请从两者中注销。
2. 在隐身模式下打开网页。
3. 访问您的 IdP 网页。由于您未登录到 IdP，您将经历一个认证过程。使用相关用户登录。
4. 搜索并选择 AppsFlyer。您将被引导到 AppsFlyer 主页。这表明过程成功。

<div id="test-authentication-via-your-service-provider-appsflyer" />

#### 通过您的服务提供商（AppsFlyer）测试认证

如果您已配置通过服务提供商（AppsFlyer）登录的认证流程，请检查用户是否可以使用他们的电子邮件进入 AppsFlyer：

<Image align="center" alt="log_in_to_af_by_email2.png" src="https://files.readme.io/ae22ff9ba0216f54bee4cea82ed7d35cea656a68e30c0a0e4f549b1855ec7cfd-17233244746257.png" width="245px" />

1. 如果您已登录到 AppsFlyer 和 IdP，请从两者中注销。
2. 在隐身模式下打开网页。
3. 访问 <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">AppsFlyer 登录页面</Anchor> 并点击 **使用 SSO 登录**。
4. 输入相关电子邮件并点击 **继续**。您现在被引导到身份提供者进行身份验证。
5. 在身份提供者身份验证后，您将作为已登录用户被引导回 AppsFlyer。这表明过程成功。

</Accordion>

</Accordion>

</Accordion>

<div id="edit-exception-users-1" />

<div id="note-8" />

<div id="important" />

<div id="manage-sso-configuration" />

## 管理 SSO 配置

一旦您设置了 SSO 配置，您可以编辑该配置或将其删除。

查看如何 [访问 SSO 配置页面](#访问-sso-配置页面)。

<div id="zd-edit-sso" />

<div id="edit-exception-users" />

<div id="edit-sso" />

<Accordion title="编辑 SSO">

在此页面上，您可以编辑以下任何选项：

* 身份验证起始点
* 登录方式
* 证书类型
* 服务提供者（AppsFlyer 元数据） - 详细信息可以获取
* 身份提供者元数据

> 🚧 **重要提示！**
>
> 更改证书类型或身份验证起始点时，AppsFlyer 元数据会发生变化。在保存更改后，立即复制最新的服务提供者（AppsFlyer）SSO 元数据并在您的 IdP SAML 配置中实施。

**要编辑 SSO 配置：**

1. 点击 **编辑** <Image alt="edit-icon.jpg" src="https://files.readme.io/d32f150cb5d0271c5504fb3c107e23f73e59c9a3be1630769ad309edf4e79ea0-31780971794321.jpg" width="24px" />图标，位于 **SAML 单点登录 (SSO)** 部分的右侧。
2. 转到任何部分并选择您首选的选项。
3. 点击**Save changes**。出现确认消息，指示更改的状态。

</Accordion>

<div id="remove-sso-configuration" />

<Accordion title="删除 SSO 配置">

**要删除SSO配置：**

1. 从**SAML单点登录(SSO)** 部分右侧点击**删除**垃圾桶图标。
2. 转到任何部分并选择您首选的选项。
3. 点击**Save changes**。出现确认消息，指示更改的状态。

> 📘 **注意**
>
> 删除SSO配置时，存储在AppsFlyer中的IdP SSO元数据将被删除。

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 描述 |
| --- | --- |
| 电子邮件地址中的符号 | SSO不支持带有+符号的电子邮件地址。<br /><br />例如：my+customer@demo.com<br /><br />拥有此项将导致登录失败。 |

</Accordion>

<div id="see-also" />

> 📄 **相关文档**
>
> <Anchor target="_blank" href="/marketers/zh/docs/sso-authentication-overview-and-faq">了解SSO认证并找到常见问题的答案</Anchor>

<div data-zendesk-anchors="considerations=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 h_01J7KK52TX8WGA3EK110R9M0GY=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 access-the-sso-configuration-page=%E8%AE%BF%E9%97%AE-sso-%E9%85%8D%E7%BD%AE%E9%A1%B5%E9%9D%A2 h_01J7X4Y5Y50EFAPVP6JY8WAMKN=%E8%AE%BF%E9%97%AE-sso-%E9%85%8D%E7%BD%AE%E9%A1%B5%E9%9D%A2 setting-up-sso-authentication=%E8%AE%BE%E7%BD%AE-sso h_01HCHG901V25TSRGRT9244384D=%E8%AE%BE%E7%BD%AE-sso h_01J530X1930CMCF7XJM1XKPC74=%E6%B3%A8%E6%84%8F 01J530ZP34SQKHM5324DNFA25Y=step-1-set-up-the-idp-platform configuration-overview-for-other-idp-platforms=%E5%85%B6%E4%BB%96-idp-%E5%B9%B3%E5%8F%B0%E7%9A%84%E8%AE%BE%E7%BD%AE%E6%A6%82%E8%BF%B0 h_01HCHG901VPG0ZJ20XJBFPY7CD=%E5%85%B6%E4%BB%96-idp-%E5%B9%B3%E5%8F%B0%E7%9A%84%E8%AE%BE%E7%BD%AE%E6%A6%82%E8%BF%B0 h_01HCHG901VH2XZS9Q0KM9D26WX=%E6%B3%A8%E6%84%8F-1 h_01J5303SNTEVQNA4KZEMS2VG04=step-2-set-up-appsflyer h_01J4PGJ2T73313B1X6ECQ17S7Q=step-1-select-authentication-starting-point identity-provider-idp=%E8%BA%AB%E4%BB%BD%E6%8F%90%E4%BE%9B%E8%80%85-idp h_01J4PHJ8FECGSAGQJGWREX3PKK=%E8%BA%AB%E4%BB%BD%E6%8F%90%E4%BE%9B%E8%80%85-idp h_01J4PHSVS55G2M00S00KG06BB7=%E6%B3%A8%E6%84%8F-2 service-provider-appsflyer=%E6%9C%8D%E5%8A%A1%E6%8F%90%E4%BE%9B%E5%95%86appsflyer h_01J4PHTR1E9JV3SM0A7N4X3WJY=%E6%9C%8D%E5%8A%A1%E6%8F%90%E4%BE%9B%E5%95%86appsflyer h_01J4PJEQTBJ9P2SZBKGPF2696S=%E6%B3%A8%E6%84%8F-3 h_01J4PGJ2T7BQKNS08R22WFPM50=step-2-set-login-method h_01J4PGJ2T76F7YTK42VBW8J1P6=step-3-select-certificate-type h_01J8CEE2BZN0THJ7DNSGRCGJNQ=%E6%B3%A8%E6%84%8F-4 h_01J4PGJ2T76PKE0V7NS7YXC4T5=step-4-obtain-service-provider-appsflyer-metadata h_01J4PGJ2T7SM8EGYZCW6D7AQN8=step-5-provide-idp-metadata h_01J5303SNTYMDMP2DW4GQCGEHK=step-3-test-the-sso-configuration testing-authentication-via-the-idp=%E9%80%9A%E8%BF%87%E6%82%A8%E7%9A%84-idp-%E6%B5%8B%E8%AF%95%E8%AE%A4%E8%AF%81 h_01HCHG901WXSQ2VPCH2NKE63SE=%E9%80%9A%E8%BF%87%E6%82%A8%E7%9A%84-idp-%E6%B5%8B%E8%AF%95%E8%AE%A4%E8%AF%81 testing-authentication-via-appsflyer=%E9%80%9A%E8%BF%87%E6%82%A8%E7%9A%84%E6%9C%8D%E5%8A%A1%E6%8F%90%E4%BE%9B%E5%95%86appsflyer%E6%B5%8B%E8%AF%95%E8%AE%A4%E8%AF%81 h_01HCHG901W6DJ3GN6E7WFR6RNK=%E9%80%9A%E8%BF%87%E6%82%A8%E7%9A%84%E6%9C%8D%E5%8A%A1%E6%8F%90%E4%BE%9B%E5%95%86appsflyer%E6%B5%8B%E8%AF%95%E8%AE%A4%E8%AF%81 manage-sso-configuration=%E7%AE%A1%E7%90%86-sso-%E9%85%8D%E7%BD%AE h_01J7WKPGTNPF10N4XMJG9ZDN87=%E7%AE%A1%E7%90%86-sso-%E9%85%8D%E7%BD%AE h_01J7X4P6B18HXJB99JYTVSC75N=edit-sso h_01J7WT7362KNX2K9KGW48R2N1P=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01J7X4P6B1THTVR1M966JS4P99=remove-sso-configuration h_01J7X4D9F2BDH1SPBJPNV929X0=%E6%B3%A8%E6%84%8F-5 h_01K44S4WP3N8HG872PQX1CCES8=traits-and-limitations h_01HDPF69BTMRYR6E6VNMFR4JY4=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
