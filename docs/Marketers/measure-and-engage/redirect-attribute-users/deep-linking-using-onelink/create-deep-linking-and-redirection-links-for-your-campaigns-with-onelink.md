---
title: "Create deep linking and redirection links for your campaigns with OneLink"
excerpt: "Create links that give users exactly the experience you want them to have, with OneLink, redirecting them to the correct app store, web URL, or into the app."
---
**At a glance:** Create links that give users exactly the experience you want them to have, with OneLink. Users who click the link are redirected to the correct app store, web URL, or into the app, and attributed to the media source.

## OneLink links and experiences

<Embed title="Create deep linking and redirection links for your campaigns with OneLink" typeOfEmbed="youtube" url="https://www.youtube.com/embed/KZBrxGEjVUE" providerUrl="https://www.youtube.com" />

Your customers interact with your brand across many different online and offline touchpoints. No matter where your users come from, you can create a link that provides the perfect experience for them, from click, to app install, to deep linking to deferred deep linking.

The steps required to set up a link are described in detail in the section that follows, but basically, they include the following:

* Selecting a user experience
* General settings
* Experience-specific settings
* Deep linking and redirections settings
* Additional parameter settings

## Create a OneLink link

| **Who's involved**<br /><br />* Only a marketer is required to create OneLink links with an experience that redirects users to app stores, web URL, or, once the template is set up to open the app with Android App Links and iOS Universal Links, into the home page of the app.<br />* To add deep linking and deferred deep linking functionality to links, both a marketer and Android/iOS developers are required. |
| --- |
| **Prerequisites**<br /><br />* An AppsFlyer account with at least one app.<br />* A [OneLink template](/docs/create-a-onelink-template) on which to base your links.<br />* For attribution: [The AppsFlyer SDK already installed](/docs/integrate-the-appsflyer-sdk) in each of your mobile apps.<br />  * If the SDK is not yet installed in your apps, it is still possible to create a working redirection link, but it will not be possible to measure installs in your dashboard, deep link, or deferred deep link. |
| **Time required**<br /><br />30 minutes for most links, but approximately 3 hours for links that require deep linking or deferred deep linking functionality. |
| **Outcome**<br /><br />* A link that sends users to the correct app store, web page, or into the app based on their device, and gives them exactly the experience you want them to have. |

**Create OneLink links from your AI tool**

