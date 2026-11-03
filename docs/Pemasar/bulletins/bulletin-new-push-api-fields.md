---
title: 'Bulletin: New Push API fields'
metadata:
  keywords:
    - Marketers
    - Raw Reports
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Raw Reports
  created_at: '2023-11-15T10:46:08Z'
  edited_at: '2023-12-12T09:37:55Z'
  id: 20161752179601
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/20161752179601-Bulletin-New-Push-API-fields
---
| **What's new** | Three new fields have been added to the push API. They are:<ul><li>engagement\_type</li><li>event\_type</li><li>store\_product\_page (new for Android)</li></ul>**<span id="engagement_type"></span>engagement\_type**<br /><br />The parameter can return the following values: preload, click\_to\_download, click\_to\_app, engaged\_click, engaged\_view, view, listening, or if not reported it will be empty<br /><br />More information on the new engagement types can be found <Anchor target="_blank" href="/marketers/id/docs/bulletin-engagement-types">here</Anchor>.<br /><br />**<span id="event_type"></span>event\_type**<br /><br />The parameter can return the following values: install, organic-install, install-in-app-event, organic-install-in-app-event, re-engagement, re-engagement-in-app-event, re-attribution, reinstall, organic-reinstall, re-attribution-in-app-event, skad-installs, skad-re-downloads, skad-in-app-events, skad-postbacks, skad-postbacks-copy.<br /><br />**<span id="store_product_page"></span>store\_product\_page**<br /><br />This parameter follows the current iOS values.<br /><br />For more information click <Anchor target="_blank" href="/marketers/id/docs/raw-data-field-dictionary#attribution::4c11e393">here</Anchor>.<br /><br /><br /><br />**<span id="h_01HHEP7BBXF30VEK3XCSSK9GEE"></span>Note**<br />The **custom\_data** field has been changed to include a colon between the field name and the field value. |
| --- | --- |
| **Effective date** | January 17, 2024 |
| **What this impacts** | Advertisers and agencies using the <Anchor target="_blank" href="/marketers/id/docs/push-api-streaming-raw-data">push API</Anchor> |

<div data-zendesk-anchors="h_01HF9A6PNHDEQR9GVVW49ADB1E=engagement_type h_01HF9A6TA5Y3D485BFJ5FF42H6=event_type h_01HF9A6XV28CYDEPAZ352VY44K=store_product_page" />
