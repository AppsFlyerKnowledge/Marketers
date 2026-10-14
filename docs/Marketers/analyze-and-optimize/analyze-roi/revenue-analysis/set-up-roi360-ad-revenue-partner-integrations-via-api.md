---
title: "Set up ROI360 ad revenue partner integrations via API"
excerpt: "Configure ad revenue partner integrations for your AppsFlyer account or individual apps via API."
x-zendesk:
  id: 9901416616465
  url: https://support.appsflyer.com/hc/en-us/articles/9901416616465-Set-up-ROI360-ad-revenue-partner-integrations-via-API
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Revenue analysis
  section_id: 6551069075089
  position: 7
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-michael-talapov, Marketers, ROI360]
  labels: [ad revenue, Premium, Marketers, ROI360]
  promoted: false
  comments_disabled: true
  created_at: '2022-10-16T14:53:47Z'
  edited_at: '2025-04-05T11:17:41Z'
---
## Ad revenue partner integration API

The ad revenue partner integration API is used to:

* Set app-level ad revenue partner configurations for your entire account.
* Get a list of current ad revenue partner configurations for your entire account.

<Accordion title="Set API">

**To set (configure) ad revenue partner integrations via API**:

1. [Get your API V2 token](/docs/managing-appsflyer-tokens) from the AppsFlyer dashboard. Required for API authorization. **Note**: This must be done by the account admin.
2. Prepare the parameters to include in the API request, as described in the table that follows.
3. Give the parameter values your developer and tell them to follow the [Set integrations API instructions](https://dev.appsflyer.com/hc/reference/post_integrations) in the dev hub.  
   Integration takes effect at 00:00 UTC the following day.

#### Request parameters

| Parameter | Description |
| --- | --- |
| integrations | <ul><li>Top-level object that must include app\_id, network, and products (listed below).</li><li>Other fields could include credentials, event\_name, and source\_event.</li></ul> |
| app\_id | The app ID for the app you want to integrate. |
| network | <ul><li>The partner you want to integrate.</li><li>For a list of supported networks, see the network column of the [Ad revenue partner API parameter table](https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx).</li></ul> |
| credentials | <ul><li>1 or more credentials required for the network integration.</li><li>For the list of credentials, see the cred columns of the [Ad revenue partner API parameter table](https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx).</li></ul> |
| event\_name | <ul><li>Default value: af\_ad\_revenue</li><li>Can also be a custom event name [beta]</li><li>event\_name isn't required if enabled is set to false.</li></ul> |
| products | <ul><li>List of all enabled products under an integration, including the parameters name, enabled, and if relevant, source\_event (listed below).</li><li>For a list of supported products per network, see the bulk API products column of the [Ad revenue partner API parameter table](https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx).</li></ul> |
| name | <ul><li>The name of the integration type.</li><li>For a list of integration type names, see the bulk API products column of the [Ad revenue partner API parameter table](https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx).</li></ul> |
| enabled | <ul><li>Possible values:<ul><li>true</li><li>false</li></ul></li><li>For app-level integration types, a source-event is required.</li><li>If value is false, neither source\_event nor event\_name is required.</li></ul> |
| source\_event | <ul><li>Relevant only for aggregate-level S2S API partner integrations.</li><li>For app-level integration types, if enabled is set to true, a source\_event is required.</li></ul> |

</Accordion>

<Accordion title="Get API">

**To get a list of your ad revenue partner integrations via API**:

1. [Get your API V2 token](/docs/managing-appsflyer-tokens) from the AppsFlyer dashboard. Required for API authorization.
2. Tell your developer to follow the [List integrations API instructions](https://dev.appsflyer.com/hc/reference/post_integrations) in the dev hub.

</Accordion>

### Specs and limitations

| **Spec** | **Remarks** |
| --- | --- |
| Call limit | Up to 1,000 integrations within a single call. |
| OAuth | Partners that are integrated via OAuth (like Google and Facebook) aren't supported. |