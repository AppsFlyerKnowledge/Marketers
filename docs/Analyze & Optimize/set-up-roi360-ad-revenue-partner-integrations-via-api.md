---
title: "Set up ROI360 ad revenue partner integrations via API"
excerpt: "Configure and manage your AppsFlyer ad revenue partner integrations at the account or app level using the API."
---
**At a glance:** Configure ad revenue partner integrations for your AppsFlyer account or individual apps via API.

## Ad revenue partner integration API

The ad revenue partner integration API is used to:

- Set app-level ad revenue partner configurations for your entire account.
- Get a list of current ad revenue partner configurations for your entire account.

### Set API

**To set (configure) ad revenue partner integrations via API**:

1. [Get your API V2 token](https://support.appsflyer.com/hc/articles/360004562377) from the AppsFlyer dashboard. Required for API authorization. 

> 📘 Note
>
> This must be done by the account admin.

2. Prepare the parameters to include in the API request, as described in the table that follows.
3. Give the parameter values your developer and tell them to follow the [Set integrations API instructions](https://dev.appsflyer.com/hc/reference/post_integrations) in the dev hub.

Integration takes effect at 00:00 UTC the following day.

#### Request parameters

| Parameter | Description |
| --- | --- |
| integrations | - Top-level object that must include app\_id, network, andproducts (listed below).<br>- Other fields could include credentials, event\_name, and source\_event. |
| app\_id | The app ID for the app you want to integrate. |
| network | - The partner you want to integrate. <br>- For a list of supported networks, see the network column of the [Ad revenue partner API parameter table](https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx). |
| credentials | - 1 or more credentials required for the network integration.<br>- For the list of credentials, see the cred columns of the [Ad revenue partner API parameter table](https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx). |
| event\_name | - Default value: af\_ad\_revenue<br>- Can also be a custom event name [beta]<br>- event\_name isn't required if enabled is set to false. |
| products | - List of all enabled products under an integration, including the parameters name, enabled, and if relevant, source\_event (listed below).<br>- For a list of supported products per network, see the bulk API products column of the [Ad revenue partner API parameter table](https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx). |
| name | - The name of the integration type.<br>- For a list of integration type names, see the bulk API products column of the [Ad revenue partner API parameter table](https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx). |
| enabled | - Possible values:<br>  - true<br>  - false<br>- For app-level integration types, a source-event is required.<br>- If value is false, neither source\_event nor event\_name is required. |
| source\_event | - Relevant only for aggregate-level S2S API partner integrations.<br>- For app-level integration types, if enabled is set to true, a source\_event is required. |

### Get API

**To get a list of your ad revenue partner integrations via API**:

1. [Get your API V2 token](https://support.appsflyer.com/hc/articles/360004562377) from the AppsFlyer dashboard. Required for API authorization.
2. Tell your developer to follow the [List integrations API instructions](https://dev.appsflyer.com/hc/reference/post_integrations) in the dev hub.

### Specs and limitations

| **Spec** | **Remarks** |
| --- | --- |
| Call limit | Up to 1,000 integrations within a single call. |
| OAuth | Partners that are integrated via OAuth (like Google and Facebook) aren't supported. |