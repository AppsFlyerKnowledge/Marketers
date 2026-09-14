---
title: "Instagram mobile app install ads configuration"
excerpt: "Learn how to add Instagram mobile app installs to your Meta ads account and configure landing pages for deep linking."
---
**At a glance:** Add Instagram mobile app installs to your Meta ads account.

![instagram_logo.jpg](https://files.readme.io/55ab80e2b1ba9d164d978116f3aaaacb9fe7e4571f71e0130a40e1ded16679db-360000492725.jpg)

## Setting up Instagram

The setup for Instagram is listed under Meta ads in the AppsFlyer Active Integrations section.

Meta documentation can be found [here](https://developers.facebook.com/docs/marketing-api/guides/instagramads/) and [here](https://www.facebook.com/business/help/1634705703469129).

1. Link your Instagram account to Meta Business Manager

![link-inst-with_fb-account.png](https://files.readme.io/c6c7fe17274f0b9af008c4452b4b7ea2233cc5bca8773307fef6afaeb7d06015-11212956311441.png)

2. Once added in Business Manager, Assign an Ad Account to your Instagram Account

![assign-inst-ad-to-fb.png](https://files.readme.io/658dc57d0056a2217a9f0f5c785b87e24c297158b75c5815eddb64930d00ea17-11213052873745.png)

3. Configure Meta ads under the Active Integrations Configuration by adding your Facebook App ID.
4. If you do not have a Facebook App ID, create one [here](https://developers.facebook.com/apps).

[![facebook_app_id.png](https://files.readme.io/2e497e1e00c22d0006aebd540b24c47ba4f2907ee9de061dc04ab50bbbe2cc67-14069602144273.png)](https://support.appsflyer.com/hc/article_attachments/360002280605)

## Instagram landing page for deep linking

Currently, [Instagram supports deep linking into iOS apps using Universal Links](https://support.appsflyer.com/hc/articles/208874366#social-app-landing-page) for Static ads (non-catalog). iOS Universal Links and Android App Links are only supported in campaigns where **App** is selected as a destination.

If you need to use custom links with deep linking on Instagram in campaigns where **App** cannot be selected, for example, if you set up an awareness campaign in Meta - as this campaign does not allow **App** to be selected as a destination, iOS Universal Links and Android App Links are not supported. You can [configure Instagram landing](https://support.appsflyer.com/hc/articles/208874366#social-app-landing-page). This allows you to use OneLink with Universal Links in Instagram to deep link users for better user experience.

For Dynamic ads, iOS Universal Links, Android App Links, and URI schemes can be used as outlined [here](https://support.appsflyer.com/hc/articles/4410472805649-Facebook-Ads-FAQ#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads).