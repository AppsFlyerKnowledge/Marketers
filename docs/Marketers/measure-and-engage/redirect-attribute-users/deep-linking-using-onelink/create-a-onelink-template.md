---
title: Create a OneLink template
metadata:
  keywords:
    - template
    - Marketers
    - Link Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Link Management
  created_at: '2014-11-03T12:35:49Z'
  edited_at: '2026-08-31T12:47:56Z'
  id: 207032246
  locale: en-us
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207032246-Create-a-OneLink-template
---
> **At a glance:** Create a template to form the basis of the redirection logic for all OneLink links that you create for your various marketing campaigns. A template is required for creating links and end-user experiences.

<div id="onelink-templates" />

## OneLink templates

<Embed title="Create a OneLink template" typeOfEmbed="youtube" url="https://www.youtube.com/embed/d4AtCJ9122Q" providerUrl="https://www.youtube.com" />

A OneLink template:

* Is not a clickable link for your end-users; it is the foundation for generating many custom links. Usually, you only need one template per app (outside of testing) to generate as many links as you want for all your different advertising campaigns.
* Is where you record your decisions on how to redirect users based on their device platform and on whether or not they have your app installed.
* Represents the routing logic at the core of all the OneLink links you create for your various marketing campaigns. This includes the redirection settings for:
  * **New users without your app installed**: To the correct app store or web URL
  * **Existing users with your app already installed**: Opening the app via Android App Links, iOS Universal Links, or URI schemes. This involves some developer work to set up.
  * **Note**: Redirection settings for website or app store can be overridden on the link level.

<div id="create-a-onelink-template" />

## Create a OneLink template

| Who's involved | Prerequisites | Time required | Outcome |
| --- | --- | --- | --- |
| <ul><li>Only a marketer is required to set up redirection logic for new users who don't have your app installed (for example, to the correct app store or web page).</li><li>To add redirection logic for existing app users who already have your app installed (for example, to open the app), both a marketer and Android/iOS developers are required.</li></ul> | <ul><li>An AppsFlyer account with at least one app.</li><li>Marketer must either be an AppsFlyer admin user, or have permission to add/edit OneLink templates.</li></ul> | Approximately 1.5 hours, working together with your Android/iOS developers. | A template from which you can create links that send users to the correct app store, web page, or into the app based on their device. |

<div id="create-a-onelink-template-with-redirection-logic-for-new-app-users" />

<Accordion title="Create a OneLink template with redirection logic for new app users">

**To create a OneLink template:**

