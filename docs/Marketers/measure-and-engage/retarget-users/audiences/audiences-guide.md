---
title: "Audiences guide"
excerpt: "Increase the efficiency of your user acquisition and remarketing campaigns by using AppsFlyer Audiences to build and connect audience segments to your partner networks."
x-zendesk:
  id: 115002689186
  url: https://support.appsflyer.com/hc/en-us/articles/115002689186-Audiences-guide
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Audiences
  section_id: 6551336428945
  position: 1
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11085
  content_tags: [pm-neama-benhabib, Marketers, Audience Segmentation]
  labels: [Audiences, Advertisers, Premium, Premium Feature, Marketers, Loc Published]
  promoted: true
  comments_disabled: true
  created_at: '2017-05-30T07:21:22Z'
  edited_at: '2026-05-31T10:25:39Z'
---
![Intro_image.png](https://files.readme.io/645503f41e6a76c854c62236fc279be591849879790d02001eafc75f0d1a974a-30258966500753.png)

## Audiences basics

AppsFlyer Audiences lets you easily build audience segments and connect them to your owned and paid channels—so you can deliver tailored campaigns for better engagement and performance. And once your campaign’s been sent, you can view performance metrics in Audiences as well.

An audience is a segment of current or past users of your app that meet the specific criteria that you define. Audiences can be based on personal characteristics, behavior, in-app activity, attribution source, revenue generated, geographic location, device type, and more.

**Step 1 - Build your audience in AppsFlyer:** You can build a custom audience from scratch, import one, or select from our ready-made, fully customizable list of “Suggested Audiences”, which save you time and are based on industry best practices.

**Step 2 - Connect the audience:** Once you’ve built your audience, the next step is connecting it to your media partners from within AppsFlyer, which sends identifiers for the members of that audience to the partners and creates the audience on the partners’ systems. This enables them to serve specific ads only to these users. Audiences are automatically refreshed and pushed to partners once daily. Additionally, you can upload an audience to 3rd-party services such as Amazon S3 buckets, or download it as a CSV file right from the dashboard.

All the information needed to upload audience data to a media partner is specified in a partner connection. You can have multiple connections for a single media partner (using different accounts, login information, etc.). In order to enable compliance with the privacy requirements of iOS 14.5 and other user privacy considerations, **Audiences allows you full control to determine which identifiers are shared with partners**, both at the account level and for each partner connection.

### Audience split and Incrementality testing

[Incrementality](/docs/incrementality-for-remarketing-overview) testing measures the real impact of your campaigns with A/B testing that accurately measures “incremental lift”—the difference between conversions that happened as a result of your marketing campaigns and those that would have happened anyway. AppsFlyer Audiences sets the stage for testing with an optional feature that splits the audience among selected media partners and a control group, so you can use the Incrementality dashboard to understand the true value of your campaigns.

## Get started

Follow these steps to get started with Audiences:

|  | Steps |
| --- | --- |
| 1 | In AppsFlyer, from the side menu, select **Engage** > **Audiences**<br /><br />**Note:** Audiences is a premium feature. If you need help getting started, reach out to your customer success manager, or write to [hello@appsflyer.com](mailto:hello@appsflyer.com) |
| 2 | Set account-level [policy](/docs/audiences-user-identifier-policy) for sharing user identifiers with partners |
| 3 | Create a new audience:<ul><li>[Custom Audience](/docs/audiences-guide#create-a-custom-audience) - Build your audience from scratch</li><li>[Suggested Audience](/docs/audiences-guide#create-a-suggested-audience) - Ready-made, customizable audiences that are based on industry best practices</li><li>[Import audience](/docs/audiences-import-audience-segments-from-internal-systems) - Import audience segments from your internal systems (such as BI or CRM)</li></ul> |
| 4 | Connect the audience to one or more media partners |
| Optional | [Split the audience among partners and a control group](/docs/audiences-guide#audience-split-and-control-groups) |
| Optional | [Import <span id="user-attributes"></span>user attributes](/docs/audiences-create-better-audiences-with-user-attribute-data) |

## Create and manage audiences

This section describes how to create and manage audiences and set up Incrementality testing.

<div id="create-a-custom-audience" />

<Accordion title="Create a Custom Audience">

A Custom Audience is built from scratch using any rulesets and filters you wish.

**To create a Custom Audience:**

1. In AppsFlyer, from the side menu, select **Engage** > **Audiences**.
2. Click **New audience**.
3. Select **Custom audience**.  
   The **Build** tab displays.
4. Enter a unique **Audience name**.  
   **Note:** Audience names can't include special characters (" ’ # % & * + / : ; `< = >` ? ( ) [ ] `{ }` \ | ~)
5. Select the platform: **Android** or **iOS**.
6. Select the [user identifier](/docs/audiences-guide#user-identifier-device-id-vs-customer-id):
7. [Default] **Device ID**: Evaluates rules by device ID only.
8. **Customer ID**: Evaluates rules by grouping devices using the CUID (use this method only after you verify that your data has valid CUIDs.)
9. Select **New ruleset**, or if you wish to add the users of an existing audience, click **Existing audience**then select the specific audience from the list.
10. Build the audience guided by the user interface. For specific information about rule options, see [All about rulesets](/docs/audiences-guide#all-about-rulesets).
11. Combine rulesets using the operators and, or, exclude.
12. As you build your audience, the panes on the right side automatically update the estimated audience and per-partner upload sizes.
13. Complete defining the audience, then click **Next.**  
    The **Audience connection** window appears. This is where you [connect the audience to your media partners](/docs/audiences-guide#connect-an-audience-to-media-partners).

> 📘 **Notes**
>
> * You can have up to 100 active Custom/Suggested audiences at a time.
> * Audience names may be visible on your connected media partner sites. Do not include sensitive information in names.

</Accordion>

<div id="create-a-suggested-audience" />

<Accordion title="Create a Suggested Audience">

Suggested Audiences enable you to explore and discover **ready-made audience segments, that are based on industry best practices.** You can select an audience, customize it, and connect it with your partner networks for optimally targeted marketing campaigns.

Choose from over 30+ audiences within the **categories of Acquire, Activate, Engage, Monetize, and industry-specific audiences.** The audiences are 100% customizable, so you can create the exact audience you need. Audiences include:

* Convert ad clicks into installs
* Get lookalikes
* Suppression lists
* Encourage registration
* Encourage purchase
* Monetize purchasers
* And a lot more…

> 📘 **Example use case**
>
> This example illustrates one typical use case. Let’s say you want to urge active users of your app, who haven’t purchased yet, to make their first purchase. You can select the “Encourage purchase” audience and customize it to specify which event defines an in-app purchase. Then you can connect the audience to your partners and run a promotional campaign that nudges them towards making a purchase and leads them to the app's purchase page.
>
> ![Encourage_purchase_image_this_one.jpeg](https://files.readme.io/8b49590a0c97707bd4a0b151d30cc48183e15ffb13d2d4e9ee25d522de71846c-30259018203153.jpg)

**To create a Suggested Audience:**

1. In AppsFlyer, from the side menu, select **Engage** > **Audiences**.
2. Click **New audience**.
3. Select **Suggested audience**.
4. Select the app.
5. Browse through the various categories and select an audience that matches your goals.   
   **Note:** Some audiences require you to add the specific [in-app events](/docs/in-app-events-overview) to define the audience criteria. If the AppsFlyer [predefined event](/docs/in-app-events-event-structure#predefined-event-names) has already been configured in your app, it will be pre-selected. If not, you'll need to select the appropriate custom event from the dropdown menu. ![Select_an_event__1_.jpeg](https://files.readme.io/b5055ca61791f15efc3a91f3f2d749e1df9e3f5e8b956b9167e186474de57ac4-30258966520721.jpg)
6. Click **Select & customize**.
7. Enter a unique **Audience name**.  
   **Note:** Audience names can't include special characters (" ’ # % & * + / : ; `< = >` ? ( ) [ ] `{ }` \ | ~)
8. Select the platform: Android or iOS.
9. Select the [user identifier](/docs/audiences-guide#user-identifier-device-id-vs-customer-id):
   * [Default] **Device ID**: Evaluates rules by device ID only.
   * **Customer ID**: Evaluates rules by grouping devices using the CUID (use this method only after you verify that your data has valid CUIDs.)
10. If you wish to further customize the audience by adding additional [rulesets](/docs/audiences-guide#all-about-rulesets), you can do so if you wish by clicking **+ Filter**. When done, click **Next**.   
    The **Audience connection** window appears. This is where you [connect the audience to your media partners](/docs/audiences-guide#connect-an-audience-to-media-partners).

> 📘 **Notes**
>
> * You can have up to 100 active Custom/Suggested audiences at a time.
> * Audience names may be visible on your connected media partner sites. Do not include sensitive information in names.

</Accordion>

<div id="import-an-audience" />

<Accordion title="Import an audience">

You can [import predefined audience segments](/docs/audiences-import-audience-segments-from-internal-systems) from your internal systems (such as BI and CRM) to AppsFlyer Audiences, and use it as your central point for connecting and maintaining all of your audience segments with your advertising partners. Additionally, it allows you to enjoy Audiences features, such as identifier matching/data enrichment and connected campaign metrics.

</Accordion>

<div id="connect-an-audience-to-media-partners" />

<Accordion title="Connect an audience to media partners">

Once you've defined your audience, the next step is connecting it to your media partners.

**To connect your audience to media partners:**

1. After defining your new audience on the audience **Build** page, click **Next**. The **Audience connection** window appears.
2. Click **+ Partner connection**, then do one of the following:
   * **To add a new connection**, click **+ Add partner connection** (see the [Create a new connection](/docs/audiences-guide#create-a-new-connection) section below for detailed instructions).
   * **To select from existing connections:**
     1. Search for the partner connection.
     2. Select one or more existing connections.
     3. Click **Save**.  
        The Audience connection window opens.
     4. [Optional] [Split an audience between partners and a control group](/docs/audiences-guide#audience-split-and-control-groups)
     5. [Optional] [Copy split groups to S3](/docs/audiences-guide#audience-split-and-control-groups).
3. Click **Save**.  
   Once connected, the audience is updated and pushed to partners daily.

</Accordion>

<div id="user-identifier-device-id-vs-customer-id" />

<Accordion title="User identifier—Device ID vs. Customer ID">

Audience rule evaluation is performed using an app user identifier. Select from:

* [Default] **Device ID:** Ruleset compliance is assessed using the device ID (GAID or IDFA/IDFV). When compliant with the ruleset, the device ID is added to the audience list. **Note:** The device ID will be shared with partners only when permitted by your user identifier policy.
* [**Customer ID (CUID)**](/docs/customer-user-id-field-cuid):
  * Ruleset compliance is assessed by grouping all device IDs associated with the same CUID. If the group complies with the ruleset, then the device IDs comprising the group are added to the audience. **Note**: The CUID itself is not part of the audience list and is not sent to media partners.
  * CUID implementation considerations:
    * Ensure that your data is populated with valid CUIDs.
    * App users (devices) without a CUID are ignored.
    * When a device ID is matched to a CUID, historical audience data for the user is updated retroactively and included in audience builds going forward. **Note**: No change is made to raw data.
    * If a device ID is associated with two different CUIDs, the most recently associated CUID is used.
    * When building an audience with CUID as the identifier, the CUID association must have been received by AppsFlyer on the install (not just on post-install events) for complete association with the relevant devices and successful enrichment with device identifiers (i.e., GAID, IDFA). [Learn more](/docs/customer-user-id-field-cuid#setting-the-cuid)

![CuidExaplainded_us-en.jpg](https://files.readme.io/d40309ab2fd34a4862b9c089ac2fade2f5642973fc4d4977da66f1ee6bf1e390-30258966523921.jpg)

> 📘 **Example: Device ID vs. CUID**
>
> An audience of users who spent more than $5
>
>
>
> | Advertising  <br />ID | CUID | Purchase $ |
> | --- | --- | --- |
> | A | 99 | 1 |
> | A | 99 | 2 |
> | B | 77 | 1 |
> | B | 77 | 5 |
> | C | 99 | 3 |
> | D | None | 50 |
>
>
>
> | Rule evaluated by | Device IDs included in the audience | Explanation |
> | --- | --- | --- |
> | Device ID | B, D | A and C are not included - the spend was less than $5 |
> | CUID | A, B, C | * A and C have the same CUID (99) - the combined spend is $6.<br />* D is ignored - there is no CUID |
>
>
> <br /><br />**Note**<br />>
> #### Note
>
> The same method of summing spend across device IDs grouped by CUID, shown in the example above, also applies to other numerical attributes (for example, scoring).

</Accordion>

<div id="audience-split-and-control-groups" />

<Accordion title="Audience split and control groups">

Use the toggle that splits the audience among partners and a control group to effortlessly set the stage for A/B testing and [Incrementality measurement](/docs/incrementality-for-remarketing-overview) so you can get the crucial insights you need about campaign impact. When enabled, the feature randomly splits the audience among your selected partners and a control group. The control group is the portion of the audience that is held back from partners and is a necessary requirement for Incrementality measurement. You can adjust any of the split percentages you wish and disable or re-enable the split per audience.

| Feature | Description |
| --- | --- |
| Split audience | <ul><li>This feature randomly splits the audience among your selected partners and a control group. **It is enabled by default for Incrementality subscribers**, and can easily be disabled or re-enabled at any time.</li><li>Split audiences for a variety of reasons, such as A/B testing and Incrementality measurement.</li><li>**Note:** Modifying an existing split allocation between partners causes redistribution of the entire audience. This may negatively impact the validity of A/B testing and will cause active Incrementality experiments to end and restart as new experiments.</li></ul> |
| Control group | A portion of the audience is held back in a control group, which is not sent to any partner:<ul><li>Control groups are used in A/B testing and to measure the incremental lift of your marketing campaigns.</li><li>15% of the audience (or higher) is recommended for an effective control group.</li><li>The minimum control group % needed to run an Incrementality experiment is 1%.</li></ul> |
| Send a copy of split lists to an S3 bucket | CSV files containing the split audience lists and control group can be sent to an Amazon S3 bucket.<ul><li>**Note**: This is not the same as defining Amazon S3 as a connected partner.</li><li>The audience lists can be downloaded to a CSV file. Use the CSV file, for example, to send to partners who are not integrated with AppsFlyer.</li></ul> |

**To split the audience and perform other partner actions:**

1. In the AppsFlyer left-side panel, go to **Engage** > **Audiences**.
2. In the **Audiences** tab, select the audience.
3. Go to the **Connect** tab.  
   [![audience_split_1200px.png](https://files.readme.io/1a9decaea5f77ec36c111a132c12733cfa44bb1e87c6515e71843e6c7fcabfee-46335667595281.png)](https://files.readme.io/1a9decaea5f77ec36c111a132c12733cfa44bb1e87c6515e71843e6c7fcabfee-46335667595281.png) The current settings display:
   * The top, right-side pane displays estimated total audience and upload sizes (for all partners)
   * The bottom, right-side presents a visualization of:
     * Estimated upload size for each partner
     * Partner overlap (for audiences that aren't split)
4. Take any of the following actions:

| Action | Procedure |
| --- | --- |
| Split an audience between partners and control group | <ol><li>Make sure the **Split audience/Measure incremental impact** toggle is enabled.<ul><li>The total of the control group and split to partners combined must be 100%.</li><li>If you don't want to include the control group in the split: allocate 0%.</li><li>All connected partners must be allocated a portion of the split (Don't allocate a partner 0%)</li><li>To view the total allocated: scroll down; the total percent split displays.</li></ul></li><li>Enter the percentage allocated to:<ul><li>**Control group -** 15% or higher is recommended.</li><li>Enter a split percentage per connection.</li><li>Scroll down to display the total allocation in percent, and make sure that the total allocation is 100%.</li><li>Click **Save split**.</li><li>Click **Save**.</li></ul></li></ol> |
| Copy split groups to S3 | **To send a copy of the audience split list to an S3 bucket:**<ol><li>Click **Copy split groups to S3.**</li><li>Select a connection.</li><li>Click **Save**.</li></ol>Files are sent using the following directory and filename structure:<ul><li>**Directory**:</li></ul>```<br />\YYYY-MM-DD\audienceID_audienceName_timestamp\<br />```<ul><li>**Filename**: the name of the partner or control group<br />Note: If the connection to the partner fails, and the file is not uploaded, the word **failed** will be appended to the partner name (for example, *partner\_name\_failed.csv*)</li></ul> |
| Create and add a new connection | **To create a new connection:**<ol><li>Click **Add** **partner** **connection.**</li><li>Type a connection name.</li><li>Select a partner.</li><li>Complete the process according to the instructions in the user interface.</li><li>Click **Add partner connection.**</li></ol> |
| Add or remove an existing connection | **To remove or add an existing connection:**<ol><li>Hover over the partner connection.</li><li>Click the "Remove" icon.</li><li>Click **Save**.</li></ol> |

</Accordion>

<Accordion title="Manage audiences">

**To manage audiences from the Audiences dashboard:**

1. In the AppsFlyer left-side panel, go to **Engage** > **Audiences**.
2. The following options are available:

| Option | Description |
| --- | --- |
| Create a new audience | Create a new audience |
| Change audience settings | Click an **Audience name,** do one of the following:<ul><li>In the **Build** tab: View and change rulesets.</li><li>In the **Connect** tab: Set audience split and control group options.</li></ul> |
| Actions | In the  ![3_dots_icon.png](https://files.readme.io/e1b296a694e4803662b2d3776ce001f981e44ada6d3f7552974417b3d6fc7169-46335625061649.png)  icon that appears on the right when hovering over an audience on the main Audiences page:<ul><li>**View history**: Displays the audience upload history including audience size, and split between partners.</li><li>**Upload now**: Sends the audience to connected partners.</li><li>**Download as CSV**:<ul><li>Generates and downloads the audience list as CSV files(s) that include the identifiers you select. Only data that complies with your [user identifier policy](/docs/audiences-user-identifier-policy) will be downloaded.</li><li>One file is generated for each partner.</li><li>The file(s) are downloaded after calculation of the audience, which can take some time after you create or modify an audience.</li><li>Downloaded files are limited to 5 million records. For larger files, send the file to an [S3 bucket](/docs/audiences-partner-connections#amazon-s3).</li><li>Only an audience that is connected to partner networks will be updated daily and kept current. If the audience is not connected to partner networks, it will not be kept current beyond the audience creation date. If you want to download the most current info, you can duplicate the audience to recreate it (see below), then download the CSV from the duplicated audience.</li></ul></li><li>**Duplicate**:<ul><li>Copies the audience definition.</li><li>When you duplicate an audience, give it a unique name.</li><li>[Option] Remove one or more of the connected partners during duplication.</li></ul></li><li>**Calculate now**: [For imported audiences] Recalculates the number of users in an audience. Use as needed to refresh the audience size if it does not look correct.</li><li>**Pause:**</li></ul><ul><li>Pausing the audience inactivates it so that it no longer gets calculated and uploaded to connected partners (existing audience data from the past 3 years is retained).</li><li>You can pause audiences you don't use to keep within the allowed maximum number of active audiences. You can have up to 100 active Custom/Suggested audiences and up to 500 active imported audiences at a time.</li></ul>**To pause an audience:**<ol><li>Hover over the audience on the main Audiences page so that the  ![3 dots icon.png](https://files.readme.io/e1b296a694e4803662b2d3776ce001f981e44ada6d3f7552974417b3d6fc7169-46335625061649.png) (Actions menu) icon appears on the right.</li></ol>![Actions menu.jpg](https://files.readme.io/d7ad8445c7e886ef4669155391419c9bb5538552f9a0bc1dabaa85a4ad819a1e-46335625065873.jpg)<ol><li>Click the icon and select **Pause**.</li></ol>The audience is now paused.<br /><br />You can also pause multiple audiences at once by checking the box next to the audiences and then clicking **Pause** which will appear on the upper right.<ul><li>**Delete:** Permanently deletes the audience.</li></ul> |
| Bulk actions | Carry out the same action on multiple audiences. To use bulk actions, select two or more audiences, then select one of the following bulk actions:<ul><li>**Upload now**</li><li>**Show audience overlap**: displays the audience overlap between the selected audiences</li><li>**Delete**</li></ul> |

</Accordion>

## All about rulesets

Learn how to use rulesets to define your audiences.

<Accordion title="Audience segmentation rulesets">

![audience_segmentation_rulesets.jpg](https://files.readme.io/4407da232d372a98afcd30df3a832f6ef38bb55a6b02640587f44c7501b014f2-46335625066897.jpg)

* An audience segment ruleset consists of one or multiple rules to enable precision filtering.
* Combine rulesets using operators: and, or, exclude.
* As rules are defined and layered, the estimated audience size displays in real-time.
* Rulesets can be duplicated by clicking the ![duplicate_icon.png](https://files.readme.io/c4e2321280c4141e70c499adc92837d663fd29942b1c88532c6f2f3327efc400-46335667603729.png) icon.
* Where an audience consists of multiple rulesets, use the overlap visualization display to better understand your audience segments.
* The [user identifier](/docs/audiences-guide#user-identifier-device-id-vs-customer-id) used to evaluate rules is either the device ID [default] or the customer user ID (CUID).

The examples that follow illustrate ruleset implementation in various scenarios.

</Accordion>

<Accordion title="Ruleset examples">

> 📘 **Example: Location-based rule**
>
> Users from New York who uninstalled the app in the last month
>
> ![example_location_based_rule.jpg](https://files.readme.io/7ee7e2b9e8f06dc47c93148767fd67d87855a05cd09ba06f2dd2c0ea9dc29607-46335625068817.jpg)

> 📘 **Example: User attributes-based rule**
>
> Users who launched the app in the last 7 days at least once and whose favorite weapon is a sword.
>
> ![example_user_attributes_based_rule.jpg](https://files.readme.io/8ab97cdccd2a1b33b671b1f686ca642306197ccf5151ca2ba9836db8ca496d03-46335625073809.jpg)

> 📘 **Example: Revenue**
>
> Users who installed the app during the last seven days, and spent $1
>
> ![example_revenue.jpg](https://files.readme.io/d7768bec78ff5981639da4e1c8e1a3121961464c0a5932bf8f542f27979358a8-46335625074833.jpg)

> 📘 **Example: Owned media filter**
>
> Build targeted audiences consisting of users who were attributed to specific owned media sources such as social media (excluding paid advertising), SMS, email, referrals, web, or QR codes. You can also choose your level of granularity and target users who came from a specific media source, campaign, ad set, or individual ad.
>
> Here's an example with users who launched the app at least once in the last 7 days and whose install was attributed to a specific email campaign as well as specific ad sets and ads.
>
> ![Owned_media_example.jpg](https://files.readme.io/4b9c076f5299f4f59524a7f816964f4db2c8edd73690aa899e34fcac0d145628-46335667611409.jpg)
>
> The audience can be used to re-engage these users with personalized messaging on either owned or paid media, or as an exclusion list to prevent them from seeing irrelevant or unnecessary ads when running campaigns.

> 📘 **Example: Remarketing**
>
> Using clicks and views for effective remarketing. To convert these users, a little extra convincing or a gentle reminder is needed. These users have a high probability of converting so remarketing to them can produce significantly better results than advertising to new segments. Create precise audiences for remarketing based on clicks and impressions data collected.
>
> Build an audience of potential users that clicked on an ad but did not install in the last two days.
>
> ![example_remarketing.jpg](https://files.readme.io/715c42d56c0deffdb4d28acd213f4a5da62de75bbcd6834a927b9226d2fea43e-46335667613329.jpg)
>
> These are users who, in the recent past, were sufficiently interested in your mobile app to click on your ad, but for some reason did not install the app, or installed the app but did not launch it. Some users just need a reminder (push) to install it. Others may need to see more screens or features of your app to finally convert. Therefore, if you have a primary creative you use on new audiences, it might be better to use a different creative for audiences that clicked but did not install.

</Accordion>

<div id="h_01HBQMA61AEKT6N97SJBW4B01C" />

<Accordion title="Ruleset filters">

* A ruleset consists of one or multiple rules.
* There are various ruleset filter categories such as Events, Revenue, Geo, Attribution, User attributes, Devices, and Owned media.
* Rules have different parameters and settings, as listed in the table below.

<table><tbody><tr><td colspan="3"><h4>Events</h4><p><img alt="engagement_filter_with_A___B.jpg" src="https://files.readme.io/ea3063532ff666f6d8a0f90d55c86007d8a54b25017d93ed7bc19e0d727d9193-46335625077777.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Viewed an ad</li><li>Clicked an ad</li><li>Installed the app</li><li>Did not install the app</li><li>Launched the app</li><li>Did not launch the app</li><li>Uninstalled the app </li></ul></td><td colspan="2"><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><p>Time frame and Frequency </p></td></tr><tr><td colspan="3"><h4>In-app events</h4><p><img alt="in-app_event_filter.jpg" src="https://files.readme.io/1bb8a78b3c64ab8e0d01c1e2be63e9bdd00b2be2396335b3a01289b0b0837593-46335625078929.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Did event [<em>event name</em>]</li><li>Did not do event: [<em>event name]</em></li></ul></td><td><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><p>Time frame and Frequency </p></td><td><p><img alt="C.jpg" src="https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg"/></p><p>Event attribute + value:</p><ul><li>Is</li><li>Is not</li><li>Greater than</li><li>Less than</li><li><a href="./audiences-guide#contains-does-not-contain-logic">Contains</a></li><li><a href="./audiences-guide#contains-does-not-contain-logic">Does not contain</a></li></ul></td></tr><tr><td colspan="3"><br /><br />**Note**<br /><h4>In-app event notes</h4><ul><li>The in-app event list updates <a href="./about-data-freshness-and-timezone-support#daily-processing">daily.</a></li><li>If <strong>Did event </strong>is selected, and the in-app event has attributes associated with it, you can filter by the in-app-event attribute value. </li><li><p>In-app events, by default, are limited to 100 unique values per attribute. For example, if the event is "purchase" and the attribute is "content-type" there can only be 100 (or fewer) possible content types. However, numeric values are unlimited.<br/>If there are in-app event attributes (parameters) and values that don't appear in the list, you can add them manually by clicking on <strong>Add event attribute</strong> &gt; <strong>Add item</strong><br/> </p><p><strong><img alt="Add_item.jpg" src="https://files.readme.io/00d62c7edfa556c3ecb50842003fb64ecde848413f1b81fd100f3da7257bc38e-46335625079825.jpg"/></strong></p></li><li>All manually added event items must be entered as string type (text) only. Numeric values should not be added, and will not work correctly.</li><li>When a manually added event item is added, the "Estimated audience size" may not reflect accurately. <br/>If you require more than 100 attributes/values to appear in the list, you can also contact your CSM or send an email to hello@appsflyer.com.</li></ul><h4><strong><span id="contains-does-not-contain-logic"></span>Contains / Does not contain logic:</strong></h4><p><strong>Contains: </strong>Matches users whose event attribute values contain a specific word(s). Matching is partial and case-insensitive. For example, the keyword "bag" matches attributes such as "handbag" or "Bag".</p><p><strong>Does not contain:</strong> Matches users whose event attribute values do not contain the specified word(s). The matching logic is also partial and case-insensitive.</p><br /><br />**Note**<br /><h4>Contains logic notes</h4><ul><li>Minimum keyword length: 2 characters.</li><li>Maximum allowed inputs per rule: 1 keyword per AND condition.</li><li>Numeric and special-character-only attributes are not supported.</li><li>Multilingual support includes accented and non-Latin characters (e.g., é, ü, Korean characters).</li><li>When using the "Contains" or "Does not contain" operators, estimated audience size and estimated upload size are unavailable. </li></ul></td></tr><tr><td colspan="3"><h4>Revenue</h4><p><img alt="revenue_filter.jpg" src="https://files.readme.io/e896abde88511e5675074d5e4d995ed810637be8327c7c157ddf65668839fd4a-46335625080209.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Total in-app purchases revenue</li><li>Total ad revenue</li><li>Total revenue </li></ul></td><td colspan="2"><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><ul><li>Is</li><li>Greater than</li><li>Less than </li></ul><p><strong>Definitions:</strong></p><ul><li><strong>Total in-app purchases revenue:</strong> total value of all events reported using the <code>af_revenue</code> parameter for a specific device/CUID</li><li><strong>Total ad revenue:</strong> total ad revenue generated by a specific device/CUID</li><li><strong>Total revenue:</strong> Total in-app purchases revenue + Total ad revenue</li></ul><p><strong>Notes:</strong></p><ul><li>To use the <strong>Total ad revenue</strong> and <strong>Total revenue</strong> filters, <a href="./roi360-guide-ad-revenue-attribution">Ad revenue attribution</a> must be implemented in your AppsFlyer account.</li><li>All revenue filter options are measured in USD.</li></ul></td></tr><tr><td colspan="3"><h4>Geo</h4><p><img alt="location_filter.jpg" src="https://files.readme.io/62f6144d23ef23070e2d6d8891a420691633a466d1b8d76365b4d82f40c725c6-46335625081361.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Location </li></ul></td><td><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><ul><li>Is</li><li>Is not</li></ul></td><td><p><img alt="C.jpg" src="https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg"/></p><p><strong>Location options</strong></p><ul><li>Country</li><li>State</li><li>City</li></ul></td></tr><tr><td colspan="3"><p><strong>Notes relating to location:</strong></p><ul><li>If you select multiple countries, you can't select states.</li><li>If you select multiple states, you can select cities.</li></ul></td></tr><tr><td colspan="3"><h4>Owned media</h4><p><img alt="doctored_owned_media_image_with_app_specified__final_version_.jpg" src="https://files.readme.io/0d15fa734e11164e6e525e26c66291c52144586c8c35dad77a71e471cbf3326d-46335667621649.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Owned media source</li><li>Owned media campaign</li><li>Owned media ad set</li><li>Owned media ad</li></ul></td><td><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><ul><li>Is</li><li>Is not</li></ul></td><td><p><img alt="C.jpg" src="https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg"/></p><p>Values such as:</p><ul><li>Email</li><li>SMS</li><li>Web</li><li>Social media (excluding paid advertising)</li><li>QR codes</li><li>Referrals</li><li>Specific media campaigns, ad sets, and ads</li></ul></td></tr><tr><td colspan="3"><p>You can build targeted audiences consisting of users who were attributed to specific owned media sources. Additionally, you can choose the level of granularity and target users who came from a specific owned media source, campaign, ad set, and/or individual ad.</p><p>Use the audiences you create to re-engage users with personalized messaging on either owned or paid media, or as exclusion lists to prevent them from seeing irrelevant or unnecessary ads when running user acquisition or re-engagement campaigns.</p></td></tr><tr><td colspan="3"><h4>Device</h4><p><img alt="device_filter.jpg" src="https://files.readme.io/184cd84f83b94c38f53ca5a9ef67a4f2c6ad8f8a78d832f6c7979a2c88f61cb5-46335667623441.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Device brand</li><li>Device model</li><li>App version</li><li>OS version</li><li>Carrier</li></ul></td><td><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><ul><li>Is</li><li>Is not </li></ul></td><td><img alt="C.jpg" src="https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg"/> Selected value</td></tr><tr><td colspan="3"><h4>Attribution</h4><p><img alt="Attribution_filter.jpg" src="https://files.readme.io/c7aee01564562bc7d468d6b2bd59ff3d26a028d19382dfdbc35c3fe700f214e7-46335625087249.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Organic</li><li>Retargeting</li></ul></td><td><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><ul><li>False</li><li>True</li></ul></td><td> </td></tr><tr><td colspan="3"><h4><a href="./audiences-create-better-audiences-with-user-attribute-data">User attributes</a></h4><p><img alt="user_attribute_filter.jpg" src="https://files.readme.io/add34f52509bf733f10364691e32ab88331a1caee4bbc4627fb665ec3826422d-46335625088145.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><p>User attribute name</p></td><td><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><ul><li>String type<ul><li>Is</li><li>Is not</li></ul></li><li>Number type<ul><li>Is</li><li>Is greater than</li><li>Is lower than</li></ul></li></ul></td><td><p><img alt="C.jpg" src="https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg"/><br/>For string: Select a value</p><p>For number: Enter a value</p></td></tr></tbody></table>

</Accordion>

<Accordion title="Combine rulesets">

**To combine a ruleset with an existing audience:**

1. Go to **Engage** > **Audiences**.
2. Click **Add Audience**.  
   The **Build** tab displays.
3. Enter a unique **Audience name**.
4. Select the platform: **Android** or **iOS**.
5. [Optional] Select **Advanced settings** to select the [user identifier:](/docs/audiences-guide#user-identifier-device-id-vs-customer-id)
   * [Default] **Device ID**: evaluates rules by device ID only.
   * **Customer user ID**: evaluates rules by grouping devices using the CUID. Use this method after you verify that your data has valid CUIDs.
6. Click **Existing audience**, then select the specific audience.
7. Select an operator: and, or, exclude.

**Limitations:**

* The existing audience must be on the same platform (such as iOS or Android) as the new audience.
* An audience that is based on an existing audience can’t be used.
* An imported audience can’t be used.

</Accordion>

## Create and manage partner connections

This section describes how to create and manage media partner connections.

<div id="create-a-new-connection" />

<Accordion title="Create a new connection">

The **Connections** tab displays all your partner connections and the status of each. All the information needed to upload audience data to a media partner is specified in a partner connection. You can have multiple connections for a single media partner (using different accounts, login information, etc.).

**To create a new connection:**

1. Go to **Engage** > **Audiences > Connections**.
2. Click **+ New connection**.  

   **Note:** If you are creating a new partner connection from within the audience builder, click on **+ Add partner connection** within the **Manage audience connections** window.
3. Select a **Partner name**.
4. Enter a **Connection name**.  

   **Note:** It must be a new name that was never used when creating other connections.
5. Complete the required fields/login information for the partner. Some partners have [detailed instructions about how to connect.](/docs/audiences-partner-connections)  

   **Note:** Credentials must be unique. To prevent duplicate connection creation, you'll be blocked from creating the new connection if the credentials have already been used for another partner connection.
6. Select the user identifiers that you authorize for sharing with this partner.
   * Supported identifiers vary by partner. Only those identifiers supported by the selected partner will appear in the list.
   * Only identifiers that comply with your [account-level user identifier policy](/docs/audiences-user-identifier-policy) will be uploaded. You will see a caution message if you select an identifier that is disallowed by your account policy.  
     ![doctored_connection_image.jpg](https://files.readme.io/5de138c4a2c2a3f26bebc6bd14d9703408a986dc4f8c53235d4be337784603af-46335625091345.jpg)
7. Click **Save.**

</Accordion>

<div id="manage-connections" />

<Accordion title="Manage connections">

**To manage an existing connection:**

1. Select a partner.
2. Select a connection. ![Edit_connection_screen.jpg](https://files.readme.io/8c13e9dc04e98ca959b9ca250ff4954079d71e4ccd4cb2047f9037f31def0aeb-46335625091729.jpg)
3. Take any of the following actions:

| Option | Procedure |
| --- | --- |
| Change the connection name | **To change the connection name,** edit it directly in the **Connection name** field. |
| Reconnect | **To reconnect:**<ol><li>If the connection status is not active, click **Reconnect**.</li><li>Update the connection credentials or login to the partner to re-authenticate according to the instruction in the user interface.</li></ol> |
| Modify user identifiers | **To modify user identifiers,** select/deselect the user identifiers that you authorize for sharing with this partner.Only identifiers that comply with your [account-level user identifier policy](/docs/audiences-user-identifier-policy) will be uploaded. |
| Delete connection | **To delete a connection:**<ol><li>If there are any audiences connected, remove them as follows:<ol><li>Select the audience.</li><li>The audience connects tab opens in a new tab.</li><li>Remove the connection.</li><li>Close the tab.</li></ol></li><li>Repeat this procedure until no audiences are connected to the connection.</li><li>Click **Delete connection**.</li></ol> |

</Accordion>

## Dashboard and metrics

This section describes the features and campaign metrics that appear on the dashboard.

<Accordion title="Audiences dashboard">

[![new_dashboard_image_doctored.jpg](https://files.readme.io/98da5fffae48c7fafd48d45444085fb9bce804e2f03690994a23699604e0367e-46335625092369.jpg)](https://files.readme.io/98da5fffae48c7fafd48d45444085fb9bce804e2f03690994a23699604e0367e-46335625092369.jpg)

| Column | Description |
| --- | --- |
| Audience name | Audience name |
| Size | All users that match the audience criteria |
| Upload size | The audience size available for upload after the application of your account-level [user identifier policy](/docs/audiences-user-identifier-policy) and selected identifiers for the linked partner connections.<br /><br />**Note:** The actual size on the partner side may be different for various reasons including:<ul><li>The partner matching process.</li><li>The upload size for iOS reflects the number of enriched segments based on IDFVs which may include duplicated IDFAs. Deduplication is done when uploaded to the partner side, potentially causing size discrepancies.</li></ul> |
| App name | The app(s) referenced in the audience definition. These are not necessarily the apps targeted by the campaigns that utilize the audience. |
| Upload to | <ul><li>Icons of partners to whom the audience is sent</li><li>![SplitAudiences.png](https://files.readme.io/85891dd56649980b8324ee9680e8e0d73898dc3f18a66428c147bc689ba08201-46335667629457.png) indicates that the audience is split between partners</li></ul> |
| Incrementality | This column displays if you subscribe to [Incrementality.](/docs/incrementality-for-remarketing-overview)Statuses include:<ul><li>**Pending** - Initial data-gathering period (48 hours) starting from the campaign start date</li><li>**Link campaign** - Select the relevant campaign(s) to link to the experiment. If we have a campaign suggestion for you, it will be pre-selected (with any additional suggestions ordered by relevance in the dropdown list).</li><li>**Active** - The experiment is in progress</li><li>**Completed** - The experiment has ended</li></ul>Clicking on a status takes you to the Incrementality dashboard. |
| Upload status | <ul><li>The current audience upload status</li><li>The tooltip displays the date and time of the most recent upload</li><li>In case of failure, click **View details**and take corrective action in accordance with the detailed error message that displays</li></ul> |

</Accordion>

<div id="campaign-metrics" />

<Accordion title="Campaign metrics">

#### metrics hash

#### Campaign metrics basics

The **Campaign metrics** section of the Audiences dashboard displays data for campaigns that used an audience for targeting (whether for inclusion, exclusion, or as the basis of a lookalike audience).

* Using an audience for targeting (and deciding how it is used) is part of setting up campaigns with media partners. Media partners vary in their support for how audiences can be used.

**Supported partners:** Currently, data is available for Meta ads, Google Ads, and Snapchat. The **Campaign metrics** section of the dashboard is visible only if you have audiences connected to supported partners.

**To view Campaign metrics:**

1. Scroll to the far right of the Audiences dashboard to make the **Campaign metrics** section fully visible.
2. Use the date picker to select the timeframe for which you want to display data. (By default, the dashboard displays data for the past 7 days.)

**To download Campaign metrics** **for the selected timeframe:**

1. Click the **Export** button at the top of the Audiences dashboard.
2. Once the file has been generated, it downloads automatically.


#### Summary view

The initial **Campaign metrics** view displays summary campaign data for each audience:

[![campaign_metrics_summary_view.jpg](https://files.readme.io/a7fb8a1909ca9536914822008dc140cb66270d3ff9ceec8d09647a9f81b463ae-46335625093649.jpg)](https://files.readme.io/3b3c1878471a1b77cb7e4296b966302873caa6313f8779b99f4f3687c36bfa5d-46335625093009.png)

| Column | Description |
| --- | --- |
| Campaigns | Total number of campaigns that used the audience for targeting during the selected timeframe (campaigns run with supported partners only) |
| Campaign cost | Total cost of these campaigns during the selected timeframe |
| Campaign revenue | Total revenue attributed to these campaigns during the selected timeframe |

#### Detailed view

From the summary view, click on the ![show_detailed_view_icon.png](https://files.readme.io/597b5a91c35cab2df040fbf12be1b4bf41fa82471e4f533e8da48a7aa93bb174-46335667631761.png) icon to enter the detailed view for the selected audience. (The  ![show_detailed_view_icon.png](https://files.readme.io/597b5a91c35cab2df040fbf12be1b4bf41fa82471e4f533e8da48a7aa93bb174-46335667631761.png) icon appears at the far right of a row when you place your mouse anywhere on that row.)

The detailed view displays data broken down by supported partner and campaign:

[![campaign_metrics_detailed_view.jpg](https://files.readme.io/cee8910e07bdf6707feeda39dd5e480b19b27fad801dd99d501c2c1ceb4bb49d-46335667634193.jpg)](https://files.readme.io/44b5b71c5832a27785a3f8919a05ed9456e02e3f59ee822b021cd3f08089609f-46335625094417.png)

If the selected audience was used to target more than one app, use the drop-down list ![pin_A.png](https://files.readme.io/dcf60cd17a1135e63f6443728c3d713d9cacd6af0e1c010c226d1a092770c40b-46335667636113.png) to filter the data by app.

Click the **Overview dashboard** link ![pin_B.png](https://files.readme.io/b8c902aab2ca2f748dfe647dab3f52e66f6c161d173cb3cf53dbf4ecdc1edef1-46335667637009.png) to view the campaigns on the Overview dashboard:

* The dashboard will open in a new browser tab, automatically filtered by the relevant campaigns.
* If the **Overview dashboard** link is disabled, you can enable it by selecting a single app from the drop-down list ![pin_A.png](https://files.readme.io/dcf60cd17a1135e63f6443728c3d713d9cacd6af0e1c010c226d1a092770c40b-46335667636113.png). Once the link is enabled, clicking it will take you to the Overview dashboard for the selected app.

| Column | Description |
| --- | --- |
| Cost | Campaign cost during the selected timeframe (in total, then broken down by supported partner and campaign) |
| Revenue | Revenue attributed to the campaigns during the selected timeframe (in total, then broken down by supported partner and campaign) |
| Daily reach | The average number of unique users per day who saw ads from the campaign during the selected timeframe (as reported by the partner) |

#### Data sources and availability

It's easier to understand the availability of **Campaign metrics** data when we take a look at where the data comes from:

* **Partner data:** Since you select the audience(s) to be targeted by specific campaigns through your media partners, only these partners are able to provide certain information:
  * The connection of an audience to a campaign (in other words, the fact that a particular audience was used for targeting by that campaign)
  * The number of unique users per day who saw ads from the campaign ("daily reach")
* **AppsFlyer data:** Cost and revenue data is provided by AppsFlyer.

<Accordion title="Partner data availability">

Data is reported only for campaigns run with [supported partners](/docs/audiences-guide#campaign-metrics-basics).

* **Note:** Google Ads doesn't support the reporting of daily reach.

</Accordion>

<Accordion title="AppsFlyer data availability">

Cost and revenue data is available within the context of **Campaign metrics** if it is reported for your apps in other areas of AppsFlyer (for example, the Overview and Event dashboards).

* Cost data requires a subscription to [ROI360](/docs/roi360-cost-aggregation-overview).
* Revenue data requires that you have configured [ad revenue attribution](/docs/roi360-guide-ad-revenue-attribution) and/or [in-app event revenue attribution](/docs/roi360-revenue-attribution-overview).

</Accordion>

<Accordion title="Why don't I see Campaign metrics data for campaigns run with supported partners?">

Campaign metrics data is available only for:

* Campaigns that are connected to an audience.
* Campaigns that are running on supported media partner sites.
* Active campaigns within the main date range selected.
* Campaigns that we receive install traffic from, within the date range selected on the Campaign Metrics filter.
* Users configured for the partner connection that have permissions to receive campaign-level data. To view this data, change the user's permissions with the partner or use different credentials in the partner connection settings.

</Accordion>

</Accordion>

## Traits and limitations

Please note the following traits and limitations.

<Accordion title="Traits">

| Trait | Supported | Remarks |
| --- | --- | --- |
| Ad networks | **x** |  |
| Agencies | **x** |  |
| Agency transparency | **x** |  |
| App-specific time zone | N/A |  |
| App-specific currency | N/A |  |
| Data protection | **✓** | Your audience data may be processed to support AI-powered Audiences capabilities. Your account data is never shared and is used only to improve internal models and predictions. |
| Size limitations | N/A |  |
| Organic data | **✓** | Included |
| Non-organic data | **✓** | Included |
| Data freshness | Daily UTC | <ul><li>Updates are pushed to partners on a daily basis.</li><li>The in-app event lists in the rule-builder update Daily.</li></ul> |
| Historical data | **✓** | Audiences has access to app event data from 90 days prior to your Audiences subscription date (for clicks and impressions, it’s 31 days prior). The data is fully available once the backfill process is complete (which takes between 5 - 14 days). |
| Account user access | **✓** | <ul><li>Some functions, like CSV download, setting S3, and Slack partner connections require [user account permission to access raw data](/docs/user-management).</li><li>As a security measure, if the account of a user who created an audience has been deleted, AppsFlyer stops uploading that audience's data to the media partner(s). To check the upload status of your audiences, go to **Engage** > **Audiences**. To reactivate the audience, duplicate it and configure the [split audience](/docs/audiences-guide#audience-split-and-control-groups) settings.</li></ul> |

</Accordion>

<div id="limitations" />

<Accordion title="Limitations">

| Limitations | Remarks |
| --- | --- |
| Attribution data | Clicks and impressions data only contains devices that have an advertising\_id/idfa on their original click URL. The devices of users from SRNs, which don't use external attribution links, are not included in the click data for audiences. |
| Audience creation | <ul><li>Audience names can't be changed on the connected partners’ side.</li><li>When creating an audience, only the top 100 events display. However, when you begin entering an event name, all events display.</li><li>When using the Total Revenue filter within the query builder, the estimated audience size is not available. This doesn't affect the audience creation process.</li></ul> |
| Connections | Creating duplicate partner connections (connections with the same account / login / property ID / etc.) is not supported and will result in errors. |
| Download audience CSV file | Download file size is limited to 5 million records. |
| Imported audiences | You can't combine imported audiences with other audiences or rulesets. |
| Inactive audiences | Audiences that are inactive will be paused. This means that they will no longer be calculated or uploaded to connected partners. The audience can always be "unpaused" by clicking Upload now. This will resume audience calculations and automatic uploads to partners as before. |
| Not supported | The following are not supported by AppsFlyer Audiences:<ul><li>[Google Ads](/docs/audiences-partner-connections#google-ads): UAC campaigns aren't supported. Other campaign types are supported.</li><li>Windows phone OS</li><li>Nested event values</li></ul> |
| Number of audiences | <ul><li>You can create up to 100 audiences per day.</li><li>You can have up to 100 active Custom/Suggested audiences at a time.</li><li>You can have up to 500 active imported audiences at a time.</li></ul> |
| Rulesets | <ul><li>Within rulesets, in-app events are limited to 100 unique values per attribute. For example, if the event is "purchase" and the attribute is "content-type" there can only be 100 (or fewer) possible content types. However, numeric values are unlimited. If more values per attribute are required, contact your CSM or send an email to hello@appsflyer.com.</li><li>Only integer (whole) numbers are supported in numeric ruleset filters. Float type (decimal) numbers are not supported. Example: In-app revenue is equal to $1 USD is supported but $1.5 USD is not.</li></ul> |
| S2S reporting | Ensure that user identifiers (IDFV or IDFA) are sent in the S2S in-app events payload and that the IDFV or IDFA is consistent with AppsFlyer SDK collection. This will ensure that data isn’t missed and that audience calculations are accurate. |

</Accordion>

> 📘 **See also**
>
> * [Incrementality guide](/docs/incrementality-for-remarketing-overview)
> * [Running an Incrementality experiment](/docs/run-an-incrementality-for-remarketing-experiment)