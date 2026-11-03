---
title: Beta -  Advanced Security Protect360 Module
metadata:
  keywords:
    - Beta feature
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2025-09-17T15:23:22Z'
  edited_at: '2026-11-01T11:13:44Z'
  id: 39145848948625
  locale: en-us
  section: Protect your traffic
  section_id: 6551015912465
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/39145848948625-Beta-Advanced-Security-Protect360-Module
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **At a glance:** Strengthen fraud protection for your Android app with the Advanced Security Module. This real-time solution detects and blocks attribution spoofing and manipulated traffic before installs are attributed. Designed for high-traffic apps and Protect360 clients, especially those working with affiliates. The module is fully configurable by you, allowing initial setup and ongoing maintenance to adapt to evolving fraud patterns and protect data integrity.

> 🚧 **Important!**
>
> The Advanced Security Protect360 Module beta is available to all Protect360 customers. To join, contact your CSM.

## What is SDK spoofing?

SDK spoofing is an advanced fraud tactic where attackers send fake install and in-app event requests directly to AppsFlyer servers—without installing or running the app on a real device. The app SDK isn’t hacked or modified. Instead, fraudsters mimic the network requests a real app would send, making the activity look legitimate.

For advertisers, SDK spoofing can lead to installs and engagement that never occurred, inflated install volumes, discrepancies between AppsFlyer and app store numbers, and wasted ad spend.

## About the Advanced Security Module

The **Advanced Security Module** is an add-on to AppsFlyer’s Protect360 suite, designed to detect and stop advanced attribution spoofing techniques on Android. By evaluating install activity after the first app launch but before attribution occurs, the module identifies suspicious traffic and prevents fraudulent installs from impacting your performance metrics.

This solution is especially valuable for apps facing discrepancies between app store data and AppsFlyer attribution, or those managing affiliate traffic, two common indicators of install fraud.

**How it works**

The module is triggered after the first app launch (logged by the SDK) but before the install is attributed. To use the Advanced Security Module, you must be using the Android SDK v6.15.2 or later.

## Prerequisites

Before you begin, make sure you have the following:

* **Android SDK v6.15.2 or later** integrated in your app.
* **An API V2 token** — required for Maven repository authentication when your developer integrates the Security Module dependency. See <Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens#applications-of-the-api-v2-token">Managing AppsFlyer tokens</Anchor> for how to retrieve or generate one.
* **All certificate hashes (SHA-256)** for every certificate used to sign your app (debug and release). See <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-security-plugin#generating-a-sha256-fingerprint">Generating a SHA256 fingerprint</Anchor>.

> 🚧 **Important!**
>
> If your account has already reached the two-token limit for API V2 tokens, you do not need to request a new one, an existing API V2 token can be reused for this integration. Contact your CSM if you have questions about token allocation.
>
> For the full technical integration steps, see the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-security-plugin">Android security plugin developer guide</Anchor>.

## Set the Advanced Security Module

Set up the Advanced Security Module to validate that in-app traffic is coming from your signed app builds and to detect (and optionally block) spoofed traffic.

<Accordion title="Configure the Advanced Security Module">

#### **Step 1: Open and select an app**

1. In AppsFlyer, go to **Settings > Protect360 > Advanced security module**.
2. Click **Get Started** or **Add build**.
3. Select the app you want to implement the Advanced Security Module solution on.
4. Click **Next**

#### **Step 2: Add certificate**

1. Add the:
   1. Certificate name
   2. Certificate Value
2. Click **Next**

