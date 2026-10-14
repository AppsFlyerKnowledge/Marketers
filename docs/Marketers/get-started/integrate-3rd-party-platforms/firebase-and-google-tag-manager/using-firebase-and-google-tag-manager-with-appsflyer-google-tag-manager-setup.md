---
title: "Using Firebase and Google Tag Manager with AppsFlyer—Google Tag Manager setup"
excerpt: "Instructions for setting up event sending reported via Firebase SDK to AppsFlyer in Google Tag Manager."
x-zendesk:
  id: 4410481509393
  url: https://support.appsflyer.com/hc/en-us/articles/4410481509393-Using-Firebase-and-Google-Tag-Manager-with-AppsFlyer-Google-Tag-Manager-setup
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  position: 5
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Developers, Marketers, Loc In Prog, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2021-11-09T10:28:45Z'
  edited_at: '2026-08-14T16:22:49Z'
---
## Google Tag Manager setup

This section discusses the necessary setup in Google Tag Manager (GTM) UI. All the steps described in this section are required in order for GTM to send events to AppsFlyer. Follow the steps in the order they are listed.

The following steps are for Google Tag Manager for mobile apps. If the UI that you see in your Google Tag Manager is different than the screenshots in the various steps, check the following:

1. Your Google Tag Manager container is configured for mobile apps.
2. The container is v5. For more information, click [here](https://support.google.com/tagmanager/answer/7003315).

**Note**

The steps described in this section relate to a purchase event but are relevant for any event that you wish to send.

<Accordion title="1. Creating event parameter variables">

Event parameter variables allow Google Tag Manager to obtain data from the event. When the event is sent, the AppsFlyer ID and Dev Key variables are passed along with it. Google Tag Manager then evaluates their value and this is how it obtains them. The data from the event has two functions:

1. Provide Google Tag Manager with the AppsFlyer ID and Dev Key
2. Provide Google Tag Manager with the event name and event parameters

<Accordion title="AppsFlyer Device ID and Dev Key">

Whenever Google Tag Manager sends an event to AppsFlyer, it must send it with the AppsFlyer ID and Dev Key. The Dev Key allows Google Tag Manager to communicate with AppsFlyer servers. The AppsFlyer ID lets AppsFlyer know what user to attribute the event to.

1. In Google Tag Manager, click ***Variables*** and then ***New***
2. Name the variable as "AppsFlyer Dev Key" and click on ***Variable Configuration***
3. Choose ***Event Parameter***
4. Choose ***Custom Parameter***
5. In the ***Event Parameter*** field, enter "dev\_key" and save
6. Repeat the process for AppsFlyer ID as well - name the variable as "AppsFlyer Device ID" and enter "af\_id" in the ***Event Parameter*** field

**Example**

Below is a screenshot from GTM UI. It shows the event parameter's final configuration:

![event_parameter_variable_dev_key.png](https://files.readme.io/f5030ce110ec4459f673a4088c2c09a4e3f90a35976f4fbfccb8750cb112e69e-49839295695889.png)

**Important!**

For iOS, an additional Event Parameter should be configured. Follow the same flow as listed above. Create a variable and name it "Apple App ID". In the Event Parameter field, enter "apple\_app\_id" and save.

The next step is to create and set AppsFlyer ID and Dev Key variables inside the app. This step is discussed in the [Sending Events](/docs/using-firebase-and-google-tag-manager-with-appsflyer-sending-installs-and-events#configuring-events-in-the-app) Section.

</Accordion>

<Accordion title="Revenue and Price">

Most in-app events require event value parameters. In this case, it is the af\_revenue and af\_price parameters but you can send any event parameters. Now that the event is configured in the app, revenue and price variables need to be created in Google Tag Manager. These variables are used later on in the Purchase event tag.

1. In Google Tag Manager, create two Event Parameter variables for af\_revenue and af\_price
2. For "af\_revenue", name the variable "Revenue" and set the ***Event Parameter Key*** to "af\_revenue"
3. For "af\_price", name the variable "Price" and set the ***Event Parameter Key*** to "af\_price"

**Example**

Below is a screenshot from GTM UI. It shows the event parameter's final configuration:

![event_parameter_variable_revenue.png](https://files.readme.io/40e6ccd8d2df9370210847d6ff54a5a44c04f295dac9ece18dac715e5fc335a1-49839295696657.png)

**Note**

The example here shows how to create event parameter variables for Revenue and Price event parameters. You can create event parameter variables for any kind of event parameter, according to the event that is sent.

</Accordion>

</Accordion>

<Accordion title="2. Creating a trigger for the purchase event">

In order for Google Tag Manager to know if the event should be sent to AppsFlyer, a trigger for the event must be configured.

1. In Google Tag Manager Click on ***Triggers*** and then ***New***
2. Name the trigger as "Purchase" and click on ***Trigger Configuration***
3. Choose ***Custom***
4. Choose ***Some Events***
5. In the conditions, set the trigger to fire when the ***Event Name*** equals "af\_purchase"
6. Click ***Save***

**Example**

Below is a screenshot from GTM UI. It shows the trigger's final configuration:

![trigger_purchase_event.png](https://files.readme.io/ef2e70fb2aa0b25f1243d6fa565e3cdb1df407fd2d4b3105dee412ccad7f2704-49839256428689.png)

</Accordion>

<Accordion title="3. Creating a tag for the purchase event">

Now that the required variables and the event trigger are set, you can create the Purchase event tag.

1. In Google Tag Manager click on ***Tags*** and then ***New***
2. Name the tag as "Purchase" and click on ***Tag Configuration***
3. Choose ***AppsFlyer***
4. In the ***Application ID*** field, set the built-in variable the App ID

   **Important!**

   For iOS, set the "apple\_app\_id" custom variable in the ***Application ID*** field.
5. In the ***Dev Key*** field, choose the "AppsFlyer Dev Key" variable
6. In the ***AppsFlyer Device ID*** field, choose the "AppsFlyer Device ID" variable
7. In the Event Name field, set the built-in variable ***Event Name***
8. In the ***Event Currency*** field, set your currency code e.g. USD
9. Click twice on ***Add Event Value***
10. Set the following:  
    ***Key***: af\_revenue, ***Value***: choose the Event Parameter Variable "Revenue"  
    ***Key***: af\_price, ***Value***: choose the Event Parameter Variable "Price"
11. In the ***Triggering*** section, set the ***Firing Trigger***to the "Purchase" event trigger
12. Click ***Save***

**Example**

Below is a screenshot from GTM UI. It shows the Tag's final configuration:

![purchase_tag.png](https://files.readme.io/893bdf6ce65bf6bd0435f4e7c02ff044b35e5e14ebea131f547040f763d7512d-49839295697169.png)

</Accordion>

<Accordion title="4. Publishing the tag manager container">

After each change in Google Tag Manager (adding tags etc.) you must download the container and add it to your app root folder:

* Android - app/src/main/assets/containers
* iOS - root folder/container

Build and install the application on a test device and check the debug log to see that the event is triggered and sent.

</Accordion>
