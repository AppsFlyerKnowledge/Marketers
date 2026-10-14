---
title: Apply IP masking to user data
excerpt: >-
  How to mask app user IP addresses in AppsFlyer raw data reports and in
  postbacks sent to partners.
metadata:
  keywords:
    - IP masking
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2016-05-23T12:59:55Z'
  edited_at: '2025-06-03T07:49:17Z'
  id: 208879066
  locale: en-us
  section: Preserve user privacy
  section_id: 6551440878097
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/208879066-Apply-IP-masking-to-user-data
---
## IP masking

When turning on IP masking:

* User IP addresses aren't listed in raw data reports nor are they provided via postbacks to partners
* IP address field is populated with the value 1.1.1.1

> 📘 **Note**
>
> * Installs that occurred before IP masking was turned on aren't masked
> * [AEM data sharing](/docs/meta-ads-aggregate-event-measurement-aem-for-ios#aem-data-sharing) for Meta ads isn't supported for both server-to-server and SDK events when IP masking is turned on. This means data isn't shared with Meta ads.

> 📘 **Example**
>
> * The IP masking setting follows this path: Turned off, turned on, and then turned off.
> * Three users install the app on different dates as shown in the app install table
> * The IP masking and raw data report table below shows the status of the IP masking setting and related raw data on the relevant dates.
>
> App installs:
>
>
>
> | Install date | User ID | IP address |
> | --- | --- | --- |
> | January 2 | User\_A | 192.0.2.1 |
> | January 7 | User\_B | 192.0.2.33 |
> | January 14 | User\_C | 203.0.113.1 |
>
>
>
> IP masking and raw data:
>
>
>
> | Date | IP masking setting status | Raw data report |
> | --- | --- | --- |
> | January 1 | Off | User A 192.0.2.1 |
> | January 2 | On | User\_A 192.0.2.1 |
> | January 8 | On | User\_A 192.0.2.1  <br />User\_B 1.1.1.1 |
> | January 9 | Off | User\_A 192.0.2.1  <br />User\_B 1.1.1.1 |
> | January 15 | Off | User\_A 192.0.2.1  <br />User\_B 1.1.1.1  <br />User\_C 203.0.113.1 |

## Turn on IP masking

IP masking is set per app and affects installs from all sources.

**To enable IP masking:**

1. In AppsFlyer, from the side menu, select **Settings** > **App Settings.**
2. Scroll down to **Advanced Settings**.
3. Turn on **Mask IP addresses**.

## IP masking in raw data reports

When IP masking is turned on:

* New installs and in-app events show an IP address of 1.1.1.1.
* [Location-related parameters](/docs/determine-user-location), like country and city, still appear in raw data reports.

**Example raw data report**

![ip_masking.png](https://files.readme.io/e52f8bd698191f0b1ac08e595e539f15bda59567ed51ddda32a0d80db3bdf23c-360001962938.png)

<div data-zendesk-anchors="h_01HA91HHADCTT7QS2K79TJEY2C=ip-masking h_01HA92HF3ZYR2NBTXQ1S2AHCAA=note h_01HA91HHAD7BCXRZW6AD9NRDBN=example enabling-ip-masking=turn-on-ip-masking h_01HA91HHAEM220CE8805GFQYKR=turn-on-ip-masking h_01HA91HHAE14D6ES1ERNK93VY9=ip-masking-in-raw-data-reports" />
