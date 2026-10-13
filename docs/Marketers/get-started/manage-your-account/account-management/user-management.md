---
title: "User management"
excerpt: "Create and manage your account's AppsFlyer users, and assign them permissions to access features, apps, and data."
x-zendesk:
  id: 4409128270481
  url: https://support.appsflyer.com/hc/en-us/articles/4409128270481-User-management
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Account management
  section_id: 6551191075473
  position: 1
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11085
  content_tags: [pm-roy-negri, Marketers, Platform essentials]
  labels: [Advertisers, Marketers, Localize, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2021-10-17T11:54:49Z'
  edited_at: '2026-09-20T12:12:52Z'
---
**At a glance:** Create and manage your account's AppsFlyer users, and assign them permissions to access features, apps, and data.

## Overview

AppsFlyer accounts allow for multiple users, each with individually-managed permissions. The maximum number of users per account is determined by your subscription plan.

Each user’s permissions are defined along 3 primary dimensions:

* **Role** (capabilities to access features and perform functions)
* **App access** for current and future apps
* **Data access** by media source and geo
  * Important! Certain AppsFlyer dashboards and features are unavailable to users with limited data access (to media sources and geos). These dashboards and features are [listed here](#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access).

Permissions within each of these dimensions are assigned independently. In other words, you may assign a user a **role** with broad functional capabilities but allow them to exercise those capabilities only within a narrowly-defined set of **apps, media sources, and geos.** The only exception is the [Admin role](#admin%E2%80%94a-special-role), as discussed below, which has access to all capabilities, apps, media sources, and geos.

Admins can [add users to multiple accounts](#multiple-accounts) so they can easily switch between accounts.

## User management page

**To access the User management page:**

* From the top bar, open the account menu (email address dropdown) > **User management**.

[![user-management-page.jpg](https://files.readme.io/0ca6dd472b6f50bfde693bba9c131ce9454dc1df90e3a0fb029e2e05b2330db4-31780969019665.jpg)](https://files.readme.io/0ca6dd472b6f50bfde693bba9c131ce9454dc1df90e3a0fb029e2e05b2330db4-31780969019665.jpg)

### Users tab

The **Users** tab displays a table of all existing users in your account. This is the starting point for creating, managing, and deleting users.

Tips for navigating the Users tab:

* Click the **User** column heading to sort the table alphabetically (ascending/descending).
* Use the search box to find and display specific users.
* Click the filter icon ![filter_icon.png](https://files.readme.io/a71945008c33bf583972af260535d4681c833fc90a6919fbcd628078d6ed6840-31780969026321.png) in the **Role** column heading to filter users by their role (including temp roles).
  * To clear the filter, select **None** in the filter dropdown list.
* Click the **Last login** column heading to sort users by the date they last logged in to AppsFlyer.
  * **Tip:** Use this feature to easily identify and [delete](#deleting-users) inactive users, keep your account secure from unauthorized logins.
* Use the checkboxes to select and [edit multiple users](#multiuser-editing) at the same time.
* Admins only: Click the download icon ![download_icon.png](https://files.readme.io/fba5d56ceb7f6b3dc3191e5ec33c85ccbba0f7dc409ad0390de238c12b479b61-31780969029777.png) in the upper-right corner of the page to download the full user table as a CSV file.
  * The downloaded file includes the same columns as the table in the **Users** tab.

### Roles tab

The **Roles** tab displays a list of all roles defined in your account, including:

* [Predefined roles](#predefined-roles)
* [Custom roles](#managing-custom-roles) you have created
* Any [temp roles](#temp-roles) currently assigned to users

Next to each role, you can see the number of users currently assigned to that role.

Click on the name of any role in the left panel to display the full details of the role’s capabilities.

Explore below the available actions to effectively manage your users and their roles.

## Manage users

Admins can create new users, add them to multiple accounts, edit their details such as roles and access they have to apps and data, and delete users. Some of these actions can be done [in bulk using a dedicated API](#manage-users-in-bulk-via-api).

### Create users

<Embed title="User management" typeOfEmbed="youtube" url="https://www.youtube.com/embed/wLCXP5dFrKg" providerUrl="https://www.youtube.com" />

The page for creating or editing a user includes a number of sections. Make sure to complete them, as described below. When you're finished making the necessary changes, click **Save** at the bottom-right of the page.

#### User details

1. On the **Users** tab, click **New user**.
2. Enter the user’s name (required):
   * Can include letters, numbers, spaces, periods (.), hyphens (-), underscores (\_), and single (') or double (") quotation marks.
   * Other special characters are not allowed.
3. Enter the user’s email address (required):

   * Can include letters, numbers, apostrophes ('), ampersands (&), dollar signs ($), hash symbols (#), hyphens (-), underscores (\_), and periods (.)
   * Two consecutive periods (..) and other special characters are not allowed.
   * Must end with a valid email domain.CALLSTART::Note::

   #### Important!

   A user’s email address is what identifies them in the AppsFlyer platform, meaning:

   * It can't later be changed without deleting and recreating the user.
   * It must be a valid email address at which the user can receive emails.
   * It can't be associated with another user in any AppsFlyer account, [except for users in multiple accounts](#multiple-accounts). If the email address is already in use (either in your account or a different one), you will see the message *Can't create this user.* Follow the [troubleshooting steps below](/docs/user-management#troubleshooting-can%E2%80%99t-create-this-user) to resolve this issue.CALLEND::
4. [Optional] Select the user’s department.

#### Role

Select the user’s role (required)– either a predefined role or a custom role you have already created.

#### App access

Select which apps the user can access:

* The default setting allows access to all current and future apps in the account. To change this setting, use the checkboxes to select and deselect apps.
* A user can be given access to all future apps only if they have access to all current apps.

#### Data access

Set user access levels for media sources and geos. Decide whether to grant access to all or select access to specific ones.

> 📘 **Note**
>
> Users with limited access to media source or geos are unable to access certain [dashboards and features](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access).

#### Media sources

By default, the setting **All** allows access to all media sources within the account. This includes those that will be added in the future. Selecting specific media sources doesn't include access to future media sources.

> 📘 **Note**
>
> * Users with limited media source access are unable to access certain [dashboards and features](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access).
> * Admin and security roles have unrestricted access to all media sources. This can't be changed.

**Media source types:**

There are two types of media sources shown in the list:

* **Paid media sources:** Ad networks, self-reporting ad networks (SRNs), and agencies
* **Custom media sources:** Predefined media sources. This can include owned media links, single source links, OneLink links, and links the advertiser created outside of AppsFlyer.

**Specifications for the list of media sources:**

* Presents media sources with traffic from the past 24 months, sorted by those with the most recent traffic
* Agencies are grouped separately at the bottom of the list
* Contains a maximum of 100,000 media sources:
  * Up to 50,000 ad networks, SRNs, and custom media sources
  * Up to 50,000 agencies
* Is updated once a day. Newly added media sources are only visible in the list one day after traffic has entered the system.
* Media sources with no traffic for over 5 years are removed from the list.

**To change the default setting:**

1. Under **Media sources**, click **All**.
2. From the dropdown list, select the specific media sources to grant access to the user.

After these settings are saved, the user dashboards show only data from the selected media sources.

#### Geos

Select if users have access to data for **All** geos or specific geos only. The default setting allows access to all geos. Limited access means users are unable to access certain [dashboards and features](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access).

**To change the default setting:**

1. Under **Geos**, click **All**.
2. From the dropdown list, select the specific geos to grant access to the user.

#### User activation

Once the user is created, you can see them in the user table with an envelope icon ![pending_invitation_icon.png](https://files.readme.io/cd556e0b9137fbcfbf4bef574332622ca1e567ac76a041b7f7f3874052b037e6-31780969031825.png). This indicates an invitation has been sent and the account is awaiting activation. The user must activate their account using the link in their email. The activation link is valid for 48 hours. After the user activates their account, the envelope disappears.

> 📘 **Note**
>
> If the user didn’t receive the invitation or if the link has expired, you can [resend the invitation](/docs/user-management#resending-a-user-invitation).

### Add users to multiple accounts

Users can be added to multiple accounts and assigned to different roles in each account. This helps users work in different accounts without the need to re-enter credentials.

#### Log in to multiple accounts

Users can log in to multiple accounts using all login methods: credentials (username and password), [2FA](/docs/implementing-and-using-2fa-login), and [SSO](/docs/set-up-sso-authentication-with-your-identity-provider-idp).

> 📘 **Note**
>
> When switching between accounts (not during initial login), users must also enter a 6-digit verification code sent to their email, regardless of which login method they used to sign in. [See this article for more information on how to switch accounts](/docs/welcome-to-appsflyer#h_01H9G1MP3ZYYQCCE6J8Q8GCAWG).

#### Supported accounts and users

Advertiser accounts support having the same user in multiple accounts. With the right permissions, they can add users to all their accounts. See limitations below.

#### Limitations on adding users to multiple accounts

* This feature is available only to advertiser accounts, and only to users with appropriate User management permissions.
* A user can have the role of an [account owner](#account-owner) for one account only. In other accounts, they can hold any other role.
* Users who haven't yet [activated their account](#user-activation) can't be added to another account.

#### Add users to multiple accounts

**To add the same user to multiple accounts:**

1. Log in to the account in which you'd like to add the user.
2. From the menu bar, click the **email address dropdown** > **User management**.
3. From the **Users** tab, click **New user**.
4. Enter the required details, select the role for the user in this account, and click **Save**.
5. Repeat steps 1-4 to add the users to other accounts.

### Edit users

Users can be edited either one at a time or in groups.

#### Individual editing

**To edit an individual user:**

1. On the **Users** tab, click the **Actions** ![actions_icon.png](https://files.readme.io/c7dc63f2be01982234448350bf3ad77bb3ce8ec81907755d7474b667602dab68-31780971791249.png) button on the far-right side of the user’s row.
2. Select **Edit** from the menu.
3. Edit user settings as required.
4. All settings other than email address are editable (including role, apps, media sources, and geos).
5. Click **Save**.

#### Multi-user editing

Multi-user editing is an efficient way to change the account permissions of several users at one time. Using this feature in combination with the search and filtering capabilities of the **Users** tab can make it particularly helpful for managing large numbers of users.

> 📘 **Note**
>
> You can't assign users to the Admin role using multi-user editing.

**To edit multiple users:**

1. On the **Users** tab, select the checkboxes of the user or users you want to edit.
   * Select the checkbox in the column heading to select all visible users.
   * The number of currently-selected users is displayed on the right side of the search box. Note that the [account owner](#account-owner) cannot be selected and is not included in the number of selected users.
2. A series of buttons displays at the top-right of the table: **Role, Apps, Media sources,** and **Geos.**
   * If one or more of the selected users has access to future apps, the **Apps** button is not available. (See [Temp role limitations](/docs/user-management#temp-role-limitations), below.)
3. Click the button for the permissions you want to change.
4. Make the necessary changes using the dialog box or dropdown lists that are displayed.
   * Remember that your changes apply to all selected users!
5. The edited users are highlighted in the table, and the users appear as they will once the changes are saved. However, you still have the opportunity to review your changes and confirm or cancel them in the next step.
6. Review your changes. Click **Save** to confirm or **Cancel** to undo them.

> 📘 **Example**
>
> **Scenario:**
>
> * There are 30 users in your account. Ten of these are in the **Marketing – limited** role.
> * Alice, Bill, and Charlie have just received promotions, and you want to change them from the **Marketing – limited** role to the **Marketing** role.
> * Alice will be working with the Astounding app. Bill will be working with the Beautiful app. Charlie will be working with the Charming app.
>
> **Steps:**
>
> 1. Use the Role filter ![filter_icon.png](https://files.readme.io/a71945008c33bf583972af260535d4681c833fc90a6919fbcd628078d6ed6840-31780969026321.png) to see only the users in the **Marketing–limited** role.
> 2. Change Alice, Bill, and Charlie to the **Marketing** role:
>    * Select the checkboxes for Alice, Bill, and Charlie.
>    * Click the **Role** button.
>    * Select **Marketing** from the dropdown list.
>    * Click **Save** to confirm.
>    * Note that once you confirm the changes, the **Role** filter is cleared, and the table displays all users.
> 3. Give Alice, Bill, and Charlie the appropriate app access:
>    * Use the search box to find Alice, then individually edit her user to give her access to the Astounding app.
>    * Repeat these steps for Bill and Charlie to give them access to Beautiful and Charming, respectively.

### Delete users

Multiple users can be deleted from the account in bulk.

> 📘 **Note**
>
> * The [account owner](/docs/user-management#account-owner) can't be deleted
> * Deleting users is irreversible

**To delete users:**

1. On the **Users** tab, select the checkboxes of the users you want to delete. You can use the search and filters to help find users.
2. After selecting users, click the **Delete** button that now appears at the top-right of the table.
3. The confirmation window lists users to be deleted. Click **Yes, delete** to confirm deletion.

### Manage users in bulk via API

Some user-management actions can be done in bulk using [a dedicated API](https://dev.appsflyer.com/hc/reference/bulk-users-management-overview):

* [Create](https://dev.appsflyer.com/hc/reference/bulk-users-post) multiple users
* [Delete](https://dev.appsflyer.com/hc/reference/bulk-users-delete) multiple users
* [Get](https://dev.appsflyer.com/hc/reference/bulk-users-get) access details of multiple users

The API supports the main user management features on the platform and includes the same error verifications.

## Manage roles

Each user of your AppsFlyer account must be assigned a role. Each role defines the specific AppsFlyer features the user can access and the functions they can perform. A full list of capabilities per role is available on the [Roles tab](#roles-tab) of the **User management** page.

Roles within AppsFlyer can be [predefined roles](#predefined-roles), [custom roles](#custom-roles), or (in certain circumstances) [temp roles](#temp-roles).

### Predefined roles

AppsFlyer is configured with many predefined roles:

* [Admin—a special role](#admin%E2%80%94a-special-role)
* Team manager
* Marketing lead
* Marketing
* Marketing – limited
* Contributor
* Accounting
* Security
* Quality Assurance

> 📘 **Note**
>
> For each of these predefined roles, the functional capabilities are fixed: no "mixing and matching" allowed. However, you can change a user’s functional capabilities at any time by assigning them to a different predefined or custom role (except for the [account owner](#account-owner), as discussed below).

> 📘 **Example**
>
> You have assigned Bill Bates the role of **Team manager.** This role gives Bill the ability to manage **OneLink templates,** but it does not allow him access to the **My plan** and **Payments** pages.
>
> **Question:** Can I keep Bill in the Team manager role but also give him the ability to access the My plan and Payments pages? Can I take away his ability to manage OneLink templates?
>
> **Answer:** No. As long as Bill stays in the Team manager role, you cannot give him the ability to access the My Plan and Payments pages. Nor can you remove his ability to manage OneLink templates. Of course, you can assign Bill to a different predefined role, and his capabilities will change to those defined by that role. Or, you can create a custom role for Bill that changes his capabilities according to your needs.

### Admin

An AppsFlyer account can have **one or more Admins**. This role has several unique characteristics:

#### Access

The Admin role has access to **all account capabilities**, including:

* All features and functions
* All current and future apps
* All media sources and geos

This "all-access" characteristic of the Admin role can't be changed or limited.

#### Manage tokens

Only a user with an Admin role can [manage tokens](/docs/managing-appsflyer-tokens): create, rename, and remove API and server-to-server tokens.

#### Role duplication

The Admin role **can't be duplicated** when creating [custom roles](#managing-custom-roles).

#### Invite new partners to AppsFlyer

A user with an admin role can [send an invitation link](/docs/partner-integrations#invite-new-partners-to-appsflyer) via the Partner Marketplace to invite a partner that isn't integrated with AppsFlyer.

### Account owner

The user created at the time the account was opened, the "account owner"**,** is **assigned the Admin role by default**. The account owner is initially responsible for creating additional users, until additional users with user management capabilities are created.

An account owner has unique characteristics beyond those of the Admin role who isn't the account owner. Unlike any Admin, the account owner **can't** be deleted, removed from the Admin role, or otherwise edited from the [**User management**](/docs/user-management#user-management-page) page. If you need to change the account owner, follow the [steps listed below](#changing-the-account-owner)

### Custom roles

The predefined roles in AppsFlyer have been configured with the specific combinations of capabilities required in most situations. For this reason, many advertisers find that they don't need to further customize roles. However, when additional customization is required, predefined roles are still a great starting point for managing your users' capabilities.

Learn more about [managing custom roles](#managing-custom-roles).

### Temp roles

If your AppsFlyer account existed under our prior user management system (when the only available account types were Admin and Team member), all users were brought into the new system with unchanged capabilities. As a result, most of these users appear in the current system with **temp roles**.

Learn more about [managing temp roles](#managing-temp-roles).

### Get roles data via API

Through the [Get roles API](https://dev.appsflyer.com/hc/reference/get_roles), you can retrieve a list of current roles and their corresponding attributes specific to your account.

## Manage custom roles

### Create custom roles

* **Prerequisite:** Only [account owners](#account-owner) or users with the [Admin role access](#admin%E2%80%94a-special-role) can create a custom role.

**To create a custom role:**

1. On the left panel of the **Roles** tab, under the search bar, click **+ New custom role**.
2. **Role name:** Enter a name for the new role you are creating.
   * **Note:** Once you have saved a custom role, the name of the role cannot be edited.
   * **Recommended:** Make the name descriptive and easily identifiable later.
3. **Role template:** As a starting point, select a predefined role that closely matches the capabilities and permissions for the new custom role.
4. Adjust the settings of the selected role template according to your custom role requirements. The permission levels of all editable capabilities are displayed as buttons. Click these buttons to change the permission levels for the new custom role. (Be sure to scroll down to see the full list of capabilities.)
   * **Note:** Capabilities that don't appear as buttons are currently uneditable.
5. After setting permissions to all the relevant capabilities, click **Save role**.  
   The new custom role is displayed in the left panel and can be assigned when creating new users or editing existing users.

### Edit custom roles

**To edit a custom role:**

1. On the left panel of the **Roles** tab, click on the name of the custom role you want to edit.
2. Click the **Edit** icon ![edit-icon.jpg](https://files.readme.io/d32f150cb5d0271c5504fb3c107e23f73e59c9a3be1630769ad309edf4e79ea0-31780971794321.jpg) from the top-right corner of the page. The display of the right panel changes, allowing you to edit the role permissions settings.
   * **Note:** The role name can't be edited. To change it, you must delete the role and recreate a new one with a different name.
3. The permission levels of all editable capabilities are displayed as buttons. Click these buttons to change the permission levels for the new custom role. (Be sure to scroll down to see the full list of capabilities.)
4. When you are satisfied with all of your selections, click the **Save role** button.
5. The role's permission levels are changed for all new and existing users.

> 📘 **Important!**
>
> Any changes you make to a custom role are automatically applied to **all existing users** in that role.

### Delete custom roles

**To delete a custom role:**

1. On the left panel of the **Roles** tab, click on the name of the custom role you want to delete.
2. Click the **Delete** icon ![delete-icon.jpg](https://files.readme.io/87f206e21926af0836690be064a5af7cb3bce0007f0fc62301b2925701b1d9f9-31780971797265.jpg) from the top-right corner of the page.
3. Confirm that you wish to delete the role.
   * A custom role can be deleted only when there are no users assigned to it. If there are users currently assigned to a custom role, assign these users to a different role before deleting the custom role.

## Special situations and additional procedures

### Manage temp roles

If your account previously used our prior user management system, [**temp roles**](/docs/user-management#temp-roles) were assigned to existing users to ensure that they were brought into the new system with unchanged capabilities.

* Users with the same capabilities were assigned the same temp role.
* Use the features of the [Roles tab](/docs/user-management#roles-tab) to review the capabilities of each temp role and a list of users currently in it.

#### Temp role limitations

Temp roles were designed specifically to allow seamless transition from our prior user management system. As such, they are available only in limited situations:

* Temp roles cannot be assigned to other users (whether new or existing).
* A user with a temp role cannot be assigned a different temp role (though you can change the apps, media sources, and geos to which they have access).
  * Note that a user's access to future apps **cannot** be changed while the user is in a temp role.
* When a user with a temp role is changed to a predefined role, they cannot be returned to the previously-assigned temp role (or to any other temp role).
* If the last user in a temp role is removed from it, the role will no longer appear in your account.

> 📘 **Example**
>
> Your account previously used our prior user management system. Diana and Edward were existing users at the time your account was moved to the new system. Diana is now in Temp role 1, and Edward is in Temp role 2.
>
> * You hire a new employee, Fiona. You can assign Fiona any one of the [predefined roles](/docs/user-management#predefined-roles). However, you cannot assign Fiona Temp role 1 or Temp role 2.
> * Diana cannot be moved from Temp role 1 to Temp role 2. However, you can assign her any of the predefined roles. You can also change her access to apps, media sources, and geos as necessary.
> * If you move Diana from Temp role 1 to the Accounting role, she can’t later be moved back to Temp role 1.
> * If Diana was the last user in Temp role 1 when you moved her to the Accounting role, Temp role 1 will no longer appear in your account.

### Dashboard and feature availability for users with limited media source/geo access

The following AppsFlyer dashboards are **not available** to users whose access is limited to specific media sources and geos:

* SKAN overview
* SKAN Conversion Studio
* Protect360
* Retention
* People-Based Attribution
* Incrementality

Additionally, the following AppsFlyer features are **not available** to these users:

* Pivot
* OneLink
* Validation Rules
* Audiences (not available for media source-restricted users; geo-restricted users can access only audiences that include a "Country" filter, and only for the countries they're authorized to access)
* SDK information
* Ad spend ingestion
* Cost ETL

### Combined media source and agency access

When you grant a user access to a specific agency **and** a specific media source, their data access reflects only the overlap between the two. They don't see all of that agency's data across every media source, and they don't see all of that media source's data across every agency — only the portion where both permissions intersect.

> 📘 **Example**
>
> You give a user access to Agency B and Media Source A. Agency B manages app installs coming from several media sources, including Media Source A. This user sees only the installs from Media Source A that Agency B manages — not Agency B's data from other media sources, and not Media Source A's data managed by other agencies.

### Change the account owner

Because all Admins have essentially the same permissions as the account owner, changing the account owner is not usually necessary. But if you find that you must change the account owner, follow these steps to do so.

> 📘 **Important!**
>
> Changing the account owner must be completed manually according to the steps below. It can't be done from the **User management** page.

#### #1–Assign a team member the Admin role

Changing the account owner can only be requested from a user with an Admin role. Therefore, it is recommended to:

* Assign a team member who can complete all the steps the **Admin** role.
* The user must activate their account (i.e., log in at least once).

#### #2–Send an email request

A user with an Admin role must send an email request to AppsFlyer **from the email address of the current account owner.**

* Be sure that this is the current account owner's email address as it appears in your AppsFlyer account.
* If the current account owner has left your company, ask your IT team to enable you to send an email from their address.

Include the following information in your request:

| To: | Your AppsFlyer CSM or hello@appsflyer.com |
| --- | --- |
| CC: | Email of new account owner |
| Subject: | Request to change the account owner for `{account name}` |
| Body: | Short message including the name and title of the new account owner |

Use this sample email as a reference:

![account_owner_change_email.png](https://files.readme.io/eb10736386a7a8cfc274979a3aa933e23288c74d1b26c0f06d72005ceebafe06-31780969048081.png)

#### #3–Next steps

Once the change has been processed, you'll receive an email notification from AppsFlyer.

* If you want the prior account owner to continue using your AppsFlyer account, [create a new user](/docs/user-management#creating-users) for them and assign them a new role.
* APIs using token v2 aren't affected by changing the account owner. [Learn more about managing tokens](/docs/managing-appsflyer-tokens).

### Troubleshooting: "Can’t create this user"

If you receive the error message *Can’t create this user* when entering the email address of a new user, it generally means that the email is already associated with an AppsFlyer user (either in your account or a different one). Follow the steps relevant to your situation:

If the user is in your account:

* Check to see if the user has activated their account. If not, [resend the invitation](/docs/user-management#resending-a-user-invitation) if required.
* If the user has activated their account, ask them to try to log in again using the email address associated with their user. Advise them to follow the **Forgot password** steps if required.

If the user’s email is used in a different account or you can’t determine the account in which the user’s email is used, select one of the following options:

* Delete them from the other account and add them to yours (requires that either you or the user has the required permissions in the other account); or
* Add them to your account using a different email address. This must be a valid email address at which they can actually receive an email; or
* Contact your Customer Success Manager (CSM) or send an email to our Customer Engagement team at [hello@appsflyer.com](mailto:hello@appsflyer.com).

### Resend a user invitation

If a new user did not receive their [account activation invitation](#user-activation) or if they did not activate within 48 hours, you can resend the email as follows:

1. On the **Users** tab, click the **Actions** button ![actions_icon.png](https://files.readme.io/c7dc63f2be01982234448350bf3ad77bb3ce8ec81907755d7474b667602dab68-31780971791249.png) on the far-right side of the user’s row.
   * Note that the user is still shown with an envelope icon ![pending_invitation_icon.png](https://files.readme.io/cd556e0b9137fbcfbf4bef574332622ca1e567ac76a041b7f7f3874052b037e6-31780969031825.png), indicating that they have not yet activated their account).
2. Select **Resend email invite** from the menu.

### Reset a user's two-factor authentication (2FA)

If your account uses 2FA, there may be occasions on which you need to reset a user’s 2FA settings. Do so as follows:

1. On the **Users** tab, click the **Actions** button ![actions_icon.png](https://files.readme.io/c7dc63f2be01982234448350bf3ad77bb3ce8ec81907755d7474b667602dab68-31780971791249.png) on the far-right side of the user’s row.
2. Select **Reset 2FA** from the menu.

**Note:** An admin can reset any other admin's 2FA other than their own or the [account owner's](#account-owner). To reset the account owner's 2FA, contact the AppsFlyer Support team.