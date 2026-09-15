---
title: "Audiences guide"
excerpt: "Increase the efficiency of your user acquisition and remarketing campaigns by using AppsFlyer Audiences to build and connect audience segments to your partner networks."
---
![Intro_image.png](https://files.readme.io/645503f41e6a76c854c62236fc279be591849879790d02001eafc75f0d1a974a-30258966500753.png)

## Audiences basics

AppsFlyer Audiences lets you easily build audience segments and connect them to your owned and paid channels—so you can deliver tailored campaigns for better engagement and performance. And once your campaign’s been sent, you can view performance metrics in Audiences as well.

An audience is a segment of current or past users of your app that meet the specific criteria that you define. Audiences can be based on personal characteristics, behavior, in-app activity, attribution source, revenue generated, geographic location, device type, and more.

**Step 1 - Build your audience in AppsFlyer:** You can build a custom audience from scratch, import one, or select from our ready-made, fully customizable list of “Suggested Audiences”, which save you time and are based on industry best practices.

**Step 2 - Connect the audience:** Once you’ve built your audience, the next step is connecting it to your media partners from within AppsFlyer, which sends identifiers for the members of that audience to the partners and creates the audience on the partners’ systems. This enables them to serve specific ads only to these users. Audiences are automatically refreshed and pushed to partners once daily. Additionally, you can upload an audience to 3rd-party services such as Amazon S3 buckets, or download it as a CSV file right from the dashboard.

All the information needed to upload audience data to a media partner is specified in a partner connection. You can have multiple connections for a single media partner (using different accounts, login information, etc.). In order to enable compliance with the privacy requirements of iOS 14.5 and other user privacy considerations, **Audiences allows you full control to determine which identifiers are shared with partners**, both at the account level and for each partner connection.

### Audience split and Incrementality testing

[Incrementality](https://support.appsflyer.com/hc/articles/360009360978) testing measures the real impact of your campaigns with A/B testing that accurately measures “incremental lift”—the difference between conversions that happened as a result of your marketing campaigns and those that would have happened anyway. AppsFlyer Audiences sets the stage for testing with an optional feature that splits the audience among selected media partners and a control group, so you can use the Incrementality dashboard to understand the true value of your campaigns.

## Get started

Follow these steps to get started with Audiences:

| | Steps |
| --- | --- |
| 1 | In AppsFlyer, from the side menu, select **Engage** \> **Audiences**<br>**Note:** Audiences is a premium feature. If you need help getting started, reach out to your customer success manager, or write to [hello@appsflyer.com](mailto:hello@appsflyer.com) |
| 2 | Set account-level [policy](https://support.appsflyer.com/hc/articles/360016791118) for sharing user identifiers with partners |
| 3 | Create a new audience:<br>- [Custom Audience](https://support.appsflyer.com/hc/articles/115002689186#create-a-custom-audience) - Build your audience from scratch<br>- [Suggested Audience](https://support.appsflyer.com/hc/articles/115002689186#create-a-suggested-audience) - Ready-made, customizable audiences that are based on industry best practices<br>- [Import audience](https://support.appsflyer.com/hc/articles/360013291857) - Import audience segments from your internal systems (such as BI or CRM) |
| 4 | Connect the audience to one or more media partners |
| Optional | [Split the audience among partners and a control group](https://support.appsflyer.com/hc/articles/115002689186#audience-split-and-control-groups) |
| Optional | [Import user attributes](https://support.appsflyer.com/hc/articles/360009775517) |

## Create and manage audiences

This section describes how to create and manage audiences and set up Incrementality testing.

### Create a Custom Audience

A Custom Audience is built from scratch using any rulesets and filters you wish.

**To create a Custom Audience:**

01. In AppsFlyer, from the side menu, select **Engage** \> **Audiences**.
02. Click **New audience**.
03. Select **Custom audience**.

    The **Build** tab displays.
04. Enter a unique **Audience name**.

    > 📘 Note
    >
    > Audience names can't include special characters (" ’ # % & \* + / : ; < = > ? ( ) [ ] \{ \} \ \| ~)

05. Select the platform: **Android** or **iOS**.
06. Select the [user identifier](https://support.appsflyer.com/hc/articles/115002689186#user-identifier%E2%80%94device-id-vs-customer-id):
07. [Default] **Device ID**: Evaluates rules by device ID only.
08. **Customer ID**: Evaluates rules by grouping devices using the CUID (use this method only after you verify that your data has valid CUIDs.)
09. Select **New ruleset**, or if you wish to add the users of an existing audience, click **Existing audience** then select the specific audience from the list.
10. Build the audience guided by the user interface. For specific information about rule options, see [All about rulesets](https://support.appsflyer.com/hc/articles/115002689186#all-about-rulesets).
11. Combine rulesets using the operators and, or, exclude.
12. As you build your audience, the panes on the right side automatically update the estimated audience and per-partner upload sizes.
13. Complete defining the audience, then click **Next.**

    The **Audience connection** window appears. This is where you [connect the audience to your media partners](https://support.appsflyer.com/hc/articles/115002689186#connect-an-audience-to-media-partners).

#### Notes

- You can have up to 100 active Custom/Suggested audiences at a time.
- Audience names may be visible on your connected media partner sites. Do not include sensitive information in names.

### Create a Suggested Audience

Suggested Audiences enable you to explore and discover **ready-made audience segments, that are based on industry best practices.** You can select an audience, customize it, and connect it with your partner networks for optimally targeted marketing campaigns.

Choose from over 30+ audiences within the **categories of Acquire, Activate, Engage, Monetize, and industry-specific audiences.** The audiences are 100% customizable, so you can create the exact audience you need. Audiences include:

- Convert ad clicks into installs
- Get lookalikes
- Suppression lists
- Encourage registration
- Encourage purchase
- Monetize purchasers
- And a lot more…

#### Example use case

Let’s say you want to urge active users of your app, who haven’t purchased yet, to make their first purchase. You can select the “Encourage purchase” audience and customize it to specify which event defines an in-app purchase. Then you can connect the audience to your partners and run a promotional campaign that nudges them towards making a purchase and leads them to the app's purchase page.

![Encourage_purchase_image_this_one.jpeg](https://files.readme.io/8b49590a0c97707bd4a0b151d30cc48183e15ffb13d2d4e9ee25d522de71846c-30259018203153.jpg)

**To create a Suggested Audience:**

01. In AppsFlyer, from the side menu, select **Engage** \> **Audiences**.
02. Click **New audience**.
03. Select **Suggested audience**.
04. Select the app.
05. Browse through the various categories and select an audience that matches your goals.

    > 📘 Note
    >
    >
    > Some audiences require you to add the specific [in-app events](https://support.appsflyer.com/hc/articles/115005544169) to define the audience criteria. If the AppsFlyer [predefined event](https://support.appsflyer.com/hc/articles/4410481112081#predefined-event-names) has already been configured in your app, it will be pre-selected. If not, you'll need to select the appropriate custom event from the dropdown menu. ![Select_an_event__1_.jpeg](https://files.readme.io/b5055ca61791f15efc3a91f3f2d749e1df9e3f5e8b956b9167e186474de57ac4-30258966520721.jpg)

06. Click **Select & customize**.
07. Enter a unique **Audience name**.

    > 📘 Note
    >
    > Audience names can't include special characters (" ’ # % & \* + / : ; < = > ? ( ) [ ] \{ \} \ \| ~)

08. Select the platform: Android or iOS.
09. Select the [user identifier](https://support.appsflyer.com/hc/articles/115002689186#user-identifier%E2%80%94device-id-vs-customer-id):
    - [Default] **Device ID**: Evaluates rules by device ID only.
    - **Customer ID**: Evaluates rules by grouping devices using the CUID (use this method only after you verify that your data has valid CUIDs.)
10. If you wish to further customize the audience by adding additional [rulesets](https://support.appsflyer.com/hc/articles/115002689186#all-about-rulesets), you can do so if you wish by clicking **+ Filter**. When done, click **Next**.

    The **Audience connection** window appears. This is where you [connect the audience to your media partners](https://support.appsflyer.com/hc/articles/115002689186#connect-an-audience-to-media-partners).

#### Notes

- You can have up to 100 active Custom/Suggested audiences at a time.
- Audience names may be visible on your connected media partner sites. Do not include sensitive information in names.

### Import an audience

You can [import predefined audience segments](https://support.appsflyer.com/hc/articles/360013291857) from your internal systems (such as BI and CRM) to AppsFlyer Audiences, and use it as your central point for connecting and maintaining all of your audience segments with your advertising partners. Additionally, it allows you to enjoy Audiences features, such as identifier matching/data enrichment and connected campaign metrics.

### Connect an audience to media partners

Once you've defined your audience, the next step is connecting it to your media partners.

**To connect your audience to media partners:**

1. After defining your new audience on the audience **Build** page, click **Next**. The **Audience connection** window appears.
2. Click **+ Partner connection**, then do one of the following:
   - **To add a new connection**, click **+ Add partner connection** (see the [Create a new connection](https://support.appsflyer.com/hc/articles/115002689186#create-a-new-connection) section below for detailed instructions).
   - **To select from existing connections:** 
     1. Search for the partner connection.
     2. Select one or more existing connections.
     3. Click **Save**.

        The Audience connection window opens.
     4. [Optional] [Split an audience between partners and a control group](https://support.appsflyer.com/hc/articles/115002689186#audience-split-and-control-groups)
     5. [Optional] [Copy split groups to S3](https://support.appsflyer.com/hc/articles/115002689186#audience-split-and-control-groups).
3. Click **Save**.

Once connected, the audience is updated and pushed to partners daily.

### User identifier—Device ID vs. Customer ID

Audience rule evaluation is performed using an app user identifier. Select from:

- [Default] **Device ID:** Ruleset compliance is assessed using the device ID (GAID or IDFA/IDFV). When compliant with the ruleset, the device ID is added to the audience list. **Note:** The device ID will be shared with partners only when permitted by your user identifier policy.
- [**Customer ID (CUID)**](https://support.appsflyer.com/hc/articles/207032016-Customer-user-ID-field) **:** 
  - Ruleset compliance is assessed by grouping all device IDs associated with the same CUID. If the group complies with the ruleset, then the device IDs comprising the group are added to the audience. **Note**: The CUID itself is not part of the audience list and is not sent to media partners.
  - CUID implementation considerations:
    - Ensure that your data is populated with valid CUIDs.
    - App users (devices) without a CUID are ignored.
    - When a device ID is matched to a CUID, historical audience data for the user is updated retroactively and included in audience builds going forward. **Note**: No change is made to raw data.
    - If a device ID is associated with two different CUIDs, the most recently associated CUID is used.
    - When building an audience with CUID as the identifier, the CUID association must have been received by AppsFlyer on the install (not just on post-install events) for complete association with the relevant devices and successful enrichment with device identifiers (i.e., GAID, IDFA). [Learn more](https://support.appsflyer.com/hc/articles/207032016-Customer-User-ID-field-CUID-#setting-the-cuid)

![CuidExaplainded_us-en.jpg](https://files.readme.io/d40309ab2fd34a4862b9c089ac2fade2f5642973fc4d4977da66f1ee6bf1e390-30258966523921.jpg)

#### Example: Device ID vs. CUID

An audience of users who spent more than $5

| Advertising<br />ID | CUID | Purchase $ |
| --- | --- | --- |
| A | 99 | 1 |
| A | 99 | 2 |
| B | 77 | 1 |
| B | 77 | 5 |
| C | 99 | 3 |
| D | None | 50 |

| Rule evaluated by | Device IDs included in the audience | Explanation |
| --- | --- | --- |
| Device ID | B, D | A and C are not included - the spend was less than $5 |
| CUID | A, B, C | - A and C have the same CUID (99) - the combined spend is $6.<br />- D is ignored - there is no CUID |

> 📘 Note
>
> The same method of summing spend across device IDs grouped by CUID, shown in the example above, also applies to other numerical attributes (for example, scoring).

### Audience split and control groups

Use the toggle that splits the audience among partners and a control group to effortlessly set the stage for A/B testing and [Incrementality measurement](https://support.appsflyer.com/hc/articles/360009360978) so you can get the crucial insights you need about campaign impact. When enabled, the feature randomly splits the audience among your selected partners and a control group. The control group is the portion of the audience that is held back from partners and is a necessary requirement for Incrementality measurement. You can adjust any of the split percentages you wish and disable or re-enable the split per audience.

| Feature | Description |
| --- | --- |
| Split audience | - This feature randomly splits the audience among your selected partners and a control group. **It is enabled by default for Incrementality subscribers**, and can easily be disabled or re-enabled at any time.<br />- Split audiences for a variety of reasons, such as A/B testing and Incrementality measurement.<br />- **Note:** Modifying an existing split allocation between partners causes redistribution of the entire audience. This may negatively impact the validity of A/B testing and will cause active Incrementality experiments to end and restart as new experiments. |
| Control group | A portion of the audience is held back in a control group, which is not sent to any partner:<br />- Control groups are used in A/B testing and to measure the incremental lift of your marketing campaigns.<br />- 15% of the audience (or higher) is recommended for an effective control group.<br />- The minimum control group % needed to run an Incrementality experiment is 1%. |
| Send a copy of split lists to an S3 bucket | CSV files containing the split audience lists and control group can be sent to an Amazon S3 bucket.<br />- **Note**: This is not the same as defining Amazon S3 as a connected partner.<br />- The audience lists can be downloaded to a CSV file. Use the CSV file, for example, to send to partners who are not integrated with AppsFlyer. |

**To split the audience and perform other partner actions:**

1. In the AppsFlyer left-side panel, go to **Engage** \> **Audiences**.
2. In the **Audiences** tab, select the audience.
3. Go to the **Connect** tab.

![audience_split_1200px.png](https://files.readme.io/1a9decaea5f77ec36c111a132c12733cfa44bb1e87c6515e71843e6c7fcabfee-46335667595281.png) The current settings display:
   - The top, right-side pane displays estimated total audience and upload sizes (for all partners)
   - The bottom, right-side presents a visualization of:
     - Estimated upload size for each partner
     - Partner overlap (for audiences that aren't split)
4. Take any of the following actions:

| Action | Procedure |
| --- | --- |
| Split an audience between partners and control group | 1. Make sure the **Split audience/Measure incremental impact** toggle is enabled.<br />   - The total of the control group and split to partners combined must be 100%.<br />   - If you don't want to include the control group in the split: allocate 0%.<br />   - All connected partners must be allocated a portion of the split (Don't allocate a partner 0%)<br />   - To view the total allocated: scroll down; the total percent split displays.<br />2. Enter the percentage allocated to:<br />   - **Control group -** 15% or higher is recommended.<br />   - Enter a split percentage per connection.<br />   - Scroll down to display the total allocation in percent, and make sure that the total allocation is 100%.<br />   - Click **Save split**.<br />   - Click **Save**. |
| Copy split groups to S3 | **To send a copy of the audience split list to an S3 bucket:**<br />1. Click **Copy split groups to S3.**<br />2. Select a connection.<br />3. Click **Save**.<br />Files are sent using the following directory and filename structure:<br />- **Directory**: <br />  <br />  <br />  ```auto
  Auto \YYYY-MM-DD\audienceID_audienceName_timestamp\
  ```
  <br />- **Filename**: the name of the partner or control group<br />  <br />  Note: If the connection to the partner fails, and the file is not uploaded, the word **failed** will be appended to the partner name (for example, _partner\_name\_failed.csv_) |
| Create and add a new connection | **To create a new connection:**<br />1. Click **Add** **partner** **connection.**<br />2. Type a connection name.<br />3. Select a partner.<br />4. Complete the process according to the instructions in the user interface.<br />5. Click **Add partner connection.** |
| Add or remove an existing connection | **To remove or add an existing connection:**<br />1. Hover over the partner connection.<br />2. Click the "Remove" icon.<br />3. Click **Save**. |

### Manage audiences

**To manage audiences from the Audiences dashboard:**

1. In the AppsFlyer left-side panel, go to **Engage** \> **Audiences**.
2. The following options are available:

| Option | Description |
| --- | --- |
| Create a new audience | Create a new audience |
| Change audience settings | Click an **Audience name,** do one of the following: <br />   - In the **Build** tab: View and change rulesets.<br />   - In the **Connect** tab: Set audience split and control group options. |
| Actions | In the ![3_dots_icon.png](https://files.readme.io/e1b296a694e4803662b2d3776ce001f981e44ada6d3f7552974417b3d6fc7169-46335625061649.png) icon that appears on the right when hovering over an audience on the main Audiences page:<br />   - **View history**: Displays the audience upload history including audience size, and split between partners.<br />   - **Upload now**: Sends the audience to connected partners.<br />   - **Download as CSV**: <br />     - Generates and downloads the audience list as CSV files(s) that include the identifiers you select. Only data that complies with your [user identifier policy](/docs/audiences-user-identifier-policy) will be downloaded.<br />     - One file is generated for each partner.<br />     - The file(s) are downloaded after calculation of the audience, which can take some time after you create or modify an audience.<br />     - Downloaded files are limited to 5 million records. For larger files, send the file to an [S3 bucket](https://support.appsflyer.com/hc/articles/360013960577-Audiences-partner-list-and-connection-instructions#amazon-s3).<br />     - Only an audience that is connected to partner networks will be updated daily and kept current. If the audience is not connected to partner networks, it will not be kept current beyond the audience creation date. If you want to download the most current info, you can duplicate the audience to recreate it (see below), then download the CSV from the duplicated audience.<br />   - **Duplicate**: <br />     - Copies the audience definition.<br />     - When you duplicate an audience, give it a unique name.<br />     - [Option] Remove one or more of the connected partners during duplication.<br />   - **Calculate now**: [For imported audiences] Recalculates the number of users in an audience. Use as needed to refresh the audience size if it does not look correct. <br />   - **Pause:**<br />     <br />     - Pausing the audience inactivates it so that it no longer gets calculated and uploaded to connected partners (existing audience data from the past 3 years is retained).<br />     - You can pause audiences you don't use to keep within the allowed maximum number of active audiences. You can have up to 100 active Custom/Suggested audiences and up to 500 active imported audiences at a time.<br />**To pause an audience:**<br />1\. Hover over the audience on the main Audiences page so that the ![3 dots icon.png](https://files.readme.io/e1b296a694e4803662b2d3776ce001f981e44ada6d3f7552974417b3d6fc7169-46335625061649.png) (Actions menu) icon appears on the right.<br />![Actions menu.jpg](https://files.readme.io/d7ad8445c7e886ef4669155391419c9bb5538552f9a0bc1dabaa85a4ad819a1e-46335625065873.jpg)<br />2\. Click the icon and select **Pause**.<br />The audience is now paused.<br />You can also pause multiple audiences at once by checking the box next to the audiences and then clicking **Pause** which will appear on the upper right.<br />   - **Delete:** Permanently deletes the audience. |
| Bulk actions | Carry out the same action on multiple audiences. To use bulk actions, select two or more audiences, then select one of the following bulk actions:<br />   - **Upload now**<br />   - **Show audience overlap**: displays the audience overlap between the selected audiences<br />   - **Delete** |

## All about rulesets

Learn how to use rulesets to define your audiences.

### Audience segmentation rulesets

![audience_segmentation_rulesets.jpg](https://files.readme.io/4407da232d372a98afcd30df3a832f6ef38bb55a6b02640587f44c7501b014f2-46335625066897.jpg)

- An audience segment ruleset consists of one or multiple rules to enable precision filtering.
- Combine rulesets using operators: and, or, exclude.
- As rules are defined and layered, the estimated audience size displays in real-time.
- Rulesets can be duplicated by clicking the ![duplicate_icon.png](https://files.readme.io/c4e2321280c4141e70c499adc92837d663fd29942b1c88532c6f2f3327efc400-46335667603729.png) icon.
- Where an audience consists of multiple rulesets, use the overlap visualization display to better understand your audience segments.
- The [user identifier](https://support.appsflyer.com/hc/articles/115002689186#user-identifier%E2%80%94device-id-vs-customer-id) used to evaluate rules is either the device ID [default] or the customer user ID (CUID).

The examples that follow illustrate ruleset implementation in various scenarios.

### Ruleset examples

#### Example: Location-based rule

Users from New York who uninstalled the app in the last month

![example_location_based_rule.jpg](https://files.readme.io/7ee7e2b9e8f06dc47c93148767fd67d87855a05cd09ba06f2dd2c0ea9dc29607-46335625068817.jpg)

#### Example: User attributes-based rule

Users who launched the app in the last 7 days at least once and whose favorite weapon is a sword.

![example_user_attributes_based_rule.jpg](https://files.readme.io/8ab97cdccd2a1b33b671b1f686ca642306197ccf5151ca2ba9836db8ca496d03-46335625073809.jpg)

#### Example: Revenue

Users who installed the app during the last seven days, and spent $1

![example_revenue.jpg](https://files.readme.io/d7768bec78ff5981639da4e1c8e1a3121961464c0a5932bf8f542f27979358a8-46335625074833.jpg)

#### Example: Owned media filter

Build targeted audiences consisting of users who were attributed to specific owned media sources such as social media (excluding paid advertising), SMS, email, referrals, web, or QR codes. You can also choose your level of granularity and target users who came from a specific media source, campaign, ad set, or individual ad.

Here's an example with users who launched the app at least once in the last 7 days and whose install was attributed to a specific email campaign as well as specific ad sets and ads.

![Owned_media_example.jpg](https://files.readme.io/4b9c076f5299f4f59524a7f816964f4db2c8edd73690aa899e34fcac0d145628-46335667611409.jpg)

The audience can be used to re-engage these users with personalized messaging on either owned or paid media, or as an exclusion list to prevent them from seeing irrelevant or unnecessary ads when running campaigns.

#### Example: Remarketing

Using clicks and views for effective remarketing. To convert these users, a little extra convincing or a gentle reminder is needed. These users have a high probability of converting so remarketing to them can produce significantly better results than advertising to new segments. Create precise audiences for remarketing based on clicks and impressions data collected.

Build an audience of potential users that clicked on an ad but did not install in the last two days.

![example_remarketing.jpg](https://files.readme.io/715c42d56c0deffdb4d28acd213f4a5da62de75bbcd6834a927b9226d2fea43e-46335667613329.jpg)

These are users who, in the recent past, were sufficiently interested in your mobile app to click on your ad, but for some reason did not install the app, or installed the app but did not launch it. Some users just need a reminder (push) to install it. Others may need to see more screens or features of your app to finally convert. Therefore, if you have a primary creative you use on new audiences, it might be better to use a different creative for audiences that clicked but did not install.

### Ruleset filters

- A ruleset consists of one or multiple rules.
- There are various ruleset filter categories such as Events, Revenue, Geo, Attribution, User attributes, Devices, and Owned media.
- Rules have different parameters and settings, as listed in the table below.

| | | |
| --- | --- | --- |
| **Events**<br />![engagement_filter_with_A___B.jpg](https://files.readme.io/ea3063532ff666f6d8a0f90d55c86007d8a54b25017d93ed7bc19e0d727d9193-46335625077777.jpg) | | |
| ![A_.jpg](https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg)<br />- Viewed an ad<br />- Clicked an ad<br />- Installed the app<br />- Did not install the app<br />- Launched the app<br />- Did not launch the app<br />- Uninstalled the app | ![B.jpg](https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg)<br />Time frame and Frequency | |
| **In-app events**<br />![in-app_event_filter.jpg](https://files.readme.io/1bb8a78b3c64ab8e0d01c1e2be63e9bdd00b2be2396335b3a01289b0b0837593-46335625078929.jpg) | | |
| ![A_.jpg](https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg)<br />- Did event [ _event name_]<br />- Did not do event: [ _event name]_ | ![B.jpg](https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg)<br />Time frame and Frequency | ![C.jpg](https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg)<br />Event attribute + value:<br />- Is<br />- Is not<br />- Greater than<br />- Less than<br />- [Contains](/docs/audiences-guide#contains-does-not-contain-logic)<br />- [Does not contain](/docs/audiences-guide#contains-does-not-contain-logic) |
| **In-app event notes**<br />- The in-app event list updates [daily.](https://support.appsflyer.com/hc/articles/360000310629#daily-processing)<br />- If **Did event** is selected, and the in-app event has attributes associated with it, you can filter by the in-app-event attribute value. <br />- In-app events, by default, are limited to 100 unique values per attribute. For example, if the event is "purchase" and the attribute is "content-type" there can only be 100 (or fewer) possible content types. However, numeric values are unlimited.<br /><br />If there are in-app event attributes (parameters) and values that don't appear in the list, you can add them manually by clicking on **Add event attribute** \> **Add item**<br /><br /><br /><br />**![Add_item.jpg](https://files.readme.io/00d62c7edfa556c3ecb50842003fb64ecde848413f1b81fd100f3da7257bc38e-46335625079825.jpg)**<br /><br />- All manually added event items must be entered as string type (text) only. Numeric values should not be added, and will not work correctly.<br />- When a manually added event item is added, the "Estimated audience size" may not reflect accurately. <br /><br />If you require more than 100 attributes/values to appear in the list, you can also contact your CSM or send an email to hello@appsflyer.com.<br />**Contains / Does not contain logic:**<br />**Contains:** Matches users whose event attribute values contain a specific word(s). Matching is partial and case-insensitive. For example, the keyword "bag" matches attributes such as "handbag" or "Bag".<br />**Does not contain:** Matches users whose event attribute values do not contain the specified word(s). The matching logic is also partial and case-insensitive.<br />**Contains logic notes**<br />- Minimum keyword length: 2 characters.<br />- Maximum allowed inputs per rule: 1 keyword per AND condition.<br />- Numeric and special-character-only attributes are not supported.<br />- Multilingual support includes accented and non-Latin characters (e.g., é, ü, Korean characters).<br />- When using the "Contains" or "Does not contain" operators, estimated audience size and estimated upload size are unavailable. | | |
| **Revenue**<br />![revenue_filter.jpg](https://files.readme.io/e896abde88511e5675074d5e4d995ed810637be8327c7c157ddf65668839fd4a-46335625080209.jpg) | | |
| ![A_.jpg](https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg)<br />- Total in-app purchases revenue<br />- Total ad revenue<br />- Total revenue | ![B.jpg](https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg)<br />- Is<br />- Greater than<br />- Less than <br />**Definitions:**<br />- **Total in-app purchases revenue:** total value of all events reported using the `af_revenue` parameter for a specific device/CUID<br />- **Total ad revenue:** total ad revenue generated by a specific device/CUID<br />- **Total revenue:** Total in-app purchases revenue + Total ad revenue<br />**Notes:**<br />- To use the **Total ad revenue** and **Total revenue** filters, [Ad revenue attribution](https://support.appsflyer.com/hc/articles/217490046) must be implemented in your AppsFlyer account.<br />- All revenue filter options are measured in USD. | | |
| **Geo**<br />![location_filter.jpg](https://files.readme.io/62f6144d23ef23070e2d6d8891a420691633a466d1b8d76365b4d82f40c725c6-46335625081361.jpg) | | |
| ![A_.jpg](https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg)<br />- Location | ![B.jpg](https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg)<br />- Is<br />- Is not | ![C.jpg](https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg)<br />**Location options**<br />- Country<br />- State<br />- City |
| **Notes relating to location:**<br />- If you select multiple countries, you can't select states.<br />- If you select multiple states, you can select cities. | | |
| **Owned media**<br />![doctored_owned_media_image_with_app_specified__final_version_.jpg](https://files.readme.io/0d15fa734e11164e6e525e26c66291c52144586c8c35dad77a71e471cbf3326d-46335667621649.jpg) | | |
| ![A_.jpg](https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg)<br />- Owned media source<br />- Owned media campaign<br />- Owned media ad set<br />- Owned media ad | ![B.jpg](https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg)<br />- Is<br />- Is not | ![C.jpg](https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg)<br />Values such as:<br />- Email<br />- SMS<br />- Web<br />- Social media (excluding paid advertising)<br />- QR codes<br />- Referrals<br />- Specific media campaigns, ad sets, and ads |
| You can build targeted audiences consisting of users who were attributed to specific owned media sources. Additionally, you can choose the level of granularity and target users who came from a specific owned media source, campaign, ad set, and/or individual ad.<br />Use the audiences you create to re-engage users with personalized messaging on either owned or paid media, or as exclusion lists to prevent them from seeing irrelevant or unnecessary ads when running user acquisition or re-engagement campaigns. | | |
| **Device**<br />![device_filter.jpg](https://files.readme.io/184cd84f83b94c38f53ca5a9ef67a4f2c6ad8f8a78d832f6c7979a2c88f61cb5-46335667623441.jpg) | | |
| ![A_.jpg](https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg)<br />- Device brand<br />- Device model<br />- App version<br />- OS version<br />- Carrier | ![B.jpg](https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg)<br />- Is<br />- Is not | ![C.jpg](https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg) Selected value |
| **Attribution**<br />![Attribution_filter.jpg](https://files.readme.io/c7aee01564562bc7d468d6b2bd59ff3d26a028d19382dfdbc35c3fe700f214e7-46335625087249.jpg) | | |
| ![A_.jpg](https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg)<br />- Organic<br />- Retargeting | ![B.jpg](https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg)<br />- False<br />- True | |
| **User attributes**<br />![user_attribute_filter.jpg](https://files.readme.io/add34f52509bf733f10364691e32ab88331a1caee4bbc4627fb665ec3826422d-46335625088145.jpg) | | |
| ![A_.jpg](https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg)<br />User attribute name | ![B.jpg](https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg)<br />- String type<br />  - Is<br />  - Is not<br />- Number type<br />  - Is<br />  - Is greater than<br />  - Is lower than | ![C.jpg](https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg)<br />For string: Select a value<br />For number: Enter a value |

### Combine rulesets

**To combine a ruleset with an existing audience:**

1. Go to **Engage** \> **Audiences**.
2. Click **Add Audience**.

The **Build** tab displays.
3. Enter a unique **Audience name**.
4. Select the platform: **Android** or **iOS**.
5. [Optional] Select **Advanced settings** to select the [user identifier:](https://support.appsflyer.com/hc/articles/115002689186#user-identifier%E2%80%94device-id-vs-customer-id)
   - [Default] **Device ID**: evaluates rules by device ID only.
   - **Customer user ID**: evaluates rules by grouping devices using the CUID. Use this method after you verify that your data has valid CUIDs.
6. Click **Existing audience**, then select the specific audience.
7. Select an operator: and, or, exclude.

**Limitations:**

- The existing audience must be on the same platform (such as iOS or Android) as the new audience.
- An audience that is based on an existing audience can’t be used.
- An imported audience can’t be used.

## Create and manage partner connections

This section describes how to create and manage media partner connections.

### Create a new connection

The **Connections** tab displays all your partner connections and the status of each. All the information needed to upload audience data to a media partner is specified in a partner connection. You can have multiple connections for a single media partner (using different accounts, login information, etc.).

**To create a new connection:**

1. Go to **Engage** \> **Audiences > Connections**.
2. Click **+ New connection**.

> 📘 Note
>
> If you are creating a new partner connection from within the audience builder, click on **+ Add partner connection** within the **Manage audience connections** window.

3. Select a **Partner name**.
4. Enter a **Connection name**.

> 📘 Note
>
> It must be a new name that was never used when creating other connections.

5. Complete the required fields/login information for the partner. Some partners have [detailed instructions about how to connect.](https://support.appsflyer.com/hc/articles/360013960577)

> 📘 Note
>
> Credentials must be unique. To prevent duplicate connection creation, you'll be blocked from creating the new connection if the credentials have already been used for another partner connection.

6. Select the user identifiers that you authorize for sharing with this partner.
   - Supported identifiers vary by partner. Only those identifiers supported by the selected partner will appear in the list.
   - Only identifiers that comply with your [account-level user identifier policy](/docs/audiences-user-identifier-policy) will be uploaded. You will see a caution message if you select an identifier that is disallowed by your account policy.

     ![doctored_connection_image.jpg](https://files.readme.io/5de138c4a2c2a3f26bebc6bd14d9703408a986dc4f8c53235d4be337784603af-46335625091345.jpg)
7. Click **Save.**

### Manage connections

**To manage an existing connection:**

1. Select a partner.
2. Select a connection. ![Edit_connection_screen.jpg](https://files.readme.io/8c13e9dc04e98ca959b9ca250ff4954079d71e4ccd4cb2047f9037f31def0aeb-46335625091729.jpg)
3. Take any of the following actions:

| Option | Procedure |
| --- | --- |
| Change the connection name | **To change the connection name,** edit it directly in the **Connection name** field. |
| Reconnect | **To reconnect:**<br />1. If the connection status is not active, click **Reconnect**.<br />2. Update the connection credentials or login to the partner to re-authenticate according to the instruction in the user interface. |
| Modify user identifiers | **To modify user identifiers,** select/deselect the user identifiers that you authorize for sharing with this partner **.** Only identifiers that comply with your [account-level user identifier policy](/docs/audiences-user-identifier-policy) will be uploaded. |
| Delete connection | **To delete a connection:**<br />1. If there are any audiences connected, remove them as follows:<br />   1. Select the audience.<br />   2. The audience connects tab opens in a new tab.<br />   3. Remove the connection.<br />   4. Close the tab.<br />2. Repeat this procedure until no audiences are connected to the connection.<br />3. Click **Delete connection**. |

## Dashboard and metrics

This section describes the features and campaign metrics that appear on the dashboard.

### Audiences dashboard

![new_dashboard_image_doctored.jpg](https://files.readme.io/98da5fffae48c7fafd48d45444085fb9bce804e2f03690994a23699604e0367e-46335625092369.jpg)

| Column | Description |
| --- | --- |
| Audience name | Audience name |
| Size | All users that match the audience criteria |
| Upload size | The audience size available for upload after the application of your account-level [user identifier policy](https://support.appsflyer.com/hc/articles/360016791118) and selected identifiers for the linked partner connections.<br />**Note:** The actual size on the partner side may be different for various reasons including:<br />- The partner matching process.<br />- The upload size for iOS reflects the number of enriched segments based on IDFVs which may include duplicated IDFAs. Deduplication is done when uploaded to the partner side, potentially causing size discrepancies. |
| App name | The app(s) referenced in the audience definition. These are not necessarily the apps targeted by the campaigns that utilize the audience. |
| Upload to | - Icons of partners to whom the audience is sent<br />- ![SplitAudiences.png](https://files.readme.io/85891dd56649980b8324ee9680e8e0d73898dc3f18a66428c147bc689ba08201-46335667629457.png) indicates that the audience is split between partners |
| Incrementality | This column displays if you subscribe to [Incrementality.](https://support.appsflyer.com/hc/articles/360009360978-Incrementality-guide) Statuses include:<br />- **Pending** - Initial data-gathering period (48 hours) starting from the campaign start date<br />- **Link campaign** - Select the relevant campaign(s) to link to the experiment. If we have a campaign suggestion for you, it will be pre-selected (with any additional suggestions ordered by relevance in the dropdown list).<br />- **Active** - The experiment is in progress<br />- **Completed**- The experiment has ended<br />Clicking on a status takes you to the Incrementality dashboard. |
| Upload status | - The current audience upload status<br />- The tooltip displays the date and time of the most recent upload<br />- In case of failure, click **View details** and take corrective action in accordance with the detailed error message that displays |

### Campaign metrics

#### Campaign metrics basics

The **Campaign metrics** section of the Audiences dashboard displays data for campaigns that used an audience for targeting (whether for inclusion, exclusion, or as the basis of a lookalike audience).

- Using an audience for targeting (and deciding how it is used) is part of setting up campaigns with media partners. Media partners vary in their support for how audiences can be used.

**Supported partners:** Currently, data is available for Meta ads, Google Ads, and Snapchat. The **Campaign metrics** section of the dashboard is visible only if you have audiences connected to supported partners.

**To view Campaign metrics:**

1. Scroll to the far right of the Audiences dashboard to make the **Campaign metrics** section fully visible.
2. Use the date picker to select the timeframe for which you want to display data. (By default, the dashboard displays data for the past 7 days.)

**To download Campaign metrics** **for the selected timeframe:**

1. Click the **Export** button at the top of the Audiences dashboard.
2. Once the file has been generated, it downloads automatically.

#### Summary view

The initial **Campaign metrics** view displays summary campaign data for each audience:

[![campaign_metrics_summary_view.jpg](https://files.readme.io/a7fb8a1909ca9536914822008dc140cb66270d3ff9ceec8d09647a9f81b463ae-46335625093649.jpg)](https://support.appsflyer.com/hc/article_attachments/46335625093009)

| Column | Description |
| --- | --- |
| Campaigns | Total number of campaigns that used the audience for targeting during the selected timeframe (campaigns run with supported partners only) |
| Campaign cost | Total cost of these campaigns during the selected timeframe |
| Campaign revenue | Total revenue attributed to these campaigns during the selected timeframe |

#### Detailed view

From the summary view, click on the ![show_detailed_view_icon.png](https://files.readme.io/597b5a91c35cab2df040fbf12be1b4bf41fa82471e4f533e8da48a7aa93bb174-46335667631761.png) icon to enter the detailed view for the selected audience. (The ![show_detailed_view_icon.png](https://files.readme.io/597b5a91c35cab2df040fbf12be1b4bf41fa82471e4f533e8da48a7aa93bb174-46335667631761.png) icon appears at the far right of a row when you place your mouse anywhere on that row.)

The detailed view displays data broken down by supported partner and campaign:

[![campaign_metrics_detailed_view.jpg](https://files.readme.io/cee8910e07bdf6707feeda39dd5e480b19b27fad801dd99d501c2c1ceb4bb49d-46335667634193.jpg)](https://support.appsflyer.com/hc/article_attachments/46335625094417)

If the selected audience was used to target more than one app, use the drop-down list ![pin_A.png](https://files.readme.io/dcf60cd17a1135e63f6443728c3d713d9cacd6af0e1c010c226d1a092770c40b-46335667636113.png) to filter the data by app.

Click the **Overview dashboard** link ![pin_B.png](https://files.readme.io/b8c902aab2ca2f748dfe647dab3f52e66f6c161d173cb3cf53dbf4ecdc1edef1-46335667637009.png) to view the campaigns on the Overview dashboard:

- The dashboard will open in a new browser tab, automatically filtered by the relevant campaigns.
- If the **Overview dashboard** link is disabled, you can enable it by selecting a single app from the drop-down list ![pin_A.png](https://files.readme.io/dcf60cd17a1135e63f6443728c3d713d9cacd6af0e1c010c226d1a092770c40b-46335667636113.png). Once the link is enabled, clicking it will take you to the Overview dashboard for the selected app.

| Column | Description |
| --- | --- |
| Cost | Campaign cost during the selected timeframe (in total, then broken down by supported partner and campaign) |
| Revenue | Revenue attributed to the campaigns during the selected timeframe (in total, then broken down by supported partner and campaign) |
| Daily reach | The average number of unique users per day who saw ads from the campaign during the selected timeframe (as reported by the partner) |

#### Data sources and availability

It's easier to understand the availability of **Campaign metrics** data when we take a look at where the data comes from:

- **Partner data:**Since you select the audience(s) to be targeted by specific campaigns through your media partners, only these partners are able to provide certain information: 
  - The connection of an audience to a campaign (in other words, the fact that a particular audience was used for targeting by that campaign)
  - The number of unique users per day who saw ads from the campaign ("daily reach")
- **AppsFlyer data:** Cost and revenue data is provided by AppsFlyer.

#### Partner data availability

Data is reported only for campaigns run with [supported partners](https://support.appsflyer.com/hc/articles/115002689186#campaign-metrics-basics).

- **Note:** Google Ads doesn't support the reporting of daily reach.

#### AppsFlyer data availability

Cost and revenue data is available within the context of **Campaign metrics** if it is reported for your apps in other areas of AppsFlyer (for example, the Overview and Event dashboards).

- Cost data requires a subscription to [ROI360](https://support.appsflyer.com/hc/articles/207040526).
- Revenue data requires that you have configured [ad revenue attribution](https://support.appsflyer.com/hc/articles/217490046) and/or [in-app event revenue attribution](https://support.appsflyer.com/hc/articles/360001546009).

#### Why don't I see Campaign metrics data for campaigns run with supported partners?

Campaign metrics data is available only for:

- Campaigns that are connected to an audience.
- Campaigns that are running on supported media partner sites.
- Active campaigns within the main date range selected.
- Campaigns that we receive install traffic from, within the date range selected on the Campaign Metrics filter.
- Users configured for the partner connection that have permissions to receive campaign-level data. To view this data, change the user's permissions with the partner or use different credentials in the partner connection settings.

## Traits and limitations

Please note the following traits and limitations.

### Traits

| Trait | Supported | Remarks |
| --- | --- | --- |
| Ad networks | **x** | |
| Agencies | **x** | |
| Agency transparency | **x** | |
| App-specific time zone | N/A | |
| App-specific currency | N/A | |
| Data protection | **✓** | Your audience data may be processed to support AI-powered Audiences capabilities. Your account data is never shared and is used only to improve internal models and predictions. |
| Size limitations | N/A | |
| Organic data | **✓** | Included |
| Non-organic data | **✓** | Included |
| Data freshness | Daily UTC | - Updates are pushed to partners on a daily basis.<br />- The in-app event lists in the rule-builder update Daily. |
| Historical data | **✓** | Audiences has access to app event data from 90 days prior to your Audiences subscription date (for clicks and impressions, it’s 31 days prior). The data is fully available once the backfill process is complete (which takes between 5 - 14 days). |
| Account user access | **✓** | - Some functions, like CSV download, setting S3, and Slack partner connections require [user account permission to access raw data](https://support.appsflyer.com/hc/articles/4409128270481).<br />- As a security measure, if the account of a user who created an audience has been deleted, AppsFlyer stops uploading that audience's data to the media partner(s). To check the upload status of your audiences, go to **Engage** \> **Audiences**. To reactivate the audience, duplicate it and configure the [split audience](https://support.appsflyer.com/hc/articles/115002689186#audience-split-and-control-groups) settings. |

### Limitations

| Limitations | Remarks |
| --- | --- |
| Attribution data | Clicks and impressions data only contains devices that have an advertising\_id/idfa on their original click URL. The devices of users from SRNs, which don't use external attribution links, are not included in the click data for audiences. |
| Audience creation | - Audience names can't be changed on the connected partners’ side.<br />- When creating an audience, only the top 100 events display. However, when you begin entering an event name, all events display.<br />- When using the Total Revenue filter within the query builder, the estimated audience size is not available. This doesn't affect the audience creation process. |
| Connections | Creating duplicate partner connections (connections with the same account / login / property ID / etc.) is not supported and will result in errors. |
| Download audience CSV file | Download file size is limited to 5 million records. |
| Imported audiences | You can't combine imported audiences with other audiences or rulesets. |
| Inactive audiences | Audiences that are inactive will be paused. This means that they will no longer be calculated or uploaded to connected partners. The audience can always be "unpaused" by clicking Upload now. This will resume audience calculations and automatic uploads to partners as before. |
| Not supported | The following are not supported by AppsFlyer Audiences:<br />- [Google Ads](/docs/audiences-partner-connections#google-ads): UAC campaigns aren't supported. Other campaign types are supported.<br />- Windows phone OS<br />- Nested event values |
| Number of audiences | - You can create up to 100 audiences per day.<br />- You can have up to 100 active Custom/Suggested audiences at a time.<br />- You can have up to 500 active imported audiences at a time. |
| Rulesets | - Within rulesets, in-app events are limited to 100 unique values per attribute. For example, if the event is "purchase" and the attribute is "content-type" there can only be 100 (or fewer) possible content types. However, numeric values are unlimited. If more values per attribute are required, contact your CSM or send an email to hello@appsflyer.com.<br />- Only integer (whole) numbers are supported in numeric ruleset filters. Float type (decimal) numbers are not supported. Example: In-app revenue is equal to $1 USD is supported but $1.5 USD is not. |
| S2S reporting | Ensure that user identifiers (IDFV or IDFA) are sent in the S2S in-app events payload and that the IDFV or IDFA is consistent with AppsFlyer SDK collection. This will ensure that data isn’t missed and that audience calculations are accurate. |

#### See also

- [Incrementality guide](https://support.appsflyer.com/hc/articles/360009360978)
- [Running an Incrementality experiment](https://support.appsflyer.com/hc/articles/360014225577)