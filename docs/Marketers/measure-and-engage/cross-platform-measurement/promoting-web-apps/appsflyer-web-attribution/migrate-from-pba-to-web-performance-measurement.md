---
title: Migrate from PBA to Web Performance Measurement
excerpt: >-
  People-Based Attribution (PBA) is being replaced by Web Performance
  Measurement, AppsFlyer upgraded web measurement solution. This article covers
  what's changing, the migration steps, and the full field mapping for your
  reports and server-side integrations.
metadata:
  keywords:
    - Developers
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-07-26T11:53:06Z'
  edited_at: '2026-09-07T13:34:12Z'
  id: 49156441281425
  locale: en-us
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/49156441281425-Migrate-from-PBA-to-Web-Performance-Measurement
---
## Why we're upgrading your web measurement

Web measurement matters more than ever. The website is where many of your users convert and where the path to your mobile app begins. It isn't just a landing page; it's a full acquisition funnel of quiz flows, personalized onboarding, paywalls, and web stores that often win higher-intent users at a lower acquisition cost.

AppsFlyer is bringing web measurement up to the same standard as mobile. People-Based Attribution (PBA), the legacy web product, is being replaced by Web Performance Measurement, built on top of AppsFlyer core attribution engine and unified data model. Web Performance Measurement matches everything PBA does today and adds:

* **One source of truth**, web and mobile app measurement in one place, with cost aggregation, optimization postbacks, and creative optimization together.
* **Better budget decisions**, flexible attribution that matches your business logic, so you double down on the campaigns that actually work.
* **Improved ROAS**, enriched optimization postbacks to your ad networks, and a full server-side setup that measures more conversions, so networks can optimize using better signals.
* **True cross-platform ROI**, measure every user journey across web, app, and any platform.
* **Simple, unified reporting**, one dashboard, and one set of data reports for every platform, refreshed hourly.

You don't need to replace your Web SDK. Web Performance Measurement uses the same SDK, with no code changes to your website. The effort involved in the rest of the switch varies, depending on how you currently receive your data, through the dashboard, Data Locker, or the Server-to-server (S2S) API.

## Comparing PBA and Web Performance Measurement

This section compares PBA and Web Performance Measurement in two ways: overall capabilities and traffic source resolution.

### Web Performance Measurement vs. PBA

The table below compares PBA and Web Performance Measurement capabilities across data, reporting, and attribution.

<table><tbody><tr><td>Capability</td><td>Description</td><td>PBA</td><td>Web Performance Measurement</td></tr><tr><td colspan="4"><strong>Data</strong></td></tr><tr><td>Data freshness</td><td>How quickly is data available for reporting</td><td><span><strong>✗</strong></span> Daily</td><td><span><strong>✓</strong></span> Hourly reports, approximately 2 hours of data freshness</td></tr><tr><td>Data model</td><td>Schema alignment with mobile attribution data</td><td><span><strong>✗</strong></span> Different from mobile</td><td><span><strong>✓</strong></span> Aligned with mobile, easy to join, and analyze</td></tr><tr><td colspan="4"><strong>Reporting</strong></td></tr><tr><td>Activity dashboard</td><td>Dashboard based on event time</td><td><span><strong>✓</strong></span> Supported</td><td><span><strong>✓</strong></span> Supported</td></tr><tr><td>Cohort dashboard</td><td>Analyze performance by acquisition cohort over time</td><td><span><strong>✗</strong></span> Not supported</td><td><span><strong>✓</strong></span> Supported</td></tr><tr><td>Data Locker raw data</td><td>Access to raw attribution data via Data Locker export</td><td><span><strong>✓</strong></span> Supported</td><td><span><strong>✓</strong></span> Supported</td></tr><tr><td>Ad-level granularity</td><td>Report breakdown from the campaign down to the ad level</td><td><span><strong>✗</strong></span> Dashboard only, not in raw data</td><td><span><strong>✓</strong></span> Full campaign granularity on both the dashboard and raw data</td></tr><tr><td>Cross-platform LTV</td><td>Stitch web and mobile user journeys into unified LTV</td><td><span><strong>✗</strong></span> Not supported</td><td><span><strong>✓</strong></span> Supported</td></tr><tr><td colspan="4"><strong>Cost and signals</strong></td></tr><tr><td>Web cost</td><td>Ingest and report on ad spend for web campaigns</td><td><span><strong>✗</strong></span> Not supported</td><td><span><strong>✓</strong></span> Supported</td></tr><tr><td>Optimization postbacks</td><td>Send optimization signals back to ad networks</td><td><span><strong>✗</strong></span> Not supported</td><td><span><strong>✓</strong></span> Supported</td></tr><tr><td colspan="4"><strong>Implementation</strong></td></tr><tr><td>Web SDK (Pixel)</td><td>Client-side SDK for measuring web visits and events</td><td><span><strong>✓</strong></span> Supported</td><td><span><strong>✓</strong></span> Same SDK, no code changes required</td></tr><tr><td>S2S support</td><td>Full server-side measurement for visits and events</td><td><span><strong>✗</strong></span> Events only</td><td><span><strong>✓</strong></span> Events and visits. Supports a full server-side implementation.</td></tr><tr><td colspan="4"><strong>Attribution engine</strong></td></tr><tr><td>Attribution windows</td><td>Configurable lookback, attribution, re-engagement, and inactivity windows</td><td><span><strong>✗</strong></span> Click lookback window only</td><td><span><strong>✓</strong></span> 5 configurable windows (full control)</td></tr><tr><td>Custom UA event</td><td>Define what event counts as a User Acquisition (UA) event beyond the first visit</td><td><span><strong>✗</strong></span> First visit only</td><td><span><strong>✓</strong></span> Any custom event (for example, sign-up, purchase)</td></tr><tr><td>UA vs. retargeting</td><td>Separate credit for new acquisition vs. re-engagement</td><td><span><strong>✗</strong></span> No UA concept, events attributed to last touch</td><td><span><strong>✓</strong></span> Dedicated UA and retargeting views with dual attribution credit</td></tr></tbody></table>

### Traffic source resolution, PBA vs. Web Performance Measurement

If media source, channel, or campaign values differ from what PBA reported, here's why. Both use the same underlying approach: they resolve the media source from URL parameters and the referrer at the web visit by walking a priority list until the first match wins. But several rules changed, and those changes move the values you see in reporting, based on [PBA media source attribution rules](/docs/pba-media-source-attribution-rules) and [About traffic source resolution](/docs/about-traffic-source-resolution).

<Accordion title="Media source values renamed">

| Trigger | PBA value | New value |
| --- | --- | --- |
| Google display/video (utm\_source=Google + utm\_medium= cpm / display/banner/video/listing) | `doubleclick_int` | `dv360_int` |
| Twitter via UTM (twitter + cpc) | X Ads | Twitter |

Web Performance Measurement also remaps more PID values to display names, for example, `iossearchads_int` to Apple Search Ads, `metweb_int` to Facebook Ads, `twitterweb_int` to Twitter, `tiktokweb_int` to `tiktokglobal_int`, `snapweb_int` to `snapchat_int`. Reports built on the old raw values need to expect the new ones.

</Accordion>

<Accordion title="Click ID coverage expanded, and dclid dropped">

PBA resolved three click IDs: `gclid` to `googleadwords_int`, `dclid` to `doubleclick_int`, and `msclkid` to `bingsearch_int`.

Web Performance Measurement resolves many more, `gclid`/`wbraid`/`gbraid` to `googleadwords_int`, `msclkid` to `bingsearch_int`, `twclid` to Twitter, `vmcid` to `yahoogemini_int`, `sccid` to `snapchat_int`, `li_fat_id` to `linkedin_int`, `ttclid` to `tiktokglobal_int`, `tbclid` to `taboola_int`, `ob_click_id`/`dicbo` to `outbrain_int`, `yclid` to `yandex_int`, `rdt_cid` to `reddit_int`.

Two behavior changes: dclid is no longer used for resolution on its own (PBA resolved it to doubleclick\_int), and fbclid is explicitly not used.

</Accordion>

<Accordion title="UTM custom rules expanded">

The custom `utm_source` + `utm_medium` mapping is broader in Web Performance Measurement: it includes more medium synonyms (paid, paid\_search, paid-search, etc.) and added coverage for TikTok, Snapchat, and Pinterest beyond PBA's narrow single-medium rules. Where no custom rule matches, both fall back to the raw `utm_source` value.

</Accordion>

<Accordion title="Channel">

Channel **values** also change format, from PBA's Direct / Organic search / Social media / Email / Ad / Referral / Other to the new DIRECT / ORGANIC\_SEARCH / SOCIAL\_MEDIA / EMAIL / AD / REFERRAL / OTHER. Filters and groupings keyed on the old labels need updating.

</Accordion>

## Migrate to Web Performance Measurement

Migration has one required step for everyone. After that, perform the steps that apply to your PBA setup.

**Expect differences in the numbers (everyone)**

PBA's numbers won't exactly match those you'll get after the migration. The attribution logic in Web Performance Measurement is more advanced and more flexible. PBA applied its own media source attribution rules; Web Performance Measurement uses improved traffic source resolution. See "Traffic source resolution, PBA vs. Web Performance Measurement" below, for what values to expect. Session recording logic itself is unchanged; a session still runs for 30 minutes of activity, the market standard.

### Step 1. Create a web app (required, everyone)

