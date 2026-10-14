---
title: "Enterprise-Grade Security Package"
excerpt: "Enhance your account protection with the Enterprise-Grade Security Package, a premium offering designed for enterprise-grade identity management, token access control, and extended audit visibility."
x-zendesk:
  id: 34053592094737
  url: https://support.appsflyer.com/hc/en-us/articles/34053592094737-Enterprise-Grade-Security-Package
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Account security
  section_id: 6551173202065
  position: 0
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-negri, Marketers, Platform essentials]
  labels: [Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2025-04-03T11:42:43Z'
  edited_at: '2026-04-26T06:35:42Z'
---
## Intro

The Enterprise-Grade Security Package brings together three key features that elevate your organization’s security:

* **Multi-token management with service restrictions**: Scalable token creation and granular access controls across APIs, S2S, and OneLink.
* **Audit log API with extended retention**: Gain long-term visibility into platform activity and integrate audit events into your monitoring stack.
* **SCIM provisioning**: Automate and centralize user access control via your identity provider.
* **IP allowlist for Login:** Prevent unauthorized access, ensuring log in to the AppsFlyer dashboard from only trusted networks and IPs

### Compare the standard and Enterprise-Grade packages:

| Feature | Standard package | Enterprise-Grade Security Package |
| --- | --- | --- |
| [Single sign on (SSO)](/docs/enterprise-grade-security-package#accordion-item) | SSO login (existing customers only) | SSO SAML 2.0 with SCIM provisioning for automated user and role management |
| [Token management](/docs/enterprise-grade-security-package#multitoken-management-with-restrictions) | Manage up to 2 tokens per type (API, S2S, or OneLink) | Manage multiple tokens per type (up to 30) with granular permissions |
| [Audit log access](/docs/enterprise-grade-security-package#audit-log-api-and-extended-retention) | UI access only, 90 day retention data | UI and API access, 180-day data retention |
| [User management based on roles (RBAC)](/docs/enterprise-grade-security-package#multitoken-management-with-restrictions) | Up to 10 custom roles | Up to 50 custom roles |
| [IP allowlist](/docs/enterprise-grade-security-package#ip-allowlist) | IP Allow list for APIs | IP allowlist for Login and APIs for enhanced security |
| 24/7 security monitoring | Included | Included |
| Multi-factor authentication | Included | Included |

<div id="multitoken-management-with-restrictions" />

<Accordion title="Multi-Token Management with Restrictions">

Create and manage up to **30 tokens** per type (API, S2S, OneLink) with **service-level restrictions** to enhance scalability, security, and control over tokens.

#### Key features

* Admins can create up to **30 tokens per type**, compared to the 2 tokens with the standard tokens, supporting larger teams and complex workflows.​
* Assign service-specific access permissions to API tokens, restricting access to sensitive operations.​
* Tokens can be revoked or rotated without breaking integrations or automations.
* Restrict a token to a specific app so the token can only access data or perform actions for that app.
* Simplifies collaboration with internal teams and external partners through token-specific permissions.

> 📘 **Example**
>
> Create two tokens to help maintain least-privilege access and prevent accidental data exposure.
>
> **Data only access token:** Create a token that accesses aggregated data only. This token won’t be able to access raw data or perform actions like configuration changes. Use this for analytics teams or read-only agency users.
>
> **Settings-only access token:** Issue a token that lets internal teams manage configuration settings but doesn’t allow them to pull data. This isolates admin capabilities from data access.
>
> **App-specific access token:** Create a token that works for one app only. Use this token when an internal team, external partner, or automation must access only a specific app.

> 📘 **Note**
>
> For general information about standard tokens, see [managing AppsFlyer tokens](/docs/managing-appsflyer-tokens).

#### How to access and control tokens

**To create a restricted token**

1. From the top bar, open the account menu (email address dropdown) -> **Security Center.**
2. Go to the **Token Management** page.
3. Click **Create Token**.
4. Select the token type:
   * API
   * S2S
   * OneLink
5. For **API tokens**, select one or more services from the **Access restriction** dropdown.  
   Access is binary: full access or none.
6. Select the restriction type:
   1. Service restriction: Select one or more services from the **Access restriction** drop-down list.
   2. App restriction: Select the app that the token can access.
7. Click **Save**

**Manage tokens**

To manage your tokens, from the top bar, open the account menu (email address dropdown) -> **Security center -> Token Management** page.

Here you can:

* View token metadata: name, type, restrictions, creation/expiration
* Delete tokens individually
* Monitor token activity in audit logs

> 📘 **Note**
>
> Tokens cannot be edited. To change access, delete, and recreate a token.

</Accordion>

<div id="audit-log-api-and-extended-retention" />

<Accordion title="Audit log API and extended retention">

Enhancing the existing audit log capabilities, this feature introduces an API for audit log consumption and extends data retention from 90 days to 180 days. Ideal for teams needing long-term access to user action logs or integrating audit events into external monitoring tools like SOC and SEIM.

#### Key features

* Access audit logs programmatically using a dedicated API
* Retain logs for up to **180 days**, compared to 90 days with the standard audit logs
* Filter and export data for compliance, security, or operational use
* Use service-specific tokens to isolate log access
* Export data to SIEM tools, dashboards, or cloud storage

> 📘 **Note**
>
> For general information about the standard audit log, see [Standard audit log](/docs/audit-log).

### **How to access the audit log via API**

To use the Audit Log API:

1. From the top bar, open the account menu (email address dropdown): **Security Center.**
2. In the **Audit log** section, click **View audit log.**
3. Go to the **Token Management** page.
4. Use an existing or create a new **API token**.
5. Under **Access restriction**, select **Audit log** service.
6. Use the token to authenticate requests to the audit log API endpoint.

> 📘 **Note**
>
> Make sure to store your API token securely. It can’t be retrieved after creation.

</Accordion>

<div id="accordion-item" />

<Accordion title="SSO and SCIM provisioning">

SCIM provisioning enhances AppsFlyer SSO capabilities by automating user lifecycle management directly from your identity provider (IdP), such as Okta, Entra ID (Azure), OneLogin, JumpCloud, or self-managed IDPs supporting attribute-based access. This allows organizations to onboard, update, or deactivate users without manual intervention.

By syncing users via SCIM, you maintain full control over access permissions in real-time. Combined with SAML 2.0 SSO, this forms a complete identity and access management solution for enterprise customers.

#### **Key features**

* Automatically create users in AppsFlyer based on identity provider (IdP) records.
* Changes in user roles or status in the IdP are instantly reflected in AppsFlyer.
* Uses **SAML 2.0** for secure SSO and **SCIM** for provisioning—compatible with leading IdPs like Okta and Azure AD.

#### **How to set up SCIM provisioning**

To start using SCIM provisioning in AppsFlyer, you need to:

1. [Set up SSO](/docs/enterprise-grade-security-package#sso-set-up)
2. [Enable SCIM](/docs/enterprise-grade-security-package#enable-scim)

#### SSO set up

To set up SSO, you need to:

* [Set up the IdP platform](/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-1-set-up-the-idp-platform)
* [Set up SSO in AppsFlyer](/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-set-up-appsflyer)
* [Test the SSO configuration](/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-configuration)

#### Enable SCIM

> 📘 **Note**
>
> To enable SCIM, SSO must be set up first.

To enable SCIM, there are a few steps that must be followed:

* Follow the [idP configuration instructions](/docs/enterprise-grade-security-package#idp-instruction-links)
* Configure the [SCIM connections](/docs/enterprise-grade-security-package#scim-connections)
* Add the [SCIM Attributes](/docs/enterprise-grade-security-package#scim-attributes)
* Add [roles](/docs/enterprise-grade-security-package#roles)
* Add [external namespace](/docs/enterprise-grade-security-package#external-namespace)

#### IdP instruction links

##### The instructions for the IdPs can be found below. [Okta](https://help.okta.com/en-us/content/topics/apps/apps_app_integration_wizard_scim.htm), [Entra ID (Azure)](https://learn.microsoft.com/en-us/entra/identity/app-provisioning/use-scim-to-provision-users-and-groups#integrate-your-scim-endpoint-with-the-microsoft-entra-provisioning-service), [OneLogin](https://onelogin.service-now.com/kb_view_customer.do?sysparm_article=KB0010298), [JumpCloud](https://jumpcloud.com/support/get-started-identity-management-connectors)

#### SCIM connections

In the SCIM connections, the following fields must be filled in:

| **Field name** | **Value** |
| --- | --- |
| SCIM connector base URL (SCIM endpoint) | https://hq1.appsflyer.com/api/scim/v2 |
| Unique identifier field for users | userName |
| Authentication method: HTTP header called "Authorization" | Bearer &lt;[Your AppsFlyer API token](/docs/managing-appsflyer-tokens)> |

#### SCIM attributes

| **Attribute** | **Type** | **Required** | **Field name** | **External namespace** | **Description** |
| --- | --- | --- | --- | --- | --- |
| Role | String | ✅ | role | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | <ul><li>Assign a predefined or custom role to the user.</li><li>See below for the list of AppsFlyer roles that must be entered</li></ul> |
| Allow access to all future apps | Boolean | ❌ | allowAccessToAllFutureApps | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | If enabled, the user will be granted access to new apps automatically. |
| Allowed App IDs | String | ❌ | appIDs | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | Comma-separated list of app IDs. Leave empty for all apps or set to "None" for no apps. |

#### Roles

The roles must match the [AppsFlyer roles](/docs/user-management#roles-tab). The table below shows the current AppsFlyer roles and their values. Custom roles can be added. For JumpCloud, see the [limitations](/docs/enterprise-grade-security-package#limitations) below.

| **Display name** | **Value** |
| --- | --- |
| Admin | admin |
| Team manager | team\_manager |
| Marketing lead | marketing\_lead |
| Marketing | marketing |
| Marketing-limited | marketing\_limited |
| Contributor | developer |
| Accounting | accounting |
| Security | security |
| Quality Assurance | quality\_assurance |
| Custom Role | [enter custom role value] |

#### Limitations

| **Limitation** | **Description** |
| --- | --- |
| **JumpCloud - custom atttributes** | [Custom attributes aren’t supported](https://jumpcloud.com/support/provision-and-manage-users-and-groups-in-apps-using-custom-scim-identity-management-integration#attribute-considerations). As a workaround, map the Role field to the supported field Work Street Address. See [JumpCloud SCIM support](https://jumpcloud.com/support/provision-and-manage-users-and-groups-in-apps-using-custom-scim-identity-management-integration#custom-scim-user-attributes). |

</Accordion>

<div id="ip-allowlist" />

<Accordion title="IP allowlist for Login">

Enhanced IP allowlisting improves security by preventing unauthorized access, ensuring only trusted networks can interact with the platform. This feature is especially valuable for enterprises enforcing strict security policies or managing remote access.

#### Key features

* Reduces attacks by blocking login attempts from unknown IPs.
* Enables the ability to specify IP addresses or ranges to ensure that only authorized users and networks can access the platform.
* Ideal for organizations using VPNs or requiring stricter access controls.

#### Adding IPs to the list

1. From the top bar, open the account menu (email address dropdown) > **Security center**.
2. In the **Login IP allowlist** section, click **Manage IP allowlist**.
3. Add IPs manually or via a CSV upload.
   1. If adding manually, enter the IP address or CIDR range and click **Add IP to list**.
      1. Examples: `192.168.1.1`, `185.114.120.140`
      2. To enter a range of IP addresses, use this format: `185.114.120.1/32`  
         (where `185.114.120.1` is the first address in the range and `185.114.120.32` is the last address in the range).
4. Added IPs will be shown on the right side under **See your IPs in the IP allowlist**.
5. Click **Save list**.

> 📘 **Important!**
>
> * Make sure the IP addresses or ranges you add are correct. Incorrect entries may prevent you from accessing your account.
> * The allowlist must contain at least one IP address or range before you can save and activate it, and you can add up to 100 IP addresses or ranges to the allowlist.
> * After you click Save list, the IP restrictions will be enforced starting with your next log in.

#### Removing IPs from the list

1. From the top bar, open the account menu (email address dropdown) > **Security center**.
2. In the **Login IP allowlist** section, click **Manage IP allowlist**.
3. Added IPs will be shown on the right side under **See your IPs in the IP allowlist**.
4. Click the trash icon next to the IP address you want to delete.
5. Be sure to save your changes by clicking the **Save list** button.

</Accordion>

<Accordion title="Frequently asked questions about our security package">

#### What is AppsFlyer's Enterprise-Grade Security Package?

Scale securely with advanced security capabilities that go beyond standard protections. Get SSO with SCIM provisioning, granular access controls, extended audit logs, and compliance tools designed for enterprise security and IT leaders.

#### Who is the Enterprise-Grade Security Package designed for?

Enterprise security and IT leaders preparing for audits, procurement and legal teams in regulated industries evaluating SaaS vendors, and platform admins managing complex access requirements across multiple teams and integrations.

#### How does SCIM provisioning work?

Automate user lifecycle management by connecting directly with your identity provider. SCIM automatically syncs user access and roles, handles instant onboarding and offboarding, and eliminates manual account management and orphaned access risks.

#### What compliance standards does this support?

Support audit readiness for SOC2, ISO 27001, and GDPR requirements with 180-day audit log retention, comprehensive access documentation, and real-time SIEM integration for continuous monitoring and compliance verification.

#### How many roles and API tokens can I create?

Create up to 50 customizable roles tailored to your organizational structure and up to 30 service-specific or app-specific restrictions. Isolate access for different integrations and job functions while maintaining least-privilege principles.

#### Can I integrate with my existing security tools?

Yes. Stream audit data directly to your SIEM and security tools through API-based log streaming. Enable real-time monitoring, anomaly detection, and automated security responses within your existing SOC infrastructure.

#### What network restrictions can I apply?

Control platform access through IP allowlists and geographic restrictions. Define trusted networks and locations to prevent unauthorized access while supporting remote work scenarios and secure partner collaboration.

#### How long are audit logs retained?

Access comprehensive audit trails with 180-day log retention that captures every platform interaction. Get complete visibility into user actions, API calls, and access patterns for thorough compliance documentation and security investigations.

#### Does this replace standard security features?

No. The Enterprise-Grade Security Package adds advanced capabilities on top of standard security features. You get enhanced controls, automation, and visibility while maintaining all existing security protections.

#### How quickly can I implement these security controls?

Deploy enterprise security controls rapidly through seamless SSO integration and automated SCIM provisioning. Most organizations can implement core features within days while maintaining operational continuity and user productivity.

</Accordion>
