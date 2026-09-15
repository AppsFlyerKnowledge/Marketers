---
title: "Configure AppsFlyer SSO in JumpCloud"
excerpt: "Learn how to configure the single sign-on (SSO) process using JumpCloud as your identity provider for AppsFlyer."
---
At a glance: Configure the SSO process using JumpCloud as an identity provider (IdP).

The first stage in configuring the AppsFlyer SSO process is done on the JumpCloud platform. Follow the steps below:

### Create the AppsFlyer app in JumpCloud

> 📘 Prerequisite
>
> A JumpCloud account with administrative privileges.

1. In the JumpCloud admin menu, go to [SSO](https://console.jumpcloud.com/#/sso) and click **+ Add New Application**.
2. Search for AppsFlyer in the list of apps, and click **configure**.
3. In **New SSO**, under the **General Info** tab, name your app in the **Display label** field.
4. [Optional] Add a description.
5. Under the **SSO** tab:
   1. **Upload Metadata:** Download the [AppsFlyer SSO metadata](https://hq1.appsflyer.com/auth/sso-metadata) as an XML file, then upload it here.
   2. **ACS URLs:** Enter the callback URL according to the [method for authenticating your users](/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration).
   3. **Login URL:** Enter the AppsFlyer [login URL](https://hq1.appsflyer.com/auth/login).

![jumpcloud_sso_tab2__1_.png](https://files.readme.io/3b45c98d191a35644c5479a0237e92908ca6f18416f6df2b6e0c84a30940307b-15934671100561.png)

6. Click **activate**.
7. A public certificate is created. An indication of it appears on the top right of the page. Click **Download Certificate**. This certificate is needed in [Step 2, on the AppsFlyer platform](/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer).

### Create JumpCloud users

1. Go to [Users](https://console.jumpcloud.com/#/users) from the JumpCloud admin menu, and click the **+** icon.
2. Select **Manual user entry**.

![cloud_jump_manual_user_entry.png](https://files.readme.io/d00299979fa5e036c464c8c6d360965d46e42d5042a31366ced7adc84914c0be-14947838808081.png)

3. Enter all required fields: **Username**, **Company Email**, and click **save user**.
4. Set user password settings according to the acceptable method in your company.
5. To continue adding users, click **Save And Create Another**, then repeat step 3. When done adding all users, click **Save**.

### Create JumpCloud groups and assign them to the AppsFlyer app

Create a group and assign users to it:

1. Go to [User Groups](https://console.jumpcloud.com/#/groups/user) from the JumpCloud admin menu, and click the **+** icon.
2. Enter the group name.
3. From the **Users** tab, select the users to add to this group.
4. From the **Applications** tab, select the AppsFlyer app you've just created.
5. Click **save**.

### Get IdP SSO metadata

1. From the JumpCloud admin menu, go to **SSO**.
2. Select the AppsFlyer app you've just configured, and click **Copy Metadata URL** from the top right. You'll paste this link in the next step.

### Complete the process in AppsFlyer

Now that you've configured the IdP part, go back to AppsFlyer to [complete the configuration](/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer). You can then [test](/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process) to see that it works.