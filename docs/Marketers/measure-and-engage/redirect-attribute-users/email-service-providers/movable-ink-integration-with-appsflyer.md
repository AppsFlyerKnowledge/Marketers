---
title: Movable Ink integration with AppsFlyer
excerpt: >-
  Set up an integration with Movable Ink to create unique AI-powered user
  journeys in your marketing campaigns and in-app content.
metadata:
  keywords:
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2024-09-05T11:55:13Z'
  edited_at: '2025-11-12T14:40:50Z'
  id: 28109258392977
  locale: en-us
  section: Email service providers
  section_id: 6551247620881
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/28109258392977-Movable-Ink-integration-with-AppsFlyer
---
## ![53374 Movable Ink KB image.png](https://files.readme.io/0f1a5d3d6b60cccdb8be113c9fd4f3603c7c3ed0ad8573a153709391d29b2c3b-28624891792401.png)

## About the integration

Movable Ink is a dynamic content optimization partner that provides personalized customer experiences in various channels, such as emails, push notifications and SMS. The integration between AppsFlyer and Movable Ink enables you to create uniquely personalized AI-powered journeys in your marketing campaigns and in-app content.

## Set up the integration

**Prerequisites**

* For email campaigns, you'll need to have your email service provider (ESP) integration in place.  
  A list of AppsFlyer-supported ESPs can be found [here.](/docs/email-service-provider-esp-integration-guide)
* Integration of the AppsFlyer [URL Resolver code](https://github.com/AppsFlyerSDK/appsflyer-urlresolver-client) snippet into your mobile apps (it is responsible for resolving the Movable Ink wrapped link).
* OneLink is set up and supports Universal Links/App Links. [Learn more](/docs/create-a-onelink-template#create-a-onelink-template)

**To set up the integration:**

1. **In Movable Ink:** Sign in to your Movable Ink account (for help, contact your Movable Ink representative or their client experience team).
2. Create your content in **Studio** and finalize your campaign set up.
3. Get the Movable Ink link for email campaign usage:
   * * Navigate to the **Finish & Export** page.
     * Click on the three dots (“…”) under the section **Copy Creative Tag** and choose **Copy Link URL**.   
       **Note:** Finalize your campaign setup before copying the link URL.
     * Copy the HREF URL from the copied link (highlighted) and set it aside. It will be used as the deep link value in the final link.   
       ![Movableink image highlighted.png](https://files.readme.io/a2ccca4d6053e1448094dd83478610693b13a7f04a77aaaff7d12305533e8fbe-28405439389201.png)
4. **In AppsFlyer:** Navigate to the specific [OneLink template](/docs/create-a-onelink-template) that you'll use for the campaign and retrieve the following data points for the integration:
   * * **OneLink Domain:** The subdomain for OneLink generation within AppsFlyer.
     * **Template ID:** ID of the referenced template or the one created for the campaign.
     * **PID**: The unique identification of the media source.  
       The recommended value is the ESP name.
5. Put together your link using the link structure below. 

   **Link structure:**

   https://`{{onelink.domain}}/{{template_id}}?pid={{pid_value}}&c={{link_name}}deep_link_value={{mi_link_from_creative_tag}}`

   **Example:**

   Here's an example of what a link looks like after adding the required parameters from the table below.

   https://link.movableink.com/oskuw854?pid=BRAZE&deep_link_value=https://www.movable-ink-2563.com/p/cp/ee0e28529389f573/c?url=https%3A%2F%2Fwww.movable-ink-2563.com%2Fp%2Frp%2F9011ea048ec4bf03%2Furl&url_sig=D4QtmtC8vqJhU7

   

| Parameter | Description | Example value | Note | Get from |
| --- | --- | --- | --- | --- |
| `{{onelink.domain}}` | Your AppsFlyer domain | mink.onelink.com |  | AppsFlyer UI |
| `{{template_id}}` | ID of the link template set up in AppsFlyer | 1a6f |  | AppsFlyer UI |
| `{{pid_value}}` | ID of the ESP / media source | ESP Name |  | AppsFlyer UI |
| `{{mi_link_from_creative<br /><br />_tag}}` | The HREF clickthrough link from Movable Ink’s creative tag. Available on the Finish & Export page (see image in step 3.) | https://www.movable-ink-2563<br /><br />.com /p/cp /ee0e28529389f573<br /><br />/curl=https %3A%2 F%2Fwww.<br /><br />movableink2563 .com %2Fp%2<br /><br />Frp%2F9011ea048e c4b f03%2<br /><br />Furl&url \_sig=D4QtmtC8vqJhU7 | The link should be encoded. | Movable Ink |

   > 📘 **Note**
   >
   > If the values for `af_android_url`, `af_ios_url`, and `af_web_dp` are identical, you can shorten the link by using `af_r instead`. If there is another parameter with the same value, ask your AppsFlyer customer success manager to activate the parameter duplication feature.

6. Use the new link in your campaign.  
   **Note:** The Movable Ink HREF link that you copy/pasted into your link should be encoded. However, **if using the link in an email campaign via your ESP, the ESP parameters should not be encoded**.

## Traits and limitations

See additional [attribution link traits and limitations](/docs/about-link-structure-and-parameters#traits-and-limitations).

<div data-zendesk-anchors="h_01J8HQFV2ZYYN7G1FDA1DH1GV3=about-the-integration h_01J8HX53FVT1N4MG2HPE743RTS=about-the-integration h_01J710N8QBFHSX9BS6H0NFY918=set-up-the-integration 01J9GSWGHBA01N227MCEV91YMV=note h_01J9GAS3T6STFKHD4C6Z6GYFMF=traits-and-limitations" />
