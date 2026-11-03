---
title: Understand OneLink short vs. long URLs
metadata:
  keywords:
    - Marketers
    - parameters
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2021-01-26T09:39:19Z'
  edited_at: '2026-10-13T01:36:05Z'
  id: 360017132597
  locale: zh-cn
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/zh-cn/articles/360017132597
---
> **At a glance:** Understand the difference between OneLink short and long URLs, and how to create long URLs outside of AppsFlyer.

## **About OneLink links**

* Work across all media marketing channels to redirect users to either: 
  * The correct URL/app store.
  * Open the app, and then deep link users to a specific in-app activity.
* Can support brand customization. Meaning the URL has your <Anchor target="_blank" href="/marketers/zh/docs/brand-onelink-with-your-domain">brand domain</Anchor>, instead of the OneLink subdomain.
* Can be either short or long URLs:
  * Short URLs are created in AppsFlyer (either <Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">in the UI</Anchor>, or via <Anchor target="_blank" href="/marketers/zh/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API</Anchor> or <Anchor target="_blank" href="/marketers/zh/docs/user-invite-attribution">SDK</Anchor>).
  * Long URLs:
    * Can be created in the AppsFlyer UI or outside of AppsFlyer.
    * Contain any parameters you want.
    * Can be used to generate a large number of OneLink custom links by applying your own simple formulas in a spreadsheet.   
      **Notes**:
      * Links created in a spreadsheet are not visible (and cannot be edited) in any AppsFlyer UI.
      * This spreadsheet method is different from <Anchor target="_blank" href="/marketers/zh/docs/perform-onelink-bulk-actions-via-csv">Perform OneLink bulk actions via CSV</Anchor>, which creates bulk short URLs.
    * Don't expire, meaning there is no Time to Live (TTL) limitation.  
      **Long URL considerations:**
    * Long URLs are transparent, meaning all link parameters are visible to the public, and can potentially be manipulated.
    * Long URLs may not fit into browsers, SMS, or other places with URL character limitations.

### Advantages of a short OneLink URL compared to a long URL

* Updating parameters in the OneLink short URL within the AppsFlyer dashboard does not change the shortlink ID, so there’s no need to replace or redistribute the URL or any associated QR codes, even if already in use.
* AppsFlyer seamlessly applies the updated parameters for attribution and reporting, ensuring the QR code remains functional and automatically reflects the changes.

## Procedures

**To create a OneLink long URL outside the AppsFlyer UI:**

1. Create a <Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#创建onelink模板">OneLink template</Anchor>.
2. Record the OneLink base URL, meaning the OneLink template domain + template ID.  
   Example:
   * OneLink template domain: `yourbrand.onelink.me`
   * Template ID: `1a6f`
   * OneLink base URL: `yourbrand.onelink.me/1a6f`
   * Branded domain example: `yourbrand.com/1a6f`
3. Append a `?` to the URL, followed by any parameters you want to add.
   * See <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">list of AppsFlyer parameters</Anchor>.
   * To add more than one parameter, use `&`.  
     Example: `yourbrand.onelink.me/1a6f?pid=email&c=freestuff`

**To get the long URLs for OneLink custom links you create in the AppsFlyer UI:**

1. In AppsFlyer, go to **OneLink custom links**.  
   The list of OneLinks displays.  
   [![](https://files.readme.io/53bd68c390389e48eb55802418c601e7523ab7d816d21c1ae672ed55d7ade365-360016243798.jpg)](https://files.readme.io/53bd68c390389e48eb55802418c601e7523ab7d816d21c1ae672ed55d7ade365-360016243798.jpg)
2. Go to the link for which you want the long URL, and in the **Actions** column, click **Get URL**.  
   The long URL displays.

<div data-zendesk-anchors="onelink-long-urls=about-onelink-links 01JBXQENR6QHQ1HXQQQ5NBBMKN=about-onelink-links h_01JGXTFWS509NW0ESM1CZZ1KZM=advantages-of-a-short-onelink-url-compared-to-a-long-url h_01JBXQTQ3DXPTP9BY06QKXN3NP=procedures" />
