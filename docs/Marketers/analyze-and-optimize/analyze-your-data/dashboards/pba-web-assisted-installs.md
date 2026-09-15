---
title: "PBA Web-Assisted Installs"
excerpt: "Use the PBA Web-Assisted Installs dashboard to understand the impact of your web marketing efforts on mobile app installs and to enhance the performance of web campaigns."
---
**Web-Assisted Installs use case**

![web_to_app_image.png](https://files.readme.io/9977aee19e1284e156252cf622fc3770bc730b91e5788c86f4c2977cb101ae36-360009607477.png)

## Web-Assisted Installs analysis

Web-Assisted Installs measures the impact of web marketing efforts to drive users to install an app. Advertisers view web involvement in the context of the install event; they can determine the media source that drove website visitors towards app install. The best results in web-assisted installs is achieved if you set the CUID in the app and on the [website.](https://support.appsflyer.com/hc/articles/360013821097-Onboarding-guide-to-People-Based-Attribution-#2)

### Web-Assisted Installs headline metrics

The headline metrics display the total number of app installs relative to the number of website-assisted installs divided into organic and non-organic app installs.

![WAIHeadline_en-us.png](https://files.readme.io/65310759fd91879aee94495a6ee4736e0e50afa81cfb1935d0f8c2eea6a1d79b-4408021659665.png)

Consider the use-case scenarios, in the table that follows, to Web-Assisted Installs analysis.

| Install type | Journey to install | Considerations |
| --- | --- | --- |
| Total installs | All installs engaging—at some point—with a web media source. | - What is the contribution of web marketing relative to all app installs?<br>- How are web marketing efforts distributed between media sources and channels?<br>- What is the contribution, if any, of Smart Banners? |
| Organic installs | App installs without engaging a mobile media source. | - What portion, if any, of organic installs are driven purely by web traffic?<br>- Which are the dominant media channels? <br>- What is the proportion between paid, owned, and earned media types? |
| Non-organic installs | User journeys begin on the web. The app is installed later after engaging with a mobile campaign. | - What volume of non-organic installs is influenced by the web?<br>- What web media channels and types influence non-organic installs? <br>- Do your paid mobile media sources overlap with web media sources? |

## Web-Assisted Installs dashboard

**To go to the Web-Assisted Installs dashboard:**

<Tabs>
<Tab title="Option 1">

1. In AppsFlyer, from the top menu, select **My Apps** _>_ **View brand bundles**
2. Click PBA dashboard.
3. Go to the **Web-Assisted Installs** tab.

</Tab>
<Tab title="Option 2">

1. In AppsFlyer, from the side menu, select **Analyze** \> **People-based Attribution.**
2. Go to the **Web-Assisted Installs** tab.

</Tab>
</Tabs>

### Website assisted installs and reinstalls

![30day_us-en.png](https://files.readme.io/8ed154e962fb82a6381de81b19e7e4da1b258962427ec48a9e2b86ee576958eb-360009706598.png)

Installs are considered to have been influenced by a website if they occur within 30 days of a website visit. Installs and reinstalls including retargeting installs (reattributions) can be organic or non-organic.

> 📘 Data freshness
>
> For information about data freshness, see [PBA daily](https://support.appsflyer.com/hc/articles/360000310629-Data-freshness-and-time-zone-support#pba-daily).

### Dashboard features

Use dashboard features to:

- Understand and optimize the impact of web traffic campaigns on your app installs.
- Enhance collaboration between non-organic app install campaigns and web marketing.

| Feature | Description |
| --- | --- |
| Date picker & filters | ![Headfilter_us-en.jpg](https://files.readme.io/f86fd4671a8b2013bb2635f8553ba1bcb55bdade079da7ffbe1c5db55c29a832-360009607497.jpg)<br>- Set a date range; it will include app installs during that time.<br>- Filtered data includes the most recent web visit before install.<br>- Learn about [setting filters and groupings.](https://support.appsflyer.com/hc/articles/360007630318) |
| Filters | Filter installs using the web visit, app install, or both using the media source filter. You can set multiple instances of the media source filter.<br>![WebAssistMediaSource.jpg](https://files.readme.io/601e7ebf05da3a01f6d210ebd7fad9b2cc0e38bfe244457b84908e7cca07f2bf-360019757857.jpg)<br>Example: Set the web visit media source filter to Google Search.<br>**To set the media source filter to Google Search:**<br>1. Add + filter type **Media Source**.<br>2. Select **Conversion**.<br>3. Select **Google Search**. |
| Headline metrics | The headline metrics display the number of app installs by attribution source (organic or non-organic).<br>Metrics are broken down by:<br>- Organic: Installs occurring without engaging with a paid mobile media source.<br>  <br>- Non-organic: Installs occurring after engaging with a paid mobile media source. |
| Web media channel | ![W2Amediachannel_us-en.jpg](https://files.readme.io/bb7417b789c5d12dc663794027098343cea3e9f1941dd3bc355c634ca1621518-360009607557.jpg)<br>- Indicates web [media channel](https://support.appsflyer.com/hc/articles/360002386997-Media-source-attribution-rules-in-PBA#media-source-channel) contributions that drove installs.<br>- Apply filters to evaluate the impact of different media channels. |
| Web media source | ![W2Amediasource.jpg](https://files.readme.io/fd623e449a9c47a7cf933c2c760ce98917497db138975082fd677bb0e7d89aa9-360009607577.jpg)<br>Indicates web media source contributions that drove users to install the app. |
| Web-Assisted Installs over time | ![W2Atable.jpg](https://files.readme.io/0b649fb448027a4597140fd86b90f59af76b5a0618d41c8acee35f54152f32f7-360009706658.jpg)<br>Select a view—media source or media channel—to view web activity over time. |
| Installs table | ![WebsiteAttributionTable_us-en.png](https://files.readme.io/be34ee2977015735fd2d83560e2f5559e5fe96c1b74dd99864124af54cc345f1-4402586301585.png)<br>- The table indicates the interaction between the web and mobile media sources.<br>- Metrics, available as a combination of web/mobile media sources, indicate the position of the web media source:  - **Installs:** Number indicates installs whose web media source is considered the last non-direct web visit.<br>  - Select a media source, web or mobile, to drill down to the campaign level. |
| Export CSV | Click **Export CSV** to export the Installs table. |