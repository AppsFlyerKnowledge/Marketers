---
title: "Recommended P2P lending app events"
excerpt: "Measure the quality of your users throughout their user journey by recording these suggested in-app events for your peer-to-peer (P2P) lending app."
---
## ![InApp_Events_lending.png](https://files.readme.io/e3465ee913a65a215f1c224db20d4f1fd61fd0bf488b798073c94b4e8387d252-20659507679889.png) P2P lending

P2P lending is a way for individuals and businesses to lend and borrow money from one another. The typical events that we suggest recording are the activities of individual lenders and borrowers, the types of loans people offer, and loan acceptance and rejection rates.

The data that you gather from event recording can highlight trustworthy borrowers and offer them better interest rates. Similarly, you can see who the most active lenders are and offer them lower fees. In addition, once you know what type of loans are most popular with your users, you can launch marketing campaigns that target these audiences.

> 📘 Important!
>
> * Make sure to read the [instructions](https://support.appsflyer.com/hc/articles/115005544169-Rich-in-app-events-guide#setting-up-inapp-events) for marketers about implementing in-app events.
> * To streamline the implementation process, use our [In-app event generator](http://evgen.appsflyer.com/?vertical=p2p_lending). This tool includes all of the typical in-app events described in this article and lets you modify the events according to your business needs. Once complete, share the file with your developer.
> * For each recommended event included in this article, there are [code samples](http://evgen.appsflyer.com/?vertical=p2p_lending&view=code) for iOS, Android, and Unity developers.
> * Detailed instructions for your developer can be found in the **[AppsFlyer developer hub](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions).**

For more information about recording in-app events, see the [In-app events guide](https://support.appsflyer.com/hc/articles/115005544169).

![Flowchart_for_recommended_events P2P_lending_app_user_journey](https://files.readme.io/597a98cf1df450e9e14eb32d8bdc14df647551ca91a2baca78895ca740eb805c-360020063617.png)

## Recommended structures for predefined events

The following section provides a list of event structures that are typical to the P2P lending vertical. Each structure includes a predefined event name and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

### Complete registration (af\_complete\_registration)

**Purpose**

Determine how many users actually verify their identity after registering. You can attribute these users to campaigns and see what campaigns generate active users.

**Trigger**

When the user's registration is approved

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_registration\_method | Type of signup method | email, Facebook |

### Login (af\_login)

**Purpose**

Understand the retention of your registered users

**Trigger**

When the user successfully logs in

**Event parameters**

Can be sent without any additional parameters

## Recommended structures for custom events

The following section provides a list of event structures that include custom event names and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

### Registration submitted (registration\_submitted)

**Purpose**

Since P2P lending is susceptible to abuse, users must first verify their identity. They do so by submitting a registration request. This event can help you:

* Determine how many users register but never verify their account
* See the correlation between registration methods, such as email, Facebook, Google, and verification rates

**Trigger**

After the user submits a request to register

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_registration\_method | Type of signup method | Email, Facebook |

### Fill loan form (fill\_loan\_form\_\<FORM\_NAME\>)

**Purpose**

Determine the drop rate, and retarget borrowers who do not complete their loan applications.

Note that when you send this event, include the form name in the event name.

**Trigger**

When a borrower submits a form

**Event parameters**

Can be sent without any additional parameters

> 📘 Note
>
> It is highly recommended that you associate loans with lenders. To do so, make sure to set the Customer User ID. [Setting the Customer User ID](https://support.appsflyer.com/hc/articles/207032016-Customer-User-ID) is your way to match lenders with users of your app as they appear in AppsFlyer. By setting the Customer User ID you make sure that any event is sent with the Customer User ID.

### Submit loan application (submit\_loan\_application)

**Purpose**

This event can help you :

* Determine the overall number of loan applications in your app
* Learn about the maximum, minimum, and average amount in loan applications
* Determine the type of loans people apply for

**Trigger**

When the user successfully submits a loan application

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| loan\_id | ID of the loan | 1735102 |
| loan\_amount | Amount requested | 1000 |
| loan\_type | Loan period | 3 months |

### Loan form (loan\_form)

**Purpose**

Review loan applications submitted by borrowers

**Trigger**

When the borrower successfully submits a loan application

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| loan\_id | ID of the loan | 1735102 |
| loan\_amount | Amount requested | 1000 |
| loan\_type | Loan period | 3 months |

### Submit credit check (submit\_credit\_check)

**Purpose**

Check the borrower's financial history (for example, past credit, payment habits, and types of loans) to assess the risk level.

**Trigger**

After the lender receives a request for a loan

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| loan\_id | ID of the loan | 1735102 |
| loan\_amount | Amount requested | 1000 |
| loan\_type | Loan period | 3 months |

### Loan accepted (loan\_accepted)

**Purpose**

Learn about trends in loans and other metrics. This event can help you determine:

* What type of loans are accepted
* The amount requested in loans that are approved
* Which lenders accept the most loans

**Trigger**

When a loan is accepted

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| loan\_id | ID of the loan | 1735102 |
| loan\_amount | Amount requested | 1000 |
| loan\_type | Loan period | 3 months |

### Loan rejected (loan\_rejected)

**Purpose**

Understand the reasons why loans get rejected. You can see the correlation between the loan amount, the loan period, and rejection rates. You can also retarget users whose loan gets rejected and suggest they take a smaller loan.

**Trigger**

When a lender rejects a loan

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| loan\_id | ID of the loan | 1735102 |

### Payment (payment)

**Purpose**

Helps you mark borrowers as trustworthy. Trustworthy borrowers are those that follow their obligation to cover their loans. You can attribute borrowers to campaigns and understand which campaigns generated trustworthy borrowers. In addition, this event can also help you gather data about the minimum, maximum, and average amount of payments.

**Trigger**

When a borrower makes a payment on their loan

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| loan\_id | ID of the loan | 1735102 |
| payment\_amount | Amount paid | 100 |
| payment\_id | ID of the payment | AE12SF |

### Payment completed (payment\_completed)

**Purpose**

Highlight borrowers who follow their obligation to cover a loan. You can also retarget such borrowers and offer them lower interest fees or other promotions.

**Trigger**

When a loan is fully paid back

**Event parameters**

| Field name | Description | Example value |
| --- | --- | --- |
| loan\_id | ID of the loan | 1735102 |

### Payment received (payment\_received)

**Purpose**

Verify that the borrower completes loan payments according to the terms of the loan agreement.

**Trigger**

When a borrower makes a payment on their loan

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| loan\_id | ID of the loan | 1735102 |
| payment\_amount | Amount paid | 100 |
| payment\_id | ID of the payment | AE12SF |