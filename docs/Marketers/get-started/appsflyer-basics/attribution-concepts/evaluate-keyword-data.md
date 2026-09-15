---
title: "Evaluate Keyword data"
excerpt: "Learn how to retrieve and analyze organic and non-organic keyword data for iOS and Android to optimize your app store conversions."
---
Get detailed keyword data that lets you see which search terms are most popular, so you can optimize organic conversions.

## Keyword data

Organic search is a valuable traffic source for your apps. Organic users don't incur acquisition costs and are usually among the most engaged cohorts.

With a few tweaks to your app page, it is possible to increase the amount of new organic installs. To optimize organic searches, you need to get organic keyword data for your app.

### iOS keywords

If you work with Apple Ads, you can get [detailed keyword data](https://support.appsflyer.com/hc/articles/213747963-Apple-Search-Ads-configuration#get-keyword-data) for your **non-organic** users attributed to Apple Ads. In iOS, **organic** keyword data is not available.

### Android keywords

Google shares organic keyword data (on the Referrer URL) for users that do the following:

- Use Android devices
- Use Chrome browser
- Visit Google.com and perform a search
- Install an app from the Google results page
- Launch the app

The SDK extracts the keywords when provided by Google in the _&utm\_term_ parameter of the referrer if it is part of the link to Google Play. The values where possible are contained in the following AppsFlyer raw data fields: _http\_referrer_, _gp\_broadcast\_referrer_, _keywords._

> 🚧 Important
>
> Expect that less than 1% of organic Android users follow this funnel and have organic keyword data.

In other scenarios, Google does not share organic keyword data. For example, users searching in Google Play don't have organic keyword data.

> 📘 Note
>
> This limitation is applied by Google to all external vendors, including all attribution vendors.

### Using the keyword data

Organic keyword data is found in the following:

- **Raw organic data reports**

In AppsFlyer, from the side menu, select **Export** > **Raw Data Export** to view the breakdown of used organic keywords.
- **Advanced reports**

Go to [Pivot](https://support.appsflyer.com/hc/articles/115001421846-Pivot-report), [Retention, and Cohort](https://support.appsflyer.com/hc/articles/207040496-Cohort-analytics-) reports and group by keywords.

Compare the quality of organic users based on their keywords.
- [Push API](https://support.appsflyer.com/hc/articles/207034356) messages

### Testing organic keyword data

1. Use an [allowlisted](https://support.appsflyer.com/hc/articles/207031996) Android device.
2. Open Chrome browser and go to Google.com.
3. Use a strong keyword to search for your app.

This example uses " **hotels tonight**".

<Image src="https://files.readme.io/b06db96b53df1502939b86cefd7217991d842f1c7e736cab6ba2c6e0de691400-32966747169425.jpg" alt="organic_keywords_search.jpg" />

4. Click _**Install**_ to be redirected to the Google Play Store.
5. Install and launch the app.

<Image src="https://files.readme.io/366e23d3a9b4481d3a5af0889dc73ff4149027b3bf69e115331efa9812aeca0c-Hotels_Tonight_3.png" alt="Hotels_Tonight_3.png" />

6. Search for the keyword in the AppsFlyer sources [described above](https://support.appsflyer.com/hc/articles/115002095726).