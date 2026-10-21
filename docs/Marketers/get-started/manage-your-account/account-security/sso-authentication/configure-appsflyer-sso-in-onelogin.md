---
title: Configure AppsFlyer SSO in OneLogin
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2023-05-04T07:41:06Z'
  edited_at: '2024-07-09T11:52:33Z'
  id: 15044997313041
  locale: en-us
  section: SSO authentication
  section_id: 20162151531793
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/15044997313041-Configure-AppsFlyer-SSO-in-OneLogin
---
**At a glance:** Configure the SSO process using OneLogin as an identity provider (IdP).

The first stage in configuring the AppsFlyer SSO process is done on the OneLogin platform. Follow the steps below:

<div id="create-the-appsflyer-app-in-oonelogin" />

<Accordion title="Create the AppsFlyer app in OneLogin">

**Prerequisite:** A OneLogin account with administrative privileges.

1. In the OneLogin admin console, go to **Applications** > **<Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/admin2/apps">Applications</Anchor>**.
2. From the top right, click **Add App**.
3. Search for and select **SAML Custom Connector (Advanced)**.  

   <Image alt="onelogin_saml_app.png" src="https://files.readme.io/c1e5ec122e21f05e860486ad280ba9e692b3d05b05105d9c1ca700b8921ee6ab-15045173609745.png" width="601px" />
4. In the **Display Name** field, enter the name to show in the OneLogin plugin list of apps.
5. [Optional] **App logo**: Add a logo to appear near the app name.
6. [Optional] Add a description.
7. Click **Save**. A success message appears at the top.
8. Go to the **Configuration** tab on the side menu.
9. Define the integration according to the following fields:
   * **Audience (EntityID):** Enter this link: <Anchor target="_blank" href="https://hq1.appsflyer.com/">https://hq1.appsflyer.com</Anchor>
   * **ACS (Consumer) URL Validation**, **ACS (Consumer) URL:** Enter the endpoint to which OneLogin sends the user verification. Use the link according to the <Anchor target="_blank" href="/marketers/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration">callback URL configuration described here</Anchor>
   * **Recipient:** Enter the same URL as entered in the **ACS (Consumer) URL** field.
   * **Login URL:** Enter the AppsFlyer <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">login URL</Anchor>.
   * **SAML not valid before**, **SAML not valid on or after:** Specify the time period (in minutes) the assertion is valid for.
   * **SAML initiator:** <Anchor target="_blank" href="/marketers/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration">Select from where authentication begins</Anchor>:
     * For authentication starting from the IdP, select **OneLogin**
     * For authentication starting from AppsFlyer, select **Service Provider**
   * **SAML nameID format:** Select Email.
   * **SAML issuer type:** Select Specific.
   * **SAML signature element:** Select **Both**.
   * **Encrypt assertion**: Select this checkbox.
   * **SAML encryption method:** Select **AES-256-CBC**.
10. Click **Save**.
11. **Assertion encryption:** 
    1. Open <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">the SSO metadata URL</Anchor> and copy the encryption certificate value.
    2. Go back to the **Configuration** tab and paste it into the **SAML encryption** text box.
    3. Click **Save**.

</Accordion>

<div id="get-idp-sso-metadata" />

<Accordion title="Get IdP SSO metadata">

1. From your selected application (**Applications** > **<Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/admin2/apps">Applications</Anchor>**), select **SSO** from the side menu.
2. Copy the **Issuer URL** and paste it into a new tab to download the SSO metadata.

</Accordion>

<div id="create-onelogin-users" />

<Accordion title="Create OneLogin users">

1. From the top menu, go to **Users** > <Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/users">**Users**</Anchor>.
2. Click **New User** from the top right.
3. Enter the user's **First name**, **Last name**, and **Email**.
4. From the top right, click **Save User** then **More Actions,** and select **Change Password** to set the user a password.
5. Set a password for the user and click **Update**.

</Accordion>

<div id="assign-users-to-your-app" />

<Accordion title="Assign users to your app">

1. Go to the **Application** tab in the side menu of the selected user.
2. Click the + sign near **Applications**.
3. Select the AppsFlyer app you've created and click **Continue**.  

   <Image alt="onelogin_assign_app.png" src="https://files.readme.io/a1769673f3f167f728a00fb1cccb951bd246798fd7327c51b021f73987bc8fb2-15552909316241.png" width="326px" />
4. From the top menu, go to **Applications** > **<Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/admin2/apps">Applications</Anchor>**.
5. Select the application you've just created.
6. Click **Save**.

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="Complete the process in AppsFlyer">

Now that you've configured the IdP part, go back to AppsFlyer to <Anchor target="_blank" href="/marketers/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">complete the configuration</Anchor>. You can then <Anchor target="_blank" href="/marketers/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process">test</Anchor> to see that it works.

</Accordion>

<div data-zendesk-anchors="h_01HF690GVE4FXXTMC5QWSJTY3C=create-the-appsflyer-app-in-oonelogin h_01HF690GVECMCVQAJFZ509MD50=get-idp-sso-metadata h_01HF690GVEKMV3TZ8MAD4HM635=create-onelogin-users h_01HF690GVEVEQ4GNJGXHKF5VT1=assign-users-to-your-app h_01HF690GVEWYEGR2Z9F22FQHGE=complete-the-process-in-appsflyer" />
