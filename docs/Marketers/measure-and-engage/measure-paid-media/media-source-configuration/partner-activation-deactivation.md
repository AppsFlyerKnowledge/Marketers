---
title: Partner activation/deactivation
excerpt: >-
  Activate or deactivate partner integrations, allowing or denying them from
  getting your data and performing actions.
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2019-01-29T08:53:31Z'
  edited_at: '2026-09-09T13:25:57Z'
  id: 360000844778
  locale: en-us
  section: Media source configuration
  section_id: 6551067072785
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360000844778-Partner-activation-deactivation
---
## Activation overview

Partner integrations can be either active or inactive. An integration is first activated by turning on the **Activate partner** toggle from the main integration page. There are various integration types. An integration can also be considered active if any other [integration type](#id) (see table below) is turned on, even while the **Activate partner** toggle is turned off.

> 📘 **Important!**
>
> When enabling a partner integration, certain data, including personal information (e.g., Advertising ID, IP address), will, by default, be shared with them by you. Please ensure you have the appropriate legal basis and rights to share this data. You can limit data sharing with a partner by following the instructions provided in the [Aggregated Advanced Privacy framework](/docs/apply-aggregated-advanced-privacy-framework) and [Privacy preserving methods in the SDK](/docs/apply-privacy-preserving-sdk-methods) articles.

**To get to the partner integration page of the currently selected app:**

* In AppsFlyer, from the side menu, select **Collaborate** > **Active Integrations** and select the partner.

The sections below describe the various integration types and the impact of partner activation settings on integrations:

<div id="id" />

<Accordion title="Integration types">

The primary integration (**Activate partner**) is activated on the first integration tab. Additional integration types (see table below) are activated from subsequent tabs. **Each integration runs individually**. For an integration to be considered active, at least one integration type must be turned on, regardless of the state of the Activate partner toggle.

| Integration type | Description |
| --- | --- |
| **Main integration (**[**Activate partner**](/docs/set-up-an-integrated-partner#a-activate-partner)) | Enables conversions to be attributed and postbacks to be sent to partners |
| [**Cost**](/docs/roi360-cost-aggregation-overview) (when applicable) | Enables getting data on cost, clicks, and impressions for your campaigns, adsets, ads, and geos/countries |
| [**Ad revenue**](/docs/roi360-guide-ad-revenue-attribution) (when applicable) | Enables getting data on revenue from your ads |
| [**SKAN**](/docs/skan-integrated-partners-list) (when applicable) | Enables getting SKAN postbacks from partners |
| [**Permissions**](/docs/set-up-an-integrated-partner#permissions-tab) | Enables granting permissions for ad networks and agencies to access your data and perform actions in your integration |

</Accordion>

<div id="effect-of-the-partner-activation-setting" />

<Accordion title="Effect of the partner activation setting">

The following table presents the impact of partner activation settings on attribution and postbacks in various scenarios.

<table><thead><tr><th>Scenario</th><th>Activate partner:<br/>On</th><th>Activate partner: Off</th></tr></thead><tbody><tr><td>Attribution and postbacks for new installs, <span>re-attributions, and re-engagements</span></td><td><p><strong>Attribution:</strong> Yes</p><p><strong>Postbacks:</strong> Yes</p></td><td><p><strong>Attribution:</strong> No</p><p><strong>Postbacks:</strong> No</p></td></tr><tr><td><span>Engagement (click) occurs before deactivation; install/re-attribution/re-engagement occurs after deactivation</span></td><td><p><span>Not applicable</span></p><p><strong> </strong></p></td><td><span>The deactivated partner is not attributed.</span></td></tr><tr><td>Clicks and impressions</td><td>The engagements can be attributed and displayed in the dashboard.</td><td><ul><li>The click redirects to a 403 forbidden page.</li><li>The engagements cannot be attributed and not displayed in the dashboard.</li></ul></td></tr><tr><td>SKAN attribution</td><td colspan="2"><p>Not applicable.</p><p>When SKAN attribution is configured, SKAN data is recorded whether <strong>Activate partner</strong> is turned on or off. </p></td></tr></tbody></table>

</Accordion>

## Activate a partner integration

**To activate or edit the main integration (Integration tab) of the currently selected app:**

1. **To activate:** In AppsFlyer, from the side menu, select **Collaborate > Partner Integrations > Marketplace** tab.  
   **To edit:** In AppsFlyer, from the side menu, select**Collaborate > Partner Integrations > Active integrations** tab.
2. Search for the partner and select it. You’re directed to the integration setup page.
3. From the **Integration**tab, turn on **Activate partner**.
4. Click **Save Integration**.

See [other integration types](#id).

> 📘 **Caution**
>
> Make sure not to use the **Activate partner** setting to pause or end campaigns. Doing so could cause irreversible damage to active campaign measurement.

#### Who can activate an integration?

Partner integrations can be activated by marketers and agencies in accordance with the table that follows.

| Activated by | SRN | Non-SRN |
| --- | --- | --- |
| Marketer | Activates for self-use and  on behalf of agencies | Activates for self-use |
| Agency | Can't activate | Activates agency-appointed non-SRNs |

## Deactivate a partner integration

You can deactivate a partner integration of your app by turning off the **Activate partner** toggle. This means partners don't get conversion attribution and postbacks aren't sent to them. However, if any of the other [integration types](#id) are still activated, they continue to operate even after the **Activate partner** toggle is deactivated. This means that the **integration is still Active** and data may still be collected.

<span id="deactivating-a-partner"></span>**To deactivate a partner integration:**

1. In AppsFlyer, from the side menu, select **Collaborate > Partner Integrations > Active integrations** tab.
2. Search for the partner and select it. You’re directed to the integration setup page.
3. From the **Integration**tab, turn off **Activate partner**.
4. Click **Save Integration**.
5. To completely deactivate the partner from all [other integration types](#id), go through each of the tabs on the integration page and disable them.  
   **Note:** For Google and Meta ads, to stop recording SKAN data, go to the SKAN tab and delete the connection.
6. Click **Save Integration**.
7. [Optional] After saving the integration, while remaining on the configuration page, you can **deactivate the partner from other apps:**
   1. From the top-left corner, under the partner name, click the app name to open the list of apps.
   2. Select a different app from the drop-down list.
   3. Repeat steps 2-4.

## Partner and Agency access to dashboards

Partners and agencies have different dashboard views and configuration options, according to their permissions.

### Partner visibility

* Partners view the **Activate partner** setting in read-only mode. This is the case even if the partner has permission to configure the integration.
* Visibility of partner settings depends on whether it was the marketer or the agency who configured the integration, as detailed in the following table:

| Integration configured by | Setup visible to partner |
| --- | --- |
| Marketer | Yes |
| Agency | No |

### Agency permissions

You can grant agencies permission to work with your app and run traffic on your behalf.

**To grant agency permissions to an app:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Active integrations**.
2. Find the agency and select it.
3. Go to the **Permissions** tab and turn on **Agency Permissions.**
4. [Optional] Grant the agency additional [permissions](/docs/set-up-an-integrated-partner#agency-permissions).

> 📘 **Note**
>
> * An **agency** can activate or deactivate the **Activate partner** setting for **non-SRN partners**.
> * A **Marketer** can activate or deactivate the **Activate partner** setting for **SRNs**. When doing so, installs from that SRN **aren't attributed to the agency**.

#### Disabled agency permissions

When permissions are disabled for agencies:

* The agency can't access the app on the AppsFlyer dashboard.
* New installs and events are not attributed to the agency.
* Postbacks are not sent to the media sources used by the agency.
* New events from conversions prior to disabling the agency are attributed and displayed in the marketer's dashboard, but postbacks are not sent to the media sources.

**Note:** If the marketer disables agency permissions, the agency's historical data (such as installs and cost) becomes non-transparent.

The following examples describe what happens to traffic that continues to be sent after a marketer removes agency permissions:

> 📘 **Example 1**
>
> **Agency campaign with a non-SRN (attribution link partner)**
>
> The traffic is attributed to organic, or to a prior engagement if still within its lookback window. The agency is not attributed.
>
> This example is also applicable to scenarios in which AppsFlyer receives click-through attribution links as well as querying the partner’s API

> 📘 **Example 2**
>
> **Agency campaign with an SRN (attribution link partner)**
>
> The traffic is attributed to the SRN on the marketer's dashboard, but not attributed to the agency.

<div data-zendesk-anchors="overview=activation-overview h_01HRA982WC3519NMGXV5WEY1AZ=activation-overview 01JDM949M75Q3BAG6M65DYMHZT=important %20id%3D=id integration-types=id h_01HRAERWRJ2SBRY9XQG983WP5M=effect-of-the-partner-activation-setting activating-a-partner=activate-a-partner-integration h_01HJR1D6THJ9TNGZZV78SEVBZN=activate-a-partner-integration h_01HJR1D6THSEA65CY71VWJYX1P=caution who-can-activate-partners=who-can-activate-an-integration h_01HJR1D6THRMF854SCSFVZFWM9=who-can-activate-an-integration deactivated-partners=deactivate-a-partner-integration h_01HJR1D6THE2QWSF971VQFXCBX=deactivate-a-partner-integration h_01HJR1D6THS60X7VTDN2X6FT0K=deactivating-a-partner partner-and-agency-dashboards=partner-and-agency-access-to-dashboards h_01HJR1D6THB0N1C8XCC5YAMQQ3=partner-and-agency-access-to-dashboards h_01HJR1D6TJ6D3TV2PCFWP4SEAR=partner-visibility h_01HJR1D6TJ9PHVG6GGQ2Z1KJRQ=agency-permissions h_01HJR1D6TJ9T55PSPBRNW1XXS7=note h_01HJR1D6TJ1ABQM6HCPK277R0Z=disabled-agency-permissions h_01HJR1D6TJBT0D3G2KWKFKEW5S=example-1 h_01HJR1D6TJTXF49JP3VJE6ZYC9=example-2" />
