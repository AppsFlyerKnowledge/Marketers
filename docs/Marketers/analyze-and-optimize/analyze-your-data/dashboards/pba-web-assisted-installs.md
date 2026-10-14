---
title: PBA Web-Assisted Installs
excerpt: >-
  Use the PBA Web-Assisted Installs dashboard to understand the impact of your
  web marketing efforts on mobile app installs and to enhance the performance of
  web campaigns.
metadata:
  keywords:
    - People Based Attribution
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2019-10-03T08:08:37Z'
  edited_at: '2024-04-15T18:14:08Z'
  id: 360002669837
  locale: en-us
  section: Dashboards
  section_id: 6550925337873
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360002669837-PBA-Web-Assisted-Installs
---
**Web-Assisted Installs use case**

![web_to_app_image.png](https://files.readme.io/9977aee19e1284e156252cf622fc3770bc730b91e5788c86f4c2977cb101ae36-360009607477.png)

## Web-Assisted Installs analysis

Web-Assisted Installs measures the impact of web marketing efforts to drive users to install an app. Advertisers view web involvement in the context of the install event; they can determine the media source that drove website visitors towards app install. The best results in web-assisted installs is achieved if you set the CUID in the app and on the [website.](/docs/onboarding-guide-to-people-based-attribution#2) 

### Web-Assisted Installs headline metrics

The headline metrics display the total number of app installs relative to the number of website-assisted installs divided into organic and non-organic app installs.

[![WAIHeadline_en-us.png](https://files.readme.io/65310759fd91879aee94495a6ee4736e0e50afa81cfb1935d0f8c2eea6a1d79b-4408021659665.png)](https://files.readme.io/65310759fd91879aee94495a6ee4736e0e50afa81cfb1935d0f8c2eea6a1d79b-4408021659665.png)

Consider the use-case scenarios, in the table that follows, to Web-Assisted Installs analysis.

| Install type | Journey to install | Considerations |
| --- | --- | --- |
| Total installs | All installs engaging—at some point—with a web media source. | <ul><li>What is the contribution of web marketing relative to all app installs?</li><li>How are web marketing efforts distributed between media sources and channels?</li><li>What is the contribution, if any, of Smart Banners?</li></ul> |
| Organic installs | App installs without engaging a mobile media source. | <ul><li>What portion, if any, of organic installs are driven purely by web traffic?</li><li>Which are the dominant media channels?</li><li>What is the proportion between paid, owned, and earned media types?</li></ul> |
| Non-organic installs | User journeys begin on the web. The app is installed later after engaging with a mobile campaign. | <ul><li>What volume of non-organic installs is influenced by the web?</li><li>What web media channels and types influence non-organic installs?</li><li>Do your paid mobile media sources overlap with web media sources?</li></ul> |

## Web-Assisted Installs dashboard

**To go to the Web-Assisted Installs dashboard:**

| Option 1 | Option 2 |
| --- | --- |
| <ol><li>In AppsFlyer, from the top menu, select **My Apps** *>* **View brand bundles**</li><li>Click PBA dashboard.</li><li>Go to the **Web-Assisted Installs** tab.</li></ol> | <ol><li>In AppsFlyer, from the side menu, select **Analyze** > **People-based Attribution.**</li><li>Go to the **Web-Assisted Installs** tab.</li></ol> |

<div id="website-assisted-installs-and-reinstalls" />

<Accordion title="Website assisted installs and reinstalls">

![30day_us-en.png](https://files.readme.io/8ed154e962fb82a6381de81b19e7e4da1b258962427ec48a9e2b86ee576958eb-360009706598.png)

Installs are considered to have been influenced by a website if they occur within 30 days of a website visit. Installs and reinstalls including retargeting installs (reattributions) can be organic or non-organic.

For information about data freshness, see [PBA daily](/docs/about-data-freshness-and-timezone-support#pba-daily).

</Accordion>

<div id="dashboard-features" />

<Accordion title="Dashboard features">

Use dashboard features to:

* Understand and optimize the impact of web traffic campaigns on your app installs.
* Enhance collaboration between non-organic app install campaigns and web marketing.

| Feature | Description |
| --- | --- |
| Date picker & filters | ![Headfilter_us-en.jpg](https://files.readme.io/f86fd4671a8b2013bb2635f8553ba1bcb55bdade079da7ffbe1c5db55c29a832-360009607497.jpg)<ul><li>Set a date range; it will include app installs during that time.</li><li>Filtered data includes the most recent web visit before install.</li><li>Learn about [setting filters and groupings.](/docs/using-pba-dashboards)</li></ul> |
| Filters | Filter installs using the web visit, app install, or both using the media source filter. You can set multiple instances of the media source filter.<br /><br />![WebAssistMediaSource.jpg](https://files.readme.io/601e7ebf05da3a01f6d210ebd7fad9b2cc0e38bfe244457b84908e7cca07f2bf-360019757857.jpg)<br /><br />Example: Set the web visit media source filter to Google Search.<br /><br />**To set the media source filter to Google Search:**<ol><li>Add + filter type **Media Source**.</li><li>Select **Conversion**.</li><li>Select **Google Search**.</li></ol> |
| Headline metrics | The headline metrics display the number of app installs by attribution source (organic or non-organic).<br /><br />Metrics are broken down by:<ul><li>Organic: Installs occurring without engaging with a paid mobile media source.</li><li>Non-organic: Installs occurring after engaging with a paid mobile media source.</li></ul> |
| Web media channel | [![W2Amediachannel_us-en.jpg](https://files.readme.io/bb7417b789c5d12dc663794027098343cea3e9f1941dd3bc355c634ca1621518-360009607557.jpg)](https://files.readme.io/bb7417b789c5d12dc663794027098343cea3e9f1941dd3bc355c634ca1621518-360009607557.jpg)<ul><li>Indicates web [media channel](/docs/pba-media-source-attribution-rules#media-source-channel) contributions that drove installs.</li><li>Apply filters to evaluate the impact of different media channels.</li></ul> |
| Web media source | [![W2Amediasource.jpg](https://files.readme.io/fd623e449a9c47a7cf933c2c760ce98917497db138975082fd677bb0e7d89aa9-360009607577.jpg)](https://files.readme.io/fd623e449a9c47a7cf933c2c760ce98917497db138975082fd677bb0e7d89aa9-360009607577.jpg)<br /><br />Indicates web media source contributions that drove users to install the app. |
| Web-Assisted Installs over time | [![W2Atable.jpg](https://files.readme.io/0b649fb448027a4597140fd86b90f59af76b5a0618d41c8acee35f54152f32f7-360009706658.jpg)](https://files.readme.io/0b649fb448027a4597140fd86b90f59af76b5a0618d41c8acee35f54152f32f7-360009706658.jpg)<br /><br />Select a view—media source or media channel—to view web activity over time. |
| Installs table | [![WebsiteAttributionTable_us-en.png](https://files.readme.io/be34ee2977015735fd2d83560e2f5559e5fe96c1b74dd99864124af54cc345f1-4402586301585.png)](https://files.readme.io/be34ee2977015735fd2d83560e2f5559e5fe96c1b74dd99864124af54cc345f1-4402586301585.png)<ul><li>The table indicates the interaction between the web and mobile media sources.</li><li>Metrics, available as a combination of web/mobile media sources, indicate the position of the web media source:<ul><li>**Installs:** Number indicates installs whose web media source is considered the last non-direct web visit.</li><li>Select a media source, web or mobile, to drill down to the campaign level.</li></ul></li></ul> |
| Export CSV | Click **Export CSV** to export the Installs table. |

</Accordion>

<div data-zendesk-anchors="webassisted-installs-analysis=web-assisted-installs-analysis h_01HJR78C5VWASD9M52NR43DKG6=web-assisted-installs-analysis webassisted-installs-headline-metrics=web-assisted-installs-headline-metrics h_01HJR78C5VXJPYP6P2A6BKGVN2=web-assisted-installs-headline-metrics webassisted-installs-dashboard=web-assisted-installs-dashboard h_01HJR78C5WQGENPBB5EBMHJ383=web-assisted-installs-dashboard h_01HJR78C5XY39JFNWRYNP3CR65=website-assisted-installs-and-reinstalls h_01HJR78C5X4AEEX0S34YY08XF6=dashboard-features" />
