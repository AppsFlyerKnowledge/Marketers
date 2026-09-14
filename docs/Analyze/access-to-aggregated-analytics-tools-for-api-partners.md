---
title: "Access to aggregated analytics tools for API partners"
excerpt: "Learn how API partners can use their API token to access advertisers' performance metrics and how advertisers can grant and manage these permissions."
---
API partners can use their API token to access advertisers' data when granted permission by the advertiser, allowing them to extract performance metrics from the platform.

## API token permissions

![api-access-permissions.jpg](https://files.readme.io/7961394cb39cf1e6f85d77cd732183edea5fb1408c220ca05b23ae7bbb50138e-23701010316689.jpg)

Advertisers can grant the following app-level permissions:

| Permission type | Reporting tool | Limitations |
| --- | --- | --- |
| Aggregated analytics reporting | [Cohort analytics data via DataLocker](/docs/cohort-analytics-via-data-locker) | X Ads campaign data isn't available to API partners due to their restrictions. |
| SKAN reporting | - [SKAN performance reporting](https://support.appsflyer.com/hc/articles/360014104157)<br>  <br>- [SKAN aggregate postback reporting](https://support.appsflyer.com/hc/articles/360016646557) | -- |

### Considerations

- **Advertiser perspective**   - Advertisers can grant the API partner permissions as listed in the preceding table.
- **Partner perspective**
  - Extract data by API. **Note**: Security is implemented via an authentication [token](https://support.appsflyer.com/hc/articles/360004562377-Managing-API-tokens) available in the AppsFlyer dashboard. The same token is valid for all apps and advertisers.
  - Get data via Data Locker
  - Advertisers can revoke permissions to access their app data. This won't impact your partner credentials.

Granting access to the partner

> 🚧 Warning
>
> - The permissions type lets the partner access data, including traffic brought by other partners and organic data.
> - Don't share your token with partners.

**To grant API access to the partner:**

1. In AppsFlyer, from the side menu, select **Collaborate** \> **Integrated partners** _**.**_
2. Search for the partner and select it.
3. Click **Set up integration**. You're directed to the integration setup page.
4. From the **API access** tab, turn on one or more permissions. Select from:
   - **Aggregate analytics reporting**
   - **SKAdNetwork reporting**(for iOS apps, not relevant for Data Locker)
5. Click **Save API access**.
6. Notify the partner that you have enabled the necessary API access.