---
title: Enterprise-Grade Security Package
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
  edited_at: '2026-10-14T07:44:39Z'
  id: 34053592094737
  locale: en-us
  section: Account security
  section_id: 6551173202065
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/34053592094737-Enterprise-Grade-Security-Package
---
> **At a glance:** Enhance your account protection with the **Enterprise-Grade Security Package,** a premium offering designed for enterprise-grade identity management, token access control, and extended audit visibility.

<div id="intro" />

## Intro

The Enterprise-Grade Security Package brings together three key features that elevate your organization’s security:

* **Multi-token management with service restrictions**: Scalable token creation and granular access controls across APIs, S2S, and OneLink.
* **Audit log API with extended retention**: Gain long-term visibility into platform activity and integrate audit events into your monitoring stack.
* **SCIM provisioning**: Automate and centralize user access control via your identity provider.
* **IP allowlist for Login:** Prevent unauthorized access, ensuring log in to the AppsFlyer dashboard from only trusted networks and IPs

<div id="compare-the-standard-and-enterprise-grade-packages" />

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

<div id="key-features" />

#### Key features

* Admins can create up to **30 tokens per type**, compared to the 2 tokens with the standard tokens, supporting larger teams and complex workflows.​
* Assign service-specific access permissions to API tokens, restricting access to sensitive operations.​
* Tokens can be revoked or rotated without breaking integrations or automations.
* Restrict a token to a specific app so the token can only access data or perform actions for that app.
* Simplifies collaboration with internal teams and external partners through token-specific permissions.

<div id="example" />

> 📄 **Example**
>
> Create two tokens to help maintain least-privilege access and prevent accidental data exposure.
>
> **Data only access token:** Create a token that accesses aggregated data only. This token won’t be able to access raw data or perform actions like configuration changes. Use this for analytics teams or read-only agency users.
>
> **Settings-only access token:** Issue a token that lets internal teams manage configuration settings but doesn’t allow them to pull data. This isolates admin capabilities from data access.
>
> **App-specific access token:** Create a token that works for one app only. Use this token when an internal team, external partner, or automation must access only a specific app.

<div id="note" />

> 📘 **Note**
>
> For general information about standard tokens, see <Anchor target="_blank" href="/marketers/docs/managing-appsflyer-tokens">managing AppsFlyer tokens</Anchor>.

<div id="how-to-access-and-control-tokens" />

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

<div id="note-1" />

> 📘 **Note**
>
> Tokens cannot be edited. To change access, delete, and recreate a token.

</Accordion>

<div id="audit-log-api-and-extended-retention" />

<Accordion title="Audit log API and extended retention">

Enhancing the existing audit log capabilities, this feature introduces an API for audit log consumption and extends data retention from 90 days to 180 days. Ideal for teams needing long-term access to user action logs or integrating audit events into external monitoring tools like SOC and SEIM.

<div id="key-features-1" />

#### Key features

* Access audit logs programmatically using a dedicated API
* Retain logs for up to **180 days**, compared to 90 days with the standard audit logs
* Filter and export data for compliance, security, or operational use
* Use service-specific tokens to isolate log access
* Export data to SIEM tools, dashboards, or cloud storage

<div id="note-2" />

> 📘 **Note**
>
> For general information about the standard audit log, see <Anchor target="_blank" href="/marketers/docs/audit-log">Standard audit log</Anchor>.

<div id="how-to-access-the-audit-log-via-api" />

### **How to access the audit log via API**

To use the Audit Log API:

1. From the top bar, open the account menu (email address dropdown): **Security Center.**
2. In the **Audit log** section, click **View audit log.**
3. Go to the **Token Management** page.
4. Use an existing or create a new **API token**.
5. Under **Access restriction**, select **Audit log** service.
6. Use the token to authenticate requests to the audit log API endpoint.

<div id="note-3" />

> 📘 **Note**
>
> Make sure to store your API token securely. It can’t be retrieved after creation.

</Accordion>

<div id="accordion-item" />

<Accordion title="SSO and SCIM provisioning">

SCIM provisioning enhances AppsFlyer SSO capabilities by automating user lifecycle management directly from your identity provider (IdP), such as Okta, Entra ID (Azure), OneLogin, JumpCloud, or self-managed IDPs supporting attribute-based access. This allows organizations to onboard, update, or deactivate users without manual intervention.

By syncing users via SCIM, you maintain full control over access permissions in real-time. Combined with SAML 2.0 SSO, this forms a complete identity and access management solution for enterprise customers.

