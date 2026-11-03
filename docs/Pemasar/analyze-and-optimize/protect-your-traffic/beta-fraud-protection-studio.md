---
title: '[Beta] Fraud protection studio'
metadata:
  keywords:
    - Marketers
    - Beta feature
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2024-12-08T06:38:30Z'
  edited_at: '2026-08-19T10:37:41Z'
  id: 30754984040977
  locale: en-us
  section: Protect your traffic
  section_id: 6551015912465
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/30754984040977--Beta-Fraud-protection-studio
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **At a glance:** Fraud protection studio (FPS) provides greater control over how fraud detection is applied than usual methods. With FPS, you can choose whether fraud detection data is blocked and reported as fraud or tagged, empowering tailored fraud management.

## About fraud protection studio

Fraud protection studio introduces a tagged detection status.

This status enables advertisers to detect fraud without automatically implementing actions, which provides you:

* Evaluation: Evaluate the impact of detection updates before they apply.
* Control: Tailor fraud detection to your business model and needs.
* Transparency: Tagged data provides insights on additional fraud protection layers.

> 🚧 **Important!**
>
> Only the Admin, Marketing lead, Team manager, and Security <Anchor target="_blank" href="/marketers/id/docs/user-management#manage-roles">permissions roles</Anchor> are able to access the Fraud protection Studio.

## How the fraud protection studio works

<div id="key-concepts" />

<Accordion title="Key concepts">

#### FPS modes

FPS has two modes, **implemented** and **tagged**. Advertisers can switch between these modes based on their goals, ensuring that detection is aligned with their specific needs.

**Current detection mechanism:** Installs are either considered:

* **Valid** attribution
* **Detected**
  * **Blocked** In real-time
  * **Reported** as post-attribution fraud

