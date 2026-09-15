---
title: "Bulletin: New Push API fields"
excerpt: "Three new fields have been added to the AppsFlyer Push API: engagement_type, event_type, and store_product_page."
---
Three new fields have been added to the push API. They are:
- engagement_type
- event_type
- store_product_page (new for Android)

### engagement_type

The parameter can return the following values: preload, click_to_download, click_to_app, engaged_click, engaged_view, view, listening, or if not reported it will be empty

More information on the new engagement types can be found [here](https://support.appsflyer.com/hc/articles/20161875390865).

### event_type

The parameter can return the following values: install, organic-install, install-in-app-event, organic-install-in-app-event, re-engagement, re-engagement-in-app-event, re-attribution, reinstall, organic-reinstall, re-attribution-in-app-event, skad-installs, skad-re-downloads, skad-in-app-events, skad-postbacks, skad-postbacks-copy.

### store_product_page

This parameter follows the current iOS values.

For more information click [here](/docs/raw-data-field-dictionary#attribution::4c11e393).

> 📘 Note
>
> The **custom_data** field has been changed to include a colon between the field name and the field value.

### Effective date

January 17, 2024

### What this impacts

Advertisers and agencies using the [push API](/docs/push-api-streaming-raw-data)