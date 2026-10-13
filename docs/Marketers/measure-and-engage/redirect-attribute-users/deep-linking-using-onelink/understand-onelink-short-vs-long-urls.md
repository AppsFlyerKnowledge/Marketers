---
title: "Understand OneLink short vs. long URLs"
excerpt: "Understand the difference between OneLink short and long URLs, and how to create long URLs outside of AppsFlyer."
x-zendesk:
  id: 360017132597
  url: https://support.appsflyer.com/hc/en-us/articles/360017132597-Understand-OneLink-short-vs-long-URLs
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Deep linking using OneLink
  section_id: 6551203111057
  position: 12
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-asaf-mashiah, Marketers, QR-to-App]
  labels: [Marketers, parameters]
  promoted: false
  comments_disabled: true
  created_at: '2021-01-26T09:39:19Z'
  edited_at: '2026-08-17T13:50:28Z'
---
**At a glance:** Understand the difference between OneLink short and long URLs, and how to create long URLs outside of AppsFlyer.

## **About OneLink links**

* Work across all media marketing channels to redirect users to either: 
  * The correct URL/app store.
  * Open the app, and then deep link users to a specific in-app activity.
* Can support brand customization. Meaning the URL has your [brand domain](/docs/brand-onelink-with-your-domain), instead of the OneLink subdomain.
* Can be either short or long URLs:
  * Short URLs are created in AppsFlyer (either [in the UI](/docs/onelink-guide), or via [API](/docs/use-onelink-api-to-create-links-in-large-scale-campaigns) or [SDK](/docs/user-invite-attribution)).
  * Long URLs:
    * Can be created in the AppsFlyer UI or outside of AppsFlyer.
    * Contain any parameters you want.
    * Can be used to generate a large number of OneLink custom links by applying your own simple formulas in a spreadsheet.   
      **Notes**:
      * Links created in a spreadsheet are not visible (and cannot be edited) in any AppsFlyer UI.
      * This spreadsheet method is different from [Perform OneLink bulk actions via CSV](/docs/perform-onelink-bulk-actions-via-csv), which creates bulk short URLs.
    * Don't expire, meaning there is no Time to Live (TTL) limitation.  
      **Long URL considerations:**
    * Long URLs are transparent, meaning all link parameters are visible to the public, and can potentially be manipulated.
    * Long URLs may not fit into browsers, SMS, or other places with URL character limitations.

### Advantages of a short OneLink URL compared to a long URL

* Updating parameters in the OneLink short URL within the AppsFlyer dashboard does not change the shortlink ID, so there’s no need to replace or redistribute the URL or any associated QR codes, even if already in use.
* AppsFlyer seamlessly applies the updated parameters for attribution and reporting, ensuring the QR code remains functional and automatically reflects the changes.

## Procedures

**To create a OneLink long URL outside the AppsFlyer UI:**

1. Create a [OneLink template](/docs/create-a-onelink-template#procedures).
2. Record the OneLink base URL, meaning the OneLink template domain + template ID.  
   Example:
   * OneLink template domain: `yourbrand.onelink.me`
   * Template ID: `1a6f`
   * OneLink base URL: `yourbrand.onelink.me/1a6f`
   * Branded domain example: `yourbrand.com/1a6f`
3. Append a `?` to the URL, followed by any parameters you want to add.
   * See [list of AppsFlyer parameters](/docs/about-link-structure-and-parameters).
   * To add more than one parameter, use `&`.  
     Example: `yourbrand.onelink.me/1a6f?pid=email&c=freestuff`

**To get the long URLs for OneLink custom links you create in the AppsFlyer UI:**

1. In AppsFlyer, go to **OneLink custom links**.  
   The list of OneLinks displays.  
   [![](https://files.readme.io/53bd68c390389e48eb55802418c601e7523ab7d816d21c1ae672ed55d7ade365-360016243798.jpg)](https://files.readme.io/53bd68c390389e48eb55802418c601e7523ab7d816d21c1ae672ed55d7ade365-360016243798.jpg)
2. Go to the link for which you want the long URL, and in the **Actions** column, click **Get URL**.  
   The long URL displays.