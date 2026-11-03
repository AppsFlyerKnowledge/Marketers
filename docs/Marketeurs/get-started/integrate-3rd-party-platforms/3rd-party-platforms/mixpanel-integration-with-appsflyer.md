---
title: Mixpanel integration with AppsFlyer
metadata:
  keywords:
    - Attribution
    - Mixpanel
    - SDK
    - integrated partner
    - Advertisers
    - Ad Networks
    - facebook mixpabel
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T11:33:01Z'
  edited_at: '2026-06-16T11:45:26Z'
  id: 207447103
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207447103-Mixpanel-integration-with-AppsFlyer
---
> **At a glance:** Learn how to automatically share data from AppsFlyer to Mixpanel, a product analytics platform.

![](https://cdn.appsflyer.com/marketplace/static/logo/mixpanel.png)

The integration between AppsFlyer and Mixpanel enables you to import the Acquisition Campaign information from AppsFlyer to Mixpanel.

> 🚧 **Important!**
>
> <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions#restrictions-des-sources-média">Some media sources</Anchor> restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Mixpanel

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration tab is divided into different sections as described below.

### General settings

<Image alt="mixpanel-general-settings.png" src="https://files.readme.io/df1b95eb3926aa7e10db338f156a87b88aabda6b97a4d28db2953e9e48a114e6-360017400598.png" width="542px" />

* **EU Data Residency**: AppsFlyer send data to Mixpanel's US servers as a default. To send data to Mixpanel's EU servers instead, turn this toggle on.  
  **\*token**: Mixpanel connects with AppsFlyer via a unique Token. If you don't already have it, you must obtain it from Mixpanel to continue with the integration.

  **To get the Token from Mixpanel:**

  1. Login to your Mixpanel account at: https://mixpanel.com/login/
  2. In **Mixpanel**, go to the **Analysis** dashboard and click the gear icon.

     ![mixpanel-token-1.png](https://files.readme.io/f1fbc76fff621e12a7d91fed5ba49eb20f2b049de65c70b0ab32cadd997287d2-small-360014578477.png)
  3. Copy your token from the Access Keys section of your project and paste it in the **token** field in AppsFlyer Mixpanel integration tab.

     ![mixpanel-token-2.png](https://files.readme.io/e8e633ec87d963244652a53b9b21c495b0a850e234621a44d93b3034c640bff7-360014578757.png)
* **Send Advertiser ID**:
  * If you are using AppsFlyer customer\_user\_id parameter then it is sent to Mixpanel with every install (Leave **Send Advertiser ID** disabled).
  * If you are not using AppsFlyer customer\_user\_id - enable **Send Advertiser ID.** The device ID is sent to Mixpanel as the customer\_user\_id (unique\_id in Mixpanel).  
    Learn more about the AppsFlyer SDK integration guide for <Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">Android</Anchor> and <Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">iOS</Anchor>.
* **Events:** Turn on to send install data to the Mixpanel Events endpoint.
* **People:** Turn on this to send install data to the Mixpanel People endpoint.

  > 📘 **Note**
  >
  > For install postbacks to be sent to Mixpanel, at least one of the two endpoints, **Events** or **People**, must be turned on.

* **Advanced Data Sharing:** Enable this to send additional information to Mixpanel: c (campaign), network (pid), impression\_based (is-impression).

### Default postbacks

AppsFlyer can send automatic postbacks to Mixpanel following user installs, including installs and re-engagements. Re-engagements occur when a user that already has the app installed, opens the app after a click through a campaign. Learn more about <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#default-postbacks">default postbacks</Anchor>.

[![](https://files.readme.io/6cf4f0e1b73c634c5fbe8f79e654ff3a3cd318bdca51d5e6b17933c307eb769d-36693858465809.png)](https://files.readme.io/6cf4f0e1b73c634c5fbe8f79e654ff3a3cd318bdca51d5e6b17933c307eb769d-36693858465809.png)

### In-app events settings

![mixpanel-in-app-events-settings.png](https://files.readme.io/db5e4e6d5bbe084a94b90425d49345511c214ddc39380a2b8419659ad752cdb2-360014576637.png)

In this section, you map AppsFlyer events with Mixpanel via postbacks.

> 📘 **Note**
>
> Mixpanel captures in-app events using their own SDK. The only event that can be sent to Mixpanel that is not captured by them is af\_uninstall.

Learn more about <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">in-app event postbacks</Anchor>.

**To configure in-app events postbacks:**

1. Enter the Mixpanel token.
2. Enable In-app event postback.
3. **To send the Advertiser ID of the uninstall**, enable **Send Advertiser ID**.
4. **To send additional information for the uninstall**, enable **Advanced Data Sharing**.
5. Click **Add Event** to add an SDK Event to the list.
6. Select **af\_uninstall** from the dropdown menu.
7. Select the corresponding **Partner Event Identifier** from the dropdown menu.
8. Select the required option from the Send revenue dropdown menu:
   * **No values & no revenue:** sends only the event itself without the event value.
   * **Values & no revenue:** sends all the parameters excluding the revenue value.
   * **Values & revenue:** sends all the event parameters, including the revenue value (if exists in the event).
9. To complete the integration configuration, click **Save Integration**.

Once you have saved the integration, AppsFlyer sends the following data to Mixpanel for every organic and non-organic install:

* Mixpanel token parameter
* Customer\_user\_id or Device ID (IDFA / Google Advertising ID)
* Media Source
* Campaign name

**Note**: CUID isn't sent in uninstall postbacks.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution Links are not available for this partner.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data is not supported in the integration with this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Permissions are not available for this partner.

</Accordion>

## Integrating with Mixpanel when using a login mechanism

The following shows an example of the integration steps:

1. App has been launched (opened) by the user.
2. The Mixpanel SDK generates a random distinct ID (**distinct\_id**).
3. Get the Mixpanel distinct ID, and set it as the Customer user ID, using the Appsflyer SDK function **setCustomerUserId**.
4. Send <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#start">**Start**</Anchor>. This API enables AppsFlyer to detect installations, sessions, and updates.
5. After the app installation is attributed, an **install** event is sent to Mixpanel with the Customer user ID, which includes the Mixpanel distinct ID.
6. When the user registers or logs in, the Mixpanel identify() command is called with the user identifier (for example, email or customer ID). This will map the initial random distinct ID to the registered user ID.

   <Tabs>
   <Tab title="Android">

   Mixpanel Android - <Anchor target="_blank" href="https://developer.mixpanel.com/docs/android#section-combining-anonymous-and-identifiable-user-data">Combining anonymous and identifiable user data</Anchor>

   ```java
   MixpanelAPI mixpanel = MixpanelAPI.getInstance(context, MIXPANEL_TOKEN);
   mixpanel.identify("user@example.com");

   // Mixpanel v6.2.0 and below should use the following API:
   mixpanel.getPeople().identify(“user@example.com”);
   ```

   </Tab>

   <Tab title="Objective C">

   Mixpanel iOS Objective C - <Anchor target="_blank" href="https://developer.mixpanel.com/docs/ios#section-combining-anonymous-and-identifiable-user-data">Combining anonymous and identifiable user data</Anchor>

   ```objectivec
   [mixpanel identify:@“user@example.com”];
   ```

   </Tab>

   <Tab title="Swift">

   Mixpanel iOS Swift - [Combining anonymous and identifiable user data](https://developer.mixpanel.com/docs/swift#section-combining-anonymous-and-identifiable-user-data)

   ```swift
   mixpanel.identify(“user@example.com”);
   ```

   </Tab>

   <Tab title="Unity">

   Mixpanel Unity - [Combining anonymous and identifiable user data](https://developer.mixpanel.com/docs/unity#section-combining-anonymous-user-data-with-identifiable-user-data)

   ```csharp
   // set customer user id or device id
   Mixpanel.Identify(“user@example.com”);
   ```

   </Tab>
   </Tabs>

7. Mixpanel receives the customer\_user\_id from AppsFlyer with the alias of the User ID (for example, email address).

> 📘 **Note**
>
> If you are not using any registration process inside your application, implement steps 1-3 as described above.

## Viewing AppsFlyer data in Mixpanel

The screenshots below are a Funnel report to see the conversion from install through the value event, broken down by the Media Source. Additionally, the time to convert for each Media Source can be seen.

[![](https://files.readme.io/fdffbe0a2f29c8a8b02b600966583cdeb4917bb48f0502e9b00ef39daa2fa835-9646475113361.png)](https://files.readme.io/fdffbe0a2f29c8a8b02b600966583cdeb4917bb48f0502e9b00ef39daa2fa835-9646475113361.png)

[![](https://files.readme.io/043a96a00e46a3daaef2b9fa4d58d252391ca2bb14307437f28c447d96ae97d6-9646475229841.png)](https://files.readme.io/043a96a00e46a3daaef2b9fa4d58d252391ca2bb14307437f28c447d96ae97d6-9646475229841.png)

<div data-zendesk-anchors="h_01H9FKEWTEN4F8FM5C9A9ES6HN=important h_01H9FKEWTEGMEVH3SK739DD719=setting-up-mixpanel h_01H9FKEWTE90WR75PMNN93JAXE=integration-tab h_01H9FKEWTEMT7VGTTFWFMJHYA8=general-settings h_01H9FKEWTEV3RWKMWZN0EXFFNP=note h_01H9FKEWTER31RXAH216TRXQPM=default-postbacks inapp-events-settings=in-app-events-settings h_01H9FKEWTERRVKPQFF1B8QQERE=in-app-events-settings h_01H9FKEWTEEMMQ0KKRZXRJRE25=note-1 h_01H9FKEWTEEQ0GHF87V20TX9W0=attribution-link-tab h_01H9FKEWTEJ61197SN3R6JXYCP=cost-tab h_01H9FKEWTEA7GN2HHK3QD62A3A=ad-revenue-tab h_01H9FKEWTET4QD1RE0HJZM64D4=permissions-tab h_01H9FKEWTE9DEANTXKPD286GD2=integrating-with-mixpanel-when-using-a-login-mechanism h_01H9FKEWTFZ107Y999WEMB3409=note-2 h_01H9FKEWTF9PFNVHTZGDKBX75Y=viewing-appsflyer-data-in-mixpanel" />
