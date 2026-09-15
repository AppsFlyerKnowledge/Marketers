---
title: "Apply IP masking to user data"
excerpt: "Learn how to mask app user IP addresses in AppsFlyer raw data reports and in postbacks sent to partners."
---
At a glance: How to mask app user IP addresses in AppsFlyer raw data reports and in postbacks sent to partners.

## IP masking

When turning on IP masking:

- User IP addresses aren't listed in raw data reports nor are they provided via postbacks to partners
- IP address field is populated with the value 1.1.1.1

> 📘 Note
>
> - Installs that occurred before IP masking was turned on aren't masked
> - [AEM data sharing](https://support.appsflyer.com/hc/articles/19228737402129#aem-data-sharing) for Meta ads isn't supported for both server-to-server and SDK events when IP masking is turned on. This means data isn't shared with Meta ads.

#### Example

- The IP masking setting follows this path: Turned off, turned on, and then turned off.
- Three users install the app on different dates as shown in the app install table
- The IP masking and raw data report table below shows the status of the IP masking setting and related raw data on the relevant dates.

App installs:

| Install date | User ID | IP address |
| --- | --- | --- |
| January 2 | User\_A | 192.0.2.1 |
| January 7 | User\_B | 192.0.2.33 |
| January 14 | User\_C | 203.0.113.1 |

IP masking and raw data:

| Date | IP masking setting status | Raw data report |
| --- | --- | --- |
| January 1 | Off | User A 192.0.2.1 |
| January 2 | On | User\_A 192.0.2.1 |
| January 8 | On | User\_A 192.0.2.1<br>User\_B 1.1.1.1 |
| January 9 | Off | User\_A 192.0.2.1<br>User\_B 1.1.1.1 |
| January 15 | Off | User\_A 192.0.2.1<br>User\_B 1.1.1.1<br>User\_C 203.0.113.1 |

## Turn on IP masking

IP masking is set per app and affects installs from all sources.

**To enable IP masking:**

1. In AppsFlyer, from the side menu, select **Settings** > **App Settings.**
2. Scroll down to **Advanced Settings**.
3. Turn on **Mask IP addresses**.

## IP masking in raw data reports

When IP masking is turned on:

- New installs and in-app events show an IP address of 1.1.1.1.
- [Location-related parameters](https://support.appsflyer.com/hc/articles/360000847378), like country and city, still appear in raw data reports.

**Example raw data report**

<Image src="https://files.readme.io/e52f8bd698191f0b1ac08e595e539f15bda59567ed51ddda32a0d80db3bdf23c-360001962938.png" alt="ip_masking.png" />