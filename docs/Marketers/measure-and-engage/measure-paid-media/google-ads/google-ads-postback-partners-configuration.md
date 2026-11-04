---
title: Google Ads postback partners—Configuration
metadata:
  keywords:
    - postbacks
    - Integration
    - Advertisers
    - Agencies
    - google ads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-11-16T09:36:56Z'
  edited_at: '2024-07-18T07:44:23Z'
  id: 4411047077905
  locale: en-us
  section: Google Ads
  section_id: 6551205645457
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4411047077905-Google-Ads-postback-partners-Configuration
---
> **At a glance:** Enable Google Ads postback partners to help run your Google Ads campaigns.

Some partners (for example, Bidalgo, Adquant), referred to as **Google Ads postback partners**, are similar to agencies. They help their advertiser clients run Google Ads campaigns, but require getting postbacks for Google Ads conversions.

These Google Ads Postback Partners (GAPPs) can also collect postbacks for Google Ads installs acquired by the advertiser directly, or even by other agencies (see [Use Cases](/docs/google-ads-postback-partners-configuration#google-ads-postback-partners-use-cases)). Using the postbacks information the GAPPs are able to optimize on Google Ads campaigns for the app.

<div id="important" />

> 🚧 **Important!**
>
> Google Ads Postback Partners are **NOT** attributed with installs or events in AppsFlyer.

The advertiser needs an active Google Ads account <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers">set up</Anchor> in AppsFlyer, and also to set up the specific GAPP in AppsFlyer to enable sending postbacks to it.

Other GAPPs integrated with AppsFlyer: Blackbox, Appreciate, Marin Software, Miramedia, Mpbisummer, Protonads, Springrain.

<div id="google-ads-postback-partner-setup" />

## Google Ads postback partner setup

1. In AppsFlyer, from the side menu, select **Collaborate** > **Active Integrations**.

2. Type the name of the GAPP you would like to work with into the search box and select it from the dropdown list.

<div id="tip" />

> 👍 **Tip**
>
> Enter "Google Ads" in the search box and press Enter to receive the list of GAPPs.

3. Click on the required GAPP to open its integration setup.

4. In your **Google Ads** account, copy the Customer ID (without hyphens):

![](https://files.readme.io/7afd536d06b1aca68744a83925ecac86fcef4cc47225826af20120f128da004f-21414601345681.png)

5. Paste the number in the **Google Ads Customer ID** field.

6. Configure the <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">In-App Events Postback section</Anchor>.

7. Click **Save**.

<div id="important-notes" />

> 📘 **Important Notes**
>
> * Disabling attribution for Google Ads also stops sending postbacks to GAPPs.
> * You can configure multiple Ads accounts (CID) to send postbacks (step 5) by separating each CID with a comma.
>
>   ![zds_Agency_multiple.png](https://files.readme.io/36112b9a08ca1e6a2150523e1ec39eda5c28a4be826e9f776f5dbd7b1d0c5378-21414553418897.png)
> * To work with multiple GAPPs, the campaigns for each GAPP should be run from separate google accounts. If you switch from one GAPP to another, make sure to disable the first GAPPs setup in AppsFlyer.

<div id="google-ads-postback-partners-use-cases" />

## Google Ads postback partners use cases

<div id="use-case-1-advertiser-postbacks-only" />

<Accordion title="Use case 1 - Advertiser postbacks only">

An advertiser is running Google Ads campaigns and wants the traffic from its Google Ads accounts to be sent to GAPP X.

1. Advertiser <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers">configures</Anchor> Google Ads
2. Advertiser [configures](/docs/google-ads-postback-partners-configuration#google-ads-postback-partner-setup) GAPP X - Google Ads

The advertiser must enter all its CIDs (Ads Account IDs) in the GAPP X - Google Ads configuration.

</Accordion>

<div id="use-case-2-active-agency-with-advertiser-postbacks-only" />

<Accordion title="Use case 2 - Active agency, with advertiser postbacks only">

An advertiser and an agency are both running Google Ads campaigns, the advertiser wants only its traffic to be sent to GAPP X.

1. Advertiser <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers">configures</Anchor> Google Ads
2. Agency <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-agencies">configures</Anchor> Google Ads (just for their traffic to be attributed to them as an agency)
3. Advertiser [configures](/docs/google-ads-postback-partners-configuration#google-ads-postback-partner-setup) GAPP X - Google Ads

The advertiser must enter ONLY its CIDs in the GAPP X - Google Ads configuration.

</Accordion>

<div id="use-case-3-active-advertiser-with-agency-postbacks-only" />

<Accordion title="Use case 3 - Active advertiser, with agency postbacks only">

An advertiser and agency are running Google Ads campaigns, the agency wants only its traffic to be sent to GAPP X.

1. Advertiser <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers">configures</Anchor> Google Ads
2. Agency <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-agencies">configures</Anchor> Google Ads
3. Agency [configures](/docs/google-ads-postback-partners-configuration#google-ads-postback-partner-setup) GAPP X - Google Ads

The agency must enter ONLY their CIDs in the GAPP X - Google Ads configuration

</Accordion>

<div id="use-case-4-advertiser-agency-postbacks" />

<Accordion title="Use case 4 - Advertiser & agency postbacks">

An advertiser and agency are running Google Ads campaigns, both the advertiser and agency want their traffic to be sent to GAPP X.

1. Advertiser <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers">configures</Anchor> Google Ads
2. Agency <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-agencies">configures</Anchor> Google Ads
3. Advertiser [configures](/docs/google-ads-postback-partners-configuration#google-ads-postback-partner-setup) GAPP X - Google Ads for their CIDs
4. Agency [configures](/docs/google-ads-postback-partners-configuration#google-ads-postback-partner-setup) GAPP X - Google Ads for their CIDs

Notice that these must be different CIDs between the advertiser and agency.

</Accordion>

<div id="available-parameters-for-gapps" />

## Available parameters for GAPPs

**The contents of the postbacks depend on the initial integration of the GAPPs with AppsFlyer** and are unrelated to any advertiser configuration. Therefore, any two GAPPs may have differently defined postback parameters.

For example, `campaign type`, `city`, `carrier` and `ad_type` are parameters, which may or may not exist in any GAPP's postback.

There are two sources for GAPP postback parameters:

1. **AppsFlyer macros** - for details of all the macros available on AppsFlyer's postbacks, click <Anchor target="_blank" href="/partners/docs/postback-macros-for-ad-networks">here</Anchor>.
2. **Google Response** - with every install attributed to Google Ads, AppsFlyer receives relevant information from Google. The following are available parameters on GAPPs postbacks, as received by AppsFlyer from Google Ads (for detailed parameter descriptions, click <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs#sample_responses">here</Anchor>)
   * Ad Events ID
   * Campaign ID
   * Campaign Name
   * Campaign Type
   * External Customer ID (CID)
   * Network Type
   * Network Sub Type
   * Timestamp
   * Video ID
   * Ad Group ID
   * Creative ID
   * Keyword
   * Match Type
   * Placement
   * Interaction Type
   * Ad Type
   * Conversion Metric
   * Location

<div id="note" />

> 📘 **Note**
>
> The information available is based solely on the information sent by Google to AppsFlyer. If, for some reason, Google does not send an install's information, AppsFlyer can't pass it on to the GAPP.

<div data-zendesk-anchors="h_01HKA1HTJ4VW4YRXMSVG7WBTJM=important h_01HKA1HTJ5BE5EVQJ2T9HSHKQC=google-ads-postback-partner-setup h_01HKA1HTJ5BJTTS15QC44M63B2=tip h_01HKA1HTJ5KSD1CVJ4FKDSATJX=important-notes h_01HKA1HTJ5DX0Z2ZCGX07EX15F=google-ads-postback-partners-use-cases h_01HKA1HTJ5T2XJJ4M9YZ1S52SF=use-case-1-advertiser-postbacks-only h_01HKA1HTJ5EFADYE33NQVP1NBQ=use-case-2-active-agency-with-advertiser-postbacks-only h_01HKA1HTJ5H4KK2M94QY0VFRSA=use-case-3-active-advertiser-with-agency-postbacks-only h_01HKA1HTJ537CYXEBQRCV5FSPK=use-case-4-advertiser-agency-postbacks h_01HKA1HTJ5H0SXEMBVB6K2EZ91=available-parameters-for-gapps h_01HKA1HTJ55XWMX90KSYTGFB6C=note" />
