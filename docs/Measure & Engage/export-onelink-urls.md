---
title: "Export OneLink URLs"
excerpt: "Learn how to download a CSV file containing all the OneLink URLs created in the AppsFlyer user interface."
---
At a glance: Download all OneLink URLs created in the AppsFlyer user interface.

## Export OneLink URLs

Download a CSV file of all the OneLink URLs created per OneLink template using the OneLink setup in the AppsFlyer user interface. (OneLink URLs created via SDK, OneLink API, or bulk upload, aren't exported).

The CSV file contains info regarding each link as follows:

- Link name
- Media source
- Campaign name
- Short URL
- Long URL
- Date last modified/created (MM:DD:YY HH:MM)
- Modified by (email)

[Sample CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vR02eohAyUA2fsr9iGEb0UiZI8v45wH58KGo-45wajF4KNGuk_2S_cY1WW3UV8LwPRg-wm9bkMjvWyZ/pub?output=csv)

> 📘 Note
>
> If a link is initially created in the AppsFlyer UI, but the parameters are then updated outside the UI (using OneLink API, a spreadsheet, etc.), the updated parameters are not part of the downloaded CSV.

**To download the CSV**:

1. In AppsFlyer, go to **Experiences & Deep Linking** > **OneLink Custom Links**.
2. Select the OneLink template you want a list of links for.
3. Click **Export**.

The CSV file is downloaded.

### Traits and limitations

| **Trait** | **Remarks** |
| --- | --- |
| Agencies | Can only get the links they created based on the OneLink template. |
| Advertisers | Can only get the links they created based on the OneLink template. |