---
title: Implementing and using 2FA login
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2020-06-22T10:25:26Z'
  edited_at: '2026-05-25T07:53:34Z'
  id: 360010178037
  locale: en-us
  section: Account security
  section_id: 6551173202065
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360010178037-Implementing-and-using-2FA-login
---
**At a glance:** Use two-factor authentication (2FA) to add an extra layer of security to the login process. Login credentials for account users are supplemented by Google or Microsoft Authenticator or SMS verification.

## Highlights

* 2FA is an optional feature activated by an admin user.
* Options are **Google or Microsoft Authenticator** and **SMS verification.**
* Activating/deactivating applies to all account users.
* Account users at the time of activation will be permitted to log in and prompted to set up 2FA at their next login.

## ![admin.png](https://files.readme.io/d54680123b25ab7929285cebd778e0e74bd0d032df994b04d1bca106381c3dc6-360014518718.png) Admin: Managing 2FA

Only an admin user can activate, reset, or deactivate a user's 2FA settings.

<div id="activate" />

<Accordion title="Activate">

If an admin activates **Google or Microsoft Authenticator** and **SMS verification**, account users can choose which method they prefer to use.

> 📘 **Note**
>
> SMS verification depends on SMS success rates, which vary by mobile carrier and country. Therefore, we strongly recommend enabling both SMS verification and Google or Microsoft Authenticator to avoid being locked out due to failed SMS delivery.

**To activate 2FA:**

1. From the top bar, open the account menu (email address dropdown) > **Security center**.
2. In the **Enhanced login security** section, click **Configure login method** to access the **Login security** page.
3. In the **Two-factor authentication (2FA)** section, activate the toggle for **Google or Microsoft Authenticator** and/or **SMS verification.**

</Accordion>

<div id="reset" />

<Accordion title="Reset">

For accounts using 2FA, there may be occasions on which you need to reset a user’s 2FA. Note that after reset, **Google or Microsoft Authenticator** is the default 2FA login screen.

**To reset a user's 2FA:**

1. In the menu bar, click on the email address dropdown.
2. Select **User management**.
3. On the **Users** tab, click the menu options <Image alt="actions_icon.png" src="https://files.readme.io/081e3baaa997a31ec2d420cdd05aa03973798a9e11238f418a5dc12f43fed373-19910370240913.png" width="25px" /> on the far-right side of the user’s row.
4. Select **Reset 2FA** from the menu.

**Note:** An admin can reset any other user's 2FA (including <Anchor target="_blank" href="/marketers/docs/user-management#admin">account owners</Anchor>) other than their own. In the case of no other admin users, to reset the account owner's 2FA, contact the AppsFlyer CS team.

</Accordion>

<div id="deactivate" />

<Accordion title="Deactivate">

If 2FA is deactivated, account users will log in using only their username and password.

**To deactivate 2FA:**

1. From the top bar, open the account menu (email address dropdown) > **Security center.**
2. In the **Enhanced login security** section, click **Configure login method** to access the **Login security** page.
3. In the **Two-factor authentication (2FA)** section, deactivate the toggle for **Google or Microsoft Authenticator** and/or **SMS verification.**
4. Confirm deactivation.

</Accordion>

## Account users: Using Google or Microsoft Authenticator

**Google or Microsoft Authenticator** is the initial default screen; however, the last 2FA method used appears at the next login.

If you choose not to use **Google or Microsoft Authenticator**, then the setup and login screens have a link to the **SMS verification** 2FA screen.

<div id="firsttime-setup" />

<Accordion title="First-time setup">

Before using 2FA for the first time, every account user must download **Google or Microsoft Authenticator** and a **QR code** app. These apps are available via **Google Play** (Android) or the **App Store** (iOS).

**New account user**

1. Follow email instructions and create a password.
2. Log in to **AppsFlyer,** and you'll be redirected to the 2FA setup page.
3. Set up 2FA.
   * Download **Google or Microsoft Authenticator**.
   * Scan the QR code.
   * Enter the **Google or Microsoft Authenticator**-issued verification code.
   * Click **Verify**, and you'll be redirected to the **My apps** page.

**Existing account users**

1. Log in to **AppsFlyer** (username and password), and you'll be redirected to the 2FA setup page.
2. Set up 2FA.
   * Download **Google or Microsoft Authenticator**.
   * Scan the QR code.
   * Enter the **Google or Microsoft Authenticator**-issued verification code.
   * Click **Verify,** and you'll be redirected to the **My apps** page.

</Accordion>

<div id="ongoing-use" />

<Accordion title="Ongoing use">

**Follow these steps for ongoing use.**

1. Log in to **AppsFlyer** (username and password), and you'll be redirected to the 2FA login page.
2. Open **Google or Microsoft Authenticator** on your phone to get the verification code.
3. Enter the code on the 2FA page.
4. Click **Verify,** and you'll be redirected to the **My apps** page.

</Accordion>

## Account users: Using SMS verification

If you choose not to use **SMS verification**, then the setup and login screens have a link to **Google or Microsoft Authenticator** 2FA screen.

<div id="firsttime-sms-setup" />

<Accordion title="First-time SMS setup">

**Google or Microsoft Authenticator** is the default 2FA method. To reach the **SMS verification** method, click the **SMS verification** link.

**New account user**

1. Follow email instructions and create a password.
2. Log in to **AppsFlyer,** and you'll be redirected to the 2FA setup page.
3. Set up 2FA:
   * Enter your phone number (numbers only, no special characters) and click **Send code.**
   * Enter SMS verification code > click **Verify.**

**Existing account users**

1. Log in to **AppsFlyer** (username and password), and you'll be redirected to the 2FA setup page.
2. Set up 2FA:
   * Enter your phone number (numbers only, no special characters) and click **Send code.**
   * Enter SMS verification code > click **Verify.**

</Accordion>

<div id="ongoing-sms-use" />

<Accordion title="Ongoing SMS use">

**Follow these steps for ongoing use:**

1. Log in to **AppsFlyer** (username and password), and you'll be redirected to the 2FA login page.
2. The **SMS verification** page will appear if it was used at your last login. If not, click the link at the bottom of the **Google or Microsoft Authenticator** 2FA page.
3. Your phone number will automatically display. Click **Send code.**
4. Enter the verification code sent by SMS.
5. Click **Verify.**

</Accordion>

<div data-zendesk-anchors="h_01HEHRKE8PY64KWVSSFR6T4F1Z=highlights admin-managing-2fa=-admin-managing-2fa h_01HEHRKE8PZA3H9SXPRD1FZ50S=-admin-managing-2fa h_01HEHRKE8PV0ZADPXHNBBDMKAF=activate 01JCDTA1W486FEFRPT2VYJ2PVX=note h_01HEHRKE8P9N2W871ZEB1D3MYN=reset h_01HEHRKE8PEDWCNKMG1N4CFDMN=deactivate account-users-using-google-authenticator=account-users-using-google-or-microsoft-authenticator h_01HEHRKE8P1A2BARBDVMJPH1WY=account-users-using-google-or-microsoft-authenticator h_01HEHRKE8QQTX3Y9ZY1HZ6GBAG=firsttime-setup h_01HEHRKE8QHWHCMNB5M7S5YVYJ=ongoing-use h_01HEHRKE8QZ245ZYBZ4FF814KN=account-users-using-sms-verification h_01HEHRKE8Q30QHGZ5QYMV4MR27=firsttime-sms-setup h_01HEHRKE8Q0229YE5QP5EJFSD8=ongoing-sms-use" />
