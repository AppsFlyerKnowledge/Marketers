---
title: "Configure AppsFlyer SSO in OneLogin"
excerpt: "Configure the SSO process using OneLogin as an identity provider (IdP)."
table_of_contents: false
x-zendesk:
  id: 15044997313041
  url: https://support.appsflyer.com/hc/en-us/articles/15044997313041-Configure-AppsFlyer-SSO-in-OneLogin
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: SSO authentication
  section_id: 20162151531793
  position: 4
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-negri, Marketers, Platform essentials, Agencies, Ad Networks]
  labels: [Agencies, Ad Networks, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2023-05-04T07:41:06Z'
  edited_at: '2024-07-09T11:52:33Z'
---
The first stage in configuring the AppsFlyer SSO process is done on the OneLogin platform. Follow the steps below:

<div id="create-the-appsflyer-app-in-oonelogin" />

<Accordion title="Create the AppsFlyer app in OneLogin">

**Prerequisite:** A OneLogin account with administrative privileges.

1. In the OneLogin admin console, go to **Applications** > **[Applications](https://appsflyer-dev.onelogin.com/admin2/apps)**.
2. From the top right, click **Add App**.
3. Search for and select **SAML Custom Connector (Advanced)**.  

   ![onelogin_saml_app.png](https://files.readme.io/c1e5ec122e21f05e860486ad280ba9e692b3d05b05105d9c1ca700b8921ee6ab-15045173609745.png)
4. In the **Display Name** field, enter the name to show in the OneLogin plugin list of apps.
5. [Optional] **App logo**: Add a logo to appear near the app name.
6. [Optional] Add a description.
7. Click **Save**. A success message appears at the top.
8. Go to the **Configuration** tab on the side menu.
9. Define the integration according to the following fields:
   * **Audience (EntityID):** Enter this link: [https://hq1.appsflyer.com](https://hq1.appsflyer.com/)
   * **ACS (Consumer) URL Validation**, **ACS (Consumer) URL:** Enter the endpoint to which OneLogin sends the user verification. Use the link according to the [callback URL configuration described here](/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration)
   * **Recipient:** Enter the same URL as entered in the **ACS (Consumer) URL** field.
   * **Login URL:** Enter the AppsFlyer [login URL](https://hq1.appsflyer.com/auth/login).
   * **SAML not valid before**, **SAML not valid on or after:** Specify the time period (in minutes) the assertion is valid for.
   * **SAML initiator:** [Select from where authentication begins](/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration):
     * For authentication starting from the IdP, select **OneLogin**
     * For authentication starting from AppsFlyer, select **Service Provider**
   * **SAML nameID format:** Select Email.
   * **SAML issuer type:** Select Specific.
   * **SAML signature element:** Select **Both**.
   * **Encrypt assertion**: Select this checkbox.
   * **SAML encryption method:** Select **AES-256-CBC**.
10. Click **Save**.
11. **Assertion encryption:** 
    1. Open [the SSO metadata URL](https://hq1.appsflyer.com/auth/sso-metadata) and copy the encryption certificate value.
    2. Go back to the **Configuration** tab and paste it into the **SAML encryption** text box.
    3. Click **Save**.

</Accordion>

<div id="get-idp-sso-metadata" />

<Accordion title="Get IdP SSO metadata">

1. From your selected application (**Applications** > **[Applications](https://appsflyer-dev.onelogin.com/admin2/apps)**), select **SSO** from the side menu.
2. Copy the **Issuer URL** and paste it into a new tab to download the SSO metadata.

</Accordion>

<div id="create-onelogin-users" />

<Accordion title="Create OneLogin users">

1. From the top menu, go to **Users** > [**Users**](https://appsflyer-dev.onelogin.com/users).
2. Click **New User** from the top right.
3. Enter the user's **First name**, **Last name**, and **Email**.
4. From the top right, click **Save User** then **More Actions,** and select **Change Password** to set the user a password.
5. Set a password for the user and click **Update**.

</Accordion>

<div id="assign-users-to-your-app" />

<Accordion title="Assign users to your app">

1. Go to the **Application** tab in the side menu of the selected user.
2. Click the **+** sign near **Applications**.
3. Select the AppsFlyer app you've created and click **Continue**.  

   ![onelogin_assign_app.png](https://files.readme.io/a1769673f3f167f728a00fb1cccb951bd246798fd7327c51b021f73987bc8fb2-15552909316241.png)
4. From the top menu, go to **Applications** > **[Applications](https://appsflyer-dev.onelogin.com/admin2/apps)**.
5. Select the application you've just created.
6. Click **Save**.

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="Complete the process in AppsFlyer">

Now that you've configured the IdP part, go back to AppsFlyer to [complete the configuration](/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer). You can then [test](/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process) to see that it works.

</Accordion>

<div data-zendesk-anchors="h_01HF690GVE4FXXTMC5QWSJTY3C=create-the-appsflyer-app-in-oonelogin h_01HF690GVECMCVQAJFZ509MD50=get-idp-sso-metadata h_01HF690GVEKMV3TZ8MAD4HM635=create-onelogin-users h_01HF690GVEVEQ4GNJGXHKF5VT1=assign-users-to-your-app h_01HF690GVEWYEGR2Z9F22FQHGE=complete-the-process-in-appsflyer" />
