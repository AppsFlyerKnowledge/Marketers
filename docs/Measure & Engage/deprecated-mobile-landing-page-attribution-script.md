---
title: "[Deprecated] Mobile landing page attribution script"
excerpt: "This deprecated script generates URLs embedded behind buttons on mobile websites to redirect visitors to download apps while supporting install attribution and deep linking."
---
> 🚧 Deprecation Notice
>
> This script is deprecated as of December 17, 2020, and is replaced by the [OneLink Smart Script](https://support.appsflyer.com/hc/articles/360000677217). This version continues to work, but will not be updated or changed. The script generates URLs that are embedded behind a button on your mobile website and redirects visitors to download your app. The URLs also support install attribution and deep linking.

![5648_Sunset_and_deprecation-01.png](https://files.readme.io/d081bc5f4a2dd4010efe360436973ac39fac999136c265d007646ae2e7f61fec-5648_Sunset_and_deprecation-01.png)

**[Migrate to OneLink Smart Script](https://support.appsflyer.com/hc/articles/360000677217)**

Landing pages are a very common technique among digital marketers. They allow the marketers to capture their leads' details for remarketing, even if these users don’t convert at first.

However, for mobile user acquisition, the landing page strategy has upsides and downsides.

#### The upsides:

- Leads, who eventually get to install, should be more engaged with the app.
- The more complicated services (for example, financial services) require more explanations to convert their leads, which is enabled by landing pages.

#### The downsides:

- The longer funnel reduces the final number of converted leads.
- It is more technically challenging to attribute.

## The challenges of mobile attribution on landing pages

- **Different media sources require different methods** to complete the landing page scenario with the correct attribution data.
- **Last click attribution model may cause loss of correct attribution**, if the landing page has its own attribution links.
- **Direct website visitors are recorded as organic**, unless the landing page has its own attribution links.
- **Desktop visitors are recorded as organic**, unless the landing page has a method of recording their conversions into mobile users.

## The solution

To solve the mentioned landing page attribution problems, you need to implement a javascript flow in your landing page. We offer a sample script implementation that you can use. Make sure to adjust the script to fit your requirements.

In some cases, you also need to make some adjustments to your campaigns.

The scenarios below cover the requirements for all possible media source cases.

## Landing page scenarios

Follow the implementation instructions below **for all the media sources** sending leads to your landing pages.

### Meta ads: cross-platform attribution

#### Description:

Meta ads is an SRN, which doesn't use external attribution links.

Upon the first app launch, AppsFlyer queries Meta ads whether the user has previously (within the last 28 days) engaged with an advertiser ad on the Facebook app. If they have, Meta ads self-attributes.

Meta ads also attributes cross-platform, meaning that the user may interact with any type of campaign, mobile or not, on any platform, to be self-attributed by Meta ads.

#### Conclusion:

A lead with the available device ID, coming from the Facebook app to a landing page, gets correctly attributed to Meta ads. This happens regardless of the new click recorded on the landing page.

However, when users opt not to share their device ID, as is expected with iOS 14 users during 2021, Meta ads' cross-platform attribution may not work anymore.

**When device ID sharing becomes optional, use the [Other SRNs method](/docs/deprecated-mobile-landing-page-attribution-script#other-srns-add-parameter) for Meta ads.**

- New users who share their device ID would be attributed to Meta ads correctly.
- New users who don't share their device ID would be attributed to "Facebook_LP".

#### Instructions:

1. On your Meta ads account create a **“Traffic” or "Conversions" campaign with mobile attribution enabled**, sending leads to your landing page.
2. Landing page Android download button - direct link to Google Play.
3. Landing page iOS download button - direct link to iTunes (OR attribution link **without the device ID**).

#### What the script does

The landing page script makes no changes. The script is designed to detect a user coming from the Facebook app. If it does, it doesn't do anything. It leaves the landing page direct links to the app stores as they are. This prevents another click from being recorded which could affect CTR.

In the script, look for a method called **_isFacebook()_** to learn more about what the script does when a user comes from the Facebook app.

### Google Ads: GCLID + offline conversion upload

#### Description:

The usual process for install attribution of Google Ads campaigns requires clicking leads to be redirected to the app's store page URL.

So, when redirecting leads from Google Ads to a landing page, use a mediator to connect between the mobile install and the original click on the non-mobile Google Ads campaign.

#### Conclusion:

The solution for Google Ads has 2 parts.

The first part takes care of **attributing on AppsFlyer** the mobile users that get to the landing page from Google, and install the app from there. It requires tagging the click URLs from Google, identifying them on the landing page and creating a dynamic OneLink with data from the URL.

The second part takes care of **notifying Google Ads** about these mobile installs, using Google's offline conversion upload method.

> 📘 Note
>
> This GCLID solution is not officially supported or recommended by Google.
>
> In case that Google deprecates the GCLID parameter, we will change the script to support the changes.
>
> We recommend following this article, by clicking the _**Follow**_ button in the article header, to get informed when there is an update to the article or attached script.

#### Instructions:

Part 1 - Attributing to Google Ads on AppsFlyer

On Google's dashboard - **Enable Auto-tagging** ( [here's how](https://support.google.com/analytics/answer/1033981?hl=en)).

With auto-tagging enabled, **the URL to the landingpage contains the _GCLID_ parameter**.

URL example:
```
http://www.yoursite.com/yourlandingpage?gclid={USER_GCLID}
```

On your landing page load -

1. Activate the _**generateUrl**_ Javascript function
2. The function (see below) looks for the _**GCLID**_ parameter and builds a long OneLink URL containing its value under the af_sub1 parameter (you can use any of the [subscriber parameters](https://support.appsflyer.com/hc/articles/207447163#what-are-subscriber-parameters-good-for) af_sub1 - af_sub5).
3. Landing page download button uses the generated OneLink URL.

OneLink URL example: `https://yourapp.onelink.me/abcd?pid=google_lp&c={CAMPAIGN_NAME}&af_sub1={USER_PARSED_GCLID}`
4. New mobile users are attributed to the **google_lp** media source and to the CAMPAIGN_NAME campaign (optional).
5. No postback is sent to the media source

At this point, the installs are reported in AppsFlyer under the **_google_lp_** media source, with the GCLID, but not in Google Ads.

Part 2 - Uploading Installs to Google as Offline Conversions

**This step is only required if you want the conversions to be recorded in the Google Ads platform.**

For users attributed to google_lp, the AppsFlyer raw data now displays the GCLID value in the **af_sub1** column. The GCLID is needed in order to upload offline conversions to Google Ads, you can find more information on the process [here](https://support.google.com/adwords/answer/7014069)).

The conversions can be uploaded manually or via an Adwords API (more info on the API [here](https://developers.google.com/adwords/api/docs/guides/conversion-tracking#importing_conversions)).

You can export the CSVs with this information from your AppsFlyer account, or you can get this data from Push API in real-time for every install.

> 👍 Tip
>
> You can also see the keywords your users searched for in AppsFlyer's raw data in a similar fashion to getting the GCLID:
>
> 1. For keyword recording, you must include the keyword [ValueTrack parameter](https://support.google.com/google-ads/answer/2375447) in the final URL from Google Ads to the landing page
>
> URL example:
> ```
> http://www.yoursite.com/yourlandingpage?gclid={USER_GCLID}&keyword={USER_KEYWORD}
> ```
> 2. The Javascript function (see below) looks for the _**keyword**_ parameter
> 3. The value is added to the generated OneLink URL under af_keywords
>
> OneLink URL example: `https://yourapp.onelink.me/abcd?pid=google_lp&c={CAMPAIGN_NAME}&af_sub1={USER_PARSED_GCLID}&af_keywords={USER_PARSED_KEYWORD}`
>
> The JS function below already contains the code to parse the keyword parameter as well.

#### What the script does

Google Ads carry with them a gclid parameter. The script looks for this parameter in the landing page URL. If it sees it, it creates the OneLink such that it reflects that the user comes from Google Ads. The script then puts the OneLink as the link behind the download buttons on the landing page.

In the script, look for **gclidValue** to learn how the script detects users coming from Google Ads and creates the OneLink accordingly.

### Other SRNs: add parameter

#### Description:

Other [SRNs](https://support.appsflyer.com/hc/articles/360001546905-Self-Reporting-Networks#srns-integrated-with-appsflyer), for example, Snapchat or Twitter, are not cross-platform like Meta ads, and require a bit of work to get your mobile users attributed to them.

Your campaigns with other SRNs lead your users to the landing page, and you are billed according to clicking leads, unrelated to any derived mobile users.

#### Conclusion:

When defining the landing page URL for a campaign on SRNs (besides Meta ads and Google Ads), add a Partner ID parameter to the URL, which states the original SRN.

The landing page launches a javaScript (see below) that parses that parameter and builds a OneLink URL, which has the Partner ID value. When mobile users click on that OneLink and install, they get attributed to the stated media source.

#### Instructions:

On your SRN account -

1. Create a non-mobile campaign
2. When defining the landing page URL, add a Partner ID + landing page parameter to the URL (which is not an AF attribution link). The format is " _**&af_pid=srn_lp**_". (see example below)

On your landing page load -

1. Activate the _**generateUrl**_ Javascript function
2. The function looks for the _**af_pid**_ parameter and builds a OneLink URL containing its value under the _**pid**_ parameter
3. Landing page download button uses the generated OneLink URL
4. New mobile users are attributed to the custom "Partner ID + landing page" media source
5. No postback is sent to the media source

If you specify the real SRN name, e.g. twitter_int, a postback might be sent to this SRN. This could result in double charges. See the note below for alternative names.

The script itself contains logic to prevent you from using these names. Look for `var SRNs` in the script. You should see a list of SRN names and a condition that checks if `pidValue` is any of these names. Remove this logic after you are done testing the script.

> 📘 Note
>
> If you're sending users to your landing page, we recommend that include the following parameter on the URL of your landing page:
>
> - For Twitter: use " _**&af_pid=twitter_lp**_"
> - For Snapchat: use " _**&af_pid=snapchat_lp**_"
> - For Doubleclick: use " _**&af_pid=doubleclick_lp**_"
> - For Meta ads Post (unpaid): use " _**&af_pid=fbpost_lp**_"
> - For Oath (formerly Yahoo Gemini): use " _**&af_pid=oath_lp**_"

#### What the script does

The script sees the af_pid parameter on the landing page URL and concludes that the user comes from an SRN or some other custom network. The script creates a OneLink accordingly and sets it as the link behind the download button on the landing page.

To learn more about what the script does, look for **pidValue** in the script.

### Attribution links: redirect with af_r

#### Description:

Attribution links are used for any media source, which is not an SRN. That includes thousands of integrated partners and any owned media you wish to attribute.

Luckily, the solution for landing page attribution when using AppsFlyer's attribution links is simple (and similar to the solution for Meta ads).

#### Conclusion:

the attribution link redirects the lead to a landing page, and by that also takes care of the correct attribution (if a mobile install follows).

All that is left to do is NOT prevent the correct attribution with another last click.

#### Instructions:

1. [Create the attribution link](https://support.appsflyer.com/hc/articles/208874366#create-a-onelink-link) for the media source
2. Add the [landing page parameter](https://support.appsflyer.com/hc/articles/208874366#redirection) leading to your landing page to the attribution link
3. Add `&af_redirect=true` to the landing page value under **any redirection parameters** (that is, af_r, af_ios_url, and af_android_url) in the attribution link.

Example: `https://yourapp.onelink.me/abcd?pid=email&c={CAMPAIGN_NAME}&af_r=http://www.yoursite.com/yourlandingpage?af_redirect=true`
4. **Optional** - add device ID (GAID / IDFA) to the attribution link to allow attribution by ID matching instead of Probabilistic modeling
5. Landing page Android download button - direct link to Google Play
6. Landing page iOS download button - direct link to iTunes

> 📘 Note
>
> The script and HTML sample page provide the option to set one download button that serves both Android and iOS. Read the comments in the script to learn how to implement it.

#### What the script does

The script looks for the **af_redirect** parameter in the landing page URL. If it sees it, it makes no changes to the download buttons on the landing page. This is because the af_redirect parameter indicates that the user reaches the landing page following a click. Therefore, there is no need for additional attribution links.

To learn more about what the script does to handle cases where users reach the landing page after clicking an attribution link, see the method **isAFLink()** in the script.

### Links with utm parameters: dynamic OneLink

#### Description

You may have traffic sources, which redirect users to your landing page using links with UTM parameters.

#### Conclusion:

If the original URL is NOT an AppsFlyer attribution link, the script searches for the _**utm_source**_ and _**utm_campaign**_ parameters in the link. If they exist, the script prepares a OneLink URL, that has them as the media source name (pid) and campaign name (c), respectively.

Note that with AppsFlyer attribution links, which also contain UTM parameters, the AppsFlyer parameters are being used, rather than the UTM ones.

#### Instructions:

On the media source -

1. Make sure the _**utm_source**_ exists in the link.
2. _**utm_campaign**_ parameter is optional but highly recommended.

On your landing page load -

1. Activate the _**generateUrl**_ Javascript function
2. The function looks for the _**utm_source**_ and _**utm_campaign**_ parameters and builds a OneLink URL containing their values
3. Landing page download button uses the generated OneLink URL
4. New mobile users are attributed to the value of _**utm_source**_ as the media source
5. No postback is sent to the media source.

#### What the script does

The script looks for UTM parameters in the landing page URL. If it finds any, it converts them to OneLink parameters. This way, campaign information is carried over to the final attribution.

### Mobile organic visitors: OneLink with pid=website

#### Description

Mobile organic visitors are, by definition, direct mobile web leads from unknown sources. They rarely visit dedicated landing pages but may be the vast majority of mobile installs coming from the advertiser's website.

#### Conclusion:

If you have a significant amount of mobile organic traffic from your website, it's highly recommended to record the attribution data of your own traffic.

#### Instructions:

To attribute mobile organic visitors, the website should have _**download**_ or _**install**_ buttons, with a OneLink attribution link behind them. OneLink enables diagnosing the device type and redirecting the lead to the correct app store according to it.

To learn how to set and build OneLink URLs go [here](https://support.appsflyer.com/hc/articles/207032246-OneLink-Redirections-Setup-Guide).

> 👍 Tip
>
> Add "&pid=website" to your attribution link to attribute all these visitors to your website.
>
> In each page of your website, which has a download/install button with an attribution Link, add "&c={PAGE NAME}". This can help you find the highest and lowest converting pages in your website.

#### What the script does

Exhausting all other options, the script determines that the user is an organic user that doesn't come from any campaign. The script creates a OneLink that reflects that and puts it as the link behind the download button on the landing page.

### Desktop visitors: telephone/email form

#### Description

All the options covered above assume the users use mobile devices when engaging with the campaign and the landing page.

But what about desktop users?

Desktop users may arrive at your landing page/website, and afterward "independently" visit the app store with their mobile devices, and install the mobile app. Without the preceding engagement with the mobile devices, it is impossible to attribute these users, and so, they are labeled as "Organic".

#### Conclusion:

A great solution to this attribution problem is using a **text-to-download form on your landing page**, only for desktop users. This is to be followed by sending the mobile device an SMS/Email with OneLink URL.

#### Instructions:

1. Identify that a visitor is a desktop user
2. When your user types in their phone number, text them a link to your app, with a OneLink short URL. You can also ask for their email address to email them app download messages.
3. The usage of OneLink is crucial here, as the mobile device platform isn't known when sending the message to the users. OneLink's diagnosis and redirection functionalities take care of this for you.
4. Add "&pid=desktop_website" to the OneLink URL to identify this source.
5. Add "&c={PAGE NAME}" to help you find the highest and lowest converting pages in your website for desktop users.

#### What the script does

The script detects the device or platform the user is on. If it's desktop, the script returns a link to a web form URL and puts it behind the download buttons. When the user clicks download, they are sent to a web form where they fill in their details to get an SMS or an email with a link to download the app.

It's up to you to create the web form and provide the URL to it in the script. To learn more, look for **isMobileDevice()** in the script.

## Landing page javascript

Below you can find the code implementation of the javascript that performs the full scope of attributing media sources and campaigns in landing page scenarios. **If you want to have additional data such as ad sets and ad ids, you should make the necessary adjustments in the script**.

For your convenience, you can also download the attached landing page example.

Below the code, you can find the instructions for adapting it to your landing page needs.

### The script

Consider the following before you implement the script:

- The script is offered as an example only. It covers the common landing page to attribution flow. Adapt the script to fit your requirements.
- The script looks for specific parameters in the landing page URL, like media source, campaign, keywords etc. If you want to add more parameters like site id and ad sets, you need to modify the script accordingly.

```javascript
//Returns the value of a parameter existing in the page's URL or ' ' if not exists.
function getParameterFromURL(name, url) { 
  if (!url) url = window.location.href;
  name = name.replace(/[\[\]]/g, '\\$&');
  var regex = new RegExp('[?&]' + name + '(=([^&#]*)|&|#|$)'),
    results = regex.exec(url);
  if (!results) return null;
  if (!results[2]) return '';
  return decodeURIComponent(results[2].replace(/\+/g, ' '));
}

function isMobileDevice() {
  return (typeof window.orientation !== "undefined") || (navigator.userAgent.indexOf('IEMobile') !== -1);
}

function getMobileOperatingSystem() {
  var userAgent = navigator.userAgent || navigator.vendor || window.opera;
  if (userAgent) {
    if (/android/i.test(userAgent)) {
      return "Android";
    }

    // iOS detection from: http://stackoverflow.com/a/9039885/177710
    if (/iPad|iPhone|iPod/.test(userAgent) && !window.MSStream) {
      return "iOS";
    }
  }
  return "unknown";
}

function isAFLink() {
  return getParameterFromURL('af_redirect');
}
// Note - when device ID sharing becomes optional stop calling this method (or always return false)
function isFacebook() {
  if (document.referrer && document.referrer != "") {
    return document.referrer.toLowerCase().includes('facebook');
  } else {
    return false;
  }
}

// generateUrl returns the URL to use behind the iOS and Android "Download" buttons on a landing page, based on the source of the page visitor.
// By default these buttons should direct to the apps' pages on iTunes and Google Play.
// If these links should be kept with no change, generateUrl returns ' '.
// Otherwise, generateUrl returns the URL to be used under BOTH buttons (a single app download button could also be used in this case).
// Parameters: isDebug - if true, alerts are issued for each of the cases, otherwise not.
function generateUrl(isDebug) {
  var oneLinkURL = 'https://yourapp.onelink.me/abcd';   // **** Replace with your own basic OneLink URL ****
  var webFormURL = 'https://yoursite.com/webform.html'; // **** Replace with your own web form URL for getting the user's email or SMS ****
  var finalURL = "";
  var partnerIDParam = '?pid=';

  var campaignValue;
  if (getParameterFromURL('c')) {
    campaignValue = getParameterFromURL('c');
  } else if (getParameterFromURL('utm_campaign')) {
    campaignValue = getParameterFromURL('utm_campaign');
  } else if (document.getElementsByTagName('title')[0]) {
    campaignValue = document.getElementsByTagName('title')[0].innerText;
  } else {
    campaignValue = 'unknown';
  }
  var campaignParam = '&c=';
  var gclidParam = '&af_sub1=';
  var gclidValue = getParameterFromURL('gclid');
  var kwParam = '&af_keywords=';
  var pidValue;
  var kwValue = getParameterFromURL('keyword');

  if (getParameterFromURL('af_pid')) {
    pidValue = getParameterFromURL('af_pid');
  } else if (getParameterFromURL('utm_source')) {
    pidValue = getParameterFromURL('utm_source');
  }

  // Prevent the use of real SRN names. Remove this part after you are done testing the script.
    var SRNs = [
    'twitter_int',
    'facebook_int',
    'snapchat_int',
    'doubleclick_int',
    'yahoogemini_int',
    'yahoojapan_int',
  ];

  if (SRNs.includes(pidValue)) {
  	alert("DO NOT USE NAMES OF SRNS IN af_pid or utm_source - use the names listed in Other SRNs: Add Parameter section in the landing page article\nhttps://support.appsflyer.com/hc/en-us/articles/360000677217#other-srns-add-parameter");
    return;
  }

  // Desktop user
  if (!isMobileDevice()) {
    return webFormURL;
  }

  // User was redirected using af_r parameter on an AppsFlyer attribution link
  if (isAFLink()) {
    if (isDebug) {
      alert("This user comes from AppsFlyer by redirection and is ready to be attributed. \nKeep direct app store links.");
    }
    return; // in this case, the original store links in the install buttons stay the same

    /*
    If you want one install button in the landing page that serves both iOS and Android, uncomment the code below
    The code identifies the operating system and returns the relevant direct link to Google Play or iTunes

    if (getMobileOperatingSystem() === 'Android') {
      return 'direct link to Google Play';
    }

    if (getMobileOperatingSystem() === 'iOS') {
      return 'direct link to iTunes';
    }
    */
  }

  // Google Ads
  if (gclidValue) {
    partnerIDParam += 'google_lp';
    campaignParam += campaignValue;
    gclidParam += gclidValue
    if (!kwValue) {
      finalURL = oneLinkURL + partnerIDParam + campaignParam + gclidParam;
      if (isDebug) {
        alert("This user comes from Google AdWords\n " + finalURL);
      }
      return finalURL;

    } else { // Google Ads with KW
      kwParam += kwValue;
      finalURL = oneLinkURL + partnerIDParam + campaignParam + gclidParam + kwParam;
      if (isDebug) {
        alert("This user comes from Google AdWords - there is a keyword associated with the ad\n " + finalURL);
      }
      return finalURL;
    }

  // Other SRNs and custom networks
  } else if (pidValue) {
    campaignParam += campaignValue;
    partnerIDParam += pidValue;
    finalURL = oneLinkURL + partnerIDParam + campaignParam;
    if (isDebug) {
      alert("This user comes the SRN or custom network " + pidValue + "\n" + finalURL);
    }
    return finalURL;
  } else if (isFacebook()) {
    if (isDebug) {
      alert("This user comes from a paid Facebook ad - don't do anything. \nKeep direct app store links.");
    }
    return ' ';

  } else { // organic mobile user
    campaignParam += campaignValue;
    partnerIDParam += 'website'; //**** Replace value if you wish organic users to be attributed to another media source than 'website' ****
    finalURL = oneLinkURL + partnerIDParam + campaignParam;
    if (isDebug) {
      alert("This user comes from an unknown mobile source.\n The user would be attributed to media source 'website' and to the campaign " + campaignParam + "\n" + finalURL);
    }
    return finalURL;
  }
}
```

### HTML sample for landing page

```html
<html>
<head>
  <title>Landing Page</title>
</head>
<body>
  <h1>Landing Page</h1>
  <!-- By default, the install buttons should have direct links to the stores -->
  <div>
    <a id="andrd_link" href="https://play.google.com/store/apps/details?id=com.appsflyer.sampleapp"><img src="/images/andrd.png" alt="" /></a>
  </div>
  <div>
    <a id="ios_link" href="https://itunes.apple.com/us/app/id3********"><img src="/images/ios.png" alt="" /></a>
  </div>
  <!-- If you want one button to serve both Android and iOS, use the code below instead
  <a id="store_link" href=""><img src="download.png" alt=""></a>
  -->
  <script type="text/javascript" src="/landing-page-test.js"></script>
  <script type="text/javascript">
    window.onload = function () {
      var url = generateUrl(true);

      // onelink is generated
      if (url) {
        document.getElementById('andrd_link').setAttribute('href', url);
        document.getElementById('ios_link').setAttribute('href', url);
      }

      //otherwise, if onelink is not generated it means that the user is redirected
      // and the store links in the buttons stay the same

      /* for the one button solution for both Android and iOS, use the code below instead

      document.getElementById('store_link').setAttribute('href', url);

      */

    };
  </script>
</body>

</html>
```

> 👍 Tip
>
> You can implement the javascript snippet using Google Tag Manager. Google Tag Manager makes it easier for you to control when and where the landing page javascript should be used.

### Instructions

1. Activate the _**generateUrl**_ script on page load of any page in your web site, which visitors can land on directly, and that has _**Download**_ button/s for your mobile app/s.

> ❗️ Important!
>
> **By default the _Download_ buttons should direct to the apps pages on iTunes and Google Play**. If these links are kept with no change (i.e. visitor from AF attribution link or Meta ads), _**generateUrl**_ returns ' '. Otherwise, it returns the URL to be used with BOTH Download buttons (a single _**Download**_ button could also be used in this case to cover for both apps with OneLink).

2. Replace the _**oneLinkURL**_ parameter value with your own basic OneLink URL in the exact format as the placeholder `https://yourapp.onelink.me/abcd`.

MANDATORY to attribute visitors from all SRNs (except Meta ads paid ads) and for mobile organic visitors.
3. Replace the _**webFormURL**_ parameter value with your own web form link. The web form should be able to get the user's email or SMS, and send the user's mobile device a message with a OneLink URL for downloading the app.

MANDATORY to attribute desktop visitors.
4. Replace the _**partnerIDParam**_ parameter value, if you wish mobile organic users to be attributed to another media source than 'website'.
5. By default, users are attributed to the web page they are at when clicking the _**Download**_ button unless another campaign name is specified in the landing page URL (`&c={CAMPAIGN_NAME}`). To change that, replace the value of _**campaignParam**_ parameter value.

Optional for ALL scenarios, except Meta ads paid ads.

## Viewing the results

![dashboard_landing_page_results.png](https://files.readme.io/04c44de83ad2b97c0d89224e24050763679150e6d6ccde8c5fc7fbe2eb2cd324-dashboard_landing_page_results.png)

As with any media source, you can view your landing page results on your app's dashboard, raw data or via AppsFlyer APIs.

If your mobile marketing funnel always leads to your landing page, these media sources represent the following:

| **Source** | **Description** |
| --- | --- |
| **organic** | Users that didn't go through the landing page, or didn't engage with it. Alternately, users that did engage but were not attributed for various reasons, e.g. passed the attribution look back window before launching the app. |
| **website** | Organic mobile users visiting your landing page/website and installing afterward |
| **Meta ads** | Users from paid Meta ads |
| **fbpost_lp** | Users from viral non-paid Meta ads posts |
| **google_lp** | Users from Google ads |
| **[SRN]_lp** | Users from other SRNs, i.e. Twitter (twitter_lp), Snapchat (snapchat_lp), Doubleclick (doubleclick_lp) or Oath (oath_lp) |
| **Integrated partner ID** | Users coming from an integrated partner's ad, which uses AppsFlyer's attribution link. For example, inmobi_int, tapjoy_int |
| **desktop** | Desktop users filling in the web form, and completing an install after clicking on the SMS or email sent to their mobile devices afterwards |
| **Other sources** | Users coming from owned media sources, which use AppsFlyer's attribution links. For example, email, sms, blog_post, etc |

## OneLink for landing page solution

OneLink™ is a unique AppsFlyer attribution link, which is used for device detection and redirection, or for deep linking.

The [Social apps landing page](https://support.appsflyer.com/hc/articles/208874366-OneLink-2-4-Sending-existing-users-to-open-your-app#social-app-landing-page) solution requires the advertiser to have a basic OneLink URL. Users who click ads in social media apps are then redirected to an AppsFlyer-generated landing page. From there, they can be deep linked, or continue to install the app.

AppsFlyer provides a variety of social media apps landing page templates. Element positions in the templates are fixed, but the elements themselves are customizable, including background image or color, titles, texts, images, buttons, tags, and more.

If you haven't implemented OneLink for your app:

1. Configure [OneLink template](https://support.appsflyer.com/hc/articles/207032246#procedures).
2. Create a [OneLink URL](https://support.appsflyer.com/hc/articles/208874366#create-a-onelink-link) based on the template.
3. In the script, replace https://yourapp.onelink.me/abcd with your OneLink URL.