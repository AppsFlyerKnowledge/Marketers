---
title: "Configure AppsFlyer SSO in Okta"
excerpt: "Configure the SSO process using Okta as an identity provider (IdP)."
x-zendesk:
  id: 12934808889745
  url: https://support.appsflyer.com/hc/en-us/articles/12934808889745-Configure-AppsFlyer-SSO-in-Okta
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: SSO authentication
  section_id: 20162151531793
  position: 3
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-negri, Marketers, Platform essentials, Agencies, Ad Networks]
  labels: [Agencies, Ad Networks, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2023-02-12T13:10:51Z'
  edited_at: '2024-10-09T04:55:25Z'
---
The first step in configuring the AppsFlyer SSO process is done on the Okta platform. Follow the steps below:

### Create the AppsFlyer app in Okta

> 📘 Prerequisite
>
> An Okta account with administrative privileges.

01. In the Admin Console, go to **Applications** > **Applications**.

    ![Okta_side_menu___applications.png](https://files.readme.io/c218e729a7c00158e3804e7c7d884ec5b098e56628037ced54ad3c311470e038-13572360791825.png)
02. Click **Create App Integration**.
03. In the **Create a new app integration** dialog box, select **SAML 2.0**, and click **Next**.
04. Under **(1) General Settings**, in the **App name** field, enter the name that you want to show in the Okta plugin list of apps.

    ![Okta_app_name_and_icon__1_.png](https://files.readme.io/6998e7737b0aa5c4d70ad97ab41e17e471ddaf060e78c44fa2de41be1df17574-13572380565521.png)
05. [Optional] **App logo**: Add a logo to appear near the app name.
06. Click **Next**.
07. Under **(2) Configure SAML Integration**, define the integration according to the following fields: ![okta-create-saml-integration.png](https://files.readme.io/6c276dd54afd30e828b989fc6796de5eca46282ade015e7a34e0bd1cc95d7fb8-16870970396177.png)
    - **Single sign-on URL:** Enter the endpoint to which Okta sends the user verification. Use the link according to the [callback URL configuration described here](/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration)
    - **Audience URI (SP Entity ID):** Enter this link: [https://hq1.appsflyer.com](https://hq1.appsflyer.com/)
    - **Name ID format:** Select **EmailAddress** as the format for identifying the user
    - **Application username:** Select **Okta username**

      > 📘 Note
      >
      > The email of the Okta user must be the same as the user’s AppsFlyer account email
08. Click **Show Advanced Settings** and define the integration according to each of the fields shown in the image below:

    ![Okta_advanecd_settings__1_.png](https://files.readme.io/9a3461f700cc50a54237578a304206ed7693e30cdd516398089954321cd44af4-13572576788241.png)
    - **Assertion Encryption:** Select either **Encrypted** or **Unencrypted**.

      > 📘 Note
      >
      > As assertions are controlled by your IdP, it's recommended to select **Encrypted**.
    - **Encryption certificate:** Upload the [AppsFlyer encryption certificate](/docs/set-up-sso-authentication-with-your-identity-provider-idp#obtaining-the-appsflyer-certificate-from-the-metadata-url). This certificate is signed by AppsFlyer and is used to both encrypt and sign the request.
    - [Optional] **Signature certificate:** Upload the [AppsFlyer signing certificate](/docs/set-up-sso-authentication-with-your-identity-provider-idp#the-authentication-certificate).
09. Scroll to the end of the page, and click **Next**.
10. Select **I’m an Okta customer adding an internal app**, and click **Finish**.

### Create Okta users

Now that the Okta SAML application has been created, let’s add users.

1. From the Admin console, select **Directory** > **People**.

![Okta___directory___people.png](https://files.readme.io/d9c5da8787fdb81bf97bc0753b2f7794cdc59060e5026348428545064d138d18-13572579297169.png)

2. Click **Add Person**.

![Okta___People___Add_person.png](https://files.readme.io/6bb8b854cf000259970d63b9eacb28bf6d4079d648939814aaa0e456a96c9bbe-13572600647697.png)

3. In the **Add Person** dialog box:

![Okta_Add_person__1_.png](https://files.readme.io/d6d7e198fab965872b5a01302a00bdbd0bfb5d561af372fc4390c9882a22a42c-13572617052689.png)
   - For **User type**, select **User**.
   - Enter all required fields: **First name**, **Last name**, **Username** (must be an email), and **Primary email**.
   - For **Password**, you can choose to have it set by the user or by the admin.
4. To continue adding users, click **Save and Add Another**, then repeat steps 1-4. When done adding all users, click **Save**.

### Assign users to your app

1. From the Admin console, go back to **Applications** > **Applications**.
2. Under **Browse App Catalog**, select the application you've just created.

![Okta_side_menu___applications.png](https://files.readme.io/c218e729a7c00158e3804e7c7d884ec5b098e56628037ced54ad3c311470e038-13572360791825.png)
3. From your selected application, under the **Assignments** tab, click **Assign** > **Assign to People**.

![Okta_sso_assign_to_people.png](https://files.readme.io/50930693a4a58ad8162b2ac81e476081c9b0288da4dab5b92bb41fece4aff586-14942267242769.png)
4. Find the user to be assigned to your application, and click **Assign**.
5. Repeat this step for all users.
6. Click **Done** when finished adding all users. The new users now appear under **People**.

### Get IdP SSO metadata

1. From the Admin console, go back to **Applications** > **Applications**.
2. Under **Browse App Catalog**, select your application.
3. Click the **Sign On** tab.
4. From the **SAML Signing Certificates** section, click **Actions** > **View IdP metadata** of the active certificate. ![okta_sso_view_idp_metadata.png](https://files.readme.io/a6d9f6753ead962713851bcc367abba6fad226d6e0a5f908055e44b1d3e1b2be-14942369009809.png)
5. Copy the URL from the tab that opened. You’ll use this URL in the next step on the AppsFlyer platform.

### Complete the process in AppsFlyer

Now that you've configured the IdP part, go back to AppsFlyer to [complete the configuration](/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer). You can then [test](/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process) to see that it works.

<Cards>
  <Card title="Okta SSO documentation" href="https://developer.okta.com/docs/guides/build-sso-integration/openidconnect/main/" icon="fa-solid fa-user-gear">
    View Okta's developer documentation for building SSO integrations.
  </Card>
</Cards>