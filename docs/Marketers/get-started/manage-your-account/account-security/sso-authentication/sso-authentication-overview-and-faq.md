---
title: SSO authentication—Overview and FAQ
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
  created_at: '2024-08-11T07:54:46Z'
  edited_at: '2025-01-27T00:01:02Z'
  id: 27434547337617
  locale: en-us
  section: SSO authentication
  section_id: 20162151531793
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/27434547337617-SSO-authentication-Overview-and-FAQ
---
> **At a glance:** Learn about single sign-on (SSO) authentication and the process of logging in to AppsFlyer via with your identity provider (IdP) using SSO. Find answers to FAQs about SSO login.

## What is SSO authentication?

SSO is an authentication method that allows users to access multiple independent apps, systems, or platforms by logging in once via your identity provider (for example, Okta, Azure AD, or OneLogin). Adding AppsFlyer to your IdP lets your users sign into AppsFlyer directly from your IdP by a single sign-on (SSO) process. This lets your users sign in automatically with more **secure authentication** using only one set of credentials.

## How does SSO authentication work?

The AppsFlyer platform supports SSO verification using the SAML2.0 protocol. By implementing AppsFlyer's authentication certificate into your SAML 2.0 IdP, your IdP generates a token with authenticated user data. The same process is done from your IdP to AppsFlyer—their token is implemented in AppsFlyer.

## The AppsFlyer (service provider) authentication certificate

AppsFlyer provides an encryption certificate to encrypt data and sign the SSO request. You can choose which certificate to use:

* **AppsFlyer-signed certificate:** An AppsFlyer certificate created from the <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">AppsFlyer metadata URL</Anchor>
* **CA-signed certificate:** An AppsFlyer certificate **signed by Amazon**.

> 📘 **Note**
>
> AppsFlyer does not support negative serial numbers in the certificate.

## Troubleshooting and FAQ

<div id="can-users-log-in-using-both-sso-and-2fa-methods" />

<Accordion title="Can users log in using both SSO and 2FA methods?">

Only one security login method can be used at a time, either SSO or 2FA.

* **To activate the 2FA method when SSO is active:** First deactivate SSO, then activate 2FA
* **To activate the SSO method when 2FA is active:** First deactivate 2FA, then activate SSO

</Accordion>

<div id="why-cant-some-users-connect-using-sso" />

<Accordion title="Why can't some users connect using SSO?">

Make sure all user emails are set up in both systems—in your IdP and in the AppsFlyer platform. If that isn't the reason, contact your CSM to find why and how to fix it. In the meantime, your CSM can temporarily disable the **Force SSO login** option so that users can log in using their email and password.

</Accordion>

<div id="do-i-need-a-test-environment-to-test-setup-before-pushing-to-production" />

<Accordion title="Do I need a test environment to test setup before setting the configuration?">

A test environment isn’t required. Follow the steps in Step 3 to test the SSO login, either from the IdP or the service provider's side (AppsFlyer).

</Accordion>

<div id="what-should-i-do-before-the-appsflyer-certificate-expires" />

<Accordion title="What should I do before the AppsFlyer certificate expires?">

AppsFlyer will alert you via the platform when your AppsFlyer SSO certificate is about to expire. Follow these steps to implement the new AppsFlyer certificate:

1. [Create a new certificate file with the updated encryption key](#how-to-create-the-appsflyer-certificate-file).
2. Go to your IdP and implement the new AppsFlyer certificate.
3. After implementation, return to the **Single sign-on (SSO)** section, click **Confirm certificate implementation**, and confirm you've updated the latest AppsFlyer certificate.

</Accordion>

<div id="how-can-i-unselect-the-force-sso-login-option" />

<Accordion title="Force SSO login is disabled, how can I enable it?">

Once the **Force SSO login** option is selected and the configuration is saved, this option becomes disabled. To revert and have **Force SSO login** enabled, you'll need to re-configure <Anchor target="_blank" href="/marketers/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">step 2</Anchor> of the SSO process from the beginning.

> 📘 **Note**
>
> Keeping **Force SSO login** selected is the recommended method for enforcing a more secure login. It means users trying to log in are authenticated by the IdP and can't log in with their username and password.

</Accordion>

<div id="is-it-required-to-use-the-appsflyer-certificate-in-my-idp" />

<Accordion title="Is it required to use the AppsFlyer certificate in my IdP?">

Implementing the AppsFlyer certificate in your IdP is **strongly recommended** but isn't mandatory. Some IdPs, such as Google Workspace and Microsoft Entra ID, don't require by default a service provider certificate.

</Accordion>

<div id="what-happens-when-i-deactivate-sso-and-how-do-i-do-it" />

<Accordion title="What happens when I deactivate SSO and how do I do it?">

When deactivating SSO authentication, users will be able to log in using other methods, such as their AppsFlyer usernames and passwords and the <Anchor target="_blank" href="/marketers/docs/implementing-and-using-2fa-login">2FA</Anchor> method.

1. From the top bar, open the account menu (admin email address dropdown) > **Security center**.
2. Under **Enhanced login security**, select **Configure login method**.
3. From the **Single sign-on (SSO)** section, turn off the **Single sign-on** toggle.

</Accordion>

<div id="can-i-have-negative-serial-numbers-in-the-certificate" />

<Accordion title="Can I have negative serial numbers in the certificate?">

No. AppsFlyer does not support negative serial numbers in the certificate.

</Accordion>

<div data-zendesk-anchors="what-is-sso=what-is-sso-authentication h_01J5QR4DE5EBSVWHXXENZTRPWQ=what-is-sso-authentication h_01HCHG901WVRX1MKNB0KF02PSJ=how-does-sso-authentication-work the-authentication-certificate=the-appsflyer-service-provider-authentication-certificate h_01HCHG901WG05TP2NJBJRDRWPN=the-appsflyer-service-provider-authentication-certificate h_01JJH8DC3AHNC6GST0S41X8MFV=note faq=troubleshooting-and-faq h_01HCHG901XSAQ7HSGM0ZVT7B70=troubleshooting-and-faq h_01HCHG901XJ77NQFVX01YZPGT2=can-users-log-in-using-both-sso-and-2fa-methods h_01HCHG901XH0ED40MK2YM1NGRP=why-cant-some-users-connect-using-sso h_01HCHG901X942E0WCBC00KRFSE=do-i-need-a-test-environment-to-test-setup-before-pushing-to-production h_01HCHG901XNNT8GA3TSP5XJC3B=what-should-i-do-before-the-appsflyer-certificate-expires h_01HCHG901XSKPTTRECJPNA09XR=how-can-i-unselect-the-force-sso-login-option h_01HCHG901XPKMP7HSJ04PY9KHW=note-1 h_01HYDBV18S924FNRCBSPR56CTR=is-it-required-to-use-the-appsflyer-certificate-in-my-idp h_01J5QRR54JNC5YNZHQ463KS7BS=what-happens-when-i-deactivate-sso-and-how-do-i-do-it h_01JJH8F3VFTQA1AANNNS85YBF8=can-i-have-negative-serial-numbers-in-the-certificate" />
