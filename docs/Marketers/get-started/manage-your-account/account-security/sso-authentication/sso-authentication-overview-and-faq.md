---
title: "SSO authentication—Overview and FAQ"
excerpt: "Learn about single sign-on (SSO) authentication and the process of logging in to AppsFlyer via your identity provider (IdP) using SSO."
---
At a glance: Learn about single sign-on (SSO) authentication and the process of logging in to AppsFlyer via with your identity provider (IdP) using SSO. Find answers to FAQs about SSO login.

## What is SSO authentication?

SSO is an authentication method that allows users to access multiple independent apps, systems, or platforms by logging in once via your identity provider (for example, Okta, Azure AD, or OneLogin). Adding AppsFlyer to your IdP lets your users sign into AppsFlyer directly from your IdP by a single sign-on (SSO) process. This lets your users sign in automatically with more **secure authentication** using only one set of credentials.

## How does SSO authentication work?

The AppsFlyer platform supports SSO verification using the SAML2.0 protocol. By implementing AppsFlyer's authentication certificate into your SAML 2.0 IdP, your IdP generates a token with authenticated user data. The same process is done from your IdP to AppsFlyer—their token is implemented in AppsFlyer.

## The AppsFlyer (service provider) authentication certificate

AppsFlyer provides an encryption certificate to encrypt data and sign the SSO request. You can choose which certificate to use:

- **AppsFlyer-signed certificate:** An AppsFlyer certificate created from the [AppsFlyer metadata URL](https://hq1.appsflyer.com/auth/sso-metadata)
- **CA-signed certificate:** An AppsFlyer certificate **signed by Amazon**.

> 📘 Note
>
> AppsFlyer does not support negative serial numbers in the certificate.

## Troubleshooting and FAQ

<Accordion title="Can users log in using both SSO and 2FA methods?">

Only one security login method can be used at a time, either SSO or 2FA.

- **To activate the 2FA method when SSO is active:** First deactivate SSO, then activate 2FA
- **To activate the SSO method when 2FA is active:** First deactivate 2FA, then activate SSO

</Accordion>

<Accordion title="Why can't some users connect using SSO?">

Make sure all user emails are set up in both systems—in your IdP and in the AppsFlyer platform. If that isn't the reason, contact your CSM to find why and how to fix it. In the meantime, your CSM can temporarily disable the **Force SSO login** option so that users can log in using their email and password.

</Accordion>

<Accordion title="Do I need a test environment to test setup before setting the configuration?">

A test environment isn’t required. Follow the steps [in Step 3](https://support.appsflyer.com/hc/articles/27127902898449#step-3-test-the-sso-configuration) to test the SSO login, either from the IdP or the service provider's side (AppsFlyer).

</Accordion>

<Accordion title="What should I do before the AppsFlyer certificate expires?">

AppsFlyer will alert you via the platform when your AppsFlyer SSO certificate is about to expire. Follow these steps to implement the new AppsFlyer certificate:

1. [Create a new certificate file with the updated encryption key](/docs/sso-authentication-overview-and-faq#how-to-create-the-appsflyer-certificate-file).
2. Go to your IdP and implement the new AppsFlyer certificate.
3. After implementation, return to the **Single sign-on (SSO)** section, click **Confirm certificate implementation**, and confirm you've updated the latest AppsFlyer certificate.

</Accordion>

<Accordion title="Force SSO login is disabled, how can I enable it?">

Once the **Force SSO login** option is selected and the configuration is saved, this option becomes disabled. To revert and have **Force SSO login** enabled, you'll need to re-configure [step 2](https://support.appsflyer.com/hc/articles/360015017198#step-2-complete-the-configuration-at-appsflyer) of the SSO process from the beginning.

> 📘 Note
>
> Keeping **Force SSO login** selected is the recommended method for enforcing a more secure login. It means users trying to log in are authenticated by the IdP and can't log in with their username and password.

</Accordion>

<Accordion title="Is it required to use the AppsFlyer certificate in my IdP?">

Implementing the AppsFlyer certificate in your IdP is **strongly recommended** but isn't mandatory. Some IdPs, such as Google Workspace and Microsoft Entra ID, don't require by default a service provider certificate.

</Accordion>

<Accordion title="What happens when I deactivate SSO and how do I do it?">

When deactivating SSO authentication, users will be able to log in using other methods, such as their AppsFlyer usernames and passwords and the [2FA](https://support.appsflyer.com/hc/articles/360010178037) method.

1. From the top bar, open the account menu (admin email address dropdown) > **Security center**.
2. Under **Enhanced login security**, select **Configure login method**.
3. From the **Single sign-on (SSO)** section, turn off the **Single sign-on** toggle.

</Accordion>

<Accordion title="Can I have negative serial numbers in the certificate?">

No. AppsFlyer does not support negative serial numbers in the certificate.

</Accordion>