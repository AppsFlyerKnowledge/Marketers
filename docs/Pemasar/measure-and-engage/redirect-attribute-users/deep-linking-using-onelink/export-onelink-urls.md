---
title: Export OneLink URLs
metadata:
  keywords:
    - export
    - Marketers
    - download
    - Link Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Link Management
  created_at: '2022-01-09T11:58:46Z'
  edited_at: '2026-10-01T13:43:04Z'
  id: 4416027813905
  locale: en-us
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4416027813905-Export-OneLink-URLs
---
> **At a glance:** Download all OneLink URLs created in the AppsFlyer user interface.

<div id="export-onelink-urls" />

## Export OneLink URLs

Download a CSV file of all the OneLink URLs created per OneLink template using the OneLink setup in the AppsFlyer user interface. (OneLink URLs created via SDK, OneLink API, or bulk upload, aren't exported).

The CSV file contains info regarding each link as follows:

* Link name
* Media source
* Campaign name
* Short URL
* Long URL
* Date last modified/created (MM:DD:YY HH:MM)
* Modified by (email)

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR02eohAyUA2fsr9iGEb0UiZI8v45wH58KGo-45wajF4KNGuk_2S_cY1WW3UV8LwPRg-wm9bkMjvWyZ/pub?output=csv">Sample CSV</Anchor>

**Note**: If a link is initially created in the AppsFlyer UI, but the parameters are then updated outside the UI (using OneLink API, a spreadsheet, etc.), the updated parameters are not part of the downloaded CSV.

**To download the CSV**:

1. In AppsFlyer, from the side menu, select **Engage** > **OneLink Management**.
2. Select the OneLink template you want a list of links for.
3. Click **Export**.  
   The CSV file is downloaded.

<div id="traits-and-limitations" />

### Traits and limitations

| **Trait** | **Remarks** |
| --- | --- |
| Agencies | Can only get the links they created based on the OneLink template. |
| Advertisers | Can only get the links they created based on the OneLink template. |

<div data-zendesk-anchors="h_01HKA1YMN4J2HAXWWF00252XC3=export-onelink-urls h_01HKA1YMN4P9AR949BFCSG93VY=traits-and-limitations" />
