---
title: 高级安全套餐
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
  created_at: '2025-04-03T11:42:43Z'
  edited_at: '2026-10-14T10:01:54Z'
  id: 34053592094737
  locale: zh-cn
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/zh-cn/articles/34053592094737
---
> **概要：高级安全软件包是** 专为企业级身份管理、令牌访问控制和扩展审计可见性而设计的高级产品，可增强对账户的保护。

<div id="intro" />

## 引言

高级安全软件包汇集了三个关键功能，可提升贵组织的安全性：

* **具有服务限制的多令牌管理**：跨 API、S2S 和 OneLink 的可扩展令牌创建和细粒度访问控制。
* **审计日志 API，可延长保留时间**：获得平台活动的长期可见性，并将审计事件整合到监控堆栈中。
* **SCIM 配置**：通过身份提供商实现用户访问控制的自动化和集中化。
* **允许登录的 IP 地址列表：** 防止未经授权的访问，确保仅从受信任的网络和 IP 登录 AppsFlyer 仪表板

<div id="compare-the-standard-and-enterprise-grade-packages" />

### 比较标准套餐和高级套餐：

| 功能 | 标准套餐 | 高级安全套餐 |
| --- | --- | --- |
| [单点登录（SSO）](/docs/enterprise-grade-security-package#accordion-item) | SSO 登录（仅限现有客户） | 支持 SSO SAML 2.0 与 SCIM 自动配置，实现用户与角色管理自动化 |
| [Token 管理](/docs/enterprise-grade-security-package#multitoken-management-with-restrictions) | 每种类型最多管理 2 个 token（API、S2S 或 OneLink） | 每种类型最多管理 30 个 token，权限控制更精细 |
| [审核日志访问](/docs/enterprise-grade-security-package#audit-log-api-and-extended-retention) | 仅限用户界面访问，数据保留 90 天 | UI 和 API 访问，数据保留 180天 |
| [基于角色的用户管理（RBAC）](/docs/enterprise-grade-security-package#multitoken-management-with-restrictions) | 最多 10 个自定义角色 | 最多 50 个自定义角色 |
| [IP 白名单](/docs/enterprise-grade-security-package#ip-allowlist) | 应用程序接口的 IP 允许列表 | 允许登录的 IP 列表和增强安全性的应用程序接口 |
| 24/7 安全监控 | 包含 | 包含 |
| 多重身份验证 | 包含 | 包含 |

<div id="multitoken-management-with-restrictions" />

<Accordion title="有限制的多令牌管理">

每种类型（API、S2S、OneLink）最多可创建和管理**30 个令牌**，并有**服务级别限制**，以提高令牌的可扩展性、安全性和控制力。

<div id="key-features" />

#### 主要功能

* 与标准令牌的 2 个令牌相比，管理员可为**每种类型**创建多达**30** 个令牌，从而为更大的团队和复杂的工作流程提供支持。
* 为 API 标记分配特定于服务的访问权限，限制对敏感操作的访问。
* 代币可以撤销或轮换，而不会破坏集成或自动化。
* 通过特定令牌权限，简化与内部团队和外部合作伙伴的协作。

<div id="example" />

> 📄 **示例**
>
> 创建两个令牌，以帮助保持最小权限访问，防止意外暴露数据。
>
> **仅数据访问令牌：** 创建一个只能访问汇总数据的令牌。该令牌无法访问原始数据或执行更改配置等操作。将其用于分析团队或只读机构用户。
>
> **仅用于设置的访问令牌：** 发布一个令牌，让内部团队管理配置设置，但不允许他们提取数据。这就将管理功能与数据访问隔离开来。

<div id="note" />

> 📘 **注意**
>
> 有关标准令牌的一般信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">管理 AppsFlyer 令牌</Anchor>。

<div id="how-to-access-and-control-tokens" />

#### 如何访问和控制令牌

**创建受限令牌**

1. 从页面顶部导航栏打开账户菜单（点击右上角的邮箱地址，打开下拉菜单）> **安全中心。**
2. 进入**令牌管理**页面。
3. 单击**创建token**。
4. 选择token类型。
   * API
   * S2S
   * OneLink
5. 对于**API 标记**，请从**访问限制** **下拉菜单**中选择一个或多个服务。  
   访问是二进制的：完全访问或无访问。
6. 点击**保存**。

**管理代币**

要管理令牌，请从顶部栏打开账户菜单（电子邮件地址下拉菜单）->**安全中心-> 令牌管理**页面。

您可以在这个环节完成下列配置：

* 查看令牌元数据：名称、类型、限制、创建/有效期
* 单独删除令牌
* 监控审计日志中的令牌活动

<div id="note-1" />

> 📘 **注意**
>
> 标记不可编辑。更改访问权限、删除和重新创建令牌。

</Accordion>

<div id="audit-log-api-and-extended-retention" />

<Accordion title="审计日志 API 和扩展保留">

该功能增强了现有的审计日志功能，引入了用于审计日志消耗的 API，并将数据保留时间从 90 天延长至 180 天。对于需要长期访问用户操作日志或将审计事件集成到SOC 和 SEIM 等外部监控工具中的团队来说，它是理想之选。

<div id="key-features-1" />

#### 主要功能

* 使用专用 API 以编程方式访问审计日志
* 保留日志长达**180 天**，而标准审计日志仅保留 90 天
* 为合规、安全或操作用途过滤和导出数据
* 使用特定于服务的令牌来隔离日志访问
* 将数据导出到 SIEM 工具、仪表板或云存储中

<div id="note-2" />

> 📘 **注意**
>
> 有关标准审计日志的一般信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/audit-log">标准审计日志</Anchor>。

<div id="how-to-access-the-audit-log-via-api" />

### **如何通过 API 访问审计日志**

要使用审计日志 API：

1. 从页面顶部导航栏打开账户菜单（点击右上角的邮箱地址，打开下拉菜单）> 通知。 安全中心
2. 在**审计日志**部分，单击**查看审计日志。**
3. 进入**令牌管理**页面。
4. 使用现有的**API 令牌**或创建新的**API 令牌**。
5. 在**访问限制**下，选择**审计日志**服务。
6. 使用令牌验证对审计日志 API 端点的请求。

<div id="note-3" />

> 📘 **注意**
>
> 确保安全存储 API 令牌。创建后无法检索

</Accordion>

<div id="accordion-item" />

<Accordion title="SSO 和 SCIM 配置">

SCIM 配置通过直接从身份提供商 (IdP)（如 Okta、Entra ID (Azure)、OneLogin、JumpCloud 或支持基于属性访问的自我管理 IDP）自动进行用户生命周期管理，增强了 AppsFlyer SSO 功能。这样，企业就可以在无需人工干预的情况下启用、更新或停用用户。

通过 SCIM 同步用户，您可以实时全面控制访问权限。与 SAML 2.0 SSO 相结合，可为企业客户提供完整的身份和访问管理解决方案。

<div id="key-features-2" />

#### **主要功能**

* 根据身份提供商（IdP）记录在 AppsFlyer 中自动创建用户。
* 用户角色或 IdP 状态的变化会立即反映在 AppsFlyer 中。
* 使用**SAML 2.0**进行安全 SSO，使用**SCIM**进行配置，与 Okta 和 Azure AD 等领先的 IdP 兼容。

<div id="how-to-set-up-scim-provisioning" />

#### **如何设置 SCIM 配置**

要开始在 AppsFlyer 中使用 SCIM 配置，您需要

1. [设置 SSO](/docs/enterprise-grade-security-package#sso-设置)
2. [启用 SCIM](/docs/enterprise-grade-security-package#启用-scim)

<div id="sso-set-up" />

#### SSO 设置

要设置 SSO，您需要

* <Anchor target="_blank" href="/marketers/zh/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-1-set-up-the-idp-platform">建立 IDP 平台</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-set-up-appsflyer">在 AppsFlyer 中设置 SSO</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-configuration">测试 SSO 配置</Anchor>

<div id="enable-scim" />

#### 启用 SCIM

<div id="note-4" />

> 📘 **注意**
>
> 要启用 SCIM，必须先设置 SSO

要启用 SCIM，必须遵循几个步骤：

* 按照 [idP 配置说明](/docs/enterprise-grade-security-package#idp-指令链接)操作
* 配置[SCIM 连接](/docs/enterprise-grade-security-package#scim-连接)
* 添加[SCIM 属性](/docs/enterprise-grade-security-package#scim-属性)
* 添加[角色](/docs/enterprise-grade-security-package#角色)
* 添加[外部命名空间](/docs/enterprise-grade-security-package#external-namespace)

<div id="idp-instruction-links" />

#### IdP 指令链接

<div id="the-instructions-for-the-idps-can-be-found-below-okta-entra-id-azure-onelogin-jumpcloud" />

##### IDP 的使用说明如下。<Anchor target="_blank" href="https://help.okta.com/en-us/content/topics/apps/apps_app_integration_wizard_scim.htm">Okta</Anchor>, <Anchor target="_blank" href="https://learn.microsoft.com/en-us/entra/identity/app-provisioning/use-scim-to-provision-users-and-groups#integrate-your-scim-endpoint-with-the-microsoft-entra-provisioning-service">Entra ID (Azure)</Anchor>, <Anchor target="_blank" href="https://onelogin.service-now.com/kb_view_customer.do?sysparm_article=KB0010298">OneLogin</Anchor>, <Anchor target="_blank" href="https://jumpcloud.com/support/get-started-identity-management-connectors">跳云</Anchor>

<div id="scim-connections" />

#### SCIM 连接

在 SCIM 连接中，必须填写以下字段：

| **字段名称** | **参数值** |
| --- | --- |
| SCIM 连接器基本 URL（SCIM 端点） | https://hq1.appsflyer.com/api/scim/v2 |
| 用户唯一标识符字段 | userName |
| 验证方法：名为 "授权 "的 HTTP 标头 | 承载器 &lt;<Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">您的 AppsFlyer API 标记</Anchor>> |

<div id="scim-attributes" />

#### SCIM 属性

| **属性** | **类型** | **必须配置** | **字段名称** | **外部命名空间** | **说明** |
| --- | --- | --- | --- | --- | --- |
| 角色 | 字符串 | ✅ | 角色 | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | <ul><li>为用户分配预定义或自定义角色。</li><li>请参阅以下必须输入的 AppsFlyer 角色列表</li></ul> |
| 开放所有后续应用的权限 | Boolean | ❌ | allowAccessToAllFutureApps | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | 如果启用，用户将自动获准访问新应用程序。 |
| 允许的应用程序 ID | 字符串 | ❌ | appIDs | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | 以逗号分隔的应用程序 ID 列表。所有应用程序留空，无应用程序则设置为 "无"。 |

<div id="roles" />

#### 角色

角色必须与 <Anchor target="_blank" href="/marketers/zh/docs/user-management#roles-tab">AppsFlyer 角色</Anchor>.下表显示了当前的 AppsFlyer 角色及其值。可添加自定义角色。关于 JumpCloud，请参阅以下[限制](/docs/enterprise-grade-security-package#局限性)。

| **字段名称** | **参数值** |
| --- | --- |
| 管理员 | 管理员 |
| 团队经理 | team\_manager |
| 营销负责人 | marketing\_lead |
| 营销 | 营销 |
| 市场——部分权限 | 市场——部分权限 |
| 协作方 | 开发者 |
| 财务 | 财务 |
| 数据安全 | 安全 |
| 质量保证 | 质量保证 |
| 自定义角色 | [输入自定义角色值］ |

<div id="limitations" />

#### 局限性

| **局限性** | **说明** |
| --- | --- |
| **JumpCloud - 自定义属性** | <Anchor target="_blank" href="https://jumpcloud.com/support/provision-and-manage-users-and-groups-in-apps-using-custom-scim-identity-management-integration#attribute-considerations">不支持自定义属性</Anchor>。作为一种变通方法，将角色字段映射到支持的字段 "工作街道地址"。查看 <Anchor target="_blank" href="https://jumpcloud.com/support/provision-and-manage-users-and-groups-in-apps-using-custom-scim-identity-management-integration#custom-scim-user-attributes">JumpCloud SCIM 支持</Anchor>. |

</Accordion>

<div id="ip-allowlist" />

<Accordion title="IP 白名单">

增强的 IP 允许列表功能可防止未经授权的访问，确保只有受信任的网络才能与平台互动，从而提高安全性。这一功能对于执行严格的安全策略或管理远程访问的企业尤为重要。

<div id="frequently-asked-questions-about-our-security-package" />

<div id="how-quickly-can-i-implement-these-security-controls" />

<div id="does-this-replace-standard-security-features" />

<div id="how-long-are-audit-logs-retained" />

<div id="what-network-restrictions-can-i-apply" />

<div id="can-i-integrate-with-my-existing-security-tools" />

<div id="how-many-roles-and-api-tokens-can-i-create" />

<div id="what-compliance-standards-does-this-support" />

<div id="how-does-scim-provisioning-work" />

<div id="who-is-the-enterprise-grade-security-package-designed-for" />

<div id="what-is-appsflyers-enterprise-grade-security-package" />

<div id="removing-ips-from-the-list" />

<div id="important" />

<div id="adding-ips-to-the-list" />

<div id="key-features-3" />

#### 主要功能

* 通过阻止来自未知 IP 的登录尝试来减少攻击。
* 启用指定 IP 地址或范围的功能，以确保只有授权用户和网络才能访问平台。
* 是使用 VPN 或需要更严格访问控制的组织的理想选择。

</Accordion>

<div data-zendesk-anchors="intro=%E5%BC%95%E8%A8%80 h_01JRA2GVNZCDW8C9VW6GH3G4KE=%E5%BC%95%E8%A8%80 compare-the-standard-and-advanced-packages=%E6%AF%94%E8%BE%83%E6%A0%87%E5%87%86%E5%A5%97%E9%A4%90%E5%92%8C%E9%AB%98%E7%BA%A7%E5%A5%97%E9%A4%90 h_01JVS101KETCVDMT1B2WZM89NF=%E6%AF%94%E8%BE%83%E6%A0%87%E5%87%86%E5%A5%97%E9%A4%90%E5%92%8C%E9%AB%98%E7%BA%A7%E5%A5%97%E9%A4%90 h_01JQXQ178D9JKZEREHWTQ2FKBF=multitoken-management-with-restrictions key-features=%E4%B8%BB%E8%A6%81%E5%8A%9F%E8%83%BD h_01JQXRDEMJF2NT73FP1TFJG63Z=%E4%B8%BB%E8%A6%81%E5%8A%9F%E8%83%BD h_01JVRZRXPD4AC1GAMJ2HKC1R9E=%E7%A4%BA%E4%BE%8B h_01JVRZ0ACA19TGC9WJCZ562B70=%E6%B3%A8%E6%84%8F how-to-access-and-control-tokens=%E5%A6%82%E4%BD%95%E8%AE%BF%E9%97%AE%E5%92%8C%E6%8E%A7%E5%88%B6%E4%BB%A4%E7%89%8C h_01JQXSE4TTYXTWCKXDHB20KJ1Z=%E5%A6%82%E4%BD%95%E8%AE%BF%E9%97%AE%E5%92%8C%E6%8E%A7%E5%88%B6%E4%BB%A4%E7%89%8C h_01JVRZ9X0D5V765FTXHVHMR807=%E6%B3%A8%E6%84%8F-1 h_01JQXQ178DHFQ2Y6JDYYBTKJ0V=audit-log-api-and-extended-retention key-features::8c048755=%E4%B8%BB%E8%A6%81%E5%8A%9F%E8%83%BD-1 h_01JQXR4X1CT8P8M3NYEVK0WQYM=%E4%B8%BB%E8%A6%81%E5%8A%9F%E8%83%BD-1 h_01JVRZ7WBBY3D8GJE2MJ2E4B0G=%E6%B3%A8%E6%84%8F-2 how-to-access-the-audit-log-via-api=%E5%A6%82%E4%BD%95%E9%80%9A%E8%BF%87-api-%E8%AE%BF%E9%97%AE%E5%AE%A1%E8%AE%A1%E6%97%A5%E5%BF%97 h_01JQXQM2H3VCJMWFRBJDWJ5FAZ=%E5%A6%82%E4%BD%95%E9%80%9A%E8%BF%87-api-%E8%AE%BF%E9%97%AE%E5%AE%A1%E8%AE%A1%E6%97%A5%E5%BF%97 h_01JVRZ69C2JYY9SK12SEVG3KXF=%E6%B3%A8%E6%84%8F-3 h_01JQXQ178DSG340QG8R05B8VNX=accordion-item key-features::e7dd8b4e=%E4%B8%BB%E8%A6%81%E5%8A%9F%E8%83%BD-2 h_01JV9W8DTENC21GS0380Q9DP8T=%E4%B8%BB%E8%A6%81%E5%8A%9F%E8%83%BD-2 how-to-set-up-scim-provisioning=%E5%A6%82%E4%BD%95%E8%AE%BE%E7%BD%AE-scim-%E9%85%8D%E7%BD%AE h_01JV9W8DTFCE7Z0MQP96MK7BQC=%E5%A6%82%E4%BD%95%E8%AE%BE%E7%BD%AE-scim-%E9%85%8D%E7%BD%AE sso-set-up=sso-%E8%AE%BE%E7%BD%AE h_01JV9W8DTFHJME1J1JKKJ3NA6C=sso-%E8%AE%BE%E7%BD%AE enable-scim=%E5%90%AF%E7%94%A8-scim h_01JV9W8DTG50YYPQ9RS91K2CJ4=%E5%90%AF%E7%94%A8-scim h_01JVRZ3MC8J0B1E66A47GM5WYZ=%E6%B3%A8%E6%84%8F-4 idp-instruction-links=idp-%E6%8C%87%E4%BB%A4%E9%93%BE%E6%8E%A5 h_01JV9WBJCPQ0X5SKVVNK4TBYRR=idp-%E6%8C%87%E4%BB%A4%E9%93%BE%E6%8E%A5 h_01JV9WTJ33KMJGZGM9P5PRK917=idp-%E7%9A%84%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E%E5%A6%82%E4%B8%8Bokta-entra-id-azure-onelogin-%E8%B7%B3%E4%BA%91 scim-connections=scim-%E8%BF%9E%E6%8E%A5 h_01JV9WBNC51WYW03RKWHBTP0AG=scim-%E8%BF%9E%E6%8E%A5 scim-attributes=scim-%E5%B1%9E%E6%80%A7 h_01JV9WBS928Z7WKJ2A2CFSWNT4=scim-%E5%B1%9E%E6%80%A7 roles=%E8%A7%92%E8%89%B2 h_01JV9WBX3JHEMAG62JCASYXB59=%E8%A7%92%E8%89%B2 limitations=%E5%B1%80%E9%99%90%E6%80%A7 h_01JV9DMY0Y3795TAT3Q1E3PZRM=%E5%B1%80%E9%99%90%E6%80%A7 h_01JVWCNK70QY6PKJRFZGEQ76SW=ip-allowlist key-features::cd0daf96=%E4%B8%BB%E8%A6%81%E5%8A%9F%E8%83%BD-3 h_01JVWCSA3D6DJZXJKKYDFWWPC0=%E4%B8%BB%E8%A6%81%E5%8A%9F%E8%83%BD-3" />
