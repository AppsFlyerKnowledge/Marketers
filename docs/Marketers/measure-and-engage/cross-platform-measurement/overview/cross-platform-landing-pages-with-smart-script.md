---
title: Cross-platform landing pages with Smart Script
metadata:
  keywords:
    - CTV
    - Marketers
    - gaming
    - cross-platform
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2023-09-10T07:17:21Z'
  edited_at: '2024-06-01T10:37:30Z'
  id: 18440789126289
  locale: en-us
  section: Overview
  section_id: 15323084579345
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/18440789126289-Cross-platform-landing-pages-with-Smart-Script
---
> **At a glance:** Use a cross-platform landing page running the AppsFlyer Smart Script to perform web-to-app attribution. Meaning, convert users who see a web ad from any media source into app users on CTV, PC, console, or mobile platforms.

<div id="overview" />

## Overview

With a cross-platform landing page running the AppsFlyer Smart Script, you can perform web-to-app attribution. This means you can attribute installs on any platform to ads displayed on web.

The Smart Script in a cross-platform landing page uses the incoming link (the link on the web ad) to do 2 things that ensure the original media source and web ad are attributed with the install:

* Create a cross-platform OneLink link that sends an impression to AppsFlyer.
* Create direct attribution links for each app/platform.

<div id="setup" />

## Setup

<div id="scope-of-work" />

#### SCOPE OF WORK

| **Who's involved**<ul><li>**Advertiser**:<ul><li>Decides what the outgoing [cross-platform impression](#create-crossplatform-impression-link) and [direct attribution links](#create-direct-attribution-links) should contain based on the <Anchor target="_blank" href="/marketers/docs/set-up-smart-script-to-convert-web-visitors#arguments">arguments</Anchor> in the Smart Script. This determines the attribution data that gets appended to the outgoing URL, either by manipulating the incoming URL or by forcing certain values.</li><li>Makes sure all campaigns leading to the website have incoming URLs with parameters that the script can process.</li><li><Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html">Tests the Smart Script</Anchor>.</li></ul></li><li>**Web developer**:<ul><li>Adds the arguments to the script and implements the Smart Script on the landing page.</li><li>Tests the Smart Script.</li></ul></li></ul> |
| --- |
| **Prerequisites**<ul><li>An AppsFlyer account with at least one app.</li><li>For the impression URL: A <Anchor target="_blank" href="/marketers/docs/create-a-onelink-template#create-a-onelink-template">OneLink template</Anchor> with cross-platform attribution enabled.</li></ul> |

<div id="create-crossplatform-impression-link" />

<Accordion title="Create cross-platform impression link">

**To create a cross-platform OneLink link that sends an impression to AppsFlyer**:

1. Map incoming link parameters to the parameters that the impression link should contain (for media source, campaign, ad name, etc.).
   * Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-smart-script-to-convert-web-visitors#arguments">arguments</Anchor> in the script that process the incoming URL.
   * The value of the <Anchor target="_blank" href="/marketers/docs/set-up-smart-script-to-convert-web-visitors#arguments">OneLinkURL argument</Anchor> is the domain+ID of the OneLink template with cross-platform attribution enabled.
2. Tell your developer to initialize the Smart Script arguments and call the Smart Script method `generateOneLinkURL`. <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">See developer demo and instructions</Anchor>.  
   **Note:** The `af_xplatform=true` parameter is mandatory to enable cross-platform attribution.

</Accordion>

<div id="create-direct-attribution-links" />

<Accordion title="Create direct attribution links">

1. Map incoming link parameters to the parameters that the outgoing direct attribution links should contain (media source, campaign, ad name, etc.). Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-smart-script-to-convert-web-visitors#arguments">arguments</Anchor> in the script that process the incoming URL.
2. Tell your developer to initialize the Smart Script arguments,and run the Smart Script method`generateDirectClickURL` to create a link for each platform/app. See developer <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">demo</Anchor> and <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/create-direct-click-url">instructions</Anchor>.  
   **Note:** The developer should add the following parameters:  

| Parameter/Argument | Remarks | Record your responses (for you or your developer to use) |
| --- | --- | --- |
| platform | A string describes the platform and must be from this list:<ul><li>smartcast</li><li>tizen</li><li>roku</li><li>webos</li><li>vidaa</li><li>playstation</li><li>android</li><li>ios</li><li>steam</li><li>quest</li><li>battlenet</li><li>nativepc</li></ul> |  |
| app\_id | <ul><li>App ID</li><li>Example: 123456</li></ul> |  |
| redirectURL | <ul><li>The URL to which the platform/app user should be redirected.</li><li>Example: `https://store.steampowered.com/app/123456/Team_Fortress_2/`</li></ul> |  |

</Accordion>

<div data-zendesk-anchors="01H8V0RV7X8JEVEJ36TJB1X43D=overview 01H8V0RV7X0K157JTDQMJSQYKF=setup h_01H95PGMNWPBRHSZBPMKNJ2PS6=scope-of-work 01H8EQ4KS75Q62Z7WVNSTDXBZX=create-crossplatform-impression-link 01H8EQ4KS7C6HADNKQZYNTTFMF=create-direct-attribution-links" />
