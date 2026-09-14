---
title: "Account login and password reset"
excerpt: "Learn how to log in to AppsFlyer, manage first-time access, and reset user passwords or two-factor authentication."
---
At a glance: Log in to AppsFlyer, add multiple accounts, and reset user passwords.

## Log in instructions

Log in instructions for first-time and existing users. This includes a new account creation, a new user invitation, or how to log in as an existing user.

> 📘 Note
>
> For instructions on how to create a user see [here](/docs/user-management#creating-users).

### Logging in for the first time

Whether you just signed up or have just been invited to AppsFlyer, you will receive an email with an activation link.

To sign in to AppsFlyer:

1. Open the AppsFlyer activation email
2. **For the first user on an account**:
   1. Click the activation link in the email body

      > 📘 Note
      >
      > The user created when the account is opened is the "account owner" and is assigned the [Admin role by default.](/docs/user-management#account-owner)
3. **For users using an invite**:
   1. Copy the verification code in the email body
   2. Click the **AppsFlyer login page** button in the email body
   3. Enter your code

      > 📘 Note
      >
      > Verification codes are valid for 15 minutes. If the verification code expires, click **Resend Code** to receive a new one
4. Create a password

### Existing users

Existing users can log into AppsFlyer through the [main login page](https://hq1.appsflyer.com/auth/login).

Log in to AppsFlyer can be done using your:

- Credentials (username and password)
- Google login
- [Single Sign-on](https://support.appsflyer.com/hc/sections/20162151531793-SSO-authentication)

> 📘 Note
>
> If your administrator configured a [two-factor authentication (2FA)](/docs/implementing-and-using-2fa-login) for your account, you'll be asked to verify the login using another authentication method.

### Two-factor authentication (2FA)

If 2FA is enabled in the Security Management settings, it will be activated after your initial login.

[To reset a user's 2FA, see here](/docs/account-login-and-password-reset#resetting-twofactor-authentication-2fa).

## Password, Login, or 2FA reset

Password reset for existing users and users who did not complete the initial registration or invitation process.

### Existing users and invited users who have not activated yet

To reset your password:

1. On the AppsFlyer [main login page](https://hq1.appsflyer.com/auth/login), click **Forgot password?**
2. A one-time verification code will be sent to your email
3. Copy the verification code in the email body
4. Click the **AppsFlyer login page** button in the email body
5. Enter your code

> 📘 Note
>
> Verification codes are valid for 15 minutes

If the verification code expires, click **Resend Code** to receive a new one
6. Create a new password

### Users who have not completed the initial registration

When signing up to AppsFlyer, an email invitation was sent to your email. The activation link in the email is valid for 7 days. To complete sign up, do the following:

1. Open the email
2. Click the activation **AppsFlyer sign up page** button the email body

> 📘 Note
>
> The user created at the time the account was opened, the "account owner", is assigned the [Admin role by default.](/docs/user-management#account-owner)

3. If the link has expired, complete the sign up from the beginning
4. Create a password

### Reset a user's two-factor authentication (2FA)

If your account uses 2FA, there may be occasions on which you need to reset a user’s 2FA settings. Do so as follows:

1. On the **Users** tab, click the **Actions** button ![actions_icon.png](https://files.readme.io/88a240d0697e042024a793d26bb97141a66079963636908761c8feb9db2ef4f4-33118830755985.png) on the far-right side of the user’s row.
2. Select **Reset 2FA** from the menu.

> 📘 Note
>
> An admin can reset any other user's 2FA other than their own. To reset the account owner's 2FA, [contact AppsFlyer Support team](https://support.appsflyer.com/hc/articles/360020991538).