Note: Ask your developer for all the [certificate hashes](https://dev.appsflyer.com/hc/docs/android-security-plugin#generating-a-sha256-fingerprint) used to sign the app. The Security Module uses these certificates to validate that traffic is coming from your app, so all relevant hashes should be included.

#### **Step 3: Excluded app versions from detection**

* Add app versions that should be excluded from Advanced Security detection. Typically, these would be:
  * Versions released before the Advanced Security Module was integrated.
  * Test or legacy builds that don’t include the module.

#### **Step 4: Build activation**

1. Click **Activate build**.
2. Your build will go into **In progress** until the build is complete. This may take 10-15 minutes.
3. Once complete, copy the code by clicking the **Copy code** button on the build and send it to your developer for integration into the app SDK.

> 📘 **Note**
>
> After you build, the detection mode is set to **Tagged** by default. In this mode, AppsFlyer flags suspicious traffic but doesn't block it. After the secured version is live, switch to **Implemented** mode to block spoofed traffic. For more information about the Tagged and Implemented modes, see <Anchor target="_blank" href="/marketers/fr/docs/beta-fraud-protection-studio#fps-modes">FPS Modes</Anchor>.

</Accordion>

<Accordion title="Maintaining and updating the configuration">

Fraud techniques change over time, and malicious actors may attempt to reverse-engineer detection logic. Regular maintenance ensures continued effectiveness.

#### **When to update the configuration**

Update your settings if you notice:

* Suspicious installs or events passing through detection
* Changes in traffic patterns
* New app versions or certificate changes
* Reduced effectiveness of existing protections

#### **What you can update**

You can:

* Add or update app certificates
* Modify excluded app versions
* Rebuild and redeploy the Security Module
* Adjust detection mode based on rollout status

#### **Best practices**

* Review Advanced Security insights regularly
* Coordinate with developers before app releases
* Update certificates immediately after signing changes
* Reassess configuration periodically to stay ahead of emerging fraud methods

</Accordion>

## **Data visibility**

The advanced security module detection is reflected in two places:

* Protect360 dashboard
* Fraud Protection Studio

<Accordion title="Protect360 dashboard">

The advanced security module detection can be found under the **Attribution Spoofing** section.

Data is broken up into two KPIs and a graph.

**KPIs**

* **Tagged attribution spoofing**: Number of install candidates that were detected by the advanced security module in tagged mode.
* **Implemented attribution spoofing**: Number of install candidates that were detected by the advanced security module in implemented mode, and blocked.

**Graph**

* **Attribution spoofing trend**: Reflection of the advanced security module detection over time. This graph reflects the high-level status of the spoofing detection on the app/s level.

<Image alt="" src="https://files.readme.io/2f9e63d283850d3b1150dfcefff3c3cd47383cb58c4194dbbec3296da807fcb9-39145854862353.png" width="624px" />

</Accordion>

<Accordion title="Fraud Protection Studio (FPS)">

The Advanced Security Module can be found in the Fraud Protection Studio page.

#### How to access

To access the Advanced Security Module:

1. Log in to AppsFlyer.
2. From the left-hand menu, go to Settings > Protect360 > Fraud Protection Studio.
3. Use the app dropdown at the top of the page to select the app you want to configure.
4. Select the Advanced Security Module card from the left menu.

#### The Advanced Security Module page

<Image alt="" src="https://files.readme.io/a94b0c810f719846ae2882cac2ff1dbe4e32f815ee4e023e65e563199f4e3345-39145848945681.png" width="624px" />

The Advanced Security Module page is broken into three sections.

##### Detection status

* Shows the detection mode. The two options are implemented and tagged. By default, it is set to **Tagged**.

Note: To change the detection status, contact your CSM.

##### Top app versions by detection status

* The chart shows the top 5 app versions in terms of installs volume
  * Every app version is broken down by:
    * **Untagged** - Install candidates that were not detected by the advanced security module.
    * **Tagged** - Install candidates that are detected by the advanced security module in tagged mode.
    * **Blocked** - Install candidates that are detected by the advanced security module in implemented mode. Every install candidate that is blocked will not proceed.

##### Insights

Insights help you understand the breakdown of the chart. The three types of insights are:

* **All traffic is blocked** - App versions that are 100% blocked may indicate that they were not added to the exclusion list. Please check the app version exclusion list with your CSM and consider adding the relevant app versions.
* **All traffic is tagged** - App versions that are 100% tagged may not have been added to the exclusion list. Please check the app versions exclusion list with your CSM and consider adding the relevant app versions.
* **High rate of tagged detections** - One or more app versions are showing more than 20% advanced security module detections in tagged mode. It is highly recommended to contact your CSM to switch to implemented detection mode for the best results.

</Accordion>

<Accordion title="FAQ">

#### What is Advanced Security?

Advanced Security is an additional protection layer for the AppsFlyer Android SDK that helps prevent attribution spoofing, a type of fraud where fake installs or events are reported even though no real user installed or used the app.

#### What problem does Advanced Security solve?

Advanced Security helps prevent fake installs and in-app activity caused by spoofing that appear in AppsFlyer but do not exist in the app store or backend systems. This reduces inflated install numbers, data discrepancies, and wasted ad spend.

#### What is attribution spoofing?

Attribution spoofing is a fraud technique where attackers generate fake install or in-app event data and send it to AppsFlyer while pretending it came from your app. No real app install or user activity actually occurs.

#### How does Advanced Security prevent attribution spoofing?

Advanced Security verifies that install and in-app event data truly came from your app’s SDK by adding a unique verification signature to each request. AppsFlyer checks this signature to confirm the data is genuine and has not been spoofed or manipulated.

#### Does Advanced Security affect the app or user experience?

No. Advanced Security runs in the background and does not change how users install or use the app. Any additional processing happens behind the scenes and is not noticeable to users.

#### Who should use Advanced Security?

Advanced Security is most relevant for apps that work heavily with non-SRN or affiliate networks, see unexplained gaps between app store installs and AppsFlyer data, or suspect sophisticated fraud that is difficult to detect using standard methods.

#### Is Advanced Security available for all platforms?

No. Advanced Security is currently available for Android apps only and is offered to Protect360 premium customers. It's also compatible with all AppsFlyer plugins.

#### How do I know Advanced Security is working?

Detection results are visible in the Protect360 dashboard and Fraud Protection Studio, where you can track spoofed traffic that is tagged or blocked and review trends over time.

</Accordion>

<div data-zendesk-anchors="h_01K5EBZV8BY54H332WTWEMYVSA=important h_01KH8MPFJBSN67PSQXX25NG6ZZ=what-is-sdk-spoofing h_01K5C4BCNRE8JWQ9DA20DJ3A07=about-the-advanced-security-module h_01K9PRQNEWSECTION0001AB=prerequisites h_01K9PRQNEWSECTION0002AB=important-1 h_01KHK6M3CTY4YSCRTSMS707S5Z=set-the-advanced-security-module h_01KH8XDACWA2C46MEEGFMM6J8M=step-1-open-and-select-an-app h_01KH8XDACYBFZJWHZZCD0JSNGJ=step-2-add-certificate h_01KH8XDAD08E1JJVVSV9GY4RAB=step-3-excluded-app-versions-from-detection h_01KH8XDAD122D7PWP2367YVNP2=step-4-build-activation h_01KH8XJXN717M3GDJNPPMWDBHY=note h_01KH8XDAD3M4RARMK7DS7RA08X=when-to-update-the-configuration h_01KH8XDAD46P524Z2H8BBZRAR1=what-you-can-update h_01KH8XDAD5PVKNPW37PMG3NKHH=best-practices h_01K5C4BCNTBVDQX8DGTGEAN01T=data-visibility h_01K5C4BCNZBS424A4PMS7AR8XG=how-to-access h_01K5C4BCP14ARR3JMDPMRWZPTT=the-advanced-security-module-page h_01K5C4BVN5CQVP8HJG1MBV72AW=detection-status h_01K5C4BVN69SK4TBNWPFPWYXPN=top-app-versions-by-detection-status h_01K5C4BVN6XA4SNP4TK9SSRHS9=insights h_01KH9HERVW7QE2JXCGBBC206VW=what-is-advanced-security h_01KH9HERVX8V537KQBSMAR31T8=what-problem-does-advanced-security-solve h_01KH9HERVY5G1J5KQV9ZKTHGXX=what-is-attribution-spoofing h_01KH9HERVZAT11WNX99R2EQCPB=how-does-advanced-security-prevent-attribution-spoofing h_01KH9HERW0XFEGCKGJZA6C44HY=does-advanced-security-affect-the-app-or-user-experience h_01KH9HERW00N9M05DSF8998JE0=who-should-use-advanced-security h_01KH9HERW13WYZYBAGA9XXKW1B=is-advanced-security-available-for-all-platforms h_01KH9HERW2CQ76W33ERFTP0FS9=how-do-i-know-advanced-security-is-working" />