<div id="key-features-2" />

#### **Key features**

* Automatically create users in AppsFlyer based on identity provider (IdP) records.
* Changes in user roles or status in the IdP are instantly reflected in AppsFlyer.
* Uses **SAML 2.0** for secure SSO and **SCIM** for provisioning—compatible with leading IdPs like Okta and Azure AD.

<div id="how-to-set-up-scim-provisioning" />

#### **How to set up SCIM provisioning**

To start using SCIM provisioning in AppsFlyer, you need to:

1. [Set up SSO](/docs/enterprise-grade-security-package#sso-set-up)
2. [Enable SCIM](/docs/enterprise-grade-security-package#enable-scim)

<div id="sso-set-up" />

#### SSO set up

To set up SSO, you need to:

* <Anchor target="_blank" href="/marketers/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-1-set-up-the-idp-platform">Set up the IdP platform</Anchor>
* <Anchor target="_blank" href="/marketers/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-set-up-appsflyer">Set up SSO in AppsFlyer</Anchor>
* <Anchor target="_blank" href="/marketers/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-configuration">Test the SSO configuration</Anchor>

<div id="enable-scim" />

#### Enable SCIM

<div id="note-4" />

> 📘 **Note**
>
> To enable SCIM, SSO must be set up first.

To enable SCIM, there are a few steps that must be followed:

* Follow the [idP configuration instructions](/docs/enterprise-grade-security-package#idp-instruction-links)
* Configure the [SCIM connections](/docs/enterprise-grade-security-package#scim-connections)
* Add the [SCIM Attributes](/docs/enterprise-grade-security-package#scim-attributes)
* Add [roles](/docs/enterprise-grade-security-package#roles)
* Add [external namespace](/docs/enterprise-grade-security-package#external-namespace)

<div id="idp-instruction-links" />

#### IdP instruction links

<div id="the-instructions-for-the-idps-can-be-found-below-okta-entra-id-azure-onelogin-jumpcloud" />

##### The instructions for the IdPs can be found below. <Anchor target="_blank" href="https://help.okta.com/en-us/content/topics/apps/apps_app_integration_wizard_scim.htm">Okta</Anchor>, <Anchor target="_blank" href="https://learn.microsoft.com/en-us/entra/identity/app-provisioning/use-scim-to-provision-users-and-groups#integrate-your-scim-endpoint-with-the-microsoft-entra-provisioning-service">Entra ID (Azure)</Anchor>, <Anchor target="_blank" href="https://onelogin.service-now.com/kb_view_customer.do?sysparm_article=KB0010298">OneLogin</Anchor>, <Anchor target="_blank" href="https://jumpcloud.com/support/get-started-identity-management-connectors">JumpCloud</Anchor>

<div id="scim-connections" />

#### SCIM connections

In the SCIM connections, the following fields must be filled in:

| **Field name** | **Value** |
| --- | --- |
| SCIM connector base URL (SCIM endpoint) | https://hq1.appsflyer.com/api/scim/v2 |
| Unique identifier field for users | userName |
| Authentication method: HTTP header called "Authorization" | Bearer &lt;<Anchor target="_blank" href="/marketers/docs/managing-appsflyer-tokens">Your AppsFlyer API token</Anchor>> |

<div id="scim-attributes" />

#### SCIM attributes

| **Attribute** | **Type** | **Required** | **Field name** | **External namespace** | **Description** |
| --- | --- | --- | --- | --- | --- |
| Role | String | ✅ | role | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | <ul><li>Assign a predefined or custom role to the user.</li><li>See below for the list of AppsFlyer roles that must be entered</li></ul> |
| Allow access to all future apps | Boolean | ❌ | allowAccessToAllFutureApps | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | If enabled, the user will be granted access to new apps automatically. |
| Allowed App IDs | String | ❌ | appIDs | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | Comma-separated list of app IDs. Leave empty for all apps or set to "None" for no apps. |

<div id="roles" />

#### Roles

The roles must match the <Anchor target="_blank" href="/marketers/docs/user-management#roles-tab">AppsFlyer roles</Anchor>. The table below shows the current AppsFlyer roles and their values. Custom roles can be added. For JumpCloud, see the [limitations](/docs/enterprise-grade-security-package#limitations) below.

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

<div id="limitations" />

#### Limitations

| **Limitation** | **Description** |
| --- | --- |
| **JumpCloud - custom atttributes** | <Anchor target="_blank" href="https://jumpcloud.com/support/provision-and-manage-users-and-groups-in-apps-using-custom-scim-identity-management-integration#attribute-considerations">Custom attributes aren’t supported</Anchor>. As a workaround, map the Role field to the supported field Work Street Address. See <Anchor target="_blank" href="https://jumpcloud.com/support/provision-and-manage-users-and-groups-in-apps-using-custom-scim-identity-management-integration#custom-scim-user-attributes">JumpCloud SCIM support</Anchor>. |

</Accordion>

<div id="ip-allowlist" />

<Accordion title="IP allowlist for Login">

Enhanced IP allowlisting improves security by preventing unauthorized access, ensuring only trusted networks can interact with the platform. This feature is especially valuable for enterprises enforcing strict security policies or managing remote access.

<div id="key-features-3" />

#### Key features

* Reduces attacks by blocking login attempts from unknown IPs.
* Enables the ability to specify IP addresses or ranges to ensure that only authorized users and networks can access the platform.
* Ideal for organizations using VPNs or requiring stricter access controls.

<div id="adding-ips-to-the-list" />

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

<div id="important" />

> 🚧 **Important!**
>
> * Make sure the IP addresses or ranges you add are correct. Incorrect entries may prevent you from accessing your account.
> * The allowlist must contain at least one IP address or range before you can save and activate it, and you can add up to 100 IP addresses or ranges to the allowlist.
> * After you click Save list, the IP restrictions will be enforced starting with your next log in.

<div id="removing-ips-from-the-list" />

#### Removing IPs from the list

1. From the top bar, open the account menu (email address dropdown) > **Security center**.
2. In the **Login IP allowlist** section, click **Manage IP allowlist**.
3. Added IPs will be shown on the right side under **See your IPs in the IP allowlist**.
4. Click the trash icon next to the IP address you want to delete.
5. Be sure to save your changes by clicking the **Save list** button.

</Accordion>

<div id="frequently-asked-questions-about-our-security-package" />

<Accordion title="Frequently asked questions about our security package">

<div id="what-is-appsflyers-enterprise-grade-security-package" />

#### What is AppsFlyer's Enterprise-Grade Security Package?

Scale securely with advanced security capabilities that go beyond standard protections. Get SSO with SCIM provisioning, granular access controls, extended audit logs, and compliance tools designed for enterprise security and IT leaders.

<div id="who-is-the-enterprise-grade-security-package-designed-for" />

#### Who is the Enterprise-Grade Security Package designed for?

Enterprise security and IT leaders preparing for audits, procurement and legal teams in regulated industries evaluating SaaS vendors, and platform admins managing complex access requirements across multiple teams and integrations.

<div id="how-does-scim-provisioning-work" />

#### How does SCIM provisioning work?

Automate user lifecycle management by connecting directly with your identity provider. SCIM automatically syncs user access and roles, handles instant onboarding and offboarding, and eliminates manual account management and orphaned access risks.

<div id="what-compliance-standards-does-this-support" />

#### What compliance standards does this support?

Support audit readiness for SOC2, ISO 27001, and GDPR requirements with 180-day audit log retention, comprehensive access documentation, and real-time SIEM integration for continuous monitoring and compliance verification.

<div id="how-many-roles-and-api-tokens-can-i-create" />

#### How many roles and API tokens can I create?

Create up to 50 customizable roles tailored to your organizational structure and up to 30 service-specific or app-specific restrictions. Isolate access for different integrations and job functions while maintaining least-privilege principles.

<div id="can-i-integrate-with-my-existing-security-tools" />

#### Can I integrate with my existing security tools?

Yes. Stream audit data directly to your SIEM and security tools through API-based log streaming. Enable real-time monitoring, anomaly detection, and automated security responses within your existing SOC infrastructure.

<div id="what-network-restrictions-can-i-apply" />

#### What network restrictions can I apply?

Control platform access through IP allowlists and geographic restrictions. Define trusted networks and locations to prevent unauthorized access while supporting remote work scenarios and secure partner collaboration.

<div id="how-long-are-audit-logs-retained" />

#### How long are audit logs retained?

Access comprehensive audit trails with 180-day log retention that captures every platform interaction. Get complete visibility into user actions, API calls, and access patterns for thorough compliance documentation and security investigations.

<div id="does-this-replace-standard-security-features" />

#### Does this replace standard security features?

No. The Enterprise-Grade Security Package adds advanced capabilities on top of standard security features. You get enhanced controls, automation, and visibility while maintaining all existing security protections.

<div id="how-quickly-can-i-implement-these-security-controls" />

#### How quickly can I implement these security controls?

Deploy enterprise security controls rapidly through seamless SSO integration and automated SCIM provisioning. Most organizations can implement core features within days while maintaining operational continuity and user productivity.

</Accordion>

<div data-zendesk-anchors="h_01JRA2GVNZCDW8C9VW6GH3G4KE=intro compare-the-standard-and-advanced-packages=compare-the-standard-and-enterprise-grade-packages h_01JVS101KETCVDMT1B2WZM89NF=compare-the-standard-and-enterprise-grade-packages h_01JQXQ178D9JKZEREHWTQ2FKBF=multitoken-management-with-restrictions h_01JQXRDEMJF2NT73FP1TFJG63Z=key-features h_01JVRZRXPD4AC1GAMJ2HKC1R9E=example h_01JVRZ0ACA19TGC9WJCZ562B70=note h_01JQXSE4TTYXTWCKXDHB20KJ1Z=how-to-access-and-control-tokens h_01JVRZ9X0D5V765FTXHVHMR807=note-1 h_01JQXQ178DHFQ2Y6JDYYBTKJ0V=audit-log-api-and-extended-retention key-features::8c048755=key-features-1 h_01JQXR4X1CT8P8M3NYEVK0WQYM=key-features-1 h_01JVRZ7WBBY3D8GJE2MJ2E4B0G=note-2 h_01JQXQM2H3VCJMWFRBJDWJ5FAZ=how-to-access-the-audit-log-via-api h_01JVRZ69C2JYY9SK12SEVG3KXF=note-3 h_01JQXQ178DSG340QG8R05B8VNX=accordion-item key-features::e7dd8b4e=key-features-2 h_01JV9W8DTENC21GS0380Q9DP8T=key-features-2 h_01JV9W8DTFCE7Z0MQP96MK7BQC=how-to-set-up-scim-provisioning h_01JV9W8DTFHJME1J1JKKJ3NA6C=sso-set-up h_01JV9W8DTG50YYPQ9RS91K2CJ4=enable-scim h_01JVRZ3MC8J0B1E66A47GM5WYZ=note-4 h_01JV9WBJCPQ0X5SKVVNK4TBYRR=idp-instruction-links h_01JV9WTJ33KMJGZGM9P5PRK917=the-instructions-for-the-idps-can-be-found-below-okta-entra-id-azure-onelogin-jumpcloud h_01JV9WBNC51WYW03RKWHBTP0AG=scim-connections h_01JV9WBS928Z7WKJ2A2CFSWNT4=scim-attributes h_01JV9WBX3JHEMAG62JCASYXB59=roles h_01JV9DMY0Y3795TAT3Q1E3PZRM=limitations h_01JVWCNK70QY6PKJRFZGEQ76SW=ip-allowlist key-features::cd0daf96=key-features-3 h_01JVWCSA3D6DJZXJKKYDFWWPC0=key-features-3 h_01K35NHF44511J17KCXTE073QB=adding-ips-to-the-list h_01K3DGBBVYY08KVYS60F2MYDCW=important h_01K35PGV6Y84JR4CZJ0KGQNWZS=removing-ips-from-the-list h_01K85MXJJ7A9ZTS3PSY2Q0ZDGZ=frequently-asked-questions-about-our-security-package what-is-appsflyers-enterprisegrade-security-package=what-is-appsflyers-enterprise-grade-security-package h_01K85MZT9TDAV684V6PBBFGPTX=what-is-appsflyers-enterprise-grade-security-package who-is-the-enterprisegrade-security-package-designed-for=who-is-the-enterprise-grade-security-package-designed-for h_01K85N0D7WVGH94HT1B7NY4KTZ=who-is-the-enterprise-grade-security-package-designed-for h_01K85N0ZV1CMH5VANHQCEGENAW=how-does-scim-provisioning-work h_01K85N1KB8VSR1Y44YJ7CJD4C2=what-compliance-standards-does-this-support h_01K85N26X17PGVN4C6108A47TB=how-many-roles-and-api-tokens-can-i-create h_01K85N2QW51KDHKE4CQE7VJQHE=can-i-integrate-with-my-existing-security-tools h_01K85N37KPK5XTFRRGW62CCN4M=what-network-restrictions-can-i-apply h_01K85N3SVXVC6TD85V1PQ4EF2D=how-long-are-audit-logs-retained h_01K85N4BCQ3NCH1G2P0EFWE3TQ=does-this-replace-standard-security-features h_01K85N4VR1FBESRN1QDRYF077A=how-quickly-can-i-implement-these-security-controls" />
