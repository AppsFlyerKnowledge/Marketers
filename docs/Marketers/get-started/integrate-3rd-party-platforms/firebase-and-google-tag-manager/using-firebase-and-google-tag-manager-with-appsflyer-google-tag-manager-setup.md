---
title: "Google Tag Manager Setup"
excerpt: "Learn how to configure Google Tag Manager to send events reported via the Firebase SDK to AppsFlyer."
---
Instructions for setting up event sending reported via Firebase SDK to AppsFlyer in Google Tag Manager.

## Google Tag Manager setup

This section discusses the necessary setup in Google Tag Manager (GTM) UI. All the steps described in this section are required in order for GTM to send events to AppsFlyer. Follow the steps in the order they are listed.

The following steps are for Google Tag Manager for mobile apps. If the UI that you see in your Google Tag Manager is different than the screenshots in the various steps, check the following:

1. Your Google Tag Manager container is configured for mobile apps.
2. The container is v5. For more information, click [here](https://support.google.com/tagmanager/answer/7003315).

> 📘 Note
>
> The steps described in this section relate to a purchase event but are relevant for any event that you wish to send.

### 1. Creating event parameter variables

Event parameter variables allow Google Tag Manager to obtain data from the event. When the event is sent, the AppsFlyer ID and Dev Key variables are passed along with it. Google Tag Manager then evaluates their value and this is how it obtains them. The data from the event has two functions:

1. Provide Google Tag Manager with the AppsFlyer ID and Dev Key
2. Provide Google Tag Manager with the event name and event parameters

<Tabs>
<Tab title="AppsFlyer Device ID and Dev Key">

Whenever Google Tag Manager sends an event to AppsFlyer, it must send it with the AppsFlyer ID and Dev Key. The Dev Key allows Google Tag Manager to communicate with AppsFlyer servers. The AppsFlyer ID lets AppsFlyer know what user to attribute the event to.

1. In Google Tag Manager, click **_Variables_** and then _**New**_
2. Name the variable as "AppsFlyer Dev Key" and click on _**Variable Configuration**_
3. Choose _**Event Parameter**_
4. Choose _**Custom Parameter**_
5. In the _**Event Parameter**_ field, enter "dev\_key" and save
6. Repeat the process for AppsFlyer ID as well - name the variable as "AppsFlyer Device ID" and enter "af\_id" in the _**Event Parameter**_ field

**Example**

Below is a screenshot from GTM UI. It shows the event parameter's final configuration:

![event_parameter_variable_dev_key.png](https://files.readme.io/f5030ce110ec4459f673a4088c2c09a4e3f90a35976f4fbfccb8750cb112e69e-49839295695889.png)

> ❗️ Important!
>
> For iOS, an additional Event Parameter should be configured. Follow the same flow as listed above. Create a variable and name it "Apple App ID". In the Event Parameter field, enter "apple\_app\_id" and save.

The next step is to create and set AppsFlyer ID and Dev Key variables inside the app. This step is discussed in the [Sending Events](https://support.appsflyer.com/hc/articles/4410481550609#configuring-events-in-the-app) Section.

</Tab>
<Tab title="Revenue and Price">

Most in-app events require event value parameters. In this case, it is the af\_revenue and af\_price parameters but you can send any event parameters. Now that the event is configured in the app, revenue and price variables need to be created in Google Tag Manager. These variables are used later on in the Purchase event tag.

1. In Google Tag Manager, create two Event Parameter variables for af\_revenue and af\_price
2. For "af\_revenue", name the variable "Revenue" and set the _**Event Parameter Key**_ to "af\_revenue"
3. For "af\_price", name the variable "Price" and set the _**Event Parameter Key**_ to "af\_price"

**Example**

Below is a screenshot from GTM UI. It shows the event parameter's final configuration:

![event_parameter_variable_revenue.png](https://files.readme.io/40e6ccd8d2df9370210847d6ff54a5a44c04f295dac9ece18dac715e5fc335a1-49839295696657.png)

> 📘 Note
>
> The example here shows how to create event parameter variables for Revenue and Price event parameters. You can create event parameter variables for any kind of event parameter, according to the event that is sent.

</Tab>
</Tabs>

### 2. Creating a trigger for the purchase event

In order for Google Tag Manager to know if the event should be sent to AppsFlyer, a trigger for the event must be configured.

1. In Google Tag Manager Click on _**Triggers**_ and then _**New**_
2. Name the trigger as "Purchase" and click on _**Trigger Configuration**_
3. Choose _**Custom**_
4. Choose _**Some Events**_
5. In the conditions, set the trigger to fire when the _**Event Name**_ equals "af\_purchase"
6. Click _**Save**_

**Example**

Below is a screenshot from GTM UI. It shows the trigger's final configuration:

![trigger_purchase_event.png](https://files.readme.io/ef2e70fb2aa0b25f1243d6fa565e3cdb1df407fd2d4b3105dee412ccad7f2704-49839256428689.png)

### 3. Creating a tag for the purchase event

Now that the required variables and the event trigger are set, you can create the Purchase event tag.

01. In Google Tag Manager click on _**Tags**_ and then _**New**_
02. Name the tag as "Purchase" and click on _**Tag Configuration**_
03. Choose _**AppsFlyer**_
04. In the _**Application ID**_ field, set the built-in variable the App ID

    > ❗️ Important!
    >
    > For iOS, set the "apple\_app\_id" custom variable in the _**Application ID**_ field.

05. In the _**Dev Key**_ field, choose the "AppsFlyer Dev Key" variable
06. In the _**AppsFlyer Device ID**_ field, choose the "AppsFlyer Device ID" variable
07. In the Event Name field, set the built-in variable _**Event Name**_
08. In the _**Event Currency**_ field, set your currency code e.g. USD
09. Click twice on _**Add Event Value**_
10. Set the following:
    * _**Key**_: af\_revenue, _**Value**_: choose the Event Parameter Variable "Revenue"
    * _**Key**_: af\_price, _**Value**_: choose the Event Parameter Variable "Price"
11. In the _**Triggering**_ section, set the _**Firing Trigger**_ to the "Purchase" event trigger
12. Click _**Save**_

**Example**

Below is a screenshot from GTM UI. It shows the Tag's final configuration:

![purchase_tag.png](https://files.readme.io/893bdf6ce65bf6bd0435f4e7c02ff044b35e5e14ebea131f547040f763d7512d-49839295697169.png)

### 4. Publishing the tag manager container

After each change in Google Tag Manager (adding tags etc.) you must download the container and add it to your app root folder:

- Android - app/src/main/assets/containers
- iOS - root folder/container

Build and install the application on a test device and check the debug log to see that the event is triggered and sent.