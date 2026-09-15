---
title: "Recommended finance and banking app events"
excerpt: "Measure user quality throughout their journey by recording suggested in-app events for your finance and banking app."
---
**At a glance:** Measure the quality of your users throughout their user journey by recording these suggested in-app events for your finance and banking app.

## ![banking.png](https://files.readme.io/260638f807a43f42c6ff99bb72b8d4113b2df09436b9322a820888ad3f8a01ae-20659476893969.png) Finance and banking

Finance and banking apps provide users with the ability to perform a wide range of financial-related objectives, such as signing up for new credit cards or applying for loans. The typical events that we suggest recording include account openings, credit card applications, and loan applications.

Recording these events can help you determine:

- What type of account users want the most, and provide you with ideas for retargeting
- What benefits users look for in a credit card
- What users need financial assistance for, and how much assistance they want

> ❗️ Important!
>
> * **A note from our lawyers**: Health data is considered "Restricted Data" and is considered a special category of data in many jurisdictions. As such, customers are prohibited from sending AppsFlyer any such data.
> * Make sure to read the [instructions](https://support.appsflyer.com/hc/articles/115005544169-Rich-in-app-events-guide#setting-up-inapp-events) for marketers about implementing in-app events.
> * To streamline the implementation process, use our [In-app event generator](http://evgen.appsflyer.com/?vertical=finance_banking). This tool includes all of the typical in-app events described in this article and lets you modify the events according to your business needs. Once complete, share the file with your developer.
> * For each recommended event included in this article, there are [code samples](http://evgen.appsflyer.com/?vertical=finance_banking&view=code) for iOS, Android, and Unity developers.
> * Detailed instructions for your developer can be found in the **[AppsFlyer developer hub](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions).**

For more information about recording in-app events, see the [In-app events guide](https://support.appsflyer.com/hc/articles/115005544169).

![Flowchart_for_recommended_events finance_banking_app_user_journey](https://files.readme.io/722d2a3df606df1c61f86c7e8e1524566de8fbfd0ceb48e4cd5913a0b3ac9283-360020063337.png)

## Recommended structures for predefined events

The following section provides a list of event structures that are typical to the finance and banking vertical. Each structure includes a predefined event name and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

### Login (af\_login)

**Purpose**

Understand the retention of your registered users

**Trigger**

When the user successfully logs in

**Event parameters**

Can be sent without any additional parameters

### Complete registration (af\_complete\_registration)

**Purpose**

Learn how many users installed the app and completed the signup process, and what signup methods your users prefer

**Trigger**

When the user completes the signup process

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_registration\_method | Type of signup method | Email, Facebook |

## Recommended structures for custom events

The following section provides a list of event structures that include custom event names and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

### Registration verified (registration\_verified)

**Purpose**

Record this event and compare it with other data to learn more about your users. For example, you can learn how many users sign up but aren't accepted.

**Trigger**

When the registration is verified

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| submit\_registration | Type of signup method verified. Do not enter personal identifiable information (PII). | Email, Facebook |

### Submit account application (submit\_account\_application)

**Purpose**

Record this event and compare it with other data to learn more about your users. For example, you can learn how many users sign up but do not apply to open an account.

**Trigger**

When the user completes the account application process

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| account\_type | Type of account applied for | savings |
| application\_method | Where the application was made | app |
| PII\_type | Type of ID used during application | passport |

### Open account success (open\_account\_success)

**Purpose**

Record this event and compare it with other data to learn more about your users. For example, you can learn how many users apply for accounts and are accepted; and then try to improve the funnel or retarget those users later.

**Trigger**

When the user application is accepted and the account is opened

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| account\_type | Type of account opened | savings |
| application\_method | Where the application was made | app |
| PII\_type | Type of ID used during application | identification card |

### Open account rejected (open\_account\_rejected)

**Purpose**

Record this event and compare it with other data to learn more about your users. For example, you can learn how many users apply for accounts but aren't accepted; and then try to improve the funnel or retarget those users later.

**Trigger**

When the user completes the signup process

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| account\_type | Type of account applied for | savings |