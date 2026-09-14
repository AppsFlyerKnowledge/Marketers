---
title: "Determine user location"
excerpt: "Learn how AppsFlyer determines user location using device IP addresses mapped via Digital Element, and understand potential reasons for location discrepancies."
---
**At a glance:** User location is determined using the device IP address which is mapped to the general location of the user (city, state, country, and so on). User location impacts creatives selection, campaign cost, engagement, and user quality.

![5888ResolveIpAddress_us-en.png](https://files.readme.io/166e48fb0bb90b627bc51e29b53a556b71939749ab3e5eadff7d6edf0f0dfd25-360011758517.png)

## Determining user location

User actions in the device are reported to AppsFlyer. The actions (events) contain various data fields including the device IP address.

> 🚧 VPN and Proxy Masking
>
> In some cases, the true device IP is masked by a VPN, mechanism like iOS 15 Private Relay, or SKAN postback proxy servers. Consequently, the IP address to geo-location conversion described in this article may be wrong or misleading. AppsFlyer has no control over this.

The IP address is converted by AppsFlyer into geo-location information using data provided by [Digital Element](http://www.digitalelement.com/), the global IP location leader.

- The geo-location information can include:
  - Territory (country): ISO 3166 (alpha-2) codes, or  EU (Europe) or AS (Asia) if no territory-specific information is available.
  - City: This can correlate to a neighborhood or district within the city without being directly related to the actual city boundaries.
  - DMA (designated market area, regions, or geographic areas for television viewing measured by the [Nielsen](https://www.nielsen.com/us/en/solutions/nielsen-global-connect/) company. [Metro codes in CSV file.](https://support.appsflyer.com/hc/article_attachments/360012539677)
  - Region: The geographic region or continent.
  - State or province: See table of [localized state names in CSV file](https://support.appsflyer.com/hc/article_attachments/360012615238). We use the region field in this table. This consists of up to 3 letters or numbers.
  - Postal code.
- IP address to geo-location tables are updated at regular intervals, usually weekly.

**Example: Conversion of IP address to geolocation** ![IPTables_us-en.png](https://files.readme.io/0d7d4d4190face77e18476bdb9e47fdd26ed62ab91cd641f76f728d9a7c8d005-360011787798.png)

#### Note regarding the United Kingdom (UK)

![blobid0.png](https://files.readme.io/0e65abc671ddcef188051a6c65e1dc834c359ed8fb6b2255b5700cba84324425-blobid0.png)

- In the platform, the United Kingdom is denoted using the code UK.
- The ISO 3166 code for the United Kingdom is GB. UK is reserved, but not allocated, by ISO for the United Kingdom.

### Location discrepancies

In some cases, there may be differences in the derived location of users between AppsFlyer and other platforms, even if other platform uses Digital Element to resolve IP addresses. Possible reasons for location discrepancy are:

- **Database updates:** to enable fast attribution, AppsFlyer resolves the IP addresses into location data internally. AppsFlyer fetches the global map from Digital Element periodically and not in real-time. If AppsFlyer and the other platform fetch Digital Element data at different times this can explain differences.
- **ISP changes:** Digital Element databases change rapidly as service providers (ISPs) change their IP mappings.
- **Different plans/methods:** Digital Element offers different package plans based on the required level of granularity. Other platforms using different Digital Element packages or different methods for defining a device's ID, may provide different results.
- **Proxy, or VPN:** If a user implements a VPN or proxy, then we won't know the true user IP address. The Geo resolution will be according to the VPN/proxy address.
- **To learn more:** [The tricky science behind IP geolocation](https://www.digitalelement.com/blog/the-tricky-science-behind-ip-geolocation/)

### Reference Files

<Cards>
  <Card title="metro_codes.csv" href="https://support.appsflyer.com/hc/en-us/article_attachments/360012539677">
    Download the CSV file containing Nielsen metro codes.
  </Card>
  <Card title="Localized_Region_List-UTF8.csv" href="https://support.appsflyer.com/hc/en-us/article_attachments/360012615238">
    Download the CSV file containing localized state and region names.
  </Card>
</Cards>