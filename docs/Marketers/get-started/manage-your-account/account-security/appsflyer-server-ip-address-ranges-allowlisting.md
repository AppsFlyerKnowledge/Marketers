---
title: "AppsFlyer server IP address ranges (allowlisting)"
excerpt: "A comprehensive guide to AppsFlyer's server IP address ranges and CIDR blocks required for network perimeter allowlisting."
---
**At a glance:** AppsFlyer IP addresses used for outgoing API requests.

## AppsFlyer server IP address ranges

The IP addresses listed are controlled by and for the use of AppsFlyer. The list changes from time to time according to our capacity and operational requirements. We make every effort to make list changes infrequently.

AppsFlyer APIs provide attribution and reporting services to advertisers and partners. These services include:

- Sending postbacks
- Sending Push API messages

If you use network perimeter devices such as firewalls and proxy servers, you must ask your security team to allowlist AppsFlyer IP addresses as listed in this [IP allowlist.](https://docs.google.com/spreadsheets/d/e/2PACX-1vTzJqwOhIkSV0Mbnu4DZOx2eWKAd8OPRUNCu2REjz9z9qonI5ZDlHl6kGd1KAXopaDbf1MzuNXjeVj-/pub?gid=0&single=true&output=csv)

On February 16, 2022, we deprecated legacy IP addresses and removed them from the allowlist.

Allowlisted addresses use the following CIDR blocks:

- [45.92.116.0/22]
- [194.28.46.0/23]

### Uploading Audiences

If you use network perimeter devices such as firewalls and proxy servers, you must ask your security team to allowlist AppsFlyer IP addresses as listed in this [IP allowlist for Audiences](https://support.appsflyer.com/hc/en-us/article_attachments/16888953497617/IP_list_for_Audiences.xlsx).

Learn more about [Audiences](/docs/audiences-guide).

### Pull API and server-to-server (S2S)

Pull API and S2S aren't affected by the addresses listed in this article. However, verify that the _*.appsflyer.com_ domain is allowlisted and isn't blocked in any way.