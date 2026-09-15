---
title: "[Beta] User-based cross-platform re-engagement attribution"
excerpt: "Learn how cross-platform re-engagement attribution credits the media sources that bring existing users back to your product across platforms."
---
**At a glance:** Learn how cross-platform re-engagement attribution credits the media sources that bring existing users back to your product across platforms.

## About cross-platform re-engagement attribution

Cross-platform re-engagement attribution extends the [User-based cross-platform attribution](/docs/beta-user-based-cross-platform-attribution) model to include measuring user cohorts based on the latest ad engagement, in addition to the original acquisition source.

In cross-platform user-acquisition attribution, all activity for a given user is credited to the original media source that drove their first conversion, using a persistent Customer User ID (CUID) to link events across devices and platforms. This gives you a unified view of each user's journey, regardless of where it takes place.

Cross-platform re-engagement attribution adds a layer to this model. Instead of always crediting the original acquisition source, it also gives credit to the media sources that bring existing users back to your product after a period of inactivity. This lets you measure the true impact of your campaigns across your entire product line, not just on the device or platform where they ran.

Here is how the two models relate to each other:



|  | Cross-platform user-acquisition attribution | Cross-platform re-engagement attribution |
| --- | --- | --- |
| **What it measures** | First conversion and all subsequent activity | Re-activation of existing users after inactivity |
| **Credit goes to** | Original acquisition source | Re-engaging media source (for example, Meta) |
| **Scope** | All events within the inactivity restoration window | Events within the re-engagement window only |
| **Setup** | Configured at the product line level | Opt-in, configured on top of the user acquisition setup at the product line level |



Re-engagement attribution works alongside user acquisition, so you can see both the source that first acquired a user and the source that brought them back in the same reporting view.

## How does re-engagement attribution work

For an in-app event to be attributed to a re-engaging media source, all of the following conditions must be met:

* **Cross-platform re-engagement is enabled:** Re-engagement attribution must be enabled for the product line in your AppsFlyer settings.
* **CUID is present:** The event must include a valid customer user ID (CUID) that matches a CUID previously seen in the same product line. This is how AppsFlyer identifies the user as returning, rather than new.
* **The retargeting inactivity window has elapsed:** The CUID must not have been seen for at least the duration of the inactivity window for re-engagement since its last appearance. If the event occurs within this window, it is not counted as a re-engagement, and it is attributed to the original acquisition source.
* **The event occurs within the re-engagement window:** Once a qualifying re-engagement attribution is detected, the re-engagement window opens. Only in-app events that occur within this window are attributed to the re-engaging media source. Events that occur after the window closes are attributed to the original acquisition source.

## Cross-platform re-engagement user journey example

The following examples show the same user journey twice: first without cross-platform re-engagement, then with re-engagement opted in. Comparing the two illustrates exactly how re-engagement changes attribution.

### User journey without re-engagement

Consider a user journey across three platforms. A Google ad drives users to install a mobile app, where they sign up using a customer user ID. Later, a Meta ad drives the same user to visit the web platform, where they sign in with the same customer user ID. After signing in, the user makes two purchases on mobile: $100 and $50.

[![](https://support.appsflyer.com/hc/article_attachments/45444733164945)](https://support.appsflyer.com/hc/article_attachments/45444733164945)

Because re-engagement is not enabled in this scenario, all activity is attributed to Google Ads, the original acquisition source. The $100 and $50 purchases, as well as both platform activations (mobile and web), are credited to Google. Meta receives no credit within cross-platform attribution, even though its ad drove the Web install.



| Media source | Total attributions | User acquisition | Re-engagements | Platform activations | Mobile | Web | LTV |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Google | 1 | 1 | 0 | 2 | 1 | 1 | $150 |
| Meta | 0 | 0 | 0 | 0 | 0 | 0 | $0 |



### User journey with re-engagement

The user journey is identical to the one above. The difference is that the product line has opted in to re-engagement.

[![](https://support.appsflyer.com/hc/article_attachments/45444733163409)](https://support.appsflyer.com/hc/article_attachments/45444733163409)

In this case, the retargeting inactivity window determines whether the Meta-driven Web sign-in qualifies as a re-engagement event. The window opens from the last time the customer's user ID was seen, which was at mobile sign-up. If enough time passes before the Web sign-in, meaning the sign-in occurs outside the inactivity window for re-engagement, Meta receives re-engagement credit.

Once Meta is credited with the re-engagement, the re-engagement window opens. Any in-app events that occur within this window are attributed to Meta. In this example, the $100 purchase falls within the re-engagement window and is attributed to Meta. The $50 purchase falls outside the re-engagement window and is attributed back to Google.



| Media source | Total attributions | User acquisition | Re-engagements | Platform activations | Mobile | Web | LTV |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Google | 1 | 1 | 0 | 1 | 1 | 0 | $50 |
| Meta | 1 | 0 | 1 | 1 | 0 | 1 | $100 |



## Set up cross-platform re-engagement attribution

To set up cross-platform re-engagement attribution, you need to apply a few settings in AppsFlyer specific to re-engagement on top of your product line setup. For more information, see [How to create a product line](/docs/product-line-group-apps-for-cross-platform-attribution#how-to-create-a-product-line).

## View cross-platform attribution results

> 📘 **Note**
>
> #### See also
>
> * [Data Locker end-user events cross-platform report](/docs/end-user-events-cross-platform-report-in-data-locker)
> * [The cross-platform dashboard](/docs/my-dashboards#crossplatform-dashboard)