1. [Create the new web app](/docs/adding-an-app-to-appsflyer#web), selecting your existing web Dev Key in the **Web SDK ID** field. This keeps your current website code working as-is, with no code changes.
2. [Configure the attribution settings](/docs/configure-web-performance-measurement-settings) on the new app.

### Step 2. If you send events through the S2S API

Migrate to the new S2S API:

1. Review [PBA Web-S2S to new S2S API migration](#pba-web-s2s-to-new-s2s-api-migration) for what's different from your current PBA S2S integration, endpoints, authentication, and payload fields.
2. Set up the [new S2S API](/docs/server-to-server-s2s-api-for-web-performance-measurement) for Web Performance Measurement.
3. Update your server-side integration to send to the new endpoints.

### Step 3. If you consume PBA's raw data reports

Move to the new Data Locker reports. The End User Events report replaces [PBA's Website visits and Website events reports](/docs/pba-raw-data-reports).

1. Confirm you have Data Locker. If you don't, you'll need to add it to your account or purchase it.
2. Review [Raw data field mapping](#raw-data-field-mapping) for the full field-level mapping, renamed, redefined, or deprecated fields.
3. Enable the new report using [Export AppsFlyer Web Attribution report data from Data Locker](/docs/export-web-performance-measurement-report-data-from-data-locker).
4. Point your BI/ETL to the new report location and fields. This applies whether your events arrive via SDK or S2S; both land in the same raw report.

### Step 4. If you use the PBA Brand Bundle for cross-platform reporting

1. [Create a product line](/docs/product-line-group-apps-for-cross-platform-attribution).
2. Group your web app with your other apps under that product line to unlock [cross-platform user LTV reporting](/docs/beta-user-based-cross-platform-attribution).

## Capabilities being discontinued

| Capability | What changes | Details |
| --- | --- | --- |
| Conversion path | Already deprecated. | N/A |
| Web-assisted installs (credit to a web campaign that helped drive a later mobile install) | No dedicated "web-assisted installs" view. | Web-to-app journeys are measured with Smart Script and Smart Banner. The cross-platform report provides a similar, though not identical, analysis. Like PBA, it's based on the Customer User Identifier (CUID):<ul><li>Web campaigns that assisted an install previously reported as organic now appear as non-organic user acquisition. These aren't assists; the web campaign is the acquisition source.</li><li>Web campaigns that assisted a non-organic install: the web campaign serves as user acquisition, and the mobile install serves as cross-platform retargeting.</li></ul> |
| Backward recalculation | No backward recalculation beyond the default 30-minute delay. | Attribution is finalized after a 30-minute delay, giving users time to identify themselves during that window. |
| Raw data fields | Mobile-related fields are deprecated for the web. Some fields are renamed, and some values change. | See [Raw data field mapping](#raw-data-field-mapping) for the full field mapping. |
| Late S2S events | Events that arrive later than 30 minutes after the end of the UTC day in which they occurred are still accepted, but their event time is replaced with the time AppsFlyer received them. | Send events in real time, preferably within 30 minutes of the event occurring, rather than batching them into a single daily upload. Accurate attribution depends on receiving events close to when they happen. This aligns the web with the existing mobile behavior. |

## Raw data field mapping

If you already consume PBA's Website visits and Website events raw data reports, here's what changes. The report itself moves to Data Locker, and this is the complete field-by-field mapping to the new End User Events report, based on [PBA raw data reports](/docs/pba-raw-data-reports).

Raw data for any platform and cross-platform reporting are available only through Data Locker. See step 3 or step 4 above if you don't have Data Locker yet.

* **Unchanged**, same field name and data.
* **Renamed**, same data, new column name.
* **Redefined**, same or similar name, but the data or value format changes (needs care before reuse).
* **Deprecated**, no equivalent in the new report.

| Field name | Description | Status | New field/note |
| --- | --- | --- | --- |
| `advertising_id` | Advertising ID (GAID) | Deprecated | Mobile/device advertising ID, stitched cross-platform in PBA. Cross-platform LTV and user journey reports are CUID-based and don't use this field. |
| `af_web_id` | Cookie ID sent from the web SDK | Renamed | `appsflyer_id_value`, same web cookie. |
| `amazon_aid` | Amazon Fire TV advertising ID | Deprecated | Mobile/device ID, not relevant for web. |
| `android_id` | Android device ID | Deprecated | Mobile/device ID, not relevant for web. |
| `app_id` | Most recent app ID installed | Deprecated | Mobile cross-platform field. The web app identifier in the new report is `unified_app_id` ("website-`{domain}`"), a different concept. |
| `app_name` | Most recent app name | Unchanged | `app_name`. |
| `app_version` | Most recent app version | Deprecated | Mobile cross-platform field, not relevant for web. |
| `appsflyer_id` | AppsFlyer (install) ID | Deprecated | Mobile install ID. The new `appsflyer_id_value` is the web cookie (`af_web_id`), a distinct identifier. |
| `attributed_touch_time` | Timestamp of the (attributed) web visit | Renamed | `event_time__attribution`, the attributed touch (engagement) time. |
| `attributed_touch_type` | Type of touchpoint, always "web visit" | Deprecated | Constant value in PBA. Visit-vs-event now lives in `end_user_event_type` (SESSION / IN\_APP). |
| `bundle_id` | PBA bundle ID | Deprecated | Replaced by the Product Line grouping (web + mobile apps) in the cross-platform report. |
| `campaign` | Attributed to the website visit | Renamed | `campaign_name`. |
| `campaign_id` | Attributed to the website visit | Unchanged | `campaign_id`. |
| `city` | Resolved using the IP address | Unchanged | `city`. |
| `country_code` | Resolved using the IP address | Unchanged | `country_code`. |
| `customer_user_id` | Customer User Identifier (CUID) | Unchanged | `customer_user_id`. |
| `device_type` | The type of device | Renamed | `device_category`, values differ ("Desktop" vs. "MOBILE\_PHONE" / "TV"). |
| `dma` | Resolved using the IP address | Unchanged | `dma`. |
| `event_name` | Visits: always "website visit". Events: event name sent | Redefined | Empty on visits (PBA wrote "website visit"). Unchanged for events. |
| `event_revenue` | Event revenue amount in purchase currency | Renamed | `revenue_value_original`. |
| `event_revenue_currency` | 3-digit currency code of `event_revenue` | Renamed | `revenue_currency_original`. |
| `event_revenue_usd` | `event_revenue` converted to USD | Renamed | `revenue_usd`. |
| `event_source` | Either the web SDK or Server-to-server | Unchanged | `event_source`. |
| `event_time` | Visits: time of visit. Events: time of event | Unchanged | `event_time`. |
| `event_type` | Standard event/conversion event/website visit | Redefined | Conversion-event marking no longer exists. Visit-vs-event lives in `end_user_event_type` (SESSION / IN\_APP). |
| `event_url` | URL of the webpage where the event occurred (equals Original URL on visits) | Unchanged | `event_url`, now also the main place to read URL query params (UTMs, etc.). |
| `event_value` | Events: event details as JSON. Visits: null | Unchanged | `event_value`. |
| `idfa` | Advertising identifier | Deprecated | Mobile/device ID, not relevant for web. |
| `idfv` | Advertising identifier | Deprecated | Mobile/device ID, not relevant for web. |
| `imei` | Device identifier | Deprecated | Mobile/device ID, not relevant for web. |
| `install_time` | Most recent app install time | Deprecated | Mobile cross-platform field. The web user-acquisition (conversion) time is `event_time__conversion` a separate concept. |
| `ip` | Visitor IP address | Renamed | `ip_address_value`, same value, plus `ip_address_type` for the hashing method. |
| `language` | Reported by user agent (for example, "English") | Redefined | `language`, value format changes to ISO 639-1 and country code. |
| `media_channel` | Attributed to the website visit ("Ad") | Deprecated | Can be covered by `sub_param_1-5` if needed. |
| `media_source` | Attributed to the website visit | Unchanged | `media_source`. |
| `media_type` | Attributed to the website visit ("Paid") | Deprecated | Empty for web. Organic vs. paid now comes from the `is_organic` boolean. |
| `oaid` | Advertising identifier | Deprecated | Mobile/device ID, not relevant for web. |
| `original_url` | URL that redirected the user on the attributed visit | Renamed | Consolidated into `event_url` (on visits, `event_url` equals the original URL). The standalone column is gone. |
| `platform` | The platform ("macOS", "Windows") | Redefined | The platform is always "WEBSITE". The OS moved to `os_version` / `user_agent`. |
| `postal_code` | Resolved using the IP address | Unchanged | `postal_code`. |
| `query_params` | Query params on the redirecting URL, as JSON | Deprecated | The raw query string lives in `event_url`. The parsed-JSON column is gone. |
| `referrer` | HTTP referrer of the attributed website visit | Renamed | `http_referrer`. |
| `region` | Resolved using the IP address ("NA") | Renamed | `continent`, continent code, for example, "NA". |
| `state` | Resolved using the IP address | Unchanged | `state`. |

<Accordion title="Ready-to-use coding-agent prompt for Data Locker ETL migration">

To make this transition easier, we've prepared a ready-to-use prompt for your AI coding agent (Claude Code, Cursor, or similar). Give the agent access to your existing ETL code and paste the prompt below; it contains the full field mapping and every behavioral difference. It will guide the agent to learn your current pipeline and rebuild it for the new report.

```
You are migrating an ETL pipeline from AppsFlyer's legacy PBA Data Locker raw-data reports (Website visits + Website events) to AppsFlyer's Web Performance Measurement Data Locker report (End User Events). Everything you need is in this prompt: the structural changes, the complete field-by-field mapping, and the validation steps. Do not guess anything beyond what is written here; if something is ambiguous, ask me.

## Step 1: Learn the current pipeline

Before writing any code, explore the existing codebase and produce an inventory:
1. Which PBA reports we consume (Website visits, Website events, or both) and where they are ingested.
2. Every PBA field we read, and where each is used downstream (transforms, joins, dashboards, alerts, exports).
3. The load cadence and scheduling assumptions (PBA delivered daily).
4. Any logic that separates or joins visit rows and event rows.
5. Any filters, groupings, or hardcoded values keyed on PBA field values (for example, media_source names, channel labels, event_type, platform values).

Present this inventory to me and wait for my confirmation before proceeding.

## Step 2: Ask me these questions

1. Is the new End User Events report already enabled in Data Locker (enabled from the AppsFlyer UI)? If not, I need to enable it first.
2. What is our new web app's Unified App ID? Format: "website-{domain}" (for example, website-www.example.com). If I don't know it, I'll get it from the AppsFlyer dashboard before we continue.
3. Do we want a parallel-run period (old and new pipelines side by side, comparing outputs) or a direct cutover? Recommend parallel-run.
4. Should the new pipeline also consume the Conversions report (unique attribution instances, no duplicate rows) or the cross-platform End User Events report (CUID-deduplicated, web+mobile user-level)? Default scope is the platform-level End User Events report, the direct successor of the PBA reports.

## Structural changes to design around

1. **One report instead of two.** PBA split visits and events into two reports. The new End User Events report holds both: visits are rows with end_user_event_type = 'SESSION', events are rows with end_user_event_type = 'IN_APP'. Only IN_APP rows carry a valid event_name; on SESSION rows event_name is empty (PBA wrote "website visit" there).
2. **One schema across platforms.** The report is shared by website, mobile, CTV, and PC. Always filter platform = 'WEBSITE' to isolate web data.
3. **Dual attribution credit, deduplicate.** The same action can appear twice: a primary-credit row and a secondary-credit row (original UA source, for UA-view LTV). Filter is_primary_attribution = true by default to avoid double-counting. Drop the filter only for dedicated UA-view vs retargeting-view analysis using conversion_type.
4. **Hourly instead of daily.** The new report delivers hourly with approximately 2 hours of data freshness. Redesign incremental loads around hourly batches instead of a daily drop.
5. **Organic vs paid.** PBA's media_type ("Paid") is gone. Use the is_organic boolean; never infer organic/paid from media_source.
6. **User counting.** Count and join users with COALESCE(customer_user_id, appsflyer_id_value), the stable customer user ID first, the cookie-based ID as fallback.
7. **Empty values.** STRING fields are '', NUMERIC fields are NULL.

## Field-by-field mapping (PBA → End User Events)

Status legend: Unchanged = same name and data. Renamed = same data, new column. Redefined = data or value format changes (handle with care). Deprecated = no equivalent.

| PBA field | Status | New field / handling |
|---|---|---|
| advertising_id | Deprecated | Mobile/device ID. Cross-platform reports are CUID-based; drop it. |
| af_web_id | Renamed | appsflyer_id_value, same web cookie. |
| amazon_aid | Deprecated | Mobile/device ID, not relevant for web. |
| android_id | Deprecated | Mobile/device ID, not relevant for web. |
| app_id | Deprecated | Mobile cross-platform field. The new web app identifier is unified_app_id ("website-{domain}"), a different concept, not a rename. |
| app_name | Unchanged | app_name. |
| app_version | Deprecated | Mobile cross-platform field. |
| appsflyer_id | Deprecated | Mobile install ID. Note: the new appsflyer_id_value is the web cookie (PBA's af_web_id), NOT this field. |
| attributed_touch_time | Renamed | event_time__attribution. |
| attributed_touch_type | Deprecated | Was a constant. Visit-vs-event now lives in end_user_event_type. |
| bundle_id | Deprecated | Replaced by the Product Line grouping in the cross-platform report. |
| campaign | Renamed | campaign_name. |
| campaign_id | Unchanged | campaign_id. |
| city | Unchanged | city. |
| country_code | Unchanged | country_code. |
| customer_user_id | Unchanged | customer_user_id. |
| device_type | Renamed + values change | device_category, values differ (for example, "Desktop" → "MOBILE_PHONE" / "TV" style values). Update any value-keyed logic. |
| dma | Unchanged | dma. |
| event_name | Redefined | Events: unchanged. Visits: now empty (PBA wrote "website visit"). Use end_user_event_type = 'SESSION' to identify visits. |
| event_revenue | Renamed | revenue_value_original. |
| event_revenue_currency | Renamed | revenue_currency_original. |
| event_revenue_usd | Renamed | revenue_usd. |
| event_source | Unchanged | event_source. |
| event_time | Unchanged | event_time. |
| event_type | Redefined | "Conversion event" marking no longer exists. Visit-vs-event lives in end_user_event_type (SESSION / IN_APP). |
| event_url | Unchanged | event_url, now also the main place URL query params (UTMs, etc.) are read from. |
| event_value | Unchanged | event_value. |
| idfa / idfv / imei / oaid | Deprecated | Mobile/device IDs, not relevant for web. |
| install_time | Deprecated | Mobile field. The web user-acquisition time is event_time__conversion, a separate concept. |
| ip | Renamed | ip_address_value (plus ip_address_type for the hashing method). |
| language | Redefined | language, format changes to ISO 639-1 + country code (was, for example, "English"). |
| media_channel | Deprecated | Can be covered by sub_param_1-5 if needed. |
| media_source | Unchanged | media_source (but see value renames below). |
| media_type | Deprecated | Use the is_organic boolean instead. |
| original_url | Renamed | Consolidated into event_url (on visits, event_url equals the original URL). Standalone column gone. |
| platform | Redefined | platform is always "WEBSITE". The OS moved to os_version / user_agent. |
| postal_code | Unchanged | postal_code. |
| query_params | Deprecated | The raw query string lives in event_url; the parsed-JSON column is gone. Re-implement parsing from event_url if needed. |
| referrer | Renamed | http_referrer. |
| region | Renamed | continent, continent code (for example, "NA"). |
| state | Unchanged | state. |

## Attributed-value changes (update filters and groupings)

The attribution engine resolves traffic sources differently, so some VALUES change even where field names don't:
- media_source renames: doubleclick_int → dv360_int (Google display/video via UTM); "X Ads" → "Twitter" (Twitter via UTM). More PID values now remap to display names (for example, iossearchads_int → Apple Search Ads, metweb_int → Facebook Ads, tiktokweb_int → tiktokglobal_int, snapweb_int → snapchat_int).
- Channel labels change format: Direct / Organic search / Social media / Email / Ad / Referral / Other become DIRECT / ORGANIC_SEARCH / SOCIAL_MEDIA / EMAIL / AD / REFERRAL / OTHER.
- Click-ID coverage expanded (more networks resolve from click IDs); dclid alone no longer resolves; fbclid is not used.

Scan the codebase for any filter, CASE, join key, or dashboard grouping keyed on these old values and update them.

## Step 3: Build

1. Propose the new ETL design (ingestion, schema, incremental hourly logic, the mandatory filters from "Structural changes").
2. After my approval, implement it, reusing our existing conventions and infrastructure.
3. For every Deprecated field the inventory found in downstream use, list the consumer and propose a resolution (drop, replace with the suggested alternative, or flag to the business owner).

## Step 4: Validate

1. Run both pipelines on the same day range and compare: visits (SESSION rows) vs PBA website visits, events (IN_APP rows) vs PBA website events, and revenue totals.
2. Expect differences, not equality: the new attribution logic is more advanced, so attributed dimensions (media_source, campaign) will not match PBA exactly. Session counting logic is unchanged (30 minutes of activity), so expect visit volumes to stay in the same ballpark.
3. Verify the is_primary_attribution filter is applied everywhere; its absence shows up as inflated event counts.
4. Produce a short migration report: what was mapped, what was dropped, what changed in values, and any open items for the business owner.
```

</Accordion>

## PBA Web-S2S to new S2S API migration

If you report events to PBA through the [Web Server-to-server events API (Web-S2S)](/docs/web-server-to-server-events-api-for-pba-web-s2s), move to the [new S2S API](/docs/server-to-server-s2s-api-for-web-performance-measurement). The new API supports both visits and events, so your website can run fully server-side; PBA's S2S accepts only events.

<Accordion title="Endpoints and authentication">

|  | PBA Web-S2S | New S2S API |
| --- | --- | --- |
| Base URL | `https://webs2s.appsflyer.com` | `https://events.appsflyer.com` |
| Event call | `POST /v1/{bundleId}/event` | `POST /v2.0/s2s/inapps/app/web/{appId}` |
| Visit call | Not available (visits came from the Web SDK only) | `POST /v2.0/s2s/visits/app/web/{appId}` |
| Identity call | `POST /v1/{bundleId}/setcuid` (separate call to associate a CUID with a web user) | None, identity is sent inline in the `user_id` object on every event/visit |
| App identifier | `bundleId` (brand bundle ID) in the path | `appId` = the web `unified_app_id` ("website-`{domain}`") in the path |
| Authentication | `webDevKey` inside the JSON body on every call | Authorization header carrying the S2S API key |
| Content type | `application/json` | `application/json` |
| Success response | 200 OK | 202 Accepted |

</Accordion>

<Accordion title="Payload field mapping">

| PBA Web-S2S field | New S2S field | Note |
| --- | --- | --- |
| `customerUserId` | `user_id.customer_user_id` | Now nested in the `user_id` object. |
| `afUserId` | `user_id.appsflyer_id` | Now nested in the `user_id` object. Send at least one of `customer_user_id` or `appsflyer_id`; send both whenever the user is identified. |
| `webDevKey` | N/A | Removed from the body. Authentication moved to the Authorization header; the app is identified by `appId` in the path. |
| `eventType` (always EVENT) | N/A | Removed. The endpoint (/inapps vs. /visits) determines the type. |
| `eventName` | `event_name` | 1-64 chars; cannot contain `@ = + -`. |
| `timestamp` (Unix ms, 13 digits) | `timestamp` (Unix ms) | Same format. Recommended on every call; if omitted, AppsFlyer uses the receive time. |
| `eventValue` | `event_value` | Free-form; supports a `custom_parameters` sub-object. |
| `eventRevenue` | `event_revenue` | Now optional (PBA required it for dashboards). |
| `eventRevenueCurrency` | `event_revenue_currency` | Now optional (PBA required it for dashboards). |
| `referrer` | `http_referrer` | Renamed. |
| `userAgent` | `user_agent` | Renamed. |
| `ip` | `ip` | Unchanged. |
| N/A | `event_url` | New. Required on visits; optional on events. |
| N/A | `customer_dedup_id` | New. Deduplicates against the same event arriving from another source (for example, the Web SDK). |
| N/A | `email_hashed`, `phone_number_hashed`, `phone_number_e164_hashed`, `first_name_hashed`, `last_name_hashed` | New. SHA256 (64-char lowercase hex) of normalized values, for identity enrichment. |

</Accordion>

<Accordion title="S2S API notes">

* **Visits are now server-side.** PBA's S2S only accepted events; visits had to come from the Web SDK. The new /visits endpoint lets the website run fully server-side.
* **No more setcuid call.** PBA required the Web SDK, so a separate call was needed to tie a CUID to a web user. The new API carries identity inline on every request, so that step is dropped.
* **Late data window.** Send events and visits in real time, preferably within 30 minutes of the event occurring, rather than batching them into a single daily upload. Data that arrives later than 30 minutes after the end of the UTC day in which the event occurred is still accepted, but its event time is replaced with the time AppsFlyer received it.

</Accordion>

<Accordion title="S2S service migration: ready-to-use coding-agent prompt">

If you report events through the PBA Server-to-server API, we've prepared a ready-to-use prompt for your AI coding agent (Claude Code, Cursor, or similar). Give the agent access to the service that sends events to AppsFlyer and paste the prompt below; it contains the full endpoint and payload mapping. It will guide the agent to learn your current implementation and build the updated one.

```
You are migrating a server-side integration from AppsFlyer's legacy PBA Web S2S events API (webs2s.appsflyer.com) to AppsFlyer's new S2S API for Web Performance Measurement (events.appsflyer.com). Everything you need is in this prompt: endpoints, authentication, the complete payload mapping, and the behavior changes. Do not guess anything beyond what is written here; if something is ambiguous, ask me.

## Step 0: Ask me these questions before touching code

1. Should we modify the existing service in place, or create a new service/module alongside it (allowing a parallel-run and clean cutover)? Recommend a new module alongside.
2. Do I know our new web app's Unified App ID? Format: "website-{domain}" (for example, website-www.example.com). It replaces PBA's bundle ID in the URL path. If I don't know it, I'll get it from the AppsFlyer dashboard before we continue.
3. Do I have the new S2S API key? Authentication moved from the webDevKey in the request body to an Authorization header carrying this key. If I don't have it, I'll retrieve it from the AppsFlyer dashboard.
4. Do we want to send events only (like PBA), or adopt the new visits endpoint too? The new API supports server-side visits, so the website can run fully server-side; PBA accepted events only.
5. Is the AppsFlyer Web SDK still running on our site? (Determines whether visits come from the SDK and whether we need event deduplication between SDK and S2S.)

## Step 1: Learn the current service

Explore the codebase and produce an inventory:
1. Every call site to webs2s.appsflyer.com, the /event calls and any /setcuid calls.
2. The fields populated on each call (customerUserId, afUserId, eventName, eventValue, eventRevenue, timestamp, referrer, userAgent, ip, etc.) and where their values come from.
3. Error handling and monitoring keyed on the 200 OK response.
4. Retry, batching, and queueing behavior.

Present this inventory to me and wait for my confirmation before proceeding.

## What changed: endpoints and authentication

|  | PBA Web-S2S (old) | New S2S API |
|---|---|---|
| Base URL | https://webs2s.appsflyer.com | https://events.appsflyer.com |
| Event call | POST /v1/{bundleId}/event | POST /v2.0/s2s/inapps/app/web/{appId} |
| Visit call | Not available | POST /v2.0/s2s/visits/app/web/{appId} |
| Identity call | POST /v1/{bundleId}/setcuid | None, identity is inline in the user_id object on every call |
| App identifier in path | bundleId (brand bundle ID) | appId = the web Unified App ID ("website-{domain}") |
| Authentication | webDevKey in the JSON body | Authorization header with the S2S API key |
| Content type | application/json | application/json (415 if missing) |
| Success response | 200 OK | 202 Accepted |

## Payload field mapping

| PBA field | New field | Note |
|---|---|---|
| customerUserId | user_id.customer_user_id | Nested in the user_id object. |
| afUserId | user_id.appsflyer_id | Nested in the user_id object. Send at least one of customer_user_id or appsflyer_id; send both whenever the user is identified. |
| webDevKey | (removed) | Auth moved to the Authorization header; the app is identified by appId in the path. |
| eventType (always "EVENT") | (removed) | The endpoint (/inapps vs /visits) determines the type. |
| eventName | event_name | 1-64 chars; cannot contain @ = + - characters. |
| timestamp (Unix ms) | timestamp (Unix ms) | Same format. Recommended on every call; if omitted, AppsFlyer uses receive time. |
| eventValue | event_value | Free-form; supports a custom_parameters sub-object. |
| eventRevenue | event_revenue | Now optional (PBA required it for dashboards). |
| eventRevenueCurrency | event_revenue_currency | Now optional (PBA required it for dashboards). |
| referrer | http_referrer | Renamed. |
| userAgent | user_agent | Renamed. |
| ip | ip | Unchanged. |
| (new) | event_url | Required on visits; optional on events. |
| (new) | customer_dedup_id | Deduplicates against the same event arriving from another source (for example, the Web SDK). |
| (new) | email_hashed, phone_number_hashed, phone_number_e164_hashed, first_name_hashed, last_name_hashed | SHA256 (64-char lowercase hex) of normalized values, for identity enrichment. |

## Behavior changes and gotchas

1. **appId is the Unified App ID, not the "Web SDK ID".** The AppsFlyer app settings page shows a "Web SDK ID" UUID (the former Web Dev Key, kept for SDK continuity). The S2S path must carry the Unified App ID ("website-{domain}"), never that UUID. A 401 "app not found" usually means a wrong appId in the path or a missing/invalid Authorization header.
2. **Success is 202, not 200.** Update health checks, retries, and alerting accordingly.
3. **Don't validate against the old endpoint.** The legacy endpoint may still return 200, but that response is not proof that data reached Web Performance Measurement. Always verify events actually appear in the new web app's data.
4. **Drop the setcuid flow entirely.** Identity travels inline in the user_id object on every event and visit.
5. **Visits before events.** The system expects a visit before any event from a user; events for a user with no prior visit are classified as organic. Visits come from the Web SDK, or, new, from the /visits endpoint.
6. **Send in real time; don't batch.** Send every event and visit as it happens, preferably within 30 minutes of the event occurring. Data that arrives later than 30 minutes after the end of the UTC day in which the event occurred is still accepted, but its event time is replaced with the receive time, which distorts attribution. Always send a timestamp. Note that the approximately 30-minute attribution delay you may read about is a separate, server-side hold on AppsFlyer's side, nothing for us to implement.
7. **Full server-side option (if we adopt visits).** With no Web SDK, our server owns the web user identifier: generate a stable ID for first-time visitors, persist it as a server-set first-party HTTP cookie (Set-Cookie header, not JavaScript; JS cookies are capped at approximately 7 days on Safari), reuse it on every request, and send it as user_id.appsflyer_id. The visit payload must include event_url, and we recommend also including ip, user_agent, and http_referrer for attribution quality.
8. **SDK + S2S together.** If both send the same event, populate customer_dedup_id so AppsFlyer keeps one copy.

## Step 2: Build

1. Propose the design: new client/module, config (base URL, appId, API key storage in our secrets manager, never hardcoded), payload builders for events (and visits, if in scope), and the response/retry handling for 202.
2. After my approval, implement it following our existing conventions.
3. Map every field from the inventory through the payload mapping above; flag any field we currently send that has no new equivalent.

## Step 3: Validate

1. Send a test event (and visit, if in scope) and confirm a 202 response.
2. Verify the test data appears in the new web app in AppsFlyer (dashboard or Data Locker); this is the real success signal, not the HTTP response.
3. Confirm event names comply with the new constraints (1-64 chars, no @ = + -).
4. If running in parallel with the old service, compare event volumes between old and new for a few days before cutover, then decommission the old calls including setcuid.
```

</Accordion>

<div data-zendesk-anchors="h_01KYM7JM37WVTV7XHEHVTPKWM9=why-were-upgrading-your-web-measurement h_01KYM7JM3711FXC132MSC3B4A9=comparing-pba-and-web-performance-measurement h_01KYM7JM3711FXC132MSC3B4A8=web-performance-measurement-vs-pba h_01KYM7JM387R5YEYJK9CD0AQJ0=traffic-source-resolution-pba-vs-web-performance-measurement h_01KYM7JM37HG8YAX02XMSKBTPP=migrate-to-web-performance-measurement h_01KYM7JM37HG8YAX02XMSKBTPP01=step-1-create-a-web-app-required-everyone create-a-web-app=step-1-create-a-web-app-required-everyone h_01KYM7JM37HG8YAX02XMSKBTPP02=step-2-if-you-send-events-through-the-s2s-api if-you-send-events-through-the-s2s-api=step-2-if-you-send-events-through-the-s2s-api h_01KYM7JM37HG8YAX02XMSKBTPP03=step-3-if-you-consume-pbas-raw-data-reports if-you-consume-pbas-raw-data-reports=step-3-if-you-consume-pbas-raw-data-reports h_01KYM7JM37HG8YAX02XMSKBTPP04=step-4-if-you-use-the-pba-brand-bundle-for-cross-platform-reporting if-you-use-pba-brand-bundle-for-cross-platform-reporting=step-4-if-you-use-the-pba-brand-bundle-for-cross-platform-reporting h_01KYM7JM37JJ25D3RFE2V7BM4D=capabilities-being-discontinued h_01KYM7JM37Z7Z21FJ2G83T2WPG=raw-data-field-mapping h_01KYM7JM38K9C01XDZY99KZVTX=pba-web-s2s-to-new-s2s-api-migration" />
