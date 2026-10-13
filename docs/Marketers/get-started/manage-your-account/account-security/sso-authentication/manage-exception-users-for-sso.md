---
title: "Manage exception users for SSO"
excerpt: "Learn how to configure and manage exception users who can bypass SSO using alternative login methods like username/password or authenticator apps."
x-zendesk:
  id: 47096696016529
  url: https://support.appsflyer.com/hc/en-us/articles/47096696016529-Manage-exception-users-for-SSO
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
  content_tags: [pm-roy-negri, Marketers, Platform essentials]
  labels: []
  promoted: false
  comments_disabled: true
  created_at: '2026-05-27T08:43:46Z'
  edited_at: '2026-05-31T05:00:01Z'
---
Exception users are users who aren’t required to log in through SSO. SSO remains enforced for the account, and admins can give specific users access to an assigned alternative login method.

## **About exception users**

Exception users provide controlled access for users who need a non-SSO login method. For example, admins can use exception users for break-glass access or for users who can’t use the account’s identity provider.

Exception users can log in with SSO or with the alternative login method assigned to them. Users who aren’t added as exception users must log in through SSO.

> 👍 Recommended practice
>
> We recommend adding at least one trusted admin as an exception user during initial SSO setup. If the SSO configuration is incorrect, the admin can log in with their assigned alternative login method and update the configuration.

## **Prerequisites**

- SSO must be configured for the account.
- To manage SSO and exception users, you must have **Login security** permission set to **Manage**.

### Add exception users during SSO setup

> 📘 Recommended
>
> Add at least one trusted admin as an exception user before activating SSO. This helps prevent account lockout if the SSO configuration is incorrect.

To add exception users:

1. In the **Add exception users** step, click **Add exception users**.
2. Search for a user by name or email.
3. Select the user you want to add.
4. From the **Alternative login method** drop-down list, select one of the following:
   - **Username & password**
   - **Authenticator app**
5. Repeat steps 2-4 for each user you want to add.
6. Click **Add exception users**.
7. Click **Activate SSO**.

If you don’t add exception users, everyone on the account must log in through SSO after activation.

### Add login methods for multiple users

To add the same alternative login method for multiple users:

1. Select the checkboxes for the users you want to update.
2. Click **Set login method for selected users**.
3. Select one of the following:
   - **Apply username and password for all selected users**
   - **Apply authenticator app for all selected users**

### Edit exception users after SSO activation

After SSO is active, you can add exception users, delete exception users, or update their alternative login methods.

To edit exception users:

1. Go to **Security center** \> **Login security**.
2. From the **SAML Single sign-on (SSO)** section, click the **Edit** icon.
3. Open the **Exception users** section.
4. Click **Edit exception users**.
5. Add users, delete users, or update alternative login methods.
6. Click **Save**.
7. In the **Save changes?** dialog, click **Save changes**.

Previously added exception users appear with their current alternative login method.

### Delete exception users

To delete an exception user:

In the Edit exception users dialog, find the user you want to delete.

Click the Delete icon.

The user is deleted from the list immediately.

### Alternative login methods

| **Login method** | **Description** |
| --- | --- |
| Username & password | Lets the exception user log in with their AppsFlyer username and password. |
| Authenticator app | Lets the exception user log in using an authenticator app. SMS isn’t supported. |

### Handle partial activation failures

In some cases, SSO activation succeeds, but one or more exception users aren’t added.

When this happens:

- SSO stays active.
- Users who weren’t added as exception users must log in through SSO.
- Admins can add or update exception users from **Edit SSO**.

### Reset passwords for SSO accounts

All users can start the forgot-password flow. However, only exception users assigned the **Username & password** alternative login method can log in with the new password.

Users who aren’t exception users must continue logging in through SSO.

### Migrate from legacy Unforce SSO

For accounts migrated from legacy account-level Unforce SSO, existing users who logged in with username and password are added as exception users with **Username & password** as their alternative login method.

New users created after migration must log in through SSO unless an admin explicitly adds them as exception users.

### Traits and limitations

| **Trait** | **Description** |
| --- | --- |
| SSO enforcement | SSO remains enforced for the account. Exception users are controlled user-level exceptions. |
| Supported alternative login methods | Exception users can use **Username & password** or **Authenticator app**. |
| SMS authentication | SMS isn’t supported as an alternative login method. |
| Required permission | To manage exception users, admins must have **Login security** permission set to **Manage**. |
| View-only permission | Admins with view-only access can view existing exception users but can’t edit them. |
| New users after migration | New users must log in through SSO unless an admin adds them as exception users. |