---
title: Set up your domain redirect allowlist
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2024-05-15T11:31:00Z'
  edited_at: '2026-05-14T12:00:22Z'
  id: 25068636064529
  locale: en-us
  section: Account security
  section_id: 6551173202065
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/25068636064529-Set-up-your-domain-redirect-allowlist
---
> **At a glance:** Set up a domain redirect allowlist to ensure users are redirected to verified, trustworthy domains, protecting their data and safeguarding your brand integrity.

## <Image alt="Main redirect allowlist image.png" src="https://files.readme.io/a13b1c4641f4b265ef93ba9b65c57b0a7891336d6f6c21e94dd2ff5d83b948d6-30258741325713.png" width="1340px" />About the redirect allowlist

Use the redirect allowlist to define a list of specific root domains and subdomains to which link redirection is allowed, to protect your links from unauthorized redirects, phishing attacks, and fraud. Once your allowlist is active, links you create via AppsFlyer will only redirect users to web URLs whose domains are in the allowlist. Otherwise, users will be sent to the app store. The redirect allowlist applies to <Anchor target="_blank" href="/marketers/id/docs/onelink-guide">OneLink</Anchor>, single-platform attribution links via <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#attribution-link-tab">partner integration</Anchor>, and <Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-platform-direct-attribution-links">direct attribution links</Anchor> for CTV, PC, and console platforms. The redirect allowlist (and custom web redirection) is available to Zero, Growth, and Enterprise plan subscribers. To prevent abuse, Zero plan subscribers must have a credit card on file (it will not be charged).

## Set up your redirect allowlist

You can set up your allowlist manually or via CSV file. Before setup, it's recommended to verify your trusted domain list with your security team.

<div id="manual-setup" />

<Accordion title="Manual setup">

**To set up manually:**

1. From the top bar, open the account menu (email address dropdown) > **Security Center**

<Image align="center" alt="from account click security center Cropped.jpg" src="https://files.readme.io/4ee3279e382e97817a6b977f50bff7054868f03c22186ed2bd79d712e2316ad4-25381243839377.jpg" />

2. In the **Redirect allowlist** section, click **Manage redirect allowlist**.

<Image align="center" alt="Manage redirect allowlist with arrow.jpg" src="https://files.readme.io/e9cd8c263eb618b86d3c10b1d9fc367390dfd1f9b6cc12afd7ac5f37411ba25c-25644439175313.jpg" width="549px" />

The **Redirect allowlist** page opens.

3. Under the **Manual** tab, enter a root domain or subdomain in the **Domain name** field, then click **Add domain to list**.

<Image align="center" alt="Manually add domains.jpg" src="https://files.readme.io/95b37db2064ddba8c787d2dd5ac5ab2aa7698605f5c6eb3b4a59dd6324dee355-25103405228689.jpg" width="403px" />

* Use only letters, numbers, hyphens, and periods.
* Domains must start and end with a letter or number and can be up to 253 characters.
* Don't add prefixes, such as https://.

