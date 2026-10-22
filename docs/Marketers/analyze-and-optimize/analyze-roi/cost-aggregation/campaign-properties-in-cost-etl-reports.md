---
title: Campaign properties in cost ETL reports
metadata:
  keywords:
    - cost
    - Advertisers
    - Xpend
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - ROI360
  created_at: '2021-06-02T17:21:22Z'
  edited_at: '2025-04-05T11:08:21Z'
  id: 360020994977
  locale: en-us
  section: Cost aggregation
  section_id: 6551029483281
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360020994977-Campaign-properties-in-cost-ETL-reports
---
> **At a glance:** Learn about campaign properties and how they display in AppsFlyer Cost ETL data.

## About campaign properties

Campaign properties are a special group of dimensions that represent various settings of an advertising campaign, including campaign objective, bid type, and bid amount. These are settings you normally view and edit in your ad network dashboard, but AppsFlyer pulls the campaign properties dimensions and makes the data available in Cost ETL, just as you view other dimensions.

With campaign properties data, you can:

* See all bid changes made by your UA team.
* Measure and analyze the effectiveness of a bid change and whether it had the intended effect.

AppsFlyer campaign properties data is available for Meta ads and Google. See what data AppsFlyer pulls, and how it is normalized and mapped to each ad network, in the sections that follow.

<div id="facebook" />

<Accordion title="Meta ads">

See what data AppsFlyer pulls, and how it is standardized and mapped to Meta ads, in the table that follows.

