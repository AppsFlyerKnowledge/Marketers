---
title: URI scheme fallback for iOS
metadata:
  keywords:
    - Advertisers
    - Redirects
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2017-05-10T12:50:00Z'
  edited_at: '2025-11-25T15:15:46Z'
  id: 115002366466
  locale: en-us
  section: iOS platform
  section_id: 6551263106577
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/115002366466-URI-scheme-fallback-for-iOS
---
> **At a glance:** Understand the flow when a user with an iOS device clicks on a OneLink custom link and Universal Links fails to open the app.

<div id="about-uri-fallback-for-ios" />

## About URI fallback for iOS

* The best-supported way to open apps on iOS devices is by using Universal Links. Since 2016, there are considerable built-in OS limitations to using URI schemes as a fallback method for when iOS Universal Links don't open the app. These limitations are not AppsFlyer-related, and would also impact any other links with URI schemes you might use to open the app.
* By default, URI schemes (carried as the value of the af\_dp param) are only used as a fallback method for opening the app on iOS on a few specific browsers/platforms.
* For Safari, you can try to use URI schemes as a fallback to open apps on iOS by setting the following parameters on your OneLink URL: 
  * `af_dp` (that carries the URI scheme as the value).
  * `af_force_deeplink=true` (that forces the app to open using the af\_dp URI scheme). Without this parameter, the app doesn't open using the URI scheme.
* For other browsers, URI schemes are unpredictable and therefore, not supported by default. Users clicking the link are likely to be redirected to the App Store (or if set, to the URL set on the `af_ios_url` param).
* See the scenarios flowchart and use cases that follow for additional details.

<div id="note" />

> 📘 **Note**
>
> X (Twitter) does not support URI schemes. We recommend using a social app landing page with Universal Link setup to avoid app-launching issues.

<div id="scenarios-flowchart" />

### Scenarios flowchart

<Image align="center" alt="flowchartdoctored.png" src="https://files.readme.io/5917ad4d8a01010db16eb16dd4c9a5beca02e80797ec9d47999772a8d4433401-41284711408529.png" width="1564px" />

<div id="use-cases" />

## Use cases

<div id="browsers-that-can-use-uri-schemes-by-default" />

<Accordion title="Browsers that can use URI schemes by default">

Sometimes, Universal Links fail to open the app, either because the app does not exist, or the link does not have Universal Links configured. In those cases, the following browsers/platforms can use URI schemes as a fallback method to open the app by default:

* Chrome
* Kakaotalk
* Naver
* Naver-Blog
* Weibo

<div id="flowchart" />

#### **Flowchart**

<Image align="center" alt="use case flowchart.png" src="https://files.readme.io/9b68ccc634b55d72a9be8f8b07d9744214a10b2f14f11bf97416fcb377b28963-41284872656401.png" width="75.41%" />

</Accordion>

<div id="safari" />

<Accordion title="Safari">

The following describes the flow for users when Universal Links fail to open the app, and the link contains `af_dp` (that carries the URI scheme as the value).

**If the app is not installed:**

1. Safari error message dialog displays: "Safari cannot open the page because the address is invalid”  
   <Image align="center" alt="" src="https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg" />
2. User clicks **OK** to dismiss the dialog, briefly sees a landing page load in the background, and then within 1 second, is automatically redirected to the App Store, or as per the af\_ios\_url param.

**If the app is installed:**

* If the link does not contain `af_force_deeplink=true`, user is redirected to the App Store, or as per the af\_ios\_url param.
* If the link contains `af_force_deeplink=true`:
  1. Safari dialog displays.  
     <Image align="center" alt="" src="https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg" />
  2. If the user clicks **Open**, the app opens.
  3. If the user clicks **Cancel:**
     * If the af\_ios\_url param is set, the user is redirected accordingly.
     * If the af\_ios\_url param is not set, the Safari error message dialog displays over a landing page in the background which says "Safari cannot open the page because the address is invalid”.  
       <Image align="center" alt="" src="https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg" />
  4. User clicks **OK** and see a landing page with a call to action (CTA).
  5. User clicks the CTA and a dialog displays.  
     <Image align="center" alt="" src="https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg" />
  6. If the user clicks **Open**, the app opens.
  7. If the user clicks **Cancel**, a dialog displays.  
     <Image align="center" alt="" src="https://files.readme.io/dd3aa8492bdf1883246bd740118e1b8d2f075a77a164e3ad55843f7c4d44d2b9-360016210038.jpg" />
  8. If the user clicks **OK**, they are redirected to the App Store.
  9. If the user clicks **Cancel**, they remain on the landing page.

<div id="flowchart-1" />

#### **Flowchart**

<Image align="center" alt="Copy_of_Ios_fall_back_-_safari.png" src="https://files.readme.io/5e50eb558b23a849f02e1ffe5df3181ad7c8d9514f5813fbffcfa6160493de81-360016515318.png" />

</Accordion>

<div id="facebook-post-unpaid" />

<Accordion title="Facebook post—unpaid">

The following describes the flow for users when Universal Links fail to open the app, and the link contains `af_dp` (that carries the URI scheme as the value).

**If the app is installed:**

* The app opens.

**If the app is not installed:**

1. If there is no social media app configured, or after the user clicks the CTA on the SALP, a dialog displays over a landing page in the background.  
   <Image align="center" alt="" src="https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg" />
2. Click Open App. One of the following results can occur:
   * If the `af_ios_url` param is set, the user is redirected accordingly.
   * If the `af_ios_url` param is not set and if `af_force_deeplink=true` is not on the link the user is redirected accordingly.
   * If the af\_ios\_url param is not set, and If `af_force_deeplink=true` is on the link, the dialog displays again over the landing page in the background.  
     <Image align="center" alt="" src="https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg" />
3. If the user clicks **Open**, they are sent to the App Store.
4. If the user clicks **Close**, the landing page in the background displays.  
   <Image align="center" alt="" src="https://files.readme.io/98748f47f3f9df43addc9c871c8165ecf4f849b17bdcfd660b90d4b6ded6727d-360016668478.jpg" />
5. User clicks the App Store badge and is redirected to the App Store.

<div id="flowchart-2" />

#### **Flowchart**

<Image align="center" alt="diagram-X.png" src="https://files.readme.io/0c8040d27bbf34fdf1374b4b40a8239b6af7b6c7719db9666f36dd2829bc3217-small-17710399441553.png" />

</Accordion>

<div data-zendesk-anchors="h_01HFV6PXS5401CCW6N2T04HGSM=about-uri-fallback-for-ios h_01KAXQDBSG2YCPBDYYPFHBXR91=note h_01HFV6PXS5WWS0B1VYF7RJAV1J=scenarios-flowchart h_01HFV6PXS51B2W497TADRGBX7Y=use-cases h_01HFV6PXS5HE462CJEE18CM5ZR=browsers-that-can-use-uri-schemes-by-default h_01HFV6PXS5N98MHJFYPSAB5XKZ=flowchart h_01HFV6PXS521E3MTCHJ5QBQGJ2=safari flowchart::db5f50ee=flowchart-1 h_01HFV6PXS57ZRSX2WAECS69XB4=flowchart-1 facebook-post%E2%80%94unpaid=facebook-post-unpaid h_01HFV6PXS5K8YZPE2B82V3DNTV=facebook-post-unpaid flowchart::df1b7de0=flowchart-2 h_01HFV6PXS504YQRDHZ1S1WS8CV=flowchart-2" />