See also allowlist [traits and limitations](/docs/set-up-your-domain-redirect-allowlist#traits-and-limitations).

The added domains will be displayed in the right-side list.

4. Click **Save list**.

Once saved, the allowlist will be enforced on clicks within about an hour.

</Accordion>

<div id="setup-via-csv-file" />

<Accordion title="Setup via CSV file">

**To set up via CSV file upload:**

1. From the top bar, open the account menu (email address dropdown) > **Security Center**  

<Image align="center" alt="from account click security center Cropped.jpg" src="https://files.readme.io/4ee3279e382e97817a6b977f50bff7054868f03c22186ed2bd79d712e2316ad4-25381243839377.jpg" />

2. In the **Redirect allowlist** section, click **Manage redirect allowlist**.  
<Image align="center" alt="Manage redirect allowlist with arrow.jpg" src="https://files.readme.io/e9cd8c263eb618b86d3c10b1d9fc367390dfd1f9b6cc12afd7ac5f37411ba25c-25644439175313.jpg" width="530px" />

The **Redirect allowlist** page opens.

3. Click the **CSV file** tab, then follow the **CSV file instructions** to create a file containing your domain list.  
<Image align="center" alt="CSV file upload.jpg" src="https://files.readme.io/2be73080048545f79e102e6f48df0db956e6739f156153c172c4fef5a2ea339f-25381979219345.jpg" />

4. Upload the CSV file to the upload field.

* Once the file is uploaded it will be parsed, and values will be validated.
* Valid values will be automatically added and displayed in the right-side list.
* Invalid values won’t be added. Information about invalid values will be displayed in the **Upload status** section so you can take the following action: review or fix the values and re-upload. See allowlist [traits and limitations](/docs/set-up-your-domain-redirect-allowlist#traits-and-limitations) for more details.

5. Click **Save list**.

Once saved, the redirect allowlist will be enforced on clicks within about an hour.

</Accordion>

<div id="edit-the-redirect-allowlist" />

<Accordion title="Edit the redirect allowlist">

You can add or delete domains from the allowlist at any time.

**To delete a domain from the allowlist:**

1. On the right-side list, hover on the domain you want to delete and a delete icon will appear.
2. Click the delete icon.
3. Click **Save list** to save the change.

**Note:** Once saved, the updated redirect allowlist will be enforced on clicks within about an hour.

</Accordion>

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Setup | <ul><li>The redirect allowlist can be accessed and managed by the "Admin" and "Security" roles.</li><li>The redirect allowlist is at the account level and applies to all apps in the account and all AppsFlyer links.</li><li>The redirect allowlist is not available to team members associated with multiple accounts if an account lacks a payment method.</li><li>Notify coworkers and stakeholders managing AppsFlyer link creation about redirect allowlist enforcement and the permitted redirect domains.</li></ul> |
| Applicability | <ul><li>The allowlist affects **all links created via AppsFlyer**, either with <Anchor target="_blank" href="/marketers/id/docs/onelink-guide">OneLink</Anchor>, single-platform attribution links via <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#attribution-link-tab">partner integration</Anchor>, or <Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-platform-direct-attribution-links">direct attribution links</Anchor> for CTV, PC, and console platforms, no matter when they were created.</li><li>Include in the allowlist the domains of any URL set as a value on the link redirection setup specified here, whether it's a custom website/landing page, the Google Play/App Store, or another app store website. The allowlist supports and protects redirections for the following:<ul><li>Link parameters:<ul><li>`af_r`</li><li>`af_web_dp`</li><li>`af_ios_url`</li><li>`af_android_url`</li></ul></li><li>OneLink template redirection setup for iOS, Android, and Desktop.</li><li>`af_dp` with a web URL value, however, this is not a recommended value type. This parameter is intended to populate a <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#af_dp">URI scheme</Anchor> to open your app.</li></ul></li><li>**Link previews may show fallback content:** When AppsFlyer generates a social preview for a link, it validates the link’s redirect parameters against your redirect allowlist. If it isn’t, AppsFlyer won’t fetch a preview from that page and will instead show a fallback preview.</li></ul> |
| Domains | <ul><li>The allowlist must include at least one domain.</li><li>Only root domains or subdomains are allowed, not specific paths. Don't include `https://` or `http://` protocols in the value.</li><li>When adding a root domain, it will apply to all subdomains within the root domain.<br />For example, if the root domain "website.com" is added, it will cover "abc.website.com" and "xyz.website.com" as well.</li><li>Redirection is only supported for publicly accessible domains.</li><li>Don't include AppsFlyer domains (e.g., onelink.me, app.appsflyer.com) or other domains that have their own redirection mechanism (e.g., bit.ly) to fortify the predictability of the redirection of your links.</li><li>Up to 250 domains/subdomains can be added to the allowlist. You can view the number of domains already added by going to the redirect allowlist, where the number of domains is indicated.</li></ul> |
| Redirection | If you’re unsure whether a domain your link redirects to is allowed:<br /><br />Review the allowlist to make sure it’s included.<br /><br />Or<br /><br />Use the <Anchor target="_blank" href="/marketers/id/docs/discover-your-campaign-link-parameters-and-behavior">Link Discovery</Anchor> tool. When a link is entered, an alert will appear in the **Parameters** column (under **Redirection**) if a domain isn’t in the allowlist. |

<div data-zendesk-anchors="overview=about-the-redirect-allowlist h_01HYTJSH4YMAJ3CV88KZ9JD9XR=about-the-redirect-allowlist h_01HY0BNRBEN91348744YME42SW=set-up-your-redirect-allowlist h_01HY04JEK8J3664HE8J9783S61=manual-setup h_01HY04JEK8Y51EG3H6WFKHYYH4=setup-via-csv-file h_01HY04JEK840Q4DZ2SRMTB7HRE=edit-the-redirect-allowlist h_01J6S6HS0H0M6GQ81WGZ3XT0P9=traits-and-limitations" />
