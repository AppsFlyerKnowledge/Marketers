---
title: "Set up SSO authentication with your identity provider (IdP)"
excerpt: "By integrating AppsFlyer with your identity provider (IdP), AppsFlyer account users can log in to AppsFlyer using single sign-on (SSO). Learn how to set up SSO authentication, activate SSO, and optionally add exception users who can log in with an assigned alternative login method."
x-zendesk:
  id: 360015017198
  url: https://support.appsflyer.com/hc/en-us/articles/360015017198-Set-up-SSO-authentication-with-your-identity-provider-IdP
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: SSO authentication
  section_id: 20162151531793
  position: 0
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-negri, Marketers, Platform essentials, Agencies, Ad Networks]
  labels: [Agencies, Ad Networks, login security, SSO, SSO verification, SSO certificate, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2020-11-02T10:50:55Z'
  edited_at: '2026-05-31T05:00:01Z'
---
## Considerations

- Users must be set up in both AppsFlyer and the identity provider (IdP) with the same email address.
- SSO configuration settings can only be managed and deleted by an admin with **Login security** permission set to **Manage**.
- SSO is enforced for the account by default.
- Admins can add exception users who can log in with SSO or an assigned alternative login method.
- Supported alternative login methods for exception users are:
  - Username & password
  - Authenticator app (2FA)
- SMS isn’t supported as an alternative login method for exception users.
- When no exception users are added, all users by default are enforced using SSO after activation.

> 🚧 Recommended practice
>
> We recommend adding at least one trusted admin as an exception user before activating SSO. This helps prevent account lockout if the SSO configuration is incorrect

## Access the SSO configuration page

1. From the top bar, open the account menu (admin email address dropdown) > **Security center**.
2. Under **Enhanced login security**, select **Configure login method**.
3. From the **Login security** page, click **Configure SSO**.

## Set up SSO

The SSO configuration is done on both the IdP platform and in AppsFlyer, as detailed in the steps below. The configuration status can either be **Active** when SSO is set up, or **Not configured** when no configuration was set or the configuration setup has been removed.

> 📘 Note
>
> This guide includes detailed procedures for the IdPs below. A general setup overview is described for all other IdPs.
> - JumpCloud
> - Okta
> - OneLogin
> - Ping Identity

### Step 1: Set up the IdP platform

See the detailed procedures for configuring SSO authentication in the following IdPs:

- [JumpCloud](/docs/configure-appsflyer-sso-in-jumpcloud)
- [Okta](/docs/configure-appsflyer-sso-in-okta)
- [OneLogin](/docs/configure-appsflyer-sso-in-onelogin)
- [Ping Identity](/docs/configure-appsflyer-sso-in-ping-identity)

#### Setup overview for other IdP platforms

The process for configuring other IdP platforms is outlined below:

- Create an AppsFlyer app on the IdP platform using the SAML 2.0 protocol, and integrate the [AppsFlyer authentication certificate](/docs/set-up-sso-authentication-with-your-identity-provider-idp#the-authentication-certificate) within the IdP platform.
- Assign users to the newly created AppsFlyer app.
- Retrieve the IdP certificate or metadata to be used in AppsFlyer (as mentioned in [Step 2: Set up AppsFlyer --> 5. Provide IdP metadata](/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-5-provide-idp-metadata)).

> 🚧 Important!
>
> When assigning users to the IdP, make sure you're using the same user email as in AppsFlyer so that each user on both platforms has the same email.
> 
> The [AppsFlyer metadata](https://hq1.appsflyer.com/auth/sso-metadata) contains:
> - Encryption and signing certificates
> - Entity ID
> - Callback URL

### Step 2: Set up AppsFlyer

The following flow takes you through the steps to set up SSO authentication in AppsFlyer after you've configured it on the IdP platform.

See how to [access the SSO configuration setup page](/docs/set-up-sso-authentication-with-your-identity-provider-idp#access-the-sso-configuration-page).

### 1\. Select authentication starting point

1. Select from where users enter AppsFlyer. This also defines the authentication process.
   - [Identity provider (IdP)](/docs/set-up-sso-authentication-with-your-identity-provider-idp#identity-provider-idp)
   - [Service provider (AppsFlyer)](/docs/set-up-sso-authentication-with-your-identity-provider-idp#service-provider-appsflyer)
2. Click **Next**.

#### Identity provider (IdP)

Users log in through the IdP authentication plugin or webpage and are then directed to AppsFlyer after authentication.

> 📘 Note
>
> By selecting this option, users can log in through both the IdP and the service provider (AppsFlyer).

#### Service provider (AppsFlyer)

Users enter AppsFlyer via the [AppsFlyer SSO login page](https://hq1.appsflyer.com/auth/sso-callback) by clicking **Login with SSO** and entering their email address. They are then directed to the IdP for authentication and redirected to the AppsFlyer homepage.

![AppsFlyer_login_page.png](https://files.readme.io/fb80e44cf0cad29349ec85f75f65de73041b1787b278ae9d96449783580faeaa-17233244722577.png)

> 📘 Note
>
> By selecting this option, users can log in only via the service provider (AppsFlyer) and not directly from the IdP.

### 2\. Select certificate type

AppsFlyer offers two types of public encryption key certificates to encrypt data and sign the SSO request:

- **AppsFlyer-signed certificate:** An AppsFlyer certificate created from the [AppsFlyer metadata URL](https://hq1.appsflyer.com/auth/sso-metadata).
- **CA-signed certificate:** An AppsFlyer certificate **signed by Amazon**.

**To perform this step:**

- Select the certificate type and click **Next**.

> 📘 Note
>
> The certificate becomes activated only after both sides complete the mutual certificate implementation process: AppsFlyer incorporates the IdP SAML configuration, and the IdP integrates the latest AppsFlyer SSO metadata. This is done in the following steps below.

### 3\. Obtain service provider (AppsFlyer) metadata

1. Copy the latest AppsFlyer SSO metadata and implement it into your IdP SAML configuration.
   - If you've selected the **AppsFlyer-signed certificate:** Copy any of the fields below.
     - **Metadata URL:** For IdPs that support full metadata URLs, copy the URL and implement it in your IdP.
     - **Metadata components:** For IdPs that don't support full metadata URLs, copy each of the components and implement them in the corresponding section in your IdP: **Entity ID**, **Encryption key** (downloadable), and **Location URL**.
     - **XML file:** You have the option to download the AppsFlyer SSO metadata as an XML file.
   - If you've selected the **CA-signed certificate:** Copy the **Metadata components**.
2. Click **Next**.

### 4\. Provide IdP metadata

Provide the IdP SSO metadata using the options below, then validate the metadata format. **Note**: The IdP certificate data must be in a single-line format without meta characters.

1. Select the preferred method for providing your IdP metadata:
   - **URL:** Enter the IdP metadata URL.
   - **XML file:** Upload the IdP metadata XML file.
2. Click **Validate**. A confirmation message appears at the top of the page indicating the validation status.
3. Click **Activate**. A confirmation message appears at the top of the page indicating the SSO authentication activation status.

### 5\. Add exception users

Exception users are users who aren’t required to log in through SSO. SSO remains enforced for the account, and only users explicitly added as exception users can log in with an assigned alternative login method.

Adding exception users is optional. If you don’t add exception users, all users must log in through SSO after activation.

> 📘 Note
>
> Add at least one trusted admin as an exception user before activating SSO. If the SSO configuration is incorrect, this user can log in with their assigned alternative login method and update the configuration.

To add exception users:

1. Click **Add exception users**.
2. In the **Add exception users** dialog, search for a user by name or email.
3. Select the user you want to add.
4. From the **Alternative login method** drop-down list, select one of the following:
   - **Username & password**
   - **Authenticator app**
5. Repeat steps 2-4 for each user you want to add.
6. Click **Add exception users**.

### **Add login methods for multiple users**

To add the same alternative login method for multiple exception users:

1. Select the checkboxes for the users you want to update.
2. Click **Set login method for selected users**.
3. Select one of the following:
   - **Apply username and password for all selected users**
   - **Apply authenticator app for all selected users**

### **Delete an exception user**

To delete a user from the exception users list:

- Click the **Delete** icon in the user row.

The user is deleted from the list immediately.

### 6\. Activate SSO

> 📘 Note
>
> Before activating SSO, we recommend adding at least one trusted admin as an exception user. This helps prevent account lockout if the SSO configuration is incorrect.

To activate SSO:

1. Click **Activate SSO**.
2. In the **Activate SSO?** dialog, review your SSO settings.
3. Click **Activate SSO**.

Incorrect configuration may lock users out of AppsFlyer. Review your configuration before activating SSO.

If no exception users were added, the confirmation dialog shows a message that everyone will be required to log in through SSO after activation.

### **Activation results**

| Result | Description |
| --- | --- |
| **SSO activation succeeds and exception users are added** | SSO is active, and exception users are configured. |
| **SSO activation succeeds, but some exception users aren’t added** | SSO stays active. Add or update exception users from **Edit SSO**. |
| **SSO activation fails** | SSO isn’t activated, and the configuration status returns to **Not configured**. |

## **Edit SSO**

After SSO is active, you can edit the SSO configuration and manage exception users.

To edit the SSO configuration:

1. From the **SAML Single sign-on (SSO)** section, click the **Edit** icon.
2. Open the section you want to update.
3. Make the required changes.
4. Click **Save**.
5. In the **Save changes?** dialog, review the changes.
6. Click **Save changes**.

When you update the certificate type or authentication starting point, the AppsFlyer metadata changes. Copy the latest service provider (AppsFlyer) SSO metadata and add it to your IdP SAML configuration immediately after saving your changes.

### **Edit exception users**

To edit exception users:

1. From the SSO edit page, open the **Exception users** section.
2. Click **Edit exception users**.
3. In the **Edit exception users** dialog, add users, delete users, or update alternative login methods.
4. Click **Save**.
5. In the **Save changes?** dialog, click **Save changes**.

Previously added exception users appear with their current alternative login method.

### Step 3: Test the SSO configuration

After completing the SSO configuration on both platforms—the IdP and AppsFlyer, check to make sure users can log in to AppsFlyer in **either** of the [URL callback methods](/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration): your IdP or the service provider (AppsFlyer), but not both.

#### Test authentication via your IdP

If you've configured the authentication to log in via your IdP, check that users can enter AppsFlyer from the IdP plugin or webpage:

1. If you're signed in to AppsFlyer and the IdP, sign out from both.
2. Open a webpage in incognito mode.
3. Go to your IdP webpage. Since you're not signed in to the IdP, you'll go through an authentication process. Sign in with the relevant user.
4. Search for and select AppsFlyer. You're directed to the AppsFlyer homepage. This indicates the process was successful.

#### Test authentication via your service provider (AppsFlyer)

If you've configured the authentication flow to log in via your service provider (AppsFlyer), check that users can enter AppsFlyer using their email:

![log_in_to_af_by_email2.png](https://files.readme.io/ae22ff9ba0216f54bee4cea82ed7d35cea656a68e30c0a0e4f549b1855ec7cfd-17233244746257.png)

1. If you're signed in to AppsFlyer and the IdP, sign out from both.
2. Open a webpage in incognito mode.
3. Go to the [AppsFlyer login page](https://hq1.appsflyer.com/auth/login) and click **Login with SSO**.
4. Enter the relevant email and click **Continue**. You're now directed to the IdP for authentication.
5. After IdP authentication, you're directed back to AppsFlyer as a logged-in user. This indicates the process was successful.

## Manage SSO configuration

Once you've set up the SSO configuration, you can edit the configuration or remove it.

See how to [access the SSO configuration page](/docs/set-up-sso-authentication-with-your-identity-provider-idp#access-the-sso-configuration-page).

### Edit SSO

From this page, you can edit any of the following options:

- Authentication starting point
- Certificate type
- Service provider metadata
- Identity provider metadata
- Exception users

> 🚧 Important!
>
> When you update the certificate type or authentication starting point, the AppsFlyer metadata changes. Copy the latest service provider metadata from AppsFlyer and add it to your identity provider (IdP) SAML configuration immediately after saving your changes

> 📘 Note
>
> Add at least one trusted admin as an exception user. If the SSO configuration is incorrect, this user can log in with their assigned alternative login method and update the configuration.

To edit the SSO configuration:

1. From the **SAML Single sign-on (SSO)** section, click the **Edit** icon.
2. Open the section you want to update.
3. Make the required changes.
4. Click **Save**.
5. In the **Save changes?** dialog, review the changes.
6. Click **Save changes**.

### Edit exception users

To edit exception users:

1. Open the **Exception users** section.
2. Click **Edit exception users**.
3. In the **Edit exception users** user list, add users, delete users, or update alternative login methods.
4. Click **Save**.
5. In the **Save changes?** dialog, click **Save changes**.

Previously added exception users appear with their current alternative login method.

### Delete SSO configuration

To delete the SSO configuration:

1. From the **SAML Single sign-on (SSO)** section, click the **Delete** icon.
2. In the confirmation dialog, review the impact of deleting the configuration.
3. Click **Delete**.

When you delete the SSO configuration, AppsFlyer deletes the SSO metadata and settings saved for the account.

### Traits and limitations

| Name | Description |
| --- | --- |
| Symbols in email address | SSO does not support email addresses with the + sign in the email address.<br />For example: my+customer@demo.com<br />Having this will result in login failure. |
| Exception users | Exception users must be explicitly added by an admin. |
| Alternative login methods | Supported alternative login methods are **Username & password** and **Authenticator app**. |
| SMS authentication | SMS isn’t supported as an alternative login method for exception users. |
| No exception users | If no exception users are added, all users must log in through SSO after activation. |
| Permissions | To configure SSO and manage exception users, admins must have **Login security** permission set to **Manage**. |
| View-only permissions | Admins with view-only access to **Login security** can view the SSO page but can’t edit SSO settings or exception users. |
| Legacy Unforce SSO migration | For accounts migrated from legacy account-level Unforce SSO, existing username/password users are added as exception users. New users must log in through SSO unless an admin explicitly adds them as exception users. |
| Recommended exception user | We recommend adding at least one trusted admin as an exception user before activating SSO. This helps prevent account lockout if the SSO configuration is incorrect. |

<Cards>
  <Card title="About SSO authentication" href="/docs/sso-authentication-overview-and-faq" icon="fa-solid fa-circle-question">
    Learn about SSO authentication and find answers to FAQs.
  </Card>
  <Card title="Managing exception users" href="/docs/manage-exception-users-for-sso/" icon="fa-solid fa-user-gear">
    Learn about managing exception users for SSO.
  </Card>
</Cards>