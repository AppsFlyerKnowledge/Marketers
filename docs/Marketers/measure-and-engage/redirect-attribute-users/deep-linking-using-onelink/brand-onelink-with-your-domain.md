---
title: Brand OneLink with your domain
metadata:
  keywords:
    - Marketers
    - cname
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-08-26T09:00:09Z'
  edited_at: '2026-08-14T16:22:56Z'
  id: 360002329137
  locale: en-us
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360002329137-Brand-OneLink-with-your-domain
---
> **At a glance:** Advertisers using OneLink links can brand them with their own domain. This improves campaign performance and increases brand exposure.

<Image align="center" alt="Branded_1__3_.jpg" src="https://files.readme.io/20d0a59aa3e896960c9a0faaacad51a58e314073368452e07a7507e0770ca817-30192959736465.png" />

<div id="branded-domains" />

## Branded Domains

* Branded Domains are used to brand attribution links with your brand and domain. For example, as illustrated in the preceding figure:
  * OneLink: abcdef.onelink.me
  * Brand abcdef.com
  * Subdomain: For example, app
  * Implement Branded Domains and use your full domain, with the attribution link being click.abcdef.com
* Branded Domains improve campaign performance because they:
  * Drive trust: Capitalize on your branding, ensure consistent identity, remove friction from user journeys, and improve CTR rates.
  * Allow deep linking using your brand.
  * Are simple to implement and behave the same as OneLinks.
  * Promote brand awareness: Your brand marks your campaigns, instead of a generic link.
  * Enable emails to avoid being flagged as spam due to the link not matching the sender email.
  * Branded domains are included in paid AppsFlyer <Anchor target="_blank" href="/marketers/docs/account-management-plans-payments-and-billing">subscription plans</Anchor>.

<div id="principles-of-implementation" />

### Principles of implementation

Branded Domains are implemented by associating a full domain defined in your Domain Name System (DNS) with a OneLink subdomain (the AppsFlyer CNAME destination). This is done by using standard settings in your DNS and setting up a Branded Domain in AppsFlyer. In addition, you will need to make some minor changes in your app to support Branded Domains.

You will need the assistance of the DNS admin, usually a member of your IT team or your DNS hosting provider and the app developer.

Multiple full domains can be associated with a single OneLink subdomain. This means you can have multiple brands using the same OneLink subdomain.

<div id="setting-up-branded-domains" />

### Setting up Branded Domains

Complete the action list to set up a Branded Domain.

