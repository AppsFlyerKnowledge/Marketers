---
title: "[Beta] Advanced Security Protect360 Module"
excerpt: "Strengthen fraud protection for your Android app with the Advanced Security Module, a real-time solution that detects and blocks attribution spoofing and manipulated traffic."
---
**At a glance:** Strengthen fraud protection for your Android app with the Advanced Security Module. This real-time solution detects and blocks attribution spoofing and manipulated traffic before installs are attributed. Designed for high-traffic apps and Protect360 clients, especially those working with affiliates. The module is fully configurable by you, allowing initial setup and ongoing maintenance to adapt to evolving fraud patterns and protect data integrity.

> 📘 **Important!**
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
* **An API V2 token** — required for Maven repository authentication when your developer integrates the Security Module dependency. See [Managing AppsFlyer tokens](/docs/managing-appsflyer-tokens#h_01HG64DMW7PYRXBMZN00EQN991) for how to retrieve or generate one.
* **All certificate hashes (SHA-256)** for every certificate used to sign your app (debug and release). See [Generating a SHA256 fingerprint](https://dev.appsflyer.com/hc/docs/android-security-plugin#generating-a-sha256-fingerprint).

> 📘 **Important!**
>
> If your account has already reached the two-token limit for API V2 tokens, you do not need to request a new one, an existing API V2 token can be reused for this integration. Contact your CSM if you have questions about token allocation.
>
> For the full technical integration steps, see the [Android security plugin developer guide](https://dev.appsflyer.com/hc/docs/android-security-plugin).

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
> After you build, the detection mode is set to **Tagged** by default. In this mode, AppsFlyer flags suspicious traffic but doesn't block it. After the secured version is live, switch to **Implemented** mode to block spoofed traffic. For more information about the Tagged and Implemented modes, see [FPS Modes](/docs/beta-fraud-protection-studio#fps-modes).

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

![](https://files.readme.io/2f9e63d283850d3b1150dfcefff3c3cd47383cb58c4194dbbec3296da807fcb9-39145854862353.png)

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

![](https://files.readme.io/a94b0c810f719846ae2882cac2ff1dbe4e32f815ee4e023e65e563199f4e3345-39145848945681.png)

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

* **All traffic is blocked** -App versions that are 100% blocked may indicate that they were not added to the exclusion list. Please check the app version exclusion list with your CSM and consider adding the relevant app versions.
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
