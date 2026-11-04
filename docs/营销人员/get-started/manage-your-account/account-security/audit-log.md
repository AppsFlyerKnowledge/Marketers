---
title: Audit log
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
  created_at: '2020-05-05T14:18:09Z'
  edited_at: '2024-09-15T05:36:12Z'
  id: 360007971697
  locale: en-us
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/en-us/articles/360007971697-Audit-log
---
> **At a glance:** Identify and protect against unauthorized access to your AppsFlyer account using the Audit log. View and download a summary of security-related activity in your account.

<div id="overview" />

## Overview

The **Audit log** provides a central location to review various activities in your account, such as logins, data access, API calls, configuration and permission modifications to integrated partners, validation rules, audiences, and other significant events. This plays a key role in ensuring transparency, security, and adherence to compliance standards. To protect the security of your AppsFlyer account, it's recommended to periodically review **who** is accessing your account and **how** it is being accessed. Audit log data is available for the past 90 days.

**To access the Audit log:**

1. From the top bar, open the account menu (email address dropdown): **Security center.**
2. In the **Audit log** section, click **View audit log.**

<div id="using-the-audit-log" />

## Using the Audit log

A description of the data provided by the audit log and a summary of its capabilities are provided in the table below.

[![audit_log.png](https://files.readme.io/4101dfb4dc84e4e916d165a22387bd6a84fa7889bc4e82e636c980fde1cac248-6867050961809.png)](https://files.readme.io/4101dfb4dc84e4e916d165a22387bd6a84fa7889bc4e82e636c980fde1cac248-6867050961809.png)

|  | Item | Description |
| --- | --- | --- |
| ![A.png](https://files.readme.io/d515ad5eb908256574b52dee5d598a785020c3392b410b9fa4574eeb8c4ae594-6867187386897.png) | Search box & filters | Filter the displayed data to focus only on what you want to see:<ul><li>Use the search box to filter the data by a specific term (such as a relevant App ID, email address, etc.)</li><li>Use the date picker to select the timeframe for which data is displayed</li><li>Use the service filter to filter the data based on the specific services accessed:<ul><li>System access</li><li>Integrated partner permissions</li><li>User management</li><li>Validation Rules</li><li>API calls</li></ul></li></ul>Note that the **API calls** service is deselected by default in order to optimize report readability. Be sure to select this service if you want to include it in the report. |
| ![B.png](https://files.readme.io/ee0be2e394ad7bf76766a84c3bcad882a55dd0522e0aa41ed8ef11432c0df592-6867187537809.png) | Audit log data | Each entry in the the audit log includes the following data:<ul><li>**Date & time:** the date and time the service was accessed (in UTC)</li><li>**App/account accessed:**<ul><li>For user logins (System access) and User management, this column shows **Account** (indicating account-level access).</li><li>For API calls, this column shows either **Account** access or the **App ID** of the app for which data was accessed.</li></ul></li><li>**Credentials**<ul><li>For System access or User management, this column shows the email address of the user accessing the service.</li><li>For API calls, this column shows the AppsFlyer API token used (V2)</li></ul></li><li>**Service:** the service that was accessed (System access, User management, or API calls)</li><li>**Action:** the logged action (examples: login, logout, the data accessed by an API)</li><li>**Details:** Additional details about the logged action</li></ul> |
| ![C.png](https://files.readme.io/078ad9663eed2141f7047e0869fe02f4d1a0f8545176bce4d1c6027bfaa439b3-6867187658385.png) | ![audit_log_download_button.png](https://files.readme.io/50e6cfef2aceb4b199f79008090da39d021f94be8d88d329bb8c8a0723edfa75-6867407922577.png) | Click the download button to download the audit log as a CSV file.<ul><li>All selections applied to the report as displayed on screen (using the search box and filters) are applied to the downloaded file as well.</li></ul> |

<div id="troubleshooting" />

## Troubleshooting

<div id="why-does-an-advertiser-audit-log-show-partner-api-call-requests" />

<Accordion title="Why does an advertiser's audit log show partner API call requests?">

When a partner makes an API request on an app owned by an advertiser, both the partner and the advertiser see the request in their audit log.

When an advertiser makes an API request using their own token, it will only show in the advertiser's audit log.

</Accordion>

<div data-zendesk-anchors="h_01H9Q3XYYBKYSRP3T0R2MP712C=overview h_01H9Q3XYYBBCB6PXBZBF97QE11=using-the-audit-log h_01H9Q3XYYB24R3EATM7R32V0G7=troubleshooting h_01H9Q3XYYCHWJ1NQS389MR311X=why-does-an-advertiser-audit-log-show-partner-api-call-requests" />