|  | Responsibility | Action | Remarks |
| --- | --- | --- | --- |
| 1 | Marketer assisted by the DNS admin | [Set up a Branded Link in AppsFlyer](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer) | The DNS admin, usually a member of your IT team or your DNS hosting provider, needs to define the full domain (aka host) and set a CNAME record as described in the procedure. |
| 2 | Developer | [Set up Branded Domains in the app](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app) | Make minor changes to the app code. |
| 3 | Marketer | [Using and testing Branded Domains](/docs/brand-onelink-with-your-domain#using-and-testing-branded-domains) |  |
| As needed | Marketer | [Editing and deleting Branded Domains](/docs/brand-onelink-with-your-domain#editing-and-deleting-branded-domains) |  |

<div id="procedures" />

### Procedures

<div id="set-up-a-branded-domain-in-appsflyer" />

<Accordion title="Set up a Branded Domain in AppsFlyer">

Setting up a Branded Domain consists of associating a full domain set in your DNS with a OneLink subdomain in AppsFlyer as depicted in the following figure.

**Branded Domain pointing to AppsFlyer servers**

<Image align="center" alt="Branded Domain pointing to AppsFlyer servers diagram" src="https://files.readme.io/43bcdbe50ec58af434f404f0216f90ad345b7b1e034cb7d7c80e3c3c4307c1d2-30192946333713.png" />

**Before you begin:**

* Choose a full domain name, for example, app.abcdef.com where  
  abcdef.com is your brand. The subdomain, for example, app, can also be customized.
* Request that the DNS admin create the full domain (aka host).
* Request that the DNS admin set a CNAME record such that the full  
  domain (Brand domain) points to the specified URL (aka AppsFlyer host).  
  This is depicted in the figure Branded Domain pointing to AppsFlyer servers (above).

**To map your full domain to a OneLink subdomain**:

1. In AppsFlyer, click on **Engage** > **Branded Domains**.
2. Click **+ New Branded Domain**.
3. In the **Brand Domain** field, enter your full domain as set in your DNS. For example, **click.abcdef.com Note:** Do not place a period after the domain.
4. Select the OneLink subdomain from the list that displays. If no list  
   displays, you need to create a OneLink template, which will provide a  
   default subdomain.
5. Click **Next.**
6. Set a CNAME record:
   * If your domain is properly pointed to the AppsFlyer CNAME  
     destination, "AppsFlyer CNAME was found" displays.
   * If a CNAME is not found, copy the AppsFlyer CNAME destination, send it to your DNS admin, and ask them to make sure your full domain is mapped to the CNAME destination. The DNS admin must map your full domain to an AppsFlyer CNAME destination. Otherwise, the branded domain is created but doesn't work.

     <div id="note" />

     > 📘 **Note**
     >
     > The CNAME record must be mapped within a time span of 7 days, starting from the branded domain creation date and ending on the date specified in the confirmation dialog.  
     > If the CNAME record is not mapped by the specified date, you must  
     > [renew the 7-day period](#renew-the-7-day-period-for-mapping-the-cname-record).

7. Click **Done**. You can now create new links based on the OneLink template with your branded domain.

   <div id="note-1" />

   > 📘 **Note**
   >
   > * If you already created links based on your OneLink template without the branded domain, they still work.
   > * It can take up to 24 hours for a new branded domain to start working.


<div id="renew-the-7-day-period-for-mapping-the-cname-record" />

#### Renew the 7-day period for mapping the CNAME record

The new branded domain does not work if the CNAME record of your full domain isn't mapped to AppsFlyer within 7 days of your branded domain creation.

<div id="note-2" />

> 📘 **Note**
>
> If the record was mapped after the 7-day period expired, you still need to renew the 7-day period for the new branded domain to work.

**To renew the 7-day period:**

1. In AppsFlyer, from the side menu, select **Engage** > **Branded Domains.**
2. Go to the branded domain that is not yet mapped to AppsFlyer, indicated by the warning icon (![alert.png](https://files.readme.io/7df53739ca5c629ec0bda789563f59717da9699986222705228f57e0d947c8de-30192946335761.png)).
3. Click the refresh icon (<Image alt="refresh.png" src="https://files.readme.io/052b47c423612c1b0549f37ed6394373d37f28331e09f4c709601a7e5473bf2b-30192959741585.png" width="18px" />) to renew the 7-day period.

<div id="note-3" />

> 📘 **Note**
>
> You can delete the branded domain by clicking the Delete icon (<Image alt="delete-subdomain.png" src="https://files.readme.io/0029cc63db331d998182d46a63f9da9856de9b2351abd5b2d87fb2b47ae853c2-30192959748241.png" width="16px" />) if you decide not to renew the 7-day period. Only branded domains that are not yet mapped to AppsFlyer can be deleted.

<div id="custom-ssl-certificate-optional" />

#### Custom SSL certificate (optional)

AppsFlyer-managed SSL is the default and recommended option for most customers and requires no additional action because AppsFlyer automatically handles certificate issuance and renewal. If you have specific security or compliance requirements, you can choose to use your own SSL certificate authority (custom SSL certificate) instead of AppsFlyer-managed SSL. If you choose this option, you are responsible for issuing, uploading, maintaining, and renewing the certificate. If the certificate expires and is not renewed on time, service may be disrupted.

**To use a custom SSL certificate:**

1. [Create the branded domain](/docs/brand-onelink-with-your-domain#setting-up-branded-domains).
2. In AppsFlyer, from **Engage** > **Branded domains**, hover on the relevant domain and select the "Custom SSL certificate" icon.

   <Image align="center" alt="SSL certificate icon Newest minimal.png" src="https://files.readme.io/8b22a41fd755a3f36e8eaf4a869b107661894d81504bbfb44e1fc728b9b06751-45231876708497.png" width="1044px" />
3. Fill out the certificate details form.

   <Image align="center" alt="fill in form to generate CSR file.png" src="https://files.readme.io/4327a4da0cbcc6243c9bbdbec21fe4f91d7fe701ccbffca99e629a5eadd248e8-45231876709649.png" width="722px" />
4. Click **Download CSR** to download a copy of the form you just filled out.
   <Image align="center" alt="Download CSR file.png" src="https://files.readme.io/9a560d19e38593fbc379efc6bdb1e636e1fa34f894dca4b46a23be30019127dd-45231892701585.png" width="254px" />
5. Provide the CSR file you just downloaded to the SSL certificate authority of your choice.
6. Once they give you your new SSL certificate, upload it back to AppsFlyer.

<Image align="center" alt="Upload new SSL certificate to AF.png" src="https://files.readme.io/b22525d9f653c3897f39f02a7beded3ad5c42d74a5487458f2ed720a20351e03-45231892701969.png" width="811px" />

<div id="note-4" />

> 📘 **Note**
>
> SSL certificates expire. You are responsible for renewing it and uploading the updated certificate to AppsFlyer before the current one expires.

</Accordion>

<div id="set-up-branded-domains-in-the-app" />

<Accordion title="Set up Branded Domains in the app">

* Use the following SDK versions:
  * Android V4.10.1 and later
  * iOS V4.10.1 and later
  * User invite referral (invite a friend) requires SDK version V5.2.0 and later for both iOS and Android

**Branded Domains SDK implementation considerations**

* When deep linking takes place using Branded Domains, the AppsFlyer SDK can't get conversion data for installs and deep linking.
* To overcome this, the developer uses the `setOneLinkCustomDomain` and `oneLinkCustomDomains` SDK API for Android and iOS respectively.
* This API queries the branded domain, gets the OneLink domain to which it is mapped, and completes the OneLink.

<Tabs>
<Tab title="Android">

Ensure that you update the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#adding-app-link-intent-filter-to-main-activity">intent-filter</Anchor> of the manifest to include your brand domain by setting the android:host.

Use this API before initializing the SDK in the <Anchor target="_blank" href="https://developer.android.com/reference/android/app/Application">Android global application class.</Anchor>

**Example**

```java
public class AFApplication extends Application {

    @Override
    public void onCreate() {
    super.onCreate();

      // Set branded link domain. Don't include https:// as part of the domain. 
      AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com");
      AppsFlyerLib.getInstance().init(AF_DEV_KEY, conversionListener, this);
      AppsFlyerLib.getInstance().start(this, AF_DEV_KEY);

    }
}
```

If you have several branded domains, pass them all to the API to ensure that you always get the conversion data and can deep link into the app.

**Example**

```java
AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com", 
                                                        "click.greatapp.com", 
                                                        "deals.greatapp.com");
```

</Tab>

<Tab title="iOS">

**To associate domains for iOS Universal Links:**

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#enabling-associated-domains">Set up</Anchor> the **OneLink domain/subdomain** as an associated domain in Xcode.
* Set up the **branded domain** as an <Anchor target="_blank" href="https://developer.apple.com/documentation/security/password_autofill/setting_up_an_app_s_associated_domains">associated domain</Anchor> in Xcode.
* Set up the branded link to be able to get conversion data. For instructions, click the relevant programming language below.

<Tabs>
<Tab title="Objective C">

Use the API in the AppDelegate.m, inside the didFinishLaunchingWithOptions method:

```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    /** APPSFLYER INIT **/
    [AppsFlyerLib shared].appsFlyerDevKey = @"SED_DEV_KEY";
    [AppsFlyerLib shared].appleAppID = @"123456789";
    [AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com"];
    //...
    //...
  }
```

If you have several branded domains, pass them all to the API to ensure that you always get the conversion data and can deep link into the app.

**Example**

```objectivec
[AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com", @"click.greatapp.com"];
```

</Tab>

<Tab title="Swift">

The API should be used in the AppDelegate.swift, inside the didFinishLaunchingWithOptions method:

```swift
   func application(_ application: UIApplication, didFinishLaunchingWithOptions 
        launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {
          AppsFlyerLib.shared().appsFlyerDevKey = "6CQi4Be6Zs9oNLsCusPbUL"
          AppsFlyerLib.shared().appleAppID = "340954504"
          AppsFlyerLib.shared().oneLinkCustomDomains = ["example.com"]
          //...
          //...
   }
```

If you have several branded domains, you can pass them to the API as an array of strings. This ensures that no matter what branded link is used, you always get the conversion data and can deep link into the app.

**Example**

```objectivec
AppsFlyerLib.shared().oneLinkCustomDomains = ["promotion.greatapp.com", "click.greatapp.com"]
```

</Tab>
</Tabs>

</Tab>
</Tabs>

</Accordion>

<div id="using-and-testing-branded-domains" />

<Accordion title="Using and testing Branded Domains">

**Prerequisites**:

Before using and testing, Branded Domains complete the steps in the [Branded Domains workflow](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app).

**To create and test branded domains:**

1. <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-onelink-link">Create a OneLink link</Anchor> using the OneLink template mapped to the branded domain.
2. Copy the custom attribution link to a text editor.
3. The custom attribution link is made up of a OneLink subdomain, OneLink ID, and custom Link ID. Replace the OneLink subdomain with the Branded Domain full domain. Example:

| Custom attribution link | Branded Domain |
| --- | --- |
| **abcdef.onelink.me**/A1bc/dc1234ef | **click.abcdef.com**/A1bc/dc1234ef |

4. Use the branded link to <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">test installs and deep linking</Anchor>.
5. If you use raw data reports as part of the testing, the Original URL field is populated by the branded links.

</Accordion>

<div id="editing-verifying-and-deleting-branded-domains" />

<Accordion title="Editing, verifying, and deleting Branded Domains">

<div id="edit-a-branded-domain-mapping" />

#### **Edit a branded domain mapping**

You can change the mapping of an existing full domain to a different OneLink subdomain. There is no need to set a CNAME.

1. In AppsFlyer, from the side menu, select **Engage** > **Branded Domains.**
2. Go to the branded domain you want to edit.
3. Click the Edit icon (<Image alt="edit-subdomain.png" src="https://files.readme.io/ffe3da7d1c065a806a44c607bcf1231e06bf7e7478ca50187e57cb5ab876ae72-30192959751185.png" width="17px" />).
4. Select the new OneLink subdomain.
5. Click **Next.** There is no need to set a CNAME.
6. Click **Done**.

<div id="important" />

> 🚧 **Important**
>
> **Warning**
>
> Modifying the Branded Domain of active campaigns may alter or disable link functionality.

<div id="verify-a-branded-domain-mapping" />

#### **Verify a branded domain mapping**

After changing the OneLink subdomain mapped to your branded domain verify that the branded domain is mapped properly:

1. In AppsFlyer, from the side menu, select **Engage** > **Branded Domains.**
2. Go to the branded domain you want to verify.
3. Click the Verify icon (<Image alt="verify-2.png" src="https://files.readme.io/4ac94a535e9101b3e727351f67df8917c0870d6ede8ec963de8c5528893b8e2b-30192946342929.png" width="17px" />).

<div id="note-5" />

> 📘 **Note**
>
> If the verification fails because the CNAME record isn't mapped yet, you have a time span of up to 7 days to do so ending on the date specified in the verification failure dialog. If the CNAME record is not mapped by the specified date you must renew the 7-day period.

<div id="domain-cname-record-no-longer-pointing-to-appsflyer" />

#### **Domain CNAME record no longer pointing to AppsFlyer**

Changing your CNAME record to no longer point to AppsFlyer will result in the branded domain deletion from AppsFlyer.

<div id="delete-a-branded-domain-mapping" />

#### **Delete a branded domain mapping**

To delete a branded domain contact your AppsFlyer CSM or hello@appsflyer.com.

</Accordion>

<div id="troubleshooting-traits-and-limitations" />

## Troubleshooting, traits, and limitations

<div id="troubleshooting" />

<Accordion title="Troubleshooting">

| Symptom | Cause/solution |
| --- | --- |
| Branded Domain cannot be mapped to a OneLink template | <ul><li>**Invalid domain name:** When mapping a Branded Domain to a OneLink template, AppsFlyer tries to verify that the branded link has a valid domain name. A valid domain name has the format click.abdef.com</li><li>**The Branded Domain is already mapped**: A full domain can only be mapped once.</li></ul> |
| Branded Domain is not deep linking into the app | <ul><li>[Verify that the Branded Domain is operational](#verify-a-branded-domain-mapping)</li><li>**Verify CNAME**: Ensure that a CNAME record points from your Branded Domain to AppsFlyer.</li><li>**Verify deep linking setting for OneLink template**: It's possible there is an issue with the OneLink deep linking settings. Make sure to set up deep linking with OneLink.</li><li>**OneLink mapping changed**: You can edit the Branded Domain and map it to a different OneLink. If the newly mapped OneLink has different deep linking settings or no deep linking settings, deep linking might not work.</li></ul> |
| No installs measured from Branded Domains | <ul><li>**Check OneLink template settings**: Make sure that the OneLink subdomain used to map to the branded domain is associated with the correct apps.</li><li>**OneLink subdomain changed:** If you map a branded domain to a OneLink template and the OneLink subdomain changes, it might affect attribution.</li><li>**Ensure implementation:** Of setOneLinkCustomDomain API in the app.</li></ul> |
| No re-engagements recorded from branded domains | Ensure that the following are active and configured:<ul><li><Anchor target="_blank" href="/marketers/docs/onelink-guide#setting-up-onelink">Configure deep linking using OneLink</Anchor>.</li><li>The app makes use of the dedicated [SDK API setOneLinkCustomDomain](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer).</li><li><Anchor target="_blank" href="/marketers/docs/retargeting-attribution-guide#retargeting-settings">Retargeting is enabled in the app settings</Anchor>.</li></ul> |
| During Branded Domain setup, **Domain doesn't exist** message displays | <ol><li>Contact your DNS admin and ask them to investigate.</li><li>Wait for the DNS admin to confirm that the domain is registered.</li><li>Click **Reverify**.</li></ol> |
| During Branded Domain setup, **AppsFlyer CNAME not found** message displays | <ol><li>Request that the DNS admin set a CNAME record such that the full domain (Brand domain) points to the specified URL (aka AppsFlyer host). This is depicted in the figure Branded Link pointing to AppsFlyer servers in this section.</li><li>Wait for the DNS admin to confirm that the CNAME is active.</li></ol> |
| **You have been blocked** message when loading a branded domain page | Branded domains do not include the template or any parameters. When using a branded domain, you must add the template or parameters to the end of the branded domain URL.<br /><br />For example, if 'click.abcdef.com' is your branded domain, using just '**click.abcdef.com'**, will lead to a **you have been blocked** message.<br /><br />You must add the parameters or templates to the end. For example, click.abcdef.com **/A1bc/dc1234ef** |
| **err\_cert\_authority\_invalid** error when loading a branded domain page | This error indicates that your branded domain lacks a valid HTTPS certificate because the Certificate Authority is not recognized. Since AppsFlyer certifies your Branded domains with Let's Encrypt the error is likely due to Let's Encrypt not being recognized as a valid Certificate Authority (CA) according to the CAA (Certification Authority Authorization) DNS records of your domain.<br /><br />**Solution**<br />Please perform the following:<ol><li>Determine if your domain recognize Let's Encrypt as CA using services such as <Anchor target="_blank" href="https://www.entrust.com/resources/certificate-solutions/tools/caa-lookup">this one</Anchor>.</li><li>Ask your system administrators to update your domain CAA records to include Let's Encrypt as an authorized CA.</li></ol> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Yes ✓ / No **x** | Remarks |
| --- | --- | --- |
| Account user access | ✓ |  |
| Ad network access | **x** |  |
| Agency access | **x** | Agencies cannot create Branded Domains (or OneLink links). |
| Agency transparency | **x** |  |
| App-specific currency | N/A |  |
| App-specific time zone | N/A |  |
| Branded domain availability | N/A | Branded domains are available with eligible paid plans only. If your subscription plan lapses or is canceled, access to branded domains is removed, and existing links that use your branded domains won't work. |
| Character limitation | N/A | When entering your branded domain, the last character cannot be a period ("."). |
| Data freshness | N/A |  |
| Historical data | ✓ |  |
| HTTP | **x** | The HTTP protocol is not supported by branded links. HTTPS must be used. |
| Non-organic data | ✓ |  |
| Organic data | ✓ |  |
| Rate limitation | ✓ | Branded Domain SSL/HTTP certificates are arranged by AppsFlyer using <Anchor target="_blank" href="https://letsencrypt.org/">Let's Encrypt</Anchor>, with a rate limit of 50 new certificates per week per domain. |
| Size limitations | N/A |  |
| SSL/HTTP certificate renewal | ✓ | Your branded Domain SSL/HTTP certificates managed by AppsFlyer are automatically renewed without any action required on your part. |

</Accordion>

<div data-zendesk-anchors="h_01HFM51V4PE53FQAED68V8Q834=branded-domains h_01HFM51V4PPJXMCSV5ZVDPT49M=principles-of-implementation h_01HFM51V4PH58ZA4ZXHP5J6K2W=setting-up-branded-domains h_01HFM51V4PWWX7TBCHFMPR3QVB=procedures h_01HQ5CWGQNRBXQ6QQDADV7XCQP=set-up-a-branded-domain-in-appsflyer renew-the-day=renew-the-7-day-period-for-mapping-the-cname-record h_01HQ5CWGQNQJJ1CXDKTGZ8N9ZE=renew-the-7-day-period-for-mapping-the-cname-record custom-ssl-certificate=custom-ssl-certificate-optional h_01KM0E8VHARA2JRAR2H37QM91Y=custom-ssl-certificate-optional h_01HFM51V4PP0NQHVHTKB86250R=set-up-branded-domains-in-the-app h_01HFM51V4PN0FPEDNAF0Q1QS8P=using-and-testing-branded-domains h_01HQ5CWGQPZ6MEFA6MDTHYHCSA=editing-verifying-and-deleting-branded-domains h_01HQ5FJZD6QMNFA45Z2C7CA3ST=edit-a-branded-domain-mapping h_01HQ5FK5XJNZ1EABJA66RMYBCN=verify-a-branded-domain-mapping h_01JSHFECXS00M6BXH8168ZWJE5=domain-cname-record-no-longer-pointing-to-appsflyer h_01JSHF5RMXXFJTXC246KKAQBSS=delete-a-branded-domain-mapping h_01HFM51V4PH4YM13DVXENRWF2E=troubleshooting-traits-and-limitations h_01HFM51V4PJNHZTD97X75WPN98=troubleshooting h_01HFM51V4QQ2TZQMJ2ATNDG91F=traits-and-limitations" />
