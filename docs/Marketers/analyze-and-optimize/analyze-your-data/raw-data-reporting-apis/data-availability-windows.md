---
title: "Data availability windows"
excerpt: "Learn about the data availability windows and retention periods for raw and aggregated reports in AppsFlyer."
---
> 📘 Difference between availability and retention
>
> The terms **availability window** and **data retention** mean different things. [Data retention](https://www.appsflyer.com/legal/services-privacy-policy/) relates to the period we keep raw data on our servers and is of longer duration than the availability window.

> 📘 Good to know
>
> * The window duration depends on your subscription package.
> * The article doesn't apply to [Data Locker](/docs/data-locker-for-marketers).

### Raw data availability window

The availability window limits raw data provided by Pull API and the Raw Data export page. The window duration depends on the report type, as detailed in the following table.

| Report event type | Example report types | Default availability window |
| --- | --- | --- |
| Attributions | Organic installs, non-organic installs, retargeting conversions, uninstalls | 60 out of the last 90 days |
| In-app events | Organic in-app events, non-organic in-app events, retargeting in-app events | 31 out of the last 90 days |

### Aggregated data availability window

An availability window limits data provided by Pull API and the Aggregated Data export page. The window duration depends on the report type, as detailed in the following table.

| Report | Availability window |
| --- | --- |
| Aggregated reports | 25 months (2 years + 1 month), [starting with the first app install](/docs/bulletin-aggregated-ltv-data-availability) |

<Cards>
  <Card title="Report generation quotas" href="/docs/report-generation-quotas-rate-limitations">
    View the report generation quotas and limits for your account.
  </Card>
</Cards>