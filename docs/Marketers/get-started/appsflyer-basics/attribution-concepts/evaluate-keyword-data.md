---
title: Evaluate Keyword data
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2023-07-25T08:19:25Z'
  edited_at: '2026-06-11T08:43:58Z'
  id: 17255366785553
  locale: en-us
  section: Attribution concepts
  section_id: 6551394235409
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/17255366785553-Evaluate-Keyword-data
---
> **At a glance:** Get detailed keyword data that lets you see which search terms are most popular, so you can optimize organic conversions.

## Keyword data

Organic search is a valuable traffic source for your apps. Organic users don't incur acquisition costs and are usually among the most engaged cohorts.

With a few tweaks to your app page, it is possible to increase the amount of new organic installs. To optimize organic searches, you need to get organic keyword data for your app.

### iOS keywords

If you work with Apple Ads, you can get <Anchor target="_blank" href="/marketers/docs/apple-ads-integration-setup#get-keyword-data">detailed keyword data</Anchor> for your **non-organic** users attributed to Apple Ads. In iOS, **organic** keyword data is not available.

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
  Go to <Anchor target="_blank" href="/marketers/docs/pivot-table-user-metrics">Pivot</Anchor>, <Anchor target="_blank" href="/marketers/docs/cohort-and-retention-dashboard">Retention, and Cohort</Anchor> reports and group by keywords.  
  Compare the quality of organic users based on their keywords.
* <Anchor target="_blank" href="/marketers/docs/push-api-streaming-raw-data">Push API</Anchor> messages

### Testing organic keyword data

1. Use an <Anchor target="_blank" href="/marketers/docs/registering-test-devices">allowlisted</Anchor> Android device.
2. Open Chrome browser and go to Google.com.
3. Use a strong keyword to search for your app.   
   This example uses "**hotels tonight**".  
     
   [<Image alt="organic_keywords_search.jpg" src="https://files.readme.io/b06db96b53df1502939b86cefd7217991d842f1c7e736cab6ba2c6e0de691400-32966747169425.jpg" width="426px" />](https://files.readme.io/b06db96b53df1502939b86cefd7217991d842f1c7e736cab6ba2c6e0de691400-32966747169425.jpg)
4. Click ***Install*** to be redirected to the Google Play Store.
5. Install and launch the app.  
   [<Image alt="Hotels_Tonight_3.png" src="https://files.readme.io/c455f8229ba7879157eec6782d0eb2d94a91e1080a3c081f5452cc7e92608047-205710046.png" width="373px" />](https://files.readme.io/c455f8229ba7879157eec6782d0eb2d94a91e1080a3c081f5452cc7e92608047-205710046.png)
6. Search for the keyword in the AppsFlyer sources described above.

<div data-zendesk-anchors="h_01HKA1D1TW1R20X6K05Q9GX904=keyword-data h_01HKA1D1TW9YXBMGERHW4EHZZN=ios-keywords h_01HKA1D1TWT1VQ6NZ789BTCZJX=android-keywords h_01HKA1D1TW7E2RM7SXC9R5SA99=note using-the%C2%A0keyword%C2%A0data=using-thekeyworddata h_01HKA1D1TWRPGTNGJKF7T1R71B=using-thekeyworddata testing-organic%C2%A0keyword%C2%A0data=testing-organickeyworddata h_01HKA1D1TW5W9A72V2NMPX932H=testing-organickeyworddata" />
