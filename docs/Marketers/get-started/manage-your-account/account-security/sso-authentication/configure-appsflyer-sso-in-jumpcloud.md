---
title: Configure AppsFlyer SSO in JumpCloud
excerpt: Configure the SSO process using JumpCloud as an identity provider (IdP).
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
  created_at: '2023-03-08T07:39:41Z'
  edited_at: '2023-11-15T10:59:34Z'
  id: 13563131567249
  locale: en-us
  section: SSO authentication
  section_id: 20162151531793
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/13563131567249-Configure-AppsFlyer-SSO-in-JumpCloud
---
The first stage in configuring the AppsFlyer SSO process is done on the JumpCloud platform. Follow the steps below:

<div id="create-the-appsflyer-app-in-jumpcloud" />

<Accordion title="Create the AppsFlyer app in JumpCloud">

**Prerequisite:** A JumpCloud account with administrative privileges.

1. In the JumpCloud admin menu, go to [SSO](https://console.jumpcloud.com/#/sso) and click **+ Add New Application**.
2. Search for AppsFlyer in the list of apps, and click **configure**.
3. In **New SSO**, under the **General Info** tab, name your app in the **Display label** field.
4. [Optional] Add a description.
5. Under the **SSO** tab:
   1. **Upload Metadata:** Download the [AppsFlyer SSO metadata](https://hq1.appsflyer.com/auth/sso-metadata) as an XML file, then upload it here.
   2. **ACS URLs:** Enter the callback URL according to the [method for authenticating your users](/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration).
   3. **Login URL:** Enter the AppsFlyer [login URL](https://hq1.appsflyer.com/auth/login).  

      ![jumpcloud_sso_tab2__1_.png](https://files.readme.io/3b45c98d191a35644c5479a0237e92908ca6f18416f6df2b6e0c84a30940307b-15934671100561.png)
6. Click **activate**.
7. A public certificate is created. An indication of it appears on the top right of the page. Click **Download Certificate**. This certificate is needed in [Step 2, on the AppsFlyer platform](/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer).

</Accordion>

<div id="create-jumpcloud-users" />

<Accordion title="Create JumpCloud users">

1. Go to [Users](https://console.jumpcloud.com/#/users) from the JumpCloud admin menu, and click the **+** icon.
2. Select **Manual user entry**.  
   ![cloud_jump_manual_user_entry.png](https://files.readme.io/d00299979fa5e036c464c8c6d360965d46e42d5042a31366ced7adc84914c0be-14947838808081.png)
3. Enter all required fields: **Username**, **Company Email**, and click **save user**.
4. Set user password settings according to the acceptable method in your company.
5. To continue adding users, click **Save And Create Another**, then repeat step 3. When done adding all users, click **Save**.

</Accordion>

<div id="create-jumpcloud-groups" />

<Accordion title="Create JumpCloud groups and assign them to the AppsFlyer app">

Create a group and assign users to it:

1. Go to [User Groups](https://console.jumpcloud.com/#/groups/user) from the JumpCloud admin menu, and click the **+** icon.
2. Enter the group name.
3. From the **Users** tab, select the users to add to this group.
4. From the **Applications** tab, select the AppsFlyer app you've just created.
5. Click **save**.

</Accordion>

<div id="get-idp-sso-metadata" />

<Accordion title="Get IdP SSO metadata">

1. From the JumpCloud admin menu, go to **SSO**.
2. Select the AppsFlyer app you've just configured, and click **Copy Metadata URL** from the top right. You'll paste this link in the next step.

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="Complete the process in AppsFlyer">

Now that you've configured the IdP part, go back to AppsFlyer to [complete the configuration](/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer). You can then [test](/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process) to see that it works.

</Accordion>

<div data-zendesk-anchors="h_01HF99ZFBKPYCP8228VKWPCRHX=create-the-appsflyer-app-in-jumpcloud h_01HF99ZFBKXD6HQE44FDQVQZWK=create-jumpcloud-users h_01HF99ZFBK0T9JQVFNTX705V9M=create-jumpcloud-groups h_01HF99ZFBKDFKTFXEE8Q0MH6SY=get-idp-sso-metadata h_01HF99ZFBK40ZTFKKJNXP4N294=complete-the-process-in-appsflyer" />
