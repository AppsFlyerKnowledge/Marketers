---
title: "Evaluate Keyword data"
excerpt: "Get detailed keyword data that lets you see which search terms are most popular, so you can optimize organic conversions."
x-zendesk:
  id: 17255366785553
  url: https://support.appsflyer.com/hc/en-us/articles/17255366785553-Evaluate-Keyword-data
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Attribution concepts
  section_id: 6551394235409
  position: 25
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-moran-davida, Marketers, Mobile Attribution]
  labels: [Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2023-07-25T08:19:25Z'
  edited_at: '2026-06-11T08:43:58Z'
---
## Keyword data

Organic search is a valuable traffic source for your apps. Organic users don't incur acquisition costs and are usually among the most engaged cohorts.

With a few tweaks to your app page, it is possible to increase the amount of new organic installs. To optimize organic searches, you need to get organic keyword data for your app.

### iOS keywords

If you work with Apple Ads, you can get [detailed keyword data](/docs/apple-ads-integration-setup#get-keyword-data) for your **non-organic** users attributed to Apple Ads. In iOS, **organic** keyword data is not available.

### Android keywords

Google shares organic keyword data (on the Referrer URL) for users that do the following:

* Use Android devices
* Use Chrome browser
* Visit Google.com and perform a search
* Install an app from the Google results page
* Launch the app

The SDK extracts the keywords when provided by Google in the *&utm\_term* parameter of the referrer if it is part of the link to Google Play. The values where possible are contained in the following AppsFlyer raw data fields: *http\_referrer*, g*p\_broadcast\_referrer*, *keywords.*

**Expect that less than 1% of organic Android users follow this funnel and have organic keyword data**.

In other scenarios, Google does not share organic keyword data. For example, users searching in Google Play don't have organic keyword data.

> 📘 **Note**
>
> This limitation is applied by Google to all external vendors, including all attribution vendors.

### Using the keyword data

Organic keyword data is found in the following:

* **Raw organic data reports**  
  In AppsFlyer, from the side menu, select **Export** > **Raw Data Export** to view the breakdown of used organic keywords.
* **Advanced reports**   
  Go to [Pivot](/docs/pivot-table-user-metrics), [Retention, and Cohort](/docs/cohort-and-retention-dashboard) reports and group by keywords.  
  Compare the quality of organic users based on their keywords.
* [Push API](/docs/push-api-streaming-raw-data) messages

### Testing organic keyword data

1. Use an [allowlisted](/docs/registering-test-devices) Android device.
2. Open Chrome browser and go to Google.com.
3. Use a strong keyword to search for your app.   
   This example uses "**hotels tonight**".  
     
   [![organic_keywords_search.jpg](https://files.readme.io/b06db96b53df1502939b86cefd7217991d842f1c7e736cab6ba2c6e0de691400-32966747169425.jpg)](https://files.readme.io/b06db96b53df1502939b86cefd7217991d842f1c7e736cab6ba2c6e0de691400-32966747169425.jpg)
4. Click ***Install*** to be redirected to the Google Play Store.
5. Install and launch the app.  
   [![Hotels_Tonight_3.png](https://files.readme.io/c455f8229ba7879157eec6782d0eb2d94a91e1080a3c081f5452cc7e92608047-205710046.png)](https://files.readme.io/c455f8229ba7879157eec6782d0eb2d94a91e1080a3c081f5452cc7e92608047-205710046.png)
6. Search for the keyword in the AppsFlyer sources described above.