---
title: "Implementing and using 2FA login"
excerpt: "Two-factor authentication (2FA) is used to add an extra layer of security to the login process. Login credentials for account users are supplemented by Google or Microsoft Authenticator."
x-zendesk:
  id: 41585422141585
  url: https://support.appsflyer.com/hc/en-us/articles/41585422141585-Implementing-and-using-2FA-login
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: Ad network onboarding
  section_id: 6551058566033
  position: 0
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: []
  promoted: false
  comments_disabled: true
  created_at: '2025-12-04T09:21:41Z'
  edited_at: '2026-08-09T07:02:53Z'
---
## Intro

> 📘 **Note**
>
> Each person who accesses AppsFlyer must have their own user account. User credentials can’t be shared, and 2FA must be set up individually for every user. If you need to add users to the account, go to User management and create new users as needed. For details, see [User management.](/docs/user-management-for-agencies)

* 2FA is mandatory by AppsFlyer.
* 2FA must be set up using **Google or Microsoft Authenticator.**

> 📘 **Important!**
>
> After you set up 2FA, don’t delete your authenticator app. Doing so breaks the connection to AppsFlyer, and you won’t be able to log in.

<Accordion title="First-time setup">

#### **New account user**

1. Follow email instructions and create a password.
2. Log in to **AppsFlyer,** and you'll be redirected to the 2FA setup page.
3. Set up 2FA.
   * Download **Google or Microsoft Authenticator**.
   * Scan the QR code.
   * Enter the **Google or Microsoft Authenticator**-issued verification code.
   * Click **Verify**, and you'll be redirected to the **My apps** page.

#### **Existing account users**

1. Log in to **AppsFlyer** (username and password), and you'll be redirected to the 2FA setup page.
2. Set up 2FA.
   * Download **Google or Microsoft Authenticator**.
   * Scan the QR code.
   * Enter the **Google or Microsoft Authenticator**-issued verification code.
   * Click **Verify,** and you'll be redirected to the **My apps** page.

</Accordion>

<Accordion title="Ongoing use">

**Follow these steps for ongoing use.**

1. Log in to **AppsFlyer** (username and password), and you'll be redirected to the 2FA login page.
2. Open **Google or Microsoft Authenticator** on your phone to get the verification code.
3. Enter the code on the 2FA page.
4. Click **Verify,** and you'll be redirected to the **My apps** page.

</Accordion>

<Accordion title="Reset a user's 2FA">

<Embed title="Implementing and using 2FA login" typeOfEmbed="youtube" url="https://www.youtube-nocookie.com/embed/15sYaqz89ys" providerUrl="https://www.youtube-nocookie.com" />

To reset your 2FA, contact your Admin. The admin should follow these steps:

Note: If you are an account owner, you can reset your own 2FA in [the steps that follow](/docs/implementing-and-using-2fa-login-partners#for-an-account-owner-resetting-their-own-2fa).

#### **For an Admin resetting a user's 2FA**

1. In the menu bar, click the email address dropdown.
2. Select **User management**.
3. On the **Users** tab, click the menu options on the far right side of the user’s row.
4. Select **Reset 2FA** from the menu.

#### **For an Account owner resetting their own 2FA**

1. On the 2FA login page, click **Click here to start the reset process.**
2. An email will be sent with a code and a link to the new 2FA login page.
3. Copy the code from the email and click the link in the email.
4. Enter the code in the 2FA setup page.
5. Follow the steps for setting up your new 2FA [here](/docs/implementing-and-using-2fa-login-partners#existing-account-users).

</Accordion>

<Accordion title="Traits and limitations">

| Name | Description |
| --- | --- |
| AppsFlyer apps | With 2FA enabled, both the AppsFlyer apps, **My Device ID by AppsFlyer** and **AppsFlyer**, cannot be used. To register test devices, use the method [here](/docs/registering-test-devices). |

</Accordion>
