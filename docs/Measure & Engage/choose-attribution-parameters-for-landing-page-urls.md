---
title: "Choose attribution parameters for landing page URLs"
excerpt: "Learn how to use consistent PID and UTM parameters in your landing page URLs to ensure accurate campaign attribution and granularity in Web Performance Measurement."
---
Use consistent, complete URL parameters in your website landing page links to get the best campaign granularity while maintaining accurate attribution in Web Performance Measurement.

## About URL attribution parameter classes

AppsFlyer reads campaign parameters from your landing page URL (the link a user clicks) and uses them to attribute sessions and events to the correct **media source**, **campaign**, and (when available) deeper hierarchy such as **ad set** and **ad**.

The parameters that you include determine the measurement results of your campaign. In other words, the same landing page can produce very different results depending on which parameters you include.

The URL parameters can belong to one of two classes: PID and UTM.

* The PID class includes the AppsFlyer URL parameters.
* The UTM class includes the standard UTM parameters.

For more information about how Web Performance Measurement processes URL parameters, see [About traffic source resolution](https://support.appsflyer.com/hc/articles/43518064765201--WIP-About-traffic-source-resolution).

### Supported PID and UTM parameters

Web Performance Measurement supports the following parameters.

| # | Parameter | Used for | Parameter class | Available in the dashboard | Raw data field |
| --- | --- | --- | --- | --- | --- |
| 1 | `pid` | Media source | PID | Yes | `media_source` |
| 2 | `c` | Campaign name | PID | Yes | `campaign_name` |
| 3 | `af_c_id` | Campaign ID | PID | Yes | `campaign_id` |
| 4 | `af_adset` | Ad set name | PID | Yes | `adset_name` |
| 5 | `af_adset_id` | Ad set ID | PID | Yes | `adset_id` |
| 6 | `af_ad` | Ad name | PID | Yes | `ad_name` |
| 7 | `af_ad_id` | Ad ID | PID | Yes | `ad_id` |
| 8 | `utm_source` | Media source | UTM | Yes | `media_source` |
| 9 | `utm_medium` | Media type | UTM | No | `media_type` |
| 10 | `utm_campaign` | Campaign name | UTM | Yes | `campaign_name` |

## Choose the right attribution parameters

AppsFlyer evaluates URL parameters independently for each reporting field (such as Media Source or Campaign) using a specific priority waterfall. This approach allows you to support AppsFlyer attribution alongside other tools, such as Google Analytics, by using both the **PID class** (AppsFlyer-native) and the **UTM class** (standard marketing) in the same URL.

Web Performance Measurement checks the priority order for each field individually. If a parameter from the higher-priority PID class is not present for a specific attribute, the system automatically falls back to the corresponding parameter in the UTM class to determine the correct value for that field.

<Tabs>
<Tab title="Scenario A: PID class only">

Use the PID class when AppsFlyer reporting is your primary goal.

```auto
www.website.com?pid=facebook_int&c={{campaign.name}}&af_c_id={{campaign.id}}
```

**Result**: AppsFlyer identifies the media source using `pid` and the campaign using `c`.

</Tab>
<Tab title="Scenario B: UTM class only">

If `pid` is missing, AppsFlyer falls back to the UTM class.

```auto
www.website.com?utm_source=facebook&utm_medium=paidsocial&utm_campaign={{campaign.name}}
```

**Result**: AppsFlyer identifies the media source using `utm_source` and the campaign using `utm_campaign`.

</Tab>
<Tab title="Scenario C: Both PID and UTM classes">

AppsFlyer allows you to include parameters from different classes (e.g., PID and UTM) within the same URL. This is useful when you need to support AppsFlyer attribution alongside other analytics tools, such as Google Analytics or internal measurement systems.

AppsFlyer processes attribution fields, such as Media Source and Campaign, independently. For each specific field, the system follows a priority waterfall to determine which value to record. Generally, the **PID class** takes precedence over the **UTM class** for that specific field.

#### Example 1: Overlapping parameters

```auto
www.website.com?pid=facebook_ads&c=summer_sale&utm_source=facebook&utm_campaign=seasonal_promo
```

* **Media Source:** AppsFlyer detects both `pid` and `utm_source`. Following the priority waterfall for this field, it records `facebook_ads`.
* **Campaign:** AppsFlyer detects both `c` and `utm_campaign`. Following the priority waterfall for this field, it records `summer_sale`.
* **Result:** AppsFlyer uses the higher-priority PID class values, while external tools can still read the UTM values.

#### Example 2: Mixed parameter classes

```auto
www.website.com?utm_source=facebook&c=summer_sale
```

* **Media Source:** AppsFlyer detects `utm_source`. Since no PID class equivalent (`pid`) is present, it records `facebook` from the UTM class.
* **Campaign:** AppsFlyer detects `c`. Since no UTM class equivalent (`utm_campaign`) is present, it records `summer_sale` from the PID class.
* **Result:** AppsFlyer successfully attributes the event using values from both classes because each field is resolved independently.

</Tab>
</Tabs>

## Other Best Practices

### Keep parameter values in a consistent case

Parameter values are **case-sensitive**. For example, `utm_source=channel1` and `utm_source=CHANNEL1` are treated as **different media sources**.

> 👍 Best practice
>
> Define a casing convention (lowercase is common) and apply it across all URLs.

### Use question marks only once

Rules:

* Use only **one** question mark (`?`) before the query parameters in the URL.
* Don’t use additional question marks in the URL.

Correct:

* `www.website.com?parameters`

Incorrect:

* `www.website.com??parameters`
* `www.website.com?parameter1?parameter2`

### Don’t use anchor signs (#)

Don’t use anchor signs (`#`) in the URL.

Why: parameters after `#` may not load and may not be recorded by the web SDK.