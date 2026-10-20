---
title: AppsFlyer server IP address ranges (allowlisting)
excerpt: AppsFlyer IP addresses used for outgoing API requests.
metadata:
  keywords:
    - whitelisting
    - AppsFlyer
    - IPs
    - Advertisers
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
    - Ad Networks
  created_at: '2015-12-24T11:30:11Z'
  edited_at: '2023-07-12T00:00:57Z'
  id: 207447093
  locale: en-us
  section: Account security
  section_id: 6551173202065
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207447093-AppsFlyer-server-IP-address-ranges-allowlisting
---
## AppsFlyer server IP address ranges

The IP addresses listed are controlled by and for the use of AppsFlyer. The list changes from time to time according to our capacity and operational requirements. We make every effort to make list changes infrequently.

AppsFlyer APIs provide attribution and reporting services to advertisers and partners. These services include:

* Sending postbacks
* Sending Push API messages

If you use network perimeter devices such as firewalls and proxy servers, you must ask your security team to allowlist AppsFlyer IP addresses as listed in this [IP allowlist.](https://docs.google.com/spreadsheets/d/e/2PACX-1vTzJqwOhIkSV0Mbnu4DZOx2eWKAd8OPRUNCu2REjz9z9qonI5ZDlHl6kGd1KAXopaDbf1MzuNXjeVj-/pub?gid=0&single=true&output=csv)

On February 16, 2022, we deprecated legacy IP addresses and removed them from the allowlist.

Allowlisted addresses use the following CIDR blocks:

* [45.92.116.0/22]
* [194.28.46.0/23]

### Uploading Audiences

If you use network perimeter devices such as firewalls and proxy servers, you must ask your security team to allowlist AppsFlyer IP addresses as listed in this [IP allowlist for Audiences](https://support.appsflyer.com/hc/en-us/article_attachments/16888953497617/IP_list_for_Audiences.xlsx).

Learn more about [Audiences](/docs/audiences-guide).

### Pull API and server-to-server (S2S)

Pull API and S2S aren't affected by the addresses listed in this article. However, verify that the **.appsflyer.com* domain is allowlisted and isn't blocked in any way.

<div data-zendesk-anchors="pull-api-and-servertoserver-s2s=pull-api-and-server-to-server-s2s" />