<Table>
  <thead>
    <tr>
      <th>
        Dimension
      </th>
      <th>
        Description
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        Campaign objective
      </td>
      <td>
        Pulled from: [campaign.objective](https://developers.facebook.com/docs/marketing-api/reference/ad-campaign-group/insights)
      </td>
    </tr>
    <tr>
      <td>
        Cost model
      </td>
      <td>
        Pulled from: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview#opt">adset.optimization\_goal</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        AppsFlyer normalized cost model mapping
      </td>
      <td>
        <table><thead><tr><th>Cost model</th><th>Normalized cost model</th></tr></thead><tbody><tr><td>\* LINK\_CLICKS \* POST\_ENGAGEMENT \* REPLIES \* LANDING\_PAGE\_VIEWS</td><td>CPC</td></tr><tr><td>\* OFFSITE\_ CONVERSIONS \* DERIVED\_EVENTS \* LEAD\_GENERATION</td><td>CPA</td></tr><tr><td>APP\_INSTALLS</td><td>CPI</td></tr><tr><td>VALUE</td><td>ROI</td></tr><tr><td>\* REACH \* IMPRESSIONS \* SOCIAL\_IMPRESSIONS</td><td>CPM</td></tr><tr><td>\* THRUPLAY \* VIDEO\_VIEWS \* TWO\_SECOND\_CONTINUOUS\_VIDEO\_VIEWS</td><td>CPCV</td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        Cost model
      </td>
      <td>
        Normalized cost model
      </td>
    </tr>
    <tr>
      <td>
        <ul><li>LINK\_CLICKS</li><li>POST\_ENGAGEMENT</li><li>REPLIES</li><li>LANDING\_PAGE\_VIEWS</li></ul>
      </td>
      <td>
        CPC
      </td>
    </tr>
    <tr>
      <td>
        <ul><li>OFFSITE\_ CONVERSIONS</li><li>DERIVED\_EVENTS</li><li>LEAD\_GENERATION</li></ul>
      </td>
      <td>
        CPA
      </td>
    </tr>
    <tr>
      <td>
        APP\_INSTALLS
      </td>
      <td>
        CPI
      </td>
    </tr>
    <tr>
      <td>
        VALUE
      </td>
      <td>
        ROI
      </td>
    </tr>
    <tr>
      <td>
        <ul><li>REACH</li><li>IMPRESSIONS</li><li>SOCIAL\_IMPRESSIONS</li></ul>
      </td>
      <td>
        CPM
      </td>
    </tr>
    <tr>
      <td>
        <ul><li>THRUPLAY</li><li>VIDEO\_VIEWS</li><li>TWO\_SECOND\_CONTINUOUS\_VIDEO\_VIEWS</li></ul>
      </td>
      <td>
        CPCV
      </td>
    </tr>
    <tr>
      <td>
        Bid strategy
      </td>
      <td>
        Pulled from: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy">adset.bid\_strategy</Anchor><br /><br />If there is no bid\_strategy in the adset level, then: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy">campaign.bid\_strategy</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        AppsFlyer normalized bid strategy
      </td>
      <td>
        <table><thead><tr><th>Bid strategy</th><th>Normalized bid strategy</th></tr></thead><tbody><tr><td>\* LOWEST\_COST\_ WITHOUT\_CAP \* COST\_CAP \* LOWEST\_COST\_ WITH\_MIN\_ROAS</td><td>Auto bid</td></tr><tr><td>TARGET\_COST</td><td>Target bid</td></tr><tr><td>Anything else</td><td>Unknown</td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        Bid strategy
      </td>
      <td>
        Normalized bid strategy
      </td>
    </tr>
    <tr>
      <td>
        <ul><li>LOWEST\_COST\_ WITHOUT\_CAP</li><li>COST\_CAP</li><li>LOWEST\_COST\_ WITH\_MIN\_ROAS</li></ul>
      </td>
      <td>
        Auto bid
      </td>
    </tr>
    <tr>
      <td>
        TARGET\_COST
      </td>
      <td>
        Target bid
      </td>
    </tr>
    <tr>
      <td>
        Anything else
      </td>
      <td>
        Unknown
      </td>
    </tr>
    <tr>
      <td>
        Bid amount
      </td>
      <td>
        Bid amount in advertiser currency
      </td>
    </tr>
    <tr>
      <td>
        Original bid amount
      </td>
      <td>
        Pulled from: adset.bid\_amount
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="google" />

<Accordion title="Google">

See what data AppsFlyer pulls, and how it is standardized and mapped to Google, in the table that follows.

<table><thead><tr><th><font> <span>Dimension</span> </font></th><th><span> <font>Description</font> </span></th></tr></thead><tbody><tr><td><span> <font> <span>Campaign objective</span> </font> </span></td><td><p><font> <span>Pulled from: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.advertising_channel_sub_type" target="_blank">campaign.advertising_channel_sub_type</a></span> </font></p><p><font> <span>Note: The following fields population depends on the channel_sub_type:</span> </font></p><ul><li><font> <span>AC: APP_CAMPAIGN or APP_CAMPAIGN_FOR_ENGAGEMENT</span> </font></li><li><font> <span>Non-AC: Every other value for channel_sub_type</span> </font></li></ul></td></tr><tr><td><span> <font>Cost model</font> </span></td><td><ul><li><span>For AC, pulled from: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type" target="_blank">campaign.app_campaign_setting.bidding_strategy_goal_type</a></span></li><li><span>For non-AC, pulled from: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type" target="_blank">campaign.bidding_strategy_type</a></span></li></ul></td></tr><tr><td><span> <span>AppsFlyer normalized cost model mapping</span> </span></td><td><table><thead><tr><th colspan="2">Cost model</th><th>Normalized cost model</th></tr></thead><tbody><tr><td rowspan="4"><span>AC</span><span><br/></span></td><td><ul><li>OPTIMIZE_INSTALLS_TARGET_INSTALL_COST</li><li>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_INSTALL_COST</li></ul></td><td><span>CPI</span></td></tr><tr><td><p>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_CONVERSION_COST</p></td><td><span>CPA</span></td></tr><tr><td>OPTIMIZE_RETURN_ON_ADVERTISING_SPEND</td><td><span>ROI</span></td></tr><tr><td><ul><li>UNKNOWN</li><li>UNSPECIFIED</li></ul></td><td><span>Other</span></td></tr><tr><td>Non-AC</td><td><ul><li>REACH</li><li>ENHANCED_CPC</li><li>MANUAL_CPC</li><li>PERCENT_CPC</li><li>TARGET_SPEND</li></ul></td><td><span>CPC</span></td></tr><tr><td> </td><td><ul><li>MANUAL_CPM</li><li>TARGET_CPM</li><li>TARGET_IMPRESSION_SHARE</li></ul></td><td><span>CPM</span></td></tr><tr><td> </td><td>MANUAL_CPV</td><td><span>CPCV</span></td></tr><tr><td> </td><td><ul><li>MAXIMIZE_CONVERSIONS</li><li>TARGET_CPA</li></ul></td><td><span>CPA</span></td></tr><tr><td> </td><td><ul><li>MAXIMIZE_CONVERSION_VALUE</li><li>TARGET_ROAS</li></ul></td><td><span>ROI</span></td></tr><tr><td><span> </span></td><td><ul><li>COMMISSION</li><li>PAGE_ONE_PROMOTED</li><li>TARGET_OUTRANK_SHARE</li><li>UNKNOWN</li><li>UNSPECIFIED</li></ul></td><td><span>Other</span></td></tr></tbody></table></td></tr><tr><td><span> <font>Bid strategy</font> </span></td><td><ul><li><span>For AC, pulled from: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type" target="_blank">campaign.app_campaign_setting.bidding_strategy_goal_type</a></span></li><li><span>For non-AC, pulled from: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type" target="_blank">campaign.bidding_strategy_type</a></span></li></ul></td></tr><tr><td><font> <span>AppsFlyer normalized bid strategy</span> </font></td><td><table><thead><tr><th colspan="2"><font> <span>Bid strategy</span> </font></th><th><font> <span>Normalized bid strategy</span> </font></th></tr></thead><tbody><tr><td rowspan="3"><font> <span>AC</span> </font></td><td><ul><li><font> <span>OPTIMIZE_INSTALLS_TARGET_INSTALL_COST</span> </font></li><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_CONVERSION_COST</span> </font></li></ul></td><td><font> <span>Max bid</span> </font></td></tr><tr><td><ul><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_INSTALL_COST</span> </font></li><li><font> <span>OPTIMIZE_RETURN_ON_ADVERTISING_SPEND</span> </font></li></ul></td><td><font> <span>Target bid</span> </font></td></tr><tr><td><ul><li><font> <span>UNKNOWN</span> </font></li><li><font> <span>UNSPECIFIED</span> </font></li></ul></td><td><font> <span>Other</span> </font></td></tr><tr><td rowspan="5"><font> <span>Non-AC</span> </font></td><td><ul><li><font> <span>ENHANCED_CPC</span> </font></li><li><font> <span>MANUAL_CPC</span> </font></li><li><font> <span>MANUAL_CPM</span> </font></li><li><font> <span>MANUAL_CPV</span> </font></li></ul></td><td><font> <span>Manual bid</span> </font></td></tr><tr><td><ul><li><font> <span>MAXIMIZE_CONVERSIONS</span> </font></li><li><font> <span>MAXIMIZE_CONVERSION_VALUE</span> </font></li><li><font> <span>PAGE_ONE_PROMOTED</span> </font></li><li><font> <span>TARGET_IMPRESSION_SHARE</span> </font></li><li><font> <span>TARGET_OUTRANK_SHARE</span> </font></li><li><font> <span>TARGET_SPEND</span> </font></li></ul></td><td><font> <span>Auto bid</span> </font></td></tr><tr><td><ul><li><font> <span>PERCENT_CPC</span> </font></li><li><font> <span>TARGET_CPA</span> </font></li><li><font> <span>TARGET_CPM</span> </font></li><li><font> <span>TARGET_ROAS</span> </font></li></ul></td><td><font> <span>Target bid</span> </font></td></tr><tr><td><ul><li><font> <span>COMMISSION</span> </font></li><li><font> <span>UNKNOWN</span> </font></li><li><font> <span>UNSPECIFIED</span> </font></li></ul></td><td><font> <span>Other</span> </font></td></tr><tr><td><font> <span>Anything else</span> </font></td><td><font> <span>Unknown</span> </font></td></tr></tbody></table></td></tr><tr><td><span> <font>Bid amount</font> </span></td><td><span> <font>Bid amount in advertiser currency</font> </span></td></tr><tr><td><span> <font>Original bid amount</font> </span></td><td><span> <font>Pulled from: </font> </span> <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.target_cpa.target_cpa_micros" target="_blank">campaign.target_cpa.target_cpa_micros</a></td></tr></tbody></table>

</Accordion>

<div id="snap" />

<Accordion title="Snap">

<Table>
  <thead>
    <tr>
      <th>
        Dimension
      </th>
      <th>
        Description
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        Campaign objective
      </td>
      <td>
        Pulled from: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#campaigns">campaign.objective</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Cost model
      </td>
      <td>
        Pulled from: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#squad-optimization-goals">adsquad.optimization\_goal</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        AppsFlyer normalized cost model mapping
      </td>
      <td>
        <table><thead><tr><th>Cost model</th><th>Normalized cost model</th></tr></thead><tbody><tr><td>\* SWIPES \* STORY\_OPENS</td><td>CPC</td></tr><tr><td>\* USES \* PIXEL\_ADD\_TO\_CART \* PIXEL\_PURCHASE \* PIXEL\_SIGNUP \* APP\_ADD\_TO\_CART \* APP\_PURCHASE \* APP\_SIGNUP</td><td>CPA</td></tr><tr><td>APP\_INSTALLS</td><td>CPI</td></tr><tr><td>\* IMPRESSIONS</td><td>CPM</td></tr><tr><td>\* VIDEO\_VIEWS \* VIDEO\_VIEWS\_15\_SEC</td><td>CPCV</td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        Cost model
      </td>
      <td>
        Normalized cost model
      </td>
    </tr>
    <tr>
      <td>
        <ul><li>SWIPES</li><li>STORY\_OPENS</li></ul>
      </td>
      <td>
        CPC
      </td>
    </tr>
    <tr>
      <td>
        <ul><li>USES</li><li>PIXEL\_ADD\_TO\_CART</li><li>PIXEL\_PURCHASE</li><li>PIXEL\_SIGNUP</li><li>APP\_ADD\_TO\_CART</li><li>APP\_PURCHASE</li><li>APP\_SIGNUP</li></ul>
      </td>
      <td>
        CPA
      </td>
    </tr>
    <tr>
      <td>
        APP\_INSTALLS
      </td>
      <td>
        CPI
      </td>
    </tr>
    <tr>
      <td>
        <ul><li>IMPRESSIONS</li></ul>
      </td>
      <td>
        CPM
      </td>
    </tr>
    <tr>
      <td>
        <ul><li>VIDEO\_VIEWS</li><li>VIDEO\_VIEWS\_15\_SEC</li></ul>
      </td>
      <td>
        CPCV
      </td>
    </tr>
    <tr>
      <td>
        Bid strategy
      </td>
      <td>
        Pulled from: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#bid-strategy">adsquad.bid\_strategy</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        AppsFlyer normalized bid strategy
      </td>
      <td>
        <table><thead><tr><th>Bid strategy</th><th>Normalized bid strategy</th></tr></thead><tbody><tr><td>\* MIN\_ROAS \* AUTO\_BID</td><td>Auto bid</td></tr><tr><td>LOWEST\_COST\_ WITH\_MAX\_BID</td><td>Max bid</td></tr><tr><td>TARGET\_COST</td><td>Target bid</td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        Bid strategy
      </td>
      <td>
        Normalized bid strategy
      </td>
    </tr>
    <tr>
      <td>
        <ul><li>MIN\_ROAS</li><li>AUTO\_BID</li></ul>
      </td>
      <td>
        Auto bid
      </td>
    </tr>
    <tr>
      <td>
        LOWEST\_COST\_ WITH\_MAX\_BID
      </td>
      <td>
        Max bid
      </td>
    </tr>
    <tr>
      <td>
        TARGET\_COST
      </td>
      <td>
        Target bid
      </td>
    </tr>
    <tr>
      <td>
        Bid amount
      </td>
      <td>
        Bid amount in advertiser currency
      </td>
    </tr>
    <tr>
      <td>
        Original bid amount
      </td>
      <td>
        Pulled from: adsquad.bid\_micro
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div data-zendesk-anchors="h_01J1PX98QNCZG9Y9PRZQ4ZEEFK=about-campaign-properties h_01J1PX98QNX2T408GB2WV0RFZH=facebook h_01J1PX98QP22PPG9V84DD5WEM1=google h_01J1PXNDS4V16NQQQGMBND9PAF=snap" />