1. In AppsFlyer, from the side menu, select **Engage** > **OneLink management**.  
   The OneLink suite is an account-level feature, which lets you create OneLink templates and their custom links for all your apps.  
   [![](https://files.readme.io/c5aacf61d1d1dc75ac7f0b9b6f681bb00e6521f6436fad3d2f073a42d4b0153f-4406696125713.png)](https://files.readme.io/c5aacf61d1d1dc75ac7f0b9b6f681bb00e6521f6436fad3d2f073a42d4b0153f-4406696125713.png) **Note**: If you don't have any templates created, an onboarding wizard opens. Follow the directions in the wizard and disregard the rest of this procedure.
2. Click the menu icon > **Add OneLink template**.  
   The OneLink template setup page opens.  
   <Image align="center" alt="OneLink_template_page_en-us.png" src="https://files.readme.io/d773d60cd2febcf6a8389e9586e8ca23a1515fc853e4d42d0db98661cacb387a-360009665478.png" />
3. In the **OneLink template name** field, enter a name.

   <div id="note" />

   > 📘 **Note**
   >
   > * A good OneLink template name includes the **name of the app** (for example feed\_me) or the use case or experience represented by the OneLink (for example pre\_launch\_landing\_page).
   > * The name should not include the campaign or channel name or media source (since this isn't the actual end-user link, just the underlying template to create many links), or the name of the platform (Android, iOS, since multiple platforms are usually the reason for using a OneLink template in the first place).
   > * This template name is only used internally. It doesn't affect your marketing attribution data and is not seen by users.

4. In the **Subdomain** field, enter your <Anchor target="_blank" href="/marketers/docs/appsflyer-knowledge-base-glossary#subdomain">subdomain</Anchor> name.
   * Choose a subdomain that matches your brand. For example, if your website is www.abcd.com choose abcd as your subdomain.
   * Users will see this subdomain as part of the link URL. For example: `https://abcd.onelink.me/RPsv/37e5cd36`.
   * The subdomain can’t be changed once custom links are created based on this template.
   * Only use lower-case letters, digits, or hyphen (-).
   * OneLink also supports fully branded domains, that can help you improve campaign performance and increase brand exposure. <Anchor target="_blank" href="/marketers/docs/brand-onelink-with-your-domain">Learn more</Anchor>
5. Select your Android app, iOS app, or both.
6. (Optional) Turn on Secure Shortlinks if you want to stop your links from being hijacked with extra parameters. **To turn on secure shortlinks:**

   Under **Secure Shortlinks**, turn on **Don't attribute clicks with added parameters**.

   Here's what this means for you: once it's on, if anyone adds a parameter to a shortlink created from this template, that click won't be attributed. The user is redirected according to the template's redirection settings; only attribution is affected.  

   **Example:**

| Link | Result |
| --- | --- |
| `[subdomain].onelink.me/[template_id]/[shortlink_id]` | Attributed as usual. |
| `[subdomain].onelink.me/[template_id]/[shortlink_id]?param=value` | A parameter was added, so the click isn't attributed. |

   **Notes:**

   * This setting applies at the template level. There's no way to turn it on or off for individual links.
   * For templates created before this feature's release, the setting is off. Turn it on if you want it. For templates created after release, it's on by default; turn it off if you don't want it.
7. Set where to redirect users **When app isn't installed**.  
   * If you've selected an Android app and an iOS app, the template is by default configured to send new app users to the correct app store.
   * If you've selected only one app, Android or iOS, the template is configured to send ALL users (iOS and Android, new and existing) to the single defined destination.
   * If you select an Android app that isn't in Google Play, you must enter a URL to which Android users are redirected.
   * [Optional] **Redirect to third-party app stores** if the app is in other stores besides Google Play. Make sure the app in the other stores has the same package name as the Android app selected in your OneLink template.
   * [Optional] **Change to a different URL**: In some cases, you may prefer to take new users to a mobile web experience instead of directly to the app store (or your app may not be listed in the store). To implement, enter that URL in the URL field. **Note**: If you set both a third-party redirection and a different URL, the default redirection is to the third-party app store.
   * [Optional] Turn on **Display App Clip for users with Private Relay** (available on iOS 14+). <Anchor target="_blank" href="/marketers/docs/apple-app-clips-integration-guide">Learn more about App Clips</Anchor>.
8. Skip **When app is installed**. This is discussed in the [next procedure](/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users).
9. [Optional] Change destination for **When link is clicked on desktop.**  
   * In some cases, your link might be clicked on a desktop computer, especially if it is sent via email or social media. If you expect a lot of desktop traffic to your link, you might want to send those users to a landing page or the main website homepage, or a page where they can request an SMS link on their phone, instead of the correct app store.
   * By default, desktop users are redirected to a web version of the App Store or the Google Play store - depending on the apps set on the template.
     * To change the default store option, select "Desktop web URL" and add the relevant web store URL. Make sure to add the store domain to the redirect allowlist.
10. [Optional] **Select apps from other platforms**  
    If you have a dedicated app version for the following:
    * **Windows phone**: Turn on the toggle and select app or **Change to a different URL**.
    * **iPad**: Turn on the toggle and select iPad app
    * **Amazon Kindle Fire**: Turn on the toggle and add the Amazon store ASIN or app page URL.
11. Click **Save OneLink template** (Update OneLink template for edited templates).   
    Your OneLink template is now created and can be used to create many different clickable links (see <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLink links and experiences</Anchor>).

</Accordion>

<div id="add-redirection-logic-for-existing-app-users" />

<Accordion title="Add redirection logic for existing app users">

Existing app users usually expect to be redirected directly into the app, not to an app store or web page. There are three technologies available to open the app directly after a click:

* **iOS Universal Links**: Works with iOS 9 and up, and provides a smooth, secure experience when opening your app.
* **Android App Links**: Works with Android 6 and up, and provides a smooth, secure experience when opening your app. **Note**: Samsung Internet Browser can't open apps using Android App Links.
* **URI scheme**:  
  * Fallback method:
    * Android: URI scheme is an effective fallback method for when Android App Links fail to open the app either because they don't work or aren't set up
    * iOS: Limited fallback capabilities for when Universal Links fail to open the app either because they don't work or aren't set up. <Anchor target="_blank" href="/marketers/docs/uri-scheme-fallback-for-ios">Learn more</Anchor>
  * Primary method for opening apps on Samsung devices.
  * Is an address, that when accessed, opens your app if it's installed. They are similar to website links, but open apps instead of websites.
  * Must be the same for iOS and Android.

For the best user experience, security, and device coverage, we recommend enabling as many technologies as possible. If you enable all link technologies, OneLink will automatically apply the best method for each user.

**To add redirection logic for existing app users to your OneLink template:**

1. In AppsFlyer, from the side menu, select **Engage** > **OneLink management**.
2. Select the OneLink template you want to edit.
3. Click the menu icon (⋮), then click **Edit OneLink template**.
4. Scroll down to **When app is installed**. [![](https://files.readme.io/c0e8e5364f0b184f33d72e33f28df131d5a8bb6c377dc74f0ec190bcc6e63e75-18363965490833.png)](https://files.readme.io/c0e8e5364f0b184f33d72e33f28df131d5a8bb6c377dc74f0ec190bcc6e63e75-18363965490833.png)
5. Follow the instructions for iOS, Android, and fallback setup:

   <Tabs>
   <Tab title="iOS Universal Links">

   Universal Links take the format of regular web links (e.g. https://yourbrand.onelink.me or https://www.yourbrand.com) and thus require setting a subdomain (covered in the [previous guide](/docs/create-a-onelink-template#create-a-onelink-template)). OneLink also supports fully <Anchor target="_blank" href="/marketers/docs/brand-onelink-with-your-domain">branded domains</Anchor>, but that isn't necessary to complete this guide.

   **To launch the app using Universal Links**:

   1. Contact your iOS developer:
      * Give them the subdomain for this OneLink template.
      * Tell them to follow <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">these instructions</Anchor>.
      * The developer returns to you with the Team ID (also called Apple App ID Prefix, for example, PF23MIWNTW).
      * If the app is not yet published, the developer must also give you the Bundle Identifier (for example, com.myapp.something).  
        <Image align="center" alt="" src="https://files.readme.io/c469a6c99515b0d76d075b0036ea118af16cd11b2ef134a63499acf0467895a0-18363965493521.png" />
   2. In the OneLink template page click **Change to launch the app using Universal Links**.
   3. In the new window, select **Launch the app using Universal Links**.
   4. In the **Team ID** field, enter the team ID provided by the developer.
   5. If the app is not published, also enter the **Bundle Identifier**.
   6. Click **Save changes**.

   </Tab>

   <Tab title="Android App Links">

   App Links take the format of regular web links (e.g. https://yourbrand.onelink.me or https://www.yourbrand.com) and thus require setting a subdomain (covered in the [previous guide](/docs/create-a-onelink-template#create-a-onelink-template)). OneLink also supports fully <Anchor target="_blank" href="/marketers/docs/brand-onelink-with-your-domain">branded domains</Anchor>, but that isn't necessary to complete this guide.

   **Before you begin**:

   Record the subdomain you chose for this OneLink template.

   **To launch the app using Android App Links**:

   1. Contact your Android developer:   
      Tell them to generate a SHA256 fingerprint by following <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#generating-a-sha256-fingerprint">these instructions</Anchor>.  
      The developer will come back to you with the SHA256 fingerprint. For example: `DC:65:43:67:F3:BD:02:52:AC:B4:50:F1:74:54: 23:49:4D:49:6C:E6:DF:56:BD:CB:53:06:11:5B:C9:4E:5D:0C`
   2. In the OneLink template page click **Change to launch the app using App Links**.
   3. In the new window, select **Launch the app using App Links**.
   4. In the **SHA256 fingerprint** field, enter the SHA256 fingerprint provided by the developer.  
      An auto-generated intent-filter code appears.
   5. Contact your Android developer:   
      Give them the auto-generated intent-filter code.  
      Tell them to follow <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#adding-app-link-intent-filter-to-main-activity">these instructions</Anchor> and confirm completion.

   </Tab>

   <Tab title="URI scheme">

   The URI scheme mainly serves as a fallback for both iOS and Android users, and so must be the same at both.

   **To set the Android and iOS URI fallback:**

   1. Contact your iOS AND Android developers and decide on a URI scheme. For example: `feedmeapp://`

      <div id="h_01H9Q4E7VR4CAK0PJY269GQ9XJ" />

      <div id="tip" />

      > 👍 **Tip**
      >
      > * Neither Apple or Google enforce unique naming for app schemes. **Choose a scheme name unique to your brand** to avoid conflicting schemes across different applications. A good scheme name could be your app bundle ID, for example, **com.company.app**
      > * To enable OneLink to serve both iOS and Android, it is important that **the same scheme is defined for both platforms**. Here are instructions for <Anchor target="_blank" href="https://help.contrast.co/hc/en-us/articles/200865293-URL-Scheme-Intro-for-App-Developers">iOS</Anchor> and <Anchor target="_blank" href="https://developer.android.com/training/app-links/deep-linking.html">Android</Anchor>.
      > * The URI scheme should not start with http or https.

   2. Tell the iOS developer to implement the URI scheme in their app by <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-uri-scheme">following these instructions</Anchor>.  
      **AND**  
      Tell the Android developer to implement the URI scheme in their app by <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#procedures-for-uri-scheme">following these instructions</Anchor>.
   3. When done, the developer confirms the value of the URI scheme implemented. Expect it to look like: `exampleapp://` or `exampleapp://home` or `exampleapp://main`, etc.
   4. In the OneLink template page click **Add URI scheme to launch the app**.
   5. Select **Launch the app using URI scheme**.
   6. Enter the URI scheme value.
   7. Click **Save changes**.
   8. Test the URI scheme (this can be done by you OR your developers):
      1. Go to <Anchor target="_blank" href="https://halgatewood.com/deeplink/">this free public testing tool</Anchor> on both an iOS and an Android device that has your app installed.
      2. Tap the link generated by the tool.  
         If the URI scheme is correct, the app opens.

   </Tab>
   </Tabs>

6. Click **Update OneLink template**.

<div id="note-1" />

> 📘 **Note**
>
> * When you save or update your OneLink template, AppsFlyer automatically generates the AASA and/or Digital Asset Links JSON file to verify your app domain, and hosts it for you. This is critical for your Universal Links and App Links to work properly.
> * It can take up to 1 hour for OneLink template updates to take effect.

</Accordion>

<div id="customize-qr-codes" />

<Accordion title="Customize QR codes">

<Image align="center" alt="OnelinkQRFinal__1_.gif" src="https://files.readme.io/6eb996db8c8bcdb8ac46380151fc54c8ef5b686999aaaef3d1a951d627eadc70-11902870808081.gif" />

You can customize the QR codes generated via OneLink by:

* Adding your logo to the QR code
* Changing the color of the QR code.

**Note**: QR code customization occurs at the template level; not at the individual link level. Therefore, customizations affect all QR codes based on the edited template.

**To customize your QR code**:

1. In AppsFlyer, from the side menu, select **Engage** > **OneLink Custom Links**.
2. Hover over the **Actions** icon of the template you want to edit and click **Customize QR code**.  
   The QR code editor opens.
3. Enter the URL where your logo is hosted. For example: https://yourbrand.com/logo.png.  
   Logo requirements:

   * PNG or JPG format
   * Square or circular with a transparent background
   * Minimum dimensions 400 x 400 px
   * For printing, use maximum image resolution
4. Set the QR code color.
5. Click **Save**.

</Accordion>

<div id="h_favicon" />

<Accordion title="Set a favicon for link previews">

A favicon is the small icon that appears next to your link title when a link is shared on social media or messaging apps. Customize how it looks by adding your own icon here. It applies to all links based on this template, and displays on supported platforms when a link is shared with a custom social media preview configured.

<div id="note-2" />

> 📘 **Note**
>
> This favicon only appears in link previews on platforms that support it, and only when **Custom preview (image and tags)** is configured at the link level. <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags">Learn more</Anchor>

**To set a favicon for your OneLink template:**

1. In AppsFlyer, from the side menu, select **Engage** > **OneLink management**.
2. Select the OneLink template you want to edit.
3. Click the menu icon (⋮), then click **Edit OneLink template**.
4. Scroll down to the **Favicon** section.
5. In the **Favicon Image URL** field, enter the URL of your favicon image.
   * Supported format: ICO
   * Recommended icon size: 32×32 or 64×64 pixels
   * The file size should not exceed 100 KB.
   * The URL must be publicly accessible
6. Check the **Preview** to confirm the icon displays correctly.
7. Click **Update OneLink template**.

</Accordion>

<div id="traits-and-limitations" />

## Traits and limitations

<div id="key-traits-and-limitations" />

<Accordion title="Key traits and limitations">

| Trait | Remarks |
| --- | --- |
| Agencies | Agencies cannot create OneLink templates and links. |
| Add/edit OneLink templates | Account users require <Anchor target="_blank" href="/marketers/docs/user-management">permission</Anchor> to add and edit OneLink templates. |
| OneLink templates | Up to 600 OneLink templates per account. |
| Desktop | When you set the OneLink URL or template to redirect desktop users to a different URL, the web URL is added to the link in the `af_web_dp` parameter. When the link contains `af_web_dp`, AppsFlyer does not register a click when it comes from a desktop. |
| Redirect to third-party app stores | Multiple app stores can be set on the OneLink template only if the app package name is the same for all app stores. To learn more about OneLink redirection to third-party Android app stores see <Anchor target="_blank" href="/marketers/docs/bulletin-onelink-redirection-to-third-party-android-app-stores?query=3rd%20party%20store">here</Anchor>.<br /><br />**Note**:<ul><li>Huawei and other third-party stores sometimes require different package names. When this is the case, the same OneLink template can't be used for multiple app stores.</li><li>Some Xiaomi devices have the GetApps store which uses the same URI scheme as Google Play. This means that if your intention is to redirect these device users to Google Play but your app doesn't exist in Xiaomi, the link will redirect to GetApps.</li><li>If the package name is the same, but the channel is different, the redirection works, but attribution doesn't.</li><li><Anchor target="_blank" href="/marketers/docs/set-up-multi-store-android-attribution">Learn more</Anchor> about third-party app store attribution and data.</li></ul> |
| Updating a template | <ul><li>Changes to the configuration of a OneLink template take up to 1 hour to apply.</li><li>Onelink templates can't be edited if an associated app was deleted from the account. In this case, you can:<ul><li>Create a new template.</li><li>Contact your AppsFlyer customer success manager or write to hello@appsflyer.com to restore the deleted app.</li></ul></li></ul> |
| URI scheme | See <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#chrome-browser-on-ios">here</Anchor>. |

</Accordion>

Got a question about OneLink templates? Check out our <Anchor target="_blank" href="/marketers/docs/onelink-troubleshooting-and-faq#onelink-template-faq">FAQ</Anchor>!

<div id="next-step" />

## Next step

Follow the instructions to <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">create OneLink links</Anchor> based on your template.

<div data-zendesk-anchors="h_01H9Q4E7VQ0GKZ9HFF88190TYN=onelink-templates procedures=create-a-onelink-template h_01H9Q4E7VQYGZ1MH5SS3ZYZF1K=create-a-onelink-template h_01H9Q4E7VQ648CQ1VJTB1TC571=create-a-onelink-template-with-redirection-logic-for-new-app-users h_01H9Q4E7VQ15AAR1VXNKWR1XGT=note h_01H9Q4E7VQ4NEWYAD6AMR9YKGY=add-redirection-logic-for-existing-app-users h_01H9Q4E7VR8164HR6MD0EAV2SN=note-1 h_01H9Q4E7VR0F4B7CTF08YTG715=customize-qr-codes set-a-favicon-for-link-previews=h_favicon h_01KT6GG94CRBYFDWZ28BA8HEYY=note-2 h_01KZX85DYWA1TJ0AS3QV27VPA4=traits-and-limitations h_01H9Q4E7VR2B50EQE31DDG8GNZ=key-traits-and-limitations h_01H9Q4E7VRJK31P9CSGJFCKQQF=next-step" />