[<Image alt="Image description" src="https://files.readme.io/86996ca9cf4fb83b5cfa24473a302d4e978732495348e3e7432ca2117d1f03c9-30885578633745.png" width="75%" />](https://files.readme.io/86996ca9cf4fb83b5cfa24473a302d4e978732495348e3e7432ca2117d1f03c9-30885578633745.png)   
**Mechanism with FPS:** Installs are either considered:

* **Valid** attribution
* **Detected** and
  * **Tagged** but remain **valid** for attribution
  * **Implemented**
    * **Blocked** In real-time
    * **Reported** as post-attribution fraud

[<Image alt="Image description" src="https://files.readme.io/465289666e54257f02cfe0a3b34a765e7109426c1f6438f455613cc53351e4f4-31990048826513.png" width="75%" />](https://files.readme.io/465289666e54257f02cfe0a3b34a765e7109426c1f6438f455613cc53351e4f4-31990048826513.png)

> 📘 **Note**
>
> In tagged mode, all fraud detections that are tagged but remain valid are considered valid according to the client configuration, and as such, we won’t credit back to the consumption plan

#### Where is tagged detection reflected?

Tagged detections aren't reflected in fraud reports. Tagged detections are available in regular attribution reports and the Protect360 dashboard as follows:

**Reports**:

* Real-time tagged installs
* Post-attribution tagged installs
* Real-time tagged in-app events
* Post-attribution tagged in-app events

**Protect360 dashboard**:

[<Image alt="example10.png" src="https://files.readme.io/cf4c836ee78519bd0723bcc1fafb202110fa014be1582853646261d89eb37104-48783289649937.png" width="50%" />](https://files.readme.io/cf4c836ee78519bd0723bcc1fafb202110fa014be1582853646261d89eb37104-48783289649937.png)

* Total tagged count in the upper page components (1)
* Overtime trend of “Detection Status” (2)
* Identified fraud by “Tag type”, “Tag reason,” “Tag Sub Reason” (3)

</Accordion>

## How to use fraud protection studio

<div id="general" />

<Accordion title="General">

FPS is a configuration page allowing you to specify when you want detections to be [implemented or tagged](/docs/beta-fraud-protection-studio#fps-modes). The platform helps define tagging requirements by providing:

* Detection status data.
* Option to switch between implemented and tagged modes.

To get started:

1. Log in to AppsFlyer.
2. From the left-hand menu, go to **Settings > Protect360 > Fraud Protection Studio**.
3. Use the app dropdown at the top of the page to select the app you want to configure.
4. Select the card from the left menu. the current options are:
   * [Click flood](/docs/beta-fraud-protection-studio#click-flood-detection)
   * [New releases](/docs/beta-fraud-protection-studio#new-releases)

</Accordion>

<div id="click-flood-detection" />

<Accordion title="Click flood detection">

FPS makes managing click flood detection simple and customizable. Allowing tagging of click flood detections on the app level (all partners) and showing tagged click flood detection data in dedicated reports.

On the click flood card page you can [see and adjust the detection status](/docs/beta-fraud-protection-studio#how-to-access-click-flood) between implemented and tagged, and view the [current detection status](/docs/beta-fraud-protection-studio#analyze-click-flood-by-media-source) data.

Download the Click flood report data sample

> 🚧 **Important!**
>
> * When tagged detection is selected they are reported in raw data reports, meaning, not in fraud reports.
> * Tagging the click flood is on the app level and will prevent blocking or post-attribution implementation. Therefore, by tagging it, you are exposed to abuse on your non-organic and organic installs.

#### How to access Click Flood

1. Log in to AppsFlyer.
2. From the left-hand menu, go to **Settings > Protect360 > Fraud Protection Studio**.
3. Use the app dropdown at the top of the page to select the app you want to configure.
4. From the left menu, select the **Click Flood** card

### Click flood page

The click flood page is broken into two sections:

[Detection Status](/docs/beta-fraud-protection-studio#detection-status)

[Current detection status](/docs/beta-fraud-protection-studio#current-detection-status)

#### Detection Status

* [Detection status](/docs/beta-fraud-protection-studio#how-to-access-click-flood) - Allows you to choose the [detection](/docs/beta-fraud-protection-studio#fps-modes) mode. you can choose between **implemented** and **tagged**
* [Current detection status](/docs/beta-fraud-protection-studio#current-detection-status) - Shows how enabling Click Flood would have affected your installs and relative events based on the last 7 days prior to last week. This section is further broken up into:
  * Current detection widget
  * Click Flood detection breakdown widget
  * Click Flood by media source widget

#### **How to adjust the detection status**

The detection status allows you to choose the [detection](/docs/beta-fraud-protection-studio#fps-modes) mode. you can choose between **implemented** and **tagged.**

1. In the Click Flood window, choose the [detection mode](/docs/beta-fraud-protection-studio#fps-modes).
2. Click the **Save** button at the bottom of the page.

   [<Image alt="Expandable Image" src="https://files.readme.io/c472a15b2775d97c097196d2ce97d59f997219beb44c662a7c7a0e1c17682fb6-31776609579025.png" width="1906px" />](https://files.readme.io/c472a15b2775d97c097196d2ce97d59f997219beb44c662a7c7a0e1c17682fb6-31776609579025.png)

#### **Current detection status**

The current detection status section shows an estimation based on the last 7 days prior to last week.

The current detection status section shows the following:

* Current detection widget
* Click Flood detection breakdown widget
* Click Flood by media source widget

**Current detection widget**

* **Total installs** - The total amount of app installs
* **Click flood detection** - The total detected click floods
* **Total detection** (without click flood) - The total amount of fraud detections not including click flood
* **Total detection** ( with click flood) - The total amount of fraud including click flood. Calculated by: (Click flood detection + Total detection (without click flood) )

**Click flood detection breakdown widget**

This shows the breakdown of the Click Flood detection by organic and non-organic installs.

**Click Flood by media source widget**

Shows the detected click Flood installs broken down by media source.

Note: for a more detailed report, click the **Export** button to download the detection metrics as a CSV file for offline analysis.

</Accordion>

<div id="new-releases" />

<Accordion title="New releases">

With New Releases, you can evaluate the impact of new fraud detection updates before implementation. By default, each new fraud detection package starts in tagged mode, giving you time and control to evaluate its impact.

Download the New Release report data sample

> 📘 **Note**
>
> A detection package is one or multiple detection updates that are grouped and released together.

#### How this works

* Fraud detection updates are grouped into packages.
* Fraud detection packages start in [tagged mode](/docs/beta-fraud-protection-studio#fps-modes).
* New packages can be set to tagged mode for up to 14 days.
* The current active package can be evaluated and implemented.
* You will be notified of new package releases through the notification bell.

#### How to access New Releases

1. Log in to AppsFlyer.
2. From the left-hand menu, go to **Settings > Protect360 > Fraud Protection Studio**.
3. Use the app dropdown at the top of the page to select the app you want to configure.
4. From the left menu, select the **New Release** card.

### New releases page

The New Releases page is broken up into two sections.

* [Future Releases](/docs/beta-fraud-protection-studio#how-to-access-new-releases) - Allows you to evaluate the impact of new fraud detection packages by marking detections as tagged for up to 14 days before they come into effect.
* [New Releases](/docs/beta-fraud-protection-studio#how-to-evaluate-and-implement-current-active-packages) - Allows you to evaluate the current active package by monitoring its detection performance and implementing it now.

#### How to set the tagged mode time period for future packages

Future Releases allow you to set the number of days you want future detection packages to be marked as [tagged](/docs/beta-fraud-protection-studio#fps-modes) before they go into effect. To set this:

1. In the New Release window, from the dropdown box, select the number of days you want to mark new packages as tagged before they get implemented (default: 14 days, adjustable up to 14 days)
2. Click the **Save**.

<Image alt="futrele.png" src="https://files.readme.io/eb832fdacd720f273a5ac26bc8e08fe1d215a99e477ff3bcfe3b91d46c41234a-31500353666321.png" width="2142px" />

> 📘 **Note**
>
> * This only affects future packages. Detection packages that are currently in effect will not get delayed or changed.
> * Selecting 0 days from the dropdown box is equivalent to selecting [Implement now](/docs/beta-fraud-protection-studio#to-implement-the-current-package-if-in-tagged-status), and overrides the the [Future Release](/docs/beta-fraud-protection-studio#how-to-access-new-releases) settings for this package.

#### How to evaluate and implement current active packages

The New Current Release section allows you to see:

* The last package released
* Released date
* Status - when this package will go into effect (if this package is in tagged mode).
* Metrics on how this detection package will affect your data
* Export detail reports
* Bypass the Future Releases settings and implement this detection package now

#### To implement the current package if in tagged status.

1. Open the **New Release Card** in the FPS tab.
2. Monitor detection performance using the table, and exportable reports.
3. When ready, click **Implement Now** to apply the changes.  
   [![](https://files.readme.io/4c11614b4f74ffa435e75cb7e79ef4f61ac750f5bc49331387b45a0ceb83e0da-31776606696081.png)](https://files.readme.io/4c11614b4f74ffa435e75cb7e79ef4f61ac750f5bc49331387b45a0ceb83e0da-31776606696081.png)

> 📘 **Note**
>
> This overrides the [Future Release](/docs/beta-fraud-protection-studio#how-to-access-new-releases) settings for this package.

</Accordion>

<div id="app-detection-evaluation" />

<Accordion title="App detection evaluation">

The App Detection Evaluation Card allows you to change a detection’s status based on your business objectives. Decisions made here are applied at the app level and affect all of the advertiser’s partners.

Tagging a detection on the App Detection Evaluation Card impacts all Protect360 logic. However, detections triggered by your defined validation rules are not affected. These detections remain in Implemented status unless you manually deactivate the corresponding validation rule.

On the App detection evaluation page you can [see and adjust the detection status](/docs/beta-fraud-protection-studio#how-to-access-click-flood) between implemented and tagged, and view the [current detection status](/docs/beta-fraud-protection-studio#analyze-click-flood-by-media-source) data.

> 🚧 **Important!**
>
> * When tagged detection is selected, they are reported in raw data reports, meaning not in fraud reports.
> * Tagging the app detection evaluation is on the app level and will prevent blocking or post-attribution implementation of Protect360 logics. Therefore, by tagging it, you are exposed to abuse on your non-organic and organic installs.
> * Any validation rule defined and activated will always remain in implemented mode. To pause the implementation of any validation rules, go to the validation rules page and deactivate it there.

#### **How to access App detection evaluation**

1. Log in to AppsFlyer.
2. From the left-hand menu, go to **Settings > Protect360 >** **Fraud Protection Studio**.
3. Use the app dropdown at the top of the page to select the app you want to configure.
4. From the left menu, select the **App Detection Evaluation** card.

#### **App detection evaluation page**

The app detection evaluation page is broken into two sections.

* [Detection status](/docs/beta-fraud-protection-studio#how-to-access-click-flood) - Allows you to choose the [detection](/docs/beta-fraud-protection-studio#fps-modes) mode. you can choose between implemented and tagged.
* [Current detection status](/docs/beta-fraud-protection-studio#current-detection-status) - Shows the current detection affecting your installs and relative events based on the last 7 days prior to last week. This section is further broken up into:
  * **Protect360 logics**   
    Implemented detection mode:
    * **Implementation rate** - the rate represents (*the amount of logic implemented by Protect360 logics*) divided by (*the app’s total attributions*).
  * **App-level**  
    Tagged detection mode:
    * **Tagged rate** - the rate represents (*the amount of logic tagged by the app detection evaluation tagging*) divided by (*the app’s total attributions*)
  * **Total installs**
  * **Total detections**
  * **Implemented detection** - Used to assist you before making the decision to change the [detection status](/docs/beta-fraud-protection-studio#how-to-access-click-flood) from implementation to tagging
    * Protect360 logics - This shows how much of the detection is by Protect360 logics. When changing to tagged - this is the expected amount of detection which will be converted to tagged detection
    * Validation rules—This shows how much of the detection is based on validation rules you have defined and activated. If you change the detection mode to tagging, validation rules-based detection will remain in the implemented mode.
  * **Tagged detections** - Used to assist before making the decision to change the [detection status](/docs/beta-fraud-protection-studio#how-to-access-click-flood) from tagging to implementation. You will have a reflection of all the tagging reasons to reflect the expected outcome before changing the detection status from tagged to implemented 
    * App level - This KPI allows you to understand how much of the tagged is due to tagging made by the app detection evaluation card. The number reflected in this KPI is the expected increase if you implement the detection status.
    * Other tagging - You can tag the detection in multiple capabilities (cards) in the fraud protection studio.

#### **How to adjust the detection status**

The detection status allows you to choose the [detection](/docs/beta-fraud-protection-studio#fps-modes) mode. You can choose between implemented and tagged (the default is implemented)

1. In the app detection evaluation page, choose the [detection mode](/docs/beta-fraud-protection-studio#fps-modes).
2. Click the Save button at the bottom of the page.

</Accordion>

<div id="reengagement-hijacking-detection" />

<Accordion title="Re-engagement hijacking detection">

The Re-engagement hijacking detection in Protect360 expands the standard fraud detection coverage specifically for re-engagement activities. This detection enhances your control over fraud management.

By default, this detection is released in [tagged mode](/docs/beta-fraud-protection-studio#fps-modes), allowing you to evaluate its effectiveness and potential impact before implementation.

#### How this works

* The re-engagement hijacking detection is set to tagged mode by default. You can evaluate its detection performance without impacting your live attribution data.
* When implemented, detections occur post-attribution, meaning fraudulent re-engagements are identified and removed from attribution records.
* When implemented, all in-app events following a detection removal will be re-attributed to the original User Acquisition (UA) provider or marked as organic if no valid UA provider exists.

#### How to access

1. Log in to **AppsFlyer**.
2. From the left-hand menu, go to **Settings > Protect360 > Fraud Protection Studio**.
3. Select the app you wish to configure using the app dropdown at the top.
4. From the left menu, choose the **Re-engagement Hijacking** card.

#### Re-engagement hijacking page

The Re-engagement hijacking page is broken into two sections.

* [Detection status](/docs/beta-fraud-protection-studio#how-to-access-click-flood) - Allows you to choose the [detection](/docs/beta-fraud-protection-studio#fps-modes) mode. You can choose between implemented and tagged
* [Current detection status](/docs/beta-fraud-protection-studio#current-detection-status) - Shows how enabling Re-engagement hijacking would have affected your installs and relative events based on the last 14 days (excluding the current day).  
  **Note:** Since Re-engagement Hijacking Detection operates post-attribution, data from the last 7 days may be partial and continue to update retroactively.  

  This section is further broken up into:
  * Re-engagement hijacking detection widget
    * Detections - the number of detections by the re-engagement hijacking logic alone
    * Detection rate - percentage of re-engagement hijacking detections out of the re-engagement detection
  * Total Re-engagements detection widget - the amount of overall re-engagement detection from all logics
  * Re-engagement attribution volume widget
    * Attributions - The amount of re-engagement attribution in the timeframe
    * Rate out of total attributions - the portion of re-engagement attributions out of all app’s attributions
  * Re-engagement detection by media source - The number of re-engagement hijacking detections for the top detected media sources

<Image alt="" src="https://files.readme.io/bab73f39f3792401dd8795a78c64d88c26d075cdb7d693a5871bba668495f8d1-35682380370321.png" width="624px" />

</Accordion>

<div id="inapp-based-detection" />

<Accordion title="In-app based detection">

In-app based detection deterministically marks installs as fraud in post-attribution by analyzing in-app behavioral anomalies. It identifies sophisticated fraud schemes such as bots that mimic real engagement but display unusual event flows and timing patterns after install.

#### How to access

1. Log in to AppsFlyer.
2. From the left-hand menu, go to **Settings > Protect360 > Fraud Protection Studio**.
3. Use the app dropdown at the top of the page to select the app you want to configure.
4. From the left menu, select the **In-app based detection** card.

#### The In-app based detection page

The in-app base detection page is broken into two sections.

* [Detection status](/docs/beta-fraud-protection-studio#how-to-access-click-flood) - Allows you to choose the [detection](/docs/beta-fraud-protection-studio#fps-modes) mode. You can choose between implemented and tagged.
* [Current detection status](/docs/beta-fraud-protection-studio#current-detection-status) - Shows how enabling In-app Based Detection would have affected your installs based on the last 14 days (excluding the current day).   

  Note: Since In-app based detection operates post-attribution, data from the last 7 days may be partial and continue to update retroactively.

This section is further broken up into:

* **New detections by in-app based logic**
  * Detections - the number of installs detected by the in-app logic
  * Added value rate - In-app based detection divided by your app’s total installs
* **Fake detected installs**
  * Detections - Total number of fake detections
  * Detection rate - Fake detections divided by your app’s total installs
* **Total installs**

* **In-app based detection by media source** - The number of installs by the top media sources.

<Image alt="" src="https://files.readme.io/63eedf0c4aa28471d4044a8896e349612fb9d8e9f06aed6b1efbaa825330d150-36947287654033.png" width="624px" />

</Accordion>

<div id="h_01K0ASM01ADVSECMOD01" />

<Accordion title="Advanced Security Module data">

Review Advanced Security Module detections of install candidate cyberattacks in real time, for Android apps. This helps make sure only verified traffic reaches your app.

#### How to access

1. Log in to AppsFlyer.
2. From the left-hand menu, go to **Settings > Protect360 > Fraud Protection Studio**.
3. Use the app dropdown at the top of the page to select the app you want to configure.
4. From the left menu, select the **Advanced Security Module** card.

#### The Advanced Security Module page

The Advanced Security Module page shows:

* **Top app versions** — the top 5 app versions by install volume, so you can spot where spoofed traffic is concentrated.

Detections are shown as one of the following:

* **Blocked** — traffic stopped in real time, before attribution.
* **Tagged** — traffic flagged as suspicious but still attributed, so you can review before enforcing. This is the default detection mode.
* **Untagged** — install candidates the module didn't flag.

> 📘 **Note**
>
> For full setup, requirements, and detailed reporting, see <Anchor target="_blank" href="/marketers/id/docs/beta-advanced-security-protect360-module">[Beta] Advanced Security Protect360 Module</Anchor>.

</Accordion>

## FAQs

<div id="can-i-tag-detection-for-specific-partnersmedia-sources" />

<Accordion title="Can I configure tagged detection for partners or media sources?">

This depends on the detection type. For example, partner tagging is unavailable for hijacking detection to prevent biased detection.

<div id="what-happens-when-the-tagging-period-ends" />

<Accordion title="What happens when the tagging period ends?">

At the end of the evaluation period, tagged detection automatically converts to implemented mode.

</Accordion>

<div id="where-can-i-see-tagged-installs" />

<Accordion title="Where can I see tagged installs?">

Tagged data is available in the following reports in **Raw data reports**:

* Tagged installs
  * Real-time
* Tagged installs
  * Post-attribution
* Tagged in-app events
  * Real-time
* Tagged in-app events
* Post-attribution

The following tagged report is also available in **Data Locker**:

* Tagged installs
  * Real-time
* Tagged in-app events
  * Real-time

</Accordion>

<div id="can-tagged-detection-be-adjusted-for-appspecific-settings" />

<Accordion title="Can tagged detection be adjusted for app-specific settings?">

Yes, click flood tagging is configurable at the app level.

</Accordion>

<div id="can-i-see-tagged-inapp-events" />

<Accordion title="Can I see tagged in-app events?">

Yes. In-app events that are connected to a tagged install by the same AppsFlyer ID will also be tagged.

</Accordion>

<div id="who-can-change-set-up-or-view-fps" />

<Accordion title="Who can change, set up, or view FPS?">

Only the admin can change the set up of FPS. FPS is visible according to the <Anchor target="_blank" href="/marketers/id/docs/manage-data-access-permissions">permissions page</Anchor>.

</Accordion>

<div id="are-tagged-installs-credited-back-to-the-consumption-plan" />

<Accordion title="Are tagged installs credited back to the consumption plan?">

No. tagged detection will not be credited back to the consumption plan.

</Accordion>

<div id="are-tagged-installs-considered-as-fraud" />

<Accordion title="Are tagged installs considered as fraud?">

Tagged installs are detected by Protect360. However, they are tagged per the customer configuration. Therefore, both in the Overview and in the Protect360 dashboards they will be reflected under the attributed metrics.

</Accordion>

<div id="can-i-see-how-many-installs-are-tagged-only-by-the-click-flood-tagging" />

<Accordion title="Can I see how many installs are tagged only by the click flood tagging?">

Yes. This data is available in the new dedicated reports on the export page and on the Protect360 Dashboard.

</Accordion>

</Accordion>

<div data-zendesk-anchors="why-flexible-protection=about-fraud-protection-studio 01JEQR86DC1CK03DKCZH760N4M=about-fraud-protection-studio h_01JK3BGVNMYFQYQGRPJBVN2A7Z=important how-flexible-protection-works=how-the-fraud-protection-studio-works 01JEQR86DEG7RTRNYFP02WHJGQ=how-the-fraud-protection-studio-works 01JETRN5S347ZXV8CGZJDHQH56=key-concepts h_01JEWZEBBA9VAPCKR87NJ5AK3C=fps-modes 01JEWZQ7PBD6W4J15W0HE2Q4MJ=note 01JEWZT9N34FZ9SE8H7EGCMPBZ=where-is-tagged-detection-reflected how-to-use-flexible-protection=how-to-use-fraud-protection-studio 01JEQR86ECSYTM7RN3YPYRSAGE=how-to-use-fraud-protection-studio 01JETF4NJX02APNK1TDV91JQAB=general 01JETF4NJZ7P5M5RTCEFFD0WEP=click-flood-detection 01JFSPDB630RE494JG1W618TKR=important-2 adjust-detection-status=how-to-access-click-flood 01JEQVJS6YTQD299X39Q8E3506=how-to-access-click-flood h_01JJKE1ZKE5WDRSPKS8JE9MRRG=click-flood-page h_01JZQ81MW4HMY9B782Y7PWVE8Y=detection-status h_01JJKE1ZKEJ4QM2HTT37FERA92=how-to-adjust-the-detection-status 01JEQVZCNSTXY4V8H2Y1QP224C=current-detection-status 01JETF4NK2KT4MY2G6WMWGMVKB=new-releases 01JFQPRZ5NGEAFBWB1FS0D6DCT=note-1 h_01JEXC0ABSTCEA939DGQ5SDJBJ=how-this-works how-to-set-the-tagged-mode-time-period-for-future-packages=how-to-access-new-releases h_01JEXC2HAR2S6BWK28N8W3HHSZ=how-to-access-new-releases h_01JJKE1ZKE0K1W2VE3KHQ639B1=new-releases-page h_01JJKE1ZKE13D7EC6BMN3JJNGW=how-to-set-the-tagged-mode-time-period-for-future-packages 01JF50BVZ75ZSXTJEKAV4HVSTZ=note-2 h_01JEXC3DESR10WVV34ED30B7BH=how-to-evaluate-and-implement-current-active-packages h_01JF505FK4NP88WYXP8PVQRYDS=to-implement-the-current-package-if-in-tagged-status 01JF50BVZ9QPT5W41P8KQAREKV=note-3 h_01JQXFMBGXWKXMFFAPHN5V66Q7=app-detection-evaluation h_01JQXPVD4MXPYQQZXNTM2H9BNA=important-2 h_01JQXG4GJ2DB8HM26K3E1WA3A1=how-to-access-app-detection-evaluation h_01JQXG6QDSTAPCJDMQVQMXS86W=app-detection-evaluation-page how-to-adjust-the-detection-status=how-to-adjust-the-detection-status-1 h_01JQXG6QEAM0Y67G504JV2SA5R=how-to-adjust-the-detection-status-1 h_01JWAVMSW1K6R4FJ8J9AYYNHQW=reengagement-hijacking-detection how-this-works::a0e9054=how-this-works-1 h_01JWAVPAVKM9RSXFMZN9CM36ER=how-this-works-1 h_01JWAVPAVK7ZT471AQAFKAS64K=how-to-access reengagement-hijacking-page=re-engagement-hijacking-page h_01JWAVPAVKKB4JSP41P967EESS=re-engagement-hijacking-page h_01JZMAX35E1KT04VTKAFB8FAF3=inapp-based-detection how-to-access::db81debe=how-to-access-1 h_01JZMAZET0JXYEDGKE0B797TQ7=how-to-access-1 the-inapp-based-detection-page=the-in-app-based-detection-page h_01JZMB0NET3Y8CFVZ1WP0WDPMJ=the-in-app-based-detection-page advanced-security-module=h_01K0ASM01ADVSECMOD01 h_01K0ASM02ADVSECMOD02=how-to-access-2 h_01K0ASM07ADVSECMOD07=the-advanced-security-module-page h_01K0ASM13ADVSECMOD13=note-4 01JEQR86EMZQFNSZ5NWZ08F5YQ=faqs 01JETRQMEJHZMHAKHHX5SZ028N=can-i-tag-detection-for-specific-partnersmedia-sources 01JETRQMEKJ27S5GGVR73H6WZB=what-happens-when-the-tagging-period-ends 01JETRQMEMKV8K7EQMS1BJB989=where-can-i-see-tagged-installs 01JETRQMEM6BMEXGYJM6WVE313=can-tagged-detection-be-adjusted-for-appspecific-settings 01JF79M50ZZ7HP0XCW1F4YJH7R=can-i-see-tagged-inapp-events 01JF79M50ZTMM1Y2YW8ARTYVTN=who-can-change-set-up-or-view-fps 01JF79M510HGEVC1WTWXAHSAQH=are-tagged-installs-credited-back-to-the-consumption-plan 01JF79M510B5WW067Q4T4FDVSC=are-tagged-installs-considered-as-fraud 01JF79M5105Z9AH95K6VVANANM=can-i-see-how-many-installs-are-tagged-only-by-the-click-flood-tagging" />
