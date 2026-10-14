---
title: "Set up your domain redirect allowlist"
excerpt: "Set up a domain redirect allowlist to ensure users are redirected to verified, trustworthy domains, protecting their data and safeguarding your brand integrity."
x-zendesk:
  id: 25068636064529
  url: https://support.appsflyer.com/hc/en-us/articles/25068636064529-Set-up-your-domain-redirect-allowlist
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Account security
  section_id: 6551173202065
  position: 4
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-negri, Marketers, Platform essentials]
  labels: [Marketers, Loc Published]
  promoted: false
  comments_disabled: false
  created_at: '2024-05-15T11:31:00Z'
  edited_at: '2026-05-14T12:00:22Z'
---
## ![Main redirect allowlist image.png](https://files.readme.io/a13b1c4641f4b265ef93ba9b65c57b0a7891336d6f6c21e94dd2ff5d83b948d6-30258741325713.png) About the redirect allowlist

Use the redirect allowlist to define a list of specific root domains and subdomains to which link redirection is allowed, to protect your links from unauthorized redirects, phishing attacks, and fraud. Once your allowlist is active, links you create via AppsFlyer will only redirect users to web URLs whose domains are in the allowlist. Otherwise, users will be sent to the app store. The redirect allowlist applies to [OneLink](/docs/onelink-guide), single-platform attribution links via [partner integration](/docs/set-up-an-integrated-partner#attribution-link-tab), and [direct attribution links](/docs/ctv-pc-and-console-platform-direct-attribution-links) for CTV, PC, and console platforms. The redirect allowlist (and custom web redirection) is available to Zero, Growth, and Enterprise plan subscribers. To prevent abuse, Zero plan subscribers must have a credit card on file (it will not be charged).

## Set up your redirect allowlist

You can set up your allowlist manually or via CSV file. Before setup, it's recommended to verify your trusted domain list with your security team.

<Accordion title="Manual setup">

**To set up manually:**

1. From the top bar, open the account menu (email address dropdown) > **Security Center**

![from account click security center Cropped.jpg](https://files.readme.io/4ee3279e382e97817a6b977f50bff7054868f03c22186ed2bd79d712e2316ad4-25381243839377.jpg)

2. In the **Redirect allowlist** section, click **Manage redirect allowlist**.

![Manage redirect allowlist with arrow.jpg](https://files.readme.io/e9cd8c263eb618b86d3c10b1d9fc367390dfd1f9b6cc12afd7ac5f37411ba25c-25644439175313.jpg)  

The **Redirect allowlist** page opens.

3. Under the **Manual** tab, enter a root domain or subdomain in the **Domain name** field, then click **Add domain to list**.

![Manually add domains.jpg](https://files.readme.io/95b37db2064ddba8c787d2dd5ac5ab2aa7698605f5c6eb3b4a59dd6324dee355-25103405228689.jpg)

* Use only letters, numbers, hyphens, and periods.
* Domains must start and end with a letter or number and can be up to 253 characters.
* Don't add prefixes, such as https://.

See also allowlist [traits and limitations](/docs/set-up-your-domain-redirect-allowlist#traits-and-limitations).

The added domains will be displayed in the right-side list.

4. Click **Save list**.

Once saved, the allowlist will be enforced on clicks within about an hour.

</Accordion>

<Accordion title="Setup via CSV file">

**To set up via CSV file upload:**

1. From the top bar, open the account menu (email address dropdown) > **Security Center**  

![from account click security center Cropped.jpg](https://files.readme.io/4ee3279e382e97817a6b977f50bff7054868f03c22186ed2bd79d712e2316ad4-25381243839377.jpg)

2. In the **Redirect allowlist** section, click **Manage redirect allowlist**.  
![Manage redirect allowlist with arrow.jpg](https://files.readme.io/e9cd8c263eb618b86d3c10b1d9fc367390dfd1f9b6cc12afd7ac5f37411ba25c-25644439175313.jpg)  

The **Redirect allowlist** page opens.

3. Click the **CSV file** tab, then follow the **CSV file instructions** to create a file containing your domain list.  
![CSV file upload.jpg](https://files.readme.io/2be73080048545f79e102e6f48df0db956e6739f156153c172c4fef5a2ea339f-25381979219345.jpg)

4. Upload the CSV file to the upload field.

* Once the file is uploaded it will be parsed, and values will be validated.
* Valid values will be automatically added and displayed in the right-side list.
* Invalid values won’t be added. Information about invalid values will be displayed in the **Upload status** section so you can take the following action: review or fix the values and re-upload. See allowlist [traits and limitations](/docs/set-up-your-domain-redirect-allowlist#traits-and-limitations) for more details.

5. Click **Save list**.

Once saved, the redirect allowlist will be enforced on clicks within about an hour.

</Accordion>

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
| Applicability | * The allowlist affects **all links created via AppsFlyer**, either with [OneLink](/docs/onelink-guide), single-platform attribution links via [partner integration](/docs/set-up-an-integrated-partner#attribution-link-tab), or [direct attribution links](/docs/ctv-pc-and-console-platform-direct-attribution-links) for CTV, PC, and console platforms, no matter when they were created.<br />* Include in the allowlist the domains of any URL set as a value on the link redirection setup specified here, whether it's a custom website/landing page, the Google Play/App Store, or another app store website. The allowlist supports and protects redirections for the following:  <br />  * Link parameters:  <br />    * `af_r`<br />    * `af_web_dp`<br />    * `af_ios_url`<br />    * `af_android_url`<br />  * OneLink template redirection setup for iOS, Android, and Desktop.<br />  * `af_dp` with a web URL value, however, this is not a recommended value type. This parameter is intended to populate a [URI scheme](/docs/about-link-structure-and-parameters#af_dp) to open your app.<br />* **Link previews may show fallback content:** When AppsFlyer generates a social preview for a link, it validates the link’s redirect parameters against your redirect allowlist. If it isn’t, AppsFlyer won’t fetch a preview from that page and will instead show a fallback preview. |
| Domains | * The allowlist must include at least one domain.<br />* Only root domains or subdomains are allowed, not specific paths. Don't include `**https://**` or `**http://**` protocols in the value.<br />* When adding a root domain, it will apply to all subdomains within the root domain.  <br />  For example, if the root domain "website.com" is added, it will cover "abc.website.com" and "xyz.website.com" as well.<br />* Redirection is only supported for publicly accessible domains.<br />* Don't include AppsFlyer domains (e.g., onelink.me, app.appsflyer.com) or other domains that have their own redirection mechanism (e.g., bit.ly) to fortify the predictability of the redirection of your links.<br />* Up to 250 domains/subdomains can be added to the allowlist. You can view the number of domains already added by going to the redirect allowlist, where the number of domains is indicated. |
| Redirection | If you’re unsure whether a domain your link redirects to is allowed:<br /><br />Review the allowlist to make sure it’s included.<br /><br />Or<br /><br />Use the [Link Discovery](/docs/discover-your-campaign-link-parameters-and-behavior) tool. When a link is entered, an alert will appear in the **Parameters** column (under **Redirection**) if a domain isn’t in the allowlist. |