You can also create OneLink links by describing them in plain language in an AI tool connected to the [AppsFlyer MCP](/docs/beta-appsflyer-mcp "/docs/beta-appsflyer-mcp")[.](/docs/beta-appsflyer-mcp) For example: "Create a link for our Black Friday email newsletter that opens the sale page in the app." The AI maps your request to the right parameters, shows you the link details, and creates the link only after you approve. Links are created under an existing OneLink template. [Learn more](/docs/beta-appsflyer-mcp#h_01JY3VJEQMRDFAFTKZMPZ90RHP)

**To create a OneLink link with a specific user experience:**

1. In AppsFlyer, from the side menu, select **Engage** > **OneLink management**.
2. Select the **OneLink template** to add a custom link for.
3. Click **Add link**.
4. Select the [experience](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#experiences) you want to create for your users.
5. Select a media source or enter a custom media source. This is the media source under which data displays in AppsFlyer. The media source is included in your link as the `pid` parameter value.

   CALLSTART::Note::

   #### Note

   AppsFlyer blocks attribution links that use reserved [SRN](/docs/self-reporting-networks-srns#srns-integrated-with-appsflyer) names as PID values in owned media sources, such as email and SMS. This restriction does not apply to ASRNs.

   CALLEND::
6. Click **Next**.
7. Complete [General settings](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings).
8. Click **Next**.
9. [Optional] Complete the procedures relevant to the user experience you're creating:

   

| Experience | Procedure options |
| --- | --- |
| * Social-to-app<br />* Text-to-app<br />* Referral to app<br />* Custom link | * [Social media preview](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags)<br />* [Social app landing page](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page) |
| Email-to-app | If you're using an ESP, follow the [ESP integration instructions](/docs/email-service-provider-esp-integration-guide). |
| App-to-app | You can create dynamic links that work across multiple apps via [cross-promotion](/docs/cross-promotion-attribution-for-marketers). |
| Referral-to-app | * [Social media preview](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags)<br />* [Social app landing page](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page)<br />* You can dynamically create referral-to-app links via the SDK in your app via [user invite integration](/docs/user-invite-attribution). |

10. Click **Next**.
11. [Optional] In **Deep linking and redirection**, complete [deep linking/deferred deep linking setup](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking). Skip this section if this link isn't intended for deep linking.
12. [Optional] In **Deep linking and redirection**, change the [redirection settings](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#redirection). Skip this section if the redirection settings from the OneLink template are correct.
13. Click **Next**.
14. In **Additional parameters**, [add predefined or custom parameters](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#additional-parameters) to your link for more granular analysis. [Learn more about attribution parameters](/docs/about-link-structure-and-parameters)
15. Click **Generate link**.
16. Make sure your [domain redirect allowlist](/docs/set-up-your-domain-redirect-allowlist) is updated with all domains you want to redirect users to.

### Experiences

You can create links for the following user experiences:

* **Social-to-app**: Engage your users on social media and send them from social media posts to your app.
* **App-to-app**: Send users to your app via ads that they see in other apps.
* [**QR-to-app**](/docs/qr-to-app-conversion): Use QR codes to drive app installs by having users scan a QR code at key points during their offline customer experience. You can also put QR codes on your desktop site, or on TV and CTV ads to route users to your app.
* **Email-to-app**: Use email service providers (ESPs) to engage users via email and send them from their inbox to your app.
* **Text-to-app**: Create links for your SMS and messaging campaigns and engage users via texts messages.
* **Referral-to-app**: Create user invite links that allow users or influencers to invite others to your app or share specific in-app content, for example, an article.
* **Custom link**: For user journeys that don't fit one of the experiences mentioned above, you can create a OneLink custom link. Then, no matter where your users come from, whether via desktop or mobile, online or offline, owned or paid media, you can easily send them to the right place.

### General settings

General settings is a section of the OneLink link creation process that applies to all experiences.

**To complete the general settings**:

1. [Optional] Change the media source name.
2. [Optional] Change the campaign name.
3. [Optional] Turn on **Retargeting** if you plan to use this link to target existing users.

   This enables you to see the re-engagements performed by users clicking on your custom link.

   Existing users that click on non-retargeting links (UA) also launch the app, and have the same user experience. However, their re-engagements are recorded as regular sessions, which means it's impossible to measure the success of the owned media campaign.

   CALLSTART::Note::

   #### Important!

   For retargeting to work, you also need to enable retargeting for the app.

   CALLEND::
4. [Optional] Turn on **Ignore active users for retargeting** and select the inactivity window.  
   This adds the parameter af\_inactivity\_window=[number of days] to your link, and all users active during the period are ignored for retargeting.
5. Set the re-engagement window to determine the time period following the re-engagement, where the user's in-app events are attributed to the retargeting media source.
   * You can set the value in days (1-90), hours (up to 23), or even lifetime.
   * The re-engagement window is added to the link in the af\_reengagement\_window parameter.
6. [Optional] In the **Link branding** subsection:
   * Select a different domain to reflect your brand. [Learn more](/docs/brand-onelink-with-your-domain)
   * Edit the URL ID to highlight the campaign offering. The URL ID must be maximum 50 characters and can be a combination of letters and numbers. By default, it is 8 characters.

#### Enable retargeting for the app

If Retargeting was never enabled for the app, you need to do it once. [Learn more](/docs/app-settings#attribution-settings)

**To set Retargeting at the app level:**

1. In AppsFlyer, from the side menu, select **Settings** > **App Settings**.
2. In the **Attribution** section, enable **Re-engagement attribution**.
3. Click **Save settings**.

### Social media preview - OG tags

When a link is shared, open graph (OG) tags are used to generate a preview with a title, description, and image.

These OG tags may automatically be taken from the web URL or app store you are redirecting to. However, sometimes this method of generating a preview fails. Therefore, we recommend setting your social media previews in OneLink, either using the OneLink UI, or, for links not created in the OneLink UI, by adding OG tag parameters to your link.

**To create your own social media preview in the OneLink UI:**

1. In your OneLink custom link editor, go to the **Share on social media** section.
2. In the **Social media preview** section, select **Default preview (from website/store)** to use OG tags from your destination URL, or **Custom preview (image and tags)** to set your own.
3. If you selected **Custom preview (image and tags)**, enter a:
   * Title
   * Description
   * Image URL
4. [Optional] Review the **Template favicon** field.
   * This shows the favicon configured in your OneLink [template settings](/docs/create-a-onelink-template#set-a-favicon-for-link-previews). It displays automatically in link previews on supported platforms.
   * To change the favicon, go to your [template settings](/docs/create-a-onelink-template#set-a-favicon-for-link-previews).
   * If no favicon is shown, none has been configured on the template yet. You can still use Custom preview without a favicon.

**To add OG tag parameters to your link**(if it was not created in the OneLink UI)**:**

* Add the following required parameters:
  * af\_og\_title (up to 40 characters)
  * af\_og\_description (up to 300 characters)
  * af\_og\_image

> 📘 **Note**
>
> * You can add the OG tag parameters to your link outside the AppsFlyer UI.
> * If you add separate OG tags for X (formerly Twitter), they will override the regular AppsFlyer preview.

### Social app landing page

> 📘 **Important!**
>
> iOS Universal Links are now supported in Meta ads.
>
> * As Meta now [supports universal links](/docs/meta-ads-faq#are-ios-universal-links-and-android-app-links-supported-in-meta-ads), a social app landing page is no longer required for Meta paid ads that support universal links.
> * A social app landing page is needed for owned posts (non paid ads).

Social media apps may break the smooth experience of existing users using Universal Links. This can be overcome by:

* [**Recommended**] Creating a social app landing page.  
  When creating a social media app landing page, we recommend making sure you have a URI scheme configured.  
  **Note:** X (formerly Twitter) doesn't support URI schemes for iOS. A Social app landing page with Universal Links should be used to avoid app-launching issues.
* [Alternative] [Forcing the app to open](/docs/onelink-troubleshooting-and-faq#forced-deep-linking) using the `af_force_deeplink=true` parameter.  
  **Note**: This parameter is automatically enabled for Kakaotalk, Naver, Naver-Blog, Chrome, Weibo, and X (formerly Twitter).

With a social app landing page, users who click ads in social media apps are redirected to an AppsFlyer-generated landing page. From there, they can be deep linked, or continue to install the app.

AppsFlyer provides a variety of social app landing page templates. Element positions in the templates are fixed, but the elements themselves are customizable, including background image or color, titles, texts, images, buttons, tags, and more.

The social app landing page can be used with the following social media apps:

* Instagram
* Facebook/Facebook Messenger (**Note**: For Facebook and Facebook Messenger, if both URI scheme and a Social app landing page are set up, the Social app landing page doesn't display.)
* LinkedIn
* Pinterest for iOS
* Snapchat
* X (formerly Twitter)
* WeChat

**User experience**

When the user engages with the CTA button in the landing page:

* **If app is installed**: the clicking user launches the app.
* **If app is NOT installed**: the user is taken to the relevant app store. Upon install, it's possible to defer deep linking the user (explained in [deep linking and deferred deep linking](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking)).

> 📘 **Note**
>
> The social app landing page only supports OneLink short URL.

#### **To use the social app landing page:**

1. Configure the landing page as described in the following section.
2. Record the generated OneLink **short** URL.  
   The social app landing page does not work with long OneLink URLs.
3. Post the OneLink short URL on the social app.

Attribution is determined based on your attribution settings.

#### **To set up the Social apps landing page:**

1. In your custom link setup, go to the **Social-to-app** section.
2. In the **Social app landing page** section, click **Create social app landing page**.  
   A window to choose a landing page template opens.  
   [![](https://files.readme.io/82a65bf446c4e6ae8803eaf048cc95ebe9c312f574fb8eda2764c123f0a50ee6-30151216576657.jpg)](https://files.readme.io/82a65bf446c4e6ae8803eaf048cc95ebe9c312f574fb8eda2764c123f0a50ee6-30151216576657.jpg)
3. To choose a landing page template, hover over the selected template and click **Create**. **Tip**: Hover over the 🛈 icon of a template to see in which cases it should be used. Clustered Poster and ShowAndTell are recommended for Instagram.
4. Customize all the elements in the landing page creative. To do so, select elements by name or click on them on the preview image.    
   **Tip**: Save your texts in case you replace the creative template.
5. Replace all template images with your own images.  
   1. Enter image URLs including the extension, for example, `https://example.com/image.png`.
   2. Use one of the following file types: jpeg, jpg, png.   
      **Note**: webp format isn't supported.
   3. The recommendations for the images are:

      

| Template image type | Maximum image file size | Image ratio |
| --- | --- | --- |
| Collection | 300 KB | 16:9 (horizontal) |
| * Trapeze<br />* Carousel<br />* ShowAndTell | 300 KB | 1:1 |
| * Flyer<br />* Poster<br />* Blurry poster<br />* Clustered poster | 300 KB | 9:16 (vertical) |

   4. If one or more of the images isn't an exact URL, an error will display, and you will not be able to review the creative.  
      [![](https://files.readme.io/63223efc74994143111d5a5ef6b2d5fa7b84ac4f1033f8713d96cc293ba47588-30151216583697.png)](https://files.readme.io/63223efc74994143111d5a5ef6b2d5fa7b84ac4f1033f8713d96cc293ba47588-30151216583697.png)
6. To review the landing page creative, click **Review**.  
   If changes are needed, click **Back to editor**.  
   [![](https://files.readme.io/90b52321a6f7061a77624ec4486d6e2628c38c49ea0de734cf1c1fd0bc888cee-30151216593169.png)](https://files.readme.io/90b52321a6f7061a77624ec4486d6e2628c38c49ea0de734cf1c1fd0bc888cee-30151216593169.png)
7. To save your landing page, click **Done**.  
   **Important**: New/updated landing page creatives only apply after generating/updating the custom link.
8. [Optional] To edit your landing page, click **Edit social app landing page**.

### Deep linking and deferred deep linking

Deep linking means you retarget your existing app users and send them directly into a specific experience (for example, a specific page) within your app, without being directed to the app store or app home page first. These users are attributed using retargeting attribution.

Deferred deep linking means you give new users a similar deep linking experience as existing users. But their user flow is that first, new users are sent to the app store, and after they download and launch the app, they are sent to the specific experience or page.

> 📘 **Note**
>
> Setting up deep linking and deferred deep linking requires your Android and iOS developers.

**To set up deep linking and deferred deep linking to direct users to a specific experience in the app:**

1. Contact your iOS and Android developers to plan the **deep\_link\_value**to set on your links.
   * The **deep\_link\_value** is the value name for the specific in-app content that users will be directed to. The developers implement the desired behavior of the **deep\_link\_value** in the code.
   * The developers implement the desired behavior in the code. Share the guide so they understand the technical flow and see examples:
     * For [deep linking AND deferred deep linking](https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl) new or existing users, with or without your app.  
       **Considerations for UDL:**
       * Requires SDK V6.1 or later.
       * Click lookback window can be up to 15 minutes.
     * **Note**: Customers already using OneLink for deep linking may be using the legacy methods for [Android](https://dev.appsflyer.com/hc/docs/dl_android_gcd_legacy) and [iOS](https://dev.appsflyer.com/hc/docs/dl_ios_gcd_legacy), instead of UDL.

       CALLSTART::Note::

       #### Tips

       The **deep\_link\_value** can be based on a product SKU, social media post ID, URL path, or any other value.

       It is important to work with your developers to come up with the best long-term system for the **deep\_link\_value** and any other parameters or values. This will minimize additional app updates. Speak to your developer about the use of dynamic values, to generate many different deep links that go to different content within the app, **without needing to change the app code every time.**

       For example, the **deep\_link\_value** of a fruit type was chosen and the developers made the values dynamic. This means you can enter any fruit without the need for further work by your dev team.

       `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month``&deep_link_value=apples``...`

       `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month``&deep_link_value=bananas``...`

       `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month``&deep_link_value=peaches``...`

       CALLEND::
2. After receiving confirmation from the developers that the app behaves according to the selected parameters and values, in the **Deep linking and redirection** section of the link setup page, enter the **Deep link value** according to what you decided with the developers.
3. [Optional] If your deep linking requires more than one in-app experience (for example, you want to direct users to a product, and separately offer them a discount), you can add an **Additional deep link value** (that uses the parameter deep\_link\_sub1) to the deep linking data payload. You can add further deep link parameters  (deep\_link\_sub2-10) in the **Additional parameters** section.
   1. Contact your iOS and Android developers to plan the values.
   2. The developers implement the desired behavior in the code. Share the OneLink guides with your developers to understand the technical flow and see examples.

      Android iOSUnity

      [Developer instructions for Android](https://dev.appsflyer.com/hc/docs/dl_android_overview)

      [Developer instructions for iOS](https://dev.appsflyer.com/hc/docs/dl_ios_overview)
   3. In the **Additional parameters** section, add custom parameters **deep\_link\_sub2-10** and values as required, according to what you decided with the developers.

> 📘 **Note**
>
> Once parameters and dynamic values are implemented by the developers, the marketer can use OneLink API to automatically generate thousands of custom links. [Learn more](/docs/use-onelink-api-to-create-links-in-large-scale-campaigns)

### Redirection

**To send new users to a landing page, instead of to the app store**:

1. In the **Deep linking and redirection** section of the link setup page, under When app isn't installed, select to send users to a different URL.  
   The custom Android and iOS URLs redirect new users to the landing page you specify.   
   **Note!** If your OneLink template already has a set value for a custom URL, these custom link URLs override it.
2. You can also send new users to [custom store product pages](/docs/redirect-users-to-custom-app-store-product-pages).

### Additional parameters

You may want to add additional parameters to your link, such as Campaign, Ad set name, Ad name, Channel, your own custom parameters, or 1-5 [subscriber parameters](/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for). This enables a more granular analysis of your marketing efforts. Read more about [additional attribution parameters](/docs/about-link-structure-and-parameters).

You can also add additional deep linking parameters (deep\_link\_sub2-10).

**To add parameters**:

1. In the **Additional parameters** section of the link setup, click **Add parameter**.
2. Select the parameter to add or enter a custom parameter.

### Testing

You can test whether your link works to redirect:

* New users without your app installed
* Existing users with your app installed

#### New users without your app installed

**Prerequisites**: A [registered test device](/docs/registering-test-devices) without the app.

**To test your link**:

1. In AppsFlyer, from the side menu, select **Engage** > **OneLink Management**.
2. Hover over the **Actions** icon of the link you want to test and click **Get URL**.
3. Send the short or long URL to your phone. You can either:
   * Scan the QR code with your phone camera or QR scanner app.
   * Email or WhatsApp yourself the link, and open it on your phone.  
     **Note:** Do not paste into iOS notes, or directly into a mobile browser. Often, the mobile operating system intentionally will not open the app in this context.
4. Click the link on your mobile device.  
   Depending on your platform, it should take you to the app store or landing page.  
   **Note**: A real click on a mobile device is needed. Javascript or 301/302 redirects can't trigger Universal Links and Android App Links. Even basic redirections fail with these methods on some browsers.
5. Download and launch the app.
   * The app should open to its home screen.
   * If you implemented deferred deep linking, the app should open to the content you specified in the link parameters.
6. In the AppsFlyer **Overview dashboard** look for a new install.  
   Look for a new click and install under media source (e.g. test) and the campaign name you put in the URL.

Link not working as expected? Check out the [OneLink FAQ and troubleshooting guide.](/docs/onelink-troubleshooting-and-faq)

#### Existing users with your app installed

**Prerequisites**: An Android and/or iOS device with the app installed. Make sure it is the app source and version where the developer(s) made changes (and implemented Universal Links, App Links, and/or URI schemes).

**To test your link:**

1. In AppsFlyer, from the side menu, select **Engage** > **OneLink Management**.
2. Click the selected **OneLink template**.
3. From the list, select the Custom link.
4. Hover over the **Actions** icon of the link you want to test and click **Get URL**.
5. Send the short or long URL to your phone. You can either:
   * Scan the QR code with your phone camera or QR scanner app.
   * Email or WhatsApp yourself the link, and open it on your phone.  
     **Note:** Do not paste into iOS notes, or directly into a mobile browser. Often, the mobile operating system intentionally will not open the app in this context.
6. Click the link on your mobile device.
   * The app should open to its home screen.
   * If you implemented deep linking, the app should open to the content you specified in the link parameters.
7. Go to the AppsFlyer **Overview** dashboard (**View type: Retargeting**).  
   Look for a new click/re-engagement (app open) under your link's media source (e.g. test) and the campaign name you put in the URL.

Link not working as expected? Check out the [OneLink FAQ and troubleshooting guide.](/docs/onelink-troubleshooting-and-faq)

## Additional procedures

### Create a custom impression URL

Custom impression links enable you to:

* Measure the [impressions to clicks conversion rates](/docs/about-conversion-rates#marketing-funnel-stages-and-conversion-rates::74b1530a) of the ads you display.
* Receive attribution for impressions.

**Prerequisites:** A working OneLink long URL. Short URLs are not supported.

**Who is involved:**

Marketer and web developer

**To create impression URLs for measuring impressions only:**

1. In AppsFlyer, from the side menu, select **Engage** > **OneLink Management**.
2. Hover over the Options menu**,** of the link you want to test and click **Get URL**.
3. Copy the OneLink long URL for editing.  
   Example: `https://subdomain.onelink.me/j7rN?pid=email&c=Spring`
4. Replace the subdomain (or the entire Branded Domain, if you're using one) with 'impressions'.    
   Example: If you are using a branded OneLink that looks like `https://app.alltrails.com/Waim?` change it to an impressions link `https://impressions.onelink.me/Waim?`.
5. Copy the impression URL and send it to your developer.
6. Instruct your web developer to implement the impression URL in the website logic.

Now you have an impression URL, that can be used to count impressions on your website pages **but can't attribute new installs**. For view-through attribution, follow the next steps.

**To use impression URLs for attribution:**

1. Prepare the impression URL as described in the earlier steps.
2. Make sure [view-through attribution is turned on](/docs/measure-view-through-engagements).
3. [Optional] If you wish to change the default 1-day view-through [lookback window](/docs/set-up-lookback-windows) value, add the `af_viewthrough_lookback` parameter with the new value. For example, `af_viewthrough_lookback=1d`.
4. Copy the impression URL and send it to your developer.
5. Instruct your web developer to implement the impression URL in the website logic.

Full impression URL example:

```
https://impressions.onelink.me/j7rN?pid=email&c=Spring&af_viewthrough_lookback=1d
```

### Deep linking post-event

You may want to deep link users into specific activities or pages only after an event, for example:

* Logging in
* Viewing a splash screen
* Consenting to terms and conditions
* And more

**To deep link users after an event**:

Ask your developers to follow their instructions for deep linking users post-event for [Android](https://dev.appsflyer.com/hc/docs/dl_android_dl_post_event) and [iOS](https://dev.appsflyer.com/hc/docs/dl_ios_dl_post_event).

### Deferred deep linking with iOS Private Relay

With the launch of iOS 15, Apple provides iCloud+ users with a feature called [Private Relay](https://www.macworld.com/article/348965/icloud-plus-private-relay-safari-vpn-ip-address-encryption-privacy.html), which gives them the option to encrypt their web-browsing traffic and hide their exact location, IP address, and the contents of their browsing traffic. If users opt-in to Private Relay, this could interfere with attribution and deferred deep linking. Meaning, once a new user without the app goes to the App Store, and installs and launches the app, Private Relay could prevent them from being sent to a specific page in the app.

To make sure that deferred deep linking (DDL) continues to work as expected, you need to implement one of the following AppsFlyer solutions:

* **[Recommended] App Clip-based solution**: Create an App Clip that gives you user attribution data, and directs users to a customized App Clip experience similar to the one you want DDL to achieve. The app clip can also include a flow to direct users from your App Clip to your full app.
* **Clipboard-based solution**: Create a web landing page that copies the deferred deep linking data from the URL and correctly redirects the user to the app. **Note**: This solution does not help with attribution.

### App Clip-based solution

This solution combines OneLink short URLs with the App Clips technology available on iOS, and allows you to send users to specific flows in your product without the need to install the full app. The OneLink short URL gives you user attribution data, and directs users to a customized App Clip experience similar to the one you want DDL to achieve. The app clip can also include a flow to direct users from your App Clip to your full app. **Note**: If users reinstall the full app from the App Clip-based solution, it may be reported in AppsFlyer as an organic install. 

#### **Flow**

The flow of the App Clip-based DDL solution is as follows:

1. The advertiser creates an App Clip and adds it to a OneLink template for users with Private Relay turned on.
2. The user taps the OneLink URL.
3. AppsFlyer web handler checks whether the:
   * Device is using iOS 15+
   * Browser is Safari
   * User has Private Relay turned on.
4. Once AppsFlyer confirms the above, and the user is prompted to either click **Play App Clip** or **View in Safari**.
   * If the user clicks **Play App Clip**, an App Clip card displays to the user.
   * If the user clicks View in Safari, a landing page opens, prompting them to open the App Clip.
5. The user opens the App Clip.
6. The App Clip opens and provides the user with the experience decided by the app marketer and developer.
7. If the App Clip includes a flow to direct users to the full app, the users are sent to the App Store to download the full app. Upon app launch, they get the user experience defined by the developer.

**Prerequisites:** AppsFlyer SDK V6.4.0+

**To set up the App Clip-based DDL solution**:

1. Tell the developer to follow the [App Clip-based solution dev hub instructions](https://dev.appsflyer.com/hc/docs/dl_ios_private_relay#app-clip-based-solution). and create an App Clip that provides the desired user experience. This can also include a flow to direct users from your App Clip to your full app.
2. Create or edit a [OneLink template](/docs/create-a-onelink-template) with [Universal Links](https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links) and [deferred deep linking](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking).
3. In the OneLink template, turn on **Display App Clip if user has Private Relay**. Don't turn this on unless you have an App Clip.  
   **Note**: When making changes to a OneLink template with Universal Links, such as adding (or removing) App Clip capability, it may take several hours for the AASA file to update. Therefore, the links you create based on the template may not have the updated functionality right away.
4. Create a custom link based on the OneLink template.
5. In App Store Connect, go to the **App Clip Experience** section, scroll down to **App URLs**, and enter either your OneLink template URL (domain + template ID. For example: `yourbrand.onelink.me/GrbZ`), or a specific OneLink custom link short URL.  
   **Note**: If you enter a OneLink custom link, the App Clip-based solution will only work for users tapping that specific link; other links created based off the OneLink template will not work.

### Clipboard-based solution

#### **Flow**

The flow of the clipboard-based DDL solution is as follows:

1. The advertiser creates a deferred deep link that contains the parameter `af_cp_lp=true`.
2. The user taps the deferred deep link.
3. AppsFlyer checks whether the:
   * Device is using iOS 15+
   * Browser is Safari
   * User has Private Relay turned on.
   * Link contains the parameter `af_cp_lp=true`.
4. Once AppsFlyer confirms the above, the web landing page loads, containing the app icon, image, and a CTA to get the app from the App Store. The user also sees a message that explains the process: that the URL is copied to make sure the best user experience that will send them to the specific page in the app.  
   ![ios_15_ip_masking__1_.png](https://files.readme.io/c130314c98ebd42f50feaafd752c0cea954f42c5bfd99a6dbd94daf9e48c2ff4-30151216595345.png)
5. The user taps **Get the app**.
6. The user is sent to the App Store to install the app. Then, at first launch, they are sent to the specific app page.

#### **Requirements**

The copy/paste landing page DDL solution requires:

* The user to be browsing the web on Safari.
* The deferred deep link to include the `af_cp_lp=true` parameter.
* AppsFlyer iOS SDK V6+.
* Your iOS app developer to implement code that pastes the deferred deep link data in the URL from the clipboard. This is not part of the AppsFlyer SDK.
* The end-user to keep the checkbox ticked (default). If it is unchecked, the URL is not copied and deferred deep linking doesn't work.

#### **Setup**

**To set up the clipboard-based DDL solution**:

1. Tell your iOS developer to:
   1. Follow the [dev hub instructions](https://dev.appsflyer.com/hc/docs/dl_ios_private_relay#clipboard-based-solution) and integrate the required code in the AppsFlyer SDK.
   2. Implement code that pastes the deferred deep link data in the URL from the clipboard. This is not part of the AppsFlyer SDK.
2. Add the `af_cp_lp=true` parameter to your links.   
   You can do so by adding a custom parameter in the AppsFlyer OneLink custom link UI or simply append the parameter to any of your links.

## Additional information

### Examples

**Basic example**

Mark is the marketer of a successful grocery delivery service called "Feed Me." Mark targets his user-base phone numbers to download Feed Me's new mobile iOS and Android apps. An SMS campaign is planned. However, Mark doesn't know which users have Android or iOS devices. He also doesn't know whether or not they have the app installed.

To solve this, Mark sends users an SMS containing a short URL powered by OneLink. When users receive the SMS and click the link:

* If they don't have the app yet, it automatically directs them to the appropriate app store or landing page, where it's easy for them to install the app.
* If they already have the app installed, the app opens for them.

The new installs and re-engagements are attributed to the SMS campaign, enabling Mark to check the success of the SMS campaign in AppsFlyer. 

**Deep linking example**

Mark the marketer's SMS (from the previous example) had mild success in getting users to download and open the app. However, not many users who clicked the link and opened the app converted to place an order.

Mark decides to increase conversion by offering a free bag of peaches, apples, or avocados with every purchase. For this, Mark creates a smooth, deep-linking experience for existing users. He sends his user base a detailed email stressing the benefits of these 3 healthy fruits. 

For each fruit mentioned in the email, Mark includes a link with a deep link value powered by OneLink, configured (with the help of mobile developers) to:

To solve this, Mark sends users an SMS containing a short URL powered by OneLink. When users receive the SMS and click the link:

* If they already have the app installed, they are taken straight to the relevant fruit page.
* If they don't have the app yet, they are directed to the appropriate app store or landing page, based on their device. And then, once they download and open the app, they are taken straight to the fruit page.

### Traits and limitations

| Trait | Remarks |
| --- | --- |
| OneLink characters | * Total URL length must not exceed 2000 characters<br />* Link name and media source: must not exceed 150 characters<br />* Short URL ID must not exceed 50 characters<br />* See additional redirection parameter [traits and limitations](/docs/about-link-structure-and-parameters#special-characters). |
| Maximum links | The maximum number of OneLink links you can create in AppsFlyer is 120,000 per account. |
| Posting OneLink URLs in web pages | Using `target="_blank"`in the HTML href tag does not result in redirection to Google Play or App Store. If the OneLink URL is placed inside an html **a** tag with the **target="\_blank"** attribute, it opens a blank page in Chrome on Android and iOS. This affects OneLink functionality. Make sure that the **a** tag doesn't include the target attribute. |
| Agencies | Agencies can't use OneLink templates or links. They're for custom/owned media sources only. |
| Ad networks | Ad networks can't use OneLink templates or links. They're for custom/owned media sources only. |
| Social media preview image | * If the image type is not supported by the social media platform, it doesn't display.<br />* For WhatsApp, the image can't exceed 300 KB. |
| Desktop | When you set the OneLink URL or template to redirect desktop users to a different URL, the web URL is added to the link in the `af_web_dp` parameter. When the link contains `af_web_dp`, AppsFlyer does not register a click when it comes from a desktop. |
| af\_enc\_data | Not supported in impression URLs. |
| Android social apps WebView | Due to recent changes in various Android social apps, some deep linking and store redirection flows in the internal browser view (WebView) were broken.<br /><br />**Android App links**<br /><br />Android App links are currently not supported when clicked from within the Facebook in-app browser. Using a URI scheme on links in this flow works as before.<br /><br />**Store redirection**<br /><br />To accommodate the changes and re-enable store redirection, we had to introduce additional user interaction for the following Android social apps:<br /><br />* Facebook versions above v420<br />* Instagram<br />* Facebook Messenger<br />* Snapchat<br /><br />The new user flow requires users of the above apps to click on an additional landing page button to trigger the redirection to the Google Play Store and other third-party stores.<br /><br />This button is added automatically, requiring no action.<br /><br />**Notes:**<br /><br />* Facebook versions 420 and below work as before, with no additional user interaction.<br />* Facebook App Links (using URI scheme) in Facebook posts work as before with no additional user interaction.<br />* Facebook App Links in Instagram chat work as before with no additional user interaction.<br />* In a deep linking flow, when the app is not installed, there is a known limitation: an error pop-up message. This message does not affect the flow; the user is still redirected to the store as expected. |
| OneLink link previews | **Description**  <br />OneLink link previews sometimes fail to display correctly on Facebook and LinkedIn. The issue arises when the destination website does not recognize the `AppsFlyerBot-Previewer/1.0` user-agent string in the preview request as coming from a robot (or crawler). In such cases, the website fails to respond with the appropriate OG-tagged preview content.<br /><br />**Solution**  <br />You can configure your landing page to treat pages with the `AppsFlyerBot-Previewer/1.0` user-agent header string as coming from a robot by [updating your website robot.txt file](https://moz.com/learn/seo/robotstxt).<br /><br />The preview robot also checks every link's redirect parameters against your redirect allowlist. When a parameter points to a domain that isn't in the list, the robot ignores the URL, so the preview stays blank or generic. Make sure every landing-page domain you expect to preview is added to your redirect allowlist. |
| Android Naver Blog app | Deep linking is not supported on Android Naver Blog app. Users will be taken to Google Play or to the web redirection as defined on the link. |
| Chrome browser on iOS | Due to a change in Chrome iOS, whenever a user clicks a OneLink link which contains a URI scheme link (af\_dp parameter) in Chrome on iOS, a pop-up is displayed, prompting users to confirm opening the app or redirecting to the App Store. |
| Telegram WebView | Probabilistic modeling attribution doesn't work for user engagement in Telegram WebView (Telegram browser). The reason is because WebView doesn't include device models and OS versions in its engagement requests. |
| Xiaomi Browser | Probabilistic modeling attribution doesn't work for user engagement in Xiaomi Browser. |