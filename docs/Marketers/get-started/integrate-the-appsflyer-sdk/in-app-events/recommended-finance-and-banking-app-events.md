---
title: Recommended finance and banking app events
excerpt: >-
  Measure the quality of your users throughout their user journey by recording
  these suggested in-app events for your finance and banking app .
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-04-27T12:58:44Z'
  edited_at: '2024-09-23T12:46:21Z'
  id: 360019598337
  locale: en-us
  section: In-app events
  section_id: 6551285343761
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360019598337-Recommended-finance-and-banking-app-events
---
## ![banking.png](https://files.readme.io/260638f807a43f42c6ff99bb72b8d4113b2df09436b9322a820888ad3f8a01ae-20659476893969.png) Finance and banking

Finance and banking apps provide users with the ability to perform a wide range of financial-related objectives, such as signing up for new credit cards or applying for loans. The typical events that we suggest recording include account openings, credit card applications, and loan applications.

Recording these events can help you determine:

* What type of account users want the most, and provide you with ideas for retargeting
* What benefits users look for in a credit card
* What users need financial assistance for, and how much assistance they want

> 📘 **Important!**
>
> * **A note from our lawyers**: Health data is considered "Restricted Data" and is considered a special category of data in many jurisdictions. As such, customers are prohibited from sending AppsFlyer any such data.
> * Make sure to read the [instructions](/docs/in-app-events-overview#setting-up-in-app-events) for marketers about implementing in-app events.
> * To streamline the implementation process, use our [In-app event generator](http://evgen.appsflyer.com/?vertical=finance_banking). This tool includes all of the typical in-app events described in this article and lets you modify the events according to your business needs. Once complete, share the file with your developer.
> * For each recommended event included in this article, there are [code samples](http://evgen.appsflyer.com/?vertical=finance_banking&view=code) for iOS, Android, and Unity developers.
> * Detailed instructions for your developer can be found in the  **[AppsFlyer developer hub](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions).**
>
> For more information about recording in-app events, see the [In-app events guide](/docs/in-app-events-overview).

[![Flowchart_for_recommended_events finance_banking_app_user_journey](https://files.readme.io/722d2a3df606df1c61f86c7e8e1524566de8fbfd0ceb48e4cd5913a0b3ac9283-360020063337.png)](https://files.readme.io/722d2a3df606df1c61f86c7e8e1524566de8fbfd0ceb48e4cd5913a0b3ac9283-360020063337.png)

## Recommended structures for predefined events

The following section provides a list of event structures that are typical to the finance and banking vertical. Each structure includes a predefined event name and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

<div id="login-af_login" />

<Accordion title="Login (af_login)">

**Purpose**

Understand the retention of your registered users

**Trigger**

When the user successfully logs in

**Event parameters**

Can be sent without any additional parameters

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Complete registration (af_complete_registration)">

**Purpose**

Learn how many users installed the app and completed the signup process, and what signup methods your users prefer

**Trigger**

When the user completes the signup process

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_registration\_method | Type of signup method | Email, Facebook |

</Accordion>

## Recommended structures for custom events

The following section provides a list of event structures that include custom event names and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

<div id="registration-verified-registration_verified" />

<Accordion title="Registration verified (registration_verified)">

**Purpose**

Record this event and compare it with other data to learn more about your users. For example, you can learn how many users sign up but aren't accepted. 

**Trigger**

When the registration is verified

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| submit\_registration | Type of signup method verified. Do not enter personal identifiable information (PII). | Email, Facebook |

</Accordion>

<div id="submit-account-application-submit_account_application" />

<Accordion title="Submit account application (submit_account_application)">

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

</Accordion>

<div id="open-account-success-open_account_success" />

<Accordion title="Open account success (open_account_success)">

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

</Accordion>

<div id="open-account-rejected-open_account_rejected" />

<Accordion title="Open account rejected (open_account_rejected)">

**Purpose**

Record this event and compare it with other data to learn more about your users. For example, you can learn how many users apply for accounts but aren't accepted; and then try to improve the funnel or retarget those users later.

**Trigger**

When the user completes the signup process

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| account\_type | Type of account applied for | savings |

</Accordion>

<div data-zendesk-anchors="finance-and-banking=-finance-and-banking h_01HGTAXN8PV7TPNRBWD593BR4K=-finance-and-banking h_01HGTAXN8Q652HG7412X583KWX=important h_01HGTAXN8QWEWD86FMF6GEZNZD=recommended-structures-for-predefined-events h_01HGTAXN8Q3K0EFGXZ41XZH438=login-af_login h_01HGTAXN8Q6KFDPB8XSVT3F9E8=complete-registration-af_complete_registration h_01HGTAXN8Q47F6CXXBEVCDPSBA=recommended-structures-for-custom-events h_01HGTAXN8QB911JMER3EV7RGTM=registration-verified-registration_verified h_01HGTAXN8QCYR0BQ3Q3VN0EQ9X=submit-account-application-submit_account_application h_01HGTAXN8QJ4DKQS2FY9KY0AX4=open-account-success-open_account_success h_01HGTAXN8QK1P5QYEN5SNBQ5ED=open-account-rejected-open_account_rejected" />
