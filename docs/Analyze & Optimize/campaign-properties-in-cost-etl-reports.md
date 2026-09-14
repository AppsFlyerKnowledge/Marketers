---
title: "Campaign properties in cost ETL reports"
excerpt: "Learn about campaign properties and how they display in AppsFlyer Cost ETL data for Meta ads, Google, and Snap."
---
**At a glance:** Learn about campaign properties and how they display in AppsFlyer Cost ETL data.

## About campaign properties

Campaign properties are a special group of dimensions that represent various settings of an advertising campaign, including campaign objective, bid type, and bid amount. These are settings you normally view and edit in your ad network dashboard, but AppsFlyer pulls the campaign properties dimensions and makes the data available in Cost ETL, just as you view other dimensions.

With campaign properties data, you can:

- See all bid changes made by your UA team.
- Measure and analyze the effectiveness of a bid change and whether it had the intended effect.

AppsFlyer campaign properties data is available for Meta ads and Google. See what data AppsFlyer pulls, and how it is normalized and mapped to each ad network, in the sections that follow.

<Tabs>
<Tab title="Meta ads">

See what data AppsFlyer pulls, and how it is standardized and mapped to Meta ads, in the table that follows.

| Dimension | Description |
| --- | --- |
| Campaign objective | Pulled from: [campaign.objective](https://developers.facebook.com/docs/marketing-api/reference/ad-campaign-group/insights) |
| Cost model | Pulled from: [adset.optimization\_goal](https://developers.facebook.com/docs/marketing-api/bidding/overview#opt) |
| AppsFlyer normalized cost model mapping | | Cost model | Normalized cost model |<br>| --- | --- |<br>| - LINK\_CLICKS<br>- POST\_ENGAGEMENT<br>- REPLIES<br>- LANDING\_PAGE\_VIEWS | CPC |<br>| - OFFSITE\_ CONVERSIONS<br>- DERIVED\_EVENTS<br>- LEAD\_GENERATION | CPA |<br>| APP\_INSTALLS | CPI |<br>| VALUE | ROI |<br>| - REACH<br>- IMPRESSIONS<br>- SOCIAL\_IMPRESSIONS | CPM |<br>| - THRUPLAY<br>- VIDEO\_VIEWS<br>- TWO\_SECOND\_CONTINUOUS\_VIDEO\_VIEWS | CPCV | |
| Bid strategy | Pulled from: [adset.bid\_strategy](https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy)<br>If there is no bid\_strategy in the adset level, then: [campaign.bid\_strategy](https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy) |
| AppsFlyer normalized bid strategy | | Bid strategy | Normalized bid strategy |<br>| --- | --- |<br>| - LOWEST\_COST\_ WITHOUT\_CAP<br>- COST\_CAP<br>- LOWEST\_COST\_ WITH\_MIN\_ROAS | Auto bid |<br>| TARGET\_COST | Target bid |<br>| Anything else | Unknown | |
| Bid amount | Bid amount in advertiser currency |
| Original bid amount | Pulled from: adset.bid\_amount |

</Tab>

<Tab title="Google">

See what data AppsFlyer pulls, and how it is standardized and mapped to Google, in the table that follows.

| Dimension | Description |
| --- | --- |
| Campaign objective | Pulled from: [campaign.advertising\_channel\_sub\_type](https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.advertising_channel_sub_type)<br>Note: The following fields population depends on the channel\_sub\_type:<br>- AC: APP\_CAMPAIGN or APP\_CAMPAIGN\_FOR\_ENGAGEMENT<br>- Non-AC: Every other value for channel\_sub\_type |
| Cost model | - For AC, pulled from: [campaign.app\_campaign\_setting.bidding\_strategy\_goal\_type](https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type)<br>- For non-AC, pulled from: [campaign.bidding\_strategy\_type](https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type) |
| AppsFlyer normalized cost model mapping | | Cost model | Normalized cost model |<br>| --- | --- |<br>| AC | - OPTIMIZE\_INSTALLS\_TARGET\_INSTALL\_COST<br>- OPTIMIZE\_IN\_APP\_CONVERSIONS\_TARGET\_INSTALL\_COST | CPI |<br>| OPTIMIZE\_IN\_APP\_CONVERSIONS\_TARGET\_CONVERSION\_COST | CPA |<br>| OPTIMIZE\_RETURN\_ON\_ADVERTISING\_SPEND | ROI |<br>| - UNKNOWN<br>- UNSPECIFIED | Other |<br>| Non-AC | - REACH<br>- ENHANCED\_CPC<br>- MANUAL\_CPC<br>- PERCENT\_CPC<br>- TARGET\_SPEND | CPC |<br>|  | - MANUAL\_CPM<br>- TARGET\_CPM<br>- TARGET\_IMPRESSION\_SHARE | CPM |<br>|  | MANUAL\_CPV | CPCV |<br>|  | - MAXIMIZE\_CONVERSIONS<br>- TARGET\_CPA | CPA |<br>|  | - MAXIMIZE\_CONVERSION\_VALUE<br>- TARGET\_ROAS | ROI |<br>|  | - COMMISSION<br>- PAGE\_ONE\_PROMOTED<br>- TARGET\_OUTRANK\_SHARE<br>- UNKNOWN<br>- UNSPECIFIED | Other | |
| Bid strategy | - For AC, pulled from: [campaign.app\_campaign\_setting.bidding\_strategy\_goal\_type](https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type)<br>- For non-AC, pulled from: [campaign.bidding\_strategy\_type](https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type) |
| AppsFlyer normalized bid strategy | | Bid strategy | Normalized bid strategy |<br>| --- | --- |<br>| AC | - OPTIMIZE\_INSTALLS\_TARGET\_INSTALL\_COST<br>- OPTIMIZE\_IN\_APP\_CONVERSIONS\_TARGET\_CONVERSION\_COST | Max bid |<br>| - OPTIMIZE\_IN\_APP\_CONVERSIONS\_TARGET\_INSTALL\_COST<br>- OPTIMIZE\_RETURN\_ON\_ADVERTISING\_SPEND | Target bid |<br>| - UNKNOWN<br>- UNSPECIFIED | Other |<br>| Non-AC | - ENHANCED\_CPC<br>- MANUAL\_CPC<br>- MANUAL\_CPM<br>- MANUAL\_CPV | Manual bid |<br>| - MAXIMIZE\_CONVERSIONS<br>- MAXIMIZE\_CONVERSION\_VALUE<br>- PAGE\_ONE\_PROMOTED<br>- TARGET\_IMPRESSION\_SHARE<br>- TARGET\_OUTRANK\_SHARE<br>- TARGET\_SPEND | Auto bid |<br>| - PERCENT\_CPC<br>- TARGET\_CPA<br>- TARGET\_CPM<br>- TARGET\_ROAS | Target bid |<br>| - COMMISSION<br>- UNKNOWN<br>- UNSPECIFIED | Other |<br>| Anything else | Unknown | |
| Bid amount | Bid amount in advertiser currency |
| Original bid amount | Pulled from: [campaign.target\_cpa.target\_cpa\_micros](https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.target_cpa.target_cpa_micros) |

</Tab>

<Tab title="Snap">

| Dimension | Description |
| --- | --- |
| Campaign objective | Pulled from: [campaign.objective](https://developers.snapchat.com/api/docs/#campaigns) |
| Cost model | Pulled from: [adsquad.optimization\_goal](https://developers.snapchat.com/api/docs/#squad-optimization-goals) |
| AppsFlyer normalized cost model mapping | | Cost model | Normalized cost model |<br>| --- | --- |<br>| - SWIPES<br>- STORY\_OPENS | CPC |<br>| - USES<br>- PIXEL\_ADD\_TO\_CART<br>- PIXEL\_PURCHASE<br>- PIXEL\_SIGNUP<br>- APP\_ADD\_TO\_CART<br>- APP\_PURCHASE<br>- APP\_SIGNUP | CPA |<br>| APP\_INSTALLS | CPI |<br>| - IMPRESSIONS | CPM |<br>| - VIDEO\_VIEWS<br>- VIDEO\_VIEWS\_15\_SEC | CPCV | |
| Bid strategy | Pulled from: [adsquad.bid\_strategy](https://developers.snapchat.com/api/docs/#bid-strategy) |
| AppsFlyer normalized bid strategy | | Bid strategy | Normalized bid strategy |<br>| --- | --- |<br>| - MIN\_ROAS<br>- AUTO\_BID | Auto bid |<br>| LOWEST\_COST\_ WITH\_MAX\_BID | Max bid |<br>| TARGET\_COST | Target bid | |
| Bid amount | Bid amount in advertiser currency |
| Original bid amount | Pulled from: adsquad.bid\_micro |

</Tab>
</Tabs>